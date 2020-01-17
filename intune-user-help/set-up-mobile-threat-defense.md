---
title: Mobile Threat Defense installeren op uw mobiele apparaat
description: Lees hoe u Mobile Threat Defense installeert op uw mobiele apparaat.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/25/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.custom: intune-enduser
ms.collection: ''
ms.openlocfilehash: 6b75712cf05626999c09e8d74fd28252666313c4
ms.sourcegitcommit: caee3c3fa77586314aa8040b0caf32a0527b669e
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 01/10/2020
ms.locfileid: "75857871"
---
# <a name="install-mobile-threat-defense"></a>Mobile Threat Defense installeren   

Als onderdeel van de beveiligings vereisten van uw organisatie moet u mogelijk een toepassing voor de leverancier van de Mobile Threat verdediging (MTD) installeren. Dit type app detecteert en waarschuwt u tot bedreigingen op uw apparaat, zoals verdachte apps, netwerken of beveiligings problemen van besturings systemen.  

Als u niet beschikt over de vereiste MTD-app, kunt u zich niet aanmelden bij beveiligde apps met uw werk-of school account. In dit artikel leert u hoe u [een MTD-app kunt installeren om de](set-up-mobile-threat-defense.md#install-app) blok kering op te heffen.  

Er zijn diverse MTD-apps voor de toepassing beschikbaar voor installatie. uw organisatie laat u weten welk abonnement u moet gebruiken. 


## <a name="information-your-organization-can-see"></a>Informatie die uw organisatie kan zien   

Uw organisatie kan geen gegevens zien, zoals teksten, e-mails en afbeeldingen, in uw persoonlijke apps. De MTD-app rapporteert informatie over uw apps, zoals naam en versie, aan uw organisatie. De werkelijke informatie die wordt gerapporteerd, is afhankelijk van de MTD-leverancier die uw bedrijf gebruikt. Uw organisatie kan zien:   

* App-naam  
* App-id: De unieke naam waarmee de app wordt geïdentificeerd in Google Play.  
* Appversie en verkort versienummer: De specifieke releasenummers van een app.  
* App-bundel en dynamische grootte: De hoeveelheid ruimte die een app op uw apparaat gebruikt. 


## <a name="install-app"></a>App installeren    
Wanneer u zich aanmeldt bij een beveiligde app, wordt u automatisch gevraagd om een MTD-app te installeren. Volg de stappen op het scherm om de installatie te volt ooien. Volg de stappen in deze sectie voor meer informatie.  
 
U wordt mogelijk ook gevraagd om uw apparaat te registreren. Registratie is nodig om uw identiteit te bevestigen en uw school-of werk account te verbinden met uw apparaat. Als u niet bent geregistreerd, wordt u automatisch begeleid door de installatie voordat u de MTD-app installeert. Wanneer u het scherm **toegang verkrijgen opent** , kunt u de installatie stappen starten.  

Zie [uw persoonlijke apparaat registreren op het netwerk van uw organisatie](https://docs.microsoft.com/azure/active-directory/user-help/user-help-register-device-on-network)voor meer informatie over apparaatregistratie.  

### <a name="ios-setup"></a>iOS-installatie  

1. Volg op het scherm **toegang verkrijgen** de instructies voor het installeren van de MTD-app die is vereist voor uw organisatie.   
2. Ga terug naar het scherm **toegang verkrijgen** en selecteer **openen**.  
3. De MTD-app vraagt om toestemming voor het openen van Microsoft Authenticator. Selecteer **Openen**. 
4. Selecteer uw werk account om u aan te melden. 
5. Wacht tot de MTD-app uw apparaat scant op beveiligings Risico's. 
6. Ga terug naar de school-of werk app waartoe u oorspronkelijk probeerde toegang te krijgen. Op dit moment kan uw organisatie u vragen andere vereisten voor app-beveiliging te configureren, zoals het maken van een pincode.   
7. U hebt nu toegang tot de app. Als u nog steeds bent geblokkeerd:  
    * Selecteer op het scherm **toegang verkrijgen** de optie opnieuw **controleren**.  
    * Ga naar de MTD-app en controleer op bestaande bedreigingen. Voer de aanbevolen stappen uit om de dreiging op te lossen en weer toegang te krijgen.    

### <a name="android-setup"></a>Android-configuratie 

1. Volg op het scherm **toegang verkrijgen** de instructies voor het installeren van de MTD-app die is vereist voor uw organisatie.  
2. Ga terug naar het scherm **toegang verkrijgen** en selecteer **openen**.  
3. De MTD-app vraagt om toestemming om toegang te krijgen tot bepaalde gebieden van uw apparaat, indien nodig. Als u deze app goed wilt laten werken, moet u toegang tot contact personen **toestaan** . De aangevraagde machtigingen variëren per MTD-leverancier.  
4. Selecteer uw werk account om u aan te melden.  
5. Wacht tot de MTD-app uw apparaat scant op beveiligings Risico's.  
6. Ga terug naar de school-of werk app waartoe u oorspronkelijk probeerde toegang te krijgen. Op dit moment kan uw organisatie u vragen andere vereisten voor app-beveiliging te configureren, zoals het maken van een pincode.  
7. U hebt nu toegang tot de app. Als u nog steeds bent geblokkeerd:  
    * Selecteer op het scherm **toegang verkrijgen** de optie opnieuw **controleren**.  
    * Ga naar de MTD-app en controleer op bestaande bedreigingen. Voer de aanbevolen stappen uit om de dreiging op te lossen en weer toegang te krijgen.  

### <a name="installation-failed"></a>De installatie is mislukt  

Als de installatie mislukt, neemt u contact op met uw IT-ondersteunings medewerker. [Ga naar de website van de bedrijfsportal](https://go.microsoft.com/fwlink/?linkid=2010980) om de contactgegevens van uw organisatie op te zoeken.  

U kunt ook uw app-logboeken naar uw IT-ondersteunings medewerker verzenden om hen meer context over de installatie te geven.  
* Android-gebruikers: [Upload en e-mail uw logboeken](https://docs.microsoft.com/intune-user-help/send-logs-to-your-it-admin-by-email-android) van bedrijfsportal.   

* gebruikers van iOS-apparaten: [ophalen en verzenden van uw logboeken](https://docs.microsoft.com/intune/apps/manage-microsoft-edge#use-microsoft-edge-on-ios-to-access-managed-app-logs) van micro soft Edge voor IOS.  

## <a name="resolve-a-threat"></a>Een bedreiging oplossen  
Als een bedreiging het ingestelde bedreigings niveau van uw organisatie overschrijdt, heeft uw organisatie de volgende:  
   
* Toegang blok keren: Hiermee blokkeert u het gebruik van de beveiligde apps van uw organisatie terwijl u bent aangemeld bij uw werk-of school account.  
* Gegevens wissen: verwijdert uw werk-of school gegevens uit een of meer van de beveiligde apps van uw organisatie.  

Open de MTD-app op uw apparaat om een bedreiging op te lossen en weer toegang te krijgen. Lees de verstrekte informatie om te zien hoe de dreiging uw apparaat kan beïnvloeden en hoe dit kan worden opgelost. Nadat u de stappen voor het oplossen van de bedreiging hebt gevolgd, gaat u terug naar de MTD-app en start u een nieuwe scan. Het kan enkele minuten duren om weer toegang te krijgen tot uw organisatie.  

## <a name="next-steps"></a>Volgende stappen  

Nog hulp nodig? Neem contact op met het ondersteuningsteam van uw bedrijf. Controleer of de contactgegevens beschikbaar zijn op de [bedrijfsportalwebsite](https://go.microsoft.com/fwlink/?linkid=2010980).

