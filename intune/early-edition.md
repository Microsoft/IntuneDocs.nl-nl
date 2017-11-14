---
title: Vroege editie
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 11/6/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f7cc595655950ef1bf2586e939b6f02e270e7afc
ms.sourcegitcommit: 5279a0bb8c5aef79aa57aa247ad95888ffe5a12b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/08/2017
---
# <a name="the-early-edition-for-microsoft-intune---november-2017"></a>De vroege editie voor Microsoft Intune - november 2017

De **vroege editie** bevat een lijst met functies die worden toegevoegd aan toekomstige releases van Microsoft Intune. Deze informatie wordt in beperkte mate verstrekt en kan worden gewijzigd. Deel deze informatie niet buiten uw bedrijf. Sommige functies die hier worden vermeld, zullen mogelijk niet beschikbaar zijn op de sluitingsdatum en worden mogelijk beschikbaar gesteld in een latere release. Andere functies worden getest in een proefversie, zodat we zeker weten dat ze in gebruik kunnen worden genomen. Als u vragen of opmerkingen hebt, kunt contact opnemen met uw contactpersoon voor de Microsoft-productgroep.

Deze pagina wordt regelmatig bijgewerkt. Controleer op andere updates.

> [!Note]
>De volgende wijzigingen worden momenteel ontwikkeld voor Intune. Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->


## <a name="intune-in-the-azure-portal"></a>Intune in Azure Portal


### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Mobiele apps van Office 365 toewijzen aan iOS- en Android-apparaten met behulp van de ingebouwde app-type<!-- 1332318 -->
Het **ingebouwde** app-type maakt het eenvoudiger voor u om Office 365-apps te maken en toe te wijzen aan door u beheerde iOS- en Android-apparaten. Deze apps zijn onder andere 0365-apps, zoals Word, Excel, PowerPoint en OneDrive. U kunt specifieke apps toewijzen aan het app-type en de configuratie van de app-gegevens bewerken.

### <a name="single-sign-on-support-for-ios----1333645---"></a>Ondersteuning voor Eenmalige aanmelding voor iOS<!-- 1333645 -->  
U kunt Eenmalige aanmelding voor iOS-gebruikers gebruiken. De iOS-apps die zijn gecodeerd om naar de gebruikersreferenties te zoeken in de Eenmalige aanmelding-payload zijn functioneel voor de update van de payloadconfiguratie. U kunt ook de UPN en de Intune-apparaat-id gebruiken om de Principal-naam en de Realm te configureren.

### <a name="ios-11-app-inventory-api-for-mobile-threat-detection----1391759---"></a>API iOS 11-app-inventaris voor mobiele detectie van dreigingen (MTD) <!-- 1391759 -->
Intune verzamelt informatie over de app-inventaris van apparaten in zowel privé- als bedrijfseigendom en maakt deze informatie beschikbaar voor MTD-providers om op te halen, zoals Lookout for Work. U kunt de app-inventaris verzamelen van de gebruikers van iOS 11+-apparaten.

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

### <a name="audit-updates----1412961---"></a>Updates controleren<!-- 1412961 -->  
Controles van Intune biedt een record van de wijzigingsbewerkingen ten aanzien van Intune.  Alle taakbewerkingen voor maken, bijwerken, verwijderen en externe taakbewerkingen worden vastgelegd en een jaar bewaard.  De Azure Portal voorziet in een weergave van de controlegegevens van laatste 30 dagen in elke workload, welke gefilterd kan worden.  Met de bijbehorende Graph API kunt u de controlegegevens ophalen die het afgelopen jaar zijn bewaard. 

Controles zijn te vinden onder de groep **CONTROLE**. Er is een menu-item **Controlelogboeken** voor elke workload.   

### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Tekstprotocol toegestaan vanuit beheerde Apps<!-- 1414050  -->
Met apps die worden beheerd door de Intune App SDK kunnen SMS-berichten worden verzonden.

### <a name="remotely-restart-ios-device-supervised-only----1424595---"></a>iOS-apparaat op afstand opnieuw opstarten (alleen onder supervisie)<!-- 1424595 -->
U kunt een iOS 10.3 +-apparaat onder supervisie activeren om via een apparaatactie opnieuw op te starten. Zie voor meer informatie over het gebruik van de actie voor het opnieuw opstarten van het apparaat [Apparaten op afstand opnieuw opstarten met Intune](device-restart.md).

