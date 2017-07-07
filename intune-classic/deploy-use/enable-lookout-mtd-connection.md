---
title: Lookout MTP in Intune inschakelen
description: Lookout Mobile Threat Protection inschakelen in de Intune-beheerconsole.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f835fd0-4e62-42f3-b7ca-ce8b7ddd40e4
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: aad5b158e1217155c3e3ec671654ee6e81054675
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="enable-lookout-mtd-connection-in-the-intune-classic-console"></a>De verbinding voor Lookout MTD inschakelen in de klassieke Intune-console

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Als u de verbinding voor Lookout Mobile Threat Defense (MTD) wilt inschakelen in Intune, moet u de Intune-connector al hebben geconfigureerd in de Lookout-console.  Als u dit nog niet hebt gedaan, moet u [uw Lookout Mobile Threat Defense-abonnement instellen](setup-your-lookout-mtd-subscription.md).

Kies op de pagina **Beheer** in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) de optie **Integratie van externe service** om de Lookout MTP-verbinding in te schakelen in Intune. Kies **Lookout-status** en schakel **Synchronisatie met MTP** in met behulp van de wisselknop.

![schermopname van de synchronisatiepagina voor Lookout met de ingeschakelde wisselknop gemarkeerd](../media/mtp/lookout-intune-synchronization.png)

>[!IMPORTANT]
> U **moet** de Lookout for Work-app configureren voordat u nalevingsbeleid maakt en voorwaardelijke toegang configureert. Dit zorgt ervoor dat de app beschikbaar is voor eindgebruikers en moet worden geïnstalleerd voordat ze toegang kunnen krijgen tot e-mail of andere bedrijfsbronnen.

Hiermee is de integratie van Lookout en Intune in de Intune-beheerconsole voltooid.  De volgende stappen omvatten de implementatie van het beleid voor [Lookout for Work-apps](/intune-classic/deploy-use/device-threat-protection-policy).


## <a name="next-steps"></a>Volgende stappen
[Lookout for Work-app configureren ](/intune-classic/deploy-use/device-threat-protection-apps)
