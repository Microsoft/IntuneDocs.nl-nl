---
title: Instellingen voor configuratiebeleid van Windows Team
description: Gebruik het **algemene configuratiebeleid voor Windows 10 Team** om instellingen te configureren voor geregistreerde Windows 10 Team-apparaten, zoals de Microsoft Surface Hub.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38194ef3-e26e-4682-958d-14b395fccba1
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6e0f0ea969ed78f2daf482438b056c8b4eb1a316
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="windows-team-configuration-policy-settings-in-microsoft-intune"></a>Instellingen voor configuratiebeleid voor Windows Team in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Gebruik het **algemene configuratiebeleid voor Windows 10 Team** om instellingen te configureren voor geregistreerde Windows 10 Team-apparaten, zoals de Microsoft Surface Hub.

|Naam van de instelling|Details|
|----------------|-----------|
|**Scherm automatisch laten activeren wanneer iemand zich in de ruimte bevindt**|Hiermee kunt u het apparaat automatisch laten activeren als de sensor detecteert dat er iemand in de ruimte aanwezig is.|
|**Pincode vereisen voor draadloze projectie**|Hiermee geeft u op of u een pincode moet invoeren voordat u de mogelijkheden voor draadloze projectie van het apparaat kunt gebruiken.|
|**Een onderhoudsvenster voor apparaatupdates instellen**|Hiermee configureert u het onderhoudsvenster waarbinnen updates op het apparaat kunnen worden uitgevoerd. U kunt de starttijd en de duur (van 1-5 uur) van het venster configureren.|
|**Operationeel inzicht van Azure inschakelen**|Opertioneel inzicht van Azure, onderdeel van de Microsoft Operations Manager-suite, verzamelt, bewaart en analyseert logbestandgegevens van Windows 10 Team-apparaten.<br /><br />Als u verbinding wilt maken met Operationeel inzicht van Azure, moet u een **Werkruimte-id** en een **Werkruimtesleutel** opgeven.|
|**Draadloze Miracast-projectie inschakelen**|Schakel deze optie in als u wilt dat het Windows 10 Team-apparaat Miracast-compatibele apparaten gebruikt om te projecteren.<br /><br />Als u deze optie inschakelt, selecteer dan bij **Miracast-kanaal kiezen** het Miracast-kanaal dat wordt gebruikt om inhoud te projecteren.|
|**Kiezen welke vergaderingsinformatie wordt weergegeven op het welkomstscherm**|Als u deze optie inschakelt, kunt u de informatie kiezen die wordt weergegeven op de tegel **Vergaderingen** van het scherm **Welkom**. U kunt het volgende doen:<br /><br />-   **Alleen de organisator en tijd weergeven**<br />-   **Organisator, tijd en onderwerp weergeven (onderwerp verborgen bij privévergaderingen)**|
|**URL naar de achtergrondafbeelding van het vergrendelingsscherm**|Schakel deze instelling in om via de URL die u opgeeft, een aangepaste achtergrond weer te geven op het scherm **Welkom** van Windows 10 Team-apparaten.<br /><br />De afbeelding moet een bestand met PNG-indeling zijn en de URL moet beginnen met **https://**.|


### <a name="see-also"></a>Zie tevens
[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

