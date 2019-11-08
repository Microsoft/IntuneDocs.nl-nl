---
title: In ontwikkeling - Microsoft Intune
titleSuffix: ''
description: Microsoft Intune-functies in ontwikkeling
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/28/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.assetid: 25b3c26e-cf4e-4152-8306-bf4be4af2ad1
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3720b0b9a67f0c3462993feef4162ef35f7f3f92
ms.sourcegitcommit: d1b36501186e867355843ddd67c795ade800b76a
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/31/2019
ms.locfileid: "73182919"
---
# <a name="in-development-for-microsoft-intune---november-2019"></a>In ontwikkeling voor Microsoft Intune - november 2019

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

### <a name="smime-support-for-microsoft-outlook-mobile----2669398----"></a>S/MIME-ondersteuning voor micro soft Outlook Mobile <!-- 2669398  -->
InTune biedt ondersteuning voor het leveren van S/MIME-ondertekening en versleutelings certificaten die kunnen worden gebruikt met Outlook Mobile op iOS en Android. Zie [e-mail instellingen voor IOS-apparaten](~/configuration/email-settings-ios.md) en [e-mail instellingen voor Android-apparaten](~/configuration/email-settings-android.md)voor meer informatie.

### <a name="custom-settings-support-for-macos-applications----4736278----"></a>Ondersteuning van aangepaste instellingen voor macOS-toepassingen <!-- 4736278  -->
InTune ondersteunt aangepaste instellingen, zodat u specifieke sleutels en waarden kunt toevoegen aan een bestaand eigenschappen lijst bestand voor voor keuren (. plist) om macOS-apps en het apparaat te configureren. Niet alle apps ondersteunen beheerde voor keuren, en in sommige gevallen kunnen alleen specifieke instellingen worden beheerd. De instellingen worden alleen geïmplementeerd via het kanaal van het apparaat. U moet alleen eigenschappen lijst bestanden of XML-bestanden uploaden die de kanaal instellingen van het apparaat hebben.

### <a name="assignment-type-value-in-windows-company-portal----5459950----"></a>Waarde van toewijzings type in Windows Bedrijfsportal <!-- 5459950  -->
De pagina **geïnstalleerde apps** van de Windows bedrijfsportal-app wordt bijgewerkt. De kolom **toewijzings type** van de pagina **geïnstalleerde apps** is bijgewerkt met de naam ' vereist door uw organisatie '. Mogelijke waarden zijn **Ja** of **Nee** om de vereiste versus beschik bare apps aan te wijzen. Deze wijziging wordt aangebracht in reactie op de Verwar ring van de eind gebruiker. Meer informatie over de Windows-bedrijfsportal vindt u in [De app Microsoft Intune-bedrijfsportal configureren](~/apps/company-portal-app.md).

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

### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Inhoud van app-meldingen voor organisatie accounts configureren <!-- 2576686 -->
Met de intune-APP op Android-en iOS-apparaten kunt u app-meldings inhoud voor organisatie accounts beheren. Deze functie vereist ondersteuning van toepassingen en is mogelijk niet beschikbaar voor alle toepassingen waarvoor APP is ingeschakeld. Zie [Overzicht van App-beveiligingsbeleid](../apps/app-protection-policy.md) voor meer informatie over APP.


<!-- ***********************************************-->
## <a name="device-configuration"></a>Apparaatconfiguratie

### <a name="use-pkcs-certificates-with-wi-fi-profiles-on-windows-10-and-later-devices----3246388----"></a>PKCS-certificaten gebruiken met Wi-Fi-profielen op apparaten met Windows 10 en hoger <!-- 3246388  -->
Op dit moment kunt u Windows Wi-Fi-profielen verifiëren met SCEP-certificaten (**apparaatconfiguratie** > **profielen** > **profiel maken** > **Windows 10 en hoger** voor platform > **Wi-Fi** voor Profiel type > EAP- **type** > - **onderneming** ). U kunt PKCS-certificaten gebruiken met uw Windows Wi-Fi-profielen. Met deze functie kunnen gebruikers Wi-Fi-profielen verifiëren met behulp van nieuwe of bestaande PKCS-certificaat profielen in uw Tenant. 

