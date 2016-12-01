---
title: Migreren naar Azure Active Directory-groepen | Microsoft Intune
description: Hoe uw groepen worden gemigreerd van Intune naar Azure AD
keywords: 
author: Mtillman
ms.author: mtillman
manager: angerobe
ms.date: 10/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 03b69afa-3548-4033-9039-191528f3fd99
translationtype: Human Translation
ms.sourcegitcommit: 17b957cc2baedddfc53bfdf7b875e4ecb28b8517
ms.openlocfilehash: e14bbadc4293b7b963197b35704a7170e4fc29e8


---

## <a name="the-new-admin-experience-for-groups"></a>De nieuwe beheerderservaring voor groepen
    
Op basis van uw feedback, waaruit naar voren kwam dat u groepen graag op één uniforme manier wilt samenstellen en beheren binnen de hele Enterprise Mobility + Security-suite, gaan we Intune-groepen converteren naar Azure Active Directory-beveiligingsgroepen. Dit zal leiden tot een uniformer beheer van groepen voor zowel Intune als Azure Active Directory (Azure AD). Deze nieuwe manier van werken voorkomt dat u groepen moet dupliceren voor verschillende services en biedt uitbreidingsmogelijkheden met PowerShell en Graph. 

### <a name="how-and-when-will-i-migrate-to-the-new-groups-experience"></a>Wanneer en hoe vindt mijn migratie naar deze nieuwe manier van werken met groepen plaats?
Voor huidige klanten wordt de migratie gespreid over een langere periode, maar niet eerder dan december 2016. We sturen u een kennisgeving voordat uw groepen worden gemigreerd. Als u vragen of opmerkingen hebt over de migratie, kunt u contact opnemen met ons migratieteam op [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="what-new-features-will-be-available-to-me"></a>Welke nieuwe functies zijn er beschikbaar voor mij?
Dit is de nieuwe functionaliteit die wordt geïntroduceerd: 
 
-    Azure AD-beveiligingsgroepen worden ondersteund in Intune voor alle typen implementaties. 
-    Azure AD-beveiligingsgroepen ondersteunen het groeperen van apparaten samen met gebruikers.
-    Azure AD-beveiligingsgroepen ondersteunen dynamische groepen met Intune-apparaatkenmerken. U kunt apparaten bijvoorbeeld dynamisch groeperen op basis van hun platform, zoals iOS. Op die manier wordt een nieuw iOS-apparaat dat wordt ingeschreven in uw organisatie, automatisch toegevoegd aan de dynamische iOS-apparaatgroep.
-    Beheerders kunnen groepsbeheertaken in Azure AD en Intune op een uniforme manier uitvoeren.
- De *Intune-servicebeheerdersrol* wordt toegevoegd aan Azure AD om servicebeheerders in Intune in staat te stellen beheertaken uit te voeren in Azure AD.

 
### <a name="what-intune-functionality-wont-be-available"></a>Welke Intune-functionaliteit is straks niet meer beschikbaar?
Hoewel het werken met groepen wordt verbeterd, zal bepaalde Intune-functionaliteit niet meer beschikbaar zijn na de migratie.

#### <a name="group-management-functionality"></a>Groepsbeheerfunctionaliteit

-   U kunt geen leden of groepen meer uitsluiten wanneer u een nieuwe groep maakt. Met de dynamische groepen van Azure AD kunt u echter wel gebruikmaken van kenmerken om geavanceerde regels te maken waarmee u leden kunt uitsluiten op basis van criteria. U kunt bijvoorbeeld een geavanceerde regel maken waarmee u alle personen op de afdeling Verkoop opneemt in een beveiligingsgroep, behalve degenen waarbij het woord 'assistent' in hun titel voorkomt. Deze geavanceerde regel ziet er als volgt uit: `(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`. Zie [Geavanceerde regels maken met kenmerken](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/) voor meer informatie.
-   De groepen **Niet-gegroepeerde gebruikers** en **Niet-gegroepeerde apparaten** worden niet meer ondersteund. Deze groepen worden ook niet gemigreerd.

#### <a name="group-dependent-functionality"></a>Groepsafhankelijke functionaliteit

-   De servicebeheerdersrol heeft geen machtigingen voor **Groepen beheren**.
-   U kunt geen Exchange ActiveSync-apparaten groeperen.  Uw groep van **alle met EAS beheerde apparaten** wordt geconverteerd van een groep naar een rapportweergave.
-  Het maken van draaitabellen met groepen in rapporten is niet mogelijk.
-  Het maken van meldingsregels die zijn gericht op aangepaste groepen, is niet mogelijk.

### <a name="what-should-i-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
 Hier zijn enkele aanbevelingen die deze overgang eenvoudiger zullen maken voor u:
 
- Verwijder ongewenste of overbodige Intune-groepen voordat de migratie plaatsvindt.
- Beoordeel de manier waarop gebruikmaakt van uitsluiting in groepen en bedenk hoe u uw groepen opnieuw wilt vormgeven, zodat u geen uitsluiting hoeft te gebruiken of zodat u geavanceerde regels kunt gebruiken om hetzelfde doel te bereiken.
-  Hebt u beheerders die geen machtigingen hebben voor het maken van groepen in Azure AD, vraag dan uw Azure AD-beheerder om deze beheerders toe te voegen aan de Azure AD-rol **Intune-servicebeheerder** .

Hier vindt u ook meer informatie over beveiligingsgroepen in Azure AD:
-  Lees voor een overzicht [Toegang tot resources beheren met Azure Active Directory-groepen](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/).
-  Zie voor meer informatie over het maken en beheren van Azure AD-groepen [Groepen beheren in Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/).
-  Zie voor meer informatie over geavanceerde regels voor beveiligingsgroepen [Geavanceerde regels maken met kenmerken](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).

> [!NOTE]
Het zal u waarschijnlijk opvallen dat in de documentatie over beveiligingsgroepen in Azure AD niet gesproken wordt over het maken van groepen voor apparaten. Die functionaliteit wordt ingeschakeld in Azure AD voordat de migratie van de Intune-groep begint.

## <a name="migration-details"></a>Details van de migratie
Hier vindt u de details van hoe uw Intune-groepen worden gemigreerd naar Azure AD-beveiligingsgroepen.

### <a name="migration-of-existing-groups"></a>Migratie van bestaande groepen

| Intune-groep wordt...|...Azure AD-beveiligingsgroep|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Statische gebruikersgroepen waarop Intune-beleid is gericht|Statische Azure AD-beveiligingsgroepen met dezelfde gebruikers|
|Dynamische gebruikersgroepen waarop Intune-beleid is gericht|Statische Azure AD-beveiligingsgroepen met een Azure AD-beveiligingsgroepshiërarchie|
|Statische apparaatgroepen waarop Intune-beleid is gericht|Statische Azure AD-beveiligingsgroepen met apparaten|
|Dynamische apparaatgroepen met apparaatkenmerken waarop Intune-beleid is gericht|Dynamische Azure AD-beveiligingsgroepen met apparaatkenmerken|
|Een groep met een voorwaarde voor opneming|Een afzonderlijke statische Azure AD-beveiligingsgroep die een groep plus eventuele statische/dynamische leden zal bevatten, die overeenkomstig de voorwaarde voor opneming in Intune werden toegestaan|
|Een groep met een uitsluitingsvoorwaarde|...wordt niet gemigreerd. Uitsluitingsvoorwaarden worden niet ondersteund tijdens het maken van statische groepen in Azure AD. Een uitsluitingsvoorwaarde kan worden gebruikt bij het maken van een dynamische groep in Azure AD.|
|De standaardgroepen van **Alle gebruikers**, **Niet-gegroepeerde gebruikers**, **Alle apparaten**, **Niet-gegroepeerde apparaten**, **Alle computers**, **Alle mobiele apparaten**, **Alle met MDM-beheerde apparaten** en **Alle met EAS beheerde apparaten** die u in Intune-beleid gebruikt  |Azure AD-beveiligingsgroepen. Standaardgroepen die niet worden gebruikt, zouden met behulp van dynamische groepen door de klant moeten worden gemaakt wanneer deze nodig zijn.|

### <a name="changes-in-hierarchical-views"></a>Wijzigingen in hiërarchische weergaven
Hiërarchische weergave voor groepen in Intune  Een relatie tussen een bovenliggende en onderliggende groep was in Intune een relatie tussen een hoofdverzameling en een deelverzameling, wat in Azure AD niet het geval is. Onderliggende groepen kunnen leden hebben die de bovenliggende groepen niet hadden. Groepen kunnen ook cyclisch van aard zijn in Azure AD: een bovenliggende groep kan een onderliggende groep van een onderliggende groep zijn.

### <a name="attribute-conversion-during-migration"></a>Conversie van kenmerken tijdens een migratie
Kenmerken zijn eigenschappen van apparaten die kunnen worden gebruikt om groepen te definiëren. Deze tabel bevat een beschrijving van hoe deze criteria worden gemigreerd naar Azure AD-beveiligingsgroepen.

| Intune-kenmerk|Azure AD-kenmerk|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|OE-kenmerk (organisatie-eenheid) voor apparaatgroepen|OE-kenmerk voor dynamische groepen. Waarden voor kenmerken die beschikbaar zijn gemaakt door de beheerder en die betrekking hebben op elke tenant, door ze voor weergavedoeleinden toe te voegen als een van de tenantonderdelen.|
|Domeinnaamkenmerk voor apparaatgroepen|Domeinnaamkenmerk voor dynamische groepen. Waarden voor kenmerken die beschikbaar zijn gemaakt door de beheerder en die betrekking hebben op elke tenant, door ze voor weergavedoeleinden toe te voegen als een van de tenantonderdelen|
|Beveiligingsgroep als een kenmerk voor gebruikersgroepen|Groepen kunnen geen kenmerken zijn van dynamische query's in Azure AD. Dynamische groepen kunnen alleen kenmerken bevatten die specifiek zijn voor een gebruiker of apparaat.|
|Kenmerk manager voor gebruikersgroepen|Geavanceerde regel voor kenmerk *manager* in dynamische groepen|
|Alle gebruikers van de bovenliggende gebruikersgroep|Statische groep met die groep als een lid|
|Alle mobiele apparaten uit de bovenliggende apparaatgroep|Statische groep met die groep als een lid|
|Alle mobiele apparaten die beheerd worden met direct beheer van Microsoft Intune|Kenmerk beheertype met 'MDM' als waarde voor dynamische groep|
|Alle mobiele apparaten die worden beheerd met EAS|EAS-apparaten kunnen niet worden gegroepeerd in Azure AD. Uw groep van **alle met EAS beheerde apparaten** wordt geconverteerd van een groep naar een rapportweergave.|
|Geneste groepen binnen statische groepen |Geneste groepen binnen statische groepen|
|Geneste groepen binnen dynamische groepen|Dynamische groep met één genest niveau|


## <a name="migration-of-policies"></a>Migratie van beleid
Terwijl de groep wordt gemigreerd, kunt u uw beleid blijven beheren in de Intune-console. Er bevindt zich een koppeling in de Intune-console naar uw Azure-beheerconsole, waar u uw groepen gaat beheren. Uw beleid zal geïmplementeerd blijven worden naar de gemigreerde Azure AD-beveiligingsgroepen die parallel lopen aan uw oude Intune-groepen.

Wanneer de volledige functionaliteit van Intune naar de Azure-beheerportal is gemigreerd (rond het eerste kwartaal van 2017), gaat u beleidsregels en groepen vanaf hier beheren.

     
### <a name="see-also"></a>Zie tevens
[Toegang tot resources beheren met Azure Active Directory-groepen](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/)

[Groepen beheren in Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/)

[Geavanceerde regels maken met kenmerken](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/)



<!--HONumber=Nov16_HO1-->


