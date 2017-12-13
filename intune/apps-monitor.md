---
title: App-gegevens en -toewijzingen controleren
titlesuffix: Azure portal
description: Nadat u een app hebt toegewezen aan gebruikers of apparaten, kunt u met behulp van deze informatie de status ervan controleren.
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0298fc255b3c11a12b5bf225968d6f2303192053
ms.sourcegitcommit: 520eb7712625e129b781e2f2b9fe16f9b9f3d08a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>App-gegevens en -toewijzingen controleren met Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune biedt een aantal manieren om de eigenschappen en toewijzingsstatus te controleren van apps die u beheert.

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** + **Intune**.
3. Kies in de workload **Mobiele apps** **Apps** in de groep **Beheren**.
5. Kies een app in de lijst met app-blades. U ziet dan de blade <*app-naam*> **Installatiestatus apparaat**.

## <a name="app-overview-blade"></a>Overzichtsblade van apps

U kunt de blade <*app-naam*> **Installatiestatus apparaat** gebruiken voor meer informatie over de status van een app in uw omgeving.

### <a name="essentials"></a>Essentiële informatie

De sectie **Essentiële informatie** bevat de volgende informatie over de app:

 - **Uitgever**  
De uitgever van de app.
 - **Besturingssysteem**  
Het besturingssysteem van de app (Windows, iOS, Android, enz.)
 - **Maken**  
Het tijdstip waarop deze revisie is gemaakt.
 - **Toegewezen**  
**Ja** of **Nee** als de app is toegewezen.

### <a name="status"></a>Status
Elke grafiek geeft aantallen voor de volgende status weer:

 - **Geïnstalleerd**  
Het aantal geïnstalleerde apps.
 - **Niet geïnstalleerd**  
Het aantal niet-geïnstalleerde apps.
 - **Wacht op installatie**  
Het aantal apps dat momenteel wordt geïnstalleerd.
 - **Mislukt**  
Het aantal mislukte installaties.
 - **Onbekend**  
Het aantal apps met een onbekende status.

### <a name="device-status"></a>Apparaatstatus

De apparaatstatus. Een ringdiagram die de installatiestatus van de app op apparaten weergeeft. Klik op de grafiek om een lijst met details over de apparaatstatus te openen. De tabel bevat de volgende kolommen:

 - **Apparaatnaam**  
Naam van het apparaat op platforms waarop het benoemen van een apparaat is toegestaan. Op andere platforms maakt Intune een naam op basis van andere eigenschappen. Dit kenmerk is niet beschikbaar voor alle apparaten.
 - **Gebruikersnaam**  
De naam van de gebruiker.
 - **Platform**  
Het besturingssysteem van het apparaat (Windows, iOS, Android, enz.)
 - **Versie**  
Het versienummer van de app. Voor line-of-business-apps wordt het volledige versienummer van de app weergegeven. Het volledige versienummer duidt een specifieke release van de app aan. Het nummer wordt weergegeven als _Versie_(_Build_). Bijvoorbeeld 2.2(2.2.17560800)
 - **Status**  
De status van de app.
 - **Statusdetails**  
Details van de status.
 - **Laatste check-in**  
Datum van de laatste synchronisatie van het apparaat met Intune.


### <a name="user-status"></a>Gebruikersstatus

De gebruikersstatus. Een ringdiagram die de installatiestatus van de app voor gebruikers weergeeft. Klik op de grafiek om een lijst met details over de apparaatstatus te openen. De tabel bevat de volgende kolommen:
 - **Naam**  
De naam van de gebruiker in Azure AD.
 - **Gebruikersnaam**  
De unieke naam van de gebruiker.
 - **Installaties**  
Het aantal installaties van apps dat wordt gebruikt door de gebruiker.
 - **Fouten**  
Het aantal mislukte installaties door de gebruiker.
 - **Niet geïnstalleerd**  
Het aantal apps dat niet door de gebruiker is geïnstalleerd.


## <a name="next-steps"></a>Volgende stappen

Zie [Het Intune-datawarehouse gebruiken](reports-nav-create-intune-reports.md) voor meer informatie over werken met uw Intune-gegevens.