---
title: Nalevingsbeleid voor apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Vereisten voor het gebruik van apparaatnalevingsbeleid, overzicht van status- en ernstniveaus, gebruik van Respijtperiode-status, werken met voorwaardelijke toegang, verwerking van apparaten zonder toegewezen beleid en de verschillen in naleving tussen de Azure Portal en de klassieke portal in Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3326ecccd0d20602d6a9445b62c39f582354f238
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="get-started-with-device-compliance-policies-in-intune"></a>Aan de slag met apparaatnalevingsbeleid in Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Nalevingsvereisten zijn in wezen regels zoals het vereisen van een apparaatpincode of het vereisen van versleuteling. Het apparaatnalevingsbeleid bevat de regels en instellingen waaraan een apparaat moet voldoen om te voldoen aan het beleid. Deze regels omvatten:

- Een wachtwoord gebruiken voor toegang tot het apparaat

- Versleuteling

- Of het apparaat jailbroken of geroot is

- Minimaal vereiste versie van het besturingssysteem

- Maximale versie van het besturingssysteem dat is toegestaan

- Vereisen dat het apparaat zich op of onder het Mobile Threat Defense-niveau bevindt

U kunt een apparaatnalevingsbeleid ook gebruiken om de naleving van uw apparaten te bewaken.

<!---### Actions for noncompliance

You can specify what needs to happen when a device is determined as noncompliant. This can be a sequence of actions during a specific time.
When you specify these actions, Intune will automatically initiate them in the sequence you specify. See the following example of a sequence of
actions for a device that continues to be in the noncompliant status for
a week:

-   When the device is first determined to be noncompliant, an email with noncompliant notification is sent to the user.

-   3 days after initial noncompliance state, a follow up reminder is sent to the user.

-   5 days after initial noncompliance state, a final reminder with a notification that access to company resources will be blocked on the device in 2 days if the compliance issues are not remediated is sent to the user.

-   7 days after initial noncompliance state, access to company resources is blocked. This requires that you have conditional access policy that specifies that access from noncompliant devices should    be blocked for services such as Exchange and SharePoint.

### Grace Period

This is the time between when a device is first determined as
noncompliant to when access to company resources on that device is blocked. This time allows for time that the user has to resolve
compliance issues on the device. You can also use this time to create your action sequences to send notifications to the user before their access is blocked.

Remember that you need to implement conditional access policies in addition to compliance policies in order for access to company resources to be blocked.--->

## <a name="prerequisites"></a>Vereisten
Het volgende is vereist om apparaatnalevingsbeleid te gebruiken:

- Gebruik de volgende abonnementen:

  - Intune
  - Azure Active Directory (AD) Premium

- Gebruik een ondersteund platform:

  - Android
  - iOS
  - macOS (preview)
  - Windows 8.1
  - Windows Phone 8.1
  - Windows 10

- Apparaten moeten worden geregistreerd bij Intune om over het nalevingsbeleid voor apparaten te rapporteren

## <a name="how-intune-device-compliance-policies-work-with-azure-ad"></a>Hoe het Intune-apparaatnalevingsbeleid werkt met Azure AD

Wanneer een apparaat wordt ingeschreven bij Intune, begint het Azure AD-registratieproces en worden de apparaatkenmerken in Azure AD bijgewerkt. Een van de belangrijkste apparaatgegevens is de nalevingsstatus van het apparaat. Deze nalevingsstatus wordt door de beleidsregels voor voorwaardelijke toegang gebruikt om de toegang tot e-mail en andere bedrijfsresources toe te staan of te blokkeren.

In het [Azure AD-registratieproces](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) vindt u meer informatie.

### <a name="assign-a-resulting-device-configuration-profile-status"></a>Een resulterend configuratieprofiel aan een apparaatstatus toewijzen

