---
title: In ontwikkeling - Microsoft Intune
titleSuffix: ''
description: Microsoft Intune-functies in ontwikkeling
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.assetid: 25b3c26e-cf4e-4152-8306-bf4be4af2ad1
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 04b284a62076122cec70b6b455151a0377470521
ms.sourcegitcommit: 16a9109b4028589c17695d41271ca4fee8b1d697
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 11/26/2019
ms.locfileid: "74540739"
---
# <a name="in-development-for-microsoft-intune---december-2019"></a>In ontwikkeling voor Microsoft Intune - december 2019

Als hulp bij uw gereedheid en planning worden op deze pagina updates voor en functies van de Intune-gebruikersinterface vermeld die in ontwikkeling zijn, maar nog niet zijn uitgebracht. Naast de informatie op deze pagina:

- Als we verwachten dat u actie moet ondernemen vóór een wijziging, publiceren we een aanvullend bericht in het Office-berichtencentrum.
- Wanneer een functie productie wordt ingevoerd, of het nu gaat om een preview-versie of algemeen beschikbaar is, wordt de beschrijving van de functie verplaatst van deze pagina naar [wat er nieuw](whats-new.md)is.
- Deze pagina en de pagina [Nieuwe functies](whats-new.md) worden regelmatig bijgewerkt. Controleer op andere updates.
- Raadpleeg de [Microsoft 365-roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) voor strategische producten en tijdlijnen.

> [!NOTE]
> Deze pagina weerspiegelt onze huidige verwachtingen over de mogelijkheden van intune in een toekomstige release. Datums en afzonderlijke functies kunnen worden gewijzigd. Op deze pagina worden niet alle functies in de ontwikkeling beschreven.

**RSS feed**: u ziet wanneer deze pagina wordt bijgewerkt door de volgende URL in uw feedlezer te kopiëren en plakken: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->

<!-- Common categories:  
## App management
## Device configuration
## Device enrollment
## Device management
## Intune apps
## Monitor and troubleshoot
## Role-based access control
## Security

-->
 
<!-- ***********************************************-->
## <a name="app-management"></a>Appbeheer

### <a name="ios-user-licensed-vpp-apps---5619268-idready---"></a>met iOS-licenties voor gebruikers met VPP<!-- 5619268 idready -->
Voor gebruikers registratie iOS-apparaten worden eind gebruikers niet langer weer gegeven met VPP-toepassingen met een licentie die zijn geïmplementeerd als beschikbaar. Eind gebruikers blijven echter alle gebruikers met een openstaande VPP-app in de Bedrijfsportal zien. Zie [iOS- en macOS-apps beheren die zijn aangeschaft via een Apple Volume Purchase Program met Microsoft Intune](~/apps/vpp-apps-ios.md) voor meer informatie over VPP-apps.

