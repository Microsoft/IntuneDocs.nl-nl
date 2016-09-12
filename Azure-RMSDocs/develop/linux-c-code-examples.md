---
title: Linux-codevoorbeelden | Azure RMS
description: "In dit onderwerp vindt u belangrijke scenario’s en code-elementen voor de Linux-versie van de RMS SDK."
keywords: 
author: bruceperlerms
manager: mbaldwin
ms.date: 08/24/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 0F7714CA-1D3E-4846-B187-739825B7DE26
audience: developer
ms.reviewer: shubhamp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 024a29d7c7db2e4c0578a95c93e22f8e7a5b173e
ms.openlocfilehash: 0d63a47f15d4ef08d9e17a0416f9d6f06536b6aa


---

# Linux-codevoorbeelden

In dit onderwerp vindt u belangrijke scenario’s en code-elementen voor de Linux-versie van de RMS SDK.

De onderstaande codefragmenten maken deel uit van de voorbeeldtoepassingen *rms\_sample* en *rmsauth\_sample*. Voor meer informatie raadpleegt u de [voorbeelden](https://github.com/AzureAD/rms-sdk-for-cpp/tree/master/samples) in de GitHub-opslagplaats.

## Scenario: toegang verkrijgen tot beveiligingsbeleidgegevens van een beveiligd bestand

**Een met RMS beveiligd bestand openen en lezen**
**Bron**: [rms\_sample/mainwindow.cpp](https://github.com/AzureAD/rms-sdk-for-cpp/tree/master/samples/rms_sample)

**Beschrijving**: nadat er een bestandsnaam is opgehaald bij de gebruiker, de certificaten zijn gelezen (zie *MainWindow::addCertificates*), de verificatiecallback is ingesteld met client-id en doorverwijzings-URL, en *ConvertFromPFile* is aangeroepen (zie het volgende codevoorbeeld), worden de naam van het beveiligingsbeleid, de beschrijving en de geldigheidsdatum van de inhoud uitgelezen.

**C++**:

    void MainWindow::ConvertFromPFILE(const string& fileIn,
        const string& clientId,
        const string& redirectUrl,
        const string& clientEmail) 
    {
    // add trusted certificates using HttpHelpers of RMS and Auth SDKs
    addCertificates();
    
    // create shared in/out streams
    auto inFile = make_shared<ifstream>(
    fileIn, ios_base::in | ios_base::binary);
    
    if (!inFile->is_open()) {
     AddLog("ERROR: Failed to open ", fileIn.c_str());
    return;
    }
    
    string fileOut;
    
    // generate output filename
    auto pos = fileIn.find_last_of('.');
    
    if (pos != string::npos) {
     fileOut = fileIn.substr(0, pos);
    }
    
     // create streams
    auto outFile = make_shared<fstream>(
    fileOut, ios_base::in | ios_base::out | ios_base::trunc | ios_base::binary);
    
    if (!outFile->is_open()) {
     AddLog("ERROR: Failed to open ", fileOut.c_str());
     return;
      }
    
    try
    {
    // create authentication context
    AuthCallback auth(clientId, redirectUrl);
    
    // process convertion
    auto pfs = PFileConverter::ConvertFromPFile(
      clientEmail,
      inFile,
      outFile,
      auth,
      this->consent);
    
    AddLog("Successfully converted to ", fileOut.c_str());
    }
    catch (const rmsauth::Exception& e)
    {
    AddLog("ERROR: ", e.error().c_str());
    }
    catch (const rmscore::exceptions::RMSException& e) {
    AddLog("ERROR: ", e.what());
    }
    inFile->close();
    outFile->close();
    }

**Een beveiligde bestandsstroom maken**
**Bron**: [rms\_sample/pfileconverter.cpp](https://github.com/AzureAD/rms-sdk-for-cpp/tree/master/samples/rms_sample)

**Beschrijving**: met deze methode maakt u een beveiligde bestandsstroom vanaf de backing-stream via de SDK-methode *ProtectedFileStream::Aquire*. Vervolgens worden bestanden geretourneerd naar de aanroeper.

**C++**:

    shared_ptr<GetProtectedFileStreamResult>PFileConverter::ConvertFromPFile(
    const string           & userId,
    shared_ptr<istream>      inStream,
    shared_ptr<iostream>     outStream,
    IAuthenticationCallback& auth,
    IConsentCallback       & consent)
    {
    auto inIStream = rmscrypto::api::CreateStreamFromStdStream(inStream);
    
    auto fsResult = ProtectedFileStream::Acquire(
    inIStream,
    userId,
    auth,
    consent,
    POL_None,
    static_cast<ResponseCacheFlags>(RESPONSE_CACHE_INMEMORY
                                    | RESPONSE_CACHE_ONDISK));
    
    if ((fsResult.get() != nullptr) && (fsResult->m_status == Success) &&
      (fsResult->m_stream != nullptr)) {
    auto pfs = fsResult->m_stream;
    
    // preparing
    readPosition  = 0;
    writePosition = 0;
    totalSize     = pfs->Size();
    
    // start threads
    for (size_t i = 0; i < THREADS_NUM; ++i) {
      threadPool.push_back(thread(WorkerThread,
                                  static_pointer_cast<iostream>(outStream), pfs,
                                  false));
    }
    
    for (thread& t: threadPool) {
      if (t.joinable()) {
        t.join();
      }
    }
    }
      return fsResult;
    }

## Scenario: een nieuw beveiligd bestand maken met behulp van een sjabloon

**Een bestand beveiligen met een door de gebruiker geselecteerde sjabloon**
**Bron**: [rms\_sample/mainwindow.cpp](https://github.com/AzureAD/rms-sdk-for-cpp/tree/master/samples/rms_sample)

**Beschrijving**: nadat er een bestandsnaam is opgehaald bij de gebruiker, de certificaten zijn gelezen (zie *MainWindow::addCertificates*) en de verificatiecallback is ingesteld met client-id en doorverwijzings-URL, wordt het geselecteerde bestand beveiligd door *ConvertFromPFile* aan te roepen (zie het volgende codevoorbeeld).

**C++**:

    void MainWindow::ConvertToPFILEUsingTemplates(const string& fileIn,
                                              const string& clientId,
                                              const string& redirectUrl,
                                              const string& clientEmail) 
    {
    // generate output filename
    string fileOut = fileIn + ".pfile";
    
    // add trusted certificates using HttpHelpers of RMS and Auth SDKs
    addCertificates();
    
    // create shared in/out streams
    auto inFile = make_shared<ifstream>(
    fileIn, ios_base::in | ios_base::binary);
    auto outFile = make_shared<fstream>(
    fileOut, ios_base::in | ios_base::out | ios_base::trunc | ios_base::binary);
    
    if (!inFile->is_open()) {
    AddLog("ERROR: Failed to open ", fileIn.c_str());
    return;
    }
    
    if (!outFile->is_open()) {
    AddLog("ERROR: Failed to open ", fileOut.c_str());
    return;
    }
    
    // find file extension
    string fileExt;
    auto   pos = fileIn.find_last_of('.');
    
    if (pos != string::npos) {
    fileExt = fileIn.substr(pos);
    }
    
    try {
    // create authentication callback
    AuthCallback auth(clientId, redirectUrl);
    
    // process convertion
    PFileConverter::ConvertToPFileTemplates(
      clientEmail, inFile, fileExt, outFile, auth,
      this->consent, this->templates);
    
    AddLog("Successfully converted to ", fileOut.c_str());
    }
   catch (const rmsauth::Exception& e) { AddLog("ERROR: ", e.error().c_str()); outFile->close(); remove(fileOut.c_str()); } catch (const rmscore::exceptions::RMSException& e) { AddLog("ERROR: ", e.what());
    
    outFile->close();
    remove(fileOut.c_str());
    }
    inFile->close();
    outFile->close();
    }


**Een bestand beveiligen met een beleid dat is gemaakt op basis van een sjabloon**
**Bron**: [rms\_sample/pfileconverter.cpp](https://github.com/AzureAD/rms-sdk-for-cpp/tree/master/samples/rms_sample)

**Beschrijving**: de lijst met sjablonen die zijn gekoppeld aan de gebruiker, wordt opgehaald en de geselecteerde sjabloon wordt vervolgens gebruikt voor het maken van beleid, dat op zijn beurt wordt gebruikt om het bestand te beveiligen.

**C++**:

    void PFileConverter::ConvertToPFileTemplates(const string           & userId,
                                             shared_ptr<istream>      inStream,
                                             const string           & fileExt,
                                             std::shared_ptr<iostream>outStream,
                                             IAuthenticationCallback& auth,
                                             IConsentCallback& /*consent*/,
                                             ITemplatesCallback     & templ)
    {
    auto templates = TemplateDescriptor::GetTemplateList(userId, auth);
    
    rmscore::modernapi::AppDataHashMap signedData;
    
    size_t pos = templ.SelectTemplate(templates);
    
    if (pos < templates.size()) {
    auto policy = UserPolicy::CreateFromTemplateDescriptor(
      templates[pos],
      userId,
      auth,
      USER_AllowAuditedExtraction,
      signedData);
   
    ConvertToPFileUsingPolicy(policy, inStream, fileExt, outStream);
    }
    }

**Een bestand beveiligen met het opgegeven beleid**
**Bron**: [rms\_sample/pfileconverter.cpp](https://github.com/AzureAD/rms-sdk-for-cpp/tree/master/samples/rms_sample)

**Beschrijving**: hiermee maakt u een beveiligde bestandsstroom met het opgegeven beleid en beveiligt u het bestand vervolgens.

**C++**:

    void PFileConverter::ConvertToPFileUsingPolicy(shared_ptr<UserPolicy>   policy,
                                               shared_ptr<istream>      inStream,
                                               const string           & fileExt,
                                               std::shared_ptr<iostream>outStream)
    {
    if (policy.get() != nullptr) {
    auto outIStream = rmscrypto::api::CreateStreamFromStdStream(outStream);
    auto pStream    = ProtectedFileStream::Create(policy, outIStream, fileExt);
    
    // preparing
    readPosition  = 0;
    writePosition = pStream->Size();
    
    inStream->seekg(0, ios::end);
    totalSize = inStream->tellg();
    
    // start threads
    for (size_t i = 0; i < THREADS_NUM; ++i) {
      threadPool.push_back(thread(WorkerThread,
                                  static_pointer_cast<iostream>(inStream),
                                  pStream,
                                  true));
    }
    
    for (thread& t: threadPool) {
      if (t.joinable()) {
        t.join();
      }
    }
    
    pStream->Flush();
    }
    


## Scenario: een bestand beveiligen met aangepaste beveiliging

**Een bestand beveiligen met aangepaste beveiliging**
**Bron**: [rms\_sample/mainwindow.cpp](https://github.com/AzureAD/rms-sdk-for-cpp/tree/master/samples/rms_sample)

**Beschrijving**: nadat er een bestandsnaam is opgehaald bij de gebruiker, de certificaten zijn gelezen (zie *MainWindow::addCertificates*), de rechteninformatie van de gebruiker is verzameld en de verificatiecallback is ingesteld met client-id en doorverwijzings-URL, wordt het geselecteerde bestand beveiligd door *ConvertToPFilePredefinedRights* aan te roepen (zie het volgende codevoorbeeld).

**C++**:

    void MainWindow::ConvertToPFILEUsingRights(const string            & fileIn,
                                           const vector<UserRights>& userRights,
                                           const string            & clientId,
                                           const string            & redirectUrl,
                                           const string            & clientEmail)
    {
    // generate output filename
    string fileOut = fileIn + ".pfile";
    
    // add trusted certificates using HttpHelpers of RMS and Auth SDKs
    addCertificates();
    
    // create shared in/out streams
    auto inFile = make_shared<ifstream>(
    fileIn, ios_base::in | ios_base::binary);
    auto outFile = make_shared<fstream>(
    fileOut, ios_base::in | ios_base::out | ios_base::trunc | ios_base::binary);
    
    if (!inFile->is_open()) {
    AddLog("ERROR: Failed to open ", fileIn.c_str());
    return;
    }
    
    if (!outFile->is_open()) {
    AddLog("ERROR: Failed to open ", fileOut.c_str());
    return;
    }
    
    // find file extension
    string fileExt;
    auto   pos = fileIn.find_last_of('.');
    
    if (pos != string::npos) {
    fileExt = fileIn.substr(pos);
    }
    
    // is anything to add
    if (userRights.size() == 0) {
    AddLog("ERROR: ", "Please fill email and check rights");
    return;
    }
    
    
    try {
    // create authentication callback
    AuthCallback auth(clientId, redirectUrl);
    
    // process convertion
    PFileConverter::ConvertToPFilePredefinedRights(
      clientEmail,
      inFile,
      fileExt,
      outFile,
      auth,
      this->consent,
      userRights);
    
    AddLog("Successfully converted to ", fileOut.c_str());
    }
    catch (const rmsauth::Exception& e) {
    AddLog("ERROR: ", e.error().c_str());
    
    outFile->close();
    remove(fileOut.c_str());
    }
    catch (const rmscore::exceptions::RMSException& e) {
    AddLog("ERROR: ", e.what());
    
    outFile->close();
    remove(fileOut.c_str());
    }
    inFile->close();
    outFile->close();
    }


**Een beveiligingsbeleid maken en een gebruiker geselecteerde rechten geven**
**Bron**: [rms\_sample/pfileconverter.cpp](https://github.com/AzureAD/rms-sdk-for-cpp/tree/master/samples/rms_sample)

**Beschrijving**: hiermee maakt u een beleidsdescriptor en vult u deze met de rechteninformatie van de gebruiker. Gebruik vervolgens de beleidsdescriptor om gebruikersbeleid te maken. Dit beleid wordt gebruikt voor het beveiligen van het geselecteerde bestand door *ConvertToPFileUsingPolicy* aan te roepen (dit wordt beschreven in een eerder gedeelte van dit onderwerp).

**C++**:

    void PFileConverter::ConvertToPFilePredefinedRights(
    const string            & userId,
    shared_ptr<istream>       inStream,
    const string            & fileExt,
    shared_ptr<iostream>      outStream,
    IAuthenticationCallback & auth,
    IConsentCallback& /*consent*/,
    const vector<UserRights>& userRights)
    {
    auto endValidation = chrono::system_clock::now() + chrono::hours(48);
    
    
    PolicyDescriptor desc(userRights);
    
    desc.Referrer(make_shared<string>("https://client.test.app"));
    desc.ContentValidUntil(endValidation);
    desc.AllowOfflineAccess(false);
    desc.Name("Test Name");
    desc.Description("Test Description");
    
    auto policy = UserPolicy::Create(desc, userId, auth,
                                   USER_AllowAuditedExtraction);
    ConvertToPFileUsingPolicy(policy, inStream, fileExt, outStream);
    

## WorkerThread: een ondersteunende methode


De *WorkerThread()*-methode wordt aangeroepen in twee van de vorige voorbeeldscenario’s: **Een beveiligde bestandsstroom maken** en **Een bestand beschermen met beleid**. Dat gebeurt op de volgende manier:

**C++**:

    threadPool.push_back(thread(WorkerThread,
                                  static_pointer_cast<iostream>(outStream), pfs,
                                  false));


**Ondersteunende methode, WorkerThread()**

**C++**:

    static mutex   threadLocker;
    static int64_t totalSize     = 0;
    static int64_t readPosition  = 0;
    static int64_t writePosition = 0;
    static vector<thread> threadPool;
    
    static void WorkerThread(shared_ptr<iostream>           stdStream,
                         shared_ptr<ProtectedFileStream>pStream,
                         bool                           modeWrite) {
    vector<uint8_t> buffer(4096);
    int64_t bufferSize = static_cast<int64_t>(buffer.size());
    
    while (totalSize - readPosition > 0) {
    // lock
    threadLocker.lock();
    
    // check remain
    if (totalSize - readPosition <= 0) {
      threadLocker.unlock();
      return;
    }
    
    // get read/write offset
    int64_t offsetRead  = readPosition;
    int64_t offsetWrite = writePosition;
    int64_t toProcess   = min(bufferSize, totalSize - readPosition);
    readPosition  += toProcess;
    writePosition += toProcess;
    
    // no need to lock more
    threadLocker.unlock();
    
    if (modeWrite) {
      // stdStream is not thread safe!!!
      try {
        threadLocker.lock();
    
        stdStream->seekg(offsetRead);
        stdStream->read(reinterpret_cast<char *>(&buffer[0]), toProcess);
        threadLocker.unlock();
        auto written =
          pStream->WriteAsync(
            buffer.data(), toProcess, offsetWrite, std::launch::deferred).get();
    
        if (written != toProcess) {
          throw rmscore::exceptions::RMSStreamException("Error while writing data");
        }
      }
      catch (exception& e) {
        qDebug() << "Exception: " << e.what();
      }
    } else {
      auto read =
        pStream->ReadAsync(&buffer[0],
                           toProcess,
                           offsetRead,
                           std::launch::deferred).get();
    
      if (read == 0) {
        break;
      }
    
      try {
        // stdStream is not thread safe!!!
        threadLocker.lock();
    
        // seek to write
        stdStream->seekp(offsetWrite);
        stdStream->write(reinterpret_cast<const char *>(buffer.data()), read);
        threadLocker.unlock();
      }
      catch (exception& e) {
        qDebug() << "Exception: " << e.what();
      }
    }
    }
    }


## Scenario: RMS-verificatie

In de volgende voorbeelden ziet u twee verschillende manieren van verificatie: het Azure oAuth2-verificatietoken ophalen mét en zonder gebruikersinterface.
**oAuth2-verificatietoken ophalen met UI**
**Bron**: [rmsauth\_sample/mainwindow.cpp](https://github.com/AzureAD/rms-sdk-for-cpp/tree/master/samples/rmsauth_sample)

**Stap 1**: maak een gedeeld punt van een **rmsauth::FileCache**-object.
Beschrijving: u kunt een cachepad instellen of de standaardoptie gebruiken.

**C++**:

    auto FileCachePtr = std::make_shared< rmsauth::FileCache>();


**Stap 2**: **rmsauth::AuthenticationContext**-object maken Beschrijving: *URI van instantie* voor Azure en *FileCache*-object opgeven.

**C++**:

    AuthenticationContext authContext(
                              std::string(“https://sts.aadrm.com/_sts/oauth/authorize”),
                              AuthorityValidationType::False,
                              FileCachePtr);


**Stap 3**: **aquireToken**-methode van het **authContext**-objecten aanroepen en de volgende parameters opgeven: Beschrijving:

-   *Gevraagde resource*: beveiligde resource die u wilt openen
-   *Unieke id van client*: meestal een GUID
-   *Omleidings-URI*: de URI die wordt gebruikt nadat het verificatietoken is opgehaald
-   *Verificatiepromptgedrag*: als u **PromptBehavior::Auto** instelt, probeert de bibliotheek het cachegeheugen te gebruiken en indien nodig het token te vernieuwen
-   *Gebruikers-id*: de gebruikersnaam die wordt weergegeven in het promptvenster

**C++**:

    auto result = authContext.acquireToken(
                std::string(“api.aadrm.com”),
                std::string(“4a63455a-cfa1-4ac6-bd2e-0d046cf1c3f7”),
                std::string(“https://client.test.app”),
                PromptBehavior::Auto,
                std::string(“john.smith@msopentechtest01.onmicrosoft.com”));


**Stap 4**: toegangstoken ophalen uit resultaat Beschrijving: methode **result-> accessToken()** aanroepen

**Opmerking:** met alle verificatiemethoden voor de bibliotheek kan **rmsauth::Exception** worden gegenereerd

 
**oAuth2-verificatietoken ophalen zonder UI**
**Bron**: [rmsauth\_sample/mainwindow.cpp](https://github.com/AzureAD/rms-sdk-for-cpp/tree/master/samples/rmsauth_sample)

**Stap 1**: een gedeeld punt maken van het **rmsauth::FileCache**-object Beschrijving: u kunt het cachepad instellen of de standaardwaarde gebruiken

**C++**:

    auto FileCachePtr = std::make_shared< rmsauth::FileCache>();


**Stap 2**: **UserCredential**-object maken Beschrijving: *gebruikersaanmelding* en *wachtwoord* opgeven

**C++**:

    auto userCred = std::make_shared<UserCredential>("john.smith@msopentechtest01.onmicrosoft.com",
                                                 "SomePass");


**Stap 3**: object **rmsauth::AuthenticationContext** maken Beschrijving: *URI* van Azure-instantie en *FileCache*-object opgeven

**C++**:

    AuthenticationContext authContext(
                        std::string(“https://sts.aadrm.com/_sts/oauth/authorize”),
                        AuthorityValidationType::False,
                        FileCachePtr);


**Stap 4**: roep de methode **aquireToken** van het object **authContext** aan en geef parameters op:
-   *Gevraagde resource*: beveiligde resource die u wilt openen
-   *Unieke id van client*: meestal een GUID
-   *Gebruikersreferenties*: hiermee geeft u het gemaakte object door

**C++**:

    auto result = authContext.acquireToken(
                std::string(“api.aadrm.com”),
                std::string(“4a63455a-cfa1-4ac6-bd2e-0d046cf1c3f7”),
                userCred);


**Stap 5**: toegangstoken ophalen uit resultaat Beschrijving: methode **result-> accessToken()** aanroepen

**Opmerking:** met alle verificatiemethoden voor de bibliotheek kan **rmsauth::Exception** worden gegenereerd




<!--HONumber=Aug16_HO4-->


