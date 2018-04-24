﻿---
title: Blijf op de hoogte met waarschuwingen | Microsoft Docs
description: Informatie over hoe waarschuwingen ervoor zorgen dat u op de hoogte blijft van wat er in Microsoft Intune gebeurt.
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/7/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 396ea714-0433-4bd5-a934-8d0b477f28e4
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: efad781dca4a759335b67126026bf4fed127380e


---

# <a name="get-notified-by-microsoft-intune-alerts"></a>Blijf op de hoogte met Microsoft Intune-waarschuwingen

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Waarschuwingen zorgen ervoor dat u op de hoogte blijft van wat er in Microsoft Intune gebeurt.

Waarschuwingen kunnen u bijvoorbeeld op de hoogte brengen van de volgende gebeurtenissen:

-   Een probleem met de Exchange-connector dat gevolgen heeft voor het beheer van mobiele apparaten

-   Malware die is aangetroffen op een computer

-   Een conflict tussen twee Intune-beleidsregels dat is gedetecteerd


## <a name="how-alerts-work"></a>Hoe waarschuwingen werken
Waarschuwingen worden gegenereerd op basis van **waarschuwingstypen**, een reeks vooraf geconfigureerde regels die in Intune zijn geïntegreerd. Waarschuwingen van het type **Cloudopslag heeft 10% of minder vrije ruimte**, waarschuwen u bijvoorbeeld wanneer er bijna geen schijfruimte meer is voor het opslaan van uw apps in de cloud. U kunt waarschuwingstypen in- of uitschakelen en eigenschappen configureren voor elk waarschuwingstype. Voor het bovenstaande berichttype kunt u bijvoorbeeld het volgende configureren:

-   **Status:** Of dit type waarschuwing is ingeschakeld of uitgeschakeld

-   **Ernst:** Hoe ernstig is deze waarschuwing?


|Ernst|Details|
|--------|-------|
    |![Kritieke waarschuwing](../media/Critical-Alert.jpg)|Wijst u op een ernstig probleem dat u zo snel mogelijk moet onderzoeken, bijvoorbeeld op het probleem dat er malware is gedetecteerd op een computer.|
    |![Waarschuwing](../media/Warning-Alert.jpg)|Wijst u op een probleem dat momenteel niet ernstig is, maar wel ernstig kan worden als u er geen aandacht aan besteedt, bijvoorbeeld op het feit dat er beveiligingsupdates beschikbaar zijn die gereed zijn om te worden geïnstalleerd.|
    |![Informatieve waarschuwing](../media/Informational-Alert.jpg)|Geeft informatie aan die niet essentieel is voor uw activiteiten, bijvoorbeeld dat er een nieuwe versie van de Exchange-connector beschikbaar is.|

Overige waarschuwingstypen bevatten mogelijk andere items die u kunt configureren, zoals het percentage apparaten dat door een probleem moet worden getroffen voordat er een waarschuwing wordt gegenereerd.

**Als aan de criteria in een waarschuwingstype wordt voldaan, wordt er een waarschuwing gegenereerd en weergegeven in de Intune-beheerconsole.**

Bovendien kunt u Intune zodanig configureren dat u per e-mail wordt gewaarschuwd wanneer er een waarschuwing wordt gegenereerd.

## <a name="set-up-alerts"></a>Waarschuwingen instellen
Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) de opties **Beheer** &gt; **Waarschuwingen en meldingen** en kies vervolgens een van de deze taken:

