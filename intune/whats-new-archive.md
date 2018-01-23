---
title: Wat was er de vorige maanden nieuw in Microsoft Intune
titlesuffix: Azure portal
description: Raadpleeg oudere berichten op de Wat is er nieuw-pagina voor Intune
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9ba01d60-4a03-4e3e-9aba-8be905c0054c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4564155c2fb94ac2726d002b3ea5eb09916eff10
ms.sourcegitcommit: 22ab1c6a6bfeb4fef9850d12b29829c3fecbbeed
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/12/2018
---
# <a name="whats-new-in-the-microsoft-intune---previous-months"></a>Wat is er nieuw in Microsoft Intune - vorige maanden

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="september-2017"></a>September 2017

### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>Eindgebruikers informeren welke apparaatgegevens voor iOS kunnen worden gezien <!--739894-->

Aan het scherm voor apparaatgegevens in de bedrijfsportal-app voor iOS is de optie **Eigendomstype** toegevoegd. Hierdoor kunnen gebruikers meer over privacy te weten komen vanaf deze pagina in de documenten voor Intune-eindgebruikers. Deze informatie is ook te vinden op het scherm Info.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Eindgebruikers zonder inschrijving toegang geven tot de Intune-bedrijfsportal-app voor Android <!---1169910--->

Eindgebruikers hoeven hun apparaat binnenkort niet meer in te schrijven om toegang te krijgen tot de Intune-bedrijfsportal-app voor Android. Eindgebruikers in organisaties die gebruikmaken van beleid voor app-beveiliging zien bij het openen van de Intune-bedrijfsportal-app geen instructie meer dat ze hun apparaat moeten registreren. Bovendien kunnen eindgebruikers apps installeren via de bedrijfsportal zonder dat ze hun apparaat hoeven te registreren. 


### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android----1396349---"></a>Gemakkelijker te begrijpen formulering voor de bedrijfsportal-app voor Android <!---1396349--->  

