---
title: Wat is er nieuw in Microsoft Intune?
titleSuffix: Intune on Azure
description: Ontdekken wat er nieuw is in Intune Azure Portal
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 08/10/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f915c805b20e88c661ad52e280a31054bbebce02
ms.sourcegitcommit: 2ed8d1c39d4b3e3282111f1d758afb3a50f19f8f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2017
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
  ### Intune apps
-->   

## <a name="week-of-july-31-2017"></a>Week van 31 juli 2017

### <a name="device-enrollment"></a>Apparaatinschrijving  

#### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version------1333256--1245463----"></a>Registratie van Android- en iOS-apparaten beperken op basis van de versie van het besturingssysteem  <!--- 1333256,  1245463 --->
Intune biedt nu ondersteuning voor het beperken van registraties van iOS- en Android-apparaten op basis van het versienummer van het besturingssysteem. Bij **Apparaattypebeperking** kan de IT-beheerder een platformconfiguratie instellen met een minimum- en maximumversie van het besturingssysteem, zodat alleen apparaten met versies in dit bereik kunnen worden geregistreerd. De versies van het Android-besturingssysteem moeten worden opgegeven als Major.Minor.Build.Rev, waarbij Minor, Build en Rev optioneel zijn. iOS-versies moeten worden opgegeven als Primair.Secundair.Build, waarbij Minor en Build optioneel zijn. Meer informatie over [beperkingen voor het registreren van apparaten](enrollment-restrictions-set.md).

>[!NOTE]
>Registratie via het inschrijvingsprogramma van Apple of Apple Configurator wordt niet beperkt.

#### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment------1333272--1333275-1245709----"></a>Apparaatregistratie beperken van Android-, iOS- en macOS-apparaten die privé-eigendom zijn  <!--- 1333272,  1333275, 1245709 --->
Intune kan de registratie van persoonlijke apparaten beperken door IMEI-nummers van bedrijfsapparaten op te nemen in een lijst met toegestane apparaten. De functionaliteit van Intune is nu uitgebreid naar iOS, Android en macOS via het gebruik van de serienummers van apparaten. Door serienummers te uploaden naar Intune, kunt u apparaten vooraf markeren als bedrijfseigendom. Aan de hand van inschrijvingsbeperkingen kunt u de registratie blokkeren van apparaten die privé-eigendom (BYOD) zijn. Op deze manier maakt u beleid waardoor alleen apparaten kunnen worden ingeschreven die bedrijfseigendom zijn. Meer informatie over [beperkingen voor het registreren van apparaten](enrollment-restrictions-set.md).

Als u serienummers wilt importeren in, gaat u naar **Apparaatinschrijving** > **Bedrijfsapparaat-id's** en klikt u op **Toevoegen**. Upload vervolgens een CSV-bestand met deze specificaties (geen header, twee kolommen, één voor de serienummers en één voor gegevens zoals IMEI-nummers).  Als u de registratie van apparaten in privé-eigendom wilt beperken, gaat u naar **Apparaatinschrijving** > **Inschrijvingsbeperkingen**. Selecteer **Standaard** onder **Apparaattypebeperking** en selecteer vervolgens **Platformconfiguraties**. Selecteer **Toestaan** of **Blokkeren** voor iOS-, Android- en macOS-apparaten die privé-eigendom zijn. 


### <a name="device-management"></a>Apparaatbeheer   

#### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>Nieuwe apparaatactie om apparaten geforceerd te synchroniseren met Intune <!-- 711369 -->
In deze versie is een nieuwe apparaatactie toegevoegd die ervoor zorgt dat het geselecteerde apparaat direct wordt ingecheckt bij Intune. Wanneer een apparaat wordt ingecheckt, worden direct eventuele openstaande acties of toegewezen beleidsregels toegepast.  Met deze actie kunt u toegewezen beleid meteen controleren en in het geval van problemen direct aanpassen, zonder dat u hoeft te wachten op de volgende geplande check-in.
Zie [Apparaat synchroniseren](device-sync.md) voor meer informatie

#### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>Nieuwste software-update geforceerd installeren op iOS-apparaten die onder supervisie staan<!-- 777100 -->
Er is een nieuw beleid beschikbaar in de werkruimte Software-updates waarmee u kunt afdwingen dat automatisch de nieuwste software-update wordt geïnstalleerd op onder supervisie staande iOS-apparaten. Zie [Updatebeleid voor iOS configureren](/intune/software-updates-ios) voor meer informatie


#### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner-----954651-1172027---"></a>Check Point SandBlast Mobile - nieuwe Mobile Threat Defense-partner  <!-- 954651, 1172027 -->
U kunt de toegang van mobiele apparaten tot bedrijfsresources beheren door middel van voorwaardelijke toegang op basis van een risicoanalyse die wordt uitgevoerd door Check Point SandBlast Mobile, een oplossing voor de beveiliging tegen bedreigingen op mobiele apparaten die met Microsoft Intune is geïntegreerd.

##### <a name="how-integration-with-intune-works"></a>Hoe werkt de integratie met Intune?
Risico's worden beoordeeld op basis van telemetriegegevens die zijn verzameld op apparaten met Check Point SandBlast Mobile. U kunt het EMS-beleid voor voorwaardelijke toegang configureren op basis van de risicoanalyse van Check Point SandBlast Mobile die wordt ingeschakeld via het Intune-nalevingsbeleid voor apparaten. U kunt apparaten die niet compatibel zijn op basis van gedetecteerde bedreigingen al dan niet toegang bieden tot bedrijfsresources.


### <a name="app-management"></a>Appbeheer

#### <a name="deploy-an-app-as-available-in-the-microsoft-store-for-business----748101---"></a>Een app als beschikbaar implementeren in Microsoft Store voor Bedrijven <!-- 748101 -->
Met deze versie kunnen beheerders de Microsoft Store voor Bedrijven nu toewijzen als beschikbaar. Wanneer Microsoft Store voor Bedrijven is ingesteld als beschikbaar, kunnen eindgebruikers de app installeren via de bedrijfsportal-app of -website zonder dat ze worden omgeleid naar de Microsoft Store.


### <a name="intune-apps"></a>Intune-apps  

