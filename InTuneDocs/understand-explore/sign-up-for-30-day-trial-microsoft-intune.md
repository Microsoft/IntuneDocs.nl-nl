---
title: Aanmelden voor een gratis proefversie van 30 dagen van Microsoft Intune | Microsoft-documentatie
description: Meld u aan voor een gratis evaluatieversie van Microsoft Intune die u 30 dagen kunt uitproberen.
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 11/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 619a1d11-3d22-4635-8f70-770eba3e1712
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: a65ead23e62870647245120d1663706fc46810ac


---

# <a name="sign-up-for-a-microsoft-intune-free-trial"></a>Registreren voor een gratis proefversie van Microsoft Intune
In dit artikel wordt uitgelegd hoe zich registreert voor een proefversie van Intune. Daarnaast voegt u enkele gebruikers aan uw proefversie toe zodat u de bijbehorende evaluatiehandleiding kunt volgen om te zien hoe mobiele apparaten met Intune worden beheerd. <!---or app data when devices are not enrolled in Intune.--->

## <a name="assumptions"></a>Aannames
In dit artikel over de aanmelding en in de evaluatiehandleiding wordt verondersteld dat u de evaluatieversie uitsluitend voor evaluatiedoeleinden gebruikt en u met een schone omgeving wilt beginnen wanneer u zich abonneert.

We zorgen ervoor dat u snel aan de slag kunt met de proefversie door een zeer eenvoudige omgeving in te stellen die alleen gebruikmaakt van Intune en ervan uitgaat dat dit de enige methode is waarmee u apparaten beheert (ook wel de instantie voor beheer van mobiele apparaten genoemd). De handleiding bevat echter ook verwijzingen naar diepere technische inhoud voor verdere exploratie.

De proefversie biedt dezelfde mogelijkheden als de abonnementsversie. Het enige verschil is dat de proefversie is beperkt tot maximaal 100 gebruikersaccounts.

## <a name="sign-up-for-your-trial"></a>Aanmelden voor de proefversie
Ga naar de [registratiepagina voor Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) en vul het formulier in om u aan te melden voor een proefabonnement.

Als u een werk- of schoolaccount hebt en dit wilt gebruiken voor de proefversie van Intune, volgt u [deze aanmeldingsinstructies](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-1). In dit artikel en de evaluatiehandleidingen wordt echter verondersteld dat u geen dergelijk account gebruikt.

> [!TIP]
> Als de landinstellingen voor de meeste IT-activiteiten en van de meeste gebruikers afwijkt van die van u, kunt u de desbetreffende landinstellingen configureren voor uw proef om de prestaties te testen.

### <a name="post-sign-up-considerations"></a>Overwegingen voor na uw registratie
Wanneer u zich registreert voor een proefversie, ontvangt u een e-mailbericht met gegevens over uw account op het e-mailadres dat u hebt opgegeven tijdens het registratieproces. In deze e-mail wordt bevestigd dat uw proefversie actief is.

Wanneer het registratieproces is voltooid, wordt u omgeleid naar een pagina waarop u gebruikers kunt toevoegen en licenties kunt toewijzen met behulp van het Office 365-beheercentrum. Wanneer u zich een volgende keer aanmeldt bij Intune, wordt u automatisch omgeleid naar de beheerconsole van Intune.

