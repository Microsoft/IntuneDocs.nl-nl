---
title: Instellingen voor nalevingsbeleid voor Android for Work | Microsoft Docs
description: In dit onderwerp worden de instellingen beschreven voor het nalevingsbeleid voor Android-apparaten die compatibel zijn met Android for Work.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 2b53e7a410d0ce268ce395c08161095af42857b7


---


# <a name="compliance-policy-settings-for-android-for-work-devices-in-microsoft-intune"></a>Instellingen voor nalevingsbeleid voor Android for Work-apparaten in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

De beleidsinstellingen die in dit onderwerp worden beschreven, zijn van toepassing op Android for Work-apparaten.

Als u op zoek bent naar informatie over andere platforms, selecteert u een van de volgende opties:
> [!div class="op_single_selector"]
- [Instellingen voor nalevingsbeleid voor Android](android-compliance-policy-settings-in-microsoft-intune.md)
- [Instellingen voor nalevingsbeleid voor iOS-apparaten](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Instellingen voor nalevingsbeleid voor Windows-apparaten](windows-compliance-policy-settings-in-microsoft-intune.md)

## <a name="system-security-settings"></a>Systeembeveiligingsinstellingen
### <a name="password"></a>Wachtwoord
- **Een wachtwoord vereisen voor het ontgrendelen van mobiele apparaten:** stel deze optie in op **Ja** als u gebruikers wilt verplichten een wachtwoord in te voeren om toegang te krijgen tot hun apparaat.

-  **Minimale wachtwoordlengte**: hiermee geeft u het minimale aantal cijfers of tekens aan waaruit het wachtwoord van de gebruiker moet bestaan.

- **Wachtwoordkwaliteit:** met deze instelling wordt gedetecteerd of de vereisten voor het wachtwoord die u opgeeft op het apparaat zijn geconfigureerd. Gebruik deze instelling als u wilt afdwingen dat gebruikers bepaalde wachtwoordvereisten voor Android-apparaten instellen. U kunt kiezen uit:
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

### <a name="encryption"></a>Versleuteling
- **Versleuteling vereisen op mobiel apparaat:** u hoeft deze instelling niet te configureren, omdat versleuteling wordt afgedwongen op Android for Work-apparaten.

## <a name="device-health-and-security-settings"></a>Status en beveiligingsinstellingen van apparaat

- **Jailbreaken of uitvoeren als rootgebruiker niet toegestaan:** als u deze instelling inschakelt, worden apparaten waarop jailbreaking is uitgevoerd of die als rootgebruiker worden uitgevoerd als niet-compatibel beschouwd.
- **Vereisen dat de installatie van apps van onbekende bronnen worden voorkomen:** u hoeft deze instelling niet te configureren, omdat installatie van onbekende bronnen altijd wordt voorkomen op Android for Work-apparaten. .  

- **Vereisen dat USB-foutopsporing is uitgeschakeld**: u hoeft deze instelling niet te configureren, omdat USB-foutopsporing altijd al is uitgeschakeld op Android for Work-apparaten.

- **Minimaal niveau voor de Android-beveiligingspatch**: gebruik deze instelling om het minimale Android-patchniveau op te geven.  Apparaten die niet ten minste dit patchniveau hebben, worden als niet-compatibel gezien. De datum moet de volgende notatie hebben: dd-mm-jjjj.
- **Vereisen dat Device Threat Protection wordt ingeschakeld**: Gebruik deze instelling om de risicobeoordeling uit de Lookout MTP-oplossing als voorwaarde voor naleving te gebruiken. Selecteer het maximaal toegestane bedreigingsniveau. U kunt daarbij kiezen uit:

  - **Geen (beveiligd)**: Dit is het veiligste niveau. Dit betekent dat er op het apparaat geen bedreigingen mogen staan. Als een van de bedreigingsniveaus voor het apparaat wordt gedetecteerd, wordt het apparaat geëvalueerd als niet-compatibel.
  - **Laag**: Het apparaat wordt als compatibel geëvalueerd als er bedreigingen met een laag niveau op staan. Als een hoger niveau wordt aangetroffen, krijgt het apparaat de status niet-compatibel.
  - **Gemiddeld**: Het apparaat wordt als compatibel geëvalueerd als de bedreigingen op het apparaat van laag of gemiddeld niveau zijn. Als bedreigingen met hoog niveau worden aangetroffen op het apparaat, wordt het apparaat als niet-compatibel beoordeeld.
  - **Hoog**: Dit is de minst veilige optie. Het komt erop neer dat alle bedreigingniveaus worden toegestaan. Dit kan misschien alleen nuttig zijn als u dit alleen voor rapportagedoeleinden gebruikt.

  Zie [De regel Device Threat Protection inschakelen in het nalevingsbeleid](enable-device-threat-protection-rule-in-compliance-policy.md) voor meer informatie.

## <a name="device-property-settings"></a>Instellingen voor apparaateigenschappen
- **Minimale versie van het besturingssysteem die is vereist:** wanneer een apparaat niet voldoet aan de minimumvereisten met betrekking tot de versie van het besturingssysteem wordt dit apparaat gerapporteerd als niet-compatibel.
  Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. De eindgebruiker kan dan kiezen om een upgrade van zijn apparaat uit te voeren, waarna die toegang tot bedrijfsbronnen krijgt.

- **Maximale versie van het besturingssysteem die is toegestaan:** wanneer een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie die in de regel is opgegeven, wordt de toegang tot bedrijfsresources geblokkeerd en wordt de gebruiker gevraagd contact op te nemen met de IT-beheerder. Tot er een wijziging is doorgevoerd in de regel die de versie van het besturingssysteem toestaat, kan dit apparaat niet worden gebruikt om toegang tot bedrijfsbronnen te krijgen.



<!--HONumber=Dec16_HO2-->


