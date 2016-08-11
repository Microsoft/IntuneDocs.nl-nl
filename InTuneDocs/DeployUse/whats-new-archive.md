---
title: Wat is er nieuw? | Microsoft Intune
description: 
keywords: 
author: Lindavr
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 300df17fd5844589a1e81552d2d590aee5615897
ms.openlocfilehash: 458ee268d0c6a8fa6cbe6cc23ad07f0e45eff3e5


---
## December 2015
### Wijzigingen en updates voor de Microsoft-bedrijfsportal
In deze versie zijn de volgende wijzigingen aangebracht aan de bedrijfsportal.

**Android-bedrijfsportal-app**

De volgende wijzigingen zijn aangebracht om te voldoen aan nieuwe Google-vereisten. Op apparaten met Android 6.0 en hoger worden twee nieuwe berichten weergegeven voor gebruikers:
* De bedrijfsportal toestaan telefoongesprekken uit te voeren en beheren?
* De bedrijfsportal toegang verlenen tot foto's, media en bestanden op uw apparaat?

Zie de volgende tabellen voor meer informatie over deze twee berichten.



Berichttekst  |De bedrijfsportal toestaan telefoongesprekken uit te voeren en beheren?  
---------|---------
Betekenis van het bericht     |  Het telefoonnummer en het IMEI-nummer van het apparaat van de gebruiker kunnen naar de Intune-service worden verzonden en worden weergegeven in de beheerconsole op de pagina Hardware.   </br></br>**OPMERKING: de bedrijfsportal-app voert nooit telefoongesprekken uit en beheert deze niet.** De berichttekst wordt beheerd door Google en kan niet worden gewijzigd. </br></br>Als u de pagina **Hardware** wilt weergeven, gaat u naar **Groepen** > **Alle mobiele apparaten** > **Apparaten**. Selecteer het apparaat van de gebruiker en ga naar **Eigenschappen weergeven** > **Hardware**.    
Waar en wanneer het bericht wordt weergegeven  | Het bericht wordt weergegeven wanneer gebruikers zich voor het eerst aanmelden bij de bedrijfsportal-app om hun apparaat in te schrijven.|         
Wat er gebeurt als gebruikers toegang toestaan  |  Het telefoonnummer en het IMEI-nummer van het apparaat worden weergegeven op de pagina Hardware page in de beheerconsole. |         
Wat er gebeurt als gebruikers toegang weigeren     | Gebruikers kunnen de bedrijfsportal-app blijven gebruiken en hun apparaten inschrijven, maar het telefoonnummer en het IMEI-nummer van het apparaat van de gebruikers zijn leeg op de pagina Hardware in de beheerconsole.       </br></br> De tweede keer dat gebruikers zich aanmelden bij de bedrijfsportal-app nadat ze toegang hebben geweigerd, wordt in het bericht een selectievakje bij **Niet opnieuw vragen** weergegeven dat gebruikers kunnen inschakelen zodat het bericht nooit meer wordt weergegeven.</br></br>Als gebruikers toegang verlenen en deze later weer intrekken, wordt het bericht de volgende keer dat gebruikers zich bij de bedrijfsportal-app aanmelden, weergegeven na de registratie.</br></br>Als gebruikers later alsnog besluiten om toegang te verlenen, kunnen ze naar **Instellingen** > **Apps** > **Bedrijfsportal** > **Machtigingen** > **Telefoon** gaan en de machtiging instellen.
Meer informatie     |  Voor uw gebruikers: [aanmelden bij de bedrijfsportal](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_signin_cp)  </br></br>Voor IT-professionals: de informatie in deze tabel bevindt zich ook in [Gebruikers informatie geven over berichten over de bedrijfsportal-app](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs)   

