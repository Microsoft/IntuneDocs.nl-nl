---
title: Include-bestand
description: Include-bestand
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 11/19/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: 6064fb657454106a8a7213e0bbbcecdcef765857
ms.sourcegitcommit: c7c6be3833d9a63d43f31d598b555b49b33cf5cb
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/03/2020
ms.locfileid: "76966352"
---
Deze mededelingen bevatten belangrijke informatie die u kan helpen om voorbereid te zijn op toekomstige wijzigingen en functies in Intune.

### <a name="updated-support-statement-for-adobe-acrobat-reader-for-intune-mobile-app--5746776--"></a>Bijgewerkte ondersteuningsmededeling over de mobiele app Adobe Acrobat Reader voor Intune<!--5746776-->
Eind augustus hebben we via MC188653 meegedeeld dat de mobiele app Adobe Acrobat Reader voor Intune op 1 december 2019 het eind van zijn levenscyclus heeft bereikt en dat Adobe van plan is om ondersteuning te bieden voor de app-beveiliging van Intune vanuit de belangrijkste Acrobat Reader-app. Sindsdien hebben we feedback van klanten ontvangen dat we IT-beheerders meer tijd moesten geven om zich bezig te houden met Adobe Acrobat Reader voor Intune en dat eindgebruikers meer tijd nodig hadden om zich Adobe Acrobat Reader voor Intune eigen te maken. Omdat Adobe Acrobat Reader voor Intune veel wordt gebruikt op apparaten van eindgebruikers en een belangrijke rol speelt in bedrijfsscenario's, willen we kunnen blijven garanderen dat elke ervaring voldoet aan de vereisten die uw organisatie stelt aan de bescherming van haar apps. 

