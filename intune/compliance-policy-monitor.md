---
title: Nalevingsbeleid voor Intune-apparaten controleren
titlesuffix: Azure portal
description: Meer informatie over het controleren van het nalevingsbeleid voor apparaten.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 503d1dd2-a647-4aea-bf48-55319a3dd8a7
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4b293ff41af58d4ab41a8477219939b13ffe361c
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/09/2017
---
# <a name="monitor-intune-device-compliance-policies"></a>Nalevingsbeleid voor Intune-apparaten controleren

Nalevingsrapporten helpen beheerders het nalevingspostuur van apparaten in hun organisatie te analyseren en snel de door gebruikers binnen hun organisatie aangetroffen problemen met naleving op te lossen. U kunt informatie weergeven over de algemene nalevingsstatus van apparaten, de nalevingsstatus voor een specifieke instelling en de nalevingsstatus voor een specifiek beleid, en inzoomen op afzonderlijke apparaten om specifieke instellingen en beleidsregels die van invloed zijn op het apparaat weer te geven.

## <a name="before-you-begin"></a>Voordat u begint

Volg de onderstaande stappen om te zoeken naar de **Intune-dashboard voor apparaatnaleving** in Azure Portal:

1.  Ga naar [Azure Portal](https://portal.azure.com) en meld u aan met uw Intune-referenties.

2.  Kies **Meer services** in het linkermenu en typ dan **Intune** in het vak tekstfilter.

3.  Kies **Intune** &gt; **Apparaatnaleving** &gt; **Overzicht**. Het **Dashboard voor apparaatnaleving** wordt geopend.

> [!IMPORTANT] 
> Apparaten moeten worden ingeschreven bij Intune om het nalevingsbeleid voor apparaten te ontvangen.

## <a name="device-compliance-dashboard"></a>Dashboard voor apparaatnaleving

In het **Dashboard voor apparaatnaleving** kunt u de status van het nalevingsbeleid van apparaten controleren. Het dashboard biedt verschillende rapporten in verschillende tegels met het nalevingspostuur van apparaten in uw organisatie. U kunt de volgende rapporten bekijken:

-   Cumulatieve algehele apparaatnaleving

-   Apparaatnaleving per beleid

-   Apparaatnaleving per instelling

![Dashboard voor apparaatnaleving](./media/idc-1.png)

U kunt ook de specifieke nalevingsbeleidsregels en -instellingen bekijken die van toepassing zijn op een bepaald apparaat en de laatste nalevingsstatus voor elk van deze instellingen op het apparaat weergeven.

### <a name="overall-device-compliance-aggregate-report"></a>Rapport cumulatieve algehele apparaatnaleving

Dit is een ringdiagram met de cumulatieve nalevingsstatus voor alle bij Intune ingeschreven apparaten. De nalevingsstatussen van een apparaat worden opgeslagen in twee verschillende databases, te weten Intune en Azure Active Directory. Hieronder vindt u meer informatie over de statussen van het nalevingsbeleid van het apparaat:

-   **Compatibel**: op het apparaat is een of meer nalevingsbeleidsinstellingen voor apparaten toegepast waarop de beheerder zich richt.

-   **Niet-compatibel:** op het apparaat is een of meer nalevingsbeleidsinstellingen niet toegepast waarop de beheerder zich richt, of de gebruiker voldoet niet aan de beleidsregels waarop de beheerder zich richt.

-   **In respijtperiode:**de beheerder heeft of meer nalevingsbeleidsinstellingen voor apparaten gericht op het apparaat, maar de gebruiker heeft het beleid nog niet toegepast, wat betekent dat het apparaat niet compatibel is, maar zich in de respijtperiode bevindt die door de beheerder is vastgesteld.

    -   Meer informatie over Acties voor niet-compatibele apparaten.

-   **Het apparaat is niet gesynchroniseerd:** voor het apparaat is de nalevingsbeleidsstatus niet doorgegeven, om een van de volgende redenen:

    -   **Onbekend**: het apparaat is offline of kan om andere redenen niet communiceren met Intune of Azure AD.

    -   **Fout**: het apparaat kan niet communiceren met Intune en Azure AD en heeft een foutbericht met de reden ontvangen.

> [!IMPORTANT] 
> Apparaten die zijn geregistreerd bij Intune, maar waarop geen nalevingsbeleid voor apparaten is gericht, worden in dit rapport opgenomen onder de bucket **Compatibel**.

#### <a name="drill-down-option"></a>Inzoomoptie

Als u in het **Dashboard voor apparaatnaleving** klikt op de tegel Apparaatnaleving, kunt u inzoomen op een specifieke **nalevingsstatus**, **e-mailalias van de gebruiker**, **apparaatmodel** en **locatie ** voor elk apparaat waarop het nalevingsbeleid voor apparaten is gericht.

![Inzoomen in het dashboard voor apparaatnaleving](./media/idc-2.png)

Als u meer informatie over een specifieke gebruiker nodig hebt, kunt u filteren in het rapport Apparaatnalevingsgrafiek door de e-mailalias van de gebruiker in te voeren.

![Specifieke gebruiker in het dashboard voor apparaatnaleving](./media/idc-3.png)

U kunt ook op de afwijkende nalevingsstatus in de Apparaatnalevingsgrafiek klikken voor meer informatie over statussen van de gebruiker met betrekking tot het nalevingsbeleid.

![Verschillende statussen in het dashboard voor apparaatnaleving](./media/idc-4.png)

#### <a name="filter"></a>Filter

Als u op de **knop Filteren** klikt, wordt het uitvoegfilter geopend met de volgende opties:

-   Model

    -   Tekstvak waarin een vrije zoekreeks kan worden ingevoerd
<br></br>
-   Platform

    -   Android

    -   iOS

    -   Mac OS

    -   Windows

    -   Windows Phone

-   Status

    -   Compliant

    -   Niet compatibel

    -   In Respijtperiode

    -   Onbekend

    -   Fout

Als u op de **knop Bijwerken** klikt, wordt het uitvoegfilter gesloten en worden resultaten bijgewerkt aan de hand van de geselecteerde filtercriteria.

##### <a name="device-details"></a>Apparaatgegevens

Wanneer u op een apparaat klikt, wordt de **blade Apparaten** geopend met het geselecteerde apparaat. Deze blade biedt gedetailleerde informatie over de nalevingsbeleidsinstelling die op het apparaat is toegepast.

![Dashboard voor apparaatnaleving](./media/idc-6.png)

Wanneer u op het nalevingsbeleid voor apparaten zelf klikt, ziet u de naam van het nalevingsbeleid waaruit de nalevingsinstelling afkomstig waarop de beheerder zich richt.

![Naam van de instelling voor apparaatnaleving](./media/idc-7.png)

### <a name="per-policy-device-compliance-report"></a>Rapport apparaatnaleving per beleid

Dit rapport biedt een weergave per nalevingsbeleid en het totale aantal apparaten in elke nalevingsstatus. De tegel **Beleidsnaleving** is beschikbaar vanuit het **Dashboard voor apparaatnaleving**. Hierin worden alle beleidsregels die zijn gemaakt door de beheerder, de platforms waarop het beleid wordt toegepast, het aantal compatibele apparaten en het aantal niet-compatibele apparaten weergegeven.

![Rapport apparaatnaleving per beleid](./media/idc-8.png)

Als u op de tegel Beleidsnaleving klikt, en vervolgens klikt op een van de nalevingsbeleidsregels voor apparaten, ziet u de **nalevingsstatus**, het **e-mailalias van de gebruiker**, het **apparaatmodel** en de **locatie** voor elk apparaat waarop dat nalevingsbeleid voor apparaten is gericht.

![Tegel Beleidsnaleving](./media/idc-9.png)

### <a name="per-setting-device-compliance-report"></a>Rapport apparaatnaleving per instelling

Met dit rapport kunt u per nalevingsinstelling het totale aantal apparaten in elke nalevingsstatus bekijken. De tegel **Naleving van instelling** is beschikbaar vanuit het **Dashboard voor apparaatnaleving**. Hierin worden alle nalevingsbeleidsinstellingen voor apparaten van alle nalevingsbeleidsregels voor apparaten die door de beheerder zijn gemaakt, de platforms waarop de beleidsinstellingen zijn toegepast en het aantal niet-compatibele apparaten weergegeven.

![Rapport apparaatnaleving per instelling](./media/idc-10.png)

Als u op de tegel Naleving van instelling klikt, en vervolgens klikt op een van de nalevingsbeleidsinstellingen voor apparaten, ziet u de **nalevingsstatus**, het **e-mailalias van de gebruiker**, het **apparaatmodel** en de **locatie** voor elk apparaat waarop die nalevingsbeleidsinstelling voor apparaten is gericht.

![Tegel Naleving van instelling](./media/idc-11.png)
