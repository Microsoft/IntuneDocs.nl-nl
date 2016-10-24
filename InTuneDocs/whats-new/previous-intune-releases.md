---
title: Vorige versies | Microsoft Intune
description: 
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ffbb26f30c7801789a47d57ffed00696f5e6d81a
ms.openlocfilehash: 11e90ce994d17d9dcc62edba775dd0ab8110414e


---

# Vorige versies van Intune
## Augustus 2016
## Augustus 2016
## Appbeheer
<!---@Barry, I created the buckets of App management, Device management, etc but am not tied to them. Just wanted to break up and organize the feature list. If you're going to take over the Company Portal section, please talk to Stacie about how she's been organizing it. --->

### Verborgen en weergegeven apps voor iOS 9.3
Voor apparaten met supervisie met iOS 9.3 of hoger kunt u de lijst met verborgen of weergegeven apps in het algemene configuratiebeleid voor iOS gebruiken om het volgende te doen:
- Een lijst opstellen met apps die verborgen zijn voor gebruikers. Gebruikers kunnen deze apps niet weergeven of starten.
- Een lijst opstellen met apps die gebruikers kunnen weergeven en starten. Andere apps kunnen niet worden weergegeven of gestart.

De apps die u kunt opgeven zijn zowel apps die u hebt geïmplementeerd als de ingebouwde iOS-apps, zoals Berichten en Notities. Zie [Instellingen voor iOS-beleid in Microsoft Intune]( /intune/deploy-use/ios-policy-settings-in-microsoft-intune) voor meer informatie.
<!---TFS 1279009 checked--->
### Beleid voor toegestane en geblokkeerde apps voor Samsung KNOX-apparaten
U kunt nu een aangepast beleid voor Samsung KNOX-apparaten configureren, waarmee u het volgende kunt maken:
- Een lijst met apps die niet kunnen worden uitgevoerd op het apparaat. Apps in deze lijst kunnen niet op het apparaat worden geactiveerd, ongeacht of ze daarop zijn geïnstalleerd.
- Een lijst met apps die gebruikers van het apparaat kunnen installeren uit de Google Play Store. Geen andere apps kunnen worden geïnstalleerd uit de Store.

Deze instellingen kunnen alleen worden gebruikt door apparaten met Samsung KNOX.
Zie [Aangepaste beleidsregels gebruiken om apps toe te staan of te blokkeren voor Samsung KNOX-apparaten](/intune/deploy-use/custom-policy-to-allow-and-block-samsung-knox-apps) voor meer informatie.
<!---TFS 1311629 checked --->
### Nieuwe apps die compatibel zijn met de beleidsregels van Mobile Application Management (MAM)
De app Yammer voor [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) en [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) is nu compatibel met [de Intune MAM-beleidsregels (Mobile Application Management)](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune), ongeacht of het apparaat is ingeschreven of niet.

Zie de website [Microsoft Intune-toepassingspartners](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) voor een volledige lijst met apps die compatibel zijn met MAM.
<!--- TFS 1252335 & 1252336 checked--->


<!--- I started putting TFS numbers in the What's Coming topic and found it helpful when updating the What's New. Up to you if you want to continue. --->

### Intune-viewer-apps
Met het uitbrengen van de nieuwe RMS-app voor delen, worden de volgende Intune-viewer-apps vanaf augustus 2016 verwijderd:
- Intune AV-viewer
- Intune PDF-viewer
- Intune-afbeeldingsviewer voor Android van Google Play

In plaats van de viewer-apps van Intune kunt u beter de nieuwe [Rights Management-app (RMS sharing) voor Android](/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app) gebruiken, zodat u één app in plaats van drie afzonderlijke apps kunt implementeren om veilig bedrijfsbestanden op Android-apparaten te bekijken. Als de Intune-viewer-app niet meer wordt ondersteund, wordt deze verwijderd uit de Google Store en zal deze niet meer beschikbaar zijn voor toekomstig gebruik.

## Apparaatbeheer
### Android 7.0-ondersteuning
Intune biedt vanaf dag één ondersteuning voor het toekomstige Android 7.0-besturingssysteem voor mobiele apparaten.
<!---TFS 1262053--->
### Google verwijdert het op afstand opnieuw instellen van de wachtwoordcode voor Android 7.0-apparaten
Google verwijdert de mogelijkheid van IT-beheerders en eindgebruikers om de wachtwoordcode van Android 7.0-apparaten op afstand opnieuw in te stellen. Voorheen konden IT-beheerders op afstand de wachtwoordcode van een gebruiker opnieuw instellen, en konden eindgebruikers hun wachtwoordcodes opnieuw instellen via de bedrijfsportalwebsite.



## Updates voor de bedrijfsportal
### Bedrijfsportalwebsite
- **Feedbackkoppeling van de bedrijfsportal naar Microsoft** <br/>
Op de website van de bedrijfsportal kunnen eindgebruikers tikken op de nieuwe koppeling Feedback onder aan de pagina en zo feedback verzenden naar Microsoft over hun ervaringen met de site. De verzamelde, geanonimiseerde feedback helpt Microsoft bij het verbeteren van de gebruikerservaring van de bedrijfsportalwebsite.
<!--- TFS 1313657 checked--->

### iOS
- **Minimale iOS Managed Browser-versie is bijgewerkt naar 8.0**<br/>
De Microsoft Intune Managed Browser-app voor iOS is bijgewerkt voor ondersteuning van apparaten met iOS 8.0 of hoger. Hoewel op iOS 7.1-apparaten nog steeds de bestaande Managed Browser-app kan worden gebruikt, is het verstandig om uw gebruikers aan te raden hun apparaat bij te werken naar iOS 8.0 of hoger, zodat ze volledig kunnen profiteren van de nieuwe Managed Browser-functies.  
<!---TFS 1313253 checked--->

## Binnenkort

### Ondersteuning voor iOS 10
Intune biedt volledige ondersteuning voor iOS 10. Meer informatie volgt bij de openbare release van iOS 10.

### Intune-groepen stappen over naar Azure Active Directory-groepen met ingang van september 2016
Intune is bezig met het creëren van een nieuwe ervaring voor het beheer van groepen die gebruikmaakt van Azure Active Directory (AAD)-beveiligingsgroepen als gebruikers- en apparaatgroepen in Intune. Deze groepen worden gebruikt voor alle groepsbeheer en voor implementatie van beleid en profielen **wanneer wij het nieuwe op Azure gebaseerde Intune-beheerportal introduceren**.

Door deze nieuwe ervaring hoeft u niet langer groepen te dupliceren tussen services, **hebt u toegang tot een aantal nieuwe groepsfuncties van Azure Active Directory Premium (AADP)**, en profiteert u van uitbreidbaarheid met behulp van PowerShell en Graph. Dit zorgt tevens voor een uniforme ervaring voor groepsbeheer voor het gehele beheer van bedrijfsmobiliteit.

Om de overstap naar beveiligingsgroepen mogelijk te maken, wordt de ervaring in de **huidige beheerconsole** ietwat gewijzigd. **Deze wijzigingen, en het gebruik van AAD-beveiligingsgroepen, worden beschreven in de Intune-documentatie**.

Voor nieuwe Intune-klanten worden bepaalde **wijzigingen van beveiligingsgroepen eerder doorgevoerd dan voor bestaande klanten**.

Naast de wijzigingen in het groepsbeheer, **wordt de volgende functionaliteit afgeschaft**:
- Uitsluiten van leden of groepen tijdens het maken van een nieuwe groep
- Groepen van **Niet-gegroepeerde gebruikers** en **Niet-gegroepeerde apparaten**
- **Groepen beheren** in de rol van servicebeheerder
- Aangepaste waarschuwingen op basis van groepen voor meldingsregels
- Draaien met groepen in rapporten
<!--- TFS 1295329--->

