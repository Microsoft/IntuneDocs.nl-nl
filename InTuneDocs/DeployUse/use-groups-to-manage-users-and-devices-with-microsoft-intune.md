---
title: Groepen gebruiken om gebruikers en apparaten te beheren | Microsoft Intune
description: Groepen maken en beheren met behulp van de werkruimte Groepen.
keywords: 
author: Nbigman
manager: angrobe
ms.date: 06/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb9b01ce-9b9b-4c2a-bf99-3879c0bdaba5
ms.reviewer: lpatha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 300df17fd5844589a1e81552d2d590aee5615897
ms.openlocfilehash: 53a7bda5dd5adcac512c413c7069723ae638f279


---

# Groepen maken om gebruikers en apparaten te beheren met Microsoft Intune

Voor het maken en beheren van groepen gebruikt u de werkruimte **Groepen** in de Microsoft Intune-beheerconsole. De pagina **Overzicht van groepen** bevat statusoverzichten die u helpen bij het identificeren en prioriteren van problemen die uw aandacht nodig hebben voor:

-   Waarschuwingen
-   Software-updates
-   Endpoint Protection
-   Beleid
-   Softwarebeheer

Daarnaast wordt uw groepshiërarchie weergegeven met statusoverzichten om u te helpen bij het identificeren en oplossen van problemen voor leden van een geselecteerde groep.


> [!TIP]
> Als u uw groepen maakt, denk dan na over hoe u het beleid toepast. Wellicht hebt u beleidsregels die specifiek zijn voor besturingssystemen van apparaten en beleidsregels die specifiek zijn voor verschillende rollen in uw organisatie of organisatie-eenheden die u al hebt gedefinieerd in Active Directory. Voor sommigen is het nuttig om specifieke apparaatgroepen voor iOS, Android en Windows en gebruikersgroepen voor elke organisatierol te hebben.
>
> U wilt waarschijnlijk een standaardbeleid maken dat van toepassing is op alle groepen en apparaten, om de basisvereisten voor naleving binnen uw bedrijf vast te leggen. Vervolgens maakt u specifieker beleid voor de breedste categorieën gebruikers en apparaten, bijvoorbeeld een e-mailbeleid voor elk apparaatbesturingssysteem.
>
> Kies de naam voor elk beleid zorgvuldig, zodat u deze later eenvoudig kunt herkennen. Een goede beschrijvende naam is bijvoorbeeld **WP-e-mailbeleid voor het hele bedrijf**.
>
> U wilt waarschijnlijk elk nieuw beleid aan uw gebruikers communiceren. Besteed daarom na het maken van algemene groepen extra aandacht aan hoe u kleinere groepen indeelt, om de communicatie te beperken.


## Een apparaatgroep maken

1.  Kies in de Intune-beheerconsole **Groepen** &gt; **Overzicht** &gt; **Groep maken**.

2.  Geef een naam en een optionele beschrijving voor de groep op en selecteer een apparaatgroep als de bovenliggende groep. Kies **Volgende**.

3.  Op de pagina **Lidmaatschapscriteria definiëren** selecteert u het type apparaten dat de groep zal bevatten. Aanvullende opties voor het configureren van de groep zijn afhankelijk van het type apparaten dat u selecteert:

    -   **Computer:** geef op of u alle leden van de bovenliggende groep wilt opnemen, welke organisatie-eenheden (OE) u wilt opnemen of uitsluiten, en welke domeinen u wilt opnemen of uitsluiten. De informatie over OE en domein voor een computer wordt opgehaald uit de inventaris.

    -   **Mobiel:** geef op of u alleen mobiele apparaten wilt opnemen die worden beheerd door Intune, die worden beheerd door Exchange ActiveSync of door beide.

    -   **Alle apparaten:** deze optie omvat alle apparaten zonder uitsluitingen op basis van criteria.

4.  Op de pagina **Direct lidmaatschap definiëren** kunt u afzonderlijke apparaten opnemen of uitsluiten die u opgeeft door te klikken op **Bladeren**. Als u de optie gebruikt om apparaten te selecteren die zich niet in de door u opgegeven bovenliggende groep bevinden, worden die apparaten automatisch toegevoegd aan de bovenliggende groep.


