---
title: Aan de slag met apps in Microsoft Intune
titlesuffix: 
description: Zoek apps en voeg ze toe aan apparaten om het voor uw medewerkers mogelijk te maken om hun werk uit te voeren.
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 3/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0185eebbe436da73e1920d7cd834f0897a143894
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/05/2018
---
# <a name="get-started-with-adding-apps-in-microsoft-intune"></a>Aan de slag met het toevoegen van apps in Microsoft Intune

Voordat u apps kunt toewijzen, controleren, configureren of beveiligen, moet u ze aan Intune toevoegen. Intune biedt ondersteuning voor verschillende app-typen. De beschikbare opties verschillen per app-type.

In Intune kunt u deze typen apps toevoegen en toewijzen aan uw bedrijfsapparaten:
- **Apps uit de Store**: voor apparaten waarvoor u extra Mobile Application Management wilt toepassen op apps die beschikbaar zijn in de App Store.
- **Apps die intern zijn ontwikkeld (line-of-business)**: u uploadt een bestand dat wordt gedownload naar de apparaten van gebruikers.
- **Apps die zijn ingebouwd**:hierbij wijst u gecureerde beheerde apps, zoals Office 365-apps, toe aan iOS- en Android-apparaten. 
- **Apps op internet**: er wordt door Intune een snelkoppeling gemaakt naar de web-app op het beginscherm van het apparaat.

## <a name="how-do-i-assign-a-public-store-app"></a>Hoe kan ik een app uit de openbare store toewijzen?

Aan de hand van het volgende voorbeeld komt u te weten hoe u een iOS-app toevoegt in Microsoft Intune.

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies **Mobiele apps** op de blade **Intune**.
4. In de workload **Mobiele apps** kiest u **Apps** in het gedeelte **Beheren**.
5. Kies **Toevoegen** aan de rechterkant van het deelvenster **Apps**.
6. In de lijst **App-type** selecteert u **iOS** bij de beschikbare typen **Store-apps**.
6. Kies **Zoeken in de App Store**.
7. Selecteer in de blade **Zoeken in de App Store** eerst de landinstelling voor de Store.
8. Typ de naam (of een deel daarvan) in het zoekvak. De Store wordt doorzocht met Intune, waarna een lijst met relevante resultaten wordt weergegeven.
9. Kies de gewenste app in de lijst en klik op **Selecteren**.
10. Voor het configureren van de app-gegevens selecteert u de blade **App-gegevens**.
11. (optioneel) U kunt gegevens toevoegen om de app beter te organiseren. Zo kunt u waarden opgeven voor **Eigenaar**, **Opmerkingen**, **Ontwikkelaar** en **Privacy-URL**. Via deze URL kunnen gebruikers het privacybeleid van uw bedrijf weergeven.
12. Selecteer **Ja** voor de optie **Deze weergeven als aanbevolen app in de bedrijfsportal**. 
13. Klik op **OK** nadat u alle benodigde informatie over de app hebt toegevoegd.
14. Klik op **Toevoegen** op de blade **App toevoegen**. U gaat dan naar het **overzicht** van de app. 

## <a name="next-steps"></a>Volgende stappen

Nu u een app aan Intune hebt toegevoegd, kunt u groepen werknemers toewijzen; deze kunnen van de app gebruikmaken op hun apparaat.

- [Apps aan groepen toewijzen](apps-deploy.md)
- 
## <a name="learn-more"></a>Meer informatie

* [Wat is app-beheer met Intune?](app-management.md)
* [Overzicht van de app-levenscyclus](app-lifecycle.md)
* [Wat zijn beleidsregels voor de beveiliging van apps?](app-protection-policy.md)
