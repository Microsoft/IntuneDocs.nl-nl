---
title: Alleen zakelijke gegevens wissen uit apps
titleSuffix: Microsoft Intune
description: Meer informatie over het selectief wissen van apps met Microsoft Intune.
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42605e6e-5b84-44ff-b86e-346ea123b53e
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dfd1b37c1b944a545234b93b44d651ead8f0f486
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/05/2018
---
# <a name="how-to-wipe-only-corporate-data-from-intune-managed-apps"></a>Alleen zakelijke gegevens wissen uit door Intune beheerde apps

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Wanneer een apparaat is vermist of is gestolen, of als een werknemer uw bedrijf verlaat, wilt u dat de gegevens in zakelijke apps van het apparaat worden verwijderd. Maar u wilt mogelijk geen persoonlijke gegevens op het apparaat verwijderen, vooral niet als het apparaat het eigendom van de werknemer is.

>[!NOTE]
> De iOS- en Android-platforms zijn de twee platforms die momenteel worden ondersteund voor het wissen van bedrijfsgegevens uit door Intune beheerde apps.

Als u alleen de gegevens van de zakelijke apps wilt verwijderen, maakt u een verzoek om te wissen aan de hand van de stappen in dit onderwerp. Wanneer de aanvraag is voltooid, worden de bedrijfsgegevens uit de app verwijderd wanneer de app de volgende keer op het apparaat wordt uitgevoerd.

>[!IMPORTANT]
> Contactpersonen die rechtstreeks vanuit de app zijn gesynchroniseerd met het systeemeigen adresboek, worden verwijderd. Contactpersonen die vanuit het systeemeigen adresboek zijn gesynchroniseerd met een andere externe bron, kunnen niet worden gewist. Dit is momenteel alleen van toepassing op de Microsoft Outlook-app.

## <a name="create-a-wipe-request"></a>Een wisaanvraag maken

1.  Meld u aan bij [Azure Portal](https://portal.azure.com).

2.  Kies **Meer services**, typ **Intune** in het filtertekstvak en selecteer **Intune**. De Intune-blade wordt geopend. Selecteer **Mobiele apps**.

    ![Schermopname van de Microsoft Intune-blade](./media/apps-selective-wipe01.png)

3.  Kies op de **blade Mobiele apps** de optie **App selectief wissen**.

4.  Kies **Nieuw verzoek om te wissen**. Hiermee opent u het deelvenster **Nieuw verzoek om te wissen**.

    ![Schermafbeelding van deelvenster met een nieuwe wisaanvraag](./media/AzurePortal_MAM_NewWipeRequest.png)

5.  Kies **Gebruiker** om het tabblad **Gebruiker** te openen en selecteer vervolgens de gebruiker van wie u de app-gegevens wilt wissen.

6.  Kies vervolgens **Apparaat** op de blade **Nieuw verzoek om te wissen**. Met deze actie opent u de blade **Apparaat selecteren**. Hierop staan alle apparaten die aan de geselecteerde gebruiker zijn gekoppeld. In dit deelvenster staat ook de naam van het apparaat, wat een beschrijvende naam is die is gedefinieerd door de gebruiker, en het apparaattype, dat het apparaatplatform aangeeft. 

7. Selecteer het apparaat dat u wilt wissen in de lijst.

8.  U bent nu terug op het tabblad **Nieuw verzoek om te wissen**. Kies **Ok** om een wisaanvraag te maken.

De service maakt en volgt voor elke beveiligde app op het apparaat een afzonderlijk verzoek om te wissen en de gebruiker die is gekoppeld aan het verzoek om te wissen.

## <a name="monitor-your-wipe-requests"></a>Uw verzoeken om te wissen bijhouden

U kunt een verkort rapport weergeven met de algemene status van het verzoek om te wissen, het aantal verzoeken dat in behandeling is en het aantal verzoeken dat is mislukt. Voor meer informatie volgt u deze stappen:

1.  Op de blade **Mobiele apps - App selectief wissen** ziet u een lijst met uw verzoeken, gegroepeerd per gebruiker. Omdat het systeem voor elke beveiligde app die op het apparaat wordt uitgevoerd een verzoek om te wissen maakt, ziet u mogelijk meerdere verzoeken voor dezelfde gebruiker. De status geeft aan of een verzoek om te wissen **in behandeling**, **mislukt**of **geslaagd**is.

    ![Schermafbeelding van de status van de aanvraag voor wissen in het deelvenster App selectief wissen](./media/wipe-request-status-1.png)

U ziet ook de apparaatnaam en het apparaattype, wat nuttig kan zijn bij het lezen van de rapporten.

>[!IMPORTANT]
> De gebruiker moet de app openen voordat het wissen wordt uitgevoerd, en het wissen kan tot 30 minuten duren nadat het verzoek is gemaakt.

## <a name="delete-a-wipe-request"></a>Een verzoek om te wissen verwijderen

Wisverzoeken die nog in behandeling zijn, worden weergegeven totdat u ze handmatig verwijdert. Handmatig een verzoek om te wissen verwijderen:

1.  Open de blade **Mobiele apps - App selectief wissen**.

2.  Klik met de rechtermuisknop op de aanvraag voor wissen die u wilt verwijderen, en kies vervolgens **Aanvraag voor wissen verwijderen**.

    ![Schermafbeelding van de lijst met aanvragen voor wissen in het deelvenster App selectief wissen](./media/delete-wipe-request.png)

3.  U wordt gevraagd om het verwijderen te bevestigen. Kies **Ja** of **Nee** en klik vervolgens op **OK**.

### <a name="see-also"></a>Zie ook
[Wat is app-beveiligingsbeleid](app-protection-policy.md)

[Wat is app-beheer](app-management.md)
