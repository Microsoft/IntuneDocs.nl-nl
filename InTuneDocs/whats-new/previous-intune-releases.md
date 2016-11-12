---
title: Vorige versies | Microsoft Intune
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1360a23647d6e66ba682548ad2b158bb9047265d
ms.openlocfilehash: ec1b118b2c7681f351d83f469b8c32e95f8fa71f


---

# Vorige versies van Intune

## September 2016
### Nieuwe functies, aankondigingen en informatie
* [Voorwaardelijke toegang tot Windows](#windows-conditional-access)
* [Ondersteuning voor iOS 10](#ios-10-support)
* [App Wrapping Tool ondersteunt MAM zonder apparaatinschrijving voor Android en iOS](#app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios)
* [Intune-groepen beginnen in september met het overstappen naar Azure Active Directory](#intune-groups-begin-transitioning-to-azure-active-directory-in-september)
* [Lookout-integratie om Android-apparaten te beveiligen](#lookout-integration-to-protect-android-devices)
* [Bedrijfsportalupdates voor Android, iOS en Windows](#company-portal-updates)
* [Verklarende woordenlijst voor Intune](#intune-glossary)
* [Binnenkort](#whats-coming)

### Voorwaardelijke toegang tot Windows
U kunt nu voorwaardelijk toegangsbeleid creëren via de beheerdersconsole van Intune. Zo kunt u voorkomen dat Windows-pc's toegang hebben tot Exchange Online en SharePoint Online. Ook kunt u voorwaardelijke toegang creëren om de toegang te blokkeren tot Office- desktop en universele toepassingen.

### Ondersteuning voor iOS 10
Bestaande Intune MDM- en MAM-scenario's zijn compatibel met iOS 10. Raadpleeg voor tips de [Intune-teamblog voor ondersteuning](https://blogs.technet.microsoft.com/intunesupport/2016/09/13/support-tip-intune-support-for-ios-10/).

### App Wrapping Tool ondersteunt MAM zonder apparaatinschrijving voor Android en iOS
Intune App Wrapping Tool is een opdrachtregelprogramma dat wordt gebruikt voor het inschakelen van Intune MAM voor LOB-apps (Line-Of-Business) voor iOS en Android. Dit is de eenvoudigste manier om de Intune MAM SDK in uw app op te nemen, zodat in uw app MAM-beleid kan worden afgedwongen dat is geïmplementeerd via Intune. Met MAM-beleid kunt u het volgende doen:

1. De gegevens van de app versleutelen.
2. De informatiemedewerker vragen een pincode in te voeren bij het starten van de app.
3. Toestaan dat met de app alleen gegevens worden overgebracht naar andere beheerde apps.
4. Voorkomen dat met de app een back-up wordt opgeslagen in Android, iTunes of iCloud.
5. Knippen, kopiëren en plakken in en uit andere beheerde apps toestaan.

De openbare preview-versie van de bijgewerkte Intune App Wrapping Tool ondersteunt nu MAM zonder apparaatinschrijving voor interne LOB-apps voor iOS en Android. Dit betekent dat uw eindgebruikers hun apparaten niet hoeven in te schrijven met Intune om voor MAM geschikte LOB-apps te gebruiken.

Iedereen kan de openbare preview-software testen en nuttige documentatie in msintuneappsdk's GitHub lezen:

http://www.github.com/msintuneappsdk/intune-app-wrapper-ios-preview

http://www.github.com/msintuneappsdk/intune-app-wrapper-android-preview

Voordat u Microsoft Intune App Wrapper voor Android en iOS Pre-Release installeert en gebruikt, moet u:

* De licentievoorwaarden van Microsoft voor Microsoft Intune App Wrapping Tool voor Android en iOS Pre-Release lezen;
* Een exemplaar van de licentievoorwaarden voor uw administratie afdrukken en bewaren. Door Microsoft Intune App Wrapping Tool voor Android Pre-Release te downloaden en gebruiken, geeft u aan dat u akkoord gaat met deze licentievoorwaarden. Als u deze niet accepteert, moet u de software niet gebruiken.
<!---TFS 1235607--->

### Intune-groepen beginnen in september met het overstappen naar Azure Active Directory
Sommige nieuwe Intune-accounts gebruiken Azure Active Directory-beveiligingsgroepen in plaats van Intune-gebruikersgroepen. U zult merken dat u met beveiligingsgroepen werkt, doordat de pagina voor Intune-portalgroepen dan een koppeling heeft die u doorstuurt naar de Azure-beheerportal.

### Lookout-integratie om Android-apparaten te beveiligen
Microsoft is aan het integreren met de oplossing voor beveiliging tegen mobiele bedreigingen van Lookout om mobiele Android-apparaten te beveiligen door malware, riskante apps enzovoort op apparaten te detecteren. De oplossing van Lookout helpt u het (configureerbare) risiconiveau te bepalen. U kunt een beleidsregel in Intune maken om de apparaatnaleving te bepalen op basis van de risicoanalyse door Lookout. Met behulp van beleid voor voorwaardelijke toegang kunt u toegang tot bedrijfsbronnen toestaan of blokkeren op basis van de apparaatnalevingsstatus.

Eindgebruikers van apparaten die niet voldoen aan het beleid, moeten hun apparaten inschrijven en de Lookout for Work-toepassing op Android-apparaten installeren, de app activeren en bedreigingen verhelpen die zijn gerapporteerd in de Lookout for Work-toepassing om toegang te krijgen. Zie voor meer informatie [Toegang beperken op basis van apparaat, netwerk en toepassingsrisico](restrict-access-based-on-device-network-app-risk.md).


### Updates voor de bedrijfsportal

### Android
**Toevoeging van 'Meldingen' aan de bedrijfsportal voor Android**<br/>
Er is op de startpagina een nieuw meldingenpictogram toegevoegd aan de bedrijfsportal voor Android. Door op dit pictogram te tikken wordt de pagina Meldingen geopend waar de eindgebruikers alle items zien die aandacht vereisen in de bedrijfsportal-app, zoals niet-compatibele apparaten, inschrijvingsupdates en activering van inschrijvingen. Met de iOS-bedrijfsportal-app kunt u de meldingen al zien. Door de introductie van de pagina Meldingen zien gebruikers niet langer de pagina Bedrijfstoegang instellen wanneer zij de bedrijfsportal starten of hervatten als het apparaat al is geregistreerd. Als u uw eigen richtlijnen voor eindgebruikers maakt, is het raadzaam om uw documentatie bij te werken met deze wijziging. Zoek [hier](https://aka.ms/androidcpupdate) naar bijgewerkte schermafbeeldingen.  
<!---TFS 1095560--->

**Feedback geven in de bedrijfsportal voor Android**</br>
Er is een nieuw item toegevoegd aan het menu van de bedrijfsportal voor Android. Wanneer u op **Help en Feedback** tikt, ziet u drie acties:
* Gebruik **Hulp vragen** om problemen met de bedrijfsportal te melden aan uw IT-afdeling. IT maakt een e-mailbericht met behulp van uw e‑mailclient en voegt de logboeken van de bedrijfsportal toe als bijlage. **Hulp vragen** vervangt de functie **Gegevens verzenden** op de pagina **Instellingen**.
* Gebruik **Feedback geven** om feedback te geven aan het bedrijfsportalteam.
* Gebruik **Onze app beoordelen** om de bedrijfsportal-app te beoordelen of te recenseren op Google Play.

### iOS
**Wijzigingen in de ondersteuning voor de iOS-bedrijfsportal-app**<br/>
Alle gebruikers van de Microsoft Intune-bedrijfsportal-app voor iOS moeten nu overstappen naar de nieuwste versie. Nieuwe gebruikers kunnen alleen de nieuwste versie downloaden en bestaande gebruikers moeten bijwerken naar de nieuwe versie. De meest recente versie vereist iOS 8.0 of hoger, zodat apparaten met oudere versies van iOS de bedrijfsportal niet kunnen gebruiken en niet kunnen registreren totdat ze hun apparaat hebben bijgewerkt naar iOS 8.0 of hoger en vervolgens de Bedrijfsportal-app bijwerken naar de nieuwste versie. Geregistreerde apparaten met een versie lager dan iOS 8.0 worden gewoon nog worden beheerd met en vermeld in de Intune-beheerconsole.
<!---TFS 1283165--->

**Verbeteringen aan hoe iOS-eindgebruikers hun apps verkrijgen**<br/>
De volgende wijzigingen zijn aangebracht in de app-tegels in de Bedrijfsportal-app voor iOS, zodat gebruikers op één locatie (de Bedrijfsportal-website) naar verschillende weergaven worden verwezen voor alle apps. Het wordt door Apple verboden om LOB- (Line-Of-Business) en beheerde App Store-apps te vermelden in de Bedrijfsportal-app en gebruikers moeten verschillende weergaven openen om al hun apps te vinden.

- De tegel **Bedrijfsapps** verwees eerder naar alle apps op het tabblad ALLE van de Bedrijfsportal-website, en deze blijft op dezelfde manier werken. De naam van de tegel is gewijzigd in **Alle apps**.
- De tegel **Andere apps** verwees eerder naar een weergave in de bedrijfsportal-app waarin alle apps worden vermeld die van Apple mogen worden weergegeven in de app. De naam van de tegel is gewijzigd in **Aanbevolen apps**. Wanneer gebruikers op de tegel tikken, gaan ze naar het tabblad AANBEVOLEN van de bedrijfsportal-website.
-  De tegel **Categorieën** verwees eerder naar een weergave in de bedrijfsportal-app waarin app-categorieën worden vermeld. De naam van de tegel is niet gewijzigd, maar de tegel verwijst nu naar het tabblad CATEGORIEËN van de bedrijfsportal-website.
U vindt [hier](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186) bijgewerkte schermafbeeldingen.
<!---TFS 1317133--->

**Vragen om de iOS-app voor de Managed Browser te installeren als de IT-professional dat vereist voor een app**<br/>
Als u hebt geconfigureerd dat webclips alleen worden geopend in Managed Browser en Managed Browser niet is geïnstalleerd op een apparaat, krijgen gebruikers via de Bedrijfsportal-app op het apparaat de instructie om Managed Browser te installeren. Daarna kunnen ze de webclip pas openen.
<!---TFS 1228570--->

### Windows
**De knop Feedback is toegevoegd aan de bedrijfsportal-app voor Windows Phone 8.1**<br/>
Via de bedrijfsportal-app voor Windows Phone 8.1 kunnen eindgebruikers feedback over de app verzenden met een nieuwe knop Feedback verzenden. Gebruikers vinden de knop door te tikken op het menu met drie punten rechtsonder in het scherm van de bedrijfsportal-app en vervolgens te tikken op **feedback verzenden**. De verzamelde, geanonimiseerde feedback helpt Microsoft bij het verbeteren van de gebruikerservaring van de bedrijfsportal-app.
<!---TFS 1317806--->

### Verklarende woordenlijst voor Intune</br>
We hebben een nieuw [woordenlijstitem](https://docs.microsoft.com/intune/understand-explore/intune-glossary) toegevoegd aan de bibliotheek om meer duidelijkheid te geven over de termen die worden gebruikt bij het Intune-product.


## Augustus 2016
### Appbeheer
<!---@Barry, I created the buckets of App management, Device management, etc but am not tied to them. Just wanted to break up and organize the feature list. If you're going to take over the Company Portal section, please talk to Stacie about how she's been organizing it. --->

__Verborgen en weergegeven apps voor iOS 9.3__ Voor apparaten met supervisie waarop iOS 9.3 of hoger wordt uitgevoerd, kunt u de lijst met verborgen of weergegeven apps in het algemene configuratiebeleid voor iOS gebruiken om het volgende te doen:
- Een lijst opstellen met apps die verborgen zijn voor gebruikers. Gebruikers kunnen deze apps niet weergeven of starten.
- Een lijst opstellen met apps die gebruikers kunnen weergeven en starten. Andere apps kunnen niet worden weergegeven of gestart.

De apps die u kunt opgeven zijn zowel apps die u hebt geïmplementeerd als de ingebouwde iOS-apps, zoals Berichten en Notities. Zie [Instellingen voor iOS-beleid in Microsoft Intune]( /intune/deploy-use/ios-policy-settings-in-microsoft-intune) voor meer informatie.
<!---TFS 1279009 checked--->
__Beleid voor toegestane en geblokkeerde apps voor Samsung KNOX-apparaten__ U kunt nu een aangepast beleid voor Samsung KNOX-apparaten configureren om het volgende te maken:
- Een lijst met apps die niet kunnen worden uitgevoerd op het apparaat. Apps in deze lijst kunnen niet op het apparaat worden geactiveerd, ongeacht of ze daarop zijn geïnstalleerd.
- Een lijst met apps die gebruikers van het apparaat kunnen installeren uit de Google Play Store. Geen andere apps kunnen worden geïnstalleerd uit de Store.

Deze instellingen kunnen alleen worden gebruikt door apparaten met Samsung KNOX.
Zie [Aangepaste beleidsregels gebruiken om apps toe te staan of te blokkeren voor Samsung KNOX-apparaten](/intune/deploy-use/custom-policy-to-allow-and-block-samsung-knox-apps) voor meer informatie.
<!---TFS 1311629 checked --->
__Nieuwe apps die compatibel zijn met de beleidsregels van Mobile Application Management (MAM)__ De app Yammer voor [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) en [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) is nu compatibel met de [Intune MAM-beleidsregels (Mobile Application Management)](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune), ongeacht of het apparaat is ingeschreven of niet.

Zie de website [Microsoft Intune-toepassingspartners](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) voor een volledige lijst met apps die compatibel zijn met MAM.
<!--- TFS 1252335 & 1252336 checked--->

<!--- I started putting TFS numbers in the What's Coming topic and found it helpful when updating the What's New. Up to you if you want to continue. --->

__Intune-viewer-apps__ Met het uitbrengen van de nieuwe RMS-app voor delen worden de volgende Intune-viewer-apps vanaf augustus 2016 verwijderd:
- Intune AV-viewer
- Intune PDF-viewer
- Intune-afbeeldingsviewer voor Android van Google Play

In plaats van de viewer-apps van Intune kunt u beter de nieuwe [Rights Management-app (RMS sharing) voor Android](/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app) gebruiken, zodat u één app in plaats van drie afzonderlijke apps kunt implementeren om veilig bedrijfsbestanden op Android-apparaten te bekijken. Als de Intune-viewer-app niet meer wordt ondersteund, wordt deze verwijderd uit de Google Store en zal deze niet meer beschikbaar zijn voor toekomstig gebruik.

### Apparaatbeheer
__Android 7.0-ondersteuning__ Intune biedt vanaf dag één ondersteuning voor het toekomstige Android 7.0-besturingssysteem voor mobiele apparaten.
<!---TFS 1262053--->

__Google verwijdert het op afstand opnieuw instellen van de wachtwoordcode voor Android 7.0-apparaten__ Google verwijdert de mogelijkheid van IT-beheerders en eindgebruikers om de wachtwoordcode van Android 7.0-apparaten op afstand opnieuw in te stellen. Voorheen konden IT-beheerders op afstand de wachtwoordcode van een gebruiker opnieuw instellen, en konden eindgebruikers hun wachtwoordcodes opnieuw instellen via de bedrijfsportalwebsite.

### Updates voor de bedrijfsportal
__Bedrijfsportalwebsite__
- **Feedbackkoppeling van de bedrijfsportal naar Microsoft** <br/>
Op de website van de bedrijfsportal kunnen eindgebruikers tikken op de nieuwe koppeling Feedback onder aan de pagina en zo feedback verzenden naar Microsoft over hun ervaringen met de site. De verzamelde, geanonimiseerde feedback helpt Microsoft bij het verbeteren van de gebruikerservaring van de bedrijfsportalwebsite.
<!--- TFS 1313657 checked--->

__iOS__
- **Minimale iOS Managed Browser-versie is bijgewerkt naar 8.0**<br/>
De Microsoft Intune Managed Browser-app voor iOS is bijgewerkt voor ondersteuning van apparaten met iOS 8.0 of hoger. Hoewel op iOS 7.1-apparaten nog steeds de bestaande Managed Browser-app kan worden gebruikt, is het verstandig om uw gebruikers aan te raden hun apparaat bij te werken naar iOS 8.0 of hoger, zodat ze volledig kunnen profiteren van de nieuwe Managed Browser-functies.  
<!---TFS 1313253 checked--->

### Binnenkort

__iOS 10-ondersteuning__ Intune biedt volledige ondersteuning voor iOS 10. Meer informatie volgt bij de openbare release van iOS 10.

__Intune-groepen stappen met ingang van september 2016 over naar Azure Active Directory-groepen__ Intune is bezig met het creëren van een nieuwe ervaring voor het beheer van groepen die gebruikmaakt van Azure Active Directory (AAD)-beveiligingsgroepen als gebruikers- en apparaatgroepen in Intune. Deze groepen worden gebruikt voor alle groepsbeheer en voor implementatie van beleid en profielen **wanneer wij het nieuwe op Azure gebaseerde Intune-beheerportal introduceren**.

Door deze nieuwe ervaring hoeft u niet langer groepen te dupliceren tussen services, **hebt u toegang tot een aantal nieuwe groepsfuncties van Azure Active Directory Premium (AADP)**, en profiteert u van uitbreidbaarheid met behulp van PowerShell en Graph. Dit zorgt tevens voor een uniforme ervaring voor groepsbeheer voor het gehele beheer van bedrijfsmobiliteit.

Om de overstap naar beveiligingsgroepen mogelijk te maken, wordt de ervaring in de **huidige beheerconsole** ietwat gewijzigd. **Deze wijzigingen, en het gebruik van AAD-beveiligingsgroepen, worden beschreven in de Intune-documentatie**.

Voor nieuwe Intune-klanten worden bepaalde **wijzigingen van beveiligingsgroepen eerder doorgevoerd dan voor bestaande klanten**.

Naast de wijzigingen in het groepsbeheer, **wordt de volgende functionaliteit afgeschaft**:
- Uitsluiten van leden of groepen tijdens het maken van een nieuwe groep
- Groepen van **Niet-gegroepeerde gebruikers** en **Niet-gegroepeerde apparaten**
- **Groepen beheren** in de rol van servicebeheerder
- Aangepaste waarschuwingen op basis van groepen voor meldingsregels
- Draaien met groepen in rapporten
<!--- TFS 1295329--->

__Toevoeging van 'Meldingen' aan de bedrijfsportal voor Android__ In september brengen wij een update uit van de bedrijfsportal voor Android, waarmee een nieuw pictogram **Meldingen** wordt geïntroduceerd op de startpagina. Door op dit pictogram te tikken wordt de pagina **Meldingen** geopend waar de eindgebruiker alle items ziet die aandacht vereisen in de bedrijfsportal-app, zoals niet-compatibele apparaten, inschrijvingsupdates en activering van inschrijvingen. Als u ook de iOS-bedrijfsportal-app gebruikt, kunt u de meldingen al zien. Door de introductie van de pagina **Meldingen** ziet u niet langer de pagina **Bedrijfstoegang instellen** wanneer u de bedrijfsportal voor Android start of hervat als het apparaat reeds is ingeschreven. Wij weten dat velen van u een handleiding hebben gemaakt voor eindgebruikers en stellen het op prijs wanneer u ons tijdig informeert wanneer uw handleiding en/of schermafbeeldingen moeten worden bijgewerkt. Werk uw documentatie bij zodat toekomstige wijzigingen in de gebruikerservaring goed worden beschreven. Bijgewerkte schermafbeeldingen vindt u hier: https://aka.ms/androidcpupdate.  

__Verbeteringen aan hoe iOS-eindgebruikers hun apps verkrijgen__ De volgende wijzigingen worden in september aangebracht aan de apptegels in de Bedrijfsportal-app voor iOS, zodat gebruikers op één locatie (de Bedrijfsportal-app) naar verschillende weergaven worden verwezen voor alle apps. Op dit moment wordt het door Apple verboden om line-of-business en beheerde App Store-apps te vermelden in de Bedrijfsportal-app en moeten gebruikers verschillende weergaven openen om al hun apps te vinden.

- De tegel **Bedrijfsapps** verwijst momenteel naar alle apps op het tabblad ALLE van de Bedrijfsportal-website, en deze blijft ook op dezelfde manier werken. De naam van de tegel wordt gewijzigd in **Alle apps**.
- De tegel **Andere apps** verwijst momenteel naar een weergave in de Bedrijfsportal-app waarin alle apps worden vermeld die van Apple mogen weergegeven in de app. De naam van de tegel wordt gewijzigd in **Uitgelichte apps**. Wanneer gebruikers op de tegel tikken, gaan ze naar het tabblad UITGELICHT van de Bedrijfsportal-website.
-  De tegel **Categorieën** verwijst momenteel naar een weergave in de Bedrijfsportal-app waarin appcategorieën worden vermeld. De naam van de tegel wordt niet gewijzigd, maar verwijst nu naar het tabblad CATEGORIEËN van de Bedrijfsportal-website. U vindt [hier](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186) bijgewerkte schermafbeeldingen.
<!---TFS 1317133--->

### Cloudroadmap
Blijf op de hoogte van toekomstige ontwikkelingen op het gebied van Intune met de [Cloud Platform roadmap](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).

### Serviceafschaffing
<!---@Barry, we started listing service deprecations earlier this summer. --->
- **Wijzigingen in de ondersteuning voor de iOS-bedrijfsportal-app**<br/>
In september moeten alle gebruikers van de Microsoft Intune-bedrijfsportal-app voor iOS overstappen naar de nieuwste versie. Nieuwe gebruikers kunnen alleen de nieuwste versie downloaden en bestaande gebruikers moeten bijwerken naar de nieuwe versie. De meest recente versie vereist iOS 8.0 of hoger, zodat apparaten met oudere versies van iOS de bedrijfsportal niet kunnen gebruiken en niet kunnen registreren totdat ze hun apparaat naar hebben bijgewerkt naar iOS 8.0 of hoger en vervolgens de bedrijfsportal-app bijwerken naar de nieuwste versie. Geregistreerde apparaten met een versie lager dan iOS 8.0 worden gewoon nog worden beheerd met en vermeld in de Intune-beheerconsole.  

- **Minimale iOS Managed Browser-versie is bijgewerkt naar 8.0**<br/>
In augustus brengt Intune een bijgewerkte Microsoft Intune Managed Browser-app uit voor iOS die alleen apparaten ondersteund waarop iOS 8.0 of later wordt uitgevoerd. Hoewel iOS 7.1-apparaten nog steeds de bestaande Managed Browser-app kunnen gebruiken, dient u uw gebruikers aan te moedigen bij te werken naar iOS 8.0 of later om volledig te kunnen profiteren van nieuwe functies van Managed Browser.  
<!---TFS 1313253--->

- **Bedrijfsportal-apps voor Windows 8 en Windows Phone 8 worden afgeschaft** <br/>
Vanaf oktober 2016 biedt Microsoft Intune geen ondersteuning meer voor Windows 8- en Windows Phone 8-bedrijfsportal-apps. Microsoft Intune biedt dan ook geen ondersteuning meer voor het Windows Phone 8-platform. Als gevolg hiervan kunt u geen Windows Phone 8-apparaten meer registreren of bijwerken. U kunt Windows Phone 8- en Windows 8-apparaten die al zijn geregistreerd blijven beheren. Werk Windows 8- en Windows Phone 8-apparaten bij naar Windows 8.1 en Windows Phone 8.1. Gebruik de bijbehorende bedrijfsportal-apps voor Windows 8.1 en Windows Phone 8.1 om zonder onderbrekingen door te gaan met het distribueren van apps naar deze apparaten.
<!---TFS 1255391--->

<!--- - **Custom Group Targeting of Notification Rules Removal.**<br/>
Intune notification rules define who an email alert will be sent to from Intune. Currently, you can configure notification rules to send emails to all users of devices in an Intune device group that you created. From around June 1st 2016 moving forward, targeting user-created groups will no longer be supported.

    Today, to target a notification rule to a group you created from the Microsoft Intune administration console, you would take the following steps:

    In the **Admin** workspace, click **Notification Rules** > **Create New Rule**

    In step two of the Create Notification Rule Wizard, select the device groups which the rule will target. This step, “select device groups”, is being removed from the Intune Console.

    The preliminary timeline for this change is as follows:
    - In August, 2016, new tenants will not see step two of the Create Notification Rule Wizard. Exiting tenants are unaffected.
    - Around September, 2016, some existing tenants will not see the “select device groups” in the wizard.
    - Around November, 2016, we expect that all tenants will not see the “select device groups” in the wizard.

--->

## Juli 2016
### Appbeheer

__De update-ervaring van het inrichtingsprofiel van de app verbeteren__ Apple iOS mobiele Line-Of-Business-apps zijn gebouwd met een inrichtingsprofiel en code die is ondertekend met een certificaat. Wanneer de app wordt uitgevoerd op een iOS-apparaat, bevestigt iOS de integriteit van de iOS-app en worden beleidsregels afgedwongen die zijn gedefinieerd door het inrichtingsprofiel.

Het handtekeningcertificaat voor ondernemingen dat u gebruikt om apps te ondertekenen is doorgaans 3 jaar geldig. Het inrichtingsprofiel verloopt echter na één jaar. Met deze update biedt Intune u de hulpmiddelen om proactief een nieuw beleid voor inrichtingsprofielen te implementeren op apparaten met apps die bijna zijn verlopen terwijl het certificaat nog geldig is. Zie voor meer informatie [iOS-beleid voor mobiele inrichtingsprofielen gebruiken om uw Line-Of-Business-apps up-to-date te houden](/intune/deploy-use/ios-mobile-app-provisioning-profiles).
<!--- TFS 1280247--->

__Xamarin SDK voor Intune-apps is beschikbaar__ Met het onderdeel Intune App SDK Xamarin kunt u de beheerfuncties voor Intune Mobile App inschakelen in mobiele iOS- en Android-apps die zijn gebouwd met Xamarin. U vindt het onderdeel in de [Xamarin Store](https://components.xamarin.com/view/Microsoft.Intune.MAM) of op de [Microsoft Intune Github-pagina](https://github.com/msintuneappsdk).
<!--- TFS 1061478 --->

### Apparaatbeheer
__Verbeterde limieten voor apparaatinschrijvingen__ Intune heeft de maximaal configureerbare limiet voor apparaatinschrijvingen verhoogd van 5 naar 15 apparaten per gebruiker.
<!---TFS 1289896 --->

__TeamViewer-integratie voor Windows-pc's met de Intune-clientsoftware__
[TeamViewer](https://www.teamviewer.com) voor Windows-pc's die worden beheerd met de Intune-client kunt u, ter ondersteuning van uw helpdeskafdeling, sessies voor hulp op afstand met Windows-pc's uitvoeren. Dit is van toepassing op Windows 7, 8, 8.1 en 10. Zie [Algemene beheertaken voor Windows-pc’s met de Microsoft Intune-computerclient voor meer informatie](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client).
<!---TFS 1284856--->

### Updates voor de bedrijfsportal

__Bedrijfsportalwebsite__
- **Verbeterde ervaring voor de eindgebruiker bij het inschrijven van Windows-apparaten**<br/>
Wanneer u voorwaardelijke toegang gebruikt, zijn de stappen voor inschrijving voor Windows 8.1, Windows 10 Desktop en Windows 10 Mobile verbeterd op de bedrijfsportalwebsite. Gebruikers zien nu de afzonderlijke stappen 'Apparaatinschrijving' en 'Workplace Join', waardoor de status van hun apparaat beter zichtbaar is en het proces eenvoudiger kan worden voltooid wanneer er een fout optreedt met Workplace Join (WPJ). De afzonderlijke stappen vereenvoudigen tevens de probleemoplossing voor IT-beheerders. Wanneer eindgebruikers voorheen probeerden in te schrijven en alle inschrijvingsstappen waren geslaagd behalve WPJ, dan werd het ingeschreven apparaat niet weergegeven in de lijst met apparaten voor gebruikers, wat verwarrend was voor gebruikers.

__Android__
- **Android-bedrijfsportal-app**<br/>
Als Android-eindgebruikers een foutmelding krijgen dat er een vereist certificaat ontbreekt voor hun apparaat, dan kunnen zij op een knop 'Oplossing' tikken voor [stappen](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) om het ontbrekende certificaat te installeren. Als gebruikers de stappen voltooien, maar er nogmaals een foutmelding over een ontbrekend certificaat wordt weergegeven, dan wordt hen gevraagd contact op te nemen met de IT-beheerder en deze [koppeling](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues) door te geven die de stappen bevat waarmee IT-beheerders het certificaatprobleem kunnen oplossen.

- **Beperken van extern geladen (ofwel 'side-loaded') app-installaties op ingeschreven apparaten**<br/>
Android-apparaten kunnen geen toepassingen meer installeren via de bedrijfsportalwebsite tenzij deze apparaten zijn ingeschreven bij Intune via de Intune-bedrijfsportal-app voor Android.
<!---TFS 1299082--->

__iOS__
- **Wijzigingen in de beheeraccounts voor apparaatinschrijving in de iOS-bedrijfsportal-app**<br/>
Om de prestaties en schaalbaarheid te verbeteren, worden in het deelvenster **Mijn apparaten** van de iOS-bedrijfsportal-app niet meer alle Device Enrollment Managers (DEM)-apparaten weergegeven door Intune. Alleen het lokale apparaat waarop de app wordt uitgevoerd, wordt weergegeven en wel alleen als het apparaat is geregistreerd via de bedrijfsportal-app.

De DEM-gebruiker kan acties op het lokale apparaat uitvoeren, maar extern beheer van andere geregistreerde apparaten kan alleen worden uitgevoerd vanuit de Intune-beheerconsole. Daarnaast is het gebruik in Intune van DEM-accounts met het Apple Device Enrollment Program of het hulpprogramma Apple Configurator beëindigd. Deze twee registratiemethoden bieden al ondersteuning voor gebruikersloze registratie voor gedeelde iOS-apparaten.

Gebruik alleen DEM-accounts wanneer gebruikersloze registratie voor gedeelde apparaten niet beschikbaar is. Zie voor meer informatie [Apparaten in bedrijfseigendom inschrijven met de apparaatinschrijvingsbeheerder in Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

### Wijziging van de namen voor Windows-functies
- [Microsoft Passport for Windows](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) is nu bekend als **Windows Hello voor Bedrijven**.
- [Ondernemingsgegevensbescherming](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) is nu bekend als **Windows Information Protection**.

## Juni 2016
### Servicestatus van Intune
Servicestatusgegevens voor Intune is verplaatst naar een centrale locatie met andere Microsoft-services. U vindt deze informatie nu in de Office 365-beheerportal onder Servicestatus. Lees [dit blogbericht](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/) voor meer informatie.

### Appbeheer
- **Verbeterde ervaring voor configuratie van Windows 10-beleid voor ondernemingsgegevens.** Er zijn verbeteringen aangebracht in de ervaring voor configuratie van het Windows 10-beleid voor ondernemingsgegevensbescherming. Deze verbeteringen hebben betrekking op het maken van app-regels, het opgeven van netwerkdefinities en op andere instellingen voor ondernemingsgegevensbescherming. Zie [Een Enterprise Data Protection-beleid (EDP) maken met Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) voor meer informatie.


### Apparaatbeheer
- **Windows Defender-beleidsinstelling voor beveiliging tegen mogelijk ongewenste apps.** **Detectie van mogelijk ongewenste toepassingen** is een nieuwe Windows Defender-instelling die toegevoegd aan het algemene configuratiebeleid voor Windows 10 Desktop en Mobile. U kunt deze instelling gebruiken als u geregistreerde Windows-desktopcomputers wilt beveiligen tegen het uitvoeren van software die door Windows Defender als mogelijk ongewenst is gedefinieerd. U kunt voorkomen dat deze toepassingen worden uitgevoerd, of de controlemodus gebruiken om te rapporteren wanneer een mogelijk ongewenste toepassing wordt geïnstalleerd. Zie [Windows 10-beleidsinstellingen in Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune) voor meer informatie.
<!---TFS 1244478--->

### Voorwaardelijke toegang
- **Cisco ISE-netwerktoegangscontrolebeleid voor Intune.**  Klanten die Cisco Identity Service Engine (ISE) 2.1 en Microsoft Intune gebruiken, kunnen een netwerktoegangsbeleid instellen in ISE.

    Met dit beleid moeten apparaten die via Wi-Fi of VPN verbinding willen maken met het netwerk, voldoen aan de volgende voorwaarden voordat ze toegang krijgen:

    * Moeten worden beheerd met Intune
    * Moeten voldoen aan geïmplementeerd Intune-nalevingsbeleid

 Eindgebruikers van niet-compatibele apparaten wordt gevraagd zich te registreren en nalevingsproblemen op te lossen om toegang te krijgen.
- **Voorwaardelijke toegang voor de browser.** U kunt een beleid voor voorwaardelijke toegang instellen voor [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) en [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune), zodat deze alleen toegankelijk zijn via ondersteunde webbrowsers op beheerde en compatibele iOS- en Android-apparaten. Eindgebruikers die proberen zich met iOS- en Android-apparaten aan te melden bij Outlook Web Access (OWA) en SharePoint-sites, wordt gevraagd hun apparaat te registreren bij Intune en eventuele problemen met de compatibiliteit op te lossen. Hierna kan de aanmelding worden voltooid.
<!---TFS 1175844--->

- **Dynamics CRM Online biedt ondersteuning voor voorwaardelijke toegang.** U kunt beleid voor voorwaardelijke toegang instellen voor [Dynamics CRM Online](/intune/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune), zodat dit alleen toegankelijk is voor beheerde en compatibele iOS- en Android-apparaten. Eindgebruikers die zich op iOS en Android willen aanmelden bij de mobiele app Dynamics CRM, moeten zich registreren bij Intune en eventuele problemen met de naleving oplossen voordat de aanmelding wordt voltooid.
<!---TFS1295358--->

### Updates voor de Intune-bedrijfsportal

__Android-bedrijfsportal-app__

- Wanneer IT-beheerders het nieuwe beleid Vereisen dat apparaten de installatie van apps van onbekende bronnen niet toestaan (Android 4.0+) toepassen, krijgen eindgebruikers met een apparaat met Android 4.0 of hoger het volgende bericht te zien: De installatie vanuit onbekende bronnen moet worden uitgeschakeld. Gebruikers moeten naar **Instellingen** > **Beveiliging** gaan en **Onbekende bronnen** uitschakelen. Via een koppeling in het nalevingsbericht kunnen gebruikers meer [informatie](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android) verkrijgen over het bericht en over waarom ze de instelling moeten uitschakelen.

- Wanneer IT-beheerders het nieuwe beleid Vereisen dat apparaten het scannen van apps op beveiligingsrisico's inschakelen (Android 4.0+) toepassen, krijgen eindgebruikers met een apparaat met Android 4.0 of hoger het volgende bericht te zien: Apparaat scannen op beveiligingsrisico's. Gebruikers moeten naar **Instellingen** > **Google** > **Beveiliging** gaan en **Apparaat scannen op beveiligingsrisico's** inschakelen. Via een koppeling in het nalevingsbericht kunnen gebruikers meer [informatie](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) verkrijgen over het bericht en over waarom ze de instelling moeten inschakelen.

- Wanneer IT-beheerders het nieuwe beleid Vereisen dat USB-foutopsporing wordt uitgeschakeld (Android 4.2+) toepassen, krijgen eindgebruikers met een apparaat met Android 4.2 of hoger het volgende bericht te zien: USB-foutopsporing moet worden uitgeschakeld. Gebruikers moeten naar **Instellingen** > **Opties voor ontwikkelaars** gaan en **USB-foutopsporing** uitschakelen. Via een koppeling in het nalevingsbericht kunnen gebruikers meer [informatie](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android) verkrijgen over het bericht en over waarom ze de instelling moeten uitschakelen.

- Wanneer IT-beheerders het nieuwe beleid Minimaal niveau voor de Android-beveiligingspatch (Android 6.0+) toepassen, krijgen eindgebruikers met een apparaat met Android 6.0 of hoger het volgende bericht te zien: Dit apparaat voldoet niet aan het minimale Android-beveiligingspatchniveau. Gebruikers moeten de vereiste beveiligingspatch installeren. Via een koppeling in het nalevingsbericht kunnen gebruikers meer [informatie](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) verkrijgen over hoe de vereiste beveiligingspatch moet worden geïnstalleerd en over welke beveiligingspatch momenteel is geïnstalleerd.

__iOS-bedrijfsportal-app__

- Eindgebruikers die LOB-apps installeren, hebben nu een verbeterde ervaring tijdens de installatie van deze apps. Als de app-installatie lang duurt, kunnen gebruikers hun apparaat handmatig synchroniseren om hervatting van het synchronisatieproces af te dwingen. Zie [Sync your iOS device manually](/Intune/EndUser/sync-your-device-manually-ios) (Uw iOS-apparaat handmatig synchroniseren) voor de instructies voor eindgebruikers.

- De Microsoft Intune-bedrijfsportal-app voor iOS is bijgewerkt. Nu wordt iOS-versie 8.0 en hoger ondersteund. Deze update betekent dat eindgebruikers de bedrijfsportal-app kunnen installeren en alleen nieuwe apparaten kunnen registreren bij Intune als het apparaat iOS-versie 8.0 of hoger heeft. Gebruikers die werken met eerder ingeschreven apparaten met niet-ondersteunde versie van iOS kunnen de bedrijfsportal-app die op hun apparaat is geïnstalleerd blijven gebruiken.


## Mei 2016
Al deze functies worden ook ondersteund voor hybride implementaties (Configuration Manager met Intune). Zie de pagina met [nieuwe hybridefuncties](https://technet.microsoft.com/en-us/library/mt718155.aspx) (Engelstalig) voor meer informatie over nieuwe hybridefuncties.

### Documentatie
Dit is de preview-versie van [docs.microsoft.com](https://docs.microsoft.com/en-us/intune).
Dit is een volledig nieuw, modern inhoudsplatform dat is ontworpen om Intune gebruikersvriendelijker en eenvoudiger te maken.
Zie [Kennismaking met docs.microsoft.com](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/)

### Servicestatus van Intune
Servicestatusgegevens voor Intune is verplaatst naar een centrale locatie met andere Microsoft-services. U vindt deze informatie nu in de [Office 365-beheerportal](https://portal.office.com/Admin/Default.aspx) onder **Servicestatus**.
Lees [dit blogbericht](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/) voor meer informatie.


### Appbeheer
- **MAM SDK: ondersteuning voor configuratie van de lengte van de pincode.** Net als bij pincodes voor apparaten het geval is, kunt u ook voor MAM-apps de lengte van de pincode opgeven. Hiervoor moeten eindgebruikers voldoen aan de nieuwe beperkingen die u instelt. Ze zien dan een enigszins gewijzigd pincodescherm, waarin de langere code kan worden ingevoerd. Zie [MAM-beleidsinstellingen voor Android](/intune/deploy-use/android-mam-policy-settings) en [MAM-beleidsinstellingen voor iOS](/intune/deploy-use/ios-mam-policy-settings) voor meer informatie.

- **Skype voor Bedrijven voor iOS en Android.** U kunt Skype voor Bedrijven nu gebruiken met [MAM zonder inschrijvingsbeleid](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune). Zodra gebruikers zich aanmelden, wordt het MAM-beleid toegepast.

- **Nieuwe beschikbare apps voor beheer met MAM-beleid.** De Microsoft Word-, Excel- en PowerPoint-apps voor Android kunnen nu worden gekoppeld aan MAM-beleid op apparaten die niet zijn geregistreerd bij Intune. Ga voor de volledige lijst met ondersteunde apps naar de galerie met mobiele toepassingen van Microsoft Intune op de pagina [Microsoft Intune-toepassingen van partners](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).


### Updates voor de bedrijfsportal

#### Android-bedrijfsportal-app
- **Pop-upmeldingen voor eindgebruikers**: eindgebruikers krijgen nu pop-upmeldingen uit de Android-bedrijfsportal te zien wanneer ze hun apparaten registreren bij of verwijderen uit de bedrijfsportal.

- **Wijzigingen in de apparaatregistratiebeheeraccounts in de Android-bedrijfsportal-app.** Ter verbetering van de prestaties en schaalbaarheid worden er in het deelvenster Mijn apparaten van de Android-bedrijfsportal-app niet meer alle DEM-apparaten (Device Enrollment Manager; apparaatregistratiebeheer) door Intune weergegeven. Alleen het lokale apparaat waarop de app wordt uitgevoerd, wordt weergegeven en wel alleen als het apparaat is geregistreerd via de bedrijfsportal-app. De DEM-gebruiker kan acties op het lokale apparaat uitvoeren, maar extern beheer van andere geregistreerde apparaten kan alleen worden uitgevoerd vanuit de Intune-beheerconsole.

#### Bedrijfsportalwebsite
- **Bedrijfsportalwebsite: de banner voor apparaatidentificatie biedt eindgebruikers meer informatie.** Eindgebruikers kunnen het apparaat dat ze hebben geselecteerd, nu gemakkelijker identificeren wanneer ze de website van de bedrijfsportal gebruiken. Als er een verkeerd apparaat is geselecteerd, kunnen ze het juiste apparaat selecteren door op de koppeling **Tik hier** in de banner op de startpagina te tikken.

### Serviceafschaffing
- **Intune-viewer-apps.** Met het uitbrengen van de nieuwe RMS-app voor delen, worden volgende Intune-viewer-apps vanaf augustus 2016 verwijderd:
    - Intune AV-viewer
    - Intune PDF-viewer
    - Intune-afbeeldingsviewer voor Android van Google Play

  In plaats van de viewer-apps van Intune kunt u beter de nieuwe Rights Management-app (RMS sharing) voor Android gebruiken, zodat u één app in plaats van drie afzonderlijke apps kunt implementeren om veilig bedrijfsbestanden op Android-apparaten te bekijken. Meer informatie over de app RMS sharing (met een koppeling naar de documentatie).

- **Meldingsregels voor aangepaste groepen wordt verwijderd.**
Met de Intune-meldingsregels wordt gedefinieerd wie een e-mailwaarschuwing ontvangt Intune. Op dit moment kunt u meldingsregels configureren om e-mails te verzenden naar alle gebruikers van apparaten in een Intune-apparaatgroep die u hebt gemaakt. Vanaf 1 juni 2016 wordt de targeting van groepen die zijn gemaakt door gebruikers, niet meer ondersteund.

    Als u nu een meldingsregel wilt targeten op een groep die u in de Microsoft Intune-beheerconsole hebt gemaakt, voert u de volgende stappen uit:

    Klik in de werkruimte **Beheerder** op **Meldingsregels** > **Nieuwe regel maken**

    In stap 2 van de wizard Meldingsregel maken selecteert u de apparaatgroepen waarop de regel betrekking heeft. De stap voor het selecteren van apparaatgroepen wordt uit de Intune-console verwijderd.

    De voorlopige tijdlijn voor deze wijziging is als volgt:
    - In juni 2016 krijgen nieuwe tenants stap 2 van de wizard Meldingsregel maken niet meer te zien. Voor de huidige tenants blijft de situatie ongewijzigd.
    - Rond augustus 2016 krijgen enkele bestaande tenants de wizardoptie voor het selecteren van apparaatgroepen niet meer te zien.
    - Naar verwachting krijgt rond oktober 2016 geen enkele bestaande tenant de wizardoptie voor het selecteren van apparaatgroepen nog te zien.


- **Wijzigingen in de ondersteuning voor de iOS-bedrijfsportal-app**. In de komende maanden zal de Microsoft Intune-bedrijfsportal-app voor iOS worden bijgewerkt en biedt deze alleen nog ondersteuning voor apparaten met iOS 8.0 of later. Gebruikers kunnen geen nieuwe apparaten met een versie lager dan iOS 8.0 registreren. Geregistreerde apparaten met een versie lager dan iOS 8.0 worden gewoon nog beheerd en kunnen, voor een beperkte periode, gebruik blijven maken van de bedrijfsportal-app. Apparaten moeten echter over iOS 8.0 of later beschikken voor toegang tot de nieuwste versie van de bedrijfsportal-app. U kunt gebruikers het beste adviseren bij te werken naar iOS 8.0 of later om optimaal gebruik te kunnen maken van de nieuwe Intune-functies.  


## April 2016
Al deze functies worden ook ondersteund voor hybride klanten (Configuration Manager geïntegreerd met Intune).

### Appbeheer
- **Naleving van beleid door MAM-gebruikers.**
U kunt nu de [status](/intune/deploy-use/monitor-mobile-app-management-policies-with-Microsoft-Intune) van uw beleid voor toepassingsbeheer bekijken voor gebruikers in uw AAD-tenant (Azure Active Directory). Dit omvat:
   - Apparaten
   - Apps op het apparaat

   Statuswaarden:

   **Ingecheckt**: hiermee wordt aangegeven dat het beleid is geïmplementeerd voor de gebruiker, dat de app is gebruikt in een werkcontext en dat het beleid is ontvangen.

    **Niet ingecheckt**: hiermee wordt aangegeven dat het beleid is geïmplementeerd voor de gebruiker, maar dat de app sindsdien niet is gebruikt in een werkcontext.


- **MAM-besturingselementen om te voorkomen dat Outlook-contactpersonen worden gesynchroniseerd (Android).**
Er is een nieuwe instelling beschikbaar voor [Mobile Application Management](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) zonder apparaatregistratie. Met deze instelling kunt u voorkomen dat een toepassing contactpersonen synchroniseert met het systeemeigen adresboek op Android-apparaten. Wanneer deze instelling is ingeschakeld, kunnen doeltoepassingen niet langer contactpersonen in het systeemeigen adresboek opslaan. Wanneer deze instelling is uitgeschakeld, kunnen doeltoepassingen wel contactpersonen in het systeemeigen adresboek opslaan. Wanneer u [een apparaat of app op afstand wist](/intune/deploy-use/wipe-managed-company-app-data-with-Microsoft-Intune), worden de contactpersonen verwijderd die al in het systeemeigen adresboek zijn opgeslagen. Deze nieuwe instelling wordt in eerste instantie ondersteund door de Outlook-toepassing op Android-apparaten.

### Apparaatbeheer
- **Nummerherkenning voor apparaten die bedrijfseigendom zijn.** Telefoons die zijn aangemerkt als bedrijfseigendom, worden nu aangeduid met hun volledige telefoonnummer wanneer u bijvoorbeeld een inventarisrapport voor mobiele apparaten uitvoert. Telefoonnummers voor BYOD-apparaten worden nog steeds gemaskeerd met ****, waarbij alleen de laatste 4 cijfers worden weergegeven.


### Updates voor bedrijfsportal
**Android-bedrijfsportal-app** Gebruikers die hun apparaat niet bij Intune hebben ingeschreven en bij wie niet het juiste certificaat is geïnstalleerd, kunnen zich niet aanmelden bij de bedrijfsportal-app voor Android en zien het bericht 'U kunt u niet aanmelden omdat een vereist certificaat ontbreekt op het apparaat'. Het bericht bevat een koppeling Oplossing waarop gebruikers kunnen tikken om instructies te zien voor het installeren van het certificaat. Zie [Er ontbreekt een vereist certificaat voor uw apparaat](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing) om te zien welke stappen eindgebruikers moeten volgen om het probleem op te lossen.

**iOS-bedrijfsportal-app** Er is ondersteuning toegevoegd voor de actie 'veeg naar beneden om te vernieuwen' om de inhoud van het startscherm (met onder meer de lijst met apps, de lijst met apparaten en de contactgegevens van de IT-afdeling) te vernieuwen. De actie 'veeg naar beneden om te vernieuwen' controleert niet op naleving van beleid of beleidsgegevens. Dat kunt u doen door de tegel voor uw huidige apparaat te selecteren en op de knop **Synchroniseren** te tikken.

**Windows 10 Mobile- en Windows Phone 8.1-bedrijfsportal-app** Eindgebruikers die LOB-apps installeren, hebben nu een verbeterde ervaring tijdens de installatie van deze apps. Als de app-installatie lang duurt, kunnen gebruikers hun apparaat handmatig synchroniseren om hervatting van het synchronisatieproces af te dwingen. Zie [Sync your device manually to speed up app installations](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually) (Uw apparaat handmatig synchroniseren om de installatie van apps te versnellen) om de instructies voor eindgebruikers te bekijken.

**Bedrijfsportalwebsite** Wanneer gebruikers van Windows 10 Mobile en Windows Phone 8.1 LOB-apps installeren, zien ze nu de volgende nieuwe statussen, waardoor ze meer details over de status van hun installatie krijgen:

* **In afwachting van synchronisatie van het apparaat**: de gebruiker heeft op Installeren getikt en er wordt nu geprobeerd het apparaat te synchroniseren met de Intune-infrastructuur. Synchronisatie is vereist voordat de installatie kan worden voltooid. Het bericht 'In afwachting van synchronisatie van het apparaat' is ook een koppeling waarop gebruikers kunnen tikken om [instructies](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually) te zien over hoe zij hun apparaat handmatig kunnen synchroniseren met Intune als het synchronisatieproces lang duurt of vastloopt.
* **Downloaden**: de downloadaanvraag van de gebruiker wordt verwerkt en het apparaat downloadt en installeert de app.

Voordat deze statussen werden toegevoegd, raakten gebruikers in de war als de installatie van een app lang duurde, omdat ze alleen de status 'Installeren' zagen, die mogelijk uren lang op het scherm bleef staan. Het toevoegen van de nieuwe statussen betekent dat gebruikers in plaats van ondersteuning te bellen nu op de koppeling 'In afwachting van synchronisatie van het apparaat' kunnen tikken en de instructies voor het afdwingen van hervatting van het synchronisatieproces kunnen volgen.

>[!div class="step-by-step"]

>[&larr; **Wat is er nieuw in Intune?**](whats-new-in-microsoft-intune.md)    



<!--HONumber=Oct16_HO3-->


