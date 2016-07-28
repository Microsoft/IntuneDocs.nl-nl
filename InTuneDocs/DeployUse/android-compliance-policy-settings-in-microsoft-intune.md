---
title: Instellingen voor nalevingsbeleid voor Android-apparaten | Microsoft Intune
description: In dit onderwerp worden de instellingen voor het nalevingsbeleid voor Android-apparaten beschreven.
keywords: 
author: karthikaraman
manager: jeffgilb
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 359f76daa35a14e4107a9e03c6a1b1f4d1215777
ms.openlocfilehash: 38763f73ebb3e6d629c2e7ea43ad34514a8b3ad5


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

- **Wachtwoordkwaliteit**: gebruik deze instelling om de wachtwoordvereisten voor Android-apparaten in te stellen. U kunt kiezen uit:
  -   **Lage beveiligingsbiometrie**
  - **Vereist**
  -   **Ten minste numeriek**
  -   **Ten minste alfabetisch**
  -   **Ten minste alfanumeriek**
  -   **Alfanumeriek met tekens**

- **Minuten inactief voordat wachtwoord is vereist:** hiermee geeft u aan na hoeveel niet-actieve tijd gebruikers hun wachtwoord opnieuw moeten invoeren.

- **Wachtwoord verloopt (in dagen):** selecteer het aantal dagen waarna het wachtwoord van gebruikers verloopt en ze een nieuw wachtwoord moeten maken.

- **Wachtwoordgeschiedenis onthouden:** gebruik deze instelling in combinatie met **Wachtwoorden niet opnieuw gebruiken** om te voorkomen dat gebruikers eerder gebruikte wachtwoorden opnieuw gebruiken.

- **Wachtwoorden niet opnieuw gebruiken:** als **Wachtwoordgeschiedenis onthouden** is geselecteerd, geeft u het aantal eerder gebruikte wachtwoorden op dat niet opnieuw kan worden gebruikt.

- **Een wachtwoord vereisen wanneer het apparaat wordt geactiveerd vanuit een niet-actieve status:** deze instelling moet worden gebruikt samen met de instelling **Minuten van inactiviteit voordat het wachtwoord wordt vereist**. Eindgebruikers wordt gevraagd een wachtwoord op te geven om toegang te krijgen tot een apparaat dat inactief is geweest gedurende de tijd die is opgegeven bij de instelling **Minuten van inactiviteit voordat wachtwoord vereist is**.

### Versleuteling
- **Versleuteling vereisen op een mobiel apparaat:** stel deze optie in op **Ja** als u wilt dat apparaten moeten worden versleuteld om verbinding te maken met resources. Apparaten worden versleuteld wanneer u de instelling **Wachtwoord vereisen voor het ontgrendelen van mobiele apparaten** configureert.

## Instellingen voor de status van het apparaat

- **Jailbreaken of uitvoeren als rootgebruiker niet toegestaan:** als u deze instelling inschakelt, worden apparaten waarop jailbreaking is uitgevoerd of die als rootgebruiker worden uitgevoerd als niet-compatibel beschouwd.

## Instellingen voor apparaateigenschappen
- **Minimale versie van het besturingssysteem die is vereist:** wanneer een apparaat niet voldoet aan de minimumvereisten met betrekking tot de versie van het besturingssysteem wordt dit apparaat gerapporteerd als niet-compatibel.
  Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. De eindgebruiker kan dan kiezen om een upgrade van zijn apparaat uit te voeren, waarna die toegang tot bedrijfsbronnen krijgt.

- **Maximale versie van het besturingssysteem die is toegestaan:** wanneer een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie die in de regel is opgegeven, wordt de toegang tot bedrijfsresources geblokkeerd en wordt de gebruiker gevraagd contact op te nemen met de IT-beheerder. Tot er een wijziging is doorgevoerd in de regel die de versie van het besturingssysteem toestaat, kan dit apparaat niet worden gebruikt om toegang tot bedrijfsbronnen te krijgen.



<!--HONumber=Jul16_HO3-->


