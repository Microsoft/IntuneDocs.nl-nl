---
title: Wat is er nieuw? | Microsoft Intune
description: Ontdek wat er nieuw is in de release van Microsoft Intune van deze maand en in oudere releases
keywords: 
author: Lindavr
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 03a5dd14b854fedf7e2cb5b949580960a0eab9de
ms.openlocfilehash: 1d09e5a0adb3ecfa8f2d64f668ea7ff16bdf31fa


---

# Wat is er nieuw in Microsoft Intune -- september
Ontdek wat er nieuw is in deze release van Microsoft Intune. U vindt hier ook informatie over toekomstige wijzigingen waar u rekening mee moet houden én informatie over oudere releases.

Al deze functies worden uiteindelijk ondersteund voor implementaties voor hybride klanten (Configuration Manager met Intune). Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](https://technet.microsoft.com/library/mt718155.aspx).
<!---@Barry, the above blurb stays in each version, but make sure Tyler signs off each time. Also, remember to set the ms.date in the metadata to the sprint release. --->

>[!IMPORTANT]
>Blogbericht: Ervoor zorgen dat mobiele apparaten zijn bijgewerkt met Microsoft Intune<br>
>Na aanleiding van de recente 'Trident'-malwareaanvallen op iOS-apparaten is er een nieuw blogbericht gepubliceerd, [Ensuring mobile devices are up to date using Microsoft Intune](https://blogs.technet.microsoft.com/enterprisemobility/2016/08/26/ensuring-mobile-devices-are-up-to-date-using-microsoft-intune/) (Ervoor zorgen dat mobiele apparaten zijn bijgewerkt met Microsoft Intune), voor meer informatie over de verschillende manieren waarmee u met Intune uw apparaten beveiligd en bijgewerkt kunt houden.

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


### iOS
**Wijzigingen in de ondersteuning voor de iOS-bedrijfsportal-app**<br/>
Alle gebruikers van de Microsoft Intune-bedrijfsportal-app voor iOS moeten nu overstappen naar de nieuwste versie. Nieuwe gebruikers kunnen alleen de nieuwste versie downloaden en bestaande gebruikers moeten bijwerken naar de nieuwe versie. De meest recente versie vereist iOS 8.0 of hoger, zodat apparaten met oudere versies van iOS de bedrijfsportal niet kunnen gebruiken en niet kunnen registreren totdat ze hun apparaat hebben bijgewerkt naar iOS 8.0 of hoger en vervolgens de Bedrijfsportal-app bijwerken naar de nieuwste versie. Geregistreerde apparaten met een versie lager dan iOS 8.0 worden gewoon nog worden beheerd met en vermeld in de Intune-beheerconsole.
<!---TFS 1283165--->

**Verbeteringen aan hoe iOS-eindgebruikers hun apps verkrijgen**<br/>
De volgende wijzigingen zijn aangebracht in de app-tegels in de Bedrijfsportal-app voor iOS, zodat gebruikers op één locatie (de Bedrijfsportal-website) naar verschillende weergaven worden verwezen voor alle apps. Het wordt door Apple verboden om LOB- (Line-Of-Business) en beheerde App Store-apps te vermelden in de Bedrijfsportal-app en gebruikers moeten verschillende weergaven openen om al hun apps te vinden.

- De tegel **Bedrijfsapps** verwees eerder naar alle apps op het tabblad ALLE van de Bedrijfsportal-website, en deze blijft op dezelfde manier werken. De naam van de tegel is gewijzigd in **Alle apps**.
- De tegel **Andere apps** verwees eerder naar een weergave in de Bedrijfsportal-app waarin alle apps worden vermeld die van Apple mogen worden weergegeven in de app. De naam van de tegel is gewijzigd in **Aanbevolen apps**. Wanneer gebruikers op de tegel tikken, gaan ze naar het tabblad AANBEVOLEN van de Bedrijfsportal-website.
-  De tegel **Categorieën** verwees eerder naar een weergave in de Bedrijfsportal-app waarin app-categorieën worden vermeld. De naam van de tegel is niet gewijzigd, maar verwijst nu naar het tabblad CATEGORIEËN van de Bedrijfsportal-website.
U vindt [hier](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186) bijgewerkte schermafbeeldingen.
<!---TFS 1317133--->

**Vragen om de iOS-app voor de Managed Browser te installeren als de IT-professional dat vereist voor een app**<br/>
Als u hebt geconfigureerd dat webclips alleen worden geopend in Managed Browser en Managed Browser niet is geïnstalleerd op een apparaat, krijgen gebruikers via de Bedrijfsportal-app op het apparaat de instructie om Managed Browser te installeren. Daarna kunnen ze de webclip pas openen. 
<!---TFS 1228570--->

### Windows
**De knop Feedback is toegevoegd aan de bedrijfsportal-app voor Windows Phone 8.1**<br/>
Via de bedrijfsportal-app voor Windows Phone 8.1 kunnen eindgebruikers feedback over de app verzenden met een nieuwe knop Feedback verzenden. Gebruikers vinden de knop door te tikken op het menu met drie punten rechtsonder in het scherm van de bedrijfsportal-app en vervolgens te tikken op **feedback verzenden**. De verzamelde, geanonimiseerde feedback helpt Microsoft bij het verbeteren van de gebruikerservaring van de bedrijfsportal-app.
<!---TFS 1317806--->


## Binnenkort

### Intune-groepen stappen over naar Azure Active Directory-groepen
Intune is bezig met het creëren van een nieuwe ervaring voor het beheer van groepen die gebruikmaakt van Azure Active Directory (AAD)-beveiligingsgroepen als gebruikers- en apparaatgroepen in Intune. Deze groepen worden gebruikt voor alle groepsbeheer en voor implementatie van beleid en profielen **wanneer wij het nieuwe op Azure gebaseerde Intune-beheerportal introduceren**.

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

### Nieuw app-beleid voor voorwaardelijke toegang voor Exchange Online en SharePoint Online
U kunt de toegang tot Exchange Online en SharePoint Online beperken, zodat toegang alleen mogelijk is vanuit mobiele Office-apps, zoals Outlook, Word, Excel en OneDrive. Deze nieuwe functie past perfect bij het Intune MAM-beleid (Mobile App Management), aangezien u de toegang tot ingebouwde e-mailclients of andere apps die niet zijn geconfigureerd met het Intune MAM-beleid, kunt blokkeren. Hiermee zorgt u ervoor dat uw gebruikers de gegevens van uw organisatie gebruiken met apps die kunnen worden beveiligd met Intune MAM. U kunt aan de slag gaan met Intune Mobile App Management via Azure Portal. De nieuwe sectie Voorwaardelijke toegang kunt u in de blade Instellingen vinden.



### Serviceafschaffing

- **Bedrijfsportal-apps voor Windows 8 en Windows Phone 8 worden afgeschaft** <br/>
Vanaf oktober 2016 biedt Microsoft Intune geen ondersteuning meer voor Windows 8- en Windows Phone 8-bedrijfsportal-apps. Microsoft Intune biedt dan ook geen ondersteuning meer voor het Windows Phone 8-platform. Als gevolg hiervan kunt u geen Windows Phone 8-apparaten meer registreren of bijwerken. U kunt Windows Phone 8- en Windows 8-apparaten die al zijn geregistreerd blijven beheren. Werk Windows 8- en Windows Phone 8-apparaten bij naar Windows 8.1 en Windows Phone 8.1. Gebruik de bijbehorende bedrijfsportal-apps voor Windows 8.1 en Windows Phone 8.1 om zonder onderbrekingen door te gaan met het distribueren van apps naar deze apparaten.



### Cloudroadmap
Blijf op de hoogte van toekomstige ontwikkelingen op het gebied van Intune met de [Cloud Platform roadmap](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).


## Vorige versies van Intune
Raadpleeg het artikel over [Vorige versies van Intune](previous-intune-releases.md) als u wilt zien wat er de afgelopen zes maanden voor Intune is uitgekomen.

### Zie tevens
* [Microsoft Intune-blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform roadmap](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)



<!--HONumber=Sep16_HO3-->


