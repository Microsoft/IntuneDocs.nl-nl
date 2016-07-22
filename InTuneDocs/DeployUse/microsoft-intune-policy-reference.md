---
# required metadata

title: Documentatie voor Microsoft Intune-beleid | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: d27f2739-9791-4aae-a9db-01a4e59ccfe5

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Documentatie voor Microsoft Intune-beleid

Gebruik de informatie in dit onderwerp om u te helpen bepalen welk Microsoft Intune-beleid u moet gebruiken voor het beheren van uw apparaten.

> [!TIP]
> Zie [Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) voor gedetailleerdere informatie over het gebruik van beleid..


## Configuratiebeleid voor Android

|Naam van beleid|Gebruik dit beleid wanneer u het volgende wilt doen|
|---------------|------------------------|
|**Aangepaste configuratie (Android 4 en hoger, Samsung KNOX Standard 4.0 en hoger)**|OMA-URI-instellingen implementeren, zoals Wi-Fi-instellingen die kunnen worden gebruikt om functies op Android-apparaten te beheren. Dit is handig wanneer de instelling die u nodig hebt, niet beschikbaar is in een configuratiebeleid.<br /><br />Zie [Instellingen voor Android-beleid in Microsoft Intune](android-policy-settings-in-microsoft-intune.md) voor meer informatie..|
|**E-mailprofiel (Samsung KNOX Standard 4.0 en hoger)**|E-mailinstellingen voor Exchange ActiveSync maken, implementeren en bewaken op beheerde apparaten. Hiermee hebben gebruikers toegang tot bedrijfse-mail op hun eigen apparaten zonder dat ze zelf instellingen moeten doorvoeren.<br /><br />Zie [De toegang tot zakelijke e-mail configureren met e-mailprofielen bij Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md) voor meer informatie..|
|**Algemene configuratie (Android 4 en hoger, Samsung KNOX Standard 4.0 en hoger)**|Beveiligings- en functionele instellingen voor mobiele apparaten configureren.<br />Apps opgeven die compatibel of niet-compatibel zijn en rapporteren wanneer deze worden gebruikt.<br />Kioskmodus configureren waarmee apparaten worden vergrendeld zodat alleen bepaalde functies werken. U kunt bijvoorbeeld toestaan dat het apparaat slechts één app uitvoert of u kunt de volumeknoppen uitschakelen.<br /><br />Zie [Instellingen voor Android-beleid in Microsoft Intune](android-policy-settings-in-microsoft-intune.md) voor meer informatie..|
|**PKCS #12 (. PFX)-certificaatprofiel (Android 4 en hoger)**|Gebruik dit profiel om PFX-instellingen te maken en implementeren voor certificaataanvragen voor apparaten.<br /><br />Zie [Toegang tot beveiligde bronnen met certificaatprofielen in Microsoft Intune](secure-resource-access-with-certificate-profiles.md) voor meer informatie..|
|**SCEP-certificaatprofiel (Android 4 en hoger)**|Hier kunt u een Simple Certificate Enrollment Protocol-certificaat configureren dat met een vertrouwd certificaat voor mobiele apparaten kan worden gebruikt om mobiele apparaten te verifiëren zodat ze toegang krijgen tot netwerkresources, zoals bijvoorbeeld netwerkresources die zijn geconfigureerd met Wi-Fi- en VPN-profielen.<br /><br />Zie [Toegang tot beveiligde bronnen met certificaatprofielen in Microsoft Intune](secure-resource-access-with-certificate-profiles.md) voor meer informatie..|
|**Vertrouwd-certificaatprofiel (Android 4 en hoger)**|Hier kunt u een vertrouwd certificaat voor mobiele apparaten configureren dat kan worden gebruikt voor verificatie van mobiele apparaten zodat ze toegang krijgen tot netwerkresources zoals die zijn geconfigureerd met Wi-Fi- en VPN-profielen.<br /><br />Zie [Toegang tot beveiligde bronnen met certificaatprofielen in Microsoft Intune](secure-resource-access-with-certificate-profiles.md) voor meer informatie..|
|**VPN-profiel (Android 4 en hoger)**|Hier kunt u instellingen configureren en implementeren waarmee gebruikers beveiligde toegang tot uw bedrijfsnetwerk krijgen vanaf hun mobiele apparaat. Als u deze instellingen implementeert, kan de eindgebruiker zonder veel moeite verbinding met zijn werk maken.<br /><br />Zie [VPN-verbindingen in Microsoft Intune](vpn-connections-in-microsoft-intune.md) voor meer informatie..|
|**Wi-Fi-profiel (Android 4 en hoger)**|Hier kunt u instellingen voor draadloze netwerken configureren en implementeren voor gebruikers in uw organisatie. Als u deze instellingen implementeert, kan de eindgebruiker zonder veel moeite verbinding met het draadloze netwerk maken.<br /><br />Zie [Wi-Fi-verbindingen in Microsoft Intune](wi-fi-connections-in-microsoft-intune.md) voor meer informatie..|

