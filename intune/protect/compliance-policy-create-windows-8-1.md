---
title: Nalevingsinstellingen voor Windows 8.1 in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk een overzicht van alle instellingen die u kunt gebruiken bij het instellen van naleving voor uw Windows 8.1- en Windows Phone 8.1-apparaten in Microsoft Intune. Controleer naleving van het minimale en maximale besturingssysteem, stel wachtwoordbeperkingen en -lengte in, schakel versleuteling voor de gegevensopslag in en meer.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/22/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3e074d922078a9772ca67a6ebd99948bc3e64601
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72813209"
---
# <a name="windows-81-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>Windows 8.1-instellingen om te markeren of apparaten wel of niet conform zijn met behulp van Intune

Dit artikel bevat een overzicht en beschrijving van de verschillende instellingen die u kunt configureren op Windows 8.1-apparaten in Intune. Gebruik als deze instellingen als onderdeel van uw MDM-oplossing (Mobile Device Management) om eenvoudige wachtwoorden te blokkeren, een minimale en maximale versie van het besturingssysteem in te stellen, en meer.

Deze functie is van toepassing op:

- Windows Phone 8.1
- Windows 8.1 en hoger

Gebruik deze nalevingsinstellingen als Intune-beheerder om de resources van uw organisatie beter te beschermen. Zie [Aan de slag met apparaatnalevingsbeleid](device-compliance-get-started.md) voor meer informatie over nalevingsbeleid en wat dit doet.

## <a name="before-you-begin"></a>Voordat u begint

