---
title: Een macOS-nalevingsbeleid voor apparaten maken in Microsoft Intune - Azure | Microsoft Docs
description: Een Microsoft Intune-apparaatnalevingsbeleid voor macOS-apparaten maken of configureren om beveiliging van systeemintegriteit te gebruiken, de minimale en maximale besturingssysteemversie in te stellen, uw wachtwoordvereisten te kiezen en gegevensopslag te versleutelen.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/14/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 21eca671d40f1ee2f2f9176a272cab5754140a26
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57566604"
---
# <a name="add-a-device-compliance-policy-for-macos-devices-with-intune"></a>Een apparaatnalevingsbeleid toevoegen voor macOS-apparaten in Intune

Een Intune-apparaatnalevingsbeleid voor macOS bepaalt de regels en instellingen waaraan een macOS-apparaat moet voldoen om te voldoen aan het beleid. Wanneer u apparaatnalevingsbeleid gebruikt met voorwaardelijke toegang, kunt u toegang tot bedrijfsbronnen toestaan of blokkeren. U kunt ook apparaatrapporten krijgen en maatregelen nemen voor niet-naleving. Nalevingsbeleid voor apparaten kan voor elk platform worden gemaakt in de Intune Azure Portal. Zie [Aan de slag met apparaatnalevingsbeleid](device-compliance-get-started.md) voor meer informatie over nalevingsbeleid en eventuele vereisten.

In de volgende tabel wordt beschreven hoe niet-compatibele instellingen worden beheerd wanneer een nalevingsbeleid wordt gebruikt in combinatie met beleid voor voorwaardelijke toegang:

---------------------------

| Beleidsinstelling | macOS 10.11 of hoger |
| --- | --- |
| **Configuratie van pincode of wachtwoord** | Hersteld |   
| **Apparaatversleuteling** | Hersteld (door een pincode in te stellen) |
| **E-mailprofiel** | In quarantaine |
|**Minimale versie van het besturingssysteem** | In quarantaine |
| **Maximale versie van het besturingssysteem** | In quarantaine |

---------------------------

**Hersteld** = het besturingssysteem van het apparaat dwingt naleving af. De gebruiker wordt bijvoorbeeld gedwongen een pincode in te stellen.

**In quarantaine** = het besturingssysteem van het apparaat dwingt geen naleving af. (Bij Android-apparaten bijvoorbeeld wordt de gebruiker niet gedwongen het apparaat te versleutelen.) Als het apparaat niet compatibel is, worden de volgende acties uitgevoerd:

- Het apparaat wordt geblokkeerd als een beleid voor voorwaardelijke toegang van toepassing is voor de gebruiker.
- De bedrijfsportal stelt de gebruiker op de hoogte van eventuele nalevingsproblemen.

## <a name="create-a-device-compliance-policy"></a>Een nalevingsbeleid voor apparaten maken

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
4. Selecteer voor **Platform** de optie **macOS**. 
5. Kies **Instellingen configureren** om instellingen op te geven voor **Apparaatstatus**, **Apparaateigenschappen** en **Systeembeveiliging** zoals wordt beschreven in dit artikel. Selecteer **OK** en **Maken** als u klaar bent.

## <a name="device-health"></a>Apparaatstatus