## Configuratiebeleid voor iOS

|Naam van beleid|Gebruik dit beleid wanneer u het volgende wilt doen|
|---------------|------------------------|
|**Aangepaste configuratie (iOS 7.1 en hoger)**|Hier kunt u configuratieprofielen implementeren op iOS-apparaten, welke profielen u hebt gemaakt met het hulpprogramma Apple Configurator. Dit is handig wanneer de instelling die u nodig hebt, niet beschikbaar is in een configuratiebeleid.<br /><br />Zie [Instellingen voor iOS-beleid in Microsoft Intune](ios-policy-settings-in-microsoft-intune.md) voor meer informatie..|
|**E-mailprofiel (iOS 7.1 en hoger)**|E-mailinstellingen voor Exchange ActiveSync maken, implementeren en bewaken op beheerde apparaten. Hiermee hebben gebruikers toegang tot bedrijfse-mail op hun eigen apparaten zonder dat ze zelf instellingen moeten doorvoeren.<br /><br />Zie [De toegang tot zakelijke e-mail configureren met e-mailprofielen bij Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md) voor meer informatie..|
|**Algemene configuratie (iOS 7.1 en hoger)**|Beveiligings- en functionele instellingen voor mobiele apparaten configureren.<br />- Apps opgeven die compatibel of niet-compatibel zijn en rapporteren wanneer deze worden gebruikt.<br />Kioskmodus configureren waarmee apparaten worden vergrendeld zodat alleen bepaalde functies werken. U kunt bijvoorbeeld toestaan dat het apparaat slechts één app uitvoert of u kunt de volumeknoppen uitschakelen.<br /><br />Zie [Instellingen voor iOS-beleid in Microsoft Intune](ios-policy-settings-in-microsoft-intune.md) voor meer informatie..|
|**SCEP-certificaatprofiel (iOS 7.1 en hoger)**|Hier kunt u een Simple Certificate Enrollment Protocol-certificaat configureren dat met een vertrouwd certificaat voor mobiele apparaten kan worden gebruikt om mobiele apparaten te verifiëren zodat ze toegang krijgen tot netwerkresources, zoals bijvoorbeeld netwerkresources die zijn geconfigureerd met Wi-Fi- en VPN-profielen.<br /><br />Zie [Toegang tot beveiligde bronnen met certificaatprofielen in Microsoft Intune](secure-resource-access-with-certificate-profiles.md) voor meer informatie..|
|**Vertrouwd-certificaatprofiel (iOS 7.1 en hoger)**|Hier kunt u een vertrouwd certificaat voor mobiele apparaten configureren dat kan worden gebruikt voor verificatie van mobiele apparaten zodat ze toegang krijgen tot netwerkresources zoals die zijn geconfigureerd met Wi-Fi- en VPN-profielen.<br /><br />Zie [Toegang tot beveiligde bronnen met certificaatprofielen in Microsoft Intune](secure-resource-access-with-certificate-profiles.md) voor meer informatie..|
|**VPN-profiel (iOS 7.1 en hoger)**|Hier kunt u instellingen configureren en implementeren waarmee gebruikers beveiligde toegang tot uw bedrijfsnetwerk krijgen vanaf hun mobiele apparaat. Als u deze instellingen implementeert, kan de eindgebruiker zonder veel moeite verbinding met zijn werk maken.<br /><br />Zie [VPN-verbindingen in Microsoft Intune](vpn-connections-in-microsoft-intune.md) voor meer informatie..|
|**Wi-Fi-profiel (iOS 7.1 en hoger)**|Hier kunt u instellingen voor draadloze netwerken configureren en implementeren voor gebruikers in uw organisatie. Als u deze instellingen implementeert, kan de eindgebruiker zonder veel moeite verbinding met het draadloze netwerk maken.<br /><br />Zie [Wi-Fi-verbindingen in Microsoft Intune](wi-fi-connections-in-microsoft-intune.md) voor meer informatie..|
|**Configuratiebeleid voor mobiele apps (iOS 7.1 en hoger)**|Gebruik het configuratiebeleid voor mobiele apps om automatisch instellingen op te geven die mogelijk vereist zijn wanneer de gebruiker een iOS-app uitvoert.<br /><br />Zie [iOS-apps met configuratiebeleid voor mobiele apps in Microsoft Intune configureren](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md) voor meer informatie..|

