---
title: Vroege editie
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 08/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5d5d8e0500a0ee928b1037a978f6d4dadab71495
ms.sourcegitcommit: 2ed8d1c39d4b3e3282111f1d758afb3a50f19f8f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2017
---
# <a name="the-early-edition-for-microsoft-intune---august-2017"></a>De vroege editie voor Microsoft Intune - augustus 2017

De **vroege editie** bevat een lijst met functies die worden toegevoegd aan toekomstige releases van Microsoft Intune. Deze informatie wordt in beperkte mate verstrekt en kan worden gewijzigd. Deel deze informatie niet buiten uw bedrijf. Sommige functies die hier worden vermeld, zullen mogelijk niet beschikbaar zijn op de sluitingsdatum en worden mogelijk beschikbaar gesteld in een latere release. Andere functies worden getest in een proefversie, zodat we zeker weten dat ze in gebruik kunnen worden genomen. Als u vragen of opmerkingen hebt, kunt contact opnemen met uw contactpersoon voor de Microsoft-productgroep.

Deze pagina wordt regelmatig bijgewerkt. Controleer op andere updates.

> [!Note]
>De volgende wijzigingen worden momenteel ontwikkeld voor Intune. Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--

## What's coming to Intune on the Azure portal  
## What's coming to Intune apps
## Notices

-->



## <a name="intune-on-the-azure-portal"></a>Intune in Azure Portal

### <a name="actions-for-non-compliance----730266--"></a>Acties voor niet-naleving  <!--730266-->     
*Acties voor niet-naleving* is een nieuwe functie van nalevingsbeleid waarmee u actie kunt ondernemen voor apparaten die niet meer compatibel zijn. U kunt een of meer acties opgeven, samen met de tijdsduur waarbinnen deze acties moeten plaatsvinden. U kunt bijvoorbeeld gebruikers van niet-compatibele apparaten een melding via e-mail sturen onmiddellijk nadat de compatibiliteit van de apparaten is opgeheven, of u kunt de toegang van niet-compatibele apparaten tot bedrijfsbronnen blokkeren na een respijtperiode van 3 dagen via voorwaardelijke toegang.

### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Nieuw rapport met iOS-apparaten met oudere iOS-versies   <!-- 1352223 -->
Het rapport **Out-of-date iOS Devices** (Verouderde iOS-apparaten) is beschikbaar in de werkruimte **Software-updates**. Het rapport bevat een lijst met gecontroleerde iOS-apparaten waarop een iOS-updatebeleid van toepassing is geweest en waarvoor updates beschikbaar zijn. Voor elk apparaat kunt u bekijken waarom het apparaat niet automatisch is bijgewerkt. 

### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices-----822899--1305423--"></a>Nieuwe instellingen om apps toe te staan of te blokkeren voor Samsung KNOX Standard-apparaten  <!-- 822899,  1305423-->   
We gaan nieuwe [instellingen voor apparaatbeperkingen](device-restrictions-android.md) toevoegen waarmee u de volgende app-lijsten kunt opgeven:
  - Apps die gebruikers mogen installeren
  - Apps die gebruikers niet kunnen uitvoeren
  - Apps die voor de gebruiker worden verborgen op het apparaat  

U kunt de app opgeven met de URL of met de pakketnaam opgeven, of kiezen in de lijst met apps die u beheert.

### <a name="new-settings-for-windows-10-device-restriction-profile"></a>Nieuwe instellingen voor het apparaatbeperkingsprofiel voor Windows 10
<!--- 978575, 1308849, 1308850 -->
Er worden nieuwe instellingen toegevoegd aan het apparaatbeperkingsprofiel voor Windows 10 in de categorie Windows Defender SmartScreen.

Zie [Apparaatbeperkingsinstellingen voor Windows 10-apparaten en hoger]( device-restrictions-windows-10.md) voor meer informatie.

### <a name="new-device-restriction-settings-for-windows-10------1063965---"></a>Nieuwe apparaatbeperkingsinstellingen voor Windows 10   <!-- 1063965 -->
Er worden nieuwe instellingen toegevoegd voor het [apparaatbeperkingsprofiel voor Windows 10](/intune/device-restrictions-windows-10), en wel in de volgende categorieën:
- Windows Defender SmartScreen
- App Store


