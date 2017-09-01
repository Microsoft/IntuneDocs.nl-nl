---
title: Wat zijn apparaatprofielen in Microsoft Intune?
titleSuffix: Intune on Azure
description: Meer informatie over Intune-apparaatprofielen en hoe u ze kunt gebruiken bij het beheren en beveiligen van apparaten in uw bedrijf.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 95ce3b6a307a71431b9717abdc3980f15a916a18
ms.sourcegitcommit: 4dc5bed94cc965a54eacac2d87fb2d49c9300c3a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/25/2017
---
# <a name="what-are-microsoft-intune-device-profiles"></a>Wat zijn Microsoft Intune-apparaatprofielen?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Gebruik de Microsoft Intune-workload **Apparaatconfiguratie** om instellingen en functies te beheren op alle apparaten die u beheert. U gebruikt deze workload voornamelijk om apparaatprofielen te maken, waarmee u vele verschillende functies kunt beheren en configureren op apparaten.

Als u deze workload opent, ziet u de volgende opties:

- **Overzicht**: deze pagina biedt u statusinformatie en rapporten die u helpen apparaatconfiguraties te bewaken die u hebt toegewezen aan gebruikers en apparaten.
- **Profielen beheren**: in deze sectie kunt u apparaatconfiguratieprofielen maken. U vindt verderop in dit onderwerp een lijst met alle profieltypen die u kunt maken.
- **Certificeringsinstantie instellen**: deze werkstroom leidt u door de stappen die nodig zijn om Intune-certificaatprofielen te configureren.

## <a name="getting-started"></a>Aan de slag

De werkstroom voor het maken van apparaatprofielen is gelijk voor alle profielen. Lees [Apparaatconfiguratieprofielen maken in Microsoft Intune](device-profile-create.md) voor informatie over het maken van profielen. Lees vervolgens verder voor specifieke informatie over het maken van instellingen voor elk profieltype.

U kunt de volgende mogelijkheden op uw apparaten beheren:

## <a name="device-features"></a>Apparaatfuncties

Met apparaatfuncties kunt u functies op iOS- en macOS-apparaten beheren, zoals AirPrint, meldingen en configuraties voor gedeelde apparaten.
Zie [Instellingen voor apparaatfuncties configureren](device-features-configure.md) voor meer informatie. Biedt ondersteuning voor: iOS en macOS.

## <a name="device-restrictions"></a>Apparaatbeperkingen
Met apparaatbeperkingen kunt u allerlei instellingen uit verschillende categorieën beheren, zoals beveiliging, hardware en instellingen voor het delen van gegevens. U kunt bijvoorbeeld een apparaatbeperkingsprofiel maken waarmee wordt voorkomen dat gebruikers van iOS-apparaten toegang kunnen krijgen tot de camera van het apparaat.
Zie [Instellingen voor apparaatfuncties configureren in Microsoft Intune](device-restrictions-configure.md) voor meer informatie. Ondersteunt: Android, iOS, macOS, Windows 10 en Windows 10 Team.

## <a name="email"></a>E-mail
U kunt met e-mailprofielen de e-mailinstellingen voor Exchange ActiveSync maken, toewijzen en bewaken op apparaten die u beheert. E-mailprofielen zorgen voor consistentie, verminderen het aantal ondersteuningsaanvragen en bieden u eindgebruikers toegang tot bedrijfse-mail op hun eigen apparaten zonder dat ze instellingen hoeven op te geven.
Zie [E-mailinstellingen configureren in Microsoft Intune](email-settings-configure.md) voor meer informatie. Ondersteunt: Android, iOS, Windows Phone 8.1 en Windows 10.

## <a name="wi-fi"></a>Wi-Fi
Gebruik Wi-Fi-profielen om instellingen voor draadloze netwerken toe te wijzen voor gebruikers en apparaten in uw organisatie. Wanneer u een Wi-Fi-profiel toewijst, hebben uw gebruikers toegang tot uw zakelijke Wi-Fi zonder dat ze dit zelf hoeven te configureren.
Zie [Wi-Fi-instellingen configureren in Microsoft Intune](wi-fi-settings-configure.md) voor meer informatie. Ondersteunt: Android, iOS, macOS en Windows Phone 8.1 (alleen importeren).

