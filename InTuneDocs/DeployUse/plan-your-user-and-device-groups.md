---
title: Uw gebruikers- en apparaatgroepen plannen| Microsoft Intune
description: 
keywords: 
author: nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f11bb256-1094-4f7e-b826-1314c57f3356
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 82ab2dbfada6c0745195da149d5f0dc1948ceb92
ms.openlocfilehash: e89d8384532b994d810649fc07c698237e2f3cec


---

# Uw gebruikers- en apparaatgroepen plannen
Groepen in Intune bieden u een hoge mate van flexibiliteit voor het beheren van uw apparaten en gebruikers. U kunt groepen instellen voor uw organisatiebehoeften op basis van:

- geografische locatie
- afdeling
- hardwarekenmerken
- besturingssysteem
- of het apparaat eigendom is van de gebruiker of van het bedrijf


## De werking van de Intune-groepen


De standaardweergave van het knooppunt groepen in de Intune-beheerconsole is:

![Schermafdruk van de standaardweergave van het knooppunt Groepen in de Intune-beheerconsole](/intune/media/Intune_Planning_Groups_Default_small.png)

Beleidsregels worden toegepast op groepen, waardoor groepshiërarchie een van uw belangrijkste ontwerpoverwegingen is. Het is ook belangrijk te weten dat de bovenliggende groep niet kan worden gewijzigd nadat de groep is gemaakt. Het ontwerp van de groepen is dus zeer belangrijk vanaf het moment dat u begint met de Intune-service. Sommige van de aanbevolen procedures voor het ontwerpen van een groepshiërarchie op basis van de behoeften van uw organisatie worden hier beschreven.

## Lidmaatschapsregels

1. Een groep kan gebruikers of apparaten bevatten, maar niet beide.

    * **Apparaatgroepen:** deze omvatten zowel computers als mobiele apparaten. Voordat u een computer aan een groep kunt toevoegen, moet deze worden ingeschreven. Voordat u een mobiel apparaat aan een groep kunt toevoegen, moet uw omgeving worden geconfigureerd voor ondersteuning van mobiele apparaten en moeten de apparaten worden ingeschreven of worden gedetecteerd door Exchange ActiveSync.

    * **Gebruikersgroepen:** een groep kan gebruikers bevatten uit beveiligingsgroepen. Dit zijn groepen die worden gesynchroniseerd vanuit Active Directory. Als u geen synchronisatie vanuit Active Directory gebruikt, kunt u deze groepen handmatig maken.

2. Een apparaat of een gebruiker kan tot meer dan één groep behoren.

3. Een groep kan leden opnemen en uitsluiten op basis van de volgende lidmaatschapsregels:

    * **Lidmaatschapscriteria:** dit zijn dynamische regels die door Intune worden uitgevoerd om leden op te nemen of uit te sluiten. Deze criteria maken gebruik van **beveiligingsgroepen** en andere informatie die wordt gesynchroniseerd vanuit uw lokale Active Directory (AD). Wanneer de beveiligingsgroep of de gegevens wijzigen, wijzigt ook het groepslidmaatschap wanneer u met AD synchroniseert.

    * **Direct lidmaatschap:** dit zijn statische regels waarmee leden expliciet worden toegevoegd of uitgesloten. De lidmaatschapslijst is statisch.

4. Active Directory Domain Services (AD DS) is niet vereist voor het maken van gebruikers- of apparaatgroepen die gebruikers of computers bevatten, maar als u wilt dat apparaatgroepen mobiele apparaten bevatten, moet uw omgeving worden geconfigureerd voor ondersteuning van mobiele apparaten.

    Bovendien moeten de apparaten worden gedetecteerd en toegevoegd aan Intune.

## Regels voor groepsrelaties

1. Elke groep die u maakt, moet een bovenliggende groep hebben en u kunt de bovenliggende groep niet wijzigen nadat de groep is gemaakt.

