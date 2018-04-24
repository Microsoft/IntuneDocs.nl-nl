---
title: Kiezen hoe u mobiele apparaten registreert
description: Bepalen hoe u mobiele apparaten in Intune kunt registreren door enkele eenvoudige vragen te beantwoorden
keywords: ''
author: NathBarn
ms.author: nathbarn
manager: dougeby
ms.date: 03/27/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 40262e47-1ab4-437d-8ca5-c89b5022f91f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.custom: intune-classic EXPIERIMENT
ms.openlocfilehash: b730aae4e3e8f576824ac61811018293cc07e080
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="choose-how-to-enroll-mobile-devices"></a>Kiezen hoe u mobiele apparaten registreert

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Aan de hand van uw antwoorden op de volgende vragen kan worden bepaald welke registratiemethode u het beste kunt gebruiken voor de apparaten die u beheert.

## <a name="how-will-you-manage-dedicated-corporate-owned-devices"></a>**Hoe beheert u apparaten die het eigendom zijn van uw bedrijf?**

> [!div class="button"]
> [iOS DEP >](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)  
> [!div class="button"]
> [iOS-configuratieassistent >](/intune-classic/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
> [!div class="button"]
> [Labellen met IMEI >](/intune-classic/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  U kunt apparaten in bedrijfseigendom met toegewezen gebruikers op de volgende manieren registreren:

  - **Het Device Enrollment Program (DEP) van Apple**: u kunt voor iOS-apparaten die zijn aangeschaft of worden beheerd met DEP een registratieprofiel gebruiken. Wanneer gebruikers hun apparaat voor het eerst inschakelen, downloadt het apparaat het DEP-profiel en wordt het apparaat geregistreerd bij Intune.

  - **Apple Configurator op een Mac**: Apple Configurator is een Apple-toepassing die wordt uitgevoerd op een Mac-computer. U kunt uw iOS-apparaten met een USB-kabel aansluiten op de Mac om een registratieprofiel op het apparaat te installeren. Als u de fabrieksinstellingen van het apparaat kunt terugzetten om ze te registreren, gebruikt u Registratie van configuratieassistent.

  - **Label met IMEI-nummer**: door de IMEI-nummers (International Mobile Equipment Identity) van bedrijfseigen apparaten te importeren, kunt u ze in Intune labelen als apparaten die eigendom zijn van het bedrijf. Dit is de enige manier om specifieke Windows- en Android-apparaten (met één gebruiker) te identificeren als bedrijfseigendom. iOS-apparaten die niet worden geregistreerd bij het apparaatregistratieprogramma van Apple of Apple Configurator, kunnen ook worden gelabeld met een IMEI-nummer. Wanneer u apparaten hebt geregistreerd als bedrijfseigendom, kunt u ze distribueren aan gebruikers. Gebruikers kunnen hun apparaten vervolgens registreren als een speciaal apparaat door de bedrijfsportal te installeren voor toegang tot bedrijfsresources, zoals e-mail, apps en gegevens.

> [!div class="button"]
> [< Terug](choose-how-to-enroll-devices3.md)
