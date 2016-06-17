---
# required metadata

title: Mogelijkheden voor Mobile Device Management| Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f23b3ee7-78da-4e53-9fc2-78e58401bcf9

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---
# Mogelijkheden voor Mobile Device Management in Microsoft Intune

Met Microsoft Intune kunt u vele apparaten beheren door ze *in te schrijven* bij de service. Gebruikers kunnen vervolgens een *bedrijfsportal* gebruiken om allerlei bewerkingen uit te voeren, zoals hun apparaat registreren, zoeken naar en installeren van apps, ervoor zorgen dat het apparaat voldoet aan het bedrijfsbeleid en contact opnemen met de IT-ondersteuning.
Dit onderwerp bevat een volledige lijst van de mogelijkheden die geregistreerde apparaten u bieden.

Beheer, inventarisatie, app-implementatie, inrichting en buitengebruikstelling worden alle afgehandeld via de Intune-beheerconsole. Gebruikers krijgen toegang tot de bedrijfsportal waar ze apps kunnen installeren, apparaten kunnen inschrijven en verwijderen en contact kunnen opnemen met hun IT-afdeling of helpdesk.



## Apparaatbeveiliging en -configuratie

|Mogelijkheid|Details|Meer informatie|
|--------------|-----------|--------------------|
|Configuratiebeleid<br><br>Aangepast beleid|Met configuratiebeleid voor mobiele apparaten kunt u veel instellingen en functies op mobiele apparaten in uw organisatie beheren. U kunt bijvoorbeeld een wachtwoord vereisen, het aantal mislukte pogingen beperken, het aantal minuten beperken voordat het scherm wordt vergrendeld, instellen dat wachtwoorden verlopen en voorkomen dat eerder gebruikte wachtwoorden opnieuw worden gebruikt. U kunt ook het gebruik van hardware- en softwarefuncties controleren, zoals de camera of de webbrowser van het apparaat.<br><br>Gebruik aangepast beleid wanneer configuratiebeleid niet de instelling bevat die u nodig hebt. Op iOS-apparaten kunt u instellingen importeren die u hebt geëxporteerd uit de Apple Configurator Tool. Op andere apparaten kunt u OMA-URI-instellingen gebruiken om instellingen en functies op het apparaat te configureren.|[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)<br />|
|Wissen op afstand, vergrendelen op afstand en wachtwoordcode opnieuw instellen|Gevoelige gegevens wissen wanneer een apparaat is vermist of gestolen. U kunt bijvoorbeeld het apparaat op afstand vergrendelen, de fabrieksinstellingen terugzetten of alleen bedrijfsgegevens wissen.<br>U kunt wachtwoordcodes opnieuw instellen als gebruikers geen toegang meer krijgen tot hun apparaat, verloren of gestolen apparaten vergrendelen of zelfs gegevens op verloren of gestolen apparaten wissen.|[Uw gegevens beschermen met vergrendelen op afstand of het opnieuw instellen van de wachtwoordcode](/intune/deploy-use/use-remote-lock-and-passcode-reset-in-microsoft-intune) en [Apparaten buiten gebruik stellen vanuit Intune-beheer](/intune/deploy-use/retire-devices-from-microsoft-intune-management)|
|Kioskmodus|Hiermee kunt u bepaalde functies van mobiele apparaten, zoals schermafbeelding en de aan/uit-knop, vergrendelen. U kunt hiermee apparaten ook beperken tot het uitvoeren van een enkele app die u opgeeft.|[Beleidsinstellingen voor iOS-configuraties in Microsoft Intune](/intune/deploy-use/ios-policy-settings-in-microsoft-intune)|

## Appbeheer

