---
title: Inzicht in de inschrijvingservaring voor iOS-apparaten
titlesuffix: Microsoft Intune
description: Maak kennis met het inschrijvingsproces door een volledige inschrijvingsprocedure voor een iOS-apparaat te doorlopen.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: b595848d-c451-43ab-812d-b22e0170fb7a
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 487ad607bc34d5fc2137f1b3903b0711e793658d
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55840529"
---
# <a name="understand-the-users-experience-enrolling-an-ios-device"></a>Inzicht in de gebruikerservaring bij het inschrijven van iOS-apparaten

Microsoft Intune helpt u om uw werknemers met mobiele apparaten uit te rusten terwijl uw zakelijke gegevens worden beveiligd. Aangezien uw eindgebruikers interactie met Intune hebben op hun apparaten en niet in de beheerconsole, is het belangrijk dat u goed op de hoogte bent van het registratieproces. Alleen dan kunt u goed ontworpen nalevingsbeleid combineren met een prettige registratie-ervaring voor uw gebruikers. Dit is vooral belangrijk omdat uw gebruikers precies weten welke gegevens u als beheerder kunt zien:

| Wat de IT-afdeling niet kan zien | Wat de IT-afdeling kan zien |
|---|---|
| Oproepen en browsegeschiedenis | Model |
| Locatie | Serienummer |
| Persoonlijke e-mails | Versie van besturingssysteem |
| SMS-berichten | App-namen |
| Contactpersonen | Eigenaar |
| Wachtwoorden van uw persoonlijke accounts | Apparaatnaam |
| Agenda-items | De fabrikant (voor apparaten die niet door Apple zijn gemaakt) |
| Foto's, met inbegrip van wat er in de app Foto's of het camera-album staat | Telefoonnummer (voor zakelijke apparaten het hele nummer. Voor persoonlijke apparaten alleen de laatste vier cijfers.) |

## <a name="how-do-i-enroll-a-device"></a>Hoe registreer ik een apparaat?

Vaak is de registratie van hun apparaat de eerste ervaring van eindgebruikers die toegang willen hebben tot bedrijfsresources. Een [goed begrip van deze ervaring](end-user-educate.md) kan voorkomen dat een in theorie prettige ervaring frustraties oplevert bij de gebruiker.

1. Open de **App Store** en zoek naar **Intune-bedrijfsportal**.
2. Download de **Microsoft Intune-bedrijfsportal**-app.
3. Open de app **Bedrijfsportal**, voer het e-mailadres en het wachtwoord van een testgebruiker in, en tik vervolgens op **Aanmelden**.
4. Wijzig het tijdelijke wachtwoord in een nieuw wachtwoord.
5. Tik op de pagina **Instellen van bedrijfstoegang** op **Apparaatinschrijving**.
6. Lees op de pagina **Waarom moet u uw apparaat registreren?** informatie over wat een gebruiker kan doen wanneer ze hun apparaat registreren en tik vervolgens op **Doorgaan**.
7. Bekijk de lijst met items waartoe een gebruiker toegang krijgt wanneer ze zich registreren en tik vervolgens op **Doorgaan**.
8. Neem door wat IT-beheerders wel en niet kunnen zien op het apparaat van een gebruiker en tik op **Doorgaan**.
9. Lees op de pagina **De volgende stap** wat er gebeurt tijdens het registreren en tik vervolgens op **Registreren**.
10. Tik op de pagina **Profiel installeren** op **Installeren**, en voer de wachtwoordcode van het apparaat in als daarom wordt gevraagd.
11. Tik op **INSTALLEREN**.
12. Tik nogmaals op **Installeren** om aan te geven dat u de waarschuwing hebt gelezen.
13. Tik in de**waarschuwing** op **Vertrouwen**.
14. Wanneer het scherm verandert om weer te geven dat het profiel is geïnstalleerd, tikt u op **Gereed**.
15. U ziet een bericht dat het apparaat wordt geregistreerd en vervolgens dat de registratie van het apparaat is voltooid. Er verschijnt een pop-up met de vraag de pagina in de bedrijfsportal te openen. Tik op **Openen**.
16. U gaat terug naar het scherm **Instellen van bedrijfstoegang**. Als u geen testbeleid hebt ingesteld, moet het apparaat als compatibel worden weergegeven. Als u wel testbeleid hebt gemaakt, tikt u op **Apparaatcompatibiliteit** om een bericht weer te geven dat er bepaalde dingen moeten worden gedaan om het apparaat veilig te maken.

## <a name="next-steps"></a>Volgende stappen

[Aan de slag met het toevoegen van apps](get-started-apps.md) - Zoek apps en voeg ze toe aan apparaten om het voor uw medewerkers mogelijk te maken om hun werk uit te voeren.

## <a name="learn-more"></a>Meer informatie

* [Registratieopties voor Intune](enrollment-options.md)
* [Bring Your Own Device mogelijk maken met Intune](byod-enable.md)
* [Uw eindgebruikers voorlichten over inschrijving en apparaatbeheer](end-user-educate.md)