## Configuratiebeleid voor Mac OS X

|Naam van beleid|Gebruik dit beleid wanneer u het volgende wilt doen|
|---------------|------------------------|
|**Aangepaste configuratie (Mac OS X 10.9 en hoger)**|Hier kunt u configuratieprofielen u met het hulpprogramma Apple Configurator hebt gemaakt, implementeren op Mac-computers. Dit is handig wanneer de instelling die u nodig hebt, niet beschikbaar is in een configuratiebeleid.<br /><br />Zie [Instellingen voor Mac OS X-beleid in Microsoft Intune](mac-os-x-policy-settings-in-microsoft-intune.md) voor meer informatie..|
|**Algemene configuratie (Mac OS X 10.9 en hoger)**|Beveiligings- en functionele instellingen voor mobiele apparaten configureren.<br />Apps opgeven die compatibel of niet-compatibel zijn en rapporteren wanneer deze worden gebruikt.<br /><br />Zie [Instellingen voor Mac OS X-beleid in Microsoft Intune](mac-os-x-policy-settings-in-microsoft-intune.md) voor meer informatie..|
|**SCEP-certificaatprofiel (Mac OS X 10.9 en hoger)**|Hier kunt u een Simple Certificate Enrollment Protocol-certificaat configureren dat met een vertrouwd certificaat voor mobiele apparaten kan worden gebruikt om mobiele apparaten te verifiëren zodat ze toegang krijgen tot netwerkresources, zoals bijvoorbeeld netwerkresources die zijn geconfigureerd met Wi-Fi- en VPN-profielen.<br /><br />Zie [Toegang tot beveiligde bronnen met certificaatprofielen in Microsoft Intune](secure-resource-access-with-certificate-profiles.md) voor meer informatie..|
|**Vertrouwd-certificaatprofiel (Mac OS X 10.9 en hoger)**|Hier kunt u een vertrouwd certificaat voor mobiele apparaten configureren dat kan worden gebruikt voor verificatie van mobiele apparaten zodat ze toegang krijgen tot netwerkresources zoals die zijn geconfigureerd met Wi-Fi- en VPN-profielen.<br /><br />Zie [Toegang tot beveiligde bronnen met certificaatprofielen in Microsoft Intune](secure-resource-access-with-certificate-profiles.md) voor meer informatie..|
|**VPN-profiel (Mac OS X 10.9 en hoger)**|Hier kunt u instellingen configureren en implementeren waarmee gebruikers beveiligde toegang tot uw bedrijfsnetwerk krijgen vanaf hun mobiele apparaat. Als u deze instellingen implementeert, kan de eindgebruiker zonder veel moeite verbinding met zijn werk maken.<br /><br />Zie [VPN-verbindingen in Microsoft Intune](vpn-connections-in-microsoft-intune.md) voor meer informatie..|
|**Wi-Fi-profiel (Mac OS X 10.9 en hoger)**|Hier kunt u instellingen voor draadloze netwerken configureren en implementeren voor gebruikers in uw organisatie. Als u deze instellingen implementeert, kan de eindgebruiker zonder veel moeite verbinding met het draadloze netwerk maken.<br /><br />Zie [Wi-Fi-verbindingen in Microsoft Intune](wi-fi-connections-in-microsoft-intune.md) voor meer informatie..|

## Configuratiebeleid voor Windows
Is alleen van toepassing op Windows Phone-apparaten en ingeschreven Windows-apparaten.

