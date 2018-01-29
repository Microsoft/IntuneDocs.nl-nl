---
title: Vroege editie
description: 
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 01/18/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 12f4a09fe10ec792abe8183369a21f53c23f5d1a
ms.sourcegitcommit: 53d272defd2ec061dfdfdae3668d1b676c8aa7c6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/23/2018
---
# <a name="the-early-edition-for-microsoft-intune---january-2018"></a>De vroege editie voor Microsoft Intune - januari 2018

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

### <a name="easier-resolution-of-compliance-issues-for-the-company-portal-app-for-windows-10---676546---"></a>Eenvoudigere oplossing van problemen met naleving voor de bedrijfsportal-app voor Windows 10 <!--676546 -->

Eindgebruikers met Windows-apparaten kunnen tikken op de reden van niet-naleving in de bedrijfsportal-app. Indien mogelijk worden ze hiermee rechtstreeks naar de juiste locatie geleid in de instellingen-app om het probleem te verhelpen.

### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625---"></a>Nieuwe optie voor gebruikersverificatie voor bulkinschrijving met Apple <!-- 747625 -->
Intune biedt voor de volgende registratiemethoden de optie om apparaten te verifiëren met behulp van de bedrijfsportal-app:

- Apple Device Enrollment Program
- Apple School Manager
- Apple Configurator Enrollment

Wanneer u de bedrijfsportal-optie gebruikt, kan meervoudige verificatie van Azure Active Directory worden afgedwongen zonder deze registratiemethoden te blokkeren.

Wanneer u de bedrijfsportal-optie gebruikt, slaat Intune verificatie van gebruikers in de iOS-configuratieassistent over voor registratie op basis van gebruikersaffiniteit. Dit betekent dat het apparaat in eerste instantie wordt geregistreerd als een apparaat zonder gebruiker en derhalve geen configuraties of beleid van gebruikersgroepen ontvangt. Het apparaat ontvangt alleen configuraties en beleid voor apparaatgroepen. Intune installeert echter automatisch de bedrijfsportal-app op het apparaat. De eerste gebruiker die de bedrijfsportal-app start en zich aanmeldt, wordt in Intune aan het apparaat gekoppeld. Op dat punt ontvangt de gebruiker configuraties en beleid van zijn of haar gebruikersgroepen. De koppeling met de gebruiker kan niet worden gewijzigd zonder opnieuw te registreren.

### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Intune-ondersteuning voor meerdere Apple DEP-/Apple School Manager-accounts <!-- 747685 -->
Intune ondersteunt de registratie van apparaten uit maximaal 100 verschillende Apple Device Enrollment Program (DEP)- of Apple School Manager-accounts. Elk geüpload token kan afzonderlijk worden beheerd voor registratieprofielen en -apparaten. Er kan automatisch een ander registratieprofiel worden toegewezen per geüpload DEP-/School Manager-token. Als er meerdere School Manager-tokens zijn geüpload, kan er per keer slechts één worden gedeeld met Microsoft School Data Sync.

Na de migratie werken de bèta Graph API's en gepubliceerde scripts voor het beheren van Apple DEP of ASM over Graph niet meer. Nieuwe bèta Graph API's zijn in ontwikkeling en zullen na de migratie worden uitgebracht.

### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963-eeready---"></a>Apparaatcategorieën selecteren met behulp van de instellingen voor Toegang tot werk of school <!-- 1058963 eeready -->
Als u [apparaatgroeptoewijzing](https://docs.microsoft.com/en-us/intune/device-group-mapping) hebt ingeschakeld, wordt gebruikers van Windows 10 gevraagd een apparaatcategorie te selecteren na registratie via de knop **Verbinding maken** in **Instellingen**  >  **Accounts** > **Toegang tot werk of school** of tijdens de standaardprocedure.

### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Nalevingsbeleid afstemmen op apparaten in apparaatgroepen <!--1307012 -->

U kunt nalevingsbeleid richten op gebruikers in gebruikersgroepen. U kunt nalevingsbeleid richten op apparaten in apparaatgroepen.

### <a name="including-and-excluding-app-assignment-based-on-groups----1406920---"></a>App-toewijzing opnemen en uitsluiten op basis van groepen <!-- 1406920 -->

Tijdens toewijzing van een app en na het selecteren van een toewijzingstype, kunt u selecteren welke groepen u wilt opnemen en welke u wilt uitsluiten.

### <a name="remote-erase-command-support----1438084---"></a>Ondersteuning voor externe opdracht 'Wissen' <!-- 1438084 -->

Beheerders kunnen op afstand een opdracht voor wissen geven.

> [!IMPORTANT]
> De wisopdracht kan niet ongedaan worden gemaakt en moet voorzichtig worden gebruikt.

Met de wisopdracht worden alle gegevens van een apparaat verwijderd, inclusief het besturingssysteem. Hiermee wordt ook het apparaat uit Intune verwijderd. De gebruiker krijgt geen waarschuwing te zien en het verwijderen gebeurt onmiddellijk nadat de opdracht is gegeven.

U kunt wel een 6-cijferige herstelpincode configureren. Deze pincode kan worden gebruikt voor het ontgrendelen van het gewiste apparaat, waarna het besturingssysteem opnieuw wordt geïnstalleerd. Nadat het verwijderen is gestart, wordt de pincode weergegeven in een statusbalk op de overzichtsblade van het apparaat in Intune. De pincode blijft intact zolang het verwijderen wordt uitgevoerd. Nadat het verwijderen is voltooid, verdwijnt het apparaat volledig uit Intune-beheer. Zorg ervoor dat u de herstelpincode vastlegt zodat degene die het apparaat terugzet deze kan gebruiken.

### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Versleutelde gegevens van Windows Information Protection (WIP) in zoekresultaten van Windows <!-- 1469193 -->

Met een nieuwe instelling in het WIP-beleid (Windows Information Protection) kunt u zelf regelen of met WIP versleutelde gegevens in de zoekresultaten van Windows worden opgenomen.

### <a name="website-learning-mode----1631908---"></a>Website Learning-modus <!-- 1631908 -->

Intune komt met een uitbreiding van de Windows Information Protection (WIP) Learning-modus. Er wordt informatie over WIP-apps weergegeven en u kunt een overzicht bekijken van de apparaten die zakelijke gegevens hebben gedeeld met websites. Met deze informatie kunt u bepalen welke websites er moeten worden toegevoegd aan WIP-beleid voor groepen en gebruikers.

### <a name="updates-to-compliance-emails---1637547---"></a>Updates voor e-mailberichten over naleving <!--1637547 -->

Wanneer er een e-mailbericht wordt verzonden om een niet-compatibel apparaat te melden, worden daarin gegevens over het niet-compatibele apparaat opgenomen. Het volgende artikel wordt bijgewerkt om dat aan te geven: [Acties voor niet-naleving automatiseren](#actions-for-noncompliance).

### <a name="conditional-access-policies-for-intune-is-only-available-from-the-azure-portal-----1737088-1634311---"></a>Beleid voor voorwaardelijke toegang voor Intune is alleen beschikbaar vanuit Azure Portal <!-- 1737088 1634311 -->
We gaan het configureren en beheren van voorwaardelijke toegang voor u vereenvoudigen. U kunt uw beleid configureren en beheren in [Azure Portal](https://portal.azure.com) via **Azure Active Directory** > **Voorwaardelijke toegang**. Voor uw gemak hebt u ook toegang tot deze blade vanuit Intune in Azure Portal via **Intune** > **Voorwaardelijke toegang**.

###  <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire----1639263---"></a>Waarschuwingen voor vervallen tokens en tokens die binnenkort vervallen <!-- 1639263 -->
De overzichtspagina geeft waarschuwingen weer voor vervallen tokens en tokens die binnenkort vervallen. Wanneer u op een waarschuwing voor een specifiek token klikt, gaat u naar de detailpagina van dat token.  Als u op een waarschuwing met meerdere tokens klikt, gaat u naar een lijst met alle tokens met hun status. Beheerders moeten hun tokens vóór de vervaldatum vernieuwen.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>Extern afdrukken via een beveiligd netwerk <!-- 1709994  -->
Met de oplossingen voor draadloos mobiel afdrukken van PrinterOn kunnen gebruikers op afstand vanaf elke locatie en op elk gewenst moment afdrukken via een beveiligd netwerk. PrinterOn wordt geïntegreerd met de Intune APP SDK voor zowel iOS als Android. U kunt app-beveiligingsbeleid toepassen op deze app via de Intune-blade **App-beveiligingsbeleid** in de beheerconsole. Eindgebruikers kunnen de app 'PrinterOn for Microsoft' downloaden via de Play Store of iTunes voor gebruik binnen hun Intune-ecosysteem.

### <a name="approve-the-company-portal-app-for-android-for-work---1797090---"></a>De bedrijfsportal-app voor Android for Work goedkeuren <!--1797090 -->
Als uw organisatie Android for Work gebruikt, moet u de bedrijfsportal-app voor Android handmatig goedkeuren zodat deze automatische updates vanuit de beheerde Google Play Store blijft ontvangen.

### <a name="faceid-on-ios-devices----1807377---"></a>Face ID op iOS-apparaten <!-- 1807377 -->
Beveiligingsbeleid voor apps in Intune ondersteunt nu een instelling voor Face ID op iOS-apparaten. Deze instelling wordt gebruikt voor apparaten die ondersteuning bieden voor Face ID (momenteel alleen de iPhone X). Deze instelling staat los van de besturingselementen voor Touch ID die momenteel worden ondersteund. Organisaties kunnen kiezen om Face ID te vertrouwen als een geldige pincodeprompt als alternatief voor de besturingselementen voor Touch ID.

### <a name="microsoft-graph-api-for-intune---general-availability-----1833289---"></a>Microsoft Graph API voor Intune - algemene beschikbaarheid <!-- 1833289 -->
Intune API's in Microsoft Graph bieden programmatisch toegang tot gegevens en methoden voor het automatiseren van beheertaken voor de Intune-service.  Met de **Algemene beschikbaarheid** van deze API's kunnen klanten, partners en ontwikkelaars de API's gebruiken voor integratie met interne of commerciële oplossingen die betrekking hebben op of de ondersteuning nodig hebben van Intune of andere Microsoft-services die beschikbaar zijn via Microsoft Graph.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Beleid voor app-beveiliging <!-- 679615 -->
Via het beveiligingsbeleid voor Intune-apps kunt u algemene standaardbeleidsregels maken om snel beveiliging in te schakelen voor alle gebruikers in de gehele tenant.

### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>Apps uit het volume-aankoopprogramma voor iOS intrekken <!-- 820863 -->
Voor een bepaald apparaat met een of meer iOS-apps uit het volume-aankoopprogramma (VPP) kunt u de gekoppelde apparaatgebaseerde app-licentie voor het apparaat intrekken. Als u een app-licentie intrekt, wordt de desbetreffende VPP-app niet van het apparaat verwijderd. Als u een VPP-app wilt verwijderen, moet u de toewijzingsactie wijzigen in **Verwijderen**. Zie [iOS-apps beheren die zijn aangeschaft via een volume-aankoopprogramma met Microsoft Intune](vpp-apps-ios.md) voor meer informatie.

### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>Licenties intrekken voor een token van het iOS-volume-aanschafprogramma<!-- 820870 -->
U kunt de licentie van alle iOS-apps uit het volume-aanschafprogramma (VPP) voor een bepaalde VPP-token intrekken.

### <a name="new-ios-device-action------1244701---"></a>Nieuwe actie voor iOS-apparaten <!-- 1244701 -->
U kunt door iOS 10.3 gecontroleerde apparaten afsluiten. Deze actie sluit het apparaat direct af zonder waarschuwing voor de eindgebruiker. U vindt de actie **Afsluiten (alleen gecontroleerd)** in de apparaateigenschappen wanneer u een apparaat selecteert in de werkbelasting **Apparaat**.


### <a name="intune-now-provides-the-account-move-operation-----1573558-1579830---"></a>Intune biedt nu de bewerking Account verplaatsen <!-- 1573558, 1579830 -->
**Account verplaatsen** migreert een tenant van de ene ASU (Azure Scale Unit) naar een andere. **Account verplaatsen** kan worden gebruikt voor door de klant geïnitieerde scenario's, wanneer u het Intune-ondersteuningsteam belt om dit aan te vragen en in een door Microsoft aangestuurd scenario waarin Microsoft aan de back-end wijzigingen moet aanbrengen in de service. Tijdens de **accountverplaatsing** wordt voor de tenant de modus alleen-lezen (ROM) geactiveerd. Servicebewerkingen zoals inschrijven, de naam van apparaten wijzigen of de nalevingsstatus bijwerken mislukken tijdens de ROM-periode.




<!-- the following are present prior to 1712 -->
### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Mobiele apps van Office 365 toewijzen aan iOS- en Android-apparaten met behulp van de ingebouwde app-type<!-- 1332318 -->
Het **ingebouwde** app-type maakt het eenvoudiger voor u om Office 365-apps te maken en toe te wijzen aan door u beheerde iOS- en Android-apparaten. Deze apps zijn onder andere 0365-apps, zoals Word, Excel, PowerPoint en OneDrive. U kunt specifieke apps toewijzen aan het app-type en de configuratie van de app-gegevens bewerken.


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

### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866--"></a>Update van de gebruikerservaring voor de bedrijfsportal-app voor iOS<!--1412866-->

We zullen een grote update uitbrengen van de gebruikerservaring voor de bedrijfsportal-app voor iOS. De update heeft een volledig nieuw visueel ontwerp, waaronder een gemoderniseerde uitstraling met verbeterde bruikbaarheid en toegankelijkheid. De huidige functionaliteit van de iOS-bedrijfsportal-app blijft behouden.

We bieden een voorlopige versie van de bijgewerkte bedrijfsportal-app voor iOS via het Apple TestFlight-programma. U kunt deze versie gebruiken en uw feedback geven. Meld u aan bij https://aka.ms/intune_ios_cp_testflight voor toegang tot TestFlight. 

![teaserafbeeldingen voor de nieuwe iOS-bedrijfsportal-app](./media/ios-cp-app-redesign-1801-teaser.png)


<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Azure Active Directory-websites kunnen de Intune Managed Browser-app vereisen en ondersteunen eenmalige aanmelding voor de Managed Browser (openbare preview) <!-- 710595 -->   
Met Azure Active Directory (Azure AD) kunt u de toegang tot websites op mobiele apparaten beperken tot de Intune Managed Browser-app. In de Managed Browser blijven websitegegevens veilig en gescheiden van de persoonlijke gegevens van eindgebruikers. Daarnaast ondersteunt de Managed Browser eenmalige aanmelding voor sites die door Azure AD worden beveiligd. Door u aan te melden bij de Managed Browser of door de Managed Browser op een apparaat te gebruiken met een andere app die door Intune wordt beheerd, krijgt de Managed Browser toegang tot bedrijfssites die door Azure AD worden beveiligd, zonder dat de gebruiker referenties hoeft in te voeren. Deze functionaliteit is van toepassing op sites zoals Outlook Web Access (OWA) en SharePoint Online, evenals andere bedrijfssites zoals intranetbronnen die via de Azure App Proxy worden geopend.


<!-- the following are present prior to 1710 -->



### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Ondersteuning voor het editie-upgradebeleid voor Windows 10   <!-- 903672(archived), 1119689 -->  
U kunt een editie-upgradebeleid voor Windows 10 maken dat Windows 10-apparaten upgradet naar Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education en Windows 10 Professional Education N. Raadpleeg [Editie-upgrades voor Windows 10 configureren](edition-upgrade-configure-windows-10.md) voor meer informatie over editie-upgrades voor Windows 10.




<!-- the following are present prior to 1709 -->


### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Hulpmiddelen voor Intune-app-beveiliging en Citrix MDX <!-- 709185 -->
U kunt apparaten en apps beheren met een combinatie van Citrix XenMobile MDX en Microsoft Intune. Hierdoor kunt u apps beheren met het Intune-beveiligingsbeleid voor apps met behulp van de mVPN-technologie van Citrix.

U kunt een opslagplaats voor codes vinden met de Intune App Wrapping Tool en Intune App SDK voor iOS en Android, die integreren met Citrix MDX mVPN-technologie.




<!-- the following are present prior to 1711 -->


### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a>MacOS-gebruikers omleiden naar onze nieuwe bedrijfsportal-app <!--1380728-->   
Wanneer eindgebruikers zich aanmelden bij de bedrijfsportalwebsite om hun macOS-apparaten in te schrijven, worden ze gevraagd de nieuwe bedrijfsportal-app voor macOS te downloaden om het proces te voltooien. Dit gebeurt voor macOS-apparaten waarop OS X El Capitan 10.11 of hoger wordt uitgevoerd. 



<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Ondersteuning van Intune Managed Browser voor iOS en Android <!-- 1374196 -->
Vanaf oktober 2017 ondersteunt de app Intune Managed Browser voor Android alleen nog apparaten waarop Android 4.4 en hoger wordt uitgevoerd. De app Intune Managed Browser voor iOS ondersteunt alleen apparaten met iOS 9.0 en hoger. Oudere versies van Android en iOS kunnen Managed Browser nog steeds gebruiken, maar er kunnen geen nieuwe versies van de app op worden geïnstalleerd en kan er dus geen gebruik worden gemaakt van alle mogelijkheden van de app. U wordt aangeraden deze apparaten bij te werken tot een ondersteunde versie van het besturingssysteem.


### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Verbeterd foutbericht als een gebruiker het maximum aantal apparaten bereikt dat mag worden ingeschreven <!-- 1270370 -->
In plaats van een algemeen foutbericht krijgen eindgebruikers van Androis-apparaten een gebruikersvriendelijk foutbericht te zien waarop een actie kan worden uitgevoerd: 'U hebt het maximum aantal apparaten ingeschreven dat door de IT-beheerder is toegestaan. Verwijder een ingeschreven apparaat of vraag assistentie van uw IT-beheerder.'




## <a name="notices"></a>Mededelingen

Er zijn geen actieve meldingen op dit moment.




### <a name="see-also"></a>Zie ook
Zie [Wat is er nieuw in Microsoft Intune?](whats-new.md) voor meer informatie over recente ontwikkelingen.
