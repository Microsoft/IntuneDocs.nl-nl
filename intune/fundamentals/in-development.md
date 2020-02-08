---
title: In ontwikkeling - Microsoft Intune
titleSuffix: ''
description: Microsoft Intune-functies in ontwikkeling
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/07/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.assetid: 25b3c26e-cf4e-4152-8306-bf4be4af2ad1
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: d71ae3c15dddedd5d9ebfaf06fcae25af89f6b82
ms.sourcegitcommit: c46b0c2d4507be6a2786a4ea06009b2d5aafef85
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/01/2020
ms.locfileid: "76912625"
---
# <a name="in-development-for-microsoft-intune---january-2020"></a>In ontwikkeling voor Microsoft Intune - januari 2020

Als hulp bij uw gereedheid en planning worden op deze pagina updates voor en functies van de Intune-gebruikersinterface vermeld die in ontwikkeling zijn, maar nog niet zijn uitgebracht. Naast de informatie op deze pagina geldt het volgende: 

- Als we verwachten dat u actie moet ondernemen vóór een wijziging, publiceren we een aanvullend bericht in het Office-berichtencentrum.
- Als een functie in productie gaat, of het nu gaat om een preview of algemene beschikbaarheid, wordt de functiebeschrijving verplaatst van deze pagina naar [Nieuwe functies](whats-new.md).
- Deze pagina en de pagina [Nieuwe functies](whats-new.md) worden regelmatig bijgewerkt. Controleer op andere updates.
- Raadpleeg de [Microsoft 365-roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) voor strategische producten en tijdlijnen.

> [!NOTE]
> Deze pagina bevat onze huidige verwachtingen over Intune-mogelijkheden in een toekomstige release. Datums en afzonderlijke functies kunnen worden gewijzigd. Op deze pagina worden niet alle functies in ontwikkeling beschreven.

**RSS-feed**: U ziet wanneer deze pagina wordt bijgewerkt door de volgende URL in uw feedlezer te kopiëren en plakken: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->

<!-- Common categories:  
## App management
## Device configuration
## Device enrollment
## Device management
## Intune apps
## Monitor and troubleshoot
## Role-based access control
## Security

-->
 
<!-- ***********************************************-->
## <a name="app-management"></a>Appbeheer

### <a name="display-notifications-for-the-company-portal-app-on-windows---1808082----"></a>Meldingen weergeven voor de Bedrijfsportal-app in Windows<!-- 1808082  -->
De Bedrijfsportal-app wordt bijgewerkt op Windows-apparaten om pop-upmeldingen voor gebruikers weer te geven, ook wanneer de toepassing gesloten is. In de update worden alleen meldingen voor beschikbare apps weergegeven wanneer de installatiestatus is voltooid of mislukt. In de Bedrijfsportal-app worden geen meldingen weergegeven voor vereiste toepassingen. 

### <a name="display-installation-status-messages-for-the-company-portal-app---2514416----"></a>Berichten over de installatiestatus voor de Bedrijfsportal-app weergeven<!-- 2514416  -->
In de Bedrijfsportal-app worden aanvullende berichten over de status van de app-installatie weergegeven voor eindgebruikers. De volgende voorwaarden zijn van toepassing op nieuwe Win32-afhankelijkheidsfuncties:
- App installeren mislukt. Er is niet voldaan aan afhankelijkheden die zijn gedefinieerd door de beheerder.

### <a name="retarget-web-clips-to-microsoft-edge-on-ios-devices---5455276---"></a>Microsoft Edge als nieuw doel opgeven voor webclips op iOS-apparaten<!-- 5455276 -->
Webclips, die fungeren als vastgemaakte web-apps op iOS-apparaten, moeten worden bijgewerkt. Zojuist geïmplementeerde webclips worden in Microsoft Edge geopend in plaats van in de Intune Managed Browser als openen in een beveiligde browser wordt vereist. U moet een nieuw doel opgeven voor reeds bestaande webclips om ervoor te zorgen dat deze worden geopend in Microsoft Edge in plaats van de Managed Browser. 


<!-- ***********************************************-->
## <a name="device-configuration"></a>Apparaatconfiguratie

### <a name="wired-network-device-configuration-profiles-for-macos-devices---3508686----"></a>Configuratieprofielen voor een bekabeld netwerkapparaat voor macOS-apparaten<!-- 3508686  -->
Er wordt een nieuw configuratieprofiel voor macOS-apparaten beschikbaar gemaakt om bekabelde netwerken te configureren (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **macOS** als platform > **Bekabeld netwerk** als profieltype). Gebruik deze functie om 802.1x-profielen te maken om bekabelde netwerken te beheren en om deze bekabelde netwerken te implementeren op uw macOS-apparaten.

Van toepassing op:
- macOS

