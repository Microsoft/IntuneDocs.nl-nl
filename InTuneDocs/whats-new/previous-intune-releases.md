---
title: Vorige versies | Microsoft Docs
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6bc3afe58d5e0f1f12c8b6c6fc62e37d01cd5132
ms.openlocfilehash: cab9833a1e1b92c156a2eb77411436289c70ad71


---

# <a name="previous-intune-releases"></a>Vorige versies van Intune

Deze pagina bevat een overzicht van de aankondigingen in [Wat is er nieuw in Microsoft Intune](whats-new-in-microsoft-intune.md).

[!INCLUDE[wit_nextref](../includes/whats-new-last-six-months.md)]

## <a name="july-2016"></a>Juli 2016

### <a name="app-management"></a>Appbeheer

__De update-ervaring van het inrichtingsprofiel van de app verbeteren__ Apple iOS mobiele Line-Of-Business-apps zijn gebouwd met een inrichtingsprofiel en code die is ondertekend met een certificaat. Wanneer de app wordt uitgevoerd op een iOS-apparaat, bevestigt iOS de integriteit van de iOS-app en worden beleidsregels afgedwongen die zijn gedefinieerd door het inrichtingsprofiel.

Het handtekeningcertificaat voor ondernemingen dat u gebruikt om apps te ondertekenen is doorgaans 3 jaar geldig. Het inrichtingsprofiel verloopt echter na één jaar. Met deze update biedt Intune u de hulpmiddelen om proactief een nieuw beleid voor inrichtingsprofielen te implementeren op apparaten met apps die bijna zijn verlopen terwijl het certificaat nog geldig is. Zie voor meer informatie [iOS-beleid voor mobiele inrichtingsprofielen gebruiken om uw Line-Of-Business-apps up-to-date te houden](/intune/deploy-use/ios-mobile-app-provisioning-profiles).
<!--- TFS 1280247--->

