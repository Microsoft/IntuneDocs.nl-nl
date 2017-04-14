---
title: Apps toevoegen aan Microsoft Intune
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: met deze procedures kunt u ervoor zorgen dat uw apps in Intune gereed zijn voor toewijzing aan gebruikers en apparaten. '
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e4a6aaa1a8e23dc2c58345f73ff8db86018843e1
ms.openlocfilehash: fe12a6b890c2d5cba874e820afbe7671b754deb5
ms.lasthandoff: 04/11/2017

---

# <a name="how-to-add-an-app-to-microsoft-intune"></a>Een app toevoegen aan Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Voordat u apps kunt beheren en toewijzen, moet u deze toevoegen aan Intune. Intune biedt ondersteuning voor een breed scala aan verschillende typen apps en de opties voor elk type kunnen afwijken.

Intune ondersteunt het toevoegen en toewijzen van de volgende typen apps:

![Typen apps die worden ondersteund door Intune](./media/app-types.png)

De volgende platformen worden ondersteund. Klik op een van de onderwerpen voor meer informatie over het toevoegen van elk type app.

- [Android Store-apps](/intune-azure/manage-apps/android-store-app)
- [iOS Store-apps](/intune-azure/manage-apps/ios-store-app)
- [Web-apps (voor alle platformen)](/intune-azure/manage-apps/web-app)
- [Windows Phone 8.1 Store-apps](/intune-azure/manage-apps/windows-phone-8-1-store-app)
- [Windows Store-apps](/intune-azure/manage-apps/windows-store-app)

> [!NOTE]
> Wanneer u een app vanuit een App Store toevoegt en implementeert, moeten eindgebruikers beschikken over een account bij die Store om de app te kunnen installeren.

## <a name="cloud-storage-space"></a>Cloudopslag
Alle apps die u maakt met het installatietype van het software-installatieprogramma (bijvoorbeeld een Line-Of-Business-app), worden verpakt en geüpload naar Microsoft Intune-cloudopslag. Een proefabonnement op Intune omvat 2 GB (gigabyte) cloudopslag, die wordt gebruikt voor het opslaan van beheerde apps en updates. Uw volledige abonnement omvat 20 GB aan opslagruimte.

U kunt extra opslagruimte kopen voor Intune met uw oorspronkelijke aankoopmethode.  Als u hebt betaald via een factuur of met een creditcard, gaat u naar de [Beheerportal abonnementen](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions).  Neem anders contact op met uw partner of verkoopassistent.

De vereisten voor cloudopslag zijn als volgt:

-   Alle app-installatiebestanden moeten zich in dezelfde map bevinden.
-   De maximale bestandsgrootte voor elk bestand dat u uploadt, is 2 GB.

## <a name="how-to-create-and-edit-categories-for-apps"></a>Categorieën voor apps maken en bewerken 

App-categorieën kunnen worden gebruikt om apps te sorteren, zodat eindgebruikers deze sneller kunnen vinden in de bedrijfsportal. U kunt een of meer categorieën toewijzen aan een app, bijvoorbeeld **Ontwikkelaars-apps** of **Communicatie-apps**. Als u een app aan Intune toevoegt, kunt u de gewenste categorie selecteren. Aan de hand van de platformenpecifieke onderwerpen kunt u een app toevoegen en categorieën toewijzen. Als u uw eigen categorieën wilt maken en bewerken, gebruikt u de volgende procedure: 

1. Meld u aan bij Azure Portal. 
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**. 
3. Kies **Apps beheren** op de blade **Intune**. 
4. Kies **Instellen** > **App-categorieën** in de workload **Mobiele apps**. 
5. Op de blade **App-categorieën** wordt een lijst met de huidige categorieën weergegeven. Kies een van de volgende acties: 
    - **Een categorie maken**: voer op de blade **Categorie maken** een naam voor de nieuwe categorie in. Namen kunnen slechts in één taal worden ingevoerd en worden niet door Intune vertaald. Wanneer u klaar bent, klikt u op **Maken**.
    - **Een categorie bewerken**: kies voor elke categorie in de lijst '**...**'. Geef op de blade **Eigenschappen** een nieuwe naam voor de categorie op of verwijder de categorie.




