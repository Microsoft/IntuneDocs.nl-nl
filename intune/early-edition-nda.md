---
title: Vroege editie | Microsoft Intune
titlesuffix: ''
description: Vroege editie van Microsoft Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/04/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: d50925d9f5422e1bfea01869233c63d6a2889109
ms.sourcegitcommit: 12f8b7f0bca1baa2c1f68dd6af4f16a4814daa11
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/05/2019
ms.locfileid: "55737499"
---
# <a name="the-early-edition-for-microsoft-intune---january-2019"></a>De vroege editie voor Microsoft Intune - januari 2019

> [!Note]
> NDA-melding: De volgende wijzigingen worden momenteel ontwikkeld voor Intune. Deze informatie wordt in heel beperkte mate verstrekt onder de geheimhoudingsverklaring. Plaats deze informatie niet op sociale media of openbare websites als Twitter, UserVoice, Reddit, enzovoort. 

De **vroege editie** bevat een lijst met functies, gedeeld onder geheimhoudingsverklaring, die worden toegevoegd aan toekomstige releases van Microsoft Intune. Deze informatie wordt in beperkte mate verstrekt en kan worden gewijzigd. Stuur over deze informatie geen tweets, plaats hier niets over op UserVoice en deel hier op geen enkele andere wijze iets over buiten uw bedrijf. Sommige functies die hier worden vermeld, zullen mogelijk niet beschikbaar zijn op de sluitingsdatum en worden mogelijk beschikbaar gesteld in een latere release. Andere functies worden getest in een proefversie, zodat we zeker weten dat ze in gebruik kunnen worden genomen. Als u vragen of opmerkingen hebt, kunt contact opnemen met uw contactpersoon voor de Microsoft-productgroep.

Deze pagina wordt regelmatig bijgewerkt. Controleer op andere updates.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune in Azure Portal
<!-- 1902 start-->

### <a name="powershell-scripts-can-run-in-a-64-bit-host-on-64-bit-devices----1862675----"></a>PowerShell-scripts kunnen worden uitgevoerd in een 64-bits host op 64-bits apparaten <!-- 1862675  -->
Wanneer u een PowerShell-script aan een apparaatconfiguratieprofiel toevoegt, wordt het script altijd uitgevoerd in 32 bits, zelfs op 64-bits besturingssystemen. Met deze update kan een beheerder het script uitvoeren in een 64-bits PowerShell-host op 64-bits apparaten (**Apparaatconfiguratie** > **PowerShell-scripts** > **Toevoegen** > **Configureren** > **Script uitvoeren in 64-bits PowerShell-host**).
Zie [PowerShell-scripts in Intune](intune-management-extension.md) voor meer details over het gebruik van PowerShell.
Van toepassing op: Windows 10 en hoger

### <a name="rename-an-enrolled-windows-device----1911112----"></a>De naam van een geregistreerd Windows-apparaat wijzigen <!-- 1911112  -->
U kunt de naam van geregistreerde Windows 10-apparaten (RS4 of later) wijzigen. Kies hiervoor **Intune** > **Apparaten** > **Alle apparaten** > kies een apparaat > **Naam van apparaat wijzigen**.

