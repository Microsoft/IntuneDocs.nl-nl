---
title: App-meldingen maken voor iOS-apparaten - Microsoft Intune - Azure | Microsoft Docs
description: App-meldingen voor iOS-apparaten toevoegen of maken in Microsoft Intune. Kies naar welke apps u meldingen wilt verzenden, configureer de instellingen voor meldingen op het vergrendelingsscherm, schakel geluid in, kies het type melding en voeg een badge toe.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bda26d1d-2a3b-4669-adf8-a5aa7f994916
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 43068163c15c0588a8a6ef745d5b191f4547a94d
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31025702"
---
# <a name="configure-app-notifications-settings-on-ios-devices-in-intune"></a>App-meldingsinstellingen op iOS-apparaten in Intune configureren

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Configureer hoe apps die op een iOS-apparaat zijn geïnstalleerd meldingen verzenden. Deze instellingen bieden ondersteuning voor apparaten onder supervisie waarop iOS 9.3 of hoger wordt uitgevoerd.

## <a name="add-the-app-notification"></a>De app-melding toevoegen

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer binnen het iOS- of macOS- profiel **Apparaatfuncties**. [iOS- of Mac OS apparaatfuncties](device-features-configure.md) vermeldt de stappen om een profiel te maken.
3. Selecteer **App-meldingen (alleen onder supervisie)** en selecteer vervolgens **Toevoegen**: ![App-melding toevoegen aan iOS- of macOS-profiel in Intune](./media/ios-macos-app-notifications.png)
4. Voer de volgende eigenschappen in:

   - **App-bundel-id**: voer de **App-bundel-id** in van de app die u wilt configureren. Zie voor hulp **Lijst van bundel-id’s voor ingebouwde iOS-apps** (in dit artikel).
   - **App-naam**: voer de naam in van de app die u wilt configureren. Deze naam wordt niet weergegeven op het apparaat en wordt gebruikt om de app te herkennen in de lijst.
   - **Uitgever**: voer de uitgever in van de app die u wilt configureren. De naam van de uitgever wordt niet weergegeven op het apparaat en wordt alleen gebruikt om de app te herkennen in de lijst.
   - **Meldingen**: in- of uitschakelen dat de app meldingen naar het apparaat verzendt. Als u deze instelling uitschakelt, worden de volgende instellingen ook uitgeschakeld.
     - **Weergeven in het meldingencentrum**: schakel deze instelling in om de app meldingen te laten weergeven in het meldingencentrum van het apparaat.
     - **Weergeven in het vergrendelingsscherm**: schakel deze instelling in om meldingen van de app weer te geven op het vergrendelingsscherm van de app.
     - **Waarschuwingstype**: selecteer het gewenste type melding wanneer het apparaat wordt ontgrendeld vanuit:
       - **Geen**: er wordt geen melding weergegeven.
       - **Banner** er wordt kort een vaandel weergegeven met hierin de melding.
       - **Modal**: de melding wordt weergegeven en de gebruiker moet deze handmatig sluiten voordat de gebruiker kan doorgaan en het apparaat kan gebruiken.
     - **Badge op app-pictogram**: schakel deze instelling in om een badge toe te voegen aan het app-pictogram om aan te geven dat de app een melding heeft verzonden.
     - **Geluiden**: schakel deze instelling in om een geluid af te spelen wanneer er een melding wordt weergegeven.

5. Ga door en voeg zo veel apps toe als u wilt. Wanneer u klaar bent met het toevoegen van apps, selecteert u **OK**.
6. Selecteer **Maken** om het profiel op te slaan.

## <a name="bundle-id-reference-for-built-in-ios-apps"></a>Lijst van bundel-id's voor ingebouwde iOS-apps

De volgende lijst bevat de bundel-id's van een aantal algemene ingebouwde iOS-apps. Als u de bundel-id van andere apps wilt weten, kunt u het beste contact opnemen met de softwareleverancier.

|||
|-|-|
|App-naam|Bundel-id|
|App Store|com.apple.AppStore|
|Rekenmachine|com.apple.calculator|
|Kalender|com.apple.mobilecal|
|Camera|com.apple.camera|
|Klok|com.apple.mobiletimer|
|Kompas|com.apple.compass|
|Contactpersonen|com.apple.MobileAddressBook|
|FaceTime|com.apple.facetime|
|Zoek vrienden|com.apple.mobileme.fmf1|
|Zoek mijn iPhone|com.apple.mobileme.fmip1|
|Game Center|com.apple.gamecenter|
|GarageBand|com.apple.mobilegarageband|
|Status|com.apple.Health|
|iBooks|com.apple.iBooks|
|iTunes Store|com.apple.MobileStore|
|iTunes U|com.Apple.itunesu|
|Keynote|com.apple.Keynote|
|Mail|com.Apple.mobilemail|
|Kaarten|com.apple.Maps|
|Berichten|com.apple.MobileSMS|
|Music|com.apple.Music|
|Nieuws|com.apple.news|
|Opmerkingen|com.apple.mobilenotes|
|Getallen|com.apple.Numbers|
|Pages|com.apple.Pages|
|Photo Booth|com.apple.Photo-Booth|
|Foto's|com.apple.mobileslideshow|
|Podcasts|com.apple.podcasts|
|Herinneringen|com.apple.reminders|
|Safari|com.apple.mobilesafari|
|Instellingen|com.apple.Preferences|
|Aandelen|com.apple.stocks|
|Tips|com.apple.tips|
|Video 's|com.apple.videos|
|Dictafoon|com.apple.VoiceMemos|
|Wallet|com.apple.Passbook|
|Watch|com.apple.Bridge|
|Weer|com.apple.weather|

## <a name="next-steps"></a>Volgende stappen

Wijs het apparaatprofiel toe aan de gewenste groepen. In [Apparaatprofielen toewijzen](device-profile-assign.md) worden de stappen beschreven.