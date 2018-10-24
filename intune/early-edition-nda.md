---
title: Vroege editie
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/03/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 72585982cd27962981f581a99f0ea361642df0ee
ms.sourcegitcommit: ba0699cc351954960b222223c60c4ecd50edc829
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49652135"
---
# <a name="the-early-edition-for-microsoft-intune---october-2018"></a>De vroege editie voor Microsoft Intune – oktober 2018

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

<!-- 1810 start -->

### <a name="use-microsoft-recommended-settings-with-security-baselines----2055484---"></a>Door Microsoft aanbevolen instellingen gebruiken met beveiligingsbasislijnen <!-- 2055484 -->
Intune is geïntegreerd met andere services die op beveiliging gericht zijn, inclusief Windows Defender ATP en Office 365 ATP. Klanten vragen om een gemeenschappelijke strategie en een samenhangende set van end-to-end beveiligingsworkflows voor alle Microsoft 365-diensten. Ons doel is om strategieën af te stemmen en oplossingen te ontwikkelen die beveiligingsactiviteiten en gebruikelijke beheerderstaken combineren. In Intune willen we dit doel bereiken door het publiceren van een set beveiligingsbasislijnen die door Microsoft zijn aanbevolen (**Intune** >  **Beveiligingsbasislijnen**).  Beheerders krijgen de mogelijkheid om direct op basis van deze basislijnen een beveiligingsbeleid op te stellen en dit vervolgens voor hun gebruikers te implementeren. Ze kunnen ook de aanbevolen procedures aanpassen aan de behoeften van hun organisatie. Intune zorgt ervoor dat apparaten deze basislijnen blijven naleven, en waarschuwt beheerders wanneer gebruikers of apparaten van de basislijnen afwijken.

### <a name="autopilot-support-for-hybrid-azure-active-directory-joined-devices----1048100---"></a>Autopilot-ondersteuning voor hybride apparaten die zijn toegevoegd aan Azure Active Directory <!-- 1048100 -->
U kunt hybride apparaten die aan Azure Active Directory zijn toegevoegd, instellen met behulp van Autopilot. Apparaten moeten aan het netwerk van uw organisatie zijn toegevoegd om de hybride Autopilot-functie te kunnen gebruiken.

### <a name="scope-tags-for-apps---1081941---"></a>Bereiktags voor apps <!--1081941 -->
Binnenkort kunt u bereiktags gebruiken om de toegang tot Intune-resources te beperken. Voeg een bereiktag toe aan een roltoewijzing en voeg de bereiktag vervolgens toe aan een configuratieprofiel. De rol heeft dan alleen toegang tot resources met configuratieprofielen met overeenkomende bereiktags (of zonder bereiktag).
Selecteer voor het maken van een bereiktag **Intune-rollen** > **Bereik (tags)** > **Maken**.
Als u een bereiktag wilt toevoegen aan een roltoewijzing, selecteert u **Intune-rollen** > **Alle rollen** > **Beleid- en profielbeheerder** > **Toewijzingen** > **Bereik (tags)**.
Als u een bereiktag wilt toevoegen aan een configuratieprofiel, selecteert u **Apparaatconfiguratie** > **Profielen** > Een profiel kiezen > **Eigenschappen** > **Bereik (tags)**.

