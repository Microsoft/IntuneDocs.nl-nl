---
title: Beheermogelijkheden voor apparaten in Microsoft Intune
description: Raadpleeg dit onderwerp als u wilt weten hoe u met Intune de apparaten kunt beheren die u registreert.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/16/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 293fa40b59d0005f60aad45a3fc42d3dd790857d
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/23/2019
ms.locfileid: "61510143"
---
# <a name="enrolled-device-management-capabilities-of-microsoft-intune"></a>Beheermogelijkheden voor geregistreerde apparaten in Microsoft Intune

Met Microsoft Intune kunt u vele apparaten beheren door ze *in te schrijven* bij de service. U kunt sommige apparaattypen zelf inschrijven, maar u kunt ook gebruikers apparaten laten inschrijven met de *bedrijfsportal*-app. Als gebruikers apparaten inschrijven, kunnen ze apps zoeken en installeren. Zorg daarom ervoor dat deze apparaten voldoen aan het bedrijfsbeleid en neem contact op met de IT-ondersteuning van de gebruikers.

Dit onderwerp bevat een volledige lijst met de mogelijkheden die u hebt nadat u uw apparaat hebt ingeschreven.

Beheer, inventarisatie, app-implementatie, inrichting en buitengebruikstelling worden allemaal afgehandeld via Azure Portal.

Gebruikers krijgen toegang tot de bedrijfsportal waar ze apps kunnen installeren, apparaten kunnen inschrijven en verwijderen en contact kunnen opnemen met hun IT-afdeling of helpdesk.



## <a name="device-security-and-configuration"></a>Apparaatbeveiliging en -configuratie

|Mogelijkheid|Details|Meer informatie|
|--------------|-----------|--------------------|
|Configuratiebeleid<br><br>Aangepast beleid| Hiermee kunt u veel instellingen en functies op mobiele apparaten in uw organisatie beheren. U kunt bijvoorbeeld een wachtwoord vereisen, het aantal mislukte pogingen beperken, de tijd waarna het scherm wordt vergrendeld verkorten, bepalen na hoeveel tijd wachtwoorden verlopen en voorkomen dat eerder gebruikte wachtwoorden opnieuw worden gebruikt. U kunt ook het gebruik van hardware- en softwarefuncties controleren, zoals de camera of de webbrowser van het apparaat.<br><br>Gebruik aangepast beleid wanneer configuratiebeleid niet de instellingen bevat die u nodig hebt. Op iOS-apparaten kunt u instellingen importeren die u hebt geëxporteerd uit Apple Configurator. Op andere apparaten kunt u OMA-URI-instellingen (Open Mobile Alliance Uniform Resource Identifier) gebruiken om instellingen en functies op het apparaat te configureren.|[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](device-compliance-get-started.md)|
|Wissen op afstand, vergrendelen op afstand en wachtwoordcode opnieuw instellen|Hiermee wist u gevoelige gegevens wanneer een apparaat is zoekgeraakt of gestolen. U kunt bijvoorbeeld het apparaat op afstand vergrendelen, de fabrieksinstellingen terugzetten of alleen bedrijfsgegevens wissen.<br><br>U kunt wachtwoordcodes opnieuw instellen als gebruikers geen toegang meer krijgen tot hun apparaat, verloren of gestolen apparaten vergrendelen of zelfs gegevens op verloren of gestolen apparaten wissen.|Uw apparaten beschermen met [extern vergrendelen](device-remote-lock.md) en [het opnieuw instellen van de wachtwoordcode](device-passcode-reset.md)|
|Kioskmodus|Hiermee kunt u bepaalde functies van mobiele apparaten vergrendelen, zoals schermafbeeldingen en de aan/uit-knop. U kunt hiermee apparaten ook beperken tot het uitvoeren van een enkele app die u opgeeft. |[Beleidsinstellingen voor iOS-configuraties in Microsoft Intune](device-restrictions-ios.md)|

## <a name="app-management"></a>Appbeheer

