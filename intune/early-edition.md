---
title: Vroege editie
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 09/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 31c3d3750aadbe8d302713f081f01f7c51d8ce96
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/09/2017
---
# <a name="the-early-edition-for-microsoft-intune---september-2017"></a>De vroege editie voor Microsoft Intune - september 2017

De **vroege editie** bevat een lijst met functies die worden toegevoegd aan toekomstige releases van Microsoft Intune. Deze informatie wordt in beperkte mate verstrekt en kan worden gewijzigd. Deel deze informatie niet buiten uw bedrijf. Sommige functies die hier worden vermeld, zullen mogelijk niet beschikbaar zijn op de sluitingsdatum en worden mogelijk beschikbaar gesteld in een latere release. Andere functies worden getest in een proefversie, zodat we zeker weten dat ze in gebruik kunnen worden genomen. Als u vragen of opmerkingen hebt, kunt contact opnemen met uw contactpersoon voor de Microsoft-productgroep.

Deze pagina wordt regelmatig bijgewerkt. Controleer op andere updates.

> [!Note]
>De volgende wijzigingen worden momenteel ontwikkeld voor Intune. Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--

## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices

-->



## <a name="intune-in-the-azure-portal"></a>Intune in Azure Portal


### <a name="google-play-protect-support-on-android----908720----"></a>Ondersteuning van Google Play Protect op Android <!-- 908720  -->  
Google introduceert tegelijkertijd met Android Oreo een reeks beveiligingsfuncties met de naam Google Play Protect waarmee gebruikers en organisaties beveiligde apps en beveiligde Android-installatiekopieën kunnen uitvoeren. Intune zal de functies van Google Play Protect, inclusief SafetyNet voor externe verklaringen, ondersteunen.  Beheerders kunnen eisen voor een nalevingsbeleid instellen die vereisen dat Google Play Protect wordt geconfigureerd en in orde is. De instelling **SafetyNet-apparaatverklaring** vereist dat het apparaat verbinding maakt met een service van Google om te controleren of het apparaat in orde is en er niet mee is geknoeid. Beheerders kunnen tevens een configuratieprofielinstelling voor Android for Work instellen om te vereisen dat geïnstalleerde apps worden geverifieerd met behulp van Google Play-services.  Voorwaardelijke toegang kan de toegang van gebruikers tot bedrijfsbronnen blokkeren als een apparaat niet aan de eisen van Google Play Protect voldoet. 

### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time-----1333292---"></a>Voorkomen dat gebruikers van Android-apparaten de datum en tijd van hun apparaat wijzigen  <!-- 1333292 -->
U kunt een [aangepast beleid voor Android-apparaten](custom-settings-android.md) gebruiken om te voorkomen dat gebruikers van Android-apparaten de datum en tijd van het apparaat wijzigen.
Configureer hiervoor een aangepast Android-beleid met de instelling URI ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange Stel dit in op **TRUE** en wijs het vervolgens toe aan de vereiste groepen.

### <a name="view-app-protection-policy-assignments-for-troubleshooting-----1475003---"></a>Beleidstoewijzingen voor app-beveiliging bekijken om problemen op te lossen <!--  1475003 -->
In deze toekomstige release wordt de optie **App-beveiligingsbeleid** toegevoegd aan de vervolgkeuzelijst **Toewijzingen** op de blad voor probleemoplossing. U kunt nu beleid voor app-beveiliging selecteren om de beleidsregels voor app-beveiliging te zien die aan de geselecteerde gebruikers zijn toegewezen.

### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>iOS-apps maken die zijn beperkt tot specifieke regionale Apple App Stores <!-- 1281692 -->
U kunt de landinstelling voor een land opgeven wanneer u een beheerde app voor de Apple App Store maakt.

> [!NOTE]  
> Op dit moment kunt u alleen beheerde apps voor de Apple App Store maken die aanwezig zijn in de store voor de VS.

