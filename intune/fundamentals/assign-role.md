---
title: Een rol aan een Intune-gebruiker toewijzen
description: Meer informatie over het toewijzen van ingebouwde of aangepaste rollen aan gebruikers in Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: pjain
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: c82805bf70259d43d738644e5663b93533bcb56a
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2019
ms.locfileid: "75207159"
---
# <a name="assign-a-role-to-an-intune-user"></a>Een rol aan een Intune-gebruiker toewijzen

U kunt een [ingebouwde](role-based-access-control.md#built-in-roles) of [aangepaste](create-custom-role.md) rol toewijzen aan een Intune-gebruiker.

Als u rollen wilt maken, bewerken of toewijzen, moet uw account een van de volgende machtigingen hebben in Azure AD:
- **Globale beheerder**
- **Intune-servicebeheerder**

1. Kies in het [Microsoft Endpoint Manager-beheercentrum ](https://go.microsoft.com/fwlink/?linkid=2109431)**Rollen** > **Alle rollen**.

2. Kies op de blade **Intune-rollen - Alle rollen** voor de ingebouwde rol die u wilt toewijzen.

3. Kies **Beheren** > **Toewijzingen** op de blade <*rolnaam*> - **Overzicht**.

4. Kies op de blade voor aangepaste rollen de optie **Toewijzen**.

5. Voer op de blade **Roltoewijzingen** een **Toewijzingsnaam** en desgewenst een **Beschrijving van toewijzing** in voor de toewijzing.

6. **Leden (groepen)** : kies de groep die de gebruiker bevat aan wie u de machtigingen wilt verlenen.

7. **Bereik (groepen)** : kies de groep die de gebruikers/apparaten bevat die het hierboven genoemde lid mag beheren.

8. **Bereik (tags)** : kies de tags waarop deze roltoewijzing moet worden toegepast.

9. Als u klaar bent, kiest u **OK**. De nieuwe toewijzing wordt in de lijst met toewijzingen weergegeven.


## <a name="next-steps"></a>Volgende stappen
- [Meer informatie over op rollen gebaseerd toegangsbeheer in Intune](role-based-access-control.md)
- [Een aangepaste rol maken](create-custom-role.md)
