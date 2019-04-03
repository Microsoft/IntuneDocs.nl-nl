---
title: In ontwikkeling - Microsoft Intune
titlesuffix: ''
description: Microsoft Intune-functies in ontwikkeling
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/29/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3e068e2c9834290b705e8e7bc2f895636415f9ba
ms.sourcegitcommit: 69aaf89140f82f344404e75a69dc59d8a1585b10
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/30/2019
ms.locfileid: "58675439"
---
# <a name="in-development-for-microsoft-intune---april-2019"></a>In de ontwikkeling voor Microsoft Intune - April 2019

Om te helpen bij uw gereedheid en planning, deze pagina is een lijst met Intune UI-updates en functies die zijn in ontwikkeling, maar nog niet is vrijgegeven. Daarnaast:

- Als we verwachten, moet u maatregelen nemen voordat u een wijziging, publiceren we een gratis Office Message Center-bericht.
- Als een functie als een Preview-versie in productie, wordt gestart of algemeen beschikbaar is, de beschrijving van de functie worden verplaatst uit deze pagina en naar de [wat is er nieuw-pagina](whats-new.md).
- Deze pagina en de [wat is er nieuw-pagina](whats-new.md) worden regelmatig bijgewerkt. Controleer op andere updates.
- Raadpleeg de [M365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) voor strategische producten en tijdlijnen.

> [!Note]
> Deze items zijn de huidige verwachtingen van Microsoft over de mogelijkheden van Intune die afkomstig zijn in een toekomstige release. Datums en functies afzonderlijk kunnen worden gewijzigd. Niet alle items in de ontwikkeling hebben een omschrijving op deze pagina.

**RSS feed**: ontvang een melding wanneer deze pagina wordt bijgewerkt door de volgende URL in uw feedlezer te kopiëren en plakken: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune in Azure Portal

<!-- 1904 start-->

### <a name="set-login-settings-and-control-restart-options-on-macos-devices----1210083---"></a>Aanmelding configureren en beheren van opties voor opnieuw opstarten op macOS-apparaten <!-- 1210083 -->
Op macOS-apparaten, kunt u een apparaatconfiguratieprofiel maken (**apparaatconfiguratie** > **profielen** > **-profiel maken** > Kies **macOS** voor platform > **apparaatfuncties** voor profieltype). Nieuwe aanmelding vensterinstellingen omvat items zoals het weergeven van een aangepaste banner, kiest u hoe gebruikers zich aanmelden, weergeven of verbergen van de energie-instellingen en meer.

Als u wilt zien van de huidige instellingen, gaat u naar [instellingen van apparaatfuncties voor macOS](macos-device-features-settings.md).

Is van toepassing op: macOS

### <a name="advanced-settings-for-windows-defender-firewall----1311949---"></a>Geavanceerde instellingen voor Windows Defender Firewall <!-- 1311949 -->
U binnenkort mogelijk om Intune te gebruiken voor het beheren van de aangepaste firewallregels op clients voor Windows Defender. Regels kunnen inkomende en uitgaande gedrag voor toepassingen, netwerkadressen en poorten opgeven. 

### <a name="require-app-protection-conditional-access----1634317---"></a>Voorwaardelijke toegang voor App-beveiliging is vereist  <!--1634317 -->
U zult gebruiken *vereisen App-beveiligingsbeleid*, waarmee wordt bevestigd beleid wordt toegepast op van een gebruiker app voordat de aanmelding is voltooid om te voorkomen dat gebruikers toegang krijgen tot gegevens die u beveiligt met voorwaardelijke toegang. Terwijl beleid assurance de eerste gebruikerservaring van vertragen, wordt het helpt te beschermen tegen netwerkproblemen, administratieve onjuiste configuraties of opzettelijk inspanningen voor het beveiligingsbeleid voor toepassingen weren. 

