---
title: Vroege editie
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5eab3fb933b2999e23115091cf0ded3f140e114c
ms.sourcegitcommit: f5c6e8b218431dc9a8d85464d7f58adebd048866
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/06/2017
---
# <a name="the-early-edition-for-microsoft-intune---july-2017"></a>De vroege editie voor Microsoft Intune - juli 2017

De **vroege editie** bevat een lijst met functies die worden toegevoegd aan toekomstige releases van Microsoft Intune. Deze informatie wordt in zeer beperkte mate verstrekt en kan worden gewijzigd. Deel deze informatie niet buiten uw bedrijf. Sommige functies die hier worden vermeld, zullen mogelijk niet beschikbaar zijn op de sluitingsdatum en worden mogelijk beschikbaar gesteld in een latere release. Andere functies worden getest in een proefversie, zodat we zeker weten dat ze in gebruik kunnen worden genomen. Als u vragen of opmerkingen hebt, kunt contact opnemen met uw contactpersoon voor de Microsoft-productgroep.

Deze pagina wordt regelmatig bijgewerkt. Controleer op andere updates.

> [!Note]
>De volgende wijzigingen worden momenteel ontwikkeld voor Intune. Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--

## What's coming to Intune on the Azure portal  
## What's coming to Intune apps
## Notices

-->



## <a name="whats-coming-to-intune-on-the-azure-portal"></a>Wat er op stapel staat voor Intune in Azure Portal

### <a name="easier-installation-of-office-365-apps-----1121362----"></a>Eenvoudigere installatie van Office 365-apps <!--- 1121362 --->
Het nieuwe app-type **Office 365 ProPlus** maakt het eenvoudig voor u om Office 365 ProPlus-apps toe te wijzen aan apparaten die u beheert waarop de nieuwste versie van Windows 10 wordt uitgevoerd. Daarnaast kunt u Microsoft Project en Microsoft Visio installeren, als u licenties hebt voor deze producten. De gewenste apps worden gebundeld en worden als één app weergegeven in de lijst met apps in de Intune-console.
 

### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>Nieuwe apparaatactie om apparaten geforceerd te synchroniseren met Intune <!-- 711369 -->    
We voegen een nieuwe apparaatactie toe die ervoor zorgt dat het geselecteerde apparaat direct wordt ingecheckt bij Intune. Wanneer een apparaat wordt ingecheckt, worden direct eventuele openstaande acties of toegewezen beleidsregels toegepast.  Met deze actie kunt u toegewezen beleid meteen controleren en in het geval van problemen direct aanpassen, zonder dat u hoeft te wachten op de volgende geplande check-in.

### <a name="actions-for-non-compliance----730266--"></a>Acties voor niet-naleving  <!--730266-->     
*Acties voor niet-naleving* is een nieuwe functie van nalevingsbeleid waarmee u actie kunt ondernemen voor apparaten die niet meer compatibel zijn. U kunt een of meer acties opgeven, samen met de tijdsduur waarbinnen deze acties moeten plaatsvinden. U kunt bijvoorbeeld gebruikers van niet-compatibele apparaten een melding via e-mail sturen onmiddellijk nadat de compatibiliteit van de apparaten is opgeheven, of u kunt de toegang van niet-compatibele apparaten tot bedrijfsbronnen blokkeren na een respijtperiode van 3 dagen via voorwaardelijke toegang.

### <a name="new-app-configuration-settings-for-the-intune-managed-browser-----682951----"></a>Nieuw app-configuratie-instellingen voor Intune Managed Browser <!--- 682951 --->
We gaan meer configuraties toevoegen voor de app Intune Managed Browser. U kunt een app-configuratiebeleid gebruiken om de standaardstartpagina en -bladwijzers voor de browser te configureren.

### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version------1333256--1245463----"></a>Registratie van Android- en iOS-apparaten beperken op basis van de versie van het besturingssysteem  <!--- 1333256,  1245463 --->  
Intune biedt nu ondersteuning voor het beperken van registraties van iOS- en Android-apparaten op basis van het versienummer van het besturingssysteem. Bij **Intune** > **Inschrijvingsbeperkingen** > **Apparaattypebeperking** > **Standaard** > **Platformbeperkingen** kan de IT-beheerder een platformconfiguratie instellen met een minimum- en maximumversie van het besturingssysteem, zodat alleen apparaten met versies in dit bereik kunnen worden geregistreerd. Versies van het Android-besturingssysteem moeten worden opgegeven als Primair.Secundair.Build.Rev, waarbij Build en Rev optioneel zijn. iOS-versies moeten worden opgegeven als Primair.Secundair.Build, waarbij Build optioneel is.