### <a name="vpn-profiles-with-ikev2-vpn-connections-can-use-always-on-with-ios-devices----1947932-idready---"></a>Voor VPN-profielen met IKEv2 VPN-verbindingen kan AlwaysOn worden gebruikt voor iOS-apparaten <!-- 1947932 idready -->
Op iOS-apparaten kunt u een VPN-profiel maken dat gebruikmaakt van een IKEv2-verbinding (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS/iPadOS** als platform > **VPN** als profieltype). In een toekomstige update kunt u AlwaysOn configureren met IKEv2. IKEv2 VPN-profielen maken, nadat deze zijn geconfigureerd, automatisch verbinding en blijven verbonden (of maken snel opnieuw verbinding) met het VPN. De verbinding blijft bestaan, ook bij wisselingen van netwerk of als apparaten opnieuw worden opgestart.

Op iOS is AlwaysOn VPN beperkt tot IKEv2-profielen.

Als u wilt zien welke IKEv2-instellingen u momenteel kunt configureren, gaat u naar [VPN-instellingen toevoegen op iOS-apparaten in Microsoft Intune](../configuration/vpn-settings-ios.md#ikev2-settings).

Van toepassing op:
- iOS

### <a name="improved-user-interface-experience-when-creating-configuration-profiles-on-ios-and-macos-devices---5569008-5569039-5569057-5569110-5569116-5569131-5569139-5569153-5859984-idready---"></a>Verbeterde gebruikersinterface-ervaring bij het maken van configuratieprofielen op iOS-en macOS-apparaten<!-- 5569008-5569039-5569057-5569110-5569116-5569131-5569139-5569153-5859984 idready -->
Wanneer u een profiel voor iOS-of macOS-apparaten maakt, wordt de ervaring in het Beheercentrum voor Eindpuntbeheer bijgewerkt. Deze wijziging is van invloed op de volgende apparaatconfiguratieprofielen (**Apparaten** > **Configuratieprofielen** > **Profiel maken** > **iOS** of **macOS** als platform):

- Aangepast: iOS, macOS
- Apparaatfuncties: iOS, macOS
- Apparaatbeperkingen: iOS, macOS
- Endpoint Protection: macOS
- Extensies: macOS
- Voorkeursbestand: macOS

### <a name="improved-user-interface-experience-when-creating-oemconfig-configuration-profiles-on-android-enterprise-devices---5568645-idready----"></a>Verbeterde gebruikersinterface-ervaring bij het maken van OEMConfig-configuratieprofielen op Android Enterprise-apparaten<!-- 5568645 idready  -->
Wanneer u een OEMConfig-profiel voor Android Enterprise-apparaten maakt of bewerkt, wordt de ervaring in het Beheercentrum voor Eindpuntbeheer bijgewerkt. De bijgewerkte ervaring biedt in één oogopslag een overzicht van de instellingen die u hebt geconfigureerd. Deze wijziging is van invloed op het OEMConfig-apparaatconfiguratieprofiel (**Apparaten** > **Configuratieprofielen** > **Profiel maken** > **Android Enterprise** als platform > **OEMConfig** als profieltype).

Deze functie is van toepassing op:
- Android Enterprise 

<!-- ***********************************************-->
<!--## Device enrollment-->



<!-- ***********************************************-->
<!--## Device management-->



<!-- ***********************************************-->
<!--## Intune apps-->
 

<!-- ***********************************************-->

<!--
## Monitoring and troubleshooting
-->


<!-- ***********************************************-->
## <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer

### <a name="intune-roles-user-interface-changes-coming--5801612-idready--"></a>Wijzigingen in de gebruikersinterface van Intune-rollen zijn binnenkort beschikbaar<!--5801612 idready-->
De gebruikersinterface voor [Beheercentrum voor Microsoft Eindpuntbeheer](https://go.microsoft.com/fwlink/?linkid=2109431) > **Tenantbeheer** > **Rollen** wordt gewijzigd in een gebruiksvriendelijk en intuïtief ontwerp. Deze ervaring biedt dezelfde instellingen en gegevens als u nu gebruikt, maar werkt met een wizardachtige procedure.


<!-- ***********************************************-->
## <a name="security"></a>Beveiliging

### <a name="derived-credentials-support-on-android-cobo-devices--4839592--"></a>Ondersteuning voor afgeleide referenties op Android COBO-apparaten<!--4839592-->
U kunt afgeleide referenties gebruiken op volledig beheerde Android Enterprise-apparaten. Ondersteuning wordt opgenomen voor het ophalen van een afgeleide referentie voor Entrust Datacard, Intercede en DISA Purebred. U kunt een afgeleide referentie gebruiken voor appverificatie, Wi-Fi, VPN of voor S/MIME-ondertekening en/of versleuteling voor apps die dit ondersteunen. 

<!-- ***********************************************-->
## <a name="notices"></a>Mededelingen

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Zie tevens
Voor meer informatie over recente ontwikkelingen raadpleegt u [Wat is er nieuw in Microsoft Intune?](whats-new.md).


