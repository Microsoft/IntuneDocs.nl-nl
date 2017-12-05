---
title: Vroege editie
description: 
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 11/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1ea734e83cfab3fff22c775764ac9814012d52b6
ms.sourcegitcommit: 70dc0aaad51b447e173b663d1092d993dc81ffdd
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/02/2017
---
# <a name="the-early-edition-for-microsoft-intune---december-2017"></a>De vroege editie voor Microsoft Intune - december 2017

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

### <a name="app-protection-policies-----679615---"></a>Beleid voor app-beveiliging <!-- 679615 -->
Via het beveiligingsbeleid voor Intune-apps kunt u algemene standaardbeleidsregels maken om snel beveiliging in te schakelen voor alle gebruikers in de gehele tenant.

### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>Apps uit het volume-aankoopprogramma voor iOS intrekken <!-- 820863 -->
Voor een bepaald apparaat met een of meer iOS-apps uit het volume-aankoopprogramma (VPP) kunt u de gekoppelde apparaatgebaseerde app-licentie voor het apparaat intrekken. Als u een app-licentie intrekt, wordt de desbetreffende VPP-app niet van het apparaat verwijderd. Als u een VPP-app wilt verwijderen, moet u de toewijzingsactie wijzigen in **Verwijderen**. Zie [iOS-apps beheren die zijn aangeschaft via een volume-aankoopprogramma met Microsoft Intune](vpp-apps-ios.md) voor meer informatie.

### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>Licenties intrekken voor een token van het iOS-volume-aanschafprogramma<!-- 820870 -->
U kunt de licentie van alle iOS-apps uit het volume-aanschafprogramma (VPP) voor een bepaalde VPP-token intrekken.

### <a name="delete-an-ios--volume-purchasing-program-token----820879---"></a>Een token van het iOS-volume-aanschafprogramma verwijderen <!-- 820879 -->
U kunt de token van het iOS-volume-aanschafprogramma (VPP) verwijderen via de console. Dit kan nodig zijn als er dubbele exemplaren van een VPP-token zijn.

### <a name="network-access-control-nac-device-check-in-reporting-----1232250---"></a>Rapportage over inchecken van NAC-apparaten (netwerktoegangsbeheer) <!-- 1232250 -->
Vóór deze wijziging konden IT-beheerders niet vanaf de Intune-kant bepalen of een via NAC beheerd apparaat communiceerde met hun NAC-oplossing. Wanneer een via NAC beheerd apparaat niet communiceert met de NAC-oplossing, wordt het apparaat door de NAC-oplossing beschouwd als niet-compatibel en daarom geblokkeerd door de NAC-oplossing zelf. Vervolgens wordt het apparaat geblokkeerd door beleid voor voorwaardelijke toegang dat is gebaseerd op de nalevingsstatus van het apparaat.

Met deze wijziging kunnen IT-beheerders zien welke via NAC beheerde apparaten succesvol hebben gecommuniceerd met hun NAC-oplossing. Deze nieuwe mogelijkheid bestaat uit twee nieuwe controlefuncties in de werkbelasting voor apparaatnaleving in Intune, waarvan de statistieken hieronder worden weergegeven:
- **Gemiddelde NAC-aanroepen in het afgelopen uur**
- **Laatste binnenkomende NAC-aanvraag (datum/tijd)**

### <a name="new-ios-device-action------1244701---"></a>Nieuwe actie voor iOS-apparaten <!-- 1244701 -->
U kunt door iOS 10.3 gecontroleerde apparaten afsluiten. Deze actie sluit het apparaat direct af zonder waarschuwing voor de eindgebruiker. U vindt de actie **Afsluiten (alleen gecontroleerd)** in de apparaateigenschappen wanneer u een apparaat selecteert in de werkbelasting **Apparaat**.

### <a name="palo-alto-vpn-now-supported----1333680-eeready---"></a>Palo Alto-VPN wordt nu ondersteund <!-- 1333680 eeready -->
De lijst **Verbindingstype** bevat nu de Palo Alto-VPN wanneer u uw basis-VPN configureert.

### <a name="multiple-connector-support-for-scep-and-pfx-certificate-handling----1361755-eeready---"></a>Ondersteuning voor meerdere connectoren voor het verwerken van SCEP- en PFX-certificaten <!-- 1361755 eeready -->
Klanten die de on-premises NDES-connector gebruiken om certificaten aan apparaten te leveren, kunnen nu meerdere connectoren in één tenant configureren.