|Mogelijkheid|Details|Meer informatie|
|--------------|-----------|--------------------|
|Implementatie en beheer van apps|Biedt een reeks hulpmiddelen voor het beheren van mobiele apps gedurende hun levensduur, met inbegrip van app-implementatie vanaf de installatiebestanden en vanuit app stores, gedetailleerde bewaking van app-status en verwijdering van de app.|[Apps in Microsoft Intune implementeren](apps-deploy.md)|
|Compatibele en niet-compatibele apps|Hiermee kunt u een lijst opgeven met compatibele apps (die gebruikers mogen installeren) en niet-compatibele apps (die gebruikers niet mogen installeren).|[Instellingen voor iOS-beleid in Microsoft Intune](device-restrictions-ios.md)|
|Beheer van mobiele toepassingen|Hiermee configureert u beperkingen voor apps met Mobile Application Management voor alle apparaten: zowel apparaten die met Intune worden beheerd als apparaten die niet met Intune worden beheerd. U kunt de beveiliging van uw bedrijfsgegevens verbeteren door bepaalde bewerkingen te beperken, zoals kopiëren en plakken, het maken van een externe back-up van gegevens en de gegevensoverdracht tussen apps.|[Mobile Application Management-beleid configureren en implementeren in de Microsoft Intune-console](app-wrapper-prepare-android.md)|
|Configuratie van mobiele apps voor iOS-apparaten|Configuratiebeleidsregels voor mobiele apps worden gebruikt om voor iOS-apps instellingen op te geven die mogelijk vereist zijn wanneer de gebruiker de app uitvoert. Een app kan bijvoorbeeld vereisen dat de gebruiker een poortnummer of aanmeldingsgegevens opgeeft. U kunt de app-configuratie stroomlijnen en het aantal telefonische ondersteuningsvragen verminderen.|[iOS-apps met configuratiebeleid voor mobiele apps in Microsoft Intune configureren](app-configuration-policies-use-ios.md)|
|Profielen voor mobiele apps voor iOS-apparaten inrichten|Deze helpen u bij het implementeren van inrichtingsprofielen voor iOS-apps die bijna zijn verlopen. |[Gebruik beleidsregels voor profielinrichting voor mobiele iOS-apps om te voorkomen dat uw apps verlopen](app-provisioning-profile-ios.md)|
|Beheerde browser|Hiermee configureert u Managed Browser-beleid waarmee u bepaalt welke websites apparaatgebruikers wel en niet kunnen bezoeken. U kunt bovendien ook Mobile Application Management-beleid toepassen op de beheerde browser.|[Internettoegang beheren met beheerde-browserbeleid met Microsoft Intune](app-configuration-managed-browser.md)|
|Windows Hello voor Bedrijven|Hiermee maakt u integratie met Windows Hello voor Bedrijven mogelijk. Dit is een alternatieve aanmeldingsmethode voor Windows 10 waarbij on-premises Active Directory of Azure Active Directory wordt gebruikt ter vervanging van een wachtwoord, smartcards of virtuele smartcards.|[Instellingen van Windows Hello voor Bedrijven beheren op apparaten met Microsoft Intune](windows-hello.md)|
|Apps die zijn gekocht via het volume-aankoopprogramma|Hiermee kunt u apps beheren die u via een volume-aankoopprogramma hebt gekocht, door de licentiegegevens uit de App Store te importeren en bij te houden hoeveel licenties u hebt gebruikt. Zo wordt voorkomen dat u meer exemplaren van de app installeert dan u hebt gekocht.|[Met Microsoft Intune apps beheren die zijn gekocht via het volume-aankoopprogramma](vpp-apps.md)|

## <a name="company-resource-access"></a>Toegang tot bedrijfsresources

|Mogelijkheid|Details|Meer informatie|
|--------------|-----------|--------------------|
|Certificaatprofielen|Hiermee kunt u vertrouwd-certificaatprofielen en SCEP-certificaten (Simple Certificate Enrollment Protocol) maken en implementeren, die kunnen worden gebruikt om Wi-Fi-, VPN- en e-mailprofielen te beveiligen en verifiëren.|[Toegang tot beveiligde bronnen met certificaatprofielen in Microsoft Intune](certificates-configure.md)|
|Wi-Fi-profielen|Hiermee kunt u instellingen voor draadloze netwerken implementeren voor uw gebruikers. Als u deze instellingen implementeert, kan de gebruiker zonder veel moeite verbinding met het bedrijfsnetwerk maken.|[Wi-Fi-verbindingen in Microsoft Intune](wi-fi-settings-configure.md)|
|E-mailprofielen|Hiermee worden e-mailinstellingen gemaakt en op apparaten geïmplementeerd zodat gebruikers toegang kunnen krijgen tot zakelijke e-mail op hun eigen apparaten zonder dat ze zelf instellingen hoeven te configureren.|[De toegang tot zakelijke e-mail configureren met e-mailprofielen bij Microsoft Intune](email-settings-configure.md)|
|VPN-profielen|Hiermee kunt u VPN-instellingen implementeren voor gebruikers en apparaten in uw organisatie. Als u deze instellingen implementeert, kan de gebruiker zonder veel moeite verbinding maken met bronnen op het bedrijfsnetwerk.|[VPN-verbindingen in Microsoft Intune](device-profiles.md#vpn)|
|Beleid voor voorwaardelijke toegang|Hiermee kunt u toegang tot Microsoft Exchange-e-mailberichten en SharePoint Online beheren vanaf apparaten die niet worden beheerd door Intune.|[Toegang tot e-mail en SharePoint beperken met Microsoft Intune](app-based-conditional-access-intune.md)|

## <a name="next-steps"></a>Volgende stappen

[Bekijk een lijst met apparaten die u kunt beheren](device-management.md).
