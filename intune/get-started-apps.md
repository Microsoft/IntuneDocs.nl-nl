---
title: Aan de slag met apps
titlesuffix: Azure portal
description: Zoek apps en voeg ze toe aan apparaten om het voor uw medewerkers mogelijk te maken om hun werk uit te voeren.
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bb02c362f056c454f4d141ce7ae20b9c3ca8035d
ms.sourcegitcommit: a7c1e10e615e5c975bb5d52eca986c5cf5287687
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/07/2017
---
# <a name="get-started-with-adding-apps"></a>Aan de slag met het toevoegen van apps

Intune ondersteunt een aantal verschillende manieren om apps te implementeren op apparaten die bedrijfseigendom zijn:

* **Software-installatieprogramma's**: u uploadt een uitvoerbaar bestand dat wordt gedownload naar de apparaten van gebruikers
* __Externe koppelingen__: voor een app in een openbare App Store of voor een web-app
* **Beheerde apps**: voor iOS-apparaten waarvoor u extra Mobile Application Management wilt toepassen op apps die beschikbaar zijn in de App Store

U kiest voor een van de snellere methoden voor het implementeren van een toepassing als u een app uit een openbare App Store toewijst.

## <a name="how-do-i-assign-a-public-store-app"></a>Hoe kan ik een app uit de openbare store toewijzen?

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Gebruik **Resources zoeken** om te zoeken naar **Intune**.
3. Selecteer **Mobile Apps** en selecteer daarna **Apps**.
4. Selecteer **Toevoegen** en selecteer vervolgens **iOS** onder **Store-app** als het **app-type**.
5. Kies **App selecteren** om de blade **Zoeken in de App Store** weer te geven.
6. Gebruik het tekstvak om te zoeken naar een app die u wilt toewijzen aan het apparaat. Kies de app en klik vervolgens op **Selecteren**.
7. Selecteer **App-gegevens** op de blade **App toevoegen** en vul vervolgens alle gegevens van de app in. U kunt andere, optionele gegevens toevoegen om de app beter te organiseren. Zo kunt u waarden opgeven voor **Eigenaar**, **Opmerkingen**, **Ontwikkelaar** en **Privacy-URL**. Via deze URL kunnen gebruikers het privacybeleid van uw bedrijf weergeven.
8. Vergeet niet om **Ja** te selecteren voor de optie **Deze weergeven als aanbevolen app in de bedrijfsportal** en selecteer vervolgens **OK**.
9. Selecteer **Toevoegen** vanuit de blade **App toevoegen** om de app toe te voegen. U ziet nu de pagina **Overzicht** van de app. Kies **Toewijzingen** en klik vervolgens op **Groepen selecteren** om de app toe te wijzen aan uw testgroep. Selecteer **Beschikbaar** zodat de app kan worden gedownload. De app moet nu worden weergegeven bij **Aanbevolen app** op uw testapparaat.

## <a name="learn-more"></a>Meer informatie

* [Wat is app-beheer met Intune?](app-management.md)
* [Overzicht van de app-levenscyclus](app-lifecycle.md)
* [Wat zijn beleidsregels voor de beveiliging van apps?](app-protection-policy.md)
