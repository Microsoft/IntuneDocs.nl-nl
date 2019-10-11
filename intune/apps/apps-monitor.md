---
title: App-gegevens en -toewijzingen controleren
titleSuffix: Microsoft Intune
description: Nadat u een app hebt toegewezen aan gebruikers of apparaten, kunt u met behulp van deze informatie de status van de app controleren.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 03c38472a3100ec2d717e802e07e189a53ac0866
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71725007"
---
# <a name="monitor-app-information-and-assignments-with-microsoft-intune"></a>App-gegevens en -toewijzingen controleren met Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune biedt een aantal manieren om de eigenschappen te controleren van apps die u beheert en om de status van app-toewijzingen te beheren.

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Selecteer in het deelvenster **Intune** de optie **Client-apps**.
4. Selecteer **Apps** in de sectie **Beheren** van het menu.
5. Selecteer in de lijst met apps een app om te controleren. Vervolgens ziet u het deelvenster met een app-overzicht van de apparaat- en gebruikersstatus.

> [!NOTE]
> Van Android Store-apps die als **beschikbaar** worden ingericht, wordt de installatiestatus niet vermeld.

## <a name="app-overview-pane"></a>Deelvenster met een app-overzicht

In dit app-deelvenster kunt u details bekijken over de status van een app in uw omgeving.

### <a name="essentials"></a>Essentials
De sectie **Essentiële informatie** bevat de volgende informatie over de app:

 | **App-details**            | **Beschrijving**                                                      |
|------------------------|------------------------------------------------------------------|
| **Uitgever**          | De uitgever van de app.                                            |
| **Besturingssysteem**   | Het app-besturingssysteem (Windows, iOS, Android, enzovoort). |
| **Gemaakt**             | De datum en tijd waarop deze revisie is gemaakt. <b>**Opmerking**: Deze datumwaarde wordt bijgewerkt wanneer een IT-beheerder de app-metagegevens wijzigt, bijvoorbeeld door de app-categorie of app-beschrijving te wijzigen.                        |
| **Toegewezen**           | Of de app is toegewezen (**Ja** of **Nee**).                  |

### <a name="device-and-user-status-graphs"></a>Apparaat- en gebruikersstatusgrafieken
In de grafieken wordt het aantal apps weergegeven voor de volgende status:

| **Apparaatstatus**       | **Beschrijving**                                       |
|-----------------------|-------------------------------------------------------|
| **Geïnstalleerd**         | Het aantal geïnstalleerde apps.                         |
| **Niet geïnstalleerd**     | Het aantal niet-geïnstalleerde apps.                     |
| **Mislukt**            | Het aantal mislukte installaties.                   |
| **Wacht op installatie**   | Het aantal apps dat momenteel wordt geïnstalleerd. |
| **Niet van toepassing**           | Het aantal apps waarvan de status is Niet toegepast.            |

> [!NOTE]
> Houd er rekening mee dat Android-LOB-apps (.APK) die zijn geïmplementeerd als **Beschikbaar met of zonder inschrijving**, alleen een app-installatiestatus voor ingeschreven apparaten rapporteren. De app-installatiestatus is niet beschikbaar voor apparaten die niet zijn ingeschreven bij Intune.

### <a name="device-install-status"></a>Apparaatinstallatiestatus

Wanneer u **Apparaatinstallatiestatus** in de sectie **Controleren** van het menu selecteert, wordt een lijst met apparaatstatussen weergegeven. De tabel bevat de volgende kolommen:

| **Apparaatkolom**      | **Beschrijving**                                                                                                                                                                                                                                            |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Apparaatnaam**      | De naam van het apparaat op platforms waarop het benoemen van een apparaat is toegestaan. Op andere platforms maakt Intune een naam op basis van andere eigenschappen. Dit kenmerk is niet beschikbaar op andere apparaten.                                                                       |
| **Gebruikersnaam**        | De naam van de gebruiker.                                                                                                                                                                                                                                      |
| **Platform**         | Het besturingssysteem van het apparaat (Windows, iOS, Android, enzovoort).                                                                                                                                                                                           |
| **Versie**          | Het versienummer van de app. Voor LOB-apps (Line-Of-Business) en Microsoft Store voor Bedrijven wordt het volledige versienummer van de app weergegeven. Het volledige versienummer duidt een specifieke release van de app aan. Het nummer wordt weergegeven als _Versie_(_Build_). Bijvoorbeeld 2.2(2.2.17560800). Voor standaard-Store-apps worden geen versies weergegeven. |
| **Status**           | De status van de app.                                                                                                                                                                                                                                     |
| **Statusdetails**   | De details van de status.                                                                                                                                                                                                                                     |
| **Laatste check-in**    | De datum van de laatste synchronisatie van het apparaat met Intune.                                                                                                                                                                                                                  |


### <a name="user-install-status"></a>Gebruikersinstallatiestatus

Wanneer u **Gebruikersinstallatiestatus** selecteert in de sectie **Controleren** van het menu, wordt een lijst met gebruikersstatussen weergegeven. De tabel bevat de volgende kolommen:

| **Gebruikerskolom**     | **Beschrijving**                           |
|---------------------|-------------------------------------------|
| **Naam**            | De naam van de gebruiker in Azure Active Directory.         |
| **Gebruikersnaam**       | De unieke naam van de gebruiker.              |
| **Installaties**   | Het aantal apps dat is geïnstalleerd door de gebruiker. |
| **Fouten**        | Het aantal mislukte app-installaties voor de gebruiker.     |
| **Niet geïnstalleerd**   | Het aantal apps dat niet is geïnstalleerd door de gebruiker. |


## <a name="next-steps"></a>Volgende stappen

- Zie [Het Intune-datawarehouse gebruiken](../reports-nav-create-intune-reports.md) voor meer informatie over werken met uw Intune-gegevens.
- Zie [App-configuratiebeleidsregels voor Intune](app-configuration-policies-overview.md) voor informatie over app-configuratiebeleid.
