---
title: Apparaten beheren met Intune
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: meer informatie over het weergeven van apparaten die u met Intune beheert en verschillende bewerkingen die u op deze apparaten kunt uitvoeren.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/13/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: 25a46754f6c7e44b3f4fef7e8eef015cf559e31f
ms.lasthandoff: 04/19/2017


---

# <a name="what-is-microsoft-intune-device-management"></a>Wat is Microsoft Intune-apparaatbeheer?


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

De workload **Apparaten** biedt inzicht in de apparaten die u beheert en geeft u de mogelijkheid om taken op afstand voor deze apparaten uit te voeren. Toegang krijgen tot de workload:

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apparaten** op de blade **Intune**.

Kies een van de volgende opties:

- **Overzicht**: informatie over apparaten die u hebt ingeschreven en de besturingssystemen die op elk apparaat worden uitgevoerd.
- **Beheren**: kies **Alle apparaten** voor een overzicht van de apparaten die u beheert.
    Selecteer een van deze apparaten in de lijst om de blade <*apparaatnaam*> **Overzicht** te kiezen, waar u kunt een van de volgende opties kunt selecteren:
    - **Overzicht**: algemene informatie over het apparaat, waaronder informatie over de naam van het apparaat, de eigenaar, of het wel of geen BYOD-apparaat is en wanneer het voor het laatst is ingecheckt.

    - **Hardware**: meer gedetailleerde informatie over het apparaat, zoals de beschikbare opslagruimte, het model en de fabrikant.
    ![Beheerde hardware-inventaris van apparaten](./media/hardware-inventory.png)
    - **Gedetecteerde toepassingen**: geeft een lijst van alle apps weer die op het apparaat zijn geïnstalleerd.
    ![Knooppunt van gedetecteerde toepassingen](./media/detected-applications.png)
- **Monitor**: kies **Apparaatacties** voor een overzicht van apparaatacties die zijn uitgevoerd op apparaten die u beheert en de huidige status van deze acties.
![Apparaatbedreigingen bewaken](./media/monitor-device-actions.png)
- **Help en ondersteuning**: bevat koppelingen naar documentatie over probleemoplossing en ondersteuning.

## <a name="available-device-actions"></a>Beschikbare apparaatbedreigingen

Bovendien kunt u de volgend acties op afstand op het apparaat uitvoeren (niet alle acties worden door alle platformen ondersteund):

### <a name="remove-company-data"></a>**Bedrijfsgegevens verwijderen**
Hiermee verwijdert u alleen bedrijfsgegevens die worden beheerd door Intune. Persoonlijke gegevens worden niet van het apparaat verwijderd. Het apparaat wordt niet meer beheerd door Intune en heeft geen toegang meer tot bedrijfsresources (niet ondersteund voor Windows-apparaten die zijn gekoppeld aan Azure Active Directory).

### <a name="factory-reset"></a>**Fabrieksinstellingen terugzetten**
Hiermee worden de standaardinstellingen van het apparaat hersteld. Het apparaat wordt niet meer beheerd door Intune en de bedrijfsgegevens en persoonlijke gegevens worden verwijderd. U kunt deze actie niet ongedaan maken.

### <a name="remote-lock"></a>**Vergrendelen op afstand**
Hiermee wordt het apparaat vergrendeld. De eigenaar van het apparaat moet de wachtwoordcode gebruiken om het apparaat te ontgrendelen. U kunt alleen een apparaat vergrendelen dat op afstand is vergrendeld met een pincode of een wachtwoord.

### <a name="reset-passcode"></a>**Wachtwoordcode opnieuw instellen**
Hiermee wordt een nieuwe wachtwoordcode gegenereerd voor het <*apparaat dat wordt weergegeven op de blade*> **Overzicht**.

### <a name="bypass-activation-lock"></a>**Activeringsvergrendeling overslaan**
Hiermee verwijdert u de activeringsvergrendeling van een iOS-apparaat zonder dat u de Apple ID en het wachtwoord van de gebruiker nodig hebt. Als u de activeringsvergrendeling hebt overgeslagen, wordt de activeringsvergrendeling opnieuw ingeschakeld zodra de app Zoek mijn iPhone start. Sla de activeringsvergrendeling alleen over als u fysiek toegang hebt tot het apparaat.