Deze nieuwe mogelijkheid biedt ondersteuning voor het volgende scenario:

- **Hoge beschikbaarheid**

    Elke NDES-connector haalt certificaataanvragen uit Intune op.  Als één NDES-connector offline gaat, kan de andere connector aanvragen blijven verwerken.

### <a name="new-automatic-redeployment-setting----1469168---"></a>Nieuwe instelling voor automatisch opnieuw implementeren <!-- 1469168 -->
Deze instelling maakt het mogelijk dat gebruikers met beheerdersrechten alle gebruikersgegevens en -instellingen verwijderen met **CTRL + Win + R** op het vergrendelingsscherm van het apparaat. Het apparaat wordt automatisch opnieuw geconfigureerd en opnieuw ingeschreven bij het beheer.

U vindt deze instelling onder Windows 10 -> Apparaatbeperkingen -> Algemeen -> Automatisch opnieuw installeren.

### <a name="install-office-apps-on-macos-devices----1494311---"></a>Office-apps installeren op macOS-apparaten <!-- 1494311 -->
U kunt Office-apps installeren op macOS-apparaten. Met dit nieuwe app-type kunt u Word, Excel, PowerPoint, Outlook en OneNote installeren. Deze apps worden ook geleverd met Microsoft AutoUpdater (MAU) om te zorgen dat uw apps veilig en up-to-date blijven.

### <a name="surface-hub-resource-account-supported----1566442-eeready---"></a>Resource-account voor Surface Hub ondersteund <!-- 1566442 eeready -->
Een nieuwe apparaatactie wordt toegevoegd, zodat beheerders het resource-account dat is gekoppeld aan een Surface Hub, kunnen definiëren en bijwerken.

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

   - **E-mailadres**    
     Het e-mailadres van het apparaat-/resource-account.

   - **Exchange-server**    
     Alleen vereist wanneer automatische detectie mislukt.

   - **Agendasynchronisatie**    
     Hiermee geeft u op of agendasynchronisatie en andere Exchange Server-services zijn ingeschakeld. Bijvoorbeeld: synchronisatie van vergaderingen.

### <a name="intune-now-provides-the-account-move-operation-----1573558-1579830---"></a>Intune biedt nu de bewerking Account verplaatsen <!-- 1573558, 1579830 -->
**Account verplaatsen** migreert een tenant van de ene ASU (Azure Scale Unit) naar een andere. **Account verplaatsen** kan worden gebruikt voor door de klant geïnitieerde scenario's, wanneer u het Intune-ondersteuningsteam belt om dit aan te vragen en in een door Microsoft aangestuurd scenario waarin Microsoft aan de back-end wijzigingen moet aanbrengen in de service. Tijdens de **accountverplaatsing** wordt voor de tenant de modus alleen-lezen (ROM) geactiveerd. Servicebewerkingen zoals inschrijven, de naam van apparaten wijzigen of de nalevingsstatus bijwerken mislukken tijdens de ROM-periode.

### <a name="new-windows-defender-security-center-wdsc-device-configuration-profile-settings----1335507---"></a>Nieuwe profielinstellingen voor apparaatconfiguratie voor Windows Defender Security Center (WDSC) <!-- 1335507 -->
Intune voegt een nieuwe sectie toe in de profielinstellingen voor apparaatconfiguratie onder de eindpuntbeveiliging genaamd **Windows Defender Security Center**. IT-beheerders kunnen configureren tot welke onderdelen van de Windows Defender Security Center-app eindgebruikers toegang hebben. Als een IT-beheerder een onderdeel verbergt in de Windows Defender Security Center-app, worden alle meldingen die betrekking hebben op het verborgen onderdeel, niet weergeven op het apparaat van de gebruiker.

De volgende onderdelen kunnen worden verborgen in de profielinstellingen voor apparaatconfiguratie van Windows Defender Security Center:
- Virus- en bedreigingsbeveiliging
- Prestaties en status van apparaat
- Firewall- en netwerkbeveiliging
- App- en browserbeheer
- Gezinsopties

