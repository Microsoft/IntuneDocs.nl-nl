---
title: Nalevingsinstellingen voor macOS-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk een overzicht van alle instellingen die u kunt gebruiken bij het instellen van naleving voor uw macOS-apparaten in Microsoft Intune. Beveiliging van systeemintegriteit van Apple vereisen, wachtwoordbeperkingen instellen, een firewall vereisen, Gatekeeper toestaan en meer.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/04/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f0e3164c84c9a4088068fcf920903c6bb76cd30a
ms.sourcegitcommit: 7315fe72b7e55c5dcffc6d87f185f3c2cded9028
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 07/02/2019
ms.locfileid: "71305068"
---
# <a name="macos-settings-to-mark-devices-as-compliant-or-not-compliant-using-intune"></a>macOS-instellingen om te markeren of apparaten wel of niet conform zijn met behulp van Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Dit artikel bevat een overzicht en beschrijving van de verschillende nalevingsinstellingen die u kunt configureren op macOS-apparaten in Intune. Gebruik deze instellingen als onderdeel van uw MDM-oplossing (Mobile Device Management) om een minimale en maximale versie van het besturingssysteem in te stellen, in te stellen dat wachtwoorden verlopen en meer.

Deze functie is van toepassing op:

- macOS

Gebruik deze nalevingsinstellingen als Intune-beheerder om de resources van uw organisatie beter te beschermen. Zie [Aan de slag met apparaatnalevingsbeleid](device-compliance-get-started.md) voor meer informatie over nalevingsbeleid en wat dit doet.

## <a name="before-you-begin"></a>Voordat u begint