[Een nalevingsbeleid maken](create-compliance-policy.md#create-the-policy). Voor **Platform**, selecteert u **Windows Phone 8.1** of **Windows 8.1 en hoger**.

## <a name="device-properties"></a>Apparaateigenschappen

### <a name="operating-system-version"></a>Versie van besturingssysteem

**Windows Phone 8.1 en hoger**
- **Minimale versie van het besturings systeem voor mobiele apparaten**:  
  Voer de mini maal toegestane versie in. Als een apparaat niet voldoet aan de minimumvereisten met betrekking tot de versie van het besturingssysteem, wordt dit apparaat gerapporteerd als niet-conform. Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. Apparaatgebruikers kunnen kiezen om een upgrade van hun apparaat uit te voeren, waarna ze toegang tot bedrijfsresources krijgen.

- **Maximum versie van het besturings systeem voor mobiele apparaten**:  
  Voer de Maxi maal toegestane versie in. Wanneer een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie die in de regel is ingevoerd, wordt de toegang tot organisatieresources geblokkeerd. De apparaatgebruiker wordt gevraagd contact op te nemen met de IT-beheerder. Op dit apparaat kan geen toegang worden verkregen tot organisatorische resources zolang een regel niet zodanig is gewijzigd dat de versie van het besturingssysteem is toegestaan.

**Windows 8.1 en hoger**
- **Minimale versie van het besturingssysteem**:  
  Voer de mini maal toegestane versie in. Als een apparaat niet voldoet aan de minimumvereisten met betrekking tot de versie van het besturingssysteem, wordt dit apparaat gerapporteerd als niet-conform. Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. Apparaatgebruikers kunnen kiezen om een upgrade van hun apparaat uit te voeren, waarna ze toegang tot bedrijfsresources krijgen.

- **Maximale versie van het besturingssysteem**:  
  Voer de Maxi maal toegestane versie in. Wanneer een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie die in de regel is ingevoerd, wordt de toegang tot organisatieresources geblokkeerd. De apparaatgebruiker wordt gevraagd contact op te nemen met de IT-beheerder. Op dit apparaat kan geen toegang worden verkregen tot organisatorische resources zolang een regel niet zodanig is gewijzigd dat de versie van het besturingssysteem is toegestaan.

Windows 8.1-pc's retourneren versie **3**. Als de besturingssysteemversieregel is ingesteld op Windows 8.1 voor Windows, wordt het apparaat gerapporteerd als niet-conform, zelfs als het apparaat Windows 8.1 heeft.

## <a name="system-security"></a>Systeembeveiliging

### <a name="password"></a>Wachtwoord

- **Wachtwoord vereist voor het ontgrendelen van mobiele apparaten**:  
  - **Niet geconfigureerd** (*standaard*) - Deze instelling wordt niet beoordeeld op naleving of niet-naleving.
  - **Vereisen** - Gebruikers moeten een wachtwoord invoeren voordat ze toegang kunnen krijgen tot hun apparaat.

- **Eenvoudige wachtwoorden**:  
  - **Niet geconfigureerd** (*standaard*): gebruikers kunnen eenvoudige wacht woorden maken, zoals **1234** of **1111**.
  - **Blokkeren** - Gebruikers kunnen geen eenvoudige wachtwoorden maken, zoals **1234** of **1111**.  

- **Minimale wachtwoordlengte**:  
  Voer het aantal cijfers of tekens in waaruit het wachtwoord minimaal moet bestaan.

  Voor apparaten waarop Windows wordt uitgevoerd en die worden geopend met een Microsoft-account, kan het nalevings beleid niet correct worden geëvalueerd als aan een van de volgende voor waarden wordt voldaan:  
  - De minimale wachtwoordlengte is langer dan acht tekens
  - Het minimumaantal tekensets is meer dan twee

- **Wachtwoordtype**:  
  Kies of een wachtwoord alleen **numerieke** tekens mag bevatten of uit een combinatie van cijfers en andere tekens moet bestaan (**alfanumeriek**).

  Als deze optie is ingesteld op *alfanumeriek*, is de volgende instelling beschikbaar.  

  - **Het aantal niet-alfanumerieke tekens in het wachtwoord**:  
    Wanneer het *wachtwoord type* is ingesteld op **alfanumeriek**, geeft u het minimum aantal teken sets op waaruit het wacht woord moet bestaan. Opties zijn **0** tot **4** sets, met een standaard waarde van **1**.
    
    De vier tekensets zijn:
    - Kleine letters
    - Hoofdletters
    - Symbolen
    - Getallen

    Als u een hogere waarde instelt, moet de gebruiker een wachtwoord maken dat complexer is. Voor apparaten die worden geopend met een Microsoft-account, kan het nalevings beleid niet correct worden geëvalueerd als aan een van de volgende voor waarden wordt voldaan:

    - De minimale wachtwoordlengte is langer dan acht tekens
    - Het minimumaantal tekensets is meer dan twee

- **Maximum aantal minuten inactief voordat wachtwoord is vereist**:  
  Voer in na hoeveel niet-actieve tijd gebruikers hun wachtwoord opnieuw moeten invoeren.

- **Wachtwoordverlooptijd (dagen)** :  
  Selecteer het aantal dagen waarna het wachtwoord verloopt en gebruikers een nieuw wachtwoord moeten maken.

- **Aantal eerdere wachtwoorden dat niet opnieuw mag worden gebruikt**:  
  Voer het aantal eerder gebruikte wachtwoorden in dat niet opnieuw mag worden gebruikt.

### <a name="encryption"></a>Versleuteling

- **Versleuteling van gegevensopslag op apparaat**:  
  - **Niet geconfigureerd** (*standaard*)
  - **Vereisen** - Gebruik *Vereisen* om de gegevensopslag op uw apparaten te versleutelen.


<!-- not on phone   
- **Require encryption on mobile device**: **Require** the device to be encrypted to connect to data storage resources.
--> 

## <a name="next-steps"></a>Volgende stappen

- [Voeg acties voor niet-conforme apparaten toe](actions-for-noncompliance.md) en [gebruik bereiktags om beleidsregels te filteren](../fundamentals/scope-tags.md).
- [Controleer uw nalevingsbeleid](compliance-policy-monitor.md).
- Zie de [Instellingen voor nalevingsbeleid voor apparaten met Windows 10 en later](compliance-policy-create-windows.md).