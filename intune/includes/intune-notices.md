---
title: Include-bestand
description: Include-bestand
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: 041f37e56e85b0ac26a4dd7a9dbbdb49bc0ebd9e
ms.sourcegitcommit: 1494ff4b33c13a87f20e0f3315da79a3567db96e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/20/2019
ms.locfileid: "71166329"
---
Deze mededelingen bevatten belangrijke informatie die u kan helpen om voorbereid te zijn op toekomstige wijzigingen en functies in Intune. 


### <a name="decreasing-support-for-android-device-administrator"></a>Afgenomen ondersteuning voor Android-apparaatbeheerder 
Android-apparaatbeheerder (soms aangeduid met het verouderde Android-beheer, uitgebracht met Android 2.2) is een manier om Android-apparaten te beheren. Er is nu echter verbeterde beheerfunctionaliteit beschikbaar met [Android Enterprise](../connect-intune-android-enterprise.md) (uitgebracht met Android 5.0). In een poging om apparaatbeheer moderner, breder en veiliger te maken, vermindert Google ondersteuning voor apparaatbeheerder in nieuwe Android-versies.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Deze wijzigingen van Google zijn op de volgende manieren van invloed op Intune-gebruikers: 
- Tot de zomer van 2020 biedt Intune alleen nog maar ondersteuning voor Android-apparaten met Android 10 (ook bekend als Android Q) en hoger die door apparaatbeheerder worden beheerd. Deze datum is wanneer de volgende primaire versie van Android wordt verwacht.  
- Apparaten die worden beheerd met apparaatbeheerder en worden uitgevoerd met Android 10 of hoger, kunnen na de zomer van 2020 niet langer volledig worden beheerd.    
- Android-apparaten die worden beheerd met apparaatbeheerder en worden uitgevoerd met oudere versies dan Android 10, worden niet getroffen en kunnen volledig beheerd blijven worden met apparaatbeheerder.  
- Voor alle apparaten met Android 10 of hoger heeft Google de toegang voor apparaatbeheerderagents als de Bedrijfsportal tot apparaat-id's beperkt. Nadat een apparaat wordt bijgewerkt naar Android 10 of hoger, heeft dit gevolgen voor de volgende Intune-functies: 
    - Netwerktoegangsbeheer voor VPN werkt niet meer.  
    - Als u apparaten identificeert als 'In bedrijfseigendom' met een IMEI of serienummer, wordt het apparaat niet automatisch gemarkeerd als 'In bedrijfseigendom'. 
    - IMEI en serienummers zijn niet langer zichtbaar voor IT-beheerder in Intune. 
        > [!Note]
        > Dit heeft alleen gevolgen voor apparaten die worden beheerder met apparaatbeheerder en worden uitgevoerd met Android 10 of hoger en is niet van invloed op apparaten die worden beheerd met Android Enterprise. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
We raden u het volgende aan om te voorkomen dat u in de zomer van 2020 te kampen heeft met beperkte functionaliteit:
- Leg geen nieuwe apparaten vast in apparaatbeheerder.
- Als bij een apparaat een update naar Android 10 wordt verwacht, migreert u deze van apparaatbeheerder naar Android Enterprise-beheer en/of app-beveiligingsbeleid.

