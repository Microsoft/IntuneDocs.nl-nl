---
title: Verbinding maken met het datawarehouse met Power BI
titleSuffix: Microsoft Intune
description: U kunt een bestand downloaden voor gebruik met Microsoft Power BI om interactieve, dynamisch gegenereerde rapporten te laden voor uw Microsoft Intune-tenant.
keywords: Intune-datawarehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/03/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 5E5A35D3-88F8-441B-8A0B-C5D7A1E5137B
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6d99410416da4c98bb01611051176b793c845237
ms.sourcegitcommit: 8d7406b75ef0d75cc2ed03b1a5e5f74ff10b98c0
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 01/03/2020
ms.locfileid: "75654104"
---
# <a name="connect-to-the-data-warehouse-with-power-bi"></a>Verbinding maken met het datawarehouse met Power BI

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

U kunt de Compliance-app van Power BI gebruiken om interactieve, dynamisch gegenereerde rapporten voor uw Intune-tenant te laden. Verder kunt u uw tenantgegevens in Power BI laden met behulp van de OData-koppeling. Intune biedt verbindingsinstellingen voor uw tenant zodat u voorbeeldrapporten en -grafieken met betrekking tot het volgende kunt weergeven:  

- Apparaten
- Inschrijving
- Beleid voor app-beveiliging
- Nalevingsbeleid
- Apparaatconfiguratieprofielen
- Software-updates
- Apparaatinventarisatielogboeken

Er worden ook trends gemarkeerd voor inschrijving, naleving, apparaatconfiguratieprofiel en software-updates. In de voorbeeldgrafieken en -rapporten worden gebruiksvriendelijke filters toegepast op het canvas. Als u geavanceerde filters wilt gebruiken, gaat u naar het deelvenster **Filter** in Power BI Desktop.

De volgende stappen laten zien hoe u het Power BI-bestand downloadt en hoe u de OData-koppeling gebruikt met Power BI.

[!INCLUDE [reports-credential-reqs](../includes/reports-credential-reqs.md)]

## <a name="install-power-bi"></a>Power BI installeren

