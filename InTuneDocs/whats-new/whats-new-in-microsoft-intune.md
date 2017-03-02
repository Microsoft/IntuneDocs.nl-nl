---
title: Wat is er nieuw? | Microsoft Docs
description: Ontdek wat er nieuw is in de release van Microsoft Intune van deze maand en in oudere releases
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 846084a3810e43d9fd6a6c254f1b0167a36f37ff
ms.openlocfilehash: b99731c7becd90f4092ec758234a96e202d95130
ms.lasthandoff: 02/15/2017


---
# <a name="whats-new-in-microsoft-intune---february-2017"></a>Wat is er nieuw in Microsoft Intune - februari 2017
Ontdek wat er nieuw is in deze release van Microsoft Intune. U vindt hier ook informatie over toekomstige wijzigingen waar u rekening mee moet houden én informatie over oudere releases.

> [!Note]
> Al deze functies worden uiteindelijk ondersteund voor implementaties voor hybride klanten (Configuration Manager met Intune). Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nieuwe mogelijkheden

### <a name="modernizing-the-company-portal-website---753980--"></a>De bedrijfsportalwebsite moderniseren <!--753980-->
De bedrijfsportalwebsite ondersteunt apps die zijn gericht op gebruikers die geen beheerde apparaten hebben. De website wordt in overeenstemming gebracht met andere Microsoft-producten en -services met een nieuw contrasterend kleurenschema, dynamische illustraties en een 'hamburgermenu', ![Kleine afbeelding van het hamburgermenu dat nu is toegevoegd in de linkerbovenhoek van de bedrijfsportalwebsite](./media/CP_hamburger_menu.png) dat contactgegevens van de helpdesk bevat, alsmede informatie over bestaande beheerde apparaten. De landingspagina wordt opnieuw ingedeeld om de nadruk te leggen op apps die beschikbaar zijn voor gebruikers, met carrousels voor uitgelichte en recent bijgewerkte apps. De [pagina met UI-updates](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui) bevat voor-en-na afbeeldingen.

### <a name="new-guided-experience-for-windows-10-company-portal---713927--"></a>Nieuwe begeleide ervaring voor Windows 10-bedrijfsportal<!--713927-->
Vanaf maart bevat de bedrijfsportal voor Windows 10 een begeleiding voor Intune voor apparaten die nog niet zijn geïdentificeerd of geregistreerd. Deze nieuwe ervaring biedt stapsgewijze instructies voor de gebruiker van de aangepaste Windows 10-build-versie, die gebruikers begeleidt bij het uitvoeren van AAD-registratie (vereist voor de identificatie voor voorwaardelijke toegangsfuncties) en MDM-registratie (vereist voor beheerfuncties op het apparaat). Deze ervaring is toegankelijk vanaf de startpagina van de bedrijfsportal en is optioneel. Gebruikers kunnen de app blijven gebruiken zolang ze de registratie en aanmelding niet voltooien. De functionaliteit kan echter beperkt zijn.

## <a name="notices"></a>Mededelingen

### <a name="group-migration-will-not-require-any-updates-to-groups-or-policies-for-ios-devices---898837--"></a>Bij groepsmigratie zijn geen updates voor groepen of beleidsregels vereist voor iOS-apparaten <!--898837-->
Voor elke Intune-apparaatgroep die vooraf is toegewezen door een inschrijvingsprofiel voor bedrijfsapparaten, wordt tijdens de migratie naar Azure Active Directory-apparaatgroepen een overeenkomende dynamische apparaatgroep in AAD gemaakt op basis van de naam van het inschrijvingsprofiel. Dit zorgt ervoor dat apparaten wanneer ze worden ingeschreven automatisch worden gegroepeerd en hetzelfde beleid en dezelfde apps ontvangen als de oorspronkelijke Intune-groep. 

Wanneer een tenant in het migratieproces wordt ingevoerd voor groepering en targeting, wordt in Intune automatisch een dynamische AAD-groep gemaakt die overeenkomt met een Intune-groep waarop een inschrijvingsprofiel voor bedrijfsapparaten is gericht. Als de Intune-beheerder de betreffende Intune-groep verwijdert, wordt de overeenkomende dynamische AAD-groep niet verwijderd. Leden van de groep en de dynamische query worden gewist, maar de groep zelf blijft aanwezig totdat de IT-beheerder deze via de AAD-portal verwijdert.

Ook als de IT-beheerder de Intune-groep wijzigt waarop een inschrijvingsprofiel voor bedrijfsapparaten is gericht, wordt in Intune een nieuwe dynamische groep gemaakt op basis van de nieuwe profieltoewijzing en wordt de dynamische groep die werd gemaakt voor de oude toewijzing niet verwijderd.

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Standaardinstelling voor het beheren van Windows-desktops via Windows-instellingen <!--663050-->
Het standaardgedrag voor het registreren van Windows 10-desktops verandert. Nieuwe registraties volgen het standaardproces van registratie via de MDM-agent in plaats van via de pc-agent. De bedrijfsportalwebsite biedt gebruikers van Windows 10-desktops registratie-instructies om ze te helpen bij het toevoegen van Windows 10-desktopcomputers als mobiele apparaten. Dit heeft geen gevolgen voor momenteel ingeschreven pc's en met behulp van de pc-agent kan uw organisatie nog altijd Windows 10-desktops beheren [als u dat liever hebt](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Verbetering van MAM-ondersteuning voor selectief wissen <!--581242-->
Eindgebruikers krijgen extra informatie over het verkrijgen van toegang tot werk- of schoolgegevens als die gegevens automatisch worden verwijderd op basis van het beleid 'Offline interval voordat app-gegevens worden gewist'.<!--, or the removal of the Intune Company Portal on Android.-->

### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Bedrijfsportal voor iOS-koppelingen openen in de app <!--665954-->
Koppelingen in de bedrijfsportal-app voor iOS, inclusief koppelingen naar documentatie en apps, worden rechtstreeks in de bedrijfsportal-app geopend met behulp van in-app-weergave van Safari. Deze update wordt afzonderlijk van de service-update in januari verzonden.

### <a name="new-mdm-server-address-for-windows-devices---893007--"></a>Nieuw MDM-serveradres voor Windows-apparaten <!--893007-->
Wanneer Windows- en Windows Phone-gebruikers een apparaat willen inschrijven, mislukt dit als ze (desgevraagd) __manage.microsoft.com__ invullen als het MDM-serveradres. Het MDM-serveradres is gewijzigd van __manage.microsoft.com__ in __enrollment.manage.microsoft.com__. Stel uw gebruikers ervan op de hoogte dat ze __enrollment.manage.microsoft.com__ moeten gebruiken als het MDM-serveradres als dit wordt gevraagd tijdens het inschrijven van een Windows- of Windows Phone-apparaat. Ga voor meer informatie over deze wijziging naar [aka.ms/intuneenrollsvrchange](https://aka.ms/intuneenrollsvrchange).

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Nieuwe gebruikerservaring voor de bedrijfsportal-app voor Android <!--621622-->
Vanaf maart volgt de bedrijfsportal-app voor Android [richtlijnen voor het ontwerpen van materiaal](https://material.io/guidelines/material-design/introduction.html) voor een moderne vormgeving. Deze verbeterde gebruikerservaring omvat het volgende:

* __Kleuren__: tabbladkoppen kunnen worden gekleurd volgens uw aangepaste kleurenpalet.
* __Interface__: de knoppen Aanbevolen apps en Alle apps op het tabblad Apps zijn bijgewerkt. De knop Zoeken is nu een zwevende actieknop.
* __Navigatie__: Alle apps biedt een tabbladweergave van de opties Aanbevolen, Alle en Categorieën om de navigatie te vereenvoudigen.
* __Service__: de leesbaarheid van de tabbladen Mijn apparaten en Contact opnemen met IT is verbeterd.

De [pagina met UI-updates](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui) bevat voor-en-na afbeeldingen.

### <a name="associate-multiple-management-tools-with-the-windows-store-for-business---926135--"></a>Meerdere beheerhulpprogramma's koppelen aan de Windows Store voor Bedrijven<!--926135-->
Als u meer dan één beheerhulpprogramma voor het implementeren van Windows Store voor Bedrijven-apps gebruikt, kon u voorheen slechts één van deze programma’s koppelen met de Windows Store voor Bedrijven. U kunt nu meerdere beheerhulpprogramma's met de Store koppelen, bijvoorbeeld Intune en Configuration Manager. Zie [Apps die u hebt aangeschaft in de Windows Store voor Bedrijven, beheren met Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune#associate-your-windows-store-for-business-account-with-intune) voor meer informatie.

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Wat is er nieuw in de openbare preview-versie van de nieuwe Intune-ervaring voor beheerders in Azure <!--736542-->

Aan het begin van kalenderjaar 2017 migreren we de volledige functionaliteit voor beheerders naar Azure, voor krachtig en geïntegreerd beheer van EMS-kernwerkstromen op een modern serviceplatform dat kan worden uitgebreid met Graph API’s.

Vanaf deze maand zal de openbare preview-versie van de nieuwe beheerderservaring te zien zijn voor nieuwe evaluatietenants in de Azure-portal. Tijdens de preview-periode worden de mogelijkheden en pariteit met de bestaande Intune-console iteratief geleverd.

De beheerderservaring in de Azure-portal zal gebruikmaken van de eerder aangekondigde nieuwe functionaliteit voor groepen en targeting. Wanneer uw bestaande tenant wordt gemigreerd naar de nieuwe ervaring voor groepen, vindt ook de migratie plaats naar de preview-versie van de nieuwe beheerderservaring. Als u in de tussentijd de nieuwe functionaliteit wilt testen of bekijken totdat de migratie van uw tenant is voltooid, kunt u zich aanmelden voor een nieuw Intune-evaluatieaccount of de [nieuwe documentatie](https://docs.microsoft.com/intune-azure/introduction/whats-new) raadplegen.

Als u vragen hebt over de planning van de migratie van uw tenant, neemt u contact op met het migratieteam via [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

U kunt [hier](https://docs.microsoft.com/intune-azure/introduction/whats-new) vinden wat er nieuw is in de Intune-preview-versie in Azure.

### <a name="see-also"></a>Zie tevens
* [Microsoft Intune-blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Roadmap voor cloudplatform](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Wat is nieuw in de Azure-preview?](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [Wat is er nieuw in de gebruikersinterface van de bedrijfsportal?](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)
* [Wat is er nieuw (archief)](whats-new-archive.md)

