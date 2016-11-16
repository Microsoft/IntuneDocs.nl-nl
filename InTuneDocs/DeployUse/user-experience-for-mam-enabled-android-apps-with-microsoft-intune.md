---
title: Android-apps met MAM-beleid | Microsoft Intune
description: Dit onderwerp beschrijft wat u kunt verwachten wanneer uw app wordt beheerd door beleidsregels voor beheer van mobiele apps.
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c8e2ad-f627-425b-9adc-39ca69dbb460
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 389daf0ed39fa2cd4b2e5d6e52cbd6809a568c9e
ms.openlocfilehash: 546b909737b4ea34bd747880fe8ed2d366c6b18a


---

# Wat u kunt verwachten wanneer uw Android-app wordt beheerd door MAM-beleid
Dit onderwerp beschrijft de gebruikerservaring voor apps met MAM-beleid. Beleid voor het beheer van mobiele toepassingen (MAM) wordt alleen toegepast wanneer apps worden gebruikt in een werkcontext, dus wanneer u apps gebruikt met uw werkaccount of bestanden opent die zijn opgeslagen in de OneDrive voor Bedrijven-locatie van uw bedrijf.
##  Apps openen

De bedrijfsportal-app is vereist voor alle apps die zijn gekoppeld aan MAM-beleid op Android-apparaten.

Op apparaten die niet zijn ingeschreven bij Intune moet de bedrijfsportal-app worden geïnstalleerd. De gebruikers hoeven de bedrijfsportal-app echter niet te starten of zich er bij aan te melden voordat ze de apps kunnen gebruiken die worden beheerd door het MAM-beleid.
De bedrijfsportal-app wordt door Intune gebruikt om gegevens te delen op een veilige locatie, en is dus ook vereist als het apparaat niet is ingeschreven bij Intune.


##  Apps met ondersteuning voor meerdere identiteiten gebruiken

Het MAM-beleid wordt alleen toegepast wanneer de app wordt gebruikt in een werkcontext, dus de app werkt mogelijk anders afhankelijk van de context waarin u die gebruikt (werk of persoonlijk).

Voor apps die meerdere identiteiten ondersteunen past Intune het MAM-beleid alleen toe wanneer de eindgebruiker de app gebruikt in de werkcontext.  De gebruiker moet bijvoorbeeld een pincode invoeren bij het openen van bedrijfsgegevens.  Bij de **Outlook-app** wordt de gebruiker gevraagd een pincode in te voeren bij het starten van de app. Bij de **OneDrive-app** gebeurt dit wanneer de eindgebruiker het werkaccount invoert.  Bij Microsoft **Word**, **PowerPoint* en **Excel** gebeurt dit wanneer de eindgebruiker documenten opent die zijn opgeslagen in de OneDrive voor Bedrijven-locatie van uw bedrijf.
##  Gebruikersaccounts op het apparaat beheren

Intune biedt alleen ondersteuning voor het implementeren van MAM-beleid naar slechts één gebruikersaccount per apparaat.

* Afhankelijk van de app die u gebruikt, kan het zijn dat de tweede gebruiker op het apparaat wordt geblokkeerd. In alle gevallen wordt echter alleen de eerste gebruiker die het MAM-beleid ontvangt, door het beleid beïnvloed.

  * **Microsoft Word**, **Excel** en **PowerPoint** blokkeren een tweede gebruikersaccount niet, maar de tweede gebruikersaccount wordt niet beïnvloed door het MAM-beleid.

  * Voor de **OneDrive-app en Outlook-app** kunt u slechts één werkaccount gebruiken.  Het toevoegen van meerdere werkaccounts is op deze apps geblokkeerd.  U kunt wel een gebruiker verwijderen en een andere gebruiker op het apparaat toevoegen.


* Als een apparaat meerdere gebruikersaccounts heeft voordat het MAM-beleid wordt geïmplementeerd, wordt het account waarop het MAM-beleid als eerste wordt geïmplementeerd, door het Intune MAM-beleid beheerd.


Lees het voorbeeldscenario hieronder om meer inzicht te krijgen in hoe meerdere gebruikersaccounts worden behandeld.

Gebruiker A werkt voor twee bedrijven: **bedrijf X** en **bedrijf Y**. Gebruiker A heeft voor elk bedrijf een werkaccount en voor beide accounts wordt gebruikgemaakt van Intune om MAM-beleid te implementeren. **Bedrijf X** implementeert MAM-beleid **voordat** **bedrijf Y** dat doet. Het MAM-beleid wordt toegepast op het account dat is gekoppeld aan **bedrijf X**, niet op het account dat is gekoppeld aan bedrijf Y. Als u wilt dat het gebruikersaccount dat is gekoppeld aan bedrijf Y, door het MAM-beleid wordt beheerd, moet u het gebruikersaccount dat is gekoppeld aan bedrijf X, verwijderen.
### Een tweede account toevoegen
####  Android
Als u een Android-apparaat gebruikt, ziet u mogelijk een blokkeringsbericht met instructies voor het verwijderen van het bestaande account en toevoegen van een nieuwe account.  Als u het bestaande account wilt verwijderen, gaat u naar **Instellingen &gt;Algemeen &gt; Toepassingsbeheer &gt;Bedrijfsportal en selecteert u Gegevens wissen**.

![Schermafbeelding van het foutbericht en instructies om het account te verwijderen](../media/AppManagement/Android_SwitchUser.png)

##  Mediabestanden weergeven met de Azure Information Protection-app (voorheen de Rights Management-app voor delen)
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
## Volgende stappen
[Wat u kunt verwachten wanneer uw iOS-app wordt beheerd door MAM-beleid](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)

### Zie tevens
[Beleid voor Mobile App Management maken en implementeren met Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


