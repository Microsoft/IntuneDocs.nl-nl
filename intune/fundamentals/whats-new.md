---
title: Nieuwe functies in Microsoft Intune - Azure | Microsoft Docs
titleSuffix: ''
description: Ontdekken wat er nieuw is in Intune Azure Portal
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/03/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2f46b8c7f0f57ab7831d6487495946aa9326b2d5
ms.sourcegitcommit: 24487f078349795922dc497c952e8358cf767a1a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/04/2020
ms.locfileid: "76977781"
---
# <a name="whats-new-in-microsoft-intune"></a>Wat is er nieuw in Microsoft Intune?

Ontdek elke week wat er nieuw is in Microsoft Intune. U vindt hier ook [belangrijke kennisgevingen](#notices), [oudere releases](whats-new-archive.md) en informatie over [hoe service-updates voor Intune worden uitgebracht](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728). 

> [!Note]
> Het kan voor elke [maandelijkse update](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728) tot drie dagen duren totdat deze wordt geïmplementeerd. Dit gebeurt in de volgende volgorde:
>
> - Dag 1: Azië en Stille Oceaan (APAC)
> - Dag 2: Europa, Midden-Oosten en Afrika (EMEA)
> - Dag 3: Noord-Amerika
> - Dag 4+: Intune for Government
>
> Sommige functies worden gedurende een aantal weken geïmplementeerd en zijn mogelijk niet voor alle gebruikers in de eerste week beschikbaar.
>
> Controleer de [pagina In ontwikkeling](in-development.md) voor een lijst met nieuwe functies in een versie.

**RSS-feed**: ontvang een melding wanneer deze pagina wordt bijgewerkt door de volgende URL in uw feedlezer te kopiëren en plakken: `https://docs.microsoft.com/api/search/rss?search=%22What%27s+new+in+microsoft+intune%3F+-+Azure%22&locale=en-us`

<!-- Common categories:  
### App management
### Device configuration
### Device enrollment
### Device management
### Device security
### Intune apps
### Monitor and troubleshoot
### Role-based access control
-->  

<!-- ########################## -->
## <a name="week-of-february-03-2020"></a>Week van 03 februari 2020

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Appbeheer

#### <a name="company-portal-app-improved-performance---6178652---"></a>Verbeterde prestaties van de Bedrijfsportal-app<!-- 6178652 -->
De Bedrijfsportal-app is bijgewerkt om de verbeterde prestaties te ondersteunen voor apparaten die gebruikmaken van ARM64-processors, zoals de Surface Pro X. Voorheen werkte de Bedrijfsportal in een geëmuleerde ARM32-modus. Nu is de Bedrijfsportal-app systeemeigen gecompileerd voor ARM64. Raadpleeg [De Microsoft Intune-bedrijfsportal-app configureren](~/apps/company-portal-app.md) voor meer informatie over de Bedrijfsportal-app.

<!-- ########################## -->
## <a name="week-of-january-27-2020"></a>De week van 27 januari 2020

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Appbeheer

#### <a name="new-setting-to-remove-specific-windows-built-in-apps---6184390---"></a>Nieuwe instelling voor het verwijderen van specifieke ingebouwde Windows-apps<!-- 6184390 -->
Met een nieuwe beleidsinstelling voor de configuratie van Windows 10-apparaten kunt u de volgende ingebouwde Windows-apps verwijderen:

- Mixed Reality-viewer
- MSN weer
- App-installatieprogramma
- Microsoft Tips
- Mijn Office
- Microsoft Solitaire Collection 
- Mobiele abonnementen
- Feedback-hub 
- Xbox 
- Groove Music
- Mail
- Kalender

Selecteer in het Microsoft Endpoint Manager-beheercentrum de opties **Apparaten** > **Configuratieprofielen** > **Profiel maken**. Selecteer vervolgens **Windows 10 en hoger** als het **Platform**. Selecteer **Apparaatbeperkingen** als het **Profieltype**. Selecteer **App Store** in het deelvenster **Apparaatbeperkingen**. Selecteer onder aan het deelvenster naast **Ingebouwde apps** de optie **Verwijderen**. Raadpleeg [Ingebouwde apps toevoegen aan Microsoft Intune](~/apps/apps-add-built-in.md) voor meer informatie over het toevoegen van ingebouwde apps.

#### <a name="intune-support-for-additional-microsoft-edge-version-77-deployment-channel-for-macos---5983950----"></a>Intune-ondersteuning voor het extra implementatiekanaal van Microsoft Edge-versie 77 voor macOS<!-- 5983950  -->
Microsoft Intune biedt nu ondersteuning voor het extra **stabiele** implementatiekanaal voor de Microsoft Edge-app voor macOS. Het **stabiele** kanaal is het aanbevolen kanaal voor een brede implementatie van Microsoft Edge in Enterprise-omgevingen. Het wordt elke zes weken bijgewerkt en elke release bevat verbeteringen uit het **Beta**-kanaal. Naast het **stabiele** kanaal en het **Beta**-kanaal, biedt Intune ook ondersteuning voor een **Dev**-kanaal. De openbare preview-versie biedt een stabiel kanaal en een Dev-kanaal voor Microsoft Edge-versie 77 en hoger voor macOS. Automatische updates van de browser is standaard ingeschakeld. Raadpleeg [Microsoft Edge toevoegen aan macOS-apparaten met behulp van Microsoft Intune](~/apps/apps-edge-macos.md) voor meer informatie.

#### <a name="retirement-of-intune-managed-browser--5728447---"></a>Buiten gebruik stellen van Microsoft Intune Managed Browser<!--5728447 -->
De Intune Managed Browser wordt buiten gebruik gesteld. Gebruik Microsoft Edge als uw beveiligde Intune-browser. Voor meer informatie bekijkt u het gedeelte [Actie ondernemen: Gebruik Microsoft Edge als uw beveiligde Intune-browser](~/fundamentals/whats-new.md#take-action-use-microsoft-edge-for-your-protected-intune-browser-experience) in de sectie [Aankondigingen](~/fundamentals/whats-new.md#notices) hieronder.

<!-- ########################## -->
## <a name="week-of-january-20-2020-2001-service-release"></a>Week van 20 januari 2020 (2001 servicerelease)

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Appbeheer

#### <a name="user-experience-change-when-adding-apps-to-intune---4705829-----"></a>Wijziging in gebruikerservaring bij het toevoegen van apps aan Intune<!-- 4705829   -->
U ziet een nieuwe gebruikerservaring wanneer u apps toevoegt via Intune. Deze ervaring biedt dezelfde instellingen en gegevens die u eerder hebt gebruikt. De nieuwe ervaring volgt echter stappen die vergelijkbaar zijn met die van een wizard voordat een app wordt toegevoegd aan Intune. Deze nieuwe ervaring biedt ook een controlepagina voordat u de app toevoegt. Selecteer vanuit het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) de opties **Apps** > **Alle apps** > **Toevoegen**. Zie [Web-apps toevoegen aan Microsoft Intune](~/apps/apps-add.md) voor meer informatie.

#### <a name="require-win32-apps-to-restart----5622282-----"></a>Vereisen dat Win32-apps opnieuw worden gestart <!-- 5622282   -->
U kunt vereisen dat een Win32-app opnieuw moet worden gestart na een geslaagde installatie. U kunt ook de hoeveelheid tijd (de respijtperiode) kiezen, voordat opnieuw wordt gestart.

#### <a name="user-experience-change-when-configuring-apps-in-intune---4207990-----"></a>Wijziging in gebruikerservaring bij het configureren van apps in Intune<!-- 4207990   -->
U ziet een nieuwe gebruikerservaring bij het maken van app-configuratiebeleid in Intune. Deze ervaring biedt dezelfde instellingen en gegevens die u eerder hebt gebruikt. De nieuwe ervaring volgt echter stappen die vergelijkbaar zijn met die van een wizard voordat beleid wordt toegevoegd aan Intune. Selecteer in het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) de optie **Apps** > **App-configuratiebeleid** > **Toevoegen**. Zie [App-configuratiebeleidsregels voor Microsoft Intune](~/apps/app-configuration-policies-overview.md) voor meer informatie. 

