---
ms.openlocfilehash: 8483ed3d4198e228bdaaf4723b2c9c0dca9cecfc
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "71830514"
---
<!-- This include is part of the Intune Data Warehouse documentation. -->

## <a name="azure-ad-and-intune-credential-requirements"></a>Azure AD en Intune-referentievereisten

Verificatie en autorisatie zijn gebaseerd op Azure AD-referenties en Intune RBAC (Role-Based Access Control, op rollen gebaseerd toegangsbeheer). Alle globale beheerders en Intune-servicebeheerders voor uw tenant hebben standaard toegang tot het datawarehouse. Gebruik Intune-rollen om toegang te bieden voor meer gebruikers door hen toegang tot de **Intune-datawarehouse**-resource te verlenen.

De vereisten voor toegang tot het Intune-datawarehouse (inclusief de API) zijn:

- Gebruiker moet een van de volgende zijn:
  - Globale Azure AD-beheerder
  - Een Intune-servicebeheerder
  - Gebruiker met op rollen gebaseerde toegang tot de **Intune-datawarehouse**-resource
  - Verificatie zonder gebruiker via [verificatie via alleen de toepassing](../developer/data-warehouse-app-only-auth.md) 
