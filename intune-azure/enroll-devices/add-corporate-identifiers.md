---
title: IMEI-id&quot;s toevoegen aan Intune | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: informatie over het toevoegen van zakelijke id&quot;s (IMEI-nummers) aan Microsoft Intune. '
keywords: 
author: staciebarker
ms.author: stabark
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: e134a6e3ff143dacce1d70ef0ab44ade0722ed57

---

# <a name="add-corporate-identifiers"></a>Zakelijke id's toevoegen

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

U kunt een lijst met IMEI-nummers (International Mobile Equipment Identity) maken voor de identificatie van uw zakelijke apparaten. Deze apparaten kunnen wel of niet worden geregistreerd en ze hebben de status Geregistreerd of Geen contact gemaakt. Geen contact gemaakt betekent dat het apparaat nooit ingecheckt wordt bij de Intune-service.

Maak een lijst met twee kolommen met door komma's gescheiden waarden (.csv) zonder koptekst. Voeg de IMEI-id in de linkerkolom toe en de details in de rechterkolom. Een lijst kan momenteel maximaal 500 rijen bevatten.

In een teksteditor ziet de .csv-lijst er ongeveer zo uit:

01 234567 890123, apparaatdetails</br>
02 234567 890123, apparaatdetails

**Een .csv-lijst van zakelijke id's toevoegen**

1. Kies in Azure Portal **Meer services**, voer **Intune** in het tekstvak in en kies **Overige** > **Intune**.

2. Kies **Apparaten inschrijven** op de blade Intune en kies vervolgens **Zakelijke apparaat-id's**.

3. Als u een bestand met nieuwe details importeert die de bestaande details overschrijven, selecteert u **Details voor bestaande id's overschrijven** zodat de nieuwe details de bestaande vervangen.

4. Navigeer naar het IMEI .csv-bestand en selecteer **Toevoegen**.

**Een .csv-lijst van zakelijke id's verwijderen**

1. Kies **Apparaten inschrijven** op de blade Intune en kies vervolgens **Zakelijke apparaat-id's**.

2. Kies **Verwijderen**.



<!--HONumber=Feb17_HO1-->