### <a name="deployment-of-online-licensed-microsoft-store-for-business-apps----16726660---"></a>Implementatie van online gelicentieerde Microsoft Store voor Bedrijven-apps <!-- 16726660 -->
U kunt vereiste online gelicentieerde Microsoft Store voor Bedrijven-apps in de apparaatcontext toewijzen. Wanneer u op deze manier een Microsoft Store voor bedrijven-app implementeert, kan de app worden geïnstalleerd voor alle gebruikers op het apparaat. Dit is alleen van toepassing op Windows 10 RS4+ Desktop-apparaten. De optie om de app in de apparaatcontext te installeren, is beschikbaar op de toewijzingspagina voor client-apps voor gelicentieerde MSFB Online-apps.

### <a name="include-and-exclude-mixture-of-user-groups-and-device-groups-when-assigning-policies-and-profiles----1807547---"></a>Opnemen en uitsluiten van de combinatie van gebruikersgroepen en apparaatgroepen bij het toewijzen van beleidsregels en profielen <!-- 1807547 -->
Bij het toewijzen van beleidsregels voor naleving of configuratieprofielen, kunt u ze toewijzen aan beveiligingsgroepen met gebruikers of apparaten. U kunt op dit moment opnemen en uitsluiten alleen gebruikersgroepen *of* opnemen en uitsluiten alleen groepen apparaten. U kan opnemen en uitsluiten van een combinatie van groepen, bevatten, zoals gebruikersgroepen *en* uitsluiten van een groep apparaten.

U zult kunnen opnemen en uitsluiten van een combinatie van gebruikersgroepen en apparaatgroepen. U kunt een groep gebruikers opnemen en uitsluiten van een groep apparaten. U kunt bijvoorbeeld toewijzen of implementeren van een apparaatconfiguratieprofiel voor een groep gebruikers, maar uitsluiten van persoonlijke apparaten.

[Profielen voor apparaatconfiguratie toewijzen](device-profile-assign.md) bevat meer informatie over het toewijzen van profielen aan gebruikersgroepen en apparaatgroepen.

Is van toepassing op: alle platforms

### <a name="retire-noncompliant-devices----1827291---"></a>Niet-compatibele apparaten buiten gebruik stellen <!-- 1827291 -->
We gaan om toe te voegen een nieuwe nalevingsactie om een niet-compatibel apparaat buiten gebruik stellen. Buiten gebruik stellen van een niet-compatibel apparaat, worden alle bedrijfsgegevens verwijderd uit het en verwijdert u ook het apparaat wordt beheerd door Intune. Deze actie wordt uitgevoerd wanneer de geconfigureerde waarde in dagen is bereikt. De minimumwaarde is 30 dagen. 

### <a name="configure-settings-for-kernel-extensions-on-macos-devices----2043024---"></a>Instellingen voor kernel-extensies op macOS-apparaten configureren <!-- 2043024 -->
Op macOS-apparaten, kunt u een apparaatconfiguratieprofiel maken (**apparaatconfiguratie** > **profielen** > **-profiel maken** > Kies **macOS** voor platform). Een nieuwe groep instellingen kunt u configureren en gebruiken van kernel-uitbreidingen op uw apparaten.

Van toepassing op: macOS 10.13.2 en hoger

### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470---"></a>Profiel configureren om bepaalde vensters over te slaan tijdens het doorlopen van de configuratieassistent <!-- 2276470 -->
Wanneer u een macOS-registratieprofiel maakt, kunt u binnenkort instellen dat de configuratieassistent de volgende schermen overslaat:
- Migratie vanaf Android
- Weergavekleur
- Privacy
- iCloudStorage Als u een nieuw profiel maakt of een profiel bewerkt, moeten de geselecteerde skip-schermen worden gesynchroniseerd met de Apple MDM-server. Gebruikers kunnen de opdracht tot een handmatige synchronisatie van de apparaten geven, zodat er geen vertraging in het ophalen van de profielwijzigingen is.
Raadpleeg [MacOS-apparaten automatisch inschrijven met het Device Enrollment Program of Apple School Manager](device-enrollment-program-enroll-macos.md) voor meer informatie.

