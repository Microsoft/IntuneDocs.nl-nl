---
title: Registratie van Android-apparaatbeheerder in Microsoft Intune
titleSuffix: ''
description: Android-apparaten registreren bij Intune met de registratie van een apparaatbeheerder.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ebeb5830136ad6dae19babbc8ecf45c1d6e5c36c
ms.sourcegitcommit: 2506cdbfccefd42587a76f14ee50c3849dad1708
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/11/2020
ms.locfileid: "75885980"
---
# <a name="android-device-administrator-enrollment"></a>Registratie van Android-apparaatbeheerder

Android-apparaatbeheerder (soms aangeduid met het verouderde Android-beheer, uitgebracht met Android 2.2) is een manier om Android-apparaten te beheren. Er is nu echter verbeterde beheerfunctionaliteit beschikbaar met [Android Enterprise](https://www.android.com/enterprise/management/) (uitgebracht met Android 5.0). In een poging om apparaatbeheer moderner, breder en veiliger te maken, vermindert Google ondersteuning voor apparaatbeheerder in nieuwe Android-versies.

Daarom raden we af om nieuwe apparaten te registreren aan de hand van het onderstaande proces voor apparaatbeheerder, om verminderde functionaliteit te vermijden.

Om diezelfde redenen raden we ook aan dat u apparaten migreert van apparaatbeheerder als de apparaten worden bijgewerkt naar Android 10. 

Voor meer informatie over Intune-ondersteuning voor Android-apparaatbeheerder, raadpleegt u het gedeelte [Aankondigingen](../fundamentals/whats-new.md#decreasing-support-for-android-device-administrator).

Als u toch besluit om gebruikers hun Android-apparaten te laten registreren met apparaatbeheerder, gaat u door naar het volgende gedeelte.  

Voor meer informatie over de Android Enterprise-functies van Google, raadpleegt u de volgende artikelen:
- [Google-richtlijnen voor migratie van apparaatbeheerder naar Android Enterprise](http://static.googleusercontent.com/media/android.com/en/enterprise/static/2016/pdfs/enterprise/Android-Enterprise-Migration-Bluebook_2019.pdf)
- [Google-documentatie over het plan om de apparaatbeheerder-API af te schaffen](https://developers.google.com/android/work/device-admin-deprecation)


## <a name="set-up-device-administrator-enrollment"></a>Registratie van apparaatbeheerder instellen

1. U moet de MDM-instantie instellen op **Microsoft Intune** als voorbereiding op het beheer van mobiele apparaten. Zie [Set the MDM authority](../fundamentals/mdm-authority-set.md) (De MDM-instantie instellen) voor instructies. U stelt de instantie slechts één keer in, wanneer u Intune voor het eerst instelt voor het beheer van mobiele apparaten.
2. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) en kies > **Apparaten** > **Android** > **Android-inschrijving** > **Persoonlijke apparaten en apparaten die bedrijfseigendom zijn met bevoegdheden om apparaten te beheren** > **Apparaatbeheerder gebruiken om apparaten te beheren**.
3. [Vertel uw gebruikers hoe ze hun apparaten moeten registreren](/intune-user-help/enroll-your-device-in-intune-android).  

Nadat een gebruiker zich heeft geregistreerd, kunt u beginnen met het beheer van hun apparaten in Intune, met inbegrip van [toewijzen van nalevingsbeleid](../protect/compliance-policy-create-android.md), [beheren van apps](../apps/app-management.md) en nog veel meer.

Zie de volgende artikelen voor meer informatie over andere taken voor gebruikers:
- [Bronnen over de eindgebruikerservaring in Microsoft Intune](../fundamentals/end-user-educate.md)
- [Uw Android-apparaat gebruiken met Intune](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)


## <a name="block-device-administrator-enrollment"></a>Registratie van apparaatbeheerder blokkeren
Als u apparaten met Android-apparaatbeheerder of alleen de registratie van persoonlijke apparaten met Android-apparaatbeheerder wilt blokkeren, raadpleegt u [Beperkingen voor apparaattypen instellen](enrollment-restrictions-set.md).



## <a name="next-steps"></a>Volgende stappen
- [Nalevingsbeleid toewijzen](../protect/compliance-policy-create-android.md)
- [Apps beheren](../apps/app-management.md)
