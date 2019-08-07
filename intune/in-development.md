---
title: In ontwikkeling - Microsoft Intune
titleSuffix: ''
description: Microsoft Intune-functies in ontwikkeling
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 969e7bc4804e1f66230c76d742bec2c67c2fa006
ms.sourcegitcommit: 99b74d7849fbfc8f5cf99cba33e858eeb9f537aa
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/31/2019
ms.locfileid: "68670922"
---
# <a name="in-development-for-microsoft-intune---august-2019"></a>In ontwikkeling voor Microsoft Intune - augustus 2019

Als ondersteuning bij uw gereedheid en planning worden op deze pagina updates voor en functies van de Intune-gebruikersinterface vermeld die in ontwikkeling zijn, maar nog niet zijn uitgebracht. Daarnaast:

- Als we verwachten dat u actie moet ondernemen vóór een wijziging, publiceren we een aanvullend bericht in het Office-berichtencentrum.
- Als er een functie wordt uitgebracht in productie, ofwel als preview ofwel als algemeen beschikbare functie, wordt de functiebeschrijving verplaatst van deze pagina naar de [pagina Nieuwe functies](whats-new.md).
- Deze pagina en de pagina [Nieuwe functies](whats-new.md) worden regelmatig bijgewerkt. Controleer op andere updates.
- Raadpleeg de [M365-roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) voor strategische producten en tijdlijnen.

> [!Note]
> Deze items representeren de huidige verwachtingen van Microsoft over Intune-mogelijkheden in een toekomstige release. Datums en afzonderlijke functies kunnen worden gewijzigd. Niet alle items in ontwikkeling hebben een functieomschrijving op deze pagina.

**RSS feed**: ontvang een melding wanneer deze pagina wordt bijgewerkt door de volgende URL in uw feedlezer te kopiëren en plakken: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->

<!-- Common categories:  
#### App management
#### Device configuration
#### Device enrollment
#### Device management
#### Intune apps
#### Monitor and troubleshoot
#### Role-based access control
#### Security

-->
 
<!-- ***********************************************-->
## <a name="app-management"></a>Appbeheer

### <a name="control-ios-app-uninstall-behavior-at-device-unenrollment----3504144---"></a>Gedrag van het verwijderen van iOS-apps bij het uitschrijven van apparaten beheren <!-- 3504144 -->
Beheerders kunnen beheren of een app wordt verwijderd of op een apparaat wordt bewaard wanneer het apparaat niet is inge schreven op het niveau van een gebruiker of apparaat. 

### <a name="categorize-microsoft-store-for-business-apps----3926922---"></a>Microsoft Store voor Bedrijven-apps categoriseren <!-- 3926922 -->
U kunt Microsoft Store voor zakelijke apps categoriseren. Als u dit wilt doen ****  > , kiest u intune-**apps** voor**client-apps** > > Selecteer een Microsoft Store voor zakelijke app >**categorie**met **app-gegevens** > . Wijs een categorie toe aan de vervolg keuzelijst.
### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Inhoud van app-meldingen voor organisatie accounts configureren <!-- 2576686 -->
Met intune app-beveiligings beleid (APP) op Android-en iOS-apparaten kunt u inhoud voor app-meldingen beheren voor organisatie accounts. Deze functie vereist ondersteuning van toepassingen en is mogelijk niet beschikbaar voor alle toepassingen die zijn ingeschakeld voor apps. Zie [Wat is beveiligingsbeleid voor apps?](app-protection-policy.md) voor meer informatie over APP.

### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956----"></a>Beschikbare rapportage over Google Play-apps voor Android-werkprofielen <!-- 3041956  -->
U kunt voor beschikbare app-installaties op apparaten met Android-werkprofielen de status van de app-installatie en de geïnstalleerde versie van beheerde Google Play-apps bekijken. Zie [How to monitor app protection policies](app-protection-policies-monitor.md) (App-beveiligingsbeleid controleren), [Manage Android work profile devices with Intune](android-enterprise-overview.md) (Apparaten met Android-werkprofielen beheren met Intune) en [Managed Google Play app type](apps-add-android-for-work.md#managed-google-play-app-type) (Type beheerde Google Play-app) voor meer informatie.

<!-- ***********************************************-->
## <a name="device-configuration"></a>Apparaatconfiguratie

### <a name="some-unsupervised-ios-device-restrictions-will-become-supervised-only-with-the-ios-130-release----4867809----"></a>Sommige beperkingen van het iOS-apparaat zonder super visie worden alleen gecontroleerd met de iOS 13,0-release <!-- 4867809  -->
Sommige instellingen zijn alleen van toepassing op apparaten met Super visie met de iOS 13,0-release. Deze instellingen omvatten:

- App Store, documenten bekijken, gamen
  - App Store
  - Expliciete iTunes-, muziek-, podcast-of nieuws inhoud
  - Game Center-vrienden toevoegen
  - Games voor meerdere spelers
- Ingebouwde apps
  - Camera
    - FaceTime
  - Safari
    - Automatisch doorvoeren
- Cloud en opslag
  - Back-up naar iCloud
  - ICloud-document synchronisatie blok keren
  - Synchronisatie van iCloud-sleutelhanger blokkeren

Als deze instellingen zijn geconfigureerd en toegewezen aan apparaten zonder super visie vóór de iOS 13,0-release, worden de instellingen nog steeds toegepast op deze apparaten zonder super visie. Ze zijn ook nog steeds van toepassing nadat de apparaten zijn bijgewerkt naar iOS 13,0. Deze beperkingen worden verwijderd op apparaten zonder toezicht waarvan een back-up is gemaakt en die worden hersteld. 

Als u de huidige instellingen wilt zien, gaat u naar [iOS-apparaatinstellingen voor het toestaan of beperken van functies met Intune](device-restrictions-ios.md).

Van toepassing op:  
- iOS 13,0 en hoger

### <a name="new-settings-and-changes-to-existing-settings-to-restrict-features-on-ios-and-macos-devices----4867699-4867709----"></a>Nieuwe instellingen en wijzigingen in bestaande instellingen om functies op iOS-en macOS-apparaten te beperken <!-- 4867699 4867709  -->
U kunt profielen maken om instellingen te beperken op apparaten met IOS en MacOS (**apparaatconfiguratie** > **profielen** > **profiel** > maken**IOS** of **MacOS** voor platform Typ > **beperkingen**van het apparaat). De volgende functies worden toegevoegd:

- Gebruik voor de**beperkingen** **** ****  >  > van het MacOS-apparaat**Cloud en Storage**de nieuwe instelling besteld om te voor komen dat gebruikers vanaf een MacOS-apparaat aan de slag gaan en op een ander MacOS-of IOS-apparaat werken.
  Als u de huidige instellingen wilt zien, gaat u naar [macOS-apparaatinstellingen voor het toestaan of beperken van functies met Intune](device-restrictions-macos.md).
- Op het **IOS** > -**apparaat gelden**enkele wijzigingen:
  - **Ingebouwde apps** > **zoeken mijn iPhone (alleen onder Super visie)** : nieuwe instelling die deze functie blokkeert in de functie mijn app zoeken. 
  - **Ingebouwde apps** > **zoeken naar mijn vrienden (alleen onder Super visie)** : nieuwe instelling die deze functie blokkeert in de functie mijn app zoeken. 
  - **** Draadloze > **wijziging van de Wi-Fi-status (alleen onder Super visie)** : nieuwe instelling die voor komt dat gebruikers Wi-Fi op het apparaat in-of uitschakelen.
  - **Toetsen bord en woorden lijst** > **QuickPath (alleen onder Super visie)** : nieuwe instelling die de QuickPath-functie blokkeert.
  - **Cloud en opslag**: de voortzetting van de **activiteiten** wordt gewijzigd **** in de bewaarde.

  Als u de huidige instellingen wilt zien, gaat u naar [iOS-apparaatinstellingen voor het toestaan of beperken van functies met Intune](device-restrictions-ios.md).

Van toepassing op:  
- macOS 10,15 en hoger
- iOS 13 en hoger

### <a name="control-the-apps-files-documents-and-folders-that-open-when-user-signs-in-to-macos-devices---3914202----"></a>De apps, bestanden, documenten en mappen beheren die worden geopend wanneer de gebruiker zich aanmeldt bij macOS-apparaten <!--3914202  -->
U kunt functies inschakelen en configureren op macOS-apparaten (**apparaatconfiguratie** > **profielen** >  **** **profiel** > maken voor het platform > **apparaat-functies** voor Profiel type). 

Er zijn nieuwe instellingen voor aanmeldings items om te bepalen welke apps, bestanden, documenten en mappen worden geopend wanneer een gebruiker zich aanmeldt bij het geregistreerde apparaat. 

Ga naar [Instellingen van apparaatfuncties voor macOS in Intune](macos-device-features-settings.md) om de huidige instellingen te zien.

Van toepassing op:  
- macOS

### <a name="new-features-for-android-enterprise-dedicated-devices-in-multi-app-mode----3755304-3041943-3041946----"></a>Nieuwe functies voor speciaal voor Android-apparaten in de modus voor meerdere apps <!-- 3755304 3041943 3041946  -->
U kunt de functies en instellingen in een kiosk stijl beheren op uw door Android Enter prise toegewezen apparaten. Als u dit wilt doen, kiest u **configuratie** > **profielen** > voor apparaten**profiel** > maken**Android Enter prise** voor platform > **alleen apparaat-eigenaar, beperkingen** voor het profiel type.

De volgende functies worden toegevoegd:
- **Gereserveerde apparaten** > **multi-app**: de knop voor de **virtuele start** kan worden weer gegeven door op het apparaat te vegen of op het scherm te zweven zodat gebruikers het kunnen verplaatsen.
- **Toegewezen apparaten** > **multi-app**: met **zaklantaarn toegang** kunnen gebruikers de zaklantaarn gebruiken. 
- **Toegewezen apparaten** > **multi-app**: met **volume regeling van media** kunnen gebruikers het Media volume van het apparaat beheren met behulp van een schuif regelaar. 
- **Toegewezen apparaten** > **multi-app**: Schakel scherm beveiliging in, upload een aangepaste installatie kopie en bepaal wanneer de scherm beveiliging wordt weer gegeven.

Ga naar [Android Enterprise-apparaatinstellingen om beperkingsfuncties toe te staan of te beperken met behulp van Intune](device-restrictions-android-for-work.md#dedicated-device-settings) om de huidige instellingen te zien.

Van toepassing op:  
- Toegewezen Android Enterprise-apparaten

### <a name="new-app-and-configuration-profiles-for-android-enterprise-fully-managed-devices----3574215----"></a>Nieuwe app-en configuratie profielen voor volledig beheerde Android Enter prise-apparaten <!-- 3574215  -->
Met behulp van profielen kunt u instellingen configureren waarmee VPN-, e-mail-en Wi-Fi-instellingen worden toegepast op uw volledig beheerde Android-apparaten. U kunt het volgende doen:
- Gebruik app-profielen voor het implementeren van Outlook-, Gmail-en negen werk-e-mail instellingen.
- Gebruik apparaatconfiguratie-profielen om instellingen voor het vertrouwde basis certificaat te implementeren.
- Gebruik apparaatconfiguratie-profielen voor het implementeren van VPN-en Wi-Fi-instellingen.

Gebruikers verifiëren zich met hun gebruikers naam en wacht woord voor VPN-, Wi-Fi-en e-mail profielen. Op dit moment is verificatie op basis van certificaten niet beschikbaar. 

Van toepassing op:  
- Volledig beheerde Android Enterprise-apparaten

### <a name="support-for-ikev2-vpn-profiles-for-ios----1943438---"></a>Ondersteuning voor IKEv2 VPN-profielen voor iOS <!-- 1943438 -->
U kunt met het IKEv2-protocol VPN-profielen voor de systeemeigen VPN-client van iOS maken. IKEv2 is een nieuw verbindingstype in **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **VPN** voor profieltype > **Instellingen**.

Met deze VPN-profielen wordt de systeemeigen VPN-client geconfigureerd. Er worden dus geen VPN-client-apps geïnstalleerd of naar beheerde apparaten gepusht. Deze functie vereist dat apparaten zijn ingeschreven bij Intune (MDM-inschrijving).

Als u wilt zien welke VPN-instellingen u momenteel kunt configureren, gaat u naar [Configure VPN settings on iOS devices in Microsoft Intune](vpn-settings-ios.md) (VPN-instellingen configureren op iOS-apparaten in Microsoft Intune).

Van toepassing op: iOS

<!-- ***********************************************-->
## <a name="device-enrollment"></a>Apparaatinschrijving

### <a name="skip-more-screens-in-setup-assistant---4877451---"></a>Meer schermen in de Configuratieassistent overs Laan <!--4877451 -->
U kunt Device Enrollment Program profielen instellen om de volgende schermen van de Configuratieassistent over te slaan: 
- Schermtijd
- Touch ID instellen

Als u dit wilt doen, gaat u naar **Device Enrollment** > **Apple inschrijving** > **Program tokens** > kiest u een token > **profielen** > Kies een profiel > **Eigenschappen** > **bewerken** naast de **aanpassing**van de Configuratieassistent.
Zie [een Apple-inschrijvings profiel maken ](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile)voor meer informatie over het aanpassen van de Configuratieassistent.

### <a name="android-enrollment-device-administrator-support----4869749----"></a>Ondersteuning voor Android-registratie apparaat beheerder <!-- 4869749  -->
De optie registratie voor Android-apparaten beheerder wordt toegevoegd aan de registratie pagina van ****  > Android (intune-inschrijving voor**Android**-**apparaten** > ). Android-Apparaatbeheer wordt standaard ingeschakeld voor alle tenants.  

### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal----4394993----"></a>Voor iOS-apparaten past u het scherm voor inschrijvings proces van de Bedrijfsportal aan <!-- 4394993  -->
Met prijs verlaging kunt u het privacy-scherm van de Bedrijfsportal aanpassen dat eind gebruikers te zien krijgen tijdens de iOS-registratie. U kunt met name de lijst met dingen aanpassen die uw organisatie niet kan zien of op het apparaat kan doen.

<!-- ***********************************************-->
## <a name="device-management"></a>Apparaatbeheer

### <a name="build-number-included-on-android-device-hardware-page----4461910----"></a>Buildnummer opgenomen op de pagina hardware van Android-apparaat <!-- 4461910  -->
Een nieuw item op de pagina hardware voor elk Android-apparaat bevat het buildnummer van het besturings systeem van het apparaat.

### <a name="configure-automatic-device-clean-up-time-limit-down-to-30-days---4231059----"></a>De tijds limiet voor het automatisch opschonen van apparaten configureren tot 30 dagen <!--4231059  -->
U kunt de tijds limiet voor automatische opschoning van apparaten instellen op 30 dagen (in plaats van de huidige limiet van 90 dagen) na de laatste aanmelding. Als u dit wilt doen, gaat u naar **intune** > **apparaten** > regels voor het opschonen**van**apparaten**instellen** > .

<!-- ***********************************************-->
## <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer

### <a name="default-scope-tag----3702875---"></a>Label voor standaard bereik <!-- 3702875 -->
Er is een nieuwe ingebouwde standaard bereik markering beschikbaar. Alle niet-gelabelde intune-objecten die bereik Tags ondersteunen, worden automatisch toegewezen aan de standaard bereik label. De **standaard** label voor het bereik wordt toegevoegd aan alle bestaande roltoewijzingen om pariteit met de beheerders ervaring te behouden. Als u niet wilt dat een beheerder intune-objecten met standaard bereik Tags ziet, verwijdert u de standaard bereik markering uit de roltoewijzing. Deze functie is vergelijkbaar met de functie beveiligingsbereiken in System Center Configuration Manager.

<!-- ***********************************************-->
## <a name="security"></a>Beveiliging

### <a name="import-and-export-security-baselines------3408610------------"></a>Beveiligings basislijnen importeren en exporteren    <!--3408610          -->  
We voegen de mogelijkheid toe om beveiligings basislijnen te exporteren en te importeren. Met deze functie kunt u uw aanpassingen door nemen en delen tussen de intune-omgevingen.

<!-- ***********************************************-->
## <a name="notices"></a>Mededelingen

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

## <a name="see-also"></a>Zie tevens
Zie [Wat is er nieuw in Microsoft Intune?](whats-new.md) voor meer informatie over recente ontwikkelingen.




