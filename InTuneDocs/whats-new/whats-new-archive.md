---
title: Wat is er nieuw? | Microsoft Intune
description: 
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ec77bc20bf429c804cb502bb46fc549d080a94ac
ms.openlocfilehash: 14698e5f40e76e370e178aeb6187d89fbc5cb2bd


---
## September 2016
## Nieuwe functies, aankondigingen en informatie
* [Voorwaardelijke toegang tot Windows](#windows-conditional-access)
* [Ondersteuning voor iOS 10](#ios-10-support)
* [App Wrapping Tool ondersteunt MAM zonder apparaatinschrijving voor Android en iOS](#app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios)
* [Intune-groepen beginnen in september met het overstappen naar Azure Active Directory](#intune-groups-begin-transitioning-to-azure-active-directory-in-september)
* [Lookout-integratie om Android-apparaten te beveiligen](#lookout-integration-to-protect-android-devices)
* [Bedrijfsportalupdates voor Android, iOS en Windows](#company-portal-updates)
* [Verklarende woordenlijst voor Intune](#intune-glossary)
* [Binnenkort](#whats-coming)

## Voorwaardelijke toegang tot Windows
U kunt nu voorwaardelijk toegangsbeleid creëren via de beheerdersconsole van Intune. Zo kunt u voorkomen dat Windows-pc's toegang hebben tot Exchange Online en SharePoint Online. Ook kunt u voorwaardelijke toegang creëren om de toegang te blokkeren tot Office- desktop en universele toepassingen.

## Ondersteuning voor iOS 10
Bestaande Intune MDM- en MAM-scenario's zijn compatibel met iOS 10. Raadpleeg voor tips de [Intune-teamblog voor ondersteuning](https://blogs.technet.microsoft.com/intunesupport/2016/09/13/support-tip-intune-support-for-ios-10/).

## App Wrapping Tool ondersteunt MAM zonder apparaatinschrijving voor Android en iOS
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

## Intune-groepen beginnen in september met het overstappen naar Azure Active Directory
Sommige nieuwe Intune-accounts gebruiken Azure Active Directory-beveiligingsgroepen in plaats van Intune-gebruikersgroepen. U zult merken dat u met beveiligingsgroepen werkt, doordat de pagina voor Intune-portalgroepen dan een koppeling heeft die u doorstuurt naar de Azure-beheerportal.

## Lookout-integratie om Android-apparaten te beveiligen
Microsoft is aan het integreren met de oplossing voor beveiliging tegen mobiele bedreigingen van Lookout om mobiele Android-apparaten te beveiligen door malware, riskante apps enzovoort op apparaten te detecteren. De oplossing van Lookout helpt u het (configureerbare) risiconiveau te bepalen. U kunt een beleidsregel in Intune maken om de apparaatnaleving te bepalen op basis van de risicoanalyse door Lookout. Met behulp van beleid voor voorwaardelijke toegang kunt u toegang tot bedrijfsbronnen toestaan of blokkeren op basis van de apparaatnalevingsstatus.

Eindgebruikers van apparaten die niet voldoen aan het beleid, moeten hun apparaten inschrijven en de Lookout for Work-toepassing op Android-apparaten installeren, de app activeren en bedreigingen verhelpen die zijn gerapporteerd in de Lookout for Work-toepassing om toegang te krijgen. Zie voor meer informatie [Toegang beperken op basis van apparaat, netwerk en toepassingsrisico](restrict-access-based-on-device-network-app-risk.md).


## Updates voor de bedrijfsportal

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

## Verklarende woordenlijst voor Intune</br>
We hebben een nieuw [woordenlijstitem](https://docs.microsoft.com/intune/understand-explore/intune-glossary) toegevoegd aan de bibliotheek om meer duidelijkheid te geven over de termen die worden gebruikt bij het Intune-product.



<!--HONumber=Oct16_HO2-->


