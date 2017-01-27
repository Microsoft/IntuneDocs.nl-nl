---
title: "Scenario’s voor het beveiligen van e-mail | Microsoft Docs"
description: "Enkele voorbeeldscenario&quot;s en hoe deze kunnen worden geïmplementeerd met voorwaardelijke toegang."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 454eab79-b620-42c9-b8e6-fada6e719fcd
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9f05e516723976dcf6862475dbb78f9dce2913be
ms.openlocfilehash: c02961aa984f8041394639a872bf4cfcdfc0be91


---

# <a name="protect-access-to-email-with-microsoft-intune-example-scenarios"></a>Toegang tot e-mail beveiligen met Microsoft Intune: voorbeeldscenario’s

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="scenario-1-block-users-from-using-noncompliant-devices-to-access-exchange-online"></a>Scenario 1: de toegang tot Exchange Online blokkeren voor gebruikers met een apparaat dat niet voldoet aan het beleid.
### <a name="scenario-requirements"></a>Scenariovereisten
- Voor alle gebruikers in de Azure Active Directory-beveiligingsgroep **Accounting** moet de toegang tot Exchange Online worden geblokkeerd als hun apparaat niet voldoet aan het door u geïmplementeerde nalevingsbeleid.
- Als de groep gebruikers bevat van wie het apparaat niet door [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] wordt ondersteund, mogen zij via dat apparaat geen toegang krijgen tot Exchange Online.
- Bovendien moeten alle gebruikers in de Azure Active Directory-beveiligingsgroep **Finance** worden uitgesloten van het beleid, zelfs als ze zich ook in de beveiligingsgroep **Accounting** bevinden.

U doet dit door een beleid voor voorwaardelijke toegang voor Exchange Online te configureren met de volgende instellingen:

- Kies **Beleid voor voorwaardelijke toegang inschakelen**.

- Kies de platformen die u toegang wilt geven vanuit apps met moderne verificatie.
- Kies voor Exchange ActiveSync-apps de optie **Apparaten die het beleid niet naleven op platformen die worden ondersteund door Microsoft Intune** en **Alle andere apparaten op platformen die niet worden ondersteund door Microsoft Intune blokkeren**.
-   Kies in de sectie **Doelgroep** onder **Geselecteerde beveiligingsgroepen** de gebruikersgroep **Accounting**.

-   Kies in de sectie **Uitgesloten groep** onder **Geselecteerde beveiligingsgroepen** de gebruikersgroep **Finance**.


De volgende werkstroom wordt in het scenario gebruikt om te bepalen welke apparaten toegang krijgen tot Exchange Online:

![Diagram met werkstroom voor toegang tot apparaten](./media/ConditionalAccess8-5.png)

## <a name="scenario-2-all-ios-devices-that-access-exchange-on-premises-must-be-managed-by-intune"></a>Scenario 2: alle iOS-apparaten die toegang hebben tot Exchange On-premises, moeten worden beheerd door Intune
### <a name="scenario-requirements"></a>Scenariovereisten
- Alleen apparaten met iOS hebben toegang tot Exchange On-premises.
- De apparaten moeten ook worden ingeschreven in Intune en voldoen aan de regels van het nalevingsbeleid voordat ze kunnen worden gebruikt om toegang te krijgen tot Exchange.

U doet dit door het volgende beleid voor voorwaardelijke toegang voor Exchange On-premises te configureren met de volgende instellingen:

-   Kies de optie **De toegang tot Exchange On-premises blokkeren voor e-mail-apps indien het apparaat niet voldoet aan het beleid of niet is geregistreerd bij Microsoft Intune**. Door deze optie te kiezen, wordt het beleid voor voorwaardelijke toegang ingeschakeld, waarvoor is vereist dat alle apparaten in Microsoft Intune moeten zijn geregistreerd en voldoen aan de regels van het nalevingsbeleid, voordat ze toegang kunnen krijgen tot Exchange.

-   Als u geavanceerde Exchange Active Sync-instellingen wilt maken, maakt u het volgende:

  -   Platformuitzondering waardoor apparaten met iOS toegang krijgen tot Exchange.   

  -   Als voor een apparaat een standaardregel geldt waarmee wordt aangegeven wanneer de platformuitzonderingsregel niet van toepassing is op een apparaat, mag dat apparaat geen toegang krijgen tot Exchange. Deze regel zorgt ervoor dat de toegang tot Exchange voor apparaten zonder iOS wordt geblokkeerd.

U gebruikt de volgende stroom om te bepalen welke apparaten toegang krijgen tot Exchange:

![Diagram met werkstroom voor toegang tot apparaten](./media/ConditionalAccess8-3.png)

## <a name="scenario-3-no-android-devices-can-access-exchange-on-premises"></a>Scenario 3: Android-apparaten krijgen geen toegang tot Exchange On-premises
### <a name="scenario-requirements"></a>Scenariovereisten
- Voor alle Android-apparaten moet de toegang tot Exchange worden geblokkeerd.
- Alle andere ondersteunde apparaten kunnen wel toegang krijgen tot Exchange op voorwaarde dat ze worden beheerd door [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

U doet dit door een beleid voor voorwaardelijke toegang voor Exchange On-premises te configureren met de volgende instellingen:

-   Kies de optie **De toegang tot Exchange On-premises blokkeren voor e-mail-apps indien het apparaat niet voldoet aan het beleid of niet is geregistreerd bij Microsoft Intune**. Als u deze optie kiest, moet elk apparaat zijn geregistreerd bij Intune en voldoen aan de regels van het nalevingsbeleid.

- Als u geavanceerde Exchange Active Sync-instellingen wilt maken, maakt u het volgende:
  -   Een platformuitzondering waardoor apparaten met Android geen toegang krijgen tot Exchange. Deze regel zorgt ervoor dat Android-apparaten niet kunnen worden gebruikt voor toegang tot Exchange.

  -   Een standaardregel waarmee wordt aangegeven dat wanneer een apparaat niet onder andere regels valt, er toegang tot Exchange moet worden gegeven. Deze standaardregel zorgt ervoor dat apparaten waarop een ander platform dan Android wordt uitgevoerd, maar dat wel door Microsoft Intune wordt ondersteund, kunnen worden gebruikt voor toegang tot Exchange. Ze moeten echter bij Intune worden geregistreerd en voldoen aan de regels van het nalevingsbeleid.

U gebruikt de volgende stroom om te bepalen welke apparaten toegang krijgen tot Exchange:

![Diagram met werkstroom voor toegang tot apparaten](./media/ConditionalAccess8-4.png)



<!--HONumber=Jan17_HO4-->


