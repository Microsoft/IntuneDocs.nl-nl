---
title: 'Snelstartgids: App-beveiligingsbeleid maken en toewijzen'
titleSuffix: Microsoft Intune
description: In deze snelstartgids gebruikt u Microsoft Intune om een beveiligingsbeleid voor apps te maken en toe te wijzen.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/26/2019
ms.topic: quickstart
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2586fce0-5dca-4686-b9c4-791778838401
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6ec42d122bf3da3fbacef513d6af2dbe124b196c
ms.sourcegitcommit: 7315fe72b7e55c5dcffc6d87f185f3c2cded9028
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/02/2019
ms.locfileid: "67530773"
---
# <a name="quickstart-create-and-assign-an-app-protection-policy"></a>Quickstart: Beveiligingsbeleid voor apps maken en toewijzen

In deze snelstartgids gaat u met Intune app-beveiligingsbeleid maken en aan een client-app op een apparaat van een eindgebruiker toewijzen. Intune maakt gebruik van app-beveiligingsbeleid om te controleren dat uw apps aan de beveiligingsvereisten voor de gegevens van uw organisatie voldoen.

Als u niet over een Intune-abonnement beschikt, kunt u [zich registreren voor een gratis proefaccount](free-trial-sign-up.md).

## <a name="prerequisites"></a>Vereisten

- Als u deze snelstartgids wilt uitvoeren, moet u [een gebruiker maken](quickstart-create-user.md), [een groep maken](quickstart-create-group.md), [een apparaat inschrijven](quickstart-setup-auto-enrollment.md) en [een app toevoegen en toewijzen](quickstart-add-assign-app.md).

## <a name="sign-in-to-intune"></a>Aanmelden bij Intune

Meld u aan bij [Intune](https://aka.ms/intuneportal) als [globale beheerder of Intune-servicebeheerder](users-add.md#types-of-administrators). Als u een Intune-proefabonnement hebt gemaakt, is het account waarmee u het abonnement hebt gemaakt de globale beheerder.

## <a name="create-an-app-protection-policy"></a>Beveiligingsbeleid voor apps maken

Gebruik de volgende stappen om een app-beveiligingsbeleid te maken:

1. Selecteer in [Intune](https://aka.ms/intuneportal) **Client-apps** > **App-beveiligingsbeleid** > **Beleid maken**. 
2. Voer de volgende gegevens in: 

    - **Naam**: *Inhoudsbeveiliging Windows 10*
    - **Beschrijving**: *Gebruikers die zijn gekoppeld aan dit beleid kunnen niet inhoud van de toegewezen app knippen/plakken of naar andere niet-beheerde apps op het apparaat kopiëren en omgekeerd.*
    - **Platform**: *Windows 10*
    - **Status van de inschrijving**: *Ingeschreven*

3. Selecteer **Beveiligde apps** om de apps te kiezen die aan dit beleid moeten voldoen.
4. Klik op **Apps toevoegen**.
5. Selecteer onder **Aanbevolen apps** **Word Mobiel**.
5. Klik op **OK** > **OK**. 
6. Selecteer **Vereiste instellingen** om de app te configureren.
7. Klik op **Onderdrukkingen toestaan** om de modus Windows Information Protection in te stellen. Als u deze optie selecteert, wordt voorkomen dat bedrijfsgegevens uit de beveiligde app worden gehaald.
8. Klik op **OK** > **Maken**.

U ziet nu het app-beveiligingsbeleid in Intune.

### <a name="assign-the-app-protection-policy"></a>Beveiligingsbeleid voor apps toewijzen

Nadat u beveiligingsbeleid voor apps in Intune hebt gemaakt, kunt u dit toewijzen aan groepen. 

Gebruik de volgende stappen om beveiligingsbeleid voor apps toe te wijzen:

1. Selecteer in [Intune](https://aka.ms/intuneportal) **Intune** > **Client-apps** > **App-beveiligingsbeleid**. 
2. Selecteer het app-beveiligingsbeleid dat u eerder hebt gemaakt. In deze snelstartgids is het beleid **Inhoudsbeveiliging Windows 10**.
3. Selecteer **Toewijzingen**.
4. Selecteer de optie **Op te nemen groepen selecteren** op het tabblad **Opnemen**.
5. Selecteer **Contoso-testers** als de op te nemen groep.
6. Klik op **Selecteren** > **Opslaan**. 

U hebt nu het beveiligingsbeleid voor apps toegewezen.

> [!NOTE]
> App-beveiligingsbeleid kan alleen worden toegepast op groepen met gebruikers, niet op groepen met apparaten.

## <a name="next-steps"></a>Volgende stappen

In deze snelstartgids hebt u beveiligingsbeleid voor apps gemaakt en toegewezen. Gebruikers van de app waaraan dit beleid is toegewezen, kunnen niet inhoud van de toegewezen app knippen/plakken of naar andere niet-beheerde apps op het apparaat kopiëren en omgekeerd. Met dit type beveiliging kunnen gegevens van uw organisatie worden beveiligd. Zie [Wat is een app-beveiligingsbeleid?](app-protection-policy.md) voor meer informatie over app-beveiligingsbeleid in Intune.

Als u deze reeks snelstartgidsen voor Intune wilt volgen, kunt u doorgaan met de volgende snelstartgids.

> [!div class="nextstepaction"]
> [Quickstart: Een aangepaste rol maken en toewijzen](quickstart-create-custom-role.md)
