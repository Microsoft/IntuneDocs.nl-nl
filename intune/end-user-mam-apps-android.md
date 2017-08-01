---
title: Android-apps met beveiligingsbeleid voor apps
description: In dit onderwerp wordt beschreven wat u kunt verwachten wanneer uw app wordt beheerd door een app-beveiligingsbeleid.
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c8e2ad-f627-425b-9adc-39ca69dbb460
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 030e17a9f28a9476c82e89d4dd26151a2d3cb953
ms.sourcegitcommit: f100c943a635f5a08254ba7cf30f1aaebb7e810e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2017
---
# <a name="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies"></a>Wat u kunt verwachten wanneer uw Android-app wordt beheerd door een app-beveiligingsbeleid

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

In dit onderwerp wordt de gebruikerservaring voor apps met app-beveiligingsbeleid beschreven. App-beveiligingsbeleid wordt alleen toegepast wanneer apps worden gebruikt in een werkcontext, bijvoorbeeld wanneer de gebruiker apps gebruikt met een werkaccount of bestanden opent die zijn opgeslagen in de OneDrive voor Bedrijven-locatie van uw bedrijf.
##  <a name="access-apps"></a>Toegang tot apps

De bedrijfsportal-app is vereist voor alle apps die zijn gekoppeld aan app-beveiligingsbeleid op Android-apparaten.

Op apparaten die niet zijn geregistreerd bij Intune, moet de bedrijfsportal-app worden geïnstalleerd. De gebruikers hoeven de bedrijfsportal-app echter niet te starten of zich er bij aan te melden om apps te kunnen gebruiken die worden beheerd door het app-beveiligingsbeleid.

De bedrijfsportal-app is een manier voor Intune om op een veilige locatie gegevens te delen. De bedrijfsportal-app is daarom vereist voor alle apps die zijn gekoppeld aan app-beveiligingsbeleid, zelfs als het apparaat niet is geregistreerd bij Intune.


##  <a name="use-apps-with-multi-identity-support"></a>Apps met ondersteuning voor meerdere identiteiten gebruiken

App-beveiligingsbeleid wordt alleen toegepast in een werkcontext. Daarom is het mogelijk dat de app zich anders gedraagt, afhankelijk of het om een persoonlijke of werkcontext gaat.

De gebruiker moet bijvoorbeeld een pincode invoeren bij het openen van werkgegevens. Voor de **Outlook-app** wordt de gebruiker gevraagd een pincode in te voeren bij het starten van de app. Voor de **OneDrive app** wordt de gebruiker om een pincode gevraagd wanneer deze het werkaccount typt. Bij Microsoft **Word**, **PowerPoint** en **Excel** wordt de gebruiker om de pincode gevraagd wanneer deze documenten opent die zijn opgeslagen op de OneDrive voor Bedrijven-locatie van het bedrijf.

##  <a name="manage-user-accounts-on-the-device"></a>Gebruikersaccounts op het apparaat beheren

Intune biedt ondersteuning voor de implementatie van app-beveiligingsbeleid voor slechts één gebruikersaccount per apparaat.

* Afhankelijk van de app die u gebruikt, kan het zijn dat de tweede gebruiker op het apparaat wordt geblokkeerd. In alle gevallen wordt echter alleen de eerste gebruiker die het app-beveiligingsbeleid ontvangt, door het beleid beïnvloed.

  * **Microsoft Word**, **Excel** en **PowerPoint** blokkeren een tweede gebruikersaccount niet, maar het tweede gebruikersaccount wordt niet beïnvloed door het app-beveiligingsbeleid.

  * Voor de apps **OneDrive** en **Outlook** kunt u slechts één werkaccount gebruiken.  Het is niet mogelijk om meerdere werkaccounts voor deze apps toe te voegen.  U kunt wel een gebruiker verwijderen en een andere gebruiker op het apparaat toevoegen.


* Als een apparaat meerdere gebruikersaccounts heeft voordat het app-beveiligingsbeleid wordt geïmplementeerd, wordt het account waarop het app-beveiligingsbeleid als eerste wordt geïmplementeerd, door het app-beveiligingsbeleid van Intune beheerd.


Lees het volgende voorbeeldscenario om meer inzicht te krijgen in hoe meerdere gebruikersaccounts worden behandeld.

Gebruiker A werkt voor twee bedrijven: **bedrijf X** en **bedrijf Y**. Gebruiker A heeft voor elk bedrijf een werkaccount en voor beide accounts wordt gebruikgemaakt van Intune om app-beveiligingsbeleid te implementeren. **Bedrijf X** implementeert app-beveiligingsbeleid **voordat** **bedrijf Y** dat doet. Het app-beveiligingsbeleid wordt toegepast op het account dat is gekoppeld aan **bedrijf X**, niet op het account dat is gekoppeld aan bedrijf Y. Als u wilt dat het gebruikersaccount dat is gekoppeld aan bedrijf Y, door het app-beveiligingsbeleid wordt beheerd, moet u het gebruikersaccount dat is gekoppeld aan bedrijf X, verwijderen.
### <a name="add-a-second-account"></a>Een tweede account toevoegen
####  <a name="android"></a>Android
Als u een Android-apparaat gebruikt, ziet u mogelijk een blokkeringsbericht met instructies voor het verwijderen van het bestaande account en toevoegen van een nieuwe account.  Als u het bestaande account wilt verwijderen, gaat u naar **Instellingen &gt;Algemeen &gt; Toepassingsbeheer &gt;Bedrijfsportal**. Vervolgens kiest u **Gegevens wissen**.

![Schermafbeelding van het foutbericht en instructies om het account te verwijderen](./media/Android_SwitchUser.png)

##  <a name="view-media-files-with-the-azure-information-protection-app"></a>Mediabestanden weergeven met de Azure Information Protection-app
Als u AV-, PDF- en afbeeldingsbestanden van uw bedrijf op een Android-apparaat wilt weergeven, gebruikt u de [Microsoft Information Protection-app](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer) (voorheen de Rights Management-app voor delen).

U kunt deze app downloaden via de Google Play Store.  

De volgende bestandstypen worden ondersteund:

* **Audio:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (enhanced AAC+), AAC ELD (enhanced low delay AAC), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE
* **Video:** H.263, H.264 AVC, MPEG-4 SP, VP8
* **Afbeelding:** jpg, pjpg, png, ppng, bmp, pbmp, gif, pgif, jpeg, pjpeg
* **Documenten:** PDF, PPDF


|**pfile**|**tekst**|
|----|----|
|Pfile is een algemene 'wrapper'-indeling voor beveiligde bestanden waarmee de versleutelde inhoud en de Azure Information Protection-licenties worden ingekapseld. Deze indeling kan worden gebruikt voor het beveiligen van elk bestandstype.|Tekstbestanden, zoals XML, CSV enzovoort, kunnen worden geopend voor weergave in de app, zelfs wanneer ze zijn beveiligd. Bestandstypen: txt, ptxt, csv, pcsv, log, plog, xml, pxml.|

## <a name="next-steps"></a>Volgende stappen
[Wat u kunt verwachten wanneer uw iOS-app wordt beheerd door een app-beveiligingsbeleid](end-user-mam-apps-ios.md)
