---
title: In ontwikkeling - Microsoft Intune
titleSuffix: ''
description: Microsoft Intune-functies in ontwikkeling
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/15/2019
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
ms.openlocfilehash: aa38a684a32756d4f2c3be3b750f8e79b66e98f6
ms.sourcegitcommit: 8c795b041cd39e3896595f64f53ace48be0ec84c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2019
ms.locfileid: "59587379"
---
# <a name="in-development-for-microsoft-intune---april-2019"></a>In ontwikkeling voor Microsoft Intune - april 2019

Als ondersteuning bij uw gereedheid en planning worden op deze pagina updates voor en functies van de Intune-gebruikersinterface vermeld die in ontwikkeling zijn, maar nog niet zijn uitgebracht. Daarnaast:

- Als we verwachten dat u actie moet ondernemen voorafgaand aan een wijziging, publiceren we een aanvullend bericht in het Office-berichtencentrum.
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
 
## <a name="intune-in-the-azure-portal"></a>Intune in Azure Portal

<!-- 1904 start-->

### <a name="set-login-settings-and-control-restart-options-on-macos-devices----1210083---"></a>Aanmeldingsinstellingen configureren en opties voor opnieuw opstarten beheren op macOS-apparaten <!-- 1210083 -->
U kunt op macOS-apparaten een apparaatconfiguratieprofiel maken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **macOS** kiezen als platform > **Apparaatfuncties** als profieltype). Er komen nieuwe instellingen voor het aanmeldingsvenster, zoals het weergeven van een aangepaste banner, het kiezen hoe gebruikers zich aanmelden, het weergeven of verbergen van de energie-instellingen en meer.

Ga naar [Instellingen van apparaatfuncties voor macOS](macos-device-features-settings.md) als u de huidige instellingen wilt zien.

Is van toepassing op: macOS

### <a name="advanced-settings-for-windows-defender-firewall----1311949---"></a>Geavanceerde instellingen voor Windows Defender Firewall <!-- 1311949 -->
U kunt binnenkort Intune gebruiken om de aangepaste firewallregels op clients voor Windows Defender te beheren. Met regels kunt u inkomend en uitgaand gedrag voor toepassingen, netwerkadressen en poorten opgeven. 

### <a name="require-app-protection-conditional-access----1634317---"></a>Voorwaardelijke toegang voor app-beveiliging vereisen  <!--1634317 -->
U kunt gebruikmaken van *App-beveiligingsbeleid vereisen*, waarmee wordt bevestigd dat beleid wordt toegepast op een app van een gebruiker voordat de aanmelding wordt voltooid, om te voorkomen dat gebruikers toegang krijgen tot gegevens die u beveiligt met voorwaardelijke toegang. Door beleidscontrole kan de eerste gebruikservaring kan worden vertraagd, maar het helpt bescherming te bieden tegen netwerkproblemen, onjuiste beheerconfiguraties of opzettelijke pogingen om het beveiligingsbeleid voor toepassingen te omzeilen. 

### <a name="retire-noncompliant-devices----1827291---"></a>Niet-compatibele apparaten buiten gebruik stellen <!-- 1827291 -->
We gaan een nieuwe nalevingsactie toevoegen om een niet-conform apparaat buiten gebruik te stellen. Bij het buiten gebruik stellen van een niet-conform apparaat worden alle bedrijfsgegevens verwijderd en wordt het apparaat ook uit het Intune-beheer verwijderd. Deze actie wordt uitgevoerd wanneer de geconfigureerde waarde in dagen is bereikt. De minimumwaarde is 30 dagen. 

### <a name="configure-settings-for-kernel-extensions-on-macos-devices----2043024---"></a>Instellingen voor kernelextensies configureren op macOS-apparaten <!-- 2043024 -->
U kunt op macOS-apparaten een apparaatconfiguratieprofiel maken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** kies > **macOS** als platform). Met een nieuwe groep instellingen kunt u kernelextensies op uw apparaten configureren en gebruiken.