>[!NOTE]
>Deze instelling werkt niet voor inschrijvingen via registratieprogramma's van Apple, zoals het Apple Device Enrollment Program en Apple School Manager, of Apple Configurator.

### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment------1333272--1333275-1245709----"></a>Apparaatregistratie beperken van Android-, iOS- en macOS-apparaten die privé-eigendom zijn  <!--- 1333272,  1333275, 1245709 --->
Intune ondersteunt nu het beperken van registraties van iOS-, Android- en macOS-apparaten die privé-eigendom zijn met behulp van apparaatserienummers. Sommige apparaten verstrekken geen serienummers. Neem voor meer informatie contact op met de fabrikanten van de apparaten. Door serienummers te uploaden naar Intune, kunt u apparaten vooraf markeren als bedrijfseigendom. Aan de hand van inschrijvingsbeperkingen kunt u de registratie blokkeren van apparaten die privé-eigendom (BYOD) zijn. Op deze manier maakt u beleid waardoor alleen apparaten kunnen worden ingeschreven die bedrijfseigendom zijn.

Als u serienummers wilt importeren in de Intune-portal, gaat u naar **Apparaatinschrijving** > **Bedrijfsapparaat-id's** en klikt u op **Toevoegen**. Upload vervolgens een CSV-bestand met deze specificaties: geen header, twee kolommen, één voor de serienummers en één voor gegevens zoals IMEI-nummers.  Als u de registratie van apparaten in privé-eigendom wilt beperken, gaat u naar **Apparaatinschrijving** > **Inschrijvingsbeperkingen**. Selecteer **Standaard** onder **Apparaattypebeperking** en selecteer vervolgens **Platformconfiguraties**. Selecteer **Toestaan** of **Blokkeren** voor iOS-, Android- en macOS-apparaten die privé-eigendom zijn. 

### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>Nieuwste software-update geforceerd installeren op iOS-apparaten die onder supervisie staan<!-- 777100 -->   
Er komt een nieuw beleid beschikbaar in de werkruimte Software-updates waarmee u kunt afdwingen dat automatisch de nieuwste software-update wordt geïnstalleerd op onder supervisie staande iOS-apparaten. Ook is het mogelijk om een nieuw rapport op te vragen met een lijst van iOS-apparaten met oudere versies en een toelichting waarom ze niet actueel zijn.

### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices-----822899--1305423--"></a>Nieuwe instellingen om apps toe te staan of te blokkeren voor Samsung KNOX Standard-apparaten  <!-- 822899,  1305423-->   
We gaan nieuwe [instellingen voor apparaatbeperkingen](device-restrictions-android.md) toevoegen waarmee u de volgende app-lijsten kunt opgeven:
  - Apps die gebruikers mogen installeren
  - Apps die gebruikers niet kunnen uitvoeren
  - Apps die voor de gebruiker worden verborgen op het apparaat  

U kunt de app opgeven met de URL of met de pakketnaam opgeven, of kiezen in de lijst met apps die u beheert.

### <a name="android-for-work-support-for-lookout----1087312---"></a>Android for Work-ondersteuning voor Lookout <!-- 1087312 -->   
De Intune-connector met Lookout biedt ondersteuning voor Android for Work-apparaten wanneer u de Lookout voor Work-app gebruikt. U kunt de Lookout-app in of buiten de container implementeren.


### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner-----954651--and--1172027----"></a>Check Point SandBlast Mobile - nieuwe Mobile Threat Defense-partner  <!-- 954651  and  1172027 ? -->  
U kunt de toegang van mobiele apparaten tot bedrijfsresources beheren door middel van voorwaardelijke toegang op basis van een risicoanalyse die wordt uitgevoerd door Check Point SandBlast Mobile, een oplossing voor de beveiliging tegen bedreigingen op mobiele apparaten die met Microsoft Intune is geïntegreerd.

