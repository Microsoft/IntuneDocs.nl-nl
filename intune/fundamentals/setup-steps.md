---
title: Microsoft Intune instellen
description: Vereisten en voorwaarden om uw Intune-abonnement te gaan gebruiken
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/24/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d158503c-1276-422b-ab81-5f66c1cd7e7a
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7a45160fc0e728b4c53590455a2bd0b5d904ddb1
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72504894"
---
# <a name="set-up-intune"></a>Intune instellen

Deze installatiestappen helpen u om Mobile Device Management (MDM) in te schakelen met Intune. Apparaten moeten worden beheerd voordat u gebruikers toegang kunt geven tot zakelijke resources of voordat ze instellingen op deze apparaten kunnen beheren.

Sommige stappen, zoals het instellen van een Intune-abonnement en het instellen van de MDM-instantie, zijn voor de meeste scenario’s vereist. Andere stappen, zoals het configureren van een aangepast domein of het toevoegen van apps, zijn optioneel en afhankelijk van de behoeften van uw organisatie.

Als u momenteel Microsoft System Center Configuration Manager gebruikt voor het beheer van computers en servers, kunt u [Configuration Manager in de cloud koppelen met co-beheer ](https://docs.microsoft.com/sccm/comanage/overview).

>[!TIP]
>Als u ten minste 150 licenties koopt voor Intune als onderdeel van een in aanmerking komend abonnement, kunt u *FastTrack Center Benefit* gebruiken. Met deze service werken Microsoft-specialisten met u samen om uw omgeving gereed te maken voor Intune. Zie [FastTrack Center Benefit-proces voor Enterprise Mobility + Security (EMS)](https://docs.microsoft.com/enterprise-mobility-security/Solutions/enterprise-mobility-fasttrack-program).



| Stappen |                                                                                                                       Status                                                                                                                       |
|-------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|   1   |                                        [Ondersteunde configuraties](supported-devices-browsers.md): informatie die u moet hebben voordat u aan de slag gaat. Hier vallen ook ondersteunde configuraties en netwerkvereisten onder.                                         |
|   2   |                                                                 [Aanmelden bij Intune](account-sign-up.md): meld u aan bij uw proefabonnement of maak een nieuw Intune-abonnement.                                                                  |
|   3   |                [Domeinnaam configureren](custom-domain-name-configure.md): stel de DNS-registratie in om de domeinnaam van uw bedrijf te verbinden met Intune. Hiermee geeft u gebruikers een bekend domein als ze verbinding maken met Intune en resources gebruiken.                |
|   4   |                                   [Gebruikers toevoegen](users-add.md): voeg handmatig gebruikers toe of maak verbinding met Active Directory om gebruikers te synchroniseren met Intune. Vereist tenzij uw apparaten bijvoorbeeld kioskapparaten 'zonder gebruiker' zijn.                                    |
|   5   |                                            [Licenties toewijzen](../licenses-assign.md): geef gebruikers machtigen om Intune te gebruiken. Elk apparaat, met of zonder gebruiker, vereist een Intune-licentie om toegang te krijgen tot de service.                                             |
|   6   |                                               [Groepen toevoegen](../groups-add.md): gebruik groepen met gebruikers en groepen met apparaten om beheertaken te vereenvoudigen. Groepen worden gebruikt om apps, instellingen en andere resources toe te wijzen.                                                |
|   7   |                                                                        [Apps toevoegen](../apps/apps-add.md): apps kunnen worden toegewezen aan groepen en automatisch of optioneel worden geïnstalleerd.                                                                         |
|   8   | [Apparaten configureren](../configuration/device-profiles.md): stel profielen in die apparaatinstellingen beheren. Apparaatprofielen kunnen voorinstellingen voor e-mail, VPN, wifi en functies van het apparaat bevatten. Ze kunnen ook apparaten beperken om zowel apparaten als gegevens te beschermen. |
|   9   |       [Bedrijfsportal aanpassen](../apps/company-portal-app.md): pas de Intune-bedrijfsportal aan die gebruikers gebruiken om apparaten in te schrijven en apps te installeren. Deze instellingen worden zowel in de bedrijfsportal-app als op de Intune-bedrijfsportalwebsite weergegeven.       |
|  10   |                                [Inschrijving van apparaten inschakelen](mdm-authority-set.md): schakel Intune-beheer van iOS-, Windows-, Android- en Mac-apparaten in door de MDM-instantie in te stellen en specifieke platforms in te schakelen.                                 |
|  11   |                                                        [App-beleidsregels configureren](../apps/app-protection-policy.md): geef specifieke instellingen op die zijn gebaseerd op de app-beveiligingsbeleidsregels in Microsoft Intune.                                                         |

