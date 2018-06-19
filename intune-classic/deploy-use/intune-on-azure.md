---
title: Overwegingen bij het beheren van Windows-apparaten met Intune in Azure
description: Overwegingen bij het gebruik van Intune in Azure voor het beheren van Windows-apparaten van uw organisatie.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/14/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 71effb587bfb82ecae18afda67b05fffd2127052
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
ms.locfileid: "30015256"
---
# <a name="intune-on-azure-console-and-legacy-intune-pc-client"></a>Console voor Intune in Azure en verouderde Intune PC Client

Intune is onlangs overgestapt op een architectuur op basis van Azure SaaS-toepassingsservices. Azure biedt aanzienlijke verbeteringen op het gebied van schaal, prestaties en capaciteit. Door deze overstap is ook het beheer van Intune verbeterd en zijn de werkstromen in Azure Portal geoptimaliseerd. 

Houd bij het gebruik van Intune in Azure voor het beheren van Windows-apparaten van uw organisatie rekening met de volgende punten:

## <a name="legacy-pc-client-features-are-only-available-in-the-silverlight-console"></a>Verouderde PC Client-functies zijn alleen beschikbaar in de Silverlight-console

De werkstromen voor Intune PC Client-beheer maken gebruik van de [op Silverlight gebaseerde Intune-beheerconsole](https://manage.microsoft.com/). Dat heeft de volgende consequenties:

- Voor alle beheertaken die niet met groepering te maken hebben en die de Intune PC Client gebruiken, hebt u de Silverlight-console nodig.
- Bij het beheren van groepen moet u de [Intune in Azure Portal](https://portal.azure.com/) gebruiken. Dit is vereist omdat Intune nu Azure AD-groepen gebruikt in plaats van verouderde Intune-groepen. 

Vanwege de overstap naar Azure AD-groepen is het 'op groepen gebaseerd' filteren in de dashboardweergaven van de Silverlight-console enigszins gewijzigd. Als u wilt filteren in de bijgewerkte Silverlight-UI, voert u de volgende stappen uit:

1. Selecteer een weergave.
2. Voer in het vak **Filters** de naam in van de groep waarop u wilt filteren en druk op Enter. Hiermee wordt de lijstweergave gefilterd op de apparaten in die specifieke groep.

   ![](media/intune_on_azure/image01.png)

## <a name="manage-windows-10-devices-by-using-mdm"></a>Windows 10-apparaten beheren via MDM

Het is raadzaam gebruik te maken van [Mobile Device Management (MDM) voor het beheren van uw Windows 10-apparaten](https://docs.microsoft.com/intune/device-restrictions-windows-10) in plaats van de verouderde Intune PC Client. De mogelijkheid voor het beheren van Windows 10 via MDM is beschikbaar in de Intune in Azure Portal. Windows 10 MDM biedt veel nieuwe beheer- en beveiligingsmogelijkheden die niet beschikbaar zijn via de verouderde Intune PC Client.

## <a name="continue-to-manage-windows-7-by-using-intune-pc-client"></a>Doorgaan met het beheren van Windows 7 met behulp van Intune PC Client

Voor Windows 7, dat niet kan worden beheerd via MDM, blijven we bestaande mogelijkheden voor Intune PC Client alleen in de Silverlight-console ondersteunen. U kunt migratie naar MDM-beheer overwegen wanneer u een upgrade naar Windows 10 uitvoert.

## <a name="mdm-capabilities"></a>MDM-mogelijkheden

Zie [Het beheren van Windows-pc's als computers of mobiele apparaten vergelijken](https://docs.microsoft.com/intune-classic/deploy-use/pc-management-comparison) voor een gedetailleerde vergelijking tussen de mogelijkheden voor PC Client en MDM. Met MDM-updates komen er voortdurend nieuwe beheermogelijkheden beschikbaar voor bij MDM ingeschreven Windows 10-apparaten, met inbegrip van evaluatie-opties voor Win 32-apps. Zie [Wat is er nieuw](https://docs.microsoft.com/intune/whats-new) voor de toevoegingen in de laatste release aan de service.

## <a name="switch-from-pc-client-to-mdm"></a>Overschakelen van PC Client naar MDM

Als u wilt overschakelen van het beheren van Windows 10-apparaten met de Intune PC Client naar beheer met MDM , voert u de volgende stappen uit:

1. Voer in de Silverlight-console **selectief wissen** uit om de inschrijving van het apparaat in de PC Client ongedaan te maken.
  ![](media/intune_on_azure/image02.png)
2. Schrijf het apparaat opnieuw in met behulp van [MDM (en/of Azure AD Join)](https://docs.microsoft.com/intune/windows-enroll). 

## <a name="next-steps"></a>Volgende stappen
[Windows-apparaten inschrijven](https://docs.microsoft.com/intune/windows-enroll)

 
