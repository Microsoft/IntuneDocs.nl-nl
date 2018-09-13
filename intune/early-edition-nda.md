---
title: Vroege editie
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6cc33bc6e03d2e0370c9e2c2dd9d3462296710e6
ms.sourcegitcommit: e814cfbbefe818be3254ef6f859a7bf5f5b99123
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/31/2018
ms.locfileid: "43329681"
---
# <a name="the-early-edition-for-microsoft-intune---august-2018"></a>De vroege editie voor Microsoft Intune - augustus 2018

> [!Note]
> Melding geheimhoudingsverklaring: de volgende wijzigingen worden momenteel ontwikkeld voor Intune. Deze informatie wordt in heel beperkte mate verstrekt onder de geheimhoudingsverklaring. Plaats deze informatie niet op sociale media of openbare websites als Twitter, UserVoice, Reddit, enzovoort. 

De **vroege editie** bevat een lijst met functies, gedeeld onder geheimhoudingsverklaring, die worden toegevoegd aan toekomstige releases van Microsoft Intune. Deze informatie wordt in beperkte mate verstrekt en kan worden gewijzigd. Stuur over deze informatie geen tweets, plaats hier niets over op UserVoice en deel hier op geen enkele andere wijze iets over buiten uw bedrijf. Sommige functies die hier worden vermeld, zullen mogelijk niet beschikbaar zijn op de sluitingsdatum en worden mogelijk beschikbaar gesteld in een latere release. Andere functies worden getest in een proefversie, zodat we zeker weten dat ze in gebruik kunnen worden genomen. Als u vragen of opmerkingen hebt, kunt contact opnemen met uw contactpersoon voor de Microsoft-productgroep.

Deze pagina wordt regelmatig bijgewerkt. Controleer op andere updates.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune in Azure Portal

<!-- 1808 start -->



### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Apple VPP-token die wordt gebruikt door een andere MDM <!-- 1488946 -->
Intune kan detecteren of een token van het volumeaankoopprogramma van Apple (VPP) wordt gebruikt door zowel Intune als een andere MDM en vervolgens meer informatie weergeven.

### <a name="ios-version-number-and-build-number-are-shown----1892471---"></a>iOS-versienummer en -buildnummer weergegeven <!-- 1892471 -->
Onder **Apparaatnaleving** > **Apparaatnaleving** wordt de versie van het iOS-besturingssysteem weergegeven. In een toekomstige update wordt ook het buildnummer weergegeven.
Wanneer er beveiligingsupdates worden uitgebracht, laat Apple doorgaans het versienummer ongewijzigd, maar wordt het buildnummer wel bijgewerkt. Door het buildnummer weer te geven, kunt u eenvoudig controleren of een beveiligingsupdate is geïnstalleerd.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Buiten gebruik gestelde apparaten in het dashboard voor apparaatnaleving <!-- 1981119 -->
In een toekomstige update worden buiten gebruik gestelde apparaten verwijderd uit het dashboard voor apparaatnaleving. Dit zorgt voor veranderingen in de aantallen in uw nalevingsrapporten.

### <a name="new-user-experience-update-for-the-company-portal-website---2000968---"></a>Nieuwe update van de gebruikerservaring voor de bedrijfsportalwebsite <!--2000968 -->
Op basis van feedback van klanten voegen we nieuwe functies toe aan de website van de bedrijfsportal. U zult een aanzienlijke verbetering ervaren wat betreft de bestaande functionaliteit en bruikbaarheid van uw Android-, iOS- en Windows-apparaten. Delen van de site, zoals apparaatdetails, feedback en ondersteuning, en apparaatoverzicht, krijgen een nieuw, modern, responsief ontwerp. U ziet ook:
- Gestroomlijnde werkstromen voor alle apparaatplatforms
- Verbeterde apparaat-id en inschrijvingsstromen
- Nuttigere foutberichten
- Toegankelijker taal, minder technische jargon
- Mogelijkheid om directe koppelingen naar apps te delen
- Verbeterde prestaties voor grote app-catalogi
- Beter toegankelijk voor alle gebruikers

### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470---"></a>Profiel configureren om bepaalde vensters over te slaan tijdens het doorlopen van de configuratieassistent <!-- 2276470 -->
Wanneer u een macOS-registratieprofiel maakt, kunt u binnenkort instellen dat de configuratieassistent de volgende schermen overslaat:
- Migratie vanaf Android
- Weergavekleur
- Privacy
- iCloudStorage

### <a name="change-in-the-update-process-for-on-premises-connectors----2277554---"></a>Wijziging in het updateproces voor on-premises connectors <!-- 2277554 -->
Op basis van feedback van klanten passen we de manier aan waarop on-premises connectors worden bijgewerkt. Nadat u een on-premises connector hebt geïnstalleerd, worden updates automatisch uitgevoerd. Deze wijziging begint met de nieuwe PFX-certificaatconnector voor Microsoft Intune en wordt vervolgens voor andere soorten on-premises connectors doorgevoerd. 



