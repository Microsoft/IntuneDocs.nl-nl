---
title: Verouderde Intune-client voor pc en Intune in Azure
description: Overwegingen bij het gebruik van Intune in Azure voor het beheren van Windows-apparaten van uw organisatie.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/15/2018
ms.topic: archived
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.assetid: 1f104923-12df-453c-9c20-942ef65a0945
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5ab1be3d34d52e824d1ff06124e28206fb7b07a1
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72510187"
---
# <a name="intune-on-azure-console-and-legacy-intune-pc-client"></a>Console voor Intune in Azure en verouderde Intune-client voor pc

Intune maakt gebruik van een architectuur op basis van Azure SaaS-toepassingsservices. Azure biedt aanzienlijke verbeteringen op het gebied van schaal, prestaties en capaciteit. Dit biedt verbeterd beheer van Intune en geoptimaliseerde werkstromen in Azure Portal. 

Houd bij het gebruik van Intune in Azure voor het beheren van Windows-apparaten van uw organisatie rekening met de volgende punten:

## <a name="manage-windows-10-devices-by-using-mdm"></a>Windows 10-apparaten beheren via MDM

Het is raadzaam gebruik te maken van [Mobile Device Management (MDM) voor het beheren van uw Windows 10-apparaten](../configuration/device-restrictions-windows-10.md) in plaats van de verouderde Intune PC Client. De mogelijkheid voor het beheren van Windows 10 via MDM is beschikbaar in de Intune in Azure Portal. Windows 10 MDM biedt veel nieuwe beheer- en beveiligingsmogelijkheden die niet beschikbaar zijn via de verouderde Intune PC Client.

## <a name="legacy-pc-client-features-are-only-available-in-the-silverlight-console"></a>Verouderde PC Client-functies zijn alleen beschikbaar in de Silverlight-console

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

De werkstromen voor Intune PC Client-beheer maken gebruik van de [op Silverlight gebaseerde Intune-beheerconsole](https://manage.microsoft.com/). Dat heeft de volgende consequenties:

- Voor alle beheertaken die niet met groepering te maken hebben en die de Intune PC Client gebruiken, hebt u de Silverlight-console nodig.
- Bij het beheren van groepen moet u de [Intune in Azure Portal](https://portal.azure.com/) gebruiken. Dit is vereist omdat Intune nu Azure AD-groepen gebruikt in plaats van verouderde Intune-groepen. 

Vanwege de overstap naar Azure AD-groepen is het 'op groepen gebaseerd' filteren in de dashboardweergaven van de Silverlight-console enigszins gewijzigd. Als u wilt filteren in de bijgewerkte Silverlight-UI, voert u de volgende stappen uit:

1. Selecteer een weergave.
2. Voer in het vak **Filters** de naam in van de groep waarop u wilt filteren en druk op Enter. Hiermee wordt de lijstweergave gefilterd op de apparaten in die specifieke groep.

   ![Invoer vervolg keuzelijst voor filters met geen geselecteerd](./media/intune-legacy-pc-client/image01.png)


## <a name="continue-to-manage-windows-7-by-using-intune-pc-client"></a>Doorgaan met het beheren van Windows 7 met behulp van Intune PC Client

Voor Windows 7, dat niet kan worden beheerd via MDM, blijven we bestaande mogelijkheden voor Intune PC Client alleen in de Silverlight-console ondersteunen. U kunt migratie naar MDM-beheer overwegen wanneer u een upgrade naar Windows 10 uitvoert.

## <a name="mdm-capabilities"></a>MDM-mogelijkheden

Zie [Het beheren van Windows-pc's als computers of mobiele apparaten vergelijken](pc-management-comparison.md) voor een gedetailleerde vergelijking tussen de mogelijkheden voor PC Client en MDM. Met MDM-updates komen er voortdurend nieuwe beheermogelijkheden beschikbaar voor bij MDM ingeschreven Windows 10-apparaten, met inbegrip van evaluatie-opties voor Win 32-apps. Zie [Wat is er nieuw](whats-new.md) voor de toevoegingen in de laatste release aan de service.

## <a name="switch-from-pc-client-to-mdm"></a>Overschakelen van PC Client naar MDM

Als u wilt overschakelen van het beheren van Windows 10-apparaten met de Intune PC Client naar beheer met MDM , voert u de volgende stappen uit:

1. Voer in de Silverlight-console **selectief wissen** uit om de inschrijving van het apparaat in de PC Client ongedaan te maken.
  ![waarschuwing pop-up met het keuze rondje ' selectief wissen van het apparaat ' is geselecteerd](./media/intune-legacy-pc-client/image02.png)
2. Schrijf het apparaat opnieuw in met behulp van [MDM (en/of Azure AD Join)](../enrollment/windows-enroll.md).

## <a name="next-steps"></a>Volgende stappen
[Windows-apparaten inschrijven](../enrollment/windows-enroll.md)
