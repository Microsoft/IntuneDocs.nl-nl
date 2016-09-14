---
title:
- De MAM-configuratie valideren | Microsoft Intune
description: In deze onderwerpen wordt beschreven hoe u kunt testen en valideren of uw MAM-beleid juist is ingesteld en naar behoren werkt.
keywords: 
author: karthikaraman
manager: angerobe
ms.date: 08/16/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 41d82597-e13e-4c3e-9151-e71392236ca0
ms.reviewer: joglocke
translationtype: Human Translation
ms.sourcegitcommit: 52d9301f6297065f752cea1dd19024efb11f0730
ms.openlocfilehash: a92334871301523c33f7453038df3ae0fc1fd1a4


---

# De Mobile Application Management-configuratie valideren

Dit onderwerp bevat informatie over het controleren op problemen na de configuratie van Mobile Application Management (MAM). Deze informatie is van toepassing op MAM-beleid in de Azure-portal.

### Controleren op symptomen
Gebruikers melden waarschijnlijk geen problemen, omdat MAM een hulpprogramma voor gegevensbeveiliging is. Als er een probleem is met de MAM-configuratie, heeft de gebruiker onbeperkte toegang zoals ook het geval is zonder MAM, en weet de gebruiker niet dat er een probleem is. Daarom raden wij aan dat u de MAM-configuratie valideert door uw MAM-beleid te testen met een kleine groep gebruikers die de MAM-beperkingen bewust kunnen testen. 


### Wat u moet controleren 

Als blijkt dat uw MAM-beleid niet werkt zoals verwacht, is het raadzaam het volgende te controleren:

- Hebben de gebruikers een licentie voor MAM?
- Hebben de gebruikers een licentie voor O365?
- De status van alle MAM-apps van de gebruikers. De apps kunnen de status **Ingecheckt** of **Niet ingecheckt** hebben.

#### MAM-status van gebruikers
1. Kies in de Azure-portal **Intune Mobile Application Management** > **Instellingen** > **App-beheer** > **Alle instellingen** > **App-rapportage door de gebruiker** > **Gebruikers**.

2. Kies een gebruiker uit de lijst of zoek een gebruiker en kies vervolgens **Gebruiker selecteren**. Boven aan de kolom **App-rapportage** ziet u of de gebruiker een licentie voor MAM heeft. Daaronder ziet u of de gebruiker een licentie voor O365 heeft en wat de app-status voor alle apparaten van de gebruiker is.

![App-status voor MAM](..\media\ts-mam-use-apps.png) 

### Wat u moet doen
Hier ziet u welke acties u moet ondernemen op basis van de gebruikersstatus:

- Als de gebruiker geen licentie voor MAM heeft, wijst u de gebruiker een Intune-licentie toe zoals beschreven in [Intune-licenties beheren](..\get-started\start-with-a-paid-subscription-to-microsoft-intune).
- Als de gebruiker geen licentie voor O365 heeft, vraagt u een licentie voor de gebruiker aan.
- Als de app van een gebruiker de status **Niet ingecheckt** heeft, controleert u of het MAM-beleid voor die app correct hebt geconfigureerd.
- Zorg ervoor dat deze voorwaarden worden toegepast op alle gebruikers waarop MAM-beleid van toepassing moet zijn.

### Zie tevens
[Voorbereidingen voor het configureren van beleid voor het beheer van mobiele apps (Mobile App Management) met Microsoft Intune](..\deploy-use\get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)

[App-gegevens beveiligen via beleid voor het beheer van mobiele apps met Microsoft Intune](..\deploy-use\protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)



<!--HONumber=Aug16_HO5-->


