---
title: App-meldingsinstellingen voor iOS-apparaten in Intune
titlesuffix: Azure portal
description: In dit onderwerp leest u over de instellingen die u kunt gebruiken voor het beheren van meldingen op iOS-apparaten.
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bda26d1d-2a3b-4669-adf8-a5aa7f994916
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 91e4b6197c7606a70862ad5fb12b10b5e0f3ed81
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="intune-app-notifications-settings-for-ios-devices"></a>App-meldingsinstellingen voor iOS-apparaten in Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Hiermee kunt u configureren hoe apps die op een apparaat zijn geïnstalleerd meldingen verzenden. Deze instellingen bieden ondersteuning voor apparaten onder supervisie waarop iOS 9.3 of hoger wordt uitgevoerd.

## <a name="configure-settings"></a>Instellingen configureren

1. Kies op de blade Apparaatfuncties de optie **App-meldingen (alleen onder supervisie)**.
2. Kies **Toevoegen**op de blade **Appmeldingen** en configureer vervolgens de volgende waarden:
    - **App-bundel-id**: voer de **App-bundel-id** in van de app die u wilt configureren. Zie voor hulp **Lijst van bundel-id's voor ingebouwde iOS-apps** verderop in dit onderwerp.
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
3. Ga door en voeg zo veel apps toe als u wilt. Als u klaar bent, kiest u **OK**.
4. Kies **OK** totdat u terugkeert naar de blade **Profiel maken** en kies vervolgens **Maken**. 


## <a name="bundle-id-reference-for-built-in-ios-apps"></a>Lijst van bundel-id’s voor ingebouwde iOS-apps

Deze lijst bevat de bundel-id's van een aantal algemene ingebouwde iOS-apps. Als u de bundel-ID van andere apps wilt weten, neemt u contact op met de softwareleverancier. 

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

U kunt het apparaatprofiel nu toewijzen aan de gewenste groepen. Zie [Apparaatprofielen toewijzen](device-profile-assign.md) voor meer informatie.