Berichttekst  |De bedrijfsportal toegang verlenen tot foto's, media en bestanden op uw apparaat?  
---------|---------
Betekenis van het bericht     |  Het apparaat kan gegevenslogboeken schrijven naar de SD-kaart van het apparaat waardoor logboeken kunnen worden verplaatst via een USB-kabel.   </br></br>**OPMERKING: de bedrijfsportal-app gebruikt nooit foto's, media en bestanden van de gebruiker.** De berichttekst wordt beheerd door Google en kan niet worden gewijzigd.     
Waar en wanneer het bericht wordt weergegeven  | Het bericht wordt weergegeven wanneer gebruikers op **Gegevens verzenden** tikken om gegevenslogboeken te verzenden naar de IT-beheerder.|         
Wat er gebeurt als gebruikers toegang toestaan  |  De logboeken worden gekopieerd naar de SD-kaart. |         
Wat er gebeurt als gebruikers toegang weigeren     | Ze kunnen nog steeds gegevenslogboeken verzenden, maar de logboeken worden niet gekopieerd naar de SD-kaart van het apparaat.       </br></br> De tweede keer dat gebruikers zich aanmelden bij de bedrijfsportal-app nadat ze toegang hebben geweigerd, wordt in het bericht een selectievakje bij **Niet opnieuw vragen** weergegeven dat gebruikers kunnen inschakelen zodat het bericht nooit meer wordt weergegeven.</br></br>Als gebruikers toegang verlenen en deze later weer intrekken, wordt het bericht de volgende keer dat ze logboeken verzenden weergegeven.</br></br>Als gebruikers later alsnog besluiten om toegang te verlenen, kunnen ze naar **Instellingen** > **Apps** > **Bedrijfsportal** > **Machtigingen** > **Opslag** gaan en de machtiging instellen.
Meer informatie     |  Voor uw gebruikers: [logboeken met diagnostische gegevens naar de IT-beheerder verzenden via e-mail](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_send_diag_logs)  </br></br>Voor IT-professionals: de informatie in deze tabel bevindt zich ook in [Gebruikers informatie geven over berichten over de bedrijfsportal-app](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs)   


**iOS-bedrijfsportal-app**
* Gebruikers kunnen nu Microsoft Outlook of andere e-mailapps gebruiken om diagnostische logboeken te verzenden naar de IT-beheerder. Eerder kon alleen de systeemeigen app worden gebruikt.
* Ondersteuning voor het Device Enrollment Program (DEP) van Apple en zakelijke ingeschreven apparaten is verbeterd. Zie [U wordt gevraagd uw apparaat te identificeren wanneer u het apparaat probeert te registreren](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_id_your_device) voor meer informatie.
* In de lijst met geregistreerde apparaten van de gebruiker wordt nu een groen vinkje weergegeven naast het apparaat dat momenteel wordt gebruikt door de gebruiker. Voordat dit selectievakje werd toegevoegd, konden gebruikers niet zien welk ingeschreven apparaat ze gebruikten.

**Windows-bedrijfsportal-app**

Microsoft verzamelt automatisch anonieme gegevens over de prestaties en het gebruik van de bedrijfsportal om Microsoft-producten en -services te verbeteren. Eindgebruikers kunnen  het verzamelen van gegevens uitschakelen met de instelling Gebruiksgegevens op hun apparaat. Beheerders hebben geen controle over het verzamelen van deze gegevens en ze kunnen de selectie van de gebruiker voor deze instelling niet wijzigen.



## November 2015
### Appbeheer
Intune ondersteunt Mobile Application Management-beleidsregels (MAM) die helpen te voorkomen dat bedrijfsgegevens uitlekken naar consumenten-apps of -services. Deze beleidsregels zouden normaal alleen worden toegepast op mobiele apps op apparaten die ook bij Intune zijn ingeschreven voor Mobile Device Management (MDM).

In de update van deze maand biedt Intune nieuwe apparaatklassen aanvullende MAM-mogelijkheden. U kunt nu, naast de apparaten die zijn ingeschreven bij Intune, MAM-beleid ook toepassen op:
* apparaten die worden beheerd door een andere MDM-oplossing (Mobile Device Management)
* apparaten die niet zijn ingeschreven bij een apparaatbeheersysteem, meestal BYO-apparaten (Bring Your Own)

U vindt meer informatie over deze nieuwe MAM-mogelijkheden in de volgende blogberichten:
* [Beheerde mobiele productiviteit verbeteren](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)
* [Nieuwe mogelijkheden van Microsoft Enterprise Mobility aangekondigd](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)

