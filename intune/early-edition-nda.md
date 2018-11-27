---
title: Vroege editie
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: fbe8cc0fc3e835ee5807dfbe56ea1aa3c728547e
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52184723"
---
# <a name="the-early-edition-for-microsoft-intune---november-2018"></a>De vroege editie voor Microsoft Intune - november 2018

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

<!-- 1811 start -->

### <a name="uninstalling-apps-on-corporate-owned-supervised-ios-devices----1281677---"></a>Apps verwijderen op onder supervisie staande iOS-apparaten in bedrijfseigendom <!-- 1281677 -->
U kunt alle apps op onder supervisie staande iOS-apparaten in bedrijfseigendom verwijderen. U kunt alle apps verwijderen voor gebruikers- of apparaatgroepen met het toewijzingstype **Verwijderen**. Voor persoonlijke of niet onder supervisie staande iOS-apparaten kunt u nog steeds alleen de apps verwijderen die zijn geïnstalleerd met behulp van Intune.

### <a name="track-installation-of-office-proplus---2620217--"></a>Installatie van Office ProPlus bijhouden <!--2620217-->
U kunt de voortgang van de installatie van [Office ProPlus](apps-add-office365.md) bijhouden met behulp van de [Pagina Status van inschrijving](windows-enrollment-status.md).

### <a name="macos-device-enrollment-program-support-for-apple-school-manager-accounts---3006133--"></a>Ondersteuning voor het macOS Device Enrollment Program voor Apple School Manager-accounts <!--3006133-->
Intune biedt ondersteuning met behulp van het Device Enrollment Program op macOS-apparaten voor Apple School Manager-accounts.

### <a name="temporarily-pause-kiosk-mode-on-android-devices-to-make-changes----3041935---"></a>Kioskmodus op Android-apparaten tijdelijk onderbreken om wijzigingen aan te brengen <!-- 3041935 -->
Wanneer u Android-apparaten in de kioskmodus voor meerdere apps gebruikt, moet de IT-beheerder mogelijk wijzigingen aanbrengen aan het apparaat. Met een nieuwe instelling voor kiosken voor meerdere apps kan de IT-beheerder de kioskmodus tijdelijk onderbreken met behulp van een pincode om toegang tot het hele apparaat te krijgen.
Zie [Kioskinstellingen voor Android](android-kiosk-settings.md) voor de huidige kioskinstellingen.

### <a name="set-custom-background-in-managed-home-screen-app-----3041945---"></a>Aangepaste achtergrond in de app voor het beheerde startscherm instellen <!-- 3041945 -->
We voegen een instelling toe waarmee u de achtergrond van de app voor het beheerde startscherm op Android Enterprise-apparaten in de kioskmodus voor meerdere apps kunt aanpassen.  Om de **Aangepaste URL-achtergrond** te configureren, gaat u naar Intune in de Azure-portal > Apparaatconfiguratie. Selecteer een huidig apparaatconfiguratieprofiel of maak een nieuw profiel als u de kioskinstellingen wilt bewerken.

### <a name="enable-virtual-home-button-on-android-enterprise-kiosk-devices-----3042021---"></a>Virtuele startknop op kioskapparaten voor Android Enterprise inschakelen <!-- 3042021 -->
Met een nieuwe instelling kunnen gebruikers op een soft-keyknop op hun apparaat tikken om over te schakelen tussen de app voor het beheerde startscherm en andere toegewezen apps op hun kioskapparaat voor meerdere apps. Deze instelling is vooral handig in scenario's waarbij de kiosk-app van een gebruiker niet op de juiste wijze op de knop 'Terug' reageert. U kunt deze instelling configureren voor Android-apparaten in bedrijfseigendom voor eenmalig gebruik. Om de **Virtuele startknop** in of uit te schakelen, gaat u naar Intune in Azure Portal > Apparaatconfiguratie. Selecteer een huidig apparaatconfiguratieprofiel of maak een nieuw profiel als u de kioskinstellingen wilt bewerken.

### <a name="app-protection-policy-assignment-save-and-apply----3104570---"></a>Beleidstoewijzing voor app-beveiliging opslaan en toepassen <!-- 3104570 -->
U krijgt meer controle over uw beleidstoewijzingen voor app-beveiliging. Door uw beleidstoewijzingen voor app-beveiliging op te slaan en toe te passen, worden alleen de beoogde gebruikers rechtstreeks beïnvloed door een toewijzingsbeleid voor app-beveiliging.

