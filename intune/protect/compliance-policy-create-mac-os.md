---
title: Nalevingsinstellingen voor macOS-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk een overzicht van alle instellingen die u kunt gebruiken bij het instellen van naleving voor uw macOS-apparaten in Microsoft Intune. Beveiliging van systeemintegriteit van Apple vereisen, wachtwoordbeperkingen instellen, een firewall vereisen, Gatekeeper toestaan en meer.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/22/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: samyada
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 518f0b825b71a9773ed66dd480b329e998f919c4
ms.sourcegitcommit: 25acfc88b366d2da71c37d354a0238e4f1168325
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/23/2019
ms.locfileid: "72813502"
---
# <a name="macos-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>macOS-instellingen om te markeren of apparaten wel of niet conform zijn met behulp van Intune

Dit artikel bevat een overzicht en beschrijving van de verschillende nalevingsinstellingen die u kunt configureren op macOS-apparaten in Intune. Gebruik deze instellingen als onderdeel van uw MDM-oplossing (Mobile Device Management) om een minimale en maximale versie van het besturingssysteem in te stellen, in te stellen dat wachtwoorden verlopen en meer.

Deze functie is van toepassing op:

- macOS

Gebruik deze nalevingsinstellingen als Intune-beheerder om de resources van uw organisatie beter te beschermen. Zie [Aan de slag met apparaatnalevingsbeleid](device-compliance-get-started.md) voor meer informatie over nalevingsbeleid en wat dit doet.

## <a name="before-you-begin"></a>Voordat u begint