### <a name="select-apple-country-store-to-sync-vpp-apps-----1332311---"></a>Specifieke Apple Store selecteren om VPP-apps te synchroniseren  <!-- 1332311 -->  
U kunt de store in het land voor het volumeaankoopprogramma (VPP) configureren als u uw VPP-token uploadt. Intune synchroniseert VPP-apps voor alle landinstellingen uit de opgegeven store uit het land waar de VPP geldt.

> [!NOTE]  
> Op dit moment synchroniseert Intune alleen VPP-apps uit de store van het VPP-land dat overeenkomt met de Intune-landinstelling waarin de Intune-tenant werd gemaakt.

###  <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>Gelicentieerde iOS-apps voor VPP-gebruikers en -apparaten bijwerken  <!-- 1305564 -->  
U kunt het VPP-token voor iOS zo configureren dat alle apps die voor dat token zijn gekocht worden bijgewerkt via de Intune-service. Intune detecteert updates voor de VPP-app in de app store en stuurt ze automatisch naar het apparaat als dit incheckt.

### <a name="ios-11-support----1428975---"></a>Ondersteuning voor iOS 11 <!-- 1428975 -->
Intune zal iOS 11 ondersteunen als dit door Apple wordt uitgebracht.

### <a name="new-settings-for-windows-10-team-device-restriction-profile------1308838----"></a>Nieuwe instellingen voor het beperkingsprofiel voor Windows 10 Team-apparaten <!--- 1308838  -->
In deze versie voegen we veel nieuwe instellingen toe aan het beperkingsprofiel voor Windows 10 Team-apparaten om u te helpen bij het beheren van Surface Hub-apparaten.
Raadpleeg [Intune-apparaatbeperkingen voor Windows 10 Team](device-restrictions-windows-10-teams.md) voor meer informatie over dit profiel.

### <a name="support-for-windows-10-edition-upgrade-policy------903672-1119689---"></a>Ondersteuning voor het editie-upgradebeleid voor Windows 10   <!-- 903672, 1119689 -->  
U kunt een editie-upgradebeleid voor Windows 10 maken dat Windows 10-apparaten upgradet naar Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education en Windows 10 Professional Education N. Raadpleeg [Editie-upgrades voor Windows 10 configureren in Intune](edition-upgrade-configure-windows-10.md) voor meer informatie over editie-upgrades voor Windows 10.

### <a name="review-policy-compliance-for-windows-10-update-rings----1352223---"></a>Naleving van het beleid voor Windows 10-update-ringen controleren <!-- 1352223 -->  
U kunt een beleidsrapport voor uw Windows 10-update-ringen bekijken via **Software-updates** > **Implementatiestatus per update-ring**. Het beleidsrapport bevat de implementatiestatus voor de update-ringen die u hebt geconfigureerd. 

### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy----677129---"></a>Windows 10-bedrijfsportal-app toegevoegd het toelatingsbeleid van Windows Information Protection <!-- 677129 -->  
De Windows 10-bedrijfsportal-app wordt bijgewerkt zodat deze Windows Information Protection (WIP) ondersteunt. De app kan worden toegevoegd aan het toelatingsbeleid van WIP. Door deze wijziging hoeft de app niet langer te worden toegevoegd aan de lijst **Uitgezonderd**. 

