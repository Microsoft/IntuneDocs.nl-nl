---
title: Bewerkingen voor uw Azure Rights Management-tenantsleutel | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 1284d0ee-0a72-45ba-a64c-3dcb25846c3d
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0f355da35dff62ecee111737eb1793ae286dc93e
ms.openlocfilehash: 44408fd8f9da73d8050e0938aa1cc9bc76688bed


---

# Bewerkingen voor uw Azure Rights Management-tenantsleutel

*Van toepassing op: Azure Rights Management, Office 365*

Afhankelijk van uw tenantsleuteltopologie (door Microsoft of de klant beheerd) beschikt u over verschillende niveaus van controle en verantwoordelijkheid voor uw Microsoft Azure Rights Management-tenantsleutel (Azure RMS) nadat deze is geïmplementeerd.

Als u uw eigen tenantsleutel beheert, wordt hier vaak naar verwezen als Bring Your Own Key (BYOK). Zie [Uw Azure Rights Management-tenantsleutel plannen en implementeren](../plan-design/plan-implement-tenant-key.md) voor meer informatie over dit scenario en over hoe u kiest tussen de twee tenantsleuteltopologieën.

In de volgende tabel staat welke bewerkingen u kunt uitvoeren, afhankelijk van de topologie die u voor uw Azure RMS-tenantsleutel hebt gekozen.

|Levenscyclusbewerking|Door Microsoft beheerd (standaard)|Door de klant beheerd (BYOK)|
|-----------------------|-------------------------------|---------------------------|
|Uw tenantsleutel intrekken|Nee (automatisch)|Nee (automatisch)|
|Uw tenantsleutel opnieuw instellen|Ja|Ja|
|Een back-up van uw tenantsleutel maken en deze herstellen|Nee|Ja|
|Uw tenantsleutel exporteren|Ja|Nee|
|Reageren op een schending|Ja|Ja|

Wanneer u hebt vastgesteld welke topologie u hebt geïmplementeerd, kiest u een van de volgende opties voor meer informatie over de bewerkingen voor uw Azure RMS-tenantsleutel:


- [Door Microsoft beheerde tenantsleutel](operations-microsoft-managed-tenant-key.md)
- [Door de klant beheerde tenantsleutel](operations-customer-managed-tenant-key.md)







<!--HONumber=Jun16_HO4-->


