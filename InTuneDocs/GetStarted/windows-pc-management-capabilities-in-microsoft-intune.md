---
title: Beheermogelijkheden voor Windows-pc's | Microsoft Intune
description: Meer informatie over de mogelijkheden van Intune wanneer u Windows-pc's beheert met de Intune-clientsoftware.
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 77fa5c66-a87c-47df-964c-800eea509b33
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a6caef9e0f4d6235ecf1a89c1765d6c8e6ce1a7b
ms.openlocfilehash: e5e3833a38434d4fe55cae554fc49f567b606ad8


---

# Beheermogelijkheden voor Windows-pc's (met de Microsoft Intune-pc-client)
In de meeste gevallen schrijft u uw apparaten in bij Microsoft Intune, waarmee u over een groter aantal mogelijkheden beschikt dan bij de Intune-pc-client. U kunt echter ook pc's beheren met behulp van de Intune-pc-client, die u de volgende functies biedt:

-   **Beheer van software-updates**: u kunt computers up-to-date houden en bepalen wanneer updates moeten worden toegepast.

-   **Windows Firewall-beleid**: hiermee kunt u ervoor zorgen dat geen enkele computer die door uw bedrijf wordt gebruikt, een niet-actieve of niet goed geconfigureerde Windows Firewall heeft.

-   **Anti-malwarebeveiliging**: in Intune is Endpoint Protection opgenomen, waarmee uw computers worden beschermd tegen malware.

-   **Hulp op afstand**: met Intune kunnen gebruikers contact opnemen met IT-ondersteuningsmedewerkers, die vervolgens hulp kunnen bieden met de functie Extern bureaublad, die in Intune is opgenomen (vereist TeamViewer-software).

-   **Softwarelicentiebeheer**: houdt bij hoeveel softwarelicenties er nog beschikbaar zijn en hoeveel licenties er al worden gebruikt.
-   **App-implementatie**: implementeer software op pc's die u beheert. Bepaalde app-beheerfuncties zijn niet beschikbaar wanneer u pc's met de clientsoftware beheert.


Intune biedt ondersteuning voor maximaal 7000 installaties van de pc-clientsoftware op Windows-apparaten.

## Besturingssysteemvereisten
Intune kan computers beheren met de volgende Windows-versies (zowel 32-bits als 64-bits):


-   **Windows Vista**: de versies Business, Enterprise en Ultimate

-   **Windows 7**: de versies Pro, Enterprise en Ultimate (zonder servicepack of met SP1)

-   **Windows 8**: de versies Pro en Enterprise

-   **Windows 8.1**: de versies Pro en Enterprise

- **Windows 10**: de versies Pro, Education en Enterprise


## Minimale hardwarevereisten
Hier volgen de minimale hardwarevereisten voor het installeren van de Intune-pc-client:

|Vereiste|Details|
|---------------|--------------------|
|Netwerk|De client vereist dat de computer een internetverbinding heeft.|
|Processor en geheugen|Raadpleeg de vereisten voor de processor en het RAM-geheugen voor het besturingssysteem van de computer.|
|Schijfruimte|200 MB vrije schijfruimte voordat de clientsoftware wordt geïnstalleerd.|

## Overige vereisten
Hier volgen de softwarevereisten voor het installeren van de Intune-pc-client:

|Vereiste|Details|
|---------------|--------------------|
|Beheermachtigingen|Het account waarmee de clientsoftware wordt geïnstalleerd, moet lokale beheerdersmachtigingen voor die computer hebben.|
|Windows Installer 3.1|De computer moet minimaal Windows Installer 3.1 hebben.|
|Niet-compatibele clientsoftware verwijderen|Voordat u de Intune-pc-clientsoftware installeert, moet u de volgende clientsoftware van die computer verwijderen:<br /><br />- Alle versies van Configuration Manager<br />- Alle versies van Microsoft Systems Management Server (SMS)|

### Zie tevens
[Beheermogelijkheden voor mobiele apparaten in Microsoft Intune](./mobile-device-management-capabilities-in-microsoft-intune.md)



<!--HONumber=Aug16_HO3-->


