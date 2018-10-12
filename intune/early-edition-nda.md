---
title: Vroege editie
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/4/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: beee1462c1b6e683287b4d304df386ce525be820
ms.sourcegitcommit: 8fdddb684ecf5eabf071907168413bcd89a2f702
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/07/2018
ms.locfileid: "44141635"
---
# <a name="the-early-edition-for-microsoft-intune---september-2018"></a>De vroege editie voor Microsoft Intune - september 2018

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

<!-- 1809 start -->

### <a name="user-account-access-of-intune-apps-on-managed-android-and-ios-devices-----1248496----"></a>Toegang van gebruikersaccounts tot Intune-apps op beheerde Android- en iOS-apparaten <!-- ! 1248496  -->

Als Microsoft Intune-beheerder kunt u bepalen welke gebruikersaccounts worden toegevoegd aan Microsoft Office-toepassingen op beheerde apparaten. U kunt de toegang beperken tot uitsluitend toegestane gebruikersaccounts van de organisatie en persoonlijke accounts op ingeschreven apparaten blokkeren. 

### <a name="create-dns-suffixes-in-vpn-configuration-profiles-on-devices-running-windows-10----1333668---"></a>DNS-achtervoegsels maken in VPN-configuratieprofielen op apparaten met Windows 10 <!-- 1333668 -->
Wanneer u een VPN-apparaatconfiguratieprofiel maakt (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** platform > **VPN** profieltype), voert u bepaalde DNS-instellingen in. U kunt ook meerdere **DNS-achtervoegsels** invoeren in Intune. Wanneer u DNS-achtervoegsels gebruikt, kunt u naar een netwerkbron zoeken met behulp van de korte naam, in plaats van met de Fully Qualified Domain Name (FQDN). Met deze update kunt u ook de volgorde van de DNS-achtervoegsels in Intune wijzigen.
In [VPN-instellingen voor Windows 10](vpn-settings-windows-10.md#dns-settings) worden de huidige DNS-instellingen vermeld.
Dit is van toepassing op: Windows 10-apparaten

### <a name="support-for-always-on-vpn-for-android-enterprise-work-profiles----1333705---"></a>Ondersteuning voor altijd ingeschakelde VPN voor Android Enterprise-werkprofielen <!-- 1333705 -->
U kunt altijd ingeschakelde VPN-verbindingen gebruiken op Android Enterprise-apparaten met beheerde werkprofielen. Altijd ingeschakelde VPN-verbindingen blijven verbonden en maken direct opnieuw verbinding wanneer gebruikers hun apparaat ontgrendelen, het apparaat opnieuw wordt opgestart of het draadloze netwerk wordt gewijzigd. U kunt de verbinding ook in de vergrendelingsmodus zetten. Hiermee wordt al het netwerkverkeer geblokkeerd totdat de VPN-verbinding actief is.
De instelling voor altijd ingeschakelde VPN vindt u in **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** voor platform > **Apparaatbeperkingen** onder instellingen **Werkprofielen alleen** voor profieltype > **Verbinding**. 

### <a name="outlook-for-ios-and-android-app-configuration-policy---1828527---"></a>App-configuratiebeleid voor Outlook voor iOS en Android <!--1828527 -->
U kunt een app-configuratiebeleid voor Outlook voor iOS en Android maken. Aanvullende configuratie-instellingen worden toegevoegd wanneer het beleid wordt ingeschakeld voor Outlook voor iOS en Android.

### <a name="remotely-lock-noncompliant-devices----2064495---"></a>Niet-compatibele apparaten op afstand vergrendelen <!-- 2064495 -->
Wanneer een apparaat niet compatibel is, kunt u een actie maken voor het nalevingsbeleid waarbij het apparaat op afstand wordt vergrendeld. Maak in Intune > **Apparaatcompatibiliteit** een nieuw beleid of selecteer een bestaand beleid. Selecteer **Acties voor niet-naleving** > **Toevoegen** en kies ervoor om het apparaat op afstand te vergrendelen.
Ondersteund in: 
- Android
- iOS
- macOS
- Windows 10 Mobile 
- Windows Phone 8.1 en hoger 

### <a name="intune-app-data-transfer-settings-on-ios-mdm-enrolled-devices----2244713---"></a>Instellingen voor Intune APP-gegevensoverdracht op iOS-apparaten die via MDM zijn ingeschreven <!-- 2244713 -->
U kunt het beheer van instellingen voor Intune APP-gegevensoverdracht op iOS-apparaten die zijn ingeschreven via MDM scheiden van het opgeven van de identiteit van de ingeschreven gebruiker. Beheerders die de IntuneMAMUPN niet gebruiken, zullen geen wijziging in het gedrag opmerken. Als deze functionaliteit beschikbaar is, moeten beheerders die de IntuneMAMUPN gebruiken om het gedrag van de gegevensoverdracht op ingeschreven apparaten te beheren de nieuwe instellingen controleren en hun APP-instellingen zo nodig bijwerken.

### <a name="use-a-pre-shared-key-in-a-windows-10-wi-fi-profile----2662938---"></a>Een vooraf gedeelde sleutel gebruiken in een Wi-Fi-profiel voor Windows 10 <!-- 2662938 -->
U kunt een vooraf gedeelde sleutel gebruiken met het persoonlijke WPA/WPA2-beveiligingsprotocol om een Wi-Fi-configuratieprofiel voor Windows 10 te verifiëren.
U moet momenteel een Wi-Fi-profiel importeren of een aangepast profiel maken om een vooraf gedeelde sleutel te gebruiken. In [Wi-Fi-instellingen voor Windows 10](wi-fi-settings-windows.md) worden de huidige instellingen vermeld. 

### <a name="autopilot-device-sync-frequency-increasing-to-every-12-hours----2753673---"></a>De synchronisatiefrequentie voor Autopilot-apparaten wordt verhoogd naar elke 12 uur <!-- 2753673 -->
Autopilot-apparaten worden elke 12 uur in plaats van elke 24 uur gesynchroniseerd.

### <a name="apply-autopilot-profile-to-enrolled-win-10-devices-not-already-registered-for-autopilot----1558983---"></a>Het Autopilot-profiel toepassen op ingeschreven Windows 10-apparaten die nog niet zijn geregistreerd voor Autopilot <!-- 1558983 -->
U kunt Autopilot-profielen toepassen op ingeschreven Windows 10-apparaten die nog niet zijn geregistreerd voor Autopilot. Kies in het Autopilot-profiel de optie **Alle doelapparaten converteren naar Autopilot** om automatisch niet-Autopilot-apparaten te registreren bij de Autopilot-implementatieservice. Het kan 48 uur duren voordat de registratie is verwerkt. Wanneer het apparaat wordt uitgeschreven en opnieuw wordt ingesteld, wordt het door Autopilot ingericht. 

### <a name="create-and-assign-multiple-enrollment-status--page-profiles-to-azure-ad-groups----2526564--"></a>Meerdere profielen voor inschrijvingsstatuspagina's maken en toewijzen aan Azure AD-groepen <!-- 2526564-->
U kunt meerdere profielen voor inschrijvingsstatuspagina's maken en toewijzen aan Azure AD-gebruikersgroepen.

### <a name="intune-landing-page-updates-and-node-rename---2867309---"></a>Updates voor de Intune-landingspagina en de naamswijziging van een knooppunt <!--2867309 -->
Updates voor de Intune-landingspagina bevatten nieuwe en gewijzigde tegels en grafieken voor controle voor een betere gegevensvisualisatie. Het knooppunt **Mobiele apps** wordt gewijzigd in **Client-apps**.

### <a name="increased-end-user-access-using-the-company-portal-app----772203---"></a>Verbeterde toegang voor de eindgebruiker met de bedrijfsportal-app <!-- 772203 -->
Eindgebruikers hebben via de bedrijfsportal-app toegang tot belangrijke handelingen voor het account, zoals het opnieuw instellen van het wachtwoord en het AAD-profiel.

### <a name="issue-scep-certificates-to-user-less-devices----1744554---"></a>SCEP-certificaten uitgeven voor apparaten zonder gebruiker <!-- 1744554 -->
Momenteel worden certificaten uitgegeven voor gebruikers. U kunt SCEP-certificaten uitgeven voor apparaten, waaronder apparaten zonder gebruiker, zoals kiosken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** voor platform > **SCEP-certificaat** voor profiel). Andere updates bevatten:
- De eigenschap **Onderwerp** in een SCEP-profiel is nu een aangepast tekstvak en kan nieuwe variabelen bevatten. 
- De eigenschap **Alternatieve naam voor onderwerp** in een SCEP-profiel heeft nu een tabelopmaak en kan nieuwe variabelen bevatten. Een beheerder kan in de tabel een kenmerk toevoegen en de waarde in een aangepast tekstvak invullen. De alternatieve naam voor het onderwerp ondersteunt de volgende kenmerken: 
  - DNS
  - E-mailadres
  - UPN Deze nieuwe variabelen kunnen met statische tekst worden toegevoegd in een tekstvak voor aangepaste waarden. Het DNS-kenmerk kan bijvoorbeeld worden toegevoegd als `DNS = {{AzureADDeviceId}}.domain.com`.
  > [!NOTE]
  > Accolades, puntkomma's en pijp-symbolen '{} ; |' kunnen niet worden gebruikt in de statische tekst van de alternatieve naam voor het onderwerp. Accolades worden alleen geaccepteerd voor `Subject` of `Subject alternative name`, als ze een van de nieuwe apparaatcertificaatvariabelen omsluiten. Nieuwe apparaatcertificaatvariabelen:  
