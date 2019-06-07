---
title: Nieuwe functies in Microsoft Intune - Azure | Microsoft Docs
titleSuffix: ''
description: Ontdekken wat er nieuw is in Intune Azure Portal
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/31/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 72b96714e8740fe4077583cfa5d9f148c2ee0908
ms.sourcegitcommit: f41b22f65286a64a8002e2cbe80debfdd6692278
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/03/2019
ms.locfileid: "66469584"
---
# <a name="whats-new-in-microsoft-intune"></a>Wat is er nieuw in Microsoft Intune?

Ontdek elke week wat er nieuw is in Microsoft Intune. U vindt hier ook [geplande wijzigingen](in-development.md), [belangrijke kennisgevingen](#notices) en informatie over [oudere releases](whats-new-archive.md). 

> [!Note]
> Sommige functies worden gedurende een aantal weken geïmplementeerd en zijn mogelijk niet voor alle gebruikers in de eerste week beschikbaar.

**RSS-feed**: ontvang een melding wanneer deze pagina wordt bijgewerkt door de volgende URL in uw feedlezer te kopiëren en plakken: `https://docs.microsoft.com/api/search/rss?search=%22What%27s+new+in+microsoft+intune%3F+-+Azure%22&locale=en-us`

<!-- Common categories:  
### App management
### Device configuration
### Device enrollment
### Device management
### Intune apps
### Monitor and troubleshoot
### Role-based access control

-->  

<!-- ########################## -->

## <a name="week-of-may-27-2019"></a>Week van 27 mei 2019 

### <a name="app-management"></a>Appbeheer

#### <a name="reporting-for-potentially-harmful-apps-on-android-devices----4223162---"></a>Rapportage voor mogelijk schadelijke apps op Android-apparaten <!-- 4223162 -->
Intune biedt nu aanvullende rapportagegegevens over mogelijk schadelijke apps op Android-apparaten. 

## <a name="week-of-may-20-2019"></a>Week van 20 mei 2019 

### <a name="app-management"></a>Appbeheer

#### <a name="windows-company-portal-app----3316993---"></a>Windows-bedrijfsportal-app <!-- 3316993 -->
De Windows-bedrijfsportal-app heeft nu een nieuwe pagina met het label **Apparaten**. Op de pagina **Apparaten** staan de eindgebruikers van alle ingeschreven apparaten. Gebruikers zien deze wijziging in de bedrijfsportal als ze versie 10.3.4291.0 of hoger gebruiken. Voor informatie over het configureren van de bedrijfsportal-app, ziet u [How to configure the Microsoft Intune Company Portal app](company-portal-app.md) (De app Microsoft Intune-bedrijfsportal configureren).

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="autopilot-device-orderid-attribute-name-changed-to-group-tag----4659453---"></a>De kenmerknaam OrderID voor Autopilot-apparaten is gewijzigd in Groepstag <!-- 4659453 -->

Voor een meer intuïtieve benadering is de kenmerknaam **OrderID** voor Autopilot-apparaten gewijzigd in **Groepstag**. Als u CSV's gebruikt voor het uploaden van Autopilot-apparaatgegevens, moet u Groepstag als kolomkop gebruiken en niet OrderID.  

## <a name="week-of-may-13-2019"></a>Week van 13 mei 2019 

### <a name="app-management"></a>Appbeheer

#### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359-idready-wnready--"></a>Intune-beleid werkt de verificatiemethode en installatie van de Bedrijfsportal-app bij  <!-- 1927359 idready wnready-->
Intune biedt geen ondersteuning meer voor de Bedrijfsportal wanneer deze handmatig door eindgebruikers uit de appstore wordt geïnstalleerd op apparaten die al met behulp van Configuratieassistent zijn ingeschreven via een van de Apple-registratiemethoden voor bedrijfsapparaten. Deze wijziging is alleen relevant wanneer u tijdens de inschrijving verifieert met Apple Setup Assistant. Deze wijziging is eveneens alleen van invloed op iOS-apparaten die zijn ingeschreven via:  
* Apple Configurator

* Apple Business Manager

* Apple School Manager

* Apple Device Enrollment Program (DEP)

Als gebruikers de Bedrijfsportal-app installeren uit de App Store en vervolgens apparaten via de app proberen te registreren, treedt er een foutmelding op. Er wordt van uitgegaan dat deze apparaten de Bedrijfsportal alleen gebruiken wanneer het automatisch door Intune tijdens de registratie is gepusht. Inschrijvingsprofielen in Intune in de Azure-portal worden bijgewerkt zodat u kunt opgeven hoe apparaten zich verifiëren en hoe zij de Bedrijfsportal-app ontvangen. Als u wilt dat uw DEP-apparaatgebruikers de Bedrijfsportal hebben, moet u uw voorkeuren in een inschrijvingsprofiel opgeven. 

Bovendien wordt het scherm **Uw apparaat identificeren** in de Bedrijfsportal-app van iOS binnenkort niet meer gebruikt. Beheerders die voorwaardelijke toegang willen inschakelen of bedrijfs-apps willen implementeren moeten daarom het DEP-inschrijvingsprofiel bijwerken. Deze vereiste geldt alleen als de DEP-inschrijving wordt geverifieerd met Configuratieassistent. In dat geval moet u de Bedrijfsportal naar het apparaat pushen. Hiervoor kiest u **Intune** > **Apparaatinschrijving** > **Apple-inschrijving** > **Tokens voor het inschrijfprogramma** > kies een token > **Profielen** > kies een profiel > **Eigenschappen** > stel **Bedrijfsportal installeren** in op **Ja**.

Als u de Bedrijfsportal wilt installeren op DEP-apparaten die al zijn ingeschreven, gaat u naar Intune > Client-apps en pusht u de app als beheerde app met app-configuratiebeleid. 

#### <a name="configure-how-end-users-update-a-line-of-business-lob-app-using-an-app-protection-policy----3568384---"></a>Configureren hoe eindgebruikers een LOB-app (Line-Of-Business) bijwerken met behulp van een beveiligingsbeleid voor apps <!-- 3568384 -->
U kunt nu configureren waar uw eindgebruikers een bijgewerkte versie van een LOB-app (Line-Of-Business) kunnen downloaden. Eindgebruikers zien deze functie in het dialoogvenster **minimale app-versie** van de functie voor voorwaardelijk starten, waarin eindgebruikers wordt gevraagd om bij te werken naar een minimale versie van de LOB-app. U moet deze informatie opgeven als onderdeel van uw het beveiligingsbeleid voor uw LOB-app (APP). Deze functie is beschikbaar voor iOS en Android. Voor iOS vereist deze functie dat de app is geïntegreerd (of verpakt met behulp van het wrapping-programma) met de Intune SDK voor iOS versie 10.0.7 of hoger. Voor Android vereist deze functie de meest recente versie van de Bedrijfsportal. Als u wilt configureren hoe een eindgebruiker een LOB-app kan bijwerken, moet er configuratiebeleid voor een beheerde app worden verzonden naar de app met de sleutel `com.microsoft.intune.myappstore`. De verzonden waarde bepaalt uit welke store de eindgebruiker de app kan downloaden. Als de app wordt geïmplementeerd via de Bedrijfsportal-app, moet de waarde `CompanyPortal` zijn. Voor iedere andere store moet u een volledige URL opgeven.

#### <a name="intune-management-extension-powershell-scripts-----3734186-idready---"></a>Intune-beheerextensie voor PowerShell-scripts  <!-- 3734186 idready -->
U kunt configureren dat PowerShell-scripts worden uitgevoerd met de beheerdersbevoegdheden van de gebruiker op het apparaat. Zie [PowerShell-scripts op Windows 10-apparaten gebruiken in Intune](intune-management-extension.md) en [Win32 app management](apps-win32-app-management.md) (Beheer van Win32-apps) voor meer informatie.

#### <a name="android-enterprise-app-management----4459905---"></a>Beheer van Android Enterprise-apps <!-- 4459905 -->
Om het eenvoudiger te maken voor IT-beheerders om Android Enterprise-beheer te configureren en gebruiken, voegt Intune automatisch vier veelgebruikte Android Enterprise apps toe aan de beheerconsole van Intune. Het betreft de volgende vier Android Enterprise-apps:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)** : wordt gebruikt voor scenario's met volledig beheer door Android Enterprise.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)** : helpt om u aan te melden bij uw accounts als u tweeledige verificatie gebruikt.
- **[Intune-bedrijfsportal](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)** : wordt gebruikt voor beleidsregels voor app-beveiliging (APP) en werkprofielscenario's van Android Enterprise.
- [Managed Home Screen](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise): wordt gebruikt voor toegewezen/kiosk-scenario's van Android Enterprise.

