---
title: Apps geschikt maken voor beheer van mobiele apps met Microsoft Intune
description: Aan de hand van de informatie in dit onderwerp kunt u beslissen wanneer u het hulpmiddel App Wrapping en de App SDK moet gebruiken om uw aangepaste LOB-apps in te schakelen voor gebruik van de beleidsregels voor het beheren van mobiele apps.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/09/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 901eaafb24cda185540ffc4b1a56484042af74c1
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "74547687"
---
# <a name="prepare-line-of-business-apps-for-app-protection-policies"></a>Line-of-business-apps voorbereiden voor app-beveiligingsbeleid

U kunt uw apps gebruik laten maken van app-beveiligingsbeleid door de Intune App Wrapping Tool of de Intune App SDK te gebruiken. In deze informatie wordt uitgelegd hoe en wanneer u deze twee methoden gebruikt.

## <a name="intune-app-wrapping-tool"></a>Intune App Wrapping Tool

De App Wrapping Tool wordt hoofdzakelijk gebruikt voor **interne** LOB-apps (Line-Of-Business). Het hulpprogramma is een opdrachtregeltoepassing waarmee een wrapper rond de app wordt gemaakt, zodat de app vervolgens kan worden beheerd door app-beveiligingsbeleid van Intune. Bij het beveiligen van een app die is geleverd door een ISV (onafhankelijke softwareleverancier) is het belangrijk om te achterhalen of de ISV de verpakte app nog ondersteunt.

Om het hulpprogramma te kunnen gebruiken, hebt u de broncode niet nodig, maar wel ondertekeningsreferenties. Zie het [Intune-blog](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/) voor meer informatie over ondertekeningsreferenties. Zie [Android App Wrapping Tool ](app-wrapper-prepare-android.md) en [iOS App Wrapping Tool](app-wrapper-prepare-ios.md) voor informatie over de App Wrapping Tool.

De App Wrapping Tool biedt **geen** ondersteuning voor apps in de Apple App Store of Google Play Store. De tool biedt ook geen ondersteuning voor bepaalde functies waarvoor ontwikkelaarsintegratie vereist is (zie de volgende functievergelijkingstabel).

Zie [Line-Of-Business-apps en -gegevens beveiligen op apparaten die niet zijn geregistreerd bij Microsoft Intune](../apps/apps-add.md) voor meer informatie over de App Wrapping Tool voor app-beveiligingsbeleid op apparaten die niet zijn geregistreerd bij Intune.

### <a name="reasons-to-use-the-app-wrapping-tool"></a>Redenen om de App Wrapping Tool te gebruiken

* Uw app heeft geen ingebouwde functies voor gegevensbescherming
* Uw app is eenvoudig
* Uw app wordt intern geïmplementeerd
* U hebt geen toegang tot de broncode van de app
* U hebt de app niet ontwikkeld
* De gebruikersverificatie van uw app is minimaal

### <a name="supported-app-development-platforms"></a>Ondersteunde platforms voor app-ontwikkeling

|**App Wrapping Tool** | **Xamarin** |**Cordova** |
|------|----|----|
|**iOS** |Yes|Yes|
|**Android**|Nee, gebruik de [Intune App SDK Xamarin Bindings](app-sdk-xamarin.md).|Ja|

## <a name="intune-app-sdk"></a>Intune App SDK

De App SDK is hoofdzakelijk ontworpen voor klanten die apps in de Apple App Store of Google Play Store hebben en hun apps willen beheren met Intune. Elke app kan echter profiteren van integratie van de SDK, zelfs als het een Line-Of-Business app is.

Zie [Overzicht](app-sdk.md) voor meer informatie over de SDK. Zie [Aan de slag met de Microsoft Intune App SDK](app-sdk-get-started.md) om aan de slag te gaan met de SDK.

### <a name="reasons-to-use-the-sdk"></a>Redenen om de SDK te gebruiken

* Uw app heeft geen ingebouwde functies voor gegevensbescherming
* Uw app is complex en bevat veel ervaringen
* Uw app is geïmplementeerd op een openbare app-store, zoals Google Play of de App Store van Apple
* U bent app-ontwikkelaar en beschikt over de technische achtergrond om de SDK te gebruiken
* Uw app bevat andere SDK-integraties
* Uw app wordt regelmatig bijgewerkt

### <a name="supported-app-development-platforms"></a>Ondersteunde platforms voor app-ontwikkeling