### <a name="remote-support-for-windows-and-windows-mobile-devices-----1070473---"></a>Externe ondersteuning voor Windows- en Windows Mobile-apparaten  <!-- 1070473 -->    
Intune kan de afzonderlijk verkrijgbare [TeamViewer](https://www.teamviewer.com)-software gebruiken zodat u uw gebruikers met Windows- en Windows Mobile-apparaten hulp op afstand kunt bieden.

### <a name="scan-devices-with-windows-defender----1280988--1280990-----"></a>Apparaten scannen met Windows Defender <!-- 1280988  1280990   -->
U kunt een **Snelle scan** en **Volledige scan** uitvoeren en **Handtekeningen bijwerken** met Windows Defender Antivirus op beheerde Windows 10-apparaten. Kies op de overzichtsblade van het apparaat de actie die u op het apparaat wilt uitvoeren. U wordt gevraagd om de actie te bevestigen voordat de opdracht naar het apparaat wordt verzonden. 

**Snelle scan**: een snelle scan scant locaties waar malware zich registreert, zoals registercodes en bekende opstartmappen in Windows. Een snelle scan duurt gemiddeld vijf minuten. In combinatie met de instelling **Realtimebeveiliging altijd ingeschakeld**, die bestanden scant wanneer ze worden geopend en gesloten en wanneer een gebruiker naar een map gaat, helpt een snelle scan om bescherming te bieden tegen malware die zich mogelijk in het systeem of de kernel bevindt. Gebruikers zien de scanresultaten op hun apparaten wanneer hij is voltooid. 

**Volledige scan**: een volledige scan kan handig zijn om vast te stellen of er inactieve componenten zijn die een diepgaandere opschoning vereisen op apparaten die met een malwarebedreiging te maken hebben gekregen. De scan is handig voor het uitvoeren van scans op aanvraag. Het uitvoeren van volledige scans kan een uur duren. Gebruikers zien de scanresultaten op hun apparaat wanneer de scan is voltooid. 

**Handtekeningen bijwerken**: de opdracht Handtekeningen bijwerken werkt de malwaredefinities en-handtekeningen in Windows Defender Antivirus bij. Dit helpt ervoor te zorgen dat Windows Defender Antivirus malware effectief detecteert. Deze functie is alleen voor Windows 10-apparaten en zolang er een internetverbinding is. 

### <a name="bitlocker-device-configuration----1397398---"></a>Configuratie van BitLocker-apparaat <!-- 1397398 -->  
**Windows-versleuteling > Basisinstellingen** bevat een nieuwe instelling **Waarschuwing voor een andere schijfversleuteling** waarmee u de [waarschuwing](https://docs.microsoft.com/en-us/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption) voor versleuteling van een andere schijf die mogelijk op het apparaat van de gebruiker wordt gebruikt kunt uitschakelen.  De waarschuwing vereist dat eindgebruikers toestemming geven voordat ze BitLocker op het apparaat configureren en blokkeert de configuratie van Bitlocker totdat de eindgebruiker bevestigend heeft gereageerd.  De nieuwe instelling schakelt de waarschuwing voor de eindgebruiker uit.

### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>Bedrijfsportal voor Windows 8.1 en Windows Phone 8.1 wordt verplaatst naar onderhoudsmodus <!--1428681-->
Vanaf oktober 2017 worden de bedrijfsportal-apps voor Windows 8.1 en Windows Phone 8.1 verplaatst naar de onderhoudsmodus. Dit betekent dat de apps en bestaande scenario’s, zoals inschrijving en naleving, op deze platforms ondersteund blijven worden. De apps blijven beschikbaar om te worden gedownload via bestaande release-kanalen, zoals de Microsoft Store. 

In de onderhoudsmodus worden er alleen kritieke beveiligingsupdates voor deze apps uitgebracht. Er worden geen extra updates of functies voor deze apps uitgebracht. Wanneer u nieuwe functies wilt, raden we u aan om uw apparaten bij te werken naar Windows 10 of Windows 10 Mobile. 

###  <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>Kopiëren en plakken tussen werkprofielen en persoonlijke profielen blokkeren in Android for Work <!-- 1098994 -->   
Door deze release kunt u het werkprofiel voor Android for Work zo configureren dat kopiëren en plakken tussen zakelijke en persoonlijke apps wordt geblokkeerd. U kunt deze nieuwe instelling vinden in het profiel **Apparaatbeperkingen** voor het **Android for Work**-platform onder **Werkprofielinstellingen**.

### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>Nieuw gedrag voor de bedrijfsportal-app voor Android met werkprofielen <!---1485783--->
Als u een Android voor Work-apparaat met een werkprofiel inschrijft, voert de bedrijfsportal-app in het werkprofiel beheertaken uit op het apparaat. De bedrijfsportal-app voor Android wordt niet langer gebruikt, tenzij u een app met MAM-functionaliteit in het persoonlijke profiel gebruikt. Intune zal automatisch de persoonlijke bedrijfsportal-app verbergen om uw ervaring met het werkprofiel te verbeteren nadat de inschrijving van het werkprofiel is geslaagd.

De bedrijfsportal-app voor Android kan op elk gewenst moment in het persoonlijke profiel worden ingeschakeld door naar [Bedrijfsportal te zoeken in de Play Store](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) en op **Inschakelen** te tikken.

### <a name="intune-mam--outlook-for-android-add-ins-----1450688---"></a>Intune MAM- en Outlook voor Android-invoegtoepassingen  <!-- 1450688 -->
Het Office-team zal binnen een paar weken invoegtoepassingen voor Outlook voor Android aankondigen. Deze functieset met invoegtoepassingen bestaat al in Outlook voor Windows, iOS, web en Mac. Omdat invoegtoepassingen worden beheerd via Exchange, kunnen gebruikers gegevens en berichten kopiëren en delen tussen Outlook en niet-beheerde invoegtoepassingen, tenzij de toegang tot invoegtoepassingen door uw Exchange-beheerder wordt uitgeschakeld. 

Werk samen met uw Exchange-beheerder om te zorgen dat uw MAM-beleid voor het beveiligen van gegevens van toepassing is op invoegtoepassingen wanneer u de machtigingen voor toegang van gebruikers tot invoegtoepassingen beheert.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
U hoeft niet verder te lezen als uw Exchange-beleid al is ingesteld om het zijdelings gebruiken of installeren van invoegtoepassingen te voorkomen. Uw MAM-beleid zal worden toegepast zoals u dat verwacht. Als u echter beleid in MAM hebt ingesteld om knip-, kopieer- en plakbewerkingen in Outlook voor Android te beperken en uw beleid voor invoegtoepassingen niet in Exchange hebt ingesteld, dient u te weten dat gebruikers standaard invoegtoepassingen voor Outlook kunnen installeren. Deze invoegtoepassingen hebben toegang tot de berichttekst, het onderwerp en andere eigenschappen van berichten. U kunt de mogelijkheid van eindgebruikers om invoegtoepassingen te installeren uitschakelen door uw Exchange-beheerder de rollen 'Mijn Marketplace-apps' en 'Mijn aangepaste apps' te laten verwijderen. Raadpleeg de koppeling voor extra informatie die hieronder wordt gedeeld voor meer informatie.

Houd er rekening mee dat een wijziging in de instelling in Exchange ook wordt toegepast op Outlook voor Windows, iOS, web, Mac en mobiele apparaten. 

#### <a name="what-do-i-need-to-do"></a>Wat moet ik doen?
Controleer vandaag uw Exchange-beleid. Informeer uw IT- en helpdeskmedewerkers. Neem contact op met ons ondersteuningsteam met een specifieke vragen of opmerkingen. 

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Verzameling voor koppelingsentiteit voor apparaten van gebruikers toegevoegd aan het Intune-datawarehouse-gegevensmodel <!-- 1187917 -->
U kunt rapporten en gegevensvisualisaties maken met behulp van de informatie over de koppeling van apparaten van gebruikers; deze koppeling verzamelingen over gebruikers en apparaten. Het gegevensmodel is toegankelijk via het Power BI-bestand (PBIX) dat wordt opgehaald op de datawarehouse-pagina in Intune, via het OData-eindpunt of door een aangepaste client te ontwikkelen.


<!-- the following are present prior to 1709 -->

### <a name="actions-for-non-compliance----730266--"></a>Acties voor niet-naleving  <!--730266-->     
*Acties voor niet-naleving* is een nieuwe functie van nalevingsbeleid waarmee u actie kunt ondernemen voor apparaten die niet meer compatibel zijn. U kunt een of meer acties opgeven, samen met de tijdsduur waarbinnen deze acties moeten plaatsvinden. U kunt bijvoorbeeld gebruikers van niet-compatibele apparaten een melding via e-mail sturen onmiddellijk nadat de compatibiliteit van de apparaten is opgeheven, of u kunt de toegang van niet-compatibele apparaten tot bedrijfsbronnen blokkeren na een respijtperiode van 3 dagen via voorwaardelijke toegang.

### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Nieuw rapport met iOS-apparaten met oudere iOS-versies   <!-- 1352223 -->
Het rapport **Out-of-date iOS Devices** (Verouderde iOS-apparaten) is beschikbaar in de werkruimte **Software-updates**. Het rapport bevat een lijst met gecontroleerde iOS-apparaten waarop een iOS-updatebeleid van toepassing is geweest en waarvoor updates beschikbaar zijn. Voor elk apparaat kunt u bekijken waarom het apparaat niet automatisch is bijgewerkt. 

### <a name="new-settings-for-windows-10-device-restriction-profile"></a>Nieuwe instellingen voor het apparaatbeperkingsprofiel voor Windows 10
<!--- 978575, 1308849, -->
Er worden nieuwe instellingen toegevoegd aan het apparaatbeperkingsprofiel voor Windows 10 in de categorie Windows Defender SmartScreen.

Zie [Apparaatbeperkingsinstellingen voor Windows 10-apparaten en hoger]( device-restrictions-windows-10.md) voor meer informatie.

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
### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Actie voor vernieuwen toegevoegd aan de bedrijfsportal-app voor Windows 10 <!--1132468-->
De bedrijfsportal-app voor Windows 10 stelt gebruikers in staat om de gegevens in de app te vernieuwen door te trekken om te vernieuwen of door op pc’s op F5 te drukken.


### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Apps die met of zonder inschrijving beschikbaar zijn, kunnen nu worden geïnstalleerd zonder dat er om inschrijving wordt gevraagd. <!-- 1334712 -->
Bedrijfs-apps die met of zonder inschrijving beschikbaar zijn gemaakt in de bedrijfsportal-app voor Android kunnen worden geïnstalleerd zonder dat er om inschrijving wordt gevraagd.

### <a name="ios-company-portal-display-large-icons----1454593---"></a>Grote pictogrammen in bedrijfsportal voor iOS <!-- 1454593 -->
We werken aan een oplossing voor een bekend probleem met de manier waarop de iOS-bedrijfsportal pictogrammen weergeeft in de app-tegel. Als u app-pictogrammen van minimaal 120x120 pixels uploadt, worden ze nu op de [bedrijfsportalwebsite] (https://portal.manage.microsoft.com) en in de pagina’s van de bedrijfsportal-apps weergegeven op volledige grootte van de app-tegel.

### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android------1396349---"></a>Gemakkelijker te begrijpen formulering voor de bedrijfsportal-app voor Android   <!---1396349--->    
Het inschrijvingsproces voor de bedrijfsportal-app voor Android is vereenvoudigd met nieuwe tekst om het eindgebruikers gemakkelijker te maken om zich in te schrijven. 


<!-- the following are present prior to 1709 -->


### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Ondersteuning van Intune Managed Browser voor iOS en Android <!---1374196--->
Vanaf oktober 2017 ondersteunt de app Intune Managed Browser voor Android alleen nog apparaten waarop Android 4.4 en hoger wordt uitgevoerd. De app Intune Managed Browser voor iOS ondersteunt alleen apparaten met iOS 9.0 en hoger. Oudere versies van Android en iOS kunnen Managed Browser nog steeds gebruiken, maar er kunnen geen nieuwe versies van de app op worden geïnstalleerd en kan er dus geen gebruik worden gemaakt van alle mogelijkheden van de app. U wordt aangeraden deze apparaten bij te werken tot een ondersteunde versie van het besturingssysteem.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Eindgebruikers zonder inschrijving toegang geven tot de Intune-bedrijfsportal-app voor Android <!---1169910--->  
Eindgebruikers hoeven hun apparaat binnenkort niet meer in te schrijven om toegang te krijgen tot de Intune-bedrijfsportal-app voor Android. Eindgebruikers in organisaties die gebruikmaken van beleid voor app-beveiliging zien bij het openen van de Intune-bedrijfsportal-app geen instructie meer dat ze hun apparaat moeten registreren. Bovendien kunnen eindgebruikers apps installeren via de bedrijfsportal zonder dat ze hun apparaat hoeven te registreren. 

### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Verbeterd foutbericht als een gebruiker het maximum aantal apparaten bereikt dat mag worden ingeschreven <!-- 1270370 -->
In plaats van een algemeen foutbericht krijgen eindgebruikers een gebruikersvriendelijk foutbericht te zien waarop een actie kan worden uitgevoerd: 'U hebt het maximum aantal apparaten ingeschreven dat door de IT-beheerder is toegestaan. Verwijder een ingeschreven apparaat of vraag assistentie van uw IT-beheerder.'

### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>Eindgebruikers informeren welke apparaatgegevens voor iOS kunnen worden gezien <!--739894-->
Aan het scherm voor apparaatgegevens in de bedrijfsportal-app voor iOS wordt de optie **Eigendomstype ** toegevoegd. Hierdoor kunnen gebruikers meer over privacy te weten komen vanaf deze pagina in de documenten voor Intune-eindgebruikers. Deze informatie is ook te vinden op het scherm Info.

### <a name="apps-details-pages-display-new-information-for-android-devices---1287476--"></a>Op de pagina's met gegevens over de apps wordt nieuwe informatie weergegeven voor Android-apparaten <!--1287476-->
In de bedrijfsportal-app voor Android worden op de pagina met gegevens over de apps de app-categorieën weergegeven die de IT-beheerder voor die app heeft gedefinieerd.

### <a name="intune-mobile-application-management-mam-dialog-boxes-now-have-a-modern-interface----1199015---"></a>Intune Mobile Application Management (MAM)-dialoogvensters hebben nu een moderne interface <!-- 1199015 -->
Intune Mobile Application Management (MAM)-dialoogvensters zijn bijgewerkt en hebben nu een modern uiterlijk. De dialoogvensters werken op dezelfde manier als de vorige.

De op moderne Android-apparaten weergegeven dialoogvensters met fouten of meldingen hebben voortaan een bijgewerkt uiterlijk.



## <a name="notices"></a>Mededelingen
### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple vereist updates voor Application Transport Security <!--748318-->   
Apple heeft aangekondigd dat vanaf het voorjaar van 2017 specifieke vereisten gaan gelden voor Application Transport Security (ATS). ATS wordt gebruikt om betere beveiliging af te dwingen voor alle app-communicatie die verloopt via HTTPS. Deze wijziging heeft gevolgen voor Intune-klanten die de bedrijfsportal-app gebruiken op iOS. Bekijk ons [Intune-ondersteuningsblog](https://aka.ms/compportalats) voor meer informatie.

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Geplande wijziging: Intune verandert in de Intune Partner Portal-ervaring<!-- 1050016 -->
De pagina Intune Partner wordt verwijderd uit manage.microsoft.com die begint met de service-update halverwege mei 2017.  

Als u een partnerbeheerder bent, kunt u niet langer weergeven of actie ondernemen namens uw klanten vanaf de pagina Intune Partner. U moet zich aanmelden bij een van de twee andere partnerportals bij Microsoft.

U kunt zich bij het [Microsoft Partner Center](https://partnercenter.microsoft.com/) en het [Microsoft Office 365-partnerbeheercentrum](https://portal.office.com/) aanmelden bij de klantaccounts die u beheert. Gebruik in de toekomst als partner een van deze sites voor het beheren van uw klanten.



### <a name="see-also"></a>Zie tevens
Zie [Wat is er nieuw in Microsoft Intune?](whats-new.md) voor meer informatie over recente ontwikkelingen.
