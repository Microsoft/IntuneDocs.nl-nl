---
title: Problemen met app-installatie oplossen
titlesuffix: Microsoft Intune
description: Gebruik het Microsoft Intune-deelvenster voor probleemoplossing om u te helpen bij het oplossen van installatieproblemen.
keywords: ''
author: ErikRe
ms.author: erikre
manager: dougeby
ms.date: 07/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: b613f364-0150-401f-b9b8-2b09470b34f4
ms.reviewer: mghadial
ms.custom: intune-azure
ms.openlocfilehash: c1c2a37103f8fedc09a70b4387aae3f472dfb636
ms.sourcegitcommit: dc8b6f802cca7895a19ec38bec283d4b3150d213
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/19/2018
ms.locfileid: "39138676"
---
# <a name="troubleshoot-app-installation-issues"></a>Problemen met app-installatie oplossen

Op apparaten die met Microsoft Intune MDM worden beheerd, mislukken app-installaties wel eens. Als deze apps niet kunnen worden geïnstalleerd, is het soms lastig om de reden van het probleem te achterhalen of om het probleem op te lossen. Microsoft Intune biedt details van app-installatiefouten. Zo kunnen helpdeskmedewerkers en Intune-beheerders app-informatie bekijken om de hulpverzoeken van gebruikers te beantwoorden. Het deelvenster voor probleemoplossing binnen Intune biedt foutdetails, waaronder details over beheerde apps op een apparaat van een gebruiker. Er worden details van de end-to-end-levenscyclus van een app van elk afzonderlijk apparaat getoond in het deelvenster **Beheerde apps**. U kunt installatieproblemen bekijken, zoals wanneer de app was gemaakt, bewerkt, ingericht op en geleverd aan een apparaat. 

## <a name="to-review-app-troubleshooting-details"></a>Details voor app-probleemoplossing weergeven

Intune biedt details van app-probleemoplossing op basis van de geïnstalleerde apps op een specifiek apparaat van een gebruiker.

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies in het deelvenster **Intune** de optie **Problemen oplossen**.
4. Klik op **Gebruiker selecteren** om een gebruiker te selecteren waarvoor er problemen opgelost moeten worden. Het deelvenster **Gebruikers selecteren** wordt weergegeven.
5. Selecteer de gebruiker door een naam of e-mailadres te typen. Klik onder aan het deelvenster op **Selecteren**. De informatie voor het oplossen van problemen voor de gebruiker wordt weergegeven in het deelvenster **Probleemoplossing**. 
6. Selecteer in de lijst **Apparaten** het apparaat waarbij u problemen wilt oplossen.
    ![Het deelvenster Intune-probleemoplossing.](media/troubleshoot-app-install-01.png)
7. Selecteer **Beheerde apps** in het deelvenster van het geselecteerde apparaat. Er wordt een lijst met beheerde apps weergegeven.
    ![Details van een specifiek apparaat dat door Intune wordt beheerd.](media/troubleshoot-app-install-02.png)
8. Selecteer een app in de lijst waarbij de **Installatiestatus** een fout aangeeft.
    ![Een geselecteerde app waarbij een installatiefout wordt aangegeven.](media/troubleshoot-app-install-03.png)

    > [!Note]  
    > Dezelfde app kan worden toegewezen aan meerdere groepen, maar met verschillende beoogde acties (intenties) voor de app. Een opgeloste intentie voor een app wordt bijvoorbeeld weergegeven als **uitgesloten** als de app voor een gebruiker is uitgesloten tijdens de app-toewijzing. Raadpleeg [Hoe conflicten tussen app-intenties worden opgelost](apps-deploy.md#how-conflicts-between-app-intents-are-resolved) voor meer informatie.<br><br>
    > Momenteel worden apps op basis van het besturingssysteemplatform door Intune niet weggefilterd.

De details van de app-installatieproblemen geven het probleem aan. U kunt deze details gebruiken om de beste actie vast te stellen waarmee het probleem wordt opgelost. Raadpleeg [Error Codes For Troubleshooting App Installation Issues](https://blogs.technet.microsoft.com/intunesupport/2018/05/15/error-codes-for-troubleshooting-app-installation-issues) (Foutcodes voor oplossing van app-installatieproblemen) voor meer informatie over het oplossen van app-installatieproblemen.

> [!Note]  
> U kunt het deelvenster **Probleemoplossing** ook openen door in uw browser naar het volgende adres te gaan: [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting).

## <a name="next-steps"></a>Volgende stappen

- Raadpleeg [De portal voor probleemoplossing gebruiken om gebruikers in uw bedrijf te helpen](help-desk-operators.md) voor meer informatie over probleemoplossing met Intune. 
- Ontdek meer over bekende problemen in Microsoft Intune. Zie [Bekende problemen in Microsoft Intune](known-issues.md) voor meer informatie.
- Extra hulp nodig? Zie [Ondersteuning voor Microsoft Intune krijgen](get-support.md).