#### <a name="ui-updates-to-the-company-portal-website---1313244-part-1--"></a>Updates aan de gebruikersinterface van de bedrijfsportalwebsite <!--1313244 part 1-->
Er zijn een aantal updates aan de gebruikersinterface van de [bedrijfsportalwebsite](https://portal.manage.microsoft.com) uitgevoerd om de gebruikerservaring te verbeteren.

- __Verbeteringen aan app-tegels__: app-pictogrammen worden nu weergegeven met een achtergrond die automatisch wordt gegenereerd op basis van de overheersende kleur van het pictogram (mits detecteerbaar). Indien van toepassing wordt de grijze rand die voorheen zichtbaar was op app-tegels, vervangen door deze achtergrond.

    In de volgende versie worden er waar mogelijk grote pictogrammen weergegeven op de bedrijfsportalwebsite. IT-beheerders wordt aangeraden apps te publiceren met pictogrammen met een hoge resolutie en een minimumgrootte van 120 x 120 pixels. 

- __Wijzigingen in de navigatie__: items op de navigatiebalk zijn verplaatst naar het hamburgermenu linksboven. De pagina Categorieën is verwijderd. Gebruikers kunnen nu tijdens het browsen inhoud filteren op categorie.

- __Updates voor aanbevolen apps__: Er is een speciale pagina aan de site toegevoegd waar gebruikers door apps kunnen bladeren die door u zijn aanbevolen. Ook zijn er enkele correcties aan de gebruikersinterface aangebracht in de sectie Aanbevolen op de startpagina.

#### <a name="ibooks-support-for-the-company-portal-website---1231841--"></a>Ondersteuning van iBooks voor de bedrijfsportalwebsite <!--1231841-->
Er is een speciale pagina toegevoegd aan de bedrijfsportalwebsite waarmee gebruikers iBooks kunnen zoeken en downloaden. 

### <a name="reporting"></a>Rapporten

#### <a name="intune-data-warehouse-public-preview"></a>Intune-datawarehouse (openbare preview-versie)

In het Intune-datawarehouse worden dagelijks gegevens verzameld om een historisch overzicht te bieden van uw tenant. U kunt hebt toegang tot de gegevens via een Power BI-bestand (PBIX), een OData-koppeling die compatibel is met tal van analysehulpprogramma's of via interactie met de REST API. Zie [Het Intune-datawarehouse gebruiken](reports-nav-create-intune-reports.md) voor meer informatie.


## <a name="week-of-july-23rd-2017"></a>Week van 23 juli 2017

### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Lichte en donkere modi beschikbaar voor de Intune-bedrijfsportal-app voor Windows 10 <!---676547--->
Eindgebruikers kunnen de kleurenmodus voor de Intune-bedrijfsportal-app voor Windows 10 aanpassen. Dit kan in de sectie Instellingen van de Intune-bedrijfsportal-app. De wijziging wordt van kracht nadat de gebruiker de app opnieuw heeft gestart. Voor Windows 10 versie 1607 en hoger wordt voor de app-modus standaard de systeeminstelling gebruikt. Voor Windows 10 versie 1511 en lager wordt voor de app-modus standaard de lichte modus gebruikt.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10----807046--"></a>Eindgebruikers kunnen hun apparaatgroep taggen in de Intune-bedrijfsportal-app voor Windows 10 <!---807046-->
Eindgebruikers kunnen voortaan aangeven bij welke groep hun apparaat hoort door deze rechtstreeks vanuit de bedrijfsportal-app voor Windows 10 te taggen.




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

### <a name="end-of-support-for-ios-80----1164477---"></a>Einde van ondersteuning voor iOS 8.0 <!---1164477--->
Beheerde apps en de Intune-bedrijfsportal-app voor iOS vereisen iOS 9.0 en hoger voor toegang tot bedrijfsresources. Apparaten die niet voor september zijn bijgewerkt, hebben geen toegang meer tot de bedrijfsportal of beheerde apps. 

### <a name="ui-updates-to-the-company-portal-website---1313244-part-2--"></a>Updates aan de gebruikersinterface van de bedrijfsportalwebsite <!--1313244 part 2-->
__Updates voor aanbevolen apps__  
Er is een speciale pagina aan de site toegevoegd waar gebruikers door apps kunnen bladeren die door u zijn aanbevolen. Ook zijn er enkele correcties aan de gebruikersinterface aangebracht in de sectie Aanbevolen op de startpagina. U kunt deze wijzigingen zien op de pagina [met wijzigingen aan de app-gebruikersinterface](whats-new-app-ui.md).


### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Einde van ondersteuning voor Android 4.3 en lager <!---1171127, 1326920 --->
Beheerde apps en de Intune-bedrijfsportal-app voor Android vereisen Android 4.4 en hoger voor toegang tot bedrijfsresources. Apparaten die niet voor begin van oktober zijn bijgewerkt, hebben geen toegang meer tot de bedrijfsportal of beheerde apps. Vanaf december worden alle ingeschreven apparaten verplicht buiten gebruik gesteld, waardoor bedrijfsresources niet meer toegankelijk zijn. Als u beleid voor app-beveiliging zonder MDM gebruikt, krijgen apps geen updates meer en neemt de gebruikservaring na verloop van tijd steeds verder af.


### <a name="platform-support-reminder-windows-phone-81-mainstream-support-ended-july-11-2017"></a>Herinnering voor platformondersteuning: de algemene ondersteuning voor Windows Phone 8.1 is gestopt op 11 juli 2017
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
