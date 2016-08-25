---
title: Bewerkingen voor uw Azure Rights Management-tenantsleutel | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 08/17/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 1284d0ee-0a72-45ba-a64c-3dcb25846c3d
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 437afd88efebd9719a3db98f8ab0ae07403053f7
ms.openlocfilehash: 19cae6be4de2eec65414596976062736af4b63b2


---

# Bewerkingen voor uw Azure Rights Management-tenantsleutel

*Van toepassing op: Azure Rights Management, Office 365*

Afhankelijk van uw tenantsleuteltopologie (door Microsoft of de klant beheerd) beschikt u over verschillende niveaus van controle en verantwoordelijkheid voor uw Microsoft Azure Rights Management-tenantsleutel (Azure RMS) nadat deze is geïmplementeerd.

Als u uw eigen tenantsleutel beheert in Azure Key Vault, wordt hier vaak naar verwezen als Bring Your Own Key (BYOK). Zie [Uw Azure Rights Management-tenantsleutel plannen en implementeren](../plan-design/plan-implement-tenant-key.md) voor meer informatie over dit scenario en over hoe u kiest tussen de twee tenantsleuteltopologieën.

In de volgende tabel staat welke bewerkingen u kunt uitvoeren, afhankelijk van de topologie die u voor uw Azure RMS-tenantsleutel hebt gekozen.

|Levenscyclusbewerking|Door Microsoft beheerd (standaard)|Door de klant beheerd (BYOK)|
|-----------------------|-------------------------------|---------------------------|
|Uw tenantsleutel intrekken|Nee (automatisch)|Ja|
|Uw tenantsleutel opnieuw instellen|Yes|Yes|
|Een back-up van uw tenantsleutel maken en deze herstellen|Nee|Yes|
|Uw tenantsleutel exporteren|Yes|Nee|
|Reageren op een schending|Yes|Yes|

Wanneer u hebt vastgesteld welke topologie u hebt geïmplementeerd, kiest u een van de volgende opties voor meer informatie over de bewerkingen voor uw Azure RMS-tenantsleutel:


- [Door Microsoft beheerde tenantsleutel](operations-microsoft-managed-tenant-key.md)
- [Door de klant beheerde tenantsleutel](operations-customer-managed-tenant-key.md)







<!--HONumber=Aug16_HO3-->


