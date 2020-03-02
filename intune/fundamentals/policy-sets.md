---
title: Beleidssets
titleSuffix: Microsoft Intune
description: Gebruik beleidssets om verzamelingen beheerobjecten te groeperen in Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: craigma
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 48bfe727615f5165fc70ed2e08f98f01203dc895
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514826"
---
# <a name="use-policy-sets-to-group-collections-of-management-objects"></a>Beleidssets gebruiken om verzamelingen beheerobjecten te groeperen

Met beleidssets kunt u een bundel verwijzingen maken naar reeds bestaande beheerentiteiten die moeten worden geïdentificeerd, gericht en bewaakt als één conceptuele eenheid. Een beleidsset is een toewijsbare verzameling apps, beleidsregels en andere beheerobjecten die u hebt gemaakt. Als u een beleidsset maakt, kunt u veel verschillende objecten tegelijk selecteren en deze toewijzen vanaf één locatie. Wanneer uw organisatie verandert, kunt u objecten en toewijzingen toevoegen aan of verwijderen uit uw beleidsset. U kunt een beleidsset gebruiken om bestaande objecten, zoals apps, beleidsregels en VPN's, in één pakket te koppelen en toe te wijzen. 

> [!IMPORTANT]
> Zie [Bekende problemen met beleidssets](~/fundamentals/policy-sets.md#policy-sets-known-issues) voor een lijst met bekende problemen met betrekking tot beleidssets.

Met beleidssets worden geen bestaande concepten of objecten vervangen. U kunt afzonderlijke objecten blijven toewijzen en u kunt ook verwijzen naar afzonderlijke objecten als onderdeel van een beleidsset. Daarom worden wijzigingen aan deze afzonderlijke objecten weergegeven in de beleidsset. 

U kunt beleidssets gebruiken voor het volgende:

- Objecten groeperen die samen moeten worden toegewezen
- De minimale configuratievereisten van uw organisatie toewijzen op alle beheerde apparaten
- Veelgebruikte of relevante apps toewijzen aan alle gebruikers

U kunt de volgende beheerobjecten insluiten in een beleidsset:
- Apps
- App-configuratiebeleid
- Beleid voor app-beveiliging
- Apparaatconfiguratieprofielen
- Nalevingsbeleid voor apparaten
- Beperkingen voor apparaattypen
- Implementatieprofielen voor Windows Autopilot
- Pagina Status van inschrijving

Wanneer u een beleidsset maakt, maakt u één toewijzingseenheid en beheert u koppelingen tussen verschillende objecten. Een beleidsset wordt een verwijzing naar externe objecten ervan. Eventuele wijzigingen in de opgenomen objecten zijn ook van invloed op de beleidsset. Nadat u een beleidsset hebt gemaakt, kunt u de objecten en toewijzingen ervan herhaaldelijk weergeven en bewerken. 

> [!NOTE]
> Beleidssets ondersteunen Windows-, Android-, macOS- en iOS/iPadOS-instellingen, en kunnen aan meerdere platforms worden toegewezen.

## <a name="how-to-create-a-policy-set"></a>Een beleidsset maken

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apparaten** > **Beleidssets** > **Beleidssets** > **Maken**.
3. Voeg op de pagina **Basisinformatie** de volgende waarden toe:
    - **Naam van beleidsset**: geef een naam voor deze beleidsset op.
    - **Beschrijving**: geef indien gewenst een beschrijving op voor de beleidsset.
   <p>
   <img alt="Create policy set - Basics" src="~/fundamentals/media/policy-sets/policy-sets-01.png">

4. Klik op **Volgende: toepassingsbeheer**.<br>
   Op de pagina **Toepassingsbeheer** kunt u desgewenst [apps](~/apps/apps-add.md), [app-configuratiebeleid](~/apps/app-configuration-policies-overview.md) en [app-beveiligingsbeleid](~/apps/app-protection-policy.md) aan uw beleidsset toevoegen. Zie [Wat is Microsoft Intune-appbeheer?](~/apps/app-management.md) voor meer informatie over het beheren van apps in Intune. 
5. Klik op **Volgende: apparaatbeheer**.<br>
   Op de pagina **Apparaatbeheer** kunt u apparaatbeheerobjecten toevoegen aan uw beleidsset, zoals [apparaatconfiguratieprofielen](~/configuration/device-profiles.md) en [nalevingsbeleid voor apparaten](~/protect/device-compliance-get-started.md). Zorg ervoor dat u alle gekoppelde objecten opneemt, zoals andere beleidsregels, certificaten en profielen voor beveiligingsbasislijnprofielen.
6. Klik op **Volgende: apparaatinschrijving**.<br>
   Op de pagina **Apparaatinschrijving** kunt u inschrijvingsobjecten voor apparaten toevoegen aan uw beleidsset, zoals [beperkingen voor apparaattypen](~/enrollment/enrollment-restrictions-set.md), [implementatieprofielen voor Windows Autopilot](~/enrollment/enrollment-autopilot.md) en [profielen voor inschrijvingsstatuspagina](~/enrollment/windows-enrollment-status.md).
7. Klik op **Volgende: toewijzingen**.<br>
   Op de pagina **Toewijzingen** kunt u de beleidsinstelling toewijzen aan gebruikers en apparaten. Het is belangrijk dat u weet dat u een app kunt toewijzen aan een apparaat, ongeacht of het apparaat wordt beheerd in Intune.
8. Klik op **Volgende: beoordelen en maken** om de waarden te controleren die u hebt ingevoerd voor het profiel.
9. Wanneer u klaar bent, klikt u op **Maken** om de beleidsset in Intune te maken. 

## <a name="policy-sets-known-issues"></a>Bekende problemen met beleidssets

Voor beleidssets, nieuw voor 1910, zijn de volgende problemen bekend.

- Wanneer u een beleidsset maakt en een beheerder met bereik probeert een beleidsset te maken zonder dat er bereiktags zijn geselecteerd, mislukt de validatie bij het bereiken van de pagina **Beoordelen en maken** en wordt er een fout weergegeven op de statusbalk. De beheerder moet schakelen naar een andere pagina in het proces en vervolgens terugkeren naar de pagina **Beoordelen en maken**. Hierdoor wordt de optie **Maken** ingeschakeld.  
 
- De volgende app-typen worden momenteel ondersteund door beleidssets:
    - iOS/iPadOS Store-app
    - Line-Of-Business-app voor iOS/iPadOS
    - Beheerde Line-Of-Business-app voor iOS/iPadOS
    - Android Store-app
    - Line-Of-Business-app voor Android
    - Beheerde Line-Of-Business-app voor Android
    - Office 365 ProPlus-suite (Windows 10)
    - Webkoppeling
    - Ingebouwde iOS/iPadOS-app
    - Ingebouwde Android-app

- Het instellen van een beleidssettoewijzing van **Alle gebruikers** op **Autopilot-profiel** wordt niet ondersteund.

- Beleidssets hebben de volgende inschrijvingsbeperkingen en problemen met de pagina Inschrijvingsstatus:
    - Beperkingen en de pagina Inschrijvingsstatus bieden geen ondersteuning voor virtuele groepstoewijzingen.
    - Beperkingen en de pagina Inschrijvingsstatus bieden geen strikte ondersteuning voor toewijzingen van uitsluitingsgroepen. 
    - Beperkingen en de pagina Inschrijvingssstatus maken gebruik van conflictoplossing op basis van prioriteit. Beperkingen en de pagina Inschrijvingsstatus worden mogelijk niet toegepast op dezelfde gebruikers als de rest van de payloads van een beleidsset als de beperkingen en de pagina Inschrijvingsstatus ook doel zijn van restricties met een hogere prioriteit en de pagina Inschrijvingsstatus.
    - De standaardbeperkingen en de pagina Inschrijvingsstatus kunnen niet worden toegevoegd aan een beleidsset.

- MAM-beleidstypen die beleidssets ondersteunen, zijn onder meer: 
    - MAM WIP (Windows) MDM-gerichte beheerde app-beveiliging 
    - MAM iOS/iPadOS-gerichte beheerde app-beveiliging
    - MAM Android-gerichte beheerde app-beveiliging
    - MAM iOS/iPadOS-gerichte beheerde app-configuratie
    - MAM Android-gerichte beheerde app-configuratie

- MAM-beleidstypen die geen beleidssets ondersteunen zijn onder meer: 
    - MAM WIP (Windows)-gerichte beheerde app-beveiliging

- In MAM worden beleidssettoewijzingen verwerkt als rechtstreekse toewijzingen voor de volgende beleidstypen:
    - MAM iOS/iPadOS-gerichte beheerde app-beveiliging
    - MAM Android-gerichte beheerde app-beveiliging
    - MAM iOS/iPadOS-gerichte beheerde app-configuratie
    - MAM Android-gerichte beheerde app-configuratie

    Als een beleidsregel wordt toegevoegd aan een beleidsset die is geïmplementeerd voor een groep, wordt de groep weergegeven als rechtstreeks in de workload toegewezen, niet als 'toegewezen via de beleidsset'. Als gevolg hiervan worden in MAM geen verwijderingen verwerkt van groepstoewijzingen die afkomstig zijn uit beleidssets.

- MAM biedt geen ondersteuning voor implementatie in de virtuele groepen **Alle gebruikers** en **Alle apparaten**. Dit geldt voor alle beleidstypen.

## <a name="next-steps"></a>Volgende stappen

- [Apparaten registreren in Microsoft Intune](~/enrollment/index.yml).