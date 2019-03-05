---
title: Een Wi-Fi-profiel maken voor apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk de stappen voor het maken van een configuratieprofiel voor een Wi-Fi-apparaat in Microsoft Intune. Maak profielen voor Android, Android Enterprise, Android kiosk, iOS, macOS, Windows 10 en hoger, en Windows Holografic for Business. Gebruik deze profielen voor het maken van een Wi-Fi-verbinding om certificaten te gebruiken, een EAP-type te kiezen, een verificatiemethode te selecteren, een proxy in te schakelen en meer.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/16/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2a11b99a52fe1aec8d8908cdffa2a763e7462bd4
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57233760"
---
# <a name="add-and-use-wi-fi-settings-on-your-devices-in-microsoft-intune"></a>Wi-Fi-instellingen toevoegen en gebruiken op uw apparaten in Microsoft Intune

Wi-Fi is een draadloos netwerk dat door veel mobiele apparaten wordt gebruikt om toegang tot het netwerk te krijgen. Microsoft Intune omvat ingebouwde Wi-Fi-instellingen die kunnen worden geïmplementeerd voor gebruikers en apparaten in uw organisatie. Deze groep instellingen wordt een 'profiel' genoemd en kan worden toegewezen aan verschillende gebruikers en groepen. Wanneer het profiel is toegewezen, krijgen uw gebruikers toegang tot het Wi-Fi-netwerk van uw organisatie zonder dat zij dit zelf hoeven te configureren.

U installeert bijvoorbeeld een nieuw Wi-Fi-netwerk met de naam Contoso Wi-Fi. U wilt vervolgens alle iOS-apparaten instellen om verbinding te maken met dit netwerk. Dit is het proces:

1. Maak een Wi-Fi-profiel met daarin de instellingen voor de verbinding met het draadloze netwerk Contoso Wi-Fi.
2. Wijs het profiel toe aan een groep die alle gebruikers van iOS-apparaten omvat.
3. Gebruikers vinden het nieuwe Contoso Wi-Fi-netwerk in de lijst met draadloze netwerken op hun apparaat. Ze kunnen dan verbinding maken met het netwerk via de door u gekozen verificatiemethode.

In dit artikel worden de stappen vermeld voor het maken van een Wi-Fi-profiel. Het bevat ook koppelingen die de verschillende instellingen voor elk platform beschrijven.

## <a name="supported-device-platforms"></a>Ondersteunde apparaatplatformen

Wi-Fi-profielen ondersteunen de volgende apparaatplatformen:

- Android 4 en hoger
- Android Enterprise en kiosk
- iOS 8.0 en hoger
- macOS (Max OS X 10.11 en hoger)
- Windows 10 en hoger, Windows 10 Mobile en Windows Holographic for Business

> [!NOTE]
> Voor apparaten met Windows 8.1 kunt u een Wi-Fi-configuratie importeren die eerder vanaf een andere apparaat is geëxporteerd.

## <a name="create-a-device-profile"></a>Een apparaatprofiel maken

1. Selecteer in de [Azure-portal](https://portal.azure.com) **Alle services** > filter op **Intune** en selecteer **Microsoft Intune**. 
2. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Geef een **naam** en **beschrijving** op voor het Wi-Fi-profiel.
4. Selecteer in de vervolgkeuzelijst **Platform** het apparaatplatform waarop u de Wi-Fi-instellingen wilt toepassen. Uw opties zijn:

    - **Android**
    - **Android Enterprise**
    - **iOS**
    - **macOS**
    - **Windows 8.1 en hoger**
    - **Windows 10 en hoger**

5. In **Profieltype**, kiest u **Wi-Fi**.

    - Voor **Android Enterprise**-apparaten die als kiosk draaien, kunt u **Alleen apparaateigenaar** > **Wi-Fi** kiezen.
    - Voor **Vensters 8.1 en hoger** kunt u **Wi-Fi-import** kiezen. Met deze optie kunt u Wi-Fi-instellingen die u eerder vanaf een ander apparaat hebt geëxporteerd, importeren als een XML-bestand.

6. Sommige van de Wi-Fi instellingen zijn verschillend voor elk platform. Om de instellingen voor een specifiek platform te bekijken, kiest u:

    - [Android](wi-fi-settings-android.md)
    - [Android Enterprise en kiosk](wi-fi-settings-android-enterprise.md)
    - [iOS](wi-fi-settings-ios.md)
    - [macOS](wi-fi-settings-macos.md)
    - [Windows 10 en hoger](wi-fi-settings-windows.md)
    - [Instellingen voor Windows 8.1 en hoger](wi-fi-settings-import-windows-8-1.md), inclusief Windows Holographic for Business

    De meeste platforms hebben **Basic**- en **Enterprise**-instellingen. **Basic** bevat functies zoals de netwerknaam en de SSID. Met **Enterprise** kunt u uitgebreidere informatie zoals het Extensible Authentication Protocol (EAP) opgeven.

7. Wanneer u klaar bent met het toevoegen van uw Wi-Fi-instellingen, selecteert u **Profiel maken** > **Maken** om het configuratieprofiel toe te voegen. Het profiel wordt gemaakt en wordt weergegeven in de lijst met profielen (**Apparaatconfiguratie** > **Profielen**).

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt niets. Vervolgens moet u [dit profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).
