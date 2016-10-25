---
title: Wat is er nieuw? | Microsoft Intune
description: Ontdek wat er nieuw is in de release van Microsoft Intune van deze maand en in oudere releases
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 503719953031bf5079b2bf5bc84a0497d708f79a
ms.openlocfilehash: 730809e0841a248b90f5fe157f2c6338bfd32b2d


---
# Wat is nieuw in Microsoft Intune -- oktober 2016
Ontdek wat er nieuw is in deze release van Microsoft Intune. U vindt hier ook informatie over toekomstige wijzigingen waar u rekening mee moet houden én informatie over oudere releases.

Al deze functies worden uiteindelijk ondersteund voor implementaties voor hybride klanten (Configuration Manager met Intune). Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](https://technet.microsoft.com/library/mt718155.aspx).
<!---@Barry, the above blurb stays in each version, but make sure Tyler signs off each time. Also, remember to set the ms.date in the metadata to the sprint release. --->

## Wat is er nieuw?

### Voorwaardelijke toegang voor beheer van mobiele toepassingen
U kunt de toegang tot Exchange Online beperken, zodat toegang alleen mogelijk is vanuit apps waarin beheerbeleid voor mobiele toepassingen met Intune wordt ondersteund, zoals Outlook. [Deze nieuwe functie](/intune/deploy-use/allow-policy-managed-apps-access-to-o365) past perfect bij het Intune MAM-beleid (Mobile App Management), aangezien u de toegang tot ingebouwde e-mailclients of andere apps die niet zijn geconfigureerd met het Intune MAM-beleid, kunt blokkeren. Hiermee zorgt u ervoor dat uw gebruikers de gegevens van uw organisatie gebruiken met apps die kunnen worden beveiligd met Intune MAM. U kunt aan de slag gaan met Intune Mobile App Management via Azure Portal. De nieuwe sectie Voorwaardelijke toegang kunt u in de blade Instellingen vinden.

### Voorwaardelijke toegang voor Windows-pc's
U kunt nu voorwaardelijk toegangsbeleid creëren via de beheerdersconsole van Intune. Zo kunt u voorkomen dat Windows-pc's toegang hebben tot [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) en [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune). Ook kunt u voorwaardelijke toegang creëren om de toegang te blokkeren tot Office- desktop en universele toepassingen.

### Ondersteuning van Android for Work
Intune is nu onderdeel van het Android for Work-programma. De ondersteuning van Intune voor de functies van het Android for Work-programma wordt met ingang van deze maand geïmplementeerd.
[Lees de aankondiging van Microsoft over ondersteuning van Intune voor Android for Work](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

De volgende onderwerpen voor Intune zijn nieuw, of bijgewerkt met informatie over Android for Work:

Voor IT-professionals:
- [Android for Work instellen](/intune/deploy-use/set-up-android-for-work)
<!--- [Nathan Bigman's resource access topics]()-->
- [De toegang tot e-mail beperken bij Exchange Online en de nieuwe Exchange Online Dedicated met Microsoft Intune](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
- [Toegang tot e-mail beperken op Exchange On-premises en oudere Exchange Online Dedicated met Microsoft Intune](/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
- [Instellingen voor nalevingsbeleid voor Android for Work](/intune/deploy-use/afw-compliance-policy-settings-in-microsoft-intune)
- [Android for Work-apps implementeren](/intune/deploy-use/android-for-work-apps)
- [Android for Work-apps configureren met configuratiebeleid voor mobiele apps](/intune/deploy-use/afw-app-configuration-policy)
- [Android for Work-beleidsinstellingen](/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)

Voor eindgebruikers:
- [Wat gebeurt er wanneer u een werkprofiel maakt](/intune/enduser/what-happens-when-you-create-a-work-profile-android)
- [Een werkprofiel maken en uw apparaat registreren bij Intune](/intune/enduser/create-a-work-profile-and-enroll-your-device-in-intune-android)

### Lookout-integratie om iOS-apparaten te beveiligen
In oktober integreert Microsoft met de oplossing voor beveiliging tegen mobiele bedreigingen van Lookout, om mobiele iOS-apparaten te beveiligen door detectie van bijvoorbeeld malware en riskante apps op apparaten. De oplossing van Lookout helpt u het (configureerbare) risiconiveau te bepalen. U kunt een beleidsregel in Intune maken om de apparaatnaleving te bepalen op basis van de risicoanalyse door Lookout. Met behulp van beleid voor voorwaardelijke toegang kunt u toegang tot bedrijfsbronnen toestaan of blokkeren op basis van de apparaatnalevingsstatus.

Eindgebruikers van iOS-apparaten die niet voldoen aan het beleid, moeten hun apparaten inschrijven en de Lookout for Work-toepassing op hun apparaten installeren, de app activeren en bedreigingen verhelpen die zijn gerapporteerd in de Lookout for Work-toepassing om toegang te krijgen tot bedrijfsgegevens. Lees hoe u [Lookout for Work-apps kunt configureren en implementeren](/intune/deploy-use/configure-and-deploy-lookout-for-work-apps).
<!--TFS 1319493-->

<!--### New Microsoft Intune Company Portal available for Windows 10 devices
Microsoft is releasing a new [Microsoft Intune Company Portal for Windows 10 devices](https://go.microsoft.com/fwlink/?linkid=830663). This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike, while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on (SSO) and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store.-->

### Intune App Wrapping Tool voor Android
U kunt uw apps gebruik laten maken van Mobile Application Management-beleid (MAM) van Intune door de Intune App Wrapping Tool te gebruiken. Ondersteuning voor MAM-beleid van Intune zonder apparaatregistratie is nu beschikbaar.

### Afdrukbeheer voor apps die worden beheerd met MAM-beleid
U kunt nu voorkomen dat bedrijfsgegevens worden afgedrukt met apps waarop een MAM-beleid van toepassing is. Deze instelling is beschikbaar op de [Azure-portal](/Intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) en werkt met zowel [iOS](/Intune/deploy-use/ios-mam-policy-settings)- als [Android](/Intune/deploy-use/android-mam-policy-settings)-apparaten.
<!--TFS 1014328-->

## Mededelingen

### Compatibiliteit van Android Samsung KNOX met Intune
Bepaalde modellen van de Samsung Galaxy Ace-telefoon kunnen niet als Samsung KNOX-apparaat worden beheerd door Intune. Wanneer u deze apparaten registreert bij Intune, worden ze beheerd als standaard Android-apparaten.

De betrokken modelnummers zijn:

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

U en uw eindgebruikers hoeven niets te doen. Ga voor meer informatie naar de [Samsung KNOX](https://www.samsungknox.com)-website.

### De bedrijfsportalapp voor Windows 8 wordt afgeschaft; ondersteuning voor Windows Phone 8 en Windows RT-platformen wordt afgeschaft
Vanaf oktober 2016 biedt Microsoft Intune geen ondersteuning meer voor de Windows 8-bedrijfsportal. Microsoft Intune biedt dan ook geen ondersteuning meer voor het Windows Phone 8- en Windows RT-platform. Als gevolg hiervan kunt u geen Windows Phone 8- of Windows RT-apparaten meer registreren of bijwerken.

U kunt Windows Phone 8-, Windows RT- en Windows 8-apparaten die al zijn geregistreerd blijven beheren. Werk Windows 8- en Windows Phone 8-apparaten bij naar Windows 8.1 en Windows Phone 8.1. Gebruik de bijbehorende bedrijfsportalapps voor Windows 8.1 en Windows Phone 8.1 om zonder onderbrekingen door te gaan met het distribueren van apps naar deze apparaten.

Vanaf november 2016 bieden we geen ondersteuning meer voor de Windows Phone 8-bedrijfsportal.
<!--TFS 1255391-->

## Binnenkort

### Nieuwe Microsoft Intune-bedrijfsportal voor Windows 10-apparaten
Microsoft brengt een nieuwe Microsoft Intune-bedrijfsportal voor Windows 10-apparaten uit. Deze app maakt gebruik van de Windows 10 Universal-indeling en biedt gebruikers een bijgewerkte gebruikerservaring in de app zelf, en een identieke gebruikerservaring op alle Windows 10-apparaten (pc en mobiel), met behoud van de functionaliteit die ze momenteel gebruiken.

Met de nieuwe app kunnen gebruikers van Windows 10-apparaten ook gebruikmaken van aanvullende functies van het platform, zoals eenmalige aanmelding (SSO) en verificatie op basis van certificaten. De app wordt beschikbaar gesteld als een upgrade van de bestaande Windows 8.1-bedrijfsportal en Windows Phone 8.1-bedrijfsportal in de Windows Store. Zie [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp) voor meer informatie.
<!--TFS 1016502-->

### Zie tevens
* [Microsoft Intune-blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Cloud Platform roadmap](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Vorige versies van Intune](previous-intune-releases.md)



<!--HONumber=Oct16_HO3-->


