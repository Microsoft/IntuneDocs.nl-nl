---
title: De configuratie van uw beveiligingsbeleid voor apps valideren
titleSuffix: Microsoft Intune
description: Informatie over hoe u kunt testen of het beveiligingsbeleid van uw app is ingesteld en correct werkt in Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/27/2020
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.topic: conceptual
ms.technology: ''
ms.assetid: 15f8a838-0b69-412b-a42e-c6edb61f0cae
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ae6bfd71cb6730c9e71075df5ea2f45aa514178a
ms.sourcegitcommit: 045ca42cad6f86024af9a38a380535f42a6b4bef
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77781696"
---
# <a name="how-to-validate-your-app-protection-policy-setup-in-microsoft-intune"></a>De configuratie van uw beveiligingsbeleid voor apps valideren in Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Valideren dat het beveiligingsbeleid van uw app correct is ingesteld en werkt. Deze informatie is van toepassing op beveiligingsbeleid voor apps in Azure Portal.

## <a name="checking-for-symptoms"></a>Controleren op symptomen
Gebruikers melden waarschijnlijk geen problemen, omdat app-beveiliging een hulpprogramma voor gegevensbeveiliging is. Als er een probleem is met de beveiligingsconfiguratie voor de app, heeft de gebruiker onbeperkte toegang zoals ook het geval is zonder app-beveiliging, en weet de gebruiker niet dat er een probleem is. Daarom raden wij aan dat u de beveiligingsconfiguratie voor de app valideert door uw app-beveiligingsbeleid te testen met een kleine groep gebruikers die de beperkingen van de app-beveiliging bewust kunnen testen.

## <a name="what-to-check"></a>Wat u moet controleren

Als blijkt dat uw beveiligingsbeleid voor apps niet werkt zoals verwacht, controleert u deze items:

- Hebben de gebruikers een licentie voor app-beveiliging?
- Hebben de gebruikers een licentie voor O365?
- Is de status van elke beschermingsapp van de gebruiker zoals verwacht. De apps kunnen de status **Ingecheckt** of **Niet ingecheckt** hebben.

### <a name="user-app-protection-status"></a>Gebruikersstatus van de app-beveiliging
1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Selecteer **Apps** >  **App-beveiligingsstatus** en vervolgens de tegel **Toegewezen gebruikers**. 
4. Op de pagina **App-rapportage** selecteert u **Gebruiker selecteren** voor een lijst met gebruikers en groepen. 
5. Zoek naar en selecteer een gebruiker uit de lijst en kies vervolgens **Gebruiker selecteren**. Bovenaan het venster **App-rapportage** ziet u of de gebruiker een licentie voor app-beveiliging heeft. U kunt ook zien of de gebruiker een licentie voor O365 heeft en wat de app-status voor alle apparaten van de gebruiker is.

## <a name="what-to-do"></a>Wat u moet doen
Hier ziet u welke acties u moet ondernemen op basis van de gebruikersstatus:

- Als de gebruiker geen licentie voor app-beveiliging heeft, moet u een [Intune-licentie](../fundamentals/licenses.md) toewijzen aan de gebruiker.
- Als de gebruiker geen licentie voor O365 heeft, vraagt u een [licentie](../fundamentals/licenses.md) voor de gebruiker aan.
- Als de app van een gebruiker de status **Niet ingecheckt** heeft, controleert u of u het [beveiligingsbeleid voor apps](app-protection-policies-validate.md) voor de betreffende app correct hebt geconfigureerd.
- Zorg ervoor dat deze voorwaarden van toepassing zijn op alle gebruikers waarop [beveiligingsbeleid voor apps](app-protection-policies-monitor.md) van toepassing moet zijn.

## <a name="see-also"></a>Zie tevens

- [Wat is een app-beveiligingsbeleid in Intune?](app-protection-policies.md)
- [Licenties met Intune](../fundamentals/licenses.md)
- [Licenties toewijzen aan gebruikers zodat ze apparaten kunnen inschrijven bij Intune](../fundamentals/licenses-assign.md)
- [De configuratie van uw beveiligingsbeleid voor apps valideren](app-protection-policies-validate.md)
- [App-beveiligingsbeleid bewaken](app-protection-policies-monitor.md)

