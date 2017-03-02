---
title: Apps aan groepen toewijzen | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: als u een app aan Intune hebt toegevoegd, wilt u deze wellicht toewijzen aan groepen met gebruikers of apparaten.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 638ad0d87c19c9e40e96b42d18e5c4342f40a156
ms.lasthandoff: 02/16/2017

---

# <a name="how-to-assign-apps-to-groups-with-microsoft-intune"></a>Apps aan groepen toewijzen met Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Wanneer u een app aan Intune hebt toegevoegd, wilt u deze wellicht distribueren naar gebruikers en apparaten. U kunt dit doen door de app toe te wijzen.

Apps kunnen worden toegewezen aan apparaten, ongeacht of ze worden beheerd door Intune. In de volgende tabel ziet u de verschillende opties voor het toewijzen van apps aan gebruikers en apparaten.

||||
|-|-|-|-|
|&nbsp;|Apparaten die zijn ingeschreven met Intune|Apparaten die niet zijn ingeschreven met Intune|
|Toewijzen aan gebruikers|Yes|Ja|
|Toewijzen aan apparaten|Yes|Nee|
|Ingepakte apps of apps waarin Intune SDK is opgenomen (voor app-beveiligingsbeleid) toewijzen|Yes|Yes|
|Apps toewijzen als beschikbaar|Ja|Yes|
|Apps toewijzen als vereist|Yes|Nee|
|Apps verwijderen|Ja|Yes|
|Eindgebruikers installeren beschikbare apps vanuit de bedrijfsportal-app|Yes|Nee|
|Eindgebruikers installeren beschikbare apps vanuit de bedrijfsportal-app op internet|Yes|Yes|

> [!NOTE]
> Op dit moment kunt u iOS- en Android-apps (beide Line-Of-Business-apps en apps die in de Store zijn gekocht) toewijzen aan apparaten die niet met Intune zijn ingeschreven.

## <a name="how-to-assign-an-app"></a>Een app toewijzen

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apps beheren** op de blade **Intune**.
1. Kies **Beheren** > **Apps** in de workload **Apps beheren**.
2. Kies de app die u wilt toewijzen op de blade met de lijst met apps.
3. Kies **Beheren** > **Toewijzingen** op de blade <*app-naam*> - **Overzicht**.
4. Kies **Groepen selecteren** en kies op de blade **Groepen selecteren** de Azure AD-groepen waaraan u de app wilt toewijzen.
5. Voor elke app die u kiest, moet u een **toewijzingstype** voor de app selecteren. U hebt de volgende mogelijkheden:
    - **Beschikbaar**: gebruikers installeren de app vanuit de bedrijfsportal-app of vanaf de website.
    - **Niet van toepassing**: de app wordt niet geïnstalleerd en niet weergegeven in de bedrijfsportal.
    - **Vereist**: de app wordt geïnstalleerd op apparaten in de geselecteerde groepen.
    - **Verwijderen**: de app wordt verwijderd van apparaten in de geselecteerde groepen.
    - **Beschikbaar met of zonder inschrijving**: deze app wordt toegewezen aan groepen met gebruikers van wie de apparaten niet zijn ingeschreven met Intune. Zie de tabel hierboven voor meer informatie.
6. Als u klaar bent, kiest u **Opslaan**.

De app is nu toegewezen aan de groep die u hebt gekozen.

Zie [How to monitor apps](monitor-apps.md) (Apps controleren) voor meer informatie over het controleren van app-toewijzingen.

