---
title: De MAM-configuratie valideren | Microsoft Docs
description: In deze onderwerpen wordt beschreven hoe u kunt testen en valideren of uw MAM-beleid juist is ingesteld en naar behoren werkt.
keywords: 
author: andredm7
ms.author: andredm
manager: angerobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 41d82597-e13e-4c3e-9151-e71392236ca0
ms.reviewer: joglocke
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: ab04c85d6704d7011cc5d4ea2a9f83d78b5b73e3
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="validating-your-mobile-application-management-setup"></a>De Mobile Application Management-configuratie valideren

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Dit onderwerp bevat informatie over het controleren op problemen na de configuratie van Mobile Application Management (MAM). Deze informatie is van toepassing op MAM-beleid in de Azure-portal.

### <a name="checking-for-symptoms"></a>Controleren op symptomen
Gebruikers melden waarschijnlijk geen problemen, omdat MAM een hulpprogramma voor gegevensbeveiliging is. Als er een probleem is met de MAM-configuratie, heeft de gebruiker onbeperkte toegang zoals ook het geval is zonder MAM, en weet de gebruiker niet dat er een probleem is. Daarom raden wij aan dat u de MAM-configuratie valideert door uw MAM-beleid te testen met een kleine groep gebruikers die de MAM-beperkingen bewust kunnen testen.


### <a name="what-to-check"></a>Wat u moet controleren

Als blijkt dat uw MAM-beleid niet werkt zoals verwacht, is het raadzaam het volgende te controleren:

- Hebben de gebruikers een licentie voor MAM?
- Hebben de gebruikers een licentie voor O365?
- De status van alle MAM-apps van de gebruikers. De apps kunnen de status **Ingecheckt** of **Niet ingecheckt** hebben.

#### <a name="user-mam-status"></a>MAM-status van gebruikers
1. Kies in de Azure-portal **Intune Mobile Application Management** > **Instellingen** > **App-beheer** > **Alle instellingen** > **App-rapportage door de gebruiker** > **Gebruikers**.

2. Kies een gebruiker uit de lijst of zoek een gebruiker en kies vervolgens **Gebruiker selecteren**. Boven aan de kolom **App-rapportage** ziet u of de gebruiker een licentie voor MAM heeft. Daaronder ziet u of de gebruiker een licentie voor O365 heeft en wat de app-status voor alle apparaten van de gebruiker is.

![App-status voor MAM](..\media\ts-mam-user-apps.png)

### <a name="what-to-do"></a>Wat u moet doen
Hier ziet u welke acties u moet ondernemen op basis van de gebruikersstatus:

- Als de gebruiker geen licentie voor MAM heeft, wijst u de gebruiker een Intune-licentie toe zoals beschreven in [Intune-licenties beheren](..\get-started\start-with-a-paid-subscription-to-microsoft-intune.md).
- Als de gebruiker geen licentie voor O365 heeft, vraagt u een licentie voor de gebruiker aan.
- Als de app van een gebruiker de status **Niet ingecheckt** heeft, controleert u of het MAM-beleid voor die app correct hebt geconfigureerd.
- Zorg ervoor dat deze voorwaarden worden toegepast op alle gebruikers waarop MAM-beleid van toepassing moet zijn.

### <a name="see-also"></a>Zie tevens
[Voorbereidingen voor het configureren van beleid voor het beheer van mobiele apps (Mobile App Management) met Microsoft Intune](..\deploy-use\get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)

[App-gegevens beveiligen via beleid voor het beheer van mobiele apps met Microsoft Intune](..\deploy-use\protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

