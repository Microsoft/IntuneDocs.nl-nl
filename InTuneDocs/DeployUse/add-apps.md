---
title: Apps toevoegen | Microsoft Intune
description: "Neemt u even de tijd om u in te lezen in de concepten die worden geïntroduceerd in dit onderwerp, voordat u begint met het implementeren van apps met Intune."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b770f4f-6d36-41e4-b535-514b46e29aaa
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c880bd9dfb998355a18e78af898a96d4cee393f7
ms.openlocfilehash: c4b1e5d3bb8b949096f7d15ddbbf0d1540485d0d


---

# Apps toevoegen met Microsoft Intune
Neemt u even de tijd om u in te lezen in de concepten die worden geïntroduceerd in dit onderwerp, voordat u begint met het implementeren van apps met Microsoft Intune. Deze begrippen helpen u te begrijpen welke apps u op welk platform kunt implementeren. Ze helpen u ook om inzicht te krijgen in de vereisten waaraan moet worden voldaan voordat u de apps kunt implementeren.

## Typen apps die u kunt implementeren

### Software-installatieprogramma

|App-type|Details|
|----------------|-------|
|**Windows Installer (&#42;.exe, &#42;.msi)**|Apps van dit type moeten ondersteuning bieden voor installatie op de achtergrond, zonder gebruikersinvoer. Uw appdocumentatie moet alle relevante opdrachtregelopties bevatten om de app op de achtergrond te installeren (bijvoorbeeld **/q**). U vindt een lijst met algemene opdrachtregelopties in [Opdrachtregelschakelopties voor het hulpprogramma Microsoft Windows Installer](https://support.microsoft.com/en-us/kb/227091).<br><br>Aanvullende bestanden en mappen die voor het installatieprogramma van de app vereist zijn, moeten beschikbaar zijn op de locatie die u voor de installatiebestanden van de app opgeeft.<br><br>In de meeste gevallen hoeven voor bestanden van Windows Installer (.msi) en Windows Installer-patch (.msp) geen opdrachtregelargumenten te worden geïnstalleerd door Intune. Raadpleeg de documentatie van uw app.<br><br>Als opdrachtregelargumenten vereist zijn, moeten deze worden ingevoerd als naamwaardeparen (zoals TRANSFORMS=custom_transform.mst).|
|**App-pakket voor Android (&#42;.apk)**|Als u Android-apps wilt implementeren, moet u een geldig .apk-pakket hebben.|
|**App-pakket voor iOS (&#42;.ipa)**|Als u iOS-apps wilt implementeren, moet u een geldig .ipa-pakket hebben.<br><br>Het .ipa-pakket moet zijn ondertekend door Apple en de vervaldatum in het inrichtingsprofiel moet geldig zijn. Intune kan iOS-toepassingen met een bedrijfscertificaat distribueren.<br><br>Niet alle apps met Apple-ontwikkelaarscertificaat worden ondersteund.<br><br>Uw bedrijf moet zijn geregistreerd voor het iOS Developer Enterprise Program.<br><br>Zorg ervoor dat de firewall van uw organisatie toegang geeft tot de inrichtings- en certificeringswebsites voor iOS.<br><br>U hoeft geen manifestbestand (.plist) te implementeren met de app.|
|**App-pakket voor Windows Phone (&#42;.xap, .appx, .appxbundle)**|Als u apps wilt implementeren, hebt u een bedrijfscertificaat voor handtekeningen bij programmacode nodig. Voor meer informatie gaat u naar [Windows Phone-beheer instellen met Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md).|
|**App-pakket voor Windows (.appx, .appxbundle)**|Als u apps wilt implementeren, hebt u een bedrijfscertificaat voor handtekeningen bij programmacode nodig. Voor meer informatie gaat u naar [Windows-apparaatbeheer instellen met Microsoft Intune](set-up-windows-device-management-with-microsoft-intune.md).|
|**Windows Installer via MDM (&#42;.msi)**|Met deze app kunt u op Windows Installer gebaseerde apps maken en implementeren op geregistreerd pc’s waarop Windows 10 wordt uitgevoerd. Deze pc's worden beheerd via Mobile Device Management (MDM).<br /><br />U kunt slechts één bestand met de extensie .msi uploaden.<br><br>De productcode en -versie van het bestand worden gebruikt voor detectie van de app.<br><br>Het standaardgedrag voor opnieuw opstarten van de app wordt gebruikt. Intune heeft hierop geen invloed.<br><br>MSI-pakketten per gebruiker worden voor één gebruiker geïnstalleerd.<br><br>MSI-pakketten per computer worden voor alle gebruikers op het apparaat geïnstalleerd.<br><br>Dual-mode MSI-pakketten voeren momenteel alleen installaties voor alle gebruikers op het apparaat uit.<br><br>App-updates worden ondersteund wanneer de MSI-productcode van elke versie dezelfde is.<br>
Alle typen software-installatieprogramma-apps worden geüpload naar uw opslagruimte in de cloud.

### **Externe koppeling**
Gebruik een externe koppeling wanneer u beschikt over een:
- URL waarmee gebruikers een app kunnen downloaden uit een app store.
- Koppeling naar een web-app die vanuit de webbrowser wordt uitgevoerd.

Apps op basis van externe koppelingen worden niet opgeslagen in de Intune-cloudopslag.
### **Beheerde iOS-app uit de App Store**
U kunt beheerde iOS-apps gebruiken om gratis iOS-apps uit de App Store te beheren en implementeren. U kunt ook beheerde iOS-apps gebruiken om [Mobile Application Management-beleid](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) aan [compatibele apps](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) te koppelen en hun status controleren in de beheerconsole.<br /><br />Beheerde iOS-apps worden niet opgeslagen in uw Intune-cloudopslag.

> [!TIP]
> Opties voor mobiele apparaten worden pas beschikbaar wanneer u de [MDM-instantie](prerequisites-for-enrollment.md) hebt ingesteld op Intune.

## Uitgever van Microsoft Intune-software
De Uitgever van Microsoft Intune-software wordt gestart wanneer u apps aan de Intune-beheerconsole toevoegt of hierin wijzigt. Vanuit de Uitgever selecteert en configureert u een type software-installatieprogramma dat een van de volgende dingen doet:

- Apps uploaden (programma's voor computers of apps voor mobiele apparaten) die moeten worden opgeslagen in Intune-cloudopslag.
- Een koppeling maken naar een onlinewinkel of webtoepassing.

Voordat u begint met het gebruik van de software-uitgever, moet u de volledige versie van [Microsoft .NET Framework 4.0](https://www.microsoft.com/download/details.aspx?id=17851) installeren. Na de installatie moet u uw computer mogelijk opnieuw opstarten voordat de software-uitgever correct wordt geopend.

## Cloudopslag
Alle apps die u maakt met het installatietype van het software-installatieprogramma (bijvoorbeeld een Line-Of-Business-app), worden verpakt en geüpload naar Microsoft Intune-cloudopslag. Een proefabonnement op Intune omvat 2 GB (gigabyte) cloudopslag, die wordt gebruikt voor het opslaan van beheerde apps en updates. Uw volledige abonnement omvat 20 GB aan opslagruimte.

In het knooppunt **Opslaggebruik** van de werkruimte **Beheer** kunt u zien hoeveel ruimte u gebruikt.

De vereisten voor cloudopslag zijn als volgt:

-   Alle app-installatiebestanden moeten zich in dezelfde map bevinden.
-   De maximale bestandsgrootte voor elk bestand dat u uploadt, is 2 GB.


## Ondersteuning voor UWP-apps
Bij Windows 10-pc's is geen sideloadsleutel vereist voor de installatie van Line-Of-Business-apps. De registersleutel **HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Appx\AllowAllTrustedApps** moet echter de waarde **1** hebben, zodat extern laden kan worden ingeschakeld.

Als deze registersleutel niet is geconfigureerd, wordt deze waarde door Intune automatisch ingesteld op **1** wanneer u voor het eerst een app op het apparaat implementeert. Als u deze waarde hebt ingesteld op **0**, kan de waarde niet automatisch door Intune worden gewijzigd en mislukt de implementatie van de Line-Of-Business-apps.

Line-Of-Business-UWP-apps moeten zijn ondertekend met een certificaat voor de ondertekening van de programmacode, dat wordt vertrouwd op elk apparaat waarop de app is geïmplementeerd. U kunt een certificaat gebruiken van een interne PKI-infrastructuur (Public Key Infrastructure) of een certificaat van een openbaar basiscertificaat van derden dat op het apparaat is geïnstalleerd.

Op Windows 10 Mobile-apparaten kunt u een certificaat voor de ondertekening van de programmacode van andere producenten dan Symantec gebruiken voor de ondertekening van universele **.appx**-apps. Voor **.xap**-apps en **.appx**-pakketten die zijn gemaakt voor Windows Phone 8.1 en die u op Windows 10 Mobile-apparaten wilt installeren, moet u een certificaat voor de ondertekening van de programmacode van Symantec gebruiken.

## Volgende stappen

U moet apps aan de Intune-console toevoegen voordat u ze kunt implementeren. U kunt apps toevoegen voor [geregistreerde apparaten](add-apps-for-mobile-devices-in-microsoft-intune.md), of voor [Windows-pc's die u met de Intune-clientsoftware beheert](add-apps-for-windows-pcs-in-microsoft-intune.md).



<!--HONumber=Sep16_HO4-->


