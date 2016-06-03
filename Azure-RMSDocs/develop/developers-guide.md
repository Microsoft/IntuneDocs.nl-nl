---
# required metadata

title: Handleiding voor ontwikkelaars | Azure RMS
description: Overzicht van hulpprogramma's voor ontwikkelaars; SDK's, aanvullende bibliotheken en codevoorbeelden.
keywords:
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: a22e6bd0-8ce8-45b4-9a32-273126ab831e
# optional metadata

#ROBOTS:
audience: developer
#ms.devlang:
ms.reviewer: shubhamp
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Handleiding voor ontwikkelaars

## Overzicht ##
Deze handleiding bevat een overzicht van onze suite van Rights Management SDK's en een toenemende verzameling hulpprogramma's en codevoorbeelden voor alle ondersteunde platforms. 

## Software Development Kits ##
Er zijn nu drie generaties van de RMS SDK beschikbaar, zoals beschreven in de volgende tabel.

| SDK | Beschrijving |
|------|---------|
| [RMS SDK 4.2](active-directory-rights-management-services-multi-platform-thin-client-sdk-portal.md) | Een vereenvoudigde set hulpprogramma’s van de volgende generatie die basisfunctionaliteit voor ontwikkeling biedt voor het inschakelen van gegevensbeveiliging via Microsoft Rights Management Services op uw apparaat-apps met Android, iOS, Mac OS X-, Windows Phone/RT en Linux/C++. |
| [RMS SDK 2.1](microsoft-information-protection-and-control-client-portal.md) | Een krachtige SDK die ontwikkelaars van Windows-bureaubladtoepassingen en providers van servergebaseerde oplossingen in staat stelt hun producten te voorzien van Rights Management.|
|[AD RMS SDK](https://msdn.microsoft.com/en-us/library/cc530379(v=vs.85).aspx)|** OPMERKING **: functionaliteit die gebruikmaakt van de AD RMS SDK en door de client beschikbaar wordt gesteld in Msdrm.dll, is beschikbaar voor gebruik in Windows Server 2012, Windows 8, Windows Server 2008 R2, Windows 7, Windows Server 2008 en Windows Vista. Dergelijke functionaliteit is in latere versies mogelijk gewijzigd of niet beschikbaar. Gebruik in plaats daarvan de Microsoft Rights Management Services SDK 2.1, die gebruikmaakt van functionaliteit die door de client beschikbaar wordt gesteld in Msipc.dll.|
|[AD RMS script-API](https://msdn.microsoft.com/en-us/library/bb968797(v=vs.85).aspx)| Wordt gebruikt voor het maken van scripts voor het beheren van een AD RMS-installatie.|

## Codevoorbeelden en hulpprogramma 's
Deze verzameling van door Microsoft RMS meegeleverde codevoorbeelden en ondersteuningsprogramma’s voor ontwikkelaars beslaat alle ondersteunde besturingssystemen (Android, iOS/OS X , Windows Phone en Windows Desktop) en wordt regelmatig bijgewerkt om compatibiliteit met de ondersteunde SDK te handhaven.

### Android

De volgende hulpprogramma’s worden uitgevoerd op Android en ondersteund door de [RMS SDK 4.2](active-directory-rights-management-services-multi-platform-thin-client-sdk-portal.md) en hogere versies van de 4.x SDK.

- [UI-bibliotheek en voorbeeldapp](https://github.com/AzureAD/rms-sdk-ui-for-android) op GitHub, dus u kunt snel aan de slag en onze standaardgebruikersinterface in uw apps hergebruiken.
- [Android-gebruiksscenario's](https://msdn.microsoft.com/en-us/library/dn758246(v=vs.85).aspx) in Java geven belangrijke ontwikkelscenario's weer om u vertrouwd te maken met de RMS SDK. Voorbeelden zijn onder meer gebruik van de door Microsoft beveiligde bestandsindeling, aangepaste beveiligde bestandsindelingen en aangepaste UI-besturingselementen.

### iOS/OS X

De volgende hulpprogramma’s worden uitgevoerd op iOS/OS X en ondersteund door de [RMS SDK 4.2](active-directory-rights-management-services-multi-platform-thin-client-sdk-portal.md) en hogere versies van de 4.x SDK.

- [iOS-/OS X-gebruiksscenario's](https://msdn.microsoft.com/en-us/library/dn758307(v=vs.85).aspx) in Objective C geven belangrijke ontwikkelscenario's weer om u vertrouwd te maken met de RMS SDK. Voorbeelden zijn onder meer gebruik van de door Microsoft beveiligde bestandsindeling, aangepaste beveiligde bestandsindelingen en aangepaste UI-besturingselementen.
- [UI-bibliotheek en voorbeeldapp](https://github.com/AzureAD/rms-sdk-ui-for-ios) op GitHub, dus u kunt snel aan de slag en onze standaardgebruikersinterface in uw apps hergebruiken. Alleen ondersteund voor **iOS**.

### Windows 10 Desktop

De volgende hulpprogramma’s worden uitgevoerd op Windows Desktop en ondersteund door de [RMS SDK 2.1](microsoft-information-protection-and-control-client-portal.md) en hogere versies van de 2.x SDK.

- [Read PFILE protected PDF](https://blogs.msdn.microsoft.com/rms/2015/11/09/reading-a-pfile-protected-pdf/) is een eenvoudig codevoorbeeld op ons blog voor RMS-ontwikkelaars dat gebruikmaakt van het bestand MSIPC API om een met PFILE beveiligd PDF-document te ontsleutelen en te openen.
- [IpcManagedAPI](https://github.com/Azure-Samples/active-directory-dotnet-rms) is een .NET (C#)-weergave van de RMS SDK 2.1 waarmee u uw beheerde toepassing eenvoudig kunt inschakelen voor RMS.
- [IPCNotepad](https://code.msdn.microsoft.com/ipcnotepad-sample-f67dae80) is een voorbeeldtoepassing met RMS die u door de basisstappen leidt die voor elke toepassing met RMS moeten worden uitgevoerd voor het beveiligen en gebruiken van beperkte inhoud.
- [IpcDlp](https://github.com/Azure-Samples/active-directory-dotnet-rms) is een voorbeeld van een DLP-toepassing (Data Leak Protection) met RMS die u door de basisstappen leidt die voor elke toepassing met DLP-RMS moeten worden uitgevoerd met behulp van de bestands-API voor het beveiligen en gebruiken van beperkte inhoud.
- [IpcAzureApp](https://github.com/Azure-Samples/active-directory-dotnet-rms) is een voorbeeldtoepassing die u laat zien hoe u de RMS SDK in de Azure-toepassing gebruikt voor het beveiligen van gegevens in Azure Blob-opslag.
- [RmsDocumentInspector](https://github.com/Azure-Samples/active-directory-dotnet-rms) is een hulpprogramma dat informatie kan geven over elk met RMS beveiligd bestand, zoals de inhouds-id of de gebruikersrechten.
- [RmsFileWatcher](https://github.com/Azure-Samples/active-directory-dotnet-rms) is een voorbeeldtoepassing die u laat zien hoe u een Windows-toepassing bouwt die de mappen in het bestandssysteem controleert en RMS-beveiligingsbeleid toepast op elke wijziging, bijvoorbeeld een toegevoegd bestand of een gewijzigd bestand.

### Windows Store en Phone

- [UI-bibliotheek voor Windows Store](https://github.com/AzureAD/rms-sdk-ui-for-windowsstore): een UI-bibliotheek voor de Microsoft RMS SDK v4.1 voor Windows Store-toepassingen. Deze bibliotheek is optioneel en een ontwikkelaar kan ervoor kiezen een eigen gebruikersinterface te bouwen bij gebruik van de Microsoft RMS SDK v4.1.

- [UI-bibliotheek voor Windows Phone](https://github.com/AzureAD/rms-sdk-ui-for-winphone): een UI-bibliotheek voor de Microsoft RMS SDK v4.1 voor Windows Phone-toepassingen. Deze bibliotheek is optioneel en een ontwikkelaar kan ervoor kiezen een eigen gebruikersinterface te bouwen bij gebruik van de Microsoft RMS SDK v4.1.

- [Voorbeeldtoepassing](https://github.com/Azure-Samples/active-directory-dotnet-rms-windowsstore): de voorbeeldtoepassing voor de Microsoft RMS SDK v4.1 voor Windows Store-toepassingen biedt een voorbeeld van basisdocumentgebruik voor het platform.


<!--HONumber=Apr16_HO4-->


