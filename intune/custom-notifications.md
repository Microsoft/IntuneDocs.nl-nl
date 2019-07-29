---
title: Aangepaste meldingen naar gebruikers verzenden met Microsoft Intune
titleSuffix: ''
description: U kunt Intune gebruiken om aangepaste pushmeldingen naar gebruikers van iOS- en Android-apparaten te verzenden
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 7/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: jinyoon
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1caff820daf2e278c50d154873f569163b264315
ms.sourcegitcommit: c3a4fefbac8ff7badc42b1711b7ed2da81d1ad67
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/22/2019
ms.locfileid: "68378127"
---
# <a name="send-custom-notifications-in-intune"></a>Aangepaste meldingen verzenden in Intune  

Gebruik Microsoft Intune om aangepaste meldingen te verzenden naar de gebruikers van beheerde iOS- en Android-apparaten. Deze berichten worden op de apparaten van gebruikers weergegeven als reguliere pushmeldingen vanuit de Bedrijfsportal-app, net zoals meldingen van andere toepassingen op het apparaat worden weergegeven. De aangepaste meldingen van Intune worden niet ondersteund door Windows-apparaten.   

Aangepaste meldingen hebben een korte titel en een hoofdtekst van maximaal 500 tekens. De berichten kunnen worden aangepast voor algemene communicatiedoeleinden.

## <a name="common-scenarios-for-sending-custom-notifications"></a>Algemene scenario's voor het verzenden van aangepaste meldingen  

- U kunt aangepaste meldingen gebruiken op specifieke gebruikers te laten weten dat er een nieuwe app beschikbaar is in de bedrijfsportal.  
- Informeer alle werknemers over een wijziging in de planning, bijvoorbeeld omdat het gebouw wordt gesloten vanwege guur weer.  

## <a name="considerations-for-using-custom-notifications"></a>Overwegingen voor het gebruik van aangepaste meldingen  

**Apparaatconfiguratie**:  
- Op apparaten moet de app Bedrijfsportal zijn geïnstalleerd, anders kunnen gebruikers geen aangepaste meldingen ontvangen. Er moeten ook machtigingen zijn geconfigureerd op basis waarvan de app Bedrijfsportal pushmeldingen mag verzenden. De app Bedrijfsportal vraagt gebruikers om meldingen toe te staan.  
- Op Android is Google Play Services een vereiste afhankelijkheid.  

**Meldingen maken**:  
- Als u een bericht wilt maken, gebruikt u een account waaraan een Intune-rol is toegewezen met de machtiging **Bijwerken** voor **Organisatie**. Voor het toewijzen van machtigingen aan een gebruiker ziet u [Roltoewijzingen](role-based-access-control.md#role-assignments)  
- Aangepaste meldingen mogen een titel hebben van maximaal 50 tekens en een hoofdtekst van maximaal 500 tekens.  
- Verzonden berichten worden niet opgeslagen door Intune. Als u een bericht opnieuw wilt verzenden, moet u het bericht opnieuw maken.  
- U kunt maximaal 25 berichten per uur verzenden. Deze beperking is ingesteld op het tenantniveau.  
- Met elke melding kunt u maximaal 25 groepen tegelijk benaderen. Geneste groepen tellen niet mee voor dit totaal.  
- Groepen kunnen gebruikers en apparaten omvatten, maar berichten worden alleen naar gebruikers verzonden. Ze worden naar alle iOS- en Android-apparaten verzonden die de gebruiker heeft geregistreerd.  

**Levering**:  
- Intune probeert berichten gedurende maximaal één uur nadat de melding is verzonden, af te leveren.  
- Intune verzendt berichten naar de app Bedrijfsportal van de gebruikers. Deze app creëert vervolgens de pushmelding. Gebruikers hoeven niet bij de app aangemeld te zijn om meldingen naar het apparaat te kunnen pushen.  
- Intune en de app Bedrijfsportal kunnen niet garanderen dat aangepaste meldingen worden afgeleverd. Aangepaste meldingen kunnen met enkele uren vertraging worden weergegeven (áls ze al worden weergegeven), dus het is geen goed idee om deze voor dringende berichten te gebruiken.  
- Aangepaste meldingen vanuit Intune worden als reguliere pushmeldingen weergegeven op apparaten. Als de app Bedrijfsportal is geopend op een iOS-apparaat wanneer de melding wordt ontvangen, wordt de melding in de app weergegeven in plaats van als pushmelding.  
- Aangepaste meldingen kunnen worden weergegeven op het vergrendelingsscherm van zowel iOS- als Android-apparaten, afhankelijk van de apparaatinstellingen.  
- Op Android-apparaten hebben andere apps mogelijk toegang tot de gegevens in uw aangepaste meldingen. Gebruik ze niet voor het overdragen van gevoelige informatie.  
- Gebruikers van apparaten die recent zijn uitgeschreven en gebruikers die uit een groep zijn verwijderd, ontvangen mogelijk wel nog aangepaste meldingen die naar die groep worden verzonden.  Het is ook zo dat als u een gebruiker aan een groep toevoegt nadat er een aangepaste melding naar de groep is verzonden, de nieuwe gebruiker de eerder verzonden melding ook nog kan ontvangen.  

## <a name="send-a-custom-notification"></a>Een aangepaste melding verzenden  

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) met een account met machtigingen voor het maken en verzenden van meldingen en ga dan naar **Apparaten** > **Aangepaste meldingen verzenden**.  

2. Geef op het tabblad Basisinformatie de volgende informatie op en selecteer **Volgende** om door te gaan.  
   - **Titel**: geef deze melding een titel. De titel mag maximaal 50 tekens lang zijn.  
   - **Hoofdtekst**: geef het bericht op. Berichten mogen maximaal 500 tekens lang zijn

   ![Een aangepaste melding maken](./media/custom-notifications/custom-notifications.png)  

3. Selecteer op het tabblad **Toewijzingen** de groepen waarnaar u deze aangepaste melding wilt verzenden en selecteer dan Volgende om door te gaan.  

4. Controleer op het tabblad **Beoordelen en maken** de gegevens en als u er klaar voor bent om de melding te verzenden, selecteert u **Maken**.  

Intune verwerkt de berichten die u maakt onmiddellijk. De enige bevestiging dat het bericht is verzonden, is een Intune-melding waarin wordt bevestigd dat de aangepaste melding is verzonden.  

![Bevestiging van een verzonden melding](./media/custom-notifications/notification-sent.png)  

Intune volgt verzonden aangepaste meldingen niet. Apparaten registreren ontvangst ook niet buiten het meldingencentrum van de apparaten.  

## <a name="receive-a-custom-notification"></a>Een aangepaste melding ontvangen  

Gebruikers zien op hun apparaat aangepaste meldingen die door Intune worden verzonden als reguliere pushmeldingen uit de app Bedrijfsportal. Deze meldingen zijn vergelijkbaar met de pushmeldingen die gebruikers ontvangen van andere apps op het apparaat.  

Als de app Bedrijfsportal is geopend op een iOS-apparaat wanneer de melding wordt ontvangen, wordt de melding in de app weergegeven in plaats van als pushmelding.  

De melding blijft bewaard totdat de gebruiker deze sluit.  

## <a name="next-steps"></a>Volgende stappen  
[Apparaten beheren](device-management.md)
