---
title: Wat is er nieuw in Microsoft Intune?
titlesuffix: Azure portal
description: Ontdekken wat er nieuw is in Intune Azure Portal
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 11/2/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a683fcf96b09a19a84f429d8ccfab6788983d6d2
ms.sourcegitcommit: 0f877251e6adf4e45b918cc8dc9193626727f2d9
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2017
---
# <a name="whats-new-in-microsoft-intune"></a>Wat is er nieuw in Microsoft Intune?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ontdek elke week wat er nieuw is in Microsoft Intune. U vindt hier ook informatie over [toekomstige wijzigingen](#whats-coming), [belangrijke kennisgevingen](#notices) betreffende de service en informatie over [oudere releases](whats-new-archive.md).

> [!Note]
> Veel van deze functies worden uiteindelijk ondersteund voor hybride implementaties met Configuration Manager. Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
  ### Role-based access control
  ### Intune apps
  ### Monitor and troubleshoot

-->   

## <a name="week-of-october-30-2017"></a>Week van 30 oktober 2017

### <a name="ios-and-android-line-of-business-app-version-number-is-visible----1380712---"></a>Het versienummer van de line-of-business-app voor iOS en Android is zichtbaar <!-- 1380712 -->

In Apps in Intune wordt nu het versienummer voor iOS- en Android-line-of-business-apps weergegeven. Het nummer wordt in de Azure Portal in de app-lijst en in de blade App-overzicht getoond. Eindgebruikers kunnen het app-nummer in de bedrijfsportal-app en in de webportal zien.

#### <a name="full-version-number"></a>Volledig versienummer

Het volledige versienummer duidt een specifieke release van de app aan. Het nummer wordt weergegeven als _Versie_(_Build_). Bijvoorbeeld 2.2(2.2.17560800)

Het volledige versienummer bevat twee onderdelen:

 - **Versie**  
   Het versienummer is het door mensen leesbare releasenummer van de app. Dit wordt door eindgebruikers gebruikt om de verschillende releases van de app aan te duiden.

 - **Buildnummer**  
    Het buildnummer is een intern nummer dat voor de detectie van apps en het beheer van apps via een programma kan worden gebruikt. Het buildnummer verwijst naar een iteratie van de app die refereert aan wijzigingen in de code.

