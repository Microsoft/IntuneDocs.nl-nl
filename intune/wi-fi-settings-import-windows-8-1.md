---
title: Wi-Fi-instellingen importeren voor Windows 8.1 en hoger
titleSuffix: Microsoft Intune
description: Wi-Fi-instellingen van Windows in een Intune-Wi-Fi-profiel importeren.
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 890a10ecf4212656c189adaf46bb2839898758c1
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/08/2018
---
# <a name="import-wi-fi-settings-for-windows-81-and-later-devices-in-microsoft-intune"></a>Wi-Fi-instellingen voor apparaten met Windows 8.1 en hoger in Microsoft Intune importeren

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Voor apparaten met Windows 8.1, Windows 10 Desktop of Mobile of Windows Holographic for Business kunt u een Wi-Fi-configuratieprofiel importeren dat eerder naar een bestand is geëxporteerd.

## <a name="export-wi-fi-settings-from-a-windows-device"></a>Wi-Fi-instellingen exporteren vanuit een Windows-apparaat

Gebruik in Windows het hulpprogramma **netsh wlan** om een bestaand Wi-Fi-profiel te exporteren naar een XML-bestand dat kan worden gelezen door Intune. Volg de volgende procedure op een Windows-computer waarop het vereiste Wi-Fi-profiel is geïnstalleerd.
1. Maak een lokale map voor de geëxporteerde Wi-Fi-profielen, zoals **c:\WiFi**.
1. Open een opdrachtprompt als beheerder.
1. Voer de opdracht **netsh wlan show profiles** uit en noteer de naam van het profiel dat u wilt exporteren. In dit voorbeeld is de naam van het profiel **WiFiName**.
1. Voer de volgende opdracht uit: **netsh wlan export profile name="ProfileName" folder=c:\Wifi**. Hiermee wordt in de doelmap een Wi-Fi-profielbestand met de naam **Wi-Fi-WiFiName.xml** gemaakt.

## <a name="import-the-wi-fi-settings-into-intune"></a>De Wi-Fi-instellingen importeren in Intune

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies in het deelvenster **Intune** de optie **Apparaatconfiguratie**.
4. Kies in het deelvenster **Apparaatconfiguratie** onder de sectie **Beheren** de optie **Profielen**.
5. Klik op **Profiel maken** in het deelvenster Profielen.
6. Voer in het deelvenster **Profiel maken** een **naam** en **beschrijving** in voor het apparaatbeperkingsprofiel.


   > [!WARNING]
   > De naam **moet** overeenkomen met het naamkenmerk in het xml-bestand van het Wi-Fi-profiel, anders mislukt dit.

7. Kies in de vervolgkeuzelijst **Platform** de optie **Windows 8.1 en hoger**.
8. Kies in de vervolgkeuzelijst **Profieltype** de optie **Wi-Fi importeren**.
9. Configureer in het deelvenster **Wi-Fi** de volgende instellingen:
    - **Verbindingsnaam**: voer de naam van de Wi-Fi-verbinding in. Deze naam wordt weergegeven voor eindgebruikers wanneer ze door de beschikbare Wi-Fi-netwerken bladeren.
    - **XML-bestand voor het profiel**: klik op de knop Bladeren om het XML-bestand met de Wi-Fi-profielinstellingen te selecteren dat u in Intune wilt importeren.
    - **Bestandsinhoud**: hier wordt de XML-code weergegeven voor het configuratieprofiel dat u hebt geselecteerd.
10. Als u klaar bent, kiest u **OK**, gaat u terug naar het deelvenster **Profiel maken** en kiest u **Maken**.

Het profiel wordt gemaakt en wordt weergegeven in het deelvenster met de profielenlijst.
