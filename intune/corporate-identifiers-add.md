---
title: IMEI-id's toevoegen aan Intune
titleSuffix: Intune on Azure
description: Meer informatie over het toevoegen van zakelijke id's (IMEI-nummers) aan Microsoft Intune. "
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 57ab3b79ad53a4b195fac426d211a114f054602f
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="add-corporate-identifiers"></a>Zakelijke id's toevoegen

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Als IT-beheerder kunt u een bestand met door komma's gescheiden waarden (CSV) maken en importeren, waarin de IMEI-nummers (International Mobile Equipment Identifier) of serienummers worden vermeld waarmee apparaten in bedrijfseigendom worden geïdentificeerd. U kunt alleen serienummers declareren voor iOS- en Android-apparaten. Voor elk IMEI-nummer of serienummer kunnen gegevens zijn opgegeven in de lijst voor beheerdoeleinden.

<!-- When you upload serial numbers for company-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as company-owned. -->

[Lees hier meer informatie over het vinden van het serienummer van een Apple-apparaat](https://support.apple.com/HT204308).
[Lees hier meer informatie over het vinden van het serienummer van een Android-apparaat](https://support.google.com/store/answer/3333000).

## <a name="add-corporate-identifiers"></a>Zakelijke id's toevoegen
Maak een lijst met twee kolommen met door komma's gescheiden waarden (.csv) zonder koptekst. Plaats de IMEI- of serienummers in de linkerkolom en de details in de rechterkolom. U kunt in één CSV-bestand maar één type id, IMEI-nummer of serienummer importeren. De details zijn beperkt tot 128 tekens en zijn alleen bedoeld voor beheerders. De details worden niet op het apparaat weergegeven. De huidige limiet is 500 rijen per CSV-bestand.

**Een CSV-bestand met serienummers uploaden**: maak een lijst in twee kolommen met door komma's gescheiden waarden (CSV) zonder koptekst. Zorg ervoor dat het CSV-bestand niet meer dan 5000 apparaten bevat en niet groter is dan 5 MB.

|||
|-|-|
|&lt;Id 1&gt;|&lt;Details apparaat 1&gt;|
|&lt;Id 2&gt;|&lt;Details apparaat 2&gt;|

Dit CSV-bestand ziet er in een teksteditor als volgt uit:

```
01234567890123,device details
02234567890123,device details
```

> [!IMPORTANT]
> Sommige Android-apparaten hebben meerdere IMEI-nummers. Intune leest maar één IMEI-nummer per ingeschreven apparaat. Als u een IMEI-nummer importeert dat niet het IMEI-nummer is dat door Intune is geïnventariseerd, wordt het apparaat geclassificeerd als een persoonlijk apparaat in plaats van een apparaat in bedrijfseigendom. Als u meerdere IMEI-nummers voor een apparaat importeert, krijgen niet-geïnventariseerde nummers de inschrijvingsstatus **Onbekend**.

**Een .csv-lijst van zakelijke id's toevoegen**

1. Kies in de Intune-portal achtereenvolgens **Apparaatinschrijving** > **Inschrijvingsbeperkingen** en **Zakelijke apparaat-id's** en klik op **Toevoegen**.

 ![Schermopname van de werkruimte Zakelijke apparaat-id's met de knop Toevoegen gemarkeerd.](./media/add-corp-id.png)

2. Geef op de blade **Id's toevoegen** het type id op: **IMEI** of **Serienummer**. U kunt opgeven of eerder geïmporteerde nummers **details voor bestaande id's moeten overschrijven**.

3. Klik op het mappictogram en geef het pad op naar de lijst die u wilt importeren. Navigeer naar het CSV-bestand en selecteer **Toevoegen**. Klik op **Vernieuwen** voor een overzicht van nieuwe apparaat-id's.

Wanneer de nummers zijn geïmporteerd, kunnen de apparaten wel of niet zijn ingeschreven en kunnen ze de status **Ingeschreven** of **Geen contact gemaakt** hebben. **Geen contact gemaakt** betekent dat het apparaat nooit gecommuniceerd heeft met de Intune-service.

## <a name="delete--corporate-identifiers"></a>Zakelijke id's verwijderen

1. Kies in de Intune-portal achtereenvolgens **Apparaatinschrijving** > **Inschrijvingsbeperkingen** en **Zakelijke apparaat-id's** en **Verwijderen**.

3. Op de blade **Id's verwijderen** bladert u naar het .csv-bestand met te verwijderen apparaat-id's en klikt u op **Verwijderen**.

## <a name="imei-specifications"></a>IMEI-specificaties
Zie [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729) voor gedetailleerde specificaties over International Mobile Equipment Identifiers.
