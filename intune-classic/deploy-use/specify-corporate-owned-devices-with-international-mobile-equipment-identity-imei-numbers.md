---
title: IMEI-nummers opgeven
description: Met Microsoft Intune kunnen beheerders IMEI-nummers importeren voor platforms voor mobiele apparaten om ze te helpen bij het identificeren van mobiele apparaten in bedrijfseigendom
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1712bd39-562b-4409-9cec-155d5f4d8a39
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9038670a4c0b4bf52868ba739336dd35366eed2f
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/10/2017
---
# <a name="specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers"></a>Apparaten in bedrijfseigendom met een IMEI-nummer opgeven

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Voor het beheer van mobiele apparaten in bedrijfseigendom stelt Microsoft Intune beheerders in staat om IMEI-nummers (International Mobile Equipment Identity-nummers) te importeren voor mobiele apparaten die hierover beschikken. Nadat apparaten zijn ingeschreven bij Intune, kunt u zien welke apparaten IMEI-nummers hebben geïmporteerd onder **Groepen** > **Overzicht** > **Alle apparaten**. Onder **Apparaatgroep** staan apparaten met geïmporteerde IMEI-nummers, die worden weergegeven met **Bedrijf** in de kolom **Eigendom**.

1. Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) achtereenvolgens **Groepen** &gt; **Alle apparaten** &gt; **Alle vooraf geregistreerde bedrijfsapparaten** &gt; **Op IMEI (alle platformen)** en kies vervolgens **Apparaten toevoegen…**. U kunt apparaten op twee manieren toevoegen:

    -   **Een CSV-bestand met serienummers uploaden**: maak een lijst in twee kolommen met door komma's gescheiden waarden (CSV) zonder koptekst. Zorg ervoor dat het CSV-bestand niet meer dan 5000 apparaten bevat en niet groter is dan 5 MB. Het veld Details is beperkt tot 128 tekens. 

        |||
        |-|-|
        |&lt;IMEI 1&gt;|&lt;Details apparaat 1&gt;|
        |&lt;IMEI 2&gt;|&lt;Details apparaat 2&gt;|
        Dit CSV-bestand ziet er in een teksteditor als volgt uit:

        ```
        01234567890123,device details
        02234567890123,device details
        ```

    -   **Handmatig apparaatdetails toevoegen**: geef het IMEI-nummer en de apparaatdetails van maximaal 15 apparaten op.

   Het veld *Details* is bedoeld voor beheerders. U kunt details opgeven voor het identificeren van het apparaat in de lijst met apparaten in bedrijfseigendom, waarin apparaten worden weergegeven op hardware-id. Deze informatie wordt niet naar het apparaat verzonden, maar weergegeven in de Intune-console.

2.   Kies **Volgende**.
3.  In het deelvenster **Apparaten controleren** kunt u de geïmporteerde IMEI-nummers controleren. U kunt ook bepalen of de **Details** moeten worden overschreven voor IMEI-nummers die opnieuw worden geïmporteerd. Schakel het selectievakje **Overschrijven** uit als u de huidige details wilt behouden. Kies **Voltooien** om de IMEI-nummers te importeren.
4.  De geïmporteerde IMEI-nummers en beschrijvingen worden toegevoegd aan de lijst **Op IMEI (alle platformen)**.

> [!IMPORTANT]
> Als u IMEI-nummers importeert voor Android-apparaten, moet u er rekening mee houden dat sommige Android-apparaten meerdere IMEI-nummers kunnen hebben. Als u een IMEI-nummer importeert dat niet het IMEI-nummer is dat door het apparaat is gerapporteerd aan Intune, wordt het apparaat geclassificeerd als persoonlijk apparaat in plaats van een bedrijfsapparaat.

Wanneer het apparaat met een IMEI-nummer wordt ingeschreven bij Intune, wat meestal gebeurt wanneer een gebruiker de bedrijfsportal-app installeert en het inschrijvingsproces voltooit, wordt het apparaat gemarkeerd als eigendom van het bedrijf en weergegeven als geregistreerd in de groep **IMEI-apparaten**.

>[!NOTE]
> Als uw organisatie in de nabije toekomst wordt gemigreerd naar de nieuwe Azure-portal, verandert deze functie. In de bestaande Intune-beheerconsole kunnen beheerders bijbehorende gegevens accepteren uit een geüpload CSV-bestand en de bestaande gegevens voor afzonderlijke hardware-id's overschrijven. In de nieuwe Azure-portal kunt u de gegevens voor alle hardware-id's automatisch overschrijven of alle nieuwe gegevens voor bestaande id's negeren.

Zie [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729) voor gedetailleerde specificaties over International Mobile Equipment Identifiers.
