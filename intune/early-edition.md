---
title: Vroege editie
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/03/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b6ca8108924c6c062da0d0ef56ab5b68635dd9ca
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="the-early-edition-for-microsoft-intune---april-2018"></a>De vroege editie voor Microsoft Intune - april 2018

De **vroege editie** bevat een lijst met functies die worden toegevoegd aan toekomstige releases van Microsoft Intune. Deze informatie wordt in beperkte mate verstrekt en kan worden gewijzigd. Deel deze informatie niet buiten uw bedrijf. Sommige functies die hier worden vermeld, zullen mogelijk niet beschikbaar zijn op de sluitingsdatum en worden mogelijk beschikbaar gesteld in een latere release. Andere functies worden getest in een proefversie, zodat we zeker weten dat ze in gebruik kunnen worden genomen. Als u vragen of opmerkingen hebt, kunt contact opnemen met uw contactpersoon voor de Microsoft-productgroep.

Deze pagina wordt regelmatig bijgewerkt. Controleer op andere updates.

> [!Note]
>De volgende wijzigingen worden momenteel ontwikkeld voor Intune. Zie de pagina met [nieuwe hybridefuncties](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) (Engelstalig) voor meer informatie over nieuwe hybridefuncties.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune in Azure Portal

<!-- 1804 start -->

### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252-----from-1802--"></a>Er worden nieuwe Windows Defender Credential Guard-instellingen toegevoegd aan de Endpoint Protection-instellingen <!--1102252 --><!--from 1802-->

Nieuwe instellingen voor [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard) worden toegevoegd aan **Apparaatconfiguratie** > **Profielen** > **Endpoint Protection**. De volgende instellingen worden toegevoegd:

- Platformbeveiligingsniveau: geef aan of het platformbeveiligingsniveau wordt ingeschakeld bij de volgende keer dat de computer wordt opgestart. Bij beveiliging op basis van virtualisatie is beveiligd opstarten vereist. Beveiliging op basis van virtualisatie kan eventueel worden ingeschakeld met behulp van DMA-beveiligingen (Direct Memory Access). Voor DMA-beveiligingen is hardwareondersteuning vereist en deze worden alleen ingeschakeld op apparaten die juist zijn geconfigureerd.
- Beveiliging op basis van virtualisatie: geef aan of beveiliging op basis van virtualisatie wordt ingeschakeld bij de volgende keer dat de computer wordt opgestart.
- Windows Defender Credential Guard: schakel Credential Guard met beveiliging op basis van virtualisatie in om referenties te kunnen beveiligen bij de volgende keer dat de computer wordt opgestart, wanneer het platformbeveiligingsniveau met beveiligd opstarten en de beveiliging op basis van virtualisatie beide zijn ingeschakeld. U kunt kiezen uit de volgende opties: **Uitgeschakeld**, **Ingeschakeld met UEFI-vergrendeling**, **Ingeschakeld zonder vergrendeling** en **Niet geconfigureerd**.
  - Met de optie Uitgeschakeld wordt Credential Guard extern uitgeschakeld als deze eerder is ingeschakeld met de optie Ingeschakeld zonder vergrendeling.

  - Bij de optie Ingeschakeld met UEFI-vergrendeling kan Credential Guard niet worden uitgeschakeld met de registersleutel of via Groepsbeleid. Als u Credential Guard wilt uitschakelen nadat deze instelling is gebruikt, moet u het groepsbeleid instellen op Uitgeschakeld en de beveiligingsfunctionaliteit van elke computer, met een fysiek aanwezige gebruiker, verwijderen om de configuratie die is bewaard in UEFI te wissen. Zolang de UEFI-configuratie behouden blijft, is Credential Guard ingeschakeld.

  - Met de optie Ingeschakeld zonder vergrendeling kan Credential Guard extern worden uitgeschakeld via Groepsbeleid. Op de apparaten die gebruikmaken van deze instelling moet ten minste Windows 10 (versie 1511) worden uitgevoerd.

  - Bij de optie Niet geconfigureerd is de beleidsinstelling niet gedefinieerd. De beleidsinstelling wordt door Groepsbeleid niet naar het register weggeschreven en deze heeft dus geen invloed op computers of gebruikers. Als het register een actuele instelling bevat, wordt deze niet gewijzigd.

