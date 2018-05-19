---
title: Nieuwe functies in Microsoft Intune - Azure | Microsoft Docs
titlesuffix: ''
description: Ontdekken wat er nieuw is in Intune Azure Portal
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/08/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
/ms.custom: intune-azure
ms.openlocfilehash: e677e15d1e4ee688a826683ecd1d8d68620d2796
ms.sourcegitcommit: b0ad42fe5b5627e5555b2f9e5bb81bb44dbff078
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/09/2018
---
# <a name="whats-new-in-microsoft-intune"></a>Wat is er nieuw in Microsoft Intune?
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ontdek elke week wat er nieuw is in Microsoft Intune. U vindt hier ook informatie over [toekomstige wijzigingen](#whats-coming), [belangrijke kennisgevingen](#notices) betreffende de service en informatie over [oudere releases](whats-new-archive.md). Sommige functies worden gedurende een aantal weken geïmplementeerd en zijn mogelijk niet voor alle gebruikers in de eerste week beschikbaar.

> [!Note]
> Zie de [pagina Wat is er nieuw](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) voor informatie over nieuwe functionaliteit in het hybride beheer van mobiele apparaten (MDM).


<!-- Common categories:  
  ### App management
  ### Device enrollment
  ### Device management
  ### Device configuration
  ### Intune apps
  ### Monitor and troubleshoot
  ### Role-based access control

-->   

## <a name="week-of-may-7-2018"></a>Week van 7 mei 2018

### <a name="app-management"></a>Appbeheer

#### <a name="samsung-knox-mobile-enrollment-support---1112863--"></a>Ondersteuning voor Samsung Knox Mobile Enrollment<!--1112863-->

Wanneer u Intune met Samsung Knox Mobile Enrollment (KME) gebruikt, kunt u een groot aantal bedrijfseigen Android-apparaten inschrijven. Gebruikers op wifi- of mobiele netwerken kunnen inschrijven met een paar tikken wanneer ze hun apparaten voor het eerst inschakelen. Apparaten kunnen ook met Bluetooth of NFC worden ingeschreven als de Knox-registratie-app wordt gebruikt. Zie [Android-apparaten automatisch registreren met behulp van de Knox Mobile Enrollment van Samsung](android-samsung-knox-mobile-enroll.md) voor meer informatie.

#### <a name="requesting-help-in-the-company-portal-for-windows-10----1874137---"></a>Hulp aanvragen in de bedrijfsportal voor Windows 10 <!-- 1874137 -->

Vanuit de bedrijfsportal voor Windows 10 worden app-logboeken nu rechtstreeks naar Microsoft verzonden wanneer de gebruiker de werkstroom voor hulp bij een probleem in gang zet. Dit vereenvoudigt het detecteren en oplossen van problemen die aan Microsoft worden gemeld.

## <a name="week-of-april-23-2018"></a>Week van 23 april 2018

### <a name="app-management"></a>Appbeheer

#### <a name="passcode-support-for-mam-pin-on-android---1438086---"></a>Ondersteuning van de wachtwoordcode voor MAM-pincode op Android<!-- 1438086 -->

Intune-beheerders kunnen instellen dat een toepassing moet worden gestart om een wachtwoordcode af te dwingen in plaats van een numerieke MAM-pincode. Als dit is geconfigureerd, moet de gebruiker een wachtwoordcode instellen en gebruiken wanneer daarom wordt gevraagd, alvorens toegang te krijgen tot toepassingen met MAM-functionaliteit. Een wachtwoordcode wordt gedefinieerd als een numerieke pincode met ten minste één speciaal teken of een hoofdletter/kleine letter. Intune ondersteunt wachtwoordcodes op dezelfde manier als de bestaande numerieke pincodes: er kan een minimumlengte worden ingesteld en tekens en tekenreeksen mogen via de beheerconsole worden herhaald. Voor deze functie moet de meest recente versie van de bedrijfsportal voor Android zijn geïnstalleerd. Deze functie is al beschikbaar voor iOS.

#### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>Ondersteuning voor LOB-apps (line-of-business) voor macOS <!-- 1473977 -->
Microsoft Intune biedt de mogelijkheid om LOB-apps voor macOS te installeren vanuit Azure Portal. U kunt een macOS LOB-app aan Intune toevoegen nadat deze vooraf is verwerkt door het hulpprogramma dat beschikbaar is in GitHub. Kies op de blade **Intune** van Azure Portal **Mobiele apps**. Kies op de blade **Mobiele apps** **Apps** > **Toevoegen**. Selecteer op de blade **App toevoegen** de optie **Line-Of-Business-app**. 

#### <a name="built-in-all-users-and-all-devices-group-for-android-for-work-afw-app-assignment----1813073---"></a>Ingebouwde groepen Alle gebruikers en Alle apparaten voor app-toewijzing voor Android for Work (AFW) <!-- 1813073 -->
U kunt gebruikmaken van de ingebouwde groepen **Alle gebruikers** en **Alle apparaten** voor de app-toewijzing voor AFW. Zie [App-toewijzingen opnemen en uitsluiten in Microsoft Intune](apps-inc-exl-assignments.md) voor meer informatie.

#### <a name="intune-will-reinstall-required-apps-that-are-uninstalled-by-users----1947010---"></a>Vereiste apps die door gebruikers zijn verwijderd, worden opnieuw geïnstalleerd in Intune <!-- 1947010 -->
Als een eindgebruiker een vereiste app verwijdert, wordt de app in Intune automatisch binnen 24 uur opnieuw geïnstalleerd in plaats van te wachten op de herbeoordelingscyclus van 7 dagen.

### <a name="device-configuration"></a>Apparaatconfiguratie

####  <a name="device-profile-chart-and-status-list-show-all-devices-in-a-group----1449153-eeready---"></a>De profielgrafiek van het apparaat en de statuslijst geven alle apparaten in een groep weer <!-- 1449153 eeready -->
Wanneer u een apparaatprofiel configureert (**Apparaatconfiguratie** > **Profielen**), kunt u het apparaatprofiel, zoals iOS, kiezen. U kunt dit profiel toewijzen aan een groep met iOS-apparaten en niet-iOS-apparaten. De grafiek laat zien dat het profiel wordt toegepast op iOS- *en* niet-iOS-apparaten (**Apparaatconfiguratie** > **Profielen** > selecteer een bestaand profiel > **Overzicht**). Wanneer u de grafiek op het tabblad **Overzicht** selecteert, worden in **Apparaatstatus** alle apparaten in de groep weergegeven, niet alleen de iOS-apparaten. 

Met deze update wordt in de grafiek (**Apparaatconfiguratie** > **Profielen** > selecteer een bestaand profiel > **Overzicht**) alleen het aantal voor het specifieke apparaatprofiel weergegeven. Als bijvoorbeeld het apparaatprofiel wordt toegepast op iOS-apparaten, geeft de grafiek alleen het aantal iOS-apparaten weer. Als u de grafiek selecteert en de **apparaatstatus** opent, worden alleen de iOS-apparaten weergegeven.

Tijdens het maken van deze update is de grafiek tijdelijk verwijderd. 

#### <a name="always-on-vpn-for-windows-10---1333666---"></a>De optie Altijd aan voor VPN in Windows 10 <!--1333666 -->

Momenteel kan de optie [Altijd aan](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-auto-trigger-profile#always-on) worden gebruikt op Windows 10-apparaten door een aangepast VPN-profiel te gebruiken dat is gemaakt met OMA-URI.

Met deze update kunnen beheerders de optie Altijd aan rechtstreeks inschakelen in Intune in Azure Portal voor VPN-profielen in Windows 10. VPN-profielen met de optie Altijd aan maken automatisch verbinding wanneer:

- Gebruikers zich aanmelden op hun apparaten
- Het netwerk op het apparaat wijzigt
- Het scherm op het apparaat wordt ingeschakeld nadat het was uitgeschakeld

#### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Nieuwe printerinstellingen voor onderwijsprofielen <!-- 1308900 -->

Voor onderwijsprofielen zijn nieuwe instellingen beschikbaar onder de categorie **Printers**: **Printers**, **Standaardprinter**, **Nieuwe printers toevoegen**.

#### <a name="show-caller-id-in-personal-profile---android-for-work---1098984---"></a>Beller-id in persoonlijk profiel weergeven - Android for Work <!--1098984 -->
Wanneer u een persoonlijk profiel op een apparaat gebruikt, kunnen eindgebruikers de details van de beller-id van een zakelijke contactpersoon niet weergegeven. 

Er is een nieuwe instelling in **Android for Work** > **Apparaatbeperkingen** > **Instellingen voor werkprofiel**:
- Beller-id van zakelijk contactpersoon weergeven in persoonlijk profiel

Indien ingeschakeld (niet-geconfigureerd), worden de details van de beller die een zakelijke contactpersoon is, weergegeven in het persoonlijke profiel. Indien geblokkeerd, wordt het nummer van deze zakelijke contactpersoon niet weergegeven in het persoonlijke profiel. 

Van toepassing op: apparaten met Android-werkprofiel voor Android 6.0 en hoger

#### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252-----from-1802-and-1804--"></a>Er worden nieuwe Windows Defender Credential Guard-instellingen toegevoegd aan de Endpoint Protection-instellingen <!--1102252 --><!--from 1802 and 1804-->

In deze update, [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard) (**Apparaatconfiguratie** > **Profielen** > **Eindpuntbeveiliging**) zijn de volgende instellingen opgenomen: 

- **Windows Defender Credential Guard**: schakelt Credential Guard in met beveiliging op basis van virtualisatie. Het inschakelen van deze functie helpt om de referenties te beveiligen bij de volgende keer opstarten, wanneer **Niveau van platformbeveiliging met Beveiligd opstarten** en **Beveiliging op basis van virtualisatie** beide zijn ingeschakeld. Opties zijn onder andere:
  - **Uitgeschakeld**: Credential Guard wordt extern uitgeschakeld als deze eerder is ingeschakeld met de optie **Ingeschakeld zonder vergrendeling**.

  - **Ingeschakeld met UEFI-vergrendeling**: met deze optie kan Credential Guard niet worden uitgeschakeld met behulp van een registersleutel of via Groepsbeleid. Als u Credential Guard wilt uitschakelen nadat u deze instelling hebt gebruikt, moet u het Groepsbeleid instellen op Uitgeschakeld. Vervolgens verwijdert u de beveiligingsfunctie van elke computer, met een fysiek aanwezige gebruiker. Met deze stappen wordt de configuratie gewist die is behouden in UEFI. Zolang de UEFI-configuratie behouden blijft, is Credential Guard ingeschakeld.

  - **Uitgeschakeld zonder vergrendeling**: met deze optie kan Credential Guard extern worden uitgeschakeld via Groepsbeleid. Op de apparaten die gebruikmaken van deze instelling moet ten minste Windows 10 (versie 1511) worden uitgevoerd.

De volgende afhankelijke technologieën worden automatisch ingeschakeld bij het configureren van Credential Guard: 

  - **Beveiliging op basis van virtualisatie (VBS)**: schakelt Beveiliging op basis van virtualisatie (VBS) in bij de volgende keer opstarten. Beveiliging op basis van virtualisatie maakt gebruik van Windows Hypervisor om ondersteuning te bieden voor beveiligingsservices. Beveiligd opstarten is vereist.
  - **Beveiligd opstarten met directe geheugentoegang (DMA)**: hiermee schakelt u VBS in met Beveiligd opstarten en directe geheugentoegang. Voor DMA-beveiliging is hardwareondersteuning vereist en deze wordt alleen ingeschakeld op apparaten die juist zijn geconfigureerd. 

#### <a name="use-a-custom-subject-name-on-scep-certificate----2064190---"></a>Een aangepaste onderwerpnaam gebruiken in een SCEP-certificaat <!-- 2064190 -->
U kunt de algemene naam **OnPremisesSamAccountName** gebruiken in een aangepast onderwerp voor een SCEP-certificaatprofiel. U kunt bijvoorbeeld `CN={OnPremisesSamAccountName})` gebruiken.

####  <a name="block-camera-and-screen-captures-on-android-for-work----1098977-eeready--"></a>De camera en schermopnamen blokkeren op Android for Work <!-- 1098977 eeready-->
Er zijn twee nieuwe eigenschappen beschikbaar die kunnen worden geblokkeerd wanneer u apparaatbeperkingen voor Android-apparaten configureert: 
- Camera: hiermee blokkeert u de toegang tot alle camera's op het apparaat
- Schermopname: hiermee blokkeert u de schermopname en voorkomt ook dat de inhoud wordt weergegeven op weergaveapparaten die geen beveiligde video-uitvoer hebben

Geldt voor Android for Work.


### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="new-enrollment-steps-for-users-on-devices-with-macos-high-sierra-10132---1734567---"></a>Nieuwe stappen voor registratie voor gebruikers op apparaten met macOS High Sierra 10.13.2+ <!--1734567 -->
macOS High Sierra 10.13.2 introduceert het concept Gebruiker goedgekeurd voor MDM-inschrijving. Met goedgekeurde inschrijvingen kan in Intune een aantal vertrouwelijke instellingen worden beheerd. Zie de ondersteuningsdocumentatie van Apple https://support.apple.com/HT208019 voor meer informatie.

Apparaten die zijn geregistreerd met behulp van de bedrijfsportal voor macOS, worden beschouwd als Niet door de gebruiker goedgekeurd, tenzij de eindgebruiker Systeemvoorkeuren opent en handmatig goedkeuring verleent. De bedrijfsportal voor macOS vraagt gebruikers van macOS 10.13.2 en hoger om hun registratie aan het einde van het registratieproces handmatig goed te keuren. De Intune-beheerconsole rapporteert of een geregistreerd apparaat door de gebruiker is goedgekeurd.



### <a name="device-management"></a>Apparaatbeheer

#### <a name="advanced-threat-protection-atp-and-intune-are-fully-integrated----eeready-1629303---"></a>ATP (Advanced Threat Protection) en Intune zijn volledig geïntegreerd<!-- EEready 1629303 -->

[Advanced Threat Protection (ATP)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection) geeft het risiconiveau van Windows 10-apparaten weer. In Windows Defender Security Center (ATP-portal) kunt u een verbinding maken met Microsoft Intune. Zodra de verbinding is gemaakt, wordt Intune-nalevingsbeleid gebruikt om het acceptabele bedreigingsniveau te bepalen. Als het bedreigingsniveau wordt overschreden, kan de toegang tot verschillende apps in uw organisatie worden geblokkeerd op basis van Azure AD-beleid (Azure Directory) voor voorwaardelijke toegang.

Met deze functie kunnen bestanden worden gescand, bedreigingen worden gedetecteerd en alle risico's op uw Windows 10-apparaten worden gerapporteerd via ATP.

Zie [ATP voor voorwaardelijke toegang inschakelen in Intune](advanced-threat-protection.md).

#### <a name="support-for-user-less-devices----1637553---"></a>Ondersteuning voor apparaten zonder gebruiker <!-- 1637553 -->
Intune ondersteunt de mogelijkheid om naleving te evalueren op een apparaat zonder gebruiker, zoals de Microsoft Surface Hub. Nalevingsbeleid kan worden gericht op specifieke apparaten. Naleving (en niet-naleving) kan worden vastgesteld voor apparaten waaraan geen gebruiker is gekoppeld.

#### <a name="delete-autopilot-devices----1713650---"></a>Autopilot-apparaten verwijderen <!-- 1713650 -->
Intune-beheerders kunnen [AutoPilot-apparaten verwijderen](enrollment-autopilot.md#delete-autopilot-devices).

#### <a name="improved-device-deletion-experience---1832333---"></a>Verbeterde ervaring bij het verwijderen van apparaten <!--1832333 -->
U hoeft geen bedrijfsgegevens meer te verwijderen of de fabrieksinstellingen op een apparaat te herstellen voordat u [een apparaat uit Intune verwijdert](devices-wipe.md#delete-devices-from-the-intune-portal).

Meld u voor deze nieuwe ervaring aan in Intune en selecteer **Apparaten** > **Alle apparaten** > de naam van het apparaat > **Verwijderen**.

Als u een bevestiging van het wissen of terugtrekken van een apparaat wilt blijven ontvangen, kunt u de standaard levenscyclusroute van een apparaat gebruiken door **Bedrijfsgegevens verwijderen** en **Fabrieksinstellingen terugzetten** uit te geven voordat u **Verwijderen** selecteert. 

#### <a name="play-sounds-on-ios-when-in-lost-mode----1947769---"></a>Geluid afspelen in iOS in de modus Apparaat verloren <!-- 1947769 -->
Wanneer iOS-apparaten onder supervisie in MDM (Mobile Device Management) in de modus [Apparaat verloren](device-lost-mode.md) zijn, kunt u [een geluid afspelen](device-locate.md#activate-lost-mode-sound-alert-on-an-ios-device) (**Apparaten** > **Alle apparaten** > selecteer een iOS-apparaat > **Overzicht** > **Meer**). Het geluid wordt afgespeeld totdat het apparaat niet meer de modus Apparaat verloren heeft of totdat een gebruiker het geluid op het apparaat uitschakelt. Van toepassing op apparaten met iOS 9.3 en hoger.

#### <a name="block-or-allow-web-results-in-searches-made-on-an-intune-device---1972804--"></a>Webresultaten blokkeren of toestaan in zoekopdrachten die zijn uitgevoerd op een Intune-apparaat <!--1972804-->

Beheerders kunnen nu webresultaten blokkeren in zoekopdrachten die zijn uitgevoerd op een apparaat.

#### <a name="improved-error-messaging-for-apple-mdm-push-certificate-upload-failure----2172331---"></a>Verbeterde foutberichten voor fouten bij het uploaden van Apple MDM-pushcertificaten <!-- 2172331 -->

In het foutbericht wordt uitgelegd dat dezelfde Apple ID moet worden gebruikt bij het vernieuwen van een bestaand MDM-certificaat.

#### <a name="test-the-company-portal-for-macos-on-virtual-machines----2216679---"></a>De bedrijfsportal voor macOS testen op virtuele machines <!-- 2216679 -->

We hebben een handleiding gepubliceerd om IT-beheerders te helpen bij het testen van de bedrijfsportal-app voor macOS op virtuele machines in Parallels Desktop en VMware Fusion. U vindt meer informatie in [virtuele macOS-machines inschrijven voor testen](macos-enroll.md#enroll-virtual-macos-machines-for-testing).


### <a name="user-interface"></a>Gebruikersinterface

#### <a name="improved-device-tiles-in-the-windows-10-company-portal---2213364---"></a>Verbeterde apparaattegels in de Windows 10-bedrijfsportal <!--2213364 -->

De tegels zijn bijgewerkt zodat ze toegankelijker zijn voor gebruikers met een beperkt gezichtsvermogen en beter werken op schermlezers.

#### <a name="send-diagnostic-reports-in-company-portal-app-for-macos----2216677---"></a>Diagnostische rapporten in de bedrijfsportal-app voor macOS verzenden <!-- 2216677 -->
De bedrijfsportal-app voor macOS-apparaten wordt bijgewerkt om de manier waarop gebruikers fouten in Intune rapporteren, te verbeteren. Vanuit de bedrijfsportal-app kunnen werknemers:

- Diagnostische rapporten rechtstreeks naar het Microsoft-ontwikkelteam uploaden.
- Via e-mail een incident-id aan het IT-ondersteuningsteam van uw bedrijf verzenden.

Zie [Fouten verzenden voor macOS](/intune-user-help/send-errors-macos) voor meer informatie.

#### <a name="intune-adapts-to-fluent-design-system-in-the-company-portal-app-for-windows-10----1195010-wnready---"></a>Intune wordt aangepast aan Fluent Design System in de bedrijfsportal-app voor Windows 10 <!-- 1195010 WNready -->
De Intune-bedrijfsportal-app voor Windows 10 is bijgewerkt met de [Fluent Design System-navigatieweergave](https://docs.microsoft.com/en-us/windows/uwp/design/basics/navigation-basics). Aan de zijkant van de app wordt een statische verticale lijst weergegeven met alle toplevelpagina's. Klik op een willekeurige koppeling om snel pagina's weer te geven en te schakelen tussen pagina's. Dit is de eerste van verschillende updates die onderdeel uitmaken van onze voortdurende inspanningen om een meer adaptieve, intuïtieve en vertrouwde versie van Intune te maken. Ga naar [Wat is er nieuw in de gebruikersinterface van de app?](whats-new-app-ui.md) om het bijgewerkte uiterlijk te bekijken.

## <a name="week-of-april-16-2018"></a>Week van 16 april 2018

#### <a name="use-cisco-anyconnect-client-for-ios----eeready-1333708---"></a>Cisco AnyConnect-client voor iOS gebruiken <!-- EEready 1333708 -->

Wanneer u een nieuw VPN-profiel voor iOS maakt, hebt u nu twee opties: **Cisco AnyConnect** en **Cisco Legacy AnyConnect**. Cisco AnyConnect-profielen bieden ondersteuning voor 4.0.7x en nieuwere versies. Bestaande iOS Cisco AnyConnect VPN-profielen krijgen het label **Cisco Legacy AnyConnect** en blijven op dezelfde manier werken met Cisco AnyConnect 4.0.5x en oudere versies.

> [!NOTE]
> Deze wijziging is alleen van toepassing op iOS. Er blijft slechts één Cisco AnyConnect-optie voor platforms van Android, Android for Work en macOS.

#### <a name="jamf-enrolled-macos-devices-can-now-register-with-intune----2370684---"></a>Via Jamf ingeschreven macOS-apparaten kunnen nu worden geregistreerd bij Intune <!-- 2370684 -->

In versie 1.3 en 1.4 van de bedrijfsportal voor macOS zijn Jamf-apparaten niet geregistreerd bij Intune. Dit probleem is opgelost in versie 1.4.2 van de macOS-portal.


## <a name="week-of-april-9-2018"></a>Week van 9 april 2018

#### <a name="updated-help-experience-in-company-portal-app-for-android----1631531---"></a>Bijgewerkte Help-ervaring voor de bedrijfsportal-app voor Android <!-- 1631531 -->

We hebben de Help-ervaring in de bedrijfsportal-app voor Android bijgewerkt, zodat deze overeenkomt met de aanbevolen procedures voor het Android-platform. Wanneer gebruikers nu een probleem in de app tegenkomen, kunnen ze op **Menu** > **Help** tikken en:
- Logboeken met diagnostische gegevens uploaden naar Microsoft.
- Een e-mail verzenden waarin het probleem en de incident-id worden vermeld voor een ondersteuningsmedewerker.  

Als u de bijgewerkte Help-ervaring wilt bekijken, gaat u naar [Logboeken via e-mail verzenden](/intune-user-help/send-logs-to-your-it-admin-by-email-android) en [Fouten naar Microsoft verzenden](/intune-user-help/send-logs-to-microsoft-android).


#### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table----1471783---"></a>Nieuwe tabel met fouten bij inschrijving, trendgrafieken en oorzaken van fouten <!-- 1471783 -->

Op de overzichtspagina voor inschrijvingen kunt u de trend van mislukte inschrijvingen en de top vijf van oorzaken van fouten bekijken. Door te klikken op de grafiek of de tabel, kunt u inzoomen op gegevens om advies voor probleemoplossing en suggesties voor herstel te krijgen.

#### <a name="update-where-to-configure-your-app-protection-policies----2144597---"></a>Bijwerken waar u uw app-beveiligingsbeleid configureert <!-- 2144597 -->

U wordt van de serviceblade **Intune-app-beveiliging** in Azure Portal tijdelijk omgeleid naar de blade **Mobiele app**. Al uw beleidsregels voor de beveiliging van apps staan al in de blade **Mobiele app** in Intune onder App-configuratie. Het enige verschil is dat u naar Intune gaat in plaats van naar Intune-app-beveiliging. In april 2018 wordt deze omleiding beëindigd en wordt de serviceblade **Intune-app-beveiliging** helemaal verwijderd, zodat er slechts één locatie voor het app-beveiligingsbeleid in Intune is. 

**Wat betekent dit voor mij?**
Deze wijziging is van invloed op zowel zelfstandige als hybride klanten (Intune met Configuration Manager) van Intune. Door deze integratie wordt het beheer van uw cloud vereenvoudigd.

**Wat moet ik doen om me voor te bereiden op deze wijziging?**
Label **Intune** als favoriet in plaats van de serviceblade **Intune-app-beveiliging** en zorg ervoor dat u bekend bent met de werkstroom voor het beleid voor app-beveiliging in de blade **Mobiele app** in Intune. U wordt slechts tijdelijk omgeleid. De blade **App-beveiliging** wordt uiteindelijk verwijderd. Alle beleidsregels voor de beveiliging van apps staan al in Intune en u kunt uw beleid voor voorwaardelijke toegang wijzigen. Zie [Voorwaardelijke toegang in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) voor meer informatie over het wijzigen van het beleid voor voorwaardelijke toegang. Zie [Wat is beveiligingsbeleid voor apps?](app-protection-policy.md) voor meer informatie. 


## <a name="week-of-april-2-2018"></a>Week van 2 april 2018

### <a name="intune-apps"></a>Intune-apps

#### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866---"></a>Update van de gebruikerservaring voor de bedrijfsportal-app voor iOS<!--1412866 -->
Er is een grote update uitgebracht van de gebruikerservaring voor de bedrijfsportal-app voor iOS. De update is voorzien van een volledig nieuw visueel ontwerp met een gemoderniseerd uiterlijk. De functionaliteit van de app is behouden. De gebruiksvriendelijkheid en toegankelijkheid zijn echter verhoogd.  

U ziet ook:
- Ondersteuning voor iPhone X.
- De app start sneller en de laadsnelheid is verhoogd, zodat gebruikers tijd besparen.
- Aanvullende voortgangsbalken om gebruikers de meest recente statusgegevens te bieden.
- Verbeteringen in de manier waarop gebruikers logboeken uploaden, zodat u het eenvoudiger kunt melden als er iets fout gaat.  

Ga naar [Wat is er nieuw in de gebruikersinterface van de app?](whats-new-app-ui.md) om het bijgewerkte uiterlijk te bekijken.

#### <a name="protect-on-premise-exchange-data-using-intune-app-and-ca----1056954---"></a>On-premises Exchange-gegevens beveiligen met Intune APP en CA <!-- 1056954 -->
U kunt nu Intune App Policy Protection (APP) en Conditional Access (CA) gebruiken om de toegang tot on-premises Exchange-gegevens te beveiligen met Outlook Mobile. Als u beleid voor app-beveiliging wilt toevoegen of wijzigen in Azure Portal, selecteert u **Microsoft Intune** > **Mobiele apps** > **Beleid voor app-beveiliging**. Voordat u deze functie gebruikt, moet u ervoor zorgen dat u voldoet aan de [Outlook voor iOS- en Android-vereisten](https://technet.microsoft.com/en-us/library/mt846639(v=exchg.160).aspx).

## <a name="week-of-march-26-2018"></a>Week van 26 maart 2018

### <a name="app-management"></a>Appbeheer

#### <a name="alerts-for-expiring-ios-line-of-business-lob-apps-for-microsoft-intune----748789---"></a>Waarschuwingen voor iOS LOB-apps (Line-of-Business) voor Microsoft Intune die verlopen <!-- 748789 -->

In Azure Portal waarschuwt Intune u met betrekking tot iOS line-of-business-apps die bijna verlopen. Nadat een nieuwe versie van de iOS line-of-business-app is geüpload, verwijdert Intune de melding over het verlopen uit de lijst met apps. Deze melding wordt alleen actief voor recent geüploade iOS Line-Of-Business-apps. Een waarschuwing wordt 30 dagen voordat het inrichtingsprofiel voor iOS line-of-business-app verloopt, weergegeven. Zodra het profiel is verlopen, wijzigt de waarschuwing in Verlopen.

#### <a name="customize-your-company-portal-themes-with-hex-codes---1049561---"></a>De bedrijfsportalthema's aanpassen met hexadecimale codes <!--1049561 -->

U kunt de themakleur in de bedrijfsportal-apps aanpassen met hexadecimale codes. Wanneer u de hexadecimale code invoert, wordt door Intune bepaald met welke tekstkleur de hoogste mate van contrast tussen de tekstkleur en de achtergrondkleur wordt bereikt. U kunt in **Mobiele apps** > **Bedrijfsportal** bekijken hoe de tekstkleur en uw bedrijfslogo bij deze kleur worden weergegeven.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise----1813081---"></a>App-toewijzing op basis van groepen opnemen en uitsluiten voor Android Enterprise <!-- 1813081 -->

Android Enterprise (voorheen bekend als Android for Work) ondersteunt het opnemen en uitsluiten van groepen, maar biedt geen ondersteuning voor de vooraf gemaakte ingebouwde groepen **Alle gebruikers** en **Alle apparaten**. Zie [App-toewijzingen opnemen en uitsluiten in Microsoft Intune](apps-inc-exl-assignments.md) voor meer informatie.


### <a name="device-management"></a>Apparaatbeheer

#### <a name="new-security-enhancements-in-the-intune-service-----1637539---"></a>Verbeteringen in de beveiliging van de Intune-service <!-- 1637539 -->   

Er is een wisselknop in Intune geïntroduceerd waarmee zelfstandige klanten van Intune zonder dat een beleid is toegewezen apparaten kunnen behandelen als **Compatibel** (beveiligingsfunctie uitgeschakeld) of als **Niet compatibel** (beveiligingsfunctie ingeschakeld). Hierdoor kan alleen toegang tot de resources worden verkregen nadat de compatibiliteit van het apparaat is geëvalueerd.

De invloed van deze functies verschilt, afhankelijk of u al nalevingsbeleid hebt toegewezen of niet.

- Als u een nieuw of bestaand account hebt en geen nalevingsbeleid aan uw apparaten hebt toegewezen, wordt de wisselknop automatisch ingesteld op **Compatibel**. De functie wordt standaard uitgeschakeld als standaardinstelling in de console. Dit heeft geen gevolgen voor eindgebruikers.
- Als u een bestaand account hebt en u apparaten hebt waaraan een nalevingsbeleid is toegewezen, wordt de wisselknop automatisch ingesteld op **Niet-compatibel**. Zodra de update van maart is uitgerold, is deze functie beschikbaar als standaardinstelling.

Als u nalevingsbeleid met voorwaardelijke toegang (CA) gebruikt en deze functie is ingeschakeld, worden apparaten waaraan niet ten minste één nalevingsbeleid is toegewezen, door CA geblokkeerd. Eindgebruikers die zijn gekoppeld aan deze apparaten en eerder toegang hadden tot e-mail, raken deze toegang kwijt tenzij u ten minste één nalevingsbeleid aan alle apparaten toewijst.   

Hoewel de standaard status in-/uitschakelen wordt weergegeven in de gebruikersinterface na de update van maart, wordt deze status niet direct afgedwongen. Eventuele wijzigingen die u in de wisselknop aanbrengt, hebben geen invloed op de compatibiliteit van apparaten totdat de wisselknop in uw account werkt. In Berichtencentrum vindt u informatie over wanneer uw account is bijgewerkt. Dit kan enkele dagen duren nadat uw Intune-service is bijgewerkt voor maart.

**Aanvullende informatie**: [https://aka.ms/compliance_policies](https://aka.ms/compliance_policies)

#### <a name="enhanced-jailbreak-detection----846515---"></a>Verbeterde jailbreakdetectie <!-- 846515 -->

Verbeterde jailbreak-detectie is een nieuwe nalevingsinstelling die de manier waarop Intune opengebroken apparaten evalueert, verbetert. De instelling zorgt ervoor dat het apparaat regelmatiger incheckt bij Intune, waarvoor de locatieservices van het apparaat worden gebruikt. Ook heeft dit invloed op het batterijvermogen.

#### <a name="reset-passwords-for-android-o-devices----1238299---"></a>Wachtwoorden voor Android O-apparaten opnieuw instellen <!-- 1238299 -->
U kunt de wachtwoorden voor ingeschreven Android 8.0-apparaten opnieuw instellen met werkprofielen. Wanneer u een aanvraag Wachtwoord opnieuw instellen naar een Android 8.0-apparaat verzendt, wordt hiermee een nieuw wachtwoord voor het ontgrendelen van het apparaat of een vraag voor het beheerde profiel ingesteld voor de huidige gebruiker. Het wachtwoord of de vraag wordt verzonden en is onmiddellijk van kracht.

#### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Nalevingsbeleid afstemmen op apparaten in apparaatgroepen <!--1307012 -->

U kunt nalevingsbeleid richten op gebruikers in gebruikersgroepen. Met deze update kunt u nalevingsbeleid richten op apparaten in apparaatgroepen. Apparaten waarop beleid is gericht als onderdeel van apparaatgroepen, ontvangen geen maatregelen voor naleving.

#### <a name="new-management-name-column----1333586---"></a>Nieuwe kolom Naam voor beheer <!-- 1333586 -->
 Een nieuwe kolom met de naam **Naam voor beheer** is beschikbaar op de blade voor apparaten. Dit is een automatisch gegenereerde, niet bewerkbare naam die per apparaat wordt toegewezen op basis van de volgende formule:
- Standaardnaam voor alle apparaten: <username><em><devicetype></em><enrollmenttimestamp>
- Voor bulksgewijs toegevoegde apparaten: < PackageId/ProfileId ><em><DeviceType></em><EnrollmentTime>

Dit is een optionele kolom in de blade voor apparaten. Deze is niet standaard beschikbaar en u kunt de kolom alleen openen via de kolomkiezer. De naam van het apparaat wordt niet beïnvloed door deze nieuwe kolom.

#### <a name="ios-devices-are-prompted-for-a-pin-every-15-minutes---1550837---"></a>Op iOS-apparaten wordt elke vijftien minuten om een pincode gevraagd <!--1550837 -->
Nadat een nalevings- of configuratiebeleid op een iOS-apparaat is toegepast, wordt gebruikers elke vijftien minuten gevraagd een pincode in te stellen. Gebruikers wordt continu gevraagd een pincode in te stellen totdat de code is ingesteld.

#### <a name="schedule-your-automatic-updates---1805514---"></a>Automatische updates plannen <!--1805514 -->
In Intune kunt u met behulp van de [instellingen voor Windows 10-updatering](windows-update-for-business-configure.md) bepalen hoe automatische updates worden geïnstalleerd. Met deze update kunt u terugkerende updates plannen en de week, de dag en het tijdstip opgeven.

#### <a name="use-fully-distinguished-name-as-subject-for-scep-certificate---2221763---"></a>De volledige DN-naam gebruiken als onderwerp voor het SCEP-certificaat <!--2221763 -->
Wanneer u een SCEP-certificaatprofiel maakt, voert u de naam van het onderwerp in. Met deze update kunt u als naam van het onderwerp de volledige DN-naam gebruiken. Selecteer **Aangepast** bij **Onderwerpnaam** en voer `CN={{OnPrem_Distinguished_Name}}` in. Als u de variabele `{{OnPrem_Distinguished_Name}}` wilt gebruiken, moet u het gebruikerskenmerk `onpremisesdistingishedname` met behulp van [Azure Active Directory (AD) Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) synchroniseren met uw exemplaar van Azure AD.

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="enable-bluetooth-contact-sharing---android-for-work---1098983---"></a>Delen van contactpersonen via Bluetooth inschakelen - Android for Work <!--1098983 -->
Standaard wordt op Android-apparaten voorkomen dat contactpersonen in het werkprofiel kunnen worden gesynchroniseerd met Bluetooth-apparaten. Als gevolg hiervan worden contactpersonen in het werkprofiel niet weergegeven bij Nummerweergave voor Bluetooth-apparaten.

Er is een nieuwe instelling in **Android for Work** > **Apparaatbeperkingen** > **Instellingen voor werkprofiel**:
- Contactpersoon delen via Bluetooth

De Intune-beheerder kan deze instellingen configureren om delen in te schakelen. Dit is handig als u een apparaat wilt koppelen met een Bluetooth-apparaat in auto's waarop Nummerweergave wordt weergegeven voor handsfreegebruik. Als deze instellingen zijn ingeschakeld, worden de contactpersonen voor het werkprofiel weergegeven. Als deze instellingen niet zijn ingeschakeld, worden de contactpersonen voor het werkprofiel niet weergegeven.

#### <a name="configure-gatekeeper-to-control-macos-app-download-source----1690459---"></a>Gatekeeper configureren om de downloadbron van macOS-apps te beheren <!-- 1690459 -->

U kunt Gatekeeper configureren om uw apparaten te beveiligen tegen apps door te bepalen waarvan de apps kunnen worden gedownload. U kunt de volgende downloadbronnen configureren: **Mac App Store**, **Mac App Store en geïdentificeerde ontwikkelaars** of **Overal**. U kunt ook configureren of gebruikers een app kunnen installeren door middel van CTRL+klikken om deze Gatekeeper-voorzieningen te overschrijven.

Deze instellingen zijn te vinden onder **Apparaatconfiguratie** -> **Profiel maken** -> **macOS**  ->   **Eindpuntbeveiliging**.

#### <a name="configure-the-mac-application-firewall----1690461---"></a>De firewall van Mac-toepassingen configureren <!-- 1690461 -->

U kunt de firewall van Mac-toepassingen configureren. U kunt deze gebruiken om verbindingen per toepassing te controleren, in plaats van per poort. Zo kunt u beter profiteren van de voordelen van firewallbeveiliging. Bovendien helpt het te voorkomen dat ongewenste apps gebruikmaken van netwerkpoorten die zijn geopend voor legitieme apps.

Deze functie kunt u vinden onder **Apparaatconfiguratie** -> **Profiel maken** -> **macOS** -> **Eindpuntbeveiliging**.

Wanneer u de Firewall-instelling hebt ingeschakeld, kunt u de firewall configureren met behulp van twee strategieën:

- Alle binnenkomende verbindingen blokkeren

   U kunt alle binnenkomende verbindingen voor de doelapparaten blokkeren. Als u ervoor kiest om dit te doen, worden binnenkomende verbindingen voor alle apps geblokkeerd.

- Specifieke apps blokkeren of toestaan

   U kunt specifieke apps toestemming geven binnenkomende verbindingen te ontvangen of u kunt apps blokkeren. U kunt ook de verborgen modus inschakelen om reacties op peilverzoeken te voorkomen.

####  <a name="detailed-error-codes-and-messages----1376342---"></a>Gedetailleerde foutcodes en -berichten <!-- 1376342 -->

In uw apparaatconfiguratie kunnen gedetailleerde foutcodes en -berichten worden weergegeven. In deze verbeterde rapportage worden de instellingen, de status van deze instellingen en details over probleemoplossing weergegeven.

##### <a name="more-information"></a>Meer informatie

- Alle binnenkomende verbindingen blokkeren

   Hiermee worden alle services voor delen (zoals delen van bestanden en delen van het scherm) geblokkeerd en kunnen deze geen binnenkomende verbindingen ontvangen. De systeemservices die nog steeds binnenkomende verbindingen kunnen ontvangen, zijn:
  - configd - implementeert DHCP en andere services voor netwerkconfiguratie
  - mDNSResponder - implementeert Bonjour
  - racoon - implementeert IPSec

    Als u services voor delen wilt gebruiken, zorgt u ervoor dat **Binnenkomende verbindingen** is ingesteld op **Niet geconfigureerd** (niet op **Blokkeren**).

- Verborgen modus

   Schakel deze optie in om te voorkomen dat de computer reageert op peilverzoeken. De computer reageert nog wel op binnenkomende verzoeken voor toegestane apps. Onverwachte aanvragen, zoals ICMP (ping), worden genegeerd.

#### <a name="disable-checks-on-device-restart---1805490---"></a>Controles bij opnieuw starten van apparaat uitschakelen <!--1805490 -->
In Intune kunt u [software-updates beheren]](windows-update-for-business-configure.md). In deze update is de eigenschap <strong>Controles voor opnieuw starten</strong> beschikbaar en standaard ingeschakeld. Als u de standaardcontroles wilt overslaan die worden uitgevoerd wanneer u een apparaat opnieuw start (controle van actieve gebruikers, batterijniveau, enzovoort), selecteert u <strong>Overslaan</strong>.

#### <a name="new-windows-10-insider-preview-channels-available-for-deployment-rings----1746293---"></a>Nieuwe Windows 10 Insider Preview-kanalen beschikbaar voor implementatieringen <!-- 1746293 -->
U kunt nu de volgende Windows 10 Insider Preview-onderhoudskanalen selecteren wanneer u een Windows 10-implementatiering maakt:
- Windows Insider build &#8208; Snel
- Windows Insider build &#8208; Langzaam
- Windows Insider-build vrijgeven 

Zie [Insider Preview-builds beheren](https://insider.windows.com/en-us/for-business-organization-admin/) voor meer informatie over deze kanalen.   
Zie [Software-updates beheren in Intune](windows-update-for-business-configure.md) voor meer informatie over het maken van implementatiekanalen in Intune.

### <a name="intune-apps"></a>Intune-apps

#### <a name="company-portal-enrollment-improved----1874230-eeready--"></a>Inschrijving bedrijfsportal verbeterd <!-- 1874230 eeready-->
Gebruikers die een apparaat inschrijven via de bedrijfsportal in Windows 10-build 1703 en hoger, kunnen de eerste stap van de inschrijving voltooien zonder de app te verlaten.
#### <a name="hololens-and-surface-hub-now-appear-in-device-lists---1725868---"></a>HoloLens en Surface Hub nu worden weergegeven in de apparaatlijsten <!--1725868 -->
Er is ondersteuning toegevoegd voor het weergeven van HoloLens- en Surface Hub-apparaten die via Intune zijn geregistreerd bij de bedrijfsportal-app voor Android.

#### <a name="custom-book-categories-for-volume-purchase-progream-vpp-ebooks----1488911---"></a>Aangepaste boekcategorieën voor eBooks in het VPP-programma (volume-aankoopprogramma) <!-- 1488911 -->
U kunt aangepaste eBook-categorieën maken en vervolgens VPP eBooks toewijzen aan deze aangepaste eBook-categorieën. Eindgebruikers kunnen de nieuwe eBook-categorieën en de boeken die zijn toegewezen aan de categorieën bekijken. Zie [Apps en boeken met Microsoft Intune beheren die via het Volume Purchase Program zijn gekocht](vpp-apps.md) voor meer informatie.  

#### <a name="support-changes-for-company-portal-app-for-windows-send-feedback-option----2070166---"></a>Optie voor feedback verzenden voor wijzigingen in de ondersteuning voor de bedrijfsportal-app voor Windows<!-- 2070166 -->
Vanaf 30 april 2018 werkt de optie **Feedback verzenden** in de bedrijfsportal-app voor Windows alleen op apparaten met de Windows 10 Jubileumupdate (1607) en hoger. De optie voor het verzenden van feedback wordt niet meer ondersteund bij gebruik van de bedrijfsportal-app voor Windows met:  
- Windows 10, 1507 release  
- Windows 10, 1511 release  
- Windows Phone 8.1 

Als uw apparaat Windows 10 RS1 of hoger gebruikt, moet u de nieuwste versie van de Windows-bedrijfsportal downloaden in de Store. Als u een niet-ondersteunde versie uitvoert, kunt u feedback blijven verzenden via de volgende kanalen: 
- De Feedback Hub-app in Windows 10
- E-mail WinCPfeedback@microsoft.com  

#### <a name="new-windows-defender-application-guard-settings----1631890---"></a>Nieuwe instellingen voor Windows Defender Application Guard <!-- 1631890 -->

- **Grafische versnelling inschakelen**: beheerders kunnen voortaan een virtuele grafische processor inschakelen voor Windows Defender Application Guard. Met deze instelling kan de CPU taken voor de grafische weergave overdragen aan de vGPU. Dit kan de prestaties verbeteren wanneer u met websites werkt die veeleisende grafische weergaven bevatten of een video in de container bekijkt.

- **SaveFilestoHost**: beheerders kunnen ervoor zorgen dat bestanden worden doorgegeven van Microsoft Edge, die in de container wordt uitgevoerd, naar het hostbestandsysteem. Wanneer u deze optie inschakelt, kunnen gebruikers bestanden uit Microsoft Edge in de container downloaden naar het hostbestandsysteem.

#### <a name="mam-protection-policies-targeted-based-on-management-state----1665993---"></a>Gericht MAM-beleid op basis van de beheerstatus <!-- 1665993 -->
U kunt zich richten op MAM-beleid op basis van de beheerstatus van het apparaat:
- **Android-apparaten**: u kunt zich richten op niet-beheerde apparaten, door Intune beheerde apparaten en door Intune beheerde Android Enterprise-profielen (voorheen Android for Work).
- **iOS-apparaten**: u kunt zich richten op niet-beheerde apparaten (alleen MAM) of door Intune beheerde apparaten.

    > [!NOTE]
    > - iOS-ondersteuning voor deze functionaliteit wordt in april 2018 uitgerold.

Zie [Beleidsregels voor app-beveiliging toepassen op basis van de apparaatbeheerstatus](app-protection-policies.md) voor meer informatie.

#### <a name="improvements-to-the-language-in-the-company-portal-app-for-windows----1683758---"></a>Verbeteringen in de taal in de bedrijfsportal-app voor Windows <!-- 1683758 -->
In de bedrijfsportal voor Windows 10 is de taal gebruiksvriendelijker en meer specifiek voor uw bedrijf gemaakt. Zie [Wat is er nieuw in de gebruikersinterface van apps?](whats-new-app-ui.md) voor een aantal voorbeeldafbeeldingen van wat we hebben gedaan.

#### <a name="new-additions-to-our-docs-about-user-privacy----1440709---"></a>Toevoegingen aan onze documentatie over de privacy van gebruikers <!-- 1440709 -->
Als onderdeel van onze inspanning om eindgebruikers meer controle over hun gegevens en privacy te geven, is de documentatie bijgewerkt waarin wordt uitgelegd hoe u gegevens die lokaal zijn opgeslagen door de bedrijfsportal-apps kunt weergeven en verwijderen. U vindt deze updates op:

- **Android**: [Uw Android-apparaat uit Intune verwijderen](/intune-user-help/unenroll-your-device-from-intune-android.md)
- **Android, wanneer de gebruiker de gebruiksvoorwaarden heeft afgewezen**: [Beheer van uw apparaten verwijderen als u de gebruiksvoorwaarden hebt afgewezen](/intune-user-help/unenroll-your-device-from-intune-if-you-declined-terms-of-use-android.md)
- **iOS**: [Uw iOS-apparaat uit Intune verwijderen](/intune-user-help/unenroll-your-device-from-intune-ios.md)
- **Windows**: [Uw Windows-apparaat uit Intune verwijderen](/intune-user-help/unenroll-your-device-from-intune-windows.md)

## <a name="week-of-march-19-2018"></a>Week van 19 maart 2018

### <a name="export-all-devices-into-csv-files-in-ie-edge-or-chrome----2258071---"></a>Alle apparaten exporteren naar CSV-bestanden in Internet Explorer, Edge of Chrome <!-- 2258071 -->
In **Apparaten** > **Alle apparaten** kunt u de apparaten **Exporteren** naar een lijst met de CSV-indeling. Gebruikers van Internet Explorer (IE) met meer dan 10.000 apparaten kunnen hun apparaten exporteren naar meerdere bestanden. Elk bestand bevat maximaal 10.000 apparaten.

Gebruikers van Edge en Chrome met meer dan 30.000 apparaten kunnen hun apparaten exporteren naar meerdere bestanden. Elk bestand bevat maximaal 30.000 apparaten.

[Apparaten beheren](device-management.md) biedt meer details over wat u kunt doen met apparaten die u beheert.

## <a name="week-of-march-12-2018"></a>Week van 12 maart 2018

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Azure Active Directory-websites kunnen de Intune Managed Browser-app vereisen en ondersteunen eenmalige aanmelding voor de Managed Browser (openbare preview) <!-- 710595 -->

Met Azure Active Directory (Azure AD) kunt u nu de toegang tot websites op mobiele apparaten beperken tot de Intune Managed Browser-app. In de Managed Browser blijven websitegegevens veilig en gescheiden van de persoonlijke gegevens van eindgebruikers. Daarnaast ondersteunt de Managed Browser eenmalige aanmelding voor sites die door Azure AD worden beveiligd. Door u aan te melden bij de Managed Browser of door de Managed Browser op een apparaat te gebruiken met een andere app die door Intune wordt beheerd, krijgt de Managed Browser toegang tot bedrijfssites die door Azure AD worden beveiligd, zonder dat de gebruiker referenties hoeft in te voeren. Deze functionaliteit is van toepassing op sites zoals Outlook Web Access (OWA) en SharePoint Online, evenals andere bedrijfssites zoals intranetbronnen die via de Azure App Proxy worden geopend.

#### <a name="company-portal-app-for-android-visual-updates---976944---"></a>Bedrijfsportal-app voor visuele Android-updates <!--976944 -->

De bedrijfsportal-app voor Android is bijgewerkt om de richtlijnen voor [Ontwerp van materiaal](https://material.io/) van Android te volgen. In het Engelstalige artikel [What's new in app UI](whats-new-app-ui.md) (Nieuw in de gebruikersinterface van de app) kunt u afbeeldingen van de nieuwe pictogrammen bekijken.

### <a name="new-windows-defender-exploit-guard-settings----1631893---"></a>Nieuwe instellingen voor Windows Defender Exploit Guard <!-- 1631893 -->

Zes nieuwe instellingen voor <strong>Kwetsbaarheid voor aanvallen verminderen</strong> en uitgebreide mogelijkheden voor <strong>Gecontroleerde mappentoegang: mapbeveiliging</strong> zijn nu beschikbaar. Deze instellingen kunt u vinden op: Apparaatconfiguratie\Profielen\
Profiel maken\Endpoint Protection\Windows Defender Exploit Guard.

#### <a name="attack-surface-reduction"></a>Kwetsbaarheid voor aanvallen verminderen

|Naam van de instelling  |Instellingsopties  |Description  |
|---------|---------|---------|
|Geavanceerde ransomwarebeveiliging|Ingeschakeld, Controleren, Niet geconfigureerd|Gebruik agressieve ransomwarebeveiliging.|
|Referentiediefstal in het Windows-subsysteem voor de lokale beveiligingsautoriteit markeren|Ingeschakeld, Controleren, Niet geconfigureerd|Markeer referentiediefstal in het Windows-subsysteem voor de lokale beveiligingsautoriteit (lsass.exe).|
|Het maken van processen met PSExec- en WMI-opdrachten|Blokkeren, Controleren, Niet geconfigureerd|Blokkeer het maken van processen die afkomstig zijn van PSExec- en WMI-opdrachten.|
|Niet-vertrouwde en niet-ondertekende processen die worden uitgevoerd vanaf een USB|Blokkeren, Controleren, Niet geconfigureerd|Blokkeer niet-vertrouwde en niet-ondertekende processen die worden uitgevoerd vanaf een USB.|
|Uitvoerbare bestanden die niet voldoen aan een bepaalde gangbaarheid, ouderdom of aan criteria voor vertrouwde lijsten blokkeren|Blokkeren, Controleren, Niet geconfigureerd|Voorkomen dat uitvoerbare bestanden worden uitgevoerd tenzij deze voldoen aan een bepaalde gangbaarheid, ouderdom of criteria voor vertrouwde lijsten.|

#### <a name="controlled-folder-access"></a>Gecontroleerde mappentoegang

|              Naam van de instelling               |                                                              Instellingsopties                                                              | Description |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Mapbeveiliging (al geïmplementeerd) | Niet geconfigureerd, Inschakelen, Alleen controleren (al geïmplementeerd)<br><br> <strong>Nieuw</strong><br>Schijfwijziging blokkeren, schijfwijziging controleren |             |

Beveilig bestanden en mappen tegen niet-geautoriseerde wijzigingen door niet-goedgekeurde apps.<br><br>**Inschakelen**: voorkom dat bestanden in beveiligde mappen door niet-vertrouwde apps worden gewijzigd of verwijderd en dat gegevens door deze apps naar schijfsectoren worden weggeschreven.<br><br>
**Alleen schijfwijziging blokkeren**:<br>Voorkom dat gegevens door niet-vertrouwde apps worden weggeschreven naar schijfsectoren. Bestanden in beveiligde mappen kunnen nog steeds door niet-vertrouwde apps worden gewijzigd of verwijderd.|

## <a name="week-of-february-19-2018"></a>Week van 19 februari 2018

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Intune-ondersteuning voor meerdere Apple DEP-/Apple School Manager-accounts <!-- 747685 -->

Intune ondersteunt nu de inschrijving van apparaten uit maximaal 100 verschillende [Apple Device Enrollment Program (DEP)](device-enrollment-program-enroll-ios.md)- of [Apple School Manager](apple-school-manager-set-up-ios.md)-accounts. Elk geüpload token kan afzonderlijk worden beheerd voor registratieprofielen en -apparaten. Er kan automatisch een ander registratieprofiel worden toegewezen per geüpload DEP-/School Manager-token. Als er meerdere School Manager-tokens zijn geüpload, kan er per keer slechts één worden gedeeld met Microsoft School Data Sync.

Na de migratie werken de bèta Graph API's en gepubliceerde scripts voor het beheren van Apple DEP of ASM over Graph niet meer. Nieuwe bèta Graph API's zijn in ontwikkeling en zullen na de migratie worden uitgebracht.

#### <a name="see-enrollment-restrictions-per-user----1634444-eeready-wnready---"></a>Inschrijvingsbeperkingen per gebruiker bekijken <!-- 1634444 eeready wnready -->
Op de blade **Probleemoplossing** kunt u nu de [inschrijvingsbeperkingen](enrollment-restrictions-set.md) bekijken die gelden voor elke gebruiker. Selecteer hiervoor **Inschrijvingsbeperkingen** in de lijst **Toewijzingen**.

### <a name="device-management"></a>Apparaatbeheer
#### <a name="windows-defender-health-status-and-threat-status-reports---854704---"></a>Rapporten over de integriteitsstatus en bedreigingsstatus van Windows Defender<!--854704 -->

Inzicht in de integriteit en status van Windows Defender is essentieel voor het beheren van Windows-pc's.  Dankzij deze update worden door Intune nieuwe rapporten en acties toegevoegd aan de status en integriteit van de Windows Defender-agent. Wanneer u een rapport voor het verzamelen van de status gebruikt in de [workload voor apparaatcompatibiliteit](compliance-policy-monitor.md), worden apparaten weergegeven waarvoor een of meer van de volgende acties moeten worden uitgevoerd:
- het bijwerken van de handtekening
- Opnieuw opstarten
- handmatige interventie
- volledige scan
- interventie die is vereist voor andere agentstatussen

In een gedetailleerd rapport voor elke statuscategorie worden de afzonderlijke pc's vermeld waarvoor aandacht is vereist of die als **schoon** zijn gerapporteerd.

#### <a name="new-privacy-settings-for-device-restrictions---1308926---"></a>Nieuwe privacyinstellingen voor apparaatbeperkingen <!--1308926 -->
Er zijn [twee nieuwe privacyinstellingen](device-restrictions-windows-10.md#privacy) voor apparaten beschikbaar:
- **Gebruikersactiviteiten publiceren**: stel dit in op **Blokkeren** om gedeelde ervaringen en de detectie van recent gebruikte resources in de taakwisselaar te voorkomen.
- **Alleen lokale activiteiten**: stel dit in op **Blokkeren** om gedeelde ervaringen en de detectie van recent gebruikte resources in de taakwisselaar alleen op basis van de lokale activiteit te voorkomen.

#### <a name="new-settings-for-the-edge-browser---1469166---"></a>Nieuwe instellingen voor de Microsoft Edge-browser <!--1469166 -->
Er zijn [twee nieuwe instellingen](device-restrictions-windows-10.md#edge-browser) beschikbaar voor apparaten met de Microsoft Edge-browser: **Pad naar het bestand met favorieten** en **Wijzigingen in Favorieten**.

### <a name="app-management"></a>Appbeheer
#### <a name="protocol-exceptions-for-applications---1035509---"></a>Protocoluitzonderingen voor toepassingen <!--1035509 -->

U kunt nu uitzonderingen maken voor het gegevensoverdrachtbeleid van Intune MAM (Mobile Application Management) om specifieke onbeheerde toepassingen te openen. Dergelijke toepassingen moeten door de IT-afdeling als vertrouwde toepassingen worden beschouwd. Afgezien van de uitzonderingen die u maakt, wordt de gegevensoverdracht nog steeds beperkt tot de toepassingen die door Intune worden beheerd als uw beleid voor gegevensoverdracht is ingesteld op **Uitsluitend beheerde apps**. U kunt de beperkingen maken met behulp van protocollen (iOS) of pakketten (Android).

U kunt bijvoorbeeld het Webex-pakket toevoegen als een uitzondering op het MAM-gegevensoverdrachtbeleid. Op die manier kunnen Webex-koppelingen in een beheerd e-mailbericht van Outlook rechtstreeks in de Webex-toepassing worden geopend. De gegevensoverdracht wordt nog steeds beperkt in andere onbeheerde toepassingen. Zie [Uitzonderingen voor gegevensoverdrachtsbeleid voor apps](app-protection-policies-exception.md) voor meer informatie.

#### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Versleutelde gegevens van Windows Information Protection (WIP) in zoekresultaten van Windows <!-- 1469193 -->
Met een instelling in het WIP-beleid (Windows-gegevensbescherming) kunt u zelf regelen of met WIP versleutelde gegevens in de zoekresultaten van Windows worden opgenomen. Stel deze optie voor app-beveiligingsbeleid in door de optie **Windows Search-indexeerfunctie toestaan om versleutelde items te zoeken** te selecteren in de **geavanceerde instellingen** van het Windows-gegevensbeschermingsbeleid. Het beveiligingsbeleid van de app moet worden ingesteld op het *Windows 10*-platform en de **inschrijvingsstatus** van het app-beleid moet worden ingesteld op **Bij inschrijving**. Zie [De Windows Search-indexeerfunctie toestaan om versleutelde items te zoeken](windows-information-protection-policy-create.md#allow-windows-search-indexer-to-search-encrypted-items) voor meer informatie.

#### <a name="configuring-a-self-updating-mobile-msi-app----1740840---"></a>Een mobiele MSI-app configureren die automatisch wordt bijgewerkt <!-- 1740840 -->
U kunt een bekende mobiele MSI-app die automatisch wordt bijgewerkt configureren om de versiecontrole te negeren. Met deze functie kunt u voorkomen dat er een racevoorwaarde optreedt. Dit type racevoorwaarde kan bijvoorbeeld optreden wanneer de app die automatisch wordt bijgewerkt door de app-ontwikkelaar ook wordt bijgewerkt door Intune. Er kan door beide partijen worden geprobeerd om een versie van de app op een Windows-client af te dwingen, waardoor een conflict kan ontstaan. Voor deze automatisch bijgewerkte MSI-apps kunt u de instelling **App-versie negeren** in de blade **App-informatie** configureren. Wanneer deze instelling op **Ja** staat, negeert Microsoft Intune de app-versie die is geïnstalleerd op de Windows-client.

#### <a name="related-sets-of-app-licenses-supported-in-intune----1864117---"></a>Gerelateerde groepen van app-licenties worden in Intune ondersteund <!-- 1864117 -->
Intune in Azure Portal biedt nu ondersteuning voor de vermelding van gerelateerde groepen van app-licenties als één app-item in de gebruikersinterface. Bovendien worden apps met offlinelicenties die zijn gesynchroniseerd vanuit Microsoft Store voor Bedrijven geconsolideerd in één app-vermelding. Eventuele implementatiegegevens uit de afzonderlijke pakketten worden naar die ene vermelding gemigreerd. Als u gerelateerde groepen van app-licenties in Azure Portal wilt bekijken, selecteert u **App-licenties** op de blade **Mobiele apps**.

### <a name="device-configuration"></a>Apparaatconfiguratie
#### <a name="windows-information-protection-wip-file-extensions-for-automatic-encryption----1463582---"></a>Bestandsextensies voor automatische versleuteling door Windows-gegevensbescherming (WIP) <!-- 1463582 -->
Met een instelling in het Windows-gegevensbeschermingsbeleid (WIP) kunt u nu opgeven welke bestandsextensies automatisch worden versleuteld bij het kopiëren vanaf een Server Message Block-share (SMB) binnen het bedrijf, zoals gedefinieerd in het WIP-beleid.

#### <a name="configure-resource-account-settings-for-surface-hubs"></a>Resourceaccountinstellingen voor Surface Hubs configureren

U kunt nu resourceaccountinstellingen voor Surface Hubs extern configureren.

Het resourceaccount wordt door een Surface Hub gebruikt voor verificatie bij Exchange/Skype, zodat kan worden deelgenomen aan een vergadering.
U kunt een uniek resourceaccount maken, zodat de Surface Hub in de vergadering kan worden weergegeven als de vergaderruimte.
Bijvoorbeeld een resourceaccount als **Vergaderruimte B41/6233**.

> [!NOTE]
> - Als u velden leeg laat, overschrijft u de eerder geconfigureerde kenmerken op het apparaat.
>
> - Resourceaccounteigenschappen kunnen in de Surface Hub dynamisch worden gewijzigd. Bijvoorbeeld als wisseling van het wachtwoord is ingeschakeld. Het is dus mogelijk dat de waarden in de Azure-console pas na enige tijd in overeenstemming zijn met de waarden op het apparaat.
>
>   Om te weten wat er op dat moment op de Surface Hub is geconfigureerd, kunnen de resourceaccountgegevens in de hardware-inventaris (die al een interval van zeven dagen heeft) of als alleen-lezen eigenschappen worden opgenomen. Voor een grotere nauwkeurigheid na de uitvoering van de externe actie kunt u de status van de parameters onmiddellijk na het uitvoeren van de actie ophalen om het account/de parameters op de Surface Hub bij te werken.


##### <a name="attack-surface-reduction"></a>Kwetsbaarheid voor aanvallen verminderen


|Naam van de instelling  |Instellingsopties  |Description  |
|---------|---------|---------|
|Uitvoering van met een wachtwoord beschermde uitvoerbare inhoud uit e-mails|Blokkeren, Controleren, Niet geconfigureerd|Voorkom dat uitvoerbare bestanden met wachtwoordbescherming uit e-mails worden uitgevoerd.|
|Geavanceerde ransomwarebeveiliging|Ingeschakeld, Controleren, Niet geconfigureerd|Gebruik agressieve ransomwarebeveiliging.|
|Referentiediefstal in het Windows-subsysteem voor de lokale beveiligingsautoriteit markeren|Ingeschakeld, Controleren, Niet geconfigureerd|Markeer referentiediefstal in het Windows-subsysteem voor de lokale beveiligingsautoriteit (lsass.exe).|
|Het maken van processen met PSExec- en WMI-opdrachten|Blokkeren, Controleren, Niet geconfigureerd|Blokkeer het maken van processen die afkomstig zijn van PSExec- en WMI-opdrachten.|
|Niet-vertrouwde en niet-ondertekende processen die worden uitgevoerd vanaf een USB|Blokkeren, Controleren, Niet geconfigureerd|Blokkeer niet-vertrouwde en niet-ondertekende processen die worden uitgevoerd vanaf een USB.|
|Uitvoerbare bestanden die niet voldoen aan een bepaalde gangbaarheid, ouderdom of aan criteria voor vertrouwde lijsten blokkeren|Blokkeren, Controleren, Niet geconfigureerd|Voorkomen dat uitvoerbare bestanden worden uitgevoerd tenzij deze voldoen aan een bepaalde gangbaarheid, ouderdom of criteria voor vertrouwde lijsten.|

##### <a name="controlled-folder-access"></a>Gecontroleerde mappentoegang

|              Naam van de instelling               |                                                              Instellingsopties                                                              | Description |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Mapbeveiliging (al geïmplementeerd) | Niet geconfigureerd, Inschakelen, Alleen controleren (al geïmplementeerd)<br><br> <strong>Nieuw</strong><br>Schijfwijziging blokkeren, schijfwijziging controleren |             |

Beveilig bestanden en mappen tegen niet-geautoriseerde wijzigingen door niet-goedgekeurde apps.<br><br>**Inschakelen**: voorkom dat bestanden in beveiligde mappen door niet-vertrouwde apps worden gewijzigd of verwijderd en dat gegevens door deze apps naar schijfsectoren worden weggeschreven.<br><br>
**Alleen schijfwijziging blokkeren**:<br>Voorkom dat gegevens door niet-vertrouwde apps worden weggeschreven naar schijfsectoren. Bestanden in beveiligde mappen kunnen nog steeds door niet-vertrouwde apps worden gewijzigd of verwijderd.|

#### <a name="additions-to-system-security-settings-for-windows-10-and-later-compliance-policies---1704133--"></a>Toevoegingen aan systeembeveiligingsinstellingen voor nalevingsbeleid voor Windows 10 en hoger <!--1704133-->

Toevoegingen aan de nalevingsinstellingen voor Windows 10 zijn nu beschikbaar, waaronder het verplichte gebruik van een firewall en Windows Defender Antivirus.


### <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer
### <a name="intune-apps"></a>Intune-apps
#### <a name="support-for-offline-apps-from-the-microsoft-store-for-business---1222672--"></a>Ondersteuning voor offlineapps uit Microsoft Store voor Bedrijven <!--1222672-->
Offlineapps die u hebt gekocht in Microsoft Store voor Bedrijven worden voortaan gesynchroniseerd met Azure Portal. Vervolgens kunt u deze apps implementeren in apparaat- of gebruikersgroepen. Offlineapps worden geïnstalleerd door Intune en niet door de Store.

#### <a name="prevent-end-users-from-manually-adding-or-removing-accounts-in-the-work-profile----1728700---"></a>Hiermee voorkomt u dat eindgebruikers handmatig accounts in het werkprofiel kunnen toevoegen of uit het werkprofiel kunnen verwijderen <!-- 1728700 -->

Wanneer u de Gmail-app implementeert in een Android for Work-profiel, kunt u voorkomen dat eindgebruikers accounts handmatig aan het werkprofiel toevoegen of uit het werkprofiel verwijderen door de instelling **Accounts toevoegen en verwijderen** te gebruiken in het Android for Work-apparaatbeperkingsprofiel.

## <a name="week-of-february-5-2018"></a>Week van 5 februari 2018

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625-eeready---"></a>Nieuwe optie voor gebruikersverificatie voor bulkinschrijving met Apple <!-- 747625 eeready -->

> [!NOTE]
> Voor nieuwe tenants is deze nieuwe optie direct beschikbaar. Voor bestaande tenants wordt deze functie in april geïmplementeerd. Zolang deze implementatie nog niet is voltooid, hebt u mogelijk geen toegang tot deze nieuwe functies.

Intune biedt voor de volgende registratiemethoden de optie om apparaten te verifiëren met behulp van de bedrijfsportal-app:

- Apple Device Enrollment Program
- Apple School Manager
- Apple Configurator Enrollment

Wanneer u de bedrijfsportal-optie gebruikt, kan meervoudige verificatie van Azure Active Directory worden afgedwongen zonder deze registratiemethoden te blokkeren.

Wanneer u de bedrijfsportal-optie gebruikt, slaat Intune verificatie van gebruikers in de iOS-configuratieassistent over voor registratie op basis van gebruikersaffiniteit. Dit betekent dat het apparaat in eerste instantie wordt geregistreerd als een apparaat zonder gebruiker en derhalve geen configuraties of beleid van gebruikersgroepen ontvangt. Het apparaat ontvangt alleen configuraties en beleid voor apparaatgroepen. Intune installeert echter automatisch de bedrijfsportal-app op het apparaat. De eerste gebruiker die de bedrijfsportal-app start en zich aanmeldt, wordt in Intune aan het apparaat gekoppeld. Op dat punt ontvangt de gebruiker configuraties en beleid van zijn of haar gebruikersgroepen. De koppeling met de gebruiker kan niet worden gewijzigd zonder opnieuw te registreren.

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685-eeready---"></a>Intune-ondersteuning voor meerdere Apple DEP-/Apple School Manager-accounts <!-- 747685 eeready -->

Intune ondersteunt nu de registratie van apparaten uit maximaal 100 verschillende Apple Device Enrollment Program (DEP)- of Apple School Manager-accounts. Elk geüpload token kan afzonderlijk worden beheerd voor registratieprofielen en -apparaten. Er kan automatisch een ander registratieprofiel worden toegewezen per geüpload DEP-/School Manager-token. Als er meerdere School Manager-tokens zijn geüpload, kan er per keer slechts één worden gedeeld met Microsoft School Data Sync.

Na de migratie werken de bèta Graph API's en gepubliceerde scripts voor het beheren van Apple DEP of ASM over Graph niet meer. Nieuwe bèta Graph API's zijn in ontwikkeling en zullen na de migratie worden uitgebracht.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>Extern afdrukken via een beveiligd netwerk <!-- 1709994  -->
Met de oplossingen voor draadloos mobiel afdrukken van PrinterOn kunnen gebruikers op afstand vanaf elke locatie en op elk gewenst moment afdrukken via een beveiligd netwerk. PrinterOn wordt geïntegreerd met de Intune APP SDK voor zowel iOS als Android. U kunt app-beveiligingsbeleid toepassen op deze app via de Intune-blade **App-beveiligingsbeleid** in de beheerconsole. Eindgebruikers kunnen de app 'PrinterOn for Microsoft' downloaden via de Play Store of iTunes voor gebruik binnen hun Intune-ecosysteem.

### <a name="macos-company-portal-support-for-enrollments-that-use-the-device-enrollment-manager----1352411---"></a>Ondersteuning van de macOS-bedrijfsportal voor inschrijvingen die gebruikmaken van de apparaatinschrijvingsmanager <!-- 1352411 -->

Gebruikers kunnen nu de apparaatinschrijvingsmanager gebruiken bij het inschrijven via de macOS-bedrijfsportal.

## <a name="week-of-january-29-2018"></a>De week van 29 januari 2018

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire----1639263---"></a>Waarschuwingen voor vervallen tokens en tokens die binnenkort vervallen <!-- 1639263 -->
De overzichtspagina geeft nu waarschuwingen weer voor vervallen tokens en tokens die binnenkort vervallen. Wanneer u op een waarschuwing voor een specifiek token klikt, gaat u naar de detailpagina van dat token.  Als u op een waarschuwing met meerdere tokens klikt, gaat u naar een lijst met alle tokens met hun status. Beheerders moeten hun tokens vóór de vervaldatum vernieuwen.

### <a name="device-management"></a>Apparaatbeheer

#### <a name="remote-erase-command-support-for-macos-devices----1438084---"></a>Ondersteuning voor externe opdracht 'Wissen' voor macOS-apparaten <!-- 1438084 -->

Beheerders kunnen op afstand een opdracht voor wissen geven voor macOS-apparaten.

> [!IMPORTANT]
> De wisopdracht kan niet ongedaan worden gemaakt en moet voorzichtig worden gebruikt.

Met de wisopdracht worden alle gegevens van een apparaat verwijderd, inclusief het besturingssysteem. Hiermee wordt ook het apparaat uit Intune verwijderd. De gebruiker krijgt geen waarschuwing te zien en het verwijderen gebeurt onmiddellijk nadat de opdracht is gegeven.

U moet wel een 6-cijferige herstelpincode configureren. Deze pincode kan worden gebruikt voor het ontgrendelen van het gewiste apparaat, waarna het besturingssysteem opnieuw wordt geïnstalleerd. Nadat het verwijderen is gestart, wordt de pincode weergegeven in een statusbalk op de overzichtsblade van het apparaat in Intune. De pincode blijft intact zolang het verwijderen wordt uitgevoerd. Nadat het verwijderen is voltooid, verdwijnt het apparaat volledig uit Intune-beheer. Zorg ervoor dat u de herstelpincode vastlegt zodat degene die het apparaat terugzet deze kan gebruiken.

#### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>Licenties intrekken voor een token van het iOS-volume-aanschafprogramma<!-- 820870 -->
U kunt de licentie van alle iOS-apps uit het volume-aanschafprogramma (VPP) voor een bepaalde VPP-token intrekken.

### <a name="app-management"></a>Appbeheer

#### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>Apps uit het volume-aankoopprogramma voor iOS intrekken <!-- 820863 -->
Voor een bepaald apparaat met een of meer iOS-apps uit het volume-aankoopprogramma (VPP) kunt u de gekoppelde op een apparaat gebaseerde app-licentie voor het apparaat intrekken. Als u een app-licentie intrekt, wordt de desbetreffende VPP-app niet van het apparaat verwijderd. Als u een VPP-app wilt verwijderen, moet u de toewijzingsactie wijzigen in **Verwijderen**. Zie [iOS-apps beheren die zijn aangeschaft via een volume-aankoopprogramma met Microsoft Intune](vpp-apps-ios.md) voor meer informatie.

#### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Mobiele apps van Office 365 toewijzen aan iOS- en Android-apparaten met behulp van de ingebouwde app-type<!-- 1332318 -->
Het **ingebouwde** app-type maakt het eenvoudiger voor u om Office 365-apps te maken en toe te wijzen aan door u beheerde iOS- en Android-apparaten. Deze apps zijn onder andere 0365-apps, zoals Word, Excel, PowerPoint en OneDrive. U kunt specifieke apps toewijzen aan het app-type en de configuratie van de app-gegevens bewerken.

#### <a name="including-and-excluding-app-assignment-based-on-groups----1406920---"></a>App-toewijzing opnemen en uitsluiten op basis van groepen <!-- 1406920 -->

Tijdens toewijzing van een app en na het selecteren van een toewijzingstype, kunt u selecteren welke groepen u wilt opnemen en welke u wilt uitsluiten.

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="you-can-assign-an-application-configuration-policy-to-groups-by-including-and-excluding-assignments-----1480316---"></a>U kunt een toepassingsconfiguratiebeleid toewijzen aan groepen door toewijzingen op te nemen en uit te sluiten <!-- 1480316 -->

U kunt een toepassingsconfiguratiebeleid toewijzen aan een groep gebruikers en apparaten met behulp van een combinatie van opgenomen en uitgesloten toewijzingen. U kunt toewijzingen kiezen als een aangepaste selectie groepen of als afzonderlijke groep. Een virtuele groep kan **Alle gebruikers**, **Alle apparaten** of **Alle gebruikers + alle apparaten** bevatten.

#### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Ondersteuning voor het editie-upgradebeleid voor Windows 10   <!-- 903672(archived), 1119689 -->  
U kunt een editie-upgradebeleid voor Windows 10 maken dat Windows 10-apparaten upgradet naar Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education en Windows 10 Professional Education N. Raadpleeg [Editie-upgrades voor Windows 10 configureren](edition-upgrade-configure-windows-10.md) voor meer informatie over editie-upgrades voor Windows 10.

#### <a name="conditional-access-policies-for-intune-is-only-available-from-the-azure-portal-----1737088-1634311---"></a>Beleid voor voorwaardelijke toegang voor Intune is alleen beschikbaar vanuit Azure Portal <!-- 1737088 1634311 -->

Vanaf deze versie moet u uw beleid voor voorwaardelijke toegang configureren en beheren in het [Azure Portal](https://portal.azure.com) via **Azure Active Directory** > **Voorwaardelijke toegang**. Voor uw gemak hebt u ook toegang tot deze blade vanuit Intune in Azure Portal via **Intune** > **Voorwaardelijke toegang**.

#### <a name="updates-to-compliance-emails---1637547---"></a>Updates voor e-mailberichten over naleving <!--1637547 -->

Wanneer er een e-mailbericht wordt verzonden om een niet-compatibel apparaat te melden, worden daarin gegevens over het niet-compatibele apparaat opgenomen.


## <a name="week-of-january-22-2018"></a>De week van 22 januari 2018

### <a name="intune-apps"></a>Intune-apps

#### <a name="new-functionality-for-the-resolve-action-for-android-devices---1583480--"></a>Nieuwe functionaliteit voor de actie 'Oplossen' voor Android-apparaten <!--1583480-->

De bedrijfsportal-app voor Android breidt de actie 'Oplossen' uit voor **Apparaatinstellingen bijwerken** om [problemen met de versleuteling van het apparaat](/intune-user-help/encrypt-your-device-android) op te lossen.

#### <a name="remote-lock-available-in-company-portal-app-for-windows-10---676506--"></a>Externe vergrendeling is beschikbaar in de bedrijfsportal-app voor Windows 10<!--676506-->
Eindgebruikers kunnen nu in de bedrijfsportal-app voor Windows 10 hun apparaten extern vergrendelen. Dit wordt niet weergegeven voor het lokale apparaat dat op dat moment wordt gebruikt.

#### <a name="easier-resolution-of-compliance-issues-for-the-company-portal-app-for-windows-10---676546--"></a>Eenvoudigere oplossing van problemen met naleving voor de bedrijfsportal-app voor Windows 10 <!--676546-->
Eindgebruikers met Windows-apparaten kunnen tikken op de reden van niet-naleving in de bedrijfsportal-app. Indien mogelijk worden ze hiermee rechtstreeks naar de juiste locatie geleid in de instellingen-app om het probleem te verhelpen.

## <a name="week-of-december-11-2017"></a>Week van 11 december 2017

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="new-automatic-redeployment-setting----1469168---"></a>Nieuwe instelling voor automatisch opnieuw implementeren <!-- 1469168 -->
De instelling **Automatisch opnieuw implementeren** maakt het mogelijk dat gebruikers met beheerdersrechten alle gebruikersgegevens en -instellingen verwijderen met **CTRL + Win + R** op het vergrendelingsscherm van het apparaat. Het apparaat wordt automatisch opnieuw geconfigureerd en opnieuw ingeschreven bij het beheer. U vindt deze instelling onder Windows 10 > Apparaatbeperkingen > Algemeen > Automatisch opnieuw installeren. Zie [Intune-apparaatbeperkingsinstellingen voor Windows 10](device-restrictions-windows-10.md#general) voor meer informatie.

#### <a name="support-for-additional-source-editions-in-the-windows-10-edition-upgrade-policy-----903672--1119689---"></a>Ondersteuning voor extra bronedities in het beleid voor editie-upgrades voor Windows 10<!-- 903672,  1119689 -->
U kunt nu het beleid voor editie-upgrades voor Windows 10 gebruiken om een upgrade uit te voeren voor extra edities van Windows 10 (Windows 10 Pro, Windows 10 Pro Education, Windows 10 Cloud, enzovoort). Vóór deze release waren de ondersteunde editie-upgradepaden beperkter. Zie [Editie-upgrades voor Windows 10 configureren](edition-upgrade-configure-windows-10.md) voor meer informatie.

#### <a name="new-windows-defender-security-center-wdsc-device-configuration-profile-settings----1335507---"></a>Nieuwe profielinstellingen voor apparaatconfiguratie voor Windows Defender Security Center (WDSC) <!-- 1335507 -->

Intune voegt een nieuwe sectie toe in de profielinstellingen voor apparaatconfiguratie onder de eindpuntbeveiliging genaamd **Windows Defender Security Center**. IT-beheerders kunnen configureren tot welke onderdelen van de Windows Defender Security Center-app eindgebruikers toegang hebben. Als een IT-beheerder een onderdeel verbergt in de Windows Defender Security Center-app, worden alle meldingen die betrekking hebben op het verborgen onderdeel, niet weergeven op het apparaat van de gebruiker.

De volgende onderdelen kunnen worden verborgen in de profielinstellingen voor apparaatconfiguratie van Windows Defender Security Center:
- Virus- en bedreigingsbeveiliging
- Prestaties en status van apparaat
- Firewall- en netwerkbeveiliging
- App- en browserbeheer
- Gezinsopties

IT-beheerders kunnen ook aanpassen welke meldingen gebruikers ontvangen. U kunt bijvoorbeeld configureren of de gebruikers alle meldingen ontvangen die worden gegenereerd door zichtbare onderdelen in het WDSC of alleen kritieke meldingen. Niet-kritieke meldingen zijn bijvoorbeeld periodieke samenvattingen van Windows Defender Antivirus-activiteiten en meldingen wanneer scans zijn voltooid. Alle andere meldingen worden beschouwd als kritiek. Daarnaast kunt u ook de inhoud van meldingen zelf aanpassen. U kunt bijvoorbeeld contactgegevens van de IT-afdeling toevoegen aan meldingen die worden weergegeven op apparaten van gebruikers.

#### <a name="multiple-connector-support-for-scep-and-pfx-certificate-handling----1361755---"></a>Ondersteuning voor meerdere connectoren voor het verwerken van SCEP- en PFX-certificaten <!-- 1361755 -->

Klanten die de on-premises NDES-connector gebruiken om certificaten aan apparaten te leveren, kunnen nu meerdere connectoren in één tenant configureren.

Deze nieuwe mogelijkheid biedt ondersteuning voor het volgende scenario:

- **Hoge beschikbaarheid**

Elke NDES-connector haalt certificaataanvragen uit Intune op.  Als één NDES-connector offline gaat, kan de andere connector aanvragen blijven verwerken.

#### <a name="customer-subject-name-can-use-aaddeviceid-variable-----1468599---"></a>Aangepaste onderwerpnaam kan de AAD_DEVICE_ID-variabele <!-- 1468599 --> gebruiken

Wanneer u een SCEP-certificaatprofiel in Intune maakt, kunt u nu de AAD_DEVICE_ID-variabele gebruiken bij het samenstellen van de aangepaste onderwerpnaam.   Wanneer het certificaat wordt aangevraagd via dit SCEP-profiel, wordt de variabele vervangen door de AAD-apparaat-id van het apparaat dat de certificaataanvraag doet.


### <a name="device-management"></a>Apparaatbeheer

#### <a name="manage-jamf-enrolled-macos-devices-with-intunes-device-compliance-engine----1592747---"></a>Via Jamf ingeschreven macOS-apparaten beheren met de Intune-engine voor apparaatnaleving<!-- 1592747 -->
U kunt nu Jamf gebruiken om statusinformatie over macOS-apparaten naar Intune te sturen, waarna het apparaat wordt geëvalueerd op naleving van het beleid dat is gedefinieerd in de Intune-console. Op basis van de nalevingsstatus van het apparaat en van andere omstandigheden (zoals locatie, gebruikersrisico en dergelijke) dwingt voorwaardelijke toegang naleving af voor macOS-apparaten die toegang hebben tot toepassingen in de cloud en on-premises die zijn verbonden met Azure AD, met inbegrip van Office 365. Meer informatie over [integratie met Jamf instellen](conditional-access-integrate-jamf.md) en [afdwingen van naleving voor door Jamf beheerde apparaten](conditional-access-assign-jamf.md).

#### <a name="new-ios-device-action------1424701---"></a>Nieuwe actie voor iOS-apparaten <!-- 1424701 -->

U kunt nu door iOS 10.3 gecontroleerde apparaten afsluiten. Deze actie sluit het apparaat direct af zonder waarschuwing voor de eindgebruiker. U vindt de actie **Afsluiten (alleen gecontroleerd)** in de apparaateigenschappen wanneer u een apparaat selecteert in de werkbelasting **Apparaat**.

#### <a name="disallow-datetime-changes-to-samsung-knox-devices----1468103---"></a>Geen datum-/tijdwijzigingen voor Samsung Knox-apparaten toestaan <!-- 1468103 -->

We hebben een nieuwe functie toegevoegd waarmee u datum- en tijdwijzigingen op Samsung Knox-apparaten kunt blokkeren. U kunt dit vinden in **Apparaatconfiguratieprofielen** > **Apparaatbeperkingen (Android)** > **Algemeen**.

#### <a name="surface-hub-resource-account-supported----1566442----"></a>Resource-account voor Surface Hub ondersteund <!-- 1566442  -->

Er is een nieuwe apparaatactie toegevoegd, zodat beheerders het resource-account dat is gekoppeld aan een Surface Hub, kunnen definiëren en bijwerken.

Het resource-account wordt door een Surface Hub gebruikt voor verificatie bij Exchange/Skype, zodat kan worden deelgenomen aan een vergadering. U kunt een uniek resource-account maken, zodat de Surface Hub als vergaderruimte wordt weergegeven in de vergadering. Het resource-account kan bijvoorbeeld worden weergegeven als *Vergaderzaal B41/6233*. Het resource-account (ook wel het apparaataccount genoemd) voor de Surface Hub moet meestal worden geconfigureerd voor de locatie van de vergaderruimte en wanneer andere parameters van het resource-account moeten worden gewijzigd.

Wanneer beheerders het resource-account op een apparaat willen bijwerken, moeten ze de huidige referenties voor Active Directory/Azure Active Directory voor het apparaat opgeven. Als wisseling van het wachtwoord is ingeschakeld voor het apparaat, moeten beheerders het wachtwoord zoeken in Azure Active Directory.

> [!NOTE]
> Alle velden in een bundel worden verzonden en overschrijven alle velden die eerder zijn geconfigureerd. Lege velden overschrijven ook bestaande velden.

Beheerders kunnen de volgende instellingen configureren:

- **Resource-account**
   - **Active Directory-gebruiker**

      Domeinnaam\gebruikersnaam of UPN (Principle-naam van gebruiker):user@domainname.com

   - **Wachtwoord**

- **Optionele parameters voor het resource-account** (moeten worden ingesteld met het opgegeven resource-account)

   - **Periode voor de wisseling van het wachtwoord**

     Zorgt ervoor dat het accountwachtwoord uit veiligheidsoverwegingen elke week automatisch wordt bijgewerkt door de Surface Hub. Als u parameters wilt configureren nadat dit is ingeschakeld, moet eerst het wachtwoord voor het account in Azure Active Directory opnieuw worden ingesteld.

   - **SIP-adres (Session Initiation Protocol)**

     Wordt alleen gebruikt als automatische detectie mislukt.

   - **E-mail**

     Het e-mailadres van het apparaat-/resource-account.

   - **Exchange-server**

     Alleen vereist wanneer automatische detectie mislukt.

   - **Agendasynchronisatie**

     Hiermee geeft u op of agendasynchronisatie en andere Exchange Server-services zijn ingeschakeld. Bijvoorbeeld: synchronisatie van vergaderingen.

#### <a name="install-office-apps-on-macos-devices----1494311---"></a>Office-apps installeren op macOS-apparaten <!-- 1494311 -->
U kunt nu Office-apps installeren op macOS-apparaten. Met dit nieuwe app-type kunt u Word, Excel, PowerPoint, Outlook en OneNote installeren. Deze apps worden ook geleverd met Microsoft AutoUpdate (MAU) om te zorgen dat uw apps veilig en up-to-date blijven.

### <a name="app-management"></a>Appbeheer

#### <a name="delete-an-ios--volume-purchasing-program-token----820879---"></a>Een token van het iOS-volume-aanschafprogramma verwijderen <!-- 820879 -->
U kunt het token van het iOS-volume-aanschafprogramma (VPP) verwijderen via de console. Dit kan nodig zijn als er dubbele exemplaren van een VPP-token zijn.

### <a name="intune-apps"></a>Intune-apps


### <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer

#### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1667026---"></a>De nieuwe entiteitverzameling Huidige gebruiker is beperkt tot gegevens van actieve gebruikers <!-- 1667026 -->

De entiteitverzameling **Gebruiker** bevat alle Azure Active Directory-gebruikers (Azure AD) met toegewezen licenties in uw onderneming. Een gebruiker kan bijvoorbeeld worden toegevoegd aan Intune en vervolgens ergens gedurende de afgelopen maand zijn verwijderd. Ook al is deze gebruiker niet aanwezig op het moment dat het rapport wordt gegenereerd, toch zijn de gebruiker en de status aanwezig in de gegevens. U kunt een rapport maken dat de duur van de historische aanwezigheid van de gebruiker in uw gegevens weergeeft.

Daarentegen bevat de nieuwe entiteitverzameling **Huidige gebruiker** alleen gebruikers die niet zijn verwijderd. De entiteitverzameling **Huidige gebruiker** bevat alleen gebruikers die momenteel actief zijn. Zie [Naslaginformatie voor huidige gebruikersentiteit](reports-ref-current-user.md) voor informatie over de entiteitverzameling **Huidige gebruiker**.


### <a name="updated-graph-apis----1736360---"></a>Bijgewerkte Graph API's <!-- 1736360 -->

We hebben in deze release enkele Graph API's voor Intune bijgewerkt die nog in de bètafase zijn. Bekijk de maandelijkse [Graph API changelog](https://developer.microsoft.com/graph/docs/concepts/changelog) voor meer informatie.

## <a name="week-of-december-4-2017"></a>Week van 4 december 2017

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="intune-supports-windows-information-protection-wip-denied-apps----1479103---"></a>Intune biedt ondersteuning voor door Windows Information Protection (WIP) geweigerde apps <!-- 1479103 -->
U kunt geweigerde apps opgeven in Intune. Als een app wordt geweigerd, heeft deze geen toegang tot zakelijke gegevens. Dit is dus eigenlijk het tegenovergestelde van de lijst met toegestane apps. Zie [Aanbevolen lijst voor weigeren voor Windows Information Protection](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp?f=255&MSPPError=-2147217396#recommended-deny-list-for-windows-information-protection) voor meer informatie.


## <a name="week-of-november-27-2017"></a>Week van 27 november 2017

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="troubleshoot-enrollment-issues-----746324---"></a>Inschrijvingsproblemen oplossen <!-- 746324 -->

De werkruimte **Problemen oplossen** toont problemen met gebruikersinschrijving. Details over het probleem en voorgestelde herstelstappen kunnen beheerders en helpdeskmedewerkers helpen problemen op te lossen. Bepaalde inschrijvingsproblemen worden niet vastgelegd en voor sommige fouten zijn er misschien geen herstelvoorstellen.

#### <a name="group-assigned-enrollment-restrictions----747598---"></a>Beperkingen aan groepen toegewezen inschrijving <!-- 747598 -->

Als Intune-beheerder kunt u de [aangepaste inschrijvingsbeperkingen Apparaattype en Apparaatlimiet maken voor gebruikersgroepen](enrollment-restrictions-set.md).

Met de Intune Azure Portal kunt u maximaal 25 exemplaren van elk beperkingstype maken die vervolgens kunnen worden toegewezen aan gebruikersgroepen. Aan groepen toegewezen beperkingen overschrijven de standaardbeperkingen.

Alle exemplaren van een beperkingstype worden bijgehouden in een strikt geordende lijst. Deze volgorde bepaalt een prioriteitswaarde voor conflictoplossing. Een gebruiker die getroffen is door meer dan één beperkingsexemplaar wordt alleen beperkt door het exemplaar met de hoogste prioriteitswaarde. U kunt de prioriteit van een bepaald exemplaar wijzigen door dit naar een andere positie in de lijst te slepen.

Deze functionaliteit wordt vrijgegeven met de migratie van Android for Work-instellingen van het menu Android for Work-inschrijving naar het menu Inschrijvingsbeperkingen. Aangezien deze migratie enkele dagen kan duren, kan uw account worden bijgewerkt ten aanzien van andere onderdelen van de release van november voordat u ziet dat groepstoewijzing wordt ingeschakeld voor Inschrijvingsbeperkingen.

#### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors----1528104---"></a>Ondersteuning voor meerdere connectors voor de Network Device Enrollment-service (NDES)<!-- 1528104 -->

Met de NDES kunnen mobiele apparaten die zonder domeinreferenties worden uitgevoerd certificaten verkrijgen op basis van het Simple Certificate Enrollment Protocol (SCEP).
Dankzij deze update worden meerdere NDES-connectors ondersteund.

#### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731-eeready--"></a>Android for Work-apparaten onafhankelijk van de Android-apparaten beheren<!-- 1490731 EEready-->

Intune ondersteunt het inschrijvingsbeheer voor Android for Work-apparaten onafhankelijk van het Android-platform. Deze instellingen worden beheerd onder **Apparaatinschrijving** > **Inschrijvingsbeperkingen** > **Apparaattypebeperkingen**. (Ze bevonden zich eerder onder **Apparaatinschrijving** > **Android for Work-inschrijving** > **Android for Work-inschrijvingsinstellingen**.)

Standaard zijn instellingen voor uw Android for Work-apparaten gelijk aan de instellingen voor uw Android-apparaten. Wanneer u echter uw Android for Work-instellingen wijzigt, is dat niet meer het geval.

Als u een persoonlijke Android for Work-inschrijving blokkeert, kunnen alleen zakelijke Android-apparaten worden ingeschreven als Android for Work.

Bedenk de volgende punten wanneer u met de nieuwe instellingen werkt:

##### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Als u nog nooit een Android for Work-inschrijving hebt toegevoegd

Het nieuwe Android for Work-platform wordt geblokkeerd in de standaard apparaattypebeperkingen. Wanneer u de functie toevoegt, kunt u de Android for Work-inschrijving van apparaten toestaan. Hiervoor wijzigt u de standaardinstelling of maakt u een nieuwe apparaattypebeperking ter vervanging van de standaard apparaattypebeperking.

##### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Als u de Android for Work-inschrijving hebt toegevoegd

Als u dit al eerder hebt gedaan, is uw situatie afhankelijk van de instelling die u hebt gekozen:

| Instelling | De status van Android for Work bij een standaard apparaattypebeperking | Opmerkingen |
| --- | --- | --- |
| **Alle apparaten beheren als Android** | Geblokkeerd | U mag geen Android-apparaten bij Android for Work hebben ingeschreven. |
| **Ondersteunde apparaten beheren als Android for Work** | Toegestaan | Alle Android-apparaten die ondersteuning bieden voor Android for Work moeten zijn ingeschreven bij Android for Work. |
| **Alleen ondersteunde apparaten voor de gebruikers in deze groepen beheren als Android for Work** | Geblokkeerd | Er is een afzonderlijk beleid voor apparaattypebeperkingen gemaakt om de standaardinstelling te overschrijven. Dit beleid bepaalt de groepen die u eerder hebt geselecteerd om Android for Work-inschrijving toe te staan. Gebruikers binnen de geselecteerde groepen mogen hun Android for Work-apparaten blijven inschrijven. Alle andere gebruikers worden uitgesloten van inschrijving bij Android for Work. |

In alle gevallen blijft uw beoogde regel behouden. Er is geen actie vereist van uw kant om de globale of groepsgewijze toestemming voor Android for Work in uw omgeving te handhaven.

### <a name="app-management"></a>Appbeheer

#### <a name="app-install-report-updated-to-include-install-pending-status----1249446---"></a>Het statusrapport van de app-installatie wordt bijgewerkt met de status Installatie in behandeling <!-- 1249446 -->  

Het **Statusrapport van de app-installatie**, dat toegankelijk is voor elke app via de **App**-lijst in de **Mobiele apps**-workload, bevat nu **Installatie in behandeling** voor gebruikers en apparaten.

#### <a name="ios-11-app-inventory-api-for-mobile-threat-detection----1391759---"></a>API iOS 11-app-inventaris voor mobiele detectie van dreigingen (MTD) <!-- 1391759 -->

Intune verzamelt informatie over de app-inventaris van apparaten in zowel privé- als bedrijfseigendom en maakt deze informatie beschikbaar voor MTD-providers om op te halen, zoals Lookout for Work. U kunt de app-inventaris verzamelen van gebruikers van iOS 11+-apparaten.

**App-inventaris**  
Inventarissen van iOS 11 +-apparaten in zowel bedrijfs- en privé-eigendom worden verzonden naar uw MTD-serviceprovider. Gegevens in de app-inventarisatie bestaan onder andere uit:

 - App-id
 - App-versie
 - Verkorte App-versie
 - App-naam
 - Grootte van de App-bundel
 - Dynamische grootte van de App
 - App is wel of niet gevalideerd
 - App is wel of niet beheerd


### <a name="device-management"></a>Apparaatbeheer

#### <a name="migrate-hybrid-mdm-users-and-devices-to-intune-standalone----1463747-wnready---"></a>Hybride MDM-gebruikers en -apparaten migreren naar Intune (zelfstandig)<!-- 1463747 wnready -->
Er zijn nu nieuwe processen en hulpprogramma's beschikbaar om in Azure Portal gebruikers en hun apparaten van hybride MDM naar Intune te verplaatsen, zodat u het volgende kunt doen:
- In Azure Portal beleidsregels en profielen van de Configuration Manager-console naar Intune kopiëren
- In Azure Portal een subset gebruikers naar Intune verplaatsen, terwijl de rest in hybride MDM blijft
- In Azure Portal apparaten naar Intune migreren zonder dat u ze opnieuw hoeft te registreren

Zie [Hybride MDM-gebruikers en -apparaten migreren naar Intune (zelfstandig)](https://docs.microsoft.com/sccm/mdm/deploy-use/migrate-hybridmdm-to-intunesa) voor meer informatie.

#### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Hoge beschikbaarheid van on-premises Exchange Connector  <!-- 676614 -->
Nadat de Exchange Connector verbinding met Exchange heeft gemaakt met behulp van de opgegeven CAS, kan de connector nu andere CAS-instanties detecteren. Als de primaire CAS niet beschikbaar is, zoekt de connector naar een andere CAS (indien beschikbaar) totdat de primaire CAS beschikbaar komt. Zie [Hoge beschikbaarheid van on-premises Exchange Connector](exchange-connector-install.md#on-premises-exchange-connector-high-availability-support) voor meer informatie.

#### <a name="remotely-restart-ios-device-supervised-only----1424595---"></a>iOS-apparaat op afstand opnieuw opstarten (alleen onder supervisie)<!-- 1424595 -->

U kunt een iOS 10.3 +-apparaat onder supervisie activeren om via een apparaatactie opnieuw op te starten. Zie voor meer informatie over het gebruik van de actie voor het opnieuw opstarten van het apparaat [Apparaten op afstand opnieuw opstarten met Intune](device-restart.md).

> [!Note]
> Deze opdracht vereist toegangsrechten tot apparaten onder supervisie en **Apparaatvergrendeling**. Het apparaat wordt onmiddellijk opnieuw opgestart. Met een toegangscode vergrendelde iOS-apparaten wordt niet opnieuw verbonden met een Wi-Fi-netwerk na opnieuw te zijn opgestart; na opnieuw te zijn opgestart kunnen deze mogelijk niet communiceren met de server.

#### <a name="single-sign-on-support-for-ios----1333645---"></a>Ondersteuning voor Eenmalige aanmelding voor iOS<!-- 1333645 -->  

U kunt Eenmalige aanmelding voor iOS-gebruikers gebruiken. De iOS-apps die zijn gecodeerd om naar de gebruikersreferenties te zoeken in de Eenmalige aanmelding-payload zijn functioneel voor de update van de payloadconfiguratie. U kunt ook de UPN en de Intune-apparaat-id gebruiken om de Principal-naam en de Realm te configureren. Zie [Intune configureren voor eenmalige aanmelding vanaf iOS-apparaten](sso-ios.md) voor meer informatie.

#### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Mijn iPhone vinden toevoegen voor privéapparaten<!--1427287-->
U kunt nu bekijken of bij iOS-apparaten Activeringsslot is ingeschakeld. Deze functie was eerder te vinden in de klassieke portal in Intune.


#### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Beheerde macOS-apparaten op afstand vergrendelen met Intune<!-- 1437691 -->

U kunt een verloren Mac OS-apparaat vergrendelen en een 6-cijferige pincode voor wachtwoordherstel instellen. Als het apparaat is vergrendeld, toont de blade **Apparaatoverzicht** de pincode totdat een andere apparaatactie wordt verzonden.

Zie voor meer informatie [Beheerde apparaten op afstand vergrendelen met Intune](device-remote-lock.md).

#### <a name="new-scep-profile-details-supported----1559808---"></a>Nieuwe SCEP-profielgegevens ondersteund<!-- 1559808 -->

Beheerders kunnen aanvullende instellingen configureren bij het maken van een SCEP-profiel op Windows-, iOS-, Mac OS- en Android-platformen.  Beheerders kunnen het IMEI-nummer, het serienummer of de algemene naam met inbegrip van e-mail in de indeling van de onderwerpnaam instellen.

<!-- #### Update to what device details your company may see -1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources. -->

#### <a name="retain-data-during-a-factory-reset----1588489---"></a>Gegevens behouden tijdens fabrieksinstellingen terugzetten <!--1588489 -->
Wanneer Windows 10 versie 1709 en later naar de fabrieksinstellingen wordt hersteld, is een nieuwe functie beschikbaar. Beheerders kunnen opgeven of apparaatinschrijving en andere ingerichte gegevens worden bewaard op een apparaat via fabrieksinstellingen terugzetten.

De volgende gegevens wordt behouden via fabrieksinstellingen terugzetten:
- Gebruikersaccounts die zijn gekoppeld aan het apparaat
- Status van de machine (lid van domein, lid van Azure Active Directory)
- MDM-inschrijving
- Door OEM geïnstalleerde apps (Store- en Win32-apps)
- Gebruikersprofiel
- Gebruikersgegevens buiten het gebruikersprofiel
- Autologon gebruiker

De volgende gegevens blijven niet behouden:
- Gebruikersbestanden
- Door de gebruiker geïnstalleerde apps (Store- en Win32-apps)
- Niet-standaard apparaatinstellingen

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen
#### <a name="window-10-update-ring-assignments-are-displayed----1621837---"></a>Er worden toewijzingen voor de Windows 10-updatering weergegeven <!-- 1621837 -->
Wanneer u bezig bent met de **probleemoplossing** voor de door u weergegeven gebruiker, kunt u eventuele toewijzingen voor de Windows 10-updatering zien.  

#### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings-----1455974----"></a>Frequentie-instellingen van rapporten van Windows Defender Advanced Threat Protection <!-- 1455974  -->
Met de service Windows Defender Advanced Threat Protection (WDATP) kunnen beheerders de rapportagefrequentie voor beheerde apparaten beheren. Met de nieuwe optie **Frequentie van telemetrierapporten versnellen** verzamelt vaker WDATP gegevens en beoordeelt vaker risico's. De standaardwaarde voor rapportage zorgt voor optimale snelheid en prestaties. Het verhogen van de rapportagefrequentie kan waardevol zijn voor apparaten met een hoog risico. Deze instelling kunt u vinden in het **Windows Defender ATP**-profiel in **Apparaatconfiguraties**.

#### <a name="audit-updates----1412961---"></a>Updates controleren<!-- 1412961 -->  
Controles van Intune biedt een record van de wijzigingsbewerkingen ten aanzien van Intune.  Alle taakbewerkingen voor maken, bijwerken, verwijderen en externe taakbewerkingen worden vastgelegd en een jaar bewaard.  De Azure Portal voorziet in een weergave van de controlegegevens van laatste 30 dagen in elke workload, welke gefilterd kan worden.  Met de bijbehorende Graph API kunt u de controlegegevens ophalen die het afgelopen jaar zijn bewaard.

Controles zijn te vinden onder de groep **CONTROLE**. Er is een menu-item **Controlelogboeken** voor elke workload.




## <a name="week-of-november-20-2017"></a>Week van 20 november 2017

### <a name="app-management"></a>Appbeheer

#### <a name="google-play-protect-support-on-android----908720---"></a>Ondersteuning van Google Play Protect op Android <!-- 908720 -->

Google introduceert tegelijkertijd met Android Oreo een reeks beveiligingsfuncties met de naam Google Play Protect waarmee gebruikers en organisaties beveiligde apps en beveiligde Android-installatiekopieën kunnen uitvoeren. Intune ondersteunt de functies van Google Play Protect, inclusief SafetyNet voor externe verklaringen. Beheerders kunnen eisen voor een nalevingsbeleid instellen die vereisen dat Google Play Protect wordt geconfigureerd en in orde is.
De instelling **SafetyNet-apparaatverklaring** vereist dat het apparaat verbinding maakt met een service van Google om te controleren of het apparaat in orde is en er niet mee is geknoeid. Beheerders kunnen tevens een configuratieprofielinstelling voor Android for Work instellen om te vereisen dat geïnstalleerde apps worden geverifieerd met behulp van Google Play-services. Als een apparaat niet aan de eisen van Google Play Protect voldoet, kan voorwaardelijke toegang de toegang van gebruikers tot bedrijfsbronnen blokkeren.

- Meer informatie over [het maken van een nalevingsbeleid voor apparaten om Google Play Protect in te schakelen](https://docs.microsoft.com/intune/compliance-policy-create-google-play-protect).

#### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Tekstprotocol toegestaan vanuit beheerde Apps<!-- 1414050  -->

Met apps die worden beheerd door de Intune App SDK kunnen SMS-berichten worden verzonden.

## <a name="week-of-november-13-2017"></a>Week van 13 november 2017

### <a name="intune-apps"></a>Intune-apps
#### <a name="company-portal-app-for-macos-is-available---1541700--"></a>De bedrijfsportal-app voor macOS is beschikbaar <!--1541700-->
De Intune-bedrijfsportal op macOS is bijgewerkt en geoptimaliseerd, zodat alle informatie en nalevingsmeldingen die uw gebruikers nodig hebben voor alle apparaten die ze hebben ingeschreven, overzichtelijk wordt weergegeven. En als de Intune-bedrijfsportal eenmaal is geïmplementeerd op een apparaat, zorgt Microsoft AutoUpdate voor macOS voor de updates. U kunt de nieuwe Intune-bedrijfsportal voor macOS downloaden door u aan te melden bij de website van de Intune-bedrijfsportal vanaf een macOS-apparaat.

#### <a name="microsoft-planner-is-now-part-of-the-mobile-app-management-mam-list-of-approved-apps-----1248473---"></a>Microsoft Planner maakt nu deel uit van de MAM-lijst (beheer van mobiele apps) met goedgekeurde apps <!-- 1248473 -->
De app Microsoft Planner voor iOS en Android maakt nu deel uit van de goedgekeurde apps voor Mobile App Management (MAM). De app kan via de blade Intune-app-beveiliging in Azure Portal worden geconfigureerd voor alle tenants.
- Meer informatie over de [MAM-lijst met goedgekeurde apps](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

#### <a name="per-app-vpn-requirement-update-frequency-on-ios-devices------1547061---"></a>Vereiste updatefrequentie voor VPN per app op iOS-apparaten <!-- 1547061 -->  
Beheerders kunnen nu de vereisten voor VPN per app verwijderen voor apps op iOS-apparaten. Dit wordt toegepast op de betreffende apparaten na de eerstvolgende check-in bij Intune, gewoonlijk binnen 15 minuten.  

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen
#### <a name="support-for-system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Ondersteuning van management pack van System Center Operations Manager voor Exchange Connector <!-- 885457 -->
Het management pack van System Center Operations Manager (SCOM) voor Exchange Connector is nu beschikbaar om de logboeken van Exchange Connector te parseren. Hiermee kunt u de service op verschillende manieren controleren wanneer u problemen moet oplossen.

## <a name="week-of-november-6-2017"></a>Week van 6 november 2017

### <a name="device-enrollment"></a>Apparaatinschrijving
#### <a name="co-management-for-windows-10-devices-----1243445---"></a>Co-management voor Windows 10-apparaten <!-- 1243445 -->
Co-management is een oplossing die een brug slaat tussen traditioneel en modern beheer en het biedt een gefaseerde benadering om de overstap te maken. Co-management is in feite een oplossing waarbij Windows 10-apparaten gelijktijdig worden beheerd door Configuration Manager en Microsoft Intune en zijn gekoppeld aan Active Directory (AD) en Azure Active Directory (Azure AD).  Deze configuratie geeft u een manier om mettertijd te moderniseren, in een tempo dat geschikt is voor uw organisatie als u niet allemaal tegelijk kunt overstappen.  

#### <a name="restrict-windows-enrollment-by-os-version----245498---"></a>Windows-inschrijving beperken door de versie van het besturingssysteem <!-- 245498 -->
Als Intune-beheerder kunt u een minimale en maximale versie opgeven van Windows 10 voor de inschrijving van apparaten. U kunt deze beperkingen instellen op de blade **Platformconfiguraties**.

Intune blijft ondersteuning bieden voor registratie Windows 8.1-pc's en -telefoons. U kunt echter alleen minimale en maximale versies instellen voor Windows 10-versies. Als u de inschrijving van 8.1-apparaten wilt toestaan, laat u de minimale versie leeg.

#### <a name="alerts-for-windows-autopilot-unassigned-devices-----1631236---"></a>Waarschuwingen voor niet-toegewezen Windows AutoPilot-apparaten <!-- 1631236 -->
Er is een nieuwe waarschuwing voor niet-toegewezen Windows AutoPilot-apparaten op de pagina **Microsoft Intune** > **Apparaatinschrijving** > **Overzicht**. Deze waarschuwing geeft aan voor hoeveel apparaten van het AutoPilot-programma geen AutoPilot-implementatieprofielen zijn toegewezen. Aan de hand van de informatie in de waarschuwing kunt u profielen maken en deze toewijzen aan de niet-toegewezen apparaten. Als u op de waarschuwing klikt, verschijnt een volledige lijst met Windows AutoPilot-apparaten en gedetailleerde informatie. Zie [Windows-apparaten inschrijven met het Windows AutoPilot Deployment-programma](https://docs.microsoft.com/intune/enrollment-autopilot) voor meer informatie.

### <a name="device-management"></a>Apparaatbeheer

#### <a name="refresh-button-for-devices-list-------1333581---"></a>Knop voor het vernieuwen van de lijst met apparaten    <!-- 1333581 -->
Omdat de lijst met apparaten niet automatisch wordt vernieuwd, kunt u de nieuwe knop gebruiken om de apparaten bij te werken die worden weergegeven in de lijst.

#### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Ondersteuning voor Symantec Cloud Certification Authority (CA)  <!-- 1333638 -->    
Intune ondersteunt nu Symantec Cloud CA, die de Intune Certificate Connector in staat stelt PKCS-certificaten van Symantec Cloud CA vrij te geven voor beheerde Intune-apparaten. Als u de Intune Certificate Connector al gebruikt met Microsoft Certification Authority (CA), kunt u de bestaande configuratie van de Intune Certificate Connector gebruiken om de ondersteuning voor Symantec CA toe te voegen.

#### <a name="new-items-added-to-device-inventory-----1404455---"></a>Nieuwe items toegevoegd aan de apparaatinventarisatie   <!--1404455 -->
De volgende nieuwe items zijn nu beschikbaar voor de [inventaris van ingeschreven apparaten](device-inventory.md):

- Mac-adres van Wi-Fi
- Totale opslagruimte
- Totale vrije ruimte
- MEID
- Provider van abonnee


### <a name="app-management"></a>Appbeheer
#### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Toegang instellen voor apps via minimale Android-beveiligingspatch op het apparaat<!-- 1278463 -->   
Een beheerder kan de minimale Android-beveiligingspatch definiëren die op het apparaat moet zijn geïnstalleerd om toegang te kunnen krijgen tot een beheerde toepassing onder een beheerd account.

> [!Note]  
> Deze functie beperkt alleen beveiligingspatches die door Google zijn vrijgegeven op Android 6.0+ apparaten.

#### <a name="app-conditional-launch-support----1193313---"></a>Ondersteuning voor app-voorwaardelijk starten <!-- 1193313 -->
IT-beheerders kunnen nu via de Azure-beheerportal een vereiste instellen om een wachtwoordcode in plaats van een numerieke pincode af te dwingen via Mobile App Management (MAM) wanneer de toepassing start. Als dit is geconfigureerd, moet de gebruiker een wachtwoordcode instellen en gebruiken wanneer daarom wordt gevraagd, alvorens toegang te krijgen tot toepassingen met MAM-functionaliteit. Een wachtwoordcode wordt gedefinieerd als een numerieke pincode met ten minste één speciaal teken of een hoofdletter/kleine letter. Bij deze release van Intune wordt deze functie **alleen op iOS** ingeschakeld. Intune ondersteunt wachtwoordcodes op dezelfde manier als numerieke pincodes: er is een minimumlengte, en tekens en tekenreeksen mogen worden herhaald. Deze functie vereist dat toepassingen (WXP, Outlook, Managed Browser, Yammer) de Intune App SDK integreren met de code voor deze functie om de wachtwoordcode-instellingen af te dwingen in de doeltoepassingen.

#### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>App-versienummer voor line-of-business in rapport Installatiestatus van het apparaat <!-- 1233999 -->
Bij deze release toont het rapport Installatiestatus van het apparaat het app-versienummer voor de line-of-business-apps voor iOS en Android. U kunt deze informatie gebruiken om problemen met uw apps op te lossen of om apparaten te vinden waarop verouderde app-versies worden uitgevoerd.


### <a name="device-configuration"></a>Apparaatconfiguratie
#### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>Beheerders kunnen de firewall-instellingen op een apparaat nu configureren met behulp van een apparaatconfiguratieprofiel <!-- 951708 -->   
Beheerders kunnen de firewall inschakelen voor apparaten, en ook verschillende protocollen voor domein-, privé- en openbare netwerken configureren.  Deze firewall-instellingen staan in het profiel 'Endpoint Protection'.

#### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>Windows Defender Application Guard helpt apparaten te beschermen tegen niet-vertrouwde websites, zoals gedefinieerd door uw organisatie <!-- 958257 -->   
Beheerders kunnen sites als 'vertrouwd' of 'zakelijk' definiëren met behulp van een Windows Information Protection-werkstroom of het nieuwe profiel 'Netwerkgrens' onder apparaatconfiguraties. Sites die niet in een vertrouwde netwerkgrens van een 64-bits Windows 10-apparaat staan, worden in een browser op een virtuele Hyper-V-computer geopend als ze met Microsoft Edge worden bekeken.

Application Guard staat in de apparaatconfiguratieprofielen, in het profiel 'Endpoint Protection'. Beheerders kunnen daar interactie configureren tussen de gevirtualiseerde browser en de hostcomputer, niet-vertrouwde sites en vertrouwde sites, en gegevens opslaan die in de gevirtualiseerde browser worden gegenereerd. Als u Application Guard op een apparaat wilt gebruiken, moet er eerst een netwerkgrens worden geconfigureerd. Het is belangrijk slechts één netwerkgrens te definiëren voor een apparaat.  

#### <a name="windows-defender-application-control-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>Windows Defender Application Control op Windows 10 Enterprise biedt een modus om alleen geautoriseerde apps te vertrouwen <!-- 1031096 -->    
Aangezien er elke dag duizenden nieuwe schadelijke bestanden worden gemaakt, biedt malwaredetectie op basis van handtekeningen misschien niet meer voldoende bescherming tegen nieuwe aanvallen. Met Windows Defender Application Control op Windows 10 Enterprise kunt u de apparaatconfiguratie wijzigen van een modus waarin apps worden vertrouwd tenzij ze door een antivirus- of andere beveiligingsoplossing worden geblokkeerd, naar een modus waarin het besturingssysteem alleen apps vertrouwt die door uw onderneming zijn geautoriseerd. In Windows Defender Application Control definieert u welke apps u vertrouwt.

Met Intune kunt u het toepassingsbeheerbeleid configureren in de modus 'Alleen controle' of in de modus 'Afdwingen'. Apps worden niet geblokkeerd wanneer ze in de modus 'Alleen controle' worden uitgevoerd. De modus 'Alleen controle' registreert alle gebeurtenissen in lokale clientlogboeken. U kunt ook configureren of alleen Windows-onderdelen en Microsoft Store-apps mogen worden uitgevoerd of dat aanvullende apps met een goede reputatie, zoals die is gedefinieerd door de Intelligent Security Graph, ook mogen worden uitgevoerd.

#### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10----1063615---"></a>Window Defender Exploit Guard is een nieuwe verzameling inbraakpreventiefuncties voor Windows 10 <!-- 1063615 -->   
Window Defender Exploit Guard omvat aangepaste regels om de exploiteerbaarheid van toepassingen te reduceren, voorkomt macro- en scriptbedreigingen, blokkeert automatisch netwerkverbindingen naar IP-adressen met een slechte reputatie, en kan gegevens uit ransomware en onbekende bedreigingen beveiligen. Windows Defender Exploit Guard bestaat uit de volgende onderdelen:

- **Attack Surface Reduction (ASR)** biedt regels waarmee u macro-, script- en e-mailbedreigingen kunt voorkomen.
- **Gecontroleerde maptoegang** blokkeert automatisch de toegang tot inhoud in beveiligde mappen.
- **Netwerkfilter** blokkeert uitgaande verbindingen van een app naar een IP/domein met een slechte reputatie
- **Exploit-beveiliging** biedt geheugen-, controlestroom- en beleidsbeperkingen die kunnen worden gebruikt om een toepassing te beschermen tegen aanvallen.


#### <a name="manage-powershell-scripts-in-intune-for-windows-10-devices----790537---"></a>PowerShell-scripts in Intune beheren voor Windows 10-apparaten <!-- 790537 -->

Met de Intune-beheeruitbreiding kunt u PowerShell-scripts uploaden in Intune om deze uit te voeren op Windows 10-apparaten. De uitbreiding is een aanvulling op de Windows 10 MDM-functionaliteit en maakt het eenvoudiger voor u om uw beheer te moderniseren. Zie [PowerShell-scripts in Intune beheren voor Windows 10-apparaten](intune-management-extension.md) voor meer informatie.

#### <a name="new-device-restriction-settings-for-windows-10---------1308850---"></a>Nieuwe apparaatbeperkingsinstellingen voor Windows 10      <!-- 1308850 -->
-    Berichten (alleen mobiel) - testen of MMS-berichten uitschakelen
-    Wachtwoord - instellingen om FIPS en het gebruik van secundaire Windows Hello-apparaten in te schakelen voor verificatie 
-    Weergave - instellingen om GDI-schaalbaarheid in of uit te schakelen voor verouderde apps

#### <a name="windows-10-kiosk-mode-device-restrictions----1308872---"></a>Apparaatbeperkingen Windows 10-kioskmodus <!-- 1308872 -->   
U kunt gebruikers van Windows 10-apparaten beperken tot de kioskmodus, zodat ze worden beperkt tot een verzameling vooraf gedefinieerde apps.  Om dit te doen, maakt u een Windows 10-apparaatbeperkingsprofiel en configureert u de kioskinstellingen.

De kioskmodus ondersteunt twee modi: **één app** (waarbij een gebruiker slechts één app mag uitvoeren) en **meerdere apps** (geeft toegang tot een verzameling apps).  U definieert het gebruikersaccount en de apparaatnaam, waarmee de ondersteunde apps worden bepaald.  Wanneer de gebruiker is aangemeld, is hij/zij beperkt tot de gedefinieerde apps.  Zie [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) voor meer informatie. 

De kioskmodus vereist het volgende:

- Intune moet de MDM-instantie zijn.
- De apps moeten al op het doelapparaat zijn geïnstalleerd.
- Het apparaat moet [goed ingericht](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions) zijn.

#### <a name="new-device-configuration-profile-for-creating-network-boundaries----1311967---"></a>Nieuw apparaatconfiguratieprofiel voor het maken van netwerkgrenzen <!-- 1311967 -->   
Bij uw andere apparaatconfiguratieprofielen vindt u een nieuw apparaatconfiguratieprofiel genaamd **Netwerkgrens**. Gebruik dit profiel om onlinebronnen te definiëren die u als zakelijk en vertrouwd wilt beschouwen. U moet een netwerkgrens voor een apparaat definiëren *voordat* functies zoals Windows Defender Application Guard en Windows Information Protection op het apparaat kunnen worden gebruikt. Het is belangrijk slechts één netwerkgrens te definiëren voor elk apparaat.

U kunt bedrijfscloudresources, IP-adresbereiken en interne proxyservers definiëren die u als vertrouwd wilt beschouwen. Nadat u de netwerkgrens hebt gedefinieerd, kan deze worden gebruikt door andere functies zoals Windows Defender Application Guard en Windows Information Protection.

####  <a name="two-additional-settings-for-windows-defender-antivirus----1338409---"></a>Twee aanvullende instellingen voor Windows Defender Antivirus <!-- 1338409 -->  
**Blokkeringsniveau voor bestanden**

| | |
|---|---|
| Niet geconfigureerd | **Niet geconfigureerd** gebruikt het standaard Windows Defender Antivirus-blokkeringsniveau en biedt sterke detectie zonder het risico te vergroten dat legitieme bestanden worden gedetecteerd. |
| Hoog | **Hoog** past een sterk detectieniveau toe.
| Hoog +  | **Hoog +** biedt het niveau Hoog met aanvullende beveiligingsmaatregelen die de clientprestaties kunnen beïnvloeden.
| Zero tolerance  | **Zero tolerance** blokkeert alle onbekende uitvoerbare bestanden. |

Als u dit op **Hoog** instelt, worden sommige legitieme bestanden misschien gedetecteerd, hoewel dit onwaarschijnlijk is.
Het is raadzaam het Blokkeringsniveau voor bestanden in te stellen op de standaardinstelling **Niet geconfigureerd**.

**Time-outverlenging voor het scannen van bestanden door de cloud**  

| | |
|--|--|
| Aantal seconden (0-50) | Geef op hoelang Windows Defender Antivirus een bestand maximaal moet blokkeren terwijl u op een resultaat van de cloud wacht. De standaardinstelling is 10 seconden: de aanvullende tijd die u hier opgeeft (tot 50 seconden) wordt toegevoegd aan die 10 seconden. In de meeste gevallen duurt de scan veel korter dan de maximuminstelling. Als u de tijd verlengt, kan de cloud verdachte bestanden grondig onderzoeken. Het is raadzaam deze instelling in te schakelen en ten minste 20 aanvullende seconden op te geven. |

#### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Citrix-VPN toegevoegd voor Windows 10-apparaten <!-- 1512457 -->  
U kunt Citrix-VPN configureren voor Windows 10-apparaten van klanten. U kunt de Citrix-VPN kiezen in de lijst *Een verbindingstype selecteren* in de blade **Basis-VPN** wanneer u een VPN voor Windows 10 en hoger configureert.

> [!Note]
> Citrix-configuratie bestond voor iOS en Android.

#### <a name="wi-fi-connections-support-pre-shared-keys-on-ios----1550823---"></a>Wi-Fi-verbindingen ondersteunen vooraf gedeelde sleutels voor iOS <!-- 1550823 -->
Klanten kunnen Wi-Fi-profielen configureren voor het gebruik van vooraf gedeelde sleutels (PSK) voor WPA/WPA2 persoonlijke verbindingen op iOS-apparaten. Deze profielen worden gepusht naar het apparaat van de gebruiker als het apparaat is ingeschreven bij Intune.

Wanneer het profiel naar het apparaat is gepusht, is de volgende stap afhankelijk van de profielconfiguratie.  Als automatische verbinding is ingesteld, wordt automatisch verbinding gemaakt zodra het netwerk nodig is.  Als handmatige verbinding is ingesteld, moet de gebruiker de verbinding handmatig activeren.  

### <a name="intune-apps"></a>Intune-apps

#### <a name="access-to-managed-app-logs-for-ios----1469920---"></a>Toegang tot de logboeken van de beheerde app voor iOS <!-- 1469920 -->
Eindgebruikers waarvoor de beheerde browser is geïnstalleerd kunnen de beheerstatus van alle gepubliceerde Microsoft-apps bekijken en logbestanden versturen om problemen met hun beheerde iOS-apps op te lossen.

Zie [Toegang tot de logboeken van de beheerde app voor iOS](app-configuration-managed-browser.md#how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios) voor meer informatie over het inschakelen van de probleemoplossingsmodus in de beheerde browser op een iOS-apparaat.

#### <a name="improvements-to-device-setup-workflow-in-the-company-portal-for-ios-in-version-290----1417174---"></a>Verbeteringen in de werkstroom voor apparaatinstellingen in de bedrijfsportal voor iOS in versie 2.9.0 <!-- 1417174 -->

De werkstroom voor apparaatinstellingen in de bedrijfsportal-app voor iOS is verbeterd. De taal is gebruiksvriendelijker en waar mogelijk hebben we schermen gecombineerd. De taal is ook specifieker voor uw bedrijf gemaakt door overal in de installatietekst de naam van uw bedrijf te gebruiken. U kunt deze bijgewerkte werkstroom zien op de  [pagina met nieuwe functies in de app](whats-new-app-ui.md).

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>De gebruikersentiteit bevat de meest recente gebruikersgegevens in het datawarehouse-gegevensmodel <!-- 1544273 -->
De eerste versie van het gegevensmodel Intune-datawarehouse bevat alleen recente, historische Intune-gegevens. Rapportopstellers kunnen de huidige status van een gebruiker niet vastleggen. In deze update wordt  **Gebruikersentiteit** ingevuld met de meest recente gebruikersgegevens.


## <a name="notices"></a>Mededelingen

### <a name="plan-for-change-new-windows-10-setting-for-kiosk-configuration-in-intune----1560072---"></a>Plannen voor wijziging: nieuwe Windows 10-instelling voor kioskconfiguratie in Intune <!-- 1560072 -->
De manier waarop u bureaubladen van Windows 10 1709 en hoger (RS3 en hoger) configureert in de Intune-portal van Azure is gewijzigd.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij? 
Volgens onze gegevens gebruikt u de instelling Windows 10 > Apparaatbeperkingen > Kiosk (preview). Deze instelling wordt in mei gewijzigd in Windows 10 > Apparaatbeperkingen > Kiosk (verouderd) om aan te geven dat deze instelling niet meer wordt aanbevolen. De instelling blijft echter functioneren tot de update van juli naar Intune. Vervolgens wordt de instelling ingesteld als verouderd, waardoor deze niet meer werkt. Als alternatief introduceren wordt in mei een nieuw apparaatconfiguratieprofiel geïntroduceerd: Windows 10 > Kiosk, met de instellingen om kiosken te configureren in Windows 10 RS4 en hoger.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?  
Wanneer de service-update rond eind mei wordt vrijgegeven, worden instructies verzonden waarmee u kunt testen en controleren of u uw kioskconfiguratie van Windows 10 RS3 naar Windows 10 RS4 kunt migreren. Met deze instructies kunt u uw apparaten als kiosken configureren met het nieuwe apparaatconfiguratieprofiel voor kiosken.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Deze wijziging is van invloed op zowel zelfstandige als hybride klanten (Intune met Configuration Manager) van Intune. Door deze integratie wordt het beheer van uw cloud vereenvoudigd. U kunt groepen, beleidsregels, apps en mobiele apparaten voortaan vanaf één blade in Azure, de blade Intune, beheren.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
Label Intune als favoriet in plaats van de serviceblade Intune-app-beveiliging en zorg ervoor dat u bekend bent met de werkstroom voor het beleid voor app-beveiliging in de blade Mobiele app in Intune. U wordt slechts tijdelijk omgeleid. De blade App-beveiliging wordt uiteindelijk verwijderd. Alle beleidsregels voor de beveiliging van apps staan al in Intune en u kunt uw beleid voor voorwaardelijke toegang wijzigen aan de hand van de volgende documentatie: [https://aka.ms/azuread_ca](https://aka.ms/azuread_ca).

**Aanvullende informatie**: [https://aka.ms/intuneapppolicy](https://aka.ms/intuneapppolicy)

### <a name="plan-for-change-change-in-support-for-the-microsoft-intune-app-sdk-for-cordova-plugin"></a>Plannen voor wijziging: wijziging in de ondersteuning voor Microsoft Intune App SDK voor Cordova-invoegtoepassing
Intune beëindigt de ondersteuning voor de [Microsoft Intune App SDK Cordova-invoegtoepassing](app-sdk-cordova.md) op 1 mei 2018. We raden u aan in plaats daarvan de Intune App Wrapping Tool te gebruiken om uw op Cordova gebaseerde apps voor te bereiden op beheerbaarheid en beschikbaarheid in Intune. Zodra deze wijziging is doorgevoerd, wordt de Microsoft Intune APP SDK voor de Cordova-invoegtoepassing niet langer onderhouden en worden er geen updates meer voor gegeven. App-ontwikkelaars kunnen deze invoegtoepassing dan niet langer gebruiken. Intune is van plan apps die met Cordova zijn gebouwd te blijven ondersteunen. Alle apps die zijn gebouwd met Microsoft Intune APP SDK voor de Cordova-invoegtoepassing zullen echter kampen met beperkte functionaliteit in Intune. Nadat u apps hebt verpakt met de Intune App Wrapping Tool, kunnen deze apps zoals u gewend bent voor eindgebruikers worden geïmplementeerd. Voor Android-apps op basis van Cordova die in de Google Play Store worden gepubliceerd, geldt het volgende:
- Wanneer eindgebruikers de app voor het eerst starten, moeten ze referenties opgeven om het Intune-beleid te ontvangen.
- Apps moeten gericht op Intune-gebruikers worden gepubliceerd in de App Store, bijvoorbeeld ‘Contoso-app voor Intune’.

Zie [App Wrapping Tool voor iOS](app-wrapper-prepare-ios.md) en [App Wrapping Tool voor Android](app-wrapper-prepare-android.md) voor meer informatie over de App Wrapping Tool. Voor eventuele problemen of vragen neemt u contact op met [msintuneappsdk@microsoft.com](mailto:msintuneappsdk@microsoft.com).

### <a name="plan-for-change-use-intune-on-azure-now-for-your-mdm-management----1227338---"></a>Wijzigingsplannen: u kunt Intune op Azure nu gebruiken voor uw MDM-beheer <!-- 1227338 -->
Een jaar geleden hebben we de [openbare preview van Intune op Azure](https://cloudblogs.microsoft.com/enterprisemobility/2016/12/07/public-preview-of-intune-on-azure/) aangekondigd en zes maanden geleden hebben we deze opgevolgd met de [algemene beschikbaarheid van de nieuwe beheerderservaring](https://cloudblogs.microsoft.com/enterprisemobility/2017/06/08/the-new-intune-and-conditional-access-admin-consoles-are-ga/) voor Intune. Vanaf 31 augustus 2018 wordt MDM (Mobile Device Management) uitgeschakeld in de klassieke Silverlight-console voor klanten met de zelfstandige versie van Intune. In plaats daarvan kunt u [Intune op Azure](https://aka.ms/Intune_on_Azure) gebruiken voor MDM. Als u nog steeds de klassieke console voor MDM gebruikt, moet u hiermee stoppen en uzelf vertrouwd maken met Intune op Azure. We verwachten niet dat deze wijziging gevolgen heeft voor eindgebruikers. Klassiek pc-beheer blijft in Silverlight nog gewoon aanwezig. U vindt [hier](https://aka.ms/Intune_on_Azure_mdm) meer informatie over deze wijziging en over eventuele gevolgen voor u.

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Rechtstreekse toegang tot Apple-scenario's voor inschrijving <!--951869-->
Voor Intune-accounts die na januari 2017 zijn gemaakt, heeft Intune rechtstreekse toegang ingeschakeld tot Apple-inschrijvingsscenario's. Hiervoor is de werkstroom voor het inschrijven van apparaten gebruikt in Azure Portal. Voorheen was de Apple-inschrijvingspreview alleen toegankelijk via koppelingen in de klassieke Intune-portal. Intune-accounts die vóór januari 2017 zijn gemaakt, moeten eenmalig worden gemigreerd om de functies in Azure beschikbaar te maken. De planning voor de migratie is nog niet aangekondigd, maar de informatie wordt zo snel mogelijk beschikbaar gemaakt. Het wordt aangeraden om een testaccount te maken om de nieuwe ervaring te testen als u met uw bestaande account geen toegang hebt tot Azure Portal.

## <a name="whats-coming"></a>Binnenkort

### <a name="local-device-security-option-settings----1251887---"></a>Instellingen voor de beveiligingsopties van lokale apparaten <!-- 1251887 -->
U kunt beveiligingsinstellingen op Windows 10-apparaten inschakelen met de nieuwe instellingen voor de beveiligingsopties van lokale apparaten. U vindt deze instellingen in de Endpoint Protection-categorie wanneer u een configuratiebeleid voor Windows 10-apparaten maakt.

### <a name="new-user-experience-update-for-the-company-portal-website---2000968--"></a>Nieuwe update van de gebruikerservaring voor de bedrijfsportalwebsite <!--2000968-->

In april wordt een nieuwe ervaring voor de bedrijfsportalwebsite geïntroduceerd, met UI-updates, gestroomlijnde werkstromen en toegankelijkheidsverbeteringen. Deze omvat klantgestuurde verbeteringen zoals het delen van apps en verbeterde algehele prestaties voor een gebruikersvriendelijker ervaring.
Er is een aantal nieuwe functies toegevoegd op basis van feedback van klanten zoals u. Hiermee worden de bestaande functionaliteit en bruikbaarheid aanzienlijk verbeterd:

-   UI-verbeteringen in de gehele website
-   Mogelijkheid om directe koppelingen naar apps te delen
- Verbeterde prestaties voor grote app-catalogi

U hoeft niets te doen om u op deze wijziging voor te bereiden. Wij brengen u op de hoogte wanneer de bijgewerkte bedrijfsportalwebsite voor u beschikbaar komt. U moet wellicht uw documentatie voor eindgebruikers met bijgewerkte schermafbeeldingen updaten. Ook moet u mogelijk documentatie voor de bedrijfsportal-app op iOS updaten, omdat de website de sectie **Apps** van de iOS-app mogelijk maakt. U kunt hiervan een voorbeeldafbeelding bekijken op de pagina [Nieuw in de gebruikersinterface van de app](whats-new-app-ui.md).

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple vereist updates voor Application Transport Security <!--748318-->
Apple heeft aangekondigd dat specifieke vereisten gaan gelden voor Application Transport Security (ATS). ATS wordt gebruikt om betere beveiliging af te dwingen voor alle app-communicatie die verloopt via HTTPS. Deze wijziging heeft gevolgen voor Intune-klanten die de bedrijfsportal-app gebruiken op iOS. De [Intune-ondersteuningsblog](https://aka.ms/compportalats) wordt bijgewerkt met informatie.



## <a name="see-also"></a>Zie ook
* [Microsoft Intune-blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Roadmap voor cloudplatform](https://www.microsoft.com/cloud-platform/roadmap)
* [Wat is er nieuw in de gebruikersinterface van de bedrijfsportal?](whats-new-app-ui.md)
* [Wat was er in de vorige maanden nieuw](whats-new-archive.md)
