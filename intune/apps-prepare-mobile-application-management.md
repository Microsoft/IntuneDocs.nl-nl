---
title: Bepalen hoe u apps voorbereidt op Mobile Application Management met Microsoft Intune
description: Aan de hand van de informatie in dit onderwerp kunt u beslissen wanneer u het hulpmiddel App Wrapping en de App SDK moet gebruiken om uw aangepaste LOB-apps in te schakelen voor gebruik van de beleidsregels voor het beheren van mobiele apps.
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: oldang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e8b218ce38a7e76135a62b1155dbf9060ba511cc
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="prepare-line-of-business-apps-for-mam"></a>Line-Of-Business-apps voorbereiden voor MAM

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

U kunt uw apps gebruik laten maken van Mobile Application Management-beleid (MAM) door de Intune App Wrapping Tool of de Intune App SDK te gebruiken. In deze informatie wordt uitgelegd hoe en wanneer u deze twee methoden gebruikt.

## <a name="intune-app-wrapping-tool"></a>Intune App Wrapping Tool
De App Wrapping Tool wordt hoofdzakelijk gebruikt voor interne LOB-apps (Line-Of-Business-apps). Het hulpprogramma is een opdrachtregeltoepassing waarmee een wrapper rond de app wordt gemaakt, zodat de app vervolgens kan worden beheerd door Intune MAM-beleid.

Om het hulpprogramma te kunnen gebruiken, hebt u de broncode niet nodig, maar wel ondertekeningsreferenties.  Zie het [Intune-blog](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/) voor meer informatie over ondertekeningsreferenties. Zie [Android App Wrapping Tool ](app-wrapper-prepare-android.md) en [iOS App Wrapping Tool](app-wrapper-prepare-ios.md) voor documentatie over de App Wrapping Tool.

De App Wrapping Tool biedt **geen** ondersteuning voor apps in de Apple App Store of Google Play Store. De tool biedt ook geen ondersteuning voor bepaalde functies waarvoor ontwikkelaarsintegratie vereist is (zie de volgende functievergelijkingstabel).


Zie [Line-Of-Business-apps en -gegevens beveiligen op apparaten die niet zijn geregistreerd bij Microsoft Intune](/intune-classic/deploy-use/protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune) voor meer informatie over de App Wrapping Tool voor MAM op apparaten die niet zijn ingeschreven bij Intune.

### <a name="reasons-to-use-the-app-wrapping-tool"></a>Redenen om de App Wrapping Tool te gebruiken:
* Uw app heeft geen ingebouwde functies voor gegevensbescherming.
* Uw app is eenvoudig.
* Uw app wordt intern geïmplementeerd.
* U hebt geen toegang tot de broncode van de app.
* U hebt de app niet ontwikkeld.
* De gebruikersverificatie van uw app is minimaal.


### <a name="supported-app-development-platforms"></a>Ondersteunde platforms voor app-ontwikkeling

|**App Wrapping Tool** | **Xamarin** |**Cordova** |
|------|----|----|
|**iOS** |Ja|Yes|
|**Android**| Nee |Yes|

## <a name="intune-app-sdk"></a>Intune App SDK
De App SDK is hoofdzakelijk ontworpen voor klanten die apps in de Apple App Store of Google Play Store hebben en hun apps willen beheren met Intune. Elke app kan echter profiteren van integratie van de SDK, zelfs als het een Line-Of-Business app is.

Zie [Overzicht](app-sdk.md) voor meer informatie over de SDK. Zie [Aan de slag met de Microsoft Intune App SDK](app-sdk-get-started.md) om aan de slag te gaan met de SDK.

### <a name="reasons-to-use-the-sdk"></a>Redenen om de SDK te gebruiken
* Uw app heeft geen ingebouwde functies voor gegevensbescherming.
* Uw app is complex en bevat veel ervaringen.
* Uw app is geïmplementeerd op een openbare app-store, zoals Google Play of de App Store van Apple.
* U bent app-ontwikkelaar en beschikt over de technische achtergrond om de SDK te gebruiken.
* Uw app bevat andere SDK-integraties.
* Uw app wordt regelmatig bijgewerkt.

### <a name="supported-app-development-platforms"></a>Ondersteunde platforms voor app-ontwikkeling

|**Intune App SDK** |**Xamarin** |**Cordova**
|------|----|----|
|**iOS**|Ja, gebruik het [Intune App SDK Xamarin-onderdeel](app-sdk-xamarin.md).|Ja, gebruik de [Intune App SDK Cordova-invoegtoepassing](app-sdk-cordova.md).|
|**Android**| Ja, gebruik het [Intune App SDK Xamarin-onderdeel](app-sdk-xamarin.md).|Ja, gebruik de [Intune App SDK Cordova-invoegtoepassing](app-sdk-cordova.md).|

## <a name="feature-comparison"></a>Vergelijking van functies
In deze tabel staan de instellingen die u kunt gebruiken voor de App SDK en de App Wrapping Tool.

> [!NOTE]
> De App Wrapping Tool kan worden gebruikt met de zelfstandige versie van Intune of met Intune met Configuration Manager.

|Onderdeel|App SDK|App Wrapping Tool|
|-----------|---------------------|-----------|
|Webinhoud beperken en weergeven in een bedrijfsbeheerde browser|X|X|
|Back-ups verhinderen van Android, iTunes of iCloud|X|X|
|App mag gegevens overdragen naar ander apps|X|X|
|App mag gegevens ontvangen van andere apps|X|X|
|Knippen, kopiëren en plakken met andere apps beperken|X|X|
|Eenvoudige pincode vereist voor toegang|X|X|
|De in de app ingebouwde pincode vervangen door de pincode van Intune|X||
|Het aantal pogingen opgeven voordat de pincode opnieuw wordt ingesteld|X|X|
|Vingerafdruk in plaats van pincode toestaan |X|X|
|Bedrijfsreferenties vereisen voor toegang|X|X|
|De uitvoering blokkeren van beheerde apps die op gekraakte of geroote apparaten worden uitgevoerd|X|X|
|App-gegevens versleutelen|X|X|
|De toegangsvereisten na een opgegeven aantal minuten opnieuw controleren|X|X|
|De offlinerespijtperiode opgeven|X|X|
|Schermafbeeldingen maken blokkeren (alleen Android)|X|X|
|Ondersteuning van MAM zonder apparaatinschrijving|X|X|
|Volledig wissen|X|X|
|Selectief wissen <br></br>**Opmerking:** bij iOS geldt dat als het beheerprofiel wordt verwijderd, ook de app wordt verwijderd.|X||
|'Opslaan als' voorkomen |X||
|Configuratie van doeltoepassingen |X||
|Ondersteuning voor meerdere identiteiten|X||
|Aanpasbare stijl |X|||
### <a name="see-also"></a>Zie tevens

[Android App Wrapping Tool](app-wrapper-prepare-android.md)</br>
[iOS App Wrapping Tool](app-wrapper-prepare-ios.md)</br>
[De SDK gebruiken om apps geschikt te maken voor Mobile Application Management](/intune-classic/deploy-use/use-the-sdk-to-enable-apps-for-mobile-application-management)
