---
title: Wat is er nieuw in Microsoft Intune?
titleSuffix: Intune on Azure
description: Ontdekken wat er nieuw is in Intune Azure Portal
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 07/03/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fdda99bfd72c71d36a19449d43bc6cbf6a00babe
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2017
---
# <a name="whats-new-in-microsoft-intune"></a>Wat is er nieuw in Microsoft Intune?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ontdek elke week wat er nieuw is in Microsoft Intune. U vindt hier ook informatie over [toekomstige wijzigingen](#whats-coming), [belangrijke kennisgevingen](#notices) betreffende de service en informatie over [oudere releases](whats-new-archive.md).

> [!Note]
> Veel van deze functies worden uiteindelijk ondersteund voor hybride implementaties met Configuration Manager. Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
  ### Role-based access control
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
-->   



## <a name="week-of-june-26th-2017"></a>Week van 26 juni 2017

### <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer
#### <a name="new-role-based-administration-access-for-intune-admins------1099990---"></a>Nieuwe toegangsrol voor Intune-beheerders   <!-- 1099990 -->  
Er wordt een nieuwe beheerdersrol voor voorwaardelijke toegang toegevoegd waarmee het voorwaardelijke toegangsbeleid van Azure AD kan worden weergegeven, gemaakt en gewijzigd. Voorheen beschikten alleen hoofdbeheerders en beveiligingsbeheerders over deze machtiging. Deze rolmachtiging kan nu ook worden toegekend aan Intune-beheerders, zodat ze toegang hebben tot de beleidsregels voor voorwaardelijke toegang.


### <a name="device-enrollment"></a>Apparaatinschrijving
#### <a name="tag-corporate-owned-devices-with-serial-number----1215070---"></a>Labelen van apparaten in bedrijfseigendom met een serienummer <!-- 1215070 -->  
Intune ondersteunt nu het uploaden van serienummers van iOS-, macOS- en Android-apparaten als id's van apparaten in bedrijfseigendom. U kunt op dit moment geen serienummers gebruiken om de registratie van persoonlijke apparaten te blokkeren, omdat er geen serienummers worden geverifieerd tijdens de registratie. U kunt persoonlijke apparaten binnenkort ook blokkeren op basis van het serienummer.


### <a name="device-management"></a>Apparaatbeheer
#### <a name="new-remote-actions-for-ios-devices----854689---"></a>Nieuwe externe acties voor iOS-apparaten <!-- 854689 -->
In deze release hebben we twee nieuwe externe acties voor iOS-apparaten toegevoegd:

-   [Huidige gebruiker afmelden](device-logout-user.md): hiermee kunt u de huidige gebruiker afmelden van een iOS-apparaat dat u kiest.
-   [Gebruiker verwijderen](device-remove-user.md): hiermee kunt u een gebruiker verwijderen uit de lokale cache op een iOS-apparaat.


Met behulp van deze externe acties kunnen beheerders de gebruikersaccounts beheren die zijn opgeslagen in de cache op een gedeelde iPad en ook de gebruiker afmelden die momenteel is aangemeld bij het apparaat.

Tijdens de registratie bepaalt de beheerder het maximum aantal gebruikersaccounts dat kan worden opgeslagen in de cache van een apparaat. Met de actie Gebruiker verwijderen kunnen beheerders specifieke gebruikers verwijderen die in de cache zijn opgeslagen.

De actie Huidige gebruiker afmelden is bedoeld om de gebruiker af te melden die momenteel bij het apparaat is aangemeld. Deze actie vindt u bovenaan de blade met het overzicht van het apparaat, waar apparaatacties altijd worden weergegeven.

Met de actie Gebruiker verwijderen wordt een opgegeven gebruiker verwijderd uit de lokale cache van het apparaat. Voor deze actie kiest u Bewaken > Gebruikers en klikt u met de rechtermuisknop op een specifieke gebruiker in de lijst. Gegevens die zijn gekoppeld aan het gebruikersaccount en die niet zijn gesynchroniseerd, gaan verloren. Het kan overigens maximaal 24 uur duren voordat de lijst met gebruikers is bijgewerkt en de verwijderde gebruiker niet meer wordt vermeld.

#### <a name="support-for-shared-ipads-with-the-ios-classroom-app----1044681---"></a>Ondersteuning voor gedeelde iPads met de iOS-app Classroom <!-- 1044681 -->
In deze release is de ondersteuning voor het beheren van de iOS-app Classroom uitgebreid naar studenten die zich met hun beheerde Apple ID aanmelden bij gedeelde iPads.


