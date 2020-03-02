---
title: App-configuratiebeleid voor Microsoft Intune
titleSuffix: ''
description: Informatie over het gebruik van app-configuratiebeleid op een iOS-/iPadOS- of Android-apparaat in Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/06/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 834B4557-80A9-48C0-A72C-C98F6AF79708
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 334cadfb7e668febad95a512eb34f62a73667ec6
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77513993"
---
# <a name="app-configuration-policies-for-microsoft-intune"></a>App-configuratiebeleid voor Microsoft Intune

Door App-configuratiebeleid kunnen problemen met app-instellingen worden voorkomen doordat u configuratie-instellingen kunt toewijzen aan beleid dat aan eindgebruikers wordt toegewezen voordat ze de app uitvoeren. De instellingen worden vervolgens automatisch verstrekt wanneer de app wordt geconfigureerd op het apparaat van eindgebruikers. Eindgebruikers hoeven zelf geen actie te ondernemen. De configuratie-instellingen zijn uniek voor elke app. 

U kunt app-configuratiebeleid maken en gebruiken om configuratie-instellingen te verstrekken voor zowel iOS-/iPadOS- als Android-apps. Met deze configuratie-instellingen kan een app worden aangepast met behulp van app-configuratie en -beheer. De configuratiebeleidsinstellingen worden gebruikt wanneer deze instellingen in de app worden gecontroleerd, doorgaans als de app voor het eerst wordt uitgevoerd. 

Het is bijvoorbeeld mogelijk dat u een van de volgende details moet opgeven voor een app-configuratie-instelling:

- Een aangepast poortnummer
- Taalinstellingen
- Beveiligingsinstellingen
- Huisstijlinstellingen, zoals een bedrijfslogo

Als deze instellingen in plaats daarvan door eindgebruikers zouden kunnen worden ingevoerd, zouden ze daarbij fouten kunnen maken. Met App-configuratiebeleid kan de consistentie in een onderneming toenemen en het aantal telefoontjes naar de helpdesk worden beperkt van eindgebruikers die proberen de instellingen zelf te configureren. Door gebruik te maken van app-configuratiebeleid kunnen apps eenvoudiger en sneller worden geaccepteerd.

De beschikbare configuratieparameters worden uiteindelijk bepaald door de ontwikkelaars van de app. De documentatie van de leverancier van de toepassing moet worden gecontroleerd om te zien of een app configuratie ondersteunt en welke configuraties beschikbaar zijn. Voor sommige toepassingen worden de beschikbare configuratie-instellingen door Intune bepaald. 