Meer informatie over versienummers en het ontwikkelen van line-of-business-apps in [Aan de slag met Microsoft Intune App SDK](app-sdk-get-started.md#line-of-business-app-version-numbers).

### <a name="device-and-app-management-integration----677972---"></a>Integratie van apparaat- en appbeheer <!-- 677972 -->   
Nu Mobile Device Management (MDM) en Mobile Application Management (MAM) van Intune beide toegankelijk zijn vanuit de Azure-portal, is Intune begonnen met het integreren van de IT-beheerervaring omtrent app- en apparaatbeheer. Deze wijzigingen zijn bedoeld om uw apparaat- en appbeheer te vereenvoudigen.

Meer informatie over de aangekondigde MDM- en MAM-wijzigingen staat in de [blog van het Intune-ondersteuningsteam](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/).

### <a name="new-enrollment-alerts-for-apple-devices----1471790---"></a>Nieuwe inschrijvingswaarschuwingen voor Apple-apparaten<!---1471790--->
De overzichtspagina voor de inschrijving toont nuttige waarschuwingen voor IT-beheerders met betrekking tot beheer van apparaten van Apple. Waarschuwingen worden weergegeven op de overzichtspagina wanneer het Apple MDM push-certificaat verloopt of al is verlopen, wanneer het token Device Enrollment Program verloopt of al is verlopen en wanneer er zich niet-toegewezen apparaten in het Device Enrollment Program bevinden.

### <a name="support-token-replacement-for-app-configuration-without-device-enrollment----1080364---"></a>Ondersteuning voor token-vervanging voor de configuratie van de app zonder apparaatinschrijving <!-- 1080364 -->

U kunt tokens gebruiken voor dynamische waarden in app-configuraties voor apps op apparaten die niet zijn ingeschreven. Zie voor meer informatie [App-configuratiebeleidsregels toevoegen voor beheerde apps zonder apparaatinschrijving](app-configuration-policies-managed-app.md).

## <a name="week-of-october-23-2017"></a>Week van 23 oktober 2017

### <a name="intune-apps"></a>Intune-apps

#### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios---1029830--"></a>Ondersteuning voor op certificaten gebaseerde verificatie op de bedrijfsportal voor iOS <!--1029830-->
We hebben ondersteuning voor op certificaten gebaseerde verificatie toegevoegd in de bedrijfsportal-app voor iOS. Gebruikers met deze verificatie voeren hun gebruikersnaam in en tikken vervolgens op de koppeling 'Aanmelden met een certificaat'. Dit wordt al ondersteund in de bedrijfsportal-app voor Android en Windows. Meer informatie staat op de pagina [Aanmelden bij de bedrijfsportal-app](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal).

## <a name="week-of-october-16-2017"></a>Week van 16 oktober 2017

### <a name="device-enrollment"></a>Apparaatinschrijving
#### <a name="windows-autopilot-deployment-program-support-in-microsoft-intune-----747617----"></a>Ondersteuning voor het Windows AutoPilot Deployment-programma in Microsoft Intune <!-- 747617  -->
U kunt nu Microsoft Intune gebruiken met het Windows AutoPilot Deployment-programma om uw gebruikers de mogelijkheid te geven hun bedrijfsapparaten in te richten zonder de tussenkomst van de IT-afdeling. U kunt de Out-of-the-box-ervaring (OOBE) aanpassen en gebruikers begeleiden bij het toevoegen van hun apparaat aan Azure AD en inschrijven bij Intune. Samen nemen Microsoft Intune en Windows AutoPilot de noodzaak weg voor het implementeren, onderhouden en beheren van installatiekopieën van besturingssystemen. Zie [Windows-apparaten inschrijven met het Windows AutoPilot Deployment-programma](https://docs.microsoft.com/intune/enrollment-autopilot) voor meer informatie.

#### <a name="quick-start-for-device-enrollment-----1425655---"></a>Snel starten met apparaatinschrijving <!-- 1425655 --> 
Snel starten is nu beschikbaar in **Apparaatinschrijving** en bevat een tabel met naslagonderwerpen voor het beheren van platformen en configureren van het inschrijvingsproces. Dankzij een korte beschrijving van elk item en koppelingen naar documentatie met stapsgewijze instructies kunt u sneller aan de slag.

#### <a name="device-categorization----1427491---"></a>Categorisatie van apparaten <!-- 1427491 -->
In de grafiek met platformen van ingeschreven apparaten op de blade **Apparaten > Overzicht** zijn apparaten geordend op platform, zoals Android, iOS, macOS, Windows en Windows Mobile.  Apparaten met een ander besturingssysteem zijn gegroepeerd in de categorie ‘Overig’.  Dit omvat apparaten van Blackberry, Nokia en andere fabrikanten.  

Als u wilt weten wat dit voor gevolgen heeft voor de apparaten in uw tenant, kiest u **Beheren > Alle apparaten** en gebruikt u vervolgens **Filter** om de inhoud van het veld **Besturingssysteem** te beperken.

### <a name="device-management"></a>Apparaatbeheer
#### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium - nieuwe Mobile Threat Defense-partner   <!-- 954681 -->  
U kunt de toegang van mobiele apparaten tot bedrijfsresources beheren door middel van voorwaardelijke toegang op basis van een risicoanalyse die wordt uitgevoerd door Zimperium, een oplossing voor de beveiliging tegen bedreigingen op mobiele apparaten die met Microsoft Intune is geïntegreerd.

##### <a name="how-integration-with-intune-works"></a>Hoe werkt de integratie met Intune
Risico's worden beoordeeld op basis van telemetrische gegevens die zijn verzameld op apparaten met door Zimperium. U kunt het EMS-beleid voor voorwaardelijke toegang configureren op basis van de Zimperium-risicoanalyse die via het Intune-nalevingsbeleid voor apparaten wordt ingeschakeld. U kunt met dit beleid de toegang tot bedrijfsresources voor niet-compatibele apparaten toestaan of blokkeren op basis van de gedetecteerde bedreigingen.

#### <a name="new-settings-for-windows-10-device-restriction-profile------978575-1308849---"></a>Nieuwe instellingen voor het beperkingsprofiel voor Windows 10-apparaten  <!--- 978575, 1308849, -->  
Er worden nieuwe instellingen toegevoegd aan het apparaatbeperkingsprofiel voor Windows 10 in de categorie Windows Defender SmartScreen.

Zie [Apparaatbeperkingsinstellingen voor Windows 10-apparaten en hoger]( device-restrictions-windows-10.md) voor meer informatie.

#### <a name="remote-support-for-windows-and-windows-mobile-devices------1070473---"></a>Externe ondersteuning voor Windows- en Windows Mobile-apparaten  <!-- 1070473 -->  
Intune kan de afzonderlijk verkrijgbare [TeamViewer](https://www.teamviewer.com)-software gebruiken zodat u uw gebruikers met Windows- en Windows Mobile-apparaten hulp op afstand kunt bieden.

#### <a name="scan-devices-with-windows-defender----1280988--1280990-----"></a>Apparaten scannen met Windows Defender <!-- 1280988  1280990   -->
U kunt nu een **Snelle scan** en **Volledige scan** uitvoeren en **Handtekeningen bijwerken** met Windows Defender Antivirus op beheerde Windows 10-apparaten. Kies op de overzichtsblade van het apparaat de actie die u op het apparaat wilt uitvoeren. U wordt gevraagd om de actie te bevestigen voordat de opdracht naar het apparaat wordt verzonden. 

**Snelle scan**: een snelle scan scant locaties waar malware zich registreert, zoals registercodes en bekende opstartmappen in Windows. Een snelle scan duurt gemiddeld vijf minuten. In combinatie met de instelling **Realtimebeveiliging altijd ingeschakeld**, die bestanden scant wanneer ze worden geopend en gesloten en wanneer een gebruiker naar een map gaat, helpt een snelle scan om bescherming te bieden tegen malware die zich mogelijk in het systeem of de kernel bevindt. Gebruikers zien de scanresultaten op hun apparaten wanneer hij is voltooid. 

**Volledige scan**: een volledige scan kan handig zijn om vast te stellen of er inactieve componenten zijn die een diepgaandere opschoning vereisen op apparaten die met een malwarebedreiging te maken hebben gekregen. De scan is handig voor het uitvoeren van scans op aanvraag. Het uitvoeren van volledige scans kan een uur duren. Gebruikers zien de scanresultaten op hun apparaat wanneer de scan is voltooid. 

**Handtekeningen bijwerken**: de opdracht Handtekeningen bijwerken werkt de malwaredefinities en-handtekeningen in Windows Defender Antivirus bij. Dit helpt ervoor te zorgen dat Windows Defender Antivirus malware effectief detecteert. Deze functie is alleen voor Windows 10-apparaten en zolang er een internetverbinding is. 

#### <a name="the-enabledisable-button-is-removed-from-the-intune-certificate-authority-page-of-the-intune-azure-portal-----1400455---"></a>De knop Inschakelen/Uitschakelen is verwijderd van de pagina Intune-certificaatinstantie van de Intune Azure-portal <!-- 1400455 -->
 We verwijderen een extra stap voor het instellen van de certificaatconnector in Intune. Op dit moment downloadt u de certificaatconnector en schakelt u die in de Intune-console in. Als u de connector echter uitschakelt in de Intune-console, blijft de connector toch certificaten uitgeven.

##### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Met ingang van oktober is de knop Inschakelen/Uitschakelen niet langer aanwezig op de pagina Certificaatinstantie in de Azure-portal. De functionaliteit van de connector blijft hetzelfde. Certificaten worden nog steeds geïmplementeerd naar apparaten die zijn ingeschreven in Intune. U kunt de certificaatconnector nog steeds downloaden en installeren. Als u niet langer certificaten wilt uitgeven, verwijdert u de certificaatconnector in plaats van dat u die uitschakelt.

##### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
Als de certificaatconnector momenteel is uitgeschakeld, moet u die verwijderen.



### <a name="device-configuration"></a>Apparaatconfiguratie
#### <a name="new-settings-for-windows-10-team-device-restriction-profile-------1308838---"></a>Nieuwe instellingen voor het beperkingsprofiel voor Windows 10 Team-apparaten <!--- 1308838 -->
In deze versie hebben we veel nieuwe instellingen toegevoegd aan het beperkingsprofiel voor Windows 10 Team-apparaten, om u te helpen bij het beheren van Surface Hub-apparaten.

Raadpleeg [Intune-apparaatbeperkingen voor Windows 10 Team](device-restrictions-windows-10-teams.md) voor meer informatie over dit profiel.

#### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time-----1333292---"></a>Voorkomen dat gebruikers van Android-apparaten de datum en tijd van hun apparaat wijzigen  <!-- 1333292 -->
U kunt een [aangepast beleid voor Android-apparaten](custom-settings-android.md) gebruiken om te voorkomen dat gebruikers van Android-apparaten de datum en tijd van het apparaat wijzigen.

Configureer hiervoor een aangepast Android-beleid met de instelling URI ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange Stel dit in op **TRUE** en wijs het vervolgens toe aan de vereiste groepen.

#### <a name="bitlocker-device-configuration----1397398---"></a>Configuratie van BitLocker-apparaat <!-- 1397398 -->
**Windows-versleuteling > Basisinstellingen** bevat een nieuwe instelling **Waarschuwing voor een andere schijfversleuteling** waarmee u de [waarschuwing](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption) voor versleuteling van een andere schijf die mogelijk op het apparaat van de gebruiker wordt gebruikt kunt uitschakelen.  De waarschuwing vereist dat eindgebruikers toestemming geven voordat ze BitLocker op het apparaat configureren en blokkeert de configuratie van Bitlocker totdat de eindgebruiker bevestigend heeft gereageerd.  De nieuwe instelling schakelt de waarschuwing voor de eindgebruiker uit.


### <a name="app-management"></a>Appbeheer
#### <a name="volume-purchase-program-for-business-apps-will-now-sync-to-your-intune-tenant----800882---"></a>Het volume-aankoopprogramma voor zakelijke apps synchroniseert nu met uw Intune-tenant <!-- 800882 -->  
Externe ontwikkelaars kunnen privé apps distribueren naar geautoriseerde VPP (volume-aankoopprogramma) for Business-leden die zijn opgegeven in iTunes Connect. Deze VPP for Business-leden kunnen zich aanmelden bij de Volume Purchase Program App Store en hun apps kopen.

Met ingang van deze release worden VPP for Business-apps die door de gebruiker zijn gekocht, gesynchroniseerd met hun Intune-tenant.

#### <a name="select-apple-country-store-to-sync-vpp-apps-----1332311---"></a>Specifieke Apple Store selecteren om VPP-apps te synchroniseren  <!-- 1332311 -->  
U kunt de store in het land voor het volumeaankoopprogramma (VPP) configureren als u uw VPP-token uploadt. Intune synchroniseert VPP-apps voor alle landinstellingen uit de opgegeven store uit het land waar de VPP geldt.

> [!NOTE]  
> Op dit moment synchroniseert Intune alleen VPP-apps uit de store van het VPP-land dat overeenkomt met de Intune-landinstelling waarin de Intune-tenant werd gemaakt.




### <a name="intune-apps"></a>Intune-apps
#### <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>Kopiëren en plakken tussen werkprofielen en persoonlijke profielen blokkeren in Android for Work <!-- 1098994 -->
Door deze release kunt u het werkprofiel voor Android for Work zo configureren dat kopiëren en plakken tussen zakelijke en persoonlijke apps wordt geblokkeerd. U kunt deze nieuwe instelling vinden in het profiel **Apparaatbeperkingen** voor het **Android for Work**-platform onder **Werkprofielinstellingen**.

#### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>iOS-apps maken die zijn beperkt tot specifieke regionale Apple App Stores <!-- 1281692 -->
U kunt de landinstelling voor een land opgeven wanneer u een beheerde app voor de Apple App Store maakt.

> [!Note]  
> Op dit moment kunt u alleen beheerde apps voor de Apple App Store maken die aanwezig zijn in de store voor de VS.

####  <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>Gelicentieerde iOS-apps voor VPP-gebruikers en -apparaten bijwerken  <!-- 1305564 -->  
U kunt het VPP-token voor iOS zo configureren dat alle apps die voor dat token zijn gekocht worden bijgewerkt via de Intune-service. Intune detecteert updates voor de VPP-app in de app store en stuurt ze automatisch naar het apparaat als dit incheckt.

Zie [iOS-apps beheren die zijn aangeschaft via een volumeaankoopprogramma met Microsoft Intune] (/intune/vpp-apps-ios) voor meer informatie over het instellen van een VPP-token en inschakelen van automatische updates.



### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen
#### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Verzameling voor koppelingsentiteit voor apparaten van gebruikers toegevoegd aan het Intune-datawarehouse-gegevensmodel <!-- 1187917 -->
U kunt rapporten en gegevensvisualisaties maken met behulp van de informatie over de gebruikersapparaatkoppelingen; deze koppelen verzamelingen over gebruikers en apparaten. Het gegevensmodel is toegankelijk via het Power BI-bestand (PBIX) dat wordt opgehaald op de datawarehouse-pagina in Intune, via het OData-eindpunt of door een aangepaste client te ontwikkelen.

#### <a name="review-policy-compliance-for-windows-10-update-rings----1067886---"></a>Naleving van het beleid voor Windows 10-update-ringen controleren <!-- 1067886 -->
U kunt een beleidsrapport voor uw Windows 10-update-ringen bekijken via Software-updates > Implementatiestatus per update-ring. Het beleidsrapport bevat de implementatiestatus voor de update-ringen die u hebt geconfigureerd. 

#### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Nieuw rapport met iOS-apparaten met oudere iOS-versies   <!-- 1352223 -->
Het rapport **Out-of-date iOS Devices** (Verouderde iOS-apparaten) is beschikbaar in de werkruimte **Software-updates**. Het rapport bevat een lijst met gecontroleerde iOS-apparaten waarop een iOS-updatebeleid van toepassing is geweest en waarvoor updates beschikbaar zijn. Voor elk apparaat kunt u bekijken waarom het apparaat niet automatisch is bijgewerkt. 

#### <a name="view-app-protection-policy-assignments-for-troubleshooting-----1475003---"></a>Beleidstoewijzingen voor app-beveiliging bekijken om problemen op te lossen <!--  1475003 -->
In deze toekomstige release wordt de optie **App-beveiligingsbeleid** toegevoegd aan de vervolgkeuzelijst **Toewijzingen** op de blad voor probleemoplossing. U kunt nu beleid voor app-beveiliging selecteren om de beleidsregels voor app-beveiliging te zien die aan de geselecteerde gebruikers zijn toegewezen.



## <a name="week-of-october-2-2017"></a>Week van 2 oktober 2017

### <a name="intune-apps"></a>Intune-apps
#### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a>Verbeteringen in de werkstroom voor apparaatinstellingen in de bedrijfsportal <!--1490692-->
We hebben de werkstroom voor apparaatinstellingen in de bedrijfsportal-app voor Android verbeterd. De taal is gebruiksvriendelijker en specifiek voor uw bedrijf. Daarnaast hebben we waar mogelijk schermen gecombineerd. U kunt deze zien op de pagina [Nieuw in de app-gebruikersinterface](whats-new-app-ui.md#week-of-october-2-2017).

#### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices---1484985--"></a>Verbeterde richtlijnen voor het aanvragen van toegang tot contactpersonen op Android-apparaten <!--1484985-->

Voor de bedrijfsportal-app voor Android moet de eindgebruiker vaak de machtiging Contactpersonen accepteren. Als een eindgebruiker deze toegang weigert, ziet deze nu een melding in de app waarin wordt aangegeven dat deze moet worden verleend voor voorwaardelijke toegang. 

#### <a name="secure-startup-remediation-for-android---1490712--"></a>Beveiligd opstartherstel voor Android<!--1490712-->

Eindgebruikers met Android-apparaten kunnen tikken op de reden van niet-naleving in de bedrijfsportal-app. Indien mogelijk worden ze hiermee rechtstreeks naar de juiste locatie geleid in de instellingen-app om het probleem te verhelpen. 

#### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-oreo---1475932--"></a>Aanvullende pushmeldingen voor eindgebruikers op de bedrijfsportal-app voor Android Oreo <!--1475932-->

Eindgebruikers ontvangen aanvullende meldingen wanneer de bedrijfsportal-app voor Android Oreo achtergrondtaken uitvoert, zoals het ophalen van beleid van de Intune-service. Dit biedt gebruikers meer transparantie over wanneer de bedrijfsportal-app beheertaken uitvoert op hun apparaat. Dit maakt deel uit van de algehele [optimalisatie van de gebruikersinterface van de bedrijfsportal](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) voor de bedrijfsportal-app voor Android Oreo. 

Er zijn nog meer optimalisaties voor nieuwe UI-elementen die in Android Oreo zijn ingeschakeld.  Eindgebruikers ontvangen aanvullende meldingen wanneer de bedrijfsportal achtergrondtaken uitvoert, zoals het ophalen van beleid van de Intune-service.  Dit biedt eindgebruikers meer transparantie over wanneer met de bedrijfsportal-app beheertaken worden uitgevoerd op het apparaat.

#### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>Nieuw gedrag voor de bedrijfsportal-app voor Android met werkprofielen <!---1485783--->

Als u een Android voor Work-apparaat met een werkprofiel inschrijft, voert de bedrijfsportal-app in het werkprofiel beheertaken uit op het apparaat. 

De bedrijfsportal-app voor Android wordt niet langer gebruikt, tenzij u een app met MAM-functionaliteit in het persoonlijke profiel gebruikt. Intune zal automatisch de persoonlijke bedrijfsportal-app verbergen om uw ervaring met het werkprofiel te verbeteren nadat de inschrijving van het werkprofiel is geslaagd.

De bedrijfsportal-app voor Android kan op elk gewenst moment in het persoonlijke profiel worden ingeschakeld door naar [Bedrijfsportal te zoeken in de Play Store](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) en op **Inschakelen** te tikken.

#### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>Bedrijfsportal voor Windows 8.1 en Windows Phone 8.1 wordt verplaatst naar onderhoudsmodus <!--1428681-->

Vanaf oktober 2017 worden de bedrijfsportal-apps voor Windows 8.1 en Windows Phone 8.1 verplaatst naar de onderhoudsmodus. Dit betekent dat de apps en bestaande scenario’s, zoals inschrijving en naleving, op deze platforms ondersteund blijven worden. De apps blijven beschikbaar om te worden gedownload via bestaande release-kanalen, zoals de Microsoft Store. 

In de onderhoudsmodus worden er alleen kritieke beveiligingsupdates voor deze apps uitgebracht. Er worden geen extra updates of functies voor deze apps uitgebracht. Wanneer u nieuwe functies wilt, raden we u aan om uw apparaten bij te werken naar Windows 10 of Windows 10 Mobile. 


### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="block-unsupported-samsung-knox-device-enrollment------1490695----"></a>Registratie van niet-ondersteunde Samsung Knox-apparaten blokkeren <!--- 1490695 --->

Via de bedrijfsportal-app worden alleen ondersteunde Samsung Knox-apparaten geregistreerd. Om KNOX activeringsfouten te voorkomen waardoor de MDM-registratie onmogelijk wordt, wordt de apparaatregistratie alleen uitgevoerd als het apparaat wordt weergegeven in de [lijst met apparaten die is gepubliceerd door Samsung](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Bepaalde modelnummers van Samsung-apparaten bieden ondersteuning voor KNOX, andere niet. Controleer de KNOX-compatibiliteit bij de verkoper van uw apparaat voordat u een apparaat koopt en implementeert. U vindt de volledige lijst met gecontroleerde apparaten in de [beleidsinstellingen voor Android en Samsung KNOX Standard](/intune/supported-devices-browsers.md#intune-supported-devices).

#### <a name="end-of-support-for-android-43-and-lower----1171126-1326920----"></a>Einde van ondersteuning voor Android 4.3 en lager <!---1171126, 1326920 --->
Beheerde apps en de Intune-bedrijfsportal-app voor Android vereisen Android 4.4 en hoger voor toegang tot bedrijfsresources. Vanaf december worden alle ingeschreven apparaten verplicht buiten gebruik gesteld, waardoor bedrijfsresources niet meer toegankelijk zijn. Als u beleid voor app-beveiliging zonder MDM gebruikt, krijgen apps geen updates meer en neemt de gebruikservaring na verloop van tijd steeds verder af.

#### <a name="inform-end-users-what-device-information-can-be-seen-on-enrolled-devices---1165314--"></a>Eindgebruikers informeren over welke apparaatgegevens worden weergegeven op geregistreerde apparaten <!--1165314-->
Aan het scherm voor apparaatgegevens in alle bedrijfsportal-apps wordt de optie **Eigendomstype** toegevoegd. Hierdoor kunnen gebruikers meer over privacy te weten komen rechtstreeks via het artikel [Welke informatie kan uw bedrijf zien?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune) Dit zal binnenkort worden geïmplementeerd in alle bedrijfsportal-apps. Voor iOS hebben we dit aangekondigd in [september](https://docs.microsoft.com/intune/whats-new#week-of-september-11-2017).


## <a name="week-of-september-25-2017"></a>Week van 25 september 2017

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="intune-supports-ios-11---1428975--"></a>Intune biedt ondersteuning voor iOS 11 <!--1428975-->
Intune biedt ondersteuning voor iOS 11. Dit werd eerder aangekondigd in de [blog Intune Support](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/).

#### <a name="end-of-support-for-ios-80----1164477---"></a>Einde van ondersteuning voor iOS 8.0 <!---1164477--->
Beheerde apps en de Intune-bedrijfsportal-app voor iOS vereisen iOS 9.0 en hoger voor toegang tot bedrijfsresources. Apparaten die niet voor september zijn bijgewerkt, hebben geen toegang meer tot de bedrijfsportal of beheerde apps. 

### <a name="intune-apps"></a>Intune-apps

#### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Actie voor vernieuwen toegevoegd aan de bedrijfsportal-app voor Windows 10 <!--1132468-->
Met de bedrijfsportal-app voor Windows 10 kunnen gebruikers de gegevens in de app vernieuwen door deze op te halen voor vernieuwing of door op pc’s op F5 te drukken.



## <a name="notices"></a>Mededelingen

### <a name="new-path-for-managed-devices-in-graph-api----1586728---"></a>Nieuw pad voor beheerde apparaten in Graph API <!-- 1586728 -->
We wijzigen we het pad dat wordt gebruikt voor toegang tot beheerde apparaten in de bètaversie van de Graph API. 

| | |
|--|--|
| Huidig pad |  https://graph.microsoft.com/beta/managedDevices |
| Nieuw pad | https://graph.microsoft.com/beta/deviceManagement/managedDevices |

Beide paden zullen werken gedurende de maand oktober. Na de servicerelease van oktober zal alleen het nieuwe pad werken.  Als u de Graph API gebruikt voor toegang tot beheerde apparaten, moet u uw scripts en toepassingen bijwerken en verifiëren met het nieuwe pad. Bekijk het maandelijkse [Graph API-wijzigingslogboek](https://developer.microsoft.com/graph/docs/concepts/changelog) voor aanvullende wijzigingen.


### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Rechtstreekse toegang tot Apple-scenario's voor inschrijving <!--951869-->
Voor Intune-accounts die na januari 2017 zijn gemaakt, heeft Intune rechtstreekse toegang ingeschakeld tot Apple-inschrijvingsscenario's. Hiervoor is de werkstroom voor het inschrijven van apparaten gebruikt in Azure Portal. Voorheen was de Apple-inschrijvingspreview alleen toegankelijk via koppelingen in de klassieke Intune-portal. Intune-accounts die vóór januari 2017 zijn gemaakt, moeten eenmalig worden gemigreerd om de functies in Azure beschikbaar te maken. De planning voor de migratie is nog niet aangekondigd, maar de informatie wordt zo snel mogelijk beschikbaar gemaakt. Het wordt aangeraden om een testaccount te maken om de nieuwe ervaring te testen, als u met uw bestaande account geen toegang hebt tot Azure Portal.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Beheerdersrollen die worden vervangen in Azure Portal
De bestaande MAM-beheerdersrollen (Mobile Application Management), namelijk Inzender, Eigenaar en Alleen-lezen, die in de klassieke Intune-portal (Silverlight) worden gebruikt, worden vervangen door een volledig nieuw op rollen gebaseerd toegangsbeheer in Intune Azure Portal. Wanneer u naar Azure Portal bent gemigreerd, moet u uw beheerders opnieuw toewijzen aan deze nieuwe beheerdersrollen. Zie [Op rollen gebaseerd toegangsbeheer voor Microsoft Intune](/intune/role-based-access-control) voor meer informatie over op rollen gebaseerd toegangsbeheer en de nieuwe rollen.



## <a name="whats-coming"></a>Binnenkort

### <a name="changes-in-support-for-the-intune-ios-company-portal-app-----1164474----"></a>Wijzigingen in de ondersteuning van de Intune-bedrijfsportal-app voor iOS  <!-- 1164474  -->
Binnen afzienbare tijd zal er een nieuwe versie van de Microsoft Intune-bedrijfsportal-app voor iOS uitkomen die alleen nog werkt met apparaten met iOS 9.0 of hoger. De versie van de bedrijfsportal die ondersteuning biedt voor iOS 8 zal nog maar voor zeer korte tijd beschikbaar zijn. Als u echter ook iOS-apps met MAM-functionaliteit gebruikt, is iOS 9.0 en hoger vereist. Het is dus belangrijk om te controleren of uw eindgebruikers zijn bijgewerkt naar de nieuwste versie van het besturingssysteem. 

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Hoewel er nog geen specifieke datums bekend zijn, melden we dit nu al zodat u genoeg tijd hebt om de update te plannen. Zorg ervoor dat uw gebruikers een update uitvoeren naar iOS 9 of hoger. Op het moment dat de nieuwe versie van de Intune-bedrijfsportal-app uitkomt, moeten uw eindgebruikers de bedrijfsportal-app bijwerken.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
Vertel uw gebruikers dat ze een update moeten uitvoeren naar iOS 9.0 of hoger om optimaal gebruik te kunnen maken van nieuwe Intune-functies.  Vertel uw gebruikers dat ze de nieuwe versie van de bedrijfsportal moeten installeren om toegang te krijgen tot de nieuwe functies van de portal.

Ga naar de Intune-portal in de Azure-portal en kies Apparaten > Alle apparaten. Filter op iOS-versie om apparaten te zien met een oudere versie dan iOS 9.


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple vereist updates voor Application Transport Security <!--748318-->
Apple heeft aangekondigd dat specifieke vereisten gaan gelden voor Application Transport Security (ATS). ATS wordt gebruikt om betere beveiliging af te dwingen voor alle app-communicatie die verloopt via HTTPS. Deze wijziging heeft gevolgen voor Intune-klanten die de bedrijfsportal-app gebruiken op iOS.

Een versie van de bedrijfsportal-app is beschikbaar gemaakt voor iOS via het Apple TestFlight-programma waarmee naleving van de nieuwe ATS-vereisten wordt afgedwongen. Als u dit wilt proberen zodat u uw ATS-compatibiliteit kunt testen, stuurt u een e-mail naar <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app"> CompanyPortalBeta@microsoft.com </a> met uw voornaam, achternaam, e-mailadres en bedrijfsnaam. Bekijk ons [Intune-ondersteuningsblog](https://aka.ms/compportalats) voor meer informatie.

## <a name="see-also"></a>Zie tevens
* [Microsoft Intune-blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Roadmap voor cloudplatform](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Wat is er nieuw in de gebruikersinterface van de bedrijfsportal?](whats-new-app-ui.md)
* [Wat was er in de vorige maanden nieuw](whats-new-archive.md)
