---
title: Wat is er nieuw? | Microsoft Intune
description: Ontdek wat er nieuw is in de release van Microsoft Intune van deze maand en in oudere releases
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8e88c14ad77d8fe1b4c0fe2e7676d126e6288146
ms.openlocfilehash: bcd77b751c2059131558e1cbfeebd4d3f71086e5


---
# <a name="whats-new-in-microsoft-intune---november-2016"></a>Wat is er nieuw in Microsoft Intune - november 2016
Ontdek wat er nieuw is in deze release van Microsoft Intune. U vindt hier ook informatie over toekomstige wijzigingen waar u rekening mee moet houden én informatie over oudere releases.

Al deze functies worden uiteindelijk ondersteund voor implementaties voor hybride klanten (Configuration Manager met Intune). Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](https://technet.microsoft.com/library/mt718155.aspx).
<!---@Barry, the above blurb stays in each version, but make sure Tyler signs off each time. Also, remember to set the ms.date in the metadata to the sprint release. --->

## <a name="new-capabilities"></a>Nieuwe mogelijkheden

<!--### View App States for All Platforms in Real Time
App installation status is now shown in real-time in the console. When you previously deployed an app, you had to wait for a targeted device to report back before the app install status was displayed in the Intune console.

### Streamline iOS App Management for your End Users
Intune can now automatically take over management of the previously installed app and no end user action is required.

Previously, if the end user of an enrolled iOS device installed an app from the App Store before you deployed that same app with a deployment action of __Available__, then the end user had to:

1. Open the __Company Portal__.
2. Select the app.
3. Tap __Install__ to enable Intune to take over management of the app.-->

<!--### New Microsoft Intune Company Portal App for Windows 10 Devices
Microsoft is releasing a new Intune Company Portal for Windows 10 devices. This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike - while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store. It will also be available for sideloading.-->

<!--### Support for Windows Store for Business Apps Being Deployed as Available
You can now deploy apps you synchronized from the Windows Store for Business (WSfB) with a deployment action of __Available__ or __Required__. After syncing WSfB apps into Intune, administrators will be able to target those apps as available installs to groups of users. End users will see the deployed WSfB apps as available for install in the Universal Company Portal, where they can choose whether they would like to acquire the apps.

### Conditional Access for MAM with SharePoint Online

You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint online.  You can get started in Intune mobile app management via the Azure portal. Look for the  Conditional Access section in the “Settings” blade which now includes the option for SharePoint online.-->

> [!IMPORTANT]

> __Een update voor Intune en Android for Work__

> Hoewel u Android for Work-apps kunt implementeren met de actie __Vereist__, kunt u apps alleen implementeren als __Beschikbaar__ als uw Intune-groepen zijn gemigreerd naar de nieuwe functie voor groepen van Azure AD.

### <a name="intune-app-sdk-for-cordova-plugin-now-supports-mam-without-enrollment"></a>De Intune App SDK Cordova-invoegtoepassing ondersteunt nu MAM zonder inschrijving
App-ontwikkelaars kunnen de App SDK Cordova-invoegtoepassing nu gebruiken om MAM-functionaliteit zonder apparaatinschrijving in te schakelen in hun op Cordova gebaseerde apps voor Android en iOS. U vindt de Intune App SDK Cordova-invoegtoepassing [hier](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam).

### <a name="intune-app-sdk-xamarin-component-now-supports-mam-without-enrollment"></a>Het Intune App SDK Xamarin-onderdeel ondersteunt nu MAM zonder inschrijving
App-ontwikkelaars kunnen het Xamarin-onderdeel van de Intune App SDK gebruiken om MAM-functionaliteit zonder apparaatinschrijving in te schakelen in hun op Xamarin gebaseerde apps voor Android en iOS. U vindt het Xamarin-onderdeel van de Intune App SDK [hier](https://github.com/msintuneappsdk/intune-app-sdk-xamarin).

## <a name="notices"></a>Mededelingen

### <a name="symantec-signing-certificate-no-longer-requires-signed-windows-phone-8-company-portal-for-upload"></a>Ondertekende Windows Phone 8-bedrijfsportal is niet meer vereist voor uploaden van Symantec-handtekeningcertificaat
Voor het uploaden van het Symantec-handtekeningcertificaat is geen ondertekende bedrijfsportal-app voor Windows Phone 8 meer vereist. Het certificaat kan afzonderlijk worden geüpload.

## <a name="deprecations"></a>Afschaffingen

### <a name="support-for-the-windows-phone-8-company-portal"></a>Ondersteuning van de bedrijfsportal voor Windows Phone 8
Ondersteuning voor de Windows Phone 8-bedrijfsportal wordt nu afgeschaft. Ondersteuning voor het Windows Phone 8- en Windows RT-platform is afgeschaft in oktober 2016. Ondersteuning voor de Windows 8-bedrijfsportal is ook in oktober 2016 afgeschaft.


### <a name="see-also"></a>Zie tevens
* [Microsoft Intune-blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Roadmap voor cloudplatform](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Vorige versies van Intune](whats-new-archive.md)



<!--HONumber=Nov16_HO3-->