Zie [Wi-Fi-instellingen voor Windows 10-en nieuwere apparaten toevoegen in intune](../configuration/wi-fi-settings-windows.md)voor meer informatie over Wi-Fi-profielen.

Van toepassing op:
- Windows 10 en hoger

### <a name="new-exchangeactivesync-settings-when-creating-an-email-device-configuration-profile-on-ios-devices----4892824----"></a>Nieuwe ExchangeActiveSync-instellingen bij het maken van een configuratie profiel voor een e-mail apparaat op iOS-apparaten <!-- 4892824  --> 
Op iOS/iPadOS-apparaten kunt u een e-mail verbinding configureren in een configuratie profiel voor een apparaat (**apparaatconfiguratie** > **profielen** > **profiel maken** > **IOS/IPadOS** voor platform > **-e-mail** voor het profiel type). 

Er worden nieuwe ExchangeActiveSync-instellingen beschikbaar, waaronder:
- Kies de services die u wilt synchroniseren (of blok keren synchronisatie), zoals e-mail, agenda en contact personen.
- Gebruikers toestaan om de synchronisatie-instellingen voor deze services op hun apparaten te wijzigen. 

Als u de huidige instellingen wilt zien, gaat u naar [e-mail Profiel instellingen voor IOS-apparaten in intune](../configuration/email-settings-ios.md).

Van toepassing op:
- iOS 13.0 en hoger
- iPadOS 13.0 en hoger

### <a name="prevent-users-from-adding-personal-google-accounts-to-android-enterprise-device-owner-and-dedicated-devices----5353228----"></a>Voor komen dat gebruikers persoonlijke Google-accounts toevoegen aan de eigenaar van het Android-apparaat en de toegewezen apparaten <!-- 5353228  -->
U kunt voor komen dat gebruikers persoonlijke Google-accounts maken op Android Enter prise Device-eigenaar en toegewezen apparaten (**apparaatconfiguratie** > **profielen** > **profiel maken** > **Android Enter prise** alleen voor platform > **apparaat-eigenaar > beperkingen van apparaten** voor profiel type > **gebruikers en account instellingen**).

Ga naar [Met Android Enterprise-apparaatinstellingen functies toestaan of beperken met behulp van Intune](../configuration/device-restrictions-android-for-work.md) als u alle instellingen wilt bekijken die u momenteel kunt configureren.

Van toepassing op:
- Android Enterprise-apparaateigenaar
- Toegewezen Android Enterprise-apparaten

### <a name="server-side-logging-for-siri-commands-setting-is-removed-in-ios-device-restrictions-profile----5468501----"></a>De instelling logboek registratie aan server zijde voor SIRI-opdrachten wordt verwijderd in profiel voor iOS-apparaten <!-- 5468501  -->
Op iOS-apparaten kunt u een profiel voor beperkingen voor apparaten maken waarmee logboek registratie aan de server zijde wordt geconfigureerd voor SIRI-opdrachten (**apparaatconfiguratie** > **profielen** > **maken** > **IOS/iPadOS** voor platform > **Beperkingen** voor het profiel type > **ingebouwde apps**). De instelling **logboek registratie aan server zijde voor SIRI-opdrachten** wordt verwijderd.

Deze instelling wordt verwijderd uit de intune-beheer console. Deze instelling heeft geen effect op het apparaat, zelfs als bestaande beleids regels waarvoor deze instelling is geconfigureerd, de instelling blijven weer geven. Als u de instelling uit bestaande beleids regels wilt verwijderen, gaat u naar het beleid, maakt u een kleine bewerking, slaat u deze op en wordt het beleid bijgewerkt.

Ga naar [iOS- en iPadOS-apparaatinstellingen om functies toe te staan of te beperken met Intune](../configuration/device-restrictions-ios.md) als u alle configureerbare instellingen wilt bekijken.

Van toepassing op:
- iOS


<!-- ***********************************************-->
<!--## Device enrollment-->

<!-- ***********************************************-->
## <a name="device-management"></a>Apparaatbeheer

### <a name="edit-device-name-value-for-autopilot-devices---2640074----"></a>Waarde voor apparaatnaam bewerken voor auto pilot-apparaten<!-- 2640074  -->
U kunt de waarde voor de apparaatnaam voor Azure AD gekoppelde auto pilot-apparaten bewerken. Als u dit wilt doen, gaat u naar **intune** > **apparaatregistratie** > **Windows-inschrijving** > **Windows auto pilot** > - **apparaten** > kiest u het apparaat > de waarde **apparaatnaam** in het rechterdeel venster te wijzigen > **Opslaan**.


