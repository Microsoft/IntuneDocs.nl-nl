---
title: App-toegang tot SharePoint Online configureren
description: 
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 531b09bb-ddfd-498f-8ee3-6675d2466208
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: 992273f88e4bbe234f11f936d6416dbaf0d394e9
ms.lasthandoff: 04/19/2017


---

# <a name="create-a-sharepoint-online-conditional-access-policy-to-only-allow-apps-supported-by-mam"></a>Beleid voor voorwaardelijke toegang maken zodat alleen apps die worden ondersteund door MAM toegang hebben tot SharePoint Online
Dit onderwerp bevat stapsgewijze instructies over het instellen van voorwaardelijke toegang voor Exchange Online zodat alleen mobiele apps die ondersteuning bieden voor Intune MAM-beleidsregels (Mobile App Management).

## <a name="configure-a-sharepoint-online-policy"></a>Een SharePoint Online-beleid configureren
**Stap 1**: aanmelden bij [Azure Portal](https://portal.azure.com) waarin de functie voor app-toegang is opgenomen. Lees eerst het onderwerp [Azure-portal voor MAM-beleid](azure-portal-for-microsoft-intune-mam-policies.md) als u nog niet bekend met de Azure-portal.

**Stap 2**: ga naar **Bladeren > Intune > blade Intune mobile application management > Instellingen**. Kies vervolgens in de sectie voor **voorwaardelijke toegang** de optie **SharePoint Online**.

![Schermafbeelding van de instellingenblade met het gedeelte voor voorwaardelijke toegang en de blade SharePoint Online geopend](../media/mam-ca-settings-spo.png)

**Stap 3**: kies in de blade **Toegestane apps** de optie **Apps met ondersteuning voor Intune-beleid toestaan** om alleen apps met ondersteuning voor Intune MAM-beleid toegang te bieden tot SharePoint Online. Wanneer u de optie selecteert om alleen apps toe te staan die worden ondersteund door Intune MAM-beleid, wordt de lijst met ondersteunde apps weergegeven.

![Schermafbeelding van de blade met toegestane apps en de lijst met apps](../media/mam-ca-spo-allowed-apps.png)

**Stap 4**: als u dit beleid wilt toepassen op gebruikers, opent u de blade **Beperkte gebruikersgroepen** en kiest u **Gebruikersgroep toevoegen**. Selecteer een of meer gebruikersgroepen waarop u dit beleid wilt toepassen.

![Schermafbeelding van de blade Beperkte gebruikersgroepen met de optie Gebruikersgroep toevoegen gemarkeerd](../media/mam-ca-spo-restricted-groups.png)


**Stap 5**: mogelijk wilt u dat dit beleid niet wordt toegepast op bepaalde gebruikers in de gebruikersgroep die u in de vorige stap hebt geselecteerd. In dat geval voegt u die gebruikersgroepen toe aan de lijst met uitgesloten gebruikersgroepen. Kies in de blade **SharePoint Online** de optie **Uitgesloten gebruikersgroepen**. Kies **Gebruikersgroep toevoegen** om de lijst met gebruikersgroepen te openen. Selecteer de groepen die u van dit beleid wilt uitsluiten.  

## <a name="modifying-an-existing-policy"></a>Een bestaand beleid wijzigen
### <a name="adding-or-deleting-user-groups"></a>Gebruikersgroepen toevoegen of verwijderen
Als u **een gebruikersgroep wilt verwijderen** uit de lijst met **beperkte gebruikersgroepen**, opent u de blade Beperkte gebruikersgroepen en markeert u de gebruikersgroep die u wilt verwijderen. Klik vervolgens op ... om de verwijderingsoptie te zien. Kies **Verwijderen** om de gebruikersgroep uit de lijst te verwijderen. U kunt dezelfde procedure volgen als u een gebruikersgroep uit de lijst met **uitgesloten gebruikersgroepen** wilt verwijderen.


## <a name="next-steps"></a>Volgende stappen
[App-toegang configureren voor Exchange Online](mam-ca-for-exchange-online.md)

[Apps die geen gebruik maken van moderne verificatie blokkeren](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>Zie tevens

[App-gegevens beveiligen met MAM-beleid](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

