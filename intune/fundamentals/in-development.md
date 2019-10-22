---
title: In ontwikkeling - Microsoft Intune
titleSuffix: ''
description: Microsoft Intune-functies in ontwikkeling
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.assetid: 25b3c26e-cf4e-4152-8306-bf4be4af2ad1
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: ea5fae72f6e2057ef0b03a7bd295085ed1ac3bbd
ms.sourcegitcommit: 5807f4db4a45a093ce2fd6cb0c480bec384ec1ff
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/19/2019
ms.locfileid: "72601523"
---
# <a name="in-development-for-microsoft-intune---october-2019"></a>In ontwikkeling voor Microsoft Intune - oktober 2019

Als hulp bij uw gereedheid en planning worden op deze pagina updates voor en functies van de Intune-gebruikersinterface vermeld die in ontwikkeling zijn, maar nog niet zijn uitgebracht. Naast de informatie op deze pagina:

- Als we verwachten dat u actie moet ondernemen vóór een wijziging, publiceren we een aanvullend bericht in het Office-berichtencentrum.
- Wanneer een functie productie wordt ingevoerd, of het nu gaat om een preview-versie of algemeen beschikbaar is, wordt de beschrijving van de functie verplaatst van deze pagina naar [wat er nieuw](whats-new.md)is.
- Deze pagina en de pagina [Nieuwe functies](whats-new.md) worden regelmatig bijgewerkt. Controleer op andere updates.
- Raadpleeg de [Microsoft 365-roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) voor strategische producten en tijdlijnen.

> [!NOTE]
> Deze pagina weerspiegelt onze huidige verwachtingen over de mogelijkheden van intune in een toekomstige release. Datums en afzonderlijke functies kunnen worden gewijzigd. Op deze pagina worden niet alle functies in de ontwikkeling beschreven.

**RSS feed**: u ziet wanneer deze pagina wordt bijgewerkt door de volgende URL in uw feedlezer te kopiëren en plakken: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->

<!-- Common categories:  
## App management
## Device configuration
## Device enrollment
## Device management
## Intune apps
## Monitor and troubleshoot
## Role-based access control
## Security

-->
 
<!-- ***********************************************-->
## <a name="app-management"></a>Appbeheer

### <a name="apply-dark-mode-in-ios-company-portal----4911422----"></a>Donkere modus in iOS-Bedrijfsportal Toep assen <!-- 4911422  -->
De donkere modus is gepland voor iOS-Bedrijfsportal. U kunt bedrijfsapps downloaden, uw apparaten beheren en ondersteuning krijgen in het kleuren schema van uw keuze. Meer informatie over de iOS-bedrijfsportal vindt u in [De app Microsoft Intune-bedrijfsportal configureren](../apps/company-portal-app.md).

### <a name="run-win32-apps-on-windows-10-s-mode-devices----3747604----"></a>Win32-apps uitvoeren op Windows 10 S-modus apparaten <!-- 3747604  --> 
U kunt Win32-apps installeren en uitvoeren op apparaten die worden beheerd in de modus Windows 10 S. Maak een of meer aanvullende beleids regels voor de modus S door gebruik te maken van de Windows Defender Application Control (WDAC) Power shell-hulpprogram ma's. Gebruik de handtekening portal van Device Guard om het aanvullende beleid te ondertekenen. Upload en distribueer vervolgens het beleid via intune. 

In intune kunt u deze mogelijkheid vinden door client- **apps** te selecteren  > **Windows 10 S aanvullende beleids regels**. 

### <a name="set-app-availability-based-on-a-date-and-time----3510685----"></a>Beschik baarheid van apps instellen op basis van een datum en tijd <!-- 3510685  -->
Als beheerder kunt u de begin tijd en deadline voor een vereiste app configureren. Op het moment van de intune-beheer uitbreiding wordt de inhoud van de app gedownload en opgeslagen in de cache. De app wordt geïnstalleerd op het tijdstip van de deadline. Voor beschik bare apps wordt de begin tijd bepaald wanneer de app wordt weer gegeven in Bedrijfsportal. 

De beschik baarheid van apps instellen op basis van datum en tijd:

1. Selecteer in Intune **Client-apps** > **Apps**. 
1. Selecteer een app uit de lijst of Voeg een nieuwe toe door **toevoegen**te selecteren. 
1. Selecteer in de Blade app **toewijzingen** > **groep toevoegen**. 
1. Stel het **toewijzings type** in op **vereist** en selecteer vervolgens **opgenomen groepen**. 
1. Stel **deze app voor alle gebruikers** in op **Ja**. 
1. Selecteer **bewerken** om de opties voor de **eind gebruikers ervaring** te wijzigen. 
1. Stel op de Blade **eind gebruikers ervaring** de **software beschik bare tijd** in als nodig. 

Zie [Web-apps toevoegen aan Microsoft Intune](../apps/apps-add.md) voor meer informatie.

### <a name="require-win32-apps-to-restart----3136567----"></a>Vereisen dat Win32-apps opnieuw worden opgestart <!-- 3136567  -->
U kunt vereisen dat een Win32-app opnieuw wordt opgestart na een geslaagde installatie. U kunt de hoeveelheid tijd (de respijt periode) kiezen voordat de computer opnieuw wordt opgestart.

### <a name="display-notifications-for-the-company-portal-app-on-windows----1808082----"></a>Meldingen weer geven voor de Bedrijfsportal-app in Windows <!-- 1808082  -->
De Bedrijfsportal-app wordt bijgewerkt op Windows-apparaten om pop-upmeldingen voor gebruikers weer te geven, zelfs wanneer de toepassing wordt gesloten. In de update worden alleen meldingen voor beschik bare apps weer gegeven wanneer de installatie status is voltooid of mislukt. De Bedrijfsportal-app toont geen meldingen voor vereiste toepassingen.

### <a name="display-installation-status-messages-for-the-company-portal-app----2514416----"></a>Berichten over de installatie status voor de app Bedrijfsportal weer geven <!-- 2514416  -->
In de Bedrijfsportal-app worden aanvullende status berichten voor de app-installatie weer gegeven voor eind gebruikers. De volgende voor waarden zijn van toepassing op nieuwe Win32-afhankelijkheids functies:
- App installeren mislukt. Er is niet voldaan aan de afhankelijkheden die zijn gedefinieerd door de beheerder.
- De app is geïnstalleerd, maar moet opnieuw worden opgestart.
- De app wordt geïnstalleerd, maar moet opnieuw worden opgestart om verder te gaan.

### <a name="assign-the-microsoft-edge-beta-for-macos----4678761----"></a>De bèta versie van micro soft Edge voor macOS toewijzen <!-- 4678761  -->
U kunt de nieuwste versie van de micro soft Edge Beta toevoegen en toewijzen aan intune voor macOS-apparaten. 

De micro soft Edge Beta voor macOS-apparaten toewijzen:
1. Selecteer in intune **client-apps**  > **apps**  > **app toevoegen**  > **micro soft Edge-macOS**. 
1. Wijs de bèta versie van micro soft Edge toe aan de gewenste groepen. Micro soft auto update (MAU) houdt micro soft Edge up-to-date. 
 
Zie voor meer informatie over micro soft Edge [webtoegang beheren met behulp van micro soft Edge met Microsoft intune](../apps/manage-microsoft-edge.md).

### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Inhoud van app-meldingen voor organisatie accounts configureren <!-- 2576686 -->
Met de intune-APP op Android-en iOS-apparaten kunt u app-meldings inhoud voor organisatie accounts beheren. Deze functie vereist ondersteuning van toepassingen en is mogelijk niet beschikbaar voor alle toepassingen waarvoor APP is ingeschakeld. Zie [Overzicht van App-beveiligingsbeleid](../apps/app-protection-policy.md) voor meer informatie over APP.


<!-- ***********************************************-->
## <a name="device-configuration"></a>Apparaatconfiguratie

### <a name="new-device-firmware-configuration-interface-profile-for-devices-that-run-windows-10-and-later----2266073----"></a>Nieuw firmware configuratie interface profiel voor apparaten met Windows 10 en hoger <!-- 2266073  -->
In Windows 10 en hoger kunt u een configuratie profiel voor een apparaat maken om instellingen en functies te beheren: 

1. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
1. Voor het platform selecteert u **Windows 10 en hoger**. 
 
Met een nieuw profiel voor de firmware configuratie interface van een apparaat kan intune UEFI-instellingen (BIOS) beheren.

Zie voor meer informatie over de huidige instellingen die u kunt configureren [onderdelen en instellingen op uw apparaten Toep assen met behulp van apparaatprofielen in Microsoft intune](../configuration/device-profiles.md).