### <a name="fresh-start"></a>**Nieuwe start**

Hiermee verwijdert u alle apps die zijn geïnstalleerd op een computer met Windows 10 met de makersupdate. De computer wordt vervolgens automatisch bijgewerkt naar de nieuwste versie van Windows.
U kunt dit gebruiken om vooraf geïnstalleerde OEM-apps te verwijderen die vaak op nieuwe computers staan. U kunt configureren of de gebruikersgegevens bewaard blijven wanneer u deze actie uitvoert. In dit geval worden apps en instellingen verwijderd, maar de inhoud van de basismap Gebruikers blijft bewaard.


### <a name="lost-mode"></a>**Modus Apparaat verloren**
Als een iOS-apparaat is verloren of gestolen, kunt u de modus Apparaat verloren inschakelen. Met deze modus kunt u een bericht en een telefoonnummer opgeven die op het vergrendelingsscherm van het apparaat worden weergeven. U doet dit als volgt:
1.    Kies **Meer** > **modus Apparaat verloren** op de eigenschappenblade voor een iOS-apparaat.
2.    Schakel op de blade **modus Apparaat verloren** de modus Apparaat verloren in, voer het bericht in dat wordt weergegeven en voeg indien gewenst een telefoonnummer toe.
3.    Klik op **OK**.
Wanneer u de modus Apparaat verloren inschakelt, wordt het gebruik van het apparaat volledig geblokkeerd. De gebruiker krijgt pas weer toegang tot het apparaat als de modus Apparaat verloren is uitgeschakeld. Als de modus Apparaat verloren is ingeschakeld, kunt u de bewerking **Apparaat zoeken** uitvoeren om te weten te komen waar het apparaat is.
Als u de modus Apparaat verloren wilt gebruiken, moet het apparaat een iOS-apparaat in bedrijfseigendom zijn, dat via DEP is ingeschreven en waarop de supervisiemodus is ingeschakeld.

### <a name="locate-device"></a>**Apparaat zoeken**
Gebruik deze externe actie om de locatie van een verloren of gestolen iOS-apparaat op een kaart weer te geven. Het apparaat moet een iOS-apparaat in bedrijfseigendom zijn, dat via DEP is ingeschreven en waarop de supervisiemodus is ingeschakeld. Voordat u deze actie gebruikt, moet op het apparaat de modus Apparaat verloren zijn ingeschakeld.
1.    Kies **Meer** > **Apparaat zoeken** op de eigenschappenblade voor een iOS-apparaat.
2.    Als het apparaat is gevonden, wordt de locatie weergegeven op de blade **Apparaat zoeken**.
    ![De blade Apparaat zoeken](./media/locate-device.png)

>[!NOTE]
>De afstand die u op de kaart kunt inzoomen, is om privacyredenen beperkt.

### <a name="restart"></a>**Opnieuw opstarten**
Hiermee zorgt u ervoor dat het apparaat opnieuw wordt opgestart. De eigenaar van het apparaat wordt niet op de hoogte gesteld dat het apparaat opnieuw wordt opgestart. Hierdoor kan eventueel werk verloren gaan.


## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Beveiligings- en privacygegevens voor de acties modus Apparaat verloren en Apparaat zoeken
- Er wordt geen locatie-informatie over het apparaat verzonden naar Intune voordat u deze actie hebt ingeschakeld.
- Wanneer u de actie Apparaat zoeken gebruikt, worden de lengte- en breedtegraadcoördinaten van het apparaat verzonden naar Intune en weergegeven in Azure Portal.
- De gegevens worden gedurende 24 uur opgeslagen, waarna ze worden verwijderd. U kunt de locatiegegevens niet handmatig verwijderen.
- De locatiegegevens worden versleuteld terwijl ze zijn opgeslagen en terwijl ze worden verzonden.
- Wanneer u de modus Apparaat verloren configureert, wordt aangeraden in het bericht dat op het vergrendelingsscherm wordt weergegeven de melding op te nemen dat de locatie van het apparaat kan worden bepaald.

