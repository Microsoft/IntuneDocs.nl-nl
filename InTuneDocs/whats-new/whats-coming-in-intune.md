---
title: De vroege editie | Microsoft Intune
description: 
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 10/05/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a5c4b0f15456a9f24c95954d669a17c63f96a459
ms.openlocfilehash: 273016d4fe114bbe60e9cebc06e89584c8f91f0b


---

# Binnenkort in Microsoft Intune - oktober
De **Vroege editie** bevat een lijst met functies die worden toegevoegd aan toekomstige releases van Microsoft Intune. Deze informatie wordt in zeer beperkte mate onder geheimhoudingsverklaring verstrekt en kan worden gewijzigd. Sommige functies die hier worden vermeld, zullen mogelijk niet beschikbaar zijn op de sluitingsdatum en worden mogelijk beschikbaar gesteld in een latere release. Andere functies worden getest in een proefversie, zodat we zeker weten dat ze in gebruik kunnen worden genomen. Neem bij vragen contact op met uw contactpersoon voor Intune/projectmanagement.

Deze pagina wordt regelmatig bijgewerkt. Kom daarom om de tijd terug om te zien of er nieuws is over wat er binnenkort beschikbaar is.

De volgende wijzigingen worden momenteel ontwikkeld voor Intune. Al deze functies worden uiteindelijk ondersteund voor implementaties voor hybride klanten (Configuration Manager met Intune). Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

### Afdrukbeheer voor apps die worden beheerd met MAM-beleid
U kunt nu voorkomen dat bedrijfsgegevens worden afgedrukt met apps waarop een MAM-beleid van toepassing is. Deze instelling is beschikbaar op de [Azure-portal](..deployuse/create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) en werkt met zowel [iOS](..deployuse/ios-mam-policy-settings)- als [Android](..deployuse/android-mam-policy-settings)-apparaten.
<!--TFS 1014328-->

### Nieuwe Microsoft Intune-bedrijfsportal voor Windows 10-apparaten
Microsoft brengt een nieuwe Microsoft Intune-bedrijfsportal voor Windows 10-apparaten uit. Deze app maakt gebruik van de Windows 10 Universal-indeling en biedt gebruikers een bijgewerkte gebruikerservaring in de app zelf, en een identieke gebruikerservaring op alle Windows 10-apparaten (pc en mobiel), met behoud van de functionaliteit die ze momenteel gebruiken.

Met de nieuwe app kunnen gebruikers van Windows 10-apparaten ook gebruikmaken van aanvullende functies van het platform, zoals eenmalige aanmelding (SSO) en verificatie op basis van certificaten. De app wordt beschikbaar gesteld als een upgrade van de bestaande Windows 8.1-bedrijfsportal en Windows Phone 8.1-bedrijfsportal in de Windows Store.
<!--TFS 1016502-->

### Ondersteuning van Android for Work

