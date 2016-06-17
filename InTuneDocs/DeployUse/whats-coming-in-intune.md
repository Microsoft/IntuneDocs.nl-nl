---
# required metadata

title: Binnenkort | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 05/17/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Binnenkort in Microsoft Intune
Deze informatie wordt in zeer beperkte mate onder geheimhoudingsverklaring verstrekt en kan worden gewijzigd. Sommige functies die hier worden vermeld, zullen mogelijk niet beschikbaar zijn op de sluitingsdatum en worden mogelijk beschikbaar gesteld in een latere release. Andere functies worden getest in een proefversie, zodat we zeker weten dat ze in gebruik kunnen worden genomen. Neem bij vragen contact op met uw contactpersoon voor Intune/projectmanagement.

Deze pagina wordt regelmatig bijgewerkt. Kom daarom om de tijd terug om te zien of er nieuws is over wat er binnenkort beschikbaar is.

De volgende wijzigingen worden momenteel ontwikkeld voor Intune. Al deze functies worden ook ondersteund voor implementaties voor hybride klanten (Configuration Manager met Intune). Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

## Intune-communicatie
- **Statusgegevens voor de Intune-service.** voor Intune zijn verplaatst naar een centrale locatie met andere Microsoft-services. U vindt deze informatie nu in de [Office 365-beheerportal](https://portal.office.com/Admin/Default.aspx) onder Servicestatus. Lees [dit blogbericht](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/) voor meer informatie.

- **Onboarding van de gebruikersinterface van Berichtencentrum.** Als onderdeel van de migratie van Intune in de [Office 365-beheerportal](https://portal.office.com/) benutten we het bijbehorende Berichtencentrum om nieuwe functies en andere meldingen te communiceren. U kunt ook de bijbehorende mobiele app voor Office 365-beheer installeren om meldingen te ontvangen op uw mobiele telefoon en eenvoudig berichten naar gebruikers of een distributiealias te sturen.
We gebruiken het Berichtencentrum voor onze release in mei om u te laten weten wanneer er updates voltooid zijn. Ook brengen we u op de hoogte van nieuwe en verbeterde Intune-functies. Bekijk het Berichtencentrum meteen door u aan te melden bij de [Office 365-beheerportal](https://portal.office.com/) en de optie **Berichtencentrum** te kiezen in het navigatiepaneel aan de linkerkant.

## Appbeheer
- **Nieuwe beschikbare apps voor beheer met MAM-beleid.** De Microsoft Word-, Excel- en PowerPoint-apps voor Android kunnen nu worden gekoppeld aan MAM-beleid op apparaten die niet zijn geregistreerd bij Intune. Ga voor de volledige lijst met ondersteunde apps naar de galerie met mobiele toepassingen van Microsoft Intune op de pagina [Microsoft Intune-toepassingen van partners](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).


- **Voorwaardelijke toegang voor de browser.** U kunt een beleid voor voorwaardelijke toegang instellen voor Exchange Online en SharePoint Online, zodat deze alleen toegankelijk zijn voor beheerde en compatibele iOS- en Android-apparaten. Eindgebruikers die proberen zich met iOS- en Android-apparaten aan te melden bij Outlook Web Access (OWA) en SharePoint-sites, wordt gevraagd hun apparaat in te schrijven bij Intune en eventuele problemen met de compatibiliteit op te lossen. Hierna kan de aanmelding worden voltooid.
<!---TFS 1175844--->

- **MAM SDK: ondersteuning voor configuratie van de lengte van de pincode.** Net als bij pincodes voor apparaten het geval is, kunt u ook voor MAM-apps de lengte van de pincode opgeven. Hiervoor moeten eindgebruikers voldoen aan de nieuwe beperkingen die u instelt. Ze zien dan een enigszins gewijzigd pincodescherm, waarin de langere code kan worden ingevoerd.
<!--- TFS 1104753--->

- **Skype voor Bedrijven voor Android.** Intune-beheerders kunnen nu Skype voor Bedrijven gebruiken met MAM zonder registratiebeleid.  Zodra de gebruikers zich hebben aangemeld, wordt het MAM-beleid toegepast.
<!--- TFS item 1248444 --->

- **Skype voor Bedrijven voor iOS.** Intune-beheerders kunnen nu Skype voor Bedrijven gebruiken met MAM zonder registratiebeleid.  Zodra de gebruikers zich hebben aangemeld, wordt het MAM-beleid toegepast.
<!--- TFS item 1248443 --->

### Xamarin-ondersteuning
De Microsoft Intune App SDK ondersteunt nu Xamarin-apps in deze scenario's:

- Het schrijven van nieuwe apps of het wijzigen van de code van bestaande line-of-business-apps met de Intune-SDK. U kunt de invoegtoepassing downloaden via de pagina [Microsoft Intune Github](https://github.com/msintuneappsdk).
- Het toevoegen van MAM-ondersteuning aan bestaande line-of-business-apps met de Intune App Wrapping Tool

Zie [Bepalen hoe u apps met Microsoft Intune voorbereidt op Mobile Application Management met Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune) voor meer informatie om te bepalen welke methode u wilt gebruiken.
<!--- TFS 1061478 & TFS 1152340--->


## Apparaatbeheer
- **Externe hulpsessies voor Windows-pc's.** Met de integratie van TeamViewer voor pc's die worden beheerd door Windows-bureaubladagents, kunt u ter ondersteuning van helpdeskafdelingen voor eindgebruikers externe hulpsessies tot stand brengen met pc's die worden beheerd door Windows-bureaubladagents. Dit is van toepassing op Windows 7, 8, 8.1 en 10.
<!--- TFS 1284856--->



## Bedrijfsportal

- **Pop-upmeldingen voor eindgebruikers.** Eindgebruikers krijgen nu pop-upmeldingen uit de Android-bedrijfsportal te zien wanneer ze hun apparaten registreren bij of verwijderen uit de bedrijfsportal.
- **De banner voor apparaatidentificatie biedt eindgebruikers meer informatie.** Eindgebruikers kunnen het apparaat dat ze hebben geselecteerd, gemakkelijk identificeren bij gebruik van de site van de bedrijfsportal. Als er een verkeerd apparaat is geselecteerd, kunnen ze het juiste apparaat selecteren door op de koppeling Tik hier in de banner op de startpagina te tikken.
<!--- TFS 1231157--->

- **Wijzigingen in de accounts van managers voor apparaatregistratie in de Android-bedrijfsportal-app.** Ter verbetering van de prestaties en schaalbaarheid worden er in het deelvenster **Mijn apparaten** van de Android-bedrijfsportal-app niet meer alle DEM-apparaten (Device Enrollment Managers; managers voor apparaatregistratie) weergegeven. Alleen het lokale apparaat waarop de app wordt uitgevoerd, wordt weergegeven en alleen als het apparaat is geregistreerd via de bedrijfsportal-app. De DEM-gebruiker kan acties op het lokale apparaat uitvoeren, maar extern beheer van andere geregistreerde apparaten kan alleen worden uitgevoerd vanuit de Intune-beheerconsole.

- **Wijzigingen in de accounts van managers voor apparaatregistratie in de iOS-bedrijfsportal-app.** Ter verbetering van de prestaties en schaalbaarheid worden er in het deelvenster Mijn apparaten van de iOS-bedrijfsportal-app niet meer alle DEM-apparaten (Device Enrollment Managers; managers voor apparaatregistratie) door Intune weergegeven. Alleen het lokale apparaat waarop de app wordt uitgevoerd, wordt weergegeven en wel alleen als het apparaat is geregistreerd via de bedrijfsportal-app. De DEM-gebruiker kan acties op het lokale apparaat uitvoeren, maar extern beheer van andere geregistreerde apparaten kan alleen worden uitgevoerd vanuit de Intune-beheerconsole.  Daarnaast is het gebruik in Intune van DEM-accounts met het Apple Device Enrollment Program of het hulpprogramma Apple Configurator beëindigd. Deze twee registratiemethoden bieden al ondersteuning voor gebruikersloze registratie voor gedeelde iOS-apparaten.  Gebruik alleen DEM-accounts wanneer gebruikersloze registratie voor gedeelde apparaten niet beschikbaar is.



## Serviceafschaffing
**Meldingsregels voor aangepaste groepen wordt verwijderd.**
Met de Intune-meldingsregels wordt gedefinieerd wie een e-mailwaarschuwing ontvangt Intune. Op dit moment kunt u meldingsregels configureren om e-mails te verzenden naar alle gebruikers van apparaten in een Intune-apparaatgroep die u hebt gemaakt. Vanaf 1 juni 2016 wordt de targeting van groepen die zijn gemaakt door gebruikers, niet meer ondersteund.

Als u nu een meldingsregel wilt targeten op een groep die u in de Microsoft Intune-beheerconsole hebt gemaakt, voert u de volgende stappen uit:

Klik in de werkruimte **Beheerder** op **Meldingsregels** > **Nieuwe regel maken**.

In stap 2 van de wizard Meldingsregel maken selecteert u de apparaatgroepen waarop de regel betrekking heeft. De stap voor het selecteren van apparaatgroepen wordt uit de Intune-console verwijderd.

De voorlopige tijdlijn voor deze wijziging is als volgt:
- In juni 2016 krijgen nieuwe tenants stap 2 van de wizard Meldingsregel maken niet meer te zien. Voor de huidige tenants blijft de situatie ongewijzigd.
- Rond augustus 2016 krijgen enkele bestaande tenants de wizardoptie voor het selecteren van apparaatgroepen niet meer te zien.
- Naar verwachting krijgt rond oktober 2016 geen enkele bestaande tenant de wizardoptie voor het selecteren van apparaatgroepen nog te zien.

<!---   TFS 1278864--->
**Wijzigingen in de ondersteuning voor de iOS-bedrijfsportal-app.**
In de komende maanden zal de Microsoft Intune-bedrijfsportal-app voor iOS worden bijgewerkt en biedt deze alleen nog ondersteuning voor apparaten met iOS 8.0 of later. Gebruikers kunnen geen nieuwe apparaten met een versie lager dan iOS 8.0 registreren. Geregistreerde apparaten met een versie lager dan iOS 8.0 worden gewoon nog beheerd en kunnen, voor een beperkte periode, gebruik blijven maken van de bedrijfsportal-app. Apparaten moeten echter over iOS 8.0 of later beschikken voor toegang tot de nieuwste versie van de bedrijfsportal-app. U kunt gebruikers het beste adviseren bij te werken naar iOS 8.0 of later om optimaal gebruik te kunnen maken van de nieuwe Intune-functies.  

- **Intune-viewer-apps.** Met het uitbrengen van de nieuwe RMS-app voor delen, worden volgende Intune-viewer-apps vanaf augustus 2016 verwijderd:
    - Intune AV-viewer
    - Intune PDF-viewer
    - Intune-afbeeldingsviewer voor Android van Google Play

  In plaats van de viewer-apps van Intune kunt u beter de nieuwe Rights Management-app (RMS sharing) voor Android gebruiken, zodat u één app in plaats van drie afzonderlijke apps kunt implementeren om veilig bedrijfsbestanden op Android-apparaten te bekijken. Meer informatie over de app RMS sharing (met een koppeling naar de documentatie).






### Zie ook
Zie [Wat is er nieuw in Microsoft Intune?](whats-new-in-microsoft-intune.md) voor meer informatie over recente ontwikkelingen.


<!--HONumber=May16_HO5-->


