---
title: Include-bestand
description: Include-bestand
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: fab8f2be48a30f6ad058b3eeb6874a44ff04e6ac
ms.sourcegitcommit: 7ceae61e036ccf8b33704751b0b39fee81944072
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/06/2019
ms.locfileid: "66744319"
---
Deze mededelingen bevatten belangrijke informatie die u kan helpen om voorbereid te zijn op toekomstige wijzigingen en functies in Intune. 

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

### <a name="plan-for-change-intune-moving-to-support-ios-11-and-higher-in-september----4665342--"></a>Geplande wijziging: Intune zal vanaf september iOS 11 en hoger ondersteunen <!-- 4665342-->
We verwachten dat iOS 13 in september wordt uitgebracht door Apple. Kort na de release van iOS 13 zullen Intune-inschrijving, de bedrijfsportal en de beheerde browser ondersteuning bieden voor iOS 11 en hoger.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Onder voorwaarde dat de mobiele Office 365-apps worden ondersteund in iOS 11.0 en hoger, heeft dit mogelijk geen gevolgen voor u omdat u waarschijnlijk het besturingssysteem of de apparaten al hebt geüpgraded. Als u echter over een van de hieronder vermelde apparaten beschikt of als u een van de hieronder vermelde apparaten wilt inschrijven, moet u er rekening mee houden dat de onderstaande apparaten alleen iOS 10 en eerdere versies ondersteunen. Deze apparaten moeten worden geüpgraded naar een apparaat dat ondersteuning biedt voor iOS 11 of hoger:

- iPhone 5
- iPhone 5c
- iPad (4e generatie)

Vanaf juli krijgen apparaten met iOS 10 en de bedrijfsportal die bij MDM zijn ingeschreven een bericht waarin wordt vermeld dat het besturingssysteem of het apparaat moet worden geüpgraded. Als u Application Protection Policies (APP) gebruikt, kunt u ook de toegangsinstelling 'Minimumversie van het iOS-besturingssysteem vereisen (alleen waarschuwing)' instellen.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
Controleer uw Intune-rapporten om te zien voor welke apparaten of gebruikers dit gevolgen kan hebben. Ga naar **Apparaten** > **Alle apparaten** en filter op besturingssysteem. U kunt extra kolommen toevoegen, zodat u eenvoudiger kunt vaststellen wie in uw organisatie apparaten met iOS 10 gebruikt. Verzoek uw eindgebruikers om vóór september hun apparaten te upgraden naar een ondersteunde besturingssysteemversie.

### <a name="plan-for-change-support-for-version-811-and-higher-of-intune-app-sdk-for-ios----3586942--"></a>Geplande wijziging: Ondersteuning voor versie 8.1.1 en hoger van de Intune App SDK voor iOS <!-- 3586942-->
Vanaf september 2019 biedt Intune ondersteuning voor iOS-apps met Intune App SDK 8.1.1 en hoger. Apps die zijn gemaakt met SDK-versies lager dan 8.1.1 worden niet meer ondersteund. Deze wijziging wordt van kracht met de Apple-release van iOS 13, die rond september wordt verwacht en ook is aangekondigd in MC181399.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Met de integratie van de Intune App SDK of App Wrapping kunt u bedrijfsgegevens via gegevensversleuteling beveiligen tegen niet-goedgekeurde toepassingen en gebruikers. De Intune App SDK voor iOS gebruikt standaard 256-bits versleutelingssleutels wanneer versleuteling is ingeschakeld door Intune App Protection Policies (APP). Na deze wijziging kunnen iOS-apps voor SDK-versies lager dan 8.1.1, die gebruikmaken van 128-bits versleutelingssleutels, geen gegevens meer delen met toepassingen die zijn geïntegreerd met SDK 8.1.1 of die gebruikmaken van de 256-bits sleutels. Alle iOS-apps moeten eerst over een SDK-versie 8.1.1 of hoger beschikken, als u het beveiligd delen van gegevens wilt toestaan.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Wat kan ik doen om me voor te bereiden op deze wijziging?
Controleer uw Microsoft-apps, apps van derden en LOB-apps (Line-Of-Business). U moet ervoor zorgen dat al uw toepassingen die met Intune APP worden beveiligd, gebruikmaken van SDK-versie 8.1.1 of hoger.

- Voor LOB-apps: U moet uw apps die zijn geïntegreerd met SDK-versie 8.1.1 of hoger mogelijk opnieuw publiceren. U wordt aangeraden de meest recente SDK-versie te gebruiken. Bekijk [Line-Of-Business-apps voorbereiden voor app-beveiligingsbeleid](../apps-prepare-mobile-application-management.md) om te zien hoe u uw LOB-apps voorbereidt voor app-beveiligingsbeleid.
- Voor Microsoft-apps/apps van derden: Zorg ervoor dat u de meest recente versie van deze apps naar uw gebruikers implementeert.

U moet zo nodig ook uw documentatie of de richtlijnen voor ontwikkelaars bijwerken, zodat deze wijziging in de ondersteuning voor de SDK is opgenomen.

#### <a name="additional-information"></a>Aanvullende informatie
https://docs.microsoft.com/intune/apps-prepare-mobile-application-management
