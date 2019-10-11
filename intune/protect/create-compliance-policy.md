---
title: Nalevingsbeleid voor apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Ga aan de slag met het gebruik van apparaatnalevingsbeleid, overzicht van status- en ernstniveaus, gebruik van Respijtperiode-status, werken met voorwaardelijke toegang, verwerking van apparaten zonder toegewezen beleid en de verschillen in naleving tussen de Azure-portal en de klassieke portal in Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c8b3a99744f830da3c88473e79bce78c97875d73
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71722628"
---
# <a name="create-a-compliance-policy-in-microsoft-intune"></a>Een nalevingsbeleid maken in Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Nalevingsbeleid voor apparaten is belangrijk voor het beveiligen van de resources van uw organisatie als u gebruikmaakt van Intune. In Intune kunt u regels en instellingen maken waar apparaten zich aan moeten houden om te voldoen, zoals een minimale versie van het besturingssysteem. Als het apparaat niet voldoet, kunt u toegang tot gegevens en resources blokkeren middels [voorwaardelijke toegang](conditional-access.md).

U kunt ook maatregelen nemen bij niet-naleving; zo kunt u bijvoorbeeld een e-mailmelding naar de gebruiker verzenden. Zie [Aan de slag met apparaatnaleving](device-compliance-get-started.md) voor een overzicht van de werking van nalevingsbeleid.

Dit artikel:

- Geeft de vereisten en stappen weer voor het maken van nalevingsbeleid.
- Laat zien hoe u het beleid kunt toewijzen aan uw gebruikers- en apparaatgroepen.
- Beschrijft aanvullende functies, waaronder bereiktags om uw beleid te filteren, en stappen die u kunt uitvoeren voor apparaten die niet compatibel zijn.
- Geeft de cyclusduur voor vernieuwen van check-ins weer wanneer apparaten beleidsupdates ontvangen.

## <a name="before-you-begin"></a>Voordat u begint

Neem het volgende in acht voor het gebruik van het nalevingsbeleid voor apparaten:

- Gebruik de volgende abonnementen:

  - Intune
  - U hebt de Azure AD (Active Directory) Premium-editie is nodig om voorwaardelijke toegang te gebruiken. In [Prijzen van Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/) wordt vermeld wat u krijgt bij de verschillende edities. voor Intune-naleving is geen Azure AD vereist.

- Gebruik een ondersteund platform:

  - Android
  - Android Enterprise
  - iOS
  - macOS (preview)
  - Windows 10
  - Windows 8.1
  - Windows Phone 8.1

- Apparaten registreren in Intune (vereist om de nalevingsstatus te zien)

- Registreer apparaten voor één gebruiker of registreer ze zonder een primaire gebruiker. Apparaten die zijn geregistreerd voor meerdere gebruikers worden niet ondersteund.