Van toepassing op: macOS 10.13.2 en hoger

### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470---"></a>Profiel configureren om bepaalde vensters over te slaan tijdens het doorlopen van de configuratieassistent <!-- 2276470 -->
Wanneer u een macOS-registratieprofiel maakt, kunt u binnenkort instellen dat de configuratieassistent de volgende schermen overslaat:
- Migratie vanaf Android
- Weergavekleur
- Privacy
- iCloudStorage Als u een nieuw profiel maakt of een profiel bewerkt, moeten de geselecteerde skip-schermen worden gesynchroniseerd met de Apple MDM-server. Gebruikers kunnen de opdracht tot een handmatige synchronisatie van de apparaten geven, zodat er geen vertraging in het ophalen van de profielwijzigingen is.
Raadpleeg [MacOS-apparaten automatisch inschrijven met het Device Enrollment Program of Apple School Manager](device-enrollment-program-enroll-macos.md) voor meer informatie.

### <a name="device-users-can-view-all-managed-apps-theyve-installed-or-tried-to-install----2352913---"></a>Apparaatgebruikers kunnen alle beheerde apps bekijken die ze hebben geïnstalleerd of hebben geprobeerd te installeren <!-- 2352913 -->
In Bedrijfsportal voor Windows komen alle beheerde apps &ndash; zowel vereiste als beschikbare &ndash; die op het apparaat van een gebruiker zijn geïnstalleerd. Gebruikers kunnen geprobeerde en in behandeling zijnde app-installaties bekijken met de huidige status ervan. Als uw organisatie geen apps verplicht of beschikbaar stelt, krijgen gebruikers het bericht te zien dat er geen bedrijfs-apps zijn geïnstalleerd. Gebruikers kunnen hun apps ook sorteren of filteren op installatiestatus.

### <a name="scope-tags-for-apple-vpp-tokens---2371886---"></a>Bereiktags voor Apple VPP-tokens <!--2371886 -->
U kunt bereiktags toevoegen aan Apple VPP-tokens. Alleen gebruikers aan wie dezelfde bereiktag is toegewezen, hebben toegang tot het Apple VPP-token met die tag. VPP-apps en e-Books die zijn gekocht met dit token nemen de bereiktags ervan over. Zie [RBAC en bereiktags gebruiken](scope-tags.md) voor meer informatie over bereiktags.

### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>Toepasselijkheidsregels gebruiken bij het maken van Windows 10-apparaatconfiguratieprofielen <!-- 2549910 -->
U kunt Windows 10-apparaatconfiguratieprofielen maken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10** als platform). U kunt een **toepassingsregel** maken zodat het profiel alleen van toepassing is op een specifieke editie of versie. U maakt bijvoorbeeld een profiel waarmee bepaalde BitLocker-instellingen worden ingeschakeld. Als u het profiel toevoegt, gebruikt u een toepassingsregel zodat het profiel alleen van toepassing is op apparaten met Windows 10 Enterprise.

Van toepassing op: 
- Windows 10 en hoger

### <a name="enable-win32-app-dependencies----2617348---"></a>Win32-app-afhankelijkheden inschakelen <!-- 2617348 -->
Openbare preview - Als beheerder kunt u vereisen dat andere apps worden geïnstalleerd als afhankelijkheden voordat uw Win32-app wordt geïnstalleerd. Op het apparaat moet(e) met name de afhankelijke app(s) worden geïnstalleerd voordat de Win32-app wordt geïnstalleerd. Deze functionaliteit is alleen beschikbaar als de Intune-beheeragent naar versie 1904 (hoger dan 1.18.120.0) is geüpgraded. Dit kan 1 à 2 weken extra vergen nadat we de service naar 1904 hebben geüpgraded. Selecteer in Intune, **Client-apps** > **Apps** > **Toevoegen** om de blade **App toevoegen** weer te geven. Selecteer **Windows-app (Win32)** als **App-type**. Zie [Intune Standalone - Win32-app-beheer](apps-win32-app-management.md) voor meer informatie.