> [!Note]  
> Deze opdracht vereist toegangsrechten tot apparaten onder supervisie en **Apparaatvergrendeling**. Het apparaat wordt onmiddellijk opnieuw opgestart. Met een toegangscode vergrendelde iOS-apparaten wordt niet opnieuw verbonden met een Wi-Fi-netwerk na opnieuw te zijn opgestart; na opnieuw te zijn opgestart kunnen deze mogelijk niet communiceren met de server.

### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Beheerde macOS-apparaten op afstand vergrendelen met Intune<!-- 1437691 -->
U kunt een verloren Mac OS-apparaat vergrendelen en een 6-cijferige pincode voor wachtwoordherstel instellen. Als het apparaat is vergrendeld, toont de blade **Apparaatoverzicht** de pincode totdat een andere apparaatactie wordt verzonden.

Zie voor meer informatie [Beheerde apparaten op afstand vergrendelen met Intune](device-remote-lock.md).

### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings------1455974-----"></a>Frequentie-instellingen van rapporten van Windows Defender Advanced Threat Protection <!--- 1455974  --->
Met de service Windows Defender Advanced Threat Protection (WDATP) kunnen beheerders de rapportagefrequentie voor beheerde apparaten beheren. Met de nieuwe optie **Frequentie van telemetrierapporten versnellen** verzamelt vaker WDATP gegevens en beoordeelt vaker risico's. De standaardwaarde voor rapportage zorgt voor optimale snelheid en prestaties. Het verhogen van de rapportagefrequentie kan waardevol zijn voor apparaten met een hoog risico. Deze instelling kunt u vinden in het **Windows Defender ATP**-profiel in **Apparaatconfiguraties**.

### <a name="assignment-conflict-resolution-has-changed-for-ios-store-apps----1480316---"></a>Toewijzing van conflictoplossing is gewijzigd voor iOS Store-apps <!-- 1480316 -->
Eindgebruikers kunnen een wijziging ervaren in de beschikbaarheid van iOS Store-apps. Op dit moment wordt een app die is toegewezen aan twee groepen met een conflict tussen **Vereist en Beschikbaar** en **Niet van toepassing** omgezet naar **Vereist en Beschikbaar**. Met de wijziging wordt een app die dit conflict ondervindt, omgezet naar **Niet van toepassing**.

De wijziging doet iets aan de verwarring wanneer één app is toegewezen aan meerdere groepen met verschillende app-intents.

Als u graag wilt dat uw app beschikbaar wordt in de portal voor informatiemedewerkers en het bedrijfsportal vóór de servicerelease van november, hebt u twee opties:

1. Verwijder de toewijzing **Niet van toepassing** voor uw groep.
2. Maak een nieuwe groep die geen leden bevat met een toegewezen intent **Vereist en Beschikbaar** en wijs die groep aan als **Niet van toepassing**.

Zie [Apps aan groepen toewijzen met Microsoft Intune](apps-deploy.md) voor meer informatie.

> [!Note]
> Na de release kunt u de toewijzingen van Mobile Device Management (MDM)-apps niet meer weergeven of wijzigen in de klassieke Intune-console. U kunt echter met de Azure-console of de Graph API van Intune toewijzingen van uw app maken.

### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731---"></a>Android for Work-apparaten onafhankelijk van de Android-apparaten beheren<!-- 1490731 -->
Intune ondersteunt het inschrijvingsbeheer voor Android for Work-apparaten onafhankelijk van het Android-platform. Deze instellingen worden beheerd onder **Apparaatinschrijving** > **Inschrijvingsbeperkingen** > **Apparaattypebeperkingen**. (Ze bevonden zich eerder onder **Apparaatinschrijving** > **Android for Work-inschrijving** > **Android for Work-inschrijvingsinstellingen**.)

Standaard zijn instellingen voor uw Android for Work-apparaten gelijk aan de instellingen voor uw Android-apparaten. Wanneer u echter uw Android for Work-instellingen wijzigt, is dat niet meer het geval.
 
Als u een persoonlijke Android for Work-inschrijving blokkeert, kunnen alleen zakelijke Android-apparaten worden ingeschreven als Android for Work.

Bedenk het volgende wanneer u met de nieuwe instellingen werkt:

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

De implementatie van deze wijzigingen gaat van start bij de update van november, maar de uitvoering ervan voor uw account kan nog wel even duren. U ontvangt een bevestigingsbericht in de Office 365-portal wanneer deze wijzigingen voor uw account van kracht zijn.

### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors----1528104---"></a>Ondersteuning voor meerdere connectors voor de Network Device Enrollment-service (NDES)<!-- 1528104 -->
Met de NDES kunnen mobiele apparaten die zonder domeinreferenties worden uitgevoerd certificaten verkrijgen op basis van het Simple Certificate Enrollment Protocol (SCEP). Dankzij deze update worden meerdere NDES-connectors ondersteund.

