---
title: Beheermogelijkheden voor geregistreerde apparaten
description: Raadpleeg dit onderwerp als u wilt weten hoe u met Intune de apparaten kunt beheren die u registreert.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/12/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f23b3ee7-78da-4e53-9fc2-78e58401bcf9
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5fc5e6108e7e7841ed142f24f463d85273ae8a12
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="enrolled-device-management-capabilities-of-microsoft-intune"></a>Beheermogelijkheden voor geregistreerde apparaten in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Met Microsoft Intune kunt u vele apparaten beheren door ze *in te schrijven* bij de service. U kunt sommige apparaattypen zelf inschrijven, maar u kunt ook gebruikers apparaten laten inschrijven met de *bedrijfsportal*-app. Dit biedt ze bovendien de mogelijkheid om bewerkingen uit te voeren, zoals apps zoeken en installeren, zorgen dat hun apparaten voldoen aan de bedrijfsbeleidsregels en contact opnemen met hun IT-afdeling voor ondersteuning.

Dit onderwerp bevat een volledige lijst van de mogelijkheden die u hebt nadat u uw apparaat hebt ingeschreven.

Beheer, inventarisatie, app-implementatie, inrichting en buitengebruikstelling worden alle afgehandeld via de Intune-beheerconsole. Gebruikers krijgen toegang tot de bedrijfsportal waar ze apps kunnen installeren, apparaten kunnen inschrijven en verwijderen en contact kunnen opnemen met hun IT-afdeling of helpdesk.



## <a name="device-security-and-configuration"></a>Apparaatbeveiliging en -configuratie

|Mogelijkheid|Details|Meer informatie|
|--------------|-----------|--------------------|
|Configuratiebeleid<br><br>Aangepast beleid| Hiermee kunt u veel instellingen en functies op mobiele apparaten in uw organisatie beheren. U kunt bijvoorbeeld een wachtwoord vereisen, het aantal mislukte pogingen beperken, de tijd waarna het scherm wordt vergrendeld verkorten, bepalen na hoeveel tijd wachtwoorden verlopen en voorkomen dat eerder gebruikte wachtwoorden opnieuw worden gebruikt. U kunt ook het gebruik van hardware- en softwarefuncties controleren, zoals de camera of de webbrowser van het apparaat.<br><br>Gebruik aangepast beleid wanneer configuratiebeleid niet de instellingen bevat die u nodig hebt. Op iOS-apparaten kunt u instellingen importeren die u hebt geëxporteerd uit Apple Configurator. Op andere apparaten kunt u OMA-URI-instellingen (Open Mobile Alliance Uniform Resource Identifier) gebruiken om instellingen en functies op het apparaat te configureren.|[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)|
|Wissen op afstand, vergrendelen op afstand en wachtwoordcode opnieuw instellen|Hiermee wist u gevoelige gegevens wanneer een apparaat is zoekgeraakt of gestolen. U kunt bijvoorbeeld het apparaat op afstand vergrendelen, de fabrieksinstellingen terugzetten of alleen bedrijfsgegevens wissen.<br><br>U kunt wachtwoordcodes opnieuw instellen als gebruikers geen toegang meer krijgen tot hun apparaat, verloren of gestolen apparaten vergrendelen of zelfs gegevens op verloren of gestolen apparaten wissen.|[Uw apparaten beschermen met extern vergrendelen en het opnieuw instellen van de wachtwoordcode](/intune-classic/deploy-use/retire-devices-from-microsoft-intune-management)|
|Kioskmodus|Hiermee kunt u bepaalde functies van mobiele apparaten vergrendelen, zoals schermafbeeldingen en de aan/uit-knop. U kunt hiermee apparaten ook beperken tot het uitvoeren van een enkele app die u opgeeft.|[Beleidsinstellingen voor iOS-configuraties in Microsoft Intune](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune)|

## <a name="app-management"></a>Appbeheer

