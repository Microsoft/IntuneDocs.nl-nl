---
title: Uw Intune Data Warehouse-accountgegevens verplaatsen
titlesuffix: Microsoft Intune
description: Begrijpen hoe u een back-up maakt van uw Intune Data Warehouse-gegevens bij het verplaatsen van uw account.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/19/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ee3ccbf9-82fc-4fbf-9d3d-8f05e431d090
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: da1dbf963b0dd564235a59e8b6c0e970d8cd86da
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57235528"
---
# <a name="move-your-intune-data-warehouse-account-data"></a>Uw Intune Data Warehouse-accountgegevens verplaatsen 

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Door het aanvragen van de verplaatsing van een account, hebt u aangevraagd dat uw datacenter wordt gewijzigd naar een andere locatie. Na het verplaatsen wordt uw Data Warehouse opnieuw ingesteld en begint deze het met het opnemen van gegevens op de nieuwe locatie op basis van de opgegeven dag dat uw verplaatsing begint. Voltooi de volgende stappen om de back-up van uw eerdere Data Warehouse-gegevens te maken, **voordat** u uw account verplaatst. De meeste Data Warehouse-tabellen houden gegevens 30 dagen vast, dus elk gat in de gegevens in deze tabellen is 30 dagen na het verplaatsen van uw account niet langer beschikbaar. Zie voor meer informatie over bewaarperiodes voor specifieke tabellen het [Data Warehouse-gegevensmodel](reports-ref-data-model.md). 

## <a name="back-up-your-data-warehouse-data"></a>Back-ups maken van de Data Warehouse-databases 

Als u een back-up van uw Data Warehouse-gegevens wilt maken, moet u uw Data Warehouse-gegevens opslaan in een *CSV*-bestand met behulp van de API van Data Warehouse:  

1. Als u voor de eerste keer de API van Data Warehouse gebruikt, volgt u het eenmalige proces dat is opgegeven in het volgende artikel, [Gegevens ophalen uit de API van Intune Data Warehouse met een REST-client](reports-proc-data-rest.md).
2. Gebruik het PowerShell-voorbeeld met de titel [Access the Intune Data Warehouse with PowerShell](https://github.com/Microsoft/Intune-Data-Warehouse/tree/master/Samples/PowerShell) (Toegang tot het datawarehouse van Intune met PowerShell) om al uw gegevens te downloaden naar CSV-bestanden. 

## <a name="back-up-your-trend-charts-from-the-azure-portal"></a>Maak een back-up van uw trendgrafieken uit Azure Portal

Sommige trendgrafieken in de weergave van Azure Portal worden opnieuw ingesteld. U kunt een back-up van deze grafieken maken door het volgende script uit te voeren in **Graph**:   

### <a name="terms--conditions-acceptance-reports"></a>Algemene Voorwaarden acceptatierapporten
1. Navigeer in Azure Portal naar **Microsoft Intune** -> **Apparaatinschrijving** -> **Algemene Voorwaarden**.
2. Selecteer voor elk item in de**Algemene Voorwaarden** **Acceptatierapport** gevolgd door **Exporteren**.
3. Sla het rapport lokaal op.
 
### <a name="app-protection-reports"></a>Rapportage van de app-beveiliging  
1. Navigeer in Azure Portal naar **Microsoft Intune** -> **Client-apps** -> **App-beveiligingsstatus**.
2. Klik op het downloadpictogram (⤓) om elk rapport op te slaan.

### <a name="device-configuration-charts"></a>Apparaatconfiguratie-grafieken 
1. Navigeer in Azure Portal naar **Microsoft Intune** -> **Apparaatconfiguratie**.
2. Download met Microsoft [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer) de gegevens achter de grafieken. 
    - Zie voor de implementatiestatus van alle apparaat-configuratieprofielen voor alle apparaten [Apparaat-implementatiestatus](https://graph.microsoft.com/beta/reports/deviceConfigurationDeviceActivity/content).

    - Zie voor de implementatiestatus van alle apparaat-configuratieprofielen voor alle gebruikers [Gebruiker-implementatiestatus](https://graph.microsoft.com/beta/reports/deviceConfigurationUserActivity/content).

    - Zie voor een profiel-implementatiestatus [Implementatiestatus opgeven](https://graph.microsoft.com/beta/deviceManagement/deviceConfigurations?$select=id,displayName,lastModifiedDateTime,deviceStatusOverview&$expand=deviceStatusOverview).
  
    > [!NOTE]
    > U moet een geldig authentificatie-token hebben voor toegang tot de apparaatconfiguratie en informatie over de status van de implementatie.

## <a name="device-enrollment-charts"></a>Device Enrollment-grafieken
1. Navigeer in Azure Portal naar **Microsoft Intune** -> **DeviceEnrollment**.
2. Download met Microsoft [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer) de gegevens achter de grafieken.
    - Kopieer voor de inschrijvingsstatus deze [inschrijvingsstatus-query](https://graph.microsoft.com/beta/reports/managedDeviceEnrollmentFailureTrends()/content) en plak deze in [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).
    - Kopieer voor de top mislukte inschrijvingen deze [mislukte inschrijvingen-query](https://graph.microsoft.com/beta/reports/managedDeviceEnrollmentTopFailures(period=null)/content) en plak deze in [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).

    > [!NOTE]
    > U moet een geldig authentificatie-token hebben voor toegang tot de inschrijvingsgegevens van het apparaat. 

## <a name="after-a-data-warehouse-account-move"></a>Na de verplaatsing van een Data Warehouse-account

Nadat u het Data Warehouse-account hebt verplaatst, ziet u in Intune dat het datawarehouse opnieuw is ingesteld en uw gegevens nu worden opgeslagen op de nieuwe locatie. De grafieken en exportopties worden opnieuw ingesteld en u ziet een melding. Wanneer u hier op klikt wordt u doorgeleid naar een artikel waarin wordt uitgelegd waarom de grafieken opnieuw zijn ingesteld.  

## <a name="data-warehouse-move-example"></a>Voorbeeld van datawarehouse verplaatsen 

Klant X vraagt een verplaatsing van het account aan, te beginnen op 06/1/2018. De klant ontvangt als antwoord op de aanvraag een link om gedetailleerde informatie te zien over de benodigde stappen voor het maken van een back-up van hun vorige datawarehouse. Op 06/1/2018 worden het datawarehouse en de grafieken die het ondersteunt opnieuw ingesteld en worden gegevens opgeslagen in het nieuwe datacentrum. 

## <a name="next-steps"></a>Volgende stappen

 - Ontdek [wat er elke week nieuw is in Intune](whats-new.md). U vindt hier ook informatie over toekomstige wijzigingen, belangrijke kennisgevingen betreffende de service en informatie over oudere releases.
 - Lees het [Microsoft Intune-blog](https://go.microsoft.com/fwlink/?LinkID=273882).