### <a name="android-for-work-support-for-lookout----1087312---"></a>Android for Work-ondersteuning voor Lookout <!-- 1087312 -->   
De Intune-connector met Lookout biedt ondersteuning voor Android for Work-apparaten wanneer u de Lookout voor Work-app gebruikt. U kunt de Lookout-app binnen of buiten de container implementeren.


### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Hulpmiddelen voor Intune-app-beveiliging en Citrix MDX <!-- 709185 -->
U kunt apparaten en apps beheren met een combinatie van Citrix XenMobile MDX en Microsoft Intune. Hierdoor kunt u apps beheren met het Intune-beveiligingsbeleid voor apps met behulp van de mVPN-technologie van Citrix.

U kunt een opslagplaats voor codes vinden met de Intune App Wrapping Tool en Intune App SDK voor iOS en Android, die integreren met Citrix MDX mVPN-technologie.


### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium - nieuwe Mobile Threat Defense-partner   <!-- 954681 -->
U kunt de toegang van mobiele apparaten tot bedrijfsresources beheren door middel van voorwaardelijke toegang op basis van een risicoanalyse die wordt uitgevoerd door Zimperium, een oplossing voor de beveiliging tegen bedreigingen op mobiele apparaten die met Microsoft Intune is geïntegreerd.

#### <a name="how-integration-with-intune-works"></a>Hoe werkt de integratie met Intune?
Risico's worden beoordeeld op basis van telemetrische gegevens die zijn verzameld op apparaten met door Zimperium. U kunt het EMS-beleid voor voorwaardelijke toegang configureren op basis van de Zimperium-risicoanalyse die via het Intune-nalevingsbeleid voor apparaten wordt ingeschakeld. U kunt met dit beleid de toegang tot bedrijfsresources voor niet-compatibele apparaten toestaan of blokkeren op basis van de gedetecteerde bedreigingen.

### <a name="new-azure-ad-conditional-access-policy-ui-link-from-intune-----1016201---"></a>Koppeling van Intune naar de nieuwe gebruikersinterface voor beleid voor voorwaardelijke toegang van Azure AD  <!-- 1016201 -->
IT-beheerders kunnen op apps gebaseerd voorwaardelijk beleid instellen via de nieuwe gebruikersinterface voor beleid voor voorwaardelijke toegang in Azure AD-werkbelastingen. Het op apps gebaseerde voorwaardelijk beleid in de sectie Intune-app-beveiliging in Azure blijft hier voorlopig aanwezig en wordt naast elkaar afgedwongen. Er is vanaf de Intune-werkbelasting ook een handige koppeling naar de nieuwe gebruikersinterface voor beleid voor voorwaardelijke toegang in Azure AD.


### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Hoge beschikbaarheid van on-premises Exchange Connector  <!-- 676614 -->   
U kunt meerdere CAS-rollen (Client Access Server) instellen voor on-premises Exchange Connector. Als de hoofd-CA bijvoorbeeld uitvalt, ontvangt Exchange Connector een query om over te schakelen naar een andere CAS. Deze functie zorgt ervoor dat de service niet wordt onderbroken.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Management pack van System Center Operations Manager voor Exchange Connector <!-- 885457 -->   
Het management pack van System Center Operations Manager voor Exchange Connector kunt u gebruiken om de logboeken van Exchange Connector te parseren. Met dit management pack kunt u Intune op verschillende manieren controleren wanneer u problemen moet oplossen.

### <a name="end-of-support-for-ios-80----1164477---"></a>Einde van ondersteuning voor iOS 8.0 <!---1164477--->
Beheerde apps en de Intune-bedrijfsportal-app voor iOS vereisen iOS 9.0 en hoger voor toegang tot bedrijfsresources. Apparaten die niet voor september zijn bijgewerkt, hebben geen toegang meer tot de bedrijfsportal of beheerde apps. Vanaf december wordt alle toegang tot bedrijfsresources, inclusief e-mail, voorkomen. 

### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Einde van ondersteuning voor Android 4.3 en lager <!---1171127, 1326920 --->
Beheerde apps en de Intune-bedrijfsportal-app voor Android vereisen Android 4.4 en hoger voor toegang tot bedrijfsresources. Apparaten die niet voor begin van oktober zijn bijgewerkt, hebben geen toegang meer tot de bedrijfsportal of beheerde apps. Vanaf december worden alle ingeschreven apparaten verplicht buiten gebruik gesteld, waardoor bedrijfsresources niet meer toegankelijk zijn. Als u beleid voor app-beveiliging zonder MDM gebruikt, krijgen apps geen updates meer en neemt de gebruikservaring na verloop van tijd steeds verder af.


