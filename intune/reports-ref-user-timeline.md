---
title: Levensduur datawarehouse-gebruikersentiteiten
titlesuffix: Microsoft Intune
description: Lees hoe het datawarehouse van Intune gebruikers in een tijdlijn laat zien.
keywords: Intune-datawarehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 363D148E-688F-4830-B6DE-AB4FE3648817
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: 4493ea8442642c09ee7a94b9b73fe0412c015649
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52189908"
---
# <a name="user-lifetime-representation-in-the-microsoft-intune-data-warehouse"></a>Levensduur gebruikers weergeven in het Microsoft Intune-datawarehouse

De maand aan momentopnamen van gegevens die zijn opgeslagen in het datawarehouse van Intune kunt u gebruiken voor het beantwoorden van vragen over trends op basis van tijd. U kunt bijvoorbeeld kijken naar het aantal gebruikers dat gedurende een maand wordt toegevoegd. U kunt ook vragen naar het aantal gebruikers dat uit het systeem is verwijderd.

In het datawarehouse worden historische gegevens opgeslagen om dit type informatie te kunnen verschaffen. In het datawarehouse kan de levensduur van een entiteit worden bijgehouden. Bij wijzigingen in de status van een entiteit en bij het verwijderen van de entiteit wordt in het datawarehouse vastgelegd wanneer een entiteit is gemaakt. Omdat de geschiedenis wordt vastgelegd met dagelijkse momentopnamen van kwantitatieve metingen, kunt u een bepaalde dag met de vorige vergelijken, enzovoort.

Werken met de levensduur van entiteiten kan verwarrend zijn omdat de status van uw entiteiten verandert. Dit betekent dat als u een momentopname op dag 30 bekijkt, er geen gebruikersrecord met een actieve status in de gegevens bestaat. Op dag 29-28 kan de entiteitsrecord een actieve status hebben. En vóór dag 28 bestond de gebruiker in het geheel niet.

Dit scenario wordt mogelijk wat duidelijker bij het doorlopen van de levensduur van een entiteit.

Als we ervan uitgaan dat een gebruiker, bijvoorbeeld **Jan de Vries**, een licentie krijgt toegewezen op 01-06-2017, bevat de tabel **Gebruiker** de volgende vermelding: 
 
| DisplayName | IsDeleted | StartDateInclusiveUTC | EndDateExclusiveUTC | IsCurrent 
| -- | -- | -- | -- | -- |
| Jan de Vries | ONWAAR | 01-06-2017 | 31-12-9999 | WAAR
 
Jan de Vries beëindigt zijn licentie op 25-07-2017. De tabel **Gebruiker** bevat de volgende vermeldingen. Wijzigingen in bestaande records zijn `marked`. 

| DisplayName | IsDeleted | StartDateInclusiveUTC | EndDateExclusiveUTC | IsCurrent 
| -- | -- | -- | -- | -- |
| Jan de Vries | ONWAAR | 01-06-2017 | `07/26/2017` | `FALSE` 
| Jan de Vries | WAAR | 26-07-2017 | 31-12-9999 | WAAR 

De eerste rij geeft aan dat Jan de Vries in Intune bestond van 01-06-2017 tot 25-07-2017. De tweede record geeft aan dat de gebruiker op 25-07-2017 werd verwijderd en niet meer in Intune aanwezig is.

Laten we er nu van uitgaan dat Jan de Vries een nieuwe licentie krijgt toegewezen op 31-08-2017. In dat geval bevat de tabel Gebruiker de volgende vermeldingen:
 
| DisplayName | IsDeleted | StartDateInclusiveUTC | EndDateExclusiveUTC | IsCurrent 
| -- | -- | -- | -- | -- |
| Jan de Vries | ONWAAR | 01-06-2017 | 26-07-2017 | ONWAAR 
| Jan de Vries | WAAR | 26-07-2017 | `08/31/2017` | `FALSE` 
| Jan de Vries | ONWAAR | 08/31/2017 | 31-12-9999 | WAAR 
 
Iemand die de huidige status van alle gebruikers wil zien, kan als filter `IsCurrent = TRUE` gebruiken. 
 
Iemand die alleen bestaande gebruikers wil zien, kan als filter `IsCurrent = TRUE AND IsDeleted = FALSE` gebruiken.

## <a name="dimension-tables-in-the-entity-lifetime"></a>Dimensietabellen in de levensduur van de entiteit

Om de geschiedenis van statuswijzigingen in entiteiten te kunnen bewaren, verwijdert Intune geen records. In plaats daarvan worden records alleen gemarkeerd als verwijderd. Dit wordt voorlopig verwijderen genoemd. De dimensietabellen bevatten diverse kolommen met metagegevens om de levensduur van records bij te houden. 

De meest gebruikte kolommen voor metagegevens zijn: 

| Eigenschapsnaam metagegevens  | Interpretatie van waarden |
|--|--|
| IsDeleted | Hiermee wordt aangegeven of de entiteit in Intune werd verwijderd. |
| StartDateInclusiveUTC  | De UTC-datum waarop de entiteit werd geladen in het Intune-datawarehouse. Het is mogelijk dat de entiteit is gemaakt voordat deze werd geïmporteerd in het Intune-datawarehouse. |
| DeletedDateUTC  | De UTC-datum waarop de entiteit in Intune werd verwijderd. |  

Kolommen met metagegevens die beginnen met het voorvoegsel **Rij**, zoals **RowLastModifiedDateTimeUTC**, geven aan wanneer een record in de Intune-datawarehouse is gemaakt of gewijzigd. Het datawarehouse bevindt zich downstream van de gegevens in Intune. Deze waarde heeft geen betrekking op de levensduur van de entiteit in Intune.  
 
Een persoon die alleen de dimensie-entiteiten wil zien die momenteel aanwezig zijn, kan een filter toepassen met **IsDeleted = FALSE**.

## <a name="next-steps"></a>Volgende stappen

 - Zie [Naslaginformatie voor huidige gebruikersentiteit](reports-ref-current-user.md) voor meer informatie over de entiteit **Huidige gebruiker**.
 - Zie [Naslaginformatie voor gebruikersentiteit](reports-ref-user.md) voor meer informatie over de entiteit **Gebruiker**.