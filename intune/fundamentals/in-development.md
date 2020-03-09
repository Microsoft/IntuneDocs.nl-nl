---
title: In ontwikkeling - Microsoft Intune
titleSuffix: ''
description: Microsoft Intune-functies in ontwikkeling
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/03/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.assetid: 25b3c26e-cf4e-4152-8306-bf4be4af2ad1
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: e099537bce6327e9a8991bc42f406e4abd3dfd2e
ms.sourcegitcommit: 6608dc70d01376e0cd90aa620a2fe01337f6a2f1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/04/2020
ms.locfileid: "78260228"
---
# <a name="in-development-for-microsoft-intune---march-2020"></a>In ontwikkeling voor Microsoft Intune: maart 2020

Als hulp bij uw gereedheid en planning worden op deze pagina updates voor en functies van de Intune-gebruikersinterface vermeld die in ontwikkeling zijn, maar nog niet zijn uitgebracht. Naast de informatie op deze pagina geldt het volgende: 

- Als we verwachten dat u actie moet ondernemen vóór een wijziging, publiceren we een aanvullend bericht in het Office-berichtencentrum.
- Als een functie in productie gaat, of het nu gaat om een preview of algemene beschikbaarheid, wordt de functiebeschrijving verplaatst van deze pagina naar [Nieuwe functies](whats-new.md).
- Deze pagina en de pagina [Nieuwe functies](whats-new.md) worden regelmatig bijgewerkt. Controleer op andere updates.
- Raadpleeg de [Microsoft 365-roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) voor strategische producten en tijdlijnen.

> [!NOTE]
> Deze pagina bevat onze huidige verwachtingen over Intune-mogelijkheden in een toekomstige release. Datums en afzonderlijke functies kunnen worden gewijzigd. Op deze pagina worden niet alle functies in ontwikkeling beschreven.

**RSS-feed**: U ziet wanneer deze pagina wordt bijgewerkt door de volgende URL in uw feedlezer te kopiëren en plakken: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->

<!-- Common categories:  
## App management
## Device configuration
## Device enrollment
## Device management
## Intune apps
## Monitor and troubleshoot
## Role-based access control
## Security

-->
 
<!-- ***********************************************-->
## <a name="app-management"></a>Appbeheer

### <a name="retarget-web-clips-to-microsoft-edge-on-iosipados-devices---5455276---"></a>Microsoft Edge als nieuw doel opgeven voor webclips op iOS-/iPadOS-apparaten<!-- 5455276 -->
Webclips, die fungeren als vastgemaakte web-apps op iOS-/iPadOS-apparaten, moeten worden bijgewerkt. Zojuist geïmplementeerde webclips worden in Microsoft Edge geopend in plaats van in de Intune Managed Browser als openen in een beveiligde browser wordt vereist. U moet een nieuw doel opgeven voor reeds bestaande webclips om ervoor te zorgen dat deze worden geopend in Microsoft Edge in plaats van de Managed Browser.

### <a name="macos-and-ios-company-portal-updates---5779439-5780234----"></a>Updates voor de macOS- en iOS-bedrijfsportal<!-- 5779439, 5780234  -->
Het deelvenster Profiel van de macOS- en iOS-bedrijfsportal worden bijgewerkt met de knop Afmelden. Daarnaast bevat deze update verbeteringen voor de gebruikersinterface in het deelvenster Profiel in de macOS-bedrijfsportal. Raadpleeg [De bedrijfsportal-app van Microsoft Intune configureren](~/apps/company-portal-app.md) voor meer informatie over de bedrijfsportal-app.

### <a name="updates-to-branding-and-customization-pane---5236032---"></a>Updates voor het deelvenster Huisstijl en aanpassing<!-- 5236032 -->
Het Intune-deelvenster dat momenteel Huisstijl en aanpassing heet, wordt aangepast met enkele verbeteringen, zoals:

- De naam van het deelvenster wordt gewijzigd in **Aanpassing**.
- De rangschikking en het ontwerp van de instellingen wordt verbeterd.
- De tekst en knopinfo voor instellingen wordt verbeterd.

