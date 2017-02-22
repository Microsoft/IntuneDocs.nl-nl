---
title: Vroege editie | Microsoft Docs
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 68c7a23dc8769330c14f74e6aebb07eeb188a991
ms.openlocfilehash: 4bc9a2799bcce035c6847b7b2884ee24160426da


---


# <a name="the-early-edition-for-microsoft-intune---february-2017"></a>De vroege editie voor Microsoft Intune - februari 2017

De **Vroege editie** bevat een lijst met functies die worden toegevoegd aan toekomstige releases van Microsoft Intune. Deze informatie wordt in zeer beperkte mate onder geheimhoudingsverklaring verstrekt en kan worden gewijzigd. Sommige functies die hier worden vermeld, zullen mogelijk niet beschikbaar zijn op de sluitingsdatum en worden mogelijk beschikbaar gesteld in een latere release. Andere functies worden getest in een proefversie, zodat we zeker weten dat ze in gebruik kunnen worden genomen. Neem bij vragen contact op met uw contactpersoon voor Intune/projectmanagement.

Deze pagina wordt regelmatig bijgewerkt. Controleer op andere updates.

> [!Note]
> De volgende wijzigingen worden momenteel ontwikkeld voor Intune. Al deze functies worden uiteindelijk ondersteund voor implementaties voor hybride klanten (Configuration Manager met Intune). Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nieuwe mogelijkheden

### <a name="modernizing-the-company-portal-website---753980--"></a>De bedrijfsportalwebsite moderniseren <!--753980-->
De bedrijfsportalwebsite ondersteunt apps die zijn gericht op gebruikers die geen beheerde apparaten hebben. De website wordt in overeenstemming gebracht met andere Microsoft-producten en -services met een nieuw contrasterend kleurenschema, dynamische illustraties en een 'hamburgermenu', ![Kleine afbeelding van het hamburgermenu dat nu is toegevoegd in de linkerbovenhoek van de bedrijfsportalwebsite](./media/CP_hamburger_menu.png) dat contactgegevens van de helpdesk bevat, alsmede informatie over bestaande beheerde apparaten. De landingspagina wordt opnieuw ingedeeld om de nadruk te leggen op apps die beschikbaar zijn voor gebruikers, met carrousels voor uitgelichte en recent bijgewerkte apps. De [pagina met UI-updates](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui) bevat voor-en-na afbeeldingen.

### <a name="new-guided-experience-for-windows-10-company-portal---713927--"></a>Nieuwe begeleide ervaring voor Windows 10-bedrijfsportal<!--713927-->
Vanaf maart bevat de bedrijfsportal voor Windows 10 een begeleiding voor Intune voor apparaten die nog niet zijn geïdentificeerd of geregistreerd. Deze nieuwe ervaring biedt stapsgewijze instructies voor de gebruiker van de aangepaste Windows 10-build-versie, die gebruikers begeleidt bij het uitvoeren van AAD-registratie (vereist voor de identificatie voor voorwaardelijke toegangsfuncties) en MDM-registratie (vereist voor beheerfuncties op het apparaat). Deze ervaring is toegankelijk vanaf de startpagina van de bedrijfsportal en is optioneel. Gebruikers kunnen de app blijven gebruiken zolang ze de registratie en aanmelding niet voltooien. De functionaliteit kan echter beperkt zijn.

###

## <a name="notices"></a>Mededelingen

### <a name="group-migration-will-not-require-any-updates-to-groups-or-policies-for-ios-devices---898837--"></a>Bij groepsmigratie zijn geen updates voor groepen of beleidsregels vereist voor iOS-apparaten <!--898837-->
Voor elke Intune-apparaatgroep die vooraf is toegewezen door een inschrijvingsprofiel voor bedrijfsapparaten, wordt tijdens de migratie naar Azure Active Directory-apparaatgroepen een overeenkomende dynamische apparaatgroep in AAD gemaakt op basis van de naam van het inschrijvingsprofiel. Dit zorgt ervoor dat apparaten wanneer ze worden ingeschreven automatisch worden gegroepeerd en hetzelfde beleid en dezelfde apps ontvangen als de oorspronkelijke Intune-groep.

Wanneer een tenant in het migratieproces wordt ingevoerd voor groepering en targeting, wordt in Intune automatisch een dynamische AAD-groep gemaakt die overeenkomt met een Intune-groep waarop een inschrijvingsprofiel voor bedrijfsapparaten is gericht. Als de Intune-beheerder de betreffende Intune-groep verwijdert, wordt de overeenkomende dynamische AAD-groep niet verwijderd. Leden van de groep en de dynamische query worden gewist, maar de groep zelf blijft aanwezig totdat de IT-beheerder deze via de AAD-portal verwijdert.