#### <a name="intune-support-for-additional-microsoft-edge-for-windows-10-deployment-channel---5861774---"></a>Intune-ondersteuning voor het extra implementatiekanaal van Microsoft Edge voor Windows 10<!-- 5861774 -->
Microsoft Intune biedt nu ondersteuning voor het extra **stabiele** implementatiekanaal voor de app Microsoft Edge (versie 77 en hoger) voor Windows 10. Het **stabiele** kanaal is het aanbevolen kanaal voor een brede implementatie van Microsoft Edge voor Windows 10 in Enterprise-omgevingen. Dit kanaal wordt elke zes weken bijgewerkt en elke release bevat verbeteringen uit het **Beta**-kanaal. Naast het **stabiele** kanaal en het **Beta**-kanaal, biedt Intune ook ondersteuning voor een **Dev**-kanaal. Raadpleeg [Microsoft Edge voor Windows 10 - App-instellingen configureren](~/apps/apps-windows-edge.md#configure-app-settings) voor meer informatie.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="improved-user-interface-experience-when-configuring-exchange-activesync-on-premises-connector-ui---5695492-----"></a>Verbeterde ervaring voor de gebruikersinterface bij het configureren van de UI voor de on-premises Exchange ActiveSync-connector<!-- 5695492   -->
We hebben de ervaring voor het [configureren van de on-premises Exchange ActiveSync-connector](../protect/exchange-connector-install.md) bijgewerkt. De bijgewerkte ervaring maakt gebruik van één deelvenster voor het configureren, bewerken en samenvatten van de details van uw on-premises connectors. 

#### <a name="add-automatic-proxy-settings-to-wi-fi-profiles-for-android-enterprise-work-profiles---4490822-----"></a>Automatische proxyinstellingen toevoegen aan Wi-Fi-profielen voor Android Enterprise-werkprofielen<!-- 4490822   -->
Op apparaten met een Android Enterprise-werkprofiel kunt u Wi-Fi-profielen maken. Wanneer u het type Wi-Fi Enterprise kiest, kunt u ook het type EAP (Extensible Authentication Protocol) invoeren dat in uw Wi-Fi-netwerk wordt gebruikt.

Wanneer u nu het Enterprise-type kiest, kunt u ook automatische proxyinstellingen invoeren, inclusief een proxyserver-URL, zoals `proxy.contoso.com`.

Ga naar [Wi-Fi-instellingen voor apparaten met Android Enterprise en Android Kiosk in Microsoft Intune toevoegen](../configuration/wi-fi-settings-android-enterprise.md) om de huidige Wi-Fi-instellingen te zien die u kunt configureren.

Van toepassing op:
- Android Enterprise - Werkprofiel

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="block-android-enrollments-by-device-manufacturer--5197392----"></a>Android-inschrijvingen blokkeren op apparaatfabrikant<!--5197392  -->
U kunt inschrijven van bepaalde apparaten blokkeren, op basis van de fabrikant van het apparaat. Dit is van toepassing op apparaten met Android-apparaatbeheerder en een Android Enterprise-werkprofiel. Ga naar het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) > **Apparaten** > **Inschrijvingsbeperkingen** om de inschrijvingsbeperkingen te zien.

