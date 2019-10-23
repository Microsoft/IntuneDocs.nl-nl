---
title: Gegevens die Intune naar Google verzendt
titleSuffix: Microsoft Intune
description: Lijst met gegevens die door Intune worden verzonden naar Google.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a5c3bec4-18ed-11e8-accf-0ed5f89f718b
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9f6ab8a4e8e46373a536949c13ceaebb267f34cd
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72504454"
---
# <a name="data-intune-sends-to-google"></a>Gegevens die Intune naar Google verzendt

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Als zakelijk Android-apparaatbeheer is ingeschakeld op een apparaat, maakt Microsoft Intune verbinding met Google en worden er gebruikers- en apparaatgegevens gedeeld met Google. Voordat Microsoft Intune verbinding kan maken, moet u een Google-account maken.

De volgende tabel bevat de gegevens die Microsoft Intune naar Google verzendt wanneer apparaatbeheer op een apparaat wordt ingeschakeld:


| Gegevens die worden verzonden naar Google | Details | Gebruikt voor | Voorbeeld |
|:---:|:---:|:---:|:---:|
| EnterpriseId | Afkomstig van Google bij het koppelen van uw Gmail-account aan Intune. | Primaire id, gebruikt om communicatie mogelijk te maken tussen Intune en Google.  Deze communicatie gaat over het instellen van beleid, het beheer van apparaten en het koppelen van Android-apparaten aan Intune (of het opheffen van de koppeling). | Unieke id. Voorbeeldnotatie: LC04eik8a6 |
| Hoofdtekst beleid | Afkomstig uit Intune; ontstaan bij het opslaan van een nieuwe app of een nieuw configuratiebeleid. | Beleidsregels toepassen op apparaten. | Dit is een verzameling van alle geconfigureerde instellingen voor een toepassing of configuratiebeleid. Dit kan klantinformatie bevatten als dit wordt geleverd als onderdeel van een beleid, zoals netwerknamen, toepassingsnamen en app-specifieke instellingen. |
| Apparaatgegevens | Bij apparaten in een werkprofielscenario moeten die apparaten eerst worden ingeschreven bij Intune. Bij apparaten in een beheerde-apparatenscenario moeten die apparaten eerst worden ingeschreven bij Google. | Er worden tussen Intune en Google apparaatgegevens gedeeld voor verschillende acties, zoals het toepassen van beleid, het beheren van het apparaat en algemene rapportage. | **De unieke id die de apparaatnaam vertegenwoordigt.** Voorbeeld: enterprises/LC04ebru7b/devices/3592d971168f9ae4<br>**De unieke id die de gebruikersnaam vertegenwoordigt.** Voorbeeld: Enterprises/LC04ebru7b/users/116838519924207449711<br>**Apparaatstatus.** Voorbeelden: Actief, Uitgeschakeld, Wordt ingericht.<br>**Nalevingsstatussen.** Voorbeelden: Instelling wordt niet ondersteund, Vereiste apps ontbreken<br>**Software-informatie.** Voorbeelden: softwareversies en patchniveau.<br>**Netwerkinformatie.** Voorbeelden: IMEI, MEID, WifiMacAddress<br>**Apparaatinstellingen.** Voorbeelden: Informatie over de versleutelingsniveaus en of op apparaten onbekende apps zijn toegestaan.<br> Hieronder vindt u een voorbeeld van een JSON-bericht. |
| newPassword | Afkomstig uit Intune. | De wachtwoordcode van het apparaat wordt opnieuw ingesteld. | De tekenreeks die het nieuwe wachtwoord vertegenwoordigt. |
| Google-gebruiker | Google | Het werkprofiel beheren in werkprofielscenario's (BYOD). | De unieke id die het gekoppelde Gmail-account vertegenwoordigt. Voorbeeld: 114223373813435875042 |
| Toepassingsgegevens | Afkomstig uit Intune, bij het opslaan van toepassingsbeleid. |  | Tekenreeks voor naam van toepassing. Voorbeeld: app:com.microsoft.windowsintune.companyportal |
| Zakelijk serviceaccount | Afkomstig van Google, op verzoek van Intune. | Wordt gebruikt voor verificatie tussen Intune en Google, speciaal voor transacties waar deze klant bij is betrokken. | Er zijn verschillende onderdelen:<br> **Ondernemings-id**: eerder beschreven.<br>**UPN**: gegenereerde UPN, gebruikt voor verificatie namens de klant.<br>Voorbeeld: w49d77900526190e26708c31c9e8a0@pfwp-commicrosoftonedfmdm2.google.com.iam.gserviceaccount.com<br>**Sleutel**: Op basis van Base64 versleutelde blob, gebruikt in verificatieaanvragen en versleuteld opgeslagen in de service. De blob ziet er als volgt uit:<br> De unieke id die de sleutel van de klant vertegenwoordigt<br>Voorbeeld: a70d4d53eefbd781ce7ad6a6495c65eb15e74f1f |


Als u zakelijke Android-apparaten niet meer wilt beheren met Microsoft Intune en u de gegevens wilt verwijderen, moet u zowel het zakelijke Android-apparaatbeheer via Microsoft Intune uitschakelen als uw Google-account verwijderen. In uw Google-account vindt u meer informatie over accountbeheer.