2. Wanneer u gebruikers of apparaten aan een onderliggende groep toevoegt:

    * Onderliggende groepen zijn altijd subsets van de bovenliggende groep.

    * Nieuwe leden die u aan een onderliggende groep toevoegt, worden automatisch aan de bovenliggende groep toegevoegd.

    * U kunt geen lid aan een onderliggende groep toevoegen wanneer dat lid is uitgesloten van de bovenliggende groep.

3. Het lidmaatschap van een bovenliggende groep definieert het beschikbare lidmaatschap voor de onderliggende groep.

4. Wanneer u een bovenliggende groep verwijdert, worden alle onderliggende groepen verwijderd.

5. U kunt inhoud en beleidsregels op een bovenliggende groep implementeren terwijl u implementatie op onderliggende groepen uitsluit.

6. U kunt een specifieke gebruiker of een specifiek apparaat toevoegen aan een onderliggende groep die geen lid is van de bovenliggende groep. Als u dit doet, wordt het nieuwe groepslid toegevoegd aan de bovenliggende groep.

    U kunt echter geen lid toevoegen aan een onderliggende groep die is uitgesloten van de bovenliggende groep.

7. Groepslidmaatschap is recursief. Bijvoorbeeld:

    * **Pat** is lid van slechts één groep, de beveiligingsgroep **Laptopgebruikers** .

    * De groep **Laptopgebruikers** is lid van de beveiligingsgroep **Goedgekeurde gebruikers** .

    * U maakt een groep in Intune die gebruikmaakt van een dynamische lidmaatschapsquery die de leden van de groep **Goedgekeurde gebruikers** omvat. Het resultaat is dat **Pat** in uw Intune-gebruikersgroep wordt opgenomen.

> [!TIP]
> Als u uw groepen maakt, denk dan na over hoe u het beleid toepast. Wellicht hebt u beleidsregels die specifiek zijn voor besturingssystemen van apparaten en beleidsregels die specifiek zijn voor verschillende rollen in uw organisatie of organisatie-eenheden die u al hebt gedefinieerd in Active Directory. Voor sommigen is het nuttig om specifieke apparaatgroepen voor iOS, Android en Windows en gebruikersgroepen voor elke organisatierol te hebben.

<!--- should we just link to a policies topic at this point and remove this? Ask Rob
 You'll probably want to create a default policy that applies to all groups and devices, to establish the basic compliance requirements of your company. Then create more specific policies for the broadest categories of users and devices, for example, email policies for each of the device operating systems.

 Be careful naming your policies so that you can easily identify them later. For example, a good, descriptive policy name is **WP Email Policy for Entire Company**.

 Each time you create a restrictive policy you'll want to communicate it to your users, so after you create the more general groups and policies pay attention to how you create smaller groups so that you can reduce unnecessary communication.--->

## Ingebouwde groepen
Intune biedt negen ingebouwde groepen die u niet kunt bewerken of verwijderen: <!--maybe a screen shot would be best?-->

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
> Gebruik als motto: *houd het eenvoudig*. Als uw organisatie geen specifieke vereisten heeft, zoals die hieronder worden beschreven, moet u deze eenvoudig houden en gebruikt u de standaardgroepsstructuur en het standaardbeleid om de service op de lange termijn beter beheerbaar te houden. Onderhoud wordt gemakkelijker als u uw gebruikers als groep op dezelfde wijze kunt behandelen, met kleine verschillen. Hierdoor hoeft u minder beleidsregels te onderhouden.


### Alle gebruikers en apparaten in uw organisatie
Definieer een bovenliggende groep voor alle gebruikers en apparaten in uw organisatie, omdat er waarschijnlijk beleidsregels zullen zijn die van toepassing zijn op alle gebruikers en apparaten. Hiervoor kunt u de standaardgroepen **Alle gebruikers** en **Alle apparaten** in Intune gebruiken. Subgroepen waarin apparaten zijn gerangschikt op specifieke kenmerken, zoals een groep voor BYOD (Bring Your Own Device) en een groep voor apparaten die bedrijfseigendom zijn, kunnen onderliggende groepen zijn van de bovenliggende groepen **Alle gebruikers** en **Alle apparaten**.