Het inschrijvingsproces voor de bedrijfsportal-app voor Android is vereenvoudigd met nieuwe tekst om het eindgebruikers gemakkelijker te maken om zich in te schrijven. Als u aangepaste inschrijvingsdocumentatie hebt, is het aan te raden om die bij te werken met de nieuwe schermen. Voorbeeldafbeeldingen zijn te vinden op de pagina [UI-updates voor Intune-apps voor eindgebruikers](whats-new-app-ui.md#week-of-september-11-2017).

### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy----677129---"></a>Windows 10-bedrijfsportal-app toegevoegd het toelatingsbeleid van Windows Information Protection <!-- 677129 -->

De Windows 10-bedrijfsportal-app is bijgewerkt met ondersteuning voor Windows Information Protection (WIP). De app kan worden toegevoegd aan het toelatingsbeleid van WIP. Door deze wijziging hoeft de app niet langer te worden toegevoegd aan de lijst **Uitgezonderd**.


## <a name="august-2017"></a>Augustus 2017

### <a name="improvements-to-device-overview----1404453---"></a>Verbeteringen aan het apparaatoverzicht <!-- 1404453 -->  
Door verbeteringen aan het apparaatoverzicht worden nu geregistreerde apparaten weergegeven, met uitzondering van apparaten die worden beheerd door Exchange ActiveSync. Exchange ActiveSync-apparaten hebben niet dezelfde beheeropties als geregistreerde apparaten. Als u het aantal geregistreerde apparaten en het aantal geregistreerde apparaten per platform in Intune in de Azure-portal wilt zien, gaat u naar **Apparaten** > **overzicht**.

### <a name="improvements-to-device-inventory-collected-by-intune"></a>Verbeteringen aan de apparaatinventaris verzameld door Intune
<!-- 961134, 1104426, 1281327, 1333543 -->
We hebben in deze versie de volgende verbeteringen aangebracht in de inventarisatiegegevens die zijn verzameld door apparaten die u beheert:
 
-   Voor Android-apparaten kunt u nu een kolom aan de apparaatinventaris toevoegen die het meest recente patchniveau voor elk apparaat laat zien. Voeg de kolom **Beveiligingspatchniveau** toe aan uw apparatenlijst om dit te zien.
-   Als u de apparaatweergave filtert, kunt u nu apparaten filteren op de datum waarop ze zijn geregistreerd. U kunt bijvoorbeeld alleen die apparaten weergeven die zijn geregistreerd na een datum die u opgeeft.
-   We hebben verbeteringen aangebracht aan het filter dat wordt gebruikt door het **Laatste check-in**-item.
-   U kunt nu het telefoonnummer van bedrijfsapparaten weergeven in de lijst met apparaten.
Daarnaast kunt u het filterdeelvenster gebruiken om te zoeken naar apparaten op telefoonnummer.
 
Zie [Inventaris van Intune-apparaten weergeven](device-inventory.md) voor meer informatie over apparaatinventarisatie.

### <a name="conditional-access-support-for-macos-devices"></a>Ondersteuning voor voorwaardelijke toegang voor macOS-apparaten 
<!-- 720172 -->
U kunt nu een beleid voor voorwaardelijke toegang instellen waardoor Mac-apparaten moeten worden geregistreerd bij Intune en moeten voldoen aan het Intune-nalevingsbeleid voor apparaten. Gebruikers kunnen bijvoorbeeld de Intune-bedrijfsportal-app voor macOS downloaden en hun Mac-apparaten registreren bij Intune. Er wordt vervolgens een evaluatie uitgevoerd in Intune om te bepalen of het Mac-apparaat al dan niet voldoet aan vereisten zoals pincode, versleuteling, versie van het besturingssysteem en systeemintegriteit.

- Meer informatie over [ondersteuning voor voorwaardelijke toegang voor macOS-apparaten](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).

### <a name="company-portal-app-for-macos-is-in-public-preview----1484796---"></a>Bedrijfsportal-app voor macOS is in openbare preview <!---1484796--->
De bedrijfsportal-app voor macOS is nu beschikbaar als onderdeel van de openbare preview voor voorwaardelijke toegang in Enterprise Mobility + Security. Deze release ondersteunt macOS 10.11 en hoger. Download deze op [https://aka.ms/macOScompanyportal](https://aka.ms/macOScompanyportal). 


### <a name="new-device-restriction-settings-for-windows-10"></a>Nieuwe apparaatbeperkingsinstellingen voor Windows 10    
<!--1063965, 1308850  -->
In deze release hebben we nieuwe instellingen toegevoegd voor het [profiel voor apparaatbeperking van Windows 10](/intune/device-restrictions-windows-10), en wel in de volgende categorieën:

-   Windows Defender SmartScreen
-   App Store

### <a name="updates-to-the-windows-10-endpoint-protection-device-profile-for-bitlocker-settings"></a>Updates voor het apparaatprofiel voor Windows 10 Endpoint Protection voor BitLocker-instellingen
<!--1459533 -->    
We hebben in deze release de volgende verbeteringen aangebracht in de werking van BitLocker-instellingen in een apparaatprofiel voor Windows 10 Endpoint Protection:
 
Wanneer u onder **BitLocker-instellingen voor OS-stations**, voor de instelling **BitLocker met niet-compatibele TPM-chip**, de optie **Blokkeren** selecteert, zou BitLocker voorheen daadwerkelijk worden toegestaan. We hebben dit nu opgelost door BitLocker te blokkeren wanneer deze optie is geselecteerd.
U kunt nu onder **BitLocker-instellingen voor OS-stations**, voor de instelling **Agent voor herstel van gegevens op basis van een certificaat**, expliciet de agent voor herstel van gegevens op basis van een certificaat blokkeren. Standaard is de agent echter toegestaan.
U kunt nu onder **Instellingen voor met BitLocker beveiligde vaste-gegevensstations**, voor de instelling **Agent voor gegevensherstel**, expliciet de agent voor gegevensherstel blokkeren.
Zie [Instellingen voor de beveiliging van eindpunten voor Windows 10 en hoger](endpoint-protection-windows-10.md) voor meer informatie.


### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users----621669---"></a>Nieuwe aanmeldingsmogelijkheid voor gebruikers van de Android-bedrijfsportal en van het app-beveiligingsbeleid <!-- 621669 -->
Eindgebruikers kunnen nu in apps bladeren, apparaten beheren en de gegevens voor de IT-contactpersoon bekijken met de Android-bedrijfsportal-app zonder dat ze hun Android-apparaten hoeven in te schrijven. Als een eindgebruiker al een app gebruikt die wordt beveiligd door Intune-app-beveiligingsbeleid en de Android-bedrijfsportal opent, wordt hem of haar ook niet meer gevraagd het apparaat in te schrijven.

### <a name="new-setting-in-the-android-company-portal-app-to-toggle-battery-optimization---1405990--"></a>Nieuwe instelling in de Android-bedrijfsportal-app om batterijoptimalisatie in- of uit te schakelen <!--1405990-->
De pagina **Instellingen** in de bedrijfsportal-app voor Android heeft een nieuwe instelling. Hiermee kunnen gebruikers gemakkelijk batterijoptimalisatie uitschakelen voor bedrijfsportal- en Microsoft Authenticator-apps. De naam van de app die in de instelling wordt getoond, is afhankelijk van welke app het werkaccount beheert. Gebruikers wordt aangeraden batterijoptimalisatie uit te schakelen voor betere prestaties van werk-apps die e-mail en gegevens synchroniseren. 

### <a name="multi-identity-support-for-onenote-for-ios---------1234281---"></a>Ondersteuning voor meerdere identiteiten voor OneNote voor iOS     <!-- 1234281 -->
Eindgebruikers kunnen nu verschillende accounts (voor werk en privé) gebruiken met Microsoft OneNote voor iOS. App-beveiligingsbeleid kan worden toegepast op bedrijfsgegevens in notitieblokken voor het werk zonder dat dit van invloed is op hun persoonlijke notitieblokken. Een beleid kan bijvoorbeeld toestaan dat een gebruiker naar informatie zoekt in notitieblokken van het werk, maar voorkomen dat de gebruiker bedrijfsgegevens vanuit het notitieblok kopieert naar een persoonlijk notitieblok.
 
- Meer informatie over de apps die ondersteuning bieden voor [app-beveiliging en meervoudige identiteiten](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) met Intune.

### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices"></a>Nieuwe instellingen om apps toe te staan of te blokkeren voor Samsung Knox Standard-apparaten
<!-- 1305423 822899-->  
In deze release voegen we nieuwe [instellingen voor apparaatbeperkingen](device-restrictions-android.md) toe waarmee u de volgende app-lijsten kunt opgeven:
 
- Apps die gebruikers mogen installeren
- Apps die gebruikers niet kunnen uitvoeren
- Apps die voor de gebruiker worden verborgen op het apparaat
 
U kunt de app opgeven met de URL of met de pakketnaam opgeven, of kiezen in de lijst met apps die u beheert.

### <a name="new-azure-ad-app-based-conditional-access-policy-ui-link-from-intune"></a>Koppeling van Intune naar de nieuwe gebruikersinterface voor beleid voor op apps gebaseerde voorwaardelijke toegang van Azure AD
<!-- 1016201 -->
IT-beheerders kunnen nu op apps gebaseerd voorwaardelijk beleid instellen via de nieuwe gebruikersinterface voor beleid voor voorwaardelijke toegang in de Azure AD-werkbelasting. De op apps gebaseerde voorwaardelijke toegang in de sectie Intune-app-beveiliging in de Azure-portal blijft hier voorlopig aanwezig en wordt naast elkaar afgedwongen. Er is in de Intune-werkbelasting ook een handige koppeling naar de nieuwe gebruikersinterface voor beleid voor voorwaardelijke toegang.

- Meer informatie over [op apps gebaseerde voorwaardelijke toegang in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference).



## <a name="july-2017"></a>Juli 2017

### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version------1333256--1245463----"></a>Registratie van Android- en iOS-apparaten beperken op basis van de versie van het besturingssysteem  <!--- 1333256,  1245463 --->
Intune biedt nu ondersteuning voor het beperken van registraties van iOS- en Android-apparaten op basis van het versienummer van het besturingssysteem. Bij **Apparaattypebeperking** kan de IT-beheerder een platformconfiguratie instellen met een minimum- en maximumversie van het besturingssysteem, zodat alleen apparaten met versies in dit bereik kunnen worden geregistreerd. De versies van het Android-besturingssysteem moeten worden opgegeven als Major.Minor.Build.Rev, waarbij Minor, Build en Rev optioneel zijn. iOS-versies moeten worden opgegeven als Primair.Secundair.Build, waarbij Minor en Build optioneel zijn. Meer informatie over [beperkingen voor het registreren van apparaten](enrollment-restrictions-set.md).

>[!NOTE]
>Registratie via het inschrijvingsprogramma van Apple of Apple Configurator wordt niet beperkt.

### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment------1333272--1333275-1245709----"></a>Apparaatregistratie beperken van Android-, iOS- en macOS-apparaten die privé-eigendom zijn  <!--- 1333272,  1333275, 1245709 --->
Intune kan de registratie van persoonlijke apparaten beperken door IMEI-nummers van bedrijfsapparaten op te nemen in een lijst met toegestane apparaten. De functionaliteit van Intune is nu uitgebreid naar iOS, Android en macOS via het gebruik van de serienummers van apparaten. Door serienummers te uploaden naar Intune, kunt u apparaten vooraf markeren als bedrijfseigendom. Aan de hand van inschrijvingsbeperkingen kunt u de registratie blokkeren van apparaten die privé-eigendom (BYOD) zijn. Op deze manier maakt u beleid waardoor alleen apparaten kunnen worden ingeschreven die bedrijfseigendom zijn. Meer informatie over [beperkingen voor het registreren van apparaten](enrollment-restrictions-set.md).

Als u serienummers wilt importeren in, gaat u naar **Apparaatinschrijving** > **Bedrijfsapparaat-id's** en klikt u op **Toevoegen**. Upload vervolgens een CSV-bestand met deze specificaties (geen header, twee kolommen, één voor de serienummers en één voor gegevens zoals IMEI-nummers).  Als u de registratie van apparaten in privé-eigendom wilt beperken, gaat u naar **Apparaatinschrijving** > **Inschrijvingsbeperkingen**. Selecteer **Standaard** onder **Apparaattypebeperking** en selecteer vervolgens **Platformconfiguraties**. Selecteer **Toestaan** of **Blokkeren** voor iOS-, Android- en macOS-apparaten die privé-eigendom zijn. 


### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>Nieuwe apparaatactie om apparaten geforceerd te synchroniseren met Intune <!-- 711369 -->
In deze versie is een nieuwe apparaatactie toegevoegd die ervoor zorgt dat het geselecteerde apparaat direct wordt ingecheckt bij Intune. Wanneer een apparaat wordt ingecheckt, worden direct eventuele openstaande acties of toegewezen beleidsregels ontvangen die erop zijn toegepast.  Met deze actie kunt u toegewezen beleid meteen controleren en in het geval van problemen direct aanpassen, zonder dat u hoeft te wachten op de volgende geplande check-in.
Zie [Apparaat synchroniseren](device-sync.md) voor meer informatie

### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>Nieuwste software-update geforceerd installeren op iOS-apparaten die onder supervisie staan<!-- 777100 -->
Er is een nieuw beleid beschikbaar in de werkruimte Software-updates waarmee u kunt afdwingen dat automatisch de nieuwste software-update wordt geïnstalleerd op onder supervisie staande iOS-apparaten. Zie [Updatebeleid voor iOS configureren](/intune/software-updates-ios) voor meer informatie

### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner-----954651-1172027---"></a>Check Point SandBlast Mobile - nieuwe Mobile Threat Defense-partner  <!-- 954651, 1172027 -->
U kunt de toegang van mobiele apparaten tot bedrijfsresources beheren door middel van voorwaardelijke toegang op basis van een risicoanalyse die wordt uitgevoerd door Check Point SandBlast Mobile, een oplossing voor de beveiliging tegen bedreigingen op mobiele apparaten die met Microsoft Intune is geïntegreerd.

#### <a name="how-integration-with-intune-works"></a>Hoe werkt de integratie met Intune?
Risico's worden beoordeeld op basis van telemetriegegevens die zijn verzameld op apparaten met Check Point SandBlast Mobile. U kunt het EMS-beleid voor voorwaardelijke toegang configureren op basis van de risicoanalyse van Check Point SandBlast Mobile die wordt ingeschakeld via het Intune-nalevingsbeleid voor apparaten. U kunt apparaten die niet compatibel zijn op basis van gedetecteerde bedreigingen al dan niet toegang bieden tot bedrijfsresources.


### <a name="deploy-an-app-as-available-in-the-microsoft-store-for-business----748101---"></a>Een app als beschikbaar implementeren in Microsoft Store voor Bedrijven <!-- 748101 -->
Met deze versie kunnen beheerders de Microsoft Store voor Bedrijven nu toewijzen als beschikbaar. Wanneer Microsoft Store voor Bedrijven is ingesteld als beschikbaar, kunnen eindgebruikers de app installeren via de bedrijfsportal-app of -website zonder dat ze worden omgeleid naar de Microsoft Store.

### <a name="ui-updates-to-the-company-portal-website---1313244-part-1--"></a>Updates aan de gebruikersinterface van de bedrijfsportalwebsite <!--1313244 part 1-->
Er zijn een aantal updates aan de gebruikersinterface van de [bedrijfsportalwebsite](https://portal.manage.microsoft.com) uitgevoerd om de gebruikerservaring te verbeteren.

- __Verbeteringen aan app-tegels__: app-pictogrammen worden nu weergegeven met een achtergrond die automatisch wordt gegenereerd op basis van de overheersende kleur van het pictogram (mits detecteerbaar). Indien van toepassing wordt de grijze rand die voorheen zichtbaar was op app-tegels, vervangen door deze achtergrond.

    In de volgende versie worden er waar mogelijk grote pictogrammen weergegeven op de bedrijfsportalwebsite. IT-beheerders wordt aangeraden apps te publiceren met pictogrammen met een hoge resolutie en een minimumgrootte van 120 x 120 pixels. 

- __Wijzigingen in de navigatie__: items op de navigatiebalk zijn verplaatst naar het hamburgermenu linksboven. De pagina Categorieën is verwijderd. Gebruikers kunnen nu tijdens het browsen inhoud filteren op categorie.

- __Updates voor aanbevolen apps__: Er is een speciale pagina aan de site toegevoegd waar gebruikers door apps kunnen bladeren die door u zijn aanbevolen. Ook zijn er enkele correcties aan de gebruikersinterface aangebracht in de sectie Aanbevolen op de startpagina.

### <a name="ibooks-support-for-the-company-portal-website---1231841--"></a>Ondersteuning van iBooks voor de bedrijfsportalwebsite <!--1231841-->
Er is een speciale pagina toegevoegd aan de bedrijfsportalwebsite waarmee gebruikers iBooks kunnen zoeken en downloaden. 


### <a name="additional-help-desk-troubleshooting-details------applies-to-1263399-1326964-1341642----"></a>Aanvullende helpdeskgegevens voor probleemoplossing <!---  Applies to 1263399, 1326964, 1341642 --->
De weergave voor probleemoplossing in Intune is bijgewerkt en toegevoegd aan de informatie voor beheerders en hepdeskmedewerkers. U ziet nu een tabel **Toewijzingen** met een overzicht van alle toewijzingen voor de gebruiker op basis van groepslidmaatschap. Dit overzicht bevat:
- Mobiele apps
- Nalevingsbeleid
- Configuratieprofielen
 
Bovendien zijn in de tabel **Apparaten** nu de kolommen **Type Azure AD-join** en **Azure AD-compatibel** opgenomen. Zie voor meer informatie [Gebruikers helpen om problemen op te lossen](help-desk-operators.md).



### <a name="intune-data-warehouse-public-preview"></a>Intune-datawarehouse (openbare preview-versie)
In het Intune-datawarehouse worden dagelijks gegevens verzameld om een historisch overzicht te bieden van uw tenant. U kunt hebt toegang tot de gegevens via een Power BI-bestand (PBIX), een OData-koppeling die compatibel is met tal van analysehulpprogramma's of via interactie met de REST API. Zie [Het Intune-datawarehouse gebruiken](reports-nav-create-intune-reports.md) voor meer informatie.


### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Lichte en donkere modi beschikbaar voor de Intune-bedrijfsportal-app voor Windows 10 <!---676547--->
Eindgebruikers kunnen de kleurenmodus voor de Intune-bedrijfsportal-app voor Windows 10 aanpassen. Dit kan in de sectie Instellingen van de Intune-bedrijfsportal-app. De wijziging wordt van kracht nadat de gebruiker de app opnieuw heeft gestart. Voor Windows 10 versie 1607 en hoger wordt voor de app-modus standaard de systeeminstelling gebruikt. Voor Windows 10 versie 1511 en lager wordt voor de app-modus standaard de lichte modus gebruikt.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10----807046--"></a>Eindgebruikers kunnen hun apparaatgroep taggen in de Intune-bedrijfsportal-app voor Windows 10 <!---807046-->
Eindgebruikers kunnen voortaan aangeven bij welke groep hun apparaat hoort door deze rechtstreeks vanuit de bedrijfsportal-app voor Windows 10 te taggen.



## <a name="june-2017"></a>Juni 2017

### <a name="new-role-based-administration-access-for-intune-admins------1099990---"></a>Nieuwe toegangsrol voor Intune-beheerders   <!-- 1099990 -->  
Er wordt een nieuwe beheerdersrol voor voorwaardelijke toegang toegevoegd waarmee het voorwaardelijke toegangsbeleid van Azure AD kan worden weergegeven, gemaakt en gewijzigd. Voorheen beschikten alleen hoofdbeheerders en beveiligingsbeheerders over deze machtiging. Deze rolmachtiging kan nu ook worden toegekend aan Intune-beheerders, zodat ze toegang hebben tot de beleidsregels voor voorwaardelijke toegang.


### <a name="tag-corporate-owned-devices-with-serial-number----1215070---"></a>Labelen van apparaten in bedrijfseigendom met een serienummer <!-- 1215070 -->  
Intune ondersteunt nu het uploaden van serienummers van iOS-, macOS- en Android-apparaten als id's van apparaten in bedrijfseigendom. U kunt op dit moment geen serienummers gebruiken om de registratie van persoonlijke apparaten te blokkeren, omdat er geen serienummers worden geverifieerd tijdens de registratie. U kunt persoonlijke apparaten binnenkort ook blokkeren op basis van het serienummer.


### <a name="new-remote-actions-for-ios-devices----854689---"></a>Nieuwe externe acties voor iOS-apparaten <!-- 854689 -->
In deze release zijn twee nieuwe acties voor externe apparaten toegevoegd voor gedeelde iPad-apparaten die de Apple Classroom-app beheren:

-   [Huidige gebruiker afmelden](device-logout-user.md): hiermee kunt u de huidige gebruiker afmelden van een iOS-apparaat dat u kiest.
-   [Gebruiker verwijderen](device-remove-user.md): hiermee kunt u een gebruiker verwijderen uit de lokale cache op een iOS-apparaat.


### <a name="support-for-shared-ipads-with-the-ios-classroom-app----1044681---"></a>Ondersteuning voor gedeelde iPads met de iOS-app Classroom <!-- 1044681 -->
In deze release is de ondersteuning voor het beheren van de iOS-app Classroom uitgebreid naar studenten die zich met hun beheerde Apple ID aanmelden bij gedeelde iPads.


### <a name="changes-to-intune-built-in-apps----1332306---"></a>Wijzigingen aan in Intune ingebouwde apps <!-- 1332306 -->
Voorheen bevatte Intune een aantal ingebouwde apps die u snel kon toewijzen. Op basis van uw feedback is deze lijst verwijderd en krijgt u niet langer ingebouwde apps te zien.
Als u echter al ingebouwde apps hebt toegewezen, dan zijn deze nog steeds zichtbaar in de lijst met apps. U kunt deze apps desgewenst blijven toewijzen.
In een volgende release wordt een makkelijkere methode toegevoegd voor het selecteren en toewijzen van ingebouwde apps vanuit de Azure-portal.

### <a name="easier-installation-of-office-365-apps-----1121362----"></a>Eenvoudigere installatie van Office 365-apps <!--- 1121362 --->
Het nieuwe app-type **Office 365 ProPlus** maakt het eenvoudig voor u om Office 365 ProPlus 2016-apps toe te wijzen aan apparaten die u beheert waarop de nieuwste versie van Windows 10 wordt uitgevoerd. Daarnaast kunt u Microsoft Project en Microsoft Visio installeren, als u licenties hebt voor deze producten. De gewenste apps worden gebundeld en worden als één app weergegeven in de lijst met apps in de Intune-console.
Zie [Office 365-apps voor Windows 10 toevoegen](apps-add-office365.md) voor meer informatie.


### <a name="support-for-offline-apps-from-the-microsoft-store-for-business-----777044----"></a>Ondersteuning voor offlineapps uit Microsoft Store voor Bedrijven <!--- 777044 --->
Offlineapps die u hebt gekocht in Microsoft Store voor Bedrijven worden voortaan gesynchroniseerd met de Azure-portal. Vervolgens kunt u deze apps implementeren naar apparaat- of gebruikersgroepen. Offline apps worden geïnstalleerd door Intune en niet door de store.

### <a name="microsoft-teams-is-now-part-of-the-app-based-ca-list-of-approved-apps------1257019---"></a>Microsoft Teams is nu opgenomen in de lijst met goedgekeurde apps voor voorwaardelijke toegang   <!-- 1257019 -->
De Microsoft Teams-app voor iOS en Android is nu een goedgekeurde app voor toepassing van beleid voor voorwaardelijke toegang op basis van apps voor Exchange en SharePoint Online. De app kan via de blade Intune-app-beveiliging in Azure Portal worden geconfigureerd voor alle tenants die op dit moment gebruikmaken van voorwaardelijke toegang op basis van apps.

### <a name="managed-browser-and-app-proxy-integration----1287310---"></a>Managed Browser en app-proxy-integratie <!-- 1287310 -->
De Intune-app Managed Browser kan nu worden geïntegreerd met de Azure AD-toepassingsproxy om gebruikers ook toegang te bieden tot interne websites als ze op afstand werken. Gebruikers van de browser voeren op de gebruikelijke manier de URL van de gewenste site in en de Managed Browser-app verstuurt de aanvraag via de webgateway van de toepassingsproxy. Zie [Internettoegang beheren met beleid van Managed Browser](app-configuration-managed-browser.md) voor meer informatie.

### <a name="new-app-configuration-settings-for-the-intune-managed-browser----682951---"></a>Nieuw app-configuratie-instellingen voor Intune Managed Browser <!-- 682951 -->
In deze release hebben we weer extra configuraties toegevoegd voor de Intune Managed Browser-app voor iOS en Android. U kunt nu een beleid voor app-configuratie gebruiken om de standaardstartpagina en -bladwijzers voor de browser te configureren.
Zie [Internettoegang beheren met beleid van Managed Browser](app-configuration-managed-browser.md) voor meer informatie.

### <a name="bitlocker-settings-for-windows-10-----951707---"></a>BitLocker-instellingen voor Windows 10  <!-- 951707 -->
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


### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a>De Intune-bedrijfsportal-app voor Android heeft een nieuwe interface voor app-beveiligingsbeleid <!--1305217-->
Op basis van feedback van klanten hebben we de Intune-bedrijfsportal-app voor Android aangepast en de knop **Toegang verkrijgen tot bedrijfsinhoud** toegevoegd. De reden hiervoor is dat eindgebruikers dan niet onnodig het registratieproces moeten doorlopen wanneer ze alleen toegang nodig hebben tot apps die ondersteuning bieden voor app-beveiligingsbeleid, een functie van Intune Mobile Application Management. U kunt deze wijzigingen zien op [deze pagina](whats-new-app-ui.md).

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>Nieuwe menu-actie voor het eenvoudig verwijderen van de bedrijfsportal <!--1164569-->
Op basis van feedback van gebruikers is aan de bedrijfsportal-app voor Android een nieuwe menu-actie toegevoegd om het verwijderen van de bedrijfsportal van uw apparaat te starten. Met deze actie verwijdert u het apparaat uit Intune-beheer, zodat de app door de gebruiker van het apparaat kan worden verwijderd. U kunt deze wijzigingen zien op de pagina [Wat is er nieuw in de gebruikersinterface van apps](whats-new-app-ui.md) en in de [Android-eindgebruikersdocumentatie](/intune-user-help/unenroll-your-device-from-intune-android).

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>Verbeterde synchronisatie van apps met Windows 10-makersupdate <!--676505-->
De bedrijfsportal-app voor Windows 10 voert nu automatisch een synchronisatie uit voor app-installatieaanvragen voor apparaten met Windows 10-makersupdate (versie 1703). Hierdoor is de kans aanzienlijk kleiner dat app-installaties worden gestopt tijdens de status Synchronisatie in behandeling. Daarnaast kunnen gebruikers handmatig een synchronisatie uitvoeren vanuit de app. U kunt deze wijzigingen zien op [deze pagina](whats-new-app-ui.md).

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Nieuwe begeleide ervaring voor Windows 10-bedrijfsportal<!---1058938--->
De bedrijfsportal-app voor Windows 10 bevat een begeleiding voor Intune voor apparaten die nog niet zijn geïdentificeerd of geregistreerd. Deze nieuwe ervaring biedt stapsgewijze instructies die gebruikers begeleidt bij de registratie bij Azure Active Directory (vereist voor de voorwaardelijke toegangsfuncties) en MDM-registratie (vereist voor apparaatbeheerfuncties). De stapsgewijze instructies zijn toegankelijk via de startpagina van de bedrijfsportal. Als gebruikers de registratie en inschrijving niet voltooien, kunnen ze de app gewoon blijven gebruiken, maar is de functionaliteit beperkt.

Deze update is alleen zichtbaar op apparaten met Windows 10 Jubileumupdate (build 1607) of hoger. U kunt deze wijzigingen zien op [deze pagina](whats-new-app-ui.md).


### <a name="microsoft-intune-and-conditional-access-admin-consoles-are-generally-available"></a>Beheerconsoles voor Microsoft Intune en Voorwaardelijke toegang zijn algemeen beschikbaar
Microsoft kondigt de algemene beschikbaarheid van zowel de nieuwe Intune in de beheerconsole van de Azure-portal als de beheerconsole voor Voorwaardelijke toegang aan. Via Intune in de Azure-portal kunt u nu alle Intune MAM- en de MDM-mogelijkheden beheren in één geconsolideerde beheerderservaring en gebruikmaken van groeperen en doelen instellen met Azure AD. Voorwaardelijke toegang in Azure biedt uitgebreide mogelijkheden in Azure AD en Intune samen in één centrale console. En vanuit beheerdersoogpunt kunt u door de overgang naar het Azure-platform gebruikmaken van moderne browsers.

Intune is nu zichtbaar zonder het label **preview** in de Azure-portal op portal.azure.com.

Er is op dit moment geen actie vereist voor bestaande klanten, tenzij u in het berichtencenter een bericht hebt ontvangen waarin u wordt gevraagd actie te ondernemen, zodat de groepen kunnen worden gemigreerd. Mogelijk hebt u in het berichtencentrum ook een kennisgeving ontvangen waarin wordt gemeld dat de migratie langer duurt als gevolg van fouten aan de kant van Microsoft. Microsoft blijft zich ten volle inzetten voor het migreren van de betrokken klanten.

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>Verbeteringen in de app-tegels in de bedrijfsportal-app voor iOS
Het ontwerp van de app-tegels op de startpagina is bijgewerkt in overeenstemming met de huisstijlkleur die u voor de bedrijfsportal instelt. Raadpleeg [Wat is er nieuw in de gebruikersinterface van apps?](whats-new-app-ui.md) voor meer informatie.

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>Account objectkiezer nu beschikbaar voor de bedrijfsportal-app voor iOS
Gebruikers van iOS-apparaten zien mogelijk onze nieuwe accountkiezer wanneer ze zich aanmelden bij de bedrijfsportal als ze hun werk- of schoolaccount gebruiken voor aanmelding bij andere Microsoft-apps. Raadpleeg [Wat is er nieuw in de gebruikersinterface van apps?](whats-new-app-ui.md) voor meer informatie.

## <a name="may-2017"></a>Mei 2017

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>Wijzig uw MDM-instantie zonder de registratie van beheerde apparaten ongedaan te maken <!--1103950-->
U kunt nu uw MDM-instantie wijzigen zonder dat u contact hoeft op te nemen met Microsoft Ondersteuning en zonder dat u de registratie van bestaande beheerde apparaten ongedaan hoeft te maken om ze vervolgens opnieuw te registreren. In de Configuration Manager-console kunt u uw [MDM-instantie wijzigen](/sccm/mdm/deploy-use/change-mdm-authority) van Ingesteld op Configuration Manager (hybride) naar Microsoft Intune (zelfstandig) of vice versa.


### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Verbeterde melding voor Samsung Knox-opstartpincodes <!--1087143-->
Als eindgebruikers een opstartpincode op Samsung Knox-apparaten moeten instellen om te voldoen aan de versleuteling, wordt er een melding aan eindgebruikers weergegeven. Wanneer eindgebruikers op deze melding tikken, worden ze omgeleid naar de exacte plaats in de app Instellingen.  Voorheen werd de eindgebruiker omgeleid naar het scherm voor het wijzigen van het wachtwoord.

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
Sommige Android-apps uit de store ondersteunen beheerde configuratieopties waarmee een IT-beheerder kan controleren hoe een app wordt uitgevoerd in het werkprofiel. Met Intune kunt u nu de configuraties weergeven die worden ondersteund door een app en deze configureren vanuit de Azure-portal met een configuratieontwerper of een JSON-editor. Zie [Use app configurations for Android for Work](app-configuration-policies-use-android.md) (App-configuraties gebruiken voor Android for Work) voor meer informatie.

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
- Alleen een wachtwoordcodebeleid voor een werkprofiel definiëren: steeds wanneer gebruikers een app in het werkprofiel openen, worden ze gevraagd een wachtwoordcode in te voeren.
- Zowel een apparaat- als een werkprofielbeleid definiëren: de IT-beheer kan verschillende sterktes voor de wachtwoordcodes in het beleid voor apparaten en het beleid voor werkprofielen definiëren (bijvoorbeeld een pincode van vier cijfers om het apparaat te ontgrendelen, maar een pincode van zes cijfers om een werk-app te openen).

Zie [Android for Work-apparaatbeperkingsinstellingen in Microsoft Intune](device-restrictions-android-for-work.md) voor meer informatie.

> [!NOTE]
> Dit is alleen beschikbaar in Android 7.0 en later.  De eindgebruiker kan standaard de twee afzonderlijk gedefinieerde pincodes gebruiken, maar kan er ook voor kiezen om de twee gedefinieerde pincodes te combineren in de sterkste van de twee.

#### <a name="new-settings-for-windows-10-devices----978585---"></a>Nieuwe instellingen voor Windows 10-apparaten <!-- 978585 -->
Er zijn nieuwe [Instellingen beperkingen voor Windows-apparaten](device-restrictions-windows-10.md) toegevoegd. Hiermee worden zaken als draadloze beeldschermen, apparaatdetectie, het schakelen tussen taken en simkaartfoutberichten beheerd.

#### <a name="updates-to-certificate-configuration----918991-and-823198---"></a>Updates voor de certificaatconfiguratie <!-- 918991 and 823198 -->
Wanneer u een SCEP-certificaatprofiel maakt voor **indeling van de onderwerpnaam**, is de **aangepaste** optie beschikbaar voor iOS-, Android- en Windows-apparaten. Voor deze update was het veld **aangepast** beschikbaar voor iOS-apparaten. Zie [Een SCEP-certificaatprofiel maken] (certificates-scep-configure.md#how-to-create-a-scep-certificate-profile) voor meer informatie.

Wanneer u een PKCS certificaatprofiel maakt, is voor **Alternatieve naam voor onderwerp** het **Aangepaste Azure AD-kenmerk** beschikbaar. De optie **Afdeling** is beschikbaar wanneer u **Aangepast Azure AD-kenmerk** selecteert. Zie [Een PKCS-certificaatprofiel maken](certficates-pfx-configure.md#create-a-device-configuration-profile) voor meer informatie.

#### <a name="configure-multiple-apps-that-can-run-when-an-android-device-is-in-kiosk-mode----662059---"></a>Meerdere apps configureren die kunnen worden uitgevoerd wanneer een Android-apparaat in kioskmodus wordt uitgevoerd <!-- 662059 -->
Voorheen kon u slechts één app configureren die mocht worden uitgevoerd op een Android-apparaat dat in kioskmodus wordt uitgevoerd. U kunt nu meerdere apps configureren met de app-ID, de URL van de store of door een Android-app te selecteren die u al beheert. Zie [Instellingen voor kioskmodus](device-restrictions-android.md#kiosk) voor meer informatie.



## <a name="april-2017"></a>April 2017

### <a name="support-for-managing-the-apple-classroom-app"></a>Ondersteuning voor het beheer van de app Apple Classroom
U kunt nu de iOS-app Classroom beheren op iPad-apparaten. Configureer de app Classroom op de iPad van docenten, met de juiste klas- en studentengegevens en configureer vervolgens de iPads van studenten die zijn geregistreerd bij een klas, zodat u deze met de app kunt beheren.
Zie [Opleidingsinstellingen voor iOS configureren](education-settings-configure-ios.md) voor meer informatie.

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Ondersteuning voor beheerde configuratieopties voor Android-apps <!-- 621621 -->
Android-apps in de Play Store die beheerde configuratieopties ondersteunen kunnen nu worden geconfigureerd door Intune.  Dankzij deze functie kan de IT-afdeling een lijst weergeven met de configuratiewaarden die door een app worden ondersteund, en kunnen die waarden worden geconfigureerd in een begeleide, eersteklas gebruikersinterface.

### <a name="new-android-policy-for-complex-pins----722069---"></a>Nieuw Android-beleid voor complexe pincodes <!-- 722069 -->
U kunt een verplicht type [wachtwoord](device-restrictions-android.md#password) instellen op Numeriek complex in een Android-apparaatprofiel voor apparaten met Android 5.0 en hoger.  Met deze instelling voorkomt u dat gebruikers een pincode kiezen die herhalende of opeenvolgende cijfers bevat, zoals 1111 of 1234.

### <a name="additional-support-for-android-for-work-devices"></a>Aanvullende ondersteuning voor Android for Work-apparaten
- **Wachtwoord- en werkprofieleninstellingen beheren** <!-- 612808 -->

  Met dit nieuwe Android for Work-apparaatbeperkingsbeleid kunt u uw wachtwoord- en werkprofielinstellingen beheren op de Android for Work-apparaten die u beheert.

- **Gegevens delen tussen werkprofielen en persoonlijke profielen toestaan** <!-- 1045102 -->

Dit werkprofiel voor Android for Work-apparaatbeperkingen heeft nieuwe opties waarmee u het delen van gegevens tussen werkprofielen en persoonlijke profielen kunt configureren.

- **Kopiëren en plakken tussen werkprofielen en persoonlijke profielen beperken** <!-- 1046094 -->

  Er is nu een nieuw aangepast apparaatprofiel voor Android for Work-apparaten, waarmee u kunt instellen of het kopiëren en plakken tussen werk-apps en persoonlijke apps is toegestaan.

Zie voor meer informatie [Apparaatbeperkingen voor Android for Work](device-restrictions-android-for-work.md).

### <a name="assign-lob-apps-to-ios-and-android-devices----1057568---"></a>LOB-apps toewijzen aan iOS- en Android-apparaten <!-- 1057568 -->
U kunt nu line-of-business-apps (LOB) voor [iOS](lob-apps-ios.md) (IPA-bestanden) en [Android](lob-apps-android.md) (APK-bestanden) toewijzen aan gebruikers of apparaten.


###  <a name="new-device-policies-for-ios----723774-723815-723826-723830---"></a>Nieuw apparaatbeleid voor iOS <!-- 723774, 723815, 723826, 723830 -->
- **Apps op beginscherm**: u kunt instellen welke apps gebruikers zien op het [startscherm van hun iOS-apparaat](home-screen-settings-ios.md). Dit beleid wijzigt de indeling van het beginscherm, maar implementeert geen apps.

- **Verbindingen met AirPrint-apparaten**: u kunt instellen met welke [AirPrint-apparaten](air-print-settings-ios-macos.md) (netwerkprinters) de eindgebruikers van het iOS-apparaat verbinding kunnen maken.

- **Verbindingen met AirPlay-apparaten**: u kunt bepalen met welke [AirPlay-apparaten](airplay-settings-ios.md) (zoals Apple TV) de eindgebruikers van het iOS-apparaat verbinding kunnen maken.

- **Aangepast bericht vergrendelingsscherm**: U kunt een aangepast bericht configureren dat de gebruikers zien op het vergrendelingsscherm van hun iOS-apparaat. Dit bericht vervangt het standaardbericht op het vergrendelingsscherm. Zie [De modus Apparaat verloren activeren op iOS-apparaten](device-lost-mode.md) voor meer informatie

### <a name="restrict-push-notifications-for-ios-apps----723767---"></a>Pushmeldingen voor iOS-apps beperken <!-- 723767 -->
In een Intune-apparaatbeperkingsprofiel kunt u nu de volgende [meldingsinstellingen](app-notification-settings-ios.md) voor iOS-apparaten configureren:

- Meldingen voor een opgegeven app volledig in- of uitschakelen.
- Meldingen voor een opgegeven app in- of uitschakelen in het berichtencentrum.
- Het type waarschuwing opgeven: **Geen**, **Banner** of **Modale waarschuwing**.
- Opgeven of badges zijn toegestaan voor deze app.
- Opgeven of meldingsgeluiden zijn toegestaan.

### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---"></a>iOS-apps configureren voor autonome uitvoering in één-app-modus <!-- 737837 -->
U kunt nu een Intune-apparaatprofiel gebruiken om iOS-apparaten te configureren voor het uitvoeren van opgegeven apps in de [Autonome modus voor enkele toepassing](device-restrictions-ios.md#autonomous-single-app-mode-supervised-only). Wanneer deze modus is geconfigureerd en de app wordt uitgevoerd, wordt het apparaat vergrendeld zodat alleen de betreffende app kan worden uitgevoerd. U kunt bijvoorbeeld een app configureren die de gebruikers een test laat uitvoeren op het apparaat. Wanneer de acties van de app zijn voltooid of u het beleid verwijdert, keert het apparaat terug naar de normale staat.

### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---"></a>Vertrouwde domeinen configureren voor e-mail en browsen op het web op iOS-apparaten <!-- 723765 -->
In een iOS-apparaatbeperkingsprofiel kunt u nu de volgende [domeininstellingen](device-restrictions-ios.md#domains) configureren:

- **Niet-gemarkeerde e-maildomeinen**: e-mailberichten die de gebruiker verzendt of ontvangt die niet overeenkomen met de domeinen die u hier opgeeft, worden gemarkeerd als niet-vertrouwd.

- **Beheerde webdomeinen**: documenten die zijn gedownload via de URL's die u hier opgeeft, worden als beheerd beschouwd (alleen in Safari).  

- **Domeinen voor automatisch invullen van wachtwoorden in Safari**: gebruikers kunnen alleen wachtwoorden opslaan in Safari voor de URL's die overeenkomen met de patronen die u hier opgeeft. Als u deze instelling wilt gebruiken, moet het apparaat in de supervisiemodus staan en niet zijn geconfigureerd voor meerdere gebruikers. (iOS 9.3+)


### <a name="vpp-apps-available-in-ios-company-portal----748782---"></a>VPP-apps beschikbaar in de iOS-bedrijfsportal <!-- 748782 -->
U kunt iOS-apps die zijn gekocht via het volume-aankoopprogramma toewijzen als **Beschikbaar** voor installatie door eindgebruikers. Eindgebruikers hebben een Apple Store-account nodig om de app te installeren.

### <a name="synchronize-ebooks-from-apple-vpp-store----800878---"></a>eBooks synchroniseren vanuit Apple VPP Store <!-- 800878 -->
U kunt nu met Intune [boeken synchroniseren](vpp-apps-ios.md) die u hebt gekocht via het volume-aankoopprogramma van Apple en de boeken toewijzen aan gebruikers.

### <a name="multi-user-management-for-samsung-knox-standard-devices----971988---"></a>Beheer van meerdere gebruikers voor Samsung Knox Standard-apparaten <!-- 971988 -->
Apparaten waarop Samsung Knox Standard wordt uitgevoerd, bieden nu ondersteuning voor [beheer van meerdere gebruikers](android-enroll.md) in Intune. Dit betekent dat eindgebruikers zich kunnen aan- en afmelden bij het apparaat met hun Azure Active Directory-referenties, en dat het apparaat centraal wordt beheerd, ongeacht of het wordt gebruikt of niet.  Wanneer eindgebruikers zich aanmelden, hebben ze toegang tot apps en wordt eventueel aanvullend beleid toegepast. Wanneer ze zich afmelden, worden alle app-gegevens gewist.

### <a name="additional-windows-device-restriction-settings----818566---"></a>Aanvullende Windows 10-apparaatbeperkingsinstellingen <!-- 818566 -->
Er is ondersteuning toegevoegd voor aanvullende [Windows-apparaatbeperkingsinstellingen](device-restrictions-windows-10.md), zoals aanvullende ondersteuning voor Edge, het aanpassen van het vergrendelingsscherm, het aanpassen van het startmenu, het instellen van de zoekfunctie van Windows Spotlight als achtergrondafbeelding en proxy-instellingen.

### <a name="multi-user-support-for-windows-10-creators-update----822547---"></a>Ondersteuning voor meerdere gebruikers van Windows 10-makersupdate <!-- 822547 -->
Er is ondersteuning toegevoegd voor het [beheer van meerdere gebruikers](windows-enroll.md) voor apparaten waarop de Windows 10-makersupdate wordt uitgevoerd en die zijn toegevoegd aan een Azure Active Directory-domein. Dit betekent dat wanneer verschillende standaardgebruikers zich aanmelden op het apparaat met hun Azure AD-referenties, ze de apps en beleidsregels ontvangen die zijn toegewezen aan hun gebruikersnaam. Gebruikers kunnen de bedrijfsportal op dit moment niet gebruiken voor selfservice scenario's zoals het installeren van apps.

### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Fresh Start voor Windows 10-pc's<!-- 1004830 -->
Er is nu een apparaatactie [Nieuwe start](device-fresh-start.md) voor Windows 10-pc's beschikbaar.  Wanneer u deze actie uitvoert, worden alle apps die op de pc zijn geïnstalleerd verwijderd en wordt de pc automatisch bijgewerkt naar de laatste Windows-versie. Hiermee verwijdert u vooraf geïnstalleerde OEM-apps die vaak op nieuwe pc's staan. U kunt configureren of de gebruikersgegevens bewaard blijven wanneer u deze actie uitvoert.

### <a name="additional-windows-10-upgrade-paths----903672---"></a>Aanvullende upgradepaden voor Windows 10 <!-- 903672 -->
U kunt nu een [versie-upgradebeleid maken om apparaten bij te werken](edition-upgrade-configure-windows-10.md) naar de volgende aanvullende Windows 10-edities:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Windows 10-apparaten bulksgewijs inschrijven <!-- 747607 -->
U kunt nu grote aantallen apparaten waarop de Windows 10-makersupdate wordt uitgevoerd toevoegen aan Azure Active Directory en Intune met Windows Configuration Designer (WCD). Als u [bulksgewijze MDM-registratie](windows-bulk-enroll.md) voor uw Azure AD-tenant wilt inschakelen, maakt u een inrichtingspakket waarmee apparaten worden toegevoegd aan uw Azure AD-tenant met Windows Configuration Designer. Vervolgens past u het pakket toe op apparaten die bedrijfseigendom zijn en die u bulksgewijs wilt registreren en beheren. Zodra het pakket is toegepast op de apparaten, worden deze toegevoegd aan Azure AD, ingeschreven bij Intune en zijn ze klaar voor aanmelding door uw Azure AD-gebruikers.  Azure AD-gebruikers zijn standaardgebruikers op deze apparaten en ontvangen toegewezen beleid en de vereiste apps. Scenario's voor de selfserviceportal en de bedrijfsportal worden momenteel niet ondersteund.

### <a name="new-mam-settings-for-pin-and-managed-storage-locations----581122-736644---"></a>Nieuwe MAM-instellingen voor pincode en beheerde opslaglocaties <!-- 581122, 736644 -->
Er zijn nu twee nieuwe app-instellingen beschikbaar voor het beheren van mobiele toepassingen:

- **App-pincode uitschakelen wanneer apparaatpincode wordt beheerd**: deze instelling detecteert of er een apparaatpincode aanwezig is op het ingeschreven apparaat. Als dat het geval is, wordt de app-pincode die wordt geactiveerd door het app-beveiligingsbeleid omzeild. Deze instelling zorgt ervoor dat gebruikers minder vaak een pincode hoeven in te voeren wanneer zij een beheerde mobiele toepassing openen op een ingeschreven apparaat. Deze functie is beschikbaar op Android en iOS.

- **Selecteer naar welke opslagservices bedrijfsgegevens kunnen worden opgeslagen**: hiermee kunt u opgeven welke opslaglocaties mogen worden gebruikt voor het opslaan van bedrijfsgegevens. Gebruikers kunnen alleen opslaan in de geselecteerde opslaglocatieservices, wat inhoudt dat de opslaglocatieservices die niet worden vermeld, zijn geblokkeerd.

  Lijst met ondersteunde opslaglocatieservices:

  - OneDrive
  - Zakelijke SharePoint Online
  - Lokale opslag

### <a name="help-desk-troubleshooting-portal----907448---"></a>Portal voor problemen oplossen van helpdesk<!-- 907448 -->
Met de nieuwe [Portal voor problemen oplossen](help-desk-operators.md) kunnen helpdeskmedewerkers en Intune-beheerders de gebruikers en hun apparaten weergeven, en taken uitvoeren voor het oplossen van technische problemen met Intune.

## <a name="march-2017"></a>Maart 2017

### <a name="support-for-ios-lost-mode---431695--"></a>Ondersteuning voor iOS voor de modus Apparaat verloren<!--431695-->
Voor apparaten met iOS 9.3 en hoger is in Intune ondersteuning toegevoegd voor de **modus Apparaat verloren**. U kunt nu een apparaat vergrendelen om verder gebruik te voorkomen en een bericht en telefoonnummer weergeven op het vergrendelingsscherm van het apparaat.

De eindgebruiker kan het apparaat pas ontgrendeld wanneer een beheerder de modus Apparaat verloren heeft uitgeschakeld. Als de modus Apparaat verloren is ingeschakeld, kunt u de actie **Apparaat zoeken** uitvoeren om de geografische locatie van het apparaat weer te geven op een kaart in de Intune-console.

Het apparaat moet een iOS-apparaat in bedrijfseigendom zijn, dat via DEP is ingeschreven en waarop de supervisiemodus is ingeschakeld.

Zie [Wat is Microsoft Intune-apparaatbeheer?](device-management.md) voor meer informatie.

### <a name="improvements-to-device-actions-report---677150--"></a>Verbeteringen aan het rapport Apparaatacties <!--677150-->
Er zijn verbeteringen aangebracht aan het rapport Apparaatacties voor betere prestaties. Bovendien kunt u het rapport nu filteren op basis van status. U kunt het rapport bijvoorbeeld filteren zodat alleen de apparaatacties worden weergegeven die zijn voltooid.

### <a name="custom-app-categories---748805--"></a>Aangepaste app-categorieën <!--748805-->
U kunt nu categorieën maken, bewerken en toewijzen voor apps die u aan Intune toevoegt. Categorieën kunnen momenteel alleen worden opgegeven in het Engels.
Zie [Een app toevoegen aan Intune](apps-add.md).

### <a name="assign-lob-apps-to-users-with-unenrolled-devices---748823--"></a>LOB-apps toewijzen aan gebruikers met niet-ingeschreven apparaten <!--748823-->
U kunt nu Line-Of-Business-apps uit de store toewijzen aan gebruikers, ongeacht of hun apparaten zijn ingeschreven bij Intune. Als een apparaat van een gebruiker niet is geregistreerd bij Intune, moet deze daarvoor de bedrijfsportalwebsite gebruiken en niet de bedrijfsportal-app.

### <a name="new-compliance-reports---846671--"></a>Nieuwe nalevingsrapporten <!--846671-->
U hebt nu nalevingsrapporten die u informatie bieden over de naleving van apparaten in uw bedrijf. U kunt dan ook snel aan naleving gerelateerde problemen oplossen waar uw gebruikers mee te maken krijgen. U kunt informatie bekijken over

- De algemene nalevingsstatus van apparaten
- De nalevingsstatus voor een specifieke instelling
- De nalevingsstatus voor een specifiek beleid

U kunt deze rapporten ook gebruiken om in te zoomen op een specifiek apparaat, om op die manier te bekijken welke instellingen en beleidsregels van invloed zijn op dat apparaat.

<!--- You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N --->

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Rechtstreekse toegang tot Apple-scenario's voor inschrijving <!--951869-->
Voor Intune-accounts die na januari 2017 zijn gemaakt, heeft Intune rechtstreekse toegang ingeschakeld tot Apple-inschrijvingsscenario's. Hiervoor is de werkstroom voor het inschrijven van apparaten gebruikt in Azure Portal. Voorheen was de Apple-inschrijvingspreview alleen toegankelijk via koppelingen in de Azure-portal. Intune-accounts die vóór januari 2017 zijn gemaakt, moeten eenmalig worden gemigreerd om de functies in Azure beschikbaar te maken. De planning voor de migratie is nog niet aangekondigd, maar de informatie wordt zo snel mogelijk beschikbaar gemaakt. Het wordt aangeraden om een testaccount te maken om de nieuwe ervaring te testen, als u met uw bestaande account geen toegang hebt tot de preview.


## <a name="february-2017"></a>Februari 2017

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Mogelijkheid om de inschrijving van mobiele apparaten te beperken <!--747600, 795782-->
Er zijn in Intune nieuwe inschrijvingsbeperkingen toegevoegd die bepalen welke platforms voor mobiele apparaten kunnen worden ingeschreven. Intune onderscheidt platforms voor mobiele apparaten als iOS, macOS, Android, Windows en Windows Mobile.

* Een beperking voor de registratie van mobiele apparaten, betekent niet dat de PC-clientregistratie ook is beperkt.  
* Alleen voor iOS en Android geldt er een extra optie voor het blokkeren van de inschrijving van apparaten die in persoonlijk eigendom zijn.

Intune markeert alle nieuwe apparaten als persoonlijk, tenzij de IT-beheerder actie onderneemt om deze te markeren als bedrijfseigen, zoals uitgelegd in [dit artikel](https://docs.microsoft.com/intune-classic/deploy-use/manage-corporate-owned-devices).

### <a name="view-all-actions-on-managed-devices---677150--"></a>Alle acties voor beheerde apparaten weergeven <!--677150-->
Er is een nieuw rapport __Apparaatacties__, waarin wordt weergegeven wie externe acties, zoals het herstellen van fabrieksinstellingen, op apparaten heeft uitgevoerd. In dit rapport wordt ook de status van de actie getoond. Zie [Wat is apparaatbeheer?](device-management.md).

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Niet-beheerde apparaten hebben toegang tot toegewezen apps <!--664691-->
Als onderdeel van de ontwerpwijzigingen op de bedrijfsportalwebsite kunnen iOS- en Android-gebruikers op hun niet-beheerde apparaten apps installeren die aan hen zijn toegewezen als 'beschikbaar zonder inschrijving'. Gebruikers kunnen zich met behulp van hun Intune-referenties aanmelden bij de bedrijfsportalwebsite en de lijst met aan hen toegewezen apps bekijken. De app-pakketten van de 'beschikbaar zonder inschrijving'-apps kunnen worden gedownload via de bedrijfsportalwebsite. Deze wijziging is niet van toepassing op apps die pas na inschrijving kunnen worden geïnstalleerd, omdat gebruikers wordt gevraagd hun apparaat in te schrijven als zij deze apps willen installeren.

### <a name="custom-app-categories---748805--"></a>Aangepaste app-categorieën <!--748805-->
U kunt nu categorieën maken, bewerken en toewijzen voor apps die u aan Intune toevoegt. Categorieën kunnen momenteel alleen worden opgegeven in het Engels.
Zie [Een app toevoegen aan Intune](apps-add.md).

### <a name="display-device-categories---814654--"></a>Apparaatcategorieën weergeven <!--814654-->
U kunt nu de apparaatcategorie als kolom in de lijst met apparaten weergeven. U kunt ook de categorie uit de sectie met eigenschappen van de apparaateigenschappenblade bewerken. Zie [Een app toevoegen aan Intune](apps-add.md).

### <a name="configure-windows-update-for-business-settings---776716--"></a>Instellingen voor Windows Update voor bedrijven configureren.<!--776716-->

Windows as a Service is de nieuwe manier voor het aanbieden van updates voor Windows 10. Vanaf Windows 10 bevatten alle Upgrades van onderdelen en Kwaliteitsupdates de inhoud van alle voorgaande updates. Dit houdt in dat, als u de nieuwste update hebt geïnstalleerd, u zeker weet dat uw Windows 10-apparaten volledig zijn bijgewerkt. In tegenstelling tot eerdere versies van Windows, moet u nu de volledige update installeren in plaats van een onderdeel van een update.

Met Windows Update voor bedrijven kunt u updatebeheer vereenvoudigen, zodat u geen afzonderlijke updates voor groepen apparaten hoeft goed te keuren. U kunt nog steeds risico's in uw omgeving beheren door een strategie voor update-implementatie te configureren. Windows Update zorgt ervoor dat updates op tijd worden geïnstalleerd. Microsoft Intune biedt de mogelijkheid update-instellingen op apparaten te configureren en biedt u de mogelijkheid de installatie van updates uit te stellen. Intune slaat de updates niet op, maar alleen de beleidstoewijzing voor de update. Apparaten hebben voor de updates rechtstreeks toegang tot Windows Update. Voor het configureren en beheren van **Windows 10-updateringen** wordt Intune gebruikt. Een updatering bevat een aantal instellingen waarin is geconfigureerd wanneer en hoe Windows 10-updates worden geïnstalleerd. Zie [Instellingen voor Windows Update voor bedrijven configureren](windows-update-for-business-configure.md) voor meer informatie.