### <a name="new-microsoft-edge-browser-settings-for-windows-10-and-later----3174639---"></a>Nieuwe Microsoft Edge-browserinstellingen voor Windows 10 en hoger <!-- 3174639 -->
Er wordt een nieuwe instelling toegevoegd om de Microsoft Edge-browser op uw apparaten te controleren en te beheren. Zie [Apparaatbeperkingsinstellingen voor Windows 10 (en hoger)](device-restrictions-windows-10.md#microsoft-edge-browser) voor een lijst met de huidige instellingen.

### <a name="select-apps-tracked-on-the-enrollment-status-page---2531007---"></a>Apps die worden bijgehouden op de pagina Status van inschrijving selecteren<!-- 2531007 -->
U kunt straks kiezen welke apps worden bijgehouden op de pagina Status van inschrijving.

### <a name="intune-app-protection-policies-ui-update----3251427---"></a>Update van de gebruikersinterface voor beveiligingsbeleid voor apps in Intune <!-- 3251427 -->

Met behulp van beveiligingsbeleid voor apps in Intune kunt u verschillende instellingen voor gegevensbescherming voor met Intune beveiligde apps configureren, zoals Microsoft Outlook en Word. We wijzigen de instelling en knoplabels zodat ze gemakkelijker te begrijpen zijn. De besturingselementen worden gewijzigd van de besturingselementen **ja**/**nee** in voornamelijk de besturingselementen **blokkeren**/**toestaan** en **uitschakelen**/**inschakelen**, en de labels worden ook bijgewerkt voor de duidelijkheid. De instellingen krijgen ook een nieuwe indeling, zodat de instelling en het bijbehorende label naast elkaar in het besturingselement staan, wat een betere navigatie biedt. De standaardinstellingen en een aantal instellingen blijven hetzelfde, maar met deze wijziging kan de gebruiker de instellingen beter begrijpen, gebruiken en er door navigeren om het geselecteerde app-beveiligingsbeleid toe te passen.



<!-- 1810 start -->

### <a name="use-microsoft-recommended-settings-with-security-baselines----2055484---"></a>Door Microsoft aanbevolen instellingen gebruiken met beveiligingsbasislijnen <!-- 2055484 -->
Intune is geïntegreerd met andere services die op beveiliging gericht zijn, inclusief Windows Defender ATP en Office 365 ATP. Klanten vragen om een gemeenschappelijke strategie en een samenhangende set van end-to-end beveiligingsworkflows voor alle Microsoft 365-diensten. Ons doel is om strategieën af te stemmen en oplossingen te ontwikkelen die beveiligingsactiviteiten en gebruikelijke beheerderstaken combineren. In Intune willen we dit doel bereiken door het publiceren van een set beveiligingsbasislijnen die door Microsoft zijn aanbevolen (**Intune** >  **Beveiligingsbasislijnen**).  Beheerders krijgen de mogelijkheid om direct op basis van deze basislijnen een beveiligingsbeleid op te stellen en dit vervolgens voor hun gebruikers te implementeren. Ze kunnen ook de aanbevolen procedures aanpassen aan de behoeften van hun organisatie. Intune zorgt ervoor dat apparaten deze basislijnen blijven naleven, en waarschuwt beheerders wanneer gebruikers of apparaten van de basislijnen afwijken.

### <a name="scope-tags-for-apps---1081941---"></a>Bereiktags voor apps <!--1081941 -->
Binnenkort kunt u bereiktags gebruiken om de toegang tot Intune-resources te beperken. Voeg een bereiktag toe aan een roltoewijzing en voeg de bereiktag vervolgens toe aan een configuratieprofiel. De rol heeft dan alleen toegang tot resources met configuratieprofielen met overeenkomende bereiktags (of zonder bereiktag).
Selecteer voor het maken van een bereiktag **Intune-rollen** > **Bereik (tags)** > **Maken**.
Als u een bereiktag wilt toevoegen aan een roltoewijzing, selecteert u **Intune-rollen** > **Alle rollen** > **Beleid- en profielbeheerder** > **Toewijzingen** > **Bereik (tags)**.
Als u een bereiktag wilt toevoegen aan een configuratieprofiel, selecteert u **Apparaatconfiguratie** > **Profielen** > Een profiel kiezen > **Eigenschappen** > **Bereik (tags)**.

### <a name="tenant-health-dashboard----1124854---"></a>Dashboard voor tenantstatus<!-- 1124854 -->
De pagina Tenantstatus in Intune biedt een uitputtend overzicht van alle informatie over de status van tenants. De pagina is onderverdeeld in vier secties:  
- **Tenantdetails**: bevat uiteenlopende informatie, zoals uw MDM-instantie, het totale aantal ingeschreven apparaten in uw tenant en uw aantal licenties. Deze sectie bevat ook de huidige servicerelease voor uw tenant.
- **Connectorstatus**: bevat informatie voor geconfigureerde connectoren, zoals Apple VPP, Windows Store for Business en certificaatconnectoren. Op basis van hun huidige status worden de connectoren gemarkeerd als *In orde*,  *Waarschuwing* of *Niet in orde*.
- **Intune servicestatus**: bevat actieve incidenten of storingen voor uw tenant. De informatie in deze sectie wordt rechtstreeks opgehaald uit het Office Message Center ([https://portal.office.com](https://portal.office.com)).
- **Intune nieuws**: bevat actieve berichten voor uw tenant, zoals meldingen dat uw tenant de laatste Intune-functies heeft ontvangen. De informatie in deze sectie wordt rechtstreeks opgehaald uit het Office Message Center ([https://portal.office.com](https://portal.office.com)).


### <a name="deployed-wip-policies-without-user-enrollment----1434452---"></a>Geïmplementeerd WIP-beleid zonder gebruikersinschrijving <!-- 1434452 -->
WIP-beleid (Windows Information Protection) kan worden ingezet zonder dat MDM-gebruikers hun Windows 10-apparaat hoeven in te schrijven. Met deze configuratie kunnen bedrijven hun bedrijfsdocumenten op basis van de WIP-configuratie beschermen, terwijl gebruikers hun eigen Windows-apparaten kunnen blijven beheren. Zodra documenten met WIP-beleid zijn beveiligd, kunnen de beschermde gegevens selectief worden gewist door een Intune-beheerder. Door een gebruiker en een apparaat te selecteren een en wisaanvraag te versturen, worden alle gegevens onbruikbaar die met het WIP-beleid zijn beschermd. Vanuit Intune in de Azure-portal selecteert u hiervoor **Mobiele app** > **App selectief wissen**.


<!-- 1809 start -->  

### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>APP-instellingen voor webgegevens <!-- 2662995 -->
De APP-instellingen voor webcontent op zowel Android- als iOS-apparaten worden bijgewerkt om zowel http- als https-webkoppelingen beter te kunnen verwerken, evenals de gegevensoverdracht via iOS Universal- en Android App-koppelingen.  

<!-- 1808 start -->

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Apple VPP-token die wordt gebruikt door een andere MDM <!-- 1488946 -->
Intune kan detecteren of een token van het volumeaankoopprogramma van Apple (VPP) wordt gebruikt door zowel Intune als een andere MDM en vervolgens meer informatie weergeven.

### <a name="ios-and-macos-version-numbers-and-build-numbers-are-available-in-compliance-policies----1892471---"></a>iOS- en macOS-versienummers en buildnummers zijn beschikbaar in het compatibiliteitsbeleid <!-- 1892471 -->
In **Apparaatcompatibiliteit** > **Apparaatcompatibiliteit** worden de versies van het iOS- en macOS-besturingssysteem weergegeven en zijn beschikbaar voor gebruik in compatibiliteitsbeleid. In een toekomstige update kan ook het buildnummer voor beide platformen worden geconfigureerd.

Wanneer er beveiligingsupdates worden uitgebracht, laat Apple doorgaans het versienummer ongewijzigd, maar wordt het buildnummer wel bijgewerkt. Door het buildnummer in een compatibiliteitsbeleid te gebruiken, kunt u eenvoudig controleren of een beveiligingsupdate is geïnstalleerd.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Buiten gebruik gestelde apparaten in het dashboard voor apparaatnaleving <!-- 1981119 -->
In een toekomstige update worden buiten gebruik gestelde apparaten verwijderd uit het dashboard voor apparaatnaleving. Dit zorgt voor veranderingen in de aantallen in uw nalevingsrapporten.


### <a name="change-in-the-update-process-for-on-premises-connectors----2277554---"></a>Wijziging in het updateproces voor on-premises connectors <!-- 2277554 -->
Op basis van feedback van klanten passen we de manier aan waarop on-premises connectors worden bijgewerkt. Nadat u een on-premises connector hebt geïnstalleerd, worden updates automatisch uitgevoerd. Deze wijziging begint met de nieuwe PFX-certificaatconnector voor Microsoft Intune en wordt vervolgens voor andere soorten on-premises connectors doorgevoerd. 

<!-- 1807 start -->

### <a name="check-for-configuration-manager-compliance----2192052---"></a>Controleren op Configuration Manager-compatibiliteit <!-- 2192052 -->
Een toekomstige update bevat een nieuwe instelling voor System Center Configuration Manager-compatibiliteit (**Apparaatcompatibiliteit** > **Beleid** > **Beleid maken** > **Windows 10**). Configuration Manager verzendt signalen naar Intune-naleving. Met de Intune-instelling kunt u vereisen dat alle Configuration Manager-signalen de waarde 'compatibel' retourneren.

U kunt bijvoorbeeld vereisen dat alle software-updates worden geïnstalleerd op apparaten. Deze vereiste heeft in Configuration Manager de status 'Geïnstalleerd'. Als programma's op het apparaat zich in onbekende staat bevinden, is het apparaat niet-compatibel in Intune.

Van toepassing op Windows 10 en hoger

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Meldingen voor verlopend VPP-token of onvoldoende bedrijfsportal-licenties <!-- 2237572 -->
Als u het Volume Purchase Program (VPP) gebruikt om de bedrijfsportal vooraf in te richten tijdens DEP-inschrijving, waarschuwt Intune u wanneer het VPP-token bijna verloopt en wanneer er bijna te weinig licenties zijn voor de bedrijfsportal.



<!-- the following are present prior to 1711 -->

## <a name="notices"></a>Mededelingen

Er zijn geen actieve meldingen op dit moment.

### <a name="see-also"></a>Zie ook
Zie [Wat is er nieuw in Microsoft Intune?](whats-new.md) voor meer informatie over recente ontwikkelingen.



