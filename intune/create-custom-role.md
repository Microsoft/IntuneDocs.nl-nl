---
title: Een aangepaste rol in Intune maken
description: Leer hoe u een aangepaste rol maakt in Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: pjain
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 10366a41be05dbedee5cd84a1222a727a02a1b93
ms.sourcegitcommit: 74911a263944f2dbd9b754415ccda6c68dae0759
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2019
ms.locfileid: "71071464"
---
# <a name="create-a-custom-role-in-intune"></a>Een aangepaste rol in Intune maken

U kunt een aangepaste Intune-rol maken die alle machtigingen bevat die vereist zijn voor een bepaalde taakfunctie. Als een groep van de IT-afdeling bijvoorbeeld toepassingen, beleidsregels en configuratieprofielen beheert, kunt u al deze machtigingen samenvoegen tot één aangepaste rol. Nadat u een aangepaste rol hebt gemaakt, kunt u deze [toewijzen](assign-role.md) aan elke gebruiker die die machtigingen nodig heeft.

Als u rollen wilt maken, bewerken of toewijzen, moet uw account een van de volgende machtigingen hebben in Azure AD:
- **Globale beheerder**
- **Intune-servicebeheerder**

## <a name="to-create-a-custom-role"></a>Een aangepaste rol maken

1. Meld u aan bij [Azure Portal](https://portal.azure.com) met uw Intune-referenties.

2. Kies **Alle services** in het linkermenu en typ dan **Intune** in het filtertekstvak.

3. Kies **Intune** > **Rollen** > **Alle rollen** > **Toevoegen**.

4. Voer op de blade **Aangepaste rol toevoegen** een naam en beschrijving in voor de nieuwe rol en klik vervolgens op **Machtigingen**.

5. Kies op de blade **Machtigingen** de machtigingen die u voor deze rol wilt gebruiken. Gebruik de [Intune RBAC-tabel](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) om te bepalen welke machtigingen u wilt toepassen.

6. Kies op de blade **Bereik (tags)** de tags voor deze rol. Deze rol heeft toegang tot resources waaraan deze tags ook zijn toegevoegd.

7. Als u klaar bent, kiest u **OK**.

8. Klik op de blade **Aangepaste rol toevoegen** op **Maken**. De nieuwe rol wordt weergegeven in de lijst op de blade **Intune-rollen - Alle rollen**.

## <a name="next-steps"></a>Volgende stappen
- [Een rol toewijzen aan een gebruiker](assign-role.md)
- [Meer informatie over op rollen gebaseerd toegangsbeheer in Intune](role-based-access-control.md)