### <a name="platform-support-reminder-windows-phone-81-mainstream-support-will-end-july-11-2017----1327781---"></a>Herinnering voor platformondersteuning: de algemene ondersteuning voor Windows Phone 8.1 stopt op 11 juli 2017 <!-- 1327781 -->  
Op 11 juli 2017 stopt de algemene ondersteuning voor het Windows Phone 8.1-platform. De ondersteuning voor Windows 8.1 voor pc's loopt gewoon door.

Er zijn geen directe gevolgen voor een apparaat met Windows Phone 8.1 dat wordt beheerd door de Intune-service. Apparaten die zijn ingeschreven, blijven gewoon werken en alle beleidsregels, configuraties en apps blijven eveneens werken zoals verwacht. Het is wel zo dat er geen verbeteringen meer worden aangebracht aan het Windows Phone 8.1-platform in de Intune-service, en evenmin voor de Intune-bedrijfsportal-app voor Windows Phone 8.1.

Het is raadzaam om in aanmerking komende Windows Phone 8.1-apparaten zo snel mogelijk te upgraden naar Windows 10 Mobile. 

## <a name="intune-apps"></a>Intune-apps

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Ondersteuning van Intune Managed Browser voor iOS en Android <!---1374196--->

Vanaf oktober 2017 ondersteunt de app Intune Managed Browser voor Android alleen nog apparaten waarop Android 4.4 en hoger wordt uitgevoerd. De app Intune Managed Browser voor iOS ondersteunt alleen apparaten met iOS 9.0 en hoger. Oudere versies van Android en iOS kunnen Managed Browser nog steeds gebruiken, maar er kunnen geen nieuwe versies van de app op worden geïnstalleerd en kan er dus geen gebruik worden gemaakt van alle mogelijkheden van de app. U wordt aangeraden deze apparaten bij te werken tot een ondersteunde versie van het besturingssysteem.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Eindgebruikers zonder inschrijving toegang geven tot de Intune-bedrijfsportal-app voor Android <!---1169910--->  
Eindgebruikers hoeven hun apparaat binnenkort niet meer in te schrijven om toegang te krijgen tot de Intune-bedrijfsportal-app voor Android. Eindgebruikers in organisaties die gebruikmaken van beleid voor app-beveiliging zien bij het openen van de Intune-bedrijfsportal-app geen instructie meer dat ze hun apparaat moeten registreren. Bovendien kunnen eindgebruikers apps installeren via de bedrijfsportal zonder dat ze hun apparaat hoeven te registreren. 

### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Verbeterd foutbericht als een gebruiker het maximum aantal apparaten bereikt dat mag worden ingeschreven <!-- 1270370 -->
In plaats van een algemeen foutbericht krijgen eindgebruikers een gebruikersvriendelijk foutbericht te zien waarop een actie kan worden uitgevoerd: 'U hebt het maximum aantal apparaten ingeschreven dat door de IT-beheerder is toegestaan. Verwijder een ingeschreven apparaat of vraag assistentie van uw IT-beheerder.'

### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users----621669---"></a>Nieuwe aanmeldingsmogelijkheid voor gebruikers van de Android-bedrijfsportal en van het app-beveiligingsbeleid <!-- 621669 -->
Eindgebruikers kunnen in apps bladeren, apparaten beheren en de gegevens voor de IT-contactpersoon bekijken met de Android-bedrijfsportal-app zonder dat ze hun Android-apparaten hoeven in te schrijven. Als een eindgebruiker al een app gebruikt die wordt beveiligd door Intune-app-beveiligingsbeleid en de Android-bedrijfsportal opent, wordt hem of haar ook niet meer gevraagd het apparaat in te schrijven. 

### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>Eindgebruikers informeren welke apparaatgegevens voor iOS kunnen worden gezien <!--739894-->
Aan het scherm voor apparaatgegevens in de bedrijfsportal-app voor iOS wordt de optie **Eigendomstype**  toegevoegd. Hierdoor kunnen gebruikers meer over privacy te weten komen vanaf deze pagina in de documenten voor Intune-eindgebruikers. Deze informatie is ook te vinden op het scherm Info.

