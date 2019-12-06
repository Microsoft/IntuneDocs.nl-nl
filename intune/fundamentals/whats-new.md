---
title: Nieuwe functies in Microsoft Intune - Azure | Microsoft Docs
titleSuffix: ''
description: Ontdekken wat er nieuw is in Intune Azure Portal
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/22/2019
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
ms.openlocfilehash: 7ad5c26770537ce6a285989f8ca3804277616419
ms.sourcegitcommit: 16a9109b4028589c17695d41271ca4fee8b1d697
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/26/2019
ms.locfileid: "74540791"
---
# <a name="whats-new-in-microsoft-intune"></a>Wat is er nieuw in Microsoft Intune?

Ontdek elke week wat er nieuw is in Microsoft Intune. U vindt hier ook [belangrijke kennisgevingen](#notices), [oudere releases](whats-new-archive.md) en informatie over [hoe service-updates voor Intune worden uitgebracht](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728).

> [!Note]
> Het kan voor elke [maandelijkse update](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728) tot drie dagen duren totdat deze wordt geïmplementeerd. Dit gebeurt in de volgende volgorde:
>
> - Dag 1: Azië en Stille Oceaan (APAC)
> - Dag 2: Europa, Midden-Oosten en Afrika (EMEA)
> - Dag 3: Noord-Amerika
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
## <a name="week-of-november-18-2019-1911-service-release"></a>Week van 18 november 2019 (1911 servicerelease)

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Appbeheer

#### <a name="smime-support-with-microsoft-outlook-for-ios---2669398-idready---"></a>S/MIME-ondersteuning met Microsoft Outlook voor iOS<!-- 2669398 idready -->
Intune biedt ondersteuning voor het leveren van S/MIME-ondertekening- en versleutelingscertificaten die kunnen worden gebruikt met Outlook voor iOS op iOS-apparaten. Zie [S/MIME configureren voor Outlook voor iOS](~/apps/app-configuration-policies-outlook-smime.md) voor meer informatie.

#### <a name="ui-update-when-selectively-wiping-app-data---4102028---"></a>Update van gebruikersinterface bij selectief wissen van app-gegevens<!-- 4102028 -->
De gebruikersinterface voor het selectief wissen van app-gegevens in Intune is bijgewerkt. De gebruikersinterface wordt onder andere op deze punten gewijzigd:
- Een vereenvoudigde ervaring in de vorm van een wizard, beknopt weergegeven binnen één deelvenster.
- Een update van de maakstroom om toewijzingen toe te voegen.
- Een samenvattingspagina van alle items die zijn ingesteld bij het weergeven van eigenschappen, vóór het maken van een nieuw beleid of bij het bewerken van een eigenschap. Tijdens het bewerken van eigenschappen toont de samenvatting ook alleen een lijst met items in de categorie met eigenschappen die wordt bewerkt.

Zie [Alleen zakelijke gegevens wissen uit door Intune beheerde apps](~/apps/apps-selective-wipe.md) voor meer informatie.

#### <a name="ios-and-ipados-third-party-keyboard-support---4922950---"></a>Toetsenbordondersteuning voor iOS en iPadOS van derden<!-- 4922950 -->
In maart 2019 is het verwijderen aangekondigd van ondersteuning voor de instelling voor iOS-beleid voor appbeveiliging Toetsenborden van derden. De functie keert in Intune terug met ondersteuning voor iOS en iPadOS. U kunt deze instelling inschakelen via het tabblad **Gegevensbescherming** van een nieuw of bestaand iOS-/iPadOS-beleid voor appbeveiliging. Zoek de instelling **Toetsenborden van derden** onder **Gegevensoverdracht**.

Het gedrag van deze beleidsinstelling wijkt enigszins af van de vorige implementatie. In apps met meerdere identiteiten met SDK-versie 12.0.16 en hoger, gericht op beleid voor appbeveiliging waarbij deze instelling is ingesteld op **Blokkeren**, kunnen eindgebruikers voor hun organisatie- en persoonlijke accounts geen toetsenborden van derden kiezen. Apps met SDK-versies 12.0.12 en eerder blijven het gedrag vertonen dat is vastgelegd in de titel van de blogpost, [Bekend probleem: toetsenborden van derden worden in iOS niet geblokkeerd voor persoonlijke accounts](https://aka.ms/3rdparty_iOS_Intune).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="target-macos-user-groups-to-require-jamf-management---4061739----"></a>Richten op macOS-gebruikersgroepen waarvoor Jamf-beheer is vereist<!-- 4061739  --> 
U kunt zich op specifieke groepen gebruikers richten die hun [macOS-apparaten laten beheren door Jamf](../protect/conditional-access-integrate-jamf.md). Hierdoor kunt u de nalevingsintegratie van Jamf toepassen op een subset van macOS-apparaten, terwijl andere apparaten door Intune worden beheerd. Als u de Jamf-integratie al gebruikt, zijn alle gebruikers standaard bedoeld voor de integratie.

#### <a name="new-exchange-activesync-settings-when-creating-an-email-device-configuration-profile-on-ios-devices---4892824-----"></a>Nieuwe Exchange ActiveSync-instellingen bij het maken van een configuratieprofiel voor een e-mailapparaat op iOS-apparaten<!-- 4892824   --> 
U kunt op iOS/iPadOS-apparaten e-mailconnectiviteit configureren in een apparaatconfiguratieprofiel (**Apparaatconfiguratie** > **Profielen** > **Profiel maken**  > **iOS/iPadOS** als platform > **E-mail** als profieltype). 

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

#### <a name="improved-macos-enrollment-experience-in-company-portal----5074349-wnready---"></a>Verbeterde macOS-registratie in bedrijfsportal <!-- 5074349 WNready -->  
De bedrijfsportal voor macOS-registratie heeft een eenvoudiger registratieproces dat nauwkeuriger is afgestemd met de bedrijfsportal voor iOS-registratie. Apparaatgebruikers zien nu het volgende:  

* Een gestroomlijndere gebruikers interface.  
* Een verbeterde controlelijst voor registratie.  
* Duidelijkere instructies over het registreren van apparaten.  
* Verbeterde opties voor probleemoplossing.  

#### <a name="web-apps-launched-from-the-windows-company-portal-app---5030972---"></a>Web-apps starten vanuit de Windows-bedrijfsportal-app<!-- 5030972 -->
Eindgebruikers kunnen web-apps nu direct vanuit de Windows-bedrijfsportal-app starten. Eindgebruikers kunnen de web-app selecteren en vervolgens de optie **In browser openen** kiezen. De gepubliceerde web-URL wordt rechtstreeks in een webbrowser geopend. Deze functionaliteit wordt de komende week doorgevoerd. Zie [Web-apps toevoegen aan Microsoft Intune](~/apps/web-app.md) voor meer informatie over het toevoegen van web-apps.  


#### <a name="new-assignment-type-column-in-company-portal-for-windows-10----5459950-wnready---"></a>Nieuwe kolom voor toewijzingstype in bedrijfsportal voor Windows 10 <!-- 5459950 WNready -->
De naam van de kolom Bedrijfsportal > **Geïnstalleerde apps** > **Toewijzingstype** is gewijzigd in **Vereist door uw organisatie**.  Onder die kolom zien gebruikers de waarde **Ja** of **Nee** staan om aan te geven dat een app vereist is of optioneel is gemaakt door hun organisatie. Deze wijzigingen zijn aangebracht, omdat de apparaatgebruikers in de war raakten van het concept van beschikbare apps. Uw gebruikers kunnen meer informatie vinden over het installeren van apps via de bedrijfsportal in [Apps installeren en delen op uw apparaat](/intune-user-help/install-apps-cpapp-windows). Zie [De app Microsoft Intune-bedrijfsportal configureren](~/apps/company-portal-app.md) voor meer informatie over het configureren van de bedrijfsportal-app voor uw gebruikers.  

<!-- ########################## -->
## <a name="week-of-november-4-2019"></a>Week van 4 november 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Apparaatbeveiliging

#### <a name="security-baselines-are-supported-on-microsoft-azure-government---4062552---"></a>Beveiligingsbasislijnen worden ondersteund op Microsoft Azure Government<!-- 4062552 -->

In exemplaren van Intune die worden gehost op *Microsoft Azure Government* kunt u nu [beveiligingsbasislijnen](../protect/security-baselines.md) gebruiken om uw gebruikers en apparaten te beveiligen en beschermen.

<!-- ########################## -->
## <a name="week-of-october-28-2019"></a>Week van 28 oktober 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Appbeheer

#### <a name="improved-checklist-design-in-company-portal-app-for-android---5550857---"></a>Verbeterd ontwerp van de controlelijst in de bedrijfsportal-app voor Android<!-- 5550857 -->  
De setup-controlelijst in de Bedrijfsportal-app voor Android is bijgewerkt met een lichtgewicht ontwerp en nieuwe pictogrammen. De veranderingen zijn in lijn met de recente updates voor de Bedrijfsportal-app voor iOS. In [Wat is er nieuw in de gebruikersinterface van de app ](whats-new-app-ui.md) kunt u de oude en nieuwe versie naast elkaar zien. Zie [Inschrijven met Android-werkprofiel](/intune-user-help/enroll-device-android-work-profile) en [Uw Android-apparaat inschrijven](/intune-user-help/enroll-device-android-company-portal) voor een overzicht van de bijgewerkte inschrijvingsstappen.  

#### <a name="win32-apps-on-windows-10-s-mode-devices---3747604---"></a>Win32-apps op Windows 10 S-modusapparaten<!-- 3747604 --> 
U kunt Win32-apps installeren en uitvoeren op beheerde apparaten met Windows 10 S-modus. Hiervoor kunt u een of meer aanvullende beleidsregels maken voor de Windows S-modus met behulp van de PowerShell-hulpprogramma's van Windows Defender Application Control (WDAC). Onderteken het aanvullende beleid met de Device Guard Signing-ondertekeningsportal en upload en distribueer het beleid vervolgens via Intune. In Intune vindt u deze mogelijkheid door **Client-apps** > **Aanvullend beleid voor Windows 10 S** te selecteren. Zie [Win32-apps inschakelen op S-modusapparaten](~/apps/apps-win32-s-mode.md) voor meer informatie.

#### <a name="set-win32-app-availability-based-on-a-date-and-time---3510685---"></a>De beschikbaarheid van Win32-apps instellen op basis van een datum en tijd<!-- 3510685 -->
Als beheerder kunt u de begintijd en deadline voor een vereiste Win32-app configureren. Bij de begintijd start de Intune-beheerextensie het downloaden van de app-inhoud en slaat deze op in de cache. De app wordt geïnstalleerd op het tijdstip van de deadline. Voor beschikbare apps bepaalt de begintijd wanneer de app zichtbaar is in Bedrijfsportal. Zie [Intune Win32 app-beheer](~/apps/apps-win32-app-management.md#set-win32-app-availability-and-notifications) voor meer informatie.

#### <a name="require-device-restart-based-on-grace-period-after-win32-app-install---3136567---"></a>Opnieuw opstarten van apparaat verplicht stellen op basis van een respijtperiode na het installeren van Win32-apps<!-- 3136567 -->
U kunt eisen dat een apparaat opnieuw moet worden opgestart nadat een Win32-app is geïnstalleerd. Zie [Win32-app-beheer - app-installatiegegevens configureren](~/apps/apps-win32-app-management.md#step-4-configure-app-installation-details)voor meer informatie.

#### <a name="dark-mode-for-ios-company-portal---4911422---"></a>Donkere modus voor iOS-bedrijfsportal<!-- 4911422 -->
Donkere modus is beschikbaar voor de iOS-bedrijfsportal. Gebruikers kunnen bedrijfsapps downloaden, hun apparaten beheren en IT-ondersteuning krijgen in het gewenste kleurenschema op basis van hun apparaatinstellingen. De iOS-bedrijfsportal wordt automatisch afgestemd op de apparaatinstellingen van de eindgebruiker voor donkere of lichte modus. Zie [Introductie van donkere modus op Microsoft Intune-bedrijfsportal voor iOS](https://techcommunity.microsoft.com/t5/Enterprise-Mobility-Security/Introducing-dark-mode-on-Microsoft-Intune-Company-Portal-for-iOS/ba-p/918453) voor meer informatie. Meer informatie over de iOS-bedrijfsportal vindt u in [De app Microsoft Intune-bedrijfsportal configureren](~/apps/company-portal-app.md).

#### <a name="android-company-portal-enforced-minimum-app-version---2378776---"></a>Afgedwongen minimale app-versie voor Android-bedrijfsportal<!-- 2378776 -->
Met behulp van de instelling **Minimale versie bedrijfsportal** van een app-beveiligingsbeleid kunt u een minimale versie van de bedrijfsportal opgeven die wordt afgedwongen op het apparaat van de eindgebruiker. Met deze instelling voor voorwaardelijk starten kunt u **Toegang blokkeren**, **Gegevens wissen** or **Waarschuwen** als mogelijke acties wanneer niet aan een waarde wordt voldaan. De mogelijke notaties voor deze waarde volgen het patroon *[major].[minor]* , *[major].[minor].[build]* , of *[major].[minor].[build].[revision]* .

Indien de instelling **Minimale versie bedrijfsportal** is geconfigureerd, beïnvloedt deze elke eindgebruiker die versie 5.0.4560.0 en toekomstige versies van de bedrijfsportal ontvangt. Deze instelling heeft geen invloed op gebruikers die gebruikmaken van een versie van bedrijfsportal die ouder is dan de versie waarop deze functie wordt uitgebracht. Eindgebruikers die automatische app-updates op hun apparaat gebruiken, krijgen waarschijnlijk geen dialoogvensters van deze functie te zien, aangezien ze waarschijnlijk de nieuwste versie van de bedrijfsportal hebben. Deze instelling is alleen voor Android met app-beveiliging voor ingeschreven en niet-ingeschreven apparaten. Zie [Instellingen app-beveiligingsbeleid voor Android - Voorwaardelijk starten](~/apps/app-protection-policy-settings-android.md#conditional-launch) voor meer informatie.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->

### <a name="microsoft-365-device-management"></a>Microsoft 365 Device Management

#### <a name="introducing-endpoint-security-node-in-microsoft-365-device-management---5630102---"></a>Introductie van Endpoint Security-knooppunt in Microsoft 365 Device Management<!-- 5630102 -->

Een **Endpoint Security**-knooppunt is nu algemeen beschikbaar in de gespecialiseerde werkruimte van Microsoft 365 Device Management op https://devicemanagement.microsoft.com, waar de mogelijkheden voor het beveiligen van eindpunten zijn samengebracht, zoals:

- Beveiligingsbasislijnen:  Vooraf geconfigureerde groep instellingen die u helpen bij het toepassen van bekende groepen instellingen en standaardwaarden die door Microsoft worden aanbevolen.

- Beveiligingstaken: Profiteer van het Threat and Vulnerability Management (TVM) van Microsoft Defender ATP en gebruik Intune om zwakke punten in eindpunten te herstellen.

- Microsoft Defender ATP: Geïntegreerde Microsoft Defender Advanced Threat Protection (ATP) om beveiligingsschendingen te voorkomen.

Deze instellingen blijven toegankelijk via andere toepasselijke knooppunten (zoals apparaten) en de huidige geconfigureerde status blijft hetzelfde, ongeacht waar u deze mogelijkheden opent en inschakelt.

Voor meer informatie over deze verbeteringen, zie de [Blogpost voor Intune-klantsucces ](https://aka.ms/Endpoint_security_node) op de Microsoft Tech Community-website.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Apparaatbeheer

#### <a name="intune-supports-ios-11-and-later---4665324----"></a>Intune ondersteunt iOS 11 en hoger<!-- 4665324  -->

De Intune-inschrijving en bedrijfsportal ondersteunen nu iOS versie 11 en hoger. Oudere versies worden niet ondersteund.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Apparaatbeveiliging

#### <a name="microsoft-edge-baseline-preview----3787164----"></a>Microsoft Edge-basislijn (Preview)<!--  3787164  -->

We hebben een beveiligingsbasislijn-preview toegevoegd voor [Microsoft Edge-instellingen](../protect/security-baseline-settings-edge.md). 

<!-- ########################## -->
## <a name="week-of-october-21-2019-1910-service-release"></a>Week van 21 oktober 2019 (1910 servicerelease)

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="microsoft-365-device-management"></a>Microsoft 365 Device Management

#### <a name="improved-administration-experience-in-microsoft-365-device-management---5551239---"></a>Verbeterde beheerervaring in Microsoft 365 Device Management<!-- 5551239 -->

Een vernieuwde en gestroomlijnde beheerervaring is nu algemeen beschikbaar in de gespecialiseerde werkruimte van Microsoft 365 Device Management op [https://devicemanagement.microsoft.com](https://devicemanagement.microsoft.com), met daarin:

- **Bijgewerkte navigatie**: U profiteert van een vereenvoudigde navigatie op het eerste niveau die functies op logische wijze groepeert.
- **Nieuwe platformfilters**: Op de pagina's voor apparaten en apps kunt u één platform selecteren dat alleen het beleid en de apps voor het geselecteerde platform toont.
- **Nieuwe startpagina**: Een snel overzicht van de servicestatus, tenantstatus, nieuws enz. op de nieuwe homepage.

Voor meer informatie over deze verbeteringen, zie de [Blogpost voor Enterprise Mobility + Security](https://go.microsoft.com/fwlink/?linkid=2109094) op de Microsoft Tech Community-website.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Appbeheer

#### <a name="add-mobile-threat-defense-apps-to-unenrolled-devices---3005337---"></a>Mobile Threat Defense-apps toevoegen aan niet-ingeschreven apparaten<!-- 3005337 -->
U kunt een app-beschermingsbeleid voor Intune maken dat de bedrijfsgegevens van gebruikers kan blokkeren of selectief kan wissen op basis van de status van een apparaat. De status van het apparaat wordt bepaald met behulp van de geselecteerde Mobile Threat Defense-oplossing (MTD). Deze mogelijkheid bestaat voor Intune-ingeschreven apparaten nu als een nalevingsinstelling voor apparaten. Met deze nieuwe functie breiden we de dreigingsdetectie uit van een Mobile Threat Defense-leverancier naar niet-ingeschreven apparaten. Op Android vereist deze functie de nieuwste versie van de bedrijfsportal op het apparaat. Op iOS is deze functie beschikbaar voor gebruik wanneer apps de nieuwste Intune-SDK (v 12.0.15+) integreren. We zullen het onderwerp 'Wat is er nieuw' bijwerken wanneer de eerste app de nieuwste Intune-SDK heeft. De overige apps zullen doorlopend beschikbaar komen. Zie [App-beveiligingsbeleid voor Mobile Threat Defense maken met Intune](~/protect/mtd-app-protection-policy.md).

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="new-device-firmware-configuration-interface-profile-for-windows-10-and-later-devices-public-preview---2266073----"></a>Nieuw configuratie-interfaceprofiel voor apparaatfirmware voor Windows 10 en hoger (openbare preview)<!-- 2266073  -->

In Windows 10 en hoger kunt u een configuratieprofiel voor een apparaat maken om instellingen en functies te beheren (**Configuratie van apparaten** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** voor platform). In deze update is er een nieuw profieltype voor de configuratie-interface voor apparaatfirmware waarmee Intune UEFI-instellingen (BIOS) kan beheren.

Zie [DFCI-profielen gebruiken op Windows-apparaten in Microsoft Intune](../configuration/device-firmware-configuration-interface-windows.md) voor meer informatie over deze functie.

Van toepassing op:
- Windows 10 RS5 (1809) en nieuwer op ondersteunde firmware

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="toggle-to-only-show-enrollment-status-page-on-devices-provisioned-by-out-of-box-experience-oobe--3959566--"></a>Wisselknop om alleen de pagina voor inschrijvingsstatus weer te geven op apparaten die zijn ingericht door out-of-box experience (OOBE)<!--3959566-->
U kunt er nu voor kiezen om alleen de pagina voor inschrijvingsstatus weer te geven op apparaten die zijn ingericht door Autopilot OOBE.

Om de nieuwe wisselknop weer te geven, kiest u **Intune** > **Apparaatinschrijving** > **Windows-inschrijving** > **Pagina met inschrijvingsstatus** > **Profiel maken** > **Instellingen** > **Alleen pagina's weergeven aan apparaten die zijn ingericht door out-of-box experience (OOBE)** .


<!-- ########################## -->
## <a name="week-of-october-14-2019"></a>Week van 14 oktober 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Appbeheer 

#### <a name="available-google-play-app-reporting-for-android-work-profiles---3041956-----"></a>Beschikbare rapportage over Google Play-apps voor Android-werkprofielen<!-- 3041956   -->
U kunt voor beschikbare app-installaties op toegewezen en volledig beheerde apparaten met Android Enterprise-werkprofielen de status van de app-installatie evenals de geïnstalleerde versie van beheerde Google Play-apps bekijken. Zie [How to monitor app protection policies](~/apps/app-protection-policies-monitor.md) (App-beveiligingsbeleid controleren), [Manage Android work profile devices with Intune](~/enrollment/android-enterprise-overview.md) (Apparaten met Android-werkprofielen beheren met Intune) en [Managed Google Play app type](~/apps/apps-add-android-for-work.md#managed-google-play-app-types) (Type beheerde Google Play-app) voor meer informatie.

#### <a name="microsoft-edge-version-77-and-later-for-windows-10-and-macos-public-preview---3872025-4678761----"></a>Microsoft Edge versie 77 en later voor Windows 10 en macOS (openbare preview)<!-- 3872025, 4678761  -->
Microsoft Edge versie 77 en hoger wordt beschikbaar voor implementatie op pc's met Windows 10 en macOS. 

De openbare preview biedt **Dev**- en **Bèta**-kanalen voor Windows 10 en een **Bèta**-kanaal voor macOS. De implementatie is alleen in het Engels (EN) beschikbaar, maar eindgebruikers kunnen de weergavetaal wijzigen in de browser via **Instellingen** > **Talen**. Microsoft Edge is een Win32-app die wordt geïnstalleerd in systeemcontext en in soortgelijke architecturen (x86-app in een x86-besturingssysteem en x64-app in een x64-besturingssysteem). Automatische updates van de browser is bovendien standaard **Ingeschakeld** en Microsoft Edge kan niet worden verwijderd. Zie [Microsoft Edge voor Windows 10 toevoegen aan Microsoft Intune](~/apps/apps-windows-edge.md) en [Documentatie bij Microsoft Edge](https://go.microsoft.com/fwlink/?linkid=2103823) voor meer informatie.

#### <a name="update-to-app-protection-ui-and-ios-app-provisioning-ui---4102027-4102029-----"></a>Update van de gebruikersinterface voor app-beveiliging en de gebruikersinterface voor inrichting van iOS-apps<!-- 4102027, 4102029   -->
De gebruikersinterface om app-beveiligingsbeleid en inrichtingsprofielen voor iOS-apps in Intune te maken en bewerken, is bijgewerkt. De gebruikersinterface wordt onder andere op deze punten gewijzigd:
- Een vereenvoudigde ervaring in de vorm van een wizard, beknopt weergegeven binnen één blade. 
- Een update van de maakstroom om toewijzingen toe te voegen.
- Een samenvattingspagina van alle items die zijn ingesteld bij het weergeven van eigenschappen, vóór het maken van een nieuw beleid of bij het bewerken van een eigenschap. Tijdens het bewerken van eigenschappen toont de samenvatting ook alleen een lijst met items in de categorie met eigenschappen die wordt bewerkt.

Zie [App-beveiligingsbeleid maken en toewijzen](~/apps/app-protection-policies.md) en [Inrichtingsprofielen voor iOS-apps gebruiken ](~/apps/app-provisioning-profile-ios.md)voor meer informatie.

#### <a name="intune-guided-scenarios---4850318-4831296-3610611----"></a>Begeleide scenario's voor Intune<!-- 4850318, 4831296, 3610611  -->
Intune biedt nu begeleide scenario's die u helpen bij het voltooien van een specifieke taak of een set taken in Intune. Een begeleid scenario is een aangepaste reeks stappen (werkstroom) die zijn gecentreerd rond een end-to-end-use-case. Algemene scenario's worden gedefinieerd op basis van de rol die een beheerder, gebruiker of apparaat in uw organisatie speelt. Deze werkstromen vereisen doorgaans een verzameling zorgvuldig gegroepeerde profielen, instellingen, toepassingen en beveiligingsmechanismen om de beste gebruikerservaring en beveiliging te kunnen bieden. Nieuwe begeleide scenario's zijn onder meer:
- [Microsoft Edge voor mobiel implementeren](~/fundamentals/guided-scenarios-edge.md)
- [Veilige mobiele apps voor Microsoft Office](~/fundamentals/guided-scenarios-office-mobile.md) 
- [Modern bureaublad met cloudbeheer](~/fundamentals/guided-scenarios-cloud-managed-pc.md)

Zie [Overzicht van begeleide scenario's voor Intune](guided-scenarios-overview.md) voor meer informatie.

#### <a name="additional-app-configuration-variable-available---4969237-----"></a>Extra variabele voor app-configuratie beschikbaar<!-- 4969237   -->
Wanneer u een app-configuratiebeleid maakt, kunt u de configuratievariabele `AAD Device ID` opnemen als onderdeel van de configuratie-instellingen. Selecteer in Intune **Client-apps** > **App-configuratiebeleid** > **Toevoegen**. Voer de gegevens van uw configuratiebeleid in en selecteer **Configuratie-instellingen** om de blade **Configuratie-instellingen** weer te geven. Zie voor meer informatie [App-configuratiebeleid voor beheerde Android Enterprise-apparaten: de configuratie-ontwerper gebruiken](~/apps/app-configuration-policies-use-android.md#use-the-configuration-designer).


#### <a name="create-groups-of-management-objects-called-policy-sets---3762880----"></a>Groepen beheerobjecten, zogenaamde beleidssets, maken<!-- 3762880  -->
Met beleidssets kunt u een bundel met verwijzingen maken naar reeds bestaande beheerentiteiten die moeten worden geïdentificeerd, waarop moet worden gericht en die moet worden bewaakt als één conceptuele eenheid. Met beleidssets worden geen bestaande concepten of objecten vervangen. U kunt afzonderlijke objecten blijven toewijzen in Intune en u kunt verwijzen naar afzonderlijke objecten als onderdeel van een beleidsset. Daarom worden wijzigingen aan deze afzonderlijke objecten weergegeven in de beleidsset.  In Intune selecteert u **Beleidssets** > **Maken** om een nieuwe beleidsset te maken. 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="ui-update-for-creating-and-editing-windows-10-update-rings---4099089-----------"></a>Update van de gebruikersinterface voor het maken en bewerken van Windows 10-update-ringen<!-- 4099089         -->
De gebruikersinterface-ervaring voor [het maken en bewerken van Windows 10-update-ringen](../protect/windows-update-for-business-configure.md#create-and-assign-update-rings) voor Intune is bijgewerkt. Wijzigingen in de gebruikersinterface zijn onder andere:  
- Een indeling in de vorm van een wizard, beknopt weergegeven op één blade van de console waardoor de wildgroei aan blades komt te vervallen wanneer u update-ringen configureert.   
- De gewijzigde werkstroom bevat Toewijzingen, voordat de initiële configuratie van de ring wordt voltooid.
- Een overzichtspagina die u kunt gebruiken om alle configuraties te bekijken die u hebt gemaakt, voordat u een nieuwe update-ring opslaat en implementeert. Tijdens het bewerken van een update-ring toont de samenvatting alleen de lijst met items die zijn ingesteld binnen de categorie met eigenschappen die u hebt bewerkt.

#### <a name="ui-update-for-creating-and-editing-ios-software-update-policy---4099090---------"></a>Update van de gebruikersinterface voor het maken en bewerken van beleid voor iOS-software-updates<!-- 4099090       --> 
De gebruikersinterface-ervaring voor het [maken](../protect/software-updates-ios.md#configure-the-policy) en [ bewerken](../protect/software-updates-ios.md#edit-a-policy) van iOS-software-updatebeleid voor Intune is bijgewerkt.  Wijzigingen in de gebruikersinterface zijn onder andere:  
- Een indeling in de vorm van een wizard, beknopt weergegeven op één blade van de console waardoor de wildgroei aan blades komt te vervallen bij het configureren van updatebeleid.   
- De gewijzigde werkstroom bevat Toewijzingen, voordat de initiële configuratie van het beleid wordt voltooid.
- Een overzichtspagina die u kunt gebruiken om alle configuraties te bekijken die u hebt gemaakt, voordat u een nieuw beleid opslaat en implementeert. Tijdens het bewerken van een beleid, toont het overzicht alleen de lijst met items die zijn ingesteld binnen de categorie met eigenschappen die u hebt bewerkt.

#### <a name="engaged-restart-settings-are-removed-from-windows-update-rings----4464404---wnready-----"></a>Instellingen voor gepland opnieuw opstarten zijn verwijderd uit Windows-update-ringen<!--  4464404   WNReady   -->
Zoals eerder aangekondigd, ondersteunen Windows 10-update-ringen van Intune nu [instellingen voor deadlines](../protect/windows-update-settings.md) en wordt *Gepland opnieuw opstarten* niet meer ondersteund. Instellingen voor *Gepland opnieuw opstarten* zijn niet meer beschikbaar wanneer u update-ringen in Intune configureert of beheert.  

Deze wijziging ligt op één lijn met [wijzigingen in Windows-service](https://docs.microsoft.com//windows/whats-new/whats-new-windows-10-version-1903#servicing). Verder vervangen op apparaten met Windows 10 1903 of hoger *deadlines* configuraties voor *gepland opnieuw opstarten*.

#### <a name="prevent-installation-of-apps-from-unknown-sources-on-android-enterprise-work-profile-devices---4760025-----"></a>Installatie van apps van onbekende bronnen op apparaten met een Android Enterprise-werkprofiel voorkomen<!-- 4760025   -->
Op apparaten met een Android Enterprise-werkprofiel kunnen gebruikers nooit apps van onbekende bronnen installeren. In deze update is er een nieuwe instelling, namelijk **App-installaties van onbekende bronnen in het persoonlijke profiel voorkomen**. Met deze instelling wordt standaard voorkomen dat gebruikers apps van onbekende bronnen extern kunnen laden in het persoonlijke profiel op het apparaat.

Ga naar [Met Android Enterprise-apparaatinstellingen functies toestaan of beperken met behulp van Intune](../configuration/device-restrictions-android-for-work.md) als u de configureerbare instelling wilt bekijken.

Van toepassing op:
- Android Enterprise - Werkprofiel

#### <a name="create-a-global-http-proxy-on-android-enterprise-device-owner-devices---4816339-----"></a>Een algemene HTTP-proxy maken op Android Enterprise-apparaten met een apparaateigenaar<!-- 4816339   -->
Op Android Enterprise-apparaten kunt u een globale HTTP-proxy configureren om te voldoen aan de standaarden voor webbrowsen van uw organisatie (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** voor platform > **Apparaateigenaar > Apparaatbeperkingen** voor profieltype > **Connectiviteit**). Zodra dit is geconfigureerd, gebruikt al het HTTP-verkeer deze proxy.

Ga naar [Met Android Enterprise-apparaatinstellingen functies toestaan of beperken met behulp van Intune](../configuration/device-restrictions-android-for-work.md) als u deze functie wilt configureren en alle configureerbare instellingen wilt bekijken.

Van toepassing op:
- Android Enterprise-apparaateigenaar

#### <a name="connect-automatically-setting-is-removed-in-wi-fi-profiles-on-android-device-administrator-and-android-enterprise---5021055-----"></a>De instelling automatisch verbinding maken is verwijderd uit Wi-Fi-profielen op Android-apparaatbeheerder en Android Enterprise<!-- 5021055   -->
Op Android-apparaatbeheerder en Android Enterprise-apparaten kunt u een Wi-Fi-profiel maken om verschillende instellingen te configureren (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android-apparaatbeheerder** of **Android Enterprise** voor platform > **Wi-Fi-** voor profieltype). In deze update is de instelling **Automatisch verbinding maken** verwijderd, omdat deze [niet door Android wordt ondersteund](https://developer.android.com/reference/android/net/wifi/WifiManager.html#enableNetwork%28int%2c%20boolean%29). 

Als u deze instelling in een Wi-Fi-profiel gebruikt, hebt u mogelijk opgemerkt dat **Automatisch verbinding maken** niet werkt. U hoeft geen actie te ondernemen, maar houd er rekening mee dat deze instelling wordt verwijderd uit de Intune-gebruikersinterface.

Raadpleeg [Wi-Fi-instellingen van Android](../configuration/wi-fi-settings-android.md) of [Wi-Fi-instellingen van Android Enterprise](../configuration/wi-fi-settings-android-enterprise.md).

Van toepassing op:
- Android-apparaatbeheerder 
- Android Enterprise


#### <a name="new-device-configuration-settings-for-supervised-ios-and-ipados-devices---5199328-----"></a>Nieuwe instellingen voor apparaatconfiguratie voor iOS- en iPadOS-apparaten onder supervisie<!-- 5199328   -->
Op iOS- en iPadOS-apparaten kunt u een profiel maken om functies en instellingen op apparaten te beperken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS/iPadOS** voor platform > **Apparaatbeperkingen** voor profieltype). Deze update bevat nieuwe instellingen die u kunt beheren: 
- Toegang tot netwerkstation in Bestanden-app  
- Toegang tot USB-station in Bestanden-app 
- Wi-Fi altijd ingeschakeld 

Als u deze instellingen wilt bekijken, gaat u naar [iOS-apparaatinstellingen voor het toestaan of beperken van functies met behulp van Intune](../configuration/device-restrictions-ios.md).

Van toepassing op:
- iOS 13.0 en hoger
- iPadOS 13.0 en hoger

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="specify-which-android-device-operating-system-versions-enroll-with-work-profile-or-device-administrator-enrollment---4350697-----"></a>Opgeven welke besturingssysteemversies van Android-apparaten registreren met werkprofiel of apparaatbeheerderinschrijving<!-- 4350697   -->
Met behulp van de Intune-beperkingen voor apparaattypen kunt u de besturingssysteemversie van het apparaat gebruiken om op te geven welke gebruikersapparaten de Android Enterprise-werkprofiel-inschrijving of Android-apparaatbeheerderinschrijving gebruiken.  Zie [Inschrijvingsbeperkingen instellen](../enrollment/enrollment-restrictions-set.md) voor meer informatie.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Apparaatbeheer

#### <a name="new-restrictions-for-renaming-windows-devices---3478938----"></a>Nieuwe beperkingen voor het wijzigen van de naam van Windows-apparaten<!-- 3478938  -->
Wanneer u de naam van een Windows-apparaat wijzigt, moet u nieuwe regels volgen:
- Maximaal 15 tekens (moet kleiner zijn dan of gelijk zijn aan 63 bytes, exclusief navolgende null-tekens)
- Niet null of een lege tekenreeks
- Toegestane ASCII: Letters (a-z, A-Z), cijfers (0-9) en afbreekstreepjes
- Toegestane Unicode: tekens > = 0x80, moet geldige UTF8 zijn, moet IDN-toewijsbaar zijn (dat wil zeggen dat RtlIdnToNameprepUnicode moet slagen, zie RFC 3492)
- Namen mogen niet alleen cijfers bevatten
- Namen mogen geen spaties bevatten
- Niet-toegestane tekens: { | } ~ [ \ ] ^ ' : ; < = > ? & @ ! " # $ % ` ( ) + / , . _ *)

 Zie [De naam van een apparaat wijzigen in Intune](../remote-actions/device-rename.md) voor meer informatie.

### <a name="new-android-report-on-devices-overview-page---4924364---"></a>Nieuw Android-rapport op de overzichtspagina Apparaten<!-- 4924364 -->
In een nieuw rapport op de overzichtspagina Apparaten wordt weergegeven hoeveel Android-apparaten zijn geregistreerd in elke oplossing voor apparaatbeheer. In dit diagram ziet u het aantal apparaten met werkprofiel, volledig beheerd, toegewezen en door de beheerder geregistreerd. Als u het rapport wilt zien, kiest u **Intune** > **Apparaten** > **Overzicht**.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Apparaatbeveiliging

#### <a name="pkcs-certificates-for-macos---1333650---------"></a>PKCS-certificaten voor macOS<!-- 1333650       -->
U kunt nu [PKCS-certificaten gebruiken met macOS](../protect/certficates-pfx-configure.md#create-a-pkcs-certificate-profile). U kunt het PKCS-certificaat selecteren als profieltype voor macOS en certificaten voor gebruikers en apparaten implementeren die [velden voor aangepaste naam voor het onderwerp en alternatieve onderwerpnaam](../protect/certficates-pfx-configure.md#subject-name-format-for-macos) bevatten.  

PKCS-certificaat voor macOS biedt ook ondersteuning voor een nieuwe instelling, _Alle apps toegang toestaan_. Met deze instelling kunt u alle gekoppelde apps toegang geven tot de persoonlijke sleutel van het certificaat.  Raadpleeg de Apple-documentatie op https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf voor meer informatie over deze instelling.

####   <a name="derived-credentials-to-provision-ios-mobile-devices-with-certificates----1736036-1736037-1772050-2777333-----------"></a>Afgeleide referenties voor het inrichten van mobiele iOS-apparaten met certificaten<!--  1736036, 1736037, 1772050, 2777333         -->  
Intune ondersteunt het gebruik van [afgeleide referenties](../protect/derived-credentials.md) als een verificatiemethode en voor S/MIME-ondertekening en versleuteling voor iOS-apparaten. Afgeleide referenties zijn een implementatie van de *National Institute of Standards and Technology (NIST) 800-157* -standaard voor het implementeren van certificaten op apparaten.  

Afgeleide referenties zijn afhankelijk van het gebruik van een Personal Identity Verification (PIV) of Common Access Card (CAC), zoals een smartcard. Om een afgeleide referentie voor hun mobiele apparaat te verkrijgen, beginnen gebruikers in de app Bedrijfsportal en volgen ze een registratiewerkstroom die uniek is voor de provider die u gebruikt.  Alle providers hebben met elkaar gemeen dat ze vereisen dat een smartcard voor verificatie bij de afgeleide referentieprovider. Deze provider verzendt vervolgens een certificaat naar het apparaat dat is afgeleid van de smartcard van de gebruiker.  

Intune biedt ondersteuning voor de volgende afgeleide referentieproviders:
- DISA Purebred
- Entrust Datacard
- Intercede

U gebruikt afgeleide referenties als verificatiemethode voor configuratieprofielen voor apparaten voor VPN, Wi-Fi en e-mailberichten. U kunt ze ook gebruiken voor app-verificatie en S/MIME-ondertekening en -versleuteling.  

Raadpleeg [Afgeleide PIV-referenties](https://www.nccoe.nist.gov/projects/building-blocks/piv-credentials) op www.nccoe.nist.gov voor meer informatie over de standaard.

#### <a name="use-graph-api-to-specify-a-on-premises-user-principal-name-as-a-variable-for-scep-certificates----5437939----------"></a>Graph API gebruiken om een on-premises user principal name op te geven als een variabele voor SCEP-certificaten<!--  5437939        -->  
Wanneer u de [Intune Graph API](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0)gebruikt, kunt u onPremisesUserPrincipalName opgeven als een variabele voor de alternatieve naam voor het onderwerp (SAN) voor SCEP-certificaten.



<!-- ########################## -->

## <a name="week-of-september-23-2019"></a>Week van 23 september 2019

#### <a name="ios-user-enrollment-in-preview---4817900---"></a>Inschrijving van iOS-gebruikers in Preview<!-- 4817900 -->
De iOS 13.1-release van Apple bevat Gebruikersinschrijving, een nieuwe vorm van Lightweight Management voor iOS-apparaten. Deze functie kan worden gebruikt in plaats van Apparaatinschrijving of Automatische apparaatinschrijving (voorheen Device Enrollment Program) voor apparaten die persoonlijk eigendom zijn. De Preview-versie van Intune ondersteunt deze functieset zodat u het volgende kunt doen:

- Gebruikersinschrijving richten op gebruikersgroepen.
- Eindgebruikers de mogelijkheid geven om te kiezen tussen het lichtere Gebruikersregistratie of het sterkere Apparaatinschrijving bij het inschrijven van hun apparaten.

Vanaf 24 september 2019, met de release van iOS 13.1, worden deze updates geïmplementeerd voor alle klanten. We verwachten dat dit proces eind volgende week is voltooid.
Van toepassing op:

iOS 13.1 en hoger

#### <a name="intune-support-for-ipados-and-ios-131-devices--5439574--"></a>Intune-ondersteuning voor iPadOS- en iOS 13.1-apparaten<!--5439574-->
Intune biedt nu ondersteuning voor iPadOS- en iOS 13.1-apparaten. Lees [dit blogbericht](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Support-for-iOS-13-1-and-iPadOS/ba-p/873094) voor meer informatie.

<!-- ########################## -->

## <a name="week-of-september-16-2019-1909-service-release"></a>Week van 16 september 2019 (1909 servicerelease)

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Appbeheer 

#### <a name="managed-google-play-private-lob-apps---1464182----"></a>Privé-LOB-apps uit de beheerde Google Play Store<!-- 1464182  -->
In Intune is nu toegestaan dat IT-beheerders privé-LOB-apps van Android publiceren in de beheerde Google Play Store, via een iFrame ingesloten in de Intune-console.  Voorheen moesten IT-beheerders LOB-apps rechtstreeks publiceren in de publicatieconsole van de Google Play Store. Hiervoor zijn verschillende stappen nodig en het is tijdrovend. Met deze nieuwe functie kunnen LOB-apps eenvoudig worden gepubliceerd met een minimaal aantal stappen, zonder de Intune-console te verlaten.  Beheerders hoeven zich niet meer handmatig als een ontwikkelaar te registreren bij Google, en ze hoeven de registratiekosten van $ 25 niet te betalen.  Elk van deze scenario’s voor Android Enterprise-beheer waarin de beheerde Google Play Store wordt gebruikt, kunnen profiteren van deze functie (werkprofiel, toegewezen, volledig beheerd, en niet-ingeschreven apparaten). Vanuit Intune selecteert u **Client-apps** > **Apps** > **Toevoegen**. Selecteer vervolgens **Beheerde Google Play** in de lijst met **App-typen**. Zie [Beheerde Google Play-apps toevoegen aan Android Enterprise-apparaten met Intune](../apps/apps-add-android-for-work.md) voor meer informatie over beheerde Google Play-apps.

#### <a name="windows-company-portal-experience---1473353-3598357---"></a>Versie van de Windows-bedrijfsportal-app<!-- 1473353, 3598357 -->
De Windows-bedrijfsportal wordt bijgewerkt. U kunt meerdere filters gebruiken op de apps-pagina in de Windows-bedrijfsportal. De pagina met apparaatdetails is ook bijgewerkt met een verbeterde gebruikerservaring. Deze updates worden momenteel geïmplementeerd voor alle klanten. We verwachten dat dit proces eind volgende week is voltooid.

#### <a name="macos-support-for-web-apps---3174427---"></a>macOS-ondersteuning voor web-apps<!-- 3174427 -->
Web-apps, waarmee u een snelkoppeling naar een URL op het web kunt toevoegen, kunnen in de Dock worden geïnstalleerd met behulp van de bedrijfsportal voor macOS. Eindgebruikers hebben toegang tot de actie **Installeren** op de pagina met app-details voor een web-app in de macOS-bedrijfsportal. Zie [Apps toevoegen aan Microsoft Intune](../apps/apps-add.md) en [Web-apps toevoegen aan Microsoft Intune](../apps/web-app.md) voor meer informatie over het app-type **Webkoppeling**.

#### <a name="macos-support-for-vpp-apps---3173501----"></a>macOS-ondersteuning voor VPP-apps<!-- 3173501  -->
macOS-apps, gekocht met Apple Business Manager, worden in de console weergegeven wanneer Apple VPP-tokens worden gesynchroniseerd in Intune. Met de Intune-console kunt u op apparaten en gebruikers gebaseerde licenties voor groepen toewijzen, intrekken en opnieuw toewijzen. Microsoft Intune maakt het makkelijker om VPP-apps te beheren die voor gebruik in uw bedrijf zijn gekocht door:

- Licentiegegevens rapporteren vanuit de App Store.
- Bijhouden hoeveel van de licenties u hebt gebruikt.
- U te helpen voorkomen dat er meer exemplaren van de app worden geïnstalleerd dan waarvan u eigenaar bent.

Voor meer informatie over Intune en VPP raadpleegt u [Apps en boeken met Microsoft Intune beheren die via het Volume Purchase Program zijn gekocht](../apps/vpp-apps.md).

#### <a name="managed-google-play-iframe-support---2871756----"></a>Ondersteuning voor de beheerde Google Play-iFrame<!-- 2871756  -->
Intune biedt nu ondersteuning voor het rechtstreeks toevoegen en beheren van webkoppelingen in de Intune-console via de beheerde Google Play-iFrame.  Hiermee kunnen IT-beheerders een URL en pictogramafbeelding verzenden, en deze koppelingen vervolgens implementeren op apparaten, zoals gewone Android-apps. Elk van deze scenario’s voor Android Enterprise-beheer waarin de beheerde Google Play Store wordt gebruikt, kunnen profiteren van deze functie (werkprofiel, toegewezen, volledig beheerd, en niet-ingeschreven apparaten). Vanuit Intune selecteert u **Client-apps** > **Apps** > **Toevoegen**. Selecteer vervolgens **Beheerde Google Play** in de lijst met **App-typen**. Zie [Beheerde Google Play-apps toevoegen aan Android Enterprise-apparaten met Intune](../apps/apps-add-android-for-work.md) voor meer informatie over beheerde Google Play-apps.

#### <a name="silently-install-android-lob-apps-on-zebra-devices---4252734----"></a>LOB-apps van Android op de achtergrond installeren op Zebra-apparaten<!-- 4252734  -->
Wanneer u LOB-apps (Line-of-Business) van Android installeert op [Zebra-apparaten](../configuration/android-zebra-mx-overview.md), kunt u de app op de achtergrond installeren, in plaats van dat u wordt gevraagd om de LOB-app zowel te downloaden als te installeren. Selecteer in Intune de optie **Client-apps** > **Apps** > **Toevoegen**. Selecteer in het deelvenster **App toevoegen** de optie **Line-Of-Business-app**. Zie [Een Android Line-Of-Business-app toevoegen aan Microsoft Intune](../apps/lob-apps-android.md) voor meer informatie.

Momenteel wordt, nadat de LOB-app is gedownload, een melding over het **slagen van de download** weergegeven op het apparaat van de gebruiker. U kunt deze melding alleen negeren door in de schaduw van de melding te tikken op **Alles wissen**. Dit meldingsprobleem wordt opgelost in een toekomstige release, en de installatie vindt volledig op de achtergrond plaats, zonder dat dit zichtbaar is.

#### <a name="read-and-write-graph-api-operations-for-intune-apps---5031704----"></a>Graph API-bewerkingen voor Intune-apps lezen en schrijven<!-- 5031704  -->
De Intune Graph API kan via lees- en schrijfbewerkingen worden aangeroepen voor toepassingen, met behulp van de app-id zonder gebruikersreferenties. Zie [Working with Intune in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0) (Werken met intune in Microsoft Graph) voor meer informatie over het openen van de Microsoft Graph API voor Intune.

#### <a name="protected-data-sharing-and-encryption-for-intune-app-sdk-for-ios---3586942----"></a>Het delen en versleutelen van beveiligde gegevens voor Intune App SDK voor iOS<!-- 3586942  -->
De Intune App-SDK voor iOS gebruikt 256-bits versleutelingssleutels wanneer versleuteling is ingeschakeld door app-beveiligingsbeleid. Alle apps moeten eerst over een SDK-versie 8.1.1 beschikken, als u het delen van beveiligde gegevens wilt toestaan.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="support-for-ikev2-vpn-profiles-for-ios---1943438-----"></a>Ondersteuning voor IKEv2 VPN-profielen voor iOS<!-- 1943438   -->
In deze update kunt u met het IKEv2-protocol VPN-profielen maken voor de systeemeigen VPN-client van iOS. IKEv2 is een nieuw verbindingstype in **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **VPN** voor profieltype > **Verbindingstype**.

Met deze VPN-profielen wordt de systeemeigen VPN-client geconfigureerd. Er worden dus geen VPN-client-apps geïnstalleerd of gepusht naar beheerde apparaten. Deze functie vereist dat apparaten zijn ingeschreven bij Intune (MDM-inschrijving).

Als u wilt zien welke VPN-instellingen u momenteel kunt configureren, gaat u naar [VPN-instellingen configureren op iOS-apparaten](../configuration/vpn-settings-ios.md).

Van toepassing op:
- iOS

#### <a name="device-features-device-restrictions-and-extension-profiles-for-ios-and-macos-settings-are-shown-by-enrollment-type---4886161-----"></a>Apparaatfuncties, apparaatbeperkingen, en extensieprofielen voor iOS- en macOS-instellingen worden weergegeven op inschrijvingstype<!-- 4886161   -->

In Intune maakt u profielen voor iOS- en macOS-apparaten (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** of **macOS** voor platform > **Apparaatfuncties**, **Apparaatbeperkingen**, of **Extensies** voor profieltype). 

In deze update zijn de beschikbare instellingen in de Intune-portal gecategoriseerd op basis van het inschrijvingstype waarop ze zijn toegepast:

- iOS
  - Gebruikersinschrijving
  - Apparaatinschrijving
  - Automatische apparaatinschrijving (onder toezicht)
  - Alle inschrijvingstypen

- macOS
  - Goedgekeurd door de gebruiker
  - Apparaatinschrijving
  - Automatische apparaatinschrijving
  - Alle inschrijvingstypen

Van toepassing op:
- iOS

#### <a name="new-voice-control-settings-for-supervised-ios-devices-running-in-kiosk-mode---4892835-----"></a>Nieuwe instellingen voor spraakbeheer voor iOS-apparaten onder supervisie die worden uitgevoerd in de kioskmodus<!-- 4892835   -->
In Intune kunt u beleid maken om iOS-apparaten onder supervisie uit te voeren als een kiosk of toegewezen apparaat (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype > **Kiosk**).

Deze update bevat nieuwe instellingen die u kunt beheren:
- **Spraakbeheer**: Hiermee wordt Spraakbeheer ingeschakeld op het apparaat, wanneer het apparaat in de kioskmodus is.
- **Aanpassing van spraakbeheer**: Gebruikers toestaan de instelling voor spraakbeheer te wijzigen op het apparaat, wanneer het apparaat in de kioskmodus is.

Als u de huidige instellingen wilt zien, gaat u naar de [iOS Kiosk-instellingen](../configuration/device-restrictions-ios.md#kiosk).

Van toepassing op:
- iOS 13.0 en hoger

#### <a name="use-single-sign-on-for-apps-and-websites-on-your-ios-and-macos-devices---4893175-----"></a>Eenmalige aanmelding gebruiken voor apps en websites op iOS- en macOS-apparaten<!-- 4893175   -->
Deze update bevat enkele nieuwe instellingen voor eenmalige aanmelding voor iOS- en macOS-apparaten (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** of **macOS** voor platform > **Apparaatfuncties**, voor profieltype).

Gebruik deze instellingen om eenmalige aanmelding te configureren, speciaal bedoeld voor apps en websites die gebruikmaken van Kerberos-verificatie. U kunt kiezen tussen een algemene app-extensie voor referenties met eenmalige aanmelding, en de ingebouwde Kerberos-extensie van Apple.

Als u wilt zien welke huidige apparaatfuncties u kunt configureren, gaat u naar [iOS-apparaatfuncties](../configuration/ios-device-features-settings.md) en [macOS-apparaatfuncties](../configuration/macos-device-features-settings.md).

Van toepassing op:
- iOS 13.0 en hoger
- macOS 10.15 of hoger

#### <a name="associate-domains-to-apps-on-macos-1015-devices---4898079-----"></a>Domeinen koppelen aan apps op macOS 10.15-apparaten en hoger<!-- 4898079   -->
Op macOS-apparaten kunt u verschillende functies configureren en deze functies naar uw apparaten pushen met behulp van beleid (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **macOS** voor platform > **Apparaatfuncties** voor profieltype). In deze update kunt u domeinen koppelen aan uw apps. Deze functie helpt bij het delen van referenties op websites die verband houden met uw app, en kan worden gebruikt met de extensie voor eenmalige aanmelding, universele koppelingen, en automatisch invullen van wachtwoorden van Apple. 

Ga naar [Instellingen van macOS-apparaatfuncties in Intune](../configuration/macos-device-features-settings.md) om te zien welke huidige functies u kunt configureren.

Van toepassing op:
- macOS 10.15 of hoger

#### <a name="use-itunes-and-apps-in-the-itunes-app-store-url-when-showing-or-hiding-apps-on-ios-supervised-devices---4928474-----"></a>Gebruik 'iTunes' en 'apps' in de iTunes App Store-URL bij het weergeven of verbergen van apps op iOS-apparaten onder supervisie<!-- 4928474   --> 
In Intune kunt u beleid maken om apps weer te geven of te verbergen op iOS-apparaten onder supervisie (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype > **Apps weergeven of verbergen**). 

U kunt de iTunes App Store-URL invoeren, zoals `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`. In deze update kan zowel `apps` als `itunes` worden gebruikt in de URL, zoals:
- `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`
- `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`

Zie [Apps weergeven of verbergen](../configuration/device-restrictions-ios.md#show-or-hide-apps) voor meer informatie over deze instellingen.

Van toepassing op:
- iOS

#### <a name="windows-10-compliance-policy-password-type-values-are-clearer-and-match-csp---5138985---"></a>Waarden voor het wachtwoordtype voor Windows 10-nalevingsbeleid zijn duidelijker en komen niet overeen met CSP<!-- 5138985 -->
Op Windows 10-apparaten kunt u nalevingsbeleid maken waarvoor specifieke wachtwoordfuncties zijn vereist (**Apparaatcompatibiliteit** > **beleid** > **Beleid maken** > **Windows 10 en later** voor platform > **Systeembeveiliging**). In deze update:
- De waarden voor **Wachtwoordtype** zijn duidelijker, en zijn bijgewerkt om overeen te komen met de [DeviceLock/AlphanumericDevicePasswordRequired CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-alphanumericdevicepasswordrequired).
- De instelling **Wachtwoordverlooptijd (dagen)** is bijgewerkt om waarden toe te staan van minimaal 1 en maximaal 730 dagen. 

Zie [Instellingen voor Windows 10 en later om apparaten te markeren als compatibel of niet-compatibel](../protect/compliance-policy-create-windows.md) voor meer informatie over instellingen voor Windows 10-naleving. 

Van toepassing op:
- Windows 10 en hoger

 #### <a name="updated-ui-for-configuring-microsoft-exchange-on-premises-access---4092920---"></a>Bijgewerkte gebruikersinterface voor het configureren van on-premises toegang tot Microsoft Exchange<!-- 4092920 -->  
De console is bijgewerkt, zodat u [on-premises toegang tot Microsoft Exchange kunt configureren](../protect/conditional-access-exchange-create.md). Alle configuraties voor on-premises toegang tot Exchange zijn nu beschikbaar in hetzelfde deelvenster van de console waar u *Beheer voor on-premises toegang tot Exchange kunt inschakelen*.  

#### <a name="allow-or-restrict-adding-app-widgets-to-the-home-screen-on-android-enterprise-work-profile-devices---1109650----"></a>Het toevoegen van app-widgets aan het startscherm in apparaten met Android Enterprise-werkprofielen toestaan of beperken<!-- 1109650  --> 
Op Android Enterprise-apparaten kunt u functies in het werkprofiel configureren (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** voor platform > **Alleen werkprofiel > Apparaatbeperkingen** voor profieltype). In deze update kunt u gebruikers toestaan om widgets die worden weergegeven in werkprofiel-apps, toe te voegen aan het startscherm van het apparaat.

Ga naar [Met Android Enterprise-apparaatinstellingen functies toestaan of beperken met behulp van Intune](../configuration/device-restrictions-android-for-work.md) als u alle configureerbare instellingen wilt bekijken.

Van toepassing op:
- Android Enterprise - Werkprofiel

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="new-tenants-will-default-away-from-android-device-administrator-management---4869790-----"></a>Nieuwe tenants worden standaard verwijderd uit het beheer van Android-apparaatbeheerders<!-- 4869790   -->
De beheermogelijkheden voor Android-apparaten zijn vervangen door Android Enterprise. Daarom raden we u aan om vanaf nu Android Enterprise te gebruiken voor nieuwe inschrijvingen. Bij een toekomstige update moeten de volgende vereiste stappen voor Android-inschrijving worden uitgevoerd voor nieuwe tenants, om beheer van apparaatbeheerders te gebruiken: Ga naar **Intune** > **Apparaatinschrijving** > **Android-inschrijving** > **Persoonlijke apparaten en apparaten in bedrijfseigendom met bevoegdheden voor het beheren van apparaten** > **Apparaatbeheer gebruiken om apparaten te beheren**.

De omgevingen van bestaande tenants worden niet gewijzigd.

Zie [Inschrijving van Android-apparaatbeheerders](https://docs.microsoft.com/intune/android-enroll-device-administrator) voor meer informatie over Android-apparaatbeheerders in Intune.

#### <a name="list-of-dep-devices-associated-with-a-profile---5012045-idmiss---"></a>Lijst met DEP-apparaten die zijn gekoppeld aan een profiel<!-- 5012045 idmiss -->
U kunt nu een lijst met pagina’s bekijken met geautomatiseerde DEP-apparaten van Apple (Device Enrollment Program) die zijn gekoppeld aan een profiel. U kunt in de lijst zoeken vanaf elke pagina in de lijst. Als u deze lijst wilt bekijken, gaat u naar **Intune** > **Apparaatinschrijving** > **Apple-inschrijving** > **Tokens voor het inschrijvingsprogramma** > kies een token > **Profielen** > kies een profiel > **Toegewezen apparaten** (onder**Monitor**).

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Apparaatbeheer

#### <a name="more-android-fully-managed-support---3464667-4631425-4631440-5227935-4062195-----"></a>Meer ondersteuning voor volledig beheerde Android-apparaten<!-- 3464667, 4631425, 4631440, 5227935, 4062195   -->
We hebben de volgende ondersteuning toegevoegd voor volledig beheerde Android-apparaten:

- SCEP-certificaten voor volledig beheerde Android-apparaten zijn beschikbaar voor certificaatverificatie op apparaten die worden beheerd als Apparaateigenaar. SCEP-certificaten worden al ondersteund op Werkprofiel-apparaten.  Met SCEP-certificaten voor Apparaateigenaar kunt u het volgende doen: <!-- 5227935 -->
    - SCEP-profiel maken onder de DO-sectie van Android Enterprise
    - SCEP-certificaten koppelen aan een DO-Wi-Fi-profiel voor verificatie
    - SCEP-certificaten koppelen aan DO-VPN-profielen voor verificatie
    - SCEP-certificaten koppelen aan DO-e-mailprofielen voor verificatie (via AppConfig)
- Systeem-apps worden ondersteund op Android Enterprise-apparaten. Voeg in Intune een Android Enterprise-systeem-app toe door **Client-apps** > **Apps** > **Toevoegen** te selecteren. Selecteer in de lijst **App-type** het type **Android Enterprise-systeem-app**. Zie [Android Enterprise-systeem-apps toevoegen aan Microsoft Intune](../apps/apps-ae-system.md) voor meer informatie. <!-- 4062195 -->
- In **Apparaatcompatibiliteit** > **Android Enterprise** > **Apparaateigenaar**, kunt u nalevingsbeleid maken waarmee het niveau van SafetyNet-attestation wordt ingesteld.   <!-- 4631425 -->
- Op volledig beheerde Android Enterprise-apparaten worden de Mobile Threat Defense-providers ondersteund. In **Apparaatcompatibiliteit** > **Android Enterprise** > **Apparaateigenaar**, kunt u een acceptabel bedreigingsniveau kiezen. <!-- 4631440 --> In [Android Enterprise-instellingen om te markeren of apparaten wel of niet conform zijn met behulp van Intune](../protect/compliance-policy-create-android-for-work.md#device-owner) worden de huidige instellingen vermeld.
- De Microsoft Launcher-app kan nu op volledig beheerde Android Enterprise-apparaten worden geconfigureerd via app-configuratiebeleid, voor een gestandaardiseerde eindgebruikerservaring op volledig beheerde apparaten. De Microsoft Launcher-app kan worden gebruikt om uw Android-apparaat te personaliseren. Door de app te gebruiken samen met een Microsoft-account of werk/school-account hebt u toegang tot uw agenda, documenten en recente activiteiten in uw gepersonaliseerde feed. <!-- 5334044 -->

We zijn blij te kunnen aankondigen dat met deze update Intune-ondersteuning voor volledig beheerde Android Enterprise-apparaten nu algemeen beschikbaar is.

Van toepassing op:

- Volledig beheerde Android Enterprise-apparaten

#### <a name="send-custom-notifications-to-a-single-device---4928910---"></a>Aangepaste meldingen verzenden naar één apparaat<!-- 4928910 -->
U kunt nu één apparaat selecteren en vervolgens een externe apparaatactie gebruiken om [een aangepaste melding te verzenden naar alleen dit specifieke apparaat](../remote-actions/custom-notifications.md#send-a-custom-notification-to-a-single-device).

#### <a name="wipe-and-passcode-reset-actions-arent-available-for-ios-devices-that-are-enrolled-by-using-user-enrollment---4950491---"></a>Acties voor wissen en het opnieuw instellen van wachtwoordcode zijn niet beschikbaar voor iOS-apparaten die zijn ingeschreven met behulp van gebruikersinschrijving<!-- 4950491 -->
Gebruikersinschrijving is een nieuw type inschrijving voor Apple-apparaten. Wanneer u apparaten inschrijft met behulp van gebruikersinschrijving, zijn de externe acties voor wissen en het opnieuw instellen van wachtwoordcode niet beschikbaar voor dergelijke apparaten.

#### <a name="intune-support-for-ios-13-and-macos-catalina-devices---4665317---"></a>Intune-ondersteuning voor iOS 13- en macOS Catalina-apparaten<!-- 4665317 -->
Intune biedt nu ondersteuning voor iOS 13- en macOS Catalina-apparaten.
Zie de [blogpost Microsoft Intune-ondersteuning voor iOS 13 en iPadOS](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Support-for-iOS-13-and-iPadOS/ba-p/861998) voor meer informatie.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Apparaatbeveiliging

#### <a name="bitlocker-support-for-client-driven-recovery-password-rotation----3444125---"></a>BitLocker-ondersteuning voor clientgestuurde rotatie van herstelwachtwoorden<!--  3444125 -->
Gebruik Intune Endpoint Protection om [Clientgestuurde rotatie van herstelwachtwoorden](../protect/endpoint-protection-windows-10.md#windows-encryption) voor BitLocker te configureren voor apparaten waarop Windows-versie 1909 of later wordt uitgevoerd.

Met deze instelling wordt een clientgestuurde vernieuwing van het herstelwachtwoord geïnitieerd na het herstellen van het OS-station (hetzij met behulp van bootmgr of WinRE) en het ontgrendelen van het herstelwachtwoord op een vaste-gegevensstations. Met deze instelling wordt het specifieke gebruikte herstelwachtwoord vernieuwd. Andere niet-gebruikte wachtwoorden in het volume blijven ongewijzigd. Raadpleeg de BitLocker CSP-documentatie voor [ConfigureRecoveryPasswordRotation](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) voor meer informatie.

#### <a name="tamper-protection-for-windows-defender-antivirus---4705448----------"></a>Manipulatiebeveiliging voor Windows Defender Antivirus<!-- 4705448        -->
Gebruik Intune om *Manipulatiebeveiliging* te beheren voor Windows Defender Antivirus. U vindt de [instelling voor Manipulatiebeveiliging](../protect/endpoint-protection-windows-10.md#microsoft-defender-security-center) in de groep Microsoft Defender-beveiligingscentrum wanneer u apparaatconfiguratieprofielen gebruikt voor Windows 10 Endpoint Protection. U kunt Manipulatiebeveiliging instellen op *Ingeschakeld* om beperkingen voor manipulatiebeveiliging in te schakelen, op *Uitgeschakeld* om deze uit te schakelen, of op *Niet geconfigureerd* om de huidige configuratie van apparaten te behouden.  

Zie [Wijzigingen in beveiligingsinstellingen voorkomen met Manipulatiebeveiliging](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection) voor meer informatie over Manipulatiebeveiliging in de Windows-documentatie.

#### <a name="advanced-settings-for-windows-defender-firewall-are-now-generally-available----5317392---------"></a>Geavanceerde instellingen voor Windows Defender Firewall zijn nu algemeen beschikbaar<!--  5317392       -->  
De [aangepaste Windows Defender-firewallregels voor eindpuntbescherming](../protect/endpoint-protection-configure.md#add-custom-firewall-rules-for-windows-10-devices) die u configureert als onderdeel van een apparaatconfiguratieprofiel, zijn niet meer in de openbare preview-versie en zijn algemeen beschikbaar (GA).  U kunt deze regels gebruiken om inkomend en uitgaand gedrag voor toepassingen, netwerkadressen en poorten op te geven. Deze regels zijn in juli uitgebracht als een openbare preview-versie. 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer

#### <a name="scope-tags-now-support-terms-of-use-policies---2358863-idmiss---"></a>Bereiktags bieden nu ondersteuning voor beleid voor gebruiksvoorwaarden<!-- 2358863 idmiss -->
U kunt nu [bereiktags](scope-tags.md) toewijzen aan beleid voor gebruiksvoorwaarden. Hiervoor gaat u naar **Intune** > **Apparaatinschrijving** > **Voorwaarden** > kies een item in de lijst > **Eigenschappen** > **Bereiktags** > kies een bereiktag.

## <a name="week-of-september-9-2019"></a>Week van 9 september 2019

### <a name="app-management"></a>Appbeheer

#### <a name="updates-to-microsoft-intune-app---4997846---"></a>Updates voor de Microsoft Intune-app<!-- 4997846 -->
De Microsoft Intune-app voor Android is bijgewerkt met de volgende verbeteringen:
- De lay-out is bijgewerkt en verbeterd, zodat de belangrijkste navigatiehandelingen nu onderaan staan.
- Er is een extra pagina toegevoegd waarop het gebruikersprofiel wordt weergegeven.
- Er is een weergave van meldingen toegevoegd waarvoor de gebruiker handelingen moet verrichten, zoals wanneer apparaatinstellingen moeten worden bijgewerkt.
- Er is een weergave van aangepaste pushmeldingen toegevoegd. Dit is in lijn met de ondersteuning die recent is toegevoegd in de bedrijfsportal-apps voor iOS en Android. Zie [Aangepaste meldingen verzenden in Intune](../remote-actions/custom-notifications.md) voor meer informatie.

#### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal---4394993---"></a>Voor iOS-apparaten past u het privacyvenster voor het inschrijvingsproces van de Bedrijfsportal aan<!-- 4394993 -->
Met behulp van Markdown kunt u het privacyvenster van de Bedrijfsportal aanpassen dat eindgebruikers te zien krijgen tijdens de iOS-registratie. U kunt met name de lijst met dingen aanpassen die uw organisatie niet op het apparaat kan zien of doen. Zie [De app Intune-bedrijfsportal configureren](../apps/company-portal-app.md#privacy-statement-customization) voor meer informatie.


## <a name="week-of-september-2-2019"></a>Week van 2 september 2019

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="intune-user-interface-update--tenant-status-dashboard---5273210----"></a>Update voor Intune-gebruikersinterface – dashboard Tenantstatus<!-- 5273210  -->
De gebruikersinterface voor het dashboard Tenantstatus is bijgewerkt om deze in lijn te brengen met de stijlen van de Azure-gebruikersinterface. Zie [Tenantstatus](../tenant-status.md) voor meer informatie.

## <a name="week-of-august-26-2019"></a>Week van 26 augustus 2019

### <a name="configure-microsoft-edge-settings-using-administrative-templates-for-windows-10-and-newer---5228061---"></a>Microsoft Edge-instellingen configureren met beheersjablonen voor Windows 10 en nieuwer<!-- 5228061 -->

Op Windows 10- en nieuwere apparaten kunt u beheersjablonen maken om instellingen voor groepsbeleid te configureren in Intune. In deze update kunt u instellingen configureren die van toepassing zijn op Microsoft Edge-versie 77 en nieuwer.

Zie [Windows 10-sjablonen gebruiken voor het configureren van instellingen voor groepsbeleid in Intune](../configuration/administrative-templates-windows.md) voor meer informatie over deze beheersjalbonen.

Van toepassing op:

- Windows 10 en nieuwer (Windows RS4+)

## <a name="week-of-august-12-2019-1908-service-release"></a>Week van 12 augustus 2019 (1908 servicerelease)

### <a name="app-management"></a>Appbeheer

#### <a name="control-ios-app-uninstall-behavior-at-device-unenrollment---3504144-----"></a>Gedrag van het verwijderen van iOS-apps beheren bij het uitschrijven van apparaten<!-- 3504144   -->
Beheerders kunnen beheren of een app wordt verwijderd of behouden op een apparaat wanneer het apparaat wordt uitgeschreven op het niveau van een gebruikers- of apparaatgroep. 

#### <a name="categorize-microsoft-store-for-business-apps---3926922---"></a>Microsoft Store voor Bedrijven-apps categoriseren<!-- 3926922 -->
U kunt Microsoft Store voor Bedrijven-apps categoriseren. Selecteer hiertoe **Intune** > **Client-apps** > **Apps** > selecteer een Microsoft Store voor Bedrijven-app > **App-gegevens** > **Categorie**. Wijs een categorie toe in de vervolgkeuzelijst.

#### <a name="customized-notifications-for-microsoft-intune-app-users---4843354----"></a>Aangepaste meldingen voor gebruikers van Microsoft Intune-apps<!-- 4843354  -->
De Microsoft Intune-app voor Android ondersteunt nu het weergeven van aangepaste pushmeldingen. Dit is in lijn met de ondersteuning die recent is toegevoegd in de bedrijfsportal-apps voor iOS en Android. Zie [Aangepaste meldingen verzenden in Intune](../remote-actions/custom-notifications.md) voor meer informatie.

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="new-features-for-android-enterprise-dedicated-devices-in-multi-app-mode---3755304-3041943-3041946-----"></a>Nieuwe functies voor aan Android Enterprise toegewezen apparaten in de modus voor meerdere apps<!-- 3755304 3041943 3041946   -->

U kunt in Intune functies en instellingen beheren in een kioskstijl op uw toegewezen Android Enterprise-apparaten (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** voor platform > **Alleen apparaateigenaar, Apparaatbeperkingen** voor profieltype).

In deze update worden de volgende functies toegevoegd:

- **Toegewezen apparaten** > Meerdere apps **:** de **Virtuele startknop** kan worden weergegeven door op het apparaat te vegen of op het scherm te zweven zodat gebruikers deze kunnen verplaatsen.
- **Toegewezen apparaten** > Meerdere apps **:** met **zaklantaarn**toegang kunnen gebruikers de zaklantaarn gebruiken. 
- **Toegewezen apparaten** > Meerdere apps **:** met **volumeregeling van media** kunnen gebruikers het mediavolume van het apparaat beheren met behulp van een schuifregelaar. 
- **Toegewezen apparaten** > Meerdere apps **:**  **een schermbeveiliging inschakelen**, een aangepaste afbeelding uploaden en bepalen wanneer de schermbeveiliging wordt weergegeven.

Ga naar [Android Enterprise-apparaatinstellingen om beperkingsfuncties toe te staan of te beperken met behulp van Intune](../configuration/device-restrictions-android-for-work.md#dedicated-device-settings) om de huidige instellingen te zien.

Van toepassing op:

- Toegewezen Android Enterprise-apparaten

#### <a name="new-app-and-configuration-profiles-for-android-enterprise-fully-managed-devices---3574215-3574238-3574235-3574232-----"></a>Nieuwe app- en configuratieprofielen voor volledig beheerde Android Enterprise-apparaten<!-- 3574215 3574238 3574235 3574232   -->
Met behulp van profielen kunt u instellingen configureren die VPN-, e-mail-en Wi-Fi-instellingen toepassen op uw (volledig beheerde) Android Enterprise-apparaten in zakelijk eigendom. In deze update kunt u het volgende doen:

- [App-configuratiebeleid](../apps/app-configuration-policies-use-android.md) gebruiken voor het implementeren van e-mail instellingen van Outlook, Gmail en Nine Work.
- Apparaatconfiguratieprofielen gebruiken om [instellingen voor vertrouwde basiscertificaten](../protect/certificates-configure.md) te implementeren.
- Apparaatconfiguratieprofielen gebruiken om instellingen voor [VPN](../configuration/vpn-settings-android-enterprise.md) en [Wi-Fi](../configuration/wi-fi-settings-android-enterprise.md) te implementeren.

> [!IMPORTANT]
> Met deze functie gebruiken gebruikers hun gebruikersnaam en wachtwoord voor verificatie bij VPN-, Wi-Fi- en e-mailprofielen. Op dit moment is verificatie op basis van certificaten niet beschikbaar.

Van toepassing op:  
- Android Enterprise-apparaten in zakelijk eigendom (volledig beheerd)

#### <a name="control-the-apps-files-documents-and-folders-that-open-when-users-sign-in-to-macos-devices--3914202-----"></a>De apps, bestanden, documenten en mappen beheren die worden geopend wanneer gebruikers zich aanmelden bij macOS-apparaten<!--3914202   -->
U kunt functies inschakelen en configureren op macOS-apparaten (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **macOS** voor platform > **Apparaatfuncties** voor profieltype). 

In deze update is er een nieuwe instelling voor Aanmeldingsitems om te bepalen welke apps, bestanden, documenten en mappen worden geopend wanneer een gebruiker zich aanmeldt bij het geregistreerde apparaat. 

Ga naar [Instellingen van apparaatfuncties voor macOS in Intune](../configuration/macos-device-features-settings.md) om de huidige instellingen te zien.

Van toepassing op:  
- macOS

#### <a name="deadlines-replace-engaged-restart-settings-for-windows-update-rings---4464404----------"></a>Deadlines vervangen instellingen voor gepland opnieuw opstarten voor Windows-updateringen<!-- 4464404        -->
In lijn met recente [wijzigingen in Windows-onderhoud](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903#servicing) ondersteunen de Windows 10-updateringen van Intune nu [instellingen voor deadlines](../protect/windows-update-settings.md). *Deadlines* bepalen wanneer door een apparaat functie-en beveiligingsupdates worden geïnstalleerd.  Op apparaten waarop Windows 10 1903 of hoger wordt uitgevoerd, vervangen *deadlines* de configuraties voor *gepland opnieuw opstarten*.  In de toekomst gaan *deadlines* ook *gepland opnieuw opstarten* in eerdere versies van Windows 10 vervangen.  

Wanneer u geen *deadlines*configureert, blijven apparaten de instellingen voor *gepland opnieuw opstarten* gebruiken. In een toekomstige update gaat Intune ondersteuning voor gepland opnieuw opstarten echter stopzetten.  

Plan het *gebruik* van deadlines voor al uw Windows 10-apparaten. Nadat de instellingen voor *deadlines* zijn ingesteld, kunt u de Intune-configuraties voor *gepland opnieuw opstarten* wijzigen in Niet geconfigureerd. Als deze zijn ingesteld op Niet geconfigureerd, stopt Intune het beheer van deze instellingen op apparaten, maar worden de laatste configuraties voor de instelling niet van het apparaat verwijderd. Daarom blijven de laatste configuraties die zijn ingesteld voor *gepland opnieuw opstarten* actief en in gebruik op apparaten totdat deze instellingen worden gewijzigd door een andere methode dan Intune. Later, wanneer de apparaatversie van Windows verandert of wanneer Intune ondersteuning voor *deadlines* uitbreidt naar de Windows-versie van het apparaat, gaat het apparaat de nieuwe instellingen gebruiken, die al aanwezig zijn.

#### <a name="support-for-multiple-microsoft-intune-certificate-connectors-----4704642--------"></a>Ondersteuning voor meerdere Microsoft Intune Certificate Connectors<!--   4704642      -->
InTune biedt nu ondersteuning voor installatie en gebruik van meerdere [Microsoft Intune Certificate Connectors voor PKCS-bewerkingen](../protect/certficates-pfx-configure.md). Deze wijziging ondersteunt taakverdeling en hoge beschikbaarheid van de connector. Elke connectorinstantie kan certificaataanvragen van Intune verwerken.  Als er geen connector beschikbaar is, blijven andere connectors aanvragen verwerken.

Als u meerdere connectors wilt gebruiken, hoeft u geen upgrade uit te voeren naar de nieuwste versie van de connectorsoftware.  

#### <a name="new-settings-and-changes-to-existing-settings-to-restrict-features-on-ios-and-macos-devices---4867699-4867709-----"></a>Nieuwe instellingen en wijzigingen in bestaande instellingen om functies op iOS-en macOS-apparaten te beperken<!-- 4867699 4867709   -->
U kunt profielen maken om instellingen te beperken op apparaten waarop iOS en macOS worden uitgevoerd (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** of **macOS** voor platform > **Apparaatbeperkingen**). Deze update bevat onder andere de volgende functies:

- Gebruik in **macOS** > **Apparaatbeperkingen** > **Cloud en opslag** de nieuwe **Handoff**-instellingen om te blokkeren dat gebruikers werk starten op een macOS-apparaat en blijven werken op een ander macOS- of iOS-apparaat.

  Als u de huidige instellingen wilt zien, gaat u naar [macOS-apparaatinstellingen voor het toestaan of beperken van functies met Intune](../configuration/device-restrictions-macos.md).

- Er zijn enkele wijzigingen in **iOS** > **Apparaatbeperkingen**:

  - **Ingebouwde apps** > **Zoek mijn iPhone (alleen onder supervisie)** : nieuwe instelling die deze functie blokkeert in de functie Zoek mijn app. 
  - **Ingebouwde apps** > **Zoek mijn vrienden (alleen onder supervisie)** : nieuwe instelling die deze functie blokkeert in de functie Zoek mijn app. 
  - **Draadloos** > **Wijziging van Wi-Fi-status (alleen onder supervisie)** : nieuwe instelling die voorkomt dat gebruikers Wi-Fi op het apparaat in- of uitschakelen.
  - **Toetsenbord en woordenboek** > **QuickPath (alleen onder toezicht)** : nieuwe instelling die de QuickPath-functie blokkeert.
  - **Cloud en opslag**: de naam van de term **Voortzetting van activiteit** is gewijzigd in **Handoff**.

  Als u de huidige instellingen wilt zien, gaat u naar [iOS-apparaatinstellingen voor het toestaan of beperken van functies met Intune](../configuration/device-restrictions-ios.md).

Van toepassing op:  
- macOS 10.15 of hoger
- iOS 13 en hoger

#### <a name="some-unsupervised-ios-device-restrictions-will-become-supervised-only-with-the-ios-130-release---4867809-----"></a>Sommige iOS-apparaatbeperkingen zonder supervisie worden pas met de release van iOS 13.0 onder supervisie geplaatst<!-- 4867809   -->
In deze update zijn sommige instellingen alleen van toepassing op apparaten met supervisie met de release van iOS 13.0. Als deze instellingen zijn geconfigureerd en toegewezen aan apparaten zonder supervisie vóór de iOS 13.0-release, worden de instellingen nog steeds toegepast op deze apparaten zonder supervisie. Ze zijn ook nog steeds van toepassing nadat de apparaten zijn bijgewerkt naar iOS 13.0. Deze beperkingen worden verwijderd op apparaten zonder supervisie waarvan een back-up is gemaakt en die zijn hersteld.

Deze instellingen omvatten:

- App Store, documenten bekijken, gamen
  - App Store
  - Expliciete muziek-, podcast- of nieuwsinhoud op iTunes
  - Game Center-vrienden toevoegen
  - Games voor meerdere spelers
- Ingebouwde apps
  - Camera
    - FaceTime
  - Safari
    - Automatisch doorvoeren
- Cloud en opslag
  - Back-up naar iCloud
  - ICloud-documentsynchronisatie blokkeren
  - Synchronisatie van iCloud-sleutelhanger blokkeren

Als u de huidige instellingen wilt zien, gaat u naar [iOS-apparaatinstellingen voor het toestaan of beperken van functies met Intune](../configuration/device-restrictions-ios.md).

Van toepassing op:  
- iOS 13.0 en hoger

#### <a name="improved-device-status-for-macos-filevault-encryption---4944983-----------"></a>Verbeterde apparaatstatus voor macOS FileVault-versleuteling<!-- 4944983         -->
We hebben een aantal van de [statusberichten](../protect/encryption-monitor.md#device-encryption-status) voor FileVault-versleuteling op macOS-apparaten bijgewerkt.

#### <a name="some-windows-defender-antivirus-scan-settings-in-the-reporting-show-a-failed-status---5119229---"></a>Sommige scaninstellingen voor Windows Defender Antivirus geven in de rapporten de status Mislukt weer<!-- 5119229 -->
In Intune kunt u beleidsregels maken om Windows Defender Antivirus te gebruiken voor het scannen van uw Windows 10-apparaten (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** voor platform > **Apparaatbeperkingen** voor profieltype > **Windows Defender Antivirus**). De rapporten **Tijd waarop een dagelijkse snelle scan moet worden uitgevoerd** en **Type systeemscan dat moet worden uitgevoerd** bevatten de status Mislukt, terwijl het in werkelijkheid de status Geslaagd was. 

In deze update is dit opgelost. De instellingen **Tijd waarop een dagelijkse snelle scan moet worden uitgevoerd** en **Type systeemscan dat moet worden uitgevoerd** geven nu de status Geslaagd weer wanneer de scans met succes zijn uitgevoerd en geven de status Mislukt weer als de instellingen niet kunnen worden toegepast.

Zie [Apparaatinstellingen van Windows 10 (en hoger) voor het toestaan of beperken van functies met Intune](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus) voor meer informatie over de instellingen van Windows Defender Antivirus.

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="default-scope-tags---3702875----"></a>Standaardbereiktags<!-- 3702875  -->
Er is nu een nieuwe ingebouwde standaardbereiktag beschikbaar. Alle niet-getagde Intune-objecten die bereiktags ondersteunen, worden automatisch toegewezen aan de standaardbereiktag. De **standaard**bereiktag wordt toegevoegd aan alle bestaande roltoewijzingen om pariteit met de beheerderservaring te behouden. Als u niet wilt dat een beheerder Intune-objecten met de standaardbereiktag ziet, verwijdert u de standaardbereiktag uit de roltoewijzing. Deze functie is vergelijkbaar met de functie voor beveiligingsbereiken in System Center Configuration Manager. Zie [RBAC en bereiktags gebruiken voor gedistribueerde IT](scope-tags.md) voor meer informatie.

#### <a name="android-enrollment-device-administrator-support---4869749-----"></a>Ondersteuning voor inschrijving van Android-apparaatbeheerder<!-- 4869749   -->
De optie voor inschrijving van Android-apparaatbeheerders is toegevoegd aan de inschrijvingspagina voor Android (**Intune** > **Apparaatinschrijving** > **Android-inschrijving**). Android-apparaatbeheerders worden nog steeds standaard ingeschakeld voor alle tenants.  Zie [Inschrijving van Android-apparaatbeheerders](../enrollment/android-enroll-device-administrator.md) voor meer informatie.

#### <a name="skip-more-screens-in-setup-assistant---4877451----"></a>Meer schermen in de Configuratieassistent overslaan <!--4877451  -->
U kunt Device Enrollment Program-profielen instellen om de volgende schermen van de Configuratieassistent over te slaan:
- Voor iOS
    - Uiterlijk
    - Express-taal
    - Voorkeurstaal
    - Migratie van apparaat naar apparaat
- Voor macOS
    - Schermtijd
    - Touch ID instellen

Zie [Een Apple-inschrijvingsprofiel maken voor iOS ](../enrollment/device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) en [Een Apple-inschrijvingsprofiel maken voor macOS ](../enrollment/device-enrollment-program-enroll-macos.md#create-an-apple-enrollment-profile) voor meer informatie over het aanpassen van de Configuratieassistent.

#### <a name="add-a-user-column-to-the-autopilot-device-csv-upload-process---3823054---"></a>Een gebruikerskolom toevoegen aan het CSV-uploadproces van het Autopilot-apparaat<!-- 3823054 -->
U kunt nu een gebruikerskolom toevoegen aan de CSV-upload voor Autopilot-apparaten. Zo kunt u gebruikers bulksgewijs toewijzen op het moment dat u het CSV-bestand importeert. Zie [Windows-apparaten in Intune inschrijven met Windows Autopilot](../enrollment/enrollment-autopilot.md) voor meer informatie.


### <a name="device-management"></a>Apparaatbeheer

#### <a name="configure-automatic-device-clean-up-time-limit-down-to-30-days--4231059----"></a>De tijdslimiet voor het automatisch opschonen van apparaten verkorten tot 30 dagen<!--4231059  -->
U kunt de tijdslimiet voor automatische opschoning van apparaten instellen op 30 dagen (in plaats van de vorige limiet van 90 dagen) na de laatste aanmelding. Als u dit wilt doen, gaat u naar **intune** > **apparaten** > regels voor het opschonen**van**apparaten**instellen** > .

#### <a name="build-number-included-on-android-device-hardware-page---4461910-----"></a>Buildnummer opgenomen op de hardwarepagina van het Android-apparaat<!-- 4461910   -->
Een nieuw item op de hardwarepagina voor elk Android-apparaat bevat het buildnummer van het besturingssysteem van het apparaat. Zie [Apparaatdetails weergeven in Intune](../remote-actions/device-inventory.md) voor meer informatie.


<!-- ########################## -->

## <a name="week-of-august-5-2019"></a>Week van 5 augustus 2019

### <a name="zebra-technologies-is-a-supported-oem-for-oemconfig-on-android-enterprise-devices---4843713---"></a>Zebra Technologies is een ondersteunde OEM voor OEMConfig op Android Enterprise-apparaten<!-- 4843713 -->

In Intune kunt u apparaatconfiguratieprofielen maken, en instellingen toepassen op Android Enterprise-apparaten met behulp van OEMConfig (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** voor platform > **OEMConfig** voor profieltype).

In deze update is Zebra Technologies een ondersteunde OEM (Original Equipment Manufacturer) voor OEMConfig. Zie [Android Enterprise-apparaten gebruiken en beheren met OEMConfig](../configuration/android-oem-configuration-overview.md) voor meer informatie over OEMConfig.

Van toepassing op:  
- Android Enterprise

<!-- ########################## -->

## <a name="week-of-july-22-2019-1907-service-release"></a>Week van 22 juli 2019 (1907 servicerelease)

### <a name="app-management"></a>Appbeheer

#### <a name="customized-notifications-for-users-and-groups---16766574------------"></a>Aangepaste meldingen voor gebruikers en groepen<!-- 16766574          -->
Verzend aangepaste pushmeldingen vanaf de bedrijfsportaltoepassing naar gebruikers met iOS- en Android-apparaten die u met Intune beheert. Deze mobiele pushmeldingen zijn zeer goed met vrije tekst aan te passen en kunnen voor elk doeleinde worden gebruikt. U kunt ze voor verschillende gebruikersgroepen in uw organisatie gebruiken. Zie [aangepaste meldingen](../remote-actions/custom-notifications.md) voor meer informatie.

#### <a name="googles-device-policy-controller-app---3041950----"></a>App Device Policy Controller van Google<!-- 3041950  -->
De app Managed Home Screen biedt nu toegang tot de app Android Device Policy van Google. De app Managed Home Screen is een aangepast startprogramma dat wordt gebruikt voor apparaten die bij Intune zijn ingeschreven als toegewezen Android Enterprise-apparaat (AE) op basis van de kioskmodus voor meerdere apps. U kunt de app Android Device Policy openen of gebruikers naar de app leiden voor ondersteuning en foutopsporing. De opstartmogelijkheid is beschikbaar op het moment dat het apparaat wordt ingeschreven en wordt gekoppeld aan Managed Home Screen. Er zijn geen extra installaties nodig voor het gebruik van deze functionaliteit.

#### <a name="outlook-protection-settings-for-ios-and-android-devices---3212619---"></a>Outlook-beveiligingsinstellingen voor iOS- en Android-apparaten<!-- 3212619 -->
U kunt nu de algemene configuratie-instellingen voor apps en gegevensbeveiliging configureren voor Outlook voor iOS en Android met behulp van besturingselementen voor eenvoudig Intune-beheer zonder apparaatregistratie. De algemene instellingen voor het configureren van apps bieden pariteit met de instellingen die beheerders kunnen inschakelen bij het beheren van Outlook voor iOS en Android op geregistreerde apparaten. Zie [Deploying Outlook for iOS and Android app configuration settings](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune) (Configuratie-instellingen voor apps implementeren voor Outlook voor iOS en Android) voor meer informatie over instellingen in Outlook.

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910-eeready---idstaged---"></a>Toepasselijkheidsregels gebruiken bij het maken van Windows 10-apparaatconfiguratieprofielen <!-- 2549910 eeready   idstaged -->

U kunt configuratieprofielen voor een Windows 10-apparaat maken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10** als platform > **Toepasbaarheidsregels**). In deze update kunt u een **toepassingsregel** maken, zodat het profiel alleen van toepassing is op een specifieke editie of versie. U maakt bijvoorbeeld een profiel waarmee bepaalde BitLocker-instellingen worden ingeschakeld. Als u het profiel toevoegt, gebruikt u een toepassingsregel zodat het profiel alleen van toepassing is op apparaten met Windows 10 Enterprise.

Zie [Toepasbaarheidsregels](../configuration/device-profile-create.md#applicability-rules) om een toepasbaarheidsregel toe te voegen.

Van toepassing op: Windows 10 en hoger

#### <a name="use-tokens-to-add-device-specific-information-in-custom-profiles-for-ios-and-macos-devices---3330008----"></a>Tokens gebruiken om apparaatspecifieke informatie toe te voegen aan aangepaste profielen voor iOS- en macOS-apparaten<!-- 3330008  -->
U kunt aangepaste profielen op iOS- en macOS-apparaten gebruiken om instellingen en functies te configureren die niet zijn ingebouwd in Intune (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **IOS** of **macOS** als platform > **Aangepast** voor profieltype). In deze update kunt u tokens toevoegen aan uw `.mobileconfig`-bestanden om apparaatspecifieke informatie toe te voegen. U kunt bijvoorbeeld `Serial Number: {{serialnumber}}` toevoegen aan uw configuratiebestand om het serienummer van het apparaat weer te geven.

Zie [Aangepaste iOS-instellingen](../configuration/custom-settings-ios.md) of [Aangepaste macOS-instellingen](../configuration/custom-settings-macos.md) als u een aangepast profiel wilt maken.

Van toepassing op:
- iOS
- macOS

#### <a name="new-configuration-designer-when-creating-an-oemconfig-profile-for-android-enterprise---3712769-----"></a>Nieuwe configuratieontwerper bij het maken van een OEMConfig-profiel voor Android Enterprise<!-- 3712769   -->
U kunt in Intune een apparaatconfiguratieprofiel maken dat gebruikmaakt van een OEMConfig-app (Apparaatconfiguratie > Profielen > Profiel maken > Android Enterprise als platform > OEMConfig als profieltype). Wanneer u dit doet, wordt er een JSON-editor geopend met een sjabloon en waarden die u kunt wijzigen. 

Deze update bevat een versie van Configuratieontwerper met een verbeterde gebruikerservaring, waarin in de app ingesloten details worden weergegeven, waaronder titels, beschrijvingen en meer. De JSON-editor is nog steeds beschikbaar en toont wijzigingen die u aanbrengt in Configuratieontwerper.

Als u de huidige instellingen wilt bekijken, gaat u naar [Android Enterprise-apparaten gebruiken en beheren met OEMConfig](../configuration/android-oem-configuration-overview.md).

Van toepassing op: Android Enterprise

#### <a name="updated-ui-for-configuring-windows-hello---4089576--------------"></a>Bijgewerkte gebruikersinterface voor het configureren van Windows Hello<!-- 4089576            -->
De console waar u [Intune kunt configureren voor het gebruik van Windows Hello voor Bedrijven](../protect/windows-hello.md) is bijgewerkt. Alle configuratie-instellingen zijn nu beschikbaar in hetzelfde deelvenster van de console waar u ondersteuning voor Windows Hello inschakelt.

#### <a name="intune-powershell-sdk---4924113---"></a>Intune PowerShell SDK<!-- 4924113 --> 
De Intune PowerShell SDK, die ondersteuning biedt voor de Intune API via Microsoft Graph, is bijgewerkt naar versie 6.1907.1.0. De SDK ondersteunt nu het volgende:
- Werkt met Azure Automation.
- Ondersteunt leesbewerkingen ter verificatie voor alleen apps. 
- Ondersteunt beschrijvende namen als aliassen.
- Voldoet aan de naamgevingsconventies voor PowerShell. Specifiek is parameter `PSCredential` (in cmdlet `Connect-MSGraph`) gewijzigd in `Credential`.
- Ondersteunt het handmatig opgeven van de waarde van de `Content-Type`-header bij gebruik van cmdlet `Invoke-MSGraphRequest`.

Zie [PowerShell SDK for Microsoft Intune Graph API](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune) (PowerShell SDK voor Microsoft Intune Graph API) voor meer informatie.


### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="updates-for-enrollment-restrictions---2871968---"></a>Updates voor inschrijvingsbeperkingen<!-- 2871968 -->
Inschrijvingsbeperkingen voor nieuwe tenants zijn bijgewerkt, zodat Android Enterprise-werkprofielen standaard worden toegestaan. Bestaande tenants worden niet gewijzigd. Als u Android Enterprise-werkprofielen wilt gebruiken, moet u [uw Intune-account koppelen aan uw beheerde Google Play-account](../enrollment/connect-intune-android-enterprise.md).

#### <a name="ui-updates-for-apple-enrollment-and-enrollment-restrictions--4089575-4089579----"></a>UI-updates voor Apple-inschrijvingen en inschrijvingsbeperkingen<!--4089575, 4089579  -->
De volgende twee processen maken gebruik van een gebruikersinterface in wizardstijl:
- Inschrijving van Apple-apparaten. Zie [iOS-apparaten automatisch inschrijven met het Device Enrollment Program van Apple](../enrollment/device-enrollment-program-enroll-ios.md) voor meer informatie.
- Inschrijvingsbeperkingen maken. Zie [Inschrijvingsbeperkingen instellen](../enrollment/enrollment-restrictions-set.md) voor meer informatie.

#### <a name="handling-pre-configuration-of-corporate-device-identifiers-for-android-q-devices---4711509--idmiss---"></a>Voorbereiding van de configuratie van bedrijfsapparaat-id's voor Android Q-apparaten<!-- 4711509  idmiss -->
In Android Q (v10) verwijdert Google de mogelijkheid voor MDM-agents om op Android-apparaten met verouderd beheer (apparaatbeheerder) informatie over de apparaat-id te verzamelen.  Intune bevat een functie waarmee IT-beheerders [vooraf een lijst met serienummers of IMEI's kunnen configureren](../enrollment/corporate-identifiers-add.md#identify-corporate-owned-devices-with-imei-or-serial-number) om deze apparaten automatisch aan te merken als bedrijfseigendom. Deze functie werkt niet voor Android Q-apparaten die door een apparaatbeheerder worden beheerd.  Ongeacht of het serienummer of IMEI voor het apparaat wordt geüpload, wordt dit tijdens de inschrijving bij Intune altijd als een persoonlijk apparaat beschouwd.  U kunt het eigendom na de inschrijving handmatig overzetten naar het bedrijf.  Dit is alleen van invloed op nieuwe inschrijvingen. Bestaande ingeschreven apparaten worden hierdoor niet beïnvloed.  Android-apparaten die worden beheerd met werkprofielen, worden door deze wijziging niet beïnvloed en blijven werken zoals ze dit momenteel doen.  Ook kunnen Android Q-apparaten die als apparaatbeheerder zijn ingeschreven, niet langer een serienummer of IMEI als apparaateigenschappen rapporteren in de Intune-console.

#### <a name="icons-have-changed-for-android-enterprise-enrollments-work-profile-dedicated-devices-and-fully-managed-devices---4977730---"></a>Voor Android Enterprise zijn enkele pictogrammen gewijzigd (werkprofiel, toegewezen apparaten en volledig beheerde apparaten)<!-- 4977730 -->
De pictogrammen voor Android Enterprise-inschrijvingsprofielen zijn gewijzigd. Als u de nieuwe pictogrammen wilt zien, gaat u naar **Intune** > **Inschrijving** > **Android-inschrijving** > en kijkt u onder **Inschrijvingsprofielen**.


#### <a name="windows-diagnostic-data-collection-change---4113859---"></a>Wijziging in het verzamelen van diagnostische gegevens<!-- 4113859 -->
De standaardwaarde voor het verzamelen van diagnostische gegevens is gewijzigd voor apparaten met Windows 10, versie 1903 en hoger. Vanaf Windows 10 1903 is het verzamelen van diagnostische gegevens standaard ingeschakeld. Diagnostische gegevens van Windows zijn vitale technische gegevens van Windows-apparaten over het apparaat en over hoe Windows en gerelateerde software worden uitgevoerd. Zie [Diagnostische gegevens van Windows in uw organisatie configureren](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization) voor meer informatie. Autopilot-apparaten worden ook ingeschreven voor 'volledige' telemetrie, tenzij dit anders is ingesteld in het Autopilot-profiel met [System/AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry).

### <a name="device-management"></a>Apparaatbeheer

#### <a name="improve-device-location---3855417----"></a>Lokalisatie van apparaat verbeteren<!-- 3855417  -->
U kunt inzoomen op de exacte coördinaten van een apparaat met behulp van de actie **Apparaat zoeken**. Zie [Verloren iOS-apparaten zoeken](../remote-actions/device-locate.md) voor meer informatie over het zoeken naar verloren iOS-apparaten.

### <a name="device-security"></a>Apparaatbeveiliging

#### <a name="advanced-settings-for-windows-defender-firewall--public-preview----1311949-------"></a>Geavanceerde instellingen voor Windows Defender Firewall (openbare preview)<!--  1311949     -->  
Gebruik Intune voor het beheren van [aangepaste firewallregels als onderdeel van een configuratieprofiel voor een apparaat](../protect/endpoint-protection-configure.md#add-custom-firewall-rules-for-windows-10-devices) voor eindpuntbeveiliging in Windows 10. Met regels kunt u inkomend en uitgaand gedrag voor toepassingen, netwerkadressen en poorten opgeven. 

#### <a name="updated-ui-for-managing-security-baselines---4091125-------"></a>Bijgewerkte gebruikersinterface voor het beheren van beveiligingsbasislijnen<!-- 4091125     -->
[Maken en bewerken](../protect/security-baselines.md#create-the-profile) in de Intune-console voor de beveiligingsbasislijnen is bijgewerkt. De wijzigingen zijn onder andere:

Een eenvoudigere wizardstijl die op één blade is samengevoegd. binnen één blade. In dit nieuwe ontwerp wordt niet langer gebruikgemaakt van meerdere blades, waarbij IT-professionals in meerdere, afzonderlijke deelvensters moeten inzoomen.  
U kunt nu toewijzingen maken als onderdeel van het maken en bewerken. Hierdoor hoeft u later geen basislijnen meer toe te voegen. Er is een samenvatting van de instellingen toegevoegd die u kunt bekijken voordat u een nieuwe basislijn maakt of een bestaande regel bewerkt. Tijdens het bewerken toont de samenvatting alleen de lijst met items die zijn ingesteld binnen de categorie met eigenschappen die worden bewerkt.

<!-- ########################## -->

## <a name="week-of-july-15-2019"></a>Week van 15 juli 2019 

### <a name="app-management"></a>Appbeheer

#### <a name="managed-home-screen-and-managed-settings-icons---4918107---"></a>Pictogrammen Managed Home Screen en Beheerde instellingen<!-- 4918107 -->
Het app-pictogram Managed Home Screen en het pictogram **Beheerde instellingen** zijn bijgewerkt. De app Managed Home Screen wordt alleen gebruikt voor apparaten die bij Intune zijn ingeschreven als toegewezen Android Enterprise-apparaat (AE) en die worden uitgevoerd in de kioskmodus voor meerdere apps. Zie [De app Microsoft Managed Home Screen voor Android Enterprise configureren](../apps/app-configuration-managed-home-screen-app.md) voor meer informatie over de app Managed Home Screen.

#### <a name="android-device-policy-on-android-enterprise-dedicated-devices---4918136---"></a>Android Device Policy op toegewezen Android Enterprise-apparaten<!-- 4918136 -->
U kunt de toepassing Android Device Policy openen vanuit het scherm voor het opsporen van fouten in de app Managed Home Screen. De app Managed Home Screen wordt alleen gebruikt voor apparaten die bij Intune zijn ingeschreven als toegewezen Android Enterprise-apparaat (AE) en die worden uitgevoerd in de kioskmodus voor meerdere apps. Zie [De app Microsoft Managed Home Screen voor Android Enterprise](../apps/app-configuration-managed-home-screen-app.md) voor meer informatie.

#### <a name="ios-company-portal-updates---3902931---"></a>Updates voor de iOS-bedrijfsportal<!-- 3902931 -->
De naam van uw bedrijf in prompts van iOS-app-beheer vervangt de huidige tekst 'i.manage.microsoft.com'. Gebruikers zien bijvoorbeeld hun bedrijfsnaam in plaats van 'i.manage.microsoft.com' wanneer ze een iOS-app willen installeren vanuit de bedrijfsportal of wanneer ze beheer van de app toestaan. Dit wordt de komende dagen voor alle klanten uitgebracht.

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="manage-filevault-for-macos----3858502--4557986--1210104----"></a>FileVault voor macOS beheren<!--  3858502 + 4557986 + 1210104  -->
U kunt Intune gebruiken voor het [beheren van FileVault-versleuteling van sleutels voor macOS-apparaten](../protect/encrypt-devices.md). Gebruik een configuratieprofiel voor apparaten met eindpuntbeveiliging als u een apparaat wilt versleutelen.

De ondersteuning voor FileVault omvat het versleutelen van niet-versleutelde apparaten, borgstelling van de persoonlijke herstelsleutel voor apparaten, automatische of handmatige rotatie van persoonlijke versleutelingssleutels en het ophalen van sleutels voor uw zakelijke apparaten. Eindgebruikers kunnen ook de website van de bedrijfsportal gebruiken om de persoonlijke herstelsleutel voor hun versleutelde apparaten op te halen.

Het versleutelingsrapport is aangevuld met [informatie over FileVault](../protect/encryption-monitor.md) en informatie over BitLocker, zodat u alle gegevens over de apparaatversleuteling op één plek kunt bekijken.

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="windows-autopilot-reset-removes-the-devices-primary-user---4156123---"></a>Met Windows Autopilot opnieuw instellen wordt de primaire gebruiker van het apparaat verwijderd<!-- 4156123 -->
Wanneer Autopilot opnieuw instellen op een apparaat wordt gebruikt, wordt de primaire gebruiker van het apparaat verwijderd. De volgende gebruiker die zich na het opnieuw instellen aanmeldt, wordt ingesteld als primaire gebruiker. Deze functie wordt de komende dagen voor alle klanten uitgebracht.

## <a name="week-of-july-8-2019"></a>Week van 8 juli 2019

### <a name="new-office-windows-and-onedrive-settings-in-windows-10-administrative-templates----3510695---"></a>Nieuwe instellingen voor Office, Windows en OneDrive in Windows 10-beheersjablonen <!-- 3510695 -->

In Intune kunt u beheersjablonen maken die het on-premises beheer van het groepsbeleid nabootsen (**Apparaatbeheer** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** als platform > **Beheersjabloon** als profieltype).

Deze update bevat meer instellingen voor Office, Windows en OneDrive die u aan uw sjablonen kunt toevoegen. Met deze nieuwe instellingen kunt u nu meer dan 2500 instellingen configureren die voor 100% op de cloud gebaseerd zijn.

Zie [Windows 10-sjablonen gebruiken voor het configureren van instellingen voor groepsbeleid in Intune](../configuration/administrative-templates-windows.md) voor meer informatie over deze functie.

Van toepassing op: Windows 10 en hoger

## <a name="week-of-july-1-2019"></a>Week van 1 juli, 2019 

### <a name="app-management"></a>Appbeheer

#### <a name="aad-and-app-on-android-enterprise-devices---3574267---"></a>AAD en APP op Android Enterprise-apparaten<!-- 3574267 -->
Bij het onboarden van volledig beheerde Android Enterprise-apparaten registreren gebruikers zich tijdens de eerste installatie van hun nieuwe apparaat (of hun apparaat die naar de fabrieksinstellingen is teruggezet) voortaan bij Azure Active Directory (AAD). Voor een volledig beheerd apparaat was het voorheen zo dat de gebruiker de Microsoft Intune-app na voltooiing van de installatie handmatig moest starten om AAD-registratie te starten. Als de gebruiker nu na de initiële installatie op de startpagina van het apparaat terechtkomt, wordt het apparaat ingeschreven en geregistreerd.

Naast de AAD-updates worden beleidsregels voor Intune-app-beveiliging (APP) voortaan ondersteund op volledig beheerde Android Enterprise-apparaten. Deze functionaliteit wordt beschikbaar tijdens de implementatie. Zie [Beheerde Google Play-apps toevoegen aan Android Enterprise-apparaten met Intune](../apps/apps-add-android-for-work.md) voor meer informatie.

## <a name="week-of-june-24-2019-1906-service-release"></a>Week van 24 juni 2019 (1906 servicerelease)

### <a name="app-management"></a>Appbeheer

#### <a name="configure-which-browser-is-allowed-to-link-to-organization-data---3145939---"></a>Configureren welke browser een koppeling met organisatiegegevens mag maken<!-- 3145939 -->
Met beleidsregels voor Intune-app-beveiliging (APP) op Android- en iOS-apparaten kunt u webkoppelingen van een organisatie overbrengen naar een specifieke browser buiten Intune Managed Browser of Microsoft Edge.  Zie [Wat is beveiligingsbeleid voor apps?](../apps/app-protection-policy.md) voor meer informatie over APP.

#### <a name="all-apps-page-identifies-onlineoffline-microsoft-store-for-business-apps--4089647---"></a>Op de pagina Alle apps worden online/offline Microsoft Store voor zakelijke apps geïdentificeerd<!--4089647 -->
De pagina **Alle apps** bevat nu labels voor het identificeren van MSFB-apps (Microsoft Store for Business) als online- of offline-apps. Elke MSFB-app bevat nu een achtervoegsel voor **Online** of **Offline**. De pagina met app-details bevat ook informatie over het **licentietype** en **ondersteunt de installatie van apparaatcontext** (alleen offline gelicentieerde apps).

#### <a name="company-portal-app-on-windows-shared-devices--4393553---"></a>Bedrijfsportal-app op gedeelde Windows-apparaten<!--4393553 -->
Gebruikers hebben nu toegang tot de Bedrijfsportal-app op gedeelde Windows-apparaten. Eindgebruikers krijgen het label **Gedeeld** op de apparaattegel te zien. Dit geldt voor versie 10.3.45609.0 en hoger van de Windows Bedrijfsportal-app.

#### <a name="view-all-installed-apps-from-new-company-portal-web-page---4224326---"></a>Alle geïnstalleerde apps weergeven op de nieuwe webpagina van de bedrijfsportal<!-- 4224326 -->
De nieuwe pagina **Geïnstalleerde apps** van de website van de bedrijfsportal geeft alle beheerde apps (zowel vereiste als beschikbare) weer die op het apparaat van een gebruiker zijn geïnstalleerd. Naast het type toewijzing kunnen gebruikers de uitgever van de app, de publicatiedatum en de huidige installatiestatus weergeven. Als u geen apps voor uw gebruikers verplicht of beschikbaar hebt gesteld, zien zij het bericht dat er geen bedrijfs-apps zijn geïnstalleerd. Ga naar de [website van de bedrijfsportal](https://portal.manage.microsoft.com) en klik op **Geïnstalleerde apps** om de nieuwe pagina op het web te zien.  

#### <a name="new-view-lets-app-users-see-all-managed-apps-installed-on-device---2352913---"></a>In de nieuwe weergave kunnen app-gebruikers alle beheerde apps zien die op het apparaat zijn geïnstalleerd<!-- 2352913 -->  
De bedrijfsportal voor Windows toont nu alle beheerde apps (zowel vereiste als beschikbare) die op het apparaat van een gebruiker zijn geïnstalleerd. Gebruikers kunnen ook geprobeerde en in behandeling zijnde app-installaties weergeven met de huidige status ervan. Als u geen apps voor uw gebruikers verplicht of beschikbaar hebt gesteld, zien zij het bericht dat er geen bedrijfs-apps zijn geïnstalleerd. Ga naar het navigatievenster in de bedrijfsportal en selecteer **Apps** > **Geïnstalleerde apps** om de nieuwe weergave weer te geven.

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="configure-settings-for-kernel-extensions-on-macos-devices---2043024---"></a>Instellingen voor kernelextensies configureren op macOS-apparaten<!-- 2043024 -->
U kunt op macOS-apparaten een apparaatconfiguratieprofiel maken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** kies > **macOS** als platform). Deze update bevat een nieuwe groep instellingen waarmee u kernelextensies op uw apparaten kunt configureren en gebruiken. U kunt specifieke extensies toevoegen, maar ook alle uitbreidingen van een specifieke partner of ontwikkelaar toestaan.

Zie [overzicht van de kernelextensies](../configuration/kernel-extensions-overview-macos.md) en [instellingen voor de kernelextensie](../configuration/kernel-extensions-settings-macos.md) voor meer informatie over deze functie.

Van toepassing op: macOS 10.13.2 en hoger

#### <a name="apps-from-the-store-only-setting-for-windows-10-devices-includes-more-configuration-options---2697002---"></a>Instelling Alleen apps van de Store voor Windows 10-apparaten bevat meer configuratieopties<!-- 2697002 -->
Wanneer u een apparaatbeperkingsprofiel voor Windows-apparaten maakt, kunt u de instelling **Alleen apps van de Store** gebruiken, zodat gebruikers alleen apps van Windows App Store installeren (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** voor platform > **Apparaatbeperkingen** voor profieltype). In deze update wordt deze instelling uitgebreid om meer opties te ondersteunen.

Als u de nieuwe instelling wilt zien, gaat u naar [Apparaatinstellingen voor Windows 10 (en hoger) voor het toestaan of beperken van functies](../configuration/device-restrictions-windows-10.md#app-store).

Van toepassing op: Windows 10 en hoger

#### <a name="deploy-multiple-zebra-mobility-extensions-device-profiles-to-a-device-same-user-group-or-same-devices-group---4089955---"></a>Meerdere apparaatprofielen voor Zebra-mobiliteitsextensies op een apparaat of voor dezelfde gebruikersgroep of groep apparaten implementeren<!-- 4089955 -->
U kunt in Intune Zebra-mobiliteitsextensies (MX) gebruiken in een apparaatconfiguratieprofiel om instellingen aan te passen voor Zebra-apparaten die niet in Intune zijn ingebouwd. Op dit moment kunt u één profiel op één apparaat implementeren. In deze update kunt u meerdere profielen implementeren voor het volgende:
- Dezelfde gebruikersgroep
- Dezelfde groep apparaten
- Eén apparaat

In [Use and manage Zebra devices with Zebra Mobility Extensions in Microsoft Intune](../configuration/android-zebra-mx-overview.md) (Zebra-apparaten gebruiken en beheren met Zebra Mobility Extensions in Microsoft Intune) ziet u hoe u MX in Intune gebruikt.

Van toepassing op: Android

#### <a name="some-kiosk-settings-on-ios-devices-are-set-using-block-replacing-allow---4404075----"></a>Sommige kioskinstellingen op iOS-apparaten worden ingesteld met behulp van Blokkeren, waardoor Toestaan wordt vervangen<!-- 4404075  -->
Wanneer u een apparaatbeperkingsprofiel maakt op iOS-apparaten (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype > **Kiosk**), stelt u de **automatisch vergrendeling**, **schakelaar voor het belsignaal**, **schermrotatie**, **schermsluimerknop** en **volumeknoppen** in.

In deze update gaat het om de waarden **Blokkeren** (blokkeert de functie) of **Niet geconfigureerd** (staat de functie toe). Als u de instellingen wilt bekijken, gaat u naar [iOS-apparaatinstellingen voor het toestaan of beperken van functies](../configuration/device-restrictions-ios.md#kiosk).

Van toepassing op: iOS

#### <a name="use-face-id-for-password-authentication-on-ios-devices---4490704---"></a>Face ID voor wachtwoordverificatie op iOS-apparaten gebruiken<!-- 4490704 -->
Wanneer u een apparaatbeperkingsprofiel voor iOS-apparaten maakt, kunt u een vingerafdruk als wachtwoord gebruiken. In deze update is met de instellingen voor vingerafdrukwachtwoorden ook gezichtsherkenning mogelijk (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** als platform > **Apparaatbeperkingen** als profieltype > **Wachtwoord**). Als gevolg hiervan zijn de volgende instellingen gewijzigd:

- **Ontgrendelen met vingerafdruk** is nu **Touch ID en Face ID ontgrendelen**.
- **Wijziging van vingerafdruk (alleen onder supervisie)** is nu **Aanpassing van Touch ID en Face ID (alleen onder supervisie)** .

Face ID is beschikbaar in iOS 11.0 en hoger. Als u de instellingen wilt bekijken, gaat u naar [iOS-apparaatinstellingen voor het toestaan of beperken van functies met behulp van Intune](../configuration/device-restrictions-ios.md#password).

Van toepassing op: iOS

#### <a name="restricting-gaming-and-app-store-features-on-ios-devices-is-now-dependent-on-ratings-region---4593948---"></a>Het beperken van gaming- en App Store-functies op iOS-apparaten is nu afhankelijk van de regio voor restricties<!-- 4593948 -->
Op iOS-apparaten kunt u functies toestaan of beperken met betrekking tot gaming, de App Store en het weergeven van documenten (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype > **App Store, documentweergave, gaming**). U kunt ook de classificatieregio kiezen, zoals de Verenigde Staten.

In deze update wordt de functie **Apps** een onderliggend element van **Regio voor restricties** en is deze afhankelijk van **Regio voor restricties**. Als u de instellingen wilt bekijken, gaat u naar [iOS-apparaatinstellingen voor het toestaan of beperken van functies met behulp van Intune](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming).

Van toepassing op: iOS

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="windows-autopilot-support-for-hybrid-azure-ad-join---4809146--"></a>Ondersteuning voor Windows Autopilot voor Hybrid Azure AD Join<!-- 4809146-->
Windows Autopilot voor bestaande apparaten ondersteunt nu Hybrid Azure AD Join (naast de bestaande ondersteuning voor Azure AD Join). Is van toepassing op Windows 10-apparaten, versie 1809 en hoger. Zie [Windows Autopilot voor bestaande apparaten](https://docs.microsoft.com/windows/deployment/windows-autopilot/existing-devices) voor meer informatie.

### <a name="device-management"></a>Apparaatbeheer

#### <a name="see-the-security-patch-level-for-android-devices---4461911---"></a>Het niveau van de beveiligingspatch voor Android-apparaten bekijken<!-- 4461911 -->
U kunt nu het niveau van de beveiligingspatch voor Android-apparaten bekijken. Kies hiervoor **Intune** > **Apparaten** > **Alle apparaten** > kies een apparaat > **Hardware**.
Het patchniveau wordt weergegeven in het gedeelte **Besturingssysteem**.

#### <a name="assign-scope-tags-to-all-managed-devices-in-a-security-group---3173810---"></a>Bereiktags toewijzen aan alle beheerde apparaten in een beveiligingsgroep<!-- 3173810 -->
U kunt nu bereiktags toewijzen aan een beveiligingsgroep waarbij ook alle apparaten in de beveiligingsgroep aan die bereiktags worden gekoppeld. De bereiktag wordt ook aan alle apparaten in deze groepen toegewezen. De bereiktags die worden ingesteld met deze functie, vervangen de bereiktags die zijn ingesteld met de huidige stroom voor apparaatbereiktags. Zie [RBAC en bereiktags gebruiken voor gedistribueerde IT](scope-tags.md) voor meer informatie.

### <a name="device-security"></a>Apparaatbeveiliging

#### <a name="use-keyword-search-with-security-baselines------"></a>Zoekopdrachten met trefwoorden gebruiken met Beveiligingsbasislijnen<!--  -->
Wanneer u [beveiligingsbasislijnprofielen](../protect/security-baselines.md#create-the-profile) maakt of bewerkt, kunt u trefwoorden opgeven in de nieuwe *zoekbalk* om de beschikbare groepen instellingen te filteren op degene die de zoekcriteria bevatten.

#### <a name="the-security-baselines-feature-is-now-generally-available---3785395---"></a>De functie Beveiligingsbasislijnen is nu algemeen beschikbaar<!-- 3785395 -->
Voor de functie **Beveiligingsbasislijnen** is de previewfase beëindigd. De functie is nu algemeen beschikbaar.  Dit betekent dat de functie gereed is voor gebruik in productie. De afzonderlijke basislijnsjablonen blijven mogelijk echter wel in de previewfase, en worden geëvalueerd en op basis van hun eigen planningen algemeen uitgebracht.

#### <a name="the-mdm-security-baseline-template-is-now-generally-available---3794072-4217151--3534649---"></a>De sjabloon MDM-beveiligingsbasislijn is algemeen beschikbaar<!-- 3794072, 4217151,  3534649 -->
Voor de sjabloon MDM-beveiligingsbasislijn is de previewfase beëindigd. De functie is nu algemeen beschikbaar. De algemeen beschikbare sjabloon wordt geïdentificeerd als **MDM-beveiligingsbasislijn voor mei 2019**.  Dit is een nieuwe sjabloon en geen upgrade van de previewversie.  Voor een nieuwe sjabloon moet u de [instellingen die deze bevat](../protect/security-baseline-settings-mdm.md), controleren en vervolgens nieuwe profielen maken om de sjabloon voor uw apparaat te implementeren. Andere beveiligingsbasislijnsjablonen blijven mogelijk in de previewfase. Zie [Beschikbare beveiligingsbasislijnen](../protect/security-baselines.md#available-security-baselines) voor een lijst met beschikbare basislijnen.  

De nieuwe sjabloon *MDM-beveiligingsbasislijn voor mei 2019* bevat de twee instellingen die onlangs zijn aangekondigd in het artikel In ontwikkeling:  
- Vergrendeling boven: Door spraak geactiveerde apps vanaf een vergrendeld scherm  
- DeviceGuard: Gebruik Beveiliging op basis van virtualisatie (VBS) als de apparaten de volgende keer opnieuw worden opgestart.  

Voor de *MDM-beveiligingsbasislijn voor mei 2019* geldt dat er ook een aantal nieuwe instellingen is toegevoegd, andere eruit zijn verwijderd en de standaardwaarde van één instelling is gewijzigd. Zie **wat is er gewijzigd in de nieuwe sjabloon** voor een uitgebreide lijst met de wijzigingen van de previewversie (nu algemeen uitgebracht).

#### <a name="security-baseline-versioning---3194322---"></a>Versiebeheer van beveiligingsbasislijnen<!-- 3194322 -->
Beveiligingsbasislijnen voor versiebeheer van de ondersteuning voor Intune. Nu er nieuwe versies van elke beveiligingsbasislijn worden uitgebracht, kunt u dankzij deze ondersteuning uw bestaande beveiligingsbasislijnprofielen bijwerken voor gebruik van de nieuwere basislijnversie, zonder dat u zelf opnieuw een geheel nieuwe basislijn hoeft te maken en te implementeren. Daarnaast kunt u in de Intune-console informatie bekijken over elke basislijn, zoals het aantal afzonderlijke profielen die gebruikmaken van de basislijn, hoeveel verschillende basislijnversies er door uw profielen worden gebruikt en wanneer de meest recente release van een bepaalde beveiligingbasislijn is geweest.  Zie **Beveiligingsbasislijnen** voor meer informatie.

#### <a name="the-use-security-keys-for-sign-in-setting-has-moved---4501151---"></a>De instelling Beveiligingssleutels gebruiken voor aanmelden is verplaatst<!-- 4501151 -->
De instelling voor apparaatconfiguratie voor identiteitsbeveiliging met de naam **Beveiligingssleutels gebruiken voor aanmelden** is niet meer aanwezig als subinstelling van *Windows Hello voor Bedrijven configureren*. Het is nu een instelling op het hoogste niveau die altijd beschikbaar is, ook als u het gebruik van Windows Hello voor Bedrijven niet inschakelt. Zie [Identity Protection](../protect/identity-protection-windows-settings.md) voor meer informatie.

### <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer

#### <a name="new-permissions-for-assigned-group-admins---4504437-----"></a>Nieuwe machtigingen voor toegewezen groepsbeheerders<!-- 4504437   -->
De in Intune ingebouwde rol School Administrator bevat nu machtigingen voor maken, lezen, bijwerken en verwijderen (CRUD-machtigingen) voor beheerde apps. Deze update betekent dat als u in Intune for Education bent toegewezen als groepsbeheerder, u voortaan het iOS MDM-pushcertificaat, iOS MDM-servertokens en iOS VPP-tokens kunt maken, weergeven, bijwerken en verwijderen, in combinatie met [alle bestaande machtigingen die u hebt](https://docs.microsoft.com/intune-education/group-admin-delegate#group-admin-permissions). Als u een van deze acties wilt uitvoeren, gaat u naar **Tenantinstellingen** > **iOS-apparaatbeheer**.  

#### <a name="applications-can-use-the-graph-api-to-call-read-operations-without-user-credentials---4655885---"></a>Toepassingen kunnen gebruikmaken van de Graph API om leesbewerkingen aan te roepen zonder gebruikersreferenties<!-- 4655885 -->
Toepassingen kunnen met app-identiteiten Intune Graph API-leesbewerkingen aanroepen, zonder dat er gebruikersreferenties nodig zijn. Zie [Working with Intune in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0) (Werken met intune in Microsoft Graph) voor meer informatie over het openen van de Microsoft Graph API voor Intune.

#### <a name="apply-scope-tags-to-microsoft-store-for-business-apps---4392555---"></a>Bereiktags toepassen op Microsoft Store voor Bedrijven-apps<!-- 4392555 -->
U kunt voortaan bereiktags toepassen op Microsoft Store voor Bedrijven-apps. Zie [Use role-based access control and scope tags for distributed IT](scope-tags.md) (Op rollen gebaseerd toegangsbeheer (RBAC) en bereiktags gebruiken voor gedistribueerde IT) voor meer informatie over bereiktags.

## <a name="week-of-june-17-2019"></a>Week van 17 juni 2019

### <a name="app-management"></a>Appbeheer

#### <a name="new-features-in-microsoft-intune-app"></a>Nieuwe functies in Microsoft Intune-app
We hebben nieuwe functies toegevoegd aan de Microsoft Intune-app (preview) voor Android. Gebruikers op volledig beheerde Android-apparaten kunnen nu:  

* De apparaten weergeven en beheren die zij hebben ingeschreven via de Intune-bedrijfsportal of de Microsoft Intune-app.
* Contact opnemen met hun organisatie voor ondersteuning.
* Feedback naar Microsoft sturen.
* Algemene voorwaarden bekijken als deze zijn ingesteld door hun organisatie.

## <a name="week-of-june-10-2019"></a>Week van 10 juni 2019

### <a name="app-management"></a>Appbeheer

#### <a name="new-sample-apps-showing-intune-sdk-integration-available-on-github---2653471---"></a>Er zijn nieuwe voorbeeld-apps met Intune SDK-integratie beschikbaar op GitHub<!-- 2653471 -->
Met het GitHub-account msintuneappsdk zijn nieuwe voorbeeldtoepassingen toegevoegd voor iOS (Swift), Android, Xamarin.iOS, Xamarin Forms en Xamarin.Android. Deze apps zijn bedoeld als aanvulling op onze bestaande documentatie en demonstraties van hoe u de Intune APP SDK kunt integreren in uw eigen mobiele apps. Als u als app-ontwikkelaar aanvullende begeleiding bij de Intune SDK nodig hebt, raadpleegt u de volgende gekoppelde voorbeelden:
- [Chatr](https://github.com/msintuneappsdk/Chatr-Sample-Intune-iOS-App): een systeemeigen iOS (Swift)-berichtenapp die gebruikmaakt van de Azure Active Directory Authentication Library (ADAL) voor verificatie via een broker.
- [Taskr](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Android-App): een systeemeigen Android-app voor takenlijsten die gebruikmaakt van ADAL voor verificatie via een broker.
- [Taskr](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Xamarin-Android-Apps): een Xamarin.Android-app voor takenlijsten die gebruikmaakt van ADAL voor verificatie via een broker. Deze opslagplaats bevat ook de Xamarin.Forms-app.
- [Voorbeeld-app voor Xamarin.iOS](https://github.com/msintuneappsdk/sample-intune-xamarin-ios): een barebones Xamarin.iOS-voorbeeld-app.

## <a name="week-of-may-27-2019"></a>Week van 27 mei 2019

### <a name="app-management"></a>Appbeheer

#### <a name="reporting-for-potentially-harmful-apps-on-android-devices---4223162---"></a>Rapportage voor mogelijk schadelijke apps op Android-apparaten<!-- 4223162 -->
Intune biedt nu aanvullende rapportagegegevens over mogelijk schadelijke apps op Android-apparaten. 

## <a name="week-of-may-20-2019"></a>Week van 20 mei 2019

### <a name="app-management"></a>Appbeheer

#### <a name="windows-company-portal-app---3316993---"></a>Windows-bedrijfsportal-app<!-- 3316993 -->
De Windows-bedrijfsportal-app heeft nu een nieuwe pagina met het label **Apparaten**. Op de pagina **Apparaten** staan de eindgebruikers van alle ingeschreven apparaten. Gebruikers zien deze wijziging in de bedrijfsportal als ze versie 10.3.4291.0 of hoger gebruiken. Voor informatie over het configureren van de bedrijfsportal-app, ziet u [How to configure the Microsoft Intune Company Portal app](../apps/company-portal-app.md) (De app Microsoft Intune-bedrijfsportal configureren).

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="autopilot-device-orderid-attribute-name-changed-to-group-tag----4659453---"></a>De kenmerknaam OrderID voor Autopilot-apparaten is gewijzigd in Groepstag <!-- 4659453 -->

Voor een meer intuïtieve benadering is de kenmerknaam **OrderID** voor Autopilot-apparaten gewijzigd in **Groepstag**. Als u CSV's gebruikt voor het uploaden van Autopilot-apparaatgegevens, moet u Groepstag als kolomkop gebruiken en niet OrderID.  

## <a name="week-of-may-13-2019-1905-service-release"></a>Week van 13 mei 2019 (1905 servicerelease)

### <a name="app-management"></a>Appbeheer

#### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation---1927359----"></a>Intune-beleid werkt de verificatiemethode en installatie van de Bedrijfsportal-app bij<!-- 1927359  -->
Intune biedt geen ondersteuning meer voor de Bedrijfsportal wanneer deze handmatig door eindgebruikers uit de appstore wordt geïnstalleerd op apparaten die al met behulp van Configuratieassistent zijn ingeschreven via een van de Apple-registratiemethoden voor bedrijfsapparaten. Deze wijziging is alleen relevant wanneer u tijdens de inschrijving verifieert met Apple Setup Assistant. Deze wijziging is eveneens alleen van invloed op iOS-apparaten die zijn ingeschreven via:  
* Apple Configurator

* Apple Business Manager

* Apple School Manager

* Apple Device Enrollment Program (DEP)

Als gebruikers de Bedrijfsportal-app installeren uit de App Store en vervolgens apparaten via de app proberen te registreren, treedt er een foutmelding op. Er wordt van uitgegaan dat deze apparaten de Bedrijfsportal alleen gebruiken wanneer het automatisch door Intune tijdens de registratie is gepusht. Inschrijvingsprofielen in Intune in de Azure-portal worden bijgewerkt zodat u kunt opgeven hoe apparaten zich verifiëren en hoe zij de Bedrijfsportal-app ontvangen. Als u wilt dat uw DEP-apparaatgebruikers de Bedrijfsportal hebben, moet u uw voorkeuren in een inschrijvingsprofiel opgeven. 

Bovendien wordt het scherm **Uw apparaat identificeren** in de Bedrijfsportal-app van iOS binnenkort niet meer gebruikt. Beheerders die voorwaardelijke toegang willen inschakelen of bedrijfs-apps willen implementeren moeten daarom het DEP-inschrijvingsprofiel bijwerken. Deze vereiste geldt alleen als de DEP-inschrijving wordt geverifieerd met Configuratieassistent. In dat geval moet u de Bedrijfsportal naar het apparaat pushen. Hiervoor kiest u **Intune** > **Apparaatinschrijving** > **Apple-inschrijving** > **Tokens voor het inschrijfprogramma** > kies een token > **Profielen** > kies een profiel > **Eigenschappen** > stel **Bedrijfsportal installeren** in op **Ja**.

Als u de Bedrijfsportal wilt installeren op DEP-apparaten die al zijn ingeschreven, gaat u naar Intune > Client-apps en pusht u de app als beheerde app met app-configuratiebeleid. 

#### <a name="configure-how-end-users-update-a-line-of-business-lob-app-using-an-app-protection-policy---3568384---"></a>Configureren hoe eindgebruikers een LOB-app (Line-Of-Business) bijwerken met behulp van een beveiligingsbeleid voor apps<!-- 3568384 -->
U kunt nu configureren waar uw eindgebruikers een bijgewerkte versie van een LOB-app (Line-Of-Business) kunnen downloaden. Eindgebruikers zien deze functie in het dialoogvenster **minimale app-versie** van de functie voor voorwaardelijk starten, waarin eindgebruikers wordt gevraagd om bij te werken naar een minimale versie van de LOB-app. U moet deze informatie opgeven als onderdeel van uw het beveiligingsbeleid voor uw LOB-app (APP). Deze functie is beschikbaar voor iOS en Android. Voor iOS vereist deze functie dat de app is geïntegreerd (of verpakt met behulp van het wrapping-programma) met de Intune SDK voor iOS versie 10.0.7 of hoger. Voor Android vereist deze functie de meest recente versie van de Bedrijfsportal. Als u wilt configureren hoe een eindgebruiker een LOB-app kan bijwerken, moet er configuratiebeleid voor een beheerde app worden verzonden naar de app met de sleutel `com.microsoft.intune.myappstore`. De verzonden waarde bepaalt uit welke store de eindgebruiker de app kan downloaden. Als de app wordt geïmplementeerd via de Bedrijfsportal-app, moet de waarde `CompanyPortal` zijn. Voor iedere andere store moet u een volledige URL opgeven.

#### <a name="intune-management-extension-powershell-scripts---3734186----"></a>Intune-beheerextensie voor PowerShell-scripts<!-- 3734186  -->
U kunt configureren dat PowerShell-scripts worden uitgevoerd met de beheerdersbevoegdheden van de gebruiker op het apparaat. Zie [PowerShell-scripts op Windows 10-apparaten gebruiken in Intune](../apps/intune-management-extension.md) en [Win32 app management](../apps/app-management.md) (Beheer van Win32-apps) voor meer informatie.

#### <a name="android-enterprise-app-management---4459905---"></a>Beheer van Android Enterprise-apps<!-- 4459905 -->
Om het eenvoudiger te maken voor IT-beheerders om Android Enterprise-beheer te configureren en gebruiken, voegt Intune automatisch vier veelgebruikte Android Enterprise apps toe aan de beheerconsole van Intune. Het betreft de volgende vier Android Enterprise-apps:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)** : wordt gebruikt voor scenario's met volledig beheer door Android Enterprise.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)** : om u aan te melden bij uw accounts als u verificatie in twee stappen gebruikt.
- **[Intune-bedrijfsportal](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)** : wordt gebruikt voor beleidsregels voor app-beveiliging (APP) en werkprofielscenario's van Android Enterprise.
- [Managed Home Screen](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise): wordt gebruikt voor toegewezen/kiosk-scenario's van Android Enterprise.

Eerder moesten IT-beheerders deze apps als onderdeel van de installatie handmatig zoeken en goedkeuren in de [beheerde Google Play Store](https://play.google.com/store/apps). Met deze wijziging worden deze eerdere handmatige stappen weggenomen om het gemakkelijker en sneller te maken voor klanten om Android Enterprise-beheer te gebruiken.

Deze vier apps worden automatisch toegevoegd aan de lijst met Intune-apps van beheerders op het moment dat ze hun Intune-tenant voor het eerst verbinden met de beheerde Google Play Store. Zie [Uw Intune-account verbinden met uw Beheerde Google Play-account](../enrollment/connect-intune-android-enterprise.md) voor meer informatie. Beheerders die hun tenant al hebben verbonden of die al gebruikmaken van Android Enterprise hoeven niets te doen. Zeven dagen na het voltooien van de implementatie van de service-update van mei 2019 zijn deze vier apps automatisch beschikbaar.

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune---1533038---"></a>Bijgewerkte PFX-certificaatconnector voor Microsoft Intune<!-- 1533038 -->
We hebben een update uitgebracht voor de [PFX Certificate Connector voor Microsoft Intune](../protect/certficates-pfx-configure.md#whats-new-for-connectors) die een oplossing biedt voor een probleem waarbij bestaande PFX-certificaten steeds opnieuw worden verwerkt. Hierdoor stopt de connector met het verwerken van nieuwe aanvragen.

#### <a name="intune-security-tasks-for-defender-atp-in-public-preview---3208597---"></a>Intune-beveiligingstaken voor Defender ATP (in openbare preview)<!-- 3208597 -->
In de openbare preview-versie kunt u Intune gebruiken voor het beheren van [beveiligingstaken voor Microsoft Defender Advanced Threat Protection (ATP)](../protect/atp-manage-vulnerabilities.md). Door deze integratie met ATP wordt er een op risico's gebaseerde aanpak voor het detecteren, classificeren en oplossen van beveiligingsproblemen en onjuiste configuraties van eindpunten toegevoegd, terwijl er ook minder tijd zit tussen het detecteren en oplossen van beveiligingsproblemen.

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy---3617671---idstaged--"></a>Controleren of er zich een TPM-chipset in een nalevingsbeleid voor Windows 10-apparaten bevindt<!-- 3617671   idstaged-->
Veel apparaten met Windows 10 en hoger hebben TPM-chipsets (Trusted Platform Module). Deze update bevat een nieuwe nalevingsinstelling die de versie van de TPM-chip in het apparaat controleert.

Deze instelling wordt beschreven in [Instellingen voor nalevingsbeleid voor apparaten met Windows 10 en later](../protect/compliance-policy-create-windows.md#device-security).

Van toepassing op: Windows 10 en hoger

#### <a name="prevent-end-users-from-modifying-their-personal-hotspot-and-disable-siri-server-logging-on-ios-devices---4097904-----"></a>Voorkomen dat gebruikers hun persoonlijke hotspot wijzigen en logboekregistratie van Siri-server op iOS-apparaten uitschakelen<!-- 4097904   -->  
U maakt een profiel met apparaatbeperkingen op het iOS-apparaat (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype). Deze update bevat nieuwe instellingen die u kunt configureren:

- **Ingebouwde apps**: logboekregistratie op de server voor Siri-opdrachten
- **Draadloos**: wijzing van persoonlijke hotspot door gebruiker (alleen onder supervisie)

Als u deze instellingen wilt zien, gaat u naar [ingebouwde app-instellingen voor iOS](../configuration/device-restrictions-ios.md#built-in-apps) en [draadloze instellingen voor iOS](../configuration/device-restrictions-ios.md#wireless).

Van toepassing op: iOS 12.2 en nieuwer

#### <a name="new-classroom-app-device-restriction-settings-for-macos-devices---4097905-----"></a>Nieuwe instellingen voor apparaatbeperkingen voor Klaslokaal-app op macOS-apparaten<!-- 4097905   --> 
U kunt apparaatconfiguratieprofiel voor macOS-apparaten maken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **macOS** voor platform > **Apparaatbeperkingen** voor profieltype). Deze update bevat nieuwe instellingen voor de Classroom-app, de optie om schermopnamen te blokkeren en de optie om de iCloud-fotobibliotheek uit te schakelen.

Als u de huidige instellingen wilt zien, gaat u naar [macOS-apparaatinstellingen voor het toestaan of beperken van functies met Intune](../configuration/device-restrictions-macos.md).

Is van toepassing op: macOS

#### <a name="the-ios-password-to-access-app-store-setting-is-renamed---4557891----"></a>De naam van het iOS-wachtwoord voor toegang tot App Store-instellingen is gewijzigd<!-- 4557891  -->
De naam van de instelling **Wachtwoord voor toegang tot de App Store** is gewijzigd in **iTunes Store-wachtwoord vereisen voor alle aankopen** (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype > **App Store, documenten bekijken, gamen**).

Als u de beschikbare instellingen wilt zien, gaat u naar [App Store, documenten bekijken, gamen](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming).

Van toepassing op: iOS

#### <a name="microsoft-defender-advanced-threat-protection--baseline--preview----3754134---"></a>Microsoft Defender Advanced Threat Protection-basislijn (preview)<!--  3754134 -->
We hebben een preview van een basislijn voor beveiliging toegevoegd voor [Microsoft Defender Advanced Threat Protection](../protect/security-baseline-settings-defender-atp.md)-instellingen. Deze basislijn is beschikbaar als uw omgeving voldoet aan de vereisten voor het gebruik van [Microsoft Defender Advanced Threat Protection](../protect/advanced-threat-protection.md#prerequisites).

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="windows-enrollment-status-page-esp-is-now-generally-available---3605348---"></a>Pagina Status van inschrijving is nu algemeen beschikbaar<!-- 3605348 -->
De pagina Status van inschrijving is nu uit preview en algemeen beschikbaar. Raadpleeg [Een pagina voor de status van de inschrijving instellen](../enrollment/windows-enrollment-status.md) voor meer informatie.


#### <a name="intune-user-interface-update---autopilot-enrollment-profile-creation---4593669---"></a>Update van Intune-gebruikersinterface - Autopilot-inschrijvingsprofiel maken<!-- 4593669 -->
De gebruikersinterface voor het maken van een Autopilot-inschrijvingsprofiel is bijgewerkt om deze in lijn te brengen met de stijlen van de Azure-gebruikersinterface. Zie [Een Autopilot-inschrijvingsprofiel maken](../enrollment/enrollment-autopilot.md#create-an-autopilot-deployment-profile) voor meer informatie. Binnenkort worden ook andere Intune-scenario's bijgewerkt naar deze nieuwe stijl voor de gebruikersinterface.

#### <a name="enable-autopilot-reset-for-all-windows-devices---4225665---"></a>Autopilot opnieuw instellen voor alle Windows-apparaten inschakelen<!-- 4225665 -->
Autopilot opnieuw instellen werkt nu voor alle Windows-apparaten, ook als deze niet zijn geconfigureerd voor het gebruik van de pagina Status van inschrijving. Als er tijdens de eerste apparaatregistratie geen pagina voor de status van inschrijving is geconfigureerd voor het apparaat, wordt op het apparaat direct het bureaublad weergegeven na het aanmelden. Het duurt maximaal acht uur totdat de synchronisatie is voltooid en het apparaat als compatibel wordt weergegeven in Intune. Zie [Reset devices with remote Windows Autopilot Reset](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-reset-remote) (Apparaten op afstand opnieuw instellen met Autopilot opnieuw instellen van Windows) voor meer informatie.

#### <a name="exact-imei-format-not-required-when-searching-all-devices--30407680---"></a>Exacte IME-indeling niet vereist bij het zoeken naar alle apparaten<!--30407680 -->
U hoeft geen spaties op te nemen in IMEI-nummers wanneer u zoekt met **Alle apparaten**.

#### <a name="deleting-a-device-in-the-apple-portal-will-be-reflected-in-the-intune-portal--2489996---"></a>Verwijderen van apparaat in de Apple-portal wordt doorgevoerd in de Intune-portal<!--2489996 -->
Als een apparaat wordt verwijderd uit de portal van het Device Enrollment Program van Apple of van Apple Business Manager, wordt het apparaat bij de volgende synchronisatie automatisch verwijderd uit Intune.

### <a name="the-enrollment-status-page-now-tracks-win32-apps---2714451---"></a>Op de pagina Status van inschrijving worden nu Win32-apps bijgehouden<!-- 2714451 -->
Dit is alleen van toepassing op apparaten met Windows 10 versie 1903 en hoger. Raadpleeg [Een pagina voor de status van de inschrijving instellen](../enrollment/windows-enrollment-status.md) voor meer informatie.

### <a name="device-management"></a>Apparaatbeheer

#### <a name="reset-and-wipe-devices-in-bulk-by-using-the-graph-api---3295288---"></a>Apparaten in bulk opnieuw instellen en wissen met behulp van de Graph API<!-- 3295288 -->
U kunt nu in één bulkbewerking tot wel 100 apparaten opnieuw instellen en wissen met behulp van de Graph API.

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="the-encryption-report-is-out-of-public-preview---4587546--------"></a>Het rapport Versleuteling is uit openbare preview<!-- 4587546      -->
Het [rapport voor BitLocker- en apparaatversleuteling](../protect/encryption-monitor.md) is nu algemeen beschikbaar en maakt geen deel meer uit van de openbare preview.

<!-- ########################## -->

#### <a name="outlook-signature-and-biometric-settings-for--ios-and-android-devices---4050557---"></a>Outlook-handtekening en biometrische instellingen voor iOS- en Android-apparaten<!-- 4050557 -->
U kunt nu opgeven of de standaardhandtekening moet worden ingeschakeld in Outlook voor iOS- en Android-apparaten. Bovendien kunt u eventueel toestaan dat gebruikers de biometrische instelling wijzigen in Outlook voor iOS.

## <a name="week-of-may-6-2019"></a>Week van 6 mei 2019

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="network-access-control-nac-support-for-f5-access-for-ios-devices---4500808---"></a>Ondersteuning voor netwerktoegangsbeheer (NAC) voor F5 Access voor iOS-apparaten<!-- 4500808 -->

F5 heeft een update voor BIG-IP 13 uitgebracht waardoor de NAC-functionaliteit is toegestaan voor F5-toegang op iOS in Intune. Om deze functie te gebruiken, moet u ook het volgende doen:

- Werk BIG-IP bij naar 13.1.1.5, vernieuwen. BIG-IP 14 wordt niet ondersteund.
- Integreer BIG-IP met Intune voor NAC. Stappen in [Overzicht: APM configureren voor apparaatpostuurcontroles met eindpuntbeheersystemen](https://techdocs.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html).
- Schakel de instelling **Netwerktoegangsbeheer (NAC) inschakelen** in het VPN-profiel in Intune in.

Ga naar [VPN-instellingen configureren op iOS-apparaten](../configuration/vpn-settings-ios.md) om de beschikbare instelling te zien.

Van toepassing op: iOS

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune---doc-vso-1521237----"></a>Bijgewerkte PFX-certificaatconnector voor Microsoft Intune<!-- doc-vso 1521237  -->  
We hebben een update uitgebracht voor de [PFX-certificaatconnector voor Microsoft Intune](../protect/certficates-pfx-configure.md#whats-new-for-connectors), waardoor de polling-interval wordt verlaagd van 5 minuten naar 30 seconden.




## <a name="notices"></a>Mededelingen

[!INCLUDE [Intune notices](../includes/intune-notices.md)]
