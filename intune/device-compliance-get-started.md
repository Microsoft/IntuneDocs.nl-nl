---
title: Nalevingsbeleid voor apparaten van Microsoft Intune
titleSuffix: 
description: Meer informatie over apparaatnaleving in Microsoft Intune
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/1/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9e3a7bdf3ddf6ad77a82ac6dc7075d696fbe6497
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2018
---
# <a name="get-started-with-microsoft-intune-device-compliance-policies"></a>Aan de slag met het apparaatnalevingsbeleid van Microsoft Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Het Intune-apparaatnalevingsbeleid bevat de regels en instellingen waaraan een apparaat moet voldoen om te voldoen aan het beleid van Intune.

Deze regels zijn onder meer de volgende:

- Een wachtwoord gebruiken voor toegang tot het apparaat

- Versleuteling

- Of het apparaat jailbroken of geroot is

- Minimaal vereiste versie van het besturingssysteem

- Maximale versie van het besturingssysteem dat is toegestaan

- Vereisen dat het apparaat zich op of onder het Mobile Threat Defense-niveau bevindt

U kunt een apparaatnalevingsbeleid ook gebruiken om de naleving van uw apparaten te bewaken.

## <a name="device-compliance-requirements"></a>Apparaatcompatibiliteitsvereisten

Nalevingsvereisten zijn in feite regels, zoals het vereisen van een pincode voor het apparaat of versleuteling, die u kunt opgeven als vereist of niet vereist voor een nalevingsbeleid.

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

##  <a name="pre-requisites"></a>Vereisten

Als u een apparaatnalevingsbeleid wilt gebruiken in Intune, moet u de volgende abonnementen hebben:

- Intune EMS

- Azure AD Premium

###  <a name="supported-platforms"></a>Ondersteunde platformen:

-   Android

-   iOS

-   macOS (preview)

-   Windows 8.1

-   Windows Phone 8.1

-   Windows 10

> [!IMPORTANT]
> Apparaten moeten worden ingeschreven bij Intune om over het nalevingsbeleid voor apparaten te rapporteren.

## <a name="how-intune-device-compliance-policies-work-with-azure-ad"></a>Hoe het Intune-apparaatnalevingsbeleid werkt met Azure AD

Wanneer een apparaat wordt ingeschreven bij Intune, vindt het Azure AD-registratieproces plaats, dat de apparaatkenmerken bijwerkt met meer informatie in Azure AD. Een van de belangrijkste apparaatgegevens is de nalevingsstatus van het apparaat, die door de beleidsregels voor voorwaardelijke toegang wordt gebruikt om de toegang tot e-mail en andere bedrijfsmiddelen toe te staan of te blokkeren.

- Meer informatie over het [Azure AD-registratieproces](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction).

### <a name="assigning-a-resulting-device-configuration-profile-status"></a>Een resulterend configuratieprofiel aan een apparaatstatus toewijzen

Wanneer aan een apparaat meerdere configuratieprofielen zijn toegewezen en het apparaat verschillende nalevingsstatussen heeft voor twee of meerdere toegewezen configuratieprofielen, moet één resulterende nalevingsstatus worden toegewezen. Deze toewijzing is gebaseerd op een conceptueel ernstniveau dat is toegewezen aan elke nalevingsstatus. Elke nalevingsstatus heeft een van de volgende ernstniveaus:


|Status  |Ernst  |
|---------|---------|
|In behandeling     |1|
|Geslaagd     |2|
|Mislukt     |3|
|Fout     |4|

De resulterende status van twee of meer configuratieprofielen wordt vervolgens toegewezen door het hoogste ernstniveau te selecteren van alle profielen die aan een apparaat zijn toegewezen.

Stel dat aan een apparaat drie profielen zijn toegewezen, één met de status In behandeling (ernst = 1), één met de status Geslaagd (ernst = 2) en één met de status Fout (ernst =4). De status Fout heeft het hoogste ernstniveau, waardoor deze status wordt toegewezen als de resulterende nalevingsstatus voor alle drie de profielen.

### <a name="assigning-an-ingraceperiod-status-for-an-assigned-compliance-policy"></a>De status Respijtperiode toewijzen voor een toegewezen nalevingsbeleid

De status Respijtperiode voor een nalevingsbeleid is een waarde die wordt bepaald door de combinatie van de respijtperiode van een apparaat en de werkelijke status van een apparaat voor het toegewezen nalevingsbeleid. 

Als een apparaat de status Niet-compatibel heeft voor een toegewezen nalevingsbeleid, en:

- er geen respijtperiode is toegewezen aan het apparaat, is de toegewezen waarde voor het nalevingsbeleid Niet-compatibel.
- de respijtperiode voor het apparaat is verlopen, is de toegewezen waarde voor het nalevingsbeleid Niet-compatibel.
- de respijtperiode voor het apparaat in de toekomst ligt, is de toegewezen waarde voor het nalevingsbeleid Respijtperiode.

De volgende tabel geeft een overzicht van de vorige punten:


|Werkelijke nalevingsstatus|Waarde van toegewezen respijtperiode|Effectieve nalevingsstatus|
|---------|---------|---------|
|Niet-compatibel |Er is geen respijtperiode toegewezen |Niet-compatibel |
|Niet-compatibel |De datum van gisteren|Niet-compatibel|
|Niet-compatibel |De datum van morgen|Respijtperiode|

Zie [Nalevingsbeleid voor Intune-apparaten controleren](compliance-policy-monitor.md) voor meer informatie over het controleren van nalevingsbeleid voor apparaten.

