---
title: Een rol aan een Intune-gebruiker toewijzen
description: Meer informatie over het toewijzen van ingebouwde of aangepaste rollen aan gebruikers in Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/26/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: a59c413fcc11dfce76152a7325517703a71785d2
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/23/2019
ms.locfileid: "61508173"
---
# <a name="assign-a-role-to-an-intune-user"></a>Een rol aan een Intune-gebruiker toewijzen

U kunt een [ingebouwde](role-based-access-control.md#built-in-roles) of [aangepaste](create-custom-role.md) rol toewijzen aan een Intune-gebruiker.

Als u rollen wilt maken, bewerken of toewijzen, moet uw account een van de volgende machtigingen hebben in Azure AD:
- **Globale beheerder**
- **Intune-servicebeheerder**

Zie [Intune RBAC-tabel](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) voor een volledige lijst met de machtigingen voor elke ingebouwde rol.

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).

2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.

3. Kies op de blade **Intune** voor de optie **Rollen** > **Alle rollen**.

4. Kies op de blade **Intune-rollen - Alle rollen** voor de ingebouwde rol die u wilt toewijzen.

5. Kies **Beheren** > **Toewijzingen** op de blade <*rolnaam*> - **Overzicht**.

6. Kies op de blade voor aangepaste rollen de optie **Toewijzen**.

7. Voer op de blade **Roltoewijzingen** een **Toewijzingsnaam** en desgewenst een **Beschrijving van toewijzing** in voor de toewijzing.

8. **Leden (groepen)**: kies de groep die de gebruiker bevat aan wie u de machtigingen wilt verlenen.

9. **Bereik (groepen)**: kies de groep die de gebruikers/apparaten bevat die het hierboven genoemde lid mag beheren.

10. **Bereik (tags)**: kies de tags waarop deze roltoewijzing moet worden toegepast.

11. Als u klaar bent, kiest u **OK**. De nieuwe toewijzing wordt in de lijst met toewijzingen weergegeven.


## <a name="next-steps"></a>Volgende stappen
- [Meer informatie over op rollen gebaseerd toegangsbeheer in Intune](role-based-access-control.md)
- [Een aangepaste rol maken](create-custom-role.md)
