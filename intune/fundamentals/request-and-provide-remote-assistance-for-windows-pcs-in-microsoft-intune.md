---
title: Hulp op afstand voor Windows-pc's aanvragen en bieden
titleSuffix: Microsoft Intune
description: Hierin worden de stappen voor eindgebruikers en IT-beheerders beschreven om hulp op afstand te kunnen bieden voor Windows-desktops die worden beheerd als pc's en stappen om een pc op afstand te starten.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: archived
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: c2654491-5144-408a-a45a-644eb91ac1bb
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6a85cbc33ec0cf597db553506a91e61ee301419c
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71736166"
---
# <a name="request-and-provide-remote-assistance-for-windows-pcs"></a>Hulp op afstand voor Windows-pc's aanvragen en bieden

[!INCLUDE [classic-portal](../../intune-classic/includes/classic-portal.md)]

De informatie in dit onderwerp geldt alleen voor Windows-desktops die u als pc's beheert met behulp van de Intune-softwareclient.

Intune werkt met de afzonderlijk verkrijgbare [TeamViewer](https://www.teamviewer.com)-software zodat u uw gebruikers die de Intune-softwareclient uitvoeren hulp op afstand kunt bieden. Wanneer een gebruiker hulp via Microsoft Intune Center aanvraagt, ontvangt u een waarschuwing, kunt u de aanvraag accepteren en vervolgens hulp verlenen. Deze functionaliteit vervangt de bestaande Windows Hulp op afstand-functionaliteit in Intune.


## <a name="before-you-start"></a>Voordat u begint

Voordat u aanvragen voor hulp op afstand uitvoert en beantwoordt, moet u ervoor zorgen dat aan de volgende vereisten is voldaan:

- U moet zich hebben [geregistreerd voor een TeamViewer-account](https://login.teamviewer.com/LogOn#register) om u te kunnen aanmelden bij de TeamViewer-website.
- De Windows-pc's die u wilt beheren, moeten worden [beheerd door de Windows-softwareclient](../manage-windows-pcs-with-microsoft-intune.md)
- Alle Windows PC-besturingssystemen die worden ondersteund door Intune, kunnen worden beheerd.

## <a name="configure-the-teamviewer-connector"></a>De TeamViewer-connector configureren

1. Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) de optie **Beheer**.
2. Kies in de werkruimte **Beheer** de optie **TeamViewer**.
3. Kies op de pagina **TeamViewer** onder **TeamViewer-connector** de optie **Inschakelen**.
4. Lees de licentievoorwaarden in het dialoogvenster **TeamViewer inschakelen** en klik vervolgens op **Accepteren** om ze te accepteren. Als u nog geen TeamViewer-licentie hebt, kiest u **Een TeamViewer-licentie kopen**.
5. Nadat het TeamViewer-browservenster is geopend, meldt u zich aan met uw TeamViewer-referenties aan bij de site.
6. Lees en accepteer de opties op de TeamViewer-site, zodat Intune verbinding kan maken met TeamViewer.
7. Controleer in de Intune-console of het item **TeamViewer-connector** wordt weergegeven als **Ingeschakeld**.


## <a name="open-a-remote-assistance-request-end-user"></a>Een aanvraag voor hulp op afstand openen (eindgebruiker)

1. Open **Microsoft Intune Center** op een client-pc met Windows.
2. Kies onder **Hulp op afstand** de optie **Hulp op afstand aanvragen**.
3. Nadat u de aanvraag hebt goedgekeurd (zie hieronder), wordt TeamViewer geopend op de client. De gebruiker moet alle berichten accepteren die aangeven dat de webbrowser de TeamViewer-toepassing probeert te openen.
4. De gebruiker ziet een bericht waarin wordt gevraagd of u de pc mag beheren. Ze moeten dit bericht accepteren om door te kunnen gaan.
5. Tijdens de sessie van Hulp op afstand wordt er een venster weergegeven waarin de gebruiker kan zien dat u bent verbonden. Als dit venster wordt gesloten, wordt de externe sessie beëindigd.

## <a name="respond-to-a-remote-assistance-request"></a>Reageren op een aanvraag voor hulp op afstand

1. Wanneer een gebruiker een aanvraag voor hulp op afstand verzendt, kunt u deze bekijken in de werkruimte **Waarschuwingen** onder **Bewaking** > **Hulp op afstand**. Bijvoorbeeld:
   > ![Schermafbeelding van een aanvraag voor hulp op afstand](./media/request-and-provide-remote-assistance-for-windows-pcs-in-microsoft-intune/team-viewer.png)

<br>Als een aanvraag niet binnen vier uur wordt beantwoord, wordt deze verwijderd.
2. Kies **Aanvraag goedkeuren en Hulp op afstand starten** om een aanvraag te accepteren.
3. Kies in het dialoogvenster **Er wacht een nieuw verzoek om hulp op afstand** de optie **Het verzoek om hulp op afstand accepteren**. Als dat nog niet is gedaan, installeert TeamViewer alle benodigde apps op uw pc.
4. TeamViewer informeert de eindgebruiker vervolgens dat u wilt de controle over de pc wilt overnemen. Nadat de gebruiker de aanvraag heeft geaccepteerd, wordt het TeamViewer-venster geopend en kunt u de pc beheren.

Tijdens een sessie van Hulp op afstand kunt u alle beschikbare TeamViewer-opdrachten gebruiken om de externe pc te beheren. Voor hulp bij deze opdrachten, downloadt u de [Handleiding voor extern beheer](http://www.teamviewer.com/en/support/documents/) van de TeamViewer-website.

## <a name="close-the-remote-assistance-session"></a>De sessie van Hulp op afstand sluiten

Kies in het menu **Acties** van het venster **TeamViewer** de optie **Sessie beëindigen**.

## <a name="remotely-restart-a-windows-pc"></a>Een Windows-pc op afstand opnieuw opstarten
Wanneer u uw gebruikers helpt met problemen, is het mogelijk dat u af en toe de pc op afstand opnieuw moet opstarten. Gebruik de volgende stappen om een Windows-pc op afstand opnieuw op te starten.

1. Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) de optie **Groepen**&gt;**Alle apparaten** (of een andere groep die de pc bevat die u opnieuw wilt starten).

2. Selecteer een of meer pc's en klik op **Externe taken**&gt;**Computer opnieuw opstarten**.

3. Als u de status van de taak wilt weergeven, klikt u op **Externe taken** in de rechterbenedenhoek van de pagina.

4. In het dialoogvenster **Taakstatus** controleert u de huidige externe taken, de taakstatus, de apparaatnaam en eventuele gerapporteerde fouten.

## <a name="see-also"></a>Zie tevens

[Algemene beheertaken voor Windows-pc's met de Intune-softwareclient](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)
