---
# required metadata

title: Bepalen hoe u apps met Microsoft Intune voorbereidt op Mobile Application Management | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Bepalen hoe u apps met Microsoft Intune voorbereidt op Mobile Application Management
U kunt uw apps gebruik laten maken van Mobile Application Management-beleid door de Intune App Wrapping Tool of de Intune App SDK te gebruiken. In deze informatie wordt uitgelegd hoe en wanneer u deze twee methoden gebruikt.

## Intune App Wrapping Tool
De App Wrapping Tool wordt hoofdzakelijk gebruikt voor interne LOB-apps (Line-Of-Business-apps). Het hulpprogramma is een opdrachtregeltoepassing waarmee een wrapper rond de app wordt gemaakt, zodat de app vervolgens kan worden beheerd door Intune Mobile Application Management-beleid. Om het hulpprogramma te kunnen gebruiken, hebt u de broncode niet nodig, maar wel ondertekeningsreferenties.  Zie het [Intune-blog](http://blogs.technet.com/b/microsoftintune/archive/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios.aspx) voor meer informatie over ondertekeningsreferenties. Zie [Android App Wrapping Tool ](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) en [iOS App Wrapping Tool](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) voor documentatie over de App Wrapping Tool.

De App Wrapping Tool biedt geen ondersteuning voor apps in de App Store of Play Store of voor functies waarvoor ontwikkelingstijdintegratie is vereist (zie de volgende functievergelijkingstabel).

U moet de App Wrapping Tool in plaats van de SDK gebruiken als de app al is geschreven of als de broncode niet beschikbaar is.

## Intune App SDK
De App SDK is hoofdzakelijk ontworpen voor klanten die apps in de App Store of Play Store hebben en hun apps willen beheren met Intune. Elke app kan echter profiteren van integratie van de SDK, zelfs als het een LOB-app is.

Voor het integreren van de SDK moet u toegang hebben tot de broncode van de app. Zie [Microsoft Intune App SDK](https://msdn.microsoft.com/library/mt627769.aspx) voor instructies over het integreren van de SDK..

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


<!--HONumber=May16_HO1-->


