---
title: Include-bestand
description: Include-bestand
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: 073115d33f9a4f22fe3706ef15860c2a8d8a68ee
ms.sourcegitcommit: 69aaf89140f82f344404e75a69dc59d8a1585b10
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 03/30/2019
ms.locfileid: "58675490"
---
Deze berichten bevatten belangrijke informatie waarmee u kunt voorbereiden op toekomstige Intune wijzigingen en functies. 

### <a name="change-in-enrollment-workflow-with-intune-company-portal-on-corporate-ios-devices-authenticating-with-setup-assistant----1927359---"></a>Wijziging in de werkstroom van de inschrijving met Intune-bedrijfsportal op zakelijke iOS-apparaten verifiëren met Configuratieassistent <!-- 1927359 -->
Er is een toekomstige wijzigingen in de werkstroom voor het inschrijven van iOS-apparaten via een van de Apple bedrijfsapparaten registratiemethoden - Apple Configurator, Apple Business Manager, Apple School Manager of het Apple Device Enrollment Program (DEP) van bij het gebruik van Setup Assistant voor verificatie. Deze wijziging geldt alleen voor apparaten die zijn ingeschreven met gebruikersaffiniteit.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Wanneer deze wijziging in ~~maart~~ april wordt uitgerold, worden inschrijvingsprofielen in Intune in Azure Portal bijgewerkt zodat u kunt opgeven hoe apparaten zich verifiëren en hoe zij de bedrijfsportal-app ontvangen. Er is een verbeterde werkstroom voor iOS-apparaten inschrijven via de hierboven genoemde methoden. 

- Wanneer nieuwe apparaten inschrijven en verificatie met Configuratieassistent, u zult kunnen kiezen of u de bedrijfsportal-app automatisch te implementeren. Eindgebruikers wordt niet meer zien het scherm 'Uw apparaat identificeren' en het scherm 'Bevestig uw apparaat' in de stroom voor inschrijving.  
- Op apparaten die al zijn ingeschreven via Configuratieassistent via een van de Apple bedrijfsapparaten registratiemethoden, moet u actie ondernemen als u wilt inschakelen van voorwaardelijke toegang. Hebt u een configuratiebeleid voor apps configureren met een specifieke xml in de bedrijfsportal-App omlaag naar deze apparaten te pushen. Er zijn instructies om dit te doen in het blogbericht: op de koppeling meer informatie. Als u ervoor kiest om de bedrijfsportal-App op deze manier, zien eindgebruikers niet meer het scherm 'Uw apparaat identificeren' en het scherm 'Bevestig uw apparaat' in de stroom voor inschrijving. 
- Na deze wijziging wordt geïmplementeerd, als u de bedrijfsportal-App met hebt geïmplementeerd krijgt het app-configuratieprofiel hierboven genoemde en als eindgebruikers downloaden van de bedrijfsportal-app vanuit de App store en deze zich kan aanmelden, maar u een foutmelding. Ze niet mogelijk de app voor voorwaardelijke toegang gebruiken. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
Als u van plan bent over het gebruik van de werkstroom gewijzigd, moet u de richtlijnen van uw eindgebruikers om aan te geven die bijwerken:

- Eindgebruikers kunnen zichtbaar de twee schermen hierboven vermeld in de stroom voor inschrijving niet meer. 
- Ze moet zich aanmelden bij de bedrijfsportal-App wanneer deze automatisch wordt geïmplementeerd en niet uit de appstore te downloaden. 

U kunt nu een app-configuratiebeleid maken indien nodig, ter voorbereiding op deze wijziging. Wanneer deze nieuwe werkstroom zichtbare ziet u bijgewerkte inschrijvingsprofielen in de console. We u ook kennis van deze implementatie via het berichtencentrum. Hierna moet u de actie ondernemen, zodat uw eindgebruikers door te verifiëren met Configuratieassistent via DEP inschrijven en kunt u bedrijfsportal-App voor voorwaardelijke toegang kunt.

Zie onze blogbericht ondersteuning op de koppeling meer informatie voor meer informatie over deze wijziging.