## Groepen aanpassen voor uw organisatie

### BYOD-apparaten en apparaten die bedrijfseigendom zijn
Als uw organisatie de mogelijkheid biedt dat werknemers hun eigen apparaten op het werk gebruiken (BYOD), als uw organisatie apparaten aanbiedt die bedrijfseigendom zijn, of als uw organisatie een combinatie van beide beleidsregels gebruikt, raden we aan dat u beleidsregels toepast op basis van deze twee categorieën apparaten.

Zorg dat u beleidsregels plant die de lokale privacyregelgeving niet schenden in het geval van BYOD of een combinatie van regels. Maak een bovenliggende groep voor alle gebruikers die hun eigen apparaten meebrengen. Deze groep kan vervolgens worden gebruikt om beleidsregels toe te passen die gelden voor alle gebruikers in deze categorie.

![Schermafdruk van het maken van een bovenliggende BYOD-groep](/intune/media/Intune_Planning_Groups_BYOD_small.png)

Op deze manier kunt u een groep maken voor de gebruikers met een apparaat van het bedrijf:

![Schermafdruk van de gebruikersgroepen op hetzelfde niveau voor BYOD-apparaten en apparaten van het bedrijf](/intune/media/Intune_Planning_Groups_BYOD_Hierachy_View_small.png)

<!---START HERE--->

### Groepen voor geografische regio 's
Als uw organisatie beleid nodig heeft voor specifieke regio's, kunt u groepen maken op basis van een geografische regio. U kunt deze baseren op regionale groepen die u mogelijk al hebt gemaakt in Active Directory (AD), en deze kunt u synchroniseren met Azure AD. U kunt ze ook rechtstreeks in Azure AD maken.

Op deze schermafdrukken ziet u hoe u Intune-groepen maakt op basis van groepen die zijn gesynchroniseerd vanuit uw lokale AD. In het volgende voorbeeld wordt ervan uitgegaan dat u een AD-beveiligingsgroep hebt met de naam **US Users Group**.

1. Geef eerst algemene informatie op.

![Schermopname van het gebied Groep bewerken](/intune/media/Intune_Planning_Groups_AD_General_small.png)

Selecteer onder Lidmaatschapscriteria **US Users Group**, gesynchroniseerd uit Active Directory als de beveiligingsgroep die u wilt gebruiken onder Lidmaatschapsregels.

![Dialoogvenster Groep bewerken](/intune/media/Intune_Planning_Groups_AD_Criteria_small.png)

Controleer en kies vervolgens **Voltooien** om het maken van de groep te voltooien.

![Dialoogvenster Groep bewerken](/intune/media/Intune_Planning_Groups_AD_Summary_small.png)

In ons voorbeeld hebben we ook een groep gemaakt voor het Midden-Oosten en Azië (MEA).

> [!NOTE]
> Als het groepslidmaatschap niet is ingevuld op basis van het lidmaatschap van de beveiligingsgroep, controleert u of u Intune-licenties aan die leden hebt toegewezen.

### Groepen voor specifieke hardware
Als in uw organisatie beleidsregels worden vereist die van toepassing zijn op specifieke hardwaretypen, kunt u groepen maken op basis van deze vereiste. U kunt deze baseren op specifieke groepen die u al hebt gemaakt in uw lokale AD en deze naar Azure AD synchroniseren. U kunt ze ook rechtstreeks in Azure AD maken. In dit voorbeeld gebruiken we de groep **US Users Group** als het bovenliggende item voor de groep **Laptopgebruikers**.

![Dialoogvenster Beveiligingsgroep selecteren](/intune/media/Intune_Planning_Groups_Laptop_small.png)

De hiërarchie van groepen moet er op dit moment uitzien zoals hieronder is weergegeven. Zoals u ziet, zijn er nu leden binnen de Intune-groep **Laptopgebruikers**. Elk beleid dat wordt toegepast op deze groep wordt nu ook toegepast op BYOD-laptopgebruikers uit de Verenigde Staten.