#### <a name="how-integration-with-intune-works"></a>Hoe werkt de integratie met Intune?
Risico's worden beoordeeld op basis van telemetrische gegevens die zijn verzameld op apparaten met Check Point SandBlast Mobile. U kunt het EMS-beleid voor voorwaardelijke toegang configureren op basis van de risicoanalyse van Check Point SandBlast Mobile die wordt ingeschakeld via het Intune-nalevingsbeleid voor apparaten. U kunt apparaten die niet compatibel zijn op basis van gedetecteerde bedreigingen al dan niet toegang bieden tot bedrijfsresources.

### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium - nieuwe Mobile Threat Defense-partner   <!-- 954681 -->
U kunt de toegang van mobiele apparaten tot bedrijfsresources beheren door middel van voorwaardelijke toegang op basis van een risicoanalyse die wordt uitgevoerd door Zimperium, een oplossing voor de beveiliging tegen bedreigingen op mobiele apparaten die met Microsoft Intune is geïntegreerd.

#### <a name="how-integration-with-intune-works"></a>Hoe werkt de integratie met Intune?
Risico's worden beoordeeld op basis van telemetrische gegevens die zijn verzameld op apparaten met door Zimperium. U kunt het EMS-beleid voor voorwaardelijke toegang configureren op basis van de Zimperium-risicoanalyse die via het Intune-nalevingsbeleid voor apparaten wordt ingeschakeld. U kunt met dit beleid de toegang tot bedrijfsresources voor niet-compatibele apparaten toestaan of blokkeren op basis van de gedetecteerde bedreigingen.

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Hoge beschikbaarheid van on-premises Exchange Connector  <!-- 676614 -->   
U kunt meerdere CAS-rollen (Client Access Server) instellen voor on-premises Exchange Connector. Als de hoofd-CA bijvoorbeeld uitvalt, ontvangt Exchange Connector een query om over te schakelen naar een andere CAS. Deze functie zorgt ervoor dat de service niet wordt onderbroken.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Management pack van System Center Operations Manager voor Exchange Connector <!-- 885457 -->   
Het management pack van System Center Operations Manager voor Exchange Connector kunt u gebruiken om de logboeken van Exchange Connector te parseren. Zodoende kunt u Intune op verschillende manieren controleren wanneer u problemen moet oplossen.

### <a name="conditional-access-support-for-mac-devices-----720172---"></a>Ondersteuning voor voorwaardelijke toegang voor Mac-apparaten  <!-- 720172 -->   
U kunt binnenkort een beleid voor voorwaardelijke toegang instellen waardoor Mac-apparaten moeten worden geregistreerd bij Intune en moeten voldoen aan het Intune-nalevingsbeleid voor apparaten. Gebruikers kunnen bijvoorbeeld de Intune-bedrijfsportal-app voor macOS downloaden en hun Mac-apparaten registreren bij Intune. Er wordt vervolgens een evaluatie uitgevoerd in Intune om te bepalen of het Mac-apparaat al dan niet voldoet aan vereisten zoals pincode, versleuteling, versie van het besturingssysteem en systeemintegriteit.

### <a name="end-of-support-for-ios-80----1164477---"></a>Einde van ondersteuning voor iOS 8.0 <!---1164477--->
Beheerde apps en de Intune-bedrijfsportal-app voor iOS vereisen iOS 9.0 en hoger voor toegang tot bedrijfsresources. Apparaten die niet voor september zijn bijgewerkt, hebben geen toegang meer tot de bedrijfsportal of beheerde apps. Vanaf december wordt alle toegang tot bedrijfsresources, inclusief e-mail, voorkomen. 

### <a name="end-of-support-for-android-43-and-lower----1171127---"></a>Einde van ondersteuning voor Android 4.3 en lager <!---1171127--->
Beheerde apps en de Intune-bedrijfsportal-app voor Android vereisen Android 4.4 en hoger voor toegang tot bedrijfsresources. Apparaten die niet voor begin van oktober zijn bijgewerkt, hebben geen toegang meer tot de bedrijfsportal of beheerde apps. Vanaf december worden alle ingeschreven apparaten verplicht buiten gebruik gesteld, waardoor bedrijfsresources niet meer toegankelijk zijn. Als u beleid voor app-beveiliging zonder MDM gebruikt, krijgen apps geen updates meer en neemt de gebruikservaring na verloop van tijd steeds verder af.