|Mogelijkheid|Details|Meer informatie|
|--------------|-----------|--------------------|
|Implementatie en beheer van apps|Biedt een reeks hulpmiddelen voor het beheren van mobiele apps gedurende hun levensduur, met inbegrip van app-implementatie vanaf de installatiebestanden en vanuit app stores, gedetailleerde bewaking van app-status en verwijdering van de app.|[Apps in Microsoft Intune implementeren](/intune-classic/deploy-use/deploy-apps)|
|Compatibele en niet-compatibele apps|Hiermee kunt u een lijst opgeven met compatibele apps (die gebruikers mogen installeren) en niet-compatibele apps (die gebruikers niet mogen installeren).|[Instellingen voor iOS-beleid in Microsoft Intune](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune)|
|Beheer van mobiele toepassingen|Hiermee configureert u beperkingen voor apps met Mobile Application Management voor alle apparaten: zowel apparaten die met Intune worden beheerd als apparaten die niet met Intune worden beheerd. Op deze manier kunt u de beveiliging van uw bedrijfsgegevens verbeteren door bepaalde bewerkingen te beperken, zoals kopiëren en plakken, het maken van een externe back-up van gegevens en de gegevensoverdracht tussen apps.|[Mobile Application Management-beleid configureren en implementeren in de Microsoft Intune-console](/intune/app-wrapper-prepare-android)|
|Configuratie van mobiele apps voor iOS-apparaten|Configuratiebeleidsregels voor mobiele apps worden gebruikt om voor iOS-apps instellingen op te geven die mogelijk vereist zijn wanneer de gebruiker de app uitvoert. Een app kan bijvoorbeeld vereisen dat de gebruiker een poortnummer of aanmeldingsgegevens opgeeft. Zo kunt u de app-configuratie stroomlijnen en het aantal telefonische ondersteuningsvragen verminderen.|[iOS-apps met configuratiebeleid voor mobiele apps in Microsoft Intune configureren](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)|
|Profielen voor mobiele apps voor iOS-apparaten inrichten|Deze helpen u bij het implementeren van inrichtingsprofielen voor iOS-apps die bijna zijn verlopen. |[Gebruik beleidsregels voor profielinrichting voor mobiele iOS-apps om te voorkomen dat uw apps verlopen](/intune-classic/deploy-use/ios-mobile-app-provisioning-profiles)|
|Beheerde browser|Hiermee configureert u Managed Browser-beleid waarmee u bepaalt welke websites apparaatgebruikers wel en niet kunnen bezoeken. U kunt bovendien ook Mobile Application Management-beleid toepassen op de beheerde browser.|[Internettoegang beheren met beheerde-browserbeleid met Microsoft Intune](/intune-classic/deploy-use/manage-internet-access-using-managed-browser-policies)|
|Windows Hello voor Bedrijven|Hiermee maakt u integratie met Windows Hello voor Bedrijven mogelijk. Dit is een alternatieve aanmeldingsmethode voor Windows 10 waarbij on-premises Active Directory of Azure Active Directory wordt gebruikt ter vervanging van een wachtwoord, smartcards of virtuele smartcards.|[Instellingen van Windows Hello voor Bedrijven beheren op apparaten met Microsoft Intune](/intune-classic/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune)|
|Apps die zijn gekocht via het volume-aankoopprogramma|Hiermee kunt u apps beheren die u via een volume-aankoopprogramma hebt gekocht, door de licentiegegevens uit de App Store te importeren en bij te houden hoeveel licenties u hebt gebruikt. Zo wordt voorkomen dat u meer exemplaren van de app installeert dan u hebt gekocht.|[Met Microsoft Intune apps beheren die zijn gekocht via het volume-aankoopprogramma](/intune-classic/deploy-use/manage-volume-purchased-apps-in-microsoft-intune)|

## <a name="company-resource-access"></a>Toegang tot bedrijfsresources

|Mogelijkheid|Details|Meer informatie|
|--------------|-----------|--------------------|
|Certificaatprofielen|Hiermee kunt u vertrouwd-certificaatprofielen en SCEP-certificaten (Simple Certificate Enrollment Protocol) maken en implementeren, die kunnen worden gebruikt om Wi-Fi-, VPN- en e-mailprofielen te beveiligen en verifiëren.|[Toegang tot beveiligde bronnen met certificaatprofielen in Microsoft Intune](/intune-classic/deploy-use/secure-resource-access-with-certificate-profiles)|
|Wi-Fi-profielen|Hiermee kunt u instellingen voor draadloze netwerken implementeren voor uw gebruikers. Als u deze instellingen implementeert, kan de gebruiker zonder veel moeite verbinding met het bedrijfsnetwerk maken.|[Wi-Fi-verbindingen in Microsoft Intune](/intune-classic/deploy-use/wi-fi-connections-in-microsoft-intune)|
|E-mailprofielen|Hiermee kunt u e-mailinstellingen maken en op apparaten implementeren. Dit betekent dat gebruikers toegang kunnen krijgen tot zakelijke e-mail op hun eigen apparaten zonder dat ze zelf instellingen hoeven te configureren.|[De toegang tot zakelijke e-mail configureren met e-mailprofielen bij Microsoft Intune](/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune)|
|VPN-profielen|Hiermee kunt u VPN-instellingen implementeren voor gebruikers en apparaten in uw organisatie. Als u deze instellingen implementeert, kan de gebruiker zonder veel moeite verbinding maken met bronnen op het bedrijfsnetwerk.|[VPN-verbindingen in Microsoft Intune](/intune-classic/deploy-use/vpn-connections-in-microsoft-intune)|
|Beleid voor voorwaardelijke toegang|Hiermee kunt u toegang tot Microsoft Exchange-e-mailberichten en SharePoint Online beheren vanaf apparaten die niet worden beheerd door Intune.|[Toegang tot e-mail en SharePoint beperken met Microsoft Intune](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)|

## <a name="inventory-and-reporting"></a>Inventarisatie en rapportage

|Mogelijkheid|Details|Meer informatie|
|--------------|-----------|--------------------|
|Inventarisatie en rapportage|Hiermee kunt u naar informatie zoeken over de apparaten die u beheert en de software die deze apparaten gebruiken.|[Inzicht in uw apparaten met inventarisaties in Microsoft Intune](/intune-classic/deploy-use/understand-your-devices-with-inventory-in-microsoft-intune)|
