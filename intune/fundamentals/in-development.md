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
ms.openlocfilehash: 01ea2f75d166e5cc6aef4b890dba5722a74c1f61
ms.sourcegitcommit: 8f56220e7cafc5bc43135940575a9acb5afde730
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 01/09/2020
ms.locfileid: "75827816"
---
# <a name="in-development-for-microsoft-intune---january-2020"></a>In ontwikkeling voor Microsoft Intune - januari 2020

Als hulp bij uw gereedheid en planning worden op deze pagina updates voor en functies van de Intune-gebruikersinterface vermeld die in ontwikkeling zijn, maar nog niet zijn uitgebracht. Naast de informatie op deze pagina: 

- Als we verwachten dat u actie moet ondernemen vóór een wijziging, publiceren we een aanvullend bericht in het Office-berichtencentrum.
- Wanneer een functie productie wordt ingevoerd, of het nu gaat om een preview-versie of algemeen beschikbaar is, wordt de beschrijving van de functie verplaatst van deze pagina naar [wat er nieuw](whats-new.md)is.
- Deze pagina en de pagina [Nieuwe functies](whats-new.md) worden regelmatig bijgewerkt. Controleer op andere updates.
- Raadpleeg de [Microsoft 365-roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) voor strategische producten en tijdlijnen.

> [!NOTE]
> Deze pagina weerspiegelt onze huidige verwachtingen over de mogelijkheden van intune in een toekomstige release. Datums en afzonderlijke functies kunnen worden gewijzigd. Op deze pagina worden niet alle functies in de ontwikkeling beschreven.

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

### <a name="display-notifications-for-the-company-portal-app-on-windows---1808082----"></a>Meldingen weer geven voor de Bedrijfsportal-app in Windows<!-- 1808082  -->
De Bedrijfsportal-app wordt bijgewerkt op Windows-apparaten om pop-upmeldingen voor gebruikers weer te geven, zelfs wanneer de toepassing wordt gesloten. In de update worden alleen meldingen voor beschik bare apps weer gegeven wanneer de installatie status is voltooid of mislukt. De Bedrijfsportal-app toont geen meldingen voor vereiste toepassingen. 

### <a name="display-installation-status-messages-for-the-company-portal-app---2514416----"></a>Berichten over de installatie status voor de app Bedrijfsportal weer geven<!-- 2514416  -->
In de Bedrijfsportal-app worden aanvullende status berichten voor de app-installatie weer gegeven voor eind gebruikers. De volgende voor waarden zijn van toepassing op nieuwe Win32-afhankelijkheids functies:
- App installeren mislukt. Er is niet voldaan aan de afhankelijkheden die zijn gedefinieerd door de beheerder.

### <a name="retarget-web-clips-to-microsoft-edge-on-ios-devices---5455276-idready---"></a>Webclipers omdoelen naar micro soft Edge op iOS-apparaten<!-- 5455276 idready -->
Webclips, die als vastgemaakte web-apps op iOS-apparaten fungeren, moeten worden bijgewerkt. Nieuwe geïmplementeerde webclips worden in micro soft Edge geopend in plaats van de Intune Managed Browser als dit nodig is om te openen in een beveiligde browser. U moet bestaande webclips opnieuw bedoelen om ervoor te zorgen dat ze worden geopend in micro soft Edge in plaats van de Managed Browser. 

### <a name="user-experience-change-when-adding-apps-to-intune---4705829-idready---"></a>Gebruikers ervaring verandert bij het toevoegen van apps aan intune<!-- 4705829 idready -->
Er wordt een nieuwe gebruikers ervaring weer geven bij het toevoegen van apps via intune. Deze ervaring biedt dezelfde instellingen en details die u eerder hebt gebruikt, maar de nieuwe ervaring volgt een wizard-soortgelijk proces voordat een app aan intune wordt toegevoegd. Deze nieuwe ervaring biedt ook een controle pagina voordat u de app toevoegt. Selecteer vanuit het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) de opties **Apps** > **Alle apps** > **Toevoegen**. Zie [Web-apps toevoegen aan Microsoft Intune](~/apps/apps-add.md) voor meer informatie.

#### <a name="require-win32-apps-to-restart----3136567--"></a>Vereisen dat Win32-apps opnieuw worden opgestart <!-- 3136567-->
U kunt vereisen dat een Win32-app opnieuw moet worden gestart na een geslaagde installatie. U kunt ook de hoeveelheid tijd (de respijt periode) kiezen voordat de computer opnieuw moet worden opgestart.

