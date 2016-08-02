---
title: Machtigingen wijzigen voor bestanden die zijn beveiligd door Rights Management | Azure RMS
description: Wanneer een bestand is beveiligd met Rights Management, kunt u de machtigingen wijzigen door het bestand opnieuw te beveiligen en op te geven welke gebruikers toegang hebben tot het bestand en welke machtigingen u aan hen wilt geven.
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 07/27/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 5ac121b3-d7a0-40e4-8fe7-90bf4cf796f1
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e65fe3e6994352296cdf58d4b53de421389790f7
ms.openlocfilehash: 492f651f9234a8428a0f39da93b332a552894993


---

# Machtigingen voor bestanden wijzigen die door Rights Management worden beveiligd

*Van toepassing op: Active Directory Rights Management Services, Azure Rights Management, Windows 10, Windows 7 met SP1, Windows 8, Windows 8.1*

Wanneer een bestand is beveiligd met Rights Management, kunt u de machtigingen wijzigen door het bestand opnieuw te beveiligen en op te geven welke gebruikers toegang hebben tot het bestand en welke machtigingen u aan hen wilt geven.

> [!IMPORTANT]
> Dit is een complete wijziging. U beveiligt het bestand opnieuw met de reeks machtigingen die u wilt toekennen.
> 
>  Als een bestand bijvoorbeeld zo wordt beveiligd dat alleen medewerkers van de marketingafdeling het bestand kunnen openen en u wilt instellen dat ook medewerkers van de verkoopafdeling het bestand kunnen openen, moet u het bestand opnieuw beveiligen, zodat zowel de verkoop- als marketingafdeling het bestand kan openen.
>
> Als u een machtiging wilt toevoegen of verwijderen, kunt u dit niet zomaar opgeven. U moet alle machtigingen voor bepaalde personen opgeven.

