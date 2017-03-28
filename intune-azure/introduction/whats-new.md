---
title: Wat is er nieuw in Microsoft Intune Preview
titleSuffix: Intune Azure preview
description: Ontdekken wat er nieuw is in Intune Azure Preview
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/17/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 671d862c8d9a98e02f33d96cf6ceba712e740dec
ms.openlocfilehash: 586bdab54ee60ba8d620857ab3506aa27622d17a
ms.lasthandoff: 03/17/2017

---

# <a name="whats-new-in-the-microsoft-intune-preview"></a>Wat is er nieuw in Microsoft Intune Preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Als de openbare preview-versie verder wordt ontwikkeld en er meer functies worden toegevoegd, wordt u hier op de hoogte gebracht.

> [!Note]
> De wijzigingen die op deze pagina zijn opgesomd voor Azure Portal Preview worden uitgerold. De wijzigingen zijn echter mogelijk niet meteen beschikbaar vanwege de manier waarop de Intune-service wordt bijgewerkt.  Verschillende onderdelen van de service moeten opeenvolgend worden bijgewerkt voordat de nieuwe functies van de portal beschikbaar zijn. U zult deze wijzigingen zien wanneer ze later deze maand worden uitgerold.

## <a name="march-2017"></a>Maart 2017

### <a name="support-for-ios-lost-mode---431695--"></a>Ondersteuning voor iOS voor de modus Apparaat verloren<!--431695-->

Voor apparaten met iOS 9.3 en hoger is in Intune ondersteuning toegevoegd voor de **modus Apparaat verloren**. U kunt nu een apparaat vergrendelen om verder gebruik te voorkomen en een bericht en telefoonnummer weergeven op het vergrendelingsscherm van het apparaat.

De eindgebruiker kan het apparaat pas ontgrendeld wanneer een beheerder de modus Apparaat verloren heeft uitgeschakeld. Als de modus Apparaat verloren is ingeschakeld, kunt u de actie **Apparaat zoeken** uitvoeren om de geografische locatie van het apparaat weer te geven op een kaart in de Intune-console.

Het apparaat moet een iOS-apparaat in bedrijfseigendom zijn, dat via DEP is ingeschreven en waarop de supervisiemodus is ingeschakeld.

Zie [Wat is Microsoft Intune-apparaatbeheer?](/intune-azure/manage-devices/what-is) voor meer informatie.

### <a name="improvements-to-device-actions-report---677150--"></a>Verbeteringen aan het rapport Apparaatacties <!--677150-->

Er zijn verbeteringen aangebracht aan het rapport Apparaatacties voor betere prestaties. Bovendien kunt u het rapport nu filteren op basis van status. U kunt het rapport bijvoorbeeld filteren zodat alleen de apparaatacties worden weergegeven die zijn voltooid.

### <a name="actions-for-non-compliance---730266--"></a>Acties voor niet-naleving <!--730266-->

**Acties voor niet-naleving** is een nieuwe functie van nalevingsbeleid waarmee u actie kunt ondernemen voor apparaten die niet meer compatibel zijn. U kunt een of meer acties opgeven, samen met de tijdsduur waarbinnen deze acties moeten plaatsvinden. U kunt bijvoorbeeld gebruikers van niet-compatibele apparaten een melding via e-mail sturen onmiddellijk nadat de compatibiliteit van de apparaten is opgeheven, of u kunt de toegang van niet-compatibele apparaten tot bedrijfsbronnen blokkeren na een respijtperiode van 3 dagen via voorwaardelijke toegang.

### <a name="custom-app-categories---748805--"></a>Aangepaste app-categorieën <!--748805-->

U kunt nu categorieën maken, bewerken en toewijzen voor apps die u aan Intune toevoegt. Categorieën kunnen momenteel alleen worden opgegeven in het Engels.
Zie [Een app toevoegen aan Intune](/intune-azure/manage-apps/add-apps).

### <a name="assign-lob-apps-to-users-with-unenrolled-devices---748823--"></a>LOB-apps toewijzen aan gebruikers met niet-ingeschreven apparaten <!--748823-->

