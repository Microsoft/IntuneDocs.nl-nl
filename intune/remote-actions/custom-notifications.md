---
title: Aangepaste meldingen naar gebruikers verzenden met Microsoft Intune
titleSuffix: Microsoft Intune
description: U kunt Intune gebruiken om aangepaste pushmeldingen naar gebruikers van iOS- en Android-apparaten te verzenden
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/15/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: jinyoon
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d42651b11891f3d830c0d90e70a9ecd98ea5bfb7
ms.sourcegitcommit: 52475fcd8d05d2f6b858d780ebb3d88eaadb0849
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/15/2020
ms.locfileid: "76036611"
---
# <a name="send-custom-notifications-in-intune"></a>Aangepaste meldingen verzenden in Intune  

Gebruik Microsoft Intune om aangepaste meldingen te verzenden naar de gebruikers van beheerde iOS- en Android-apparaten. Deze berichten worden op de apparaten van gebruikers weergegeven als reguliere pushmeldingen vanuit de Bedrijfsportal-app en de Microsoft Intune-app, net zoals meldingen van andere toepassingen op het apparaat worden weergegeven. De aangepaste meldingen van Intune worden niet ondersteund voor macOS- Windows-apparaten.   

Aangepaste meldingen hebben een korte titel en een hoofdtekst van maximaal 500 tekens. De berichten kunnen worden aangepast voor algemene communicatiedoeleinden.

## <a name="common-scenarios-for-sending-custom-notifications"></a>Algemene scenario's voor het verzenden van aangepaste meldingen  

- Informeer alle werknemers over een wijziging in de planning, bijvoorbeeld omdat het gebouw wordt gesloten vanwege slechte weersomstandigheden.
- Stuur de gebruiker van één apparaat een melding om een dringend verzoek te communiceren, zoals een apparaat opnieuw opstarten om de installatie van een update te voltooien. 

## <a name="considerations-for-using-custom-notifications"></a>Overwegingen voor het gebruik van aangepaste meldingen

**Apparaatconfiguratie** 

- Op apparaten moet de Bedrijfsportal-app of de Microsoft Intune-app zijn geïnstalleerd, anders kunnen gebruikers geen aangepaste meldingen ontvangen. Er moeten ook machtigingen zijn geconfigureerd op basis waarvan de Bedrijfsportal-app of de Microsoft Intune-app pushmeldingen mag verzenden. Indien nodig, kunnen de Bedrijfsportal-app en de Microsoft Intune-app gebruikers vragen om meldingen toe te staan.  
- Op Android is Google Play Services een vereiste afhankelijkheid.  
- Het apparaat moet bij MDM zijn ingeschreven.

**Machtigingen**:
- Als u meldingen wilt verzenden naar groepen, moet uw account beschikken over de volgende RBAC-machtiging in intune: *Organisatie* > **Bijwerken**.
- Als u meldingen wilt verzenden naar een apparaat, moet uw account beschikken over de volgende RBAC-machtiging in Intune: *Externe taken* > **Aangepaste meldingen verzenden**.

