---
title: Gebruiker - Intune-datawarehouse | Microsoft Docs
description: Naslagonderwerp voor de categorie Gebruiker van entiteitverzamelingen in de Intune-datawarehouse-API.
keywords: Intune-datawarehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: C29A6EEA-72B7-427E-9601-E05B408F3BB0
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2d81d17bc9489900f9d17101db1f1496ba8d55e9
ms.sourcegitcommit: d26930f45ba9e6292a49bcb08defb5b3f14b704b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/15/2017
---
# <a name="reference-for-user-entity"></a>Naslag voor gebruikersentiteit

De categorie **Gebruiker** bevat de entiteit **Gebruiker** waarmee eigenschappen van gebruikers en agents worden gedefinieerd in het gegevensmodel.

## <a name="user"></a>Gebruiker

De entiteit **Gebruiker** bevat een lijst van alle Azure Active Directory-gebruikers (Azure AD) met toegewezen licenties in uw onderneming.

De entiteitverzameling **Gebruiker** bevat gegevens van de afgelopen maand. Deze records bevatten gebruikersstatussen gedurende de periode van gegevensverzameling, ook als de gebruiker is verwijderd. Een gebruiker kan bijvoorbeeld worden toegevoegd aan Intune en vervolgens ergens gedurende de afgelopen maand zijn verwijderd. Ook al is deze gebruiker niet aanwezig op het moment dat het rapport wordt gegenereerd, toch zijn de gebruiker en de status aanwezig in de gegevens van de vorige maand. U kunt een rapport maken dat de duur van de historische aanwezigheid van de gebruiker in uw gegevens weergeeft.

| Eigenschap  | Beschrijving | Voorbeeld |
|---------|------------|--------|
| UserKey |De unieke id van de gebruiker in het datawarehouse (surrogaatsleutel). |123 |
| UserId |De unieke id van de gebruiker, vergelijkbaar met UserKey, maar het is een natuurlijke sleutel. |b66bc706-ffff-7437-0340-032819502773 |
| UserEmail |Het e-mailadres van de gebruiker. |John@constoso.com |
| UPN | De UPN (user principal name) van de gebruiker. | John@constoso.com |
| DisplayName |De weergavenaam van de gebruiker. |Jan |
| IntuneLicensed |Geeft aan of deze gebruiker een licentie heeft voor Intune |Waar/onwaar |
| IsDeleted | Geeft aan of alle licenties van de gebruiker zijn verlopen en of de gebruiker daarom uit Intune werd verwijderd. Deze markering verandert niet voor één record. In plaats daarvan wordt er een nieuwe record gemaakt voor een nieuwe gebruikersstatus. |Waar/onwaar |
| StartDateInclusiveUTC |Als IsDeleted = FALSE: datum/tijd in UTC wanneer aan de gebruiker een licentie is toegewezen en de gebruiker zijn aanwezigheid in Intune kenbaar heeft gemaakt. Als IsDeleted = TRUE: datum/tijd in UTC wanneer de licentie van de gebruiker is verlopen en werd verwijderd uit Intune. |11/23/2016 12:00:00 AM |
| EndDateExclusiveUTC |Als IsDeleted = FALSE: datum/tijd in UTC wanneer de licentie van de gebruiker is verlopen en werd verwijderd uit Intune. De licentie is ergens in de loop van de vorige dag verlopen. Als IsDeleted = TRUE: datum/tijd in UTC wanneer de gebruiker een nieuwe licentie heeft gekregen en opnieuw in Intune is gemaakt.  |11/23/2016 12:00:00 AM |
| IsCurrent |Geeft aan of deze record de meest recente status van de gebruiker vertegenwoordigt. Er kunnen voor één gebruiker meerdere records bestaan, maar slechts één daarvan vertegenwoordigt de huidige status.  |Waar/onwaar |
| RowLastModifiedDateTimeUTC |De datum en tijd in UTC waarop de record het laatst is gewijzigd in het datawarehouse  |11/23/2016 12:00:00 AM |

## <a name="next-steps"></a>Volgende stappen
 - Met de entiteitverzameling **Huidige gebruiker** kunt u de gebruikersgegevens beperken tot gebruikers die momenteel actief zijn. Zie [Naslag voor huidige gebruikersentiteit](reports-ref-current-user.md) voor meer informatie. 
 - Zie [Levensduur gebruikers weergeven in Intune-datawarehouse](reports-ref-user-timeline.md) voor meer informatie over hoe het datawarehouse de levensduur van een gebruiker in Intune bijhoudt.