U kunt nu Line-Of-Business-apps uit de store toewijzen aan gebruikers, ongeacht of hun apparaten zijn ingeschreven bij Intune. Als een apparaat van een gebruiker niet is geregistreerd bij Intune, moet deze daarvoor de bedrijfsportalwebsite gebruiken en niet de bedrijfsportal-app.

### <a name="new-compliance-reports---846671--"></a>Nieuwe nalevingsrapporten <!--846671-->

U hebt nu nalevingsrapporten die u informatie bieden over de naleving van apparaten in uw bedrijf. U kunt dan ook snel aan naleving gerelateerde problemen oplossen waar uw gebruikers mee te maken krijgen. U kunt informatie bekijken over

- De algemene nalevingsstatus van apparaten
- De nalevingsstatus voor een specifieke instelling
- De nalevingsstatus voor een specifiek beleid

U kunt deze rapporten ook gebruiken om in te zoomen op een specifiek appraat, om op die manier te bekijken welke instellingen en beleidsregels van invloed zijn op dat apparaat.

<!--- You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N --->

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Rechtstreekse toegang tot Apple-scenario's voor inschrijving <!--951869-->

Voor Intune-accounts die na januari 2017 zijn gemaakt, heeft Intune rechtstreekse toegang ingeschakeld tot Apple-inschrijvingsscenario's. Hiervoor is de werkstroom voor het inschrijven van apparaten gebruikt in de Azure Preview Portal. Voorheen was de Apple-inschrijvingspreview alleen toegankelijk via koppelingen in de klassieke Intune-portal. Intune-accounts die vóór januari 2017 zijn gemaakt, moeten eenmalig worden gemigreerd om de functies in Azure beschikbaar te maken. De planning voor de migratie is nog niet aangekondigd, maar de informatie wordt zo snel mogelijk beschikbaar gemaakt. Het wordt aangeraden om een testaccount te maken om de nieuwe ervaring te testen, als u met uw bestaande account geen toegang hebt tot de preview.


## <a name="february-2017"></a>Februari 2017

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Mogelijkheid om de inschrijving van mobiele apparaten te beperken <!--747600, 795782-->
Er zijn in Intune nieuwe inschrijvingsbeperkingen toegevoegd die bepalen welke platforms voor mobiele apparaten kunnen worden ingeschreven. Intune onderscheidt platforms voor mobiele apparaten als iOS, Mac OS, Android, Windows en Windows Mobile.

* Een beperking voor de registratie van mobiele apparaten, betekent niet dat de PC-clientregistratie ook is beperkt.  
* Alleen voor iOS en Android geldt er een extra optie voor het blokkeren van de inschrijving van apparaten die in persoonlijk eigendom zijn.

Intune markeert alle nieuwe apparaten als persoonlijk, tenzij de IT-beheerder actie onderneemt om deze te markeren als bedrijfseigen, zoals uitgelegd in [dit artikel](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices).

