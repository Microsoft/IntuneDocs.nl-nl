---
title: Uw gebruikers- en apparaatgroepen plannen
description: Plan groepen om aan de behoeften van uw organisatie te voldoen.
keywords: 
author: sanchusa
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f11bb256-1094-4f7e-b826-1314c57f3356
ms.reviewer: lpatha
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1362c42cb44848d5ab3a88d08b19d8f6aee195b9
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="plan-your-user-and-device-groups"></a>Uw gebruikers- en apparaatgroepen plannen

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Groepen in Intune bieden u een hoge mate van flexibiliteit wanneer u apparaten en gebruikers beheert. U kunt groepen instellen voor uw organisatiebehoeften op basis van:

- geografische locatie
- afdeling
- hardwarekenmerken
- besturingssysteem
- of het apparaat eigendom is van de gebruiker of van het bedrijf


## <a name="how-intune-groups-work"></a>De werking van de Intune-groepen


Dit is de standaardweergave van het knooppunt **Groepen** in de Intune-beheerconsole:

![Schermafdruk van de standaardweergave van het knooppunt Groepen in de Intune-beheerconsole](../media/Intune_Planning_Groups_Default_small.png)

Beleidsregels worden toegepast op groepen, waardoor de groepshiërarchie een van uw belangrijkste ontwerpoverwegingen is. Het is belangrijk om te weten dat wanneer u een groep hebt gemaakt, u de bovenliggende groep van die groep niet meer kunt wijzigen. Hoe u uw groepen ontwerpt, is van cruciaal belang vanaf het moment dat u de Intune-service in gebruik neemt. Hier worden enkele aanbevolen procedures beschreven voor het ontwerpen van een groepshiërarchie op basis van de behoeften van uw organisatie.

## <a name="group-membership-rules"></a>Lidmaatschapsregels

- Een groep kan gebruikers of apparaten bevatten, maar niet beide.

    * **Apparaatgroepen**. Deze groepen kunnen zowel computers als mobiele apparaten bevatten. Voordat u een computer aan een groep kunt toevoegen, moet deze worden ingeschreven. Voordat u een mobiel apparaat aan een groep kunt toevoegen, moet uw omgeving zodanig worden geconfigureerd dat het deze mobiele apparaten ondersteunt en moeten de apparaten worden ingeschreven of worden gedetecteerd in Exchange ActiveSync.

    * **Gebruikersgroepen**. Een groep kan gebruikers uit beveiligingsgroepen bevatten. Beveiligingsgroepen worden gesynchroniseerd met uw exemplaar van Active Directory. Als u niet synchroniseert met Active Directory, kunt u deze groepen handmatig maken.

- Een apparaat of een gebruiker kan tot meer dan één groep behoren.

- Een groep kan leden opnemen en uitsluiten op basis van de volgende lidmaatschapsregels:

    * **Lidmaatschapscriteria**. Dit zijn dynamische regels die door Intune worden uitgevoerd om leden op te nemen of uit te sluiten. Deze criteria maken gebruik van beveiligingsgroepen en andere informatie die wordt gesynchroniseerd met uw lokale exemplaar van Active Directory. Wanneer de beveiligingsgroep of de gegevens veranderen, verandert ook het groepslidmaatschap wanneer u met Active Directory synchroniseert.

    * **Direct lidmaatschap**. Dit zijn statische regels die expliciet leden toevoegen of uitsluiten. De lidmaatschapslijst is statisch.

-   Active Directory Domain Services (AD DS) is niet vereist wanneer u gebruikersgroepen of apparaatgroepen maakt die gebruikers of computers bevatten. Maar voor apparaatgroepen waarin u mobiele apparaten wilt opnemen, moet uw omgeving zo worden geconfigureerd dat deze mobiele apparaten ondersteunt.

    Bovendien moeten de apparaten worden gedetecteerd en toegevoegd aan Intune.

## <a name="group-relationship-rules"></a>Regels voor groepsrelaties

- Elke groep die u maakt, moet een bovenliggende groep hebben. Nadat u een groep hebt gemaakt, kunt u de bovenliggende groep van die groep niet meer wijzigen.

- Wanneer u gebruikers of apparaten aan een onderliggende groep toevoegt:

    * De onderliggende groep is altijd een subset van de bovenliggende groep.

    * Nieuwe leden die u aan een onderliggende groep toevoegt, worden automatisch aan de bovenliggende groep toegevoegd.

    * U kunt geen lid aan een onderliggende groep toevoegen wanneer dat lid is uitgesloten van de bovenliggende groep.