|**Intune App SDK** |**Xamarin** |**Cordova**
|------|----|----|
|**iOS**|Ja, gebruik de [Intune App SDK Xamarin Bindings](app-sdk-xamarin.md).|Nee|
|**Android**| Ja, gebruik de [Intune App SDK Xamarin Bindings](app-sdk-xamarin.md).|Nee|

### <a name="not-using-an-app-development-platform-listed-above"></a>Maakt u geen gebruik van een app-ontwikkelings platform dat hierboven wordt vermeld?

Het Intune SDK-ontwikkelingsteam houdt zich actief bezig met het testen en onderhouden van ondersteuning voor apps die zijn gebouwd met de systeemeigen Android-, iOS- (Objective-C, Swift), Xamarin-, Xamarin.Forms- en Cordova-platforms. Hoewel het sommige klanten is gelukt om de Intune SDK te integreren in andere platforms, zoals React Native en NativeScript, bieden we geen specifieke instructies of plug-ins voor app-ontwikkelaars die andere platforms gebruiken dan de platforms die door ons worden ondersteund. 

## <a name="feature-comparison"></a>Vergelijking van functies

In deze tabel staan de instellingen die u kunt gebruiken voor de App SDK en de App Wrapping Tool.

|Onderdeel|App SDK|App Wrapping Tool|
|-----------|---------------------|-----------|
|Webinhoud beperken en weergeven in een bedrijfsbeheerde browser|X|X|
|Back-ups verhinderen van Android, iTunes of iCloud|X|X|
|App mag gegevens overdragen naar ander apps|X|X|
|App mag gegevens ontvangen van andere apps|X|X|
|Knippen, kopiëren en plakken met andere apps beperken|X|X|
|Geef het aantal tekens op dat mag worden geknipt of gekopieerd uit een beheerde app|X|X|
|Eenvoudige pincode vereisen voor toegang|X|X|
|Het aantal pogingen opgeven voordat de pincode opnieuw wordt ingesteld|X|X|
|Vingerafdruk in plaats van pincode toestaan|X|X|
|Gezichtsherkenning toestaan in plaats van pincode (alleen iOS)|X|X|
|Bedrijfsreferenties vereisen voor toegang|X|X|
|Verlopen van een pincode instellen|X|X|
|De uitvoering blokkeren van beheerde apps die op gekraakte of geroote apparaten worden uitgevoerd|X|X|
|App-gegevens versleutelen|X|X|
|De toegangsvereisten na een opgegeven aantal minuten opnieuw controleren|X|X|
|De offlinerespijtperiode opgeven|X|X|
|Schermafbeeldingen maken blokkeren (alleen Android)|X|X|
|Ondersteuning van MAM zonder apparaatinschrijving|X|X|
|Volledig wissen van app-gegevens|X|X|
|Selectief wissen van werk- en schoolgegevens in scenario's met meerdere identiteiten <br><br>**Opmerking:** bij iOS geldt dat als het beheerprofiel wordt verwijderd, ook de app wordt verwijderd.|X||
|'Opslaan als' voorkomen|X||
|Configuratie van de doel toepassing (of app-configuratie via het ' MAM-kanaal ')|X||
|Ondersteuning voor meerdere identiteiten|X||
|Aanpasbare stijl |X|||
|VPN-verbindingen met Citrix mVPN op aanvraag voor toepassingen|X|X| 
|Synchroniseren van contactpersonen uitschakelen|X|X|
|Afdrukken uitschakelen|X|X|
|Minimumversie van app vereisen|X|X|
|Minimumversie van het iOS-besturingssysteem vereisen|X|X|
|Minimale versie van Android-beveiligingspatch vereisen (alleen Android)|X|X|
|Minimale Intune SDK voor iOS vereisen (alleen iOS)|X|X|
|Attestation van SafetyNet-apparaten (alleen Android)|X|X|
|Bedreigings scan voor apps (alleen Android)|X|X|

## <a name="next-steps"></a>Volgende stappen

Meer informatie over app-beveiligingsbeleid en Intune kunt u vinden in de volgende onderwerpen:

- [Android App Wrapping Tool](app-wrapper-prepare-android.md)<br>
- [iOS App Wrapping Tool](app-wrapper-prepare-ios.md)<br>
- [De SDK gebruiken om apps geschikt te maken voor Mobile Application Management](app-sdk.md)
