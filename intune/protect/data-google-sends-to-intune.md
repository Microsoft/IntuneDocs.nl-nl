---
title: Gegevens die Google verzendt naar Intune
titleSuffix: Microsoft Intune
description: Lijst met gegevens die door Google worden verzonden naar Intune.
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
ms.assetid: c379c8db-788a-454e-9098-665ea3bc7b56
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 914ce3aa15099b7692d524dbfa368f99f0d092e8
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72504488"
---
# <a name="data-google-sends-to-intune"></a>Gegevens die Google verzendt naar Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Als zakelijk Android-apparaatbeheer is ingeschakeld op een apparaat, maakt Microsoft Intune verbinding met Google en worden er gebruikers- en apparaatgegevens gedeeld tussen Intune en Google. Voordat Microsoft Intune verbinding kan maken, moet u een Google-account maken.

De volgende tabel bevat de gegevens die Google naar Microsoft Intune verzendt wanneer apparaatbeheer op een apparaat wordt ingeschakeld:


| Gegevens die Google verzendt naar Intune | Details | Gebruikt voor | Voorbeeld |
|:---:|:---:|:---:|:---:|
| Zakelijke gegevens | Ondernemings-id's van de klant in Google. | Hiermee worden gegevens van de klant gekoppeld tussen Intune en Google. | Voorbeeld van **enterpriseId**: LC04eik8a6.<br>**Naam**. De naam van de beheerder die is ingevoerd bij het configureren van Android Enterprise. Voorbeeld: Stefan Spel.<br>**E-mailadres beheerder**. YourAdmin@gmail.com die is gebruikt bij het configureren van Android Enterprise. |
| Toepassingsgegevens | Gegevens voor beheerde Play Store-toepassingen. | Bedoeld voor de toepassing voor gebruikers of apparaten als deze beschikbaar of vereist zijn. | Voorbeeld van **Toepassingsnaam**: Contoso-toepassing voor magazijninventarisatie.<br>Voorbeeld van **unieke id voor de toepassing**: app:com. Contoso.magazijn.inventarisatie |
| Serviceaccount | Uniek, intern Google-serviceaccount voor gebruik met specifieke klantaanroepen. | Wordt gebruikt voor aanroepen in Google namens de klant (om apps en apparaten te bekijken en meer) | Voorbeeld van **naam**: InternalAccount@InternalService.com.<br>Voorbeeld van **Sleutels**: ServiceAccountPassword |


Als u zakelijke Android-apparaten niet meer wilt beheren met Microsoft Intune en u de gegevens wilt verwijderen, moet u zowel het zakelijke Android-apparaatbeheer via Microsoft Intune uitschakelen als uw Google-account verwijderen. In uw Google-account vindt u meer informatie over accountbeheer.


