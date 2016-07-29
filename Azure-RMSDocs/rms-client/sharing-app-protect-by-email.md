---
title: Een bestand beveiligen dat u deelt via e-mail met behulp van de Rights Management-toepassing voor delen | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 07/13/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 4c1cd1d3-78dd-4f90-8b37-dcc9205a6736
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 67129d6cdac124947fc07aa4d42523686227752e
ms.openlocfilehash: 13f44e93ee9c1c0583bd75121aec638fee09b748


---

# Een bestand beveiligen dat u deelt via e-mail met behulp van de Rights Management-toepassing voor delen.

*Van toepassing op: Active Directory Rights Management Services, Azure Rights Management, Windows 10, Windows 7 met SP1, Windows 8, Windows 8.1*

Wanneer u een bestand beveiligt dat u deelt via e-mail, wordt een nieuwe versie van het oorspronkelijke bestand gemaakt. Het oorspronkelijke bestand blijft onbeveiligd en de nieuwe versie is beveiligd en wordt automatisch toegevoegd aan een e-mailbericht dat u vervolgens verzendt.

In sommige gevallen (voor de bestanden die zijn gemaakt in Microsoft Word, Excel en PowerPoint), worden met de RMS-toepassing voor delen twee versies van het bestand gemaakt en toegevoegd aan het e-mailbericht. De tweede versie van het bestand heeft de bestandsnaamextensie **.ppdf**. Dit is een pdf-schaduwkopie van het bestand. Deze versie van het bestand zorgt ervoor dat ontvangers het bestand altijd kunnen lezen, zelfs als ze niet dezelfde toepassing hebben geïnstalleerd die u hebt gebruikt om het bestand te maken. Dit is vaak het geval wanneer mensen hun e-mail op mobiele apparaten lezen en hun e-mailbijlagen willen bekijken. Ze hebben alleen maar de RMS-toepassing voor delen nodig om het bestand te openen. Vervolgens kan het bijgevoegde bestand worden gelezen, maar ze kunnen dit niet wijzigen totdat de andere versie van het bestand wordt geopend met een toepassing die RMS ondersteunt.

Als uw organisatie Azure RMS gebruikt, kunt u de bestanden bijhouden die u beveiligt door te delen:

-   Selecteer een optie voor het ontvangen van e-mailberichten wanneer iemand deze beveiligde bijlagen wil openen. Telkens wanneer het bestand wordt geopend, krijgt u een melding van wie het bestand probeerde te openen en wanneer en of het ze is gelukt (ze zijn geverifieerd) of niet.

-   Gebruik de site voor documenttracking. U kunt zelf stoppen met het bestand te delen door de toegang tot het bestand in te trekken op de site voor documenttracking. Zie [Uw documenten bijhouden en intrekken met gebruik van de RMS-toepassing voor delen](sharing-app-track-revoke.md) voor meer informatie.

## Outlook gebruiken: een bestand beveiligen dat u deelt via e-mail

1.  Maak uw e-mailbericht en voeg het bestand bij. Klik vervolgens op het tabblad **Bericht** in de groep **RMS** op **Beveiligd delen**. Klik vervolgens nogmaals op **Beveiligd delen**:

    ![Invoegtoepassing Outlook voor de RMS-toepassing voor delen](../media/ADRMS_MSRMSApp_SP_OutlookToolbar.png)

    Als u deze knop niet ziet, is het waarschijnlijk dat de RMS-toepassing voor delen niet op uw computer is geïnstalleerd, de meest recente versie niet is geïnstalleerd of uw computer opnieuw moet worden opgestart om de installatie te voltooien. Zie [De Rights Management-toepassing voor delen downloaden en installeren](install-sharing-app.md) voor meer informatie over het installeren van de toepassing voor delen.

2.  Geef in het [dialoogvenster Beveiligd delen](sharing-app-dialog-box.md) de gewenste opties voor dit bestand op en klik vervolgens op **Nu verzenden**.

### Andere manieren om een bestand te beveiligen dat u deelt via e-mail
Naast het delen van een beveiligd bestand via Outlook kunt u ook deze alternatieve methoden gebruiken:

