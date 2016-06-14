---
# required metadata

title: Intune-evaluatiehandleiding | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 619a1d11-3d22-4635-8f70-770eba3e1712

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Intune-evaluatiehandleiding
Het instellen van een gratis evaluatieversie van 30 dagen voor Microsoft Intune voor het beheren van uw mobiele apparaten en computers is snel en eenvoudig. Met slechts enkele eenvoudige stappen kunt u in de evaluatieversie tot 100 gebruikers en apparaten toevoegen, groepen instellen, nalevingsbeleid configureren, en mobiele apparaten en computers inschrijven en beheren.

In dit onderwerp leert u de basisbeginselen om een evaluatie met Intune op te zetten en krijgt u een overzicht van de service, zodat u de functies en mogelijkheden van Intune kunt evalueren.

Bekijk deze demovideo van vijf minuten en zie hoe eenvoudig u aan de slag kunt met een gratis evaluatieversie van Microsoft Intune en uw apparaten kunt beheren:

<iframe width="675" height="480" src="https://www.youtube.com/embed/ltcZvm4VOFU" frameborder="0" allowfullscreen></iframe>

## Voordat u begint
Voordat u aan de slag gaat met Intune, hebt u het volgende nodig:

-   Een apparaat met een webbrowser die Silverlight ondersteunt waarmee u toegang hebt tot de websites waar u Intune-gebruikersaccounts kunt maken (het **Office 365-beheercentrum**) en waar u apparaten, groepen en beleidsregels beheert (de **Intune-beheerconsole**).).

-   Een tweede apparaat met een webbrowser. Hiermee test u hoe Intune-gebruikers hun apparaten via de bedrijfsportal registreren en beheren. U test ook hoe gebruikers apps zoeken en installeren, en hulp vragen aan beheerders. Als u niet over een tweede apparaat met een webbrowser beschikt, kunt u de instelling 'privacymodus' gebruiken in de browser die u ook gebruikt voor Intune-beheer (in Internet Explorer kunt u bijvoorbeeld klikken op **Extra** &gt; **InPrivate-navigatie**).).

-   Als u al een bestaand Microsoft Online Services-account hebt, hebt u de beheerdersreferenties nodig voor dat account. U hebt deze beheerdersreferenties niet nodig als u zo’n account niet hebt of de Intune-tenant alleen wilt gebruiken voor evaluatiedoeleinden.

-   Als u met de evaluatieversie van Intune iOS- of Windows Phone-apparaten gaat beheren, hebt u certificaten (of sleutels) en accounts nodig om de certificaten op te halen (zie de volgende tabel). Voor Android-apparaten zijn geen extra certificaten vereist.

    |Platfofm|Certificaatvereisten|Meer informatie|
    |------------|----------------------------|--------------------|
    |Windows Phone 8.1 en Windows Phone 8 |Er is geen certificaat vereist voor Windows Phone 8.1-gebruikers die de app Bedrijfsportal uit de Store installeren. Er is een Symantec-certificaat vereist voor Windows Phone 8.0 of voor het gebruik van Intune om de app Bedrijfsportal te implementeren op Windows Phone 8.1-apparaten.|In deze richtlijnen wordt ervan uitgegaan dat uw gebruikers de app Bedrijfsportal vanuit de Store downloaden op een apparaat met Windows Phone 8.1 of hoger. Zie voor meer informatie over de ondersteuning van Windows Phone 8.0 [Windows Phone-beheer met Microsoft Intune instellen](/Intune/DeployUse/set-up-windows-phone-management-with-microsoft-intune)..|
    |Windows 10-, Windows RT 8.1-, Windows RT- of Windows 8.1-apparaten|Er zijn geen certificaten vereist voor de registratie van apparaten met Windows RT en Windows.|[Installeer de Windows-pc-client met Microsoft Intune](/Intune/DeployUse/install-the-windows-pc-client-with-microsoft-intune).|
    |iOS 7.1 of hoger|Haal een Apple Push Notification Service-certificaat op.|Vraag een Apple Push Notification Service-certificaat aan bij Apple, zoals hier wordt beschreven: [iOS- en Mac-beheer instellen met Microsoft Intune](/Intune/DeployUse/set-up-ios-and-mac-management-with-microsoft-intune)..|

## Stappen voor het voltooien van een 30-daagse evaluatieversie van Intune
- [Stap 1: Registreren of aanmelden voor een evaluatie van 30 dagen](get-started-with-a-30-day-trial-of-microsoft-intune-step-1.md). Voordat u zich registreert of aanmeldt bij Intune, moet u bepalen of u zich aanmeldt met een bestaand account of een tijdelijk account maakt dat alleen wordt gebruikt voor de evaluatieversie van 30 dagen van Microsoft Intune.
- [Stap 2: Gebruikers toevoegen](get-started-with-a-30-day-trial-of-microsoft-intune-step-2.md). Nu u uw account hebt ingesteld, kunt u afzonderlijke gebruikersaccounts of meerdere gebruikers tegelijk aan Intune toevoegen (zie de instructies in deze sectie). Voordat u begint, is het belangrijk dat u weet hoe Intune met beheerdersaccounts omgaat.
- [Stap 3: Groepen maken om gebruikers en apparaten in te delen](get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md). Groepen in Intune bieden u een hoge mate van flexibiliteit voor het beheren van uw apparaten en gebruikers. U kunt groepen aanpassen aan de behoeften van uw organisatie (bijvoorbeeld per geografische locatie, afdeling of hardware-eigenschappen) en gebruiken om een breed scala aan administratieve taken uit te voeren, van het instellen van beleidsregels voor een groep gebruikers tot het implementeren van toepassingen op een reeks apparaten.
- [Stap 4: Beleid maken en een app publiceren](get-started-with-a-30-day-trial-of-microsoft-intune-step-4.md). Intune-beleid biedt u instellingen waarmee u de beveiligingsinstellingen op mobiele apparaten kunt controleren, Windows Firewall- en Endpoint Protection-instellingen voor computers kunt onderhouden en toepassingen kunt implementeren.
- [Stap 5: Mobiele apparaten inschrijven en een app installeren](get-started-with-a-30-day-trial-of-microsoft-intune-step-5.md). Als u het beheer van mobiele apparaten met Intune wilt instellen, moet u de instantie voor het beheer van mobiele apparaten instellen, beheer voor specifieke apparaatplatforms inschakelen en vervolgens uw apparaten inschrijven met behulp van de app Bedrijfsportal. Vervolgens kunt u de Microsoft Skype-toepassing implementeren die u hebt gepubliceerd.
- [Stap 6: Andere opties en extra's](get-started-with-a-30-day-trial-of-microsoft-intune-step-6.md). Kies hoe u waarschuwingen, rapporten en andere mogelijkheden van Intune wilt gebruiken om te voldoen aan de behoeften van uw bedrijf.
- [Stap 7: Volgende stappen](get-started-with-a-30-day-trial-of-microsoft-intune-step-7.md). Tref voorbereidingen om over te stappen op een betaald abonnement op Intune en te profiteren van het FastTrack Center Benefit voor Intune.


### Volgende stappen
Het is nu tijd om aan de slag te gaan met uw evaluatieversie van 30 dagen.

>[!div class="step-by-step"]
[**Aanmelden voor Intune** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-1.md)

### Zie tevens
[Snelstartgids voor Intune](/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune)


<!--HONumber=May16_HO1-->


