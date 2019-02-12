---
title: Huidige gebruiker - Intune-datawarehouse
titlesuffix: Microsoft Intune
description: Naslagonderwerp voor de categorie Huidige gebruiker van entiteitverzamelingen in de Intune-datawarehouse-API.
keywords: Intune-datawarehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: C10E6752-E925-40AD-ABBF-6B621FB7AFC4
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: b9fdd1891f8a0e893d61ac3a0b40dac5a01f602c
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55851335"
---
# <a name="reference-for-current-user-entity"></a>Naslaginformatie voor huidige gebruikersentiteit

De categorie **Huidige gebruiker** bevat gebruikerseigenschappen in het gegevensmodel. De entiteitverzameling **Huidige gebruiker** is beperkt tot gebruikers die momenteel actief zijn. De entiteit bevat alle Azure Active Directory-gebruikers aan wie momenteel een licentie is toegewezen. De licentie kan een Intune-licentie, een hybride licentie of een licentie voor Microsoft Office 365 zijn. Als een gebruiker is verwijderd, wordt deze niet weergegeven in de verzameling Huidige gebruiker. Zie [Naslag voor gebruikersentiteit](reports-ref-user.md) voor een verzameling die een overzicht van wijzigingen in de status van de gebruiker bevat.


## <a name="current-user"></a>Huidige gebruiker

De entiteit **Huidige gebruiker** bevat een lijst van alle Azure Active Directory-gebruikers (Azure AD) met toegewezen licenties in uw onderneming.

| Eigenschap  | Beschrijving | Voorbeeld |
|---------|------------|--------|
| UserKey |De unieke id van de gebruiker in het datawarehouse (surrogaatsleutel). |123 |
| UserId |De unieke id van de gebruiker, vergelijkbaar met UserKey, maar het is een natuurlijke sleutel. |b66bc706-ffff-7437-0340-032819502773 |
| UserEmail |Het e-mailadres van de gebruiker. |John@constoso.com |
| UPN | De UPN (user principal name) van de gebruiker. | John@constoso.com |
| DisplayName |De weergavenaam van de gebruiker. |Jan |
| IntuneLicensed |Geeft aan of deze gebruiker een licentie heeft voor Intune |Waar/onwaar |
| StartDateInclusiveUTC |De datum en tijd in UTC waarop deze gebruiker is gemaakt in het datawarehouse. |11/23/2016 12:00:00 AM |
| RowLastModifiedDateTimeUTC |De datum en tijd in UTC waarop deze gebruiker het laatst is gewijzigd in het datawarehouse. |11/23/2016 12:00:00 AM |

## <a name="next-steps"></a>Volgende stappen
 - Met de entiteitverzameling **Gebruikers** kunt u de gebruikersgegevens uitbreiden naar gebruikers die momenteel niet actief zijn. Zie [Naslag voor gebruikersentiteit](reports-ref-user.md) voor meer informatie.
 - Zie [Levensduur gebruikers weergeven in Intune-datawarehouse](reports-ref-user-timeline.md) voor meer informatie over hoe het datawarehouse de levensduur van een gebruiker in Intune bijhoudt.
