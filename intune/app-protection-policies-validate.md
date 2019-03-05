---
title: De configuratie van uw beveiligingsbeleid voor apps valideren
titleSuffix: Microsoft Intune
description: Informatie over hoe u kunt testen of het beveiligingsbeleid van uw app is ingesteld en correct werkt.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/13/2018
ms.prod: ''
ms.service: microsoft-intune
ms.topic: conceptual
ms.technology: ''
ms.assetid: 15f8a838-0b69-412b-a42e-c6edb61f0cae
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c2156dc466fa1b49c9bb3886af596b8a2cb0ccc2
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57234303"
---
# <a name="how-to-validate-your-app-protection-policy-setup"></a>De configuratie van uw beveiligingsbeleid voor apps valideren

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Valideren dat het beveiligingsbeleid van uw app correct is ingesteld en werkt. Deze informatie is van toepassing op beveiligingsbeleid voor apps in Azure Portal.

## <a name="checking-for-symptoms"></a>Controleren op symptomen
Gebruikers melden waarschijnlijk geen problemen, omdat app-beveiliging een hulpprogramma voor gegevensbeveiliging is. Als er een probleem is met de beveiligingsconfiguratie voor de app, heeft de gebruiker onbeperkte toegang zoals ook het geval is zonder app-beveiliging, en weet de gebruiker niet dat er een probleem is. Daarom raden wij aan dat u de beveiligingsconfiguratie voor de app valideert door uw app-beveiligingsbeleid te testen met een kleine groep gebruikers die de beperkingen van de app-beveiliging bewust kunnen testen.


## <a name="what-to-check"></a>Wat u moet controleren

Als blijkt dat uw beveiligingsbeleid voor apps niet werkt zoals verwacht, controleert u deze items:

- Hebben de gebruikers een licentie voor app-beveiliging?
- Hebben de gebruikers een licentie voor O365?
- De status van alle app-beveiligingsapps van de gebruikers. De apps kunnen de status **Ingecheckt** of **Niet ingecheckt** hebben.

### <a name="user-app-protection-status"></a>Gebruikersstatus van de app-beveiliging
1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Selecteer **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Selecteer **Client-apps** > **Bewaken** >  **App-beveiligingsstatus** en vervolgens de tegel **Toegewezen gebruikers**. 
4. Op de pagina **App-rapportage** selecteert u **Gebruiker selecteren** voor een lijst met gebruikers en groepen. 
5. Zoek naar en selecteer een gebruiker uit de lijst en kies vervolgens **Gebruiker selecteren**. Bovenaan het venster **App-rapportage** ziet u of de gebruiker een licentie voor app-beveiliging heeft. U kunt ook zien of de gebruiker een licentie voor O365 heeft en wat de app-status voor alle apparaten van de gebruiker is.



## <a name="what-to-do"></a>Wat u moet doen
Hier ziet u welke acties u moet ondernemen op basis van de gebruikersstatus:

- Als de gebruiker geen licentie voor app-beveiliging heeft, moet u een Intune-licentie toewijzen aan de gebruiker.
- Als de gebruiker geen licentie voor O365 heeft, vraagt u een licentie voor de gebruiker aan.
- Als de app van een gebruiker de status **Niet ingecheckt** heeft, controleert u of u het beveiligingsbeleid voor apps voor de betreffende app correct hebt geconfigureerd.
- Zorg ervoor dat deze voorwaarden van toepassing zijn op alle gebruikers waarop beveiligingsbeleid voor apps van toepassing moet zijn.

## <a name="see-also"></a>Zie tevens

[Wat is een app-beveiligingsbeleid in Intune?](app-protection-policies.md)
