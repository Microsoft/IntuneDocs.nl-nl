---
title: Binnenkort | Microsoft Intune
description: 
keywords: 
author: Lindavr
manager: angrobe
ms.date: 08/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1f941fad998c6c0e07437c8f476df55325a4741b
ms.openlocfilehash: dd7bd41188cee812aafc8c439f703fa4abd42858


---

# Binnenkort in Microsoft Intune - augustus
Deze informatie wordt in zeer beperkte mate onder geheimhoudingsverklaring verstrekt en kan worden gewijzigd. Sommige functies die hier worden vermeld, zullen mogelijk niet beschikbaar zijn op de sluitingsdatum en worden mogelijk beschikbaar gesteld in een latere release. Andere functies worden getest in een proefversie, zodat we zeker weten dat ze in gebruik kunnen worden genomen. Neem bij vragen contact op met uw contactpersoon voor Intune/projectmanagement.

Deze pagina wordt regelmatig bijgewerkt. Kom daarom om de tijd terug om te zien of er nieuws is over wat er binnenkort beschikbaar is.

De volgende wijzigingen worden momenteel ontwikkeld voor Intune. Al deze functies worden uiteindelijk ondersteund voor implementaties voor hybride klanten (Configuration Manager met Intune). Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).


## Appbeheer
### Verborgen en weergegeven apps voor iOS 9.3
Voor apparaten met iOS 9.3 of hoger kunt u de lijst met verborgen of weergegeven apps in het algemene configuratiebeleid voor iOS gebruiken om het volgende te doen:
- Een lijst opstellen met apps die verborgen zijn voor gebruikers. Gebruikers kunnen deze apps niet weergeven of starten.
- Een lijst opstellen met apps die gebruikers kunnen weergeven en starten. Andere apps kunnen niet worden weergegeven of gestart.

De apps die u kunt opgeven zijn zowel apps die u hebt geïmplementeerd als de ingebouwde iOS-apps, zoals Berichten en Notities.
<!---TFS 1279009--->

### Beleid voor toegestane en geblokkeerde apps voor Samsung KNOX-apparaten

U kunt nu een aangepast beleid voor Samsung KNOX-apparaten configureren, waarmee u het volgende kunt maken:
- Een lijst met apps die niet kunnen worden uitgevoerd op het apparaat. Apps in deze lijst kunnen niet op het apparaat worden geactiveerd, ongeacht of ze daarop zijn geïnstalleerd.
- Een lijst met apps die gebruikers van het apparaat kunnen installeren uit de Google Play Store. Geen andere apps kunnen worden geïnstalleerd uit de Store.

Deze instellingen kunnen alleen worden gebruikt door apparaten met Samsung KNOX.
<!--- For details, see [Use custom policies to allow and block apps for Samsung KNOX devices]( custom-policy-to-allow-and-block-samsung-knox-apps.md)--->
<!---TFS 1311629 --->

### Nieuwe apps die compatibel zijn met de beleidsregels van Mobile Application Management (MAM)
De app Yammer voor [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) en [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) is compatibel met [de beleidsregels van Intune Mobile Application Management (MAM)](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune), ongeacht of het apparaat is geregistreerd.

