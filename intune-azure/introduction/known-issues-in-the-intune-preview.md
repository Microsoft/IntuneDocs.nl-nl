---
title: Bekende problemen in Microsoft Intune Preview
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: in dit onderwerp leest u meer over bekende problemen in de preview-versie'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/06/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: b6c245d60c661c04b4c4d29c9bdcdd752254d978
ms.openlocfilehash: ec3f87994b19591bda4ec201eac3c839798d634c
ms.lasthandoff: 03/15/2017


---

# <a name="known-issues-in-the-microsoft-intune-preview"></a>Bekende problemen in Microsoft Intune Preview


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Gebruik dit onderwerp als u meer informatie wilt over bekende problemen in de preview-versie van Intune.

Als u een fout wilt melden die bug hier niet wordt weergegeven, kunt u een [ondersteuningsaanvraag openen](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

Als u een suggestie wilt doen voor een nieuwe functie in Intune, kunt u een rapport op de site [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console) indienen.

## <a name="administration-and-accounts"></a>Beheer en accounts

- Globale beheerders (ook wel tenantbeheerders genoemd) kunnen de reguliere beheertaken voortzetten zonder afzonderlijke Intune- of Enterprise Mobility Suite-licentie (ESM). Als hoofdbeheerders echter de service willen gebruiken, bijvoorbeeld om hun eigen apparaat of een bedrijfsapparaat in te schrijven of om de Intune-bedrijfsportal te gebruiken, moeten ze net als anderen beschikken over een Intune- of EMS-licentie.

## <a name="apple-enrollment-profile-migration"></a>Profielmigratie van Apple-inschrijving
- In de komende maanden wordt het beheren van Apple Device Enrollment Program- en de Apple Configurator-inschrijvingen via Intune mogelijk via de nieuwe Azure Portal. Als u het Apple Device Enrollment Program-token verwijdert en geen bijgewerkt token uploadt, wordt het oorspronkelijke token hersteld in de nieuwe Azure Portal als onderdeel van de migratie van uw Intune-account. Als u dit token wilt verwijderen en DEP-inschrijving wilt voorkomen, hoeft u alleen het token te verwijderen uit Azure Portal. 

