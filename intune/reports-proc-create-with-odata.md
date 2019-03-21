---
title: Een rapport maken van de OData-feed met Power BI
titlesuffix: Microsoft Intune
description: Maak een treemapvisualisatie met Power BI Desktop, met een interactief filter uit de Intune-datawarehouse-API.
keywords: Intune-datawarehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/06/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: A2C8A336-29D3-47DF-BB4A-62748339391D
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3cd0f8b5337ad562bddd65bc449a35ec0773f5ed
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57565618"
---
# <a name="create-a-report-from-the-odata-feed-with-power-bi"></a>Een rapport maken van de OData-feed met Power BI

In dit artikel leest u hoe u een treemapvisualisatie maakt in Power BI Desktop met een interactief filter. Uw CFO wil bijvoorbeeld weten hoe de algehele verdeling van apparaten is in vergelijking met de verhouding bedrijfseigen-persoonlijke apparatuur. Deze treemap biedt inzicht in het totaalaantal apparaattypen. U kunt het aantal iOS-, Android- en Windows-apparaten die al dan niet eigendom zijn van het bedrijf weergeven.

### <a name="overview-of-creating-the-chart"></a>Overzicht van het maken van de grafiek

Ga als volgt te werk voor het maken van deze grafiek:
1. Installeer Power BI Desktop als u dat nog niet hebt gedaan.
2. Maak verbinding met het gegevensmodel van het Intune-datawarehouse en haal de actuele gegevens voor het model op.
3. Maak of beheer de relaties in het gegevensmodel.
4. Maak de grafiek met de gegevens uit de tabel **apparaten**.
5. Maak een interactief filter.
6. Bekijk de voltooide grafiek.

### <a name="a-note-about-tables-and-entities"></a>Een opmerking over tabellen en entiteiten

In Power BI werkt u met tabellen. Een tabel bevat gegevensvelden. Elk gegevensveld heeft een gegevenstype. Het veld kan alleen gegevens van dat gegevenstype bevatten. Gegevenstypen zijn getallen, tekst, datums enzovoort. De tabellen in Power BI worden gevuld met recente historische gegevens van uw tenant wanneer u het model laadt. Hoewel de specifieke gegevens in de loop der tijd veranderen, verandert de tabelstructuur niet tenzij het onderliggende gegevensmodel wordt bijgewerkt.

Mogelijk zijn de termen _entiteit_ en _tabel_ enigszins verwarrend. Het gegevensmodel is toegankelijk via een OData-feed. De containers die in Power BI tabellen worden genoemd, heten entiteiten in de context van OData. Beide termen verwijzen naar hetzelfde item dat uw gegevens bevat.

## <a name="install-power-bi-desktop"></a>Power BI Desktop installeren