![Weergave van de groep Laptopgebruikers](/intune/media/Intune_Planning_Groups_Laptop_Hierarchy_small.png)

### Groepen voor specifieke besturingssystemen
Als in uw organisatie beleidsregels worden vereist die van toepassing zijn op bepaalde besturingssystemen, zoals Android, iOS of Windows, kunt u groepen maken op basis van deze vereiste. Net zoals in de vorige voorbeelden kunt u deze baseren op specifieke groepen die u al hebt gemaakt in uw lokale AD en deze naar Azure AD synchroniseren. U kunt ze ook rechtstreeks in Azure AD maken.

Het volgen van dezelfde methode van de eerdere voorbeelden, maken we weergegeven op basis van gebruikers <!--devices?--> met specifieke besturingssysteem-platforms.

> [!NOTE]
> Als u gebruikers hebt met meerdere mobiele platforms of besturingssystemen en u geen automatische manier hebt om gebruikers te categoriseren als gebruikers met Android, iOS of Windows, overweeg dan beleidsregels toe te passen op apparaatniveau. Hiermee hebt u meer flexibiliteit bij het toepassen van beleid dat specifiek is voor het besturingssysteem.
>
> U kunt groepen dynamisch inrichten op basis van het besturingssysteem van het apparaat. Doe dit met AD- of AAD-beveiligingsgroepen.

![Weergave van de groep Laptopgebruikers](/intune/media/Intune_Planning_Groups_OS_Hierachy_small.png)

Als alle gebruikersgroepen zijn ingevuld op basis van deze vereisten van de organisatie, moet uw hiërarchie er als volgt uitzien:

![Weergave groepshiërarchie](/intune/media/Intune_Planning_Groups_Midpoint_Hierachy_small.png)

Met deze hiërarchie kunt u de beleidsregels van de organisatie op de juiste wijze toepassen.

### Device groups
U kunt ook vergelijkbare groepen maken voor apparaten zoals hieronder weergegeven, beginnend met een grote groep met alle apparaten die eigendom zijn van werknemers, voor het BYOD-scenario:

![Dialoogvenster Groep maken](/intune/media/Intune_Planning_Groups_Device_General_small.png)

Zorg ervoor dat u **Alle apparaten (computers en mobiele)** selecteert, zodat de groep alle BYO-apparaten bevat:

![De pagina Lidmaatschapscriteria opgeven](/intune/media/Intune_Planning_Groups_Device_Criteria_small.png)

Bekijk en kies **Voltooien** om de BYOD-groep te maken.

![Dialoogvenster Groep maken](/intune/media/Intune_Planning_Groups_Device_Summary_small.png)

Ga door met het maken van apparaatgroepen totdat u een hiërarchie van apparaatgroepen hebt die vergelijkbaar is met de hiërarchie van gebruikersgroepen. Vervolgens ziet uw groepsknooppunt in de Intune-beheerconsole er ongeveer als volgt uit:

![Weergave Intune-groepshiërarchie](/intune/media/Intune_Groups_Hierarchy_Final_Small.png)

## Groepshiërarchieën en naamgevingsregels
Voor een eenvoudiger beheer, wordt u aangeraden de naam van elk beleid te baseren op het doel, het platform en de omvang waarop het beleid wordt toegepast. Deze naamgevingsnorm moet de groepsstructuur volgen die u hebt gemaakt als voorbereiding op het toepassen van uw beleid.

Een Android-beleid dat wordt toegepast op alle zakelijke, mobiele Android-apparaten in de VS kan bijvoorbeeld de naam **CO_US_Mob_Android_General** krijgen.

![Beleid voor Android maken](/intune/media/Intune_planning_policy_android_small.png)

Met deze methode van naamgeving voor beleidsregels kunt u snel beleidsregels en hun bedoelde gebruik en omvang vinden in het beleidsknooppunt van de console. Zie de afbeelding:

![Lijst van Intune-beleidsregels](/intune/media/Intune_planning_policy_view_small.png)

## Volgende stappen
[Groepen maken](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)



<!--HONumber=Jun16_HO4-->


