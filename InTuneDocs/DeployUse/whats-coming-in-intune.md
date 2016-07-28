---
title: Binnenkort | Microsoft Intune
description: 
keywords: 
author: Lindavr
manager: jeffgilb
ms.date: 07/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 35ee5d0c8898c95898c0527a623cf13c454387f2
ms.openlocfilehash: 831cec6cd0e02a94c1a3f67d4adf5a5dcbb01449


---

# Binnenkort in Microsoft Intune - juli
Deze informatie wordt in zeer beperkte mate onder geheimhoudingsverklaring verstrekt en kan worden gewijzigd. Sommige functies die hier worden vermeld, zullen mogelijk niet beschikbaar zijn op de sluitingsdatum en worden mogelijk beschikbaar gesteld in een latere release. Andere functies worden getest in een proefversie, zodat we zeker weten dat ze in gebruik kunnen worden genomen. Neem bij vragen contact op met uw contactpersoon voor Intune/projectmanagement.

Deze pagina wordt regelmatig bijgewerkt. Kom daarom om de tijd terug om te zien of er nieuws is over wat er binnenkort beschikbaar is.

De volgende wijzigingen worden momenteel ontwikkeld voor Intune. Al deze functies worden uiteindelijk ondersteund voor implementaties voor hybride klanten (Configuration Manager met Intune). Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).


## Appbeheer
### De update-ervaring van het inrichtingsprofiel van de app verbeteren
Apple iOS mobiele Line-Of-Business-apps zijn gebouwd met een inrichtingsprofiel en code die is ondertekend met een certificaat. Wanneer de app wordt uitgevoerd op een iOS-apparaat, bevestigt iOS de integriteit van de iOS-app en worden beleidsregels afgedwongen die zijn gedefinieerd door het inrichtingsprofiel.

Het handtekeningcertificaat voor ondernemingen dat u gebruikt om apps te ondertekenen is doorgaans 3 jaar geldig. Het inrichtingsprofiel verloopt echter na één jaar. Met deze update biedt Intune u de hulpmiddelen om proactief een nieuw beleid voor inrichtingsprofielen te implementeren op apparaten met apps die bijna zijn verlopen terwijl het certificaat nog geldig is.
<!--- TFS 1280247--->

### Xamarin-ondersteuning
De Microsoft Intune App SDK biedt nu ondersteuning voor Xamarin-apps in deze scenario's:

