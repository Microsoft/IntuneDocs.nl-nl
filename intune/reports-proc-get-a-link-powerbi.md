---
title: Verbinding maken met het datawarehouse met Power BI | Microsoft Docs
description: U kunt een bestand downloaden voor gebruik met Microsoft Power BI om interactieve, dynamisch gegenereerde rapporten te laden voor uw Intune-tenant.
keywords: Intune-datawarehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5E5A35D3-88F8-441B-8A0B-C5D7A1E5137B
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0b3436a22543eb07cedb0780984766bcb7faa284
ms.sourcegitcommit: 0ee9909fc041c2e49c0e0312ae05f40bbeb2ee51
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/14/2017
---
# <a name="connect-to-the-data-warehouse-with-power-bi"></a>Verbinding maken met het datawarehouse met Power BI

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

U kunt een bestand downloaden voor gebruik met Microsoft Power BI om interactieve, dynamisch gegenereerde rapporten te laden voor uw Intune-tenant. Het Power BI-bestand voor het datawarehouse (pbix) bevat verbindingsinstellingen voor uw tenant, plus de volgende voorbeelden van rapporten en grafieken:  

  -  Apparaten
  -  Inschrijving
  -  Beleid voor app-beveiliging
  -  Nalevingsbeleid
  -  Apparaatconfiguratieprofielen
  -  Software-updates
  -  Apparaatinventarisatielogboeken

Er worden ook trends gemarkeerd voor inschrijving, naleving, apparaatconfiguratieprofiel en software-updates. In de voorbeeldgrafieken en -rapporten worden gebruiksvriendelijke filters toegepast op het canvas. Als u geavanceerde filters wilt gebruiken, gaat u naar het deelvenster **Filter** in Power BI Desktop.

De volgende stappen laten zien hoe u het Power BI-bestand downloadt en hoe u de OData-koppeling gebruikt met Power BI.

## <a name="install-power-bi"></a>Power BI installeren

Installeer de nieuwste versie van Power BI Desktop. U kunt Power BI Desktop downloaden van: [PowerBI.microsoft.com](https://powerbi.microsoft.com/en-us/desktop)

## <a name="load-the-data-and-reports-using-the-power-bi-file-pbix"></a>Gegevens en rapporten laden via Power BI-bestand (pbix)

Het Power BI-bestand (pbix) bevat verbindingsgegevens voor uw tenant en een set vooraf gedefinieerde rapporten op basis van het datawarehouse-gegevensmodel. Open het bestand in Power BI Desktop en meld u aan bij Azure AD. De gegevens uit uw Intune-tenant worden in het rapport geladen.

> [!Important]  
> Elk Power BI-bestand (pbix) is mogelijk anders afhankelijk van de locatie van de tenant. Als u meerdere Intune-tenants beheert, moet u ervoor zorgen dat u het bestand gebruikt dat u hebt gedownload van Azure Portal terwijl was aangemeld bij de betreffende tenant.  

1.  Meld u aan bij Azure Portal en kies **Bewaking en beheer** > **Intune**. U kunt ook zoeken naar resources voor **Intune**.  
2.  Open de blade **Microsoft Intune-datawarehouse-API (preview-versie)**.
3.  Klik op **Power BI-bestand downloaden**. Het bestand met de extensie pbix wordt gedownload naar de locatie die u hebt opgegeven.
4.  Open het bestand met Power BI. De *Intune-datawarehouserapporten* worden geladen, maar het kan even duren omdat de gegevens van uw tenant moeten worden opgehaald.
5.  Klik op **Vernieuwen** om de gegevens van uw tenant te laden en de rapporten te bekijken.
6.  Als Power BI niet is geverifieerd met uw Azure Active Directory-referenties, wordt u door Power BI gevraagd om uw referenties. Kies bij het selecteren van uw referenties **Werkaccount** als de verificatiemethode.

## <a name="load-the-data-in-power-bi-using-the-odata-link"></a>Gegevens via OData-koppeling laden in Power BI

Nadat een client is geverifieerd bij Azure AD, wordt de OData-URL verbonden met het RESTful-eindpunt in de datawarehouse-API die het gegevensmodel weergeeft in de rapportageclient. Volg deze instructies om met behulp van Power BI Desktop een verbinding tot stand te brengen en uw eigen rapporten te maken. U bent niet beperkt tot Power BI Desktop, maar kunt uw favoriete analyseprogramma gebruiken met de OData-URL. Dit is echter alleen mogelijk als de client OAUTH2.0-verificatie en de OData-v4.0 standaard ondersteunt.

1.  Meld u aan bij Azure Portal en kies **Bewaking en beheer** > **Intune**. U kunt ook zoeken naar resources voor **Intune**.  
2.  Open de blade **Microsoft Intune-datawarehouse-API (preview-versie)**.
3. Haal via de rapportage-blade de aangepaste URL van de feed op, bijvoorbeeld `https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`
4. Open **Power BI Desktop**.
5. Kies **Home** > **Get Data**. Selecteer **OData feed**.
6. Selecteer **Basic**.
7. Typ of plak de **OData-URL** in het vak URL.
8. Klik op **OK**.
9. Als u de tenant niet vanuit de Power BI Desktop-client hebt geverifieerd bij Azure AD, typt u uw referenties.  
    1.  Selecteer **Werkaccount**.  
    2.  Typ uw gebruikersnaam en wachtwoord.  
    3.  Klik op **Sign In.**  
    4.  Klik op **Verbinden**.  
10. Klik op **Load**.

## <a name="next-steps"></a>Volgende stappen

U kunt antwoord vinden op vragen over uw omgeving, zoals het aantal apparaten dat per dag is geregistreerd gedurende de afgelopen week. U kunt inzicht krijgen in uw Intune-tenant en de clientpopulatie aan de hand van rapporten die u genereert met behulp van het Power BI-bestand (pbix) voor het Intune-datawarehouse dat u ophaalt van de blade in Azure. Intune biedt echter verschillende andere manieren waarop u de gegevens kunt uitbreiden of hergebruiken. U kunt nog allerlei andere dingen doen met Power BI en de Intune-datawarehouse-API, zoals:

<!-- -  You can use Power BI Desktop to create additional report types with your data. For example, you could create a custom chart representing the ratio of device manufactures in your enterprise. For more information about creating custom reports with Power BI and the Intune Data Warehouse, see `BLOG POST ON POWER BI`. -->
 -  De gegevens van uw tenant zijn zo georganiseerd dat u op verschillende manieren inzicht kunt krijgen in uw gegevens. Zie [Data Warehouse Data Model](reports-ref-data-model.md) (Datawarehouse-gegevensmodel) voor meer informatie over de ordening van de gegevens.
 -  U kunt de gegevens ook openen via een Restful-interface en de gegevens in uw eigen app opnemen. Zie [Gegevens ophalen uit de datawarehouse-API met een REST-client](reports-proc-data-rest.md) voor meer informatie.
