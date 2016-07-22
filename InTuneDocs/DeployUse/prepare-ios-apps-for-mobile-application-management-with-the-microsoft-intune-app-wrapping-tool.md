---
# required metadata

title: iOS-apps voorbereiden voor beheer met de App Wrapping Tool | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 99ab0369-5115-4dc8-83ea-db7239b0de97

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# iOS-apps voorbereiden voor Mobile Application Management met de Intune App Wrapping Tool
Wijzig met de **Microsoft Intune App Wrapping Tool voor iOS** de werking van interne iOS-apps, door functies van de app te beperken zonder dat u de code van de app zelf wijzigt.

Het hulpprogramma is een Mac OS-opdrachtregeltoepassing waarmee een 'wrapper' rond een app wordt gemaakt. Wanneer een app is verwerkt, kunt u de app-functionaliteit wijzigen met [Mobile Application Management-beleid](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) dat u configureert.

Zie [Microsoft Intune App Wrapping Tool voor iOS](http://www.microsoft.com/en-us/download/details.aspx?id=45218) als u het hulpprogramma wilt downloaden.

## Stap 1: voldoe aan de vereisten voor het gebruik van de App Wrapping Tool

|Vereiste|Meer informatie|
|---------------|--------------------------------|
|Ondersteunde hulpmiddelenset en besturingssysteem|U moet de App Wrapping Tool uitvoeren op een Mac met OS X 10.8.5 of hoger, waarop XCode toolset versie 5 of hoger is geïnstalleerd.|
|Handtekeningcertificaat en inrichtingsprofiel|U moet over een Apple-handtekeningcertificaat en -inrichtingsprofiel beschikken. Zie de [Apple-documentatie voor ontwikkelaars](https://developer.apple.com/) voor meer informatie.|
|Een app verwerken met de App Wrapping Tool|Apps moeten zijn ontwikkeld en ondertekend door uw bedrijf of een onafhankelijke softwareleverancier (ISV). U kunt dit hulpprogramma niet gebruiken om apps uit de Apple Store te verwerken. Apps moeten zijn geschreven voor iOS 7.0 of hoger. Apps moeten ook de Position Independent Executable-indeling (PIE) hebben. Zie de Apple-documentatie voor ontwikkelaars voor meer informatie over de PIE-indeling. Tot slot moet de app de extensie **.app** of **.ipa** hebben.|
|Apps die de Wrapping Tool niet kan verwerken|Versleutelde apps, niet-ondertekende apps en apps met uitgebreide bestandskenmerken.|
|Apps die gebruikmaken van Azure Active Directory Library (ADAL)|Als uw app gebruikmaakt van ADAL, moet deze gebruikmaken van ADAL versie 1.0.2 of hoger en moet de ontwikkelaar de app toegang bieden tot de Intune Mobile Application Management-resource.<br /><br />Zie [Informatie voor apps die gebruikmaken van de Azure Active Directory Library](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md#information-for-apps-that-use-the-azure-active-directory-library) in dit artikel voor meer informatie over het gebruik van ADAL.|
|Rechten instellen voor uw app|Voordat u de app verpakt, moet u rechten instellen zodat de app naast de standaardmachtigingen en -mogelijkheden ook over andere machtigingen en -mogelijkheden beschikt. Zie [App-rechten instellen](#setting-app-entitlements) voor instructies.|

## Stap 2: installeer de App Wrapping Tool

1.  Ga naar de pagina **Microsoft Intune App Wrapping Tool voor iOS** in het [Microsoft Downloadcentrum](https://www.microsoft.com/download/details.aspx?id=45218)en download het installatiebestand voor het hulpprogramma naar een Mac-computer.

2.  Dubbelklik op de Mac-computer op het installatiebestand **Microsoft Intune App Wrapping Tool for iOS.dmg**.

3.  Klik op **Akkoord** om de gebruiksrechtovereenkomst (EULA) te accepteren. Het installatieprogramma wordt gekoppeld en weergegeven op de Mac-computer.

4.  Open het installatieprogramma en kopieer de weergegeven bestanden naar een nieuwe map op de Mac-computer. U kunt nu het gekoppelde installatiestation loskoppelen.

    U bent gereed om de App Wrapping Tool uit te voeren.

## Stap 3: voer de App Wrapping Tool uit

1.  Open op de Mac-computer een Terminal-venster en navigeer naar de map waarin u de bestanden hebt opgeslagen. Omdat het uitvoerbare bestand zich in het pakket bevindt, moet u de opdracht als volgt uitvoeren:
```
    ./IntuneMAMPackager.app/Contents/MacOS/IntuneMAMPackager –i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> –p /<path to provisioning profile> –c <SHA1 hash of the certificate> -a <client ID of input app> -r <reply URI of input app> -v true
```
    > [!NOTE]
    > Some parameters are optional as shown in the table below.

    **Example:** The following example command runs the app wrapping tool on an app named **MyApp.ipa**. A provisioning profile and SHA-1 hash are specified. The processed app is created and stored in the **/users/myadmin/Documents** on the Mac computer.

    ```
    /users/myadmin/Downloads/IntuneMAMPackager.app/Contents/MacOS/IntuneMAMPackager -i /users/myadmin/Downloads/MyApp.ipa -o /users/myadmin/Documents/MyApp_Wrapped.ipa -p /users/myadmin/Downloads/My_Provisioning_Profile_.mobileprovision -c 12A3BC45D67EF8901A2B3CDEF4ABC5D6E7890FAB –a 20e1cd0d-268e-4308-9583-02ae97dd353e –r https://contoso/ -v true
    ```
    You can use the following command line properties with the app wrapping tool:

|Eigenschap|Meer informatie|
  |------------|--------------------|
  |**-h**|De beschikbare opdrachtregeleigenschappen voor de App Wrapping Tool weergeven.|
  |**-i**|Het pad en de bestandsnaam van de invoerapp opgeven.|
  |**-o**|Het pad opgeven waarin de verwerkte app wordt opgeslagen.|
  |**-p**|Het pad naar uw inrichtingsprofiel voor iOS-apps opgeven.|
  |**-c**|De SHA1-hash van het ondertekeningscertificaat opgeven.|
  |**-a**|De client-id van de invoerapp (in GUID-indeling) als de app gebruikmaakt van Azure Active Directory Libraries (optioneel).|
  |**-r**|Omleidings-URI van de invoerapp als de app gebruikmaakt van Azure Active Directory Libraries (optioneel).|
  |**-v**|Uitgebreide berichten uitvoeren naar de console (optioneel).|

2. Nadat de verwerking is voltooid, wordt het bericht **The application was successfully wrapped** weergegeven.

    Zie [Foutberichten](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md#error-messages) voor hulp als er een fout optreedt.

3.  De ingepakte app wordt opgeslagen in de uitvoermap die u eerder hebt opgegeven. U kunt de app nu uploaden naar [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] en deze koppelen aan een beheerbeleid voor mobiele apps.

    > [!IMPORTANT]
    > U moet de app uploaden als een nieuwe app. U kunt een oudere, niet-ingepakte versie van de app niet bijwerken.

    U kunt de app nu voor de [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-groepen implementeren en de app wordt op het apparaat uitgevoerd met de app-beperkingen die u opgeeft.

## Foutberichten en logboekbestanden
Gebruik de volgende informatie voor het oplossen van problemen die zich voordoen met de App Wrapping Tool.

### Foutberichten
Als de App Wrapping Tool niet kan worden voltooid, wordt mogelijk een van de volgende foutberichten weergegeven:

|Foutbericht|Meer informatie|
|-----------------|--------------------|
|U moet een geldig iOS-inrichtingsprofiel opgeven.|Uw inrichtingsprofiel is mogelijk niet geldig. Controleer of u de juiste machtigingen hebt voor apparaten en of uw profiel correct is gemaakt voor ontwikkeling of distributie. Uw inrichtingsprofiel kan ook zijn verlopen.|
|Geef een geldige naam op voor een invoerapp.|Zorg dat u de juiste naam opgeeft voor de invoerapp.|
|Geef een geldig pad naar de uitvoerapp op.|Zorg dat het pad naar de uitvoerapp dat u hebt opgegeven bestaat en correct is.|
|Geef een geldig inrichtingsprofiel voor invoer op.|Zorg dat u een geldige naam en extensie voor het inrichtingsprofiel hebt opgegeven. Er ontbreken mogelijk rechten in uw inrichtingsprofiel of mogelijk hebt u de opdrachtregeloptie **–p** niet toegevoegd.|
|De invoerapp die u hebt opgegeven, is niet gevonden. Geef een geldige naam en een geldig pad op voor de invoerapp.|Zorg dat het pad naar uw invoerapp geldig is en bestaat. Zorg dat de invoerapp op die locatie bestaat.|
|Het inrichtingsprofielbestand voor invoer dat u hebt opgegeven, is niet gevonden. Geef een geldige inrichtingsprofielbestand voor invoer op.|Zorg dat het pad naar het inrichtingsbestand voor invoer geldig is en dat het opgegeven bestand bestaat.|
|De appmap voor uitvoer die u hebt opgegeven, is niet gevonden. Geef een geldig pad naar de uitvoerapp op.|Zorg dat het opgegeven uitvoerpad geldig is en bestaat.|
|App voor uitvoer heeft geen IPA-extensie.|Alleen apps met de extensies **.app** en **.ipa** worden geaccepteerd door de App Wrapping Tool. Zorg dat uw bestand voor uitvoer een geldige extensie heeft.|
|Er is een ongeldig handtekeningcertificaat opgegeven. Geef een geldig handtekeningcertificaat van Apple op.|Zorg dat u het juiste handtekeningcertificaat hebt gedownload vanuit de Apple-portal voor ontwikkelaars. Het certificaat kan ook zijn verlopen. Als uw Apple-certificaat en inrichtingsprofiel kunnen worden gebruikt om een app correct te ondertekenen in Xcode, zijn deze ook geldig voor de App Wrapping Tool.|
|De opgegeven app voor invoer is ongeldig. Geef een geldige app op.|Zorg dat u een geldige iOS-app hebt die is gecompileerd als APP of IPA-bestand.|
|De opgegeven app voor invoer is versleuteld. Geef een geldige niet-versleutelde app op.|De App Wrapping Tool ondersteunt geen versleutelde apps. Geef een niet-versleutelde app op.|
|De opgegeven app voor invoer die u hebt opgegeven, heeft geen Position Independent Executable-indeling (PIE). Geef een geldige app in de PIE-indeling op.|Position Independent Executable-apps (PIE) kunnen worden geladen op een willekeurig geheugenadres wanneer ze worden uitgevoerd. Dit kan beveiligingsvoordelen hebben. Zie de Apple-documentatie voor ontwikkelaars voor meer informatie.|
|De opgegeven app voor invoer is al ingepakt. Geef een geldige niet-ingepakte app op.|U kunt een app die al is verwerkt door het hulpprogramma, niet opnieuw verwerken. Als u wilt een app opnieuw wilt verwerken, moet u het hulpprogramma uitvoeren met de oorspronkelijke versie van de app.|
|De app voor invoer die u hebt opgegeven, is niet ondertekend. Geef een geldige ondertekende app op.|De App Wrapping Tool vereist dat apps zijn ondertekend. Raadpleeg de documentatie voor ontwikkelaars voor meer informatie over hoe u een ingepakte app ondertekent.|
|De app voor invoer die u hebt opgegeven, moet de indeling .ipa of .app hebben.|Alleen de extensies .app en .ipa worden geaccepteerd door de App Wrapping Tool. Zorg dat uw invoerbestand een geldige extensie heeft en is gecompileerd als bestand met de extensie .app of .ipa.|
|De app voor die u hebt opgegeven, is al ingepakt en heeft de meest recente beleidssjabloonversie.|De App Wrapping Tool pakt een bestaande ingepakte app met de meest recente beleidssjabloonversie niet opnieuw in.|
|De opgegeven Azure Active Directory-client-id is geen goed ingedeelde GUID. Geef een geldige client-id op.|Wanneer u de client-id-parameter gebruikt, controleert u of u een geldige client-id in de GUID-indeling hebt opgegeven.|
|De opgegeven antwoord-URI van de Azure Active Directory heeft geen juiste URI-notatie. Geef een geldige antwoord-URI op.|Wanneer u de opdrachtregeleigenschap antwoord-URI gebruikt, controleert u of u een geldige antwoord-URI hebt opgegeven.|
|WAARSCHUWING: u hebt geen SHA1-certificaat-hash opgegeven. Zorg dat uw verpakte app is ondertekend voordat u deze implementeert.|Zorg dat u een geldige SHA-hash opgeeft (met de opdrachtregeleigenschap **–c** ).|

### Logboekbestanden voor de App Wrapping Tool
Apps die zijn verpakt met de App Wrapping Tool genereren logboeken die worden geschreven naar de console van het iOS-clientapparaat. Deze informatie is nuttig voor situaties waarin u problemen ondervindt met de app en wilt achterhalen of het probleem is gerelateerd aan de App Wrapping Tool. Als u deze informatie wilt ophalen, gebruikt u de volgende stappen:

1.  Reproduceer het probleem door de app uit te voeren.

2.  Verzamel de uitvoer van de console door de instructies van Apple voor [foutopsporing in geïmplementeerde iOS-apps](https://developer.apple.com/library/ios/qa/qa1747/_index.html) te volgen.

3.  Filter de opgeslagen logboeken op beperkingen voor apps door het volgende script in te voeren in de console:

    ```
    grep “IntuneAppRestrictions” <text file containing console output> > <required filtered log file name>
    ```
    U kunt de gefilterde logboeken naar Microsoft verzenden.

    > [!NOTE]
    > In het logboekbestand komt het item 'build version' overeen met de buildversie van Xcode.

    Ingepakte apps bieden gebruikers ook de optie om logboeken rechtstreeks vanaf het apparaat te verzenden nadat de app is vastgelopen. Gebruikers kunnen het logboek naar u verzenden zodat u het kunt onderzoeken en zo nodig kunt doorsturen naar Microsoft.

## Informatie voor apps die gebruikmaken van de Azure Active Directory Library
De informatie in deze sectie geldt alleen voor apps die gebruikmaken van de Azure Active Directory Library (ADAL). Als u niet zeker weet of uw app gebruikmaakt van deze bibliotheek, neemt u contact op met de ontwikkelaar van de app.

In de app moet ADAL-versie 1.0.2 of hoger zijn opgenomen.

Voor apps die gebruikmaken van de ADAL, moet het volgende waar zijn:

-   De app moet gebruikmaken van ADAL versie 1.0.2 of hoger.

-   Ontwikkelaars moeten de app toegang verlenen tot de Intune Mobile Application Management-resource, zoals is beschreven in [De stappen die u moet volgen voor apps die gebruikmaken van ADAL](#steps-to-follow-for-apps-that-use-adal).

### Overzicht van id's die u moet ophalen
Apps die gebruikmaken van de ADAL moeten worden geregistreerd via de Azure-beheerportal om twee unieke id's voor de app op te vragen:

|Id|Meer informatie|Standaardwaarde|
|--------------|--------------------|-----------------|
|**Client-id**|Een unieke id van de GUID wordt voor elke app gegenereerd nadat deze is geregistreerd in de Azure Active Directory.<br /><br />Als u de specifieke client-id van de app hebt, kunt u deze waarde opgeven. Anders moet de standaardwaarde worden gebruikt.|6c7e8096-f593-4d72-807f-a5f86dcc9c77|
|**Omleidings-URI**|Een URI-waarde die ontwikkelaars kunnen opgeven wanneer zij de app registreren in de Azure Active Directory om te zorgen dat de verificatietokens worden geretourneerd naar dat eindpunt.<br /><br />De omleidings-URI is een optionele parameter voor de App Wrapping Tool. Als deze niet is opgegeven, wordt een standaard-URI gebruikt.|urn:ietf:wg:oauth:2.0:oob|


### De stappen die u moet volgen voor apps die gebruikmaken van ADAL

1.  Controleer [Overzicht van id's die u moet ophalen](#overview-of-identifiers-you-need-to-get) voor meer informatie over de waarden die u moet ophalen.

2.  Configureer de toegang tot Mobile Application Management in Azure Active Directory door de volgende handelingen uit te voeren:

    1. Meld u aan bij een bestaand Azure Active Directory-account op de Azure-beheerportal.

    2.  Klik op **existing LOB application registration** in de Azure Active Directory.

    3.  Kies in het gedeelte Configureren de optie **Toegang tot web-API's in andere toepassingen configureren**.

    4.  Kies in het gedeelte **Machtiging voor andere toepassingen** de optie **Intune Mobile Application Management** in de vervolgkeuzelijst.

        U kunt nu de client-id van de app gebruiken in de App Wrapping Tool. U vindt de client-id van de app in de Azure Active Directory-beheerportal, zoals is beschreven in het gedeelte [Overzicht van id’s die u moet ophalen](#overview-of-identifiers-you-need-to-get).

3.  Gebruik de waarden voor **Client-id** (met de eigenschap **–a**) en **Omleidings-URI** als opdrachtregeleigenschappen in de App Wrapping Tool. Als u niet over deze waarden beschikt, worden de standaardwaarden gebruikt. U moet beide waarden opgeven, anders kan de eindgebruiker de verwerkte app niet verifiëren.

### Certificaat-, inrichtingsprofiel- en verificatievereisten

|Vereiste|Details|
|---------------|-----------|
|Inrichtingsprofiel|**Controleer of het inrichtingsprofiel geldig is voordat u het toevoegt**: de App Wrapping Tool controleert niet of het inrichtingsprofiel is verlopen wanneer een iOS-app wordt verwerkt. Als een verlopen inrichtingsprofiel is opgegeven, voegt de App Wrapping Tool het verlopen inrichtingsprofiel toe en weet u niet dat er een probleem is tot de installatie van de app op een iOS-apparaat mislukt.|
|Certificaat|**Controleer of het certificaat geldig is voordat u het opgeeft**: de App Wrapping Tool controleert niet of een certificaat is verlopen wanneer iOS-apps worden verwerkt. Als de hash voor een verlopen certificaat is opgegeven, verwerkt en ondertekent het hulpprogramma de app, maar kan de app niet worden geïnstalleerd op apparaten.<br /><br />**Zorg dat het certificaat dat is opgegeven voor het ondertekenen van de ingepakte app ook voorkomt in het inrichtingsprofiel**: het hulpprogramma controleert niet of het certificaat dat is opgegeven voor het ondertekenen van de ingepakte app voorkomt in het inrichtingsprofiel.|
|Verificatie|Op het apparaat moet een pincode zijn ingesteld voor een goede werking van versleuteling. Op apparaten waarop u een ingepakte app hebt geïmplementeerd, wordt de gebruiker gevraagd om zich opnieuw te verifiëren bij [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] wanneer hij de statusbalk aanraakt. Het standaardbeleid in een verpakte toepassing is *verificatie bij opnieuw opstarten*. iOS verwerkt alle externe meldingen (bijvoorbeeld een telefoongesprek) als het afsluiten van de app en het vervolgens opnieuw starten van de app.<br /><br />Voor ingepakte apps wordt de eerste gebruiker die zich aanmeldt bij een ingepakte app van dezelfde uitgever, opgeslagen in de cache. Daarna krijgt alleen die gebruiker toegang tot de app. De gebruiker kan alleen opnieuw worden ingesteld door het apparaat uit te schrijven en vervolgens weer in te schrijven.|

### Probleemoplossing voor en technische opmerkingen over ADAP

-   Als er geen ADAL-bronnen zijn gevonden, voegt het hulpprogramma de dynamische ADAL-bibliotheek toe. Het hulpprogramma zoekt naar de ADAL-bibliotheek met de naam **ADALiOS.bundle** in de hoofdmap.

-   Het hulpprogramma zoekt niet naar binaire ADAL-bestanden (indien aanwezig) in de app. Als de app is gekoppeld aan een verouderde versie, kunnen er runtimefouten tijdens de aanmelding optreden als verificatiebeleid is ingeschakeld.

-   [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] haalt de AAD-token voor de [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] MAM-bron-id op voor verificatie. Dit wordt echter niet gebruikt in aanroepen die op hun beurt de geldigheid van het token verifiëren. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] leest alleen de UPN van de aangemelde gebruiker om app-toegang te bepalen. De AAD-token wordt niet gebruikt voor verdere serviceaanroepen.

-   Verificatietokens worden gedeeld tussen apps van dezelfde uitgever omdat ze worden opgeslagen in een gedeelde sleutelketen. Als u een specifieke app wilt isoleren, moet u een ander handtekeningcertificaat en inrichtingsprofiel voor die app gebruiken.

-   Als u de client-id en omleidings-URI van de clientapp opgeeft, worden dubbele aanmeldprompts voorkomen. Deze client-id moet worden geregistreerd voor toegang tot de gepubliceerde [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] MAM-bron-id in het AAD-dashboard. Als u dit niet doet, treedt er een aanmeldfout op wanneer de app wordt uitgevoerd.

## App-rechten instellen
Voordat u de app verpakt, kunt u **rechten** verlenen zodat de app over meer machtigingen en mogelijkheden beschikt dan standaard het geval is.  Voor de ondertekening van de programmacode wordt gebruikgemaakt van een **rechtenbestand** om speciale machtigingen in uw app (bijvoorbeeld de toegang tot een gedeelde sleutelketen) op te geven. Specifieke app-services, ook wel **mogelijkheden** genoemd, worden in Xcode ingeschakeld tijdens het ontwikkelen van de app. Wanneer de mogelijkheden eenmaal zijn ingeschakeld, worden deze weergegeven in uw rechtenbestand. Zie [Mogelijkheden toevoegen](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) in de bibliotheek voor iOS-ontwikkelaars voor meer informatie over rechten en mogelijkheden. Zie [Ondersteunde mogelijkheden](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/SupportedCapabilities/SupportedCapabilities.html) voor een volledige lijst met ondersteunde mogelijkheden.

### Ondersteunde mogelijkheden voor de App Wrapping Tool voor iOS

|Mogelijkheid|Beschrijving|Aanbevolen richtlijnen|
|--------------|---------------|------------------------|
|App-groepen|Gebruik app-groepen zodat meerdere apps toegang kunnen krijgen tot gedeelde containers en sta aanvullende communicatie tussen processen van de verschillende apps toe.<br /><br />Als u app-groepen wilt inschakelen, opent u het deelvenster **Mogelijkheden** en klikt u op de schakelaar **AAN** in het gedeelte **App-groepen **. U kunt app-groepen toevoegen of bestaande app-groepen selecteren.|Pas omgekeerde DNS-notatie toe wanneer u app-groepen gebruikt:<br /><br />*group.com.companyName.AppGroup*|
|Achtergrondmodi|Wanneer u achtergrondmodi inschakelt, kan uw iOS-app op de achtergrond actief blijven.||
|Gegevensbescherming|Met de gegevensbescherming voegt u een beveiligingsniveau toe aan bestanden die op schijf zijn opgeslagen door de iOS-app. De gegevensbescherming maakt gebruik van de ingebouwde versleutelingshardware die aanwezig is op de specifieke apparaten en waarmee bestanden in een versleutelde indeling op de schijf worden opgeslagen. Uw app moet worden ingericht voor het gebruik van de gegevensbescherming.||
|Aankopen binnen apps|Bij aankopen binnen apps wordt een winkel rechtstreeks in uw app opgenomen en kunt u verbinding maken met de winkel en veilig betalingen van de gebruiker verwerken. U kunt aankopen binnen apps gebruiken voor het ontvangen van betalingen voor uitgebreide functionaliteit of voor aanvullende inhoud die kan worden gebruikt met uw app.||
|Het delen van sleutelketens|Wanneer u het delen van sleutelketens inschakelt, kan uw app wachtwoorden in de sleutelketen delen met andere apps die door uw team zijn ontwikkeld.|Pas omgekeerde DNS-notatie toe wanneer u gebruikmaakt van het delen van sleutelketens:<br /><br />*com.companyName.KeychainGroup*|
|Persoonlijke VPN|Sta een persoonlijk VPN toe zodat uw app een aangepaste systeemconfiguratie voor VPN kan maken en beheren met Network Extension Framework.||
|Pushmeldingen|Met de Apple Push Notification-service (APNs) kan de gebruiker via een app die actief is op de achtergrond worden geïnformeerd dat er een bericht is voor de gebruiker.|Voor pushmeldingen hebt u een app-specifiek inrichtingsprofiel nodig.<br /><br />Volg de stappen in de [Apple-documentatie voor ontwikkelaars](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html).|
|Configuratie van draadloze accessoires|Wanneer u de configuratie van draadloze accessoires inschakelt, wordt External Accessory Framework aan uw project toegevoegd en kunt u met uw app MFi Wi-Fi-accessoires configureren.||

### De stappen voor het inschakelen van rechten

1.  U schakelt als volgt mogelijkheden in uw app in:

    1.  Navigeer in Xcode naar het doel van uw app en klik op het deelvenster **Mogelijkheden**

    2.  Schakel de gewenste mogelijkheden in. Zie [Mogelijkheden toevoegen](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) in de bibliotheek voor iOS-ontwikkelaars voor gedetailleerde informatie over elke mogelijkheid en het bepalen van de juiste waarden.

    3.  Noteer de id's die u tijdens de procedure hebt gemaakt.

    4.  Bouw en onderteken uw app zodat deze kan worden verpakt.

2.  U schakelt als volgt rechten in uw inrichtingsprofiel in:

    1.  Meld u aan bij het Apple Developer Member Center.

    2.  Maak een inrichtingsprofiel voor uw app. Zie [De vereisten voor de Intune App Wrapping Tool voor iOS ophalen](http://blogs.technet.com/b/microsoftintune/archive/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios.aspx) voor instructies.

    3.  Schakel in het inrichtingsprofiel dezelfde rechten in als in uw app. U moet dezelfde id's gebruiken die u bij het ontwikkelen van de app hebt opgegeven.

    4.  Voer de wizard voor inrichtingsprofielen uit en download het bestand.

3.  Zorg ervoor dat u aan alle vereisten hebt voldaan en verpak de app.

### Het oplossen van veelvoorkomende problemen met rechten
Als door de App Wrapping Tool voor iOS een fout met de rechten wordt weergegeven, voert u de volgende probleemoplossingsstappen uit.

|Probleem|Oorzaak|Oplossing|
|---------|---------|--------------|
|Het parseren van rechten die zijn gegenereerd uit de invoertoepassing is mislukt.|Het rechtenbestand dat is opgehaald uit de app kan niet door de App Wrapping Tool worden gelezen. Het rechtenbestand is mogelijk ongeldig.|Controleer het rechtenbestand voor uw app. Volg hiervoor de instructies die hieronder staan beschreven. Controleer bij de inspectie van het rechtenbestand op ongeldige syntaxis. Het bestand moet de XML-indeling hebben.|
|Er ontbreken rechten in het inrichtingsprofiel (de ontbrekende rechten worden weergegeven). Verpak de app opnieuw met een inrichtingsprofiel dat deze rechten bevat.|De rechten die zijn ingeschakeld in het inrichtingsprofiel en de mogelijkheden die zijn ingeschakeld in de app komen niet overeen. Dit verschil geldt ook voor de id's die zijn gekoppeld aan de specifieke mogelijkheden (app-groepen, toegang tot de sleutelketen, enzovoort).|Over het algemeen is het mogelijk om een nieuw inrichtingsprofiel te maken waarmee dezelfde mogelijkheden kunnen worden ingeschakeld als voor de app. Wanneer de id’s van het profiel en de app niet overeenkomen, worden deze, indien mogelijk, door de App Wrapping Tool vervangen. Als u nog steeds deze foutmelding krijgt nadat u een nieuw inrichtingsprofiel hebt gemaakt, kunt u de rechten van de app verwijderen met de parameter **–e** (zie het gedeelte De parameter–e gebruiken om rechten te verwijderen uit een app, hieronder).|

### De bestaande rechten van een ondertekende app zoeken
U kunt als volgt de bestaande rechten van een ondertekende app en inrichtingsprofiel bekijken:

1.  Ga naar het IPA-bestand en wijzig de extensie in .zip.

2.  Pak het ZIP-bestand uit. De map Payload met daarin uw app-bundel wordt weergegeven.

3.  Controleer als volgt de rechten voor de app-bundel met het hulpprogramma voor het ondertekenen van de programmacode:

    ```
    $ codesign -d --entitlements :- "Payload/YourApp.app"
    ```
    hierbij staat `YourApp.app` voor de werkelijke naam van uw .app-bundel.

4.  Controleer met het beveiligingsprogramma de rechten van het inrichtingsprofiel dat in de app is opgenomen:

    ```
    $ security -D -i "Payload/YourApp.app/embedded.mobileprovision"
    ```
    hierbij staat `YourApp.app` voor de werkelijke naam van uw .app-bundel.

### De parameter –e gebruiken om rechten te verwijderen uit een app
Met deze opdracht worden ingeschakelde mogelijkheden in de app verwijderd die niet worden vermeld in het rechtenbestand. Als u mogelijkheden verwijdert die worden gebruikt door de app, kan dit de app beschadigen. Een voorbeeld van waar u mogelijkheden met ontbrekende rechten kunt verwijderen, is als u een app van een leverancier hebt die standaard beschikt over alle mogelijkheden.

```
./IntuneMAMPackager.app/Contents/MacOS/IntuneMAMPackager –i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> –p /<path to provisioning profile> –c <SHA1 hash of the certificate> -e
```

## Beveiliging en privacy voor de App Wrapping Tool
Gebruik de volgende best practices voor beveiliging en privacy wanneer u de App Wrapping Tool gebruikt.

-   Het handtekeningcertificaat, het inrichtingsprofiel en de Line-of Business-app die u opgeeft, moeten zich op de Mac-computer bevinden waarop u de App Wrapping Tool uitvoert. Als de bestanden zich op een UNC-pad bevinden, moet u zorgen dat ze toegankelijk zijn vanaf de Mac-computer. Het pad moet worden beveiligd via IPSec- of SMB-ondertekening.

    De verpakte toepassing die in de [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-console is geïmporteerd, moet zich op dezelfde computer bevinden als waarop u het hulpprogramma uitvoert. Als het bestand zich op een UNC-pad bevindt, moet u zorgen dat het toegankelijk is op de computer waarop de [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-console wordt uitgevoerd. Het pad moet worden beveiligd via IPSec- of SMB-ondertekening.

-   De omgeving waarnaar de App Wrapping Tool wordt gedownload van het Microsoft Download Center, moet zijn beveiligd via IPSec- of SMB-ondertekening.

-   De app die u verwerkt, moet afkomstig zijn van een betrouwbare bron voor een goede bescherming tegen aanvallen.

-   Zorg dat de map voor uitvoer die u in de App Wrapping Tool hebt opgegeven is beveiligd, in het bijzonder als het een externe map is.

-   iOS-apps, die een dialoogvenster voor het uploaden van bestanden hebben, kunnen gebruikers toestaan om beperkingen voor knippen, kopiëren en plakken die zijn toegepast op de app te omzeilen. Zo kan een gebruiker het dialoogvenster voor het uploaden van bestanden bijvoorbeeld gebruiken om een schermopname van de app-gegevens te uploaden.

-   Wanneer gebruikers de documentenmap op hun apparaat bewaken vanuit een verpakte app, zien ze mogelijk een map met de naam **.msftintuneapplauncher**. Als deze map wordt gewijzigd of verwijderd, kan dit van invloed zijn op de goede werking van beperkte apps.

### Zie tevens
- [Bepalen hoe u apps met Microsoft Intune voorbereidt op Mobile Application Management](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)</br>
- [Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)</br>
- [De SDK gebruiken om apps geschikt te maken voor Mobile Application Management](use-the-sdk-to-enable-apps-for-mobile-application-management.md)


<!--HONumber=May16_HO1-->