Installeer de nieuwste versie van Power BI Desktop. U kunt Power BI Desktop downloaden van: [PowerBI.microsoft.com](https://powerbi.microsoft.com/desktop)

## <a name="connect-to-the-odata-feed-for-the-intune-data-warehouse-for-your-tenant"></a>Verbinding maken met de OData-feed voor het Intune-datawarehouse van uw tenant

> [!Note]  
> U hebt machtigingen nodig om **Rapporten** te maken in Intune. Zie [Autorisatie](reports-api-url.md) voor meer informatie.

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Open het deelvenster **Intune-datawarehouse**.
4. Kopieer de aangepaste feed-URL. Bijvoorbeeld: `https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta`
5. Open Power BI Desktop.
6. Kies **Gegevens ophalen** > **OData-feed**.
7. Plak de aangepaste feed-URL in het vak voor de URL in het venster **OData-feed**.
8. Selecteer **Eenvoudig**.

    ![OData-feed voor het Intune-datawarehouse van uw tenant](media/reports-create-01-odatafeed.png)

9. Selecteer **OK**.
10. Selecteer **Organisatieaccount** en meld u aan met uw Intune-referenties.

    ![Referenties organisatieaccount](media/reports-create-02-org-account.png)

11. Selecteer **Verbinden**. De Navigator wordt geopenden er wordt een lijst met tabellen in het Intune-datawarehouse weergegeven.

    ![Schermopname van de Navigator: de lijst met datawarehousetabellen](media/reports-create-02-loadentities.png)

12. Selecteer de tabellen **Apparaten** en **OwnerTypes**.  Selecteer **Laden**. Power BI laadt gegevens in het model.

## <a name="create-a-relationship"></a>Relatie maken

U kunt meerdere tabellen importeren, zodat u niet alleen de gegevens in een enkele tabel kunt analyseren, maar ook gerelateerde gegevens in meerdere tabellen.  Power BI heeft een functie genaamd **autodetectie** die relaties zoekt en maakt. De tabellen in het datawarehouse zijn gebouwd om te werken met de autodetectiefunctie in Power BI. Maar ook als Power BI de relaties niet automatisch vindt, beheert u de relaties toch.

![Relaties beheren van gerelateerde gegevens in verschillende tabellen](media/reports-create-03-managerelationships.png)

1. Selecteer **Relaties beheren**.
2. Selecteer **Autodetectie...** als Power BI de relaties nog niet heeft gedetecteerd.

De relatie wordt weergegeven met een kolom Van en een kolom Naar. In dit voorbeeld is het gegevensveld **OwnerTypeKey** in de tabel **apparaten** gekoppeld aan het gegevensveld **ownerTypeKey** in de tabel **ownerTypes**. U gebruikt de relatie om de gewone naam bij de typecode van het apparaat op te zoeken in de tabel **apparaten**.

## <a name="create-a-treemap-visualization"></a>Een treemapvisualisatie maken

In een treemapgrafiek worden hiërarchische gegevens weergegeven als vakken binnen vakken. Elke vertakking van de hiërarchie is een vak dat kleinere vakken bevat, die subvertakkingen weergeven. U kunt Power BI Desktop gebruiken om een treemap van uw Intune-gegevens te maken.

![Power BI-treemapvisualizaties](media/reports-create-03-treemap.png)

1. Selecteer een grafiektype. Selecteer **Treemap**.
2. Ga naar de tabel **apparaten** in het gegevensmodel.
3. Vouw de tabel **apparaten** uit en selecteer het gegevensveld **fabrikant** in het deelvenster **Velden**.
4. Sleep het gegevensveld **fabrikant** naar de treemapgrafiek op het rapportcanvas.
5. Sleep het gegevensveld **deviceKey** van de tabel **apparaten** naar de sectie **Waarden** onder het deelvenster **Visualisaties** en plaats het op het vak met de tekst **Gegevensveld hier neerzetten**.  

U hebt nu een visueel element dat de verdeling van apparaten per fabrikant binnen uw organisatie weergeeft.

![Treemap met gegevens: de verdeling van apparaatfabrikanten](media/reports-create-06-treemapwdata.png)

## <a name="add-a-filter"></a>Een filter toevoegen

U kunt een filter aan uw treemap toevoegen om aanvullende vragen te beantwoorden met uw app.


1. Selecteer het rapportcanvas en selecteer vervolgens het **slicerpictogram** (![treemap met gegevensmodel en ondersteunde relaties](media/reports-create-slicer.png)) onder **Visualisaties** om een filter toe te voegen.
2. Ga naar de tabel **ownerTypes** en sleep het gegevensveld **ownertypeName** naar de sectie **Filters** in het deelvenster **Visualisaties**.  

   Onder de tabel apparaten staat een gegevensveld genaamd **OwnerTypeKey**, dat ene code bevat die aangeeft of het apparaat persoonlijk is of eigendom van het bedrijf. Om de beschrijvende namen in dit filter weer te geven, gaat u naar de tabel **ownerTypes** en sleept u de **ownerTypeName**. Dit voorbeeld toont aan hoe het gegevensmodel relaties tussen tabellen ondersteunt.

![Treemap met filter: ondersteunt relaties tussen tabellen](media/reports-create-08_ownertype.png)

U hebt nu een interactief filter dat u kunt gebruiken om te schakelen tussen apparaten in bedrijfseigendom en persoonlijke apparaten. Gebruik dit filter om te zien hoe de distributie verandert.

1. Selecteer **Bedrijf** om de apparaten in bedrijfseigendom weer te geven.
2. Selecteer **Persoonlijk** om de persoonlijke apparaten weer te geven.

## <a name="next-steps"></a>Volgende stappen

 - Lees de Power BI-documentatie voor meer informatie over het [maken en beheren van relaties](https://powerbi.microsoft.com/documentation/powerbi-desktop-create-and-manage-relationships/) in Power BI Desktop.
 - Raadpleeg het [Intune-datawarehousemodel](https://docs.microsoft.com/intune/reports-ref-data-model).
