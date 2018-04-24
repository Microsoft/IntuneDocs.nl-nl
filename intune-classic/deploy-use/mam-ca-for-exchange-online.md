---
title: App-toegang voor Exchange Online
description: In dit onderwerp wordt beschreven hoe u een beleid voor voorwaardelijke toegang voor MAM-apps kunt configureren.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 10/15/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f2cd1a1f-fd29-4081-8dfa-c40993a107d5
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a64a5ac7f10bb7988c75dd473e1e87dae03959d4
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="create-an-exchange-online-conditional-access-to-only-allow-apps-supported-by-mam"></a>Beleid voor voorwaardelijke toegang maken zodat alleen apps die worden ondersteund door MAM toegang hebben tot Exchange Online

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Dit onderwerp bevat stapsgewijze instructies over het instellen van voorwaardelijke toegang voor Exchange Online zodat alleen mobiele apps die ondersteuning bieden voor Intune beveiligingsbeleid voor apps worden toegestaan.


## <a name="create-an-exchange-online-policy"></a>Beleid voor Exchange Online maken
1.  Meld u aan bij de [Azure-portal](https://portal.azure.com) waarin de functie voor app-toegang is opgenomen. Lees eerst het onderwerp [Azure-portal voor beveiligingsbeleid voor apps](azure-portal-for-microsoft-intune-mam-policies.md) als u nog niet bekend bent met de Azure-portal.

2.  Kies **Meer services** en typ Intune.

3.  Kies **Intune-app-beveiliging**.

4.  Kies in de blade **Intune Mobile Application Management** de optie **Alle instellingen**.

5.  Kies in de sectie **Voorwaardelijke toegang** de optie **Exchange Online**.

    ![Schermafdruk van de blade Instellingen met de sectie voor voorwaardelijke toegang met de optie Exchange Online gemarkeerd](../media/MAM-conditional-access-1.png)

6. Kies in de blade **Toegestane apps** de optie **Apps met ondersteuning voor Intune-beleid toestaan** als alleen apps met ondersteuning voor Intune beveiligingsbeleid voor apps toegang mogen hebben tot Exchange Online. Wanneer u deze optie selecteert, wordt de lijst met ondersteunde apps weergegeven.

    >[!NOTE]
    >Alle Exchange Active Sync-e-mailclients, met inbegrip van de ingebouwde e-mailclients op iOS en Android die verbinding met Exchange Online maken, kunnen geen e-mail verzenden of ontvangen. In plaats daarvan ontvangen gebruikers één e-mailbericht dat ze de Outlook-e-mail-app moeten gebruiken.

7. Als u dit beleid wilt toepassen op gebruikers, opent u de blade **Beperkte gebruikersgroepen** en kiest u **Gebruikersgroep toevoegen**. Selecteer een of meer gebruikersgroepen waarop u dit beleid wilt toepassen.

    ![Schermafbeelding van de blade Beperkte gebruikersgroepen met de optie Gebruikersgroep toevoegen gemarkeerd](../media/mam-ca-add-user-group.png)

8. Mogelijk wilt u dat dit beleid niet wordt toegepast op bepaalde gebruikers in de gebruikersgroep die u in de vorige stap hebt geselecteerd. In dat geval voegt u die gebruikersgroepen toe aan de lijst met uitgesloten gebruikersgroepen. Kies in de blade **Exchange Online** de optie **Uitgesloten gebruikersgroepen**. Kies **Gebruikersgroep toevoegen** om de lijst met gebruikersgroepen te openen. Selecteer de groepen die u van dit beleid wilt uitsluiten.  

## <a name="modify-an-existing-policy"></a>Bestaand beleid wijzigen
### <a name="add-or-delete-user-groups"></a>Gebruikersgroepen toevoegen of verwijderen

Als u **een gebruikersgroep wilt verwijderen** uit de lijst met **beperkte gebruikersgroepen**, opent u de blade **Beperkte gebruikersgroepen** en markeert u de gebruikersgroep die u wilt verwijderen. Klik vervolgens op het **beletselteken (...)** om de optie **Verwijderen** weer te geven. Kies **Verwijderen** om de gebruikersgroep uit de lijst te verwijderen. U kunt dezelfde procedure volgen als u een gebruikersgroep uit de lijst met **uitgesloten gebruikersgroepen** wilt verwijderen.


## <a name="next-steps"></a>Volgende stappen
[Apps die geen gebruik maken van moderne verificatie blokkeren](block-apps-with-no-modern-authentication.md)
### <a name="see-also"></a>Zie ook
[Beveilig app-gegevens met beveiligingsbeleid voor apps](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
