---
ms.openlocfilehash: 6ec8f8a613d3b0a0b17f2615de634e70fa282fd7
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2019
ms.locfileid: "68229320"
---
<!-- This include is part of the Intune Data Warehouse documentation. -->

## <a name="azure-ad-and-intune-credential-requirements"></a>Azure AD en Intune-referentievereisten

Verificatie en autorisatie zijn gebaseerd op Azure AD-referenties en Intune RBAC (Role-Based Access Control, op rollen gebaseerd toegangsbeheer). Alle globale beheerders en Intune-servicebeheerders voor uw tenant hebben standaard toegang tot het datawarehouse. Gebruik Intune-rollen om toegang te bieden voor meer gebruikers door hen toegang tot de **Intune-datawarehouse**-resource te verlenen.

De vereisten voor toegang tot het Intune-datawarehouse (inclusief de API) zijn:

- Gebruiker moet een van de volgende zijn:
  - Globale Azure AD-beheerder
  - Een Intune-servicebeheerder
  - Gebruiker met op rollen gebaseerde toegang tot de **Intune-datawarehouse**-resource
  - Verificatie zonder gebruiker via [verificatie via alleen de toepassing](../data-warehouse-app-only-auth.md) 