#### <a name="additional-information"></a>Als u meer informatie 
[https://aka.ms/enrollment_setup_assistant](https://aka.ms/enrollment_setup_assistant)

### <a name="plan-for-change-user-experience-update-to-intune-company-portal-app-for-ios"></a>Geplande wijziging: update van de gebruikerservaring voor de iOS-bedrijfsportal-app van Intune
Met trots kunnen we mededelen dat Intune binnenkort een geheel nieuwe gebruikerservaring biedt voor de iOS-bedrijfsportal-app. De startpagina is qua vormgeving geheel vernieuwd en bevat geavanceerde filters en snellere toegang tot apps en boeken.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Deze update behoudt de functionaliteit van de huidige iOS-bedrijfsportal en biedt daarnaast de volgende nieuwe functies:
- Een startpagina met het uiterlijk van iOS 
- De mogelijkheid om te filteren op inhoud en zoekresultaten, de mogelijkheid om te filteren op het type inhoud (apps of eBooks) en beschikbaarheid (hiervoor is apparaatbeheer vereist; of beschikbaar zonder inschrijving)
- Mogelijkheid om te zoeken naar eBooks
- Zoekgeschiedenis voor apps en e-Books

Als u meedoet aan het TestFlight-programma van Apple, krijgt u een melding zodra de voorlopige versie van de bijgewerkte iOS-bedrijfsportal-app van Intune beschikbaar is. Als u niet meedoet aan het TestFlight-programma van Apple, kunt u zich hiervoor alsnog aanmelden. Als u zich aanmeldt, kunt u de bijgewerkte bedrijfsportal-app gebruiken voordat deze beschikbaar is voor uw eindgebruikers. U kunt ook feedback rechtstreeks naar de Intune-team.  

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Wat kan ik doen om me voor te bereiden op deze wijziging?
U hoeft geen actie te ondernemen; deze wijzigingen zullen worden doorgevoerd in een nieuwe versie van de iOS-bedrijfsportal-app. 

#### <a name="additional-information"></a>Als u meer informatie
[https://aka.ms/cp_update_iOS](https://aka.ms/cp_update_iOS)

### <a name="check-your-delay-visibility-of-software-updates-setting-in-intune"></a>Controleer de instelling 'Vertraging zichtbaarheid van de Software-updates' in Intune 

We gedeeld in MC171466 die er enkele instellingen in alle richtingen in de console verplaatsen zijn. Met de update van maart aan Intune, wordt de instelling 'Vertraging zichtbaarheid van de Software-updates' volledig verwijdert uit de beleidsblade van het iOS-update. Dit heeft geen invloed op hoe uw geplande software-updates van toepassing zijn, maar dit mogelijk invloed op hoe lang de zichtbaarheid van een update is uitgesteld voor eindgebruikers. Het is mogelijk om actie te ondernemen vóór het einde van maart als u deze instelling gebruiken. 

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Nadat de update van februari Intune-service, zult u merken dat de instelling zich dat in apparaatbeperkingsprofielen in de console en in de iOS-beleid in de Software-update-blade bijwerken. Wanneer u deze wijziging is doorgevoerd in de console ziet, volgt wat u mogelijk nodig om te doen.

- Voor bestaande updatebeleid voor iOS: hebt u aangepaste geconfigureerd met deze instelling op een andere waarde dan de standaard 30 dagen en wilt dat uw bestaande configuraties voor de instelling voor de zichtbaarheid vertraging om door te gaan moet worden toegepast na het einde van maart, moet u een nieuwe maken iOS-apparaatbeperkingsprofiel. Hier, moet de instelling voor de zichtbaarheid vertraging dezelfde waarden zoals in de bestaande iOS-updatebeleid en aan dezelfde groepen worden toegepast. Nadat de service-update van maart u worden niet meer waarden voor deze instelling in bestaande iOS-updatebeleid bewerken, omdat deze niet langer zichtbaar is in deze blade. U kunt deze instelling wordt in plaats daarvan configureert in de nieuwe profielen.
  Als de waarde voor aantal dagen dat u kunt uitstellen zichtbaarheid komt niet overeen met op beide locaties voor aangepaste geconfigureerde instellingswaarden, de vertraging zichtbaarheid instelling niet werkt, en eindgebruikers de te zien op hun apparaten zodra deze beschikbaar is. Dit kan minimale gevolgen voor de meeste klanten hebben omdat de andere instellingen in de blade beleid voor Software-Update altijd voorrang via deze instelling in de console genomen hebben.
- Voor nieuwe updatebeleid voor iOS: als u probeert te maken van nieuw beleid op de blade van Software-updates na de update van februari voor Intune-service, ziet u deze instelling grijs. Hier ziet u een opmerking in de console die u wordt omgeleid naar de blade van het apparaat configureren als u wilt uitstellen zichtbaarheid van updates.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Wat kan ik doen om me voor te bereiden op deze wijziging?
U hoeft geen actie te ondernemen als u deze instelling niet gebruikt of niet wilt uitstellen zichtbaarheid van de software-updates voor uw eindgebruikers.

Als u wilt de zichtbaarheid van updates uitstellen, start u de instelling configureren in de nieuwe profielen in de blade van de apparaatconfiguratie onder Apparaatbeperkingen > Algemeen. Als u hebt deze aangepaste instelling geconfigureerd in de bestaande iOS-updatebeleid, een nieuwe gelijkwaardige apparaatbeperkingsprofiel maken met dezelfde waarde voor 'days' vertraging zichtbaarheid van updates voor uw gebruikers, nadat de februari en bijwerken vóór maart is uitgerold. 

U wilt mogelijk bijwerken van de richtlijnen van uw IT-professionals en kennis van de helpdesk.

Zie onze ondersteuning-blogbericht op aanvullende informatie voor meer informatie over het configureren van deze instelling.

#### <a name="additional-information"></a>Als u meer informatie 
[https://aka.ms/Delay_visibility_setting_iOS](https://aka.ms/Delay_visibility_setting_iOS)

### <a name="plan-for-change-upcoming-fix-for-windows-10-email-profiles-in-intune---3904031--"></a>Plannen voor wijziging: aankomende oplossing voor Windows 10-e-mailprofielen in Intune <!--3904031-->
De manier waarop die intune e schrijft-profielen voor Windows 10 in de April naar de Intune-service ook is een fout opgelost bijwerken dat uw e-mailprofielen blijven werken in toekomstige versies van Windows 10 worden bijgewerkt. Er is een actie die u wilt uitvoeren nadat u hebt deze oplossing wordt geïmplementeerd.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Deze wijziging heeft gevolgen voor u als u e-mailprofielen en Windows 10
- De systeemeigen e-mailclient op Windows 10-desktops of
- De Outlook-e-mailclient op Windows 10 Mobile

Dit heeft gevolgen voor zowel Intune standalone en hybride Mobile Device Management (MDM)-klanten.

Nadat de update van April implementeert, moet u deze profielen in de Intune-beheerconsole (in de Configuration Manager-beheerconsole als u hybride MDM) opnieuw maken.

Als u geen actie uitvoert, moet u dit is wat u ziet voor profielen die zijn gemaakt vóór de update van April:

- Bestaande e-mailprofielen worden weergegeven in de foutstatus in de Intune-console of de Configuration Manager-beheerconsole, maar eindgebruikers wordt nog steeds toegang hebben tot e-mail. Nadat een nieuwe Windows-update implementeert, wordt deze profielen niet werken. Eindgebruikers op apparaten die worden toegepast met deze profielen verliest de toegang tot e-mail.
- Wijzigingen in deze profielen nadat April wordt niet weerspiegeld in de beoogde apparaten.
- Selectief wissen werkt niet voor het verwijderen van deze profielen, zelfs nadat de oplossing wordt geïmplementeerd in April.

Als u actie ondernemen en opnieuw e-mailprofielen maken, moeten eindgebruikers vergelijkbaar met de stappen doorlopen wanneer een e-mailprofiel voor de eerste keer wordt geïmplementeerd. De e-mail kunnen worden gesynchroniseerd als ze akkoord gaat met de update die van toepassing het nieuwe profiel is.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
U moet actie ondernemen nadat de oplossing wordt geïmplementeerd met de update van April. We vragen u u via het berichtencentrum wanneer deze wijziging live meteen zodat u beginnen kunt met het opnieuw maken van de profielen in Intune.

Als u Windows 10-e-mailprofielen in Intune gebruikt, moet u de volgende stappen uit:

1. Bestaande Windows 10-profiel-instellingen vastleggen
2. Toewijzing ongedaan maken en/of bestaande profielen verwijderen
3. Nieuwe profielen met behulp van de vastgelegde instellingen maken en de nieuwe profielen toewijzen aan dezelfde groepen

Mogelijk moet u uw eindgebruikers informeren en laat uw helpdesk weten van deze wijziging. Zie het blogbericht: ondersteuning voor de foutdetails en instructies voor het maken van deze profielen opnieuw op als u meer informatie.

#### <a name="additional-information"></a>Als u meer informatie
https://aka.ms/Win10EmailProfiles