[Een nalevingsbeleid maken](create-compliance-policy.md#create-the-policy). Selecteer voor **Platform** de optie **macOS**.

## <a name="device-health"></a>Apparaatstatus

- **Beveiliging van systeem integriteit vereisen**:  
  - **Niet geconfigureerd** (*standaard*) - Deze instelling wordt niet beoordeeld op naleving of niet-naleving.
  - **Vereisen** : vereisen dat macOS-apparaten [systeem integriteits beveiliging](https://support.apple.com/HT204899) hebben (Hiermee opent u de website van Apple) ingeschakeld.  

## <a name="device-properties"></a>Apparaateigenschappen

- **Minimale versie van het besturingssysteem die is vereist**:  
  Als een apparaat niet voldoet aan de minimumvereisten met betrekking tot de versie van het besturingssysteem, wordt dit apparaat gerapporteerd als niet-conform. Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. De apparaatgebruiker kan kiezen om het apparaat bij te werken. Daarna zijn de resources van de organisatie toegankelijk.

- **Maximale versie van het besturingssysteem dat is toegestaan**:  
  Wanneer een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie in de regel, wordt de toegang tot organisatieresources geblokkeerd. De apparaatgebruiker wordt gevraagd contact op te nemen met de IT-beheerder. Op dit apparaat kan geen toegang worden verkregen tot organisatieresources zolang een regel niet zodanig is gewijzigd dat de versie van het besturingssysteem is toegestaan.

- **Minimumversie van OS-build**:  
  Als Apple beveiligingsupdates publiceert, wordt het buildnummer meestal bijgewerkt, niet de versie van het besturingssysteem. Gebruik deze functie om het buildnummer in te voeren dat minimaal is toegestaan op het apparaat.

- **Maximumversie van OS-build**:  
  Als Apple beveiligingsupdates publiceert, wordt het buildnummer meestal bijgewerkt, niet de versie van het besturingssysteem. Gebruik deze functie om het buildnummer in te voeren dat maximaal is toegestaan op het apparaat.

## <a name="system-security-settings"></a>Systeembeveiligingsinstellingen

### <a name="password"></a>Wachtwoord

- **Wachtwoord vereist voor het ontgrendelen van mobiele apparaten**:  
  - **Niet geconfigureerd** (*standaard*)
  - **Vereisen** - Gebruikers moeten een wachtwoord invoeren voordat ze toegang kunnen krijgen tot hun apparaat.

- **Eenvoudige wachtwoorden**:  
  - **Niet geconfigureerd** (*standaard*): gebruikers kunnen wacht woorden eenvoudig maken, zoals **1234** of **1111**.
  - **Blokkeren** - Gebruikers kunnen geen eenvoudige wachtwoorden maken, zoals **1234** of **1111**.

- **Minimale wachtwoordlengte**:  
  Voer het aantal cijfers of tekens in waaruit het wachtwoord minimaal moet bestaan.

- **Wachtwoordtype**: kies of een wachtwoord alleen **numerieke** tekens mag bevatten of uit een combinatie van cijfers en andere tekens moet bestaan (**alfanumeriek**).

- **Het aantal niet-alfanumerieke tekens in het wachtwoord**:  
  Voer het minimumaantal speciale tekens (zoals `&`, `#`, `%`, `!` enz.) in dat het wachtwoord moet bevatten.

  Als u een hogere waarde instelt, moet de gebruiker een wachtwoord maken dat complexer is.

- **Maximum aantal minuten inactief voordat wachtwoord is vereist**:  
  Voer in na hoeveel niet-actieve tijd gebruikers hun wachtwoord opnieuw moeten invoeren.

- **Wachtwoordverlooptijd (dagen)** :  
  selecteer het aantal dagen waarna het wachtwoord verloopt en gebruikers een nieuw wachtwoord moeten maken.

- **Aantal eerdere wachtwoorden dat niet opnieuw mag worden gebruikt**:  
  Voer het aantal eerder gebruikte wachtwoorden in dat niet opnieuw mag worden gebruikt.
> [!IMPORTANT]
> Als de wachtwoordvereiste op een macOS-apparaat wordt gewijzigd, wordt deze vereiste pas van kracht als de gebruiker de eerstvolgende keer het wachtwoord wil wijzigen. Als u bijvoorbeeld de lengtebeperking voor het wachtwoord instelt op acht cijfers en op het macOS-apparaat nog een beperking voor zes cijfers geldt, gaat de nieuwe beperking pas in de eerstvolgende keer dat de gebruiker het wachtwoord wil bijwerken.

### <a name="encryption"></a>Versleuteling

- **Versleuteling van gegevensopslag op een apparaat**:  
  - **Niet geconfigureerd** (*standaard*)
  - **Vereisen** - Gebruik *Vereisen* om de gegevensopslag op uw apparaten te versleutelen.

### <a name="device-security"></a>Apparaatbeveiliging

Apparaten worden door de firewall tegen onbevoegde netwerktoegang beschermd. U kunt Firewall gebruiken om verbindingen te beheren op basis van de toepassing. 

- **Firewall**:  
  - **Niet geconfigureerd** (*standaard*) - Deze instelling zorgt ervoor dat de firewall uitgeschakeld blijft en dat netwerkverkeer is toegestaan (niet geblokkeerd).
  - **Inschakelen** - Gebruik *Inschakelen* om apparaten te beveiligen tegen onbevoegde toegang. Door deze functie in te schakelen, kunt u binnenkomende internetverbindingen verwerken en de verborgen modus gebruiken. 

- **Binnenkomende verbindingen**:  
  - **Niet geconfigureerd** (*standaard*) - Staat binnenkomende verbindingen en services voor delen toe.
  - **Blokkeren**: - Blokkeer alle binnenkomende verbindingen, behalve de verbindingen die vereist zijn voor basisinternetservices, zoals DHCP, Bonjour en IPSec. Via deze instelling worden ook alle services voor delen geblokkeerd, met inbegrip van het delen van het scherm, externe toegang, het delen van iTunes-muziek en meer.  

- **Verborgen modus**:  
  - **Niet geconfigureerd** (*standaard*): deze instelling laat de verborgen modus uitgeschakeld.
  - **Inschakelen** - U kunt de verborgen modus inschakelen om te voorkomen dat het apparaat reageert op testaanvragen van kwaadwillige gebruikers. Wanneer de modus is ingeschakeld, reageert het apparaat nog wel op binnenkomende verzoeken voor toegestane apps.  

### <a name="gatekeeper"></a>Gatekeeper

Zie [Gatekeeper in macOS](https://support.apple.com/HT202491) (hiermee wordt een Apple-website geopend) voor meer informatie.

**Alle apps toestaan die zijn gedownload vanaf deze locaties**: hiermee staat u toe dat ondersteunde toepassingen vanaf verschillende locaties op uw apparaten worden geïnstalleerd. Uw locatieopties:

- **Niet geconfigureerd** (*standaard*): de gate keeper-optie heeft geen invloed op naleving of niet-naleving.  
- **Mac App Store** - Alleen apps voor de Mac App Store installeren. Apps van derden en van niet-geïdentificeerde ontwikkelaars kunnen niet worden geïnstalleerd. Als een gebruiker Gatekeeper selecteert om apps buiten de Mac App Store om te installeren, wordt het apparaat vervolgens beschouwd als niet compatibel.
- **Mac App Store en geïdentificeerde ontwikkelaars** - Apps voor de Mac App Store en geïdentificeerde ontwikkelaars installeren. macOS controleert de identiteit van ontwikkelaars en voert daarnaast enkele andere controles uit om de integriteit van de app te verifiëren. Als een gebruiker Gatekeeper selecteert om apps buiten deze opties om te installeren, wordt het apparaat vervolgens beschouwd als niet compatibel.
- **Overal** -Apps kunnen vanaf elke locatie en van elke ontwikkelaar worden geïnstalleerd. Dit is de minst veilige optie.
 

## <a name="next-steps"></a>Volgende stappen

- [Voeg acties voor niet-conforme apparaten toe](actions-for-noncompliance.md) en [gebruik bereiktags om beleidsregels te filteren](../fundamentals/scope-tags.md).
- [Controleer uw nalevingsbeleid](compliance-policy-monitor.md).
- Zie [Instellingen voor nalevingsbeleid voor iOS](compliance-policy-create-ios.md)-apparaten.