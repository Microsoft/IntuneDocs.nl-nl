---
title: Wat is er nieuw? | Microsoft Intune
description: Ontdek wat er nieuw is in de release van Microsoft Intune van deze maand en in oudere releases
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/2/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b5035c4560fa298af83fe0d016cd83b85959b450
ms.openlocfilehash: 12c066ed165509cc9182a3735d516fa2dd3e6a90


---
# <a name="whats-new-in-microsoft-intune-october-2016"></a>Wat is er nieuw in Microsoft Intune - oktober 2016
Ontdek wat er nieuw is in deze release van Microsoft Intune. U vindt hier ook informatie over toekomstige wijzigingen waar u rekening mee moet houden én informatie over oudere releases.

Al deze functies worden uiteindelijk ondersteund voor implementaties voor hybride klanten (Configuration Manager met Intune). Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](https://technet.microsoft.com/library/mt718155.aspx).
<!---@Barry, the above blurb stays in each version, but make sure Tyler signs off each time. Also, remember to set the ms.date in the metadata to the sprint release. --->

## <a name="whats-new"></a>Wat is er nieuw?

### <a name="conditional-access-for-mobile-application-management"></a>Voorwaardelijke toegang voor beheer van mobiele toepassingen
U kunt de toegang tot Exchange Online beperken, zodat toegang alleen mogelijk is vanuit apps waarin beheerbeleid voor mobiele toepassingen met Intune wordt ondersteund, zoals Outlook. [Deze nieuwe functie](/intune/deploy-use/allow-policy-managed-apps-access-to-o365) past perfect bij het Intune MAM-beleid (Mobile App Management), aangezien u de toegang tot ingebouwde e-mailclients of andere apps die niet zijn geconfigureerd met het Intune MAM-beleid, kunt blokkeren. Hiermee zorgt u ervoor dat uw gebruikers de gegevens van uw organisatie gebruiken met apps die kunnen worden beveiligd met Intune MAM. U kunt aan de slag gaan met Intune Mobile App Management via Azure Portal. De nieuwe sectie Voorwaardelijke toegang kunt u in de blade Instellingen vinden.

### <a name="conditional-access-for-windows-pcs"></a>Voorwaardelijke toegang voor Windows-pc's
U kunt nu voorwaardelijk toegangsbeleid creëren via de beheerdersconsole van Intune. Zo kunt u voorkomen dat Windows-pc's toegang hebben tot [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) en [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune). Ook kunt u voorwaardelijke toegang creëren om de toegang te blokkeren tot Office- desktop en universele toepassingen.

### <a name="android-for-work-support"></a>Ondersteuning van Android for Work
Intune is nu onderdeel van het AfW-programma (Android for Work). Vanaf deze maand beginnen we met het implementeren van ondersteuning voor AfW-functies. Dit zal enkele maanden duren. Houd er rekening mee dat bij de beschikbare app-implementatie van AfW gebruik wordt gemaakt van de nieuwe groeperings- en targetingervaring. Nieuw ingerichte Intune-serviceaccounts kunnen deze functie gebruiken zodra AfW voor de accounts beschikbaar is.

Bestaande Intune-klanten kunnen deze functie in productie gebruiken nadat hun tenant is gemigreerd. Bestaande klanten kunnen een Intune-proefaccount maken om voor deze functie te plannen en de functie te testen tot hun tenant is gemigreerd. Neem voor vragen over groeperen en targetingtijdlijnen contact op met ons [migratieteam](mailto:intunegrps@microsoft.com).

[Lees de aankondiging van Microsoft over ondersteuning van Intune voor Android for Work](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

De volgende onderwerpen voor Intune zijn nieuw, of bijgewerkt met informatie over Android for Work:

Voor IT-professionals:
- [Android for Work installeren](/intune/deploy-use/set-up-android-for-work)
<!--- [Nathan Bigman's resource access topics]()-->
- [E-mailtoegang beperken tot Exchange Online en het nieuwe Exchange Online-specifiek met Intune](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
- [E-mailtoegang beperken tot Exchange On-Premises en het oude Exchange Online-specifiek met Intune](/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
- [Instellingen voor Android for Work-nalevingsbeleid](/intune/deploy-use/afw-compliance-policy-settings-in-microsoft-intune)
- [Android for Work-apps implementeren](/intune/deploy-use/android-for-work-apps)
- [Android for Work-apps configureren met beleid voor de configuratie van mobiele apps](/intune/deploy-use/afw-app-configuration-policy)
- [Android for Work-beleidsinstellingen](/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)

Voor eindgebruikers:
- [Wat gebeurt er wanneer u een werkprofiel maakt](/intune/enduser/what-happens-when-you-create-a-work-profile-android)
- [Een werkprofiel maken en uw apparaat registreren bij Intune](/intune/enduser/create-a-work-profile-and-enroll-your-device-in-intune-android)

### <a name="lookout-integration-to-protect-ios-devices"></a>Lookout-integratie om iOS-apparaten te beveiligen
In oktober integreert Microsoft met de oplossing voor beveiliging tegen mobiele bedreigingen van Lookout, om mobiele iOS-apparaten te beveiligen door detectie van bijvoorbeeld malware en riskante apps op apparaten. De oplossing van Lookout helpt u het (configureerbare) risiconiveau te bepalen. U kunt een beleidsregel in Intune maken om de apparaatnaleving te bepalen op basis van de risicoanalyse door Lookout. Met behulp van beleid voor voorwaardelijke toegang kunt u toegang tot bedrijfsbronnen toestaan of blokkeren op basis van de apparaatnalevingsstatus.

Eindgebruikers van iOS-apparaten die niet voldoen aan het beleid, moeten hun apparaten inschrijven en de Lookout for Work-toepassing op hun apparaten installeren, de app activeren en bedreigingen verhelpen die zijn gerapporteerd in de Lookout for Work-toepassing om toegang te krijgen tot bedrijfsgegevens. Lees hoe u [Lookout for Work-apps kunt configureren en implementeren](/intune/deploy-use/configure-and-deploy-lookout-for-work-apps).
<!--TFS 1319493-->

<!--### New Microsoft Intune Company Portal available for Windows 10 devices
Microsoft is releasing a new [Microsoft Intune Company Portal for Windows 10 devices](https://go.microsoft.com/fwlink/?linkid=830663). This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike, while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on (SSO) and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store.-->

### <a name="intune-app-wrapping-tool-for-android"></a>Intune App Wrapping Tool voor Android
U kunt uw apps gebruik laten maken van Mobile Application Management-beleid (MAM) van Intune door de Intune App Wrapping Tool te gebruiken. Ondersteuning voor MAM-beleid van Intune zonder apparaatregistratie is nu beschikbaar.

### <a name="manage-printing-from-apps-managed-using-mam-policies"></a>Afdrukbeheer voor apps die worden beheerd met MAM-beleid
U kunt nu voorkomen dat bedrijfsgegevens worden afgedrukt met apps waarop een MAM-beleid van toepassing is. Deze instelling is beschikbaar op de [Azure-portal](/Intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) en werkt met zowel [iOS](/Intune/deploy-use/ios-mam-policy-settings)- als [Android](/Intune/deploy-use/android-mam-policy-settings)-apparaten.
<!--TFS 1014328-->

### <a name="support-for-fingerprints-on-android-devices"></a>Ondersteuning voor vingerafdrukken op Android-apparaten
Gebruikers kunnen met het MAM-beleid (Mobile App Management) voor Android nu met hun vingerafdruk toegang tot een app krijgen in plaats van een pincode te typen. Raadpleeg dit en andere [beleidsinstellingen voor het beheer van mobiele apps voor Android hier](/Intune/deploy-use/android-mam-policy-settings).

## <a name="notices"></a>Mededelingen

### <a name="android-samsung-knox-compatibility-with-intune"></a>Compatibiliteit van Android Samsung KNOX met Intune
Bepaalde modellen van de Samsung Galaxy Ace-telefoon kunnen niet als Samsung KNOX-apparaat worden beheerd door Intune. Wanneer u deze apparaten registreert bij Intune, worden ze beheerd als standaard Android-apparaten.

De betrokken modelnummers zijn:

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

U en uw eindgebruikers hoeven niets te doen. Ga voor meer informatie naar de [Samsung KNOX](https://www.samsungknox.com)-website.

### <a name="company-portal-app-for-windows-8-is-deprecated-support-for-windows-phone-8-and-windows-rt-platforms-are-being-deprecated"></a>De bedrijfsportalapp voor Windows 8 wordt afgeschaft; ondersteuning voor Windows Phone 8 en Windows RT-platformen wordt afgeschaft
Vanaf oktober 2016 biedt Microsoft Intune geen ondersteuning meer voor de Windows 8-bedrijfsportal. Microsoft Intune biedt dan ook geen ondersteuning meer voor het Windows Phone 8- en Windows RT-platform. Als gevolg hiervan kunt u geen Windows Phone 8- of Windows RT-apparaten meer registreren of bijwerken.

U kunt Windows Phone 8-, Windows RT- en Windows 8-apparaten die al zijn geregistreerd blijven beheren. Werk Windows 8- en Windows Phone 8-apparaten bij naar Windows 8.1 en Windows Phone 8.1. Gebruik de bijbehorende bedrijfsportalapps voor Windows 8.1 en Windows Phone 8.1 om zonder onderbrekingen door te gaan met het distribueren van apps naar deze apparaten.

Vanaf november 2016 bieden we geen ondersteuning meer voor de Windows Phone 8-bedrijfsportal.
<!--TFS 1255391-->

## <a name="whats-coming"></a>Binnenkort

### <a name="new-microsoft-intune-company-portal-available-for-windows-10-devices"></a>Nieuwe Microsoft Intune-bedrijfsportal voor Windows 10-apparaten
Microsoft brengt een nieuwe Microsoft Intune-bedrijfsportal voor Windows 10-apparaten uit. Deze app maakt gebruik van de Windows 10 Universal-indeling en biedt gebruikers een bijgewerkte gebruikerservaring in de app zelf, en een identieke gebruikerservaring op alle Windows 10-apparaten (pc en mobiel), met behoud van de functionaliteit die ze momenteel gebruiken.

Met de nieuwe app kunnen gebruikers van Windows 10-apparaten ook gebruikmaken van aanvullende functies van het platform, zoals eenmalige aanmelding (SSO) en verificatie op basis van certificaten. De app wordt beschikbaar gesteld als een upgrade van de bestaande Windows 8.1-bedrijfsportal en Windows Phone 8.1-bedrijfsportal in de Windows Store. Zie [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp) voor meer informatie.
<!--TFS 1016502-->

### <a name="see-also"></a>Zie tevens
* [Microsoft Intune-blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Roadmap voor cloudplatform](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Vorige versies van Intune](previous-intune-releases.md)



<!--HONumber=Nov16_HO1-->


