---
title: Apps aan groepen toewijzen | Microsoft Docs
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: als u een app aan Intune hebt toegevoegd, wilt u deze wellicht toewijzen aan groepen met gebruikers of apparaten.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 1246ef539c044b894b4e4a93f449e60e6462600a
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017

---

# <a name="how-to-assign-apps-to-groups-with-microsoft-intune"></a>Apps aan groepen toewijzen met Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

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
|Apps verwijderen|Yes|Nee|
|Eindgebruikers installeren beschikbare apps vanuit de bedrijfsportal-app|Yes|Nee|
|Eindgebruikers installeren beschikbare apps vanuit de bedrijfsportal-app op internet|Yes|Yes|

> [!NOTE]
> Op dit moment kunt u iOS- en Android-apps (beide Line-Of-Business-apps en apps die in de Store zijn gekocht) toewijzen aan apparaten die niet met Intune zijn ingeschreven.

## <a name="changes-to-how-you-assign-apps-to-groups-in-the-intune-preview"></a>Wijzigingen in hoe u apps toewijst aan groepen in de preview-versie van Intune

In de preview-versie van Intune Azure wijst u apps niet langer toe aan Intune-groepen, maar gebruikt u beveiligingsgroepen van Azure Active Directory (Azure AD). Daarom is het van belang dat u weet hoe sommige wijzigingen in app-toewijzingen werken, met name als u apps hebt toegewezen aan onderliggende groepen in Intune.
Het belangrijkste om te onthouden, is dat onderliggende groepen niet bestaan in Azure AD. Maar sommige groepen kunnen wel dezelfde leden bevatten. In dit geval verschilt het gedrag van de klassieke versie van Intune en de preview-versie van Intune Azure. Dit wordt weergegeven in de volgende tabel:

||||||
|-|-|-|-|-|
|**Klassieke versie van Intune (vóór de tenantmigratie)**|-|**Intune Azure (na voltooiing van de tenantmigratie)**|-|**Meer informatie**|
|**Toewijzingsopzet bovenliggende groepen**|**Toewijzingsopzet onderliggende groepen**|**Resulterende toewijzingsopzet voor gedeelde leden van eerdere bovenliggende en onderliggende groep**|**Resulterende toewijzingsopzetactie voor leden van bovenliggende groep**|-|
|Beschikbaar|Vereist|Vereist en beschikbaar|Beschikbaar|Vereist en beschikbaar betekent dat apps die zijn toegewezen als Vereist ook worden weergegeven in de Bedrijfsportal-app.
|Niet van toepassing|Beschikbaar|Niet van toepassing|Niet van toepassing|Tijdelijke oplossing: verwijder de toewijzingsopzet Niet van toepassing uit de bovenliggende groep in Intune.
|Vereist|Beschikbaar|Vereist en beschikbaar|Vereist|-|
|Vereist en beschikbaar<sup>1</sup>|Beschikbaar|Vereist en beschikbaar|Vereist en beschikbaar|-|
|Vereist|Niet van toepassing|Vereist|Vereist|-|
|Vereist en beschikbaar|Niet van toepassing|Vereist en beschikbaar|Vereist en beschikbaar|-|
|Vereist|Verwijderen|Vereist|Vereist|-|
|Vereist en beschikbaar|Verwijderen|Vereist en beschikbaar|Vereist en beschikbaar|-|
<sup>1</sup> Alleen voor beheerde iOS Store-apps: wanneer u deze toevoegt aan Intune en toewijst als Vereist, worden ze automatisch gemaakt met zowel de opzet Vereist als Beschikbaar.

U kunt de volgende acties ondernemen om toewijzingsconflicten te voorkomen:

1.    Als u voorheen apps toewees aan verwante bovenliggende en onderliggende groepen in Intune, kunt u deze toewijzingen verwijderen voordat de migratie van uw tenant begint.
2.    Verwijder de onderliggende groepen uit de bovenliggende groepen, en maak een nieuwe groep die de leden van de voormalige onderliggende groep bevat. Vervolgens kunt u een nieuwe app-toewijzing aan deze groep maken.
Opmerking: als de vorige bovenliggende groep ‘Alle gebruikers’ was, moet u een nieuwe dynamische groep maken die niet de leden van de onderliggende groep bevat.
Als u wijzigingen wilt aanbrengen in zowel gebruikers- als apparaatgroepen, doet u dat in de [Azure Portal](https://portal.azure.com/). In de [klassieke Azure Portal](https://manage.windowsazure.com/) kunt u alleen wijzigingen aanbrengen in gebruikersgroepen.


## <a name="how-to-assign-an-app"></a>Een app toewijzen

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Mobiele apps** op de blade **Intune**.
1. Kies **Beheren** > **Apps** in de workload **Mobiele apps**.
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

Zie [How to monitor apps](apps-monitor.md) (Apps controleren) voor meer informatie over het controleren van app-toewijzingen.