## <a name="keeping-the-admin-center-and-the-intune-administration-console-straight"></a>Het beheercentrum en de Intune-beheerconsole recht houden
U gebruikt twee portals voor Intune: het Office 365-beheercentrum ([portal.office.com](https://portal.office.com)) en de Intune-beheerconsole ([manage.microsoft.com](https://manage.microsoft.com)).

Normaal gesproken voert u uw werkzaamheden uit in de Intune-beheerconsole, zoals hieronder. Dit is de site waar u uw groepen, beleid, apparaten en apps instelt en beheert.

![Afbeelding van de Intune-beheerconsole](./media/sign-up/intune-admin-console.png)

U gebruikt het Office 365-beheercentrum (zie hieronder) echter om gebruikers en andere aspecten van uw account toe te voegen en te beheren, met inbegrip van de facturering en ondersteuning.

![Afbeelding van het Office 365-beheercentrum](./media/sign-up/office-admin-center.png)

U kunt van het Office 365-beheercentrum naar de Intune-beheerconsole navigeren. De beheercentra bevinden zich onder het laatste item in het linker navigatiedeelvenster. Kies **Intune** om de Intune-beheerconsole te openen in een nieuw tabblad.

![Afbeelding van een koppeling naar de Intune-beheerconsole](./media/sign-up/link-to-intune.png)

Als van Intune terug wilt keren naar het Office 365-beheercentrum, kiest u op de pagina Overzicht groepen de taak **Gebruikers toevoegen**.

![Afbeelding van een link terug naar het Office 365-beheercentrum](./media/sign-up/task-add-users.png)

## <a name="add-users"></a>Gebruikers toevoegen
Voordat u het Office 365-beheercentrum verlaat om terug te keren naar Intune, moet u enkele gebruikers toevoegen aan uw proefaccount.

In het Office 365-beheercentrum kunt u gebruikers afzonderlijk of in bulk toevoegen door een CSV-bestand te uploaden. Voor uw proefaccount doen we beide. U wilt in uw productieomgeving echter waarschijnlijk ook profiteren van uw Azure Active Directory-gebruikersaccounts. Meer informatie hierover vindt u in de [Introductiehandleiding](https://docs.microsoft.com/en-us/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3) en in de sectie [Volgende stappen](#Next-steps) in dit artikel.

### <a name="add-an-individual-user"></a>Een afzonderlijke gebruiker toevoegen
1. Kies een van de opties voor het toevoegen van een gebruiken om een formulier te openen waarmee u een gebruiker kunt maken. Alleen de items die zijn gemarkeerd met een asterisk (\*) zijn verplicht.
![Afbeelding van de opties voor de knop voor het toevoegen van gebruikers](./media/sign-up/add-user.png)


2.  Wanneer u de gebruiker toevoegt, wordt er als laatste stap e-mailbericht met het tijdelijke wachtwoord voor Intune verzonden. In het kader van deze evaluatie gebruikt u uw eigen zakelijke e-mailadres, zodat u de aanmeldingsgegevens ontvangt en de e-mail krijgt te zien die uw gebruikers ontvangen. Vervolgens kunt u deze gebruikersidentiteiten gebruiken om de testapparaten te registreren.<br/>

 ![Afbeelding van de laatste stap voor het toevoegen van een gebruiker](./media/sign-up/new-user-2.png)

3. Als u een beheerdersrol aan een gebruiker wilt toewijzen nadat u deze hebt gemaakt, kunt u de rol bewerken in het Office 365-beheercentrum door de gebruikersnaam in uw lijst met gebruikers te selecteren en vervolgens in de regel Rol de optie **Bewerken** te selecteren om de lijst met gebruikersrollen weer te geven die u kunt selecteren en aan de betreffende gebruiker kunt toewijzen.

 ![Afbeelding van de opties voor gebruikersrollen](./media/sign-up/change-user-role.png)

### <a name="import-multiple-users"></a>Meerdere gebruikers importeren
1. U vindt de wizard voor het importeren van meerdere gebruikers in de lijst **Meer**.

 ![Afbeelding van de optie voor het toevoegen van meerdere gebruikers](./media/sign-up/add-multiple-users.png)

2. Voor de correcte configuratie van uw CSV-bestand kunt u een sjabloonbestand downloaden waarin u uw gebruikersgegevens kunt invullen. Download het CSV-bestand dat kopteksten en gegevens over voorbeeldgebruikers bevat om te zien wat voor gegevens er precies nodig zijn voor elk veld.

 ![Afbeelding van de eerste stap in de wizard voor bulksgewijs registreren](./media/sign-up/bulk-enroll-step-1.png)


3. Nadat u het CSV-bestand hebt gemaakt en opgeslagen, kiest u **Bladeren** om het bestand te selecteren. Controleer het bestand en kies **Volgende**. Uw gebruikers worden geüpload en toegevoegd aan uw lijst met actieve gebruikers.

Het is nu tijd om naar de Intune-beheerconsole te gaan en te beginnen met het beheren van uw gebruikers, hun apparaten en hun apps.

> [!NOTE]
> Uw gebruikers worden pas in Intune weergegeven nadat ze een apparaat hebben geregistreerd dat moet worden beheerd.

## <a name="next-steps"></a>Volgende stappen
Evaluatiescenario: [Mobile Device Management evalueren in Microsoft Intune](mobile-device-management-trial-guide-microsoft-intune.md)

Meer informatie over het gebruik van uw Azure Active Directory-gebruikersaccounts met Intune:
- [Identiteitsvereisten](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)
- [Adreslijstsynchronisatie](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)
- [Vereisten voor Multi-factor Authentication](https://docs.microsoft.com/en-us/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements)

Meer informatie over het gebruik van [Intune met System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/mdm/understand/hybrid-mobile-device-management)



<!--HONumber=Dec16_HO2-->