### <a name="app-management"></a>Appbeheer  
#### <a name="support-for-offline-apps-from-the-windows-store-for-business-----777044----"></a>Ondersteuning voor offline apps uit de Windows Store voor Bedrijven <!--- 777044 --->
Offline-apps die u hebt gekocht in de Windows Store voor Bedrijven worden voortaan gesynchroniseerd met de Intune-portal. Vervolgens kunt u deze apps implementeren naar apparaat- of gebruikersgroepen. Offline apps worden geïnstalleerd door Intune en niet door de store.

#### <a name="microsoft-teams-is-now-part-of-the-app-based-ca-list-of-approved-apps------1257019---"></a>Microsoft Teams is nu opgenomen in de lijst met goedgekeurde apps voor voorwaardelijke toegang   <!-- 1257019 -->

De Microsoft Teams-app voor iOS en Android is nu een goedgekeurde app voor toepassing van beleid voor voorwaardelijke toegang op basis van apps voor Exchange en SharePoint Online. De app kan via de blade Intune-app-beveiliging in Azure Portal worden geconfigureerd voor alle tenants die op dit moment gebruikmaken van voorwaardelijke toegang op basis van apps.

#### <a name="managed-browser-and-app-proxy-integration----1287310---"></a>Managed Browser en app-proxy-integratie <!-- 1287310 -->
 De Intune-app Managed Browser kan nu worden geïntegreerd met de Azure AD-toepassingsproxy om gebruikers ook toegang te bieden tot interne websites als ze op afstand werken. Gebruikers van de browser voeren op de gebruikelijke manier de URL van de gewenste site in en de Managed Browser-app verstuurt de aanvraag via de webgateway van de toepassingsproxy. Zie [Internettoegang beheren met beleid van Managed Browser](app-configuration-managed-browser.md) voor meer informatie.


#### <a name="new-app-configuration-settings-for-the-intune-managed-browser----682951---"></a>Nieuw app-configuratie-instellingen voor Intune Managed Browser <!-- 682951 -->
In deze release hebben we weer extra configuraties toegevoegd voor de Intune Managed Browser-app voor iOS en Android. U kunt nu een beleid voor app-configuratie gebruiken om de standaardstartpagina en -bladwijzers voor de browser te configureren.
Zie [Internettoegang beheren met beleid van Managed Browser](app-configuration-managed-browser.md) voor meer informatie.




### <a name="device-configuration"></a>Apparaatconfiguratie  
#### <a name="bitlocker-settings-for-windows-10-----951707---"></a>BitLocker-instellingen voor Windows 10  <!-- 951707 -->
U kunt nu BitLocker-instellingen configureren voor Windows 10-apparaten met behulp van een nieuw Intune-apparaatprofiel. U kunt bijvoorbeeld afdwingen dat apparaten worden versleuteld en nog andere instellingen configureren die worden toegepast als BitLocker is ingeschakeld.
Zie [Instellingen voor de beveiliging van eindpunten voor Windows 10 en hoger](endpoint-protection-windows-10.md) voor meer informatie.

### <a name="new-settings-for-windows-10-device-restriction-profile-----978527--978550-978569-1050031-1058611-----"></a>Nieuwe instellingen voor het beperkingsprofiel voor Windows 10-apparaten <!--- 978527,  978550, 978569, 1050031, 1058611,  --->

In deze release hebben we nieuwe instellingen toegevoegd voor het profiel voor apparaatbeperking van Windows 10, en wel in de volgende categorieën:

 -  Windows Defender
-  Mobiel en connectiviteit
-  Vergrendeld scherm
-  Privacy
-  Zoeken
-  Windows Spotlight
-  Edge-browser

Zie [Instellingen voor apparaatbeperking van Windows 10 en hoger](device-restrictions-windows-10.md) voor meer informatie over Windows 10-instellingen.

## <a name="week-of-june-12-2017"></a>Week van 12 juni 2017

### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a>De Intune-bedrijfsportal-app voor Android heeft een nieuwe interface voor app-beveiligingsbeleid<!--1305217-->
Op basis van feedback van klanten hebben we de Intune-bedrijfsportal-app voor Android aangepast en de knop **Toegang verkrijgen tot bedrijfsinhoud** toegevoegd. De reden hiervoor is dat eindgebruikers dan niet onnodig het registratieproces moeten doorlopen wanneer ze alleen toegang nodig hebben tot apps die ondersteuning bieden voor app-beveiligingsbeleid, een functie van Intune Mobile Application Management. U kunt deze wijzigingen zien op [deze pagina](whats-new-app-ui.md).

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>Nieuwe menu-actie voor het eenvoudig verwijderen van de bedrijfsportal <!--1164569-->
Op basis van feedback van gebruikers is aan de bedrijfsportal-app voor Android een nieuwe menu-actie toegevoegd om het verwijderen van de bedrijfsportal van uw apparaat te starten. Met deze actie verwijdert u het apparaat uit Intune-beheer, zodat de app door de gebruiker van het apparaat kan worden verwijderd. U kunt deze wijzigingen zien op de pagina [Wat is er nieuw in de gebruikersinterface van apps](whats-new-app-ui.md) en in de [Android-eindgebruikersdocumentatie](/intune-user-help/unenroll-your-device-from-intune-android).

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>Verbeterde synchronisatie van apps met Windows 10-makersupdate <!--676505-->

De bedrijfsportal-app voor Windows 10 voert nu automatisch een synchronisatie uit voor app-installatieaanvragen voor apparaten met Windows 10-makersupdate (versie 1703). Hierdoor is de kans aanzienlijk kleiner dat app-installaties worden gestopt tijdens de status Synchronisatie in behandeling. Daarnaast kunnen gebruikers handmatig een synchronisatie uitvoeren vanuit de app. U kunt deze wijzigingen zien op [deze pagina](whats-new-app-ui.md).

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Nieuwe begeleide ervaring voor Windows 10-bedrijfsportal<!---1058938--->

De bedrijfsportal-app voor Windows 10 bevat een begeleiding voor Intune voor apparaten die nog niet zijn geïdentificeerd of geregistreerd. Deze nieuwe ervaring biedt stapsgewijze instructies die gebruikers begeleidt bij de registratie bij Azure Active Directory (vereist voor de voorwaardelijke toegangsfuncties) en MDM-registratie (vereist voor apparaatbeheerfuncties). De stapsgewijze instructies zijn toegankelijk via de startpagina van de bedrijfsportal. Als gebruikers de registratie en inschrijving niet voltooien, kunnen ze de app gewoon blijven gebruiken, maar is de functionaliteit beperkt.

Deze update is alleen zichtbaar op apparaten met Windows 10 Jubileumupdate (build 1607) of hoger. U kunt deze wijzigingen zien op [deze pagina](whats-new-app-ui.md).

## <a name="week-of-june-5-2017"></a>Week van 5 juni 2017

### <a name="microsoft-intune-and-conditional-access-admin-consoles-are-generally-available"></a>Beheerconsoles voor Microsoft Intune en Voorwaardelijke toegang zijn algemeen beschikbaar

Microsoft kondigt de algemene beschikbaarheid van zowel de nieuwe Intune op Azure-beheerconsole als de beheerconsole voor Voorwaardelijke toegang aan. Via Intune in Azure kunt u nu alle Intune MAM- en de MDM-mogelijkheden beheren in één geconsolideerde beheerderservaring en gebruikmaken van groeperen en doelen instellen met Azure AD. Voorwaardelijke toegang in Azure biedt uitgebreide mogelijkheden in Azure AD en Intune samen in één centrale console. En vanuit beheerdersoogpunt kunt u door de overgang naar het Azure-platform gebruikmaken van moderne browsers.

Intune is nu zichtbaar zonder het label **preview** in de Azure-console op portal.azure.com.

Er is op dit moment geen actie vereist voor bestaande klanten, tenzij u in het berichtencenter een bericht hebt ontvangen waarin u wordt gevraagd actie te ondernemen, zodat de groepen kunnen worden gemigreerd. Mogelijk hebt u in het berichtencentrum ook een kennisgeving ontvangen waarin wordt gemeld dat de migratie langer duurt als gevolg van fouten aan de kant van Microsoft. Microsoft blijft zich ten volle inzetten voor het migreren van de betrokken klanten.

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>Verbeteringen in de app-tegels in de bedrijfsportal-app voor iOS
Het ontwerp van de app-tegels op de startpagina is bijgewerkt in overeenstemming met de huisstijlkleur die u voor de bedrijfsportal instelt. Raadpleeg [Wat is er nieuw in de gebruikersinterface van apps?](whats-new-app-ui.md) voor meer informatie.

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>Account objectkiezer nu beschikbaar voor de bedrijfsportal-app voor iOS
Gebruikers van iOS-apparaten zien mogelijk onze nieuwe accountkiezer wanneer ze zich aanmelden bij de bedrijfsportal als ze hun werk- of schoolaccount gebruiken voor aanmelding bij andere Microsoft-apps. Raadpleeg [Wat is er nieuw in de gebruikersinterface van apps?](whats-new-app-ui.md) voor meer informatie.

