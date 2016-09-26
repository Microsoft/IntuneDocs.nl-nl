---
title: Apps geschikt maken voor beheer van mobiele apps | Microsoft Intune
description: Aan de hand van de informatie in dit onderwerp kunt u beslissen wanneer u het hulpmiddel App Wrapping en de App SDK moet gebruiken om uw aangepaste LOB-apps in te schakelen voor gebruik van de beleidsregels voor het beheren van mobiele apps.
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: oldang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 70f9fb5580b114fe1ba14a1bd05de58467d5cd00
ms.openlocfilehash: b5dd5bec0910a8ce3a940b5ed288907aba0f7ee4


---

# Bepalen hoe u apps met Microsoft Intune voorbereidt op Mobile Application Management
U kunt uw apps gebruik laten maken van Mobile Application Management-beleid (MAM) door de Intune App Wrapping Tool of de Intune App SDK te gebruiken. In deze informatie wordt uitgelegd hoe en wanneer u deze twee methoden gebruikt.

## Intune App Wrapping Tool
De App Wrapping Tool wordt hoofdzakelijk gebruikt voor interne LOB-apps (Line-Of-Business-apps). Het hulpprogramma is een opdrachtregeltoepassing waarmee een wrapper rond de app wordt gemaakt, zodat de app vervolgens kan worden beheerd door Intune Mobile Application Management-beleid. Om het hulpprogramma te kunnen gebruiken, hebt u de broncode niet nodig, maar wel ondertekeningsreferenties.  Zie het [Intune-blog](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/) voor meer informatie over ondertekeningsreferenties. Zie [Android App Wrapping Tool ](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) en [iOS App Wrapping Tool](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) voor documentatie over de App Wrapping Tool.

De App Wrapping Tool biedt geen ondersteuning voor apps in de App Store of Play Store of voor functies waarvoor ontwikkelingstijdintegratie is vereist (zie de volgende functievergelijkingstabel).

U moet de App Wrapping Tool in plaats van de SDK gebruiken als de app al is geschreven of als de broncode niet beschikbaar is.

**De App Wrapping Tool voor MAM op apparaten die niet bij Intune worden geregistreerd, wordt momenteel in de openbare preview-versie ondersteund. Zie voor meer informatie het onderwerp [Protect LOB apps on devices not enrolled in Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md) (LOB-apps beveiligen op apparaten die niet zijn geregistreerd bij Microsoft Intune)**.

### Ondersteunde platformen

|**App Wrapping Tool** | **Xamarin** |**Cordova** |
|------|----|----|
|**iOS** |Yes|Yes|
|**Android**| Nee |Yes|
## Intune App SDK
De App SDK is hoofdzakelijk ontworpen voor klanten die apps in de App Store of Play Store hebben en hun apps willen beheren met Intune. Elke app kan echter profiteren van integratie van de SDK, zelfs als het een LOB-app is.

Zie [Overzicht](/intune/develop/intune-app-sdk) voor meer informatie over de SDK. Zie [Aan de slag met de Microsoft Intune App SDK](/intune/develop/intune-app-sdk-get-started) om aan de slag te gaan met de SDK.

### Ondersteunde platformen
|**Intune App SDK** |**Xamarin** |**Cordova**
|------|----|----|
|**iOS**|Ja, gebruik het Xamarin-onderdeel van de Intune App SDK|Ja, gebruik de Cordova-invoegtoepassing van de Intune App SDK|
|**Android**| Ja, gebruik het Xamarin-onderdeel van de Intune App SDK|Ja, gebruik de Cordova-invoegtoepassing van de Intune App SDK|

## Vergelijking van functies
In deze tabel staan de instellingen die u kunt gebruiken voor de App SDK en de App Wrapping Tool.

> [!NOTE]
> De App Wrapping Tool kan worden gebruikt met Intune Standalone of Intune met Configuration Manager.

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
|Vingerafdruk vereisen in plaats van pincode (alleen iOS)<br></br>**Opmerking:** uitsluitend beschikbaar in omgevingen met alleen MAM.|X||
|Bedrijfsreferenties vereisen voor toegang|X|X|
|De uitvoering blokkeren van beheerde apps die op gekraakte of geroote apparaten worden uitgevoerd|X|X|
|App-gegevens versleutelen|X|X|
|De toegangsvereisten na een opgegeven aantal minuten opnieuw controleren|X|X|
|De offlinerespijtperiode opgeven|X|X|
|Schermafbeeldingen maken blokkeren (alleen Android)|X|X|
|Volledig wissen|X|X|
|Selectief wissen <br></br>**Opmerking:** bij iOS geldt dat als het beheerprofiel wordt verwijderd, ook de app wordt verwijderd.|X||
|'Opslaan als' voorkomen |X||
|Ondersteuning voor meerdere identiteiten|X||
### Zie tevens

[Android App Wrapping Tool](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[iOS App Wrapping Tool](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[Gebruik de SDK om apps geschikt te maken voor Mobile Application Management](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Sep16_HO2-->