#### <a name="additional-information"></a>Aanvullende informatie
- [Google-richtlijnen voor migratie van apparaatbeheerder naar Android Enterprise](http://static.googleusercontent.com/media/android.com/en/enterprise/static/2016/pdfs/enterprise/Android-Enterprise-Migration-Bluebook_2019.pdf)
- [Google-documentatie over het plan om de apparaatbeheerder-API af te schaffen](https://developers.google.com/android/work/device-admin-deprecation)

### <a name="update-your-android-company-portal-app-to-the-latest-version---4536963--"></a>Android-bedrijfsportal-app bijwerken naar de nieuwste versie <!--4536963-->
Er worden regelmatig updates van Intune gepubliceerd voor de Android-versie van de bedrijfsportal-app. In november 2018 hebben we een update voor de bedrijfsportal gepubliceerd, met onder andere een schakeloptie voor de back-end om u voor te bereiden op de wijziging van Google waarbij ze hun bestaande meldingenplatform gaan overzetten naar Firebase Cloud Messaging (FCM) van Google. Als Google hun bestaande meldingenplatform uit de lucht haalt en overstapt naar FCM, moeten eindgebruikers hun bedrijfsportal-app hebben bijgewerkt naar ten minste de versie van november 2018 om te kunnen blijven communiceren met de Google Play Store.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Onze telemetrie geeft aan dat u apparaten hebt met een versie van de bedrijfsportal-app die ouder is dan 5.0.4269.0. Als niet deze versie of hoger van de bedrijfsportal-app is geïnstalleerd, bestaat de kans dat door IT-personeel gestarte apparaatacties, zoals wissen, wachtwoord opnieuw instellen, beschikbare en vereiste app-installaties, en certificaatinschrijving, niet werken zoals verwacht. Als uw apparaten via een MDM zijn geregistreerd bij Intune, kunt u de versies en gebruikers van de bedrijfsportal zien door naar Client-apps – Gedetecteerde apps te gaan. Selecteer een eerdere versie van de bedrijfsportal-app om te zien welke gebruikers de apparaten hebben waarop de bedrijfsportal-app niet is bijgewerkt.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
Vraag eindgebruikers van Android-apparaten die niet up-to-date zijn om de bedrijfsportal-app bij te werken via de Google Play Store. Informeer de helpdesk voor het geval een gebruiker niet voor het automatisch bijwerken van de bedrijfsportal-app heeft gekozen. Volg de koppeling bij Aanvullende informatie voor meer informatie over het FCM-platform van Google en de aanstaande wijziging.

#### <a name="additional-information"></a>Aanvullende informatie
https://firebase.google.com/docs/cloud-messaging/


### <a name="new-fullscreen-experience-coming-to-intune---4593669--"></a>Er komt een nieuwe ervaring voor volledig scherm naar Intune <!--4593669-->
We brengen bijgewerkte gebruikersinterfaces voor maken en bewerken uit in Intune in de Azure-portal. Deze nieuwe ervaring vereenvoudigt de bestaande werkstromen door een wizardachtige indeling te gebruiken die op één blade is samengevoegd. Deze update zorgt ervoor dat er minder blades of werkstromen voor maken en bewerken zijn waarbij u in verschillende blades ver moet doorklikken. De werkstromen voor maken worden ook bijgewerkt, want Toewijzingen wordt toegevoegd (behalve app-toewijzing).

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
De ervaring wordt in de komende maanden uitgebracht voor Intune via portal.azure.com en devicemanagement.microsoft.com. Deze update voor de gebruikersinterface is niet van invloed op de functionaliteit van uw bestaande beleid en profielen, maar u ziet een licht aangepaste werkstroom. Wanneer u bijvoorbeeld nieuw beleid maakt, kunt u toewijzingen instellen als onderdeel van deze stroom, in plaats van dat te doen nadat u het beleid hebt gemaakt. Bekijk de blogpost bij Aanvullende informatie voor schermopnames van hoe de nieuwe ervaring er in de console uitziet.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Wat kan ik doen om me voor te bereiden op deze wijziging?
U hoeft geen actie meer te ondernemen, maar u kunt overwegen uw IT-begeleiding bij te werken, indien nodig. We werken onze documentatie bij wanneer deze ervaring wordt uitgebracht in verschillende blades in Intune in de Azure-portal.

#### <a name="additional-information"></a>Aanvullende informatie 
https://aka.ms/intune_fullscreen

### <a name="plan-for-change-intune-moving-to-support-ios-11-and-higher-in-september----4665324--"></a>Geplande wijziging: Intune zal vanaf september iOS 11 en hoger ondersteunen <!-- 4665324-->
We verwachten dat iOS 13 in september wordt uitgebracht door Apple. Kort na de release van iOS 13 zullen Intune-inschrijving, de bedrijfsportal en de beheerde browser ondersteuning bieden voor iOS 11 en hoger.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Onder voorwaarde dat de mobiele Office 365-apps worden ondersteund in iOS 11.0 en hoger, heeft dit mogelijk geen gevolgen voor u omdat u waarschijnlijk het besturingssysteem of de apparaten al hebt geüpgraded. Als u echter over een van de hieronder vermelde apparaten beschikt of als u een van de hieronder vermelde apparaten wilt inschrijven, moet u er rekening mee houden dat de onderstaande apparaten alleen iOS 10 en eerdere versies ondersteunen. Deze apparaten moeten worden geüpgraded naar een apparaat dat ondersteuning biedt voor iOS 11 of hoger:

- iPhone 5
- iPhone 5c
- iPad (4e generatie)

Als u Application Protection Policies (APP) gebruikt, kunt u ook de toegangsinstelling 'Minimumversie van het iOS-besturingssysteem vereisen (alleen waarschuwing)' instellen.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
Controleer uw Intune-rapporten om te zien voor welke apparaten of gebruikers dit gevolgen kan hebben. Ga naar **Apparaten** > **Alle apparaten** en filter op besturingssysteem. U kunt extra kolommen toevoegen, zodat u eenvoudiger kunt vaststellen wie in uw organisatie apparaten met iOS 10 gebruikt. Verzoek uw eindgebruikers om vóór september hun apparaten te upgraden naar een ondersteunde besturingssysteemversie.

### <a name="plan-for-change-support-for-version-811-and-higher-of-intune-app-sdk-for-ios----3586942--"></a>Geplande wijziging: Ondersteuning voor versie 8.1.1 en hoger van de Intune App SDK voor iOS <!-- 3586942-->
Vanaf september 2019 biedt Intune ondersteuning voor iOS-apps met Intune App SDK 8.1.1 en hoger. Apps die zijn gemaakt met SDK-versies lager dan 8.1.1 worden niet meer ondersteund. Deze wijziging wordt van kracht met de Apple-release van iOS 13, die rond september wordt verwacht en ook is aangekondigd in MC181399.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Met de integratie van de Intune App SDK of App Wrapping kunt u bedrijfsgegevens via gegevensversleuteling beveiligen tegen niet-goedgekeurde toepassingen en gebruikers. De Intune App SDK voor iOS gebruikt standaard 256-bits versleutelingssleutels wanneer versleuteling is ingeschakeld door Intune App Protection Policies (APP). Na deze wijziging kunnen iOS-apps voor SDK-versies lager dan 8.1.1, die gebruikmaken van 128-bits versleutelingssleutels, geen gegevens meer delen met toepassingen die zijn geïntegreerd met SDK 8.1.1 of die gebruikmaken van de 256-bits sleutels. Alle iOS-apps moeten eerst over een SDK-versie 8.1.1 of hoger beschikken, als u het beveiligd delen van gegevens wilt toestaan.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Wat kan ik doen om me voor te bereiden op deze wijziging?
Controleer uw Microsoft-apps, apps van derden en LOB-apps (Line-Of-Business). Zorg ervoor dat al uw toepassingen die met Intune APP worden beveiligd, gebruikmaken van SDK-versie 8.1.1 of hoger.

- Voor LOB-apps: U moet uw apps die zijn geïntegreerd met SDK-versie 8.1.1 of hoger mogelijk opnieuw publiceren. U wordt aangeraden de meest recente SDK-versie te gebruiken. Raadpleeg [Line-Of-Business-apps voorbereiden voor app-beveiligingsbeleid](../apps-prepare-mobile-application-management.md) om te zien hoe u uw LOB-apps voorbereidt voor app-beveiligingsbeleid.
- Voor Microsoft-apps/apps van derden: Zorg ervoor dat u de meest recente versie van deze apps naar uw gebruikers implementeert.

U moet zo nodig ook uw documentatie of de richtlijnen voor ontwikkelaars bijwerken, zodat deze wijziging in de ondersteuning voor de SDK is opgenomen.

#### <a name="additional-information"></a>Aanvullende informatie
[Line-of-business-apps voorbereiden voor app-beveiligingsbeleid](../apps-prepare-mobile-application-management.md)

### <a name="plan-for-change-new-windows-updates-settings-in-intune----4464404---"></a>Geplande wijziging: Nieuwe instellingen voor Windows-updates in Intune <!-- 4464404 -->
Vanaf de versie van augustus van de Intune-service of 1908 voegen we nieuwe 'Deadline-instellingen' toe die u kunt configureren in plaats van de instellingen 'Gebruikers toestaan opnieuw te starten (gepland opnieuw opstarten)'. We zijn van plan de instellingen voor gepland opnieuw opstarten in de gebruikersinterface uit te schakelen in 1909 of de update van september en om deze aan het eind van oktober volledig uit de console te verwijderen. 

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Als u Windows 10-apparaten in uw omgeving beheert: 
- Met de Intune-update van augustus of update 1908 ziet u nieuwe deadline-instellingen in de console, naast de oude instellingen voor gepland opnieuw opstarten.
- Wanneer zowel deze oude als nieuwe instellingen zijn geconfigureerd, overschrijven de deadline-instellingen de instellingswaarden voor gepland opnieuw opstarten.
- De deadline-instellingen vervangen de optie 'Gebruikers toestaan opnieuw te starten (gepland opnieuw opstarten)' in update 1910.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Wat kan ik doen om me voor te bereiden op deze wijziging?
Begin de deadline-instellingen in update 1908 te gebruiken door deze te configureren met de gewenste waarden. Als u dat hebt gedaan, kunt u de instelling voor gepland opnieuw opstarten instellen op 'Niet geconfigureerd' om u voor te bereiden op de verwijdering van deze instellingen in oktober.

Werk indien nodig uw documentatie en eventuele automatiseringsscripts bij. 

We houden u op de hoogte en plaatsen een herinnering in het berichtencentrum voordat we de instellingen voor gepland opnieuw opstarten verwijderen.

### <a name="plan-for-change-intune-app-sdk-and-app-protection-policies-for-android-moving-to-support-android-50-and-higher-in-october---4911065---"></a>Geplande wijziging: Intune App SDK en app-beveiligingsbeleid voor Android ondersteunen vanaf oktober Android 5.0 en hoger <!--4911065 -->
Intune gaat Android 5.x (Lollipop) en hoger vanaf oktober ondersteunen. Werk alle verpakte apps bij met de nieuwste Intune App SDK en werk uw apparaten bij.

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