### <a name="new-device-restriction-setting-for-android-enterprise-device-owner-let-users-connect-to-wi-fi-networks-on-android-enterprise-dedicated-devices-running-multi-app-kiosk-mode---3041940---"></a>Nieuwe apparaatbeperkingsinstelling voor Android Enterprise, apparaateigenaar: gebruikers verbinding laten maken met wifinetwerken op toegewezen Android Enterprise-apparaten die worden uitgevoerd in de kioskmodus voor meerdere apps <!--3041940 -->
Beheerders kunnen een nieuwe instelling in- of uitschakelen om gebruikers Bluetooth te laten configureren op hun toegewezen Android Enterprise-apparaat dat wordt uitgevoerd in de kioskmodus voor meerdere apps. U kunt deze instelling als volgt bekijken op de Intune-console: kies **Intune** > **Apparaatconfiguratie** > **Profielofielen** > **Profiel maken** > kies **Android Enterprise** als platform en > **Alleen eigenaar van het apparaat, Apparaatbeperkingen** als profieltype > **Instellingen**  > **Toegewezen apparaten** > selecteer **Meerdere apps** in de instellingen in de vervolgkeuzelijst **Kioskmodus**. Er komt een in te schakelen optie met de naam **Wificonfiguratie** beschikbaar. 

Van toepassing op: aan Android Enterprise toegewezen apparaten die worden uitgevoerd in de kioskmodus voor meerdere apps. 

### <a name="new-device-restriction-setting-for-android-enterprise-device-owner-let-users-configure-bluetooth-and-pairing-on-android-enterprise-dedicated-devices---3041941---"></a>Nieuwe apparaatbeperkingsinstelling voor Android Enterprise, apparaateigenaar: gebruikers verbinding laten maken met Bluetooth en koppelen op toegewezen Android Enterprise-apparaten <!--3041941 -->
Beheerders kunnen een nieuwe instelling in- of uitschakelen om gebruikers Bluetooth te laten configureren op hun toegewezen Android Enterprise-apparaat dat wordt uitgevoerd in de kioskmodus voor meerdere apps. U kunt deze instelling als volgt bekijken op de Intune-console: kies **Intune** > **Apparaatconfiguratie** > **Profielofielen** > **Profiel maken** > kies **Android Enterprise** als platform > **Alleen eigenaar van het apparaat, Apparaatbeperkingen** als profieltype > **Instellingen**  > **Toegewezen apparaten** > selecteer **Meerdere apps** in de instellingen in de vervolgkeuzelijst **Kioskmodus**. Er komt een in te schakelen optie met de naam **Wificonfiguratie**. 

Van toepassing op: aan Android Enterprise toegewezen apparaten die worden uitgevoerd in de kioskmodus voor meerdere apps. 

### <a name="monitor-security-baseline-status-public-preview----3082047---"></a>Status beveiligingsbasislijnen controleren (openbare preview) <!-- 3082047 --> 
Wanneer u de *Apparaatstatus* voor uw beveiligingsbasislijnen controleert, wordt de status in de weergave georganiseerd per basislijncategorie, zoals *Vergrendeling boven*, *BitLocker* en  *Browser*. Alle beschikbare basislijncategorieën worden weergegeven. Voor elke categorie is te zien hoeveel apparaten niet overeenkomen met een specifieke basislijncategorie, onjuist zijn geconfigureerd of niet van toepassing zijn.

###  <a name="intune-security-tasks-for-defender-atp-in-public-preview----3208597---"></a>Intune-beveiligingstaken voor Defender ATP (in openbare preview) <!-- 3208597 -->
Binnenkort krijgt Intune in openbare preview aanvullende beveiligingstaken voor het pas aangekondigde Microsoft Defender Threat and Vulnerability Management.  Met deze integratie kunt kunnen beveiligingsbeheerders in Windows Defender ATP (WDATP) de aanbevolen herstelbewerkingen voor opduikende bedreigingen effectiever communiceren met Intune-beheerders. Met de toevoeging van beveiligingstaken komt er een op risico's gebaseerde aanpak voor het detecteren en classificeren van beveiligingsproblemen en onjuiste configuraties van eindpunten.

