---
title: Uw documenten bijhouden en intrekken met gebruik van de RMS-toepassing voor delen | Azure RMS
description: Nadat u uw documenten hebt beveiligd met behulp van de RMS-toepassing voor delen, kunt u, als uw organisatie gebruikmaakt van Azure Rights Management in plaats van Active Directory Rights Management Services, bijhouden hoe mensen uw beveiligde documenten gebruiken. Indien nodig kunt u ook de toegang tot deze documenten intrekken als u ze niet langer wilt delen. Hiervoor gebruikt u op Windows-computers, Mac-computers en zelfs op tablets en telefoons de site voor documenttracking.
author: cabailey
manager: mbaldwin
ms.date: 08/10/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 61f349ce-bdd2-45c1-acc5-bc83937fb187
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 26b043f1f9e7a1e0cd00c2f31c28f7d6685f0232
ms.openlocfilehash: d27a516339a9687cb5ce117b6a2aa93730863c2d


---

# Uw documenten bijhouden en intrekken met gebruik van de RMS-toepassing voor delen

>*Van toepassing op: Azure Rights Management, Windows 10, Windows 7 met SP1, Windows 8, Windows 8.1*

Nadat u uw documenten hebt beveiligd met behulp van de RMS-toepassing voor delen, kunt u, als uw organisatie gebruikmaakt van Azure Rights Management in plaats van Active Directory Rights Management Services, bijhouden hoe mensen uw beveiligde documenten gebruiken. Indien nodig kunt u ook de toegang tot deze documenten intrekken als u ze niet langer wilt delen. Hiervoor gebruikt u op Windows-computers, Mac-computers en zelfs op tablets en telefoons de **site voor documenttracking**.

<div style="padding-top: 56.25%; position: relative; width: 100%;">
<iframe style="position: absolute;top: 0;left: 0;right: 0;bottom: 0;" width="100%" height="100%" src="https://channel9.msdn.com/Series/Information-Protection/Azure-RMS-Document-Tracking-and-Revocation/player" frameborder="0" allowfullscreen></iframe>
</div>