|Naam van beleid|Gebruik dit beleid wanneer u het volgende wilt doen|
|---------------|------------------------|
|**Aangepaste configuratie (Windows 10 Desktop en Mobile en hoger)**|OMA-URI-instellingen implementeren die kunnen worden gebruikt om apparaatfuncties te besturen. Dit is handig wanneer de instelling die u nodig hebt, niet beschikbaar is in een configuratiebeleid.<br />    Zie [Instellingen voor Windows 10-beleid in Microsoft Intune](windows-10-policy-settings-in-microsoft-intune.md) voor meer informatie..|
|**Aangepaste configuratie (Windows Phone 8.1 en hoger)**|OMA-URI-instellingen implementeren die kunnen worden gebruikt om apparaatfuncties te besturen. Dit is handig wanneer de instelling die u nodig hebt, niet beschikbaar is in een configuratiebeleid.<br /><br />Zie [Instellingen voor Windows Phone 8.1-beleid in Microsoft Intune](windows-phone-8-1-policy-settings-in-microsoft-intune.md) voor meer informatie..|
|**Beleid voor editie-upgrades (Windows 10 Desktop en hoger)**<br><br>**Beleid voor editie-upgrades (Windows 10 Holographic en hoger)**|Configureren en implementeren van beleid met licentie- of productsleutelgegevens dat wordt gebruikt voor het bijwerken van Windows 10-apparaten naar een nieuwere versie.<br><br>Zie [Beleidsinstellingen in Microsoft Intune voor upgrades van de Windows-editie](edition-upgrade-policy-settings-in-microsoft-intune.md) voor meer informatie..|  
|**E-mailprofiel (Windows Phone 8 en hoger)**<br /><br />**E-mailprofiel (Windows 10 Desktop en Mobile en hoger)**|E-mailinstellingen voor Exchange ActiveSync maken, implementeren en bewaken op beheerde apparaten. Hiermee hebben gebruikers toegang tot bedrijfse-mail op hun eigen apparaten zonder dat ze zelf instellingen moeten doorvoeren.<br /><br />Zie [De toegang tot zakelijke e-mail configureren met e-mailprofielen bij Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md) voor meer informatie..|
|**Algemene configuratie (Windows 10 Desktop en Mobile en hoger)**|Beveiligings- en functionele instellingen voor mobiele apparaten configureren voor ingeschreven Windows 10 Desktop- en Mobile-apparaten.<br /><br />Zie [Instellingen voor Windows 10-beleid in Microsoft Intune](windows-10-policy-settings-in-microsoft-intune.md) voor meer informatie..|
|**Algemene configuratie (Windows 10 Team en hoger)**|Configureer de apparaatbeveiliging en functionele instellingen voor ingeschreven Windows 10 Team-apparaten (bijvoorbeeld een Surface Hub-apparaat).<br /><br />Zie [Instellingen voor configuratiebeleid voor Windows Team in Microsoft Intune](windows-team-configuration-policy-settings-in-microsoft-intune.md) voor meer informatie..|
|**Algemene configuratie (Windows 8.1 en hoger)**|Beveiligings- en functionele instellingen voor mobiele apparaten configureren voor ingeschreven Windows-apparaten.<br /><br />Zie [Instellingen voor Windows-beleid in Microsoft Intune](windows-configuration-policy-settings-in-microsoft-intune.md) voor meer informatie..|
|**Algemene configuratie (Windows Phone 8.1 en hoger)**|Beveiligings- en functionele instellingen voor mobiele apparaten configureren.<br />Hier kunt u apps opgeven die gebruikers al dan niet kunnen gebruiken en de installatie of het gebruik van niet-compatibele apps blokkeren.<br /><br />Zie [Instellingen voor Windows Phone 8.1-beleid in Microsoft Intune](windows-phone-8-1-policy-settings-in-microsoft-intune.md) voor meer informatie..|
|**PKCS #12 (. PFX)-certificaatprofiel (Windows 10 Desktop en Mobile en hoger)**|Gebruik dit profiel om PFX-instellingen te maken en implementeren voor certificaataanvragen voor apparaten.<br /><br />Zie [Toegang tot beveiligde bronnen met certificaatprofielen in Microsoft Intune](secure-resource-access-with-certificate-profiles.md) voor meer informatie..|
|**SCEP-certificaatprofiel (Windows 8.1 en hoger)**<br /><br />**SCEP-certificaatprofiel (Windows Phone 8.1 en hoger)**|Hier kunt u een Simple Certificate Enrollment Protocol-certificaat configureren dat met een vertrouwd certificaat voor mobiele apparaten kan worden gebruikt om mobiele apparaten te verifiëren zodat ze toegang krijgen tot netwerkresources, zoals bijvoorbeeld netwerkresources die zijn geconfigureerd met Wi-Fi- en VPN-profielen.<br /><br />Zie [Toegang tot beveiligde bronnen met certificaatprofielen in Microsoft Intune](secure-resource-access-with-certificate-profiles.md) voor meer informatie..|
|**Vertrouwd certificaatprofiel (Windows 8.1 en hoger)**<br /><br />**Vertrouwd-certificaatprofiel (Windows Phone 8.1 en hoger)**|Hier kunt u een vertrouwd certificaat voor mobiele apparaten configureren dat kan worden gebruikt voor verificatie van mobiele apparaten zodat ze toegang krijgen tot netwerkresources zoals die zijn geconfigureerd met Wi-Fi- en VPN-profielen.<br /><br />Zie [Toegang tot beveiligde bronnen met certificaatprofielen in Microsoft Intune](secure-resource-access-with-certificate-profiles.md) voor meer informatie.).|
|**VPN-profiel (Windows 10 Desktop en Mobile en hoger)**<br /><br />**VPN-profiel (Windows 8.1 en hoger)**<br /><br />**VPN-profiel (Windows Phone 8.1 en hoger)**|Hier kunt u instellingen configureren en implementeren waarmee gebruikers beveiligde toegang tot uw bedrijfsnetwerk krijgen vanaf hun mobiele apparaat. Als u deze instellingen implementeert, kan de eindgebruiker zonder veel moeite verbinding met zijn werk maken.<br /><br />Zie [VPN-verbindingen in Microsoft Intune](vpn-connections-in-microsoft-intune.md) voor meer informatie..|
|**Wi-Fi importeren**|Hier kunt u Windows Wi-Fi-configuraties die u eerder naar een bestand hebt geëxporteerd, importeren en implementeren.<br /><br />Zie [Wi-Fi-verbindingen in Microsoft Intune](wi-fi-connections-in-microsoft-intune.md) voor meer informatie..|

