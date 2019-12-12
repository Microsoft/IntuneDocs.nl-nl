---
title: Een Intune-rapport maken van de OData-feed met Power BI
titleSuffix: Microsoft Intune
description: Maak een treemapvisualisatie met Power BI Desktop, met een interactief filter uit de Intune-datawarehouse-API.
keywords: Intune-datawarehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/03/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: A2C8A336-29D3-47DF-BB4A-62748339391D
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 18815fb671e853bc0463fed750d40b80ccb285fb
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "74784269"
---
# <a name="create-an-intune-report-from-the-odata-feed-with-power-bi"></a>Een Intune-rapport maken van de OData-feed met Power BI

In dit artikel wordt uitgelegd hoe u een Treemap-visualisatie van uw intune-gegevens maakt met behulp van Power BI Desktop die gebruikers een interactief filter hebben. Uw CFO kan bijvoorbeeld weten hoe de algehele distributie van apparaten vergelijkt tussen apparaten in bedrijfs eigendom en persoonlijke apparaten. Deze treemap biedt inzicht in het totaalaantal apparaattypen. U kunt het aantal iOS-, Android- en Windows-apparaten die al dan niet eigendom zijn van het bedrijf weergeven.

## <a name="overview-of-creating-the-chart"></a>Overzicht van het maken van de grafiek

Ga als volgt te werk voor het maken van deze grafiek:
1. Installeer Power BI Desktop als u dat nog niet hebt gedaan.
2. Maak verbinding met het gegevensmodel van het Intune-datawarehouse en haal de actuele gegevens voor het model op.
3. Maak of beheer de relaties in het gegevensmodel.
4. Maak de grafiek met de gegevens uit de tabel **apparaten**.
5. Maak een interactief filter.
6. Bekijk de voltooide grafiek.

### <a name="a-note-about-tables-and-entities"></a>Een opmerking over tabellen en entiteiten

In Power BI werkt u met tabellen. Een tabel bevat gegevensvelden. Elk gegevensveld heeft een gegevenstype. Het veld kan alleen gegevens van dat gegevenstype bevatten. Gegevenstypen zijn getallen, tekst, datums enzovoort. De tabellen in Power BI worden gevuld met recente historische gegevens van uw tenant wanneer u het model laadt. Hoewel de specifieke gegevens in de loop der tijd veranderen, verandert de tabelstructuur niet tenzij het onderliggende gegevensmodel wordt bijgewerkt.

Mogelijk zijn de termen *entiteit* en *tabel* enigszins verwarrend. Het gegevens model is toegankelijk via een OData-feed (Open Data Protocol). De containers die in Power BI tabellen worden genoemd, heten entiteiten in de context van OData. Beide termen verwijzen naar hetzelfde item dat uw gegevens bevat. Zie [odata-overzicht](/odata/overview)voor meer informatie over odata.

## <a name="install-power-bi-desktop"></a>Power BI Desktop installeren