### <a name="device-users-can-view-all-managed-apps-theyve-installed-or-tried-to-install----2352913---"></a>Gebruikers van apparaten kunnen weergeven alle beheerde apps ze hebt geïnstalleerd of is geprobeerd te installeren <!-- 2352913 -->
Bedrijf Portal voor Windows wordt een lijst alle beheerde apps&ndash; zowel vereiste als beschikbare&ndash; die op het apparaat van een gebruiker worden geïnstalleerd. Gebruikers kunnen naar de weergave heeft geprobeerd en in afwachting van app-installaties en de huidige status worden. Als uw organisatie maakt geen apps vereist of beschikbaar zijn, wordt een bericht waarin wordt uitgelegd dat er geen bedrijfs-apps zijn geïnstalleerd door gebruikers zien. Gebruikers kunnen ook sorteren of hun apps filteren op status van de installatie.

### <a name="scope-tags-for-apple-vpp-tokens---2371886---"></a>Bereiktags voor Apple VPP-tokens <!--2371886 -->
U zult kunnen bereiktags toevoegen aan Apple VPP-tokens. Alleen gebruikers die zijn toegewezen met dezelfde bereiktag hebben toegang tot de Apple VPP-token met dit label. Overgenomen door de bereiktags VPP-apps en e-Books gekocht met dit token. Zie voor meer informatie over bereiktags [gebruik RBAC en scope-tags](scope-tags.md).

### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>Gebruik "regels voor toepasselijkheid" wanneer het maken van Windows 10-apparaat-configuratieprofielen <!-- 2549910 -->
U Windows 10-apparaat-configuratieprofielen maken (**apparaatconfiguratie** > **profielen** > **-profiel maken**  >  **Windows 10** voor platform). U moet mogelijk maken een **toepassingsregel** , zodat het profiel is alleen van toepassing op een specifieke editie of een specifieke versie. U maakt bijvoorbeeld een profiel waarmee bepaalde BitLocker-instellingen. Als u het profiel toevoegt, gebruikt u een toepassingsregel, zodat het profiel is alleen van toepassing op apparaten met Windows 10 Enterprise.

Van toepassing op: 
- Windows 10 en hoger

### <a name="enable-win32-app-dependencies----2617348---"></a>Win32-app-afhankelijkheden inschakelen <!-- 2617348 -->
Openbare preview - als de beheerder, u hebt mogelijk om te vereisen dat andere apps als afhankelijkheden zijn geïnstalleerd voordat u de Win32-app installeert. Het apparaat moet met name de afhankelijke App (s) installeren voordat deze de Win32-app wordt geïnstalleerd. Deze functionaliteit is beschikbaar nadat de Intune-beheer-agent is bijgewerkt naar 1904 versie (groter dan 1.18.120.0) die 1 of 2 weken extra nadat we de service naar 1904 upgraden kan duren. Selecteer in Intune, **Client-apps** > **Apps** > **toevoegen** om weer te geven de **app toevoegen** blade. Selecteer **Windows-app (Win32)** als de **App-type**. Zie voor meer informatie, [Intune Standalone - Win32-app-beheer](apps-win32-app-management.md).

### <a name="new-device-restriction-setting-for-android-enterprise-device-owner-let-users-connect-to-wi-fi-networks-on-android-enterprise-dedicated-devices-running-multi-app-kiosk-mode---3041940---"></a>Nieuwe apparaat beperkingsinstelling voor Android Enterprise, de eigenaar van apparaat: toestaan dat gebruikers verbinding maken met Wi-Fi-netwerken op Android Enterprise toegewezen apparaten kioskmodus voor meerdere Apps <!--3041940 -->
Beheerders zich om uit te schakelen van een nieuwe instelling waarmee gebruikers kunnen het configureren van Bluetooth op hun Android Enterprise toegewezen apparaten met meerdere Apps kioskmodus bevindt. Kies een overzicht van deze instelling in de Intune-console **Intune** > **apparaatconfiguratie** > **profielen**  >  **-Profiel maken** > Kies **Android Enterprise** voor platform > **alleen de eigenaar van apparaat, apparaatbeperkingen** voor profieltype > **instellingen**   >  **Toegewezen apparaten** > Selecteer **meerdere Apps** uit de **kioskmodus** instelling vervolgkeuzelijst. Een optie met de naam **Wi-Fi-configuratie** beschikbaar om in te schakelen. 