- Het registeren van nieuwe apps of het wijzigen van de code van bestaande line-of-business-apps met de Intune-SDK. U kunt de invoegtoepassing downloaden via de pagina [Microsoft Intune Github](https://github.com/msintuneappsdk).
- Het toevoegen van MAM-ondersteuning aan bestaande line-of-business-apps met de Intune App Wrapping Tool

Zie [Bepalen hoe u apps met Microsoft Intune voorbereidt op Mobile Application Management met Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune) voor meer informatie om te bepalen welke methode u wilt gebruiken.

<!--- TFS 1061478 & TFS 1152340--->

## Apparaatbeheer
### Verbeterde limieten voor apparaatinschrijvingen
Intune zal de maximaal configureerbare limiet voor apparaatinschrijvingen verhogen van 5 naar 15 apparaten per gebruiker.
<!---TFS 1289896 --->

## Beheer van groepen
### Intune-groepen stappen over naar Azure Active Directory-groepen met ingang van augustus 2016
Intune is bezig met het creëren van een nieuwe ervaring voor het beheer van groepen die gebruikmaakt van Azure Active Directory (AAD)-beveiligingsgroepen als gebruikers- en apparaatgroepen in Intune. Deze groepen worden gebruikt voor alle groepsbeheer en voor implementatie van beleid en profielen **wanneer wij het nieuwe op Azure gebaseerde Intune-beheerportal introduceren**.

Door deze nieuwe ervaring hoeft u niet langer groepen te dupliceren tussen services, **hebt u toegang tot een aantal nieuwe groepsfuncties van Azure Active Directory Premium (AADP)**, en profiteert u van uitbreidbaarheid met behulp van PowerShell en Graph. Dit zorgt tevens voor een uniforme ervaring voor groepsbeheer voor het gehele beheer van bedrijfsmobiliteit.

Om de overstap naar beveiligingsgroepen mogelijk te maken, wordt de ervaring in de **huidige beheerconsole** ietwat gewijzigd. **Deze wijzigingen, en het gebruik van AAD-beveiligingsgroepen, worden beschreven in de Intune-documentatie**.

Voor nieuwe Intune-klanten worden bepaalde **wijzigingen van beveiligingsgroepen eerder doorgevoerd dan voor bestaande klanten**.

Naast de wijzigingen in het groepsbeheer, **wordt de volgende functionaliteit afgeschaft**:
- Uitsluiten van leden of groepen tijdens het maken van een nieuwe groep
- 'Groepen beheren' in de rol van servicebeheerder
- Aangepaste waarschuwingen op basis van groepen voor meldingsregels
- Draaien met groepen in rapporten


## Bedrijfsportal

### Toevoeging van 'Meldingen' aan de bedrijfsportal voor Android
In augustus brengen wij een update uit van de bedrijfsportal voor Android, waarmee een nieuw pictogram **Meldingen** wordt geïntroduceerd op de startpagina. Door op dit pictogram te tikken wordt de pagina **Meldingen** geopend waar de eindgebruiker alle items ziet die aandacht vereisen in de bedrijfsportal-app, zoals niet-compatibele apparaten, inschrijvingsupdates en activering van inschrijvingen. Als u ook de iOS-bedrijfsportal-app gebruikt, kunt u de meldingen al zien. Door de introductie van de pagina **Meldingen** ziet u niet langer de pagina **Bedrijfstoegang instellen** wanneer u de bedrijfsportal voor Android start of hervat als het apparaat reeds is ingeschreven. Wij weten dat velen van u een handleiding hebben gemaakt voor eindgebruikers en stellen het op prijs wanneer u ons tijdig informeert wanneer uw handleiding en/of schermafbeeldingen moeten worden bijgewerkt. Werk uw documentatie bij zodat toekomstige wijzigingen in de gebruikerservaring goed worden beschreven. Ga voor bijgewerkte schermafbeeldingen naar: https://aka.ms/androidcpupdate  

### Gebruikers helpen bij het oplossen van inschrijvingsproblemen wanneer Workplace Join resulteert in een foutmelding
Wanneer u voorwaardelijke toegang gebruikt, zijn de stappen voor inschrijving voor Windows 8.1, Windows 10 Desktop en Windows 10 Mobile verbeterd op de bedrijfsportalwebsite voor eindgebruikers die te maken hebben met een fout van Workplace Join (WPJ). Wanneer eindgebruikers voorheen probeerden in te schrijven en een WPJ uit te voeren, en alle inschrijvingsstappen waren geslaagd behalve WPJ, dan werd het ingeschreven apparaat niet weergegeven in de lijst met apparaten voor gebruikers, wat verwarrend was voor gebruikers. Gebruikers zien nu de afzonderlijke stappen 'Apparaatinschrijving' en 'Workplace Join', waardoor de status van hun apparaat beter zichtbaar is en het proces eenvoudiger kan worden voltooid na een fout met Workplace Join (WPJ). De afzonderlijke stappen vereenvoudigen tevens de probleemoplossing voor IT-beheerders.

### Wijzigingen in de beheeraccounts voor apparaatinschrijving in de iOS-bedrijfsportal-app
Om de prestaties en schaalbaarheid te verbeteren, worden in het deelvenster Mijn apparaten van de iOS-bedrijfsportal-app niet meer alle apparaten van apparaatregistratiebeheer weergegeven door Intune. Alleen het lokale apparaat waarop de app wordt uitgevoerd, wordt weergegeven en alleen als het apparaat is geregistreerd via de bedrijfsportal-app. De DEM-gebruiker kan acties op het lokale apparaat uitvoeren, maar extern beheer van andere geregistreerde apparaten kan alleen worden uitgevoerd vanuit de Intune-beheerconsole.  Daarnaast is het gebruik in Intune van DEM-accounts met het Apple Device Enrollment Program of het hulpprogramma Apple Configurator beëindigd. Deze twee registratiemethoden bieden al ondersteuning voor gebruikersloze registratie voor gedeelde iOS-apparaten. Gebruik alleen DEM-accounts wanneer gebruikersloze registratie voor gedeelde apparaten niet beschikbaar is.
<!---TFS 1233681--->
### Beperken van extern geladen (ofwel 'side-loaded') app-installaties op ingeschreven Android-apparaten
Android-apparaten kunnen geen toepassingen meer installeren via de bedrijfsportalwebsite tenzij deze apparaten zijn ingeschreven bij Intune via de Intune-bedrijfsportal-app voor Android. 
<!---TFS 1299082--->

## Serviceafschaffing
**Bedrijfsportal-apps voor Windows 8 en Windows Phone 8 worden vanaf september 2016 afgeschaft.** Vanaf september 2016 biedt Microsoft Intune geen ondersteuning meer voor de Microsoft Intune-bedrijfsportal-apps voor Windows Phone 8 en Windows 8. Apparaten bijwerken naar Windows 8.1 en Windows Phone 8.1 en de bijbehorende bedrijfsportal-app voor Windows 8.1 en Windows Phone 8.1 gebruiken om door te gaan met het distribueren van apps naar deze apparaten.
<!---TFS 1255391--->

**Meldingsregels voor aangepaste groepen wordt verwijderd.**
Met de Intune-meldingsregels wordt gedefinieerd wie een e-mailwaarschuwing ontvangt Intune. Op dit moment kunt u meldingsregels configureren om e-mails te verzenden naar alle gebruikers van apparaten in een Intune-apparaatgroep die u hebt gemaakt. Vanaf 1 juni 2016 wordt de targeting van groepen die zijn gemaakt door gebruikers, niet meer ondersteund.

De voorlopige tijdlijn voor deze wijziging is als volgt:
- In augustus 2016 krijgen nieuwe tenants stap 2 van de wizard Meldingsregel maken niet meer te zien. Voor de huidige tenants blijft de situatie ongewijzigd.
- Rond september 2016 krijgen enkele bestaande tenants de wizardoptie voor het selecteren van apparaatgroepen niet meer te zien.
- Naar verwachting krijgt rond november 2016 geen enkele bestaande tenant de wizardoptie voor het selecteren van apparaatgroepen nog te zien.

<!---   TFS 1278864--->

**Wijzigingen in de ondersteuning voor de iOS-bedrijfsportal-app.**
In juli moeten alle gebruikers van de Microsoft Intune-bedrijfsportal-app voor iOS overstappen naar de nieuwste versie. Nieuwe gebruikers kunnen alleen de nieuwste versie downloaden en bestaande gebruikers moeten bijwerken naar de nieuwe versie. De meest recente versie vereist iOS 8.0 of hoger, zodat apparaten met oudere versies van iOS de bedrijfsportal niet kunnen gebruiken en niet kunnen registreren totdat ze hun apparaat naar hebben bijgewerkt naar iOS 8.0 of hoger en vervolgens de bedrijfsportal-app bijwerken naar de nieuwste versie. Geregistreerde apparaten met een versie lager dan iOS 8.0 worden gewoon nog worden beheerd met en vermeld in de Intune-beheerconsole.  

**Intune-viewer-apps.** Met het uitbrengen van de nieuwe RMS-app voor delen, worden volgende Intune-viewer-apps vanaf augustus 2016 verwijderd:
- Intune AV-viewer
- Intune PDF-viewer
- Intune-afbeeldingsviewer voor Android van Google Play

In plaats van de viewer-apps van Intune kunt u beter de nieuwe Rights Management-app (RMS sharing) voor Android gebruiken, zodat u één app in plaats van drie afzonderlijke apps kunt implementeren om veilig bedrijfsbestanden op Android-apparaten te bekijken. Meer informatie over de app RMS sharing (met een koppeling naar de documentatie).



### Zie tevens
Zie [Wat is er nieuw in Microsoft Intune?](whats-new-in-microsoft-intune.md) voor meer informatie over recente ontwikkelingen.



<!--HONumber=Jul16_HO3-->


