---
title: In ontwikkeling - Microsoft Intune
titleSuffix: ''
description: Microsoft Intune-functies in ontwikkeling
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/29/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7bba992c79f69a126f0199d9cdac52779910ff38
ms.sourcegitcommit: 068c4e4bc6e6d778ece4a83d000128c4d2b732db
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/29/2019
ms.locfileid: "64910315"
---
# <a name="in-development-for-microsoft-intune---may-2019"></a>In ontwikkeling voor Microsoft Intune - mei 2019

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
 
## <a name="intune-in-the-azure-portal"></a>Intune in Azure Portal


<!-- 1905 start-->


### <a name="deleting-a-device-in-the-apple-portal-will-be-reflected-in-the-intune-portal---2489996---"></a>Verwijderen van apparaat in de Apple-portal wordt doorgevoerd in de Intune-portal <!--2489996 -->
Als een apparaat wordt verwijderd uit de portal van het Device Enrollment Program van Apple of van Apple Business Manager, wordt het apparaat bij de volgende synchronisatie automatisch verwijderd uit Intune.

### <a name="baseline-support-for-keyword-search-----3082036-----------"></a>Basislijnondersteuning voor zoeken op trefwoord  <!-- 3082036         -->
Als u een basislijnprofiel voor beveiliging gaat maken of bewerken, kunt u binnenkort de *zoekfunctie* gebruiken om de instellingen te filteren die in de console worden weergegeven.   

### <a name="reset-and-wipe-devices-in-bulk-by-using-the-graph-api----3295288---"></a>Apparaten in bulk opnieuw instellen en wissen met behulp van de Graph API <!-- 3295288 -->
U kunt in één bulkbewerking maximaal 100 apparaten opnieuw instellen en wissen met behulp van de Graph API.

### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---"></a>Controleren of er zich een TPM-chipset in een nalevingsbeleid voor Windows 10-apparaten bevindt <!-- 3617671 -->
Veel apparaten met Windows 10 en hoger hebben TPM-chipsets (Trusted Platform Module). Deze update bevat een nieuwe nalevingsinstelling die de versie van de TPM-chip in het apparaat controleert. 

Deze instelling wordt beschreven in [Instellingen voor nalevingsbeleid voor apparaten met Windows 10 en later](compliance-policy-create-windows.md#device-security).

Van toepassing op Windows 10 en hoger

### <a name="intune-management-extension-powershell-scripts-----3734186------"></a>Intune-beheerextensie voor PowerShell-scripts  <!-- 3734186    -->
U kunt instellen dat PowerShell-scripts worden uitgevoerd met de beheerdersbevoegdheden van de gebruiker op het apparaat. Zie [PowerShell-scripts op Windows 10-apparaten gebruiken in Intune](intune-management-extension.md) voor meer informatie.

### <a name="prevent-end-users-from-modifying-their-personal-hotspot-and-disable-siri-server-logging-on-ios-supervised-devices----4097904----"></a>Voorkomen dat gebruikers hun persoonlijke hotspot wijzigen en logboekregistratie van Siri-server op iOS-apparaten onder supervisie uitschakelen <!-- 4097904  --> 
U maakt een profiel met apparaatbeperkingen op het iOS-apparaat (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype). Deze update bevat nieuwe instellingen die u kunt configureren:

- Persoonlijke hotspot
- Logboekregistratie van Siri-server

Als u de huidige instellingen wilt zien, gaat u naar [iOS-apparaatinstellingen voor het toestaan of beperken van functies](device-restrictions-ios.md). 

Van toepassing op: iOS 12.2 en nieuwer

### <a name="new-classroom-app-device-restriction-settings-for-dep-enrolled-macos-devices----4097905----"></a>Nieuwe instellingen voor apparaatbeperkingen voor Klaslokaal-app op met DEP geregistreerde macOS-apparaten <!-- 4097905  --> 
U kunt apparaatconfiguratieprofiel voor macOS-apparaten maken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **macOS** voor platform > **Apparaatbeperkingen** voor profieltype). Deze update bevat nieuwe instellingen voor de Klaslokaal-app voor met DEP geregistreerde apparaten en de optie om de iCloud-fotobibliotheek uit te schakelen.

Als u de huidige instellingen wilt zien, gaat u naar [macOS-apparaatinstellingen voor het toestaan of beperken van functies met Intune](device-restrictions-macos.md).

Van toepassing op: macOS 10.14.4 en hoger

### <a name="android-enterprise-app-management----4459905-idready---"></a>Beheer van Android Enterprise-apps <!-- 4459905 idready -->
Om het eenvoudiger te maken voor IT-beheerders om Android Enterprise-beheer te configureren en gebruiken, voegt Intune automatisch vier veelgebruikte Android Enterprise apps toe aan de beheerconsole van Intune. Het betreft de volgende vier Android Enterprise-apps:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)**: wordt gebruikt voor scenario's met volledig beheer door Android Enterprise.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)**: helpt om u aan te melden bij uw accounts als u tweeledige verificatie gebruikt.
- **[Intune-bedrijfsportal](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)**: wordt gebruikt voor beleidsregels voor app-beveiliging (APP) en werkprofielscenario's van Android Enterprise.
- [Managed Home Screen](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise): wordt gebruikt voor toegewezen/kiosk-scenario's van Android Enterprise.

