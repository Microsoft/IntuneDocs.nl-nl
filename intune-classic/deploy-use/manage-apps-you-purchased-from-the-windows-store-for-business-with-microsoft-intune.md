---
title: Apps uit de Windows Store voor Bedrijven beheren | Microsoft Docs
description: Microsoft Intune verbinden met de Windows Store voor Bedrijven als u apps via het volume-aankoopprogramma hebt gekocht vanuit de Intune-console.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e38d47d-0c5e-40ce-b379-29d3657f5c28
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 0a6c84735b6bb8e7f636ea155437e7d90b8f3cc0
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune"></a>Apps die u hebt aangeschaft in de Windows Store voor Bedrijven, beheren met Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

[Windows Store voor Bedrijven](https://www.microsoft.com/business-store) biedt een centrale locatie om apps te zoeken en aan te schaffen voor uw organisatie. U kunt zowel afzonderlijke exemplaren van een app als grotere volumes aanschaffen. Als u een koppeling tussen Windows Store en Microsoft Intune instelt, kunt u apps die in grotere volumes zijn aangeschaft, beheren vanuit de Intune-console. Bijvoorbeeld:
* U kunt de lijst met aangeschafte apps synchroniseren met Intune.
* Apps die zijn gesynchroniseerd, worden weergegeven in de Intune-beheerconsole en u kunt deze op dezelfde manier implementeren als andere apps.
* U kunt in de Intune-beheerconsole bijhouden hoeveel licenties er beschikbaar zijn en hoeveel licenties er worden gebruikt.
* Als er onvoldoende licenties beschikbaar zijn, worden de implementatie en installatie van apps geblokkeerd met Intune.

## <a name="before-you-start"></a>Voordat u begint
Lees de volgende informatie voordat u begint met het synchroniseren en implementeren van apps uit Windows Store voor Bedrijven:
* U moet Intune configureren als de Mobile Device Management-instantie voor uw organisatie. Zie [Prerequisites for enrolling devices in Microsoft Intune](prerequisites-for-enrollment.md) (Vereisten voor het inschrijven van apparaten in Microsoft Intune) voor meer informatie.
* U moet zich hebben geregistreerd voor een account in Windows Store voor Bedrijven.
* Hebt u eenmaal een Windows Store voor Bedrijven-account aan Intune gekoppeld, dan kunt u later niet meer overschakelen op een ander account.
* Apps die zijn aangeschaft in Windows Store, kunnen niet handmatig worden toegevoegd aan of verwijderd uit Intune. Ze kunnen alleen worden gesynchroniseerd met Windows Store voor Bedrijven.
* In Intune kunnen alleen online gelicentieerde apps worden gesynchroniseerd die u hebt aangeschaft in Windows Store voor Bedrijven.
* Apparaten moeten zijn gekoppeld aan Active Directory Domain Services of aan de werkplek zijn toegevoegd om deze mogelijkheid te kunnen gebruiken.
* Ingeschreven apparaten moeten gebruikmaken van de 1511-versie van Windows 10.

## <a name="associate-your-windows-store-for-business-account-with-intune"></a>Uw Windows Store voor Bedrijven-account koppelen aan Intune
Voordat u synchronisatie inschakelt in de Intune-console, moet u uw Store-account configureren om Intune te gebruiken als beheerprogramma:
1. Zorg ervoor dat u zich bij Windows Store voor Bedrijven aanmeldt met hetzelfde tenantaccount dat u gebruikt om u aan te melden bij Intune.
2. Kies in Windows Store voor Bedrijven **Instellingen** > **Beheerprogramma's**.
3. Kies op de pagina Beheerprogramma's de optie **Beheerprogramma toevoegen** en kies **Microsoft Intune**.

> [!NOTE]
> Als u meer dan één beheerhulpprogramma voor het implementeren van Windows Store voor Bedrijven-apps gebruikt, kon u voorheen slechts één van deze programma’s koppelen met de Windows Store voor Bedrijven. U kunt nu meerdere beheerhulpprogramma's met de Store koppelen, bijvoorbeeld Intune en Configuration Manager.

U kunt nu doorgaan en synchronisatie instellen in de Intune-console.

## <a name="configure-synchronization"></a>Synchronisatie configureren

1. Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) de optie **Beheer**.
2. Vouw in de werkruimte **Beheer** de optie **Mobile Device Management** > **Windows** uit en kies **Store voor Bedrijven**.
3. Voer op de pagina **Windows Store voor Bedrijven** de volgende handelingen uit:
 * Klik, als u dit nog niet hebt gedaan, op de koppeling om u te registreren bij Windows Store voor Bedrijven.
 * Wanneer u zich hebt geregistreerd, kiest u **Synchronisatie configureren**.
4. Selecteer in het dialoogvenster **Synchronisatie met de app Windows Store voor Bedrijven configureren** de optie **Synchronisatie met Windows Store voor Bedrijven inschakelen**.
5. Kies in de vervolgkeuzelijst **Taal** de taal waarin apps uit Windows Store voor Bedrijven moeten worden weergegeven in de Intune-console. Ongeacht de taal waarin deze apps worden weergegeven, worden ze geïnstalleerd in de taal van de eindgebruiker (indien beschikbaar).
6. Klik op **OK**.

## <a name="synchronize-apps"></a>Apps synchroniseren

1. Kies **Nu synchroniseren** op de pagina **Windows Store voor Bedrijven** om de apps te synchroniseren die u met Intune hebt aangeschaft in de Store.
2. Kies in de werkruimte **Apps** de optie **Apps** > **Apps die zijn gekocht via het volume-aankoopprogramma** om de apps te bekijken die u kunt implementeren en te controleren of uw aangeschafte apps juist zijn geïmporteerd. Bij de apps in dit knooppunt wordt weergegeven hoeveel licenties u in totaal bezit en hoeveel licenties er voor u beschikbaar zijn.
U kunt bijvoorbeeld de bedrijfsportal-app (met onlinelicentie) aanschaffen in de Windows Store voor Bedrijven, deze synchroniseren met de Intune-console en de app vervolgens als vereiste app implementeren op de vereiste Windows 10-apparaten. 


## <a name="deploy-apps"></a>Apps implementeren

U kunt apps uit de Store op dezelfde manier implementeren als elke andere Intune-app. Zie [Deploy apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md) (Apps implementeren in Microsoft Intune) voor meer informatie
Wanneer u een Windows Store voor Bedrijven-app implementeert, heeft elke gebruiker die de app installeert, hiervoor een licentie nodig. Als alle beschikbare licenties voor een geïmplementeerde app zijn gebruikt, kunt u geen exemplaren van de app meer implementeren. Voer een van de volgende acties uit:
* Verwijder de app van bepaalde apparaten.
* Beperk het bereik van de huidige implementatie tot het aantal gebruikers waarvoor u een licentie hebt.
* Koop meer exemplaren van de app in de Windows Store voor Bedrijven.

> [!Important]
> Geïmplementeerde apps zijn alleen beschikbaar voor de gebruiker die het apparaat oorspronkelijk heeft geregistreerd. Andere gebruikers kunnen de app niet gebruiken.


### <a name="see-also"></a>Zie tevens
[Apps voor mobiele apparaten toevoegen in Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md)