### <a name="tenant-health-dashboard----1124854---"></a>Dashboard voor tenantstatus<!-- 1124854 -->
De pagina Tenantstatus in Intune biedt een uitputtend overzicht van alle informatie over de status van tenants. De pagina is onderverdeeld in vier secties:  
- **Tenantdetails**: bevat uiteenlopende informatie, zoals uw MDM-instantie, het totale aantal ingeschreven apparaten in uw tenant en uw aantal licenties. Deze sectie bevat ook de huidige servicerelease voor uw tenant.
- **Connectorstatus**: bevat informatie voor geconfigureerde connectoren, zoals Apple VPP, Windows Store for Business en certificaatconnectoren. Op basis van hun huidige status worden de connectoren gemarkeerd als *In orde*,  *Waarschuwing* of *Niet in orde*.
- **Intune servicestatus**: bevat actieve incidenten of storingen voor uw tenant. De informatie in deze sectie wordt rechtstreeks opgehaald uit het Office Message Center ([https://portal.office.com](https://portal.office.com)).
- **Intune nieuws**: bevat actieve berichten voor uw tenant, zoals meldingen dat uw tenant de laatste Intune-functies heeft ontvangen. De informatie in deze sectie wordt rechtstreeks opgehaald uit het Office Message Center ([https://portal.office.com](https://portal.office.com)).

### <a name="enrollment-abandonment-report----1382924---"></a>Rapport over afgebroken inschrijvingen <!-- 1382924 -->
Een nieuw rapport met details over afgebroken inschrijvingen wordt beschikbaar via **Apparaatinschrijving** > **Monitor**.

### <a name="deployed-wip-policies-without-user-enrollment----1434452---"></a>Geïmplementeerd WIP-beleid zonder gebruikersinschrijving <!-- 1434452 -->
WIP-beleid (Windows Information Protection) kan worden ingezet zonder dat MDM-gebruikers hun Windows 10-apparaat hoeven in te schrijven. Met deze configuratie kunnen bedrijven hun bedrijfsdocumenten op basis van de WIP-configuratie beschermen, terwijl gebruikers hun eigen Windows-apparaten kunnen blijven beheren. Zodra documenten met WIP-beleid zijn beveiligd, kunnen de beschermde gegevens selectief worden gewist door een Intune-beheerder. Door een gebruiker en een apparaat te selecteren een en wisaanvraag te versturen, worden alle gegevens onbruikbaar die met het WIP-beleid zijn beschermd. Vanuit Intune in de Azure-portal selecteert u hiervoor **Mobiele app** > **App selectief wissen**.


### <a name="add-custom-brand-image-for-company-portal-app----1916266---"></a>Aangepaste merkafbeelding toevoegen voor bedrijfsportal-app <!-- 1916266 -->
Als Microsoft Intune-beheerder kunt u een aangepaste merkafbeelding uploaden die als achtergrondafbeelding wordt weergegeven op de profielpagina van de gebruiker in de bedrijfsportal-app. Voor meer informatie over het configureren van de bedrijfsportal-app, zie [Handleiding voor configuratie van de Microsoft Intune bedrijfsportal-app](company-portal-app.md).

### <a name="group-windows-autopilot-enrolled-devices-by-correlator-id----2075110---"></a>Voor Windows Autopilot ingeschreven apparaten groeperen op correlator-ID <!-- 2075110 -->
Intune ondersteunt het groeperen van ingeschreven Windows-apparaten op correlator-ID met behulp van [Autopilot voor bestaande apparaten](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) via Configuration Manager. De correlator-ID is een parameter van het Autopilot-configuratiebestand. Intune stelt automatisch de [enrollmentProfileName van het Azure ID-apparaatkenmerk](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#using-attributes-to-create-rules-for-device-objects) in zodat deze aansluit bij de "OfflineAutopilotprofile-\<correlator-ID\>". Hierdoor kunnen willekeurige dynamische groepen in Azure AD op basis van correlator-ID’s worden gecreëerd via het kenmerk enrollmentprofileName voor offline Autopilot-inschrijvingen. 


### <a name="support-for-ios-12-oauth-in-ios-email-profiles---2155106---"></a>Ondersteuning van iOS 12 OAuth in iOS-e-mailprofielen <!--2155106 -->
De iOS-e-mailprofielen van Intune ondersteunen iOS 12 OAuth. Om deze functie te bekijken, kiest u **Intune** > **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **OAuth**. Als deze instelling is ingeschakeld, gebeuren er twee dingen:
1. Apparaten die al als doel zijn ingesteld, krijgen een nieuw profiel.
2. Eindgebruikers worden opnieuw om hun inloggegevens gevraagd.

### <a name="new-required-password-type-default-setting-for-android-android-enterprise---2649963---"></a>Nieuwe standaardwaarde voor ‘Vereist wachtwoordtype’ voor Android, Android Enterprise<!-- 2649963 -->
Wanneer u een nieuw nalevingsbeleid maakt (**Intune** > **Apparaatnaleving** > **Beleid** > **Beleid maken** > **Android** of **Android enterprise** voor platform > Systeembeveiliging), verandert de standaardwaarde voor **Vereist wachtwoordtype**. Huidige standaardwaarde: standaardwaarde apparaat. Nieuwe standaardwaarde: ten minste numeriek. Geldt voor: Android, Android Enterprise

### <a name="assign-autopilot-profiles-to-the-all-devices-virtual-group---2715522---"></a>Autopilot-profielen toewijzen aan de virtuele groep Alle apparaten <!--2715522 -->
U kunt Autopilot-profielen toewijzen aan de virtuele groep Alle apparaten. Kies hiervoor **Inschrijving apparaat** > **Inschrijving Windows** > **Implementatieprofielen** > kies een profiel >  **Toewijzingen** > onder  **Toewijzen aan** kies **Alle apparaten**.

### <a name="new-azure-active-directory-terms-of-use-feature----2870393---"></a>Nieuwe gebruiksvoorwaardenfunctie voor Azure Active Directory <!-- 2870393 -->
Azure Active Directory krijgt een gebruiksvoorwaardenfunctie die u kunt gebruiken in plaats van de bestaande Intune-voorwaarden. De gebruiksvoorwaardenfunctie voor Azure AD biedt meer flexibiliteit als het gaat om welke voorwaarden wanneer worden weergegeven, en biedt betere lokalisatieondersteuning, meer controle over de weergave van voorwaarden en verbeterde rapportage. De gebruiksvoorwaardenfunctie voor Azure AD vereist wel Azure Active Directory Premium P1, dat ook onderdeel is van de Enterprise Mobility + Security E3-suite.


### <a name="intune-will-maintain-the-office-localized-language-when-updating-office-on-end-users-machines----2971030---"></a>Intune behoudt de in Office gelokaliseerde taal bij het bijwerken van Office op machines van eindgebruikers <!-- 2971030 -->
Wanneer Intune Office op de machines van uw eindgebruiker installeert, krijgen eindgebruikers automatisch dezelfde taalpakketten als bij eerdere .MSI Office installaties. 

<!-- 1809 start -->  

### <a name="intune-app-data-transfer-settings-on-ios-mdm-enrolled-devices----2244713---"></a>Instellingen voor Intune APP-gegevensoverdracht op iOS-apparaten die via MDM zijn ingeschreven <!-- 2244713 -->
U kunt het beheer van instellingen voor Intune APP-gegevensoverdracht op iOS-apparaten die zijn ingeschreven via MDM scheiden van het opgeven van de identiteit van de ingeschreven gebruiker. Beheerders die de IntuneMAMUPN niet gebruiken, zullen geen wijziging in het gedrag opmerken. Als deze functionaliteit beschikbaar is, moeten beheerders die de IntuneMAMUPN gebruiken om het gedrag van de gegevensoverdracht op ingeschreven apparaten te beheren de nieuwe instellingen controleren en hun APP-instellingen zo nodig bijwerken.

### <a name="use-a-pre-shared-key-in-a-windows-10-wi-fi-profile----2662938---"></a>Een vooraf gedeelde sleutel gebruiken in een Wi-Fi-profiel voor Windows 10 <!-- 2662938 -->
U kunt een vooraf gedeelde sleutel gebruiken met het persoonlijke WPA/WPA2-beveiligingsprotocol om een Wi-Fi-configuratieprofiel voor Windows 10 te verifiëren.
U moet momenteel een Wi-Fi-profiel importeren of een aangepast profiel maken om een vooraf gedeelde sleutel te gebruiken. In [Wi-Fi-instellingen voor Windows 10](wi-fi-settings-windows.md) worden de huidige instellingen vermeld. 

### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>APP-instellingen voor webgegevens <!-- 2662995 -->
De APP-instellingen voor webcontent op zowel Android- als iOS-apparaten worden bijgewerkt om zowel http- als https-webkoppelingen beter te kunnen verwerken, evenals de gegevensoverdracht via iOS Universal- en Android App-koppelingen.  

### <a name="autopilot-device-sync-frequency-increasing-to-every-12-hours----2753673---"></a>De synchronisatiefrequentie voor Autopilot-apparaten wordt verhoogd naar elke 12 uur <!-- 2753673 -->
Autopilot-apparaten worden elke 12 uur in plaats van elke 24 uur gesynchroniseerd.

### <a name="intune-landing-page-updates-and-node-rename---2867309---"></a>Updates voor de Intune-landingspagina en de naamswijziging van een knooppunt <!--2867309 -->
Updates voor de Intune-landingspagina bevatten nieuwe en gewijzigde tegels en grafieken voor controle voor een betere gegevensvisualisatie. Het knooppunt **Mobiele apps** wordt gewijzigd in **Client-apps**.

### <a name="increased-end-user-access-using-the-company-portal-app----772203---"></a>Verbeterde toegang voor eindgebruikers met de bedrijfsportal-app <!-- 772203 -->
Eindgebruikers hebben via de bedrijfsportal-app toegang tot belangrijke handelingen voor het account, zoals het opnieuw instellen van het wachtwoord en het AAD-profiel.  

<!-- 1808 start -->

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Apple VPP-token die wordt gebruikt door een andere MDM <!-- 1488946 -->
Intune kan detecteren of een token van het volumeaankoopprogramma van Apple (VPP) wordt gebruikt door zowel Intune als een andere MDM en vervolgens meer informatie weergeven.

### <a name="ios-version-number-and-build-number-are-shown----1892471---"></a>iOS-versienummer en -buildnummer weergegeven <!-- 1892471 -->
Onder **Apparaatnaleving** > **Apparaatnaleving** wordt de versie van het iOS-besturingssysteem weergegeven. In een toekomstige update wordt ook het buildnummer weergegeven.
Wanneer er beveiligingsupdates worden uitgebracht, laat Apple doorgaans het versienummer ongewijzigd, maar wordt het buildnummer wel bijgewerkt. Door het buildnummer weer te geven, kunt u eenvoudig controleren of een beveiligingsupdate is geïnstalleerd.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Buiten gebruik gestelde apparaten in het dashboard voor apparaatnaleving <!-- 1981119 -->
In een toekomstige update worden buiten gebruik gestelde apparaten verwijderd uit het dashboard voor apparaatnaleving. Dit zorgt voor veranderingen in de aantallen in uw nalevingsrapporten.


### <a name="change-in-the-update-process-for-on-premises-connectors----2277554---"></a>Wijziging in het updateproces voor on-premises connectors <!-- 2277554 -->
Op basis van feedback van klanten passen we de manier aan waarop on-premises connectors worden bijgewerkt. Nadat u een on-premises connector hebt geïnstalleerd, worden updates automatisch uitgevoerd. Deze wijziging begint met de nieuwe PFX-certificaatconnector voor Microsoft Intune en wordt vervolgens voor andere soorten on-premises connectors doorgevoerd. 

<!-- 1807 start -->

### <a name="improved-company-portal-app-experience-for-device-enrollment-manager-users----675800---"></a>Verbeterde Bedrijfsportal-app-ervaring voor gebruikers van de apparaatinschrijvingsmanager <!-- 675800 -->
Wanneer een apparaatinschrijvingsmanager (DEM) zich aanmeldt bij de Bedrijfsportal-app voor Windows, wordt in de app alleen het huidige DEM-apparaat weergegeven dat wordt uitgevoerd. Dankzij deze verbetering treden er minder time-outs op. Deze time-outs traden voorheen op wanneer de app probeerde alle apparaten met DEM-registratie te laden.  

### <a name="check-for-configuration-manager-compliance----2192052---"></a>Controleren op Configuration Manager-compatibiliteit <!-- 2192052 -->
Een toekomstige update bevat een nieuwe instelling voor System Center Configuration Manager-compatibiliteit (**Apparaatcompatibiliteit** > **Beleid** > **Beleid maken** > **Windows 10**). Configuration Manager verzendt signalen naar Intune-naleving. Met de Intune-instelling kunt u vereisen dat alle Configuration Manager-signalen de waarde 'compatibel' retourneren.

U kunt bijvoorbeeld vereisen dat alle software-updates worden geïnstalleerd op apparaten. Deze vereiste heeft in Configuration Manager de status 'Geïnstalleerd'. Als programma's op het apparaat zich in onbekende staat bevinden, is het apparaat niet-compatibel in Intune.

Van toepassing op Windows 10 en hoger

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Meldingen voor verlopend VPP-token of onvoldoende bedrijfsportal-licenties <!-- 2237572 -->
Als u het Volume Purchase Program (VPP) gebruikt om de bedrijfsportal vooraf in te richten tijdens DEP-inschrijving, waarschuwt Intune u wanneer het VPP-token bijna verloopt en wanneer er bijna te weinig licenties zijn voor de bedrijfsportal.

<!-- 1806 start -->

### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Toetsenborden van derden kunnen worden geblokkeerd door APP-instellingen op iOS <!-- 1248481 -->
Op iOS-apparaten kunnen Intune-beheerders het gebruik blokkeren van toetsenborden van derden bij het benaderen van organisatiegegevens in door beleid beveiligde apps. Wanneer het Application Protection Policy (APP; appbeveiligingsbeleid) is ingesteld om toetsenborden van derden te blokkeren, ontvangt de gebruiker een bericht als hij de eerste keer met bedrijfsgegevens werkt met een toetsenbord van derden. Alle opties, behalve het systeemeigen toetsenbord, worden geblokkeerd en zijn niet zichtbaar voor apparaatgebruikers. Apparaatgebruikers zien het dialoogvenster slechts één keer. 

<!-- 1805 start -->

### <a name="require-non-biometric-after-specified-timeout----1506985---"></a>Een niet-biometrische pincode vereisen na de opgegeven time-out <!-- 1506985 --> 

Door een niet-biometrische pincode te vereisen na een door de beheerder opgegeven time-out, biedt Intune een betere beveiliging voor apps die geschikt zijn voor Mobile Application Management (MAM) door het gebruik van biometrische identificatie voor toegang tot zakelijke gegevens te beperken. De instellingen hebben invloed op gebruikers die Touch ID (iOS), Face ID (iOS), Android Biometric of andere toekomstige biometrische verificatiemethoden gebruiken om toegang te krijgen tot voor APP/MAM geschikte toepassingen. Door deze instellingen hebben Intune-beheerders gedetailleerdere controle over gebruikerstoegang. Op deze manier wordt de kans kleiner dat een onjuiste gebruiker bedrijfsgegevens kan zien op een apparaat met meerdere vingerafdrukken of andere biometrische toegangsmethoden. Open **Microsoft Intune** in de Azure-Portal. Selecteer **Mobiele apps** > **App-beveiligingsbeleid** > **Een beleid toevoegen** > **Instellingen**. Ga voor specifieke instellingen naar de sectie **Toegang**.

<!-- 1803 start -->

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>De Help- en Feedback-ervaring op de bedrijfsportal-app voor Android bijwerken <!--1631531 -->

De Help- en Feedback-ervaring op de bedrijfsportal-app voor Android wordt bijgewerkt, zodat deze overeenkomt met de aanbevolen procedures voor Android-apps. De bedrijfsportal-app voor Android wordt in de komende maanden ook bijgewerkt om het menu-item **Help en Feedback** op te delen in afzonderlijke menu-items, namelijk **Help** en **Feedback verzenden**. Op de **Help**-pagina komt een sectie **Veelgestelde vragen** sectie en een knop **E-mailondersteuning** waarmee eindgebruikers logboeken naar Microsoft kunnen uploaden en e-mail kunnen verzenden naar bedrijfsondersteuning om het probleem te beschrijven. **Feedback verzenden** leidt de gebruiker door een standaard Microsoft-feedbackformulier, waarin de gebruiker wordt gevraagd een keuze te maken uit: "Ik vindt iets leuk", "Ik vind iets niet leuk" of "Ik heb een idee."



<!-- the following are present prior to 1711 -->

## <a name="notices"></a>Mededelingen

Er zijn geen actieve meldingen op dit moment.

### <a name="see-also"></a>Zie ook
Zie [Wat is er nieuw in Microsoft Intune?](whats-new.md) voor meer informatie over recente ontwikkelingen.