Intune is nu onderdeel van het [Android for Work-programma](https://enterprise.google.com/android/partners/). De ondersteuning van Intune voor de functies van het Android for Work-programma wordt met ingang van deze maand geïmplementeerd.

[Lees de aankondiging van Microsoft over ondersteuning van Intune voor Android for Work](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

<!---This month, some newly provisioned Intune tenants will start seeing the Android for Work features. We will announce later when existing tenants will begin to see this feature.--->
<!--TFS 1043303-->

### Compatibiliteit van Android Samsung KNOX met Intune

Bepaalde modellen van de Samsung Galaxy Ace-telefoon kunnen niet als Samsung KNOX-apparaat worden beheerd door Intune. Wanneer u deze apparaten registreert bij Intune, worden ze beheerd als standaard Android-apparaten.
De betrokken modelnummers zijn:

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

U en uw eindgebruikers hoeven niets te doen.
Ga voor meer informatie naar de [Samsung KNOX](https://www.samsungknox.com)-website.

<!--TFS 1173566 iX blurb provided by Barry; requires PM signoff

### Multi-factor authentication for Android and iOS enrollment

In addition to Windows 8.1 and later, administrators can now enable multi-factor authentication for Android and iOS devices in the Microsoft Intune Enrollment application. -->    

### De bedrijfsportal-app voor Windows 8 wordt afgeschaft; ondersteuning voor Windows Phone 8 en Windows RT-platformen wordt afgeschaft
Vanaf oktober 2016 biedt Microsoft Intune geen ondersteuning meer voor de Windows 8-bedrijfsportal. Microsoft Intune biedt dan ook geen ondersteuning meer voor het Windows Phone 8- en Windows RT-platform. Als gevolg hiervan kunt u geen Windows Phone 8- of Windows RT-apparaten meer registreren of bijwerken.

U kunt Windows Phone 8-, Windows RT- en Windows 8-apparaten die al zijn geregistreerd blijven beheren. Werk Windows 8- en Windows Phone 8-apparaten bij naar Windows 8.1 en Windows Phone 8.1. Gebruik de bijbehorende bedrijfsportal-apps voor Windows 8.1 en Windows Phone 8.1 om zonder onderbrekingen door te gaan met het distribueren van apps naar deze apparaten.

Vanaf november 2016 bieden we geen ondersteuning meer voor de Windows Phone 8-bedrijfsportal.
<!--TFS 1255391-->

### Voorwaardelijke toegang voor beheer van mobiele toepassingen
U kunt nu voorwaardelijk toegangsbeleid creëren om te voorkomen dat onbeheerde mobiele toepassingen toegang hebben tot [Exchange Online](..deployuse/restrict-access-to-exchange-online-with-microsoft-intune.md) en [SharePoint Online](..deployuse/restrict-access-to-sharepoint-online-with-microsoft-intune.md). U kunt de ingebouwde e‑mailclients en apps blokkeren waarvoor MAM niet is ingeschakeld met de Intune App SDK.  Dit doet u door via de Azure-portal een beleid voor voorwaardelijke toegang te maken, waarbij u de toepassingen opgeeft die u toegang wilt geven tot Exchange Online en SharePoint Online.
<!--TFS 1317673-->

<!--TFS 1318014; awaiting approval in notes as to whether to proceed

### "Default" policy is deprecated

To minimize unintentionally assigned profiles, Intune is removing support for the "default" Corporate Device Enrollment profile for Apple Device Enrollment Program (DEP) device serial numbers in the new Azure console. Serial numbers synchronized from an Apple DEP account will initially have no Corporate Device Enrollment profile assigned.  A profile must be assigned manually after synchronization. This change will apply to the new console only. Until the existing Admin console is retired, no change will take place.
-->

<!--TFS 1318023; awaiting approval in notes as to whether to proceed

### Deprecation of row-by-row iOS Details review for iOS device CSV uploads

In order to streamline uploading IMEI numbers for Corporate devices and Apple serial numbers for Configurator enrollment, Intune is removing the row by row review of hardware identifiers already found in the system. This review allows the IT Pro to accept associated Details from the CSV to overwrite the existing details for a hardware identifier already in the system. The review will be replaced by a single option to automatically overwrite Details for all hardware identifiers or ignore new details for existing identifiers. This change will apply to the new console only. Until the existing Admin console is retired, no change will take place.
-->

### Lookout-integratie om iOS-apparaten te beveiligen
In oktober integreert Microsoft met de oplossing voor beveiliging tegen mobiele bedreigingen van Lookout, om mobiele iOS-apparaten te beveiligen door detectie van bijvoorbeeld malware en riskante apps op apparaten. De oplossing van Lookout helpt u het (configureerbare) risiconiveau te bepalen. U kunt een beleidsregel in Intune maken om de apparaatnaleving te bepalen op basis van de risicoanalyse door Lookout. Met behulp van beleid voor voorwaardelijke toegang kunt u toegang tot bedrijfsbronnen toestaan of blokkeren op basis van de apparaatnalevingsstatus.

Eindgebruikers van iOS-apparaten die niet voldoen aan het beleid, moeten hun apparaten inschrijven en de Lookout for Work-toepassing op hun apparaten installeren, de app activeren en bedreigingen verhelpen die zijn gerapporteerd in de Lookout for Work-toepassing om toegang te krijgen tot bedrijfsgegevens.
<!--TFS 1319493-->

### Intune App SDK en App Wrapping Tool voor Android
U kunt uw apps gebruik laten maken van Mobile Application Management-beleid (MAM) van Intune door de Intune App Wrapping Tool of de Intune App SDK te gebruiken. Nieuwe updates voor de App Wrapping Tool en SDK zijn onder andere:

* Ondersteuning voor Android N
* Ondersteuning voor MAM-beleid van Intune zonder apparaatregistratie
* Ondersteuning voor Android-apps op basis van Xamarin

U kunt hier de ondersteuning voor MAM zonder apparaatregistratie en Xamarin testen met de openbare preview-versie van de Android Wrapping Tool: [https://github.com/msintuneappsdk/intune-app-wrapper-android-preview](https://github.com/msintuneappsdk/intune-app-wrapper-android-preview).
<!--TFS 1319511; please create new TFS entry for WN text associated with this TFS item-->

<!--TFS 1319613; no iX review on PM text blurb

### Private preview customers using MAM Conditional Access will have their policies reset

Due to changes in the policy structure for Conditional Access for Mobile App Management, any existing policies that were set by customers through the private preview will be removed. Customers will need to set new policies once the change is made. The timing will coincide with the October service update.
-->

### Zie ook
Zie [Wat is er nieuw in Microsoft Intune?](whats-new-in-microsoft-intune.md) voor meer informatie over recente ontwikkelingen.



<!--HONumber=Oct16_HO1-->