## Beleid voor software

|Naam van beleid|Gebruik dit beleid wanneer u het volgende wilt doen|
|---------------|------------------------|
|**Beheerde-browserbeleid (Android 4 en hoger)**<br /><br />**Managed Browser-beleid (iOS 7.1 en hoger)**|Hier kunt u de websites opgeven waartoe gebruikers al dan geen toegang hebben wanneer ze de beheerde-browserapp gebruiken.<br /><br />Zie [Internettoegang beheren met beheerde-browserbeleid met Microsoft Intune](manage-internet-access-using-managed-browser-policies.md) voor meer informatie..|
|**Mobile Application Management-beleid (Android 4 en hoger)**<br /><br />**Mobile Application Management-beleid (iOS 7.1 en hoger)**|Hier kunt u de functionaliteit wijzigen van apps die u implementeert om ervoor te zorgen dat de apps in overeenstemming zijn met het nalevings- en beveiligingsbeleid van uw bedrijf. U kunt bijvoorbeeld knip-, kopieer- en plakbewerkingen beperken in een beperkte app of een app configureren om alle webkoppelingen te openen binnen de beheerde browser.<br /><br />Zie [Mobile Application Management-beleid configureren en implementeren in de Microsoft Intune-console](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) voor meer informatie.|

## Algemene instellingen voor mobiele apparaten

|Naam van beleid|Gebruik dit beleid wanneer u het volgende wilt doen|
|---------------|------------------------|
|**Exchange ActiveSync-beleid**|Beveiligings- en functionele instellingen voor mobiele apparaten configureren voor apparaten die worden beheerd door Exchange ActiveSync.<br /><br />Zie [Exchange ActiveSync-beleidsinstellingen in Microsoft Intune](exchange-activesync-policy-settings-in-microsoft-intune.md) voor meer informatie..|
|**Beveiligingsbeleid voor mobiele apparaten**|<ul><li>Hiermee worden instellingen geconfigureerd voor mobiele apparaten (alle platforms), waaronder:<br /><br /><ul><li>Beveiliging</li><li>Versleuteling</li><li>Systeem</li><li>E-mail</li><li>Toepassingen</li></ul></li></ul> **Belangrijk:** Microsoft Intune bevat nu afzonderlijk **configuratiebeleid** voor elk apparaatplatform. Dit beleid bevat de meest recente instellingen die u kunt gebruiken. U kunt het beveiligingsbeleid voor mobiele apparaten blijven gebruiken en eventuele bestaande implementaties zullen nog steeds werken, maar u moet echter zo snel mogelijk naar de nieuwe configuratiebeleidsregels migreren.<br />Zie [Instellingen voor beveiligingsbeleid van mobiele apparaten in Microsoft Intune](mobile-device-security-policy-settings-in-microsoft-intune.md) voor meer informatie..|

