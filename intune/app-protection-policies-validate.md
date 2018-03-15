---
title: De configuratie van uw beveiligingsbeleid voor apps valideren
titleSuffix: Microsoft Intune
description: Informatie over hoe u kunt testen of het beveiligingsbeleid van uw app is ingesteld en correct werkt.
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 15f8a838-0b69-412b-a42e-c6edb61f0cae
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 980773eb59553c492ac338808476cfb55f2ddfb8
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/05/2018
---
# <a name="how-to-validate-your-app-protection-policy-setup"></a>De configuratie van uw beveiligingsbeleid voor apps valideren

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Valideren dat het beveiligingsbeleid van uw app correct is ingesteld en werkt. Deze informatie is van toepassing op beveiligingsbeleid voor apps in Azure Portal.

### <a name="checking-for-symptoms"></a>Controleren op symptomen
Gebruikers melden waarschijnlijk geen problemen, omdat app-beveiliging een hulpprogramma voor gegevensbeveiliging is. Als er een probleem is met de configuratie van de app-beveiliging, heeft de gebruiker onbeperkte toegang zoals ook het geval is zonder app-beveiliging, en weet de gebruiker niet dat er een probleem is. Daarom raden wij aan dat u de configuratie van de app-beveiliging valideert door uw app-beveiligingsbeleid te testen met een kleine groep gebruikers die de beperkingen van de app-beveiliging bewust kunnen testen.


### <a name="what-to-check"></a>Wat u moet controleren

Als blijkt dat uw beveiligingsbeleid voor apps niet werkt zoals verwacht, is het raadzaam deze items te controleren:

- Hebben de gebruikers een licentie voor app-beveiliging?
- Hebben de gebruikers een licentie voor O365?
- De status van alle app-beveiligingsapps van de gebruikers. De apps kunnen de status **Ingecheckt** of **Niet ingecheckt** hebben.

#### <a name="user-app-protection-status"></a>Gebruikersstatus van de app-beveiliging
1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Bewaking en beheer**.
1. Kies **Apps beheren** > **Bewaken** >  **App- beveiligingsstatus** > **Toegewezen gebruikers**.

2. Kies een gebruiker uit de lijst of zoek en selecteer een gebruiker en kies vervolgens **Gebruiker selecteren**. Bovenaan de kolom **App-rapportage** ziet u of de gebruiker een licentie voor app-beveiliging heeft. U kunt ook zien of de gebruiker een licentie voor O365 heeft en wat de app-status voor alle apparaten van de gebruiker is.



### <a name="what-to-do"></a>Wat u moet doen
Hier ziet u welke acties u moet ondernemen op basis van de gebruikersstatus:

- Als de gebruiker geen licentie voor app-beveiliging heeft, moet u een Intune-licentie toewijzen aan de gebruiker.
- Als de gebruiker geen licentie voor O365 heeft, vraagt u een licentie voor de gebruiker aan.
- Als de app van een gebruiker de status **Niet ingecheckt** heeft, controleert u of u het beveiligingsbeleid voor apps voor de betreffende app correct hebt geconfigureerd.
- Zorg ervoor dat deze voorwaarden worden toegepast op alle gebruikers waarop beveiligingsbeleid voor apps van toepassing moet zijn.

### <a name="see-also"></a>Zie ook

[Wat is een app-beveiligingsbeleid in Intune?](app-protection-policies.md)
