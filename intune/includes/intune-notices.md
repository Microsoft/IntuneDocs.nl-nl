---
ms.openlocfilehash: dc86f2c22410236368753acd4dd3b66698037241
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57736849"
---

Deze berichten bevatten belangrijke informatie waarmee u kunt voorbereiden op toekomstige Intune wijzigingen en functies. 

### <a name="change-in-enrollment-workflow-with-intune-company-portal-on-corporate-ios-devices-authenticating-with-setup-assistant----1927359---"></a>Wijziging in de werkstroom van de inschrijving met Intune-bedrijfsportal op zakelijke iOS-apparaten verifiëren met Configuratieassistent <!-- 1927359 -->
Er is een toekomstige wijzigingen in de werkstroom voor het inschrijven van iOS-apparaten via een van de Apple bedrijfsapparaten registratiemethoden - Apple Configurator, Apple Business Manager, Apple School Manager of het Apple Device Enrollment Program (DEP) van bij het gebruik van Setup Assistant voor verificatie. Deze wijziging geldt alleen voor apparaten die zijn ingeschreven met gebruikersaffiniteit.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Wanneer deze wijziging in ~~maart~~ april wordt uitgerold, worden inschrijvingsprofielen in Intune in Azure Portal bijgewerkt zodat u kunt opgeven hoe apparaten zich verifiëren en hoe zij de bedrijfsportal-app ontvangen. Er is een verbeterde werkstroom voor iOS-apparaten inschrijven via de hierboven genoemde methoden. Opmerking:

- Wanneer nieuwe apparaten inschrijven en verificatie met Configuratieassistent, u zult kunnen kiezen of u de bedrijfsportal-app automatisch te implementeren. Eindgebruikers wordt niet meer zien het scherm 'Uw apparaat identificeren' en het scherm 'Bevestig uw apparaat' in de stroom voor inschrijving.  
- Op apparaten die al zijn ingeschreven via Configuratieassistent via een van de Apple bedrijfsapparaten registratiemethoden, moet u actie ondernemen als u wilt inschakelen van voorwaardelijke toegang. Hebt u een configuratiebeleid voor apps configureren met een specifieke xml in de bedrijfsportal-App omlaag naar deze apparaten te pushen. Er zijn instructies om dit te doen in het blogbericht: op de koppeling meer informatie. Als u ervoor kiest om de bedrijfsportal-App op deze manier, zien eindgebruikers niet meer het scherm 'Uw apparaat identificeren' en het scherm 'Bevestig uw apparaat' in de stroom voor inschrijving. 
- Nadat deze wijziging wordt geïmplementeerd, als u de bedrijfsportal-App met hebt geïmplementeerd er het app-configuratieprofiel hierboven genoemde en als ze, maar eindgebruikers kunnen downloaden van de bedrijfsportal-app vanuit de App store en ze kunt u zich aanmeldt, wordt een foutbericht weergegeven. Ze niet mogelijk de app voor voorwaardelijke toegang gebruiken. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
Als u van plan bent over het gebruik van de werkstroom gewijzigd, moet u de richtlijnen van uw eindgebruikers om aan te geven die bijwerken:

- Eindgebruikers kunnen zichtbaar de twee schermen hierboven vermeld in de stroom voor inschrijving niet meer. 
- Ze moet zich aanmelden bij de bedrijfsportal-App wanneer deze automatisch wordt geïmplementeerd en niet uit de appstore te downloaden. 

U kunt nu een app-configuratiebeleid maken indien nodig, ter voorbereiding op deze wijziging. Wanneer deze nieuwe werkstroom zichtbare ziet u bijgewerkte inschrijvingsprofielen in de console. We u ook kennis van deze implementatie via het berichtencentrum. Hierna moet u de actie ondernemen, zodat uw eindgebruikers door te verifiëren met Configuratieassistent via DEP inschrijven en kunt u bedrijfsportal-App voor voorwaardelijke toegang kunt.

Zie onze blogbericht ondersteuning op de koppeling meer informatie voor meer informatie over deze wijziging.

