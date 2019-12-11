---
title: Android-apps met beveiligingsbeleid voor apps
description: In dit onderwerp wordt beschreven wat u kunt verwachten wanneer uw app wordt beheerd door een app-beveiligingsbeleid.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 02/15/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 53c8e2ad-f627-425b-9adc-39ca69dbb460
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 946ce31c613ddb3c7dd2bf4dfde7561dd56e4ca0
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "73414048"
---
# <a name="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies"></a>Wat u kunt verwachten wanneer uw Android-app wordt beheerd door een app-beveiligingsbeleid

In dit artikel wordt de gebruikerservaring voor apps met app-beveiligingsbeleid beschreven. App-beveiligingsbeleid wordt alleen toegepast wanneer apps worden gebruikt in een werkcontext, bijvoorbeeld wanneer de gebruiker apps opent met een werkaccount of bestanden opent die zijn opgeslagen in een locatie van OneDrive voor Bedrijven.

## <a name="access-apps"></a>Toegang tot apps

De bedrijfsportal-app is vereist voor alle apps die zijn gekoppeld aan app-beveiligingsbeleid op Android-apparaten.

Op apparaten die niet zijn geregistreerd bij Intune, moet de bedrijfsportal-app worden geïnstalleerd. De gebruikers hoeven de bedrijfsportal-app echter niet te starten of zich er bij aan te melden om apps te kunnen gebruiken die worden beheerd door het app-beveiligingsbeleid.

De bedrijfsportal-app is een manier voor Intune om op een veilige locatie gegevens te delen. De bedrijfsportal-app is daarom vereist voor alle apps die zijn gekoppeld aan app-beveiligingsbeleid, zelfs als het apparaat niet is geregistreerd bij Intune.

## <a name="use-apps-with-multi-identity-support"></a>Apps met ondersteuning voor meerdere identiteiten gebruiken

App-beveiligingsbeleid wordt alleen toegepast in een werkcontext. Daarom is het mogelijk dat de app zich anders gedraagt, afhankelijk of het om een persoonlijke of werkcontext gaat.

De gebruiker moet bijvoorbeeld een pincode invoeren bij het openen van werkgegevens. Voor de **Outlook-app** wordt de gebruiker gevraagd een pincode in te voeren bij het starten van de app. Voor de **OneDrive app** wordt de gebruiker om een pincode gevraagd wanneer deze het werkaccount typt. Bij Microsoft **Word**, **PowerPoint** en **Excel** wordt de gebruiker om de pincode gevraagd wanneer deze documenten opent die zijn opgeslagen op de OneDrive voor Bedrijven-locatie van het bedrijf.

## <a name="manage-user-accounts-on-the-device"></a>Gebruikersaccounts op het apparaat beheren

Met toepassingen met meerdere identiteiten kunnen gebruikers meerdere accounts toevoegen.  Intune-app-beveiliging ondersteunt slechts één beheerd account.  Intune-app-beveiliging beperkt niet het aantal niet-beheerde accounts.

Wanneer er een beheerd account in een toepassing is:

* Als een gebruiker een tweede beheerd account probeert toe te voegen, moet de gebruiker selecteren welk beheerd account moet worden gebruikt.  Het andere account wordt verwijderd.
* Als de IT-beheerder een beleid toevoegt aan een tweede bestaand account, moet de gebruiker selecteren welk beheerd account moet worden gebruikt.  Het andere account wordt verwijderd.

Lees het volgende voorbeeldscenario om meer inzicht te krijgen in hoe meerdere gebruikersaccounts worden behandeld.

Gebruiker A werkt voor twee bedrijven: **bedrijf X** en **bedrijf Y**. Gebruiker A heeft voor elk bedrijf een werkaccount en voor beide accounts wordt gebruikgemaakt van Intune om app-beveiligingsbeleid te implementeren. **Bedrijf X** implementeert app-beveiligingsbeleid **voordat** **bedrijf Y** dat doet. Het app-beveiligingsbeleid wordt toegepast op het account dat is gekoppeld aan **bedrijf X**, niet op het account dat is gekoppeld aan bedrijf Y. Als u wilt dat het gebruikersaccount dat is gekoppeld aan bedrijf Y door het app-beveiligingsbeleid wordt beheerd, moet u het gebruikersaccount dat is gekoppeld aan bedrijf X verwijderen en het account toevoegen dat is gekoppeld aan bedrijf Y.

### <a name="add-a-second-account"></a>Een tweede account toevoegen

#### <a name="android"></a>Android

Als u een Android-apparaat gebruikt, ziet u mogelijk een blokkeringsbericht met instructies voor het verwijderen van het bestaande account en toevoegen van een nieuwe account.  Als u het bestaande account wilt verwijderen, gaat u naar **Instellingen &gt;Algemeen &gt; Toepassingsbeheer &gt;Bedrijfsportal**. Vervolgens kiest u **Gegevens wissen**.

![Schermafbeelding van het foutbericht en instructies om het account te verwijderen](./media/end-user-mam-apps-android/Android_SwitchUser.png)

## <a name="view-media-files-with-the-azure-information-protection-app"></a>Mediabestanden weergeven met de Azure Information Protection-app

Als u AV-, PDF- en afbeeldingsbestanden van uw bedrijf op een Android-apparaat wilt weergeven, gebruikt u de [Microsoft Information Protection-app](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer) (voorheen de Rights Management-app voor delen).

U kunt deze app downloaden via de Google Play Store.  

De volgende bestandstypen worden ondersteund:

* **Audio:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (enhanced AAC+), AAC ELD (enhanced low delay AAC), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE
* **Video:** H.263, H.264 AVC, MPEG-4 SP, VP8
* **Afbeelding:** jpg, pjpg, png, ppng, bmp, pbmp, gif, pgif, jpeg, pjpeg
* **Documenten:** PDF, PPDF

|**pfile**|
|----|
|Pfile is een algemene 'wrapper'-indeling voor beveiligde bestanden waarmee de versleutelde inhoud en de Azure Information Protection-licenties worden ingekapseld. Deze indeling kan worden gebruikt voor het beveiligen van elk bestandstype.|

## <a name="next-steps"></a>Volgende stappen
[Wat u kunt verwachten wanneer uw iOS-app wordt beheerd door een app-beveiligingsbeleid](end-user-mam-apps-ios.md)
