---
# required metadata

title: Binnenkort | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 05/03/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Binnenkort in Microsoft Intune
Deze informatie wordt in zeer beperkte mate onder geheimhoudingsverklaring verstrekt en kan worden gewijzigd. Sommige functies die hier worden vermeld, zullen mogelijk niet beschikbaar zijn op de sluitingsdatum en worden mogelijk beschikbaar gesteld in een latere release. Andere functies worden getest in een proefversie, zodat we zeker weten dat ze in gebruik kunnen worden genomen. Neem bij vragen contact op met uw contactpersoon voor Intune/projectmanagement.

Deze pagina wordt regelmatig bijgewerkt. Kom daarom om de tijd terug om te zien of er nieuws is over wat er binnenkort beschikbaar is.

De volgende wijzigingen worden momenteel ontwikkeld voor Intune. Al deze functies worden ook ondersteund voor implementaties voor hybride klanten (Configuration Manager met Intune). Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

## Message Center-onboarding
Als onderdeel van de migratie van Intune in de [Office 365-beheerportal](https://portal.office.com/) benutten we het bijbehorende Berichtencentrum om nieuwe functies en andere meldingen te communiceren.  U kunt ook de bijbehorende mobiele app voor Office 365-beheer installeren om meldingen te ontvangen op uw mobiele telefoon en eenvoudig berichten naar gebruikers of een distributiealias te sturen.<br>  
We gebruiken het Berichtencentrum voor onze release in mei om u te laten weten wanneer er updates voltooid zijn. Ook brengen we u op de hoogte van nieuwe en verbeterde Intune-functies.  Bekijk het Berichtencentrum meteen door u aan te melden bij de [Office 365-beheerportal](https://portal.office.com/) en de optie **BERICHTENCENTRUM** te kiezen in het navigatiepaneel aan de linkerkant.
<!---TFS 1242782--->


## App-beheer
- **Voorwaardelijke toegang voor de browser.** U kunt een beleid voor voorwaardelijke toegang instellen voor Exchange Online en SharePoint Online, zodat deze alleen toegankelijk zijn voor beheerde en compatibele iOS- en Android-apparaten. Eindgebruikers die proberen zich met iOS- en Android-apparaten aan te melden bij Outlook Web Access (OWA) en SharePoint-sites, wordt gevraagd hun apparaat in te schrijven bij Intune en eventuele problemen met de compatibiliteit op te lossen. Hierna kan de aanmelding worden voltooid.
<!---TFS 1175844--->

- **MAM SDK: ondersteuning voor configuratie van de lengte van de pincode.** Net als bij pincodes voor apparaten het geval is, kunt u ook voor MAM-apps de lengte van de pincode opgeven. Hiervoor moeten eindgebruikers voldoen aan de nieuwe beperkingen die u instelt. Ze zien dan een enigszins gewijzigd pincodescherm, waarin de langere code kan worden ingevoerd.
<!--- TFS 1104753--->

- **MAM-besturingselementen om te voorkomen dat Outlook-contactpersonen worden gesynchroniseerd (iOS).** Er is een nieuwe instelling beschikbaar voor Mobile Application Management zonder apparaatinschrijving. Met deze instelling kan de Intune-beheerder voorkomen dat een toepassing contactpersonen synchroniseert met het systeemeigen adresboek op iOS-apparaten. Wanneer deze instelling is ingeschakeld, kan de app niet langer contactpersonen in het systeemeigen adresboek opslaan. Wanneer deze instelling is uitgeschakeld, kan de app contactpersonen in het systeemeigen adresboek opslaan. Wanneer een Intune-beheerder een apparaat selectief wist, worden alle contactpersonen die al in het systeemeigen adresboek zijn opgeslagen, verwijderd. Deze nieuwe instelling wordt nu ondersteund door de Outlook-toepassing op iOS-apparaten.
<!---TFS item 1276166--->

- **Skype voor Bedrijven voor Android.** Intune-beheerders kunnen nu Skype voor Bedrijven gebruiken met MAM zonder inschrijvingsbeleid.  Zodra de gebruikers zich hebben aangemeld, wordt het MAM-beleid toegepast.
<!--- TFS item 1248444 --->

- **Skype voor Bedrijven voor iOS.** Intune-beheerders kunnen nu Skype voor Bedrijven gebruiken met MAM zonder inschrijvingsbeleid.  Zodra de gebruikers zich hebben aangemeld, wordt het MAM-beleid toegepast.
<!--- TFS item 1248443 --->

### Xamarin-ondersteuning
De Microsoft Intune App SDK ondersteunt nu Xamarin-apps in deze scenario's:

- Het schrijven van nieuwe apps of het wijzigen van de code van bestaande line-of-business-apps met de Intune-SDK. U kunt de invoegtoepassing downloaden via de pagina [Microsoft Intune Github](https://github.com/msintuneappsdk).
- Het toevoegen van MAM-ondersteuning aan bestaande line-of-business-apps met de Intune App Wrapping Tool

Zie [Bepalen hoe u apps met Microsoft Intune voorbereidt op Mobile Application Management met Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune) voor meer informatie om te bepalen welke methode u wilt gebruiken..
<!--- TFS 1061478 & TFS 1152340--->


## Apparaatbeheer
- **Externe hulpsessies voor Windows-pc's.** Met de integratie van TeamViewer voor pc's die worden beheerd door Windows-bureaubladagents, kunt u ter ondersteuning van helpdeskafdelingen voor eindgebruikers externe hulpsessies tot stand brengen met pc's die worden beheerd door Windows-bureaubladagents. Dit is van toepassing op Windows 7, 8, 8.1 en 10.
<!--- TFS 1284856--->


<!--- TFS item 1274326 --->

## Toegangsbeheer
* **Skype voor Bedrijven Online biedt ondersteuning voor voorwaardelijke toegang.** Intune-beheerders kunnen beleid voor voorwaardelijke toegang instellen voor Skype voor Bedrijven Online, zodat dit alleen toegankelijk is voor beheerde en compatibele iOS- en Android-apparaten. Eindgebruikers die zich op een iOS- of Android-apparaat willen aanmelden bij de mobiele app voor Skype voor Bedrijven, wordt gevraagd zich in te schrijven bij Intune en eventuele problemen met de compatibiliteit op te lossen. Hierna kan de aanmelding worden voltooid.
<!---TFS item 1254499--->

## Bedrijfsportal
* **De banner voor apparaatidentificatie biedt eindgebruikers meer informatie.** Eindgebruikers kunnen het apparaat dat ze hebben geselecteerd, gemakkelijk identificeren bij gebruik van de site van de bedrijfsportal. Als er een verkeerd apparaat is geselecteerd, kunnen ze het juiste apparaat selecteren door op de koppeling Tik hier in de banner op de startpagina te tikken.
<!--- TFS 1231157--->

* **Windows App-pakketten beschikbaar rechtstreeks vanuit de bedrijfsportal**: gebruikers van een pc met Windows 8, Windows 8.1 of Windows RT kunnen Windows App-pakketten (met de extensie .appx) nu rechtstreeks installeren vanaf de website van de bedrijfsportal. Eerder moesten Intune-beheerders de bedrijfsportal-app implementeren of moesten gebruikers deze installeren op hun apparaten om apps te kunnen installeren.
<!--- TFS item 1082481 --->

* **Gebruikers kunnen hun apparaat via de bedrijfsportal op afstand vergrendelen** Er is een nieuwe optie voor vergrendeling op afstand toegevoegd aan de website van de bedrijfsportal, zodat eindgebruikers hun apparaat via de portal op afstand kunnen vergrendelen als hun apparaat verloren of gestolen is. In de volgende tabel ziet u een lijst met de beschikbare platformondersteuning voor vergrendelen op afstand voor Intune en Intune met Configuration Manager.
<!--- TFS item 1195661 --->

|Platform  |Ondersteuningsgegevens|
|---------|---------|
|iOS | Ondersteund|
|Android | Ondersteund|
|Windows Phone 8,1 | Ondersteund|
|Windows 10 Mobile | Wordt alleen ondersteund als op de telefoon een wachtwoordcode is ingesteld|
|Pc (Windows 8.0 en eerder) | Niet ondersteund|
|Pc (Windows 8.1) | Niet ondersteund|
|Windows Phone 8.0 | Niet ondersteund|
|Windows 10 Desktop | Niet ondersteund|

## Serviceafschaffing
* **Meldingsregels voor aangepaste groepen wordt verwijderd.** Begin juni 2016 kunt u de wizard Meldingsregel maken niet langer gebruiken om meldingsregels te maken voor door een gebruiker gemaakte groepen.

    Op dit moment kunt u het volgende kiezen als u in de Microsoft Intune-beheerconsole een door een gebruiker gemaakte groep wilt gebruiken: **Beheer** > **Meldingsregels** > **Nieuwe regel maken**. In stap 2 van de wizard Meldingsregel maken moet u de apparaatgroepen selecteren waarop de regel betrekking heeft. Deze stap, **Apparaatgroepen selecteren**, wordt uit de Intune-console verwijderd.

    **Apparaatgroepen selecteren** wordt na de Intune-release van juni 2016 niet meer ondersteund. De optie wordt echter weergegeven tot augustus 2016. Na augustus zullen we onze tenants geleidelijk gedurende een periode van twee maanden overzetten. In oktober 2016 moeten alle bestaande klanten zijn overgezet. Na de migratie krijgt u de optie om meldingsregels te gebruiken voor een specifieke groep, niet langer te zien.
<!---   TFS 1278864--->







### Zie tevens
Zie [Wat is er nieuw in Microsoft Intune?](whats-new-in-microsoft-intune.md) voor meer informatie over recente ontwikkelingen.


<!--HONumber=May16_HO1-->


