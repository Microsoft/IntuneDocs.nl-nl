---
title: Microsoft Intune-apparaatbeperkingen voor Windows 10 Team
titlesuffix: ''
description: Meer informatie over de apparaatbeperkingen die beschikbaar zijn voor apparaten met Windows 10 Team.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ea48fdcafb0a4e8ab634873e512cde40407bd1cc
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57233573"
---
# <a name="microsoft-intune-windows-10-team-device-restriction-settings"></a>Microsoft Intune Windows 10 Team-apparaatbeperkingsinstellingen

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In dit artikel komt u meer te weten over de Microsoft Intune-apparaatbeperkingsinstellingen die u kunt configureren voor apparaten met Windows 10 Team.


## <a name="apps-and-experience"></a>Apps en ervaring

- **Scherm activeren wanneer iemand in de ruimte is**: hiermee kunt u het apparaat automatisch laten activeren als de sensor detecteert dat er iemand in de ruimte aanwezig is.
- **Informatie over de vergadering die wordt weergegeven op het aanmeldingsscherm**: schakel deze optie in als u de informatie wilt kiezen die wordt weergegeven op de tegel Vergaderingen van het scherm Welkom. U kunt het volgende doen:
    - **Alleen de organisator en tijd weergeven**
    - **Organisator, tijd en onderwerp weergeven (onderwerp verborgen bij privévergaderingen)**
- **URL van de achtergrondafbeelding voor het aanmeldingsscherm**: schakel deze instelling in om via de URL die u opgeeft, een aangepaste achtergrond weer te geven op het scherm **Welkom** van Windows 10 Team-apparaten.<br>De afbeelding moet een bestand met PNG-indeling zijn en de URL moet beginnen met **https://**.

## <a name="azure-operational-insights"></a>Operational Insights van Azure

- **Azure Operational Insights**: Azure Operational Insights, onderdeel van de Microsoft Operations Manager-suite, verzamelt, bewaart en analyseert logbestandsgegevens van Windows 10 Team-apparaten.
Als u verbinding wilt maken met Operational Insights van Azure, moet u een **Werkruimte-id** en een **Werkruimtesleutel** opgeven.

## <a name="maintenance"></a>Onderhoud

- **Onderhoudsvenster voor updates**: hiermee configureert u het onderhoudsvenster waarbinnen updates op het apparaat kunnen worden uitgevoerd. U kunt de **starttijd** en de **duur in uren** (1-5 uur) van het venster configureren.

## <a name="wireless-projection"></a>Draadloze projectie

- **Pincode voor draadloze projectie**: hiermee geeft u aan of u een pincode moet invoeren voordat u de mogelijkheden voor draadloze projectie van het apparaat kunt gebruiken.
- **Draadloze Miracast-projectie**: als u wilt dat het Windows 10 Team-apparaat Miracast-compatibele apparaten gebruikt om te projecteren, schakelt u deze optie in.
- **Draadloos Miracast-projectiekanaal**: kies het Miracast-kanaal dat u gebruikt om de verbinding te maken.


## <a name="next-steps"></a>Volgende stappen

Gebruik de informatie in [Intune- apparaatbeperkingsinstellingen configureren](device-restrictions-configure.md) om het profiel op te slaan en toe te wijzen aan gebruikers en apparaten.
