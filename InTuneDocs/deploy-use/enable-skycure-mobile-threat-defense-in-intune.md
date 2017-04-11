---
title: Skycure Mobile Threat Defense inschakelen in Intune | Microsoft Docs
description: Schakel in de klassieke Intune-console Skycure Mobile Threat Defense in.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0cc4e59d-819a-47a2-a26f-4f8d0f8df7bf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e76d66768ac58df25313e102b7f60d2bc7bbc59b
ms.openlocfilehash: a110f2ae4d8a101a7fb977aa651e5ce2c8828e7e
ms.lasthandoff: 03/22/2017


---

# <a name="enable-skycure-mobile-threat-defense-in-intune"></a>Skycure Mobile Threat Defense inschakelen in Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Als u de verbinding voor Skycure Mobile Threat Defense (MTD) wilt inschakelen in Intune, moet u de [Intune-connector al in de Skycure-console](https://docs.microsoft.com/intune/deploy-use/setup-the-skycure-integration-with-Intune) hebben geconfigureerd.

## <a name="to-enable-the-skycure-mtd-connection-in-intune"></a>De verbinding voor Skycure MTD inschakelen in Intune

1.  Ga naar de [klassieke Intune-console](https://manage.microsoft.com/) en voer vervolgens uw referenties in.

2.  Kies **Admin** &gt; **Integratie van een service van derden** en kies vervolgens **Skycure-status** en schakel **Synchronisatie met MTD** in met behulp van de wisselknop.

    ![De wisselknop voor het inschakelen van Skycure in de klassieke Intune-console](../media/mtp/enable-skycure-1.png)

> [!IMPORTANT] 
> U moet de Skycure-apps configureren voordat u de regels voor het nalevingsbeleid maakt en de voorwaardelijke toegang configureert. Dit zorgt ervoor dat de app beschikbaar is voor eindgebruikers en moet worden geïnstalleerd voordat ze toegang kunnen krijgen tot e-mail of andere bedrijfsbronnen.

Hiermee is het instellen van de Skycure- en Intune-integratie in de Intune-beheerconsole voltooid. De volgende stappen voor het implementeren van deze oplossing hebben betrekking op de implementatie van de Skycure for Work-apps en het instellen van het nalevingsbeleid.

## <a name="next-steps"></a>Volgende stappen

[Het nalevingsbeleid voor Skycure Mobile Threat Defense maken](https://docs.microsoft.com/intune/deploy-use/create-skycure-mobile-threat-defense-compliance-policy)

