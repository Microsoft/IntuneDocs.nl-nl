---
title: In ontwikkeling - Microsoft Intune
titleSuffix: ''
description: Microsoft Intune-functies in ontwikkeling
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/27/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 009b9cf22bcdd73eb563c772cc9995047f05a9c1
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71735763"
---
# <a name="in-development-for-microsoft-intune---october-2019"></a>In ontwikkeling voor Microsoft Intune - oktober 2019

Als ondersteuning bij uw gereedheid en planning worden op deze pagina updates voor en functies van de Intune-gebruikersinterface vermeld die in ontwikkeling zijn, maar nog niet zijn uitgebracht. Daarnaast:

- Als we verwachten dat u actie moet ondernemen vóór een wijziging, publiceren we een aanvullend bericht in het Office-berichtencentrum.
- Als er een functie wordt uitgebracht in productie, ofwel als preview ofwel als algemeen beschikbare functie, wordt de functiebeschrijving verplaatst van deze pagina naar de [pagina Nieuwe functies](whats-new.md).
- Deze pagina en de pagina [Nieuwe functies](whats-new.md) worden regelmatig bijgewerkt. Controleer op andere updates.
- Raadpleeg de [M365-roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) voor strategische producten en tijdlijnen.

> [!Note]
> Deze items representeren de huidige verwachtingen van Microsoft over Intune-mogelijkheden in een toekomstige release. Datums en afzonderlijke functies kunnen worden gewijzigd. Niet alle items in ontwikkeling hebben een functieomschrijving op deze pagina.

**RSS feed**: ontvang een melding wanneer deze pagina wordt bijgewerkt door de volgende URL in uw feedlezer te kopiëren en plakken: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

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

### <a name="additional-app-configuration-variable-available----4969237----"></a>Extra app-configuratie variabele beschikbaar <!-- 4969237  -->
Bij het maken van een app-configuratie beleid kunt u de configuratie variabele `AAD Device ID` opnemen als onderdeel van uw configuratie-instellingen. Selecteer in Intune **Client-apps** > **App-configuratiebeleid** > **Toevoegen**. Voer uw configuratie beleids gegevens in en selecteer **configuratie-instellingen** om de Blade configuratie- **instellingen** weer te geven.

### <a name="dark-mode-for-ios-company-portal----4911422----"></a>Donkere modus voor iOS-Bedrijfsportal <!-- 4911422  -->
De donkere modus is gepland voor de iOS-Bedrijfsportal. Down load bedrijfsapps, beheer uw apparaten en ontvang IT-ondersteuning in het kleuren schema van uw keuze. Meer informatie over de iOS-bedrijfsportal vindt u in [De app Microsoft Intune-bedrijfsportal configureren](../apps/company-portal-app.md).

### <a name="prevent-installation-of-apps-from-unknown-sources-on-android-enterprise-devices----4760025----"></a>Installatie van apps van onbekende bronnen op Android Enter prise-apparaten voor komen <!-- 4760025  -->
In het geval van een Android Enter prise work-profiel apparaat is het nooit mogelijk dat eind gebruikers apps van onbekende bronnen installeren in het werk profiel. U kunt deze beperking eventueel ook uitbreiden naar het persoonlijke profiel. Als u deze beperking inschakelt, kunnen eind gebruikers van apparaten met een Android-werk profiel ook voor komen dat apps van onbekende bronnen worden geladen in de persoonlijke kant van hun apparaat. 

### <a name="update-to-app-protection-ui-and-ios-app-provisioning-ui----4102027-4102029----"></a>Bijwerken naar de gebruikers interface van de app-beveiliging en de gebruikers interface voor iOS-apps inrichten <!-- 4102027, 4102029  -->
De gebruikers interface voor het maken en bewerken van app-beveiligings beleid en inrichtings profielen voor iOS-apps in intune wordt bijgewerkt. De gebruikersinterface wordt onder andere op deze punten gewijzigd:
- Een vereenvoudigde ervaring met behulp van een indeling van de wizard stijl, versmald binnen één Blade. 
- Een update voor het maken van een stroom voor het toevoegen van toewijzingen.
- Een samenvattings pagina van alle items die zijn ingesteld bij het weer geven van eigenschappen, vóór het maken van een nieuw beleid of bij het bewerken van een eigenschap. Bij het bewerken van eigenschappen wordt in de samen vatting ook een lijst met items weer gegeven uit de categorie met eigenschappen die worden bewerkt.

