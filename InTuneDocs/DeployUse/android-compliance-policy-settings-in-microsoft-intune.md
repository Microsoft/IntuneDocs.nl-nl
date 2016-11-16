---
title: Instellingen voor nalevingsbeleid voor Android-apparaten | Microsoft Intune
description: In dit onderwerp worden de instellingen voor het nalevingsbeleid voor Android-apparaten beschreven.
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e24de6814d9e01c64768f425e961a7822f4b27a1
ms.openlocfilehash: 5f02618da6fb3c538ad131fe8abaf35a6be6e177


---


# Instellingen voor nalevingsbeleid voor Android-apparaten in Microsoft Intune

De beleidsinstellingen die in dit onderwerp worden beschreven, zijn van toepassing op apparaten met Android 4.0 en hoger en Samsung KNOX 4.0 of hoger.

Als u op zoek bent naar informatie over andere platforms, selecteert u een van de volgende opties:
> [!div class="op_single_selector"]
- [Instellingen voor nalevingsbeleid voor iOS-apparaten](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Instellingen voor nalevingsbeleid voor Windows-apparaten](windows-compliance-policy-settings-in-microsoft-intune.md)

## Systeembeveiligingsinstellingen
### Wachtwoord
- **Een wachtwoord vereisen voor het ontgrendelen van mobiele apparaten:** stel deze optie in op **Ja** als u gebruikers wilt verplichten een wachtwoord in te voeren om toegang te krijgen tot hun apparaat.

-  **Minimale wachtwoordlengte**: hiermee geeft u het minimale aantal cijfers of tekens aan waaruit het wachtwoord van de gebruiker moet bestaan.

- **Wachtwoordkwaliteit:** met deze instelling wordt gedetecteerd of de vereisten voor het wachtwoord die u opgeeft, op het apparaat zijn geconfigureerd. Gebruik deze instelling als u wilt afdwingen dat gebruikers voldoen aan bepaalde wachtwoordvereisten voor Android-apparaten. U kunt kiezen uit:

  -   **Lage beveiligingsbiometrie**
  -   **Vereist**
  -   **Ten minste numeriek**
  -   **Ten minste alfabetisch**
  -   **Ten minste alfanumeriek**
  -   **Alfanumeriek met tekens**

- **Minuten inactief voordat wachtwoord is vereist:** hiermee geeft u aan na hoeveel niet-actieve tijd gebruikers hun wachtwoord opnieuw moeten invoeren.

- **Wachtwoord verloopt (in dagen):** selecteer het aantal dagen waarna het wachtwoord van gebruikers verloopt en ze een nieuw wachtwoord moeten maken.

- **Wachtwoordgeschiedenis onthouden:** gebruik deze instelling samen met **Wachtwoorden niet opnieuw gebruiken** om te voorkomen dat gebruikers eerder gebruikte wachtwoorden opnieuw gebruiken.

- **Wachtwoorden niet opnieuw gebruiken:** als u **Wachtwoordgeschiedenis onthouden** hebt geselecteerd, geeft u het aantal eerder gebruikte wachtwoorden op dat niet opnieuw kan worden gebruikt.

- **Wachtwoord vereisen wanneer het apparaat wordt geactiveerd vanuit een niet-actieve status:** gebruik deze instelling samen met de instelling **Minuten van inactiviteit voordat wachtwoord vereist is**. De gebruiker wordt gevraagd een wachtwoord op te geven om toegang te krijgen tot een apparaat dat inactief is geweest gedurende de tijd die is opgegeven bij de instelling **Minuten van inactiviteit voordat wachtwoord vereist is**.

### Versleuteling
- **Versleuteling vereisen op een mobiel apparaat:** stel deze optie in op **Ja** als u wilt dat apparaten moeten worden versleuteld om verbinding te maken met resources. Apparaten worden versleuteld wanneer u de instelling **Wachtwoord vereisen voor het ontgrendelen van mobiele apparaten** kiest.

## Status en beveiligingsinstellingen van apparaat

