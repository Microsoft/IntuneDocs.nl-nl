---
title: Vroege editie
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ab6c808fc860491ddece5751983071d40864c8dd
ms.sourcegitcommit: 8f68cd3112a71d1cd386da6ecdae3cb014d570f2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/06/2018
ms.locfileid: "39575080"
---
# <a name="the-early-edition-for-microsoft-intune---august-2018"></a>De vroege editie voor Microsoft Intune - augustus 2018

> [!Note]
> Melding geheimhoudingsverklaring: de volgende wijzigingen worden momenteel ontwikkeld voor Intune. Deze informatie wordt in heel beperkte mate verstrekt onder de geheimhoudingsverklaring. Plaats deze informatie niet op sociale media of openbare websites als Twitter, UserVoice, Reddit, enzovoort. 

De **vroege editie** bevat een lijst met functies, gedeeld onder geheimhoudingsverklaring, die worden toegevoegd aan toekomstige releases van Microsoft Intune. Deze informatie wordt in beperkte mate verstrekt en kan worden gewijzigd. Stuur over deze informatie geen tweets, plaats hier niets over op UserVoice en deel hier op geen enkele andere wijze iets over buiten uw bedrijf. Sommige functies die hier worden vermeld, zullen mogelijk niet beschikbaar zijn op de sluitingsdatum en worden mogelijk beschikbaar gesteld in een latere release. Andere functies worden getest in een proefversie, zodat we zeker weten dat ze in gebruik kunnen worden genomen. Als u vragen of opmerkingen hebt, kunt contact opnemen met uw contactpersoon voor de Microsoft-productgroep.

Deze pagina wordt regelmatig bijgewerkt. Controleer op andere updates.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune in Azure Portal

<!-- 1808 start -->

### <a name="windows-hello-will-target-users-and-devices----1106609---"></a>Windows Hello is gericht op gebruikers en apparaten <!-- 1106609 -->
Wanneer u een beleid voor [Windows Hello voor Bedrijven](windows-hello.md) maakt, geldt dit voor alle gebruikers binnen de organisatie (tenant-breed). Met deze update kan het beleid ook worden toegepast op specifieke gebruikers of specifieke apparaten met behulp van een beleid voor apparaatconfiguratie (**Apparaatconfiguratie** > **Profielen**  >  **Profiel maken** > **Identiteitsbescherming** > **Windows Hello voor Bedrijven**).

In Intune in de Azure-portal zijn de Windows Hello-configuratie en -instellingen zowel onder **Apparaatinschrijving** als onder **Apparaatconfiguratie** beschikbaar. **Apparaatinschrijving** is gericht op de hele organisatie (tenant-breed) en biedt ondersteuning voor Windows AutoPilot (OOBE). **Apparaatconfiguratie** is gericht op apparaten en gebruikers met behulp van een beleid dat wordt toegepast tijdens het inchecken.

Van toepassing op:  
- Windows 10 en hoger
- Windows Holographic for Business

