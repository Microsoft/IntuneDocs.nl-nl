---
title: Apps toevoegen
description: Neemt u even de tijd om u in te lezen in de concepten die worden geïntroduceerd in dit onderwerp, voordat u begint met het implementeren van apps met Intune.
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 07/13/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2b770f4f-6d36-41e4-b535-514b46e29aaa
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4c455d590c693893edc5e82c01095b9751a8e357
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="add-apps-with-microsoft-intune"></a>Apps toevoegen met Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Neemt u even de tijd om u in te lezen in de concepten die worden geïntroduceerd in dit onderwerp, voordat u begint met het implementeren van apps met Microsoft Intune. Deze begrippen helpen u te begrijpen welke apps u op welk platform kunt implementeren. Ze helpen u ook om inzicht te krijgen in de vereisten waaraan moet worden voldaan voordat u de apps kunt implementeren.

## <a name="app-types-that-you-can-deploy"></a>Typen apps die u kunt implementeren

### <a name="software-installer"></a>Software-installatieprogramma

|                                  App-type                                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                    Details                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
|----------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         <strong>Windows Installer (&#42;.exe, &#42;.msi)</strong>          | Apps van dit type moeten ondersteuning bieden voor installatie op de achtergrond, zonder gebruikersinvoer. Uw appdocumentatie moet alle relevante opdrachtregelopties bevatten om de app op de achtergrond te installeren (bijvoorbeeld <strong>/q</strong>). U vindt een lijst met algemene opdrachtregelopties in [Opdrachtregelschakelopties voor het hulpprogramma Microsoft Windows Installer](https://support.microsoft.com/kb/227091).<br><br>Aanvullende bestanden en mappen die voor het installatieprogramma van de app vereist zijn, moeten beschikbaar zijn op de locatie die u voor de installatiebestanden van de app opgeeft.<br><br>In de meeste gevallen hoeven voor bestanden van Windows Installer (.msi) en Windows Installer-patch (.msp) geen opdrachtregelargumenten te worden geïnstalleerd door Intune. Raadpleeg de documentatie van uw app.<br><br>Als opdrachtregelargumenten vereist zijn, moeten deze worden ingevoerd als naamwaardeparen (zoals TRANSFORMS=custom_transform.mst).<br><br>Dit type app is alleen beschikbaar voor pc’s waarop de Intune-softwareclient wordt uitgevoerd. |
|            <strong>App-pakket voor Android (&#42;.apk)</strong>            |                                                                                                                                                                                                                                                                                                                                                                                                                                          Als u Android-apps wilt implementeren, moet u een geldig .apk-pakket hebben.                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|              <strong>App-pakket voor iOS (&#42;.ipa)</strong>              |                                                                                                                                                                            Als u iOS-apps wilt implementeren, moet u een geldig .ipa-pakket hebben.<br><br>Het .ipa-pakket moet zijn ondertekend door Apple en de vervaldatum in het inrichtingsprofiel moet geldig zijn. Intune kan iOS-toepassingen met een bedrijfscertificaat distribueren.<br><br>Niet alle apps met Apple-ontwikkelaarscertificaat worden ondersteund.<br><br>Uw bedrijf moet zijn geregistreerd voor het iOS Developer Enterprise Program.<br><br>Zorg ervoor dat de firewall van uw organisatie toegang geeft tot de inrichtings- en certificeringswebsites voor iOS.<br><br>U hoeft geen manifestbestand (.plist) te implementeren met de app.                                                                                                                                                                             |
| <strong>App-pakket voor Windows Phone (&#42;.xap, .appx, .appxbundle)</strong> |                                                                                                                                                                                                                                                                                                                                                                  Als u apps wilt implementeren, hebt u een bedrijfscertificaat voor handtekeningen bij programmacode nodig. Voor meer informatie gaat u naar [Windows Phone-beheer instellen met Microsoft Intune](set-up-windows-device-management-with-microsoft-intune.md).                                                                                                                                                                                                                                                                                                                                                                  |
|         <strong>App-pakket voor Windows (.appx, .appxbundle)</strong>          |                                                                                                                                                                                                                                                                                                                                                                 Als u apps wilt implementeren, hebt u een bedrijfscertificaat voor handtekeningen bij programmacode nodig. Voor meer informatie gaat u naar [Windows-apparaatbeheer instellen met Microsoft Intune](set-up-windows-device-management-with-microsoft-intune.md).                                                                                                                                                                                                                                                                                                                                                                  |
|         <strong>Windows Installer via MDM (&#42;.msi)</strong>         |                                                                                             Met deze app kunt u op Windows Installer gebaseerde apps maken en implementeren op geregistreerd pc’s waarop Windows 10 wordt uitgevoerd. Deze pc's worden beheerd via Mobile Device Management (MDM).<br /><br />U kunt slechts één bestand met de extensie .msi uploaden.<br><br>De productcode en -versie van het bestand worden gebruikt voor detectie van de app.<br><br>Het standaardgedrag voor opnieuw opstarten van de app wordt gebruikt. Intune heeft op dit gedrag geen invloed.<br><br>MSI-pakketten per gebruiker worden voor één gebruiker geïnstalleerd.<br><br>MSI-pakketten per computer worden voor alle gebruikers op het apparaat geïnstalleerd.<br><br>Dual-mode MSI-pakketten voeren momenteel alleen installaties voor alle gebruikers op het apparaat uit.<br><br>App-updates worden ondersteund wanneer de MSI-productcode van elke versie dezelfde is.<br>                                                                                             |

Alle typen software-installatieprogramma-apps worden geüpload naar uw opslagruimte in de cloud.

### <a name="external-link"></a>**Externe koppeling**
Gebruik een externe koppeling wanneer u beschikt over een:
- URL waarmee gebruikers een app kunnen downloaden uit een app store.
- Koppeling naar een web-app die vanuit de webbrowser wordt uitgevoerd.

Apps op basis van externe koppelingen worden niet opgeslagen in de Intune-cloudopslag.
### <a name="managed-ios-app-from-the-app-store"></a>**Beheerde iOS-app uit de App Store**
U kunt beheerde iOS-apps gebruiken om gratis iOS-apps uit de App Store te beheren en implementeren. U kunt ook beheerde iOS-apps gebruiken om [Mobile Application Management-beleid](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) aan [compatibele apps](https://www.microsoft.com/server-cloud/products/microsoft-intune/partners.aspx) te koppelen en hun status controleren in de beheerconsole.<br /><br />Beheerde iOS-apps worden niet opgeslagen in uw Intune-cloudopslag.

> [!TIP]
> Opties voor mobiele apparaten worden pas beschikbaar wanneer u de [MDM-instantie](prerequisites-for-enrollment.md) hebt ingesteld op Intune.

## <a name="intune-software-publisher"></a>Uitgever van Microsoft Intune-software
De Uitgever van Microsoft Intune-software wordt gestart wanneer u apps aan de Intune-beheerconsole toevoegt of hierin wijzigt. Vanuit de Uitgever selecteert en configureert u een type software-installatieprogramma dat een van de volgende dingen doet:

- Apps uploaden (programma's voor computers of apps voor mobiele apparaten) die moeten worden opgeslagen in Intune-cloudopslag.
- Een koppeling maken naar een onlinewinkel of webtoepassing.

Voordat u begint met het gebruik van de software-uitgever, moet u de volledige versie van [Microsoft .NET Framework 4.0](https://www.microsoft.com/download/details.aspx?id=17851) installeren. Na de installatie moet u uw computer mogelijk opnieuw opstarten voordat de software-uitgever correct wordt geopend.

## <a name="cloud-storage-space"></a>Cloudopslag
Alle apps die u maakt met behulp van het installatietype van het software-installatieprogramma, moeten naar Microsoft Intune-cloudopslag worden geüpload. Een proefabonnement op Intune omvat 2 GB (gigabyte) cloudopslag, die wordt gebruikt voor het opslaan van beheerde apps en updates. Uw volledige abonnement omvat 20 GB aan opslagruimte.

In het knooppunt **Opslaggebruik** van de werkruimte **Beheer** kunt u zien hoeveel ruimte u gebruikt. U kunt extra opslagruimte kopen voor Intune met uw oorspronkelijke aankoop-methode.  Als u hebt betaald via een factuur of met een creditcard, gaat u naar de [Beheerportal abonnementen](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions).  Neem anders contact op met uw partner of verkoopassistent.

De vereisten voor cloudopslag zijn als volgt:

-   Alle app-installatiebestanden moeten zich in dezelfde map bevinden.
-   De maximale bestandsgrootte voor elk bestand dat u uploadt, is 2 GB.


## <a name="support-for-universal-windows-platform-uwp-apps"></a>Ondersteuning voor UWP-apps
Bij Windows 10-pc's is geen sideloadsleutel vereist voor de installatie van Line-Of-Business-apps. De registersleutel **HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Appx\AllowAllTrustedApps** moet echter de waarde **1** hebben, zodat extern laden kan worden ingeschakeld.

Als deze registersleutel niet is geconfigureerd, wordt deze waarde door Intune automatisch ingesteld op **1** wanneer u voor het eerst een app op het apparaat implementeert. Als u deze waarde hebt ingesteld op **0**, kan de waarde niet automatisch door Intune worden gewijzigd en mislukt de implementatie van de Line-Of-Business-apps.

Line-Of-Business-UWP-apps moeten zijn ondertekend met een certificaat voor de ondertekening van de programmacode, dat wordt vertrouwd op elk apparaat waarop de app is geïmplementeerd. U kunt een certificaat gebruiken van een interne PKI-infrastructuur (Public Key Infrastructure) of een certificaat van een openbaar basiscertificaat van derden dat op het apparaat is geïnstalleerd.

Op Windows 10 Mobile-apparaten kunt u een certificaat voor de ondertekening van de programmacode van andere producenten dan Symantec gebruiken voor de ondertekening van universele **.appx**-apps. Voor **.xap**-apps en **.appx**-pakketten die zijn gemaakt voor Windows Phone 8.1 en die u op Windows 10 Mobile-apparaten wilt installeren, moet u een certificaat voor de ondertekening van de programmacode van Symantec gebruiken.

### <a name="dependencies-for-uwp-apps"></a>Afhankelijkheden voor UWP-apps

Wanneer u een pakket met Windows 10 Universal-appxbundle aan Intune toevoegt, moet u er ook voor zorgen dat eventuele afhankelijkheden voor de app worden geüpload.
Om afhankelijkheden te uploaden, moet u ervoor zorgen dat de map **Afhankelijkheden** die is gemaakt tijdens het bouwen van de app, zich in dezelfde map bevindt als het appxbundle-bestand zelf.
Zodoende worden alle bestanden in de map **Afhankelijkheden** ook geüpload wanneer u de app uploadt naar Intune. Dit proces kan worden geïllustreerd aan de hand van de volgende schermafbeelding:


![appxbundle-afhankelijkheden voor Windows 10 UWP selecteren](./media/w10-dependencies.png)


## <a name="next-steps"></a>Volgende stappen

U voegt apps toe aan de Intune-console voordat u ze kunt implementeren. U kunt apps toevoegen voor [geregistreerde apparaten](add-apps-for-mobile-devices-in-microsoft-intune.md), of voor [Windows-pc's die u met de Intune-clientsoftware beheert](add-apps-for-windows-pcs-in-microsoft-intune.md).
