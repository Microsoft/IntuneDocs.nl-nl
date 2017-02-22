---
title: Apparaatnaleving | Intune Azure Preview | Microsoft Docs
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
translationtype: Human Translation
ms.sourcegitcommit: 7693d49e2f0fa6e4aa40b6bb71433a7eaab8dd15
ms.openlocfilehash: a4254503e4e6b86079f862966dee2727934f1ee6


---

# <a name="what-is-device-compliance-in-intune-azure-preview"></a>Wat is apparaatnaleving in Intune Azure Preview?


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

U moet er voor de beveiliging van bedrijfsgegevens voor zorgen dat de apparaten die worden gebruikt voor toegang tot bedrijfs-apps en- gegevens, voldoen aan bepaalde regels. Deze regels kunnen bijvoorbeeld zijn dat voor toegang tot apparaten een pincode moet worden opgegeven en dat gegevens op apparaten moeten zijn versleuteld. Een verzameling van dergelijke regels wordt een **nalevingsbeleid** genoemd.

##  <a name="how-should-i-use-a-device-compliance-policy"></a>Hoe gebruikt u een nalevingsbeleid?
U kunt een nalevingsbeleid gebruiken met voorwaardelijke toegang om alleen toegang te verlenen aan apparaten die voldoen aan de regels van het nalevingsbeleid voor de toegang tot e-mail en andere services.

U kunt nalevingsbeleid ook onafhankelijk van voorwaardelijke toegang gebruiken.
Bij onafhankelijk gebruik van nalevingsbeleid worden de betreffende apparaten geëvalueerd en samen met hun nalevingsstatus gerapporteerd. U kunt bijvoorbeeld rapporteren over het aantal apparaten dat niet is versleuteld of over welke apparaten zijn opengebroken of geroot. Bij onafhankelijk gebruik van nalevingsbeleid zijn er echter geen toegangsbeperkingen tot bedrijfsbronnen aanwezig.

U implementeert nalevingsbeleid voor gebruikers. Wanneer er nalevingsbeleid wordt geïmplementeerd voor een gebruiker, worden de apparaten van de gebruiker gecontroleerd op naleving. Zie Instellingen en functies op uw apparaten beheren voor meer informatie over hoe lang het duurt voordat mobiele apparaten een beleid krijgen nadat het beleid is geïmplementeerd.

##  <a name="concepts"></a>Concepten
Hieronder vindt u een aantal termen en begrippen die nuttig zijn voor een goed inzicht in nalevingsbeleid.

### <a name="compliance-requirements"></a>Nalevingsvereisten
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

##  <a name="differences-between-the-classic-intune-admin-console-and-intune-in-the-azure-portal"></a>Verschillen tussen de klassieke Intune-beheerconsole en Intune in Azure Portal


Als u eerder hebt gewerkt met de klassieke Intune-beheerconsole, moet u rekening houden met de volgende verschillen bij de overgang naar een nieuwe werkstroom voor het nalevingsbeleid voor apparaten in Azure Portal:


-   In Azure Portal wordt het nalevingsbeleid voor elk platform afzonderlijk gemaakt. In de Intune-beheerconsole werd één nalevingsbeleid voor alle ondersteunde platformen gemaakt.


<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="next-steps"></a>Volgende stappen

[Aan de slag met nalevingsbeleid](get-started-with-device-compliance.md)


<!---### See also

Conditional access--->



<!--HONumber=Feb17_HO1-->


