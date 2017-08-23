---
title: Apps beheren via Microsoft Store voor Bedrijven
titleSuffix: Intune on Azure
description: Meer informatie over hoe u apps kunt synchroniseren in Intune vanuit Microsoft Store voor Bedrijven en ze vervolgens kunt toewijzen en bijhouden."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ed5d3f0-2749-45cd-b6bf-fd8c7c08bc1b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f5f1b49d0785682f72d208287098466934ff0e1
ms.sourcegitcommit: 1c71fff769ca0097faf46fc2b58b953ff28386e8
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2017
---
# <a name="how-to-manage-apps-you-purchased-from-the-microsoft-store-for-business-with-microsoft-intune"></a>Apps die u hebt aangeschaft in Microsoft Store voor Bedrijven, beheren met Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


[Microsoft Store voor Bedrijven](https://www.microsoft.com/business-store) biedt een centrale locatie om apps te zoeken en aan te schaffen voor uw organisatie. U kunt zowel afzonderlijke exemplaren van een app als grotere volumes aanschaffen. Als u Windows Store voor Bedrijven aan Microsoft Intune koppelt, kunt u apps die zijn aangeschaft via een volume-aankoopprogramma, beheren in de Intune-portal. Bijvoorbeeld:
* U kunt de lijst met aangeschafte apps synchroniseren met Intune.
* Apps die zijn gesynchroniseerd, worden weergegeven in de Intune-beheerconsole en u kunt deze apps op dezelfde manier toewijzen als andere apps.
* U kunt in de Intune-beheerconsole bijhouden hoeveel licenties er beschikbaar zijn en hoeveel licenties er worden gebruikt.
* Als er onvoldoende licenties beschikbaar zijn, worden de toewijzing en installatie van apps geblokkeerd met Intune.

## <a name="before-you-start"></a>Voordat u begint

Lees de volgende informatie voordat u begint met het synchroniseren en toewijzen van apps vanuit Microsoft Store voor Bedrijven:

- Configureer Intune als de Mobile Device Management-instantie voor uw organisatie.
- U moet zich hebben geregistreerd voor een account in Microsoft Store voor Bedrijven.
- Hebt u eenmaal een Windows Store voor Bedrijven-account aan Intune gekoppeld, dan kunt u later niet meer overschakelen op een ander account.
- Apps die zijn aangeschaft in Windows Store, kunnen niet handmatig worden toegevoegd aan of verwijderd uit Intune. Ze kunnen alleen worden gesynchroniseerd met Microsoft Store voor Bedrijven.
- In Intune kunt u zowel online als offline gelicentieerde apps synchroniseren die u hebt gekocht in Microsoft Store voor Bedrijven.
- Alleen gratis offline-apps kunnen worden gesynchroniseerd met Intune.
- Als u deze mogelijkheid wilt gebruiken, moeten apparaten zijn gekoppeld aan Active Directory Domain Services of aan de werkplek zijn toegevoegd.
- Geregistreerde apparaten moeten gebruikmaken van de 1511-versie van Windows 10 of hoger.

## <a name="associate-your-microsoft-store-for-business-account-with-intune"></a>Uw Microsoft Store voor Bedrijven-account koppelen aan Intune
Voordat u synchronisatie inschakelt in de Intune-console, moet u uw Store-account configureren om Intune te gebruiken als beheerprogramma:
1. Zorg ervoor dat u zich bij Windows Store voor Bedrijven aanmeldt met hetzelfde tenantaccount dat u gebruikt om u aan te melden bij Intune.
2. Kies in Windows Store voor Bedrijven **Instellingen** > **Beheerprogramma's**.
3. Kies op de pagina Beheerprogramma's de optie **Beheerprogramma toevoegen** en kies **Microsoft Intune**.

> [!NOTE]
> Eerder kon u maar één beheerhulpprogramma koppelen om apps toe te wijzen via Microsoft Store voor Bedrijven. U kunt nu meerdere beheerhulpprogramma's met de Store koppelen, bijvoorbeeld Intune en Configuration Manager.

U kunt nu doorgaan en synchronisatie instellen in de Intune-console.

## <a name="configure-synchronization"></a>Synchronisatie configureren

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Mobiele apps** op de blade **Intune**.
1. Kies op de blade **Mobiele apps** de optie **Instellen** > **Microsoft Store voor Bedrijven**.
2. Klik op **Inschakelen**.
3. Klik, als u dit nog niet hebt gedaan, op de koppeling om u te registreren bij Microsoft Store voor Bedrijven en uw account te koppelen zoals eerder is beschreven.
5. Kies in de vervolgkeuzelijst **Taal** de taal waarin apps uit Microsoft Store voor Bedrijven moeten worden weergegeven in de Intune-portal. Ongeacht de taal waarin deze apps worden weergegeven, worden ze geïnstalleerd in de taal van de eindgebruiker (indien beschikbaar).
6. Klik op **Synchroniseren** om de apps die u hebt aangeschaft in Microsoft Store, op te halen in Intune.

## <a name="synchronize-apps"></a>Apps synchroniseren

1. Kies in de workload **Mobiele apps** de optie **Instellen** > **Microsoft Store voor Bedrijven**.
2. Klik op **Synchroniseren** om de apps die u hebt aangeschaft in Microsoft Store, op te halen in Intune.

## <a name="assign-apps"></a>Apps toewijzen

U kunt apps uit de store op dezelfde manier toewijzen als elke andere Intune-app. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor meer informatie. In plaats van apps toe te wijzen vanaf de pagina **Alle apps** wijst u ze toe vanaf de pagina **Apps met een licentie**.

Offline-apps kunnen worden gericht op gebruikersgroepen, apparaatgroepen of groepen met gebruikers en apparaten.
Offline-apps kunnen worden geïnstalleerd voor een specifieke gebruiker op een apparaat of voor alle gebruikers op een apparaat. 


Wanneer u een Microsoft Store voor Bedrijven-app toewijst, heeft elke gebruiker die de app installeert hiervoor een licentie nodig. Als alle beschikbare licenties voor een toegewezen app zijn gebruikt, kunt u geen exemplaren van de app meer toewijzen. Ga in dat geval op een van de volgende manieren te werk:
* Verwijder de app van bepaalde apparaten.
* Beperk het bereik van de huidige toewijzing tot het aantal gebruikers waarvoor u een licentie hebt.
* Koop meer exemplaren van de app in Microsoft Store voor Bedrijven.


