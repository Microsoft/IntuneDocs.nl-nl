---
title: Nieuwe functies in Microsoft Intune - Azure | Microsoft Docs
titlesuffix: ''
description: Ontdekken wat er nieuw is in Intune Azure Portal
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/27/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
ms.custom: intune-azure; get-started
ms.openlocfilehash: 567a28679b244088af8c943eb483eb4b2b4d88be
ms.sourcegitcommit: 2795255e89cbe97d0b17383d446cca57c7335016
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/27/2018
ms.locfileid: "47403626"
---
# <a name="whats-new-in-microsoft-intune"></a>Wat is er nieuw in Microsoft Intune?
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Ontdek elke week wat er nieuw is in Microsoft Intune. U vindt hier ook informatie over [toekomstige wijzigingen](#whats-coming), [belangrijke kennisgevingen](#notices) betreffende de service en informatie over [oudere releases](whats-new-archive.md). Sommige functies worden gedurende een aantal weken geïmplementeerd en zijn mogelijk niet voor alle gebruikers in de eerste week beschikbaar.

> [!Note]
> Zie de [pagina Wat is er nieuw](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) voor informatie over nieuwe functionaliteit in het hybride beheer van mobiele apparaten (MDM).


<!-- Common categories:  
### App management
### Device configuration
### Device enrollment
### Device management
### Intune apps
### Monitor and troubleshoot
### Role-based access control

-->   

## <a name="week-of-september-24-2018"></a>Week van 24 september 2018

### <a name="microsoft-365-device-management-administration-center----3078424---"></a>Beheercentrum voor Microsoft 365-apparaatbeheer <!-- 3078424 -->
Een van de beloften van Microsoft 365 is vereenvoudigd beheer. In de afgelopen jaren is de back-end Microsoft 365-services geïntegreerd voor het leveren van complete scenario’s zoals voorwaardelijke toegang voor Intune en Azure AD. Het nieuwe [Microsoft 365-beheercentrum](http://devicemanagement.microsoft.com) is de plek waar de beheerervaring wordt versterkt, vereenvoudigd en geïntegreerd. De gespecialiseerde werkruimte voor apparaatbeheer biedt eenvoudige toegang tot alle apparaat- en appbeheerinformatie en taken die uw organisatie nodig heeft. Naar verwachting zal dat dit de primaire cloudwerkruimte voor zakelijke computerteams van eindgebruikers worden.

### <a name="support-for-more-third-party-certification-authorities-ca----3093107---"></a>Ondersteuning voor meer externe certificeringsinstanties (CA’s) <!-- 3093107 -->
Met behulp van het Simple Certificate Enrollment Protocol (SCEP) kunt u nu nieuwe certificaten uitgeven en certificaten vernieuwen op mobiele apparaten met behulp van Windows, iOS, Android en macOS.

## <a name="week-of-september-17-2018"></a>Week van 17 september 2018

### <a name="app-management"></a>Appbeheer

### <a name="remove-duplication-of-app-protection-status-tiles----3083391---"></a>Duplicatie van beschermingsstatustegels in de app verwijderen <!-- 3083391 -->
De tegels **Gebruikersstatus voor iOS** en de **Gebruikersstatus voor Android** werden zowel op de pagina **Client-apps: overzicht** als op de pagina **Client-apps: beschermingsstatus van de app** vermeld. De statustegels zijn verwijderd van de pagina **Client-apps: overzicht** om duplicatie te voorkomen. 

## <a name="week-of-august-27-2018"></a>Week van 27 augustus 2018

### <a name="app-management"></a>Appbeheer

#### <a name="packet-tunnel-support-for-ios-per-app-vpn-profiles-for-custom-and-pulse-secure-connection-types----1520957---"></a>Ondersteuning voor pakkettunnels voor VPN-profielen in iOS op basis van individuele apps voor aangepaste verbindingstypen en Pulse Secure-verbindingstypen <!-- 1520957 -->
Wanneer u in iOS VPN-profielen voor individuele apps gebruikt, kunt u ervoor kiezen om tunnels op app-niveau (app-proxy) of op pakketniveau (pakkettunnel) te gebruiken. Deze opties zijn beschikbaar voor de volgende verbindingstypen:
- Aangepaste VPN
- Pulse Secure Als u niet zeker weet welke waarde u moet gebruiken, raadpleegt u de documentatie van uw VPN-provider.

#### <a name="delay-when-ios-software-updates-are-shown-on-the-device----1949583---"></a>Vertragen wanneer software-updates voor iOS worden weergegeven op het apparaat <!-- 1949583 -->
In Intune > **Software-updates** > **Beleid voor bijwerken van iOS** kunt u dagen en tijden instellen waarop apparaten geen updates mogen installeren. In een toekomstige update krijgt u de mogelijkheid uit te stellen (met een periode van 1 tot 90 dagen) wanneer een software-update wordt weergegeven op het apparaat. 
De huidige instellingen worden weergegeven op de pagina [iOS-updatebeleid configureren in Microsoft Intune](software-updates-ios.md)

#### <a name="office-365-proplus-version----2213968---"></a>Office 365 ProPlus-versie <!-- 2213968 -->
Binnenkort kunt u de Office-versie selecteren wanneer u met Intune Office 365 ProPlus-apps toewijst op Windows 10-apparaten. Selecteer in de Azure-portal **Microsoft Intune** > **Apps** > **Apps toevoegen**. Selecteer daarna **Office 365 ProPlus Suite (Windows 10)** in de vervolgkeuzelijst **Soort**. Selecteer **App Suite-instellingen** om de bijbehorende blade weer te geven. Stel **Kanaal bijwerken** in op een waarde, zoals **Maandelijks**. Verwijder eventueel andere versies van Office (msi) van eindgebruikersapparaten door **Ja** te selecteren. Selecteer **Specifiek** om voor het geselecteerde kanaal een specifieke versie van Office te installeren op apparaten van eindgebruikers. U kunt hier ook opgeven welke **Specifieke versie** van Office u wilt gebruiken. Welke versies er beschikbaar zijn, verandert in de loop van de tijd. Daarom is het mogelijk dat er bij het maken van een nieuwe implementatie nieuwere versies beschikbaar zijn en dat bepaalde oudere versies niet meer beschikbaar zijn. Huidige implementaties blijven de oudere versie implementeren, maar de versielijst wordt voortdurend per kanaal bijgewerkt. Zie [Overzicht van updatekanalen voor Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus) voor meer informatie.

#### <a name="support-for-register-dns-setting-for-windows-10-vpn----2282852---"></a>Ondersteuning voor het registreren van DNS-instellingen voor Windows 10-VPN <!-- 2282852 -->
Met deze update wordt het binnenkort mogelijk om VPN-profielen voor Windows 10 zo te configureren dat deze de IP-adressen die door de interne DNS aan de VPN-interface worden toegewezen, automatisch registreren, zonder dat u hiervoor aangepaste profielen hoeft te gebruiken.
Zie [Windows 10 VPN-instellingen](vpn-settings-windows-10.md) voor informatie over de instellingen die nu beschikbaar zijn voor VPN-profielen. 

#### <a name="the-macos-company-portal-installer-now-includes-the-version-number-in-the-installer-file-name---2652728--"></a>Het installatieprogramma van de macOS-bedrijfsportal-app bevat nu het versienummer in de bestandsnaam van het installatieprogramma <!--2652728-->

#### <a name="ios-automatic-app-updates----2729759-wnready---"></a>Automatische iOS-app-updates <!-- 2729759 wnready -->
Automatische updates voor apps worden gebruikt voor apps voor zowel gelicentieerde apparaten als gebruikers voor iOS-versie 11.0 en later.




### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="windows-hello-will-target-users-and-devices----1106609---"></a>Windows Hello is gericht op gebruikers en apparaten <!-- 1106609 -->
Wanneer u een beleid voor [Windows Hello voor Bedrijven](windows-hello.md) maakt, geldt dit voor alle gebruikers binnen de organisatie (tenant-breed). Met deze update kan het beleid ook worden toegepast op specifieke gebruikers of specifieke apparaten met behulp van een beleid voor apparaatconfiguratie (**Apparaatconfiguratie** > **Profielen**  >  **Profiel maken** > **Identiteitsbescherming** > **Windows Hello voor Bedrijven**).
In Intune in Azure Portal zijn nu de Windows Hello-configuratie en -instellingen zowel onder **Apparaatinschrijving** als onder **Apparaatconfiguratie** beschikbaar. **Apparaatinschrijving** is gericht op de hele organisatie (tenant-breed) en biedt ondersteuning voor Windows AutoPilot (OOBE). **Apparaatconfiguratie** is gericht op apparaten en gebruikers met behulp van een beleid dat wordt toegepast tijdens het inchecken.
Deze functie is van toepassing op:  
- Windows 10 en hoger
- Windows Holographic for Business

#### <a name="zscaler-is-an-available-connection-for-vpn-profiles-on-ios----1769858-eeready---"></a>Zscaler is een beschikbare verbinding voor VPN-profielen voor iOS <!-- 1769858 eeready -->
Wanneer u een VPN-apparaatconfiguratieprofiel in iOS maakt (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** platform > **VPN** profieltype), zijn er verschillende verbindingstypen beschikbaar, waaronder Cisco, Citrix en meer. In deze update wordt Zscaler toegevoegd als verbindingstype. 
De pagina [VPN-instellingen voor apparaten met iOS](vpn-settings-ios.md) biedt een lijst met beschikbare verbindingstypen.

#### <a name="fips-mode-for-enterprise-wi-fi-profiles-for-windows-10----1879077-eeready---"></a>FIPS-modus voor Enterprise Wi-Fi-profielen voor Windows 10 <!-- 1879077 eeready -->
U kunt nu de modus Federal Information Processing Standards (FIPS) voor Enterprise Wi-Fi-profielen voor Windows 10 inschakelen in Intune Azure Portal. Zorg ervoor dat de FIPS-modus is ingeschakeld op uw Wi-Fi-infrastructuur als u dit in uw Wi-Fi-profielen inschakelt.
[Wi-Fi-instellingen voor apparaten met Windows 10 en hoger in Intune](wi-fi-settings-windows.md) laten u zien hoe een Wi-Fi-profiel wordt gemaakt.

#### <a name="control-s-mode-on-windows-10-and-later-devices---public-preview----1958649---"></a>S-modus beheren op apparaten met Windows 10 en hoger - openbare preview <!-- 1958649 -->
Met deze functie-update kunt u een apparaatconfiguratieprofiel maken dat een Windows 10-apparaat uit de S-modus haalt of voorkomt dat gebruikers het apparaat uit de S-modus halen. Deze functie bevindt zich in Intune > **Apparaatconfiguratie** > **Profielen** >  **Windows 10 en hoger** > **Editie-upgrade en modus schakelen**.
De pagina [Maak kennis met Windows 10 in S-⁠modus](https://www.microsoft.com/windows/s-mode) biedt meer informatie over de S-modus.
Van toepassing op: de meeste recente build van [Windows Insider](https://docs.microsoft.com/en-us/windows-insider/at-work-pro/) (in preview).


#### <a name="windows-defender-atp-configuration-package-automatically-added-to-configuration-profile----2144658---"></a>Windows Defender ATP configuratiepakket automatisch toegevoegd aan configuratieprofiel <!-- 2144658 -->
Wanneer u [Advanced Threat Protection en onboarding](advanced-threat-protection.md#onboard-devices-using-a-configuration-profile)-apparaten gebruikt in Intune, moest u voorheen een configuratiepakket downloaden en dit aan uw configuratieprofiel toevoegen. Met deze update haalt Intune het pakket automatisch op uit het Windows Defender-beveiligingscentrum en voegt het toe aan uw profiel.
Van toepassing op Windows 10 en hoger.

#### <a name="require-users-to-connect-during-device-setup---2311457--"></a>Gebruikers verplichten om verbinding te maken tijdens de installatie van het apparaat <!--2311457-->
U kunt nu apparaatprofielen instellen om verplicht te stellen dat het apparaat verbinding maakt met een netwerk alvorens verder te gaan na de netwerkpagina tijdens de installatie van Windows 10. Hoewel deze functie nog in preview is, moet deze instelling worden gebruikt door een Windows Insider build 1809 of hoger.
Van toepassing op: de meeste recente build van [Windows Insider](https://docs.microsoft.com/en-us/windows-insider/at-work-pro/) (in preview).


#### <a name="restricts-apps-and-block-access-to-company-resources-on-ios-and-android-enterprise-devices----2451462---"></a>Apps beperken en de toegang tot bedrijfsbronnen blokkeren op iOS- en Android Enterprise-apparaten <!-- 2451462 -->
Er is onder **Apparaatnaleving** > **Beleid** > **Beleid maken** > **iOS** > **Systeembeveiliging** een nieuwe instelling: **Beperkte toepassingen**. Deze nieuwe instelling maakt gebruik van een nalevingsbeleid om toegang tot bedrijfsbronnen te blokkeren als bepaalde apps op het apparaat zijn geïnstalleerd. Het apparaat wordt beschouwd als niet conform beleid totdat de beperkte apps van het apparaat worden verwijderd.
Van toepassing op: iOS

#### <a name="modern-vpn-support-updates-for-ios----2459928-1819876-and-2650856---"></a>Moderne VPN-ondersteuningsupdates voor iOS <!-- 2459928, 1819876, and 2650856 -->
Deze update biedt extra ondersteuning voor de volgende iOS VPN-clients: 
- F5 Access (versie 3.0.1 en hoger)
- Citrix SSO
- Palo Alto Networks GlobalProtect (versie 5.0 en hoger) Ook beschikbaar in deze update:
- De naam van het bestaande verbindingstype **F5 Access** is gewijzigd in **F5 Access Legacy** voor iOS.
- De naam van het bestaande verbindingstype **Palo Alto Networks GlobalProtect** wordt gewijzigd in **Palo Alto Networks GlobalProtect (verouderd)** voor iOS.
Bestaande profielen met deze verbindingstypen blijven werken met hun respectieve verouderde VPN-clients. Als u in iOS gebruikmaakt van Cisco Legacy AnyConnect, F5 Access Legacy, Citrix VPN of Legacy Palo Alto Networks GlobalProtect versie 4.1, moet u overstappen op de nieuwe apps. Doe dit zo spoedig mogelijk, om ervoor te zorgen dat VPN-toegang beschikbaar blijft voor iOS-apparaten die worden bijgewerkt naar iOS 12.
Zie de [blog van het Microsoft Intune-ondersteuningsteam](https://go.microsoft.com/fwlink/?linkid=2013806) voor meer informatie over iOS 12 en VPN-profielen.

#### <a name="export-azure-classic-portal-compliance-policies-to-recreate-these-policies-in-the-intune-azure-portal----2469637---"></a>Nalevingsbeleid van de klassieke Azure Portal exporteren om dit beleid opnieuw te maken in Intune Azure Portal<!-- 2469637 -->
Nalevingsbeleid gemaakt in de klassieke Azure-portal wordt afgeschaft. U kunt alle bestaande beleidsregels bekijken en verwijderen. U kunt ze echter niet meer bijwerken. Als u nalevingsbeleidsregels moet migreren naar de huidige Intune Azure Portal, kunt u het beleid exporteren als een door komma's gescheiden bestand (*CSV*-bestand). Vervolgens kunt u de details in het bestand gebruiken om dit beleid opnieuw te maken in Intune Azure Portal.

> [!IMPORTANT]
> Wanneer de klassieke Azure Portal buiten gebruik wordt gesteld, is het niet meer mogelijk om uw nalevingsbeleid te openen of weer te geven. Zorg er daarom voor dat u uw beleidsregels exporteert en opnieuw maakt in Azure Portal, voordat de klassieke Azure Portal buiten gebruik wordt gesteld.

#### <a name="better-mobile---new-mobile-threat-defense-partner----22662717---"></a>Better Mobile: nieuwe Mobile Threat Defense-partner <!-- 22662717 -->
U kunt de toegang van mobiele apparaten tot bedrijfsresources beheren met voorwaardelijke toegang op basis van een risicoanalyse die wordt uitgevoerd door Better Mobile, een Mobile Threat Defense-oplossing die in Microsoft Intune is geïntegreerd.

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="lock-the-company-portal-in-single-app-mode-until-user-sign-in---1067692---"></a>De bedrijfsportal in de modus voor enkele toepassing vergrendelen tot een gebruiker zich aanmeldt <!--1067692 --> 
U hebt nu de optie om de bedrijfsportal uit te voeren in de modus voor enkele toepassing als u een gebruiker verifieert via de bedrijfsportal, in plaats van via de configuratieassistent, tijdens de DEP-registratie. Met deze optie wordt het apparaat onmiddellijk vergrendeld nadat de configuratieassistent is voltooid, zodat een gebruiker zich moet aanmelden om toegang te krijgen tot het apparaat. Dit proces zorgt ervoor dat de onboarding voor het apparaat wordt voltooid en het niet in een staat zonder gekoppelde gebruiker blijft.

#### <a name="assign-a-user-and-friendly-name-to-an-autopilot-device---1346521---"></a>Een gebruiker en een beschrijvende naam toewijzen aan een AutoPilot-apparaat <!--1346521 -->
U kunt nu [een gebruiker toewijzen aan een specifiek Autopilot-apparaat](enrollment-autopilot.md). Beheerders kunnen dan ook beschrijvende namen opgeven die aan gebruikers worden getoond wanneer deze hun apparaat instellen met AutoPilot.
Van toepassing op: de meeste recente build van [Windows Insider](https://docs.microsoft.com/en-us/windows-insider/at-work-pro/) (in preview).

#### <a name="use-vpp-device-licenses-to-pre-provision-the-company-portal-during-dep-enrollment----1608345---"></a>VPP-apparaatlicenties gebruiken om de bedrijfsportal vooraf in te richten tijdens DEP-registratie <!-- 1608345 -->
U kunt nu VPP-apparaatlicenties (Volume Purchase Program) gebruiken om de bedrijfsportal vooraf in te richten tijdens de DEP-registraties (Device Enrollment Program). Om dit te doen, geeft u, wanneer u [een registratieprofiel maakt of bewerkt](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile), het VPP-token op dat u wilt gebruiken om de bedrijfsportal te installeren. Controleer of uw token niet verloopt en of u voldoende licenties heeft voor de bedrijfsportal-app. Wanneer het token verloopt of onvoldoende licenties heeft, pusht Intune in plaats daarvan de App Store-bedrijfsportal (deze vraagt om een Apple ID).

#### <a name="confirmation-required-to-delete-vpp-token-that-is-being-used-for-company-portal-pre-provisioning----2237634---"></a>Bevestiging vereist om het VPP-token te verwijderen dat wordt gebruikt voor het vooraf inrichten van de bedrijfsportal <!-- 2237634 -->
Er is nu een bevestiging vereist om een Volume Purchase Program-token (VPP) te verwijderen als dit wordt gebruikt voor het vooraf inrichten van de bedrijfsportal tijdens de DEP-inschrijving.

#### <a name="block-windows-personal-device-enrollments----1849498---"></a>Persoonlijke apparaatinschrijvingen in Windows blokkeren <!-- 1849498 -->
U kunt hiermee [voorkomen dat persoonlijke Windows-apparaten](enrollment-restrictions-set.md#set-device-type-restrictions) in Intune worden geregistreerd met behulp van [beheer van mobiele apparaten](windows-enroll.md) (Mobile Device Management, MDM). Apparaten die zijn geregistreerd bij de [Intune PC-agent](manage-windows-pcs-with-microsoft-intune.md), kunnen niet met deze functie worden geblokkeerd. Deze functie wordt in de komende weken uitgerold; u ziet deze mogelijk dus niet direct terug in de gebruikersinterface.

#### <a name="specify-machine-name-patterns-in-an-autopilot-profile---1849855--"></a>Computernaampatronen opgeven in een AutoPilot-profiel <!--1849855-->
U kunt hiermee [een computernaamsjabloon](enrollment-autopilot.md#create-an-autopilot-deployment-profile) opgeven om tijdens inschrijving via AutoPilot [computernamen](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) te genereren en in te stellen. Van toepassing op: de meeste recente build van [Windows Insider](https://docs.microsoft.com/en-us/windows-insider/at-work-pro/) (in preview).


#### <a name="for-windows-autopilot-profiles-hide-the-change-account-options-on-the-company-sign-in-page-and-domain-error-page---1901669---"></a>De opties voor het wijzigen van een account op de aanmeldingspagina en domeinfoutpagina van een bedrijf verbergen voor Windows AutoPilot-profielen <!--1901669 -->
Er zijn [nieuwe opties voor Windows AutoPilot-profielen](enrollment-autopilot.md#create-an-autopilot-deployment-profile) beschikbaar, waarmee beheerders de opties voor het wijzigen van een account kunnen verbergen op de aanmeldingspagina en domeinfoutpagina's van een bedrijf. Als u deze opties wilt verbergen, moet er een aangepaste huisstijl zijn geconfigureerd in Azure Active Directory. Van toepassing op: de meeste recente build van [Windows Insider](https://docs.microsoft.com/en-us/windows-insider/at-work-pro/) (in preview).



### <a name="device-management"></a>Apparaatbeheer

#### <a name="delete-jamf-devices----2653306--"></a>Jamf-apparaten verwijderen <!-- 2653306-->
U kunt door JAMF beheerde apparaten als volgt verwijderen: ga naar **Apparaten** > kies het Jamf-apparaat > **Verwijderen**.

#### <a name="change-terminology-to-retire-and-wipe----2175759---"></a>Terminologie wijzigen in 'buiten gebruik stellen' en 'wissen' <!-- 2175759 -->
In de gebruikersinterface en documentatie van Intune zijn de volgende begrippen gewijzigd, om consistent te zijn met Graph API:
- **Bedrijfsgegevens verwijderen** wordt gewijzigd in ‘buiten gebruik stellen’
- **Fabrieksinstellingen** wordt gewijzigd in **wissen**

#### <a name="confirmation-dialog-if-admin-tries-to-delete-mdm-push-certificate----297909500--"></a>Het bevestigingsvenster als de beheerder probeert het MDM-Pushcertificaat te verwijderen <!-- 297909500-->
Als iemand probeert een Apple MDM-pushcertificaat te verwijderen, wordt in een bevestigingsvenster het betreffende aantal iOS- en macOS-apparaten weergegeven. Als het certificaat wordt verwijderd, moeten deze apparaten opnieuw worden ingeschreven.

### <a name="additional-security-settings-for-windows-installer----2282430---"></a>Aanvullende beveiligingsinstellingen voor Windows Installer <!-- 2282430 -->
U kunt gebruikers toestemming geven om app-installaties te beheren. Als u deze functie is ingeschakeld, kunnen installaties worden toegestaan die anders worden gestopt vanwege een beveiligingsfout. U kunt het Windows-installatieprogramma de opdracht geven om verhoogde bevoegdheden te gebruiken wanneer een programma op een systeem wordt geïnstalleerd. Verder kunt u ingeschakelde items van Windows-gegevensbescherming laten indexeren en de metagegevens voor de items laten opslaan op een niet-versleutelde locatie. Als het beleid is uitgeschakeld, worden de items met WIP-beveiliging niet geïndexeerd en worden ze niet weergegeven in de resultaten in Cortana of Verkenner. De functionaliteit voor deze opties is standaard uitgeschakeld. 

### <a name="new-user-experience-update-for-the-company-portal-website---2000968---"></a>Nieuwe update van de gebruikerservaring voor de bedrijfsportalwebsite <!--2000968 -->
Op basis van feedback van klanten zijn er nieuwe functies toegevoegd aan de website van de bedrijfsportal. U zult een aanzienlijke verbetering ervaren wat betreft de bestaande functionaliteit en bruikbaarheid van uw apparaten. Delen van de site &ndash;zoals apparaatgegevens, feedback en ondersteuning, en apparaatoverzicht&ndash; krijgen een nieuw, modern, responsief ontwerp. U ziet ook:

- Gestroomlijnde werkstromen voor alle apparaatplatforms
- Verbeterde apparaat-id en inschrijvingsstromen
- Nuttigere foutberichten
- Toegankelijker taal, minder technische jargon
- Mogelijkheid om directe koppelingen naar apps te delen
- Verbeterde prestaties voor grote app-catalogi
- Beter toegankelijk voor alle gebruikers  

De [documentatie voor Intune-bedrijfsportalwebsite](https://docs.microsoft.com/en-us/intune-user-help/using-the-intune-company-portal-website) is bijgewerkt, waarbij deze wijzigingen zijn meegenomen. Zie [UI-updates voor Intune-eindgebruiker-apps](whats-new-app-ui.md) voor een voorbeeld van de app-uitbreidingen.  

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="enhanced-jailbreak-detection-in-compliance-reporting---2198738---"></a>Verbeterde jailbreakdetectie in nalevingsrapporten<!-- 2198738 -->
De instellingsstatussen van de verbeterde jailbreakdetectie worden nu in alle nalevingsrapporten weergegeven in de beheerconsole.

### <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer

#### <a name="scope-tags-for-policies---1081974-eeready--"></a>Bereiktags voor beleid <!--1081974 eeready-->
U kunt [bereiktags maken](scope-tags.md) om de toegang tot Intune-resources te beperken. Voeg een bereiktag toe aan een roltoewijzing en voeg de bereiktag vervolgens toe aan een configuratieprofiel. De rol heeft dan alleen toegang tot resources met configuratieprofielen met overeenkomende bereiktags (of zonder bereiktag).

## <a name="week-of-august-14-2018"></a>Week van 14 augustus 2018

### <a name="macos-support-for-apple-device-enrollment-program----747651---"></a>macOS-ondersteuning voor het Apple Device Enrollment Program <!-- 747651 -->
Intune ondersteunt nu inschrijving van macOS-apparaten in het Apple Device Enrollment Program (DEP). Zie [MacOS-apparaten automatisch inschrijven met het Device Enrollment Program van Apple](device-enrollment-program-enroll-macos.md) voor meer informatie.

## <a name="week-of-july-23-2018"></a>Week van 23 juli 2018

### <a name="app-management"></a>Appbeheer

#### <a name="line-of-business-lob-app-support-for-macos----1895847---"></a>Ondersteuning voor LOB-apps (line-of-business) voor macOS <!-- 1895847 -->
Met Microsoft Intune kunnen macOS LOB-apps worden geïmplementeerd als **Vereist** of **Beschikbaar met inschrijving**. Eindgebruikers kunnen apps laten implementeren als **Beschikbaar** met behulp van de bedrijfsportal voor macOS of de [bedrijfsportalwebsite](https://portal.manage.microsoft.com).

#### <a name="ios-built-in-app-support-for-kiosk-mode----2051098---"></a>ondersteuning voor ingebouwde iOS-app voor de kioskmodus <!-- 2051098 -->
Naast de Store-apps en andere beheerde apps kunt u nu een geïntegreerde app (zoals Safari) selecteren die in de kioskmodus op een iOS-apparaat wordt uitgevoerd.

#### <a name="edit-your-office-365-pro-plus-app-deployments----2150145---"></a>Uw implementaties van de Office 365 Pro Plus-app bewerken <!-- 2150145 -->
Als beheerder van Microsoft Intune hebt u meer mogelijkheden om de implementaties van de Office 365 Pro Plus-app te bewerken. Bovendien hoeft u uw implementaties niet meer te verwijderen om een van de eigenschappen van het pakket te wijzigen. Selecteer in Azure Portal **Microsoft Intune** > **Client-apps** > **Apps**. Selecteer uw Office 365 Pro Plus-pakket in de lijst met apps.  


#### <a name="updated-intune-app-sdk-for-android-is-now-available----2744271--"></a>De bijgewerkte Intune App SDK voor Android is nu beschikbaar <!-- 2744271-->

Er is een bijgewerkte versie van de Intune APP SDK voor Android beschikbaar ter ondersteuning van de Android P-release. Als u een app-ontwikkelaar bent en de Intune SDK voor Android gebruikt, moet u de bijgewerkte versie van de Intune App SDK installeren om ervoor te zorgen dat Intune-functionaliteit binnen uw Android-apps blijft werken zoals verwacht op Android P-apparaten. Deze versie van de Intune App SDK biedt een ingebouwde invoegtoepassing waarmee de SDK-updates worden uitgevoerd. U hoeft geen bestaande code die is geïntegreerd, opnieuw te schrijven. Raadpleeg [Intune SDK voor Android](https://github.com/msintuneappsdk/ms-intune-app-sdk-android) voor meer informatie. Als u de oude badging-stijl voor Intune gebruikt, raden we u aan om het pictogram Werkmap te gebruiken. Ga naar [deze GitHub-opslagplaats](https://github.com/msintuneappsdk/intune-app-partner-badge) voor details over de huisstijl.


### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="use-smime-to-encrypt-and-sign-a-users-multiple-devices-----1333642---"></a>S/MIME gebruiken om meerdere apparaten van een gebruiker te coderen en ondertekenen <!-- 1333642 -->
Deze update bevat een S/MIME-e-mailversleuteling met een nieuw profiel voor een geïmporteerd certificaat (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > selecteer het platform > profieltype **Geïmporteerd PKCS-certificaat**). In Intune kunt u certificaten importeren in PFX-indeling. Intune kan deze certificaten dan leveren aan meerdere apparaten die zijn geregistreerd door één gebruiker. Dit omvat ook:

- Het systeemeigen iOS-e-mailprofiel ondersteunt het inschakelen van S/MIME-versleuteling met behulp van geïmporteerde certificaten in de PFX-indeling.
- De systeemeigen mail-app op Windows Phone 10-apparaten gebruikt automatisch het S/MIME-certificaat.
- De persoonlijke certificaten kunnen worden afgeleverd op meerdere platformen. Maar niet alle e-mail-apps ondersteunen S/MIME.
- Op andere platformen moet u mogelijk de mail-app handmatig configureren om S/MIME in te schakelen.  
- E-mail-apps die ondersteuning bieden voor S/MIME-versleuteling, kunnen het ophalen van certificaten voor S/MIME-e-mailversleuteling verwerken op een manier die een MDM niet kan ondersteunen, zoals het lezen van het certificaatarchief van de uitgever.

Wordt ondersteund op: Windows, Windows Phone 10, macOS, iOS, Android

#### <a name="create-device-compliance-policy-using-firewall-settings-on-macos-devices----1497640---"></a>Apparaatnalevingsbeleid maken met behulp van firewallinstellingen op macOS-apparaten <!-- 1497640 -->
Wanneer u een nieuw macOS-nalevingsbeleid maakt (**Apparaatcompatibiliteit** > **Beleid** > **Beleid maken**  >  **Platform: macOS** > **Systeembeveiliging**), ziet u enkele nieuwe instellingen bij **Firewall**: 

- **Firewall**: configureer hoe binnenkomende verbindingen in uw omgeving worden verwerkt.
- **Binnenkomende verbindingen**: **blokkeer** alle binnenkomende verbindingen, behalve de verbindingen die vereist zijn voor basisinternetservices, zoals DHCP, Bonjour en IPSec. Deze instelling blokkeert ook alle services voor delen.
- **Verborgen modus**: u kunt de verborgen modus **inschakelen** om te voorkomen dat het apparaat reageert op peilverzoeken. Het apparaat reageert nog wel op binnenkomende verzoeken voor toegestane apps.

Van toepassing op: macOS 10.12 en hoger

#### <a name="new-wi-fi-device-configuration-profile-for-windows-10-and-later----1879077---"></a>Nieuw Wi-Fi-configuratieprofiel voor Windows 10 en hoger <!-- 1879077 -->
Momenteel kunt u Wi-Fi-profielen importeren en exporteren met XML-bestanden. Met deze update kunt u een Wi-Fi-apparaatconfiguratieprofiel rechtstreeks in Intune maken, evenals in enkele andere platformen.

Om het profiel te maken, opent u **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** > **Wi-Fi**. 

Van toepassing op Windows 10 en hoger.

#### <a name="kiosk---obsolete-is-grayed-out-and-cant-be-changed----2149998-eeready---"></a>Kiosk - verouderd wordt grijs weergegeven en kan niet worden gewijzigd <!-- 2149998 eeready -->
De [Kiosk-functie](device-restrictions-windows-10.md#kiosk-preview---obsolete) (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** > **Apparaatbeperkingen**) is verouderd en wordt vervangen door [Kiosk-instellingen voor Windows 10 en hoger](kiosk-settings.md). Bij deze update wordt de functie **Kiosk - verouderd** grijs weergegeven en de gebruikersinterface kan niet worden gewijzigd of bijgewerkt. 

Zie voor het inschakelen van de kioskmodus [Kiosk-instellingen voor Windows 10 en hoger](kiosk-settings.md).

Is van toepassing op Windows 10 en hoger, Windows Holographic for Business

#### <a name="apis-to-use-3rd-party-certification-authorities----2184013---"></a>API’s gaan basiscertificeringsinstanties van derden gebruiken <!-- 2184013 -->
Bij deze update komt een Java-API voor waarmee u certificeringsinstanties van derden kunnen integreren met Intune en SCEP. Vervolgens kunnen gebruikers het SCEP-certificaat toevoegen aan een profiel en toepassen op apparaten via MDM.

Intune ondersteunt momenteel [SCEP-aanvragen met Active Directory Certificate Services](certificates-scep-configure.md).

#### <a name="toggle-to-show-or-not-show-the-end-session-button-on-a-kiosk-browser----2455253---"></a>In-/uitschakelen om de knop Sessie beëindigen wel of niet weer te geven in een Kiosk-browser <!-- 2455253 -->
U kunt configureren of Kiosk-browsers de knop Sessie beëindigen wel of niet weergeven. U ziet het besturingselement in **Apparaatconfiguratie** > **Kiosk (preview-versie)** > **Kiosk-webbrowser**. Indien ingeschakeld vraagt de app, wanneer een gebruiker op de knop klikt, om bevestiging om de sessie te beëindigen. Wanneer bevestigd, wist de browser alle browsegegevens en keert terug naar de standaard-URL.

#### <a name="create-an-esim-cellular-configuration-profile----2564077---"></a>Een mobiel eSIM-configuratieprofiel maken <!-- 2564077 -->
In **Apparaatconfiguratie** kunt u een mobiel eSIM-profiel maken. U kunt een bestand importeren dat mobiele activeringscodes bevat die u van uw mobiele operator krijgt. Vervolgens kunt u deze profielen implementeren op uw Windows 10-apparaten met eSIM LTE, zoals de Surface Pro LTE en andere voor eSIM geschikte apparaten.

Controleer of uw [apparaten eSIM-profielen ondersteunen](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data).

Van toepassing op Windows 10 en hoger. 




### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="automatically-mark-android-devices-enrolled-by-using-samsung-knox-mobile-enrollment-as-corporate----2404851---"></a>Android-apparaten die zijn ingeschreven met Knox Mobile Enrollment van Samsung automatisch markeren als ‘zakelijk’. <!-- 2404851 -->
Android-apparaten die zijn ingeschreven met Samsung Knox Mobile Enrollment worden nu standaard gemarkeerd als **zakelijk** onder **Apparaateigendom**. U hoeft zakelijke apparaten niet handmatig te identificeren met IMEI- of serienummers voordat wordt ingeschreven met Knox Mobile Enrollment.

### <a name="device-management"></a>Apparaatbeheer

#### <a name="bulk-delete-devices-on-devices-blade----1793693---"></a>Apparaten bulksgewijs verwijderen op apparatenblade <!-- 1793693 -->

U kunt nu meerdere apparaten tegelijk verwijderen op de blade Apparaten. Kies **Apparaten** > **Alle apparaten** > selecteer de apparaten die u wilt verwijderen > **Verwijderen**. In het geval van apparaten die niet kunnen worden verwijderd, wordt een melding weergegeven.

## <a name="week-of-july-16-2018"></a>Week van 16 juli 2018  

### <a name="more-opportunities-to-sync-in-the-company-portal-app-for-windows"></a>Meer synchronisatiemogelijkheden in de Bedrijfsportal-app voor Windows  
Met de Bedrijfsportal-app voor Windows kunt u nu een synchronisatie rechtstreeks vanuit de Windows-taakbalk en het menu Start in werking stellen. Deze functie is vooral nuttig als uw enige taak bestaat uit het synchroniseren van apparaten en verkrijgen van toegang tot bedrijfsbronnen. Klik voor toegang tot de nieuwe functie met de rechtermuisknop op het Bedrijfsportal-pictogram dat is vastgemaakt aan de taakbalk of het menu Start. Selecteer in de menu-opties (ook wel een Jump List genoemd) **Dit apparaat synchroniseren**. De Bedrijfsportal-app wordt geopend op de pagina **Instellingen** en de synchronisatie starten. Zie [Wat is er nieuw in de gebruikersinterface](whats-new-app-ui.md) voor een overzicht van de nieuwe functionaliteit.   

### <a name="new-browsing-experiences-in-the-company-portal-app-for-windows"></a>Nieuwe bladerervaringen in de Bedrijfsportal-app voor Windows  

Wanneer u bladert of apps zoekt in de Bedrijfsportal-app voor Windows, kunt u nu schakelen tussen de bestaande **Tegels**-weergave en de recent toegevoegde **Details**-weergave. De nieuwe weergave bevat informatie over toepassingen, zoals de naam, de uitgever, de publicatiedatum en de installatiestatus.  

De pagina **Apps** bevat de weergave **Geïnstalleerd**, waarop u meer informatie kunt vinden over app-installaties die zijn voltooid en die nog bezig zijn. Zie [Wat is er nieuw in de gebruikersinterface](whats-new-app-ui.md) voor het uiterlijk van de nieuwe weergave.  
### <a name="improved-company-portal-app-experience-for-device-enrollment-managers"></a>Verbeterde Bedrijfsportal-app-ervaring voor gebruikers van de apparaatinschrijvingsmanagers  
Wanneer een apparaatinschrijvingsmanager (DEM) zich aanmeldt bij de Bedrijfsportal-app voor Windows, wordt nu in de app alleen het huidige DEM-apparaat weergegeven dat wordt uitgevoerd. Dankzij deze verbetering treden er minder time-outs op. Deze time-outs traden voorheen op wanneer de app probeerde alle apparaten met DEM-registratie weer te geven.  


## <a name="week-of-july-9-2018"></a>Week van 9 juli 2018

### <a name="app-management"></a>Appbeheer

### <a name="block-app-access-based-on-unapproved-device-vendors-and-models-----1425689----"></a>App-toegang blokkeren op basis van niet-goedgekeurde apparaatleveranciers en -modellen <!-- 1425689 ! -->
De Intune-IT-beheerder kan via het Intune-app-beveiligingsbeleid een lijst laten opstellen met Android-fabrikanten en/of iOS-modellen. De IT-beheerder kan een met puntkomma's gescheiden lijst van fabrikanten voor Android-beleid en apparaatmodellen voor iOS-beleid verstrekken. Intune-app-beveiligingsbeleid is alleen van toepassing op Android en iOS. Er zijn twee afzonderlijke acties die kunnen worden uitgevoerd op basis van de opgegeven lijst:
- Het blokkeren van toegang tot een app voor apparaten die niet in de lijst voorkomen.
- Of het selectief wissen van bedrijfsgegevens op apparaten die niet in de lijst voorkomen. 

De gebruiker heeft geen toegang tot de beoogde toepassing als niet is voldaan aan de vereisten van het beleid. Afhankelijk van de instellingen wordt de gebruiker geblokkeerd of worden zakelijke gegevens selectief in de app gewist. Op iOS-apparaten vereist deze functie dat toepassingen (zoals WXP, Outlook, Managed Browser, Yammer) integreren met de Intune APP SDK opdat deze functie wordt afgedwongen voor de doeltoepassingen. Deze integratie vindt doorlopend plaats en is afhankelijk van de specifieke toepassingsteams. Op Android vereist deze functie de meest recente versie van de bedrijfsportal. 

Op apparaten van eindgebruikers moet de Intune-client actie ondernemen op basis van een eenvoudige overeenkomst met de tekenreeksen die zijn opgegeven in de Intune-blade Beveiligingsbeleid van toepassing. Dit is volledig afhankelijk van de waarde die het apparaat rapporteert. De IT-beheerder wordt dan ook aangemoedigd ervoor te zorgen dat het bedoelde gedrag correct is. Dit kan worden bereikt door deze instelling te testen voor verschillende fabrikanten en modellen en voor een kleine groep gebruikers. Selecteer in Microsoft Intune **Client-apps** > **App-beveiligingsbeleid** om app-beveiligingsbeleidsregels weer te geven en toe te voegen. Zie [What are app protection policies](app-protection-policy.md) (Wat is beveiligingsbeleid voor apps) en [Selectively wipe data using app protection policy access actions in Intune](app-protection-policies-access-actions.md) (Gegevens selectief wissen met toegangsacties van beveiligingsbeleid voor apps in Intune) voor meer informatie over beveiligingsbeleid voor apps.

### <a name="access-to-macos-company-portal-pre-release-build----1734766---"></a>Toegang tot de voorlopige versie van de macOS-bedrijfsportal <!-- 1734766 -->
U kunt zich met Microsoft AutoUpdate registreren voor het vroeg ontvangen van builds door deel te nemen aan het Insider-programma. Als u zich registreert, kunt u de bijgewerkte bedrijfsportal gebruiken voordat deze beschikbaar is voor uw eindgebruikers. Zie de [Microsoft Intune-blog](https://blogs.technet.microsoft.com/intunesupport/2018/07/13/use-microsoft-autoupdate-for-early-access-to-the-macos-company-portal-app/)voor meer informatie.

## <a name="week-of-july-2-2018"></a>Week van 2 juli, 2018

### <a name="app-management"></a>Appbeheer

#### <a name="monitor-ios--app-configuration-status-per-device----880037---"></a>Configuratiestatus van een iOS-app per apparaat controleren <!-- 880037 -->
Als Microsoft Intune-beheerder kunt u de configuratiestatus van iOS-apps voor elk beheerd apparaat controleren. Selecteer vanaf **Microsoft Intune** in Azure Portal de optie **Apparaten** > **Alle apparaten**. Selecteer in de lijst met beheerde apparaten een specifiek apparaat om een blade voor het apparaat weer te geven. Selecteer **App-configuratie** op de apparaatblade.

#### <a name="access-actions-for-app-protection-policies----1483510---"></a>Acties voor het apps-beveiligingsbeleid weergeven <!-- 1483510 -->
U kunt het beleid voor app-beveiliging expliciet configureren voor het blokkeren van niet-compatibele apparaten, het wissen van gegevens op deze apparaten of het verzenden van waarschuwingen naar deze apparaten. Met de actie *Wissen* worden bedrijfsgegevens van een apparaat verwijderd. Als een wisbewerking wordt uitgevoerd, wordt de gebruiker van het apparaat geïnformeerd over de reden en over de stappen om de gegevens te herstellen. Voor sommige instellingen, zoals de minimale versie van het besturingssysteem, moet u meerdere acties toepassen, bijvoorbeeld blokkeren en wissen. Deze acties worden geactiveerd wanneer de app wordt gestart.

#### <a name="selective-wipe-of-organizations-app-data----1507030---"></a>Selectief wissen van de app-gegevens van een organisatie <!-- 1507030 -->
Beheerders kunnen nu een selectieve wisbewerking van de gegevens van de organisatie als een nieuwe actie configureren wanneer niet wordt voldaan aan de voorwaarden van de toegangsinstellingen voor toepassingsbeveiligingsbeleid.  Dankzij deze functie kunnen beheerders gevoelige organisatiegegevens automatisch beveiligen en verwijderen uit toepassingen op basis van vooraf geconfigureerde criteria.

#### <a name="revoking-an-ios-app-purchased-through-vpp----1777384---"></a>Een iOS-app intrekken die is aangeschaft via VPP <!-- 1777384 -->
Als Microsoft Intune-beheerder kunt u alle licenties intrekken voor een geselecteerde iOS-app die is gekocht via het Volume Purchase Program (VPP). U kunt gebruikers waarschuwen wanneer een app met gebruikerslicentie niet meer aan hen is toegewezen. Als u een app-licentie intrekt, wordt de desbetreffende VPP-app niet van het apparaat verwijderd. Als u een VPP-app wilt verwijderen, moet u de toewijzingsactie wijzigen in **Verwijderen**. Het aantal geregenereerde licenties wordt weergegeven in het knooppunt **Gelicentieerde apps** in de workload **App** van Intune. Zie [iOS-apps beheren die zijn aangeschaft via een volume-aankoopprogramma met Microsoft Intune](vpp-apps-ios.md) voor meer informatie over iOS VPP-apps.

#### <a name="updates-to-out-of-compliance-messages-in-company-portal-app----1832222---"></a>Updates in niet-compatibiliteitsberichten in de bedrijfsportal-app <!-- 1832222 -->
De berichten die apparaatgebruikers zien wanneer een apparaat niet compatibel is, zijn herzien. De berichten behouden de oorspronkelijke betekenis, maar zijn bijgewerkt met toegankelijkere taal en minder technisch jargon. Ook zijn koppelingen naar documentatie en herstelstappen vernieuwd, zodat deze bijgewerkt zijn.
De volgende tekst is een voorbeeld van tekst voor en na de update:
- **Voor**: *Dit apparaat heeft geen contact opgenomen met de Intune-service binnen de periode die is ingesteld door de IT-beheerder. Open de bedrijfsportal-app op het apparaat en klik op de knop Naleving controleren om dit probleem op te lossen.*
- **Na**: *Dit apparaat is al een tijdje niet ingecheckt bij uw organisatie. Open de bedrijfsportal-app op het apparaat en tik op Instellingen controleren voor uw apparaat om opnieuw verbinding te maken*.

#### <a name="revoke-ios-vpp-app-license----1863797---"></a>iOS VPP-app-licentie intrekken <!-- 1863797 -->
Als beheerder kunt u een licentie voor een iOS VPP-app vrijmaken die is toegewezen aan een gebruiker of apparaat. Wanneer u een iOS VPP-app verwijdert, kunt u ook de app-licentie vrijmaken. Voordat u de app verwijdert, moet de gebruiker of het apparaat worden verwijderd uit de groep waarop de app is gericht. Als u de gebruiker of het apparaat verwijdert uit de groep, hoeft u de app niet opnieuw te installeren. Wanneer deze stappen zijn voltooid, kunt u de app-licentie toewijzen aan een andere gebruiker of een ander apparaat. Zie [Apps beheren die zijn gekocht via het iOS-volumeaankoopprogramma in Microsoft Intune](vpp-apps-ios.md) voor meer informatie over iOS VPP-app-licenties.

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963-eenotready---"></a>Apparaatcategorieën selecteren met behulp van de instellingen voor Toegang tot werk of school <!-- 1058963 eenotready --> 
Als u [apparaatgroeptoewijzing](https://docs.microsoft.com/en-us/intune/device-group-mapping) hebt ingeschakeld, wordt gebruikers van Windows 10 nu gevraagd een apparaatcategorie te selecteren na registratie via de knop **Verbinding maken** in **Instellingen** > **Accounts** > **Toegang tot werk- of schoolaccount**. 

#### <a name="use-samaccountname-as-the-account-username-for-email-profiles----1500307---"></a>Gebruik sAMAccountName als de accountgebruikersnaam voor e-mailprofielen <!-- 1500307 -->
U kunt de on-premises **sAMAccountName** gebruiken als de accountgebruikersnaam voor e-mailprofielen voor Android, iOS en Windows 10. U kunt ook het domein verkrijgen van het kenmerk `domain` of `ntdomain` in Azure Active Directory (Azure AD). Of geef een aangepast statisch domein op.

Om deze functie te gebruiken, moet u het kenmerk `sAMAccountName` van uw on-premises Active Directory-omgeving synchroniseren naar Azure AD.

Van toepassing op [Android](email-settings-android.md), [iOS](email-settings-ios.md), [Windows 10 en hoger](email-settings-windows-10.md)

#### <a name="see-device-configuration-profiles-in-conflict----1556983---"></a>Zie conflicterende apparaatconfiguratieprofielen <!-- 1556983 -->
In **Apparaatconfiguratie** wordt een lijst met de bestaande profielen weergegeven. Met deze update wordt een nieuwe kolom toegevoegd die gegevens bevat over conflicterende profielen. U kunt een rij met een conflict selecteren om de instelling en het profiel met het conflict te zien. 

Meer informatie over [configuratieprofielen beheren](device-profile-monitor.md#view-conflicts).

#### <a name="new-status-for-devices-in-device-compliance----2308882---"></a>Nieuwe status voor apparaten in apparaatcompatibiliteit <!-- 2308882 -->
De volgende nieuwe statussen zijn toegevoegd in **Apparaatcompatibiliteit** > **Beleid** > selecteer een beleid > **Overzicht**:
- geslaagd
- fout
- conflict
- in behandeling
- niet van toepassing Er wordt ook een afbeelding weergegeven waarin het aantal apparaten van een ander platform wordt weergegeven. Als u bijvoorbeeld een iOS-profiel kijkt, laat de nieuwe tegel ook het aantal niet-iOS-apparaten zien die ook zijn toegewezen aan dit profiel. Zie [Nalevingsbeleid voor apparaten](compliance-policy-monitor.md#view-status-of-device-policies).

#### <a name="device-compliance-supports-3rd-party-anti-virus-solutions----2325484---"></a>Apparaatcompatibiliteit ondersteunt antivirusoplossingen van derden <!-- 2325484 -->
Wanneer u een apparaatnalevingsbeleid maakt (**Apparaatcompatibiliteit** > **Beleid** > **Beleid maken** > **Platform: Windows 10 en hoger** > **Instellingen** > **Systeembeveiliging**), zijn er enkele nieuwe opties voor **[Apparaatbeveiliging](compliance-policy-create-windows.md#windows-10-and-later-policy-settings)**: 
- **Antivirussoftware**: als deze optie is ingesteld op **Vereisen**, kunt u de naleving controleren met behulp van antivirusoplossingen die zijn geregistreerd bij het Windows-beveiligingscentrum, zoals Symantec en Windows Defender. 
- **Antispyware**: als deze optie is ingesteld op **Vereisen**, kunt u de naleving controleren met behulp van antispywareoplossingen die zijn geregistreerd bij het Windows-beveiligingscentrum, zoals Symantec en Windows Defender. 

Van toepassing op Windows 10 en hoger 

### <a name="device-enrollment"></a>Apparaatinschrijving

####  <a name="devices-without-profiles-column-in-the-list-of-enrollment-program-tokens----1853904---"></a>Kolom met apparaten zonder profiel in de lijst met tokens voor het inschrijvingsprogramma <!-- 1853904 -->
De lijst met tokens voor het inschrijvingsprogramma bevat een nieuwe kolom met het aantal apparaten waaraan geen profiel is toegewezen. Dit helpt beheerders bij het toewijzen van profielen aan deze apparaten voordat ze deze toekennen aan gebruikers. Als u de nieuwe kolom wilt zien, gaat u naar **Apparaatinschrijving** > **Apple-inschrijving** > **Tokens voor het inschrijvingsprogramma**.

### <a name="device-management"></a>Apparaatbeheer

#### <a name="google-name-changes-for-android-for-work-and-play-for-work---842873---"></a>Google-naamwijzigingen voor Android for Work en Play for Work <!--842873 -->
Intune heeft de Android for Work-terminologie bijgewerkt om de wijzigingen in de Google-huisstijl te weerspiegelen. De termen Android for Work en Play for Work worden niet meer gebruikt. Afhankelijk van de context wordt andere terminologie gebruikt:
- Android Enterprise verwijst naar de algemene moderne Android-beheerstack.
- Werkprofiel of Profieleigenaar verwijst naar BYOD-apparaten die worden beheerd met werkprofielen.
- Beheerde Google Play verwijst naar de Google App Store.

#### <a name="rules-for-removing-devices----1609459---"></a>Regels voor het verwijderen van apparaten <!-- 1609459 -->
Er zijn nieuwe regels beschikbaar waarmee u automatisch apparaten kunt verwijderen die een aantal dagen niet zijn ingecheckt. U kunt dit aantal instellen. Ga naar het deelvenster **Intune**, selecteer **Apparaten** en selecteer vervolgens **Regels voor opschonen van apparaat** om de nieuwe regel te zien.

#### <a name="corporate-owned-single-use-support-for-android-devices----1630973---"></a>COSU-ondersteuning (Corporate-Owned, Single Use) voor Android-apparaten <!-- 1630973 -->

Intune ondersteunt nu maximaal beheerde, vergrendelde Android-apparaten in de kiosk-stijl. Hierdoor kunnen beheerders het gebruik van een apparaat verder vergrendelen tot een enkele app of een klein aantal apps en kan worden voorkomen dat gebruikers andere apps inschakelen of andere bewerkingen uitvoeren op het apparaat. Om Android-kiosk in te stellen, gaat u naar Intune > **Apparaatinschrijving** > **Android-inschrijving** > **Kiosk- en taakapparaatinschrijvingen**. Zie [Inschrijving van kioskapparaten voor Android Enterprise instellen](android-kiosk-enroll.md) voor meer informatie.

#### <a name="per-row-review-of-duplicate-corporate-device-identifiers-uploaded----2203794--"></a>Controle per rij van geüploade dubbele zakelijke apparaat-id's <!-- 2203794-->
Tijdens het uploaden van bedrijfs-id's geeft Intune nu een lijst weer met dubbele waarden en hebt u de optie om de bestaande gegevens te vervangen of te behouden. Het rapport wordt weergegeven als er dubbele waarden zijn nadat u **Apparaatinschrijving** > **Zakelijke apparaat-id's** > **Id's toevoegen** hebt gekozen. 

#### <a name="manually-add-corporate-device-identifiers----2203803---"></a>Zakelijke apparaat-id's handmatig toevoegen <!-- 2203803 -->
U kunt bedrifjsapparaat-id's nu handmatig toevoegen. Kies **Apparaatinschrijving** > **Zakelijke apparaat-id’s** > **Toevoegen**. 

## <a name="week-of-june-25-2018"></a>Week van 25 juni 2018

### <a name="pradeo---new-mobile-threat-defense-partner----1169249---"></a>Pradeo: nieuwe Mobile Threat Defense-partner <!-- 1169249 -->

U kunt de toegang van mobiele apparaten tot bedrijfsresources beheren door middel van voorwaardelijke toegang op basis van een risicoanalyse die door Pradeo wordt uitgevoerd. Pradeo is een oplossing voor beveiliging tegen bedreigingen op mobiele apparaten die met Microsoft Intune is geïntegreerd.

## <a name="week-of-june-18-2018"></a>Week van 18 juni 2018

### <a name="edge-mobile-support-for-intune-app-protection-policies----1817882---"></a>Mobiele ondersteuning in Edge voor beveiligingsbeleid voor apps in Intune <!-- 1817882 -->

De Microsoft Edge-browser voor mobiele apparaten biedt nu ondersteuning voor het beveiligingsbeleid voor apps dat in Intune is gedefinieerd.

## <a name="week-of-june-11-2018"></a>Week van 11 juni 2018

### <a name="use-fips-mode-with-the-ndes-certificate-connector----1333688---"></a>De FIPS-modus gebruiken met de NDES-certificaatconnector <!-- 1333688 -->
Wanneer u de NDES-certificaatconnector installeert op een computer waarop de FIPS-modus (Federal Information Processing Standard) is ingeschakeld, werkt het uitgeven en intrekken van certificaten niet zoals verwacht. Deze update bevat ondersteuning voor FIPS met de NDES-certificaatconnector. 

Deze update bevat verder:

- Voor de NDES-certificaatconnector is .NET 4.5 Framework vereist. Dit wordt automatisch geleverd bij Windows Server 2016 en Windows Server 2012 R2. Eerder was .NET 3.5 Framework de minimaal vereiste versie.
- TLS 1.2-ondersteuning wordt geleverd met de NDES-certificaatconnector. Als de server met daarop de NDES-certificaatconnector TLS 1.2 ondersteunt, wordt TLS 1.2 gebruikt. Als de server TLS 1.2 niet ondersteunt, wordt TLS 1.1 gebruikt. Momenteel wordt TLS 1.1 gebruikt voor verificatie tussen de apparaten en de server.

Zie [SCEP-certificaten configureren en gebruiken](certificates-scep-configure.md) en [PKCS-certificaten configureren en gebruiken](certficates-pfx-configure.md) voor meer informatie.

## <a name="week-of-june-4-2018"></a>Week van 4 juni 2018

### <a name="app-management"></a>Appbeheer

#### <a name="retrieve-the-associated-app-user-model-id-aumid-for-microsoft-store-for-business-apps-in-kiosk-mode----1560077----"></a>De bijbehorende app-gebruikersmodel-id (AUMID) ophalen voor de Microsoft Store voor Bedrijven-apps in de kioskmodus <!-- 1560077 ! -->
Intune kan nu de app-gebruikersmodel-id's (AUMID's) voor Microsoft Store voor Bedrijven-apps (WSfB) ophalen voor een verbeterde configuratie van het kioskprofiel.

Raadpleeg [Apps die u hebt aangeschaft in Microsoft Store voor Bedrijven, beheren met Microsoft Intune](windows-store-for-business.md) voor meer informatie over Microsoft Store voor Business-apps.

#### <a name="new-company-portal-branding-page----1916370---"></a>Nieuwe huisstijlpagina Bedrijfsportal <!-- 1916370 -->
De huisstijlpagina Bedrijfsportal heeft een nieuwe indeling, berichten en knopinfo.


### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="support-for-palo-alto-networks-globalprotect-vpn-profiles----1333680-eeready----"></a>Ondersteuning voor Palo Alto Networks GlobalProtect VPN-profielen <!-- 1333680 eeready ! -->
Met deze update kunt u Palo Alto Networks GlobalProtect kiezen als VPN-verbindingstype voor VPN-profielen in Intune (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Profieltype** > **VPN**). In deze versie worden de volgende platformen ondersteund: 

- iOS
- Windows 10

#### <a name="additions-to-local-device-security-options-settings----1403702---"></a>Toevoegingen aan instellingen voor de beveiligingsopties van lokale apparaten <!-- 1403702 -->
U kunt nu aanvullende instellingen voor de beveiligingsopties van lokale apparaten voor Windows 10-apparaten configureren. Er zijn extra instellingen beschikbaar voor Microsoft Network Client, Microsoft-netwerkserver, toegang tot het netwerk en beveiliging en interactief aanmelden. U vindt deze instellingen in de Endpoint Protection-categorie wanneer u een configuratiebeleid voor Windows 10-apparaten maakt.

#### <a name="enable-kiosk-mode-on-windows-10-devices----1560072----"></a>Kioskmodus inschakelen op Windows 10-apparaten <!-- 1560072 ! -->
Op Windows 10-apparaten kunt u een configuratieprofiel maken en de kioskmodus inschakelen (**Apparaatconfiguratie** > **Profielen** > **Profiel maken**  >  **Windows 10** > **Apparaatbeperkingen** > **Kioskmodus**). In deze update is de naam van de instelling **Kiosk (preview)** gewijzigd in **Kiosk (verouderd)**. Het gebruik van **Kiosk (verouderd)** wordt niet meer aanbevolen maar de optie blijft nog werken tot de update van juli. **Kiosk (verouderd)** wordt vervangen door het nieuwe profieltype **Kiosk** (**Profiel maken** > **Windows 10** > **Kiosk (preview)**). Dit profiel bevat de instellingen voor het configureren van kiosken in Windows 10 RS4 en hoger.

Van toepassing op Windows 10 en hoger.

#### <a name="device-profile-graphical-user-chart-is-back----2160133---"></a>De grafische gebruikersgrafiek van het apparaatprofiel is terug <!-- 2160133 -->
Bij het verbeteren van de aantallen die in de grafische gebruikersgrafiek van het apparaatprofiel (**Apparaatconfiguratie** > **Profielen** > selecteer een bestaand profiel > **Overzicht**) worden weergegeven, was de grafische gebruikersgrafiek tijdelijk verwijderd.

In deze update is de grafische gebruikersgrafiek terug. Deze wordt weergegeven in de Azure Portal.

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="support-for-windows-autopilot-enrollment-without-user-authentication----1165118-wnready---"></a>Ondersteuning voor Windows Autopilot-inschrijving zonder gebruikersverificatie <!-- 1165118 wnready -->
Intune ondersteunt nu Windows Autopilot-inschrijving zonder gebruikersverificatie. Dit is een nieuwe optie in het implementatieprofiel Windows AutoPilot; 'Automatische piloot implementatiemodus' is ingesteld op 'Zelf-implementerend'.  Het apparaat moet build 17672 of hoger van Windows 10 Insider Preview bevatten en beschikken over een TPM 2.0-chip voor dit type inschrijving. Omdat er geen gebruikersverificatie is vereist, moet u deze optie alleen toewijzen aan apparaten waartoe u fysiek toegang hebt.

#### <a name="new-languageregion-setting-when-configuring-oobe-for-autopilot----1821766-eeready---"></a>Nieuwe taal-/landinstelling wanneer u OOBE configureert voor AutoPilot <!-- 1821766 eeready -->
Er is een nieuwe configuratie-instelling beschikbaar om de taal en regio in te stellen voor AutoPilot-profielen tijdens de Out-of-Box Experience. Om de nieuwe instelling te zien, kiest u **Apparaatinschrijving** > **Windows-inschrijving** > **Implementatieprofielen** > **Profiel maken** > **Implementatiemodus** = **Zelf-implementerend** > **Standaardwaarden geconfigureerd**.

#### <a name="new-setting-for-configuring-device-keyboard----1821768---"></a>Nieuwe instelling voor het configureren van het apparaattoetsenbord <!-- 1821768 -->
Er is een nieuwe configuratie-instelling waarmee u tijdens de Out of Box Experience het toetsenbord voor AutoPilot-profielen kunt instellen. Om de nieuwe instelling te zien, kiest u **Apparaatinschrijving** > **Windows-inschrijving** > **Implementatieprofielen** > **Profiel maken** > **Implementatiemodus** = **Zelf-implementerend** > **Standaardwaarden geconfigureerd**.

#### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>AutoPilot-profielen verplaatst naar de groep met <!-- 1877935 -->
AutoPilot-implementatieprofielen kunnen worden toegewezen aan Azure AD-groepen die AutoPilot-apparaten bevatten.

### <a name="device-management"></a>Apparaatbeheer

#### <a name="set-compliance-by-device-location----851881----"></a>Naleving instellen per apparaatlocatie <!-- 851881 ! -->
In sommige situaties wilt u mogelijk de toegang beperken tot bedrijfsresources op een specifieke locatie, gedefinieerd door een netwerkverbinding. U kunt nu een nalevingsbeleid maken (**Apparaatnaleving** > **Locaties**) op basis van het IP-adres van het apparaat. Als het apparaat wordt verplaatst naar een locatie buiten het IP-bereik, heeft het apparaat geen toegang meer tot bedrijfsresources.

Is van toepassing op: Android-apparaten 6.0 en hoger, met de bijgewerkte Bedrijfsportal-app

#### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>De installatie van consumenten-apps en -ervaringen op Windows 10 Enterprise RS4 Autopilot-apparaten voorkomen<!-- 1621980 -->
U kunt voorkomen dat consumenten-apps en -ervaringen op uw apparaten met Windows 10 Enterprise RS4 AutoPilot kunnen worden geïnstalleerd. Om deze functie te zien, gaat u naar **Intune** > **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Platform** = **Windows 10 of hoger** > **Profieltype** = **Apparaatbeperkingen** > **Configureren** > **Windows Spotlight** > **Consumentenfuncties**. 

#### <a name="uninstall-the-latest-from-windows-10-software-updates----1732948-eeready---"></a>De nieuwste versie van software-updates voor Windows 10 verwijderen <!-- 1732948 eeready -->
Indien u een probleem ontdekt op uw Windows 10-computers, dan kunt u de meest recente functie-update of de nieuwste kwaliteitsupdate verwijderen (terugdraaien). U kunt alleen een functie- of kwaliteitsupdate verwijderen voor het servicekanaal waarop het apparaat zich bevindt. Door de verwijdering wordt een beleid geactiveerd waarmee de vorige update op uw Windows 10-computers wordt hersteld. Specifiek voor functie-updates kunt u de tijd beperken van 2 tot 60 dagen waarin een verwijdering van de meest recente versie kan worden toegepast. Als u verwijderopties voor software-update wilt instellen, selecteert u **Software-updates** in de blade **Microsoft Intune** binnen Azure Portal. Kies vervolgens **Windows 10-updateringen** op de blade **Software-updates**. U kunt vervolgens de optie **Verwijderen** kiezen in de sectie **Overzicht**.

#### <a name="search-all-devices-for-imei-and-serial-number----1793685---"></a>Op alle apparaten zoeken naar IMEI-nummer en serienummer <!-- 1793685 -->
U kunt nu zoeken naar IMEI-nummers en serienummers op de blade Alle apparaten (e-mailadres, apparaatnaam en managementnaam zijn nog steeds beschikbaar). Kies in Intune **Apparaten** > **Alle apparaten** > voer de zoekopdracht in het zoekvak in.

#### <a name="management-name-field-will-be-editable----1875989---"></a>Het veld Managementnaam kan worden bewerkt <!-- 1875989 -->
U kunt nu het veld met de managementnaam bewerken op de blade **Eigenschappen** van een apparaat. Als u dit veld wilt bewerken, kiest u **Apparaten** > **Alle apparaten** > kies het apparaat > **Eigenschappen**. U kunt het veld Managementnaam gebruiken om een apparaat op unieke wijze te identificeren.

#### <a name="new-all-devices-filter-device-category----1878520---"></a>Nieuw filter Alle apparaten: Apparaatcategorie <!-- 1878520 -->
U kunt nu de lijst **Alle apparaten** filteren op apparaatcategorie. Als u dit wilt doen, kiest u **Apparaten** > **Alle apparaten** > **Filter** > **Apparaatcategorie**.

#### <a name="use-teamviewer-to-screen-share-ios-and-macos-devices----1985547---"></a>TeamViewer gebruiken voor het delen van schermen op iOS- en MacOS-apparaten <!-- 1985547 -->
Beheerders kunnen nu verbinding maken met [TeamViewer](device-profile-android-teamviewer.md) en een sessie voor het delen van schermen starten met iOS- en macOS-apparaten. iPhone-, iPad- en MacOS-gebruikers kunnen hun schermen live delen met andere pc's of mobiele apparaten. 

#### <a name="multiple-exchange-connector-support----2070451---"></a>Ondersteuning voor meerdere Exchange Connectors <!-- 2070451 -->
U bent niet langer beperkt tot één Microsoft Intune Exchange Connector per tenant. Intune ondersteunt nu meerdere Exchange Connectors, zodat u voorwaardelijke toegang van Intune kunt instellen met meerdere on-premises Exchange-organisaties.

Met een on-premises Exchange Connector voor Intune kunt u apparaattoegang tot uw on-premises Exchange-postvakken beheren op basis van of een apparaat is ingeschreven bij Intune en voldoet aan het Intune-nalevingsbeleid voor apparaten. Als u een connector wilt instellen, downloadt u de on-premises Exchange Connector voor Intune vanaf Azure Portal en installeert u deze op een server in uw Exchange-organisatie. Kies op het Microsoft Intune-dashboard **On-premises toegang** en kies vervolgens onder **Installatie** de optie **Exchange ActiveSync-connector**. Download de on-premises Exchange Connector en installeer deze op een server in uw Exchange-organisatie. Nu u niet meer beperkt bent tot één Exchange Connector per tenant, kunt u, als u extra Exchange-organisaties hebt, dit zelfde proces volgen om een connector te downloaden en installeren voor elke extra Exchange-organisatie.

#### <a name="new-device-hardware-detail-ccid----2156657---"></a>Nieuw apparaathardwaredetail: CCID <!-- 2156657 -->
De CCID-informatie (Chip Card Interface Device) is nu opgenomen voor elk apparaat. Als u deze wilt zien, kiest u **Apparaten** > **Alle apparaten** > kies een apparaat > **Hardware**> controleer onder **Netwerkdetails**>

#### <a name="assign-all-users-and-all-devices-as-scope-groups----2196803---"></a>Alle gebruikers en apparaten toewijzen als bereikgroepen <!-- 2196803 -->
U kunt nu alle gebruikers, alle apparaten, en alle gebruikers en alle apparaten in bereikgroepen toewijzen. Kies hiervoor **Intune-rollen** > **Alle rollen** > **Beleid en profielbeheer** > **Toewijzingen** > kies een toewijzing > **Bereik (groepen)**.

#### <a name="udid-information-now-included-for-ios-and-macos-devices----2219806-wnready--"></a>UDID-informatie is nu opgenomen voor iOS- en macOS-apparaten <!-- 2219806 wnready-->
Als u de unieke apparaat-id (UDID) voor iOS- en macOS-apparaten wilt zien, gaat u naar **Apparaten** > **Alle apparaten** > kies een apparaat > **Hardware**. UDID is alleen beschikbaar voor bedrijfsapparaten (zoals ingesteld onder **Apparaten** > **Alle apparaten** > kies een apparaat > **Eigenschappen** > **Apparaateigendom**).

### <a name="intune-apps"></a>Intune-apps

#### <a name="improved-troubleshooting-for-app-installation----928990---"></a>Verbeterde probleemoplossing voor app-installatie <!-- 928990 -->
Op apparaten die met Microsoft Intune MDM worden beheerd, mislukken app-installaties wel eens. Als deze apps niet kunnen worden geïnstalleerd, is het soms lastig om de reden van het probleem te achterhalen of om het probleem op te lossen. We brengen een openbare preview-versie uit van de functies voor het oplossen van problemen met apps. U ziet een nieuw knooppunt, **Beheerde apps**, onder elk apparaat. Hier ziet u de apps die via Intune MDM zijn geleverd. In het knooppunt ziet u een lijst met de installatiestatussen van de apps. Als u een bepaalde app selecteert, ziet u de probleemoplossingsweergave voor die app. In de probleemoplossingsweergave ziet u de gehele levenscyclus van de app, zoals wanneer de app is gemaakt, gewijzigd, gebruikt en geleverd aan een apparaat. En als installatie van de app niet is geslaagd, wordt de foutcode weergegeven en een informatief bericht over de oorzaak van de fout. 

#### <a name="intune-app-protection-policies-and-microsoft-edge----1818968---"></a>Beveiligingsbeleid voor apps in Intune en Microsoft Edge <!-- 1818968 -->
De Microsoft Edge-browser voor mobiele apparaten (iOS en Android) biedt nu ondersteuning voor het app-beveiligingsbeleid van Microsoft Intune. Gebruikers van iOS- en Android-apparaten die zich in de Edge-toepassing aanmelden met hun zakelijk Azure AD-account worden beveiligd door Intune. Op iOS-apparaten kunnen gebruikers dankzij het beleid **Beheerde browser vereisen voor webinhoud** koppelingen openen in Edge wanneer het wordt beheerd.

## <a name="week-of-may-14-2018"></a>Week van 14 mei 2018

### <a name="app-management"></a>Appbeheer

#### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>Installatie van beleid, apps en certificaat- en netwerkprofielen vereisen <!-- 1553555 -->

Beheerders kunnen de toegang tot het Windows 10 RS4-bureaublad voor eindgebruikers blokkeren totdat beleid, apps en certificaat- en netwerkprofielen worden geïnstalleerd tijdens de inrichting van AutoPilot-apparaten. Zie [Een pagina voor de status van de inschrijving instellen](windows-enrollment-status.md) voor meer informatie.

#### <a name="configuring-your-app-protection-policies----2144597-part-2---"></a>Beveiligingsbeleid voor apps configureren<!-- 2144597 Part 2 -->

Ga in de Azure-portal niet naar de serviceblade Intune-app-beveiliging maar naar Intune. Er is nu nog maar één locatie voor beleidsregels voor app-beveiliging in Intune. Al uw beleidsregels voor de beveiliging van apps staan al in de blade **Mobiele app** in Intune onder **App-beveiligingsbeleid**. Door deze integratie wordt het beheer van uw cloud vereenvoudigd. Alle beleidsregels voor de beveiliging van apps staan al in Intune en u kunt al uw eerder geconfigureerde beleid wijzigen. Het beleid voor Intune APP (beveiligingsbeleid voor apps) en voorwaardelijke toegang (CA) bevindt zich nu onder **Voorwaardelijke toegang**, te vinden in het gedeelte **Beheren** in de blade **Microsoft Intune** of in het gedeelte **Beveiliging** in de blade **Azure Active Directory**. Zie [Voorwaardelijke toegang in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) voor meer informatie over het wijzigen van het beleid voor voorwaardelijke toegang. Zie [Wat is beveiligingsbeleid voor apps?](app-protection-policy.md) voor meer informatie.

## <a name="week-of-may-7-2018"></a>Week van 7 mei 2018

### <a name="app-management"></a>Appbeheer

#### <a name="samsung-knox-mobile-enrollment-support---1112863--"></a>Ondersteuning voor Samsung Knox Mobile Enrollment<!--1112863-->

Wanneer u Intune met Samsung Knox Mobile Enrollment (KME) gebruikt, kunt u een groot aantal bedrijfseigen Android-apparaten inschrijven. Gebruikers op wifi- of mobiele netwerken kunnen inschrijven met een paar tikken wanneer ze hun apparaten voor het eerst inschakelen. Apparaten kunnen ook met Bluetooth of NFC worden ingeschreven als de Knox-registratie-app wordt gebruikt. Zie [Android-apparaten automatisch registreren met behulp van de Knox Mobile Enrollment van Samsung](android-samsung-knox-mobile-enroll.md) voor meer informatie.

#### <a name="requesting-help-in-the-company-portal-for-windows-10----1874137---"></a>Hulp aanvragen in de bedrijfsportal voor Windows 10 <!-- 1874137 -->

Vanuit de bedrijfsportal voor Windows 10 worden app-logboeken nu rechtstreeks naar Microsoft verzonden wanneer de gebruiker de werkstroom voor hulp bij een probleem in gang zet. Dit vereenvoudigt het detecteren en oplossen van problemen die aan Microsoft worden gemeld.

## <a name="week-of-april-23-2018"></a>Week van 23 april 2018

### <a name="app-management"></a>Appbeheer

#### <a name="passcode-support-for-mam-pin-on-android---1438086---"></a>Ondersteuning van de wachtwoordcode voor MAM-pincode op Android<!-- 1438086 -->

Intune-beheerders kunnen instellen dat een toepassing moet worden gestart om een wachtwoordcode af te dwingen in plaats van een numerieke MAM-pincode. Als dit is geconfigureerd, moet de gebruiker een wachtwoordcode instellen en gebruiken wanneer daarom wordt gevraagd, alvorens toegang te krijgen tot toepassingen met MAM-functionaliteit. Een wachtwoordcode wordt gedefinieerd als een numerieke pincode met ten minste één speciaal teken of een hoofdletter/kleine letter. Intune ondersteunt wachtwoordcodes op dezelfde manier als de bestaande numerieke pincodes: er kan een minimumlengte worden ingesteld en tekens en tekenreeksen mogen via de beheerconsole worden herhaald. Voor deze functie moet de meest recente versie van de bedrijfsportal voor Android zijn geïnstalleerd. Deze functie is al beschikbaar voor iOS.

#### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>Ondersteuning voor LOB-apps (line-of-business) voor macOS <!-- 1473977 -->
Microsoft Intune biedt de mogelijkheid om LOB-apps voor macOS te installeren vanuit Azure Portal. U kunt een macOS LOB-app aan Intune toevoegen nadat deze vooraf is verwerkt door het hulpprogramma dat beschikbaar is in GitHub. Kies op de blade **Intune** van Azure Portal **Client-apps**. Kies op de blade **Client-apps** **Apps** > **Toevoegen**. Selecteer op de blade **App toevoegen** de optie **Line-Of-Business-app**. 

#### <a name="built-in-all-users-and-all-devices-group-for-android-for-work-afw-app-assignment----1813073---"></a>Ingebouwde groepen Alle gebruikers en Alle apparaten voor app-toewijzing voor Android for Work (AFW) <!-- 1813073 -->
U kunt gebruikmaken van de ingebouwde groepen **Alle gebruikers** en **Alle apparaten** voor de app-toewijzing voor AFW. Zie [App-toewijzingen opnemen en uitsluiten in Microsoft Intune](apps-inc-exl-assignments.md) voor meer informatie.

#### <a name="intune-will-reinstall-required-apps-that-are-uninstalled-by-users----1947010---"></a>Vereiste apps die door gebruikers zijn verwijderd, worden opnieuw geïnstalleerd in Intune <!-- 1947010 -->
Als een eindgebruiker een vereiste app verwijdert, wordt de app in Intune automatisch binnen 24 uur opnieuw geïnstalleerd in plaats van te wachten op de herbeoordelingscyclus van 7 dagen.

### <a name="device-configuration"></a>Apparaatconfiguratie

####  <a name="device-profile-chart-and-status-list-show-all-devices-in-a-group----1449153-eeready---"></a>De profielgrafiek van het apparaat en de statuslijst geven alle apparaten in een groep weer <!-- 1449153 eeready -->
Wanneer u een apparaatprofiel configureert (**Apparaatconfiguratie** > **Profielen**), kunt u het apparaatprofiel, zoals iOS, kiezen. U kunt dit profiel toewijzen aan een groep met iOS-apparaten en niet-iOS-apparaten. De grafiek laat zien dat het profiel wordt toegepast op iOS- *en* niet-iOS-apparaten (**Apparaatconfiguratie** > **Profielen** > selecteer een bestaand profiel > **Overzicht**). Wanneer u de grafiek op het tabblad **Overzicht** selecteert, worden in **Apparaatstatus** alle apparaten in de groep weergegeven, niet alleen de iOS-apparaten. 

Met deze update wordt in de grafiek (**Apparaatconfiguratie** > **Profielen** > selecteer een bestaand profiel > **Overzicht**) alleen het aantal voor het specifieke apparaatprofiel weergegeven. Als bijvoorbeeld het apparaatprofiel wordt toegepast op iOS-apparaten, geeft de grafiek alleen het aantal iOS-apparaten weer. Als u de grafiek selecteert en de **apparaatstatus** opent, worden alleen de iOS-apparaten weergegeven.

Tijdens het maken van deze update is de grafiek tijdelijk verwijderd. 

#### <a name="always-on-vpn-for-windows-10---1333666---"></a>De optie Altijd aan voor VPN in Windows 10 <!--1333666 -->

Momenteel kan de optie [Altijd aan](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-auto-trigger-profile#always-on) worden gebruikt op Windows 10-apparaten door een aangepast VPN-profiel te gebruiken dat is gemaakt met OMA-URI.

Met deze update kunnen beheerders de optie Altijd aan rechtstreeks inschakelen in Intune in Azure Portal voor VPN-profielen in Windows 10. VPN-profielen met de optie Altijd aan maken automatisch verbinding wanneer:

- Gebruikers zich aanmelden op hun apparaten
- Het netwerk op het apparaat wijzigt
- Het scherm op het apparaat wordt ingeschakeld nadat het was uitgeschakeld

#### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Nieuwe printerinstellingen voor onderwijsprofielen <!-- 1308900 -->

Voor onderwijsprofielen zijn nieuwe instellingen beschikbaar onder de categorie **Printers**: **Printers**, **Standaardprinter**, **Nieuwe printers toevoegen**.

#### <a name="show-caller-id-in-personal-profile---android-for-work---1098984---"></a>Beller-id in persoonlijk profiel weergeven - Android for Work <!--1098984 -->
Wanneer u een persoonlijk profiel op een apparaat gebruikt, kunnen eindgebruikers de details van de beller-id van een zakelijke contactpersoon niet weergegeven. 

Er is een nieuwe instelling in **Android for Work** > **Apparaatbeperkingen** > **Instellingen voor werkprofiel**:
- Beller-id van zakelijk contactpersoon weergeven in persoonlijk profiel

Indien ingeschakeld (niet-geconfigureerd), worden de details van de beller die een zakelijke contactpersoon is, weergegeven in het persoonlijke profiel. Indien geblokkeerd, wordt het nummer van deze zakelijke contactpersoon niet weergegeven in het persoonlijke profiel. 

Van toepassing op: apparaten met Android-werkprofiel voor Android 6.0 en hoger

#### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252-----from-1802-and-1804--"></a>Er worden nieuwe Windows Defender Credential Guard-instellingen toegevoegd aan de Endpoint Protection-instellingen <!--1102252 --><!--from 1802 and 1804-->

In deze update, [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard) (**Apparaatconfiguratie** > **Profielen** > **Eindpuntbeveiliging**) zijn de volgende instellingen opgenomen: 

- **Windows Defender Credential Guard**: schakelt Credential Guard in met beveiliging op basis van virtualisatie. Het inschakelen van deze functie helpt om de referenties te beveiligen bij de volgende keer opstarten, wanneer **Niveau van platformbeveiliging met Beveiligd opstarten** en **Beveiliging op basis van virtualisatie** beide zijn ingeschakeld. Opties zijn onder andere:
  - **Uitgeschakeld**: Credential Guard wordt extern uitgeschakeld als deze eerder is ingeschakeld met de optie **Ingeschakeld zonder vergrendeling**.

  - **Ingeschakeld met UEFI-vergrendeling**: met deze optie kan Credential Guard niet worden uitgeschakeld met behulp van een registersleutel of via Groepsbeleid. Als u Credential Guard wilt uitschakelen nadat u deze instelling hebt gebruikt, moet u het Groepsbeleid instellen op Uitgeschakeld. Vervolgens verwijdert u de beveiligingsfunctie van elke computer, met een fysiek aanwezige gebruiker. Met deze stappen wordt de configuratie gewist die is behouden in UEFI. Zolang de UEFI-configuratie behouden blijft, is Credential Guard ingeschakeld.

  - **Uitgeschakeld zonder vergrendeling**: met deze optie kan Credential Guard extern worden uitgeschakeld via Groepsbeleid. Op de apparaten die gebruikmaken van deze instelling moet ten minste Windows 10 (versie 1511) worden uitgevoerd.

De volgende afhankelijke technologieën worden automatisch ingeschakeld bij het configureren van Credential Guard: 

  - **Beveiliging op basis van virtualisatie (VBS)**: schakelt Beveiliging op basis van virtualisatie (VBS) in bij de volgende keer opstarten. Beveiliging op basis van virtualisatie maakt gebruik van Windows Hypervisor om ondersteuning te bieden voor beveiligingsservices. Beveiligd opstarten is vereist.
  - **Beveiligd opstarten met directe geheugentoegang (DMA)**: hiermee schakelt u VBS in met Beveiligd opstarten en directe geheugentoegang. Voor DMA-beveiliging is hardwareondersteuning vereist. Deze wordt alleen ingeschakeld op apparaten die juist zijn geconfigureerd. 

#### <a name="use-a-custom-subject-name-on-scep-certificate----2064190---"></a>Een aangepaste onderwerpnaam gebruiken in een SCEP-certificaat <!-- 2064190 -->
U kunt de algemene naam **OnPremisesSamAccountName** gebruiken in een aangepast onderwerp voor een SCEP-certificaatprofiel. U kunt bijvoorbeeld `CN={OnPremisesSamAccountName})` gebruiken.

####  <a name="block-camera-and-screen-captures-on-android-for-work----1098977-eeready--"></a>De camera en schermopnamen blokkeren op Android for Work <!-- 1098977 eeready-->
Er zijn twee nieuwe eigenschappen beschikbaar die kunnen worden geblokkeerd wanneer u apparaatbeperkingen voor Android-apparaten configureert: 
- Camera: hiermee blokkeert u de toegang tot alle camera's op het apparaat
- Schermopname: hiermee blokkeert u de schermopname en voorkomt ook dat de inhoud wordt weergegeven op weergaveapparaten die geen beveiligde video-uitvoer hebben

Geldt voor Android for Work.


### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="new-enrollment-steps-for-users-on-devices-with-macos-high-sierra-10132---1734567---"></a>Nieuwe stappen voor registratie voor gebruikers op apparaten met macOS High Sierra 10.13.2+ <!--1734567 -->
macOS High Sierra 10.13.2 introduceert het concept Gebruiker goedgekeurd voor MDM-inschrijving. Met goedgekeurde inschrijvingen kan in Intune een aantal vertrouwelijke instellingen worden beheerd. Zie de ondersteuningsdocumentatie van Apple https://support.apple.com/HT208019 voor meer informatie.

Apparaten die zijn geregistreerd met behulp van de bedrijfsportal voor macOS, worden beschouwd als Niet door de gebruiker goedgekeurd, tenzij de eindgebruiker Systeemvoorkeuren opent en handmatig goedkeuring verleent. De bedrijfsportal voor macOS vraagt gebruikers van macOS 10.13.2 en hoger om hun registratie aan het einde van het registratieproces handmatig goed te keuren. De Intune-beheerconsole rapporteert of een geregistreerd apparaat door de gebruiker is goedgekeurd.



### <a name="device-management"></a>Apparaatbeheer

#### <a name="advanced-threat-protection-atp-and-intune-are-fully-integrated----eeready-1629303---"></a>ATP (Advanced Threat Protection) en Intune zijn volledig geïntegreerd<!-- EEready 1629303 -->

[Advanced Threat Protection (ATP)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection) geeft het risiconiveau van Windows 10-apparaten weer. In Windows Defender Security Center (ATP-portal) kunt u een verbinding maken met Microsoft Intune. Zodra de verbinding is gemaakt, wordt Intune-nalevingsbeleid gebruikt om het acceptabele bedreigingsniveau te bepalen. Als het bedreigingsniveau wordt overschreden, kan de toegang tot verschillende apps in uw organisatie worden geblokkeerd op basis van Azure AD-beleid (Azure Directory) voor voorwaardelijke toegang.

Met deze functie kunnen bestanden worden gescand, bedreigingen worden gedetecteerd en alle risico's op uw Windows 10-apparaten worden gerapporteerd via ATP.

Zie [ATP voor voorwaardelijke toegang inschakelen in Intune](advanced-threat-protection.md).

#### <a name="support-for-user-less-devices----1637553---"></a>Ondersteuning voor apparaten zonder gebruiker <!-- 1637553 -->
Intune ondersteunt de mogelijkheid om naleving te evalueren op een apparaat zonder gebruiker, zoals de Microsoft Surface Hub. Nalevingsbeleid kan worden gericht op specifieke apparaten. Naleving (en niet-naleving) kan worden vastgesteld voor apparaten waaraan geen gebruiker is gekoppeld.

#### <a name="delete-autopilot-devices----1713650---"></a>Autopilot-apparaten verwijderen <!-- 1713650 -->
Intune-beheerders kunnen [AutoPilot-apparaten verwijderen](enrollment-autopilot.md#delete-autopilot-devices).

#### <a name="improved-device-deletion-experience---1832333---"></a>Verbeterde ervaring bij het verwijderen van apparaten <!--1832333 -->
U hoeft geen bedrijfsgegevens meer te verwijderen of de fabrieksinstellingen op een apparaat te herstellen voordat u [een apparaat uit Intune verwijdert](devices-wipe.md#delete-devices-from-the-intune-portal).

Meld u voor deze nieuwe ervaring aan in Intune en selecteer **Apparaten** > **Alle apparaten** > de naam van het apparaat > **Verwijderen**.

Als u een bevestiging van het wissen of terugtrekken van een apparaat wilt blijven ontvangen, kunt u de standaard levenscyclusroute van een apparaat gebruiken door **Bedrijfsgegevens verwijderen** en **Fabrieksinstellingen terugzetten** uit te geven voordat u **Verwijderen** selecteert. 

#### <a name="play-sounds-on-ios-when-in-lost-mode----1947769---"></a>Geluid afspelen in iOS in de modus Apparaat verloren <!-- 1947769 -->
Wanneer iOS-apparaten onder supervisie in MDM (Mobile Device Management) in de modus [Apparaat verloren](device-lost-mode.md) zijn, kunt u [een geluid afspelen](device-locate.md#activate-lost-mode-sound-alert-on-an-ios-device) (**Apparaten** > **Alle apparaten** > selecteer een iOS-apparaat > **Overzicht** > **Meer**). Het geluid wordt afgespeeld totdat het apparaat niet meer de modus Apparaat verloren heeft of totdat een gebruiker het geluid op het apparaat uitschakelt. Van toepassing op apparaten met iOS 9.3 en hoger.

#### <a name="block-or-allow-web-results-in-searches-made-on-an-intune-device---1972804--"></a>Webresultaten blokkeren of toestaan in zoekopdrachten die zijn uitgevoerd op een Intune-apparaat <!--1972804-->

Beheerders kunnen nu webresultaten blokkeren in zoekopdrachten die zijn uitgevoerd op een apparaat.

#### <a name="improved-error-messaging-for-apple-mdm-push-certificate-upload-failure----2172331---"></a>Verbeterde foutberichten voor fouten bij het uploaden van Apple MDM-pushcertificaten <!-- 2172331 -->

In het foutbericht wordt uitgelegd dat dezelfde Apple ID moet worden gebruikt bij het vernieuwen van een bestaand MDM-certificaat.

#### <a name="test-the-company-portal-for-macos-on-virtual-machines----2216679---"></a>De bedrijfsportal voor macOS testen op virtuele machines <!-- 2216679 -->

We hebben een handleiding gepubliceerd om IT-beheerders te helpen bij het testen van de bedrijfsportal-app voor macOS op virtuele machines in Parallels Desktop en VMware Fusion. U vindt meer informatie in [virtuele macOS-machines inschrijven voor testen](macos-enroll.md#enroll-virtual-macos-machines-for-testing).


### <a name="user-interface"></a>Gebruikersinterface

#### <a name="improved-device-tiles-in-the-windows-10-company-portal---2213364---"></a>Verbeterde apparaattegels in de Windows 10-bedrijfsportal <!--2213364 -->

De tegels zijn bijgewerkt zodat ze toegankelijker zijn voor gebruikers met een beperkt gezichtsvermogen en beter werken op schermlezers.

#### <a name="send-diagnostic-reports-in-company-portal-app-for-macos----2216677---"></a>Diagnostische rapporten in de bedrijfsportal-app voor macOS verzenden <!-- 2216677 -->
De bedrijfsportal-app voor macOS-apparaten wordt bijgewerkt om de manier waarop gebruikers fouten in Intune rapporteren, te verbeteren. Vanuit de bedrijfsportal-app kunnen werknemers:

- Diagnostische rapporten rechtstreeks naar het Microsoft-ontwikkelteam uploaden.
- Via e-mail een incident-id aan het IT-ondersteuningsteam van uw bedrijf verzenden.

Zie [Fouten verzenden voor macOS](/intune-user-help/send-errors-macos) voor meer informatie.

#### <a name="intune-adapts-to-fluent-design-system-in-the-company-portal-app-for-windows-10----1195010-wnready---"></a>Intune wordt aangepast aan Fluent Design System in de bedrijfsportal-app voor Windows 10 <!-- 1195010 WNready -->
De Intune-bedrijfsportal-app voor Windows 10 is bijgewerkt met de [Fluent Design System-navigatieweergave](https://docs.microsoft.com/en-us/windows/uwp/design/basics/navigation-basics). Aan de zijkant van de app wordt een statische verticale lijst weergegeven met alle toplevelpagina's. Klik op een willekeurige koppeling om snel pagina's weer te geven en te schakelen tussen pagina's. Dit is de eerste van verschillende updates die onderdeel uitmaken van onze voortdurende inspanningen om een meer adaptieve, intuïtieve en vertrouwde versie van Intune te maken. Ga naar [Wat is er nieuw in de gebruikersinterface van de app?](whats-new-app-ui.md) om het bijgewerkte uiterlijk te bekijken.

## <a name="week-of-april-16-2018"></a>Week van 16 april 2018

#### <a name="use-cisco-anyconnect-client-for-ios----eeready-1333708---"></a>Cisco AnyConnect-client voor iOS gebruiken <!-- EEready 1333708 -->

Wanneer u een nieuw VPN-profiel voor iOS maakt, hebt u nu twee opties: **Cisco AnyConnect** en **Cisco Legacy AnyConnect**. Cisco AnyConnect-profielen bieden ondersteuning voor 4.0.7x en nieuwere versies. Bestaande iOS Cisco AnyConnect VPN-profielen krijgen het label **Cisco Legacy AnyConnect** en blijven op dezelfde manier werken met Cisco AnyConnect 4.0.5x en oudere versies.

> [!NOTE]
> Deze wijziging is alleen van toepassing op iOS. Er blijft slechts één Cisco AnyConnect-optie voor platforms van Android, Android for Work en macOS.

#### <a name="jamf-enrolled-macos-devices-can-now-register-with-intune----2370684---"></a>Via Jamf ingeschreven macOS-apparaten kunnen nu worden geregistreerd bij Intune <!-- 2370684 -->

In versie 1.3 en 1.4 van de bedrijfsportal voor macOS zijn Jamf-apparaten niet geregistreerd bij Intune. Dit probleem is opgelost in versie 1.4.2 van de macOS-portal.


## <a name="week-of-april-9-2018"></a>Week van 9 april 2018  
#### <a name="updated-help-experience-in-company-portal-app-for-android----1631531---"></a>Bijgewerkte Help-ervaring voor de bedrijfsportal-app voor Android <!-- 1631531 -->

We hebben de Help-ervaring in de bedrijfsportal-app voor Android bijgewerkt, zodat deze overeenkomt met de aanbevolen procedures voor het Android-platform. Wanneer gebruikers nu een probleem in de app tegenkomen, kunnen ze op **Menu** > **Help** tikken en:
- Logboeken met diagnostische gegevens uploaden naar Microsoft.
- Een e-mail verzenden waarin het probleem en de incident-id worden vermeld voor een ondersteuningsmedewerker.  

Als u de bijgewerkte Help-ervaring wilt bekijken, gaat u naar [Logboeken via e-mail verzenden](/intune-user-help/send-logs-to-your-it-admin-by-email-android) en [Fouten naar Microsoft verzenden](/intune-user-help/send-logs-to-microsoft-android).


#### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table----1471783---"></a>Nieuwe tabel met fouten bij inschrijving, trendgrafieken en oorzaken van fouten <!-- 1471783 -->

Op de overzichtspagina voor inschrijvingen kunt u de trend van mislukte inschrijvingen en de top vijf van oorzaken van fouten bekijken. Door te klikken op de grafiek of de tabel kunt u inzoomen op gegevens om advies voor probleemoplossing en suggesties voor herstel te krijgen.

#### <a name="update-where-to-configure-your-app-protection-policies----2144597---"></a>Bijwerken waar u uw app-beveiligingsbeleid configureert <!-- 2144597 -->

U wordt van de serviceblade **Intune-app-beveiliging** in Azure Portal tijdelijk omgeleid naar de blade **Mobiele app**. Al uw beleidsregels voor de beveiliging van apps staan al in de blade **Mobiele app** in Intune onder App-configuratie. Het enige verschil is dat u naar Intune gaat in plaats van naar Intune-app-beveiliging. In april 2018 wordt deze omleiding beëindigd en wordt de serviceblade **Intune-app-beveiliging** helemaal verwijderd, zodat er slechts één locatie voor het app-beveiligingsbeleid in Intune is. 

**Wat betekent dit voor mij?**
Deze wijziging is van invloed op zowel zelfstandige als hybride klanten (Intune met Configuration Manager) van Intune. Door deze integratie wordt het beheer van uw cloud vereenvoudigd.

**Wat moet ik doen om me voor te bereiden op deze wijziging?**
Label **Intune** als favoriet in plaats van de serviceblade **Intune-app-beveiliging** en zorg ervoor dat u bekend bent met de werkstroom voor het beleid voor app-beveiliging in de blade **Mobiele app** in Intune. U wordt slechts tijdelijk omgeleid. De blade **App-beveiliging** wordt uiteindelijk verwijderd. Alle beleidsregels voor de beveiliging van apps staan al in Intune en u kunt uw beleid voor voorwaardelijke toegang wijzigen. Zie [Voorwaardelijke toegang in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) voor meer informatie over het wijzigen van het beleid voor voorwaardelijke toegang. Zie [Wat is beveiligingsbeleid voor apps?](app-protection-policy.md) voor meer informatie. 


## <a name="week-of-april-2-2018"></a>Week van 2 april 2018

### <a name="intune-apps"></a>Intune-apps

#### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866---"></a>Update van de gebruikerservaring voor de bedrijfsportal-app voor iOS<!--1412866 -->
Er is een grote update uitgebracht van de gebruikerservaring voor de bedrijfsportal-app voor iOS. De update is voorzien van een volledig nieuw visueel ontwerp met een gemoderniseerd uiterlijk. De functionaliteit van de app is behouden. De gebruiksvriendelijkheid en toegankelijkheid zijn echter verhoogd.  

U ziet ook:
- Ondersteuning voor iPhone X.
- De app start sneller en de laadsnelheid is verhoogd, zodat gebruikers tijd besparen.
- Aanvullende voortgangsbalken om gebruikers de meest recente statusgegevens te bieden.
- Verbeteringen in de manier waarop gebruikers logboeken uploaden, zodat u het eenvoudiger kunt melden als er iets fout gaat.  

Ga naar [Wat is er nieuw in de gebruikersinterface van de app?](whats-new-app-ui.md) om het bijgewerkte uiterlijk te bekijken.

#### <a name="protect-on-premises-exchange-data-using-intune-app-and-ca----1056954---"></a>On-premises Exchange-gegevens beveiligen met Intune APP en CA <!-- 1056954 -->
U kunt nu Intune App Policy Protection (APP) en Conditional Access (CA) gebruiken om de toegang tot on-premises Exchange-gegevens te beveiligen met Outlook Mobile. Als u beleid voor app-beveiliging wilt toevoegen of wijzigen in Azure Portal, selecteert u **Microsoft Intune** > **Client-apps** > **Beleid voor app-beveiliging**. Voordat u deze functie gebruikt, moet u ervoor zorgen dat u voldoet aan de [Outlook voor iOS- en Android-vereisten](https://technet.microsoft.com/en-us/library/mt846639(v=exchg.160).aspx).

## <a name="notices"></a>Mededelingen

### <a name="plan-for-change-intune-will-move-to-support-macos-1012-and-higher-in-december---2970975--"></a>Plan voor wijziging: Intune stapt over naar ondersteuning voor macOS 10.12 en hoger in december <!--2970975--> 

Apple heeft onlangs macOS 10.14 uitgebracht. Dienovereenkomstig stapt Intune in december 2018 over naar ondersteuning voor macOS 10.12 en hoger. 

### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?

Vanaf december kunnen eindgebruikers op apparaten met macOS 10.11 en eerder geen gebruik meer maken van de bedrijfsportal om zich in te schrijven in Intune. Ze moeten hun apparaat upgraden naar macOS 10.12 of hoger en de bedrijfsportal-app upgraden naar de nieuwste versie om ondersteuning en nieuwe functies te blijven ontvangen. 

macOS-versies 10.12 en hoger worden momenteel ondersteund op: 
- MacBook (eind 2009 of nieuwer). 
- iMac (eind 2009 of nieuwer)
- MacBook Air (late 2010 of nieuwer).  
- MacBook Pro (eind 2010 of nieuwer). 
- Mac Mini (eind 2010 of nieuwer). 
- Mac Pro (eind 2010 of nieuwer). 

Na december hebben eindgebruikers met andere dan de hierboven vermelde apparaten geen toegang meer tot de nieuwste versie van de bedrijfsportal-app voor macOS. Bestaande ingeschreven apparaten met een niet-ondersteunde versie lager dan macOS 10.12 worden gewoon nog beheerd met en vermeld in de Intune-beheerconsole.

### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?

Verzoek uw eindgebruikers om vóór december 2018 hun apparaten te upgraden naar een ondersteunde versie van het besturingssysteem. 
- Controleer uw Intune-rapporten in de Intune op Azure-console om te zien welke apparaten of gebruikers hierdoor kunnen worden beïnvloed. Ga naar Apparaten > Alle apparaten en filter op besturingssysteem. U kunt extra kolommen toevoegen om te achterhalen wie in uw organisatie apparaten gebruikt waarop macOS 10.11 wordt uitgevoerd. 
- Als u hybride Mobile Device Management (MDM) gebruikt, gaat u naar Assets en naleving > Apparaten in de Configuration Manager-console. Klik met de rechtermuisknop op de kolommen om de kolommen Besturingssysteem en Clientversie toe te voegen en sorteer de kolommen vervolgens op besturingssysteem. Let op: hybride MDM wordt nu afgeschaft en u moet zo snel mogelijk overstappen naar Intune op Azure. 
 
Extra informatie[https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos-cp](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos-cp)
 

### <a name="plan-for-change-new-intune-support-experience-for-premier-customers"></a>Plan voor wijziging: nieuwe Intune-ondersteuningservaring voor Premier-klanten 
Als Microsoft Premier-klant kunt u momenteel gebruikmaken van de Microsoft Premier Online-portal (MPO) (premier.microsoft.com) en Intune op Azure (portal.azure.com) om ondersteuningsaanvragen voor Intune te maken. Als u na 3 december 2018 de Premier-ondersteuningservaring wilt blijven verbeteren, kunt u alleen ondersteuningsaanvragen in Intune op Azure maken.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Na 3 december kunt u geen ondersteuningsaanvragen meer maken in MPO.  Wanneer u dit toch probeert te doen, ziet u een prompt met een melding die u niet kunt sluiten en wordt u doorgestuurd naar Intune op Azure. Hier kunt u een ondersteuningsaanvraag maken die naar speciale Microsoft Ondersteuning voor Intune wordt doorgestuurd, zodat uw probleem zo snel mogelijk wordt gediagnosticeerd en opgelost. Ondersteuningsaanvragen die in de MPO-portal zijn gemaakt , kunnen niet worden weergegeven in Azure Portal; maak dus geen ondersteuningsaanvragen meer in MPO.  

Als u hybride Mobile Device Management (hybride MDM) of gemeenschappelijk beheer gebruikt, kunt u MPO blijven gebruiken om ondersteuningsaanvragen voor ConfigMgr te maken. Gebruikt u echter Azure Portal om ondersteuningsaanvragen voor Intune te maken. Ter herinnering: hybride MDM wordt afgeschreven en u moet de overstap naar Intune op Azure zo snel mogelijk inplannen. Raadpleeg Overstappen van hybride Mobile Device Management naar Intune op Azure voor meer informatie.

Let op: alleen gebruikers met de rol van algemene beheerder, Intune-servicebeheerder of serviceondersteuningsbeheerder mogen ondersteuningstickets maken in Azure Portal.

#### <a name="what-can-i-do-to-prepare-for-this-change"></a>Wat kan ik doen om me voor te bereiden op deze wijziging?
- Beëindig het gebruik van MPO en gebruik Intune op Azure om al uw Intune-ondersteuningsaanvragen te maken en te beheren.  
- Informeer uw helpdesk en werk de documentatie waar nodig bij.
- Als u gebruikers zonder de rol van algemene beheerder of Intune-servicebeheerder hebt die momenteel ondersteuningsaanvragen in MPO maken, wijst u de rol van serviceondersteuningsbeheerder aan ze toe in Azure Active Directory, zodat ze ondersteuningstickets kunnen blijven maken in Azure Portal.
- Klik op Aanvullende informatie voor meer informatie en nuttige koppelingen.

#### <a name="additional-information"></a>Als u meer informatie
[https://aka.ms/IntuneSupport_MPO_to_Azure](https://aka.ms/IntuneSupport_MPO_to_Azure)

### <a name="take-action-please-update-your-android-device-restriction-or-compliance-policy-password-settings-in-intune"></a>Onderneem actie: werk in Intune uw wachtwoordinstellingen voor het Android-apparaatbeperkings- of nalevingsbeleid bij
In Intune wordt het beschikbare wachtwoordtype standaardwaarde voor het apparaat verwijderd voor apparaten met Android 4.4 en hoger. Vanwege verschillen in de Android-platformen en standaardinstellingen voor apparaten wordt dat beleid door het apparaat vaak beschouwd als optioneel. Om verwarring te voorkomen over wanneer deze instelling wordt afgedwongen op Android, wordt deze instelling in een toekomstige release verwijderd uit de gebruikersinterface. 
#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
- Als u een wachtwoord op de apparaten wilt verplichten, wordt aangeraden in plaats van de standaardwaarde voor het apparaat de profielen voor het Android-platform te wijzigen om duidelijk te maken wat het vereiste wachtwoordtype is.
- Als u de gebruiker zelf wilt laten kiezen of deze een wachtwoord instelt, selecteert u de knop Niet geconfigureerd. Als deze instelling vanuit de gebruikersinterface is verwijderd maar de instelling nog is geconfigureerd, wordt u bij de volgende bewerking van het profiel gevraagd een andere waarde dan de standaardwaarde van het apparaat te kiezen.
Wat moet ik doen om me voor te bereiden op deze wijziging?
Controleer de wachtwoordinstellingen in uw Android- en Android Enterprise-apparaatbeperkingsbeleid en nalevingsbeleid. Deze zijn opgenomen onder Systeembeveiliging voor Nalevingsbeleid en het onder Apparaatwachtwoord of Werkprofielinstellingen voor Apparaatbeperkingen. In de aanvullende informatie vindt u een koppeling naar meer informatie over en schermopnamen van waar deze instellingen worden geconfigureerd.
#### <a name="additional-information"></a>Aanvullende informatie
https://aka.ms/PasswordSettings 

### <a name="plan-for-change-change-password-at-next-auth-added-to-intune---1873216---"></a>Plannen voor wijziging: Wachtwoord wijzigen bij volgende verificatie toegevoegd aan Intune<!-- 1873216 -->
In de onderhoudsrelease van september wordt de nieuwe Apple-instelling **Wachtwoord wijzigen bij volgende verificatie** geïntegreerd voor apparaten met Mac OS-versies 10.13 en nieuwer. In de huidige situatie (zonder deze instelling) kunnen MDM-providers niet controleren of de wachtwoordcode van het apparaat is gewijzigd, zodat aan het beleid wordt voldaan. Het beleid voor configuratie en naleving van Intune geeft zonder deze instelling alleen aan dat een apparaatwachtwoord voldoet aan het beleid wanneer dit wordt gewijzigd. Wanneer deze nieuwe functie van Apple wordt toegevoegd, krijgen uw macOS-gebruikers een verzoek om hun wachtwoord bij te werken, zelfs als het wachtwoord aan het beleid voldoet.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Dit heeft gevolgen voor omgevingen met een macOS-apparaatbeleid dat gebruikmaakt van Intune of een hybride MDM. Nu Apple de instelling **Wachtwoord wijzigen bij volgende verificatie** heeft geïmplementeerd, kan Intune afdwingen dat gebruikers na het pushen van een wachtwoordbeleid hun wachtwoord wijzigen. Als u bedrijfsresources blokkeert totdat het apparaat wordt gemarkeerd als conform, hebben uw eindgebruikers mogelijk geen toegang meer tot bedrijfsresources, zoals e-mail of SharePoint-sites, totdat ze hun wachtwoord opnieuw hebben ingesteld. In de toekomst moeten gebruikers na elke wijziging in configuratie- en nalevingsbeleid voor wachtwoorden hun wachtwoord bijwerken.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
Breng uw helpdesk op de hoogte. Als u dit macOS-apparaatbeleid niet wilt afdwingen, raden we aan toewijzing van uw bestaande macOS-beleid ongedaan te maken of dit beleid te verwijderen. Uit klantonderzoek blijkt dat de meeste klanten niet worden beïnvloed door deze wijziging. De meeste eindgebruikers werken hun wachtwoord bij wanneer ze een verzoek krijgen zich te registreren met een wachtwoord of stellen hun wachtwoord opnieuw in om aan het beleid te voldoen.

### <a name="plan-for-change-intune-moving-to-tls-12"></a>Plannen voor wijziging: Intune gaat over op TLS 1.2
Vanaf 31 oktober 2018 biedt Intune ondersteuning voor TLS-protocolversie 1.2 (Transport Layer Security) voor de best mogelijke codering, om ervoor te zorgen dat onze service standaard veiliger is en is afgestemd op andere Microsoft-services zoals Microsoft Office 365. Office heeft deze wijziging aangekondigd in MC128929.

Ook de bedrijfsportal stapt over op ondersteuning voor TLS 1.2 en wel op 31 oktober 2018.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Intune biedt vanaf 31 oktober 2018 geen ondersteuning meer voor TLS-protocol versie 1.0 of 1.1. Alle combinaties van client/server en browser/server moeten TLS-versie 1.2 gebruiken voor een probleemloze verbinding met Intune. Houd er rekening mee dat deze wijziging van invloed is op apparaten van eindgebruikers die niet meer worden ondersteund door Intune, maar nog wel beleid ontvangen via Intune en die TLS-versie 1.2 niet kunnen gebruiken. Dit omvat onder andere apparaten waarop Android 4.3 en lager wordt uitgevoerd. Zie Aanvullende informatie hieronder voor een lijst met apparaten en browsers waarop deze wijziging van invloed is.

Als u na 31 oktober 2018 een probleem ervaart met betrekking tot het gebruik van een oude TLS-versie, moet u bijwerken naar TLS 1.2 of een apparaat gebruiken dat ondersteuning biedt voor TLS 1.2.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
U wordt aangeraden proactief TLS 1.0- en 1.1-afhankelijkheden uit uw omgevingen te verwijderen en waar mogelijk TLS 1.0 en 1.1 uit te schakelen op het niveau van het besturingssysteem. Begin vandaag nog met het plannen van uw migratie naar TLS 1.2. Lees de onderstaande ondersteuningsblogpost voor een lijst met apparaten die momenteel niet worden ondersteund door Intune, maar die mogelijk wel beleid ontvangen en TLS-versie 1.2 niet kunnen gebruiken voor communicatie. U moet mogelijk de eindgebruikers informeren dat ze de toegang tot bedrijfsresources verliezen.

**Aanvullende informatie**: [Intune gaat over op TLS 1.2 voor versleuteling](https://blogs.technet.microsoft.com/intunesupport/2018/06/05/intune-moving-to-tls-1-2-for-encryption/)


### <a name="plan-for-change-use-intune-on-azure-now-for-your-mdm-management----1227338---"></a>Wijzigingsplannen: u kunt Intune op Azure nu gebruiken voor uw MDM-beheer <!-- 1227338 -->
Een jaar geleden hebben we de [openbare preview van Intune op Azure](https://cloudblogs.microsoft.com/enterprisemobility/2016/12/07/public-preview-of-intune-on-azure/) aangekondigd en zes maanden geleden hebben we deze opgevolgd met de [algemene beschikbaarheid van de nieuwe beheerderservaring](https://cloudblogs.microsoft.com/enterprisemobility/2017/06/08/the-new-intune-and-conditional-access-admin-consoles-are-ga/) voor Intune. Vanaf 31 augustus 2018 wordt MDM (Mobile Device Management) uitgeschakeld in de klassieke Silverlight-console voor klanten met de zelfstandige versie van Intune. In plaats daarvan kunt u [Intune op Azure](https://aka.ms/Intune_on_Azure) gebruiken voor MDM. Als u nog steeds de klassieke console voor MDM gebruikt, moet u hiermee stoppen en uzelf vertrouwd maken met Intune op Azure. We verwachten niet dat deze wijziging gevolgen heeft voor eindgebruikers. Klassiek pc-beheer blijft in Silverlight nog gewoon aanwezig. U vindt [hier](https://aka.ms/Intune_on_Azure_mdm) meer informatie over deze wijziging en over eventuele gevolgen voor u.

## <a name="whats-coming"></a>Binnenkort

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple vereist updates voor Application Transport Security <!--748318-->
Apple heeft aangekondigd dat specifieke vereisten gaan gelden voor Application Transport Security (ATS). ATS wordt gebruikt om betere beveiliging af te dwingen voor alle app-communicatie die verloopt via HTTPS. Deze wijziging heeft gevolgen voor Intune-klanten die de bedrijfsportal-app gebruiken op iOS. De [Intune-ondersteuningsblog](https://aka.ms/compportalats) wordt bijgewerkt met informatie.



## <a name="see-also"></a>Zie ook
* [Microsoft Intune-blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Roadmap voor cloudplatform](https://www.microsoft.com/cloud-platform/roadmap)
* [Wat is er nieuw in de gebruikersinterface van de bedrijfsportal?](whats-new-app-ui.md)
* [Wat was er in de vorige maanden nieuw](whats-new-archive.md)