Is van toepassing op: Android Enterprise toegewezen apparaten met meerdere Apps kioskmodus bevindt. 

### <a name="new-device-restriction-setting-for-android-enterprise-device-owner-let-users-configure-bluetooth-and-pairing-on-android-enterprise-dedicated-devices---3041941---"></a>Nieuwe apparaat beperkingsinstelling voor Android Enterprise, de eigenaar van apparaat: toestaan dat gebruikers te nemen op apparaten met Android Enterprise die zijn toegewezen en een Bluetooth-configureren <!--3041941 -->
Beheerders zich om uit te schakelen van een nieuwe instelling waarmee gebruikers kunnen het configureren van Bluetooth op hun Android Enterprise toegewezen apparaten met meerdere Apps kioskmodus bevindt. Kies een overzicht van deze instelling in de Intune-console **Intune** > **apparaatconfiguratie** > **profielen**  >  **-Profiel maken** > Kies **Android Enterprise** voor platform > **alleen de eigenaar van apparaat, apparaatbeperkingen** voor profieltype > **instellingen**   >  **Toegewezen apparaten** > Selecteer **meerdere Apps** uit de **kioskmodus** instelling vervolgkeuzelijst. Een optie met de naam **Bluetooth-configuratie** beschikbaar om in te schakelen. 

Is van toepassing op: Android Enterprise toegewezen apparaten met meerdere Apps kioskmodus bevindt. 

### <a name="monitor-security-baseline-status-public-preview----3082047---"></a>Controleren voor basisbeveiliging (openbare preview) <!-- 3082047 --> 
Wanneer u bewaken de *Apparaatstatus* voor uw basisbeveiliging de weergave organiseert de status van de basislijn-categorieën, zoals *vergrendeling*, *BitLocker*, en  *Browser*. Alle beschikbare basislijn categorieën worden weergegeven. Voor elke categorie ziet u hoeveel apparaten komen niet overeen met een specifieke basislijn-categorie, zijn onjuist geconfigureerd of zijn niet van toepassing.

###  <a name="intune-security-tasks-for-defender-atp-in-public-preview----3208597---"></a>Intune beveiligingstaken voor Defender ATP (In openbare preview-versie) <!-- 3208597 -->
Binnenkort als openbare preview, wordt Intune binnenkort toegevoegd beveiligingstaken voor de nieuw aangekondigde Microsoft Defender Threat & beveiligingsproblemen.  Met deze integratie kunt kunnen bewerkingen Beveiligingsbeheerders in Windows Defender ATP (WDATP) de aanbevolen herstelbewerkingen voor opkomende bedreigingen voor de Intune-beheerders effectiever communiceren. Het toevoegen van taken die wordt toegevoegd een benadering op basis van risico's voor het detecteren, prioriteren en beveiligingsproblemen van het eindpunt en onjuiste configuraties herstellen.

Voor meer informatie over taken die in Intune, Zie het blogbericht over [Intune beveiligingstaken gebruiken voor het uitbreiden van de bedreiging en beveiligingsproblemen Microsoft Defender ATP](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/Microsoft-Intune-security-tasks-extend-Microsoft-Defender-ATP-s/ba-p/369857). 

### <a name="create-and-use-oemconfig-device-configuration-profiles-in-intune----3305883---"></a>Maken en gebruiken van OEMConfig apparaatconfiguratieprofielen in Intune <!-- 3305883 -->
Intune biedt ondersteuning voor configureren van Android Enterprise-apparaten met OEMConfig. Specifiek, u kunt een apparaatconfiguratieprofiel maken, en instellingen van toepassing op Android Enterprise-apparaten met behulp van OEMConfig (**apparaatconfiguratie** > **profielen**  >  **-Profiel maken** > **Android enterprise** voor platform).

