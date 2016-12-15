---
title: Lookout MTP inschakelen in Intune | Microsoft Intune
description: Lookout Mobile Threat Protection inschakelen in de Intune-beheerconsole.
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 2f835fd0-4e62-42f3-b7ca-ce8b7ddd40e4
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: 1bef6c15387309e1b36bc85758ca699acd54fdd0


---

# <a name="enable-lookout-mtp-connection-in-the-intune-admin-console"></a>Lookout MTP-verbinding inschakelen in de Intune-beheerconsole.
In dit onderwerp wordt beschreven hoe u de Lookout MTP-verbinding in Intune kunt inschakelen. Voordat u deze stap uitvoert, moet u de Intune-connector al in de Lookout-console hebben geconfigureerd.  Als u dit nog niet hebt gedaan, voert u de stappen uit die in [Uw abonnement instellen met Lookout Mobile Threat Protection](set-up-your-subscription-with-lookout-mtp.md) worden beschreven.

Kies op de pagina **Beheer** in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) de optie **Integratie van externe service** om de Lookout MTP-verbinding in te schakelen in Intune. Kies **Lookout-status** en schakel **Synchronisatie met MTP** in met behulp van de wisselknop.

![schermopname van de synchronisatiepagina voor Lookout met de ingeschakelde wisselknop gemarkeerd](../media/mtp/lookout-intune-synchronization.png)

Hiermee is de integratie van Lookout en Intune in de Intune-beheerconsole voltooid.  De volgende stappen omvatten de implementatie van de [Lookout for Work-apps](configure-and-deploy-lookout-for-work-apps.md) en het instellen van het [nalevingsbeleid](enable-device-threat-protection-rule-in-compliance-policy.md).

>[!IMPORTANT]
> U **moet** de Lookout for Work-app configureren voordat u nalevingsbeleid maakt en voorwaardelijke toegang configureert. Dit zorgt ervoor dat de app beschikbaar is voor eindgebruikers en moet worden geïnstalleerd voordat ze toegang kunnen krijgen tot e-mail of andere bedrijfsbronnen.
## <a name="next-steps"></a>Volgende stappen
[Lookout for Work-app configureren ](configure-and-deploy-lookout-for-work-apps.md)



<!--HONumber=Dec16_HO2-->