Installeer de nieuwste versie van [Power BI Desktop](https://aka.ms/intune/datawarehouseapi/installpowerbi). Zie [Power BI Desktop](https://powerbi.microsoft.com/desktop) voor meer informatie

## <a name="load-the-data-and-reports-using-the-power-bi-intune-compliance-data-warehouse-app"></a>De gegevens en rapporten laden met behulp van de Intune Compliance Data Warehouse-app van Power BI

De [Intune Compliance Data Warehouse-app](https://aka.ms/intune/datawarehouseapi/getpowerbiapp) van Power BI bevat verbindingsgegevens voor uw tenant en een set vooraf gedefinieerde rapporten op basis van het datawarehouse-gegevensmodel.

1. Navigeer naar de pagina **AppSource** van de [Intune Compliance (Data Warehouse)-app](https://aka.ms/intune/datawarehouseapi/getpowerbiapp) om te beginnen met het installatieproces.
2. Klik op de knop **nu downloaden** en klik vervolgens op **door gaan**.
3. Klik op **installeren**wanneer u wordt gevraagd de Power bi-app te installeren.
4. Nadat de installatie is voltooid, klikt u op de tegel van de app **intune-compatibiliteit (Data Warehouse)** .
5. Klik op de knop **verbinding maken** . Het dialoogvenster **Verbinding maken met Intune Compliance (Data Warehouse)** wordt weergegeven.
6. Klik op de knop **Aanmelden**.
7. Meld u aan met een gebruikersaccount dat toegang heeft tot het Intune-datawarehouse voor de tenant die de rapporten bevat die u wilt weergeven.
8. Als u het dash board wilt weer geven, klikt u op het tabblad **Dash boards** en klikt u vervolgens op het dash board **overzicht van naleving** .
9. Als u alle beschik bare rapporten wilt weer geven, klikt u op het tabblad **rapporten** en klikt u vervolgens op het rapport **compliance v 1.0** . Blader door de rapport pagina's door te klikken op de tabbladen aan de onderkant.
10. U kunt later eenvoudig terugkeren naar deze rapporten als u op de ster naast het rapport **Naleving V1.0** klikt. Hiermee wordt het rapport toegevoegd aan uw Power BI-favorieten.

U kunt ook de app ook installeren vanuit de Intune-portal:

1. Meld u aan bij Azure Portal en kies **Bewaking en beheer** > **Intune**. U kunt ook zoeken naar resources voor Intune.
2. Open de blade **Intune-datawarehouse instellen**.
3. Selecteer **Power BI-app ophalen** voor toegang tot en het delen van vooraf gemaakte Power BI-rapporten voor uw tenant in de browser.
4. Volg de bovenstaande stappen 2-10.

## <a name="load-the-data-in-power-bi-using-the-odata-link"></a>Gegevens via OData-koppeling laden in Power BI

Nadat een client is geverifieerd bij Azure AD, wordt de OData-URL verbonden met het RESTful-eindpunt in de datawarehouse-API die het gegevensmodel weergeeft in de rapportageclient. Volg deze instructies om met behulp van Power BI Desktop een verbinding tot stand te brengen en uw eigen rapporten te maken. U bent niet beperkt tot Power BI Desktop, maar kunt uw favoriete analyseprogramma gebruiken met de OData-URL. Dit is echter alleen mogelijk als de client OAUTH2.0-verificatie en de OData-v4.0 standaard ondersteunt.

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Klik op **intune-Data Warehouse instellen** onder het gedeelte **andere taken** aan de rechter kant van de Blade overzicht. De Blade **intune-Data Warehouse** wordt weer gegeven.
3. Haal de aangepaste URL van de feed op via de rapportage-blade, bijvoorbeeld:<br>
    `https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=v1.0`
4. Open **Power BI Desktop**.
5. Kies **bestand** > **gegevens**op te halen. Selecteer **OData feed**.
6. Selecteer **Basic**.
7. Typ of plak de **OData-URL** in het vak URL.
8. Selecteer **OK**.
9. Als u de tenant niet vanuit de Power BI Desktop-client hebt geverifieerd bij Azure AD, typt u uw referenties. Om toegang tot uw gegevens te krijgen, moet u zich door middel van OAuth 2.0 autoriseren bij Azure Active Directory (Azure AD).  
    1. Selecteer **Organisatieaccount**.  
    2. Typ uw gebruikersnaam en wachtwoord.  
    3. Selecteer **Aanmelden.**  
    4. Selecteer **Verbinden**.  
10. Selecteer **Laden**.

## <a name="next-steps"></a>Volgende stappen

U kunt antwoord vinden op vragen over uw omgeving, zoals het aantal apparaten dat per dag is geregistreerd gedurende de afgelopen week. U kunt inzicht krijgen in uw Intune-tenant en de clientpopulatie met behulp van de Intune-datawarehouserapporten van Power BI die u ophaalt van de blade in Azure. Intune biedt echter verschillende andere manieren waarop u de gegevens kunt uitbreiden of hergebruiken. Power BI en de Intune-datawarehouse-API bieden aanvullende functionaliteit, bijvoorbeeld:

<!-- - You can use Power BI Desktop to create additional report types with your data. For example, you could create a custom chart representing the ratio of device manufactures in your enterprise. For more information about creating custom reports with Power BI and the Intune Data Warehouse, see `BLOG POST ON POWER BI`. -->
- De gegevens van uw tenant zijn zo georganiseerd dat u op verschillende manieren inzicht kunt krijgen in uw gegevens. Zie [Data Warehouse Data Model](reports-ref-data-model.md) (Datawarehouse-gegevensmodel) voor meer informatie over de ordening van de gegevens.
- U kunt de gegevens ook openen via een Restful-interface en de gegevens in uw eigen app opnemen. Zie [Gegevens ophalen uit de datawarehouse-API met een REST-client](../reports-proc-data-rest.md) voor meer informatie.