Ga voor deze instelling in Intune naar het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) en selecteer **Tenantbeheer** > **Aanpassing**. Zie [De bedrijfsportal-app van Microsoft Intune configureren](~/apps/company-portal-app.md) voor informatie over bestaande aanpassingen.

### <a name="configure-the-ios-microsoft-azure-ad-sso-app-extension---567534----"></a>De SSO-app-extensie van Microsoft Azure AD voor iOS configureren<!-- 567534  -->
Het Microsoft Azure AD-team ontwikkelt een SSO-app-extensie (eenmalige aanmelding) voor omleiden zodat gebruikers van iOS en iPadOS 13.0 en hoger naadloos toegang kunnen krijgen tot Microsoft-apps en -websites met eenmalige aanmelding. Zodra de AAD SSO-app-extensie wordt uitgebracht, kunt u in slechts enkele klikken de SSO-extensie configureren met het profiel **Apparaatfuncties** > **App-extensie voor eenmalige aanmelding** op de beheerconsole. 

Zie [App-extensie voor eenmalige aanmelding](~/configuration/device-features-configure.md#single-sign-on-app-extension) voor meer informatie over SSO-app-extensies voor iOS of het configureren van apparaatfuncties.

### <a name="company-portal-for-ios-to-support-landscape-mode--6048329----"></a>Bedrijfsportal voor iOS ter ondersteuning van liggende modus<!--6048329  -->
Gebruikers kunnen hun apparaat inschrijven, apps zoeken en ondersteuning krijgen met hun favoriete schermstand. De app detecteert automatisch de stand en past de weergave aan de liggende of staande modus van het scherm aan, tenzij gebruikers het scherm vergrendelen in de staande modus. 

### <a name="configure-if-enrollment-is-available-in-company-portal-for-android-and-ios---4260128-idready-idstaged---"></a>Configureren bij inschrijving is beschikbaar in de bedrijfsportal voor Android en iOS<!-- 4260128 idready idstaged -->
Binnenkort is een nieuwe instelling beschikbaar waarmee u kunt configureren of apparaatinschrijving in de bedrijfsportal op Android- en iOS-apparaten beschikbaar is met prompts, beschikbaar is zonder prompts of niet beschikbaar is voor gebruikers. Ga naar het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) en selecteer **Tenantbeheer** > **Aanpassing** > **Bewerken** > **Apparaatinschrijving** om deze instelling in Intune te zoeken. Raadpleeg [De bedrijfsportal-app van Microsoft Intune configureren](~/apps/company-portal-app.md) voor meer informatie over de bestaande bedrijfsportal-aanpassingen.

### <a name="improved-sign-in-experience-in-company-portal-for-android---6103997----"></a>Bijgewerkte aanmeldervaring voor de bedrijfsportal-app voor Android<!-- 6103997  -->
De indeling van diverse aanmeldingsschermen in de bedrijfsportal-app voor Android wordt momenteel bijgewerkt voor een modernere, eenvoudige en duidelijke ervaring voor gebruikers.

<!-- ***********************************************-->
## <a name="device-configuration"></a>Apparaatconfiguratie

### <a name="wired-network-device-configuration-profiles-for-macos-devices---3508686----"></a>Configuratieprofielen voor een bekabeld netwerkapparaat voor macOS-apparaten<!-- 3508686  -->
Er wordt een nieuw configuratieprofiel voor macOS-apparaten beschikbaar gemaakt om bekabelde netwerken te configureren (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **macOS** als platform > **Bekabeld netwerk** als profieltype). Gebruik deze functie om 802.1x-profielen te maken om bekabelde netwerken te beheren en om deze bekabelde netwerken te implementeren op uw macOS-apparaten.

Van toepassing op:
- macOS

### <a name="vpn-profiles-with-ikev2-vpn-connections-can-use-always-on-with-iosipados-devices----1947932----"></a>Voor VPN-profielen met IKEv2 VPN-verbindingen kan AlwaysOn worden gebruikt voor iOS-/iPadOS-apparaten <!-- 1947932  -->
Op iOS-/iPadOS-apparaten kunt u een VPN-profiel maken dat gebruikmaakt van een IKEv2-verbinding (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS/iPadOS** als platform > **VPN** als profieltype). In een toekomstige update kunt u AlwaysOn configureren met IKEv2. IKEv2 VPN-profielen maken, nadat deze zijn geconfigureerd, automatisch verbinding en blijven verbonden (of maken snel opnieuw verbinding) met het VPN. De verbinding blijft bestaan, ook bij wisselingen van netwerk of als apparaten opnieuw worden opgestart.

