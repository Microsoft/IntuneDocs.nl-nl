---
title: Beveiligingsbeleid voor apps valideren
titleSuffix: Azure portal
description: In deze onderwerpen wordt beschreven hoe u kunt testen en valideren of uw beveiligingsbeleid voor apps juist is ingesteld en naar behoren werkt.
keywords: 
author: erikre
ms.author: erikre
manager: angerobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 15f8a838-0b69-412b-a42e-c6edb61f0cae
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7914946519bc1977aeabfb474f66d4ced2a8f8ee
ms.sourcegitcommit: 67ec0606c5440cffa7734f4eefeb7121e9d4f94f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/08/2017
---
# <a name="how-to-validate-your-app-protection-policy-setup"></a>De configuratie van uw beveiligingsbeleid voor apps valideren

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Dit onderwerp bevat informatie over het controleren op problemen na de configuratie van een beveiligingsbeleid voor apps. Deze informatie is van toepassing op beveiligingsbeleid voor apps in Azure Portal.

### <a name="checking-for-symptoms"></a>Controleren op symptomen
Gebruikers melden waarschijnlijk geen problemen, omdat app-beveiliging een hulpprogramma voor gegevensbeveiliging is. Als er een probleem is met de configuratie van de app-beveiliging, heeft de gebruiker onbeperkte toegang zoals ook het geval is zonder app-beveiliging, en weet de gebruiker niet dat er een probleem is. Daarom raden wij aan dat u de configuratie van de app-beveiliging valideert door uw app-beveiligingsbeleid te testen met een kleine groep gebruikers die de beperkingen van de app-beveiliging bewust kunnen testen.


### <a name="what-to-check"></a>Wat u moet controleren

Als blijkt dat uw beveiligingsbeleid voor apps niet werkt zoals verwacht, is het raadzaam het volgende te controleren:

- Hebben de gebruikers een licentie voor app-beveiliging?
- Hebben de gebruikers een licentie voor O365?
- De status van alle app-beveiligingsapps van de gebruikers. De apps kunnen de status **Ingecheckt** of **Niet ingecheckt** hebben.

#### <a name="user-app-protection-status"></a>Gebruikersstatus van de app-beveiliging
1. Kies **Apps beheren** > **Controleren** >  **Gebruikersstatus van de app-beveiliging** > **Gebruikers** in Azure Portal.

2. Kies een gebruiker uit de lijst of zoek een gebruiker en kies vervolgens **Gebruiker selecteren**. Boven aan de kolom **App-rapportage** ziet u of de gebruiker een licentie voor app-beveiliging heeft. Daaronder ziet u of de gebruiker een licentie voor O365 heeft en wat de app-status voor alle apparaten van de gebruiker is.



### <a name="what-to-do"></a>Wat u moet doen
Hier ziet u welke acties u moet ondernemen op basis van de gebruikersstatus:

- Als de gebruiker geen licentie voor app-beveiliging heeft, moet u een Intune-licentie toewijzen aan de gebruiker.
- Als de gebruiker geen licentie voor O365 heeft, vraagt u een licentie voor de gebruiker aan.
- Als de app van een gebruiker de status **Niet ingecheckt** heeft, controleert u of u het beveiligingsbeleid voor apps voor de betreffende app correct hebt geconfigureerd.
- Zorg ervoor dat deze voorwaarden worden toegepast op alle gebruikers waarop beveiligingsbeleid voor apps van toepassing moet zijn.

### <a name="see-also"></a>Zie tevens

[Wat is een app-beveiligingsbeleid in Intune?](app-protection-policies.md)