### <a name="edit-the-group-tag-value-for-autopilot-devices---4816775---"></a>De groeps label waarde voor auto pilot-apparaten bewerken<!-- 4816775 -->
U kunt de **groeps label** waarde voor auto pilot-apparaten bewerken:

1. Selecteer **intune**  > **apparaatregistratie**  > **Windows-inschrijving**  > **Windows auto pilot**  > -**apparaten**.
1. Kies het apparaat.
1. Wijzig in het deel venster aan de rechter kant de waarde **groeps label** .
1. Selecteer **Opslaan**.

### <a name="target-macos-user-groups-to-require-jamf-management----4061739---"></a>MacOS-gebruikers groepen die Jamf-beheer vereisen <!-- 4061739 -->
U kunt specifieke groepen gebruikers bereiken om te vereisen dat hun macOS-apparaten worden beheerd door Jamf. Met dit doel kunt u de integratie van Jamf-naleving Toep assen op een subset van macOS-apparaten, terwijl andere apparaten door intune worden beheerd. Met doel items kunt u ook de apparaten van gebruikers geleidelijk van het ene Mobile Device Management (MDM)-systeem naar de andere migreren.

<!-- ***********************************************-->
## <a name="intune-apps"></a>Intune-apps

### <a name="improved-macos-enrollment-experience-in-company-portal----5074349----"></a>Verbeterde macOS-inschrijvings ervaring in Bedrijfsportal <!-- 5074349  -->
De Bedrijfsportal voor de registratie van macOS heeft een eenvoudig inschrijvings proces dat nauw keuriger wordt afgestemd op de Bedrijfsportal voor iOS-registratie. Gebruikers van het apparaat zien:  

* Een gestroomlijnde gebruikers interface.  
* Een verbeterde controle lijst voor de inschrijving.  
* Duidelijkere instructies over het inschrijven van hun apparaten.  
* Verbeterde opties voor probleem oplossing.  

### <a name="improved-checklist-design-in-company-portal-app-for-android---5550857----"></a>Verbeterd controlelijst ontwerp in Bedrijfsportal app voor Android<!-- 5550857  -->
De installatie controlelijst in de Bedrijfsportal-app voor Android wordt bijgewerkt met een licht gewicht ontwerp en nieuwe pictogrammen. De wijzigingen worden uitgelijnd met de recente updates die zijn aangebracht in de Bedrijfsportal-app voor iOS.

<!-- ***********************************************-->
## <a name="monitoring-and-troubleshooting"></a>Bewaking en probleem oplossing

### <a name="updated-support-experience-------5012398------"></a>Bijgewerkte ondersteunings ervaring   <!--  5012398    -->
Als onderdeel van de voortdurende verbeteringen wordt de ondersteunings ervaring in de console voor intune bijgewerkt.  We verbeteren de zoek opdracht in de console en feedback voor veelvoorkomende problemen en stroom lijnen de werk stroom om contact op te nemen met de ondersteuning.     

<!-- ***********************************************-->
## <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer

### <a name="duplicate-custom-or-built-in-roles----1081938---"></a>Dubbele aangepaste of ingebouwde rollen <!-- 1081938 -->
U kunt ingebouwde en aangepaste rollen kopiëren. Als u dit wilt doen, gaat u naar **intune** - > **rollen** > **alle rollen** > kies een rol in de lijst > **dupliceren**. Zorg ervoor dat u een nieuwe naam invoert die uniek is.

<!-- ***********************************************-->

## <a name="security"></a>Beveiliging

### <a name="bitlocker-key-rotation--------2564951--------"></a>BitLocker-sleutel rotatie     <!-- 2564951      -->
U kunt intune gebruiken voor het roteren van de BitLocker-herstel sleutels voor beheerde apparaten waarop Windows versie 1909 of hoger wordt uitgevoerd. 

<!-- ***********************************************-->
## <a name="notices"></a>Mededelingen

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Zie tevens
Voor meer informatie over recente ontwikkelingen raadpleegt u [Wat is er nieuw in Microsoft Intune?](whats-new.md).
