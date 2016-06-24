---
# required metadata

title: Kiezen hoe u mobiele apparaten registreert |Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 06/06/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: cac62b64-3f8b-47ae-aa66-970c7ba15466

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: damionw
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Kiezen hoe u mobiele apparaten registreert

Registratie van mobiele apparaten is het proces waarmee u smartphones, tablets en pc's onder beheer van Microsoft Intune brengt. Als beheerder moet u bepalen hoe u op basis van het volgende uw apparaten het beste kunt registreren:

 -  Eigendom (persoonlijk apparaat versus apparaat in eigendom van het bedrijf)
 -  Gebruik (gedeeld versus persoonlijk)
 -  Platform (iOS, Android, Windows Phone, Windows-pc, Mac-computer)

Aan de hand van uw antwoorden op de volgende vragen kan worden bepaald welke registratiemethode u het best kunt gebruiken voor de apparaten die u beheert.

## Gebruiken werknemers hun eigen apparaten of worden de apparaten geleverd door uw organisatie?

  **Eigen apparaten van gebruikers**: BYOD-registratie (Bring Your Own Device): gebruikers kunnen de Intune-bedrijfsportal-app op hun apparaten installeren en deze vervolgens registreren, zodat ze toegang krijgen tot bedrijfsresources zoals e-mail, bedrijfsapps, bedrijfsgegevens en ondersteuning.  
  > [!div class="button"]   [BYOD-registratie >](..deploy-use/get-ready-to-enroll-devices-in-microsoft-intune)

  **Apparaten in bedrijfseigendom**: bedrijfsapparaten (COD) kunnen op verschillende manieren worden geregistreerd, al naar gelang de behoeften van de organisatie en de typen apparaten die worden beheerd. Volgende vraag...

## Worden de bedrijfseigen apparaten gedeeld of hebben ze individuele gebruikers?

**Gedeelde bedrijfseigen apparaten**: deze apparaten hebben meerdere gebruikers en zijn doorgaans niet geconfigureerd voor toegang tot e-mail. Voorbeelden zijn onder meer kioskapparaten of de taakgerichte apparaten die beschikbaar zijn en die gebruikers na gebruik weer terugbrengen. De aanbevolen registratiemethode is afhankelijk van het platform van het apparaat.

  - **Windows- en Android-apparaten**: een account voor *apparaatregistratiebehee* is een Intune-account waarmee u verschillende gedeelde apparaten via de bedrijfsportal-app kunt registreren.
  > [!div class="button"]   [Apparaatregistratiebeheer >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **iOS-apparaten**: gedeelde iOS-apparaten kunnen op drie manieren worden beheerd.  **Hoe registreert u uw gedeelde iOS-apparaten?**

    - **Het Device Enrollment Program (DEP) van Apple**: u kunt voor iOS-apparaten die zijn aangeschaft of worden beheerd met DEP een registratieprofiel gebruiken. Wanneer gebruikers hun apparaat voor het eerst inschakelen, downloadt het apparaat het DEP-profiel en wordt het apparaat geregistreerd bij de profiel-DEP.
    > [!div class="button"]     [DEP-registratie >](../deploy-use/ios-device-enrollment-program-in-microsoft-intune)

    - **Apple Configurator op een Mac**: Apple Configurator is een Apple-toepassing die wordt uitgevoerd op een Mac-computer. U kunt uw iOS-apparaten met een USB-kabel aansluiten op de Mac om een registratieprofiel op het apparaat te installeren. Als u de fabrieksinstellingen van het apparaat kunt terugzetten om ze te registreren, gebruikt u Registratie van configuratieassistent. Als u de fabrieksinstellingen van het apparaat niet wilt terugzetten, gebruikt u Direct registratie.

    > [!div class="button"]     [Registratie van configuratieassistent >](../deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) of [Directe registratie >](../deploy-use/ios-direct-enrollment-in-microsoft-intune)

    - **Geen van bovenstaande**: als u de registratiemethode met Apple DEP of Apple Configurator niet kunt of wilt gebruiken, kunt u de functie voor apparaatregistratiebeheer van Intune gebruiken.
    > [!div class="button"]     [DEM-registratie >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

**Afzonderlijke gebruikers**: bedrijfseigen apparaten die worden toegewezen aan individuele gebruikers, moeten worden bijgehouden als bedrijfsmiddelen en gebruikers tegelijkertijd toegang tot e-mail en gegevens bieden als persoonlijke apparaten. De aanbevolen registratiemethode is afhankelijk van het platform van het apparaat.

  - **Windows- en Android-apparaten**: door de IMEI-nummers (International Mobile Equipment Identity) van bedrijfseigen apparaten te importeren, kunt u ze in Intune labelen als apparaten die eigendom zijn van het bedrijf. Gebruikers kunnen hun apparaten vervolgens registreren als een persoonlijk apparaat door de bedrijfsportal te installeren voor toegang tot bedrijfsresources, zoals e-mail, apps en gegevens.
  > [!div class="button"]   [Labelen met IMEI >](../deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  - **iOS-apparaten**: gedeelde iOS-apparaten kunnen op drie manieren worden beheerd.  **Hoe registreert u uw gedeelde iOS-apparaten?**

    - **Het Device Enrollment Program (DEP) van Apple**: u kunt voor iOS-apparaten die zijn aangeschaft of worden beheerd met DEP een registratieprofiel gebruiken. Wanneer gebruikers hun apparaat voor het eerst inschakelen, downloadt het apparaat het DEP-profiel en wordt het apparaat geregistreerd overeenkomstig het profiel.
    > [!div class="button"]     [DEP-registratie](../deploy-use/ios-device-enrollment-program-in-microsoft-intune).

    - **Apple Configurator op een Mac**: Apple Configurator is een Apple-toepassing die wordt uitgevoerd op een Mac-computer. U kunt uw iOS-apparaten met een USB-kabel aansluiten op de Mac om een registratieprofiel op het apparaat te installeren. Als u de fabrieksinstellingen van het apparaat kunt terugzetten om ze te registreren, gebruikt u Registratie van configuratieassistent.

    Als u de fabrieksinstellingen van het apparaat niet wilt terugzetten, gebruikt u Direct registratie.
    Als u de fabrieksinstellingen van het apparaat kunt terugzetten om ze te registreren, gebruikt u Registratie van configuratieassistent.
    > [!div class="button"][Registratie met iOS-configuratieassistent](../deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [!div class="button"][Directe iOS-registratie](../deploy-use/ios-direct-enrollment-in-microsoft-intune).

    - **Geen van de bovenstaande**: als u de registratiemethode met Apple DEP of Apple Configurator niet kunt of wilt gebruiken, kunt u ze, door de IMEI-nummers (International Mobile Equipment Identity) van bedrijfseigen apparaten te importeren, in Intune labelen als apparaten die eigendom zijn van het bedrijf. Gebruikers kunnen hun apparaten vervolgens registreren als een persoonlijk apparaat door de bedrijfsportal te installeren voor toegang tot bedrijfsresources, zoals e-mail, apps en gegevens. > [!div class="button"][Apparaten labelen met IMEI-nummers](../deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)


<!--HONumber=Jun16_HO1-->