### Toevoeging van 'Meldingen' aan de bedrijfsportal voor Android
In september brengen wij een update uit van de bedrijfsportal voor Android, waarmee een nieuw pictogram **Meldingen** wordt geïntroduceerd op de startpagina. Door op dit pictogram te tikken wordt de pagina **Meldingen** geopend waar de eindgebruiker alle items ziet die aandacht vereisen in de bedrijfsportal-app, zoals niet-compatibele apparaten, inschrijvingsupdates en activering van inschrijvingen. Als u ook de iOS-bedrijfsportal-app gebruikt, kunt u de meldingen al zien. Door de introductie van de pagina **Meldingen** ziet u niet langer de pagina **Bedrijfstoegang instellen** wanneer u de bedrijfsportal voor Android start of hervat als het apparaat reeds is ingeschreven. Wij weten dat velen van u een handleiding hebben gemaakt voor eindgebruikers en stellen het op prijs wanneer u ons tijdig informeert wanneer uw handleiding en/of schermafbeeldingen moeten worden bijgewerkt. Werk uw documentatie bij zodat toekomstige wijzigingen in de gebruikerservaring goed worden beschreven. Bijgewerkte schermafbeeldingen vindt u hier: https://aka.ms/androidcpupdate.  

### Verbeteringen aan hoe iOS-eindgebruikers hun apps verkrijgen
De volgende wijzigingen worden in september aangebracht aan de apptegels in de Bedrijfsportal-app voor iOS, zodat gebruikers op één locatie (de Bedrijfsportal-app) naar verschillende weergaven worden verwezen voor alle apps. Op dit moment wordt het door Apple verboden om line-of-business en beheerde App Store-apps te vermelden in de Bedrijfsportal-app en moeten gebruikers verschillende weergaven openen om al hun apps te vinden.

- De tegel **Bedrijfsapps** verwijst momenteel naar alle apps op het tabblad ALLE van de Bedrijfsportal-website, en deze blijft ook op dezelfde manier werken. De naam van de tegel wordt gewijzigd in **Alle apps**.
- De tegel **Andere apps** verwijst momenteel naar een weergave in de Bedrijfsportal-app waarin alle apps worden vermeld die van Apple mogen weergegeven in de app. De naam van de tegel wordt gewijzigd in **Uitgelichte apps**. Wanneer gebruikers op de tegel tikken, gaan ze naar het tabblad UITGELICHT van de Bedrijfsportal-website.
-  De tegel **Categorieën** verwijst momenteel naar een weergave in de Bedrijfsportal-app waarin appcategorieën worden vermeld. De naam van de tegel wordt niet gewijzigd, maar verwijst nu naar het tabblad CATEGORIEËN van de Bedrijfsportal-website. U vindt [hier](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186) bijgewerkte schermafbeeldingen.
<!---TFS 1317133--->

### Cloudroadmap
Blijf op de hoogte van toekomstige ontwikkelingen op het gebied van Intune met de [Cloud Platform roadmap](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).

### Serviceafschaffing
<!---@Barry, we started listing service deprecations earlier this summer. --->
- **Wijzigingen in de ondersteuning voor de iOS-bedrijfsportal-app**<br/>
In september moeten alle gebruikers van de Microsoft Intune-bedrijfsportal-app voor iOS overstappen naar de nieuwste versie. Nieuwe gebruikers kunnen alleen de nieuwste versie downloaden en bestaande gebruikers moeten bijwerken naar de nieuwe versie. De meest recente versie vereist iOS 8.0 of hoger, zodat apparaten met oudere versies van iOS de bedrijfsportal niet kunnen gebruiken en niet kunnen registreren totdat ze hun apparaat naar hebben bijgewerkt naar iOS 8.0 of hoger en vervolgens de bedrijfsportal-app bijwerken naar de nieuwste versie. Geregistreerde apparaten met een versie lager dan iOS 8.0 worden gewoon nog worden beheerd met en vermeld in de Intune-beheerconsole.  

- **Minimale iOS Managed Browser-versie is bijgewerkt naar 8.0**<br/>
In augustus brengt Intune een bijgewerkte Microsoft Intune Managed Browser-app uit voor iOS die alleen apparaten ondersteund waarop iOS 8.0 of later wordt uitgevoerd. Hoewel iOS 7.1-apparaten nog steeds de bestaande Managed Browser-app kunnen gebruiken, dient u uw gebruikers aan te moedigen bij te werken naar iOS 8.0 of later om volledig te kunnen profiteren van nieuwe functies van Managed Browser.  
<!---TFS 1313253--->

- **Bedrijfsportal-apps voor Windows 8 en Windows Phone 8 worden afgeschaft** <br/>
Vanaf oktober 2016 biedt Microsoft Intune geen ondersteuning meer voor Windows 8- en Windows Phone 8-bedrijfsportal-apps. Microsoft Intune biedt dan ook geen ondersteuning meer voor het Windows Phone 8-platform. Als gevolg hiervan kunt u geen Windows Phone 8-apparaten meer registreren of bijwerken. U kunt Windows Phone 8- en Windows 8-apparaten die al zijn geregistreerd blijven beheren. Werk Windows 8- en Windows Phone 8-apparaten bij naar Windows 8.1 en Windows Phone 8.1. Gebruik de bijbehorende bedrijfsportal-apps voor Windows 8.1 en Windows Phone 8.1 om zonder onderbrekingen door te gaan met het distribueren van apps naar deze apparaten.
<!---TFS 1255391--->

<!--- - **Custom Group Targeting of Notification Rules Removal.**<br/>
Intune notification rules define who an email alert will be sent to from Intune. Currently, you can configure notification rules to send emails to all users of devices in an Intune device group that you created. From around June 1st 2016 moving forward, targeting user-created groups will no longer be supported.

    Today, to target a notification rule to a group you created from the Microsoft Intune administration console, you would take the following steps:

    In the **Admin** workspace, click **Notification Rules** > **Create New Rule**

    In step two of the Create Notification Rule Wizard, select the device groups which the rule will target. This step, “select device groups”, is being removed from the Intune Console.

    The preliminary timeline for this change is as follows:
    - In August, 2016, new tenants will not see step two of the Create Notification Rule Wizard. Exiting tenants are unaffected.
    - Around September, 2016, some existing tenants will not see the “select device groups” in the wizard.
    - Around November, 2016, we expect that all tenants will not see the “select device groups” in the wizard.

--->

## Juli 2016
### Appbeheer
#### De update-ervaring van het inrichtingsprofiel van de app verbeteren
Apple iOS mobiele Line-Of-Business-apps zijn gebouwd met een inrichtingsprofiel en code die is ondertekend met een certificaat. Wanneer de app wordt uitgevoerd op een iOS-apparaat, bevestigt iOS de integriteit van de iOS-app en worden beleidsregels afgedwongen die zijn gedefinieerd door het inrichtingsprofiel.

