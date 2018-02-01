---
title: Intune apparaatnalevingsbeleid
titleSuffix: Azure portal
description: Meer informatie over apparaatnaleving in Microsoft Intune
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 07/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a916fa0d-890d-4efb-941c-7c3c05f8fe7c
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1e6d758d10a3527e0dc350115f2f8f10e2c62322
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="get-started-with-intune-device-compliance-policies"></a>Aan de slag met Intune-apparaatnalevingsbeleid

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="what-is-device-compliance-in-intune"></a>Wat is apparaatnaleving in Intune?

Het Intune-apparaatnalevingsbeleid bevat de regels en instellingen waaraan een apparaat moet voldoen om ook te voldoen aan het beleid van Intune.

Deze regels zijn onder meer de volgende:

- Een wachtwoord gebruiken voor toegang tot het apparaat

- Versleuteling

- Of het apparaat jailbroken of geroot is

- Minimaal vereiste versie van het besturingssysteem

- Maximale versie van het besturingssysteem dat is toegestaan

- Vereisen dat het apparaat zich op of onder het Mobile Threat Defense-niveau bevindt

U kunt een apparaatnalevingsbeleid ook gebruiken om de naleving van uw apparaten te bewaken.

### <a name="device-compliance-requirements"></a>Apparaatcompatibiliteitsvereisten

Nalevingsvereisten zijn in feite regels, zoals het vereisen van een pincode voor het apparaat of versleuteling, die u kunt opgeven als vereist of niet vereist voor een nalevingsbeleid.

<!---### Actions for noncompliance

You can specify what needs to happen when a device is determined as noncompliant. This can be a sequence of actions during a specific time.
When you specify these actions, Intune will automatically initiate them in the sequence you specify. See the following example of a sequence of
actions for a device that continues to be in the noncompliant status for
a week:

-   When the device is first determined to be non-compliant, an email with noncompliant notification is sent to the user.

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

- Meer informatie over het [Azure AD-registratieproces](https://docs.microsoft.com/azure/active-directory/active-directory-device-registration-overview).

##  <a name="ways-to-use-device-compliance-policies"></a>Nalevingsbeleid voor apparaten gebruiken

### <a name="with-conditional-access"></a>Met voorwaardelijke toegang
U kunt een nalevingsbeleid gebruiken met voorwaardelijke toegang om alleen toegang te verlenen aan een of meer apparaten die voldoen aan de regels van het nalevingsbeleid voor de toegang tot e-mail en andere bedrijfsbronnen.

### <a name="without-conditional-access"></a>Zonder voorwaardelijke toegang
U kunt een nalevingsbeleid voor apparaten ook onafhankelijk van voorwaardelijke toegang gebruiken. Bij onafhankelijk gebruik van nalevingsbeleid worden de betreffende apparaten geëvalueerd en samen met hun nalevingsstatus gerapporteerd. U kunt bijvoorbeeld rapporteren over het aantal apparaten dat niet is versleuteld of over welke apparaten jailbroken of geroot zijn. Bij onafhankelijk gebruik van nalevingsbeleid zijn er echter geen toegangsbeperkingen tot bedrijfsbronnen aanwezig.

U implementeert nalevingsbeleid voor gebruikers. Wanneer er nalevingsbeleid wordt geïmplementeerd voor een gebruiker, worden de apparaten van de gebruiker gecontroleerd op naleving. Zie Instellingen en functies op uw apparaten beheren voor meer informatie over hoe lang het duurt voordat mobiele apparaten een beleid krijgen nadat het beleid is geïmplementeerd.

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

Een nalevingsbeleid maken voor de volgende platformen:

- [Android](compliance-policy-create-android.md)
- [Android for Work](compliance-policy-create-android-for-work.md)
- [iOS](compliance-policy-create-ios.md)
- [macOS](compliance-policy-create-mac-os.md)
- [Windows](compliance-policy-create-windows.md)