-   Via Verkenner: deze methode werkt voor alle bestanden.

-   Vanuit een Office-toepassing: deze methode werkt voor toepassingen die de RMS-toepassing voor delen ondersteunt met behulp van de Office-invoegtoepassing, zodat u de **RMS**-groep op het lint ziet.

#### Met Verkenner of een Office-toepassing: een bestand beveiligen dat u deelt via e-mail

1.  Gebruik een van de volgende opties:

    -   Voor Verkenner: klik met de rechtermuisknop op het bestand, selecteer **Beveiligen met RMS** en selecteer vervolgens **Beveiligd delen**.

        ![Menuoptie Beveiligd delen](../media/ADRMS_MSRMSApp_ShareProtectedMenu.png)

    -   Voor de Office-toepassingen Word, Excel en PowerPoint: zorg ervoor dat u het bestand eerst opslaat. Klik vervolgens op het tabblad **Start** in de groep **RMS** op **Beveiligd delen**. Klik vervolgens nogmaals op **Beveiligd delen**:

        ![Invoegtoepassing Office-werkbalk](../media/ADRMS_MSRMSApp_SP_OfficeToolbar.png)

    Als u deze opties voor beveiliging niet ziet, is het waarschijnlijk dat de RMS-toepassing voor delen niet op uw computer is geïnstalleerd, de meest recente versie niet is geïnstalleerd of uw computer opnieuw moet worden gestart om de installatie te voltooien. Zie [De Rights Management-toepassing voor delen downloaden en installeren](install-sharing-app.md) voor meer informatie over het installeren van de toepassing voor delen.

2.  Geef in het [dialoogvenster Beveiligd delen](sharing-app-dialog-box.md) de gewenste opties voor dit bestand op en klik vervolgens op **Verzenden**.

3.  U ziet kort een dialoogvenster waarin wordt uitgelegd dat het bestand wordt beveiligd. Vervolgens ziet u een e-mailbericht waarin aan de ontvangers wordt uitgelegd dat de bijlagen zijn beveiligd met Microsoft RMS en dat zij zich moeten aanmelden. Wanneer ze op de koppeling klikken om zich aan te melden, zien ze instructies en koppelingen voor het openen van de beveiligde bijlage.

    Voorbeeld:

    ![E-mailbericht voor Azure RMS](../media/ADRMS_MSRMSApp_EmailMessage.PNG)

    Vraagt u zich af: [Wat is het .ppdf-bestand dat automatisch wordt gemaakt?](sharing-app-dialog-box.md#what-s-the-ppdf-file-that-s-automatically-created)

4.  Optioneel: u kunt dit e-mailbericht zelf wijzigen. U kunt bijvoorbeeld het onderwerp of de tekst in het bericht wijzigen of tekst toevoegen.

    > [!WARNING]
    > Hoewel u personen aan dit bericht kunt toevoegen of eruit verwijderen, worden de machtigingen die u in het dialoogvenster **Beveiligd delen** voor de bijlage hebt opgegeven, niet gewijzigd. Als u deze machtigingen wilt wijzigen, bijvoorbeeld een nieuwe persoon toestemming geven om het bestand te openen, sluit dan het e-mailbericht zonder op te slaan of te verzenden en ga terug naar stap 1.

5.  Verzend het e-mailbericht.

## Voorbeelden en andere instructies
Voor voorbeelden over hoe u de Rights Management-toepassing voor delen kunt gebruiken en praktische instructies, zie de volgende secties van de gebruikershandleiding voor de Rights Management-toepassing voor delen:

-   [Voorbeelden voor het gebruik van de RMS-toepassing voor delen](sharing-app-user-guide.md#examples-for-using-the-rms-sharing-application)

-   [Wat wilt u doen?](sharing-app-user-guide.md#what-do-you-want-to-do)

## Zie ook
[Gebruikershandleiding voor de Rights Management-toepassing voor delen](sharing-app-user-guide.md)



<!--HONumber=Jul16_HO3-->


