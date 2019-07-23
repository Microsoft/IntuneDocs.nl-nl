---
title: In ontwikkeling - Microsoft Intune
titleSuffix: ''
description: Microsoft Intune-functies in ontwikkeling
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6ee62213c9ef23302de7fa7342569e1903514699
ms.sourcegitcommit: 11a31cd39b727f2254e2705b07d18924e103bd2e
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 07/19/2019
ms.locfileid: "68341341"
---
# <a name="in-development-for-microsoft-intune---july-2019"></a>In ontwikkeling voor Microsoft Intune - juli 2019

Als ondersteuning bij uw gereedheid en planning worden op deze pagina updates voor en functies van de Intune-gebruikersinterface vermeld die in ontwikkeling zijn, maar nog niet zijn uitgebracht. Daarnaast:

- Als we verwachten dat u actie moet ondernemen voorafgaand aan een wijziging, publiceren we een aanvullend bericht in het Office-berichtencentrum.
- Als er een functie wordt uitgebracht in productie, ofwel als preview ofwel als algemeen beschikbare functie, wordt de functiebeschrijving verplaatst van deze pagina naar de [pagina Nieuwe functies](whats-new.md).
- Deze pagina en de pagina [Nieuwe functies](whats-new.md) worden regelmatig bijgewerkt. Controleer op andere updates.
- Raadpleeg de [M365-roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) voor strategische producten en tijdlijnen.

> [!Note]
> Deze items representeren de huidige verwachtingen van Microsoft over Intune-mogelijkheden in een toekomstige release. Datums en afzonderlijke functies kunnen worden gewijzigd. Niet alle items in ontwikkeling hebben een functieomschrijving op deze pagina.

**RSS feed**: ontvang een melding wanneer deze pagina wordt bijgewerkt door de volgende URL in uw feedlezer te kopiëren en plakken: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->

<!-- Common categories:  
#### App management
#### Device configuration
#### Device enrollment
#### Device management
#### Intune apps
#### Monitor and troubleshoot
#### Role-based access control
#### Security

-->
 
<!-- ***********************************************-->
## <a name="app-management"></a>Appbeheer


### <a name="customized-notifications-for-users-and-groups-------16766574-----"></a>Aangepaste meldingen voor gebruikers en groepen    <!-- 16766574   -->
U kunt binnenkort aangepaste ad hoc push meldingen verzenden vanuit de Bedrijfsportal-toepassing naar gebruikers op iOS-en Android-apparaten die u met intune beheert. Deze aangepaste meldingen zijn niet gekoppeld aan bepaalde intune-functies en kunnen worden gebruikt voor elk gewenst doel einde, met inbegrip van algemene meldingen die u naar sommige of al uw werk nemers wilt verzenden.  

### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Inhoud van app-meldingen voor organisatie accounts configureren <!-- 2576686 -->
Met intune app-beveiligings beleid (APP) op Android-en iOS-apparaten kunt u inhoud voor app-meldingen beheren voor organisatie accounts. Deze functie vereist ondersteuning van toepassingen en is mogelijk niet beschikbaar voor alle toepassingen die zijn ingeschakeld voor apps. Zie [Wat is beveiligingsbeleid voor apps?](app-protection-policy.md) voor meer informatie over APP.

### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956----"></a>Beschikbare rapportage over Google Play-apps voor Android-werkprofielen <!-- 3041956  -->
U kunt voor beschikbare app-installaties op apparaten met Android-werkprofielen de status van de app-installatie evenals de geïnstalleerde versie van beheerde Google Play-apps bekijken. Zie [How to monitor app protection policies](app-protection-policies-monitor.md) (App-beveiligingsbeleid controleren), [Manage Android work profile devices with Intune](android-enterprise-overview.md) (Apparaten met Android-werkprofielen beheren met Intune) en [Managed Google Play app type](apps-add-android-for-work.md#managed-google-play-app-type) (Type beheerde Google Play-app) voor meer informatie.

<!-- ***********************************************-->
## <a name="device-configuration"></a>Apparaatconfiguratie


### <a name="support-for-ikev2-vpn-profiles-for-ios----1943438---"></a>Ondersteuning voor IKEv2 VPN-profielen voor iOS <!-- 1943438 -->
U kunt met het IKEv2-protocol VPN-profielen voor de systeemeigen VPN-client van iOS maken. IKEv2 is een nieuw verbindingstype in **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **VPN** voor profieltype > **Instellingen**.

Met deze VPN-profielen wordt de systeemeigen VPN-client geconfigureerd. Er worden dus geen VPN-client-apps geïnstalleerd of naar beheerde apparaten gepusht. Deze functie vereist dat apparaten zijn ingeschreven bij Intune (MDM-inschrijving).

Als u wilt zien welke VPN-instellingen u momenteel kunt configureren, gaat u naar [Configure VPN settings on iOS devices in Microsoft Intune](vpn-settings-ios.md) (VPN-instellingen configureren op iOS-apparaten in Microsoft Intune).

Van toepassing op: iOS

### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>Toepasselijkheidsregels gebruiken bij het maken van Windows 10-apparaatconfiguratieprofielen <!-- 2549910 -->
U kunt Windows 10-apparaatconfiguratieprofielen maken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10** als platform). U kunt een **toepassingsregel** maken zodat het profiel alleen van toepassing is op een specifieke editie of versie. U maakt bijvoorbeeld een profiel waarmee bepaalde BitLocker-instellingen worden ingeschakeld. Als u het profiel toevoegt, gebruikt u een toepassingsregel zodat het profiel alleen van toepassing is op apparaten met Windows 10 Enterprise.

Van toepassing op: 
- Windows 10 en hoger

### <a name="advanced-settings-for-windows-defender-firewall-------1311949-------"></a>Geavanceerde instellingen voor Windows Defender Firewall   <!--  1311949     -->
Als openbare preview kunt u binnenkort Intune gebruiken om de aangepaste firewallregels op clients voor Windows Defender te beheren.  

### <a name="new-configuration-designer-when-creating-an-oemconfig-profile-for-android-enterprise----3712769----"></a>Nieuwe configuratie Designer bij het maken van een OEMConfig-profiel voor Android Enter prise <!-- 3712769  -->
U kunt in intune een configuratie profiel voor een apparaat maken dat gebruikmaakt van een OEMConfig-app (apparaatconfiguratie > Profielen > profiel maken > Android Enter prise voor platform > OEMConfig voor profiel type). Wanneer u dit doet, wordt een JSON-editor geopend met een sjabloon en waarden die u kunt wijzigen. Deze update bevat een configuratie ontwerper met een verbeterde gebruikers ervaring waarin in de app Inge sloten Details worden weer gegeven, met inbegrip van titels, beschrijvingen en meer. De JSON-editor is nog steeds beschikbaar en toont de wijzigingen die u aanbrengt in de Configuration Designer.

Als u de huidige instellingen wilt zien, gaat u naar [Android Enter prise-apparaten gebruiken en beheren met OEMConfig](android-oem-configuration-overview.md).

Van toepassing op: Android Enterprise


<!-- ***********************************************-->
## <a name="device-management"></a>Apparaatbeheer

### <a name="improve-device-location---3855417---"></a>De locatie van het apparaat verbeteren<!-- 3855417 -->
U kunt inzoomen op de exacte coördinaten van een apparaat met behulp van de actie **apparaat zoeken** . Zie [Zoek verloren IOS-apparaten](device-locate.md)voor meer informatie over het zoeken naar verloren IOS-apparaten.

### <a name="configure-automatic-device-clean-up-time-limit-down-to-30-days---4231059----"></a>De tijds limiet voor het automatisch opschonen van apparaten configureren tot 30 dagen <!--4231059  -->
U kunt de tijds limiet voor automatische opschoning van apparaten instellen op 30 dagen (in plaats van de huidige limiet van 90 dagen) na de laatste aanmelding. Als u dit wilt doen, gaat u naar **intune** > **apparaten** > regels voor het opschonen**van**apparaten**instellen** > .


<!-- ***********************************************-->
## <a name="security"></a>Beveiliging

### <a name="import-and-export-security-baselines------3408610------------"></a>Beveiligings basislijnen importeren en exporteren    <!--3408610          -->  
We voegen de mogelijkheid toe om beveiligings basislijnen te exporteren en te importeren, zodat u uw aanpassingen kunt door nemen en delen tussen de intune-omgevingen.



<!-- ***********************************************-->
## <a name="notices"></a>Mededelingen

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

## <a name="see-also"></a>Zie tevens
Zie [Wat is er nieuw in Microsoft Intune?](whats-new.md) voor meer informatie over recente ontwikkelingen.