Deze functie is van toepassing op Windows 10 RS5 (1809) en hoger, op apparaten selecteren.
 

<!-- ***********************************************-->
## <a name="device-enrollment"></a>Apparaatinschrijving

### <a name="for-ios-devices-customize-the-enrollment-privacy-window-of-company-portal----4394993----"></a>Voor iOS-apparaten past u het venster voor inschrijvings-privacy van Bedrijfsportal <!-- 4394993  -->
Met behulp van markdown kunt u het privacyvenster van de bedrijfsportal aanpassen dat eindgebruikers te zien krijgen tijdens de iOS-registratie. U kunt met name de lijst aanpassen met zaken die uw organisatie niet op het apparaat kan zien of doen.

<!-- ***********************************************-->
## <a name="device-management"></a>Apparaatbeheer


### <a name="edit-the-group-tag-value-for-autopilot-devices---4816775---"></a>De groeps label waarde voor auto pilot-apparaten bewerken<!-- 4816775 -->
U kunt de **groeps label** waarde voor auto pilot-apparaten bewerken:

1. Selecteer **intune**  > **apparaatregistratie**  > **Windows-inschrijving**  > **Windows auto pilot**  > -**apparaten**.
1. Kies het apparaat.
1. Wijzig in het deel venster aan de rechter kant de waarde **groeps label** .
1. Selecteer **Opslaan**.

### <a name="target-macos-user-groups-to-require-jamf-management----4061739---"></a>MacOS-gebruikers groepen die Jamf-beheer vereisen <!-- 4061739 -->
U kunt specifieke groepen gebruikers bereiken om te vereisen dat hun macOS-apparaten worden beheerd door Jamf. Met dit doel kunt u de integratie van Jamf-naleving Toep assen op een subset van macOS-apparaten, terwijl andere apparaten door intune worden beheerd. Met doel items kunt u ook de apparaten van gebruikers geleidelijk van het ene Mobile Device Management (MDM)-systeem naar de andere migreren.

### <a name="deploy-software-updates-to-macos-devices----3194876---"></a>Software-updates implementeren op macOS-apparaten <!-- 3194876 -->
U kunt software-updates implementeren op groepen macOS-apparaten. Deze functie omvat essentiële, firmware, configuratie bestand en andere updates. U kunt updates verzenden tijdens het volgende inchecken van het apparaat. U kunt ook een wekelijks schema selecteren om updates in of uit Peri Oden te implementeren die u hebt ingesteld. 

Deze functie helpt u bij het bijwerken van apparaten buiten de standaardwerk uren of buiten kantoor uren wanneer uw Help Desk volledig is gewerkt. U krijgt ook een gedetailleerd rapport van alle macOS-apparaten waarop updates zijn geïmplementeerd. U kunt inzoomen op het rapport op apparaat om de status van een bepaalde update weer te geven.

<!-- ***********************************************-->
## <a name="monitoring-and-troubleshooting"></a>Bewaking en probleem oplossing

### <a name="android-report-on-the-devices-overview-page----2984353----"></a>Android-rapport op de pagina overzicht van apparaten <!-- 2984353  -->
We gaan een nieuw rapport toevoegen aan de **overzichts** pagina met apparaten. In het rapport wordt weer gegeven hoeveel Android-apparaten zijn geregistreerd bij elke oplossing voor Apparaatbeheer. In de grafiek worden de aantallen apparaten weer gegeven voor het werk profiel, volledig beheerd, toegewezen en apparaat-Administrator die zijn Inge schreven. 

Als u het rapport wilt zien, kiest u **intune** > **apparaten** > **Overview**.

### <a name="updated-support-experience-------5012398------"></a>Bijgewerkte ondersteunings ervaring   <!--  5012398    -->
Als onderdeel van de voortdurende verbeteringen wordt de ondersteunings ervaring in de console voor intune bijgewerkt.  We verbeteren de zoek opdracht in de console en feedback voor veelvoorkomende problemen en stroom lijnen de werk stroom om contact op te nemen met de ondersteuning.     

<!-- ***********************************************-->
<!--## Security-->


<!-- ***********************************************-->
## <a name="notices"></a>Mededelingen

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Zie tevens
Voor meer informatie over recente ontwikkelingen raadpleegt u [Wat is er nieuw in Microsoft Intune?](whats-new.md).
