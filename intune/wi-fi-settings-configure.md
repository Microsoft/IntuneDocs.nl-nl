---
title: Wi-Fi-instellingen configureren in Intune
titleSuffix: Azure portal
description: In dit onderwerp leest u hoe u Intune kunt gebruiken voor het configureren van Wi-Fi-verbindingen op de apparaten die u beheert."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1fadb488-9c6c-43c1-ba23-8c69db633b96
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ae5210cb3da5503c4cf1b85be8b8522fa1cfd6ce
ms.sourcegitcommit: 1df625330f4e8f7f661b5f2b9f16b5590971838d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/10/2017
---
# <a name="how-to-configure-wi-fi-settings-in-microsoft-intune"></a>Wi-Fi-instellingen configureren in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Gebruik Wi-Fi-profielen van Microsoft Intune om instellingen voor draadloze netwerken toe te wijzen aan gebruikers en apparaten in uw organisatie. Wanneer u een Wi-Fi-profiel toewijst, hebben uw gebruikers toegang tot uw zakelijke Wi-Fi-netwerk zonder dat ze dit zelf hoeven te configureren.

Een voorbeeld: u installeert een nieuw Wi-Fi-netwerk met de naam Contoso Wi-Fi en wilt instellen dat alle iOS-apparaten verbinding met dit netwerk maken. Dit is het proces:

1. Maak een Wi-Fi-profiel met de instellingen die nodig zijn om verbinding te maken met het draadloze netwerk Contoso Wi-Fi.
2. Wijs het profiel toe aan een groep met alle gebruikers van iOS-apparaten.
3. Gebruikers vinden het nieuwe Contoso Wi-Fi-netwerk in de lijst met draadloze netwerken op hun apparaat en kunnen gemakkelijk verbinding met dit netwerk maken.

Wi-Fi-profielen ondersteunen de volgende apparaatplatformen:

- Android 4 en hoger
- Android for Work
- iOS 8.0 en hoger
- macOS (Max OS X 10.9 en hoger)

Voor apparaten met Windows 8.1, Windows 10 en Windows 10 Mobile kunt u een Wi-Fi-configuratie importeren die eerder van een andere apparaat is geëxporteerd.

Gebruik de informatie in dit onderwerp voor meer informatie over de basisbeginselen voor het configureren van een Wi-Fi-profiel en lees vervolgens de aanvullende onderwerpen voor elk platform voor meer apparaatspecifieke informatie.

## <a name="create-a-device-profile-containing-wi-fi-settings"></a>Een apparaatprofiel met Wi-Fi-instellingen maken

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies op de blade **Intune** de optie **Apparaatconfiguratie**.
2. Kies **Beheren** > **Profielen** op de blade **Apparaatconfiguratie**.
3. Kies **Profiel maken** op de blade Profielen.
4. Voer op de blade **Profiel maken** een **naam** en een **beschrijving** in voor het Wi-Fi-profiel.
5. Selecteer in de vervolgkeuzelijst **Platform** het apparaatplatform waarop u de Wi-Fi-instellingen wilt toepassen. Op dit moment kunt u een van de volgende platformen kiezen voor Wi-Fi-instellingen:
    - **Android**
    - **Android for Work**
    - **iOS**
    - **macOS**
    - **Windows 8.1 en hoger (een profiel importeren)**
6. Kies **Wi-Fi Basic** of **Wi-Fi Enterprise** in de vervolgkeuzelijst **Profieltype**. U kunt **Wi-Fi Basic** gebruiken als u basisfuncties zoals de netwerknaam en de SSID wilt opgeven. Met **Wi-Fi Enterprise** kunt u uitgebreidere informatie over EAP (Extensible Authentication Protocol) opgeven als dit protocol in uw Wi-Fi-netwerk wordt gebruikt. Met **Wi-Fi importeren** (voor Windows 8.1 en Windows 10) kunt u Wi-Fi-instellingen die u eerder van een ander apparaat hebt geëxporteerd, importeren als een XML-bestand.
7. Welke instellingen u kunt configureren, is afhankelijk van het platform dat u hebt gekozen. Raadpleeg een van de volgende onderwerpen voor gedetailleerde instellingen voor elk platform:
    - [Instellingen voor Android en Android for Work](wi-fi-settings-android.md)
    - [iOS-instellingen](wi-fi-settings-ios.md)
    - [macOS-instellingen](wi-fi-settings-macos.md)
    - [Windows Phone 8.1-instellingen](wi-fi-settings-import-windows-8-1.md)
8. Als u klaar bent, gaat u terug naar de blade **Profiel maken** en kiest u **Maken**.

Het profiel wordt gemaakt en wordt weergegeven op de blade met de profielenlijst.
Zie [How to assign device profiles](device-profile-assign.md) (Apparaatprofielen toewijzen) als u wilt doorgaan en dit profiel wilt toewijzen aan groepen.