## <a name="week-of-may-29-2017"></a>Week van 29 mei 2017

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>Wijzig uw MDM-instantie zonder de registratie van beheerde apparaten ongedaan te maken <!--1103950-->

U kunt nu uw MDM-instantie wijzigen zonder dat u contact hoeft op te nemen met Microsoft Ondersteuning en zonder dat u de registratie van bestaande beheerde apparaten ongedaan hoeft te maken om ze vervolgens opnieuw te registreren. In de Configuration Manager-console kunt u uw [MDM-instantie wijzigen](/sccm/mdm/deploy-use/change-mdm-authority) van Ingesteld op Configuration Manager (hybride) naar Microsoft Intune (zelfstandig) of vice versa.


### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Verbeterde melding voor Samsung KNOX-opstartpincodes<!--1087143-->
Als eindgebruikers een opstartpincode op Samsung KNOX-apparaten moeten instellen om te voldoen aan de versleuteling, wordt er een melding aan eindgebruikers weergegeven. Wanneer eindgebruikers op deze melding tikken, worden ze omgeleid naar de exacte plaats in de app Instellingen.  Voorheen werd de eindgebruiker omgeleid naar het scherm voor het wijzigen van het wachtwoord.


### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="apple-school-manager-asm-support-with-shared-ipad----748864-770395--"></a>Ondersteuning voor Apple School Manager (ASM) met gedeelde iPad<!-- 748864, 770395-->

Intune ondersteunt nu het gebruik van Apple School Manager (ASM) in plaats van Apple Device Enrollment Program voor een out-of-box-registratie van iOS-apparaten. Onboarding van ASM is vereist om de app Classroom voor gedeelde iPads te kunnen gebruiken en om gegevens via Microsoft School Data Sync (SDS) te kunnen synchroniseren van ASM naar Azure Active Directory. Zie [Inschrijving van iOS-apparaten inschakelen met Apple School Manager](apple-school-manager-set-up-ios.md) voor meer informatie.

> [!NOTE]
> Voor het configureren van gedeelde iPads voor het werken met de app Classroom zijn iOS Education-configuraties in Azure vereist die nog niet beschikbaar zijn.  Deze functionaliteit wordt binnenkort toegevoegd.

### <a name="device-management"></a>Apparaatbeheer

#### <a name="provide-remote-assistance-to-android-devices-using-teamviewer----675418---"></a>Hulp op afstand verlenen op Android-apparaten met TeamViewer <!-- 675418 -->