### <a name="assigning-a-resulting-compliance-policy-status"></a>Een resulterende nalevingsbeleidsstatus toewijzen

Wanneer aan een apparaat meerdere nalevingsbeleidsregels zijn toegewezen en het apparaat verschillende nalevingsstatussen heeft voor twee of meerdere toegewezen nalevingsbeleidsregels, moet één resulterende nalevingsstatus worden toegewezen. Deze toewijzing is gebaseerd op een conceptueel ernstniveau dat is toegewezen aan elke nalevingsstatus. Elke nalevingsstatus heeft een van de volgende ernstniveaus: 

|Status  |Ernst  |
|---------|---------|
|Onbekend     |1|
|Niet van toepassing     |2|
|Compliant|3|
|Respijtperiode|4|
|Niet-compatibel|5|
|Fout|6|

De resulterende status van twee of meer configuratieprofielen wordt vervolgens toegewezen door het hoogste ernstniveau te selecteren van alle profielen die aan een apparaat zijn toegewezen.
 
Stel dat aan een apparaat drie nalevingsbeleidsregels zijn toegewezen, één met de status Onbekend (ernst = 1), één met de status Compatibel (ernst = 3) en één met de status Respijtperiode (ernst =4). De status Respijtperiode heeft het hoogste ernstniveau, waardoor deze status wordt toegewezen als de resulterende nalevingsstatus voor alle drie de profielen.  

##  <a name="ways-to-use-device-compliance-policies"></a>Nalevingsbeleid voor apparaten gebruiken

### <a name="with-conditional-access"></a>Met voorwaardelijke toegang
U kunt een nalevingsbeleid gebruiken met voorwaardelijke toegang om alleen toegang te verlenen aan een of meer apparaten die voldoen aan de regels van het nalevingsbeleid voor de toegang tot e-mail en andere bedrijfsbronnen.

### <a name="without-conditional-access"></a>Zonder voorwaardelijke toegang
U kunt een nalevingsbeleid voor apparaten ook onafhankelijk van voorwaardelijke toegang gebruiken. Bij onafhankelijk gebruik van nalevingsbeleid worden de betreffende apparaten geëvalueerd en samen met hun nalevingsstatus gerapporteerd. U kunt bijvoorbeeld rapporteren over het aantal apparaten dat niet is versleuteld of over welke apparaten jailbroken of geroot zijn. Bij onafhankelijk gebruik van nalevingsbeleid zijn er echter geen toegangsbeperkingen tot bedrijfsbronnen aanwezig.

U implementeert nalevingsbeleid voor gebruikers. Wanneer er nalevingsbeleid wordt geïmplementeerd voor een gebruiker, worden de apparaten van de gebruiker gecontroleerd op naleving. Raadpleeg [Problemen met apparaatprofielen oplossen in Microsoft Intune](device-profile-troubleshoot.md#how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned) voor meer informatie over hoe lang het duurt voordat mobiele apparaten een beleid krijgen nadat het beleid is geïmplementeerd.

#### <a name="actions-for-non-compliance"></a>Acties voor niet-naleving

Met de acties voor niet-naleving kunt u een op tijd geordende opeenvolgende reeks acties configureren die worden toegepast op apparaten die niet voldoen aan de criteria van het nalevingsbeleid. Zie [Acties voor niet-naleving automatiseren](actions-for-noncompliance.md) voor meer informatie.

##  <a name="using-device-compliance-policies-in-the-intune-classic-portal-vs-azure-portal"></a>Het gebruik van apparaatnalevingsbeleid in de klassieke Intune-portal ten opzichte van Azure Portal

Informatie over de belangrijkste verschillen om u te helpen met de overgang naar de nieuwe werkstroom voor apparaatnalevingsbeleid in Azure Portal.

- In Azure Portal wordt het nalevingsbeleid voor elk platform afzonderlijk gemaakt.
- In de klassieke Intune-portal werd één apparaatnalevingsbeleid voor alle ondersteunde platformen gemaakt.

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="migrate-device-compliance-policies-from-the-intune-classic-portal-to-the-azure-portal"></a>Apparaatnalevingsbeleid migreren van de klassieke Intune-portal naar Azure Portal

Nalevingsbeleid voor apparaten dat is gemaakt in de [klassieke Intune-portal](https://manage.microsoft.com) wordt niet weergegeven in de nieuwe [Intune Azure Portal](https://portal.azure.com). Dit nalevingsbeleid wordt echter nog steeds toegepast op gebruikers en beheerd via de klassieke Intune-portal.

Als u gebruik wilt maken van de nieuwe functies voor het nalevingsbeleid voor apparaten in Azure Portal, moet u een nieuw nalevingsbeleid voor apparaten maken in Azure Portal zelf. Als u een nieuw nalevingsbeleid voor apparaten in Azure Portal toewijst aan een gebruiker, aan wie ook een nalevingsbeleid voor apparaten uit de klassieke Intune-console is toegewezen, heeft het nalevingsbeleid voor apparaten uit Intune Azure Portal voorrang boven het beleid dat in de klassieke Intune-portal is gemaakt.

##  <a name="next-steps"></a>Volgende stappen

- Een nalevingsbeleid maken voor de volgende platformen:

   - [Android](compliance-policy-create-android.md)
   - [Android for Work](compliance-policy-create-android-for-work.md)
   - [iOS](compliance-policy-create-ios.md)
   - [macOS](compliance-policy-create-mac-os.md)
   - [Windows](compliance-policy-create-windows.md)

- Zie [Naslag voor beleidsentiteiten](reports-ref-policy.md) voor meer informatie over de beleidsentiteiten voor Intune-datawarehouse.
