---
title: Nalevingsinstellingen voor Windows 8.1 in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk een overzicht van alle instellingen die u kunt gebruiken bij het instellen van naleving voor uw Windows 8.1- en Windows Phone 8.1-apparaten in Microsoft Intune. Controleer naleving van het minimale en maximale besturingssysteem, stel wachtwoordbeperkingen en -lengte in, schakel versleuteling voor de gegevensopslag in en meer.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/04/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4ed863378616f8001beab89177c642404287e7d3
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2019
ms.locfileid: "59424933"
---
# <a name="windows-81-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Windows 8.1-instellingen om te markeren of apparaten wel of niet conform zijn met behulp van Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Dit artikel bevat een overzicht en beschrijving van de verschillende instellingen die u kunt configureren op Windows 8.1-apparaten in Intune. Gebruik als deze instellingen als onderdeel van uw MDM-oplossing (Mobile Device Management) om eenvoudige wachtwoorden te blokkeren, een minimale en maximale versie van het besturingssysteem in te stellen, en meer.

Deze functie is van toepassing op:

- Windows Phone 8.1
- Windows 8.1 en hoger

Gebruik deze nalevingsinstellingen als Intune-beheerder om de resources van uw organisatie beter te beschermen. Zie [Aan de slag met apparaatnalevingsbeleid](device-compliance-get-started.md) voor meer informatie over nalevingsbeleid en wat dit doet.

## <a name="before-you-begin"></a>Voordat u begint

[Een nalevingsbeleid maken](create-compliance-policy.md#create-the-policy). Voor **Platform**, selecteert u **Windows Phone 8.1** of **Windows 8.1 en hoger**.

## <a name="device-properties"></a>Apparaateigenschappen

- **Minimale versie van het besturingssysteem die is vereist**: Voer de minimaal toegestane versie in. Als een apparaat niet voldoet aan de minimumvereisten met betrekking tot de versie van het besturingssysteem, wordt dit apparaat gerapporteerd als niet-conform. Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. Gebruikers kunnen dan kiezen om een upgrade van hun apparaat uit te voeren, waarna ze toegang tot bedrijfsresources krijgen.
- **Maximale versie van besturingssysteem die is toegestaan**: Voer de maximaal toegestane versie in. Wanneer een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie die is ingevoerd in de regel, wordt de toegang tot bedrijfsresources geblokkeerd. De gebruiker wordt gevraagd contact op te nemen met de IT-beheerder. Het apparaat heeft geen toegang tot organisatieresources totdat u de regel wijzigt zodat de versie van het besturingssysteem is toegestaan.

Windows 8.1-pc's retourneren versie **3**. Als de besturingssysteemversieregel is ingesteld op Windows 8.1 voor Windows, wordt het apparaat gerapporteerd als niet-conform, zelfs als het apparaat Windows 8.1 heeft.

## <a name="system-security"></a>Systeembeveiliging

### <a name="password"></a>Wachtwoord

- **Een wachtwoord vereisen voor het ontgrendelen van mobiele apparaten**: **verplicht** gebruikers een wachtwoord in te voeren om toegang te krijgen tot hun apparaat.
- **Eenvoudige wachtwoorden**: stel deze optie in op **Blokkeren** zodat de gebruiker geen eenvoudig wachtwoord kan maken, zoals **1234** of **1111**. Stel deze optie in op **Niet geconfigureerd** om gebruikers toe te staan wachtwoorden als **1234** of **1111** te maken.
- **Minimale wachtwoordlengte**: voer het minimale aantal cijfers of tekens aan waaruit het wachtwoord moet bestaan.

  Voor apparaten waarop Windows wordt uitgevoerd en met een Microsoft-account toegankelijk zijn, kan het nalevingsbeleid niet correct evalueren:
  - Als de minimale wachtwoordlengte langer is dan acht tekens
  - Of als het minimale aantal tekensets meer is dan twee

- **Wachtwoordtype**: kies of een wachtwoord alleen **numerieke** tekens mag bevatten of uit een combinatie van cijfers en andere tekens moet bestaan (**alfanumeriek**).
  
  - **Aantal niet-alfanumerieke tekens in wachtwoord**: als **Vereist wachtwoordtype** is ingesteld op **Alfanumeriek**, wordt met deze instelling het minimale aantal tekensets opgegeven waaruit het wachtwoord moet bestaan. De vier tekensets zijn:
    - Kleine letters
    - Hoofdletters
    - Symbolen
    - Getallen

    Als u een hogere waarde instelt, moet de gebruiker een wachtwoord maken dat complexer is. Voor apparaten die toegankelijk zijn met een Microsoft-account, kan het nalevingsbeleid niet juist worden geëvalueerd:

    - Als de minimale wachtwoordlengte langer is dan acht tekens
    - Of als het minimale aantal tekensets meer is dan twee

- **Maximum aantal minuten van inactiviteit voordat wachtwoord is vereist**: geef aan na hoeveel niet-actieve tijd de gebruiker het wachtwoord opnieuw moet invoeren.
- **Wachtwoord verloopt (in dagen)**: selecteer het aantal dagen waarna het wachtwoord verloopt en gebruikers een nieuw wachtwoord moeten maken.
- **Aantal eerdere wachtwoorden dat niet opnieuw mag worden gebruikt**: voer het aantal eerder gebruikte wachtwoorden in dat niet opnieuw mag worden gebruikt.

### <a name="encryption"></a>Versleuteling

- **Versleuteling vereisen op een mobiel apparaat**: **vereis** dat het apparaat versleuteld moet zijn om verbinding te maken met gegevensopslag-resources.

Selecteer **OK** > **Maken** om uw wijzigingen op te slaan.

## <a name="next-steps"></a>Volgende stappen

- [Voeg acties voor niet-conforme apparaten toe](actions-for-noncompliance.md) en [gebruik bereiktags om beleidsregels te filteren](scope-tags.md).
- [Controleer uw nalevingsbeleid](compliance-policy-monitor.md).
- Zie de [Instellingen voor nalevingsbeleid voor apparaten met Windows 10 en later](compliance-policy-create-windows.md).