Hier volgen bovendien enkele belangrijke functies en aanvullende informatie over de MAM-functies van Intune:
* Bedrijfsgegevens worden geïsoleerd van de consumentgegevens in apps die geschikt zijn voor Intune, waaronder Office Mobile-apps, apps van derden met de Intune-SDK of Line-Of-Business-apps die zijn ingepakt door Intune.
* Bedrijfsgegevens kunnen worden gedeeld (**knippen/kopiëren/plakken**) tussen bedrijfs-apps, terwijl wordt voorkomen dat bedrijfsgegevens worden gedeeld in persoonlijke apps. Lees [Hoe MAM-beleid app-gegevens beschermt](https://technet.microsoft.com/library/mt627825.aspx) voor meer informatie. In dit voorbeeldscenario, waarin [de Microsoft Word-app wordt gebruikt voor het werk en persoonlijke taken](https://technet.microsoft.com/library/mt627827.aspx), ziet u hoe het delen van bedrijfsgegevens met persoonlijke apps wordt voorkomen.
* Beleid ter preventie van het verlies van sleutelgegevens zoals pincodes per app, 'opslaan als'-besturingselementen en beheerd gegevens delen tussen apps. Zie [Beleid voor Mobile App Management maken en implementeren met Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx) voor een lijst met alle beleidsmogelijkheden.
* Word, Excel, PowerPoint, Outlook, OneNote en OneDrive voor Bedrijven hebben deze nieuwe functies en kunnen worden beheerd met en zonder apparaatregistratie. Er zijn systeemeigen mogelijkheden voor preventie van gegevensverlies ingebouwd in de standaard-Office-apps uit App Store en Google Play. Hierbij is er geen noodzaak voor het inpakken van apps of sideloading.
* Zie [Aan de slag met beleid voor het beheer van mobiele apps in Azure Portal](https://technet.microsoft.com/library/mt627830.aspx) voor meer informatie om aan de slag te gaan. Zie [Beleid voor Mobile App Management maken en implementeren met Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx) voor meer informatie over het configureren en implementeren van Mobile App Management-beleid.
* Wanneer eindgebruikers zich in de app verifiëren met hun bedrijfsreferenties, worden de mogelijkheden voor preventie van gegevensverlies automatisch ingesteld. Het onderwerp [Eindgebruikerservaring voor apps die zijn gekoppeld aan MAM-beleid van Microsoft Intune](https://technet.microsoft.com/library/mt627827.aspx) bevat enkele voorbeeldscenario’s over het benaderen van OneDrive op iOS- en Android-apparaten.
* Werkt op iOS- en Android-apparaten.

De lijst met [Microsoft-apps die u met MAM-beleid van Microsoft Intune kunt gebruiken](https://technet.microsoft.com/library/dn708489.aspx) is bijgewerkt met de nieuwste apps.

### Apparaatbeheer
 **Mac OS X-apparaatbeheer** Met Intune kunt u nu Mac OS X-apparaten registreren en beheren. U kunt het volgende doen met uw Mac OS X-apparaten:
* Apparaten registreren om ze te laten beheren door Intune. Zie [iOS- en Mac-beheer instellen met Microsoft Intune](https://technet.microsoft.com/library/dn408185.aspx).
* Apparaatinstellingen beheren met een algemeen configuratiebeleid. Zie [Instellingen voor configuratiebeleid voor Mac OS X in Microsoft Intune](https://technet.microsoft.com/library/mt627823.aspx).
* Mac OS X-instellingen implementeren die u hebt gemaakt met de Apple Configurator. Zie [Aangepaste beleidsinstellingen voor Mac OS X in Microsoft Intune](https://technet.microsoft.com/library/mt627820.aspx).
* Hardware- en software-inventarisaties verzamelen van Mac OS X-apparaten. Zie [Inzicht in uw apparaten met inventarisaties in Microsoft Intune](https://technet.microsoft.com/library/jj733634.aspx).
* Nieuwe rapporten genereren met informatie over de Mac OS X-apparaten die u beheert. Zie [Microsoft Intune-bewerkingen begrijpen met behulp van rapporten](https://technet.microsoft.com/library/dn646977.aspx).

**Nieuwe Edge-browserinstellingen voor Windows 10-apparaten** Er zijn nieuwe instellingen toegevoegd aan het algemene configuratiebeleid van Windows 10 waarmee u instellingen en functies van de Microsoft Edge-browser kunt beheren. Zie [Instellingen voor configuratiebeleid voor Windows 10 in Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx).

**E-mailprofielen** Er is een nieuw beleid voor e-mailprofielen toegevoegd voor apparaten met Windows 10 Desktop en Windows 10 Mobile. Zie [Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](https://technet.microsoft.com/library/dn646984.aspx).

**Nieuwe beleidsinstellingen voor naleving** De volgende nieuwe beveiligings- en systeembeleidsinstellingen zijn toegevoegd aan de lijst met nalevingsbeleidsregels:
* Om ervoor te zorgen dat apparaten met Windows 8.1 of hoger die toegang hebben tot uw bedrijfsbronnen beschikken over de nieuwste updates, gebruikt u de instelling **Automatische updates vereisen**. U kunt ook opgeven welk type updates automatisch moet worden geïnstalleerd, ofwel alle als belangrijk gemarkeerde updates worden geïnstalleerd of alle updates die als belangrijk of aanbevolen zijn gemarkeerd. Zie [Manage device compliance policies for Microsoft Intune](https://technet.microsoft.com/library/dn705843.aspx) (Nalevingsbeleid voor apparaten beheren voor Microsoft Intune) voor de volledige lijst met instellingen voor nalevingsbeleid.
* Met de nieuwe instelling **Wachtwoord vereisen wanneer het apparaat wordt geactiveerd vanuit een niet-actieve status** in combinatie met de bestaande instelling **Minuten van inactiviteit voordat wachtwoord vereist is** kunt u een nalevingsinstelling maken waarbij de eindgebruiker een wachtwoord moet invoeren om een apparaat te gebruiken dat al een bepaalde tijd inactief is.

**Nieuwe beleidsopties voor voorwaardelijke toegang** U kunt beleid voor voorwaardelijke toegang toepassen op **alle gebruikers** in een nieuw of bestaand beleid voor voorwaardelijke toegang. Alle gebruikers met een licentie voor Intune en Office 365 moeten hun apparaten registreren. Als het apparaatplatform niet wordt ondersteund door Intune, wordt de toegang tot clienttoepassingen geblokkeerd via [aanmelding op basis van Active Directory-verificatie (moderne verificatie)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/).

U kunt ook opgeven dat het beleid voor voorwaardelijke toegang van toepassing is op **alle platforms**.  Elke clienttoepassing die gebruikmaakt van [aanmelding op basis van Active Directory-verificatie (moderne verificatie)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/), moet voldoen aan het beleid voor voorwaardelijke toegang. Als het platform niet door Intune wordt ondersteund, wordt het geblokkeerd.

### Wijzigingen en updates voor de Microsoft-bedrijfsportal
In deze release zijn de volgende wijzigingen aangebracht aan de bedrijfsportal-apps:

* **Android**: er is een welkomstscherm toegevoegd aan de Android-bedrijfsportal-app om gebruikers meer inzicht te geven in het doel van de bedrijfsportal-app. Dit scherm is bedoeld om de app alleen beschikbaar te stellen als download voor gebruikers van bedrijven die geen Intune-abonnement hebben.

* **iOS**: Intune ondersteunt nu de registratie van Mac OS X-apparaten via de [bedrijfsportal-website](https://portal.manage.microsoft.com). Zie [Enroll your Mac OS X device in Intune](https://technet.microsoft.com/library/mt598622.aspx) (Uw Mac OS X-apparaat registreren bij Intune) voor instructies.

* **Bedrijfsportal-website**: gebruikers die hun apparaat bij Intune hebben ingeschreven, kunnen nu hun wachtwoordcode opnieuw instellen met de optie **Wachtwoordcode opnieuw instellen** op de bedrijfsportal-website. Eerder konden alleen IT-beheerders de wachtwoordcodes van gebruikers opnieuw instellen. De optie Wachtwoordcode opnieuw instellen wordt niet ondersteund op Windows 8.1- en Windows RT-apparaten. De optie wordt alleen weergegeven wanneer apparaten zijn ingeschreven in Mobile Device Management (MDM) of MDM met Exchange ActiveSync. Zie [Reset your passcode](https://technet.microsoft.com/library/mt590895.aspx) (Uw wachtwoordcode opnieuw instellen) voor instructies.

### Wijzigingen in de licentieverlening voor hoofdbeheerders
In oktober is bekendgemaakt dat hoofdbeheerders (ook wel tenantbeheerders genoemd) de reguliere beheertaken zouden kunnen voortzetten zonder afzonderlijke Intune- of Enterprise Mobility Suite-licentie (ESM). Als hoofdbeheerders echter de service willen gebruiken, bijvoorbeeld om hun eigen apparaat of een bedrijfsapparaat in te schrijven of om de Intune-bedrijfsportal te gebruiken, moeten ze net als anderen beschikken over een Intune- of EMS-licentie. Hieronder vindt u aanvullende informatie.
* In de Intune-bedrijfsportal kunnen eindgebruikers:
    * hun apparaat registreren
    * de status van hun apparaat weergeven
    * software downloaden die een hoofdbeheerder heeft geïmplementeerd voor de organisatie
    * koppelingen zoeken die door de hoofdbeheerder zijn gepubliceerd om contactgegevens van de IT-afdeling te verschaffen

    [Meer informatie over de bedrijfsportal](https://technet.microsoft.com/library/dn646966.aspx#BKMK_CompanyPortal) en [manieren om de bedrijfsportal aan te passen](https://technet.microsoft.com/library/dn646983.aspx#BKMK_ConfigureCompanyPortal).
* De persoon die zich aanmeldt om Intune of EMS te kopen namens een organisatie, wordt automatisch de eerste hoofdbeheerder in de tenant. Sinds deze herfst wijst Intune automatisch een Intune- of EMS-licentie toe aan die eerste hoofdbeheerder, als onderdeel van de overstap op de [Office 365-portal](http://portal.office.com/) en het buiten gebruik stellen van de [Intune-accountportal](http://account.manage.microsoft.com/). Er kunnen zonder afzonderlijke Intune- en EMS-licenties eventueel andere hoofdbeheerders worden toegevoegd voor het dagelijkse beheer. Als er acties worden uitgevoerd als eindgebruiker en wanneer er eigen (of bedrijfs)apparaten worden ingeschreven, of wanneer er software wordt gedownload via de bedrijfsportal, moet er toch een licentie worden aangeschaft, net als voor andere gebruikers het geval is.
* De wijziging wordt gefaseerd geïmplementeerd en is van toepassing vanaf januari 2016.
* Voor Microsoft-partners heeft deze wijziging geen invloed op het vermogen om de service namens klanten te beheren. Voor eindgebruikerstaken moet een gebruiker beschikken over een Intune- of EMS-licentie om een apparaat in te schrijven en software via de bedrijfsportal te openen of downloaden.

Als u vragen hebt over deze wijziging, kunt u contact opnemen met het ondersteuningsteam van Intune:
* [Ondersteuningskanalen voor Microsoft Intune](https://technet.microsoft.com/library/jj839713.aspx)
* [Communityondersteuning](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)

Voor algemene feedback over Microsoft Intune en het rapporteren van ontwerpwijzigingsaanvragen (DCR's) en fouten gaat u naar [Intune UserVoice](https://microsoftintune.uservoice.com/).


### Wat is er nieuw in de Intune-documentatie -- november 2015
**Nieuwe inhoud**
* [Instellingen voor configuratiebeleid voor Mac OS X in Microsoft Intune](https://technet.microsoft.com/library/mt627823.aspx): apparaatinstellingen en functies beheren voor Mac OS X-apparaten.
* [Aangepaste beleidsinstellingen voor Mac OS X in Microsoft Intune](https://technet.microsoft.com/library/mt627820.aspx): Mac OS X-apparaatinstellingen implementeren die u hebt gemaakt met het hulpprogramma Apple Configurator.
* [App-beleid voor het voorkomen van gegevensverlies configureren met Microsoft Intune](https://technet.microsoft.com/library/mt627825.aspx): bevat informatie over de scenario's waarin MAM-beleid (Mobile App Management) wordt ondersteund en hoe het beleid werkt bij het beveiligen van gegevens.
* [Aan de slag met MAM-beleid in de Azure-portal](https://technet.microsoft.com/library/mt627830.aspx): wat u nodig hebt om met Azure Preview Portal aan de slag te gaan voor MAM-beleid.
* [MAM-beleid maken en implementeren met Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx): bevat een stapsgewijs overzicht voor het maken van MAM-beleid in Azure Preview Portal.
* [MAM-beleid bewaken met Microsoft Intune](https://technet.microsoft.com/library/mt627824.aspx): informatie over het bewaken van uw MAM-beleid via Azure Preview Portal.
* [Microsoft Intune MAM-beleid en iOS Open in](https://technet.microsoft.com/library/mt627821.aspx): informatie over hoe MAM-beleid werkt met de functie iOS Open in.
* [Eindgebruikerservaring voor apps die zijn gekoppeld aan het MAM-beleid van Microsoft Intune](https://technet.microsoft.com/library/mt627827.aspx): wat de ervaring voor eindgebruikers is wanneer apps worden gebruikt die zijn gekoppeld aan het MAM-beleid.
* [Bedrijfsgegevens van beheerde apps wissen met Microsoft Intune](https://technet.microsoft.com/library/mt627826.aspx): hoe u gegevens van bedrijfsapps kunt wissen.

**Bijgewerkte inhoud**
* [Instellingen voor configuratiebeleid voor Windows 10 in Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx): er zijn nieuwe Microsoft Edge-browserinstellingen toegevoegd.
* [iOS- en Mac-beheer instellen met Microsoft Intune](http://technet.microsoft.com/library/dn408185.aspx): er is informatie toegevoegd over het registreren van Mac OS X-apparaten.
* [Inzicht in uw apparaten met inventarisaties in Microsoft Intune](https://technet.microsoft.com/library/jj733634.aspx): er is informatie toegevoegd over de inventarisaties die worden verzameld van Mac OS X-apparaten. Het onderwerp met de nieuwste informatie over alle apparaatplatforms is ook bijgewerkt.
* [Microsoft Intune-bewerkingen begrijpen met behulp van rapporten](https://technet.microsoft.com/library/dn646977.aspx): er is informatie toegevoegd over de twee nieuwe rapporten die worden gebruikt om informatie weer te geven over uw beheerde Mac OS X-apparaten.
* [Nalevingsbeleid voor apparaten beheren voor Microsoft Intune](https://technet.microsoft.com/library/dn705843.aspx): er is informatie toegevoegd over het nieuwe nalevingsbeleid voor het vereisen van automatische updates en wachtwoorden wanneer een apparaat wordt geactiveerd vanuit een niet-actieve status.
* [Toegang tot e-mail beheren met Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx): er is informatie toegevoegd over de mogelijkheid om beleid voor voorwaardelijke toegang toe te passen op alle platforms en alle gebruikers.
* [Toegang tot SharePoint Online beheren met Microsoft Intune](https://technet.microsoft.com/library/dn705844.aspx): er is informatie toegevoegd over de mogelijkheid om beleid voor voorwaardelijke toegang toe te passen op alle platforms en alle gebruikers.

## Oktober 2015

### Updates voor voorwaardelijke toegang voor de on-premises Exchange-toepassing
**U kunt nu toegang tot Exchange ActiveSync-e-mail toestaan voor compatibele apparaten die zijn ingeschreven bij Intune wanneer de globale Exchange-regel is ingesteld op blokkeren of in quarantaine plaatsen** Tot nu toe moest de algemene Exchange-regel worden ingesteld op **Toestaan** om e-mailtoegang toe te staan op ingeschreven en compatibele apparaten.

Door deze service-update is deze instelling niet langer een vereiste voor voorwaardelijke toegang. Als uw Exchange-omgeving vereist dat de standaard toegepaste globale regel moet worden ingesteld op **Blokkeren/In quarantaine**, schakelt u gewoon het selectievakje **Standaardregel negeren** in op de pagina met het beleid voor voorwaardelijke toegang tot de on-premises Exchange-toepassing. Het onderwerp [Toegang tot e-mail beheren met Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx) bevat meer informatie over de regels en de daaruit voortkomende meldingen voor de eindgebruikers.

**Nieuwe mogelijkheid om in e-mailberichten in quarantaine met één klik een apparaat in te schrijven**: de registratie vanuit een e-mailbericht in quarantaine is vereenvoudigd en kan nu met één klik worden gedaan. Door deze service-update hoeven eindgebruikers maar op één koppeling in het e-mailbericht in quarantaine te klikken om het apparaat bij de bedrijfsportal-app in te schrijven.
### Updates voor mobiele apparaten en appbeheer
**Android** Alle Intune-beheerfuncties ondersteunen nu Android 6.0 (Marshmallow) zoals is beschreven in dit blogbericht: [Microsoft Intune Provides Day 0 Support for Android Marshmallow](http://blogs.technet.com/b/microsoftintune/archive/2015/10/09/microsoft-intune-to-provide-day-0-support-for-android-marshmallow.aspx).

**iOS** U kunt geen nieuwe apps meer implementeren op iOS-apparaten met een besturingssysteem dat ouder is dan iOS 7.1. Eventuele bestaande geïmplementeerde apps op apparaten met een ouder besturingssysteem dan iOS 7.1 blijven werken en worden beheerd door Intune.

**Windows 10** Intune ondersteunt nu de implementatie van Windows 10 Universal-apps met een software-installatieprogramma van het type **Windows-app-pakket**. Zie [Aan de slag met app-implementatie in Microsoft Intune](http://technet.microsoft.com/en-US/library/dn646955.aspx) voor meer informatie en vereisten.


### Wijzigingen en updates voor Microsoft-bedrijfsportal-apps
De volgende wijzigingen zijn aangebracht aan de bedrijfsportal-apps in deze versie: **iOS** Er zijn nieuwe knoppen toegevoegd aan de bedrijfsportal-app om het gemakkelijker voor gebruikers te maken diagnostische logboeken naar de IT-beheerder te verzenden:

|Naam van de knop|Waar deze wordt weergegeven|
|------------|---------------|
|Rapport|Waarschuwingsberichten bij fouten|
|Diagnostisch rapport verzenden|Het scherm Over van de bedrijfsportal-app|



## September 2015
### Updates voor mobiele apparaten en appbeheer
**Alle Intune iOS-beheerfuncties ondersteunen nu iOS 9** Zie [dit blogbericht](http://blogs.technet.com/b/microsoftintune/archive/2015/09/09/day-zero-support-for-ios-9-with-intune.aspx) voor meer informatie over iOS 9-beheermogelijkheden.

**Nieuw configuratiebeleid voor mobiele apps voor iOS** Gebruik het nieuwe configuratiebeleid voor mobiele apps om automatisch instellingen op te geven die nodig kunnen zijn voor een iOS-app wanneer deze wordt uitgevoerd. U kunt bijvoorbeeld een netwerkpoort of een gebruikersnaam opgeven. Zie [Apps configureren met configuratiebeleid voor mobiele apps in Microsoft Intune](https://technet.microsoft.com/library/mt481447.aspx) voor meer informatie.

**Eenvoudiger app-beheer voor iOS 9-gebruikers**
 In deze release kunt u reeds geïmplementeerde apps onderbrengen bij Intune-beheer voor iOS-9-gebruikers. Voor eerdere versies van iOS geldt dat wanneer u een app implementeert en er op een apparaat al een niet-beheerde versie van de app is geïnstalleerd, u alsnog aan de gebruiker moet vragen om de app handmatig te verwijderen voordat de beheerde app met Intune kan worden geïnstalleerd.

 Vanaf deze versie van Intune kunt u gebruikers van iOS 9-apparaten vragen toestemming te geven aan Intune om het beheer van de app over te nemen en eventuele relevante Mobile Application Management-beleidsregels toe te passen.

 **Windows 10-beheer** Gebruik het nieuwe [algemene configuratiebeleid voor Windows 10](https://technet.microsoft.com/library/mt404697.aspx) om wachtwoord-, apparaat-, browser- en overige instellingen te configureren voor ingeschreven apparaten met Windows 10 en Windows 10 Mobile.

 **Apps maken en implementeren voor ingeschreven Windows 10-apparaten** Met het nieuwe type software-installatieprogramma, Windows Installer via MDM (&#42;.msi), kunt u Windows Installer-apps maken en implementeren op ingeschreven apparaten met Windows 10. Zie [Aan de slag met app-implementatie in Microsoft Intune](https://technet.microsoft.com/library/dn646955.aspx) voor meer informatie.

### Wijzigingen en updates voor Microsoft-bedrijfsportal-apps
In deze release zijn de volgende wijzigingen aangebracht aan de bedrijfsportal-apps:

**iOS**
* Microsoft verzamelt automatisch anonieme gegevens over de prestaties en het gebruik van de bedrijfsportal om Microsoft-producten en -services te verbeteren. Eindgebruikers kunnen  het verzamelen van gegevens uitschakelen met de instelling Gebruiksgegevens op hun apparaat. Beheerders hebben geen controle over het verzamelen van deze gegevens en ze kunnen de selectie van de gebruiker voor deze instelling niet wijzigen.
* Ondersteuning voor volledige schermresolutie op iPhone 6 en 6 Plus
* Oplossingen voor verbeterde beveiliging

### Wat is er nieuw in de Intune-documentatie -- september 2015
**Nieuwe onderwerpen**

|Naam|Details|
|----|--------|
|[Instellingen voor configuratiebeleid voor Windows in Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx)|Dit is een nieuw configuratiebeleid waarmee u instellingen en functies op apparaten met Windows 10 en Windows 10 Mobile beheert.
| [Apps configureren met configuratiebeleid voor mobiele apps in Microsoft Intune](https://technet.microsoft.com/library/mt481447.aspx)|Dit is een nieuw beleidstype waarmee u automatisch instellingen opgeeft die mogelijk vereist zijn wanneer de gebruiker een iOS-app gebruikt. |

**Bijgewerkte onderwerpen**

|Naam|Details|
|----|-------|
|[Beleid gebruiken voor het beheren van computers en mobiele apparaten met Microsoft Intune](https://technet.microsoft.com/library/dn743712.aspx)|Bijgewerkt met de laatste informatie voor een beter inzicht in beleidsregels en ondersteuning bij het maken van deze regels.|

## Augustus 2015
### Updates voor mobiele apparaten en appbeheer
* **Voorwaarden** voor Intune-registratie en bedrijfstoegang worden [nu beheerd via beleidsregels](https://technet.microsoft.com/library/mt405893.aspx). U kunt verschillende sets voorwaarden instellen om te voldoen aan de vereisten voor specifieke gebruikersgroepen. U kunt bijvoorbeeld voorwaarden in verschillende talen implementeren naar geografisch gedefinieerde gebruikersgroepen. U kunt [uw voorwaarden ook bewerken](https://technet.microsoft.com/library/mt405893.aspx#BKMK_TCVers) en opgeven of het versienummer moet worden verhoogd, zodat gebruikers de nieuwe voorwaarden moeten accepteren voordat ze de bedrijfsportal kunnen gebruiken.
* **Een aantal Intune-beleidsregels is hernoemd** zodat ze consistenter zijn binnen het gehele product en eenvoudiger te vinden zijn. Zie [Beleid gebruiken voor het beheren van computers en mobiele apparaten met Microsoft Intune](https://technet.microsoft.com/library/dn743712.aspx) voor een lijst met alle beschikbare Intune-beleidsregels.
* **PKCS #12-certificaatprofielen (.PFX)** zijn beschikbaar voor Android 4.0 of hoger en Windows 10 (desktop en mobiel) en hoger. Voor het gebruik van .PFX is geen NDES-server vereist. Zie [Toegang tot bedrijfsbronnen inschakelen met certificaatprofielen met Microsoft Intune](http://technet.microsoft.com/library/dn818904.aspx) voor meer informatie over het gebruik van .PFX-certificaatprofielen
* **Instellingen van bedrijfsgrenzen voor Windows 10 Desktop en Mobile** maken het gebruik van gedetailleerde VPN-instellingen mogelijk, zoals beschreven in [Gebruikers helpen om verbinding met hun werk te maken met behulp van VPN-profielen met Microsoft Intune](https://technet.microsoft.com/library/dn818905.aspx)
* **De app OneDrive voor Android ondersteunt nu meerdere identiteiten**. Deze en andere updates aan beleidsregels voor het beheer van mobiele apps worden beschreven in de [lijst met Microsoft-toepassingen die u kunt beheren](https://technet.microsoft.com/library/dn708489.aspx).
* **Bypass van iOS-activeringsvergrendeling**. Als iOS-apparaten in bedrijfseigendom worden beschermd door activeringsvergrendeling, moet u de Apple-id en het wachtwoord van de gebruiker invoeren voordat u het apparaat kunt wissen of opnieuw activeren. Dit kan leiden tot problemen wanneer gebruikers het bedrijf verlaten en een apparaat in bedrijfseigendom retourneren zonder de activeringsvergrendeling uit te schakelen. U kunt [Bypass van activeringsvergrendeling voor Intune](https://technet.microsoft.com/library/mt414176.aspx) gebruiken om dit probleem op te lossen

### Voorwaardelijke toegang voor pc’s
U kunt nu voorwaardelijke beleidsregels configureren voor pc's. Hiermee krijgen Office desktopapps toegang tot Exchange Online en SharePoint Online-services.
Om voorwaardelijke beleidsregels voor pc's in te schakelen, moet de pc lid zijn van het domein of hiermee compatibel zijn.
* Zie de sectie **Aan de slag** in [Toegang tot e-mail en SharePoint beheren met Microsoft Intune](http://technet.microsoft.com/library/dn818907).aspx) voor de volledige lijst met vereisten voor het inschakelen van voorwaardelijke toegang voor pc's.
* Zie [Toegang tot e-mail beheren met Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx) voor opties die u kunt instellen om voorwaardelijke toegang tot e-mail in te schakelen.
* Zie [Toegang tot SharePoint Online beheren met Microsoft Intune](https://technet.microsoft.com/library/dn705844.aspx) voor opties die u kunt instellen om voorwaardelijke toegang tot SharePoint Online in te schakelen.

### Wijzigingen en updates voor Microsoft-bedrijfsportal-apps
In deze release zijn de volgende wijzigingen aangebracht aan de bedrijfsportal-apps:

**Android**

Als gebruikers hun apparaat nog niet hebben geregistreerd voor apparaatbeheer, zien ze na het aanmelden instructies voor het registreren van hun apparaat.

### Wat is er nieuw in Intune-documentatie -- augustus 2015
**Nieuwe onderwerpen**

|Titel|Details|
|-----|-------|
|[iOS-apparaten beschermen met bypass van activeringsvergrendeling voor Microsoft Intune](https://technet.microsoft.com/library/mt414176.aspx)|Meer informatie over hoe u Intune kunt gebruiken voor bypass van iOS-activeringsvergrendeling wanneer een gebruiker het bedrijf verlaat en een vergrendeld apparaat retourneert.|

**Bijgewerkte onderwerpen**

|Titel|Details|
|-----|-------|
|[Microsoft-apps die u met MAM-beleidsregels van Microsoft Intune kunt gebruiken](https://technet.microsoft.com/library/dn708489.aspx)|Bijgewerkt met de meest recente informatie over apps die u met Mobile Application Management-beleid kunt beheren.
|[Beleid gebruiken voor het beheren van computers en mobiele apparaten met Microsoft Intune](http://technet.microsoft.com/library/dn743712.aspx)|Bijgewerkt met de nieuwste beleidsregels die aan Intune zijn toegevoegd.|
<!---
## July 2015
July updates for Intune are limited to behind-the-scenes enhancements that allow us to continue providing you with a high-quality service experience. New features are not included in this service update.

### Intune Onboarding benefit
Microsoft offers the Intune Onboarding benefit for eligible plans. The Onboarding benefit lets you work remotely with Microsoft specialists to get your Intune environment ready for use. For more information, see [Microsoft Intune Onboarding benefit description](https://technet.microsoft.com/library/mt228266.aspx)
### Changes and updates to Microsoft Company Portal apps
The following changes have been made to the company portal apps in this release.

**Android**

Microsoft automatically collects anonymous data about the performance and use of the company portal to improve Microsoft products and services. End users can turn off data collection by using the Usage Data setting on their device, but administrators have no control over the data collection and cannot change the end user’s selection for this setting.--->



<!--HONumber=Jul16_HO4-->