Zie voor meer informatie over beveiligingstaken in Intune het blogbericht over [het gebruik van Intune-beveiligingstaken als uitbreiding van Threat and Vulnerability Management van Microsoft Defender ATP](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/Microsoft-Intune-security-tasks-extend-Microsoft-Defender-ATP-s/ba-p/369857). 

### <a name="create-and-use-oemconfig-device-configuration-profiles-in-intune----3305883---"></a>OEMConfig-apparaatconfiguratieprofielen in Microsoft Intune maken en gebruiken <!-- 3305883 -->
Intune gaat ondersteuning bieden voor het configureren van Android Enterprise-apparaten met OEMConfig. U kunt specifiek een apparaatconfiguratieprofiel maken, en instellingen toepassen op Android Enterprise-apparaten met behulp van OEMConfig (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** als platform).

Ondersteuning voor OEM's is momenteel per OEM. Als de gewenste OEMConfig app niet beschikbaar is in de lijst met OEMConfig-apps, neemt u contact op met `IntuneOEMConfig@microsoft.com`.

Van toepassing op: 
- Android Enterprise

### <a name="new-device-restriction-settings-for-android-enterprise-device-owner----3574254---"></a>Nieuwe apparaatbeperkingsinstellingen voor Android Enterprise-apparaateigenaar <!-- 3574254 -->
Op Android Enterprise-apparaten kunt u een profiel voor apparaatbeperking maken om functies toe te staan of te beperken en regels voor wachtwoorden in te stellen (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > Kies **Android Enterprise** als platform > **Alleen apparaateigenaar > Apparaatbeperkingen** als profieltype). 

Er worden nieuwe instellingen beschikbaar gesteld, waaronder wachtwoordinstellingen, waarmee volledig beheerde apparaten volledige toegang krijgen tot apps in de Google Play Store, en meer. 

Ga naar [Met Android Enterprise-apparaatinstellingen functies toestaan of beperken](device-restrictions-android-for-work.md) voor de huidige lijst met instellingen. 

Van toepassing op: volledig beheerde Android Enterprise-apparaten

### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---"></a>Controleren of er zich een TPM-chipset in een nalevingsbeleid voor Windows 10-apparaten bevindt <!-- 3617671 -->
Veel apparaten met Windows 10 en hoger hebben TPM-chipsets (Trusted Platform Module). Met een nieuwe nalevingsinstelling wordt gecontroleerd of het apparaat een TPM bevat.

In [Instellingen voor nalevingsbeleid voor Windows 10 en hoger](compliance-policy-create-windows.md) worden de huidige instellingen vermeld.

Van toepassing op: 
- Windows 10 en hoger

### <a name="configure-your-win32-apps-to-be-installed-on-intune-enrolled-azure-ad-joined-devices----3695227---"></a>Uw Win32-apps configureren voor een installatie op bij Intune ingeschreven apparaten die met Azure AD zijn gekoppeld <!-- 3695227 -->
U kunt uw Win32-apps toewijzen om te worden geïnstalleerd op apparaten die bij Intune zijn geregistreerd en aan Microsoft Azure AD zijn gekoppeld. Zie [Win32-app-beheer](apps-win32-app-management.md) voor meer informatie over Win32-apps in Intune.

### <a name="windows-defender-advanced-threat-protection-baseline----3754134---"></a>Windows Defender Advanced Threat Protection-basislijn <!-- 3754134 -->
We voegen een nieuwe basislijn toe om u te helpen bij het configureren van Windows Defender Advanced Threat Protection-instellingen.

