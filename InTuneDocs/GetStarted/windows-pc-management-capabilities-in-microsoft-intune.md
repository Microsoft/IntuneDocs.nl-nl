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
ms.sourcegitcommit: 49a236359692a5bbccf9ee0bb263094434049a91
ms.openlocfilehash: f5ade985900e2387b19b4ed2786f22d8a216d8d8


---

# Beheermogelijkheden voor Windows-pc's (met de Microsoft Intune-pc-client)
In de meeste gevallen schrijft u uw apparaten in bij Microsoft Intune, waarmee u over een groter aantal mogelijkheden beschikt dan bij de Intune-pc-client. U kunt echter ook pc's beheren met behulp van de Intune-pc-client, die u de volgende functies biedt:

-   **Software-updates beheren**: u kunt computers up-to-date houden en beheren wanneer er updates worden toegepast.

-   **Windows Firewall-beleid**: hiermee kunt u ervoor zorgen dat geen enkele computer die door uw bedrijf wordt gebruikt, een niet-actieve of niet goed geconfigureerde Windows Firewall heeft.

-   **Anti-malwarebeveiliging**: in Intune is Endpoint Protection opgenomen, waarmee uw computers worden beschermd tegen malware.

-   **Hulp op afstand**: met Intune kunnen gebruikers contact opnemen met IT-ondersteuningsmedewerkers, die vervolgens hulp kunnen bieden met de functie Extern bureaublad, die in Intune is opgenomen (vereist TeamViewer-software).

-   **Softwarelicentiebeheer**: houdt bij hoeveel softwarelicenties er nog beschikbaar zijn en hoeveel licenties er al worden gebruikt.
-   **App-implementatie**: implementeer software op pc's die u beheert. Bepaalde app-beheerfuncties zijn niet beschikbaar wanneer u pc's met de clientsoftware beheert.


Intune biedt ondersteuning voor maximaal 7000 installaties van de pc-clientsoftware op Windows-apparaten.

## Besturingssysteemvereisten
Intune kan pc’s met de volgende Windows-versies (zowel x86 als x64) beheren:


-   **Windows Vista**: de versies Business, Enterprise en Ultimate.

-   **Windows 7**: de versies Pro, Enterprise en Ultimate (zonder servicepack of met SP1).

-   **Windows 8**: de versies Pro en Enterprise.

-   **Windows 8.1**: de versies Pro en Enterprise.

- **Windows 10**: de versies Pro, Education en Enterprise.


## Minimale hardwarevereisten
Hieronder staan de minimale hardwarevereisten voor het installeren van de Intune-pc-client:

|Vereiste|Details|
|---------------|--------------------|
|Netwerk|De client vereist dat de computer een internetverbinding heeft.|
|Processor en geheugen|Raadpleeg de vereisten voor de processor en het RAM-geheugen voor het besturingssysteem van de computer.|
|Schijfruimte|200 MB vrije schijfruimte voordat de clientsoftware wordt geïnstalleerd.|

## Overige vereisten
Hieronder staan de softwarevereisten voor het installeren van de Intune-pc-client:

|Vereiste|Details|
|---------------|--------------------|
|Beheermachtigingen|Het account waarmee de clientsoftware wordt geïnstalleerd, moet lokale beheerdersmachtigingen op die computer hebben.|
|Windows Installer 3.1|Op de pc moet minimaal Windows Installer 3.1 zijn geïnstalleerd.|
|Niet-compatibele clientsoftware verwijderen|Voordat u de Intune-pc-clientsoftware installeert, moet u de volgende clientsoftware van die computer verwijderen:<br /><br />- Alle versies van Configuration Manager<br />- Alle versies van Microsoft Systems Management Server (SMS)|

### Zie tevens
[Beheermogelijkheden voor mobiele apparaten in Microsoft Intune](./mobile-device-management-capabilities-in-microsoft-intune.md)



<!--HONumber=Aug16_HO1-->


