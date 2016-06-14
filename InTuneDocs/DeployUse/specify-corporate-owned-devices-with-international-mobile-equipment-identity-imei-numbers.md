---
# required metadata

title: Apparaten in bedrijfseigendom met IMEI (International Mobile Equipment Identity) opgeven | Microsoft Intune
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

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Apparaten in bedrijfseigendom met IMEI (International Mobile Equipment Identity) opgeven
Voor het beheer van mobiele apparaten in bedrijfseigendom stelt Microsoft Intune beheerders in staat om IMEI-nummers (International Mobile Equipment Identity-nummers) te importeren voor mobiele apparaten die hierover beschikken. Wanneer apparaten met geïmporteerde IMEI-nummers zijn ingeschreven in Intune, worden deze gelabeld als bedrijfseigendom, zodat op die apparaten andere beleidsregels kunnen worden toegepast dan op persoonlijke apparaten.

1. Ga in de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) naar **Groepen** &gt; **Alle apparaten** &gt; **Vooraf ingeschreven bedrijfsapparaten** &gt; **Op IMEI (alle platforms)** en klik op **Apparaten toevoegen...**. U kunt apparaten op twee manieren toevoegen:

    -   **Een csv-bestand met serienummers uploaden**: maak een lijst met door komma's gescheiden waarden (csv) van twee kolommen zonder koptekst voor maximaal 5000 apparaten of 5 MB per CSV-bestand.

        |||
        |-|-|
        |&lt;IMEI 1&gt;|&lt;Details apparaat 1&gt;|
        |&lt;IMEI 2&gt;|&lt;Details apparaat 2&gt;|
        Dit csv-bestand ziet er in een teksteditor als volgt uit:

        ```
        AA-BBBBBB-CCCCCC-D,PO 1234
        AA-BBBBBB-CCCCCC-E,PO 1234
        ```

    -   **Handmatig apparaatdetails toevoegen**: geef het IMEI-nummer en de apparaatdetails van maximaal vijf apparaten op.

   *Details* zijn voor administratief gebruik, zodat u weet welk IMEI-nummer is gekoppeld aan een apparaat. Deze informatie wordt niet naar het apparaat verzonden, maar weergegeven in de Intune-console.

2.   Klik op **Volgende**.
3.  In het deelvenster **Apparaten controleren** kunt u controleren welke IMEI-nummers van apparaten er worden geïmporteerd. U kunt ook bepalen of de **Details** moeten worden overschreven voor IMEI-nummers die opnieuw worden geïmporteerd. Schakel het selectievakje **Overschrijven** uit als u de huidige details wilt behouden. Klik op **Voltooien** om de IMEI-nummers te importeren.
4.  De toegevoegde IMEI-nummers en beschrijvingen worden toegevoegd aan de lijst **Op IMEI (alle platforms)**.

Wanneer het apparaat met het betreffende IMEI-nummer wordt ingeschreven, gewoonlijk wanneer een gebruiker de bedrijfsportal-app installeert en het inschrijvingsproces voltooit, wordt het apparaat gemarkeerd als eigendom van het bedrijf en weergegeven als ingeschreven in de groep **IMEI-apparaten**.


<!--HONumber=May16_HO1-->