Ondersteuning voor OEM's is momenteel op basis van de per-OEM. Als een OEMConfig app die u wilt niet beschikbaar is in de lijst met apps OEMConfig, neem dan contact op met `IntuneOEMConfig@microsoft.com`.

Van toepassing op: 
- Android Enterprise

### <a name="new-device-restriction-settings-for-android-enterprise-device-owner----3574254---"></a>Nieuwe apparaatbeperkingsinstellingen voor Android Enterprise, de eigenaar van apparaat <!-- 3574254 -->
Op apparaten met Android Enterprise, kunt u een profiel voor apparaatbeperking als u wilt toestaan of beperken van functies en regels voor wachtwoorden instellen (**apparaatconfiguratie** > **profielen**  >  **-Profiel maken** > Kies **Android Enterprise** voor platform > **alleen de eigenaar van apparaat > apparaatbeperkingen** voor profieltype). 

Nieuwe instellingen, zoals wachtwoordinstellingen, waardoor volledige toegang tot toepassingen in de Google Play Store voor volledig beheerde apparaten en meer beschikbaar. 

Ga naar [Met Android Enterprise-apparaatinstellingen functies toestaan of beperken](device-restrictions-android-for-work.md) voor de huidige lijst met instellingen. 

Is van toepassing op: Android Enterprise volledig beheerde apparaten

### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---"></a>Controleer voor een TPM-chipset in een nalevingsbeleid voor Windows 10-apparaten <!-- 3617671 -->
Groot aantal Windows 10 en hoger apparaten hebben chipsets Trusted Platform Module (TPM). Een nieuwe nalevingsinstelling wordt gecontroleerd of een TPM op het apparaat.

