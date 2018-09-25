---
title: Apps beheren via Microsoft Store voor Bedrijven
titlesuffix: Microsoft Intune
description: Meer informatie over hoe u apps kunt synchroniseren in Intune vanuit Microsoft Store voor Bedrijven en hoe u de apps vervolgens kunt toewijzen en bijhouden.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2ed5d3f0-2749-45cd-b6bf-fd8c7c08bc1b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0d1fe40b1cb5a496b3111b2630718a3dd17486ab
ms.sourcegitcommit: 63b74a60aafa8d2d6af0594448ae0471fbd79194
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/20/2018
ms.locfileid: "46494010"
---
# <a name="how-to-manage-apps-you-purchased-from-the-microsoft-store-for-business-with-microsoft-intune"></a>Apps die u hebt aangeschaft in Microsoft Store voor Bedrijven, beheren met Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

[Microsoft Store voor Bedrijven](https://www.microsoft.com/business-store) biedt een centrale locatie om apps te zoeken en aan te schaffen voor uw organisatie. U kunt zowel afzonderlijke exemplaren van een app als grotere volumes aanschaffen. Als u Windows Store voor Bedrijven aan Microsoft Intune koppelt, kunt u apps die zijn aangeschaft via een volume-aankoopprogramma, beheren in de Azure-portal. Bijvoorbeeld:
* U kunt de lijst met aangeschafte apps synchroniseren met Intune.
* Apps die zijn gesynchroniseerd, worden weergegeven in de Intune-beheerconsole en u kunt deze apps op dezelfde manier toewijzen als andere apps.
* U kunt in de Intune-beheerconsole bijhouden hoeveel licenties er beschikbaar zijn en hoeveel licenties er worden gebruikt.
* Als er onvoldoende licenties beschikbaar zijn, worden de toewijzing en installatie van apps geblokkeerd met Intune.
* Apps die worden beheerd door Microsoft Store voor Bedrijven trekken licenties automatisch in als een gebruiker het bedrijf verlaat of als de beheerder de gebruiker en de apparaten van de gebruiker verwijdert.

## <a name="before-you-start"></a>Voordat u begint

Lees de volgende informatie voordat u begint met het synchroniseren en toewijzen van apps vanuit Microsoft Store voor Bedrijven:

- Configureer Intune als de Mobile Device Management-instantie voor uw organisatie.
- U moet zich hebben geregistreerd voor een account in Microsoft Store voor Bedrijven.
- Wanneer u eenmaal een Microsoft Store voor Bedrijven-account aan Intune hebt gekoppeld, dan kunt u later niet meer overschakelen op een ander account.
- Apps die zijn aangeschaft in Windows Store, kunnen niet handmatig worden toegevoegd aan of verwijderd uit Intune. Ze kunnen alleen worden gesynchroniseerd met Microsoft Store voor Bedrijven.
- In de Intune-portal kunt u zowel online als offline gelicentieerde apps synchroniseren die u hebt gekocht in Microsoft Store voor Bedrijven. Vervolgens kunt u deze apps implementeren in apparaat- of gebruikersgroepen. 
- Online-app-installaties worden beheerd door de Store.
- Gratis offline-apps kunnen ook worden gesynchroniseerd met Intune. Deze apps worden geïnstalleerd door Intune en niet door de Store.
- Als u deze mogelijkheid wilt gebruiken, moeten apparaten zijn gekoppeld aan Active Directory Domain Services of aan de werkplek zijn toegevoegd.
- Geregistreerde apparaten moeten gebruikmaken van de 1511-versie van Windows 10 of hoger.

Daarnaast worden gerelateerde sets en gelicentieerde offline-apps die via de Microsoft Store voor Bedrijven werden gesynchroniseerd, nu geconsolideerd in een enkele app-vermelding in de gebruikersinterface. Alle implementatiegegevens van de afzonderlijke pakketten worden gemigreerd naar die ene vermelding. Als u gerelateerde sets in Azure Portal wilt bekijken, selecteert u **App-licenties** op de blade **Client-apps**.

## <a name="associate-your-microsoft-store-for-business-account-with-intune"></a>Uw Microsoft Store voor Bedrijven-account koppelen aan Intune
Voordat u synchronisatie inschakelt in de Intune-console, moet u uw Store-account configureren om Intune te gebruiken als beheerprogramma:
1. Zorg ervoor dat u zich bij Windows Store voor Bedrijven aanmeldt met hetzelfde tenantaccount dat u gebruikt om u aan te melden bij Intune.
2. Kies in Windows Store voor Bedrijven **Instellingen** > **Beheerprogramma's**.
3. Kies op de pagina Beheerprogramma's de optie **Beheerprogramma toevoegen** en kies **Microsoft Intune**.

> [!NOTE]
> Eerder kon u maar één beheerhulpprogramma koppelen om apps toe te wijzen via Microsoft Store voor Bedrijven. U kunt nu meerdere beheerhulpprogramma's met de Store koppelen, bijvoorbeeld Intune en Configuration Manager.

U kunt nu doorgaan en synchronisatie instellen in de Intune-console.

## <a name="configure-synchronization"></a>Synchronisatie configureren

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies in het deelvenster **Intune** de optie **Client-apps**.
1. Kies in het deelvenster **Client-apps** de optie **Instellen** > **Microsoft Store voor Bedrijven**.
2. Klik op **Inschakelen**.
3. Klik, als u dit nog niet hebt gedaan, op de koppeling om u te registreren bij Microsoft Store voor Bedrijven en uw account te koppelen zoals eerder is beschreven.
5. Kies in de vervolgkeuzelijst **Taal** de taal waarin apps uit Microsoft Store voor Bedrijven moeten worden weergegeven in Azure Portal. Ongeacht de taal waarin deze apps worden weergegeven, worden ze geïnstalleerd in de taal van de eindgebruiker (indien beschikbaar).
6. Klik op **Synchroniseren** om de apps die u hebt aangeschaft in Microsoft Store, op te halen in Intune.

## <a name="synchronize-apps"></a>Apps synchroniseren

1. Kies in de workload **Client-apps** de optie **Instellen** > **Microsoft Store voor Bedrijven**.
2. Klik op **Synchroniseren** om de apps die u hebt aangeschaft in Microsoft Store, op te halen in Intune.

## <a name="assign-apps"></a>Apps toewijzen

U kunt apps uit de store op dezelfde manier toewijzen als elke andere Intune-app. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor meer informatie. In plaats van apps toe te wijzen vanaf de pagina **Alle apps** wijst u ze toe vanaf de pagina **Apps met een licentie**.

Offline-apps kunnen worden gericht op gebruikersgroepen, apparaatgroepen of groepen met gebruikers en apparaten.
Offline-apps kunnen worden geïnstalleerd voor een specifieke gebruiker op een apparaat of voor alle gebruikers op een apparaat. 


Wanneer u een Microsoft Store voor Bedrijven-app toewijst, heeft elke gebruiker die de app installeert hiervoor een licentie nodig. Als alle beschikbare licenties voor een toegewezen app zijn gebruikt, kunt u geen exemplaren van de app meer toewijzen. Ga in dat geval op een van de volgende manieren te werk:
* Verwijder de app van bepaalde apparaten.
* Beperk het bereik van de huidige toewijzing tot het aantal gebruikers waarvoor u een licentie hebt.
* Koop meer exemplaren van de app in Microsoft Store voor Bedrijven.