Ook als de IT-beheerder de Intune-groep wijzigt waarop een inschrijvingsprofiel voor bedrijfsapparaten is gericht, wordt in Intune een nieuwe dynamische groep gemaakt op basis van de nieuwe profieltoewijzing en wordt de dynamische groep die werd gemaakt voor de oude toewijzing niet verwijderd.

### <a name="new-mdm-server-address-for-windows-devices---893007--"></a>Nieuw MDM-serveradres voor Windows-apparaten <!--893007-->
Wanneer Windows- en Windows Phone-gebruikers een apparaat willen inschrijven, mislukt dit als ze (desgevraagd) __manage.microsoft.com__ invullen als het MDM-serveradres. Het MDM-serveradres is gewijzigd van __manage.microsoft.com__ in __enrollment.manage.microsoft.com__. Stel uw gebruikers ervan op de hoogte dat ze __enrollment.manage.microsoft.com__ moeten gebruiken als het MDM-serveradres als dit wordt gevraagd tijdens het inschrijven van een Windows- of Windows Phone-apparaat. Voor deze update moet een CNAME in DNS waarmee __EnterpriseEnrollment.contoso.com__ wordt omgeleid naar __manage.microsoft.com__ worden vervangen door een CNAME in DNS waarmee __EnterpriseEnrollment.contoso.com__ wordt omgeleid naar __EnterpriseEnrollment-s.manage.microsoft.com__. Ga voor meer informatie over deze wijziging naar [aka.ms/intuneenrollsvrchange](https://aka.ms/intuneenrollsvrchange).

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Nieuwe gebruikerservaring voor de bedrijfsportal-app voor Android <!--621622-->
Vanaf maart volgt de bedrijfsportal-app voor Android [richtlijnen voor het ontwerpen van materiaal](https://material.io/guidelines/material-design/introduction.html) voor een moderne vormgeving. Deze verbeterde gebruikerservaring omvat het volgende:

* __Kleuren__: tabbladkoppen kunnen worden gekleurd volgens uw aangepaste kleurenpalet.
* __Interface__: de knoppen Aanbevolen apps en Alle apps op het tabblad Apps zijn bijgewerkt. De knop Zoeken is nu een zwevende actieknop.
* __Navigatie__: Alle apps biedt een tabbladweergave van de opties Aanbevolen, Alle en Categorieën om de navigatie te vereenvoudigen.
* __Service__: de leesbaarheid van de tabbladen Mijn apparaten en Contact opnemen met IT is verbeterd.

De [pagina met UI-updates](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui) bevat voor-en-na afbeeldingen.

### <a name="associate-multiple-management-tools-with-the-windows-store-for-business---926135--"></a>Meerdere beheerhulpprogramma's koppelen aan de Windows Store voor Bedrijven<!--926135-->
Als u meer dan één beheerhulpprogramma voor het implementeren van Windows Store voor Bedrijven-apps gebruikt, kon u voorheen slechts één van deze programma’s koppelen met de Windows Store voor Bedrijven. U kunt nu meerdere beheerhulpprogramma's met de Store koppelen, bijvoorbeeld Intune en Configuration Manager. Zie [Apps die u hebt aangeschaft in de Windows Store voor Bedrijven, beheren met Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune#associate-your-windows-store-for-business-account-with-intune) voor meer informatie.

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Openbare preview-versie van de nieuwe Intune-ervaring voor beheerders op Azure <!--736542-->

Aan het begin van kalenderjaar 2017 migreren we de volledige functionaliteit voor beheerders naar Azure, voor krachtig en geïntegreerd beheer van EMS-kernwerkstromen op een modern serviceplatform dat kan worden uitgebreid met Graph API’s.

Vanaf deze maand zal de openbare preview-versie van de nieuwe beheerderservaring te zien zijn voor nieuwe evaluatietenants in de Azure-portal. Tijdens de preview-periode worden de mogelijkheden en pariteit met de bestaande Intune-console iteratief geleverd.

De beheerderservaring in de Azure-portal zal gebruikmaken van de eerder aangekondigde nieuwe functionaliteit voor groepen en targeting. Wanneer uw bestaande tenant wordt gemigreerd naar de nieuwe ervaring voor groepen, vindt ook de migratie plaats naar de preview-versie van de nieuwe beheerderservaring. Als u in de tussentijd de nieuwe functionaliteit wilt testen of bekijken totdat de migratie van uw tenant is voltooid, kunt u zich aanmelden voor een nieuw Intune-evaluatieaccount of de [nieuwe documentatie](https://docs.microsoft.com/en-us/intune-azure/introduction/what-is-microsoft-intune) raadplegen.

Als u vragen hebt over de planning van de migratie van uw tenant, neemt u contact op met het migratieteam via [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="february-2017"></a>Februari 2017

#### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Mogelijkheid om de inschrijving van mobiele apparaten te beperken <!--747600, 795782-->
Er zijn in Intune nieuwe inschrijvingsbeperkingen toegevoegd die bepalen welke platforms voor mobiele apparaten kunnen worden ingeschreven. Intune onderscheidt platforms voor mobiele apparaten als iOS, Mac OS, Android, Windows en Windows Mobile.

* Een beperking voor de registratie van mobiele apparaten, betekent niet dat de PC-clientregistratie ook is beperkt.  
* Alleen voor iOS en Android geldt er een extra optie voor het blokkeren van de inschrijving van apparaten die in persoonlijk eigendom zijn.

Intune markeert alle nieuwe apparaten als persoonlijk, tenzij de IT-beheerder actie onderneemt om deze te markeren als bedrijfseigen, zoals uitgelegd in [dit artikel](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices).

#### <a name="view-all-actions-on-managed-devices---677150--"></a>Alle acties voor beheerde apparaten weergeven <!--677150-->
Er is een nieuw rapport __Apparaatacties__, waarin wordt weergegeven wie externe acties, zoals het herstellen van fabrieksinstellingen, op apparaten heeft uitgevoerd. In dit rapport wordt ook de status van de actie getoond.

#### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Niet-beheerde apparaten hebben toegang tot toegewezen apps <!--664691-->
Als onderdeel van de ontwerpwijzigingen op de bedrijfsportalwebsite kunnen iOS- en Android-gebruikers op hun niet-beheerde apparaten apps installeren die aan hen zijn toegewezen als 'beschikbaar zonder inschrijving'. Gebruikers kunnen zich met behulp van hun Intune-referenties aanmelden bij de bedrijfsportalwebsite en de lijst met aan hen toegewezen apps bekijken. De app-pakketten van de 'beschikbaar zonder inschrijving'-apps kunnen worden gedownload via de bedrijfsportalwebsite. Deze wijziging is niet van toepassing op apps die pas na inschrijving kunnen worden geïnstalleerd, omdat gebruikers wordt gevraagd hun apparaat in te schrijven als zij deze apps willen installeren.

#### <a name="custom-app-categories---748805--"></a>Aangepaste app-categorieën <!--748805-->
U kunt nu categorieën maken, bewerken en toewijzen voor apps die u aan Intune toevoegt. Categorieën kunnen momenteel alleen worden opgegeven in het Engels.
Zie [Een app toevoegen aan Intune](/intune-azure/manage-apps/add-apps).

#### <a name="display-device-categories---814654--"></a>Apparaatcategorieën weergeven <!--814654-->
U kunt nu de apparaatcategorie als kolom in de lijst met apparaten weergeven. U kunt ook de categorie uit de sectie met eigenschappen van de apparaateigenschappenblade bewerken.

### <a name="january-2017"></a>Januari 2017

#### <a name="custom-app-categories---748805--"></a>Aangepaste app-categorieën <!--748805-->
U kunt nu categorieën maken, bewerken en toewijzen voor apps die u aan Intune toevoegt. Categorieën kunnen momenteel alleen worden opgegeven in het Engels.

#### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748803--"></a>Toewijzen van line-of-business-apps, ongeacht of apparaten al dan niet zijn geregistreerd <!--748803-->
U kunt nu line-of-business-apps uit de store toewijzen aan gebruikers, ongeacht of hun apparaten al dan niet zijn geregistreerd bij Intune. Als een apparaat van gebruikers niet is geregistreerd bij Intune, moeten ze daarvoor de bedrijfsportalwebsite gebruiken en niet de bedrijfsportal-app.

### <a name="december-2016"></a>December 2016

#### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Integratie van onkostenbeheer voor telecom in de openbare preview-versie van Azure-portal<!--747605-->
We beginnen nu met preview-versies van de integratie met externe systemen voor onkostenbeheer voor telecom (TEM) in de Azure-portal. U kunt Intune gebruiken om limieten in te stellen voor gegevensgebruik, voor zowel nationaal als roaming. Hierbij beginnen we met [Saaswedo](http://www.saaswedo.com). Als u deze functie in uw proeftenant wilt inschakelen, neemt u [contact op met Microsoft-ondersteuning](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

### <a name="see-also"></a>Zie tevens
Zie [Wat is er nieuw in Microsoft Intune?](whats-new-in-microsoft-intune.md) voor meer informatie over recente ontwikkelingen.



<!--HONumber=Feb17_HO2-->