### <a name="new-scep-profile-details-supported----1559808---"></a>Nieuwe SCEP-profielgegevens ondersteund<!-- 1559808 -->
Beheerders kunnen aanvullende instellingen configureren bij het maken van een SCEP-profiel op Windows-, iOS-, Mac OS- en Android-platformen.  Beheerders kunnen het IMEI-nummer, het serienummer of de algemene naam met inbegrip van e-mail in de indeling van de onderwerpnaam instellen.

### <a name="configure-an-ios-app-pin----1586774---"></a>Een pincode voor een iOS-app configureren <!-- 1586774 -->
U kunt binnenkort een pincode vereisen voor de betreffende iOS-apps. U kunt de vereisten voor de pincode en de vervaldatum in dagen via Azure Portal configureren. Indien vereist,wordt een gebruiker verplicht om een nieuwe pincode in te stellen en te gebruiken voordat deze toegang krijgt tot een iOS-app. Alleen iOS-apps met een app-beveiliging die is ingeschakeld met de Intune App SDK ondersteunen deze functie.

### <a name="retain-data-during-a-factory-reset-----1588489---"></a>Gegevens behouden tijdens fabrieksinstellingen terugzetten <!-- 1588489 -->
We voegen ondersteuning toe voor een nieuwe functionaliteit voor Windows 	Fabrieksinstellingen terugzetten. Beheerders kunnen nu opgeven of apparaatinschrijving en andere ingerichte gegevens worden bewaard op een apparaat via fabrieksinstellingen terugzetten. 
 
De volgende gegevens wordt behouden via fabrieksinstellingen terugzetten:
- Gebruikersaccounts die zijn gekoppeld aan het apparaat
- Status van de machine (lid van domein, AADJ)
- MDM-inschrijving
- Door OEM geïnstalleerde apps (Store- en Win32-apps)
- Gebruikersprofiel
- Gebruikersgegevens buiten het gebruikersprofiel
- Autologon gebruiker
 
De volgende gegevens blijven niet behouden:
- Gebruikersbestanden
- Door de gebruiker geïnstalleerde apps (Store- en Win32-apps)
- Niet-standaard apparaatinstellingen 

### <a name="app-install-status-report-now-a-bar-chart----1249446---"></a>Statusrapport app-installatie is nu een staafdiagram <!-- 1249446 -->  
Het **Statusrapport van de app-installatie** is toegankelijk voor elke app via de **App**-lijst in de **Mobiele apps**-workload wordt binnenkort weergegeven als een staafdiagram.

### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Mijn iPhone vinden toevoegen voor privéapparaten<!--1427287-->
U kunt bekijken of bij iOS-apparaten Activeringsslot is ingeschakeld. Deze functie was eerder te vinden in de klassieke portal in Intune.

### <a name="group-assigned-enrollment-restrictions----747598---"></a>Beperkingen aan groepen toegewezen inschrijving <!-- 747598 -->
Als Intune-beheerder kunt u de aangepaste inschrijvingsbeperkingen Apparaattype en Apparaatlimiet maken voor gebruikersgroepen.
 
Met de Intune Azure Portal kunt u maximaal 25 exemplaren van elk beperkingstype maken die vervolgens kunnen worden toegewezen aan gebruikersgroepen. Aan groepen toegewezen beperkingen overschrijven de standaardbeperkingen.
 
Alle exemplaren van een beperkingstype worden bijgehouden in een strikt geordende lijst. Deze volgorde bepaalt een prioriteitswaarde voor conflictoplossing. Een gebruiker die getroffen is door meer dan één beperkingsexemplaar wordt alleen beperkt door het exemplaar met de hoogste prioriteitswaarde. U kunt de prioriteit van een bepaald exemplaar wijzigen door dit naar een andere positie in de lijst te slepen. 
 
Deze functionaliteit wordt vrijgegeven met de migratie van Android for Work-instellingen van het menu Android for Work-inschrijving naar het menu Inschrijvingsbeperkingen. Aangezien deze migratie enkele dagen kan duren, kan uw account worden bijgewerkt ten aanzien van andere onderdelen van de release van november voordat u ziet dat groepstoewijzing wordt ingeschakeld voor Inschrijvingsbeperkingen.

### <a name="windows-10-update-ring-assignments-are-displayed----1621837---"></a>Er worden toewijzingen voor de Windows 10-updatering weergegeven <!-- 1621837 -->
Wanneer u bezig bent met de **probleemoplossing** voor de door u weergegeven gebruiker, kunt u eventuele toewijzingen voor de Windows 10-updatering zien.  



