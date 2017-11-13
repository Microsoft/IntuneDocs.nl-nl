---
title: Gebruiker - Intune-datawarehouse | Microsoft Docs
description: Naslagonderwerp voor de categorie Gebruiker van entiteitverzamelingen in de Intune-datawarehouse-API.
keywords: Intune-datawarehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: C29A6EEA-72B7-427E-9601-E05B408F3BB0
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 8088127f5968c0b4f07f83b1dad02ba90f4e6b9a
ms.sourcegitcommit: e9f9fccccef691333143b7523d1b325ee7d1915a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/02/2017
---
# <a name="reference-for-user-entity"></a>Naslag voor gebruikersentiteit

De categorie **Gebruiker** bevat de entiteit **Gebruiker** waarmee eigenschappen van gebruikers en agents worden gedefinieerd in het gegevensmodel.

**Gebruiker**

De entiteit **Gebruiker** bevat een lijst van alle Azure Active Directory-gebruikers (Azure AD) met toegewezen licenties in uw onderneming.

| Eigenschap  | Beschrijving | Voorbeeld |
|---------|------------|--------|
| UserKey |De unieke id van de gebruiker in het datawarehouse (surrogaatsleutel). |123 |
| UserId |De unieke id van de gebruiker, vergelijkbaar met UserKey, maar het is een natuurlijke sleutel. |b66bc706-ffff-7437-0340-032819502773 |
| UserEmail |Het e-mailadres van de gebruiker. |John@constoso.com |
| DisplayName |De weergavenaam van de gebruiker. |Jan |
| IntuneLicensed |Geeft aan of deze gebruiker een licentie heeft voor Intune |Waar/onwaar |
| IsDeleted |Geeft aan of deze gebruikersrecord is bijgewerkt.  Waar: deze gebruiker heeft een nieuwe record met bijgewerkte velden in deze tabel. Onwaar: de meest recente record voor deze gebruiker. |Waar/onwaar |
| StartDateInclusiveUTC |De datum en tijd in UTC waarop deze gebruiker is gemaakt in het datawarehouse. |11/23/2016 12:00:00 AM |
| EndDateExclusiveUTC |De datum en tijd in UTC waarop IsDeleted is gewijzigd in Waar. |11/23/2016 12:00:00 AM |
| IsCurrent |Geeft aan of deze gebruikersrecord actueel is of niet aanwezig is in het datawarehouse. |Waar/onwaar |
| RowLastModifiedDateTimeUTC |De datum en tijd in UTC waarop deze gebruiker het laatst is gewijzigd in het datawarehouse. |11/23/2016 12:00:00 AM |