Eerder moesten IT-beheerders deze apps als onderdeel van de installatie handmatig zoeken en goedkeuren in de [beheerde Google Play Store](https://play.google.com/store/apps). Met deze wijziging worden deze eerdere handmatige stappen weggenomen om het gemakkelijker en sneller te maken voor klanten om Android Enterprise-beheer te gebruiken.

Deze vier apps worden automatisch toegevoegd aan de lijst met Intune-apps van beheerders op het moment dat ze hun Intune-tenant voor het eerst verbinden met de beheerde Google Play Store. Zie [Uw Intune-account verbinden met uw Beheerde Google Play-account](connect-intune-android-enterprise.md) voor meer informatie. Beheerders die hun tenant al hebben verbonden of die al gebruikmaken van Android Enterprise hoeven niets te doen. Deze vier apps komen automatisch beschikbaar, binnen maximaal zeven dagen na het voltooien van de implementatie van de service-update van mei 2019.

<!-- 1904 start-->

### <a name="advanced-settings-for-windows-defender-firewall----1311949---"></a>Geavanceerde instellingen voor Windows Defender Firewall <!-- 1311949 -->
U kunt binnenkort Intune gebruiken om de aangepaste firewallregels op clients voor Windows Defender te beheren. Met regels kunt u inkomend en uitgaand gedrag voor toepassingen, netwerkadressen en poorten opgeven. 


### <a name="device-users-can-view-all-managed-apps-theyve-installed-or-tried-to-install----2352913---"></a>Apparaatgebruikers kunnen alle beheerde apps bekijken die ze hebben geïnstalleerd of hebben geprobeerd te installeren <!-- 2352913 -->
In Bedrijfsportal voor Windows komen alle beheerde apps &ndash; zowel vereiste als beschikbare &ndash; die op het apparaat van een gebruiker zijn geïnstalleerd. Gebruikers kunnen geprobeerde en in behandeling zijnde app-installaties bekijken met de huidige status ervan. Als uw organisatie geen apps verplicht of beschikbaar stelt, krijgen gebruikers het bericht te zien dat er geen bedrijfs-apps zijn geïnstalleerd. Gebruikers kunnen hun apps ook sorteren of filteren op installatiestatus.

### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>Toepasselijkheidsregels gebruiken bij het maken van Windows 10-apparaatconfiguratieprofielen <!-- 2549910 -->
U kunt Windows 10-apparaatconfiguratieprofielen maken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10** als platform). U kunt een **toepassingsregel** maken zodat het profiel alleen van toepassing is op een specifieke editie of versie. U maakt bijvoorbeeld een profiel waarmee bepaalde BitLocker-instellingen worden ingeschakeld. Als u het profiel toevoegt, gebruikt u een toepassingsregel zodat het profiel alleen van toepassing is op apparaten met Windows 10 Enterprise.

Van toepassing op: 
- Windows 10 en hoger

###  <a name="intune-security-tasks-for-defender-atp-in-public-preview----3208597---"></a>Intune-beveiligingstaken voor Defender ATP (in openbare preview) <!-- 3208597 -->
Binnenkort krijgt Intune in openbare preview aanvullende beveiligingstaken voor het pas aangekondigde Microsoft Defender Threat and Vulnerability Management.  Met deze integratie kunt kunnen beveiligingsbeheerders in Windows Defender ATP (WDATP) de aanbevolen herstelbewerkingen voor opduikende bedreigingen effectiever communiceren met Intune-beheerders. Met de toevoeging van beveiligingstaken komt er een op risico's gebaseerde aanpak voor het detecteren en classificeren van beveiligingsproblemen en onjuiste configuraties van eindpunten.

Zie voor meer informatie over beveiligingstaken in Intune het blogbericht over [het gebruik van Intune-beveiligingstaken als uitbreiding van Threat and Vulnerability Management van Microsoft Defender ATP](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/Microsoft-Intune-security-tasks-extend-Microsoft-Defender-ATP-s/ba-p/369857). 

### <a name="windows-defender-advanced-threat-protection-baseline----3754134---"></a>Windows Defender Advanced Threat Protection-basislijn <!-- 3754134 -->
We voegen een nieuwe basislijn toe om u te helpen bij het configureren van Windows Defender Advanced Threat Protection-instellingen.



## <a name="notices"></a>Mededelingen

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Zie tevens
Zie [Wat is er nieuw in Microsoft Intune?](whats-new.md) voor meer informatie over recente ontwikkelingen.