Hoewel we nog steeds aanraden om uw beleid op de algemene mobiele Acrobat Reader-app toe te passen, omdat de mobiele Acrobat Reader-app beveiligingsbeleid voor apps ondersteunt en de Intune-SDK erin is geïntegreerd, wordt de Adobe Acrobat Reader voor Intune-app nog ondersteund tot en met 31 maart 2020. 

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
U ontvangt dit bericht omdat tijdens onze rapportage is gebleken dat er een of meer beleidsregels in uw organisatie zijn die zich richten op de toepassing Adobe Acrobat Reader voor Intune en/of omdat u onze vorige EOL-communicatie hebt ontvangen. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
Breng uw eindgebruikers en helpdesk op de hoogte van deze wijziging. U kunt de [functionaliteit van de bedrijfsportal voor het afhandelen van ondersteuningsinformatie](../apps/company-portal-app.md#support-information) gebruiken om een kanaal op te zetten voor het stellen en beantwoorden van vragen met betrekking tot Intune.

#### <a name="additional-information"></a>Aanvullende informatie
https://helpx.adobe.com/acrobat/kb/intune-app-end-of-life.html


### <a name="end-support-for-windows-phone-81--3544909--"></a>Ondersteuning voor Windows Phone 8.1 beëindigd<!--3544909-->
In juli 2017 is de reguliere ondersteuning van Microsoft voor Windows Phone 8.1 beëindigd en in juni 2019 de uitgebreide ondersteuning. De Bedrijfsportal-app voor Windows Phone 8.1 bevindt zich sinds oktober 2017 in de continuïteitsmodus. Microsoft Intune beëindigt nu op 20 februari 2020 de ondersteuning voor Windows Phone 8.1.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Na 20 februari 2020 ontvangen deze apparaten geen beveiligingsupdates meer en kunt u geen nieuwe apparaten meer inschrijven. Bestaande Windows Phone 8.1-apparaten blijven ingeschreven (beleid, apps en rapportage). Na de genoemde datum wordt probleemoplossing voor bestaande inschrijvingen echter niet meer ondersteund, aangezien veel onderdelen, zoals certificaten van derden, de ondersteuning voor het platform al eerder hebben beëindigd. Intune beëindigt het testen van de compatibiliteit met Intune en Windows Phone 8.1.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
Controleer uw Intune-rapporten om na te gaan voor welke apparaten of gebruikers dit gevolgen kan hebben. Ga naar Apparaten > Alle apparaten en filter op besturingssysteem. U kunt extra kolommen toevoegen, zodat u eenvoudiger kunt vaststellen wie in uw organisatie apparaten met Windows Phone 8.1 gebruikt. Vraag uw eindgebruikers om hun apparaten te upgraden naar een ondersteunde besturingssysteemversie.


### <a name="take-action-use-microsoft-edge-for-your-protected-intune-browser-experience--5728447--"></a>Onderneem actie: Gebruik Microsoft Edge als uw beveiligde Intune-browser<!--5728447-->
Zoals we al hebben gecommuniceerd in het afgelopen jaar, ondersteunt Microsoft Edge voor mobiel dezelfde beheerfuncties als Managed Browser, maar is de ervaring voor de eindgebruiker sterk verbeterd. Om plaats te maken voor de nieuwe gebruikerservaring die met Microsoft Edge wordt geboden, wordt Intune Managed Browser buiten gebruik gesteld. Vanaf 27 januari 2020 wordt Intune Managed Browser niet meer ondersteund door Intune.  

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij? 
Vanaf 1 februari 2020 is Intune Managed Browser niet meer beschikbaar in de Google Play Store of de App Store voor iOS. Vanaf dan kunt u nog steeds nieuw app-beveiligingsbeleid toepassen op Intune Managed Browser, maar kunnen nieuwe gebruikers de Intune Managed Browser-app niet meer downloaden. In iOS worden bovendien nieuwe webclips die worden gepusht naar apparaten die via MDM zijn ingeschreven, geopend in Microsoft Edge in plaats van in Intune Managed Browser.  

Op 31 maart 2020 wordt Intune Managed Browser verwijderd uit de Azure-console. Dit betekent dat u geen nieuwe beleidsregels meer kunt maken voor Intune Managed Browser. Bestaand Intune Managed Browser-beleid dat u hebt geïmplementeerd, wordt hierdoor niet beïnvloed. Intune Managed Browser wordt weergegeven in de console als een LOB-app zonder pictogram en bestaande beleidsregels worden nog steeds weergegeven als gericht op de app. Vanaf dan wordt ook de optie voor het omleiden van webinhoud naar Intune Managed Browser verwijderd uit de sectie Gegevensbescherming van App-beveiligingsbeleid.  

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging? 
Voor een soepele overgang van Intune Managed Browser naar Microsoft Edge wordt u aangeraden de volgende stappen proactief uit te voeren: 

1. Stel Microsoft Edge voor iOS en Android in als doel met app-beveiligingsbeleid (ook wel MAM genoemd) en app-configuratie-instellingen. U kunt uw Intune Managed Browser-beleid opnieuw gebruiken voor Microsoft Edge door ook die bestaande beleidsregels te richten op Microsoft Edge.  
2. Voor alle apps in uw omgeving die met MAM worden beveiligd, moet de app-beveiligingsbeleidsinstelling 'Overdracht van webinhoud met andere apps beperken' zijn ingesteld op 'Browsers die worden beheerd met beleid'. 
3. Stel het doel in van alle apps die met MAM worden beveiligd, waarbij u de configuratie-instelling 'com.microsoft.intune.useEdge' van de beheerde app instelt op true (waar). Met ingang van de release van 1911 kunt u stap 2 en stap 3 eenvoudig uitvoeren door de instelling 'Overdracht van webinhoud met andere apps beperken' te configureren voor Microsoft Edge in de sectie Gegevensbescherming van uw app-beveiligingsbeleid. 

Ondersteuning voor webclips in iOS en Android is binnenkort beschikbaar. Wanneer deze ondersteuning wordt uitgebracht, moet u het doel van bestaande webclips opnieuw instellen om ervoor te zorgen dat ze worden geopend in Microsoft Edge in plaats van in Managed Browser. 

#### <a name="additional-information"></a>Aanvullende informatie
Bekijk onze documenten over het [gebruik van Microsoft Edge met app-beveiligingsbeleid](../apps/manage-microsoft-edge.md) voor meer informatie of lees onze [blogpost over ondersteuning](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Use-Microsoft-Edge-for-your-Protected-Intune-Browser-Experience/ba-p/1004269).


### <a name="end-of-support-for-legacy-pc-management"></a>Einde van ondersteuning voor verouderd pc-beheer

Verouderd pc-beheer wordt vanaf 15 oktober 2020 niet meer ondersteund. Werk apparaten bij naar Windows 10 en registreer deze opnieuw als MDM-apparaten (Mobile Device Management) om ze door Intune te blijven laten beheren.

[Meer informatie](https://go.microsoft.com/fwlink/?linkid=2107122)

### <a name="decreasing-support-for-android-device-administrator"></a>Afgenomen ondersteuning voor Android-apparaatbeheerder 
Android-apparaatbeheerder (soms aangeduid met het verouderde Android-beheer, uitgebracht met Android 2.2) is een manier om Android-apparaten te beheren. Er is nu echter verbeterde beheerfunctionaliteit beschikbaar met [Android Enterprise](../enrollment/connect-intune-android-enterprise.md) (uitgebracht met Android 5.0). In een poging om apparaatbeheer moderner, breder en veiliger te maken, vermindert Google ondersteuning voor apparaatbeheerder in nieuwe Android-versies.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Deze wijzigingen van Google zijn op de volgende manieren van invloed op Intune-gebruikers:  
- Intune biedt slechts tot het tweede kwartaal van 2020 nog ondersteuning voor Android-apparaten met Android 10 en hoger die door apparaatbeheerder worden beheerd. Apparaten die worden beheerd met apparaatbeheerder en worden uitgevoerd met Android 10 of hoger, kunnen na dit moment niet langer volledig worden beheerd. Betrokken apparaten ontvangen met name geen nieuwe wachtwoordvereisten meer.
    - Samsung Knox-apparaten worden gedurende deze periode niet beïnvloed, omdat uitgebreide ondersteuning wordt geboden via de integratie van Intune met het Knox-platform. Dit geeft u meer tijd om af te stappen van apparaatbeheerder.    
- Android-apparaten die worden beheerd met apparaatbeheerder en worden uitgevoerd met oudere versies dan Android 10, worden niet getroffen en kunnen volledig beheerd blijven worden met apparaatbeheerder.    
- Voor alle apparaten met Android 10 of hoger heeft Google de toegang voor apparaatbeheerderagents als de Bedrijfsportal tot apparaat-id's beperkt. Nadat een apparaat naar Android 10 of hoger is bijgewerkt, heeft deze beperking gevolgen voor de volgende Intune-functies:  
    - Netwerktoegangsbeheer voor VPN werkt niet meer.   
    - Als u apparaten identificeert als 'In bedrijfseigendom' met een IMEI of serienummer, wordt het apparaat niet automatisch gemarkeerd als 'In bedrijfseigendom'.  
    - Het IMEI en serienummers zijn niet langer zichtbaar voor IT-beheerder in Intune. 
        > [!NOTE]
        > Dit heeft alleen gevolgen voor apparaten die worden beheerder met apparaatbeheerder en worden uitgevoerd met Android 10 of hoger en is niet van invloed op apparaten die worden beheerd met Android Enterprise. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
Volg de volgende aanbevelingen op om te voorkomen dat u in het derde kwartaal van 2020 te kampen hebt met beperkte functionaliteit:
- Leg geen nieuwe apparaten vast in apparaatbeheerder.
- Als bij een apparaat een update naar Android 10 wordt verwacht, migreert u deze van apparaatbeheerder naar Android Enterprise-beheer en/of app-beveiligingsbeleid.

#### <a name="additional-information"></a>Aanvullende informatie
- [Google-richtlijnen voor migratie van apparaatbeheerder naar Android Enterprise](http://static.googleusercontent.com/media/android.com/en/enterprise/static/2016/pdfs/enterprise/Android-Enterprise-Migration-Bluebook_2019.pdf)
- [Google-documentatie over het plan om de apparaatbeheerder-API af te schaffen](https://developers.google.com/android/work/device-admin-deprecation)

### <a name="plan-for-change-intune-app-sdk-and-app-protection-policies-for-android-moving-to-support-android-50-and-higher-in-an-upcoming-release---4911065---"></a>Geplande wijziging: Intune app-SDK en app-beveiligingsbeleid voor Android wordt in een volgende versie verplaatst voor ondersteuning van Android 5.0 en hoger <!--4911065 -->
Intune wordt in een volgende versie verplaatst voor ondersteuning van Android 5.x (Lollipop) en hoger. Werk alle verpakte apps bij met de nieuwste Intune App SDK en werk uw apparaten bij.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Als u niet van plan bent om de SDK of APP voor Android te gebruiken, is deze wijziging niet van invloed op u. Als u de Intune App SDK gebruikt, zorg er dan voor dat u deze bijwerkt naar de nieuwste versie en werk ook uw apparaten bij naar Android 5.x en hoger. Als u geen update uitvoert, ontvangen apps geen updates en gaat de kwaliteit van de ervaring langzaam achteruit.

Hieronder vindt u een lijst van algemene apparaten die worden geregistreerd bij Intune en die Android-versie 4.x uitvoeren. Als u een van deze apparaten hebt, voer dan de stappen uit om ervoor te zorgen dat dit apparaat Android-versie 5.0 of hoger ondersteunt, of dat het wordt vervangen door een apparaat dat Android-versie 5.0 of hoger ondersteunt. Deze lijst is niet aangevuld met alle apparaten die mogelijk opnieuw moeten worden geëvalueerd:

- Samsung SM-T561  
- Samsung SM-T365
- Samsung GT-I9195
- Samsung SM-G800F
- Samsung SM-G357FZ
- Motorola XT1080
- Samsung GT-I9305
- Samsung SM-T231

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
Verpak je apps met de nieuwste Intune App SDK. U kunt ook de voorwaardelijke startinstelling 'Minimale OS-versie vereisen (alleen waarschuwen)' instellen om eindgebruikers op persoonlijke apparaten een melding te sturen om een upgrade uit te voeren.

### <a name="intune-plan-for-change-nearing-end-of-support-for-windows-7---3042987---"></a>Intune-plan voor wijziging Het einde van ondersteuning voor Windows 7 nadert<!-- 3042987 -->
Zoals we in september 2018 in het bericht MC148476 en in maart 2019 in het bericht MC176794 hebben gemeld, bereikt Windows 7 op 14 januari 2020 het einde van de uitgebreide ondersteuning. Op dat moment wordt de ondersteuning door Intune voor apparaten met Windows 7 beëindigd, zodat we kunnen investeren in het ondersteunen van nieuwere technologieën en het bieden van fantastische nieuwe ervaringen voor eindgebruikers. Na deze datum zijn technische hulp en automatische updates ter beveiliging van uw Windows 7-pc niet langer beschikbaar via Intune. Microsoft raadt u ten zeerste aan om vóór januari 2020 over te stappen op Windows 10, om situaties te vermijden waarin u service of ondersteuning nodig hebt die niet meer beschikbaar is. Meer informatie over de levenscyclus voor Windows-ondersteuning leest u [hier](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
U ontvangt dit bericht omdat u momenteel Windows 7-pc's beheert met behulp van de verouderde Intune-software-agent voor pc's. Omdat de uitgebreide ondersteuning van Windows 7 in minder dan een jaar wordt beëindigd, raden wij uw organisatie ten zeerste aan om zo snel mogelijk een upgrade naar Windows 10 uit te voeren.  

Beheermogelijkheden voor pc's zijn rechtstreeks in het Windows 10-besturingssysteem ingebouwd, zodat u geen client-agent meer hoeft te installeren, zoals de Intune-software-client voor Windows 7. Vanaf Windows 8.1 gebruikt Microsoft architectuur voor Mobile Device Management (MDM) om Windows-pc's in te richten, te configureren, bij te werken en te beheren. Wanneer u Intune hebt ingesteld, kunt u Windows-enrollment vereenvoudigen door [Windows 10-pc's bij Intune te registreren](..\windows-enroll.md) met behulp van het MDM-kanaal. U wordt aangeraden om deze 'agentloze' MDM-beheeroplossing te gebruiken voor het beheren van uw Windows 10-pc's.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
We raden uw organisatie aan om dit actieplan onmiddellijk te overwegen:

- Plan vóór 14 januari 2020 een upgrade naar Windows 10 voor uw Windows 7-apparaten en voer deze uit.
- Lees meer over de [implementatie-ondersteuning voor Windows 10](https://docs.microsoft.com/windows/deployment/) voor meer informatie over het upgraden van uw bestaande Windows 7-pc's naar Windows 10.
- Bekijk het aanbod voor [Desktop App Assure](https://www.microsoft.com/fasttrack/microsoft-365/desktop-app-assure?rtc=1) via Fast Track voor hulp met de belofte van programmacompatibiliteit van Microsoft.
- Migreer bestaande apparaten die worden beheerd met de verouderde Intune-softwareclient naar de door Microsoft aanbevolen oplossing om Windows 10 met behulp van MDM te beheren. Registreer alle nieuwe Windows 10-pc's met behulp van MDM-beheer voor Intune in de Azure-portal.

Lees [deze blogpost](https://aka.ms/Windows7_Intune) voor meer informatie.