## <a name="create-the-policy"></a>Beleid maken

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **Apparaatnaleving**. U hebt de volgende opties:

    - **Overzicht**: Geeft aan hoeveel apparaten compatibel zijn, niet geëvalueerd zijn, enzovoort, en geeft hier een samenvatting van. Ook worden het beleid en de afzonderlijke instellingen in uw beleid vermeld. U vindt nuttige informatie hierover in [Nalevingsbeleid voor Intune-apparaten controleren](compliance-policy-monitor.md).
    - **Beheren**: Maak apparaatbeleid, stuur [meldingen](quickstart-send-notification.md) naar niet-compatibele apparaten, en schakel [netwerkbegrenzing](use-network-locations.md) in.
    - **Bewaken**: Controleer de nalevingsstatus van uw apparaten, zowel op instellings- als op beleidsniveau. [Nalevingsbeleid voor Intune-apparaten controleren](compliance-policy-monitor.md) is een goede resource. Bekijk ook de logboeken en de status van de bedreigingsagent van uw apparaten.
    - **Configureren**: Gebruik het [ingebouwde nalevingsbeleid](device-compliance-get-started.md#ways-to-deploy-device-compliance-policies), schakel [Microsoft Defender ATP (Advanced Threat Protection)](advanced-threat-protection.md) in, voeg een [Mobile Threat Defense-connector](mobile-threat-defense.md) toe en gebruik [Jamf](conditional-access-integrate-jamf.md).

3. Selecteer **Beleid** > **Beleid maken**. Voer de volgende eigenschappen in:

    - **Naam**: Voer een beschrijvende naam in voor het beleid. Geef uw beleid een naam zodat u het later eenvoudig kunt identificeren. **iOS-apparaten die zijn opengebroken, niet markeren als compatibel** is bijvoorbeeld een goede beleidsnaam.
    - **Beschrijving**: Voer een beschrijving in voor het beleid. Deze instelling is optioneel, maar wordt aanbevolen.
    - **Platform**: Kies het platform van uw apparaten. Uw opties zijn:  

       - **Android**
       - **Android Enterprise**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 en hoger**
       - **Windows 10 en hoger**

    - **Instellingen**: In de volgende artikelen worden de instellingen voor elk platform vermeld beschreven:

        - [Android](compliance-policy-create-android.md)
        - [Android Enterprise](compliance-policy-create-android-for-work.md)
        - [iOS](compliance-policy-create-ios.md)
        - [macOS](compliance-policy-create-mac-os.md)
        - [Windows Phone 8.1, Windows 8.1 en hoger](compliance-policy-create-windows-8-1.md)
        - [Windows 10 en hoger](compliance-policy-create-windows.md)

4. Wanneer u klaar bent, selecteert u **OK** > **Maken** om uw wijzigingen op te slaan. Het beleid wordt gemaakt en in de lijst weergegeven. Vervolgens wijst u het beleid toe aan uw groepen.

## <a name="assign-user-groups"></a>Gebruikersgroepen toewijzen

Als een beleid eenmaal is gemaakt, is de volgende stap dit beleid toewijzen aan uw groepen:

1. Kies een beleid dat u hebt gemaakt. Bestaande beleidsregels bevinden zich in **Apparaatcompatibiliteit** > **Beleid**.
2. Selecteer het beleid > **Toewijzingen**. U kunt Azure Active Directory-beveiligingsgroepen (AD) opnemen of uitsluiten.
3. Kies **Geselecteerde groepen** om uw Azure AD-beveiligingsgroepen te zien. Selecteer de gebruikersgroepen waarop u dit beleid wilt toepassen > Kies **Opslaan** om het beleid te implementeren voor gebruikers.

U hebt het beleid toegepast op gebruikers. De apparaten die worden gebruikt door de gebruikers op wie het beleid wordt toegepast, worden gecontroleerd om te zien of ze voldoen aan de vereisten.

### <a name="evaluate-how-many-users-are-targeted"></a>Evalueren op hoeveel gebruikers een beleid is gericht

Als u het beleid toewijst, kunt u ook **Evalueren** hoeveel gebruikers moeten worden beïnvloed. Met deze functie worden gebruikers berekend, geen apparaten.

1. Selecteer in Intune **Apparaatcompatibiliteit** > **Beleid**.
2. Selecteer een beleid > **Toewijzingen** > **Evalueren**. In een bericht wordt weergegeven op hoeveel gebruikers dit beleid is gericht.

Als de knop **Evalueren** is uitgeschakeld, controleert u of het beleid is toegewezen aan een of meer groepen.

## <a name="actions-for-noncompliance"></a>Acties voor niet-naleving

Voor apparaten die niet voldoen aan uw nalevingsbeleid, kunt u een reeks acties toevoegen die automatisch moeten worden toegepast. U kunt het schema veranderen wanneer het apparaat wordt gemarkeerd als niet-compatibel, zoals na één dag. U kunt ook een tweede actie toevoegen, waarbij een e-mailbericht wordt verzonden naar de gebruiker wanneer het apparaat niet voldoet.

[Acties voor niet-compatibele apparaten toevoegen](actions-for-noncompliance.md) biedt meer informatie, onder andere over het maken van een e-mailmelding voor uw gebruikers.

U gebruikt bijvoorbeeld de functie Locaties en u voegt een locatie toe aan een nalevingsbeleid. De standaardactie bij niet-naleving wordt uitgevoerd als u ten minste één locatie hebt geselecteerd. Als het apparaat niet is verbonden met de geselecteerde locaties, wordt het apparaat direct gezien als 'niet compatibel'. U kunt gebruikers bijvoorbeeld een respijtperiode van één dag bieden.

## <a name="scope-tags"></a>Bereiktags

Met bereiktags kunt u eenvoudig beleid toewijzen aan en filteren voor specifieke groepen, zoals Verkoop, HR, Alle NL-AMST-werknemers, enzovoort. Nadat u de instellingen hebt toegevoegd, kunt u ook een bereiktag toevoegen aan het nalevingsbeleid. [Bereiktags gebruiken om beleid te filteren](../fundamentals/scope-tags.md) is een goede resource.

## <a name="refresh-cycle-times"></a>Cyclusduur vernieuwen

In Intune worden verschillende vernieuwingscycli gebruikt om te controleren op updates voor nalevingsbeleid. Als het apparaat onlangs is ingeschreven, worden de check-ins vaker uitgevoerd. [Vernieuwingscycli voor beleidsregels en profielen](../configuration/device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned) bevat de geschatte vernieuwingstijden.

Gebruikers kunnen ook op elk gewenst moment de bedrijfsportal-app openen en het apparaat synchroniseren om onmiddellijk op beleidsupdates te controleren.

### <a name="assign-an-ingraceperiod-status"></a>Een Respijtperiode-status toewijzen

De Respijtperiode-status voor een nalevingsbeleid is een waarde. Deze waarde wordt bepaald door de combinatie van de respijtperiode van een apparaat en de daadwerkelijke status van een apparaat voor dit nalevingsbeleid.

Als een apparaat de status Niet-compatibel heeft voor een toegewezen nalevingsbeleid, en:

- er geen respijtperiode is toegewezen aan het apparaat, is de toegewezen waarde voor het nalevingsbeleid Niet-compatibel
- de respijtperiode voor het apparaat is verlopen, is de toegewezen waarde voor het nalevingsbeleid Niet-compatibel
- de respijtperiode voor het apparaat in de toekomst ligt, is de toegewezen waarde voor het nalevingsbeleid Respijtperiode

De volgende tabel geeft een overzicht van deze punten:

|Werkelijke nalevingsstatus|Waarde van toegewezen respijtperiode|Effectieve nalevingsstatus|
|---------|---------|---------|
|Niet-compatibel |Er is geen respijtperiode toegewezen |Niet-compatibel |
|Niet-compatibel |De datum van gisteren|Niet-compatibel|
|Niet-compatibel |De datum van morgen|Respijtperiode|

Zie [Nalevingsbeleid voor Intune-apparaten controleren](compliance-policy-monitor.md) voor meer informatie over het controleren van nalevingsbeleid voor apparaten.

### <a name="assign-a-resulting-compliance-policy-status"></a>Een resulterende nalevingsbeleidsstatus toewijzen

Wanneer een apparaat meerdere nalevingsbeleidsregels heeft en het apparaat verschillende nalevingsstatussen heeft voor twee of meer toegewezen nalevingsbeleidsregels, wordt één resulterende nalevingsstatus toegewezen. Deze toewijzing is gebaseerd op een conceptueel ernstniveau dat is toegewezen aan elke nalevingsstatus. Elke nalevingsstatus heeft een van de volgende ernstniveaus:

|Status  |Ernst  |
|---------|---------|
|Onbekend     |1|
|Niet van toepassing     |2|
|Compliant|3|
|Respijtperiode|4|
|Niet-compatibel|5|
|Fout|6|

Wanneer een apparaat meerdere nalevingsbeleidsregels heeft, wordt het hoogste ernstniveau van alle beleidsregels toegewezen aan dat apparaat.

Aan een apparaat kunnen bijvoorbeeld drie nalevingsbeleidsregels zijn toegewezen: één met de status Unknown (ernst = 1), één met de status Compliant (ernst = 3) en één met de status InGracePeriod (ernst =4). De status InGracePeriod heeft het hoogste ernstniveau. Dus hebben alle drie de beleidsregels de nalevingsstatus InGracePeriod.

## <a name="next-steps"></a>Volgende stappen

[Controleer uw beleidsregels](compliance-policy-monitor.md).