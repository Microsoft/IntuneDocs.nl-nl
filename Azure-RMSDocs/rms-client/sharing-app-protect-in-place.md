---
title: Een bestand beveiligen op een apparaat (direct beveiligen) met behulp van de Rights Management-toepassing voor delen | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 05/09/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 33920329-5247-4f6c-8651-6227afb4a1fa
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c611fa8a846612fed238e59e5077be67f6f9531a
ms.openlocfilehash: 7cf6ecb95374c080b9b2e94f948ec53ea5e6bb46


---

# Een bestand op een apparaat beveiligen (direct beveiligen) met de Rights Management-toepassing voor delen

*Van toepassing op: Active Directory Rights Management Services, Azure Rights Management, Windows 10, Windows 7 met SP1, Windows 8, Windows 8.1*

Wanneer u een bestand in-place beveiligt, dan vervangt deze het oorspronkelijke, niet-beveiligde bestand. Vervolgens kunt u het bestand laten waar het is, kopiëren naar een andere map of apparaat, of de map waar het in zit delen en het bestand blijft beveiligd. U kunt het beveiligde bestand ook in een e-mailbericht bijsluiten, hoewel de aanbevolen manier om een beveiligd bestand via e-mail te delen rechtstreeks vanuit Verkenner of een Office-toepassing is (zie [Een bestand beveiligen dat u per e-mail deelt met de Rights Management-toepassing voor delen](sharing-app-protect-by-email.md)).

> [!TIP]
> Als u fouten ziet wanneer u bestanden probeert te beveiligen, raadpleegt u [Veelgestelde vragen over Microsoft Rights Management-toepassing voor delen voor Windows](http://go.microsoft.com/fwlink/?LinkId=303971).

## Een bestand op een apparaat beveiligen (direct beveiligen)

1.  Selecteer in Verkenner een bestand dat moet worden beveiligd. Klik met de rechtermuisknop op **Beschermen met RMS** en selecteer vervolgens **Direct beveiligen**. Bijvoorbeeld:

    ![Menuoptie Direct beveiligen](../media/ADRMS_MSRMSApp_SP_CompanyDefined.png)

    > [!NOTE]
    > Als u de optie **Beschermen met RMS** niet ziet, is de RMS-toepassing voor delen waarschijnlijk niet geïnstalleerd op uw computer of moet uw computer opnieuw worden opgestart om de installatie te voltooien. Zie [De Rights Management-toepassing voor delen downloaden en installeren](install-sharing-app.md) voor meer informatie over het installeren van de RMS-toepassing voor delen.

2.  Voer een van de volgende handelingen uit:

    -   Selecteer een beleidssjabloon: dit zijn vooraf gedefinieerde machtigingen voor mensen in uw organisatie om toegang en gebruik te beperken. Als de naam van uw bedrijf bijvoorbeeld Contoso Ltd is, ziet u mogelijk het volgende: **Contoso Ltd - alleen vertrouwelijke weergave** Als dit de eerste keer is dat u een bestand op deze computer beveiligt, moet u eerst **Door bedrijf gedefinieerde beveiliging** selecteren om de sjablonen te downloaden.

        De volgende keer dat u op de optie **Direct beveiligen** klikt, worden er maximaal 10 sjablonen weergegeven om uit te kiezen. Als er meer dan 10 sjablonen beschikbaar zijn en de gewenste sjabloon niet wordt weergegeven, klikt u op **Door bedrijf gedefinieerde beveiliging** om alle sjablonen te downloaden en weer te geven.

        Wanneer u een beleidssjabloon selecteert, kunt u ook meerdere bestanden en een map beveiligen. Wanneer u een map selecteert, worden alle bestanden in die map automatisch geselecteerd voor beveiliging, maar nieuwe bestanden die u in die map maakt zullen niet automatisch worden beveiligd.

    -   Selecteer **Aangepaste machtigingen**: selecteer deze optie als de sjablonen niet het beveiligingsniveau bieden dat u nodig hebt of als u de beveiligingsopties expliciet zelf wilt instellen. Geef in het [dialoogvenster Beveiliging instellen](sharing-app-dialog-box.md) de gewenste opties voor dit bestand op en klik vervolgens op **Toepassen**.

3.  U ziet kort een dialoogvenster waarin wordt uitgelegd dat het bestand wordt beveiligd en vervolgens wordt er teruggegaan naar Verkenner. Nu is het geselecteerde bestand of zijn de geselecteerde bestanden beveiligd. In sommige gevallen (wanneer het beveiligen de bestandsextensie wijzigt) wordt het oorspronkelijke bestand in Verkenner vervangen door een nieuw bestand met het Rights Management-beveiligingspictogram. Bijvoorbeeld:

    ![Beveiligd bestand met vergrendelingspictogram voor de RMS-toepassing voor delen](../media/ADRMS_MSRMSApp_Pfile.png)

Als u de beveiliging van een bestand later wilt opheffen, raadpleegt u [Beveiliging van een bestand verwijderen met behulp van de Rights Management-toepassing voor delen](sharing-app-remove-protection.md).

## Voorbeelden en andere instructies
Voor voorbeelden over hoe u de Rights Management-toepassing voor delen kunt gebruiken en praktische instructies, zie de volgende secties van de gebruikershandleiding voor de Rights Management-toepassing voor delen:

-   [Voorbeelden voor het gebruik van de RMS-toepassing voor delen](sharing-app-user-guide.md#examples-for-using-the-rms-sharing-application)

-   [Wat wilt u doen?](sharing-app-user-guide.md#what-do-you-want-to-do-)

## Zie ook
[Gebruikershandleiding voor de Rights Management-toepassing voor delen](sharing-app-user-guide.md)



<!--HONumber=Jun16_HO4-->


