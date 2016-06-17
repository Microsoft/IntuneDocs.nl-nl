---
# required metadata

experiment_id: lindavr-abtest-20160527
title: Wat is er nieuw? | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Wat is er nieuw in Microsoft Intune?

## Mei 2016


Met uitzondering van de TeamViewer-integratie worden al deze functies ook ondersteund voor hybride implementaties (Configuration Manager met Intune). Zie de pagina met [nieuwe hybridefuncties](https://technet.microsoft.com/en-us/library/mt718155.aspx) (Engelstalig) voor meer informatie over nieuwe hybridefuncties.

### Documentatie

Welkom bij de voorbeeldversie van [docs.microsoft.com](https://docs.microsoft.com/en-us/intune).
Dit is een volledig nieuw, modern inhoudsplatform dat is ontworpen om Intune gebruikersvriendelijker en eenvoudiger te maken.
Zie [Kennismaking met docs.microsoft.com](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/)

### Servicestatus van Intune
Servicestatusgegevens voor Intune is verplaatst naar een centrale locatie met andere Microsoft-services. U vindt deze informatie nu in de [Office 365-beheerportal](https://portal.office.com/Admin/Default.aspx) onder **Servicestatus**.
Lees [dit blogbericht](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/) voor meer informatie.


### Appbeheer

- **MAM SDK: ondersteuning voor configuratie van de lengte van de pincode.** Net als bij pincodes voor apparaten het geval is, kunt u ook voor MAM-apps de lengte van de pincode opgeven. Hiervoor moeten eindgebruikers voldoen aan de nieuwe beperkingen die u instelt. Ze zien dan een enigszins gewijzigd pincodescherm, waarin de langere code kan worden ingevoerd. Zie [MAM-beleidsinstellingen voor Android](/intune/deploy-use/android-mam-policy-settings) en [ MAM-beleidsinstellingen voor iOS](/intune/deploy-use/ios-mam-policy-settings) voor meer informatie.

- **Skype voor Bedrijven voor iOS en Android.** U kunt Skype voor Bedrijven nu gebruiken met [MAM zonder registratiebeleid](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune). Zodra gebruikers zich aanmelden, wordt het MAM-beleid toegepast.

- **Nieuwe beschikbare apps voor beheer met MAM-beleid.** De Microsoft Word-, Excel- en PowerPoint-apps voor Android kunnen nu worden gekoppeld aan MAM-beleid op apparaten die niet zijn geregistreerd bij Intune. Ga voor de volledige lijst met ondersteunde apps naar de galerie met mobiele toepassingen van Microsoft Intune op de pagina [Microsoft Intune-toepassingen van partners](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).

### Apparaatbeheer

- **Externe hulpsessies voor Windows-pc's.** Dankzij de TeamViewer-integratie voor Windows-pc's die worden beheerd met de Intune-clientsoftware kunt u ter ondersteuning van uw helpdeskafdeling sessies voor hulp op afstand met Windows-pc's uitvoeren. Ondersteunde pc's zijn onder meer Windows 7, 8, 8.1 en Windows 10.
Zie [Algemene beheertaken voor Windows-pc’s met de Microsoft Intune-computerclient voor meer informatie](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#respond-to-a-remote-assistance-request).

### Updates voor bedrijfsportal

#### Bedrijfsportal-app voor Android

- **Pop-upmeldingen voor eindgebruikers**: eindgebruikers krijgen nu pop-upmeldingen uit de Android-bedrijfsportal te zien wanneer ze hun apparaten registreren bij of verwijderen uit de bedrijfsportal.

- **Wijzigingen in de accounts van managers voor apparaatregistratie in de Android-bedrijfsportal-app.** Ter verbetering van de prestaties en schaalbaarheid worden er in het deelvenster Mijn apparaten van de Android-bedrijfsportal-app niet meer alle DEM-apparaten (Device Enrollment Managers; managers voor apparaatregistratie) door Intune weergegeven. Alleen het lokale apparaat waarop de app wordt uitgevoerd, wordt weergegeven en wel alleen als het apparaat is geregistreerd via de bedrijfsportal-app. De DEM-gebruiker kan acties op het lokale apparaat uitvoeren, maar extern beheer van andere geregistreerde apparaten kan alleen worden uitgevoerd vanuit de Intune-beheerconsole.
-
#### Bedrijfsportalwebsite

**Bedrijfsportalwebsite: de banner voor apparaatidentificatie biedt eindgebruikers meer informatie.** Eindgebruikers kunnen het apparaat dat ze hebben geselecteerd, nu gemakkelijker identificeren wanneer ze de website van de bedrijfsportal gebruiken. Als er een verkeerd apparaat is geselecteerd, kunnen ze het juiste apparaat selecteren door op de koppeling **Tik hier** in de banner op de startpagina te tikken.


## Binnenkort

- **Onboarding van de gebruikersinterface van Berichtencentrum**. Als onderdeel van de migratie van Intune in de [Office 365-beheerportal](https://portal.office.com/) benutten we het bijbehorende Berichtencentrum om nieuwe functies en andere meldingen te communiceren. U kunt ook de bijbehorende mobiele app voor Office 365-beheer installeren om meldingen te ontvangen op uw mobiele telefoon en eenvoudig berichten naar gebruikers of een distributiealias te sturen.
We gebruiken het Berichtencentrum voor onze release in mei om u te laten weten wanneer er updates voltooid zijn. Ook brengen we u op de hoogte van nieuwe en verbeterde Intune-functies. Bekijk het Berichtencentrum meteen door u aan te melden bij de [Office 365-beheerportal](https://portal.office.com/) en de optie BERICHTENCENTRUM te kiezen in het navigatiepaneel aan de linkerkant.

- **Wijzigingen in de accounts van managers voor apparaatregistratie**. Ter verbetering van de prestaties en schaalbaarheid worden er in het deelvenster **Mijn apparaten** van de iOS-bedrijfsportal-app niet meer **alle** DEM-apparaten (Device Enrollment Managers; managers voor apparaatregistratie) door Intune weergegeven. Alleen het lokale apparaat waarop de app wordt uitgevoerd, wordt weergegeven en wel alleen als het apparaat is geregistreerd via de bedrijfsportal-app. De DEM-gebruiker kan acties op het lokale apparaat uitvoeren, maar extern beheer van andere geregistreerde apparaten kan alleen worden uitgevoerd vanuit de Intune-beheerconsole. Daarnaast is het gebruik in Intune van DEM-accounts met het Apple Device Enrollment Program of het hulpprogramma Apple Configurator beëindigd. Deze twee registratiemethoden bieden al ondersteuning voor gebruikersloze registratie voor gedeelde iOS-apparaten. Gebruik alleen DEM-accounts wanneer gebruikersloze registratie voor gedeelde apparaten niet beschikbaar is.

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

    Klik in de werkruimte **Beheerder** op **Meldingsregels** > **Nieuwe regel maken**.

    In stap 2 van de wizard Meldingsregel maken selecteert u de apparaatgroepen waarop de regel betrekking heeft. De stap voor het selecteren van apparaatgroepen wordt uit de Intune-console verwijderd.

    De voorlopige tijdlijn voor deze wijziging is als volgt:
    - In juni 2016 krijgen nieuwe tenants stap 2 van de wizard Meldingsregel maken niet meer te zien. Voor de huidige tenants blijft de situatie ongewijzigd.
    - Rond augustus 2016 krijgen enkele bestaande tenants de wizardoptie voor het selecteren van apparaatgroepen niet meer te zien.
    - Naar verwachting krijgt rond oktober 2016 geen enkele bestaande tenant de wizardoptie voor het selecteren van apparaatgroepen nog te zien.


- **Wijzigingen in de ondersteuning voor de iOS-bedrijfsportal-app**. In de komende maanden zal de Microsoft Intune-bedrijfsportal-app voor iOS worden bijgewerkt en biedt deze alleen nog ondersteuning voor apparaten met iOS 8.0 of later. Gebruikers kunnen geen nieuwe apparaten met een versie lager dan iOS 8.0 registreren. Geregistreerde apparaten met een versie lager dan iOS 8.0 worden gewoon nog beheerd en kunnen, voor een beperkte periode, gebruik blijven maken van de bedrijfsportal-app. Apparaten moeten echter over iOS 8.0 of later beschikken voor toegang tot de nieuwste versie van de bedrijfsportal-app. U kunt gebruikers het beste adviseren bij te werken naar iOS 8.0 of later om optimaal gebruik te kunnen maken van de nieuwe Intune-functies.



## Vorige versies van Intune
Raadpleeg het artikel over [Vorige versies van Intune](previous-intune-releases.md) als u wilt zien wat er de afgelopen zes maanden voor Intune is uitgekomen.
> [!div class="op_single_selector"]
- [April 2016](previous-intune-releases.md)
- [Maart 2016](previous-intune-releases.md)
- [Februari 2016](previous-intune-releases.md)
- [Januari 2016](previous-intune-releases.md)
- [December 2015](previous-intune-releases.md)
- [November 2015](previous-intune-releases.md)




### Zie ook
* [Microsoft Intune-blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform roadmap](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)


<!--HONumber=Jun16_HO1-->


