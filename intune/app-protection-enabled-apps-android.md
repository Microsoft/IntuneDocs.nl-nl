---
title: Android-apps met beveiligingsbeleid voor apps
titleSuffix: Intune on Azure
description: In dit onderwerp wordt beschreven wat u kunt verwachten wanneer uw Android-app wordt beheerd door een app-beveiligingsbeleid.
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a6816285-8e43-4dc8-bca0-e80ec5ef01e6
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 63badd001958f22339415e0cd03da9ade275c6f3
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies"></a>Wat u kunt verwachten wanneer uw Android-app wordt beheerd door een app-beveiligingsbeleid 
[!INCLUDE[azure_portal](./includes/azure_portal.md)]In dit onderwerp wordt de gebruikerservaring voor apps met app-beveiligingsbeleid beschreven. App-beveiligingsbeleid wordt alleen toegepast wanneer apps worden gebruikt in een werkcontext, dus wanneer u apps gebruikt met uw werkaccount of bestanden opent die zijn opgeslagen in de OneDrive voor Bedrijven-locatie van uw bedrijf.
##  <a name="accessing-apps"></a>Apps openen

De bedrijfsportal-app is vereist voor alle apps die zijn gekoppeld aan app-beveiligingsbeleid op Android-apparaten.

Op apparaten die niet zijn ingeschreven bij Intune moet de bedrijfsportal-app worden geïnstalleerd. De gebruikers hoeven de bedrijfsportal-app echter niet te starten of zich er bij aan te melden voordat ze de apps kunnen gebruiken die worden beheerd door app-beveiligingsbeleid.
De bedrijfsportal-app wordt door Intune gebruikt om gegevens te delen op een veilige locatie, en is dus ook vereist als het apparaat niet is ingeschreven bij Intune.


##  <a name="using-apps-with-multi-identity-support"></a>Apps met ondersteuning voor meerdere identiteiten gebruiken

App-beveiligingsbeleid wordt alleen toegepast wanneer de app wordt gebruikt in een werkcontext, dus de app werkt mogelijk anders afhankelijk van de context waarin u die gebruikt (werk of persoonlijk).

Voor apps die meerdere identiteiten ondersteunen past Intune het app-beveiligingsbeleid alleen toe wanneer de eindgebruiker de app gebruikt in de werkcontext.  De gebruiker moet bijvoorbeeld een pincode invoeren bij het openen van bedrijfsgegevens.  Bij de **Outlook-app** wordt de gebruiker gevraagd een pincode in te voeren bij het starten van de app. Bij de **OneDrive-app** gebeurt dit wanneer de eindgebruiker het werkaccount invoert.  Bij **Microsoft Word**, **PowerPoint* en **Excel** gebeurt dit wanneer de eindgebruiker documenten opent die zijn opgeslagen in de OneDrive voor Bedrijven-locatie van uw bedrijf.
##  <a name="managing-user-accounts-on-the-device"></a>Gebruikersaccounts op het apparaat beheren

Intune biedt alleen ondersteuning voor het implementeren van app-beveiligingsbeleid naar slechts één gebruikersaccount per apparaat.

* Afhankelijk van de app die u gebruikt, kan het zijn dat de tweede gebruiker op het apparaat wordt geblokkeerd. In alle gevallen wordt echter alleen de eerste gebruiker die het app-beveiligingsbeleid ontvangt, door het beleid beïnvloed.

  * **Microsoft Word**, **Excel** en **PowerPoint** blokkeren een tweede gebruikersaccount niet, maar het tweede gebruikersaccount wordt niet beïnvloed door het app-beveiligingsbeleid.

  * Voor de **OneDrive-app en Outlook-app** kunt u slechts één werkaccount gebruiken.  Het toevoegen van meerdere werkaccounts is op deze apps geblokkeerd.  U kunt wel een gebruiker verwijderen en een andere gebruiker op het apparaat toevoegen.


* Als een apparaat meerdere gebruikersaccounts heeft voordat het app-beveiligingsbeleid wordt geïmplementeerd, wordt het account waarop het app-beveiligingsbeleid als eerste wordt geïmplementeerd, door het app-beveiligingsbeleid van Intune beheerd.


Lees het voorbeeldscenario hieronder om meer inzicht te krijgen in hoe meerdere gebruikersaccounts worden behandeld.

Gebruiker A werkt voor twee bedrijven: **bedrijf X** en **bedrijf Y**. Gebruiker A heeft voor elk bedrijf een werkaccount en voor beide accounts wordt gebruikgemaakt van Intune om app-beveiligingsbeleid te implementeren. **Bedrijf X** implementeert app-beveiligingsbeleid **voordat** **bedrijf Y** dat doet. Het app-beveiligingsbeleid wordt toegepast op het account dat is gekoppeld aan **bedrijf X**, niet op het account dat is gekoppeld aan bedrijf Y. Als u wilt dat het gebruikersaccount dat is gekoppeld aan bedrijf Y, door het app-beveiligingsbeleid wordt beheerd, moet u het gebruikersaccount dat is gekoppeld aan bedrijf X, verwijderen.
### <a name="adding-a-second-account"></a>Een tweede account toevoegen
####  <a name="android"></a>Android
Als u een Android-apparaat gebruikt, ziet u mogelijk een blokkeringsbericht met instructies voor het verwijderen van het bestaande account en toevoegen van een nieuwe account.  Als u het bestaande account wilt verwijderen, gaat u naar **Instellingen &gt;Algemeen &gt; Toepassingsbeheer &gt;Bedrijfsportal en selecteert u Gegevens wissen**.

![Schermafbeelding van het foutbericht en instructies om het account te verwijderen](./media/android-switch-user.png)

##  <a name="viewing-media-files-with-the-azure-information-protection-app-previously-known-as-rights-management-sharing-app"></a>Mediabestanden weergeven met de Azure Information Protection-app (voorheen de Rights Management-app voor delen)
Als u AV-, PDF- en afbeeldingsbestanden van uw bedrijf op een Android-apparaat wilt weergeven, gebruikt u de [Microsoft Information Protection-app](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer).

Download deze app in Google Play.  

De volgende bestandstypen worden ondersteund:

* **Audio:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (enhanced AAC+), AAC ELD (enhanced low delay AAC), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE.
* **Video:** H.263, H.264 AVC, MPEG-4 SP, VP8.
* **Afbeelding:** jpg, pjpg, png, ppng, bmp, pbmp, gif, pgif, jpeg, pjpeg.
* **Documenten:** PDF, PPDF

------------
|**pfile**|**tekst**|
|----|----|
|Pfile is een algemene 'wrapper'-indeling voor beveiligde bestanden waarmee de versleutelde inhoud en de Azure Information Protection-licenties worden ingekapseld en die kan worden gebruikt voor het beveiligen van elk bestandstype.|Tekstbestanden, zoals XML, CSV enzovoort, kunnen worden geopend voor weergave in de app, zelfs wanneer ze zijn beveiligd. Bestandstypen: txt, ptxt, csv, pcsv, log, plog, xml, pxml.|
---------------
## <a name="next-steps"></a>Volgende stappen
[Wat u kunt verwachten wanneer uw iOS-app wordt beheerd door een app-beveiligingsbeleid](app-protection-enabled-apps-ios.md)

### <a name="see-also"></a>Zie tevens
[App-beveiligingsbeleid maken en implementeren met Microsoft Intune](app-protection-policies.md)
