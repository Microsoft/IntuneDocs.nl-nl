---
title: Wi-Fi-instellingen importeren voor Windows-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Exporteer Wi-Fi-instellingen van een Windows-apparaat als een XML-bestand met behulp van netsh wlan. Importeer dit bestand vervolgens in Intune om een Wi-Fi-profiel te maken voor apparaten met Windows 8.1, Windows 10 en Windows Holographic for Business.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/18/2018
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 40569af35a812074cc62546e3f85929416202b3b
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72506426"
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
3. Voer de opdracht `netsh wlan show profiles` uit en noteer de naam van het profiel dat u wilt exporteren. In dit voorbeeld is de naam van het profiel **WiFiName**.
4. Voer de opdracht `netsh wlan export profile name="ProfileName" folder=c:\Wifi` uit. Met deze opdracht wordt in uw doelmap een Wi-Fi-profielbestand met de naam **Wi-Fi-WiFiName.xml** gemaakt.

## <a name="import-the-wi-fi-settings-into-intune"></a>De Wi-Fi-instellingen importeren in Intune

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Geef een **naam** en **beschrijving** op voor het beperkingsprofiel voor het apparaat.

    > [!IMPORTANT]
    > - De naam **moet** overeenkomen met het naamkenmerk in het XML-bestand van het Wi-Fi-profiel. Anders mislukt de bewerking.
    > - Als u een Wi-Fi-profiel met een vooraf gedeelde sleutel exporteert, **moet** u `key=clear` aan de opdracht toevoegen. Voer bijvoorbeeld `netsh wlan export profile name="ProfileName" key=clear folder=c:\Wifi` in.
    > - Door gebruik van een vooraf gedeelde sleutel met Windows 10 wordt een herstelfout weergegeven in Intune. Als dit gebeurt, wordt het Wi-Fi-profiel correct toegewezen aan het apparaat en werkt het profiel zoals verwacht.
    > - Als u een Wi-Fi-profiel met een vooraf gedeelde sleutel exporteert, moet u ervoor zorgen dat het bestand is beveiligd. De sleutel bestaat uit tekst zonder opmaak. Het is dus uw verantwoordelijkheid om de sleutel te beveiligen.

4. In **Platform** selecteert u **Windows 8.1 en hoger**.
5. In **profieltype** selecteert u **Wi-Fi importeren**.
6. Configureer de volgende instellingen:
    - **Verbindingsnaam**: voer een naam voor de Wi-Fi-verbinding in. Deze naam wordt weergegeven voor eindgebruikers wanneer ze door de beschikbare Wi-Fi-netwerken bladeren.
    - **Profiel XML**: selecteer de bladerknop en kies het xml-bestand met de Wi-Fi-profielinstellingen die u wilt importeren.
    - **Bestandsinhoud**: hier wordt de XML-code weergegeven voor het configuratieprofiel dat u hebt geselecteerd.
7. Wanneer u klaar bent, selecteert u **OK** > **Maken** om uw wijzigingen op te slaan. Het profiel wordt gemaakt en wordt weergegeven in de lijst met profielen.

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt niets. Vervolgens [wijst u dit profiel toe](device-profile-assign.md).

## <a name="more-resources"></a>Meer bronnen

[Overzicht Wi-Fi-instellingen](wi-fi-settings-configure.md), met inbegrip van andere platforms.
