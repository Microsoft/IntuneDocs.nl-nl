---
title: Gebruiker - Intune-datawarehouse
titleSuffix: Microsoft Intune
description: Naslagonderwerp voor de categorie Gebruiker van entiteitverzamelingen in de Intune-datawarehouse-API.
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
ms.assetid: C29A6EEA-72B7-427E-9601-E05B408F3BB0
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 202d9e53ff21e5677a212012d37b0e909cc8c562
ms.sourcegitcommit: 8d7406b75ef0d75cc2ed03b1a5e5f74ff10b98c0
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 01/03/2020
ms.locfileid: "75654087"
---
# <a name="reference-for-user-entity"></a>Naslag voor gebruikersentiteit

De categorie **Gebruikers** bevat de entiteit **gebruiker** waarmee eigenschappen van gebruikers in het gegevensmodel worden gedefinieerd.

## <a name="users"></a>gebruikers

De entiteit **user** bevat een lijst van alle Azure Active Directory-gebruikers (Azure AD) met toegewezen licenties in uw onderneming.

De entiteitverzameling **user** bevat gebruikersgegevens. Deze records bevatten gebruikersstatussen gedurende de periode van gegevensverzameling, ook als de gebruiker is verwijderd. Een gebruiker kan bijvoorbeeld worden toegevoegd aan Intune en vervolgens ergens gedurende de afgelopen maand zijn verwijderd. Ook al is deze gebruiker niet aanwezig op het moment dat het rapport wordt gegenereerd, toch zijn de gebruiker en de status aanwezig in de gegevens van de vorige maand. U kunt een rapport maken dat de duur van de historische aanwezigheid van de gebruiker in uw gegevens weergeeft.

|          Eigenschap          |                                                                                                           Beschrijving                                                                                                          |                Voorbeeld               |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:------------------------------------:|
| userKey                    | De unieke id van de gebruiker in het datawarehouse - surrogaatsleutel.                                                                                                                                                         | 123                                  |
| userId                     | De unieke id van de gebruiker, vergelijkbaar met UserKey, maar dit is een natuurlijke sleutel.                                                                                                                                                    | b66bc706-ffff-7437-0340-032819502773 |
| userEmail                  | Het e-mailadres van de gebruiker.                                                                                                                                                                                                     | John@constoso.com                    |
| userPrincipalName                        | De UPN (user principal name) van de gebruiker.                                                                                                                                                                                               | John@constoso.com                    |
| displayName                | De weergavenaam van de gebruiker.                                                                                                                                                                                                      | Jan                                 |
| intuneLicensed             | Geeft aan of deze gebruiker een licentie heeft voor Intune                                                                                                                                                                              | Waar/onwaar                           |
| isDeleted                  | Geeft aan of alle licenties van de gebruiker zijn verlopen en of de gebruiker daarom uit Intune werd verwijderd. Deze markering verandert niet voor één record. In plaats daarvan wordt er een nieuwe record gemaakt voor een nieuwe gebruikersstatus. | Waar/onwaar                           |
| RowLastModifiedDateTimeUTC | De datum en tijd in UTC waarop de record het laatst is gewijzigd in het datawarehouse                                                                                                                                                 | 23-11-2016, 0:00                      |


## <a name="next-steps"></a>Volgende stappen
- Met de entiteitverzameling **Huidige gebruiker** kunt u de gebruikersgegevens beperken tot gebruikers die momenteel actief zijn. Zie [Naslag voor huidige gebruikersentiteit](../reports-ref-current-user.md) voor meer informatie.
- Zie [Levensduur gebruikers weergeven in Intune-datawarehouse](reports-ref-user-timeline.md) voor meer informatie over hoe het datawarehouse de levensduur van een gebruiker in Intune bijhoudt.
