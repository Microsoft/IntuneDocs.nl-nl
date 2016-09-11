---
title: Exchange ActiveSync Device Management | Microsoft Intune
description: Mobiele apparaten beheren met Exchange ActiveSync-beheer (EAS) met de Exchange Connector
keywords: 
author: nathbarn
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 14f5cf53-6764-4e22-a18b-fa750b3acd41
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: de3296e81c88b3ac04e3ba3f3d3ca222a59df7bd
ms.openlocfilehash: 96d8911dafe7897458297867ddfef97206fdfc9c


---

# Mobiele apparaten met Exchange ActiveSync beheren met Microsoft Intune
Als u wilt dat Microsoft Intune mobiele apparaten rechtstreeks beheert, moeten de apparaten zijn [geregistreerd in Intune](get-ready-to-enroll-devices-in-microsoft-intune.md). Als alternatief kunnen beheerders een beperktere beheeroplossing gebruiken, die gebruikmaakt van Exchange ActiveSync-beheer (EAS) met een Exchange Connector. Apparaten kunnen worden beheerd op lokale Exchange-servers en Exchange Online met gebruik van Microsoft Office 365. Intune ondersteunt slechts één type Exchange Connector-verbinding per abonnement.

## Exchange-toegangsregels voor mobiele apparaten ##

Exchange vereist een reeks regels waarin is gedefinieerd wat er gebeurt als mobiele apparaten verbinding proberen te maken met EAS. Deze regels worden beheerd in de Intune-beheerconsole

[Exchange-toegangsregels voor mobiele apparaten](exchange-access-rules-for-mobile-devices.md)

## De Exchange-connector installeren
Met de Exchange-connector kunt u uw Exchange-implementatie in de Intune-console beheren. U moet eerst de juiste Intune-naar-Exchange-connector installeren en configureren. Kies de gewenste optie op basis van het gegeven of u gebruikmaakt van een lokale Exchange-server of van in de cloud gehoste Exchange:

-   [Intune configureren voor Exchange Online- of nieuwe Exchange Online Dedicated-omgevingen](intune-service-to-service-exchange-connector.md)
-   [De Intune-connector installeren voor lokale Exchange-servers en oudere Exchange Online Dedicated-omgevingen](intune-on-premises-exchange-connector.md)


## Beleid voor door Exchange beheerde mobiele apparaten toepassen
De Intune-console kan worden gebruikt voor het beheren van [EAS-beleidsinstellingen](exchange-activesync-policy-settings-in-microsoft-intune.md) en het [beperken van de toegang tot bedrijfsbronnen](restrict-access-to-email-and-o365-services-with-microsoft-intune.md). Voor een lijst met Exchange ActiveSync-beleidsinstellingen en -functies die worden ondersteund door specifieke mobiele apparaten, raadpleegt u de [Exchange ActiveSync Client Comparison Table](http://go.microsoft.com/fwlink/?LinkId=247270).

> [!NOTE]
> Wanneer u Intune hebt verbonden met een Microsoft Exchange-omgeving, wordt het EAS-beleid van alle gebruikers die via Intune worden beheerd, opnieuw ingesteld op het huidige standaardbeleid op de Microsoft Exchange-server, tenzij er binnen Intune een meer specifiek beleid is gedefinieerd.

## Bedrijfsgegevens van mobiele apparaten wissen
Ten slotte kunt u [bedrijfsgegevens van door EAS beheerde mobiele apparaten wissen](wipe-for-exchange-managed-mobile-devices.md) wanneer deze apparaten niet langer in gebruik zijn, of zijn gestolen of verloren.



<!--HONumber=Jul16_HO5-->