Het handtekeningcertificaat voor ondernemingen dat u gebruikt om apps te ondertekenen is doorgaans 3 jaar geldig. Het inrichtingsprofiel verloopt echter na één jaar. Met deze update biedt Intune u de hulpmiddelen om proactief een nieuw beleid voor inrichtingsprofielen te implementeren op apparaten met apps die bijna zijn verlopen terwijl het certificaat nog geldig is. Zie voor meer informatie [iOS-beleid voor mobiele inrichtingsprofielen gebruiken om uw Line-Of-Business-apps up-to-date te houden](/intune/deploy-use/ios-mobile-app-provisioning-profiles).
<!--- TFS 1280247--->
#### Xamarin SDK voor Intune-apps is beschikbaar
Met het onderdeel Intune App SDK Xamarin kunt u de beheerfuncties voor Intune Mobile App inschakelen in mobiele iOS- en Android-apps die zijn gebouwd met Xamarin. U vindt het onderdeel in de [Xamarin Store](https://components.xamarin.com/view/Microsoft.Intune.MAM) of op de [Microsoft Intune Github-pagina](https://github.com/msintuneappsdk).
<!--- TFS 1061478 --->

### Apparaatbeheer
#### Verbeterde limieten voor apparaatinschrijvingen
Intune heeft de maximaal configureerbare limiet voor apparaatinschrijvingen verhoogd van 5 naar 15 apparaten per gebruiker.
<!---TFS 1289896 --->

#### TeamViewer-integratie voor Windows-pc's met de Intune-clientsoftware
Dankzij de integratie van [TeamViewer](https://www.teamviewer.com) voor Windows-pc's die worden beheerd met de Intune-client kunt u, ter ondersteuning van uw helpdeskafdeling, sessies voor hulp op afstand met Windows-pc's uitvoeren. Dit is van toepassing op Windows 7, 8, 8.1 en 10. Zie [Algemene beheertaken voor Windows-pc’s met de Microsoft Intune-computerclient voor meer informatie](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client).
<!---TFS 1284856--->

### Updates voor de bedrijfsportal
#### Bedrijfsportalwebsite
- **Verbeterde ervaring voor de eindgebruiker bij het inschrijven van Windows-apparaten**<br/>
Wanneer u voorwaardelijke toegang gebruikt, zijn de stappen voor inschrijving voor Windows 8.1, Windows 10 Desktop en Windows 10 Mobile verbeterd op de bedrijfsportalwebsite. Gebruikers zien nu de afzonderlijke stappen 'Apparaatinschrijving' en 'Workplace Join', waardoor de status van hun apparaat beter zichtbaar is en het proces eenvoudiger kan worden voltooid wanneer er een fout optreedt met Workplace Join (WPJ). De afzonderlijke stappen vereenvoudigen tevens de probleemoplossing voor IT-beheerders. Wanneer eindgebruikers voorheen probeerden in te schrijven en alle inschrijvingsstappen waren geslaagd behalve WPJ, dan werd het ingeschreven apparaat niet weergegeven in de lijst met apparaten voor gebruikers, wat verwarrend was voor gebruikers.

#### Android
- **Android-bedrijfsportal-app**<br/>
Als Android-eindgebruikers een foutmelding krijgen dat er een vereist certificaat ontbreekt voor hun apparaat, dan kunnen zij op een knop 'Oplossing' tikken voor [stappen](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) om het ontbrekende certificaat te installeren. Als gebruikers de stappen voltooien, maar er nogmaals een foutmelding over een ontbrekend certificaat wordt weergegeven, dan wordt hen gevraagd contact op te nemen met de IT-beheerder en deze [koppeling](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues) door te geven die de stappen bevat waarmee IT-beheerders het certificaatprobleem kunnen oplossen.

- **Beperken van extern geladen (ofwel 'side-loaded') app-installaties op ingeschreven apparaten**<br/>
Android-apparaten kunnen geen toepassingen meer installeren via de bedrijfsportalwebsite tenzij deze apparaten zijn ingeschreven bij Intune via de Intune-bedrijfsportal-app voor Android.
<!---TFS 1299082--->

#### iOS
- **Wijzigingen in de beheeraccounts voor apparaatinschrijving in de iOS-bedrijfsportal-app**<br/>
Om de prestaties en schaalbaarheid te verbeteren, worden in het deelvenster **Mijn apparaten** van de iOS-bedrijfsportal-app niet meer alle Device Enrollment Managers (DEM)-apparaten weergegeven door Intune. Alleen het lokale apparaat waarop de app wordt uitgevoerd, wordt weergegeven en wel alleen als het apparaat is geregistreerd via de bedrijfsportal-app.

De DEM-gebruiker kan acties op het lokale apparaat uitvoeren, maar extern beheer van andere geregistreerde apparaten kan alleen worden uitgevoerd vanuit de Intune-beheerconsole. Daarnaast is het gebruik in Intune van DEM-accounts met het Apple Device Enrollment Program of het hulpprogramma Apple Configurator beëindigd. Deze twee registratiemethoden bieden al ondersteuning voor gebruikersloze registratie voor gedeelde iOS-apparaten.

Gebruik alleen DEM-accounts wanneer gebruikersloze registratie voor gedeelde apparaten niet beschikbaar is. Zie voor meer informatie [Apparaten in bedrijfseigendom inschrijven met de apparaatinschrijvingsbeheerder in Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

### Wijziging van de namen voor Windows-functies
- [Microsoft Passport for Windows](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) is nu bekend als **Windows Hello voor Bedrijven**.
- [Ondernemingsgegevensbescherming](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) is nu bekend als **Windows Information Protection**.

## Juni 2016
### Servicestatus van Intune
Servicestatusgegevens voor Intune is verplaatst naar een centrale locatie met andere Microsoft-services. U vindt deze informatie nu in de Office 365-beheerportal onder Servicestatus. Lees [dit blogbericht](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/) voor meer informatie.

### Appbeheer
- **Verbeterde ervaring voor configuratie van Windows 10-beleid voor ondernemingsgegevens.** Er zijn verbeteringen aangebracht in de ervaring voor configuratie van het Windows 10-beleid voor ondernemingsgegevensbescherming. Deze verbeteringen hebben betrekking op het maken van app-regels, het opgeven van netwerkdefinities en op andere instellingen voor ondernemingsgegevensbescherming. Zie [Een Enterprise Data Protection-beleid (EDP) maken met Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) voor meer informatie.


### Apparaatbeheer
- **Windows Defender-beleidsinstelling voor beveiliging tegen mogelijk ongewenste apps.** **Detectie van mogelijk ongewenste toepassingen** is een nieuwe Windows Defender-instelling die toegevoegd aan het algemene configuratiebeleid voor Windows 10 Desktop en Mobile. U kunt deze instelling gebruiken als u geregistreerde Windows-desktopcomputers wilt beveiligen tegen het uitvoeren van software die door Windows Defender als mogelijk ongewenst is gedefinieerd. U kunt voorkomen dat deze toepassingen worden uitgevoerd, of de controlemodus gebruiken om te rapporteren wanneer een mogelijk ongewenste toepassing wordt geïnstalleerd. Zie [Windows 10-beleidsinstellingen in Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune) voor meer informatie.
<!---TFS 1244478--->

### Voorwaardelijke toegang
- **Cisco ISE-netwerktoegangscontrolebeleid voor Intune.**  Klanten die Cisco Identity Service Engine (ISE) 2.1 en Microsoft Intune gebruiken, kunnen een netwerktoegangsbeleid instellen in ISE.

    Met dit beleid moeten apparaten die via Wi-Fi of VPN verbinding willen maken met het netwerk, voldoen aan de volgende voorwaarden voordat ze toegang krijgen:

    * Moeten worden beheerd met Intune
    * Moeten voldoen aan geïmplementeerd Intune-nalevingsbeleid

 Eindgebruikers van niet-compatibele apparaten wordt gevraagd zich te registreren en nalevingsproblemen op te lossen om toegang te krijgen.
- **Voorwaardelijke toegang voor de browser.** U kunt een beleid voor voorwaardelijke toegang instellen voor [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) en [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune), zodat deze alleen toegankelijk zijn via ondersteunde webbrowsers op beheerde en compatibele iOS- en Android-apparaten. Eindgebruikers die proberen zich met iOS- en Android-apparaten aan te melden bij Outlook Web Access (OWA) en SharePoint-sites, wordt gevraagd hun apparaat te registreren bij Intune en eventuele problemen met de compatibiliteit op te lossen. Hierna kan de aanmelding worden voltooid.
<!---TFS 1175844--->

- **Dynamics CRM Online biedt ondersteuning voor voorwaardelijke toegang.** U kunt beleid voor voorwaardelijke toegang instellen voor [Dynamics CRM Online](/intune/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune), zodat dit alleen toegankelijk is voor beheerde en compatibele iOS- en Android-apparaten. Eindgebruikers die zich op iOS en Android willen aanmelden bij de mobiele app Dynamics CRM, moeten zich registreren bij Intune en eventuele problemen met de naleving oplossen voordat de aanmelding wordt voltooid.
<!---TFS1295358--->

##Updates voor de E-bedrijfsportal

#### Android-bedrijfsportal-app

- Wanneer IT-beheerders het nieuwe beleid Vereisen dat apparaten de installatie van apps van onbekende bronnen niet toestaan (Android 4.0+) toepassen, krijgen eindgebruikers met een apparaat met Android 4.0 of hoger het volgende bericht te zien: De installatie vanuit onbekende bronnen moet worden uitgeschakeld. Gebruikers moeten naar **Instellingen** > **Beveiliging** gaan en **Onbekende bronnen** uitschakelen. Via een koppeling in het nalevingsbericht kunnen gebruikers meer [informatie](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android) verkrijgen over het bericht en over waarom ze de instelling moeten uitschakelen.

- Wanneer IT-beheerders het nieuwe beleid Vereisen dat apparaten het scannen van apps op beveiligingsrisico's inschakelen (Android 4.0+) toepassen, krijgen eindgebruikers met een apparaat met Android 4.0 of hoger het volgende bericht te zien: Apparaat scannen op beveiligingsrisico's. Gebruikers moeten naar **Instellingen** > **Google** > **Beveiliging** gaan en **Apparaat scannen op beveiligingsrisico's** inschakelen. Via een koppeling in het nalevingsbericht kunnen gebruikers meer [informatie](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) verkrijgen over het bericht en over waarom ze de instelling moeten inschakelen.

- Wanneer IT-beheerders het nieuwe beleid Vereisen dat USB-foutopsporing wordt uitgeschakeld (Android 4.2+) toepassen, krijgen eindgebruikers met een apparaat met Android 4.2 of hoger het volgende bericht te zien: USB-foutopsporing moet worden uitgeschakeld. Gebruikers moeten naar **Instellingen** > **Opties voor ontwikkelaars** gaan en **USB-foutopsporing** uitschakelen. Via een koppeling in het nalevingsbericht kunnen gebruikers meer [informatie](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android) verkrijgen over het bericht en over waarom ze de instelling moeten uitschakelen.

- Wanneer IT-beheerders het nieuwe beleid Minimaal niveau voor de Android-beveiligingspatch (Android 6.0+) toepassen, krijgen eindgebruikers met een apparaat met Android 6.0 of hoger het volgende bericht te zien: Dit apparaat voldoet niet aan het minimale Android-beveiligingspatchniveau. Gebruikers moeten de vereiste beveiligingspatch installeren. Via een koppeling in het nalevingsbericht kunnen gebruikers meer [informatie](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) verkrijgen over hoe de vereiste beveiligingspatch moet worden geïnstalleerd en over welke beveiligingspatch momenteel is geïnstalleerd.

#### iOS-bedrijfsportal-app

- Eindgebruikers die LOB-apps installeren, hebben nu een verbeterde ervaring tijdens de installatie van deze apps. Als de app-installatie lang duurt, kunnen gebruikers hun apparaat handmatig synchroniseren om hervatting van het synchronisatieproces af te dwingen. Zie [Sync your iOS device manually](/Intune/EndUser/sync-your-device-manually-ios) (Uw iOS-apparaat handmatig synchroniseren) voor de instructies voor eindgebruikers.

- De Microsoft Intune-bedrijfsportal-app voor iOS is bijgewerkt. Nu wordt iOS-versie 8.0 en hoger ondersteund. Deze update betekent dat eindgebruikers de bedrijfsportal-app kunnen installeren en alleen nieuwe apparaten kunnen registreren bij Intune als het apparaat iOS-versie 8.0 of hoger heeft. Gebruikers die werken met eerder ingeschreven apparaten met niet-ondersteunde versie van iOS kunnen de bedrijfsportal-app die op hun apparaat is geïnstalleerd blijven gebruiken.


## Mei 2016

Al deze functies worden ook ondersteund voor hybride implementaties (Configuration Manager met Intune). Zie de pagina met [nieuwe hybridefuncties](https://technet.microsoft.com/en-us/library/mt718155.aspx) (Engelstalig) voor meer informatie over nieuwe hybridefuncties.

### Documentatie
Dit is de preview-versie van [docs.microsoft.com](https://docs.microsoft.com/en-us/intune).
Dit is een volledig nieuw, modern inhoudsplatform dat is ontworpen om Intune gebruikersvriendelijker en eenvoudiger te maken.
Zie [Kennismaking met docs.microsoft.com](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/)

### Servicestatus van Intune
Servicestatusgegevens voor Intune is verplaatst naar een centrale locatie met andere Microsoft-services. U vindt deze informatie nu in de [Office 365-beheerportal](https://portal.office.com/Admin/Default.aspx) onder **Servicestatus**.
Lees [dit blogbericht](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/) voor meer informatie.


### Appbeheer
- **MAM SDK: ondersteuning voor configuratie van de lengte van de pincode.** Net als bij pincodes voor apparaten het geval is, kunt u ook voor MAM-apps de lengte van de pincode opgeven. Hiervoor moeten eindgebruikers voldoen aan de nieuwe beperkingen die u instelt. Ze zien dan een enigszins gewijzigd pincodescherm, waarin de langere code kan worden ingevoerd. Zie [MAM-beleidsinstellingen voor Android](/intune/deploy-use/android-mam-policy-settings) en [MAM-beleidsinstellingen voor iOS](/intune/deploy-use/ios-mam-policy-settings) voor meer informatie.

- **Skype voor Bedrijven voor iOS en Android.** U kunt Skype voor Bedrijven nu gebruiken met [MAM zonder inschrijvingsbeleid](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune). Zodra gebruikers zich aanmelden, wordt het MAM-beleid toegepast.

- **Nieuwe beschikbare apps voor beheer met MAM-beleid.** De Microsoft Word-, Excel- en PowerPoint-apps voor Android kunnen nu worden gekoppeld aan MAM-beleid op apparaten die niet zijn geregistreerd bij Intune. Ga voor de volledige lijst met ondersteunde apps naar de galerie met mobiele toepassingen van Microsoft Intune op de pagina [Microsoft Intune-toepassingen van partners](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).


### Updates voor de bedrijfsportal

#### Android-bedrijfsportal-app
- **Pop-upmeldingen voor eindgebruikers**: eindgebruikers krijgen nu pop-upmeldingen uit de Android-bedrijfsportal te zien wanneer ze hun apparaten registreren bij of verwijderen uit de bedrijfsportal.

- **Wijzigingen in de apparaatregistratiebeheeraccounts in de Android-bedrijfsportal-app.** Ter verbetering van de prestaties en schaalbaarheid worden er in het deelvenster Mijn apparaten van de Android-bedrijfsportal-app niet meer alle DEM-apparaten (Device Enrollment Manager; apparaatregistratiebeheer) door Intune weergegeven. Alleen het lokale apparaat waarop de app wordt uitgevoerd, wordt weergegeven en wel alleen als het apparaat is geregistreerd via de bedrijfsportal-app. De DEM-gebruiker kan acties op het lokale apparaat uitvoeren, maar extern beheer van andere geregistreerde apparaten kan alleen worden uitgevoerd vanuit de Intune-beheerconsole.

#### Bedrijfsportalwebsite
- **Bedrijfsportalwebsite: de banner voor apparaatidentificatie biedt eindgebruikers meer informatie.** Eindgebruikers kunnen het apparaat dat ze hebben geselecteerd, nu gemakkelijker identificeren wanneer ze de website van de bedrijfsportal gebruiken. Als er een verkeerd apparaat is geselecteerd, kunnen ze het juiste apparaat selecteren door op de koppeling **Tik hier** in de banner op de startpagina te tikken.

## Binnenkort
- **Onboarding van de gebruikersinterface van Berichtencentrum**. Als onderdeel van de migratie van Intune in de [Office 365-beheerportal](https://portal.office.com/) benutten we het bijbehorende Berichtencentrum om nieuwe functies en andere meldingen te communiceren. U kunt ook de bijbehorende mobiele app voor Office 365-beheer installeren om meldingen te ontvangen op uw mobiele telefoon en eenvoudig berichten naar gebruikers of een distributiealias te sturen.
We gebruiken het Berichtencentrum voor onze release in mei om u te laten weten wanneer er updates voltooid zijn. Ook brengen we u op de hoogte van nieuwe en verbeterde Intune-functies. Bekijk het Berichtencentrum meteen door u aan te melden bij de [Office 365-beheerportal](https://portal.office.com/) en de optie BERICHTENCENTRUM te kiezen in het navigatiepaneel aan de linkerkant.

- **Wijzigingen in de apparaatregistratiebeheeraccounts**. Ter verbetering van de prestaties en schaalbaarheid worden er in het deelvenster **Mijn apparaten** van de iOS-bedrijfsportal-app niet meer **alle** DEM-apparaten (Device Enrollment Manager; apparaatregistratiebeheer) door Intune weergegeven. Alleen het lokale apparaat waarop de app wordt uitgevoerd, wordt weergegeven en wel alleen als het apparaat is geregistreerd via de bedrijfsportal-app. De DEM-gebruiker kan acties op het lokale apparaat uitvoeren, maar extern beheer van andere geregistreerde apparaten kan alleen worden uitgevoerd vanuit de Intune-beheerconsole. Daarnaast is het gebruik in Intune van DEM-accounts met het Apple Device Enrollment Program of het hulpprogramma Apple Configurator beëindigd. Deze twee registratiemethoden bieden al ondersteuning voor gebruikersloze registratie voor gedeelde iOS-apparaten. Gebruik alleen DEM-accounts wanneer gebruikersloze registratie voor gedeelde apparaten niet beschikbaar is.

### Cloudroadmap
Blijf op de hoogte van toekomstige ontwikkelingen op het gebied van Intune met de [Cloud Platform roadmap](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).

### Serviceafschaffing
- **Intune-viewer-apps.** Met het uitbrengen van de nieuwe RMS-app voor delen, worden volgende Intune-viewer-apps vanaf augustus 2016 verwijderd:
    - Intune AV-viewer
    - Intune PDF-viewer
    - Intune-afbeeldingsviewer voor Android van Google Play

  In plaats van de viewer-apps van Intune kunt u beter de nieuwe Rights Management-app (RMS sharing) voor Android gebruiken, zodat u één app in plaats van drie afzonderlijke apps kunt implementeren om veilig bedrijfsbestanden op Android-apparaten te bekijken. Meer informatie over de app RMS sharing (met een koppeling naar de documentatie).

- **Meldingsregels voor aangepaste groepen wordt verwijderd.**
Met de Intune-meldingsregels wordt gedefinieerd wie een e-mailwaarschuwing ontvangt Intune. Op dit moment kunt u meldingsregels configureren om e-mails te verzenden naar alle gebruikers van apparaten in een Intune-apparaatgroep die u hebt gemaakt. Vanaf 1 juni 2016 wordt de targeting van groepen die zijn gemaakt door gebruikers, niet meer ondersteund.

    Als u nu een meldingsregel wilt targeten op een groep die u in de Microsoft Intune-beheerconsole hebt gemaakt, voert u de volgende stappen uit:

    Klik in de werkruimte **Beheerder** op **Meldingsregels** > **Nieuwe regel maken**

    In stap 2 van de wizard Meldingsregel maken selecteert u de apparaatgroepen waarop de regel betrekking heeft. De stap voor het selecteren van apparaatgroepen wordt uit de Intune-console verwijderd.

    De voorlopige tijdlijn voor deze wijziging is als volgt:
    - In juni 2016 krijgen nieuwe tenants stap 2 van de wizard Meldingsregel maken niet meer te zien. Voor de huidige tenants blijft de situatie ongewijzigd.
    - Rond augustus 2016 krijgen enkele bestaande tenants de wizardoptie voor het selecteren van apparaatgroepen niet meer te zien.
    - Naar verwachting krijgt rond oktober 2016 geen enkele bestaande tenant de wizardoptie voor het selecteren van apparaatgroepen nog te zien.


- **Wijzigingen in de ondersteuning voor de iOS-bedrijfsportal-app**. In de komende maanden zal de Microsoft Intune-bedrijfsportal-app voor iOS worden bijgewerkt en biedt deze alleen nog ondersteuning voor apparaten met iOS 8.0 of later. Gebruikers kunnen geen nieuwe apparaten met een versie lager dan iOS 8.0 registreren. Geregistreerde apparaten met een versie lager dan iOS 8.0 worden gewoon nog beheerd en kunnen, voor een beperkte periode, gebruik blijven maken van de bedrijfsportal-app. Apparaten moeten echter over iOS 8.0 of later beschikken voor toegang tot de nieuwste versie van de bedrijfsportal-app. U kunt gebruikers het beste adviseren bij te werken naar iOS 8.0 of later om optimaal gebruik te kunnen maken van de nieuwe Intune-functies.  


## April 2016
Al deze functies worden ook ondersteund voor hybride klanten (Configuration Manager geïntegreerd met Intune).
### Appbeheer
- **Naleving van beleid door MAM-gebruikers.**
U kunt nu de [status](/intune/deploy-use/monitor-mobile-app-management-policies-with-Microsoft-Intune) van uw beleid voor toepassingsbeheer bekijken voor gebruikers in uw AAD-tenant (Azure Active Directory). Dit omvat:
   - Apparaten
   - Apps op het apparaat

   Statuswaarden:

   **Ingecheckt**: hiermee wordt aangegeven dat het beleid is geïmplementeerd voor de gebruiker, dat de app is gebruikt in een werkcontext en dat het beleid is ontvangen.

    **Niet ingecheckt**: hiermee wordt aangegeven dat het beleid is geïmplementeerd voor de gebruiker, maar dat de app sindsdien niet is gebruikt in een werkcontext.


- **MAM-besturingselementen om te voorkomen dat Outlook-contactpersonen worden gesynchroniseerd (Android).**
Er is een nieuwe instelling beschikbaar voor [Mobile Application Management](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) zonder apparaatregistratie. Met deze instelling kunt u voorkomen dat een toepassing contactpersonen synchroniseert met het systeemeigen adresboek op Android-apparaten. Wanneer deze instelling is ingeschakeld, kunnen doeltoepassingen niet langer contactpersonen in het systeemeigen adresboek opslaan. Wanneer deze instelling is uitgeschakeld, kunnen doeltoepassingen wel contactpersonen in het systeemeigen adresboek opslaan. Wanneer u [een apparaat of app op afstand wist](/intune/deploy-use/wipe-managed-company-app-data-with-Microsoft-Intune), worden de contactpersonen verwijderd die al in het systeemeigen adresboek zijn opgeslagen. Deze nieuwe instelling wordt in eerste instantie ondersteund door de Outlook-toepassing op Android-apparaten.

### Apparaatbeheer
- **Nummerherkenning voor apparaten die bedrijfseigendom zijn.** Telefoons die zijn aangemerkt als bedrijfseigendom, worden nu aangeduid met hun volledige telefoonnummer wanneer u bijvoorbeeld een inventarisrapport voor mobiele apparaten uitvoert. Telefoonnummers voor BYOD-apparaten worden nog steeds gemaskeerd met ****, waarbij alleen de laatste 4 cijfers worden weergegeven.


### Updates voor bedrijfsportal
**Android-bedrijfsportal-app** Gebruikers die hun apparaat niet bij Intune hebben ingeschreven en bij wie niet het juiste certificaat is geïnstalleerd, kunnen zich niet aanmelden bij de bedrijfsportal-app voor Android en zien het bericht 'U kunt u niet aanmelden omdat een vereist certificaat ontbreekt op het apparaat'. Het bericht bevat een koppeling Oplossing waarop gebruikers kunnen tikken om instructies te zien voor het installeren van het certificaat. Zie [Er ontbreekt een vereist certificaat voor uw apparaat](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing) om te zien welke stappen eindgebruikers moeten volgen om het probleem op te lossen.

**iOS-bedrijfsportal-app** Er is ondersteuning toegevoegd voor de actie 'veeg naar beneden om te vernieuwen' om de inhoud van het startscherm (met onder meer de lijst met apps, de lijst met apparaten en de contactgegevens van de IT-afdeling) te vernieuwen. De actie 'veeg naar beneden om te vernieuwen' controleert niet op naleving van beleid of beleidsgegevens. Dat kunt u doen door de tegel voor uw huidige apparaat te selecteren en op de knop **Synchroniseren** te tikken.

**Windows 10 Mobile- en Windows Phone 8.1-bedrijfsportal-app** Eindgebruikers die LOB-apps installeren, hebben nu een verbeterde ervaring tijdens de installatie van deze apps. Als de app-installatie lang duurt, kunnen gebruikers hun apparaat handmatig synchroniseren om hervatting van het synchronisatieproces af te dwingen. Zie [Sync your device manually to speed up app installations](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually) (Uw apparaat handmatig synchroniseren om de installatie van apps te versnellen) om de instructies voor eindgebruikers te bekijken.

**Bedrijfsportalwebsite** Wanneer gebruikers van Windows 10 Mobile en Windows Phone 8.1 LOB-apps installeren, zien ze nu de volgende nieuwe statussen, waardoor ze meer details over de status van hun installatie krijgen:

* **In afwachting van synchronisatie van het apparaat**: de gebruiker heeft op Installeren getikt en er wordt nu geprobeerd het apparaat te synchroniseren met de Intune-infrastructuur. Synchronisatie is vereist voordat de installatie kan worden voltooid. Het bericht 'In afwachting van synchronisatie van het apparaat' is ook een koppeling waarop gebruikers kunnen tikken om [instructies](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually) te zien over hoe zij hun apparaat handmatig kunnen synchroniseren met Intune als het synchronisatieproces lang duurt of vastloopt.
* **Downloaden**: de downloadaanvraag van de gebruiker wordt verwerkt en het apparaat downloadt en installeert de app.

Voordat deze statussen werden toegevoegd, raakten gebruikers in de war als de installatie van een app lang duurde, omdat ze alleen de status 'Installeren' zagen, die mogelijk uren lang op het scherm bleef staan. Het toevoegen van de nieuwe statussen betekent dat gebruikers in plaats van ondersteuning te bellen nu op de koppeling 'In afwachting van synchronisatie van het apparaat' kunnen tikken en de instructies voor het afdwingen van hervatting van het synchronisatieproces kunnen volgen.


## Maart 2016
### Wat is er nieuw vanaf 29 maart 2016
Met uitzondering van de update voor het algemene configuratiebeleid voor Windows 10 worden alle functies die op 29 maart 2016 worden vrijgeven ook ondersteund voor hybride klanten (Configuration Manager geïntegreerd met Intune). Hybride ondersteuning voor de update van het algemene configuratiebeleid voor Windows 10 wordt binnenkort beschikbaar. Voor sommige van deze functies is mogelijk de nieuwste versie van Configuration Manager vereist.

### Appbeheer
- **MAM-besturingselementen om te voorkomen dat Outlook-contactpersonen worden gesynchroniseerd (iOS).** Er is een nieuwe instelling beschikbaar voor Mobile Application Management zonder apparaatregistratie. Met deze instelling kunt u voorkomen dat een toepassing contactpersonen synchroniseert met het systeemeigen adresboek op iOS-apparaten. Wanneer deze instelling is ingeschakeld, kan de app niet langer contactpersonen in het systeemeigen adresboek opslaan. Wanneer deze instelling is uitgeschakeld, kan de app contactpersonen in het systeemeigen adresboek opslaan. Wanneer u een apparaat selectief wist, worden de contactpersonen verwijderd die al in het systeemeigen adresboek waren opgeslagen. Deze nieuwe instelling wordt ondersteund door de Outlook-toepassing op iOS-apparaten. Zie [MAM-beleid maken en implementeren](https://technet.microsoft.com/en-us/library/dn292747.aspx) voor meer informatie over deze en andere instellingen.

### Toegangsbeheer
- **Skype voor Bedrijven Online biedt ondersteuning voor voorwaardelijke toegang.** U kunt een beleid voor voorwaardelijke toegang instellen voor Skype voor Bedrijven Online, zodat het programma alleen toegankelijk is voor beheerde en compatibele iOS- en Android-apparaten. Eindgebruikers die zich willen aanmelden bij de mobiele app voor Skype voor Bedrijven op iOS en Android, moeten zich registreren bij Intune en eventuele problemen met de naleving oplossen voordat de aanmelding wordt voltooid. Zie [Manage access to Skype for Business Online](https://technet.microsoft.com/en-us/library/mt695297.aspx) (Toegang tot Skype voor Bedrijven Online beheren) voor meer informatie.

### Apparaatbeheer
- **Intune-ondersteuning voor iOS 9.3.** Op maandag 21 maart heeft Apple aangekondigd dat iOS 9.3 beschikbaar wordt. Wij hebben er hard aan gewerkt om ervoor te zorgen dat Microsoft Intune compatibel is met de nieuwste versie van het mobiele besturingssysteem van Apple. [Intune biedt nu ondersteuning voor het beheer van iOS 9.3-apparaten](https://blogs.technet.microsoft.com/microsoftintune/2016/03/23/microsoft-intune-provides-support-for-ios-9-3/).

  Alle bestaande Intune-functies die momenteel beschikbaar zijn voor het beheer van iOS-apparaten blijven naadloos werken wanneer gebruikers hun apparaten upgraden naar iOS 9.3. iOS 9.3 wordt daarnaast nu ook ondersteund voor hybride klanten (Configuration Manager geïntegreerd met Intune).

- **Het algemene configuratiebeleid voor Windows 10 bevat nu instellingen voor het beheer van Windows Defender op ingeschreven Windows 10-pc's.** Zie [Instellingen voor configuratiebeleid voor Windows 10 in Microsoft Intune](https://technet.microsoft.com/en-us/library/mt404697.aspx) voor meer informatie


### Bedrijfsportal

- **Windows-app-pakketten die rechtstreeks via de bedrijfsportal-website beschikbaar zijn.** Gebruikers van pc's met Windows 8, Windows 8.1 en Windows RT kunnen nu Windows-app-pakketten (met de extensie .appx) rechtstreeks installeren vanaf de bedrijfsportal-website. Eerder moest u de bedrijfsportal-app implementeren of moesten gebruikers deze installeren op hun apparaten om apps te installeren.

- **Gebruikers kunnen hun apparaat extern vergrendelen op de bedrijfsportal-website.** Er is een nieuwe optie voor vergrendeling op afstand toegevoegd aan de bedrijfsportal-website, zodat gebruikers hun apparaat via de portal op afstand kunnen vergrendelen als hun apparaat zoekgeraakt of gestolen is. Zie de [instructies voor eindgebruikers](https://technet.microsoft.com/library/mt590895.aspx/?wt.mc_id=ui#BKMK_iwp_remote_lock). In de volgende tabel ziet u een lijst met de beschikbare platformondersteuning voor vergrendelen op afstand voor Intune Standalone en Intune met Configuration Manager.

|Platform | Ondersteuningsgegevens|
|---------|----------------|
|Android |Ondersteund|
|iOS |Ondersteund|
|Windows 10 Mobile |Alleen ondersteund als op de telefoon een wachtwoordcode is ingesteld|
|Windows 10 Desktop |Niet ondersteund|
|Windows Phone 8,1 |Alleen ondersteund als op de telefoon een wachtwoordcode is ingesteld|
|Windows Phone 8.0 |Niet ondersteund|
|Pc (Windows 8.0 en lager) |Niet ondersteund|
|Pc (Windows 8.1) |Niet ondersteund|

### Wat is er nieuw vanaf 10 maart 2016

### Appbeheer

- **Profiteren van iOS 'Open-in'-beheer voor apparaten die zijn ingeschreven bij een externe MDM-oplossing**. U kunt uw externe MDM-leverancier (Mobile Device Management) gebruiken om te profiteren van iOS 'Open-in'-beheer. U kunt de beperkingen in de configuratieprofielinstellingen configureren en de app implementeren via [Gegevensoverdracht tussen iOS-apps beheren](/intune/deploy-use/manage-data-transfer-between-ios-apps-with-microsoft-intune).

     Deze methode biedt twee belangrijke voordelen:

     1. Gebruikers moeten zich aanmelden met hun werkaccount voordat ze toegang tot bedrijfsgegevens krijgen via Cloud Services of andere apps. Hiermee zorgt u ervoor dat het MAM-beleid (Mobile App Management) wordt toegepast bij het openen van de gegevens.

     2. Beheerde e-mailprofielen en andere beheerde apps die worden geïmplementeerd via een MDM-oplossing van derden kunnen bestanden en gegevens delen met de apps die beschikken over Intune MAM-beleid.

- **De Microsoft Outlook-app met MAM-beleid beheren voor apparaten die niet zijn ingeschreven in Intune** U kunt nu de Microsoft Outlook-app beheren op apparaten die niet zijn ingeschreven in Intune met het Intune MAM-beleid. De bijgewerkte Microsoft Outlook-app met MAM-mogelijkheden is beschikbaar voor zowel [iOS](https://itunes.apple.com/us/app/microsoft-outlook-email-calendar/id951937596?mt=8)- als [Android](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook)-apparaten. Volg de instructies in het onderwerp [Beleid voor Mobile App Management maken en implementeren](https://technet.microsoft.com/library/mt627829.aspx) om MAM-beleid te maken.  


- **Configuratiebeleid voor mobiele apps biedt u meer flexibiliteit om gebruikersdetails voor iOS-apps op te geven** U kunt gebruikersinstellingen opgeven die een iOS-app mogelijk nodig heeft wanneer deze wordt geopend. U kunt bijvoorbeeld een netwerkpoort of een gebruikersnaam opgeven. Zie [iOS-apps met configuratiebeleid voor mobiele apps in Microsoft Intune configureren](/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune) voor meer informatie.


- **Adobe Reader voor Microsoft Intune implementeren op met Intune beheerde iOS-apparaten in uw onderneming** De Adobe Reader-app voor iOS kan nu worden beheerd op ingeschreven apparaten met het Intune Mobile Application Management-beleid.

- **Ervoor zorgen dat geïmplementeerde webclips worden geopend in Managed Browser** U kunt doelwebclips implementeren op iOS- en Android-apparaten die alleen kunnen worden geopend met behulp van Managed Browser. U implementeert bijvoorbeeld koppelingen naar bedrijfsbronnen via de bedrijfsportal, en wanneer gebruikers naar de koppelingen navigeren, worden deze rechtstreeks in Managed Browser geopend zodat er sprake is van beveiliging via MAM-beleid. Zie [Apps implementeren](/intune/deploy-use/deploy-apps) voor meer informatie.


- **Zoeken, beheren en distribueren van Windows Store voor Bedrijven-apps voor Windows 10-apparaten via de Intune-beheerconsole** Ondersteuning voor Windows Store voor Bedrijven is beschikbaar in Intune voor het helpen zoeken, beheren en distribueren van apps voor de Windows 10-apparaten die u beheert. In Windows Store voor Bedrijven kunt u het proces voor het implementeren en bewaken van deze apps beheren via de Intune-beheerconsole: dezelfde console die u gebruikt voor het beheren van uw andere apps. Windows Store voor Bedrijven beheert met name de inhoud en licenties van online gelicentieerde apps. Zie [Manage apps you purchased from the Windows Store for Business](/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune) (Apps beheren die u hebt aangeschaft in Windows Store voor Bedrijven) voor meer informatie.


### Apparaatbeheer
- **Distributie van PFX-certificaten voor iOS-apparaten** Intune-beheerders kunnen iOS PFX-certificaten maken en implementeren voor Wi-Fi-, e-mail- en VPN-verificatie op iOS-apparaten. Deze functie is al beschikbaar voor Android- en Windows 10-apparaten. Zie [Toegang tot bedrijfsbronnen inschakelen met behulp van certificaatprofielen](/intune/deploy-use/secure-resource-access-with-certificate-profiles) voor meer informatie.


- **Apps en beleid toepassen op verschillende apparaatgroepen op basis van de selectie van de gebruikerscategorie** Intune-beheerders kunnen nu aangepaste apparaatcategorieën definiëren waaruit gebruikers tijdens de registratie kunnen selecteren. Beheerders kunnen bijvoorbeeld hun gebruikers laten opgeven of ze een apparaat registreren dat gebruikt wordt voor de kassa, de vrachtwagen of het magazijn. Afhankelijk van de geselecteerde categorie wordt het apparaat lid van een Intune-apparaatgroep die kan worden gebruikt voor het implementeren van verschillende apps en beleidsregels voor het ingeschreven apparaat. Zie [Categorize devices with device group mapping](/intune/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune) (Apparaten categoriseren met apparaatgroeptoewijzing) voor meer informatie.

### Wijzigingen en updates voor de Microsoft-bedrijfsportal
In deze versie zijn de volgende wijzigingen aangebracht aan de bedrijfsportal.

**Android-bedrijfsportal-app**

* Wanneer gebruikers een app openen die wordt beheerd via Mobile Application Management (MAM), krijgen ze een bericht te zien met de melding dat de app wordt beheerd door het bedrijf. Gebruikers kunnen nu tikken op Meer informatie om [meer informatie](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_use_mgd_apps) te ontvangen over wat het betekent als apps worden beheerd. Ze kunnen ook tikken op Niet meer weergeven zodat het bericht niet meer wordt weergegeven bij het openen van de app.
* Er zijn ook nieuwe schermen toegevoegd om gebruikers door het registratieproces te leiden en meer informatie te bieden over waarom de gebruikers zich moeten registreren en over wat IT-beheerders wel en niet kunnen zien op de ingeschreven apparaten. Zie de [registratie-instructies](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc) voor meer informatie.
* Er worden nu registratiefoutberichten weergegeven in de bedrijfsportal-app. Deze berichten werden eerder weergegeven op de bedrijfsportal-website. Dankzij deze wijziging worden alle foutberichten nu op één plaats weergegeven in plaats van op twee verschillende plaatsen.


**iOS-bedrijfsportal-app**
* Wanneer gebruikers een app openen die wordt beheerd via Mobile Application Management (MAM), krijgen ze een bericht te zien met de melding dat de app wordt beheerd door het bedrijf. Gebruikers kunnen nu tikken op Meer informatie om [meer informatie](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_use_mgd_apps) te ontvangen over wat het betekent als apps worden beheerd. Ze kunnen ook tikken op Niet meer weergeven zodat het bericht niet meer wordt weergegeven bij het openen van de app.
* Er zijn ook nieuwe schermen toegevoegd om gebruikers door het registratieproces te leiden en meer informatie te bieden over waarom de gebruikers zich moeten registreren en over wat IT-beheerders wel en niet kunnen zien op de ingeschreven apparaten. Zie de [registratie-instructies](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device) voor meer informatie.
* Er worden nu registratiefoutberichten weergegeven in de bedrijfsportal-app. Deze berichten werden eerder weergegeven op de bedrijfsportal-website. Dankzij deze wijziging worden alle foutberichten nu op één plaats weergegeven in plaats van op twee verschillende plaatsen.




## Februari 2016
### Wijzigingen en updates voor de Microsoft-bedrijfsportal

In deze versie zijn de volgende wijzigingen aangebracht aan de bedrijfsportal.

#### Android-bedrijfsportal-app
- Er zijn ook nieuwe schermen toegevoegd om gebruikers door het registratieproces te leiden en meer informatie te bieden over waarom de gebruikers zich moeten registreren en over wat IT-beheerders wel en niet kunnen zien op de ingeschreven apparaten. Zie de [registratie-instructies](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc) voor meer informatie.
- Er worden nu registratiefoutberichten weergegeven in de bedrijfsportal-app. Deze berichten werden eerder weergegeven op de bedrijfsportal-website. Dankzij deze wijziging worden alle foutberichten nu op één plaats weergegeven in plaats van op twee verschillende plaatsen.

#### iOS-bedrijfsportal-app
 - Er zijn ook nieuwe schermen toegevoegd om gebruikers door het registratieproces te leiden en meer informatie te bieden over waarom de gebruikers zich moeten registreren en over wat IT-beheerders wel en niet kunnen zien op de ingeschreven apparaten. Zie de [registratie-instructies](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device) voor meer informatie.

 - Er worden nu registratiefoutberichten weergegeven in de bedrijfsportal-app. Deze berichten werden eerder weergegeven op de bedrijfsportal-website. Dankzij deze wijziging worden alle foutberichten nu op één plaats weergegeven in plaats van op twee verschillende plaatsen.


## Januari 2016

### Profiteren van Windows 10-functies
* **Voorwaardelijke toegang met de Health Attestation-service** Intune-beheerders kunnen nu de status van Windows 10 Apparaatstatusverklaring bekijken in de Intune-beheerconsole. Met Health Attestation van apparaten kan de beheerder zorgen dat clientcomputers over betrouwbare configuraties van BIOS, TPM en opstartsoftware beschikken. De functie voor apparaatstatusverklaring wordt alleen ondersteund op clientapparaten waarop Windows 10 wordt uitgevoerd en TPM 2 is ingeschakeld. Met Health Attestation van apparaten wordt het aantal apparaten weergegeven dat is ingeschakeld voor elk van de volgende:
    * Vroegtijdig starten van anti-malware
    * BitLocker
    * Beveiligd opstarten
    * Code-integriteit

    Lees [Inleiding in nalevingsbeleid voor apparaten voor Microsoft Intune](/intune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) voor meer informatie over de apparaatstatusinstelling, verzamelde gegevenspunten en het statusverklaringsrapport. In [HAS-servicedetails](https://msdn.microsoft.com/en-us/library/dn934876.aspx) wordt de service gedetailleerd besproken.

* **Windows 10 Passport for Work-beleid en certificaatbeheer** Intune biedt de mogelijkheid van [integratie met Microsoft Passport for Work](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune). Dit is een alternatieve aanmeldingsmethode voor Windows 10 waarbij Active Directory of een Azure Active Directory-account wordt gebruikt ter vervanging van een wachtwoord, smartcard of virtuele smartcard. Met Passport kan de gebruiker zich aanmelden met een gebaar in plaats van met een wachtwoord. Een gebaar van de gebruiker kan een eenvoudige pincode zijn, biometrische verificatie zoals Windows Hello of een extern apparaat zoals een vingerafdruklezer.

* **VPN voor specifieke apps**U kunt de apps selecteren die automatisch verbinding maken met uw bedrijfsnetwerk via VPN. Maak de lijst met apps wanneer u het VPN-profiel instelt, zoals wordt beschreven in Gebruikers helpen om verbinding met hun werk te maken met behulp van VPN-profielen met Microsoft Intune.

* **Windows 10-ondersteuning voor Volledig wissen** U kunt nu de opdracht Volledig wissen op afstand activeren voor Windows 10-bureaubladapparaten die zijn ingeschreven bij Intune via de Intune-beheerconsole. Bij Volledig wissen in Windows 10 worden de fabrieksinstellingen van het apparaat hersteld.


### Apple-VPP (Volume Purchase Program) bijwerken
Intune kan u nu helpen bij het [beheer van apps die u hebt aangeschaft via Apple-VPP (Volume Purchase Program) voor bedrijven](/intune/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune). Dit omvat het synchroniseren van licentiegegevens tussen Apple en Intune, en het bijhouden hoeveel exemplaren van elke app u hebt geïmplementeerd.

### IMEI-nummers gebruiken om apparaten in bedrijfseigendom te identificeren
U kunt nu [IMEI-nummers (International Mobile Equipment Identity) importeren](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers) voor mobiele-apparaatplatforms met een IMEI-nummer om mobiele apparaten in bedrijfseigendom te identificeren. Wanneer apparaten met geïmporteerde IMEI-nummers zijn ingeschreven in Intune, worden deze gelabeld als bedrijfseigendom, zodat op die apparaten andere beleidsregels kunnen worden toegepast dan op persoonlijke apparaten.

### Er zijn nu meer apps compatibel met Intune MAM-beleid
Aanvullende apps van Microsoft-partners zijn nu compatibel met Intune Mobile Application Management-beleid (MAM) (voor apparaten die worden beheerd door Intune):
* Box for EMM (van Box Inc) - alleen iOS
* Adobe Reader (van Adobe) - alleen Android
* Foxit PDF Reader (van Foxit Corporation) - iOS en Android


### IE9-ondersteuning eindigt in januari
Vanaf februari 2016 wordt Internet Explorer 9 niet meer ondersteund als officiële browser voor toegang tot de website van de Microsoft Intune-bedrijfsportal, de Intune-accountportal en de Intune-beheerconsole. U moet dan migreren naar Internet Explorer 10 of hoger.


>[!div class="step-by-step"]

>[&larr; **Wat is er nieuw in Intune?**](whats-new-in-microsoft-intune.md)    



<!--HONumber=Oct16_HO1-->


