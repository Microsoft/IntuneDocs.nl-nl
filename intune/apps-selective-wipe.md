---
title: Alleen zakelijke gegevens wissen uit apps
titleSuffix: Intune on Azure
description: Meer informatie over het selectief wissen van apps met Microsoft Intune.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 02/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42605e6e-5b84-44ff-b86e-346ea123b53e
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bfebc391997ac4e63466eb3a09044318cf807dbc
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-wipe-only-corporate-data-from-intune-managed-apps"></a>Alleen zakelijke gegevens wissen uit door Intune beheerde apps

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Wanneer een apparaat is vermist of is gestolen, of als een werknemer uw bedrijf verlaat, wilt u dat de gegevens in zakelijke apps van het apparaat worden verwijderd. Maar u wilt mogelijk geen persoonlijke gegevens op het apparaat verwijderen, vooral niet als het apparaat het eigendom van de werknemer is.

Als u alleen de gegevens van de zakelijke apps wilt verwijderen, maakt u een verzoek om te wissen aan de hand van de stappen in dit onderwerp. Wanneer de aanvraag is voltooid, worden de bedrijfsgegevens uit de app verwijderd wanneer de app de volgende keer op het apparaat wordt uitgevoerd.

>[!IMPORTANT]
> Contactpersonen die rechtstreeks vanuit de app zijn gesynchroniseerd met het systeemeigen adresboek, worden verwijderd. Contactpersonen die vanuit het systeemeigen adresboek zijn gesynchroniseerd met een andere externe bron, kunnen niet worden gewist. Dit is momenteel alleen van toepassing op de Microsoft Outlook-app.

## <a name="create-a-wipe-request"></a>Een wisaanvraag maken

1.  Meld u aan bij [Azure Portal](https://portal.azure.com).

2.  Kies **Meer services**, typ **Intune** in het filtertekstvak en selecteer **Intune**. De blade Intune wordt geopend. Kies de blade **Apps beheren**.

    ![Schermafbeelding van tabblad met een nieuwe wisaanvraag](./media/intune-azure-preview-blade.png)

3.  Kies op de **blade Mobiele apps** de optie **Nieuw verzoek om te wissen**. Hiermee opent u het tabblad **Nieuw verzoek om te wissen**.

4.  Kies **Nieuw verzoek om te wissen**. Hiermee opent u het tabblad **Nieuw verzoek om te wissen**.

    ![Schermafbeelding van tabblad met een nieuwe wisaanvraag](./media/AzurePortal_MAM_NewWipeRequest.png)

5.  Kies **Gebruiker** om het tabblad **Gebruiker** te openen en selecteer vervolgens de gebruiker van wie u de app-gegevens wilt wissen.

6.  Kies **Apparaat**. Hiermee opent u de blade **Apparaat** waarop een lijst wordt weergegeven met alle apparaten die zijn gekoppeld aan de geselecteerde gebruiker. De blade bevat ook twee kolommen, de apparaatnaam, een beschrijvende naam die door de gebruiker is gedefinieerd en het apparaattype, het apparaatplatform. Selecteer het apparaat dat u wilt wissen.

7.  U bent nu terug op het tabblad **Nieuw verzoek om te wissen**. Kies **Ok** om een wisaanvraag te maken. 

De service maakt en volgt voor elke beveiligde app op het apparaat een afzonderlijk verzoek om te wissen en de gebruiker die is gekoppeld aan het verzoek om te wissen.

## <a name="monitor-your-wipe-requests"></a>Uw verzoeken om te wissen bijhouden

U kunt een verkort rapport weergeven met de algemene status van het verzoek om te wissen, het aantal verzoeken dat in behandeling is en het aantal verzoeken dat is mislukt. Voor meer informatie volgt u deze stappen:

1.  Op **Mobiele apps - blade App selectief wissen** ziet u een lijst met uw verzoeken, gegroepeerd per gebruiker. Omdat het systeem voor elke beveiligde app die op het apparaat wordt uitgevoerd een verzoek om te wissen maakt, ziet u mogelijk meerdere verzoeken voor dezelfde gebruiker. De status geeft aan of een verzoek om te wissen **in behandeling**, **mislukt**of **geslaagd**is.

    ![Schermafbeelding van tabblad met een nieuwe wisaanvraag](./media/wipe-request-status-1.png)

U ziet ook de apparaatnaam en het apparaattype, wat nuttig kan zijn bij het lezen van de rapporten.

>[!IMPORTANT]
> De gebruiker moet de app openen voordat het wissen wordt uitgevoerd, en het wissen kan tot 30 minuten duren nadat het verzoek is gemaakt.

## <a name="delete-a-wipe-request"></a>Een verzoek om te wissen verwijderen

Wisverzoeken die nog in behandeling zijn, worden weergegeven totdat u ze handmatig verwijdert.  Handmatig een verzoek om te wissen verwijderen:

1.  Kies op de blade **Verzoek om te wissen** de tegel **Verzoek om te wissen** om de blade **Verzoek om te wissen** te openen.

2.  Klik met de rechtermuisknop op het verzoek om te wissen dat u wilt verwijderen, en kies vervolgens **Verzoek om te wissen verwijderen**.

    ![Schermafbeelding van tabblad met een nieuwe wisaanvraag](./media/delete-wipe-request.png)

3.  U wordt gevraagd om het verwijderen te bevestigen. Kies **Ja** of **Nee** en klik vervolgens op **OK**.

### <a name="see-also"></a>Zie tevens
[Wat is app-beveiligingsbeleid](app-protection-policy.md)

[Wat is app-beheer](app-management.md)