### <a name="view-all-actions-on-managed-devices---677150--"></a>Alle acties voor beheerde apparaten weergeven <!--677150-->
Er is een nieuw rapport __Apparaatacties__, waarin wordt weergegeven wie externe acties, zoals het herstellen van fabrieksinstellingen, op apparaten heeft uitgevoerd. In dit rapport wordt ook de status van de actie getoond. Zie [Wat is apparaatbeheer?](https://docs.microsoft.com/intune-azure/manage-devices/what-is).

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Niet-beheerde apparaten hebben toegang tot toegewezen apps <!--664691-->
Als onderdeel van de ontwerpwijzigingen op de bedrijfsportalwebsite kunnen iOS- en Android-gebruikers op hun niet-beheerde apparaten apps installeren die aan hen zijn toegewezen als 'beschikbaar zonder inschrijving'. Gebruikers kunnen zich met behulp van hun Intune-referenties aanmelden bij de bedrijfsportalwebsite en de lijst met aan hen toegewezen apps bekijken. De app-pakketten van de 'beschikbaar zonder inschrijving'-apps kunnen worden gedownload via de bedrijfsportalwebsite. Deze wijziging is niet van toepassing op apps die pas na inschrijving kunnen worden geïnstalleerd, omdat gebruikers wordt gevraagd hun apparaat in te schrijven als zij deze apps willen installeren.

### <a name="custom-app-categories---748805--"></a>Aangepaste app-categorieën <!--748805-->
U kunt nu categorieën maken, bewerken en toewijzen voor apps die u aan Intune toevoegt. Categorieën kunnen momenteel alleen worden opgegeven in het Engels.
Zie [Een app toevoegen aan Intune](/intune-azure/manage-apps/add-apps).

### <a name="display-device-categories---814654--"></a>Apparaatcategorieën weergeven <!--814654-->
U kunt nu de apparaatcategorie als kolom in de lijst met apparaten weergeven. U kunt ook de categorie uit de sectie met eigenschappen van de apparaateigenschappenblade bewerken. Zie [Een app toevoegen aan Intune](/intune-azure/manage-apps/add-apps).

### <a name="configure-windows-update-for-business-settings---776716--"></a>Instellingen voor Windows Update voor bedrijven configureren.<!--776716-->

Windows as a Service is de nieuwe manier voor het aanbieden van updates voor Windows 10. Vanaf Windows 10 bevatten alle Upgrades van onderdelen en Kwaliteitsupdates de inhoud van alle voorgaande updates. Dit houdt in dat, als u de nieuwste update hebt geïnstalleerd, u zeker weet dat uw Windows 10-apparaten volledig zijn bijgewerkt. In tegenstelling tot eerdere versies van Windows, moet u nu de volledige update installeren in plaats van een onderdeel van een update.

Met Windows Update voor bedrijven kunt u updatebeheer vereenvoudigen, zodat u geen afzonderlijke updates voor groepen apparaten hoeft goed te keuren. U kunt nog steeds risico’s in uw omgeving beheren door een strategie voor update-implementatie te configureren. Windows Update zorgt ervoor dat updates op tijd worden geïnstalleerd. Microsoft Intune biedt de mogelijkheid update-instellingen op apparaten te configureren en biedt u de mogelijkheid de installatie van updates uit te stellen. Intune slaat de updates niet op, maar alleen de beleidstoewijzing voor de update. Apparaten hebben voor de updates rechtstreeks toegang tot Windows Update. Voor het configureren en beheren van **Windows 10-updateringen** wordt Intune gebruikt. Een updatering bevat een aantal instellingen waarin is geconfigureerd wanneer en hoe Windows 10-updates worden geïnstalleerd. Zie [Instellingen voor Windows Update voor bedrijven configureren](/intune-azure/configure-devices/how-to-configure-windows-update-for-business) voor meer informatie.

## <a name="january-2017"></a>Januari 2017

### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748823--"></a>Toewijzen van line-of-business-apps, ongeacht of apparaten al dan niet zijn geregistreerd <!--748823-->
U kunt nu line-of-business-apps uit de store toewijzen aan gebruikers, ongeacht of hun apparaten al dan niet zijn geregistreerd bij Intune. Als een apparaat van gebruikers niet is geregistreerd bij Intune, moeten ze daarvoor de bedrijfsportalwebsite gebruiken en niet de bedrijfsportal-app. Zie [Wat is app-beheer](/intune-azure/manage-apps/what-is-app-management).

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>Oplossing voor het probleem waarbij iOS-apparaten inactief zijn of waarbij de beheerconsole er niet mee kan communiceren
Wanneer het contact tussen de apparaten van gebruikers en Intune verloren gaat, kunt u de gebruikers stappen voor probleemoplossing aandragen waarmee ze weer toegang krijgen tot de bedrijfsresources. Zie [Apparaten zijn inactief of de beheerconsole kan er niet mee communiceren](/intune-azure/enroll-devices/troubleshoot-device-enrollment#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## <a name="december-2016-initial-release"></a>December 2016 (oorspronkelijke versie)

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Integratie van onkostenbeheer voor telecom in de openbare preview-versie van Azure-portal<!--747605-->
We beginnen nu met preview-versies van de integratie met externe systemen voor onkostenbeheer voor telecom (TEM) in de Azure-portal. U kunt Intune gebruiken om limieten in te stellen voor gegevensgebruik, voor zowel nationaal als roaming. Hierbij beginnen we met [Saaswedo](http://www.saaswedo.com). Als u deze functie in uw proeftenant wilt inschakelen, neemt u [contact op met Microsoft-ondersteuning](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

- Apps uit een store op iOS-, Android- en Windows-apparaten implementeren en beheren
- LOB-apps (Line-Of-Business) op iOS-, Android- en Windows-apparaten implementeren en beheren
- Apps die zijn gekocht via het volume-aankoopprogramma, implementeren en beheren op iOS- en Windows-apparaten
- Web-apps implementeren en beheren op Android-, iOS- en Windows-apparaten
- Door iOS beheerde app-configuratieprofielen
- App-beveiligingsbeleid configureren en LOB-apps (Line-Of-Business) implementeren op apparaten die niet zijn geregistreerd met Intune
- VPN-profielen, VPN-, Wi-Fi-, e-mail- en certificaatprofielen per app
- Nalevingsbeleid
- Voorwaardelijke toegang voor Azure AD
- Voorwaardelijke toegang voor On-premises Exchange
- Apparaatinschrijving
- Op rollen gebaseerd toegangsbeheer

## <a name="deprecated-features-in-the-azure-portal"></a>Afgeschafte functies in Azure Portal

### <a name="support-for-row-by-row-review-of-hardware-identifiers"></a>Ondersteuning voor beoordeling van hardware-id's per rij
Azure Portal biedt geen ondersteuning voor de beoordeling van hardware-id's per rij voor IMEI-nummers en serienummers van Apple. U kunt in de klassieke Intune-console gegevens importeren uit een bestand met door komma's gescheiden waarden (CSV-bestand) en de bestaande gegevens voor afzonderlijke hardware-id's overschrijven. Azure Portal bevat één gestroomlijnde optie waarmee gegevens voor alle hardware-id's automatisch worden overschreven of nieuwe gegevens voor bestaande id's worden genegeerd.

#### <a name="how-this-affects-you"></a>Welke gevolgen heeft dit voor u
In Azure Portal kunt u niet per rij bepalen welke IMEI-apparaten (International Mobile Equipment Identity) moeten worden bijgewerkt. In de klassieke Intune-console blijft de ondersteuning voor deze functionaliteit gehandhaafd.

#### <a name="how-to-get-ready-for-this-change"></a>Hoe bereidt u zich voor op deze wijziging
Deze informatie wordt nu al verstrekt, zodat u uw ondersteuningsbeheerders van deze wijziging op de hoogte kunt brengen, als dit voor u van toepassing is. Deze wijziging valt samen met de overgang naar Azure Portal (naar verwachting in de eerste helft van 2017).


### <a name="support-for-default-corporate-device-enrollment-profiles-in-apple-dep"></a>Ondersteuning voor de standaardprofielen voor de registratie van bedrijfsapparaten in Apple DEP
Azure Portal biedt geen ondersteuning voor het standaardprofiel voor de registratie van bedrijfsapparaten voor Apple DEP-apparaatserienummers (Device Enrollment Program). Deze functionaliteit, die beschikbaar is in de klassieke Intune-console, wordt stopgezet om het onbedoeld toewijzen van profielen te voorkomen. In Azure Portal worden aan serienummers die zijn gesynchroniseerd vanuit een Apple DEP-account, in eerste instantie geen profiel voor de registratie van bedrijfsapparaten toegewezen.

#### <a name="how-this-affects-you"></a>Welke gevolgen heeft dit voor u
U kunt in Azure Portal geen standaardprofielbeleid voor alle Apple-apparaten instellen. In de klassieke Intune-console blijft de ondersteuning voor deze functionaliteit gehandhaafd.

#### <a name="how-to-get-ready-for-this-change"></a>Hoe bereidt u zich voor op deze wijziging
Deze informatie wordt nu al verstrekt, zodat u uw ondersteuningsbeheerders van deze wijziging op de hoogte kunt brengen, als dit voor u van toepassing is. Deze wijziging valt samen met de overgang naar Azure Portal (naar verwachting in de eerste helft van 2017).

