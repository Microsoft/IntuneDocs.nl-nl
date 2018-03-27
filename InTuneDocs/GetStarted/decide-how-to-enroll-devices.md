---
title: Kiezen hoe u mobiele apparaten registreert |Microsoft Intune
description: Bepalen hoe u mobiele apparaten in Intune kunt registreren door enkele eenvoudige vragen te beantwoorden
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 178df739-d3b9-43cb-8440-c5c110b1276b
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: a4f7a503417938eabb4334757dcf12a63f082fd3
ms.openlocfilehash: f4e6c17624f509b83ca594750c0db8931bc54b35


---

# Kiezen hoe u mobiele apparaten registreert

Registratie van mobiele apparaten is het proces waarmee u smartphones, tablets en pc's onder beheer van Microsoft Intune brengt. Als beheerder moet u bepalen hoe u op basis van het volgende uw apparaten het beste kunt registreren:

 -  Eigendom (persoonlijk apparaat versus apparaat in eigendom van het bedrijf)
 -  Gebruik (gedeeld versus persoonlijk)
 -  Platform (iOS, Android, Windows Phone, Windows-pc, Mac-computer)

Aan de hand van uw antwoorden op de volgende vragen kan worden bepaald welke registratiemethode u het best kunt gebruiken voor de apparaten die u beheert.

## **Gebruiken werknemers hun eigen apparaten of worden de apparaten geleverd door uw organisatie?**

  - **Eigen apparaten van gebruikers**: BYOD-registratie (Bring Your Own Device): gebruikers kunnen de Intune-bedrijfsportal-app op hun apparaten installeren en deze vervolgens registreren, zodat ze toegang krijgen tot bedrijfsresources zoals e-mail, bedrijfsapps, bedrijfsgegevens en ondersteuning.  

  - **Apparaten in bedrijfseigendom**: bedrijfsapparaten (COD) kunnen op verschillende manieren worden geregistreerd, al naar gelang de behoeften van de organisatie en de typen apparaten die worden beheerd.

> [!div class="button"]
[BYOD-inschrijving >](#what-byod-devices-can-your-users-enroll)   [COD-inschrijving >](#are-your-company-owned-devices-shared-or-do-they-have-dedicated-users)

## **Welke BYOD-apparaten kunnen uw gebruikers inschrijven?**

> [!div class="button"]
[Android](/intune/deploy-use/set-up-android-management-with-microsoft-intune) [iOS en Mac](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) [Windows 10 Mobile en Window Phone](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) [Windows-pc’s](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)

## **Worden de bedrijfseigen apparaten gedeeld of hebben deze apparaten toegewezen gebruikers?**

- **Gedeelde bedrijfseigen apparaten**: deze apparaten hebben meerdere gebruikers en zijn doorgaans niet geconfigureerd voor toegang tot e-mail. Voorbeelden zijn onder meer kioskapparaten of de taakgerichte apparaten die beschikbaar zijn en die gebruikers na gebruik weer terugbrengen. De aanbevolen registratiemethode is afhankelijk van het platform van het apparaat.

- **Toegewezen gebruikers**: bedrijfseigen apparaten die worden toegewezen aan individuele gebruikers, moeten worden bijgehouden als bedrijfsmiddelen en gebruikers tegelijkertijd toegang tot e-mail en gegevens bieden als persoonlijke apparaten. De aanbevolen registratiemethode is afhankelijk van het platform van het apparaat.

> [!div class="button"]
[Gedeeld >](#what-operating-system-are-your-shared-devices-running)   [Specifiek >](#how-will-you-manage-dedicated-ios-devices)


## **Welk besturingssysteem wordt uitgevoerd op uw gedeelde apparaten?**

  > [!div class="button"]
  [Windows >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#how-will-you-manage-shared-ios-devices)

## **Hoe beheert u uw gedeelde iOS-apparaten?**

- **Het Device Enrollment Program (DEP) van Apple**: u kunt voor iOS-apparaten die zijn aangeschaft of worden beheerd met DEP een registratieprofiel gebruiken. Wanneer gebruikers hun apparaat voor het eerst inschakelen, downloadt het apparaat het DEP-profiel en wordt het apparaat geregistreerd bij de profiel-DEP.

- **Apple Configurator op een Mac**: Apple Configurator is een Apple-toepassing die wordt uitgevoerd op een Mac-computer. U kunt uw iOS-apparaten met een USB-kabel aansluiten op de Mac om een registratieprofiel op het apparaat te installeren. Als u de fabrieksinstellingen van het apparaat kunt terugzetten om ze te registreren, gebruikt u Registratie van configuratieassistent. Als u de fabrieksinstellingen van het apparaat niet wilt terugzetten, gebruikt u Direct registratie.

- **Beheerfunctie voor apparaatregistratie**: met de beheerfunctie voor apparaatregistratie (DEM) van Intune kan een manager of beheerder een groot aantal mobiele apparaten registreren met één gebruikersaccount. Deze apparaten kunnen geen gebruikersaffiniteit (ofwel toegewezen gebruikers) hebben, en kunnen alleen worden geregistreerd na installatie van en aanmelding bij de bedrijfsportal-app.

  > [!div class="button"]
  [iOS DEP-inschrijving >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Directe iOS-inschrijving >](/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune) [DEM-inschrijving >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

## **Hoe beheert u uw specifieke iOS-apparaten?**

U kunt apparaten in bedrijfseigendom met toegewezen gebruikers op de volgende manieren registreren:

- **Het Device Enrollment Program (DEP) van Apple**: u kunt voor iOS-apparaten die zijn aangeschaft of worden beheerd met DEP een registratieprofiel gebruiken. Wanneer gebruikers hun apparaat voor het eerst inschakelen, downloadt het apparaat het DEP-profiel en wordt het apparaat geregistreerd bij Intune.

- **Apple Configurator op een Mac**: Apple Configurator is een Apple-toepassing die wordt uitgevoerd op een Mac-computer. U kunt uw iOS-apparaten met een USB-kabel aansluiten op de Mac om een registratieprofiel op het apparaat te installeren. Als u de fabrieksinstellingen van het apparaat kunt terugzetten om ze te registreren, gebruikt u Registratie van configuratieassistent.

- **Label met IMEI-nummer**: door de IMEI-nummers (International Mobile Equipment Identity) van bedrijfseigen apparaten te importeren, kunt u ze in Intune labelen als apparaten die eigendom zijn van het bedrijf. Gebruikers kunnen hun apparaten vervolgens registreren als een persoonlijk apparaat door de bedrijfsportal te installeren voor toegang tot bedrijfsresources, zoals e-mail, apps en gegevens.

  > [!div class="button"]
  [Label met IMEI >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers) [iOS DEP](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [iOS-Configuratieassistent](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Code met IMEI](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)



<!--HONumber=Oct16_HO4-->


