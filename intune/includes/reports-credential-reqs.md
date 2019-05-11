---
ms.openlocfilehash: 015e50d24149a6b6242eda86d5f3d62489e9955d
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 04/23/2019
ms.locfileid: "61511326"
---
<!-- This include is part of the Intune Data Warehouse documentation. -->

## <a name="azure-ad-and-intune-credential-requirements"></a>Azure AD en Intune-referentievereisten

Verificatie en autorisatie zijn gebaseerd op Azure AD-referenties en Intune RBAC (Role-Based Access Control, op rollen gebaseerd toegangsbeheer). Alle globale beheerders en Intune-servicebeheerders voor uw tenant hebben standaard toegang tot het datawarehouse. Gebruik Intune-rollen om toegang te bieden voor meer gebruikers door hen toegang tot de **Intune-datawarehouse**-resource te verlenen.

De vereisten voor toegang tot het Intune-datawarehouse (inclusief de API) zijn:

  -  Gebruiker moet een van de volgende zijn:
      -  Globale Azure AD-beheerder
      -  Een Intune-servicebeheerder
      -  Gebruiker met op rollen gebaseerde toegang tot de **Intune-datawarehouse**-resource
      -  Verificatie zonder gebruiker via [verificatie via alleen de toepassing](../data-warehouse-app-only-auth.md) 