#### <a name="improvements-to-the-iosipados-create-enrollment-type-profile-ui---6055005---"></a>Verbeteringen in de UI voor het iOS/iPadOS-profielinschrijvingstype maken<!-- 6055005 -->
Voor iOS/iPadOS-gebruikersinschrijving is de pagina **Profielinschrijvingstype maken** **Instellingen** gestroomlijnd om het keuzeproces voor **Inschrijvingstype** te verbeteren met behoud van dezelfde functionaliteit. Als u de nieuwe UI wilt bekijken, gaat u naar het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) > **Apparaten** > **iOS** > **iOS-inschrijving** > **Inschrijvingstypen** > **Profiel maken** > **pagina Instellingen**. Raadpleeg [Een gebruikersinschrijvingsprofiel maken in Intune](../enrollment/ios-user-enrollment.md#create-a-user-enrollment-profile-in-intune) voor meer informatie.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Apparaatbeheer

#### <a name="new-information-in-device-details---4471759-5604099----"></a>Nieuwe informatie in apparaatdetails<!-- 4471759 5604099  -->
De pagina **Overzicht** voor apparaten bevat nu de volgende informatie:
- Geheugencapaciteit (hoeveelheid fysiek geheugen op het apparaat)
- Geheugenopslag (hoeveelheid fysieke opslag op het apparaat) 
- CPU-architectuur


#### <a name="ios-bypass-activation-lock-remote-action-renamed-to-disable-activation-lock---5904591----"></a>De externe actie iOS-activeringsvergrendeling overslaan heet nu Activeringsvergrendeling uitschakelen <!--5904591  -->
De externe actie **Activeringsvergrendeling overslaan** heeft een nieuwe naam gekregen en heet nu **Activeringsvergrendeling uitschakelen**. Raadpleeg [iOS-activeringsvergrendeling met Intune uitschakelen](../remote-actions/device-activation-lock-bypass.md) voor meer informatie.

#### <a name="windows-10-feature-update-deployment-support-for-autopilot-devices---5948137-----"></a>Ondersteuning voor implementatie van Windows 10-onderdelenupdate voor Autopilot-apparaten<!-- 5948137   -->
Intune biedt nu ondersteuning voor geregistreerde Autopilot-apparaten met behulp van [implementaties van Windows 10-onderdelenupdates](../protect/windows-update-for-business-configure.md#windows-10-feature-updates).

Beleidsregels voor de Windows 10-onderdelenupdates kunnen niet worden toegepast tijdens de OOBE (Out of Box Experience) van Autopilot en worden alleen toegepast nadat de eerste scan van Windows Update is uitgevoerd nadat een apparaat is ingericht (doorgaans een dag).


<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="windows-autopilot-deployment-reports-preview----3856172-----"></a>Windows Autopilot-implementatierapporten (preview) <!-- 3856172   -->
In een nieuw rapport kunt u de details bekijken van elk apparaat dat via Windows Autopilot is geïmplementeerd. Zie [Autopilot-implementatierapport](../enrollment/enrollment-autopilot.md#autopilot-deployments-report) voor meer informatie.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer

#### <a name="new-intune-built-in-role-endpoint-security-manager--4253397-----"></a>Nieuwe ingebouwde Intune-rol Eindpuntbeveiligingsbeheerder<!--4253397   -->
Er is een nieuwe ingebouwde Intune-rol beschikbaar: Eindpuntbeveiligingsbeheerder. Deze nieuwe rol biedt beheerders volledige toegang tot het knooppunt Eindpuntbeheer in Intune en alleen-lezentoegang tot andere gebieden. De rol is een uitbreiding van de rol Beveiligingsbeheerder van Azure AD. Als u momenteel alleen Algemene beheerder als rol gebruik, zijn er geen wijzigingen nodig. Als u rollen gebruikt, en u de granulariteit wilt gebruiken die de rol Eindpuntbeveiligingsbeheerder biedt, wijst u die rol toe wanneer deze beschikbaar is. Zie [Op rollen gebaseerd toegangsbeheer](role-based-access-control.md) voor meer informatie over ingebouwde rollen.

<!-- ########################## -->
## <a name="week-of-january-6-2020"></a>De week van 6 januari 2020

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Appbeheer

#### <a name="smime-support-for-microsoft-outlook-for-ios---2669398---"></a>S/MIME-ondersteuning voor Microsoft Outlook voor iOS<!-- 2669398 -->
Intune biedt ondersteuning voor het leveren van S/MIME-ondertekening- en versleutelingscertificaten die kunnen worden gebruikt met Outlook voor iOS op iOS-apparaten. Zie [Sensitivity labeling and protection in Outlook for iOS and Android](https://aka.ms/omsmime) (Gevoeligheidslabels en -bescherming in Outlook voor iOS en Android) voor meer informatie.

#### <a name="cache-win32-app-content-using-microsoft-connected-cache-server---6030314---"></a>Win32-app-inhoud in de cache opslaan met Microsoft Connected Cache-server<!-- 6030314 -->
U kunt een Microsoft Connected Cache-server op uw Configuration Manager-distributiepunten installeren om inhoud van Intune Win32-apps op te slaan in de cache. Zie [Microsoft Connected Cache in Configuration Manager: ondersteuning voor Intune Win32-apps](https://docs.microsoft.com/configmgr/core/plan-design/hierarchy/microsoft-connected-cache#bkmk_intune) voor meer informatie.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer

#### <a name="windows-10-administrative-templates-admx-profiles-now-support-scope-tags---5137390---"></a>Profielen voor Windows 10-beheersjablonen (ADMX) ondersteunen nu bereiktags <!--5137390 -->
U kunt nu bereiktags toewijzen aan beheersjabloonprofielen (ADMX). Ga hiervoor naar **Intune** > **Apparaten** > **Configuratieprofielen** > kies een beheersjabloonprofiel in de lijst > **Eigenschappen** > **Bereiktags**. Zie [Assign scope tags to other objects](../fundamentals/scope-tags.md#assign-scope-tags-to-other-objects) (bereiktags toewijzen aan andere objecten) voor meer informatie over bereiktags.

<!-- ########################## -->
## <a name="week-of-december-30-2019"></a>Week van 30 december 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Appbeheer

#### <a name="retrieve-personal-recovery-key-from-mem-encrypted-macos-devices---4851745---"></a>Persoonlijke herstelsleutel ophalen van met MEM versleutelde macOS-apparaten<!-- 4851745 -->
Eindgebruikers kunnen hun persoonlijke herstelsleutel (FileVault Key) ophalen met behulp van de Bedrijfsportal-app voor iOS. Het apparaat met de persoonlijke herstelsleutel moet zijn geregistreerd bij Intune en moet zijn versleuteld met FileVault via intune. Met de Bedrijfsportal-app voor iOS kan een eindgebruiker zijn persoonlijke herstelsleutel ophalen op zijn versleutelde macOS-apparaat door te klikken op **Herstelsleutel ophalen**. U kunt de herstelsleutel ook ophalen uit Intune door **Apparaten** > *het versleutelde en geregistreerde macOS-apparaat* > **Herstelsleutel ophalen** te selecteren. Zie [FileVault-versleuteling voor macOS](~/protect/encrypt-devices.md#filevault-encryption-for-macos) voor meer informatie over FileVault.

#### <a name="ios-and-ipados-user-licensed-vpp-apps---5619268---"></a>VPP-apps met gebruikerslicenties voor iOS- en iPadOS<!-- 5619268 -->
Op door de gebruiker ingeschreven iOS- en iPadOS-apparaten krijgen eindgebruikers niet langer pas gemaakte VPP-toepassingen met apparaatlicenties te zien die zijn geïmplementeerd als beschikbaar. Eindgebruikers blijven echter alle gebruikerslicenties voor VPP in de Bedrijfsportal zien. Zie [iOS- en macOS-apps beheren die zijn aangeschaft via een Apple Volume Purchase Program met Microsoft Intune](~/apps/vpp-apps-ios.md) voor meer informatie over VPP-apps.

<!-- ########################## -->
## <a name="week-of-december-23-2019"></a>Week van 23 december 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Appbeheer

#### <a name="notice---windows-10-1703-rs2-will-be-moving-out-of-support----5026679---"></a>Kennisgeving: Windows 10 1703 (RS2) wordt binnenkort niet meer ondersteund <!-- 5026679 -->
Vanaf 9 oktober 2018, biedt Microsoft geen ondersteuning meer voor de edities Home, Pro en Pro voor werkstations van Windows 10 1703 (RS2). Voor de edities Enterprise en Education van Windows 10 1703 (RS2) wordt sinds 8 oktober 2019 geen ondersteuning meer geboden. Vanaf 26 december 2019 wordt de minimale versie van de Windows Bedrijfsportal-app bijgewerkt naar Windows 10 1709 (RS3). Op computers met versies van vóór 1709 worden bijgewerkte versies van de app niet meer ontvangen via de Microsoft Store. We hebben deze wijziging eerder meegedeeld aan klanten die oudere versies van Windows 10 beheren via het berichtencentrum. Zie het [informatieblad over de levenscyclus van Windows](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet) voor meer informatie.

<!-- ########################## -->

## <a name="week-of-december-16-2019"></a>Week van 16 december 2019

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="updates-to-administrative-templates-for-windows-10-devices----5941568---"></a>Updates voor Beheersjablonen voor Windows 10-apparaten <!-- 5941568 -->

U kunt ADMX-sjablonen in Microsoft Intune gebruiken om de instellingen voor Microsoft Edge, Office en Windows te beheren. De volgende updates zijn doorgevoerd door beleidsinstellingen van Beheersjablonen in Intune:

- Er is ondersteuning toegevoegd voor de versies 78 en 79 van Microsoft Edge.
- Omvat de ADMX-bestanden van 11 november 2019 in [Beheersjabloon-bestanden (ADMX/ADML) en het hulpprogramma voor het aanpassen van Office voor Office 365 ProPlus, Office 2019 en Office 2016](https://www.microsoft.com/download/details.aspx?id=49030).

Bekijk voor meer informatie over ADMX-sjablonen in Intune het artikel [Windows 10-sjablonen gebruiken voor het configureren van instellingen voor groepsbeleid in Microsoft Intune](../configuration/administrative-templates-windows.md).

Van toepassing op:

- Windows 10 en hoger

## <a name="week-of-december-9-2019-1912-service-release"></a>Week van 9 december 2019 (1912 servicerelease)

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Appbeheer

#### <a name="migrating-to-microsoft-edge-for-managed-browsing-scenarios---5173762---"></a>Migreren naar Microsoft Edge voor beheerdebrowserscenario's<!-- 5173762 -->
Met het naderen van de buitengebruikstelling van de Intune Managed Browser zijn wijzigingen aangebracht in het beveiligingsbeleid voor apps om de benodigde stappen voor het migreren van uw gebruikers naar Edge te vereenvoudigen. De opties voor de instelling **Overdracht van webinhoud met andere apps beperken** van het beveiligingsbeleid voor apps zijn gewijzigd naar de volgende opties:

- Elke app
- Intune Managed Browser
- Microsoft Edge
- Niet-beheerde browser 

Wanneer u **Microsoft Edge** selecteert, ontvangen uw eindgebruikers een melding over voorwaardelijke toegang, waarin wordt aangegeven dat Microsoft Edge vereist is voor beheerdebrowserscenario's. Ze worden gevraagd om Microsoft Edge te downloaden en zich aan te melden met hun AAD-account, als ze dit nog niet hebben gedaan.  Dit is kan worden vergeleken met de instelling van de app-configuratie-instellingen `com.microsoft.intune.useEdge` op **waar** voor uw MAM-apps. Voor bestaand beveiligingsbeleid voor apps dat gebruikmaakte van de **door beleid beheerde browsers** wordt nu **Intune Managed Browser** geselecteerd. Het gedrag zal niet wijzigen. Dit betekent dat uw gebruikers via berichten zal worden gevraagd Microsoft Edge te gebruiken als u de app-configuratie-instelling **useEdge** hebt ingesteld op **Waar**. We stimuleren alle klanten aan om hun app-beveiligingsbeleid bij te werken met **Overdracht van webinhoud met andere apps beperken** om ervoor te zorgen dat gebruikers de juiste richtlijnen zien voor de overgang naar Microsoft Edge, ongeacht vanuit welke app koppelingen worden gestart. 

#### <a name="configure-app-notification-content-for-organization-accounts---2576686----"></a>Inhoud van app-meldingen voor organisatieaccounts configureren<!-- 2576686  -->
Met beveiligingsbeleid voor apps in Intune (APP) op Android- en iOS-apparaten kunt u inhoud voor app-meldingen beheren voor organisatieaccounts. U kunt een optie selecteren (Toestaan, Organisatiegegevens blokkeren of Geblokkeerd) om op te geven hoe meldingen voor organisatieaccounts voor de geselecteerde app worden weergegeven. Deze functie vereist ondersteuning van apps en is mogelijk niet beschikbaar voor alle apps waarvoor APP is ingeschakeld. Outlook voor iOS 4.15.0 (of hoger) en Outlook voor Android 4.83.0 (of hoger) biedt ondersteuning voor deze instelling. De instelling is beschikbaar in de console, maar de functionaliteit wordt pas van kracht na 16 december 2019. Zie [Wat is beveiligingsbeleid voor apps?](../apps/app-protection-policy.md) voor meer informatie over APP.

#### <a name="microsoft-app-icons-update--4677605----"></a>Nieuwe pictogrammen voor Microsoft-apps<!--4677605  -->
De pictogrammen die worden gebruikt voor Microsoft-apps in het deelvenster met apps voor het app-beveiligingsbeleid en het app-configuratiebeleid zijn bijgewerkt.

#### <a name="require-use-of-approved-keyboards-on-android--4761794----"></a>Vereist gebruik van goedgekeurde toetsenborden in Android<!--4761794  -->
Als onderdeel van een beveiligingsbeleid voor apps kunt u de instelling [**Goedgekeurde toetsenborden**](../apps/app-protection-policy-settings-android.md#data-protection) opgeven om te beheren welke Android-toetsenborden kunnen worden gebruikt met beheerde Android-apps. Wanneer een gebruiker de beheerde app opent en nog geen een goedgekeurd toetsenbord voor die app gebruikt, wordt hij gevraagd om over te schakelen naar een van de goedgekeurde toetsenborden die al op het apparaat zijn geïnstalleerd. Als het nodig is, wordt er een koppeling weergegeven om een goedgekeurd toetsenbord te downloaden uit de Google Play Store, die de gebruiker kan installeren en instellen. De gebruiker kan alleen tekstvelden in een beheerde app bewerken wanneer het actieve toetsenbord niet een van de goedgekeurde toetsenborden is.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="updated-single-sign-on-experience-for-apps-and-websites-on-your-ios-ipados-and-macos-devices---4999578----"></a>Nieuwe ervaring met eenmalige aanmelding voor apps en websites op iOS-, iPadOS- en macOS-apparaten<!-- 4999578  -->
Intune heeft meer instellingen voor eenmalige aanmelding (SSO) toegevoegd voor iOS-, iPadOS-en macOS-apparaten. U kunt nu SSO-extensies voor omleiding configureren die zijn geschreven door uw organisatie of door uw id-provider. Gebruik deze instellingen on naadloze eenmalige aanmelding te configureren voor apps en websites die gebruikmaken van moderne verificatiemethodes, zoals OAuth en SAML2. 

Deze nieuwe instellingen zijn een uitbreiding van de vorige instellingen voor SSO-app-extensies en de ingebouwde Kerberos-uitbreiding van Apple (**Apparaten** > **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS/iPadOS** of **macOS** voor het platformtype > **Apparaatfuncties** voor het profieltype). 

Ga naar [SSO op iOS](../configuration/ios-device-features-settings.md#single-sign-on-app-extension) en [SSO op macOS](../configuration/macos-device-features-settings.md#single-sign-on-app-extension) voor een overzicht van de instellingen voor SSO-app-extensies die u kunt configureren.

Van toepassing op:

- iOS/iPadOS
- macOS

#### <a name="we-have-updated-two-device-restriction-settings-for-ios-and-ipados-devices-to-correct-their-behavior---5701352------"></a>Er zijn twee instellingen voor apparaatbeperking voor iOS- en iPadOS-apparaten bijgewerkt om het gedrag ervan te corrigeren<!-- 5701352    -->
Voor iOS-apparaten kunt u beperkingsprofielen voor apparaten maken die **Draadloze PKI-updates toestaan** en **Beperkte USB-modus blokkeren** (**Apparaten** > **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS/iPadOS** voor platform > **Apparaatbeperkingen** voor het profieltype). Vóór deze release waren de instellingen en beschrijvingen van de gebruikersinterface voor de volgende instellingen onjuist. Deze zijn nu gecorrigeerd. Vanaf deze release is het gedrag van de instellingen als volgt:

**Draadloze PKI-updates blokkeren**: **Blokkeren** voorkomt dat uw gebruikers software-updates ontvangen tenzij het apparaat is verbonden met een computer. **Niet geconfigureerd** (standaard): hiermee staat u toe dat een apparaat software-updates ontvangt zonder dat het verbonden is met een computer.
- Voorheen kon u met deze instelling het volgende configureren: Met **Toestaan** konden uw gebruikers software-updates ontvangen zonder dat hun apparaten zijn aangesloten op een computer.
**USB-accessoires toestaan terwijl het apparaat is vergrendeld**: Met **Toestaan** kunnen USB-accessoires gegevens uitwisselen met een apparaat dat al meer dan een uur is vergrendeld. **Niet geconfigureerd** (standaard) werkt de beperkte USB-modus niet bij op het apparaat en USB-accessoires kunnen geen gegevens overdragen vanaf het apparaat als het meer dan een uur is vergrendeld.
- Voorheen kon u met deze instelling het volgende configureren: Met **Blokkeren** kon u de beperkte USB-modus uitschakelen op apparaten in de supervisiemodus.

Zie [iOS- en iPadOS-apparaatinstellingen om functies toe te staan of te beperken met Intune](../configuration/device-restrictions-ios.md) voor meer informatie over de configureerbare instellingen.

Deze functie is van toepassing op:

- OS/iPadOS

#### <a name="wired-network-device-configuration-profiles-for-macos-devices---3508686----"></a>Configuratieprofielen voor een bekabeld netwerkapparaat voor macOS-apparaten<!-- 3508686  -->
   > [!NOTE]
   > Deze functie is vertraagd, maar wordt binnenkort vrijgegeven.

#### <a name="block-users-from-configuring-certificate-credentials-in-the-managed-keystore-on-android-enterprise-device-owner-devices---3311998---"></a>Voorkomen dat gebruikers certificaatreferenties configureren in de beheerde sleutelopslag op Android Enterprise-apparaten van eigenaars<!-- 3311998 -->
Op Android Enterprise-apparaten van een eigenaar kunt u een nieuwe instelling configureren die voorkomt dat gebruikers hun certificaatreferenties configureren in de beheerde keystore (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** voor platform > **Alleen apparaateigenaar > Apparaatbeperkingen** voor profieltype > **Gebruikers en accounts**).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Apparaatbeheer

#### <a name="protected-wipe-action-now-available--51150000---"></a>De actie Beveiligd wissen is nu beschikbaar<!--51150000 -->
U hebt nu de mogelijkheid om de actie Apparaat wissen te gebruiken om een apparaat beveiligd te wissen. Beveiligd wissen werkt hetzelfde als standaard wissen, behalve dat deze actie niet kan worden omzeild door het apparaat uit te schakelen. Als de opdracht Beveiligd wissen is gegeven, wordt het apparaat gereset totdat de opdracht is uitgevoerd. In sommige configuraties kan deze actie ervoor zorgen dat het apparaat niet opnieuw kan worden opgestart. Zie [Apparaten buiten gebruik stellen of wissen](../remote-actions/devices-wipe.md) voor meer informatie.

#### <a name="device-ethernet-mac-address-added-to-devices-overview-page--5562275---"></a>Ethernet MAC-adres van apparaat toegevoegd aan de overzichtspagina van het apparaat<!--5562275 -->
U kunt nu het Ethernet MAC-adres van een apparaat zien op de pagina met details van het apparaat (**Apparaten** > **Alle apparaten** > een apparaat kiezen > **Overzicht**.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Apparaatbeveiliging

#### <a name="improved-experience-on-a-shared-device-when-device-based-conditional-access-policies-are-enabled---1734096----"></a>Verbeterde ervaring op een gedeeld apparaat wanneer op apparaten gebaseerd beleid voor voorwaardelijke toegang is ingeschakeld<!-- 1734096  -->
We hebben de ervaring verbeterd op een gedeeld apparaat met meerdere gebruikers die op apparaten gebaseerd beleid voor voorwaardelijke toegang gebruiken. Dit hebben we gedaan door de nieuwste nalevingsevaluatie voor de gebruiker te controleren bij het afdwingen van het beleid. Zie de volgende overzichtsartikelen voor meer informatie:
- [Overzicht van voorwaardelijke toegang in Azure](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)
- [Overzicht van apparaatnaleving in Intune](../protect/device-compliance-get-started.md)

#### <a name="use-pkcs-certificate-profiles-to-provision-devices-with-certificates---2317124-2317130-2317139-2340517-2340528-2340529----"></a>PKCS-certificaatprofielen gebruiken om apparaten in te richten met certificaten<!-- 2317124, 2317130, 2317139, 2340517, 2340528, 2340529  -->
U kunt nu PKCS-certificaatprofielen gebruiken om certificaten uit te geven aan *apparaten* met Android for Work, iOS en Windows. Dit geldt wanneer deze zijn gekoppeld aan profielen zoals die voor Wi-Fi en VPN. Voorheen ondersteunden deze drie platformen alleen op gebruikers gebaseerde certificaten. Ondersteuning op basis wat alleen beschikbaar op macOS.

> [!NOTE]
> PKCS-certificaatprofielen worden niet ondersteund met Wi-Fi-profielen. Gebruik in plaats daarvan SCEP-certificaatprofielen wanneer u een [EAP-type](../configuration/wi-fi-settings-windows.md#enterprise-profile)gebruikt.

Als u een certificaat op basis van een apparaat wilt gebruiken wanneer u [een PKCS-certificaatprofiel maakt](../protect/certficates-pfx-configure.md#create-a-pkcs-certificate-profile) voor de ondersteunde platformen, selecteert u **Instellingen**. U ziet nu de instelling voor **Certificaattype**, die ondersteuning biedt voor de opties Apparaat en Gebruiker.



<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="centralized-audit-logs--5603185-5697164---"></a>Gecentraliseerde auditlogboeken<!--5603185, 5697164 -->
Een nieuwe gecentraliseerde functie voor auditlogboeken verzamelt nu auditlogboeken voor alle categorieën op één pagina. U kunt de logboeken filteren om de gegevens op te halen die u zoekt. Als u de auditlogboeken wilt bekijken, gaat u naar **Tenantbeheer** > **Auditlogboeken**. 

#### <a name="scope-tag-information-included-in-audit-log-activity-details--5763534---"></a>Informatie over bereiktags opgenomen in de details van auditlogboeken<!--5763534 -->
De details van de activiteiten in het auditlogboek bevatten nu informatie over bereiktags (voor Intune-objecten die ondersteuning bieden voor bereiktags). Zie [Auditlogboeken gebruiken om gebeurtenissen bij te houden en te controleren](monitor-audit-logs.md) voor meer informatie over auditlogboeken.


<!-- ########################## -->
## <a name="week-of-december-2-2019"></a>Week van 2 december 2019

#### <a name="new-microsoft-endpoint-configuration-manager-co-management-licensing--5027281--"></a>Nieuw co-beheer met Microsoft Endpoint Configuration Manager-licentiëring<!--5027281-->
Configuration Manager-klanten met Software Assurance hebben toegang tot Intune-co-beheer voor Windows 10-pc's zonder dat ze een extra Intune-licentie voor co-beheer hoeven aan te schaffen. Klanten hoeven geen afzonderlijke Intune/EMS-licenties meer toe te wijzen aan hun eindgebruikers voor het co-beheer van Windows 10.
- Apparaten die worden beheerd door Configuration Manager en die zijn ingeschreven bij co-beheer hebben bijna dezelfde rechten als zelfstandige door Intune beheerde pc's. Na het opnieuw instellen kunnen ze echter niet opnieuw worden ingericht met behulp van Autopilot.
- Voor Windows 10-apparaten die via een andere methode zijn ingeschreven bij Intune zijn volledige Intune-licenties vereist.
- Voor apparaten op andere platforms zijn nog steeds volledige Intune-licenties vereist.

Zie [Licentievoorwaarden](https://www.microsoft.com/en-us/Licensing/product-licensing/products) voor meer informatie.


<!-- ########################## -->
## <a name="week-of-november-18-2019-1911-service-release"></a>Week van 18 november 2019 (1911 servicerelease)

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Appbeheer

#### <a name="ui-update-when-selectively-wiping-app-data---4102028---"></a>Update van gebruikersinterface bij selectief wissen van app-gegevens<!-- 4102028 -->
De gebruikersinterface voor het selectief wissen van app-gegevens in Intune is bijgewerkt. De gebruikersinterface wordt onder andere op deze punten gewijzigd:
- Een vereenvoudigde ervaring in de vorm van een wizard, beknopt weergegeven binnen één deelvenster.
- Een update van de maakstroom om toewijzingen toe te voegen.
- Een samenvattingspagina van alle items die zijn ingesteld bij het weergeven van eigenschappen, vóór het maken van een nieuw beleid of bij het bewerken van een eigenschap. Tijdens het bewerken van eigenschappen toont de samenvatting ook alleen een lijst met items in de categorie met eigenschappen die wordt bewerkt.

Zie [Alleen zakelijke gegevens wissen uit door Intune beheerde apps](~/apps/apps-selective-wipe.md) voor meer informatie.

#### <a name="ios-and-ipados-third-party-keyboard-support---4922950---"></a>Toetsenbordondersteuning voor iOS en iPadOS van derden<!-- 4922950 -->
In maart 2019 is aangekondigd dat de instelling voor iOS-beleid voor appbeveiliging Toetsenborden van derden niet meer wordt ondersteund. De functie keert in Intune terug met ondersteuning voor iOS en iPadOS. U kunt deze instelling inschakelen via het tabblad **Gegevensbescherming** van een nieuw of bestaand iOS-/iPadOS-beleid voor appbeveiliging. Zoek de instelling **Toetsenborden van derden** onder **Gegevensoverdracht**.

Het gedrag van deze beleidsinstelling wijkt enigszins af van de vorige implementatie. In apps met meerdere identiteiten met SDK-versie 12.0.16 en hoger, gericht op beleid voor appbeveiliging waarbij deze instelling is ingesteld op **Blokkeren**, kunnen eindgebruikers voor hun organisatie- en persoonlijke accounts geen toetsenborden van derden kiezen. Apps met SDK-versies 12.0.12 en eerder blijven het gedrag vertonen dat is vastgelegd in de titel van de blogpost, [Bekend probleem: toetsenborden van derden worden in iOS niet geblokkeerd voor persoonlijke accounts](https://aka.ms/3rdparty_iOS_Intune).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="target-macos-user-groups-to-require-jamf-management---4061739----"></a>Richten op macOS-gebruikersgroepen waarvoor Jamf-beheer is vereist<!-- 4061739  --> 
U kunt zich op specifieke groepen gebruikers richten die hun [macOS-apparaten laten beheren door Jamf](../protect/conditional-access-integrate-jamf.md). Hierdoor kunt u de nalevingsintegratie van Jamf toepassen op een subset van macOS-apparaten, terwijl andere apparaten door Intune worden beheerd. Als u de Jamf-integratie al gebruikt, zijn alle gebruikers standaard bedoeld voor de integratie.

#### <a name="new-exchange-activesync-settings-when-creating-an-email-device-configuration-profile-on-ios-devices---4892824-----"></a>Nieuwe Exchange ActiveSync-instellingen bij het maken van een configuratieprofiel voor een e-mailapparaat op iOS-apparaten<!-- 4892824   --> 
U kunt op iOS/iPadOS-apparaten e-mailconnectiviteit configureren in een apparaatconfiguratieprofiel (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS/iPadOS** als platform > **E-mail** als profieltype). 

Er zijn nieuwe Exchange ActiveSync-instellingen beschikbaar, waaronder:
- **Exchange-gegevens om te synchroniseren**: Kies de Exchange-services voor het synchroniseren (of blokkeren van de synchronisatie) van de agenda, contactpersonen, herinneringen, notities en e-mail.
- **Gebruikers toestaan om de synchronisatie-instellingen te wijzigen**: Gebruikers toestaan (weigeren) de synchronisatie-instellingen voor deze services op hun apparaten te wijzigen.  

Ga naar [E-mailprofielinstellingen voor iOS-apparaten in Intune](../configuration/email-settings-ios.md) voor meer informatie over deze instelling. 

Van toepassing op:

- iOS 13.0 en hoger
- iPadOS 13.0 en hoger

#### <a name="prevent-users-from-adding-personal-google-accounts-to-android-enterprise-fully-managed-and-dedicated-devices---5353228-----"></a>Voorkomen dat gebruikers persoonlijke Google-accounts toevoegen aan volledig beheerde en toegewezen Android Enterprise-apparaten<!-- 5353228   -->
Op volledig beheerde en toegewezen Android Enterprise-apparaten is een nieuwe instelling aanwezig waarmee wordt voorkomen dat gebruikers persoonlijke Google-accounts kunnen maken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** als platform > **Alleen apparaateigenaar > Apparaatbeperkingen** als profieltype > **Instellingen voor gebruikers en accounts** > **Persoonlijke Google-accounts**).

Ga naar [Met Android Enterprise-apparaatinstellingen functies toestaan of beperken met behulp van Intune](../configuration/device-restrictions-android-for-work.md) als u alle configureerbare instellingen wilt bekijken.

Van toepassing op:

- Volledig beheerde Android Enterprise-apparaten
- Toegewezen Android Enterprise-apparaten

#### <a name="server-side-logging-for-siri-commands-setting-is-removed-in-iosipados-device-restrictions-profile----5468501-----"></a>De instelling Logboekregistratie op de server voor Siri-opdrachten wordt verwijderd in het profiel voor iOS-/iPadOS-apparaatbeperkingen <!-- 5468501   -->
Op iOS- en iPadOS-apparaten wordt de instelling **Logboekregistratie op de server voor Siri-opdrachten** uit de Microsoft Endpoint Manager-beheerconsole verwijderd (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS/iPadOS** als platform > **Apparaatbeperkingen** als profieltype > **Ingebouwde apps**). 

Deze instelling heeft geen effect op apparaten. Als u de instelling van bestaande profielen wilt verwijderen, opent u het profiel, brengt u de gewenste wijzigingen aan en slaat u het profiel op. Het profiel wordt bijgewerkt en de instelling wordt van de apparaten verwijderd.

Zie [iOS- en iPadOS-apparaatinstellingen om functies toe te staan of te beperken met Intune](../configuration/device-restrictions-ios.md) als u alle configureerbare instellingen wilt bekijken.

Van toepassing op:

- iOS/iPadOS

#### <a name="windows-10-feature-updates-public-preview---2384877---"></a>Windows 10-onderdelenupdates (openbare preview)<!-- 2384877 -->
U kunt nu [Windows 10-onderdelenupdates](../protect/windows-update-for-business-configure.md#windows-10-feature-updates) implementeren op Windows 10-apparaten. Windows 10-onderdelenupdates zijn een nieuw beleid voor software-updates waarmee de versie van Windows 10 wordt ingesteld die door apparaten moet worden geïnstalleerd en op het systeem blijft. U kunt dit nieuwe beleidstype samen met uw bestaande Windows 10-updateringen gebruiken.

Op apparaten die het beleid voor Windows 10-onderdelenupdates ontvangen, wordt de opgegeven versie van Windows geïnstalleerd en blijft deze versie tot het beleid wordt gewijzigd of verwijderd. Apparaten waarop een nieuwere versie van Windows wordt uitgevoerd, houden de huidige versie. Op apparaten die op een specifieke versie van Windows worden gehouden, kunnen kwaliteits- en beveiligingsupdates voor die versie nog steeds worden geïnstalleerd via Windows 10-updateringen.

Dit nieuwe type beleid wordt vanaf deze week voor tenants geïmplementeerd. Als dit beleid nog niet beschikbaar is voor uw tenant, komt het binnenkort.

#### <a name="add-and-change-key-information-in-plist-files-for-macos-applications---4736278---"></a>Belangrijke informatie toevoegen en wijzigen in PLIST-bestanden voor macOS-toepassingen<!-- 4736278 -->
Op macOS-apparaten kunt u nu een apparaatconfiguratieprofiel maken dat een eigenschappenlijstbestand (.plist) uploadt dat aan een app of het apparaat is gekoppeld (**Apparaten** > **Configuratieprofielen** > **Profiel maken** > **macOS** als platform > **Voorkeursbestand** als profieltype).

Alleen bepaalde apps ondersteunen beheerde voorkeuren. In deze apps kunt u mogelijk niet alle instellingen beheren. Upload een bestand met een eigenschappenlijstbestand waarmee apparaatkanaalinstellingen worden geconfigureerd, geen gebruikerskanaalinstellingen.

Zie [Een eigenschappenlijstbestand toevoegen aan macOS-apparaten met behulp van Microsoft Intune](../configuration/preference-file-settings-macos.md) voor meer informatie over deze functie.

Van toepassing op:

- macOS-apparaten met 10.7 en hoger

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Apparaatbeheer

#### <a name="edit-device-name-value-for-autopilot-devices---2640074---"></a>Waarde van apparaatnaam bewerken voor Autopilot-apparaten<!-- 2640074 -->
U kunt de waarde van de apparaatnaam voor aan Azure AD gekoppelde Autopilot-apparaten bewerken.  Zie [Kenmerken van Autopilot-apparaten bewerken](../enrollment/enrollment-autopilot.md#edit-autopilot-device-attributes) voor meer informatie.

#### <a name="edit-group-tag-value-for-autopilot-devices---4816775-----"></a>Waarde van groepstag bewerken voor Autopilot-apparaten<!-- 4816775   -->
U kunt de waarde van groepstag bewerken voor Autopilot-apparaten. Zie [Kenmerken van Autopilot-apparaten bewerken](../enrollment/enrollment-autopilot.md#edit-autopilot-device-attributes) voor meer informatie.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="updated-support-experience---5012398---"></a>Bijgewerkte ondersteuningservaring<!-- 5012398 -->

Met ingang van vandaag wordt een bijgewerkte en gestroomlijnde console-ervaring voor het [verkrijgen van help en ondersteuning voor Intune](get-support.md) voor tenants geïmplementeerd. Als deze nieuwe ervaring nog niet beschikbaar is voor u, komt dit binnenkort.

We hebben de in-console-zoekfunctie en de feedbackfunctie voor veelvoorkomende problemen verbeterd, evenals de workflow voor het opnemen van contact met de ondersteuning. Bij het openen van een supportprobleem ziet u realtime schattingen van wanneer u een antwoord via telefoon of e-mail kunt verwachten. Klanten met Premier- en Unified-ondersteuning kunnen eenvoudig een ernst van hun probleem specificeren om sneller ondersteuning te krijgen.

#### <a name="improved-intune-reporting-experience-public-preview----3791418---"></a>Verbeterde rapportering van Intune (openbare preview) <!-- 3791418 -->
Intune biedt nu verbeterde rapportagemogelijkheden, waaronder nieuwe rapporttypen, betere organisatie van rapporten, meer gerichte weergaven, verbeterde rapportfunctionaliteit, en consistente en actuele gegevens. Nieuwe rapporttypen richten zich op het volgende:
- **Operationeel**: bevat nieuwe records die zich richten op een negatieve status. 
- **Organisatorisch**: biedt een breder overzicht van de algemene status.
- **Historisch**: bevat patronen en trends gedurende een bepaalde periode.
- **Specialistisch**: hiermee kunt u onbewerkte gegevens gebruiken om uw eigen aangepaste rapporten te maken.

De eerste set nieuwe rapporten richt zich op de naleving van apparaten. Zie [Microsoft Intune Reporting Framework](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/New-Reporting-Framework-Coming-to-Intune/ba-p/1009553) (Rapportageframework van Microsoft Intune) en [Intune-rapporten](~/fundamentals/reports.md) voor meer informatie.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer

#### <a name="duplicate-custom-or-built-in-roles----1081938-----"></a>Dubbele aangepaste of ingebouwde rollen <!-- 1081938   -->
U kunt voortaan ingebouwde als aangepaste rollen kopiëren. Zie [Rol kopiëren](../fundamentals/create-custom-role.md#copy-a-role) voor meer informatie.

#### <a name="new-permissions-for-school-administrator-role----5621805----"></a>Nieuwe machtigingen voor de rol Schoolbeheerder <!-- 5621805  -->  
De twee nieuwe machtigingen **Profiel toewijzen** en **Apparaat synchroniseren** zijn aan de rol Schoolbeheerder toegevoegd > **Machtigingen** > **Inschrijvingsprogramma's**. Met de machtiging Apparaat synchroniseren kunnen groepsbeheerders Windows Autopilot-apparaten synchroniseren. Met de machtiging Profiel toewijzen kunnen ze door de gebruiker geïnitieerde Apple-inschrijvingsprofielen verwijderen. Het verleent ook machtigingen voor het beheren van Autopilot-apparaattoewijzingen en Autopilot-implementatieprofieltoewijzingen. Zie [Groepsbeheerders toewijzen](https://docs.microsoft.com/intune-education/group-admin-delegate) voor een lijst met alle machtigingen van de schoolbeheerder/groepsbeheerder. 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="security"></a>Beveiliging

#### <a name="bitlocker-key-rotation---2564951----"></a>BitLocker-sleutelrotatie<!-- 2564951  -->
U kunt een Intune-apparaatactie gebruiken om [BitLocker-herstelsleutels](../protect/encrypt-devices.md#rotate-bitlocker-recovery-keys) op afstand te roteren voor beheerde apparaten met Windows versie 1909 of hoger. Apparaten moeten worden geconfigureerd voor het ondersteunen van de rotatie van herstelsleutels om in aanmerking te komen voor het roteren van herstelsleutels.  

#### <a name="updates-to-dedicated-device-enrollment-to-support-scep-device-certificate-deployment----5198878----"></a>Updates voor de inschrijving van toegewezen apparaten ter ondersteuning van de implementatie van SCEP-apparaatcertificaten <!-- 5198878  -->
Intune biedt nu ondersteuning voor de implementatie van SCEP-apparaatcertificaten op toegewezen Android Enterprise-apparaten voor op certificaten gebaseerde toegang tot Wi-Fi-profielen. De implementatie werkt alleen als de app Microsoft Intune op het apparaat aanwezig is. Als gevolg hiervan hebben we de inschrijving voor toegewezen Android Enterprise-apparaten bijgewerkt. Nieuwe inschrijvingen worden nog steeds op dezelfde manier gestart (met QR, NFC, Zero-touch of apparaat-id), maar bevatten nu een stap waarvoor gebruikers de Intune-app moeten installeren. De app wordt automatisch en op voortschrijdende basis op bestaande apparaten geïnstalleerd.

#### <a name="intune-audit-logs-for-business-to-business-collaboration--5670211---"></a>Intune-auditlogboeken voor business-to-business-samenwerking<!--5670211 -->
Met B2B-samenwerking (business-to-business) kunt u de toepassingen en services van uw bedrijf veilig delen met gastgebruikers van andere organisaties, zonder dat u de controle verliest over uw eigen bedrijfsgegevens. Intune biedt nu ondersteuning voor auditlogboeken voor B2B-gastgebruikers. Als gastgebruikers bijvoorbeeld wijzigingen aanbrengen, kunnen deze gegevens worden vastgelegd via auditlogboeken. Zie [Wat is gastgebruikerstoegang in Azure Active Directory B2B?](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b) voor meer informatie


<!-- ########################## -->
## <a name="week-of-november-11-2019"></a>Week van 11 november 2019  

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Appbeheer  

#### <a name="improved-macos-enrollment-experience-in-company-portal----5074349----"></a>Verbeterde macOS-registratie in bedrijfsportal <!-- 5074349  -->  
De bedrijfsportal voor macOS-registratie heeft een eenvoudiger registratieproces dat nauwkeuriger is afgestemd met de bedrijfsportal voor iOS-registratie. Apparaatgebruikers zien nu het volgende:  

* Een gestroomlijndere gebruikers interface.  
* Een verbeterde controlelijst voor registratie.  
* Duidelijkere instructies over het registreren van apparaten.  
* Verbeterde opties voor probleemoplossing.  

#### <a name="web-apps-launched-from-the-windows-company-portal-app---5030972---"></a>Web-apps starten vanuit de Windows-bedrijfsportal-app<!-- 5030972 -->
Eindgebruikers kunnen web-apps nu direct vanuit de Windows-bedrijfsportal-app starten. Eindgebruikers kunnen de web-app selecteren en vervolgens de optie **In browser openen** kiezen. De gepubliceerde web-URL wordt rechtstreeks in een webbrowser geopend. Deze functionaliteit wordt de komende week doorgevoerd. Zie [Web-apps toevoegen aan Microsoft Intune](~/apps/web-app.md) voor meer informatie over het toevoegen van web-apps.  


#### <a name="new-assignment-type-column-in-company-portal-for-windows-10----5459950----"></a>Nieuwe kolom voor toewijzingstype in bedrijfsportal voor Windows 10 <!-- 5459950  -->
De naam van de kolom Bedrijfsportal > **Geïnstalleerde apps** > **Toewijzingstype** is gewijzigd in **Vereist door uw organisatie**.  Onder die kolom zien gebruikers de waarde **Ja** of **Nee** staan om aan te geven dat een app vereist is of optioneel is gemaakt door hun organisatie. Deze wijzigingen zijn aangebracht, omdat de apparaatgebruikers in de war raakten van het concept van beschikbare apps. Uw gebruikers kunnen meer informatie vinden over het installeren van apps via de bedrijfsportal in [Apps installeren en delen op uw apparaat](/intune-user-help/install-apps-cpapp-windows). Zie [De app Microsoft Intune-bedrijfsportal configureren](~/apps/company-portal-app.md) voor meer informatie over het configureren van de bedrijfsportal-app voor uw gebruikers.  

<!-- ########################## -->
## <a name="week-of-november-4-2019"></a>Week van 4 november 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Apparaatbeveiliging

#### <a name="security-baselines-are-supported-on-microsoft-azure-government---4062552---"></a>Beveiligingsbasislijnen worden ondersteund op Microsoft Azure Government<!-- 4062552 -->

In exemplaren van Intune die worden gehost op *Microsoft Azure Government* kunt u nu [beveiligingsbasislijnen](../protect/security-baselines.md) gebruiken om uw gebruikers en apparaten te beveiligen en beschermen.

## <a name="whats-new-archive"></a>Wat is er nieuw (archief)
Raadpleeg de sectie [Wat is er nieuw (archief)](whats-new-archive.md) voor eerdere maanden.

## <a name="notices"></a>Mededelingen

[!INCLUDE [Intune notices](../includes/intune-notices.md)]
