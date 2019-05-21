---
title: Include-bestand
description: Include-bestand
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: ffcef5b4d78856709f8563ee1f667ec7e5d993b3
ms.sourcegitcommit: d2e04a38e024b0f5afb0ca202823227de9da3ad1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/09/2019
ms.locfileid: "65732614"
---
Deze mededelingen bevatten belangrijke informatie die u kan helpen om voorbereid te zijn op toekomstige wijzigingen en functies in Intune. 

### <a name="change-in-enrollment-workflow-with-intune-company-portal-on-corporate-ios-devices-authenticating-with-setup-assistant----1927359---"></a>Wijziging in de werkstroom voor registratie bij de Intune-bedrijfsportal op zakelijke iOS-apparaten die zich verifiëren met Configuratieassistent <!-- 1927359 -->
Er komt een wijziging in de werkstroom voor het registreren van iOS-apparaten via een van de registratiemethoden van Apple voor zakelijke apparaten, te weten Apple Configurator, Apple Business Manager, Apple School Manager of DEP (Apple Device Enrollment Program), als Configuratieassistent wordt gebruikt voor verificatie. Deze wijziging geldt alleen voor apparaten die worden ingeschreven met gebruikersaffiniteit.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Wanneer deze wijziging wordt uitgerold, worden registratieprofielen in Intune in de Azure-portal bijgewerkt zodat u kunt opgeven hoe apparaten zich verifiëren en of zij de bedrijfsportal-app ontvangen. Er ontstaat een verbeterde werkstroom om iOS-apparaten te registreren via de hierboven genoemde methoden. 

- Bij het registreren van nieuwe apparaten en het verifiëren van deze apparaten met Configuratieassistent, kunt u kiezen of u de bedrijfsportal-app al dan niet automatisch wilt implementeren. Eindgebruikers zien niet meer zien het scherm 'Uw apparaat identificeren' en het scherm 'Uw apparaat bevestigen' in de werkstroom voor registratie.  
- Op apparaten die al zijn geregistreerd via Configuratieassistent en een van de registratiemethoden van Apple voor zakelijke apparaten, moet u actie ondernemen als u voorwaardelijke toegang wilt inschakelen. U moet [een configuratiebeleid voor apps configureren](https://aka.ms/enrollment_setup_assistant) met een specifieke xml om de bedrijfsportal-app naar deze apparaten te pushen.  Als u ervoor kiest om de bedrijfsportal op deze manier te pushen, zien eindgebruikers niet meer zien het scherm 'Uw apparaat identificeren' en het scherm 'Uw apparaat bevestigen' in de werkstroom voor registratie. 
- Nadat deze wijziging is uitgerold, en u de bedrijfsportal-app niet hebt geïmplementeerd met het hierboven genoemde app-configuratieprofiel, en eindgebruikers de bedrijfsportal-app downloaden uit de App Store, kunnen ze zich wel aanmelden maar krijgen ze een foutmelding. Ze kunnen de app niet gebruiken voor voorwaardelijke toegang. 

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
Als u van plan bent om de gewijzigde werkstroom te gaan gebruiken, moet u de instructies voor uw eindgebruikers aanpassen om het volgende duidelijk te maken:

- Eindgebruikers zien de twee hierboven genoemde schermen niet meer in de werkstroom voor registratie. 
- Ze moeten zich aanmelden bij de bedrijfsportal-app wanneer deze automatisch wordt geïmplementeerd en de app niet downloaden uit de App Store. 

U kunt ervoor kiezen om nu een configuratiebeleid voor apps te maken indien dat nodig is, ter voorbereiding op deze wijziging. Wanneer deze nieuwe werkstroom wordt uitgerold, ziet u dan bijgewerkte registratieprofielen in de console. We informeren u ook over deze implementatie via het berichtencentrum. Vervolgens moet u actie ondernemen zodat uw eindgebruikers zich kunnen registreren via DEP door verificatie met Configuratieassistent en kunt u de bedrijfsportal-app gebruiken voor voorwaardelijke toegang.

#### <a name="additional-information"></a>Aanvullende informatie 
[https://aka.ms/enrollment_setup_assistant](https://aka.ms/enrollment_setup_assistant)


### <a name="update-your-android-company-portal-app-to-the-latest-version---4536963--"></a>Android-bedrijfsportal-app bijwerken naar de nieuwste versie <!--4536963-->
Er worden regelmatig updates van Intune gepubliceerd voor de Android-versie van de bedrijfsportal-app. In november 2018 hebben we een update voor de bedrijfsportal gepubliceerd, met onder andere een schakeloptie voor de back-end om u voor te bereiden op de wijziging van Google waarbij ze hun bestaande meldingenplatform gaan overzetten naar Firebase Cloud Messaging (FCM) van Google. Als Google hun bestaande meldingenplatform uit de lucht haalt en overstapt naar FCM, moeten eindgebruikers hun bedrijfsportal-app hebben bijgewerkt naar ten minste de versie van november 2018 om te kunnen blijven communiceren met de Google Play Store.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Onze telemetrie geeft aan dat u apparaten hebt met een versie van de bedrijfsportal-app die ouder is dan 5.0.4269.0. Als niet deze versie of hoger van de bedrijfsportal-app is geïnstalleerd, bestaat de kans dat door IT-personeel gestarte apparaatacties, zoals wissen, wachtwoord opnieuw instellen, beschikbare en vereiste app-installaties, en certificaatinschrijving, niet werken zoals verwacht. Als uw apparaten via een MDM zijn geregistreerd bij Intune, kunt u de versies en gebruikers van de bedrijfsportal zien door naar Client-apps – Gedetecteerde apps te gaan. Selecteer een eerdere versie van de bedrijfsportal-app om te zien welke gebruikers de apparaten hebben waarop de bedrijfsportal-app niet is bijgewerkt.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
Vraag eindgebruikers van Android-apparaten die niet up-to-date zijn om de bedrijfsportal-app bij te werken via de Google Play Store. Informeer de helpdesk voor het geval een gebruiker niet voor het automatisch bijwerken van de bedrijfsportal-app heeft gekozen. Volg de koppeling bij Aanvullende informatie voor meer informatie over het FCM-platform van Google en de aanstaande wijziging.

#### <a name="additional-information"></a>Aanvullende informatie
https://firebase.google.com/docs/cloud-messaging/