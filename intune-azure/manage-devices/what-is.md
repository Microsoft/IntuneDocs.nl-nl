---
title: Apparaten beheren met Intune
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: meer informatie over het weergeven van apparaten die u met Intune beheert en verschillende bewerkingen die u op deze apparaten kunt uitvoeren.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: d5d7b87f58604b93ba3b65d5d264a0a5e3743d45
ms.lasthandoff: 02/18/2017


---

# <a name="what-is-microsoft-intune-device-management"></a>Wat is Microsoft Intune-apparaatbeheer? 


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

De workload **Apparaten en groepen** biedt inzicht in de apparaten die u beheert en geeft u de mogelijkheid om taken op afstand voor deze apparaten uit te voeren. Toegang krijgen tot de workload:

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apparaten en groepen** op de blade **Intune**.

    ![Werkbelasting Apparaten en groepen](./media/devices-and-groups-workload.png)

Kies een van de volgende opties:

- **Overzicht**: informatie over apparaten die u hebt ingeschreven en de besturingssystemen die op elk apparaat worden uitgevoerd.
- **Beheren**: kies **Alle apparaten** voor een overzicht van de apparaten die u beheert.
    Selecteer een van deze apparaten in de lijst om de blade <*apparaatnaam*> **Overzicht** te kiezen, waar u kunt een van de volgende opties kunt selecteren:
    - **Overzicht**: algemene informatie over het apparaat, waaronder informatie over de naam van het apparaat, de eigenaar, of het wel of geen BYOD-apparaat is en wanneer het voor het laatst is ingecheckt. Bovendien kunt u de volgend acties op afstand op het apparaat uitvoeren (niet alle acties worden door alle platformen ondersteund):
        - **Bedrijfsgegevens verwijderen**: hiermee verwijdert u alleen bedrijfsgegevens die worden beheerd door Intune. Persoonlijke gegevens worden niet van het apparaat verwijderd. Het apparaat wordt niet meer beheerd door Intune en heeft geen toegang meer tot bedrijfsresources (niet ondersteund voor Windows-apparaten die zijn gekoppeld aan Azure Active Directory).
        - **Fabrieksinstellingen**: de standaardinstellingen van het apparaat worden hersteld. Het apparaat wordt niet meer beheerd door Intune en de bedrijfsgegevens en persoonlijke gegevens worden verwijderd. U kunt deze actie niet ongedaan maken.
        - **Vergrendelen op afstand**: het apparaat wordt vergrendeld. De eigenaar van het apparaat moet de wachtwoordcode gebruiken om het apparaat te ontgrendelen. U kunt alleen een apparaat vergrendelen dat op afstand is vergrendeld met een pincode of een wachtwoord.
        - **Wachtwoordcode opnieuw instellen**: hiermee wordt een nieuwe wachtwoordcode gegenereerd voor het <*apparaat dat wordt weergegeven op de blade *> **Overzicht**.
        - **Activeringsvergrendeling overslaan**: hiermee wordt de activeringsvergrendeling van een iOS-apparaat verwijderd zonder dat u de Apple ID en het wachtwoord van de gebruiker nodig hebt. Als u de activeringsvergrendeling hebt overgeslagen, wordt de activeringsvergrendeling opnieuw ingeschakeld zodra de app Zoek mijn iPhone start. Sla de activeringsvergrendeling alleen over als u fysiek toegang hebt tot het apparaat.
        - **Modus apparaat verloren**: als een apparaat is gestolen, kunt u de modus Apparaat verloren inschakelen. Met deze modus kunt u een bericht en een telefoonnummer opgeven die op het vergrendelingsscherm van het apparaat worden weergeven.
        - **Opnieuw opstarten**: hiermee zorgt u ervoor dat het apparaat opnieuw wordt opgestart. De eigenaar van het apparaat wordt niet op de hoogte gesteld dat het apparaat opnieuw wordt opgestart. Hierdoor kan eventueel werk verloren gaan.
        ![Overzicht van apparaat](http://i.imgur.com/4Rx4VXm.png)
        
    - **Hardware**: meer gedetailleerde informatie over het apparaat, zoals de beschikbare opslagruimte, het model en de fabrikant.
    ![Beheerde hardware-inventaris van apparaten](./media/hardware-inventory.png)
    - **Gedetecteerde toepassingen**: geeft een lijst van alle apps weer die op het apparaat zijn geïnstalleerd.
    ![Knooppunt van gedetecteerde toepassingen](./media/detected-applications.png)
- **Monitor**: kies **Apparaatacties** voor een overzicht van apparaatacties die zijn uitgevoerd op apparaten die u beheert en de huidige status van deze acties.
![Apparaatbedreigingen bewaken](./media/monitor-device-actions.png)