Wanneer een apparaat meerdere configuratieprofielen heeft en het apparaat verschillende nalevingsstatussen heeft voor twee of meer toegewezen configuratieprofielen, moet één resulterende nalevingsstatus worden toegewezen. Deze toewijzing is gebaseerd op een conceptueel ernstniveau dat is toegewezen aan elke nalevingsstatus. Elke nalevingsstatus heeft een van de volgende ernstniveaus:

|Status  |Ernst  |
|---------|---------|
|In behandeling     |1|
|Geslaagd     |2|
|Mislukt     |3|
|Fout     |4|

Wanneer een apparaat meerdere configuratieprofielen heeft, wordt het hoogste ernstniveau van alle profielen toegewezen aan dat apparaat.

Stel dat aan een apparaat drie profielen zijn toegewezen, één met de status In behandeling (ernst = 1), één met de status Geslaagd (ernst = 2) en één met de status Fout (ernst =4). De status Fout heeft het hoogste ernstniveau, waardoor alle drie de profielen de nalevingsstatus Fout hebben.

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

Stel dat aan een apparaat drie nalevingsbeleidsregels zijn toegewezen, één met de status Onbekend (ernst = 1), één met de status Compatibel (ernst = 3) en één met de status Respijtperiode (ernst =4). De status Respijtperiode heeft het hoogste ernstniveau, waardoor alle drie de beleidsregels de nalevingsstatus Respijtperiode hebben.

## <a name="ways-to-use-device-compliance-policies"></a>Nalevingsbeleid voor apparaten gebruiken

#### <a name="with-conditional-access"></a>Met voorwaardelijke toegang
Voor apparaten die aan beleidsregels voldoen, kunt u die apparaten toegang verlenen tot e-mail en andere bedrijfsresources. Als de apparaten niet aan beleidsregels voldoen, krijgen ze geen toegang tot bedrijfsresources. Dit wordt voorwaardelijke toegang genoemd.

#### <a name="without-conditional-access"></a>Zonder voorwaardelijke toegang
U kunt nalevingsbeleid voor apparaten ook zonder voorwaardelijke toegang gebruiken. Bij onafhankelijk gebruik van nalevingsbeleid worden de betreffende apparaten geëvalueerd en samen met hun nalevingsstatus gerapporteerd. U kunt bijvoorbeeld rapporteren over het aantal apparaten dat niet is versleuteld of over welke apparaten jailbroken of geroot zijn. Wanneer u nalevingsbeleid zonder voorwaardelijke toegang gebruikt, zijn er geen toegangsbeperkingen tot bedrijfsresources.

## <a name="ways-to-deploy-device-compliance-policies"></a>Nalevingsbeleid voor apparaten implementeren
U kunt nalevingsbeleid implementeren voor gebruikers in gebruikersgroepen of aan apparaten in apparaatgroepen. Wanneer er nalevingsbeleid wordt geïmplementeerd voor een gebruiker, worden de apparaten van de gebruiker gecontroleerd op naleving.

Voor apparaten in apparaatgroepen omvat **Instellingen voor nalevingsbeleid** (Azure Portal > Apparaatnaleving)

- **Apparaten waaraan geen nalevingsbeleid is toegewezen markeren als**: deze eigenschap heeft twee waarden:

  - **Compatibel**: beveiligingsfunctie uit
  - **Niet compatibel** (standaard): beveiligingsfunctie aan

  Als er geen nalevingsbeleid aan een apparaat is toegewezen, wordt dit apparaat als incompatibel beschouwd. Standaard worden apparaten gemarkeerd als **Niet compatibel**. Als u voorwaardelijke toegang gebruikt, is het raadzaam de standaardinstelling **Niet compatibel** te behouden. Als een eindgebruiker incompatibel is omdat er geen beleid is toegewezen, wordt in de bedrijfsportal `No compliance policies have been assigned` vermeld.

