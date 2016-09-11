---
title: IMEI-nummers opgeven | Microsoft Intune
description: Met Microsoft Intune kunnen beheerders IMEI-nummers importeren voor platforms voor mobiele apparaten om ze te helpen bij het identificeren van mobiele apparaten in bedrijfseigendom
keywords: 
author: NathBarn
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
ms.sourcegitcommit: e9cbf5858cc4e860b540f421b6d463b8e7a429cf
ms.openlocfilehash: 4e2092182dbda4523c19afeabc34aa0166962c40


---

# Apparaten in bedrijfseigendom met een IMEI-nummer opgeven
Voor het beheer van mobiele apparaten in bedrijfseigendom stelt Microsoft Intune beheerders in staat om IMEI-nummers (International Mobile Equipment Identity-nummers) te importeren voor mobiele apparaten die hierover beschikken. Zodra apparaten met geïmporteerde IMEI-nummers zijn geregistreerd bij Intune, kunnen ze worden bekeken onder **Groepen** > **Overzicht** > **Alle apparaten**. **Apparaatgroep**-lijsten bevatten apparaten met geïmporteerde IMEI-nummers en worden als **Bedrijf** in de kolom **Eigendom** weergegeven.

1. Kies in de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) achtereenvolgens **Groepen** &gt; **Alle apparaten** &gt; **Alle vooraf geregistreerde bedrijfsapparaten** &gt; **Op IMEI (alle platformen)** en kies vervolgens **Apparaten toevoegen…**. U kunt apparaten op twee manieren toevoegen:

    -   **Een csv-bestand met serienummers uploaden**: maak een lijst met door komma's gescheiden waarden (csv) van twee kolommen zonder koptekst voor maximaal 5000 apparaten of 5 MB per CSV-bestand.

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
3.  In het deelvenster **Apparaten controleren** kunt u controleren welke IMEI-nummers van apparaten er worden geïmporteerd. U kunt ook bepalen of de **Details** moeten worden overschreven voor IMEI-nummers die opnieuw worden geïmporteerd. Schakel het selectievakje **Overschrijven** uit als u de huidige details wilt behouden. Kies **Voltooien** om de IMEI-nummers te importeren.
4.  De toegevoegde IMEI-nummers en beschrijvingen worden toegevoegd aan de lijst **Op IMEI (alle platformen)**.

Wanneer het apparaat met het betreffende IMEI-nummer wordt geregistreerd, gewoonlijk wanneer een gebruiker de bedrijfsportal-app installeert en het registratieproces voltooit, wordt het apparaat gemarkeerd als eigendom van het bedrijf en weergegeven als geregistreerd in de groep **IMEI-apparaten**.



<!--HONumber=Jul16_HO4-->