```
"{{AAD_Device_ID}}",
"{{Device_Serial}}",
"{{Device_IMEI}}",
"{{SerialNumber}}",
"{{IMEINumber}}",
"{{AzureADDeviceId}}",
"{{WiFiMacAddress}}",
"{{IMEI}}",
"{{DeviceName}}",
"{{FullyQualifiedDomainName}}",
"{{MEID}}",
```

> [!NOTE]
>  - `{{FullyQualifiedDomainName}}` kan alleen worden gebruikt voor Windows-apparaten en apparaten die aan een domein zijn toegevoegd. 
>  -  Houd er rekening mee dat wanneer u in het onderwerp of de alternatieve naam voor het onderwerp voor een apparaatcertificaat apparaateigenschappen opgeeft, zoals het IMEI-nummer, het serienummer en de Fully Qualified Domain Name, deze eigenschappen kunnen worden vervalst door een persoon met toegang tot het apparaat. 

In [Een SCEP-certificaatprofiel maken](certificates-scep-configure.md#create-a-scep-certificate-profile) worden de huidige variabelen bij het maken van een SCEP-configuratieprofiel vermeld. 

Is van toepassing op: Windows 10 en hoger en iOS, wordt ondersteund voor Wi-Fi



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

### <a name="windows-10-and-later-kiosk-profile-improvements-in-the-azure-portal----2748224-eeready---"></a>Verbeteringen voor kioskprofielen voor Windows 10 en hoger in Azure Portal <!-- 2748224 eeready -->
Het apparaatconfiguratieprofiel voor kiosken voor Windows 10 (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** voor platform > **Kioskvoorbeeld** voor profieltype) wordt verbeterd: 
- Momenteel kunt u meerdere kioskprofielen op hetzelfde apparaat maken. Met deze update biedt Intune ondersteuning voor slechts één kioskprofiel per apparaat. Als u toch meerdere kioskprofielen op één apparaat wilt, kunt u een aangepaste URI gebruiken.
-In het profiel voor een **kiosk voor meerdere apps** kunt u de tegelgrootte en volgorde voor toepassingen selecteren voor de **opmaak van het menu Start** in het toepassingenraster. Als u meer aanpassingen wilt aanbrengen, kunt u verdergaan met het uploaden van een XML-bestand.
- De instellingen voor de kioskbrowser worden verplaatst naar de **kiosk**instellingen. Momenteel hebben de instellingen voor de **kioskwebbrowser** hun eigen categorie in Azure Portal.
Van toepassing op Windows 10 en hoger

<!-- 1807 start -->

### <a name="improved-company-portal-app-experience-for-device-enrollment-manager-users----675800---"></a>Verbeterde Bedrijfsportal-app-ervaring voor gebruikers van de apparaatinschrijvingsmanager <!-- 675800 -->
Wanneer een apparaatinschrijvingsmanager (DEM) zich aanmeldt bij de Bedrijfsportal-app voor Windows, wordt in de app alleen het huidige DEM-apparaat weergegeven dat wordt uitgevoerd. Dankzij deze verbetering treden er minder time-outs op. Deze time-outs traden voorheen op wanneer de app probeerde alle apparaten met DEM-registratie te laden.  

### <a name="check-for-configuration-manager-compliance----2192052---"></a>Controleren op Configuration Manager-compatibiliteit <!-- 2192052 -->
Een toekomstige update bevat een nieuwe instelling voor System Center Configuration Manager-compatibiliteit (**Apparaatcompatibiliteit** > **Beleid** > **Beleid maken** > **Windows 10**). Configuration Manager verzendt signalen naar Intune-naleving. Met de Intune-instelling kunt u vereisen dat alle Configuration Manager-signalen de waarde 'compatibel' retourneren.

U kunt bijvoorbeeld vereisen dat alle software-updates worden geïnstalleerd op apparaten. Deze vereiste heeft in Configuration Manager de status 'Geïnstalleerd'. Als programma's op het apparaat zich in onbekende staat bevinden, is het apparaat niet-compatibel in Intune.

Van toepassing op Windows 10 en hoger

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Meldingen voor verlopend VPP-token of onvoldoende bedrijfsportal-licenties <!-- 2237572 -->
Als u het Volume Purchase Program (VPP) gebruikt om de bedrijfsportal vooraf in te richten tijdens DEP-inschrijving, waarschuwt Intune u wanneer het VPP-token bijna verloopt en wanneer er bijna te weinig licenties zijn voor de bedrijfsportal.

### <a name="additional-security-settings-for-windows-installer----2282430---"></a>Aanvullende beveiligingsinstellingen voor Windows Installer <!-- 2282430 -->
U kunt gebruikers toestaan om de installatie van apps te beheren. Als u deze functie is ingeschakeld, kunnen installaties worden toegestaan die anders worden gestopt vanwege een beveiligingsfout. U kunt het Windows-installatieprogramma de opdracht geven om verhoogde bevoegdheden te gebruiken wanneer een programma in een systeem wordt geïnstalleerd. Verder kunt u ingeschakelde items van Microsoft Azure Information Protection laten indexeren en de metagegevens voor de items laten opslaan op een niet-versleutelde locatie. Als het beleid is uitgeschakeld, worden de items met WIP-beveiliging niet geïndexeerd en worden ze niet weergegeven in de resultaten in Cortana of Verkenner. De functionaliteit voor deze opties is standaard uitgeschakeld. 

<!-- 1806 start -->

### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Toetsenborden van derden kunnen worden geblokkeerd door APP-instellingen op iOS <!-- 1248481 -->
Op iOS-apparaten kunnen Intune-beheerders het gebruik blokkeren van toetsenborden van derden bij het benaderen van organisatiegegevens in door beleid beveiligde apps. Wanneer het Application Protection Policy (APP; appbeveiligingsbeleid) is ingesteld om toetsenborden van derden te blokkeren, ontvangt de gebruiker een bericht als hij de eerste keer met bedrijfsgegevens werkt met een toetsenbord van derden. Alle opties, behalve het systeemeigen toetsenbord, worden geblokkeerd en zijn niet zichtbaar voor apparaatgebruikers. Apparaatgebruikers zien het dialoogvenster slechts één keer. 

### <a name="office-365-pro-plus-language-packs----1833450---"></a>Office 365 Pro Plus-taalpakketten <!-- 1833450 -->
Als Intune-beheerder kunt u aanvullende talen implementeren voor Office 365 Pro Plus-apps die via Intune worden beheerd. De lijst met beschikbare talen bevat het taalpakket **Type** (kern, gedeeltelijk en spellingcontrole). Selecteer in de Azure-portal **Microsoft Intune** > **Mobiele apps** > **Apps** > **Toevoegen**. In de lijst **App-type** op de blade **App toevoegen** selecteert u **Windows 10** onder **Office 365-suite**. Selecteer **Talen** in de blade **Instellingen voor app-suite**.

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



