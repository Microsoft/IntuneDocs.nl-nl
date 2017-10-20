---
title: Op apps gebaseerd beleid voor voorwaardelijke toegang maken voor SharePoint Online
description: 
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 531b09bb-ddfd-498f-8ee3-6675d2466208
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.openlocfilehash: 4183df8e8ed982e7aba2d55d82923564f215ad53
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/10/2017
---
# <a name="set-up-app-based-conditional-access-ca-policies-for-sharepoint-online"></a>Op apps gebaseerd CA-beleid (Conditional Access; voorwaardelijke toegang) maken voor SharePoint Online

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Dit onderwerp bevat richtlijnen voor het instellen van op apps gebaseerd CA-beleid (beleid voor voorwaardelijke toegang) voor SharePoint Online. Beheerders kunnen er met op apps gebaseerde CA voor zorgen dat alleen mobiele apps waarop Intune-beleid voor de beveiliging van apps is toegepast, worden toegestaan.

## <a name="to-create-the-app-based-ca-policy-for-sharepoint-online"></a>Een CA-beleid voor SharePoint Online maken dat is gebaseerd op apps

1. Ga naar [Azure Portal](https://portal.azure.com) en meld u aan met uw referenties.

    > [!NOTE]
    > Lees eerst het onderwerp [Azure Portal voor beveiligingsbeleid voor apps](azure-portal-for-microsoft-intune-mam-policies.md) als u nog niet bekend bent met Azure Portal.

2. Kies **Meer services** in het linkermenu en typ dan **Intune** in het vak tekstfilter.

3. Kies **Intune App Protection** > **Intune mobiel applicatiebeheer** > **Alle instellingen**.

4. Kies op de blade Intune Mobile Application Management de tegel SharePoint Online.

5. Kies in de blade **Toegestane apps** de optie **Apps met ondersteuning voor Intune-beleid toestaan** om alleen apps toe te staan die worden ondersteund door Intune-beleid voor de beveiliging van apps.

    > [!NOTE] 
    > Wanneer u de optie selecteert om alleen apps toe te staan die worden ondersteund door Intune-beleid voor de beveiliging van apps, wordt **alleen** de lijst met ondersteunde apps weergegeven.

    ![Schermafbeelding van de blade met toegestane apps en de lijst met apps](../media/mam-ca-spo-allowed-apps.png)

## <a name="to-assign-app-based-ca-policies-to-your-users"></a>CA-beleid op basis van apps toewijzen aan uw gebruikers

1. Open de blade **Beperkte gebruikersgroepen** en kies vervolgens **Een gebruikersgroep toevoegen**.

2. Selecteer een of meer gebruikersgroepen waarop u dit beleid wilt toepassen.

    ![Schermafbeelding van de blade Beperkte gebruikersgroepen met de optie Gebruikersgroep toevoegen gemarkeerd](../media/mam-ca-spo-restricted-groups.png)

    > [!IMPORTANT] 
    > Mogelijk wilt u dat dit beleid niet wordt toegepast op bepaalde gebruikers in de gebruikersgroep die u in de vorige stap hebt geselecteerd. In dat geval voegt u die gebruikersgroepen toe aan de lijst met uitgesloten gebruikersgroepen. 

3. Kies op de blade **SharePoint Online** de optie **Uitgesloten gebruikersgroepen** en kies vervolgens **Een gebruikersgroep toevoegen** om de lijst met gebruikersgroepen te openen.

4. Selecteer de groepen die u van dit beleid wilt uitsluiten.  

## <a name="to-modify-or-delete-user-groups-from-an-existing-app-based-ca-policy"></a>Gebruikersgroepen aanpassen of verwijderen op basis van bestaand CA-beleid op basis van apps

1. Open de blade **Beperkte gebruikersgroepen** en markeer de gebruikersgroep die u wilt verwijderen.
2. Klik op de knop met weglatingstekens om de opties voor verwijderen weer te geven.
3. Kies **Verwijderen** om de gebruikersgroep uit de lijst te verwijderen.

> [!NOTE] 
> U kunt dezelfde stappen volgen als voor het verwijderen van een gebruikersgroep uit de lijst met **uitgesloten gebruikersgroepen**.

## <a name="next-steps"></a>Volgende stappen

[Apps die geen gebruik maken van moderne verificatie blokkeren](block-apps-with-no-modern-authentication.md)

## <a name="see-also"></a>Zie tevens

[Beveilig app-gegevens met beveiligingsbeleid voor apps](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[Op apps gebaseerd CA-beleid configureren voor Exchange Online](mam-ca-for-exchange-online.md)
