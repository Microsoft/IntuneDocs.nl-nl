---
title: Aan de slag met apps in Microsoft Intune
titlesuffix: ''
description: Zoek apps en voeg ze toe aan apparaten om het voor uw medewerkers mogelijk te maken om hun werk uit te voeren.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/09/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 399efad4f4cbe4dde1b45004daa9d0264e0db777
ms.sourcegitcommit: 11bd3dbbc9dd762df7c6d20143f2171799712547
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/10/2018
ms.locfileid: "48903400"
---
# <a name="get-started-with-adding-apps-in-microsoft-intune"></a>Aan de slag met het toevoegen van apps in Microsoft Intune

Voordat u apps kunt toewijzen, controleren, configureren of beveiligen, moet u ze aan Intune toevoegen. Intune biedt ondersteuning voor verschillende app-typen. De beschikbare opties verschillen per app-type.

In Intune kunt u deze typen apps toevoegen en toewijzen aan uw bedrijfsapparaten:
- **Apps uit de Store**: voor apparaten waarvoor u extra Mobile Application Management wilt toepassen op apps die beschikbaar zijn in de App Store.
- **Apps die intern zijn ontwikkeld (line-of-business)**: u uploadt een bestand dat wordt gedownload naar de apparaten van gebruikers.
- **Apps die zijn ingebouwd**:hierbij wijst u gecureerde beheerde apps, zoals Office 365-apps, toe aan iOS- en Android-apparaten.
- **Apps op internet**: er wordt door Intune een snelkoppeling gemaakt naar de web-app op het beginscherm van het apparaat.

> [!NOTE]
> Het kan maximaal acht uur duren voordat nieuw beleid dat is toegepast op een dynamische apparaatgroep wordt toegepast op alle apparaten in de groep.

## <a name="how-do-i-assign-a-public-store-app"></a>Hoe kan ik een app uit de openbare store toewijzen?

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Selecteer **Client-apps** en selecteer daarna **Apps**.
4. Selecteer **Toevoegen** en selecteer vervolgens **iOS** als het **app-type**.
5. Kies **App selecteren** om het deelvenster **Zoeken in de App Store** weer te geven.
6. Gebruik het tekstvak om te zoeken naar een app die u wilt toewijzen aan het apparaat. Kies de app en klik vervolgens op **Selecteren**.
7. Selecteer **App-gegevens** in het deelvenster **App toevoegen** en vul vervolgens alle gegevens van de app in. U kunt andere, optionele gegevens toevoegen om de app beter te organiseren. Zo kunt u waarden opgeven voor **Eigenaar**, **Opmerkingen**, **Ontwikkelaar** en **Privacy-URL**. Via deze URL kunnen gebruikers het privacybeleid van uw bedrijf weergeven.
8. Vergeet niet om **Ja** te selecteren voor de optie **Deze weergeven als aanbevolen app in de bedrijfsportal** en selecteer vervolgens **OK**.
9. Selecteer **Toevoegen** vanuit het deelvenster **App toevoegen** om de app toe te voegen. Hiermee gaat u naar het **overzicht** van de app. Kies **Toewijzingen** en klik vervolgens op **Groep toevoegen** om de app toe te wijzen aan uw testgroep. Selecteer **Beschikbaar** zodat de app kan worden gedownload. De app moet nu worden weergegeven bij **Aanbevolen app** op uw testapparaat.


- [Apps aan groepen toewijzen](apps-deploy.md)

## <a name="learn-more"></a>Meer informatie

* [Wat is app-beheer met Intune?](app-management.md)
* [Overzicht van de app-levenscyclus](app-lifecycle.md)
* [Wat zijn beleidsregels voor de beveiliging van apps?](app-protection-policy.md)