[Windows 10 en hoger instellingen voor nalevingsbeleid](compliance-policy-create-windows.md#windows-10-and-later-policy-settings) geeft een lijst van de huidige instellingen.

Van toepassing op: 
- Windows 10 en hoger

### <a name="configure-your-win32-apps-to-be-installed-on-intune-enrolled-azure-ad-joined-devices----3695227---"></a>Configureren van uw Win32-apps worden geïnstalleerd op ingeschreven bij Intune Azure AD gekoppelde apparaten <!-- 3695227 -->
U zult kunnen toewijzen die uw Win32-apps worden geïnstalleerd op Intune Azure AD ingeschreven gekoppelde apparaten. Zie voor meer informatie over Win32-apps in Intune, [Win32-app-beheer](apps-win32-app-management.md).

### <a name="windows-defender-advanced-threat-protection-baseline----3754134---"></a>Windows Defender Advanced Threat Protection-basislijn <!-- 3754134 -->
We gaan om toe te voegen nieuwe basislijn om te helpen u bij het configureren van instellingen voor Windows Defender Advanced Threat Protection.

### <a name="device-overview-shows-primary-user---794259---"></a>Overzicht van apparaat bevat primaire gebruiker <!--794259 -->
De overzichtspagina van het apparaat ziet u de primaire gebruiker, ook wel de gebruiker apparaten affiniteit gebruiker (UDA). Als u wilt zien dat de primaire gebruiker voor een apparaat, kies **Intune** > **apparaten** > **alle apparaten** > Kies een apparaat. De primaire gebruiker wordt weergegeven aan de bovenkant van de **overzicht** pagina.

### <a name="expanded-support-for-android-enterprise-fully-managed-devices----3903241-3903244-3903246---"></a>Uitgebreide ondersteuning voor Android Enterprise volledig beheerde apparaten <!-- 3903241, 3903244, 3903246 -->
We gaan om uit te breiden de ondersteuning van Android Enterprise volledig beheerde apparaten ([eerst aangekondigd in januari van 2019](whats-new.md#week-of-january-14-2019) het volgende opnemen:
- Naleving
- Voorwaardelijke toegang
- Nieuwe eindgebruiker App

Ga naar **Apparaatinschrijving** > **Android-inschrijving** > **Bedrijfseigendom, volledig beheerde gebruikersapparaten** om volledige beheerde Android-apparaten in te stellen. Ondersteuning voor volledig beheerde Android-apparaten blijft in preview en bepaalde Intune-functies mogelijk niet volledig functioneel. 

### <a name="additional-managed-google-play-app-reporting-for-android-enterprise-work-profile-devices----4105925---"></a>Aanvullende beheerde Google Play app-rapportage voor apparaten met Android Enterprise-werkprofiel <!-- 4105925 -->
Voor beheerde Google Play-apps op apparaten met Android Enterprise-werkprofiel hebt geïmplementeerd, is het mogelijk zijn om het specifieke versienummer van de app is geïnstalleerd op een apparaat weer te geven. Dit geldt voor alleen vereiste apps. Dezelfde functionaliteit voor beschikbare apps wordt ingeschakeld in een toekomstige release.

### <a name="ios-third-party-keyboards----4111843---"></a>iOS-toetsenborden van derden <!-- 4111843 -->
Ondersteuning voor de Intune app-beveiligingsbeleid (APP) voor de **van derden toetsenborden** instelling wordt beëindigd vanwege een wijziging in de iOS-platform. Kunt u zich niet met deze instelling configureren in de Intune-beheerconsole en wordt niet afgedwongen op de client in de Intune App SDK.

<!-- 1903 start-->

### <a name="block-users-from-scanning-for-windows-updates----3316758---"></a>Blokkeren dat gebruikers kunnen het zoeken naar updates voor Windows <!-- 3316758 -->
We voegen een nieuwe Windows update-ring instelling die u gebruiken kunt om te blokkeren dat gebruikers kunnen scannen op Windows-updates toe. Deze instelling niet beschikbaar zijn vanuit de portal, maar kan worden geconfigureerd met behulp van de Intune Graph API.

### <a name="windows-update-notifications----3316782---"></a>Windows Update-meldingen <!-- 3316782 -->
We er ondersteuning toegevoegd voor de Windows Update-ring-configuraties, zodat u kunt het configureren van de Windows Update-meldingen die uw gebruikers te zien. Deze instelling niet beschikbaar zijn vanuit de portal, maar kan worden geconfigureerd met behulp van de Intune Graph API.

### <a name="changes-to-company-portal-enrollment-for-ios-12-device-users---3448635---"></a>Wijzigingen in de bedrijfsportal-App-registratie voor gebruikers van iOS-12-apparaten <!--3448635 --> 
Bedrijfsportal-App voor iOS wordt de app-schermen voor inschrijving en de stappen om uit te lijnen met de MDM-inschrijving wijzigingen die zijn uitgebracht in Apple iOS 12.2 worden bijgewerkt. De bijgewerkte werkstroom wordt nu gevraagd voor gebruikers:

- Safari op de website bedrijfsportal (via Safari) openen en downloaden van het beheerprofiel voordat u terugkeert naar de bedrijfsportal-app toestaan.
- Open de app instellingen voor het installeren van het beheerprofiel op hun apparaat.
- Ga terug naar de bedrijfsportal-app-registratie moet voltooien.

Zie voor meer informatie over hoe u deze wijzigingen kunt voorbereiden, de [Microsoft Tech-Community post](https://aka.ms/CP_changes_iOS12). In de tussentijd ter ondersteuning van nieuwe iOS-inschrijvingen in bedrijfsportal-App, hebben we de stappen in bijgewerkt [iOS-apparaat inschrijven bij Intune](https://docs.microsoft.com/en-us/intune/ios-enroll). Deze wijzigingen doc-bestand zijn live nadat Apple iOS-versie 12.2 worden vrijgegeven. 

### <a name="easier-access-to-diagnostic-settings----3804627---"></a>Eenvoudiger toegang tot diagnostische instellingen <!-- 3804627 -->
We bij het toevoegen van een nieuwe optie om de **auditlogboeken** -blade in elke werkbelasting auditlogboek in de Intune-console die u kunt rechtstreeks openen de *diagnostische instellingen* pagina.

## <a name="notices"></a>Mededelingen

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Zie tevens
Zie [Wat is er nieuw in Microsoft Intune?](whats-new.md) voor meer informatie over recente ontwikkelingen.


