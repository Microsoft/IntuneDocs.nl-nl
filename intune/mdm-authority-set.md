---
title: De instantie voor het beheer van mobiele apparaten instellen
titlesuffix: Azure portal
description: Informatie over het instellen van de instantie voor het beheer van mobiele apparaten in Intune. "
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fc0634f5e5f4648dabaa371c3ab94f070a941057
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
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

1. Kies in de [Azure portal](https://portal.azure.com) **Meer Services** > **Bewaking en beheer** > **Intune**.
2. Selecteer de oranje banner om de instelling **Instantie voor beheer van mobiele apparaten** te openen.
3. Kies onder **Instantie voor beheer van mobiele apparaten** uw MDM-instantie uit de volgende opties:
  - **MDM-instantie voor Intune**
  - **MDM-instantie voor Configuration Manager**
  - **Geen**

  ![Schermafbeelding van het scherm De instantie voor het beheer van mobiele apparaten instellen op Intune](media/set-mdm-auth.png)

  Er verschijnt een bericht met de melding dat u uw MDM-instantie hebt ingesteld op Intune.

## <a name="enable-device-enrollment"></a>Apparaatinschrijving inschakelen

Als Intune als uw MDM-instantie is ingesteld, kunnen gebruikers hun persoonlijke apparaten inschrijven en toegang krijgen tot resources, zoals e-mail, door de bedrijfsportal te installeren (iOS en Android), werkreferenties toe te voegen (Windows) of de bedrijfsportalwebsite te openen (iOS, Android, macOS).

Verschillende platforms hebben de volgende eisen om inschrijving mogelijk te maken of te vereenvoudigen:
- **iOS** - (vereist) [Zorg voor een Apple MDM-pushcertificaat](apple-mdm-push-certificate-get.md) en schakel daarna [inschrijving voor iOS-apparaten van het bedrijf in](ios-enroll.md) (optioneel).
- **Android** - (optioneel) [Schakel Android-werkprofielen in](android-enroll.md)
- **Windows** - (optioneel) Schakel [Automatische inschrijving](windows-enroll.md) of [bulkinschrijving](windows-bulk-enroll.md) in
- **macOS** - Geen vereisten


## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Mobiele apparaten opschonen na de verloopdatum van het MDM-certificaat

Het MDM-certificaat wordt automatisch vernieuwd wanneer mobiele apparaten communiceren met de Intune-service. Als mobiele apparaten worden gewist of een bepaalde tijd niet kunnen communiceren met de Intune-service, wordt het MDM-certificaat niet vernieuwd. Het apparaat wordt 180 dagen nadat het MDM-certificaat is verlopen verwijderd uit de Azure Portal.