5.  Bekijk op de pagina **Overzicht** de acties die zullen worden uitgevoerd. Kies **Voltooien**.

U vindt de zojuist gemaakte groep in de lijst **Groepen**, in de werkruimte **Groepen**, onder de bovenliggende groep. Hier kunt u de groep ook bewerken of verwijderen.

## Een gebruikersgroep maken

1.  Kies in de Intune-beheerconsole **Groepen** &gt; **Overzicht** &gt; **Groep maken**.

2.  Geef een naam en een optionele beschrijving voor de groep op en selecteer een gebruikersgroep als de bovenliggende groep. Kies **Volgende**.

3.  Geef op de pagina **Lidmaatschapscriteria definiëren** op of u alle leden van de bovenliggende groep wilt opnemen of dat u met een lege groep wilt beginnen.  U kunt vervolgens leden opnemen of uitsluiten op basis van de **beveiligingsgroepen** van gebruikers die u handmatig configureert in het [Office 365-beheercentrum](http://go.microsoft.com/fwlink/?LinkId=698854) of die worden gesynchroniseerd vanuit uw lokale Active Directory. Als het lidmaatschap van een beveiligingsgroep verandert, kan het lidmaatschap van gebruikersgroepen die zijn gebaseerd op die beveiligingsgroep, ook veranderen.

    > [!IMPORTANT]
    > Als uw groep momenteel leden van specifieke beveiligings- of managergroepen bevat en u ook leden van specifieke groepen uitsluit, worden de aanvankelijk opgenomen leden verwijderd. Als u een groep wilt maken die zowel uitgesloten als opgenomen leden bevat, raden we u aan om eerst een bovenliggende groep te maken met de opgenomen leden. Vervolgens maakt u voor deze groep een onderliggende groep waarin de uitgesloten leden worden vermeld. U kunt die onderliggende groep vervolgens zo nodig gebruiken voor de distributie van Intune-beleid, profielen en apps.

    > [!NOTE]
    > In de Azure-beheerportal kunt u een groep maken op basis van de manager waaraan de gebruikers rapporteren. De groep heeft een dynamisch karakter en verandert met het toevoegen of verwijderen van werknemers uit het team van die manager in Azure Active Directory. De procedure voor het maken van een Azure-groep op basis van een manager wordt beschreven in [Geavanceerde regels maken met kenmerken](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/) in de sectie **To configure a group as a "Manager" group** (Een groep configureren als een 'Manager'-groep).


4.  Op de pagina **Direct lidmaatschap definiëren** kunt u afzonderlijke gebruikers opnemen of uitsluiten die u opgeeft door te klikken op **Bladeren**. Als u de optie gebruikt om gebruikers te selecteren die zich niet in de door u opgegeven bovenliggende groep bevinden, worden die apparaten automatisch toegevoegd aan de bovenliggende groep. Onder in het dialoogvenster **Leden selecteren** vindt u de optie om handmatig een gebruiker toe te voegen. Dit is handig als u een gebruiker wilt toevoegen die nog geen ingeschreven apparaat heeft.


5.  Bekijk op de pagina **Overzicht** de acties die zullen worden uitgevoerd. Kies **Voltooien**.

U vindt de zojuist gemaakte groep in de lijst **Groepen**, in de werkruimte **Groepen**, onder de bovenliggende groep. Hier kunt u de groep ook bewerken of verwijderen.

> [!TIP]
> Beveiligingsgroepen zijn een zeer waardevolle resource voor het invullen van gebruikersgroepen. Aangezien in de beveiligingsgroepen is gedefinieerd wie er toegang heeft tot resources, kunnen deze goed worden gebruikt als basis voor Intune-gebruikersgroepen. Beveiligingsgroepen die vanuit Active Directory worden gesynchroniseerd met Azure Active Directory of die rechtstreeks in Azure Active Directory zijn gemaakt via het Office 365-beheercentrum of de Azure-beheerportal, zijn allemaal beschikbaar om gebruikersgroepen in Intune te maken.

## Weergaven voor het beheerdersrollen aanpassen
Met gefilterde groepsweergaven kunt u de weergave aanpassen die beheerders op basis van hun rol te zien krijgen. U kunt ook bepalen welke groepen door elke IT-beheerder kunnen worden beheerd. Dit kan handig zijn wanneer:

-   Uw IT-beheerders alleen items mogen implementeren voor specifieke gebruikers en apparaten.

-   Voor elke IT-beheerder hoeven alleen relevante apparaat- en gebruikersgroepen te worden weergegeven.

U kunt gefilterde groepsweergaven voor servicebeheerders configureren in de Intune-beheerconsole. Zie [Wat u moet weten voordat u met Microsoft Intune aan de slag gaat](/intune/get-started/what-to-know-before-you-start-microsoft-intune) voor meer informatie.

Nadat u gefilterde groepsweergaven voor een servicebeheerder hebt geconfigureerd, geldt voor deze beheerder het volgende:

-   Alleen de groepen kunnen weergeven en selecteren die u hebt opgegeven bij het implementeren van software of beleid of bij het gebruik van rapporten.

-   Geen informatie ontvangen over de status van de volgende pagina's van de beheerconsole:

    -   **Systeemoverzicht**

    -   **Overzicht van groepen**

    -   **Overzicht van Endpoint Protection**

    -   **Overzicht van waarschuwingen**

    -   **Overzicht van software**

    -   **Overzicht van beleid**

### Gefilterde groepsweergaven configureren

1.  Kies in de Intune-beheerconsole **Beheer** &gt; **Beheerdersbeheer** &gt; **Servicebeheerders**.

2.  Selecteer de servicebeheerder voor wie u groepen wilt filteren, en klik vervolgens op **Groepen beheren**.

3.  In het dialoogvenster **Selecteer de groepen die zichtbaar zijn voor deze servicebeheerder** voegt u de groepen toe die de geselecteerde servicebeheerder mag openen, en klikt u vervolgens op **OK**.

Nadat u de gefilterde groepsweergaven hebt geconfigureerd, kan de IT-beheerder alleen de door u geselecteerde groepen weergeven en selecteren.

## Groepen beheren
Wanneer u groepen hebt gemaakt, moet u deze op basis van de behoeften van uw organisatie blijven beheren.

U kunt eigenschappen van uw groep, zoals de naam, de beschrijving en leden van de groep, wijzigen.

Groepen die niet meer aan de behoeften van uw organisatie voldoen, kunnen worden verwijderd. Als u een groep verwijdert, worden de gebruikers die deel uitmaken van deze groep niet verwijderd.

## Volgende stappen

### Uw ontwerp controleren
Nadat u groepen en beleid hebt ingesteld, controleert u de praktische gevolgen van het ontwerp aan de hand van de **Bedoelde waarde** en de **Status**.

1. Selecteer een apparaat in een apparaatgroep en blader door de gegevenscategorieën boven aan het scherm.
2. Selecteer **Beleid** . Er wordt een scherm weergegeven dat lijkt op deze schermopname van de beleidsinstellingen van een Android-apparaat.

![Voorbeeld van iOS-instellingenbeleid](../media/Intune-Device-Policy-v.2.jpg)

Elk beleid heeft een **Bedoelde waarde** en een **Status**. De beoogde waarde is wat u wilt bereiken bij het toewijzen van het beleid. De status is datgene wat u feitelijk bereikt wanneer alle beleidsregels die betrekking hebben op het apparaat, samen met de beperkingen en vereisten van de hardware en het besturingssysteem als één geheel worden beschouwd.  In de schermopname ziet u twee duidelijke voorbeelden:

-   **Eenvoudige wachtwoorden toestaan** is ingesteld op **Ja**, zoals wordt weergegeven in de kolom **Bedoelde waarde** , maar de **Status** is **Niet van toepassing**. Dit komt doordat eenvoudige wachtwoorden niet worden ondersteund voor Android-apparaten.

-   Evengoed wordt het uitgevouwen beleidsitem **E-mailinstellingen voor iOS-apparaten** niet op dit apparaat toegepast, omdat het een Android-apparaat is.

> [!NOTE]
> Houd er rekening mee dat wanneer er twee sets beleidsregels met verschillende beperkingsniveaus zijn die op hetzelfde apparaat of dezelfde gebruiker van toepassing zijn, in de praktijk het meest beperkende beleid van toepassing is.



<!--HONumber=Jul16_HO4-->


