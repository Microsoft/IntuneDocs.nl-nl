---
title: Uw Mac OS-apparaat registreren bij Intune | Microsoft Docs
description: Informatie over hoe u een Mac OS-apparaat bij Intune kunt registreren
keywords: Mac OS X, Mac OS, OS X
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58eb0e7a-1321-4c66-a281-88fb01e72c1c
searchScope: User help
ROBOTS: 
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 16f7f06d02a56b4887c0d29ffcaed111185652a9
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="enroll-your-macos-device-in-intune"></a>Uw Mac OS-apparaat registreren bij Intune

Door toegang te verkrijgen tot de apps, gegevens en bronnen van uw organisatie krijgt u uw werkzaamheden gedaan. Als u een Mac OS-apparaat op het werk gebruikt, betekent dit dat u een __beheerprofiel__ moet installeren. Dit is gewoon een bestand dat door uw IT-beheerder wordt ingesteld en dat instellingen laadt en toegang verkrijgt tot informatie op uw Mac. Wilt u meer weten? Lees [wat er gebeurt als u de bedrijfsportal-app installeert en uw apparaat registreert bij Intune](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md)

  > [!NOTE]
  > Als u een iOS-apparaat probeert te registreren, zoals een iPhone of iPad, [volgt u in plaats daarvan deze instructies](enroll-your-device-in-intune-ios.md).

1. Ga in de __Dock__ naar __Safari__ en open een nieuw venster. Open vervolgens de [bedrijfsportalwebsite](http://portal.manage.microsoft.com).
2. Meld u aan bij de bedrijfsportalwebsite met uw werk- of schoolaccount.

  [!INCLUDE[wit_nextref](includes/end-user-password-guidance.md)]

3. Wanneer u zich aanmeldt, ziet u alle beschikbare tabbladen: __Home__, __Apps__ en __Categorieën__. Op deze pagina ziet u alle beschikbare apps die u kunt installeren. Als u nog geen apparaten hebt ingeschreven, ziet u de volgende melding **We kunnen u geen apps tonen.** U kunt doorgaan door __Mijn apparaten__ te selecteren.

 ![Een schermafbeelding van de startpagina voor de web-portal waarin wordt aangegeven dat er nog geen apps kunnen worden geïnstalleerd, met een knop Mijn apparaten eronder.](./media/macOS_enroll_001_landing_page.png)

4. Op de pagina __Mijn apparaten__ ziet u ofwel een lijst van geregistreerde apparaten of gewoon een koptekst. Dit is afhankelijk van of u al een apparaat hebt ingeschreven, macOS of anderszins. Om een apparaat in te schrijven dat niet wordt weergegeven, selecteert u de koptekst __Klik hier als uw apparaat in de lijst voorkomt om het te identificeren. U kunt ook hier tikken om uw apparaat in te schrijven als dit niet wordt weergegeven__.

  ![Een schermafbeelding van de pagina Mijn apparaat met een paar onbekende apparaten boven de koptekst die vraagt naar het inschrijven van niet-vermelde apparaten of het identificeren van ongeïdentificeerde apparaten.](./media/macOS_enroll_002_tap_here_banner.png)

5. Er wordt een pop-upvenster weergegeven met een korte uitleg waarom u __dit apparaat gaat identificeren of registreren__. Controleer deze informatie en klik vervolgens op __Registreren__ om door te gaan.

 ![Dit Mac OS-apparaat identificeren of registreren](./media/macOS_enroll_003_IDenroll_popup.png)

6. Er wordt een tweede pop-upvenster weergegeven met een korte uitleg wat er gebeurt wanneer u __dit apparaat registreert__. Controleer deze informatie en klik vervolgens op __Installeren__ om door te gaan.

 ![Dit Mac OS-apparaat registreren](./media/macOS_enroll_004_enroll_popup.png)

  > [!NOTE]
  > Intune heeft toegang nodig tot uw computer om te controleren of dit apparaat voldoende is beveiligd om toegang te verkrijgen tot de bronnen van uw organisatie. Lees [wat er gebeurt wanneer u uw apparaat registreert bij Intune](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-ios.md).

7. De __Systeemvoorkeuren__ worden geopend en de vraag __Beheerprofiel installeren?__ wordt weergegeven Klik op __Installeren__ om door te gaan, of klik op __Profiel weergeven__ voor meer informatie.

 ![Beheerprofiel installeren](./media/macOS_enroll_005_sysprefs_mgmt_profile.png)

8. Er wordt een pop-upvenster van Mac OS weergegeven. Bevestig dat u wijzigen wilt aanbrengen door de __Gebruikersnaam__ en het __Wachtwoord__ van uw computer op te geven en klik vervolgens op __OK__. Hiermee installeert u het beheerprofiel op uw Mac.

 ![Pop-upvenster Mac OS-profiel installeren](./media/macOS_enroll_006_sysprefs_admin_login.png)

9. Mogelijk worden u enkele extra berichten op uw Mac weergegeven met meer informatie over het profiel of met de vraag of u zeker weet of u het profiel wilt __Installeren__. Klik in deze berichten op __Doorgaan__ en __Installeren__ om door te gaan. Nadat de installatie is voltooid, kunt u uw zojuist geïnstalleerde __Beheerprofiel__ bekijken in de lijst met __Apparaatprofielen__.

 ![Mac OS-profiel geïnstalleerd](./media/macOS_enroll_007_sysprefs_installed_profile.png)

Nog hulp nodig? Neem contact op met uw IT-beheerder. U vindt de contactgegevens van uw beheerder op de [bedrijfsportalwebsite](http://portal.manage.microsoft.com).
