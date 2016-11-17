---
title: IMEI-nummers opgeven | Microsoft Intune
description: Met Microsoft Intune kunnen beheerders IMEI-nummers importeren voor platforms voor mobiele apparaten om ze te helpen bij het identificeren van mobiele apparaten in bedrijfseigendom
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1712bd39-562b-4409-9cec-155d5f4d8a39
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 289e6019aa1a17deb91b38ed32f0432af0902a9d
ms.openlocfilehash: 14ba34d46df4b4ff9de4427800b146e383f8a3d2


---

# <a name="specify-corporateowned-devices-with-international-mobile-equipment-identity-imei-numbers"></a>Apparaten in bedrijfseigendom met een IMEI-nummer opgeven
Voor het beheer van mobiele apparaten in bedrijfseigendom stelt Microsoft Intune beheerders in staat om IMEI-nummers (International Mobile Equipment Identity-nummers) te importeren voor mobiele apparaten die hierover beschikken. Nadat apparaten zijn ingeschreven bij Intune, kunt u zien welke apparaten IMEI-nummers hebben geïmporteerd onder **Groepen** > **Overzicht** > **Alle apparaten**. Onder **Apparaatgroep** staan apparaten met geïmporteerde IMEI-nummers, die worden weergegeven met **Bedrijf** in de kolom **Eigendom**.

1. Kies in de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) achtereenvolgens **Groepen** &gt; **Alle apparaten** &gt; **Alle vooraf geregistreerde bedrijfsapparaten** &gt; **Op IMEI (alle platformen)** en kies vervolgens **Apparaten toevoegen…**. U kunt apparaten op twee manieren toevoegen:

    -   **Een CSV-bestand met serienummers uploaden**: maak een lijst in twee kolommen met door komma's gescheiden waarden (CSV) zonder koptekst. Zorg ervoor dat het CSV-bestand niet meer dan 5000 apparaten bevat en niet groter is dan 5 MB.

        |||
        |-|-|
        |&lt;IMEI 1&gt;|&lt;Details apparaat 1&gt;|
        |&lt;IMEI 2&gt;|&lt;Details apparaat 2&gt;|
        Dit CSV-bestand ziet er in een teksteditor als volgt uit:

        ```
        AABBBBBBCCCCCCD,PO 1234
        AABBBBBBCCCCCCE,PO 1234
        ```

    -   **Handmatig apparaatdetails toevoegen**: geef het IMEI-nummer en de apparaatdetails van maximaal vijf apparaten op.

   *Details* zijn voor administratief gebruik, zodat u weet welk IMEI-nummer is gekoppeld aan een apparaat. Deze informatie wordt niet naar het apparaat verzonden, maar weergegeven in de Intune-console.

2.   Kies **Volgende**.
3.  In het deelvenster **Apparaten controleren** kunt u de geïmporteerde IMEI-nummers controleren. U kunt ook bepalen of de **Details** moeten worden overschreven voor IMEI-nummers die opnieuw worden geïmporteerd. Schakel het selectievakje **Overschrijven** uit als u de huidige details wilt behouden. Kies **Voltooien** om de IMEI-nummers te importeren.
4.  De geïmporteerde IMEI-nummers en beschrijvingen worden toegevoegd aan de lijst **Op IMEI (alle platformen)**.

Wanneer het apparaat met een IMEI-nummer wordt ingeschreven bij Intune, wat meestal gebeurt wanneer een gebruiker de bedrijfsportal-app installeert en het inschrijvingsproces voltooit, wordt het apparaat gemarkeerd als eigendom van het bedrijf en weergegeven als geregistreerd in de groep **IMEI-apparaten**.



<!--HONumber=Nov16_HO1-->


