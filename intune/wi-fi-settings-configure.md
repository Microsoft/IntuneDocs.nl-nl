---
title: Wi-Fi-instellingen configureren in Intune
titleSuffix: Microsoft Intune
description: In dit onderwerp leest u hoe u Microsoft Intune kunt gebruiken voor het configureren van Wi-Fi-verbindingen op de apparaten die u beheert.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9a550e2963fa60a91db3ef63f7771bc4ca352d98
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-configure-wi-fi-settings-in-microsoft-intune"></a>Wi-Fi-instellingen configureren in Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Gebruik Wi-Fi-profielen van Microsoft Intune om instellingen voor draadloze netwerken toe te wijzen aan gebruikers en apparaten in uw organisatie. Wanneer u een Wi-Fi-profiel toewijst, hebben uw gebruikers toegang tot uw zakelijke Wi-Fi-netwerk zonder dat ze dit zelf hoeven te configureren.

Een voorbeeld: u installeert een nieuw Wi-Fi-netwerk met de naam Contoso Wi-Fi en wilt instellen dat alle iOS-apparaten verbinding met dit netwerk maken. Dit is het proces:

1. Maak een Wi-Fi-profiel met de instellingen die nodig zijn om verbinding te maken met het draadloze netwerk Contoso Wi-Fi.
2. Wijs het profiel toe aan een groep met alle gebruikers van iOS-apparaten.
3. Gebruikers vinden het nieuwe Contoso Wi-Fi-netwerk in de lijst met draadloze netwerken op hun apparaat en kunnen gemakkelijk verbinding met dit netwerk maken.

## <a name="supported-device-platforms"></a>Ondersteunde apparaatplatformen

Wi-Fi-profielen ondersteunen de volgende apparaatplatformen:

- Android 4 en hoger
- Android for Work
- iOS 8.0 en hoger
- macOS (Max OS X 10.9 en hoger)

Voor apparaten met Windows 8.1, Windows 10, Windows 10 Mobile en Windows Holographic for Business kunt u een Wi-Fi-configuratie importeren die eerder van een andere apparaat is geëxporteerd.

Gebruik de informatie in dit onderwerp voor meer informatie over de basisbeginselen voor het configureren van een Wi-Fi-profiel en lees vervolgens de aanvullende onderwerpen voor elk platform voor meer apparaatspecifieke informatie.

## <a name="create-a-device-profile-containing-wi-fi-settings"></a>Een apparaatprofiel met Wi-Fi-instellingen maken

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies in het deelvenster **Intune** de optie **Apparaatconfiguratie**.
2. Kies in het deelvenster **Apparaatconfiguratie** onder de sectie **Beheren** de optie **Profielen**.
3. Kies **Profiel maken** in het deelvenster Profielen.
4. Voer in het deelvenster **Profiel maken** een **naam** en een **beschrijving** in voor het Wi-Fi-profiel.
5. Selecteer in de vervolgkeuzelijst **Platform** het apparaatplatform waarop u de Wi-Fi-instellingen wilt toepassen. Op dit moment kunt u een van de volgende platformen kiezen voor Wi-Fi-instellingen:
    - **Android**
    - **Android for Work**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 en hoger**
    - **Windows 10 en hoger**

   > [!IMPORTANT]
   > Als u een profiel voor Windows 10-apparaten maakt, met inbegrip van Windows Holographic for Business, moet u het platform **Windows 8.1 en hoger** kiezen. Het platform **Windows 10 en hoger** heeft geen Wi-Fi-profieltype. 

6. Voor Apple- of Android-apparaten kiest u in de vervolgkeuzelijst **Wi-Fi-type** de optie **Basic** of **Enterprise**. U kunt **Basic** gebruiken als u basisfuncties zoals de netwerknaam en de SSID wilt opgeven. Met **Enterprise** kunt u uitgebreidere informatie over EAP (Extensible Authentication Protocol) opgeven als dit protocol in uw Wi-Fi-netwerk wordt gebruikt. 

   Met het profiel **Wi-Fi importeren** (voor Windows 8.1 en later) kunt u Wi-Fi-instellingen die u eerder van een ander apparaat hebt geëxporteerd, importeren als een XML-bestand.
1. Welke instellingen u kunt configureren, is afhankelijk van het platform dat u hebt gekozen. Raadpleeg een van de volgende onderwerpen voor gedetailleerde instellingen voor elk platform:
    - [Instellingen voor Android en Android for Work](wi-fi-settings-android.md)
    - [iOS-instellingen](wi-fi-settings-ios.md)
    - [macOS-instellingen](wi-fi-settings-macos.md)
    - [Instellingen voor Windows 8.1 en hoger](wi-fi-settings-import-windows-8-1.md) (inclusief Windows Holographic for Business)
1. Als u klaar bent, gaat u terug naar het deelvenster **Profiel maken** en kiest u **Maken**.

Het profiel wordt gemaakt en wordt weergegeven in het deelvenster met de profielenlijst.

## <a name="next-steps"></a>Volgende stappen

Zie [How to assign device profiles](device-profile-assign.md) (Apparaatprofielen toewijzen) als u wilt doorgaan en dit profiel wilt toewijzen aan groepen.
