---
# required metadata

title: Archief Wat is er nieuw | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


## September 2015
### Updates voor mobiele apparaten en appbeheer
**Alle Intune iOS-beheerfuncties bieden nu ondersteuning voor iOS 9**
Zie [dit blogbericht](http://blogs.technet.com/b/microsoftintune/archive/2015/09/09/day-zero-support-for-ios-9-with-intune.aspx) voor meer informatie over de beheermogelijkheden voor iOS 9.

**Nieuw configuratiebeleid voor mobiele apps voor iOS**
Gebruik het nieuwe configuratiebeleid voor mobiele apps om automatisch instellingen op te geven die nodig kunnen zijn voor een iOS-app wanneer deze wordt uitgevoerd. U kunt bijvoorbeeld een netwerkpoort of een gebruikersnaam opgeven. Zie [iOS-apps configureren met configuratiebeleid voor mobiele apps in Microsoft Intune](https://technet.microsoft.com/library/mt481447.aspx) voor meer informatie..

**Eenvoudiger app-beheer voor iOS 9-gebruikers**
 In deze release kunt u apps die al zijn geïmplementeerd, onder Intune-beheer brengen voor iOS 9-gebruikers. Voor eerdere versies van iOS geldt dat wanneer u een app implementeert en er op een apparaat al een niet-beheerde versie van de app is geïnstalleerd, u alsnog aan de gebruiker moet vragen om de app handmatig te verwijderen voordat de beheerde app met Intune kan worden geïnstalleerd.

 Vanaf deze versie van Intune kunt u gebruikers van iOS 9-apparaten vragen toestemming te geven aan Intune om het beheer van de app over te nemen en eventuele relevante Mobile Application Management-beleidsregels toe te passen.

 **Windows 10-beheer** Gebruik het nieuwe [algemene configuratiebeleid voor Windows 10](https://technet.microsoft.com/library/mt404697.aspx) om wachtwoord-, apparaat-, browser- en overige instellingen te configureren voor ingeschreven apparaten met Windows 10 en Windows 10 Mobile.

 **Apps maken en implementeren voor ingeschreven Windows 10-apparaten** Met het nieuwe type software-installatieprogramma, Windows Installer via MDM (&#42;.msi), kunt u Windows Installer-apps maken en implementeren op ingeschreven apparaten met Windows 10. Zie [Aan de slag met app-implementatie in Microsoft Intune](https://technet.microsoft.com/library/dn646955.aspx) voor meer informatie.

### Wijzigingen en updates voor Microsoft-bedrijfsportal-apps
In deze release zijn de volgende wijzigingen aangebracht aan de bedrijfsportal-apps:

**iOS**
* Microsoft verzamelt automatisch anonieme gegevens over de prestaties en het gebruik van de bedrijfsportal om Microsoft-producten en -services te verbeteren. Eindgebruikers kunnen  het verzamelen van gegevens uitschakelen met de instelling Gebruiksgegevens op hun apparaat. Beheerders hebben geen controle over het verzamelen van deze gegevens en ze kunnen de selectie van de gebruiker voor deze instelling niet wijzigen.
* Ondersteuning voor volledige schermresolutie op iPhone 6 en 6 Plus
* Oplossingen voor verbeterde beveiliging

### Wat is er nieuw in de Intune-documentatie -- september 2015
**Nieuwe onderwerpen**

|Naam|Details|
|----|--------|
|[Instellingen voor configuratiebeleid voor Windows in Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx)|Dit is een nieuw configuratiebeleid waarmee u instellingen en functies op apparaten met Windows 10 en Windows 10 Mobile beheert.
| [Apps configureren met configuratiebeleid voor mobiele apps in Microsoft Intune](https://technet.microsoft.com/library/mt481447.aspx)|Dit is een nieuw beleidstype waarmee u automatisch instellingen opgeeft die mogelijk vereist zijn wanneer de gebruiker een iOS-app gebruikt. |

**Bijgewerkte onderwerpen**

|Naam|Details|
|----|-------|
|[Beleid gebruiken voor het beheren van computers en mobiele apparaten met Microsoft Intune](https://technet.microsoft.com/library/dn743712.aspx)|Bijgewerkt met de laatste informatie voor een beter inzicht in beleidsregels en ondersteuning bij het maken van deze regels.|

## Augustus 2015
### Updates voor mobiele apparaten en appbeheer
* **Voorwaarden** voor Intune-registratie en bedrijfstoegang worden [nu beheerd via beleidsregels](https://technet.microsoft.com/library/mt405893.aspx). U kunt verschillende sets voorwaarden instellen om te voldoen aan de vereisten voor specifieke gebruikersgroepen. U kunt bijvoorbeeld voorwaarden in verschillende talen implementeren naar geografisch gedefinieerde gebruikersgroepen. U kunt [uw voorwaarden ook bewerken](https://technet.microsoft.com/library/mt405893.aspx#BKMK_TCVers) en opgeven of het versienummer moet worden verhoogd, zodat gebruikers de nieuwe voorwaarden moeten accepteren voordat ze de bedrijfsportal kunnen gebruiken.
* **Een aantal Intune-beleidsregels is hernoemd** zodat ze consistenter zijn binnen het gehele product en eenvoudiger te vinden zijn. Zie [Beleid gebruiken voor het beheren van computers en mobiele apparaten met Microsoft Intune](https://technet.microsoft.com/library/dn743712.aspx) voor een lijst met alle beschikbare Intune-beleidsregels.
* **PKCS #12-certificaatprofielen (.PFX)** zijn beschikbaar voor Android 4.0 of hoger en Windows 10 (desktop en mobiel) en hoger. Voor het gebruik van .PFX is geen NDES-server vereist. Zie [Toegang tot bedrijfsbronnen inschakelen met certificaatprofielen met Microsoft Intune](http://technet.microsoft.com/library/dn818904.aspx) voor meer informatie over het gebruik van .PFX-certificaatprofielen
* **Instellingen van bedrijfsgrenzen voor Windows 10 Desktop en Mobile** maken het gebruik van gedetailleerde VPN-instellingen mogelijk, zoals beschreven in [Gebruikers helpen om verbinding met hun werk te maken met behulp van VPN-profielen met Microsoft Intune](https://technet.microsoft.com/library/dn818905.aspx)
* **De app OneDrive voor Android ondersteunt nu meerdere identiteiten**. Deze en andere updates aan beleidsregels voor het beheer van mobiele apps worden beschreven in de [lijst met Microsoft-toepassingen die u kunt beheren](https://technet.microsoft.com/library/dn708489.aspx)..
* **Bypass van iOS-activeringsvergrendeling**. Als iOS-apparaten in bedrijfseigendom worden beschermd door activeringsvergrendeling, moet u de Apple-id en het wachtwoord van de gebruiker invoeren voordat u het apparaat kunt wissen of opnieuw activeren. Dit kan leiden tot problemen wanneer gebruikers het bedrijf verlaten en een apparaat in bedrijfseigendom retourneren zonder de activeringsvergrendeling uit te schakelen. U kunt [Bypass van activeringsvergrendeling voor Intune](https://technet.microsoft.com/library/mt414176.aspx) gebruiken om dit probleem op te lossen

### Voorwaardelijke toegang voor pc’s
U kunt nu voorwaardelijke beleidsregels configureren voor pc's. Hiermee krijgen Office desktopapps toegang tot Exchange Online en SharePoint Online-services.
Om voorwaardelijke beleidsregels voor pc's in te schakelen, moet de pc lid zijn van het domein of hiermee compatibel zijn.
* Zie de sectie **Aan de slag** in [Toegang tot e-mail en SharePoint beheren met Microsoft Intune](http://technet.microsoft.com/library/dn818907).aspx) voor de volledige lijst met vereisten voor het inschakelen van voorwaardelijke toegang voor pc's.
* Zie [Toegang tot e-mail beheren met Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx) voor opties die u kunt instellen om voorwaardelijke toegang tot e-mail in te schakelen.
* Zie [Toegang tot SharePoint Online beheren met Microsoft Intune](https://technet.microsoft.com/library/dn705844.aspx) voor opties die u kunt instellen om voorwaardelijke toegang tot SharePoint Online in te schakelen.

### Wijzigingen en updates voor Microsoft-bedrijfsportal-apps
In deze release zijn de volgende wijzigingen aangebracht aan de bedrijfsportal-apps:

**Android**

Als gebruikers hun apparaat nog niet hebben geregistreerd voor apparaatbeheer, zien ze na het aanmelden instructies voor het registreren van hun apparaat.

### Wat is er nieuw in Intune-documentatie -- augustus 2015
**Nieuwe onderwerpen**

|Titel|Details|
|-----|-------|
|[iOS-apparaten beschermen met bypass van activeringsvergrendeling voor Microsoft Intune](https://technet.microsoft.com/library/mt414176.aspx)|Meer informatie over hoe u Intune kunt gebruiken voor bypass van iOS-activeringsvergrendeling wanneer een gebruiker het bedrijf verlaat en een vergrendeld apparaat retourneert.|

**Bijgewerkte onderwerpen**

|Titel|Details|
|-----|-------|
|[Microsoft-apps die u met MAM-beleidsregels van Microsoft Intune kunt gebruiken](https://technet.microsoft.com/library/dn708489.aspx)|Bijgewerkt met de meest recente informatie over apps die u met Mobile Application Management-beleid kunt beheren.
|[Beleid gebruiken voor het beheren van computers en mobiele apparaten met Microsoft Intune](http://technet.microsoft.com/library/dn743712.aspx)|Bijgewerkt met de nieuwste beleidsregels die aan Intune zijn toegevoegd.|
<!---
## July 2015
July updates for Intune are limited to behind-the-scenes enhancements that allow us to continue providing you with a high-quality service experience. New features are not included in this service update.

### Intune Onboarding benefit
Microsoft offers the Intune Onboarding benefit for eligible plans. The Onboarding benefit lets you work remotely with Microsoft specialists to get your Intune environment ready for use. For more information, see [Microsoft Intune Onboarding benefit description](https://technet.microsoft.com/library/mt228266.aspx)
### Changes and updates to Microsoft Company Portal apps
The following changes have been made to the company portal apps in this release.

**Android**

Microsoft automatically collects anonymous data about the performance and use of the company portal to improve Microsoft products and services. End users can turn off data collection by using the Usage Data setting on their device, but administrators have no control over the data collection and cannot change the end user’s selection for this setting.--->


<!--HONumber=May16_HO1-->


