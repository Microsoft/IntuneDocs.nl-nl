---
title: E-mail en Office 365 beveiligen | Microsoft Docs
description: In dit onderwerp wordt beschreven hoe u voorwaardelijke toegang gebruikt om alleen compatibele apparaten toegang te geven tot e-mail en bedrijfsgegevens op SharePoint Online en andere services.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c564d292-b83b-440d-bf08-3f5b299b7a5e
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 9f05e516723976dcf6862475dbb78f9dce2913be
ms.openlocfilehash: 399c6260a98d51417a067d001c0fd42c926c1513
ms.lasthandoff: 01/24/2017


---

# <a name="protect-access-to-email-office-365-and-other-services-with-microsoft-intune"></a>De toegang tot e-mail, Office 365-services en andere services beveiligen met Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

U kunt toegang tot uw bedrijfs-e-mail, Office 365-services zoals **Exchange On-premises**, **Exchange Online**, **Exchange Online Dedicated**, **SharePoint Online** en **Skype voor Bedrijven Online** en andere services beveiligen met behulp van voorwaardelijke toegang van Enterprise Mobility + Security (EMS). Hiermee kunt u ervoor zorgen dat de toegang tot uw bedrijfs-e-mail en Office 365-services wordt beperkt tot apparaten die de regels voor voorwaardelijke toegang naleven die u in de Intune-beheerconsole of via de klassieke Azure-portal hebt ingesteld.
## <a name="how-does-conditional-access-work"></a>Hoe werkt voorwaardelijke toegang?
U kunt de instellingen voor nalevingsbeleid gebruiken om te evalueren in hoeverre het apparaat aan het beleid voldoet. Deze evaluatie wordt vervolgens gebruikt voor een beleid voor voorwaardelijke toegang om de toegang tot een specifieke service te beperken of toe te staan. Wanneer u een beleid voor voorwaardelijke toegang gebruikt in combinatie met een nalevingsbeleid voor apparaten, is de service alleen toegankelijk voor apparaten die voldoen aan het beleid. Het nalevingsbeleid en het beleid voor voorwaardelijke toegang worden op de gebruiker toegepast. Een apparaat dat de gebruiker gebruikt voor toegang tot de services wordt gecontroleerd op naleving van het beleid.

> [!IMPORTANT] 
> Houd er rekening mee dat er nalevingsbeleid moet worden geïmplementeerd voor de gebruiker van het apparaat, zodat de naleving door het apparaat kan worden geëvalueerd.
> Als er geen nalevingsbeleid wordt geïmplementeerd voor de gebruiker, wordt het apparaat beschouwd als een apparaat dat voldoet aan het beleid en worden er geen toegangsbeperkingen toegepast.

Wanneer apparaten niet voldoen aan de voorwaarden die in de beleidsregels zijn ingesteld, wordt de eindgebruiker door de registratieprocedure voor het apparaat geleid en ook door de procedure voor het verhelpen van het probleem dat naleving door het apparaat verhindert.

Een kenmerkend proces voor voorwaardelijke toegang:

![Diagram met de beslissingspunten die worden gebruikt om te bepalen of een apparaat toegang tot een service krijgt of wordt geblokkeerd](../media/ConditionalAccess4.png)

## <a name="setup-considerations"></a>Overwegingen bij de installatie

### <a name="licensing"></a>Licentieverlening

Microsoft Intune en Azure Active Directory (Azure AD) Premium werken naadloos samen om meerdere beheerlagen via EMS-voorwaardelijke toegang te verschaffen. Als u beleid voor voorwaardelijke toegang wilt implementeren met behulp van Intune, moet u een licentie voor beide producten hebben.

**Azure AD Premium-licenties** kunnen als zelfstandige service of (samen met Intune) als onderdeel van een Enterprise-overeenkomst worden gekocht. Als u beleid voor voorwaardelijke toegang hebt geïmplementeerd met Intune, zorg er dan voor dat u de juiste Azure AD Premium- of **EMS-licenties** hebt.

- Raadpleeg de [Enterprise Mobility-pagina met prijzen](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility-pricing) of de [Azure Active Directory-pagina met prijzen](https://azure.microsoft.com/en-us/pricing/details/active-directory/) voor meer informatie.

Controleer ook of de gebruikers voor wie u beleid voor voorwaardelijke toegang wilt instellen, [de Azure AD Premium- of EMS-licenties toegewezen hebben gekregen](/Intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-4.md).

### <a name="device-compliance-settings"></a>Instellingen voor nalevingsbeleid voor apparaten

Configureer nalevingsbeleid voor apparaten en beleid voor voorwaardelijke toegang als u voorwaardelijke toegang wilt instellen. Het nalevingsbeleid omvat instellingen zoals een wachtwoordcode, versleuteling en instructies voor als het apparaat is gekraakt. Het apparaat moet voldoen aan deze regels om te worden beschouwd als een apparaat dat het beleid naleeft.

- Meer informatie over [nalevingsbeleid voor apparaten en hoe het werkt ](introduction-to-device-compliance-policies-in-microsoft-intune.md).

### <a name="conditional-access-policy"></a>Beleid voor voorwaardelijke toegang

U kunt beleid voor voorwaardelijke toegang instellen om toegang te beveiligen op basis van:
- De nalevingsstatus van het apparaat.
- Het platform dat op het apparaat wordt uitgevoerd.
- Het type apps dat wordt gebruikt voor toegang tot de services.

In tegenstelling tot andere Intune-beleidsregels implementeert u geen beleidsregels voor voorwaardelijke toegang. Nadat u het beleid hebt geconfigureerd en de gebruikers hebt geselecteerd op wie het beleid moet worden toegepast, wordt in plaats daarvan het beleid op alle bedoelde gebruikers toegepast. Wanneer een gebruiker deel uitmaakt van de doelgroep voor het beleid, moet elk apparaat waarmee deze gebruiker werkt, aan het beleid voldoen om toegang te krijgen tot resources.


## <a name="next-steps"></a>Volgende stappen


2. [Nalevingsbeleid voor apparaten maken](create-a-device-compliance-policy-in-microsoft-intune.md).

2.  Maak beleid voor voorwaardelijke toegang voor een van de volgende Microsoft-cloudservices/-producten:

  - [Maak beleid voor voorwaardelijke toegang voor Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Maak beleid voor voorwaardelijke toegang voor Exchange On-premises](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [Maak beleid voor voorwaardelijke toegang voor Exchange Online Dedicated](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Maak beleid voor voorwaardelijke toegang voor oudere versies van Exchange Online Dedicated](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [Beleid voor voorwaardelijke toegang maken voor SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  - [Beleid voor voorwaardelijke toegang maken voor Skype voor Bedrijven Online](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  - [Beleid voor voorwaardelijke toegang maken voor Dynamics CRM Online](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)

