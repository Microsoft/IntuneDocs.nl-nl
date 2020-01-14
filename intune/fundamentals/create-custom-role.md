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
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: pjain
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 68c2dc7df123593513c14e16e2626c7426f50b01
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2019
ms.locfileid: "75207414"
---
# <a name="create-a-custom-role-in-intune"></a>Een aangepaste rol in Intune maken

U kunt een aangepaste Intune-rol maken die alle machtigingen bevat die vereist zijn voor een bepaalde taakfunctie. Als een groep van de IT-afdeling bijvoorbeeld toepassingen, beleidsregels en configuratieprofielen beheert, kunt u al deze machtigingen samenvoegen tot één aangepaste rol. Nadat u een aangepaste rol hebt gemaakt, kunt u deze [toewijzen](assign-role.md) aan elke gebruiker die die machtigingen nodig heeft.

Als u rollen wilt maken, bewerken of toewijzen, moet uw account een van de volgende machtigingen hebben in Azure AD:
- **Globale beheerder**
- **Intune-servicebeheerder**

## <a name="to-create-a-custom-role"></a>Een aangepaste rol maken

1. Kies in het [Microsoft Endpoint Manager-beheercentrum ](https://go.microsoft.com/fwlink/?linkid=2109431)**Rollen** > **Alle rollen** > **Toevoegen**.

2. Voer op de blade **Aangepaste rol toevoegen** een naam en beschrijving in voor de nieuwe rol en klik vervolgens op **Machtigingen**.

3. Kies op de blade **Machtigingen** de machtigingen die u voor deze rol wilt gebruiken.

4. Kies op de blade **Bereik (tags)** de tags voor deze rol. Deze rol heeft toegang tot resources waaraan deze tags ook zijn toegevoegd.

5. Als u klaar bent, kiest u **OK**.

6. Klik op de blade **Aangepaste rol toevoegen** op **Maken**. De nieuwe rol wordt weergegeven in de lijst op de blade **Intune-rollen - Alle rollen**.


## <a name="copy-a-role"></a>Een rol kopiëren

U kunt ook een bestaande rol kopiëren.

1. Kies in het [Microsoft Endpoint Manager-beheercentrum ](https://go.microsoft.com/fwlink/?linkid=2109431)**Rollen** > **Alle rollen** > selecteer een rol in de lijst > **Dupliceren**.

2. Voer onder **Rol dupliceren** een naam in. Zorg ervoor dat u een unieke naam gebruikt.

3. Alle machtigingen en bereiktags van de oorspronkelijke rol zijn al geselecteerd. U kunt vervolgens de **naam**, **beschrijving**, **machtigingen** en **bereik(tags)** van de dubbele rol wijzigen.

4. Selecteer **Maken**. 

## <a name="next-steps"></a>Volgende stappen
- [Een rol toewijzen aan een gebruiker](assign-role.md)
- [Meer informatie over op rollen gebaseerd toegangsbeheer in Intune](role-based-access-control.md)