<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Azure Active Directory-websites kunnen de Intune Managed Browser-app vereisen en ondersteunen eenmalige aanmelding voor de Managed Browser (openbare preview) <!-- 710595 -->   
Met Azure Active Directory (Azure AD) kunt u de toegang tot websites op mobiele apparaten beperken tot de Intune Managed Browser-app. In de Managed Browser blijven websitegegevens veilig en gescheiden van de persoonlijke gegevens van eindgebruikers. Daarnaast ondersteunt de Managed Browser eenmalige aanmelding voor sites die door Azure AD worden beveiligd. Door u aan te melden bij de Managed Browser of door de Managed Browser op een apparaat te gebruiken met een andere app die door Intune wordt beheerd, krijgt de Managed Browser toegang tot bedrijfssites die door Azure AD worden beveiligd, zonder dat de gebruiker referenties hoeft in te voeren. Deze functionaliteit is van toepassing op sites zoals Outlook Web Access (OWA) en SharePoint Online, evenals andere bedrijfssites zoals intranetbronnen die via de Azure App Proxy worden geopend.

### <a name="troubleshoot-enrollment-issues------746324----"></a>Inschrijvingsproblemen oplossen <!--- 746324 --->  
De werkruimte Problemen oplossen toont problemen met gebruikersinschrijving. Details over het probleem en voorgestelde herstelstappen kunnen beheerders en helpdeskmedewerkers helpen problemen op te lossen. Bepaalde inschrijvingsproblemen worden niet vastgelegd en voor sommige fouten zijn er misschien geen herstelvoorstellen.


















<!-- the following are present prior to 1710 -->



### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Ondersteuning voor het editie-upgradebeleid voor Windows 10   <!-- 903672(archived), 1119689 -->  
U kunt een editie-upgradebeleid voor Windows 10 maken dat Windows 10-apparaten upgradet naar Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education en Windows 10 Professional Education N. Raadpleeg [Editie-upgrades voor Windows 10 configureren](edition-upgrade-configure-windows-10.md) voor meer informatie over editie-upgrades voor Windows 10.




<!-- the following are present prior to 1709 -->



### <a name="android-for-work-support-for-lookout----1087312---"></a>Android for Work-ondersteuning voor Lookout <!-- 1087312 -->   
De Intune-connector met Lookout biedt ondersteuning voor Android for Work-apparaten wanneer u de Lookout voor Work-app gebruikt. U kunt de Lookout-app binnen of buiten de container implementeren.

### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Hulpmiddelen voor Intune-app-beveiliging en Citrix MDX <!-- 709185 -->
U kunt apparaten en apps beheren met een combinatie van Citrix XenMobile MDX en Microsoft Intune. Hierdoor kunt u apps beheren met het Intune-beveiligingsbeleid voor apps met behulp van de mVPN-technologie van Citrix.

U kunt een opslagplaats voor codes vinden met de Intune App Wrapping Tool en Intune App SDK voor iOS en Android, die integreren met Citrix MDX mVPN-technologie.


### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Hoge beschikbaarheid van on-premises Exchange Connector  <!-- 676614 -->   
U kunt meerdere CAS-rollen (Client Access Server) instellen voor on-premises Exchange Connector. Als de hoofd-CA bijvoorbeeld uitvalt, ontvangt Exchange Connector een query om over te schakelen naar een andere CAS. Deze functie zorgt ervoor dat de service niet wordt onderbroken.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Management pack van System Center Operations Manager voor Exchange Connector <!-- 885457 -->   
Het management pack van System Center Operations Manager voor Exchange Connector kunt u gebruiken om de logboeken van Exchange Connector te parseren. Met dit management pack kunt u Intune op verschillende manieren controleren wanneer u problemen moet oplossen.





## <a name="intune-apps"></a>Intune-apps

### <a name="helping-your-users-help-themselves-with-the-company-portal-app-for-android----1573324-1573150-1558616-1564878---"></a>Uw gebruikers helpen om zichzelf te redden met de bedrijfsportal-app voor Android<!---1573324, 1573150, 1558616, 1564878--->
De bedrijfsportal-app voor Android voegt aanwijzingen toe, zodat eindgebruikers meer inzicht krijgen en, waar mogelijk, nieuwe gebruikssituaties zelf oplossen. 

