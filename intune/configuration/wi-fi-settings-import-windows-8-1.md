---
title: Wi-Fi-instellingen importeren voor Windows-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Exporteer Wi-Fi-instellingen van een Windows-apparaat als een XML-bestand met behulp van netsh wlan. Importeer dit bestand vervolgens in Intune om een Wi-Fi-profiel te maken voor apparaten met Windows 8.1, Windows 10 en Windows Holographic for Business.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/18/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f79ccdc71ddbfa3f25daef629515fb612de01852
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2019
ms.locfileid: "75207006"
---
# <a name="import-wi-fi-settings-for-windows-devices-in-intune"></a>Wi-Fi-instellingen importeren voor Windows-apparaten in Intune

Voor apparaten met Windows kunt u een Wi-Fi-configuratieprofiel importeren dat eerder naar een bestand is geëxporteerd. **Voor apparaten met Windows 10 en hoger kunt u ook rechtstreeks in Intune [een Wi-Fi-profiel maken](wi-fi-settings-windows.md)** .

Van toepassing op:  
- Windows 8.1 en hoger
- Windows 10 en hoger
- Windows 10 Desktop of Mobile
- Windows Holographic for Business

## <a name="export-wi-fi-settings-from-a-windows-device"></a>Wi-Fi-instellingen exporteren vanuit een Windows-apparaat

Gebruik in Windows `netsh wlan` om een bestaand Wi-Fi-profiel te exporteren naar een XML-bestand dat kan worden gelezen door Intune. De sleutel moet worden geëxporteerd als tekst zonder opmaak om het profiel te kunnen gebruiken.

Voer de volgende stappen uit op een Windows-computer waarop het vereiste Wi-Fi-profiel al is geïnstalleerd:

1. Maak een lokale map voor de geëxporteerde Wi-Fi-profielen, zoals **c:\WiFi**.
2. Open een opdrachtprompt als beheerder.
3. Voer de opdracht `netsh wlan show profiles` uit. Noteer de naam van het profiel dat u wilt exporteren. In dit voorbeeld is de naam van het profiel **WiFiName**.
4. Voer de opdracht `netsh wlan export profile name="ProfileName" folder=c:\Wifi` uit. Met deze opdracht wordt in uw doelmap een Wi-Fi-profielbestand met de naam **Wi-Fi-WiFiName.xml** gemaakt.

## <a name="import-the-wi-fi-settings-into-intune"></a>De Wi-Fi-instellingen importeren in Intune

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apparaten** > **Configuratieprofielen** > **Profiel maken**.
3. Voer de volgende instellingen in:

    - **Naam**: Voer een beschrijvende naam in voor het profiel. De naam **moet** overeenkomen met het naamkenmerk in het XML-bestand van het Wi-Fi-profiel. Anders mislukt de bewerking.
    - **Beschrijving**: Voer een beschrijving in met een overzicht van de instelling en eventuele andere belangrijke details.
    - **Platform**: Selecteer **Windows 8.1 en later**.
    - **Profieltype**: Selecteer **Wi-Fi importeren**.

    > [!IMPORTANT]
    > - Als u een Wi-Fi-profiel met een vooraf gedeelde sleutel exporteert, **moet** u `key=clear` aan de opdracht toevoegen. Voer bijvoorbeeld `netsh wlan export profile name="ProfileName" key=clear folder=c:\Wifi` in.
    > - Door gebruik te maken van een vooraf gedeelde sleutel met Windows 10 wordt een herstelfout in Intune weergegeven. Als dit gebeurt, wordt het Wi-Fi-profiel correct toegewezen aan het apparaat en werkt het profiel zoals verwacht.
    > - Als u een Wi-Fi-profiel met een vooraf gedeelde sleutel exporteert, moet u ervoor zorgen dat het bestand is beveiligd. De sleutel bestaat uit tekst zonder opmaak. Het is dus uw verantwoordelijkheid om de sleutel te beveiligen.

4. Voer de volgende instellingen in:

    - **Verbindingsnaam**: Voer een naam in voor de Wi-Fi-verbinding. Deze naam wordt weer gegeven aan gebruikers wanneer ze door de beschik bare Wi-Fi-netwerken bladeren.
    - **Profiel-XML**: Selecteer de bladerknop en selecteer het XML-bestand met de Wi-Fi-profielinstellingen die u wilt importeren.
    - **Bestandsinhoud**: Hier wordt de XML-code weergegeven voor het configuratieprofiel dat u hebt geselecteerd.

5. Selecteer **OK** om uw wijzigingen op te slaan.
6. Wanneer u klaar bent, selecteert u **OK** > **Maken** om het Intune-profiel te maken. Wanneer het profiel is gemaakt, wordt dit weergegeven in de lijst **Apparaten - Configuratieprofielen**.

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt niets. Vervolgens kunt u [het profiel toewijzen](../device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

Zie [Overzicht Wi-Fi-instellingen](wi-fi-settings-configure.md), met inbegrip van andere beschikbare platforms.
