---
title: De instantie voor het beheer van mobiele apparaten instellen
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: informatie over het instellen van de instantie voor het beheer van mobiele apparaten in Intune. '
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 04/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: dc08ba96eeea0ce2aad78e4d6ca0d94e709d885d
ms.openlocfilehash: 6cf7c56924091713f55fe8824fb11e522825b98f
ms.lasthandoff: 04/21/2017

---

# <a name="set-the-mobile-device-management-authority"></a>De instantie voor het beheer van mobiele apparaten instellen

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Met de instantie voor het beheer van mobiele apparaten (MDM) wordt bepaald hoe u uw apparaten beheert. Als IT-beheerder moet u een MDM-instantie instellen voordat gebruikers apparaten voor beheer kunnen inschrijven.

Mogelijke configuraties zijn:

- **Intune Standalone**: cloudbeheer dat u configureert met behulp van de Azure Portal. Bevat de volledige reeks mogelijkheden van Intune. [De MDM-instantie instellen in de Intune-beheerconsole](#set-mdm-authority-to-Intune).

- **Intune Hybrid**: integratie van de Intune-cloudoplossing met System Center Configuration Manager. U kunt Intune configureren met behulp van de Configuration Manager-console. [De MDM-instantie instellen in Configuratiebeheer](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).

- **Mobile Device Management voor Office 365**: integratie van Office 365 met de Intune-cloudoplossing. U kunt Intune configureren vanuit het Office 365-beheercentrum. Bevat een subset van de mogelijkheden die beschikbaar zijn met Intune Standalone. Stel de MDM-instantie in Office 365-beheercentrum in.

>[!IMPORTANT]
>Nadat u de instantie voor beheer van mobiele apparaten hebt ingesteld, moet u contact opnemen met [Microsoft Ondersteuning](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune) om de instantie te wijzigen. Controleer daarom uw keuze zorgvuldig.

## <a name="set-mdm-authority-to-intune"></a>MDM-instantie instellen op Intune

1. Kies in Azure Portal **Meer services** > **Bewaking en beheer** > **Intune**.
  ![Schermafbeelding van de werkbelasting Problemen oplossen van Intune, met de koppeling Gebruiker selecteren](media/set-mdm-auth.png)
2. Kies **Apparaten inschrijven** op de blade Intune en kies vervolgens **Overzicht**.

3. Kies op de blade **Het beheer van apparaten starten** **MDM-instantie instellen op Intune**. Er verschijnt een bericht met de melding dat u uw MDM-instantie hebt ingesteld op Intune.

