---
title: Android-apps met MAM-beleid | Microsoft Docs
description: Dit onderwerp beschrijft wat u kunt verwachten wanneer uw app wordt beheerd door beleidsregels voor beheer van mobiele apps.
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c8e2ad-f627-425b-9adc-39ca69dbb460
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: aeacfddb3ed42938dd9443e2734222c977436430


---

# <a name="what-to-expect-when-your-android-app-is-managed-by-mam-policies"></a>Wat u kunt verwachten wanneer uw Android-app wordt beheerd door MAM-beleid

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

In dit onderwerp wordt de gebruikerservaring voor apps met MAM-beleid (Mobile Application Management) beschreven. MAM-beleidsregels worden alleen toegepast wanneer apps worden gebruikt in een werkcontext, bijvoorbeeld wanneer de gebruiker apps gebruikt met een werkaccount of bestanden opent die zijn opgeslagen in de OneDrive voor Bedrijven-locatie van uw bedrijf.
##  <a name="access-apps"></a>Toegang tot apps

De bedrijfsportal-app is vereist voor alle apps die zijn gekoppeld aan MAM-beleid op Android-apparaten.

Op apparaten die niet zijn geregistreerd bij Intune, moet de bedrijfsportal-app worden geïnstalleerd. De gebruikers hoeven de bedrijfsportal-app echter niet te starten of zich er bij aan te melden voordat ze de apps kunnen gebruiken die worden beheerd door het MAM-beleid.

De bedrijfsportal-app is een manier voor Intune om op een veilige locatie gegevens te delen. De bedrijfsportal-app is daarom vereist voor alle apps die zijn gekoppeld aan MAM-beleid, zelfs als het apparaat niet is geregistreerd bij Intune.


##  <a name="use-apps-with-multi-identity-support"></a>Apps met ondersteuning voor meerdere identiteiten gebruiken

MAM-beleidsregels worden alleen toegepast in de context van het werk. Daarom is het mogelijk dat de app zich anders gedraagt, afhankelijk of het om een persoonlijke of werkcontext gaat.

De gebruiker moet bijvoorbeeld een pincode invoeren bij het openen van werkgegevens. Voor de **Outlook-app** wordt de gebruiker gevraagd een pincode in te voeren bij het starten van de app. Voor de **OneDrive app** wordt de gebruiker om een pincode gevraagd wanneer deze het werkaccount typt. Bij Microsoft **Word**, **PowerPoint** en **Excel** wordt de gebruiker om de pincode gevraagd wanneer deze documenten opent die zijn opgeslagen op de OneDrive voor Bedrijven-locatie van het bedrijf.

##  <a name="manage-user-accounts-on-the-device"></a>Gebruikersaccounts op het apparaat beheren

Intune biedt alleen ondersteuning voor de implementatie van MAM-beleid naar slechts één gebruikersaccount per apparaat.

* Afhankelijk van de app die u gebruikt, kan het zijn dat de tweede gebruiker op het apparaat wordt geblokkeerd. In alle gevallen wordt echter alleen de eerste gebruiker die het MAM-beleid ontvangt, door het beleid beïnvloed.

  * **Microsoft Word**, **Excel** en **PowerPoint** blokkeren een tweede gebruikersaccount niet, maar de tweede gebruikersaccount wordt niet beïnvloed door het MAM-beleid.

  * Voor de apps **OneDrive** en **Outlook** kunt u slechts één werkaccount gebruiken.  Het is niet mogelijk om meerdere werkaccounts voor deze apps toe te voegen.  U kunt wel een gebruiker verwijderen en een andere gebruiker op het apparaat toevoegen.


* Als een apparaat meerdere gebruikersaccounts heeft voordat het MAM-beleid wordt geïmplementeerd, wordt het account waarop het MAM-beleid als eerste wordt geïmplementeerd, door het Intune MAM-beleid beheerd.


Lees het volgende voorbeeldscenario om meer inzicht te krijgen in hoe meerdere gebruikersaccounts worden behandeld.

Gebruiker A werkt voor twee bedrijven: **bedrijf X** en **bedrijf Y**. Gebruiker A heeft voor elk bedrijf een werkaccount en voor beide accounts wordt gebruikgemaakt van Intune om MAM-beleid te implementeren. **Bedrijf X** implementeert MAM-beleid **voordat** **bedrijf Y** dat doet. Het MAM-beleid wordt toegepast op het account dat is gekoppeld aan **bedrijf X**, niet op het account dat is gekoppeld aan bedrijf Y. Als u wilt dat het gebruikersaccount dat is gekoppeld aan bedrijf Y, door het MAM-beleid wordt beheerd, moet u het gebruikersaccount dat is gekoppeld aan bedrijf X, verwijderen.
### <a name="add-a-second-account"></a>Een tweede account toevoegen
####  <a name="android"></a>Android
Als u een Android-apparaat gebruikt, ziet u mogelijk een blokkeringsbericht met instructies voor het verwijderen van het bestaande account en toevoegen van een nieuwe account.  Als u het bestaande account wilt verwijderen, gaat u naar **Instellingen &gt;Algemeen &gt; Toepassingsbeheer &gt;Bedrijfsportal**. Vervolgens kiest u **Gegevens wissen**.

![Schermafbeelding van het foutbericht en instructies om het account te verwijderen](../media/AppManagement/Android_SwitchUser.png)

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
[Wat u kunt verwachten wanneer uw iOS-app wordt beheerd door MAM-beleid](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)

### <a name="see-also"></a>Zie tevens
[Beleid voor Mobile App Management maken en implementeren met Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