### <a name="platform-support-reminder-windows-phone-81-mainstream-support-will-end-july-11-2017----1327781---"></a>Herinnering voor platformondersteuning: de algemene ondersteuning voor Windows Phone 8.1 stopt op 11 juli 2017 <!-- 1327781 -->  
Op 11 juli 2017 stopt de algemene ondersteuning voor het Windows Phone 8.1-platform. De ondersteuning voor Windows 8.1 voor pc's loopt gewoon door.

Er zijn geen directe gevolgen voor een apparaat met Windows Phone 8.1 dat wordt beheerd door de Intune-service. Apparaten die zijn ingeschreven, blijven gewoon werken en alle beleidsregels, configuraties en apps blijven eveneens werken zoals verwacht. Het is wel zo dat er geen verbeteringen meer worden aangebracht aan het Windows Phone 8.1-platform in de Intune-service, en evenmin voor de Intune-bedrijfsportal-app voor Windows Phone 8.1.

Het is raadzaam om in aanmerking komende Windows Phone 8.1-apparaten zo snel mogelijk te upgraden naar Windows 10 Mobile. 




## <a name="whats-coming-to-intune-apps"></a>Binnenkort in de gebruikersinterface van Intune-apps

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Verbeterde aanmeldervaring in de bedrijfsportal-apps voor alle platformen <!--User Story 1132123-->    
Dit is de aankondiging van een wijziging die in de komende maanden wordt geïntroduceerd en waarmee de aanmeldervaring wordt verbeterd voor apps in de Intune-bedrijfsportal voor Android, iOS en Windows. De nieuwe gebruikerservaring wordt automatisch toegepast op alle platformen voor de bedrijfsportal-app wanneer deze wijziging wordt doorgevoerd in Azure AD. Bovendien kunnen gebruikers nu zich aanmelden bij de bedrijfsportal vanaf een ander apparaat met een gegenereerde code voor eenmalig gebruik. Dit is vooral nuttig in gevallen wanneer gebruikers zich moeten aanmelden zonder referenties.

Op de pagina [Wat is er nieuw in de app-interface](whats-new-app-ui.md) ziet u schermafbeeldingen van de vorige aanmeldingservaring, de nieuwe aanmeldingservaring met referenties en de nieuwe aanmeldingservaring vanaf een ander apparaat.

### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Lichte en donkere modi beschikbaar voor de Intune-bedrijfsportal-app voor Windows 10 <!---676547--->
Eindgebruikers kunnen de kleurenmodus voor de Intune-bedrijfsportal-app voor Windows 10 aanpassen. Dit kan in de sectie Instellingen van de Intune-bedrijfsportal-app. De wijziging wordt van kracht nadat de gebruiker de app opnieuw heeft gestart. Voor Windows 10 versie 1607 en hoger wordt voor de app-modus standaard de systeeminstelling gebruikt. Voor pc's met Windows 10 versie 1511 en eerder wordt de app modus standaard ingesteld op de lichte modus.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10----807046--"></a>Eindgebruikers kunnen hun apparaatgroep taggen in de Intune-bedrijfsportal-app voor Windows 10 <!---807046-->    
Eindgebruikers kunnen aangeven bij welke groep hun apparaat hoort door deze rechtstreeks vanuit de Intune-bedrijfsportal-app voor Windows 10 te taggen.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Eindgebruikers zonder inschrijving toegang geven tot de Intune-bedrijfsportal-app voor Android <!---1169910--->  
Eindgebruikers hoeven hun apparaat binnenkort niet meer in te schrijven om toegang te krijgen tot de Intune-bedrijfsportal-app voor Android. Eindgebruikers in organisaties die gebruikmaken van beleid voor app-beveiliging zien bij het openen van de Intune-bedrijfsportal-app geen instructie meer dat ze hun apparaat moeten registreren. Bovendien kunnen eindgebruikers apps installeren via de bedrijfsportal zonder dat ze hun apparaat hoeven te registreren. 

### <a name="users-who-are-signed-in-to-exchange-can-automatically-access-the-company-portal-website-on-windows-10-devices---1323204--"></a>Gebruikers die zijn aangemeld bij Exchange kunnen automatisch toegang krijgen tot de bedrijfsportal-website op Windows 10-apparaten <!--1323204-->  
Windows 10 gebruikers die al zijn geverifieerd in Exchange,en die een e-mailbericht voor voorwaardelijke toegang in quarantaine ontvangen en klikken op de koppeling in de e-mail, hoeven zich niet meer opnieuw te verifiëren in de browser om toegang tot de bedrijfsportal in te stellen.


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