In iOS/iPadOS is AlwaysOn VPN beperkt tot IKEv2-profielen.

Als u wilt zien welke IKEv2-instellingen u momenteel kunt configureren, gaat u naar [VPN-instellingen toevoegen op iOS-/iPadOS-apparaten in Microsoft Intune](../configuration/vpn-settings-ios.md#ikev2-settings).

Van toepassing op:
- iOS

### <a name="improved-user-interface-experience-when-creating-configuration-profiles-on-iosipados-and-macos-devices---5569008-5569039-5569057-5569110-5569116-5569131-5569139-5569153-5859984----"></a>Verbeterde gebruikersinterface-ervaring bij het maken van configuratieprofielen op iOS-/iPadOS- en macOS-apparaten<!-- 5569008-5569039-5569057-5569110-5569116-5569131-5569139-5569153-5859984  -->
Wanneer u een profiel voor iOS-/iPadOS- of macOS-apparaten maakt, wordt de ervaring in het Beheercentrum voor Eindpuntbeheer bijgewerkt. Deze wijziging is van invloed op de volgende apparaatconfiguratieprofielen (**Apparaten** > **Configuratieprofielen** > **Profiel maken** > **iOS** of **macOS** als platform):

- Aangepast: iOS/iPadOS, macOS
- Apparaatfuncties: iOS/iPadOS, macOS
- Apparaatbeperkingen: iOS/iPadOS, macOS
- Endpoint Protection: macOS
- Extensies: macOS
- Voorkeursbestand: macOS

### <a name="improved-user-interface-experience-when-creating-oemconfig-configuration-profiles-on-android-enterprise-devices---5568645-----"></a>Verbeterde gebruikersinterface-ervaring bij het maken van OEMConfig-configuratieprofielen op Android Enterprise-apparaten<!-- 5568645   -->
Wanneer u een OEMConfig-profiel voor Android Enterprise-apparaten maakt of bewerkt, wordt de ervaring in het Beheercentrum voor Eindpuntbeheer bijgewerkt. De bijgewerkte ervaring biedt in één oogopslag een overzicht van de instellingen die u hebt geconfigureerd. Deze wijziging is van invloed op het OEMConfig-apparaatconfiguratieprofiel (**Apparaten** > **Configuratieprofielen** > **Profiel maken** > **Android Enterprise** als platform > **OEMConfig** als profieltype).

Deze functie is van toepassing op:
- Android Enterprise 

### <a name="enterprise-app-trust-settings-modification-setting-will-be-removed-from-iosipados-device-restriction-profiles---6225131----"></a>De instelling voor aanpassing van de vertrouwensinstellingen voor de Enterprise-app wordt verwijderd uit de profielen voor apparaatbeperking voor iOS/iPadOS<!-- 6225131  -->
U maakt een profiel met apparaatbeperkingen op het iOS/iPadOS-apparaat (**Apparaten** > **Configuratieprofielen** > **Profiel maken** > **iOS/iPadOS** voor platform > **Apparaatbeperkingen** voor profieltype). De instelling **Aanpassing van de vertrouwensinstellingen voor de Enterprise-app** wordt door Apple verwijderd en uit Intune verwijderd. Als u deze instelling momenteel in een profiel gebruikt, heeft dit geen gevolgen en blijft deze instelling deel uitmaken van uw profiel totdat u een nieuw profiel maakt. Deze instelling wordt ook verwijderd uit rapporten in Intune.

Van toepassing op:
- iOS/iPadOS

Ga naar [iOS- en iPadOS-apparaatinstellingen om functies toe te staan of te beperken met Intune](../configuration/device-restrictions-ios.md) als u alle instellingen wilt bekijken die u kunt beperken.

### <a name="device-configuration-profile-settings-and-values-will-be-updated-for-windows-platforms---4091122---"></a>De instellingen en waarden voor apparaatconfiguratieprofielen worden bijgewerkt voor Windows-platformen<!-- 4091122 -->
Wanneer u apparaatconfiguratieprofielen voor Windows-platformen maakt (**Apparaten** > **Configuratieprofielen** > **Profiel maken** > elke **Windows**-optie voor platform), wijken een aantal instellingen en de bijbehorende waarden af van de CSP; dit kan verwarrend zijn. De namen van instellingen en de bijbehorende waarden worden bijgewerkt zodat ze duidelijker zijn.

Van toepassing op:

- Configuratieprofielen voor Windows 10 en hoger
- Apparaatconfiguratieprofielen voor Windows Holographic voor Bedrijven
- Apparaatconfiguratieprofielen voor Windows 8.1
- Apparaatconfiguratieprofielen voor Windows Phone 8.1

### <a name="improved-user-interface-experience-when-creating-device-restrictions-profiles-on-android-and-android-enterprise-devices---5841361---"></a>Verbeterde gebruikersinterface-ervaring bij het maken van profielen voor apparaatbeperkingen op Android- en Android Enterprise-apparaten<!-- 5841361 -->
Wanneer u een profiel voor Android- of Android Enterprise-apparaten maakt, wordt de ervaring in het Beheercentrum voor Eindpuntbeheer bijgewerkt. Deze wijziging is van invloed op de volgende apparaatconfiguratieprofielen (**Apparaten** > **Configuratieprofielen** > **Profiel maken** > **Android-apparaatbeheerder** of **Android Enterprise** voor platform):

- Apparaatbeperkingen: Android-apparaatbeheerder
- Apparaatbeperkingen: Android Enterprise-apparaateigenaar
- Apparaatbeperkingen: Android Enterprise - Werkprofiel

Zie [Android-apparaatbeheerder](../configuration/device-restrictions-android.md) en [Android Enterprise](../configuration/device-restrictions-android-for-work.md) voor meer informatie over de apparaatbeperkingen die u kunt configureren.

### <a name="delete-bundles-and-bundle-arrays-in-oemconfig-device-configuration-profiles-on-android-enterprise-devices---5550355----"></a>Bundels en gebundelde matrices verwijderen uit OEMConfig-apparaatconfiguratieprofielen op Android Enterprise-apparaten<!-- 5550355  -->
Op Android Enterprise-apparaten kunt u OEMConfig-profielen maken en bijwerken. Gebruikers kunnen bundels en gebundelde matrices verwijderen met behulp van de **Configuration Designer** in Intune.

Zie [Android Enterprise-apparaten gebruiken en beheren met OEMConfig in Microsoft Intune](../configuration/android-oem-configuration-overview.md) voor meer informatie over OEMConfig-profielen.

Deze functie is van toepassing op:
- Android Enterprise

### <a name="support-for-wpa-and-wpa2-in-ios-enterprise-wi-fi-profiles--6215273-----"></a>Ondersteuning voor WPA en WPA2 in Enterprise Wi-Fi-profielen voor iOS<!--6215273   -->
Het veld *Beveiligingstype* wordt toegevoegd aan het [Enterprise Wi-Fi-profiel voor iOS](../configuration/wi-fi-settings-ios.md) (**Apparaten** > **Configuratieprofielen** > **Profiel maken** en selecteer **iOS/iPadOS** als *Platform* en kies vervolgens **Wi-Fi** als *Profiel*). Dit is vergelijkbaar met de beschikbare opties voor een Wi-Fi-basisprofiel voor iOS. Dankzij deze wijziging kunt u nieuwe profielen maken waarmee het beveiligingstype **WPA-Enterprise** of **WPA/WPA2-Enterprise** wordt opgegeven. Vervolgens kunt u een selectie voor het *EAP-type* opgeven.

### <a name="new-user-experience-for-certificate-email-vpn-and-wi-fi-profiles---5615208-----"></a>Nieuwe gebruikerservaring voor certificaat-, e-mail-, VPN- en Wi-Fi-profielen<!-- 5615208   -->
De [gebruikerservaring](../configuration/device-profile-create.md) in het Beheercentrum voor Eindpuntbeheer wordt bijgewerkt (**Apparaten** > **Configuratieprofielen** > **Profiel maken**) voor het maken en aanpassen van de volgende profieltypen. De nieuwe ervaring biedt dezelfde instellingen als voorheen, maar kent een vergelijkbare wizardachtige methode waarvoor minder horizontaal bladeren is vereist. U hoeft bestaande configuraties niet bij te werken met de nieuwe ervaring.
- Afgeleide referentie
- E-mail
- PKCS-certificaat
- PKCS-geïmporteerd certificaat
- SCEP-certificaat
- Vertrouwd certificaat
- VPN
- Wi-Fi

(**Apparaten** > **Configuratieprofielen** > **Profiel maken** en selecteer vervolgens voor de eerdere profielen het *Profieltype*.)

### <a name="configure-the-microsoft-defender-atp-app-for-macos-----5520115----"></a>De Microsoft Defender ATP-app configureren voor macOS  <!-- 5520115  -->
Binnenkort kunt u de [instellingen](../protect/endpoint-protection-macos.md) configureren voor de Microsoft Defender ATP-app voor apparaten waarop macOS wordt uitgevoerd als onderdeel van een apparaatconfiguratieprofiel voor eindpuntbeveiliging (**Apparaten** > **Configuratieprofielen** > **Profiel maken**, selecteer **macOS** als *Platform* en kies vervolgens **Eindpuntbeveiliging** als *Profieltype*). Voor de configuratie van macOS-apparaten zijn acht instellingen beschikbaar. 

Defender ATP wordt ondersteund op apparaten met macOS 10.13 (High Sierra) en hoger. Bovendien moet de [Microsoft Defender ATP](../apps/apps-advanced-threat-protection-macos.md)-app worden geïmplementeerd *nadat* deze instellingen zijn toegepast. De instellingen moeten naar het apparaat worden verzonden voordat de app wordt geïmplementeerd. Bètaversies van macOS worden niet ondersteund.

### <a name="new-filevault-setting-for-macos-endpoint-protection-device-configuration-policy---5459801-----"></a>De nieuwe FileVault-instelling voor het apparaatconfiguratiebeleid voor eindpuntbeveiliging voor macOS<!-- 5459801   -->
Op de sjabloon [macOS-eindpuntbeveiliging](../protect/endpoint-protection-macos.md) wordt een nieuwe instelling aan de FileVault-categorie toegevoegd: Herstelsleutel verbergen. (**Apparaten** > **Configuratieprofielen** > **Profiel maken**, selecteer **macOS** als het *Platform* en kies vervolgens **Eindpuntbeveiliging** als het *Profieltype*). Door deze instelling wordt de persoonlijke sleutel tijdens de FileVault 2-versleuteling voor de eindgebruiker verborgen. Apparaatgebruikers kunnen hun persoonlijke herstelsleutel op elk gewenst moment weergeven via de bedrijfsportal-app voor iOS of via de bedrijfsportal-website voor het versleutelde macOS-apparaat. Ga naar Apparaatgegevens en klik op *Herstelsleutel ophalen* om de persoonlijke herstelsleutel weer te geven.

Deze instelling is niet beschikbaar in een eerder gemaakt beleid. U moet FileVault-beleidsregels opnieuw maken om deze instelling te configureren zodat u er gebruik van kunt maken. 

###  <a name="ui-update-when-configuring-compliance-policy----3961639----"></a>Update van gebruikersinterface tijdens de configuratie van het nalevingsbeleid <!-- 3961639  -->
De gebruikersinterface wordt bijgewerkt voor het configureren van nalevingsbeleid in Microsoft Endpoint Manager (**Apparaten** > **Nalevingsbeleid** > **Beleidsregels** > **Beleid maken**). U ziet een nieuwe gebruikerservaring die dezelfde instellingen en gegevens als voorheen biedt. Bij de nieuwe ervaring wordt gebruikgemaakt van een wizard om een nalevingsbeleid te maken dat de pagina bevat waarop u *Toewijzingen* voor het beleid kunt toevoegen. Ook wordt de pagina *Samenvatting* weergegeven waarop u uw configuratie kunt controleren voordat u het beleid maakt. 

### <a name="configure-delivery-optimization-agent-when-downloading-win32-app-content---5410945----"></a>Delivery Optimization-agent configureren tijdens het downloaden van inhoud voor de Win32-app<!-- 5410945  -->
U kunt de Delivery Optimization-agent configureren zodat inhoud voor de Win32-app op de achtergrond of op de voorgrond wordt gedownload op basis van de toewijzing. Voor bestaande Win32-apps wordt inhoud nog steeds op de achtergrond gedownload. Selecteer in het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) de opties **Apparaten** > **Configuratieprofielen** > **Profiel maken**. Selecteer **Windows 10 en hoger** als het **Platform**. Selecteer bij **Profieltype** de optie **Delivery Optimization**. Zie [Beheer van Win32-apps - Delivery Optimization](~/apps/apps-win32-app-management.md#delivery-optimization) voor meer informatie over Delivery Optimization.


<!-- ***********************************************-->
<!--## Device enrollment-->

<!-- ***********************************************-->
## <a name="device-management"></a>Apparaatbeheer

### <a name="change-primary-user-for-windows-devices----3794742---"></a>Primaire gebruiker wijzigen voor Windows-apparaten <!-- 3794742 -->
U kunt de primaire gebruiker voor hybride Windows-apparaten en gekoppelde Azure AD-apparaten wijzigen. Ga hiervoor naar **Intune** > **Apparaten** > **Alle apparaten** > kies een apparaat > **Eigenschappen** > **Primaire gebruiker**. 

### <a name="new-android-report-on-android-devices-overview-page---5435435---"></a>Nieuw Android-rapport op de overzichtspagina Android-apparaten<!-- 5435435 -->
Er wordt een rapport aan de Microsoft Endpoint Manager-beheerconsole toegevoegd op de pagina met het overzicht van Android-apparaten waarop wordt weergegeven hoeveel Android-apparaten zijn ingeschreven in elke oplossing voor apparaatbeheer. In dit diagram (vergelijkbaar met hetzelfde diagram dat u al via de Azure-console hebt gemaakt) ziet u het aantal apparaten met werkprofiel, volledig beheerd, toegewezen en door de beheerder geregistreerd. Kies **Apparaten** > **Android** > **Overzicht** om het rapport weer te geven.

### <a name="powershell-scripts-support-for-byod-devices---1862833----"></a>Ondersteuning van PowerShell-scripts voor BYOD-apparaten<!-- 1862833  -->
PowerShell-scripts bieden ondersteuning voor apparaten die bij Azure AD zijn geregistreerd in Intune. Zie [PowerShell-scripts op Windows 10-apparaten gebruiken in Intune](~/apps/intune-management-extension.md) voor meer informatie over PowerShell. Deze functionaliteit biedt geen ondersteuning voor apparaten waarop de Windows 10 Home-editie wordt uitgevoerd.

### <a name="additional-data-warehouse-device-inventory-properties---6125732----"></a>Aanvullende eigenschappen voor inventaris van Data Warehouse-apparaten<!-- 6125732  -->
Er zijn aanvullende eigenschappen voor de inventaris van apparaten beschikbaar met behulp van het Intune Data Warehouse. Via de verzameling [apparaten](~/developer/intune-data-warehouse-collections.md#devices) zijn de volgende eigenschappen beschikbaar:
- Opslagcapaciteit 
- Geheugencapaciteit
- Office 365-versie
- Apparaatmodel

Zie [Microsoft Intune Data Warehouse-API](~/developer/reports-nav-intune-data-warehouse.md) voor meer informatie over het datawarehouse.

### <a name="guide-users-from-android-device-administrator-management-to-work-profile-management--5857738--"></a>Gebruikers doorsturen van Beheer door Android-apparaatbeheerder naar Beheer van werkprofielen<!--5857738-->
Binnenkort wordt een nieuwe nalevingsinstelling uitgebracht voor het Android-apparaatbeheerplatform. Met behulp van deze instelling kunt u een apparaat niet-compatibel maken als dit apparaat door de apparaatbeheerder wordt beheerd.

Op deze niet-compatibele apparaten zien gebruikers op de pagina **Apparaatinstellingen bijwerken** het bericht **Verplaatsen naar nieuwe instelling voor apparaatbeheer**. Als ze op de knop **Oplossen** tikken, worden ze geholpen bij het volgende:

1. Uitschrijven bij Beheer door apparaatbeheerder
2. Inschrijven bij Beheer van werkprofielen
3. Problemen met naleving oplossen 
 
Google vermindert de ondersteuning voor apparaatbeheerders in nieuwe Android-versies in een poging om apparaatbeheer moderner, breder en veiliger te maken met behulp van Android Enterprise.  Intune biedt slechts tot het tweede kwartaal van 2020 nog ondersteuning voor Android-apparaten met Android 10 en hoger die door apparaatbeheerder worden beheerd. Apparaten die worden beheerd met apparaatbeheerder (m.u.v. Samsung) en waarop Android 10 of hoger wordt uitgevoerd, kunnen na dit moment niet langer volledig worden beheerd. Betrokken apparaten ontvangen met name geen nieuwe wachtwoordvereisten meer. Lees deze [Kennisgeving](#decreasing-support-for-android-device-administrator) voor meer informatie.

### <a name="retire-noncompliant-devices---1827291---"></a>Niet-compatibele apparaten buiten gebruik stellen<!-- 1827291 -->
Er wordt ene nieuwe optionele nalevingsactie toegevoegd, zodat een niet-compatibel apparaat buiten gebruik kan worden gesteld (**Apparaten** > **Nalevingsbeleid** > **Beleidsregels** > **Beleid maken**; geef vervolgens de beschikbare *Acties* weer op de pagina *Acties voor niet-naleving*).  Bij het buiten gebruik stellen van een niet-conform apparaat worden alle bedrijfsgegevens verwijderd en wordt het apparaat ook uit het Intune-beheer verwijderd. Deze actie wordt uitgevoerd wanneer de geconfigureerde waarde in dagen is bereikt. De minimumwaarde is 30 dagen.  Expliciete goedkeuring van de IT-beheerder is vereist voor het buiten gebruik stellen van de apparaten met behulp van de sectie *buiten gebruik stellen van niet-compatibele apparaten*, waarbij beheerders alle in aanmerking komende apparaten buiten gebruik kunnen stellen.

### <a name="new-information-in-device-details---5604099---"></a>Nieuwe informatie in apparaatdetails<!-- 5604099 -->
De pagina **Overzicht** voor apparaten bevat de volgende informatie:
- Opslagcapaciteit (hoeveelheid fysieke opslag op het apparaat)
- Geheugencapaciteit (hoeveelheid fysiek geheugen op het apparaat)

### <a name="script-support-for-macos-devices---4280361----"></a>Scriptondersteuning voor macOS-apparaten<!-- 4280361  -->
U kunt scripts toevoegen en implementeren op macOS-apparaten. Dankzij deze ondersteuning hebt u meer mogelijkheden om macOS-apparaten te configureren buiten wat al mogelijk is, met behulp van systeemeigen MDM-mogelijkheden op macOS-apparaten. 

<!-- ***********************************************-->
<!--## Intune apps-->
 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
## <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

### <a name="help-and-support-workflow-update-to-support-additional-services---5654170---"></a>Update voor hulp en ondersteuning bij workflows ter ondersteuning van extra services<!-- 5654170 -->
De pagina Hulp en ondersteuning in het Microsoft Endpoint Manager-beheercentrum wordt bijgewerkt zodat u het beheertype kunt kiezen dat u wilt gebruiken, voor het bieden van specifiekere ondersteuning (**Probleemoplossing en ondersteuning** >  **Hulp en ondersteuning**). Dankzij deze wijziging kunt u de volgende beheertypen selecteren:
- Configuration Manager (bevat Desktop Analytics)
- Intune
- Co-beheer

<!-- ***********************************************-->
<!--
## Role-based access control
-->

<!-- ***********************************************-->
## <a name="security"></a>Beveiliging

### <a name="derived-credentials-support-on-android-cobo-devices--4839592--"></a>Ondersteuning voor afgeleide referenties op Android COBO-apparaten<!--4839592-->
U kunt afgeleide referenties gebruiken op volledig beheerde Android Enterprise-apparaten. Ondersteuning wordt opgenomen voor het ophalen van een afgeleide referentie voor Entrust Datacard, Intercede en DISA Purebred. U kunt een afgeleide referentie gebruiken voor appverificatie, Wi-Fi, VPN of voor S/MIME-ondertekening en/of versleuteling voor apps die dit ondersteunen.

### <a name="use-antivirus-policy-to-manage-settings-for-microsoft-defender-antivirus-and-the-windows-security-experience--6131401---"></a>Antivirusbeleid gebruiken om instellingen voor Microsoft Defender Antivirus en de Windows-beveiligingservaring te beheren<!--6131401 -->
Vanuit het knooppunt *Eindpuntbeveiliging* kunt u instellingen voor **Antivirus** configureren. Wanneer u beleid voor Antivirus configureert, definieert u de instellingen voor uw Windows 10-apparaten via twee profieltypen:

- Microsoft Defender Antivirus: instellingen voor cloudbeveiliging, uitsluitingen voor Antivirus, herstel, scanopties, en meer beheren.
- Windows-beveiligingservaring: beheren hoe gebruikers instellingen voor Windows-beveiliging op hun apparaten ervaren. U kunt configureren wat eindgebruikers kunnen bekijken in het Microsoft Defender-beveiligingscentrum en welke meldingen ze ontvangen.

### <a name="users-personal-encrypted-recovery-key---6273943---"></a>Persoonlijke, versleutelde herstelsleutel van gebruiker<!-- 6273943 -->
Binnenkort is een nieuwe Intune-functie beschikbaar waarmee gebruikers hun persoonlijke, versleutelde **FileVault**-herstelsleutel voor Mac-apparaten kunnen downloaden via de bedrijfsportal-toepassing voor Android of via de Android Intune-toepassing. Zowel in de bedrijfsportal-toepassing als in de Intune-toepassing zal een koppeling beschikbaar zijn waarmee de onlinebedrijfsportal in een Chrome-browser wordt geopend. Hier kunnen gebruikers de **FileVault**-herstelsleutel zien die ze nodig hebben voor toegang tot hun Mac-apparaten. Zie [Apparaatversleuteling gebruiken met Intune](~/protect/encrypt-devices.md) voor meer informatie over versleuteling.

### <a name="privacy-preferences-settings-for-macos-devices---2934232---"></a>Voorkeursinstellingen voor privacy voor macOS-apparaten<!-- 2934232 --> 
Bij de release van macOS Catalina 10.15 zijn nieuwe beveiligings- en privacyverbeteringen toegevoegd. Standaard kunnen toepassingen en processen zonder toestemming van de gebruiker geen toegang krijgen tot specifieke gegevens. Als gebruikers geen toestemming geven, werken de toepassingen en processen mogelijk niet. Intune voegt ondersteuning toe voor instellingen waarmee IT-beheerders toestemming voor toegang tot gegevens namens eindgebruikers kunnen toestaan of weigeren op apparaten waarop macOS 10.14 of hoger wordt uitgevoerd. Door deze instellingen blijven toepassingen en processen goed werken en krijgen eindgebruikers minder vaak prompts te zien. 

### <a name="updated-ui-text-and-labels-for-windows-10-endpoint-protection-profile-settings---5983747---"></a>Bijgewerkte tekst en labels voor gebruikersinterface voor instellingen van het Windows 10-eindpuntbeveiligingsprofiel<!-- 5983747 -->
De tekst wordt bijgewerkt voor diverse instellingen die u als Windows 10-apparaatconfiguratieprofielen configureert, zodat u beter begrijpt wat het beoogde gebruik en de beoogde resultaten van de instellingen zijn. 

De instellingen die worden bijgewerkt, zijn onder andere Windows 10-apparaatconfiguratieprofielen voor: 
- [Apparaatbeperkingen](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus) > Microsoft Defender Antivirus  
- [Endpoint Protection](../protect/endpoint-protection-windows-10.md) > Microsoft Defender Antivirus

De instellingen die door Intune worden ondersteund, worden niet gewijzigd. Alleen de tekst van de gebruikersinterface in het Beheercentrum voor Microsoft-eindpuntbeheer wordt hierdoor bijgewerkt. 


<!-- ***********************************************-->
## <a name="notices"></a>Mededelingen

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Zie tevens
Voor meer informatie over recente ontwikkelingen raadpleegt u [Wat is er nieuw in Microsoft Intune?](whats-new.md).



