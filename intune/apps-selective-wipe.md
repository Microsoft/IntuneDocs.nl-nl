---
title: Alleen zakelijke gegevens wissen uit apps
titleSuffix: Microsoft Intune
description: Meer informatie over het selectief wissen van apps met Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 42605e6e-5b84-44ff-b86e-346ea123b53e
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 76c394be6130a874e7ce2fb1b6e3c244cad98f80
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905271"
---
# <a name="how-to-wipe-only-corporate-data-from-intune-managed-apps"></a>Alleen zakelijke gegevens wissen uit door Intune beheerde apps

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Wanneer een apparaat is vermist of is gestolen, of als een werknemer uw bedrijf verlaat, wilt u dat de gegevens in zakelijke apps van het apparaat worden verwijderd. Maar u wilt mogelijk geen persoonlijke gegevens op het apparaat verwijderen, vooral niet als het apparaat het eigendom van de werknemer is.

>[!NOTE]
> De iOS- en Android-platforms zijn de twee platforms die momenteel worden ondersteund voor het wissen van bedrijfsgegevens uit door Intune beheerde apps.

Als u alleen de gegevens van de zakelijke apps wilt verwijderen, maakt u een verzoek om te wissen aan de hand van de stappen in dit onderwerp. Wanneer de aanvraag is voltooid, worden de bedrijfsgegevens uit de app verwijderd wanneer de app de volgende keer op het apparaat wordt uitgevoerd. U kunt naast het maken van een wisaanvraag tevens een selectieve wisbewerking configureren van de gegevens van uw organisatie als nieuwe actie, wanneer niet wordt voldaan aan de voorwaarden van de toegangsinstellingen voor toepassingsbeveiligingsbeleid. Dankzij deze functie kunt u gevoelige organisatiegegevens automatisch beveiligen en verwijderen uit toepassingen op basis van vooraf geconfigureerde criteria.

>[!IMPORTANT]
> Contactpersonen die rechtstreeks vanuit de app zijn gesynchroniseerd met het systeemeigen adresboek, worden verwijderd. Contactpersonen die vanuit het systeemeigen adresboek zijn gesynchroniseerd met een andere externe bron, kunnen niet worden gewist. Dit is momenteel alleen van toepassing op de Microsoft Outlook-app.

## <a name="create-a-wipe-request"></a>Een wisaanvraag maken

1.  Meld u aan bij [Azure Portal](https://portal.azure.com).

2.  Kies **Alle services**, typ **Intune** in het filtertekstvak en selecteer **Intune**. Het deelvenster Intune wordt geopend. Kies het deelvenster **Mobiele apps**.

    ![Schermopname van het Microsoft Intune-deelvenster](./media/apps-selective-wipe01.png)

3.  Kies in het **deelvenster Mobiele apps** de optie **App selectief wissen**.

4.  Kies **Nieuw verzoek om te wissen**. Hiermee opent u het deelvenster **Nieuw verzoek om te wissen**.

    ![Schermafbeelding van deelvenster met een nieuwe wisaanvraag](./media/AzurePortal_MAM_NewWipeRequest.png)

5.  Kies een gebruiker en kies vervolgens **Selecteren** om de gebruiker te selecteren waarvan u de gegevens wilt wissen.

6.  Kies vervolgens **Apparaat** in het deelvenster **Nieuw verzoek om te wissen**. Hiermee opent u het deelvenster **Apparaat selecteren** waarin een lijst wordt weergegeven met alle apparaten die zijn gekoppeld aan de geselecteerde gebruiker. Het deelvenster bevat ook twee kolommen, de apparaatnaam (een beschrijvende naam die door de gebruiker is gedefinieerd) en het apparaattype (het apparaatplatform). Selecteer het apparaat dat u wilt wissen.

7.  U bent nu terug in het deelvenster **Nieuw verzoek om te wissen**. Kies **OK** om een wisaanvraag te maken.

De service maakt en volgt voor elke beveiligde app op het apparaat een afzonderlijk verzoek om te wissen en de gebruiker die is gekoppeld aan het verzoek om te wissen.

## <a name="monitor-your-wipe-requests"></a>Uw verzoeken om te wissen bijhouden

U kunt een verkort rapport weergeven met de algemene status van het verzoek om te wissen, het aantal verzoeken dat in behandeling is en het aantal verzoeken dat is mislukt. Voor meer informatie volgt u deze stappen:

1.  In het deelvenster **Mobiele apps - App selectief wissen** ziet u een lijst met alle aanvragen, gegroepeerd per gebruiker. Omdat het systeem voor elke beveiligde app die op het apparaat wordt uitgevoerd een verzoek om te wissen maakt, ziet u mogelijk meerdere verzoeken voor dezelfde gebruiker. De status geeft aan of een verzoek om te wissen **in behandeling**, **mislukt**of **geslaagd**is.

    ![Schermafbeelding van de status van de aanvraag voor wissen in het deelvenster App selectief wissen](./media/wipe-request-status-1.png)

U ziet ook de apparaatnaam en het apparaattype, wat nuttig kan zijn bij het lezen van de rapporten.

>[!IMPORTANT]
> De gebruiker moet de app openen voordat het wissen wordt uitgevoerd, en het wissen kan tot 30 minuten duren nadat het verzoek is gemaakt.

## <a name="delete-a-wipe-request"></a>Een verzoek om te wissen verwijderen

Wisverzoeken die nog in behandeling zijn, worden weergegeven totdat u ze handmatig verwijdert. Handmatig een verzoek om te wissen verwijderen:

1.  In het deelvenster **Mobiele apps - App selectief wissen**.

2.  Klik met de rechtermuisknop op de aanvraag voor wissen die u wilt verwijderen, en kies vervolgens **Aanvraag voor wissen verwijderen**.

    ![Schermafbeelding van de lijst met aanvragen voor wissen in het deelvenster App selectief wissen](./media/delete-wipe-request.png)

3.  U wordt gevraagd om het verwijderen te bevestigen. Kies **Ja** of **Nee** en klik vervolgens op **OK**.

### <a name="see-also"></a>Zie ook
[Wat is app-beveiligingsbeleid](app-protection-policy.md)

[Wat is app-beheer](app-management.md)
