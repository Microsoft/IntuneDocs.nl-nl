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
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cac62b64-3f8b-47ae-aa66-970c7ba15466
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: 3a00f9cdfb137306a28b33f9d1acdb6bc108670f
ms.openlocfilehash: f15c9748b1c55ec46ddd0056445bf434fa323c59


---

# <a name="choose-how-to-enroll-mobile-devices"></a>Kiezen hoe u mobiele apparaten registreert

Aan de hand van uw antwoorden op de volgende vragen kan worden bepaald welke registratiemethode u het beste kunt gebruiken voor de apparaten die u beheert.

## <a name="do-employees-bring-their-own-devices-or-are-devices-provided-by-your-organization"></a>**Gebruiken werknemers hun eigen apparaten of worden de apparaten geleverd door uw organisatie?**

  - **Apparaten van gebruikers** -'Bring your own device' (BYOD) inschrijven
  - **Bedrijfsapparaten** - COD-inschrijving

> [!div class="button"]
[BYOD-inschrijving >](#what-byod-devices-can-your-users-enroll)   
> [!div class="button"]
[COD-inschrijving >](#are-your-company-owned-devices-shared-or-do-they-have-dedicated-users)

## <a name="what-byod-devices-can-your-users-enroll"></a>**Welke BYOD-apparaten kunnen uw gebruikers inschrijven?**

> [!div class="button"]
[Android](/intune/deploy-use/set-up-android-management-with-microsoft-intune) [iOS en Mac](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) [Windows 10 Mobile en Window Phone](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) [Windows-pc’s](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)

## <a name="are-your-company-owned-devices-shared-or-do-they-have-dedicated-users"></a>**Worden de bedrijfseigen apparaten gedeeld of hebben deze apparaten toegewezen gebruikers?**

> [!div class="button"]
[Gedeeld >](#what-operating-system-are-your-shared-devices-running)   [Specifiek >](#how-will-you-manage-dedicated-ios-devices)


## <a name="what-operating-system-are-your-shared-devices-running"></a>**Welk besturingssysteem wordt uitgevoerd op uw gedeelde apparaten?**

  > [!div class="button"]
  [Windows >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#how-will-you-manage-shared-ios-devices)

## <a name="how-will-you-manage-shared-ios-devices"></a>**Hoe beheert u uw gedeelde iOS-apparaten?**

  > [!div class="button"]
  [iOS DEP-registratie >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Directe iOS-registratie >](/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune) [DEM-registratie >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **Het Device Enrollment Program (DEP) van Apple**: u kunt iOS-apparaten die zijn aangeschaft of worden beheerd met DEP aan een registratieprofiel koppelen. Wanneer gebruikers hun apparaat voor het eerst inschakelen, downloadt het apparaat het DEP-profiel en wordt het apparaat geregistreerd bij de profiel-DEP.

  - **Apple Configurator op een Mac**: Apple Configurator is een Apple-toepassing die wordt uitgevoerd op een Mac-computer. U kunt uw iOS-apparaten met een USB-kabel aansluiten op de Mac om een registratieprofiel op het apparaat te installeren. Als u de fabrieksinstellingen van het apparaat kunt terugzetten om ze te registreren, gebruikt u de optie Registratie van configuratieassistent. Als u de fabrieksinstellingen van het apparaat niet wilt terugzetten, gebruikt u de optie Directe inschrijving.

  - **Beheerfunctie voor apparaatregistratie (Intune)**: met de beheerfunctie voor apparaatregistratie (DEM) van Intune kan een manager of beheerder een groot aantal mobiele apparaten registreren met één gebruikersaccount. Deze apparaten kunnen geen toegewezen gebruikers (ofwel gebruikersaffiniteit) hebben en kunnen alleen worden geregistreerd na installatie van en aanmelding bij de bedrijfsportal-app.

## <a name="how-will-you-manage-dedicated-ios-devices"></a>**Hoe beheert u uw specifieke iOS-apparaten?**

  > [!div class="button"]
   [iOS DEP](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [iOS-configuratieassistent](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Labellen met IMEI](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  U kunt apparaten in bedrijfseigendom met toegewezen gebruikers op de volgende manieren registreren:

  - **Het Device Enrollment Program (DEP) van Apple**: u kunt iOS-apparaten die zijn aangeschaft of worden beheerd met DEP aan een registratieprofiel koppelen. Wanneer gebruikers hun apparaat voor het eerst inschakelen, downloadt het apparaat het DEP-profiel en wordt het apparaat geregistreerd bij Intune.

  - **Apple Configurator op een Mac**: Apple Configurator is een Apple-toepassing die wordt uitgevoerd op een Mac-computer. U kunt uw iOS-apparaten met een USB-kabel aansluiten op de Mac om een registratieprofiel op het apparaat te installeren. Als u de fabrieksinstellingen van het apparaat kunt terugzetten om ze te registreren, gebruikt u de optie Registratie van configuratieassistent.

  - **Label met IMEI-nummer**: door de IMEI-nummers (International Mobile Equipment Identity) van bedrijfseigen apparaten te importeren, kunt u ze in Intune labelen als apparaten die eigendom zijn van het bedrijf. Gebruikers kunnen hun apparaten vervolgens registreren als een persoonlijk apparaat door de bedrijfsportal te installeren voor toegang tot bedrijfsresources, zoals e-mail, apps en gegevens.



<!--HONumber=Nov16_HO3-->