- **Beveiliging van systeemintegriteit vereisen**: uw macOS-apparaten **verplichten** om [Beveiliging van systeemintegriteit](https://support.apple.com/HT204899) in te schakelen.

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
- **Het minimumaantal niet-alfanumerieke tekens in een wachtwoord**: voer het aantal symbooltekens (zoals &, #, %, !, enzovoort) in dat het wachtwoord moet bevatten.

    Als u een hogere waarde instelt, moet de gebruiker een wachtwoord maken dat complexer is.

- **Maximum aantal minuten van inactiviteit voordat wachtwoord is vereist**: geef aan na hoeveel niet-actieve tijd de gebruiker het wachtwoord opnieuw moet invoeren.
- **Wachtwoord verloopt (in dagen)**: selecteer het aantal dagen waarna het wachtwoord verloopt en gebruikers een nieuw wachtwoord moeten maken.
- **Aantal vorige wachtwoorden om hergebruik te voorkomen**: geef op hoeveel eerder gebruikte wachtwoorden niet opnieuw mogen worden gebruikt.

    > [!IMPORTANT]
    > Als de wachtwoordvereiste op een macOS-apparaat wordt gewijzigd, wordt deze vereiste pas van kracht als de gebruiker de eerstvolgende keer het wachtwoord wil wijzigen. Als u bijvoorbeeld de lengtebeperking voor het wachtwoord instelt op acht cijfers en op het macOS-apparaat nog een beperking voor zes cijfers geldt, gaat de nieuwe beperking pas in de eerstvolgende keer dat de gebruiker het wachtwoord wil bijwerken.

### <a name="encryption"></a>Versleuteling

- **Versleuteling van gegevensopslag op een apparaat**: kies **Vereisen** om gegevensopslag op uw apparaten te versleutelen.

### <a name="device-security"></a>Apparaatbeveiliging
Apparaten worden door de firewall tegen onbevoegde netwerktoegang beschermd. U kunt Firewall gebruiken om verbindingen te beheren op basis van de toepassing. 

- **Firewall**: u kunt deze functie **inschakelen** om apparaten beter te beveiligen tegen onbevoegde toegang. Door deze functie in te schakelen, kunt u binnenkomende internetverbindingen verwerken en de verborgen modus gebruiken. **Niet geconfigureerd** (standaard) zorgt ervoor dat de firewall uitgeschakeld blijft en dat netwerkverkeer is toegestaan (niet geblokkeerd).
- **Binnenkomende verbindingen**: **blokkeer** alle binnenkomende netwerkverbindingen, behalve de verbindingen die vereist zijn voor elementaire internetservices, zoals DHCP, Bonjour en IPSec. Via deze instellingen worden ook alle services voor delen geblokkeerd, met inbegrip van het delen van het scherm, externe toegang, het delen van iTunes-muziek en meer. **Niet geconfigureerd** (standaard) staat binnenkomende verbindingen en services voor delen toe. 
- **Verborgen modus**: u kunt de verborgen modus **inschakelen** om te voorkomen dat het apparaat reageert op peilaanvragen van kwaadwillige gebruikers. Wanneer de modus is ingeschakeld, reageert het apparaat nog wel op binnenkomende verzoeken voor toegestane apps. Bij **Niet geconfigureerd** (standaard) blijft de verborgen modus uitgeschakeld.

### <a name="gatekeeper"></a>Gatekeeper

**Alle apps toestaan die zijn gedownload vanaf deze locaties**: hiermee staat u toe dat ondersteunde toepassingen vanaf verschillende locaties op uw apparaten worden geïnstalleerd. Uw locatieopties:

- **Niet geconfigureerd** standaard. De optie Gatekeeper heeft geen invloed op naleving of niet-naleving. 
- **Mac App Store**: alleen apps voor de Mac App Store installeren. Apps van derden en van niet-geïdentificeerde ontwikkelaars kunnen niet worden geïnstalleerd. Als een gebruiker Gatekeeper selecteert om apps buiten de Mac App Store om te installeren, wordt het apparaat vervolgens beschouwd als niet compatibel.
- **Mac App Store en geïdentificeerde ontwikkelaars**: apps voor de Mac App Store en geïdentificeerde ontwikkelaars installeren. macOS controleert de identiteit van ontwikkelaars en voert daarnaast enkele andere controles uit om de integriteit van de app te verifiëren. Als een gebruiker Gatekeeper selecteert om apps buiten deze opties om te installeren, wordt het apparaat vervolgens beschouwd als niet compatibel.
- **Overal**: apps vanaf elke locatie en van elke ontwikkelaar kunnen worden geïnstalleerd. Dit is de minst veilige optie.

Zie [Gatekeeper op macOS](https://support.apple.com/HT202491) in de Apple-documentatie voor meer informatie.

## <a name="assign-user-groups"></a>Gebruikersgroepen toewijzen

1. Kies een beleid dat u hebt geconfigureerd. Bestaande beleidsregels bevinden zich in **Apparaatcompatibiliteit** > **Beleid**.
2. Kies het beleid en kies **Toewijzingen**. U kunt Azure Active Directory-beveiligingsgroepen (AD) opnemen of uitsluiten.
3. Kies **Geselecteerde groepen** om uw Azure AD-beveiligingsgroepen te zien. Selecteer de gebruikersgroepen waarop u dit beleid wilt toepassen en kies **Opslaan** om het beleid te implementeren op gebruikers.

> [!TIP]
> Standaard wordt door apparaten elke acht uur op naleving gecontroleerd. Maar gebruikers kunnen dit proces afdwingen via de Bedrijfsportal-app in Intune.

U hebt het beleid toegepast op gebruikers. De apparaten die worden gebruikt door de gebruikers op wie het beleid is toegepast, worden gecontroleerd om te zien of ze compatibel zijn.

## <a name="next-steps"></a>Volgende stappen
[E-mail automatiseren en acties voor niet-conforme apparaten toevoegen](actions-for-noncompliance.md)  
[Nalevingsbeleid voor Intune-apparaten controleren](compliance-policy-monitor.md)
