---
title: Op apps gebaseerd beleid voor voorwaardelijke toegang met Intune
description: In dit onderwerp wordt beschreven hoe u met Intune op apps gebaseerd beleid voor voorwaardelijke toegang kunt configureren.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 88db3730be62a9b481d924b4f09b70be775cb067
ms.sourcegitcommit: 4dc5bed94cc965a54eacac2d87fb2d49c9300c3a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/25/2017
---
# <a name="set-up-app-based-conditional-access-policies"></a>Op apps gebaseerd beleid voor voorwaardelijke toegang instellen

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

In dit onderwerp vindt u instructies voor het instellen van op apps gebaseerd beleid voor voorwaardelijke toegang voor apps die deel uitmaken van de lijst met goedgekeurde apps. De lijst met goedgekeurde apps bestaat uit apps die zijn getest door Microsoft.

> [!IMPORTANT]
> In dit onderwerp worden de stappen beschreven voor het toevoegen van een op apps gebaseerd beleid voor voorwaardelijke toegang met behulp van Exchange Online. U kunt dezelfde stappen echter gebruiken voor het toevoegen van andere apps uit de lijst met goedgekeurde apps, zoals SharePoint Online en Microsoft Teams.

## <a name="to-create-an-app-based-conditional-access-policy"></a>Op apps gebaseerd beleid voor voorwaardelijke toegang maken
1.  Ga naar [Azure Portal](https://portal.azure.com) en meld u aan met uw referenties.

2.  Kies **Meer services** en typ Intune.

3.  Kies **Intune-app-beveiliging**.

4.  Kies in de blade **Intune Mobile Application Management** de optie **Alle instellingen**.

5.  Kies in de sectie **Voorwaardelijke toegang** de optie **Exchange Online**.

    ![Schermafdruk van de blade Instellingen met de sectie voor voorwaardelijke toegang met de optie Exchange Online gemarkeerd](./media/MAM-conditional-access-1.png)

6. Kies in de blade **Toegestane apps** de optie **Apps met ondersteuning voor Intune-beleid toestaan** als alleen apps met ondersteuning voor Intune beveiligingsbeleid voor apps toegang mogen hebben tot Exchange Online. Wanneer u deze optie selecteert, wordt de lijst met ondersteunde apps weergegeven.

    > [!NOTE]
    > Alle Exchange Active Sync-e-mailclients, met inbegrip van de ingebouwde e-mailclients op iOS en Android die verbinding met Exchange Online maken, kunnen geen e-mail verzenden of ontvangen. In plaats daarvan ontvangen gebruikers één e-mailbericht dat ze de Outlook-e-mail-app moeten gebruiken.

7. Als u dit beleid wilt toepassen op gebruikers, opent u de blade **Beperkte gebruikersgroepen** en kiest u **Gebruikersgroep toevoegen**. Selecteer een of meer gebruikersgroepen waarop u dit beleid wilt toepassen.

    ![Schermafbeelding van de blade Beperkte gebruikersgroepen met de optie Gebruikersgroep toevoegen gemarkeerd](./media/mam-ca-add-user-group.png)

8. Mogelijk wilt u dat dit beleid niet wordt toegepast op bepaalde gebruikers in de gebruikersgroep die u in de vorige stap hebt geselecteerd. In dat geval voegt u die gebruikersgroepen toe aan de lijst met uitgesloten gebruikersgroepen. Kies in de blade **Exchange Online** de optie **Uitgesloten gebruikersgroepen**. Kies **Gebruikersgroep toevoegen** om de lijst met gebruikersgroepen te openen. Selecteer de groepen die u van dit beleid wilt uitsluiten.

## <a name="to-modify-or-delete-user-groups-from-an-existing-app-based-ca-policy"></a>Gebruikersgroepen aanpassen of verwijderen op basis van bestaand CA-beleid op basis van apps

1. Open de blade **Beperkte gebruikersgroepen** en markeer de gebruikersgroep die u wilt verwijderen.
2. Klik op de knop met weglatingstekens om de opties voor verwijderen weer te geven.
3. Kies **Verwijderen** om de gebruikersgroep uit de lijst te verwijderen.

## <a name="create-app-based-conditional-access-policies-in-azure-ad-workload"></a>Voorwaardelijk toegangsbeleid op basis van apps maken in Azure AD-werkbelasting

Vanaf versie 1708 van Intune kunnen IT-beheerders op apps gebaseerd voorwaardelijk toegangsbeleid maken uitgaande van de werkbelasting van Azure AD. Daardoor hoeft u niet te schakelen tussen Azure en de Intune-werkbelastingen.

> [!IMPORTANT]
> Als u beleid voor voorwaardelijke toegang voor Azure AD wilt instellen vanuit Intune Azure Portal, moet u een Azure AD Premium-licentie hebben.

### <a name="to-create-an-app-based-conditional-access-policy"></a>Op apps gebaseerd beleid voor voorwaardelijke toegang maken

> [!IMPORTANT]
> U moet [op apps gebaseerd beveiligingsbeleid voor Intune](app-protection-policies.md) hebben toegepast op uw apps voordat u op apps gebaseerd beleid voor voorwaardelijke toegang kunt gebruiken.

1. Kies in het**Intune-dashboard** **Voorwaardelijke toegang**.

2. Kies in de blade **Beleid** de optie **Nieuw beleid** om uw nieuwe op apps gebaseerd beleid voor voorwaardelijke toegang te maken.

4. Nadat u een naam voor het beleid hebt ingevoerd en de instellingen in de sectie **Toewijzingen** hebt geconfigureerd, kiest u **Verlenen** onder de sectie **Toegangscontroles**.

5. Kies **Goedgekeurde client-app vereisen** , kies **Selecteren** en kies vervolgens **OK** om het nieuwe beleid op te slaan.

## <a name="next-steps"></a>Volgende stappen
[Apps die geen gebruik maken van moderne verificatie blokkeren](app-modern-authentication-block.md)

### <a name="see-also"></a>Zie tevens

[App-gegevens beveiligen met app-beveiligingsbeleid](app-protection-policies.md)
[Voorwaardelijke toegang in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