### <a name="create-groups-of-management-objects-called-policy-sets----3762880----"></a>Groepen beheer objecten met de naam beleids sets maken <!-- 3762880  -->
Met beleids sets kunt u een bundel van verwijzingen maken naar bestaande beheer entiteiten die moeten worden geïdentificeerd, gericht en bewaakt als een enkele conceptuele eenheid. Met beleids sets worden bestaande concepten of objecten niet vervangen. Een beheerder kan afzonderlijke objecten gewoon blijven toewijzen. Er wordt naar afzonderlijke objecten verwezen door een beleidsset. Daarom worden wijzigingen aan deze afzonderlijke objecten weer gegeven in de beleidsset.  In intune selecteert u **beleids sets** > **Create** om een nieuwe beleidsset te maken. 

### <a name="win32-apps-on-windows-10-s-mode-devices----3747604----"></a>Win32-apps op Windows 10 S-modus apparaten <!-- 3747604  --> 
U kunt Win32-apps installeren en uitvoeren op Windows 10 S-modus-beheerde apparaten. U kunt een of meer aanvullende beleids regels maken voor de modus S met behulp van de Windows Defender Application Control (WDAC) Power shell-hulpprogram ma's. Onderteken het aanvullende beleid met de handtekening portal van Device Guard en upload en distribueer vervolgens het beleid via intune. In intune kunt u deze mogelijkheid vinden door client- **apps**te selecteren  > **Windows 10 S aanvullende beleids regels**. 

### <a name="set-app-availability-based-on-a-date-and-time----3510685----"></a>Beschik baarheid van apps instellen op basis van een datum en tijd <!-- 3510685  -->
Als beheerder kunt u de begin tijd en deadline tijd voor een vereiste app configureren. Op het moment dat de intune-beheer uitbreiding wordt gestart, wordt de inhoud van de app gedownload en in de cache opgeslagen. De app wordt geïnstalleerd op het tijdstip van de deadline. Voor beschik bare apps wordt in de start tijd gedicteerd wanneer de app wordt weer gegeven in Bedrijfsportal. Selecteer in Intune **Client-apps** > **Apps**. Selecteer vervolgens een specifieke app uit de lijst of selecteer **toevoegen** om een nieuwe app toe te voegen. Selecteer in de Blade app **toewijzingen** > **groep toevoegen**. Stel het **toewijzings type** in op **vereist** en selecteer vervolgens **opgenomen groepen**. Stel **deze app vereist voor alle gebruikers** in op **Ja** en selecteer **bewerken** om de opties voor de **eind gebruikers ervaring** te wijzigen. Stel op de Blade **eind gebruikers ervaring** de **software beschik bare tijd** in als nodig. Zie [Apps toevoegen aan Microsoft Intune](../apps/apps-add.md) voor meer informatie over het toevoegen van apps.

### <a name="require-win32-apps-to-restart----3136567----"></a>Vereisen dat Win32-apps opnieuw worden opgestart <!-- 3136567  -->
U kunt vereisen dat een Win32-app opnieuw moet worden gestart na een geslaagde installatie. U kunt ook de hoeveelheid tijd (de respijt periode) kiezen voordat de computer opnieuw moet worden opgestart.

### <a name="company-portal-app-on-windows----1808082----"></a>App Bedrijfsportal in Windows <!-- 1808082  -->
De Bedrijfsportal-app op Windows-apparaten wordt bijgewerkt om pop-upmeldingen voor gebruikers weer te geven, zelfs wanneer de toepassing wordt gesloten. In de update worden alleen meldingen voor beschik bare apps weer gegeven wanneer de installatie status is voltooid of mislukt. In de app Bedrijfsportal worden geen meldingen weer gegeven voor de vereiste toepassingen.

### <a name="company-portal-app-installation-status-messages----2514416----"></a>Berichten over de installatie status van Bedrijfsportal-app <!-- 2514416  -->
In de Bedrijfsportal-app worden aanvullende status berichten voor de app-installatie weer gegeven voor eind gebruikers. De volgende voor waarden zijn van toepassing op nieuwe Win32-afhankelijkheids functies:
- App installeren mislukt. Er is niet voldaan aan de afhankelijkheden die zijn gedefinieerd door de beheerder.
- De app is geïnstalleerd, maar moet opnieuw worden opgestart.
- De app wordt geïnstalleerd, maar moet opnieuw worden opgestart om verder te gaan.