## Beleid voor voorwaardelijke toegang en nalevingsbeleid

### Voorwaardelijke toegang

|Naam van beleid|Gebruik dit beleid wanneer u het volgende wilt doen|
|---------------|------------------------|
|**Exchange Online-beleid**<br /><br />**Beleid voor Exchange On-Premises**|Toegang tot Microsoft Exchange-e-mail beheren vanaf apparaten die niet worden beheerd door Intune of die niet compatibel zijn met nalevingsbeleid dat u hebt gemaakt.<br /><br />Zie [De toegang beperken tot e-mail bij Exchange Online en de nieuwe Exchange Online Dedicated-omgeving met Intune](restrict-access-to-exchange-online-with-microsoft-intune.md) voor meer informatie..|
|**Beleid voor SharePoint Online**|Toegang tot SharePoint Online beheren vanaf apparaten die niet worden beheerd door Intune of die niet compatibel zijn met nalevingsbeleid dat u hebt gemaakt.<br /><br />Zie [Toegang tot SharePoint Online beperken met Microsoft Intune](restrict-access-to-sharepoint-online-with-microsoft-intune.md) voor meer informatie..|
|**Skype voor bedrijven**|Toegang tot Skype voor Bedrijven beheren vanaf apparaten die niet worden beheerd door Intune of die niet compatibel zijn met nalevingsbeleid dat u hebt gemaakt.<br /><br />Zie [Toegang tot Skype voor Bedrijven beperken met Microsoft Intune](restrict-access-to-skype-for-business-online-with-microsoft-intune.md) voor meer informatie..|
> [!NOTE]
> U implementeert geen beleidsregels voor voorwaardelijke toegang voor gebruikers en apparaten. In plaats daarvan configureert u het vereiste beleid dat van toepassing is op alle groepen waarop het beleid is gericht.

### Nalevingsbeleid

|Naam van beleid|Gebruik dit beleid wanneer u het volgende wilt doen|
|---------------|------------------------|
|**Nalevingsbeleid**|Het compatibiliteitsniveau voor apparaten definiëren en vervolgens apparaten rapporteren die niet-compatibel zijn. Deze beleidsregels worden gebruikt met voorwaardelijke toegang om apparaten te evalueren die geen toegang tot services mogen hebben.<br /><br />Zie [Nalevingsbeleid voor apparaten in Microsoft Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md) voor meer informatie..|

## Windows-pc-beheer

|Naam van beleid|Gebruik dit beleid wanneer u het volgende wilt doen|
|---------------|------------------------|
|**Instellingen voor Microsoft Intune-Agent**|De Intune-pc-client op computers configureren, inclusief instellingen voor:<br /><br />- Endpoint Protection<br />- Software-updates<br />- Beleidscontroleschema<br /><br />Dit type beleid kan alleen worden geïmplementeerd op groepen van apparaten.<br /><br />Intune-clients downloaden nieuwe en bijgewerkte beleidsregels volgens de instelling **Detectiefrequentie voor updates en toepassingen** die een standaardwaarde heeft van 8 uur. U kunt echter op elk gewenst moment een vernieuwing van het beleid afdwingen op computers.<br /><br />Zie [Windows-pc’s up-to-date houden met software-updates in Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) voor meer informatie..|
|**Microsoft Intune Center-instellingen**|Details configureren die worden weergegeven in het Microsoft Intune Center op beheerde computers.<br /><br />Dit type beleid kan alleen worden geïmplementeerd op groepen van apparaten.<br /><br />Zie [Algemene beheertaken voor Windows-pc’s met de Microsoft Intune-computerclient voor meer informatie](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)..|
|**Windows Firewall-instellingen**|Hiermee worden Windows Firewall-instellingen en -uitzonderingen geconfigureerd voor algemene netwerkcommunicatie op computers, waaronder:<br /><br />- BranchCache<br />- Hulp op afstand<br />- Media delen<br /><br />Dit type beleid kan alleen worden geïmplementeerd op groepen van apparaten.<br /><br />Zie [Help Windows-pc's beveiligen met Endpoint Protection Help voor Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) voor meer informatie..|

### Zie ook

[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=May16_HO1-->