- **Verbeterde jailbreak-detectie**: als deze instelling is ingeschakeld, zorgt deze ervoor dat iOS-apparaten vaker bij Intune inchecken. Door het inschakelen van deze eigenschap worden de locatieservices van het apparaat gebruikt. Ook heeft dit invloed op het batterijverbruik. De locatiegegevens van de gebruiker worden niet opgeslagen door Intune.

  Wanneer u deze instelling inschakelt, moeten apparaten:
  - Locatieservices op het niveau van het besturingssysteem inschakelen;
  - De bedrijfsportal toestaan om locatieservices te gebruiken; en
  - Eens per 72 uur de jailbreak-status evalueren en aan Intune rapporteren. Anders wordt het apparaat gemarkeerd als Niet compatibel.

- **Geldigheidsperiode van nalevingsstatus (dagen)**: voer de periode in dat apparaten de status voor alle ontvangen nalevingsbeleidsregels rapporteren. Apparaten die niet binnen deze tijdsduur de status retourneren, worden als Niet compatibel beschouwd. De standaardwaarde is 30 dagen.

Alle apparaten hebben een **Standaardnalevingsbeleid voor apparaten** (Azure Portal > Apparaatnaleving > Beleidsnaleving). Gebruik dit standaardbeleid voor het bewaken van deze instellingen.

Raadpleeg [Problemen met apparaatprofielen oplossen](device-profile-troubleshoot.md#how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned) voor meer informatie over hoe lang het duurt voordat op mobiele apparaten een beleid wordt toegepast nadat het beleid is geïmplementeerd.

Nalevingsrapporten zijn een uitstekende manier om de status van apparaten te controleren. Zie [Nalevingsbeleid bewaken](compliance-policy-monitor.md) voor hulp.

### <a name="actions-for-noncompliance"></a>Acties voor niet-naleving
U kunt een op tijd geordende opeenvolgende reeks acties configureren die worden toegepast op apparaten die niet voldoen aan de criteria van het nalevingsbeleid. Deze acties voor niet-naleving kunnen worden geautomatiseerd, zoals beschreven in [Acties voor niet-naleving automatiseren](actions-for-noncompliance.md).

## <a name="azure-classic-portal-vs-azure-portal"></a>Vergelijking tussen klassieke Azure-portal en Azure Portal

Het belangrijkste verschil wanneer u nalevingsbeleid voor apparaten gebruikt in de Azure Portal:

- In Azure Portal wordt het nalevingsbeleid voor elk platform afzonderlijk gemaakt
- In de klassieke Azure-portal werd één apparaatnalevingsbeleid voor alle ondersteunde platformen gemaakt

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

## <a name="device-compliance-policies-in-the-classic-portal-and-azure-portal"></a>Apparaatnalevingsbeleid in de klassieke Azure-portal ten opzichte van Azure Portal

Nalevingsbeleid voor apparaten dat is gemaakt in de [klassieke portal](https://manage.microsoft.com) wordt niet weergegeven in de [Azure Portal](https://portal.azure.com). Dit nalevingsbeleid wordt echter nog steeds toegepast op gebruikers en beheerd via de klassieke portal.

Als u de functies voor het nalevingsbeleid voor apparaten in Azure Portal wilt gebruiken, moet u een nieuw nalevingsbeleid voor apparaten maken in Azure Portal. Als u een nalevingsbeleid voor apparaten in Azure Portal toewijst aan een gebruiker aan wie ook een nalevingsbeleid voor apparaten uit de klassieke portal is toegewezen, heeft het nalevingsbeleid voor apparaten uit Azure Portal voorrang boven het beleid dat in de klassieke portal is gemaakt.

## <a name="next-steps"></a>Volgende stappen

- Een nalevingsbeleid maken voor de volgende platformen:

  - [Android](compliance-policy-create-android.md)
  - [Android for Work](compliance-policy-create-android-for-work.md)
  - [iOS](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows](compliance-policy-create-windows.md)

- Zie [Naslag voor beleidsentiteiten](reports-ref-policy.md) voor meer informatie over de beleidsentiteiten voor Intune-datawarehouse.