> [!NOTE]
> In de beheerde Google Play Store worden apps die configuratie ondersteunen als zodanig gemarkeerd:
> 
> ![Schermopname van een geconfigureerde app](./media/app-configuration-policies-overview/configured-app.png)
>
> U krijgt alleen apps van de [Beheerde Google Play Store](https://play.google.com/work) te zien, niet van de [Google Play Store](https://play.google.com/store/apps), wanneer u Beheerde apparaten gebruikt als het registratietype voor Android-apparaten. Apps van de Beheerde Google Play Store, ook bekend als Android for work (AfW) en Android Enterprise, zijn de apps in het werkprofiel die de app-versies bevatten die app-configuratie ondersteunen.

U kunt app-configuratiebeleid toewijzen aan een groep eindgebruikers en apparaten door een combinatie van [toewijzingen voor opnemen en uitsluiten](apps-inc-exl-assignments.md) te gebruiken. Zodra u een appconfiguratiebeleid hebt toegevoegd, kunt u de toewijzingen voor het appconfiguratiebeleid instellen. Wanner u de toewijzingen voor het beleid instelt, kunt u ervoor kiezen de [groepen](../fundamentals/groups-add.md) eindgebruikers op wie het beleid van toepassing is op te nemen of uit te sluiten. Als u ervoor kiest een of meer groepen op te nemen, kunt u specifieke groepen selecteren waarvoor u ingebouwde groepen wilt opnemen of selecteren. Ingebouwde groepen zijn **Alle gebruikers**, **Alle apparaten** en **Alle gebruikers + alle apparaten**.

U hebt twee opties voor het gebruik van app-configuratiebeleid met Intune:
- **Beheerde apparaten**: het apparaat wordt beheerd door Intune als MDM-provider (Mobile Device Management). De app moet zodanig zijn ontworpen dat deze ondersteuning biedt voor app-configuratie.
- **Beheerde apps**: een app die is ontwikkeld om de Intune App SDK te integreren. Dit is bekend als Mobile Application Management zonder registratie ([MAM-WE](app-management.md#mobile-application-management-mam-basics)). U kunt ook een app inpakken om de Intune App SDK te implementeren en te ondersteunen. Zie [Line-Of-Business-apps voor app-beveiligingsbeleid voorbereiden](../developer/apps-prepare-mobile-application-management.md) voor meer informatie over het inpakken van apps.

    > [!NOTE]
    > In door Intune beheerde apps wordt de status van App-configuratiebeleid van Intune gecontroleerd volgens een interval van 30 minuten wanneer deze zijn geïmplementeerd in combinatie met App-beveiliging van Intune. Als App-beveiliging van Intune niet aan de gebruiker is toegewezen, wordt de interval voor het controleren van App-configuratiebeleid van Intune ingesteld op 720 minuten.

## <a name="apps-that-support-app-configuration"></a>Apps die app-configuratie ondersteunen

### <a name="managed-devices"></a>Beheerde apparaten
U kunt app-configuratiebeleid gebruiken voor apps die hiervoor ondersteuning bieden. Apps bieden alleen ondersteuning voor app-configuratie van Intune als deze zodanig zijn geschreven dat ze app-configuraties ondersteunen, zoals is gedefinieerd door het besturingssysteem. Neem contact op met de leverancier van de app voor meer informatie over welke app-configuratiesleutels worden ondersteund.

### <a name="managed-apps"></a>Managed apps
U kunt uw Line-Of-Business-apps voorbereiden door de [Intune App SDK](../developer/app-sdk.md) in de app te integreren of door de app nadat deze is ontwikkeld in te pakken met behulp van de [Intune App Wrapping Tool](../developer/apps-prepare-mobile-application-management.md). In de Intune App SDK wordt ernaar gestreefd om het aantal door de app-ontwikkelaar vereiste codewijzigingen zo laag mogelijk te houden. Zie het [overzicht van de Intune App SDK](../developer/app-sdk.md) voor meer informatie. Zie [Line-Of-Business-apps voorbereiden voor app-beveiligingsbeleid](../developer/apps-prepare-mobile-application-management.md#feature-comparison) voor een vergelijking tussen de Intune App SDK en de Intune App Wrapping tool.

Als u **Beheerde apps** selecteert als het **Type apparaatregistratie**, verwijst dat gewoonlijk naar apps die zijn geconfigureerd via Intune-configuratiebeleid op een apparaat dat niet is geregistreerd bij Apparaatbeheer, terwijl **Beheerde apparaten** van toepassing zijn op apps die zijn geïmplementeerd via het MDM-kanaal en dus door Intune worden beheerd. Selecteer de gewenste keuze op basis van deze beschrijvingen. 

![Type apparaatregistratie](./media/app-configuration-policies-overview/device-enrollment-type.png)

> [!NOTE]
> Voor apps met meerdere identiteiten, zoals Microsoft Outlook, kunnen gebruikersvoorkeuren worden overwogen. Zo worden voor het Postvak IN met prioriteit de gebruikersinstellingen gerespecteerd en wordt de configuratie ervan niet gewijzigd. Met andere parameters kunt u bepalen of een gebruiker de instelling wel of niet kan wijzigen. Zie [Configuratie-instellingen voor de Outlook-app voor iOS/iPadOS en Android implementeren](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune) voor meer informatie.

## <a name="validate-the-applied-app-configuration-policy"></a>Het toegepaste app-configuratiebeleid valideren

U kunt op de volgende drie manieren het app-configuratiebeleid valideren:

   1. Zichtbaar op het apparaat. Vertoont de doel-app het gedrag dat is toegepast in App-configuratiebeleid?
   2. Via diagnostische logboeken (zie de sectie Diagnostische logboeken hieronder).
   3. In de Intune-Portal. In de sectie **Controleren** van een beleidsregel is de relevante status te zien:

      ![Eerste schermopname van de installatiestatus van het apparaat](./media/app-configuration-policies-overview/device-install-status-1.png)

      ![Tweede schermopname van de installatiestatus van het apparaat](./media/app-configuration-policies-overview/device-install-status-2.png)

      Onder **Intune** -> **Apparaten** -> **Alle apparaten** worden verder met de optie **App-configuratie**  aan de linkerkant van het scherm alle toegewezen beleidsregels en de status ervan weergegeven:

      ![Schermopname van de app-configuratie](./media/app-configuration-policies-overview/app-configuration.png)

## <a name="diagnostic-logs"></a>Diagnostische logboeken

### <a name="iosipados-configuration-on-unmanaged-devices"></a>iOS/iPadOS-configuratie op niet-beheerde apparaten

U kunt de iOS-/iPadOS-configuratie valideren met het **diagnostische logboek van Intune** op niet-beheerde apparaten voor de configuratie van beheerde apps. Behalve met de onderstaande stappen, kunt u ook toegang krijgen tot de logboeken van beheerde apps met behulp van Microsoft Edge. Zie [Met Microsoft Edge in iOS/iPadOS logboeken voor beheerde apps openen](~/apps/manage-microsoft-edge.md#use-microsoft-edge-on-ios-to-access-managed-app-logs) voor meer informatie.

1. Download en installeer **Microsoft Edge** vanuit de App Store als het nog niet is geïnstalleerd op het apparaat. Zie [Met Microsoft Intune beveiligde apps](apps-supported-intune-apps.md) voor meer informatie.
2. Start **Microsoft Edge** en selecteer **Info** > **Help bij Intune** in de navigatiebalk.
3. Klik op **Aan de slag**.
4. Klik op **Logboeken delen**.
5. Gebruik de e-mail-app van uw keuze om de logboeken naar uzelf te verzenden zodat deze op uw pc kunnen worden weergegeven. 
6. Open **IntuneMAMDiagnostics.txt** in uw tekstbestandsviewer.
7. Zoek naar `ApplicationConfiguration`. De resultaten zien er ongeveer als volgt uit:

    ``` JSON
        {
            (
                {
                    Name = "com.microsoft.intune.mam.managedbrowser.BlockListURLs";
                    Value = "https://www.aol.com";
                },
                {
                    Name = "com.microsoft.intune.mam.managedbrowser.bookmarks";
                    Value = "Outlook Web|https://outlook.office.com||Bing|https://www.bing.com";
                }
            );
        },
        {
            ApplicationConfiguration =             
            (
                {
                Name = IntuneMAMUPN;
                Value = "CMARScrubbedM:13c45c42712a47a1739577e5c92b5bc86c3b44fd9a27aeec3f32857f69ddef79cbb988a92f8241af6df8b3ced7d5ce06e2d23c33639ddc2ca8ad8d9947385f8a";
                },
                {
                Name = "com.microsoft.outlook.Mail.NotificationsEnabled";
                Value = false;
                }
            );
        }
    ```

De configuratiedetails van uw toepassing moeten voldoen aan het toepassingsconfiguratiebeleid dat voor uw tenant is geconfigureerd. 

![Configuratie van doel-app](./media/app-configuration-policies-overview/targeted-app-configuration-3.png)

### <a name="iosipados-configuration-on-managed-devices"></a>iOS/iPadOS-configuratie op beheerde apparaten

U kunt de iOS-/iPadOS-configuratie valideren met het **diagnostische logboek van Intune** op beheerde apparaten voor de configuratie van beheerde apps.

1. Download en installeer **Microsoft Edge** vanuit de App Store als het nog niet is geïnstalleerd op het apparaat. Zie [Met Microsoft Intune beveiligde apps](apps-supported-intune-apps.md) voor meer informatie.
2. Start **Microsoft Edge** en selecteer **Info** > **Help bij Intune** in de navigatiebalk.
3. Klik op **Aan de slag**.
4. Klik op **Logboeken delen**.
5. Gebruik de e-mail-app van uw keuze om de logboeken naar uzelf te verzenden zodat deze op uw pc kunnen worden weergegeven. 
6. Open **IntuneMAMDiagnostics.txt** in uw tekstbestandsviewer.
7. Zoek naar `AppConfig`. Uw resultaten moeten voldoen aan het toepassingsconfiguratiebeleid dat voor uw tenant is geconfigureerd.

### <a name="android-configuration-on-managed-devices"></a>Android-configuratie op beheerde apparaten

U kunt de iOS-/iPadOS-configuratie valideren met het **diagnostische logboek van Intune** op beheerde apparaten voor de configuratie van beheerde apps.

Als u logboeken van een Android-apparaat wilt verzamelen, moet u of de eindgebruiker de logboeken van het apparaat downloaden via een USB-verbinding (of het equivalent van **File Explorer** op het apparaat). Dit zijn de stappen:

1. Sluit het Android-apparaat met de USB-kabel aan op de computer.
2. Zoek op de computer naar een map met de naam van uw apparaat. Zoek in die map naar `Android Device\Phone\Android\data\com.microsoft.windowsintune.companyportal`.
3. Open de map Files in de map `com.microsoft.windowsintune.companyportal` en open `OMADMLog_0`.
3. Zoek naar `AppConfigHelper` om berichten te vinden die gerelateerd zijn aan de app-configuratie. De resultaten moeten er ongeveer uitzien als het volgende gegevensblok:

    `2019-06-17T20:09:29.1970000       INFO   AppConfigHelper     10888  02256  Returning app config JSON [{"ApplicationConfiguration":[{"Name":"com.microsoft.intune.mam.managedbrowser.BlockListURLs","Value":"https:\/\/www.aol.com"},{"Name":"com.microsoft.intune.mam.managedbrowser.bookmarks","Value":"Outlook Web|https:\/\/outlook.office.com||Bing|https:\/\/www.bing.com"},{"Name":"com.microsoft.intune.mam.managedbrowser.homepage","Value":"https:\/\/www.arstechnica.com"}]},{"ApplicationConfiguration":[{"Name":"IntuneMAMUPN","Value":"AdeleV@M365x935807.OnMicrosoft.com"},{"Name":"com.microsoft.outlook.Mail.NotificationsEnabled","Value":"false"},{"Name":"com.microsoft.outlook.Mail.NotificationsEnabled.UserChangeAllowed","Value":"false"}]}] for user User-875363642`
    
## <a name="graph-api-support-for-app-configuration"></a>Graph API-ondersteuning voor app-configuratie

U kunt Graph API gebruiken om app-configuratietaken uit te voeren. Zie het Engelstalige [Graph API Reference MAM Targeted Config](https://docs.microsoft.com/graph/api/resources/intune-shared-targetedmanagedappconfiguration?view=graph-rest-beta) voor meer informatie. Zie [Working with Intune in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-beta) (Werken met intune in Microsoft Graph) voor meer informatie over Intune en Graph.

## <a name="troubleshooting"></a>Probleemoplossing

### <a name="using-logs-to-show-a-configuration-parameter"></a>Logboeken gebruiken om een configuratieparameter weer te geven
Wanneer in de logboeken een configuratieparameter wordt weergegeven die van toepassing is maar niet lijkt te werken, is er mogelijk een probleem met de configuratie-implementatie van de app-ontwikkelaar. Als u eerst contact opneemt met de app-ontwikkelaar of de kennisdatabase van de app-ontwikkelaar raadpleegt, kunt u zich mogelijk een ondersteuningsgesprek met Microsoft besparen. Als het een probleem betreft met de manier waarop de configuratie wordt verwerkt in een app, moet dit probleem worden opgelost in een toekomstige bijgewerkte versie van die app.

## <a name="next-steps"></a>Volgende stappen

### <a name="managed-devices"></a>Beheerde apparaten

- Informatie over het gebruik van app-configuratie met uw iOS-/iPadOS-apparaten.  Zie [App-configuratiebeleidsregels voor beheerde iOS-/iPadOS-apparaten toevoegen](app-configuration-policies-use-ios.md).
- Informatie over het gebruik van app-configuratie met uw Android-apparaten.  Zie [ App-configuratiebeleidsregels voor beheerde Android-apparaten](app-configuration-policies-use-android.md).

### <a name="managed-apps"></a>Managed apps

- Informatie over het gebruik van app-configuratie met beheerde apps. Zie [App-configuratiebeleidsregels toevoegen voor beheerde apps zonder apparaatinschrijving](app-configuration-policies-managed-app.md).
