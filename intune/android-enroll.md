---
title: Android-apparaten inschrijven in Intune
titlesuffix: Microsoft Intune
description: Meer informatie over het inschrijven van Android-apparaten in Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/31/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 866db22b79f2ca9255f9eccdfdba28dc353836ed
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55846754"
---
# <a name="enroll-android-devices"></a>Android-apparaten inschrijven

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Als Intune-beheerder kunt u de volgende Android-apparaten beheren:
- Android-apparaten, inclusief Samsung Knox Standard-apparaten.
- Android Enterprise-apparaten, waaronder:
    - **Apparaten met een Android-werkprofiel**: Persoonlijke apparaten die zijn gemachtigd voor toegang tot bedrijfsgegevens. Beheerders kunnen werkaccounts, apps en gegevens beheren. Persoonlijke gegevens op het apparaat worden geïsoleerd van bedrijfsgegevens en beheerders hebben geen toegang tot persoonlijke instellingen of gegevens. 
    - **Toegewezen Android-apparaten**: Apparaten in bedrijfseigendom voor eenmalig gebruik, bijvoorbeeld voor digitale ondertekening, het afdrukken van tickets of inventarisbeheer. Beheerders vergrendelen het gebruik van een apparaat voor een beperkt aantal apps en webkoppelingen. Ook wordt voorkomen dat gebruikers andere apps kunnen toevoegen of andere acties op het apparaat kunnen uitvoeren.
    - **Volledig beheerde Android-apparaten**: Apparaten in bedrijfseigendom voor één gebruiker, die exclusief worden gebruikt voor werk, niet voor persoonlijk gebruik. Beheerders kunnen het hele apparaat beheren en beleidscontroles afdwingen die niet beschikbaar zijn voor werkprofielen. 

## <a name="prerequisite"></a>Vereiste

U moet de MDM-instantie instellen op **Microsoft Intune** als voorbereiding op het beheer van mobiele apparaten. Zie [Set the MDM authority](mdm-authority-set.md) (De MDM-instantie instellen) voor instructies. U stelt de instantie slechts één keer in, wanneer u Intune voor het eerst instelt voor het beheer van mobiele apparaten.

## <a name="set-up-android-enrollment"></a>Android-inschrijving instellen

Standaard staat Intune de registratie van Android- en Samsung Knox Standard-apparaten toe. Nadat is voldaan aan de voorwaarde, hoeven beheerders alleen maar [hun gebruikers uit te leggen hoe zij hun apparaten kunnen registreren](/intune-user-help/enroll-your-device-in-intune-android).

Nadat een gebruiker zich heeft geregistreerd, kunt u beginnen met het beheer van hun apparaten in Intune, met inbegrip van [toewijzen van nalevingsbeleid](compliance-policy-create-android.md), [beheren van apps](app-management.md) en nog veel meer.

Zie de volgende artikelen voor meer informatie over andere taken voor gebruikers:

- [Bronnen over de eindgebruikerservaring in Microsoft Intune](end-user-educate.md)
- [Uw Android-apparaat gebruiken met Intune](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

Zie [Beperkingen voor apparaattypen instellen](enrollment-restrictions-set.md) als u de inschrijving wilt blokkeren van Android-apparaten of alleen Android-apparaten die het eigendom van de gebruiker zijn.

## <a name="set-up-android-enterprise-enrollment"></a>Android Enterprise-inschrijving instellen

Android Enterprise omvat een reeks functies en services voor Android-apparaten waarmee persoonlijke apps en gegevens worden gescheiden van een werkprofiel met zakelijke apps en gegevens. Android Enterprise-apparaten zijn apparaten met een werkprofiel, volledig beheerde apparaten en toegewezen apparaten. 

- [Inschrijving van Android-werkprofiel instellen](android-work-profile-enroll.md)
- [Inschrijving van toegewezen Android-apparaat instellen](android-kiosk-enroll.md)
- [Inschrijving van volledig beheerd Android-apparaat instellen](android-fully-managed-enroll.md)

## <a name="end-user-experience-when-enrolling-a-samsung-knox-device"></a>Ervaring van eindgebruikers bij het inschrijven van een Samsung Knox-apparaat

Samsung Knox Standard-apparaten bieden ondersteuning voor beheer van meerdere gebruikers in Intune. Eindgebruikers kunnen hun Azure AD-referenties gebruiken om zich aan en af te melden bij het apparaat. Het apparaat wordt centraal beheerd, ongeacht of het in gebruik is of niet. Wanneer gebruikers zich aanmelden, hebben ze toegang tot apps en wordt er een eventueel beleid toegepast. Wanneer ze zich afmelden, worden alle app-gegevens gewist.

Er zijn verschillende overwegingen bij het inschrijven van Samsung Knox-apparaten:
-   Zelfs als er voor geen enkel beleid een pincode is vereist, moet het apparaat over ten minste één viercijferige pincode beschikken om te kunnen worden geregistreerd. Als het apparaat niet over een pincode beschikt, wordt de gebruiker gevraagd er een te maken.
-   Er is geen gebruikersinteractie voor Workplace Join Certificates (WPJ).
-   De gebruiker krijgt een overzicht van informatie over inschrijving bij de service en de functies van de app.
-   De gebruiker krijgt een overzicht van informatie over inschrijving bij Knox en de functies van Knox.
-   Als er een versleutelingsbeleid van kracht is, moeten gebruikers een complex wachtwoord van zes tekens instellen als wachtwoordcode voor het apparaat.
-   De gebruiker wordt niet gevraagd extra certificaten te installeren die door een service voor toegang tot bedrijfsrecoures worden gepusht.
- Op sommige oudere Knox-apparaten worden gebruikers om aanvullende certificaten gevraagd die voor toegang tot bedrijfsresources worden gebruikt.
- Als de WPJ niet kan worden geïnstalleerd op een Samsung Mini-apparaat, met ofwel de foutmelding **Certificaat niet gevonden** of de fout **Kan apparaat niet registreren**, dient u de nieuwste Samsung Firmware-updates te installeren.

## <a name="next-steps"></a>Volgende stappen

- [Inschrijving van Android-werkprofiel instellen](android-work-profile-enroll.md)
- [Inschrijving van toegewezen Android-apparaat instellen](android-kiosk-enroll.md)
- [Inschrijving van volledig beheerd Android-apparaat instellen](android-fully-managed-enroll.md)
