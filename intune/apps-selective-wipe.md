---
title: Alleen zakelijke gegevens wissen uit apps
titleSuffix: Microsoft Intune
description: Hier vindt u meer informatie over het wissen van uitsluitend zakelijke gegevens uit door Intune beheerde apps met Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/24/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 42605e6e-5b84-44ff-b86e-346ea123b53e
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 83cc1f43faba1ee98bde680b1ff2b74c78ff65e4
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57389510"
---
# <a name="how-to-wipe-only-corporate-data-from-intune-managed-apps"></a>Alleen zakelijke gegevens wissen uit door Intune beheerde apps

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Wanneer een apparaat is vermist of is gestolen, of als een werknemer uw bedrijf verlaat, wilt u dat de gegevens in zakelijke apps van het apparaat worden verwijderd. Maar u wilt mogelijk geen persoonlijke gegevens op het apparaat verwijderen, vooral niet als het apparaat het eigendom van de werknemer is.

>[!NOTE]
> Het iOS-, Android-, en Windows 10-platform zijn momenteel de enige platforms die worden ondersteund voor het wissen van bedrijfsgegevens uit met Intune beheerde apps. Beheerde Intune-apps zijn toepassingen waarin de Intune APP SDK is opgenomen en die een gebruikersaccount bevatten met een licentie voor uw organisatie. Implementatie van beleid voor toepassingsbeveiliging is niet vereist om selectief wissen voor de app in te schakelen.

Als u alleen de gegevens van de zakelijke apps wilt verwijderen, maakt u een verzoek om te wissen aan de hand van de stappen in dit onderwerp. Wanneer de aanvraag is voltooid, worden de bedrijfsgegevens uit de app verwijderd wanneer de app de volgende keer op het apparaat wordt uitgevoerd. U kunt naast het maken van een wisaanvraag tevens een selectieve wisbewerking configureren van de gegevens van uw organisatie als nieuwe actie, wanneer niet wordt voldaan aan de voorwaarden van de toegangsinstellingen voor toepassingsbeveiligingsbeleid. Dankzij deze functie kunt u gevoelige organisatiegegevens automatisch beveiligen en verwijderen uit toepassingen op basis van vooraf geconfigureerde criteria.

>[!IMPORTANT]
> Contactpersonen die rechtstreeks vanuit de app zijn gesynchroniseerd met het systeemeigen adresboek, worden verwijderd. Contactpersonen die vanuit het systeemeigen adresboek zijn gesynchroniseerd met een andere externe bron, kunnen niet worden gewist. Dit is momenteel alleen van toepassing op de Microsoft Outlook-app.

## <a name="deployed-wip-policies-without-user-enrollment"></a>Geïmplementeerd WIP-beleid zonder gebruikersinschrijving
WIP-beleid (Windows Information Protection) kan worden geïmplementeerd zonder dat MDM-gebruikers hun Windows 10-apparaat hoeven in te schrijven. Met deze configuratie kunnen bedrijven hun bedrijfsdocumenten op basis van de WIP-configuratie beschermen, terwijl gebruikers hun eigen Windows-apparaten kunnen blijven beheren. Zodra documenten met WIP-beleid zijn beveiligd, kunnen de beschermde gegevens selectief worden gewist door een Intune-beheerder. Door een gebruiker en een apparaat te selecteren een en wisaanvraag te versturen, worden alle gegevens onbruikbaar die met het WIP-beleid zijn beschermd. Vanuit Intune in de Azure-portal selecteert u hiervoor **Client-app** > **App selectief wissen**. Zie [Beveiligingsinstelling voor de beveiliging van apps voor Windows Information Protection (WIP) maken en implementeren met Intune](windows-information-protection-policy-create.md).

## <a name="create-a-wipe-request"></a>Een wisaanvraag maken

1.  Meld u aan bij [Azure Portal](https://portal.azure.com).

2.  Kies **Alle services**, typ **Intune** in het filtertekstvak en selecteer **Intune**. Het deelvenster Intune wordt geopend. Kies het deelvenster **Client-apps**.

    ![Schermopname van het Microsoft Intune-deelvenster](./media/apps-selective-wipe01.png)

3.  Kies in het **deelvenster Client-apps** de optie **App selectief wissen**.

4.  Kies **Nieuw verzoek om te wissen**. Hiermee opent u het deelvenster **Nieuw verzoek om te wissen**.

    ![Schermafbeelding van deelvenster met een nieuwe wisaanvraag](./media/AzurePortal_MAM_NewWipeRequest.png)

5.  Kies een gebruiker en kies vervolgens **Selecteren** om de gebruiker te selecteren waarvan u de gegevens wilt wissen.

6.  Kies vervolgens **Apparaat** in het deelvenster **Nieuw verzoek om te wissen**. Hiermee opent u het deelvenster **Apparaat selecteren** waarin een lijst wordt weergegeven met alle apparaten die zijn gekoppeld aan de geselecteerde gebruiker. Het deelvenster bevat ook twee kolommen, de apparaatnaam (een beschrijvende naam die door de gebruiker is gedefinieerd) en het apparaattype (het apparaatplatform). Selecteer het apparaat dat u wilt wissen.

7.  U bent nu terug in het deelvenster **Nieuw verzoek om te wissen**. Kies **OK** om een wisaanvraag te maken.

De service maakt en volgt voor elke beveiligde app op het apparaat een afzonderlijk verzoek om te wissen en de gebruiker die is gekoppeld aan het verzoek om te wissen.

## <a name="monitor-your-wipe-requests"></a>Uw verzoeken om te wissen bijhouden

U kunt een verkort rapport weergeven met de algemene status van het verzoek om te wissen, het aantal verzoeken dat in behandeling is en het aantal verzoeken dat is mislukt. Voor meer informatie volgt u deze stappen:

1.  In het deelvenster **Client-apps - App selectief wissen** ziet u een lijst met alle aanvragen, gegroepeerd per gebruiker. Omdat het systeem voor elke beveiligde app die op het apparaat wordt uitgevoerd een verzoek om te wissen maakt, ziet u mogelijk meerdere verzoeken voor dezelfde gebruiker. De status geeft aan of een verzoek om te wissen **in behandeling**, **mislukt**of **geslaagd**is.

    ![Schermafbeelding van de status van de aanvraag voor wissen in het deelvenster App selectief wissen](./media/wipe-request-status-1.png)

U ziet ook de apparaatnaam en het apparaattype, wat nuttig kan zijn bij het lezen van de rapporten.

>[!IMPORTANT]
> De gebruiker moet de app openen voordat het wissen wordt uitgevoerd, en het wissen kan tot 30 minuten duren nadat het verzoek is gemaakt.

## <a name="delete-a-wipe-request"></a>Een verzoek om te wissen verwijderen

Wisverzoeken die nog in behandeling zijn, worden weergegeven totdat u ze handmatig verwijdert. Handmatig een verzoek om te wissen verwijderen:

1.  In het deelvenster **Client-apps - App selectief wissen**.

2.  Klik met de rechtermuisknop op de aanvraag voor wissen die u wilt verwijderen, en kies vervolgens **Aanvraag voor wissen verwijderen**.

    ![Schermafbeelding van de lijst met aanvragen voor wissen in het deelvenster App selectief wissen](./media/delete-wipe-request.png)

3.  U wordt gevraagd om het verwijderen te bevestigen. Kies **Ja** of **Nee** en klik vervolgens op **OK**.

### <a name="see-also"></a>Zie tevens
[Wat is app-beveiligingsbeleid](app-protection-policy.md)

[Wat is app-beheer](app-management.md)
