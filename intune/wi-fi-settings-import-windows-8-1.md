---
title: Wi-Fi-instellingen importeren voor Windows 8.1 en hoger
titleSuffix: Microsoft Intune
description: Wi-Fi-instellingen van Windows in een Intune-Wi-Fi-profiel importeren.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 157416738e4607d5022f1c3c7ed8251a8e32fe3e
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
ms.locfileid: "31834013"
---
# <a name="import-wi-fi-settings-for-windows-81-and-later-devices-in-microsoft-intune"></a>Wi-Fi-instellingen voor apparaten met Windows 8.1 en hoger in Microsoft Intune importeren

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Voor apparaten met Windows 8.1, Windows 10 Desktop of Mobile of Windows Holographic for Business kunt u een Wi-Fi-configuratieprofiel importeren dat eerder naar een bestand is geëxporteerd.

## <a name="export-wi-fi-settings-from-a-windows-device"></a>Wi-Fi-instellingen exporteren vanuit een Windows-apparaat

Gebruik in Windows het hulpprogramma **netsh wlan** om een bestaand Wi-Fi-profiel te exporteren naar een XML-bestand dat kan worden gelezen door Intune. De sleutel moet worden geëxporteerd als tekst zonder opmaak om het profiel te kunnen gebruiken.

Voer de volgende stappen uit op een Windows-computer waarop het vereiste Wi-Fi-profiel al is geïnstalleerd:

1. Maak een lokale map voor de geëxporteerde Wi-Fi-profielen, zoals **c:\WiFi**.
2. Open een opdrachtprompt als beheerder.
3. Voer de opdracht `netsh wlan show profiles` uit en noteer de naam van het profiel dat u wilt exporteren. In dit voorbeeld is de naam van het profiel **WiFiName**.
4. Voer de opdracht `netsh wlan export profile name="ProfileName" folder=c:\Wifi` uit. Hiermee wordt in de doelmap een Wi-Fi-profielbestand gemaakt met de naam **Wi-Fi-WiFiName.xml**.

## <a name="import-the-wi-fi-settings-into-intune"></a>De Wi-Fi-instellingen importeren in Intune

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
4. Geef een **naam** en **beschrijving** op voor het beperkingsprofiel voor het apparaat.

    > [!IMPORTANT]
    > - De naam **moet** overeenkomen met het naamkenmerk in het XML-bestand van het Wi-Fi-profiel. Anders mislukt de bewerking.
    > - Als u een Wi-Fi-profiel met een vooraf gedeelde sleutel exporteert, **moet** u `key=clear` aan de opdracht toevoegen. Voer bijvoorbeeld `netsh wlan export profile name="ProfileName" key=clear folder=c:\Wifi` in.
    > - Door gebruik van een vooraf gedeelde sleutel met Windows 10 wordt een herstelfout weergegeven in Intune. Als dit gebeurt, wordt het Wi-Fi-profiel correct toegewezen aan het apparaat en werkt het profiel zoals verwacht.
    > - Als u een Wi-Fi-profiel met een vooraf gedeelde sleutel exporteert, moet u ervoor zorgen dat het bestand is beveiligd. De sleutel bestaat uit tekst zonder opmaak. Het is dus uw verantwoordelijkheid om de sleutel te beveiligen.

5. In **Platform** selecteert u **Windows 8.1 en hoger**.
6. In **profieltype** selecteert u **Wi-Fi importeren**.
7. Configureer de volgende instellingen:
  - **Verbindingsnaam**: voer een naam voor de Wi-Fi-verbinding in. Deze naam wordt weergegeven voor eindgebruikers wanneer ze door de beschikbare Wi-Fi-netwerken bladeren.
  - **XML-bestand voor het profiel**: selecteer de knop Bladeren om het XML-bestand met de Wi-Fi-profielinstellingen te selecteren dat u in Intune wilt importeren.
  - **Bestandsinhoud**: hier wordt de XML-code weergegeven voor het configuratieprofiel dat u hebt geselecteerd.
8. Als u bent klaar, kiest u **OK** en klikt u vervolgens op **Maken** van het profiel.

Het profiel wordt gemaakt en wordt weergegeven in de lijst met profielen.
