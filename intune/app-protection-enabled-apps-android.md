---
title: Android-apps met beveiligingsbeleid voor apps
titlesuffix: Microsoft Intune
description: Informatie over wat u kunt verwachten van een Android-app met beveiligingsbeleid.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/07/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a6816285-8e43-4dc8-bca0-e80ec5ef01e6
ms.reviewer: andcerat
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 6e38ac954f0b8c85b7127143c98f41bfe5497ef9
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52179572"
---
# <a name="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies"></a>Wat u kunt verwachten wanneer uw Android-app wordt beheerd door een app-beveiligingsbeleid 

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Informatie over wat u kunt verwachten van een Android-app met beveiligingsbeleid. App-beveiligingsbeleid wordt alleen toegepast wanneer apps in de context van het werk worden gebruikt. Wanneer u bijvoorbeeld een app met een werkaccount opent, of wanneer u bestanden opent die zijn opgeslagen in de OneDrive-locatie van uw bedrijf.
##  <a name="accessing-apps"></a>Apps openen

De bedrijfsportal-app is vereist voor alle apps op Android-apparaten die app-beveiligingsbeleid hebben.

Installeer de bedrijfsportal installeren op alle apparaten die niet zijn ingeschreven bij Intune. Gebruikers hoeven zich niet aan te melden bij de bedrijfsportal-app om apps met app-beveiligingsbeleid te gebruiken.
Met de bedrijfsportal-app kunt u op een veilige locatie gegevens delen. Het is daarom zelfs voor niet-ingeschreven apparaten een vereiste.


##  <a name="using-apps-with-multi-identity-support"></a>Apps met ondersteuning voor meerdere identiteiten gebruiken

App-beveiligingsbeleid wordt pas van kracht wanneer een gebruiker probeert toegang te krijgen tot werkgerelateerde gegevens.  Mogelijk ziet u ander gedrag als de gebruiker de app voor persoonlijk gebruik opent.

Bepaalde apps ondersteunen meerdere identiteiten. In dit geval past Intune alleen app-beveiligingsbeleid toe wanneer een gebruiker zakelijke gegevens benadert.  Een gebruiker kan bijvoorbeeld om een pincode worden gevraagd.  In de **Outlook-app** wordt een prompt weergegeven wanneer een gebruiker de app start. In de **OneDrive-app** wordt een prompt weergegeven wanneer een gebruiker het werkaccount invoert.  In Microsoft **Word**, **PowerPoint** en **Excel** wordt een prompt weergegeven wanneer een gebruiker OneDrive-bedrijfsdocumenten opent.
##  <a name="managing-user-accounts-on-the-device"></a>Gebruikersaccounts op het apparaat beheren

Intune biedt ondersteuning voor het implementeren van app-beveiligingsbeleid naar één gebruikersaccount per apparaat.

* Afhankelijk van de app die u gebruikt, kan het zijn dat de tweede gebruiker op het apparaat wordt geblokkeerd. In alle gevallen wordt echter alleen de eerste gebruiker die het app-beveiligingsbeleid ontvangt, door het beleid beïnvloed.

  * **Microsoft Word**, **Excel** en **PowerPoint** blokkeren toegang tot een extra gebruikersaccount niet. Het gebruikersaccount wordt echter niet beïnvloed door het app-beveiligingsbeleid.

  * Voor de **OneDrive-app en Outlook-app** kunt u slechts één werkaccount gebruiken.  Het toevoegen van meerdere werkaccounts is op deze apps geblokkeerd.  U kunt een gebruiker echter van een apparaat verwijderen en vervolgens een andere gebruiker toevoegen aan het apparaat.


* Voordat het app-beveiligingsbeleid wordt geïmplementeerd, kan een apparaat meerdere bestaande gebruikersaccounts hebben. In dit geval wordt het eerste account waarop het app-beveiligingsbeleid wordt geïmplementeerd, beheerd door het app-beveiligingsbeleid van Intune.


Lees het volgende voorbeeldscenario voor meer informatie over hoe Intune omgaat met meerdere gebruikersaccounts.

Gebruiker A werkt voor twee bedrijven: **bedrijf X** en **bedrijf Y**. Gebruiker A heeft voor elk bedrijf een werkaccount en voor beide accounts wordt gebruikgemaakt van Intune om app-beveiligingsbeleid te implementeren. **Bedrijf X** implementeert app-beveiligingsbeleid **voordat** **bedrijf Y** dat doet. Het app-beveiligingsbeleid wordt toegepast op het account dat is gekoppeld aan **bedrijf X**, niet op het account dat is gekoppeld aan bedrijf Y. Als u wilt dat het gebruikersaccount van bedrijf Y door het app-beveiligingsbeleid wordt beheerd, moet gebruiker A het gebruikersaccount van bedrijf X verwijderen.
### <a name="adding-a-second-account"></a>Een tweede account toevoegen
####  <a name="android"></a>Android
U ziet mogelijk een prompt om het bestaande account te verwijderen en een nieuw account toe te voegen.  Als u het bestaande account wilt verwijderen, gaat u naar **Instellingen &gt;Algemeen &gt; Toepassingsbeheer &gt;Bedrijfsportal. Selecteer vervolgens "Gegevens wissen".**

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

|                                                                                 <strong>pfile</strong>                                                                                 |                                                                      <strong>tekst</strong>                                                                      |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Pfile is een algemene 'wrapper'-indeling voor beveiligde bestanden. Hiermee worden de versleutelde inhoud en de Azure Information Protection-licenties ingekapseld. Deze indeling kan worden gebruikt voor het beveiligen van elk bestandstype. | Tekstbestanden, zoals XML, CSV enzovoort, kunnen worden geopend voor weergave in de app, zelfs wanneer ze zijn beveiligd. Bestandstypen: txt, ptxt, csv, pcsv, log, plog, xml, pxml. |

---------------
## <a name="next-steps"></a>Volgende stappen
[Wat u kunt verwachten wanneer uw iOS-app wordt beheerd door een app-beveiligingsbeleid](app-protection-enabled-apps-ios.md)

### <a name="see-also"></a>Zie tevens
[App-beveiligingsbeleid maken en implementeren met Microsoft Intune](app-protection-policies.md)