Als u de eigenaar bent van het bestand dat u opnieuw wilt beveiligen (bijvoorbeeld wanneer u het bestand oorspronkelijk hebt beveiligd met behulp van de toepassing voor delen), hebt u automatisch machtigingen om het bestand opnieuw te beveiligen. Als u niet de eigenaar van het bestand bent, hebt u mogelijk geen machtigingen om het bestand opnieuw te beveiligen, afhankelijk van de huidige machtigingen voor het bestand. U hebt het [gebruiksrecht Volledig beheer](../deploy-use/configure-usage-rights.md#usage-rights-and-descriptions) nodig om een bestand opnieuw te beveiligen.

Als iemand anders het bestand bijvoorbeeld heeft beveiligd met de Rights Management-toepassing voor delen en er een groep is opgegeven waarvan u deel uitmaakt en **mede-eigenaar bent**, kunt u het bestand wel opnieuw beveiligen. Als deze persoon echter uw naam of de groep waarvan u deel uitmaakt, niet heeft opgegeven, of **Revisor - Weergeven en bewerken** heeft geselecteerd of een sjabloon gebruikt waarmee u geen machtigingen kunt verwijderen, kunt u het bestand niet opnieuw beveiligen. De snelste manier om te ontdekken wat uw mogelijkheden zijn, is door het bestand opnieuw te beveiligen.

Zie [De beveiliging van een bestand verwijderen](sharing-app-remove-protection.md) als u alle machtigingen wilt verwijderen zodat het bestand niet meer is beveiligd.

## Een bestand ter plaatse opnieuw beveiligen

1.  Selecteer in Verkenner een bestand dat moet worden beveiligd. Klik met de rechtermuisknop op **Beschermen met RMS** en selecteer vervolgens **Direct beveiligen**. Bijvoorbeeld:

    ![Menuoptie Direct beveiligen](../media/ADRMS_MSRMSApp_SP_CompanyDefined.png)

    > [!NOTE]
    > Als u de optie **Beschermen met RMS** niet ziet, is de RMS-toepassing voor delen waarschijnlijk niet geïnstalleerd op uw computer of moet uw computer opnieuw worden opgestart om de installatie te voltooien. Zie [De Rights Management-toepassing voor delen downloaden en installeren](install-sharing-app.md) voor meer informatie over het installeren van de RMS-toepassing voor delen.

2.  Voer een van de volgende handelingen uit:

    -   Selecteer een beleidssjabloon: dit zijn vooraf gedefinieerde machtigingen voor mensen in uw organisatie om toegang en gebruik te beperken. Als de naam van uw bedrijf bijvoorbeeld Contoso Ltd is, ziet u mogelijk het volgende: **Contoso Ltd - alleen vertrouwelijke weergave** Als dit de eerste keer is dat u een bestand op deze computer beveiligt, moet u eerst **Door bedrijf gedefinieerde beveiliging** selecteren om de sjablonen te downloaden.

        De volgende keer dat u op de optie **Direct beveiligen** klikt, worden er maximaal 10 sjablonen weergegeven om uit te kiezen. Als er meer dan 10 sjablonen beschikbaar zijn en de gewenste sjabloon niet wordt weergegeven, klikt u op **Door bedrijf gedefinieerde beveiliging** om alle sjablonen te downloaden en weer te geven.

        Wanneer u een beleidssjabloon selecteert, kunt u ook meerdere bestanden en een map beveiligen. Wanneer u een map selecteert, worden alle bestanden in die map automatisch geselecteerd voor beveiliging, maar nieuwe bestanden die u in die map maakt zullen niet automatisch worden beveiligd.

    -   Selecteer **Aangepaste machtigingen**: selecteer deze optie als de sjablonen niet het beveiligingsniveau bieden dat u nodig hebt of als u de beveiligingsopties expliciet zelf wilt instellen. Geef in het [dialoogvenster Beveiliging instellen](sharing-app-dialog-box.md) de gewenste opties voor dit bestand op en klik vervolgens op **Toepassen**.

3. Als u geen machtigingen hebt om het bestand opnieuw te beveiligen, verschijnt het bericht **Inhoud kan niet worden beveiligd** en wordt het e-mailadres weergegeven van de contactpersoon (de eigenaar van het document), zodat de contactpersoon de machtigingen voor u kan wijzigen.

    Als u geen machtigingen hebt om het bestand opnieuw te beveiligen, wordt kort een dialoogvenster weergegeven waarin wordt uitgelegd dat het bestand wordt beveiligd. Vervolgens keert u terug naar Bestandenverkenner. Het geselecteerde bestand of de geselecteerde bestanden zijn nu beveiligd. 

> [!NOTE]
> Voordat u het bestand opnieuw kunt beveiligen, moet met RMS worden bevestigd dat u hiertoe gemachtigd bent door uw gebruikersnaam en wachtwoord te controleren. In sommige gevallen kan dit mogelijk in de cache worden opgeslagen en wordt u niet gevraagd om uw aanmeldgegevens. In andere gevallen wordt u gevraagd uw aanmeldgegevens op te geven.
>
> Als uw organisatie geen Azure Rights Management (Azure RMS) of AD RMS gebruikt, kunt u een gratis account aanvragen waarmee uw referenties worden geaccepteerd zodat u bestanden kunt openen die beveiligd zijn met RMS:
>
> -   Als u zich wilt aanmelden voor dit account, klikt u op de koppeling om u aan te melden voor [RMS voor personen](http://go.microsoft.com/fwlink/?LinkId=309469).
>
>     Gebruik het e-mailadres van uw bedrijf in plaats van uw persoonlijke e-mailadres als u zich aanmeldt. Als u zich aanmeldt omdat u een beveiligde bijlage hebt ontvangen, gebruik dan hetzelfde e-mailadres als waarnaar de bijlage is verzonden.
> -   Zie voor meer informatie [RMS voor personen en Azure Rights Management](../understand-explore/rms-for-individuals.md).

## Een bestand opnieuw beveiligen dat u per e-mail hebt verzonden

Als u de machtigingen wilt wijzigen voor een bestand dat u per e-mail hebt verzonden:

- **Zorgen dat meer mensen het e-mailbericht lezen**: verzend het bestand per e-mail naar deze personen op basis van de instructies in [Een bestand beveiligen dat u per e-mail deelt](sharing-app-protect-by-email.md).

- **De machtigingen voor het bestand wijzigen**: verzend het bestand opnieuw op basis van de instructies in [Een bestand beveiligen dat u per e-mail deelt](sharing-app-protect-by-email.md) en selecteer de nieuwe machtigingen. 

    Aangezien u de vorige machtigingen niet kunt verwijderen voor het oorspronkelijk verzonden e-mailbericht, moet u deze vervangen door een nieuwe versie. U kunt het eerder verzonden e-mailbericht intrekken, zodat de ontvanger die versie van het document niet meer kan openen. U kunt bijvoorbeeld een e-mailbericht intrekken als u beperkingen in de machtigingen wilt aanbrengen (bijvoorbeeld door personen te verwijderen voor toegang tot het bestand of wanneer personen geen wijzigingen meer in het bericht mogen aanbrengen).

    Zie [Uw documenten bijhouden en intrekken](sharing-app-track-revoke.md) als u een verzonden e-mailbericht wilt intrekken.


## Voorbeelden en andere instructies
Voor voorbeelden over hoe u de Rights Management-toepassing voor delen kunt gebruiken en praktische instructies, zie de volgende secties van de gebruikershandleiding voor de Rights Management-toepassing voor delen:

-   [Voorbeelden voor het gebruik van de RMS-toepassing voor delen](sharing-app-user-guide.md#examples-for-using-the-rms-sharing-application)

-   [Wat wilt u doen?](sharing-app-user-guide.md#what-do-you-want-to-do)

## Zie ook
[Gebruikershandleiding voor de Rights Management-toepassing voor delen](sharing-app-user-guide.md)



<!--HONumber=Jul16_HO4-->


