---
title: Android-apparaten inschrijven in Intune
titlesuffix: Microsoft Intune
description: Meer informatie over het inschrijven van Android-apparaten in Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3b7652c8c4f471a0a0c32da23d8ac1859e84eb13
ms.sourcegitcommit: e8aaa0955d13fa6c9d5f35a730ad06509ce88d0b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/01/2018
ms.locfileid: "39400348"
---
# <a name="enroll-android-devices"></a>Android-apparaten inschrijven

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Als Intune-beheerder kunt u de volgende Android-apparaten beheren:
- Android-apparaten, inclusief Samsung Knox Standard-apparaten.
- Android Enterprise-apparaten, inclusief [apparaten met Android-werkprofiel](#enable-enrollment-of-android-for-work-devices) en kioskapparaten.

Apparaten waarop Samsung Knox Standard wordt uitgevoerd, bieden ondersteuning voor beheer van meerdere gebruikers in Intune. Eindgebruikers kunnen hun Azure AD-referenties gebruiken om zich aan en af te melden bij het apparaat. Het apparaat wordt centraal beheerd, ongeacht of het in gebruik is of niet. Wanneer gebruikers zich aanmelden, hebben ze toegang tot apps en wordt er een eventueel beleid toegepast. Wanneer ze zich afmelden, worden alle app-gegevens gewist.

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

Android Enterprise omvat een reeks functies en services voor Android-apparaten waarmee persoonlijke apps en gegevens worden gescheiden van een werkprofiel met zakelijke apps en gegevens. Android Enterprise-apparaten zijn onder meer apparaten met werkprofiel en kioskapparaten. 

Als u uw inschrijving voor Android Enterprise-apparaten wilt instellen, moet u eerst [Android Enterprise koppelen aan Intune](connect-intune-android-enterprise.md). Nadat deze stap is voltooid, kunt u het volgende doen:

[Inschrijvingen Android-werkprofiel instellen](android-work-profile-enroll.md)
[inschrijvingen Android-kiosk instellen](android-kiosk-enroll.md)

## <a name="end-user-experience-when-enrolling-a-samsung-knox-device"></a>Ervaring van eindgebruikers bij het inschrijven van een Samsung Knox-apparaat
Er zijn verschillende overwegingen bij het inschrijven van Samsung Knox-apparaten:
-   Zelfs als er voor geen enkel beleid een pincode is vereist, moet het apparaat over ten minste één viercijferige pincode beschikken om te kunnen worden geregistreerd. Als het apparaat niet over een pincode beschikt, wordt de gebruiker gevraagd er een te maken.
-   Er is geen gebruikersinteractie voor Workplace Join Certificates (WPJ).
-   De gebruiker krijgt een overzicht van informatie over inschrijving bij de service en de functies van de app.
-   De gebruiker krijgt een overzicht van informatie over inschrijving bij Knox en de functies van Knox.
-   Als er een versleutelingsbeleid van kracht is, moeten gebruikers een complex wachtwoord van zes tekens instellen als wachtwoordcode voor het apparaat.
-   De gebruiker wordt niet gevraagd extra certificaten te installeren die door een service voor toegang tot bedrijfsrecoures worden gepusht.
- Op sommige oudere Knox-apparaten worden gebruikers om aanvullende certificaten gevraagd die voor toegang tot bedrijfsresources worden gebruikt.
- Als de WPJ niet kan worden geïnstalleerd op een Samsung Mini-apparaat, met ofwel de foutmelding **Certificaat niet gevonden** of de fout **Kan apparaat niet registreren**, dient u de nieuwste Samsung Firmware-updates te installeren.
