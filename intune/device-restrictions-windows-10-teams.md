---
title: Intune-apparaatbeperkingen voor Windows 10 Team
titlesuffix: Azure portal
description: Meer informatie over de apparaatbeperkingen die beschikbaar zijn voor Windows 10 Team-apparaten.
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 677c41a2-5344-4c52-85f0-809dce3a5d5b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3648f8b273f666d1898226f3da8580e55a6bc6f8
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="windows-10-team-device-restriction-settings-in-microsoft-intune"></a>Windows 10 Team-apparaatbeperkingsinstellingen in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


## <a name="apps-and-experience"></a>Apps en ervaring

- **Scherm activeren wanneer iemand in de ruimte is**: hiermee kunt u het apparaat automatisch laten activeren als de sensor detecteert dat er iemand in de ruimte aanwezig is.
- **Informatie over de vergadering die wordt weergegeven op het aanmeldingsscherm**: schakel deze optie in als u de informatie wilt kiezen die wordt weergegeven op de tegel Vergaderingen van het scherm Welkom. U kunt het volgende doen:
    - **Alleen de organisator en tijd weergeven**
    - **Organisator, tijd en onderwerp weergeven (onderwerp verborgen bij privévergaderingen)**
- **URL van de achtergrondafbeelding voor het aanmeldingsscherm**: schakel deze instelling in om via de URL die u opgeeft, een aangepaste achtergrond weer te geven op het scherm **Welkom** van Windows 10 Team-apparaten.<br>De afbeelding moet een bestand met PNG-indeling zijn en de URL moet beginnen met **https://**.

## <a name="azure-operational-insights"></a>Operationeel inzicht van Azure

- **Azure Operational Insights**: Azure Operational Insights, onderdeel van de Microsoft Operations Manager-suite, verzamelt, bewaart en analyseert logbestandsgegevens van Windows 10 Team-apparaten.
Als u verbinding wilt maken met Operationeel inzicht van Azure, moet u een **Werkruimte-id** en een **Werkruimtesleutel** opgeven.

## <a name="maintenance"></a>Onderhoud

- **Onderhoudsvenster voor updates**: hiermee configureert u het onderhoudsvenster waarbinnen updates op het apparaat kunnen worden uitgevoerd. U kunt de **starttijd** en de **duur in uren** (1-5 uur) van het venster configureren.

## <a name="wireless-projection"></a>Draadloze projectie

- **Pincode voor draadloze projectie**: hiermee geeft u aan of u een pincode moet invoeren voordat u de mogelijkheden voor draadloze projectie van het apparaat kunt gebruiken.
- **Draadloze Miracast-projectie**: als u wilt dat het Windows 10 Team-apparaat Miracast-compatibele apparaten gebruikt om te projecteren, schakelt u deze optie in.
- **Draadloos Miracast-projectiekanaal**: kies het Miracast-kanaal dat u gebruikt om de verbinding te maken.


## <a name="next-steps"></a>Volgende stappen

Gebruik de informatie in [Intune- apparaatbeperkingsinstellingen configureren](device-restrictions-configure.md) om het profiel op te slaan en toe te wijzen aan gebruikers en apparaten.