### <a name="retrieve-personal-recovery-key-from-mem-encrypted-macos-devices---4851745-idready---"></a>Persoonlijke herstel sleutel ophalen van met MEM versleutelde macOS-apparaten<!-- 4851745 idready -->
Eind gebruikers kunnen hun persoonlijke herstel sleutel (FileVault Key) ophalen met behulp van de iOS-Bedrijfsportal-app. Het apparaat met de persoonlijke herstel sleutel moet zijn Inge schreven bij intune en moeten worden versleuteld met FileVault via intune. Met de iOS-Bedrijfsportal-app kan een eind gebruiker de Safari-webweergave openen en hun persoonlijke herstel sleutel ophalen. Selecteer in intune de optie **apparaten** > *het versleutelde en Inge schreven macOS-apparaat* > **herstel sleutel ophalen**. Zie [FileVault-versleuteling voor macOS](~/protect/encrypt-devices.md#filevault-encryption-for-macos)voor meer informatie over FileVault.

### <a name="microsoft-app-icons-update--4677605--"></a>Micro soft app-pictogrammen bijwerken<!--4677605-->
De pictogrammen die worden gebruikt voor micro soft-apps in het deel venster app-doel groep voor het app-beveiligings beleid en het app-configuratie beleid worden bijgewerkt.

### <a name="smime-support-for-microsoft-outlook-mobile---2669398----"></a>S/MIME-ondersteuning voor micro soft Outlook Mobile<!-- 2669398  -->
InTune biedt ondersteuning voor het leveren van S/MIME-ondertekening en versleutelings certificaten die kunnen worden gebruikt met Outlook Mobile op iOS en Android. Zie [e-mail instellingen voor IOS-apparaten](~/configuration/email-settings-ios.md) en [e-mail instellingen voor Android-apparaten](~/configuration/email-settings-android.md)voor meer informatie.

### <a name="custom-settings-support-for-macos-applications---4736278----"></a>Ondersteuning van aangepaste instellingen voor macOS-toepassingen<!-- 4736278  -->
InTune ondersteunt aangepaste instellingen, zodat u specifieke sleutels en waarden kunt toevoegen aan een bestaand eigenschappen lijst bestand voor voor keuren (. plist) om macOS-apps en het apparaat te configureren. Niet alle apps ondersteunen beheerde voor keuren, en in sommige gevallen kunnen alleen specifieke instellingen worden beheerd. De instellingen worden alleen geïmplementeerd via het kanaal van het apparaat. U moet alleen eigenschappen lijst bestanden of XML-bestanden uploaden die de kanaal instellingen van het apparaat hebben.

### <a name="display-notifications-for-the-company-portal-app-on-windows---1808082----"></a>Meldingen weer geven voor de Bedrijfsportal-app in Windows<!-- 1808082  -->
De Bedrijfsportal-app wordt bijgewerkt op Windows-apparaten om pop-upmeldingen voor gebruikers weer te geven, zelfs wanneer de toepassing wordt gesloten. In de update worden alleen meldingen voor beschik bare apps weer gegeven wanneer de installatie status is voltooid of mislukt. De Bedrijfsportal-app toont geen meldingen voor vereiste toepassingen.

### <a name="display-installation-status-messages-for-the-company-portal-app---2514416----"></a>Berichten over de installatie status voor de app Bedrijfsportal weer geven<!-- 2514416  -->
In de Bedrijfsportal-app worden aanvullende status berichten voor de app-installatie weer gegeven voor eind gebruikers. De volgende voor waarden zijn van toepassing op nieuwe Win32-afhankelijkheids functies:
- App installeren mislukt. Er is niet voldaan aan de afhankelijkheden die zijn gedefinieerd door de beheerder.

### <a name="configure-app-notification-content-for-organization-accounts---2576686---"></a>Inhoud van app-meldingen voor organisatie accounts configureren<!-- 2576686 -->
Met de intune-APP op Android-en iOS-apparaten kunt u app-meldings inhoud voor organisatie accounts beheren. Deze functie vereist ondersteuning van toepassingen en is mogelijk niet beschikbaar voor alle toepassingen waarvoor APP is ingeschakeld. Zie [Overzicht van App-beveiligingsbeleid](../apps/app-protection-policy.md) voor meer informatie over APP.

<!-- ***********************************************-->
## <a name="device-configuration"></a>Apparaatconfiguratie

### <a name="block-users-from-configuring-certificate-credentials-in-the-managed-keystore-on-android-enterprise-device-owner-devices---3311998-idready---"></a>Voor komen dat gebruikers certificaat referenties configureren in de beheerde-opslag op Android-apparaten met een apparaat eigenaar<!-- 3311998 idready -->
Op Android-apparaten met de eigenaar van het apparaat is er een nieuwe instelling om te voor komen dat gebruikers hun certificaat referenties configureren in de beheerde-opslag (**apparaatconfiguratie** > **profielen** > **profiel maken** > **Android Enter prise** voor platform > eigenaar van het **apparaat alleen > beperkingen** voor het profiel type > **gebruikers en accounts**).

Ga naar [Android Enterprise-apparaatinstellingen om beperkingsfuncties toe te staan of te beperken met behulp van Intune](../configuration/device-restrictions-android-for-work.md) om de huidige instellingen te zien.

Van toepassing op:
- Android Enter prise-apparaat eigenaar, inclusief toegewezen en volledig beheerde apparaten

### <a name="wired-network-device-configuration-profiles-for-macos-devices---3508686-idready---"></a>Configuratie profielen van bekabeld netwerk apparaat voor macOS-apparaten<!-- 3508686 idready -->
Op macOS-apparaten bevat een toekomstige update een nieuw configuratie profiel voor een apparaat waarmee bekabelde netwerken (**apparaatconfiguratie** > **profielen** worden geconfigureerd > **profiel** > **MacOS** voor platform > **bekabeld netwerk** voor profiel type). Gebruik deze functie om 802.1 x-profielen te maken voor het beheren van bekabelde netwerken en om deze bekabelde netwerken te implementeren op uw macOS-apparaten.

Van toepassing op:
- macOS

### <a name="add-automatic-proxy-settings-to-wi-fi-profiles-for-android-enterprise-work-profiles---4490822-idready---"></a>Automatische proxy-instellingen toevoegen aan Wi-Fi-profielen voor Android Enter prise work-profielen<!-- 4490822 idready -->
Op apparaten met een werk Profiel van Android Enter prise kunt u Wi-Fi-profielen maken. Wanneer u het type Wi-Fi Enter prise kiest, kunt u ook het type Extensible Authentication Protocol (EAP) invoeren dat in uw Wi-Fi-netwerk wordt gebruikt.

Bij een toekomstige update kunt u, wanneer u het Enter prise-type kiest, automatische proxy-instellingen invoeren, met inbegrip van een proxy server-URL, zoals `proxy.contoso.com`.

Ga voor een overzicht van de huidige Wi-Fi-instellingen die u kunt configureren naar [Wi-Fi-instellingen toevoegen voor apparaten met Android Enter prise en Android kiosk in Microsoft intune](../configuration/wi-fi-settings-android-enterprise.md).

Van toepassing op:
- Android Enterprise - Werkprofiel

### <a name="enable-network-access-control-nac-with-cisco-anyconnect-vpn-on-ios-devices---4860111-idready---"></a>Netwerk toegangs beheer (NAC) met Cisco AnyConnect VPN inschakelen op iOS-apparaten<!-- 4860111 idready -->
Op iOS-apparaten kunt u een VPN-profiel maken en verschillende verbindings typen gebruiken, waaronder Cisco AnyConnect (**apparaatconfiguratie** > **profielen** > **profiel maken** > **IOS** voor platform > **VPN** voor profiel type > **Cisco AnyConnect** voor het verbindings type). 

In een toekomstige update kunt u Network Access Control (NAC) inschakelen met Cisco AnyConnect. Om deze functie te gebruiken, moet u ook het volgende doen:

1. Gebruik de stappen in **configure Microsoft intune als MDM-server** om de Cisco Identity Services Engine (ISE) in azure te configureren in de [Cisco Identity Services engine-beheerders handleiding](https://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html).
2. Selecteer in het profiel voor configuratie van intune de optie **netwerk Access Control inschakelen (NAC)** .

Als u alle beschik bare VPN-instellingen wilt weer geven, gaat u naar [VPN-instellingen op Ios-apparaten configureren](../configuration/vpn-settings-ios.md).

Van toepassing op:
- iOS

### <a name="updated-single-sign-on-experience-for-apps-and-websites-on-your-ios-ipados-and-macos-devices---4999578-idready---"></a>De ervaring voor eenmalige aanmelding voor apps en websites op uw iOS-, iPadOS-en macOS-apparaten is bijgewerkt<!-- 4999578 idready -->
InTune voegt meer instellingen voor eenmalige aanmelding toe voor iOS-, iPadOS-en macOS-apparaten. Op dit moment kunt u referentie-SSO-toepassings uitbreidingen en de ingebouwde Kerberos-extensie van Apple configureren in intune. In een toekomstige update kunt u de SSO-extensies voor het omleiden van apps configureren die zijn geschreven door uw organisatie of door uw ID-provider. 

Gebruik deze instellingen om een naadloze eenmalige aanmelding te configureren voor apps en websites die gebruikmaken van moderne authenticatie methoden, zoals OAuth en SAML2. 

Als u wilt zien welke extensie-instellingen voor SSO-apps u kunt configureren, gaat u naar [SSO op Ios](../configuration/ios-device-features-settings.md#single-sign-on-app-extension) en [SSO op macOS](../configuration/macos-device-features-settings.md#single-sign-on-app-extension).

Van toepassing op:
- iOS/iPadOS
- macOS

### <a name="require-use-of-approved-keyboards-on-android--4761794-idready---"></a>Gebruik van goedgekeurde toetsen borden in Android vereisen<!--4761794 IDready -->
U kunt een lijst met goedgekeurde toetsen borden opgeven voor gebruik in beheerde Android-apps. Vanuit de beheerde app wordt de gebruiker gevraagd om over te scha kelen naar een van de goedgekeurde toetsen borden die al zijn geïnstalleerd op het apparaat of, indien nodig, ze naar de Google Play Store om een van de goedgekeurde toetsen borden te downloaden en in te stellen. De gebruiker kan alleen tekst velden in een beheerde app bewerken als hun actieve toetsen bord een van de goedgekeurde toetsen borden is.

### <a name="use-pkcs-certificates-with-wi-fi-profiles-on-windows-10-and-later-devices---3246388----"></a>PKCS-certificaten gebruiken met Wi-Fi-profielen op apparaten met Windows 10 en hoger<!-- 3246388  -->
Op dit moment kunt u Windows Wi-Fi-profielen verifiëren met SCEP-certificaten (**apparaatconfiguratie** > **profielen** > **profiel maken** > **Windows 10 en hoger** voor platform > **Wi-Fi** voor Profiel type > EAP- **type** > - **onderneming** ). U kunt PKCS-certificaten gebruiken met uw Windows Wi-Fi-profielen. Met deze functie kunnen gebruikers Wi-Fi-profielen verifiëren met behulp van nieuwe of bestaande PKCS-certificaat profielen in uw Tenant. 

Zie [Wi-Fi-instellingen voor Windows 10-en nieuwere apparaten toevoegen in intune](../configuration/wi-fi-settings-windows.md)voor meer informatie over Wi-Fi-profielen.

Van toepassing op:
- Windows 10 en hoger

### <a name="new-exchangeactivesync-settings-when-creating-an-email-device-configuration-profile-on-ios-devices---4892824----"></a>Nieuwe ExchangeActiveSync-instellingen bij het maken van een configuratie profiel voor een e-mail apparaat op iOS-apparaten<!-- 4892824  --> 
Op iOS/iPadOS-apparaten kunt u een e-mail verbinding configureren in een configuratie profiel voor een apparaat (**apparaatconfiguratie** > **profielen** > **profiel maken** > **IOS/IPadOS** voor platform > **-e-mail** voor het profiel type). 

Er worden nieuwe ExchangeActiveSync-instellingen beschikbaar, waaronder:
- Kies de services die u wilt synchroniseren (of blok keren synchronisatie), zoals e-mail, agenda en contact personen.
- Gebruikers toestaan om de synchronisatie-instellingen voor deze services op hun apparaten te wijzigen. 

Als u de huidige instellingen wilt zien, gaat u naar [e-mail Profiel instellingen voor IOS-apparaten in intune](../configuration/email-settings-ios.md).

Van toepassing op:
- iOS 13.0 en hoger
- iPadOS 13.0 en hoger

### <a name="prevent-users-from-adding-personal-google-accounts-to-android-enterprise-device-owner-and-dedicated-devices---5353228----"></a>Voor komen dat gebruikers persoonlijke Google-accounts toevoegen aan de eigenaar van het Android-apparaat en de toegewezen apparaten<!-- 5353228  -->
U kunt voor komen dat gebruikers persoonlijke Google-accounts maken op Android Enter prise Device-eigenaar en toegewezen apparaten (**apparaatconfiguratie** > **profielen** > **profiel maken** > **Android Enter prise** alleen voor platform > **apparaat-eigenaar > beperkingen van apparaten** voor profiel type > **gebruikers en account instellingen**).

Ga naar [Met Android Enterprise-apparaatinstellingen functies toestaan of beperken met behulp van Intune](../configuration/device-restrictions-android-for-work.md) als u alle instellingen wilt bekijken die u momenteel kunt configureren.

Van toepassing op:
- Android Enterprise-apparaateigenaar
- Toegewezen Android Enterprise-apparaten

### <a name="server-side-logging-for-siri-commands-setting-is-removed-in-ios-device-restrictions-profile---5468501----"></a>De instelling logboek registratie aan server zijde voor SIRI-opdrachten wordt verwijderd in profiel voor iOS-apparaten<!-- 5468501  -->
Op iOS-apparaten kunt u een profiel voor beperkingen voor apparaten maken waarmee logboek registratie aan de server zijde wordt geconfigureerd voor SIRI-opdrachten (**apparaatconfiguratie** > **profielen** > **maken** > **IOS/iPadOS** voor platform > **Beperkingen** voor het profiel type > **ingebouwde apps**). De instelling **logboek registratie aan server zijde voor SIRI-opdrachten** wordt verwijderd.

Deze instelling wordt verwijderd uit de intune-beheer console. Deze instelling heeft geen effect op het apparaat, zelfs als bestaande beleids regels waarvoor deze instelling is geconfigureerd, de instelling blijven weer geven. Als u de instelling uit bestaande beleids regels wilt verwijderen, gaat u naar het beleid, maakt u een kleine bewerking, slaat u deze op en wordt het beleid bijgewerkt.

Ga naar [iOS- en iPadOS-apparaatinstellingen om functies toe te staan of te beperken met Intune](../configuration/device-restrictions-ios.md) als u alle configureerbare instellingen wilt bekijken.

Van toepassing op:
- iOS

<!-- ***********************************************-->
<!--## Device enrollment-->

<!-- ***********************************************-->
<!--## Device management-->


<!-- ***********************************************-->
<!--## Intune apps-->
 

<!-- ***********************************************-->
## <a name="monitoring-and-troubleshooting"></a>Bewaking en probleem oplossing

### <a name="centralized-audit-logs--5603185-5697164--"></a>Gecentraliseerde audit logboeken<!--5603185, 5697164-->
In een nieuwe gecentraliseerde controle logboek ervaring worden audit logboeken voor alle categorieën verzameld op één pagina. You'l kunt de logboeken filteren om de gegevens op te halen die u zoekt. Als u de audit logboeken wilt bekijken, gaat u naar **Tenant beheer** > **audit logboeken**. Zie [aanstaande wijziging in audit Logboeken in intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Upcoming-change-to-Audit-logs-in-Intune/ba-p/1015858)voor meer informatie.

<!-- ***********************************************-->
<!--## Role-based access control-->


<!-- ***********************************************-->

## <a name="security"></a>Beveiliging

### <a name="use-pkcs-certificate-profiles-to-provision-devices-with-certificates---2317124-2317130-2317139-2340517-2340528-2340529-idready---"></a>PKCS-certificaat profielen gebruiken om apparaten in te richten met certificaten<!-- 2317124, 2317130, 2317139, 2340517, 2340528, 2340529 IDready -->
U kunt een PKCS-certificaat profiel gebruiken voor het uitgeven van certificaten aan apparaten, die worden uitgebreid op basis van de huidige ondersteuning voor gebruikers certificaten. Certificaten op basis van apparaten worden ondersteund door de Android-, iOS-en Windows-platforms en kunnen worden gebruikt voor Wi-Fi-en VPN-profielen.

<!-- ***********************************************-->
## <a name="notices"></a>Mededelingen

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Zie tevens
Voor meer informatie over recente ontwikkelingen raadpleegt u [Wat is er nieuw in Microsoft Intune?](whats-new.md).


