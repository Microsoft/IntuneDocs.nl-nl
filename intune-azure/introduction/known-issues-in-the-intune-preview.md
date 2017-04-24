---
title: Bekende problemen in Microsoft Intune Preview
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: in dit onderwerp leest u meer over bekende problemen in de preview-versie'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/13/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 24498abc504f05bd22dc7309bc22948292f9b1e6
ms.openlocfilehash: 4c81c17ba1419f0b5bdc4910be7d26a5893b32e0
ms.lasthandoff: 04/13/2017


---

# <a name="known-issues-in-the-microsoft-intune-preview"></a>Bekende problemen in Microsoft Intune Preview


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Gebruik dit onderwerp als u meer informatie wilt over bekende problemen in de preview-versie van Intune.

Als u een fout wilt melden die bug hier niet wordt weergegeven, kunt u een [ondersteuningsaanvraag openen](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

Als u een suggestie wilt doen voor een nieuwe functie in Intune, kunt u een rapport op de site [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console) indienen.

## <a name="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products"></a>Groepen die tijdens de migratie door Intune zijn gemaakt, hebben mogelijk invloed op de functionaliteit van andere Microsoft-producten

Wanneer u van de klassieke Intune-portal naar Azure Portal migreert, ziet u mogelijk een nieuwe groep met de naam **Alle gebruikers - b0b08746-4dbe-4a37-9adf-9e7652c0b421**. Houd er rekening mee dat deze groep alle gebruikers in uw Azure Active Directory bevat, niet alleen gebruikers met een Intune-licentie. Dit kan problemen veroorzaken met andere Microsoft-producten, als u verwacht dat sommige bestaande of nieuwe gebruikers van geen enkele groep lid zijn.

## <a name="altering-groups-created-by-intune-during-migration-will-delay-migration"></a>Het wijzigen van groepen die tijdens de migratie zijn gemaakt door Intune, vertraagt de migratie

Uw groepen worden ter voorbereiding op de migratie vanuit Intune naar Azure AD gekopieerd. Alle verdere wijzigingen die u in de klassieke Intune-portal aanbrengt, worden bijgewerkt in de Azure AD-groep. De wijzigingen die u in Azure AD aanbrengt, worden echter niet terug gesynchroniseerd naar de klassieke Intune-console. Dit kan ertoe leiden dat de migratie naar Azure Portal mislukt en dat de migratie wordt vertraagd.

## <a name="compliance-policies-from-intune-will-not-show-up-in-new-console"></a>Nalevingsbeleid uit Intune wordt niet weergegeven in de nieuwe console. 

Alle nalevingsbeleidsregels die u hebt gemaakt in de klassieke Intune-portal, worden wel gemigreerd maar worden niet weergegeven in Azure Portal. Dit probleem wordt veroorzaakt door een ontwerpwijziging in Azure Portal. Nalevingsbeleid dat u in de klassieke Intune-portal hebt gemaakt, wordt nog steeds afgedwongen, maar u moet dit beleid in de klassieke portal weergeven en bewerken.
Bovendien is nieuw nalevingsbeleid dat u in Azure Portal maakt, niet zichtbaar in de klassieke portal.
Zie [Wat is apparaatcompatibiliteit](https://docs.microsoft.com/intune-azure/set-device-compliance/what-is-device-compliance) voor meer informatie.




## <a name="administration-and-accounts"></a>Beheer en accounts

Globale beheerders (ook wel tenantbeheerders genoemd) kunnen de reguliere beheertaken voortzetten zonder afzonderlijke Intune- of Enterprise Mobility Suite-licentie (ESM). Als hoofdbeheerders echter de service willen gebruiken, bijvoorbeeld om hun eigen apparaat of een bedrijfsapparaat in te schrijven of om de Intune-bedrijfsportal te gebruiken, moeten ze net als anderen beschikken over een Intune- of EMS-licentie.

## <a name="apple-enrollment-profile-migration"></a>Profielmigratie van Apple-inschrijving
In de komende maanden wordt het beheren van Apple Device Enrollment Program- en de Apple Configurator-inschrijvingen via Intune mogelijk via de nieuwe Azure Portal. Als u het Apple Device Enrollment Program-token verwijdert en geen bijgewerkt token uploadt, wordt het oorspronkelijke token hersteld in de nieuwe Azure Portal als onderdeel van de migratie van uw Intune-account. Als u dit token wilt verwijderen en DEP-inschrijving wilt voorkomen, hoeft u alleen het token te verwijderen uit Azure Portal. 

