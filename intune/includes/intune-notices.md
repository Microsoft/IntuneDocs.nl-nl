---
title: Include-bestand
description: Include-bestand
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: include
ms.date: 03/28/2019
ms.author: erikje
ms.custom: include file
ms.openlocfilehash: 1073a38da8a5b2467b1ff8c97b32b93f92e34e4c
ms.sourcegitcommit: f90cba0b2c2672ea733052269bcc372a80772945
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/31/2019
ms.locfileid: "66454118"
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