Intune kan nu de afzonderlijk verkrijgbare [TeamViewer](https://www.teamviewer.com)-software gebruiken, zodat u uw gebruikers met Android-apparaten hulp op afstand kunt bieden. Zie [Provide remote assistance for Intune managed Android devices](device-profile-android-teamviewer.md) (Hulp op afstand verlenen voor Android-apparaten die worden beheerd door Intune) voor meer informatie.

### <a name="app-management"></a>Appbeheer

#### <a name="new-app-protection-policies-conditions-for-mam----679864---"></a>Nieuwe beleidsvoorwaarden voor MAM met betrekking tot de beveiliging van apps<!-- 679864 -->

U kunt nu een vereiste instellen voor gebruikers die MAM gebruiken zonder inschrijving. Hiermee kunt u het volgende afdwingen:

- Minimumversie van de toepassing
- Minimumversie van het besturingssysteem
- Minimumversie van de SDK voor de Intune-app van de doeltoepassing (alleen iOS)

Deze functie is beschikbaar op Android en iOS. Intune ondersteunt het afdwingen van een minimumversie voor besturingssystemen, toepassingen en de SDK voor de Intune-app. Voor iOS geldt dat toepassingen met een geïntegreerde SDK ook een minimumversie kunnen afdwingen op SDK-niveau. De gebruiker heeft geen toegang tot de betreffende toepassing als niet aan de minimale vereisten van het app-beveiligingsbeleid wordt voldaan op de hierboven genoemde drie verschillende niveaus. Op dit moment kan de gebruiker het account (voor toepassingen met meerdere identiteiten) verwijderen, de toepassing sluiten of de versie van het besturingssysteem of de toepassing bijwerken.

U kunt tevens aanvullende instellingen configureren om een niet-blokkerende melding te verstrekken waarin de gebruiker wordt aanbevolen een upgrade voor het besturingssysteem of de toepassing uit te voeren. Deze melding kan worden gesloten en de toepassing kan gewoon worden gebruikt.

Zie [Beveiligingsbeleidsinstellingen voor iOS-apps](app-protection-policy-settings-ios.md) en [Beveiligingsbeleidsinstellingen voor Android-apps](app-protection-policy-settings-android.md) voor meer informatie.

#### <a name="configure-app-configurations-for-android-for-work----621621---"></a>App-instellingen configureren voor Android for Work <!-- 621621 -->
Sommige Android-apps uit de store ondersteunen beheerde configuratieopties waarmee een IT-beheerder kan controleren hoe een app wordt uitgevoerd in het werkprofiel. Met Intune kunt u nu de configuraties weergeven die worden ondersteund door een app en deze configureren vanuit de Intune-portal met een configuratieontwerper of een JSON-editor. Zie [Use app configurations for Android for Work](app-configuration-policies-use-android.md) (App-configuraties gebruiken voor Android for Work) voor meer informatie.

#### <a name="new-app-configuration-capability-for-mam-without-enrollment----677969---"></a>Nieuwe mogelijkheid voor app-configuratie voor MAM zonder inschrijving <!-- 677969 -->

U kunt nu beleidsregels voor app-configuratie maken via het kanaal voor MAM zonder inschrijving. Deze functie is gelijk aan de beleidsregels voor app-configuratie die beschikbaar zijn in de MDM-app-configuratie (Mobile Device Management). Zie [Internettoegang beheren met beheerde-browserbeleid met Microsoft Intune](app-configuration-managed-browser.md) voor een voorbeeld van app-configuratie met MAM zonder inschrijving.

#### <a name="configure-allowed-and-blocked-url-lists-for-the-managed-browser----682960---"></a>Lijsten met toegestane en geblokkeerde URL's voor Managed Browser configureren <!-- 682960 -->

U kunt nu een lijst configureren met toegestane en geblokkeerde domeinen en URL's voor de Intune Managed Browser met app-configuratie-instellingen in Azure Portal. Deze instellingen kunnen altijd worden geconfigureerd, ongeacht of de lijst wordt gebruikt op een beheerd of onbeheerd apparaat. Zie [Internettoegang beheren met beheerde-browserbeleid met Microsoft Intune](app-configuration-managed-browser.md) voor meer informatie.

#### <a name="app-protection-policy-helpdesk-view----1069473---"></a>Helpdeskweergave voor beveiligingsbeleidsinstellingen voor apps <!-- 1069473 -->

IT-helpdeskgebruikers kunnen nu de status van de gebruikerslicentie en de status van aan gebruikers toegewezen app-beveiligingsbeleid controleren de blade voor probleemoplossing. Zie [Probleemoplossing](./help-desk-operators.md) voor meer informatie.

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="control-website-visits-on-ios-devices----723832---"></a>Websitebezoeken op iOS-apparaten controleren <!-- 723832 -->

U kunt nu bepalen welke websites de gebruikers van iOS-apparaten kunnen bezoeken met een van de volgende twee methoden:

- Toegestane en geblokkeerde URL's toevoegen met het ingebouwde webinhoudsfilter van Apple.

- Alleen opgegeven websites toestaan voor de Safari-browser. Voor elke website die u opgeeft wordt een bladwijzer gemaakt in Safari.

Zie [Filterinstellingen voor webinhoud op iOS-apparaten](web-content-filter-settings-ios.md) voor meer informatie.

#### <a name="preconfigure-device-permissions-for-android-for-work-apps----621614---"></a>Apparaatmachtigingen voor Android for Work-apps vooraf configureren<!-- 621614 -->

Voor apps die worden geïmplementeerd voor Android for Work-apparaatwerkprofielen, kunt u nu de machtigingsstatus configureren voor afzonderlijke apps.  Android-apps die apparaatmachtigingen vereisen, zoals voor toegang tot uw locatie of de apparaatcamera, vragen gebruikers de machtiging te accepteren of te weigeren.  Als een app bijvoorbeeld gebruikmaakt van de microfoon van het apparaat, wordt de gebruiker gevraagd de app toestemming te verlenen voor het gebruik van de microfoon. Met deze functie kunt u namens de eindgebruiker machtigingen definiëren.  U kunt machtigingen configureren voor a) automatisch weigeren zonder de gebruiker op de hoogte te stellen, b) automatisch goedkeuren zonder de gebruiker op de hoogte te stellen of c) de gebruiker vragen om te accepteren of weigeren. Zie [Android for Work-apparaatbeperkingsinstellingen in Microsoft Intune](device-restrictions-android-for-work.md) voor meer informatie.