Zie de website [Microsoft Intune-toepassingspartners](https://www.microsoft.com/cloud-platform/microsoft-intune-partners) voor een volledige lijst met apps die compatibel zijn met MAM.
<!--- TFS 1252335 & 1252336--->

## Apparaatbeheer
### Android 7.0-ondersteuning
Vanaf augustus biedt Intune 'day 0'-ondersteuning voor het toekomstige Android 7.0-besturingssysteem voor mobiele apparaten.
<!---TFS 1262053--->
### Google verwijdert het op afstand opnieuw instellen van de wachtwoordcode voor Android 7.0-apparaten
Google verwijdert de mogelijkheid van IT-beheerders en eindgebruikers om de wachtwoordcode van Android 7.0-apparaten op afstand opnieuw in te stellen. Voorheen konden IT-beheerders op afstand de wachtwoordcode van een gebruiker opnieuw instellen, en konden eindgebruikers hun wachtwoordcodes opnieuw instellen via de bedrijfsportalwebsite.

## Beheer van groepen
### Intune-groepen stappen over naar Azure Active Directory-groepen met ingang van september 2016
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

## Bedrijfsportal

### Feedbackkoppeling van de bedrijfsportal naar Microsoft
Op de website van de bedrijfsportal kunnen eindgebruikers tikken op een nieuwe koppeling ‘Feedback’ onderaan de pagina, en feedback verzenden naar Microsoft over hun ervaringen met de site. De verzamelde, geanonimiseerde feedback helpt Microsoft bij het verbeteren van de gebruikerservaring van de bedrijfsportalwebsite.
<!--- TFS 1313657--->

### Toevoeging van 'Meldingen' aan de bedrijfsportal voor Android
In september brengen wij een update uit van de bedrijfsportal voor Android, waarmee een nieuw pictogram **Meldingen** wordt geïntroduceerd op de startpagina. Door op dit pictogram te tikken wordt de pagina **Meldingen** geopend waar de eindgebruiker alle items ziet die aandacht vereisen in de bedrijfsportal-app, zoals niet-compatibele apparaten, inschrijvingsupdates en activering van inschrijvingen. Als u ook de iOS-bedrijfsportal-app gebruikt, kunt u de meldingen al zien. Door de introductie van de pagina **Meldingen** ziet u niet langer de pagina **Bedrijfstoegang instellen** wanneer u de bedrijfsportal voor Android start of hervat als het apparaat reeds is ingeschreven. Wij weten dat velen van u een handleiding hebben gemaakt voor eindgebruikers en stellen het op prijs wanneer u ons tijdig informeert wanneer uw handleiding en/of schermafbeeldingen moeten worden bijgewerkt. Werk uw documentatie bij zodat toekomstige wijzigingen in de gebruikerservaring goed worden beschreven. Ga voor bijgewerkte schermafbeeldingen naar: https://aka.ms/androidcpupdate.  


## Serviceafschaffing
### Bedrijfsportal-apps voor Windows 8 en Windows Phone 8 worden vanaf september 2016 afgeschaft
Vanaf september 2016 biedt Microsoft Intune geen ondersteuning meer voor de Microsoft Intune-bedrijfsportal-apps voor Windows Phone 8 en Windows 8. Apparaten bijwerken naar Windows 8.1 en Windows Phone 8.1 en de bijbehorende bedrijfsportal-app voor Windows 8.1 en Windows Phone 8.1 gebruiken om door te gaan met het distribueren van apps naar deze apparaten.
<!---TFS 1255391--->

### Meldingsregels voor aangepaste groepen wordt verwijderd
Met de Intune-meldingsregels wordt gedefinieerd wie een e-mailwaarschuwing ontvangt Intune. Op dit moment kunt u meldingsregels configureren om e-mails te verzenden naar alle gebruikers van apparaten in een Intune-apparaatgroep die u hebt gemaakt. Vanaf juni 2016 vervalt de ondersteuning voor het selecteren van door gebruikers gemaakte groepen als ontvanger.

De voorlopige tijdlijn voor deze wijziging is als volgt:
- In september 2016 krijgen nieuwe tenants stap 2 van de wizard Meldingsregel maken niet meer te zien. Voor de huidige tenants blijft de situatie ongewijzigd.
- Rond oktober 2016 krijgen enkele bestaande tenants de wizardoptie voor het selecteren van apparaatgroepen niet meer te zien.
- Naar verwachting krijgt later geen enkele bestaande tenant de wizardoptie voor het selecteren van apparaatgroepen nog te zien.

<!---   TFS 1278864--->
### Wijzigingen in de ondersteuning voor de iOS-bedrijfsportal-app
In september moeten alle gebruikers van de Microsoft Intune-bedrijfsportal-app voor iOS overstappen naar de nieuwste versie. Nieuwe gebruikers kunnen alleen de nieuwste versie downloaden en bestaande gebruikers moeten bijwerken naar de nieuwe versie. De meest recente versie vereist iOS 8.0 of hoger, zodat apparaten met oudere versies van iOS de bedrijfsportal niet kunnen gebruiken en niet kunnen registreren totdat ze hun apparaat naar hebben bijgewerkt naar iOS 8.0 of hoger en vervolgens de bedrijfsportal-app bijwerken naar de nieuwste versie. Geregistreerde apparaten met een versie lager dan iOS 8.0 worden gewoon nog worden beheerd met en vermeld in de Intune-beheerconsole.

<!---TFS 1283165--->


### Intune-viewer-apps
Met het uitbrengen van de nieuwe RMS-app voor delen, worden volgende Intune-viewer-apps in augustus 2016 verwijderd:
- Intune AV-viewer
- Intune PDF-viewer
- Intune-afbeeldingsviewer voor Android van Google Play

In plaats van de viewer-apps van Intune kunt u beter de nieuwe Rights Management-app (RMS sharing) voor Android gebruiken, zodat u één app in plaats van drie afzonderlijke apps kunt implementeren om veilig bedrijfsbestanden op Android-apparaten te bekijken. Meer informatie over de app RMS sharing (met een koppeling naar de documentatie).
<!--- goes in 1608 What's New--->


### Zie tevens
Zie [Wat is er nieuw in Microsoft Intune?](whats-new-in-microsoft-intune.md) voor meer informatie over recente ontwikkelingen.



<!--HONumber=Aug16_HO1-->