<!-- 1807 start -->

### <a name="more-sync-opportunities-in-the-company-portal-app-for-windows----2683177---"></a>Meer synchronisatiemogelijkheden in de Bedrijfsportal-app voor Windows <!-- 2683177 -->
De Bedrijfsportal-app voor Windows voegt een optie voor apparaatsynchronisatie toe aan de Windows-taakbalk en het startmenu. Klik vanuit een van de locaties om uw apparaten snel te synchroniseren en toegang te krijgen tot bedrijfsresources.  

### <a name="reset-device-passcodes-from-company-portal-app-for-windows-10----2101282---"></a>Apparaattoegangscode opnieuw instellen vanuit de bedrijfsportal-app voor Windows 10 <!-- 2101282 --> 
Uw werknemers kunnen binnenkort hun pincodes of toegangscode van hun apparaat rechtstreeks vanuit de bedrijfsportal-app voor Windows 10 opnieuw instellen. Deze functionaliteit wordt beschikbaar op zowel extern als lokaal door Intune beheerde apparaten die ondersteuning bieden voor het opnieuw instellen van toegangscodes. Afhankelijk van het type apparaat wordt bij een aanvraag die is ingediend voor een extern apparaat de huidige toegangscode verwijderd of wordt een tijdelijke toegangscode gemaakt. Gebruikers die verzoeken om een reset voor een lokaal apparaat worden doorgestuurd naar de Instellingen-app van het apparaat.  

### <a name="new-browsing-experiences-in-the-company-portal-app-for-windows----2317227---"></a>Nieuwe bladerervaringen in de Bedrijfsportal-app voor Windows <!-- 2317227 -->  
Wanneer u bladert of apps zoekt in de Bedrijfsportal-app voor Windows, kunt u schakelen tussen de bestaande weergave **Tegels** en de recent toegevoegde weergave **Details**. De nieuwe weergave bevat informatie over toepassingen, zoals de naam, de uitgever, de publicatiedatum en de installatiestatus.  

Op de pagina **Apps** staat de weergave **Geïnstalleerd**. Hier ziet u meer informatie over app-installaties die zijn voltooid en die nog bezig zijn. Wilt u feedback of ideeën over de nieuwe wijzigingen doorgeven? Stuur uw feedback op via de Bedrijfsportal-app.

### <a name="improved-company-portal-app-experience-for-device-enrollment-manager-users----675800---"></a>Verbeterde Bedrijfsportal-app-ervaring voor gebruikers van de apparaatinschrijvingsmanager <!-- 675800 -->
Wanneer een apparaatinschrijvingsmanager (DEM) zich aanmeldt bij de Bedrijfsportal-app voor Windows, wordt in de app alleen het huidige DEM-apparaat weergegeven dat wordt uitgevoerd. Dankzij deze verbetering treden er minder time-outs op. Deze time-outs traden voorheen op wanneer de app probeerde alle apparaten met DEM-registratie te laden.  

### <a name="use-vpp-device-licenses-to-pre-provision-the-company-portal-during-dep-enrollment----1608345---"></a>VPP-apparaatlicenties gebruiken om de bedrijfsportal vooraf in te richten tijdens DEP-registratie <!-- 1608345 -->
U kunt Volume Purchase Program-apparaatlicenties (VPP) gebruiken om de bedrijfsportal vooraf in te richten tijdens de Device Enrollment Program-registraties (DEP). Om dit te doen, geeft u, wanneer u een registratieprofiel maakt of bewerkt, het VPP-token op dat u wilt gebruiken om de bedrijfsportal te installeren. Controleer of uw token niet verloopt en of u voldoende licenties heeft voor de bedrijfsportal-app. Wanneer het token verloopt of onvoldoende licenties heeft, pusht Intune in plaats daarvan de App Store-bedrijfsportal (deze vraagt om een Apple ID).

### <a name="check-for-sccm-compliance----2192052---"></a>SCCM-naleving controleren <!-- 2192052 -->
Een toekomstige update bevat een nieuwe nalevingsinstelling van System Center Configuration Manager (SCCM) (**Apparaatcompatibiliteit** > **Beleid** > **Beleid maken**  >  **Windows 10**). SCCM verzendt signalen naar Intune-nalevingsbeleid. Met de Intune-instelling kunt u vereisen dat alle SCCM-signalen 'conform' retourneren.

U kunt bijvoorbeeld vereisen dat alle software-updates worden geïnstalleerd op apparaten. Deze vereiste heeft in SCCM de status 'Geïnstalleerd'. Als programma's op het apparaat zich in onbekende staat bevinden, is het apparaat niet-compatibel in Intune.

