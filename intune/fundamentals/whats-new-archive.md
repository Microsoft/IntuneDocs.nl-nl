---
title: Wat was er de vorige maanden nieuw in Microsoft Intune - Azure | Microsoft Docs
titleSuffix: ''
description: Raadpleeg oudere berichten op de Wat is er nieuw-pagina voor Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/28/2020
ms.topic: archived
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 9ba01d60-4a03-4e3e-9aba-8be905c0054c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 313d9f470e9467cc80bae9c2400d4cc64aacc7ea
ms.sourcegitcommit: 5ad0ce27a30ee3ef3beefc46d2ee49db6ec0cbe3
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 01/30/2020
ms.locfileid: "76886761"
---
# <a name="whats-new-in-the-microsoft-intune---previous-months"></a>Wat is er nieuw in Microsoft Intune - vorige maanden

[!INCLUDE [azure_portal](../includes/azure_portal.md)]


<!-- ########################## -->
## <a name="october-2019"></a>Oktober 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Appbeheer

#### <a name="improved-checklist-design-in-company-portal-app-for-android---5550857---"></a>Verbeterd ontwerp van de controlelijst in de bedrijfsportal-app voor Android<!-- 5550857 -->  
De setup-controlelijst in de Bedrijfsportal-app voor Android is bijgewerkt met een lichtgewicht ontwerp en nieuwe pictogrammen. De veranderingen zijn in lijn met de recente updates voor de Bedrijfsportal-app voor iOS. In [Wat is er nieuw in de gebruikersinterface van de app ](whats-new-app-ui.md) kunt u de oude en nieuwe versie naast elkaar zien. Zie [Inschrijven met Android-werkprofiel](/intune-user-help/enroll-device-android-work-profile) en [Uw Android-apparaat inschrijven](/intune-user-help/enroll-device-android-company-portal) voor een overzicht van de bijgewerkte inschrijvingsstappen.  

#### <a name="win32-apps-on-windows-10-s-mode-devices---3747604---"></a>Win32-apps op Windows 10 S-modusapparaten<!-- 3747604 --> 
U kunt Win32-apps installeren en uitvoeren op beheerde apparaten met Windows 10 S-modus. Hiervoor kunt u een of meer aanvullende beleidsregels maken voor de Windows S-modus met behulp van de PowerShell-hulpprogramma's van Windows Defender Application Control (WDAC). Onderteken het aanvullende beleid met de Device Guard Signing-ondertekeningsportal en upload en distribueer het beleid vervolgens via Intune. In Intune vindt u deze mogelijkheid door **Client-apps** > **Aanvullend beleid voor Windows 10 S** te selecteren. Zie [Win32-apps inschakelen op S-modusapparaten](~/apps/apps-win32-s-mode.md) voor meer informatie.

#### <a name="set-win32-app-availability-based-on-a-date-and-time---3510685---"></a>De beschikbaarheid van Win32-apps instellen op basis van een datum en tijd<!-- 3510685 -->
Als beheerder kunt u de begintijd en deadline voor een vereiste Win32-app configureren. Bij de begintijd start de Intune-beheerextensie het downloaden van de app-inhoud en slaat deze op in de cache. De app wordt geïnstalleerd op het tijdstip van de deadline. Voor beschikbare apps bepaalt de begintijd wanneer de app zichtbaar is in Bedrijfsportal. Zie [Intune Win32 app-beheer](~/apps/apps-win32-app-management.md#set-win32-app-availability-and-notifications) voor meer informatie.

#### <a name="require-device-restart-based-on-grace-period-after-win32-app-install---3136567---"></a>Opnieuw opstarten van apparaat verplicht stellen op basis van een respijtperiode na het installeren van Win32-apps<!-- 3136567 -->
U kunt eisen dat een apparaat opnieuw moet worden opgestart nadat een Win32-app is geïnstalleerd. Zie [Win32 app-beheer](~/apps/apps-win32-app-management.md) voor meer informatie.

#### <a name="dark-mode-for-ios-company-portal---4911422---"></a>Donkere modus voor iOS-bedrijfsportal<!-- 4911422 -->
Donkere modus is beschikbaar voor de iOS-bedrijfsportal. Gebruikers kunnen bedrijfsapps downloaden, hun apparaten beheren en IT-ondersteuning krijgen in het gewenste kleurenschema op basis van hun apparaatinstellingen. De iOS-bedrijfsportal wordt automatisch afgestemd op de apparaatinstellingen van de eindgebruiker voor donkere of lichte modus. Zie [Introductie van donkere modus op Microsoft Intune-bedrijfsportal voor iOS](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/Introducing-dark-mode-on-Microsoft-Intune-Company-Portal-for-iOS/ba-p/918453) voor meer informatie. Meer informatie over de iOS-bedrijfsportal vindt u in [De app Microsoft Intune-bedrijfsportal configureren](~/apps/company-portal-app.md).

#### <a name="android-company-portal-enforced-minimum-app-version---2378776---"></a>Afgedwongen minimale app-versie voor Android-bedrijfsportal<!-- 2378776 -->
Met behulp van de instelling **Minimale versie bedrijfsportal** van een app-beveiligingsbeleid kunt u een minimale versie van de bedrijfsportal opgeven die wordt afgedwongen op het apparaat van de eindgebruiker. Met deze instelling voor voorwaardelijk starten kunt u **Toegang blokkeren**, **Gegevens wissen** or **Waarschuwen** als mogelijke acties wanneer niet aan een waarde wordt voldaan. De mogelijke notaties voor deze waarde volgen het patroon *[major].[minor]* , *[major].[minor].[build]* , of *[major].[minor].[build].[revision]* .

Indien de instelling **Minimale versie bedrijfsportal** is geconfigureerd, beïnvloedt deze elke eindgebruiker die versie 5.0.4560.0 en toekomstige versies van de bedrijfsportal ontvangt. Deze instelling heeft geen invloed op gebruikers die gebruikmaken van een versie van bedrijfsportal die ouder is dan de versie waarop deze functie wordt uitgebracht. Eindgebruikers die automatische app-updates op hun apparaat gebruiken, krijgen waarschijnlijk geen dialoogvensters van deze functie te zien, aangezien ze waarschijnlijk de nieuwste versie van de bedrijfsportal hebben. Deze instelling is alleen voor Android met app-beveiliging voor ingeschreven en niet-ingeschreven apparaten. Zie [Instellingen app-beveiligingsbeleid voor Android - Voorwaardelijk starten](~/apps/app-protection-policy-settings-android.md#conditional-launch) voor meer informatie.

#### <a name="add-mobile-threat-defense-apps-to-unenrolled-devices---3005337---"></a>Mobile Threat Defense-apps toevoegen aan niet-ingeschreven apparaten<!-- 3005337 -->
U kunt een app-beschermingsbeleid voor Intune maken dat de bedrijfsgegevens van gebruikers kan blokkeren of selectief kan wissen op basis van de status van een apparaat. De status van het apparaat wordt bepaald met behulp van de geselecteerde Mobile Threat Defense-oplossing (MTD). Deze mogelijkheid bestaat voor Intune-ingeschreven apparaten nu als een nalevingsinstelling voor apparaten. Met deze nieuwe functie breiden we de dreigingsdetectie uit van een Mobile Threat Defense-leverancier naar niet-ingeschreven apparaten. Op Android vereist deze functie de nieuwste versie van de bedrijfsportal op het apparaat. Op iOS is deze functie beschikbaar voor gebruik wanneer apps de nieuwste Intune-SDK (v 12.0.15+) integreren. We zullen het onderwerp 'Wat is er nieuw' bijwerken wanneer de eerste app de nieuwste Intune-SDK heeft. De overige apps zullen doorlopend beschikbaar komen. Zie [App-beveiligingsbeleid voor Mobile Threat Defense maken met Intune](~/protect/mtd-app-protection-policy.md).

#### <a name="available-google-play-app-reporting-for-android-work-profiles---3041956-----"></a>Beschikbare rapportage over Google Play-apps voor Android-werkprofielen<!-- 3041956   -->
U kunt voor beschikbare app-installaties op toegewezen en volledig beheerde apparaten met Android Enterprise-werkprofielen de status van de app-installatie evenals de geïnstalleerde versie van beheerde Google Play-apps bekijken. Zie [How to monitor app protection policies](~/apps/app-protection-policies-monitor.md) (App-beveiligingsbeleid controleren), [Manage Android work profile devices with Intune](~/enrollment/android-enterprise-overview.md) (Apparaten met Android-werkprofielen beheren met Intune) en [Managed Google Play app type](~/apps/apps-add-android-for-work.md#managed-google-play-app-types) (Type beheerde Google Play-app) voor meer informatie.

#### <a name="microsoft-edge-version-77-and-later-for-windows-10-and-macos-public-preview---3872025-4678761----"></a>Microsoft Edge versie 77 en later voor Windows 10 en macOS (openbare preview)<!-- 3872025, 4678761  -->
Microsoft Edge versie 77 en hoger wordt beschikbaar voor implementatie op pc's met Windows 10 en macOS. 

De openbare preview biedt **Dev**- en **Bèta**-kanalen voor Windows 10 en een **Bèta**-kanaal voor macOS. De implementatie is alleen in het Engels (EN) beschikbaar, maar eindgebruikers kunnen de weergavetaal wijzigen in de browser via **Instellingen** > **Talen**. Microsoft Edge is een Win32-app die wordt geïnstalleerd in systeemcontext en in soortgelijke architecturen (x86-app in een x86-besturingssysteem en x64-app in een x64-besturingssysteem). Automatische updates van de browser is bovendien standaard **Ingeschakeld** en Microsoft Edge kan niet worden verwijderd. Zie [Microsoft Edge voor Windows 10 toevoegen aan Microsoft Intune](~/apps/apps-windows-edge.md) en [Documentatie bij Microsoft Edge](https://go.microsoft.com/fwlink/?linkid=2103823) voor meer informatie.

#### <a name="update-to-app-protection-ui-and-ios-app-provisioning-ui---4102027-4102029-----"></a>Update van de gebruikersinterface voor app-beveiliging en de gebruikersinterface voor inrichting van iOS-apps<!-- 4102027, 4102029   -->
De gebruikersinterface om app-beveiligingsbeleid en inrichtingsprofielen voor iOS-apps in Intune te maken en bewerken, is bijgewerkt. De gebruikersinterface wordt onder andere op deze punten gewijzigd:
- Een vereenvoudigde ervaring in de vorm van een wizard, beknopt weergegeven binnen één blade. 
- Een update van de maakstroom om toewijzingen toe te voegen.
- Een samenvattingspagina van alle items die zijn ingesteld bij het weergeven van eigenschappen, vóór het maken van een nieuw beleid of bij het bewerken van een eigenschap. Tijdens het bewerken van eigenschappen toont de samenvatting ook alleen een lijst met items in de categorie met eigenschappen die wordt bewerkt.

Zie [App-beveiligingsbeleid maken en toewijzen](~/apps/app-protection-policies.md) en [Inrichtingsprofielen voor iOS-apps gebruiken ](~/apps/app-provisioning-profile-ios.md)voor meer informatie.

#### <a name="intune-guided-scenarios---4850318-4831296-3610611----"></a>Begeleide scenario's voor Intune<!-- 4850318, 4831296, 3610611  -->
Intune biedt nu begeleide scenario's die u helpen bij het voltooien van een specifieke taak of een set taken in Intune. Een begeleid scenario is een aangepaste reeks stappen (werkstroom) die zijn gecentreerd rond een end-to-end-use-case. Algemene scenario's worden gedefinieerd op basis van de rol die een beheerder, gebruiker of apparaat in uw organisatie speelt. Deze werkstromen vereisen doorgaans een verzameling zorgvuldig gegroepeerde profielen, instellingen, toepassingen en beveiligingsmechanismen om de beste gebruikerservaring en beveiliging te kunnen bieden. Nieuwe begeleide scenario's zijn onder meer:
- [Microsoft Edge voor mobiel implementeren](~/fundamentals/guided-scenarios-edge.md)
- [Veilige mobiele apps voor Microsoft Office](~/fundamentals/guided-scenarios-office-mobile.md) 
- [Modern bureaublad met cloudbeheer](~/fundamentals/guided-scenarios-cloud-managed-pc.md)

Zie [Overzicht van begeleide scenario's voor Intune](guided-scenarios-overview.md) voor meer informatie.

#### <a name="additional-app-configuration-variable-available---4969237-----"></a>Extra variabele voor app-configuratie beschikbaar<!-- 4969237   -->
Wanneer u een app-configuratiebeleid maakt, kunt u de configuratievariabele `AAD Device ID` opnemen als onderdeel van de configuratie-instellingen. Selecteer in Intune **Client-apps** > **App-configuratiebeleid** > **Toevoegen**. Voer de gegevens van uw configuratiebeleid in en selecteer **Configuratie-instellingen** om de blade **Configuratie-instellingen** weer te geven. Zie voor meer informatie [App-configuratiebeleid voor beheerde Android Enterprise-apparaten: de configuratie-ontwerper gebruiken](~/apps/app-configuration-policies-use-android.md#use-the-configuration-designer).

#### <a name="create-groups-of-management-objects-called-policy-sets---3762880----"></a>Groepen beheerobjecten, zogenaamde beleidssets, maken<!-- 3762880  -->
Met beleidssets kunt u een bundel met verwijzingen maken naar reeds bestaande beheerentiteiten die moeten worden geïdentificeerd, waarop moet worden gericht en die moet worden bewaakt als één conceptuele eenheid. Met beleidssets worden geen bestaande concepten of objecten vervangen. U kunt afzonderlijke objecten blijven toewijzen in Intune en u kunt verwijzen naar afzonderlijke objecten als onderdeel van een beleidsset. Daarom worden wijzigingen aan deze afzonderlijke objecten weergegeven in de beleidsset.  In Intune selecteert u **Beleidssets** > **Maken** om een nieuwe beleidsset te maken. 


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="new-device-firmware-configuration-interface-profile-for-windows-10-and-later-devices-public-preview---2266073----"></a>Nieuw configuratie-interfaceprofiel voor apparaatfirmware voor Windows 10 en hoger (openbare preview)<!-- 2266073  -->
In Windows 10 en hoger kunt u een configuratieprofiel voor een apparaat maken om instellingen en functies te beheren (**Configuratie van apparaten** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** voor platform). In deze update is er een nieuw profieltype voor de configuratie-interface voor apparaatfirmware waarmee Intune UEFI-instellingen (BIOS) kan beheren.

Zie [DFCI-profielen gebruiken op Windows-apparaten in Microsoft Intune](../configuration/device-firmware-configuration-interface-windows.md) voor meer informatie over deze functie.

Van toepassing op:

- Windows 10 RS5 (1809) en nieuwer op ondersteunde firmware

#### <a name="ui-update-for-creating-and-editing-windows-10-update-rings---4099089-----------"></a>Update van de gebruikersinterface voor het maken en bewerken van Windows 10-update-ringen<!-- 4099089         -->
De gebruikersinterface-ervaring voor [het maken en bewerken van Windows 10-update-ringen](../protect/windows-update-for-business-configure.md#create-and-assign-update-rings) voor Intune is bijgewerkt. Wijzigingen in de gebruikersinterface zijn onder andere:  
- Een indeling in de vorm van een wizard, beknopt weergegeven op één blade van de console waardoor de wildgroei aan blades komt te vervallen wanneer u update-ringen configureert.   
- De gewijzigde werkstroom bevat Toewijzingen, voordat de initiële configuratie van de ring wordt voltooid.
- Een overzichtspagina die u kunt gebruiken om alle configuraties te bekijken die u hebt gemaakt, voordat u een nieuwe update-ring opslaat en implementeert. Tijdens het bewerken van een update-ring toont de samenvatting alleen de lijst met items die zijn ingesteld binnen de categorie met eigenschappen die u hebt bewerkt.

#### <a name="ui-update-for-creating-and-editing-ios-software-update-policy---4099090---------"></a>Update van de gebruikersinterface voor het maken en bewerken van beleid voor iOS-software-updates<!-- 4099090       --> 
De gebruikersinterface-ervaring voor het [maken](../protect/software-updates-ios.md#configure-the-policy) en [ bewerken](../protect/software-updates-ios.md#edit-a-policy) van iOS-software-updatebeleid voor Intune is bijgewerkt.  Wijzigingen in de gebruikersinterface zijn onder andere:  
- Een indeling in de vorm van een wizard, beknopt weergegeven op één blade van de console waardoor de wildgroei aan blades komt te vervallen bij het configureren van updatebeleid.   
- De gewijzigde werkstroom bevat Toewijzingen, voordat de initiële configuratie van het beleid wordt voltooid.
- Een overzichtspagina die u kunt gebruiken om alle configuraties te bekijken die u hebt gemaakt, voordat u een nieuw beleid opslaat en implementeert. Tijdens het bewerken van een beleid, toont het overzicht alleen de lijst met items die zijn ingesteld binnen de categorie met eigenschappen die u hebt bewerkt.

#### <a name="engaged-restart-settings-are-removed-from-windows-update-rings----4464404--------"></a>Instellingen voor gepland opnieuw opstarten zijn verwijderd uit Windows-update-ringen<!--  4464404      -->
Zoals eerder aangekondigd, ondersteunen Windows 10-update-ringen van Intune nu [instellingen voor deadlines](../protect/windows-update-settings.md) en wordt *Gepland opnieuw opstarten* niet meer ondersteund. Instellingen voor *Gepland opnieuw opstarten* zijn niet meer beschikbaar wanneer u update-ringen in Intune configureert of beheert.  

Deze wijziging ligt op één lijn met [wijzigingen in Windows-service](https://docs.microsoft.com//windows/whats-new/whats-new-windows-10-version-1903#servicing). Verder vervangen op apparaten met Windows 10 1903 of hoger *deadlines* configuraties voor *gepland opnieuw opstarten*.

#### <a name="prevent-installation-of-apps-from-unknown-sources-on-android-enterprise-work-profile-devices---4760025-----"></a>Installatie van apps van onbekende bronnen op apparaten met een Android Enterprise-werkprofiel voorkomen<!-- 4760025   -->
Op apparaten met een Android Enterprise-werkprofiel kunnen gebruikers nooit apps van onbekende bronnen installeren. In deze update is er een nieuwe instelling, namelijk **App-installaties van onbekende bronnen in het persoonlijke profiel voorkomen**. Met deze instelling wordt standaard voorkomen dat gebruikers apps van onbekende bronnen extern kunnen laden in het persoonlijke profiel op het apparaat.

Ga naar [Met Android Enterprise-apparaatinstellingen functies toestaan of beperken met behulp van Intune](../configuration/device-restrictions-android-for-work.md) als u de configureerbare instelling wilt bekijken.

Van toepassing op:

- Android Enterprise - Werkprofiel

#### <a name="create-a-global-http-proxy-on-android-enterprise-device-owner-devices---4816339-----"></a>Een algemene HTTP-proxy maken op Android Enterprise-apparaten met een apparaateigenaar<!-- 4816339   -->
Op Android Enterprise-apparaten kunt u een globale HTTP-proxy configureren om te voldoen aan de standaarden voor webbrowsen van uw organisatie (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** voor platform > **Apparaateigenaar > Apparaatbeperkingen** voor profieltype > **Connectiviteit**). Zodra dit is geconfigureerd, gebruikt al het HTTP-verkeer deze proxy.

Ga naar [Met Android Enterprise-apparaatinstellingen functies toestaan of beperken met behulp van Intune](../configuration/device-restrictions-android-for-work.md) als u deze functie wilt configureren en alle configureerbare instellingen wilt bekijken.

Van toepassing op:

- Android Enterprise-apparaateigenaar

#### <a name="connect-automatically-setting-is-removed-in-wi-fi-profiles-on-android-device-administrator-and-android-enterprise---5021055-----"></a>De instelling automatisch verbinding maken is verwijderd uit Wi-Fi-profielen op Android-apparaatbeheerder en Android Enterprise<!-- 5021055   -->
Op Android-apparaatbeheerder en Android Enterprise-apparaten kunt u een Wi-Fi-profiel maken om verschillende instellingen te configureren (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android-apparaatbeheerder** of **Android Enterprise** voor platform > **Wi-Fi-** voor profieltype). In deze update is de instelling **Automatisch verbinding maken** verwijderd, omdat deze [niet door Android wordt ondersteund](https://developer.android.com/reference/android/net/wifi/WifiManager.html#enableNetwork%28int%2c%20boolean%29). 

Als u deze instelling in een Wi-Fi-profiel gebruikt, hebt u mogelijk opgemerkt dat **Automatisch verbinding maken** niet werkt. U hoeft geen actie te ondernemen, maar houd er rekening mee dat deze instelling wordt verwijderd uit de Intune-gebruikersinterface.

Raadpleeg [Wi-Fi-instellingen van Android](../configuration/wi-fi-settings-android.md) of [Wi-Fi-instellingen van Android Enterprise](../configuration/wi-fi-settings-android-enterprise.md).

Van toepassing op:

- Android-apparaatbeheerder 
- Android Enterprise


#### <a name="new-device-configuration-settings-for-supervised-ios-and-ipados-devices---5199328-----"></a>Nieuwe instellingen voor apparaatconfiguratie voor iOS- en iPadOS-apparaten onder supervisie<!-- 5199328   -->
Op iOS- en iPadOS-apparaten kunt u een profiel maken om functies en instellingen op apparaten te beperken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS/iPadOS** voor platform > **Apparaatbeperkingen** voor profieltype). Deze update bevat nieuwe instellingen die u kunt beheren: 
- Toegang tot netwerkstation in Bestanden-app  
- Toegang tot USB-station in Bestanden-app 
- Wi-Fi altijd ingeschakeld 

Als u deze instellingen wilt bekijken, gaat u naar [iOS-apparaatinstellingen voor het toestaan of beperken van functies met behulp van Intune](../configuration/device-restrictions-ios.md).

Van toepassing op:

- iOS 13.0 en hoger
- iPadOS 13.0 en hoger

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="toggle-to-only-show-enrollment-status-page-on-devices-provisioned-by-out-of-box-experience-oobe--3959566--"></a>Wisselknop om alleen de pagina voor inschrijvingsstatus weer te geven op apparaten die zijn ingericht door out-of-box experience (OOBE)<!--3959566-->
U kunt er nu voor kiezen om alleen de pagina voor inschrijvingsstatus weer te geven op apparaten die zijn ingericht door Autopilot OOBE.

Om de nieuwe wisselknop weer te geven, kiest u **Intune** > **Apparaatinschrijving** > **Windows-inschrijving** > **Pagina met inschrijvingsstatus** > **Profiel maken** > **Instellingen** > **Alleen pagina's weergeven aan apparaten die zijn ingericht door out-of-box experience (OOBE)** .

#### <a name="specify-which-android-device-operating-system-versions-enroll-with-work-profile-or-device-administrator-enrollment---4350697-----"></a>Opgeven welke besturingssysteemversies van Android-apparaten registreren met werkprofiel of apparaatbeheerderinschrijving<!-- 4350697   -->
Met behulp van de Intune-beperkingen voor apparaattypen kunt u de besturingssysteemversie van het apparaat gebruiken om op te geven welke gebruikersapparaten de Android Enterprise-werkprofiel-inschrijving of Android-apparaatbeheerderinschrijving gebruiken.  Zie [Inschrijvingsbeperkingen instellen](../enrollment/enrollment-restrictions-set.md) voor meer informatie.



<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Apparaatbeheer

#### <a name="intune-supports-ios-11-and-later---4665324----"></a>Intune ondersteunt iOS 11 en hoger<!-- 4665324  -->
De Intune-inschrijving en bedrijfsportal ondersteunen nu iOS versie 11 en hoger. Oudere versies worden niet ondersteund.

#### <a name="new-restrictions-for-renaming-windows-devices---3478938----"></a>Nieuwe beperkingen voor het wijzigen van de naam van Windows-apparaten<!-- 3478938  -->
Wanneer u de naam van een Windows-apparaat wijzigt, moet u nieuwe regels volgen:
- Maximaal 15 tekens (moet kleiner zijn dan of gelijk zijn aan 63 bytes, exclusief navolgende null-tekens)
- Niet null of een lege tekenreeks
- Toegestane ASCII: letters (a-z, A-Z), cijfers (0-9) en afbreekstreepjes
- Toegestane Unicode: tekens > = 0x80, moet geldige UTF8 zijn, moet IDN-toewijsbaar zijn (dat wil zeggen dat RtlIdnToNameprepUnicode moet slagen, zie RFC 3492)
- Namen mogen niet alleen cijfers bevatten
- Namen mogen geen spaties bevatten
- Niet-toegestane tekens: { | } ~ [ \ ] ^ ' : ; < = > ? & @ ! " # $ % ` ( ) + / , . _ *)

 Zie [De naam van een apparaat wijzigen in Intune](../remote-actions/device-rename.md) voor meer informatie.

### <a name="new-android-report-on-devices-overview-page---4924364---"></a>Nieuw Android-rapport op de overzichtspagina Apparaten<!-- 4924364 -->
In een nieuw rapport op de overzichtspagina Apparaten wordt weergegeven hoeveel Android-apparaten zijn geregistreerd in elke oplossing voor apparaatbeheer. In dit diagram ziet u het aantal apparaten met werkprofiel, volledig beheerd, toegewezen en door de beheerder geregistreerd. Als u het rapport wilt zien, kiest u **Intune** > **Apparaten** > **Overzicht**.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Apparaatbeveiliging

#### <a name="microsoft-edge-baseline-preview----3787164----"></a>Microsoft Edge-basislijn (Preview)<!--  3787164  -->
We hebben een beveiligingsbasislijn-preview toegevoegd voor [Microsoft Edge-instellingen](../protect/security-baseline-settings-edge.md). 

#### <a name="pkcs-certificates-for-macos---1333650---------"></a>PKCS-certificaten voor macOS<!-- 1333650       -->
U kunt nu [PKCS-certificaten gebruiken met macOS](../protect/certficates-pfx-configure.md#create-a-pkcs-certificate-profile). U kunt het PKCS-certificaat selecteren als profieltype voor macOS en certificaten voor gebruikers en apparaten implementeren die [velden voor aangepaste naam voor het onderwerp en alternatieve onderwerpnaam](../protect/certficates-pfx-configure.md#subject-name-format) bevatten.  

PKCS-certificaat voor macOS biedt ook ondersteuning voor een nieuwe instelling, _Alle apps toegang toestaan_. Met deze instelling kunt u alle gekoppelde apps toegang geven tot de persoonlijke sleutel van het certificaat.  Raadpleeg de Apple-documentatie op https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf voor meer informatie over deze instelling.

####   <a name="derived-credentials-to-provision-ios-mobile-devices-with-certificates----1736036-1736037-1772050-2777333-----------"></a>Afgeleide referenties voor het inrichten van mobiele iOS-apparaten met certificaten<!--  1736036, 1736037, 1772050, 2777333         -->  
Intune ondersteunt het gebruik van [afgeleide referenties](../protect/derived-credentials.md) als een verificatiemethode en voor S/MIME-ondertekening en versleuteling voor iOS-apparaten. Afgeleide referenties zijn een implementatie van de *National Institute of Standards and Technology (NIST) 800-157* -standaard voor het implementeren van certificaten op apparaten.  

Afgeleide referenties zijn afhankelijk van het gebruik van een Personal Identity Verification (PIV) of Common Access Card (CAC), zoals een smartcard. Om een afgeleide referentie voor hun mobiele apparaat te verkrijgen, beginnen gebruikers in de app Bedrijfsportal en volgen ze een registratiewerkstroom die uniek is voor de provider die u gebruikt.  Alle providers hebben met elkaar gemeen dat ze vereisen dat een smartcard voor verificatie bij de afgeleide referentieprovider. Deze provider verzendt vervolgens een certificaat naar het apparaat dat is afgeleid van de smartcard van de gebruiker.  

Intune biedt ondersteuning voor de volgende afgeleide referentieproviders:
- DISA Purebred
- Entrust Datacard
- Intercede

U gebruikt afgeleide referenties als verificatiemethode voor configuratieprofielen voor apparaten voor VPN, Wi-Fi en e-mailberichten. U kunt ze ook gebruiken voor app-verificatie en S/MIME-ondertekening en -versleuteling.  

Raadpleeg [Afgeleide PIV-referenties](https://www.nccoe.nist.gov/projects/building-blocks/piv-credentials) op www.nccoe.nist.gov voor meer informatie over de standaard.

#### <a name="use-graph-api-to-specify-a-on-premises-user-principal-name-as-a-variable-for-scep-certificates----5437939----------"></a>Graph API gebruiken om een on-premises user principal name op te geven als een variabele voor SCEP-certificaten<!--  5437939        -->  
Wanneer u de [Intune Graph API](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0)gebruikt, kunt u onPremisesUserPrincipalName opgeven als een variabele voor de alternatieve naam voor het onderwerp (SAN) voor SCEP-certificaten.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="microsoft-365-device-management"></a>Microsoft 365 Device Management

#### <a name="improved-administration-experience-in-microsoft-365-device-management---5551239---"></a>Verbeterde beheerervaring in Microsoft 365 Device Management<!-- 5551239 -->
Een vernieuwde en gestroomlijnde beheerervaring is nu algemeen beschikbaar in de gespecialiseerde werkruimte van Microsoft 365 Device Management op [https://devicemanagement.microsoft.com](https://devicemanagement.microsoft.com), met daarin:

- **Bijgewerkte navigatie**: U profiteert van een vereenvoudigde navigatie op het eerste niveau die functies op logische wijze groepeert.
- **Nieuwe platformfilters**: Op de pagina's voor apparaten en apps kunt u één platform selecteren dat alleen het beleid en de apps voor het geselecteerde platform toont.
- **Nieuwe startpagina**: Een snel overzicht van de servicestatus, tenantstatus, nieuws enz. op de nieuwe homepage.

Voor meer informatie over deze verbeteringen, zie de [Blogpost voor Enterprise Mobility + Security](https://go.microsoft.com/fwlink/?linkid=2109094) op de Microsoft Tech Community-website.

#### <a name="introducing-endpoint-security-node-in-microsoft-365-device-management---5630102---"></a>Introductie van Endpoint Security-knooppunt in Microsoft 365 Device Management<!-- 5630102 -->

Een **Endpoint Security**-knooppunt is nu algemeen beschikbaar in de gespecialiseerde werkruimte van Microsoft 365 Device Management op https://devicemanagement.microsoft.com, waar de mogelijkheden voor het beveiligen van eindpunten zijn samengebracht, zoals:

- Beveiligingsbasislijnen:  Vooraf geconfigureerde groep instellingen die u helpen bij het toepassen van bekende groepen instellingen en standaardwaarden die door Microsoft worden aanbevolen.
- Beveiligingstaken: Profiteer van het Threat and Vulnerability Management (TVM) van Microsoft Defender ATP en gebruik Intune om zwakke punten in eindpunten te herstellen.
- Microsoft Defender ATP: Geïntegreerde Microsoft Defender Advanced Threat Protection (ATP) om beveiligingsschendingen te voorkomen.

Deze instellingen blijven toegankelijk via andere toepasselijke knooppunten (zoals apparaten) en de huidige geconfigureerde status blijft hetzelfde, ongeacht waar u deze mogelijkheden opent en inschakelt.

Voor meer informatie over deze verbeteringen, zie de [Blogpost voor Intune-klantsucces ](https://aka.ms/Endpoint_security_node) op de Microsoft Tech Community-website.

<!-- ########################## -->
## <a name="september-2019"></a>September 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Appbeheer

#### <a name="managed-google-play-private-lob-apps---1464182----"></a>Privé-LOB-apps uit de beheerde Google Play Store<!-- 1464182  -->
In Intune is nu toegestaan dat IT-beheerders privé-LOB-apps van Android publiceren in de beheerde Google Play Store, via een iFrame ingesloten in de Intune-console.  Voorheen moesten IT-beheerders LOB-apps rechtstreeks publiceren in de publicatieconsole van de Google Play Store. Hiervoor zijn verschillende stappen nodig en het is tijdrovend. Met deze nieuwe functie kunnen LOB-apps eenvoudig worden gepubliceerd met een minimaal aantal stappen, zonder de Intune-console te verlaten.  Beheerders hoeven zich niet meer handmatig als een ontwikkelaar te registreren bij Google, en ze hoeven de registratiekosten van $ 25 niet te betalen.  Elk van deze scenario’s voor Android Enterprise-beheer waarin de beheerde Google Play Store wordt gebruikt, kunnen profiteren van deze functie (werkprofiel, toegewezen, volledig beheerd, en niet-ingeschreven apparaten). Vanuit Intune selecteert u **Client-apps** > **Apps** > **Toevoegen**. Selecteer vervolgens **Beheerde Google Play** in de lijst met **App-typen**. Zie [Beheerde Google Play-apps toevoegen aan Android Enterprise-apparaten met Intune](../apps/apps-add-android-for-work.md) voor meer informatie over beheerde Google Play-apps.

#### <a name="windows-company-portal-experience---1473353-3598357---"></a>Versie van de Windows-bedrijfsportal-app<!-- 1473353, 3598357 -->
De Windows-bedrijfsportal wordt bijgewerkt. U kunt meerdere filters gebruiken op de apps-pagina in de Windows-bedrijfsportal. De pagina met apparaatdetails is ook bijgewerkt met een verbeterde gebruikerservaring. Deze updates worden momenteel geïmplementeerd voor alle klanten. We verwachten dat dit proces eind volgende week is voltooid.

#### <a name="macos-support-for-web-apps---3174427---"></a>macOS-ondersteuning voor web-apps<!-- 3174427 -->
Web-apps, waarmee u een snelkoppeling naar een URL op het web kunt toevoegen, kunnen in de Dock worden geïnstalleerd met behulp van de bedrijfsportal voor macOS. Eindgebruikers hebben toegang tot de actie **Installeren** op de pagina met app-details voor een web-app in de macOS-bedrijfsportal. Zie [Apps toevoegen aan Microsoft Intune](../apps/apps-add.md) en [Web-apps toevoegen aan Microsoft Intune](../apps/web-app.md) voor meer informatie over het app-type **Webkoppeling**.

#### <a name="macos-support-for-vpp-apps---3173501----"></a>macOS-ondersteuning voor VPP-apps<!-- 3173501  -->
macOS-apps, gekocht met Apple Business Manager, worden in de console weergegeven wanneer Apple VPP-tokens worden gesynchroniseerd in Intune. Met de Intune-console kunt u op apparaten en gebruikers gebaseerde licenties voor groepen toewijzen, intrekken en opnieuw toewijzen. Microsoft Intune maakt het makkelijker om VPP-apps te beheren die voor gebruik in uw bedrijf zijn gekocht door:

- Licentiegegevens rapporteren vanuit de App Store.
- Bijhouden hoeveel van de licenties u hebt gebruikt.
- U te helpen voorkomen dat er meer exemplaren van de app worden geïnstalleerd dan waarvan u eigenaar bent.

Voor meer informatie over Intune en VPP raadpleegt u [Apps en boeken met Microsoft Intune beheren die via het Volume Purchase Program zijn gekocht](../apps/vpp-apps.md).

#### <a name="managed-google-play-iframe-support---2871756----"></a>Ondersteuning voor de beheerde Google Play-iFrame<!-- 2871756  -->
Intune biedt nu ondersteuning voor het rechtstreeks toevoegen en beheren van webkoppelingen in de Intune-console via de beheerde Google Play-iFrame.  Hiermee kunnen IT-beheerders een URL en pictogramafbeelding verzenden, en deze koppelingen vervolgens implementeren op apparaten, zoals gewone Android-apps. Elk van deze scenario’s voor Android Enterprise-beheer waarin de beheerde Google Play Store wordt gebruikt, kunnen profiteren van deze functie (werkprofiel, toegewezen, volledig beheerd, en niet-ingeschreven apparaten). Vanuit Intune selecteert u **Client-apps** > **Apps** > **Toevoegen**. Selecteer vervolgens **Beheerde Google Play** in de lijst met **App-typen**. Zie [Beheerde Google Play-apps toevoegen aan Android Enterprise-apparaten met Intune](../apps/apps-add-android-for-work.md) voor meer informatie over beheerde Google Play-apps.

#### <a name="silently-install-android-lob-apps-on-zebra-devices---4252734----"></a>LOB-apps van Android op de achtergrond installeren op Zebra-apparaten<!-- 4252734  -->
Wanneer u LOB-apps (Line-of-Business) van Android installeert op [Zebra-apparaten](../configuration/android-zebra-mx-overview.md), kunt u de app op de achtergrond installeren, in plaats van dat u wordt gevraagd om de LOB-app zowel te downloaden als te installeren. Selecteer in Intune de optie **Client-apps** > **Apps** > **Toevoegen**. Selecteer in het deelvenster **App-type selecteren** de optie **Line-Of-Business-app**. Zie [Een Android Line-Of-Business-app toevoegen aan Microsoft Intune](../apps/lob-apps-android.md) voor meer informatie.

Momenteel wordt, nadat de LOB-app is gedownload, een melding over het **slagen van de download** weergegeven op het apparaat van de gebruiker. U kunt deze melding alleen negeren door in de schaduw van de melding te tikken op **Alles wissen**. Dit meldingsprobleem wordt opgelost in een toekomstige release, en de installatie vindt volledig op de achtergrond plaats, zonder dat dit zichtbaar is.

#### <a name="read-and-write-graph-api-operations-for-intune-apps---5031704----"></a>Graph API-bewerkingen voor Intune-apps lezen en schrijven<!-- 5031704  -->
De Intune Graph API kan via lees- en schrijfbewerkingen worden aangeroepen voor toepassingen, met behulp van de app-id zonder gebruikersreferenties. Zie [Working with Intune in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0) (Werken met intune in Microsoft Graph) voor meer informatie over het openen van de Microsoft Graph API voor Intune.

#### <a name="protected-data-sharing-and-encryption-for-intune-app-sdk-for-ios---3586942----"></a>Het delen en versleutelen van beveiligde gegevens voor Intune App SDK voor iOS<!-- 3586942  -->
De Intune App-SDK voor iOS gebruikt 256-bits versleutelingssleutels wanneer versleuteling is ingeschakeld door app-beveiligingsbeleid. Alle apps moeten eerst over een SDK-versie 8.1.1 beschikken, als u het delen van beveiligde gegevens wilt toestaan.

#### <a name="updates-to-microsoft-intune-app---4997846---"></a>Updates voor de Microsoft Intune-app<!-- 4997846 -->
De Microsoft Intune-app voor Android is bijgewerkt met de volgende verbeteringen:
- De lay-out is bijgewerkt en verbeterd, zodat de belangrijkste navigatiehandelingen nu onderaan staan.
- Er is een extra pagina toegevoegd waarop het gebruikersprofiel wordt weergegeven.
- Er is een weergave van meldingen toegevoegd waarvoor de gebruiker handelingen moet verrichten, zoals wanneer apparaatinstellingen moeten worden bijgewerkt.
- Er is een weergave van aangepaste pushmeldingen toegevoegd. Dit is in lijn met de ondersteuning die recent is toegevoegd in de bedrijfsportal-apps voor iOS en Android. Zie [Aangepaste meldingen verzenden in Intune](../remote-actions/custom-notifications.md) voor meer informatie.

#### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal---4394993---"></a>Voor iOS-apparaten past u het privacyvenster voor het inschrijvingsproces van de Bedrijfsportal aan<!-- 4394993 -->
Met behulp van Markdown kunt u het privacyvenster van de Bedrijfsportal aanpassen dat eindgebruikers te zien krijgen tijdens de iOS-registratie. U kunt met name de lijst met dingen aanpassen die uw organisatie niet op het apparaat kan zien of doen. Zie [De app Intune-bedrijfsportal configureren](../apps/company-portal-app.md#privacy-statement-customization) voor meer informatie.



<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="support-for-ikev2-vpn-profiles-for-ios---1943438-----"></a>Ondersteuning voor IKEv2 VPN-profielen voor iOS<!-- 1943438   -->
In deze update kunt u met het IKEv2-protocol VPN-profielen maken voor de systeemeigen VPN-client van iOS. IKEv2 is een nieuw verbindingstype in **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **VPN** voor profieltype > **Verbindingstype**.

Met deze VPN-profielen wordt de systeemeigen VPN-client geconfigureerd. Er worden dus geen VPN-client-apps geïnstalleerd of gepusht naar beheerde apparaten. Deze functie vereist dat apparaten zijn ingeschreven bij Intune (MDM-inschrijving).

Als u wilt zien welke VPN-instellingen u momenteel kunt configureren, gaat u naar [VPN-instellingen configureren op iOS-apparaten](../configuration/vpn-settings-ios.md).

Van toepassing op:

- iOS

#### <a name="device-features-device-restrictions-and-extension-profiles-for-ios-and-macos-settings-are-shown-by-enrollment-type---4886161-----"></a>Apparaatfuncties, apparaatbeperkingen, en extensieprofielen voor iOS- en macOS-instellingen worden weergegeven op inschrijvingstype<!-- 4886161   -->

In Intune maakt u profielen voor iOS- en macOS-apparaten (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** of **macOS** voor platform > **Apparaatfuncties**, **Apparaatbeperkingen**, of **Extensies** voor profieltype). 

In deze update zijn de beschikbare instellingen in de Intune-portal gecategoriseerd op basis van het inschrijvingstype waarop ze zijn toegepast:

- iOS
  - Gebruikersinschrijving
  - Apparaatinschrijving
  - Automatische apparaatinschrijving (onder toezicht)
  - Alle inschrijvingstypen

- macOS
  - Goedgekeurd door de gebruiker
  - Apparaatinschrijving
  - Automatische apparaatinschrijving
  - Alle inschrijvingstypen

Van toepassing op:

- iOS

#### <a name="new-voice-control-settings-for-supervised-ios-devices-running-in-kiosk-mode---4892835-----"></a>Nieuwe instellingen voor spraakbeheer voor iOS-apparaten onder supervisie die worden uitgevoerd in de kioskmodus<!-- 4892835   -->
In Intune kunt u beleid maken om iOS-apparaten onder supervisie uit te voeren als een kiosk of toegewezen apparaat (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype > **Kiosk**).

Deze update bevat nieuwe instellingen die u kunt beheren:
- **Spraakbeheer**: Hiermee wordt Spraakbeheer ingeschakeld op het apparaat, wanneer het apparaat in de kioskmodus is.
- **Aanpassing van spraakbeheer**: Hiermee staat u gebruikers toe de instelling voor Spraakbeheer op het apparaat te wijzigen wanneer het apparaat in de kioskmodus is.

Als u de huidige instellingen wilt zien, gaat u naar de [iOS Kiosk-instellingen](../configuration/device-restrictions-ios.md#kiosk).

Van toepassing op:

- iOS 13.0 en hoger

#### <a name="use-single-sign-on-for-apps-and-websites-on-your-ios-and-macos-devices---4893175-----"></a>Eenmalige aanmelding gebruiken voor apps en websites op iOS- en macOS-apparaten<!-- 4893175   -->
Deze update bevat enkele nieuwe instellingen voor eenmalige aanmelding voor iOS- en macOS-apparaten (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** of **macOS** voor platform > **Apparaatfuncties**, voor profieltype).

Gebruik deze instellingen om eenmalige aanmelding te configureren, speciaal bedoeld voor apps en websites die gebruikmaken van Kerberos-verificatie. U kunt kiezen tussen een algemene app-extensie voor referenties met eenmalige aanmelding, en de ingebouwde Kerberos-extensie van Apple.

Als u wilt zien welke huidige apparaatfuncties u kunt configureren, gaat u naar [iOS-apparaatfuncties](../configuration/ios-device-features-settings.md) en [macOS-apparaatfuncties](../configuration/macos-device-features-settings.md).

Van toepassing op:

- iOS 13.0 en hoger
- macOS 10.15 of hoger

#### <a name="associate-domains-to-apps-on-macos-1015-devices---4898079-----"></a>Domeinen koppelen aan apps op macOS 10.15-apparaten en hoger<!-- 4898079   -->
Op macOS-apparaten kunt u verschillende functies configureren en deze functies naar uw apparaten pushen met behulp van beleid (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **macOS** voor platform > **Apparaatfuncties** voor profieltype). In deze update kunt u domeinen koppelen aan uw apps. Deze functie helpt bij het delen van referenties op websites die verband houden met uw app, en kan worden gebruikt met de extensie voor eenmalige aanmelding, universele koppelingen, en automatisch invullen van wachtwoorden van Apple. 

Ga naar [Instellingen van macOS-apparaatfuncties in Intune](../configuration/macos-device-features-settings.md) om te zien welke huidige functies u kunt configureren.

Van toepassing op:

- macOS 10.15 of hoger

#### <a name="use-itunes-and-apps-in-the-itunes-app-store-url-when-showing-or-hiding-apps-on-ios-supervised-devices---4928474-----"></a>Gebruik 'iTunes' en 'apps' in de iTunes App Store-URL bij het weergeven of verbergen van apps op iOS-apparaten onder supervisie<!-- 4928474   --> 
In Intune kunt u beleid maken om apps weer te geven of te verbergen op iOS-apparaten onder supervisie (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype > **Apps weergeven of verbergen**). 

U kunt de iTunes App Store-URL invoeren, zoals `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`. In deze update kan zowel `apps` als `itunes` worden gebruikt in de URL, zoals:
- `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`
- `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`

Zie [Apps weergeven of verbergen](../configuration/device-restrictions-ios.md#show-or-hide-apps) voor meer informatie over deze instellingen.

Van toepassing op:
- iOS

#### <a name="windows-10-compliance-policy-password-type-values-are-clearer-and-match-csp---5138985---"></a>Waarden voor het wachtwoordtype voor Windows 10-nalevingsbeleid zijn duidelijker en komen niet overeen met CSP<!-- 5138985 -->
Op Windows 10-apparaten kunt u nalevingsbeleid maken waarvoor specifieke wachtwoordfuncties zijn vereist (**Apparaatcompatibiliteit** > **beleid** > **Beleid maken** > **Windows 10 en later** voor platform > **Systeembeveiliging**). In deze update:
- De waarden voor **Wachtwoordtype** zijn duidelijker, en zijn bijgewerkt om overeen te komen met de [DeviceLock/AlphanumericDevicePasswordRequired CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-alphanumericdevicepasswordrequired).
- De instelling **Wachtwoordverlooptijd (dagen)** is bijgewerkt om waarden toe te staan van minimaal 1 en maximaal 730 dagen. 

Zie [Instellingen voor Windows 10 en later om apparaten te markeren als compatibel of niet-compatibel](../protect/compliance-policy-create-windows.md) voor meer informatie over instellingen voor Windows 10-naleving. 

Van toepassing op:
- Windows 10 en hoger

 #### <a name="updated-ui-for-configuring-microsoft-exchange-on-premises-access---4092920---"></a>Bijgewerkte gebruikersinterface voor het configureren van on-premises toegang tot Microsoft Exchange<!-- 4092920 -->  
De console is bijgewerkt, zodat u [on-premises toegang tot Microsoft Exchange kunt configureren](../protect/conditional-access-exchange-create.md). Alle configuraties voor on-premises toegang tot Exchange zijn nu beschikbaar in hetzelfde deelvenster van de console waar u *Beheer voor on-premises toegang tot Exchange kunt inschakelen*.  

#### <a name="allow-or-restrict-adding-app-widgets-to-the-home-screen-on-android-enterprise-work-profile-devices---1109650----"></a>Het toevoegen van app-widgets aan het startscherm in apparaten met Android Enterprise-werkprofielen toestaan of beperken<!-- 1109650  --> 
Op Android Enterprise-apparaten kunt u functies in het werkprofiel configureren (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** voor platform > **Alleen werkprofiel > Apparaatbeperkingen** voor profieltype). In deze update kunt u gebruikers toestaan om widgets die worden weergegeven in werkprofiel-apps, toe te voegen aan het startscherm van het apparaat.

Ga naar [Met Android Enterprise-apparaatinstellingen functies toestaan of beperken met behulp van Intune](../configuration/device-restrictions-android-for-work.md) als u alle configureerbare instellingen wilt bekijken.

Van toepassing op:
- Android Enterprise - Werkprofiel

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="new-tenants-will-default-away-from-android-device-administrator-management---4869790-----"></a>Nieuwe tenants worden standaard verwijderd uit het beheer van Android-apparaatbeheerders<!-- 4869790   -->
De beheermogelijkheden voor Android-apparaten zijn vervangen door Android Enterprise. Daarom raden we u aan om vanaf nu Android Enterprise te gebruiken voor nieuwe inschrijvingen. Bij een toekomstige update moeten de volgende vereiste stappen voor Android-inschrijving worden uitgevoerd voor nieuwe tenants, om beheer van apparaatbeheerders te gebruiken: ga naar **Intune** > **Apparaatinschrijving** > **Android-inschrijving** > **Bevoegdheden voor apparaatbeheerder voor het beheer van persoonlijke apparaten en apparaten in bedrijfseigendom** > **Apparaatbeheerder gebruiken om apparaten te beheren.** .

De omgevingen van bestaande tenants worden niet gewijzigd.

Zie [Inschrijving van Android-apparaatbeheerders](https://docs.microsoft.com/intune/android-enroll-device-administrator) voor meer informatie over Android-apparaatbeheerders in Intune.

#### <a name="list-of-dep-devices-associated-with-a-profile---5012045----"></a>Lijst met DEP-apparaten die zijn gekoppeld aan een profiel<!-- 5012045  -->
U kunt nu een lijst met pagina’s bekijken met geautomatiseerde DEP-apparaten van Apple (Device Enrollment Program) die zijn gekoppeld aan een profiel. U kunt in de lijst zoeken vanaf elke pagina in de lijst. Als u deze lijst wilt bekijken, gaat u naar **Intune** > **Apparaatinschrijving** > **Apple-inschrijving** > **Tokens voor het inschrijvingsprogramma** > kies een token > **Profielen** > kies een profiel > **Toegewezen apparaten** (onder**Monitor**).

#### <a name="ios-user-enrollment-in-preview---4817900---"></a>Inschrijving van iOS-gebruikers in Preview<!-- 4817900 -->
De iOS 13.1-release van Apple bevat Gebruikersinschrijving, een nieuwe vorm van Lightweight Management voor iOS-apparaten. Deze functie kan worden gebruikt in plaats van Apparaatinschrijving of Automatische apparaatinschrijving (voorheen Device Enrollment Program) voor apparaten die persoonlijk eigendom zijn. De Preview-versie van Intune ondersteunt deze functieset zodat u het volgende kunt doen:

- Gebruikersinschrijving richten op gebruikersgroepen.
- Eindgebruikers de mogelijkheid geven om te kiezen tussen het lichtere Gebruikersregistratie of het sterkere Apparaatinschrijving bij het inschrijven van hun apparaten.

Vanaf 24 september 2019, met de release van iOS 13.1, worden deze updates geïmplementeerd voor alle klanten. We verwachten dat dit proces eind volgende week is voltooid.

Van toepassing op:

- iOS 13.1 en hoger

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Apparaatbeheer

#### <a name="more-android-fully-managed-support---3464667-4631425-4631440-5227935-4062195-----"></a>Meer ondersteuning voor volledig beheerde Android-apparaten<!-- 3464667, 4631425, 4631440, 5227935, 4062195   -->
We hebben de volgende ondersteuning toegevoegd voor volledig beheerde Android-apparaten:

- SCEP-certificaten voor volledig beheerde Android-apparaten zijn beschikbaar voor certificaatverificatie op apparaten die worden beheerd als Apparaateigenaar. SCEP-certificaten worden al ondersteund op Werkprofiel-apparaten.  Met SCEP-certificaten voor Apparaateigenaar kunt u het volgende doen: <!-- 5227935 -->
    - SCEP-profiel maken onder de DO-sectie van Android Enterprise
    - SCEP-certificaten koppelen aan een DO-Wi-Fi-profiel voor verificatie
    - SCEP-certificaten koppelen aan DO-VPN-profielen voor verificatie
    - SCEP-certificaten koppelen aan DO-e-mailprofielen voor verificatie (via AppConfig)
- Systeem-apps worden ondersteund op Android Enterprise-apparaten. Voeg in Intune een Android Enterprise-systeem-app toe door **Client-apps** > **Apps** > **Toevoegen** te selecteren. Selecteer in de lijst **App-type** het type **Android Enterprise-systeem-app**. Zie [Android Enterprise-systeem-apps toevoegen aan Microsoft Intune](../apps/apps-ae-system.md) voor meer informatie. <!-- 4062195 -->
- In **Apparaatcompatibiliteit** > **Android Enterprise** > **Apparaateigenaar**, kunt u nalevingsbeleid maken waarmee het niveau van SafetyNet-attestation wordt ingesteld.   <!-- 4631425 -->
- Op volledig beheerde Android Enterprise-apparaten worden de Mobile Threat Defense-providers ondersteund. In **Apparaatcompatibiliteit** > **Android Enterprise** > **Apparaateigenaar**, kunt u een acceptabel bedreigingsniveau kiezen. <!-- 4631440 --> In [Android Enterprise-instellingen om te markeren of apparaten wel of niet conform zijn met behulp van Intune](../protect/compliance-policy-create-android-for-work.md#device-owner) worden de huidige instellingen vermeld.
- De Microsoft Launcher-app kan nu op volledig beheerde Android Enterprise-apparaten worden geconfigureerd via app-configuratiebeleid, voor een gestandaardiseerde eindgebruikerservaring op volledig beheerde apparaten. De Microsoft Launcher-app kan worden gebruikt om uw Android-apparaat te personaliseren. Door de app te gebruiken samen met een Microsoft-account of werk/school-account hebt u toegang tot uw agenda, documenten en recente activiteiten in uw gepersonaliseerde feed. <!-- 5334044 -->

We zijn blij te kunnen aankondigen dat met deze update Intune-ondersteuning voor volledig beheerde Android Enterprise-apparaten nu algemeen beschikbaar is.

Van toepassing op:

- Volledig beheerde Android Enterprise-apparaten

#### <a name="send-custom-notifications-to-a-single-device---4928910---"></a>Aangepaste meldingen verzenden naar één apparaat<!-- 4928910 -->
U kunt nu één apparaat selecteren en vervolgens een externe apparaatactie gebruiken om [een aangepaste melding te verzenden naar alleen dit specifieke apparaat](../remote-actions/custom-notifications.md#send-a-custom-notification-to-a-single-device).

#### <a name="wipe-and-passcode-reset-actions-arent-available-for-ios-devices-that-are-enrolled-by-using-user-enrollment---4950491---"></a>Acties voor wissen en het opnieuw instellen van wachtwoordcode zijn niet beschikbaar voor iOS-apparaten die zijn ingeschreven met behulp van gebruikersinschrijving<!-- 4950491 -->
Gebruikersinschrijving is een nieuw type inschrijving voor Apple-apparaten. Wanneer u apparaten inschrijft met behulp van gebruikersinschrijving, zijn de externe acties voor wissen en het opnieuw instellen van wachtwoordcode niet beschikbaar voor dergelijke apparaten.

#### <a name="intune-support-for-ios-13-and-macos-catalina-devices---4665317---"></a>Intune-ondersteuning voor iOS 13- en macOS Catalina-apparaten<!-- 4665317 -->
Intune biedt nu ondersteuning voor iOS 13- en macOS Catalina-apparaten.
Zie de [blogpost Microsoft Intune-ondersteuning voor iOS 13 en iPadOS](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Support-for-iOS-13-and-iPadOS/ba-p/861998) voor meer informatie.

#### <a name="intune-support-for-ipados-and-ios-131-devices--5439574--"></a>Intune-ondersteuning voor iPadOS- en iOS 13.1-apparaten<!--5439574-->
Intune biedt nu ondersteuning voor iPadOS- en iOS 13.1-apparaten. Lees [dit blogbericht](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Support-for-iOS-13-1-and-iPadOS/ba-p/873094) voor meer informatie.


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Apparaatbeveiliging

#### <a name="bitlocker-support-for-client-driven-recovery-password-rotation----3444125---"></a>BitLocker-ondersteuning voor clientgestuurde rotatie van herstelwachtwoorden<!--  3444125 -->
Gebruik Intune Endpoint Protection om [Clientgestuurde rotatie van herstelwachtwoorden](../protect/endpoint-protection-windows-10.md#windows-encryption) voor BitLocker te configureren voor apparaten waarop Windows-versie 1909 of later wordt uitgevoerd.

Met deze instelling wordt een clientgestuurde vernieuwing van het herstelwachtwoord geïnitieerd na het herstellen van het OS-station (hetzij met behulp van bootmgr of WinRE) en het ontgrendelen van het herstelwachtwoord op een vaste-gegevensstations. Met deze instelling wordt het specifieke gebruikte herstelwachtwoord vernieuwd. Andere niet-gebruikte wachtwoorden in het volume blijven ongewijzigd. Raadpleeg de BitLocker CSP-documentatie voor [ConfigureRecoveryPasswordRotation](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) voor meer informatie.

#### <a name="tamper-protection-for-windows-defender-antivirus---4705448----------"></a>Manipulatiebeveiliging voor Windows Defender Antivirus<!-- 4705448        -->
Gebruik Intune om *Manipulatiebeveiliging* te beheren voor Windows Defender Antivirus. U vindt de [instelling voor Manipulatiebeveiliging](../protect/endpoint-protection-windows-10.md#microsoft-defender-security-center) in de groep Microsoft Defender-beveiligingscentrum wanneer u apparaatconfiguratieprofielen gebruikt voor Windows 10 Endpoint Protection. U kunt Manipulatiebeveiliging instellen op *Ingeschakeld* om beperkingen voor manipulatiebeveiliging in te schakelen, op *Uitgeschakeld* om deze uit te schakelen, of op *Niet geconfigureerd* om de huidige configuratie van apparaten te behouden.  

Zie [Wijzigingen in beveiligingsinstellingen voorkomen met Manipulatiebeveiliging](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection) voor meer informatie over Manipulatiebeveiliging in de Windows-documentatie.

#### <a name="advanced-settings-for-windows-defender-firewall-are-now-generally-available----5317392---------"></a>Geavanceerde instellingen voor Windows Defender Firewall zijn nu algemeen beschikbaar<!--  5317392       -->  
De [aangepaste Windows Defender-firewallregels voor eindpuntbescherming](../protect/endpoint-protection-configure.md#add-custom-firewall-rules-for-windows-10-devices) die u configureert als onderdeel van een apparaatconfiguratieprofiel, zijn niet meer in de openbare preview-versie en zijn algemeen beschikbaar (GA).  U kunt deze regels gebruiken om inkomend en uitgaand gedrag voor toepassingen, netwerkadressen en poorten op te geven. Deze regels zijn in juli uitgebracht als een openbare preview-versie. 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="intune-user-interface-update--tenant-status-dashboard---5273210----"></a>Update voor Intune-gebruikersinterface – dashboard Tenantstatus<!-- 5273210  -->
De gebruikersinterface voor het dashboard Tenantstatus is bijgewerkt om deze in lijn te brengen met de stijlen van de Azure-gebruikersinterface. Zie [Tenantstatus](../tenant-status.md) voor meer informatie.


### <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer

#### <a name="scope-tags-now-support-terms-of-use-policies---2358863----"></a>Bereiktags bieden nu ondersteuning voor beleid voor gebruiksvoorwaarden<!-- 2358863  -->
U kunt nu [bereiktags](scope-tags.md) toewijzen aan beleid voor gebruiksvoorwaarden. Hiervoor gaat u naar **Intune** > **Apparaatinschrijving** > **Voorwaarden** > kies een item in de lijst > **Eigenschappen** > **Bereiktags** > kies een bereiktag.

<!-- ########################## -->
## <a name="august-2019"></a>Augustus 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Appbeheer

#### <a name="control-ios-app-uninstall-behavior-at-device-unenrollment---3504144-----"></a>Gedrag van het verwijderen van iOS-apps beheren bij het uitschrijven van apparaten<!-- 3504144   -->
Beheerders kunnen beheren of een app wordt verwijderd of behouden op een apparaat wanneer het apparaat wordt uitgeschreven op het niveau van een gebruikers- of apparaatgroep. 

#### <a name="categorize-microsoft-store-for-business-apps---3926922---"></a>Microsoft Store voor Bedrijven-apps categoriseren<!-- 3926922 -->
U kunt Microsoft Store voor Bedrijven-apps categoriseren. Selecteer hiertoe **Intune** > **Client-apps** > **Apps** > selecteer een Microsoft Store voor Bedrijven-app > **App-gegevens** > **Categorie**. Wijs een categorie toe in de vervolgkeuzelijst.

#### <a name="customized-notifications-for-microsoft-intune-app-users---4843354----"></a>Aangepaste meldingen voor gebruikers van Microsoft Intune-apps<!-- 4843354  -->
De Microsoft Intune-app voor Android ondersteunt nu het weergeven van aangepaste pushmeldingen. Dit is in lijn met de ondersteuning die recent is toegevoegd in de bedrijfsportal-apps voor iOS en Android. Zie [Aangepaste meldingen verzenden in Intune](../remote-actions/custom-notifications.md) voor meer informatie.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Apparaatconfiguratie

### <a name="configure-microsoft-edge-settings-using-administrative-templates-for-windows-10-and-newer---5228061---"></a>Microsoft Edge-instellingen configureren met beheersjablonen voor Windows 10 en nieuwer<!-- 5228061 -->
Op Windows 10- en nieuwere apparaten kunt u beheersjablonen maken om instellingen voor groepsbeleid te configureren in Intune. In deze update kunt u instellingen configureren die van toepassing zijn op Microsoft Edge-versie 77 en nieuwer.

Zie [Windows 10-sjablonen gebruiken voor het configureren van instellingen voor groepsbeleid in Intune](../configuration/administrative-templates-windows.md) voor meer informatie over deze beheersjalbonen.

Van toepassing op:

- Windows 10 en nieuwer (Windows RS4+)

#### <a name="new-features-for-android-enterprise-dedicated-devices-in-multi-app-mode---3755304-3041943-3041946-----"></a>Nieuwe functies voor aan Android Enterprise toegewezen apparaten in de modus voor meerdere apps<!-- 3755304 3041943 3041946   -->

U kunt in Intune functies en instellingen beheren in een kioskstijl op uw toegewezen Android Enterprise-apparaten (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** voor platform > **Alleen apparaateigenaar, Apparaatbeperkingen** voor profieltype).

In deze update worden de volgende functies toegevoegd:

- **Toegewezen apparaten** > Meerdere apps **:** de **Virtuele startknop** kan worden weergegeven door op het apparaat te vegen of op het scherm te zweven zodat gebruikers deze kunnen verplaatsen.
- Met **Toegewezen apparaten** > **Meerdere apps**: **Zaklamp-toegang** kunnen gebruikers de zaklamp gebruiken. 
- **Toegewezen apparaten** > Meerdere apps **:** met **volumeregeling van media** kunnen gebruikers het mediavolume van het apparaat beheren met behulp van een schuifregelaar. 
- **Toegewezen apparaten** > Meerdere apps **:**  **een schermbeveiliging inschakelen**, een aangepaste afbeelding uploaden en bepalen wanneer de schermbeveiliging wordt weergegeven.

Ga naar [Android Enterprise-apparaatinstellingen om beperkingsfuncties toe te staan of te beperken met behulp van Intune](../configuration/device-restrictions-android-for-work.md#dedicated-device-settings) om de huidige instellingen te zien.

Van toepassing op:

- Toegewezen Android Enterprise-apparaten

#### <a name="new-app-and-configuration-profiles-for-android-enterprise-fully-managed-devices---3574215-3574238-3574235-3574232-----"></a>Nieuwe app- en configuratieprofielen voor volledig beheerde Android Enterprise-apparaten<!-- 3574215 3574238 3574235 3574232   -->
Met behulp van profielen kunt u instellingen configureren die VPN-, e-mail-en Wi-Fi-instellingen toepassen op uw (volledig beheerde) Android Enterprise-apparaten in zakelijk eigendom. In deze update kunt u het volgende doen:

- [App-configuratiebeleid](../apps/app-configuration-policies-use-android.md) gebruiken voor het implementeren van e-mail instellingen van Outlook, Gmail en Nine Work.
- Apparaatconfiguratieprofielen gebruiken om [instellingen voor vertrouwde basiscertificaten](../protect/certificates-configure.md) te implementeren.
- Apparaatconfiguratieprofielen gebruiken om instellingen voor [VPN](../configuration/vpn-settings-android-enterprise.md) en [Wi-Fi](../configuration/wi-fi-settings-android-enterprise.md) te implementeren.

> [!IMPORTANT]
> Met deze functie gebruiken gebruikers hun gebruikersnaam en wachtwoord voor verificatie bij VPN-, Wi-Fi- en e-mailprofielen. Op dit moment is verificatie op basis van certificaten niet beschikbaar.

Van toepassing op:  
- Android Enterprise-apparaten in zakelijk eigendom (volledig beheerd)

#### <a name="control-the-apps-files-documents-and-folders-that-open-when-users-sign-in-to-macos-devices--3914202-----"></a>De apps, bestanden, documenten en mappen beheren die worden geopend wanneer gebruikers zich aanmelden bij macOS-apparaten<!--3914202   -->
U kunt functies inschakelen en configureren op macOS-apparaten (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **macOS** voor platform > **Apparaatfuncties** voor profieltype). 

In deze update is er een nieuwe instelling voor Aanmeldingsitems om te bepalen welke apps, bestanden, documenten en mappen worden geopend wanneer een gebruiker zich aanmeldt bij het geregistreerde apparaat. 

Ga naar [Instellingen van apparaatfuncties voor macOS in Intune](../configuration/macos-device-features-settings.md) om de huidige instellingen te zien.

Van toepassing op:  
- macOS

#### <a name="deadlines-replace-engaged-restart-settings-for-windows-update-rings---4464404----------"></a>Deadlines vervangen instellingen voor gepland opnieuw opstarten voor Windows-updateringen<!-- 4464404        -->
In lijn met recente [wijzigingen in Windows-onderhoud](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903#servicing) ondersteunen de Windows 10-updateringen van Intune nu [instellingen voor deadlines](../protect/windows-update-settings.md). *Deadlines* bepalen wanneer door een apparaat functie-en beveiligingsupdates worden geïnstalleerd.  Op apparaten waarop Windows 10 1903 of hoger wordt uitgevoerd, vervangen *deadlines* de configuraties voor *gepland opnieuw opstarten*.  In de toekomst gaan *deadlines* ook *gepland opnieuw opstarten* in eerdere versies van Windows 10 vervangen.  

Wanneer u geen *deadlines*configureert, blijven apparaten de instellingen voor *gepland opnieuw opstarten* gebruiken. In een toekomstige update gaat Intune ondersteuning voor gepland opnieuw opstarten echter stopzetten.  

Plan het *gebruik* van deadlines voor al uw Windows 10-apparaten. Nadat de instellingen voor *deadlines* zijn ingesteld, kunt u de Intune-configuraties voor *gepland opnieuw opstarten* wijzigen in Niet geconfigureerd. Als deze zijn ingesteld op Niet geconfigureerd, stopt Intune het beheer van deze instellingen op apparaten, maar worden de laatste configuraties voor de instelling niet van het apparaat verwijderd. Daarom blijven de laatste configuraties die zijn ingesteld voor *gepland opnieuw opstarten* actief en in gebruik op apparaten totdat deze instellingen worden gewijzigd door een andere methode dan Intune. Later, wanneer de apparaatversie van Windows verandert of wanneer Intune ondersteuning voor *deadlines* uitbreidt naar de Windows-versie van het apparaat, gaat het apparaat de nieuwe instellingen gebruiken, die al aanwezig zijn.

#### <a name="support-for-multiple-microsoft-intune-certificate-connectors-----4704642--------"></a>Ondersteuning voor meerdere Microsoft Intune Certificate Connectors<!--   4704642      -->
InTune biedt nu ondersteuning voor installatie en gebruik van meerdere [Microsoft Intune Certificate Connectors voor PKCS-bewerkingen](../protect/certficates-pfx-configure.md). Deze wijziging ondersteunt taakverdeling en hoge beschikbaarheid van de connector. Elke connectorinstantie kan certificaataanvragen van Intune verwerken.  Als er geen connector beschikbaar is, blijven andere connectors aanvragen verwerken.

Als u meerdere connectors wilt gebruiken, hoeft u geen upgrade uit te voeren naar de nieuwste versie van de connectorsoftware.  

#### <a name="new-settings-and-changes-to-existing-settings-to-restrict-features-on-ios-and-macos-devices---4867699-4867709-----"></a>Nieuwe instellingen en wijzigingen in bestaande instellingen om functies op iOS-en macOS-apparaten te beperken<!-- 4867699 4867709   -->
U kunt profielen maken om instellingen te beperken op apparaten waarop iOS en macOS worden uitgevoerd (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** of **macOS** voor platform > **Apparaatbeperkingen**). Deze update bevat onder andere de volgende functies:

- Gebruik in **macOS** > **Apparaatbeperkingen** > **Cloud en opslag** de nieuwe **Handoff**-instellingen om te blokkeren dat gebruikers werk starten op een macOS-apparaat en blijven werken op een ander macOS- of iOS-apparaat.

  Als u de huidige instellingen wilt zien, gaat u naar [macOS-apparaatinstellingen voor het toestaan of beperken van functies met Intune](../configuration/device-restrictions-macos.md).

- Er zijn enkele wijzigingen in **iOS** > **Apparaatbeperkingen**:

  - **Ingebouwde apps** > **Zoek mijn iPhone (alleen onder supervisie)** : nieuwe instelling waarmee deze functie wordt geblokkeerd in de 'Zoek mijn'-appfunctie. 
  - **Ingebouwde apps** > **Zoek mijn vrienden (alleen onder supervisie)** : nieuwe instelling waarmee deze functie wordt geblokkeerd in de 'Zoek mijn'-appfunctie. 
  - **Draadloos** > **Wijziging van Wi-Fi-status(alleen onder supervisie)** : nieuwe instelling die voorkomt dat gebruikers Wi-Fi in- of uitschakelen op het apparaat.
  - **Toetsenbord en woordenboek** > **QuickPath (alleen onder supervisie)** : nieuwe instelling die de QuickPath-functie blokkeert.
  - **Cloud en opslag**: de naam van **Voortzetting van activiteit** is gewijzigd in **Handoff**.

  Als u de huidige instellingen wilt zien, gaat u naar [iOS-apparaatinstellingen voor het toestaan of beperken van functies met Intune](../configuration/device-restrictions-ios.md).

Van toepassing op:  
- macOS 10.15 of hoger
- iOS 13 en hoger

#### <a name="some-unsupervised-ios-device-restrictions-will-become-supervised-only-with-the-ios-130-release---4867809-----"></a>Sommige iOS-apparaatbeperkingen zonder supervisie worden pas met de release van iOS 13.0 onder supervisie geplaatst<!-- 4867809   -->
In deze update zijn sommige instellingen alleen van toepassing op apparaten met supervisie met de release van iOS 13.0. Als deze instellingen zijn geconfigureerd en toegewezen aan apparaten zonder supervisie vóór de iOS 13.0-release, worden de instellingen nog steeds toegepast op deze apparaten zonder supervisie. Ze zijn ook nog steeds van toepassing nadat de apparaten zijn bijgewerkt naar iOS 13.0. Deze beperkingen worden verwijderd op apparaten zonder supervisie waarvan een back-up is gemaakt en die zijn hersteld.

Deze instellingen omvatten:

- App Store, documenten bekijken, gamen
  - App Store
  - Expliciete muziek-, podcast- of nieuwsinhoud op iTunes
  - Game Center-vrienden toevoegen
  - Games voor meerdere spelers
- Ingebouwde apps
  - Camera
    - FaceTime
  - Safari
    - Automatisch doorvoeren
- Cloud en opslag
  - Back-up naar iCloud
  - ICloud-documentsynchronisatie blokkeren
  - Synchronisatie van iCloud-sleutelhanger blokkeren

Als u de huidige instellingen wilt zien, gaat u naar [iOS-apparaatinstellingen voor het toestaan of beperken van functies met Intune](../configuration/device-restrictions-ios.md).

Van toepassing op:  
- iOS 13.0 en hoger

#### <a name="improved-device-status-for-macos-filevault-encryption---4944983-----------"></a>Verbeterde apparaatstatus voor macOS FileVault-versleuteling<!-- 4944983         -->
We hebben een aantal van de [statusberichten](../protect/encryption-monitor.md#device-encryption-status) voor FileVault-versleuteling op macOS-apparaten bijgewerkt.

#### <a name="some-windows-defender-antivirus-scan-settings-in-the-reporting-show-a-failed-status---5119229---"></a>Sommige scaninstellingen voor Windows Defender Antivirus geven in de rapporten de status Mislukt weer<!-- 5119229 -->
In Intune kunt u beleidsregels maken om Windows Defender Antivirus te gebruiken voor het scannen van uw Windows 10-apparaten (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** voor platform > **Apparaatbeperkingen** voor profieltype > **Windows Defender Antivirus**). De rapporten **Tijd waarop een dagelijkse snelle scan moet worden uitgevoerd** en **Type systeemscan dat moet worden uitgevoerd** bevatten de status Mislukt, terwijl het in werkelijkheid de status Geslaagd was. 

In deze update is dit opgelost. De instellingen **Tijd waarop een dagelijkse snelle scan moet worden uitgevoerd** en **Type systeemscan dat moet worden uitgevoerd** geven nu de status Geslaagd weer wanneer de scans met succes zijn uitgevoerd en geven de status Mislukt weer als de instellingen niet kunnen worden toegepast.

Zie [Apparaatinstellingen van Windows 10 (en hoger) voor het toestaan of beperken van functies met Intune](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus) voor meer informatie over de instellingen van Windows Defender Antivirus.

### <a name="zebra-technologies-is-a-supported-oem-for-oemconfig-on-android-enterprise-devices---4843713---"></a>Zebra Technologies is een ondersteunde OEM voor OEMConfig op Android Enterprise-apparaten<!-- 4843713 -->
In Intune kunt u apparaatconfiguratieprofielen maken, en instellingen toepassen op Android Enterprise-apparaten met behulp van OEMConfig (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** voor platform > **OEMConfig** voor profieltype).

In deze update is Zebra Technologies een ondersteunde OEM (Original Equipment Manufacturer) voor OEMConfig. Zie [Android Enterprise-apparaten gebruiken en beheren met OEMConfig](../configuration/android-oem-configuration-overview.md) voor meer informatie over OEMConfig.

Van toepassing op:  
- Android Enterprise


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="default-scope-tags---3702875----"></a>Standaardbereiktags<!-- 3702875  -->
Er is nu een nieuwe ingebouwde standaardbereiktag beschikbaar. Alle niet-getagde Intune-objecten die bereiktags ondersteunen, worden automatisch toegewezen aan de standaardbereiktag. De **standaard**bereiktag wordt toegevoegd aan alle bestaande roltoewijzingen om pariteit met de beheerderservaring te behouden. Als u niet wilt dat een beheerder Intune-objecten met de standaardbereiktag ziet, verwijdert u de standaardbereiktag uit de roltoewijzing. Deze functie is vergelijkbaar met de functie voor beveiligingsbereiken in Configuration Manager. Zie [RBAC en bereiktags gebruiken voor gedistribueerde IT](scope-tags.md) voor meer informatie.

#### <a name="android-enrollment-device-administrator-support---4869749-----"></a>Ondersteuning voor inschrijving van Android-apparaatbeheerder<!-- 4869749   -->
De optie voor inschrijving van Android-apparaatbeheerders is toegevoegd aan de inschrijvingspagina voor Android (**Intune** > **Apparaatinschrijving** > **Android-inschrijving**). Android-apparaatbeheerders worden nog steeds standaard ingeschakeld voor alle tenants.  Zie [Inschrijving van Android-apparaatbeheerders](../enrollment/android-enroll-device-administrator.md) voor meer informatie.

#### <a name="skip-more-screens-in-setup-assistant---4877451----"></a>Meer schermen in de Configuratieassistent overslaan <!--4877451  -->
U kunt Device Enrollment Program-profielen instellen om de volgende schermen van de Configuratieassistent over te slaan:
- Voor iOS
    - Uiterlijk
    - Express-taal
    - Voorkeurstaal
    - Migratie van apparaat naar apparaat
- Voor macOS
    - Schermtijd
    - Touch ID instellen

Zie [Een Apple-inschrijvingsprofiel maken voor iOS ](../enrollment/device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) en [Een Apple-inschrijvingsprofiel maken voor macOS ](../enrollment/device-enrollment-program-enroll-macos.md#create-an-apple-enrollment-profile) voor meer informatie over het aanpassen van de Configuratieassistent.

#### <a name="add-a-user-column-to-the-autopilot-device-csv-upload-process---3823054---"></a>Een gebruikerskolom toevoegen aan het CSV-uploadproces van het Autopilot-apparaat<!-- 3823054 -->
U kunt nu een gebruikerskolom toevoegen aan de CSV-upload voor Autopilot-apparaten. Zo kunt u gebruikers bulksgewijs toewijzen op het moment dat u het CSV-bestand importeert. Zie [Windows-apparaten in Intune inschrijven met Windows Autopilot](../enrollment/enrollment-autopilot.md) voor meer informatie.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Apparaatbeheer

#### <a name="configure-automatic-device-clean-up-time-limit-down-to-30-days--4231059----"></a>De tijdslimiet voor het automatisch opschonen van apparaten verkorten tot 30 dagen<!--4231059  -->
U kunt de tijdslimiet voor automatische opschoning van apparaten instellen op 30 dagen (in plaats van de vorige limiet van 90 dagen) na de laatste aanmelding. Als u dit wilt doen, gaat u naar **intune** > **apparaten** > regels voor het opschonen**van**apparaten**instellen** > .

#### <a name="build-number-included-on-android-device-hardware-page---4461910-----"></a>Buildnummer opgenomen op de hardwarepagina van het Android-apparaat<!-- 4461910   -->
Een nieuw item op de hardwarepagina voor elk Android-apparaat bevat het buildnummer van het besturingssysteem van het apparaat. Zie [Apparaatdetails weergeven in Intune](../remote-actions/device-inventory.md) voor meer informatie.

<!-- ########################## -->
## <a name="july-2019"></a>Juli 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Appbeheer

#### <a name="customized-notifications-for-users-and-groups---16766574------------"></a>Aangepaste meldingen voor gebruikers en groepen<!-- 16766574          -->
Verzend aangepaste pushmeldingen vanaf de bedrijfsportaltoepassing naar gebruikers met iOS- en Android-apparaten die u met Intune beheert. Deze mobiele pushmeldingen zijn zeer goed met vrije tekst aan te passen en kunnen voor elk doeleinde worden gebruikt. U kunt ze voor verschillende gebruikersgroepen in uw organisatie gebruiken. Zie [aangepaste meldingen](../remote-actions/custom-notifications.md) voor meer informatie.

#### <a name="googles-device-policy-controller-app---3041950----"></a>App Device Policy Controller van Google<!-- 3041950  -->
De app Managed Home Screen biedt nu toegang tot de app Android Device Policy van Google. De app Managed Home Screen is een aangepast startprogramma dat wordt gebruikt voor apparaten die bij Intune zijn ingeschreven als toegewezen Android Enterprise-apparaat (AE) op basis van de kioskmodus voor meerdere apps. U kunt de app Android Device Policy openen of gebruikers naar de app leiden voor ondersteuning en foutopsporing. De opstartmogelijkheid is beschikbaar op het moment dat het apparaat wordt ingeschreven en wordt gekoppeld aan Managed Home Screen. Er zijn geen extra installaties nodig voor het gebruik van deze functionaliteit.

#### <a name="outlook-protection-settings-for-ios-and-android-devices---3212619---"></a>Outlook-beveiligingsinstellingen voor iOS- en Android-apparaten<!-- 3212619 -->
U kunt nu de algemene configuratie-instellingen voor apps en gegevensbeveiliging configureren voor Outlook voor iOS en Android met behulp van besturingselementen voor eenvoudig Intune-beheer zonder apparaatregistratie. De algemene instellingen voor het configureren van apps bieden pariteit met de instellingen die beheerders kunnen inschakelen bij het beheren van Outlook voor iOS en Android op geregistreerde apparaten. Zie [Deploying Outlook for iOS and Android app configuration settings](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune) (Configuratie-instellingen voor apps implementeren voor Outlook voor iOS en Android) voor meer informatie over instellingen in Outlook.


#### <a name="managed-home-screen-and-managed-settings-icons---4918107---"></a>Pictogrammen Managed Home Screen en Beheerde instellingen<!-- 4918107 -->
Het app-pictogram Managed Home Screen en het pictogram **Beheerde instellingen** zijn bijgewerkt. De app Managed Home Screen wordt alleen gebruikt voor apparaten die bij Intune zijn ingeschreven als toegewezen Android Enterprise-apparaat (AE) en die worden uitgevoerd in de kioskmodus voor meerdere apps. Zie [De app Microsoft Managed Home Screen voor Android Enterprise configureren](../apps/app-configuration-managed-home-screen-app.md) voor meer informatie over de app Managed Home Screen.

#### <a name="android-device-policy-on-android-enterprise-dedicated-devices---4918136---"></a>Android Device Policy op toegewezen Android Enterprise-apparaten<!-- 4918136 -->
U kunt de toepassing Android Device Policy openen vanuit het scherm voor het opsporen van fouten in de app Managed Home Screen. De app Managed Home Screen wordt alleen gebruikt voor apparaten die bij Intune zijn ingeschreven als toegewezen Android Enterprise-apparaat (AE) en die worden uitgevoerd in de kioskmodus voor meerdere apps. Zie [De app Microsoft Managed Home Screen voor Android Enterprise](../apps/app-configuration-managed-home-screen-app.md) voor meer informatie.

#### <a name="ios-company-portal-updates---3902931---"></a>Updates voor de iOS-bedrijfsportal<!-- 3902931 -->
De naam van uw bedrijf in prompts van iOS-app-beheer vervangt de huidige tekst 'i.manage.microsoft.com'. Gebruikers zien bijvoorbeeld hun bedrijfsnaam in plaats van 'i.manage.microsoft.com' wanneer ze een iOS-app willen installeren vanuit de bedrijfsportal of wanneer ze beheer van de app toestaan. Dit wordt de komende dagen voor alle klanten uitgebracht.

#### <a name="aad-and-app-on-android-enterprise-devices---3574267---"></a>AAD en APP op Android Enterprise-apparaten<!-- 3574267 -->
Bij het onboarden van volledig beheerde Android Enterprise-apparaten registreren gebruikers zich tijdens de eerste installatie van hun nieuwe apparaat (of hun apparaat die naar de fabrieksinstellingen is teruggezet) voortaan bij Azure Active Directory (AAD). Voor een volledig beheerd apparaat was het voorheen zo dat de gebruiker de Microsoft Intune-app na voltooiing van de installatie handmatig moest starten om AAD-registratie te starten. Als de gebruiker nu na de initiële installatie op de startpagina van het apparaat terechtkomt, wordt het apparaat ingeschreven en geregistreerd.

Naast de AAD-updates worden beleidsregels voor Intune-app-beveiliging (APP) voortaan ondersteund op volledig beheerde Android Enterprise-apparaten. Deze functionaliteit wordt beschikbaar tijdens de implementatie. Zie [Beheerde Google Play-apps toevoegen aan Android Enterprise-apparaten met Intune](../apps/apps-add-android-for-work.md) voor meer informatie.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910-eeready------"></a>Toepasselijkheidsregels gebruiken bij het maken van Windows 10-apparaatconfiguratieprofielen <!-- 2549910 eeready    -->

U kunt configuratieprofielen voor een Windows 10-apparaat maken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10** als platform > **Toepasbaarheidsregels**). In deze update kunt u een **toepassingsregel** maken, zodat het profiel alleen van toepassing is op een specifieke editie of versie. U maakt bijvoorbeeld een profiel waarmee bepaalde BitLocker-instellingen worden ingeschakeld. Als u het profiel toevoegt, gebruikt u een toepassingsregel zodat het profiel alleen van toepassing is op apparaten met Windows 10 Enterprise.

Zie [Toepasbaarheidsregels](../configuration/device-profile-create.md#applicability-rules) om een toepasbaarheidsregel toe te voegen.

Van toepassing op: Windows 10 en hoger

#### <a name="use-tokens-to-add-device-specific-information-in-custom-profiles-for-ios-and-macos-devices---3330008----"></a>Tokens gebruiken om apparaatspecifieke informatie toe te voegen aan aangepaste profielen voor iOS- en macOS-apparaten<!-- 3330008  -->
U kunt aangepaste profielen op iOS- en macOS-apparaten gebruiken om instellingen en functies te configureren die niet zijn ingebouwd in Intune (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **IOS** of **macOS** als platform > **Aangepast** voor profieltype). In deze update kunt u tokens toevoegen aan uw `.mobileconfig`-bestanden om apparaatspecifieke informatie toe te voegen. U kunt bijvoorbeeld `Serial Number: {{serialnumber}}` toevoegen aan uw configuratiebestand om het serienummer van het apparaat weer te geven.

Zie [Aangepaste iOS-instellingen](../configuration/custom-settings-ios.md) of [Aangepaste macOS-instellingen](../configuration/custom-settings-macos.md) als u een aangepast profiel wilt maken.

Van toepassing op:
- iOS
- macOS

#### <a name="new-configuration-designer-when-creating-an-oemconfig-profile-for-android-enterprise---3712769-----"></a>Nieuwe configuratieontwerper bij het maken van een OEMConfig-profiel voor Android Enterprise<!-- 3712769   -->
U kunt in Intune een apparaatconfiguratieprofiel maken dat gebruikmaakt van een OEMConfig-app (Apparaatconfiguratie > Profielen > Profiel maken > Android Enterprise als platform > OEMConfig als profieltype). Wanneer u dit doet, wordt er een JSON-editor geopend met een sjabloon en waarden die u kunt wijzigen. 

Deze update bevat een versie van Configuratieontwerper met een verbeterde gebruikerservaring, waarin in de app ingesloten details worden weergegeven, waaronder titels, beschrijvingen en meer. De JSON-editor is nog steeds beschikbaar en toont wijzigingen die u aanbrengt in Configuratieontwerper.

Als u de huidige instellingen wilt bekijken, gaat u naar [Android Enterprise-apparaten gebruiken en beheren met OEMConfig](../configuration/android-oem-configuration-overview.md).

Van toepassing op: Android Enterprise

#### <a name="updated-ui-for-configuring-windows-hello---4089576--------------"></a>Bijgewerkte gebruikersinterface voor het configureren van Windows Hello<!-- 4089576            -->
De console waar u [Intune kunt configureren voor het gebruik van Windows Hello voor Bedrijven](../protect/windows-hello.md) is bijgewerkt. Alle configuratie-instellingen zijn nu beschikbaar in hetzelfde deelvenster van de console waar u ondersteuning voor Windows Hello inschakelt.

#### <a name="intune-powershell-sdk---4924113---"></a>Intune PowerShell SDK<!-- 4924113 --> 
De Intune PowerShell SDK, die ondersteuning biedt voor de Intune API via Microsoft Graph, is bijgewerkt naar versie 6.1907.1.0. De SDK ondersteunt nu het volgende:
- Werkt met Azure Automation.
- Ondersteunt leesbewerkingen ter verificatie voor alleen apps. 
- Ondersteunt beschrijvende namen als aliassen.
- Voldoet aan de naamgevingsconventies voor PowerShell. Specifiek is parameter `PSCredential` (in cmdlet `Connect-MSGraph`) gewijzigd in `Credential`.
- Ondersteunt het handmatig opgeven van de waarde van de `Content-Type`-header bij gebruik van cmdlet `Invoke-MSGraphRequest`.

Zie [PowerShell SDK for Microsoft Intune Graph API](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune) (PowerShell SDK voor Microsoft Intune Graph API) voor meer informatie.

#### <a name="manage-filevault-for-macos----3858502--4557986--1210104----"></a>FileVault voor macOS beheren<!--  3858502 + 4557986 + 1210104  -->
U kunt Intune gebruiken voor het [beheren van FileVault-versleuteling van sleutels voor macOS-apparaten](../protect/encrypt-devices.md). Gebruik een configuratieprofiel voor apparaten met eindpuntbeveiliging als u een apparaat wilt versleutelen.

De ondersteuning voor FileVault omvat het versleutelen van niet-versleutelde apparaten, borgstelling van de persoonlijke herstelsleutel voor apparaten, automatische of handmatige rotatie van persoonlijke versleutelingssleutels en het ophalen van sleutels voor uw zakelijke apparaten. Eindgebruikers kunnen ook de website van de bedrijfsportal gebruiken om de persoonlijke herstelsleutel voor hun versleutelde apparaten op te halen.

Het versleutelingsrapport is aangevuld met [informatie over FileVault](../protect/encryption-monitor.md) en informatie over BitLocker, zodat u alle gegevens over de apparaatversleuteling op één plek kunt bekijken.

### <a name="new-office-windows-and-onedrive-settings-in-windows-10-administrative-templates----3510695---"></a>Nieuwe instellingen voor Office, Windows en OneDrive in Windows 10-beheersjablonen <!-- 3510695 -->

In Intune kunt u beheersjablonen maken die het on-premises beheer van het groepsbeleid nabootsen (**Apparaatbeheer** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** als platform > **Beheersjabloon** als profieltype).

Deze update bevat meer instellingen voor Office, Windows en OneDrive die u aan uw sjablonen kunt toevoegen. Met deze nieuwe instellingen kunt u nu meer dan 2500 instellingen configureren die voor 100% op de cloud gebaseerd zijn.

Zie [Windows 10-sjablonen gebruiken voor het configureren van instellingen voor groepsbeleid in Intune](../configuration/administrative-templates-windows.md) voor meer informatie over deze functie.

Van toepassing op: Windows 10 en hoger

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="updates-for-enrollment-restrictions---2871968---"></a>Updates voor inschrijvingsbeperkingen<!-- 2871968 -->
Inschrijvingsbeperkingen voor nieuwe tenants zijn bijgewerkt, zodat Android Enterprise-werkprofielen standaard worden toegestaan. Bestaande tenants worden niet gewijzigd. Als u Android Enterprise-werkprofielen wilt gebruiken, moet u [uw Intune-account koppelen aan uw beheerde Google Play-account](../enrollment/connect-intune-android-enterprise.md).

#### <a name="ui-updates-for-apple-enrollment-and-enrollment-restrictions--4089575-4089579----"></a>UI-updates voor Apple-inschrijvingen en inschrijvingsbeperkingen<!--4089575, 4089579  -->
De volgende twee processen maken gebruik van een gebruikersinterface in wizardstijl:
- Inschrijving van Apple-apparaten. Zie [iOS-apparaten automatisch inschrijven met het Device Enrollment Program van Apple](../enrollment/device-enrollment-program-enroll-ios.md) voor meer informatie.
- Inschrijvingsbeperkingen maken. Zie [Inschrijvingsbeperkingen instellen](../enrollment/enrollment-restrictions-set.md) voor meer informatie.

#### <a name="handling-pre-configuration-of-corporate-device-identifiers-for-android-q-devices---4711509-----"></a>Voorbereiding van de configuratie van bedrijfsapparaat-id's voor Android Q-apparaten<!-- 4711509   -->
In Android Q (v10) verwijdert Google de mogelijkheid voor MDM-agents om op Android-apparaten met verouderd beheer (apparaatbeheerder) informatie over de apparaat-id te verzamelen.  Intune bevat een functie waarmee IT-beheerders [vooraf een lijst met serienummers of IMEI's kunnen configureren](../enrollment/corporate-identifiers-add.md#identify-corporate-owned-devices-with-imei-or-serial-number) om deze apparaten automatisch aan te merken als bedrijfseigendom. Deze functie werkt niet voor Android Q-apparaten die door een apparaatbeheerder worden beheerd.  Ongeacht of het serienummer of IMEI voor het apparaat wordt geüpload, wordt dit tijdens de inschrijving bij Intune altijd als een persoonlijk apparaat beschouwd.  U kunt het eigendom na de inschrijving handmatig overzetten naar het bedrijf.  Dit is alleen van invloed op nieuwe inschrijvingen. Bestaande ingeschreven apparaten worden hierdoor niet beïnvloed.  Android-apparaten die worden beheerd met werkprofielen, worden door deze wijziging niet beïnvloed en blijven werken zoals ze dit momenteel doen.  Ook kunnen Android Q-apparaten die als apparaatbeheerder zijn ingeschreven, niet langer een serienummer of IMEI als apparaateigenschappen rapporteren in de Intune-console.

#### <a name="icons-have-changed-for-android-enterprise-enrollments-work-profile-dedicated-devices-and-fully-managed-devices---4977730---"></a>Voor Android Enterprise zijn enkele pictogrammen gewijzigd (werkprofiel, toegewezen apparaten en volledig beheerde apparaten)<!-- 4977730 -->
De pictogrammen voor Android Enterprise-inschrijvingsprofielen zijn gewijzigd. Als u de nieuwe pictogrammen wilt zien, gaat u naar **Intune** > **Inschrijving** > **Android-inschrijving** > en kijkt u onder **Inschrijvingsprofielen**.

#### <a name="windows-diagnostic-data-collection-change---4113859---"></a>Wijziging in het verzamelen van diagnostische gegevens<!-- 4113859 -->
De standaardwaarde voor het verzamelen van diagnostische gegevens is gewijzigd voor apparaten met Windows 10, versie 1903 en hoger. Vanaf Windows 10 1903 is het verzamelen van diagnostische gegevens standaard ingeschakeld. Diagnostische gegevens van Windows zijn vitale technische gegevens van Windows-apparaten over het apparaat en over hoe Windows en gerelateerde software worden uitgevoerd. Zie [Diagnostische gegevens van Windows in uw organisatie configureren](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization) voor meer informatie. Autopilot-apparaten worden ook ingeschreven voor 'volledige' telemetrie, tenzij dit anders is ingesteld in het Autopilot-profiel met [System/AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry).

#### <a name="windows-autopilot-reset-removes-the-devices-primary-user---4156123---"></a>Met Windows Autopilot opnieuw instellen wordt de primaire gebruiker van het apparaat verwijderd<!-- 4156123 -->
Wanneer Autopilot opnieuw instellen op een apparaat wordt gebruikt, wordt de primaire gebruiker van het apparaat verwijderd. De volgende gebruiker die zich na het opnieuw instellen aanmeldt, wordt ingesteld als primaire gebruiker. Deze functie wordt de komende dagen voor alle klanten uitgebracht.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Apparaatbeheer

#### <a name="improve-device-location---3855417----"></a>Lokalisatie van apparaat verbeteren<!-- 3855417  -->
U kunt inzoomen op de exacte coördinaten van een apparaat met behulp van de actie **Apparaat zoeken**. Zie [Verloren iOS-apparaten zoeken](../remote-actions/device-locate.md) voor meer informatie over het zoeken naar verloren iOS-apparaten.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Apparaatbeveiliging

#### <a name="advanced-settings-for-windows-defender-firewall--public-preview----1311949-------"></a>Geavanceerde instellingen voor Windows Defender Firewall (openbare preview)<!--  1311949     -->  
Gebruik Intune voor het beheren van [aangepaste firewallregels als onderdeel van een configuratieprofiel voor een apparaat](../protect/endpoint-protection-configure.md#add-custom-firewall-rules-for-windows-10-devices) voor eindpuntbeveiliging in Windows 10. Met regels kunt u inkomend en uitgaand gedrag voor toepassingen, netwerkadressen en poorten opgeven. 

#### <a name="updated-ui-for-managing-security-baselines---4091125-------"></a>Bijgewerkte gebruikersinterface voor het beheren van beveiligingsbasislijnen<!-- 4091125     -->
[Maken en bewerken](../protect/security-baselines.md#create-the-profile) in de Intune-console voor de beveiligingsbasislijnen is bijgewerkt. De wijzigingen zijn onder andere:

Een eenvoudigere wizardstijl die op één blade is samengevoegd. binnen één blade. In dit nieuwe ontwerp wordt niet langer gebruikgemaakt van meerdere blades, waarbij IT-professionals in meerdere, afzonderlijke deelvensters moeten inzoomen.  
U kunt nu toewijzingen maken als onderdeel van het maken en bewerken. Hierdoor hoeft u later geen basislijnen meer toe te voegen. Er is een samenvatting van de instellingen toegevoegd die u kunt bekijken voordat u een nieuwe basislijn maakt of een bestaande regel bewerkt. Tijdens het bewerken toont de samenvatting alleen de lijst met items die zijn ingesteld binnen de categorie met eigenschappen die worden bewerkt.

<!-- ########################## -->
## <a name="june-2019"></a>Juni 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Appbeheer

#### <a name="configure-which-browser-is-allowed-to-link-to-organization-data---3145939---"></a>Configureren welke browser een koppeling met organisatiegegevens mag maken<!-- 3145939 -->
Met beleidsregels voor Intune-app-beveiliging (APP) op Android- en iOS-apparaten kunt u webkoppelingen van een organisatie overbrengen naar een specifieke browser buiten Intune Managed Browser of Microsoft Edge.  Zie [Wat is beveiligingsbeleid voor apps?](../apps/app-protection-policy.md) voor meer informatie over APP.

#### <a name="all-apps-page-identifies-onlineoffline-microsoft-store-for-business-apps--4089647---"></a>Op de pagina Alle apps worden online/offline Microsoft Store voor zakelijke apps geïdentificeerd<!--4089647 -->
De pagina **Alle apps** bevat nu labels voor het identificeren van MSFB-apps (Microsoft Store for Business) als online- of offline-apps. Elke MSFB-app bevat nu een achtervoegsel voor **Online** of **Offline**. De pagina met app-details bevat ook informatie over het **licentietype** en **ondersteunt de installatie van apparaatcontext** (alleen offline gelicentieerde apps).

#### <a name="company-portal-app-on-windows-shared-devices--4393553---"></a>Bedrijfsportal-app op gedeelde Windows-apparaten<!--4393553 -->
Gebruikers hebben nu toegang tot de Bedrijfsportal-app op gedeelde Windows-apparaten. Eindgebruikers krijgen het label **Gedeeld** op de apparaattegel te zien. Dit geldt voor versie 10.3.45609.0 en hoger van de Windows Bedrijfsportal-app.

#### <a name="view-all-installed-apps-from-new-company-portal-web-page---4224326---"></a>Alle geïnstalleerde apps weergeven op de nieuwe webpagina van de bedrijfsportal<!-- 4224326 -->
De nieuwe pagina **Geïnstalleerde apps** van de website van de bedrijfsportal geeft alle beheerde apps (zowel vereiste als beschikbare) weer die op het apparaat van een gebruiker zijn geïnstalleerd. Naast het type toewijzing kunnen gebruikers de uitgever van de app, de publicatiedatum en de huidige installatiestatus weergeven. Als u geen apps voor uw gebruikers verplicht of beschikbaar hebt gesteld, zien zij het bericht dat er geen bedrijfs-apps zijn geïnstalleerd. Ga naar de [website van de bedrijfsportal](https://portal.manage.microsoft.com) en klik op **Geïnstalleerde apps** om de nieuwe pagina op het web te zien.  

#### <a name="new-view-lets-app-users-see-all-managed-apps-installed-on-device---2352913---"></a>In de nieuwe weergave kunnen app-gebruikers alle beheerde apps zien die op het apparaat zijn geïnstalleerd<!-- 2352913 -->  
De bedrijfsportal voor Windows toont nu alle beheerde apps (zowel vereiste als beschikbare) die op het apparaat van een gebruiker zijn geïnstalleerd. Gebruikers kunnen ook geprobeerde en in behandeling zijnde app-installaties weergeven met de huidige status ervan. Als u geen apps voor uw gebruikers verplicht of beschikbaar hebt gesteld, zien zij het bericht dat er geen bedrijfs-apps zijn geïnstalleerd. Ga naar het navigatievenster in de bedrijfsportal en selecteer **Apps** > **Geïnstalleerde apps** om de nieuwe weergave weer te geven.

#### <a name="new-features-in-microsoft-intune-app"></a>Nieuwe functies in Microsoft Intune-app
We hebben nieuwe functies toegevoegd aan de Microsoft Intune-app (preview) voor Android. Gebruikers op volledig beheerde Android-apparaten kunnen nu:  

* De apparaten weergeven en beheren die zij hebben ingeschreven via de Intune-bedrijfsportal of de Microsoft Intune-app.
* Contact opnemen met hun organisatie voor ondersteuning.
* Feedback naar Microsoft sturen.
* Algemene voorwaarden bekijken als deze zijn ingesteld door hun organisatie.

#### <a name="new-sample-apps-showing-intune-sdk-integration-available-on-github---2653471---"></a>Er zijn nieuwe voorbeeld-apps met Intune SDK-integratie beschikbaar op GitHub<!-- 2653471 -->
Met het GitHub-account msintuneappsdk zijn nieuwe voorbeeldtoepassingen toegevoegd voor iOS (Swift), Android, Xamarin.iOS, Xamarin Forms en Xamarin.Android. Deze apps zijn bedoeld als aanvulling op onze bestaande documentatie en demonstraties van hoe u de Intune APP SDK kunt integreren in uw eigen mobiele apps. Als u als app-ontwikkelaar aanvullende begeleiding bij de Intune SDK nodig hebt, raadpleegt u de volgende gekoppelde voorbeelden:
- [Chatr](https://github.com/msintuneappsdk/Chatr-Sample-Intune-iOS-App): een systeemeigen iOS (Swift)-berichtenapp die gebruikmaakt van de Azure Active Directory Authentication Library (ADAL) voor verificatie via een broker.
- [Taskr](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Android-App): een systeemeigen Android-app voor takenlijsten die gebruikmaakt van ADAL voor verificatie via een broker.
- [Taskr](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Xamarin-Android-Apps): een Xamarin.Android-app voor takenlijsten die gebruikmaakt van ADAL voor verificatie via een broker. Deze opslagplaats bevat ook de Xamarin.Forms-app.
- [Voorbeeld-app voor Xamarin.iOS](https://github.com/msintuneappsdk/sample-intune-xamarin-ios): een barebones Xamarin.iOS-voorbeeld-app.


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="configure-settings-for-kernel-extensions-on-macos-devices---2043024---"></a>Instellingen voor kernelextensies configureren op macOS-apparaten<!-- 2043024 -->
U kunt op macOS-apparaten een apparaatconfiguratieprofiel maken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** kies > **macOS** als platform). Deze update bevat een nieuwe groep instellingen waarmee u kernelextensies op uw apparaten kunt configureren en gebruiken. U kunt specifieke extensies toevoegen, maar ook alle uitbreidingen van een specifieke partner of ontwikkelaar toestaan.

Zie [overzicht van de kernelextensies](../configuration/kernel-extensions-overview-macos.md) en [instellingen voor de kernelextensie](../configuration/kernel-extensions-settings-macos.md) voor meer informatie over deze functie.

Van toepassing op: macOS 10.13.2 en hoger

#### <a name="apps-from-the-store-only-setting-for-windows-10-devices-includes-more-configuration-options---2697002---"></a>Instelling Alleen apps van de Store voor Windows 10-apparaten bevat meer configuratieopties<!-- 2697002 -->
Wanneer u een apparaatbeperkingsprofiel voor Windows-apparaten maakt, kunt u de instelling **Alleen apps van de Store** gebruiken, zodat gebruikers alleen apps van Windows App Store installeren (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** voor platform > **Apparaatbeperkingen** voor profieltype). In deze update wordt deze instelling uitgebreid om meer opties te ondersteunen.

Als u de nieuwe instelling wilt zien, gaat u naar [Apparaatinstellingen voor Windows 10 (en hoger) voor het toestaan of beperken van functies](../configuration/device-restrictions-windows-10.md#app-store).

Van toepassing op: Windows 10 en hoger

#### <a name="deploy-multiple-zebra-mobility-extensions-device-profiles-to-a-device-same-user-group-or-same-devices-group---4089955---"></a>Meerdere apparaatprofielen voor Zebra-mobiliteitsextensies op een apparaat of voor dezelfde gebruikersgroep of groep apparaten implementeren<!-- 4089955 -->
U kunt in Intune Zebra-mobiliteitsextensies (MX) gebruiken in een apparaatconfiguratieprofiel om instellingen aan te passen voor Zebra-apparaten die niet in Intune zijn ingebouwd. Op dit moment kunt u één profiel op één apparaat implementeren. In deze update kunt u meerdere profielen implementeren voor het volgende:
- Dezelfde gebruikersgroep
- Dezelfde groep apparaten
- Eén apparaat

In [Use and manage Zebra devices with Zebra Mobility Extensions in Microsoft Intune](../configuration/android-zebra-mx-overview.md) (Zebra-apparaten gebruiken en beheren met Zebra Mobility Extensions in Microsoft Intune) ziet u hoe u MX in Intune gebruikt.

Van toepassing op: Android

#### <a name="some-kiosk-settings-on-ios-devices-are-set-using-block-replacing-allow---4404075----"></a>Sommige kioskinstellingen op iOS-apparaten worden ingesteld met behulp van Blokkeren, waardoor Toestaan wordt vervangen<!-- 4404075  -->
Wanneer u een apparaatbeperkingsprofiel maakt op iOS-apparaten (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype > **Kiosk**), stelt u de **automatisch vergrendeling**, **schakelaar voor het belsignaal**, **schermrotatie**, **schermsluimerknop** en **volumeknoppen** in.

In deze update gaat het om de waarden **Blokkeren** (blokkeert de functie) of **Niet geconfigureerd** (staat de functie toe). Als u de instellingen wilt bekijken, gaat u naar [iOS-apparaatinstellingen voor het toestaan of beperken van functies](../configuration/device-restrictions-ios.md#kiosk).

Van toepassing op: iOS

#### <a name="use-face-id-for-password-authentication-on-ios-devices---4490704---"></a>Face ID voor wachtwoordverificatie op iOS-apparaten gebruiken<!-- 4490704 -->
Wanneer u een apparaatbeperkingsprofiel voor iOS-apparaten maakt, kunt u een vingerafdruk als wachtwoord gebruiken. In deze update is met de instellingen voor vingerafdrukwachtwoorden ook gezichtsherkenning mogelijk (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** als platform > **Apparaatbeperkingen** als profieltype > **Wachtwoord**). Als gevolg hiervan zijn de volgende instellingen gewijzigd:

- **Ontgrendelen met vingerafdruk** is nu **Touch ID en Face ID ontgrendelen**.
- **Wijziging van vingerafdruk (alleen onder supervisie)** is nu **Aanpassing van Touch ID en Face ID (alleen onder supervisie)** .

Face ID is beschikbaar in iOS 11.0 en hoger. Als u de instellingen wilt bekijken, gaat u naar [iOS-apparaatinstellingen voor het toestaan of beperken van functies met behulp van Intune](../configuration/device-restrictions-ios.md#password).

Van toepassing op: iOS

#### <a name="restricting-gaming-and-app-store-features-on-ios-devices-is-now-dependent-on-ratings-region---4593948---"></a>Het beperken van gaming- en App Store-functies op iOS-apparaten is nu afhankelijk van de regio voor restricties<!-- 4593948 -->
Op iOS-apparaten kunt u functies toestaan of beperken met betrekking tot gaming, de App Store en het weergeven van documenten (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype > **App Store, documentweergave, gaming**). U kunt ook de classificatieregio kiezen, zoals de Verenigde Staten.

In deze update wordt de functie **Apps** een onderliggend element van **Regio voor restricties** en is deze afhankelijk van **Regio voor restricties**. Als u de instellingen wilt bekijken, gaat u naar [iOS-apparaatinstellingen voor het toestaan of beperken van functies met behulp van Intune](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming).

Van toepassing op: iOS

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="windows-autopilot-support-for-hybrid-azure-ad-join---4809146--"></a>Ondersteuning voor Windows Autopilot voor Hybrid Azure AD Join<!-- 4809146-->
Windows Autopilot voor bestaande apparaten ondersteunt nu Hybrid Azure AD Join (naast de bestaande ondersteuning voor Azure AD Join). Is van toepassing op Windows 10-apparaten, versie 1809 en hoger. Zie [Windows Autopilot voor bestaande apparaten](https://docs.microsoft.com/windows/deployment/windows-autopilot/existing-devices) voor meer informatie.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Apparaatbeheer

#### <a name="see-the-security-patch-level-for-android-devices---4461911---"></a>Het niveau van de beveiligingspatch voor Android-apparaten bekijken<!-- 4461911 -->
U kunt nu het niveau van de beveiligingspatch voor Android-apparaten bekijken. Kies hiervoor **Intune** > **Apparaten** > **Alle apparaten** > kies een apparaat > **Hardware**.
Het patchniveau wordt weergegeven in het gedeelte **Besturingssysteem**.

#### <a name="assign-scope-tags-to-all-managed-devices-in-a-security-group---3173810---"></a>Bereiktags toewijzen aan alle beheerde apparaten in een beveiligingsgroep<!-- 3173810 -->
U kunt nu bereiktags toewijzen aan een beveiligingsgroep waarbij ook alle apparaten in de beveiligingsgroep aan die bereiktags worden gekoppeld. De bereiktag wordt ook aan alle apparaten in deze groepen toegewezen. De bereiktags die worden ingesteld met deze functie, vervangen de bereiktags die zijn ingesteld met de huidige stroom voor apparaatbereiktags. Zie [RBAC en bereiktags gebruiken voor gedistribueerde IT](scope-tags.md) voor meer informatie.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Apparaatbeveiliging

#### <a name="use-keyword-search-with-security-baselines------"></a>Zoekopdrachten met trefwoorden gebruiken met Beveiligingsbasislijnen<!--  -->
Wanneer u [beveiligingsbasislijnprofielen](../protect/security-baselines.md#create-the-profile) maakt of bewerkt, kunt u trefwoorden opgeven in de nieuwe *zoekbalk* om de beschikbare groepen instellingen te filteren op degene die de zoekcriteria bevatten.

#### <a name="the-security-baselines-feature-is-now-generally-available---3785395---"></a>De functie Beveiligingsbasislijnen is nu algemeen beschikbaar<!-- 3785395 -->
Voor de functie **Beveiligingsbasislijnen** is de previewfase beëindigd. De functie is nu algemeen beschikbaar.  Dit betekent dat de functie gereed is voor gebruik in productie. De afzonderlijke basislijnsjablonen blijven mogelijk echter wel in de previewfase, en worden geëvalueerd en op basis van hun eigen planningen algemeen uitgebracht.

#### <a name="the-mdm-security-baseline-template-is-now-generally-available---3794072-4217151--3534649---"></a>De sjabloon MDM-beveiligingsbasislijn is algemeen beschikbaar<!-- 3794072, 4217151,  3534649 -->
Voor de sjabloon MDM-beveiligingsbasislijn is de previewfase beëindigd. De functie is nu algemeen beschikbaar. De algemeen beschikbare sjabloon wordt geïdentificeerd als **MDM-beveiligingsbasislijn voor mei 2019**.  Dit is een nieuwe sjabloon en geen upgrade van de previewversie.  Voor een nieuwe sjabloon moet u de [instellingen die deze bevat](../protect/security-baseline-settings-mdm.md), controleren en vervolgens nieuwe profielen maken om de sjabloon voor uw apparaat te implementeren. Andere beveiligingsbasislijnsjablonen blijven mogelijk in de previewfase. Zie [Beschikbare beveiligingsbasislijnen](../protect/security-baselines.md#available-security-baselines) voor een lijst met beschikbare basislijnen.  

De nieuwe sjabloon *MDM-beveiligingsbasislijn voor mei 2019* bevat de twee instellingen die onlangs zijn aangekondigd in het artikel In ontwikkeling:  
- Vergrendeling boven: Door spraak geactiveerde apps vanaf een vergrendeld scherm  
- DeviceGuard: Gebruik Beveiliging op basis van virtualisatie (VBS) als de apparaten de volgende keer opnieuw worden opgestart.  

Voor de *MDM-beveiligingsbasislijn voor mei 2019* geldt dat er ook een aantal nieuwe instellingen is toegevoegd, andere eruit zijn verwijderd en de standaardwaarde van één instelling is gewijzigd. Zie **wat is er gewijzigd in de nieuwe sjabloon** voor een uitgebreide lijst met de wijzigingen van de previewversie (nu algemeen uitgebracht).

#### <a name="security-baseline-versioning---3194322---"></a>Versiebeheer van beveiligingsbasislijnen<!-- 3194322 -->
Beveiligingsbasislijnen voor versiebeheer van de ondersteuning voor Intune. Nu er nieuwe versies van elke beveiligingsbasislijn worden uitgebracht, kunt u dankzij deze ondersteuning uw bestaande beveiligingsbasislijnprofielen bijwerken voor gebruik van de nieuwere basislijnversie, zonder dat u zelf opnieuw een geheel nieuwe basislijn hoeft te maken en te implementeren. Daarnaast kunt u in de Intune-console informatie bekijken over elke basislijn, zoals het aantal afzonderlijke profielen die gebruikmaken van de basislijn, hoeveel verschillende basislijnversies er door uw profielen worden gebruikt en wanneer de meest recente release van een bepaalde beveiligingbasislijn is geweest.  Zie **Beveiligingsbasislijnen** voor meer informatie.

#### <a name="the-use-security-keys-for-sign-in-setting-has-moved---4501151---"></a>De instelling Beveiligingssleutels gebruiken voor aanmelden is verplaatst<!-- 4501151 -->
De instelling voor apparaatconfiguratie voor identiteitsbeveiliging met de naam **Beveiligingssleutels gebruiken voor aanmelden** is niet meer aanwezig als subinstelling van *Windows Hello voor Bedrijven configureren*. Het is nu een instelling op het hoogste niveau die altijd beschikbaar is, ook als u het gebruik van Windows Hello voor Bedrijven niet inschakelt. Zie [Identity Protection](../protect/identity-protection-windows-settings.md) voor meer informatie.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer

#### <a name="new-permissions-for-assigned-group-admins---4504437-----"></a>Nieuwe machtigingen voor toegewezen groepsbeheerders<!-- 4504437   -->
De in Intune ingebouwde rol School Administrator bevat nu machtigingen voor maken, lezen, bijwerken en verwijderen (CRUD-machtigingen) voor beheerde apps. Deze update betekent dat als u in Intune for Education bent toegewezen als groepsbeheerder, u voortaan het iOS MDM-pushcertificaat, iOS MDM-servertokens en iOS VPP-tokens kunt maken, weergeven, bijwerken en verwijderen, in combinatie met [alle bestaande machtigingen die u hebt](https://docs.microsoft.com/intune-education/group-admin-delegate#group-admin-permissions). Als u een van deze acties wilt uitvoeren, gaat u naar **Tenantinstellingen** > **iOS-apparaatbeheer**.  

#### <a name="applications-can-use-the-graph-api-to-call-read-operations-without-user-credentials---4655885---"></a>Toepassingen kunnen gebruikmaken van de Graph API om leesbewerkingen aan te roepen zonder gebruikersreferenties<!-- 4655885 -->
Toepassingen kunnen met app-identiteiten Intune Graph API-leesbewerkingen aanroepen, zonder dat er gebruikersreferenties nodig zijn. Zie [Working with Intune in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0) (Werken met intune in Microsoft Graph) voor meer informatie over het openen van de Microsoft Graph API voor Intune.

#### <a name="apply-scope-tags-to-microsoft-store-for-business-apps---4392555---"></a>Bereiktags toepassen op Microsoft Store voor Bedrijven-apps<!-- 4392555 -->
U kunt voortaan bereiktags toepassen op Microsoft Store voor Bedrijven-apps. Zie [Use role-based access control and scope tags for distributed IT](scope-tags.md) (Op rollen gebaseerd toegangsbeheer (RBAC) en bereiktags gebruiken voor gedistribueerde IT) voor meer informatie over bereiktags.

<!-- ########################## -->
## <a name="may-2019"></a>Mei 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Appbeheer

#### <a name="reporting-for-potentially-harmful-apps-on-android-devices---4223162---"></a>Rapportage voor mogelijk schadelijke apps op Android-apparaten<!-- 4223162 -->
Intune biedt nu aanvullende rapportagegegevens over mogelijk schadelijke apps op Android-apparaten. 

#### <a name="windows-company-portal-app---3316993---"></a>Windows-bedrijfsportal-app<!-- 3316993 -->
De Windows-bedrijfsportal-app heeft nu een nieuwe pagina met het label **Apparaten**. Op de pagina **Apparaten** staan de eindgebruikers van alle ingeschreven apparaten. Gebruikers zien deze wijziging in de bedrijfsportal als ze versie 10.3.4291.0 of hoger gebruiken. Voor informatie over het configureren van de bedrijfsportal-app, ziet u [How to configure the Microsoft Intune Company Portal app](../apps/company-portal-app.md) (De app Microsoft Intune-bedrijfsportal configureren).

#### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation---1927359----"></a>Intune-beleid werkt de verificatiemethode en installatie van de Bedrijfsportal-app bij<!-- 1927359  -->
Intune biedt geen ondersteuning meer voor de Bedrijfsportal wanneer deze handmatig door eindgebruikers uit de appstore wordt geïnstalleerd op apparaten die al met behulp van Configuratieassistent zijn ingeschreven via een van de Apple-registratiemethoden voor bedrijfsapparaten. Deze wijziging is alleen relevant wanneer u tijdens de inschrijving verifieert met Apple Setup Assistant. Deze wijziging is eveneens alleen van invloed op iOS-apparaten die zijn ingeschreven via:  
* Apple Configurator
* Apple Business Manager
* Apple School Manager
* Apple Device Enrollment Program (DEP)

Als gebruikers de Bedrijfsportal-app installeren uit de App Store en vervolgens apparaten via de app proberen te registreren, treedt er een foutmelding op. Er wordt van uitgegaan dat deze apparaten de Bedrijfsportal alleen gebruiken wanneer het automatisch door Intune tijdens de registratie is gepusht. Inschrijvingsprofielen in Intune in de Azure-portal worden bijgewerkt zodat u kunt opgeven hoe apparaten zich verifiëren en hoe zij de Bedrijfsportal-app ontvangen. Als u wilt dat uw DEP-apparaatgebruikers de Bedrijfsportal hebben, moet u uw voorkeuren in een inschrijvingsprofiel opgeven. 

Bovendien wordt het scherm **Uw apparaat identificeren** in de Bedrijfsportal-app van iOS binnenkort niet meer gebruikt. Beheerders die voorwaardelijke toegang willen inschakelen of bedrijfs-apps willen implementeren moeten daarom het DEP-inschrijvingsprofiel bijwerken. Deze vereiste geldt alleen als de DEP-inschrijving wordt geverifieerd met Configuratieassistent. In dat geval moet u de Bedrijfsportal naar het apparaat pushen. Hiervoor kiest u **Intune** > **Apparaatinschrijving** > **Apple-inschrijving** > **Tokens voor het inschrijfprogramma** > kies een token > **Profielen** > kies een profiel > **Eigenschappen** > stel **Bedrijfsportal installeren** in op **Ja**.

Als u de Bedrijfsportal wilt installeren op DEP-apparaten die al zijn ingeschreven, gaat u naar Intune > Client-apps en pusht u de app als beheerde app met app-configuratiebeleid. 

#### <a name="configure-how-end-users-update-a-line-of-business-lob-app-using-an-app-protection-policy---3568384---"></a>Configureren hoe eindgebruikers een LOB-app (Line-Of-Business) bijwerken met behulp van een beveiligingsbeleid voor apps<!-- 3568384 -->
U kunt nu configureren waar uw eindgebruikers een bijgewerkte versie van een LOB-app (Line-Of-Business) kunnen downloaden. Eindgebruikers zien deze functie in het dialoogvenster **minimale app-versie** van de functie voor voorwaardelijk starten, waarin eindgebruikers wordt gevraagd om bij te werken naar een minimale versie van de LOB-app. U moet deze informatie opgeven als onderdeel van uw het beveiligingsbeleid voor uw LOB-app (APP). Deze functie is beschikbaar voor iOS en Android. Voor iOS vereist deze functie dat de app is geïntegreerd (of verpakt met behulp van het wrapping-programma) met de Intune SDK voor iOS versie 10.0.7 of hoger. Voor Android vereist deze functie de meest recente versie van de Bedrijfsportal. Als u wilt configureren hoe een eindgebruiker een LOB-app kan bijwerken, moet er configuratiebeleid voor een beheerde app worden verzonden naar de app met de sleutel `com.microsoft.intune.myappstore`. De verzonden waarde bepaalt uit welke store de eindgebruiker de app kan downloaden. Als de app wordt geïmplementeerd via de Bedrijfsportal-app, moet de waarde `CompanyPortal` zijn. Voor iedere andere store moet u een volledige URL opgeven.

#### <a name="intune-management-extension-powershell-scripts---3734186----"></a>Intune-beheerextensie voor PowerShell-scripts<!-- 3734186  -->
U kunt configureren dat PowerShell-scripts worden uitgevoerd met de beheerdersbevoegdheden van de gebruiker op het apparaat. Zie [PowerShell-scripts op Windows 10-apparaten gebruiken in Intune](../apps/intune-management-extension.md) en [Win32 app management](../apps/app-management.md) (Beheer van Win32-apps) voor meer informatie.

#### <a name="android-enterprise-app-management---4459905---"></a>Beheer van Android Enterprise-apps<!-- 4459905 -->
Om het eenvoudiger te maken voor IT-beheerders om Android Enterprise-beheer te configureren en gebruiken, voegt Intune automatisch vier veelgebruikte Android Enterprise apps toe aan de beheerconsole van Intune. Het betreft de volgende vier Android Enterprise-apps:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)** : wordt gebruikt voor scenario's met volledig beheer door Android Enterprise.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)** : om u aan te melden bij uw accounts als u verificatie in twee stappen gebruikt.
- **[Intune-bedrijfsportal](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)** : wordt gebruikt voor beleidsregels voor app-beveiliging (APP) en werkprofielscenario's van Android Enterprise.
- [Managed Home Screen](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise): wordt gebruikt voor toegewezen/kiosk-scenario's van Android Enterprise.

Eerder moesten IT-beheerders deze apps als onderdeel van de installatie handmatig zoeken en goedkeuren in de [beheerde Google Play Store](https://play.google.com/store/apps). Met deze wijziging worden deze eerdere handmatige stappen weggenomen om het gemakkelijker en sneller te maken voor klanten om Android Enterprise-beheer te gebruiken.

Deze vier apps worden automatisch toegevoegd aan de lijst met Intune-apps van beheerders op het moment dat ze hun Intune-tenant voor het eerst verbinden met de beheerde Google Play Store. Zie [Uw Intune-account verbinden met uw Beheerde Google Play-account](../enrollment/connect-intune-android-enterprise.md) voor meer informatie. Beheerders die hun tenant al hebben verbonden of die al gebruikmaken van Android Enterprise hoeven niets te doen. Zeven dagen na het voltooien van de implementatie van de service-update van mei 2019 zijn deze vier apps automatisch beschikbaar.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune---1533038---"></a>Bijgewerkte PFX-certificaatconnector voor Microsoft Intune<!-- 1533038 -->
We hebben een update uitgebracht voor de [PFX Certificate Connector voor Microsoft Intune](../protect/certficates-pfx-configure.md#whats-new-for-connectors) die een oplossing biedt voor een probleem waarbij bestaande PFX-certificaten steeds opnieuw worden verwerkt. Hierdoor stopt de connector met het verwerken van nieuwe aanvragen.

#### <a name="intune-security-tasks-for-defender-atp-in-public-preview---3208597---"></a>Intune-beveiligingstaken voor Defender ATP (in openbare preview)<!-- 3208597 -->
In de openbare preview-versie kunt u Intune gebruiken voor het beheren van [beveiligingstaken voor Microsoft Defender Advanced Threat Protection (ATP)](../protect/atp-manage-vulnerabilities.md). Door deze integratie met ATP wordt er een op risico's gebaseerde aanpak voor het detecteren, classificeren en oplossen van beveiligingsproblemen en onjuiste configuraties van eindpunten toegevoegd, terwijl er ook minder tijd zit tussen het detecteren en oplossen van beveiligingsproblemen.

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy---3617671-----"></a>Controleren of er zich een TPM-chipset in een nalevingsbeleid voor Windows 10-apparaten bevindt<!-- 3617671   -->
Veel apparaten met Windows 10 en hoger hebben TPM-chipsets (Trusted Platform Module). Deze update bevat een nieuwe nalevingsinstelling die de versie van de TPM-chip in het apparaat controleert.

Deze instelling wordt beschreven in [Instellingen voor nalevingsbeleid voor apparaten met Windows 10 en later](../protect/compliance-policy-create-windows.md#device-security).

Van toepassing op: Windows 10 en hoger

#### <a name="prevent-end-users-from-modifying-their-personal-hotspot-and-disable-siri-server-logging-on-ios-devices---4097904-----"></a>Voorkomen dat gebruikers hun persoonlijke hotspot wijzigen en logboekregistratie van Siri-server op iOS-apparaten uitschakelen<!-- 4097904   -->  
U maakt een profiel met apparaatbeperkingen op het iOS-apparaat (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype). Deze update bevat nieuwe instellingen die u kunt configureren:

- **Ingebouwde apps**: logboekregistratie op de server voor Siri-opdrachten
- **Draadloos**: wijzing van persoonlijke hotspot door gebruiker (alleen onder supervisie)

Als u deze instellingen wilt zien, gaat u naar [ingebouwde app-instellingen voor iOS](../configuration/device-restrictions-ios.md#built-in-apps) en [draadloze instellingen voor iOS](../configuration/device-restrictions-ios.md#wireless).

Van toepassing op: iOS 12.2 en nieuwer

#### <a name="new-classroom-app-device-restriction-settings-for-macos-devices---4097905-----"></a>Nieuwe instellingen voor apparaatbeperkingen voor Klaslokaal-app op macOS-apparaten<!-- 4097905   --> 
U kunt apparaatconfiguratieprofiel voor macOS-apparaten maken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **macOS** voor platform > **Apparaatbeperkingen** voor profieltype). Deze update bevat nieuwe instellingen voor de Classroom-app, de optie om schermopnamen te blokkeren en de optie om de iCloud-fotobibliotheek uit te schakelen.

Als u de huidige instellingen wilt zien, gaat u naar [macOS-apparaatinstellingen voor het toestaan of beperken van functies met Intune](../configuration/device-restrictions-macos.md).

Is van toepassing op: macOS

#### <a name="the-ios-password-to-access-app-store-setting-is-renamed---4557891----"></a>De naam van het iOS-wachtwoord voor toegang tot App Store-instellingen is gewijzigd<!-- 4557891  -->
De naam van de instelling **Wachtwoord voor toegang tot de App Store** is gewijzigd in **iTunes Store-wachtwoord vereisen voor alle aankopen** (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype > **App Store, documenten bekijken, gamen**).

Als u de beschikbare instellingen wilt zien, gaat u naar [App Store, documenten bekijken, gamen](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming).

Van toepassing op: iOS

#### <a name="microsoft-defender-advanced-threat-protection--baseline--preview----3754134---"></a>Microsoft Defender Advanced Threat Protection-basislijn (preview)<!--  3754134 -->
We hebben een preview van een basislijn voor beveiliging toegevoegd voor [Microsoft Defender Advanced Threat Protection](../protect/security-baseline-settings-defender-atp.md)-instellingen. Deze basislijn is beschikbaar als uw omgeving voldoet aan de vereisten voor het gebruik van [Microsoft Defender Advanced Threat Protection](../protect/advanced-threat-protection.md#prerequisites).

#### <a name="outlook-signature-and-biometric-settings-for--ios-and-android-devices---4050557---"></a>Outlook-handtekening en biometrische instellingen voor iOS- en Android-apparaten<!-- 4050557 -->
U kunt nu opgeven of de standaardhandtekening moet worden ingeschakeld in Outlook voor iOS- en Android-apparaten. Bovendien kunt u eventueel toestaan dat gebruikers de biometrische instelling wijzigen in Outlook voor iOS.

#### <a name="network-access-control-nac-support-for-f5-access-for-ios-devices---4500808---"></a>Ondersteuning voor netwerktoegangsbeheer (NAC) voor F5 Access voor iOS-apparaten<!-- 4500808 -->
F5 heeft een update voor BIG-IP 13 uitgebracht waardoor de NAC-functionaliteit is toegestaan voor F5-toegang op iOS in Intune. Om deze functie te gebruiken, moet u ook het volgende doen:

- Werk BIG-IP bij naar 13.1.1.5, vernieuwen. BIG-IP 14 wordt niet ondersteund.
- Integreer BIG-IP met Intune voor NAC. Stappen in [Overzicht: APM configureren voor apparaatpostuurcontroles met eindpuntbeheersystemen](https://techdocs.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html).
- Schakel de instelling **Netwerktoegangsbeheer (NAC) inschakelen** in het VPN-profiel in Intune in.

Ga naar [VPN-instellingen configureren op iOS-apparaten](../configuration/vpn-settings-ios.md) om de beschikbare instelling te zien.

Van toepassing op: iOS

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune---doc-vso-1521237----"></a>Bijgewerkte PFX-certificaatconnector voor Microsoft Intune<!-- doc-vso 1521237  -->  
We hebben een update uitgebracht voor de [PFX-certificaatconnector voor Microsoft Intune](../protect/certficates-pfx-configure.md#whats-new-for-connectors), waardoor de polling-interval wordt verlaagd van 5 minuten naar 30 seconden.


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="autopilot-device-orderid-attribute-name-changed-to-group-tag----4659453---"></a>De kenmerknaam OrderID voor Autopilot-apparaten is gewijzigd in Groepstag <!-- 4659453 -->

Voor een meer intuïtieve benadering is de kenmerknaam **OrderID** voor Autopilot-apparaten gewijzigd in **Groepstag**. Als u CSV's gebruikt voor het uploaden van Autopilot-apparaatgegevens, moet u Groepstag als kolomkop gebruiken en niet OrderID.  

#### <a name="windows-enrollment-status-page-esp-is-now-generally-available---3605348---"></a>Pagina Status van inschrijving is nu algemeen beschikbaar<!-- 3605348 -->
De pagina Status van inschrijving is nu uit preview en algemeen beschikbaar. Raadpleeg [Een pagina voor de status van de inschrijving instellen](../enrollment/windows-enrollment-status.md) voor meer informatie.

#### <a name="intune-user-interface-update---autopilot-enrollment-profile-creation---4593669---"></a>Update van Intune-gebruikersinterface - Autopilot-inschrijvingsprofiel maken<!-- 4593669 -->
De gebruikersinterface voor het maken van een Autopilot-inschrijvingsprofiel is bijgewerkt om deze in lijn te brengen met de stijlen van de Azure-gebruikersinterface. Zie [Een Autopilot-inschrijvingsprofiel maken](../enrollment/enrollment-autopilot.md#create-an-autopilot-deployment-profile) voor meer informatie. Binnenkort worden ook andere Intune-scenario's bijgewerkt naar deze nieuwe stijl voor de gebruikersinterface.

#### <a name="enable-autopilot-reset-for-all-windows-devices---4225665---"></a>Autopilot opnieuw instellen voor alle Windows-apparaten inschakelen<!-- 4225665 -->
Autopilot opnieuw instellen werkt nu voor alle Windows-apparaten, ook als deze niet zijn geconfigureerd voor het gebruik van de pagina Status van inschrijving. Als er tijdens de eerste apparaatregistratie geen pagina voor de status van inschrijving is geconfigureerd voor het apparaat, wordt op het apparaat direct het bureaublad weergegeven na het aanmelden. Het duurt maximaal acht uur totdat de synchronisatie is voltooid en het apparaat als compatibel wordt weergegeven in Intune. Zie [Reset devices with remote Windows Autopilot Reset](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-reset-remote) (Apparaten op afstand opnieuw instellen met Autopilot opnieuw instellen van Windows) voor meer informatie.

#### <a name="exact-imei-format-not-required-when-searching-all-devices--30407680---"></a>Exacte IME-indeling niet vereist bij het zoeken naar alle apparaten<!--30407680 -->
U hoeft geen spaties op te nemen in IMEI-nummers wanneer u zoekt met **Alle apparaten**.

#### <a name="deleting-a-device-in-the-apple-portal-will-be-reflected-in-the-intune-portal--2489996---"></a>Verwijderen van apparaat in de Apple-portal wordt doorgevoerd in de Intune-portal<!--2489996 -->
Als een apparaat wordt verwijderd uit de portal van het Device Enrollment Program van Apple of van Apple Business Manager, wordt het apparaat bij de volgende synchronisatie automatisch verwijderd uit Intune.

### <a name="the-enrollment-status-page-now-tracks-win32-apps---2714451---"></a>Op de pagina Status van inschrijving worden nu Win32-apps bijgehouden<!-- 2714451 -->
Dit is alleen van toepassing op apparaten met Windows 10 versie 1903 en hoger. Raadpleeg [Een pagina voor de status van de inschrijving instellen](../enrollment/windows-enrollment-status.md) voor meer informatie.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Apparaatbeheer

#### <a name="reset-and-wipe-devices-in-bulk-by-using-the-graph-api---3295288---"></a>Apparaten in bulk opnieuw instellen en wissen met behulp van de Graph API<!-- 3295288 -->
U kunt nu in één bulkbewerking tot wel 100 apparaten opnieuw instellen en wissen met behulp van de Graph API.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="the-encryption-report-is-out-of-public-preview---4587546--------"></a>Het rapport Versleuteling is uit openbare preview<!-- 4587546      -->
Het [rapport voor BitLocker- en apparaatversleuteling](../protect/encryption-monitor.md) is nu algemeen beschikbaar en maakt geen deel meer uit van de openbare preview.


<!-- ########################## -->
## <a name="april-2019"></a>April 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Appbeheer
#### <a name="user-experience-update-for-the-company-portal-app-for-ios---2536024---"></a>Update van de gebruikerservaring voor de bedrijfsportal-app voor iOS<!-- 2536024 -->
De startpagina van de bedrijfsportal-app voor iOS-apparaten is opnieuw ontworpen. Door deze wijziging kan de startpagina beter patronen volgen van de iOS-gebruikersinterface en ook een verbeterde zichtbaarheid bieden voor apps en e-Books.

#### <a name="changes-to-company-portal-enrollment-for-ios-12-device-users--3448635---"></a>Wijzigingen in de bedrijfsportal-App-registratie voor gebruikers van iOS-12-apparaten<!--3448635 -->
De schermen en stappen in de bedrijfsportal-app voor iOS-inschrijving zijn bijgewerkt, zodat deze overeenkomen met de wijzigingen in de MDM-inschrijving die zijn uitgebracht in Apple iOS 12.2. In de bijgewerkte werkstroom wordt gebruikers het volgende gevraagd:  

* Safari te openen op de bedrijfsportalwebsite en het beheerprofiel te downloaden voordat zij terugkeren naar de bedrijfsportal-app.  
* De app instellingen te openen voor het installeren van het beheerprofiel op hun apparaat.
* Terug te gaan naar de bedrijfsportal-app om de inschrijving te voltooien.  

Zie [iOS-apparaat inschrijven bij Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) voor de bijgewerkte stappen en schermen voor de inschrijving.

#### <a name="openssl-encryption-for-android-app-protection-policies---3747362---"></a>OpenSSL-versleuteling voor app-beveiligingsbeleid voor Android<!-- 3747362 -->
Intune app-beveiligingsbeleid (APP) op Android-apparaten maakt nu gebruik van een OpenSSL-versleutelingsbibliotheek die compatibel is met FIPS 140-2. Zie de sectie over [versleuteling](../apps/app-protection-policy-settings-android.md#encryption) van [instellingen van app-beveiligingsbeleid voor Android in Microsoft Intune](../apps/app-protection-policy-settings-android.md) voor meer informatie.

#### <a name="enable-win32-app-dependencies---2617348----"></a>Win32-app-afhankelijkheden inschakelen<!-- 2617348  -->
Als beheerder kunt u vereisen dat andere apps worden geïnstalleerd als afhankelijkheden voordat uw Win32-app wordt geïnstalleerd. Op het apparaat moet(e) met name de afhankelijke app(s) worden geïnstalleerd voordat de Win32-app wordt geïnstalleerd. Selecteer in Intune, **Client-apps** > **Apps** > **Toevoegen** om de blade **App toevoegen** weer te geven. Selecteer **Windows-app (Win32)** als **App-type**. Nadat u de app hebt toegevoegd, kunt u **Afhankelijkheden** selecteren om de afhankelijke apps toe te voegen die moeten worden geïnstalleerd voordat de Win32-app kan worden geïnstalleerd. Zie [Intune Standalone - Win32-app-beheer](./../apps/app-management.md) voor meer informatie. 

#### <a name="app-version-installation-information-for-microsoft-store-for-business-apps---3537391-----"></a>Installatie-informatie voor de app-versie voor Microsoft Store voor Bedrijven-apps<!-- 3537391   -->
App-installatierapporten bevatten informatie over de app-versie voor Microsoft Store voor bedrijven-apps. Selecteer in Intune **Client-apps** > **Apps**. Selecteer een **Microsoft Store voor bedrijven-app** en selecteer vervolgens **Installatiestatus apparaat** onder de sectie **Monitor**.

#### <a name="additions-to-win32-apps-requirement-rules---3676883-----"></a>Toevoegingen aan de vereisteregels voor Win32-apps<!-- 3676883   -->
U kunt vereisteregels maken op basis van PowerShell-scripts, registerwaarden en informatie over het bestandssysteem. Selecteer in Intune de optie **Client-apps** > **Apps** > **Toevoegen**. Selecteer vervolgens **Windows-app (Win32)** als **App-type** in de blade **App toevoegen**.  Selecteer **Vereisten** > **Toevoegen** om aanvullende vereisteregels te configureren. Selecteer vervolgens een **Bestandstype**, **Register** of **Script** als **Vereistetype**. Zie [Win32 app-beheer](./../apps/app-management.md) voor meer informatie.

#### <a name="configure-your-win32-apps-to-be-installed-on-intune-enrolled-azure-ad-joined-devices---3695227----"></a>Uw Win32-apps configureren voor een installatie op bij Intune ingeschreven apparaten die met Azure AD zijn gekoppeld<!-- 3695227  -->
U kunt uw Win32-apps toewijzen voor een installatie op bij Intune ingeschreven apparaten die met Azure AD zijn gekoppeld. Zie [Win32-app-beheer](./../apps/app-management.md) voor meer informatie over Win32-apps in Intune.

#### <a name="device-overview-shows-primary-user--3794259----"></a>Overzicht van apparaat geeft de primaire gebruiker weer<!--3794259  -->
In de overzichtspagina van het apparaat ziet u de primaire gebruiker, ook wel de UDA-gebruiker genoemd (UDA: User Device Affinity, gebruikersaffiniteit apparaat). Als u de primaire gebruiker van een apparaat wilt zien, kiest u **Intune** > **Apparaten** > **Alle apparaten** > Een apparaat kiezen. De primaire gebruiker wordt bovenaan de pagina **Overzicht** weergegeven.

#### <a name="additional-managed-google-play-app-reporting-for-android-enterprise-work-profile-devices---4105925----"></a>Aanvullende rapportage van beheerde Google Play-apps voor apparaten met Android Enterprise-werkprofiel<!-- 4105925  -->
Voor beheerde Google Play-apps die op apparaten met Android Enterprise-werkprofiel zijn geïmplementeerd, kunt u het specifieke versienummer van de op een apparaat geïnstalleerde app weergeven. Dit geldt alleen voor vereiste apps.  

#### <a name="ios-third-party-keyboards---4111843-----"></a>iOS-toetsenborden van derden<!-- 4111843   -->
De ondersteuning voor het Intune-app-beveiligingsbeleid (APP) voor de instelling **Toetsenborden van derden** voor iOS wordt beëindigd vanwege een iOS-platformwijziging. U zult deze instelling niet meer kunnen configureren op de Intune-beheerconsole en deze wordt niet meer afgedwongen op de client in de Intune App SDK.


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="updated-certificate-connectors---icm-113304612---"></a>Bijgewerkte certificaatconnectors<!-- ICM 113304612 -->
We hebben updates uitgebracht voor zowel de [Intune-certificaatconnector als de PFX-certificaatconnector voor Microsoft Intune](../protect/certficates-pfx-configure.md#whats-new-for-connectors). Met de nieuwe releases worden verschillende bekende problemen opgelost.

#### <a name="set-login-settings-and-control-restart-options-on-macos-devices---1210083----"></a>Aanmeldingsinstellingen configureren en opties voor opnieuw opstarten beheren op macOS-apparaten<!-- 1210083  -->
U kunt op macOS-apparaten een apparaatconfiguratieprofiel maken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **macOS** kiezen als platform > **Apparaatfuncties** als profieltype). Deze update bevat nieuwe aanmeldingsvensterinstellingen, zoals het weergeven van een aangepaste banner, het kiezen hoe gebruikers zich aanmelden, het weergeven of verbergen van de energie-instellingen enzovoort.

Zie [Instellingen van macOS-apparaatfuncties](../configuration/macos-device-features-settings.md) voor het bekijken van deze instellingen.

#### <a name="configure-wifi-on-android-enterprise-device-owner-dedicated-devices-running-in-multi-app-kiosk-mode--3041940----"></a>Wi-Fi configureren op aan de apparaateigenaar toegewezen Android Enterprise-apparaten die worden uitgevoerd in de kioskmodus voor meerdere apps<!--3041940  -->
U kunt de instellingen voor Android Enterprise-apparaateigenaar inschakelen wanneer deze als toegewezen apparaat in kioskmodus voor meerdere apps wordt uitgevoerd. In deze update kunt u gebruikers in staat stellen om Wi-Fi-netwerken te configureren en ermee verbinding te maken (**Intune** > **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** als platform > **Alleen apparaateigenaar, Apparaatbeperkingen** als profieltype >  **Toegewezen apparaten** > **Kioskmodus**: **Voor meerdere apps** > **Wi-Fi-configuratie**).

Ga naar [Met Android Enterprise-apparaatinstellingen functies toestaan of beperken](../configuration/device-restrictions-android-for-work.md) als u alle configureerbare instellingen wilt bekijken.

Van toepassing op: aan Android Enterprise toegewezen apparaten die worden uitgevoerd in de kioskmodus voor meerdere apps

#### <a name="configure-bluetooth-and-pairing-on-android-enterprise-device-owner-dedicated-devices-running-in-multi-app-kiosk-mode---3041941----"></a>Bluetooth en koppelen configureren op aan apparaateigenaar toegewezen Android Enterprise-apparaten die worden uitgevoerd in de kioskmodus voor meerdere apps<!-- 3041941  -->
U kunt de instellingen voor Android Enterprise-apparaateigenaar inschakelen wanneer deze als toegewezen apparaat in kioskmodus voor meerdere apps wordt uitgevoerd. In deze update kunt u gebruikers toestaan om Bluetooth in te schakelen en via Bluetooth apparaten te koppelen (**Intune** > **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** als platform > **Alleen apparaateigenaar, Apparaatbeperkingen** als profieltype >  **Toegewezen apparaten** > **Kioskmodus**: **Voor meerdere apps** > **Bluetooth-configuratie**).

Ga naar [Met Android Enterprise-apparaatinstellingen functies toestaan of beperken](../configuration/device-restrictions-android-for-work.md) als u alle configureerbare instellingen wilt bekijken.

Van toepassing op: aan Android Enterprise toegewezen apparaten die worden uitgevoerd in de kioskmodus voor meerdere apps

#### <a name="create-and-use-oemconfig-device-configuration-profiles-in-intune---3305883----"></a>OEMConfig-apparaatconfiguratieprofielen in Microsoft Intune maken en gebruiken<!-- 3305883  -->
In deze update biedt Intune ondersteuning voor het configureren van Android Enterprise-apparaten met OEMConfig. U kunt specifiek een apparaatconfiguratieprofiel maken, en instellingen toepassen op Android Enterprise-apparaten met behulp van OEMConfig (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** als platform).

Ondersteuning voor OEM's is momenteel per OEM. Als de gewenste OEMConfig app niet beschikbaar is in de lijst met OEMConfig-apps, neemt u contact op met `IntuneOEMConfig@microsoft.com`.

Ga naar [Android-bedrijfsapparaten met OEMConfig gebruiken en beheren in Microsoft Intune](../configuration/android-oem-configuration-overview.md) voor meer informatie over deze functie.

Van toepassing op: Android Enterprise

#### <a name="windows-update-notifications---3316758-3316782----"></a>Windows Update-meldingen<!-- 3316758, 3316782  -->
We hebben twee *instellingen voor de gebruikerservaring* toegevoegd aan de Windows Update-ringconfiguraties die u vanuit de Intune-console kunt beheren. U kunt nu het volgende doen:
- Gebruikers weigeren of toestaan om [te scannen op Windows-updates](../protect/windows-update-settings.md).
- Het [meldingsniveau van Windows Update](../protect/windows-update-settings.md) dat gebruikers zien, beheren.

#### <a name="new-device-restriction-settings-for-android-enterprise-device-owner---3574254----"></a>Nieuwe apparaatbeperkingsinstellingen voor Android Enterprise-apparaateigenaar<!-- 3574254  -->
Op Android Enterprise-apparaten kunt u een profiel voor apparaatbeperking maken om functies toe te staan of te beperken en regels voor wachtwoorden in te stellen (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > Kies **Android Enterprise** als platform > **Alleen apparaateigenaar > Apparaatbeperkingen** als profieltype). 

Deze update bevat nieuwe wachtwoordinstellingen, verleent volledige toegang tot apps in de Google Play Store voor volledig beheerde apparaten enzovoort. Ga naar [Met Android Enterprise-apparaatinstellingen functies toestaan of beperken](../configuration/device-restrictions-android-for-work.md) voor de huidige lijst met instellingen. 

Van toepassing op: Volledig beheerde Android Enterprise-apparaten

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy---3617671---"></a>Controleren of er zich een TPM-chipset in een nalevingsbeleid voor Windows 10-apparaten bevindt<!-- 3617671 -->

Deze functie is vertraagd en wordt later uitgebracht.

#### <a name="updated-ui-changes-for-microsoft-edge-browser-on-windows-10-and-later-devices---3775833-----"></a>Bijgewerkte wijzigingen aan de gebruikersinterface voor de Microsoft Edge-browser op Windows 10 en hoger<!-- 3775833   -->
Wanneer u een apparaatconfiguratieprofiel maakt, kunt u Microsoft Edge-functies op Windows 10 en hoger toestaan of beperken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** als platform > **Apparaatbeperkingen** als profieltype >  **Microsoft Edge-browser**). In deze update worden de instellingen voor Microsoft Edge meer beschrijvend en gemakkelijker te begrijpen.

Als u deze functies wilt bekijken, gaat u naar [Apparaatbeperkingsinstellingen voor de Microsoft Edge-browser](../configuration/device-restrictions-windows-10.md#microsoft-edge-browser).

Van toepassing op: Windows 10 en hoger

#### <a name="expanded-support-for-android-enterprise-fully-managed-devices--preview-----3903241-3903244-3903246-----"></a>Uitgebreide ondersteuning voor volledig beheerde Android Enterprise-apparaten (preview)<!--   3903241, 3903244, 3903246   -->
Wij hebben onze ondersteuning, die nog steeds in openbare preview is, uitgebreid voor volledig beheerde Android Enterprise-apparaten (voor het eerst aangekondigd in januari 2019) en het volgende erin opgenomen:

- Op volledig beheerde en toegewezen apparaten kunt u [nalevingsbeleid](../protect/compliance-policy-create-android-for-work.md) maken met inbegrip van regels voor wachtwoorden en vereisten voor besturingssystemen (**Apparaatcompatibiliteit** > **Beleid** > **Beleid maken** > **Android Enterprise** als platform > **Apparaateigenaar** als profieltype).

  Op toegewezen apparaten kan het apparaat mogelijk worden weergegeven als **niet-compatibel**. Voorwaardelijke toegang is niet beschikbaar op toegewezen apparaten. Zorg ervoor dat u alle taken of acties uitvoert om de toegewezen apparaten compatibel te maken met uw toegewezen beleid.

- [Voorwaardelijke toegang](../protect/conditional-access.md): beleid voor voorwaardelijke toegang dat van toepassing is op Android, is ook van toepassing op volledig beheerde Android Enterprise-apparaten. Gebruikers kunnen nu hun volledig beheerd apparaat registreren bij Azure Active Directory met behulp van de **Microsoft Intune-app**. Bekijk vervolgens eventuele nalevingsproblemen voor toegang tot resources van de organisatie en los deze op.

- Nieuwe eindgebruiker-app (Microsoft Intune-app): er is een nieuwe eindgebruiker-app voor volledig beheerde Android-apparaten met de naam **Microsoft Intune**. Deze nieuwe app is licht en modern en biedt een functionaliteit die vergelijkbaar is met de bedrijfsportal-app, maar dan voor volledig beheerde apparaten. Zie [Microsoft Intune-app in Google Play](https://play.google.com/store/apps/details?id=com.microsoft.intune) voor meer informatie.

Ga naar **Apparaatinschrijving** > **Android-inschrijving** > **Bedrijfseigendom, volledig beheerde gebruikersapparaten** om volledige beheerde Android-apparaten in te stellen. Ondersteuning voor volledig beheerde Android-apparaten blijft in preview en bepaalde Intune-functies werken mogelijk niet volledig.  

Zie onze blog [Microsoft Intune - Preview 2 voor volledig beheerde Android Enterprise-apparaten](https://aka.ms/preview2_AE_fullymanaged) voor meer informatie over deze preview.

#### <a name="use-compliance-manager-to-create-assessments-for-microsoft-intune---4404750---"></a>Met behulp van Conformiteitsmanager een evaluatie voor Microsoft Intune maken<!-- 4404750 -->

[Conformiteitsmanager](https://servicetrust.microsoft.com/ComplianceManager) (hiermee opent u een andere Microsoft-website) is een hulpprogramma voor op werkstromen gebaseerde risicoanalyses in Microsoft Service Trust Portal. Hiermee kunt u activiteiten van uw organisatie op het gebied van naleving van regelgeving met betrekking tot Microsoft-services bijhouden, toewijzen en verifiëren. U kunt uw eigen nalevingsevaluatie maken met Office 365, Azure, Dynamics, Professional-Services en Intune. Intune heeft twee evaluaties beschikbaar - FFIEC en AVG.

Met Conformiteitsmanager kunt u uw inspanningen richten door besturingselementen in te delen: besturingselementen die worden beheerd door Microsoft en besturingselementen die worden beheerd door uw organisatie. U kunt de evaluaties uitvoeren en deze vervolgens exporteren en afdrukken.

[FFIEC-compliance (FFIEC: Federal Financial Institutions Examination Council)](https://www.microsoft.com/trustcenter/compliance/FFIEC) (hiermee opent u een andere Microsoft-website) is een verzameling standaarden voor internetbankieren die is uitgegeven door FFIEC. Het is de meest aangevraagde evaluatie voor financiële instellingen die gebruikmaken van Intune. Deze biedt een interpretatie van de wijze waarop u met behulp van Intune kunt voldoen aan de FFIEC-richtlijnen voor cyberbeveiliging met betrekking tot workloads in de openbare cloud. De FFIEC-evaluatie van Intune is de tweede FFIEC-evaluatie in Conformiteitsmanager.

In het volgende voorbeeld ziet u de indeling van FFIEC-besturingselementen. Microsoft gaat over 64-besturingselementen. U bent verantwoordelijk voor de resterende 12 besturingselementen.

![Bekijk een voorbeeld van een Intune-evaluatie voor FFIEC, met inbegrip van de acties van de klant en van Microsoft](./media/whats-new/intune-ffiec-assessment-status.png)

[AVG (Algemene Verordening Gegevensbescherming)](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-overview) (hiermee opent u een andere Microsoft-website) is een wet van de Europese Unie (EU) waarmee de rechten van personen en hun gegevens worden beschermd. De AVG is de meest aangevraagde evaluatie om te voldoen aan privacy-regelgeving. 

In het volgende voorbeeld ziet u de indeling van AVG-besturingselementen. Microsoft gaat over 49-besturingselementen. U bent verantwoordelijk voor de resterende 66 besturingselementen.

![Bekijk een voorbeeld van een Intune-evaluatie voor AVG, met inbegrip van de acties van de klant en van Microsoft](./media/whats-new/intune-assessment-status.png)


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="configure-profile-to-skip-some-screens-during-setup-assistant---2276470----"></a>Profiel configureren om bepaalde vensters over te slaan tijdens het doorlopen van de configuratieassistent<!-- 2276470  -->
Wanneer u een macOS-registratieprofiel maakt, kunt u binnenkort instellen dat de configuratieassistent de volgende schermen overslaat:
- Uiterlijk
- Weergavekleur
- iCloudStorage Als u een nieuw profiel maakt of een profiel bewerkt, moeten de geselecteerde skip-schermen worden gesynchroniseerd met de Apple MDM-server.  Gebruikers kunnen de opdracht tot een handmatige synchronisatie van de apparaten geven, zodat er geen vertraging in het ophalen van de profielwijzigingen is.
Raadpleeg [MacOS-apparaten automatisch inschrijven met het Device Enrollment Program of Apple School Manager](../enrollment/device-enrollment-program-enroll-macos.md) voor meer informatie.

#### <a name="bulk-device-naming-when-enrolling-corporate-ios-devices--3566569----"></a>Bulksgewijs apparaten benoemen bij het inschrijven van zakelijke iOS-apparaten<!--3566569  -->
Wanneer u een van de zakelijke inschrijvingsmethoden van Apple (DEP/ABM/ASM) gebruikt, kunt u de naamindeling van een apparaat zo instellen dat binnenkomende iOS-apparaten automatisch worden benoemd. U kunt een indeling opgeven waarin het apparaattype en serienummer in uw sjabloon wordt opgenomen. Als u dit wilt doen, kiest u **Intune** > **Apparaatinschrijving** > **Apple-inschrijving** > **Tokens voor het inschrijvingsprogramma** > **Een token selecteren** >**Profiel maken** > **Naamgevingsindeling voor apparaten**. U kunt bestaande profielen bewerken, maar alleen bij zojuist gesynchroniseerde apparaten wordt de naam toegepast.

#### <a name="updated-default-timeout-message-on-enrollment-status-page---3959331---"></a>Bijgewerkt standaard time-outbericht op de pagina Inschrijvingsstatus<!-- 3959331 -->
We hebben het standaard time-outbericht bijgewerkt dat gebruikers zien wanneer de pagina Status van inschrijving (ESP) de time-outwaarde overschrijdt die is opgegeven in het ESP-profiel. Het nieuwe standaardbericht is wat gebruikers zien en waarin duidelijk wordt gemaakt welke volgende acties ze kunnen ondernemen met hun ESP-implementatie.  

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Apparaatbeheer

#### <a name="retire-noncompliant-devices---1827291-----"></a>Niet-compatibele apparaten buiten gebruik stellen<!-- 1827291   -->
Deze functie is vertraagd en wordt in een toekomstige release geïntroduceerd.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="intune-data-warehouse-v10-changes-reflecting-back-to-beta---4403765---"></a>Wijzigingen in Intune Data Warehouse V1.0 worden doorgevoerd in de bètaversie<!-- 4403765 -->
Toen V1.0 voor het eerst werd uitgebracht in 1808, verschilde deze op belangrijke punten van de bètaversie-API. In 1903 zullen deze wijzigingen in de bètaversie-API worden doorgevoerd. Als u belangrijke rapporten hebt die gebruikmaken van de bètaversie-API, wordt u ten zeerste aangeraden deze rapporten over te zetten naar V1.0 om wijzigingen te voorkomen die fouten veroorzaken. Zie [Wijzigingenlogboek voor Intune Data Warehouse-API](../developer/reports-changelog.md#1903-part-2) voor meer informatie.

#### <a name="monitor-security-baseline-status-public-preview----3082047---"></a>Status beveiligingsbasislijnen controleren (openbare preview) <!-- 3082047 --> 
We hebben een [weergave per categorie](../protect/security-baselines-monitor.md#per-category-view) toegevoegd aan de controle van beveiligingsbasislijnen. (Beveiligingsbasislijnen blijven in preview). De weergave per categorie geeft elke categorie weer van de basislijn, samen met het percentage apparaten dat in elke statusgroep voor die categorie kan worden onderverdeeld. U kunt nu zien hoeveel apparaten niet overeenkomen met de afzonderlijke categorieën, onjuist zijn geconfigureerd of niet van toepassing zijn.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer

#### <a name="scope-tags-for-apple-vpp-tokens--2371886----"></a>Bereiktags voor Apple VPP-tokens<!--2371886  -->
U kunt nu bereiktags toevoegen aan Apple VPP-tokens. Alleen gebruikers aan wie dezelfde bereiktag is toegewezen, hebben toegang tot het Apple VPP-token met die tag. VPP-apps en e-Books die zijn gekocht met dit token nemen de bereiktags ervan over. Zie [RBAC en bereiktags gebruiken](scope-tags.md) voor meer informatie over bereiktags.

<!-- ########################## -->
## <a name="march-2019"></a>Maart 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Appbeheer
#### <a name="deploy-microsoft-visio-and-microsoft-project---3725386----"></a>Microsoft Visio en Microsoft Project implementeren<!-- 3725386  -->
U kunt nu Microsoft Visio Pro voor Office 365 en Microsoft Project Online-desktopclient implementeren als onafhankelijke apps voor Windows 10-apparaten met behulp van Microsoft Intune, mits u licenties hebt voor deze apps. Selecteer vanuit Intune **Client-apps** > **Apps** > **Toevoegen** om de blade **App toevoegen** weer te geven. Selecteer in de blade **App toevoegen** **Windows 10** als **App-type**. Selecteer daarna **App-pakket configureren** om de te installeren apps te selecteren. Zie [Office 365-apps toewijzen aan Windows 10-apparaten met Microsoft Intune](../apps/apps-add-office365.md) voor meer informatie over Office 365-apps voor Windows 10-apparaten.

#### <a name="microsoft-visio-pro-for-office-365-product-name-change---3593653----"></a>Wijziging van de productnaam Microsoft Visio Pro voor Office 365<!-- 3593653  -->
**Microsoft Visio Pro voor Office 365** heet nu **Microsoft Visio Online-abonnement 2**.  Zie [Visio Online-abonnement 2](https://products.office.com/visio/visio-online-plan-2) voor meer informatie over Microsoft Visio. Zie [Office 365-apps toewijzen aan Windows 10-apparaten met Microsoft Intune](../apps/apps-add-office365.md) voor meer informatie over Office 365-apps voor Windows 10-apparaten.

#### <a name="intune-app-protection-policy-app-character-limit-setting---3291302----"></a>Instelling van Intune app-beveiligingsbeleid (APP) voor maximum aantal tekens<!-- 3291302  -->
Intune-beheerders kunnen een uitzondering opgeven voor de Intune-app-beveiligingsbeleidsinstelling **Knippen, kopiëren en plakken met andere apps beperken**.  Als beheerder kunt u het aantal tekens opgeven dat mag worden geknipt of gekopieerd uit een beheerde app. Met deze instelling kunt u het opgegeven aantal tekens voor elke app delen, ongeacht de instelling Knippen, kopiëren en plakken met andere apps beperken. Houd er rekening mee dat de versie van de Intune-bedrijfsportal-app voor Android versie 5.0.4364.0 of hoger moet zijn. Zie [iOS-gegevensbeveiliging](../apps/app-protection-policy-settings-ios.md#data-protection), [Android-gegevensbeveiliging](../apps/app-protection-policy-settings-android.md#data-protection) en [Logboeken voor client-app-beveiliging controleren](../apps/app-protection-policy-settings-log.md#app-protection-policy-settings) voor meer informatie.

#### <a name="office-deployment-tool-odt-xml-for-office-proplus-deployment---3192477-----"></a>ODT-XML (ODT: Office Deployment Tool) voor de implementatie van Office ProPlus<!-- 3192477   -->
U kunt voorzien in een ODT-XML bij het maken van een Office Professional Plus-exemplaar in de Intune-beheerconsole. Dit biedt meer aanpassingsmogelijkheden, indien de bestaande Intune gebruikersinterfaceopties niet voldoen aan uw behoeften. Zie [Office 365-apps toewijzen aan Windows 10-apparaten met Microsoft Intune](../apps/apps-add-office365.md) en [Configuratieopties voor de Office Deployment Tool](https://docs.microsoft.com/DeployOffice/configuration-options-for-the-office-2016-deployment-tool) voor meer informatie.

#### <a name="app-icons-will-now-be-displayed-with-an-automatically-generated-background---1429026----"></a>App-pictogrammen worden nu weergegeven met een automatisch gegenereerde achtergrond<!-- 1429026  -->
In de Windows-bedrijfsportal-app-worden app-pictogrammen nu weergegeven met een automatisch gegenereerde achtergrond op basis van de overheersende kleur van het pictogram (mits deze detecteerbaar is). Indien van toepassing wordt de grijze rand die voorheen zichtbaar was op app-tegels, vervangen door deze achtergrond. Gebruikers zullen deze wijziging zien in bedrijfsportal-app-versies die hoger zijn dan 10.3.3451.0.

#### <a name="install-available-apps-using-the-company-portal-app-after-windows-bulk-enrollment---2751523-----"></a>Beschikbare apps installeren met behulp van de bedrijfsportal-app na de Windows-bulkinschrijving<!-- 2751523   -->
Windows-apparaten die zijn geregistreerd bij Intune via [Windows-bulkinschrijving](../enrollment/windows-bulk-enroll.md) (inrichtingspakketten) kunnen de bedrijfsportal-app gebruiken voor het installeren van beschikbare apps. Zie [De Windows 10-bedrijfsportal handmatig toevoegen](../apps/store-apps-company-portal-app.md) en [De Microsoft Intune-bedrijfsportal-app configureren](../apps/company-portal-app.md) voor meer informatie over de bedrijfsportal-app.

#### <a name="the-microsoft-teams-app-can-be-selected-as-part-of-the-office-app-suite---3828932----"></a>De Microsoft Teams-app kan worden geselecteerd als onderdeel van het Office-app-pakket<!-- 3828932  -->
De Microsoft Teams-app kan worden opgenomen of uitgesloten als onderdeel van de installatie van het Office Pro Plus-app-pakket. Deze functie werkt voor Office Professional Plus-buildnummer 16.0.11328.20116+. De gebruiker moet zich afmelden en vervolgens weer aanmelden op het apparaat om de installatie te voltooien. Selecteer in Intune de optie **Client-apps** > **Apps** > **Toevoegen**. Selecteer een van de app-typen van de **Office 365-Suite** en selecteer vervolgens **App-pakket configureren**.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="automatically-start-an-app-when-running-multiple-apps-in-kiosk-mode-on-windows-10-and-later-devices---2351390---"></a>Een app automatisch starten wanneer meerdere apps in de kioskmodus worden uitgevoerd op Windows 10-apparaten en hoger<!-- 2351390 -->

U kunt op Windows 10-apparaten en hoger een apparaat in de kioskmodus uitvoeren en veel apps uitvoeren. In deze update is een instelling **AutoLaunch** aanwezig (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** als platform > **Kiosk** als profieltype > **Kiosk voor meerdere apps**). Gebruik deze instelling om een app automatisch te starten wanneer de gebruiker zich aanmeldt bij het apparaat.

Zie [Instellingen van Windows 10-apparaten en hoger die als kiosk moet worden uitgevoerd in Intune](../configuration/kiosk-settings-windows.md) voor een lijst en een beschrijving van alle kioskinstellingen.

Van toepassing op: Windows 10 en hoger

#### <a name="operational-logs-also-show-details-on-non-compliant-devices---4063755----"></a>Operationele logboeken geven ook details weer over niet-compatibele apparaten<!-- 4063755  -->
Wanneer u Intune-logboeken naar Azure Monitor-functies stuurt, kunt u tevens de operationele logboeken sturen. In deze update bieden de operationele logboeken ook informatie over niet-compatibele apparaten.

Raadpleeg [Logboekgegevens verzenden naar opslag, Event Hubs of Log Analytics in Intune](../review-logs-using-azure-monitor.md) voor meer informatie over deze functie.

#### <a name="route-logs-to-azure-monitor-in-more-intune-workloads---3804627---"></a>Logboeken sturen naar Azure Monitor in meer Intune-workloads<!-- 3804627 -->
In Intune kunt u auditlogboeken en operationele logboeken sturen naar Event Hubs,opslag en Log Analytics in Azure Monitor (**Intune** > **Bewaking** > **Diagnose-instellingen**). In deze update kunt u deze logboeken routeren in meer Intune-workloads, met inbegrip van naleving, configuraties en client-apps enzovoort.

Zie [logboekgegevens verzenden naar Event Hubs, opslag en Log Analytics](../review-logs-using-azure-monitor.md) voor meer informatie over routering van logboeken naar Azure Monitor.

#### <a name="create-and-use-mobility-extensions-on-android-zebra-devices-in-intune---3305880-----"></a>Mobility-extensies maken en gebruiken op Android Zebra-apparaten in Intune<!-- 3305880   -->
In deze update biedt Intune ondersteuning voor het configureren van Android Zebra-apparaten. U kunt specifiek een apparaatconfiguratieprofiel maken en instellingen toepassen op Android Zebra-apparaten met behulp van MX-profielen (MX: Mobility-extensies) die worden gegenereerd door StageNow (**Apparaatconfiguratie** >  **Profielen** > **Profiel maken** > **Android** als platform > **MX-profiel (alleen Zebra)** als profieltype).

Zie [Zebra-apparaten gebruiken en beheren met Mobility-extensies in Intune](../configuration/android-zebra-mx-overview.md) voor meer informatie over deze functie.

Van toepassing op: Android

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Apparaatbeheer
#### <a name="encryption-report-for-windows-10-devices-in-public-preview---2351538---"></a>Versleutelingsrapport voor Windows 10-apparaten (in openbare preview)<!-- 2351538 -->
U kunt met het nieuwe [versleutelingsrapport (preview)](../protect/encryption-monitor.md) details weergeven over de versleutelingsstatus van uw Windows 10-apparaten. Beschikbare details bestaan onder meer uit een TPM-versie van apparaten, de versleutelingsgereedheid en -status, foutrapportage en meer.  

#### <a name="access-bitlocker-recovery-keys-from-the-intune-portal-in-public-preview---2351547-----"></a>Toegang krijgen tot BitLocker-herstelsleutels vanuit de Intune-portal (in openbare preview)<!-- 2351547   -->
U kunt nu Intune gebruiken om [details weer te geven](../protect/encryption-monitor.md) over BitLocker-sleutelidentificatie en BitLocker-herstelsleutels vanuit Azure Active Directory.

#### <a name="microsoft-edge-support-for-intune-scenarios-on-ios-and-android-devices---3411007---"></a>Microsoft Edge-ondersteuning voor Intune-scenario's op iOS- en Android-apparaten<!-- 3411007 -->
Microsoft Edge biedt ondersteuning voor dezelfde beheerscenario's als de Intune Managed Browser, met een verbeterde ervaring voor eindgebruikers. Microsoft Edge-functies voor bedrijven die zijn ingeschakeld door het Intune-beleid zijn onder meer dubbele identiteit, integratie van app-beveiligingsbeleid, integratie van Azure-toepassingsproxy's, beheerde favorieten en snelkoppelingen voor de startpagina. Zie de [ondersteuning voor Microsoft Edge](../apps/app-configuration-managed-browser.md#microsoft-edge-support) voor meer informatie.

#### <a name="exchange-onlineintune-connector-deprecate-support-for-eas-only-devices--3105122----"></a>Exchange Online-/Intune-connector bieden geen ondersteuning meer voor apparaten voor alleen EAS<!--3105122  -->
De Intune-console ondersteunt niet langer de weergave en het beheer van apparaten voor alleen EAS die met Exchange Online zijn verbonden met de Intune-connector. U hebt in plaats daarvan de volgende opties:
- Apparaten registreren in Mobile Device Management (MDM)
- Beleid voor Intune-app-beveiliging gebruiken om uw apparaten te beheren
- Exchange-besturingselementen gebruiken zoals wordt beschreven in [Clients en mobiel in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/clients-and-mobile-in-exchange-online)

#### <a name="search-the-all-devices-page-for-an-exact-device-by-using-name--4254930---"></a>De pagina Alle apparaten doorzoeken voor een exact apparaat met behulp van [naam]<!--4254930 -->
U kunt nu zoeken naar een exacte apparaatnaam. Ga naar **Intune** > **Apparaten** > **Alle apparaten** > plaats in het zoekvak de naam van het apparaat tussen {} om naar een exacte overeenkomst te zoeken. Bijvoorbeeld **{Device12345}** .

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="support-for-additional-connectors-on-the-tenant-status-page---3617202----"></a>Ondersteuning voor extra connectors op de pagina Tenantstatus<!-- 3617202  -->
De pagina [Tenantstatus](../tenant-status.md) geeft nu de statusinformatie weer voor extra connectors, inclusief *Windows Defender Advanced Threat Protection* (ATP) en andere Mobile Threat Defense-connectors.

#### <a name="support-for-the-power-bi-compliance-app-from-the-data-warehouse-blade-in-microsoft-intune---4260871---"></a>Ondersteuning voor de Power BI-compatibiliteit-app vanuit de blade Datawarehouse in Microsoft Intune<!-- 4260871 -->
Voorheen werd via de koppeling **Power BI-bestand downloaden** in de blade **Intune-datawarehouse** een Intune-datawarehouserapport (pbix-bestand) gedownload. Dit rapport is vervangen door de Power BI-compatibiliteit-app. De Power BI-compatibiliteit-app hoeft niet speciaal te worden geladen of ingesteld. U kunt deze rechtstreeks in de online Power BI-portal openen en ermee gegevens speciaal voor uw Intune-tenant weergeven op basis van uw referenties. Selecteer in Intune de koppeling **Intune-datawarehouse instellen** aan de rechterkant van de Intune-blade. Klik vervolgens op **Power BI-app ophalen**. Zie [Verbinding maken met het datawarehouse met Power BI](../developer/reports-proc-get-a-link-powerbi.md) voor meer informatie.


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer

#### <a name="granting-intune-read-only-access-to-some-azure-active-directory-roles---3637917----"></a>Alleen-lezentoegang voor Intune verlenen aan bepaalde Azure Active Directory-rollen<!-- 3637917  -->
Alleen-lezentoegang voor Intune is verleend aan de volgende Azure AD-rollen. Machtigingen met Azure AD-rollen hebben voorrang boven machtigingen die zijn verleend via de op rollen gebaseerd toegangsbeheer (RBAC) in Intune.

Alleen-lezentoegang tot Intune-controlegegevens:

- Beheerder voor naleving
- Beheerder voor nalevingsgegevens

Alleen-lezentoegang tot alle Intune-gegevens:

- Beveiligingsbeheer
- Beveiligingsoperator
- Beveiligingslezer

Zie [Op rollen gebaseerd toegangsbeheer](role-based-access-control.md) voor meer informatie.

#### <a name="scope-tags-for-ios-app-provisioning-profiles--2934430-----"></a>Bereiktags voor inrichtingsprofielen voor iOS-apps<!--2934430   -->
U kunt een bereiktag toevoegen aan een inrichtingsprofiel voor iOS-apps, zodat alleen personen met rollen die ook aan die bereiktag zijn toegewezen toegang hebben tot de app. Zie [RBAC en bereiktags gebruiken](scope-tags.md) voor meer informatie.

#### <a name="scope-tags-for-app-configuration-policies--2371891-----"></a>Bereiktags voor app-configuratiebeleid<!--2371891   -->
U kunt een bereiktag toevoegen aan app-configuratiebeleid, zodat alleen personen met rollen die ook zijn toegewezen aan de bereiktag, toegang hebben tot het app-configuratiebeleid. Het app-configuratiebeleid kan alleen doel zijn voor of worden gekoppeld aan apps waaraan dezelfde bereiktag is toegewezen. Zie [RBAC en bereiktags gebruiken](scope-tags.md) voor meer informatie.

#### <a name="microsoft-edge-support-for-intune-scenarios-on-ios-and-android-devices---3411007---"></a>Microsoft Edge-ondersteuning voor Intune-scenario's op iOS- en Android-apparaten<!-- 3411007 -->
Microsoft Edge biedt ondersteuning voor dezelfde beheerscenario's als de Intune Managed Browser met de toevoeging van verbeteringen in de eindgebruikerervaring. Microsoft Edge-functies voor bedrijven die zijn ingeschakeld door het Intune-beleid zijn onder meer dubbele identiteit, integratie van app-beveiligingsbeleid, integratie van Azure-toepassingsproxy's, beheerde favorieten en snelkoppelingen voor de startpagina. Zie de [ondersteuning voor Microsoft Edge](../apps/app-configuration-managed-browser.md#microsoft-edge-support) voor meer informatie.




<!-- ########################## -->
## <a name="february-2019"></a>Februari 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Appbeheer
#### <a name="intune-macos-company-portal-dark-mode---3300524----"></a>Donkere modus van Intune macOS-bedrijfsportal<!-- 3300524  -->
De Intune macOS Bedrijfsportal biedt nu ondersteuning voor de donkere modus voor macOS. Wanneer u de donkere modus inschakelt op een macOS 10.14+-apparaat, wordt de vormgeving door de Bedrijfsportal aangepast naar kleuren die overeenkomen met die modus.

#### <a name="intune-will-leverage-google-play-protect-apis-on-android-devices---2577355-----"></a>Intune gaat gebruikmaken van Google Play Protect-API’s op Android-apparaten<!-- 2577355   -->
Sommige IT-beheerders hebben te maken met een BYOD-landschap waar eindgebruikers mogelijk rooting of jailbreaking van hun mobiele telefoon veroorzaken. Dit gedrag leidt, in sommige gevallen onbewust, tot omzeiling van vele Intune-beleidsregels die zijn ingesteld om gegevens van de organisatie op de apparaten van eindgebruikers te beveiligen. Intune biedt daarom root- en jailbreakdetectie voor zowel geregistreerde als niet-geregistreerde apparaten. Met deze release zal Intune Google Play Protect-API’s aan onze bestaande rootdetectiecontroles toevoegen voor niet-geregistreerde apparaten. Hoewel Google niet alle rootdetectiecontroles die plaatsvinden deelt, verwachten we wel dat met deze API’s gebruikers worden gedetecteerd die hun apparaten om wat voor reden dan ook hebben geroot, variërend van apparaataanpassing tot de mogelijkheid nieuwere besturingssysteemupdates te krijgen op oudere apparaten. Toegang van deze gebruikers tot bedrijfsgegevens kan vervolgens worden geblokkeerd, of hun zakelijke accounts kunnen worden gewist uit via beleid ingeschakelde apps. Als extra waarde heeft de IT-beheerder nu verschillende rapportupdates op de blade Intune-app-beveiliging. Het rapport Gemarkeerde gebruikers toont welke gebruikers via de SafetyNet API-scan van Google Play Protect zijn gedetecteerd. Het rapport Mogelijk schadelijke apps toont aan welke apps zijn gedetecteerd via de scan die met de Verify Apps-API van Google is uitgevoerd. Deze functie is beschikbaar voor Android.

#### <a name="win32-app-information-available-in-troubleshooting-blade---2617342-----"></a>Informatie over Win32-apps, beschikbaar in de blade Probleemoplossing<!-- 2617342   -->
U kunt nu logboekbestanden over fouten bij een Win32-app-installatie verzamelen via de blade **Probleemoplossing** in de Intune-app. Zie [Problemen met de installatie oplossen](./../apps/troubleshoot-app-install.md) en [Problemen met Win32-apps oplossen](./../apps/troubleshoot-app-install.md#win32-app-installation-troubleshooting) voor meer informatie over problemen oplossen met de installatie van apps.

#### <a name="app-status-details-for-ios-apps---3761235-----"></a>Informatie over de appstatus voor iOS-apps<!-- 3761235   -->
Er zijn nieuwe meldingen voor installatiefouten van apps beschikbaar met betrekking tot het volgende:
- Fout tijdens het installeren van VPP-apps op een gedeelde iPad
- Fout tijdens uitschakelen van App Store
- Fout tijdens het zoeken van een VPP-licentie voor de app
- Fout tijdens het installeren van systeemapps met MDM-provider
- Fout tijdens het installeren van apps wanneer apparaat zich in de verloren-modus of kioskmodus bevindt
- Fout tijdens het installeren van apps wanneer gebruiker niet bij de App Store is aangemeld

In Intune selecteert u **Client-apps** > **Apps** > naam van de app > **Apparaatinstallatiestatus**. Nieuwe foutmeldingen zijn beschikbaar in de kolom **Statusdetails**.

#### <a name="new-app-categories-screen-in-the-company-portal-app-for-windows-10---3834780----"></a>Het scherm Nieuwe app-categorieën in de bedrijfsportal-app voor Windows 10<!-- 3834780  -->
Een nieuw scherm met de naam **App-categorieën** is toegevoegd om de blader- en selectie-ervaring voor apps te verbeteren in de bedrijfsportal voor Windows 10. Gebruikers zien nu hun apps gesorteerd onder categorieën, zoals **Aanbevolen**, **Opleiding** en **Productiviteit**. Deze wijziging wordt weergegeven in de bedrijfsportal-app-versies 10.3.3451.0 en hoger. Zie [Wat is er nieuw in de gebruikersinterface van de app?](whats-new-app-ui.md) om het nieuwe scherm te bekijken. Zie [Apps installeren en delen op uw apparaat](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows) voor meer informatie over apps in de bedrijfsportal.  

#### <a name="power-bi-compliance-app---1455231-doc-work-item---"></a>Power BI-compatibiliteit-app<!-- 1455231 doc-work-item -->
Krijg toegang tot uw Intune-datawarehouse in Power BI Online met behulp van de [Intune-compatibiliteit-app (datawarehouse)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp). Met deze Power BI-app kunt u nu vooraf gemaakte rapporten openen en delen zonder iets te hoeven instellen en zonder uw webbrowser te verlaten. Zie [Wijzigingenlogboek - Power BI-compatibiliteit-app](../developer/reports-changelog.md#power-bi-compliance-app) voor meer informatie.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="powershell-scripts-can-run-in-a-64-bit-host-on-64-bit-devices---1862675-----"></a>PowerShell-scripts kunnen worden uitgevoerd in een 64-bits host op 64-bits apparaten<!-- 1862675   -->
Wanneer u een PowerShell-script aan een apparaatconfiguratieprofiel toevoegt, wordt het script altijd uitgevoerd in 32 bits, zelfs op 64-bits besturingssystemen. Met deze update kan een beheerder het script uitvoeren in een 64-bits PowerShell-host op 64-bits apparaten (**Apparaatconfiguratie** > **PowerShell-scripts** > **Toevoegen** > **Configureren** > **Script uitvoeren in 64-bits PowerShell-host**).

Zie [PowerShell-scripts in Intune](../apps/intune-management-extension.md) voor meer details over het gebruik van PowerShell.

Van toepassing op: Windows 10 en hoger

#### <a name="macos-users-are-prompted-to-update-their-password---1873216---"></a>macOS-gebruikers wordt gevraagd hun wachtwoord bij te werken<!-- 1873216 -->
In Intune wordt de instelling **ChangeAtNextAuth** afgedwongen op macOS-apparaten. Deze instelling heeft gevolgen voor eindgebruikers en apparaten met wachtwoordbeleid voor naleving of wachtwoordprofielen voor apparaatbeperkingen. Eindgebruikers wordt eenmalig gevraagd hun wachtwoord bij te werken. Dit gebeurt wanneer een gebruiker voor het eerst een taak uitvoert die moet worden geverifieerd, zoals het aanmelden bij het apparaat. Gebruikers kunnen ook worden gevraagd hun wachtwoord bij te werken wanneer zij iets doen waarvoor beheerdersrechten zijn vereist, zoals het aanvragen van sleutelhangertoegang.

Wijzigingen in nieuw of bestaand wachtwoordbeleid door de beheerder zorgt ervoor dat opnieuw aan eindgebruikers wordt gevraagd om hun wachtwoord bij te werken.

Van toepassing op:  
macOS

#### <a name="assign-scep-certificates-to-a-userless-macos-device---2340521------"></a>SCEP-certificaten aan een macOS-apparaat zonder gebruikers toewijzen<!-- 2340521    -->
U kunt met behulp van apparaatkenmerken SCEP-certificaten (SCEP: Simple Certificate Enrollment Protocol) toewijzen aan macOS-apparaten, inclusief apparaten zonder gebruikersaffiniteit, en het certificaatprofiel met Wi-Fi -of VPN-profielen koppelen. Dit is een uitbreiding van de bestaande ondersteuning voor het [toewijzen van SCEP-certificaten aan apparaten zonder gebruikersaffiniteit](../protect/certificates-profile-scep.md) die worden uitgevoerd op Windows, iOS en Android.  In deze update wordt de optie toegevoegd waarmee een certificaattype van *Apparaat* wordt geselecteerd wanneer u een SCEP-certificaatprofiel voor macOS configureert.

Van toepassing op:
- macOS

#### <a name="intune-conditional-access-ui-update---2432313-----"></a>Update voor gebruikersinterface voor voorwaardelijke toegang tot Intune<!-- 2432313   -->
We hebben verbeteringen aangebracht in de gebruikersinterface voor voorwaardelijke toegang in de Intune-console. Deze omvatten:
- Vervanging van de Intune-blade *Voorwaardelijke toegang* door de blade van Azure Active Directory. Hiermee hebt u toegang tot alle instellingen en configuraties voor [voorwaardelijke toegang](../protect/conditional-access.md) (die een Azure AD-technologie blijven) vanuit de Intune-console. 
- We hebben de naam van de blade *On-premises toegang* gewijzigd in *Toegang tot Exchange* en de configuratie van de *Exchange-serviceconnector* verplaatst naar deze hernoemde blade.  Door deze wijziging worden de locaties gecombineerd waar u [details met betrekking tot Exchange online en on-premises configureert en bewaakt](../protect/exchange-connector-install.md).  

#### <a name="kiosk-browser-and-microsoft-edge-browser-apps-can-run-on-windows-10-devices-in-kiosk-mode---2935135-----"></a>Kiosk Browser- en Microsoft Edge Browser-apps kunnen worden uitgevoerd op Windows 10-apparaten in de kioskmodus<!-- 2935135   -->
In de kioskmodus kunnen één of meerdere apps op Windows 10-apparaten worden uitgevoerd. Deze update omvat verschillende wijzigingen in het gebruik van browserapps in de kioskmodus, waaronder:

- Voeg de Microsoft Edge Browser of Kiosk Browser toe om deze als apps uit te voeren op het kioskapparaat (**Apparaatconfiguratie** > **Profielen** > **Nieuw profiel** > **Windows 10 en later** voor platform > **Kiosk** voor profieltype).
- Er zijn nieuwe functies en instellingen beschikbaar voor toestaan of beperken (**Apparaatconfiguratie** > **Profielen** > **Nieuw profiel** > **Windows 10 en hoger** als platform > **Apparaatbeperkingen** als profieltype), waaronder:

- Microsoft Edge-browser:
  - Gebruik van Microsoft Edge-kioskmodus
  - De browser vernieuwen na niet-actieve tijd

- Favorieten en zoeken:
  - Wijzigingen in de zoekmachine toestaan

Ga voor een lijst met deze instellingen naar:

- [Instellingen voor apparaten met Windows 10 en hoger om ze als kiosk uit te voeren](../configuration/kiosk-settings-windows.md)
- [Microsoft Edge Browser-apparaatbeperkingen](../configuration/device-restrictions-windows-10.md#microsoft-edge-browser)
- [Apparaatbeperkingen voor favorieten en zoeken](../configuration/device-restrictions-windows-10.md##favorites-and-search)

Van toepassing op: Windows 10 en hoger

#### <a name="new-device-restriction-settings-for-ios-and-macos-devices---3448774-----"></a>Nieuwe apparaatbeperkingsinstellingen voor iOS- en macOS-apparaten<!-- 3448774   -->
U kunt een aantal instellingen en functies beperken op apparaten waarop iOS en macOS worden uitgevoerd (**Apparaatconfiguratie** > **Profielen** > **Nieuw profiel** > **iOS** of **macOS** voor platform > **Apparaatbeperkingen** voor profieltype). Met deze update worden meer functies en instellingen toegevoegd die u kunt beheren, waaronder het instellen van schermtijd, het wijzigen van eSIM-instellingen en mobiele abonnementen en meer op iOS-apparaten. Andere functies zijn het vertragen van de zichtbaarheid voor de gebruiker van software-updates en het blokkeren van cacheopslag van inhoud op macOS-apparaten.

Als u de functies en instellingen wilt zien die u kunt beperken, raadpleegt u:

- [Beperkingsinstellingen voor iOS-apparaten](../configuration/device-restrictions-ios.md)
- [Beperkingsinstellingen voor macOS-apparaten](../configuration/device-restrictions-macos.md)

Van toepassing op:

- iOS
- macOS

#### <a name="kiosk-devices-are-now-called-dedicated-devices-on-android-enterprise-devices---3598402-----"></a>Apparaten in de kioskmodus heten voortaan 'toegewezen apparaten' op Android Enterprise-apparaten<!-- 3598402   -->
Voor de afstemming met Android terminologie wordt **kiosk** gewijzigd in **toegewezen apparaten** voor Android Enterprise-apparaten (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > ** Android Enterprise als platform > **Alleen apparaateigenaar** > **Apparaatbeperkingen** > **Toegewezen apparaten**).

Als u de beschikbare instellingen wilt zien, gaat u naar [Apparaatinstellingen voor het toestaan of beperken van functies](../configuration/device-restrictions-android-for-work.md#dedicated-device-settings).

Van toepassing op:  
Android Enterprise

#### <a name="safari-and-delaying-user-software-update-visibility-ios-settings-are-moving-in-the-intune-ui---3640850-3803313-----"></a>iOS-instellingen voor de zichtbaarheid van Safari-software-updates en het vertragen van die zichtbaarheid voor gebruikers worden verplaatst in de Intune-gebruikersinterface<!-- 3640850, 3803313   -->
Voor iOS-apparaten kunt u Safari-instellingen instellen en software-updates configureren. In deze update worden deze instellingen naar verschillende delen van de Intune-gebruikersinterface verplaatst:

- De Safari-instellingen zijn verplaatst van **Safari** (**Apparaatconfiguratie** > **Profielen** > **Nieuw profiel** > **iOS** als platform > **Apparaatbeperkingen** als profieltype) naar **[Ingebouwde apps](../configuration/device-restrictions-ios.md#built-in-apps)** .
- De instelling **Zichtbaarheid van software-updates voor gebruikers voor iOS-apparaten onder toezicht vertragen** (**Software-updates** > **Updatebeleid voor iOS**) wordt verplaatst naar **Apparaatbeperkingen** >  **[Algemeen](../configuration/device-restrictions-ios.md#general)** .  Zie [Software-updates voor iOS](../protect/software-updates-ios.md#configure-the-policy) voor meer informatie over de gevolgen voor bestaand beleid.

Ga voor een lijst met de instellingen naar:

- [Beperkingen voor iOS-apparaten](../configuration/device-restrictions-ios.md) 
- [Updates van iOS-software](../protect/software-updates-ios.md)

Deze functie is van toepassing op:

- iOS

#### <a name="enabling-restrictions-in-the-device-settings-is-renamed-to-screen-time-on-ios-devices---3699164-----"></a>De naam Beperkingen inschakelen bij de apparaatinstellingen wordt gewijzigd in Schermtijd op iOS-apparaten<!-- 3699164   -->
U kunt **Beperkingen inschakelen bij de apparaatinstellingen** op iOS-apparaten onder toezicht configureren (**Apparaatconfiguratie** > **Profielen** > **Nieuw profiel** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype > **Algemeen**). In deze update wordt de naam van deze instelling gewijzigd in **Schermtijd (alleen onder toezicht)** .

Het gedrag blijft hetzelfde. Specifiek:

- iOS 11.4.1 en eerder: **Blokkeren** voorkomt dat eindgebruikers hun eigen beperkingen kunnen instellen bij de apparaatinstellingen. 
- iOS 12.0 en hoger: **Blokkeren** voorkomt dat eindgebruikers hun eigen **Schermtijd** kunnen instellen bij de apparaatinstellingen, waaronder inhouds- en privacybeperkingen. Op apparaten die naar iOS 12.0 zijn geüpgraded is het tabblad Beperkingen niet meer zichtbaar bij de apparaatinstellingen. Deze instellingen vindt u onder **Schermtijd**. 

Zie [Beperkingen voor iOS-apparaten](../configuration/device-restrictions-ios.md#general) voor een lijst met de instellingen.

Van toepassing op:
- iOS


#### <a name="intune-powershell-module---951068----"></a>Intune PowerShell-module<!-- 951068  -->
De Intune PowerShell-module die ondersteuning biedt voor de Intune-API via Microsoft Graph, is nu beschikbaar in de [Microsoft PowerShell Gallery](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1902.1.10).

- [Informatie over het gebruik van deze module](https://github.com/Microsoft/Intune-PowerShell-SDK/blob/master/README.md)
- [Voorbeelden van scenario's waarbij deze module wordt gebruikt](https://github.com/Microsoft/Intune-PowerShell-SDK/blob/master/Samples/README.md)

#### <a name="improved-support-for-delivery-optimization--3183757----"></a>Verbeterde ondersteuning voor Delivery Optimization<!--3183757  -->
We hebben de ondersteuning in Intune uitgebreid voor het configureren van Delivery Optimization. U kunt nu een uitgebreide lijst configureren met [Delivery Optimization-instellingen](../configuration/delivery-optimization-settings.md) en deze rechtstreeks vanuit de Intune-console toepassen op uw apparaten.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Apparaatbeheer

#### <a name="rename-an-enrolled-windows-device---1911112----"></a>De naam van een geregistreerd Windows-apparaat wijzigen<!-- 1911112  -->
U kunt nu de naam van geregistreerde Windows 10-apparaten (RS4 of later) wijzigen. Kies hiervoor **Intune** > **Apparaten** > **Alle apparaten** > kies een apparaat > **Naam van apparaat wijzigen**. Deze functie biedt momenteel geen ondersteuning voor de naamwijziging van hybride Azure AD Windows-apparaten.

#### <a name="auto-assign-scope-tags-to-resources-created-by-an-admin-with-that-scope---3173823----"></a>Bereiktags automatisch toewijzen aan resources die door een beheerder met dat bereik zijn gemaakt<!-- 3173823  -->
Wanneer een beheerder een resource maakt, worden alle bereiktags die aan de beheerder zijn toegewezen automatisch toegewezen aan die nieuwe resources.

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="failed-enrollment-report-moves-to-the-device-enrollment-blade---3560202----"></a>Mislukte verplaatsing van registratierapporten naar de blade Apparaatregistratie<!-- 3560202  -->
Het rapport **Mislukte registraties** is verplaatst naar het gedeelte **Bewaking** van de blade **Apparaatregistratie**. Twee nieuwe kolommen (Registratiemethode en besturingssysteemversie) zijn ook toegevoegd.

#### <a name="company-portal-abandonment-report-renamed-to-incomplete-user-enrollments--3815076-eemiss---"></a>De naam van het rapport Bedrijfsportal afbreken is gewijzigd in Onvolledig gebruikersinschrijvingen<!--3815076 eemiss -->
De naam van het rapport **Bedrijfsportal afbreken** is gewijzigd in **Onvolledig gebruikersinschrijvingen**.






<!-- ########################## -->
## <a name="january-2019"></a>Januari 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Appbeheer

#### <a name="intune-app-pin---2298397---"></a>Pincode voor de Intune-app<!-- 2298397 -->
Als IT-beheerder kunt u nu het aantal dagen configureren dat een eindgebruiker kan wachten voordat zijn pincode voor de Intune-app moet worden gewijzigd. De nieuwe instelling is *Pincode opnieuw instellen na aantal dagen* en is beschikbaar in Azure Portal als u **Intune** > **Client-apps** > **App-beveiligingsbeleid** > **Beleid maken** > **Instellingen** > **Toegangsvereisten** kiest. Deze functie is beschikbaar voor [iOS](../apps/app-protection-policy-settings-ios.md)- en [Android](../apps/app-protection-policy-settings-android.md)-apparaten en biedt ondersteuning voor een positief geheel getal.

#### <a name="intune-device-reporting-fields---2748738---"></a>Rapportvelden voor Intune-apparaat<!-- 2748738 -->
Intune biedt aanvullende velden voor apparaatrapporten, waaronder de registratie-id van de app, de Android-fabrikant, het model, de versie van de beveiligingspatch en het iOS-model. In Intune zijn deze velden beschikbaar door **Client-apps** > **App-beveiligingsstatus** te selecteren en vervolgens **App-beveiligingsrapport: iOS, Android** te kiezen. Bovendien helpen deze parameters u de lijst **Toestaan** te configureren voor de apparaatfabrikant (Android), evenals de lijst **Toestaan** voor het apparaatmodel (Android en iOS) en de versie-instellingen van de minimale Android-beveiligingspatch.

#### <a name="toast-notifications-for-win32-apps---3136566-----"></a>Toast-meldingen voor Win32-apps<!-- 3136566   -->
U kunt per app-toewijzing onderdrukken dat toast-meldingen voor eindgebruikers worden weergegeven. Selecteer vanuit Intune de optie **Client-apps** > **Apps** > selecteer de app > **Toewijzingen** > **Groepen opnemen**.

#### <a name="intune-app-protection-policies-ui-update---3251427----"></a>Update van de gebruikersinterface voor beveiligingsbeleid voor apps in Intune<!-- 3251427  -->
We hebben de labels voor instellingen en knoppen voor App-beveiliging van Intune gewijzigd om ze duidelijker te maken. De wijzigingen zijn onder meer:  
- Besturingselementen zijn gewijzigd van **ja** / **nee** naar primair **blokkeren** / **toestaan** en **uitschakelen** / **inschakelen**. De labels zijn ook bijgewerkt.  
- De instellingen zijn opnieuw ingedeeld, zodat de instellingen en bijbehorende labels naast elkaar in het besturingselement staan, wat betere navigatie biedt.

De standaardinstellingen en een aantal instellingen blijven dezelfde, maar met deze wijziging kan de gebruiker de instellingen beter begrijpen, gebruiken en er door navigeren om het geselecteerde app-beveiligingsbeleid toe te passen. Zie [iOS-instellingen](../apps/app-protection-policy-settings-ios.md) en [Android-instellingen](../apps/app-protection-policy-settings-android.md) voor meer informatie.

#### <a name="additional-settings-for-outlook---3301182----"></a>Extra instellingen voor Outlook<!-- 3301182  -->
U kunt nu de volgende aanvullende instellingen voor Outlook voor iOS en Android configureren met Intune:

- Instellen dat alleen werk- of schoolaccounts mogen worden gebruikt in Outlook in iOS en Android
- Moderne verificatie implementeren voor Office 365 en hybride moderne verificatie voor on-premises accounts
- `SAMAccountName` gebruiken in het gebruikersnaamveld in het e-mailprofiel als basisverificatie wordt geselecteerd
- Toestaan dat contactpersonen worden opgeslagen
- E-mailtips voor externe ontvangers configureren
- Het **Postvak IN met prioriteit** configureren
- Biometrie vereisten voor toegang tot Outlook in iOS
- Externe afbeeldingen blokkeren

> [!NOTE]
> Als u gebruikmaakt van Intune-app-beveiligingsbeleid voor het beheren van toegang tot bedrijfs-id's, wordt afgeraden **biometrie te vereisen**. Zie **Bedrijfsreferenties vereisen voor toegang** voor [iOS-toegangsinstellingen](../apps/app-protection-policy-settings-ios.md#access-requirements) en [Android-toegangsinstellingen](../apps/app-protection-policy-settings-android.md#access-requirements).

Zie [Configuratie-instellingen voor Microsoft Outlook](../apps/app-configuration-policies-outlook.md) voor meer informatie.

#### <a name="delete-android-enterprise-apps---1352553---"></a>Android Enterprise-apps verwijderen<!-- 1352553 -->
U kunt beheerde Google Play-apps verwijderen uit Microsoft Intune. Als u een beheerde Google Play-app wilt verwijderen, opent u Microsoft Intune in de Azure-portal en selecteert u **Client-apps** > **Apps**. In de lijst met apps selecteert u het beletselteken (...) rechts naast de beheerde Google Play-app en vervolgens **Verwijderen** in de weergegeven lijst. Wanneer u een beheerde Google Play-app uit de lijst met apps verwijdert, wordt de goedkeuring voor de beheerde Google Play-app automatisch verwijderd.

#### <a name="managed-google-play-app-type---1352580---"></a>Type beheerde Google Play-app<!-- 1352580 -->
Met het type **beheerde Google Play-app** hebt u toestemming om specifiek [beheerde Google Play-apps](https://play.google.com/work/search?q=microsoft&c=apps) aan Intune toe te voegen. Als Intune-beheerder kunt u nu door goedgekeurde beheerde Google Play-apps bladeren en goedgekeurde beheerde Google Play-apps zoeken, goedkeuren, synchroniseren en toewijzen in Intune.  U hoeft niet langer afzonderlijk naar de beheerde Google Play-console te bladeren en u hoeft niet opnieuw een verificatie uit te voeren.  Selecteer in Intune de optie **Client-apps** > **Apps** > **Toevoegen**. In de lijst **App-type** selecteert u **Beheerd Google Play** als app-type.

#### <a name="default-android-pin-keyboard---3802457---"></a>Standaardpincodetoetsenbord van Android<!-- 3802457 -->
Eindgebruikers die een Intune APP-pincode (App Protection Policy) op hun Android-apparaten hebben ingesteld met pincodetype Numeriek, zien nu het Android-standaardtoetsenbord in plaats van de gebruikelijke Android-toetsenbordgebruikersinterface die eerder is ontworpen. Deze wijziging is doorgevoerd voor consistentie met standaardtoetsenborden op zowel Android als iOS, voor de pincodetypen Numeriek en/of Wachtwoordcode. Zie [Android-toegangsvereisten](../apps/app-protection-policy-settings-android.md#access-requirements) voor meer informatie over de toegangsinstellingen voor eindgebruiker op Android, zoals de APP-pincode.


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Beheersjablonen zijn in openbare preview en verplaatst naar hun eigen configuratieprofiel <!-- 3322847 -->

Beheersjablonen in Intune (**Apparaatconfiguratie** > **Beheersjablonen**) zijn momenteel in openbare preview. Bij deze update:

- Beheersjablonen omvatten circa 300 instellingen die kunnen worden beheerd in Intune. Eerder bestonden deze instellingen alleen in de editor voor groepsbeleid.
- Beheersjablonen zijn beschikbaar in openbare preview.
- Beheersjablonen worden verplaatst van **Apparaatconfiguratie** > **Beheersjablonen** naar **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > kies als **Platform** **Windows 10 en hoger** > kies in **Profieltype** **Beheersjablonen**.
- Rapportage is ingeschakeld

Ga naar [Windows 10 templates to configure group policy settings](../configuration/administrative-templates-windows.md) (Windows 10-sjablonen voor het configureren van instellingen voor groepsbeleid) voor meer informatie over deze functie.

Van toepassing op: Windows 10 en hoger

#### <a name="use-smime-to-encrypt-and-sign-multiple-devices-for-a-user---1333642---"></a>S/MIME gebruiken om meerdere apparaten van een gebruiker te versleutelen en ondertekenen<!-- 1333642 -->
Deze update bevat een S/MIME-e-mailversleuteling met een nieuw profiel voor een geïmporteerd certificaat (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > selecteer het platform > profieltype **Geïmporteerd PKCS-certificaat**). In Intune kunt u certificaten importeren in PFX-indeling. Intune kan deze certificaten dan leveren aan meerdere apparaten die zijn geregistreerd door één gebruiker. Dit omvat ook:
- Het systeemeigen iOS-e-mailprofiel ondersteunt het inschakelen van S/MIME-versleuteling met behulp van geïmporteerde certificaten in de PFX-indeling.
- De systeemeigen e-mail-app op Windows Phone 10-apparaten gebruikt automatisch het S/MIME-certificaat.
- De persoonlijke certificaten kunnen worden afgeleverd op meerdere platformen. Maar niet alle e-mail-apps ondersteunen S/MIME.
- Op andere platformen moet u mogelijk de mail-app handmatig configureren om S/MIME in te schakelen.  
- E-mail-apps die ondersteuning bieden voor S/MIME-versleuteling, kunnen het ophalen van certificaten voor S/MIME-e-mailversleuteling verwerken op een manier die een MDM niet kan ondersteunen, zoals het lezen van het certificaatarchief van de uitgever.
Zie [S/MIME overview to sign and encrypt email](../protect/certificates-s-mime-encryption-sign.md) (S/MIME voor e-mailondertekening en -versleuteling) voor meer informatie over deze functie.
Ondersteund in: Windows, Windows Phone 10, macOS, iOS, Android

#### <a name="new-options-to-automatically-connect-and-persist-rules-when-using-dns-settings-on-windows-10-and-later-devices---1333665-2999078---"></a>Nieuwe opties om automatisch verbinding te maken en regels te behouden met DNS-instellingen in Windows 10 en hoger<!-- 1333665, 2999078 -->
Op apparaten met Windows 10 en hoger kunt u een VPN-configuratieprofiel maken dat een lijst DNS-servers bevat om domeinen om te zetten, zoals contoso.com. Deze update bevat nieuwe instellingen voor naamomzetting: (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > kies **Windows 10 en hoger** als platform > kies **VPN** als profieltype > **DNS-instellingen** >**Toevoegen**): 
- **Automatisch verbinding maken**: Als deze optie is **ingeschakeld**, maakt het apparaat automatisch verbinding met VPN wanneer een apparaat een domein oproept dat u invoert, bijvoorbeeld contoso.com.
- **Permanent**: Standaard zijn alle NRPT-tabelregels voor Naamomzettingsbeleid (NRPT) actief zolang het apparaat is verbonden met behulp van dit VPN-profiel. Wanneer deze instelling is **ingeschakeld** voor een NRPT-regel, blijft de regel actief op het apparaat, zelfs wanneer de VPN-verbinding wordt verbroken. De regel blijft totdat het VPN-profiel is verwijderd of totdat de regel handmatig wordt verwijderd, wat mogelijk is met behulp van PowerShell.
In [Windows 10 VPN-instellingen](../configuration/vpn-settings-windows-10.md) worden instellingen beschreven.

#### <a name="use-trusted-network-detection-for-vpn-profiles-on-windows-10-devices---1500165---"></a>Detectie van vertrouwde netwerken gebruiken voor VPN-profielen in Windows 10-apparaten<!-- 1500165 -->
Wanneer u gebruikmaakt van detectie van vertrouwde netwerken, kunt u voorkomen dat VPN-profielen automatisch een VPN-verbinding maken wanneer de gebruiker zich al op een vertrouwd netwerk bevindt. Met deze update kunt u DNS-achtervoegsels toevoegen om detectie van vertrouwde netwerken in te schakelen op apparaten met Windows 10 en hoger (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** als platform en **VPN** als profieltype).
In [VPN-instellingen voor Windows 10](../configuration/vpn-settings-windows-10.md) worden de huidige VPN-instellingen vermeld.

#### <a name="manage-windows-holographic-for-business-devices-used-by-multiple-users---1907917-1063203---"></a>Windows Holographic for Business-apparaten beheren die worden gebruikt door meerdere gebruikers<!-- 1907917, 1063203 -->
U kunt momenteel gedeelde pc-instellingen configureren op Windows 10- en Windows Holographic for Business-apparaten met een aangepaste OMA-URI-instelling. Met deze update wordt een nieuw profiel toegevoegd om instellingen voor gedeelde apparaten te configureren (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** > **Gedeeld apparaat met meerdere gebruikers**).
Ga naar [Intune settings to manage shared devices](../configuration/shared-user-device-settings.md) (Intune-instellingen voor het beheren van gedeelde apparaten) voor meer informatie over deze functie.
Van toepassing op: Windows 10 en hoger, Windows Holographic for Business

#### <a name="new-windows-10-update-settings--2626030--2512994----"></a>Nieuwe Windows 10-update-instellingen<!--2626030  2512994  -->
Voor uw [Windows 10-update-ringen](../protect/windows-update-for-business-configure.md) kunt u het volgende configureren:
- **Gedrag van automatische updates** : gebruik de nieuwe optie *Standaardinstellingen opnieuw instellen* om de oorspronkelijke instellingen voor automatische updates te herstellen op een Windows 10-computer waarop de *update van oktober 2018* is geïnstalleerd
- **Blokkeren dat gebruikers Windows-updates kunnen onderbreken**: configureer een nieuwe instelling voor software-updates waarmee u kunt toestaan of blokkeren dat gebruikers de installatie van updates kunnen onderbreken via de *Instellingen* op hun computer.

#### <a name="ios-email-profiles-can-use-smime-signing-and-encryption---2662949---"></a>iOS-e-mailprofielen kunnen gebruikmaken van S/MIME-ondertekening en versleuteling<!-- 2662949 -->
U kunt een e-mailprofiel maken dat verschillende instellingen bevat. Deze update bevat onder andere S/MIME-instellingen die kunnen worden gebruikt voor de ondertekening en versleuteling van e-mailcommunicatie op iOS-apparaten (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > kies **iOS** als platform en **E-mail** als profieltype).
In [Configuratie-instellingen voor iOS-e-mail](../configuration/email-settings-ios.md) worden de instellingen vermeld.

#### <a name="some-bitlocker-settings-support-windows-10-pro-edition---2727036---"></a>Sommige BitLocker-instellingen ondersteunen Windows 10 Pro<!-- 2727036 -->
U kunt een configuratieprofiel maken waarmee Endpoint Protection-instellingen op Windows 10-apparaten wordt ingesteld, waaronder BitLocker. Met deze update wordt voor sommige BitLocker-instellingen ondersteuning toegevoegd voor Windows 10 Professional.
Ga naar [Instellingen voor de beveiliging van eindpunten voor Windows 10](../protect/endpoint-protection-windows-10.md#windows-encryption) om deze beveiligingsinstellingen te bekijken.

#### <a name="shared-device-configuration-is-renamed-to-lock-screen-message-for-ios-devices-in-the-azure-portal---2809362---"></a>In Azure Portal is de naam Configuratie voor gedeelde apparaten voor iOS-apparaten gewijzigd in Bericht voor vergrendelingsscherm<!-- 2809362 -->
Wanneer u een configuratieprofiel voor iOS-apparaten maakt, kunt u de instelling **Configuratie voor gedeelde apparaten** toevoegen, zodat er specifieke tekst op het vergrendelingsscherm wordt weergegeven. Deze update bevat onder andere de volgende wijzigingen: 
- De instellingen voor **Configuratie voor gedeelde apparaten** in de Azure-portal worden hernoemd naar 'Vergrendelingsschermbericht (alleen onder supervisie)' (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > kies **iOS** als platform > kies **Apparaatfuncties** als profieltype > **Vergrendelingsschermbericht**).
- Wanneer u vergrendelingsschermberichten toevoegt, kunt u een serienummer, apparaatnaam of een andere apparaatspecifieke waarde als variabele invoegen in **Informatie over de assettag** en **Voetnoot voor het vergrendelingsscherm** . U kunt bijvoorbeeld `Device name: {{devicename}}` of `Serial number is {{serialnumber}}` invoeren met accolades. De lijst [iOS-tokens](../apps/app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) bevat de beschikbare tokens die kunnen worden gebruikt.
Het gedeelte [Instellingen om berichten op het vergrendelingsscherm weer te geven](../configuration/ios-device-features-settings.md#lock-screen-message) bevat de huidige instellingen.

#### <a name="new-app-store-doc-viewing-gaming-device-restriction-settings-added-to-ios-devices---2827760--"></a>Nieuwe App Store-, documentweergave-, gaminginstellingen voor apparaatbeperking toegevoegd aan iOS-apparaten<!-- 2827760-->
In **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** als platform > **Apparaatbeperkingen** als profieltype > **App Store, documentweergave, gaming** zijn de volgende instellingen toegevoegd: Toestaan dat beheerde apps contactpersonen schrijven naar niet-beheerde contactenaccounts Toestaan dat niet-beheerde apps contactpersonen lezen in beheerde accounts voor contactpersonen Als u de instellingen wilt weergeven, gaat u naar [iOS-apparaatbeperkingen](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming).

#### <a name="new-notification-hints-and-keyguard-settings-to-android-enterprise-device-owner-devices---3201839-3201843---"></a>Nieuwe instellingen voor meldingen, hints en keyguard voor Android Enterprise-apparaten in zakelijk eigendom<!-- 3201839 3201843 -->
Deze update omvat verschillende nieuwe functies in Android Enterprise-apparaten wanneer deze worden uitgevoerd in zakelijk eigendom. Als u deze functies wilt gebruiken, gaat u naar **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > als **Platform** kiest u **Android Enterprise** > in **Profieltype** kiest u **Alleen zakelijk eigendom** > **Apparaatbeperkingen**.

Nieuwe functies omvatten:

- Systeemmeldingen uitschakelen, waaronder binnenkomende oproepen, systeemwaarschuwingen, systeemfouten en meer.
- Suggestie om zelfstudies en tips over te slaan voor apps die voor de eerste keer worden geopend.
- Geavanceerde keyguard-instellingen uitschakelen, bijvoorbeeld de camera, meldingen, ontgrendelen met vingerafdruk en meer.

Ga naar [Android Enterprise device restriction settings](../configuration/device-restrictions-android-for-work.md) (Apparaatbeperkingsinstellingen voor Android Enterprise-apparaten) om de instellingen wilt bekijken.

#### <a name="android-enterprise-device-owner-devices-can-use-always-on-vpn-connections---3202194---"></a>Android Enterprise-apparaten in zakelijk eigendom kunnen AlwaysOn-VPN-verbindingen gebruiken<!-- 3202194 -->
In deze update kunt u ingeschakelde VPN-verbindingen gebruiken op Android Enterprise-apparaten in zakelijk eigendom. Altijd ingeschakelde VPN-verbindingen blijven verbonden en maken direct opnieuw verbinding wanneer gebruikers hun apparaat ontgrendelen, het apparaat opnieuw wordt opgestart of het draadloze netwerk wordt gewijzigd. U kunt de verbinding ook in de vergrendelingsmodus zetten. Hiermee wordt al het netwerkverkeer geblokkeerd totdat de VPN-verbinding actief is.
U vindt altijd ingeschakelde VPN in **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** voor platform > **Apparaatbeperkingen** voor apparaten in zakelijk eigendom > **Connectiviteit**. Ga naar [Android Enterprise device restriction settings](../configuration/device-restrictions-android-for-work.md) (Apparaatbeperkingsinstellingen voor Android Enterprise-apparaten) om de instellingen wilt bekijken.

#### <a name="new-setting-to-end-processes-in-task-manager-on-windows-10-devices---3285177---"></a>Nieuwe instelling om processen in Taakbeheer in Windows 10-apparaten te beëindigen<!-- 3285177 --> 
Deze update omvat een nieuwe instelling om processen via Taakbeheer in Windows 10-apparaten te beëindigen. Met behulp van een apparaatconfiguratieprofiel (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > als **Platform** kiest u **Windows 10** > in **Profieltype** kiest u **Apparaatbeperkingen** > **Algemene** instellingen) kunt u deze instellingen toestaan of blokkeren.
Ga naar [Apparaatbeperkingsinstellingen voor Windows 10-apparaten](../configuration/device-restrictions-windows-10.md) als u de instellingen wilt bekijken.
Van toepassing op: Windows 10 en hoger

#### <a name="use-microsoft-recommended-settings-with-security-baselines-public-preview---2055484-----"></a>Door Microsoft aanbevolen instellingen gebruiken met beveiligingsbasislijnen (openbare preview)<!-- 2055484   -->

Intune is geïntegreerd met andere services die op beveiliging gericht zijn, inclusief Windows Defender ATP en Office 365 ATP. Klanten vragen om een gemeenschappelijke strategie en een samenhangende set van end-to-end beveiligingsworkflows voor alle Microsoft 365-diensten. Ons doel is om strategieën af te stemmen en oplossingen te ontwikkelen die beveiligingsactiviteiten en gebruikelijke beheerderstaken combineren. In Intune willen we dit doel bereiken door het publiceren van een set beveiligingsbasislijnen die door Microsoft zijn aanbevolen (**Intune** >  **Beveiligingsbasislijnen**).  Beheerders kunnen direct op basis van deze basislijnen een beveiligingsbeleid opstellen en dit vervolgens voor hun gebruikers implementeren. U kunt ook de aanbevelingen voor procedures aanpassen aan de behoeften van uw organisatie. Intune zorgt ervoor dat apparaten deze basislijnen blijven naleven, en waarschuwt beheerders wanneer gebruikers of apparaten van de basislijnen afwijken.

Deze functie is beschikbaar als openbare preview, dus alle profielen die nu worden gemaakt, worden niet verplaatst naar beveiligingsbasislijnsjablonen die algemeen beschikbaar zijn. U moet deze previewsjablonen niet voor uw productieomgeving gebruiken.

Zie [Een Windows 10-beveiligingsbasislijn maken in Intune](../protect/security-baselines-monitor.md) voor meer informatie over beveiligingsbasislijnen.

Deze functie is van toepassing op: Windows 10 en hoger

#### <a name="non-administrators-can-enable-bitlocker-on-windows-10-devices-joined-to-azure-ad---2147379-----"></a>Niet-beheerders kunnen BitLocker gebruiken op Windows 10-apparaten die zijn gekoppeld aan Azure AD<!-- 2147379   -->
Wanneer u BitLocker-instellingen op Windows 10-apparaten inschakelt (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** als platform en **Endpoint Protection** als profieltype > **Windows-versleuteling**), voegt u BitLocker-instellingen toe.

Deze update bevat een nieuwe BitLocker-instellingen waarmee standaardgebruikers (niet-beheerders) versleuteling kunnen inschakelen.

Ga naar [Instellingen voor de beveiliging van eindpunten voor Windows 10](../protect/endpoint-protection-windows-10.md#windows-encryption) om de instellingen te bekijken.

#### <a name="check-for-configuration-manager-compliance---2192052--eepublished----"></a>Controleren op Configuration Manager-compatibiliteit<!-- 2192052  eepublished  -->
Deze update bevat een nieuwe instelling voor Configuration Manager-compatibiliteit (**Apparaatcompatibiliteit** > **Beleid** > **Beleid maken** > **Windows 10 en hoger** > **Configuration Manager-compatibiliteit**). Configuration Manager verzendt signalen naar Intune-naleving. Met deze instelling kunt u vereisen dat alle Configuration Manager-signalen de waarde 'compatibel' retourneren.

U kunt bijvoorbeeld vereisen dat alle software-updates worden geïnstalleerd op apparaten. Deze vereiste heeft in Configuration Manager de status 'Geïnstalleerd'. Als programma's op het apparaat een onbekende status hebben, is het apparaat niet-compatibel in Intune.

In [Configuration Manager-compatibiliteit](../protect/compliance-policy-create-windows.md#configuration-manager-compliance) wordt deze instelling beschreven.

Van toepassing op: Windows 10 en hoger

#### <a name="customize-wallpaper-on-supervised-ios-devices-using-a-device-configuration-profile---2809324-----"></a>Achtergronden op iOS-apparaten die onder toezicht staan aanpassen met behulp van een apparaatconfiguratieprofiel<!-- 2809324   -->
Wanneer u een apparaatconfiguratieprofiel voor iOS-apparaten maakt, kunt u sommige functies aanpassen (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **Apparaatfuncties** voor profieltype). Deze update bevat nieuwe **achtergrond**instellingen waarmee een beheerder een .png-, .jpg- of .jpeg-afbeelding op het startscherm of het vergrendelingsscherm kan gebruiken. Deze achtergrondinstellingen zijn alleen van toepassing op apparaten die onder supervisie staan. 

Zie [Instellingen van apparaatfuncties voor iOS](../configuration/ios-device-features-settings.md) voor een lijst met deze instellingen.

#### <a name="windows-10-kiosk-is-generally-available---3594661----"></a>Windows 10-kiosk is algemeen beschikbaar<!-- 3594661  -->
In deze update is de Kiosk-functie in Windows 10 en hoger algemeen beschikbaar. Zie [Kiosk-instellingen voor Windows 10 (en hoger)](../configuration/kiosk-settings.md) voor alle instellingen die u kunt toevoegen en configureren.

#### <a name="contact-sharing-via-bluetooth-is-removed-in-device-restrictions--device-owner-for-android-enterprise---3598396-----"></a>Contactpersonen delen via Bluetooth wordt verwijderd uit Apparaatbeperkingen > Apparaateigenaar voor Android Enterprise<!-- 3598396   -->
Wanneer u een apparaatbeperkingsbeleid voor Android Enterprise-apparaten maakt, is de instelling **Contactpersoon delen via Bluetooth** beschikbaar. In deze update is de instelling **Contactpersoon delen via Bluetooth** verwijderd (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** voor platform > **Apparaatbeperkingen > Apparaateigenaar** voor Profieltype > **Algemeen**).

De instelling **Contactpersoon delen via Bluetooth** wordt niet ondersteund voor het beheer van Android Enterprise-apparaateigenaren. Wanneer deze instelling wordt verwijderd, heeft dit dus geen invloed op apparaten of tenants, zelfs als deze instelling is ingeschakeld en geconfigureerd in uw omgeving.

Ga naar [Met Android Enterprise-apparaatinstellingen functies toestaan of beperken](../configuration/device-restrictions-android-for-work.md) voor de huidige lijst met instellingen.

Van toepassing op: Android Enterprise-apparaateigenaar


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="more-detailed-enrollment-restriction-failure-messaging---3111564---"></a>Gedetailleerdere berichten over fouten bij inschrijvingsbeperking<!-- 3111564 -->
Er komen meer gedetailleerdere foutberichten beschikbaar wanneer er niet wordt voldaan de inschrijvingsbeperkingen. Als u deze berichten wilt bekijken, gaat u naar **Intune** > **Probleemoplossing** en bekijkt u het tabel Inschrijvingsfouten. Zie de [lijst met mislukte inschrijvingen](help-desk-operators.md#enrollment-failure-reference) voor meer informatie.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Apparaatbeheer
#### <a name="preview-of-support-for-android-corporate-owned-fully-managed-devices---1574342----"></a>Voorbeeld van volledig beheerde, zakelijke Android-apparaten<!-- 1574342  -->
Intune ondersteunt nu volledig beheerde Android-apparaten, een scenario waarin apparaten 'zakelijk eigendom' zijn en nauw worden beheerd door de IT-afdeling en gekoppeld zijn aan afzonderlijke gebruikers. Hierdoor kunnen beheerders het hele apparaat beheren, een uitgebreide reeks beleidscontroles afdwingen die niet beschikbaar zijn voor werkprofielen en gebruikers beperken tot de installatie van apps uit de beheerde Google Play Store. Zie [Intune-inschrijving van volledig beheerde Android-apparaten instellen](../enrollment/android-fully-managed-enroll.md) en [Uw toegewezen apparaten of volledig beheerde apparaten inschrijven](../enrollment/android-dedicated-devices-fully-managed-enroll.md) voor meer informatie.  Let op: deze functie wordt momenteel als preview aangeboden. Sommige Intune-mogelijkheden, zoals certificaten, naleving en voorwaardelijke toegang, zijn momenteel niet beschikbaar voor volledig beheerde Android-gebruikersapparaten.

#### <a name="selective-wipe-support-for-wip-without-enrollment-devices---1434452---"></a>Ondersteuning voor selectief wissen voor WIP Without Enrollment-apparaten<!-- 1434452 -->
Met Windows Information Protection Without Enrollment (WIP-WE) kunnen klanten hun bedrijfsgegevens op Windows 10-apparaten beveiligen zonder gebruik te maken van volledige MDM-inschrijving. Zodra documenten met WIP-WE-beleid zijn beveiligd, kunnen de beschermde gegevens selectief worden gewist door een Intune-beheerder. Door een gebruiker en een apparaat te selecteren en een wisaanvraag te versturen, worden alle gegevens onbruikbaar die met het WIP-WE-beleid zijn beschermd. Vanuit Intune in de Azure-portal selecteert u hiervoor **Mobiele app** > **App selectief wissen**.


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="tenant-status-dashboard---1124854---"></a>Dashboard Tenantstatus<!-- 1124854 -->
De nieuwe [pagina Tenantstatus](tenant-status.md) biedt één locatie waar u de status en gerelateerde details voor uw tenant kunt bekijken.  Het dashboard is opgedeeld in vier gebieden:
- **Tenantdetails**: bevat uiteenlopende informatie, zoals uw tenantnaam en -locatie, uw MDM-instantie, het totale aantal ingeschreven apparaten in uw tenant en uw aantal licenties. Dit gedeelte bevat ook de huidige servicerelease voor uw tenant.
- **Connectorstatus**: bevat informatie over de beschikbare connectors die u hebt geconfigureerd. Daarnaast kunt u die connectors vermelden die u nog niet hebt ingeschakeld.  
   Op basis van de huidige status worden de connectors gemarkeerd als In orde, Waarschuwing of Niet in orde. Selecteer een connector die u gedetailleerd wilt analyseren om details of aanvullende informatie voor de connector weer te geven.
- **Intune Service Health**: bevat gedetailleerde informatie over actieve incidenten of storingen voor uw tenant. De informatie in deze sectie wordt rechtstreeks opgehaald uit het Office Message Center.
- **Intune-nieuws** : bevat actieve berichten voor uw tenant. Berichten omvatten onder andere meldingen wanneer uw tenant de nieuwste functies van Intune ontvangt.  De informatie in deze sectie wordt rechtstreeks opgehaald uit het Office Message Center.

#### <a name="new-help-and-support-experience-in-company-portal-for-windows-10---1488939--"></a>Nieuw Help en ondersteuning-ervaring in de bedrijfsportal voor Windows 10<!-- 1488939-->
Gebruikers kunnen de nieuwe pagina Help en ondersteuning van Bedrijfsportal gebruiken om problemen op te lossen en hulp te vragen voor app- en toegangsproblemen. Via deze pagina kunnen gebruikers details uit foutenlogboeken en diagnostisch logboeken mailen en kunnen ze de gegevens van de helpdesk van de organisatie vinden. Daarnaast bevat de pagina een gedeelte met veelgestelde vragen met koppelingen naar de relevante Intune-documentatie.

#### <a name="new-help-and-support-experience-for-intune---3307080---"></a>Nieuwe Help en ondersteuning-ervaring voor Intune<!-- #3307080 -->
De nieuwe Help en ondersteuning-ervaring wordt de komende paar dagen uitgerold naar alle tenants. Deze nieuwe ervaring is beschikbaar voor Intune en is toegankelijk wanneer de Intune-blades in [Azure Portal](https://portal.azure.com/) worden gebruikt.
Met de nieuwe ervaring kunt u uw probleem in uw eigen woorden beschrijven en informatie over probleemoplossing en op internet gevonden informatie over het oplossen van het probleem ontvangen. Deze oplossingen worden aangeboden via een op regels gebaseerde machine learning-algoritme, dat wordt aangestuurd door zoekvragen van gebruikers. Naast informatie die specifiek is voor problemen kunt u gebruikmaken van de nieuwe werkstroom voor het openen van een ondersteuningsvraag via e-mail of telefoon. Deze nieuwe ervaring vervangt de vorige Help en ondersteuning-ervaring die bestaat uit een statistische verzameling vooraf geselecteerde opties die zijn gebaseerd op het gebied van de console waarin u zich bevindt wanneer u Help en ondersteuning opent.
Zie [Ondersteuning voor Microsoft Intune krijgen](get-support.md) voor meer informatie.

#### <a name="new-operational-logs-and-ability-to-send-logs-to-azure-monitor-services---3762211----"></a>Nieuwe operationele logboeken en de mogelijkheid om logboeken te verzenden met Azure Monitor-services<!-- 3762211  -->
Intune beschikt over ingebouwde logboekregistratie waarmee gebeurtenissen worden bijgehouden als wijzigingen worden aangebracht. Deze update bevat nieuwe functies voor logboekregistratie, waaronder: 
- Operationele logboeken (preview), waarin details over gebruikers en apparaten die zich hebben geregistreerd worden weergegeven, inclusief geslaagde en mislukte pogingen.
- Deze auditlogboeken en operationele logboeken kunnen worden verzonden naar Azure Monitor-services, inclusief Storage Accounts, Event Hubs, en Log Analytics. Met deze services kunt u opslaan, analytics als Splunk en QRadar gebruiken en visualisaties van uw logboekregistratiegegevens verkrijgen.

In [Logboekgegevens verzenden naar Storage, Event Hubs of Log Analytics in Intune](../review-logs-using-azure-monitor.md) vindt u meer informatie over deze functie.

#### <a name="skip-more-setup-assistant-screens-on-an-ios-dep-device---2687509----"></a>Meer Setup Assistant-schermen overslaan op een iOS-DEP-apparaat<!-- 2687509  -->
Naast de schermen die u op dit moment kunt overslaan, kunt u instellen dat iOS DEP-apparaten de volgende schermen in de Setup-assistent overslaan wanneer een gebruiker het apparaat registreert: Weergavetoon, Privacy, Android-migratie, Startknop, iMessage en FaceTime, Onboarding, Migratie weergeven, Weergave, Schermtijd, Software-update, SIM-installatie.
Als u wilt kiezen welke schermen moeten worden overgeslagen, gaat u naar **Apparaatinschrijving** > **Apple-inschrijving** > **Tokens voor inschrijvingsprogramma** > kies een token > **Profielen** > kies een profiel > **Eigenschappen** > **Setup Assistant aanpassen** > kies **Verbergen** voor schermen die u wilt overslaan > **OK**.
Als u een nieuw profiel maakt of een profiel bewerkt, moeten de geselecteerde skip-schermen worden gesynchroniseerd met de Apple MDM-server. Gebruikers kunnen de opdracht tot een handmatige synchronisatie van de apparaten geven, zodat er geen vertraging in het ophalen van de profielwijzigingen is.

#### <a name="android-enterprise-app-we-app-deployment---1171203---"></a>Android Enterprise APP WE-app-implementatie<!-- 1171203 -->
Voor Android-apparaten in een niet-geregistreerd APP-WE-implementatiescenario (App Protection Policy Without Enrollment), gebruikt u de beheerde Google Play Store om store-apps en LOB-apps te implementeren bij gebruikers. In het bijzonder kunt u eindgebruikers voorzien van een app-catalogus en een installatie waarbij het niet langer nodig is dat eindgebruikers de beveiligingsstatus van hun apparaten versoepelen door installaties uit onbekende bronnen toe te staan. Bovendien biedt dit implementatiescenario een verbeterde eindgebruikerservaring.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer

#### <a name="scope-tags-for-apps---1081941---"></a>Bereiktags voor apps<!-- 1081941 -->
U kunt bereiktags maken om de toegang voor rollen en apps te beperken. U kunt een bereiktag toevoegen aan een app, zodat alleen personen met rollen die ook zijn toegewezen aan de bereiktag, toegang tot de app hebben. Momenteel kunnen er geen bereiktags worden toegewezen aan apps die vanuit de beheerde Google Play Store aan Intune zijn toegevoegd of aan apps die met behulp van het Apple Volume Purchase Program (VPP) zijn aangeschaft (er zijn wel plannen voor ondersteuning in de toekomst). Zie [Bereiktags gebruiken om beleidsregels te filteren](scope-tags.md) voor meer informatie.




<!-- ########################## -->
## <a name="december-2018"></a>December 2018

### <a name="app-management"></a>Appbeheer

#### <a name="updates-for-application-transport-security---748318---"></a>Updates voor Application Transport Security<!-- 748318 -->

Microsoft Intune ondersteunt Transport Layer Security (TLS) 1.2+ voor de best mogelijke codering, om ervoor te zorgen dat Intune standaard veiliger is en ook is afgestemd op andere Microsoft-services, zoals Microsoft Office 365. Om aan deze eis te voldoen, dwingen de iOS- en macOS-bedrijfsportals de bijgewerkte Application Transport Security (ATS)-eisen van Apple af, die ook TLS 1.2+ vereisen. ATS wordt gebruikt om betere beveiliging af te dwingen voor alle app-communicatie die verloopt via HTTPS. Deze wijziging heeft gevolgen voor Intune-klanten die de bedrijfsportal-apps gebruiken op iOS en macOS. Zie de [Intune-ondersteuningsblog](https://aka.ms/compportalats)voor meer informatie.

#### <a name="the-intune-app-sdk-will-support-256-bit-encryption-keys---1832174---"></a>De Intune App-SDK ondersteunt 256-bits versleutelingssleutels<!-- 1832174 -->
De Intune App-SDK voor Android gebruikt nu 256-bits versleutelingssleutels wanneer versleuteling is ingeschakeld door app-beveiligingsbeleid. De SDK biedt doorgaande ondersteuning voor 128-bits sleutels voor compatibiliteit met inhoud en apps die gebruikmaken van oudere SDK-versies.

#### <a name="microsoft-auto-update-version-450-required-for-macos-devices---3503442---"></a>Microsoft AutoUpdate versie 4.5.0 vereist voor macOS-apparaten<!-- 3503442 -->
Als u updates voor de app Bedrijfsportal en andere Office-toepassingen wilt blijven ontvangen, moeten macOS-apparaten die worden beheerd door Intune, upgraden naar Microsoft AutoUpdate 4.5.0. Gebruikers hebben deze versie mogelijk al voor hun Office-apps.

### <a name="device-management"></a>Apparaatbeheer

#### <a name="intune-requires-macos-1012-or-later---2827778---"></a>Voor Intune is macOS 10.12 of hoger vereist<!-- 2827778 -->
Voor Intune is nu macOS versie 10.12 of hoger vereist. Apparaten met eerdere versies van macOS kunnen de app Bedrijfsportal niet gebruiken voor registratie bij Intune. Gebruikers die ondersteuning en nieuwe functies willen krijgen, moeten hun apparaat upgraden naar macOS 10.12 of hoger en de bedrijfsportal-app naar de nieuwste versie upgraden.

<!-- ########################## -->
## <a name="november-2018"></a>November 2018

### <a name="app-management"></a>Appbeheer

#### <a name="uninstalling-apps-on-corporate-owned-supervised-ios-devices---1281677---"></a>Apps verwijderen op onder supervisie staande iOS-apparaten in bedrijfseigendom<!-- 1281677 -->
U kunt alle apps op onder supervisie staande iOS-apparaten in bedrijfseigendom verwijderen. U kunt alle apps verwijderen voor gebruikers- of apparaatgroepen met het toewijzingstype **Verwijderen**. Voor persoonlijke of niet onder supervisie staande iOS-apparaten kunt u nog steeds alleen de apps verwijderen die zijn geïnstalleerd met behulp van Intune.

#### <a name="downloading-intune-win32-app-content---2617320---"></a>Intune Win32-app-inhoud downloaden<!-- 2617320 -->
Clients van Windows 10 RS3 en hoger downloaden Intune Win32-app-inhoud via een Delivery Optimization-onderdeel in de Windows 10-client. Delivery Optimization biedt peer-to-peer-functionaliteit die standaard is ingeschakeld. Momenteel kan Delivery Optimization worden geconfigureerd via groepsbeleid. Raadpleeg [Delivery Optimization voor Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) voor meer informatie.

#### <a name="end-user-device-and-app-content-menu---2771453---"></a>Apparaat- en app-inhoudmenu voor eindgebruikers<!-- 2771453 -->
Eindgebruikers kunnen nu het contextmenu van apparaten en apps gebruiken om veelvoorkomende acties te activeren, zoals de naam van een apparaat wijzigen of de nalevingsstatus controleren.

#### <a name="set-custom-background-in-managed-home-screen-app----3041945---"></a>Aangepaste achtergrond in de app voor het beheerde startscherm instellen <!-- 3041945 -->
We voegen een instelling toe waarmee u de achtergrond van de app voor het beheerde startscherm op Android Enterprise-apparaten in de kioskmodus voor meerdere apps kunt aanpassen.  Om de **Aangepaste URL-achtergrond** te configureren, gaat u naar Intune in de Azure-portal > Apparaatconfiguratie. Selecteer een huidig apparaatconfiguratieprofiel of maak een nieuw profiel als u de kioskinstellingen wilt bewerken.
Raadpleeg [Android Enterprise-apparaatbeperkingen](../configuration/device-restrictions-android-for-work.md) voor de kioskinstellingen.

#### <a name="app-protection-policy-assignment-save-and-apply---3104570---"></a>Beleidstoewijzing voor app-beveiliging opslaan en toepassen<!-- 3104570 -->
U hebt nu meer controle over uw [beleidstoewijzingen voor app-beveiliging](../apps/app-protection-policies.md). Wanneer u *Toewijzingen* selecteert om de toewijzingen van een beleid in te stellen, moet u uw configuratie **Opslaan** voordat de wijziging wordt toegepast. Gebruik **Verwijderen** om alle wijzigingen die u maakt te verwijderen zonder wijzigingen aan de lijsten Opnemen of Uitsluiten op te slaan.  Door Opslaan of Verwijderen te vereisen, krijgen alleen de door u beoogde gebruikers een beveiligingsbeleid voor apps toegewezen.

#### <a name="new-microsoft-edge-browser-settings-for-windows-10-and-later---3174639---"></a>Nieuwe Microsoft Edge-browserinstellingen voor Windows 10 en hoger<!-- 3174639 -->
Deze update bevat nieuwe instellingen om de Microsoft Edge-browser op uw apparaten te controleren en te beheren. Raadpleeg [Apparaatbeperkingsinstellingen voor Windows 10 (en hoger)](../configuration/device-restrictions-windows-10.md#microsoft-edge-browser) voor een lijst met deze instellingen.

#### <a name="new-apps-support-with-app-protection-policies---3330037---"></a>Ondersteuning voor nieuwe apps met beveiligingsbeleid voor apps<!-- 3330037 -->
U kunt nu de volgende apps beheren met [Intune-beveiligingsbeleid voor apps](../apps/app-protection-policies.md):
- Stream (iOS)
- To DO (Android, iOS)
- PowerApps (Android, iOS)
- Flow (Android, iOS)

Gebruik beveiligingsbeleid voor apps om zakelijke gegevens te beschermen en gegevensoverdracht voor deze apps te controleren, zoals voor andere door beleid beheerde Intune-apps. Opmerking: Als Flow nog niet zichtbaar is in de console, voegt u Flow toe wanneer u app-beveiligingsbeleid maakt of bewerkt. Gebruik hiervoor de optie **+ Meer apps** en geef vervolgens de *App-ID* voor Flow op in het invoerveld. Gebruik voor Android *com.microsoft.flow* en voor iOS *com.microsoft.procsimo*.


### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="support-for-ios-12-oauth-in-ios-email-profiles--2155106---"></a>Ondersteuning van iOS 12 OAuth in iOS-e-mailprofielen<!--2155106 -->
iOS-e-mailprofielen van Intune ondersteunen iOS 12 Open Authorization (OAuth). Maak een nieuw profiel (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **E-mail** voor profieltype) of werk een bestaand e-mailprofiel voor iOS bij. Als u OAuth inschakelt in een profiel dat al naar gebruikers is geïmplementeerd, wordt gebruikers gevraagd de verificatie opnieuw uit te voeren en hun e-mail opnieuw te downloaden.

[iOS-e-mailprofielen](../configuration/email-settings-ios.md) biedt meer informatie over het gebruik van OAuth in een e-mailprofiel.

#### <a name="network-access-control-nac-support-for-citrix-sso-for-ios---3259404---"></a>Ondersteuning bij netwerktoegangsbeheer (NAC) voor Citrix SSO voor iOS<!-- 3259404 -->
Citrix heeft een update van Citrix Gateway uitgebracht voor netwerktoegangsbeheer (NAC) voor Citrix SSO voor iOS in Intune. U kunt ervoor kiezen om een apparaat-id op te nemen in een VPN-profiel in Intune en vervolgens dit profiel te pushen naar uw iOS-apparaten. U moet de nieuwste update van Citrix Gateway installeren om deze functionaliteit te kunnen gebruiken.

[VPN-instellingen configureren op iOS-apparaten](../configuration/vpn-settings-ios.md#base-vpn-settings) biedt meer informatie over het gebruik van NAC, waaronder enkele aanvullende vereisten. 

#### <a name="ios-and-macos-version-numbers-and-build-numbers-are-shown---1892471---"></a>iOS- en macOS-versienummers en buildnummers worden weergegeven<!-- 1892471 -->
In **Apparaatcompatibiliteit** > **Apparaatcompatibiliteit** worden de versies van het iOS- en macOS-besturingssysteem weergegeven en zijn beschikbaar voor gebruik in compatibiliteitsbeleid. Deze update omvat het buildnummer, dat voor beide platformen configureerbaar is.
Wanneer er beveiligingsupdates worden uitgebracht, laat Apple doorgaans het versienummer ongewijzigd, maar wordt het buildnummer wel bijgewerkt. Door het buildnummer in een compatibiliteitsbeleid te gebruiken, kunt u eenvoudig controleren of een beveiligingsupdate is geïnstalleerd.
Raadpleeg het nalevingsbeleid van [iOS](../protect/compliance-policy-create-ios.md#device-health) en [macOS](../protect/compliance-policy-create-mac-os.md#device-properties) om deze functie te gebruiken.

#### <a name="update-rings-are-being-replaced-with-delivery-optimization-settings-for-windows-10-and-later---2753807---"></a>Update-ringen worden vervangen door Delivery Optimization-instellingen voor Windows 10 en hoger<!-- 2753807 -->
Delivery Optimization is een nieuw configuratieprofiel voor Windows 10 en hoger. Deze functie biedt een meer gestroomlijnde ervaring om softwareupdates op apparaten in uw organisatie te installeren. Deze update helpt u ook om met behulp van een configuratieprofiel de instellingen in nieuwe en bestaande update-ringen te implementeren.
Raadpleeg [Delivery Optimization-instellingen voor Windows 10 (en hoger)](../configuration/delivery-optimization-windows.md) om een Delivery Optimization-configuratieprofiel te configureren.

#### <a name="new-device-restriction-settings-added-to-ios-and-macos-devices---2827760---"></a>Nieuwe apparaatbeperkingsinstellingen voor iOS en macOS-apparaten toegevoegd<!-- 2827760 -->
Deze update bevat nieuwe instellingen voor uw iOS- en macOS-apparaten die zijn uitgebracht met iOS 12:

**iOS-instellingen**: 
- Algemeen: verwijdering van apps blokkeren (alleen onder supervisie)
- Algemeen: beperkte USB-modus blokkeren (alleen onder supervisie)
- Algemeen: automatisch datum en tijd afdwingen (alleen onder supervisie)
- Wachtwoord: automatisch wachtwoorden doorvoeren blokkeren (alleen onder supervisie)
- Wachtwoord: aanvragen voor wachtwoordnabijheid blokkeren (alleen onder supervisie)
- Wachtwoord: wachtwoorden delen blokkeren (alleen onder supervisie)

**macOS-instellingen**: 
- Wachtwoord: automatisch doorvoeren van wachtwoorden blokkeren
- Wachtwoord: aanvragen voor wachtwoordnabijheid blokkeren
- Wachtwoord: delen van wachtwoorden blokkeren

Voor meer informatie over deze instellingen, zie apparaatbeperkingsinstellingen voor [iOS](../configuration/device-restrictions-ios.md) en [macOS](../configuration/device-restrictions-macos.md).

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="autopilot-support-for-hybrid-azure-active-directory-joined-devices-preview---1048100--"></a>Autopilot-ondersteuning voor hybride apparaten die zijn toegevoegd aan Azure Active Directory (preview)<!-- 1048100-->
U kunt nu hybride apparaten die aan Azure Active Directory zijn toegevoegd, instellen met behulp van Autopilot. Apparaten moeten aan het netwerk van uw organisatie zijn toegevoegd om de hybride Autopilot-functie te kunnen gebruiken. Zie [Hybride apparaten die aan Azure Active Directory zijn toegevoegd implementeren met Intune en Windows Autopilot](../enrollment/windows-autopilot-hybrid.md) voor meer informatie.
Deze functie komt de komende paar dagen beschikbaar voor onze gebruikers. Daarom kunt u deze stappen pas volgen als de functie beschikbaar is voor uw account.

#### <a name="select-apps-tracked-on-the-enrollment-status-page---2531007---"></a>Apps die worden bijgehouden op de pagina Status van inschrijving selecteren<!-- 2531007 -->
U kunt kiezen welke apps worden bijgehouden in de pagina Status van inschrijving. Totdat deze apps zijn geïnstalleerd, kan de gebruiker het apparaat niet gebruiken. Raadpleeg [Een pagina voor de status van de inschrijving instellen](../enrollment/windows-enrollment-status.md) voor meer informatie.

#### <a name="search-for-autopilot-device-by-serial-number--2595788---"></a>Op serienummer zoeken naar een Autopilot-apparaat<!--2595788 -->
U kunt nu op serienummer zoeken naar Autopilot-apparaten. Kies hiervoor **Apparaatinschrijving** > **Windows-inschrijving** > **Apparaten** > voer een serienummer in het venster **Zoeken op serienummer** in > druk op Enter.

#### <a name="track-installation-of-office-proplus--2620217---"></a>Installatie van Office ProPlus bijhouden<!--2620217 -->
Gebruikers kunnen de voortgang van de installatie van [Office ProPlus](../apps/apps-add-office365.md) bijhouden met behulp van de [Pagina Status van inschrijving](../enrollment/windows-enrollment-status.md). Raadpleeg [Een pagina voor de status van de inschrijving instellen](../enrollment/windows-enrollment-status.md) voor meer informatie.

#### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low---2237572---"></a>Meldingen voor verlopend VPP-token of onvoldoende bedrijfsportal-licenties<!-- 2237572 -->
Als u het Volume Purchase Program (VPP) gebruikt om de Bedrijfsportal vooraf in te richten tijdens DEP-inschrijving, waarschuwt Intune u wanneer het VPP-token bijna verloopt en wanneer er bijna te weinig licenties zijn voor de Bedrijfsportal.

#### <a name="macos-device-enrollment-program-support-for-apple-school-manager-accounts--3006133---"></a>Ondersteuning voor het macOS Device Enrollment Program voor Apple School Manager-accounts<!--3006133 -->
Intune ondersteunt nu het gebruik van het Device Enrollment Program op macOS-apparaten voor Apple School Manager-accounts.  Raadpleeg [MacOS-apparaten automatisch inschrijven met het Device Enrollment Program van Apple School Manager](../enrollment/device-enrollment-program-enroll-macos.md) voor meer informatie.

#### <a name="new-intune-device-subscription-sku--3312071--"></a>Nieuwe apparaatabonnements-SKU van Intune<!--3312071-->
Er is nu een nieuwe, op apparaten gebaseerde abonnements-SKU beschikbaar om de kosten van apparaatbeheer in ondernemingen te verlagen. Deze apparaat-SKU van Intune biedt licenties per apparaat op maandbasis. De prijs varieert per licentieprogramma. Deze is direct beschikbaar via de Microsoft 365-beheercentrum en via de [Enterprise Agreement](https://www.microsoft.com/licensing/licensing-programs/enterprise?activetab=enterprise-tab:primaryr2) (EA), [Microsoft Products and Services Agreement](https://www.microsoft.com/licensing/mpsa/default) (MPSA) [Microsoft Open Agreements](https://partner.microsoft.com/licensing/licensing-agreements) en [Cloud Solution Provider](https://www.microsoftpartnercommunity.com/t5/Partnership-101/What-is-the-Cloud-Solution-Provider-CSP-program/td-p/2453) (CSP).

### <a name="device-management"></a>Apparaatbeheer

#### <a name="temporarily-pause-kiosk-mode-on-android-devices-to-make-changes---3041935---"></a>Kioskmodus op Android-apparaten tijdelijk onderbreken om wijzigingen aan te brengen<!-- 3041935 -->
Wanneer u Android-apparaten in de kioskmodus voor meerdere apps gebruikt, moet de IT-beheerder mogelijk wijzigingen aanbrengen aan het apparaat. Deze update omvat nieuwe instellingen voor kiosken voor meerdere apps waarmee de IT-beheerder de kioskmodus tijdelijk kan onderbreken met behulp van een pincode om toegang tot het hele apparaat te krijgen.
Raadpleeg [Android Enterprise-apparaatbeperkingen](../configuration/device-restrictions-android-for-work.md) voor de kioskinstellingen.

#### <a name="enable-virtual-home-button-on-android-enterprise-kiosk-devices----3042021---"></a>Virtuele startknop op kioskapparaten voor Android Enterprise inschakelen <!-- 3042021 -->
Met een nieuwe instelling kunnen gebruikers op een soft-keyknop op hun apparaat tikken om over te schakelen tussen de app voor het beheerde startscherm en andere toegewezen apps op hun kioskapparaat voor meerdere apps. Deze instelling is vooral handig in scenario's waarbij de kiosk-app van een gebruiker niet op de juiste wijze op de knop 'Terug' reageert. U kunt deze instelling configureren voor Android-apparaten in bedrijfseigendom voor eenmalig gebruik. Om de **Virtuele startknop** in of uit te schakelen, gaat u naar Intune in Azure Portal > Apparaatconfiguratie. Selecteer een huidig apparaatconfiguratieprofiel of maak een nieuw profiel als u de kioskinstellingen wilt bewerken.
Raadpleeg [Android Enterprise-apparaatbeperkingen](../configuration/device-restrictions-android-for-work.md) voor de kioskinstellingen.




<!-- ########################## -->
## <a name="october-2018"></a>Oktober 2018

### <a name="app-management"></a>Appbeheer

#### <a name="access-to-key-profile-properties-using-the-company-portal-app---772203---"></a>Toegang tot belangrijke profieleigenschappen met behulp van de bedrijfsportal-app<!-- 772203 -->
Eindgebruikers hebben nu toegang tot belangrijke accounteigenschappen en -acties, zoals het wachtwoord opnieuw instellen, vanuit de bedrijfsportal-app. 

#### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios---1248481---"></a>Toetsenborden van derden kunnen worden geblokkeerd door APP-instellingen op iOS<!-- 1248481 -->
Op iOS-apparaten kunnen Intune-beheerders het gebruik blokkeren van toetsenborden van derden bij het benaderen van organisatiegegevens in door beleid beveiligde apps. Wanneer het Application Protection Policy (APP; app-beveiligingsbeleid) is ingesteld om toetsenborden van derden te blokkeren, ontvangt de gebruiker een bericht als hij de eerste keer met bedrijfsgegevens werkt met een toetsenbord van derden. Alle opties, behalve het systeemeigen toetsenbord, worden geblokkeerd en zijn niet zichtbaar voor apparaatgebruikers. Apparaatgebruikers zien het dialoogvenster slechts één keer. 

#### <a name="user-account-access-of-intune-apps-on-managed-android-and-ios-devices---1248496---"></a>Toegang van gebruikersaccounts tot Intune-apps op beheerde Android- en iOS-apparaten<!-- 1248496 -->
Als Microsoft Intune-beheerder kunt u bepalen welke gebruikersaccounts worden toegevoegd aan Microsoft Office-toepassingen op beheerde apparaten. U kunt de toegang beperken tot uitsluitend toegestane gebruikersaccounts van de organisatie, en persoonlijke accounts blokkeren op ingeschreven apparaten. 

#### <a name="outlook-ios-and-android-app-configuration-policy--1828527---"></a>App-configuratiebeleid voor Outlook voor iOS en Android<!--1828527 -->
U kunt nu een app-configuratiebeleid voor Outlook voor iOS en Android maken voor on-premises gebruikers die in iOS en Android gebruikmaken van basisverificatie met het ActiveSync-protocol. Aanvullende configuratie-instellingen worden toegevoegd wanneer het beleid wordt ingeschakeld voor Outlook voor iOS en Android.

#### <a name="office-365-pro-plus-language-packs---1833450---"></a>Office 365 Pro Plus-taalpakketten<!-- 1833450 -->
Als Intune-beheerder kunt extra talen implementeren voor Office 365 Pro Plus-apps die via Intune worden beheerd. De lijst met beschikbare talen bevat het taalpakket **Type** (kern, gedeeltelijk en spellingcontrole). Selecteer in Azure Portal **Microsoft Intune** > **Client-apps** > **Apps** > **Toevoegen**. In de lijst **App-type** op de blade **App toevoegen** selecteert u **Windows 10** onder **Office 365-suite**. Selecteer **Talen** in de blade **Instellingen voor app-suite**.

#### <a name="windows-line-of-business-lob-apps-file-extensions---1884873---"></a>Bestandsextensies van Windows LOB-apps (line-of-business)<!-- 1884873 -->
De beschikbare bestandsextensies voor Windows LOB-apps omvatten nu ook *.msi*, *.appx*, *.appxbundle*, *.msix* en *.msixbundle*. U kunt in Microsoft Intune apps toevoegen via **Client-apps** > **Apps** > **Toevoegen**. Het deelvenster **App toevoegen** wordt weergegeven. Hier kunt u het **app-type** selecteren. Selecteer voor Windows LOB-apps **Line-Of-Business-app** als het app-type, selecteer het **app-pakketbestand** en voeg vervolgens een iOS-installatiebestand toe met de juiste extensie.

#### <a name="windows-10-app-deployment-using-intune---2309001---"></a>Implementatie van Windows 10-apps met Intune<!-- 2309001 -->
Beheerders kunnen Intune gebruiken om de meeste bestaande toepassingen van hun organisatie te implementeren in Windows 10-apparaten van eindgebruikers. Daarmee wordt er uitgebouwd op de bestaande ondersteuning voor Line-Of-Business-apps (LOB) en Microsoft Store voor Bedrijven-apps. Beheerders kunnen toepassingen voor Windows 10-gebruikers toevoegen, installeren en verwijderen in verschillende indelingen, zoals MSI's, Setup.exe of MSP. Intune evalueert de regels voor de vereisten voordat er iets wordt gedownload of geïnstalleerd. Eindgebruikers worden op de hoogte gehouden van de status of vereisten voor opnieuw opstarten via het Windows 10-onderhoudscentrum. Met deze functionaliteit worden bedrijven die geïnteresseerd zijn om deze werkbelasting naar Intune en de cloud te verplaatsen effectief gedeblokkeerd. Deze functie is momenteel beschikbaar als openbare preview-versie en we verwachten in de aankomende maanden significante nieuwe mogelijkheden toe te voegen aan de functie. 

#### <a name="app-protection-policy-app-settings-for-web-data---2662995---"></a>APP-instellingen voor webgegevens<!-- 2662995 -->
De APP-instellingen voor webcontent op zowel Android- als iOS-apparaten worden bijgewerkt om zowel http- als https-webkoppelingen beter te kunnen verwerken, evenals de gegevensoverdracht via iOS Universal- en Android App-koppelingen. 

#### <a name="end-user-device-and-app-content-menu---2771453---"></a>Apparaat- en app-inhoudmenu voor eindgebruikers<!-- 2771453 -->
Eindgebruikers kunnen nu het contextmenu van apparaten en apps gebruiken om veelvoorkomende acties te activeren, zoals de naam van een apparaat wijzigen of de nalevingsstatus controleren. 

#### <a name="windows-company-portal-keyboard-shortcuts---2771518---"></a>Sneltoetsen voor Windows-bedrijfsportal<!-- 2771518 -->
Eindgebruikers kunnen nu app- en apparaatacties in de Windows-bedrijfsportal activeren met behulp van sneltoetsen (accelerators).

#### <a name="require-non-biometric-pin-after-a-specified-timeout---1506985---"></a>Een niet-biometrische pincode vereisen na de opgegeven time-out<!-- 1506985 -->
Door een niet-biometrische pincode te vereisen na een door de beheerder opgegeven time-out, biedt Intune een betere beveiliging voor apps die geschikt zijn voor Mobile Application Management (MAM) door het gebruik van biometrische identificatie voor toegang tot zakelijke gegevens te beperken. De instellingen hebben invloed op gebruikers die Touch ID (iOS), Face ID (iOS), Android Biometric of andere toekomstige biometrische verificatiemethoden gebruiken om toegang te krijgen tot voor APP/MAM geschikte toepassingen. Door deze instellingen hebben Intune-beheerders gedetailleerdere controle over gebruikerstoegang. Op deze manier wordt de kans kleiner dat een onjuiste gebruiker bedrijfsgegevens kan zien op een apparaat met meerdere vingerafdrukken of andere biometrische toegangsmethoden. Open **Microsoft Intune** in de Azure-Portal. Selecteer **Client-apps** > **App-beveiligingsbeleid** > **Een beleid toevoegen** > **Instellingen**. Ga voor specifieke instellingen naar de sectie **Toegang**. Zie [iOS-instellingen](../apps/app-protection-policy-settings-ios.md#access-requirements) en [Android-instellingen](../apps/app-protection-policy-settings-android.md#access-requirements) voor meer informatie over instellingen voor toegang.

#### <a name="intune-app-data-transfer-settings-on-ios-mdm-enrolled-devices---2244713---"></a>Instellingen voor Intune APP-gegevensoverdracht op iOS-apparaten die via MDM zijn ingeschreven<!-- 2244713 -->
U kunt het beheer van instellingen voor Intune APP-gegevensoverdracht op iOS-apparaten die zijn ingeschreven via MDM scheiden van het opgeven van de identiteit van de ingeschreven gebruiker. Dit wordt ook wel de UPN (User Principal Name) genoemd. Beheerders die de IntuneMAMUPN niet gebruiken, zullen geen wijziging in het gedrag opmerken. Als deze functionaliteit beschikbaar is, moeten beheerders die de IntuneMAMUPN gebruiken om het gedrag van de gegevensoverdracht op ingeschreven apparaten te beheren de nieuwe instellingen controleren en hun APP-instellingen zo nodig bijwerken.

#### <a name="windows-10-win32-apps---2617325---"></a>Win32-apps voor Windows 10<!-- 2617325 -->
U kunt uw Win32-apps configureren voor installatie in gebruikerscontext voor individuele gebruikers of u kunt de app installeren voor alle gebruikers van het apparaat.

#### <a name="windows-win32-apps-and-powershell-scripts---2617330---"></a>Windows Win32-apps en PowerShell-scripts<!-- 2617330 -->
Eindgebruikers hoeven niet te zijn aangemeld bij het apparaat om Win32-apps te installeren of PowerShell-scripts uit te voeren. 

#### <a name="troubleshooting-client-app-installation---1363711---"></a>Problemen met de installatie van client-apps oplossen<!-- 1363711 -->
U kunt de problemen met de installatie van client-apps oplossen door de kolom met het label **App-installatie** op de blade **Probleem oplossen** te controleren. Om de blade **Problemen oplossen** in de Intune-portal weer te geven, selecteert u **Problemen oplossen** onder **Help en ondersteuning**.

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="create-dns-suffixes-in-vpn-configuration-profiles-on-devices-running-windows-10---1333668---"></a>DNS-achtervoegsels maken in VPN-configuratieprofielen op apparaten met Windows 10<!-- 1333668 -->
Wanneer u een VPN-apparaatconfiguratieprofiel maakt (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** platform > **VPN** profieltype), voert u bepaalde DNS-instellingen in. Met deze update kunt u ook meerdere **DNS-achtervoegsels** in Intune invoeren. Wanneer u DNS-achtervoegsels gebruikt, kunt u naar een netwerkbron zoeken met behulp van de korte naam, in plaats van met de Fully Qualified Domain Name (FQDN). Met deze update kunt u ook de volgorde van de DNS-achtervoegsels in Intune wijzigen.
In [VPN-instellingen voor Windows 10](../configuration/vpn-settings-windows-10.md#dns-settings) worden de huidige DNS-instellingen vermeld.
Van toepassing op: Windows 10-apparaten

#### <a name="support-for-always-on-vpn-for-android-enterprise-work-profiles---1333705---"></a>Ondersteuning voor altijd ingeschakelde VPN voor Android Enterprise-werkprofielen<!-- 1333705 -->
In deze update kunt u ingeschakelde VPN-verbindingen gebruiken op Android Enterprise-apparaten met beheerde werkprofielen. Altijd ingeschakelde VPN-verbindingen blijven verbonden en maken direct opnieuw verbinding wanneer gebruikers hun apparaat ontgrendelen, het apparaat opnieuw wordt opgestart of het draadloze netwerk wordt gewijzigd. U kunt de verbinding ook in de vergrendelingsmodus zetten. Hiermee wordt al het netwerkverkeer geblokkeerd totdat de VPN-verbinding actief is.
U vindt altijd ingeschakelde VPN in **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** voor platform > **Apparaatbeperkingen** > **Connectiviteit**.

#### <a name="issue-scep-certificates-to-user-less-devices---1744554---"></a>SCEP-certificaten uitgeven voor apparaten zonder gebruiker<!-- 1744554 -->
Momenteel worden certificaten uitgegeven voor gebruikers. Met deze update kunnen SCEP-certificaten worden uitgegeven voor apparaten, waaronder apparaten zonder gebruiker, zoals kiosken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** voor platform > **SCEP-certificaat** voor profiel). Andere updates bevatten:
- De eigenschap **Onderwerp** in een SCEP-profiel is nu een aangepast tekstvak en kan nieuwe variabelen bevatten. 
- De eigenschap **Alternatieve naam voor onderwerp** in een SCEP-profiel heeft nu een tabelopmaak en kan nieuwe variabelen bevatten. Een beheerder kan in de tabel een kenmerk toevoegen en de waarde in een aangepast tekstvak invullen. De alternatieve naam voor het onderwerp ondersteunt de volgende kenmerken: 
  - DNS
  - E-mailadres
  - UPN

  Deze nieuwe variabelen kunnen met statische tekst worden toegevoegd in een tekstvak voor aangepaste waarden. Het DNS-kenmerk kan bijvoorbeeld worden toegevoegd als `DNS = {{AzureADDeviceId}}.domain.com`.

  > [!NOTE]
  > Accolades, puntkomma's en pijp-symbolen '{} ; |' kunnen niet worden gebruikt in de statische tekst van de alternatieve naam voor het onderwerp. Accolades worden alleen geaccepteerd voor `Subject` of `Subject alternative name`, als ze een van de nieuwe apparaatcertificaatvariabelen omsluiten. 

Nieuwe apparaatcertificaatvariabelen:  

```
"{{AAD_Device_ID}}",
"{{Device_Serial}}",
"{{Device_IMEI}}",
"{{SerialNumber}}",
"{{IMEINumber}}",
"{{AzureADDeviceId}}",
"{{WiFiMacAddress}}",
"{{IMEI}}",
"{{DeviceName}}",
"{{FullyQualifiedDomainName}}",
"{{MEID}}",
```

> [!NOTE]
> - `{{FullyQualifiedDomainName}}` kan alleen worden gebruikt voor Windows-apparaten en apparaten die aan een domein zijn toegevoegd. 
> - Houd er rekening mee dat wanneer u in het onderwerp of de alternatieve naam voor het onderwerp voor een apparaatcertificaat apparaateigenschappen opgeeft, zoals het IMEI-nummer, het serienummer en de Fully Qualified Domain Name, deze eigenschappen kunnen worden vervalst door een persoon met toegang tot het apparaat. 

In [Een SCEP-certificaatprofiel maken](../protect/certificates-profile-scep.md#create-a-scep-certificate-profile) worden de huidige variabelen bij het maken van een SCEP-configuratieprofiel vermeld. 

Van toepassing op: Windows 10 en hoger en iOS worden ondersteund voor wifi

#### <a name="remotely-lock-uncompliant-devices---2064495---"></a>Niet-compatibele apparaten op afstand vergrendelen<!-- 2064495 -->
Wanneer een apparaat niet compatibel is, kunt u een actie maken voor het nalevingsbeleid waarbij het apparaat op afstand wordt vergrendeld. Maak in Intune > **Apparaatcompatibiliteit** een nieuw beleid of selecteer een bestaand beleid > **Eigenschappen**. Selecteer **Acties voor niet-naleving** > **Toevoegen** en kies ervoor om het apparaat op afstand te vergrendelen.
Ondersteund in: 
- Android
- iOS
- macOS
- Windows 10 Mobile 
- Windows Phone 8.1 en hoger 

#### <a name="windows-10-and-later-kiosk-profile-improvements-in-the-azure-portal---2748224---"></a>Verbeteringen voor kioskprofielen voor Windows 10 en hoger in Azure Portal<!-- 2748224 -->
Deze update bevat de volgende verbeteringen voor het apparaatconfiguratieprofiel voor kiosken voor Windows 10 (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** voor platform > **Kioskvoorbeeld** voor profieltype): 
- Momenteel kunt u meerdere kioskprofielen op hetzelfde apparaat maken. Met deze update biedt Intune ondersteuning voor slechts één kioskprofiel per apparaat. Als u toch meerdere kioskprofielen op één apparaat wilt, kunt u een aangepaste URI gebruiken.
- In het profiel voor een **kiosk voor meerdere apps** kunt u de tegelgrootte en volgorde voor toepassingen selecteren voor de **opmaak van het menu Start** in het toepassingenraster. Als u meer aanpassingen wilt aanbrengen, kunt u verdergaan met het uploaden van een XML-bestand.
- De instellingen voor de kioskbrowser worden verplaatst naar de **kiosk**instellingen. Momenteel hebben de instellingen voor de **kioskwebbrowser** hun eigen categorie in Azure Portal.
Van toepassing op: Windows 10 en hoger

#### <a name="pin-prompt-when-you-change-fingerprints-or-face-id-on-an-ios-device----2637704----"></a>Pincode vragen bij het wijzigen van vingerafdrukken of Face ID op een iOS-apparaat <!-- 2637704  -->
Gebruikers wordt nu gevraagd om een pincode na het doorvoeren van biometrische wijzigingen op hun iOS-apparaat. Dit gebeurt ook bij wijzigingen in de geregistreerde gegevens voor Touch ID of Face ID. De timing van dit verzoek is afhankelijk van de configuratie van de time-out die is ingesteld bij *De toegangsvereisten opnieuw controleren na (minuten)* .  Als er geen pincode is ingesteld, wordt de gebruiker gevraagd om dit te doen. 
 
Deze functie is alleen beschikbaar voor iOS en vereist het gebruik van toepassingen die de Intune-APP SDK voor iOS, versie 9.0.1 of hoger, hebben geïntegreerd. Integratie van de SDK is nodig om het gedrag te kunnen afdwingen in de betreffende toepassingen. Deze integratie vindt doorlopend plaats en is afhankelijk van de specifieke toepassingsteams. Apps die hieraan deelnemen, zijn onder meer WXP, Outlook, Managed Browser en Yammer.

#### <a name="network-access-control-support-on-ios-vpn-clients---1333693---"></a>Ondersteuning voor netwerktoegangsbeheer op iOS VPN-clients<!-- 1333693 -->
Met deze update is er een nieuwe instelling om netwerktoegangsbeheer (NAC) in te schakelen wanneer u een VPN-configuratieprofiel maakt voor Cisco AnyConnect-, F5-toegang en Citrix SSO voor iOS. Dankzij deze instelling kan de NAC-ID van het apparaat worden opgenomen in het VPN-profiel. Momenteel zijn er geen VPN-clients of NAC-partneroplossingen die ondersteuning bieden voor deze nieuwe NAC-ID, maar we houden u op de hoogte via onze [ondersteuningsblogpost](ttps://aka.ms/iOS12_and_vpn) als dit het geval is.

Voor het gebruik van NAC moet u het volgende doen:
1. Aangeven dat Intune apparaat-id's in VPN-profielen mag opnemen
2. Uw firmware/NAC-provider-software bijwerken, met behulp van de richtlijnen van uw NAC-provider

Zie voor meer informatie over deze instelling in een iOS VPN-profiel het onderwerp [VPN-instellingen toevoegen op iOS-apparaten in Microsoft Intune](../configuration/vpn-settings-ios.md). Zie [Netwerktoegangsbeheer integreren met Intune](../protect/network-access-control-integrate.md) voor meer informatie over netwerktoegangsbeheer. 

Van toepassing op: iOS

#### <a name="remove-an-email-profile-from-a-device-even-when-theres-only-one-email-profile---1818139---"></a>Een e-mailprofiel verwijderen van een apparaat, zelfs als deze maar één e-mailprofiel bevat<!-- 1818139 -->
Voorheen kon een e-mailprofiel niet van een apparaat worden verwijderd, *als* dit het enige e-mailprofiel was. Met deze update verandert dat. Nu kunt u een e-mailprofiel verwijderen, zelfs als dit het enige e-mailprofiel op het apparaat is. Zie [E-mailinstellingen toevoegen aan apparaten met Intune](../configuration/email-settings-configure.md) voor meer informatie.

#### <a name="powershell-scripts-and-aad---2309469---"></a>PowerShell-scripts en Azure Active Directory<!-- 2309469 -->
PowerShell-scripts in Intune kunnen worden gericht op AAD-apparaatbeveiligingsgroepen.

#### <a name="new-required-password-type-default-setting-for-android-android-enterprise---2649963---"></a>Nieuwe standaardwaarde voor ‘Vereist wachtwoordtype’ voor Android, Android Enterprise<!-- 2649963 -->
Wanneer u een nieuw nalevingsbeleid maakt (**Intune** > **Apparaatnaleving** > **Beleid** > **Beleid maken** > **Android** of **Android enterprise** voor platform > Systeembeveiliging), verandert de standaardwaarde voor **Vereist wachtwoordtype**:

Van: Standaardwaarde apparaat: Ten minste numeriek

Van toepassing op: Android, Android Enterprise

Ga naar [Android](../protect/compliance-policy-create-android.md) en [Android Enterprise](../protect/compliance-policy-create-android-for-work.md) om deze instellingen te bekijken.

#### <a name="use-a-pre-shared-key-in-a-windows-10-wi-fi-profile---2662938---"></a>Een vooraf gedeelde sleutel gebruiken in een Wi-Fi-profiel voor Windows 10<!-- 2662938 -->
Met deze update kunt u een vooraf gedeelde sleutel gebruiken met het persoonlijke WPA/WPA2-beveiligingsprotocol om een Wi-Fi-configuratieprofiel voor Windows 10 te verifiëren. U kunt ook de configuratie van de kosten voor een netwerk met een datalimiet opgeven voor apparaten in Windows na de update van 10 oktober 2018.

U moet momenteel een Wi-Fi-profiel importeren of een aangepast profiel maken om een vooraf gedeelde sleutel te gebruiken. In [Wi-Fi-instellingen voor Windows 10](../configuration/wi-fi-settings-windows.md) worden de huidige instellingen vermeld. 

#### <a name="remove-pkcs-and-scep-certificates-from-your-devices---3218390---"></a>PKCS- en SCEP-certificaten van uw apparaten verwijderen<!-- 3218390 -->
In sommige gevallen werden PKCS- en SCEP-certificaten niet van apparaten verwijderd, zelfs wanneer een beleid uit een groep werd verwijderd, een configuratie of nalevingsimplementatie werd verwijderd of een beheerder een bestaand SCEP- of PKCS-profiel bijwerkte. Met deze update verandert dat. Er zijn enkele situaties waarin PKCS- en SCEP-certificaten worden verwijderd van apparaten en een aantal situaties waarin deze certificaten op het apparaat blijven gehandhaafd. Zie [SCEP- en PKCS-certificaten verwijderen in Microsoft Intune](../protect/remove-certificates.md) voor deze situaties.

#### <a name="use-gatekeeper-on-macos-devices-for-compliance---2504381---"></a>Gatekeeper gebruiken op macOS-apparaten voor naleving<!-- 2504381 -->
Deze update bevat de macOS Gatekeeper om apparaten te controleren op naleving. Als u de Gatekeeper-eigenschap wilt instellen, [voegt u een apparaatnalevingsbeleid voor macOS-apparaten toe](../protect/compliance-policy-create-mac-os.md).


### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="apply-autopilot-profile-to-enrolled-win-10-devices-not-already-registered-for-autopilot---1558983---"></a>Het Autopilot-profiel toepassen op ingeschreven Windows 10-apparaten die nog niet zijn geregistreerd voor Autopilot<!-- 1558983 -->
U kunt Autopilot-profielen toepassen op ingeschreven Windows 10-apparaten die nog niet zijn geregistreerd voor Autopilot. Kies in het Autopilot-profiel de optie **Alle doelapparaten converteren naar Autopilot** om automatisch niet-Autopilot-apparaten te registreren bij de Autopilot-implementatieservice. Het kan 48 uur duren voordat de registratie is verwerkt. Wanneer het apparaat wordt uitgeschreven en opnieuw wordt ingesteld, wordt het door Autopilot ingericht.

#### <a name="create-and-assign-multiple-enrollment-status--page-profiles-to-azure-ad-groups---2526564---"></a>Meerdere profielen voor inschrijvingsstatuspagina's maken en toewijzen aan Azure AD-groepen<!-- 2526564 -->
U kunt nu meerdere profielen voor inschrijvingsstatuspagina's [maken en toewijzen](../enrollment/windows-enrollment-status.md) aan Azure AD-groepen.

#### <a name="migration-from-device-enrollment-program-to-apple-business-manager-in-intune--2748613--"></a>Migratie van Device Enrollment Program naar Apple Business Manager in Intune<!--2748613-->
Apple Business Manager (ABM) werkt in Intune en u kunt uw account van Device Enrollment Program (DEP) upgraden naar ABM. Het proces in Intune is hetzelfde. Als u uw Apple-account wilt bijwerken van DEP naar ABM, gaat u naar [https://support.apple.com/HT208817]( https://support.apple.com/HT208817).

#### <a name="alert-and-enrollment-status-tabs-on-the-device-enrollment-overview-page--2748656--"></a>Tabbladen voor waarschuwingen en inschrijvingsstatus op de overzichtspagina Apparaatinschrijving<!--2748656-->
Waarschuwingen en mislukte inschrijvingen worden nu weergegeven op afzonderlijke tabbladen op de overzichtspagina Apparaatinschrijving.

#### <a name="enrollment-abandonment-report---1382924---"></a>Rapport over afgebroken inschrijvingen<!-- 1382924 -->
Een nieuw rapport met details over afgebroken inschrijvingen wordt beschikbaar via **Apparaatinschrijving** > **Monitor**. Zie [Rapport over afgebroken items in bedrijfsportal](../enrollment/enrollment-report-company-portal-abandon.md) voor meer informatie.

#### <a name="new-azure-active-directory-terms-of-use-feature---2870393---"></a>Nieuwe gebruiksvoorwaardenfunctie voor Azure Active Directory<!-- 2870393 -->
Azure Active Directory krijgt een gebruiksvoorwaardenfunctie die u kunt gebruiken in plaats van de bestaande Intune-voorwaarden. De gebruiksvoorwaardenfunctie voor Azure AD biedt meer flexibiliteit als het gaat om welke voorwaarden wanneer worden weergegeven, en biedt betere lokalisatieondersteuning, meer controle over de weergave van voorwaarden en verbeterde rapportage. De gebruiksvoorwaardenfunctie voor Azure AD vereist wel Azure Active Directory Premium P1, dat ook onderdeel is van de Enterprise Mobility + Security E3-suite. Zie het artikel [De voorwaarden voor gebruikerstoegang van uw bedrijf beheren](../enrollment/terms-and-conditions-create.md) voor meer informatie.

#### <a name="android-device-owner-mode-support--3188762--"></a>Ondersteuning voor de modus Android-apparaateigenaar<!--3188762-->
Voor Samsung Knox Mobile Enrollment ondersteunt Intune nu het inschrijven van apparaten bij het beheer van de modus Android-apparaateigenaar. Gebruikers op wifi- of mobiele netwerken kunnen inschrijven met een paar tikken wanneer ze hun apparaten voor het eerst inschakelen. Zie [Android-apparaten automatisch registreren met behulp van de Knox Mobile Enrollment van Samsung](../enrollment/android-samsung-knox-mobile-enroll.md) voor meer informatie.

### <a name="device-management"></a>Apparaatbeheer
#### <a name="new-settings-for-software-updates-----1907869---"></a>Nieuwe instellingen voor software-updates  <!-- 1907869 -->  
- Nu kunt u bepaalde meldingen configureren om eindgebruikers te waarschuwen dat het systeem opnieuw moet worden opgestart om de installatie van de meest recente software-updates te voltooien.   
- Nu kunt u een waarschuwingsprompt configureren over het feit dat systemen opnieuw worden opgestart buiten werkuren, waardoor BYOD-scenario's worden ondersteund.

#### <a name="group-windows-autopilot-enrolled-devices-by-correlator-id---2075110---"></a>Voor Windows Autopilot ingeschreven apparaten groeperen op correlator-ID<!-- 2075110 -->
Intune ondersteunt nu het groeperen van ingeschreven Windows-apparaten op correlator-ID met behulp van [Autopilot voor bestaande apparaten](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) via Configuration Manager. De correlator-ID is een parameter van het Autopilot-configuratiebestand. Intune stelt automatisch de [enrollmentProfileName van het Azure Active Directory-apparaatkenmerk](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices) in zodat deze aansluit bij de "OfflineAutopilotprofile-<correlator ID>". Hierdoor kunnen willekeurige dynamische groepen in Azure AD op basis van correlator-ID’s worden gecreëerd via het kenmerk enrollmentprofileName voor offline Autopilot-inschrijvingen. Zie [Windows Autopilot voor bestaande apparaten](../enrollment/enrollment-autopilot.md#windows-autopilot-for-existing-devices) voor meer informatie.

#### <a name="intune-app-protection-policies---2984657---"></a>Beveiligingsbeleid voor apps in Intune<!-- 2984657 -->
Met behulp van beveiligingsbeleid voor apps in Intune kunt u verschillende instellingen voor gegevensbescherming voor met Intune beveiligde apps configureren, zoals Microsoft Outlook en Microsoft Word. We hebben het uiterlijk van deze instellingen voor zowel [iOS](../apps/app-protection-policy-settings-ios.md) als [Android](../apps/app-protection-policy-settings-android.md) gewijzigd, zodat u de afzonderlijke instellingen gemakkelijker kunt vinden. Er zijn drie soorten beleidsinstellingen:
- **Herlocatie van gegevens**: deze groep bevat de DLP-besturingselementen voor preventie van gegevensverlies, zoals knippen, kopiëren, plakken en beperkingen voor 'opslaan als'. Deze instellingen bepalen hoe gebruikers met gegevens in de apps kunnen werken.
- **Toegangsvereisten**: deze groep bevat de pincodeopties per app die bepalen hoe de gebruiker toegang heeft tot de apps in een werkcontext.  
- **Voorwaardelijk starten**: deze groep bevat instellingen zoals de minimale instellingen van het besturingssysteem, detectie van opengebroken of geroote apparaten en offline respijtperioden.  
  
De functionaliteit van de instellingen verandert niet, maar de instellingen zijn gemakkelijker terug te vinden wanneer u bezig bent met het opstellen van beleid.

#### <a name="restricts-apps-and-block-access-to-company-resources-on-android-devices---2451462----"></a>Apps beperken en de toegang tot bedrijfsresources blokkeren op Android-apparaten<!-- 2451462  -->  
In **Apparaatcompatibiliteit** > **Beleid** > **Beleid maken** > **Android** > **Systeembeveiliging** is er een nieuwe instellingen in de sectie *Apparaatbeveiliging*, namelijk **Beperkte apps**. De instelling **Beperkte apps** maakt gebruik van een nalevingsbeleid om toegang tot bedrijfsresources te blokkeren als er bepaalde apps op het apparaat zijn geïnstalleerd. Het apparaat wordt beschouwd als niet conform beleid totdat de beperkte apps van het apparaat worden verwijderd.
Van toepassing op: 
- Android

### <a name="intune-apps"></a>Intune-apps

#### <a name="intune-will-support-a-maximum-package-size-of-8-gb-for-lob-apps---1727158---"></a>Intune biedt ondersteuning voor een maximale pakketgrootte van 8 GB voor LOB-apps<!-- 1727158 -->
Intune heeft de maximale pakketgrootte voor LOB-apps (Line-of-business) verhoogd naar 8 GB. Zie [Web-apps toevoegen aan Microsoft Intune](../apps/apps-add.md) voor meer informatie.

#### <a name="add-custom-brand-image-for-company-portal-app---1916266---"></a>Aangepaste merkafbeelding toevoegen voor de bedrijfsportal-app<!-- 1916266 -->
Als Microsoft Intune-beheerder kunt u een aangepaste merkafbeelding uploaden die als achtergrondafbeelding wordt weergegeven op de profielpagina van de gebruiker in de bedrijfsportal-app voor iOS. Voor meer informatie over het configureren van de bedrijfsportal-app, zie [Handleiding voor configuratie van de Microsoft Intune bedrijfsportal-app](../apps/company-portal-app.md).

#### <a name="intune-will-maintain-the-office-localized-language-when-updating-office-on-end-users-machines---2971030---"></a>Intune behoudt de in Office gelokaliseerde taal bij het bijwerken van Office op machines van eindgebruikers<!-- 2971030 -->
Wanneer Intune Office op de machines van uw eindgebruiker installeert, krijgen eindgebruikers automatisch dezelfde taalpakketten als bij eerdere .MSI Office installaties. Zie [Office 365-apps toewijzen aan Windows 10-apparaten met Microsoft Intune](../apps/apps-add-office365.md) voor meer informatie.

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="new-intune-support-experience-in-the-microsoft-365-device-management-portal---3076965---"></a>Nieuwe ervaring voor Intune-ondersteuning in de portal voor Microsoft 365-apparaatbeheer<!-- 3076965 -->
We implementeren een nieuwe ervaring voor help en ondersteuning voor Intune in de [portal voor Microsoft 365-apparaatbeheer]( https://devicemanagement.microsoft.com). Met de nieuwe ervaring kunt u uw probleem in uw eigen woorden beschrijven en informatie over probleemoplossing en op internet gevonden informatie over het oplossen van het probleem ontvangen. Deze oplossingen worden aangeboden via een op regels gebaseerde machine learning-algoritme, dat wordt aangestuurd door zoekvragen van gebruikers.  

Naast informatie die specifiek is voor problemen kunt u ook gebruikmaken van de nieuwe werkstroom voor het openen van een ondersteuningsvraag via e-mail of telefoon.  

Voor klanten die deel uitmaken van de implementatie, vervangt deze nieuwe ervaring de huidige help en ondersteuning die bestaat uit een statistische verzameling vooraf geselecteerde opties die zijn gebaseerd op het gebied van de console waarin u zich bevindt wanneer u Help en ondersteuning opent.  

*Deze nieuwe ervaring voor Help en ondersteuning wordt geïmplementeerd voor sommige, maar niet alle tenants en is beschikbaar in de portal voor apparaatbeheer. Deelnemers aan deze nieuwe ervaring worden willekeurig geselecteerd uit de beschikbare Intune-tenants. Nieuwe tenants worden toegevoegd als we de implementatie uitbreiden.*  

Zie [Help en ondersteuning-ervaring](get-support.md#help-and-support-experience) in Ondersteuning voor Microsoft Intune krijgen voor meer informatie.  

#### <a name="powershell-module-for-intune--preview-available---951068---"></a>PowerShell-module voor Intune - Preview-versie is beschikbaar<!-- 951068 -->
Een nieuwe PowerShell-module die ondersteuning biedt voor de Intune-API via Microsoft Graph is nu beschikbaar als preview-versie op [GitHub](https://aka.ms/intunepowershell). Zie het Leesmij-bestand op die locatie meer informatie over het gebruik van deze module.

<!-- ########################## -->
## <a name="september-2018"></a>September 2018

### <a name="app-management"></a>Appbeheer

#### <a name="remove-duplication-of-app-protection-status-tiles---3083391---"></a>Duplicatie van beschermingsstatustegels in de app verwijderen<!-- 3083391 -->
De tegels **Gebruikersstatus voor iOS** en de **Gebruikersstatus voor Android** werden zowel op de pagina **Client-apps: overzicht** als op de pagina **Client-apps: beschermingsstatus van de app** vermeld. De statustegels zijn verwijderd van de pagina **Client-apps: overzicht** om duplicatie te voorkomen. 

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="support-for-more-third-party-certification-authorities-ca---3093107---"></a>Ondersteuning voor meer externe certificeringsinstanties (CA's)<!-- 3093107 -->
Met behulp van het Simple Certificate Enrollment Protocol (SCEP) kunt u nu nieuwe certificaten uitgeven en certificaten vernieuwen op mobiele apparaten met behulp van Windows, iOS, Android en macOS.

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="intune-moves-to-support-ios-10-and-later---2454656---"></a>Intune stapt over op ondersteuning voor iOS 10 en later<!-- 2454656 -->  
Momenteel ondersteunen Intune-inschrijving, de bedrijfsportal en de beheerde browser alleen iOS-apparaten met iOS 10 en later. Als u wilt controleren of dit van invloed is op apparaten of gebruikers in uw organisatie, gaat u naar Intune in Azure Portal > **Apparaten** > **Alle apparaten**. Filter op besturingssysteem en klik op **Kolommen** om de versiedetails van het besturingssysteem te laten verschijnen. Vraag deze gebruikers om hun apparaten bij te werken naar een ondersteunde versie van het besturingssysteem.  

Als u een van de hierna vermelde apparaten hebt, of als u een van de hierna vermelde apparaten wilt inschrijven, moet u er rekening mee houden dat deze alleen iOS 9 en eerdere versies ondersteunen.  Om toegang tot de Intune-bedrijfsportal te behouden, moet u deze apparaten upgraden naar apparaten die iOS 10 of hoger ondersteunen:  

* iPhone 4S 
* iPod Touch  
* iPad 2 
* iPad (3e generatie) 
* iPad Mini (1e generatie)  

### <a name="device-management"></a>Apparaatbeheer

#### <a name="microsoft-365-device-management-administration-center---3078424---"></a>Beheercentrum voor Microsoft 365-apparaatbeheer<!-- 3078424 -->
Een van de beloften van Microsoft 365 is vereenvoudigd beheer. In de afgelopen jaren is de back-end Microsoft 365-services geïntegreerd voor het leveren van complete scenario’s, zoals voorwaardelijke toegang voor Intune en Azure AD. Het nieuwe [Microsoft 365-beheercentrum](https://devicemanagement.microsoft.com) is de plek waar de beheerervaring wordt versterkt, vereenvoudigd en geïntegreerd. De gespecialiseerde werkruimte voor apparaatbeheer biedt eenvoudige toegang tot alle apparaat- en appbeheerinformatie en taken die uw organisatie nodig heeft. Naar verwachting zal dat dit de primaire cloudwerkruimte voor zakelijke computerteams van eindgebruikers worden.


<!-- ########################## -->
## <a name="august-2018"></a>Augustus 2018

### <a name="app-management"></a>Appbeheer

#### <a name="packet-tunnel-support-for-ios-per-app-vpn-profiles-for-custom-and-pulse-secure-connection-types---1520957---"></a>Ondersteuning voor pakkettunnels voor VPN-profielen in iOS op basis van individuele apps voor aangepaste verbindingstypen en Pulse Secure-verbindingstypen<!-- 1520957 -->
Wanneer u in iOS VPN-profielen voor individuele apps gebruikt, kunt u ervoor kiezen om tunnels op app-niveau (app-proxy) of op pakketniveau (pakkettunnel) te gebruiken. Deze opties zijn beschikbaar voor de volgende verbindingstypen:
- Aangepaste VPN
- Pulse Secure Als u niet zeker weet welke waarde u moet gebruiken, raadpleegt u de documentatie van uw VPN-provider.

#### <a name="delay-when-ios-software-updates-are-shown-on-the-device---1949583---"></a>Vertragen wanneer software-updates voor iOS worden weergegeven op het apparaat<!-- 1949583 -->
In Intune > **Software-updates** > **Beleid voor bijwerken van iOS** kunt u dagen en tijden instellen waarop apparaten geen updates mogen installeren. In een toekomstige update krijgt u de mogelijkheid uit te stellen (met een periode van 1 tot 90 dagen) wanneer een software-update wordt weergegeven op het apparaat. 
De huidige instellingen worden weergegeven op de pagina [iOS-updatebeleid configureren in Microsoft Intune](../protect/software-updates-ios.md)

#### <a name="office-365-proplus-version---2213968---"></a>Office 365 ProPlus-versie<!-- 2213968 -->
Binnenkort kunt u de Office-versie selecteren wanneer u met Intune Office 365 ProPlus-apps toewijst op Windows 10-apparaten. Selecteer in de Azure-portal **Microsoft Intune** > **Apps** > **Apps toevoegen**. Selecteer daarna **Office 365 ProPlus Suite (Windows 10)** in de vervolgkeuzelijst **Soort**. Selecteer **App Suite-instellingen** om de bijbehorende blade weer te geven. Stel **Kanaal bijwerken** in op een waarde, zoals **Maandelijks**. Verwijder eventueel andere versies van Office (msi) van eindgebruikersapparaten door **Ja** te selecteren. Selecteer **Specifiek** om voor het geselecteerde kanaal een specifieke versie van Office te installeren op apparaten van eindgebruikers. U kunt hier ook opgeven welke **Specifieke versie** van Office u wilt gebruiken. Welke versies er beschikbaar zijn, verandert in de loop van de tijd. Daarom is het mogelijk dat er bij het maken van een nieuwe implementatie nieuwere versies beschikbaar zijn en dat bepaalde oudere versies niet meer beschikbaar zijn. Huidige implementaties blijven de oudere versie implementeren, maar de versielijst wordt voortdurend per kanaal bijgewerkt. Zie [Overzicht van updatekanalen voor Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus) voor meer informatie.

#### <a name="support-for-register-dns-setting-for-windows-10-vpn---2282852---"></a>Ondersteuning voor het registreren van DNS-instellingen voor Windows 10-VPN<!-- 2282852 -->
Met deze update wordt het binnenkort mogelijk om VPN-profielen voor Windows 10 zo te configureren dat deze de IP-adressen die door de interne DNS aan de VPN-interface worden toegewezen, automatisch registreren, zonder dat u hiervoor aangepaste profielen hoeft te gebruiken.
Zie [Windows 10 VPN-instellingen](../configuration/vpn-settings-windows-10.md) voor informatie over de instellingen die nu beschikbaar zijn voor VPN-profielen.

#### <a name="the-macos-company-portal-installer-now-includes-the-version-number-in-the-installer-file-name--2652728--"></a>Het installatieprogramma van de macOS-bedrijfsportal-app bevat nu het versienummer in de bestandsnaam van het installatieprogramma<!--2652728-->

#### <a name="ios-automatic-app-updates---2729759---"></a>Automatische iOS-app-updates<!-- 2729759 -->
Automatische updates voor apps worden gebruikt voor apps voor zowel gelicentieerde apparaten als gebruikers voor iOS-versie 11.0 en later.

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="windows-hello-will-target-users-and-devices---1106609---"></a>Windows Hello is gericht op gebruikers en apparaten<!-- 1106609 -->
Wanneer u een beleid voor [Windows Hello voor Bedrijven](../protect/windows-hello.md) maakt, geldt dit voor alle gebruikers binnen de organisatie (tenant-breed). Met deze update kan het beleid ook worden toegepast op specifieke gebruikers of specifieke apparaten met behulp van een beleid voor apparaatconfiguratie (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Identiteitsbescherming** > **Windows Hello voor Bedrijven**).
In Intune in Azure Portal zijn nu de Windows Hello-configuratie en -instellingen zowel onder **Apparaatinschrijving** als onder **Apparaatconfiguratie** beschikbaar. **Apparaatinschrijving** is gericht op de hele organisatie (tenant-breed) en biedt ondersteuning voor Windows AutoPilot (OOBE). **Apparaatconfiguratie** is gericht op apparaten en gebruikers met behulp van een beleid dat wordt toegepast tijdens het inchecken.
Deze functie is van toepassing op:  
- Windows 10 en hoger
- Windows Holographic for Business

#### <a name="zscaler-is-an-available-connection-for-vpn-profiles-on-ios---1769858---"></a>Zscaler is een beschikbare verbinding voor VPN-profielen voor iOS<!-- 1769858 -->
Wanneer u een VPN-apparaatconfiguratieprofiel in iOS maakt (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** platform > **VPN** profieltype), zijn er verschillende verbindingstypen beschikbaar, waaronder Cisco, Citrix en meer. In deze update wordt Zscaler toegevoegd als verbindingstype. 
De pagina [VPN-instellingen voor apparaten met iOS](../configuration/vpn-settings-ios.md) biedt een lijst met beschikbare verbindingstypen.

#### <a name="fips-mode-for-enterprise-wi-fi-profiles-for-windows-10---1879077---"></a>FIPS-modus voor Enterprise Wi-Fi-profielen voor Windows 10<!-- 1879077 -->
U kunt nu de modus Federal Information Processing Standards (FIPS) voor Enterprise Wi-Fi-profielen voor Windows 10 inschakelen in Intune Azure Portal. Zorg ervoor dat de FIPS-modus is ingeschakeld op uw Wi-Fi-infrastructuur als u dit in uw Wi-Fi-profielen inschakelt.
[Wi-Fi-instellingen voor apparaten met Windows 10 en hoger in Intune](../configuration/wi-fi-settings-windows.md) laten u zien hoe een Wi-Fi-profiel wordt gemaakt.

#### <a name="control-s-mode-on-windows-10-and-later-devices---public-preview---1958649---"></a>S-modus beheren op apparaten met Windows 10 en hoger - openbare preview<!-- 1958649 -->
Met deze functie-update kunt u een apparaatconfiguratieprofiel maken dat een Windows 10-apparaat uit de S-modus haalt of voorkomt dat gebruikers het apparaat uit de S-modus halen. Deze functie bevindt zich in Intune > **Apparaatconfiguratie** > **Profielen** >  **Windows 10 en hoger** > **Editie-upgrade en modus schakelen**.
De pagina [Maak kennis met Windows 10 in S-⁠modus](https://www.microsoft.com/windows/s-mode) biedt meer informatie over de S-modus.
Van toepassing op: de meeste recente build van [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (in preview).

#### <a name="windows-defender-atp-configuration-package-automatically-added-to-configuration-profile---2144658---"></a>Windows Defender ATP configuratiepakket automatisch toegevoegd aan configuratieprofiel<!-- 2144658 -->
Wanneer u [Advanced Threat Protection en onboarding](../protect/advanced-threat-protection.md#onboard-devices-by-using-a-configuration-profile)-apparaten gebruikt in Intune, moest u voorheen een configuratiepakket downloaden en dit aan uw configuratieprofiel toevoegen. Met deze update haalt Intune het pakket automatisch op uit het Windows Defender-beveiligingscentrum en voegt het toe aan uw profiel.
Van toepassing op Windows 10 en hoger.

#### <a name="require-users-to-connect-during-device-setup--2311457--"></a>Gebruikers verplichten om verbinding te maken tijdens de installatie van het apparaat<!--2311457-->
U kunt nu apparaatprofielen instellen om verplicht te stellen dat het apparaat verbinding maakt met een netwerk alvorens verder te gaan na de netwerkpagina tijdens de installatie van Windows 10. Hoewel deze functie nog in preview is, moet deze instelling worden gebruikt door een Windows Insider build 1809 of hoger.
Van toepassing op: de meeste recente build van [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (in preview).

#### <a name="restricts-apps-and-block-access-to-company-resources-on-ios-and-android-enterprise-devices---2451462---"></a>Apps beperken en de toegang tot bedrijfsbronnen blokkeren op iOS- en Android Enterprise-apparaten<!-- 2451462 -->
Er is onder **Apparaatnaleving** > **Beleid** > **Beleid maken** > **iOS** > **Systeembeveiliging** een nieuwe instelling: **Beperkte toepassingen**. Deze nieuwe instelling maakt gebruik van een nalevingsbeleid om toegang tot bedrijfsbronnen te blokkeren als bepaalde apps op het apparaat zijn geïnstalleerd. Het apparaat wordt beschouwd als niet conform beleid totdat de beperkte apps van het apparaat worden verwijderd.
Van toepassing op: iOS

#### <a name="modern-vpn-support-updates-for-ios---2459928-1819876-and-2650856---"></a>Moderne VPN-ondersteuningsupdates voor iOS<!-- 2459928, 1819876, and 2650856 -->
Deze update biedt extra ondersteuning voor de volgende iOS VPN-clients:
- F5 Access (versie 3.0.1 en hoger)
- Citrix SSO
- Palo Alto Networks GlobalProtect (versie 5.0 en hoger) Ook beschikbaar in deze update:
- De naam van het bestaande verbindingstype **F5 Access** is gewijzigd in **F5 Access Legacy** voor iOS.
- De naam van het bestaande verbindingstype **Palo Alto Networks GlobalProtect** wordt gewijzigd in **Palo Alto Networks GlobalProtect (verouderd)** voor iOS.
Bestaande profielen met deze verbindingstypen blijven werken met hun respectieve verouderde VPN-clients. Als u in iOS gebruikmaakt van Cisco Legacy AnyConnect, F5 Access Legacy, Citrix VPN of Legacy Palo Alto Networks GlobalProtect versie 4.1, moet u overstappen op de nieuwe apps. Doe dit zo spoedig mogelijk, om ervoor te zorgen dat VPN-toegang beschikbaar blijft voor iOS-apparaten die worden bijgewerkt naar iOS 12.
Zie de [blog van het Microsoft Intune-ondersteuningsteam](https://go.microsoft.com/fwlink/?linkid=2013806) voor meer informatie over iOS 12 en VPN-profielen.

#### <a name="export-azure-classic-portal-compliance-policies-to-recreate-these-policies-in-the-intune-azure-portal---2469637---"></a>Klassiek nalevingsbeleid van Azure Portal exporteren om dit beleid opnieuw te maken in Intune Azure Portal<!-- 2469637 -->
Nalevingsbeleid gemaakt in de klassieke Azure-portal wordt afgeschaft. U kunt alle bestaande beleidsregels bekijken en verwijderen. U kunt ze echter niet meer bijwerken. Als u nalevingsbeleidsregels moet migreren naar de huidige Intune Azure Portal, kunt u het beleid exporteren als een door komma's gescheiden bestand (*CSV*-bestand). Vervolgens kunt u de details in het bestand gebruiken om dit beleid opnieuw te maken in Intune Azure Portal.

> [!IMPORTANT]
> Wanneer de klassieke Azure Portal buiten gebruik wordt gesteld, is het niet meer mogelijk om uw nalevingsbeleid te openen of weer te geven. Zorg er daarom voor dat u uw beleidsregels exporteert en opnieuw maakt in Azure Portal, voordat de klassieke Azure Portal buiten gebruik wordt gesteld.

#### <a name="better-mobile---new-mobile-threat-defense-partner---22662717---"></a>Better Mobile: nieuwe Mobile Threat Defense-partner<!-- 22662717 -->
U kunt de toegang van mobiele apparaten tot bedrijfsresources beheren met voorwaardelijke toegang op basis van een risicoanalyse die wordt uitgevoerd door Better Mobile, een Mobile Threat Defense-oplossing die in Microsoft Intune is geïntegreerd.

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="lock-the-company-portal-in-single-app-mode-until-user-sign-in--1067692---"></a>De bedrijfsportal in de modus voor enkele toepassing vergrendelen tot een gebruiker zich aanmeldt<!--1067692 --> 
U hebt nu de optie om de bedrijfsportal uit te voeren in de modus voor enkele toepassing als u een gebruiker verifieert via de bedrijfsportal, in plaats van via de configuratieassistent, tijdens de DEP-registratie. Met deze optie wordt het apparaat onmiddellijk vergrendeld nadat de configuratieassistent is voltooid, zodat een gebruiker zich moet aanmelden om toegang te krijgen tot het apparaat. Dit proces zorgt ervoor dat de onboarding voor het apparaat wordt voltooid en het niet in een staat zonder gekoppelde gebruiker blijft.

#### <a name="assign-a-user-and-friendly-name-to-an-autopilot-device--1346521---"></a>Een gebruiker en een beschrijvende naam toewijzen aan een AutoPilot-apparaat<!--1346521 -->
U kunt nu [een gebruiker toewijzen aan een specifiek Autopilot-apparaat](../enrollment/enrollment-autopilot.md). Beheerders kunnen dan ook beschrijvende namen opgeven die aan gebruikers worden getoond wanneer deze hun apparaat instellen met AutoPilot.
Van toepassing op: de meeste recente build van [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (in preview).

#### <a name="use-vpp-device-licenses-to-pre-provision-the-company-portal-during-dep-enrollment---1608345---"></a>VPP-apparaatlicenties gebruiken om de bedrijfsportal vooraf in te richten tijdens DEP-registratie<!-- 1608345 -->
U kunt nu VPP-apparaatlicenties (Volume Purchase Program) gebruiken om de bedrijfsportal vooraf in te richten tijdens de DEP-registraties (Device Enrollment Program). Om dit te doen, geeft u, wanneer u [een registratieprofiel maakt of bewerkt](../enrollment/device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile), het VPP-token op dat u wilt gebruiken om de bedrijfsportal te installeren. Controleer of uw token niet verloopt en of u voldoende licenties heeft voor de bedrijfsportal-app. Wanneer het token verloopt of onvoldoende licenties heeft, pusht Intune in plaats daarvan de App Store-bedrijfsportal (deze vraagt om een Apple ID).

#### <a name="confirmation-required-to-delete-vpp-token-that-is-being-used-for-company-portal-pre-provisioning---2237634---"></a>Bevestiging vereist om het VPP-token te verwijderen dat wordt gebruikt voor het vooraf inrichten van de bedrijfsportal<!-- 2237634 -->
Er is nu een bevestiging vereist om een Volume Purchase Program-token (VPP) te verwijderen als dit wordt gebruikt voor het vooraf inrichten van de bedrijfsportal tijdens de DEP-inschrijving.

#### <a name="block-windows-personal-device-enrollments---1849498---"></a>Persoonlijke apparaatinschrijvingen in Windows blokkeren<!-- 1849498 -->
U kunt hiermee [voorkomen dat persoonlijke Windows-apparaten](../enrollment/enrollment-restrictions-set.md) in Intune worden geregistreerd met behulp van [beheer van mobiele apparaten](../enrollment/windows-enroll.md) (Mobile Device Management, MDM). Apparaten die zijn geregistreerd bij de [Intune PC-agent](../manage-windows-pcs-with-microsoft-intune.md), kunnen niet met deze functie worden geblokkeerd. Deze functie wordt in de komende weken uitgerold; u ziet deze mogelijk dus niet direct terug in de gebruikersinterface.

#### <a name="specify-machine-name-patterns-in-an-autopilot-profile--1849855--"></a>Computernaampatronen opgeven in een AutoPilot-profiel<!--1849855-->
U kunt hiermee [een computernaamsjabloon](../enrollment/enrollment-autopilot.md#create-an-autopilot-deployment-profile) opgeven om tijdens inschrijving via AutoPilot [computernamen](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) te genereren en in te stellen. Van toepassing op: de meeste recente build van [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (in preview).

#### <a name="for-windows-autopilot-profiles-hide-the-change-account-options-on-the-company-sign-in-page-and-domain-error-page--1901669---"></a>De opties voor het wijzigen van een account op de aanmeldingspagina en domeinfoutpagina van een bedrijf verbergen voor Windows AutoPilot-profielen<!--1901669 -->
Er zijn [nieuwe opties voor Windows AutoPilot-profielen](../enrollment/enrollment-autopilot.md#create-an-autopilot-deployment-profile) beschikbaar, waarmee beheerders de opties voor het wijzigen van een account kunnen verbergen op de aanmeldingspagina en domeinfoutpagina's van een bedrijf. Als u deze opties wilt verbergen, moet er een aangepaste huisstijl zijn geconfigureerd in Azure Active Directory. Van toepassing op: de meeste recente build van [Windows Insider](https://docs.microsoft.com/windows-insider/at-work-pro/) (in preview).

### <a name="macos-support-for-apple-device-enrollment-program---747651---"></a>macOS-ondersteuning voor het Apple Device Enrollment Program<!-- 747651 -->
Intune ondersteunt nu inschrijving van macOS-apparaten in het Apple Device Enrollment Program (DEP). Zie [MacOS-apparaten automatisch inschrijven met het Device Enrollment Program van Apple](../enrollment/device-enrollment-program-enroll-macos.md) voor meer informatie.

### <a name="device-management"></a>Apparaatbeheer

#### <a name="delete-jamf-devices---2653306--"></a>Jamf-apparaten verwijderen<!-- 2653306-->
U kunt door JAMF beheerde apparaten als volgt verwijderen: ga naar **Apparaten** > kies het Jamf-apparaat > **Verwijderen**.

#### <a name="change-terminology-to-retire-and-wipe---2175759---"></a>Terminologie wijzigen in 'buiten gebruik stellen' en 'wissen'<!-- 2175759 -->
In de gebruikersinterface en documentatie van Intune zijn de volgende begrippen gewijzigd, om consistent te zijn met Graph API:
- **Bedrijfsgegevens verwijderen** wordt gewijzigd in ‘buiten gebruik stellen’
- **Fabrieksinstellingen** wordt gewijzigd in **wissen**

#### <a name="confirmation-dialog-if-admin-tries-to-delete-mdm-push-certificate---297909500--"></a>Het bevestigingsvenster als de beheerder probeert het MDM-Pushcertificaat te verwijderen<!-- 297909500-->
Als iemand probeert een Apple MDM-pushcertificaat te verwijderen, wordt in een bevestigingsvenster het betreffende aantal iOS- en macOS-apparaten weergegeven. Als het certificaat wordt verwijderd, moeten deze apparaten opnieuw worden ingeschreven.

#### <a name="additional-security-settings-for-windows-installer---2282430---"></a>Aanvullende beveiligingsinstellingen voor Windows Installer<!-- 2282430 -->
U kunt gebruikers toestemming geven om app-installaties te beheren. Als u deze functie is ingeschakeld, kunnen installaties worden toegestaan die anders worden gestopt vanwege een beveiligingsfout. U kunt het Windows-installatieprogramma de opdracht geven om verhoogde bevoegdheden te gebruiken wanneer een programma op een systeem wordt geïnstalleerd. Verder kunt u ingeschakelde items van Windows-gegevensbescherming laten indexeren en de metagegevens voor de items laten opslaan op een niet-versleutelde locatie. Als het beleid is uitgeschakeld, worden de items met WIP-beveiliging niet geïndexeerd en worden ze niet weergegeven in de resultaten in Cortana of Verkenner. De functionaliteit voor deze opties is standaard uitgeschakeld. 

#### <a name="new-user-experience-update-for-the-company-portal-website--2000968---"></a>Nieuwe update van de gebruikerservaring voor de bedrijfsportalwebsite<!--2000968 -->
Op basis van feedback van klanten zijn er nieuwe functies toegevoegd aan de website van de bedrijfsportal. U zult een aanzienlijke verbetering ervaren wat betreft de bestaande functionaliteit en bruikbaarheid van uw apparaten. Delen van de site &ndash;zoals apparaatgegevens, feedback en ondersteuning, en apparaatoverzicht&ndash; krijgen een nieuw, modern, responsief ontwerp. U ziet ook:

- Gestroomlijnde werkstromen voor alle apparaatplatforms
- Verbeterde apparaat-id en inschrijvingsstromen
- Nuttigere foutberichten
- Toegankelijker taal, minder technische jargon
- Mogelijkheid om directe koppelingen naar apps te delen
- Verbeterde prestaties voor grote app-catalogi
- Beter toegankelijk voor alle gebruikers  

De [documentatie voor Intune-bedrijfsportalwebsite](https://docs.microsoft.com/intune-user-help/using-the-intune-company-portal-website) is bijgewerkt, waarbij deze wijzigingen zijn meegenomen. Zie [UI-updates voor Intune-eindgebruiker-apps](../whats-new-app-ui.md) voor een voorbeeld van de app-uitbreidingen.  

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="enhanced-jailbreak-detection-in-compliance-reporting---2198738---"></a>Verbeterde jailbreakdetectie in nalevingsrapporten<!-- 2198738 -->
De instellingsstatussen van de verbeterde jailbreakdetectie worden nu in alle nalevingsrapporten weergegeven in de beheerconsole.

### <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer

#### <a name="scope-tags-for-policies--1081974---"></a>Bereiktags voor beleid<!--1081974 -->
U kunt [bereiktags maken](scope-tags.md) om de toegang tot Intune-resources te beperken. Voeg een bereiktag toe aan een roltoewijzing en voeg de bereiktag vervolgens toe aan een configuratieprofiel. De rol heeft dan alleen toegang tot resources met configuratieprofielen met overeenkomende bereiktags (of zonder bereiktag).





<!-- ########################## -->
## <a name="july-2018"></a>Juli 2018

### <a name="app-management"></a>Appbeheer

#### <a name="line-of-business-lob-app-support-for-macos---1895847---"></a>Ondersteuning voor LOB-apps (line-of-business) voor macOS<!-- 1895847 -->
Met Microsoft Intune kunnen macOS LOB-apps worden geïmplementeerd als **Vereist** of **Beschikbaar met inschrijving**. Eindgebruikers kunnen apps laten implementeren als **Beschikbaar** met behulp van de bedrijfsportal voor macOS of de [bedrijfsportalwebsite](https://portal.manage.microsoft.com).

#### <a name="ios-built-in-app-support-for-kiosk-mode---2051098---"></a>Ondersteuning voor ingebouwde iOS-app voor de kioskmodus<!-- 2051098 -->
Naast de Store-apps en andere beheerde apps kunt u nu een geïntegreerde app (zoals Safari) selecteren die in de kioskmodus op een iOS-apparaat wordt uitgevoerd.

#### <a name="edit-your-office-365-pro-plus-app-deployments---2150145---"></a>Uw implementaties van de Office 365 Pro Plus-app bewerken<!-- 2150145 -->
Als beheerder van Microsoft Intune hebt u meer mogelijkheden om de implementaties van de Office 365 Pro Plus-app te bewerken. Bovendien hoeft u uw implementaties niet meer te verwijderen om een van de eigenschappen van het pakket te wijzigen. Selecteer in Azure Portal **Microsoft Intune** > **Client-apps** > **Apps**. Selecteer uw Office 365 Pro Plus-pakket in de lijst met apps.  

#### <a name="updated-intune-app-sdk-for-android-is-now-available---2744271--"></a>De bijgewerkte Intune App SDK voor Android is nu beschikbaar<!-- 2744271-->
Er is een bijgewerkte versie van de Intune APP SDK voor Android beschikbaar ter ondersteuning van de Android P-release. Als u een app-ontwikkelaar bent en de Intune SDK voor Android gebruikt, moet u de bijgewerkte versie van de Intune App SDK installeren om ervoor te zorgen dat Intune-functionaliteit binnen uw Android-apps blijft werken zoals verwacht op Android P-apparaten. Deze versie van de Intune App SDK biedt een ingebouwde invoegtoepassing waarmee de SDK-updates worden uitgevoerd. U hoeft geen bestaande code die is geïntegreerd, opnieuw te schrijven. Raadpleeg [Intune SDK voor Android](https://github.com/msintuneappsdk/ms-intune-app-sdk-android) voor meer informatie. Als u de oude badging-stijl voor Intune gebruikt, raden we u aan om het pictogram Werkmap te gebruiken. Ga naar [deze GitHub-opslagplaats](https://github.com/msintuneappsdk/intune-app-partner-badge) voor details over de huisstijl.

#### <a name="more-opportunities-to-sync-in-the-company-portal-app-for-windows"></a>Meer synchronisatiemogelijkheden in de Bedrijfsportal-app voor Windows  
Met de Bedrijfsportal-app voor Windows kunt u nu een synchronisatie rechtstreeks vanuit de Windows-taakbalk en het menu Start in werking stellen. Deze functie is vooral nuttig als uw enige taak bestaat uit het synchroniseren van apparaten en verkrijgen van toegang tot bedrijfsbronnen. Klik voor toegang tot de nieuwe functie met de rechtermuisknop op het Bedrijfsportal-pictogram dat is vastgemaakt aan de taakbalk of het menu Start. Selecteer in de menu-opties (ook wel een Jump List genoemd) **Dit apparaat synchroniseren**. De Bedrijfsportal-app wordt geopend op de pagina **Instellingen** en de synchronisatie starten. Zie [Wat is er nieuw in de gebruikersinterface](../whats-new-app-ui.md) voor een overzicht van de nieuwe functionaliteit.   

#### <a name="new-browsing-experiences-in-the-company-portal-app-for-windows"></a>Nieuwe bladerervaringen in de Bedrijfsportal-app voor Windows  
Wanneer u bladert of apps zoekt in de Bedrijfsportal-app voor Windows, kunt u nu schakelen tussen de bestaande **Tegels**-weergave en de recent toegevoegde **Details**-weergave. De nieuwe weergave bevat informatie over toepassingen, zoals de naam, de uitgever, de publicatiedatum en de installatiestatus.  

De pagina **Apps** bevat de weergave **Geïnstalleerd**, waarop u meer informatie kunt vinden over app-installaties die zijn voltooid en die nog bezig zijn. Zie [Wat is er nieuw in de gebruikersinterface](../whats-new-app-ui.md) voor het uiterlijk van de nieuwe weergave.  

#### <a name="improved-company-portal-app-experience-for-device-enrollment-managers"></a>Verbeterde Bedrijfsportal-app-ervaring voor gebruikers van de apparaatinschrijvingsmanagers  
Wanneer een apparaatinschrijvingsmanager (DEM) zich aanmeldt bij de Bedrijfsportal-app voor Windows, wordt nu in de app alleen het huidige DEM-apparaat weergegeven dat wordt uitgevoerd. Dankzij deze verbetering treden er minder time-outs op. Deze time-outs traden voorheen op wanneer de app probeerde alle apparaten met DEM-registratie weer te geven.  

#### <a name="block-app-access-based-on-unapproved-device-vendors-and-models----1425689----"></a>App-toegang blokkeren op basis van niet-goedgekeurde apparaatleveranciers en -modellen <!-- 1425689 ! -->
De Intune-IT-beheerder kan via het Intune-app-beveiligingsbeleid een lijst laten opstellen met Android-fabrikanten en/of iOS-modellen. De IT-beheerder kan een met puntkomma's gescheiden lijst van fabrikanten voor Android-beleid en apparaatmodellen voor iOS-beleid verstrekken. Intune-app-beveiligingsbeleid is alleen van toepassing op Android en iOS. Er zijn twee afzonderlijke acties die kunnen worden uitgevoerd op basis van de opgegeven lijst:
- Het blokkeren van toegang tot een app voor apparaten die niet in de lijst voorkomen.
- Of het selectief wissen van bedrijfsgegevens op apparaten die niet in de lijst voorkomen. 

De gebruiker heeft geen toegang tot de beoogde toepassing als niet is voldaan aan de vereisten van het beleid. Afhankelijk van de instellingen wordt de gebruiker geblokkeerd of worden zakelijke gegevens selectief in de app gewist. Op iOS-apparaten vereist deze functie dat toepassingen (zoals WXP, Outlook, Managed Browser, Yammer) integreren met de Intune APP SDK opdat deze functie wordt afgedwongen voor de doeltoepassingen. Deze integratie vindt doorlopend plaats en is afhankelijk van de specifieke toepassingsteams. Op Android vereist deze functie de meest recente versie van de bedrijfsportal. 

Op apparaten van eindgebruikers moet de Intune-client actie ondernemen op basis van een eenvoudige overeenkomst met de tekenreeksen die zijn opgegeven in de Intune-blade Beveiligingsbeleid van toepassing. Dit is volledig afhankelijk van de waarde die het apparaat rapporteert. De IT-beheerder wordt dan ook aangemoedigd ervoor te zorgen dat het bedoelde gedrag correct is. Dit kan worden bereikt door deze instelling te testen voor verschillende fabrikanten en modellen en voor een kleine groep gebruikers. Selecteer in Microsoft Intune **Client-apps** > **App-beveiligingsbeleid** om app-beveiligingsbeleidsregels weer te geven en toe te voegen. Zie [What are app protection policies](../apps/app-protection-policy.md) (Wat is beveiligingsbeleid voor apps) en [Selectively wipe data using app protection policy access actions in Intune](../apps/app-protection-policies-access-actions.md) (Gegevens selectief wissen met toegangsacties van beveiligingsbeleid voor apps in Intune) voor meer informatie over beveiligingsbeleid voor apps.

#### <a name="access-to-macos-company-portal-pre-release-build---1734766---"></a>Toegang tot de voorlopige versie van de macOS-bedrijfsportal<!-- 1734766 -->
U kunt zich met Microsoft AutoUpdate registreren voor het vroeg ontvangen van builds door deel te nemen aan het Insider-programma. Als u zich registreert, kunt u de bijgewerkte bedrijfsportal gebruiken voordat deze beschikbaar is voor uw eindgebruikers. Zie de [Microsoft Intune-blog](https://blogs.technet.microsoft.com/intunesupport/2018/07/13/use-microsoft-autoupdate-for-early-access-to-the-macos-company-portal-app/)voor meer informatie.

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="create-device-compliance-policy-using-firewall-settings-on-macos-devices---1497640---"></a>Apparaatnalevingsbeleid maken met behulp van firewallinstellingen op macOS-apparaten<!-- 1497640 -->
Wanneer u een nieuw macOS-nalevingsbeleid maakt (**Apparaatcompatibiliteit** > **Beleid** > **Beleid maken** > **Platform: macOS** > **Systeembeveiliging**), ziet u enkele nieuwe instellingen bij **Firewall**: 

- **Firewall**: Configureer hoe binnenkomende verbindingen in uw omgeving worden verwerkt.
- **Binnenkomende verbindingen**: **Blokkeer** alle binnenkomende verbindingen, behalve de verbindingen die vereist zijn voor basisinternetservices, zoals DHCP, Bonjour en IPSec. Deze instelling blokkeert ook alle services voor delen.
- **Verborgen modus**: U kunt de verborgen modus **inschakelen** om te voorkomen dat het apparaat reageert op peilverzoeken. Het apparaat reageert nog wel op binnenkomende verzoeken voor toegestane apps.

Van toepassing op: macOS 10.12 en hoger

#### <a name="new-wi-fi-device-configuration-profile-for-windows-10-and-later---1879077---"></a>Nieuw Wi-Fi-configuratieprofiel voor Windows 10 en hoger<!-- 1879077 -->
Momenteel kunt u Wi-Fi-profielen importeren en exporteren met XML-bestanden. Met deze update kunt u een Wi-Fi-apparaatconfiguratieprofiel rechtstreeks in Intune maken, evenals in enkele andere platformen.

Om het profiel te maken, opent u **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** > **Wi-Fi**. 

Van toepassing op Windows 10 en hoger.

#### <a name="kiosk---obsolete-is-grayed-out-and-cant-be-changed---2149998---"></a>Kiosk - verouderd wordt grijs weergegeven en kan niet worden gewijzigd<!-- 2149998 -->
De Kiosk-functie (preview-versie) (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 n later** > **Apparaatbeperkingen**) is verouderd en wordt vervangen door [Kiosk-instellingen voor Windows 10 en later](../configuration/kiosk-settings.md). Bij deze update wordt de functie **Kiosk - verouderd** grijs weergegeven en de gebruikersinterface kan niet worden gewijzigd of bijgewerkt. 

Zie voor het inschakelen van de kioskmodus [Kiosk-instellingen voor Windows 10 en hoger](../configuration/kiosk-settings.md).

Is van toepassing op Windows 10 en hoger, Windows Holographic for Business

#### <a name="apis-to-use-3rd-party-certification-authorities---2184013---"></a>API's gaan basiscertificeringsinstanties van derden gebruiken<!-- 2184013 -->
Bij deze update komt een Java-API voor waarmee u certificeringsinstanties van derden kunnen integreren met Intune en SCEP. Vervolgens kunnen gebruikers het SCEP-certificaat toevoegen aan een profiel en toepassen op apparaten via MDM.

Intune ondersteunt momenteel [SCEP-aanvragen met Active Directory Certificate Services](../protect/certificates-scep-configure.md).

#### <a name="toggle-to-show-or-not-show-the-end-session-button-on-a-kiosk-browser---2455253---"></a>In-/uitschakelen om de knop Sessie beëindigen wel of niet weer te geven in een Kiosk-browser<!-- 2455253 -->
U kunt configureren of Kiosk-browsers de knop Sessie beëindigen wel of niet weergeven. U ziet het besturingselement in **Apparaatconfiguratie** > **Kiosk (preview-versie)**  > **Kiosk-webbrowser**. Indien ingeschakeld vraagt de app, wanneer een gebruiker op de knop klikt, om bevestiging om de sessie te beëindigen. Wanneer bevestigd, wist de browser alle browsegegevens en keert terug naar de standaard-URL.

#### <a name="create-an-esim-cellular-configuration-profile---2564077---"></a>Een mobiel eSIM-configuratieprofiel maken<!-- 2564077 -->
In **Apparaatconfiguratie** kunt u een mobiel eSIM-profiel maken. U kunt een bestand importeren dat mobiele activeringscodes bevat die u van uw mobiele operator krijgt. Vervolgens kunt u deze profielen implementeren op uw Windows 10-apparaten met eSIM LTE, zoals de Surface Pro LTE en andere voor eSIM geschikte apparaten.

Controleer of uw [apparaten eSIM-profielen ondersteunen](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data).

Van toepassing op Windows 10 en hoger.

#### <a name="select-device-categories-by-using-the-access-work-or-school-settings---1058963-eenotready---"></a>Apparaatcategorieën selecteren met behulp van de instellingen voor Toegang tot werk of school<!-- 1058963 eenotready --> 
Als u [apparaatgroeptoewijzing](../enrollment/device-group-mapping.md) hebt ingeschakeld, wordt gebruikers van Windows 10 nu gevraagd een apparaatcategorie te selecteren na registratie via de knop **Verbinding maken** in **Instellingen** > **Accounts** > **Toegang tot werk- of schoolaccount**. 

#### <a name="use-samaccountname-as-the-account-username-for-email-profiles---1500307---"></a>Gebruik sAMAccountName als de accountgebruikersnaam voor e-mailprofielen<!-- 1500307 -->
U kunt de on-premises **sAMAccountName** gebruiken als de accountgebruikersnaam voor e-mailprofielen voor Android, iOS en Windows 10. U kunt ook het domein verkrijgen van het kenmerk `domain` of `ntdomain` in Azure Active Directory (Azure AD). Of geef een aangepast statisch domein op.

Om deze functie te gebruiken, moet u het kenmerk `sAMAccountName` van uw on-premises Active Directory-omgeving synchroniseren naar Azure AD.

Van toepassing op: [Android](../configuration/email-settings-android.md), [iOS](../configuration/email-settings-ios.md), [Windows 10 en hoger](../configuration/email-settings-windows-10.md)

#### <a name="see-device-configuration-profiles-in-conflict---1556983---"></a>Zie conflicterende apparaatconfiguratieprofielen<!-- 1556983 -->
In **Apparaatconfiguratie** wordt een lijst met de bestaande profielen weergegeven. Met deze update wordt een nieuwe kolom toegevoegd die gegevens bevat over conflicterende profielen. U kunt een rij met een conflict selecteren om de instelling en het profiel met het conflict te zien. 

Meer informatie over [configuratieprofielen beheren](../configuration/device-profile-monitor.md#view-conflicts).

#### <a name="new-status-for-devices-in-device-compliance---2308882---"></a>Nieuwe status voor apparaten in apparaatcompatibiliteit<!-- 2308882 -->
De volgende nieuwe statussen zijn toegevoegd in **Apparaatcompatibiliteit** > **Beleid** > selecteer een beleid > **Overzicht**:
- geslaagd
- fout
- conflict
- in behandeling
- niet van toepassing Er wordt ook een afbeelding weergegeven waarin het aantal apparaten van een ander platform wordt weergegeven. Als u bijvoorbeeld een iOS-profiel kijkt, laat de nieuwe tegel ook het aantal niet-iOS-apparaten zien die ook zijn toegewezen aan dit profiel. Zie [Nalevingsbeleid voor apparaten](../protect/compliance-policy-monitor.md#view-status-of-device-policies).

#### <a name="device-compliance-supports-3rd-party-anti-virus-solutions---2325484---"></a>Apparaatcompatibiliteit ondersteunt antivirusoplossingen van derden<!-- 2325484 -->
Wanneer u een nalevingsbeleid voor apparaten maakt (**Apparaatcompatibiliteit** > **Beleid** > **Beleid maken** > **Platform: Windows 10 en hoger** > **Instellingen** > **Systeembeveiliging**), er zijn nieuwe opties voor **[Apparaatbeveiliging](../protect/compliance-policy-create-windows.md)** : 
- **Antivirus**: Als deze optie is ingesteld op **Vereisen**, kunt u de naleving controleren met behulp van antivirusoplossingen die zijn geregistreerd bij Microsoft Beveiligingscentrum, zoals Symantec en Windows Defender. 
- **AntiSpyware**: Als deze optie is ingesteld op **Vereisen**, kunt u de naleving controleren met behulp van antivirusoplossingen die zijn geregistreerd bij het Microsoft Beveiligingscentrum, zoals Symantec en Windows Defender. 

Van toepassing op: Windows 10 en hoger 

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="automatically-mark-android-devices-enrolled-by-using-samsung-knox-mobile-enrollment-as-corporate---2404851---"></a>Android-apparaten die zijn ingeschreven met Knox Mobile Enrollment van Samsung automatisch markeren als ‘zakelijk’.<!-- 2404851 -->
Android-apparaten die zijn ingeschreven met Samsung Knox Mobile Enrollment worden nu standaard gemarkeerd als **zakelijk** onder **Apparaateigendom**. U hoeft zakelijke apparaten niet handmatig te identificeren met IMEI- of serienummers voordat wordt ingeschreven met Knox Mobile Enrollment.

#### <a name="devices-without-profiles-column-in-the-list-of-enrollment-program-tokens---1853904---"></a>Kolom met apparaten zonder profiel in de lijst met tokens voor het inschrijvingsprogramma<!-- 1853904 -->
De lijst met tokens voor het inschrijvingsprogramma bevat een nieuwe kolom met het aantal apparaten waaraan geen profiel is toegewezen. Dit helpt beheerders bij het toewijzen van profielen aan deze apparaten voordat ze deze toekennen aan gebruikers. Als u de nieuwe kolom wilt zien, gaat u naar **Apparaatinschrijving** > **Apple-inschrijving** > **Tokens voor het inschrijvingsprogramma**.

### <a name="device-management"></a>Apparaatbeheer

#### <a name="bulk-delete-devices-on-devices-blade---1793693---"></a>Apparaten bulksgewijs verwijderen op apparatenblade<!-- 1793693 -->
U kunt nu meerdere apparaten tegelijk verwijderen op de blade Apparaten. Kies **Apparaten** > **Alle apparaten** > selecteer de apparaten die u wilt verwijderen > **Verwijderen**. In het geval van apparaten die niet kunnen worden verwijderd, wordt een melding weergegeven.

#### <a name="google-name-changes-for-android-for-work-and-play-for-work--842873---"></a>Google-naamwijzigingen voor Android for Work en Play for Work<!--842873 -->
Intune heeft de Android for Work-terminologie bijgewerkt om de wijzigingen in de Google-huisstijl te weerspiegelen. De termen Android for Work en Play for Work worden niet meer gebruikt. Afhankelijk van de context wordt andere terminologie gebruikt:
- Android Enterprise verwijst naar de algemene moderne Android-beheerstack.
- Werkprofiel of Profieleigenaar verwijst naar BYOD-apparaten die worden beheerd met werkprofielen.
- Beheerde Google Play verwijst naar de Google App Store.

#### <a name="rules-for-removing-devices---1609459---"></a>Regels voor het verwijderen van apparaten<!-- 1609459 -->
Er zijn nieuwe regels beschikbaar waarmee u automatisch apparaten kunt verwijderen die een aantal dagen niet zijn ingecheckt. U kunt dit aantal instellen. Ga naar het deelvenster **Intune**, selecteer **Apparaten** en selecteer vervolgens **Regels voor opschonen van apparaat** om de nieuwe regel te zien.

#### <a name="corporate-owned-single-use-support-for-android-devices---1630973---"></a>COSU-ondersteuning (Corporate-Owned, Single Use) voor Android-apparaten<!-- 1630973 -->

Intune ondersteunt nu maximaal beheerde, vergrendelde Android-apparaten in de kiosk-stijl. Hierdoor kunnen beheerders het gebruik van een apparaat verder vergrendelen tot een enkele app of een klein aantal apps en kan worden voorkomen dat gebruikers andere apps inschakelen of andere bewerkingen uitvoeren op het apparaat. Om Android-kiosk in te stellen, gaat u naar Intune > **Apparaatinschrijving** > **Android-inschrijving** > **Kiosk- en taakapparaatinschrijvingen**. Zie [Inschrijving van kioskapparaten voor Android Enterprise instellen](../enrollment/android-kiosk-enroll.md) voor meer informatie.

#### <a name="per-row-review-of-duplicate-corporate-device-identifiers-uploaded---2203794--"></a>Controle per rij van geüploade dubbele zakelijke apparaat-id's<!-- 2203794-->
Tijdens het uploaden van bedrijfs-id's geeft Intune nu een lijst weer met dubbele waarden en hebt u de optie om de bestaande gegevens te vervangen of te behouden. Het rapport wordt weergegeven als er dubbele waarden zijn nadat u **Apparaatinschrijving** > **Zakelijke apparaat-id's** > **Id's toevoegen** hebt gekozen. 

#### <a name="manually-add-corporate-device-identifiers---2203803---"></a>Zakelijke apparaat-id's handmatig toevoegen<!-- 2203803 -->
U kunt bedrifjsapparaat-id's nu handmatig toevoegen. Kies **Apparaatinschrijving** > **Zakelijke apparaat-id’s** > **Toevoegen**. 


<!-- ########################## -->
## <a name="june-2018"></a>Juni 2018

### <a name="app-management"></a>Appbeheer

#### <a name="microsoft-edge-mobile-support-for-intune-app-protection-policies---1817882---"></a>Mobiele ondersteuning in Microsoft Edge voor beveiligingsbeleid voor apps in Intune<!-- 1817882 -->
De Microsoft Edge-browser voor mobiele apparaten biedt nu ondersteuning voor het beveiligingsbeleid voor apps dat in Intune is gedefinieerd.

#### <a name="retrieve-the-associated-app-user-model-id-aumid-for-microsoft-store-for-business-apps-in-kiosk-mode---1560077----"></a>De bijbehorende app-gebruikersmodel-id (AUMID) ophalen voor de Microsoft Store voor Bedrijven-apps in de kioskmodus<!-- 1560077 ! -->
Intune kan nu de app-gebruikersmodel-id's (AUMID's) voor Microsoft Store voor Bedrijven-apps (WSfB) ophalen voor een verbeterde configuratie van het kioskprofiel.

Raadpleeg [Apps die u hebt aangeschaft in Microsoft Store voor Bedrijven, beheren met Microsoft Intune](../apps/windows-store-for-business.md) voor meer informatie over Microsoft Store voor Business-apps.

#### <a name="new-company-portal-branding-page---1916370---"></a>Nieuwe huisstijlpagina Bedrijfsportal<!-- 1916370 -->
De huisstijlpagina Bedrijfsportal heeft een nieuwe indeling, berichten en knopinfo.


### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="pradeo---new-mobile-threat-defense-partner---1169249---"></a>Pradeo: nieuwe Mobile Threat Defense-partner<!-- 1169249 -->
U kunt de toegang van mobiele apparaten tot bedrijfsresources beheren door middel van voorwaardelijke toegang op basis van een risicoanalyse die door Pradeo wordt uitgevoerd. Pradeo is een oplossing voor beveiliging tegen bedreigingen op mobiele apparaten die met Microsoft Intune is geïntegreerd.

#### <a name="use-fips-mode-with-the-ndes-certificate-connector---1333688---"></a>De FIPS-modus gebruiken met de NDES-certificaatconnector<!-- 1333688 -->
Wanneer u de NDES-certificaatconnector installeert op een computer waarop de FIPS-modus (Federal Information Processing Standard) is ingeschakeld, werkt het uitgeven en intrekken van certificaten niet zoals verwacht. Deze update bevat ondersteuning voor FIPS met de NDES-certificaatconnector. 

Deze update bevat verder:

- Voor de NDES-certificaatconnector is .NET 4.5 Framework vereist. Dit wordt automatisch geleverd bij Windows Server 2016 en Windows Server 2012 R2. Eerder was .NET 3.5 Framework de minimaal vereiste versie.
- TLS 1.2-ondersteuning wordt geleverd met de NDES-certificaatconnector. Als de server met daarop de NDES-certificaatconnector TLS 1.2 ondersteunt, wordt TLS 1.2 gebruikt. Als de server TLS 1.2 niet ondersteunt, wordt TLS 1.1 gebruikt. Momenteel wordt TLS 1.1 gebruikt voor verificatie tussen de apparaten en de server.

Zie [SCEP-certificaten configureren en gebruiken](../protect/certificates-scep-configure.md) en [PKCS-certificaten configureren en gebruiken](../protect/certficates-pfx-configure.md) voor meer informatie.

#### <a name="support-for-palo-alto-networks-globalprotect-vpn-profiles---1333680----"></a>Ondersteuning voor Palo Alto Networks GlobalProtect VPN-profielen<!-- 1333680 ! -->
Met deze update kunt u Palo Alto Networks GlobalProtect kiezen als VPN-verbindingstype voor VPN-profielen in Intune (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Profieltype** > **VPN**). In deze versie worden de volgende platformen ondersteund: 

- iOS
- Windows 10

#### <a name="additions-to-local-device-security-options-settings---1403702---"></a>Toevoegingen aan instellingen voor de beveiligingsopties van lokale apparaten<!-- 1403702 -->
U kunt nu aanvullende instellingen voor de beveiligingsopties van lokale apparaten voor Windows 10-apparaten configureren. Er zijn extra instellingen beschikbaar voor Microsoft Network Client, Microsoft-netwerkserver, toegang tot het netwerk en beveiliging en interactief aanmelden. U vindt deze instellingen in de Endpoint Protection-categorie wanneer u een configuratiebeleid voor Windows 10-apparaten maakt.

#### <a name="enable-kiosk-mode-on-windows-10-devices---1560072----"></a>Kioskmodus inschakelen op Windows 10-apparaten<!-- 1560072 ! -->
Op Windows 10-apparaten kunt u een configuratieprofiel maken en de kioskmodus inschakelen (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10** > **Apparaatbeperkingen** > **Kioskmodus**). In deze update is de naam van de instelling **Kiosk (preview)** gewijzigd in **Kiosk (verouderd)** . Het gebruik van **Kiosk (verouderd)** wordt niet meer aanbevolen maar de optie blijft nog werken tot de update van juli. **Kiosk (verouderd)** wordt vervangen door het nieuwe profieltype **Kiosk** (**Profiel maken** > **Windows 10** > **Kiosk (preview)** ). Dit profiel bevat de instellingen voor het configureren van kiosken in Windows 10 RS4 en hoger.

Van toepassing op Windows 10 en hoger.

#### <a name="device-profile-graphical-user-chart-is-back---2160133---"></a>De grafische gebruikersgrafiek van het apparaatprofiel is terug<!-- 2160133 -->
Bij het verbeteren van de aantallen die in de grafische gebruikersgrafiek van het apparaatprofiel (**Apparaatconfiguratie** > **Profielen** > selecteer een bestaand profiel > **Overzicht**) worden weergegeven, was de grafische gebruikersgrafiek tijdelijk verwijderd.

In deze update is de grafische gebruikersgrafiek terug. Deze wordt weergegeven in de Azure Portal.

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="support-for-windows-autopilot-enrollment-without-user-authentication---1165118---"></a>Ondersteuning voor Windows Autopilot-inschrijving zonder gebruikersverificatie<!-- 1165118 -->
Intune ondersteunt nu Windows Autopilot-inschrijving zonder gebruikersverificatie. Dit is een nieuwe optie in het implementatieprofiel Windows AutoPilot; 'Automatische piloot implementatiemodus' is ingesteld op 'Zelf-implementerend'.  Het apparaat moet build 17672 of hoger van Windows 10 Insider Preview bevatten en beschikken over een TPM 2.0-chip voor dit type inschrijving. Omdat er geen gebruikersverificatie is vereist, moet u deze optie alleen toewijzen aan apparaten waartoe u fysiek toegang hebt.

#### <a name="new-languageregion-setting-when-configuring-oobe-for-autopilot---1821766---"></a>Nieuwe taal-/landinstelling wanneer u OOBE configureert voor AutoPilot<!-- 1821766 -->
Er is een nieuwe configuratie-instelling beschikbaar om de taal en regio in te stellen voor AutoPilot-profielen tijdens de Out-of-Box Experience. Om de nieuwe instelling te zien, kiest u **Apparaatinschrijving** > **Windows-inschrijving** > **Implementatieprofielen** > **Profiel maken** > **Implementatiemodus** = **Zelf-implementerend** > **Standaardwaarden geconfigureerd**.

#### <a name="new-setting-for-configuring-device-keyboard---1821768---"></a>Nieuwe instelling voor het configureren van het apparaattoetsenbord<!-- 1821768 -->
Er is een nieuwe configuratie-instelling waarmee u tijdens de Out of Box Experience het toetsenbord voor AutoPilot-profielen kunt instellen. Om de nieuwe instelling te zien, kiest u **Apparaatinschrijving** > **Windows-inschrijving** > **Implementatieprofielen** > **Profiel maken** > **Implementatiemodus** = **Zelf-implementerend** > **Standaardwaarden geconfigureerd**.

#### <a name="autopilot-profiles-moving-to-group-targeting---1877935---"></a>AutoPilot-profielen verplaatst naar de groep met<!-- 1877935 -->
AutoPilot-implementatieprofielen kunnen worden toegewezen aan Azure AD-groepen die AutoPilot-apparaten bevatten.

### <a name="device-management"></a>Apparaatbeheer

#### <a name="set-compliance-by-device-location---851881----"></a>Naleving instellen per apparaatlocatie<!-- 851881 ! -->
In sommige situaties wilt u mogelijk de toegang beperken tot bedrijfsresources op een specifieke locatie, gedefinieerd door een netwerkverbinding. U kunt nu een nalevingsbeleid maken (**Apparaatnaleving** > **Locaties**) op basis van het IP-adres van het apparaat. Als het apparaat wordt verplaatst naar een locatie buiten het IP-bereik, heeft het apparaat geen toegang meer tot bedrijfsresources.

Van toepassing op: Android-apparaten met versie 6.0 en hoger, met de bijgewerkte bedrijfsportal-app

#### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>De installatie van consumenten-apps en -ervaringen op Windows 10 Enterprise RS4 Autopilot-apparaten voorkomen<!-- 1621980 -->
U kunt voorkomen dat consumenten-apps en -ervaringen op uw apparaten met Windows 10 Enterprise RS4 AutoPilot kunnen worden geïnstalleerd. Om deze functie te zien, gaat u naar **Intune** > **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Platform** = **Windows 10 of hoger** > **Profieltype** = **Apparaatbeperkingen** > **Configureren** > **Windows Spotlight** > **Consumentenfuncties**. 

#### <a name="uninstall-the-latest-from-windows-10-software-updates---1732948---"></a>De nieuwste versie van software-updates voor Windows 10 verwijderen<!-- 1732948 -->
Indien u een probleem ontdekt op uw Windows 10-computers, dan kunt u de meest recente functie-update of de nieuwste kwaliteitsupdate verwijderen (terugdraaien). U kunt alleen een functie- of kwaliteitsupdate verwijderen voor het servicekanaal waarop het apparaat zich bevindt. Door de verwijdering wordt een beleid geactiveerd waarmee de vorige update op uw Windows 10-computers wordt hersteld. Specifiek voor functie-updates kunt u de tijd beperken van 2 tot 60 dagen waarin een verwijdering van de meest recente versie kan worden toegepast. Als u verwijderopties voor software-update wilt instellen, selecteert u **Software-updates** in de blade **Microsoft Intune** binnen Azure Portal. Kies vervolgens **Windows 10-updateringen** op de blade **Software-updates**. U kunt vervolgens de optie **Verwijderen** kiezen in de sectie **Overzicht**.

#### <a name="search-all-devices-for-imei-and-serial-number---1793685---"></a>Op alle apparaten zoeken naar IMEI-nummer en serienummer<!-- 1793685 -->
U kunt nu zoeken naar IMEI-nummers en serienummers op de blade Alle apparaten (e-mailadres, apparaatnaam en managementnaam zijn nog steeds beschikbaar). Kies in Intune **Apparaten** > **Alle apparaten** > voer de zoekopdracht in het zoekvak in.

#### <a name="management-name-field-will-be-editable---1875989---"></a>Het veld Managementnaam kan worden bewerkt<!-- 1875989 -->
U kunt nu het veld met de managementnaam bewerken op de blade **Eigenschappen** van een apparaat. Als u dit veld wilt bewerken, kiest u **Apparaten** > **Alle apparaten** > kies het apparaat > **Eigenschappen**. U kunt het veld Managementnaam gebruiken om een apparaat op unieke wijze te identificeren.

#### <a name="new-all-devices-filter-device-category---1878520---"></a>Nieuw filter Alle apparaten: Apparaatcategorie<!-- 1878520 -->
U kunt nu de lijst **Alle apparaten** filteren op apparaatcategorie. Als u dit wilt doen, kiest u **Apparaten** > **Alle apparaten** > **Filter** > **Apparaatcategorie**.

#### <a name="use-teamviewer-to-screen-share-ios-and-macos-devices---1985547---"></a>TeamViewer gebruiken voor het delen van schermen op iOS- en MacOS-apparaten<!-- 1985547 -->
Beheerders kunnen nu verbinding maken met [TeamViewer](../remote-actions/teamviewer-support.md) en een sessie voor het delen van schermen starten met iOS- en macOS-apparaten. iPhone-, iPad- en MacOS-gebruikers kunnen hun schermen live delen met andere pc's of mobiele apparaten. 

#### <a name="multiple-exchange-connector-support---2070451---"></a>Ondersteuning voor meerdere Exchange Connectors<!-- 2070451 -->
U bent niet langer beperkt tot één Microsoft Intune Exchange Connector per tenant. Intune ondersteunt nu meerdere Exchange Connectors, zodat u voorwaardelijke toegang van Intune kunt instellen met meerdere on-premises Exchange-organisaties.

Met een on-premises Exchange Connector voor Intune kunt u apparaattoegang tot uw on-premises Exchange-postvakken beheren op basis van of een apparaat is ingeschreven bij Intune en voldoet aan het Intune-nalevingsbeleid voor apparaten. Als u een connector wilt instellen, downloadt u de on-premises Exchange Connector voor Intune vanaf Azure Portal en installeert u deze op een server in uw Exchange-organisatie. Kies op het Microsoft Intune-dashboard **On-premises toegang** en kies vervolgens onder **Installatie** de optie **Exchange ActiveSync-connector**. Download de on-premises Exchange Connector en installeer deze op een server in uw Exchange-organisatie. Nu u niet meer beperkt bent tot één Exchange Connector per tenant, kunt u, als u extra Exchange-organisaties hebt, dit zelfde proces volgen om een connector te downloaden en installeren voor elke extra Exchange-organisatie.

#### <a name="new-device-hardware-detail-ccid---2156657---"></a>Nieuw apparaathardwaredetail: CCID<!-- 2156657 -->
De CCID-informatie (Chip Card Interface Device) is nu opgenomen voor elk apparaat. Als u deze wilt zien, kiest u **Apparaten** > **Alle apparaten** > kies een apparaat > **Hardware**> controleer onder **Netwerkdetails**>

#### <a name="assign-all-users-and-all-devices-as-scope-groups---2196803---"></a>Alle gebruikers en apparaten toewijzen als bereikgroepen<!-- 2196803 -->
U kunt nu alle gebruikers, alle apparaten, en alle gebruikers en alle apparaten in bereikgroepen toewijzen. Kies hiervoor **Intune-rollen** > **Alle rollen** > **Beleid en profielbeheer** > **Toewijzingen** > kies een toewijzing > **Bereik (groepen)** .

#### <a name="udid-information-now-included-for-ios-and-macos-devices---2219806---"></a>UDID-informatie is nu opgenomen voor iOS- en macOS-apparaten<!-- 2219806 -->
Als u de unieke apparaat-id (UDID) voor iOS- en macOS-apparaten wilt zien, gaat u naar **Apparaten** > **Alle apparaten** > kies een apparaat > **Hardware**. UDID is alleen beschikbaar voor bedrijfsapparaten (zoals ingesteld onder **Apparaten** > **Alle apparaten** > kies een apparaat > **Eigenschappen** > **Apparaateigendom**).

### <a name="intune-apps"></a>Intune-apps

#### <a name="improved-troubleshooting-for-app-installation---928990---"></a>Verbeterde probleemoplossing voor app-installatie<!-- 928990 -->
Op apparaten die met Microsoft Intune MDM worden beheerd, mislukken app-installaties wel eens. Als deze apps niet kunnen worden geïnstalleerd, is het soms lastig om de reden van het probleem te achterhalen of om het probleem op te lossen. We brengen een openbare preview-versie uit van de functies voor het oplossen van problemen met apps. U ziet een nieuw knooppunt, **Beheerde apps**, onder elk apparaat. Hier ziet u de apps die via Intune MDM zijn geleverd. In het knooppunt ziet u een lijst met de installatiestatussen van de apps. Als u een bepaalde app selecteert, ziet u de probleemoplossingsweergave voor die app. In de probleemoplossingsweergave ziet u de gehele levenscyclus van de app, zoals wanneer de app is gemaakt, gewijzigd, gebruikt en geleverd aan een apparaat. En als installatie van de app niet is geslaagd, wordt de foutcode weergegeven en een informatief bericht over de oorzaak van de fout. 

#### <a name="intune-app-protection-policies-and-microsoft-edge---1818968---"></a>Beveiligingsbeleid voor apps in Intune en Microsoft Edge<!-- 1818968 -->
De Microsoft Edge-browser voor mobiele apparaten (iOS en Android) biedt nu ondersteuning voor het app-beveiligingsbeleid van Microsoft Intune. Gebruikers van iOS- en Android-apparaten die zich in de Microsoft Edge-toepassing aanmelden met hun zakelijk Azure AD-account worden beveiligd door Intune. Op iOS-apparaten kunnen gebruikers dankzij het beleid **Beheerde browser vereisen voor webinhoud** koppelingen openen in Microsoft Edge wanneer het wordt beheerd.

<!-- ########################## -->
## <a name="may-2018"></a>Mei 2018

### <a name="app-management"></a>Appbeheer

#### <a name="configuring-your-app-protection-policies---2144597-part-2---"></a>Beveiligingsbeleid voor apps configureren<!-- 2144597 Part 2 -->

Ga in de Azure-portal niet naar de serviceblade Intune-app-beveiliging maar naar Intune. Er is nu nog maar één locatie voor beleidsregels voor app-beveiliging in Intune. Al uw beleidsregels voor de beveiliging van apps staan al in de blade **Mobiele app** in Intune onder **App-beveiligingsbeleid**. Door deze integratie wordt het beheer van uw cloud vereenvoudigd. Alle beleidsregels voor de beveiliging van apps staan al in Intune en u kunt al uw eerder geconfigureerde beleid wijzigen. Het beleid voor Intune APP (beveiligingsbeleid voor apps) en voorwaardelijke toegang (CA) bevindt zich nu onder **Voorwaardelijke toegang**, te vinden in het gedeelte **Beheren** op de blade **Microsoft Intune** of in het gedeelte **Beveiliging** op de blade **Azure Active Directory**. Zie [Voorwaardelijke toegang in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) voor meer informatie over het wijzigen van het beleid voor voorwaardelijke toegang. Zie [Wat is beveiligingsbeleid voor apps?](../apps/app-protection-policy.md) voor meer informatie.

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="require-installation-of-policies-apps-certificate-and-network-profiles---1553555---"></a>Installatie van beleid, apps en certificaat- en netwerkprofielen vereisen<!-- 1553555 -->
Beheerders kunnen de toegang tot het Windows 10 RS4-bureaublad voor eindgebruikers blokkeren totdat beleid, apps en certificaat- en netwerkprofielen worden geïnstalleerd tijdens de inrichting van AutoPilot-apparaten. Zie [Een pagina voor de status van de inschrijving instellen](../enrollment/windows-enrollment-status.md) voor meer informatie.

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="samsung-knox-mobile-enrollment-support--1112863--"></a>Ondersteuning voor Samsung Knox Mobile Enrollment<!--1112863-->
Wanneer u Intune met Samsung Knox Mobile Enrollment (KME) gebruikt, kunt u een groot aantal bedrijfseigen Android-apparaten inschrijven. Gebruikers op wifi- of mobiele netwerken kunnen inschrijven met een paar tikken wanneer ze hun apparaten voor het eerst inschakelen. Apparaten kunnen ook met Bluetooth of NFC worden ingeschreven als de Knox-registratie-app wordt gebruikt. Zie [Android-apparaten automatisch registreren met behulp van de Knox Mobile Enrollment van Samsung](../enrollment/android-samsung-knox-mobile-enroll.md) voor meer informatie.

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen 

#### <a name="requesting-help-in-the-company-portal-for-windows-10---1874137---"></a>Hulp aanvragen in de bedrijfsportal voor Windows 10<!-- 1874137 -->
Vanuit de bedrijfsportal voor Windows 10 worden app-logboeken nu rechtstreeks naar Microsoft verzonden wanneer de gebruiker de werkstroom voor hulp bij een probleem in gang zet. Dit vereenvoudigt het detecteren en oplossen van problemen die aan Microsoft worden gemeld.

<!-- ########################## -->
## <a name="april-2018"></a>April 2018

### <a name="app-management"></a>Appbeheer

#### <a name="passcode-support-for-mam-pin-on-android---1438086---"></a>Ondersteuning van de wachtwoordcode voor MAM-pincode op Android<!-- 1438086 -->

Intune-beheerders kunnen instellen dat een toepassing moet worden gestart om een wachtwoordcode af te dwingen in plaats van een numerieke MAM-pincode. Als dit is geconfigureerd, moet de gebruiker een wachtwoordcode instellen en gebruiken wanneer daarom wordt gevraagd, alvorens toegang te krijgen tot toepassingen met MAM-functionaliteit. Een wachtwoordcode wordt gedefinieerd als een numerieke pincode met ten minste één speciaal teken of een hoofdletter/kleine letter. Intune ondersteunt wachtwoordcodes op dezelfde manier als de bestaande numerieke pincodes: er kan een minimumlengte worden ingesteld en tekens en tekenreeksen mogen via de beheerconsole worden herhaald. Voor deze functie moet de meest recente versie van de bedrijfsportal voor Android zijn geïnstalleerd. Deze functie is al beschikbaar voor iOS.

#### <a name="line-of-business-lob-app-support-for-macos---1473977---"></a>Ondersteuning voor LOB-apps (line-of-business) voor macOS<!-- 1473977 -->
Microsoft Intune biedt de mogelijkheid om LOB-apps voor macOS te installeren vanuit Azure Portal. U kunt een macOS LOB-app aan Intune toevoegen nadat deze vooraf is verwerkt door het hulpprogramma dat beschikbaar is in GitHub. Kies op de blade **Intune** van Azure Portal **Client-apps**. Kies op de blade **Client-apps** **Apps** > **Toevoegen**. Selecteer op de blade **App toevoegen** de optie **Line-Of-Business-app**. 

#### <a name="built-in-all-users-and-all-devices-group-for-android-enterprise-work-profile-app-assignment---1813073---"></a>Ingebouwde groepen Alle gebruikers en Alle apparaten voor app-toewijzing voor werkprofielen in Android Enterprise<!-- 1813073 -->
U kunt de ingebouwde groepen **Alle gebruikers** en **Alle apparaten** gebruiken voor het toewijzen van werkprofielen voor Android Enterprise-apps. Zie [App-toewijzingen opnemen en uitsluiten in Microsoft Intune](../apps/apps-inc-exl-assignments.md) voor meer informatie.

#### <a name="intune-will-reinstall-required-apps-that-are-uninstalled-by-users---1947010---"></a>Vereiste apps die door gebruikers zijn verwijderd, worden opnieuw geïnstalleerd in Intune<!-- 1947010 -->
Als een eindgebruiker een vereiste app verwijdert, wordt de app in Intune automatisch binnen 24 uur opnieuw geïnstalleerd in plaats van te wachten op de herbeoordelingscyclus van 7 dagen.

#### <a name="update-where-to-configure-your-app-protection-policies---2144597---"></a>Bijwerken waar u uw app-beveiligingsbeleid configureert<!-- 2144597 -->

U wordt van de serviceblade **Intune-app-beveiliging** in Azure Portal tijdelijk omgeleid naar de blade **Mobiele app**. Al uw beleidsregels voor de beveiliging van apps staan al in de blade **Mobiele app** in Intune onder App-configuratie. Het enige verschil is dat u naar Intune gaat in plaats van naar Intune-app-beveiliging. In april 2018 wordt deze omleiding beëindigd en wordt de serviceblade **Intune-app-beveiliging** helemaal verwijderd, zodat er slechts één locatie voor het app-beveiligingsbeleid in Intune is. 

**Wat betekent dit voor mij?**
Deze wijziging is van invloed op zowel zelfstandige als hybride klanten (Intune met Configuration Manager) van Intune. Door deze integratie wordt het beheer van uw cloud vereenvoudigd.

**Wat moet ik doen om me voor te bereiden op deze wijziging?**
Label **Intune** als favoriet in plaats van de serviceblade **Intune-app-beveiliging** en zorg ervoor dat u bekend bent met de werkstroom voor het beleid voor app-beveiliging in de blade **Mobiele app** in Intune. U wordt slechts tijdelijk omgeleid. De blade **App-beveiliging** wordt uiteindelijk verwijderd. Alle beleidsregels voor de beveiliging van apps staan al in Intune en u kunt uw beleid voor voorwaardelijke toegang wijzigen. Zie [Voorwaardelijke toegang in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) voor meer informatie over het wijzigen van het beleid voor voorwaardelijke toegang. Zie [Wat is beveiligingsbeleid voor apps?](../apps/app-protection-policy.md) voor meer informatie. 

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="device-profile-chart-and-status-list-show-all-devices-in-a-group---1449153---"></a>De profielgrafiek van het apparaat en de statuslijst geven alle apparaten in een groep weer<!-- 1449153 -->
Wanneer u een apparaatprofiel configureert (**Apparaatconfiguratie** > **Profielen**), kunt u het apparaatprofiel, zoals iOS, kiezen. U kunt dit profiel toewijzen aan een groep met iOS-apparaten en niet-iOS-apparaten. De grafiek laat zien dat het profiel wordt toegepast op iOS- *en* niet-iOS-apparaten (**Apparaatconfiguratie** > **Profielen** > selecteer een bestaand profiel > **Overzicht**). Wanneer u de grafiek op het tabblad **Overzicht** selecteert, worden in **Apparaatstatus** alle apparaten in de groep weergegeven, niet alleen de iOS-apparaten. 

Met deze update wordt in de grafiek (**Apparaatconfiguratie** > **Profielen** > selecteer een bestaand profiel > **Overzicht**) alleen het aantal voor het specifieke apparaatprofiel weergegeven. Als bijvoorbeeld het apparaatprofiel wordt toegepast op iOS-apparaten, geeft de grafiek alleen het aantal iOS-apparaten weer. Als u de grafiek selecteert en de **apparaatstatus** opent, worden alleen de iOS-apparaten weergegeven.

Tijdens het maken van deze update is de grafiek tijdelijk verwijderd. 

#### <a name="always-on-vpn-for-windows-10--1333666---"></a>De optie Altijd aan voor VPN in Windows 10<!--1333666 -->

Momenteel kan de optie [Altijd aan](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-auto-trigger-profile#always-on) worden gebruikt op Windows 10-apparaten door een aangepast VPN-profiel te gebruiken dat is gemaakt met OMA-URI.

Met deze update kunnen beheerders de optie Altijd aan rechtstreeks inschakelen in Intune in Azure Portal voor VPN-profielen in Windows 10. VPN-profielen met de optie Altijd aan maken automatisch verbinding wanneer:

- Gebruikers zich aanmelden op hun apparaten
- Het netwerk op het apparaat wijzigt
- Het scherm op het apparaat wordt ingeschakeld nadat het was uitgeschakeld

#### <a name="new-printer-settings-for-education-profiles---1308900---"></a>Nieuwe printerinstellingen voor onderwijsprofielen<!-- 1308900 -->

Voor onderwijsprofielen zijn nieuwe instellingen beschikbaar onder de categorie **Printers**: **Printers**, **Standaardprinter**, **Nieuwe printers toevoegen**.

#### <a name="show-caller-id-in-personal-profile---android-enterprise-work-profile--1098984---"></a>Beller-id in persoonlijk profiel weergeven - werkprofiel Android Enterprise<!--1098984 -->
Wanneer u een persoonlijk profiel op een apparaat gebruikt, kunnen eindgebruikers de details van de beller-id van een zakelijke contactpersoon niet weergegeven. 

Er is een nieuwe instelling in **Android Enterprise** > **Apparaatbeperkingen** > **Instellingen voor werkprofiel**:
- Beller-id van zakelijk contactpersoon weergeven in persoonlijk profiel

Indien ingeschakeld (niet-geconfigureerd), worden de details van de beller die een zakelijke contactpersoon is, weergegeven in het persoonlijke profiel. Indien geblokkeerd, wordt het nummer van deze zakelijke contactpersoon niet weergegeven in het persoonlijke profiel. 

Van toepassing op: Apparaten met Android-werkprofiel voor Android 6.0 en hoger

#### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings--1102252-----from-1802-and-1804--"></a>Er worden nieuwe Windows Defender Credential Guard-instellingen toegevoegd aan de Endpoint Protection-instellingen<!--1102252 --><!--from 1802 and 1804-->

In deze update, [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard) (**Apparaatconfiguratie** > **Profielen** > **Eindpuntbeveiliging**) zijn de volgende instellingen opgenomen: 

- **Windows Defender Credential Guard**: met deze optie wordt Credential Guard ingeschakeld met beveiliging op basis van virtualisatie. Het inschakelen van deze functie helpt om de referenties te beveiligen bij de volgende keer opstarten, wanneer **Niveau van platformbeveiliging met Beveiligd opstarten** en **Beveiliging op basis van virtualisatie** beide zijn ingeschakeld. Opties zijn onder andere:
  - **Uitgeschakeld**: als Credential Guard eerder was ingeschakeld met de optie **Ingeschakeld zonder vergrendeling**, wordt het extern uitgeschakeld.

  - **Ingeschakeld met UEFI-vergrendeling**: deze optie zorgt ervoor dat Credential Guard niet kan worden uitgeschakeld met behulp van een registersleutel of via Groepsbeleid. Als u Credential Guard wilt uitschakelen nadat u deze instelling hebt gebruikt, moet u het Groepsbeleid instellen op Uitgeschakeld. Vervolgens verwijdert u de beveiligingsfunctie van elke computer, met een fysiek aanwezige gebruiker. Met deze stappen wordt de configuratie gewist die is behouden in UEFI. Zolang de UEFI-configuratie behouden blijft, is Credential Guard ingeschakeld.

  - **Ingeschakeld zonder vergrendeling**: Met deze optie kan Credential Guard extern worden uitgeschakeld via Groepsbeleid. Op de apparaten die gebruikmaken van deze instelling moet ten minste Windows 10 (versie 1511) worden uitgevoerd.

De volgende afhankelijke technologieën worden automatisch ingeschakeld bij het configureren van Credential Guard: 

- **Beveiliging op basis van virtualisatie (VBS)** : met deze optie wordt Beveiliging op basis van virtualisatie (VBS) ingeschakeld bij de volgende keer opnieuw opstarten. Beveiliging op basis van virtualisatie maakt gebruik van Windows Hypervisor om ondersteuning te bieden voor beveiligingsservices. Beveiligd opstarten is vereist.
- **Beveiligd opstarten met DMA (Direct Memory Access)** : met deze optie schakelt u VBS met Beveiligd opstarten en directe geheugentoegang in. Voor DMA-beveiliging is hardwareondersteuning vereist. Deze wordt alleen ingeschakeld op apparaten die juist zijn geconfigureerd. 

#### <a name="use-a-custom-subject-name-on-scep-certificate---2064190---"></a>Een aangepaste onderwerpnaam gebruiken in een SCEP-certificaat<!-- 2064190 -->
U kunt de algemene naam **OnPremisesSamAccountName** gebruiken in een aangepast onderwerp voor een SCEP-certificaatprofiel. U kunt bijvoorbeeld `CN={OnPremisesSamAccountName})` gebruiken.

#### <a name="block-camera-and-screen-captures-on-android-enterprise-work-profiles---1098977---"></a>De camera en schermopnamen blokkeren in werkprofielen in Android Enterprise<!-- 1098977 -->
Er zijn twee nieuwe eigenschappen beschikbaar die kunnen worden geblokkeerd wanneer u apparaatbeperkingen voor Android-apparaten configureert: 
- Camera: hiermee blokkeert u de toegang tot alle camera's op het apparaat
- Schermopname: hiermee blokkeert u de schermopname en voorkomt u ook dat de inhoud wordt weergegeven op weergaveapparaten die geen beveiligde video-uitvoer hebben

Van toepassing op apparaten met Android Enterprise-werkprofiel.

#### <a name="use-cisco-anyconnect-client-for-ios---1333708---"></a>Cisco AnyConnect-client voor iOS gebruiken<!-- 1333708 -->

Wanneer u een nieuw VPN-profiel voor iOS maakt, zijn er nu twee opties: **Cisco AnyConnect** en **Cisco Legacy AnyConnect**. Cisco AnyConnect-profielen bieden ondersteuning voor 4.0.7x en nieuwere versies. Bestaande iOS Cisco AnyConnect VPN-profielen krijgen het label **Cisco Legacy AnyConnect** en blijven op dezelfde manier werken met Cisco AnyConnect 4.0.5x en oudere versies.

> [!NOTE]
> Deze wijziging is alleen van toepassing op iOS. Er blijft slechts één Cisco AnyConnect-optie voor platforms van Android, werkprofielen van Android Enterprise en macOS.


### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="new-enrollment-steps-for-users-on-devices-with-macos-high-sierra-10132--1734567---"></a>Nieuwe stappen voor registratie voor gebruikers op apparaten met macOS High Sierra 10.13.2+<!--1734567 -->
macOS High Sierra 10.13.2 introduceert het concept Gebruiker goedgekeurd voor MDM-inschrijving. Met goedgekeurde inschrijvingen kan in Intune een aantal vertrouwelijke instellingen worden beheerd. Zie de ondersteuningsdocumentatie van Apple https://support.apple.com/HT208019 voor meer informatie.

Apparaten die zijn geregistreerd met behulp van de bedrijfsportal voor macOS, worden beschouwd als Niet door de gebruiker goedgekeurd, tenzij de eindgebruiker Systeemvoorkeuren opent en handmatig goedkeuring verleent. De bedrijfsportal voor macOS vraagt gebruikers van macOS 10.13.2 en hoger om hun registratie aan het einde van het registratieproces handmatig goed te keuren. De Intune-beheerconsole rapporteert of een geregistreerd apparaat door de gebruiker is goedgekeurd.

#### <a name="jamf-enrolled-macos-devices-can-now-register-with-intune---2370684---"></a>Via Jamf ingeschreven macOS-apparaten kunnen nu worden geregistreerd bij Intune<!-- 2370684 -->
In versie 1.3 en 1.4 van de bedrijfsportal voor macOS zijn Jamf-apparaten niet geregistreerd bij Intune. Dit probleem is opgelost in versie 1.4.2 van de macOS-portal.

#### <a name="updated-help-experience-in-company-portal-app-for-android---1631531---"></a>Bijgewerkte Help-ervaring voor de bedrijfsportal-app voor Android<!-- 1631531 -->
We hebben de Help-ervaring in de bedrijfsportal-app voor Android bijgewerkt, zodat deze overeenkomt met de aanbevolen procedures voor het Android-platform. Wanneer gebruikers nu een probleem in de app tegenkomen, kunnen ze op **Menu** > **Help** tikken en:
- Logboeken met diagnostische gegevens uploaden naar Microsoft.
- Een e-mail verzenden waarin het probleem en de incident-id worden vermeld voor een ondersteuningsmedewerker.  

Als u de bijgewerkte Help-ervaring wilt bekijken, gaat u naar [Logboeken via e-mail verzenden](/intune-user-help/send-logs-to-your-it-admin-by-email-android) en [Fouten naar Microsoft verzenden](/intune-user-help/send-logs-to-microsoft-android).


#### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table---1471783---"></a>Nieuwe tabel met fouten bij inschrijving, trendgrafieken en oorzaken van fouten<!-- 1471783 -->
Op de overzichtspagina voor inschrijvingen kunt u de trend van mislukte inschrijvingen en de top vijf van oorzaken van fouten bekijken. Door te klikken op de grafiek of de tabel kunt u inzoomen op gegevens om advies voor probleemoplossing en suggesties voor herstel te krijgen.


### <a name="device-management"></a>Apparaatbeheer

#### <a name="advanced-threat-protection-atp-and-intune-are-fully-integrated---1629303---"></a>ATP (Advanced Threat Protection) en Intune zijn volledig geïntegreerd<!-- 1629303 -->

[Advanced Threat Protection (ATP)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection) geeft het risiconiveau van Windows 10-apparaten weer. In Windows Defender Security Center (ATP-portal) kunt u een verbinding maken met Microsoft Intune. Zodra de verbinding is gemaakt, wordt Intune-nalevingsbeleid gebruikt om het acceptabele bedreigingsniveau te bepalen. Als het bedreigingsniveau wordt overschreden, kan de toegang tot verschillende apps in uw organisatie worden geblokkeerd op basis van Azure AD-beleid (Azure Directory) voor voorwaardelijke toegang.

Met deze functie kunnen bestanden worden gescand, bedreigingen worden gedetecteerd en alle risico's op uw Windows 10-apparaten worden gerapporteerd via ATP.

Zie [ATP voor voorwaardelijke toegang inschakelen in Intune](../protect/advanced-threat-protection.md).

#### <a name="support-for-user-less-devices---1637553---"></a>Ondersteuning voor apparaten zonder gebruiker<!-- 1637553 -->
Intune ondersteunt de mogelijkheid om naleving te evalueren op een apparaat zonder gebruiker, zoals de Microsoft Surface Hub. Nalevingsbeleid kan worden gericht op specifieke apparaten. Naleving (en niet-naleving) kan worden vastgesteld voor apparaten waaraan geen gebruiker is gekoppeld.

#### <a name="delete-autopilot-devices---1713650---"></a>Autopilot-apparaten verwijderen<!-- 1713650 -->
Intune-beheerders kunnen [AutoPilot-apparaten verwijderen](../enrollment/enrollment-autopilot.md#delete-autopilot-devices).

#### <a name="improved-device-deletion-experience--1832333---"></a>Verbeterde ervaring bij het verwijderen van apparaten<!--1832333 -->
U hoeft geen bedrijfsgegevens meer te verwijderen of de fabrieksinstellingen op een apparaat te herstellen voordat u [een apparaat uit Intune verwijdert](../remote-actions/devices-wipe.md#delete-devices-from-the-intune-portal).

Meld u voor deze nieuwe ervaring aan in Intune en selecteer **Apparaten** > **Alle apparaten** > de naam van het apparaat > **Verwijderen**.

Als u een bevestiging van het wissen of terugtrekken van een apparaat wilt blijven ontvangen, kunt u de standaard levenscyclusroute van een apparaat gebruiken door **Bedrijfsgegevens verwijderen** en **Fabrieksinstellingen terugzetten** uit te geven voordat u **Verwijderen** selecteert. 

#### <a name="play-sounds-on-ios-when-in-lost-mode---1947769---"></a>Geluid afspelen in iOS in de modus Apparaat verloren<!-- 1947769 -->
Wanneer iOS-apparaten onder supervisie in MDM (Mobile Device Management) in de modus [Apparaat verloren](../remote-actions/device-lost-mode.md) zijn, kunt u [een geluid afspelen](../remote-actions/device-locate.md#activate-lost-mode-sound-alert-on-an-ios-device) (**Apparaten** > **Alle apparaten** > selecteer een iOS-apparaat > **Overzicht** > **Meer**). Het geluid wordt afgespeeld totdat het apparaat niet meer de modus Apparaat verloren heeft of totdat een gebruiker het geluid op het apparaat uitschakelt. Van toepassing op apparaten met iOS 9.3 en hoger.

#### <a name="block-or-allow-web-results-in-searches-made-on-an-intune-device--1972804--"></a>Webresultaten blokkeren of toestaan in zoekopdrachten die zijn uitgevoerd op een Intune-apparaat<!--1972804-->

Beheerders kunnen nu webresultaten blokkeren in zoekopdrachten die zijn uitgevoerd op een apparaat.

#### <a name="improved-error-messaging-for-apple-mdm-push-certificate-upload-failure---2172331---"></a>Verbeterde foutberichten voor fouten bij het uploaden van Apple MDM-pushcertificaten<!-- 2172331 -->

In het foutbericht wordt uitgelegd dat dezelfde Apple ID moet worden gebruikt bij het vernieuwen van een bestaand MDM-certificaat.

#### <a name="test-the-company-portal-for-macos-on-virtual-machines---2216679---"></a>De bedrijfsportal voor macOS testen op virtuele machines<!-- 2216679 -->

We hebben een handleiding gepubliceerd om IT-beheerders te helpen bij het testen van de bedrijfsportal-app voor macOS op virtuele machines in Parallels Desktop en VMware Fusion. U vindt meer informatie in [virtuele macOS-machines inschrijven voor testen](../enrollment/macos-enroll.md#enroll-virtual-macos-machines-for-testing).

### <a name="intune-apps"></a>Intune-apps

#### <a name="user-experience-update-for-the-company-portal-app-for-ios--1412866---"></a>Update van de gebruikerservaring voor de bedrijfsportal-app voor iOS<!--1412866 -->
Er is een grote update uitgebracht van de gebruikerservaring voor de bedrijfsportal-app voor iOS. De update is voorzien van een volledig nieuw visueel ontwerp met een gemoderniseerd uiterlijk. De functionaliteit van de app is behouden. De gebruiksvriendelijkheid en toegankelijkheid zijn echter verhoogd.  

U ziet ook:
- Ondersteuning voor iPhone X.
- De app start sneller en de laadsnelheid is verhoogd, zodat gebruikers tijd besparen.
- Aanvullende voortgangsbalken om gebruikers de meest recente statusgegevens te bieden.
- Verbeteringen in de manier waarop gebruikers logboeken uploaden, zodat u het eenvoudiger kunt melden als er iets fout gaat.  

Ga naar [Wat is er nieuw in de gebruikersinterface van de app?](../whats-new-app-ui.md) om het bijgewerkte uiterlijk te bekijken.

#### <a name="protect-on-premises-exchange-data-using-intune-app-and-ca---1056954---"></a>On-premises Exchange-gegevens beveiligen met Intune APP en CA<!-- 1056954 -->
U kunt nu Intune App Policy Protection (APP) en Conditional Access (CA) gebruiken om de toegang tot on-premises Exchange-gegevens te beveiligen met Outlook Mobile. Als u beleid voor app-beveiliging wilt toevoegen of wijzigen in Azure Portal, selecteert u **Microsoft Intune** > **Client-apps** > **Beleid voor app-beveiliging**. Voordat u deze functie gebruikt, moet u ervoor zorgen dat u voldoet aan de [Outlook voor iOS- en Android-vereisten](https://technet.microsoft.com/library/mt846639(v=exchg.160).aspx).


### <a name="user-interface"></a>Gebruikersinterface

#### <a name="improved-device-tiles-in-the-windows-10-company-portal--2213364---"></a>Verbeterde apparaattegels in de Windows 10-bedrijfsportal<!--2213364 -->

De tegels zijn bijgewerkt zodat ze toegankelijker zijn voor gebruikers met een beperkt gezichtsvermogen en beter werken op schermlezers.

#### <a name="send-diagnostic-reports-in-company-portal-app-for-macos---2216677---"></a>Diagnostische rapporten in de bedrijfsportal-app voor macOS verzenden<!-- 2216677 -->
De bedrijfsportal-app voor macOS-apparaten wordt bijgewerkt om de manier waarop gebruikers fouten in Intune rapporteren, te verbeteren. Vanuit de bedrijfsportal-app kunnen werknemers:

- Diagnostische rapporten rechtstreeks naar het Microsoft-ontwikkelteam uploaden.
- Via e-mail een incident-id aan het IT-ondersteuningsteam van uw bedrijf verzenden.

Zie [Fouten verzenden voor macOS](/intune-user-help/send-errors-macos) voor meer informatie.

#### <a name="intune-adapts-to-fluent-design-system-in-the-company-portal-app-for-windows-10---1195010---"></a>Intune wordt aangepast aan Fluent Design System in de bedrijfsportal-app voor Windows 10<!-- 1195010 -->
De Intune-bedrijfsportal-app voor Windows 10 is bijgewerkt met de [Fluent Design System-navigatieweergave](https://docs.microsoft.com/windows/uwp/design/basics/navigation-basics). Aan de zijkant van de app wordt een statische verticale lijst weergegeven met alle toplevelpagina's. Klik op een willekeurige koppeling om snel pagina's weer te geven en te schakelen tussen pagina's. Dit is de eerste van verschillende updates die onderdeel uitmaken van onze voortdurende inspanningen om een meer adaptieve, intuïtieve en vertrouwde versie van Intune te maken. Ga naar [Wat is er nieuw in de gebruikersinterface van de app?](../whats-new-app-ui.md) om het bijgewerkte uiterlijk te bekijken.

<!-- ########################## -->
## <a name="march-2018"></a>maart 2018

### <a name="app-management"></a>Appbeheer

#### <a name="alerts-for-expiring-ios-line-of-business-lob-apps-for-microsoft-intune---748789---"></a>Waarschuwingen voor iOS LOB-apps (Line-of-Business) voor Microsoft Intune die verlopen<!-- 748789 -->

In Azure Portal waarschuwt Intune u met betrekking tot iOS line-of-business-apps die bijna verlopen. Nadat een nieuwe versie van de iOS line-of-business-app is geüpload, verwijdert Intune de melding over het verlopen uit de lijst met apps. Deze melding wordt alleen actief voor recent geüploade iOS Line-Of-Business-apps. Een waarschuwing wordt 30 dagen voordat het inrichtingsprofiel voor iOS line-of-business-app verloopt, weergegeven. Zodra het profiel is verlopen, wijzigt de waarschuwing in Verlopen.

#### <a name="customize-your-company-portal-themes-with-hex-codes--1049561---"></a>De bedrijfsportalthema's aanpassen met hexadecimale codes<!--1049561 -->

U kunt de themakleur in de bedrijfsportal-apps aanpassen met hexadecimale codes. Wanneer u de hexadecimale code invoert, wordt door Intune bepaald met welke tekstkleur de hoogste mate van contrast tussen de tekstkleur en de achtergrondkleur wordt bereikt. U kunt in **Client-apps** > **Bedrijfsportal** bekijken hoe de tekstkleur en uw bedrijfslogo bij deze kleur worden weergegeven.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise---1813081---"></a>App-toewijzing op basis van groepen opnemen en uitsluiten voor Android Enterprise<!-- 1813081 -->

Android Enterprise (voorheen bekend als Android for Work) ondersteunt het opnemen en uitsluiten van groepen, maar biedt geen ondersteuning voor de vooraf gemaakte ingebouwde groepen **Alle gebruikers** en **Alle apparaten**. Zie [App-toewijzingen opnemen en uitsluiten in Microsoft Intune](../apps/apps-inc-exl-assignments.md) voor meer informatie.


### <a name="device-management"></a>Apparaatbeheer

### <a name="export-all-devices-into-csv-files-in-ie-microsoft-edge-or-chrome---2258071---"></a>Alle apparaten exporteren naar CSV-bestanden in Internet Explorer, Microsoft Edge of Chrome<!-- 2258071 -->
In **Apparaten** > **Alle apparaten** kunt u de apparaten **Exporteren** naar een lijst met de CSV-indeling. Gebruikers van Internet Explorer (IE) met meer dan 10.000 apparaten kunnen hun apparaten exporteren naar meerdere bestanden. Elk bestand bevat maximaal 10.000 apparaten.

Gebruikers van Microsoft Edge en Chrome met meer dan 30.000 apparaten kunnen hun apparaten exporteren naar meerdere bestanden. Elk bestand bevat maximaal 30.000 apparaten.

[Apparaten beheren](../remote-actions/device-management.md) biedt meer details over wat u kunt doen met apparaten die u beheert.

#### <a name="new-security-enhancements-in-the-intune-service----1637539---"></a>Verbeteringen in de beveiliging van de Intune-service <!-- 1637539 -->   

Er is een wisselknop in Intune geïntroduceerd waarmee zelfstandige klanten van Intune zonder dat een beleid is toegewezen apparaten kunnen behandelen als **Compatibel** (beveiligingsfunctie uitgeschakeld) of als **Niet compatibel** (beveiligingsfunctie ingeschakeld). Hierdoor kan alleen toegang tot de resources worden verkregen nadat de compatibiliteit van het apparaat is geëvalueerd.

De invloed van deze functies verschilt, afhankelijk of u al nalevingsbeleid hebt toegewezen of niet.

- Als u een nieuw of bestaand account hebt en geen nalevingsbeleid aan uw apparaten hebt toegewezen, wordt de wisselknop automatisch ingesteld op **Compatibel**. De functie wordt standaard uitgeschakeld als standaardinstelling in de console. Dit heeft geen gevolgen voor eindgebruikers.
- Als u een bestaand account hebt en u apparaten hebt waaraan een nalevingsbeleid is toegewezen, wordt de wisselknop automatisch ingesteld op **Niet-compatibel**. Zodra de update van maart is uitgerold, is deze functie beschikbaar als standaardinstelling.

Als u nalevingsbeleid met voorwaardelijke toegang (CA) gebruikt en deze functie is ingeschakeld, worden apparaten waaraan niet ten minste één nalevingsbeleid is toegewezen, door CA geblokkeerd. Eindgebruikers die zijn gekoppeld aan deze apparaten en eerder toegang hadden tot e-mail, raken deze toegang kwijt tenzij u ten minste één nalevingsbeleid aan alle apparaten toewijst.   

Hoewel de standaard status in-/uitschakelen wordt weergegeven in de gebruikersinterface na de update van maart, wordt deze status niet direct afgedwongen. Eventuele wijzigingen die u in de wisselknop aanbrengt, hebben geen invloed op de compatibiliteit van apparaten totdat de wisselknop in uw account werkt. In Berichtencentrum vindt u informatie over wanneer uw account is bijgewerkt. Dit kan enkele dagen duren nadat uw Intune-service is bijgewerkt voor maart.

**Aanvullende informatie**: [https://aka.ms/compliance_policies](https://aka.ms/compliance_policies)

#### <a name="enhanced-jailbreak-detection---846515---"></a>Verbeterde jailbreakdetectie<!-- 846515 -->

Verbeterde jailbreak-detectie is een nieuwe nalevingsinstelling die de manier waarop Intune opengebroken apparaten evalueert, verbetert. De instelling zorgt ervoor dat het apparaat regelmatiger incheckt bij Intune, waarvoor de locatieservices van het apparaat worden gebruikt. Ook heeft dit invloed op het batterijvermogen.

#### <a name="reset-passwords-for-android-o-devices---1238299---"></a>Wachtwoorden voor Android O-apparaten opnieuw instellen<!-- 1238299 -->
U kunt de wachtwoorden voor ingeschreven Android 8.0-apparaten opnieuw instellen met werkprofielen. Wanneer u een aanvraag Wachtwoord opnieuw instellen naar een Android 8.0-apparaat verzendt, wordt hiermee een nieuw wachtwoord voor het ontgrendelen van het apparaat of een vraag voor het beheerde profiel ingesteld voor de huidige gebruiker. Het wachtwoord of de vraag wordt verzonden en is onmiddellijk van kracht.

#### <a name="targeting-compliance-policies-to-devices-in-device-groups--1307012---"></a>Nalevingsbeleid afstemmen op apparaten in apparaatgroepen<!--1307012 -->

U kunt nalevingsbeleid richten op gebruikers in gebruikersgroepen. Met deze update kunt u nalevingsbeleid richten op apparaten in apparaatgroepen. Apparaten waarop beleid is gericht als onderdeel van apparaatgroepen, ontvangen geen maatregelen voor naleving.

#### <a name="new-management-name-column---1333586---"></a>Nieuwe kolom Naam voor beheer<!-- 1333586 -->
 Een nieuwe kolom met de naam **Naam voor beheer** is beschikbaar op de blade voor apparaten. Dit is een automatisch gegenereerde, niet bewerkbare naam die per apparaat wordt toegewezen op basis van de volgende formule:
- Standaardnaam voor alle apparaten: <username><em><devicetype></em><enrollmenttimestamp>
- Voor bulksgewijs toegevoegde apparaten: < PackageId/ProfileId ><em><DeviceType></em><EnrollmentTime>

Dit is een optionele kolom in de blade voor apparaten. Deze is niet standaard beschikbaar en u kunt de kolom alleen openen via de kolomkiezer. De naam van het apparaat wordt niet beïnvloed door deze nieuwe kolom.

#### <a name="ios-devices-are-prompted-for-a-pin-every-15-minutes--1550837---"></a>Op iOS-apparaten wordt elke vijftien minuten om een pincode gevraagd<!--1550837 -->
Nadat een nalevings- of configuratiebeleid op een iOS-apparaat is toegepast, wordt gebruikers elke vijftien minuten gevraagd een pincode in te stellen. Gebruikers wordt continu gevraagd een pincode in te stellen totdat de code is ingesteld.

#### <a name="schedule-your-automatic-updates--1805514---"></a>Automatische updates plannen<!--1805514 -->
In Intune kunt u met behulp van de [instellingen voor Windows 10-updatering](../protect/windows-update-for-business-configure.md) bepalen hoe automatische updates worden geïnstalleerd. Met deze update kunt u terugkerende updates plannen en de week, de dag en het tijdstip opgeven.

#### <a name="use-fully-distinguished-name-as-subject-for-scep-certificate--2221763---"></a>De volledige DN-naam gebruiken als onderwerp voor het SCEP-certificaat<!--2221763 -->
Wanneer u een SCEP-certificaatprofiel maakt, voert u de naam van het onderwerp in. Met deze update kunt u als naam van het onderwerp de volledige DN-naam gebruiken. Selecteer **Aangepast** bij **Onderwerpnaam** en voer `CN={{OnPrem_Distinguished_Name}}` in. Als u de variabele `{{OnPrem_Distinguished_Name}}` wilt gebruiken, moet u het gebruikerskenmerk `onpremisesdistingishedname` met behulp van [Azure Active Directory (AD) Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) synchroniseren met uw exemplaar van Azure AD.

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="enable-bluetooth-contact-sharing---android-for-work--1098983---"></a>Delen van contactpersonen via Bluetooth inschakelen - Android for Work<!--1098983 -->
Standaard wordt op Android-apparaten voorkomen dat contactpersonen in het werkprofiel kunnen worden gesynchroniseerd met Bluetooth-apparaten. Als gevolg hiervan worden contactpersonen in het werkprofiel niet weergegeven bij Nummerweergave voor Bluetooth-apparaten.

Er is een nieuwe instelling in **Android for Work** > **Apparaatbeperkingen** > **Instellingen voor werkprofiel**:
- Contactpersoon delen via Bluetooth

De Intune-beheerder kan deze instellingen configureren om delen in te schakelen. Dit is handig als u een apparaat wilt koppelen met een Bluetooth-apparaat in auto's waarop Nummerweergave wordt weergegeven voor handsfreegebruik. Als deze instellingen zijn ingeschakeld, worden de contactpersonen voor het werkprofiel weergegeven. Als deze instellingen niet zijn ingeschakeld, worden de contactpersonen voor het werkprofiel niet weergegeven.

#### <a name="configure-gatekeeper-to-control-macos-app-download-source---1690459---"></a>Gatekeeper configureren om de downloadbron van macOS-apps te beheren<!-- 1690459 -->

U kunt Gatekeeper configureren om uw apparaten te beveiligen tegen apps door te bepalen waarvan de apps kunnen worden gedownload. U kunt de volgende downloadbronnen configureren: **Mac App Store**, **Mac App Store en geïdentificeerde ontwikkelaars** of **Overal**. U kunt ook configureren of gebruikers een app kunnen installeren door middel van CTRL+klikken om deze Gatekeeper-voorzieningen te overschrijven.

Deze instellingen zijn te vinden onder **Apparaatconfiguratie** -> **Profiel maken** -> **macOS** -> **Eindpuntbeveiliging**.

#### <a name="configure-the-mac-application-firewall---1690461---"></a>De firewall van Mac-toepassingen configureren<!-- 1690461 -->

U kunt de firewall van Mac-toepassingen configureren. U kunt deze gebruiken om verbindingen per toepassing te controleren, in plaats van per poort. Zo kunt u beter profiteren van de voordelen van firewallbeveiliging. Bovendien helpt het te voorkomen dat ongewenste apps gebruikmaken van netwerkpoorten die zijn geopend voor legitieme apps.

Deze functie kunt u vinden onder **Apparaatconfiguratie** -> **Profiel maken** -> **macOS** -> **Eindpuntbeveiliging**.

Wanneer u de Firewall-instelling hebt ingeschakeld, kunt u de firewall configureren met behulp van twee strategieën:

- Alle binnenkomende verbindingen blokkeren

   U kunt alle binnenkomende verbindingen voor de doelapparaten blokkeren. Als u ervoor kiest om dit te doen, worden binnenkomende verbindingen voor alle apps geblokkeerd.

- Specifieke apps blokkeren of toestaan

   U kunt specifieke apps toestemming geven binnenkomende verbindingen te ontvangen of u kunt apps blokkeren. U kunt ook de verborgen modus inschakelen om reacties op peilverzoeken te voorkomen.

#### <a name="detailed-error-codes-and-messages---1376342---"></a>Gedetailleerde foutcodes en -berichten<!-- 1376342 -->

In uw apparaatconfiguratie kunnen gedetailleerde foutcodes en -berichten worden weergegeven. In deze verbeterde rapportage worden de instellingen, de status van deze instellingen en details over probleemoplossing weergegeven.

##### <a name="more-information"></a>Meer informatie

- Alle binnenkomende verbindingen blokkeren

   Hiermee worden alle services voor delen (zoals delen van bestanden en delen van het scherm) geblokkeerd en kunnen deze geen binnenkomende verbindingen ontvangen. De systeemservices die nog steeds binnenkomende verbindingen kunnen ontvangen, zijn:
  - configd - implementeert DHCP en andere services voor netwerkconfiguratie
  - mDNSResponder - implementeert Bonjour
  - racoon - implementeert IPSec

    Als u services voor delen wilt gebruiken, zorgt u ervoor dat **Binnenkomende verbindingen** is ingesteld op **Niet geconfigureerd** (niet op **Blokkeren**).

- Verborgen modus

   Schakel deze optie in om te voorkomen dat de computer reageert op peilverzoeken. De computer reageert nog wel op binnenkomende verzoeken voor toegestane apps. Onverwachte aanvragen, zoals ICMP (ping), worden genegeerd.

#### <a name="disable-checks-on-device-restart--1805490---"></a>Controles bij opnieuw starten van apparaat uitschakelen<!--1805490 -->
In Intune kunt u [software-updates beheren](../protect/windows-update-for-business-configure.md). In deze update is de eigenschap <strong>Controles voor opnieuw starten</strong> beschikbaar en standaard ingeschakeld. Als u de standaardcontroles wilt overslaan die worden uitgevoerd wanneer u een apparaat opnieuw start (controle van actieve gebruikers, batterijniveau, enzovoort), selecteert u <strong>Overslaan</strong>.

#### <a name="new-windows-10-insider-preview-channels-available-for-deployment-rings---1746293---"></a>Nieuwe Windows 10 Insider Preview-kanalen beschikbaar voor implementatieringen<!-- 1746293 -->
U kunt nu de volgende Windows 10 Insider Preview-onderhoudskanalen selecteren wanneer u een Windows 10-implementatiering maakt:
- Windows Insider build &#8208; Snel
- Windows Insider build &#8208; Langzaam
- Windows Insider-build vrijgeven 

Zie [Insider Preview-builds beheren](https://insider.windows.com/for-business-organization-admin/) voor meer informatie over deze kanalen.   
Zie [Software-updates beheren in Intune](../protect/windows-update-for-business-configure.md) voor meer informatie over het maken van implementatiekanalen in Intune.

### <a name="new-windows-defender-exploit-guard-settings---1631893---"></a>Nieuwe instellingen voor Windows Defender Exploit Guard<!-- 1631893 -->

Zes nieuwe instellingen voor <strong>Kwetsbaarheid voor aanvallen verminderen</strong> en uitgebreide mogelijkheden voor <strong>Gecontroleerde mappentoegang: mapbeveiliging</strong> zijn nu beschikbaar. U kunt deze instellingen vinden op: Apparaatconfiguratie\Profielen\
Profiel maken\Endpoint Protection\Windows Defender Exploit Guard.

#### <a name="attack-surface-reduction"></a>Kwetsbaarheid voor aanvallen verminderen

|Naam van de instelling  |Instellingsopties  |Beschrijving  |
|---------|---------|---------|
|Geavanceerde ransomwarebeveiliging|Ingeschakeld, Controleren, Niet geconfigureerd|Gebruik agressieve ransomwarebeveiliging.|
|Referentiediefstal in het Windows-subsysteem voor de lokale beveiligingsautoriteit markeren|Ingeschakeld, Controleren, Niet geconfigureerd|Markeer referentiediefstal in het Windows-subsysteem voor de lokale beveiligingsautoriteit (lsass.exe).|
|Het maken van processen met PSExec- en WMI-opdrachten|Blokkeren, Controleren, Niet geconfigureerd|Blokkeer het maken van processen die afkomstig zijn van PSExec- en WMI-opdrachten.|
|Niet-vertrouwde en niet-ondertekende processen die worden uitgevoerd vanaf een USB|Blokkeren, Controleren, Niet geconfigureerd|Blokkeer niet-vertrouwde en niet-ondertekende processen die worden uitgevoerd vanaf een USB.|
|Uitvoerbare bestanden die niet voldoen aan een bepaalde gangbaarheid, ouderdom of aan criteria voor vertrouwde lijsten blokkeren|Blokkeren, Controleren, Niet geconfigureerd|Voorkomen dat uitvoerbare bestanden worden uitgevoerd tenzij deze voldoen aan een bepaalde gangbaarheid, ouderdom of criteria voor vertrouwde lijsten.|

#### <a name="controlled-folder-access"></a>Gecontroleerde mappentoegang

|              Naam van de instelling               |                                                              Instellingsopties                                                              | Beschrijving |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Mapbeveiliging (al geïmplementeerd) | Niet geconfigureerd, Inschakelen, Alleen controleren (al geïmplementeerd)<br><br> <strong>Nieuw</strong><br>Schijfwijziging blokkeren, schijfwijziging controleren |             |

Beveilig bestanden en mappen tegen niet-geautoriseerde wijzigingen door niet-goedgekeurde apps.<br><br>**Inschakelen**: Voorkom dat bestanden in beveiligde mappen door niet-vertrouwde apps worden gewijzigd of verwijderd en dat gegevens door deze apps naar schijfsectoren worden weggeschreven.<br><br>
**Alleen schijfwijziging blokkeren**:<br>Voorkom dat gegevens door niet-vertrouwde apps worden weggeschreven naar schijfsectoren. Bestanden in beveiligde mappen kunnen nog steeds door niet-vertrouwde apps worden gewijzigd of verwijderd.|

### <a name="intune-apps"></a>Intune-apps

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview---710595---"></a>Azure Active Directory-websites kunnen de Intune Managed Browser-app vereisen en ondersteunen eenmalige aanmelding voor de Managed Browser (openbare preview)<!-- 710595 -->

Met Azure Active Directory (Azure AD) kunt u nu de toegang tot websites op mobiele apparaten beperken tot de Intune Managed Browser-app. In de Managed Browser blijven websitegegevens veilig en gescheiden van de persoonlijke gegevens van eindgebruikers. Daarnaast ondersteunt de Managed Browser eenmalige aanmelding voor sites die door Azure AD worden beveiligd. Door u aan te melden bij de Managed Browser of door de Managed Browser op een apparaat te gebruiken met een andere app die door Intune wordt beheerd, krijgt de Managed Browser toegang tot bedrijfssites die door Azure AD worden beveiligd, zonder dat de gebruiker referenties hoeft in te voeren. Deze functionaliteit is van toepassing op sites zoals Outlook Web Access (OWA) en SharePoint Online, evenals andere bedrijfssites zoals intranetbronnen die via de Azure App Proxy worden geopend. Zie [Besturingselementen voor toegang in Azure Active Directory Voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-controls) voor meer informatie.

#### <a name="company-portal-app-for-android-visual-updates--976944---"></a>Bedrijfsportal-app voor visuele Android-updates<!--976944 -->

De bedrijfsportal-app voor Android is bijgewerkt om de richtlijnen voor [Ontwerp van materiaal](https://material.io/) van Android te volgen. In het Engelstalige artikel [What's new in app UI](../whats-new-app-ui.md) (Nieuw in de gebruikersinterface van de app) kunt u afbeeldingen van de nieuwe pictogrammen bekijken.

#### <a name="company-portal-enrollment-improved---1874230-eeready--"></a>Inschrijving bedrijfsportal verbeterd<!-- 1874230 eeready-->
Gebruikers die een apparaat inschrijven via de bedrijfsportal in Windows 10-build 1703 en hoger, kunnen de eerste stap van de inschrijving voltooien zonder de app te verlaten.
#### <a name="hololens-and-surface-hub-now-appear-in-device-lists--1725868---"></a>HoloLens en Surface Hub nu worden weergegeven in de apparaatlijsten<!--1725868 -->
Er is ondersteuning toegevoegd voor het weergeven van HoloLens- en Surface Hub-apparaten die via Intune zijn geregistreerd bij de bedrijfsportal-app voor Android.

#### <a name="custom-book-categories-for-volume-purchase-program-vpp-ebooks---1488911---"></a>Aangepaste boekcategorieën voor eBooks in het VPP-programma (volume-aankoopprogramma)<!-- 1488911 -->
U kunt aangepaste eBook-categorieën maken en vervolgens VPP eBooks toewijzen aan deze aangepaste eBook-categorieën. Eindgebruikers kunnen de nieuwe eBook-categorieën en de boeken die zijn toegewezen aan de categorieën bekijken. Zie [Apps en boeken met Microsoft Intune beheren die via het Volume Purchase Program zijn gekocht](../apps/vpp-apps.md) voor meer informatie.  

#### <a name="support-changes-for-company-portal-app-for-windows-send-feedback-option---2070166---"></a>Optie voor feedback verzenden voor wijzigingen in de ondersteuning voor de bedrijfsportal-app voor Windows<!-- 2070166 -->
Vanaf 30 april 2018 werkt de optie **Feedback verzenden** in de bedrijfsportal-app voor Windows alleen op apparaten met de Windows 10 Jubileumupdate (1607) en hoger. De optie voor het verzenden van feedback wordt niet meer ondersteund bij gebruik van de bedrijfsportal-app voor Windows met:  
- Windows 10, 1507 release  
- Windows 10, 1511 release  
- Windows Phone 8.1 

Als uw apparaat Windows 10 RS1 of hoger gebruikt, moet u de nieuwste versie van de Windows-bedrijfsportal downloaden in de Store. Als u een niet-ondersteunde versie uitvoert, kunt u feedback blijven verzenden via de volgende kanalen: 
- De Feedback Hub-app in Windows 10
- E-mail WinCPfeedback@microsoft.com  

#### <a name="new-windows-defender-application-guard-settings---1631890---"></a>Nieuwe instellingen voor Windows Defender Application Guard<!-- 1631890 -->

- **Grafische versnelling inschakelen**: Beheerders kunnen voortaan een virtuele grafische processor inschakelen voor Windows Defender Application Guard. Met deze instelling kan de CPU taken voor de grafische weergave overdragen aan de vGPU. Dit kan de prestaties verbeteren wanneer u met websites werkt die veeleisende grafische weergaven bevatten of een video in de container bekijkt.

- **SaveFilestoHost**: Beheerders kunnen ervoor zorgen dat bestanden vanuit Microsoft Edge, die in de container wordt uitgevoerd, worden doorgegeven aan het systeem van het hostbestand. Wanneer u deze optie inschakelt, kunnen gebruikers bestanden uit Microsoft Edge in de container downloaden naar het hostbestandsysteem.

#### <a name="mam-protection-policies-targeted-based-on-management-state---1665993---"></a>Gericht MAM-beleid op basis van de beheerstatus<!-- 1665993 -->
U kunt zich richten op MAM-beleid op basis van de beheerstatus van het apparaat:
- **Android-apparaten**: u kunt zich richten op niet-beheerde apparaten, door Intune beheerde apparaten en door Intune beheerde Android Enterprise-profielen (voorheen Android for Work).
- **iOS-apparaten**: u kunt zich richten op niet-beheerde apparaten (alleen MAM) of door Intune beheerde apparaten.

    > [!NOTE]
    > - iOS-ondersteuning voor deze functionaliteit wordt in april 2018 uitgerold.

Zie [Beleidsregels voor app-beveiliging toepassen op basis van de apparaatbeheerstatus](../apps/app-protection-policies.md) voor meer informatie.

#### <a name="improvements-to-the-language-in-the-company-portal-app-for-windows---1683758---"></a>Verbeteringen in de taal in de bedrijfsportal-app voor Windows<!-- 1683758 -->
In de bedrijfsportal voor Windows 10 is de taal gebruiksvriendelijker en meer specifiek voor uw bedrijf gemaakt. Zie [Wat is er nieuw in de gebruikersinterface van apps?](../whats-new-app-ui.md) voor een aantal voorbeeldafbeeldingen van wat we hebben gedaan.

#### <a name="new-additions-to-our-docs-about-user-privacy---1440709---"></a>Toevoegingen aan onze documentatie over de privacy van gebruikers<!-- 1440709 -->
Als onderdeel van onze inspanning om eindgebruikers meer controle over hun gegevens en privacy te geven, is de documentatie bijgewerkt waarin wordt uitgelegd hoe u gegevens die lokaal zijn opgeslagen door de bedrijfsportal-apps kunt weergeven en verwijderen. U vindt deze updates op:

- **Android**: [Uw Android-apparaat uit Intune verwijderen](/intune-user-help/unenroll-your-device-from-intune-android)
- **Android, als de gebruiker de gebruiksvoorwaarden heeft afgewezen**: [Uw apparaatbeheer verwijderen als u de gebruiksvoorwaarden hebt afgewezen](/intune-user-help/unenroll-your-device-from-intune-if-you-declined-terms-of-use-android)
- **iOS**: [Uw iOS-apparaat uit Intune verwijderen](/intune-user-help/unenroll-your-device-from-intune-ios)
- **Windows**: [Uw Windows-apparaat uit Intune verwijderen](/intune-user-help/unenroll-your-device-from-intune-windows)

<!-- ########################## -->
## <a name="february-2018"></a>februari 2018

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts---747685---"></a>Intune-ondersteuning voor meerdere Apple DEP-/Apple School Manager-accounts<!-- 747685 -->

Intune ondersteunt nu de inschrijving van apparaten uit maximaal 100 verschillende [Apple Device Enrollment Program (DEP)](../enrollment/device-enrollment-program-enroll-ios.md)- of [Apple School Manager](../enrollment/apple-school-manager-set-up-ios.md)-accounts. Elk geüpload token kan afzonderlijk worden beheerd voor registratieprofielen en -apparaten. Er kan automatisch een ander registratieprofiel worden toegewezen per geüpload DEP-/School Manager-token. Als er meerdere School Manager-tokens zijn geüpload, kan er per keer slechts één worden gedeeld met Microsoft School Data Sync.

Na de migratie werken de bèta Graph API's en gepubliceerde scripts voor het beheren van Apple DEP of ASM over Graph niet meer. Nieuwe bèta Graph API's zijn in ontwikkeling en zullen na de migratie worden uitgebracht.

#### <a name="see-enrollment-restrictions-per-user---1634444-eeready-wnready---"></a>Inschrijvingsbeperkingen per gebruiker bekijken<!-- 1634444 eeready wnready -->
Op de blade **Probleemoplossing** kunt u nu de [inschrijvingsbeperkingen](../enrollment/enrollment-restrictions-set.md) bekijken die gelden voor elke gebruiker. Selecteer hiervoor **Inschrijvingsbeperkingen** in de lijst **Toewijzingen**.

#### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment---747625-eeready---"></a>Nieuwe optie voor gebruikersverificatie voor bulkinschrijving met Apple<!-- 747625 eeready -->

> [!NOTE]
> Voor nieuwe tenants is deze nieuwe optie direct beschikbaar. Voor bestaande tenants wordt deze functie in april geïmplementeerd. Zolang deze implementatie nog niet is voltooid, hebt u mogelijk geen toegang tot deze nieuwe functies.

Intune biedt voor de volgende registratiemethoden de optie om apparaten te verifiëren met behulp van de bedrijfsportal-app:

- Apple Device Enrollment Program
- Apple School Manager
- Apple Configurator Enrollment

Wanneer u de bedrijfsportal-optie gebruikt, kan meervoudige verificatie van Azure Active Directory worden afgedwongen zonder deze registratiemethoden te blokkeren.

Wanneer u de bedrijfsportal-optie gebruikt, slaat Intune verificatie van gebruikers in de iOS-configuratieassistent over voor registratie op basis van gebruikersaffiniteit. Dit betekent dat het apparaat in eerste instantie wordt geregistreerd als een apparaat zonder gebruiker en derhalve geen configuraties of beleid van gebruikersgroepen ontvangt. Het apparaat ontvangt alleen configuraties en beleid voor apparaatgroepen. Intune installeert echter automatisch de bedrijfsportal-app op het apparaat. De eerste gebruiker die de bedrijfsportal-app start en zich aanmeldt, wordt in Intune aan het apparaat gekoppeld. Op dat punt ontvangt de gebruiker configuraties en beleid van zijn of haar gebruikersgroepen. De koppeling met de gebruiker kan niet worden gewijzigd zonder opnieuw te registreren.

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts---747685-eeready---"></a>Intune-ondersteuning voor meerdere Apple DEP-/Apple School Manager-accounts<!-- 747685 eeready -->

Intune ondersteunt nu de registratie van apparaten uit maximaal 100 verschillende Apple Device Enrollment Program (DEP)- of Apple School Manager-accounts. Elk geüpload token kan afzonderlijk worden beheerd voor registratieprofielen en -apparaten. Er kan automatisch een ander registratieprofiel worden toegewezen per geüpload DEP-/School Manager-token. Als er meerdere School Manager-tokens zijn geüpload, kan er per keer slechts één worden gedeeld met Microsoft School Data Sync.

Na de migratie werken de bèta Graph API's en gepubliceerde scripts voor het beheren van Apple DEP of ASM over Graph niet meer. Nieuwe bèta Graph API's zijn in ontwikkeling en zullen na de migratie worden uitgebracht.

### <a name="remote-printing-over-a-secure-network---1709994----"></a>Extern afdrukken via een beveiligd netwerk<!-- 1709994  -->
Met de oplossingen voor draadloos mobiel afdrukken van PrinterOn kunnen gebruikers op afstand vanaf elke locatie en op elk gewenst moment afdrukken via een beveiligd netwerk. PrinterOn wordt geïntegreerd met de Intune APP SDK voor zowel iOS als Android. U kunt app-beveiligingsbeleid toepassen op deze app via de Intune-blade **App-beveiligingsbeleid** in de beheerconsole. Eindgebruikers kunnen de app 'PrinterOn for Microsoft' downloaden via de Play Store of iTunes voor gebruik binnen hun Intune-ecosysteem.

### <a name="macos-company-portal-support-for-enrollments-that-use-the-device-enrollment-manager---1352411---"></a>Ondersteuning van de macOS-bedrijfsportal voor inschrijvingen die gebruikmaken van de apparaatinschrijvingsmanager<!-- 1352411 -->

Gebruikers kunnen nu de apparaatinschrijvingsmanager gebruiken bij het inschrijven via de macOS-bedrijfsportal.

### <a name="device-management"></a>Apparaatbeheer

#### <a name="windows-defender-health-status-and-threat-status-reports--854704---"></a>Rapporten over de integriteitsstatus en bedreigingsstatus van Windows Defender<!--854704 -->

Inzicht in de integriteit en status van Windows Defender is essentieel voor het beheren van Windows-pc's.  Dankzij deze update worden door Intune nieuwe rapporten en acties toegevoegd aan de status en integriteit van de Windows Defender-agent. Wanneer u een rapport voor het verzamelen van de status gebruikt in de [workload voor apparaatcompatibiliteit](../protect/compliance-policy-monitor.md), worden apparaten weergegeven waarvoor een of meer van de volgende acties moeten worden uitgevoerd:
- het bijwerken van de handtekening
- Opnieuw opstarten
- handmatige interventie
- volledige scan
- interventie die is vereist voor andere agentstatussen

In een gedetailleerd rapport voor elke statuscategorie worden de afzonderlijke pc's vermeld waarvoor aandacht is vereist of die als **schoon** zijn gerapporteerd.

#### <a name="new-privacy-settings-for-device-restrictions--1308926---"></a>Nieuwe privacyinstellingen voor apparaatbeperkingen<!--1308926 -->
Er zijn [twee nieuwe privacyinstellingen](../configuration/device-restrictions-windows-10.md#privacy) voor apparaten beschikbaar:
- **Gebruikersactiviteiten publiceren**: Stel dit in op **Blokkeren** om gedeelde ervaringen en de detectie van recent gebruikte resources in de taakwisselaar te voorkomen.
- **Alleen lokale activiteiten**: Stel dit in op **Blokkeren** om gedeelde ervaringen en de detectie van recent gebruikte resources in de taakwisselaar alleen op basis van de lokale activiteit te voorkomen.

#### <a name="new-settings-for-the-microsoft-edge-browser--1469166---"></a>Nieuwe instellingen voor de Microsoft Edge-browser<!--1469166 -->
Er zijn [twee nieuwe instellingen](../configuration/device-restrictions-windows-10.md#microsoft-edge-browser) beschikbaar voor apparaten met de Microsoft Edge-browser: **Pad naar het bestand met favorieten** en **Wijzigingen in Favorieten**.

### <a name="app-management"></a>Appbeheer

#### <a name="protocol-exceptions-for-applications--1035509---"></a>Protocoluitzonderingen voor toepassingen<!--1035509 -->

U kunt nu uitzonderingen maken voor het gegevensoverdrachtbeleid van Intune MAM (Mobile Application Management) om specifieke onbeheerde toepassingen te openen. Dergelijke toepassingen moeten door de IT-afdeling als vertrouwde toepassingen worden beschouwd. Afgezien van de uitzonderingen die u maakt, wordt de gegevensoverdracht nog steeds beperkt tot de toepassingen die door Intune worden beheerd als uw beleid voor gegevensoverdracht is ingesteld op **Uitsluitend beheerde apps**. U kunt de beperkingen maken met behulp van protocollen (iOS) of pakketten (Android).

U kunt bijvoorbeeld het Webex-pakket toevoegen als een uitzondering op het MAM-gegevensoverdrachtbeleid. Op die manier kunnen Webex-koppelingen in een beheerd e-mailbericht van Outlook rechtstreeks in de Webex-toepassing worden geopend. De gegevensoverdracht wordt nog steeds beperkt in andere onbeheerde toepassingen. Zie [Uitzonderingen voor gegevensoverdrachtsbeleid voor apps](../apps/app-protection-policies-exception.md) voor meer informatie.

#### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results---1469193---"></a>Versleutelde gegevens van Windows Information Protection (WIP) in zoekresultaten van Windows<!-- 1469193 -->
Met een instelling in het WIP-beleid (Windows-gegevensbescherming) kunt u zelf regelen of met WIP versleutelde gegevens in de zoekresultaten van Windows worden opgenomen. Stel deze optie voor app-beveiligingsbeleid in door de optie **Windows Search-indexeerfunctie toestaan om versleutelde items te zoeken** te selecteren in de **geavanceerde instellingen** van het Windows-gegevensbeschermingsbeleid. Het beveiligingsbeleid van de app moet worden ingesteld op het *Windows 10*-platform en de **inschrijvingsstatus** van het app-beleid moet worden ingesteld op **Bij inschrijving**. Zie [De Windows Search-indexeerfunctie toestaan om versleutelde items te zoeken](../apps/windows-information-protection-policy-create.md#allow-windows-search-indexer-to-search-encrypted-items) voor meer informatie.

#### <a name="configuring-a-self-updating-mobile-msi-app---1740840---"></a>Een mobiele MSI-app configureren die automatisch wordt bijgewerkt<!-- 1740840 -->
U kunt een bekende mobiele MSI-app die automatisch wordt bijgewerkt configureren om de versiecontrole te negeren. Met deze functie kunt u voorkomen dat er een racevoorwaarde optreedt. Dit type racevoorwaarde kan bijvoorbeeld optreden wanneer de app die automatisch wordt bijgewerkt door de app-ontwikkelaar ook wordt bijgewerkt door Intune. Er kan door beide partijen worden geprobeerd om een versie van de app op een Windows-client af te dwingen, waardoor een conflict kan ontstaan. Voor deze automatisch bijgewerkte MSI-apps kunt u de instelling **App-versie negeren** in de blade **App-informatie** configureren. Wanneer deze instelling op **Ja** staat, negeert Microsoft Intune de app-versie die is geïnstalleerd op de Windows-client.

#### <a name="related-sets-of-app-licenses-supported-in-intune---1864117---"></a>Gerelateerde groepen van app-licenties worden in Intune ondersteund<!-- 1864117 -->
Intune in Azure Portal biedt nu ondersteuning voor de vermelding van gerelateerde groepen van app-licenties als één app-item in de gebruikersinterface. Bovendien worden apps met offlinelicenties die zijn gesynchroniseerd vanuit Microsoft Store voor Bedrijven geconsolideerd in één app-vermelding. Eventuele implementatiegegevens uit de afzonderlijke pakketten worden naar die ene vermelding gemigreerd. Als u gerelateerde groepen van app-licenties in Azure Portal wilt bekijken, selecteert u **App-licenties** op de blade **Client-apps**.

### <a name="device-configuration"></a>Apparaatconfiguratie
#### <a name="windows-information-protection-wip-file-extensions-for-automatic-encryption---1463582---"></a>Bestandsextensies voor automatische versleuteling door Windows-gegevensbescherming (WIP)<!-- 1463582 -->
Met een instelling in het Windows-gegevensbeschermingsbeleid (WIP) kunt u nu opgeven welke bestandsextensies automatisch worden versleuteld bij het kopiëren vanaf een Server Message Block-share (SMB) binnen het bedrijf, zoals gedefinieerd in het WIP-beleid.

#### <a name="configure-resource-account-settings-for-surface-hubs"></a>Resourceaccountinstellingen voor Surface Hubs configureren

U kunt nu resourceaccountinstellingen voor Surface Hubs extern configureren.

Het resourceaccount wordt door een Surface Hub gebruikt voor verificatie bij Exchange/Skype, zodat kan worden deelgenomen aan een vergadering.
U kunt een uniek resourceaccount maken, zodat de Surface Hub in de vergadering kan worden weergegeven als de vergaderruimte.
Bijvoorbeeld een resourceaccount als **Vergaderruimte B41/6233**.

> [!NOTE]
> - Als u velden leeg laat, overschrijft u de eerder geconfigureerde kenmerken op het apparaat.
>
> - Resourceaccounteigenschappen kunnen in de Surface Hub dynamisch worden gewijzigd. Bijvoorbeeld als wisseling van het wachtwoord is ingeschakeld. Het is dus mogelijk dat de waarden in de Azure-console pas na enige tijd in overeenstemming zijn met de waarden op het apparaat.
>
>   Om te weten wat er op dat moment op de Surface Hub is geconfigureerd, kunnen de resourceaccountgegevens in de hardware-inventaris (die al een interval van zeven dagen heeft) of als alleen-lezen eigenschappen worden opgenomen. Voor een grotere nauwkeurigheid na de uitvoering van de externe actie kunt u de status van de parameters onmiddellijk na het uitvoeren van de actie ophalen om het account/de parameters op de Surface Hub bij te werken.

##### <a name="attack-surface-reduction"></a>Kwetsbaarheid voor aanvallen verminderen

|Naam van de instelling  |Instellingsopties  |Beschrijving  |
|---------|---------|---------|
|Uitvoering van met een wachtwoord beschermde uitvoerbare inhoud uit e-mails|Blokkeren, Controleren, Niet geconfigureerd|Voorkom dat uitvoerbare bestanden met wachtwoordbescherming uit e-mails worden uitgevoerd.|
|Geavanceerde ransomwarebeveiliging|Ingeschakeld, Controleren, Niet geconfigureerd|Gebruik agressieve ransomwarebeveiliging.|
|Referentiediefstal in het Windows-subsysteem voor de lokale beveiligingsautoriteit markeren|Ingeschakeld, Controleren, Niet geconfigureerd|Markeer referentiediefstal in het Windows-subsysteem voor de lokale beveiligingsautoriteit (lsass.exe).|
|Het maken van processen met PSExec- en WMI-opdrachten|Blokkeren, Controleren, Niet geconfigureerd|Blokkeer het maken van processen die afkomstig zijn van PSExec- en WMI-opdrachten.|
|Niet-vertrouwde en niet-ondertekende processen die worden uitgevoerd vanaf een USB|Blokkeren, Controleren, Niet geconfigureerd|Blokkeer niet-vertrouwde en niet-ondertekende processen die worden uitgevoerd vanaf een USB.|
|Uitvoerbare bestanden die niet voldoen aan een bepaalde gangbaarheid, ouderdom of aan criteria voor vertrouwde lijsten blokkeren|Blokkeren, Controleren, Niet geconfigureerd|Voorkomen dat uitvoerbare bestanden worden uitgevoerd tenzij deze voldoen aan een bepaalde gangbaarheid, ouderdom of criteria voor vertrouwde lijsten.|

##### <a name="controlled-folder-access"></a>Gecontroleerde mappentoegang

|              Naam van de instelling               |                                                              Instellingsopties                                                              | Beschrijving |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Mapbeveiliging (al geïmplementeerd) | Niet geconfigureerd, Inschakelen, Alleen controleren (al geïmplementeerd)<br><br> <strong>Nieuw</strong><br>Schijfwijziging blokkeren, schijfwijziging controleren |             |

Beveilig bestanden en mappen tegen niet-geautoriseerde wijzigingen door niet-goedgekeurde apps.<br><br>**Inschakelen**: Voorkom dat bestanden in beveiligde mappen door niet-vertrouwde apps worden gewijzigd of verwijderd en dat gegevens door deze apps naar schijfsectoren worden weggeschreven.<br><br>
**Alleen schijfwijziging blokkeren**:<br>Voorkom dat gegevens door niet-vertrouwde apps worden weggeschreven naar schijfsectoren. Bestanden in beveiligde mappen kunnen nog steeds door niet-vertrouwde apps worden gewijzigd of verwijderd.|

#### <a name="additions-to-system-security-settings-for-windows-10-and-later-compliance-policies--1704133--"></a>Toevoegingen aan systeembeveiligingsinstellingen voor nalevingsbeleid voor Windows 10 en hoger<!--1704133-->

Toevoegingen aan de nalevingsinstellingen voor Windows 10 zijn nu beschikbaar, waaronder het verplichte gebruik van een firewall en Windows Defender Antivirus.

### <a name="intune-apps"></a>Intune-apps

#### <a name="support-for-offline-apps-from-the-microsoft-store-for-business--1222672--"></a>Ondersteuning voor offlineapps uit Microsoft Store voor Bedrijven<!--1222672-->
Offlineapps die u hebt gekocht in Microsoft Store voor Bedrijven worden voortaan gesynchroniseerd met Azure Portal. Vervolgens kunt u deze apps implementeren in apparaat- of gebruikersgroepen. Offlineapps worden geïnstalleerd door Intune en niet door de Store.

#### <a name="prevent-end-users-from-manually-adding-or-removing-accounts-in-the-work-profile---1728700---"></a>Hiermee voorkomt u dat eindgebruikers handmatig accounts in het werkprofiel kunnen toevoegen of uit het werkprofiel kunnen verwijderen<!-- 1728700 -->

Wanneer u de Gmail-app implementeert in een Android for Work-profiel, kunt u voorkomen dat eindgebruikers accounts handmatig aan het werkprofiel toevoegen of uit het werkprofiel verwijderen door de instelling **Accounts toevoegen en verwijderen** te gebruiken in het Android for Work-apparaatbeperkingsprofiel.

<!-- ########################## -->
## <a name="january-2018"></a>januari 2018

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire---1639263---"></a>Waarschuwingen voor vervallen tokens en tokens die binnenkort vervallen<!-- 1639263 -->
De overzichtspagina geeft nu waarschuwingen weer voor vervallen tokens en tokens die binnenkort vervallen. Wanneer u op een waarschuwing voor een specifiek token klikt, gaat u naar de detailpagina van dat token.  Als u op een waarschuwing met meerdere tokens klikt, gaat u naar een lijst met alle tokens met hun status. Beheerders moeten hun tokens vóór de vervaldatum vernieuwen.

### <a name="device-management"></a>Apparaatbeheer

#### <a name="remote-erase-command-support-for-macos-devices---1438084---"></a>Ondersteuning voor externe opdracht 'Wissen' voor macOS-apparaten<!-- 1438084 -->

Beheerders kunnen op afstand een opdracht voor wissen geven voor macOS-apparaten.

> [!IMPORTANT]
> De wisopdracht kan niet ongedaan worden gemaakt en moet voorzichtig worden gebruikt.

Met de wisopdracht worden alle gegevens van een apparaat verwijderd, inclusief het besturingssysteem. Hiermee wordt ook het apparaat uit Intune verwijderd. De gebruiker krijgt geen waarschuwing te zien en het verwijderen gebeurt onmiddellijk nadat de opdracht is gegeven.

U moet wel een 6-cijferige herstelpincode configureren. Deze pincode kan worden gebruikt voor het ontgrendelen van het gewiste apparaat, waarna het besturingssysteem opnieuw wordt geïnstalleerd. Nadat het verwijderen is gestart, wordt de pincode weergegeven in een statusbalk op de overzichtsblade van het apparaat in Intune. De pincode blijft intact zolang het verwijderen wordt uitgevoerd. Nadat het verwijderen is voltooid, verdwijnt het apparaat volledig uit Intune-beheer. Zorg ervoor dat u de herstelpincode vastlegt zodat degene die het apparaat terugzet deze kan gebruiken.

#### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token---820870---"></a>Licenties intrekken voor een token van het iOS-volume-aanschafprogramma<!-- 820870 -->
U kunt de licentie van alle iOS-apps uit het volume-aanschafprogramma (VPP) voor een bepaalde VPP-token intrekken.

### <a name="app-management"></a>Appbeheer

#### <a name="revoking-ios-volume-purchase-program-apps----820863---"></a>Apps uit het volume-aankoopprogramma voor iOS intrekken <!-- 820863 -->
Voor een bepaald apparaat met een of meer iOS-apps uit het volume-aankoopprogramma (VPP) kunt u de gekoppelde op een apparaat gebaseerde app-licentie voor het apparaat intrekken. Als u een app-licentie intrekt, wordt de desbetreffende VPP-app niet van het apparaat verwijderd. Als u een VPP-app wilt verwijderen, moet u de toewijzingsactie wijzigen in **Verwijderen**. Zie [iOS-apps beheren die zijn aangeschaft via een volume-aankoopprogramma met Microsoft Intune](../apps/vpp-apps-ios.md) voor meer informatie.

#### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type---1332318---"></a>Mobiele apps van Office 365 toewijzen aan iOS- en Android-apparaten met behulp van de ingebouwde app-type<!-- 1332318 -->
Het **ingebouwde** app-type maakt het eenvoudiger voor u om Office 365-apps te maken en toe te wijzen aan door u beheerde iOS- en Android-apparaten. Deze apps zijn onder andere 0365-apps, zoals Word, Excel, PowerPoint en OneDrive. U kunt specifieke apps toewijzen aan het app-type en de configuratie van de app-gegevens bewerken.

#### <a name="including-and-excluding-app-assignment-based-on-groups---1406920---"></a>App-toewijzing opnemen en uitsluiten op basis van groepen<!-- 1406920 -->

Tijdens toewijzing van een app en na het selecteren van een toewijzingstype, kunt u selecteren welke groepen u wilt opnemen en welke u wilt uitsluiten.

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="you-can-assign-an-application-configuration-policy-to-groups-by-including-and-excluding-assignments----1480316---"></a>U kunt een toepassingsconfiguratiebeleid toewijzen aan groepen door toewijzingen op te nemen en uit te sluiten <!-- 1480316 -->

U kunt een toepassingsconfiguratiebeleid toewijzen aan een groep gebruikers en apparaten met behulp van een combinatie van opgenomen en uitgesloten toewijzingen. U kunt toewijzingen kiezen als een aangepaste selectie groepen of als afzonderlijke groep. Een virtuele groep kan **Alle gebruikers**, **Alle apparaten** of **Alle gebruikers + alle apparaten** bevatten.

#### <a name="support-for-windows-10-edition-upgrade-policy-----903672archived-1119689---"></a>Ondersteuning voor het editie-upgradebeleid voor Windows 10  <!-- 903672(archived), 1119689 -->  
U kunt een editie-upgradebeleid voor Windows 10 maken dat Windows 10-apparaten upgradet naar Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education en Windows 10 Professional Education N. Raadpleeg [Editie-upgrades voor Windows 10 configureren](../configuration/edition-upgrade-configure-windows-10.md) voor meer informatie over editie-upgrades voor Windows 10.

#### <a name="conditional-access-policies-for-intune-is-only-available-from-the-azure-portal----1737088-1634311---"></a>Beleid voor voorwaardelijke toegang voor Intune is alleen beschikbaar vanuit Azure Portal <!-- 1737088 1634311 -->

Vanaf deze versie moet u uw beleid voor voorwaardelijke toegang configureren en beheren in het [Azure Portal](https://portal.azure.com) via **Azure Active Directory** > **Voorwaardelijke toegang**. Voor uw gemak hebt u ook toegang tot deze blade vanuit Intune in Azure Portal via **Intune** > **Voorwaardelijke toegang**.

#### <a name="updates-to-compliance-emails--1637547---"></a>Updates voor e-mailberichten over naleving<!--1637547 -->

Wanneer er een e-mailbericht wordt verzonden om een niet-compatibel apparaat te melden, worden daarin gegevens over het niet-compatibele apparaat opgenomen.

### <a name="intune-apps"></a>Intune-apps

#### <a name="new-functionality-for-the-resolve-action-for-android-devices--1583480--"></a>Nieuwe functionaliteit voor de actie 'Oplossen' voor Android-apparaten<!--1583480-->

De bedrijfsportal-app voor Android breidt de actie 'Oplossen' uit voor **Apparaatinstellingen bijwerken** om [problemen met de versleuteling van het apparaat](/intune-user-help/encrypt-your-device-android) op te lossen.

#### <a name="remote-lock-available-in-company-portal-app-for-windows-10--676506--"></a>Externe vergrendeling is beschikbaar in de bedrijfsportal-app voor Windows 10<!--676506-->
Eindgebruikers kunnen nu in de bedrijfsportal-app voor Windows 10 hun apparaten extern vergrendelen. Dit wordt niet weergegeven voor het lokale apparaat dat op dat moment wordt gebruikt.

#### <a name="easier-resolution-of-compliance-issues-for-the-company-portal-app-for-windows-10--676546--"></a>Eenvoudigere oplossing van problemen met naleving voor de bedrijfsportal-app voor Windows 10<!--676546-->
Eindgebruikers met Windows-apparaten kunnen tikken op de reden van niet-naleving in de bedrijfsportal-app. Indien mogelijk worden ze hiermee rechtstreeks naar de juiste locatie geleid in de instellingen-app om het probleem te verhelpen.

<!-- ########################## -->
## <a name="december-2017"></a>december 2017

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="new-automatic-redeployment-setting---1469168---"></a>Nieuwe instelling voor automatisch opnieuw implementeren<!-- 1469168 -->
De instelling **Automatisch opnieuw implementeren** maakt het mogelijk dat gebruikers met beheerdersrechten alle gebruikersgegevens en -instellingen verwijderen met **CTRL + Win + R** op het vergrendelingsscherm van het apparaat. Het apparaat wordt automatisch opnieuw geconfigureerd en opnieuw ingeschreven bij het beheer. U vindt deze instelling onder Windows 10 > Apparaatbeperkingen > Algemeen > Automatisch opnieuw installeren. Zie [Intune-apparaatbeperkingsinstellingen voor Windows 10](../configuration/device-restrictions-windows-10.md#general) voor meer informatie.

#### <a name="support-for-additional-source-editions-in-the-windows-10-edition-upgrade-policy----903672--1119689---"></a>Ondersteuning voor extra bronedities in het beleid voor editie-upgrades voor Windows 10 <!-- 903672,  1119689 -->
U kunt nu het beleid voor editie-upgrades voor Windows 10 gebruiken om een upgrade uit te voeren voor extra edities van Windows 10 (Windows 10 Pro, Windows 10 Pro Education, Windows 10 Cloud, enzovoort). Vóór deze release waren de ondersteunde editie-upgradepaden beperkter. Zie [Editie-upgrades voor Windows 10 configureren](../configuration/edition-upgrade-configure-windows-10.md) voor meer informatie.

#### <a name="new-windows-defender-security-center-wdsc-device-configuration-profile-settings---1335507---"></a>Nieuwe profielinstellingen voor apparaatconfiguratie voor Windows Defender Security Center (WDSC)<!-- 1335507 -->

Intune voegt een nieuwe sectie toe in de profielinstellingen voor apparaatconfiguratie onder de eindpuntbeveiliging genaamd **Windows Defender Security Center**. IT-beheerders kunnen configureren tot welke onderdelen van de Windows Defender Security Center-app eindgebruikers toegang hebben. Als een IT-beheerder een onderdeel verbergt in de Windows Defender Security Center-app, worden alle meldingen die betrekking hebben op het verborgen onderdeel, niet weergeven op het apparaat van de gebruiker.

De volgende onderdelen kunnen worden verborgen in de profielinstellingen voor apparaatconfiguratie van Windows Defender Security Center:
- Virus- en bedreigingsbeveiliging
- Prestaties en status van apparaat
- Firewall- en netwerkbeveiliging
- App- en browserbeheer
- Gezinsopties

IT-beheerders kunnen ook aanpassen welke meldingen gebruikers ontvangen. U kunt bijvoorbeeld configureren of de gebruikers alle meldingen ontvangen die worden gegenereerd door zichtbare onderdelen in het WDSC of alleen kritieke meldingen. Niet-kritieke meldingen zijn bijvoorbeeld periodieke samenvattingen van Windows Defender Antivirus-activiteiten en meldingen wanneer scans zijn voltooid. Alle andere meldingen worden beschouwd als kritiek. Daarnaast kunt u ook de inhoud van meldingen zelf aanpassen. U kunt bijvoorbeeld contactgegevens van de IT-afdeling toevoegen aan meldingen die worden weergegeven op apparaten van gebruikers.

#### <a name="multiple-connector-support-for-scep-and-pfx-certificate-handling---1361755---"></a>Ondersteuning voor meerdere connectoren voor het verwerken van SCEP- en PFX-certificaten<!-- 1361755 -->

Klanten die de on-premises NDES-connector gebruiken om certificaten aan apparaten te leveren, kunnen nu meerdere connectoren in één tenant configureren.

Deze nieuwe mogelijkheid biedt ondersteuning voor het volgende scenario:

- **Hoge beschikbaarheid**

Elke NDES-connector haalt certificaataanvragen uit Intune op.  Als één NDES-connector offline gaat, kan de andere connector aanvragen blijven verwerken.

#### <a name="customer-subject-name-can-use-aad_device_id-variable----1468599---"></a>Aangepaste onderwerpnaam kan de AAD_DEVICE_ID-variabele gebruiken <!-- 1468599 -->

Wanneer u een SCEP-certificaatprofiel in Intune maakt, kunt u nu de AAD_DEVICE_ID-variabele gebruiken bij het samenstellen van de aangepaste onderwerpnaam.   Wanneer het certificaat wordt aangevraagd via dit SCEP-profiel, wordt de variabele vervangen door de AAD-apparaat-id van het apparaat dat de certificaataanvraag doet.


### <a name="device-management"></a>Apparaatbeheer

#### <a name="manage-jamf-enrolled-macos-devices-with-intunes-device-compliance-engine---1592747---"></a>Via Jamf ingeschreven macOS-apparaten beheren met de Intune-engine voor apparaatnaleving<!-- 1592747 -->
U kunt nu Jamf gebruiken om statusinformatie over macOS-apparaten naar Intune te sturen, waarna het apparaat wordt geëvalueerd op naleving van het beleid dat is gedefinieerd in de Intune-console. Op basis van de nalevingsstatus van het apparaat en van andere omstandigheden (zoals locatie, gebruikersrisico en dergelijke) dwingt voorwaardelijke toegang naleving af voor macOS-apparaten die toegang hebben tot toepassingen in de cloud en on-premises die zijn verbonden met Azure AD, met inbegrip van Office 365. Meer informatie over [integratie met Jamf instellen](../protect/conditional-access-integrate-jamf.md) en [afdwingen van naleving voor door Jamf beheerde apparaten](../protect/conditional-access-assign-jamf.md).

#### <a name="new-ios-device-action-----1424701---"></a>Nieuwe actie voor iOS-apparaten  <!-- 1424701 -->

U kunt nu door iOS 10.3 gecontroleerde apparaten afsluiten. Deze actie sluit het apparaat direct af zonder waarschuwing voor de eindgebruiker. U vindt de actie **Afsluiten (alleen gecontroleerd)** in de apparaateigenschappen wanneer u een apparaat selecteert in de werkbelasting **Apparaat**.

#### <a name="disallow-datetime-changes-to-samsung-knox-devices---1468103---"></a>Geen datum-/tijdwijzigingen voor Samsung Knox-apparaten toestaan<!-- 1468103 -->

We hebben een nieuwe functie toegevoegd waarmee u datum- en tijdwijzigingen op Samsung Knox-apparaten kunt blokkeren. U kunt dit vinden in **Apparaatconfiguratieprofielen** > **Apparaatbeperkingen (Android)**  > **Algemeen**.

#### <a name="surface-hub-resource-account-supported---1566442----"></a>Resource-account voor Surface Hub ondersteund<!-- 1566442  -->

Er is een nieuwe apparaatactie toegevoegd, zodat beheerders het resource-account dat is gekoppeld aan een Surface Hub, kunnen definiëren en bijwerken.

Het resource-account wordt door een Surface Hub gebruikt voor verificatie bij Exchange/Skype, zodat kan worden deelgenomen aan een vergadering. U kunt een uniek resource-account maken, zodat de Surface Hub als vergaderruimte wordt weergegeven in de vergadering. Het resource-account kan bijvoorbeeld worden weergegeven als *Vergaderzaal B41/6233*. Het resource-account (ook wel het apparaataccount genoemd) voor de Surface Hub moet meestal worden geconfigureerd voor de locatie van de vergaderruimte en wanneer andere parameters van het resource-account moeten worden gewijzigd.

Wanneer beheerders het resource-account op een apparaat willen bijwerken, moeten ze de huidige referenties voor Active Directory/Azure Active Directory voor het apparaat opgeven. Als wisseling van het wachtwoord is ingeschakeld voor het apparaat, moeten beheerders het wachtwoord zoeken in Azure Active Directory.

> [!NOTE]
> Alle velden in een bundel worden verzonden en overschrijven alle velden die eerder zijn geconfigureerd. Lege velden overschrijven ook bestaande velden.

Beheerders kunnen de volgende instellingen configureren:

- **Resource-account**
  - **Active Directory-gebruiker**

    Domeinnaam\gebruikersnaam of UPN (Principle-naam van gebruiker):user@domainname.com

  - **Wachtwoord**

- **Optionele parameters voor het resource-account** (moeten worden ingesteld met het opgegeven resource-account)

  - **Periode voor de wisseling van het wachtwoord**

    Zorgt ervoor dat het accountwachtwoord uit veiligheidsoverwegingen elke week automatisch wordt bijgewerkt door de Surface Hub. Als u parameters wilt configureren nadat dit is ingeschakeld, moet eerst het wachtwoord voor het account in Azure Active Directory opnieuw worden ingesteld.

  - **SIP-adres (Session Initiation Protocol)**

    Wordt alleen gebruikt als automatische detectie mislukt.

  - **E-mail**

    Het e-mailadres van het apparaat-/resource-account.

  - **Exchange-server**

    Alleen vereist wanneer automatische detectie mislukt.

  - **Agendasynchronisatie**

    Hiermee geeft u op of agendasynchronisatie en andere Exchange Server-services zijn ingeschakeld. Bijvoorbeeld: synchronisatie van vergaderingen.

#### <a name="install-office-apps-on-macos-devices---1494311---"></a>Office-apps installeren op macOS-apparaten<!-- 1494311 -->
U kunt nu Office-apps installeren op macOS-apparaten. Met dit nieuwe app-type kunt u Word, Excel, PowerPoint, Outlook en OneNote installeren. Deze apps worden ook geleverd met Microsoft AutoUpdate (MAU) om te zorgen dat uw apps veilig en up-to-date blijven.

### <a name="app-management"></a>Appbeheer

#### <a name="delete-an-ios--volume-purchasing-program-token---820879---"></a>Een token van het iOS-volume-aanschafprogramma verwijderen<!-- 820879 -->
U kunt het token van het iOS-volume-aanschafprogramma (VPP) verwijderen via de console. Dit kan nodig zijn als er dubbele exemplaren van een VPP-token zijn.

### <a name="intune-apps"></a>Intune-apps


### <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer

#### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data---1667026---"></a>De nieuwe entiteitverzameling Huidige gebruiker is beperkt tot gegevens van actieve gebruikers<!-- 1667026 -->

De entiteitverzameling **Gebruiker** bevat alle Azure Active Directory-gebruikers (Azure AD) met toegewezen licenties in uw onderneming. Een gebruiker kan bijvoorbeeld worden toegevoegd aan Intune en vervolgens ergens gedurende de afgelopen maand zijn verwijderd. Ook al is deze gebruiker niet aanwezig op het moment dat het rapport wordt gegenereerd, toch zijn de gebruiker en de status aanwezig in de gegevens. U kunt een rapport maken dat de duur van de historische aanwezigheid van de gebruiker in uw gegevens weergeeft.

Daarentegen bevat de nieuwe entiteitverzameling **Huidige gebruiker** alleen gebruikers die niet zijn verwijderd. De entiteitverzameling **Huidige gebruiker** bevat alleen gebruikers die momenteel actief zijn. Zie [Naslaginformatie voor huidige gebruikersentiteit](../developer/reports-ref-data-model.md) voor informatie over de entiteitverzameling **Huidige gebruiker**.

### <a name="updated-graph-apis---1736360---"></a>Bijgewerkte Graph API's<!-- 1736360 -->

We hebben in deze release enkele Graph API's voor Intune bijgewerkt die nog in de bètafase zijn. Bekijk de maandelijkse [Graph API changelog](https://developer.microsoft.com/graph/docs/concepts/changelog) voor meer informatie.

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="intune-supports-windows-information-protection-wip-denied-apps---1479103---"></a>Intune biedt ondersteuning voor door Windows Information Protection (WIP) geweigerde apps<!-- 1479103 -->
U kunt geweigerde apps opgeven in Intune. Als een app wordt geweigerd, heeft deze geen toegang tot zakelijke gegevens. Dit is dus eigenlijk het tegenovergestelde van de lijst met toegestane apps. Zie [Aanbevolen lijst voor weigeren voor Windows Information Protection](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp?f=255&MSPPError=-2147217396#recommended-deny-list-for-windows-information-protection) voor meer informatie.

<!-- ########################## -->
## <a name="november-2017"></a>November 2017

### <a name="troubleshoot-enrollment-issues----746324---"></a>Inschrijvingsproblemen oplossen <!-- 746324 -->

De werkruimte **Problemen oplossen** toont problemen met gebruikersinschrijving. Details over het probleem en voorgestelde herstelstappen kunnen beheerders en helpdeskmedewerkers helpen problemen op te lossen. Bepaalde inschrijvingsproblemen worden niet vastgelegd en voor sommige fouten zijn er misschien geen herstelvoorstellen.

### <a name="group-assigned-enrollment-restrictions---747598---"></a>Beperkingen aan groepen toegewezen inschrijving<!-- 747598 -->

Als Intune-beheerder kunt u de [aangepaste inschrijvingsbeperkingen Apparaattype en Apparaatlimiet maken voor gebruikersgroepen](../enrollment/enrollment-restrictions-set.md).

Met de Intune Azure Portal kunt u maximaal 25 exemplaren van elk beperkingstype maken die vervolgens kunnen worden toegewezen aan gebruikersgroepen. Aan groepen toegewezen beperkingen overschrijven de standaardbeperkingen.

Alle exemplaren van een beperkingstype worden bijgehouden in een strikt geordende lijst. Deze volgorde bepaalt een prioriteitswaarde voor conflictoplossing. Een gebruiker die getroffen is door meer dan één beperkingsexemplaar wordt alleen beperkt door het exemplaar met de hoogste prioriteitswaarde. U kunt de prioriteit van een bepaald exemplaar wijzigen door dit naar een andere positie in de lijst te slepen.

Deze functionaliteit wordt vrijgegeven met de migratie van Android for Work-instellingen van het menu Android for Work-inschrijving naar het menu Inschrijvingsbeperkingen. Aangezien deze migratie enkele dagen kan duren, kan uw account worden bijgewerkt ten aanzien van andere onderdelen van de release van november voordat u ziet dat groepstoewijzing wordt ingeschakeld voor Inschrijvingsbeperkingen.

### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors---1528104---"></a>Ondersteuning voor meerdere connectors voor de Network Device Enrollment-service (NDES)<!-- 1528104 -->

Met de NDES kunnen mobiele apparaten die zonder domeinreferenties worden uitgevoerd certificaten verkrijgen op basis van het Simple Certificate Enrollment Protocol (SCEP).
Dankzij deze update worden meerdere NDES-connectors ondersteund.

### <a name="manage-android-for-work-devices-independently-from-android-devices---1490731-eeready--"></a>Android for Work-apparaten onafhankelijk van de Android-apparaten beheren<!-- 1490731 EEready-->

Intune ondersteunt het inschrijvingsbeheer voor Android for Work-apparaten onafhankelijk van het Android-platform. Deze instellingen worden beheerd onder **Apparaatinschrijving** > **Inschrijvingsbeperkingen** > **Apparaattypebeperkingen**. (Ze bevonden zich eerder onder **Apparaatinschrijving** > **Android for Work-inschrijving** > **Android for Work-inschrijvingsinstellingen**.)

Standaard zijn instellingen voor uw Android for Work-apparaten gelijk aan de instellingen voor uw Android-apparaten. Wanneer u echter uw Android for Work-instellingen wijzigt, is dat niet meer het geval.

Als u een persoonlijke Android for Work-inschrijving blokkeert, kunnen alleen zakelijke Android-apparaten worden ingeschreven als Android for Work.

Bedenk de volgende punten wanneer u met de nieuwe instellingen werkt:

#### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Als u nog nooit een Android for Work-inschrijving hebt toegevoegd

Het nieuwe Android for Work-platform wordt geblokkeerd in de standaard apparaattypebeperkingen. Wanneer u de functie toevoegt, kunt u de Android for Work-inschrijving van apparaten toestaan. Hiervoor wijzigt u de standaardinstelling of maakt u een nieuwe apparaattypebeperking ter vervanging van de standaard apparaattypebeperking.

#### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Als u de Android for Work-inschrijving hebt toegevoegd

Als u dit al eerder hebt gedaan, is uw situatie afhankelijk van de instelling die u hebt gekozen:

| Instelling | De status van Android for Work bij een standaard apparaattypebeperking | Opmerkingen |
| --- | --- | --- |
| **Alle apparaten beheren als Android** | Geblokkeerd | U mag geen Android-apparaten bij Android for Work hebben ingeschreven. |
| **Ondersteunde apparaten beheren als Android for Work** | Toegestaan | Alle Android-apparaten die ondersteuning bieden voor Android for Work moeten zijn ingeschreven bij Android for Work. |
| **Alleen ondersteunde apparaten voor de gebruikers in deze groepen beheren als Android for Work** | Geblokkeerd | Er is een afzonderlijk beleid voor apparaattypebeperkingen gemaakt om de standaardinstelling te overschrijven. Dit beleid bepaalt de groepen die u eerder hebt geselecteerd om Android for Work-inschrijving toe te staan. Gebruikers binnen de geselecteerde groepen mogen hun Android for Work-apparaten blijven inschrijven. Alle andere gebruikers worden uitgesloten van inschrijving bij Android for Work. |

In alle gevallen blijft uw beoogde regel behouden. Er is geen actie vereist van uw kant om de globale of groepsgewijze toestemming voor Android for Work in uw omgeving te handhaven.

### <a name="google-play-protect-support-on-android---908720---"></a>Ondersteuning van Google Play Protect op Android<!-- 908720 -->

Google introduceert tegelijkertijd met Android Oreo een reeks beveiligingsfuncties met de naam Google Play Protect waarmee gebruikers en organisaties beveiligde apps en beveiligde Android-installatiekopieën kunnen uitvoeren. Intune ondersteunt de functies van Google Play Protect, inclusief SafetyNet voor externe verklaringen. Beheerders kunnen eisen voor een nalevingsbeleid instellen die vereisen dat Google Play Protect wordt geconfigureerd en in orde is.
De instelling **SafetyNet-apparaatverklaring** vereist dat het apparaat verbinding maakt met een service van Google om te controleren of het apparaat in orde is en er niet mee is geknoeid. Beheerders kunnen tevens een configuratieprofielinstelling voor Android for Work instellen om te vereisen dat geïnstalleerde apps worden geverifieerd met behulp van Google Play-services. Als een apparaat niet aan de eisen van Google Play Protect voldoet, kan voorwaardelijke toegang de toegang van gebruikers tot bedrijfsbronnen blokkeren.

- Meer informatie over [het maken van een nalevingsbeleid voor apparaten om Google Play Protect in te schakelen](../protect/compliance-policy-create-android.md).

### <a name="text-protocol-allowed-from-managed-apps---1414050----"></a>Tekstprotocol toegestaan vanuit beheerde Apps<!-- 1414050  -->

Met apps die worden beheerd door de Intune App SDK kunnen SMS-berichten worden verzonden.


### <a name="app-install-report-updated-to-include-install-pending-status---1249446---"></a>Het statusrapport van de app-installatie wordt bijgewerkt met de status Installatie in behandeling<!-- 1249446 -->  

Het **Statusrapport van de app-installatie**, dat toegankelijk is voor elke app via de lijst **App** in de workload **Client-apps**, bevat nu **Installatie in behandeling** voor gebruikers en apparaten.

### <a name="ios-11-app-inventory-api-for-mobile-threat-detection---1391759---"></a>API iOS 11-app-inventaris voor mobiele detectie van dreigingen (MTD)<!-- 1391759 -->

Intune verzamelt informatie over de app-inventaris van apparaten in zowel privé- als bedrijfseigendom en maakt deze informatie beschikbaar voor MTD-providers om op te halen, zoals Lookout for Work. U kunt de app-inventaris verzamelen van gebruikers van iOS 11+-apparaten.

**App-inventaris**  
Inventarissen van iOS 11 +-apparaten in zowel bedrijfs- en privé-eigendom worden verzonden naar uw MTD-serviceprovider. Gegevens in de app-inventarisatie bestaan onder andere uit:

- App-id
- App-versie
- Verkorte App-versie
- App-naam
- Grootte van de App-bundel
- Dynamische grootte van de App
- App is wel of niet gevalideerd
- App is wel of niet beheerd

### <a name="migrate-hybrid-mdm-users-and-devices-to-intune-standalone---1463747-wnready---"></a>Hybride MDM-gebruikers en -apparaten migreren naar de zelfstandige Intune-versie<!-- 1463747 wnready -->
Er zijn nu nieuwe processen en hulpprogramma's beschikbaar om in Azure Portal gebruikers en hun apparaten van hybride MDM naar Intune te verplaatsen, zodat u het volgende kunt doen:
- In Azure Portal beleidsregels en profielen van de Configuration Manager-console naar Intune kopiëren
- In Azure Portal een subset gebruikers naar Intune verplaatsen, terwijl de rest in hybride MDM blijft
- In Azure Portal apparaten naar Intune migreren zonder dat u ze opnieuw hoeft te registreren

### <a name="on-premises-exchange-connector-high-availability-support----676614---"></a>Hoge beschikbaarheid van on-premises Exchange Connector <!-- 676614 -->
Nadat de Exchange-connector een verbinding met Exchange heeft gemaakt met behulp van de opgegeven Client Access Server (CAS), heeft de connector nu de mogelijkheid om andere CAS-servers te ontdekken. Als de primaire CAS niet beschikbaar is, zoekt de connector naar een andere CAS (indien beschikbaar) totdat de primaire CAS beschikbaar komt. Zie [Hoge beschikbaarheid van on-premises Exchange Connector](../protect/exchange-connector-install.md#on-premises-intune-exchange-connector-high-availability-support) voor meer informatie.

### <a name="remotely-restart-ios-device-supervised-only---1424595---"></a>iOS-apparaat op afstand opnieuw opstarten (alleen onder supervisie)<!-- 1424595 -->

U kunt een iOS 10.3 +-apparaat onder supervisie activeren om via een apparaatactie opnieuw op te starten. Zie voor meer informatie over het gebruik van de actie voor het opnieuw opstarten van het apparaat [Apparaten op afstand opnieuw opstarten met Intune](../remote-actions/device-restart.md).

> [!Note]
> Deze opdracht vereist toegangsrechten tot apparaten onder supervisie en **Apparaatvergrendeling**. Het apparaat wordt onmiddellijk opnieuw opgestart. Met een toegangscode vergrendelde iOS-apparaten wordt niet opnieuw verbonden met een Wi-Fi-netwerk na opnieuw te zijn opgestart; na opnieuw te zijn opgestart kunnen deze mogelijk niet communiceren met de server.

### <a name="single-sign-on-support-for-ios---1333645---"></a>Ondersteuning voor Eenmalige aanmelding voor iOS<!-- 1333645 -->  

U kunt Eenmalige aanmelding voor iOS-gebruikers gebruiken. De iOS-apps die zijn gecodeerd om naar de gebruikersreferenties te zoeken in de Eenmalige aanmelding-payload zijn functioneel voor de update van de payloadconfiguratie. U kunt ook de UPN en de Intune-apparaat-id gebruiken om de Principal-naam en de Realm te configureren. Zie [Intune configureren voor eenmalige aanmelding vanaf iOS-apparaten](../configuration/ios-device-features-settings.md#single-sign-on) voor meer informatie.

### <a name="add-find-my-iphone-for-personal-devices--1427287--"></a>Mijn iPhone vinden toevoegen voor privéapparaten<!--1427287-->
U kunt nu bekijken of bij iOS-apparaten Activeringsslot is ingeschakeld. Deze functie was eerder te vinden in de klassieke portal in Intune.

### <a name="remotely-lock-managed-macos-device-with-intune---1437691---"></a>Beheerde macOS-apparaten op afstand vergrendelen met Intune<!-- 1437691 -->

U kunt een verloren Mac OS-apparaat vergrendelen en een 6-cijferige pincode voor wachtwoordherstel instellen. Als het apparaat is vergrendeld, toont de blade **Apparaatoverzicht** de pincode totdat een andere apparaatactie wordt verzonden.

Zie voor meer informatie [Beheerde apparaten op afstand vergrendelen met Intune](../remote-actions/device-remote-lock.md).

### <a name="new-scep-profile-details-supported---1559808---"></a>Nieuwe SCEP-profielgegevens ondersteund<!-- 1559808 -->

Beheerders kunnen aanvullende instellingen configureren bij het maken van een SCEP-profiel op Windows-, iOS-, Mac OS- en Android-platformen.  Beheerders kunnen het IMEI-nummer, het serienummer of de algemene naam met inbegrip van e-mail in de indeling van de onderwerpnaam instellen.

<!-- #### Update to what device details your company may see -1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources. -->

### <a name="retain-data-during-a-factory-reset---1588489---"></a>Gegevens behouden tijdens fabrieksinstellingen terugzetten <!--1588489 -->
Wanneer Windows 10 versie 1709 en later naar de fabrieksinstellingen wordt hersteld, is een nieuwe functie beschikbaar. Beheerders kunnen opgeven of apparaatinschrijving en andere ingerichte gegevens worden bewaard op een apparaat via fabrieksinstellingen terugzetten.

De volgende gegevens wordt behouden via fabrieksinstellingen terugzetten:
- Gebruikersaccounts die zijn gekoppeld aan het apparaat
- Status van de machine (lid van domein, lid van Azure Active Directory)
- MDM-inschrijving
- Door OEM geïnstalleerde apps (Store- en Win32-apps)
- Gebruikersprofiel
- Gebruikersgegevens buiten het gebruikersprofiel
- Autologon gebruiker

De volgende gegevens blijven niet behouden:
- Gebruikersbestanden
- Door de gebruiker geïnstalleerde apps (Store- en Win32-apps)
- Niet-standaard apparaatinstellingen


### <a name="window-10-update-ring-assignments-are-displayed---1621837---"></a>Er worden toewijzingen voor de Windows 10-updatering weergegeven<!-- 1621837 -->
Wanneer u bezig bent met de **probleemoplossing** voor de door u weergegeven gebruiker, kunt u eventuele toewijzingen voor de Windows 10-updatering zien.  

### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings----1455974----"></a>Frequentie-instellingen van rapporten van Windows Defender Advanced Threat Protection <!-- 1455974  -->
Met de service Windows Defender Advanced Threat Protection (WDATP) kunnen beheerders de rapportagefrequentie voor beheerde apparaten beheren. Met de nieuwe optie **Frequentie van telemetrierapporten versnellen** verzamelt vaker WDATP gegevens en beoordeelt vaker risico's. De standaardwaarde voor rapportage zorgt voor optimale snelheid en prestaties. Het verhogen van de rapportagefrequentie kan waardevol zijn voor apparaten met een hoog risico. Deze instelling kunt u vinden in het **Windows Defender ATP**-profiel in **Apparaatconfiguraties**.

### <a name="audit-updates---1412961---"></a>Updates controleren<!-- 1412961 -->  
Controles van Intune biedt een record van de wijzigingsbewerkingen ten aanzien van Intune.  Alle taakbewerkingen voor maken, bijwerken, verwijderen en externe taakbewerkingen worden vastgelegd en een jaar bewaard.  De Azure Portal voorziet in een weergave van de controlegegevens van laatste 30 dagen in elke workload, welke gefilterd kan worden.  Met de bijbehorende Graph API kunt u de controlegegevens ophalen die het afgelopen jaar zijn bewaard.

Controles zijn te vinden onder de groep **CONTROLE**. Er is een menu-item **Controlelogboeken** voor elke workload.

### <a name="company-portal-app-for-macos-is-available--1541700--"></a>De bedrijfsportal-app voor macOS is beschikbaar<!--1541700-->
De Intune-bedrijfsportal op macOS is bijgewerkt en geoptimaliseerd, zodat alle informatie en nalevingsmeldingen die uw gebruikers nodig hebben voor alle apparaten die ze hebben ingeschreven, overzichtelijk wordt weergegeven. En als de Intune-bedrijfsportal eenmaal is geïmplementeerd op een apparaat, zorgt Microsoft AutoUpdate voor macOS voor de updates. U kunt de nieuwe Intune-bedrijfsportal voor macOS downloaden door u aan te melden bij de website van de Intune-bedrijfsportal vanaf een macOS-apparaat.

### <a name="microsoft-planner-is-now-part-of-the-mobile-app-management-mam-list-of-approved-apps----1248473---"></a>Microsoft Planner maakt nu deel uit van de MAM-lijst (beheer van mobiele apps) met goedgekeurde apps <!-- 1248473 -->
De app Microsoft Planner voor iOS en Android maakt nu deel uit van de goedgekeurde apps voor Mobile App Management (MAM). De app kan via de blade Intune-app-beveiliging in Azure Portal worden geconfigureerd voor alle tenants.
- Meer informatie over de [MAM-lijst met goedgekeurde apps](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

### <a name="per-app-vpn-requirement-update-frequency-on-ios-devices-----1547061---"></a>Vereiste updatefrequentie voor VPN per app op iOS-apparaten  <!-- 1547061 -->  
Beheerders kunnen nu de vereisten voor VPN per app verwijderen voor apps op iOS-apparaten. Dit wordt toegepast op de betreffende apparaten na de eerstvolgende check-in bij Intune, gewoonlijk binnen 15 minuten.  

### <a name="support-for-system-center-operations-manager-management-pack-for-exchange-connector---885457---"></a>Ondersteuning van management pack van System Center Operations Manager voor Exchange Connector<!-- 885457 -->
Het management pack van System Center Operations Manager voor Exchange Connector is nu beschikbaar om de logboeken van Exchange Connector te parseren. Hiermee kunt u de service op verschillende manieren controleren wanneer u problemen moet oplossen.

### <a name="co-management-for-windows-10-devices----1243445---"></a>Co-beheer voor Windows 10-apparaten <!-- 1243445 -->
Co-management is een oplossing die een brug slaat tussen traditioneel en modern beheer en het biedt een gefaseerde benadering om de overstap te maken. Co-management is in feite een oplossing waarbij Windows 10-apparaten gelijktijdig worden beheerd door Configuration Manager en Microsoft Intune en zijn gekoppeld aan Active Directory (AD) en Azure Active Directory (Azure AD).  Deze configuratie geeft u een manier om mettertijd te moderniseren, in een tempo dat geschikt is voor uw organisatie als u niet allemaal tegelijk kunt overstappen.  

### <a name="restrict-windows-enrollment-by-os-version---245498---"></a>Windows-inschrijving beperken door de versie van het besturingssysteem<!-- 245498 -->
Als Intune-beheerder kunt u een minimale en maximale versie opgeven van Windows 10 voor de inschrijving van apparaten. U kunt deze beperkingen instellen op de blade **Platformconfiguraties**.

Intune blijft ondersteuning bieden voor registratie Windows 8.1-pc's en -telefoons. U kunt echter alleen minimale en maximale versies instellen voor Windows 10-versies. Als u de inschrijving van 8.1-apparaten wilt toestaan, laat u de minimale versie leeg.

### <a name="alerts-for-windows-autopilot-unassigned-devices----1631236---"></a>Waarschuwingen voor niet-toegewezen Windows Autopilot-apparaten <!-- 1631236 -->
Er is een nieuwe waarschuwing voor niet-toegewezen Windows AutoPilot-apparaten op de pagina **Microsoft Intune** > **Apparaatinschrijving** > **Overzicht**. Deze waarschuwing geeft aan voor hoeveel apparaten van het AutoPilot-programma geen AutoPilot-implementatieprofielen zijn toegewezen. Aan de hand van de informatie in de waarschuwing kunt u profielen maken en deze toewijzen aan de niet-toegewezen apparaten. Als u op de waarschuwing klikt, verschijnt een volledige lijst met Windows AutoPilot-apparaten en gedetailleerde informatie. Zie [Windows-apparaten inschrijven met het Windows AutoPilot Deployment-programma](../enrollment/enrollment-autopilot.md) voor meer informatie.


### <a name="refresh-button-for-devices-list------1333581---"></a>Knop voor het vernieuwen van de lijst met apparaten   <!-- 1333581 -->
Omdat de lijst met apparaten niet automatisch wordt vernieuwd, kunt u de nieuwe knop gebruiken om de apparaten bij te werken die worden weergegeven in de lijst.

### <a name="support-for-symantec-cloud-certification-authority-ca----1333638---"></a>Ondersteuning voor Symantec Cloud Certification Authority (CA) <!-- 1333638 -->    
Intune ondersteunt nu Symantec Cloud CA, die de Intune Certificate Connector in staat stelt PKCS-certificaten van Symantec Cloud CA vrij te geven voor beheerde Intune-apparaten. Als u de Intune Certificate Connector al gebruikt met Microsoft Certification Authority (CA), kunt u de bestaande configuratie van de Intune Certificate Connector gebruiken om de ondersteuning voor Symantec CA toe te voegen.

### <a name="new-items-added-to-device-inventory----1404455---"></a>Nieuwe items toegevoegd aan de apparaatinventarisatie  <!--1404455 -->
De volgende nieuwe items zijn nu beschikbaar voor de [inventaris van ingeschreven apparaten](../remote-actions/device-inventory.md):

- Mac-adres van Wi-Fi
- Totale opslagruimte
- Totale vrije ruimte
- MEID
- Provider van abonnee

### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Toegang instellen voor apps via minimale Android-beveiligingspatch op het apparaat<!-- 1278463 -->   
Een beheerder kan de minimale Android-beveiligingspatch definiëren die op het apparaat moet zijn geïnstalleerd om toegang te kunnen krijgen tot een beheerde toepassing onder een beheerd account.

> [!Note]  
> Deze functie beperkt alleen beveiligingspatches die door Google zijn vrijgegeven op Android 6.0+ apparaten.

### <a name="app-conditional-launch-support---1193313---"></a>Ondersteuning voor app-voorwaardelijk starten<!-- 1193313 -->
IT-beheerders kunnen nu via de Azure-beheerportal een vereiste instellen om een wachtwoordcode in plaats van een numerieke pincode af te dwingen via Mobile App Management (MAM) wanneer de toepassing start. Als dit is geconfigureerd, moet de gebruiker een wachtwoordcode instellen en gebruiken wanneer daarom wordt gevraagd, alvorens toegang te krijgen tot toepassingen met MAM-functionaliteit. Een wachtwoordcode wordt gedefinieerd als een numerieke pincode met ten minste één speciaal teken of een hoofdletter/kleine letter. Bij deze release van Intune wordt deze functie **alleen op iOS** ingeschakeld. Intune ondersteunt wachtwoordcodes op dezelfde manier als numerieke pincodes: er is een minimumlengte, en tekens en tekenreeksen mogen worden herhaald. Deze functie vereist dat toepassingen (WXP, Outlook, Managed Browser, Yammer) de Intune App SDK integreren met de code voor deze functie om de wachtwoordcode-instellingen af te dwingen in de doeltoepassingen.

### <a name="app-version-number-for-line-of-business-in-device-install-status-report---1233999---"></a>App-versienummer voor line-of-business in rapport Installatiestatus van het apparaat<!-- 1233999 -->
Bij deze release toont het rapport Installatiestatus van het apparaat het app-versienummer voor de line-of-business-apps voor iOS en Android. U kunt deze informatie gebruiken om problemen met uw apps op te lossen of om apparaten te vinden waarop verouderde app-versies worden uitgevoerd.

### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile---951708---"></a>Beheerders kunnen de firewall-instellingen op een apparaat nu configureren met behulp van een apparaatconfiguratieprofiel<!-- 951708 -->   
Beheerders kunnen de firewall inschakelen voor apparaten, en ook verschillende protocollen voor domein-, privé- en openbare netwerken configureren.  Deze firewall-instellingen staan in het profiel 'Endpoint Protection'.

### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization---958257---"></a>Windows Defender Application Guard helpt apparaten te beschermen tegen niet-vertrouwde websites, zoals gedefinieerd door uw organisatie<!-- 958257 -->   
Beheerders kunnen sites als 'vertrouwd' of 'zakelijk' definiëren met behulp van een Windows Information Protection-werkstroom of het nieuwe profiel 'Netwerkgrens' onder apparaatconfiguraties. Sites die niet in een vertrouwde netwerkgrens van een 64-bits Windows 10-apparaat staan, worden in een browser op een virtuele Hyper-V-computer geopend als ze met Microsoft Edge worden bekeken.

Application Guard staat in de apparaatconfiguratieprofielen, in het profiel 'Endpoint Protection'. Beheerders kunnen daar interactie configureren tussen de gevirtualiseerde browser en de hostcomputer, niet-vertrouwde sites en vertrouwde sites, en gegevens opslaan die in de gevirtualiseerde browser worden gegenereerd. Als u Application Guard op een apparaat wilt gebruiken, moet er eerst een netwerkgrens worden geconfigureerd. Het is belangrijk slechts één netwerkgrens te definiëren voor een apparaat.  

### <a name="windows-defender-application-control-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps---1031096---"></a>Windows Defender Application Control op Windows 10 Enterprise biedt een modus om alleen geautoriseerde apps te vertrouwen<!-- 1031096 -->    
Aangezien er elke dag duizenden nieuwe schadelijke bestanden worden gemaakt, biedt malwaredetectie op basis van handtekeningen misschien niet meer voldoende bescherming tegen nieuwe aanvallen. Met Windows Defender Application Control op Windows 10 Enterprise kunt u de apparaatconfiguratie wijzigen van een modus waarin apps worden vertrouwd tenzij ze door een antivirus- of andere beveiligingsoplossing worden geblokkeerd, naar een modus waarin het besturingssysteem alleen apps vertrouwt die door uw onderneming zijn geautoriseerd. In Windows Defender Application Control definieert u welke apps u vertrouwt.

Met Intune kunt u het toepassingsbeheerbeleid configureren in de modus 'Alleen controle' of in de modus 'Afdwingen'. Apps worden niet geblokkeerd wanneer ze in de modus 'Alleen controle' worden uitgevoerd. De modus 'Alleen controle' registreert alle gebeurtenissen in lokale clientlogboeken. U kunt ook configureren of alleen Windows-onderdelen en Microsoft Store-apps mogen worden uitgevoerd of dat aanvullende apps met een goede reputatie, zoals die is gedefinieerd door de Intelligent Security Graph, ook mogen worden uitgevoerd.

### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10---1063615---"></a>Window Defender Exploit Guard is een nieuwe verzameling inbraakpreventiefuncties voor Windows 10<!-- 1063615 -->   
Window Defender Exploit Guard omvat aangepaste regels om de exploiteerbaarheid van toepassingen te reduceren, voorkomt macro- en scriptbedreigingen, blokkeert automatisch netwerkverbindingen naar IP-adressen met een slechte reputatie, en kan gegevens uit ransomware en onbekende bedreigingen beveiligen. Windows Defender Exploit Guard bestaat uit de volgende onderdelen:

- **Attack Surface Reduction** biedt regels waarmee u macro-, script- en e-mailbedreigingen kunt voorkomen.
- **Gecontroleerde maptoegang** blokkeert automatisch de toegang tot inhoud in beveiligde mappen.
- **Netwerkfilter** blokkeert uitgaande verbindingen van een app naar een IP/domein met een slechte reputatie
- **Exploit-beveiliging** biedt geheugen-, controlestroom- en beleidsbeperkingen die kunnen worden gebruikt om een toepassing te beschermen tegen aanvallen.

### <a name="manage-powershell-scripts-in-intune-for-windows-10-devices---790537---"></a>PowerShell-scripts in Intune beheren voor Windows 10-apparaten<!-- 790537 -->

Met de Intune-beheeruitbreiding kunt u PowerShell-scripts uploaden in Intune om deze uit te voeren op Windows 10-apparaten. De uitbreiding is een aanvulling op de Windows 10 MDM-functionaliteit en maakt het eenvoudiger voor u om uw beheer te moderniseren. Zie [PowerShell-scripts in Intune beheren voor Windows 10-apparaten](../apps/intune-management-extension.md) voor meer informatie.

### <a name="new-device-restriction-settings-for-windows-10--------1308850---"></a>Nieuwe apparaatbeperkingsinstellingen voor Windows 10     <!-- 1308850 -->
- Berichten (alleen mobiel) - testen of MMS-berichten uitschakelen
- Wachtwoord - instellingen om FIPS en het gebruik van secundaire Windows Hello-apparaten in te schakelen voor verificatie 
- Weergave - instellingen om GDI-schaalbaarheid in of uit te schakelen voor verouderde apps

### <a name="windows-10-kiosk-mode-device-restrictions---1308872---"></a>Apparaatbeperkingen Windows 10-kioskmodus<!-- 1308872 -->   
U kunt gebruikers van Windows 10-apparaten beperken tot de kioskmodus, zodat ze worden beperkt tot een verzameling vooraf gedefinieerde apps.  Om dit te doen, maakt u een Windows 10-apparaatbeperkingsprofiel en configureert u de kioskinstellingen.

De kioskmodus ondersteunt twee modi: **één app** (waarbij een gebruiker slechts één app mag uitvoeren) en **meerdere apps** (geeft toegang tot een verzameling apps).  U definieert het gebruikersaccount en de apparaatnaam, waarmee de ondersteunde apps worden bepaald.  Wanneer de gebruiker is aangemeld, is hij/zij beperkt tot de gedefinieerde apps.  Zie [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) voor meer informatie. 

De kioskmodus vereist het volgende:

- Intune moet de MDM-instantie zijn.
- De apps moeten al op het doelapparaat zijn geïnstalleerd.
- Het apparaat moet [goed ingericht](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions) zijn.

### <a name="new-device-configuration-profile-for-creating-network-boundaries---1311967---"></a>Nieuw apparaatconfiguratieprofiel voor het maken van netwerkgrenzen<!-- 1311967 -->   
Bij uw andere apparaatconfiguratieprofielen vindt u een nieuw apparaatconfiguratieprofiel genaamd **Netwerkgrens**. Gebruik dit profiel om onlinebronnen te definiëren die u als zakelijk en vertrouwd wilt beschouwen. U moet een netwerkgrens voor een apparaat definiëren *voordat* functies zoals Windows Defender Application Guard en Windows Information Protection op het apparaat kunnen worden gebruikt. Het is belangrijk slechts één netwerkgrens te definiëren voor elk apparaat.

U kunt bedrijfscloudresources, IP-adresbereiken en interne proxyservers definiëren die u als vertrouwd wilt beschouwen. Nadat u de netwerkgrens hebt gedefinieerd, kan deze worden gebruikt door andere functies zoals Windows Defender Application Guard en Windows Information Protection.

### <a name="two-additional-settings-for-windows-defender-antivirus---1338409---"></a>Twee aanvullende instellingen voor Windows Defender Antivirus<!-- 1338409 -->  
**Blokkeringsniveau voor bestanden**

| | |
|---|---|
| Niet geconfigureerd | **Niet geconfigureerd** gebruikt het standaard Windows Defender Antivirus-blokkeringsniveau en biedt sterke detectie zonder het risico te vergroten dat legitieme bestanden worden gedetecteerd. |
| Hoog | **Hoog** past een sterk detectieniveau toe.
| Hoog +  | **Hoog +** biedt het niveau Hoog met aanvullende beveiligingsmaatregelen die de clientprestaties kunnen beïnvloeden.
| Zero tolerance  | **Zero tolerance** blokkeert alle onbekende uitvoerbare bestanden. |

Als u dit op **Hoog** instelt, worden sommige legitieme bestanden misschien gedetecteerd, hoewel dit onwaarschijnlijk is.
Het is raadzaam het Blokkeringsniveau voor bestanden in te stellen op de standaardinstelling **Niet geconfigureerd**.

**Time-outverlenging voor het scannen van bestanden door de cloud**  

| | |
|--|--|
| Aantal seconden (0-50) | Geef op hoelang Windows Defender Antivirus een bestand maximaal moet blokkeren terwijl u op een resultaat van de cloud wacht. De standaardinstelling is 10 seconden: de aanvullende tijd die u hier opgeeft (tot 50 seconden) wordt toegevoegd aan die 10 seconden. In de meeste gevallen duurt de scan veel korter dan de maximuminstelling. Als u de tijd verlengt, kan de cloud verdachte bestanden grondig onderzoeken. Het is raadzaam deze instelling in te schakelen en ten minste 20 aanvullende seconden op te geven. |

### <a name="citrix-vpn-added-for-windows-10-devices---1512457---"></a>Citrix-VPN toegevoegd voor Windows 10-apparaten<!-- 1512457 -->  
U kunt Citrix-VPN configureren voor Windows 10-apparaten van klanten. U kunt de Citrix-VPN kiezen in de lijst *Een verbindingstype selecteren* in de blade **Basis-VPN** wanneer u een VPN voor Windows 10 en hoger configureert.

> [!Note]
> Citrix-configuratie bestond voor iOS en Android.

### <a name="wi-fi-connections-support-pre-shared-keys-on-ios---1550823---"></a>Wi-Fi-verbindingen ondersteunen vooraf gedeelde sleutels voor iOS<!-- 1550823 -->
Klanten kunnen Wi-Fi-profielen configureren voor het gebruik van vooraf gedeelde sleutels (PSK) voor WPA/WPA2 persoonlijke verbindingen op iOS-apparaten. Deze profielen worden gepusht naar het apparaat van de gebruiker als het apparaat is ingeschreven bij Intune.

Wanneer het profiel naar het apparaat is gepusht, is de volgende stap afhankelijk van de profielconfiguratie.  Als automatische verbinding is ingesteld, wordt automatisch verbinding gemaakt zodra het netwerk nodig is.  Als handmatige verbinding is ingesteld, moet de gebruiker de verbinding handmatig activeren.  

### <a name="access-to-managed-app-logs-for-ios---1469920---"></a>Toegang tot de logboeken van de beheerde app voor iOS<!-- 1469920 -->
Eindgebruikers waarvoor de beheerde browser is geïnstalleerd kunnen de beheerstatus van alle gepubliceerde Microsoft-apps bekijken en logbestanden versturen om problemen met hun beheerde iOS-apps op te lossen.

Zie [Toegang tot de logboeken van de beheerde app voor iOS](../apps/app-configuration-managed-browser.md#how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios) voor meer informatie over het inschakelen van de probleemoplossingsmodus in de beheerde browser op een iOS-apparaat.

### <a name="improvements-to-device-setup-workflow-in-the-company-portal-for-ios-in-version-290---1417174---"></a>Verbeteringen in de werkstroom voor apparaatinstellingen in de bedrijfsportal voor iOS in versie 2.9.0<!-- 1417174 -->

De werkstroom voor apparaatinstellingen in de bedrijfsportal-app voor iOS is verbeterd. De taal is gebruiksvriendelijker en waar mogelijk hebben we schermen gecombineerd. De taal is ook specifieker voor uw bedrijf gemaakt door overal in de installatietekst de naam van uw bedrijf te gebruiken. U kunt deze bijgewerkte werkstroom zien op de  [pagina met nieuwe functies in de app](../whats-new-app-ui.md).


### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model---1544273---"></a>De gebruikersentiteit bevat de meest recente gebruikersgegevens in het datawarehouse-gegevensmodel<!-- 1544273 -->
De eerste versie van het gegevensmodel Intune-datawarehouse bevat alleen recente, historische Intune-gegevens. Rapportopstellers kunnen de huidige status van een gebruiker niet vastleggen. In deze update wordt  **Gebruikersentiteit** ingevuld met de meest recente gebruikersgegevens.

<!-- ########################## -->
## <a name="october-2017"></a>Oktober 2017

### <a name="ios-and-android-line-of-business-app-version-number-is-visible---1380712---"></a>Het versienummer van de line-of-business-app voor iOS en Android is zichtbaar<!-- 1380712 -->

In Apps in Intune wordt nu het versienummer voor iOS- en Android-line-of-business-apps weergegeven. Het nummer wordt in de Azure Portal in de app-lijst en in de blade App-overzicht getoond. Eindgebruikers kunnen het app-nummer in de bedrijfsportal-app en in de webportal zien.

__Volledig versienummer__ Het volledige versienummer duidt een specifieke release van de app aan. Het nummer wordt weergegeven als _Versie_(_Build_). Bijvoorbeeld 2.2(2.2.17560800)

Het volledige versienummer bevat twee onderdelen:

- **Versie**  
  Het versienummer is het door mensen leesbare releasenummer van de app. Dit wordt door eindgebruikers gebruikt om de verschillende releases van de app aan te duiden.

- **Buildnummer**  
  Het buildnummer is een intern nummer dat voor de detectie van apps en het beheer van apps via een programma kan worden gebruikt. Het buildnummer verwijst naar een iteratie van de app die refereert aan wijzigingen in de code.

Meer informatie over versienummers en het ontwikkelen van line-of-business-apps in [Aan de slag met Microsoft Intune App SDK](../developer/app-sdk-get-started.md#line-of-business-app-version-numbers).

### <a name="device-and-app-management-integration---677972---"></a>Integratie van apparaat- en appbeheer<!-- 677972 -->   
Nu Mobile Device Management (MDM) en Mobile Application Management (MAM) van Intune beide toegankelijk zijn vanuit de Azure-portal, is Intune begonnen met het integreren van de IT-beheerervaring omtrent app- en apparaatbeheer. Deze wijzigingen zijn bedoeld om uw apparaat- en appbeheer te vereenvoudigen.

Meer informatie over de aangekondigde MDM- en MAM-wijzigingen staat in de [blog van het Intune-ondersteuningsteam](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/).

### <a name="new-enrollment-alerts-for-apple-devices---1471790---"></a>Nieuwe inschrijvingswaarschuwingen voor Apple-apparaten<!-- 1471790 -->
De overzichtspagina voor de inschrijving toont nuttige waarschuwingen voor IT-beheerders met betrekking tot beheer van apparaten van Apple. Waarschuwingen worden weergegeven op de overzichtspagina wanneer het Apple MDM push-certificaat verloopt of al is verlopen, wanneer het token Device Enrollment Program verloopt of al is verlopen en wanneer er zich niet-toegewezen apparaten in het Device Enrollment Program bevinden.

### <a name="support-token-replacement-for-app-configuration-without-device-enrollment---1080364---"></a>Ondersteuning voor token-vervanging voor de configuratie van de app zonder apparaatinschrijving<!-- 1080364 -->

U kunt tokens gebruiken voor dynamische waarden in app-configuraties voor apps op apparaten die niet zijn ingeschreven. Zie voor meer informatie [App-configuratiebeleidsregels toevoegen voor beheerde apps zonder apparaatinschrijving](../apps/app-configuration-policies-managed-app.md).

### <a name="updates-to-the-company-portal-app-for-windows-10--1299474--"></a>Updates in de bedrijfsportal-app voor Windows 10<!--1299474-->
De pagina Instellingen in de bedrijfsportal-app voor Windows 10 is bijgewerkt, zodat de instellingen en de beoogde gebruikersacties consistenter zijn voor alle instellingen. De pagina komt nu ook beter overeen met de indeling van andere Windows-apps. U vindt afbeeldingen voor/na op de [pagina met nieuwe functies in de app](../whats-new-app-ui.md).

### <a name="inform-end-users-what-device-information-can-be-seen-for-windows-10-devices--1337920--"></a>Eindgebruikers informeren welke apparaatgegevens voor Windows 10-apparaten kunnen worden gezien<!--1337920-->
De optie **Eigendomstype** is toegevoegd aan het scherm Apparaatgegevens in de bedrijfsportal-app voor Windows 10. Hierdoor kunnen gebruikers meer over privacy te weten komen vanaf deze pagina in de documenten voor Intune-eindgebruikers. Deze informatie is ook te vinden op het scherm **Info**.

### <a name="feedback-prompts-for-the-company-portal-app-for-android--1165249--"></a>Vragen om feedback over de bedrijfsportal-app voor Android<!--1165249-->
De bedrijfsportal-app voor Android vraagt nu om feedback van eindgebruikers. Deze feedback wordt rechtstreeks naar Microsoft verzonden en biedt eindgebruikers de kans de app te beoordelen in de openbare Google Play Store. Feedback is niet vereist en kan eenvoudig worden gesloten, zodat gebruikers kunnen doorgaan met het gebruik van de app.

<!-- #### Update to what device details an organization can see 1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources.-->

### <a name="helping-your-users-help-themselves-with-the-company-portal-app-for-android---1573324-1573150-1558616-1564878---"></a>Uw gebruikers helpen om zichzelf te redden met de bedrijfsportal-app voor Android<!-- 1573324, 1573150, 1558616, 1564878 -->

De bedrijfsportal-app voor Android voegt aanwijzingen toe, zodat eindgebruikers meer inzicht krijgen en, waar mogelijk, nieuwe gebruikssituaties zelf kunnen oplossen.
- Eindgebruikers worden naar de [Azure Active Directory-portal](https://account.activedirectory.windowsazure.com/r/#/profile) geleid om een apparaat verwijderen als zij het maximum aantal apparaten hebben bereikt dat ze mogen toevoegen.
- Eindgebruikers krijgen een stapsgewijze instructie om hen te helpen [foutberichten bij de activering van Samsung Knox-apparaten op te lossen](https://go.microsoft.com/fwlink/?linkid=859718) of [de energiebesparende modus uit te schakelen](/intune-user-help/power-saving-mode-android). Als geen van deze oplossingen het probleem verhelpt, krijgt u een uitleg over het verzenden van [logboeken naar Microsoft](/intune-user-help/send-logs-to-microsoft-android).

### <a name="new-resolve-action-available-for-android-devices---1583480---"></a>Nieuwe actie 'Oplossen' beschikbaar voor Android-apparaten<!-- 1583480 -->

De bedrijfsportal-app voor Android introduceert een actie 'Oplossen' op de pagina _Apparaatinstellingen bijwerken_. Als de eindgebruiker deze optie selecteert, komt deze rechtstreeks bij de instelling terecht die de oorzaak ervan is dat hun apparaat niet compatibel is. De bedrijfsportal-app voor Android ondersteunt momenteel deze actie ten aanzien van de instellingen [Toegangscode](/intune-user-help/set-your-pin-or-password-android), [USB-foutopsporing](/intune-user-help/you-need-to-turn-off-usb-debugging-android), en [Onbekende bronnen](/intune-user-help/you-need-to-turn-off-unknown-sources-android).

### <a name="device-setup-progress-indicator-in-android-company-portal---1565657---"></a>Voortgangsindicator voor apparaatinstallatie in Android-bedrijfsportal<!-- 1565657 -->
In de bedrijfsportal-app voor Android wordt een voortgangsindicator voor de apparaatinstallatie weergegeven wanneer een gebruiker zijn of haar apparaat inschrijft. De aanduiding toont nieuwe statussen, te beginnen met 'Uw apparaat instellen...', vervolgens 'Het apparaat registreren...', daarna 'Registreren van het apparaat voltooien...' en tot slot 'Instellen van het apparaat voltooien...'.

### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios--1029830--"></a>Ondersteuning voor op certificaten gebaseerde verificatie op de bedrijfsportal voor iOS<!--1029830-->
We hebben ondersteuning voor op certificaten gebaseerde verificatie toegevoegd in de bedrijfsportal-app voor iOS. Gebruikers met deze verificatie voeren hun gebruikersnaam in en tikken vervolgens op de koppeling 'Aanmelden met een certificaat'. Dit wordt al ondersteund in de bedrijfsportal-app voor Android en Windows. Meer informatie staat op de pagina [Aanmelden bij de bedrijfsportal-app](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal).

### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment---1334712---"></a>Apps die met of zonder inschrijving beschikbaar zijn, kunnen nu worden geïnstalleerd zonder dat er om inschrijving wordt gevraagd.<!-- 1334712 -->

Bedrijfs-apps die met of zonder inschrijving beschikbaar zijn gemaakt in de bedrijfsportal-app voor Android kunnen nu worden geïnstalleerd zonder dat er om inschrijving wordt gevraagd.

### <a name="windows-autopilot-deployment-program-support-in-microsoft-intune----747617----"></a>Ondersteuning Windows AutoPilot Deployment-programma in Microsoft Intune <!-- 747617  -->
U kunt nu Microsoft Intune gebruiken met het Windows AutoPilot Deployment-programma om uw gebruikers de mogelijkheid te geven hun bedrijfsapparaten in te richten zonder de tussenkomst van de IT-afdeling. U kunt de Out-of-the-box-ervaring (OOBE) aanpassen en gebruikers begeleiden bij het toevoegen van hun apparaat aan Azure AD en inschrijven bij Intune. Samen nemen Microsoft Intune en Windows AutoPilot de noodzaak weg voor het implementeren, onderhouden en beheren van installatiekopieën van besturingssystemen. Zie [Windows-apparaten inschrijven met het Windows AutoPilot Deployment-programma](../enrollment/enrollment-autopilot.md) voor meer informatie.

### <a name="quickstart-for-device-enrollment----1425655---"></a>Snel starten met apparaatinschrijving <!-- 1425655 --> 
Snel starten is nu beschikbaar in **Apparaatinschrijving** en bevat een tabel met naslagonderwerpen voor het beheren van platformen en configureren van het inschrijvingsproces. Dankzij een korte beschrijving van elk item en koppelingen naar documentatie met stapsgewijze instructies kunt u sneller aan de slag.

### <a name="device-categorization---1427491---"></a>Categorisatie van apparaten<!-- 1427491 -->
In de grafiek met platformen van ingeschreven apparaten op de blade **Apparaten > Overzicht** zijn apparaten geordend op platform, zoals Android, iOS, macOS, Windows en Windows Mobile.  Apparaten met een ander besturingssysteem zijn gegroepeerd in de categorie ‘Overig’.  Dit omvat apparaten van Blackberry, Nokia en andere fabrikanten.  

Als u wilt weten wat dit voor gevolgen heeft voor de apparaten in uw tenant, kiest u **Beheren > Alle apparaten** en gebruikt u vervolgens **Filter** om de inhoud van het veld **Besturingssysteem** te beperken.

### <a name="zimperium---new-mobile-threat-defense-partner-----954681---"></a>Zimperium - nieuwe Mobile Threat Defense-partner  <!-- 954681 -->  
U kunt de toegang van mobiele apparaten tot bedrijfsresources beheren door middel van voorwaardelijke toegang op basis van een risicoanalyse die wordt uitgevoerd door Zimperium, een oplossing voor de beveiliging tegen bedreigingen op mobiele apparaten die met Microsoft Intune is geïntegreerd.

#### <a name="how-integration-with-intune-works"></a>Hoe werkt de integratie met Intune
Risico's worden beoordeeld op basis van telemetrische gegevens die zijn verzameld op apparaten met door Zimperium. U kunt het EMS-beleid voor voorwaardelijke toegang configureren op basis van de Zimperium-risicoanalyse die via het Intune-nalevingsbeleid voor apparaten wordt ingeschakeld. U kunt met dit beleid de toegang tot bedrijfsresources voor niet-compatibele apparaten toestaan of blokkeren op basis van de gedetecteerde bedreigingen.

### <a name="new-settings-for-windows-10-device-restriction-profile-----978575-1308849---"></a>Nieuwe instellingen voor het apparaatbeperkingsprofiel voor Windows 10 <!--- 978575, 1308849, -->  
Er worden nieuwe instellingen toegevoegd aan het apparaatbeperkingsprofiel voor Windows 10 in de categorie Windows Defender SmartScreen.

Zie [Apparaatbeperkingsinstellingen voor Windows 10-apparaten en hoger](../configuration/device-restrictions-windows-10.md) voor meer informatie.

### <a name="remote-support-for-windows-and-windows-mobile-devices-----1070473---"></a>Externe ondersteuning voor Windows- en Windows Mobile-apparaten  <!-- 1070473 -->  
Intune kan de afzonderlijk verkrijgbare [TeamViewer](https://www.teamviewer.com)-software gebruiken zodat u uw gebruikers met Windows- en Windows Mobile-apparaten hulp op afstand kunt bieden.

### <a name="scan-devices-with-windows-defender---1280988--1280990-----"></a>Apparaten scannen met Windows Defender<!-- 1280988  1280990   -->
U kunt nu een **Snelle scan** en **Volledige scan** uitvoeren en **Handtekeningen bijwerken** met Windows Defender Antivirus op beheerde Windows 10-apparaten. Kies op de overzichtsblade van het apparaat de actie die u op het apparaat wilt uitvoeren. U wordt gevraagd om de actie te bevestigen voordat de opdracht naar het apparaat wordt verzonden. 

**Snelle scan**: Een snelle scan scant locaties waar malware zich registreert om te worden gestart, zoals registercodes en bekende opstartmappen in Windows. Een snelle scan duurt gemiddeld vijf minuten. In combinatie met de instelling **Realtimebeveiliging altijd ingeschakeld**, die bestanden scant wanneer ze worden geopend en gesloten en wanneer een gebruiker naar een map gaat, helpt een snelle scan om bescherming te bieden tegen malware die zich mogelijk in het systeem of de kernel bevindt. Gebruikers zien de scanresultaten op hun apparaat wanneer de scan is voltooid. 

**Volledige scan**: Een volledige scan kan handig zijn om vast te stellen of er inactieve componenten zijn waarvoor een diepgaandere opschoning is vereist op apparaten die met een malwarebedreiging te maken hebben gekregen. De scan is handig voor het uitvoeren van scans op aanvraag. Het uitvoeren van volledige scans kan een uur duren. Gebruikers zien de scanresultaten op hun apparaat wanneer de scan is voltooid. 

**Handtekeningen bijwerken**: Met de opdracht Handtekeningen bijwerken worden de malwaredefinities en -handtekeningen in Windows Defender Antivirus bijgewerkt. Dit helpt ervoor te zorgen dat Windows Defender Antivirus malware effectief detecteert. Deze functie is alleen voor Windows 10-apparaten en zolang er een internetverbinding is. 

### <a name="the-enabledisable-button-is-removed-from-the-intune-certificate-authority-page-of-the-intune-azure-portal----1400455---"></a>De knop Inschakelen/Uitschakelen is verwijderd van de pagina Intune-certificaatinstantie van de Intune Azure-portal <!-- 1400455 -->
 We verwijderen een extra stap voor het instellen van de certificaatconnector in Intune. Op dit moment downloadt u de certificaatconnector en schakelt u die in de Intune-console in. Als u de connector echter uitschakelt in de Intune-console, blijft de connector toch certificaten uitgeven.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Met ingang van oktober is de knop Inschakelen/Uitschakelen niet langer aanwezig op de pagina Certificaatinstantie in de Azure-portal. De functionaliteit van de connector blijft hetzelfde. Certificaten worden nog steeds geïmplementeerd naar apparaten die zijn ingeschreven in Intune. U kunt de certificaatconnector nog steeds downloaden en installeren. Als u niet langer certificaten wilt uitgeven, verwijdert u de certificaatconnector in plaats van dat u die uitschakelt.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
Als de certificaatconnector momenteel is uitgeschakeld, moet u die verwijderen.

### <a name="new-settings-for-windows-10-team-device-restriction-profile------1308838---"></a>Nieuwe instellingen voor het beperkingsprofiel voor Windows 10 Team-apparaten  <!--- 1308838 -->
In deze versie hebben we veel nieuwe instellingen toegevoegd aan het beperkingsprofiel voor Windows 10 Team-apparaten, om u te helpen bij het beheren van Surface Hub-apparaten.

Raadpleeg [Intune-apparaatbeperkingen voor Windows 10 Team](../configuration/device-restrictions-windows-10-teams.md) voor meer informatie over dit profiel.

### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time----1333292---"></a>Voorkomen dat gebruikers van Android-apparaten de datum en tijd van hun apparaat wijzigen <!-- 1333292 -->
U kunt een [aangepast beleid voor Android-apparaten](../configuration/custom-settings-android.md) gebruiken om te voorkomen dat gebruikers van Android-apparaten de datum en tijd van het apparaat wijzigen.

Configureer hiervoor een aangepast Android-beleid met de instelling URI ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange Stel dit in op **TRUE** en wijs het vervolgens toe aan de vereiste groepen.

### <a name="bitlocker-device-configuration---1397398---"></a>Configuratie van BitLocker-apparaat<!-- 1397398 -->
**Windows-versleuteling > Basisinstellingen** bevat een nieuwe instelling **Waarschuwing voor een andere schijfversleuteling** waarmee u de [waarschuwing](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#allowwarningforotherdiskencryption) voor versleuteling van een andere schijf die mogelijk op het apparaat van de gebruiker wordt gebruikt kunt uitschakelen.  De waarschuwing vereist dat eindgebruikers toestemming geven voordat ze BitLocker op het apparaat configureren en blokkeert de configuratie van Bitlocker totdat de eindgebruiker bevestigend heeft gereageerd.  De nieuwe instelling schakelt de waarschuwing voor de eindgebruiker uit.


### <a name="volume-purchase-program-for-business-apps-will-now-sync-to-your-intune-tenant---800882---"></a>Het volume-aankoopprogramma voor zakelijke apps synchroniseert nu met uw Intune-tenant<!-- 800882 -->  
Externe ontwikkelaars kunnen privé apps distribueren naar geautoriseerde VPP (volume-aankoopprogramma) for Business-leden die zijn opgegeven in iTunes Connect. Deze VPP for Business-leden kunnen zich aanmelden bij de Volume Purchase Program App Store en hun apps kopen.

Met ingang van deze release worden VPP for Business-apps die door de gebruiker zijn gekocht, gesynchroniseerd met hun Intune-tenant.

### <a name="select-apple-countryregion-store-to-sync-vpp-apps----1332311---"></a>Specifieke Apple Store selecteren om VPP-apps te synchroniseren <!-- 1332311 -->  
U kunt de store in het land of de regio voor het volumeaankoopprogramma (VPP) configureren als u uw VPP-token uploadt. Intune synchroniseert VPP-apps voor alle landinstellingen uit de opgegeven store uit het land of de regio waar de VPP geldt.

> [!NOTE]  
> Op dit moment synchroniseert Intune alleen VPP-apps uit de store van het VPP-land dat of de VPP-regio die overeenkomt met de Intune-landinstelling waarin de Intune-tenant werd gemaakt.


### <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work---1098994---"></a>Kopiëren en plakken tussen werkprofielen en persoonlijke profielen blokkeren in Android for Work<!-- 1098994 -->
Door deze release kunt u het werkprofiel voor Android for Work zo configureren dat kopiëren en plakken tussen zakelijke en persoonlijke apps wordt geblokkeerd. U kunt deze nieuwe instelling vinden in het profiel **Apparaatbeperkingen** voor het **Android for Work**-platform onder **Werkprofielinstellingen**.

### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores---1281692---"></a>iOS-apps maken die zijn beperkt tot specifieke regionale Apple App Stores<!-- 1281692 -->
U kunt de landinstelling voor een land/regio opgeven wanneer u een beheerde app voor de Apple App Store maakt.

> [!Note]  
> Op dit moment kunt u alleen beheerde apps voor de Apple App Store maken die aanwezig zijn in de store voor de VS.

### <a name="update-ios-vpp-user-and-device-licensed-apps----1305564---"></a>Gelicentieerde iOS-apps voor VPP-gebruikers en -apparaten bijwerken <!-- 1305564 -->  
U kunt het VPP-token voor iOS zo configureren dat alle apps die voor dat token zijn gekocht worden bijgewerkt via de Intune-service. Intune detecteert updates voor de VPP-app in de app store en stuurt ze automatisch naar het apparaat als dit incheckt.

Zie [iOS-apps beheren die zijn aangeschaft via een volumeaankoopprogramma met Microsoft Intune] (/intune/vpp-apps-ios) voor meer informatie over het instellen van een VPP-token en inschakelen van automatische updates.


### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model---1187917---"></a>Verzameling voor koppelingsentiteit voor gebruikersapparaten toegevoegd aan het Intune-datawarehouse-gegevensmodel<!-- 1187917 -->
U kunt rapporten en gegevensvisualisaties maken met behulp van de informatie over de gebruikersapparaatkoppelingen; deze koppelen verzamelingen over gebruikers en apparaten. Het gegevensmodel is toegankelijk via het Power BI-bestand (PBIX) dat wordt opgehaald op de datawarehouse-pagina in Intune, via het OData-eindpunt of door een aangepaste client te ontwikkelen.

### <a name="review-policy-compliance-for-windows-10-update-rings---1067886---"></a>Naleving van het beleid voor Windows 10-update-ringen controleren<!-- 1067886 -->
U kunt een beleidsrapport voor uw Windows 10-update-ringen bekijken via Software-updates > Implementatiestatus per update-ring. Het beleidsrapport bevat de implementatiestatus voor de update-ringen die u hebt geconfigureerd. 

### <a name="new-report-that-lists-ios-devices-with-older-ios-versions-----1352223---"></a>Nieuw rapport met iOS-apparaten met oudere iOS-versies  <!-- 1352223 -->
Het rapport **Out-of-date iOS Devices** (Verouderde iOS-apparaten) is beschikbaar in de werkruimte **Software-updates**. Het rapport bevat een lijst met gecontroleerde iOS-apparaten waarop een iOS-updatebeleid van toepassing is geweest en waarvoor updates beschikbaar zijn. Voor elk apparaat kunt u bekijken waarom het apparaat niet automatisch is bijgewerkt. 

### <a name="view-app-protection-policy-assignments-for-troubleshooting----1475003---"></a>Beleidstoewijzingen voor app-beveiliging bekijken om problemen op te lossen<!--  1475003 -->
In deze toekomstige release wordt de optie **App-beveiligingsbeleid** toegevoegd aan de vervolgkeuzelijst **Toewijzingen** op de blad voor probleemoplossing. U kunt nu beleid voor app-beveiliging selecteren om de beleidsregels voor app-beveiliging te zien die aan de geselecteerde gebruikers zijn toegewezen.



### <a name="improvements-to-device-setup-workflow-in-company-portal--1490692--"></a>Verbeteringen in de werkstroom voor apparaatinstellingen in de bedrijfsportal<!--1490692-->
We hebben de werkstroom voor apparaatinstellingen in de bedrijfsportal-app voor Android verbeterd. De taal is gebruiksvriendelijker en specifiek voor uw bedrijf. Daarnaast hebben we waar mogelijk schermen gecombineerd. U kunt deze zien op de pagina [Nieuw in de app-gebruikersinterface](whats-new-app-ui.md#week-of-october-2-2017).

### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices--1484985--"></a>Verbeterde richtlijnen voor het aanvragen van toegang tot contactpersonen op Android-apparaten<!--1484985-->

Voor de bedrijfsportal-app voor Android moet de eindgebruiker vaak de machtiging Contactpersonen accepteren. Als een eindgebruiker deze toegang weigert, ziet deze nu een melding in de app waarin wordt aangegeven dat deze moet worden verleend voor voorwaardelijke toegang. 

### <a name="secure-startup-remediation-for-android--1490712--"></a>Beveiligd opstartherstel voor Android<!--1490712-->

Eindgebruikers met Android-apparaten kunnen tikken op de reden van niet-naleving in de bedrijfsportal-app. Indien mogelijk worden ze hiermee rechtstreeks naar de juiste locatie geleid in de instellingen-app om het probleem te verhelpen. 

### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-oreo--1475932--"></a>Aanvullende pushmeldingen voor eindgebruikers op de bedrijfsportal-app voor Android Oreo<!--1475932-->

Eindgebruikers ontvangen aanvullende meldingen wanneer de bedrijfsportal-app voor Android Oreo achtergrondtaken uitvoert, zoals het ophalen van beleid van de Intune-service. Dit biedt gebruikers meer transparantie over wanneer de bedrijfsportal-app beheertaken uitvoert op hun apparaat. Dit maakt deel uit van de algehele [optimalisatie van de gebruikersinterface van de bedrijfsportal](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) voor de bedrijfsportal-app voor Android Oreo. 

Er zijn nog meer optimalisaties voor nieuwe UI-elementen die in Android Oreo zijn ingeschakeld.  Eindgebruikers ontvangen aanvullende meldingen wanneer de bedrijfsportal achtergrondtaken uitvoert, zoals het ophalen van beleid van de Intune-service.  Dit biedt eindgebruikers meer transparantie over wanneer met de bedrijfsportal-app beheertaken worden uitgevoerd op het apparaat.

### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles---1485783---"></a>Nieuw gedrag voor de bedrijfsportal-app voor Android met werkprofielen<!-- 1485783 -->

Als u een Android voor Work-apparaat met een werkprofiel inschrijft, voert de bedrijfsportal-app in het werkprofiel beheertaken uit op het apparaat. 

De bedrijfsportal-app voor Android wordt niet langer gebruikt, tenzij u een app met MAM-functionaliteit in het persoonlijke profiel gebruikt. Intune zal automatisch de persoonlijke bedrijfsportal-app verbergen om uw ervaring met het werkprofiel te verbeteren nadat de inschrijving van het werkprofiel is geslaagd.

De bedrijfsportal-app voor Android kan op elk gewenst moment in het persoonlijke profiel worden ingeschakeld door naar [Bedrijfsportal te zoeken in de Play Store](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) en op **Inschakelen** te tikken.

### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode--1428681--"></a>Bedrijfsportal voor Windows 8.1 en Windows Phone 8.1 wordt verplaatst naar onderhoudsmodus<!--1428681-->

Vanaf oktober 2017 worden de bedrijfsportal-apps voor Windows 8.1 en Windows Phone 8.1 verplaatst naar de onderhoudsmodus. Dit betekent dat de apps en bestaande scenario’s, zoals inschrijving en naleving, op deze platforms ondersteund blijven worden. De apps blijven beschikbaar om te worden gedownload via bestaande release-kanalen, zoals de Microsoft Store. 

In de onderhoudsmodus worden er alleen kritieke beveiligingsupdates voor deze apps uitgebracht. Er worden geen extra updates of functies voor deze apps uitgebracht. Wanneer u nieuwe functies wilt, raden we u aan om uw apparaten bij te werken naar Windows 10 of Windows 10 Mobile. 


### <a name="block-unsupported-samsung-knox-device-enrollment----1490695---"></a>Registratie van niet-ondersteunde Samsung Knox-apparaten blokkeren <!-- 1490695 -->

Via de bedrijfsportal-app worden alleen ondersteunde Samsung Knox-apparaten geregistreerd. Om Knox-activeringsfouten te voorkomen waardoor de MDM-registratie onmogelijk wordt, wordt de apparaatregistratie alleen uitgevoerd als het apparaat wordt weergegeven in de [lijst met apparaten die is gepubliceerd door Samsung](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Bepaalde modelnummers van Samsung-apparaten bieden ondersteuning voor Knox, andere niet. Controleer de KNOX-compatibiliteit bij de verkoper van uw apparaat voordat u een apparaat koopt en implementeert. U vindt de volledige lijst met gecontroleerde apparaten in de [beleidsinstellingen voor Android en Samsung Knox Standard](supported-devices-browsers.md#intune-supported-web-browsers).

### <a name="end-of-support-for-android-43-and-lower---1171126-1326920---"></a>Einde van ondersteuning voor Android 4.3 en lager<!-- 1171126, 1326920 -->
Beheerde apps en de Intune-bedrijfsportal-app voor Android vereisen Android 4.4 en hoger voor toegang tot bedrijfsresources. Vanaf december worden alle ingeschreven apparaten verplicht buiten gebruik gesteld, waardoor bedrijfsresources niet meer toegankelijk zijn. Als u beleid voor app-beveiliging zonder MDM gebruikt, krijgen apps geen updates meer en neemt de gebruikservaring na verloop van tijd steeds verder af.

### <a name="inform-end-users-what-device-information-can-be-seen-on-enrolled-devices--1165314--"></a>Eindgebruikers informeren over welke apparaatgegevens worden weergegeven op geregistreerde apparaten<!--1165314-->
Aan het scherm voor apparaatgegevens in alle bedrijfsportal-apps wordt de optie **Eigendomstype** toegevoegd. Hierdoor kunnen gebruikers meer over privacy te weten komen rechtstreeks via het artikel [Welke informatie kan uw bedrijf zien?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune) Dit zal binnenkort worden geïmplementeerd in alle bedrijfsportal-apps. Voor iOS hebben we dit aangekondigd in [september](#september-2017).

<!-- ########################## -->
## <a name="september-2017"></a>September 2017

### <a name="intune-supports-ios-11--1428975--"></a>Intune biedt ondersteuning voor iOS 11<!--1428975-->
Intune biedt ondersteuning voor iOS 11. Dit werd eerder aangekondigd in de [blog Intune Support](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/).

### <a name="end-of-support-for-ios-80---1164477---"></a>Einde van ondersteuning voor iOS 8.0<!-- 1164477 -->
Beheerde apps en de Intune-bedrijfsportal-app voor iOS vereisen iOS 9.0 en hoger voor toegang tot bedrijfsresources. Apparaten die niet voor september zijn bijgewerkt, hebben geen toegang meer tot de bedrijfsportal of beheerde apps. 

### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10--1132468--"></a>Actie voor vernieuwen toegevoegd aan de bedrijfsportal-app voor Windows 10<!--1132468-->
Met de bedrijfsportal-app voor Windows 10 kunnen gebruikers de gegevens in de app vernieuwen door deze op te halen voor vernieuwing of door op pc’s op F5 te drukken.

### <a name="inform-end-users-what-device-information-can-be-seen-for-ios--739894--"></a>Eindgebruikers informeren welke apparaatgegevens voor iOS kunnen worden gezien<!--739894-->

Aan het scherm voor apparaatgegevens in de Bedrijfsportal-app voor iOS hebben we de optie **Eigendomstype** toegevoegd. Hierdoor kunnen gebruikers meer over privacy te weten komen vanaf deze pagina in de documenten voor Intune-eindgebruikers. Deze informatie is ook te vinden op het scherm Info.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment---1169910---"></a>Eindgebruikers zonder inschrijving toegang geven tot de Intune-bedrijfsportal-app voor Android<!---1169910--->

Eindgebruikers hoeven hun apparaat binnenkort niet meer in te schrijven om toegang te krijgen tot de Intune-bedrijfsportal-app voor Android. Eindgebruikers in organisaties die gebruikmaken van beleid voor app-beveiliging zien bij het openen van de Intune-bedrijfsportal-app geen instructie meer dat ze hun apparaat moeten registreren. Bovendien kunnen eindgebruikers apps installeren via de bedrijfsportal zonder dat ze hun apparaat hoeven te registreren. 


### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android---1396349---"></a>Gemakkelijker te begrijpen formulering voor de bedrijfsportal-app voor Android<!---1396349--->  

Het inschrijvingsproces voor de bedrijfsportal-app voor Android is vereenvoudigd met nieuwe tekst om het eindgebruikers gemakkelijker te maken om zich in te schrijven. Als u aangepaste inschrijvingsdocumentatie hebt, is het aan te raden om die bij te werken met de nieuwe schermen. Voorbeeldafbeeldingen zijn te vinden op de pagina [UI-updates voor Intune-apps voor eindgebruikers](whats-new-app-ui.md#week-of-september-11-2017).

### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy---677129---"></a>Windows 10-bedrijfsportal-app toegevoegd het toelatingsbeleid van Windows Information Protection<!-- 677129 -->

De Windows 10-bedrijfsportal-app is bijgewerkt met ondersteuning voor Windows Information Protection (WIP). De app kan worden toegevoegd aan het toelatingsbeleid van WIP. Door deze wijziging hoeft de app niet langer te worden toegevoegd aan de lijst **Uitgezonderd**.


<!-- ########################## -->
## <a name="august-2017"></a>Augustus 2017

### <a name="improvements-to-device-overview---1404453---"></a>Verbeteringen aan het apparaatoverzicht<!-- 1404453 -->  
Door verbeteringen aan het apparaatoverzicht worden nu geregistreerde apparaten weergegeven, met uitzondering van apparaten die worden beheerd door Exchange ActiveSync. Exchange ActiveSync-apparaten hebben niet dezelfde beheeropties als geregistreerde apparaten. Als u het aantal geregistreerde apparaten en het aantal geregistreerde apparaten per platform in Intune in de Azure-portal wilt zien, gaat u naar **Apparaten** > **overzicht**.

### <a name="improvements-to-device-inventory-collected-by-intune"></a>Verbeteringen aan de apparaatinventaris verzameld door Intune
<!-- 961134, 1104426, 1281327, 1333543 -->
We hebben in deze versie de volgende verbeteringen aangebracht in de inventarisatiegegevens die zijn verzameld door apparaten die u beheert:
 
- Voor Android-apparaten kunt u nu een kolom aan de apparaatinventaris toevoegen die het meest recente patchniveau voor elk apparaat laat zien. Voeg de kolom **Beveiligingspatchniveau** toe aan uw apparatenlijst om dit te zien.
- Als u de apparaatweergave filtert, kunt u nu apparaten filteren op de datum waarop ze zijn geregistreerd. U kunt bijvoorbeeld alleen die apparaten weergeven die zijn geregistreerd na een datum die u opgeeft.
- We hebben verbeteringen aangebracht aan het filter dat wordt gebruikt door het **Laatste check-in**-item.
- U kunt nu het telefoonnummer van bedrijfsapparaten weergeven in de lijst met apparaten.
Daarnaast kunt u het filterdeelvenster gebruiken om te zoeken naar apparaten op telefoonnummer.

Zie [Inventaris van Intune-apparaten weergeven](../remote-actions/device-inventory.md) voor meer informatie over apparaatinventarisatie.

### <a name="conditional-access-support-for-macos-devices"></a>Ondersteuning voor voorwaardelijke toegang voor macOS-apparaten 
<!-- 720172 -->
U kunt nu een beleid voor voorwaardelijke toegang instellen waardoor Mac-apparaten moeten worden geregistreerd bij Intune en moeten voldoen aan het Intune-nalevingsbeleid voor apparaten. Gebruikers kunnen bijvoorbeeld de Intune-bedrijfsportal-app voor macOS downloaden en hun Mac-apparaten registreren bij Intune. Er wordt vervolgens een evaluatie uitgevoerd in Intune om te bepalen of het Mac-apparaat al dan niet voldoet aan vereisten zoals pincode, versleuteling, versie van het besturingssysteem en systeemintegriteit.

- Meer informatie over [ondersteuning voor voorwaardelijke toegang voor macOS-apparaten](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).

### <a name="company-portal-app-for-macos-is-in-public-preview---1484796---"></a>Bedrijfsportal-app voor macOS is in openbare preview<!---1484796--->
De bedrijfsportal-app voor macOS is nu beschikbaar als onderdeel van de openbare preview voor voorwaardelijke toegang in Enterprise Mobility + Security. Deze release ondersteunt macOS 10.11 en hoger. Download deze vanaf [https://aka.ms/macOScompanyportal](https://aka.ms/macOScompanyportal). 


### <a name="new-device-restriction-settings-for-windows-10"></a>Nieuwe apparaatbeperkingsinstellingen voor Windows 10    
<!--1063965, 1308850  -->
In deze release hebben we nieuwe instellingen toegevoegd voor het [profiel voor apparaatbeperking van Windows 10](/intune/device-restrictions-windows-10), en wel in de volgende categorieën:

- Windows Defender SmartScreen
- App Store

### <a name="updates-to-the-windows-10-endpoint-protection-device-profile-for-bitlocker-settings"></a>Updates voor het apparaatprofiel voor Windows 10 Endpoint Protection voor BitLocker-instellingen
<!--1459533 -->    
We hebben in deze release de volgende verbeteringen aangebracht in de werking van BitLocker-instellingen in een apparaatprofiel voor Windows 10 Endpoint Protection:
 
- Wanneer u onder **BitLocker-instellingen voor OS-stations**, voor de instelling **BitLocker met niet-compatibele TPM-chip**, de optie **Blokkeren** selecteert, zou BitLocker voorheen daadwerkelijk worden toegestaan. We hebben dit nu opgelost door BitLocker te blokkeren wanneer deze optie is geselecteerd.
- U kunt nu onder **BitLocker-instellingen voor OS-stations**, voor de instelling **Agent voor herstel van gegevens op basis van een certificaat**, expliciet de agent voor herstel van gegevens op basis van een certificaat blokkeren. Standaard is de agent echter toegestaan.
- U kunt nu onder **Instellingen voor met BitLocker beveiligde vaste-gegevensstations**, voor de instelling **Agent voor gegevensherstel**, expliciet de agent voor gegevensherstel blokkeren.
Zie [Instellingen voor de beveiliging van eindpunten voor Windows 10 en hoger](../protect/endpoint-protection-windows-10.md) voor meer informatie.


### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users---621669---"></a>Nieuwe aanmeldingsmogelijkheid voor gebruikers van de Android-bedrijfsportal en van het app-beveiligingsbeleid<!-- 621669 -->
Eindgebruikers kunnen nu in apps bladeren, apparaten beheren en de gegevens voor de IT-contactpersoon bekijken met de Android-bedrijfsportal-app zonder dat ze hun Android-apparaten hoeven in te schrijven. Als een eindgebruiker al een app gebruikt die wordt beveiligd door Intune-app-beveiligingsbeleid en de Android-bedrijfsportal opent, wordt hem of haar ook niet meer gevraagd het apparaat in te schrijven.

### <a name="new-setting-in-the-android-company-portal-app-to-toggle-battery-optimization--1405990--"></a>Nieuwe instelling in de Android-bedrijfsportal-app om batterijoptimalisatie in- of uit te schakelen<!--1405990-->
De pagina **Instellingen** in de bedrijfsportal-app voor Android heeft een nieuwe instelling. Hiermee kunnen gebruikers gemakkelijk batterijoptimalisatie uitschakelen voor bedrijfsportal- en Microsoft Authenticator-apps. De naam van de app die in de instelling wordt getoond, is afhankelijk van welke app het werkaccount beheert. Gebruikers wordt aangeraden batterijoptimalisatie uit te schakelen voor betere prestaties van werk-apps die e-mail en gegevens synchroniseren. 

### <a name="multi-identity-support-for-onenote-for-ios--------1234281---"></a>Ondersteuning voor meerdere identiteiten voor OneNote voor iOS     <!-- 1234281 -->
Eindgebruikers kunnen nu verschillende accounts (voor werk en privé) gebruiken met Microsoft OneNote voor iOS. App-beveiligingsbeleid kan worden toegepast op bedrijfsgegevens in notitieblokken voor het werk zonder dat dit van invloed is op hun persoonlijke notitieblokken. Een beleid kan bijvoorbeeld toestaan dat een gebruiker naar informatie zoekt in notitieblokken van het werk, maar voorkomen dat de gebruiker bedrijfsgegevens vanuit het notitieblok kopieert naar een persoonlijk notitieblok.
 
- Meer informatie over de apps die ondersteuning bieden voor [app-beveiliging en meervoudige identiteiten](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) met Intune.

### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices"></a>Nieuwe instellingen om apps toe te staan of te blokkeren voor Samsung Knox Standard-apparaten
<!-- 1305423 822899-->  
In deze release voegen we nieuwe [instellingen voor apparaatbeperkingen](../configuration/device-restrictions-android.md) toe waarmee u de volgende app-lijsten kunt opgeven:
 
- Apps die gebruikers mogen installeren
- Apps die gebruikers niet kunnen uitvoeren
- Apps die voor de gebruiker worden verborgen op het apparaat
 
U kunt de app opgeven met de URL of met de pakketnaam opgeven, of kiezen in de lijst met apps die u beheert.

### <a name="new-azure-ad-app-based-conditional-access-policy-ui-link-from-intune"></a>Koppeling van Intune naar de nieuwe gebruikersinterface voor beleid voor op apps gebaseerde voorwaardelijke toegang van Azure AD
<!-- 1016201 -->
IT-beheerders kunnen nu op apps gebaseerd voorwaardelijk beleid instellen via de nieuwe gebruikersinterface voor beleid voor voorwaardelijke toegang in de Azure AD-werkbelasting. De op apps gebaseerde voorwaardelijke toegang in de sectie Intune-app-beveiliging in de Azure-portal blijft hier voorlopig aanwezig en wordt naast elkaar afgedwongen. Er is in de Intune-werkbelasting ook een handige koppeling naar de nieuwe gebruikersinterface voor beleid voor voorwaardelijke toegang.

- Meer informatie over [op apps gebaseerde voorwaardelijke toegang in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference).

<!-- ########################## -->
## <a name="july-2017"></a>Juli 2017

### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version-----1333256--1245463----"></a>De registratie van Android- en iOS-apparaten beperken op basis van de versie van het besturingssysteem <!--- 1333256,  1245463 --->
Intune biedt nu ondersteuning voor het beperken van registraties van iOS- en Android-apparaten op basis van het versienummer van het besturingssysteem. Bij **Apparaattypebeperking** kan de IT-beheerder een platformconfiguratie instellen met een minimum- en maximumversie van het besturingssysteem, zodat alleen apparaten met versies in dit bereik kunnen worden geregistreerd. De versies van het Android-besturingssysteem moeten worden opgegeven als Major.Minor.Build.Rev, waarbij Minor, Build en Rev optioneel zijn. iOS-versies moeten worden opgegeven als Primair.Secundair.Build, waarbij Minor en Build optioneel zijn. Meer informatie over [beperkingen voor het registreren van apparaten](../enrollment/enrollment-restrictions-set.md).

>[!NOTE]
>Registratie via het inschrijvingsprogramma van Apple of Apple Configurator wordt niet beperkt.

### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment-----1333272--1333275-1245709----"></a>Apparaatregistratie beperken voor persoonlijke Android-, iOS- en macOS-apparaten <!--- 1333272,  1333275, 1245709 --->
Intune kan de registratie van persoonlijke apparaten beperken door IMEI-nummers van bedrijfsapparaten op te nemen in een lijst met toegestane apparaten. De functionaliteit van Intune is nu uitgebreid naar iOS, Android en macOS via het gebruik van de serienummers van apparaten. Door serienummers te uploaden naar Intune, kunt u apparaten vooraf markeren als bedrijfseigendom. Aan de hand van inschrijvingsbeperkingen kunt u de registratie blokkeren van apparaten die privé-eigendom (BYOD) zijn. Op deze manier maakt u beleid waardoor alleen apparaten kunnen worden ingeschreven die bedrijfseigendom zijn. Meer informatie over [beperkingen voor het registreren van apparaten](../enrollment/enrollment-restrictions-set.md).

Als u serienummers wilt importeren in, gaat u naar **Apparaatinschrijving** > **Bedrijfsapparaat-id's** en klikt u op **Toevoegen**. Upload vervolgens een CSV-bestand met deze specificaties (geen header, twee kolommen, één voor de serienummers en één voor gegevens zoals IMEI-nummers). Als u de registratie van apparaten in privé-eigendom wilt beperken, gaat u naar **Apparaatinschrijving** > **Inschrijvingsbeperkingen**. Selecteer **Standaard** onder **Apparaattypebeperking** en selecteer vervolgens **Platformconfiguraties**. Selecteer **Toestaan** of **Blokkeren** voor iOS-, Android- en macOS-apparaten die privé-eigendom zijn.


### <a name="new-device-action-to-force-devices-to-sync-with-intune---711369---"></a>Nieuwe apparaatactie om apparaten geforceerd te synchroniseren met Intune<!-- 711369 -->
In deze versie is een nieuwe apparaatactie toegevoegd die ervoor zorgt dat het geselecteerde apparaat direct wordt ingecheckt bij Intune. Wanneer een apparaat wordt ingecheckt, worden direct eventuele openstaande acties of toegewezen beleidsregels ontvangen die erop zijn toegepast.  Met deze actie kunt u toegewezen beleid meteen controleren en in het geval van problemen direct aanpassen, zonder dat u hoeft te wachten op de volgende geplande check-in.
Zie [Apparaat synchroniseren](../remote-actions/device-sync.md) voor meer informatie

### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update---777100---"></a>Nieuwste software-update geforceerd installeren op iOS-apparaten die onder supervisie staan<!-- 777100 -->
Er is een nieuw beleid beschikbaar in de werkruimte Software-updates waarmee u kunt afdwingen dat automatisch de nieuwste software-update wordt geïnstalleerd op onder supervisie staande iOS-apparaten. Zie [Updatebeleid voor iOS configureren](/intune/software-updates-ios) voor meer informatie

### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner----954651-1172027---"></a>Check Point SandBlast Mobile - nieuwe Mobile Threat Defense-partner <!-- 954651, 1172027 -->
U kunt de toegang van mobiele apparaten tot bedrijfsresources beheren door middel van voorwaardelijke toegang op basis van een risicoanalyse die wordt uitgevoerd door Check Point SandBlast Mobile, een oplossing voor de beveiliging tegen bedreigingen op mobiele apparaten die met Microsoft Intune is geïntegreerd.

#### <a name="how-integration-with-intune-works"></a>Hoe werkt de integratie met Intune?
Risico's worden beoordeeld op basis van telemetriegegevens die zijn verzameld op apparaten met Check Point SandBlast Mobile. U kunt het EMS-beleid voor voorwaardelijke toegang configureren op basis van de risicoanalyse van Check Point SandBlast Mobile die wordt ingeschakeld via het Intune-nalevingsbeleid voor apparaten. U kunt apparaten die niet compatibel zijn op basis van gedetecteerde bedreigingen al dan niet toegang bieden tot bedrijfsresources.


### <a name="deploy-an-app-as-available-in-the-microsoft-store-for-business---748101---"></a>Een app als beschikbaar implementeren in Microsoft Store voor Bedrijven<!-- 748101 -->
Met deze versie kunnen beheerders de Microsoft Store voor Bedrijven nu toewijzen als beschikbaar. Wanneer Microsoft Store voor Bedrijven is ingesteld als beschikbaar, kunnen eindgebruikers de app installeren via de bedrijfsportal-app of -website zonder dat ze worden omgeleid naar de Microsoft Store.

### <a name="ui-updates-to-the-company-portal-website--1313244-part-1--"></a>Updates aan de gebruikersinterface van de bedrijfsportalwebsite<!--1313244 part 1-->
Er zijn een aantal updates aan de gebruikersinterface van de [bedrijfsportalwebsite](https://portal.manage.microsoft.com) uitgevoerd om de gebruikerservaring te verbeteren.

- __Verbeteringen aan app-tegels__:  App-pictogrammen worden nu weergegeven met een achtergrond die automatisch wordt gegenereerd op basis van de overheersende kleur van het pictogram (mits detecteerbaar). Indien van toepassing wordt de grijze rand die voorheen zichtbaar was op app-tegels, vervangen door deze achtergrond.

    In de volgende versie worden er waar mogelijk grote pictogrammen weergegeven op de bedrijfsportalwebsite. IT-beheerders wordt aangeraden apps te publiceren met pictogrammen met een hoge resolutie en een minimumgrootte van 120 x 120 pixels. 

- __Wijzigingen in de navigatie__: Items op de navigatiebalk zijn verplaatst naar het Hamburgermenu linksboven. De pagina Categorieën is verwijderd. Gebruikers kunnen nu tijdens het browsen inhoud filteren op categorie.

- __Updates voor aanbevolen apps__: Er is een speciale pagina aan de site toegevoegd waar gebruikers door apps kunnen bladeren die door u zijn aanbevolen. Ook zijn er enkele correcties aan de gebruikersinterface aangebracht in de sectie Aanbevolen op de startpagina.

### <a name="ibooks-support-for-the-company-portal-website--1231841--"></a>Ondersteuning van iBooks voor de bedrijfsportalwebsite<!--1231841-->
Er is een speciale pagina toegevoegd aan de bedrijfsportalwebsite waarmee gebruikers iBooks kunnen zoeken en downloaden. 


### <a name="additional-help-desk-troubleshooting-details-----applies-to-1263399-1326964-1341642----"></a>Aanvullende helpdeskgegevens voor probleemoplossing<!---  Applies to 1263399, 1326964, 1341642 --->
De weergave voor probleemoplossing in Intune is bijgewerkt en toegevoegd aan de informatie voor beheerders en hepdeskmedewerkers. U ziet nu een tabel **Toewijzingen** met een overzicht van alle toewijzingen voor de gebruiker op basis van groepslidmaatschap. Dit overzicht bevat:
- Mobiele apps
- Nalevingsbeleid
- Configuratieprofielen

Bovendien zijn in de tabel **Apparaten** nu de kolommen **Type Azure AD-join** en **Azure AD-compatibel** opgenomen. Zie voor meer informatie [Gebruikers helpen om problemen op te lossen](../help-desk-operators.md).



### <a name="intune-data-warehouse-public-preview"></a>Intune-datawarehouse (openbare preview-versie)
In het Intune-datawarehouse worden dagelijks gegevens verzameld om een historisch overzicht te bieden van uw tenant. U kunt hebt toegang tot de gegevens via een Power BI-bestand (PBIX), een OData-koppeling die compatibel is met tal van analysehulpprogramma's of via interactie met de REST API. Zie [Het Intune-datawarehouse gebruiken](../developer/reports-nav-create-intune-reports.md) voor meer informatie.


### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10---676547---"></a>Lichte en donkere modi beschikbaar voor de Intune-bedrijfsportal-app voor Windows 10<!---676547--->
Eindgebruikers kunnen de kleurenmodus voor de Intune-bedrijfsportal-app voor Windows 10 aanpassen. Dit kan in de sectie Instellingen van de Intune-bedrijfsportal-app. De wijziging wordt van kracht nadat de gebruiker de app opnieuw heeft gestart. Voor Windows 10 versie 1607 en hoger wordt voor de app-modus standaard de systeeminstelling gebruikt. Voor Windows 10 versie 1511 en lager wordt voor de app-modus standaard de lichte modus gebruikt.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10---807046--"></a>Eindgebruikers kunnen hun apparaatgroep taggen in de Intune-bedrijfsportal-app voor Windows 10<!---807046-->
Eindgebruikers kunnen voortaan aangeven bij welke groep hun apparaat hoort door deze rechtstreeks vanuit de bedrijfsportal-app voor Windows 10 te taggen.

<!-- ########################## -->
## <a name="june-2017"></a>Juni 2017

### <a name="new-role-based-administration-access-for-intune-admins-----1099990---"></a>Nieuwe toegangsrol voor Intune-beheerders  <!-- 1099990 -->  
Er wordt een nieuwe beheerdersrol voor voorwaardelijke toegang toegevoegd waarmee het voorwaardelijke toegangsbeleid van Azure AD kan worden weergegeven, gemaakt en gewijzigd. Voorheen beschikten alleen hoofdbeheerders en beveiligingsbeheerders over deze machtiging. Deze rolmachtiging kan nu ook worden toegekend aan Intune-beheerders, zodat ze toegang hebben tot de beleidsregels voor voorwaardelijke toegang.


### <a name="tag-corporate-owned-devices-with-serial-number---1215070---"></a>Labelen van apparaten in bedrijfseigendom met een serienummer<!-- 1215070 -->  
Intune ondersteunt nu het uploaden van serienummers van iOS-, macOS- en Android-apparaten als id's van apparaten in bedrijfseigendom. U kunt op dit moment geen serienummers gebruiken om de registratie van persoonlijke apparaten te blokkeren, omdat er geen serienummers worden geverifieerd tijdens de registratie. U kunt persoonlijke apparaten binnenkort ook blokkeren op basis van het serienummer.


### <a name="new-remote-actions-for-ios-devices---854689---"></a>Nieuwe externe acties voor iOS-apparaten<!-- 854689 -->
In deze release zijn twee nieuwe acties voor externe apparaten toegevoegd voor gedeelde iPad-apparaten die de Apple Classroom-app beheren:

- [Huidige gebruiker afmelden](../remote-actions/device-logout-user.md): hiermee kunt u de huidige gebruiker afmelden van een iOS-apparaat dat u kiest.
- [Gebruiker verwijderen](../remote-actions/device-remove-user.md): hiermee kunt u een gebruiker verwijderen uit de lokale cache op een iOS-apparaat.


### <a name="support-for-shared-ipads-with-the-ios-classroom-app---1044681---"></a>Ondersteuning voor gedeelde iPads met de iOS-app Classroom<!-- 1044681 -->
In deze release is de ondersteuning voor het beheren van de iOS-app Classroom uitgebreid naar studenten die zich met hun beheerde Apple ID aanmelden bij gedeelde iPads.


### <a name="changes-to-intune-built-in-apps---1332306---"></a>Wijzigingen aan in Intune ingebouwde apps<!-- 1332306 -->
Voorheen bevatte Intune een aantal ingebouwde apps die u snel kon toewijzen. Op basis van uw feedback is deze lijst verwijderd en krijgt u niet langer ingebouwde apps te zien.
Als u echter al ingebouwde apps hebt toegewezen, dan zijn deze nog steeds zichtbaar in de lijst met apps. U kunt deze apps desgewenst blijven toewijzen.
In een volgende release wordt een makkelijkere methode toegevoegd voor het selecteren en toewijzen van ingebouwde apps vanuit de Azure-portal.

### <a name="easier-installation-of-office-365-apps----1121362----"></a>Eenvoudigere installatie van Office 365-apps<!--- 1121362 --->
Het nieuwe app-type **Office 365 ProPlus** maakt het eenvoudig voor u om Office 365 ProPlus 2016-apps toe te wijzen aan apparaten die u beheert waarop de nieuwste versie van Windows 10 wordt uitgevoerd. Daarnaast kunt u Microsoft Project en Microsoft Visio installeren, als u licenties hebt voor deze producten. De gewenste apps worden gebundeld en worden als één app weergegeven in de lijst met apps in de Intune-console.
Zie [Office 365-apps voor Windows 10 toevoegen](../apps/apps-add-office365.md) voor meer informatie.


### <a name="support-for-offline-apps-from-the-microsoft-store-for-business----777044----"></a>Ondersteuning voor offlineapps uit Microsoft Store voor Bedrijven<!--- 777044 --->
Offlineapps die u hebt gekocht in Microsoft Store voor Bedrijven worden voortaan gesynchroniseerd met de Azure-portal. Vervolgens kunt u deze apps implementeren naar apparaat- of gebruikersgroepen. Offline apps worden geïnstalleerd door Intune en niet door de store.

### <a name="microsoft-teams-is-now-part-of-the-app-based-ca-list-of-approved-apps-----1257019---"></a>Microsoft Teams is nu opgenomen in de lijst met goedgekeurde apps voor voorwaardelijke toegang  <!-- 1257019 -->
De Microsoft Teams-app voor iOS en Android is nu een goedgekeurde app voor toepassing van beleid voor voorwaardelijke toegang op basis van apps voor Exchange en SharePoint Online. De app kan via de blade Intune-app-beveiliging in Azure Portal worden geconfigureerd voor alle tenants die op dit moment gebruikmaken van voorwaardelijke toegang op basis van apps.

### <a name="managed-browser-and-app-proxy-integration---1287310---"></a>Managed Browser en app-proxy-integratie<!-- 1287310 -->
De Intune-app Managed Browser kan nu worden geïntegreerd met de Azure AD-toepassingsproxy om gebruikers ook toegang te bieden tot interne websites als ze op afstand werken. Gebruikers van de browser voeren op de gebruikelijke manier de URL van de gewenste site in en de Managed Browser-app verstuurt de aanvraag via de webgateway van de toepassingsproxy. Zie [Internettoegang beheren met beleid van Managed Browser](../apps/app-configuration-managed-browser.md) voor meer informatie.

### <a name="new-app-configuration-settings-for-the-intune-managed-browser---682951---"></a>Nieuw app-configuratie-instellingen voor Intune Managed Browser<!-- 682951 -->
In deze release hebben we weer extra configuraties toegevoegd voor de Intune Managed Browser-app voor iOS en Android. U kunt nu een beleid voor app-configuratie gebruiken om de standaardstartpagina en -bladwijzers voor de browser te configureren.
Zie [Internettoegang beheren met beleid van Managed Browser](../apps/app-configuration-managed-browser.md) voor meer informatie.

### <a name="bitlocker-settings-for-windows-10----951707---"></a>BitLocker-instellingen voor Windows 10 <!-- 951707 -->
U kunt nu BitLocker-instellingen configureren voor Windows 10-apparaten met behulp van een nieuw Intune-apparaatprofiel. U kunt bijvoorbeeld afdwingen dat apparaten worden versleuteld en nog andere instellingen configureren die worden toegepast als BitLocker is ingeschakeld.
Zie [Instellingen voor de beveiliging van eindpunten voor Windows 10 en hoger](../protect/endpoint-protection-windows-10.md) voor meer informatie.

### <a name="new-settings-for-windows-10-device-restriction-profile----978527--978550-978569-1050031-1058611-----"></a>Nieuwe instellingen voor het apparaatbeperkingsprofiel voor Windows 10<!--- 978527,  978550, 978569, 1050031, 1058611,  --->
In deze release hebben we nieuwe instellingen toegevoegd voor het profiel voor apparaatbeperking van Windows 10, en wel in de volgende categorieën:

- Windows Defender
- Mobiel en connectiviteit
- Vergrendeld scherm
- Privacy
- Zoeken
- Windows Spotlight
- Microsoft Edge-browser

Zie [Instellingen voor apparaatbeperking van Windows 10 en hoger](../configuration/device-restrictions-windows-10.md) voor meer informatie over Windows 10-instellingen.


### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies--1305217--"></a>De bedrijfsportal-app voor Android heeft een nieuwe eindgebruikerservaring voor app-beveiligingsbeleid<!--1305217-->
Op basis van feedback van klanten hebben we de Intune-bedrijfsportal-app voor Android aangepast en de knop **Toegang verkrijgen tot bedrijfsinhoud** toegevoegd. De reden hiervoor is dat eindgebruikers dan niet onnodig het registratieproces moeten doorlopen wanneer ze alleen toegang nodig hebben tot apps die ondersteuning bieden voor app-beveiligingsbeleid, een functie van Intune Mobile Application Management. U kunt deze wijzigingen zien op [deze pagina](whats-new-app-ui.md).

### <a name="new-menu-action-to-easily-remove-company-portal--1164569--"></a>Nieuwe menu-actie voor het eenvoudig verwijderen van de bedrijfsportal<!--1164569-->
Op basis van feedback van gebruikers is aan de bedrijfsportal-app voor Android een nieuwe menu-actie toegevoegd om het verwijderen van de bedrijfsportal van uw apparaat te starten. Met deze actie verwijdert u het apparaat uit Intune-beheer, zodat de app door de gebruiker van het apparaat kan worden verwijderd. U kunt deze wijzigingen zien op de pagina [Wat is er nieuw in de gebruikersinterface van apps](whats-new-app-ui.md) en in de [Android-eindgebruikersdocumentatie](/intune-user-help/unenroll-your-device-from-intune-android).

### <a name="improvements-to-app-syncing-with-windows-10-creators-update--676505--"></a>Verbeterde synchronisatie van apps met Windows 10-makersupdate<!--676505-->
De bedrijfsportal-app voor Windows 10 voert nu automatisch een synchronisatie uit voor app-installatieaanvragen voor apparaten met Windows 10-makersupdate (versie 1703). Hierdoor is de kans aanzienlijk kleiner dat app-installaties worden gestopt tijdens de status Synchronisatie in behandeling. Daarnaast kunnen gebruikers handmatig een synchronisatie uitvoeren vanuit de app. U kunt deze wijzigingen zien op [deze pagina](whats-new-app-ui.md).

### <a name="new-guided-experience-for-windows-10-company-portal---1058938---"></a>Nieuwe begeleide ervaring voor Windows 10-bedrijfsportal<!---1058938--->
De bedrijfsportal-app voor Windows 10 bevat een begeleiding voor Intune voor apparaten die nog niet zijn geïdentificeerd of geregistreerd. Deze nieuwe ervaring biedt stapsgewijze instructies die gebruikers begeleidt bij de registratie bij Azure Active Directory (vereist voor de voorwaardelijke toegangsfuncties) en MDM-registratie (vereist voor apparaatbeheerfuncties). De stapsgewijze instructies zijn toegankelijk via de startpagina van de bedrijfsportal. Als gebruikers de registratie en inschrijving niet voltooien, kunnen ze de app gewoon blijven gebruiken, maar is de functionaliteit beperkt.

Deze update is alleen zichtbaar op apparaten met Windows 10 Jubileumupdate (build 1607) of hoger. U kunt deze wijzigingen zien op [deze pagina](whats-new-app-ui.md).


### <a name="microsoft-intune-and-conditional-access-admin-consoles-are-generally-available"></a>Beheerconsoles voor Microsoft Intune en Voorwaardelijke toegang zijn algemeen beschikbaar
Microsoft kondigt de algemene beschikbaarheid van zowel de nieuwe Intune in de beheerconsole van de Azure-portal als de beheerconsole voor Voorwaardelijke toegang aan. Via Intune in de Azure-portal kunt u nu alle Intune MAM- en de MDM-mogelijkheden beheren in één geconsolideerde beheerderservaring en gebruikmaken van groeperen en doelen instellen met Azure AD. Voorwaardelijke toegang in Azure biedt uitgebreide mogelijkheden in Azure AD en Intune samen in één centrale console. En vanuit beheerdersoogpunt kunt u door de overgang naar het Azure-platform gebruikmaken van moderne browsers.

Intune is nu zichtbaar zonder het label **preview** in de Azure-portal op portal.azure.com.

Er is op dit moment geen actie vereist voor bestaande klanten, tenzij u in het berichtencenter een bericht hebt ontvangen waarin u wordt gevraagd actie te ondernemen, zodat de groepen kunnen worden gemigreerd. Mogelijk hebt u in het berichtencentrum ook een kennisgeving ontvangen waarin wordt gemeld dat de migratie langer duurt als gevolg van fouten aan de kant van Microsoft. Microsoft blijft zich ten volle inzetten voor het migreren van de betrokken klanten.

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>Verbeteringen in de app-tegels in de bedrijfsportal-app voor iOS
Het ontwerp van de app-tegels op de startpagina is bijgewerkt in overeenstemming met de huisstijlkleur die u voor de bedrijfsportal instelt. Raadpleeg [Wat is er nieuw in de gebruikersinterface van apps?](whats-new-app-ui.md) voor meer informatie.

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>Account objectkiezer nu beschikbaar voor de bedrijfsportal-app voor iOS
Gebruikers van iOS-apparaten zien mogelijk onze nieuwe accountkiezer wanneer ze zich aanmelden bij de bedrijfsportal als ze hun werk- of schoolaccount gebruiken voor aanmelding bij andere Microsoft-apps. Raadpleeg [Wat is er nieuw in de gebruikersinterface van apps?](whats-new-app-ui.md) voor meer informatie.

<!-- ########################## -->
## <a name="may-2017"></a>Mei 2017

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices--1103950--"></a>Wijzig uw MDM-instantie zonder de registratie van beheerde apparaten ongedaan te maken<!--1103950-->
U kunt nu uw MDM-instantie wijzigen zonder dat u contact hoeft op te nemen met Microsoft Ondersteuning en zonder dat u de registratie van bestaande beheerde apparaten ongedaan hoeft te maken om ze vervolgens opnieuw te registreren. In de Configuration Manager-console kunt u uw MDM-instantie wijzigen van Ingesteld op Configuration Manager (hybride) naar Microsoft Intune (zelfstandig) of vice versa.


### <a name="improved-notification-for-samsung-knox-startup-pins--1087143--"></a>Verbeterde melding voor Samsung Knox-opstartpincodes<!--1087143-->
Als eindgebruikers een opstartpincode op Samsung Knox-apparaten moeten instellen om te voldoen aan de versleuteling, wordt er een melding aan eindgebruikers weergegeven. Wanneer eindgebruikers op deze melding tikken, worden ze omgeleid naar de exacte plaats in de app Instellingen.  Voorheen werd de eindgebruiker omgeleid naar het scherm voor het wijzigen van het wachtwoord.

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="apple-school-manager-asm-support-with-shared-ipad---748864-770395--"></a>Ondersteuning voor Apple School Manager (ASM) met gedeelde iPad<!-- 748864, 770395-->

Intune ondersteunt nu het gebruik van Apple School Manager (ASM) in plaats van Apple Device Enrollment Program voor een out-of-box-registratie van iOS-apparaten. Onboarding van ASM is vereist om de app Classroom voor gedeelde iPads te kunnen gebruiken en om gegevens via Microsoft School Data Sync (SDS) te kunnen synchroniseren van ASM naar Azure Active Directory. Zie [Inschrijving van iOS-apparaten inschakelen met Apple School Manager](../enrollment/apple-school-manager-set-up-ios.md) voor meer informatie.

> [!NOTE]
> Voor het configureren van gedeelde iPads voor het werken met de app Classroom zijn iOS Education-configuraties in Azure vereist die nog niet beschikbaar zijn.  Deze functionaliteit wordt binnenkort toegevoegd.

### <a name="device-management"></a>Apparaatbeheer

#### <a name="provide-remote-assistance-to-android-devices-using-teamviewer---675418---"></a>Hulp op afstand verlenen op Android-apparaten met TeamViewer<!-- 675418 -->

Intune kan nu de afzonderlijk verkrijgbare [TeamViewer](https://www.teamviewer.com)-software gebruiken, zodat u uw gebruikers met Android-apparaten hulp op afstand kunt bieden. Zie [Provide remote assistance for Intune managed Android devices](../remote-actions/teamviewer-support.md) (Hulp op afstand verlenen voor Android-apparaten die worden beheerd door Intune) voor meer informatie.

### <a name="app-management"></a>Appbeheer

#### <a name="new-app-protection-policies-conditions-for-mam---679864---"></a>Nieuwe beleidsvoorwaarden voor MAM met betrekking tot de beveiliging van apps<!-- 679864 -->

U kunt nu een vereiste instellen voor gebruikers die MAM gebruiken zonder inschrijving. Hiermee kunt u het volgende afdwingen:

- Minimumversie van de toepassing
- Minimumversie van het besturingssysteem
- Minimumversie van de SDK voor de Intune-app van de doeltoepassing (alleen iOS)

Deze functie is beschikbaar op Android en iOS. Intune ondersteunt het afdwingen van een minimumversie voor besturingssystemen, toepassingen en de SDK voor de Intune-app. Voor iOS geldt dat toepassingen met een geïntegreerde SDK ook een minimumversie kunnen afdwingen op SDK-niveau. De gebruiker heeft geen toegang tot de betreffende toepassing als niet aan de minimale vereisten van het app-beveiligingsbeleid wordt voldaan op de hierboven genoemde drie verschillende niveaus. Op dit moment kan de gebruiker het account (voor toepassingen met meerdere identiteiten) verwijderen, de toepassing sluiten of de versie van het besturingssysteem of de toepassing bijwerken.

U kunt tevens aanvullende instellingen configureren om een niet-blokkerende melding te verstrekken waarin de gebruiker wordt aanbevolen een upgrade voor het besturingssysteem of de toepassing uit te voeren. Deze melding kan worden gesloten en de toepassing kan gewoon worden gebruikt.

Zie [Beveiligingsbeleidsinstellingen voor iOS-apps](../apps/app-protection-policy-settings-ios.md) en [Beveiligingsbeleidsinstellingen voor Android-apps](../apps/app-protection-policy-settings-android.md) voor meer informatie.

#### <a name="configure-app-configurations-for-android-for-work---621621---"></a>App-instellingen configureren voor Android for Work<!-- 621621 -->
Sommige Android-apps uit de store ondersteunen beheerde configuratieopties waarmee een IT-beheerder kan controleren hoe een app wordt uitgevoerd in het werkprofiel. Met Intune kunt u nu de configuraties weergeven die worden ondersteund door een app en deze configureren vanuit de Azure-portal met een configuratieontwerper of een JSON-editor. Zie [Use app configurations for Android for Work](../apps/app-configuration-policies-use-android.md) (App-configuraties gebruiken voor Android for Work) voor meer informatie.

#### <a name="new-app-configuration-capability-for-mam-without-enrollment---677969---"></a>Nieuwe mogelijkheid voor app-configuratie voor MAM zonder inschrijving<!-- 677969 -->
U kunt nu beleidsregels voor app-configuratie maken via het kanaal voor MAM zonder inschrijving. Deze functie is gelijk aan de beleidsregels voor app-configuratie die beschikbaar zijn in de MDM-app-configuratie (Mobile Device Management). Zie [Internettoegang beheren met beheerde-browserbeleid met Microsoft Intune](../apps/app-configuration-managed-browser.md) voor een voorbeeld van app-configuratie met MAM zonder inschrijving.

#### <a name="configure-allowed-and-blocked-url-lists-for-the-managed-browser---682960---"></a>Lijsten met toegestane en geblokkeerde URL's voor Managed Browser configureren<!-- 682960 -->
U kunt nu een lijst configureren met toegestane en geblokkeerde domeinen en URL's voor de Intune Managed Browser met app-configuratie-instellingen in Azure Portal. Deze instellingen kunnen altijd worden geconfigureerd, ongeacht of de lijst wordt gebruikt op een beheerd of onbeheerd apparaat. Zie [Internettoegang beheren met beheerde-browserbeleid met Microsoft Intune](../apps/app-configuration-managed-browser.md) voor meer informatie.

#### <a name="app-protection-policy-helpdesk-view---1069473---"></a>Helpdeskweergave voor beveiligingsbeleidsinstellingen voor apps<!-- 1069473 -->
IT-helpdeskgebruikers kunnen nu de status van de gebruikerslicentie en de status van aan gebruikers toegewezen app-beveiligingsbeleid controleren de blade voor probleemoplossing. Zie [Probleemoplossing](./help-desk-operators.md) voor meer informatie.

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="control-website-visits-on-ios-devices---723832---"></a>Websitebezoeken op iOS-apparaten controleren<!-- 723832 -->
U kunt nu bepalen welke websites de gebruikers van iOS-apparaten kunnen bezoeken met een van de volgende twee methoden:

- Toegestane en geblokkeerde URL's toevoegen met het ingebouwde webinhoudsfilter van Apple.

- Alleen opgegeven websites toestaan voor de Safari-browser. Voor elke website die u opgeeft wordt een bladwijzer gemaakt in Safari.

Zie [Filterinstellingen voor webinhoud op iOS-apparaten](../configuration/ios-device-features-settings.md#web-content-filter) voor meer informatie.

#### <a name="preconfigure-device-permissions-for-android-for-work-apps---621614---"></a>Apparaatmachtigingen voor Android for Work-apps vooraf configureren<!-- 621614 -->
Voor apps die worden geïmplementeerd voor Android for Work-apparaatwerkprofielen, kunt u nu de machtigingsstatus configureren voor afzonderlijke apps.  Android-apps die apparaatmachtigingen vereisen, zoals voor toegang tot uw locatie of de apparaatcamera, vragen gebruikers de machtiging te accepteren of te weigeren.  Als een app bijvoorbeeld gebruikmaakt van de microfoon van het apparaat, wordt de gebruiker gevraagd de app toestemming te verlenen voor het gebruik van de microfoon. Met deze functie kunt u namens de eindgebruiker machtigingen definiëren.  U kunt machtigingen configureren voor a) automatisch weigeren zonder de gebruiker op de hoogte te stellen, b) automatisch goedkeuren zonder de gebruiker op de hoogte te stellen of c) de gebruiker vragen om te accepteren of weigeren. Zie [Android for Work-apparaatbeperkingsinstellingen in Microsoft Intune](../configuration/device-restrictions-android-for-work.md) voor meer informatie.

#### <a name="define-app-specific-pin-for-android-for-work-devices---728976-1102534---"></a>Een app-specifieke pincode definiëren voor Android for Work-apparaten<!-- 728976, 1102534 -->
U kunt een wachtwoordcodebeleid definiëren dat alleen van toepassing is op apps in het werkprofiel voor apparaten met Android 7.0 en hoger die worden beheerd als een Android for Work-apparaat.  Opties zijn onder andere:

- Alleen een apparaatbreed wachtwoordcodebeleid definiëren: dit is de wachtwoordcode die de gebruiker moet gebruiken om het hele apparaat te ontgrendelen.
- Alleen een wachtwoordcodebeleid voor een werkprofiel definiëren: steeds wanneer gebruikers een app in het werkprofiel openen, worden ze gevraagd een wachtwoordcode in te voeren.
- Zowel een apparaat- als een werkprofielbeleid definiëren: de IT-beheer kan verschillende sterktes voor de wachtwoordcodes in het beleid voor apparaten en het beleid voor werkprofielen definiëren (bijvoorbeeld een pincode van vier cijfers om het apparaat te ontgrendelen, maar een pincode van zes cijfers om een werk-app te openen).

Zie [Android for Work-apparaatbeperkingsinstellingen in Microsoft Intune](../configuration/device-restrictions-android-for-work.md) voor meer informatie.

> [!NOTE]
> Dit is alleen beschikbaar in Android 7.0 en later.  De eindgebruiker kan standaard de twee afzonderlijk gedefinieerde pincodes gebruiken, maar kan er ook voor kiezen om de twee gedefinieerde pincodes te combineren in de sterkste van de twee.

#### <a name="new-settings-for-windows-10-devices---978585---"></a>Nieuwe instellingen voor Windows 10-apparaten<!-- 978585 -->
Er zijn nieuwe [Instellingen beperkingen voor Windows-apparaten](../configuration/device-restrictions-windows-10.md) toegevoegd. Hiermee worden zaken als draadloze beeldschermen, apparaatdetectie, het schakelen tussen taken en simkaartfoutberichten beheerd.

#### <a name="updates-to-certificate-configuration---918991-and-823198---"></a>Updates voor de certificaatconfiguratie<!-- 918991 and 823198 -->
Wanneer u een SCEP-certificaatprofiel maakt voor <strong>indeling van de onderwerpnaam</strong>, is de <strong>aangepaste</strong> optie beschikbaar voor iOS-, Android- en Windows-apparaten. Voor deze update was het veld <strong>aangepast</strong> beschikbaar voor iOS-apparaten. Zie [Een SCEP-certificaatprofiel maken](../protect/certificates-profile-scep.md) voor meer informatie.

Wanneer u een PKCS certificaatprofiel maakt, is voor **Alternatieve naam voor onderwerp** het **Aangepaste Azure AD-kenmerk** beschikbaar. De optie **Afdeling** is beschikbaar wanneer u **Aangepast Azure AD-kenmerk** selecteert. Zie [Een PKCS-certificaatprofiel maken](../protect/certficates-pfx-configure.md#create-a-pkcs-certificate-profile) voor meer informatie.

#### <a name="configure-multiple-apps-that-can-run-when-an-android-device-is-in-kiosk-mode---662059---"></a>Meerdere apps configureren die kunnen worden uitgevoerd wanneer een Android-apparaat in kioskmodus wordt uitgevoerd<!-- 662059 -->
Voorheen kon u slechts één app configureren die mocht worden uitgevoerd op een Android-apparaat dat in kioskmodus wordt uitgevoerd. U kunt nu meerdere apps configureren met de app-ID, de URL van de store of door een Android-app te selecteren die u al beheert. Zie [Instellingen voor kioskmodus](../configuration/device-restrictions-android.md#kiosk) voor meer informatie.

<!-- ########################## -->
## <a name="april-2017"></a>April 2017

### <a name="support-for-managing-the-apple-classroom-app"></a>Ondersteuning voor het beheer van de app Apple Classroom
U kunt nu de iOS-app Classroom beheren op iPad-apparaten. Configureer de app Classroom op de iPad van docenten, met de juiste klas- en studentengegevens en configureer vervolgens de iPads van studenten die zijn geregistreerd bij een klas, zodat u deze met de app kunt beheren.
Zie [Opleidingsinstellingen voor iOS configureren](education-settings-configure-ios.md) voor meer informatie.

### <a name="support-for-managed-configuration-options-for-android-apps---621621---"></a>Ondersteuning voor beheerde configuratieopties voor Android-apps<!-- 621621 -->
Android-apps in de Play Store die beheerde configuratieopties ondersteunen kunnen nu worden geconfigureerd door Intune.  Dankzij deze functie kan de IT-afdeling een lijst weergeven met de configuratiewaarden die door een app worden ondersteund, en kunnen die waarden worden geconfigureerd in een begeleide, eersteklas gebruikersinterface.

### <a name="new-android-policy-for-complex-pins---722069---"></a>Nieuw Android-beleid voor complexe pincodes<!-- 722069 -->
U kunt een verplicht type [wachtwoord](../configuration/device-restrictions-android.md#password) instellen op Numeriek complex in een Android-apparaatprofiel voor apparaten met Android 5.0 en hoger.  Met deze instelling voorkomt u dat gebruikers een pincode kiezen die herhalende of opeenvolgende cijfers bevat, zoals 1111 of 1234.

### <a name="additional-support-for-android-for-work-devices"></a>Aanvullende ondersteuning voor Android for Work-apparaten
- **Wachtwoord- en werkprofieleninstellingen beheren**<!-- 612808 -->

  Met dit nieuwe Android for Work-apparaatbeperkingsbeleid kunt u uw wachtwoord- en werkprofielinstellingen beheren op de Android for Work-apparaten die u beheert.

- **Gegevens delen tussen werkprofielen en persoonlijke profielen toestaan**<!-- 1045102 -->

Dit werkprofiel voor Android for Work-apparaatbeperkingen heeft nieuwe opties waarmee u het delen van gegevens tussen werkprofielen en persoonlijke profielen kunt configureren.

- **Kopiëren en plakken tussen werkprofielen en persoonlijke profielen beperken**<!-- 1046094 -->

  Er is nu een nieuw aangepast apparaatprofiel voor Android for Work-apparaten, waarmee u kunt instellen of het kopiëren en plakken tussen werk-apps en persoonlijke apps is toegestaan.

Zie voor meer informatie [Apparaatbeperkingen voor Android for Work](../configuration/device-restrictions-android-for-work.md).

### <a name="assign-lob-apps-to-ios-and-android-devices---1057568---"></a>LOB-apps toewijzen aan iOS- en Android-apparaten<!-- 1057568 -->
U kunt nu line-of-business-apps (LOB) voor [iOS](../apps/lob-apps-ios.md) (IPA-bestanden) en [Android](../apps/lob-apps-android.md) (APK-bestanden) toewijzen aan gebruikers of apparaten.


### <a name="new-device-policies-for-ios---723774-723815-723826-723830---"></a>Nieuw apparaatbeleid voor iOS<!-- 723774, 723815, 723826, 723830 -->
- **Apps op beginscherm**: u kunt instellen welke apps gebruikers zien op het [startscherm van hun iOS-apparaat](../configuration/ios-device-features-settings.md#home-screen-layout). Dit beleid wijzigt de indeling van het beginscherm, maar implementeert geen apps.

- **Verbindingen met AirPrint-apparaten**: u kunt instellen met welke [AirPrint-apparaten](../configuration/ios-device-features-settings.md#airprint) (netwerkprinters) de eindgebruikers van het iOS-apparaat verbinding kunnen maken.

- **Verbindingen met AirPlay-apparaten**: u kunt bepalen met welke [AirPlay-apparaten](../configuration/ios-device-features-settings.md) (zoals Apple TV) de eindgebruikers van het iOS-apparaat verbinding kunnen maken.

- **Aangepast bericht vergrendelingsscherm**: U kunt een aangepast bericht configureren dat de gebruikers zien op het vergrendelingsscherm van hun iOS-apparaat. Dit bericht vervangt het standaardbericht op het vergrendelingsscherm. Zie [De modus Apparaat verloren activeren op iOS-apparaten](../remote-actions/device-lost-mode.md) voor meer informatie

### <a name="restrict-push-notifications-for-ios-apps---723767---"></a>Pushmeldingen voor iOS-apps beperken<!-- 723767 -->
In een Intune-apparaatbeperkingsprofiel kunt u nu de volgende [meldingsinstellingen](../configuration/ios-device-features-settings.md#app-notifications) voor iOS-apparaten configureren:

- Meldingen voor een opgegeven app volledig in- of uitschakelen.
- Meldingen voor een opgegeven app in- of uitschakelen in het berichtencentrum.
- Het type waarschuwing opgeven: **Geen**, **Banner** of **Modale waarschuwing**.
- Opgeven of badges zijn toegestaan voor deze app.
- Opgeven of meldingsgeluiden zijn toegestaan.

### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously---737837---"></a>iOS-apps configureren voor autonome uitvoering in één-app-modus<!-- 737837 -->
U kunt nu een Intune-apparaatprofiel gebruiken om iOS-apparaten te configureren voor het uitvoeren van opgegeven apps in de [Autonome modus voor enkele toepassing](../configuration/device-restrictions-ios.md#autonomous-single-app-mode). Wanneer deze modus is geconfigureerd en de app wordt uitgevoerd, wordt het apparaat vergrendeld zodat alleen de betreffende app kan worden uitgevoerd. U kunt bijvoorbeeld een app configureren die de gebruikers een test laat uitvoeren op het apparaat. Wanneer de acties van de app zijn voltooid of u het beleid verwijdert, keert het apparaat terug naar de normale staat.

### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices---723765---"></a>Vertrouwde domeinen configureren voor e-mail en browsen op het web op iOS-apparaten<!-- 723765 -->
In een iOS-apparaatbeperkingsprofiel kunt u nu de volgende [domeininstellingen](../configuration/device-restrictions-ios.md#domains) configureren:

- **Niet-gemarkeerde e-maildomeinen**: e-mailberichten die de gebruiker verzendt of ontvangt die niet overeenkomen met de domeinen die u hier opgeeft, worden gemarkeerd als niet-vertrouwd.

- **Beheerde webdomeinen**: documenten die zijn gedownload via de URL's die u hier opgeeft, worden als beheerd beschouwd (alleen in Safari).  

- **Domeinen voor automatisch invullen van wachtwoorden in Safari**: gebruikers kunnen alleen wachtwoorden opslaan in Safari voor de URL's die overeenkomen met de patronen die u hier opgeeft. Als u deze instelling wilt gebruiken, moet het apparaat in de supervisiemodus staan en niet zijn geconfigureerd voor meerdere gebruikers. (iOS 9.3+)


### <a name="vpp-apps-available-in-ios-company-portal---748782---"></a>VPP-apps beschikbaar in de iOS-bedrijfsportal<!-- 748782 -->
U kunt iOS-apps die zijn gekocht via het volume-aankoopprogramma toewijzen als **Beschikbaar** voor installatie door eindgebruikers. Eindgebruikers hebben een Apple Store-account nodig om de app te installeren.

### <a name="synchronize-ebooks-from-apple-vpp-store---800878---"></a>eBooks synchroniseren vanuit Apple VPP Store<!-- 800878 -->
U kunt nu met Intune [boeken synchroniseren](../apps/vpp-apps-ios.md) die u hebt gekocht via het volume-aankoopprogramma van Apple en de boeken toewijzen aan gebruikers.

### <a name="multi-user-management-for-samsung-knox-standard-devices---971988---"></a>Beheer van meerdere gebruikers voor Samsung Knox Standard-apparaten<!-- 971988 -->
Apparaten waarop Samsung Knox Standard wordt uitgevoerd, bieden nu ondersteuning voor [beheer van meerdere gebruikers](../enrollment/android-enroll.md) in Intune. Dit betekent dat eindgebruikers zich kunnen aan- en afmelden bij het apparaat met hun Azure Active Directory-referenties, en dat het apparaat centraal wordt beheerd, ongeacht of het wordt gebruikt of niet.  Wanneer eindgebruikers zich aanmelden, hebben ze toegang tot apps en wordt eventueel aanvullend beleid toegepast. Wanneer ze zich afmelden, worden alle app-gegevens gewist.

### <a name="additional-windows-device-restriction-settings---818566---"></a>Aanvullende Windows 10-apparaatbeperkingsinstellingen<!-- 818566 -->
Er is ondersteuning toegevoegd voor aanvullende [Windows-apparaatbeperkingsinstellingen](../configuration/device-restrictions-windows-10.md), zoals aanvullende ondersteuning voor Microsoft Edge, het aanpassen van het vergrendelingsscherm, het aanpassen van het startmenu, het instellen van de zoekfunctie van Windows Spotlight als achtergrondafbeelding en proxy-instellingen.

### <a name="multi-user-support-for-windows-10-creators-update---822547---"></a>Ondersteuning voor meerdere gebruikers van Windows 10-makersupdate<!-- 822547 -->
Er is ondersteuning toegevoegd voor het [beheer van meerdere gebruikers](../enrollment/windows-enroll.md) voor apparaten waarop de Windows 10-makersupdate wordt uitgevoerd en die zijn toegevoegd aan een Azure Active Directory-domein. Dit betekent dat wanneer verschillende standaardgebruikers zich aanmelden op het apparaat met hun Azure AD-referenties, ze de apps en beleidsregels ontvangen die zijn toegewezen aan hun gebruikersnaam. Gebruikers kunnen de bedrijfsportal op dit moment niet gebruiken voor selfservice scenario's zoals het installeren van apps.

### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Fresh Start voor Windows 10-pc's<!-- 1004830 -->
Er is nu een apparaatactie [Nieuwe start](../remote-actions/device-fresh-start.md) voor Windows 10-pc's beschikbaar.  Wanneer u deze actie uitvoert, worden alle apps die op de pc zijn geïnstalleerd verwijderd en wordt de pc automatisch bijgewerkt naar de laatste Windows-versie. Hiermee verwijdert u vooraf geïnstalleerde OEM-apps die vaak op nieuwe pc's staan. U kunt configureren of de gebruikersgegevens bewaard blijven wanneer u deze actie uitvoert.

### <a name="additional-windows-10-upgrade-paths---903672---"></a>Aanvullende upgradepaden voor Windows 10<!-- 903672 -->
U kunt nu een [versie-upgradebeleid maken om apparaten bij te werken](../configuration/edition-upgrade-configure-windows-10.md) naar de volgende aanvullende Windows 10-edities:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

### <a name="bulk-enroll-windows-10-devices---747607---"></a>Windows 10-apparaten bulksgewijs inschrijven<!-- 747607 -->
U kunt nu grote aantallen apparaten waarop de Windows 10-makersupdate wordt uitgevoerd toevoegen aan Azure Active Directory en Intune met Windows Configuration Designer (WCD). Als u [bulksgewijze MDM-registratie](../enrollment/windows-bulk-enroll.md) voor uw Azure AD-tenant wilt inschakelen, maakt u een inrichtingspakket waarmee apparaten worden toegevoegd aan uw Azure AD-tenant met Windows Configuration Designer. Vervolgens past u het pakket toe op apparaten die bedrijfseigendom zijn en die u bulksgewijs wilt registreren en beheren. Zodra het pakket is toegepast op de apparaten, worden deze toegevoegd aan Microsoft Azure AD, ingeschreven bij Intune en kunnen uw Azure AD-gebruikers zich erbij aanmelden.  Azure AD-gebruikers zijn standaardgebruikers op deze apparaten en ontvangen toegewezen beleid en de vereiste apps. Scenario's voor de selfserviceportal en de bedrijfsportal worden momenteel niet ondersteund.

### <a name="new-mam-settings-for-pin-and-managed-storage-locations---581122-736644---"></a>Nieuwe MAM-instellingen voor pincode en beheerde opslaglocaties<!-- 581122, 736644 -->
Er zijn nu twee nieuwe app-instellingen beschikbaar voor het beheren van mobiele toepassingen:

- **App-pincode uitschakelen wanneer apparaatpincode wordt beheerd**: deze instelling detecteert of er een apparaatpincode aanwezig is op het ingeschreven apparaat. Als dat het geval is, wordt de app-pincode die wordt geactiveerd door het app-beveiligingsbeleid omzeild. Deze instelling zorgt ervoor dat gebruikers minder vaak een pincode hoeven in te voeren wanneer zij een beheerde mobiele toepassing openen op een ingeschreven apparaat. Deze functie is beschikbaar op Android en iOS.

- **Selecteer naar welke opslagservices bedrijfsgegevens kunnen worden opgeslagen**: hiermee kunt u opgeven welke opslaglocaties mogen worden gebruikt voor het opslaan van bedrijfsgegevens. Gebruikers kunnen alleen opslaan in de geselecteerde opslaglocatieservices, wat inhoudt dat de opslaglocatieservices die niet worden vermeld, zijn geblokkeerd.

  Lijst met ondersteunde opslaglocatieservices:

  - OneDrive
  - Zakelijke SharePoint Online
  - Lokale opslag

### <a name="help-desk-troubleshooting-portal---907448---"></a>Helpdesk voor portal voor probleemoplossing<!-- 907448 -->
Met de nieuwe [Portal voor problemen oplossen](../help-desk-operators.md) kunnen helpdeskmedewerkers en Intune-beheerders de gebruikers en hun apparaten weergeven, en taken uitvoeren voor het oplossen van technische problemen met Intune.

<!-- ########################## -->
## <a name="march-2017"></a>Maart 2017

### <a name="support-for-ios-lost-mode--431695--"></a>Ondersteuning voor iOS voor de modus Apparaat verloren<!--431695-->
Voor apparaten met iOS 9.3 en hoger is in Intune ondersteuning toegevoegd voor de **modus Apparaat verloren**. U kunt nu een apparaat vergrendelen om verder gebruik te voorkomen en een bericht en telefoonnummer weergeven op het vergrendelingsscherm van het apparaat.

De eindgebruiker kan het apparaat pas ontgrendeld wanneer een beheerder de modus Apparaat verloren heeft uitgeschakeld. Als de modus Apparaat verloren is ingeschakeld, kunt u de actie **Apparaat zoeken** uitvoeren om de geografische locatie van het apparaat weer te geven op een kaart in de Intune-console.

Het apparaat moet een iOS-apparaat in bedrijfseigendom zijn, dat via DEP is ingeschreven en waarop de supervisiemodus is ingeschakeld.

Zie [Wat is Microsoft Intune-apparaatbeheer?](../remote-actions/device-management.md) voor meer informatie.

### <a name="improvements-to-device-actions-report--677150--"></a>Verbeteringen aan het rapport Apparaatacties<!--677150-->
Er zijn verbeteringen aangebracht aan het rapport Apparaatacties voor betere prestaties. Bovendien kunt u het rapport nu filteren op basis van status. U kunt het rapport bijvoorbeeld filteren zodat alleen de apparaatacties worden weergegeven die zijn voltooid.

### <a name="custom-app-categories--748805--"></a>Aangepaste app-categorieën<!--748805-->
U kunt nu categorieën maken, bewerken en toewijzen voor apps die u aan Intune toevoegt. Categorieën kunnen momenteel alleen worden opgegeven in het Engels.
Zie [Een app toevoegen aan Intune](../apps/apps-add.md).

### <a name="assign-lob-apps-to-users-with-unenrolled-devices--748823--"></a>LOB-apps toewijzen aan gebruikers met niet-ingeschreven apparaten<!--748823-->
U kunt nu Line-Of-Business-apps uit de store toewijzen aan gebruikers, ongeacht of hun apparaten zijn ingeschreven bij Intune. Als een apparaat van een gebruiker niet is geregistreerd bij Intune, moet deze daarvoor de bedrijfsportalwebsite gebruiken en niet de bedrijfsportal-app.

### <a name="new-compliance-reports--846671--"></a>Nieuwe nalevingsrapporten<!--846671-->
U hebt nu nalevingsrapporten die u informatie bieden over de naleving van apparaten in uw bedrijf. U kunt dan ook snel aan naleving gerelateerde problemen oplossen waar uw gebruikers mee te maken krijgen. U kunt informatie bekijken over

- De algemene nalevingsstatus van apparaten
- De nalevingsstatus voor een specifieke instelling
- De nalevingsstatus voor een specifiek beleid

U kunt deze rapporten ook gebruiken om in te zoomen op een specifiek apparaat, om op die manier te bekijken welke instellingen en beleidsregels van invloed zijn op dat apparaat.

<!--- You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N --->

### <a name="direct-access-to-apple-enrollment-scenarios--951869--"></a>Rechtstreekse toegang tot Apple-scenario's voor inschrijving<!--951869-->
Voor Intune-accounts die na januari 2017 zijn gemaakt, heeft Intune rechtstreekse toegang ingeschakeld tot Apple-inschrijvingsscenario's. Hiervoor is de werkstroom voor het inschrijven van apparaten gebruikt in Azure Portal. Voorheen was de Apple-inschrijvingspreview alleen toegankelijk via koppelingen in de Azure-portal. Intune-accounts die vóór januari 2017 zijn gemaakt, moeten eenmalig worden gemigreerd om de functies in Azure beschikbaar te maken. De planning voor de migratie is nog niet aangekondigd, maar de informatie wordt zo snel mogelijk beschikbaar gemaakt. Het wordt aangeraden om een testaccount te maken om de nieuwe ervaring te testen, als u met uw bestaande account geen toegang hebt tot de preview.


<!-- ########################## -->
## <a name="february-2017"></a>Februari 2017

### <a name="ability-to-restrict-mobile-device-enrollment--747600-795782--"></a>Mogelijkheid om de inschrijving van mobiele apparaten te beperken<!--747600, 795782-->
Er zijn in Intune nieuwe inschrijvingsbeperkingen toegevoegd die bepalen welke platforms voor mobiele apparaten kunnen worden ingeschreven. Intune onderscheidt platforms voor mobiele apparaten als iOS, macOS, Android, Windows en Windows Mobile.

- Een beperking voor de registratie van mobiele apparaten, betekent niet dat de PC-clientregistratie ook is beperkt.  
- Alleen voor iOS en Android geldt er een extra optie voor het blokkeren van de inschrijving van apparaten die in persoonlijk eigendom zijn.

Intune markeert alle nieuwe apparaten als persoonlijk, tenzij de IT-beheerder actie onderneemt om deze te markeren als bedrijfseigen, zoals uitgelegd in [dit artikel](../enrollment/device-enrollment.md).

### <a name="view-all-actions-on-managed-devices--677150--"></a>Alle acties voor beheerde apparaten weergeven<!--677150-->
Er is een nieuw rapport __Apparaatacties__, waarin wordt weergegeven wie externe acties, zoals het herstellen van fabrieksinstellingen, op apparaten heeft uitgevoerd. In dit rapport wordt ook de status van de actie getoond. Zie [Wat is apparaatbeheer?](../remote-actions/device-management.md).

### <a name="non-managed-devices-can-access-assigned-apps--664691--"></a>Niet-beheerde apparaten hebben toegang tot toegewezen apps<!--664691-->
Als onderdeel van de ontwerpwijzigingen op de bedrijfsportalwebsite kunnen iOS- en Android-gebruikers op hun niet-beheerde apparaten apps installeren die aan hen zijn toegewezen als 'beschikbaar zonder inschrijving'. Gebruikers kunnen zich met behulp van hun Intune-referenties aanmelden bij de bedrijfsportalwebsite en de lijst met aan hen toegewezen apps bekijken. De app-pakketten van de 'beschikbaar zonder inschrijving'-apps kunnen worden gedownload via de bedrijfsportalwebsite. Deze wijziging is niet van toepassing op apps die pas na inschrijving kunnen worden geïnstalleerd, omdat gebruikers wordt gevraagd hun apparaat in te schrijven als zij deze apps willen installeren.

### <a name="custom-app-categories--748805--"></a>Aangepaste app-categorieën<!--748805-->
U kunt nu categorieën maken, bewerken en toewijzen voor apps die u aan Intune toevoegt. Categorieën kunnen momenteel alleen worden opgegeven in het Engels.
Zie [Een app toevoegen aan Intune](../apps/apps-add.md).

### <a name="display-device-categories--814654--"></a>Apparaatcategorieën weergeven<!--814654-->
U kunt nu de apparaatcategorie als kolom in de lijst met apparaten weergeven. U kunt ook de categorie uit de sectie met eigenschappen van de apparaateigenschappenblade bewerken. Zie [Een app toevoegen aan Intune](../apps/apps-add.md).

### <a name="configure-windows-update-for-business-settings--776716--"></a>Instellingen voor Windows Update voor bedrijven configureren<!--776716-->

Windows as a Service is de nieuwe manier voor het aanbieden van updates voor Windows 10. Vanaf Windows 10 bevatten alle Upgrades van onderdelen en Kwaliteitsupdates de inhoud van alle voorgaande updates. Dit houdt in dat, als u de nieuwste update hebt geïnstalleerd, u zeker weet dat uw Windows 10-apparaten volledig zijn bijgewerkt. In tegenstelling tot eerdere versies van Windows, moet u nu de volledige update installeren in plaats van een onderdeel van een update.

Met Windows Update voor bedrijven kunt u updatebeheer vereenvoudigen, zodat u geen afzonderlijke updates voor groepen apparaten hoeft goed te keuren. U kunt nog steeds risico's in uw omgeving beheren door een strategie voor update-implementatie te configureren. Windows Update zorgt ervoor dat updates op tijd worden geïnstalleerd. Microsoft Intune biedt de mogelijkheid update-instellingen op apparaten te configureren en biedt u de mogelijkheid de installatie van updates uit te stellen. Intune slaat de updates niet op, maar alleen de beleidstoewijzing voor de update. Apparaten hebben voor de updates rechtstreeks toegang tot Windows Update. Voor het configureren en beheren van **Windows 10-updateringen** wordt Intune gebruikt. Een updatering bevat een aantal instellingen waarin is geconfigureerd wanneer en hoe Windows 10-updates worden geïnstalleerd. Zie [Instellingen voor Windows Update voor bedrijven configureren](../protect/windows-update-for-business-configure.md) voor meer informatie.