#### <a name="additional-information"></a>Als u meer informatie 
[https://aka.ms/enrollment_setup_assistant](https://aka.ms/enrollment_setup_assistant)


### <a name="company-portal-changes-for-ios-122-enrollment-in-intune"></a>Portal wijzigingen in de bedrijfsportal voor iOS 12.2-inschrijving in Intune
We hebben in MC172534 meegedeeld dat Apple een aantal wijzigingen heeft aangekondigd met betrekking tot iOS-apparaten die bij MDM-services (Mobile Device Management) worden geregistreerd. De wijziging is waarschijnlijk zichtbaar in de release van iOS in maart 2019 zit te komen, evenals alle toekomstige iOS-versies. We doorvoeren sommige updates in de bedrijfsportal-App in overeenstemming met de Apple-wijzigingen. 
 
#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Als uw gebruikers hun apparaten naar iOS 12.2 en hoger upgraden, weet u dat er een gewijzigde werkstroom en ze aanvullende maatregelen ingeschreven bij Intune nemen moeten. Na de update van maart aan Intune is dit wat ze doen:  

- Beginnen met het inschrijvingsproces in de bedrijfsportal-app voor het downloaden van een beheerprofiel
- Ga naar Instellingen > Algemeen > profielen en zoeken naar een rode badge-melding
- Selecteer het juiste profiel en klik door voor installatie
- Ga terug naar de bedrijfsportal-App-registratie moet voltooien

Klik op aanvullende informatie voor gedetailleerde informatie over de registratie-stroom.

Tenzij ze worden uitgeschreven en moeten een nieuwe inschrijving, apparaten die al ingeschreven en een upgrade uitvoeren naar iOS 12.2 zijn en hoger mag niet worden beïnvloed. De registratie-ervaring op apparaten met iOS 12.1 of eerder wordt niet veranderd met deze nieuwe release van Apple. Apparaten zijn ingeschreven via een of van Apple bedrijfsinschrijving methoden (Device Enrollment Program, Apple School Manager of Apple Business Manager) niet van invloed op.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Wat kan ik doen om me voor te bereiden op deze wijziging?
Plan de upgrade van uw documentatie en de richtlijnen voor uw eindgebruikers. Informeer uw helpdesk over deze wijzigingen. Wij houden u op de hoogte via onze pagina Wat is er nieuw wanneer deze wijziging live meteen. 

Als u profiteren van de bedrijfsportal-App-wijzigingen die we introduceren wilt, vraagt u uw eindgebruikers hun apparaat naar de nieuwe iOS-versie bijwerken nadat de update van maart naar de Intune-service wanneer Company Portal app-versie 3.9.0. Er wordt uitgebracht.

Klik op aanvullende informatie voor een blogbericht ondersteuning met schermafbeeldingen van de Preview-versie van de bedrijfsportal-App-wijzigingen.

Extra informatie[https://aka.ms/CP_changes_iOS12](https://aka.ms/CP_changes_iOS12)

### <a name="plan-for-change-workflow-changes-for-ios-12-enrollment-in-intune"></a>Plannen voor wijziging: werkstroom gewijzigd voor iOS-12-inschrijving in Intune
Apple heeft een aantal wijzigingen aangekondigd met betrekking tot iOS-apparaten die bij MDM-services (Mobile Device Management) worden geregistreerd. De wijziging zal waarschijnlijk worden doorgevoerd bij de iOS-release in het voorjaar van 2019, alsmede bij alle toekomstige iOS-releases.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Als uw eindgebruikers hun apparaten in het voorjaar bijwerken naar deze nieuwe versie van iOS 12, moet u zich ervan bewust zijn dat er een aangepaste workflow is en dat ze extra stappen moeten uitvoeren om hun registratie bij Intune te voltooien. Bij Apple deze wijzigingen introduceert, wordt eindgebruikers te hebben:

- Beginnen met het inschrijvingsproces in de bedrijfsportal-app voor het downloaden van een beheerprofiel
- Ga naar Instellingen > Algemeen > profielen
- Selecteer het juiste profiel en klik door voor installatie
- Ga terug naar de bedrijfsportal-App-registratie moet voltooien 

Op apparaten die al zijn geregistreerd en naar de nieuwe iOS-release zijn geüpgraded, heeft deze wijziging geen invloed, tenzij de registratie van deze apparaten ongedaan wordt gemaakt en ze opnieuw moeten worden geregistreerd.

De registratie-ervaring op apparaten met iOS 12.1 of eerder wordt niet veranderd met deze nieuwe release van Apple.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Wat kan ik doen om me voor te bereiden op deze wijziging?
Plan de upgrade van uw documentatie en de richtlijnen voor uw eindgebruikers. Informeer uw helpdesk over deze wijzigingen. We houden u op de hoogte via het Berichtencentrum en onze pagina Wat is er nieuw wanneer deze wijziging beschikbaar is.

#### <a name="additional-information"></a>Als u meer informatie
[Ondersteuning voor blogbericht met schermafbeeldingen en video van de stroom verwachte inschrijving](https://aka.ms/iOS_enrollment_changes).

### <a name="plan-for-change-user-experience-update-to-intune-company-portal-app-for-ios"></a>Geplande wijziging: update van de gebruikerservaring voor de iOS-bedrijfsportal-app van Intune
Met trots kunnen we mededelen dat Intune binnenkort een geheel nieuwe gebruikerservaring biedt voor de iOS-bedrijfsportal-app. De startpagina is qua vormgeving geheel vernieuwd en bevat geavanceerde filters en snellere toegang tot apps en boeken.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Deze update behoudt de functionaliteit van de huidige iOS-bedrijfsportal en biedt daarnaast de volgende nieuwe functies:
- Een startpagina met het uiterlijk van iOS 
- De mogelijkheid om te filteren op inhoud en zoekresultaten, de mogelijkheid om te filteren op het type inhoud (apps of eBooks) en beschikbaarheid (hiervoor is apparaatbeheer vereist; of beschikbaar zonder inschrijving)
- Mogelijkheid om te zoeken naar eBooks
- Zoekgeschiedenis voor apps en e-Books

Als u meedoet aan het TestFlight-programma van Apple, krijgt u een melding zodra de voorlopige versie van de bijgewerkte iOS-bedrijfsportal-app van Intune beschikbaar is. Als u niet meedoet aan het TestFlight-programma van Apple, kunt u zich hiervoor alsnog aanmelden. Als u zich aanmeldt, kunt u de bijgewerkte bedrijfsportal-app gebruiken voordat deze beschikbaar is voor uw eindgebruikers. U zult kunnen ook feedback rechtstreeks naar de Intune-team.  

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Wat kan ik doen om me voor te bereiden op deze wijziging?
U hoeft geen actie te ondernemen; deze wijzigingen zullen worden doorgevoerd in een nieuwe versie van de iOS-bedrijfsportal-app. 

#### <a name="additional-information"></a>Als u meer informatie
[https://aka.ms/cp_update_iOS](https://aka.ms/cp_update_iOS)


### <a name="reminder-removal-of-existing-exchange-online-to-intune-connectors----3105122---"></a>Herinnering: Verwijderen van bestaande Exchange met Online-connectors van Intune <!-- 3105122 -->
In MC165575 bekendgemaakt dat we zouden worden verwijderen van de Exchange Online in Intune 'Services' connector-functionaliteit in een toekomstige update. Met de update van februari naar de Intune-service, schakelen we uit de knop voor het instellen van nieuwe connectors. Wij van plan bent te verwijderen van alle bestaande Exchange Online-connectors van Intune in maart 2019.
 
#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
U ontvangt dit bericht omdat u volgens onze registratie de service-to-service-connector mogelijk in uw omgeving gebruikt. De service-to-service-connector ondersteunt Intune-beheer van Exchange Active Sync Only-apparaten voor Exchange Online en ondersteunt geen on-premises infrastructuur. Vanwege de weergave van de console lijkt het alsof deze connector nodig is voor voorwaardelijke toegang, terwijl dat niet zo is. U mogelijk al gebruikt deze connector om te begrijpen van het gebruik van Exchange Online voordat u voorwaardelijke toegang toepast. Deze informatie wordt al verstrekt door de Microsoft 365-beheercentrum. Hier vindt u hier gebruiksrapporten voor Exchange Online, met inbegrip van de app wordt gebruikt voor tussen 7 en 180 dagen. Zie voor meer informatie [Office 365-rapporten in het beheercentrum - gebruik van de E-mail-apps](https://docs.microsoft.com/office365/admin/activity-reports/email-apps-usage?view=o365-worldwide).  
 
Als u deze connector gebruikt in uw omgeving, kunt u Exchange Active Sync Only-apparaten in Intune niet bewaken of wissen nadat de connectors in februari zijn uitgeschakeld. Er worden tijdens deze wijzigingen geen gevolgen verwacht voor uw eindgebruikers.
 
#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Wat kan ik doen om me voor te bereiden op deze wijziging?
Als u de service-to-service-connector hebt ingesteld en Exchange Active Sync Only-apparaten hebt, schakelt u over naar andere methoden om uw apparaten te beheren. U hebt de volgende opties:

- Apparaten registreren in Mobile Device Management (MDM) 
- Beleid voor Intune-app-beveiliging gebruiken om uw apparaten te beheren 
- Exchange-besturingselementen gebruiken zoals wordt beschreven in [deze](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/clients-and-mobile-in-exchange-online) documentatie 

#### <a name="additional-information"></a>Als u meer informatie  
https://docs.microsoft.com/intune/exchange-service-connector-configure




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
