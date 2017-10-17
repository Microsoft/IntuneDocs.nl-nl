---
title: Instellingen voor het nalevingsbeleid voor Android
description: In dit onderwerp worden de instellingen voor het nalevingsbeleid voor Android-apparaten beschreven.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f781c5498a569a067f0f2aa6f780a6cc37c9985c
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/10/2017
---
# <a name="compliance-policy-settings-for-android-devices-in-microsoft-intune"></a>Instellingen voor nalevingsbeleid voor Android-apparaten in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

De beleidsinstellingen die in dit onderwerp worden beschreven, zijn van toepassing op apparaten met Android 4.0 en hoger en Samsung KNOX 4.0 of hoger.

Als u op zoek bent naar informatie over andere platforms, selecteert u een van de volgende opties:
> [!div class="op_single_selector"]
- [Instellingen voor nalevingsbeleid voor iOS-apparaten](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Instellingen voor nalevingsbeleid voor Windows-apparaten](windows-compliance-policy-settings-in-microsoft-intune.md)
- [Instellingen voor nalevingsbeleid voor Android for Work-apparaten](afw-compliance-policy-settings-in-microsoft-intune.md)

## <a name="system-security-settings"></a>Systeembeveiligingsinstellingen
### <a name="password"></a>Wachtwoord
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

- **Wachtwoorden niet opnieuw gebruiken:** geef het aantal eerder gebruikte wachtwoorden op dat niet opnieuw kan worden gebruikt (als **Wachtwoordgeschiedenis onthouden** is geselecteerd).

- **Wachtwoord vereisen wanneer het apparaat wordt geactiveerd vanuit een niet-actieve status:** gebruik dit samen met de instelling **Minuten inactief voordat wachtwoord is vereist**. Gebruikers wordt gevraagd een wachtwoord op te geven om toegang te krijgen tot een apparaat dat inactief is geweest gedurende de tijd die is opgegeven bij de instelling **Minuten inactief voordat wachtwoord is vereist**.

### <a name="encryption"></a>Versleuteling
- **Versleuteling vereisen op een mobiel apparaat:** stel deze optie in op **Ja** als u wilt dat apparaten moeten worden versleuteld om verbinding te kunnen maken met resources. Apparaten worden versleuteld wanneer u de instelling **Wachtwoord vereisen voor het ontgrendelen van mobiele apparaten** configureert.

## <a name="device-health-and-security-settings"></a>Status en beveiligingsinstellingen van apparaat

- **Apparaat mag niet gekraakt of geroot zijn**: als u deze instelling inschakelt, worden apparaten die zijn gekraakt of geroot als niet-compatibel beschouwd.
- **Vereisen dat de installatie van apps van onbekende bronnen wordt voorkomen (Android 4.0 en hoger)**: als u apparaten wilt blokkeren waarop **Beveiliging >Onbekende bronnen** op het apparaat is ingeschakeld, schakelt u deze instelling in en zet u deze op **Ja**.  

>[!IMPORTANT]
>Sideloading-toepassingen vereisen dat de instelling **Onbekende bronnen** is ingeschakeld. Dwing dit nalevingsbeleid alleen af als u Android-apps niet met behulp van sideloading op apparaten laadt.

- **Vereisen dat de USB-foutopsporing is uitgeschakeld (Android 4.2 of hoger)**: geef op of moet worden gedetecteerd of de USB-foutopsporingsoptie op het apparaat is ingeschakeld.
- **Vereisen dat Apparaat scannen op beveiligingsbedreigingen is ingeschakeld op apparaten (Android 4.2 - 4.4)**: geef op dat de functie **Apps controleren** is ingeschakeld op het apparaat.
- **Minimaal niveau voor de Android-beveiligingspatch (Android 6.0 of hoger)**: geef het minimale Android-patchniveau op.  Apparaten die niet ten minste dit patchniveau hebben, worden als niet-compatibel gezien. De datum moet de volgende notatie hebben: JJJJ-MM-DD.
- **Vereisen dat Device Threat Protection wordt ingeschakeld**: Gebruik deze instelling om de risicobeoordeling uit de Lookout MTP-oplossing als voorwaarde voor naleving te gebruiken. Selecteer het maximaal toegestane bedreigingsniveau. U kunt daarbij kiezen uit:

  - **Geen (beveiligd)**: Dit is het veiligste niveau. Dit betekent dat er op het apparaat geen bedreigingen mogen staan. Als er een bedreiging op het apparaat wordt gedetecteerd, wordt het geëvalueerd als niet-compatibel.
  - **Laag**: het apparaat wordt als compatibel geëvalueerd als er alleen bedreigingen van laag niveau aanwezig zijn. Als er een hoger niveau wordt aangetroffen, krijgt het apparaat de status niet-compatibel.
  - **Gemiddeld**: het apparaat wordt als compatibel geëvalueerd als de bedreigingen op het apparaat van laag of gemiddeld niveau zijn. Als er bedreigingen van hoog niveau worden aangetroffen op het apparaat, wordt het apparaat als niet-compatibel beoordeeld.
  - **Hoog**: Dit is de minst veilige optie. Het komt erop neer dat alle bedreigingsniveaus worden toegestaan. Dit zou eventueel nuttig kunnen zijn als u deze oplossing alleen voor rapportagedoeleinden gebruikt.

  Zie voor meer informatie [Lookout-nalevingsbeleid voor apparaat maken](create-lookout-device-compliance-policy.md).

## <a name="device-property-settings"></a>Instellingen voor apparaateigenschappen

- **Minimale versie van het besturingssysteem die is vereist:** wanneer een apparaat niet voldoet aan de minimumvereisten met betrekking tot de versie van het besturingssysteem, wordt dit apparaat gerapporteerd als niet-compatibel.
  Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. Gebruikers kunnen dan kiezen om een upgrade van hun apparaat uit te voeren, waarna ze toegang tot bedrijfsbronnen krijgen.

- **Maximale versie van het besturingssysteem die is toegestaan:** wanneer een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie die in de regel is opgegeven, wordt de toegang tot bedrijfsbronnen geblokkeerd en wordt de gebruiker gevraagd contact op te nemen met de IT-beheerder. Tot er een wijziging is doorgevoerd in de regel om de versie van het besturingssysteem toe te staan, kan dit apparaat niet worden gebruikt om toegang tot bedrijfsbronnen te krijgen.
