---
title: Verouderde Intune-client voor pc en Intune in Azure
description: Overwegingen bij het gebruik van Intune in Azure voor het beheren van Windows-apparaten van uw organisatie.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 071fe12df19a86e29bb7a36e3a6634fe5adb9fcd
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55848437"
---
# <a name="intune-on-azure-console-and-legacy-intune-pc-client"></a>Console voor Intune in Azure en verouderde Intune-client voor pc

Intune maakt gebruik van een architectuur op basis van Azure SaaS-toepassingsservices. Azure biedt aanzienlijke verbeteringen op het gebied van schaal, prestaties en capaciteit. Dit biedt verbeterd beheer van Intune en geoptimaliseerde werkstromen in Azure Portal. 

Houd bij het gebruik van Intune in Azure voor het beheren van Windows-apparaten van uw organisatie rekening met de volgende punten:

## <a name="manage-windows-10-devices-by-using-mdm"></a>Windows 10-apparaten beheren via MDM

Het is raadzaam gebruik te maken van [Mobile Device Management (MDM) voor het beheren van uw Windows 10-apparaten](https://docs.microsoft.com/intune/device-restrictions-windows-10) in plaats van de verouderde Intune PC Client. De mogelijkheid voor het beheren van Windows 10 via MDM is beschikbaar in de Intune in Azure Portal. Windows 10 MDM biedt veel nieuwe beheer- en beveiligingsmogelijkheden die niet beschikbaar zijn via de verouderde Intune PC Client.

## <a name="legacy-pc-client-features-are-only-available-in-the-silverlight-console"></a>Verouderde PC Client-functies zijn alleen beschikbaar in de Silverlight-console

De werkstromen voor Intune PC Client-beheer maken gebruik van de [op Silverlight gebaseerde Intune-beheerconsole](https://manage.microsoft.com/). Dat heeft de volgende consequenties:

- Voor alle beheertaken die niet met groepering te maken hebben en die de Intune PC Client gebruiken, hebt u de Silverlight-console nodig.
- Bij het beheren van groepen moet u de [Intune in Azure Portal](https://portal.azure.com/) gebruiken. Dit is vereist omdat Intune nu Azure AD-groepen gebruikt in plaats van verouderde Intune-groepen. 

Vanwege de overstap naar Azure AD-groepen is het 'op groepen gebaseerd' filteren in de dashboardweergaven van de Silverlight-console enigszins gewijzigd. Als u wilt filteren in de bijgewerkte Silverlight-UI, voert u de volgende stappen uit:

1. Selecteer een weergave.
2. Voer in het vak **Filters** de naam in van de groep waarop u wilt filteren en druk op Enter. Hiermee wordt de lijstweergave gefilterd op de apparaten in die specifieke groep.

   ![](media/intune-legacy-pc-client/image01.png)


## <a name="continue-to-manage-windows-7-by-using-intune-pc-client"></a>Doorgaan met het beheren van Windows 7 met behulp van Intune PC Client

Voor Windows 7, dat niet kan worden beheerd via MDM, blijven we bestaande mogelijkheden voor Intune PC Client alleen in de Silverlight-console ondersteunen. U kunt migratie naar MDM-beheer overwegen wanneer u een upgrade naar Windows 10 uitvoert.

## <a name="mdm-capabilities"></a>MDM-mogelijkheden

Zie [Het beheren van Windows-pc's als computers of mobiele apparaten vergelijken](pc-management-comparison.md) voor een gedetailleerde vergelijking tussen de mogelijkheden voor PC Client en MDM. Met MDM-updates komen er voortdurend nieuwe beheermogelijkheden beschikbaar voor bij MDM ingeschreven Windows 10-apparaten, met inbegrip van evaluatie-opties voor Win 32-apps. Zie [Wat is er nieuw](https://docs.microsoft.com/intune/whats-new) voor de toevoegingen in de laatste release aan de service.

## <a name="switch-from-pc-client-to-mdm"></a>Overschakelen van PC Client naar MDM

Als u wilt overschakelen van het beheren van Windows 10-apparaten met de Intune PC Client naar beheer met MDM , voert u de volgende stappen uit:

1. Voer in de Silverlight-console **selectief wissen** uit om de inschrijving van het apparaat in de PC Client ongedaan te maken.
  ![](media/intune-legacy-pc-client/image02.png)
2. Schrijf het apparaat opnieuw in met behulp van [MDM (en/of Azure AD Join)](https://docs.microsoft.com/intune/windows-enroll). 

## <a name="next-steps"></a>Volgende stappen
[Windows-apparaten inschrijven](https://docs.microsoft.com/intune/windows-enroll)

 