Van toepassing op Windows 10 en hoger

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Meldingen voor verlopend VPP-token of onvoldoende bedrijfsportal-licenties <!-- 2237572 -->
Als u het Volume Purchase Program (VPP) gebruikt om de bedrijfsportal vooraf in te richten tijdens DEP-inschrijving, waarschuwt Intune u wanneer het VPP-token bijna verloopt en wanneer er bijna te weinig licenties zijn voor de bedrijfsportal.

### <a name="confirmation-required-to-delete-vpp-token-that-is-being-used-for-company-portal-pre-provisioning----2237634---"></a>Bevestiging vereist om het VPP-token te verwijderen dat wordt gebruikt voor het vooraf inrichten van de bedrijfsportal <!-- 2237634 -->
Er is een bevestiging vereist om een Volume Purchase Program-token (VPP) te verwijderen als dit wordt gebruikt voor het vooraf inrichten van de bedrijfsportal tijdens de DEP-inschrijving.

#### <a name="additional-security-settings-for-windows-installer----2282430---"></a>Aanvullende beveiligingsinstellingen voor Windows Installer <!-- 2282430 -->
U kunt gebruikers toestemming geven om app-installaties te beheren. Als u deze functie is ingeschakeld, kunnen installaties worden toegestaan die anders worden gestopt vanwege een beveiligingsfout. U kunt het Windows-installatieprogramma de opdracht geven om verhoogde bevoegdheden te gebruiken wanneer een programma op een systeem wordt geïnstalleerd. Verder kunt u ingeschakelde items van Windows-gegevensbescherming laten indexeren en de metagegevens voor de items laten opslaan op een niet-versleutelde locatie. Als het beleid is uitgeschakeld, worden de items met WIP-beveiliging niet geïndexeerd en worden ze niet weergegeven in de resultaten in Cortana of Verkenner. De functionaliteit voor deze opties is standaard uitgeschakeld. 

<!-- 1806 start -->

### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Toetsenborden van derden kunnen worden geblokkeerd door APP-instellingen op iOS <!-- 1248481 -->
Op iOS-apparaten kunnen Intune-beheerders het gebruik blokkeren van toetsenborden van derden bij het benaderen van organisatiegegevens in door beleid beveiligde apps. Wanneer het Application Protection Policy (APP; appbeveiligingsbeleid) is ingesteld om toetsenborden van derden te blokkeren, ontvangt de gebruiker een bericht als hij de eerste keer met bedrijfsgegevens werkt met een toetsenbord van derden. Alle opties, behalve het systeemeigen toetsenbord, worden geblokkeerd en zijn niet zichtbaar voor apparaatgebruikers. Apparaatgebruikers zien het dialoogvenster slechts één keer. 

### <a name="require-non-biometric-passcode-on-app-launch-and-timeout----1506985---"></a>Niet-biometrische wachtwoordcode vereisen bij het starten en een time-out van een app <!-- 1506985 -->

Door een niet-biometrische wachtwoordcode te vereisen bij het starten van een app en na een door de beheerder opgegeven time-out, biedt Intune betere beveiliging voor apps die geschikt zijn voor Mobile Application Management (MAM) door het gebruik van biometrische identificatie voor toegang tot zakelijke gegevens te beperken. De instellingen hebben invloed op gebruikers die Touch ID (iOS), Face ID (iOS), Android Biometric of andere toekomstige biometrische verificatiemethoden gebruiken om toegang te krijgen tot voor APP/MAM geschikte toepassingen. Door deze instellingen hebben Intune-beheerders gedetailleerdere controle over gebruikerstoegang. Op deze manier wordt de kans kleiner dat een onjuiste gebruiker bedrijfsgegevens kan zien op een apparaat met meerdere vingerafdrukken of andere biometrische toegangsmethoden. Open **Microsoft Intune** in de Azure-Portal. Selecteer **Client-apps** > **App-beveiligingsbeleid** > **Een beleid toevoegen** > **Instellingen**. Ga voor specifieke instellingen naar de sectie **Toegang**.

### <a name="office-365-pro-plus-language-packs----1833450---"></a>Office 365 Pro Plus-taalpakketten <!-- 1833450 -->
Als Intune-beheerder kunt extra talen implementeren voor Office 365 Pro Plus-apps die via Intune worden beheerd. De lijst met beschikbare talen bevat het taalpakket **Type** (kern, gedeeltelijk en spellingcontrole). Selecteer in Azure Portal **Microsoft Intune** > **Client-apps** > **Apps** > **Toevoegen**. In de lijst **App-type** op de blade **App toevoegen** selecteert u **Windows 10** onder **Office 365-suite**. Selecteer **Talen** in de blade **Instellingen voor app-suite**.

