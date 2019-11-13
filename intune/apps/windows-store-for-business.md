---
title: VPP-apps beheren via Microsoft Store voor Bedrijven
titleSuffix: Microsoft Intune
description: Meer informatie over hoe u apps synchroniseert in Intune vanuit de Microsoft Store voor Bedrijven.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/06/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2ed5d3f0-2749-45cd-b6bf-fd8c7c08bc1b
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, seoapril2019
ms.collection: M365-identity-device-management
ms.openlocfilehash: 04bc1fac8d3362a173c4777cdf5228fed6b6349d
ms.sourcegitcommit: 28622c5455adfbce25a404de4d0437fa2b5370be
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2019
ms.locfileid: "73712543"
---
# <a name="how-to-manage-volume-purchased-apps-from-the-microsoft-store-for-business-with-microsoft-intune"></a>In volume aangeschafte apps beheren vanuit de Microsoft Store voor Bedrijven met Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

[Microsoft Store voor Bedrijven](https://www.microsoft.com/business-store) biedt een centrale locatie om apps te zoeken en aan te schaffen voor uw organisatie. U kunt zowel afzonderlijke exemplaren van een app als grotere volumes aanschaffen. Als u Windows Store voor Bedrijven aan Microsoft Intune koppelt, kunt u apps die zijn aangeschaft via een volume-aankoopprogramma, beheren in de Azure-portal. Bijvoorbeeld:
* U kunt de lijst met apps die u hebt aangeschaft (of die gratis zijn) vanuit de Store synchroniseren met Intune.
* Apps die zijn gesynchroniseerd, worden weergegeven in de Intune-beheerconsole en u kunt deze apps op dezelfde manier toewijzen als andere apps.
* Zowel online als offline gelicentieerde versies van apps worden gesynchroniseerd met Intune. Aan app-namen wordt 'Online' of 'Offline' toegevoegd in de portal.
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
1. Zorg ervoor dat u zich bij [Microsoft Store voor Bedrijven](https://www.microsoft.com/business-store) aanmeldt met hetzelfde tenantaccount dat u gebruikt om u aan te melden bij Intune.
2. Kies in de Store voor Bedrijven het tabblad **Beheren**, selecteer **Instellingen**, en kies het tabblad **Verdelen**.
3. Als u **Microsoft Intune** niet specifiek beschikbaar hebt als een hulpprogramma voor het beheer van mobiele apparaten, kiest u **Beheerprogramma toevoegen** om **Microsoft Intune** toe te voegen. Als u **Microsoft Intune** niet hebt geactiveerd als uw beheerprogramma voor mobiele apparaten, klikt u op **Activeren** naast **Microsoft Intune**. Let op: u moet **Microsoft Intune** in plaats van **Microsoft Intune-inschrijving** activeren.

> [!NOTE]
> Eerder kon u maar één beheerhulpprogramma koppelen om apps toe te wijzen via Microsoft Store voor Bedrijven. U kunt nu meerdere beheerhulpprogramma's met de Store koppelen, bijvoorbeeld Intune en Configuration Manager. 

U kunt nu doorgaan en synchronisatie instellen in de Intune-console.

## <a name="configure-synchronization"></a>Synchronisatie configureren

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Kies in het deelvenster **Intune** de optie **Client-apps**.
1. Kies in het deelvenster **Client-apps** de optie **Instellen** > **Microsoft Store voor Bedrijven**.
2. Klik op **Inschakelen**.
3. Klik, als u dit nog niet hebt gedaan, op de koppeling om u te registreren bij Microsoft Store voor Bedrijven en uw account te koppelen zoals eerder is beschreven.
5. Kies in de vervolgkeuzelijst **Taal** de taal waarin apps uit Microsoft Store voor Bedrijven moeten worden weergegeven in Azure Portal. Ongeacht de taal waarin deze apps worden weergegeven, worden ze geïnstalleerd in de taal van de eindgebruiker (indien beschikbaar).
6. Klik op **Synchroniseren** om de apps die u hebt aangeschaft in Microsoft Store, op te halen in Intune.

## <a name="synchronize-apps"></a>Apps synchroniseren

1. Kies in de workload **Client-apps** de optie **Instellen** > **Microsoft Store voor Bedrijven**.
2. Klik op **Synchroniseren** om de apps die u hebt aangeschaft in Microsoft Store, op te halen in Intune.

> [!NOTE]
> Apps met versleutelde app-pakketten worden momenteel niet ondersteund en worden niet gesynchroniseerd met Intune.

## <a name="assign-apps"></a>Apps toewijzen

U kunt apps uit de store op dezelfde manier toewijzen als elke andere Intune-app. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor meer informatie. 

Offline-apps kunnen worden gericht op gebruikersgroepen, apparaatgroepen of groepen met gebruikers en apparaten.
Offline-apps kunnen worden geïnstalleerd voor een specifieke gebruiker op een apparaat of voor alle gebruikers op een apparaat. 


Wanneer u een Microsoft Store voor Bedrijven-app toewijst, heeft elke gebruiker die de app installeert hiervoor een licentie nodig. Als alle beschikbare licenties voor een toegewezen app zijn gebruikt, kunt u geen exemplaren van de app meer toewijzen. Ga in dat geval op een van de volgende manieren te werk:
* Verwijder de app van bepaalde apparaten.
* Beperk het bereik van de huidige toewijzing tot het aantal gebruikers waarvoor u een licentie hebt.
* Koop meer exemplaren van de app in Microsoft Store voor Bedrijven.

## <a name="remove-apps"></a>Apps verwijderen

Als u een app wilt verwijderen die is gesynchroniseerd vanuit Microsoft Store voor Bedrijven, moet u zich aanmelden bij Microsoft Store voor Bedrijven en de app terugbetalen. Het proces is hetzelfde, ongeacht of de app wel of niet gratis is. Voor een gratis app geeft de Store een restitutie van $ 0. In het volgende voorbeeld wordt een restitutie voor een gratis app weergegeven. 

![Schermafbeelding van de details over app-verwijdering](./media/windows-store-for-business/microsoft-store-for-business-01.png)

> [!NOTE]
> Als u de zichtbaarheid van de app in de privéstore verwijdert, zorgt dit er niet voor dat Intune stopt met synchroniseren van de app. U moet de app restitueren om de app volledig te verwijderen.

## <a name="next-steps"></a>Volgende stappen

- [Apps en boeken met Microsoft Intune beheren die via het Volume Purchase Program zijn gekocht](../vpp-apps.md)
