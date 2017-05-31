---
title: "IMEI-id’s toevoegen aan Intune"
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: informatie over het toevoegen van zakelijke id&quot;s (IMEI-nummers) aan Microsoft Intune. '
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 25414cd42159d1c3e09b80d236ccb12f0df5662a
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017

---

# <a name="add-corporate-identifiers"></a>Zakelijke id's toevoegen

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Als IT-beheerder kunt u een bestand met door komma's gescheiden waarden (CSV) maken en importeren, waarin de IMEI-nummers (International Mobile Equipment Identity) worden vermeld waarmee apparaten in bedrijfseigendom worden geïdentificeerd. Voor elk IMEI-nummer kunnen gegevens zijn opgegeven in de lijst voor beheerdoeleinden.

<!-- When you upload serial numbers for company-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as company-owned. -->

## <a name="add-corporate-identifiers"></a>Zakelijke id's toevoegen
Maak een lijst met twee kolommen met door komma's gescheiden waarden (.csv) zonder koptekst. Voeg de IMEI-id in de linkerkolom toe en de details in de rechterkolom. De details zijn beperkt tot 128 tekens en zijn alleen bedoeld voor beheerders. De details worden niet op het apparaat weergegeven. De huidige limiet is 500 rijen per CSV-bestand.

**Een CSV-bestand met serienummers uploaden**: maak een lijst in twee kolommen met door komma's gescheiden waarden (CSV) zonder koptekst. Zorg ervoor dat het CSV-bestand niet meer dan 5000 apparaten bevat en niet groter is dan 5 MB. 

|||
|-|-|
|&lt;IMEI 1&gt;|&lt;Details apparaat 1&gt;|
|&lt;IMEI 2&gt;|&lt;Details apparaat 2&gt;|

Dit CSV-bestand ziet er in een teksteditor als volgt uit:

```
01234567890123,device details
02234567890123,device details
```


> [!IMPORTANT]
> Sommige Android-apparaten hebben meerdere IMEI-nummers. Intune inventariseert één IMEI-nummer per apparaat. Als u een IMEI-nummer importeert dat niet het IMEI-nummer is dat door Intune is geïnventariseerd, wordt het apparaat geclassificeerd als een persoonlijk apparaat in plaats van een apparaat in bedrijfseigendom. Als u meerdere IMEI-nummers voor een apparaat importeert, krijgen niet-geïnventariseerde nummers de inschrijvingsstatus **Onbekend**.

**Een .csv-lijst van zakelijke id's toevoegen**

1. Kies in Azure Portal **Meer services** > **Bewaking en beheer** > **Intune**.

2. Op de blade Intune kiest u **Apparaatinschrijving** > **Inschrijvingsbeperkingen**, waarna u **Zakelijke apparaat-id’s** kiest en op **Toevoegen** klikt.

3. Op de blade **Id’s toevoegen** geeft u het id-type **IMEI** op. U kunt opgeven of eerder geïmporteerde nummers **details voor bestaande id's moeten overschrijven**.  

4. Klik op het mappictogram en geef het pad op naar de lijst die u wilt importeren. Navigeer naar het IMEI .csv-bestand en selecteer **Toevoegen**.

Wanneer de nummers zijn geïmporteerd, kunnen de apparaten wel of niet zijn ingeschreven en kunnen ze de status **Ingeschreven** of **Geen contact gemaakt** hebben. **Geen contact gemaakt** betekent dat het apparaat nooit gecommuniceerd heeft met de Intune-service.

## <a name="delete--corporate-identifiers"></a>Zakelijke id's verwijderen

1. Kies in Azure Portal **Meer services** > **Bewaking en beheer** > **Intune**.

2. Op de blade Intune kiest u **Apparaatinschrijving** > **Inschrijvingsbeperkingen**, waarna u **Zakelijke apparaat-id’s** kiest en op **Verwijderen** klikt.

3. Op de blade **Id’s verwijderen** bladert u naar het .csv-bestand met te verwijderen apparaat-id’s en klikt u op **Verwijderen**.

## <a name="imei-specifications"></a>IMEI-specificaties
Zie [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729) voor gedetailleerde specificaties over International Mobile Equipment Identifiers.