### <a name="passcode-support-for-mam-pin-on-android---1438086---"></a>Ondersteuning van de wachtwoordcode voor MAM-pincode op Android<!-- 1438086 -->

Intune-beheerders kunnen instellen dat een toepassing moet worden gestart om een wachtwoordcode af te dwingen in plaats van een numerieke MAM-pincode. Als dit is geconfigureerd, moet de gebruiker een wachtwoordcode instellen en gebruiken wanneer daarom wordt gevraagd, alvorens toegang te krijgen tot toepassingen met MAM-functionaliteit. Een wachtwoordcode wordt gedefinieerd als een numerieke pincode met ten minste één speciaal teken of een hoofdletter/kleine letter. Intune ondersteunt wachtwoordcodes op dezelfde manier als de bestaande numerieke pincodes: er kan een minimumlengte worden ingesteld en tekens en tekenreeksen mogen via de beheerconsole worden herhaald. Voor deze functie moet de meest recente versie van de bedrijfsportal voor Android zijn geïnstalleerd. Deze functie is al beschikbaar voor iOS.

###  <a name="block-camera-and-screen-captures-on-android-for-work----1098977-eeready--"></a>De camera en schermopnamen blokkeren op Android for Work <!-- 1098977 eeready-->
Er zijn twee nieuwe eigenschappen beschikbaar die kunnen worden geblokkeerd wanneer u apparaatbeperkingen voor Android-apparaten configureert: 
- Camera: hiermee blokkeert u de toegang tot alle camera's op het apparaat
- Schermopname: hiermee blokkeert u de schermopname en voorkomt ook dat de inhoud wordt weergegeven op weergaveapparaten die geen beveiligde video-uitvoer hebben

Geldt voor Android for Work.

### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>Ondersteuning voor LOB-apps (line-of-business) voor macOS <!-- 1473977 -->
Microsoft Intune biedt de mogelijkheid om LOB-apps voor macOS te installeren vanuit Azure Portal. U kunt een macOS LOB-app aan Intune toevoegen nadat deze vooraf is verwerkt door het hulpprogramma dat beschikbaar is in GitHub. Kies op de blade **Intune** van Azure Portal **Mobiele apps**. Kies op de blade **Mobiele apps** **Apps** > **Toevoegen**. Selecteer op de blade **App toevoegen** de optie **Line-Of-Business-app**. 

### <a name="support-for-user-less-devices----1637553---"></a>Ondersteuning voor apparaten zonder gebruiker <!-- 1637553 -->
Intune ondersteunt de mogelijkheid om naleving te evalueren op een apparaat zonder gebruiker, zoals de Microsoft Surface Hub. Nalevingsbeleid kan worden gericht op specifieke apparaten. Naleving (en niet-naleving) kan worden vastgesteld voor apparaten waaraan geen gebruiker is gekoppeld.

### <a name="additions-to-local-device-security-options-settings----1403702---"></a>Toevoegingen aan instellingen voor de beveiligingsopties van lokale apparaten <!-- 1403702 -->
U kunt aanvullende instellingen voor de beveiligingsopties van lokale apparaten voor Windows 10-apparaten configureren. Extra instellingen zijn beschikbaar voor Microsoft Network Client, Microsoft-netwerkserver, toegang tot het netwerk en beveiliging en interactief aanmelden. U vindt deze instellingen in de Endpoint Protection-categorie wanneer u een configuratiebeleid voor Windows 10-apparaten maakt.

### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>Installatie van beleid, apps en certificaat- en netwerkprofielen vereisen <!-- 1553555 -->
Beheerders kunnen de toegang tot het Windows 10 RS4-bureaublad voor eindgebruikers blokkeren totdat beleid, apps en certificaat- en netwerkprofielen worden geïnstalleerd tijdens de inrichting van AutoPilot-apparaten.

