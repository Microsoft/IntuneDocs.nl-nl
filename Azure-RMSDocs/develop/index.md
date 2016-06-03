---
# required metadata

title: RMS-handleiding voor ontwikkelaars | Azure RMS
description: Er zijn nu drie generaties van de Rights Management SDK beschikbaar.
keywords:
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 0510ead4-2fe7-4269-885b-fe16bcc69888
# optional metadata

#ROBOTS:
audience: developer
#ms.devlang:
ms.reviewer: shubhamp
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# RMS-handleiding voor ontwikkelaars

## Overzicht ##
Er zijn nu drie generaties van de Rights Management SDK beschikbaar: **Microsoft Rights Management SDK 4.2** voor Android-, iOS-/OS X-, Windows- en Linux-apparaten, **Microsoft Rights Management SDK 2.1** voor de Windows-computerclient en de vervangen **AD RMS SDK**.

## Software Development Kits ##
| SDK | Beschrijving |
|------|---------|
| [RMS SDK 4.2](active-directory-rights-management-services-multi-platform-thin-client-sdk-portal.md) | Een vereenvoudigde set hulpprogramma’s van de volgende generatie die basisfunctionaliteit voor ontwikkeling biedt voor het inschakelen van gegevensbeveiliging via Microsoft Rights Management-services op uw apparaatapps met Android, iOS, Mac OS X, Windows Phone/RT en Linux/C++ |
| [RMS SDK 2.1](microsoft-information-protection-and-control-client-portal.md) | Een krachtige SDK die ontwikkelaars van Windows-bureaubladtoepassingen en providers van servergebaseerde oplossingen in staat stelt hun producten te voorzien van Rights Management|
|[AD RMS SDK]()|**OPMERKING**: functionaliteit die gebruikmaakt van AD RMS SDK die door de client beschikbaar wordt gesteld in Msdrm.dll, is beschikbaar voor gebruik in Windows Server 2012, Windows 8, Windows Server 2008 R2, Windows 7, Windows Server 2008 en Windows Vista. De functionaliteit is mogelijk gewijzigd of niet beschikbaar in latere versies. Gebruik in plaats daarvan de Microsoft Rights Management Services SDK 2.1, die gebruikmaakt van functionaliteit die beschikbaar wordt gesteld door de client in Msipc.dll.|
|[AD RMS script-API]()| Wordt gebruikt voor het maken van scripts voor het beheren van een AD RMS-installatie|

## Codevoorbeelden en hulpprogramma 's ##
Deze verzameling van door Microsoft RMS meegeleverde codevoorbeelden en hulpprogramma’s voor ontwikkelaars is geschikt voor alle ondersteunde besturingssystemen (Android, iOS/OS X , Windows Phone en Windows Desktop) en wordt regelmatig bijgewerkt om compatibiliteit met de ondersteunde SDK te handhaven.