- Het lidmaatschap van een bovenliggende groep definieert het beschikbare lidmaatschap voor de onderliggende groep.

- Wanneer u een bovenliggende groep verwijdert, worden alle onderliggende groepen verwijderd.

- U kunt inhoud en beleidsregels in een bovenliggende groep implementeren, maar de implementatie in onderliggende groepen uitsluiten.

- U kunt een specifieke gebruiker of een specifiek apparaat toevoegen aan een onderliggende groep als de gebruiker of het apparaat nog geen lid is van de bovenliggende groep. Als u dit doet, wordt het nieuwe lid van de onderliggende groep toegevoegd aan de bovenliggende groep.

    U kunt echter geen lid toevoegen aan een onderliggende groep als dat lid is uitgesloten van de bovenliggende groep.

- Groepslidmaatschap is recursief. Bijvoorbeeld:

    * **Pat** is lid van slechts één groep, de beveiligingsgroep **Laptopgebruikers** .

    * De groep **Laptopgebruikers** is lid van de beveiligingsgroep **Goedgekeurde gebruikers** .

    * U maakt een groep in Intune die gebruikmaakt van een dynamische lidmaatschapsquery die de leden van de groep **Goedgekeurde gebruikers** omvat. Het resultaat is dat **Pat** in uw Intune-gebruikersgroep wordt opgenomen.

> [!TIP]
> Denk bij het maken van groepen goed na over hoe u beleid toepast. U kunt bijvoorbeeld beleidsregels gebruiken die specifiek zijn voor besturingssystemen van apparaten of beleidsregels die specifiek zijn voor verschillende rollen in uw organisatie die u al hebt gedefinieerd in uw Active Directory-service. Sommige beheerders vinden het handig om aparte apparaatgroepen te maken voor iOS, Android en Windows. Dit kunt u doen als aanvulling op het maken van gebruikersgroepen voor elke rol in de organisatie.

<!--- should we just link to a policies topic at this point and remove this? Ask Rob
 You'll probably want to create a default policy that applies to all groups and devices, to establish the basic compliance requirements of your organization. Then, you create more specific policies for the broadest categories of users and devices, for example, email policies for each of the device operating systems.

 Be careful when you name your policies, so that you can easily identify them later. For example, a good, descriptive policy name is **WP Email Policy for Entire Company**.

 Each time you create a restrictive policy, you'll want to communicate it to your users. After you create the more general groups and policies, pay attention to how you create smaller groups so that you can reduce unnecessary communication.--->

## <a name="built-in-groups"></a>Ingebouwde groepen
Intune heeft negen ingebouwde groepen, die u niet kunt bewerken of verwijderen: <!--maybe a screen shot would be best?-->

-   **Alle gebruikers**
    -   Niet-gegroepeerde gebruikers
-   **Alle apparaten**
    -   Alle computers
    -   Alle mobiele apparaten
        -   Alle rechtstreekse beheerde apparaten
        -   Alle door Exchange ActiveSync beheerde apparaten
    -   Alle apparaten in bedrijfseigendom
    -   Niet-gegroepeerde apparaten

> [!NOTE]
> Gebruik als motto: *houd het eenvoudig*. Als uw organisatie geen specifieke vereisten heeft, zoals de vereisten die in de volgende secties worden beschreven, houdt u het eenvoudig en gebruikt u de standaardgroepsstructuur en het standaardbeleid. Hierdoor is de service ook op de lange termijn beter te beheren. Onderhoud kan gemakkelijker worden uitgevoerd als u al uw gebruikers op dezelfde manier kunt behandelen. Als er maar weinig differentiatie is per groep, hoeft u minder beleidsregels te handhaven.


### <a name="all-users-and-devices-in-your-organization"></a>Alle gebruikers en apparaten in uw organisatie
Definieer een bovenliggende groep voor alle gebruikers en apparaten in uw organisatie. Waarschijnlijk hebt u beleidsregels die gelden voor alle gebruikers en apparaten. U kunt voor dit doel de standaardgroepen **Alle gebruikers** en **Alle apparaten** in Intune gebruiken. Subgroepen waarin apparaten zijn gerangschikt op specifieke kenmerken, zoals een groep voor BYOD-apparaten (Bring Your Own Device) en een groep voor apparaten die bedrijfseigendom zijn, kunnen onderliggende groepen zijn van de bovenliggende groepen **Alle gebruikers** en **Alle apparaten**.