#### <a name="define-app-specific-pin-for-android-for-work-devices----728976-1102534---"></a>Een app-specifieke pincode definiëren voor Android for Work-apparaten <!-- 728976, 1102534 -->

U kunt een wachtwoordcodebeleid definiëren dat alleen van toepassing is op apps in het werkprofiel voor apparaten met Android 7.0 en hoger die worden beheerd als een Android for Work-apparaat.  Opties zijn onder andere:

- Alleen een apparaatbreed wachtwoordcodebeleid definiëren: dit is de wachtwoordcode die de gebruiker moet gebruiken om het hele apparaat te ontgrendelen.
 Alleen een wachtwoordcodebeleid voor een werkprofiel definiëren: steeds wanneer gebruikers een app in het werkprofiel openen, worden ze gevraagd een wachtwoordcode in te voeren.
- Zowel een apparaat- als een werkprofielbeleid definiëren: de IT-beheer kan verschillende sterktes voor de wachtwoordcodes in het beleid voor apparaten en het beleid voor werkprofielen definiëren (bijvoorbeeld een pincode van vier cijfers om het apparaat te ontgrendelen, maar een pincode van zes cijfers om een werk-app te openen).

Zie [Android for Work-apparaatbeperkingsinstellingen in Microsoft Intune](device-restrictions-android-for-work.md) voor meer informatie.

> [!NOTE]
> Dit is alleen beschikbaar in Android 7.0 en later.  De eindgebruiker kan standaard de twee afzonderlijk gedefinieerde pincodes gebruiken, maar kan er ook voor kiezen om de twee gedefinieerde pincodes te combineren in de sterkste van de twee.

#### <a name="new-settings-for-windows-10-devices----978585---"></a>Nieuwe instellingen voor Windows 10-apparaten <!-- 978585 -->

Er zijn nieuwe [Instellingen beperkingen voor Windows-apparaten](device-restrictions-windows-10.md) toegevoegd. Hiermee worden zaken als draadloze beeldschermen, apparaatdetectie, het schakelen tussen taken en simkaartfoutberichten beheerd.

#### <a name="updates-to-certificate-configuration----918991-and-823198---"></a>Updates voor de certificaatconfiguratie <!-- 918991 and 823198 -->