- Er wordt een nieuw bericht weergegeven waarin wordt uitgelegd dat een nalevingsbeleid voor versleuteling is geïmplementeerd, maar de [fabrikant van het apparaat versleutelt het apparaat niet](/intune-user-help/your-device-appears-encrypted-but-cp-says-otherwise-android) volgens [de door Google aanbevolen richtlijnen] (https://developer.android.com/reference/android/app/admin/DevicePolicyManager.html#setStorageEncryption(android.content.ComponentName, boolean).
- Eindgebruikers worden naar de (Azure Active Directory-portal) geleid [https://account.activedirectory.windowsazure.com/r/#/profile] om een apparaat verwijderen als zij het maximum aantal apparaten hebben bereikt dat ze mogen toevoegen. 
- Eindgebruikers krijgen een stapsgewijze instructie om hen te helpen [foutmeldingen bij de activering van Samsung KNOX-apparaten op te lossen](https://go.microsoft.com/fwlink/?linkid=859718) of [de energiebesparende modus uit te schakelen](/intune-user-help/power-saving-mode-android). Als geen van deze oplossingen het probleem verhelpt, krijgt u een uitleg over het verzenden van [logboeken naar Microsoft](/intune-user-help/send-logs-to-microsoft-ios). 


### <a name="new-resolve-action-available-for-android-devices----1583480---"></a>Nieuwe actie 'Oplossen' beschikbaar voor Android-apparaten<!---1583480--->
De bedrijfsportal-app voor Android introduceert een actie 'Oplossen' op de pagina _Apparaatinstellingen bijwerken_. Als de eindgebruiker deze optie selecteert, komt deze rechtstreeks bij de instelling terecht die de oorzaak ervan is dat hun apparaat niet compatibel is. De bedrijfsportal-app voor Android ondersteunt momenteel deze actie ten aanzien van de instellingen [Toegangscode](/intune-user-help/set-your-pin-or-password-android), [Apparaatversleuteling](/intune-user-help/encrypt-your-device-android), [USB-foutopsporing](/intune-user-help/you-need-to-turn-off-usb-debugging-android) en [Onbekende bronnen](/intune-user-help/you-need-to-turn-off-unknown-sources-android). 




<!-- the following are present prior to 1711 -->


### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a>MacOS-gebruikers omleiden naar onze nieuwe bedrijfsportal-app <!--1380728-->   
Wanneer eindgebruikers zich aanmelden bij de bedrijfsportalwebsite om hun macOS-apparaten in te schrijven, worden ze gevraagd de nieuwe bedrijfsportal-app voor macOS te downloaden om het proces te voltooien. Dit gebeurt voor macOS-apparaten waarop OS X El Capitan 10.11 of hoger wordt uitgevoerd. 


<!-- the following are present prior to 1710 -->



### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Apps die met of zonder inschrijving beschikbaar zijn, kunnen nu worden geïnstalleerd zonder dat er om inschrijving wordt gevraagd. <!-- 1334712 -->
Bedrijfs-apps die met of zonder inschrijving beschikbaar zijn gemaakt in de bedrijfsportal-app voor Android kunnen worden geïnstalleerd zonder dat er om inschrijving wordt gevraagd.


<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Ondersteuning van Intune Managed Browser voor iOS en Android <!-- 1374196 -->
Vanaf oktober 2017 ondersteunt de app Intune Managed Browser voor Android alleen nog apparaten waarop Android 4.4 en hoger wordt uitgevoerd. De app Intune Managed Browser voor iOS ondersteunt alleen apparaten met iOS 9.0 en hoger. Oudere versies van Android en iOS kunnen Managed Browser nog steeds gebruiken, maar er kunnen geen nieuwe versies van de app op worden geïnstalleerd en kan er dus geen gebruik worden gemaakt van alle mogelijkheden van de app. U wordt aangeraden deze apparaten bij te werken tot een ondersteunde versie van het besturingssysteem.


### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Verbeterd foutbericht als een gebruiker het maximum aantal apparaten bereikt dat mag worden ingeschreven <!-- 1270370 -->
In plaats van een algemeen foutbericht krijgen eindgebruikers een gebruikersvriendelijk foutbericht te zien waarop een actie kan worden uitgevoerd: 'U hebt het maximum aantal apparaten ingeschreven dat door de IT-beheerder is toegestaan. Verwijder een ingeschreven apparaat of vraag assistentie van uw IT-beheerder.'




## <a name="notices"></a>Mededelingen

Er zijn geen actieve meldingen op dit moment.




### <a name="see-also"></a>Zie tevens
Zie [Wat is er nieuw in Microsoft Intune?](whats-new.md) voor meer informatie over recente ontwikkelingen.