<!-- ***********************************************-->
## <a name="device-configuration"></a>Apparaatconfiguratie

### <a name="add-automatic-proxy-settings-to-wi-fi-profiles-for-android-enterprise-work-profiles---4490822-idready---"></a>Automatische proxy-instellingen toevoegen aan Wi-Fi-profielen voor Android Enter prise work-profielen<!-- 4490822 idready -->
Op apparaten met een werk Profiel van Android Enter prise kunt u Wi-Fi-profielen maken. Wanneer u het type Wi-Fi Enter prise kiest, kunt u ook het type Extensible Authentication Protocol (EAP) invoeren dat in uw Wi-Fi-netwerk wordt gebruikt.

Bij een toekomstige update kunt u, wanneer u het Enter prise-type kiest, automatische proxy-instellingen invoeren, met inbegrip van een proxy server-URL, zoals `proxy.contoso.com`.

Ga voor een overzicht van de huidige Wi-Fi-instellingen die u kunt configureren naar [Wi-Fi-instellingen toevoegen voor apparaten met Android Enter prise en Android kiosk in Microsoft intune](../configuration/wi-fi-settings-android-enterprise.md).

Van toepassing op:
- Android Enterprise - Werkprofiel

### <a name="wired-network-device-configuration-profiles-for-macos-devices---3508686----"></a>Configuratie profielen van bekabeld netwerk apparaat voor macOS-apparaten<!-- 3508686  -->
Er wordt een nieuw configuratie profiel voor macOS-apparaten beschikbaar waarmee bekabelde netwerken (**apparaatconfiguratie** > **profielen** worden geconfigureerd > profiel > **macOS** worden **gemaakt** voor platform > **bekabeld netwerk** voor profiel type). Gebruik deze functie om 802.1 x-profielen te maken voor het beheren van bekabelde netwerken en om deze bekabelde netwerken te implementeren op uw macOS-apparaten.

Van toepassing op:
- macOS

### <a name="vpn-profiles-with-ikev2-vpn-connections-can-use-always-on-with-ios-devices----1947932-idready---"></a>VPN-profielen met IKEv2 VPN-verbindingen kunnen altijd worden gebruikt voor iOS-apparaten <!-- 1947932 idready -->
Op iOS-apparaten kunt u een VPN-profiel maken dat gebruikmaakt van een IKEv2-verbinding (**apparaatconfiguratie** > **profielen** > **profiel maken** > **IOS/iPadOS** voor platform > **VPN** voor profiel type). In een toekomstige update kunt u altijd configureren met IKEv2. Wanneer de IKEv2 VPN-profielen zijn geconfigureerd, worden automatisch verbinding gemaakt en blijven verbonden (of snel opnieuw verbinding maken) met het VPN. Het blijft verbonden, zelfs bij het verplaatsen tussen netwerken of het opnieuw opstarten van apparaten.

Op iOS is de altijd VPN-verbinding beperkt tot IKEv2-profielen.

