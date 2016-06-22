---
# required metadata

title: Apps toevoegen | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2b770f4f-6d36-41e4-b535-514b46e29aaa

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Apps toevoegen met Microsoft Intune
Neemt u even de tijd om u in te lezen in de concepten die worden geïntroduceerd in dit onderwerp, voordat u begint met het implementeren van apps met Microsoft Intune. Dit helpt u te begrijpen welke apps u op welk platform kunt implementeren en aan welke vereisten moet worden voldaan voordat u dat doet.

## Typen apps die u kunt implementeren met Intune
U kunt apps implementeren voor alle apparaattypen die worden ondersteund door Intune. Afhankelijk van het type app dat u wilt implementeren, kunnen het proces en de ondersteunde apparaten verschillen. Gebruik de volgende informatie om inzicht te krijgen in wat u wel en niet kunt implementeren.


### **Windows Installer (&#42;.exe, &#42;.msi)**
- Apps van dit type moeten ondersteuning bieden voor installatie op de achtergrond, zonder gebruikersinvoer. Uw appdocumentatie moet alle relevante opdrachtregelopties bevatten om de app op de achtergrond te installeren (bijvoorbeeld **/q**). Een lijst met veelgebruikte opdrachtregelopties vindt u [hier](https://support.microsoft.com/en-us/kb/227091).
- Aanvullende bestanden en mappen die voor het installatieprogramma van de app vereist zijn, moeten beschikbaar zijn op de locatie die u voor de installatiebestanden van de app opgeeft.
- In de meeste gevallen hoeven voor Windows Installer-bestanden (.msi) en Windows Installer Patch-bestanden (.msp) geen opdrachtregelargumenten te worden geïnstalleerd door Intune. Raadpleeg de documentatie van uw app. Als opdrachtregelargumenten vereist zijn, moeten deze worden ingevoerd als naamwaardeparen (zoals TRANSFORMS=custom_transform.mst).

Apps van dit type worden geüpload naar uw cloudopslag.
### **App-pakket voor Android (&#42;.apk-bestand)**
Apps van dit type worden geüpload naar uw cloudopslag.
### **App-pakket voor iOS (&#42;.ipa-bestand)**
- Als u iOS-apps wilt implementeren, moet u een geldig .ipa-pakket hebben.
- Het .ipa-pakket moet zijn ondertekend door Apple en de aangegeven vervaldatum in het inrichtingsprofiel moet geldig zijn. Intune kan iOS-toepassingen met een bedrijfscertificaat distribueren. Niet alle apps met Apple-ontwikkelaarscertificaat worden ondersteund.
- Uw bedrijf moet zijn geregistreerd voor het iOS Developer Enterprise Program.
- Zorg ervoor dat de firewall van uw organisatie toegang geeft tot de inrichtings- en certificeringswebsites voor iOS.
- Er hoeft geen manifestbestand (.plist) te worden geïmplementeerd met de app.

Apps van dit type worden geüpload naar uw cloudopslag.

Op dit moment kunnen eindgebruikers zakelijke apps niet rechtstreeks installeren vanuit de Intune-bedrijfsportal-app voor iOS. Dit wordt veroorzaakt door beperkingen aan apps die worden gepubliceerd in de iOS App Store (zie [Beoordelingsrichtlijnen voor App Store](https://developer.apple.com/app-store/review/guidelines/)). Gebruikers hebben toegang tot zakelijke apps (inclusief beheerde App Store-apps en app-pakketten voor de bedrijfstak) door de bedrijfsportal-app op hun apparaat te starten en vervolgens op de tegel Bedrijfsapps te tikken, waardoor de browser wordt geopend die hen omleidt naar de Intune-webportal.

### **App-pakket voor Windows Phone (&#42;.xap, .appx, .appxbundle)**
- Als u apps wilt implementeren, hebt u een bedrijfscertificaat voor handtekeningen bij programmacode nodig. Voor meer informatie gaat u naar [Windows Phone-beheer instellen met Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md).

Apps van dit type worden geüpload naar uw cloudopslag.

Onderstaand vindt u informatie over de installatie van Line-Of-Business-UWP-apps (Universal Windows Platform) met Intune.

### **App-pakket voor Windows (.appx, .appxbundle)**
- Als u apps wilt implementeren, hebt u een bedrijfscertificaat voor handtekeningen bij programmacode nodig. Voor meer informatie gaat u naar [Windows-apparaatbeheer instellen met Microsoft Intune](set-up-windows-device-management-with-microsoft-intune.md).

Apps van dit type worden geüpload naar uw cloudopslag.
### **Windows Installer via MDM (&#42;.msi)**
Met dit installatieprogramma kunt u op Windows Installer gebaseerde apps maken en implementeren op ingeschreven pc’s waarop Windows 10 wordt uitgevoerd.<br /><br />De volgende punten zijn van toepassing wanneer u dit type installatieprogramma gebruikt:
- U kunt slechts één bestand met de extensie .msi uploaden.
- De productcode en -versie van het bestand worden gebruikt voor detectie van de app.
- Het standaardgedrag voor opnieuw opstarten van de app wordt gebruikt. Intune heeft hierop geen invloed.
- MSI-pakketten per gebruiker worden voor één gebruiker geïnstalleerd.
- MSI-pakketten per computer worden voor alle gebruikers op het apparaat geïnstalleerd.
- Dual-mode MSI-pakketten voeren momenteel alleen installaties voor alle gebruikers op het apparaat uit.
- App-updates worden ondersteund wanneer de MSI-productcode van elke versie dezelfde is.

Apps van dit type worden geüpload naar uw cloudopslag.
### **Externe koppeling**
Gebruikt wanneer u beschikt over een:
- **URL** waarmee gebruikers een app kunnen downloaden uit een app store.
- **Koppeling** naar een web-app die vanuit de webbrowser wordt uitgevoerd.

Apps op basis van externe koppelingen worden niet opgeslagen in de Intune-cloudopslag.
### **Beheerde iOS-app uit de App Store**
Hiermee kunt u gratis iOS-apps uit de App Store beheren en implementeren. U kunt ermee ook [Mobile Application Management-beleid](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) aan [compatibele apps](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) koppelen en hun status controleren in de beheerconsole.<br /><br />Beheerde iOS-apps worden niet opgeslagen in uw Intune-cloudopslag.
> [!TIP] Opties voor mobiele apparaten worden pas beschikbaar wanneer u de [Mobile Device Management-instantie hebt ingesteld](get-ready-to-enroll-devices-in-microsoft-intune.md) op Intune.

## Ondersteuning voor UWP-apps
Bij Windows 10-pc's is geen sideloadsleutel vereist voor de installatie van Line-Of-Business-apps. De registersleutel **HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Appx\AllowAllTrustedApps** moet echter de waarde **1** hebben, zodat extern laden kan worden ingeschakeld.

Als deze registersleutel niet is geconfigureerd, wordt deze waarde door Intune automatisch ingesteld op **1** wanneer u voor het eerst een app op het apparaat implementeert. Als u deze waarde hebt ingesteld op **0**, kan de waarde niet automatisch door Intune worden gewijzigd en mislukt de implementatie van de Line-Of-Business-apps.

Line-Of-Business-UWP-apps moeten zijn ondertekend met een certificaat voor de ondertekening van de programmacode dat wordt vertrouwd op elk apparaat waarop de app is geïmplementeerd. U kunt certificaten gebruiken van een interne PKI-infrastructuur of een certificaat van een openbaar basiscertificaat van derden dat op het apparaat is geïnstalleerd.

Op Windows 10 Mobile-apparaten kunt u een certificaat voor de ondertekening van de programmacode van andere producenten dan Symantec gebruiken voor de ondertekening van universele **.appx**-apps. Voor **.xap**-apps en **.appx**-pakketten die zijn gemaakt voor Windows Phone 8.1 en die u op Windows 10 Mobile-apparaten wilt installeren, moet u een certificaat voor de ondertekening van de programmacode van Symantec gebruiken.

## Volgende stappen 

Vervolgens moet u apps aan de Intune-console toevoegen voordat u ze kunt implementeren. U kunt apps toevoegen voor [geregistreerde apparaten](add-apps-for-mobile-devices-in-microsoft-intune.md), of voor [Windows-pc's die u met de Intune-clientsoftware beheert](add-apps-for-windows-pcs-in-microsoft-intune.md).

<!--HONumber=Jun16_HO2-->