## <a name="customize-groups-for-your-organization"></a>Groepen aanpassen voor uw organisatie

### <a name="byod-and-corporate-owned-devices"></a>BYOD-apparaten en apparaten die bedrijfseigendom zijn
Als uw organisatie werknemers de mogelijkheid biedt hun eigen apparaten op het werk te gebruiken (BYOD), als uw organisatie apparaten aanbiedt die bedrijfseigendom zijn of als in uw organisatie beide categorieën apparaten worden gebruikt, raden we u aan om afzonderlijke beleidsregels toe te passen voor deze categorieën apparaten.

Zorg dat u beleidsregels plant die de lokale privacyregelgeving niet schenden in het geval van BYOD of een combinatie van regels. Maak een bovenliggende groep voor alle gebruikers die hun eigen apparaten meebrengen. U kunt deze groep vervolgens gebruiken om beleidsregels toe te passen die gelden voor alle gebruikers in deze categorie.

![Een bovenliggende BYOD-groep maken](../media/Intune_Planning_Groups_BYOD_small.png)

Op dezelfde manier kunt u ook een groep maken voor gebruikers met een apparaat dat eigendom is van het bedrijf:

![Gebruikersgroepen voor BYOD-apparaten en apparaten van het bedrijf op hetzelfde niveau](../media/Intune_Planning_Groups_BYOD_Hierachy_View_small.png)

<!---START HERE--->

### <a name="groups-for-geographic-regions"></a>Groepen voor geografische regio 's
Als uw organisatie beleidsregels nodig heeft voor specifieke regio's, kunt u groepen maken op basis van geografische regio. U kunt deze groepen maken op basis van regionale groepen die u mogelijk al hebt gemaakt in uw exemplaar van Active Directory, en deze synchroniseren met uw Azure Active Directory-service. U kunt regionale groepen ook rechtstreeks in Azure Active Directory maken.

De volgende schermafbeeldingen laten zien hoe u Intune-groepen kunt maken op basis van groepen die zijn gesynchroniseerd met uw lokale Active Directory-exemplaar. In deze voorbeelden wordt ervan uitgegaan dat u een Active Directory-beveiligingsgroep hebt met de naam **US Users Group**.

Geef eerst algemene informatie op.

![Schermopname van het gebied Groep bewerken](../media/Intune_Planning_Groups_AD_General_small.png)

Selecteer onder **Lidmaatschapscriteria** de groep **US Users Group**, die is gesynchroniseerd met Active Directory, als de beveiligingsgroep die u wilt gebruiken onder lidmaatschapsregels.

![Schermafbeelding van het dialoogvenster Groep bewerken](../media/Intune_Planning_Groups_AD_Criteria_small.png)

Controleer de gegevens die u hebt ingevoerd en kies vervolgens **Voltooien** om de groep te maken.

![Schermafbeelding van het dialoogvenster Groep bewerken](../media/Intune_Planning_Groups_AD_Summary_small.png)

In dit voorbeeld hebben we ook een groep gemaakt met de naam **MEA** voor het Midden-Oosten en Azië.

> [!NOTE]
> Als het groepslidmaatschap niet is ingevuld op basis van het lidmaatschap van de beveiligingsgroep, controleert u of u Intune-licenties aan groepsleden hebt toegewezen.

### <a name="groups-for-specific-hardware"></a>Groepen voor specifieke hardware
Als in uw organisatie beleidsregels worden vereist die van toepassing zijn op specifieke hardwaretypen, kunt u groepen maken op basis van deze vereiste. U kunt de beleidsregels maken op basis van specifieke groepen die u al hebt gemaakt in uw exemplaar van Active Directory, en deze vervolgens synchroniseren met Azure Active Directory. U kunt ook rechtstreeks in Azure Active Directory groepen maken. In dit voorbeeld gebruiken we de groep **US Users Group** als de bovenliggende groep voor de groep **Laptop Users**.

![Dialoogvenster Beveiligingsgroep selecteren](../media/Intune_Planning_Groups_Laptop_small.png)

Op dit punt moet uw groepshiërarchie er ongeveer net zo uitzien als die in de volgende schermafbeelding. Zoals u ziet, zijn er nu leden aanwezig in de Intune-groep **Laptop Users**. Elke beleidsregel die wordt toegepast op deze groep, wordt toegepast op BYOD-laptopgebruikers uit de Verenigde Staten.

![Weergave van de groep Laptopgebruikers](../media/Intune_Planning_Groups_Laptop_Hierarchy_small.png)

