---
title: Intune-integratie met Microsoft-cloudservices | Microsoft Intune
description: Intune-integratie met Microsoft-cloudservices en -producten en andere Microsoft-producten
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 49675811-08a3-408f-810b-89552ff404bd
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0d422b421c3716ad576c4fc565b181dec28c947e
ms.openlocfilehash: b2df2a2ec092ed9bb7d12b7f51a4fd9c9858f041


---

# Intune-integratie met Microsoft-cloudservices en -producten

Lees voor de installatie van [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] dit onderwerp en de andere vereisten in [Wat u moet weten voordat u met Microsoft Intune aan de slag gaat](what-to-know-before-you-start-microsoft-intune.md).
##Integratie met andere Microsoft-cloudservices


[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] deelt een algemene basis met andere Microsoft-cloudservices. Als u hetzelfde account gebruikt om u te abonneren op meerdere cloudservices, gebruiken die services uw zelfde Microsoft Azure AD-infrastructuur en zijn ze tenants van Azure AD. Azure AD levert de kernfuncties voor directory- en identiteitsbeheer voor Microsoft-cloudservices.

Meer informatie over [Azure AD beheren](http://technet.microsoft.com/library/hh967611.aspx) vindt u in de TechNet-bibliotheek.

## Integratie met andere Microsoft-producten
U kunt [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] als een zelfstandige cloudservice gebruiken of als een cloudservice die is geïntegreerd met andere producten. Momenteel kan alleen [!INCLUDE[cmshort](../includes/cmshort_md.md)] rechtstreeks worden geïntegreerd met [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

De beslissing om [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] met [!INCLUDE[cmshort](../includes/cmshort_md.md)] te integreren, is een permanente keuze waarbij de instantie voor het beheer van mobiele apparaten vanaf de [!INCLUDE[cmshort](../includes/cmshort_md.md)]-console en niet vanuit de [!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)] moet worden ingesteld. Nadat de instantie voor het beheer van mobiele apparaten is ingesteld, kunt u deze configuratie niet wijzigen of terugdraaien.

Wanneer u [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] gebruikt met [!INCLUDE[cmshort](../includes/cmshort_md.md)], gebruikt u de [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] niet om [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] te beheren, maar gebruikt u in plaats daarvan de [!INCLUDE[cmshort](../includes/cmshort_md.md)]-console. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] maakt nog steeds gebruik van de eigen cloudopslag in Azure voor het hosten van software die u implementeert op apparaten die u beheert met [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

Zie voor meer informatie [Mobiele apparaten beheren met Configuration Manager en Microsoft Intune](https://docs.microsoft.com/en-us/sccm/mdm/understand/hybrid-mobile-device-management) in de SP1-documentatie voor [!INCLUDE[cm5short](../includes/cm5short_md.md)].

### Zie tevens
[Wat u moet weten voordat u met Microsoft Intune aan de slag gaat](what-to-know-before-you-start-microsoft-intune.md)



<!--HONumber=Oct16_HO4-->