|Mogelijkheid|Details|Meer informatie|
|--------------|-----------|--------------------|
|Implementatie en beheer van apps|Biedt een reeks hulpmiddelen voor het beheren van mobiele apps gedurende hun levensduur, met inbegrip van app-implementatie vanaf de installatiebestanden en vanuit app stores, gedetailleerde bewaking van app-status en verwijdering van de app.|[Apps in Microsoft Intune implementeren](/intune/deploy-use/deploy-apps)|
|Compatibele en niet-compatibele apps|Hiermee kunt u een lijst opgeven met compatibele apps (die gebruikers mogen installeren) en niet-compatibele apps (die gebruikers niet mogen installeren).|[Instellingen voor iOS-beleid in Microsoft Intune](/intune/deploy-use/ios-policy-settings-in-microsoft-intune)|
|Beheer van mobiele toepassingen|Met behulp van beheer voor mobiele toepassingen configureert u beperkingen voor apps, zowel voor apparaten die u met Intune beheert, als voor apparaten die niet met Intune worden beheerd. Zo kunt u de beveiliging van uw bedrijfsgegevens verbeteren door het beperken van bewerkingen zoals kopiëren en plakken, externe back-up van gegevens en gegevensoverdracht tussen apps.|[Configure and deploy mobile application management policies in the Microsoft Intune console](/intune/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console)<br><br>[Beleid voor Mobile App Management maken en implementeren met Microsoft Intune](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)<br /><br />[iOS-apps voorbereiden voor Mobile Application Management met de Microsoft Intune App Wrapping Tool](/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)<br /><br />[Android-apps voorbereiden voor Mobile Application Management met de Microsoft Intune App Wrapping Tool](/intune/deploy-use/prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)|
|Configuratie van mobiele apps|Gebruik configuratiebeleid voor mobiele apps om voor iOS-apps instellingen op te geven die mogelijk vereist zijn wanneer de gebruiker de app uitvoert. Een app kan bijvoorbeeld vereisen dat de gebruiker een poortnummer of aanmeldingsgegevens moet opgeven. Zo kunt u de app-configuratie stroomlijnen en het aantal telefoontjes naar de helpdesk voor ondersteuning verminderen.|[iOS-apps met configuratiebeleid voor mobiele apps in Microsoft Intune configureren](/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)|
|Beheerde browser|Nadat u de beheerde browser voor uw gebruikers hebt geïmplementeerd, kunt u een beheerde-browserbeleid configureren om te bepalen welke websites ze kunnen bezoeken. U kunt bovendien ook Mobile Application Management-beleid toepassen op de beheerde browser.|[Internettoegang beheren met beheerde-browserbeleid met Microsoft Intune](/intune/deploy-use/manage-internet-access-using-managed-browser-policies)|
|Microsoft Passport|Intune biedt de mogelijkheid van integratie met Microsoft Passport for Work. Dit is een alternatieve aanmeldingsmethode voor Windows 10 waarbij Active Directory of een Azure Active Directory-account wordt gebruikt ter vervanging van een wachtwoord, smartcard of virtuele smartcard.|[Microsoft Passport-instellingen beheren op apparaten met Microsoft Intune](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune)|

## Toegang tot bedrijfsresources

|Mogelijkheid|Details|Meer informatie|
|--------------|-----------|--------------------|
|Certificaatprofielen|Hier kunt u vertrouwd-certificaatprofielen en SCEP-certificaten (Simple Certificate Enrollment Protocol) maken en implementeren, die kunnen worden gebruikt om Wi-Fi-, VPN-, en e-mailprofielen te beveiligen en verifiëren.|[Toegang tot beveiligde bronnen met certificaatprofielen in Microsoft Intune](/intune/deploy-use/secure-resource-access-with-certificate-profiles)|
|Wi-Fi-profielen|Hier kunt u instellingen voor draadloze netwerken implementeren voor uw gebruikers. Als u deze instellingen implementeert, kan de eindgebruiker zonder veel moeite verbinding met het bedrijfsnetwerk maken.|[Wi-Fi-verbindingen in Microsoft Intune](/intune/deploy-use/wi-fi-connections-in-microsoft-intune)|
|E-mailprofielen|Hier kunt u e-mailinstellingen maken en op apparaten implementeren. Hiermee hebben gebruikers toegang tot bedrijfse-mail op hun eigen apparaten zonder dat ze zelf instellingen moeten doorvoeren.|[De toegang tot zakelijke e-mail configureren met e-mailprofielen bij Microsoft Intune](/intune/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune)|
|VPN-profielen|Hier kunt u VPN-instellingen implementeren voor gebruikers en apparaten in uw organisatie. Door het implementeren van deze instellingen minimaliseert u de eindgebruikersinspanningen die vereist zijn om verbinding te maken met resources op het bedrijfsnetwerk.|[VPN-verbindingen in Microsoft Intune](/intune/deploy-use/vpn-connections-in-microsoft-intune)|
|Beleid voor voorwaardelijke toegang|Hiermee kunt u toegang tot Microsoft Exchange-e-mailberichten en SharePoint Online beheren vanaf apparaten die niet worden beheerd door Intune.|[Toegang tot e-mail en SharePoint beperken met Microsoft Intune](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)|

## Inventarisatie en rapportage

|Mogelijkheid|Details|Meer informatie|
|--------------|-----------|--------------------|
|Inventarisatie en rapportage|Hier zoekt u naar informatie over de apparaten die u beheert en de software die ze gebruiken.|[Inzicht in uw apparaten met inventarisaties in Microsoft Intune](./deploy-use/understand-your-devices-with-inventory-in-microsoft-intune)|


### Zie ook
[Beheermogelijkheden voor Windows-pc’s in Microsoft Intune](./windows-pc-management-capabilities-in-microsoft-intune.md)


<!--HONumber=May16_HO2-->


