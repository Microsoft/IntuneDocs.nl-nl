---
title: Include-bestand
description: Include-bestand
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 11/4/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: 3d49d31ed08683508d3d231521e578688dd21bac
ms.sourcegitcommit: 737ad6c675deedfc6009f792023ff95981b06582
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/15/2019
ms.locfileid: "74125454"
---
Deze mededelingen bevatten belangrijke informatie die u kan helpen om voorbereid te zijn op toekomstige wijzigingen en functies in Intune.

### <a name="intune-plan-for-change-windows-10-version-1703-company-portal-moving-out-of-support--5026679--"></a>Intune-plan voor wijziging: Ondersteuning voor Windows 10, versie 1703 van de bedrijfsportal komt te vervallen<!--5026679-->
Windows 10, versie 1703 (ook wel bekend als Windows 10, RS2) is buiten bedrijf gesteld op 8 oktober 2019 voor Enterprise- en EDU-edities. De Intune-bedrijfsportal-app voor RS2/RS1 wordt niet meer ondersteund vanaf 26 december 2019.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
U ziet geen nieuwe functies meer in de specifieke versie van de bedrijfsportal-app, ook al wordt deze versie van de bedrijfsportal-app nog wel ondersteund tot en met 26 december 2019 en wordt de beveiliging van de bedrijfsportal-app zo nodig nog bijgewerkt. Maar omdat de beveiliging van Windows 10, versie 1703 niet meer wordt bijgewerkt nadat de versie buiten bedrijf is gesteld, wordt u ten zeerste aangeraden uw Windows-apparaten bij te werken naar een recentere versie van Windows en de nieuwste bedrijfsportal-app te gebruiken zodat u nieuwe functies en aanvullende functionaliteit blijft ontvangen.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
Welke stappen u moet uitvoeren, is afhankelijk van de configuratie van uw omgeving. Over het algemeen moet u de apparaten met de oudere versie van het besturingssysteem en/of de bedrijfsportal identificeren en die apparaten bijwerken. Meld u aan bij Intune en ga naar Software-updates – Windows 10-update-ringen om uw Windows 10-update-ringen in te stellen. De nieuwste versie van de bedrijfsportal-app is versie 10.3.5601.0. Laat uw gebruikers deze versie downloaden uit de Microsoft Store om op de hoogte te blijven van toekomstige releases. U kunt Intune ook gebruiken om de nieuwste versie op uw Windows-apparaten te installeren via de [Microsoft Store voor Bedrijven](https://docs.microsoft.com/intune/windows-store-for-business).

#### <a name="additional-information"></a>Aanvullende informatie
[De Windows 10-bedrijfsportal-app handmatig toevoegen met Microsoft Intune](https://docs.microsoft.com/intune/store-apps-company-portal-app)


### <a name="take-action-use-microsoft-edge-for-your-protected-intune-browser-experience--5728447--"></a>Onderneem actie: Gebruik Microsoft Edge als uw beveiligde Intune-browser<!--5728447-->
Zoals we al hebben gecommuniceerd in het afgelopen jaar, ondersteunt Microsoft Edge voor mobiel dezelfde beheerfuncties als Managed Browser, maar is de ervaring voor de eindgebruiker sterk verbeterd. Om plaats te maken voor de nieuwe gebruikerservaring die met Microsoft Edge wordt geboden, wordt Intune Managed Browser buiten gebruik gesteld. Vanaf 27 januari 2020 wordt Intune Managed Browser niet meer ondersteund door Intune.  

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij? 
Vanaf 1 februari 2020 is Intune Managed Browser niet meer beschikbaar in de Google Play Store of de App Store voor iOS. Vanaf dan kunt u nog steeds nieuw app-beveiligingsbeleid toepassen op Intune Managed Browser, maar nieuwe gebruikers kunnen de Intune Managed Browser-app niet meer downloaden. In iOS worden bovendien nieuwe webclips die worden gepusht naar apparaten die via MDM zijn ingeschreven, geopend in Microsoft Edge in plaats van in Intune Managed Browser.  

Op 31 maart 2020 wordt Intune Managed Browser verwijderd uit de Azure-console. Dit betekent dat u geen nieuwe beleidsregels meer kunt maken voor Intune Managed Browser. Bestaand Intune Managed Browser-beleid dat u hebt geïmplementeerd, wordt hierdoor niet beïnvloed. Intune Managed Browser wordt weergegeven in de console als een LOB-app zonder pictogram en bestaande beleidsregels worden nog steeds weergegeven als gericht op de app. Vanaf dan wordt ook de optie voor het omleiden van webinhoud naar Intune Managed Browser verwijderd uit de sectie Gegevensbescherming van App-beveiligingsbeleid.  

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging? 
Voor een soepele overgang van Intune Managed Browser naar Microsoft Edge wordt u aangeraden de volgende stappen proactief uit te voeren: 

1. Stel Microsoft Edge voor iOS en Android in als doel met app-beveiligingsbeleid (ook wel MAM genoemd) en app-configuratie-instellingen. U kunt uw Intune Managed Browser-beleid opnieuw gebruiken voor Microsoft Edge door ook die bestaande beleidsregels te richten op Microsoft Edge.  
2. Voor alle apps in uw omgeving die met MAM worden beveiligd, moet de app-beveiligingsbeleidsinstelling 'Overdracht van webinhoud met andere apps beperken' zijn ingesteld op 'Browsers die worden beheerd met beleid'. 
3. Stel het doel in van alle apps die met MAM worden beveiligd, waarbij u de configuratie-instelling 'com.microsoft.intune.useEdge' van de beheerde app instelt op true (waar). Met ingang van de release van 1911 kunt u stap 2 en stap 3 eenvoudig uitvoeren door de instelling 'Overdracht van webinhoud met andere apps beperken' te configureren voor Microsoft Edge in de sectie Gegevensbescherming van uw app-beveiligingsbeleid. 

Ondersteuning voor webclips in iOS en Android is binnenkort beschikbaar. Wanneer deze ondersteuning wordt uitgebracht, moet u het doel van bestaande webclips opnieuw instellen om ervoor te zorgen dat ze worden geopend in Microsoft Edge in plaats van in Managed Browser. 

#### <a name="additional-information"></a>Aanvullende informatie
Ga naar onze documenten over het [gebruik van Microsoft Edge met app-beveiligingsbeleid](../apps/manage-microsoft-edge.md) voor meer informatie of bekijk onze [blogpost over ondersteuning](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Use-Microsoft-Edge-for-your-Protected-Intune-Browser-Experience/ba-p/1004269).


### <a name="plan-for-change-updated-experience-when-enrolling-android-enterprise-dedicated-devices-in-intune--5198878--"></a>Geplande wijziging: Nieuwe ervaring bij het inschrijven van toegewezen Android Enterprise-apparaten in Intune<!--5198878-->
Met de release van Intune in november (1911) voegen we ondersteuning voor de implementatie van SCEP-apparaatcertificaten toe aan toegewezen Android Enterprise-apparaten om op certificaten gebaseerde toegang tot Wi-Fi-profielen mogelijk te maken. Deze verandering brengt ook enkele kleine wijzigingen met zich mee in de stroom bij het inschrijven van toegewezen Android Enterprise-apparaten.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Als u toegewezen Android Enterprise-apparaten in uw omgeving beheert, zult u in november enkele veranderingen gaan zien.

- Nieuwe inschrijvingen van toegewezen Android Enterprise-apparaten: Eindgebruikers zien een andere reeks stappen op apparaten bij het inschrijven. De inschrijving start nog steeds zoals vandaag (met QR, NFC, Zero-touch of apparaat-id), maar na de servicerelease van november volgt er een verplichte stap voor app-installatie.
- Voor bestaande Android-apparaten die zijn ingeschreven als toegewezen apparaten: Intune start met het automatisch installeren van de Microsoft Intune-app op apparaten vanaf begin november. U hoeft niets te doen. De app wordt automatisch gedownload en geïnstalleerd op apparaten. 

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Wat kan ik doen om me voor te bereiden op deze wijziging?
Maak plannen voor het bijwerken van uw eindgebruikersbegeleiding en stel uw helpdesk op de hoogte van deze wijziging. Klik op Aanvullende informatie voor meer details en screenshots. De pagina Wat is er nieuw wordt bijgewerkt zodra het uitrollen van deze wijziging begint.

#### <a name="additional-information"></a>Aanvullende informatie
[https://aka.ms/Dedicated_devices_enrollment](https://aka.ms/Dedicated_devices_enrollment)

### <a name="plan-for-change-the-server-side-logging-for-siri-commands-setting-will-be-removed-from-the-intune-console----5468501--"></a>Geplande wijziging: De instelling 'Logboekregistratie op de server voor Siri-opdrachten' wordt verwijderd van de Intune-console <!-- 5468501-->

We zijn van plan om de instelling 'Logboekregistratie op de server voor Siri-opdrachten' uit de Intune-console te verwijderen met de update voor de Intune-service in november. Deze wijziging sluit aan bij het feit dat Apple de instelling aan hun kant al heeft verwijderd.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Nadat de update van november of 1911 medio november is uitgevoerd, zult u zien dat deze instelling in de Intune-console is verwijderd uit het menu Apparaatbeperkingen (Ingebouwde apps) voor iOS-configuratieprofielen. De instelling is mogelijk nog zichtbaar in uw beleid en het beheersprofiel van het doelapparaat, maar heeft geen effect op uw apparaat. We verwachten niet veel impact op de functionaliteit, omdat de instelling momenteel niet werkt op apparaten, ook al is deze zichtbaar in het managementprofiel.

U kunt kiezen uit twee paden:
- Als u deze instelling uit uw beleid wilt verwijderen, kunt u naar het profiel met de instelling gaan, een kleine bewerking uitvoeren en het beleid opslaan. Het beleid zal in de backend opnieuw worden berekend en de instelling zal uit uw beleid worden verwijderd.
- Als u ervoor kiest om deze actie niet uit te voeren, zullen eindgebruikers deze instelling nog wel zien in het beheerprofiel van hun apparaat, maar de instelling zal geen effect hebben.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Wat kan ik doen om me voor te bereiden op deze wijziging?
U kunt bovenstaande stappen ondernemen of uw beleid laten zoals het is. We zullen onze 'Wat is er nieuw'-pagina en documentatie bijwerken wanneer deze wijziging wordt doorgevoerd.

### <a name="end-of-support-for-legacy-pc-management"></a>Einde van ondersteuning voor verouderd pc-beheer

Verouderd pc-beheer wordt vanaf 15 oktober 2020 niet meer ondersteund. Werk apparaten bij naar Windows 10 en schrijf deze opnieuw in als MDM-apparaten om ze door Intune te blijven laten beheren.

[Meer informatie](https://go.microsoft.com/fwlink/?linkid=2107122)

### <a name="decreasing-support-for-android-device-administrator"></a>Afgenomen ondersteuning voor Android-apparaatbeheerder 
Android-apparaatbeheerder (soms aangeduid met het verouderde Android-beheer, uitgebracht met Android 2.2) is een manier om Android-apparaten te beheren. Er is nu echter verbeterde beheerfunctionaliteit beschikbaar met [Android Enterprise](../enrollment/connect-intune-android-enterprise.md) (uitgebracht met Android 5.0). In een poging om apparaatbeheer moderner, breder en veiliger te maken, vermindert Google ondersteuning voor apparaatbeheerder in nieuwe Android-versies.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Deze wijzigingen van Google zijn op de volgende manieren van invloed op Intune-gebruikers:  
- Tot de zomer van 2020 biedt Intune alleen nog maar ondersteuning voor Android-apparaten met Android 10 (ook bekend als Android Q) en hoger die door apparaatbeheerder worden beheerd. Deze datum is wanneer de volgende primaire versie van Android wordt verwacht.   
- Apparaten die worden beheerd met apparaatbeheerder en worden uitgevoerd met Android 10 of hoger, kunnen na de zomer van 2020 niet langer volledig worden beheerd.       
- Android-apparaten die worden beheerd met apparaatbeheerder en worden uitgevoerd met oudere versies dan Android 10, worden niet getroffen en kunnen volledig beheerd blijven worden met apparaatbeheerder.    
- Voor alle apparaten met Android 10 of hoger heeft Google de toegang voor apparaatbeheerderagents als de Bedrijfsportal tot apparaat-id's beperkt. Nadat een apparaat wordt bijgewerkt naar Android 10 of hoger, heeft dit gevolgen voor de volgende Intune-functies:  
    - Netwerktoegangsbeheer voor VPN werkt niet meer.   
    - Als u apparaten identificeert als 'In bedrijfseigendom' met een IMEI of serienummer, wordt het apparaat niet automatisch gemarkeerd als 'In bedrijfseigendom'.  
    - Het IMEI en serienummers zijn niet langer zichtbaar voor IT-beheerder in Intune. 
        > [!NOTE]
        > Dit heeft alleen gevolgen voor apparaten die worden beheerder met apparaatbeheerder en worden uitgevoerd met Android 10 of hoger en is niet van invloed op apparaten die worden beheerd met Android Enterprise. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
We raden u het volgende aan om te voorkomen dat u in de zomer van 2020 te kampen heeft met beperkte functionaliteit:
- Leg geen nieuwe apparaten vast in apparaatbeheerder.
- Als bij een apparaat een update naar Android 10 wordt verwacht, migreert u deze van apparaatbeheerder naar Android Enterprise-beheer en/of app-beveiligingsbeleid.

#### <a name="additional-information"></a>Aanvullende informatie
- [Google-richtlijnen voor migratie van apparaatbeheerder naar Android Enterprise](http://static.googleusercontent.com/media/android.com/en/enterprise/static/2016/pdfs/enterprise/Android-Enterprise-Migration-Bluebook_2019.pdf)
- [Google-documentatie over het plan om de apparaatbeheerder-API af te schaffen](https://developers.google.com/android/work/device-admin-deprecation)

### <a name="update-your-android-company-portal-app-to-the-latest-version---4536963--"></a>Android-bedrijfsportal-app bijwerken naar de nieuwste versie <!--4536963-->
Er worden regelmatig updates van Intune gepubliceerd voor de Android-versie van de bedrijfsportal-app. In november 2018 hebben we een update voor de bedrijfsportal gepubliceerd, met onder andere een schakeloptie voor de back-end om u voor te bereiden op de wijziging van Google waarbij ze hun bestaande meldingenplatform gaan overzetten naar Firebase Cloud Messaging (FCM) van Google. Als Google zijn bestaande meldingenplatform uit de lucht haalt en overstapt naar FCM, moeten eindgebruikers hun bedrijfsportal-app hebben bijgewerkt naar ten minste de versie van november 2018 om te kunnen blijven communiceren met de Google Play Store.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Onze telemetrie geeft aan dat u apparaten hebt met een versie van de bedrijfsportal-app die ouder is dan 5.0.4269.0. Als niet deze versie of hoger van de bedrijfsportal-app is geïnstalleerd, bestaat de kans dat door IT-personeel gestarte apparaatacties, zoals wissen, wachtwoord opnieuw instellen, beschikbare en vereiste app-installaties, en certificaatinschrijving, niet werken zoals verwacht. Als uw apparaten via een MDM zijn geregistreerd bij Intune, kunt u de versies en gebruikers van de bedrijfsportal zien door naar Client-apps – Gedetecteerde apps te gaan. Selecteer een eerdere versie van de bedrijfsportal-app om te zien welke gebruikers de apparaten hebben waarop de bedrijfsportal-app niet is bijgewerkt.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
Vraag eindgebruikers van Android-apparaten die niet up-to-date zijn om de bedrijfsportal-app bij te werken via de Google Play Store. Informeer de helpdesk voor het geval een gebruiker niet voor het automatisch bijwerken van de bedrijfsportal-app heeft gekozen. Volg de koppeling bij *Aanvullende informatie* voor meer informatie over het FCM-platform van Google en de aanstaande wijziging.

#### <a name="additional-information"></a>Aanvullende informatie
https://firebase.google.com/docs/cloud-messaging/


### <a name="new-full-screen-experience-coming-to-intune---4593669--"></a>Er komt een nieuwe ervaring voor volledig scherm naar Intune <!--4593669-->
We brengen bijgewerkte gebruikersinterfaces voor maken en bewerken uit in Intune in de Azure-portal. Deze nieuwe ervaring vereenvoudigt de bestaande werkstromen door een wizardachtige indeling te gebruiken die op één blade is samengevoegd. Deze update zorgt ervoor dat er minder blades of werkstromen voor maken en bewerken zijn waarbij u in verschillende blades ver moet doorklikken. De werkstromen voor maken worden ook bijgewerkt, want Toewijzingen wordt toegevoegd (behalve app-toewijzing).

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
De ervaring wordt in de komende maanden uitgebracht voor Intune via portal.azure.com en devicemanagement.microsoft.com. Deze update voor de gebruikersinterface is niet van invloed op de functionaliteit van uw bestaande beleid en profielen, maar u ziet een licht aangepaste werkstroom. Wanneer u bijvoorbeeld nieuw beleid maakt, kunt u toewijzingen instellen als onderdeel van deze stroom, in plaats van dat te doen nadat u het beleid hebt gemaakt. Bekijk de blogpost bij *Aanvullende informatie* voor schermopnames van hoe de nieuwe ervaring er in de console uitziet.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Wat kan ik doen om me voor te bereiden op deze wijziging?
U hoeft geen actie meer te ondernemen, maar u kunt overwegen uw IT-begeleiding bij te werken, indien nodig. We werken onze documentatie bij wanneer deze ervaring wordt uitgebracht in verschillende blades in Intune in de Azure-portal.

#### <a name="additional-information"></a>Aanvullende informatie 
https://aka.ms/intune_fullscreen

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

Raadpleeg [dit blogbericht](https://aka.ms/Windows7_Intune) voor meer informatie.