### <a name="rules-for-removing-devices----1609459---"></a>Regels voor het verwijderen van apparaten <!-- 1609459 -->
Er zijn nieuwe regels beschikbaar waarmee u automatisch apparaten kunt verwijderen die een aantal dagen niet zijn ingecheckt. U kunt dit aantal instellen. Ga naar het deelvenster **Intune**, selecteer **Apparaten** en selecteer vervolgens **Regels voor het verwijderen van apparaten** om de nieuwe regel te zien.

### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>De installatie van consumenten-apps en -ervaringen op Windows 10 Enterprise RS4 Autopilot-apparaten voorkomen<!-- 1621980 -->
U kunt voorkomen dat consumenten-apps en -ervaringen op uw apparaten met Windows 10 Enterprise RS4 AutoPilot kunnen worden geïnstalleerd. Ga voor deze functie naar **Intune** > **Apparaatinschrijving** > **Windows-inschrijving** > **Windows AutoPilot-profielen** > **Nieuwe maken** > **Inschrijvingsinstellingen**. 

### <a name="advanced-threat-protection-integrated-with-intune----1629303---"></a>Advanced Threat Protection geïntegreerd in Intune <!-- 1629303 -->
[Advanced Threat Protection (ATP)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection) geeft het risiconiveau van Windows 10-apparaten weer. Wanneer Intune Windows 10-apparaten evalueert voor naleving, wordt de ATP-risicoscore opgenomen in deze evaluatie. U kunt ATP met voorwaardelijke toegang gebruiken om uw netwerk te beveiligen.

### <a name="new-enrollment-steps-for-users-on-devices-with-macos-high-sierra-10132---1734567---"></a>Nieuwe stappen voor registratie voor gebruikers op apparaten met macOS High Sierra 10.13.2+ <!--1734567 -->
macOS High Sierra 10.13.2 introduceert het concept Gebruiker goedgekeurd voor MDM-inschrijving. Voortaan kan in Intune met goedgekeurde inschrijvingen een aantal vertrouwelijke instellingen worden beheerd. Zie de ondersteuningsdocumentatie van Apple https://support.apple.com/HT208019 voor meer informatie.

Apparaten die zijn geregistreerd met behulp van de bedrijfsportal voor macOS worden beschouwd als Niet door de gebruiker goedgekeurd tenzij de eindgebruiker Systeemvoorkeuren opent en handmatig goedkeuring verleent. De bedrijfsportal voor macOS vraagt gebruikers van macOS 10.13.2 en hoger om hun registratie aan het einde van het registratieproces handmatig goed te keuren. De Intune-beheerconsole rapporteert of een geregistreerd apparaat door de gebruiker is goedgekeurd.

### <a name="delete-autopilot-devices----1713650---"></a>Autopilot-apparaten verwijderen <!-- 1713650 -->
Intune-beheerders kunnen Autopilot-apparaten verwijderen.

### <a name="built-in-all-users-and-all-devices-group-for-android-for-work-afw-app-assignment----1813073---"></a>Ingebouwde groepen Alle gebruikers en Alle apparaten voor app-toewijzing voor Android for Work (AFW) <!-- 1813073 -->
U kunt gebruikmaken van de ingebouwde groepen **Alle gebruikers** en **Alle apparaten** voor de app-toewijzing voor AFW. Zie [App-toewijzingen opnemen en uitsluiten in Microsoft Intune](apps-inc-exl-assignments.md) voor meer informatie.

### <a name="improved-device-deletion-experience---1832333---"></a>Verbeterde ervaring bij het verwijderen van apparaten <!--1832333 -->
U hoeft geen bedrijfsgegevens meer te verwijderen of de fabrieksinstellingen op een apparaat te herstellen voordat u een apparaat uit Intune verwijdert.