### <a name="device-overview-shows-primary-user---794259---"></a>Overzicht van apparaat geeft de primaire gebruiker weer <!--794259 -->
In de overzichtspagina van het apparaat ziet u de primaire gebruiker, ook wel de UDA-gebruiker genoemd (UDA: User Device Affinity, gebruikersaffiniteit apparaat). Als u de primaire gebruiker van een apparaat wilt zien, kiest u **Intune** > **Apparaten** > **Alle apparaten** > Een apparaat kiezen. De primaire gebruiker wordt bovenaan de pagina **Overzicht** weergegeven.

### <a name="expanded-support-for-android-enterprise-fully-managed-devices----3903241-3903244-3903246---"></a>Uitgebreidere ondersteuning voor volledig beheerde Android Enterprise-apparaten <!-- 3903241, 3903244, 3903246 -->
We gaan de ondersteuning voor volledig beheerde Android Enterprise-apparaten uitbreiden ([voor het eerst aangekondigd in januari 2019](whats-new.md#week-of-january-14-2019)) met het volgende:
- Naleving
- Voorwaardelijke toegang
- Een nieuwe app voor eindgebruikers

Ga naar **Apparaatinschrijving** > **Android-inschrijving** > **Bedrijfseigendom, volledig beheerde gebruikersapparaten** om volledige beheerde Android-apparaten in te stellen. Ondersteuning voor volledig beheerde Android-apparaten blijft in preview en bepaalde Intune-functies werken mogelijk niet volledig. 

### <a name="additional-managed-google-play-app-reporting-for-android-enterprise-work-profile-devices----4105925---"></a>Aanvullende rapportage van beheerde Google Play-apps voor apparaten met Android Enterprise-werkprofiel <!-- 4105925 -->
Voor beheerde Google Play-apps die op apparaten met Android Enterprise-werkprofiel zijn geïmplementeerd, wordt het mogelijk om het specifieke versienummer van de geïnstalleerde app op het apparaat weer te geven. Dit geldt alleen voor vereiste apps. Dezelfde functionaliteit voor beschikbare apps wordt ingeschakeld in een toekomstige release.

### <a name="ios-third-party-keyboards----4111843---"></a>iOS-toetsenborden van derden <!-- 4111843 -->
De ondersteuning voor het Intune-app-beveiligingsbeleid voor de instelling **Toetsenborden van derden** wordt beëindigd vanwege een iOS-platformwijziging. U zult deze instelling niet meer kunnen configureren op de Intune-beheerconsole en deze wordt niet meer afgedwongen op de client in de Intune App SDK.

<!-- 1903 start-->

### <a name="block-users-from-scanning-for-windows-updates----3316758---"></a>Blokkeren dat gebruikers kunnen zoeken naar Windows-updates <!-- 3316758 -->
We voegen een nieuwe Windows-update-ringinstelling toe waarmee u kunt blokkeren dat gebruikers zoeken naar Windows-updates. Deze instelling wordt niet beschikbaar vanuit de portal, maar kan worden geconfigureerd met behulp van de Intune Graph API.

### <a name="windows-update-notifications----3316782---"></a>Windows Update-meldingen <!-- 3316782 -->
We voegen ondersteuning toe voor de Windows-update-ringconfiguraties, zodat u de Windows Update-meldingen kunt configureren die uw gebruikers te zien krijgen. Deze instelling wordt niet beschikbaar vanuit de portal, maar kan worden geconfigureerd met behulp van de Intune Graph API.

### <a name="easier-access-to-diagnostic-settings----3804627---"></a>Eenvoudiger toegang tot Diagnostische instellingen <!-- 3804627 -->
We voegen een nieuwe optie toe aan de blade **Auditlogboeken** van elke auditlogboekworkload op de Intune-console, waarmee u rechtstreeks de pagina *Diagnostische instellingen* kunt openen.

## <a name="notices"></a>Mededelingen

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Zie tevens
Zie [Wat is er nieuw in Microsoft Intune?](whats-new.md) voor meer informatie over recente ontwikkelingen.


