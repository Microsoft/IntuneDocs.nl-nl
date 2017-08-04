---
title: De instantie voor het beheer van mobiele apparaten instellen
titleSuffix: Intune on Azure
description: Informatie over het instellen van de instantie voor het beheer van mobiele apparaten in Intune. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 97dede1ac393a434342f62d1f8488389dcb28d44
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/03/2017
---
# <a name="set-the-mobile-device-management-authority"></a>De instantie voor het beheer van mobiele apparaten instellen

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Met de instantie voor het beheer van mobiele apparaten (MDM) wordt bepaald hoe u uw apparaten beheert. Als IT-beheerder moet u een MDM-instantie instellen voordat gebruikers apparaten voor beheer kunnen inschrijven.

Mogelijke configuraties zijn:

- **Intune Standalone**: cloudbeheer dat u configureert met behulp van de Azure Portal. Bevat de volledige reeks mogelijkheden van Intune. [De MDM-instantie instellen in de Intune-beheerconsole](#set-mdm-authority-to-intune).

- **Intune Hybrid**: integratie van de Intune-cloudoplossing met System Center Configuration Manager. U kunt Intune configureren met behulp van de Configuration Manager-console. [De MDM-instantie instellen in Configuratiebeheer](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).

- **Mobile Device Management voor Office 365**: integratie van Office 365 met de Intune-cloudoplossing. U kunt Intune configureren vanuit het Office 365-beheercentrum. Bevat een subset van de mogelijkheden die beschikbaar zijn met Intune Standalone. Stel de MDM-instantie in Office 365-beheercentrum in.

>[!IMPORTANT]    
In Configuration Manager versie 1610 of hoger en Microsoft Intune versie 1705 kunt u de MDM-instantie wijzigen zonder dat u contact hoeft op te nemen met Microsoft Ondersteuning en zonder dat u de inschrijving van bestaande beheerde apparaten ongedaan hoeft te maken om ze vervolgens opnieuw in te schrijven. Zie [Wat te doen als u de verkeerde instelling kiest voor de MDM-instantie](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting) voor meer informatie.

## <a name="set-mdm-authority-to-intune"></a>MDM-instantie instellen op Intune

1. Kies in Azure Portal **Meer services** > **Bewaking en beheer** > **Intune**.
  ![Schermafbeelding van de werkbelasting Problemen oplossen van Intune, met de koppeling Gebruiker selecteren](media/set-mdm-auth.png)
2. Kies **Apparaten inschrijven** op de blade Intune en kies vervolgens **Overzicht**.

3. Kies op de blade **Het beheer van apparaten starten** **MDM-instantie instellen op Intune**. Er verschijnt een bericht met de melding dat u uw MDM-instantie hebt ingesteld op Intune.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Mobiele apparaten opschonen na de verloopdatum van het MDM-certificaat

Het MDM-certificaat wordt automatisch vernieuwd wanneer mobiele apparaten communiceren met de Intune-service. Als mobiele apparaten worden gewist of een bepaalde tijd niet kunnen communiceren met de Intune-service, wordt het MDM-certificaat niet vernieuwd. Het apparaat wordt 180 dagen nadat het MDM-certificaat is verlopen verwijderd uit de Azure Portal.