## <a name="vpn"></a>VPN
Met virtuele particuliere netwerken (VPN's) geeft u uw gebruikers veilige externe toegang tot uw bedrijfsnetwerk. Apparaten gebruiken een VPN-verbindingsprofiel om een verbinding met de VPN-server op te zetten. Wijs VPN-profielen toe aan gebruikers en apparaten in uw organisatie, zodat deze gemakkelijk en veilig verbinding met het netwerk kunnen maken.
Zie [VPN-instellingen configureren](vpn-settings-configure.md) voor meer informatie.
Ondersteunt: Android, iOS, macOS, Windows Phone 8.1, Windows 8.1 en Windows 10.

## <a name="education"></a>Education
Hiermee kunt u opties configureren voor de Windows Toets maken-app. Wanneer u deze opties configureert, kunnen er geen andere apps op het apparaat worden uitgevoerd totdat de toets is voltooid.
Zie [Opleidingsinstellingen configureren](education-settings-configure.md) voor meer informatie

## <a name="certificates"></a>Certificaten
Met dit profieltype kunt u vertrouwde, SCEP- en PKCS-certificaten configureren die kunnen worden toegewezen aan apparaten en kunnen worden gebruikt voor het verifiëren van Wi-Fi-, VPN- en e-mailprofielen.
Zie [Certificaten configureren in Microsoft Intune](certificates-configure.md) voor meer informatie. Ondersteunt: Android, iOS, Windows Phone 8.1, Windows 8.1 en Windows 10.

## <a name="edition-upgrade"></a>Editie-upgrade
Met dit profieltype kunt u apparaten waarop een bepaalde versie van Windows 10 wordt uitgevoerd, automatisch upgraden naar een nieuwere versie.
Zie [Editie-upgrades voor Windows 10 configureren in Microsoft Intune](edition-upgrade-configure-windows-10.md) voor meer informatie. Ondersteunt: alleen Windows 10.

## <a name="endpoint-protection"></a>Endpoint Protection
Met dit profieltype kunt u BitLocker- en Windows Defender-instellingen configureren voor Windows 10-apparaten.
Zie [Endpoint protection settings for Windows 10 and later in Microsoft Intune](endpoint-protection-windows-10.md) (Instellingen voor de beveiliging van eindpunten voor Windows 10 en hoger) voor meer informatie.

## <a name="windows-information-protection"></a>Windows Information Protection
Windows Information Protection helpt bij de beveiliging tegen gegevenslekken zonder dat de gebruikerservaring van werknemers hierdoor wordt beïnvloed. Het helpt tevens zakelijke apps en gegevens te beschermen tegen onbedoelde gegevenslekken op apparaten die eigendom zijn van de onderneming en persoonlijke apparaten die werknemers meenemen naar het werk, zonder dat hiervoor wijzigingen nodig zijn aan uw omgeving of andere apps.
Zie [Windows-gegevensbescherming configureren](windows-information-protection-configure.md) voor meer informatie. Ondersteunt: alleen Windows 10.

## <a name="custom"></a>Aangepast
U kunt met aangepaste instellingen apparaatinstellingen toewijzen die niet zijn ingebouwd in Intune. U kunt bijvoorbeeld op Android-apparaten OMA-URI-waarden opgeven waarmee het apparaat wordt geconfigureerd. Voor iOS-apparaten kunt u een configuratiebestand importeren dat u in Apple Configurator hebt gemaakt.
Zie [Aangepaste apparaatinstellingen configureren in Microsoft Intune](custom-settings-configure.md) voor meer informatie. Ondersteunt: Android, iOS, macOS en Windows Phone 8.1.

## <a name="next-steps"></a>Volgende stappen
Kies een van de profieltypen in de lijst om apparaten te gaan configureren.
