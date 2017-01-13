---
title: Bedrijfsgegevens van beheerde apps wissen | Microsoft Docs
description: Informatie over het op afstand selectief verwijderen van bedrijfsgegevens.
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2742e1d5-d2d5-42cd-b719-665dd6e0a0e9
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 42e8feba18330539389fc4ab7af5cbd18a8ace16


---

# <a name="wipe-managed-company-app-data-with-microsoft-intune"></a>Bedrijfsgegevens van beheerde apps wissen met Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Wanneer een apparaat is vermist of is gestolen, of als een werknemer uw bedrijf verlaat, wilt u dat de gegevens in zakelijke apps van het apparaat worden verwijderd. Maar u wilt mogelijk geen persoonlijke gegevens op het apparaat verwijderen, vooral niet als het apparaat het eigendom van de werknemer is.

Als u alleen de gegevens van de zakelijke apps wilt verwijderen, maakt u een verzoek om te wissen aan de hand van de stappen in dit onderwerp. Wanneer de aanvraag is voltooid, worden de bedrijfsgegevens uit de app verwijderd wanneer de app de volgende keer op het apparaat wordt uitgevoerd.
>[!NOTE]
> Contactpersonen die rechtstreeks vanuit de app zijn gesynchroniseerd met het systeemeigen adresboek, worden verwijderd. Contactpersonen die vanuit het systeemeigen adresboek zijn gesynchroniseerd met een andere externe bron, kunnen niet worden gewist. Dit is momenteel alleen van toepassing op de Microsoft Outlook-app.



## <a name="create-a-wipe-request"></a>Een wisaanvraag maken

1.  Kies op het tabblad **Intune Mobile Application Management** de tegel **Aanvragen voor wissen**.

    ![Schermafbeelding van het tabblad Mobile Application Management van Intune met de tegels met een samenvatting](../media/AppManagement/AzurePortal_MAM_WipeRequests.png)

2.  Kies **Nieuwe aanvragen voor wissen**. Hiermee opent u het tabblad **Nieuw verzoek om te wissen**.

    ![Schermafbeelding van tabblad met een nieuwe wisaanvraag](../media/AppManagement/AzurePortal_MAM_NewWipeRequest.png)

3.  Kies **Gebruiker** om het tabblad **Gebruiker** te openen en selecteer vervolgens de gebruiker van wie u de app-gegevens wilt wissen.

4.  Kies **Apparaat**.  Hiermee opent u het tabblad **Apparaat** met een lijst met alle apparaten die aan de geselecteerde gebruiker zijn gekoppeld.  Selecteer het apparaat dat u wilt wissen.

5.  U bent nu terug op het tabblad **Nieuw verzoek om te wissen**. Kies **Ok** om een wisaanvraag te maken. De service maakt en volgt voor elke beveiligde app op het apparaat een afzonderlijk verzoek om te wissen.


![Schermafdruk van de tegel Aanvragen voor wissen ](../media/AppManagement/AzurePortal_MAM_WipeRequestsSummary.png)

## <a name="monitor-your-wipe-requests"></a>Uw verzoeken om te wissen bijhouden
Het tabblad **Intune Mobile Application Management** biedt een samenvattingsrapport op de tegel **Verzoek om te wissen** .  Dit rapport toont de algemene status, inclusief het aantal in behandeling zijnde verzoeken en fouten. U kunt meer informatie krijgen door de onderstaande stappen te volgen:

1.  Kies op het tabblad **Intune Mobile Application Management** de tegel **Verzoek om te wissen** om het tabblad **Verzoek om te wissen** te openen.

2.  Op het tabblad **Verzoek om te wissen** ziet u een lijst met uw verzoeken, gegroepeerd per gebruiker. Omdat het systeem voor elke beveiligde app die op het apparaat wordt uitgevoerd een verzoek om te wissen maakt, ziet u mogelijk meerdere verzoeken voor dezelfde gebruiker. De status geeft aan of een verzoek om te wissen **in behandeling**, **mislukt**of **geslaagd**is.

De gebruiker moet de app openen voordat het wissen wordt uitgevoerd, en het wissen kan tot 30 minuten duren nadat het verzoek is gemaakt.

Wisverzoeken die nog in behandeling zijn, worden weergegeven totdat u ze handmatig verwijdert.  Als u een verzoek tot wissen handmatig wilt verwijderen, klikt u erop met de rechtermuisknop en kiest u verwijderen.

### <a name="see-also"></a>Zie tevens
[App-gegevens beschermen met beleid voor het beheren van mobiele apps ](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[De Azure-portal gebruiken](azure-portal-for-microsoft-intune-mam-policies.md)



<!--HONumber=Dec16_HO2-->


