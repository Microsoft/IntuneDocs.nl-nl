---
title: App-gegevens en -toewijzingen controleren
titlesuffix: Microsoft Intune
description: Nadat u een app hebt toegewezen aan gebruikers of apparaten, kunt u met behulp van deze informatie de status ervan controleren.
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/09/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2d1ca013b7000282316a17e02dcb38b3d4f27958
ms.sourcegitcommit: 820f950d1fc80b1eb5db1b0cf77f44d92a969951
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2018
---
# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>App-gegevens en -toewijzingen controleren met Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune biedt een aantal manieren om de eigenschappen en toewijzingsstatus te controleren van apps die u beheert.

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de groep **Controle en beheer**.
3. Kies **Mobiele apps** en kies **Apps** in de groep **Beheren**.
5. Kies in de lijst met apps een app die u wilt controleren. Vervolgens ziet u de app-blade met een overzicht van de apparaat- en gebruikersstatus.

## <a name="app-overview-blade"></a>Overzichtsblade van apps

U kunt de specifieke app-blade gebruiken voor meer informatie over de status van een app in uw omgeving.

### <a name="essentials"></a>Essentials
De sectie **Essentiële informatie** bevat de volgende informatie over de app:

 | **App-details**            | **Beschrijving**                                                      |
|------------------------|------------------------------------------------------------------|
| **Uitgever**          | De uitgever van de app.                                            |
| **Besturingssysteem**   | Het besturingssysteem van de app (Windows, iOS, Android enzovoort) |
| **Gemaakt**             | De datum en tijd waarop deze revisie is gemaakt.                         |
| **Toegewezen**           | **Ja** of **Nee** als de app is toegewezen.                  |

### <a name="device-and-user-status-graphs"></a>Apparaat- en gebruikersstatusgrafieken
In de grafieken ziet u het aantal voor de volgende status:

| **Apparaatstatus**       | **Beschrijving**                                       |
|-----------------------|-------------------------------------------------------|
| **Geïnstalleerd**         | Het aantal geïnstalleerde apps.                         |
| **Niet geïnstalleerd**     | Het aantal niet-geïnstalleerde apps.                     |
| **Mislukt**            | Het aantal mislukte installaties.                   |
| **Wacht op installatie**   | Het aantal apps dat momenteel wordt geïnstalleerd. |
| **Niet van toepassing**           | Het aantal apps waar de status niet van toepassing is.            |

### <a name="device-install-status"></a>Apparaatinstallatiestatus

Wanneer u **Apparaatinstallatiestatus** in de sectie **Monitor** selecteert, wordt een apparaatstatuslijst weergegeven. De tabel bevat de volgende kolommen:

| **Apparaatkolom**      | **Beschrijving**                                                                                                                                                                                                                                            |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Apparaatnaam**      | Naam van het apparaat op platforms waarop het benoemen van een apparaat is toegestaan. Op andere platforms maakt Intune een naam op basis van andere eigenschappen. Dit kenmerk is niet beschikbaar voor alle apparaten.                                                                       |
| **Gebruikersnaam**        | De naam van de gebruiker.                                                                                                                                                                                                                                      |
| **Platform**         | Het besturingssysteem van het apparaat (Windows, iOS, Android, enz.)                                                                                                                                                                                           |
| **Versie**          | Het versienummer van de app. Voor Line-Of-Business-apps wordt het volledige versienummer van de app weergegeven. Het volledige versienummer duidt een specifieke release van de app aan. Het nummer wordt weergegeven als _Versie_(_Build_). Bijvoorbeeld 2.2(2.2.17560800) |
| **Status**           | De status van de app.                                                                                                                                                                                                                                     |
| **Statusdetails**   | Details van de status.                                                                                                                                                                                                                                     |
| **Laatste check-in**    | Datum van de laatste synchronisatie van het apparaat met Intune.                                                                                                                                                                                                                  |


### <a name="user-install-status"></a>Gebruikersinstallatiestatus

Wanneer u **Gebruikersinstallatiestatus** in de sectie **Monitor** selecteert, wordt een gebruikersstatuslijst weergegeven. De tabel bevat de volgende kolommen:

| **Gebruikerskolom**     | **Beschrijving**                           |
|---------------------|-------------------------------------------|
| **Naam**            | De naam van de gebruiker in Azure AD.         |
| **Gebruikersnaam**       | De unieke naam van de gebruiker.              |
| **Installaties**   | Het aantal installaties van apps dat wordt gebruikt door de gebruiker. |
| **Fouten**        | Het aantal mislukte installaties door de gebruiker.     |
| **Niet geïnstalleerd**   | Het aantal apps dat niet door de gebruiker is geïnstalleerd. |


## <a name="next-steps"></a>Volgende stappen

- Zie [Het Intune-datawarehouse gebruiken](reports-nav-create-intune-reports.md) voor meer informatie over werken met uw Intune-gegevens.
- Zie [App-configuratiebeleidsregels voor Intune](app-configuration-policies-overview.md) voor informatie over app-configuratiebeleid.