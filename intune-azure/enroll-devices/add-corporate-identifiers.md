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
translationtype: Human Translation
ms.sourcegitcommit: 4ebd74c77145464574a1fed878ec4dbc2eb3c271
ms.openlocfilehash: 7bb8168c442a3340e8c185f1908acd9be15cab05
ms.lasthandoff: 04/05/2017

---

# <a name="add-corporate-identifiers"></a>Zakelijke id's toevoegen

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Als IT-beheerder kunt u een bestand met door komma's gescheiden waarden (CSV) maken en importeren, waarin de IMEI-nummers (International Mobile Equipment Identity) worden vermeld waarmee apparaten in bedrijfseigendom worden geïdentificeerd. Voor elk IMEI-nummer kunnen gegevens zijn opgegeven in de lijst voor beheerdoeleinden.

Wanneer u serienummers uploadt voor iOS-apparaten in bedrijfseigendom, moeten die worden gekoppeld aan een inschrijvingsprofiel voor bedrijven. Vervolgens moeten de apparaten worden ingeschreven met het Apple Device Enrollment Program (DEP) of de Apple Configurator voordat ze als bedrijfseigendom worden weergegeven. 

## <a name="create-a-csv-file"></a>Een CSV-bestand maken
Maak een lijst met twee kolommen met door komma's gescheiden waarden (.csv) zonder koptekst. Voeg de IMEI-id in de linkerkolom toe en de details in de rechterkolom. De details mogen maximaal 128 tekens lang zijn. De huidige limiet is 500 rijen per CSV-bestand.

**Een CSV-bestand met serienummers uploaden**: maak een lijst in twee kolommen met door komma's gescheiden waarden (CSV) zonder koptekst. Zorg ervoor dat het CSV-bestand niet meer dan 5000 apparaten bevat en niet groter is dan 5 MB.

|||
|-|-|
|&lt;IMEI 1&gt;|&lt;Details apparaat 1&gt;|
|&lt;IMEI 2&gt;|&lt;Details apparaat 2&gt;|

    This .csv file when viewed in a text editor appears as:

    ```
    01 234567 890123,device details
    02 234567 890123,device details
    ```

**Een .csv-lijst van zakelijke id's toevoegen**

1. Kies in Azure Portal **Meer services** > **Bewaking en beheer** > **Intune**.

2. Kies **Apparaten inschrijven** op de blade Intune en kies vervolgens **Zakelijke apparaat-id's**.

3. Als u een bestand met nieuwe details importeert die de bestaande details overschrijven, selecteert u **Details voor bestaande id's overschrijven** zodat de nieuwe details de bestaande vervangen.

4. Navigeer naar het IMEI .csv-bestand en selecteer **Toevoegen**.

> [!IMPORTANT]
> Sommige Android-apparaten hebben meerdere IMEI-nummers. Intune inventariseert één IMEI-nummer per apparaat. Als u een IMEI-nummer importeert dat niet het IMEI-nummer is dat door Intune is geïnventariseerd, wordt het apparaat geclassificeerd als een persoonlijk apparaat in plaats van een apparaat in bedrijfseigendom. Als u meerdere IMEI-nummers voor een apparaat importeert, krijgen niet-geïnventariseerde nummers de inschrijvingsstatus **Onbekend**.

Wanneer de nummers zijn geïmporteerd, kunnen de apparaten wel of niet zijn ingeschreven en kunnen ze de status **Ingeschreven** of **Geen contact gemaakt** hebben. **Geen contact gemaakt** betekent dat het apparaat nooit gecommuniceerd heeft met de Intune-service.

## <a name="delete-a-csv-list"></a>Een CSV-lijst verwijderen

1. Kies in Azure Portal **Meer services** > **Bewaking en beheer** > **Intune**.

2. Kies **Apparaten inschrijven** op de blade Intune en kies vervolgens **Zakelijke apparaat-id's**.

3. Kies **Verwijderen**.

Zie [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729) voor gedetailleerde specificaties over International Mobile Equipment Identifiers.