Eerder moesten IT-beheerders deze apps als onderdeel van de installatie handmatig zoeken en goedkeuren in de [beheerde Google Play Store](https://play.google.com/store/apps). Met deze wijziging worden deze eerdere handmatige stappen weggenomen om het gemakkelijker en sneller te maken voor klanten om Android Enterprise-beheer te gebruiken.

Deze vier apps worden automatisch toegevoegd aan de lijst met Intune-apps van beheerders op het moment dat ze hun Intune-tenant voor het eerst verbinden met de beheerde Google Play Store. Zie [Uw Intune-account verbinden met uw Beheerde Google Play-account](connect-intune-android-enterprise.md) voor meer informatie. Beheerders die hun tenant al hebben verbonden of die al gebruikmaken van Android Enterprise hoeven niets te doen. Deze vier apps komen automatisch beschikbaar, binnen maximaal zeven dagen na het voltooien van de implementatie van de service-update van mei 2019.

### <a name="device-configuration"></a>Apparaatconfiguratie

####  <a name="intune-security-tasks-for-defender-atp-in-public-preview--------3208597---"></a>Intune-beveiligingstaken voor Defender ATP (in openbare preview)     <!-- 3208597 -->
In de openbare preview kunt u Intune gebruiken voor het beheren van beveiligingstaken voor Microsoft Defender Advanced Threat Protection (ATP). Door deze integratie met ATP wordt er een op risico's gebaseerde aanpak voor het detecteren, classificeren en oplossen van beveiligingsproblemen en onjuiste configuraties van eindpunten toegevoegd, terwijl er ook minder tijd zit tussen het detecteren en oplossen van beveiligingsproblemen.

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---idstaged--"></a>Controleren of er zich een TPM-chipset in een nalevingsbeleid voor Windows 10-apparaten bevindt <!-- 3617671   idstaged-->
Veel apparaten met Windows 10 en hoger hebben TPM-chipsets (Trusted Platform Module). Deze update bevat een nieuwe nalevingsinstelling die de versie van de TPM-chip in het apparaat controleert. 

Deze instelling wordt beschreven in [Instellingen voor nalevingsbeleid voor apparaten met Windows 10 en later](compliance-policy-create-windows.md#device-security).

Van toepassing op: Windows 10 en hoger

#### <a name="prevent-end-users-from-modifying-their-personal-hotspot-and-disable-siri-server-logging-on-ios-devices----4097904-----"></a>Voorkomen dat gebruikers hun persoonlijke hotspot wijzigen en logboekregistratie van Siri-server op iOS-apparaten uitschakelen <!-- 4097904   --> 
U maakt een profiel met apparaatbeperkingen op het iOS-apparaat (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype). Deze update bevat nieuwe instellingen die u kunt configureren:

- **Ingebouwde apps**: logboekregistratie op de server voor Siri-opdrachten
- **Draadloos**: wijzing van persoonlijke hotspot door gebruiker (alleen onder supervisie)

Als u deze instellingen wilt zien, gaat u naar [ingebouwde app-instellingen voor iOS](device-restrictions-ios.md#built-in-apps) en [draadloze instellingen voor iOS](device-restrictions-ios.md#wireless).

Van toepassing op: iOS 12.2 en nieuwer

#### <a name="new-classroom-app-device-restriction-settings-for-macos-devices----4097905-----"></a>Nieuwe instellingen voor apparaatbeperkingen voor Klaslokaal-app op macOS-apparaten <!-- 4097905   --> 
U kunt apparaatconfiguratieprofiel voor macOS-apparaten maken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **macOS** voor platform > **Apparaatbeperkingen** voor profieltype). Deze update bevat nieuwe instellingen voor de Klaslokaal-app, de optie om schermopnamen te blokkeren en de optie om de iCloud-fotobibliotheek uit te schakelen.

Als u de huidige instellingen wilt zien, gaat u naar [macOS-apparaatinstellingen voor het toestaan of beperken van functies met Intune](device-restrictions-macos.md).

Is van toepassing op: macOS

#### <a name="the-ios-password-to-access-app-store-setting-is-renamed---4557891----"></a>De naam van het iOS-wachtwoord voor toegang tot App Store-instellingen is gewijzigd<!-- 4557891  -->
De naam van de instelling **Wachtwoord voor toegang tot de App Store** is gewijzigd in **iTunes Store-wachtwoord vereisen voor alle aankopen** (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype > **App Store, documenten bekijken, gamen**).

Als u de beschikbare instellingen wilt zien, gaat u naar [App Store, documenten bekijken, gamen](device-restrictions-ios.md#app-store-doc-viewing-gaming).

Van toepassing op: iOS

####  <a name="microsoft-defender-advanced-threat-protection--baseline--preview------3754134---"></a>Microsoft Defender Advanced Threat Protection-basislijn (preview)  <!--  3754134 -->
We hebben een preview van een basislijn voor beveiliging toegevoegd voor [Microsoft Defender Advanced Threat Protection](security-baseline-settings-defender-atp.md)-instellingen. Deze basislijn is beschikbaar als uw omgeving voldoet aan de vereisten voor het gebruik van [Microsoft Defender Advanced Threat Protection](advanced-threat-protection.md#prerequisites).

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="windows-enrollment-status-page-esp-is-now-generally-available----3605348---"></a>Pagina Status van inschrijving is nu algemeen beschikbaar <!-- 3605348 -->
De pagina Status van inschrijving is nu uit preview en algemeen beschikbaar. Raadpleeg [Een pagina voor de status van de inschrijving instellen](windows-enrollment-status.md) voor meer informatie.


#### <a name="intune-user-interface-update---autopilot-enrollment-profile-creation-----4593669---"></a>Update van Intune-gebruikersinterface - Autopilot-inschrijvingsprofiel maken  <!-- 4593669 -->
De gebruikersinterface voor het maken van een Autopilot-inschrijvingsprofiel is bijgewerkt om deze in lijn te brengen met de stijlen van de Azure-gebruikersinterface. Zie [Create an Autopilot enrollment profile](https://docs.microsoft.com/intune/enrollment-autopilot#create-an-autopilot-deployment-profile) (Een Autopilot-inschrijvingsprofiel maken) voor meer informatie. Binnenkort worden ook andere Intune-scenario's bijgewerkt naar deze nieuwe stijl voor de gebruikersinterface.

#### <a name="enable-autopilot-reset-for-all-windows-devices----4225665---"></a>Autopilot opnieuw instellen voor alle Windows-apparaten inschakelen <!-- 4225665 -->
Autopilot opnieuw instellen werkt nu voor alle Windows-apparaten, ook als deze niet zijn geconfigureerd voor het gebruik van de pagina Status van inschrijving. Als er tijdens de eerste apparaatregistratie geen pagina voor de status van inschrijving is geconfigureerd voor het apparaat, wordt op het apparaat direct het bureaublad weergegeven na het aanmelden. Het duurt maximaal acht uur totdat de synchronisatie is voltooid en het apparaat als compatibel wordt weergegeven in Intune. Zie [Reset devices with remote Windows Autopilot Reset](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-reset-remote) (Apparaten op afstand opnieuw instellen met Autopilot opnieuw instellen van Windows) voor meer informatie.

#### <a name="exact-imei-format-not-required-when-searching-all-devices---30407680---"></a>Exacte IME-indeling niet vereist bij het zoeken naar alle apparaten <!--30407680 -->
U hoeft geen spaties op te nemen in IMEI-nummers wanneer u zoekt met **Alle apparaten**.

#### <a name="deleting-a-device-in-the-apple-portal-will-be-reflected-in-the-intune-portal---2489996---"></a>Verwijderen van apparaat in de Apple-portal wordt doorgevoerd in de Intune-portal <!--2489996 -->
Als een apparaat wordt verwijderd uit de portal van het Device Enrollment Program van Apple of van Apple Business Manager, wordt het apparaat bij de volgende synchronisatie automatisch verwijderd uit Intune.

### <a name="the-enrollment-status-page-now-tracks-win32-apps----2714451---"></a>Op de pagina Status van inschrijving worden nu Win32-apps bijgehouden <!-- 2714451 -->
Dit is alleen van toepassing op apparaten met Windows 10 versie 1903 en hoger. Raadpleeg [Een pagina voor de status van de inschrijving instellen](windows-enrollment-status.md) voor meer informatie.

### <a name="device-management"></a>Apparaatbeheer

#### <a name="reset-and-wipe-devices-in-bulk-by-using-the-graph-api----3295288---"></a>Apparaten in bulk opnieuw instellen en wissen met behulp van de Graph API <!-- 3295288 -->
U kunt nu in één bulkbewerking tot wel 100 apparaten opnieuw instellen en wissen met behulp van de Graph API.


### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="the-encryption-report-is-out-of-public-preview------4587546--------"></a>Het rapport Versleuteling is uit openbare preview   <!-- 4587546      -->
Het [rapport voor BitLocker- en apparaatversleuteling](encryption-monitor.md) is nu algemeen beschikbaar en maakt geen deel meer uit van de openbare preview. 

<!-- ########################## -->

#### <a name="outlook-signature-and-biometric-settings-for--ios-and-android-devices----4050557---"></a>Outlook-handtekening en biometrische instellingen voor iOS- en Android-apparaten <!-- 4050557 -->
U kunt nu opgeven of de standaardhandtekening moet worden ingeschakeld in Outlook voor iOS- en Android-apparaten. Bovendien kunt u eventueel toestaan dat gebruikers de biometrische instelling wijzigen in Outlook voor iOS.

## <a name="week-of-may-6-2019"></a>Week van 6 mei 2019 

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="network-access-control-nac-support-for-f5-access-for-ios-devices----4500808---"></a>Ondersteuning voor netwerktoegangsbeheer (NAC) voor F5 Access voor iOS-apparaten <!-- 4500808 -->

F5 heeft een update voor BIG-IP 13 uitgebracht waardoor de NAC-functionaliteit is toegestaan voor F5-toegang op iOS in Intune. Om deze functie te gebruiken, moet u ook het volgende doen:

- Werk BIG-IP bij naar 13.1.1.5, vernieuwen. BIG-IP 14 wordt niet ondersteund.
- Integreer BIG-IP met Intune voor NAC. Stappen in [Overzicht: APM configureren voor apparaatpostuurcontroles met eindpuntbeheersystemen](https://support.f5.com/kb/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html#guid-0bd12e12-8107-40ec-979d-c44779a8cc89).
- Schakel de instelling **Netwerktoegangsbeheer (NAC) inschakelen** in het VPN-profiel in Intune in.

Ga naar [VPN-instellingen configureren op iOS-apparaten](vpn-settings-ios.md) om de beschikbare instelling te zien.

Van toepassing op: iOS

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune----doc-vso-1521237----"></a>Bijgewerkte PFX-certificaatconnector voor Microsoft Intune <!-- doc-vso 1521237  -->  
We hebben een update uitgebracht voor de [PFX-certificaatconnector voor Microsoft Intune](certficates-pfx-configure.md#whats-new-for-connectors), waardoor de polling-interval wordt verlaagd van 5 minuten naar 30 seconden.

## <a name="week-of-april-22-2019"></a>Week van 22 april 2019

### <a name="use-compliance-manager-to-create-assessments-for-microsoft-intune---4404750---"></a>Met behulp van Conformiteitsmanager een evaluatie voor Microsoft Intune maken<!-- 4404750 -->

[Conformiteitsmanager](https://servicetrust.microsoft.com/ComplianceManager) (hiermee opent u een andere Microsoft-website) is een hulpprogramma voor op werkstromen gebaseerde risicoanalyses in Microsoft Service Trust Portal. Hiermee kunt u activiteiten van uw organisatie op het gebied van naleving van regelgeving met betrekking tot Microsoft-services bijhouden, toewijzen en verifiëren. U kunt uw eigen nalevingsevaluatie maken met Office 365, Azure, Dynamics, Professional-Services en Intune. Intune heeft twee evaluaties beschikbaar - FFIEC en AVG.

Met Conformiteitsmanager kunt u uw inspanningen richten door besturingselementen in te delen: besturingselementen die worden beheerd door Microsoft en besturingselementen die worden beheerd door uw organisatie. U kunt de evaluaties uitvoeren en deze vervolgens exporteren en afdrukken.

[FFIEC-compliance (FFIEC: Federal Financial Institutions Examination Council)](https://www.microsoft.com/trustcenter/compliance/FFIEC) (hiermee opent u een andere Microsoft-website) is een verzameling standaarden voor internetbankieren die is uitgegeven door FFIEC. Het is de meest aangevraagde evaluatie voor financiële instellingen die gebruikmaken van Intune. Deze biedt een interpretatie van de wijze waarop u met behulp van Intune kunt voldoen aan de FFIEC-richtlijnen voor cyberbeveiliging met betrekking tot workloads in de openbare cloud. De FFIEC-evaluatie van Intune is de tweede FFIEC-evaluatie in Conformiteitsmanager.

In het volgende voorbeeld ziet u de indeling van FFIEC-besturingselementen. Microsoft gaat over 64-besturingselementen. U bent verantwoordelijk voor de resterende 12 besturingselementen.

![Bekijk een voorbeeld van een Intune-evaluatie voor FFIEC, met inbegrip van de acties van de klant en van Microsoft](./media/intune-ffiec-assessment-status.png)

[AVG (Algemene Verordening Gegevensbescherming)](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-overview) (hiermee opent u een andere Microsoft-website) is een wet van de Europese Unie (EU) waarmee de rechten van personen en hun gegevens worden beschermd. De AVG is de meest aangevraagde evaluatie om te voldoen aan privacy-regelgeving. 

In het volgende voorbeeld ziet u de indeling van AVG-besturingselementen. Microsoft gaat over 49-besturingselementen. U bent verantwoordelijk voor de resterende 66 besturingselementen.

![Bekijk een voorbeeld van een Intune-evaluatie voor AVG, met inbegrip van de acties van de klant en van Microsoft](./media/intune-assessment-status.png)

## <a name="week-of-april-15-2019"></a>Week van 15 april 2019

### <a name="app-management"></a>Appbeheer

#### <a name="openssl-encryption-for-android-app-protection-policies----3747362---"></a>OpenSSL-versleuteling voor app-beveiligingsbeleid voor Android <!-- 3747362 -->
Intune app-beveiligingsbeleid (APP) op Android-apparaten maakt nu gebruik van een OpenSSL-versleutelingsbibliotheek die compatibel is met FIPS 140-2. Zie de sectie over [versleuteling](app-protection-policy-settings-android.md#encryption) van [instellingen van app-beveiligingsbeleid voor Android in Microsoft Intune](app-protection-policy-settings-android.md) voor meer informatie.

#### <a name="enable-win32-app-dependencies----2617348----"></a>Win32-app-afhankelijkheden inschakelen <!-- 2617348  -->
Als beheerder kunt u vereisen dat andere apps worden geïnstalleerd als afhankelijkheden voordat uw Win32-app wordt geïnstalleerd. Op het apparaat moet(e) met name de afhankelijke app(s) worden geïnstalleerd voordat de Win32-app wordt geïnstalleerd. Selecteer in Intune, **Client-apps** > **Apps** > **Toevoegen** om de blade **App toevoegen** weer te geven. Selecteer **Windows-app (Win32)** als **App-type**. Nadat u de app hebt toegevoegd, kunt u **Afhankelijkheden** selecteren om de afhankelijke apps toe te voegen die moeten worden geïnstalleerd voordat de Win32-app kan worden geïnstalleerd. Zie [Intune Standalone - Win32-app-beheer](apps-win32-app-management.md) voor meer informatie. 

#### <a name="app-version-installation-information-for-microsoft-store-for-business-apps----3537391-----"></a>Installatie-informatie voor de app-versie voor Microsoft Store voor Bedrijven-apps <!-- 3537391   -->
App-installatierapporten bevatten informatie over de app-versie voor Microsoft Store voor bedrijven-apps. Selecteer in Intune **Client-apps** > **Apps**. Selecteer een **Microsoft Store voor bedrijven-app** en selecteer vervolgens **Installatiestatus apparaat** onder de sectie **Monitor**.

#### <a name="additions-to-win32-apps-requirement-rules----3676883-----"></a>Toevoegingen aan de vereisteregels voor Win32-apps <!-- 3676883   -->
U kunt vereisteregels maken op basis van PowerShell-scripts, registerwaarden en informatie over het bestandssysteem. Selecteer in Intune de optie **Client-apps** > **Apps** > **Toevoegen**. Selecteer vervolgens **Windows-app (Win32)** als **App-type** in de blade **App toevoegen**.  Selecteer **Vereisten** > **Toevoegen** om aanvullende vereisteregels te configureren. Selecteer vervolgens een **Bestandstype**, **Register** of **Script** als **Vereistetype**. Zie [Win32 app-beheer](apps-win32-app-management.md) voor meer informatie.

 #### <a name="configure-your-win32-apps-to-be-installed-on-intune-enrolled-azure-ad-joined-devices----3695227----"></a>Uw Win32-apps configureren voor een installatie op bij Intune ingeschreven apparaten die met Azure AD zijn gekoppeld <!-- 3695227  -->
U kunt uw Win32-apps toewijzen voor een installatie op bij Intune ingeschreven apparaten die met Azure AD zijn gekoppeld. Zie [Win32-app-beheer](apps-win32-app-management.md) voor meer informatie over Win32-apps in Intune.

#### <a name="device-overview-shows-primary-user---794259----"></a>Overzicht van apparaat geeft de primaire gebruiker weer <!--794259  -->
In de overzichtspagina van het apparaat ziet u de primaire gebruiker, ook wel de UDA-gebruiker genoemd (UDA: User Device Affinity, gebruikersaffiniteit apparaat). Als u de primaire gebruiker van een apparaat wilt zien, kiest u **Intune** > **Apparaten** > **Alle apparaten** > Een apparaat kiezen. De primaire gebruiker wordt bovenaan de pagina **Overzicht** weergegeven.

#### <a name="additional-managed-google-play-app-reporting-for-android-enterprise-work-profile-devices----4105925----"></a>Aanvullende rapportage van beheerde Google Play-apps voor apparaten met Android Enterprise-werkprofiel <!-- 4105925  -->
Voor beheerde Google Play-apps die op apparaten met Android Enterprise-werkprofiel zijn geïmplementeerd, kunt u het specifieke versienummer van de op een apparaat geïnstalleerde app weergeven. Dit geldt alleen voor vereiste apps.  

#### <a name="ios-third-party-keyboards----4111843-----"></a>iOS-toetsenborden van derden <!-- 4111843   -->
De ondersteuning voor het Intune-app-beveiligingsbeleid (APP) voor de instelling **Toetsenborden van derden** voor iOS wordt beëindigd vanwege een iOS-platformwijziging. U zult deze instelling niet meer kunnen configureren op de Intune-beheerconsole en deze wordt niet meer afgedwongen op de client in de Intune App SDK.

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="set-login-settings-and-control-restart-options-on-macos-devices----1210083----"></a>Aanmeldingsinstellingen configureren en opties voor opnieuw opstarten beheren op macOS-apparaten <!-- 1210083  -->
U kunt op macOS-apparaten een apparaatconfiguratieprofiel maken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **macOS** kiezen als platform > **Apparaatfuncties** als profieltype). Deze update bevat nieuwe aanmeldingsvensterinstellingen, zoals het weergeven van een aangepaste banner, het kiezen hoe gebruikers zich aanmelden, het weergeven of verbergen van de energie-instellingen enzovoort.

Zie [Instellingen van macOS-apparaatfuncties](macos-device-features-settings.md) voor het bekijken van deze instellingen.

#### <a name="configure-wifi-on-android-enterprise-device-owner-dedicated-devices-running-in-multi-app-kiosk-mode---3041940----"></a>Wi-Fi configureren op aan de apparaateigenaar toegewezen Android Enterprise-apparaten die worden uitgevoerd in de kioskmodus voor meerdere apps <!--3041940  -->
U kunt de instellingen voor Android Enterprise-apparaateigenaar inschakelen wanneer deze als toegewezen apparaat in kioskmodus voor meerdere apps wordt uitgevoerd. In deze update kunt u gebruikers in staat stellen om Wi-Fi-netwerken te configureren en ermee verbinding te maken (**Intune** > **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** als platform > **Alleen apparaateigenaar, Apparaatbeperkingen** als profieltype >  **Toegewezen apparaten** > **Kioskmodus**: **Voor meerdere apps** > **Wi-Fi-configuratie**). 

Ga naar [Met Android Enterprise-apparaatinstellingen functies toestaan of beperken](device-restrictions-android-for-work.md) als u alle configureerbare instellingen wilt bekijken.

Van toepassing op: aan Android Enterprise toegewezen apparaten die worden uitgevoerd in de kioskmodus voor meerdere apps


#### <a name="configure-bluetooth-and-pairing-on-android-enterprise-device-owner-dedicated-devices-running-in-multi-app-kiosk-mode----3041941----"></a>Bluetooth en koppelen configureren op aan apparaateigenaar toegewezen Android Enterprise-apparaten die worden uitgevoerd in de kioskmodus voor meerdere apps <!-- 3041941  -->
U kunt de instellingen voor Android Enterprise-apparaateigenaar inschakelen wanneer deze als toegewezen apparaat in kioskmodus voor meerdere apps wordt uitgevoerd. In deze update kunt u gebruikers toestaan om Bluetooth in te schakelen en via Bluetooth apparaten te koppelen (**Intune** > **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** als platform > **Alleen apparaateigenaar, Apparaatbeperkingen** als profieltype >  **Toegewezen apparaten** > **Kioskmodus**: **Voor meerdere apps** > **Bluetooth-configuratie**). 

Ga naar [Met Android Enterprise-apparaatinstellingen functies toestaan of beperken](device-restrictions-android-for-work.md) als u alle configureerbare instellingen wilt bekijken.

Van toepassing op: aan Android Enterprise toegewezen apparaten die worden uitgevoerd in de kioskmodus voor meerdere apps

#### <a name="create-and-use-oemconfig-device-configuration-profiles-in-intune----3305883----"></a>OEMConfig-apparaatconfiguratieprofielen in Microsoft Intune maken en gebruiken <!-- 3305883  -->
In deze update biedt Intune ondersteuning voor het configureren van Android Enterprise-apparaten met OEMConfig. U kunt specifiek een apparaatconfiguratieprofiel maken, en instellingen toepassen op Android Enterprise-apparaten met behulp van OEMConfig (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** als platform).

Ondersteuning voor OEM's is momenteel per OEM. Als de gewenste OEMConfig app niet beschikbaar is in de lijst met OEMConfig-apps, neemt u contact op met `IntuneOEMConfig@microsoft.com`.

Ga naar [Android-bedrijfsapparaten met OEMConfig gebruiken en beheren in Microsoft Intune](android-oem-configuration-overview.md) voor meer informatie over deze functie.

Van toepassing op: Android Enterprise

#### <a name="windows-update-notifications-----3316758-3316782----"></a>Windows Update-meldingen  <!-- 3316758, 3316782  -->
We hebben twee *instellingen voor de gebruikerservaring* toegevoegd aan de Windows Update-ringconfiguraties die u vanuit de Intune-console kunt beheren. U kunt nu het volgende doen:
- Gebruikers weigeren of toestaan om [te scannen op Windows-updates](windows-update-settings.md#block-user-from-scanning-for-windows-updates).
- Het [meldingsniveau van Windows Update](windows-update-settings.md#windows-update-notification-level) dat gebruikers zien, beheren.

#### <a name="new-device-restriction-settings-for-android-enterprise-device-owner----3574254----"></a>Nieuwe apparaatbeperkingsinstellingen voor Android Enterprise-apparaateigenaar <!-- 3574254  -->
Op Android Enterprise-apparaten kunt u een profiel voor apparaatbeperking maken om functies toe te staan of te beperken en regels voor wachtwoorden in te stellen (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > Kies **Android Enterprise** als platform > **Alleen apparaateigenaar > Apparaatbeperkingen** als profieltype). 

Deze update bevat nieuwe wachtwoordinstellingen, verleent volledige toegang tot apps in de Google Play Store voor volledig beheerde apparaten enzovoort. Ga naar [Met Android Enterprise-apparaatinstellingen functies toestaan of beperken](device-restrictions-android-for-work.md) voor de huidige lijst met instellingen. 

Van toepassing op: Volledig beheerde Android Enterprise-apparaten

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---"></a>Controleren of er zich een TPM-chipset in een nalevingsbeleid voor Windows 10-apparaten bevindt <!-- 3617671 -->

Deze functie is vertraagd en wordt later uitgebracht.

#### <a name="updated-ui-changes-for-microsoft-edge-browser-on-windows-10-and-later-devices----3775833-----"></a>Bijgewerkte wijzigingen aan de gebruikersinterface voor de Microsoft Edge-browser op Windows 10 en hoger <!-- 3775833   -->
Wanneer u een apparaatconfiguratieprofiel maakt, kunt u Microsoft Edge-functies op Windows 10 en hoger toestaan of beperken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** als platform > **Apparaatbeperkingen** als profieltype >  **Microsoft Edge-browser**). In deze update worden de instellingen voor Microsoft Edge meer beschrijvend en gemakkelijker te begrijpen. 

Als u deze functies wilt bekijken, gaat u naar [Apparaatbeperkingsinstellingen voor de Microsoft Edge-browser](device-restrictions-windows-10.md#microsoft-edge-browser).

Van toepassing op: Windows 10 en hoger

#### <a name="expanded-support-for-android-enterprise-fully-managed-devices--preview-------3903241-3903244-3903246-----"></a>Uitgebreide ondersteuning voor volledig beheerde Android Enterprise-apparaten (preview)  <!--   3903241, 3903244, 3903246   -->
Wij hebben onze ondersteuning, die nog steeds in openbare preview is, uitgebreid voor volledig beheerde Android Enterprise-apparaten ([voor het eerst aangekondigd in januari 2019](whats-new.md#week-of-january-14-2019) en het volgende erin opgenomen: 

- Op volledig beheerde en toegewezen apparaten kunt u [nalevingsbeleid](compliance-policy-create-android-for-work.md) maken met inbegrip van regels voor wachtwoorden en vereisten voor besturingssystemen (**Apparaatcompatibiliteit** > **Beleid** > **Beleid maken** > **Android Enterprise** als platform > **Apparaateigenaar** als profieltype). 

  Op toegewezen apparaten kan het apparaat mogelijk worden weergegeven als **niet-compatibel**. Voorwaardelijke toegang is niet beschikbaar op toegewezen apparaten. Zorg ervoor dat u alle taken of acties uitvoert om de toegewezen apparaten compatibel te maken met uw toegewezen beleid.

- [Voorwaardelijke toegang](conditional-access.md): beleid voor voorwaardelijke toegang dat van toepassing is op Android, is ook van toepassing op volledig beheerde Android Enterprise-apparaten. Gebruikers kunnen nu hun volledig beheerd apparaat registreren bij Azure Active Directory met behulp van de **Microsoft Intune-app**. Bekijk vervolgens eventuele nalevingsproblemen voor toegang tot resources van de organisatie en los deze op.

- Nieuwe eindgebruiker-app (Microsoft Intune-app): er is een nieuwe eindgebruiker-app voor volledig beheerde Android-apparaten met de naam **Microsoft Intune**. Deze nieuwe app is licht en modern en biedt een functionaliteit die vergelijkbaar is met de bedrijfsportal-app, maar dan voor volledig beheerde apparaten. Zie [Microsoft Intune-app in Google Play](https://play.google.com/store/apps/details?id=com.microsoft.intune) voor meer informatie.

Ga naar **Apparaatinschrijving** > **Android-inschrijving** > **Bedrijfseigendom, volledig beheerde gebruikersapparaten** om volledige beheerde Android-apparaten in te stellen. Ondersteuning voor volledig beheerde Android-apparaten blijft in preview en bepaalde Intune-functies werken mogelijk niet volledig.  

Zie onze blog [Microsoft Intune - Preview 2 voor volledig beheerde Android Enterprise-apparaten](https://aka.ms/preview2_AE_fullymanaged) voor meer informatie over deze preview.


### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470--wnstaged--"></a>Profiel configureren om bepaalde vensters over te slaan tijdens het doorlopen van de configuratieassistent <!-- 2276470  wnstaged-->
Wanneer u een macOS-registratieprofiel maakt, kunt u binnenkort instellen dat de configuratieassistent de volgende schermen overslaat:
- Uiterlijk
- Weergavekleur
- iCloudStorage Als u een nieuw profiel maakt of een profiel bewerkt, moeten de geselecteerde skip-schermen worden gesynchroniseerd met de Apple MDM-server.  Gebruikers kunnen de opdracht tot een handmatige synchronisatie van de apparaten geven, zodat er geen vertraging in het ophalen van de profielwijzigingen is.
Raadpleeg [MacOS-apparaten automatisch inschrijven met het Device Enrollment Program of Apple School Manager](device-enrollment-program-enroll-macos.md) voor meer informatie.

#### <a name="bulk-device-naming-when-enrolling-corporate-ios-devices--3566569----"></a>Bulksgewijs apparaten benoemen bij het inschrijven van zakelijke iOS-apparaten<!--3566569  -->
Wanneer u een van de zakelijke inschrijvingsmethoden van Apple (DEP/ABM/ASM) gebruikt, kunt u de naamindeling van een apparaat zo instellen dat binnenkomende iOS-apparaten automatisch worden benoemd. U kunt een indeling opgeven waarin het apparaattype en serienummer in uw sjabloon wordt opgenomen. Als u dit wilt doen, kiest u **Intune** > **Apparaatinschrijving** > **Apple-inschrijving** > **Tokens voor het inschrijvingsprogramma** > **Een token selecteren** >**Profiel maken** > **Naamgevingsindeling voor apparaten**. U kunt bestaande profielen bewerken, maar alleen bij zojuist gesynchroniseerde apparaten wordt de naam toegepast.

#### <a name="updated-default-timeout-message-on-enrollment-status-page----3959331---"></a>Bijgewerkt standaard time-outbericht op de pagina Inschrijvingsstatus <!-- 3959331 -->
We hebben het standaard time-outbericht bijgewerkt dat gebruikers zien wanneer de pagina Status van inschrijving (ESP) de time-outwaarde overschrijdt die is opgegeven in het ESP-profiel. Het nieuwe standaardbericht is wat gebruikers zien en waarin duidelijk wordt gemaakt welke volgende acties ze kunnen ondernemen met hun ESP-implementatie.  

### <a name="device-management"></a>Apparaatbeheer

#### <a name="retire-noncompliant-devices-----1827291-----"></a>Niet-compatibele apparaten buiten gebruik stellen  <!-- 1827291   -->
Deze functie is vertraagd en wordt in een toekomstige release geïntroduceerd.


### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="intune-data-warehouse-v10-changes-reflecting-back-to-beta----4403765---"></a>Wijzigingen in Intune Data Warehouse V1.0 worden doorgevoerd in de bètaversie <!-- 4403765 -->
Toen V1.0 voor het eerst werd uitgebracht in 1808, verschilde deze op belangrijke punten van de bètaversie-API. In 1903 zullen deze wijzigingen in de bètaversie-API worden doorgevoerd. Als u belangrijke rapporten hebt die gebruikmaken van de bètaversie-API, wordt u ten zeerste aangeraden deze rapporten over te zetten naar V1.0 om wijzigingen te voorkomen die fouten veroorzaken. Zie [Wijzigingenlogboek voor Intune Data Warehouse-API](reports-changelog.md#1903-part-2) voor meer informatie.

#### <a name="monitor-security-baseline-status-public-preview----3082047---"></a>Status beveiligingsbasislijnen controleren (openbare preview) <!-- 3082047 --> 
We hebben een [weergave per categorie](security-baselines-monitor.md#per-category-view) toegevoegd aan de controle van beveiligingsbasislijnen. (Beveiligingsbasislijnen blijven in preview). De weergave per categorie geeft elke categorie weer van de basislijn, samen met het percentage apparaten dat in elke statusgroep voor die categorie kan worden onderverdeeld. U kunt nu zien hoeveel apparaten niet overeenkomen met de afzonderlijke categorieën, onjuist zijn geconfigureerd of niet van toepassing zijn.

### <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer

#### <a name="scope-tags-for-apple-vpp-tokens---2371886----"></a>Bereiktags voor Apple VPP-tokens <!--2371886  -->
U kunt nu bereiktags toevoegen aan Apple VPP-tokens. Alleen gebruikers aan wie dezelfde bereiktag is toegewezen, hebben toegang tot het Apple VPP-token met die tag. VPP-apps en e-Books die zijn gekocht met dit token nemen de bereiktags ervan over. Zie [RBAC en bereiktags gebruiken](scope-tags.md) voor meer informatie over bereiktags.







## <a name="week-of-april-1-2019"></a>Week van 1 april 2019

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="updated-certificate-connectors-----icm-113304612---"></a>Bijgewerkte certificaatconnectors  <!-- ICM 113304612 -->
We hebben updates uitgebracht voor zowel de [Intune-certificaatconnector als de PFX-certificaatconnector voor Microsoft Intune](certficates-pfx-configure.md#whats-new-for-connectors). Met de nieuwe releases worden verschillende bekende problemen opgelost.  

### <a name="app-management"></a>Appbeheer

#### <a name="user-experience-update-for-the-company-portal-app-for-ios----2536024---"></a>Update van de gebruikerservaring voor de bedrijfsportal-app voor iOS <!-- 2536024 -->
De startpagina van de bedrijfsportal-app voor iOS-apparaten is opnieuw ontworpen. Door deze wijziging kan de startpagina beter patronen volgen van de iOS-gebruikersinterface en ook een verbeterde zichtbaarheid bieden voor apps en e-Books.

#### <a name="changes-to-company-portal-enrollment-for-ios-12-device-users---3448635---"></a>Wijzigingen in de bedrijfsportal-App-registratie voor gebruikers van iOS-12-apparaten <!--3448635 -->  
De schermen en stappen in de bedrijfsportal-app voor iOS-inschrijving zijn bijgewerkt, zodat deze overeenkomen met de wijzigingen in de MDM-inschrijving die zijn uitgebracht in Apple iOS 12.2. In de bijgewerkte werkstroom wordt gebruikers het volgende gevraagd:  

* Safari te openen op de bedrijfsportalwebsite en het beheerprofiel te downloaden voordat zij terugkeren naar de bedrijfsportal-app.  
* De app instellingen te openen voor het installeren van het beheerprofiel op hun apparaat.
* Terug te gaan naar de bedrijfsportal-app om de inschrijving te voltooien.  

Zie [iOS-apparaat inschrijven bij Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) voor de bijgewerkte stappen en schermen voor de inschrijving.  

## <a name="week-of-march-25-2019"></a>Week van 25 maart 2019

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

### <a name="support-for-the-power-bi-compliance-app-from-the-data-warehouse-blade-in-microsoft-intune----4260871---"></a>Ondersteuning voor de Power BI-compatibiliteit-app vanuit de blade Datawarehouse in Microsoft Intune <!-- 4260871 -->
Voorheen werd via de koppeling **Power BI-bestand downloaden** in de blade **Intune-datawarehouse** een Intune-datawarehouserapport (pbix-bestand) gedownload. Dit rapport is vervangen door de Power BI-compatibiliteit-app. De Power BI-compatibiliteit-app hoeft niet speciaal te worden geladen of ingesteld. U kunt deze rechtstreeks in de online Power BI-portal openen en ermee gegevens speciaal voor uw Intune-tenant weergeven op basis van uw referenties. Selecteer in Intune de koppeling **Intune-datawarehouse instellen** aan de rechterkant van de Intune-blade. Klik vervolgens op **Power BI-app ophalen**. Zie [Verbinding maken met het datawarehouse met Power BI](reports-proc-get-a-link-powerbi.md) voor meer informatie.

## <a name="week-of-march-18-2019"></a>Week van 18 maart 2019

### <a name="app-management"></a>Appbeheer

#### <a name="deploy-microsoft-visio-and-microsoft-project----3725386----"></a>Microsoft Visio en Microsoft Project implementeren <!-- 3725386  -->
U kunt nu Microsoft Visio Pro voor Office 365 en Microsoft Project Online-desktopclient implementeren als onafhankelijke apps voor Windows 10-apparaten met behulp van Microsoft Intune, mits u licenties hebt voor deze apps. Selecteer vanuit Intune **Client-apps** > **Apps** > **Toevoegen** om de blade **App toevoegen** weer te geven. Selecteer in de blade **App toevoegen** **Windows 10** als **App-type**. Selecteer daarna **App-pakket configureren** om de te installeren apps te selecteren. Zie [Office 365-apps toewijzen aan Windows 10-apparaten met Microsoft Intune](apps-add-office365.md) voor meer informatie over Office 365-apps voor Windows 10-apparaten.

#### <a name="microsoft-visio-pro-for-office-365-product-name-change----3593653----"></a>Wijziging van de productnaam Microsoft Visio Pro voor Office 365 <!-- 3593653  -->
**Microsoft Visio Pro voor Office 365** heet nu **Microsoft Visio Online-abonnement 2**.  Zie [Visio Online-abonnement 2](https://products.office.com/visio/visio-online-plan-2) voor meer informatie over Microsoft Visio. Zie [Office 365-apps toewijzen aan Windows 10-apparaten met Microsoft Intune](apps-add-office365.md) voor meer informatie over Office 365-apps voor Windows 10-apparaten.

#### <a name="intune-app-protection-policy-app-character-limit-setting----3291302----"></a>Instelling van Intune app-beveiligingsbeleid (APP) voor maximum aantal tekens <!-- 3291302  -->
Intune-beheerders kunnen een uitzondering opgeven voor de Intune-app-beveiligingsbeleidsinstelling **Knippen, kopiëren en plakken met andere apps beperken**.  Als beheerder kunt u het aantal tekens opgeven dat mag worden geknipt of gekopieerd uit een beheerde app. Met deze instelling kunt u het opgegeven aantal tekens voor elke app delen, ongeacht de instelling Knippen, kopiëren en plakken met andere apps beperken. Houd er rekening mee dat de versie van de Intune-bedrijfsportal-app voor Android versie 5.0.4364.0 of hoger moet zijn. Zie [iOS-gegevensbeveiliging](app-protection-policy-settings-ios.md#data-protection), [Android-gegevensbeveiliging](app-protection-policy-settings-android.md#data-protection) en [Logboeken voor client-app-beveiliging controleren](app-protection-policy-settings-log.md#app-protection-policy-settings) voor meer informatie.

#### <a name="office-deployment-tool-odt-xml-for-office-proplus-deployment----3192477-----"></a>ODT-XML (ODT: Office Deployment Tool) voor de implementatie van Office ProPlus <!-- 3192477   -->
U kunt voorzien in een ODT-XML bij het maken van een Office Professional Plus-exemplaar in de Intune-beheerconsole. Dit biedt meer aanpassingsmogelijkheden, indien de bestaande Intune gebruikersinterfaceopties niet voldoen aan uw behoeften. Zie [Office 365-apps toewijzen aan Windows 10-apparaten met Microsoft Intune](https://docs.microsoft.com/intune/apps-add-office365) en [Configuratieopties voor de Office Deployment Tool](https://docs.microsoft.com/DeployOffice/configuration-options-for-the-office-2016-deployment-tool) voor meer informatie.

#### <a name="app-icons-will-now-be-displayed-with-an-automatically-generated-background----1429026----"></a>App-pictogrammen worden nu weergegeven met een automatisch gegenereerde achtergrond <!-- 1429026  -->
In de Windows-bedrijfsportal-app-worden app-pictogrammen nu weergegeven met een automatisch gegenereerde achtergrond op basis van de overheersende kleur van het pictogram (mits deze detecteerbaar is). Indien van toepassing wordt de grijze rand die voorheen zichtbaar was op app-tegels, vervangen door deze achtergrond. Gebruikers zullen deze wijziging zien in bedrijfsportal-app-versies die hoger zijn dan 10.3.3451.0.

#### <a name="install-available-apps-using-the-company-portal-app-after-windows-bulk-enrollment----2751523-----"></a>Beschikbare apps installeren met behulp van de bedrijfsportal-app na de Windows-bulkinschrijving <!-- 2751523   -->
Windows-apparaten die zijn geregistreerd bij Intune via [Windows-bulkinschrijving](windows-bulk-enroll.md) (inrichtingspakketten) kunnen de bedrijfsportal-app gebruiken voor het installeren van beschikbare apps. Zie [De Windows 10-bedrijfsportal handmatig toevoegen](store-apps-company-portal-app.md) en [De Microsoft Intune-bedrijfsportal-app configureren](company-portal-app.md) voor meer informatie over de bedrijfsportal-app.

> [!Note]
> Deze functie is nog niet volledig geïmplementeerd voor alle klanten. Als u niet de bedrijfsportal-app kunt gebruiken op bulksgewijs ingeschreven apparaten, moet u wellicht wachten totdat deze wijziging zichtbaar wordt in uw account.

#### <a name="the-microsoft-teams-app-can-be-selected-as-part-of-the-office-app-suite----3828932----"></a>De Microsoft Teams-app kan worden geselecteerd als onderdeel van het Office-app-pakket <!-- 3828932  -->
De Microsoft Teams-app kan worden opgenomen of uitgesloten als onderdeel van de installatie van het Office Pro Plus-app-pakket. Deze functie werkt voor Office Professional Plus-buildnummer 16.0.11328.20116+. De gebruiker moet zich afmelden en vervolgens weer aanmelden op het apparaat om de installatie te voltooien. Selecteer in Intune de optie **Client-apps** > **Apps** > **Toevoegen**. Selecteer een van de app-typen van de **Office 365-Suite** en selecteer vervolgens **App-pakket configureren**.

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="automatically-start-an-app-when-running-multiple-apps-in-kiosk-mode-on-windows-10-and-later-devices----2351390---"></a>Een app automatisch starten wanneer meerdere apps in de kioskmodus worden uitgevoerd op Windows 10-apparaten en hoger <!-- 2351390 -->

U kunt op Windows 10-apparaten en hoger een apparaat in de kioskmodus uitvoeren en veel apps uitvoeren. In deze update is een instelling **AutoLaunch** aanwezig (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** als platform > **Kiosk** als profieltype > **Kiosk voor meerdere apps**). Gebruik deze instelling om een app automatisch te starten wanneer de gebruiker zich aanmeldt bij het apparaat.

Zie [Instellingen van Windows 10-apparaten en hoger die als kiosk moet worden uitgevoerd in Intune](kiosk-settings-windows.md) voor een lijst en een beschrijving van alle kioskinstellingen.

Van toepassing op: Windows 10 en hoger

#### <a name="operational-logs-also-show-details-on-non-compliant-devices----4063755----"></a>Operationele logboeken geven ook details weer over niet-compatibele apparaten <!-- 4063755  -->
Wanneer u Intune-logboeken naar Azure Monitor-functies stuurt, kunt u tevens de operationele logboeken sturen. In deze update bieden de operationele logboeken ook informatie over niet-compatibele apparaten. 

Raadpleeg [Logboekgegevens verzenden naar opslag, Event Hubs of Log Analytics in Intune](review-logs-using-azure-monitor.md) voor meer informatie over deze functie.

#### <a name="route-logs-to-azure-monitor-in-more-intune-workloads----3804627---"></a>Logboeken sturen naar Azure Monitor in meer Intune-workloads <!-- 3804627 -->
In Intune kunt u auditlogboeken en operationele logboeken sturen naar Event Hubs,opslag en Log Analytics in Azure Monitor (**Intune** > **Bewaking** > **Diagnose-instellingen**). In deze update kunt u deze logboeken routeren in meer Intune-workloads, met inbegrip van naleving, configuraties en client-apps enzovoort. 

Zie [logboekgegevens verzenden naar Event Hubs, opslag en Log Analytics](review-logs-using-azure-monitor.md) voor meer informatie over routering van logboeken naar Azure Monitor.

#### <a name="create-and-use-mobility-extensions-on-android-zebra-devices-in-intune----3305880-----"></a>Mobility-extensies maken en gebruiken op Android Zebra-apparaten in Intune <!-- 3305880   -->
In deze update biedt Intune ondersteuning voor het configureren van Android Zebra-apparaten. U kunt specifiek een apparaatconfiguratieprofiel maken en instellingen toepassen op Android Zebra-apparaten met behulp van MX-profielen (MX: Mobility-extensies) die worden gegenereerd door StageNow (**Apparaatconfiguratie** >  **Profielen** > **Profiel maken** > **Android** als platform > **MX-profiel (alleen Zebra)** als profieltype).

Zie [Zebra-apparaten gebruiken en beheren met Mobility-extensies in Intune](android-zebra-mx-overview.md) voor meer informatie over deze functie.

Van toepassing op: Android

### <a name="device-management"></a>Apparaatbeheer

#### <a name="encryption-report-for-windows-10-devices-in-public-preview---2351538---"></a>Versleutelingsrapport voor Windows 10-apparaten (in openbare preview)<!-- 2351538 -->  
U kunt met het nieuwe [versleutelingsrapport (preview)](encryption-monitor.md) details weergeven over de versleutelingsstatus van uw Windows 10-apparaten. Beschikbare details bestaan onder meer uit een TPM-versie van apparaten, de versleutelingsgereedheid en -status, foutrapportage en meer.  

#### <a name="access-bitlocker-recovery-keys-from-the-intune-portal-in-public-preview----2351547-----"></a>Toegang krijgen tot BitLocker-herstelsleutels vanuit de Intune-portal (in openbare preview) <!-- 2351547   -->  
U kunt nu Intune gebruiken om [details weer te geven](encryption-monitor.md) over BitLocker-sleutelidentificatie en BitLocker-herstelsleutels vanuit Azure Active Directory.

#### <a name="microsoft-edge-support-for-intune-scenarios-on-ios-and-android-devices----3411007---"></a>Microsoft Edge-ondersteuning voor Intune-scenario's op iOS- en Android-apparaten <!-- 3411007 -->
Microsoft Edge biedt ondersteuning voor dezelfde beheerscenario's als de Intune Managed Browser met de toevoeging van verbeteringen in de eindgebruikerervaring. Microsoft Edge-functies voor bedrijven die zijn ingeschakeld door het Intune-beleid zijn onder meer dubbele identiteit, integratie van app-beveiligingsbeleid, integratie van Azure-toepassingsproxy's, beheerde favorieten en snelkoppelingen voor de startpagina. Zie de [ondersteuning voor Microsoft Edge](app-configuration-managed-browser.md#microsoft-edge-support) voor meer informatie.

#### <a name="exchange-onlineintune-connector-deprecate-support-for-eas-only-devices---3105122----"></a>Exchange Online-/Intune-connector bieden geen ondersteuning meer voor apparaten voor alleen EAS <!--3105122  -->
De Intune-console ondersteunt niet langer de weergave en het beheer van apparaten voor alleen EAS die met Exchange Online zijn verbonden met de Intune-connector. U hebt in plaats daarvan de volgende opties:
- Apparaten registreren in Mobile Device Management (MDM)
- Beleid voor Intune-app-beveiliging gebruiken om uw apparaten te beheren
- Exchange-besturingselementen gebruiken zoals wordt beschreven in [Clients en mobiel in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/clients-and-mobile-in-exchange-online)

### <a name="search-the-all-devices-page-for-an-exact-device-by-using-name---4254930---"></a>De pagina Alle apparaten doorzoeken voor een exact apparaat met behulp van [naam] <!--4254930 -->
U kunt nu zoeken naar een exacte apparaatnaam. Ga naar **Intune** > **Apparaten** > **Alle apparaten** > plaats in het zoekvak de naam van het apparaat tussen {} om naar een exacte overeenkomst te zoeken. Bijvoorbeeld **{Device12345}** .

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="support-for-additional-connectors-on-the-tenant-status-page----3617202----"></a>Ondersteuning voor extra connectors op de pagina Tenantstatus <!-- 3617202  -->
De pagina [Tenantstatus](tenant-status.md) geeft nu de statusinformatie weer voor extra connectors, inclusief *Windows Defender Advanced Threat Protection* (ATP) en andere Mobile Threat Defense-connectors.

### <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer

#### <a name="granting-intune-read-only-access-to-some-azure-active-directory-roles----3637917----"></a>Alleen-lezentoegang voor Intune verlenen aan bepaalde Azure Active Directory-rollen <!-- 3637917  -->
Alleen-lezentoegang voor Intune is verleend aan de volgende Azure AD-rollen. Machtigingen met Azure AD-rollen hebben voorrang boven machtigingen die zijn verleend via de op rollen gebaseerd toegangsbeheer (RBAC) in Intune.

Alleen-lezentoegang tot Intune-controlegegevens:

- Beheerder voor naleving
- Beheerder voor nalevingsgegevens

Alleen-lezentoegang tot alle Intune-gegevens:

- Beveiligingsbeheerder
- Beveiligingsoperator
- Beveiligingslezer

Zie [Op rollen gebaseerd toegangsbeheer](role-based-access-control.md) voor meer informatie.

#### <a name="scope-tags-for-ios-app-provisioning-profiles---2934430-----"></a>Bereiktags voor inrichtingsprofielen voor iOS-apps <!--2934430   -->
U kunt een bereiktag toevoegen aan een inrichtingsprofiel voor iOS-apps, zodat alleen personen met rollen die ook aan die bereiktag zijn toegewezen toegang hebben tot de app. Zie [RBAC en bereiktags gebruiken](scope-tags.md) voor meer informatie.

#### <a name="scope-tags-for-app-configuration-policies---2371891-----"></a>Bereiktags voor app-configuratiebeleid <!--2371891   -->
U kunt een bereiktag toevoegen aan app-configuratiebeleid, zodat alleen personen met rollen die ook zijn toegewezen aan de bereiktag, toegang hebben tot het app-configuratiebeleid. Het app-configuratiebeleid kan alleen doel zijn voor of worden gekoppeld aan apps waaraan dezelfde bereiktag is toegewezen. Zie [RBAC en bereiktags gebruiken](scope-tags.md) voor meer informatie.

### <a name="microsoft-edge-support-for-intune-scenarios-on-ios-and-android-devices----3411007---"></a>Microsoft Edge-ondersteuning voor Intune-scenario's op iOS- en Android-apparaten <!-- 3411007 -->
Microsoft Edge biedt ondersteuning voor dezelfde beheerscenario's als de Intune Managed Browser met de toevoeging van verbeteringen in de eindgebruikerervaring. Microsoft Edge-functies voor bedrijven die zijn ingeschakeld door het Intune-beleid zijn onder meer dubbele identiteit, integratie van app-beveiligingsbeleid, integratie van Azure-toepassingsproxy's, beheerde favorieten en snelkoppelingen voor de startpagina. Zie de [ondersteuning voor Microsoft Edge](app-configuration-managed-browser.md#microsoft-edge-support) voor meer informatie.

## <a name="week-of-february-25-2019"></a>Week van 25 februari 2019

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="intune-powershell-module----951068----"></a>Intune PowerShell-module <!-- 951068  -->
De Intune PowerShell-module die ondersteuning biedt voor de Intune-API via Microsoft Graph, is nu beschikbaar in de [Microsoft PowerShell Gallery](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1902.1.10).

- [Informatie over het gebruik van deze module](https://github.com/Microsoft/Intune-PowerShell-SDK/blob/master/README.md)
- [Voorbeelden van scenario's waarbij deze module wordt gebruikt](https://github.com/Microsoft/Intune-PowerShell-SDK/blob/master/Samples/README.md)

#### <a name="improved-support-for-delivery-optimization----3183757----"></a>Verbeterde ondersteuning voor Delivery Optimization  <!--3183757  -->
We hebben de ondersteuning in Intune uitgebreid voor het configureren van Delivery Optimization. U kunt nu een uitgebreide lijst configureren met [Delivery Optimization-instellingen](delivery-optimization-settings.md) en deze rechtstreeks vanuit de Intune-console toepassen op uw apparaten.


## <a name="week-of-february-18-2019"></a>Week van 18 februari 2019

### <a name="app-management"></a>Appbeheer

#### <a name="intune-will-leverage-google-play-protect-apis-on-android-devices----2577355-----"></a>Intune gaat gebruikmaken van Google Play Protect-API’s op Android-apparaten <!-- 2577355   -->
Sommige IT-beheerders hebben te maken met een BYOD-landschap waar eindgebruikers mogelijk rooting of jailbreaking van hun mobiele telefoon veroorzaken. Dit gedrag leidt, in sommige gevallen onbewust, tot omzeiling van vele Intune-beleidsregels die zijn ingesteld om gegevens van de organisatie op de apparaten van eindgebruikers te beveiligen. Intune biedt daarom root- en jailbreakdetectie voor zowel geregistreerde als niet-geregistreerde apparaten. Met deze release zal Intune Google Play Protect-API’s aan onze bestaande rootdetectiecontroles toevoegen voor niet-geregistreerde apparaten. Hoewel Google niet alle rootdetectiecontroles die plaatsvinden deelt, verwachten we wel dat met deze API’s gebruikers worden gedetecteerd die hun apparaten om wat voor reden dan ook hebben geroot, variërend van apparaataanpassing tot de mogelijkheid nieuwere besturingssysteemupdates te krijgen op oudere apparaten. Toegang van deze gebruikers tot bedrijfsgegevens kan vervolgens worden geblokkeerd, of hun zakelijke accounts kunnen worden gewist uit via beleid ingeschakelde apps. Als extra waarde heeft de IT-beheerder nu verschillende rapportupdates op de blade Intune-app-beveiliging. Het rapport Gemarkeerde gebruikers toont welke gebruikers via de SafetyNet API-scan van Google Play Protect zijn gedetecteerd. Het rapport Mogelijk schadelijke apps toont aan welke apps zijn gedetecteerd via de scan die met de Verify Apps-API van Google is uitgevoerd. Deze functie is beschikbaar voor Android.

#### <a name="win32-app-information-available-in-troubleshooting-blade----2617342-----"></a>Informatie over Win32-apps, beschikbaar in de blade Probleemoplossing <!-- 2617342   -->
U kunt nu logboekbestanden over fouten bij een Win32-app-installatie verzamelen via de blade **Probleemoplossing** in de Intune-app. Zie [Problemen met de installatie oplossen](troubleshoot-app-install.md) en [Problemen met Win32-apps oplossen](apps-win32-app-management.md#troubleshoot-win32-app-issues) voor meer informatie over problemen oplossen met de installatie van apps.

#### <a name="app-status-details-for-ios-apps----3761235-----"></a>Informatie over de appstatus voor iOS-apps <!-- 3761235   -->
Er zijn nieuwe meldingen voor installatiefouten van apps beschikbaar met betrekking tot het volgende:
- Fout tijdens het installeren van VPP-apps op een gedeelde iPad
- Fout tijdens uitschakelen van App Store
- Fout tijdens het zoeken van een VPP-licentie voor de app
- Fout tijdens het installeren van systeemapps met MDM-provider
- Fout tijdens het installeren van apps wanneer apparaat zich in de verloren-modus of kioskmodus bevindt
- Fout tijdens het installeren van apps wanneer gebruiker niet bij de App Store is aangemeld

In Intune selecteert u **Client-apps** > **Apps** > naam van de app > **Apparaatinstallatiestatus**. Nieuwe foutmeldingen zijn beschikbaar in de kolom **Statusdetails**.

#### <a name="new-app-categories-screen-in-the-company-portal-app-for-windows-10---3834780----"></a>Het scherm Nieuwe app-categorieën in de bedrijfsportal-app voor Windows 10<!-- 3834780  -->
Een nieuw scherm met de naam **App-categorieën** is toegevoegd om de blader- en selectie-ervaring voor apps te verbeteren in de bedrijfsportal voor Windows 10. Gebruikers zien nu hun apps gesorteerd onder categorieën, zoals **Aanbevolen**, **Opleiding** en **Productiviteit**. Deze wijziging wordt weergegeven in de bedrijfsportal-app-versies 10.3.3451.0 en hoger. Zie [Wat is er nieuw in de gebruikersinterface van de app?](https://docs.microsoft.com/intune/whats-new-app-ui) om het nieuwe scherm te bekijken. Zie [Apps installeren en delen op uw apparaat](/intune-user-help/install-apps-cpapp-windows) voor meer informatie over apps in de bedrijfsportal.  

#### <a name="power-bi-compliance-app----1455231-doc-work-item---"></a>Power BI-compatibiliteit-app <!-- 1455231 doc-work-item -->
Krijg toegang tot uw Intune-datawarehouse in Power BI Online met behulp van de [Intune-compatibiliteit-app (datawarehouse)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp). Met deze Power BI-app kunt u nu vooraf gemaakte rapporten openen en delen zonder iets te hoeven instellen en zonder uw webbrowser te verlaten. Zie [Wijzigingenlogboek - Power BI-compatibiliteit-app](reports-changelog.md#power-bi-compliance-app) voor meer informatie.


### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="powershell-scripts-can-run-in-a-64-bit-host-on-64-bit-devices----1862675-----"></a>PowerShell-scripts kunnen worden uitgevoerd in een 64-bits host op 64-bits apparaten <!-- 1862675   -->
Wanneer u een PowerShell-script aan een apparaatconfiguratieprofiel toevoegt, wordt het script altijd uitgevoerd in 32 bits, zelfs op 64-bits besturingssystemen. Met deze update kan een beheerder het script uitvoeren in een 64-bits PowerShell-host op 64-bits apparaten (**Apparaatconfiguratie** > **PowerShell-scripts** > **Toevoegen** > **Configureren** > **Script uitvoeren in 64-bits PowerShell-host**).

Zie [PowerShell-scripts in Intune](intune-management-extension.md) voor meer details over het gebruik van PowerShell.

Van toepassing op: Windows 10 en hoger

#### <a name="macos-users-are-prompted-to-update-their-password----1873216---"></a>macOS-gebruikers wordt gevraagd hun wachtwoord bij te werken <!-- 1873216 -->
In Intune wordt de instelling **ChangeAtNextAuth** afgedwongen op macOS-apparaten. Deze instelling heeft gevolgen voor eindgebruikers en apparaten met wachtwoordbeleid voor naleving of wachtwoordprofielen voor apparaatbeperkingen. Eindgebruikers wordt eenmalig gevraagd hun wachtwoord bij te werken. Dit gebeurt wanneer een gebruiker voor het eerst een taak uitvoert die moet worden geverifieerd, zoals het aanmelden bij het apparaat. Gebruikers kunnen ook worden gevraagd hun wachtwoord bij te werken wanneer zij iets doen waarvoor beheerdersrechten zijn vereist, zoals het aanvragen van sleutelhangertoegang. 

Wijzigingen in nieuw of bestaand wachtwoordbeleid door de beheerder zorgt ervoor dat opnieuw aan eindgebruikers wordt gevraagd om hun wachtwoord bij te werken.

Van toepassing op:  
macOS

#### <a name="assign-scep-certificates-to-a-userless-macos-device-----2340521----"></a>SCEP-certificaten aan een macOS-apparaat zonder gebruikers toewijzen  <!-- 2340521  -->
U kunt met behulp van apparaatkenmerken SCEP-certificaten (SCEP: Simple Certificate Enrollment Protocol) toewijzen aan macOS-apparaten, inclusief apparaten zonder gebruikersaffiniteit, en het certificaatprofiel met Wi-Fi -of VPN-profielen koppelen. Dit is een uitbreiding van de bestaande ondersteuning voor het [toewijzen van SCEP-certificaten aan apparaten zonder gebruikersaffiniteit](certificates-scep-configure.md#create-a-scep-certificate-profile) die worden uitgevoerd op Windows, iOS en Android.  In deze update wordt de optie toegevoegd waarmee een certificaattype van *Apparaat* wordt geselecteerd wanneer u een SCEP-certificaatprofiel voor macOS configureert.

Van toepassing op: 
- macOS

#### <a name="intune-conditional-access-ui-update------2432313-----"></a>Update voor gebruikersinterface voor voorwaardelijke toegang tot Intune   <!-- 2432313   -->
We hebben verbeteringen aangebracht in de gebruikersinterface voor voorwaardelijke toegang in de Intune-console. Deze omvatten:
-  Vervanging van de Intune-blade *Voorwaardelijke toegang* door de blade van Azure Active Directory. Hiermee hebt u toegang tot het volledige bereik instellingen en configuraties voor [voorwaardelijke toegang](conditional-access.md) (die een Azure AD-technologie blijven) vanuit de Intune-console. 
- We hebben de naam van de blade *On-premises toegang* gewijzigd in *Toegang tot Exchange* en de configuratie van de *Exchange-serviceconnector* verplaatst naar deze hernoemde blade.  Door deze wijziging worden de locaties gecombineerd waar u [details met betrekking tot Exchange online en on-premises configureert en bewaakt](exchange-connector-install.md).  

#### <a name="kiosk-browser-and-microsoft-edge-browser-apps-can-run-on-windows-10-devices-in-kiosk-mode----2935135-----"></a>Kiosk Browser- en Microsoft Edge Browser-apps kunnen worden uitgevoerd op Windows 10-apparaten in de kioskmodus <!-- 2935135   -->
In de kioskmodus kunnen één of meerdere apps op Windows 10-apparaten worden uitgevoerd. Deze update omvat verschillende wijzigingen in het gebruik van browserapps in de kioskmodus, waaronder:

- Voeg de Microsoft Edge Browser of Kiosk Browser toe om deze als apps uit te voeren op het kioskapparaat (**Apparaatconfiguratie** > **Profielen** > **Nieuw profiel** > **Windows 10 en later** voor platform > **Kiosk** voor profieltype).
- Er zijn nieuwe functies en instellingen beschikbaar voor toestaan of beperken (**Apparaatconfiguratie** > **Profielen** > **Nieuw profiel** > **Windows 10 en hoger** als platform > **Apparaatbeperkingen** als profieltype), waaronder:

  - Microsoft Edge-browser:
  - Gebruik van Microsoft Edge-kioskmodus
  - De browser vernieuwen na niet-actieve tijd

 - Favorieten en zoeken:
  - Wijzigingen in de zoekmachine toestaan

Ga voor een lijst met deze instellingen naar:

- [Instellingen voor apparaten met Windows 10 en hoger om ze als kiosk uit te voeren](kiosk-settings-windows.md)
- [Microsoft Edge Browser-apparaatbeperkingen](device-restrictions-windows-10.md#microsoft-edge-browser)
- [Apparaatbeperkingen voor favorieten en zoeken](device-restrictions-windows-10.md##favorites-and-search)

Van toepassing op: Windows 10 en hoger

#### <a name="new-device-restriction-settings-for-ios-and-macos-devices----3448774-----"></a>Nieuwe apparaatbeperkingsinstellingen voor iOS- en macOS-apparaten <!-- 3448774   -->
U kunt een aantal instellingen en functies beperken op apparaten waarop iOS en macOS worden uitgevoerd (**Apparaatconfiguratie** > **Profielen** > **Nieuw profiel** > **iOS** of **macOS** voor platform > **Apparaatbeperkingen** voor profieltype). Met deze update worden meer functies en instellingen toegevoegd die u kunt beheren, waaronder het instellen van schermtijd, het wijzigen van eSIM-instellingen en mobiele abonnementen en meer op iOS-apparaten. Andere functies zijn het vertragen van de zichtbaarheid voor de gebruiker van software-updates en het blokkeren van cacheopslag van inhoud op macOS-apparaten. 

Als u de functies en instellingen wilt zien die u kunt beperken, raadpleegt u:

- [Beperkingsinstellingen voor iOS-apparaten](device-restrictions-ios.md)
- [Beperkingsinstellingen voor macOS-apparaten](device-restrictions-macos.md)

Van toepassing op:

- iOS
- macOS

#### <a name="kiosk-devices-are-now-called-dedicated-devices-on-android-enterprise-devices----3598402-----"></a>Apparaten in de kioskmodus heten voortaan 'toegewezen apparaten' op Android Enterprise-apparaten <!-- 3598402   -->
Voor de afstemming met Android terminologie wordt **kiosk** gewijzigd in **toegewezen apparaten** voor Android Enterprise-apparaten (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > ** Android Enterprise als platform > **Alleen apparaateigenaar** > **Apparaatbeperkingen** > **Toegewezen apparaten**).

Als u de beschikbare instellingen wilt zien, gaat u naar [Apparaatinstellingen voor het toestaan of beperken van functies](device-restrictions-android-for-work.md#dedicated-device-settings).

Van toepassing op:  
Android Enterprise

#### <a name="safari-and-delaying-user-software-update-visibility-ios-settings-are-moving-in-the-intune-ui----3640850-3803313-----"></a>iOS-instellingen voor de zichtbaarheid van Safari-software-updates en het vertragen van die zichtbaarheid voor gebruikers worden verplaatst in de Intune-gebruikersinterface <!-- 3640850, 3803313   -->
Voor iOS-apparaten kunt u Safari-instellingen instellen en software-updates configureren. In deze update worden deze instellingen naar verschillende delen van de Intune-gebruikersinterface verplaatst:

- De Safari-instellingen zijn verplaatst van **Safari** (**Apparaatconfiguratie** > **Profielen** > **Nieuw profiel** > **iOS** als platform > **Apparaatbeperkingen** als profieltype) naar **[Ingebouwde apps](device-restrictions-ios.md#built-in-apps)** .
- De instelling **Zichtbaarheid van software-updates voor gebruikers voor iOS-apparaten onder toezicht vertragen** (**Software-updates** > **Updatebeleid voor iOS**) wordt verplaatst naar **Apparaatbeperkingen** >  **[Algemeen](device-restrictions-ios.md#general)** .  Zie [Software-updates voor iOS](software-updates-ios.md#configure-the-policy) voor meer informatie over de gevolgen voor bestaand beleid. 

Ga voor een lijst met de instellingen naar:

- [Beperkingen voor iOS-apparaten](device-restrictions-ios.md) 
- [Updates van iOS-software](software-updates-ios.md)

Deze functie is van toepassing op: 

- iOS

#### <a name="enabling-restrictions-in-the-device-settings-is-renamed-to-screen-time-on-ios-devices----3699164-----"></a>De naam Beperkingen inschakelen bij de apparaatinstellingen wordt gewijzigd in Schermtijd op iOS-apparaten <!-- 3699164   -->
U kunt **Beperkingen inschakelen bij de apparaatinstellingen** op iOS-apparaten onder toezicht configureren (**Apparaatconfiguratie** > **Profielen** > **Nieuw profiel** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype > **Algemeen**). In deze update wordt de naam van deze instelling gewijzigd in **Schermtijd (alleen onder toezicht)** . 

Het gedrag blijft hetzelfde. Specifiek: 

- iOS 11.4.1 en eerder: **Blokkeren** voorkomt dat eindgebruikers hun eigen beperkingen kunnen instellen bij de apparaatinstellingen. 
- iOS 12.0 en hoger: **Blokkeren** voorkomt dat eindgebruikers hun eigen **Schermtijd** kunnen instellen bij de apparaatinstellingen, waaronder inhouds- en privacybeperkingen. Op apparaten die naar iOS 12.0 zijn geüpgraded is het tabblad Beperkingen niet meer zichtbaar bij de apparaatinstellingen. Deze instellingen vindt u onder **Schermtijd**. 

Zie [Beperkingen voor iOS-apparaten](device-restrictions-ios.md#general) voor een lijst met de instellingen.

Van toepassing op: 
- iOS


### <a name="device-management"></a>Apparaatbeheer

#### <a name="rename-an-enrolled-windows-device----1911112----"></a>De naam van een geregistreerd Windows-apparaat wijzigen <!-- 1911112  -->
U kunt nu de naam van geregistreerde Windows 10-apparaten (RS4 of later) wijzigen. Kies hiervoor **Intune** > **Apparaten** > **Alle apparaten** > kies een apparaat > **Naam van apparaat wijzigen**. Deze functie biedt momenteel geen ondersteuning voor de naamwijziging van hybride Azure AD Windows-apparaten.

#### <a name="auto-assign-scope-tags-to-resources-created-by-an-admin-with-that-scope----3173823----"></a>Bereiktags automatisch toewijzen aan resources die door een beheerder met dat bereik zijn gemaakt <!-- 3173823  -->
Wanneer een beheerder een resource maakt, worden alle bereiktags die aan de beheerder zijn toegewezen automatisch toegewezen aan die nieuwe resources.

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="failed-enrollment-report-moves-to-the-device-enrollment-blade----3560202----"></a>Mislukte verplaatsing van registratierapporten naar de blade Apparaatregistratie <!-- 3560202  -->
Het rapport **Mislukte registraties** is verplaatst naar het gedeelte **Bewaking** van de blade **Apparaatregistratie**. Twee nieuwe kolommen (Registratiemethode en besturingssysteemversie) zijn ook toegevoegd.

#### <a name="company-portal-abandonment-report-renamed-to-incomplete-user-enrollments---3815076-eemiss---"></a>De naam van het rapport Bedrijfsportal afbreken is gewijzigd in Onvolledig gebruikersinschrijvingen <!--3815076 eemiss -->
De naam van het rapport **Bedrijfsportal afbreken** is gewijzigd in **Onvolledig gebruikersinschrijvingen**.


<!-- ########################## -->
## <a name="week-of-february-4-2019"></a>Week van 4 februari 2019

### <a name="app-management"></a>Appbeheer

#### <a name="intune-macos-company-portal-dark-mode----3300524----"></a>Donkere modus van Intune macOS-bedrijfsportal <!-- 3300524  -->
De Intune macOS Bedrijfsportal biedt nu ondersteuning voor de donkere modus voor macOS. Wanneer u de donkere modus inschakelt op een macOS 10.14+-apparaat, wordt de vormgeving door de Bedrijfsportal aangepast naar kleuren die overeenkomen met die modus.

<!-- ########################## -->
## <a name="week-of-january-21-2019"></a>De week van 21 januari 2019

### <a name="app-management"></a>Appbeheer

#### <a name="toast-notifications-for-win32-apps----3136566-----"></a>Toast-meldingen voor Win32-apps <!-- 3136566   -->
U kunt per app-toewijzing onderdrukken dat toast-meldingen voor eindgebruikers worden weergegeven. Selecteer vanuit Intune de optie **Client-apps** > **Apps** > selecteer de app > **Toewijzingen** > **Groepen opnemen**. 

#### <a name="intune-app-protection-policies-ui-update----3251427----"></a>Update van de gebruikersinterface voor beveiligingsbeleid voor apps in Intune <!-- 3251427  -->
We hebben de labels voor instellingen en knoppen voor App-beveiliging van Intune gewijzigd om ze duidelijker te maken. De wijzigingen zijn onder meer:  
- Besturingselementen zijn gewijzigd van **ja** / **nee** naar primair **blokkeren** / **toestaan** en **uitschakelen** / **inschakelen**. De labels zijn ook bijgewerkt.  
- De instellingen zijn opnieuw ingedeeld, zodat de instellingen en bijbehorende labels naast elkaar in het besturingselement staan, wat betere navigatie biedt.   

De standaardinstellingen en een aantal instellingen blijven dezelfde, maar met deze wijziging kan de gebruiker de instellingen beter begrijpen, gebruiken en er door navigeren om het geselecteerde app-beveiligingsbeleid toe te passen. Zie [iOS-instellingen](app-protection-policy-settings-ios.md) en [Android-instellingen](app-protection-policy-settings-android.md) voor meer informatie.

### <a name="additional-settings-for-outlook----3301182----"></a>Extra instellingen voor Outlook <!-- 3301182  -->
U kunt nu de volgende aanvullende instellingen voor Outlook voor iOS en Android configureren met Intune:

- Instellen dat alleen werk- of schoolaccounts mogen worden gebruikt in Outlook in iOS en Android
- Moderne verificatie implementeren voor Office 365 en hybride moderne verificatie voor on-premises accounts
- `SAMAccountName` gebruiken in het gebruikersnaamveld in het e-mailprofiel als basisverificatie wordt geselecteerd
- Toestaan dat contactpersonen worden opgeslagen
- E-mailtips voor externe ontvangers configureren
- Het **Postvak IN met prioriteit** configureren
- Biometrie vereisten voor toegang tot Outlook in iOS
- Externe afbeeldingen blokkeren

> [!NOTE]
> Als u gebruikmaakt van Intune-app-beveiligingsbeleid voor het beheren van toegang tot bedrijfs-id's, wordt afgeraden **biometrie te vereisen**. Zie **Bedrijfsreferenties vereisen voor toegang** voor [iOS-toegangsinstellingen](app-protection-policy-settings-ios.md#access-requirements) en [Android-toegangsinstellingen](app-protection-policy-settings-android.md#access-requirements).

Zie [Configuratie-instellingen voor Microsoft Outlook](app-configuration-policies-outlook.md) voor meer informatie.

#### <a name="delete-android-enterprise-apps----1352553---"></a>Android Enterprise-apps verwijderen <!-- 1352553 -->
U kunt beheerde Google Play-apps verwijderen uit Microsoft Intune. Als u een beheerde Google Play-app wilt verwijderen, opent u Microsoft Intune in de Azure-portal en selecteert u **Client-apps** > **Apps**. In de lijst met apps selecteert u het beletselteken (...) rechts naast de beheerde Google Play-app en vervolgens **Verwijderen** in de weergegeven lijst. Wanneer u een beheerde Google Play-app uit de lijst met apps verwijdert, wordt de goedkeuring voor de beheerde Google Play-app automatisch verwijderd.

#### <a name="managed-google-play-app-type----1352580---"></a>Type beheerde Google Play-app <!-- 1352580 -->
Met het type **beheerde Google Play-app** hebt u toestemming om specifiek [beheerde Google Play-apps](https://play.google.com/work/search?q=microsoft&c=apps) aan Intune toe te voegen. Als Intune-beheerder kunt u nu door goedgekeurde beheerde Google Play-apps bladeren en goedgekeurde beheerde Google Play-apps zoeken, goedkeuren, synchroniseren en toewijzen in Intune.  U hoeft niet langer afzonderlijk naar de beheerde Google Play-console te bladeren en u hoeft niet opnieuw een verificatie uit te voeren.  Selecteer in Intune de optie **Client-apps** > **Apps** > **Toevoegen**. In de lijst **App-type** selecteert u **Beheerd Google Play** als app-type.

### <a name="default-android-pin-keyboard----3802457---"></a>Standaardpincodetoetsenbord van Android <!-- 3802457 -->
Eindgebruikers die een Intune APP-pincode (App Protection Policy) op hun Android-apparaten hebben ingesteld met pincodetype Numeriek, zien nu het Android-standaardtoetsenbord in plaats van de gebruikelijke Android-toetsenbordgebruikersinterface die eerder is ontworpen. Deze wijziging is doorgevoerd voor consistentie met standaardtoetsenborden op zowel Android als iOS, voor de pincodetypen Numeriek en/of Wachtwoordcode. Zie [Android-toegangsvereisten](app-protection-policy-settings-android.md#access-requirements) voor meer informatie over de toegangsinstellingen voor eindgebruiker op Android, zoals de APP-pincode.

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="use-microsoft-recommended-settings-with-security-baselines-public-preview----2055484-----"></a>Door Microsoft aanbevolen instellingen gebruiken met beveiligingsbasislijnen (openbare preview) <!-- 2055484   -->

Intune is geïntegreerd met andere services die op beveiliging gericht zijn, inclusief Windows Defender ATP en Office 365 ATP. Klanten vragen om een gemeenschappelijke strategie en een samenhangende set van end-to-end beveiligingsworkflows voor alle Microsoft 365-diensten. Ons doel is om strategieën af te stemmen en oplossingen te ontwikkelen die beveiligingsactiviteiten en gebruikelijke beheerderstaken combineren. In Intune willen we dit doel bereiken door het publiceren van een set beveiligingsbasislijnen die door Microsoft zijn aanbevolen (**Intune** >  **Beveiligingsbasislijnen**).  Beheerders kunnen direct op basis van deze basislijnen een beveiligingsbeleid opstellen en dit vervolgens voor hun gebruikers implementeren. U kunt ook de aanbevelingen voor procedures aanpassen aan de behoeften van uw organisatie. Intune zorgt ervoor dat apparaten deze basislijnen blijven naleven, en waarschuwt beheerders wanneer gebruikers of apparaten van de basislijnen afwijken.

Deze functie is beschikbaar als openbare preview, dus alle profielen die nu worden gemaakt, worden niet verplaatst naar beveiligingsbasislijnsjablonen die algemeen beschikbaar zijn. U moet deze previewsjablonen niet voor uw productieomgeving gebruiken.

Zie [Een Windows 10-beveiligingsbasislijn maken in Intune](security-baselines-monitor.md) voor meer informatie over beveiligingsbasislijnen.

Deze functie is van toepassing op: Windows 10 en hoger

#### <a name="non-administrators-can-enable-bitlocker-on-windows-10-devices-joined-to-azure-ad---2147379-----"></a>Niet-beheerders kunnen BitLocker gebruiken op Windows 10-apparaten die zijn gekoppeld aan Azure AD<!-- 2147379   -->
Wanneer u BitLocker-instellingen op Windows 10-apparaten inschakelt (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** als platform en **Endpoint Protection** als profieltype > **Windows-versleuteling**), voegt u BitLocker-instellingen toe. 

Deze update bevat een nieuwe BitLocker-instellingen waarmee standaardgebruikers (niet-beheerders) versleuteling kunnen inschakelen. 

Ga naar [Instellingen voor de beveiliging van eindpunten voor Windows 10](endpoint-protection-windows-10.md#windows-encryption) om de instellingen te bekijken.

#### <a name="check-for-configuration-manager-compliance----2192052--eepublished----"></a>Controleren op Configuration Manager-compatibiliteit <!-- 2192052  eepublished  -->
Deze update bevat een nieuwe instelling voor System Center Configuration Manager-compatibiliteit (**Apparaatcompatibiliteit** > **Beleid** > **Beleid maken** > **Windows 10 en hoger** > **Configuration Manager-compatibiliteit**). Configuration Manager verzendt signalen naar Intune-naleving. Met deze instelling kunt u vereisen dat alle Configuration Manager-signalen de waarde 'compatibel' retourneren.

U kunt bijvoorbeeld vereisen dat alle software-updates worden geïnstalleerd op apparaten. Deze vereiste heeft in Configuration Manager de status 'Geïnstalleerd'. Als programma's op het apparaat een onbekende status hebben, is het apparaat niet-compatibel in Intune.

In [Configuration Manager-compatibiliteit](compliance-policy-create-windows.md#configuration-manager-compliance) wordt deze instelling beschreven.

Van toepassing op: Windows 10 en hoger

#### <a name="customize-wallpaper-on-supervised-ios-devices-using-a-device-configuration-profile----2809324-----"></a>Achtergronden op iOS-apparaten die onder toezicht staan aanpassen met behulp van een apparaatconfiguratieprofiel <!-- 2809324   -->
Wanneer u een apparaatconfiguratieprofiel voor iOS-apparaten maakt, kunt u sommige functies aanpassen (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **Apparaatfuncties** voor profieltype). Deze update bevat nieuwe **achtergrond**instellingen waarmee een beheerder een .png-, .jpg- of .jpeg-afbeelding op het startscherm of het vergrendelingsscherm kan gebruiken. Deze achtergrondinstellingen zijn alleen van toepassing op apparaten die onder supervisie staan. 

Zie [Instellingen van apparaatfuncties voor iOS](ios-device-features-settings.md) voor een lijst met deze instellingen.

#### <a name="windows-10-kiosk-is-generally-available----3594661----"></a>Windows 10-kiosk is algemeen beschikbaar <!-- 3594661  -->
In deze update is de Kiosk-functie in Windows 10 en hoger algemeen beschikbaar. Zie [Kiosk-instellingen voor Windows 10 (en hoger)](kiosk-settings.md) voor alle instellingen die u kunt toevoegen en configureren.

#### <a name="contact-sharing-via-bluetooth-is-removed-in-device-restrictions--device-owner-for-android-enterprise----3598396-----"></a>Contactpersonen delen via Bluetooth wordt verwijderd uit Apparaatbeperkingen > Apparaateigenaar voor Android Enterprise <!-- 3598396   -->
Wanneer u een apparaatbeperkingsbeleid voor Android Enterprise-apparaten maakt, is de instelling **Contactpersoon delen via Bluetooth** beschikbaar. In deze update is de instelling **Contactpersoon delen via Bluetooth** verwijderd (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** voor platform > **Apparaatbeperkingen > Apparaateigenaar** voor Profieltype > **Algemeen**). 

De instelling **Contactpersoon delen via Bluetooth** wordt niet ondersteund voor het beheer van Android Enterprise-apparaateigenaren. Wanneer deze instelling wordt verwijderd, heeft dit dus geen invloed op apparaten of tenants, zelfs als deze instelling is ingeschakeld en geconfigureerd in uw omgeving.

Ga naar [Met Android Enterprise-apparaatinstellingen functies toestaan of beperken](device-restrictions-android-for-work.md) voor de huidige lijst met instellingen.

Van toepassing op: Android Enterprise-apparaateigenaar

### <a name="device-management"></a>Apparaatbeheer

#### <a name="selective-wipe-support-for-wip-without-enrollment-devices----1434452---"></a>Ondersteuning voor selectief wissen voor WIP Without Enrollment-apparaten <!-- 1434452 -->
Met Windows Information Protection Without Enrollment (WIP-WE) kunnen klanten hun bedrijfsgegevens op Windows 10-apparaten beveiligen zonder gebruik te maken van volledige MDM-inschrijving. Zodra documenten met WIP-WE-beleid zijn beveiligd, kunnen de beschermde gegevens selectief worden gewist door een Intune-beheerder. Door een gebruiker en een apparaat te selecteren en een wisaanvraag te versturen, worden alle gegevens onbruikbaar die met het WIP-WE-beleid zijn beschermd. Vanuit Intune in de Azure-portal selecteert u hiervoor **Mobiele app** > **App selectief wissen**.

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="new-operational-logs-and-ability-to-send-logs-to-azure-monitor-services----3762211----"></a>Nieuwe operationele logboeken en de mogelijkheid om logboeken te verzenden met Azure Monitor-services <!-- 3762211  -->
Intune beschikt over ingebouwde logboekregistratie waarmee gebeurtenissen worden bijgehouden als wijzigingen worden aangebracht. Deze update bevat nieuwe functies voor logboekregistratie, waaronder: 
- Operationele logboeken (preview), waarin details over gebruikers en apparaten die zich hebben geregistreerd worden weergegeven, inclusief geslaagde en mislukte pogingen.
- Deze auditlogboeken en operationele logboeken kunnen worden verzonden naar Azure Monitor-services, inclusief Storage Accounts, Event Hubs, en Log Analytics. Met deze services kunt u opslaan, analytics als Splunk en QRadar gebruiken en visualisaties van uw logboekregistratiegegevens verkrijgen.

In [Logboekgegevens verzenden naar Storage, Event Hubs of Log Analytics in Intune](review-logs-using-azure-monitor.md) vindt u meer informatie over deze functie.

### <a name="skip-more-setup-assistant-screens-on-an-ios-dep-device----2687509----"></a>Meer Setup Assistant-schermen overslaan op een iOS-DEP-apparaat <!-- 2687509  -->
Naast de schermen die u op dit moment kunt overslaan, kunt u instellen dat iOS DEP-apparaten de volgende schermen in de Setup-assistent overslaan wanneer een gebruiker het apparaat registreert: Weergavetoon, Privacy, Android-migratie, Startknop, iMessage en FaceTime, Onboarding, Migratie weergeven, Weergave, Schermtijd, Software-update, SIM-installatie.
Als u wilt kiezen welke schermen moeten worden overgeslagen, gaat u naar **Apparaatinschrijving** > **Apple-inschrijving** > **Tokens voor inschrijvingsprogramma** > kies een token > **Profielen** > kies een profiel > **Eigenschappen** > **Setup Assistant aanpassen** > kies **Verbergen** voor schermen die u wilt overslaan > **OK**.
Als u een nieuw profiel maakt of een profiel bewerkt, moeten de geselecteerde skip-schermen worden gesynchroniseerd met de Apple MDM-server. Gebruikers kunnen de opdracht tot een handmatige synchronisatie van de apparaten geven, zodat er geen vertraging in het ophalen van de profielwijzigingen is.

#### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Android Enterprise APP WE-app-implementatie <!-- 1171203 -->
Voor Android-apparaten in een niet-geregistreerd APP-WE-implementatiescenario (App Protection Policy Without Enrollment), gebruikt u de beheerde Google Play Store om store-apps en LOB-apps te implementeren bij gebruikers. In het bijzonder kunt u eindgebruikers voorzien van een app-catalogus en een installatie waarbij het niet langer nodig is dat eindgebruikers de beveiligingsstatus van hun apparaten versoepelen door installaties uit onbekende bronnen toe te staan. Bovendien biedt dit implementatiescenario een verbeterde eindgebruikerservaring.

<!-- ########################## -->
## <a name="week-of-january-14-2019"></a>De week van 14 januari 2019

### <a name="preview-of-support-for-android-corporate-owned-fully-managed-devices----1574342----"></a>Voorbeeld van volledig beheerde, zakelijke Android-apparaten <!-- 1574342  -->
Intune ondersteunt nu volledig beheerde Android-apparaten, een scenario waarin apparaten 'zakelijk eigendom' zijn en nauw worden beheerd door de IT-afdeling en gekoppeld zijn aan afzonderlijke gebruikers. Hierdoor kunnen beheerders het hele apparaat beheren, een uitgebreide reeks beleidscontroles afdwingen die niet beschikbaar zijn voor werkprofielen en gebruikers beperken tot de installatie van apps uit de beheerde Google Play Store. Zie [Intune-inschrijving van volledig beheerde Android-apparaten instellen](android-fully-managed-enroll.md) en [Uw toegewezen apparaten of volledig beheerde apparaten inschrijven](android-dedicated-devices-fully-managed-enroll.md) voor meer informatie.  Let op: deze functie wordt momenteel als preview aangeboden. Sommige Intune-mogelijkheden, zoals certificaten, naleving en voorwaardelijke toegang, zijn momenteel niet beschikbaar voor volledig beheerde Android-gebruikersapparaten.

<!-- ########################## -->
## <a name="week-of-january-7-2019"></a>De week van 7 januari 2019

### <a name="app-management"></a>Appbeheer

#### <a name="intune-app-pin----2298397---"></a>Pincode voor de Intune-app <!-- 2298397 -->
Als IT-beheerder kunt u nu het aantal dagen configureren dat een eindgebruiker kan wachten voordat zijn pincode voor de Intune-app moet worden gewijzigd. De nieuwe instelling is *Pincode opnieuw instellen na aantal dagen* en is beschikbaar in Azure Portal als u **Intune** > **Client-apps** > **App-beveiligingsbeleid** > **Beleid maken** > **Instellingen** > **Toegangsvereisten** kiest. Deze functie is beschikbaar voor [iOS](app-protection-policy-settings-ios.md)- en [Android](app-protection-policy-settings-android.md)-apparaten en biedt ondersteuning voor een positief geheel getal.


#### <a name="intune-device-reporting-fields----2748738---"></a>Rapportvelden voor Intune-apparaat <!-- 2748738 -->
Intune biedt aanvullende velden voor apparaatrapporten, waaronder de registratie-id van de app, de Android-fabrikant, het model, de versie van de beveiligingspatch en het iOS-model. In Intune zijn deze velden beschikbaar door **Client-apps** > **App-beveiligingsstatus** te selecteren en vervolgens **App-beveiligingsrapport: iOS, Android** te kiezen. Bovendien helpen deze parameters u de lijst **Toestaan** te configureren voor de apparaatfabrikant (Android), evenals de lijst **Toestaan** voor het apparaatmodel (Android en iOS) en de versie-instellingen van de minimale Android-beveiligingspatch. 


### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Beheersjablonen zijn in openbare preview en verplaatst naar hun eigen configuratieprofiel <!-- 3322847 -->

Beheersjablonen in Intune (**Apparaatconfiguratie** > **Beheersjablonen**) zijn momenteel in openbare preview. Bij deze update:

- Beheersjablonen omvatten circa 300 instellingen die kunnen worden beheerd in Intune. Eerder bestonden deze instellingen alleen in de editor voor groepsbeleid.
- Beheersjablonen zijn beschikbaar in openbare preview.
- Beheersjablonen worden verplaatst van **Apparaatconfiguratie** > **Beheersjablonen** naar **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > kies als **Platform** **Windows 10 en hoger** > kies in **Profieltype** **Beheersjablonen**.
- Rapportage is ingeschakeld

Ga naar [Windows 10 templates to configure group policy settings](administrative-templates-windows.md) (Windows 10-sjablonen voor het configureren van instellingen voor groepsbeleid) voor meer informatie over deze functie.

Van toepassing op: Windows 10 en hoger

#### <a name="use-smime-to-encrypt-and-sign-multiple-devices-for-a-user-----1333642---"></a>S/MIME gebruiken om meerdere apparaten van een gebruiker te versleutelen en ondertekenen  <!-- 1333642 -->
Deze update bevat een S/MIME-e-mailversleuteling met een nieuw profiel voor een geïmporteerd certificaat (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > selecteer het platform > profieltype **Geïmporteerd PKCS-certificaat**). In Intune kunt u certificaten importeren in PFX-indeling. Intune kan deze certificaten dan leveren aan meerdere apparaten die zijn geregistreerd door één gebruiker. Dit omvat ook:
- Het systeemeigen iOS-e-mailprofiel ondersteunt het inschakelen van S/MIME-versleuteling met behulp van geïmporteerde certificaten in de PFX-indeling.
- De systeemeigen mail-app op Windows Phone 10-apparaten gebruikt automatisch het S/MIME-certificaat.
- De persoonlijke certificaten kunnen worden afgeleverd op meerdere platformen. Maar niet alle e-mail-apps ondersteunen S/MIME.
- Op andere platformen moet u mogelijk de mail-app handmatig configureren om S/MIME in te schakelen.  
- E-mail-apps die ondersteuning bieden voor S/MIME-versleuteling, kunnen het ophalen van certificaten voor S/MIME-e-mailversleuteling verwerken op een manier die een MDM niet kan ondersteunen, zoals het lezen van het certificaatarchief van de uitgever.
Zie [S/MIME overview to sign and encrypt email](certificates-s-mime-encryption-sign.md) (S/MIME voor e-mailondertekening en -versleuteling) voor meer informatie over deze functie.
Ondersteund in: Windows, Windows Phone 10, macOS, iOS, Android

#### <a name="new-options-to-automatically-connect-and-persist-rules-when-using-dns-settings-on-windows-10-and-later-devices----1333665-2999078---"></a>Nieuwe opties om automatisch verbinding te maken en regels te behouden met DNS-instellingen in Windows 10 en hoger <!-- 1333665, 2999078 -->
Op apparaten met Windows 10 en hoger kunt u een VPN-configuratieprofiel maken dat een lijst DNS-servers bevat om domeinen om te zetten, zoals contoso.com. Deze update bevat nieuwe instellingen voor naamomzetting: (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > kies **Windows 10 en hoger** als platform > kies **VPN** als profieltype > **DNS-instellingen** >**Toevoegen**): 
- **Automatisch verbinding maken**: Als deze optie is **ingeschakeld**, maakt het apparaat automatisch verbinding met VPN wanneer een apparaat een domein oproept dat u invoert, bijvoorbeeld contoso.com.
- **Permanent**: Standaard zijn alle NRPT-tabelregels voor Naamomzettingsbeleid (NRPT) actief zolang het apparaat is verbonden met behulp van dit VPN-profiel. Wanneer deze instelling is **ingeschakeld** voor een NRPT-regel, blijft de regel actief op het apparaat, zelfs wanneer de VPN-verbinding wordt verbroken. De regel blijft totdat het VPN-profiel is verwijderd of totdat de regel handmatig wordt verwijderd, wat mogelijk is met behulp van PowerShell.
In [Windows 10 VPN-instellingen](vpn-settings-windows-10.md) worden instellingen beschreven. 

#### <a name="use-trusted-network-detection-for-vpn-profiles-on-windows-10-devices----1500165---"></a>Detectie van vertrouwde netwerken gebruiken voor VPN-profielen in Windows 10-apparaten <!-- 1500165 -->
Wanneer u gebruikmaakt van detectie van vertrouwde netwerken, kunt u voorkomen dat VPN-profielen automatisch een VPN-verbinding maken wanneer de gebruiker zich al op een vertrouwd netwerk bevindt. Met deze update kunt u DNS-achtervoegsels toevoegen om detectie van vertrouwde netwerken in te schakelen op apparaten met Windows 10 en hoger (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** als platform en **VPN** als profieltype).
In [VPN-instellingen voor Windows 10](vpn-settings-windows-10.md) worden de huidige VPN-instellingen vermeld.

#### <a name="manage-windows-holographic-for-business-devices-used-by-multiple-users----1907917-1063203---"></a>Windows Holographic for Business-apparaten beheren die worden gebruikt door meerdere gebruikers <!-- 1907917, 1063203 -->
U kunt momenteel gedeelde pc-instellingen configureren op Windows 10- en Windows Holographic for Business-apparaten met een aangepaste OMA-URI-instelling. Met deze update wordt een nieuw profiel toegevoegd om instellingen voor gedeelde apparaten te configureren (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** > **Gedeeld apparaat met meerdere gebruikers**).
Ga naar [Intune settings to manage shared devices](shared-user-device-settings.md) (Intune-instellingen voor het beheren van gedeelde apparaten) voor meer informatie over deze functie.
Van toepassing op: Windows 10 en hoger, Windows Holographic for Business

#### <a name="new-windows-10-update-settings---2626030--2512994----"></a>Nieuwe Windows 10-update-instellingen <!--2626030  2512994  -->
Voor uw [Windows 10-update-ringen](windows-update-for-business-configure.md) kunt u het volgende configureren:
- **Gedrag van automatische updates** : gebruik de nieuwe optie *Standaardinstellingen opnieuw instellen* om de oorspronkelijke instellingen voor automatische updates te herstellen op een Windows 10-computer waarop de *update van oktober 2018* is geïnstalleerd
- **Blokkeren dat gebruikers Windows-updates kunnen onderbreken**: configureer een nieuwe instelling voor software-updates waarmee u kunt toestaan of blokkeren dat gebruikers de installatie van updates kunnen onderbreken via de *Instellingen* op hun computer. 

#### <a name="ios-email-profiles-can-use-smime-signing-and-encryption----2662949---"></a>iOS-e-mailprofielen kunnen gebruikmaken van S/MIME-ondertekening en versleuteling <!-- 2662949 -->
U kunt een e-mailprofiel maken dat verschillende instellingen bevat. Deze update bevat onder andere S/MIME-instellingen die kunnen worden gebruikt voor de ondertekening en versleuteling van e-mailcommunicatie op iOS-apparaten (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > kies **iOS** als platform en **E-mail** als profieltype).
In [Configuratie-instellingen voor iOS-e-mail](email-settings-ios.md) worden de instellingen vermeld.

#### <a name="some-bitlocker-settings-support-windows-10-pro-edition---2727036---"></a>Sommige BitLocker-instellingen ondersteunen Windows 10 Pro<!-- 2727036 -->
U kunt een configuratieprofiel maken waarmee Endpoint Protection-instellingen op Windows 10-apparaten wordt ingesteld, waaronder BitLocker. Met deze update wordt voor sommige BitLocker-instellingen ondersteuning toegevoegd voor Windows 10 Professional. Ga naar [Instellingen voor de beveiliging van eindpunten voor Windows 10](endpoint-protection-windows-10.md#windows-encryption) om deze beveiligingsinstellingen te bekijken.

#### <a name="shared-device-configuration-is-renamed-to-lock-screen-message-for-ios-devices-in-the-azure-portal---2809362---"></a>In Azure Portal is de naam Configuratie voor gedeelde apparaten voor iOS-apparaten gewijzigd in Bericht voor vergrendelingsscherm<!-- 2809362 -->
Wanneer u een configuratieprofiel voor iOS-apparaten maakt, kunt u de instelling **Configuratie voor gedeelde apparaten** toevoegen, zodat er specifieke tekst op het vergrendelingsscherm wordt weergegeven. Deze update bevat onder andere de volgende wijzigingen: 
- De instellingen voor **Configuratie voor gedeelde apparaten** in de Azure-portal worden hernoemd naar 'Vergrendelingsschermbericht (alleen onder supervisie)' (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > kies **iOS** als platform > kies **Apparaatfuncties** als profieltype > **Vergrendelingsschermbericht**).
- Wanneer u vergrendelingsschermberichten toevoegt, kunt u een serienummer, apparaatnaam of een andere apparaatspecifieke waarde als variabele invoegen in **Informatie over de assettag** en **Voetnoot voor het vergrendelingsscherm** . U kunt bijvoorbeeld `Device name: {{devicename}}` of `Serial number is {{serialnumber}}` invoeren met accolades. De lijst [iOS-tokens](app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) bevat de beschikbare tokens die kunnen worden gebruikt.
Het gedeelte [Instellingen om berichten op het vergrendelingsscherm weer te geven](shared-device-settings-ios.md) bevat de huidige instellingen.

#### <a name="new-app-store-doc-viewing-gaming-device-restriction-settings-added-to-ios-devices----2827760--"></a>Nieuwe App Store-, documentweergave-, gaminginstellingen voor apparaatbeperking toegevoegd aan iOS-apparaten <!-- 2827760-->
In **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype > **App Store, documentweergave, gaming** zijn de volgende instellingen toegevoegd: Beheerde apps toestaan om contacten naar niet-beheerde contactenaccounts te schrijven Niet-beheerde apps toestaan om beheerde contactenaccounts te lezen Als u de instellingen wilt weergeven, gaat u naar [iOS-apparaatbeperkingen](device-restrictions-ios.md#app-store-doc-viewing-gaming).

#### <a name="new-notification-hints-and-keyguard-settings-to-android-enterprise-device-owner-devices----3201839-3201843---"></a>Nieuwe instellingen voor meldingen, hints en keyguard voor Android Enterprise-apparaten in zakelijk eigendom <!-- 3201839 3201843 -->
Deze update omvat verschillende nieuwe functies in Android Enterprise-apparaten wanneer deze worden uitgevoerd in zakelijk eigendom. Als u deze functies wilt gebruiken, gaat u naar **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > als **Platform** kiest u **Android Enterprise** > in **Profieltype** kiest u **Alleen zakelijk eigendom** > **Apparaatbeperkingen**.

Nieuwe functies omvatten: 

- Systeemmeldingen uitschakelen, waaronder binnenkomende oproepen, systeemwaarschuwingen, systeemfouten en meer.
- Suggestie om zelfstudies en tips over te slaan voor apps die voor de eerste keer worden geopend.
- Geavanceerde keyguard-instellingen uitschakelen, bijvoorbeeld de camera, meldingen, ontgrendelen met vingerafdruk en meer.


Ga naar [Android Enterprise device restriction settings](device-restrictions-android-for-work.md) (Apparaatbeperkingsinstellingen voor Android Enterprise-apparaten) om de instellingen wilt bekijken.

#### <a name="android-enterprise-device-owner-devices-can-use-always-on-vpn-connections----3202194---"></a>Android Enterprise-apparaten in zakelijk eigendom kunnen AlwaysOn-VPN-verbindingen gebruiken <!-- 3202194 -->
In deze update kunt u ingeschakelde VPN-verbindingen gebruiken op Android Enterprise-apparaten in zakelijk eigendom. Altijd ingeschakelde VPN-verbindingen blijven verbonden en maken direct opnieuw verbinding wanneer gebruikers hun apparaat ontgrendelen, het apparaat opnieuw wordt opgestart of het draadloze netwerk wordt gewijzigd. U kunt de verbinding ook in de vergrendelingsmodus zetten. Hiermee wordt al het netwerkverkeer geblokkeerd totdat de VPN-verbinding actief is.
U vindt altijd ingeschakelde VPN in **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** voor platform > **Apparaatbeperkingen** voor apparaten in zakelijk eigendom > **Connectiviteit**. Ga naar [Android Enterprise device restriction settings](device-restrictions-android-for-work.md) (Apparaatbeperkingsinstellingen voor Android Enterprise-apparaten) om de instellingen wilt bekijken.

#### <a name="new-setting-to-end-processes-in-task-manager-on-windows-10-devices----3285177---"></a>Nieuwe instelling om processen in Taakbeheer in Windows 10-apparaten te beëindigen <!-- 3285177 --> 
Deze update omvat een nieuwe instelling om processen via Taakbeheer in Windows 10-apparaten te beëindigen. Met behulp van een apparaatconfiguratieprofiel (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > als **Platform** kiest u **Windows 10** > in **Profieltype** kiest u **Apparaatbeperkingen** > **Algemene** instellingen) kunt u deze instellingen toestaan of blokkeren.
Ga naar [Apparaatbeperkingsinstellingen voor Windows 10-apparaten](device-restrictions-windows-10.md) als u de instellingen wilt bekijken.
Van toepassing op: Windows 10 en hoger


### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="more-detailed-enrollment-restriction-failure-messaging----3111564---"></a>Gedetailleerdere berichten over fouten bij inschrijvingsbeperking <!-- 3111564 -->
Er komen meer gedetailleerdere foutberichten beschikbaar wanneer er niet wordt voldaan de inschrijvingsbeperkingen. Als u deze berichten wilt bekijken, gaat u naar **Intune** > **Probleemoplossing** en bekijkt u het tabel Inschrijvingsfouten. Zie de [lijst met mislukte inschrijvingen](help-desk-operators.md#enrollment-failure-reference) voor meer informatie.

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="tenant-status-dashboard-----1124854---"></a>Dashboard Tenantstatus  <!-- 1124854 -->
De nieuwe [pagina Tenantstatus](tenant-status.md) biedt één locatie waar u de status en gerelateerde details voor uw tenant kunt bekijken.  Het dashboard is opgedeeld in vier gebieden:
- **Tenantdetails**: bevat uiteenlopende informatie, zoals uw tenantnaam en -locatie, uw MDM-instantie, het totale aantal ingeschreven apparaten in uw tenant en uw aantal licenties. Dit gedeelte bevat ook de huidige servicerelease voor uw tenant.
- **Connectorstatus**: bevat informatie over de beschikbare connectors die u hebt geconfigureerd. Daarnaast kunt u die connectors vermelden die u nog niet hebt ingeschakeld.  
   Op basis van de huidige status worden de connectors gemarkeerd als In orde, Waarschuwing of Niet in orde. Selecteer een connector die u gedetailleerd wilt analyseren om details of aanvullende informatie voor de connector weer te geven.
-  **Intune Service Health**: bevat gedetailleerde informatie over actieve incidenten of storingen voor uw tenant. De informatie in deze sectie wordt rechtstreeks opgehaald uit het Office Message Center.
-  **Intune-nieuws** : bevat actieve berichten voor uw tenant. Berichten omvatten onder andere meldingen wanneer uw tenant de nieuwste functies van Intune ontvangt.  De informatie in deze sectie wordt rechtstreeks opgehaald uit het Office Message Center.

#### <a name="new-help-and-support-experience-in-company-portal-for-windows-10----1488939--"></a>Nieuw Help en ondersteuning-ervaring in de bedrijfsportal voor Windows 10 <!-- 1488939-->
Gebruikers kunnen de nieuwe pagina Help en ondersteuning van Bedrijfsportal gebruiken om problemen op te lossen en hulp te vragen voor app- en toegangsproblemen. Via deze pagina kunnen gebruikers details uit foutenlogboeken en diagnostisch logboeken mailen en kunnen ze de gegevens van de helpdesk van de organisatie vinden. Daarnaast bevat de pagina een gedeelte met veelgestelde vragen met koppelingen naar de relevante Intune-documentatie. 

#### <a name="new-help-and-support-experience-for-intune------3307080---"></a>Nieuwe Help en ondersteuning-ervaring voor Intune   <!-- #3307080 -->
De nieuwe Help en ondersteuning-ervaring wordt de komende paar dagen uitgerold naar alle tenants. Deze nieuwe ervaring is beschikbaar voor Intune en is toegankelijk wanneer de Intune-blades in [Azure Portal](https://portal.azure.com/) worden gebruikt.
Met de nieuwe ervaring kunt u uw probleem in uw eigen woorden beschrijven en informatie over probleemoplossing en op internet gevonden informatie over het oplossen van het probleem ontvangen. Deze oplossingen worden aangeboden via een op regels gebaseerde machine learning-algoritme, dat wordt aangestuurd door zoekvragen van gebruikers. Naast informatie die specifiek is voor problemen kunt u gebruikmaken van de nieuwe werkstroom voor het openen van een ondersteuningsvraag via e-mail of telefoon. Deze nieuwe ervaring vervangt de vorige Help en ondersteuning-ervaring die bestaat uit een statistische verzameling vooraf geselecteerde opties die zijn gebaseerd op het gebied van de console waarin u zich bevindt wanneer u Help en ondersteuning opent. Zie [Ondersteuning voor Microsoft Intune krijgen](get-support.md) voor meer informatie.

### <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer

#### <a name="scope-tags-for-apps----1081941---"></a>Bereiktags voor apps <!-- 1081941 -->
U kunt bereiktags maken om de toegang voor rollen en apps te beperken. U kunt een bereiktag toevoegen aan een app, zodat alleen personen met rollen die ook zijn toegewezen aan de bereiktag, toegang tot de app hebben. Momenteel kunnen er geen bereiktags worden toegewezen aan apps die vanuit de beheerde Google Play Store aan Intune zijn toegevoegd of aan apps die met behulp van het Apple Volume Purchase Program (VPP) zijn aangeschaft (er zijn wel plannen voor ondersteuning in de toekomst). Zie [Bereiktags gebruiken om beleidsregels te filteren](scope-tags.md) voor meer informatie.

<!-- ########################## -->
## <a name="week-of-december-10-2018"></a>Week van 10 december 2018

### <a name="app-management"></a>Appbeheer

#### <a name="updates-for-application-transport-security----748318---"></a>Updates voor Application Transport Security <!-- 748318 -->

Microsoft Intune ondersteunt Transport Layer Security (TLS) 1.2+ voor de best mogelijke codering, om ervoor te zorgen dat Intune standaard veiliger is en ook is afgestemd op andere Microsoft-services, zoals Microsoft Office 365. Om aan deze eis te voldoen, dwingen de iOS- en macOS-bedrijfsportals de bijgewerkte Application Transport Security (ATS)-eisen van Apple af, die ook TLS 1.2+ vereisen. ATS wordt gebruikt om betere beveiliging af te dwingen voor alle app-communicatie die verloopt via HTTPS. Deze wijziging heeft gevolgen voor Intune-klanten die de bedrijfsportal-apps gebruiken op iOS en macOS. Zie de [Intune-ondersteuningsblog](https://aka.ms/compportalats)voor meer informatie.

#### <a name="the-intune-app-sdk-will-support-256-bit-encryption-keys----1832174---"></a>De Intune App-SDK ondersteunt 256-bits versleutelingssleutels <!-- 1832174 -->
De Intune App-SDK voor Android gebruikt nu 256-bits versleutelingssleutels wanneer versleuteling is ingeschakeld door app-beveiligingsbeleid. De SDK biedt doorgaande ondersteuning voor 128-bits sleutels voor compatibiliteit met inhoud en apps die gebruikmaken van oudere SDK-versies.

### <a name="microsoft-auto-update-version-450-required-for-macos-devices----3503442---"></a>Microsoft AutoUpdate versie 4.5.0 vereist voor macOS-apparaten <!-- 3503442 -->
Als u updates voor de app Bedrijfsportal en andere Office-toepassingen wilt blijven ontvangen, moeten macOS-apparaten die worden beheerd door Intune, upgraden naar Microsoft AutoUpdate 4.5.0. Gebruikers hebben deze versie mogelijk al voor hun Office-apps.

### <a name="intune-requires-macos-1012-or-later----2827778---"></a>Voor Intune is macOS 10.12 of hoger vereist <!-- 2827778 -->
Voor Intune is nu macOS versie 10.12 of hoger vereist. Apparaten met eerdere versies van macOS kunnen de app Bedrijfsportal niet gebruiken voor registratie bij Intune. Gebruikers die ondersteuning en nieuwe functies willen krijgen, moeten hun apparaat upgraden naar macOS 10.12 of hoger en de bedrijfsportal-app naar de nieuwste versie upgraden.

<!-- ########################## -->
## <a name="week-of-november-26-2018"></a>Week van 26 november 2018

### <a name="app-management"></a>Appbeheer

#### <a name="uninstalling-apps-on-corporate-owned-supervised-ios-devices----1281677---"></a>Apps verwijderen op onder supervisie staande iOS-apparaten in bedrijfseigendom <!-- 1281677 -->

U kunt alle apps op onder supervisie staande iOS-apparaten in bedrijfseigendom verwijderen. U kunt alle apps verwijderen voor gebruikers- of apparaatgroepen met het toewijzingstype **Verwijderen**. Voor persoonlijke of niet onder supervisie staande iOS-apparaten kunt u nog steeds alleen de apps verwijderen die zijn geïnstalleerd met behulp van Intune.

#### <a name="downloading-intune-win32-app-content----2617320---"></a>Intune Win32-app-inhoud downloaden <!-- 2617320 -->
Clients van Windows 10 RS3 en hoger downloaden Intune Win32-app-inhoud via een Delivery Optimization-onderdeel in de Windows 10-client. Delivery Optimization biedt peer-to-peer-functionaliteit die standaard is ingeschakeld. Momenteel kan Delivery Optimization worden geconfigureerd via groepsbeleid. Raadpleeg [Delivery Optimization voor Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) voor meer informatie. 

#### <a name="end-user-device-and-app-content-menu----2771453---"></a>Apparaat- en app-inhoudmenu voor eindgebruikers <!-- 2771453 -->
Eindgebruikers kunnen nu het contextmenu van apparaten en apps gebruiken om veelvoorkomende acties te activeren, zoals de naam van een apparaat wijzigen of de nalevingsstatus controleren.

#### <a name="set-custom-background-in-managed-home-screen-app-----3041945---"></a>Aangepaste achtergrond in de app voor het beheerde startscherm instellen  <!-- 3041945 -->
We voegen een instelling toe waarmee u de achtergrond van de app voor het beheerde startscherm op Android Enterprise-apparaten in de kioskmodus voor meerdere apps kunt aanpassen.  Om de **Aangepaste URL-achtergrond** te configureren, gaat u naar Intune in de Azure-portal > Apparaatconfiguratie. Selecteer een huidig apparaatconfiguratieprofiel of maak een nieuw profiel als u de kioskinstellingen wilt bewerken.
Raadpleeg [Android Enterprise-apparaatbeperkingen](device-restrictions-android-for-work.md) voor de kioskinstellingen.

#### <a name="app-protection-policy-assignment-save-and-apply----3104570---"></a>Beleidstoewijzing voor app-beveiliging opslaan en toepassen <!-- 3104570 -->
U hebt nu meer controle over uw [beleidstoewijzingen voor app-beveiliging](app-protection-policies.md#deploy-a-policy-to-users). Wanneer u *Toewijzingen* selecteert om de toewijzingen van een beleid in te stellen, moet u uw configuratie **Opslaan** voordat de wijziging wordt toegepast. Gebruik **Verwijderen** om alle wijzigingen die u maakt te verwijderen zonder wijzigingen aan de lijsten Opnemen of Uitsluiten op te slaan.  Door Opslaan of Verwijderen te vereisen, krijgen alleen de door u beoogde gebruikers een beveiligingsbeleid voor apps toegewezen.

#### <a name="new-microsoft-edge-browser-settings-for-windows-10-and-later----3174639---"></a>Nieuwe Microsoft Edge-browserinstellingen voor Windows 10 en hoger <!-- 3174639 -->
Deze update bevat nieuwe instellingen om de Microsoft Edge-browser op uw apparaten te controleren en te beheren. Raadpleeg [Apparaatbeperkingsinstellingen voor Windows 10 (en hoger)](device-restrictions-windows-10.md#microsoft-edge-browser) voor een lijst met deze instellingen.

#### <a name="new-apps-support-with-app-protection-policies----3330037---"></a>Ondersteuning voor nieuwe apps met beveiligingsbeleid voor apps <!-- 3330037 -->
U kunt nu de volgende apps beheren met [Intune-beveiligingsbeleid voor apps](app-protection-policies.md):
- Stream (iOS)
- To DO (Android, iOS)
- PowerApps (Android, iOS)
- Flow (Android, iOS)

Gebruik beveiligingsbeleid voor apps om zakelijke gegevens te beschermen en gegevensoverdracht voor deze apps te controleren, zoals voor andere door beleid beheerde Intune-apps. Opmerking: Als Flow nog niet zichtbaar is in de console, voegt u Flow toe wanneer u app-beveiligingsbeleid maakt of bewerkt. Gebruik hiervoor de optie **+ Meer apps** en geef vervolgens de *App-ID* voor Flow op in het invoerveld. Gebruik voor Android *com.microsoft.flow* en voor iOS *com.microsoft.procsimo*.


### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="ios-and-macos-version-numbers-and-build-numbers-are-shown----1892471---"></a>iOS- en macOS-versienummers en buildnummers worden weergegeven <!-- 1892471 -->
In **Apparaatcompatibiliteit** > **Apparaatcompatibiliteit** worden de versies van het iOS- en macOS-besturingssysteem weergegeven en zijn beschikbaar voor gebruik in compatibiliteitsbeleid. Deze update omvat het buildnummer, dat voor beide platformen configureerbaar is.
Wanneer er beveiligingsupdates worden uitgebracht, laat Apple doorgaans het versienummer ongewijzigd, maar wordt het buildnummer wel bijgewerkt. Door het buildnummer in een compatibiliteitsbeleid te gebruiken, kunt u eenvoudig controleren of een beveiligingsupdate is geïnstalleerd.
Raadpleeg het nalevingsbeleid van [iOS](compliance-policy-create-ios.md#device-health) en [macOS](compliance-policy-create-mac-os.md#device-properties) om deze functie te gebruiken.

#### <a name="update-rings-are-being-replaced-with-delivery-optimization-settings-for-windows-10-and-later----2753807---"></a>Update-ringen worden vervangen door Delivery Optimization-instellingen voor Windows 10 en hoger <!-- 2753807 -->
Delivery Optimization is een nieuw configuratieprofiel voor Windows 10 en hoger. Deze functie biedt een meer gestroomlijnde ervaring om softwareupdates op apparaten in uw organisatie te installeren. Deze update helpt u ook om met behulp van een configuratieprofiel de instellingen in nieuwe en bestaande update-ringen te implementeren.
Raadpleeg [Delivery Optimization-instellingen voor Windows 10 (en hoger)](delivery-optimization-windows.md) om een Delivery Optimization-configuratieprofiel te configureren.

#### <a name="new-device-restriction-settings-added-to-ios-and-macos-devices----2827760---"></a>Nieuwe apparaatbeperkingsinstellingen voor iOS en macOS-apparaten toegevoegd <!-- 2827760 -->
Deze update bevat nieuwe instellingen voor uw iOS- en macOS-apparaten die zijn uitgebracht met iOS 12:

**iOS-instellingen**: 
- Algemeen: verwijdering van apps blokkeren (alleen onder supervisie)
- Algemeen: beperkte USB-modus blokkeren (alleen onder supervisie)
- Algemeen: automatisch datum en tijd afdwingen (alleen onder supervisie)
- Wachtwoord: automatisch wachtwoorden doorvoeren blokkeren (alleen onder supervisie)
- Wachtwoord: aanvragen voor wachtwoordnabijheid blokkeren (alleen onder supervisie)
- Wachtwoord: wachtwoorden delen blokkeren (alleen onder supervisie)

**macOS-instellingen**: 
- Wachtwoord: automatisch wachtwoorden doorvoeren blokkeren
- Wachtwoord: aanvragen voor wachtwoordnabijheid blokkeren
- Wachtwoord: wachtwoorden delen blokkeren

Voor meer informatie over deze instellingen, zie apparaatbeperkingsinstellingen voor [iOS](device-restrictions-ios.md) en [macOS](device-restrictions-macos.md).

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="select-apps-tracked-on-the-enrollment-status-page---2531007---"></a>Apps die worden bijgehouden op de pagina Status van inschrijving selecteren<!-- 2531007 -->
U kunt kiezen welke apps worden bijgehouden in de pagina Status van inschrijving. Totdat deze apps zijn geïnstalleerd, kan de gebruiker het apparaat niet gebruiken. Raadpleeg [Een pagina voor de status van de inschrijving instellen](windows-enrollment-status.md) voor meer informatie.

#### <a name="search-for-autopilot-device-by-serial-number---2595788---"></a>Op serienummer zoeken naar een Autopilot-apparaat <!--2595788 -->
U kunt nu op serienummer zoeken naar Autopilot-apparaten. Kies hiervoor **Apparaatinschrijving** > **Windows-inschrijving** > **Apparaten** > voer een serienummer in het venster **Zoeken op serienummer** in > druk op Enter.

#### <a name="track-installation-of-office-proplus---2620217---"></a>Installatie van Office ProPlus bijhouden <!--2620217 -->
Gebruikers kunnen de voortgang van de installatie van [Office ProPlus](apps-add-office365.md) bijhouden met behulp van de [Pagina Status van inschrijving](windows-enrollment-status.md). Raadpleeg [Een pagina voor de status van de inschrijving instellen](windows-enrollment-status.md) voor meer informatie.

#### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Meldingen voor verlopend VPP-token of onvoldoende bedrijfsportal-licenties <!-- 2237572 -->
Als u het Volume Purchase Program (VPP) gebruikt om de Bedrijfsportal vooraf in te richten tijdens DEP-inschrijving, waarschuwt Intune u wanneer het VPP-token bijna verloopt en wanneer er bijna te weinig licenties zijn voor de Bedrijfsportal.

### <a name="macos-device-enrollment-program-support-for-apple-school-manager-accounts---3006133---"></a>Ondersteuning voor het macOS Device Enrollment Program voor Apple School Manager-accounts <!--3006133 -->
Intune ondersteunt nu het gebruik van het Device Enrollment Program op macOS-apparaten voor Apple School Manager-accounts.  Raadpleeg [MacOS-apparaten automatisch inschrijven met het Device Enrollment Program van Apple School Manager](device-enrollment-program-enroll-macos.md) voor meer informatie.

### <a name="new-intune-device-subscription-sku---3312071--"></a>Nieuwe apparaatabonnements-SKU van Intune <!--3312071-->
Er is nu een nieuwe, op apparaten gebaseerde abonnements-SKU beschikbaar om de kosten van apparaatbeheer in ondernemingen te verlagen. Deze apparaat-SKU van Intune biedt licenties per apparaat op maandbasis. De prijs varieert per licentieprogramma. Deze is direct beschikbaar via de Microsoft 365-beheercentrum en via de [Enterprise Agreement](https://www.microsoft.com/licensing/licensing-programs/enterprise?activetab=enterprise-tab:primaryr2) (EA), [Microsoft Products and Services Agreement](https://www.microsoft.com/licensing/mpsa/default) (MPSA) [Microsoft Open Agreements](https://partner.microsoft.com/licensing/licensing-agreements) en [Cloud Solution Provider](https://www.microsoftpartnercommunity.com/t5/Partnership-101/What-is-the-Cloud-Solution-Provider-CSP-program/td-p/2453) (CSP).

### <a name="device-management"></a>Apparaatbeheer

#### <a name="temporarily-pause-kiosk-mode-on-android-devices-to-make-changes----3041935---"></a>Kioskmodus op Android-apparaten tijdelijk onderbreken om wijzigingen aan te brengen <!-- 3041935 -->
Wanneer u Android-apparaten in de kioskmodus voor meerdere apps gebruikt, moet de IT-beheerder mogelijk wijzigingen aanbrengen aan het apparaat. Deze update omvat nieuwe instellingen voor kiosken voor meerdere apps waarmee de IT-beheerder de kioskmodus tijdelijk kan onderbreken met behulp van een pincode om toegang tot het hele apparaat te krijgen.
Raadpleeg [Android Enterprise-apparaatbeperkingen](device-restrictions-android-for-work.md) voor de kioskinstellingen.

#### <a name="enable-virtual-home-button-on-android-enterprise-kiosk-devices-----3042021---"></a>Virtuele startknop op kioskapparaten voor Android Enterprise inschakelen  <!-- 3042021 -->
Met een nieuwe instelling kunnen gebruikers op een soft-keyknop op hun apparaat tikken om over te schakelen tussen de app voor het beheerde startscherm en andere toegewezen apps op hun kioskapparaat voor meerdere apps. Deze instelling is vooral handig in scenario's waarbij de kiosk-app van een gebruiker niet op de juiste wijze op de knop 'Terug' reageert. U kunt deze instelling configureren voor Android-apparaten in bedrijfseigendom voor eenmalig gebruik. Om de **Virtuele startknop** in of uit te schakelen, gaat u naar Intune in Azure Portal > Apparaatconfiguratie. Selecteer een huidig apparaatconfiguratieprofiel of maak een nieuw profiel als u de kioskinstellingen wilt bewerken.
Raadpleeg [Android Enterprise-apparaatbeperkingen](device-restrictions-android-for-work.md) voor de kioskinstellingen.

<!-- ########################## -->
## <a name="week-of-november-12-2018"></a>Week van 12 november 2018

### <a name="network-access-control-nac-support-for-citrix-sso-for-ios----3259404---"></a>Ondersteuning bij netwerktoegangsbeheer (NAC) voor Citrix SSO voor iOS <!-- 3259404 -->

Citrix heeft een update van Citrix Gateway uitgebracht voor netwerktoegangsbeheer (NAC) voor Citrix SSO voor iOS in Intune. U kunt ervoor kiezen om een apparaat-id op te nemen in een VPN-profiel in Intune en vervolgens dit profiel te pushen naar uw iOS-apparaten. U moet de nieuwste update van Citrix Gateway installeren om deze functionaliteit te kunnen gebruiken.

[VPN-instellingen configureren op iOS-apparaten](vpn-settings-ios.md#base-vpn-settings) biedt meer informatie over het gebruik van NAC, waaronder enkele aanvullende vereisten. 

<!-- ########################## -->
## <a name="week-of-november-5-2018"></a>Week van 5 november 2018

### <a name="support-for-ios-12-oauth-in-ios-email-profiles---2155106---"></a>Ondersteuning van iOS 12 OAuth in iOS-e-mailprofielen <!--2155106 -->

iOS-e-mailprofielen van Intune ondersteunen iOS 12 Open Authorization (OAuth). Maak een nieuw profiel (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **E-mail** voor profieltype) of werk een bestaand e-mailprofiel voor iOS bij. Als u OAuth inschakelt in een profiel dat al naar gebruikers is geïmplementeerd, wordt gebruikers gevraagd de verificatie opnieuw uit te voeren en hun e-mail opnieuw te downloaden.

[iOS-e-mailprofielen](email-settings-ios.md) biedt meer informatie over het gebruik van OAuth in een e-mailprofiel.

### <a name="autopilot-support-for-hybrid-azure-active-directory-joined-devices-preview----1048100--"></a>Autopilot-ondersteuning voor hybride apparaten die zijn toegevoegd aan Azure Active Directory (preview) <!-- 1048100-->
U kunt nu hybride apparaten die aan Azure Active Directory zijn toegevoegd, instellen met behulp van Autopilot. Apparaten moeten aan het netwerk van uw organisatie zijn toegevoegd om de hybride Autopilot-functie te kunnen gebruiken. Zie [Hybride apparaten die aan Azure Active Directory zijn toegevoegd implementeren met Intune en Windows Autopilot](windows-autopilot-hybrid.md) voor meer informatie.
Deze functie komt de komende paar dagen beschikbaar voor onze gebruikers. Daarom kunt u deze stappen pas volgen als de functie beschikbaar is voor uw account.

<!-- ########################## -->
## <a name="week-of-october-29-2018"></a>Week van 29 oktober 2018

### <a name="app-management"></a>Appbeheer

#### <a name="require-non-biometric-pin-after-a-specified-timeout----1506985---"></a>Een niet-biometrische pincode vereisen na de opgegeven time-out <!-- 1506985 -->
Door een niet-biometrische pincode te vereisen na een door de beheerder opgegeven time-out, biedt Intune een betere beveiliging voor apps die geschikt zijn voor Mobile Application Management (MAM) door het gebruik van biometrische identificatie voor toegang tot zakelijke gegevens te beperken. De instellingen hebben invloed op gebruikers die Touch ID (iOS), Face ID (iOS), Android Biometric of andere toekomstige biometrische verificatiemethoden gebruiken om toegang te krijgen tot voor APP/MAM geschikte toepassingen. Door deze instellingen hebben Intune-beheerders gedetailleerdere controle over gebruikerstoegang. Op deze manier wordt de kans kleiner dat een onjuiste gebruiker bedrijfsgegevens kan zien op een apparaat met meerdere vingerafdrukken of andere biometrische toegangsmethoden. Open **Microsoft Intune** in de Azure-Portal. Selecteer **Client-apps** > **App-beveiligingsbeleid** > **Een beleid toevoegen** > **Instellingen**. Ga voor specifieke instellingen naar de sectie **Toegang**. Zie [iOS-instellingen](app-protection-policy-settings-ios.md#access-requirements) en [Android-instellingen](app-protection-policy-settings-android.md#access-requirements) voor meer informatie over instellingen voor toegang.

#### <a name="intune-app-data-transfer-settings-on-ios-mdm-enrolled-devices----2244713---"></a>Instellingen voor Intune APP-gegevensoverdracht op iOS-apparaten die via MDM zijn ingeschreven <!-- 2244713 -->
U kunt het beheer van instellingen voor Intune APP-gegevensoverdracht op iOS-apparaten die zijn ingeschreven via MDM scheiden van het opgeven van de identiteit van de ingeschreven gebruiker. Dit wordt ook wel de UPN (User Principal Name) genoemd. Beheerders die de IntuneMAMUPN niet gebruiken, zullen geen wijziging in het gedrag opmerken. Als deze functionaliteit beschikbaar is, moeten beheerders die de IntuneMAMUPN gebruiken om het gedrag van de gegevensoverdracht op ingeschreven apparaten te beheren de nieuwe instellingen controleren en hun APP-instellingen zo nodig bijwerken.

#### <a name="windows-10-win32-apps----2617325---"></a>Win32-apps voor Windows 10 <!-- 2617325 -->
U kunt uw Win32-apps configureren voor installatie in gebruikerscontext voor individuele gebruikers of u kunt de app installeren voor alle gebruikers van het apparaat.

#### <a name="windows-win32-apps-and-powershell-scripts----2617330---"></a>Windows Win32-apps en PowerShell-scripts <!-- 2617330 -->
Eindgebruikers hoeven niet te zijn aangemeld bij het apparaat om Win32-apps te installeren of PowerShell-scripts uit te voeren. 

#### <a name="troubleshooting-client-app-installation----1363711---"></a>Problemen met de installatie van client-apps oplossen <!-- 1363711 -->
U kunt de problemen met de installatie van client-apps oplossen door de kolom met het label **App-installatie** op de blade **Probleem oplossen** te controleren. Om de blade **Problemen oplossen** in de Intune-portal weer te geven, selecteert u **Problemen oplossen** onder **Help en ondersteuning**.

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="network-access-control-support-on-ios-vpn-clients----1333693---"></a>Ondersteuning voor netwerktoegangsbeheer op iOS VPN-clients <!-- 1333693 -->
Met deze update is er een nieuwe instelling om netwerktoegangsbeheer (NAC) in te schakelen wanneer u een VPN-configuratieprofiel maakt voor Cisco AnyConnect-, F5-toegang en Citrix SSO voor iOS. Dankzij deze instelling kan de NAC-ID van het apparaat worden opgenomen in het VPN-profiel. Momenteel zijn er geen VPN-clients of NAC-partneroplossingen die ondersteuning bieden voor deze nieuwe NAC-ID, maar we houden u op de hoogte via onze [ondersteuningsblogpost](ttps://aka.ms/iOS12_and_vpn) als dit het geval is.

Voor het gebruik van NAC moet u het volgende doen:
1. Aangeven dat Intune apparaat-id's in VPN-profielen mag opnemen
2. Uw firmware/NAC-provider-software bijwerken, met behulp van de richtlijnen van uw NAC-provider

Zie voor meer informatie over deze instelling in een iOS VPN-profiel het onderwerp [VPN-instellingen toevoegen op iOS-apparaten in Microsoft Intune](vpn-settings-ios.md). Zie [Netwerktoegangsbeheer integreren met Intune](network-access-control-integrate.md) voor meer informatie over netwerktoegangsbeheer. 

Van toepassing op: iOS

#### <a name="remove-an-email-profile-from-a-device-even-when-theres-only-one-email-profile----1818139---"></a>Een e-mailprofiel verwijderen van een apparaat, zelfs als deze maar één e-mailprofiel bevat <!-- 1818139 -->
Voorheen kon een e-mailprofiel niet van een apparaat worden verwijderd, *als* dit het enige e-mailprofiel was. Met deze update verandert dat. Nu kunt u een e-mailprofiel verwijderen, zelfs als dit het enige e-mailprofiel op het apparaat is. Zie [E-mailinstellingen toevoegen aan apparaten met Intune](email-settings-configure.md) voor meer informatie.

#### <a name="powershell-scripts-and-aad----2309469---"></a>PowerShell-scripts en Azure Active Directory <!-- 2309469 -->
PowerShell-scripts in Intune kunnen worden gericht op AAD-apparaatbeveiligingsgroepen.

#### <a name="new-required-password-type-default-setting-for-android-android-enterprise---2649963---"></a>Nieuwe standaardwaarde voor ‘Vereist wachtwoordtype’ voor Android, Android Enterprise<!-- 2649963 -->
Wanneer u een nieuw nalevingsbeleid maakt (**Intune** > **Apparaatnaleving** > **Beleid** > **Beleid maken** > **Android** of **Android enterprise** voor platform > Systeembeveiliging), verandert de standaardwaarde voor **Vereist wachtwoordtype**:

Van: Standaardwaarde apparaat: Ten minste numeriek

Van toepassing op: Android, Android Enterprise

Ga naar [Android](compliance-policy-create-android.md) en [Android Enterprise](compliance-policy-create-android-for-work.md) om deze instellingen te bekijken.

#### <a name="use-a-pre-shared-key-in-a-windows-10-wi-fi-profile----2662938---"></a>Een vooraf gedeelde sleutel gebruiken in een Wi-Fi-profiel voor Windows 10 <!-- 2662938 -->
Met deze update kunt u een vooraf gedeelde sleutel gebruiken met het persoonlijke WPA/WPA2-beveiligingsprotocol om een Wi-Fi-configuratieprofiel voor Windows 10 te verifiëren. U kunt ook de configuratie van de kosten voor een netwerk met een datalimiet opgeven voor apparaten in Windows na de update van 10 oktober 2018.

U moet momenteel een Wi-Fi-profiel importeren of een aangepast profiel maken om een vooraf gedeelde sleutel te gebruiken. In [Wi-Fi-instellingen voor Windows 10](wi-fi-settings-windows.md) worden de huidige instellingen vermeld. 

#### <a name="remove-pkcs-and-scep-certificates-from-your-devices----3218390---"></a>PKCS- en SCEP-certificaten van uw apparaten verwijderen <!-- 3218390 -->
In sommige gevallen werden PKCS- en SCEP-certificaten niet van apparaten verwijderd, zelfs wanneer een beleid uit een groep werd verwijderd, een configuratie of nalevingsimplementatie werd verwijderd of een beheerder een bestaand SCEP- of PKCS-profiel bijwerkte. Met deze update verandert dat. Er zijn enkele situaties waarin PKCS- en SCEP-certificaten worden verwijderd van apparaten en een aantal situaties waarin deze certificaten op het apparaat blijven gehandhaafd. Zie [SCEP- en PKCS-certificaten verwijderen in Microsoft Intune](remove-certificates.md) voor deze situaties.

#### <a name="use-gatekeeper-on-macos-devices-for-compliance----2504381---"></a>Gatekeeper gebruiken op macOS-apparaten voor naleving <!-- 2504381 -->
Deze update bevat de macOS Gatekeeper om apparaten te controleren op naleving. Als u de Gatekeeper-eigenschap wilt instellen, [voegt u een apparaatnalevingsbeleid voor macOS-apparaten toe](compliance-policy-create-mac-os.md).


### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="enrollment-abandonment-report----1382924---"></a>Rapport over afgebroken inschrijvingen <!-- 1382924 -->
Een nieuw rapport met details over afgebroken inschrijvingen wordt beschikbaar via **Apparaatinschrijving** > **Monitor**. Zie [Rapport over afgebroken items in bedrijfsportal](enrollment-report-company-portal-abandon.md) voor meer informatie.

#### <a name="new-azure-active-directory-terms-of-use-feature----2870393---"></a>Nieuwe gebruiksvoorwaardenfunctie voor Azure Active Directory <!-- 2870393 -->
Azure Active Directory krijgt een gebruiksvoorwaardenfunctie die u kunt gebruiken in plaats van de bestaande Intune-voorwaarden. De gebruiksvoorwaardenfunctie voor Azure AD biedt meer flexibiliteit als het gaat om welke voorwaarden wanneer worden weergegeven, en biedt betere lokalisatieondersteuning, meer controle over de weergave van voorwaarden en verbeterde rapportage. De gebruiksvoorwaardenfunctie voor Azure AD vereist wel Azure Active Directory Premium P1, dat ook onderdeel is van de Enterprise Mobility + Security E3-suite. Zie het artikel [De voorwaarden voor gebruikerstoegang van uw bedrijf beheren](terms-and-conditions-create.md) voor meer informatie.

#### <a name="android-device-owner-mode-support---3188762--"></a>Ondersteuning voor de modus Android-apparaateigenaar <!--3188762-->
Voor Samsung Knox Mobile Enrollment ondersteunt Intune nu het inschrijven van apparaten bij het beheer van de modus Android-apparaateigenaar. Gebruikers op wifi- of mobiele netwerken kunnen inschrijven met een paar tikken wanneer ze hun apparaten voor het eerst inschakelen. Zie [Android-apparaten automatisch registreren met behulp van de Knox Mobile Enrollment van Samsung](android-samsung-knox-mobile-enroll.md) voor meer informatie.

### <a name="device-management"></a>Apparaatbeheer
#### <a name="new-settings-for-software-updates------1907869---"></a>Nieuwe instellingen voor software-updates   <!-- 1907869 -->  
- Nu kunt u bepaalde meldingen configureren om eindgebruikers te waarschuwen dat het systeem opnieuw moet worden opgestart om de installatie van de meest recente software-updates te voltooien.   
- Nu kunt u een waarschuwingsprompt configureren over het feit dat systemen opnieuw worden opgestart buiten werkuren, waardoor BYOD-scenario's worden ondersteund.

#### <a name="group-windows-autopilot-enrolled-devices-by-correlator-id----2075110---"></a>Voor Windows Autopilot ingeschreven apparaten groeperen op correlator-ID <!-- 2075110 -->
Intune ondersteunt nu het groeperen van ingeschreven Windows-apparaten op correlator-ID met behulp van [Autopilot voor bestaande apparaten](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) via Configuration Manager. De correlator-ID is een parameter van het Autopilot-configuratiebestand. Intune stelt automatisch de [enrollmentProfileName van het Azure Active Directory-apparaatkenmerk](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#using-attributes-to-create-rules-for-device-objects) in zodat deze aansluit bij de "OfflineAutopilotprofile-<correlator ID>". Hierdoor kunnen willekeurige dynamische groepen in Azure AD op basis van correlator-ID’s worden gecreëerd via het kenmerk enrollmentprofileName voor offline Autopilot-inschrijvingen. Zie [Windows Autopilot voor bestaande apparaten](enrollment-autopilot.md#windows-autopilot-for-existing-devices) voor meer informatie.

#### <a name="intune-app-protection-policies----2984657---"></a>Beveiligingsbeleid voor apps in Intune <!-- 2984657 -->
Met behulp van beveiligingsbeleid voor apps in Intune kunt u verschillende instellingen voor gegevensbescherming voor met Intune beveiligde apps configureren, zoals Microsoft Outlook en Microsoft Word. We hebben het uiterlijk van deze instellingen voor zowel [iOS](app-protection-policy-settings-ios.md) als [Android](app-protection-policy-settings-android.md) gewijzigd, zodat u de afzonderlijke instellingen gemakkelijker kunt vinden. Er zijn drie soorten beleidsinstellingen:
- **Herlocatie van gegevens**: deze groep bevat de DLP-besturingselementen voor preventie van gegevensverlies, zoals knippen, kopiëren, plakken en beperkingen voor 'opslaan als'. Deze instellingen bepalen hoe gebruikers met gegevens in de apps kunnen werken.
- **Toegangsvereisten**: deze groep bevat de pincodeopties per app die bepalen hoe de gebruiker toegang heeft tot de apps in een werkcontext.  
- **Voorwaardelijk starten**: deze groep bevat instellingen zoals de minimale instellingen van het besturingssysteem, detectie van opengebroken of geroote apparaten en offline respijtperioden.  
  
De functionaliteit van de instellingen verandert niet, maar de instellingen zijn gemakkelijker terug te vinden wanneer u bezig bent met het opstellen van beleid.

### <a name="intune-apps"></a>Intune-apps

#### <a name="intune-will-support-a-maximum-package-size-of-8-gb-for-lob-apps----1727158---"></a>Intune biedt ondersteuning voor een maximale pakketgrootte van 8 GB voor LOB-apps <!-- 1727158 -->
Intune heeft de maximale pakketgrootte voor LOB-apps (Line-of-business) verhoogd naar 8 GB. Zie [Web-apps toevoegen aan Microsoft Intune](apps-add.md) voor meer informatie.

#### <a name="add-custom-brand-image-for-company-portal-app----1916266---"></a>Aangepaste merkafbeelding toevoegen voor de bedrijfsportal-app <!-- 1916266 -->
Als Microsoft Intune-beheerder kunt u een aangepaste merkafbeelding uploaden die als achtergrondafbeelding wordt weergegeven op de profielpagina van de gebruiker in de bedrijfsportal-app voor iOS. Voor meer informatie over het configureren van de bedrijfsportal-app, zie [Handleiding voor configuratie van de Microsoft Intune bedrijfsportal-app](company-portal-app.md).

#### <a name="intune-will-maintain-the-office-localized-language-when-updating-office-on-end-users-machines----2971030---"></a>Intune behoudt de in Office gelokaliseerde taal bij het bijwerken van Office op machines van eindgebruikers <!-- 2971030 -->
Wanneer Intune Office op de machines van uw eindgebruiker installeert, krijgen eindgebruikers automatisch dezelfde taalpakketten als bij eerdere .MSI Office installaties. Zie [Office 365-apps toewijzen aan Windows 10-apparaten met Microsoft Intune](apps-add-office365.md) voor meer informatie.

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="new-intune-support-experience-in-the-microsoft-365-device-management-portal----3076965---"></a>Nieuwe ervaring voor Intune-ondersteuning in de portal voor Microsoft 365-apparaatbeheer <!-- 3076965 -->
We implementeren een nieuwe ervaring voor help en ondersteuning voor Intune in de [portal voor Microsoft 365-apparaatbeheer]( http://devicemanagement.microsoft.com). Met de nieuwe ervaring kunt u uw probleem in uw eigen woorden beschrijven en informatie over probleemoplossing en op internet gevonden informatie over het oplossen van het probleem ontvangen. Deze oplossingen worden aangeboden via een op regels gebaseerde machine learning-algoritme, dat wordt aangestuurd door zoekvragen van gebruikers.  

Naast informatie die specifiek is voor problemen kunt u ook gebruikmaken van de nieuwe werkstroom voor het openen van een ondersteuningsvraag via e-mail of telefoon.  

Voor klanten die deel uitmaken van de implementatie, vervangt deze nieuwe ervaring de huidige help en ondersteuning die bestaat uit een statistische verzameling vooraf geselecteerde opties die zijn gebaseerd op het gebied van de console waarin u zich bevindt wanneer u Help en ondersteuning opent.  

*Deze nieuwe ervaring voor Help en ondersteuning wordt geïmplementeerd voor sommige, maar niet alle tenants en is beschikbaar in de portal voor apparaatbeheer. Deelnemers aan deze nieuwe ervaring worden willekeurig geselecteerd uit de beschikbare Intune-tenants. Nieuwe tenants worden toegevoegd als we de implementatie uitbreiden.*  

Zie [Help en ondersteuning-ervaring](get-support.md#help-and-support-experience) in Ondersteuning voor Microsoft Intune krijgen voor meer informatie.  

### <a name="powershell-module-for-intune--preview-available----951068---"></a>PowerShell-module voor Intune - Preview-versie is beschikbaar <!-- 951068 -->
Een nieuwe PowerShell-module die ondersteuning biedt voor de Intune-API via Microsoft Graph is nu beschikbaar als preview-versie op [GitHub]( https://aka.ms/intunepowershell). Zie het Leesmij-bestand op die locatie meer informatie over het gebruik van deze module. 


<!-- ########################## -->
## <a name="week-of-october-15-2018"></a>Week van 15 oktober 2018

### <a name="pin-prompt-when-you-change-fingerprints-or-face-id-on-an-ios-device-----2637704----"></a>Pincode vragen bij het wijzigen van vingerafdrukken of Face ID op een iOS-apparaat  <!-- 2637704  -->
Gebruikers wordt nu gevraagd om een pincode na het doorvoeren van biometrische wijzigingen op hun iOS-apparaat. Dit gebeurt ook bij wijzigingen in de geregistreerde gegevens voor Touch ID of Face ID. De timing van dit verzoek is afhankelijk van de configuratie van de time-out die is ingesteld bij *De toegangsvereisten opnieuw controleren na (minuten)* .  Als er geen pincode is ingesteld, wordt de gebruiker gevraagd om dit te doen. 
 
Deze functie is alleen beschikbaar voor iOS en vereist het gebruik van toepassingen die de Intune-APP SDK voor iOS, versie 9.0.1 of hoger, hebben geïntegreerd. Integratie van de SDK is nodig om het gedrag te kunnen afdwingen in de betreffende toepassingen. Deze integratie vindt doorlopend plaats en is afhankelijk van de specifieke toepassingsteams. Apps die hieraan deelnemen, zijn onder meer WXP, Outlook, Managed Browser en Yammer.


<!-- ########################## -->
## <a name="week-of-october-1-2018"></a>Week van 1 oktober 2018

### <a name="app-management"></a>Appbeheer

#### <a name="access-to-key-profile-properties-using-the-company-portal-app----772203---"></a>Toegang tot belangrijke profieleigenschappen met behulp van de bedrijfsportal-app <!-- 772203 -->
Eindgebruikers hebben nu toegang tot belangrijke accounteigenschappen en -acties, zoals het wachtwoord opnieuw instellen, vanuit de bedrijfsportal-app. 

#### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Toetsenborden van derden kunnen worden geblokkeerd door APP-instellingen op iOS <!-- 1248481 -->
Op iOS-apparaten kunnen Intune-beheerders het gebruik blokkeren van toetsenborden van derden bij het benaderen van organisatiegegevens in door beleid beveiligde apps. Wanneer het Application Protection Policy (APP; app-beveiligingsbeleid) is ingesteld om toetsenborden van derden te blokkeren, ontvangt de gebruiker een bericht als hij de eerste keer met bedrijfsgegevens werkt met een toetsenbord van derden. Alle opties, behalve het systeemeigen toetsenbord, worden geblokkeerd en zijn niet zichtbaar voor apparaatgebruikers. Apparaatgebruikers zien het dialoogvenster slechts één keer. 

#### <a name="user-account-access-of-intune-apps-on-managed-android-and-ios-devices----1248496---"></a>Toegang van gebruikersaccounts tot Intune-apps op beheerde Android- en iOS-apparaten <!-- 1248496 -->
Als Microsoft Intune-beheerder kunt u bepalen welke gebruikersaccounts worden toegevoegd aan Microsoft Office-toepassingen op beheerde apparaten. U kunt de toegang beperken tot uitsluitend toegestane gebruikersaccounts van de organisatie, en persoonlijke accounts blokkeren op ingeschreven apparaten. 

#### <a name="outlook-ios-and-android-app-configuration-policy---1828527---"></a>App-configuratiebeleid voor Outlook voor iOS en Android <!--1828527 -->
U kunt nu een app-configuratiebeleid voor Outlook voor iOS en Android maken voor on-premises gebruikers die in iOS en Android gebruikmaken van basisverificatie met het ActiveSync-protocol. Aanvullende configuratie-instellingen worden toegevoegd wanneer het beleid wordt ingeschakeld voor Outlook voor iOS en Android.

#### <a name="office-365-pro-plus-language-packs----1833450---"></a>Office 365 Pro Plus-taalpakketten <!-- 1833450 -->
Als Intune-beheerder kunt extra talen implementeren voor Office 365 Pro Plus-apps die via Intune worden beheerd. De lijst met beschikbare talen bevat het taalpakket **Type** (kern, gedeeltelijk en spellingcontrole). Selecteer in Azure Portal **Microsoft Intune** > **Client-apps** > **Apps** > **Toevoegen**. In de lijst **App-type** op de blade **App toevoegen** selecteert u **Windows 10** onder **Office 365-suite**. Selecteer **Talen** in de blade **Instellingen voor app-suite**.

####  <a name="windows-line-of-business-lob-apps-file-extensions----1884873---"></a>Bestandsextensies van Windows LOB-apps (line-of-business) <!-- 1884873 -->
De beschikbare bestandsextensies voor Windows LOB-apps omvatten nu ook *.msi*, *.appx*, *.appxbundle*, *.msix* en *.msixbundle*. U kunt in Microsoft Intune apps toevoegen via **Client-apps** > **Apps** > **Toevoegen**. Het deelvenster **App toevoegen** wordt weergegeven. Hier kunt u het **app-type** selecteren. Selecteer voor Windows LOB-apps **Line-Of-Business-app** als het app-type, selecteer het **app-pakketbestand** en voeg vervolgens een iOS-installatiebestand toe met de juiste extensie.

#### <a name="windows-10-app-deployment-using-intune----2309001---"></a>Implementatie van Windows 10-apps met Intune <!-- 2309001 -->
Beheerders kunnen Intune gebruiken om de meeste bestaande toepassingen van hun organisatie te implementeren in Windows 10-apparaten van eindgebruikers. Daarmee wordt er uitgebouwd op de bestaande ondersteuning voor Line-Of-Business-apps (LOB) en Microsoft Store voor Bedrijven-apps. Beheerders kunnen toepassingen voor Windows 10-gebruikers toevoegen, installeren en verwijderen in verschillende indelingen, zoals MSI's, Setup.exe of MSP. Intune evalueert de regels voor de vereisten voordat er iets wordt gedownload of geïnstalleerd. Eindgebruikers worden op de hoogte gehouden van de status of vereisten voor opnieuw opstarten via het Windows 10-onderhoudscentrum. Met deze functionaliteit worden bedrijven die geïnteresseerd zijn om deze werkbelasting naar Intune en de cloud te verplaatsen effectief gedeblokkeerd. Deze functie is momenteel beschikbaar als openbare preview-versie en we verwachten in de aankomende maanden significante nieuwe mogelijkheden toe te voegen aan de functie. 

#### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>APP-instellingen voor webgegevens <!-- 2662995 -->
De APP-instellingen voor webcontent op zowel Android- als iOS-apparaten worden bijgewerkt om zowel http- als https-webkoppelingen beter te kunnen verwerken, evenals de gegevensoverdracht via iOS Universal- en Android App-koppelingen. 

#### <a name="end-user-device-and-app-content-menu----2771453---"></a>Apparaat- en app-inhoudmenu voor eindgebruikers <!-- 2771453 -->
Eindgebruikers kunnen nu het contextmenu van apparaten en apps gebruiken om veelvoorkomende acties te activeren, zoals de naam van een apparaat wijzigen of de nalevingsstatus controleren. 

#### <a name="windows-company-portal-keyboard-shortcuts----2771518---"></a>Sneltoetsen voor Windows-bedrijfsportal <!-- 2771518 -->
Eindgebruikers kunnen nu app- en apparaatacties in de Windows-bedrijfsportal activeren met behulp van sneltoetsen (accelerators).

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="create-dns-suffixes-in-vpn-configuration-profiles-on-devices-running-windows-10---1333668---"></a>DNS-achtervoegsels maken in VPN-configuratieprofielen op apparaten met Windows 10<!-- 1333668 -->
Wanneer u een VPN-apparaatconfiguratieprofiel maakt (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** platform > **VPN** profieltype), voert u bepaalde DNS-instellingen in. Met deze update kunt u ook meerdere **DNS-achtervoegsels** in Intune invoeren. Wanneer u DNS-achtervoegsels gebruikt, kunt u naar een netwerkbron zoeken met behulp van de korte naam, in plaats van met de Fully Qualified Domain Name (FQDN). Met deze update kunt u ook de volgorde van de DNS-achtervoegsels in Intune wijzigen.
In [VPN-instellingen voor Windows 10](vpn-settings-windows-10.md#dns-settings) worden de huidige DNS-instellingen vermeld.
Van toepassing op: Windows 10-apparaten

#### <a name="support-for-always-on-vpn-for-android-enterprise-work-profiles----1333705---"></a>Ondersteuning voor altijd ingeschakelde VPN voor Android Enterprise-werkprofielen <!-- 1333705 -->
In deze update kunt u ingeschakelde VPN-verbindingen gebruiken op Android Enterprise-apparaten met beheerde werkprofielen. Altijd ingeschakelde VPN-verbindingen blijven verbonden en maken direct opnieuw verbinding wanneer gebruikers hun apparaat ontgrendelen, het apparaat opnieuw wordt opgestart of het draadloze netwerk wordt gewijzigd. U kunt de verbinding ook in de vergrendelingsmodus zetten. Hiermee wordt al het netwerkverkeer geblokkeerd totdat de VPN-verbinding actief is.
U vindt altijd ingeschakelde VPN in **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** voor platform > **Apparaatbeperkingen** > **Connectiviteit**.

#### <a name="issue-scep-certificates-to-user-less-devices----1744554---"></a>SCEP-certificaten uitgeven voor apparaten zonder gebruiker <!-- 1744554 -->
Momenteel worden certificaten uitgegeven voor gebruikers. Met deze update kunnen SCEP-certificaten worden uitgegeven voor apparaten, waaronder apparaten zonder gebruiker, zoals kiosken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** voor platform > **SCEP-certificaat** voor profiel). Andere updates bevatten:
- De eigenschap **Onderwerp** in een SCEP-profiel is nu een aangepast tekstvak en kan nieuwe variabelen bevatten. 
- De eigenschap **Alternatieve naam voor onderwerp** in een SCEP-profiel heeft nu een tabelopmaak en kan nieuwe variabelen bevatten. Een beheerder kan in de tabel een kenmerk toevoegen en de waarde in een aangepast tekstvak invullen. De alternatieve naam voor het onderwerp ondersteunt de volgende kenmerken: 
  - DNS
  - E-mailadres
  - UPN

  Deze nieuwe variabelen kunnen met statische tekst worden toegevoegd in een tekstvak voor aangepaste waarden. Het DNS-kenmerk kan bijvoorbeeld worden toegevoegd als `DNS = {{AzureADDeviceId}}.domain.com`.

  > [!NOTE]
  > Accolades, puntkomma's en pijp-symbolen '{} ; |' kunnen niet worden gebruikt in de statische tekst van de alternatieve naam voor het onderwerp. Accolades worden alleen geaccepteerd voor `Subject` of `Subject alternative name`, als ze een van de nieuwe apparaatcertificaatvariabelen omsluiten. 

Nieuwe apparaatcertificaatvariabelen:  

```
"{{AAD_Device_ID}}",
"{{Device_Serial}}",
"{{Device_IMEI}}",
"{{SerialNumber}}",
"{{IMEINumber}}",
"{{AzureADDeviceId}}",
"{{WiFiMacAddress}}",
"{{IMEI}}",
"{{DeviceName}}",
"{{FullyQualifiedDomainName}}",
"{{MEID}}",
```

> [!NOTE]
>  - `{{FullyQualifiedDomainName}}` kan alleen worden gebruikt voor Windows-apparaten en apparaten die aan een domein zijn toegevoegd. 
>  -  Houd er rekening mee dat wanneer u in het onderwerp of de alternatieve naam voor het onderwerp voor een apparaatcertificaat apparaateigenschappen opgeeft, zoals het IMEI-nummer, het serienummer en de Fully Qualified Domain Name, deze eigenschappen kunnen worden vervalst door een persoon met toegang tot het apparaat. 

In [Een SCEP-certificaatprofiel maken](certificates-scep-configure.md#create-a-scep-certificate-profile) worden de huidige variabelen bij het maken van een SCEP-configuratieprofiel vermeld. 

Van toepassing op: Windows 10 en hoger en iOS worden ondersteund voor wifi

#### <a name="remotely-lock-uncompliant-devices----2064495---"></a>Niet-compatibele apparaten op afstand vergrendelen <!-- 2064495 -->
Wanneer een apparaat niet compatibel is, kunt u een actie maken voor het nalevingsbeleid waarbij het apparaat op afstand wordt vergrendeld. Maak in Intune > **Apparaatcompatibiliteit** een nieuw beleid of selecteer een bestaand beleid > **Eigenschappen**. Selecteer **Acties voor niet-naleving** > **Toevoegen** en kies ervoor om het apparaat op afstand te vergrendelen.
Ondersteund in: 
- Android
- iOS
- macOS
- Windows 10 Mobile 
- Windows Phone 8.1 en hoger 

#### <a name="windows-10-and-later-kiosk-profile-improvements-in-the-azure-portal----2748224---"></a>Verbeteringen voor kioskprofielen voor Windows 10 en hoger in Azure Portal <!-- 2748224 -->
Deze update bevat de volgende verbeteringen voor het apparaatconfiguratieprofiel voor kiosken voor Windows 10 (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** voor platform > **Kioskvoorbeeld** voor profieltype): 
- Momenteel kunt u meerdere kioskprofielen op hetzelfde apparaat maken. Met deze update biedt Intune ondersteuning voor slechts één kioskprofiel per apparaat. Als u toch meerdere kioskprofielen op één apparaat wilt, kunt u een aangepaste URI gebruiken.
- In het profiel voor een **kiosk voor meerdere apps** kunt u de tegelgrootte en volgorde voor toepassingen selecteren voor de **opmaak van het menu Start** in het toepassingenraster. Als u meer aanpassingen wilt aanbrengen, kunt u verdergaan met het uploaden van een XML-bestand.
- De instellingen voor de kioskbrowser worden verplaatst naar de **kiosk**instellingen. Momenteel hebben de instellingen voor de **kioskwebbrowser** hun eigen categorie in Azure Portal.
Van toepassing op: Windows 10 en hoger




### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="apply-autopilot-profile-to-enrolled-win-10-devices-not-already-registered-for-autopilot----1558983---"></a>Het Autopilot-profiel toepassen op ingeschreven Windows 10-apparaten die nog niet zijn geregistreerd voor Autopilot <!-- 1558983 -->
U kunt Autopilot-profielen toepassen op ingeschreven Windows 10-apparaten die nog niet zijn geregistreerd voor Autopilot. Kies in het Autopilot-profiel de optie **Alle doelapparaten converteren naar Autopilot** om automatisch niet-Autopilot-apparaten te registreren bij de Autopilot-implementatieservice. Het kan 48 uur duren voordat de registratie is verwerkt. Wanneer het apparaat wordt uitgeschreven en opnieuw wordt ingesteld, wordt het door Autopilot ingericht.

#### <a name="create-and-assign-multiple-enrollment-status--page-profiles-to-azure-ad-groups----2526564---"></a>Meerdere profielen voor inschrijvingsstatuspagina's maken en toewijzen aan Azure AD-groepen <!-- 2526564 -->
U kunt nu meerdere profielen voor inschrijvingsstatuspagina's [maken en toewijzen](windows-enrollment-status.md) aan Azure AD-groepen.

#### <a name="migration-from-device-enrollment-program-to-apple-business-manager-in-intune---2748613--"></a>Migratie van Device Enrollment Program naar Apple Business Manager in Intune <!--2748613-->
Apple Business Manager (ABM) werkt in Intune en u kunt uw account van Device Enrollment Program (DEP) upgraden naar ABM. Het proces in Intune is hetzelfde. Als u uw Apple-account wilt bijwerken van DEP naar ABM, gaat u naar [ https://support.apple.com/HT208817]( https://support.apple.com/HT208817).

### <a name="alert-and-enrollment-status-tabs-on-the-device-enrollment-overview-page---2748656--"></a>Tabbladen voor waarschuwingen en inschrijvingsstatus op de overzichtspagina Apparaatinschrijving <!--2748656-->
Waarschuwingen en mislukte inschrijvingen worden nu weergegeven op afzonderlijke tabbladen op de overzichtspagina Apparaatinschrijving.

### <a name="device-management"></a>Apparaatbeheer

#### <a name="restricts-apps-and-block-access-to-company-resources-on-android-devices----2451462----"></a>Apps beperken en de toegang tot bedrijfsresources blokkeren op Android-apparaten <!-- 2451462  -->  
In **Apparaatcompatibiliteit** > **Beleid** > **Beleid maken** > **Android** > **Systeembeveiliging** is er een nieuwe instellingen in de sectie *Apparaatbeveiliging*, namelijk **Beperkte apps**. De instelling **Beperkte apps** maakt gebruik van een nalevingsbeleid om toegang tot bedrijfsresources te blokkeren als er bepaalde apps op het apparaat zijn geïnstalleerd. Het apparaat wordt beschouwd als niet conform beleid totdat de beperkte apps van het apparaat worden verwijderd.
Van toepassing op: 
- Android

<!-- ########################### -->
## <a name="notices"></a>Mededelingen

[!INCLUDE [Intune notices](./includes/intune-notices.md)]
