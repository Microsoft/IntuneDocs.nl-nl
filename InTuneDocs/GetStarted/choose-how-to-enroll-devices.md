---
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
ms.sourcegitcommit: 928b79530ac278f78356f8d1ef9f267077634b5b
ms.openlocfilehash: 00767d06fe0d7a10cba10d0dd428f99be0390866


---

# Kiezen hoe u mobiele apparaten registreert

Registratie van mobiele apparaten is het proces waarmee u smartphones, tablets en pc's onder beheer van Microsoft Intune brengt. Als beheerder moet u bepalen hoe u op basis van het volgende uw apparaten het beste kunt registreren:

 -  Eigendom (persoonlijk apparaat versus apparaat in eigendom van het bedrijf)
 -  Gebruik (gedeeld versus persoonlijk)
 -  Platform (iOS, Android, Windows Phone, Windows-pc, Mac-computer)

Aan de hand van uw antwoorden op de volgende vragen kan worden bepaald welke registratiemethode u het best kunt gebruiken voor de apparaten die u beheert.

## **Gebruiken werknemers hun eigen apparaten of worden de apparaten geleverd door uw organisatie?**

  **Apparaten van gebruikers** kunnen worden geregistreerd om toegang te krijgen tot bedrijfsbronnen zoals e-mail, bedrijfsapps, bedrijfsgegevens en ondersteuning. Dit wordt ook wel BYID-registratie (Bring your own device) genoemd. **Bedrijfseigen apparaten** worden door de organisatie aan werknemers verstrekt om te kunnen voldoen aan zakelijke behoeften.
  > [!div class="button"]   [BYOD-registratie >](#byod-device-enrollment)   [COD-registratie >](cod-device-enrollment)

### BYOD-apparaatregistratie

Voor BYOD-registratie is vereist dat gebruikers de Intune-bedrijfsportal-app op hun apparaten installeren. Vervolgens kunnen ze de app starten en registreren door de referenties van hun werk- of schoolaccount op te geven. Als met Intune een licentie voor deze referenties wordt gevonden, wordt het apparaat toegevoegd aan de Intune-beheerconsole en ontvangt het apparaat beleid van Intune, waardoor toegang tot bedrijfsresources wordt verleend.

**Apparaattype selecteren:**

> [!div class="op_single_selector"]
- [Android-beheer instellen met Microsoft Intune](..deploy-use/set-up-android-management-with-microsoft-intune.md)
- [Set up iOS and Mac management with Microsoft Intune](..deploy-use/set-up-ios-and-mac-management-with-microsoft-intune.md)
- [Windows Phone-beheer instellen met Microsoft Intune](..deploy-use/set-up-windows-phone-management-with-microsoft-intune.md)
- [Windows apparaatbeheer instellen met Microsoft Intune](..deploy-use/set-up-windows-device-management-with-microsoft-intune.md)


### COD-apparaatregistratie

Bedrijfseigen apparaten kunnen worden geregistreerd ter ondersteuning van een toegewezen gebruiker of de apparaten kunnen worden gedeeld.  **Gedeelde apparaten**: Deze apparaten hebben meerdere gebruikers en zijn doorgaans niet geconfigureerd voor toegang tot e-mail. Voorbeelden zijn onder meer kioskapparaten of de taakgerichte apparaten die kunnen worden geleend en die gebruikers na gebruik weer terugbrengen. De aanbevolen registratiemethode is afhankelijk van het platform van het apparaat. **Specifieke apparaten**: Deze apparaten worden toegewezen aan individuele gebruikers, moeten worden bijgehouden als bedrijfsmiddelen en moeten gebruikers als persoonlijke apparaten toegang bieden tot e-mail en gegevens. De aanbevolen registratiemethode is afhankelijk van het platform van het apparaat.

## **Worden de bedrijfseigen apparaten gedeeld of hebben deze apparaten toegewezen gebruikers?**

> [!div class="button"] [Gedeeld >](#Shared-company-owned-devices)   [Toegewezen >](..deploy-use/get-ready-to-enroll-devices-in-microsoft-intune)


### Gedeelde bedrijfseigen apparaten

Deze apparaten hebben meerdere gebruikers en zijn doorgaans niet geconfigureerd voor toegang tot e-mail. Voorbeelden zijn onder meer kioskapparaten of de taakgerichte apparaten die kunnen worden geleend en die gebruikers na gebruik weer terugbrengen. De aanbevolen registratiemethode is afhankelijk van het platform van het apparaat.

  - **Windows- en Android-apparaten**: een account voor *apparaatregistratiebeheer* is een Intune-account waarmee u verschillende gedeelde apparaten via de bedrijfsportal-app kunt registreren.
  > [!div class="button"]   [Windows >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](../deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#shared-ios-device-enrollment)

### Registratie van gedeelde iOS-apparaten

De voorkeursmethode voor registratie voor gedeelde, bedrijfseigen iOS-apparaten is afhankelijk van hoe u die apparaten koopt en beheert:

  - **Het Device Enrollment Program (DEP) van Apple**: u kunt voor iOS-apparaten die zijn aangeschaft of worden beheerd met DEP een registratieprofiel gebruiken. Wanneer gebruikers hun apparaat voor het eerst inschakelen, downloadt het apparaat het DEP-profiel en wordt het apparaat geregistreerd bij de profiel-DEP.
  - **Apple Configurator op een Mac**: Apple Configurator is een Apple-toepassing die wordt uitgevoerd op een Mac-computer. U kunt uw iOS-apparaten met een USB-kabel aansluiten op de Mac om een registratieprofiel op het apparaat te installeren. Als u de fabrieksinstellingen van het apparaat kunt terugzetten om ze te registreren, gebruikt u Registratie van configuratieassistent. Als u de fabrieksinstellingen van het apparaat niet wilt terugzetten, gebruikt u Direct registratie.
  - **Geen van bovenstaande**: als u de registratiemethode met Apple DEP of Apple Configurator niet kunt of wilt gebruiken, kunt u de functie voor apparaatregistratiebeheer van Intune gebruiken.

  **Kiezen:**
    > [!div class="button"]      [DEP-registratie >](../deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Mac >](../deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Rechtstreekse registratie >](../deploy-use/ios-direct-enrollment-in-microsoft-intune)  

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



<!--HONumber=Jun16_HO2-->