|Taak|Beschrijving|
|--------|---------------|
|**Waarschuwingstypen**|Kies het waarschuwingstype dat u wilt configureren en voer vervolgens een van de deze handelingen uit:<br /><br />Kies **Configureren**. Configureer de gewenste instellingen in het dialoogvenster **Waarschuwingstype configureren** en kies vervolgens **OK**.<br /><br />Schakel de waarschuwing **in** of **uit**.<br /><br />Vouw het knooppunt **Waarschuwingstypen** uit en kies een categorie om alleen de waarschuwingstypen in die categorie weer te geven.|
|**Ontvangers**|Kies **Toevoegen** om een nieuw e-mailadres toe te voegen voor het ontvangen van de e-mailmeldingen die u instelt.<br /><br />U kunt ook bestaande ontvangers **bewerken** of **verwijderen** .<br /><br />Als u meldingen wilt ontvangen, moet u dit e-mailadres ook toevoegen als ontvanger onder **Meldingsregels**.|
|**Meldingsregels**|Hiermee configureert u regels die definiëren naar wie een e-mailmelding wordt verzonden. U hebt de volgende mogelijkheden:<br /><br />**Een bestaande regel kiezen**: kies een regel en kies vervolgens **Ontvangers selecteren**. U kunt vervolgens alle ontvangers selecteren die een e-mailbericht ontvangen wanneer er een waarschuwing wordt gegenereerd die aan deze regel voldoet.<br /><br />**Maak een nieuwe regel**: voer een naam in voor de regel, selecteer de waarschuwingscategorie en de ernst van de waarschuwing die van toepassing zijn op de regel, selecteer de apparaatgroepen waarop de regel van toepassing is en selecteer de gebruikers die een e-mail ontvangen wanneer er een waarschuwing wordt gegenereerd.<br /><br />U kunt een bestaande regel ook **inschakelen**, **uitschakelen**, **bewerken**en **verwijderen** .|

## <a name="working-with-alerts"></a>Werken met waarschuwingen
Gebruik de volgende opties om met waarschuwingen in de Intune-beheerconsole te werken.

|Optie|Beschrijving|
|----------|---------------|
|**Actieve waarschuwingen weergeven**|Kies een van de volgende mogelijkheden:<br /><br />**Een samenvatting van waarschuwingen weergeven**: de ernstigste fouten worden weergegeven in het deelvenster Waarschuwingen van de werkruimte **Dashboard**. Kies het deelvenster voor gedetailleerde informatie.<br /><br />Daarnaast vindt u een samenvatting van de waarschuwingen op de pagina **Overzicht** van de werkruimte **Waarschuwingen** .<br /><br />**Alle waarschuwingen weergeven**: kies in de werkruimte **Waarschuwingen** de optie **Alle waarschuwingen**.|
|**Meldingen weergeven**|Kies een van de volgende mogelijkheden:<br /><br />Kies in de werkruimte **Dashboard** de optie **Meldingen**.<br /><br />Kies in de werkruimte **Waarschuwingen** achtereenvolgens de opties **Alle waarschuwingen** &gt; **Meldingen**.|
|**Een waarschuwing sluiten**|Kies in de lijst met waarschuwingen de waarschuwing die u wilt sluiten en kies vervolgens **Waarschuwing sluiten**.<br /><br />Gesloten waarschuwingen worden na 90 dagen definitief verwijderd.|
|**Een gesloten waarschuwing opnieuw activeren**|Stel in de lijst met waarschuwingen de vervolgkeuzelijst **Filters** in op **Gesloten**.<br /><br />Selecteer in de lijst met gesloten waarschuwingen de waarschuwing die u opnieuw wilt activeren en kies vervolgens **Waarschuwing opnieuw activeren**.|
Intune-waarschuwingen blijven actief tot:

-   Het probleem dat de waarschuwing heeft veroorzaakt, is opgelost

-   U de waarschuwing handmatig sluit

-   45 dagen zijn verstreken nadat de waarschuwing werd gegenereerd

> [!TIP]
> Als dezelfde waarschuwing wordt gegenereerd door apparaten waarop verschillende besturingssystemen worden uitgevoerd, ziet u mogelijk meerdere versies van dezelfde waarschuwing in de lijst met waarschuwingen.

### <a name="see-also"></a>Zie tevens
[Bewaking en rapporten voor Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