Meld u voor deze nieuwe ervaring aan in Intune en selecteer **Apparaten** > **Alle apparaten** > de naam van het apparaat > **Verwijderen**.

 Als u een bevestiging van het wissen of terugtrekken van een apparaat wilt blijven ontvangen, kunt u de standaard levenscyclusroute van een apparaat gebruiken door **Bedrijfsgegevens verwijderen** en **Fabrieksinstellingen terugzetten** uit te geven voordat u **Verwijderen** selecteert. 

### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>AutoPilot-profielen verplaatst naar de groep met <!-- 1877935 -->
Momenteel kunnen AutoPilot-implementatieprofielen worden toegewezen aan geselecteerde apparaten. Vanaf eind april kunt u deze profielen als volgt toewijzen:
- Maak (Azure AD-)groepen met AutoPilot-apparaten
- Wijs de gewenste profielen toe aan een Azure AD-groep. Het AutoPilot-profiel wordt nu toegewezen aan AutoPilot-apparaten in die groep.

### <a name="play-sounds-on-ios-when-in-lost-mode----1629303---"></a>Geluid afspelen in iOS in de modus Apparaat verloren <!-- 1629303 -->
Wanneer iOS-apparaten onder supervisie in Mobile Device Management (MDM) in de modus [Apparaat verloren](device-lost-mode.md) zijn, kunt u een geluid afspelen (**Apparaten** > **Alle apparaten** > selecteer een iOS-apparaat > **Overzicht** > **Meer**). Het geluid wordt afgespeeld totdat het apparaat is verwijderd uit de modus Apparaat verloren of wanneer een gebruiker het geluid op het apparaat uitschakelt. Van toepassing op apparaten met iOS 9.3 en hoger.

### <a name="use-a-custom-subject-name-on-scep-certificate----2064190---"></a>Een aangepaste onderwerpnaam gebruiken in een SCEP-certificaat <!-- 2064190 -->
U kunt de algemene naam **OnPremisesSamAccountName** gebruiken in een aangepast onderwerp voor een SCEP-certificaatprofiel. U kunt bijvoorbeeld `CN={OnPremisesSamAccountName})` gebruiken.

### <a name="send-diagnostic-reports-in-company-portal-app-for-macos----2216677---"></a>Diagnostische rapporten in de bedrijfsportal-app voor macOS verzenden <!-- 2216677 -->
De bedrijfsportal-app voor macOS-apparaten wordt bijgewerkt om de manier waarop gebruikers fouten in Intune rapporteren, te verbeteren. Vanuit de bedrijfsportal-app kunnen uw werknemers:
- Diagnostische rapporten rechtstreeks naar het Microsoft-ontwikkelteam uploaden.
- Via e-mail een incident-id aan het IT-ondersteuningsteam van uw bedrijf verzenden.

### <a name="always-on-vpn-for-windows-10---1333666---"></a>De optie Altijd aan voor VPN in Windows 10 <!--1333666 -->

