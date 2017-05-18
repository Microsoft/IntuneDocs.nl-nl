---
title: Bedrijfsgegevens van beheerde apps wissen | Microsoft Docs
description: Informatie over het op afstand selectief verwijderen van bedrijfsgegevens.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2742e1d5-d2d5-42cd-b719-665dd6e0a0e9
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8a3e8634769b05e6639f7efb6394b7333d998f06
ms.openlocfilehash: 5d5cde748aa8fa464526d0dc2b2ef9ee460fff9d


---

# <a name="wipe-company-app-data-with-intune-mam"></a>Bedrijfsgegevens van apps wissen met Intune-MAM

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Wanneer een apparaat is vermist of is gestolen, of als een werknemer uw bedrijf verlaat, wilt u dat de gegevens in zakelijke apps van het apparaat worden verwijderd. Maar u wilt mogelijk geen persoonlijke gegevens op het apparaat verwijderen, vooral niet als het apparaat het eigendom van de werknemer is.

Als u alleen de gegevens van de zakelijke apps wilt verwijderen, maakt u een verzoek om te wissen aan de hand van de stappen in dit onderwerp. Wanneer de aanvraag is voltooid, worden de bedrijfsgegevens uit de app verwijderd wanneer de app de volgende keer op het apparaat wordt uitgevoerd.

>[!IMPORTANT]
> Contactpersonen die rechtstreeks vanuit de app zijn gesynchroniseerd met het systeemeigen adresboek, worden verwijderd. Contactpersonen die vanuit het systeemeigen adresboek zijn gesynchroniseerd met een andere externe bron, kunnen niet worden gewist. Dit is momenteel alleen van toepassing op de Microsoft Outlook-app.

## <a name="create-a-wipe-request"></a>Een wisaanvraag maken

1.  Meld u aan bij [Azure Portal](https://portal.azure.com).

2.  Kies **Meer services**, typ **Intune** in het filtertekstvak en selecteer **Intune App Protection (Intune-app-beveiliging)**. Het tabblad Intune Mobile Application Management op de blade wordt geopend.

    ![Schermafbeelding van tabblad met een nieuwe wisaanvraag](../media/AppManagement/wipe-request-mam-main-blade.png)

2.  Kies op het tabblad **Instellingen** de optie **Aanvragen wissen**.

3.  Kies **Nieuw verzoek om te wissen**. Hiermee opent u het tabblad **Nieuw verzoek om te wissen**.

    ![Schermafbeelding van tabblad met een nieuwe wisaanvraag](../media/AppManagement/AzurePortal_MAM_NewWipeRequest.png)

4.  Kies **Gebruiker** om het tabblad **Gebruiker** te openen en selecteer vervolgens de gebruiker van wie u de app-gegevens wilt wissen.

5.  Kies **Apparaat**. Hiermee opent u de blade **Apparaat** waarop een lijst wordt weergegeven met alle apparaten die zijn gekoppeld aan de geselecteerde gebruiker. De blade bevat ook twee kolommen, de apparaatnaam, een beschrijvende naam die door de gebruiker is gedefinieerd en het apparaattype, het apparaatplatform. Selecteer het apparaat dat u wilt wissen.

6.  U bent nu terug op het tabblad **Nieuw verzoek om te wissen**. Kies **Ok** om een wisaanvraag te maken. 

De service maakt en volgt voor elke beveiligde app op het apparaat een afzonderlijk verzoek om te wissen en de gebruiker die is gekoppeld aan het verzoek om te wissen.

>[!NOTE]
> U kunt ook de opdracht **Verzoek om te wissen** maken door te klikken op **Verzoek om te wissen** op de blade Intune Mobile Application Management.

## <a name="monitor-your-wipe-requests"></a>Uw verzoeken om te wissen bijhouden

U kunt een verkort rapport weergeven met de algemene status van het verzoek om te wissen, het aantal verzoeken dat in behandeling is en het aantal verzoeken dat is mislukt. Voor meer informatie volgt u deze stappen:

1.  Klik op de blade Intune Mobile Application Management op de tegel **Verzoeken om te wissen**.

2.  Kies op de blade **Verzoek om te wissen** de tegel **Verzoek om te wissen** om de blade **Verzoek om te wissen** te openen.

3.  Op het tabblad **Verzoek om te wissen** ziet u een lijst met uw verzoeken, gegroepeerd per gebruiker. Omdat het systeem voor elke beveiligde app die op het apparaat wordt uitgevoerd een verzoek om te wissen maakt, ziet u mogelijk meerdere verzoeken voor dezelfde gebruiker. De status geeft aan of een verzoek om te wissen **in behandeling**, **mislukt**of **geslaagd**is.

    ![Schermafbeelding van tabblad met een nieuwe wisaanvraag](../media/AppManagement/wipe-request-status-1.png)

U ziet ook de apparaatnaam en het apparaattype, wat nuttig kan zijn bij het lezen van de rapporten.

>[!IMPORTANT]
> De gebruiker moet de app openen voordat het wissen wordt uitgevoerd, en het wissen kan tot 30 minuten duren nadat het verzoek is gemaakt.

## <a name="delete-a-wipe-request"></a>Een verzoek om te wissen verwijderen

Wisverzoeken die nog in behandeling zijn, worden weergegeven totdat u ze handmatig verwijdert.  Handmatig een verzoek om te wissen verwijderen

1.  Klik op de blade Intune Mobile Application Management op de tegel **Verzoeken om te wissen**.

2.  Kies op de blade **Verzoek om te wissen** de tegel **Verzoek om te wissen** om de blade **Verzoek om te wissen** te openen.

3.  Klik met de rechtermuisknop op het verzoek om te wissen dat u wilt verwijderen, en kies vervolgens **Verzoek om te wissen verwijderen**.

    ![Schermafbeelding van tabblad met een nieuwe wisaanvraag](../media/AppManagement/delete-wipe-request.png)

4.  U wordt gevraagd om het verwijderen te bevestigen. Kies **Ja** of **Nee** en klik vervolgens op **OK**.


### <a name="see-also"></a>Zie tevens
[App-gegevens beschermen met beleid voor het beheren van mobiele apps ](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[De Azure-portal gebruiken](azure-portal-for-microsoft-intune-mam-policies.md)



<!--HONumber=Feb17_HO1-->


