---
title: "IMEI-id’s toevoegen aan Intune"
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: informatie over het toevoegen van zakelijke id&quot;s (IMEI-nummers) aan Microsoft Intune. '
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: d8cb15d1b8c1c100f15084e43d2c3c4633fd64b5
ms.openlocfilehash: f12d538b1f4cd327b893d234f2b558185cdd9d85
ms.lasthandoff: 03/09/2017

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

> [!IMPORTANT]
> Sommige Android-apparaten hebben meerdere IMEI-nummers. Intune inventariseert één IMEI-nummer per apparaat. Als u een IMEI-nummer importeert dat niet het IMEI-nummer is dat door Intune is geïnventariseerd, wordt het apparaat geclassificeerd als een persoonlijk apparaat in plaats van een apparaat in bedrijfseigendom. Als u meerdere IMEI-nummers voor een apparaat importeert, krijgen niet-geïnventariseerde nummers de inschrijvingsstatus **Onbekend**.

**Een .csv-lijst van zakelijke id's verwijderen**

1. Kies in Azure Portal **Meer services** > **Bewaking en beheer** > **Intune**.

2. Kies **Apparaten inschrijven** op de blade Intune en kies vervolgens **Zakelijke apparaat-id's**.

3. Kies **Verwijderen**.

