---
title: "IMEI-id’s toevoegen aan Intune"
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: informatie over het toevoegen van zakelijke id&quot;s (IMEI-nummers) aan Microsoft Intune. '
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 0d7c8eedbdad917a43d43d2e79ead5663e8e2871
ms.lasthandoff: 02/18/2017

---

# <a name="add-corporate-identifiers"></a>Zakelijke id's toevoegen

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

U kunt een lijst met IMEI-nummers (International Mobile Equipment Identity) maken voor de identificatie van uw zakelijke apparaten. Deze apparaten kunnen wel of niet worden geregistreerd en ze hebben de status Geregistreerd of Geen contact gemaakt. Geen contact gemaakt betekent dat het apparaat nooit ingecheckt wordt bij de Intune-service.

Maak een lijst met twee kolommen met door komma's gescheiden waarden (.csv) zonder koptekst. Voeg de IMEI-id in de linkerkolom toe en de details in de rechterkolom. Een lijst kan momenteel maximaal 500 rijen bevatten.

In een teksteditor ziet de .csv-lijst er ongeveer zo uit:

01 234567 890123, apparaatdetails</br>
02 234567 890123, apparaatdetails

**Een .csv-lijst van zakelijke id's toevoegen**

1. Kies in Azure Portal **Meer services** > **Bewaking en beheer** > **Intune**.

2. Kies **Apparaten inschrijven** op de blade Intune en kies vervolgens **Zakelijke apparaat-id's**.

3. Als u een bestand met nieuwe details importeert die de bestaande details overschrijven, selecteert u **Details voor bestaande id's overschrijven** zodat de nieuwe details de bestaande vervangen.

4. Navigeer naar het IMEI .csv-bestand en selecteer **Toevoegen**.

**Een .csv-lijst van zakelijke id's verwijderen**

1. Kies in Azure Portal **Meer services** > **Bewaking en beheer** > **Intune**.

2. Kies **Apparaten inschrijven** op de blade Intune en kies vervolgens **Zakelijke apparaat-id's**.

3. Kies **Verwijderen**.

