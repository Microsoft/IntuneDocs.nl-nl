---
# required metadata

title: Instellingen voor nalevingsbeleid voor Android-apparaten | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Instellingen voor nalevingsbeleid voor Android-apparaten in Microsoft Intune

De beleidsinstellingen die in dit onderwerp worden beschreven, zijn van toepassing op apparaten met Android 4.0 en hoger en Samsung KNOX 4.0 of hoger.

Als u op zoek bent naar informatie over andere platforms, selecteert u een van de volgende opties:
> [!div class="op_single_selector"]
- [Instellingen voor nalevingsbeleid voor iOS-apparaten](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Instellingen voor nalevingsbeleid voor Windows-apparaten](windows-compliance-policy-settings-in-microsoft-intune.md)

## Systeembeveiligingsinstellingen
### Wachtwoord
- **Wachtwoord vereisen voor het ontgrendelen van mobiele apparaten**: stel dit in op **Ja** om te vereisen dat gebruikers een wachtwoord invoeren om
  toegang te krijgen tot hun apparaat.

-  **Minimale wachtwoordlengte**: hiermee geeft u het minimale aantal cijfers of tekens aan waaruit het wachtwoord van de gebruiker moet bestaan.

- **Wachtwoordkwaliteit**: gebruik deze instelling om de wachtwoordvereisten voor Android-apparaten in te stellen. U kunt kiezen uit:
  -   **Lage beveiligingsbiometrie**
  - **Vereist**
  -   **Ten minste numeriek**
  -   **Ten minste alfabetisch**
  -   **Ten minste alfanumeriek**
  -   **Alfanumeriek met tekens**

- **Minuten inactief voordat wachtwoord is vereist**: hiermee geeft u aan na hoeveel niet-actieve tijd gebruikers hun wachtwoord opnieuw moeten invoeren.

- **Verlopen van wachtwoorden (dagen)**: selecteer het aantal dagen waarna het wachtwoord van gebruikers verloopt
  en ze een nieuw wachtwoord moeten maken.

- **Wachtwoordgeschiedenis onthouden**: gebruik deze instelling in combinatie met **Wachtwoorden niet opnieuw gebruiken** om te voorkomen dat gebruikers
  eerder gebruikte wachtwoorden opnieuw gebruiken.

- **Wachtwoorden niet opnieuw gebruiken**: als **Wachtwoordgeschiedenis onthouden** is geselecteerd, geeft u op
  hoeveel eerder gebruikte wachtwoorden niet opnieuw mogen worden gebruikt.

- **Wachtwoord vereisen wanneer het apparaat wordt geactiveerd vanuit een niet-actieve status:**
  Deze instelling dient te worden gebruikt in combinatie met de instelling **Minuten inactief voordat wachtwoord is vereist**. De eindgebruikers wordt gevraagd een wachtwoord op te geven als ze toegang willen krijgen tot een apparaat dat inactief is geweest gedurende de periode die is opgegeven in de
  instelling **Minuten inactief voordat wachtwoord vereist is**.

### Versleuteling
- **Versleuteling vereisen voor mobiel apparaat**: stel dit in op **Ja** om te vereisen dat apparaten worden
  versleuteld om verbinding te kunnen maken met resources. Apparaten worden
  versleuteld wanneer u de instelling **Wachtwoord vereisen voor
  het ontgrendelen van mobiele apparaten** configureert.

## Instellingen voor de status van het apparaat

- **Het apparaat mag niet gekraakt of geroot zijn**: als u deze instelling inschakelt,
  worden gekraakte apparaten gemarkeerd als niet-compatibel.

## Instellingen voor apparaateigenschappen
- **Minimale versie van het besturingssysteem dat is vereist**: wanneer een apparaat niet voldoet aan de vereiste voor de
  minimale besturingssysteemversie, wordt deze gemarkeerd als niet-compatibel.
  Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. De eindgebruiker kan dan kiezen om een upgrade van zijn apparaat uit te voeren, waarna die toegang tot bedrijfsbronnen krijgt.

- **Maximale versie van het besturingssysteem dat is toegestaan**: wanneer een apparaat gebruikmaakt van
  een versie van het besturingssysteem die hoger is dan wat in de regel is bepaald, wordt de toegang tot bedrijfsbronnen geblokkeerd en wordt de gebruiker gevraagd contact op te nemen met zijn IT-beheerder. Tot er een wijziging is doorgevoerd in de regel die de versie van het besturingssysteem toestaat, kan dit apparaat niet worden gebruikt om toegang tot bedrijfsbronnen te krijgen.


<!--HONumber=May16_HO1-->