Als u wilt zien welke IKEv2-instellingen u momenteel kunt configureren, gaat u naar [VPN-instellingen toevoegen op iOS-apparaten in Microsoft Intune](../configuration/vpn-settings-ios.md#ikev2-settings).

Van toepassing op:
- iOS

### <a name="improved-user-interface-experience-when-creating-configuration-profiles-on-ios-and-macos-devices---5569008-5569039-5569057-5569110-5569116-5569131-5569139-5569153-5859984-idready---"></a>Verbeterde gebruikers interface-ervaring bij het maken van configuratie profielen op iOS-en macOS-apparaten<!-- 5569008-5569039-5569057-5569110-5569116-5569131-5569139-5569153-5859984 idready -->
Wanneer u een profiel voor iOS-of macOS-apparaten maakt, wordt de ervaring in het beheer centrum voor het endpoint Management bijgewerkt. Deze wijziging is van invloed op de volgende apparaatconfiguratie-profielen (**apparaten** > **configuratie profielen** > **profiel maken** > **IOS** of **macOS** voor platform):

- Aangepast: iOS, macOS
- Apparaatfuncties: iOS, macOS
- Beperkingen voor apparaten: iOS, macOS
- Endpoint Protection: macOS
- Extensies: macOS
- Voorkeurs bestand: macOS

### <a name="improved-user-interface-experience-when-creating-oemconfig-configuration-profiles-on-android-enterprise-devices---5568645-idready----"></a>Verbeterde gebruikers interface-ervaring bij het maken van OEMConfig-configuratie profielen op Android Enter prise-apparaten<!-- 5568645 idready  -->
Wanneer u een OEMConfig-profiel voor Android Enter prise-apparaten maakt of bewerkt, wordt de ervaring in het beheer centrum voor het endpoint Management bijgewerkt. De bijgewerkte ervaring bevat een overzicht van de instellingen die u in een oogopslag hebt geconfigureerd. Deze wijziging is van invloed op het configuratie Profiel van het OEMConfig (**apparaten** > **configuratie profielen** > **profiel maken** > **Android Enter prise** voor platform > **OEMConfig** voor profiel type).

Deze functie is van toepassing op:
- Android Enterprise 

<!-- ***********************************************-->
## <a name="device-enrollment"></a>Apparaatinschrijving

### <a name="block-android-enrollments-by-device-manufacturer--5197392-idready--"></a>Android-inschrijvingen op de fabrikant van het apparaat blok keren<!--5197392 idready-->
U kunt voor komen dat apparaten worden inge schreven op basis van de fabrikant van het apparaat. Dit geldt voor apparaten met Android-Apparaatbeheer en Android-werk profielen voor bedrijven. Als u registratie beperkingen wilt zien, gaat u naar het [beheer centrum van micro soft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)> **apparaten** > **registratie beperkingen**.



<!-- ***********************************************-->
## <a name="device-management"></a>Apparaatbeheer


### <a name="new-information-in-device-details---4471759-5604099----"></a>Nieuwe informatie in details van apparaat<!-- 4471759 5604099  -->
De volgende informatie wordt toegevoegd aan de **overzichts** pagina voor apparaten:
- Geheugen capaciteit (hoeveelheid fysiek geheugen op het apparaat)
- Opslag capaciteit (hoeveelheid fysieke opslag op het apparaat) 
- Type en snelheid van de CPU-processor
- RAM-en processor gegevens

<!-- ***********************************************-->
<!--## Intune apps-->
 

<!-- ***********************************************-->

<!--
## Monitoring and troubleshooting
-->


<!-- ***********************************************-->
## <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer

### <a name="new-intune-built-in-role-endpoint-security-manager--4253397-idready--"></a>Nieuwe ingebouwde functie Endpoint Security Manager van intune<!--4253397 idready-->
Er is een nieuwe ingebouwde intune-rol beschikbaar: Endpoint Security Manager. Deze nieuwe rol biedt beheerders volledige toegang tot het knoop punt van het eindpunt beheer in intune en alleen-kant-en-klare toegang tot andere gebieden. De rol is een uitbrei ding van de rol ' beveiligings beheerder ' van Azure AD. Als u momenteel alleen globale beheerders als rollen hebt, zijn er geen wijzigingen nodig. Als u rollen gebruikt, en u de granulariteit wilt zien die het Endpoint Security Manager biedt, wijst u die rol toe wanneer deze beschikbaar is. Zie [op rollen gebaseerd toegangs beheer](role-based-access-control.md)voor meer informatie over ingebouwde rollen.

### <a name="intune-roles-user-interface-changes-coming--5801612-idready--"></a>Wijzigingen in de gebruikers interface van intune-rollen<!--5801612 idready-->
De gebruikers interface voor het beheer [centrum van micro soft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) > **Tenant beheer** > **rollen** worden gewijzigd in een gebruiks vriendelijk en intuïtief ontwerp. Deze ervaring biedt dezelfde instellingen en details die u nu gebruikt. de nieuwe ervaring maakt echter gebruik van een wizard-achtige procedure.


<!-- ***********************************************-->
## <a name="security"></a>Beveiliging

### <a name="derived-credentials-support-on-android-cobo-devices--4839592--"></a>Ondersteuning voor afgeleide referenties op Android COBO-apparaten<!--4839592-->
U kunt afgeleide referenties gebruiken op door Android Enter prise volledig beheerde apparaten. Ondersteuning wordt opgenomen voor het ophalen van een afgeleide referentie voor Entrust Datacard, interDISAe en Purebred. U kunt een afgeleide referentie gebruiken voor verificatie van de app, Wi-Fi, VPN of S/MIME-ondertekening en/of versleuteling met apps die dit ondersteunen. 

<!-- ***********************************************-->
## <a name="notices"></a>Mededelingen

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Zie tevens
Voor meer informatie over recente ontwikkelingen raadpleegt u [Wat is er nieuw in Microsoft Intune?](whats-new.md).


