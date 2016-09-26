---
title: Mogelijkheden voor de Intune-pc-softwareclient | Microsoft Intune
description: Kom meer te weten over de mogelijkheden van Intune wanneer u Windows-pc's beheert met de Intune-softwareclient.
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 09/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 77fa5c66-a87c-47df-964c-800eea509b33
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 453323aa38eed0a01aa8d583376162734439a69c
ms.openlocfilehash: 0d4ec8077e2521b23808fcb537c4b2389fee714a


---

# Windows-pc-beheermogelijkheden wanneer u de Intune-softwareclient gebruikt
In de meeste gevallen registreert u uw apparaten bij Microsoft Intune, waarmee u over een groter aantal mogelijkheden beschikt. U kunt echter ook pc's beheren met behulp van de Intune-softwareclient, die u de volgende functies biedt:

-   **[Beheer van software-updates](/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)**: u kunt computers up-to-date houden en bepalen wanneer updates moeten worden toegepast.

-   **[Windows Firewall-beleid](/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune)**: hiermee kunt u ervoor zorgen dat geen enkele computer die door uw bedrijf wordt gebruikt, een niet-actieve of niet goed geconfigureerde Windows Firewall heeft.

-   **[Anti-malwarebeveiliging](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)**: in Intune is Endpoint Protection opgenomen, waarmee uw computers worden beschermd tegen malware.

-   **[Hulp op afstand](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#request-and-provide-remote-assistance-to-windows-pcs-that-use-the-intune-client-software )**: met Intune kunnen gebruikers contact opnemen met IT-ondersteuningsmedewerkers, die vervolgens hulp kunnen bieden met de functie Extern bureaublad, die in Intune is opgenomen (vereist TeamViewer-software).

-   **[Softwarelicentiebeheer](/intune/deploy-use/manage-license-agreements-for-windows-pc-software-in-microsoft-intune)**: hiermee kunt u bijhouden hoeveel softwarelicenties er nog beschikbaar zijn en hoeveel licenties er al worden gebruikt.
-   **[App-implementatie](/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)**: implementeer software op pc's die u beheert. Bepaalde app-beheerfuncties zijn niet beschikbaar wanneer u pc's met de softwareclient beheert.


Intune biedt ondersteuning voor maximaal 7000 installaties van de softwareclient op Windows-apparaten.

## Besturingssysteemvereisten
Intune kan computers beheren met de volgende Windows-versies (zowel 32-bits als 64-bits):


-   **Windows Vista**: de versies Business, Enterprise en Ultimate

-   **Windows 7**: de versies Pro, Enterprise en Ultimate (zonder servicepack of met SP1)

-   **Windows 8**: de versies Pro en Enterprise

-   **Windows 8.1**: de versies Pro en Enterprise

- **Windows 10**: de versies Pro, Education en Enterprise


## Minimale hardwarevereisten
Hier volgen de minimale hardwarevereisten voor het installeren van de Intune-softwareclient:

|Vereiste|Details|
|---------------|--------------------|
|Netwerk|De client vereist dat de computer een internetverbinding heeft.|
|Processor en geheugen|Raadpleeg de vereisten voor de processor en het RAM-geheugen voor het besturingssysteem van de computer.|
|Schijfruimte|200 MB vrije schijfruimte voordat de clientsoftware wordt geïnstalleerd.|

## Overige vereisten
Hier volgen de minimale softwarevereisten voor het installeren van de Intune-softwareclient:

|Vereiste|Details|
|---------------|--------------------|
|Beheermachtigingen|Het account waarmee de clientsoftware wordt geïnstalleerd, moet lokale beheerdersmachtigingen voor die computer hebben.|
|Windows Installer 3.1|De computer moet minimaal Windows Installer 3.1 hebben.|
|Niet-compatibele clientsoftware verwijderen|Voordat u de Intune-pc-clientsoftware installeert, moet u de volgende clientsoftware van die computer verwijderen:<br /><br />- Alle versies van Configuration Manager<br />- Alle versies van Microsoft Systems Management Server (SMS)|

### Zie tevens
[Beheermogelijkheden voor geregistreerde apparaten in Microsoft Intune](./mobile-device-management-capabilities-in-microsoft-intune.md)



<!--HONumber=Sep16_HO2-->