### <a name="groups-for-specific-operating-systems"></a>Groepen voor specifieke besturingssystemen
Als in uw organisatie beleidsregels worden vereist die van toepassing zijn op bepaalde besturingssystemen, zoals Android, iOS of Windows, kunt u groepen maken op basis van deze vereiste. Net als in eerdere voorbeelden, kunt u groepen maken op basis van besturingssysteemspecifieke groepen die u al hebt gemaakt in uw on-premises exemplaar van Active Directory, en deze vervolgens synchroniseren met Azure Active Directory. U kunt deze groepen ook rechtstreeks in uw exemplaar van Azure Active Directory maken.

Met behulp van dezelfde methode die is gebruik in eerdere voorbeelden, kunt u groepen maken op basis van gebruikers <!--devices?--> die specifieke besturingssysteemplatforms gebruiken.

> [!NOTE]
> Als u gebruikers hebt die meerdere mobiele platforms of besturingssystemen gebruiken, en u deze gebruikers niet op een geautomatiseerde manier kunt categoriseren als Android-, iOS- of Windows-gebruikers, kunt u overwegen beleidsregels toe te passen op apparaatniveau. Dat geeft u meer flexibiliteit bij het toepassen van beleidsregels die specifiek zijn voor het besturingssysteem.
>
> U kunt groepen niet dynamisch inrichten op basis van het besturingssysteem van het apparaat. In plaats daarvan kunt dit doen met Active Directory- of Azure Active Directory-beveiligingsgroepen.

![Laptopgebruikersgroep](../media/Intune_Planning_Groups_OS_Hierachy_small.png)

Nadat al uw gebruikersgroepen zijn gevuld op basis van de vereisten van uw organisatie, moet uw hiërarchie er ongeveer als volgt uitzien:

![Weergave van groepshiërarchie](../media/Intune_Planning_Groups_Midpoint_Hierachy_small.png)

U kunt deze hiërarchie gebruiken om de beleidsregels van de organisatie toe te passen.

### <a name="device-groups"></a>Device groups
U kunt ook vergelijkbare groepen maken voor apparaten, zoals hier wordt weergegeven, beginnend met een grote groep met alle apparaten die eigendom zijn van werknemers, voor het BYOD-scenario.

![Dialoogvenster Groep maken](../media/Intune_Planning_Groups_Device_General_small.png)

Zorg ervoor dat u **Alle apparaten (computers en mobiele apparaten)** selecteert, zodat de groep alle BYOD-apparaten bevat:

![De pagina Lidmaatschapscriteria opgeven](../media/Intune_Planning_Groups_Device_Criteria_small.png)

Controleer de gegevens die u hebt ingevoerd en kies vervolgens **Voltooien** om de BYOD-groep te maken.

![Dialoogvenster Groep maken](../media/Intune_Planning_Groups_Device_Summary_small.png)

Ga door met het maken van apparaatgroepen totdat u een hiërarchie van apparaatgroepen hebt die vergelijkbaar is met de hiërarchie van gebruikersgroepen. Uw groepsknooppunt in de Intune-beheerconsole zal er nu ongeveer als volgt uitzien:

![Weergave Intune-groepshiërarchie](../media/Intune_Groups_Hierarchy_Final_Small.png)

## <a name="group-hierarchies-and-naming-conventions"></a>Groepshiërarchieën en naamgevingsregels
Om het beleidsbeheer te vereenvoudigen, wordt u aangeraden om de naam van elk beleid te baseren op het doel, het platform en de verzameling apparaten waarop u het beleid toepast. Gebruik een naamgevingsconventie die de groepsstructuur volgt die u hebt gemaakt toen u zich voorbereidde op de toepassing van uw beleidsregels.

Een Android-beleid dat wordt toegepast op alle zakelijke, mobiele Android-apparaten in de regio Verenigde Staten kunt u bijvoorbeeld de naam **CO_US_Mob_Android_General** geven.

![Beleid voor Android maken](../media/Intune_planning_policy_android_small.png)

Met deze naamgevingsconventie voor beleidsregels kunt u snel de gewenste beleidsregels vinden in het knooppunt **Beleidsregels** van de console en nagaan waar ze voor worden gebruikt en op welke verzameling apparaten ze worden toegepast, zoals hier wordt getoond:

![Lijst van Intune-beleidsregels](../media/Intune_planning_policy_view_small.png)

## <a name="next-steps"></a>Volgende stappen
[Groepen maken](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)