**Meldingen maken**:  
- Als u een bericht wilt maken, gebruikt u een account waaraan een Intune-rol is toegewezen met de machtiging **Bijwerken** voor **Organisatie**. Voor het toewijzen van machtigingen aan een gebruiker ziet u [Roltoewijzingen](../fundamentals/role-based-access-control.md#role-assignments)  
- Aangepaste meldingen mogen een titel hebben van maximaal 50 tekens en een hoofdtekst van maximaal 500 tekens.  
- Verzonden berichten worden niet opgeslagen door Intune. Als u een bericht opnieuw wilt verzenden, moet u het bericht opnieuw maken.  
- U kunt maximaal 25 berichten per uur verzenden naar groepen. Deze beperking is ingesteld op het tenantniveau. Deze beperking is niet van toepassing wanneer u meldingen verzendt naar afzonderlijke gebruikers.
- Wanneer u berichten verzendt naar afzonderlijke apparaten, kunt u maximaal 10 berichten per uur verzenden naar hetzelfde apparaat. 
- U kunt meldingen naar meerdere gebruikers of apparaten verzenden door de melding toe te wijzen aan groepen. Bij het gebruik van groepen kan elke melding aan maximaal 25 groepen tegelijk worden toegewezen. Geneste groepen tellen niet mee voor dit totaal.  

  Groepen kunnen gebruikers en apparaten omvatten, maar berichten worden alleen verzonden naar gebruikers. Ze worden naar alle iOS- en Android-apparaten verzonden die de gebruiker heeft geregistreerd.  
- U kunt aangepaste meldingen verzenden naar één apparaat. In plaats van groepen te gebruiken, selecteert u een apparaat en gebruikt u vervolgens een externe [apparaatactie](device-management.md#available-device-actions) om de aangepaste melding te verzenden.  

**Levering**:  
- Intune verzendt berichten naar de Bedrijfsportal-app of de Microsoft Intune-app van de gebruikers. Deze app creëert vervolgens de pushmelding. Gebruikers hoeven niet bij de app aangemeld te zijn om meldingen naar het apparaat te kunnen pushen.  
- Intune en de Bedrijfsportal-app of de Microsoft Intune-app kunnen niet garanderen dat aangepaste meldingen worden afgeleverd. Aangepaste meldingen kunnen met enkele uren vertraging worden weergegeven (áls ze al worden weergegeven), dus het is geen goed idee om deze voor dringende berichten te gebruiken.  
- Aangepaste meldingen vanuit Intune worden als reguliere pushmeldingen weergegeven op apparaten. Als de app Bedrijfsportal is geopend op een iOS-apparaat wanneer de melding wordt ontvangen, wordt de melding in de app weergegeven in plaats van als pushmelding.  
- Aangepaste meldingen kunnen worden weergegeven op het vergrendelingsscherm van zowel iOS- als Android-apparaten, afhankelijk van de apparaatinstellingen.  
- Op Android-apparaten hebben andere apps mogelijk toegang tot de gegevens in uw aangepaste meldingen. Gebruik ze niet voor het overdragen van gevoelige informatie.  
- Gebruikers van apparaten die recent zijn uitgeschreven, of gebruikers die uit een groep zijn verwijderd, ontvangen mogelijk nog wel aangepaste meldingen die later naar zijn verzonden deze groep.  En als u een gebruiker toevoegt aan een groep nadat er een aangepaste melding naar de groep is verzonden, ontvangt de nieuwe gebruiker mogelijk ook de eerder verzonden melding.  

## <a name="send-a-custom-notification-to-groups"></a>Een aangepaste melding verzenden naar groepen  

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) met een account met machtigingen voor het maken en verzenden van meldingen en ga naar **Tenantbeheer** > **Aangepaste meldingen**.  

2. Geef op het tabblad Basisinformatie de volgende informatie op en selecteer **Volgende** om door te gaan.  
   - **Titel**: geef deze melding een titel. De titel mag maximaal 50 tekens lang zijn.  
   - **Hoofdtekst**: geef het bericht op. Berichten mogen maximaal 500 tekens bevatten.

   ![Een aangepaste melding maken](./media/custom-notifications/custom-notifications.png)  

3. Selecteer op het tabblad **Toewijzingen** de groepen waarnaar u deze aangepaste melding wilt verzenden en selecteer dan Volgende om door te gaan.  

4. Controleer op het tabblad **Beoordelen en maken** de gegevens en als u er klaar voor bent om de melding te verzenden, selecteert u **Maken**.  

Intune verwerkt de berichten die u maakt onmiddellijk. De enige bevestiging dat het bericht is verzonden, is een Intune-melding waarin wordt bevestigd dat de aangepaste melding is verzonden.  

![Bevestiging van een verzonden melding](./media/custom-notifications/notification-sent.png)  

Intune volgt verzonden aangepaste meldingen niet. Apparaten registreren ontvangst ook niet buiten het meldingencentrum van de apparaten.  

## <a name="send-a-custom-notification-to-a-single-device"></a>Een aangepaste melding verzenden naar één apparaat  

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) met een account met machtigingen voor het maken en verzenden van meldingen en ga naar **Apparaten** > **Alle apparaten**.

2. Dubbelklik op de naam van het beheerde apparaat waarnaar u een melding wilt verzenden om de pagina *Overzicht* van die apparaten te openen.

3. Op de pagina **Overzicht** van de apparaten selecteert u de apparaatactie **Aangepaste melding verzenden** om het venster *Aangepaste melding verzenden* te openen. Als de optie niet beschikbaar is, selecteert u de optie **...** (weglatingsteken) rechtsboven in de pagina en selecteert u **Aangepaste melding verzenden**.

4. Geef in het venster **Aangepaste melding verzenden** de volgende berichtdetails op:  

   - **Titel**: geef deze melding een titel. De titel mag maximaal 50 tekens lang zijn.  
   - **Hoofdtekst**: geef het bericht op. Berichten mogen maximaal 500 tekens bevatten.  

5. Selecteer **Verzenden** om de aangepaste melding te verzenden naar het apparaat. In tegenstelling tot meldingen die u verzendt naar groepen, configureert u een toewijzing niet en controleert u het bericht niet voordat u het verzendt.  

Het bericht wordt onmiddellijk verwerkt in Intune. De enige bevestiging dat het bericht is verzonden, is de Intune-melding die u ontvangt in de console, waarin de tekst wordt weergegeven van het bericht dat u hebt verzonden.  

## <a name="receive-a-custom-notification"></a>Een aangepaste melding ontvangen  

Gebruikers zien op hun apparaat aangepaste meldingen die door Intune worden verzonden als reguliere pushmeldingen uit de Bedrijfsportal-app of de Microsoft Intune-app. Deze meldingen zijn vergelijkbaar met de pushmeldingen die gebruikers ontvangen van andere apps op het apparaat.  

Als de app Bedrijfsportal is geopend op een iOS-apparaat wanneer de melding wordt ontvangen, wordt de melding in de app weergegeven in plaats van als pushmelding.  

De melding blijft bewaard totdat de gebruiker deze sluit.  

## <a name="next-steps"></a>Volgende stappen  

[Apparaten beheren](device-management.md)