### <a name="apps-details-pages-display-new-information-for-android-devices---1287476--"></a>Op de pagina's met gegevens over de apps wordt nieuwe informatie weergegeven voor Android-apparaten <!--1287476-->
In de bedrijfsportal-app voor Android worden op de pagina met gegevens over de apps de app-categorieën weergegeven die de IT-beheerder voor die app heeft gedefinieerd.

### <a name="intune-mobile-application-management-mam-dialog-boxes-now-have-a-modern-interface----1199015---"></a>Intune Mobile Application Management (MAM)-dialoogvensters hebben nu een moderne interface <!-- 1199015 -->
Intune Mobile Application Management (MAM)-dialoogvensters zijn bijgewerkt en hebben nu een modern uiterlijk. De dialoogvensters werken op dezelfde manier als de vorige.

De op moderne Android-apparaten weergegeven dialoogvensters met fouten of meldingen hebben voortaan een bijgewerkt uiterlijk.

### <a name="new-setting-in-the-android-company-portal-app-to-toggle-battery-optimization---1405990--"></a>Nieuwe instelling in de Android-bedrijfsportal-app om batterijoptimalisatie in- of uit te schakelen <!--1405990-->
De pagina **Instellingen** in de bedrijfsportal-app voor Android heeft een nieuwe instelling. Hiermee kunnen gebruikers makkelijk batterijoptimalisatie uitschakelen voor de bedrijfsportal- en Microsoft Authenticator-apps. De naam van de app die in de instelling wordt getoond, is afhankelijk van welke app het werkaccount beheert. Gebruikers wordt aangeraden batterijoptimalisatie uit te schakelen voor betere prestaties van werk-apps die e-mail en gegevens synchroniseren. 




## <a name="notices"></a>Mededelingen

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple vereist updates voor Application Transport Security <!--748318-->   
Apple heeft aangekondigd dat vanaf het voorjaar van 2017 specifieke vereisten gaan gelden voor Application Transport Security (ATS). ATS wordt gebruikt om betere beveiliging af te dwingen voor alle app-communicatie die verloopt via HTTPS. Deze wijziging heeft gevolgen voor Intune-klanten die de bedrijfsportal-app gebruiken op iOS. Bekijk ons [Intune-ondersteuningsblog](https://aka.ms/compportalats) voor meer informatie.

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Rechtstreekse toegang tot Apple-scenario's voor inschrijving <!--951869-->   
Voor Intune-accounts die na januari 2017 zijn gemaakt, heeft Intune rechtstreekse toegang ingeschakeld tot Apple-inschrijvingsscenario's. Hiervoor is de werkstroom voor het inschrijven van apparaten gebruikt in de Azure Preview Portal. Voorheen was de Apple-inschrijvingspreview alleen toegankelijk via koppelingen in de klassieke Intune-portal. Intune-accounts die vóór januari 2017 zijn gemaakt, moeten eenmalig worden gemigreerd om de functies in Azure beschikbaar te maken. De planning voor de migratie is nog niet aangekondigd, maar de informatie wordt zo snel mogelijk beschikbaar gemaakt. Het wordt aangeraden om een testaccount te maken om de nieuwe ervaring te testen, als u met uw bestaande account geen toegang hebt tot de preview.

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Geplande wijziging: Intune verandert in de Intune Partner Portal-ervaring<!-- 1050016 -->
De pagina Intune Partner wordt verwijderd uit manage.microsoft.com die begint met de service-update halverwege mei 2017.  

Als u een partnerbeheerder bent, kunt u niet langer weergeven of actie ondernemen namens uw klanten vanaf de pagina Intune Partner. U moet zich aanmelden bij een van de twee andere partnerportals bij Microsoft.

U kunt zich bij het [Microsoft Partner Center](https://partnercenter.microsoft.com/) en het [Microsoft Office 365-partnerbeheercentrum](https://portal.office.com/) aanmelden bij de klantaccounts die u beheert. Gebruik in de toekomst als partner een van deze sites voor het beheren van uw klanten.



### <a name="see-also"></a>Zie tevens
Zie [Wat is er nieuw in Microsoft Intune?](whats-new.md) voor meer informatie over recente ontwikkelingen.
