---
title: Wat zijn apparaatprofielen in Microsoft Intune? | Microsoft Docs
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: meer informatie over Intune-apparaatprofielen en hoe u ze kunt gebruiken bij het beheren en beveiligen van apparaten in uw bedrijf.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/16/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: f9e8a5deb17ebb77d480213567e5ccf6550e3493
ms.openlocfilehash: c7ddc58d15ea260b31adad0bab65428df7e4b9ac
ms.contentlocale: nl-nl
ms.lasthandoff: 05/03/2017


---

# <a name="what-are-microsoft-intune-device-profiles"></a>Wat zijn Microsoft Intune-apparaatprofielen?

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Gebruik de Microsoft Intune-workload **Apparaatconfiguratie** om instellingen en functies te beheren op alle apparaten die u beheert. U zult deze workload voornamelijk gebruiken om apparaatprofielen te maken, waarmee u vele verschillende functies kunt beheren en configureren op de apparaten die u beheert.

Als u deze workload opent, ziet u de volgende opties:

- **Overzicht**: deze pagina biedt u statusinformatie en rapporten die u helpen apparaatconfiguraties te bewaken die u hebt toegewezen aan gebruikers en apparaten.
- **Profielen beheren**: in deze sectie kunt u apparaatconfiguratieprofielen maken. U vindt hieronder een lijst met alle profieltypen die u kunt maken.
- **Certificeringsinstantie instellen**: deze werkstroom leidt u door de stappen die nodig zijn om certificaten te configureren. U moet dit doen als u met Intune-certificaatprofielen wilt werken.

## <a name="getting-started"></a>Aan de slag

De werkstroom voor het maken van apparaatprofielen is gelijk voor alle profielen. Lees [How to create Microsoft Intune device configuration profiles](/intune-azure/configure-devices/how-to-create-device-profiles) (Microsoft Intune-apparaatconfiguratieprofielen maken) voor informatie over het maken van profielen. Lees vervolgens verder voor specifieke informatie over het maken van instellingen voor elk profieltype.

U kunt de volgende mogelijkheden op uw apparaten beheren:

## <a name="device-features"></a>Apparaatfuncties

Met apparaatfuncties kunt u functies op iOS- en macOS-apparaten beheren, zoals AirPrint, meldingen en configuraties voor gedeelde apparaten.
Zie [Instellingen voor apparaatfuncties configureren](how-to-configure-device-features.md) voor meer informatie. Biedt ondersteuning voor: iOS en macOS.

## <a name="device-restrictions"></a>Apparaatbeperkingen
Met apparaatbeperkingen kunt u verschillende instellingen bepalen die u voor diverse categorieën beheert, zoals beveiliging, browsers, hardware en instellingen voor het delen van gegevens. U kunt bijvoorbeeld een apparaatbeperkingsprofiel maken waarmee wordt voorkomen dat gebruikers van iOS-apparaten toegang kunnen krijgen tot de camera van het apparaat.
Zie [How to configure device restriction settings](how-to-configure-device-restrictions.md) (Apparaatbeperkingsinstellingen configureren) voor meer informatie. Ondersteunt: Android, iOS, macOS, Windows 10 en Windows 10 Team.

## <a name="email"></a>E-mail
U kunt met e-mailprofielen de e-mailinstellingen voor Exchange ActiveSync maken, toewijzen en bewaken op apparaten die u beheert. Door deze instellingen toe te wijzen, zorgt u voor consistentie, vermindert u ondersteuningsaanvragen en biedt u eindgebruikers toegang tot bedrijfse-mail op hun eigen apparaten zonder dat ze instellingen hoeven op te geven.
Zie [How to configure email settings](how-to-configure-email-settings.md) (E-mailinstellingen configureren) voor meer informatie. Ondersteunt: Android, iOS, Windows Phone 8.1 en Windows 10.

## <a name="wi-fi"></a>Wi-Fi
Gebruik Wi-Fi-profielen om instellingen voor draadloze netwerken toe te wijzen voor gebruikers en apparaten in uw organisatie. Wanneer u een Wi-Fi-profiel toewijst, hebben uw gebruikers toegang tot uw zakelijke Wi-Fi zonder dat ze dit zelf hoeven te configureren.
Zie [How to configure Wi-Fi settings](how-to-configure-wi-fi-settings.md) (Wi-Fi-instellingen configureren) voor meer informatie. Ondersteunt: Android, iOS, macOS en Windows Phone 8.1 (alleen importeren).

## <a name="vpn"></a>VPN
Met virtuele particuliere netwerken (VPN's) geeft u uw gebruikers veilige externe toegang tot uw bedrijfsnetwerk. Apparaten gebruiken een VPN-verbindingsprofiel om een verbinding met de VPN-server op te zetten. Gebruik VPN-profielen om VPN-instellingen toe te wijzen aan gebruikers en apparaten in uw organisatie, zodat deze gemakkelijk en veilig verbinding met het netwerk kunnen maken.
Zie [VPN-instellingen configureren](how-to-configure-vpn-settings.md) voor meer informatie.
Ondersteunt: Android, iOS, macOS, Windows Phone 8.1, Windows 8.1 en Windows 10.

## <a name="education"></a>Education
Hiermee kunt u opties configureren voor de Windows Toets maken-app. Wanneer u deze opties configureert, kunnen er geen andere apps op het apparaat worden uitgevoerd totdat de toets is voltooid.
Zie [Opleidingsinstellingen configureren](how-to-configure-education-settings.md) voor meer informatie

## <a name="certificates"></a>Certificaten
Met dit profieltype kunt u vertrouwde, SCEP- en PKCS-certificaten configureren die kunnen worden toegewezen aan apparaten en kunnen worden gebruikt voor het verifiëren van Wi-Fi-, VPN- en e-mailprofielen.
Zie [How to configure certificates](how-to-configure-certificates.md) (Certificaten configureren) voor meer informatie. Ondersteunt: Android, iOS, Windows Phone 8.1, Windows 8.1 en Windows 10.

## <a name="edition-upgrade"></a>Editie-upgrade
Met dit profieltype kunt u automatisch apparaten met bepaalde versies van Windows 10 naar een nieuwere editie bijwerken. Zie [Editie-upgrades voor Windows 10 configureren](how-to-configure-windows-10-edition-upgrade.md) voor meer informatie. Ondersteunt: alleen Windows 10.

## <a name="windows-information-protection"></a>Windows Information Protection
Windows Information Protection helpt bij de beveiliging tegen gegevenslekken zonder dat de gebruikerservaring van werknemers hierdoor wordt beïnvloed. Het helpt tevens zakelijke apps en gegevens te beschermen tegen onbedoelde gegevenslekken op apparaten die eigendom zijn van de onderneming en persoonlijke apparaten die werknemers meenemen naar het werk, zonder dat hiervoor wijzigingen nodig zijn aan uw omgeving of andere apps.
Zie [Windows-gegevensbescherming configureren](how-to-configure-windows-information-protection.md) voor meer informatie. Ondersteunt: alleen Windows 10.

## <a name="custom"></a>Aangepast
U kunt met aangepaste instellingen apparaatinstellingen toewijzen die niet zijn ingebouwd in Intune. U kunt bijvoorbeeld op Android-apparaten OMA-URI-waarden opgeven waarmee het apparaat wordt geconfigureerd. Voor iOS-apparaten kunt u een configuratiebestand importeren dat u in Apple Configurator hebt gemaakt.
Zie [Aangepaste instellingen configureren](how-to-configure-custom-settings.md) voor meer informatie. Ondersteunt: Android, iOS, macOS en Windows Phone 8.1.

