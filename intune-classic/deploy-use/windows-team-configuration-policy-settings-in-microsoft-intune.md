---
title: Instellingen voor configuratiebeleid van Windows Team
description: Gebruik het **algemene configuratiebeleid voor Windows 10 Team** om instellingen te configureren voor geregistreerde Windows 10 Team-apparaten, zoals de Microsoft Surface Hub.
keywords: ''
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 38194ef3-e26e-4682-958d-14b395fccba1
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 70b1091cd58439b7d42eab1a612b0b63ca39103d
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="windows-team-configuration-policy-settings-in-microsoft-intune"></a>Instellingen voor configuratiebeleid voor Windows Team in Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Gebruik het **algemene configuratiebeleid voor Windows 10 Team** om instellingen te configureren voor geregistreerde Windows 10 Team-apparaten, zoals de Microsoft Surface Hub.


|                                  Naam van de instelling                                   |                                                                                                                                                                Details                                                                                                                                                                |
|---------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <strong>Scherm automatisch laten activeren wanneer iemand zich in de ruimte bevindt</strong>   |                                                                                                                         Hiermee kunt u het apparaat automatisch laten activeren als de sensor detecteert dat er iemand in de ruimte aanwezig is.                                                                                                                          |
|              <strong>Pincode vereisen voor draadloze projectie</strong>               |                                                                                                             Hiermee geeft u op of u een pincode moet invoeren voordat u de mogelijkheden voor draadloze projectie van het apparaat kunt gebruiken.                                                                                                             |
|          <strong>Een onderhoudsvenster voor apparaatupdates instellen</strong>           |                                                                                          Hiermee configureert u het onderhoudsvenster waarbinnen updates op het apparaat kunnen worden uitgevoerd. U kunt de starttijd en de duur (van 1-5 uur) van het venster configureren.                                                                                           |
|               
  <strong>Operational Insights van Azure inschakelen</strong>                |                  Operational Insights van Azure, onderdeel van de Microsoft Operations Manager-suite, verzamelt, bewaart en analyseert logbestandgegevens van Windows 10 Team-apparaten.<br /><br />Als u verbinding wilt maken met Operational Insights van Azure, moet u een <strong>Werkruimte-id</strong> en een <strong>Werkruimtesleutel</strong> opgeven.                   |
|              <strong>Draadloze Miracast-projectie inschakelen</strong>               |                                          Schakel deze optie in als u wilt dat het Windows 10 Team-apparaat Miracast-compatibele apparaten gebruikt om te projecteren.<br /><br />Als u deze optie inschakelt, selecteer dan bij <strong>Miracast-kanaal kiezen</strong> het Miracast-kanaal dat wordt gebruikt om inhoud te projecteren.                                           |
| <strong>Kiezen welke vergaderingsinformatie wordt weergegeven op het welkomstscherm</strong> | Als u deze optie inschakelt, kunt u de informatie kiezen die wordt weergegeven op de tegel <strong>Vergaderingen</strong> van het scherm <strong>Welkom</strong>. U kunt het volgende doen:<br /><br />-   <strong>Alleen de organisator en tijd weergeven</strong><br />-   <strong>Organisator, tijd en onderwerp weergeven (onderwerp verborgen bij privévergaderingen)</strong> |
|                <strong>URL naar de achtergrondafbeelding van het vergrendelingsscherm</strong>                 |                                           Schakel deze instelling in om via de URL die u opgeeft, een aangepaste achtergrond weer te geven op het scherm <strong>Welkom</strong> van Windows 10 Team-apparaten.<br /><br />De afbeelding moet een bestand met PNG-indeling zijn en de URL moet beginnen met <strong>https://</strong>.                                            |

### <a name="see-also"></a>Zie ook
[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

