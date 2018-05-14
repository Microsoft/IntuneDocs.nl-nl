---
title: De instantie voor het beheer van mobiele apparaten instellen
titlesuffix: Microsoft Intune
description: Stel de instantie in voor het beheer van mobiele apparaten in Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f903e9dfe5fb30f45806aac5694171814492f2e
ms.sourcegitcommit: 0f1a5d6e577915d2d748d681840ca04a0a2604dd
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2018
---
# <a name="set-the-mobile-device-management-authority"></a>De instantie voor het beheer van mobiele apparaten instellen

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Met de instantie voor het beheer van mobiele apparaten (MDM) wordt bepaald hoe u uw apparaten beheert. Als IT-beheerder moet u een MDM-instantie instellen voordat gebruikers apparaten voor beheer kunnen inschrijven.

Mogelijke configuraties zijn:

- **Intune Standalone**: cloudbeheer dat u configureert met behulp van de Azure Portal. Bevat de volledige reeks mogelijkheden van Intune. [De MDM-instantie instellen in de Intune-beheerconsole](#set-mdm-authority-to-intune).

- **Intune Hybrid**: integratie van de Intune-cloudoplossing met System Center Configuration Manager. U kunt Intune configureren met behulp van de Configuration Manager-console. [De MDM-instantie instellen in Configuratiebeheer](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).

- **Mobile Device Management voor Office 365**: integratie van Office 365 met de Intune-cloudoplossing. U kunt Intune configureren vanuit het Office 365-beheercentrum. Bevat een subset van de mogelijkheden die beschikbaar zijn met Intune Standalone. Stel de MDM-instantie in Office 365-beheercentrum in.

> [!IMPORTANT]
> In Configuration Manager versie 1610 of hoger en Microsoft Intune versie 1705 kunt u de MDM-instantie wijzigen zonder dat u contact hoeft op te nemen met Microsoft Ondersteuning en zonder dat u de inschrijving van bestaande beheerde apparaten ongedaan hoeft te maken om ze vervolgens opnieuw in te schrijven. Zie [Wat te doen als u de verkeerde instelling kiest voor de MDM-instantie](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting) voor meer informatie.

## <a name="set-mdm-authority-to-intune"></a>MDM-instantie instellen op Intune

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Selecteer de oranje banner om de instelling **Instantie voor beheer van mobiele apparaten** te openen.
4. Kies onder **Instantie voor beheer van mobiele apparaten** uw MDM-instantie uit de volgende opties:
   - **MDM-instantie voor Intune**
   - **MDM-instantie voor Configuration Manager**
   - **Geen**

   ![Schermafbeelding van het scherm De instantie voor het beheer van mobiele apparaten instellen op Intune](media/set-mdm-auth.png)

   Er verschijnt een bericht met de melding dat u uw MDM-instantie hebt ingesteld op Intune.

## <a name="enable-device-enrollment"></a>Apparaatinschrijving inschakelen

Als Intune als uw MDM-instantie is ingesteld, kunnen gebruikers hun persoonlijke apparaten inschrijven en toegang krijgen tot resources, zoals e-mail, door de bedrijfsportal te installeren (iOS, macOS en Android), werkreferenties toe te voegen (Windows) of de bedrijfsportalwebsite te openen (iOS, Android, macOS).

Verschillende platforms hebben de volgende eisen om inschrijving mogelijk te maken of te vereenvoudigen:
- **iOS** - (vereist) [Zorg voor een Apple MDM-pushcertificaat](apple-mdm-push-certificate-get.md) en schakel daarna [inschrijving voor iOS-apparaten van het bedrijf in](ios-enroll.md) (optioneel).
- **Android** - (optioneel) [Schakel Android-werkprofielen in](android-enroll.md)
- **Windows** - (optioneel) Schakel [Automatische inschrijving](windows-enroll.md) of [bulkinschrijving](windows-bulk-enroll.md) in
- **macOS** - (vereist) [Haal een Apple MDM-pushcertificaat op](apple-mdm-push-certificate-get.md).

### <a name="workflow-of-intune-administration-ui"></a>Werkstroom van de Intune-beheergebruikersinterface
Als Android- of Apple-apparaatbeheer is ingeschakeld, verstuurt Intune apparaat- en gebruikersgegevens, zodat deze kunnen worden geïntegreerd in de externe services voor het beheren van apparaten.

Scenario's waarin toestemming moet worden gegeven om gegevens te delen, zijn:
- Wanneer u Android for Work inschakelt,
- Wanneer u Apple MDM-pushcertificaten inschakelt en uploadt,
- Wanneer u een van de Apple-services zoals Device Enrollment Program, School Manager of Volume Purchasing Program inschakelt.

In elk geval wordt de toestemming beperkt tot het uitvoeren van een MDM-service, bijvoorbeeld om te bevestigen dat een IT-beheerder heeft goedgekeurd dat Google- of Apple-apparaten worden ingeschreven. Documentatie over welke informatie wordt gedeeld wanneer de nieuwe werkstromen live gaan, is beschikbaar op de volgende locaties:
- [Gegevens die Intune naar Google verzendt](https://aka.ms/Data-intune-sends-to-google)
- [Gegevens die Intune naar Apple verzendt](https://aka.ms/data-intune-sends-to-apple)

Zie [Trust Center: uw AVG-naleving beoordelen](https://aka.ms/trust_center_info) voor meer informatie over de AVG-naleving van Microsoft.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Mobiele apparaten opschonen na de verloopdatum van het MDM-certificaat

Het MDM-certificaat wordt automatisch vernieuwd wanneer mobiele apparaten communiceren met de Intune-service. Als mobiele apparaten worden gewist of een bepaalde tijd niet kunnen communiceren met de Intune-service, wordt het MDM-certificaat niet vernieuwd. Het apparaat wordt 180 dagen nadat het MDM-certificaat is verlopen verwijderd uit de Azure Portal.
