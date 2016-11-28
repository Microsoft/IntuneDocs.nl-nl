---
title: De toegang tot e-mail en O365-services beperken | Microsoft Intune
description: In dit onderwerp wordt beschreven hoe voorwaardelijke toegang kan worden gebruikt om alleen compatibele apparaten toegang te geven tot e-mail en bedrijfsgegevens op SharePoint Online en andere services.
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c564d292-b83b-440d-bf08-3f5b299b7a5e
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 027e7e56e6f7d3a604336e0465f688af514c69e6
ms.openlocfilehash: 68fc47ba9f63f2ba05abae1f0e5ae5c6b3dca463


---

# <a name="restrict-access-to-email-o365-and-other-services-with-microsoft-intune"></a>De toegang tot e-mail, O365-services en andere services beperken met Microsoft Intune
U kunt toegang tot uw bedrijfse-mail en O365-services beperken met voorwaardelijke toegang van Intune. Voorwaardelijke toegang van Intune geeft u de mogelijkheid ervoor te zorgen dat toegang tot uw bedrijfse-mail en O365-services wordt beperkt tot apparaten die de door u ingestelde regels naleven.
## <a name="how-does-conditional-access-work"></a>Hoe werkt voorwaardelijke toegang?
Op basis van de instellingen voor nalevingsbeleid wordt beoordeeld in hoeverre het apparaat het geldende beleid naleeft. Het beleid voor voorwaardelijke toegang gebruikt deze beoordeling vervolgens om de toegang tot een specifieke service te beperken of toe te staan. Wanneer beleid voor voorwaardelijke toegang wordt gebruikt in combinatie met nalevingsbeleid, kunnen alleen apparaten die het beleid naleven, toegang tot de service krijgen. Het nalevingsbeleid en het beleid voor voorwaardelijke toegang worden op de gebruiker toegepast. Een apparaat dat de gebruiker gebruikt voor toegang tot de services wordt gecontroleerd op naleving van het beleid.

Houd er rekening mee dat er nalevingsbeleid moet worden geïmplementeerd voor de gebruiker van het apparaat, zodat de naleving door het apparaat kan worden beoordeeld.
Als er geen nalevingsbeleid wordt geïmplementeerd voor de gebruiker, wordt het apparaat beschouwd als een apparaat dat het beleid naleeft en worden er geen toegangsbeperkingen toegepast.

Wanneer apparaten niet voldoen aan de voorwaarden die u in het beleid instelt, wordt de eindgebruiker door de inschrijvingsprocedure voor het apparaat geleid en ook door de procedure voor het verhelpen van het probleem dat naleving door het apparaat verhindert.

Een kenmerkend proces voor voorwaardelijke toegang:

![Het diagram geeft de beslissingspunten aan waarmee moet worden bepaald of een apparaat toegang tot een service krijgt of wordt geblokkeerd](../media/ConditionalAccess4.png)

## <a name="how-to-configure-conditional-access"></a>Hoe configureert u beleid voor voorwaardelijke toegang?
Gebruik voorwaardelijke toegang om toegang te beheren tot Microsoft **Exchange On-premises**, **Exchange Online**, **Exchange Online Dedicated**, **SharePoint Online** en **Skype voor Bedrijven Online**.

Configureer nalevingsbeleid voor apparaten en beleid voor voorwaardelijke toegang als u voorwaardelijke toegang wilt instellen.

Het nalevingsbeleid omvat instellingen zoals een wachtwoordcode, versleuteling en instructies voor als het apparaat is gekraakt. Het apparaat moet voldoen aan deze regels om te worden beschouwd als een apparaat dat het beleid naleeft.

U kunt beleid voor voorwaardelijke toegang instellen om toegang te beperken op basis van:
- De nalevingsstatus van het apparaat.
- Het platform dat op het apparaat wordt uitgevoerd.
- Het type apps dat wordt gebruikt om toegang tot de services te krijgen.

In tegenstelling tot andere Intune-beleidsregels implementeert u geen beleid voor voorwaardelijke toegang. Nadat u het beleid hebt geconfigureerd en de gebruikers hebt geselecteerd op wie het beleid moet worden toegepast, wordt in plaats daarvan het beleid op alle bedoelde gebruikers toegepast. Wanneer een gebruiker deel uitmaakt van de doelgroep voor het beleid, moet elk apparaat dat hij of zij gebruikt, aan het beleid voldoen om toegang te krijgen tot bronnen.


## <a name="next-steps"></a>Volgende stappen
1. [Meer informatie over nalevingsbeleid voor apparaten en hoe het werkt ](introduction-to-device-compliance-policies-in-microsoft-intune.md)

2. [Een nalevingsbeleid maken](create-a-device-compliance-policy-in-microsoft-intune.md)

2.  Maak beleid voor voorwaardelijke toegang voor een van de volgende producten:
> [!div class="op_single_selector"]
  - [Maak beleid voor voorwaardelijke toegang voor Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Maak beleid voor voorwaardelijke toegang voor Exchange On-premises](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [Maak beleid voor voorwaardelijke toegang voor Exchange Online Dedicated](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Maak beleid voor voorwaardelijke toegang voor oudere versies van Exchange Online Dedicated](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [Maak beleid voor voorwaardelijke toegang voor SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  - [Maak beleid voor voorwaardelijke toegang voor Skype voor Bedrijven Online](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  - [Maak beleid voor voorwaardelijke toegang voor Dynamics CRM Online](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)



<!--HONumber=Nov16_HO2-->


