---
title: Linux-codevoorbeelden | Azure RMS
description: "In dit onderwerp vindt u belangrijke scenario’s en code-elementen voor de Linux-versie van de RMS SDK."
keywords: 
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 0F7714CA-1D3E-4846-B187-739825B7DE26
audience: developer
ms.reviewer: shubhamp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 79e58b8092ea7cb057229d4c464d79f3694296e6
ms.openlocfilehash: ace7103cfb44d84a7dd6bf64f57c2a47530117e0


---

# Linux-codevoorbeelden

In dit onderwerp vindt u belangrijke scenario’s en code-elementen voor de Linux-versie van de RMS SDK.

De onderstaande codefragmenten maken deel uit van de voorbeeldtoepassingen *rms\_sample* en *rmsauth\_sample*. Voor meer informatie raadpleegt u de [voorbeelden](https://github.com/AzureAD/rms-sdk-for-cpp/tree/master/samples) in de GitHub-opslagplaats.

## Scenario: toegang verkrijgen tot beveiligingsbeleidgegevens van een beveiligd bestand

**Een met RMS beveiligd bestand openen en lezen**
**Bron**: [rms\_sample/mainwindow.cpp](https://github.com/AzureAD/rms-sdk-for-cpp/tree/master/samples/rms_sample)

**Beschrijving**: nadat er een bestandsnaam is opgehaald bij de gebruiker, de certificaten zijn gelezen (zie *MainWindow::addCertificates*), de verificatiecallback is ingesteld met client-id en doorverwijzings-URL, en *ConvertFromPFile* is aangeroepen (zie het volgende codevoorbeeld), worden de naam van het beveiligingsbeleid, de beschrijving en de geldigheidsdatum van de inhoud uitgelezen.

**C++**:

    void MainWindow::ConvertFromPFILE(const string&amp; fileIn,
        const string&amp; clientId,
        const string&amp; redirectUrl,
        const string&amp; clientEmail) 
    {
    // add trusted certificates using HttpHelpers of RMS and Auth SDKs
    addCertificates();
    
    // create shared in/out streams
    auto inFile = make_shared&lt;ifstream&gt;(
    fileIn, ios_base::in | ios_base::binary);
    
    if (!inFile-&gt;is_open()) {
     AddLog(&quot;ERROR: Failed to open &quot;, fileIn.c_str());
    return;
    }
    
    string fileOut;
    
    // generate output filename
    auto pos = fileIn.find_last_of(&#39;.&#39;);
    
    if (pos != string::npos) {
     fileOut = fileIn.substr(0, pos);
    }
    
     // create streams
    auto outFile = make_shared&lt;fstream&gt;(
    fileOut, ios_base::in | ios_base::out | ios_base::trunc | ios_base::binary);
    
    if (!outFile-&gt;is_open()) {
     AddLog(&quot;ERROR: Failed to open &quot;, fileOut.c_str());
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
      this-&gt;consent);
    
    AddLog(&quot;Successfully converted to &quot;, fileOut.c_str());
    }
    catch (const rmsauth::Exception&amp; e)
    {
    AddLog(&quot;ERROR: &quot;, e.error().c_str());
    }
    catch (const rmscore::exceptions::RMSException&amp; e) {
    AddLog(&quot;ERROR: &quot;, e.what());
    }
    inFile-&gt;close();
    outFile-&gt;close();
    }

**Een beveiligde bestandsstroom maken**
**Bron**: [rms\_sample/pfileconverter.cpp](https://github.com/AzureAD/rms-sdk-for-cpp/tree/master/samples/rms_sample)

**Beschrijving**: met deze methode maakt u een beveiligde bestandsstroom vanaf de backing-stream via de SDK-methode *ProtectedFileStream::Aquire*. Vervolgens worden bestanden geretourneerd naar de aanroeper.

**C++**:

    shared_ptr&lt;GetProtectedFileStreamResult&gt;PFileConverter::ConvertFromPFile(
    const string           &amp; userId,
    shared_ptr&lt;istream&gt;      inStream,
    shared_ptr&lt;iostream&gt;     outStream,
    IAuthenticationCallback&amp; auth,
    IConsentCallback       &amp; consent)
    {
    auto inIStream = rmscrypto::api::CreateStreamFromStdStream(inStream);
    
    auto fsResult = ProtectedFileStream::Acquire(
    inIStream,
    userId,
    auth,
    consent,
    POL_None,
    static_cast&lt;ResponseCacheFlags&gt;(RESPONSE_CACHE_INMEMORY
                                    | RESPONSE_CACHE_ONDISK));
    
    if ((fsResult.get() != nullptr) &amp;&amp; (fsResult-&gt;m_status == Success) &amp;&amp;
      (fsResult-&gt;m_stream != nullptr)) {
    auto pfs = fsResult-&gt;m_stream;
    
    // preparing
    readPosition  = 0;
    writePosition = 0;
    totalSize     = pfs-&gt;Size();
    
    // start threads
    for (size_t i = 0; i &lt; THREADS_NUM; ++i) {
      threadPool.push_back(thread(WorkerThread,
                                  static_pointer_cast&lt;iostream&gt;(outStream), pfs,
                                  false));
    }
    
    for (thread&amp; t: threadPool) {
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

    void MainWindow::ConvertToPFILEUsingTemplates(const string&amp; fileIn,
                                              const string&amp; clientId,
                                              const string&amp; redirectUrl,
                                              const string&amp; clientEmail) 
    {
    // generate output filename
    string fileOut = fileIn + &quot;.pfile&quot;;
    
    // add trusted certificates using HttpHelpers of RMS and Auth SDKs
    addCertificates();
    
    // create shared in/out streams
    auto inFile = make_shared&lt;ifstream&gt;(
    fileIn, ios_base::in | ios_base::binary);
    auto outFile = make_shared&lt;fstream&gt;(
    fileOut, ios_base::in | ios_base::out | ios_base::trunc | ios_base::binary);
    
    if (!inFile-&gt;is_open()) {
    AddLog(&quot;ERROR: Failed to open &quot;, fileIn.c_str());
    return;
    }
    
    if (!outFile-&gt;is_open()) {
    AddLog(&quot;ERROR: Failed to open &quot;, fileOut.c_str());
    return;
    }
    
    // find file extension
    string fileExt;
    auto   pos = fileIn.find_last_of(&#39;.&#39;);
    
    if (pos != string::npos) {
    fileExt = fileIn.substr(pos);
    }
    
    try {
    // create authentication callback
    AuthCallback auth(clientId, redirectUrl);
    
    // process convertion
    PFileConverter::ConvertToPFileTemplates(
      clientEmail, inFile, fileExt, outFile, auth,
      this-&gt;consent, this-&gt;templates);
    
    AddLog(&quot;Successfully converted to &quot;, fileOut.c_str());
    }
   catch (const rmsauth::Exception&amp; e) { AddLog(&quot;FOUT: &quot;, e.error().c_str()); outFile-&gt;close(); remove(fileOut.c_str()); } catch (const rmscore::exceptions::RMSException&amp; e) { AddLog(&quot;FOUT: &quot;, e.what());
    
    outFile-&gt;close();
    remove(fileOut.c_str());
    }
    inFile-&gt;close();
    outFile-&gt;close();
    }


**Een bestand beveiligen met een beleid dat is gemaakt op basis van een sjabloon**
**Bron**: [rms\_sample/pfileconverter.cpp](https://github.com/AzureAD/rms-sdk-for-cpp/tree/master/samples/rms_sample)

**Beschrijving**: de lijst met sjablonen die zijn gekoppeld aan de gebruiker, wordt opgehaald en de geselecteerde sjabloon wordt vervolgens gebruikt voor het maken van beleid, dat op zijn beurt wordt gebruikt om het bestand te beveiligen.

**C++**:

    void PFileConverter::ConvertToPFileTemplates(const string           &amp; userId,
                                             shared_ptr&lt;istream&gt;      inStream,
                                             const string           &amp; fileExt,
                                             std::shared_ptr&lt;iostream&gt;outStream,
                                             IAuthenticationCallback&amp; auth,
                                             IConsentCallback&amp; /*consent*/,
                                             ITemplatesCallback     &amp; templ)
    {
    auto templates = TemplateDescriptor::GetTemplateList(userId, auth);
    
    rmscore::modernapi::AppDataHashMap signedData;
    
    size_t pos = templ.SelectTemplate(templates);
    
    if (pos &lt; templates.size()) {
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

    void PFileConverter::ConvertToPFileUsingPolicy(shared_ptr&lt;UserPolicy&gt;   policy,
                                               shared_ptr&lt;istream&gt;      inStream,
                                               const string           &amp; fileExt,
                                               std::shared_ptr&lt;iostream&gt;outStream)
    {
    if (policy.get() != nullptr) {
    auto outIStream = rmscrypto::api::CreateStreamFromStdStream(outStream);
    auto pStream    = ProtectedFileStream::Create(policy, outIStream, fileExt);
    
    // preparing
    readPosition  = 0;
    writePosition = pStream-&gt;Size();
    
    inStream-&gt;seekg(0, ios::end);
    totalSize = inStream-&gt;tellg();
    
    // start threads
    for (size_t i = 0; i &lt; THREADS_NUM; ++i) {
      threadPool.push_back(thread(WorkerThread,
                                  static_pointer_cast&lt;iostream&gt;(inStream),
                                  pStream,
                                  true));
    }
    
    for (thread&amp; t: threadPool) {
      if (t.joinable()) {
        t.join();
      }
    }
    
    pStream-&gt;Flush();
    }
    


## Scenario: een bestand beveiligen met aangepaste beveiliging

**Een bestand beveiligen met aangepaste beveiliging**
**Bron**: [rms\_sample/mainwindow.cpp](https://github.com/AzureAD/rms-sdk-for-cpp/tree/master/samples/rms_sample)

**Beschrijving**: nadat er een bestandsnaam is opgehaald bij de gebruiker, de certificaten zijn gelezen (zie *MainWindow::addCertificates*), de rechteninformatie van de gebruiker is verzameld en de verificatiecallback is ingesteld met client-id en doorverwijzings-URL, wordt het geselecteerde bestand beveiligd door *ConvertToPFilePredefinedRights* aan te roepen (zie het volgende codevoorbeeld).

**C++**:

    void MainWindow::ConvertToPFILEUsingRights(const string            &amp; fileIn,
                                           const vector&lt;UserRights&gt;&amp; userRights,
                                           const string            &amp; clientId,
                                           const string            &amp; redirectUrl,
                                           const string            &amp; clientEmail)
    {
    // generate output filename
    string fileOut = fileIn + &quot;.pfile&quot;;
    
    // add trusted certificates using HttpHelpers of RMS and Auth SDKs
    addCertificates();
    
    // create shared in/out streams
    auto inFile = make_shared&lt;ifstream&gt;(
    fileIn, ios_base::in | ios_base::binary);
    auto outFile = make_shared&lt;fstream&gt;(
    fileOut, ios_base::in | ios_base::out | ios_base::trunc | ios_base::binary);
    
    if (!inFile-&gt;is_open()) {
    AddLog(&quot;ERROR: Failed to open &quot;, fileIn.c_str());
    return;
    }
    
    if (!outFile-&gt;is_open()) {
    AddLog(&quot;ERROR: Failed to open &quot;, fileOut.c_str());
    return;
    }
    
    // find file extension
    string fileExt;
    auto   pos = fileIn.find_last_of(&#39;.&#39;);
    
    if (pos != string::npos) {
    fileExt = fileIn.substr(pos);
    }
    
    // is anything to add
    if (userRights.size() == 0) {
    AddLog(&quot;ERROR: &quot;, &quot;Please fill email and check rights&quot;);
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
      this-&gt;consent,
      userRights);
    
    AddLog(&quot;Successfully converted to &quot;, fileOut.c_str());
    }
    catch (const rmsauth::Exception&amp; e) {
    AddLog(&quot;ERROR: &quot;, e.error().c_str());
    
    outFile-&gt;close();
    remove(fileOut.c_str());
    }
    catch (const rmscore::exceptions::RMSException&amp; e) {
    AddLog(&quot;ERROR: &quot;, e.what());
    
    outFile-&gt;close();
    remove(fileOut.c_str());
    }
    inFile-&gt;close();
    outFile-&gt;close();
    }


**Een beveiligingsbeleid maken en een gebruiker geselecteerde rechten geven**
**Bron**: [rms\_sample/pfileconverter.cpp](https://github.com/AzureAD/rms-sdk-for-cpp/tree/master/samples/rms_sample)

**Beschrijving**: hiermee maakt u een beleidsdescriptor en vult u deze met de rechteninformatie van de gebruiker. Gebruik vervolgens de beleidsdescriptor om gebruikersbeleid te maken. Dit beleid wordt gebruikt voor het beveiligen van het geselecteerde bestand door *ConvertToPFileUsingPolicy* aan te roepen (dit wordt beschreven in een eerder gedeelte van dit onderwerp).

**C++**:

    void PFileConverter::ConvertToPFilePredefinedRights(
    const string            &amp; userId,
    shared_ptr&lt;istream&gt;       inStream,
    const string            &amp; fileExt,
    shared_ptr&lt;iostream&gt;      outStream,
    IAuthenticationCallback &amp; auth,
    IConsentCallback&amp; /*consent*/,
    const vector&lt;UserRights&gt;&amp; userRights)
    {
    auto endValidation = chrono::system_clock::now() + chrono::hours(48);
    
    
    PolicyDescriptor desc(userRights);
    
    desc.Referrer(make_shared&lt;string&gt;(&quot;https://client.test.app&quot;));
    desc.ContentValidUntil(endValidation);
    desc.AllowOfflineAccess(false);
    desc.Name(&quot;Test Name&quot;);
    desc.Description(&quot;Test Description&quot;);
    
    auto policy = UserPolicy::Create(desc, userId, auth,
                                   USER_AllowAuditedExtraction);
    ConvertToPFileUsingPolicy(policy, inStream, fileExt, outStream);
    

## WorkerThread: een ondersteunende methode


De *WorkerThread()*-methode wordt aangeroepen in twee van de vorige voorbeeldscenario’s: **Een beveiligde bestandsstroom maken** en **Een bestand beschermen met beleid**. Dat gebeurt op de volgende manier:

**C++**:

    threadPool.push_back(thread(WorkerThread,
                                  static_pointer_cast&lt;iostream&gt;(outStream), pfs,
                                  false));


**Ondersteunende methode, WorkerThread()**

**C++**:

    static mutex   threadLocker;
    static int64_t totalSize     = 0;
    static int64_t readPosition  = 0;
    static int64_t writePosition = 0;
    static vector&lt;thread&gt; threadPool;
    
    static void WorkerThread(shared_ptr&lt;iostream&gt;           stdStream,
                         shared_ptr&lt;ProtectedFileStream&gt;pStream,
                         bool                           modeWrite) {
    vector&lt;uint8_t&gt; buffer(4096);
    int64_t bufferSize = static_cast&lt;int64_t&gt;(buffer.size());
    
    while (totalSize - readPosition &gt; 0) {
    // lock
    threadLocker.lock();
    
    // check remain
    if (totalSize - readPosition &lt;= 0) {
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
    
        stdStream-&gt;seekg(offsetRead);
        stdStream-&gt;read(reinterpret_cast&lt;char *&gt;(&amp;buffer[0]), toProcess);
        threadLocker.unlock();
        auto written =
          pStream-&gt;WriteAsync(
            buffer.data(), toProcess, offsetWrite, std::launch::deferred).get();
    
        if (written != toProcess) {
          throw rmscore::exceptions::RMSStreamException(&quot;Error while writing data&quot;);
        }
      }
      catch (exception&amp; e) {
        qDebug() &lt;&lt; &quot;Exception: &quot; &lt;&lt; e.what();
      }
    } else {
      auto read =
        pStream-&gt;ReadAsync(&amp;buffer[0],
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
        stdStream-&gt;seekp(offsetWrite);
        stdStream-&gt;write(reinterpret_cast&lt;const char *&gt;(buffer.data()), read);
        threadLocker.unlock();
      }
      catch (exception&amp; e) {
        qDebug() &lt;&lt; &quot;Exception: &quot; &lt;&lt; e.what();
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

    auto FileCachePtr = std::make_shared&lt; rmsauth::FileCache&gt;();


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


**Stap 4**: toegangstoken ophalen uit resultaat Beschrijving: methode **result-&gt; accessToken()** aanroepen

**Opmerking:** met alle verificatiemethoden voor de bibliotheek kan **rmsauth::Exception** worden gegenereerd

 
**oAuth2-verificatietoken ophalen zonder UI**
**Bron**: [rmsauth\_sample/mainwindow.cpp](https://github.com/AzureAD/rms-sdk-for-cpp/tree/master/samples/rmsauth_sample)

**Stap 1**: een gedeeld punt maken van het **rmsauth::FileCache**-object Beschrijving: u kunt het cachepad instellen of de standaardwaarde gebruiken

**C++**:

    auto FileCachePtr = std::make_shared&lt; rmsauth::FileCache&gt;();


**Stap 2**: **UserCredential**-object maken Beschrijving: *gebruikersaanmelding* en *wachtwoord* opgeven

**C++**:

    auto userCred = std::make_shared&lt;UserCredential&gt;(&quot;john.smith@msopentechtest01.onmicrosoft.com&quot;,
                                                 &quot;SomePass&quot;);


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


**Stap 5**: toegangstoken ophalen uit resultaat Beschrijving: methode **result-&gt; accessToken()** aanroepen

**Opmerking:** met alle verificatiemethoden voor de bibliotheek kan **rmsauth::Exception** worden gegenereerd




<!--HONumber=Jun16_HO4-->