#### <a name="assign-microsoft-edge-beta-for-macos----4678761----"></a>Micro soft Edge Beta toewijzen voor macOS <!-- 4678761  -->
U kunt de nieuwste versie van micro soft Edge Beta toevoegen en toewijzen aan intune voor macOS-apparaten. Selecteer in intune **client-apps** > **apps** > **app toevoegen** > **micro soft Edge-macOS**. Wijs vervolgens micro soft Edge Beta toe aan de gewenste groepen. Micro soft auto update (MAU) houdt micro soft Edge up-to-date. Zie voor meer informatie over micro soft Edge [webtoegang beheren met behulp van micro soft Edge met Microsoft intune](../apps/manage-microsoft-edge.md).

### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Inhoud van app-meldingen voor organisatie accounts configureren <!-- 2576686 -->
Met intune app-beveiligings beleid (APP) op Android-en iOS-apparaten kunt u inhoud voor app-meldingen beheren voor organisatie accounts. Deze functie vereist ondersteuning van toepassingen en is mogelijk niet beschikbaar voor alle toepassingen die zijn ingeschakeld voor apps. Zie [Wat is beveiligingsbeleid voor apps?](../apps/app-protection-policy.md) voor meer informatie over APP.

### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956----"></a>Beschikbare rapportage over Google Play-apps voor Android-werkprofielen <!-- 3041956  -->
U kunt voor beschikbare app-installaties op apparaten met Android-werkprofielen de status van de app-installatie en de geïnstalleerde versie van beheerde Google Play-apps bekijken. Zie [How to monitor app protection policies](../apps/app-protection-policies-monitor.md) (App-beveiligingsbeleid controleren), [Manage Android work profile devices with Intune](../enrollment/android-enterprise-overview.md) (Apparaten met Android-werkprofielen beheren met Intune) en [Managed Google Play app type](../apps/apps-add-android-for-work.md#managed-google-play-app-types) (Type beheerde Google Play-app) voor meer informatie.

<!-- ***********************************************-->
## <a name="device-configuration"></a>Apparaatconfiguratie


### <a name="new-device-configuration-settings-for-supervised-ios-and-ipados-devices----5199328----"></a>Nieuwe apparaatconfiguratie-instellingen voor iOS-en iPadOS-apparaten onder Super visie <!-- 5199328  -->
Op iOS-en iPadOS-apparaten kunt u een profiel maken om functies en instellingen op apparaten te beperken (**apparaatconfiguratie** > **profielen** > **profiel maken** > **IOS/iPadOS** voor platform > **apparaat beperkingen** voor profiel type). Er zijn nieuwe instellingen die u kunt beheren: 
- Toegang tot netwerk station in bestanden app  
- Toegang tot USB-station in bestanden app 
- Wi-Fi altijd ingeschakeld 

Als u de huidige instellingen wilt zien, gaat u naar [iOS-apparaatinstellingen voor het toestaan of beperken van functies met Intune](../configuration/device-restrictions-ios.md).

Van toepassing op:
- iOS 13.0 en hoger
- iPadOS 13,0 en hoger

### <a name="connect-automatically-setting-is-removed-in-wi-fi-profiles-on-android-and-android-enterprise----5021055----"></a>De instelling automatisch verbinding maken wordt verwijderd in Wi-Fi-profielen op Android en Android Enter prise <!-- 5021055  -->
Op Android-en Android Enter prise-apparaten kunt u een Wi-Fi-profiel maken voor het configureren van verschillende instellingen (**apparaatconfiguratie** > -**profielen** > **profiel maken** > **Android** of **Android Enter prise** voor platform > **Wi-Fi** voor profiel type). De instelling **verbinding automatisch maken** wordt verwijderd, omdat deze [niet wordt ondersteund door Android](https://developer.android.com/reference/android/net/wifi/WifiManager.html#enableNetwork%28int%2c%20boolean%29). 

Als u deze instelling in een Wi-Fi-profiel gebruikt, ziet u mogelijk dat **automatisch verbinding maken** niet werkt. U hoeft geen actie te ondernemen, maar houd er rekening mee dat deze instelling wordt verwijderd in de intune-gebruikers interface.

Als u de huidige instellingen wilt weer geven, gaat u naar instellingen voor [Android Wi-Fi-instellingen](../configuration/wi-fi-settings-android.md) of [Android-ondernemingen Wi-Fi](../configuration/wi-fi-settings-android-enterprise.md).

Van toepassing op:
- Android
- Android Enterprise

### <a name="create-a-global-http-proxy-on-android-enterprise-device-owner-devices----4816339----"></a>Een algemene HTTP-proxy maken op Android Enter prise Device owner-apparaten <!-- 4816339  -->
Op Android Enter prise-apparaten kunt u een VPN-profiel maken met verschillende VPN-clients (**apparaatconfiguratie** > **profielen** > **profiel maken** > **Android Enter prise** voor platform > eigenaar van het **apparaat > Beperkingen van apparaten** voor profiel type >- **connectiviteit**). U kunt een wereld wijde HTTP-proxy configureren om te voldoen aan de richt lijnen voor websurfen van uw organisatie. Alle apps die naar HTTP-websites gaan, gebruiken deze proxy.

Van toepassing op:
- Android Enterprise-apparaateigenaar

### <a name="new-device-firmware-configuration-interface-profile-for-windows-10-and-later-devices----2266073----"></a>Nieuw firmware configuratie interface profiel voor apparaten voor Windows 10 en hoger <!-- 2266073  -->
In Windows 10 en hoger kunt u een configuratie profiel voor een apparaat maken om instellingen en functies te beheren (**apparaatconfiguratie** > **profielen** > **profiel maken** > **Windows 10 en hoger** voor platform). Er wordt een nieuw profiel type voor de firmware configuratie-interface van een apparaat weer waarmee intune UEFI-instellingen (BIOS) kan beheren.

Voor een overzicht van alle instellingen die u kunt configureren, Zie [onderdelen en instellingen op uw apparaten Toep assen met apparaatprofielen in Microsoft intune](../configuration/device-profiles.md).

Van toepassing op:
- Windows 10 RS5 (1809) en nieuwere versie van sommige Oem's

### <a name="pkcs-certificates-for-macos-----1333650------------------"></a>PKCS-certificaten voor macOS  <!-- 1333650                -->
We gaan de volledige ondersteuning voor PKCS-certificaten toevoegen op apparaten met macOS. Gebruikers kunnen certificaten van gebruikers en apparaten implementeren met de aangepaste naam van het onderwerp en alternatieve namen voor het onderwerp. We hebben ook een nieuwe instelling om alle apps toegang toe te staan, waardoor alle gekoppelde apps toegang hebben tot de persoonlijke sleutel. Ga voor meer informatie over deze instelling naar de volgende Apple-documentatie: https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf.

###   <a name="derived-credentials-to-provision-mobile-devices-with-certificates----------1736036-1736037-1772050--------"></a>Afgeleide referenties voor het inrichten van mobiele apparaten met certificaten      <!--  1736036, 1736037, 1772050      --> 
Er wordt ondersteuning toegevoegd voor afgeleide referenties, die ondersteuning bieden voor het *National Institute of Standards and Technology (NIST) 800-157* -standaard voor het implementeren van certificaten op apparaten.  Afgeleide referenties zijn afhankelijk van het gebruik van een persoonlijke identiteits verificatie (PIV) of een gemeen schappelijke kaart (CAC), zoals een Smart Card. Gebruikers verifiëren zich met hun Smart Card op een computer en verzenden een aanvraag voor een certificaat voor hun beheerde apparaat volgens het proces dat is vereist door de afgeleide referentie provider.   

Het proces voor het gebruiken van afgeleide referenties om een certificaat op te halen, verschilt van het gebruik van SCEP-of PKCS-certificaat profielen, maar het eind resultaat is hetzelfde: mobiele apparaten met certificaten voor verificatie die kunnen worden gebruikt voor app-verificatie, VPN, Wi-Fi of e-mail adres profielen.   

Zie [afgeleide PIV-referenties](https://www.nccoe.nist.gov/projects/building-blocks/piv-credentials) op www.nccoe.nist.gov voor meer informatie.

De eerste release van afgeleide referenties ondersteunt Entrust Datacard, interDISAe en Purebred op iOS. Extra platforms en afgeleide referentie providers worden in latere versies ondersteund.   

<!-- ***********************************************-->
## <a name="device-enrollment"></a>Apparaatinschrijving

### <a name="specify-which-android-device-operating-system-versions-enroll-with-work-profile-or-device-administrator-enrollment----4350697---"></a>Opgeven welke besturingssysteem versies van Android-apparaten worden inge schreven bij het werk profiel of de beheerder van de apparaatregistratie <!-- 4350697 -->
Met behulp van intune-apparaattypen kunt u de versie van het besturings systeem van het apparaat gebruiken om op te geven op welke gebruikers apparaten het Android Enter prise work profile-inschrijving of de registratie van Android-apparaten worden gebruikt. Als u dit wilt doen, gaat u naar **intune**- > **apparaatregistratie** > **registratie beperkingen** > **beperking maken** > -beperking voor**Apparaattype** > -**platform instellingen**.

### <a name="edit-device-name-value-for-autopilot-devices----4816775---"></a>Waarde voor apparaatnaam bewerken voor auto pilot-apparaten <!-- 4816775 -->
U kunt de waarde voor de apparaatnaam voor Azure AD gekoppelde auto pilot-apparaten bewerken. Als u dit wilt doen, gaat u naar **intune**- > **registratie van apparaten** > **Windows-inschrijving** > **windows auto pilot** > **apparaten** > Kies het apparaat > de waarde apparaatnaam in het rechterdeel venster te wijzigen > **opslaan** .

### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal----4394993----"></a>Voor iOS-apparaten past u het privacyvenster voor het inschrijvingsproces van de Bedrijfsportal aan <!-- 4394993  -->
Met behulp van markdown kunt u het privacyvenster van de bedrijfsportal aanpassen dat eindgebruikers te zien krijgen tijdens de iOS-registratie. U kunt met name de lijst met dingen aanpassen die uw organisatie niet op het apparaat kan zien of doen.

<!-- ***********************************************-->
## <a name="device-management"></a>Apparaatbeheer


### <a name="edit-group-tag-value-for-autopilot-devices---4816775---"></a>Groeps label waarde voor auto pilot-apparaten bewerken<!-- 4816775 -->
U kunt de groeps label waarde voor auto pilot-apparaten bewerken. Als u dit wilt doen, gaat u naar **intune** > **registratie van apparaten** > **Windows-inschrijving** > **windows auto pilot** > **apparaten** > Kies het apparaat > de waarde groeps label in het rechterdeel venster te wijzigen > **opslaan** .

### <a name="ui-update-for-creating-and-editing-windows-10-update-rings-----4099089------------"></a>UI-update voor het maken en bewerken van Windows 10-update ringen  <!-- 4099089          -->   
Er wordt een bijgewerkte ervaring voor het maken en bewerken van gebruikers interface voor Windows 10-update ringen voor intune geïmplementeerd.  Wijzigingen in de gebruikers interface zijn onder andere:  
- Vereenvoudig de bestaande ervaring met behulp van een indeling van de wizard stijl, versmald binnen één Blade. Deze update van de gebruikers interface wordt verwijderd met Blade komen waarvoor IT-professionals een drilldownbewerking moeten doen om in te zoomen op diep gaande Blades.   
- Wijzig de stroom maken zodat deze toewijzingen bevat.  
- Het toevoegen van een samenvattings pagina van alle items die zijn ingesteld bij het weer geven van eigenschappen, vóór het maken van een nieuwe update ring en bij het bewerken van een eigenschap. Tijdens het bewerken toont de samenvatting alleen de lijst met items die zijn ingesteld binnen de categorie met eigenschappen die worden bewerkt.

### <a name="ui-update-for-creating-and-editing-ios-software-updates-----4099090----------"></a>Update van de gebruikers interface voor het maken en bewerken van iOS-software-updates  <!-- 4099090        -->   
Er wordt een bijgewerkte ervaring voor het maken en bewerken van gebruikers interface voor iOS-software-updates geïmplementeerd in intune. Wijzigingen in de gebruikers interface zijn onder andere:
- Vereenvoudig de bestaande ervaring met behulp van een indeling van de wizard stijl, versmald binnen één Blade. Deze update van de gebruikers interface wordt verwijderd met Blade komen waarvoor IT-professionals een drilldownbewerking moeten doen om in te zoomen op diep gaande Blades.  
- De stroom voor het maken van beleid voor iOS-software-updates wordt bijgewerkt met toewijzingen 
- Het iOS-software-update beleid bevat een samenvattings pagina van alle items die zijn ingesteld bij het weer geven van eigenschappen, vóór het maken van een nieuw beleid en bij het bewerken van een eigenschap. Tijdens het bewerken toont de samenvatting alleen de lijst met items die zijn ingesteld binnen de categorie met eigenschappen die worden bewerkt.

### <a name="target-macos-user-groups-to-require-jamf-management----4061739---"></a>MacOS-gebruikers groepen die Jamf-beheer vereisen <!-- 4061739 -->
U kunt specifieke groepen gebruikers bereiken om te vereisen dat hun macOS-apparaten worden beheerd door Jamf. Met dit doel kunt u de integratie van Jamf-naleving Toep assen op een subset van macOS-apparaten, terwijl andere apparaten door intune worden beheerd. Daarnaast kunt u de apparaten van gebruikers geleidelijk van het ene MDM naar het andere migreren.

### <a name="new-restrictions-for-renaming-windows-devices----3478938---"></a>Nieuwe beperkingen voor het wijzigen van de naam van Windows-apparaten <!-- 3478938 -->
De apparaatnamen moeten de volgende regels volgen:
- Maxi maal 15 tekens (moet kleiner zijn dan of gelijk zijn aan 63 bytes, niet inclusief navolgende NULLen)
- Niet null of lege teken reeks
- Toegestane ASCII: letters (a-z, A-Z), cijfers (0-9) en afbreek streepjes
- Toegestaan Unicode: tekens > = 0x80, moet een geldige UTF8 zijn, moet IDN-toewijsbaar zijn (RtlIdnToNameprepUnicode slaagt; Zie RFC 3492)
- Namen mogen niet alleen getallen bevatten of beginnen met een cijfer
- Geen spaties in de naam
- Niet-toegestane tekens: {|} ~ [\] ^:; < = >? & @! " # $ % ` ( ) + / , . _ *)

### <a name="deploy-software-updates-to-macos-devices----3194876---"></a>Software-updates implementeren op macOS-apparaten <!-- 3194876 -->
U kunt software-updates implementeren op groepen macOS-apparaten. Deze functie omvat essentiële, firmware, configuratie bestand en andere updates. U kunt updates verzenden via de volgende check van het apparaat of een wekelijkse planning selecteren voor het implementeren van updates in of een periode waarin Windows is ingesteld. Deze functie helpt u bij het bijwerken van apparaten buiten de standaard werk uren of wanneer uw Help Desk volledig is gewerkt. U krijgt ook een gedetailleerd rapport van alle macOS-apparaten waarop updates zijn geïmplementeerd. U kunt inzoomen op het rapport per apparaat om de status van bepaalde updates te bekijken.

<!-- ***********************************************-->
## <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

### <a name="new-android-report-on-devices-overview-page----2984353----"></a>Nieuw Android-rapport op de pagina overzicht van apparaten <!-- 2984353  -->
Er wordt een nieuw rapport aan de overzichts pagina met apparaten toegevoegd waarop wordt weer gegeven hoeveel Android-apparaten zijn geregistreerd in elke oplossing voor Apparaatbeheer. In dit diagram worden werk profielen weer gegeven, volledig beheerd, toegewezen en door de beheerder geregistreerde apparaten. Als u het rapport wilt zien, kiest u **intune** > **apparaten** > **Overview**.

### <a name="windows-autopilot-deployment-reports----3856172----"></a>Windows Autopilot-implementatierapporten <!-- 3856172  -->
Een nieuw rapport bevat informatie over elk apparaat dat via Windows auto pilot wordt geïmplementeerd. Deze gegevens zijn 30 dagen na de implementatie beschikbaar. Als u het rapport wilt weer geven, gaat u naar **intune**- > **registratie van apparaten** > **monitor** >  auto**pilot-implementaties**.

### <a name="updated-support-experience-------5012398------"></a>Bijgewerkte ondersteunings ervaring   <!--  5012398    -->
Als onderdeel van de voortdurende verbeteringen wordt de ondersteunings ervaring van de console voor intune bijgewerkt.  We verbeteren de zoek opdracht in de console en feedback voor veelvoorkomende problemen en stroom lijnen de werk stroom om contact op te nemen met de ondersteuning.     

<!-- ***********************************************-->
<!--## Security-->


<!-- ***********************************************-->
## <a name="notices"></a>Mededelingen

[!INCLUDE [Intune notices](../includes/intune-notices.md)]

## <a name="see-also"></a>Zie tevens
Zie [Wat is er nieuw in Microsoft Intune?](whats-new.md) voor meer informatie over recente ontwikkelingen.