Wanneer u een SCEP-certificaatprofiel maakt voor **indeling van de onderwerpnaam**, is de **aangepaste** optie beschikbaar voor iOS-, Android- en Windows-apparaten. Voor deze update was het veld **aangepast** beschikbaar voor iOS-apparaten. Zie [Een SCEP-certificaatprofiel maken] (certificates-scep-configure.md#how-to-create-a-scep-certificate-profile) voor meer informatie.

Wanneer u een PKCS certificaatprofiel maakt, is voor **Alternatieve naam voor onderwerp** het **Aangepaste Azure AD-kenmerk** beschikbaar. De optie **Afdeling** is beschikbaar wanneer u **Aangepast Azure AD-kenmerk** selecteert. Zie [Een PKCS-certificaatprofiel maken] (certficates-pfx-configure.md#how-to-create-a-pkcs-certificate-profile) voor meer informatie.

#### <a name="configure-multiple-apps-that-can-run-when-an-android-device-is-in-kiosk-mode----662059---"></a>Meerdere apps configureren die kunnen worden uitgevoerd wanneer een Android-apparaat in kioskmodus wordt uitgevoerd <!-- 662059 -->

Voorheen kon u slechts één app configureren die mocht worden uitgevoerd op een Android-apparaat dat in kioskmodus wordt uitgevoerd. U kunt nu meerdere apps configureren met de app-ID, de URL van de store of door een Android-app te selecteren die u al beheert. Zie [Instellingen voor kioskmodus](device-restrictions-android.md#kiosk) voor meer informatie.


## <a name="notices"></a>Mededelingen

### <a name="ip-addresses-for-intune-updated----1175274---"></a>IP-adressen voor Intune zijn bijgewerkt <!-- 1175274 -->

Een [Bijgewerkte lijst met DNS-namen en IP-adressen bijgewerkt](/intune/network-bandwidth-use) is beschikbaar voor de proxy-instellingen van de firewall.

### <a name="use-azure-active-directory-for-conditional-access----967947---"></a>Azure Active Directory gebruiken voor voorwaardelijke toegang <!-- 967947 -->

Voorwaardelijke toegang is beschikbaar in de sectie Azure Active Directory van de Azure-console en biedt een krachtiger en flexibeler kader voor het instellen van beleidsregels voor cloud-apps, zoals Office 365 Exchange Online en SharePoint Online.  Gebruik de blade **voorwaardelijke toegang in Azure Active Directory** voor het configureren van beleid in plaats van de klassieke Intune-beheerconsole. Bestaande beleidsregels in de klassieke Intune-beheerconsole moeten opnieuw worden gemaakt in de Azure-console. Zie [Beleid voor voorwaardelijke toegang voor Azure AD maken](/intune/conditional-access-exchange-create.md#create-azure-ad-conditional-access-policies-in-intune-azure-preview) voor meer informatie

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Rechtstreekse toegang tot Apple-scenario's voor inschrijving <!--951869-->

Voor Intune-accounts die na januari 2017 zijn gemaakt, heeft Intune rechtstreekse toegang ingeschakeld tot Apple-inschrijvingsscenario's. Hiervoor is de werkstroom voor het inschrijven van apparaten gebruikt in Azure Portal. Voorheen was de Apple-inschrijvingspreview alleen toegankelijk via koppelingen in de klassieke Intune-portal. Intune-accounts die vóór januari 2017 zijn gemaakt, moeten eenmalig worden gemigreerd om de functies in Azure beschikbaar te maken. De planning voor de migratie is nog niet aangekondigd, maar de informatie wordt zo snel mogelijk beschikbaar gemaakt. Het wordt aangeraden om een testaccount te maken om de nieuwe ervaring te testen, als u met uw bestaande account geen toegang hebt tot Azure Portal.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Beheerdersrollen die worden vervangen in Azure Portal

De bestaande MAM-beheerdersrollen (Mobile Application Management), namelijk Inzender, Eigenaar en Alleen-lezen, die in de klassieke Intune-portal (Silverlight) worden gebruikt, worden vervangen door een volledig nieuw op rollen gebaseerd toegangsbeheer in Intune Azure Portal. Wanneer u naar Azure Portal bent gemigreerd, moet u uw beheerders opnieuw toewijzen aan deze nieuwe beheerdersrollen. Zie [Op rollen gebaseerd toegangsbeheer voor Microsoft Intune](/intune/role-based-access-control) voor meer informatie over op rollen gebaseerd toegangsbeheer en de nieuwe rollen.

## <a name="whats-coming"></a>Binnenkort

### <a name="platform-support-reminder-windows-phone-81-mainstream-support-will-end-july-11-2017"></a>Herinnering voor platformondersteuning: de algemene ondersteuning voor Windows Phone 8.1 stopt op 11 juli 2017
<!-- 1327781 -->

Op 11 juli 2017 stopt de algemene ondersteuning voor het Windows Phone 8.1-platform. De ondersteuning voor Windows 8.1 voor pc's loopt gewoon door.

Er zijn geen directe gevolgen voor een apparaat met Windows Phone 8.1 dat wordt beheerd door de Intune-service. Apparaten die zijn ingeschreven, blijven gewoon werken en alle beleidsregels, configuraties en apps blijven eveneens werken zoals verwacht. Het is wel zo dat er geen verbeteringen meer worden aangebracht aan het Windows Phone 8.1-platform in de Intune-service, en evenmin voor de Intune-bedrijfsportal-app voor Windows Phone 8.1. 

Het is raadzaam om in aanmerking komende Windows Phone 8.1-apparaten zo snel mogelijk te upgraden naar Windows 10 Mobile. 

### <a name="changes-in-support-for-the-intune-ios-company-portal-app-----1164474----"></a>Wijzigingen in de ondersteuning van de Intune-bedrijfsportal-app voor iOS  <!-- 1164474  -->


Binnen afzienbare tijd zal er een nieuwe versie van de Microsoft Intune-bedrijfsportal-app voor iOS uitkomen die alleen nog werkt met apparaten met iOS 9.0 of hoger. De versie van de bedrijfsportal die ondersteuning biedt voor iOS 8 zal nog maar voor zeer korte tijd beschikbaar zijn. Als u echter ook iOS-apps met MAM-functionaliteit gebruikt, is iOS 9.0 en hoger vereist. Het is dus belangrijk om te controleren of uw eindgebruikers zijn bijgewerkt naar de nieuwste versie van het besturingssysteem. 

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Hoewel er nog geen specifieke datums bekend zijn, melden we dit nu al zodat u genoeg tijd hebt om de update te plannen. Zorg ervoor dat uw gebruikers een update uitvoeren naar iOS 9 of hoger. Op het moment dat de nieuwe versie van de Intune-bedrijfsportal-app uitkomt, moeten uw eindgebruikers de bedrijfsportal-app bijwerken.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?

Vertel uw gebruikers dat ze een update moeten uitvoeren naar iOS 9.0 of hoger om optimaal gebruik te kunnen maken van nieuwe Intune-functies.  Vertel uw gebruikers dat ze de nieuwe versie van de bedrijfsportal moeten installeren om toegang te krijgen tot de nieuwe functies van de portal.

Ga naar de Intune-portal in Azure en kies Apparaten > Alle apparaten. Filter op iOS-versie om apparaten te zien met een oudere versie dan iOS 9.

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Verbeterde aanmeldervaring in de bedrijfsportal-apps voor alle platformen <!--User Story 1132123-->

Dit is de aankondiging van een wijziging die in de komende maanden wordt geïntroduceerd en waarmee de aanmeldervaring wordt verbeterd voor apps in de Intune-bedrijfsportal voor Android, iOS en Windows. De nieuwe gebruikerservaring wordt automatisch toegepast op alle platformen voor de bedrijfsportal-app wanneer deze wijziging wordt doorgevoerd in Azure AD. Bovendien kunnen gebruikers nu zich aanmelden bij de bedrijfsportal vanaf een ander apparaat met een gegenereerde code voor eenmalig gebruik. Dit is vooral nuttig in gevallen wanneer gebruikers zich moeten aanmelden zonder referenties.

Zie [Wat is er nieuw in de app-interface](/intune/whats-new-app-ui) voor schermafbeeldingen van de vorige aanmeldingservaring, de nieuwe aanmeldingservaring met referenties en de nieuwe aanmeldingservaring vanaf een ander apparaat.

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Geplande wijziging: Intune verandert in de Intune Partner Portal-ervaring<!-- 1050016 -->

De pagina Intune Partner wordt verwijderd uit manage.microsoft.com die begint met de service-update halverwege mei 2017.  

Als u een partnerbeheerder bent, kunt u niet langer weergeven of actie ondernemen namens uw klanten vanaf de pagina Intune Partner. U moet zich aanmelden bij een van de twee andere partnerportals bij Microsoft.

U kunt zich bij het [Microsoft Partner Center](https://partnercenter.microsoft.com/) en het [Microsoft Office 365-partnerbeheercentrum](https://portal.office.com/) aanmelden bij de klantaccounts die u beheert. Gebruik in de toekomst als partner een van deze sites voor het beheren van uw klanten.


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple vereist updates voor Application Transport Security <!--748318-->

Apple heeft aangekondigd dat specifieke vereisten gaan gelden voor Application Transport Security (ATS). ATS wordt gebruikt om betere beveiliging af te dwingen voor alle app-communicatie die verloopt via HTTPS. Deze wijziging heeft gevolgen voor Intune-klanten die de bedrijfsportal-app gebruiken op iOS.

Een versie van de bedrijfsportal-app is beschikbaar gemaakt voor iOS via het Apple TestFlight-programma waarmee naleving van de nieuwe ATS-vereisten wordt afgedwongen. Als u dit wilt proberen zodat u uw ATS-compatibiliteit kunt testen, stuurt u een e-mail naar <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app"> CompanyPortalBeta@microsoft.com </a> met uw voornaam, achternaam, e-mailadres en bedrijfsnaam. Bekijk ons [Intune-ondersteuningsblog](https://aka.ms/compportalats) voor meer informatie.

### <a name="see-also"></a>Zie tevens
* [Microsoft Intune-blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Roadmap voor cloudplatform](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Wat is er nieuw in de gebruikersinterface van de bedrijfsportal?](whats-new-app-ui.md)
* [Wat was er in de vorige maanden nieuw](whats-new-archive.md)