Momenteel kan de optie [Altijd aan](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-auto-trigger-profile#always-on) worden gebruikt op Windows 10-apparaten door een aangepast VPN-profiel te gebruiken dat is gemaakt met OMA-URI.

Met deze update kunnen beheerders in Azure Portal de optie Altijd aan rechtstreeks in Intune inschakelen voor VPN-profielen in Windows 10. VPN-profielen met de optie Altijd aan maken automatisch verbinding wanneer:

- Gebruikers zich aanmelden op hun apparaten
- Het netwerk op het apparaat wijzigt
- Het scherm op het apparaat wordt ingeschakeld nadat het was uitgeschakeld

### <a name="improved-error-messaging-for-apple-mdm-push-certificate-upload-failure----2172331---"></a>Verbeterde foutberichten voor fouten bij het uploaden van Apple MDM-pushcertificaten <!-- 2172331 -->

In het foutbericht wordt uitgelegd dat dezelfde Apple ID moet worden gebruikt bij het vernieuwen van een bestaand MDM-certificaat.

###  <a name="device-profile-chart-and-status-list-show-all-devices-in-a-group----1449153-eeready---"></a>De profielgrafiek van het apparaat en de statuslijst geven alle apparaten in een groep weer <!-- 1449153 eeready -->
Wanneer u een apparaatprofiel configureert (**Apparaatconfiguratie** > **Profielen**), kunt u het apparaatprofiel, zoals iOS, kiezen. U kunt dit profiel toewijzen aan een groep met iOS-apparaten en niet-iOS-apparaten. De grafiek laat zien dat het profiel wordt toegepast op iOS- *en* niet-iOS-apparaten (**Apparaatconfiguratie** > **Profielen** > selecteer een bestaand profiel > **Overzicht**). Wanneer u de grafiek op het tabblad **Overzicht** selecteert, worden in **Apparaatstatus** alle apparaten in de groep weergegeven, niet alleen de iOS-apparaten. 

Met deze update geeft de grafiek (**Apparaatconfiguratie** > **Profielen** > selecteer een bestaand profiel > **Overzicht**) alleen het aantal voor het specifieke apparaatprofiel weer. Als bijvoorbeeld het apparaatprofiel wordt toegepast op iOS-apparaten, geeft de grafiek alleen het aantal iOS-apparaten weer. Als u de grafiek selecteert en de **apparaatstatus** opent, worden alleen de iOS-apparaten weergegeven.

Tijdens het maken van deze update is de grafiek tijdelijk verwijderd. 


<!-- 1803 start -->

#### <a name="multiple-exchange-connector-support----2070451---"></a>Ondersteuning voor meerdere Exchange Connectors <!-- 2070451 -->

U bent niet langer beperkt tot één Microsoft Intune Exchange Connector per tenant. Intune ondersteunt meerdere Exchange Connectors, zodat u voorwaardelijke toegang van Intune kunt instellen met meerdere on-premises Exchange-organisaties.

Met een on-premises Exchange Connector voor Intune kunt u apparaattoegang tot uw on-premises Exchange-postvakken beheren op basis van of een apparaat is ingeschreven bij Intune en voldoet aan het Intune-nalevingsbeleid voor apparaten. Als u een connector wilt instellen, downloadt u de on-premises Exchange Connector voor Intune vanaf Azure Portal en installeert u deze op een server in uw Exchange-organisatie. Kies op het Microsoft Intune-dashboard **On-premises toegang** en kies vervolgens onder **Installatie** de optie **Exchange ActiveSync-connector**. Download de on-premises Exchange Connector en installeer deze op een server in uw Exchange-organisatie. Nu u niet meer beperkt bent tot één Exchange Connector per tenant, kunt u, als u extra Exchange-organisaties hebt, dit zelfde proces volgen om een connector te downloaden en installeren voor elke extra Exchange-organisatie.

### <a name="support-coming-for-new-cisco-anyconnect-client-for-ios----1333708---"></a>Ondersteuning voor nieuwe Cisco AnyConnect-client voor iOS is binnenkort beschikbaar<!-- 1333708 -->

Nieuwe VPN-profielen gemaakt voor Cisco AnyConnect voor iOS werken met Cisco AnyConnect 4.0.7x en hoger. Bestaande iOS Cisco AnyConnect VPN-profielen krijgen het label **Cisco Legacy AnyConnect** en blijven op dezelfde manier werken met Cisco AnyConnect 4.0.5x .

> [!NOTE]
> Deze wijziging is alleen voor iOS; er blijft slechts één Cisco AnyConnect-optie voor Android, Android for Work en macOS.

#### <a name="more-information"></a>Meer informatie

U moet een nieuw iOS Cisco AnyConnect VPN-profiel maken voor de ondersteuning van de nieuwe app, omdat de nieuwe Cisco AnyConnect-app en de Cisco Legacy AnyConnect-app verschillende apps zijn. Als u de AnyConnect-client in uw omgeving beheert, moet u ook de nieuwe Cisco AnyConnect-app implementeren. Als u een upgrade wilt voltooien, moet u ook uw Cisco Legacy AnyConnect VPN-profiel wissen en de Cisco Legacy AnyConnect-app verwijderen.

NAC-integratie (Network Access Control) werkt in de eerste release niet voor de nieuwe AnyConnect-client. We werken samen met Cisco om NAC-integratie te bieden in een toekomstige versie van Intune.

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Mogelijkheid om vereiste line-of-business-apps (LOB) te implementeren voor alle gebruikers op apparaten met Windows 10 Desktop <!-- 1627835 RS4 -->
Klanten kunnen vereiste Windows 10 line-of-business-apps implementeren om in apparaatcontexten te installeren. Hierdoor worden deze apps beschikbaar voor alle gebruikers op het apparaat. Dit is alleen van toepassing op Windows 10 Desktop-apparaten.

### <a name="company-portal-enrollment-improved----1874230--"></a>Inschrijving bedrijfsportal verbeterd <!-- 1874230-->
Gebruikers die een apparaat inschrijven via de bedrijfsportal op Windows 10 build 1703 en hoger, kunnen de eerste stap van de inschrijving voltooien zonder de app te verlaten.

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>De Help- en Feedback-ervaring op de bedrijfsportal-app voor Android bijwerken <!--1631531 -->

We updaten de Help- en Feedback-ervaring op de bedrijfsportal-app voor Android zodat deze overeenkomt met de aanbevolen procedures voor Android-apps. We werken de bedrijfsportal-app voor Android in de komende maanden bij om het menu-item **Help en Feedback** op te delen in afzonderlijke menu-items, namelijk **Help** en **Feedback verzenden**. Op de **Help**-pagina komt een sectie **Veelgestelde vragen** sectie en een knop **E-mailondersteuning** waarmee eindgebruikers logboeken naar Microsoft kunnen uploaden en e-mail kunnen verzenden naar bedrijfsondersteuning om het probleem te beschrijven. **Feedback verzenden** leidt de gebruiker door een standaard Microsoft-feedbackformulier, waarin de gebruiker wordt gevraagd een keuze te maken uit: "Ik vindt iets leuk", "Ik vind iets niet leuk" of "Ik heb een idee."

<!-- 1802 start -->

### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Nieuwe printerinstellingen voor onderwijsprofielen <!-- 1308900 -->

Er komen voor onderwijsprofielen nieuwe instellingen beschikbaar onder de categorie **Printers**: **Printers**, **Standaardprinter**, **Nieuwe printers toevoegen**.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Beleid voor app-beveiliging <!-- 679615 -->
Via het beveiligingsbeleid voor Intune-apps kunt u algemene standaardbeleidsregels maken om snel beveiliging in te schakelen voor alle gebruikers in de gehele tenant.

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Azure Active Directory-websites kunnen de Intune Managed Browser-app vereisen en ondersteunen eenmalige aanmelding voor de Managed Browser (openbare preview) <!-- 710595 -->   
Met Azure Active Directory (Azure AD) kunt u de toegang tot websites op mobiele apparaten beperken tot de Intune Managed Browser-app. In de Managed Browser blijven websitegegevens veilig en gescheiden van de persoonlijke gegevens van eindgebruikers. Daarnaast ondersteunt de Managed Browser eenmalige aanmelding voor sites die door Azure AD worden beveiligd. Door u aan te melden bij de Managed Browser of door de Managed Browser op een apparaat te gebruiken met een andere app die door Intune wordt beheerd, krijgt de Managed Browser toegang tot bedrijfssites die door Azure AD worden beveiligd, zonder dat de gebruiker referenties hoeft in te voeren. Deze functionaliteit is van toepassing op sites zoals Outlook Web Access (OWA) en SharePoint Online, evenals andere bedrijfssites zoals intranetbronnen die via de Azure App Proxy worden geopend.




## <a name="notices"></a>Mededelingen

Er zijn geen actieve meldingen op dit moment.


### <a name="see-also"></a>Zie ook
Zie [Wat is er nieuw in Microsoft Intune?](whats-new.md) voor meer informatie over recente ontwikkelingen.


