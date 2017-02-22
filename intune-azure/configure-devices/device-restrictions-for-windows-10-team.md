---
title: Intune-apparaatbeperkingsinstellingen voor Windows 10 Team | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: in dit onderwerp vindt u meer informatie over de apparaatbeperkingen die beschikbaar zijn voor Windows 10 Team-apparaten.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 677c41a2-5344-4c52-85f0-809dce3a5d5b
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e6e0540acd5488077ae5217f8862e3bc5462ed71
ms.openlocfilehash: 342681922944fd1ea4be6aa4ddcb0725f6cfd42b


---

# <a name="windows-10-team-device-restriction-settings-in-intune-azure-preview"></a>Windows 10 Team-apparaatbeperkingsinstellingen in Intune Azure Preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

- **Scherm activeren wanneer iemand in de ruimte is**: hiermee kunt u het apparaat automatisch laten activeren als de sensor detecteert dat er iemand in de ruimte aanwezig is.
- **Pincode voor draadloze projectie**: hiermee geeft u aan of u een pincode moet invoeren voordat u de mogelijkheden voor draadloze projectie van het apparaat kunt gebruiken.
- **Draadloze Miracast-projectie**: schakel deze optie in als u wilt dat het Windows 10 Team-apparaat Miracast-compatibele apparaten gebruikt om te projecteren.
- **Informatie over de vergadering die wordt weergegeven op het aanmeldingsscherm**: schakel deze optie in als u de informatie wilt kiezen die wordt weergegeven op de tegel Vergaderingen van het scherm Welkom. U kunt het volgende doen:
    - **Alleen de organisator en tijd weergeven**
    - **Organisator, tijd en onderwerp weergeven (onderwerp verborgen bij privévergaderingen)**
- **URL van de achtergrondafbeelding voor het aanmeldingsscherm**: schakel deze instelling in om via de URL die u opgeeft, een aangepaste achtergrond weer te geven op het scherm **Welkom** van Windows 10 Team-apparaten.<br>De afbeelding moet een bestand met PNG-indeling zijn en de URL moet beginnen met **https://**.
- **Onderhoudsvenster voor updates**: hiermee configureert u het onderhoudsvenster waarbinnen updates op het apparaat kunnen worden uitgevoerd. U kunt de starttijd en de duur (van 1-5 uur) van het venster configureren.
- **Azure Operational Insights**: Azure Operational Insights, onderdeel van de Microsoft Operations Manager-suite, verzamelt, bewaart en analyseert logbestandsgegevens van Windows 10 Team-apparaten.<br>Als u verbinding wilt maken met Operationeel inzicht van Azure, moet u een **Werkruimte-id** en een **Werkruimtesleutel** opgeven.



<!--HONumber=Feb17_HO1-->