Wanneer u deze site opent, moet u zich aanmelden om uw documenten te volgen. Als uw organisatie beschikt over een [abonnement dat ondersteuning biedt voor documenttracking en het intrekken van de toegang](https://technet.microsoft.com/dn858608.aspx) en er een licentie voor dit abonnement aan u is toegewezen, kunt u zien wie er heeft geprobeerd om de bestanden die u hebt beveiligd, te openen en of dit is gelukt (aan de hand van verificatie) of niet. Telkens wanneer er wordt geprobeerd om het document te openen en de locatie op dat moment. Daarnaast:

-   Als u wilt stoppen met het delen van een document: klik op **Toegang intrekken**. Let op de periode waarin het document nog beschikbaar blijft, bepaal of u mensen wilt laten weten dat u de toegang intrekt tot het document dat u eerder hebt gedeeld en voeg een eigen bericht toe. Als u de toegang tot een document intrekt, wordt het document dat u hebt gedeeld, niet verwijderd, maar kunnen geautoriseerde gebruikers dit niet langer openen.

-   Als u wilt exporteren naar Excel: klik op **Exporteren naar CSV**, zodat u de gegevens kunt wijzigen en uw eigen weergaven en grafieken kunt maken.

-   Als u e-mailmeldingen wilt configureren: klik op **Instellingen** en selecteer of en hoe u een e-mail wilt ontvangen wanneer het document wordt geopend.

- Als u gedeelde documenten voor anderen wilt bijhouden en intrekken: beheerders voor Azure RMS kunnen documenten voor anderen bijhouden en intrekken door op het pictogram Beheerder te klikken. Alleen beheerders kunnen dit pictogram zien.

-   Als u vragen hebt of feedback wilt geven over de site voor documenttracking: klik op het pictogram Help voor toegang tot de [Veelgestelde vragen over het bijhouden van documenten](http://go.microsoft.com/fwlink/?LinkId=523977).

## Office gebruiken voor toegang tot de site voor documenttracking

-   Voor de Office-toepassingen Word, Excel en PowerPoint: klik op het tabblad **Start**. Klik daarna in de groep **RMS** op **Beveiligd delen** en vervolgens op **Gebruik bijhouden**.

    ![Gebruik van Office-toepassingen bijhouden bij het gebruik van de RMS-toepassing voor delen ](../media/ADRMS_MSRMSApp_OfficeToolbarTrackUsage.png)

-   Voor Outlook: klik op het tabblad **Start**. Klik daarna in de groep **RMS** op **Gebruik bijhouden**:

    ![Gebruik bijhouden selecteren in Outlook bij het gebruik van de RMS-toepassing voor delen ](../media/ADRMS_MSRMSApp_OutlookTrackUsage.png)

Als u deze opties voor RMS niet ziet, dan is het waarschijnlijk dat de RMS-toepassing voor delen niet is geïnstalleerd op uw computer, de meest recente versie niet is geïnstalleerd of de computer opnieuw moet worden gestart om de installatie te voltooien. Zie [De Rights Management-toepassing voor delen downloaden en installeren](install-sharing-app.md) voor meer informatie over het installeren van de toepassing voor delen.

> [!NOTE] 
> Als u de preview-versie van de [Azure Information Protection-client](../information-protection/info-protect-client.md), versie 1.0.233 of hoger, hebt geïnstalleerd, hebt u ook toegang tot de documenttrackingsite via de knop **Beveiligen**: 
> 
> - Klik in een Office-toepassing op het tabblad **Start** in de groep **Beveiliging** op **Beveiligen** > **Gebruik bijhouden**. 

### Overige manieren om uw documenten bij te houden en de toegang in te trekken
U kunt op Windows-computers uw documenten bijhouden met behulp van Office-toepassingen, maar er zijn ook alternatieve mogelijkheden:

-   **Een webbrowser gebruiken**: deze methode is geschikt voor alle ondersteunde apparaten.

-   **Verkenner gebruiken**: deze methode is geschikt voor Windows-computers.

-   **Een e-mailbericht in Outlook gebruiken**: deze methode is geschikt voor Windows-computers.

#### Een webbrowser gebruiken voor toegang tot de site voor documenttracking

-   Ga in een ondersteunde browser naar de [site voor documenttracking](http://go.microsoft.com/fwlink/?LinkId=529562).

    Ondersteunde browsers: het gebruik van ten minste Internet Explorer versie 10 wordt aanbevolen, maar u kunt al deze browsers gebruiken voor de site voor documenttracking:

    -   Internet Explorer: ten minste versie 10

    -   Internet Explorer 9 met ten minste MS12-037: cumulatieve beveiligingsupdate voor Internet Explorer: 12 juni 2012

    -   Mozilla Firefox: ten minste versie 12

    -   Apple Safari 5: ten minste versie 5

    -   Google Chrome: ten minste versie 18

#### Verkenner gebruiken voor toegang tot de site voor documenttracking

-   Klik met de rechtermuisknop op **Beveiligen met RMS** en selecteer vervolgens **Gebruik bijhouden**:

    ![Gebruik bijhouden selecteren in Verkenner bij het gebruik van de RMS-toepassing voor delen](../media/ADRMS_MSRMSApp_ExplorerTrackUsage.png)

#### Een e-mailbericht in Outlook gebruiken voor toegang tot de site voor documenttracking

-   Klik in een e-mailbericht op het tabblad **Bericht**. Klik vervolgens in de groep **RMS** op **Beveiligd delen** en klik op **Gebruik bijhouden**:

    ![Gebruik bijhouden selecteren in Outlook bij het gebruik van de RMS-toepassing voor delen](../media/ADRMS_MSRMSApp_OutlookMessageTrackUsage.png)

## Voorbeelden en andere instructies
Voor voorbeelden over hoe u de Rights Management-toepassing voor delen kunt gebruiken en praktische instructies, zie de volgende secties van de gebruikershandleiding voor de Rights Management-toepassing voor delen:

-   [Voorbeelden voor het gebruik van de RMS-toepassing voor delen](sharing-app-user-guide.md#examples-for-using-the-rms-sharing-application)

-   [Wat wilt u doen?](sharing-app-user-guide.md#what-do-you-want-to-do)

## Zie ook
[Gebruikershandleiding voor de Rights Management-toepassing voor delen](sharing-app-user-guide.md)



<!--HONumber=Aug16_HO4-->