### <a name="preview-a-new-user-experience-update-for-the-company-portal-website---2000968---"></a>Bekijk de nieuwe update van de gebruikerservaring voor de bedrijfsportalwebsite <!--2000968 -->
Op basis van feedback van klanten voegen we nieuwe functies toe aan de website van de bedrijfsportal/iOS-app-catalogus. U zult een aanzienlijke verbetering ervaren wat betreft de bestaande functionaliteit en bruikbaarheid van uw Android-, iOS- en Windows-apparaten. Delen van de site, zoals apparaatdetails, feedback en ondersteuning, en apparaatoverzicht, krijgen een nieuw, modern, responsief ontwerp. U ziet ook:

- Gestroomlijnde werkstromen voor alle apparaatplatforms
- Verbeterde apparaat-id en inschrijvingsstromen
- Nuttigere foutberichten
- Toegankelijker taal, minder technische jargon
- Mogelijkheid om directe koppelingen naar apps te delen
- Verbeterde prestaties voor grote app-catalogi
- Beter toegankelijk voor alle gebruikers

De update is momenteel beschikbaar als preview-versie. U kunt zich aanmelden voor de preview-versie op http://aka.ms/webcpflighting

<!-- 1805 start -->

### <a name="require-non-biometric-passcode-on-cold-app-launch-and-timeout----1506985---"></a>Niet-biometrische wachtwoordcode vereisen bij het koud starten en een time-out van een app <!-- 1506985 --> 

Door een niet-biometrische wachtwoordcode te vereisen bij het koud starten van een app en na een door de beheerder opgegeven time-out, biedt Intune betere beveiliging voor apps die geschikt zijn voor Mobile Application Management (MAM) door het gebruik van biometrische identificatie voor toegang tot zakelijke gegevens te beperken. De instellingen hebben invloed op gebruikers die Touch ID (iOS), Face ID (iOS), Android Biometric of andere toekomstige biometrische verificatiemethoden gebruiken om toegang te krijgen tot voor APP/MAM geschikte toepassingen. Door deze instellingen hebben Intune-beheerders gedetailleerdere controle over gebruikerstoegang. Op deze manier wordt de kans kleiner dat een onjuiste gebruiker bedrijfsgegevens kan zien op een apparaat met meerdere vingerafdrukken of andere biometrische toegangsmethoden. Open **Microsoft Intune** in de Azure-Portal. Selecteer **Client-apps** > **App-beveiligingsbeleid** > **Een beleid toevoegen** > **Instellingen**. Ga voor specifieke instellingen naar de sectie **Toegang**.

<!-- 1803 start -->

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Mogelijkheid om vereiste line-of-business-apps (LOB) te implementeren voor alle gebruikers op apparaten met Windows 10 Desktop <!-- 1627835 RS4 -->
Klanten kunnen vereiste Windows 10 line-of-business-apps implementeren om in apparaatcontexten te installeren. Hierdoor worden deze apps beschikbaar voor alle gebruikers op het apparaat. Dit is alleen van toepassing op Windows 10 Desktop-apparaten.

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>De Help- en Feedback-ervaring op de bedrijfsportal-app voor Android bijwerken <!--1631531 -->

De Help- en Feedback-ervaring op de bedrijfsportal-app voor Android wordt bijgewerkt, zodat deze overeenkomt met de aanbevolen procedures voor Android-apps. De bedrijfsportal-app voor Android wordt in de komende maanden ook bijgewerkt om het menu-item **Help en Feedback** op te delen in afzonderlijke menu-items, namelijk **Help** en **Feedback verzenden**. Op de **Help**-pagina komt een sectie **Veelgestelde vragen** sectie en een knop **E-mailondersteuning** waarmee eindgebruikers logboeken naar Microsoft kunnen uploaden en e-mail kunnen verzenden naar bedrijfsondersteuning om het probleem te beschrijven. **Feedback verzenden** leidt de gebruiker door een standaard Microsoft-feedbackformulier, waarin de gebruiker wordt gevraagd een keuze te maken uit: "Ik vindt iets leuk", "Ik vind iets niet leuk" of "Ik heb een idee."

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Beleid voor app-beveiliging <!-- 679615 -->
Via het beveiligingsbeleid voor Intune-apps kunt u algemene standaardbeleidsregels maken om snel beveiliging in te schakelen voor alle gebruikers in de gehele tenant.

<!-- the following are present prior to 1711 -->

## <a name="notices"></a>Mededelingen

Er zijn geen actieve meldingen op dit moment.

### <a name="see-also"></a>Zie ook
Zie [Wat is er nieuw in Microsoft Intune?](whats-new.md) voor meer informatie over recente ontwikkelingen.