[Een nalevingsbeleid maken](create-compliance-policy.md#create-the-policy). Selecteer voor **Platform** de optie **macOS**.

## <a name="device-health"></a>Apparaatstatus

- **Beveiliging van systeemintegriteit vereisen**: U kunt **Vereisen** dat [Beveiliging van systeemintegriteit](https://support.apple.com/HT204899) (hiermee wordt een Apple-website geopend) op uw macOS-apparaten is ingeschakeld. Als **Niet geconfigureerd** (standaard) is ingesteld, wordt deze instelling niet beoordeeld op naleving of niet-naleving.

## <a name="device-properties"></a>Apparaateigenschappen

- **Minimale versie van het besturingssysteem**: als een apparaat niet voldoet aan de minimumvereisten met betrekking tot de versie van het besturingssysteem, wordt het gerapporteerd als niet-conform. Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. Gebruikers kunnen dan kiezen om een upgrade van hun apparaat uit te voeren, waarna ze toegang tot bedrijfsresources krijgen.
- **Maximale versie van het besturingssysteem**: wanneer een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie die is opgegeven in de regel, wordt de toegang tot bedrijfsresources geblokkeerd. De gebruiker wordt gevraagd contact op te nemen met de IT-beheerder. Tot er een wijziging is doorgevoerd in de regel om de versie van het besturingssysteem toe te staan, kan dit apparaat geen toegang tot bedrijfsresources krijgen.
- **Minimale buildversie van het besturingssysteem**: als Apple beveiligingsupdates publiceert, wordt het buildnummer meestal bijgewerkt, niet de versie van het besturingssysteem. Gebruik deze functie om het buildnummer in te voeren dat minimaal is toegestaan op het apparaat.
- **Maximale buildversie van het besturingssysteem**: als Apple beveiligingsupdates publiceert, wordt het buildnummer meestal bijgewerkt, niet de versie van het besturingssysteem. Gebruik deze functie om het buildnummer in te voeren dat maximaal is toegestaan op het apparaat.

## <a name="system-security-settings"></a>Systeembeveiligingsinstellingen

### <a name="password"></a>Wachtwoord

- **Een wachtwoord vereisen voor het ontgrendelen van mobiele apparaten**: **verplicht** gebruikers een wachtwoord in te voeren om toegang te krijgen tot hun apparaat.
- **Eenvoudige wachtwoorden**: stel deze optie in op **Blokkeren** zodat de gebruiker geen eenvoudig wachtwoord kan maken, zoals **1234** of **1111**. Stel deze optie in op **Niet geconfigureerd** om gebruikers toe te staan wachtwoorden als **1234** of **1111** te maken.
- **Minimale wachtwoordlengte**: voer het minimale aantal cijfers of tekens aan waaruit het wachtwoord moet bestaan.
- **Wachtwoordtype**: kies of een wachtwoord alleen **numerieke** tekens mag bevatten of uit een combinatie van cijfers en andere tekens moet bestaan (**alfanumeriek**).
- **Het minimumaantal niet-alfanumerieke tekens in een wachtwoord**: Voer het minimale aantal speciale tekens (zoals `&`, `#`, `%`, `!` enzovoort) in dat het wachtwoord moet bevatten.

    Als u een hogere waarde instelt, moet de gebruiker een wachtwoord maken dat complexer is.

- **Maximum aantal minuten van inactiviteit voordat wachtwoord is vereist**: geef aan na hoeveel niet-actieve tijd de gebruiker het wachtwoord opnieuw moet invoeren.
- **Wachtwoord verloopt (in dagen)** : selecteer het aantal dagen waarna het wachtwoord verloopt en gebruikers een nieuw wachtwoord moeten maken.
- **Aantal eerdere wachtwoorden dat niet opnieuw mag worden gebruikt**: voer het aantal eerder gebruikte wachtwoorden in dat niet opnieuw mag worden gebruikt.

    > [!IMPORTANT]
    > Als de wachtwoordvereiste op een macOS-apparaat wordt gewijzigd, wordt deze vereiste pas van kracht als de gebruiker de eerstvolgende keer het wachtwoord wil wijzigen. Als u bijvoorbeeld de lengtebeperking voor het wachtwoord instelt op acht cijfers en op het macOS-apparaat nog een beperking voor zes cijfers geldt, gaat de nieuwe beperking pas in de eerstvolgende keer dat de gebruiker het wachtwoord wil bijwerken.

### <a name="encryption"></a>Versleuteling

- **Versleuteling van gegevensopslag op een apparaat**: kies **Vereisen** om gegevensopslag op uw apparaten te versleutelen.

### <a name="device-security"></a>Apparaatbeveiliging

Apparaten worden door de firewall tegen onbevoegde netwerktoegang beschermd. U kunt Firewall gebruiken om verbindingen te beheren op basis van de toepassing. 

- **Firewall**: Selecteer **Inschakelen** om apparaten beter te beveiligen tegen onbevoegde toegang. Door deze functie in te schakelen, kunt u binnenkomende internetverbindingen verwerken en de verborgen modus gebruiken. **Niet geconfigureerd** (standaard) zorgt ervoor dat de firewall uitgeschakeld blijft en dat netwerkverkeer is toegestaan (niet geblokkeerd).
- **Binnenkomende verbindingen**: U kunt alle binnenkomende verbindingen **Blokkeren**, behalve de verbindingen die vereist zijn voor basisinternetservices, zoals DHCP, Bonjour en IPSec. Via deze instelling worden ook alle services voor delen geblokkeerd, met inbegrip van het delen van het scherm, externe toegang, het delen van iTunes-muziek en meer. **Niet geconfigureerd** (standaard) staat binnenkomende verbindingen en services voor delen toe.
- **Verborgen modus**: U kunt de verborgen modus **Inschakelen** om te voorkomen dat het apparaat reageert op testaanvragen van kwaadwillige gebruikers. Wanneer de modus is ingeschakeld, reageert het apparaat nog wel op binnenkomende verzoeken voor toegestane apps. Bij **Niet geconfigureerd** (standaard) blijft de verborgen modus uitgeschakeld.

### <a name="gatekeeper"></a>Gatekeeper

Zie [Gatekeeper in macOS](https://support.apple.com/HT202491) (hiermee wordt een Apple-website geopend) voor meer informatie.

**Alle apps toestaan die zijn gedownload vanaf deze locaties**: hiermee staat u toe dat ondersteunde toepassingen vanaf verschillende locaties op uw apparaten worden geïnstalleerd. Uw locatieopties:

- **Niet geconfigureerd** standaard. De optie Gatekeeper heeft geen invloed op naleving of niet-naleving. 
- **Mac App Store**: alleen apps voor de Mac App Store installeren. Apps van derden en van niet-geïdentificeerde ontwikkelaars kunnen niet worden geïnstalleerd. Als een gebruiker Gatekeeper selecteert om apps buiten de Mac App Store om te installeren, wordt het apparaat vervolgens beschouwd als niet compatibel.
- **Mac App Store en geïdentificeerde ontwikkelaars**: apps voor de Mac App Store en geïdentificeerde ontwikkelaars installeren. macOS controleert de identiteit van ontwikkelaars en voert daarnaast enkele andere controles uit om de integriteit van de app te verifiëren. Als een gebruiker Gatekeeper selecteert om apps buiten deze opties om te installeren, wordt het apparaat vervolgens beschouwd als niet compatibel.
- **Overal**: apps vanaf elke locatie en van elke ontwikkelaar kunnen worden geïnstalleerd. Dit is de minst veilige optie.

Selecteer **OK** > **Maken** om uw wijzigingen op te slaan.

## <a name="next-steps"></a>Volgende stappen

- [Voeg acties voor niet-conforme apparaten toe](actions-for-noncompliance.md) en [gebruik bereiktags om beleidsregels te filteren](scope-tags.md).
- [Controleer uw nalevingsbeleid](compliance-policy-monitor.md).
- Zie [Instellingen voor nalevingsbeleid voor iOS](compliance-policy-create-ios.md)-apparaten.