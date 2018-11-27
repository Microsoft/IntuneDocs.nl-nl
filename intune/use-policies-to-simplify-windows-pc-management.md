---
title: Beleid gebruiken om het beheer van Windows-pc's te vereenvoudigen
titlesuffix: Microsoft Intune
description: Hierin worden het beheerbeleid voor Windows-pc's en de instellingen voor Microsoft Intune Center beschreven.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f0afda7e-f4c3-4bcd-b4bf-4304103cf73e
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.openlocfilehash: 56c81c04c4ee6ae319cb54f513b80738f2fbe5fb
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52188023"
---
# <a name="use-policies-to-simplify-windows-pc-management"></a>Beleid gebruiken om het beheer van Windows-pc's te vereenvoudigen

[!INCLUDE [classic-portal](includes/classic-portal.md)]

Als u Windows-desktops als pc's wilt beheren, door daarop de Intune-softwareclient uit te voeren, kunt u alleen gebruikmaken van de beleidsregels onder het **Computerbeheer**-beleid in de Intune-beheerconsole. Alle in de beheerconsole vermelde beleidsregels gelden alleen voor mobiele apparaten. Met het **Computerbeheer**-beleid kunt u de instellingen configureren in Microsoft Intune Center, de updates naar pc's beheren en Windows Firewall voor pc's configureren.

![Beleidssjablonen voor Windows-pc’s](media/pc_policy_template.png)

### <a name="manage-the-microsoft-intune-center"></a>Het Microsoft Intune Center beheren
Gebruikers zien de Intune-softwareclient als het **Microsoft Intune Center**. Met het Microsoft Intune Center kunnen gebruikers:

-   Toepassingen ophalen via de bedrijfsportal.

-   Controleren op updates.

-   Microsoft Intune Endpoint Protection beheren.

-  Hulp op afstand vragen.

Het Microsoft Intune Center wordt geïnstalleerd op alle beheerde computers. U kunt de volgende instellingen in een Intune-beleid configureren en deze instellingen worden weergegeven aan gebruikers in het Microsoft Intune Center:

|Beleidsinstelling|Details|
|------------------|--------------------|
|**Naam**|De naam van de beheerder die de computer beheert.<br />Maximale lengte: 40 tekens|
|**Telefoonnummer**|Het telefoonnummer van de beheerder die de computer beheert.<br />Maximale lengte: 20 tekens|
|**E-mailadres**|Het e-mailadres van de beheerder die de computer beheert.<br />Maximale lengte: 40 tekens|
|**Websitenaam**|De naam van uw ondersteuningswebsite voor gebruikers.<br />>Maximale lengte: 40 tekens|
|**Website-URL**|De URL van uw ondersteuningswebsite.<br />Maximale lengte: 150 tekens|
|**Opmerkingen**|Een opmerking die wordt weergegeven voor gebruikers.<br />Maximale lengte: 120 tekens|

Zie de volgende bronnen voor meer informatie over beleidsregels en instellingen die u voor Windows-pc's kunt configureren:

- [Windows-computers up-to-date houden met software-updates in Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) - op basis van deze beleidsregels controleren beheerde computers op software-updates van Microsoft en derden en worden de updates gedownload. Dit geldt niet voor updates van het besturingssysteem (bijvoorbeeld een upgrade van Windows 7 naar Windows 10 of een upgrade van een Windows 10-versie naar een nieuwere versie).

- [Help Windows-pc's beveiligen met Endpoint Protection Help voor Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) - deze instellingen omvatten onder meer scanschema's en te ondernemen acties wanneer schadelijke software wordt gedetecteerd.

- [Windows-pc's beschermen met Windows Firewall-beleid in Microsoft Intune](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) - deze beleidsregels vereenvoudigen het beheer van Windows Firewall-instellingen op beheerde computers.


### <a name="see-also"></a>Zie ook

[Algemene beheertaken voor Windows-pc's met de Intune-softwareclient](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)
