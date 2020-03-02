---
title: Alleen zakelijke gegevens wissen uit apps
titleSuffix: Microsoft Intune
description: Hier vindt u meer informatie over het wissen van uitsluitend zakelijke gegevens uit door Intune beheerde apps met Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 42605e6e-5b84-44ff-b86e-346ea123b53e
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1f6992aa93e1ca5a095b1e92a16a07bd0eb1c2f5
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77513632"
---
# <a name="how-to-wipe-only-corporate-data-from-intune-managed-apps"></a>Alleen zakelijke gegevens wissen uit door Intune beheerde apps

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Wanneer een apparaat is vermist of is gestolen, of als een werknemer uw bedrijf verlaat, wilt u dat de gegevens in zakelijke apps van het apparaat worden verwijderd. Maar u wilt mogelijk geen persoonlijke gegevens op het apparaat verwijderen, vooral niet als het apparaat het eigendom van de werknemer is.

>[!NOTE]
> Het iOS/iPadOS-, Android- en Windows 10-platform zijn momenteel de enige platformen die worden ondersteund voor het wissen van bedrijfsgegevens uit met Intune beheerde apps. Beheerde Intune-apps zijn toepassingen waarin de Intune APP SDK is opgenomen en die een gebruikersaccount bevatten met een licentie voor uw organisatie. Implementatie van beleid voor toepassingsbeveiliging is niet vereist om selectief wissen voor de app in te schakelen.

Als u alleen de gegevens van de zakelijke apps wilt verwijderen, maakt u een verzoek om te wissen aan de hand van de stappen in dit onderwerp. Wanneer de aanvraag is voltooid, worden de bedrijfsgegevens uit de app verwijderd wanneer de app de volgende keer op het apparaat wordt uitgevoerd. U kunt naast het maken van een wisaanvraag tevens een selectieve wisbewerking configureren van de gegevens van uw organisatie als nieuwe actie, wanneer niet wordt voldaan aan de voorwaarden van de toegangsinstellingen voor toepassingsbeveiligingsbeleid. Dankzij deze functie kunt u gevoelige organisatiegegevens automatisch beveiligen en verwijderen uit toepassingen op basis van vooraf geconfigureerde criteria.

>[!IMPORTANT]
> Contactpersonen die rechtstreeks vanuit de app zijn gesynchroniseerd met het systeemeigen adresboek, worden verwijderd. Contactpersonen die vanuit het systeemeigen adresboek zijn gesynchroniseerd met een andere externe bron, kunnen niet worden gewist. Dit is momenteel alleen van toepassing op de Microsoft Outlook-app.

## <a name="deployed-wip-policies-without-user-enrollment"></a>Geïmplementeerd WIP-beleid zonder gebruikersinschrijving
WIP-beleid (Windows Information Protection) kan worden geïmplementeerd zonder dat MDM-gebruikers hun Windows 10-apparaat hoeven in te schrijven. Met deze configuratie kunnen bedrijven hun bedrijfsdocumenten op basis van de WIP-configuratie beschermen, terwijl gebruikers hun eigen Windows-apparaten kunnen blijven beheren. Zodra documenten met WIP-beleid zijn beveiligd, kunnen de beschermde gegevens selectief worden gewist door een Intune-beheerder. Door een gebruiker en een apparaat te selecteren een en wisaanvraag te versturen, worden alle gegevens onbruikbaar die met het WIP-beleid zijn beschermd. Vanuit Intune in de Azure-portal selecteert u hiervoor **Client-app** > **App selectief wissen**. Zie [Beveiligingsinstelling voor de beveiliging van apps voor Windows Information Protection (WIP) maken en implementeren met Intune](windows-information-protection-policy-create.md).

## <a name="create-a-wipe-request"></a>Een wisaanvraag maken

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apps** > **App selectief wissen** > **Wisaanvraag maken**.<br>
   Het deelvenster **Wisaanvraag maken** wordt weergegeven.
3. Klik op **Gebruiker selecteren**, kies de gebruiker van wie u de app-gegevens wilt wissen en klik op **Selecteren** onder aan het deelvenster **Gebruiker selecteren**.

    ![Schermopname van deelvenster Gebruiker selecteren](./media/apps-selective-wipe/apps-selective-wipe-01.png)

4. Klik op **Selecteer het apparaat**, kies het apparaat en klik op **Selecteren** onder aan het deelvenster **Apparaat selecteren**.

    ![Schermopname van het deelvenster Wisaanvraag maken waarbij het apparaat is geselecteerd](./media/apps-selective-wipe/apps-selective-wipe-02.png)

5. Klik op **Maken** om een wisaanvraag te maken.

De service maakt en volgt voor elke beveiligde app op het apparaat een afzonderlijk verzoek om te wissen en de gebruiker die is gekoppeld aan het verzoek om te wissen.

   ![Schermopname van het deelvenster Client-apps - App selectief wissen](./media/apps-selective-wipe/apps-selective-wipe-03.png)

## <a name="monitor-your-wipe-requests"></a>Uw verzoeken om te wissen bijhouden

U kunt een verkort rapport weergeven met de algemene status van het verzoek om te wissen, het aantal verzoeken dat in behandeling is en het aantal verzoeken dat is mislukt. Voor meer informatie volgt u deze stappen:

1. In het deelvenster **Apps** > **App selectief wissen** ziet u een lijst met alle aanvragen, gegroepeerd per gebruiker. Omdat het systeem voor elke beveiligde app die op het apparaat wordt uitgevoerd een verzoek om te wissen maakt, ziet u mogelijk meerdere verzoeken voor dezelfde gebruiker. De status geeft aan of een verzoek om te wissen **in behandeling**, **mislukt**of **geslaagd**is.

    ![Schermafbeelding van de status van de aanvraag voor wissen in het deelvenster App selectief wissen](./media/apps-selective-wipe/wipe-request-status-1.png)

U ziet ook de apparaatnaam en het apparaattype, wat nuttig kan zijn bij het lezen van de rapporten.

>[!IMPORTANT]
> De gebruiker moet de app openen voordat het wissen wordt uitgevoerd, en het wissen kan tot 30 minuten duren nadat het verzoek is gemaakt.

## <a name="delete-a-wipe-request"></a>Een verzoek om te wissen verwijderen

Wisverzoeken die nog in behandeling zijn, worden weergegeven totdat u ze handmatig verwijdert. Handmatig een verzoek om te wissen verwijderen:

1. In het deelvenster **Client-apps - App selectief wissen**.

2. Klik met de rechtermuisknop op de aanvraag voor wissen die u wilt verwijderen, en kies vervolgens **Aanvraag voor wissen verwijderen**.

    ![Schermafbeelding van de lijst met aanvragen voor wissen in het deelvenster App selectief wissen](./media/apps-selective-wipe/delete-wipe-request.png)

3. U wordt gevraagd om het verwijderen te bevestigen. Kies **Ja** of **Nee** en klik vervolgens op **OK**.

## <a name="see-also"></a>Zie tevens
[Wat is app-beveiligingsbeleid](app-protection-policy.md)

[Wat is app-beheer](app-management.md)