### <a name="assign-scep-certificates-to-a-userless-macos-device-------2340521-----"></a>SCEP-certificaten aan een macOS-apparaat zonder gebruikers toewijzen <!-- 2340521   -->
U kunt SCEP-certificaten (Simple Certificate Enrollment Protocol) aan een macOS-apparaat zonder gebruikers toewijzen en het certificaat aan Wi-Fi- of VPN-profielen koppelen. Dit is een uitbreiding van de bestaande ondersteuning voor het [toewijzen van certificaten aan apparaten zonder gebruikers die worden uitgevoerd op Windows, iOS en Android](certificates-scep-configure.md#create-a-scep-certificate-profile).

### <a name="intune-conditional-access-ui-update------2432313----"></a>Update voor gebruikersinterface voor voorwaardelijke toegang tot Intune <!-- 2432313  -->
We voeren verbeteringen door in de gebruikersinterface voor voorwaardelijke toegang in de Intune-console. Deze omvatten:
- Vervanging van de Intune-blade *Voorwaardelijke toegang* door de blade van Azure Active Directory. Hiermee hebt u toegang tot het volledige bereik instellingen en configuraties voor voorwaardelijke toegang die een Azure AD-technologie blijven.
- Verplaatsing van de instelling voor de *Exchange-serviceconnector* naar wat momenteel de blade *On-premises toegang* is. Tevens wordt de naam van die blade veranderd in *Exchange-toegang*. Door deze wijziging worden de locaties gecombineerd waar u details met betrekking tot Exchange online en on-premises configureert en bewaakt.

### <a name="intune-will-leverage-google-play-protect-apis-on-android-devices----2577355----"></a>Intune gebruikt de Google Play Protect-API’s op Android-apparaten <!-- 2577355  -->
Sommige IT-beheerders hebben te maken met een BYOD-landschap waar eindgebruikers mogelijk rooting of jailbreaking van hun mobiele telefoon veroorzaken. Dit gedrag leidt, in sommige gevallen onbewust, tot omzeiling van vele Intune-beleidsregels die zijn ingesteld om gegevens van de organisatie op de apparaten van eindgebruikers te beveiligen. Intune biedt daarom root- en jailbreakdetectie voor zowel geregistreerde als niet-geregistreerde apparaten. Met deze release zal Intune Google Play Protect-API’s aan onze bestaande rootdetectiecontroles toevoegen voor niet-geregistreerde apparaten. Hoewel Google niet alle rootdetectiecontroles die plaatsvinden deelt, verwachten we wel dat met deze API’s gebruikers worden gedetecteerd die hun apparaten om wat voor reden dan ook hebben geroot, variërend van apparaataanpassing tot de mogelijkheid nieuwere besturingssysteemupdates te krijgen op oudere apparaten. Toegang van deze gebruikers tot bedrijfsgegevens kan vervolgens worden geblokkeerd, of hun zakelijke accounts kunnen worden gewist uit via beleid ingeschakelde apps. Als extra waarde heeft de IT-beheerder nu verschillende rapportupdates op de blade Intune-app-beveiliging. Het rapport Gemarkeerde gebruikers toont welke gebruikers via de SafetyNet API-scan van Google Play Protect zijn gedetecteerd. Het rapport Mogelijk schadelijke apps toont aan welke apps zijn gedetecteerd via de scan die met de Verify Apps-API van Google is uitgevoerd. Deze functie is beschikbaar voor Android. 

### <a name="win32-app-information-available-in-troubleshooting-blade----2617342------"></a>Informatie over Win32-apps, beschikbaar in de blade Probleemoplossing <!-- 2617342    -->
U kunt logboekbestanden over fouten bij een Win32-app-installatie verzamelen via de blade **Probleemoplossing** in de Intune-app. Zie [Problemen met de installatie oplossen](troubleshoot-app-install.md) voor meer informatie over de installatie van Probleemoplossing.

### <a name="kiosk-browser-and-microsoft-edge-browser-apps-can-run-on-windows-10-devices-in-kiosk-mode----2935135----"></a>Kiosk Browser- en Microsoft Edge Browser-apps kunnen worden uitgevoerd op Windows 10-apparaten in de kioskmodus <!-- 2935135  -->
In de kioskmodus kunnen één of ook meerdere apps op Windows 10-apparaten worden uitgevoerd. Deze update omvat verschillende wijzigingen in het gebruik van browserapps in de kioskmodus, waaronder:

- Voeg de Microsoft Edge Browser of Kiosk Browser toe om deze als apps uit te voeren op het kioskapparaat (**Apparaatconfiguratie** > **Profielen** > **Nieuw profiel** > **Windows 10 en later** voor platform > **Kiosk** voor profieltype).
- Beperk Microsoft Edge zodat dit wel (of niet) in de kioskmodus kan worden uitgevoerd (**Apparaatconfiguratie** > **Profielen** > **Nieuw profiel** > **Windows 10 en later** voor platform > **Apparaatbeperkingen** voor profieltype > **Microsoft Edge Browser**). Wanneer Microsoft Edge niet in de kioskmodus wordt uitgevoerd, kunnen de instellingen worden gewijzigd door eindgebruikers.

Ga voor een lijst met de huidige instellingen naar:

- [Instellingen voor apparaten met Windows 10 en hoger om ze als kiosk uit te voeren](kiosk-settings-windows.md)
- [Microsoft Edge Browser-apparaatbeperkingen](device-restrictions-windows-10.md#microsoft-edge-browser)

Van toepassing op: Windows 10 en hoger

### <a name="auto-assign-scope-tags-to-resources-created-by-an-admin-with-that-scope----3173823----"></a>Bereiktags automatisch toewijzen aan resources die door een beheerder met dat bereik zijn gemaakt <!-- 3173823  -->
Wanneer een beheerder een resource maakt, worden alle bereiktags die aan de beheerder zijn toegewezen automatisch toegewezen aan die nieuwe resources.

### <a name="new-device-restriction-settings-for-ios-and-macos-devices----3448774---"></a>Nieuwe apparaatbeperkingsinstellingen voor iOS- en macOS-apparaten <!-- 3448774 -->
U kunt een aantal instellingen en functies beperken op apparaten waarop iOS en macOS worden uitgevoerd (**Apparaatconfiguratie** > **Profielen** > **Nieuw profiel** > **iOS** of **macOS** voor platform > **Apparaatbeperkingen** voor profieltype). Met deze update worden meer functies en instellingen toegevoegd die u kunt beheren, waaronder het instellen van Schermtijd, het wijzigen van eSIM-instellingen en mobiele abonnementen, het vertragen van de zichtbaarheid van software-updates voor gebruikers, het blokkeren van cacheopslag van inhoud en meer.
Als u de huidige functies en instellingen die u kunt beperken, wilt zien, raadpleegt u:
- [Beperkingsinstellingen voor iOS-apparaten](device-restrictions-ios.md)
- [Beperkingsinstellingen voor macOS-apparaten](device-restrictions-macos.md)

Van toepassing op:
- iOS
- macOS

### <a name="failed-enrollment-report-moves-to-the-device-enrollment-blade----3560202---"></a>Mislukte verplaatsing van registratierapporten naar de blade Apparaatregistratie <!-- 3560202 -->
Het rapport **Mislukte registraties** wordt verplaatst naar het gedeelte **Bewaking** van de blade **Apparaatregistratie**. Twee nieuwe kolommen (Registratiemethode en besturingssysteemversie) worden ook toegevoegd.

### <a name="change-kiosk-to-dedicated-devices----3598402----"></a>Kiosk wijzigen in Toegewezen apparaten <!-- 3598402  -->
Voor de afstemming met Android-terminologie wordt **Kiosk** gewijzigd in **Toegewezen apparaten** onder Apparaatconfiguratieprofielen, **Android enterprise** > **Apparaateigenaar** > **Apparaatbeperkingen**.

### <a name="safari-and-delaying-user-software-update-visibility-ios-settings-are-moving-in-the-intune-ui----3640850--3803313----"></a>iOS-instellingen voor de zichtbaarheid van Safari-software-updates en het vertragen van die zichtbaarheid voor gebruikers worden verplaatst in de Intune-gebruikersinterface <!-- 3640850, , 3803313  -->
Voor iOS-apparaten kunt u Safari-instellingen instellen en software-updates configureren. In deze update worden deze instellingen naar verschillende delen van de Intune-gebruikersinterface verplaatst:

- De Safari-instellingen worden verplaatst van **Safari** (**Apparaatconfiguratie** > **Profielen** > **Nieuw profiel** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype) naar **Ingebouwde apps**. 
- De instelling **Zichtbaarheid van software-updates voor gebruikers voor iOS-apparaten onder toezicht vertragen** (**Software-updates** > **Updatebeleid voor iOS**) wordt verplaatst naar **Apparaatbeperkingen** > **Algemeen**.

Voor een lijst met de huidige instellingen raadpleegt u [iOS-apparaatbeperkingen](device-restrictions-ios.md) en [iOS-software-updates](software-updates-ios.md).

Van toepassing op: 
- iOS

### <a name="enabling-restrictions-in-the-device-settings-is-renamed-to-screen-time-on-ios-devices----3699164----"></a>De naam Beperkingen inschakelen bij de apparaatinstellingen wordt gewijzigd in Schermtijd op iOS-apparaten <!-- 3699164  -->
U kunt **Beperkingen inschakelen bij de apparaatinstellingen** op iOS-apparaten onder toezicht configureren (**Apparaatconfiguratie** > **Profielen** > **Nieuw profiel** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype > **Algemeen**). In deze update wordt de naam van deze instelling gewijzigd in **Schermtijd (alleen onder toezicht)**. Het gedrag blijft hetzelfde. Specifiek: 

- iOS 11.4.1 en eerder: **Blokkeren** voorkomt dat eindgebruikers hun eigen beperkingen kunnen instellen bij de apparaatinstellingen. 
- iOS 12.0 en hoger: **Blokkeren** voorkomt dat eindgebruikers hun eigen **Schermtijd** kunnen instellen bij de apparaatinstellingen, waaronder inhouds- en privacybeperkingen. Op apparaten die naar iOS 12.0 zijn geüpgraded is het tabblad Beperkingen niet meer zichtbaar bij de apparaatinstellingen. Deze instellingen vindt u onder **Schermtijd**. 

Zie [Beperkingen voor iOS-apparaten](device-restrictions-ios.md) voor een lijst met de huidige instellingen.

Van toepassing op: 
- iOS

### <a name="app-status-details-for-ios-apps----3761235----"></a>Meer informatie over de appstatus voor iOS-apps <!-- 3761235  -->
Er zijn nieuwe meldingen voor installatiefouten van apps beschikbaar met betrekking tot het volgende:
- Fout tijdens het installeren van VPP-apps op een gedeelde iPad
- Fout tijdens uitschakelen van App Store
- Fout tijdens het zoeken van een VPP-licentie voor de app
- Fout tijdens het installeren van systeemapps met MDM-provider
- Fout tijdens het installeren van apps wanneer apparaat zich in de verloren-modus of kioskmodus bevindt
- Fout tijdens het installeren van apps wanneer gebruiker niet bij de App Store is aangemeld

In Intune selecteert u **Client-apps** > **Apps** > naam van de app > **Apparaatinstallatiestatus**. Nieuwe foutmeldingen zijn beschikbaar in de kolom **Statusdetails**.

<!-- 1901 start -->

### <a name="deployment-of-online-licensed-microsoft-store-for-business-apps----1672660----"></a>Implementatie van online gelicentieerde Microsoft Store voor Bedrijven-apps <!-- 1672660  -->
U kunt vereiste online gelicentieerde Microsoft Store voor Bedrijven-apps in de apparaatcontext toewijzen. Wanneer u op deze manier een Microsoft Store voor bedrijven-app implementeert, kan de app worden geïnstalleerd voor alle gebruikers op het apparaat. Dit is alleen van toepassing op Windows 10 RS4+ Desktop-apparaten. De optie om de app in de apparaatcontext te installeren, is beschikbaar op de toewijzingspagina voor client-apps voor gelicentieerde MSFB Online-apps.

<!-- 1812 start -->

### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Android Enterprise APP WE-app-implementatie <!-- 1171203 -->
Voor Android-apparaten in een niet-geregistreerd App Protection Policy Without Enrollment-implementatiescenario (APP-WE), gebruikt u de beheerde Google Play Store om store-apps en LOB-apps te implementeren bij gebruikers. In het bijzonder kan de IT-afdeling eindgebruikers voorzien van een app-catalogus en een installatie waarbij het niet langer nodig is dat eindgebruikers de beveiligingsstatus van hun apparaten versoepelen door installaties uit onbekende bronnen toe te staan. Bovendien biedt dit implementatiescenario een verbeterde eindgebruikerservaring.

### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359---"></a>Intune-beleid werkt de verificatiemethode en installatie van de Bedrijfsportal-app bij <!-- 1927359 -->
Intune biedt geen ondersteuning meer voor de Bedrijfsportal wanneer deze handmatig door eindgebruikers uit de appstore wordt geïnstalleerd op apparaten die al met behulp van Configuratieassistent zijn ingeschreven via een van de Apple-registratiemethoden voor bedrijfsapparaten. Deze wijziging is alleen relevant wanneer u tijdens de inschrijving verifieert met Apple Setup Assistant. Deze wijziging is eveneens alleen van invloed op iOS-apparaten die zijn ingeschreven via:  
* Apple Configurator
* Apple Business Manager
* Apple School Manager
* Apple Device Enrollment Program (DEP)

Als gebruikers de Bedrijfsportal-app installeren uit de App Store en vervolgens apparaten via de app proberen te registreren, treedt er een foutmelding op. Er wordt van uitgegaan dat deze apparaten de Bedrijfsportal alleen gebruiken wanneer het automatisch door Intune tijdens de registratie is gepusht. Inschrijvingsprofielen in Intune in de Azure-portal worden bijgewerkt zodat u kunt opgeven hoe apparaten zich verifiëren en hoe zij de Bedrijfsportal-app ontvangen. Als u wilt dat uw DEP-apparaatgebruikers de Bedrijfsportal hebben, moet u uw voorkeuren in een inschrijvingsprofiel opgeven. Bovendien wordt binnenkort het scherm **Uw apparaat identificeren** in de Bedrijfsportal-app niet meer gebruikt.  
Als u de Bedrijfsportal wilt installeren op DEP-apparaten die al zijn ingeschreven, gaat u naar Intune > Client-apps en pusht u de app als beheerde app met app-configuratiebeleid. Details over hoe u deze stappen uitvoert, worden beschreven in toekomstige documentatie.

### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Beheersjablonen zijn in openbare preview en verplaatst naar hun eigen configuratieprofiel <!-- 3322847 -->
Beheersjablonen in Intune (**Apparaatconfiguratie** > **Beheersjablonen**) zijn momenteel in openbare preview. Bij deze update: Beheersjablonen omvatten circa 300 instellingen die kunnen worden beheerd in Intune. Eerder bestonden deze instellingen alleen in de editor voor groepsbeleid.
Beheersjablonen zijn beschikbaar in openbare preview en worden verplaatst van **Apparaatconfiguratie** > **Beheersjablonen** naar **Apparaatconfiguraatie** > **Profielen** >**Profiel maken** > kies als **Platform** **Windows 10 en later** en kies in **Profieltype** **Beheersjablonen**.
Rapportage is ingeschakeld is van toepassing op: Windows 10 en hoger

### <a name="intune-macos-company-portal-dark-mode----3300524---"></a>Donkere modus van Intune macOS Bedrijfsportal <!-- 3300524 -->
De Intune macOS Bedrijfsportal biedt nu ondersteuning voor de donkere modus voor macOS. Wanneer u de donkere modus inschakelt op een macOS 10.14+-apparaat, wordt de vormgeving door de Bedrijfsportal aangepast naar kleuren die overeenkomen met die modus.

<!-- 1809 start -->  

### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>APP-instellingen voor webgegevens <!-- 2662995 -->
De APP-instellingen voor webcontent op zowel Android- als iOS-apparaten worden bijgewerkt om zowel http- als https-webkoppelingen beter te kunnen verwerken, evenals de gegevensoverdracht via iOS Universal- en Android App-koppelingen.  

<!-- 1808 start -->

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Apple VPP-token die wordt gebruikt door een andere MDM <!-- 1488946 -->
Intune kan detecteren of een token van het volumeaankoopprogramma van Apple (VPP) wordt gebruikt door zowel Intune als een andere MDM en vervolgens meer informatie weergeven.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Buiten gebruik gestelde apparaten in het dashboard voor apparaatnaleving <!-- 1981119 -->
In een toekomstige update worden buiten gebruik gestelde apparaten verwijderd uit het dashboard voor apparaatnaleving. Dit zorgt voor veranderingen in de aantallen in uw nalevingsrapporten.

## <a name="notices"></a>Mededelingen

Er zijn geen actieve meldingen op dit moment.

### <a name="see-also"></a>Zie tevens
Zie [Wat is er nieuw in Microsoft Intune?](whats-new.md) voor meer informatie over recente ontwikkelingen.