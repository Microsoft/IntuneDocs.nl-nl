---
title: Apparaten in bedrijfseigendom met een IMEI-nummer opgeven | Microsoft Intune
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1712bd39-562b-4409-9cec-155d5f4d8a39
ms.reviewer: jeffgilb
ms.suite: ems
ms.sourcegitcommit: 398d93d4e2317d00a2f9d5f89966aaec3b942504
ms.openlocfilehash: af4b87eb8082ee5ff11cd2d42b788ad17b334bcb


---

# Apparaten in bedrijfseigendom met een IMEI-nummer opgeven
Voor het beheer van mobiele apparaten in bedrijfseigendom stelt Microsoft Intune beheerders in staat om IMEI-nummers (International Mobile Equipment Identity-nummers) te importeren voor mobiele apparaten die hierover beschikken. Zodra apparaten met geïmporteerde IMEI-nummers zijn geregistreerd bij Intune, kunnen ze worden weergegeven onder **Groepen** > **Overzicht** > **Alle apparaten** > **Vooraf geregistreerde bedrijfsapparaten** > **Op IMEI (alle platformen)**.

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



<!--HONumber=Jun16_HO3-->


