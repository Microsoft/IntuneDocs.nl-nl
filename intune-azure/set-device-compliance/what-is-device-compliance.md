---
title: Apparaatnaleving
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: gebruik dit onderwerp voor meer informatie over apparaatnaleving in Microsoft Intune'
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a916fa0d-890d-4efb-941c-7c3c05f8fe7c
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: f316b332c3f1b80b9d6af488943298fcfea13741
ms.openlocfilehash: 8cc5e12308871a3b023bed49e9647b888971f849
ms.lasthandoff: 03/30/2017


---

# <a name="what-is-device-compliance-in-intune-azure-preview"></a>Wat is apparaatnaleving in Intune Azure Preview?

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Met nalevingsbeleid in Intune definieert u de regels en instellingen waaraan een apparaat moet voldoen om ook te voldoen aan het beleid voor voorwaardelijke toegang voor Intune en EMS. U kunt ook een nalevingsbeleid voor apparaten gebruiken om nalevingsproblemen met apparaten te bewaken en op te lossen. 

Deze regels zijn onder meer de volgende:

- Een wachtwoord gebruiken voor toegang tot het apparaat
- Versleuteling
- Of het apparaat jailbroken of geroot is
- Minimaal vereiste versie van het besturingssysteem
- Maximale versie van het besturingssysteem dat is toegestaan
- Vereisen dat het apparaat zich op of onder het Mobile Threat Defense-niveau bevindt

<!---##  Concepts
Following are some terms and concepts that are useful to understanding how to use compliance policies.

### Device compliance requirements
Compliance requirements are essentially rules like requiring a device PIN or encryption that you can specify as required or not required for a compliance policy.

### Actions for noncompliance

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

##  <a name="how-should-i-use-a-device-compliance-policy"></a>Hoe gebruikt u een nalevingsbeleid?

### <a name="using-ems-conditional-access"></a>Voorwaardelijke toegang voor EMS gebruiken
U kunt een nalevingsbeleid gebruiken met voorwaardelijke toegang voor EMS om alleen toegang te verlenen aan een of meer apparaten die voldoen aan de regels van het nalevingsbeleid voor de toegang tot e-mail en andere bedrijfsbronnen.

### <a name="not-using-ems-conditional-access"></a>Geen voorwaardelijke toegang voor EMS gebruiken
U kunt een nalevingsbeleid voor apparaten ook onafhankelijk van voorwaardelijke toegang voor EMS gebruiken.
Bij onafhankelijk gebruik van nalevingsbeleid worden de betreffende apparaten geëvalueerd en samen met hun nalevingsstatus gerapporteerd. U kunt bijvoorbeeld rapporteren over het aantal apparaten dat niet is versleuteld of over welke apparaten jailbroken of geroot zijn. Bij onafhankelijk gebruik van nalevingsbeleid zijn er echter geen toegangsbeperkingen tot bedrijfsbronnen aanwezig.

U implementeert nalevingsbeleid voor gebruikers. Wanneer er nalevingsbeleid wordt geïmplementeerd voor een gebruiker, worden de apparaten van de gebruiker gecontroleerd op naleving. Zie Instellingen en functies op uw apparaten beheren voor meer informatie over hoe lang het duurt voordat mobiele apparaten een beleid krijgen nadat het beleid is geïmplementeerd.

##  <a name="intune-classic-admin-console-vs-intune-azure-preview-portal"></a>Klassieke Intune-beheerconsole vs. Intune Azure Preview Portal

Als u de klassieke Intune-beheerconsole gebruikt, moet u rekening houden met de volgende verschillen bij de overgang naar een nieuwe werkstroom voor het nalevingsbeleid voor apparaten in Azure Portal:

-   In Azure Portal wordt het nalevingsbeleid voor elk platform afzonderlijk gemaakt. In de Intune-beheerconsole werd één nalevingsbeleid voor alle ondersteunde platformen gemaakt.

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="migration-from-intune-classic-console-to-intune-azure-preview-portal"></a>Migratie van de klassieke Intune-console naar Intune Azure Preview Portal

Nalevingsbeleid voor apparaten dat is gemaakt in de [klassieke Intune-console](https://manage.microsoft.com) wordt niet weergegeven in de nieuwe [Intune Azure Portal](https://portal.azure.com). Dit nalevingsbeleid wordt echter nog steeds toegepast op gebruikers en beheerd via de klassieke Intune-console.

Als u gebruik wilt maken van de nieuwe functies voor het nalevingsbeleid voor apparaten in Intune Azure Portal, moet u een nieuw nalevingsbeleid voor apparaten maken in Intune Azure Portal zelf. Als u een nieuw nalevingsbeleid voor apparaten in Intune Azure Portal toewijst aan een gebruiker, aan wie ook een nalevingsbeleid voor apparaten uit de klassieke Intune-console is toegewezen, heeft het nalevingsbeleid voor apparaten uit Intune Azure Portal voorrang boven het beleid dat in de klassieke Intune-console is gemaakt.

##  <a name="next-steps"></a>Volgende stappen

[Aan de slag met nalevingsbeleidsregels](get-started-with-device-compliance.md)


<!---### See also

Conditional access--->

