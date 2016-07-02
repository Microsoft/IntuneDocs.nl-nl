---
title: Binnenkort | Microsoft Intune
description: 
keywords: 
author: Lindavr
manager: jeffgilb
ms.date: 06/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
ms.sourcegitcommit: b203f51171d38f2b0fc2b46e556679322701d29b
ms.openlocfilehash: 77d2e74dcb032ff52808998c56de7d6b8847ebbe


---

# Binnenkort in Microsoft Intune
Deze informatie wordt in zeer beperkte mate onder geheimhoudingsverklaring verstrekt en kan worden gewijzigd. Sommige functies die hier worden vermeld, zullen mogelijk niet beschikbaar zijn op de sluitingsdatum en worden mogelijk beschikbaar gesteld in een latere release. Andere functies worden getest in een proefversie, zodat we zeker weten dat ze in gebruik kunnen worden genomen. Neem bij vragen contact op met uw contactpersoon voor Intune/projectmanagement.

Deze pagina wordt regelmatig bijgewerkt. Kom daarom om de tijd terug om te zien of er nieuws is over wat er binnenkort beschikbaar is.

De volgende wijzigingen worden momenteel ontwikkeld voor Intune. Al deze functies worden ook ondersteund voor implementaties voor hybride klanten (Configuration Manager met Intune). Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).


## Appbeheer
- **Verbeterde ervaring voor configuratie van Windows 10-beleid voor ondernemingsgegevens.** Er zijn verbeteringen aangebracht in de ervaring voor configuratie van het Windows 10-beleid voor ondernemingsgegevensbescherming. Deze verbeteringen hebben betrekking op het maken van app-regels, het opgeven van netwerkdefinities en op andere instellingen voor ondernemingsgegevensbescherming.
<!---TFS 1303011--->

- **Voorwaardelijke toegang voor de browser.** U kunt een beleid voor voorwaardelijke toegang instellen voor Exchange Online en SharePoint Online, zodat deze alleen toegankelijk zijn voor beheerde en compatibele iOS- en Android-apparaten. Eindgebruikers die proberen zich met iOS- en Android-apparaten aan te melden bij Outlook Web Access (OWA) en SharePoint-sites, wordt gevraagd hun apparaat te registreren bij Intune en eventuele problemen met de compatibiliteit op te lossen. Hierna kan de aanmelding worden voltooid.
<!---TFS 1175844--->

- **Dynamics CRM Online biedt ondersteuning voor voorwaardelijke toegang.** Klanten kunnen beleid voor voorwaardelijke toegang instellen voor Dynamics CRM Online, zodat dit alleen toegankelijk is voor beheerde en compatibele iOS- en Android-apparaten. Eindgebruikers die zich op iOS en Android willen aanmelden bij de mobiele app Dynamics CRM, moeten zich registreren bij Intune en eventuele problemen met de naleving oplossen voordat de aanmelding wordt voltooid.
<!---TFS1295358--->

### Xamarin-ondersteuning
De Microsoft Intune App SDK biedt nu ondersteuning voor Xamarin-apps in deze scenario's:

- Het registeren van nieuwe apps of het wijzigen van de code van bestaande line-of-business-apps met de Intune-SDK. U kunt de invoegtoepassing downloaden via de pagina [Microsoft Intune Github](https://github.com/msintuneappsdk).
- Het toevoegen van MAM-ondersteuning aan bestaande line-of-business-apps met de Intune App Wrapping Tool

Zie [Bepalen hoe u apps met Microsoft Intune voorbereidt op Mobile Application Management met Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune) voor meer informatie om te bepalen welke methode u wilt gebruiken.
<!--- TFS 1061478 & TFS 1152340--->

## Apparaatbeheer
- **Windows Defender-beleidsinstelling voor beveiliging tegen mogelijk ongewenste apps.** **Detectie van mogelijk ongewenste toepassingen** is een nieuwe Windows Defender-instelling die toegevoegd aan het algemene configuratiebeleid voor Windows 10 Desktop en Mobile. U kunt deze instelling gebruiken als u geregistreerde Windows-desktopcomputers wilt beveiligen tegen het uitvoeren van software die door Windows Defender als mogelijk ongewenst is gedefinieerd. U kunt voorkomen dat deze toepassingen worden uitgevoerd, of de controlemodus gebruiken om te rapporteren wanneer een mogelijk ongewenste toepassing wordt geïnstalleerd.
<!---TFS 1244478--->

## Voorwaardelijke toegang
**Cisco ISE-netwerktoegangscontrolebeleid voor Intune.**  Klanten die Cisco Identity Service Engine (ISE) 2.1 en Microsoft Intune gebruiken, kunnen een netwerktoegangsbeleid instellen in ISE.

Met dit beleid moeten apparaten die via Wi-Fi of VPN verbinding willen maken met het netwerk, voldoen aan de volgende voorwaarden voordat ze toegang krijgen:

* Moeten worden beheerd met Intune
* Moeten voldoen aan geïmplementeerd Intune-nalevingsbeleid

Eindgebruikers van niet-compatibele apparaten wordt gevraagd zich te registreren en nalevingsproblemen op te lossen om toegang te krijgen.
<!---TFS 1299144--->

## Bedrijfsportal
**Wijzigingen in de apparaatregistratiebeheeraccounts in de iOS-bedrijfsportal-app.** Om de prestaties en schaalbaarheid te verbeteren, worden in het deelvenster Mijn apparaten van de iOS-bedrijfsportal-app niet meer alle apparaten van apparaatregistratiebeheer weergegeven door Intune. Alleen het lokale apparaat waarop de app wordt uitgevoerd, wordt weergegeven en alleen als het apparaat is geregistreerd via de bedrijfsportal-app. De DEM-gebruiker kan acties op het lokale apparaat uitvoeren, maar extern beheer van andere geregistreerde apparaten kan alleen worden uitgevoerd vanuit de Intune-beheerconsole.  Daarnaast is het gebruik in Intune van DEM-accounts met het Apple Device Enrollment Program of het hulpprogramma Apple Configurator beëindigd. Deze twee registratiemethoden bieden al ondersteuning voor gebruikersloze registratie voor gedeelde iOS-apparaten. Gebruik alleen DEM-accounts wanneer gebruikersloze registratie voor gedeelde apparaten niet beschikbaar is.
<!---TFS 1233681--->

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



<!--HONumber=Jun16_HO3-->


