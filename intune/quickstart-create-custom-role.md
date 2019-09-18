---
title: 'Snelstart: een aangepaste rol maken en toewijzen in Intune'
description: 'Snelstart: een aangepaste rol maken en toewijzen aan een externe apparaatbeheerder.'
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.localizationpriority: high
ms.topic: quickstart
ms.date: 03/26/2019
ms.author: erikje
ms.reviewer: pjain
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: f63bbc80c055cfcb3bd52f79e7b810094107ec2a
ms.sourcegitcommit: d2989b9992d10d133573d9bc31479659fb7e242c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/18/2019
ms.locfileid: "71080045"
---
# <a name="quickstart-create-and-assign-a-custom-role"></a>Quickstart: Een aangepaste rol maken en toewijzen

In deze Intune-snelstart maakt u een aangepaste rol met specifieke machtigingen voor een beveiligingsafdeling. U wijst de rol vervolgens toe aan een groep operators. Er zijn enkele standaardrollen die u direct kunt gebruiken. Als u echter aangepaste rollen zoals deze maakt, kunt u de toegang tot alle onderdelen van uw Mobile Device Management-systeem exact beheren.

Als u niet over een Intune-abonnement beschikt, kunt u [zich registreren voor een gratis proefaccount](free-trial-sign-up.md).

## <a name="prerequisites"></a>Vereisten

- Als u de stappen in deze snelstart wilt uitvoeren, moet u eerst [een groep maken](quickstart-create-group.md).

## <a name="sign-in-to-intune"></a>Aanmelden bij Intune

Meld u aan bij [Intune](https://aka.ms/intuneportal) als globale beheerder of beheerder van een Intune-service. Als u een Intune-proefabonnement hebt gemaakt, is het account waarmee u het abonnement hebt gemaakt de globale beheerder.

## <a name="create-a-custom-role"></a>Een aangepaste rol maken

Tijdens het maken van een aangepaste rol kunt u machtigingen instellen voor een groot aantal acties. Voor de rol Beveiligingsbewerkingen stelt u enkele leesmachtigingen in zodat de operator de configuratie en de beleidsregels van een apparaat kan bekijken.

1. Kies in Intune **Rollen** > **Alle rollen** > **Toevoegen**.
![Browser](media/quickstart-create-custom-role/add-custom-role.png)
2. Bij **Aangepaste rol toevoegen** voert u in het vak **Naam** *Beveiligingsbewerkingen* in.
3. In het vak **Beschrijving** voert u het volgende in: *Met deze rol kan een beveiligingsoperator de apparaatconfiguratie- en -nalevingsinformatie bewaken.*
4. Kies **Configureren** > **Bedrijfsapparaat-id's** > **Ja** naast **Lezen** > **OK**.
![Browser](media/quickstart-create-custom-role/corp-device-id-read.png)
5. Kies **Apparaatnalevingsbeleid** > **Ja** naast **Lezen** > **OK**.
6. Kies **Apparaatconfiguraties** > **Ja** naast **Lezen** > **OK**.
7. Kies **Organisatie** > **Ja** naast **Lezen** > **OK**.
8. Kies **OK** > **Maken**.

## <a name="assign-the-role-to-a-group"></a>De rol toewijzen aan een groep

Voordat de beveiligingsoperator gebruik kan maken van de nieuwe machtigingen moet u de rol toewijzen aan een groep die de beveiligingsgebruiker bevat.

1. Kies in Intune **Rollen** > **Alle rollen** > **Beveiligingsbewerkingen**.
2. Bij **Intune-rollen** kiest u **Toewijzingen** > **Toewijzen**.
3. In het vak **Toewijzingsnaam** voert u *Sec ops* in.
4. Kies **Lid (groepen)**  > **Toevoegen**.
5. Kies de groep **Contoso Testers**.
6. Kies **Selecteren** > **OK**.
7. Kies **Bereik (groepen)**  > **Selecteer groepen om op te nemen** > **Contoso Testers**.
8. Kies **Selecteren** > **OK** > **OK**.

Iedereen in de groep is nu lid van de rol *Beveiligingsbewerkingen* en kan de volgende informatie van een apparaat bekijken: bedrijfsapparaat-id's, beleidsregels voor naleving, apparaatconfiguraties en bedrijfsinformatie.

## <a name="clean-up-resources"></a>Resources opschonen

Als u de aangepaste rol niet meer wilt gebruiken, kunt u deze verwijderen. Kies **Rollen** > **Alle rollen** > kies het beletselteken naast de rol > **Verwijderen**.

## <a name="next-steps"></a>Volgende stappen

In deze snelstart hebt u een aangepaste rol voor beveiligingsmedewerkers gemaakt en deze toegewezen aan een groep. Zie [Op rollen gebaseerd toegangsbeheer (RBAC) met Intune](role-based-access-control.md) voor meer informatie over rollen in Intune

Als u deze reeks snelstartgidsen voor Intune wilt volgen, kunt u doorgaan met de volgende snelstartgids.

> [!div class="nextstepaction"]
> [Quickstart: Een e-mailprofiel voor een apparaat voor iOS maken](quickstart-email-profile.md)