| Item | Besturingssysteem | Ondersteunende SDK-versie | Beschrijving |
|------|------------------|------------------------|-------------|
| [Met PFILE beveiligde PDF-bestanden lezen](https://blogs.msdn.microsoft.com/rms/2015/11/09/reading-a-pfile-protected-pdf/) | Windows 10 Desktop| [RMS SDK 2.1](microsoft-information-protection-and-control-client-portal.md) en nieuwere versies van de SDK 2.x | **Read PFILE protected PDF** is een eenvoudig codevoorbeeld op ons blog RMS Developer’s Corner dat gebruikmaakt van MSIPC bestands-API om een met PFILE beveiligd PDF-document te ontsleutelen en te openen.|
| [IpcManagedAPI](https://github.com/Azure-Samples/active-directory-dotnet-rms) | Windows 10 Desktop | [RMS SDK 2.1](microsoft-information-protection-and-control-client-portal.md) en nieuwere versies van de SDK 2.x | **IpcManagedAPI** is een .NET-weergave (C#) van RMS SDK 2.1 waarmee u uw beheerde toepassing eenvoudig kunt inschakelen voor RMS.|
| [IPCNotepad](https://code.msdn.microsoft.com/ipcnotepad-sample-f67dae80) | Windows 10 Desktop | [RMS SDK 2.1](microsoft-information-protection-and-control-client-portal.md) en nieuwere versies van de SDK 2.x| **IPCNotepad** is een voorbeeldtoepassing met RMS die u door de basisstappen leidt die voor elke toepassing met RMS moeten worden uitgevoerd bij het beveiligen en gebruiken van beperkte inhoud.|
| [IpcDlp](https://github.com/Azure-Samples/active-directory-dotnet-rms)|Windows 10 Desktop|[RMS SDK 2.1](microsoft-information-protection-and-control-client-portal.md) en nieuwere versies van de SDK 2.x|**IpcDlp** is een voorbeeld van een DLP-toepassing (Data Leak Protection) met RMS die u door de basisstappen leidt die voor elke toepassing met DLP-RMS moeten worden uitgevoerd met behulp van de bestands-API bij het beveiligen en gebruiken van beperkte inhoud.|
| [IpcAzureApp](https://github.com/Azure-Samples/active-directory-dotnet-rms) | Windows 10 Desktop|[RMS SDK 2.1](microsoft-information-protection-and-control-client-portal.md) en nieuwere versies van de SDK 2.x|**IpcAzureApp** is een voorbeeldtoepassing die u laat zien hoe u RMS SDK in de Azure-toepassing gebruikt voor het beveiligen van gegevens in Azure Blob Storage.|
| [RmsDocumentInspector](https://github.com/Azure-Samples/active-directory-dotnet-rms) | Windows 10 Desktop|[RMS SDK 2.1](microsoft-information-protection-and-control-client-portal.md) en nieuwere versies van de SDK 2.x|**RmsDocumentInspector** is een hulpprogramma dat informatie kan bieden over elk met RMS beveiligd bestand, zoals de inhouds-id of gebruikersrechten.|
| [RmsFileWatcher](https://github.com/Azure-Samples/active-directory-dotnet-rms) | Windows 10 Desktop|[RMS SDK 2.1](microsoft-information-protection-and-control-client-portal.md) en nieuwere versies van de SDK 2.x|**RmsFileWatcher** is een voorbeeldtoepassing die u laat zien hoe u een Windows-toepassing bouwt die de mappen in het bestandssysteem controleert en RMS-beveiligingsbeleid toepast op elke wijziging, bijvoorbeeld een toegevoegd bestand of een gewijzigd bestand.|
| [Gebruiksscenario's in iOS/OS X](https://msdn.microsoft.com/en-us/library/dn758307(v=vs.85).aspx) |iOS/OS X|[RMS SDK 4.2](active-directory-rights-management-services-multi-platform-thin-client-sdk-portal.md) en nieuwere versies van de SDK 4.x|De **Objective-C**-codevoorbeelden geven belangrijke ontwikkelscenario's weer om u vertrouwd te maken met de RMS SDK. Voorbeelden zijn onder meer gebruik van de door Microsoft beveiligde bestandsindeling, aangepaste beveiligde bestandsindelingen en aangepaste UI-besturingselementen.|
| [UI-bibliotheek en voorbeeld-app](https://github.com/AzureAD/rms-sdk-ui-for-ios) |iOS|[RMS SDK 4.2](active-directory-rights-management-services-multi-platform-thin-client-sdk-portal.md) en nieuwere versies van de SDK 4.x|**UI-bibliotheken en voorbeeld-app voor iOS** op GitHub, zodat u snel aan de slag kunt en onze standaardgebruikersinterface in uw apps kunt hergebruiken.|
| [UI-bibliotheek en voorbeeld-app](https://github.com/AzureAD/rms-sdk-ui-for-android) |Android|[RMS SDK 4.2](active-directory-rights-management-services-multi-platform-thin-client-sdk-portal.md) en nieuwere versies van de SDK 4.x|**UI-bibliotheken en voorbeeld-app voor Android** op GitHub, zodat u snel aan de slag kunt en onze standaardgebruikersinterface in uw apps kunt hergebruiken.|
| [Gebruiksscenario’s in Android](https://msdn.microsoft.com/en-us/library/dn758246(v=vs.85).aspx) |Android|[RMS SDK 4.2](active-directory-rights-management-services-multi-platform-thin-client-sdk-portal.md) en nieuwere versies van de SDK 4.x|**De Java-codevoorbeelden** geven belangrijke ontwikkelscenario's weer om u vertrouwd te maken met de RMS SDK. Voorbeelden zijn onder meer gebruik van de door Microsoft beveiligde bestandsindeling, aangepaste beveiligde bestandsindelingen en aangepaste UI-besturingselementen.|


<!--HONumber=Apr16_HO4-->