__Xamarin SDK voor Intune-apps is beschikbaar__ Met het onderdeel Intune App SDK Xamarin kunt u de beheerfuncties voor Intune Mobile App inschakelen in mobiele iOS- en Android-apps die zijn gebouwd met Xamarin. U vindt het onderdeel in de [Xamarin Store](https://components.xamarin.com/view/Microsoft.Intune.MAM) of op de [Microsoft Intune Github-pagina](https://github.com/msintuneappsdk).
<!--- TFS 1061478 --->

### <a name="device-management"></a>Apparaatbeheer
__Verbeterde limieten voor apparaatinschrijvingen__ Intune heeft de maximaal configureerbare limiet voor apparaatinschrijvingen verhoogd van 5 naar 15 apparaten per gebruiker.
<!---TFS 1289896 --->

__TeamViewer-integratie voor Windows-pc's met de Intune-clientsoftware__
[TeamViewer](https://www.teamviewer.com) voor Windows-pc's die worden beheerd met de Intune-client kunt u, ter ondersteuning van uw helpdeskafdeling, sessies voor hulp op afstand met Windows-pc's uitvoeren. Dit is van toepassing op Windows 7, 8, 8.1 en 10. Zie [Algemene beheertaken voor Windows-pc’s met de Microsoft Intune-computerclient voor meer informatie](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client).
<!---TFS 1284856--->

### <a name="company-portal-updates"></a>Updates voor de bedrijfsportal

__Bedrijfsportalwebsite__
- **Verbeterde ervaring voor de eindgebruiker bij het inschrijven van Windows-apparaten**<br/>
Wanneer u voorwaardelijke toegang gebruikt, zijn de stappen voor inschrijving voor Windows 8.1, Windows 10 Desktop en Windows 10 Mobile verbeterd op de bedrijfsportalwebsite. Gebruikers zien nu de afzonderlijke stappen 'Apparaatinschrijving' en 'Workplace Join', waardoor de status van hun apparaat beter zichtbaar is en het proces eenvoudiger kan worden voltooid wanneer er een fout optreedt met Workplace Join (WPJ). De afzonderlijke stappen vereenvoudigen tevens de probleemoplossing voor IT-beheerders. Wanneer eindgebruikers voorheen probeerden in te schrijven en alle inschrijvingsstappen waren geslaagd behalve WPJ, dan werd het ingeschreven apparaat niet weergegeven in de lijst met apparaten voor gebruikers, wat verwarrend was voor gebruikers.

__Android__
- **Android-bedrijfsportal-app**<br/>
Als Android-eindgebruikers een foutmelding krijgen dat er een vereist certificaat ontbreekt voor hun apparaat, dan kunnen zij op een knop 'Oplossing' tikken voor [stappen](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) om het ontbrekende certificaat te installeren. Als gebruikers de stappen voltooien, maar er nogmaals een foutmelding over een ontbrekend certificaat wordt weergegeven, dan wordt hen gevraagd contact op te nemen met de IT-beheerder en deze [koppeling](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues) door te geven die de stappen bevat waarmee IT-beheerders het certificaatprobleem kunnen oplossen.

- **Beperken van extern geladen (ofwel 'side-loaded') app-installaties op ingeschreven apparaten**<br/>
Android-apparaten kunnen geen toepassingen meer installeren via de bedrijfsportalwebsite tenzij deze apparaten zijn ingeschreven bij Intune via de Intune-bedrijfsportal-app voor Android.
<!---TFS 1299082--->

__iOS__
- **Wijzigingen in de beheeraccounts voor apparaatinschrijving in de iOS-bedrijfsportal-app**<br/>
Om de prestaties en schaalbaarheid te verbeteren, worden in het deelvenster **Mijn apparaten** van de iOS-bedrijfsportal-app niet meer alle Device Enrollment Managers (DEM)-apparaten weergegeven door Intune. Alleen het lokale apparaat waarop de app wordt uitgevoerd, wordt weergegeven en wel alleen als het apparaat is geregistreerd via de bedrijfsportal-app.

De DEM-gebruiker kan acties op het lokale apparaat uitvoeren, maar extern beheer van andere geregistreerde apparaten kan alleen worden uitgevoerd vanuit de Intune-beheerconsole. Daarnaast is het gebruik in Intune van DEM-accounts met het Apple Device Enrollment Program of het hulpprogramma Apple Configurator beëindigd. Deze twee registratiemethoden bieden al ondersteuning voor gebruikersloze registratie voor gedeelde iOS-apparaten.

Gebruik alleen DEM-accounts wanneer gebruikersloze registratie voor gedeelde apparaten niet beschikbaar is. Zie voor meer informatie [Apparaten in bedrijfseigendom inschrijven met de apparaatinschrijvingsbeheerder in Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

### <a name="change-of-names-for-windows-features"></a>Wijziging van de namen voor Windows-functies
- [Microsoft Passport for Windows](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) is nu bekend als **Windows Hello voor Bedrijven**.
- [Ondernemingsgegevensbescherming](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) is nu bekend als **Windows Information Protection**.


## <a name="june-2016"></a>Juni 2016
### <a name="intune-service-health"></a>Servicestatus van Intune
Servicestatusgegevens voor Intune is verplaatst naar een centrale locatie met andere Microsoft-services. U vindt deze informatie nu in de Office 365-beheerportal onder Servicestatus. Lees [dit blogbericht](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/) voor meer informatie.

### <a name="app-management"></a>Appbeheer
- **Verbeterde ervaring voor configuratie van Windows 10-beleid voor ondernemingsgegevens.** Er zijn verbeteringen aangebracht in de ervaring voor configuratie van het Windows 10-beleid voor ondernemingsgegevensbescherming. Deze verbeteringen hebben betrekking op het maken van app-regels, het opgeven van netwerkdefinities en op andere instellingen voor ondernemingsgegevensbescherming. Zie [Een Enterprise Data Protection-beleid (EDP) maken met Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) voor meer informatie.


### <a name="device-management"></a>Apparaatbeheer
- **Windows Defender-beleidsinstelling voor beveiliging tegen mogelijk ongewenste apps.** **Detectie van mogelijk ongewenste toepassingen** is een nieuwe Windows Defender-instelling die toegevoegd aan het algemene configuratiebeleid voor Windows 10 Desktop en Mobile. U kunt deze instelling gebruiken als u geregistreerde Windows-desktopcomputers wilt beveiligen tegen het uitvoeren van software die door Windows Defender als mogelijk ongewenst is gedefinieerd. U kunt voorkomen dat deze toepassingen worden uitgevoerd, of de controlemodus gebruiken om te rapporteren wanneer een mogelijk ongewenste toepassing wordt geïnstalleerd. Zie [Windows 10-beleidsinstellingen in Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune) voor meer informatie.
<!---TFS 1244478--->

### <a name="conditional-access"></a>Voorwaardelijke toegang
- **Cisco ISE-netwerktoegangscontrolebeleid voor Intune.**  Klanten die Cisco Identity Service Engine (ISE) 2.1 en Microsoft Intune gebruiken, kunnen een netwerktoegangsbeleid instellen in ISE.

    Met dit beleid moeten apparaten die via Wi-Fi of VPN verbinding willen maken met het netwerk, voldoen aan de volgende voorwaarden voordat ze toegang krijgen:

    * Moeten worden beheerd met Intune
    * Moeten voldoen aan geïmplementeerd Intune-nalevingsbeleid

 Eindgebruikers van niet-compatibele apparaten wordt gevraagd zich te registreren en nalevingsproblemen op te lossen om toegang te krijgen.
- **Voorwaardelijke toegang voor de browser.** U kunt een beleid voor voorwaardelijke toegang instellen voor [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) en [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune), zodat deze alleen toegankelijk zijn via ondersteunde webbrowsers op beheerde en compatibele iOS- en Android-apparaten. Eindgebruikers die proberen zich met iOS- en Android-apparaten aan te melden bij Outlook Web Access (OWA) en SharePoint-sites, wordt gevraagd hun apparaat te registreren bij Intune en eventuele problemen met de compatibiliteit op te lossen. Hierna kan de aanmelding worden voltooid.
<!---TFS 1175844--->

- **Dynamics CRM Online biedt ondersteuning voor voorwaardelijke toegang.** U kunt beleid voor voorwaardelijke toegang instellen voor [Dynamics CRM Online](/intune/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune), zodat dit alleen toegankelijk is voor beheerde en compatibele iOS- en Android-apparaten. Eindgebruikers die zich op iOS en Android willen aanmelden bij de mobiele app Dynamics CRM, moeten zich registreren bij Intune en eventuele problemen met de naleving oplossen voordat de aanmelding wordt voltooid.
<!---TFS1295358--->

### <a name="intune-company-portal-updates"></a>Updates voor de Intune-bedrijfsportal

__Android-bedrijfsportal-app__

- Wanneer IT-beheerders het nieuwe beleid Vereisen dat apparaten de installatie van apps van onbekende bronnen niet toestaan (Android 4.0+) toepassen, krijgen eindgebruikers met een apparaat met Android 4.0 of hoger het volgende bericht te zien: De installatie vanuit onbekende bronnen moet worden uitgeschakeld. Gebruikers moeten naar **Instellingen** > **Beveiliging** gaan en **Onbekende bronnen** uitschakelen. Via een koppeling in het nalevingsbericht kunnen gebruikers meer [informatie](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android) verkrijgen over het bericht en over waarom ze de instelling moeten uitschakelen.

- Wanneer IT-beheerders het nieuwe beleid Vereisen dat apparaten het scannen van apps op beveiligingsrisico's inschakelen (Android 4.0+) toepassen, krijgen eindgebruikers met een apparaat met Android 4.0 of hoger het volgende bericht te zien: Apparaat scannen op beveiligingsrisico's. Gebruikers moeten naar **Instellingen** > **Google** > **Beveiliging** gaan en **Apparaat scannen op beveiligingsrisico's** inschakelen. Via een koppeling in het nalevingsbericht kunnen gebruikers meer [informatie](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) verkrijgen over het bericht en over waarom ze de instelling moeten inschakelen.

- Wanneer IT-beheerders het nieuwe beleid Vereisen dat USB-foutopsporing wordt uitgeschakeld (Android 4.2+) toepassen, krijgen eindgebruikers met een apparaat met Android 4.2 of hoger het volgende bericht te zien: USB-foutopsporing moet worden uitgeschakeld. Gebruikers moeten naar **Instellingen** > **Opties voor ontwikkelaars** gaan en **USB-foutopsporing** uitschakelen. Via een koppeling in het nalevingsbericht kunnen gebruikers meer [informatie](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android) verkrijgen over het bericht en over waarom ze de instelling moeten uitschakelen.

- Wanneer IT-beheerders het nieuwe beleid Minimaal niveau voor de Android-beveiligingspatch (Android 6.0+) toepassen, krijgen eindgebruikers met een apparaat met Android 6.0 of hoger het volgende bericht te zien: Dit apparaat voldoet niet aan het minimale Android-beveiligingspatchniveau. Gebruikers moeten de vereiste beveiligingspatch installeren. Via een koppeling in het nalevingsbericht kunnen gebruikers meer [informatie](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) verkrijgen over hoe de vereiste beveiligingspatch moet worden geïnstalleerd en over welke beveiligingspatch momenteel is geïnstalleerd.

__iOS-bedrijfsportal-app__

- Eindgebruikers die LOB-apps installeren, hebben nu een verbeterde ervaring tijdens de installatie van deze apps. Als de app-installatie lang duurt, kunnen gebruikers hun apparaat handmatig synchroniseren om hervatting van het synchronisatieproces af te dwingen. Zie [Sync your iOS device manually](/Intune/EndUser/sync-your-device-manually-ios) (Uw iOS-apparaat handmatig synchroniseren) voor de instructies voor eindgebruikers.

- De Microsoft Intune-bedrijfsportal-app voor iOS is bijgewerkt. Nu wordt iOS-versie 8.0 en hoger ondersteund. Deze update betekent dat eindgebruikers de bedrijfsportal-app kunnen installeren en alleen nieuwe apparaten kunnen registreren bij Intune als het apparaat iOS-versie 8.0 of hoger heeft. Gebruikers die werken met eerder ingeschreven apparaten met niet-ondersteunde versie van iOS kunnen de bedrijfsportal-app die op hun apparaat is geïnstalleerd blijven gebruiken.

## <a name="may-2016"></a>Mei 2016
Al deze functies worden ook ondersteund voor hybride implementaties (Configuration Manager met Intune). Zie de pagina met [nieuwe hybridefuncties](https://technet.microsoft.com/en-us/library/mt718155.aspx) (Engelstalig) voor meer informatie over nieuwe hybridefuncties.

### <a name="documentation"></a>Documentatie
Dit is de preview-versie van [docs.microsoft.com](https://docs.microsoft.com/en-us/intune).
Dit is een volledig nieuw, modern inhoudsplatform dat is ontworpen om Intune gebruikersvriendelijker en eenvoudiger te maken.
Zie [Kennismaking met docs.microsoft.com](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/)

### <a name="intune-service-health"></a>Servicestatus van Intune
Servicestatusgegevens voor Intune is verplaatst naar een centrale locatie met andere Microsoft-services. U vindt deze informatie nu in de [Office 365-beheerportal](https://portal.office.com/Admin/Default.aspx) onder **Servicestatus**.
Lees [dit blogbericht](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/) voor meer informatie.

### <a name="app-management"></a>Appbeheer
- **MAM SDK: ondersteuning voor configuratie van de lengte van de pincode.** Net als bij pincodes voor apparaten het geval is, kunt u ook voor MAM-apps de lengte van de pincode opgeven. Hiervoor moeten eindgebruikers voldoen aan de nieuwe beperkingen die u instelt. Ze zien dan een enigszins gewijzigd pincodescherm, waarin de langere code kan worden ingevoerd. Zie [MAM-beleidsinstellingen voor Android](/intune/deploy-use/android-mam-policy-settings) en [MAM-beleidsinstellingen voor iOS](/intune/deploy-use/ios-mam-policy-settings) voor meer informatie.

- **Skype voor Bedrijven voor iOS en Android.** U kunt Skype voor Bedrijven nu gebruiken met [MAM zonder inschrijvingsbeleid](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune). Zodra gebruikers zich aanmelden, wordt het MAM-beleid toegepast.

- **Nieuwe beschikbare apps voor beheer met MAM-beleid.** De Microsoft Word-, Excel- en PowerPoint-apps voor Android kunnen nu worden gekoppeld aan MAM-beleid op apparaten die niet zijn geregistreerd bij Intune. Ga voor de volledige lijst met ondersteunde apps naar de galerie met mobiele toepassingen van Microsoft Intune op de pagina [Microsoft Intune-toepassingen van partners](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).


### <a name="company-portal-updates"></a>Updates voor de bedrijfsportal

#### <a name="android-company-portal-app"></a>Android-bedrijfsportal-app
- **Pop-upmeldingen voor eindgebruikers**: eindgebruikers krijgen nu pop-upmeldingen uit de Android-bedrijfsportal te zien wanneer ze hun apparaten registreren bij of verwijderen uit de bedrijfsportal.

- **Wijzigingen in de beheeraccounts voor apparaatinschrijving in de iOS-bedrijfsportal-app.** Ter verbetering van de prestaties en schaalbaarheid worden er in het deelvenster Mijn apparaten van de Android-bedrijfsportal-app niet meer alle DEM-apparaten (Device Enrollment Manager; apparaatregistratiebeheer) door Intune weergegeven. Alleen het lokale apparaat waarop de app wordt uitgevoerd, wordt weergegeven en wel alleen als het apparaat is geregistreerd via de bedrijfsportal-app. De DEM-gebruiker kan acties op het lokale apparaat uitvoeren, maar extern beheer van andere geregistreerde apparaten kan alleen worden uitgevoerd vanuit de Intune-beheerconsole.

#### <a name="company-portal-website"></a>Bedrijfsportalwebsite
- **Bedrijfsportalwebsite: de banner voor apparaatidentificatie biedt eindgebruikers meer informatie.** Eindgebruikers kunnen het apparaat dat ze hebben geselecteerd, nu gemakkelijker identificeren wanneer ze de website van de bedrijfsportal gebruiken. Als er een verkeerd apparaat is geselecteerd, kunnen ze het juiste apparaat selecteren door op de koppeling **Tik hier** in de banner op de startpagina te tikken.

### <a name="service-deprecation"></a>Serviceafschaffing
- **Intune-viewer-apps.** Met het uitbrengen van de nieuwe RMS-app voor delen, worden volgende Intune-viewer-apps vanaf augustus 2016 verwijderd:
    - Intune AV-viewer
    - Intune PDF-viewer
    - Intune-afbeeldingsviewer voor Android van Google Play

  In plaats van de viewer-apps van Intune kunt u beter de nieuwe Rights Management-app (RMS sharing) voor Android gebruiken, zodat u één app in plaats van drie afzonderlijke apps kunt implementeren om veilig bedrijfsbestanden op Android-apparaten te bekijken. Meer informatie over de app RMS sharing (met een koppeling naar de documentatie).

- **Meldingsregels voor aangepaste groepen wordt verwijderd.**
Met de Intune-meldingsregels wordt gedefinieerd wie een e-mailwaarschuwing ontvangt Intune. Op dit moment kunt u meldingsregels configureren om e-mails te verzenden naar alle gebruikers van apparaten in een Intune-apparaatgroep die u hebt gemaakt. Vanaf 1 juni 2016 wordt de targeting van groepen die zijn gemaakt door gebruikers, niet meer ondersteund.

    Als u nu een meldingsregel wilt targeten op een groep die u in de Microsoft Intune-beheerconsole hebt gemaakt, voert u de volgende stappen uit:

    Klik in de werkruimte **Beheerder** op **Meldingsregels** > **Nieuwe regel maken**

    In stap&2; van de wizard Meldingsregel maken selecteert u de apparaatgroepen waarop de regel betrekking heeft. De stap voor het selecteren van apparaatgroepen wordt uit de Intune-console verwijderd.

    De voorlopige tijdlijn voor deze wijziging is als volgt:
    - In juni 2016 krijgen nieuwe tenants stap 2 van de wizard Meldingsregel maken niet meer te zien. Voor de huidige tenants blijft de situatie ongewijzigd.
    - Rond augustus 2016 krijgen enkele bestaande tenants de wizardoptie voor het selecteren van apparaatgroepen niet meer te zien.
    - Naar verwachting krijgt rond oktober 2016 geen enkele bestaande tenant de wizardoptie voor het selecteren van apparaatgroepen nog te zien.


- **Wijzigingen in de ondersteuning voor de iOS-bedrijfsportal-app**. In de komende maanden zal de Microsoft Intune-bedrijfsportal-app voor iOS worden bijgewerkt en biedt deze alleen nog ondersteuning voor apparaten met iOS 8.0 of later. Gebruikers kunnen geen nieuwe apparaten met een versie lager dan iOS 8.0 registreren. Geregistreerde apparaten met een versie lager dan iOS 8.0 worden gewoon nog beheerd en kunnen, voor een beperkte periode, gebruik blijven maken van de bedrijfsportal-app. Apparaten moeten echter over iOS 8.0 of later beschikken voor toegang tot de nieuwste versie van de bedrijfsportal-app. U kunt gebruikers het beste adviseren bij te werken naar iOS 8.0 of later om optimaal gebruik te kunnen maken van de nieuwe Intune-functies.  


## <a name="april-2016"></a>April 2016
Al deze functies worden ook ondersteund voor hybride klanten (Configuration Manager geïntegreerd met Intune).

### <a name="app-management"></a>Appbeheer
- **Naleving van beleid door MAM-gebruikers.**
U kunt nu de [status](/intune/deploy-use/monitor-mobile-app-management-policies-with-Microsoft-Intune) van uw beleid voor toepassingsbeheer bekijken voor gebruikers in uw AAD-tenant (Azure Active Directory). Dit omvat:
   - Apparaten
   - Apps op het apparaat

   Statuswaarden:

   **Ingecheckt**: hiermee wordt aangegeven dat het beleid is geïmplementeerd voor de gebruiker, dat de app is gebruikt in een werkcontext en dat het beleid is ontvangen.

    **Niet ingecheckt**: hiermee wordt aangegeven dat het beleid is geïmplementeerd voor de gebruiker, maar dat de app sindsdien niet is gebruikt in een werkcontext.


- **MAM-besturingselementen om te voorkomen dat Outlook-contactpersonen worden gesynchroniseerd (Android).**
Er is een nieuwe instelling beschikbaar voor [Mobile Application Management](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) zonder apparaatregistratie. Met deze instelling kunt u voorkomen dat een toepassing contactpersonen synchroniseert met het systeemeigen adresboek op Android-apparaten. Wanneer deze instelling is ingeschakeld, kunnen doeltoepassingen niet langer contactpersonen in het systeemeigen adresboek opslaan. Wanneer deze instelling is uitgeschakeld, kunnen doeltoepassingen wel contactpersonen in het systeemeigen adresboek opslaan. Wanneer u [een apparaat of app op afstand wist](/intune/deploy-use/wipe-managed-company-app-data-with-Microsoft-Intune), worden de contactpersonen verwijderd die al in het systeemeigen adresboek zijn opgeslagen. Deze nieuwe instelling wordt in eerste instantie ondersteund door de Outlook-toepassing op Android-apparaten.

### <a name="device-management"></a>Apparaatbeheer
- **Nummerherkenning voor apparaten die bedrijfseigendom zijn.** Telefoons die zijn aangemerkt als bedrijfseigendom, worden nu aangeduid met hun volledige telefoonnummer wanneer u bijvoorbeeld een inventarisrapport voor mobiele apparaten uitvoert. Telefoonnummers voor BYOD-apparaten worden nog steeds gemaskeerd met ****, waarbij alleen de laatste 4 cijfers worden weergegeven.


### <a name="company-portal-updates"></a>Updates voor bedrijfsportal
**Android-bedrijfsportal-app** Gebruikers die hun apparaat niet bij Intune hebben ingeschreven en bij wie niet het juiste certificaat is geïnstalleerd, kunnen zich niet aanmelden bij de bedrijfsportal-app voor Android en zien het bericht 'U kunt u niet aanmelden omdat een vereist certificaat ontbreekt op het apparaat'. Het bericht bevat een koppeling Oplossing waarop gebruikers kunnen tikken om instructies te zien voor het installeren van het certificaat. Zie [Er ontbreekt een vereist certificaat voor uw apparaat](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing) om te zien welke stappen eindgebruikers moeten volgen om het probleem op te lossen.

**iOS-bedrijfsportal-app** Er is ondersteuning toegevoegd voor de actie 'veeg naar beneden om te vernieuwen' om de inhoud van het startscherm (met onder meer de lijst met apps, de lijst met apparaten en de contactgegevens van de IT-afdeling) te vernieuwen. De actie 'veeg naar beneden om te vernieuwen' controleert niet op naleving van beleid of beleidsgegevens. Dat kunt u doen door de tegel voor uw huidige apparaat te selecteren en op de knop **Synchroniseren** te tikken.

**Windows 10 Mobile- en Windows Phone 8.1-bedrijfsportal-app** Eindgebruikers die LOB-apps installeren, hebben nu een verbeterde ervaring tijdens de installatie van deze apps. Als de app-installatie lang duurt, kunnen gebruikers hun apparaat handmatig synchroniseren om hervatting van het synchronisatieproces af te dwingen. Zie [Sync your device manually to speed up app installations](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually) (Uw apparaat handmatig synchroniseren om de installatie van apps te versnellen) om de instructies voor eindgebruikers te bekijken.

**Bedrijfsportalwebsite** Wanneer gebruikers van Windows 10 Mobile en Windows Phone 8.1 LOB-apps installeren, zien ze nu de volgende nieuwe statussen, waardoor ze meer details over de status van hun installatie krijgen:

* **In afwachting van synchronisatie van het apparaat**: de gebruiker heeft op Installeren getikt en er wordt nu geprobeerd het apparaat te synchroniseren met de Intune-infrastructuur. Synchronisatie is vereist voordat de installatie kan worden voltooid. Het bericht 'In afwachting van synchronisatie van het apparaat' is ook een koppeling waarop gebruikers kunnen tikken om [instructies](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually) te zien over hoe zij hun apparaat handmatig kunnen synchroniseren met Intune als het synchronisatieproces lang duurt of vastloopt.
* **Downloaden**: de downloadaanvraag van de gebruiker wordt verwerkt en het apparaat downloadt en installeert de app.

Voordat deze statussen werden toegevoegd, raakten gebruikers in de war als de installatie van een app lang duurde, omdat ze alleen de status 'Installeren' zagen, die mogelijk uren lang op het scherm bleef staan. Het toevoegen van de nieuwe statussen betekent dat gebruikers in plaats van ondersteuning te bellen nu op de koppeling 'In afwachting van synchronisatie van het apparaat' kunnen tikken en de instructies voor het afdwingen van hervatting van het synchronisatieproces kunnen volgen.

>[!div class="step-by-step"]

>[&larr; **Wat is er nieuw in Intune?**](whats-new-in-microsoft-intune.md)    



<!--HONumber=Feb17_HO3-->