- **Apparaat mag niet gekraakt of geroot zijn**: als u deze instelling inschakelt, worden apparaten die zijn gekraakt of geroot als niet-compatibel beschouwd.
- **Vereisen dat de installatie van apps van onbekende bronnen wordt voorkomen (Android 4.0 en hoger)** Als u apparaten wilt blokkeren waarop **Beveiliging** > **Onbekende bronnen** op het apparaat is ingeschakeld, moet u deze instelling inschakelen en op **Ja** instellen.  
>[!IMPORTANT]
>Voor sideloading-toepassingen moet de instelling **Onbekende bronnen** zijn ingeschakeld. Dwing dit nalevingsbeleid alleen af als u Android-apps niet met behulp van sideloading op apparaten laadt.

- **Vereisen dat de USB-foutopsporing is uitgeschakeld (Android 4.2 of hoger)**: deze instelling bepaalt of moet worden gedetecteerd of de USB-foutopsporingsoptie op het apparaat is ingeschakeld.
- **Vereisen dat Apparaat scannen op beveiligingsbedreigingen is ingeschakeld op apparaten (Android 4.2 - 4.4)**: deze instelling geeft aan dat de functie **Apps controleren** is ingeschakeld op het apparaat.
- **Minimaal niveau voor de Android-beveiligingspatch (Android 6.0 of hoger)**: gebruik deze instelling om het minimale Android-patchniveau op te geven. Apparaten die niet ten minste dit patchniveau hebben, worden als niet-compatibel gezien. De datum moet de volgende notatie hebben: dd-mm-jjjj.
- **Vereisen dat Device Threat Protection wordt ingeschakeld**: Gebruik deze instelling om de risicobeoordeling uit de Lookout MTP-oplossing als voorwaarde voor naleving te gebruiken. Kies het maximaal toegestane bedreigingsniveau. U kunt daarbij kiezen uit:

  - **Geen (beveiligd)**: dit is het meest veilige niveau. Dit betekent dat er op het apparaat geen bedreigingen mogen staan. Als een van de bedreigingsniveaus voor het apparaat wordt gedetecteerd, wordt het apparaat geëvalueerd als niet-compatibel.
  - **Laag**: het apparaat wordt als compatibel geëvalueerd als er bedreigingen van een laag niveau aanwezig zijn. Als een hoger niveau wordt aangetroffen, krijgt het apparaat de status niet-compatibel.
  - **Gemiddeld**: Het apparaat wordt als compatibel geëvalueerd als de bedreigingen op het apparaat van laag of gemiddeld niveau zijn. Als bedreigingen met hoog niveau worden aangetroffen op het apparaat, wordt het apparaat als niet-compatibel beoordeeld.
  - **Hoog**: dit is de minst veilige optie. In principe zijn hierdoor alle bedreigingsniveaus toegestaan. Het is wellicht het beste als u deze oplossing alleen gebruikt voor rapportagedoeleinden.

  Zie [De regel Device Threat Protection inschakelen in het nalevingsbeleid](enable-device-threat-protection-rule-in-compliance-policy.md) voor meer informatie.

## Instellingen voor apparaateigenschappen
- **Minimale versie van het besturingssysteem die is vereist:** wanneer een apparaat niet voldoet aan de minimumvereisten met betrekking tot de versie van het besturingssysteem wordt dit apparaat gerapporteerd als niet-compatibel.
  Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. Gebruikers kunnen dan kiezen om een upgrade van hun apparaat uit te voeren, waarna ze toegang tot bedrijfsbronnen krijgen.

- **Maximale versie van het besturingssysteem die is toegestaan:** wanneer een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie die in de regel is opgegeven, wordt de toegang tot bedrijfsresources geblokkeerd en wordt de gebruiker gevraagd contact op te nemen met de IT-beheerder. Totdat er een wijziging is doorgevoerd in regels om de versie van het besturingssysteem toe te staan, kan dit apparaat niet worden gebruikt om toegang tot bedrijfsbronnen te krijgen.



<!--HONumber=Oct16_HO3-->


