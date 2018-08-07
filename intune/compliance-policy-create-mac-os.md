---
title: Een macOS-nalevingsbeleid voor apparaten maken in Microsoft Intune - Azure | Microsoft Docs
description: Een Microsoft Intune-apparaatnalevingsbeleid voor macOS-apparaten maken of configureren om beveiliging van systeemintegriteit te gebruiken, de minimale en maximale besturingssysteemversie in te stellen, uw wachtwoordvereisten te kiezen en gegevensopslag te versleutelen.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6bbb09944db602b4b5a70c89e8089b1692c45223
ms.sourcegitcommit: e8e8164586508f94704a09c2e27950fe6ff184c3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/27/2018
ms.locfileid: "39321438"
---
# <a name="add-a-device-compliance-policy-for-macos-devices-with-intune"></a>Een apparaatnalevingsbeleid toevoegen voor macOS-apparaten in Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

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
5. Selecteer voor **Platform** de optie **macOS**. Kies **Instellingen configureren** om instellingen op te geven voor de **Apparaatstatus**, de **Apparaateigenschappen** en de **Systeembeveiliging**. Selecteer **OK** en **Maken** als u klaar bent.

## <a name="device-health"></a>Apparaatstatus

- **Beveiliging van systeemintegriteit vereisen**: uw macOS-apparaten **verplichten** om [Beveiliging van systeemintegriteit](https://support.apple.com/HT204899) in te schakelen.

## <a name="device-properties"></a>Apparaateigenschappen

- **Minimale versie van het besturingssysteem**: als een apparaat niet voldoet aan de minimumvereisten met betrekking tot de versie van het besturingssysteem, wordt het gerapporteerd als niet-conform. Er wordt een koppeling met informatie over het uitvoeren van een upgrade weergegeven. Gebruikers kunnen dan kiezen om een upgrade van hun apparaat uit te voeren, waarna ze toegang tot bedrijfsresources krijgen.
- **Maximale versie van het besturingssysteem**: wanneer een apparaat een versie van het besturingssysteem gebruikt die hoger is dan de versie die is opgegeven in de regel, wordt de toegang tot bedrijfsresources geblokkeerd. De gebruiker wordt gevraagd contact op te nemen met de IT-beheerder. Tot er een wijziging is doorgevoerd in de regel om de versie van het besturingssysteem toe te staan, kan dit apparaat geen toegang tot bedrijfsresources krijgen.

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