### <a name="control-s-mode-on-windows-10-and-later-devices---public-preview----1958649---"></a>S-modus beheren op apparaten met Windows 10 en hoger - openbare preview <!-- 1958649 -->
U kunt een apparaatconfiguratieprofiel maken dat een Windows 10-apparaat uit de S-modus haalt of voorkomt dat gebruikers het apparaat uit de S-modus halen. Dit onderdeel wordt beschikbaar gesteld in Intune > **Apparaatconfiguratie** > **Profielen** >  **Windows 10 en hoger** > **Editie-upgrade en modus schakelen**.
De pagina [Maak kennis met Windows 10 in S-⁠modus](https://www.microsoft.com/windows/s-mode) biedt meer informatie over de S-modus.
Van toepassing op: Windows 10 en hoger (versie 1809 en hoger)

### <a name="modern-vpn-support-updates-for-ios----2459928-1819876-and-2650856---"></a>Moderne VPN-ondersteuningsupdates voor iOS <!-- 2459928, 1819876, and 2650856 -->
Een toekomstige update biedt ondersteuning voor de volgende iOS VPN-clients: 
- F5 Access (versie 3.0.1 en hoger)
- Citrix SSO
- Palo Alto Networks GlobalProtect (versie 5.0 en hoger) Ook beschikbaar in een toekomstige update:
- Bestaande verbindingstypen voor **F5 Access** worden gewijzigd in **F5 Access Legacy** (conform de bijgewerkte F5-huisstijl)
- Bestaande verbindingstypen voor **Palo Alto Networks GlobalProtect** worden gewijzigd in **Legacy Palo Alto Networks GlobalProtect** (conform de bijgewerkte Palo Alto-huisstijl). 

Bestaande profielen met de volgende verbindingstypen blijven werken met de oude VPN-client. Als u in iOS gebruikmaakt van F5 Access Legacy, Citrix VPN of Legacy Palo Alto Networks GlobalProtect, moet u overstappen op de nieuwe apps. Doe dit zo spoedig mogelijk, om ervoor te zorgen dat VPN-toegang beschikbaar blijft voor iOS-apparaten die worden bijgewerkt naar iOS 12.

### <a name="lock-the-company-portal-in-single-app-mode-until-user-sign-in---1067692---"></a>De bedrijfsportal in de modus voor enkele toepassing vergrendelen tot een gebruiker zich aanmeldt <!--1067692 --> 
U hebt de optie om de bedrijfsportal uit te voeren in de modus voor enkele toepassing als u een gebruiker verifieert via de bedrijfsportal, in plaats van via de configuratieassistent, tijdens de DEP-registratie. Met deze optie wordt het apparaat onmiddellijk vergrendeld nadat de configuratieassistent is voltooid, zodat een gebruiker zich moet aanmelden om toegang te krijgen tot het apparaat. Dit proces zorgt ervoor dat de onboarding voor het apparaat wordt voltooid en het niet in een staat zonder gekoppelde gebruiker blijft.

### <a name="scope-tags-for-policies---1081974-eeready--"></a>Bereiktags voor beleid <!--1081974 eeready-->

Binnenkort kunt u bereiktags gebruiken om de toegang tot Intune-resources te beperken. Voeg een bereiktag toe aan een roltoewijzing en voeg de bereiktag vervolgens toe aan een configuratieprofiel. De rol heeft dan alleen toegang tot resources met configuratieprofielen met overeenkomende bereiktags (of zonder bereiktag).
Selecteer voor het maken van een bereiktag **Intune-rollen** > **Bereik (tags)** > **Maken**.
Als u een bereiktag wilt toevoegen aan een roltoewijzing, selecteert u **Intune-rollen** > **Alle rollen** > **Beleid- en profielbeheerder** > **Toewijzingen** > **Bereik (tags)**.
Als u een bereiktag wilt toevoegen aan een configuratieprofiel, selecteert u **Apparaatconfiguratie** > **Profielen** > Een profiel kiezen > **Eigenschappen** > **Bereik (tags)**.

### <a name="assign-a-user-and-friendly-name-to-an-autopilot-device---1346521---"></a>Een gebruiker en een beschrijvende naam toewijzen aan een AutoPilot-apparaat <!--1346521 -->
In een toekomstige openbare preview-versie kunnen beheerders een gebruiker toewijzen aan een enkel AutoPilot-apparaat.  Beheerders kunnen dan ook beschrijvende namen opgeven die aan gebruikers worden getoond wanneer deze hun apparaat instellen met AutoPilot.

Van toepassing op: Windows Insider 1809 of hoger (tijdens de preview).

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Apple VPP-token die wordt gebruikt door een andere MDM <!-- 1488946 -->
Intune kan detecteren of een token van het volumeaankoopprogramma van Apple (VPP) wordt gebruikt door zowel Intune als een andere MDM en vervolgens meer informatie weergeven.

### <a name="packet-tunnel-support-for-ios-per-app-vpn-profiles-for-custom-and-pulse-secure-connection-types----1520957---"></a>Ondersteuning voor pakkettunnels voor VPN-profielen in iOS op basis van individuele apps voor aangepaste verbindingstypen en Pulse Secure-verbindingstypen <!-- 1520957 -->
Wanneer u in iOS VPN-profielen voor individuele apps gebruikt, kunt u hiermee tunnels op app-niveau (app-proxy) of op pakketniveau (pakkettunnel) gebruiken. Deze opties komt beschikbaar voor de volgende verbindingstypen:
- Aangepaste VPN
- Pulse Secure Als u niet zeker weet welke waarde u moet gebruiken, raadpleegt u de documentatie van uw VPN-provider.
Van toepassing op: iOS

### <a name="zscaler-is-an-available-connection-for-vpn-profiles-on-ios----1769858-eeready---"></a>Zscaler is een beschikbare verbinding voor VPN-profielen voor iOS <!-- 1769858 eeready -->
Wanneer u een VPN-apparaatconfiguratieprofiel in iOS maakt (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** platform > **VPN** profieltype), zijn er verschillende verbindingstypen beschikbaar, waaronder Cisco, Citrix en meer. Een toekomstige update voegt Zscaler toe als verbindingstype. 
De pagina [VPN-instellingen voor apparaten met iOS](vpn-settings-ios.md) biedt een lijst met beschikbare verbindingstypen.

### <a name="block-windows-personal-device-enrollments----1849498---"></a>Persoonlijke apparaatinschrijvingen in Windows blokkeren <!-- 1849498 -->
U kunt hiermee voorkomen dat persoonlijke Windows-apparaten in Intune worden geregistreerd met behulp van [beheer van mobiele apparaten](windows-enroll.md) (Mobile Device Management, MDM). Apparaten die zijn geregistreerd bij de [Intune PC-agent](manage-windows-pcs-with-microsoft-intune.md), kunnen niet met deze functie worden geblokkeerd.
Selecteer voor deze functie **Apparaatinschrijving** > **Apparaatbeperkingen**.
Het inschakelen van deze beperking heeft geen invloed op apparaten die al zijn geregistreerd.
Nadat de beperking is ingeschakeld, wordt door Intune gecontroleerd of elke nieuwe Windows-inschrijvingsaanvraag wordt geautoriseerd als een zakelijke inschrijving. De volgende methoden worden gezien als een zakelijke inschrijving:
- De ingeschreven gebruiker maakt gebruik van [een apparaatinschrijvingsmanageraccount]( device-enrollment-manager-enroll.md).

- Het apparaat is geregistreerd via [Windows AutoPilot](enrollment-autopilot.md).
- Het IMEI-nummer van het apparaat wordt vermeld onder **Apparaatinschrijving** > **[Zakelijke apparaat-id's]( corporate-identifiers-add.md)**).
- Het apparaat is geregistreerd via een [pakket voor bulkinrichting](windows-bulk-enroll.md).
- Het apparaat is geregistreerd via [automatische inschrijving met behulp van SCCM voor co-beheer](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview#how-to-configure-co-management).
Niet-geautoriseerde inschrijvingen worden geblokkeerd.
De volgende inschrijvingen worden door Intune wel als zakelijk gemarkeerd, maar toch geblokkeerd omdat ze de Intune-beheerder geen beheer op apparaatniveau bieden:
- [Automatische MDM-inschrijving](windows-enroll.md#enable-windows-10-automatic-enrollment) met [Azure Active Directory-koppeling tijdens het instellen van Windows](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-frx.md).
- [Automatische MDM-inschrijving](windows-enroll.md#enable-windows-10-automatic-enrollment) met [Azure Active Directory-koppeling vanaf het instellen van Windows](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-frx.md).
Ook de volgende persoonlijke registratiemethoden worden geblokkeerd:
- [Automatische MDM-inschrijving](windows-enroll.md#enable-windows-10-automatic-enrollment) via [Werkaccount toevoegen vanuit de Windows-instellingen](https://docs.microsoft.com/azure/active-directory/user-help/device-management-azuread-registered-devices-windows10-setup).

- De optie [Alleen inschrijven voor MDM]( https://docs.microsoft.com/windows/client-management/mdm/mdm-enrollment-of-windows-devices#connecting-personally-owned-devices-bring-your-own-device) in de Windows-instellingen.

### <a name="specify-machine-name-patterns-in-an-autopilot-profile---1849855--"></a>Computernaampatronen opgeven in een AutoPilot-profiel <!--1849855-->
U kunt hiermee een computernaamsjabloon instellen om tijdens inschrijving via AutoPilot [computernamen](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) te genereren en in te stellen. U moet dit opgeven in het AutoPilot-profiel, te vinden onder **Apparaatinschrijving** > **Windows-inschrijving** > **Windows Autopilot Deployment-service** > **Profielen**. U kunt alleen alfanumerieke tekens en afbreekstreepjes gebruiken.
Van toepassing op: Windows Insider 1809 of hoger (tijdens de preview).

### <a name="ios-version-number-and-build-number-are-shown----1892471---"></a>iOS-versienummer en -buildnummer weergegeven <!-- 1892471 -->
Onder **Apparaatnaleving** > **Apparaatnaleving** wordt de versie van het iOS-besturingssysteem weergegeven. In een toekomstige update wordt ook het buildnummer weergegeven.
Wanneer er beveiligingsupdates worden uitgebracht, laat Apple doorgaans het versienummer ongewijzigd, maar wordt het buildnummer wel bijgewerkt. Door het buildnummer weer te geven, kunt u eenvoudig controleren of een beveiligingsupdate is geïnstalleerd.

### <a name="for-windows-autopilot-profiles-hide-the-change-account-options-on-the-company-sign-in-page-and-domain-error-page---1901669---"></a>De optie Account wijzigen verbergen op de aanmeldingspagina van uw bedrijf en de foutpagina van uw domein voor Windows AutoPilot-profielen <!--1901669 -->
In een openbare preview komen nieuwe opties voor Windows AutoPilot-profielen beschikbaar, waarmee beheerders de opties voor het wijzigen van een account op de aanmeldingspagina en domeinfoutpagina's van een bedrijf kunnen verbergen. Als u deze opties wilt verbergen, moet er een aangepaste huisstijl zijn geconfigureerd in Azure Active Directory. Van toepassing op: Windows Insider 1809 of hoger (tijdens de preview).

### <a name="delay-when-ios-software-updates-are-shown-on-the-device----1949583---"></a>Vertragen wanneer software-updates voor iOS worden weergegeven op het apparaat <!-- 1949583 -->
In Intune > **Software-updates** > **Beleid voor bijwerken van iOS** kunt u dagen en tijden instellen waarop apparaten geen updates mogen installeren. In een toekomstige update krijgt u de mogelijkheid uit te stellen (met een periode van 1 tot 90 dagen) wanneer een software-update wordt weergegeven op het apparaat. 
De huidige instellingen worden weergegeven op de pagina [iOS-updatebeleid configureren in Microsoft Intune](software-updates-ios.md)

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Buiten gebruik gestelde apparaten in het dashboard voor apparaatnaleving <!-- 1981119 -->
In een toekomstige update worden buiten gebruik gestelde apparaten verwijderd uit het dashboard voor apparaatnaleving. Dit zorgt voor veranderingen in de aantallen in uw nalevingsrapporten.

### <a name="new-user-experience-update-for-the-company-portal-website---2000968---"></a>Nieuwe update van de gebruikerservaring voor de bedrijfsportalwebsite <!--2000968 -->
Op basis van feedback van klanten voegen we nieuwe functies toe aan de website van de bedrijfsportal. U zult een aanzienlijke verbetering ervaren wat betreft de bestaande functionaliteit en bruikbaarheid van uw Android-, iOS- en Windows-apparaten. Delen van de site, zoals apparaatdetails, feedback en ondersteuning, en apparaatoverzicht, krijgen een nieuw, modern, responsief ontwerp. U ziet ook:
- Gestroomlijnde werkstromen voor alle apparaatplatforms
- Verbeterde apparaat-id en inschrijvingsstromen
- Nuttigere foutberichten
- Toegankelijker taal, minder technische jargon
- Mogelijkheid om directe koppelingen naar apps te delen
- Verbeterde prestaties voor grote app-catalogi
- Beter toegankelijk voor alle gebruikers

### <a name="office-365-proplus-version----2213968-eeready---"></a>Office 365 ProPlus-versie <!-- 2213968 eeready -->
Binnenkort kunt u de Office-versie selecteren wanneer u met Intune Office 365 ProPlus-apps toewijst op Windows 10-apparaten. Selecteer in de Azure-portal **Microsoft Intune** > **Apps** > **Apps toevoegen**. Selecteer daarna **Office 365 ProPlus Suite (Windows 10)** in de vervolgkeuzelijst **Soort**. Selecteer **App Suite-instellingen** om de bijbehorende blade weer te geven. Stel **Kanaal bijwerken** in op een waarde, zoals **Maandelijks**. Verwijder eventueel andere versies van Office (msi) van eindgebruikersapparaten door **Ja** te selecteren. Selecteer **Specifiek** om voor het geselecteerde kanaal een specifieke versie van Office te installeren op apparaten van eindgebruikers. U kunt hier ook opgeven welke **Specifieke versie** van Office u wilt gebruiken. Welke versies er beschikbaar zijn, verandert in de loop van de tijd. Daarom is het mogelijk dat er bij het maken van een nieuwe implementatie nieuwere versies beschikbaar zijn en dat bepaalde oudere versies niet meer beschikbaar zijn. Huidige implementaties blijven de oudere versie implementeren, maar de versielijst wordt voortdurend per kanaal bijgewerkt. Zie [Overzicht van updatekanalen voor Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus) voor meer informatie.

### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470---"></a>Profiel configureren om bepaalde vensters over te slaan tijdens het doorlopen van de configuratieassistent <!-- 2276470 -->
Wanneer u een macOS-registratieprofiel maakt, kunt u binnenkort instellen dat de configuratieassistent de volgende schermen overslaat:
- Migratie vanaf Android
- Weergavekleur
- Privacy
- iCloudStorage

### <a name="change-in-the-update-process-for-on-premises-connectors----2277554---"></a>Wijziging in het updateproces voor on-premises connectors <!-- 2277554 -->
Op basis van feedback van klanten passen we de manier aan waarop on-premises connectors worden bijgewerkt. Nadat u een on-premises connector hebt geïnstalleerd, worden updates automatisch uitgevoerd. Deze wijziging begint met de nieuwe PFX-certificaatconnector voor Microsoft Intune en wordt vervolgens voor andere soorten on-premises connectors doorgevoerd. 

### <a name="support-for-register-dns-setting-for-windows-10-vpn----2282852---"></a>Ondersteuning voor het registreren van DNS-instellingen voor Windows 10-VPN <!-- 2282852 -->
Het wordt binnenkort mogelijk om VPN-profielen voor Windows 10 zo te configureren dat deze de IP-adressen die door de interne DNS aan de VPN-interface worden toegewezen, automatisch registreren, zonder dat u hiervoor aangepaste profielen hoeft te gebruiken.
De pagina [Windows 10 VPN-instellingen](vpn-settings-windows-10.md) biedt een lijst met de instellingen die nu beschikbaar zijn voor VPN-profielen. 

### <a name="restricts-apps-and-block-access-to-company-resources-on-ios-and-android-for-work-devices----2451462---"></a>Apps beperken en de toegang tot bedrijfsbronnen blokkeren op iOS- en Android for Work-apparaten <!-- 2451462 -->
Er komt onder **Apparaatnaleving** > **Beleid** > **Beleid maken** > **Android for Work**  >  **Systeembeveiliging** een nieuwe instelling: **Beperkte toepassingen**. Deze nieuwe instelling maakt gebruik van een nalevingsbeleid om toegang tot bedrijfsbronnen te blokkeren als bepaalde apps op het apparaat zijn geïnstalleerd. Het apparaat wordt beschouwd als niet conform beleid totdat de beperkte apps van het apparaat worden verwijderd.
Van toepassing op: 
- iOS

### <a name="export-azure-classic-portal-compliance-policies-to-csv-file----2469637---"></a>Nalevingsbeleid van de klassieke Azure-portal exporteren naar een CSV-bestand <!-- 2469637 -->
Nalevingsbeleid gemaakt in de klassieke Azure-portal wordt afgeschaft.  Wanneer dit gebeurt, kunt u alle bestaande beleidsregels bekijken en verwijderen. U kunt ze echter niet meer bijwerken. U kunt het beleid exporteren als een door komma's gescheiden bestand (CSV-bestand). Vervolgens kunt u de details in het bestand gebruiken om het beleid opnieuw te maken via Intune in de Azure-portal.
> [!IMPORTANT]
> Wanneer de klassieke Azure-portal buiten gebruik wordt gesteld, hebt u geen toegang meer tot uw beleid en kunt u uw beleid niet meer inzien. Zorg er dus voor dat u uw beleidsregels exporteert en opnieuw maakt in de Azure-portal, voordat de klassieke Azure-portal buiten gebruik wordt gesteld.

<!-- 1807 start -->

### <a name="more-sync-opportunities-in-the-company-portal-app-for-windows----2683177---"></a>Meer synchronisatiemogelijkheden in de Bedrijfsportal-app voor Windows <!-- 2683177 -->
De Bedrijfsportal-app voor Windows voegt een optie voor apparaatsynchronisatie toe aan de Windows-taakbalk en het startmenu. Klik vanuit een van de locaties om uw apparaten snel te synchroniseren en toegang te krijgen tot bedrijfsresources.  

### <a name="reset-device-passcodes-from-company-portal-app-for-windows-10----2101282---"></a>Apparaattoegangscode opnieuw instellen vanuit de bedrijfsportal-app voor Windows 10 <!-- 2101282 --> 
Uw werknemers kunnen binnenkort hun pincodes of toegangscode van hun apparaat rechtstreeks vanuit de bedrijfsportal-app voor Windows 10 opnieuw instellen. Deze functionaliteit wordt beschikbaar op zowel extern als lokaal door Intune beheerde apparaten die ondersteuning bieden voor het opnieuw instellen van toegangscodes. Afhankelijk van het type apparaat wordt bij een aanvraag die is ingediend voor een extern apparaat de huidige toegangscode verwijderd of wordt een tijdelijke toegangscode gemaakt. Gebruikers die verzoeken om een reset voor een lokaal apparaat worden doorgestuurd naar de Instellingen-app van het apparaat.  

### <a name="new-browsing-experiences-in-the-company-portal-app-for-windows----2317227---"></a>Nieuwe bladerervaringen in de Bedrijfsportal-app voor Windows <!-- 2317227 -->  
Wanneer u bladert of apps zoekt in de Bedrijfsportal-app voor Windows, kunt u schakelen tussen de bestaande weergave **Tegels** en de recent toegevoegde weergave **Details**. De nieuwe weergave bevat informatie over toepassingen, zoals de naam, de uitgever, de publicatiedatum en de installatiestatus.  

Op de pagina **Apps** staat de weergave **Geïnstalleerd**. Hier ziet u meer informatie over app-installaties die zijn voltooid en die nog bezig zijn. Wilt u feedback of ideeën over de nieuwe wijzigingen doorgeven? Stuur uw feedback op via de Bedrijfsportal-app.

### <a name="improved-company-portal-app-experience-for-device-enrollment-manager-users----675800---"></a>Verbeterde Bedrijfsportal-app-ervaring voor gebruikers van de apparaatinschrijvingsmanager <!-- 675800 -->
Wanneer een apparaatinschrijvingsmanager (DEM) zich aanmeldt bij de Bedrijfsportal-app voor Windows, wordt in de app alleen het huidige DEM-apparaat weergegeven dat wordt uitgevoerd. Dankzij deze verbetering treden er minder time-outs op. Deze time-outs traden voorheen op wanneer de app probeerde alle apparaten met DEM-registratie te laden.  

### <a name="use-vpp-device-licenses-to-pre-provision-the-company-portal-during-dep-enrollment----1608345---"></a>VPP-apparaatlicenties gebruiken om de bedrijfsportal vooraf in te richten tijdens DEP-registratie <!-- 1608345 -->
U kunt Volume Purchase Program-apparaatlicenties (VPP) gebruiken om de bedrijfsportal vooraf in te richten tijdens de Device Enrollment Program-registraties (DEP). Om dit te doen, geeft u, wanneer u een registratieprofiel maakt of bewerkt, het VPP-token op dat u wilt gebruiken om de bedrijfsportal te installeren. Controleer of uw token niet verloopt en of u voldoende licenties heeft voor de bedrijfsportal-app. Wanneer het token verloopt of onvoldoende licenties heeft, pusht Intune in plaats daarvan de App Store-bedrijfsportal (deze vraagt om een Apple ID).

###  <a name="windows-line-of-business-lob-apps-file-extensions----1884873---"></a>Bestandsextensies van Windows LOB-apps (line-of-business) <!-- 1884873 -->
De beschikbare bestandsextensies voor Windows LOB-apps omvatten nu ook *.msi*, *.appx*, *.appxbundle*, *.msix* en *.msixbundle*. U kunt in Microsoft Intune apps toevoegen via **Mobiele apps** > **Apps** > **Toevoegen**. Het deelvenster **App toevoegen** wordt weergegeven. Hier kunt u het **app-type** selecteren. Selecteer voor Windows LOB-apps **Line-Of-Business-app** als het app-type, selecteer het **app-pakketbestand** en voeg vervolgens een iOS-installatiebestand toe met de juiste extensie.

### <a name="windows-defender-atp-configuration-package-automatically-added-to-configuration-profile----2144658---"></a>Windows Defender ATP configuratiepakket automatisch toegevoegd aan configuratieprofiel <!-- 2144658 -->
Wanneer u [Advanced Threat Protection en onboarding](advanced-threat-protection.md#onboard-devices-using-a-configuration-profile)-apparaten gebruikt in Intune, downloadt u nu een configuratiepakket en voegt u dit toe aan uw configuratieprofiel. In een toekomstige update haalt Intune het pakket automatisch op uit het Windows Defender-beveiligingscentrum en voegt het toe aan uw profiel.

Van toepassing op Windows 10 en hoger.

### <a name="check-for-sccm-compliance----2192052---"></a>SCCM-naleving controleren <!-- 2192052 -->
Een toekomstige update bevat een nieuwe nalevingsinstelling van System Center Configuration Manager (SCCM) (**Apparaatcompatibiliteit** > **Beleid** > **Beleid maken**  >  **Windows 10**). SCCM verzendt signalen naar Intune-nalevingsbeleid. Met de Intune-instelling kunt u vereisen dat alle SCCM-signalen 'conform' retourneren.

U kunt bijvoorbeeld vereisen dat alle software-updates worden geïnstalleerd op apparaten. Deze vereiste heeft in SCCM de status 'Geïnstalleerd'. Als programma's op het apparaat zich in onbekende staat bevinden, is het apparaat niet-compatibel in Intune.

Van toepassing op Windows 10 en hoger

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Meldingen voor verlopend VPP-token of onvoldoende bedrijfsportal-licenties <!-- 2237572 -->
Als u het Volume Purchase Program (VPP) gebruikt om de bedrijfsportal vooraf in te richten tijdens DEP-inschrijving, waarschuwt Intune u wanneer het VPP-token bijna verloopt en wanneer er bijna te weinig licenties zijn voor de bedrijfsportal.

### <a name="confirmation-required-to-delete-vpp-token-that-is-being-used-for-company-portal-pre-provisioning----2237634---"></a>Bevestiging vereist om het VPP-token te verwijderen dat wordt gebruikt voor het vooraf inrichten van de bedrijfsportal <!-- 2237634 -->
Er is een bevestiging vereist om een Volume Purchase Program-token (VPP) te verwijderen als dit wordt gebruikt voor het vooraf inrichten van de bedrijfsportal tijdens de DEP-inschrijving.

#### <a name="additional-security-settings-for-windows-installer----2282430---"></a>Aanvullende beveiligingsinstellingen voor Windows Installer <!-- 2282430 -->
U kunt gebruikers toestemming geven om app-installaties te beheren. Als u deze functie is ingeschakeld, kunnen installaties worden toegestaan die anders worden gestopt vanwege een beveiligingsfout. U kunt het Windows-installatieprogramma de opdracht geven om verhoogde bevoegdheden te gebruiken wanneer een programma op een systeem wordt geïnstalleerd. Verder kunt u ingeschakelde items van Windows-gegevensbescherming laten indexeren en de metagegevens voor de items laten opslaan op een niet-versleutelde locatie. Als het beleid is uitgeschakeld, worden de items met WIP-beveiliging niet geïndexeerd en worden ze niet weergegeven in de resultaten in Cortana of Verkenner. De functionaliteit voor deze opties is standaard uitgeschakeld. 

<!-- 1806 start -->

### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Toetsenborden van derden kunnen worden geblokkeerd door APP-instellingen op iOS <!-- 1248481 -->
Op iOS-apparaten kunnen Intune-beheerders het gebruik blokkeren van toetsenborden van derden bij het benaderen van organisatiegegevens in door beleid beveiligde apps. Wanneer het Application Protection Policy (APP; appbeveiligingsbeleid) is ingesteld om toetsenborden van derden te blokkeren, ontvangt de gebruiker een bericht als hij de eerste keer met bedrijfsgegevens werkt met een toetsenbord van derden. Alle opties, behalve het systeemeigen toetsenbord, worden geblokkeerd en zijn niet zichtbaar voor apparaatgebruikers. Apparaatgebruikers zien het dialoogvenster slechts één keer. 

### <a name="require-non-biometric-passcode-on-app-launch-and-timeout----1506985---"></a>Niet-biometrische wachtwoordcode vereisen bij het starten en een time-out van een app <!-- 1506985 -->

Door een niet-biometrische wachtwoordcode te vereisen bij het starten van een app en na een door de beheerder opgegeven time-out, biedt Intune betere beveiliging voor apps die geschikt zijn voor Mobile Application Management (MAM) door het gebruik van biometrische identificatie voor toegang tot zakelijke gegevens te beperken. De instellingen hebben invloed op gebruikers die Touch ID (iOS), Face ID (iOS), Android Biometric of andere toekomstige biometrische verificatiemethoden gebruiken om toegang te krijgen tot voor APP/MAM geschikte toepassingen. Door deze instellingen hebben Intune-beheerders gedetailleerdere controle over gebruikerstoegang. Op deze manier wordt de kans kleiner dat een onjuiste gebruiker bedrijfsgegevens kan zien op een apparaat met meerdere vingerafdrukken of andere biometrische toegangsmethoden. Open **Microsoft Intune** in de Azure-Portal. Selecteer **Mobiele apps** > **App-beveiligingsbeleid** > **Een beleid toevoegen** > **Instellingen**. Ga voor specifieke instellingen naar de sectie **Toegang**.

### <a name="office-365-pro-plus-language-packs----1833450---"></a>Office 365 Pro Plus-taalpakketten <!-- 1833450 -->
Als Intune-beheerder kunt extra talen implementeren voor Office 365 Pro Plus-apps die via Intune worden beheerd. De lijst met beschikbare talen bevat het taalpakket **Type** (kern, gedeeltelijk en spellingcontrole). Selecteer in de Azure-portal **Microsoft Intune** > **Mobiele apps** > **Apps** > **Toevoegen**. In de lijst **App-type** op de blade **App toevoegen** selecteert u **Windows 10** onder **Office 365-suite**. Selecteer **Talen** in de blade **Instellingen voor app-suite**.

### <a name="preview-a-new-user-experience-update-for-the-company-portal-website---2000968---"></a>Bekijk de nieuwe update van de gebruikerservaring voor de bedrijfsportalwebsite <!--2000968 -->
Op basis van feedback van klanten voegen we nieuwe functies toe aan de website van de bedrijfsportal/iOS-app-catalogus. U zult een aanzienlijke verbetering ervaren wat betreft de bestaande functionaliteit en bruikbaarheid van uw Android-, iOS- en Windows-apparaten. Delen van de site, zoals apparaatdetails, feedback en ondersteuning, en apparaatoverzicht, krijgen een nieuw, modern, responsief ontwerp. U ziet ook:

- Gestroomlijnde werkstromen voor alle apparaatplatforms
- Verbeterde apparaat-id en inschrijvingsstromen
- Nuttigere foutberichten
- Toegankelijker taal, minder technische jargon
- Mogelijkheid om directe koppelingen naar apps te delen
- Verbeterde prestaties voor grote app-catalogi
- Beter toegankelijk voor alle gebruikers

De update is momenteel beschikbaar als preview-versie. U kunt zich aanmelden voor de preview-versie op http://aka.ms/webcpflighting

<!-- 1805 start -->

### <a name="require-non-biometric-passcode-on-cold-app-launch-and-timeout----1506985---"></a>Niet-biometrische wachtwoordcode vereisen bij het koud starten en een time-out van een app <!-- 1506985 --> 

Door een niet-biometrische wachtwoordcode te vereisen bij het koud starten van een app en na een door de beheerder opgegeven time-out, biedt Intune betere beveiliging voor apps die geschikt zijn voor Mobile Application Management (MAM) door het gebruik van biometrische identificatie voor toegang tot zakelijke gegevens te beperken. De instellingen hebben invloed op gebruikers die Touch ID (iOS), Face ID (iOS), Android Biometric of andere toekomstige biometrische verificatiemethoden gebruiken om toegang te krijgen tot voor APP/MAM geschikte toepassingen. Door deze instellingen hebben Intune-beheerders gedetailleerdere controle over gebruikerstoegang. Op deze manier wordt de kans kleiner dat een onjuiste gebruiker bedrijfsgegevens kan zien op een apparaat met meerdere vingerafdrukken of andere biometrische toegangsmethoden. Open **Microsoft Intune** in de Azure-Portal. Selecteer **Mobiele apps** > **App-beveiligingsbeleid** > **Een beleid toevoegen** > **Instellingen**. Ga voor specifieke instellingen naar de sectie **Toegang**.

<!-- 1803 start -->

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Mogelijkheid om vereiste line-of-business-apps (LOB) te implementeren voor alle gebruikers op apparaten met Windows 10 Desktop <!-- 1627835 RS4 -->
Klanten kunnen vereiste Windows 10 line-of-business-apps implementeren om in apparaatcontexten te installeren. Hierdoor worden deze apps beschikbaar voor alle gebruikers op het apparaat. Dit is alleen van toepassing op Windows 10 Desktop-apparaten.

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>De Help- en Feedback-ervaring op de bedrijfsportal-app voor Android bijwerken <!--1631531 -->

De Help- en Feedback-ervaring op de bedrijfsportal-app voor Android wordt bijgewerkt, zodat deze overeenkomt met de aanbevolen procedures voor Android-apps. De bedrijfsportal-app voor Android wordt in de komende maanden ook bijgewerkt om het menu-item **Help en Feedback** op te delen in afzonderlijke menu-items, namelijk **Help** en **Feedback verzenden**. Op de **Help**-pagina komt een sectie **Veelgestelde vragen** sectie en een knop **E-mailondersteuning** waarmee eindgebruikers logboeken naar Microsoft kunnen uploaden en e-mail kunnen verzenden naar bedrijfsondersteuning om het probleem te beschrijven. **Feedback verzenden** leidt de gebruiker door een standaard Microsoft-feedbackformulier, waarin de gebruiker wordt gevraagd een keuze te maken uit: "Ik vindt iets leuk", "Ik vind iets niet leuk" of "Ik heb een idee."

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Beleid voor app-beveiliging <!-- 679615 -->
Via het beveiligingsbeleid voor Intune-apps kunt u algemene standaardbeleidsregels maken om snel beveiliging in te schakelen voor alle gebruikers in de gehele tenant.

<!-- the following are present prior to 1711 -->

## <a name="notices"></a>Mededelingen

Er zijn geen actieve meldingen op dit moment.

### <a name="see-also"></a>Zie ook
Zie [Wat is er nieuw in Microsoft Intune?](whats-new.md) voor meer informatie over recente ontwikkelingen.