IT-beheerders kunnen ook aanpassen welke meldingen gebruikers ontvangen. U kunt bijvoorbeeld configureren of de gebruikers alle meldingen ontvangen die worden gegenereerd door zichtbare onderdelen in het WDSC of alleen kritieke meldingen. Niet-kritieke meldingen zijn bijvoorbeeld periodieke samenvattingen van Windows Defender Antivirus-activiteiten en meldingen wanneer scans zijn voltooid. Alle andere meldingen worden beschouwd als kritiek. Daarnaast kunt u ook de inhoud van meldingen zelf aanpassen. U kunt bijvoorbeeld contactgegevens van de IT-afdeling toevoegen aan meldingen die worden weergegeven op apparaten van gebruikers.




<!-- the following are present prior to 1712 -->
### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Mobiele apps van Office 365 toewijzen aan iOS- en Android-apparaten met behulp van de ingebouwde app-type<!-- 1332318 -->
Het **ingebouwde** app-type maakt het eenvoudiger voor u om Office 365-apps te maken en toe te wijzen aan door u beheerde iOS- en Android-apparaten. Deze apps zijn onder andere 0365-apps, zoals Word, Excel, PowerPoint en OneDrive. U kunt specifieke apps toewijzen aan het app-type en de configuratie van de app-gegevens bewerken.

### <a name="single-sign-on-support-for-ios----1333645---"></a>Ondersteuning voor Eenmalige aanmelding voor iOS<!-- 1333645 -->  
U kunt Eenmalige aanmelding voor iOS-gebruikers gebruiken. De iOS-apps die zijn gecodeerd om naar de gebruikersreferenties te zoeken in de Eenmalige aanmelding-payload zijn functioneel voor de update van de payloadconfiguratie. U kunt ook de UPN en de Intune-apparaat-id gebruiken om de Principal-naam en de Realm te configureren.

### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Tekstprotocol toegestaan vanuit beheerde Apps<!-- 1414050  -->
Met apps die worden beheerd door de Intune App SDK kunnen SMS-berichten worden verzonden.

### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Beheerde macOS-apparaten op afstand vergrendelen met Intune<!-- 1437691 -->
U kunt een verloren Mac OS-apparaat vergrendelen en een 6-cijferige pincode voor wachtwoordherstel instellen. Als het apparaat is vergrendeld, toont de blade **Apparaatoverzicht** de pincode totdat een andere apparaatactie wordt verzonden.

Zie voor meer informatie [Beheerde apparaten op afstand vergrendelen met Intune](device-remote-lock.md).


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


### <a name="configure-an-ios-app-pin----1586774---"></a>Een pincode voor een iOS-app configureren <!-- 1586774 -->
U kunt binnenkort een pincode vereisen voor de betreffende iOS-apps. U kunt de vereisten voor de pincode en de vervaldatum in dagen via Azure Portal configureren. Indien vereist,wordt een gebruiker verplicht om een nieuwe pincode in te stellen en te gebruiken voordat deze toegang krijgt tot een iOS-app. Alleen iOS-apps met een app-beveiliging die is ingeschakeld met de Intune App SDK ondersteunen deze functie.

### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Mijn iPhone vinden toevoegen voor privéapparaten<!--1427287-->
U kunt bekijken of bij iOS-apparaten Activeringsslot is ingeschakeld. Deze functie was eerder te vinden in de klassieke portal in Intune.

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Azure Active Directory-websites kunnen de Intune Managed Browser-app vereisen en ondersteunen eenmalige aanmelding voor de Managed Browser (openbare preview) <!-- 710595 -->   
Met Azure Active Directory (Azure AD) kunt u de toegang tot websites op mobiele apparaten beperken tot de Intune Managed Browser-app. In de Managed Browser blijven websitegegevens veilig en gescheiden van de persoonlijke gegevens van eindgebruikers. Daarnaast ondersteunt de Managed Browser eenmalige aanmelding voor sites die door Azure AD worden beveiligd. Door u aan te melden bij de Managed Browser of door de Managed Browser op een apparaat te gebruiken met een andere app die door Intune wordt beheerd, krijgt de Managed Browser toegang tot bedrijfssites die door Azure AD worden beveiligd, zonder dat de gebruiker referenties hoeft in te voeren. Deze functionaliteit is van toepassing op sites zoals Outlook Web Access (OWA) en SharePoint Online, evenals andere bedrijfssites zoals intranetbronnen die via de Azure App Proxy worden geopend.


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