Installeer de nieuwste versie van Power BI Desktop. U kunt Power BI Desktop downloaden van: [PowerBI.microsoft.com](https://powerbi.microsoft.com/desktop)

## <a name="connect-to-the-odata-feed-for-the-intune-data-warehouse-for-your-tenant"></a>Verbinding maken met de OData-feed voor het Intune-datawarehouse van uw tenant

> [!Note]  
> U hebt machtigingen nodig om **Rapporten** te maken in Intune. Zie [Autorisatie](../reports-api-url.md) voor meer informatie.

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Open het deelvenster **Intune Data Warehouse** door de link Data Warehouse onder **Andere taken** te selecteren aan de rechterkant van de blade **Microsoft Intune - Overzicht**.
3. Kopieer de aangepaste feed-URL. Bijvoorbeeld: `https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta`
4. Open Power BI Desktop.
5. Selecteer in de menu balk **File** > **gegevens ophalen** > **Odata-feed**.
6. Plak de aangepaste feed-URL, die u hebt gekopieerd uit de vorige stap, in het vak URL in het venster **OData-feed** .
7. Selecteer **Eenvoudig**.

    ![OData-feed voor het Intune-datawarehouse van uw tenant](./media/reports-proc-create-with-odata/reports-create-01-odatafeed.png)

8. Selecteer **OK**.
9. Selecteer **Organisatieaccount** en meld u aan met uw Intune-referenties.

    ![Referenties organisatieaccount](./media/reports-proc-create-with-odata/reports-create-02-org-account.png)

10. Selecteer **Verbinden**. De Navigator wordt geopenden er wordt een lijst met tabellen in het Intune-datawarehouse weergegeven.

    ![Schermopname van de Navigator: de lijst met datawarehousetabellen](./media/reports-proc-create-with-odata/reports-create-02-loadentities.png)

11. Selecteer de tabellen **Apparaten** en **OwnerTypes**.  Selecteer **Laden**. Power BI laadt gegevens in het model.

## <a name="create-a-relationship"></a>Relatie maken

U kunt meerdere tabellen importeren, zodat u niet alleen de gegevens in een enkele tabel kunt analyseren, maar ook gerelateerde gegevens in meerdere tabellen. Power BI heeft een functie met de naam **autodetectie** die voor u relaties zoekt en maakt. De tabellen in het datawarehouse zijn gebouwd om te werken met de autodetectiefunctie in Power BI. Maar ook als Power BI de relaties niet automatisch vindt, kunt u toch nog de relaties beheren.

![Relaties beheren van gerelateerde gegevens in verschillende tabellen](./media/reports-proc-create-with-odata/reports-create-03-managerelationships.png)

1. Selecteer **Relaties beheren**.
2. Selecteer **Autodetectie...** als Power BI de relaties nog niet heeft gedetecteerd.

De relatie wordt weergegeven met een kolom Van en een kolom Naar. In dit voorbeeld is het gegevensveld **OwnerTypeKey** in de tabel **apparaten** gekoppeld aan het gegevensveld **ownerTypeKey** in de tabel **ownerTypes**. U gebruikt de relatie om de gewone naam bij de typecode van het apparaat op te zoeken in de tabel **apparaten**.

## <a name="create-a-treemap-visualization"></a>Een treemapvisualisatie maken

In een treemapgrafiek worden hiërarchische gegevens weergegeven als vakken binnen vakken. Elke vertakking van de hiërarchie is een vak dat kleinere vakken bevat, die subvertakkingen weergeven. U kunt Power BI bureau blad gebruiken om een Treemap van uw intune-Tenant gegevens te maken waarin de relatieve aantallen van de fabrikant typen van het apparaat worden weer gegeven.

![Power BI-treemapvisualizaties](./media/reports-proc-create-with-odata/reports-create-03-treemap.png)

1. Zoek in het deel venster **visualisaties** naar en selecteer **Treemap**. Het **Treemap** -diagram wordt toegevoegd aan het rapport canvas.
2. Zoek in het deel venster **velden** de `devices` tabel.
3. Vouw de tabel `devices` uit en selecteer het veld `manufacturer` data.
4. Sleep het `manufacturer` gegevens veld naar het teken papier van het rapport en zet het neer in het **Treemap** -diagram.
5. Sleep het `deviceKey` gegevens veld van de tabel `devices` naar het deel venster **Visualisaties** en zet het neer onder de sectie **waarden** in het vak **Voeg gegevens velden toe**.  

U hebt nu een visueel element dat de verdeling van apparaten per fabrikant binnen uw organisatie weergeeft.

![Treemap met gegevens: de verdeling van apparaatfabrikanten](./media/reports-proc-create-with-odata/reports-create-06-treemapwdata.png)

## <a name="add-a-filter"></a>Een filter toevoegen

U kunt een filter aan uw treemap toevoegen om aanvullende vragen te beantwoorden met uw app.

1. Selecteer het rapportcanvas en selecteer vervolgens het **slicerpictogram** (![treemap met gegevensmodel en ondersteunde relaties](./media/reports-proc-create-with-odata/reports-create-slicer.png)) onder **Visualisaties** om een filter toe te voegen. De lege visualisatie van de **slicer** wordt weer gegeven op het canvas.
2. Zoek in het deel venster **velden** de `ownerTypes` tabel.
3. Vouw de tabel `ownerTypes` uit en selecteer het veld `ownerTypeName` data.
4. Sleep het `onwerTypeName` gegevens veld van de tabel `ownerTypes` naar het deel venster **filters** en zet het neer onder het gedeelte **filters op deze pagina** in het vak **Voeg gegevens velden toe**.  

   In de tabel `OwnerTypes` is er een gegevens veld met de naam `OwnerTypeKey`dat een gegevens bevat om te bepalen of een apparaat bedrijfs eigendom of persoonlijk is. Ga naar de tabel `ownerTypes` en sleep de **ownerTypeName** naar de slicer om de beschrijvende namen weer te geven. Dit voorbeeld toont aan hoe het gegevensmodel relaties tussen tabellen ondersteunt.

![Treemap met filter: ondersteunt relaties tussen tabellen](./media/reports-proc-create-with-odata/reports-create-08_ownertype.png)

U hebt nu een interactief filter dat u kunt gebruiken om te schakelen tussen apparaten in bedrijfseigendom en persoonlijke apparaten. Gebruik dit filter om te zien hoe de distributie verandert.

1. Selecteer **bedrijf** in de slicer om te zien dat de apparaat-eigendom van het bedrijf is gedistribueerd.
2. Selecteer **persoonlijk** in de slicer om de persoonlijke apparaten weer te geven.

## <a name="next-steps"></a>Volgende stappen

- Lees de Power BI-documentatie voor meer informatie over het [maken en beheren van relaties](https://powerbi.microsoft.com/documentation/powerbi-desktop-create-and-manage-relationships/) in Power BI Desktop.
- Raadpleeg het [Intune-datawarehousemodel](reports-ref-data-model.md).
