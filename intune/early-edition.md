---
title: Vroege editie
description: 
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/24/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7d54cb060dc44d29c95203138396f771abbb2325
ms.sourcegitcommit: 6d69403266dbcb31c879432719798935c94917fa
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/19/2018
---
# <a name="the-early-edition-for-microsoft-intune---february-2018"></a>De vroege editie voor Microsoft Intune - februari 2018

De **vroege editie** bevat een lijst met functies die worden toegevoegd aan toekomstige releases van Microsoft Intune. Deze informatie wordt in beperkte mate verstrekt en kan worden gewijzigd. Deel deze informatie niet buiten uw bedrijf. Sommige functies die hier worden vermeld, zullen mogelijk niet beschikbaar zijn op de sluitingsdatum en worden mogelijk beschikbaar gesteld in een latere release. Andere functies worden getest in een proefversie, zodat we zeker weten dat ze in gebruik kunnen worden genomen. Als u vragen of opmerkingen hebt, kunt contact opnemen met uw contactpersoon voor de Microsoft-productgroep.

Deze pagina wordt regelmatig bijgewerkt. Controleer op andere updates.

> [!Note]
>De volgende wijzigingen worden momenteel ontwikkeld voor Intune. Zie de pagina met [nieuwe hybridefuncties](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) (Engelstalig) voor meer informatie over nieuwe hybridefuncties.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->

## <a name="intune-in-the-azure-portal"></a>Intune in Azure Portal


<!-- 1802 start -->

### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table----1471783---"></a>Nieuwe tabel met fouten bij inschrijving, trendgrafieken en oorzaken van fouten <!-- 1471783 -->

Op de overzichtspagina voor inschrijvingen kunt u de trend van mislukte inschrijvingen en de top vijf van oorzaken van fouten bekijken. Door te klikken op de grafiek of de tabel, kunt u inzoomen op gegevens om advies voor probleemoplossing en suggesties voor herstel te krijgen.

### <a name="prevent-end-users-from-adding-or-removing-accounts-in-the-work-profile----1728700---"></a>Voorkomen dat eindgebruikers accounts in het werkprofiel kunnen toevoegen of uit het werkprofiel kunnen verwijderen <!-- 1728700 -->    
Wanneer u de Gmail-app implementeert in een Android for Work-profiel, kunt u voorkomen dat eindgebruikers accounts aan het werkprofiel toevoegen of uit het werkprofiel verwijderen door de instelling **Accounts toevoegen en verwijderen** te gebruiken in het Android for Work-apparaatrestrictieprofiel.

### <a name="app-protection-policies-----679615---"></a>Beleid voor app-beveiliging <!-- 679615 -->
Via het beveiligingsbeleid voor Intune-apps kunt u algemene standaardbeleidsregels maken om snel beveiliging in te schakelen voor alle gebruikers in de gehele tenant.

### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Intune-ondersteuning voor meerdere Apple DEP-/Apple School Manager-accounts <!-- 747685 -->

Intune ondersteunt de registratie van apparaten uit maximaal 100 verschillende Apple Device Enrollment Program (DEP)- of Apple School Manager-accounts. Elk geüpload token kan afzonderlijk worden beheerd voor registratieprofielen en -apparaten. Er kan automatisch een ander registratieprofiel worden toegewezen per geüpload DEP-/School Manager-token. Als er meerdere School Manager-tokens zijn geüpload, kan er per keer slechts één worden gedeeld met Microsoft School Data Sync.

Na de migratie werken de bèta Graph API's en gepubliceerde scripts voor het beheren van Apple DEP of ASM over Graph niet meer. Nieuwe bèta Graph API's zijn in ontwikkeling en zullen na de migratie worden uitgebracht.

### <a name="windows-defender-health-status-and-threat-status-reports---854704---"></a>Rapporten over de integriteitsstatus en bedreigingsstatus van Windows Defender<!--854704 -->

Inzicht in de integriteit en status van Windows Defender is essentieel voor het beheren van Windows-pc's.  Er worden door Intune nieuwe rapporten en acties toegevoegd aan de status en integriteit van de Windows Defender-agent. Wanneer u een rapport voor het totaliseren van de status gebruikt in de workload voor apparaatcompatibiliteit, worden apparaten weergegeven waarvoor een of meer van de volgende acties moeten worden uitgevoerd:

- het bijwerken van de handtekening
- opnieuw opstarten
- handmatige interventie
- volledige scan
- interventie die is vereist voor andere agentstatussen

In bepaalde gevallen kunnen externe herstelacties worden uitgevoerd, zoals de activering van een handtekeningupdate.  Het rapport geeft ook het aantal pc's aan dat als **schoon** is gerapporteerd.

In een gedetailleerd rapport voor elke statuscategorie worden de afzonderlijke pc's vermeld waarvoor aandacht is vereist of die als **schoon** zijn gerapporteerd.

### <a name="protocol-exceptions-for-applications---1035509-eeready--"></a>Protocoluitzonderingen voor toepassingen <!--1035509 eeready-->

U kunt uitzonderingen maken voor het gegevensoverdrachtbeleid van Intune MAM (Mobile Application Management) om specifieke onbeheerde toepassingen te openen. Dergelijke toepassingen moeten door de IT-afdeling als vertrouwde toepassingen worden beschouwd. Afgezien van de uitzonderingen die u maakt, wordt de gegevensoverdracht nog steeds beperkt tot de toepassingen die door Intune worden beheerd, wanneer uw beleid voor gegevensoverdracht is ingesteld op **uitsluitend beheerde apps**. U kunt de beperkingen maken met behulp van protocollen (iOS) of pakketten (Android).

U kunt bijvoorbeeld het Webex-pakket toevoegen als een uitzondering op het MAM-gegevensoverdrachtbeleid. Op die manier kunnen Webex-koppelingen in een beheerd e-mailbericht van Outlook rechtstreeks in de Webex-toepassing worden geopend. De gegevensoverdracht wordt nog steeds beperkt in andere onbeheerde toepassingen.

### <a name="customize-your-company-portal-themes-with-hex-codes---1049561-eeready--"></a>De bedrijfsportalthema's aanpassen met hexadecimale codes <!--1049561 eeready-->

U kunt de themakleur in de bedrijfsportal-apps aanpassen met behulp van hexadecimale codes. Wanneer u de hexadecimale code invoert, wordt door Intune volgens de [WCAG 2.0-standaarden](http://www.w3.org/TR/WCAG20) bepaald met welke tekstkleur de hoogste mate van contrast tussen de tekstkleur en de achtergrondkleur wordt bereikt. U kunt in **Mobiele apps** > **Bedrijfsportal** bekijken hoe de tekstkleur en uw bedrijfslogo bij deze kleur worden weergegeven. 

### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252---"></a>Er worden nieuwe Windows Defender Credential Guard-instellingen toegevoegd aan de Endpoint Protection-instellingen <!--1102252 --> 

Er worden nieuwe instellingen voor [Windows Defender Credential Guard](https://docs.microsoft.com/nl-nl/windows/access-protection/credential-guard/credential-guard] toegevoegd aan **Apparaatconfiguratie** > **Profielen** > **Endpoint Protection**. De volgende instellingen worden toegevoegd: 

- Platformbeveiligingsniveau: geef aan of het platformbeveiligingsniveau wordt ingeschakeld bij de volgende keer dat de computer wordt opgestart. Bij beveiliging op basis van virtualisatie is beveiligd opstarten vereist. Beveiliging op basis van virtualisatie kan eventueel worden ingeschakeld met behulp van DMA-beveiligingen (Direct Memory Access). Voor DMA-beveiligingen is hardwareondersteuning vereist en deze worden alleen ingeschakeld op apparaten die juist zijn geconfigureerd.
- Beveiliging op basis van virtualisatie: geef aan of beveiliging op basis van virtualisatie wordt ingeschakeld bij de volgende keer dat de computer wordt opgestart. 
- Windows Defender Credential Guard: schakel Credential Guard met beveiliging op basis van virtualisatie in om referenties te kunnen beveiligen bij de volgende keer dat de computer wordt opgestart, wanneer het platformbeveiligingsniveau met beveiligd opstarten en de beveiliging op basis van virtualisatie beide zijn ingeschakeld. U kunt kiezen uit de volgende opties: **Uitgeschakeld**, **Ingeschakeld met UEFI-vergrendeling**, **Ingeschakeld zonder vergrendeling** en **Niet geconfigureerd**. 
  - Met de optie Uitgeschakeld wordt Credential Guard extern uitgeschakeld als deze eerder is ingeschakeld met de optie Ingeschakeld zonder vergrendeling.

  - Bij de optie Ingeschakeld met UEFI-vergrendeling kan Credential Guard niet worden uitgeschakeld met de registersleutel of via Groepsbeleid. Als u Credential Guard wilt uitschakelen nadat deze instelling is gebruikt, moet u het groepsbeleid instellen op Uitgeschakeld en de beveiligingsfunctionaliteit van elke computer, met een fysiek aanwezige gebruiker, verwijderen om de configuratie die is bewaard in UEFI te wissen. Zolang de UEFI-configuratie behouden blijft, is Credential Guard ingeschakeld.

  - Met de optie Ingeschakeld zonder vergrendeling kan Credential Guard extern worden uitgeschakeld via Groepsbeleid. Op de apparaten die gebruikmaken van deze instelling moet ten minste Windows 10 (versie 1511) worden uitgevoerd.

  - Bij de optie Niet geconfigureerd is de beleidsinstelling niet gedefinieerd. De beleidsinstelling wordt door Groepsbeleid niet naar het register weggeschreven en deze heeft dus geen invloed op computers of gebruikers. Als het register een actuele instelling bevat, wordt deze niet gewijzigd.

### <a name="synchronize-and-deploy-sparsely-bundled-windows-store-for-business-apps---1222672---"></a>Spaarzaam gebundelde Windows Store voor Bedrijven-apps synchroniseren en implementeren <!--1222672 -->
Offline apps die worden gekocht in Windows Store voor Bedrijven worden gesynchroniseerd met de Intune-portal. Vervolgens kunt u deze apps implementeren in apparaat- of gebruikersgroepen. Offline apps worden door Intune geïnstalleerd en niet door de Store.

### <a name="reset-passwords-for-android-o-devices----1238299---"></a>Wachtwoorden voor Android O-apparaten opnieuw instellen <!-- 1238299 -->
U kunt de wachtwoorden voor ingeschreven Android O-apparaten opnieuw instellen. Wanneer u een aanvraag Wachtwoord opnieuw instellen naar een Android O-apparaat verzendt, wordt hiermee een nieuw wachtwoord voor het ontgrendelen van het apparaat of een vraag voor het beheerde profiel ingesteld voor de huidige gebruiker. Er wordt een wachtwoord of vraag verzonden, naargelang het apparaat een apparaateigenaar of profieleigenaar heeft. Het wachtwoord of de vraag wordt onmiddellijk van kracht.

### <a name="local-device-security-option-settings----1251887---"></a>Instellingen voor de beveiligingsopties van lokale apparaten <!-- 1251887 -->
U kunt beveiligingsinstellingen op Windows 10-apparaten inschakelen met de nieuwe instellingen voor de beveiligingsopties van lokale apparaten. U vindt deze instellingen in de Endpoint Protection-categorie wanneer u een configuratiebeleid voor Windows 10-apparaten maakt.

### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Nieuwe printerinstellingen voor onderwijsprofielen <!-- 1308900 -->

Er komen voor onderwijsprofielen nieuwe instellingen beschikbaar onder de categorie **Printers**: **Printers**, **Standaardprinter**, **Nieuwe printers toevoegen**. 

### <a name="new-privacy-settings-for-device-restrictions---1308926---"></a>Nieuwe privacyinstellingen voor apparaatbeperkingen <!--1308926 -->

Er komen twee nieuwe privacyinstellingen voor apparaten beschikbaar:

- **Gebruikersactiviteiten publiceren**: stel dit in op **Blokkeren** om gedeelde ervaringen en de detectie van recent gebruikte resources in de taakwisselaar te voorkomen.

- **Alleen lokale activiteiten**: stel dit in op **Blokkeren** om gedeelde ervaringen en de detectie van recent gebruikte resources in de taakwisselaar alleen op basis van de lokale activiteit te voorkomen.

### <a name="macos-company-portal-support-for-enrollments-that-use-the-device-enrollment-manager----1352411---"></a>Ondersteuning van de macOS-bedrijfsportal voor inschrijvingen die gebruikmaken van de apparaatinschrijvingsmanager <!-- 1352411 -->

Gebruikers kunnen de apparaatinschrijvingsmanager gebruiken bij het inschrijven via de macOS-bedrijfsportal.

#### <a name="new-settings-for-the-edge-browser---1469166---"></a>Nieuwe instellingen voor de Microsoft Edge-browser <!--1469166 -->

Er komen twee nieuwe instellingen beschikbaar voor apparaten met de Microsoft Edge-browser: **Pad naar het bestand met favorieten** en **Wijzigingen in Favorieten**. 

### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Versleutelde gegevens van Windows Information Protection (WIP) in zoekresultaten van Windows <!-- 1469193 -->

Met een nieuwe instelling in het WIP-beleid (Windows Information Protection) kunt u zelf regelen of met WIP versleutelde gegevens in de zoekresultaten van Windows worden opgenomen.

### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>Ondersteuning voor LOB-apps (line-of-business) voor macOS <!-- 1473977 -->
Intune biedt de mogelijkheid om LOB-apps voor macOS te installeren. LOB-apps zijn apps waarbij u het installatiebestand levert en u Intune gebruikt om de app op het apparaat te installeren. Als onderdeel van de ondersteuning voor LOB-apps voor macOS moet u de Microsoft Intune App Wrapping Tool voor macOS gebruiken om LOB-apps voor macOS vooraf te verwerken.

### <a name="configure-resource-account-settings-for-surface-hubs----1475674---"></a>Resourceaccountinstellingen voor Surface Hubs configureren <!-- 1475674 -->

U kunt resourceaccountinstellingen voor Surface Hubs extern configureren.

Het resourceaccount wordt door een Surface Hub gebruikt voor verificatie bij Exchange/Skype, zodat kan worden deelgenomen aan een vergadering. U kunt een uniek resourceaccount maken, zodat de Surface Hub in de vergadering kan worden weergegeven als de vergaderruimte. Bijvoorbeeld een resourceaccount als **Vergaderruimte B41/6233**.

> [!NOTE]
> - Als u velden leeg laat, overschrijft u de eerder geconfigureerde kenmerken op het apparaat.
>
> - Resourceaccounteigenschappen kunnen in de Surface Hub dynamisch worden gewijzigd. Bijvoorbeeld als wisseling van het wachtwoord is ingeschakeld. Het is dus mogelijk dat de waarden in de Azure-console pas na enige tijd in overeenstemming zijn met de waarden op het apparaat. 
>
>   Om te weten wat er op dat moment op de Surface Hub is geconfigureerd, kunnen de resourceaccountgegevens in de hardware-inventaris (die al een interval van zeven dagen heeft) of als alleen-lezen eigenschappen worden opgenomen. Voor een grotere nauwkeurigheid na de uitvoering van de externe actie kunt u de status van de parameters onmiddellijk na het uitvoeren van de actie ophalen om het account/de parameters op de Surface Hub bij te werken.

### <a name="ios-app-provisioning-configuration----1581650---"></a>Inrichtingsconfiguratie voor iOS-apps <!-- 1581650 -->
U kunt inrichtingsprofielen voor iOS-apps toewijzen om te voorkomen dat uw apps verlopen door beveiligingsgroepen op te nemen of uit te sluiten.

### <a name="new-windows-defender-exploit-guard-settings----631893---"></a>Nieuwe instellingen voor Windows Defender Exploit Guard <!-- 631893 -->

Er komen zes nieuwe instellingen voor **Kwetsbaarheid voor aanvallen verminderen** en uitgebreide mogelijkheden voor **Gecontroleerde mappentoegang: mapbeveiliging** beschikbaar. Deze instellingen kunt u vinden op: Apparaatconfiguratie\Profielen\
Profiel maken\Endpoint Protection\Windows Defender Exploit Guard.

#### <a name="attack-surface-reduction"></a>Kwetsbaarheid voor aanvallen verminderen

|Naam van de instelling  |Instellingsopties  |Description  |
|---------|---------|---------|
|Geavanceerde ransomwarebeveiliging|Ingeschakeld, Controleren, Niet geconfigureerd|Gebruik agressieve ransomwarebeveiliging.|
|Referentiediefstal in het Windows-subsysteem voor de lokale beveiligingsautoriteit markeren|Ingeschakeld, Controleren, Niet geconfigureerd|Markeer referentiediefstal in het Windows-subsysteem voor de lokale beveiligingsautoriteit (lsass.exe).|
|Het maken van processen met PSExec- en WMI-opdrachten|Blokkeren, Controleren, Niet geconfigureerd|Blokkeer het maken van processen die afkomstig zijn van PSExec- en WMI-opdrachten.|
|Niet-vertrouwde en niet-ondertekende processen die worden uitgevoerd vanaf een USB|Blokkeren, Controleren, Niet geconfigureerd|Blokkeer niet-vertrouwde en niet-ondertekende processen die worden uitgevoerd vanaf een USB.|
|Uitvoerbare bestanden die niet voldoen aan een bepaalde gangbaarheid, ouderdom of aan criteria voor vertrouwde lijsten blokkeren|Blokkeren, Controleren, Niet geconfigureerd|Voorkomen dat uitvoerbare bestanden worden uitgevoerd tenzij deze voldoen aan een bepaalde gangbaarheid, ouderdom of criteria voor vertrouwde lijsten.|

#### <a name="controlled-folder-access"></a>Gecontroleerde mappentoegang

|Naam van de instelling  |Instellingsopties  |Description  |
|---------|---------|---------|
|Mapbeveiliging (al geïmplementeerd)|Niet geconfigureerd, Inschakelen, Alleen controleren (al geïmplementeerd)<br><br> **Nieuw**<br>Schijfwijziging blokkeren, schijfwijziging controleren|
Beveilig bestanden en mappen tegen niet-geautoriseerde wijzigingen door niet-goedgekeurde apps.<br><br>**Inschakelen**: voorkom dat bestanden in beveiligde mappen door niet-vertrouwde apps worden gewijzigd of verwijderd en dat gegevens door deze apps naar schijfsectoren worden weggeschreven.<br><br>
**Alleen schijfwijziging blokkeren**:<br>Voorkom dat gegevens door niet-vertrouwde apps worden weggeschreven naar schijfsectoren. Bestanden in beveiligde mappen kunnen nog steeds door niet-vertrouwde apps worden gewijzigd of verwijderd.|

### <a name="new-windows-defender-application-guard-settings----1631890---"></a>Nieuwe instellingen voor Windows Defender Application Guard <!-- 1631890 -->

- **Grafische versnelling inschakelen**

Beheerders kunnen voortaan een virtuele grafische processor inschakelen voor Windows Defender Application Guard. Met deze instelling kan de CPU taken voor de grafische weergave overdragen aan de vGPU. Dit kan de prestaties verbeteren wanneer u met websites werkt die veeleisende grafische weergaven bevatten of een video in de container bekijkt.

- **SaveFilestoHost**

Beheerders kunnen ervoor zorgen dat bestanden worden doorgegeven van Microsoft Edge, die in de container wordt uitgevoerd, naar het hostbestandsysteem. Wanneer u deze optie inschakelt, kunnen gebruikers bestanden uit Microsoft Edge in de container downloaden naar het hostbestandsysteem.

### <a name="see-enrollment-restrictions-per-user----1634444---"></a>Inschrijvingsbeperkingen per gebruiker bekijken <!-- 1634444 -->
Op de blade voor probleemoplossing kunt u de inschrijvingsbeperkingen bekijken die voor elke gebruiker van kracht zijn.

### <a name="configuring-a-self-updating-mobile-msi-app----1740840---"></a>Een mobiele MSI-app configureren die automatisch wordt bijgewerkt <!-- 1740840 -->
U kunt een bekende mobiele MSI-app die automatisch wordt bijgewerkt zo configureren dat de versiecontrole wordt genegeerd. Met deze functie kunt u voorkomen dat er een racevoorwaarde optreedt. Dit kan bijvoorbeeld gebeuren wanneer de app automatisch wordt bijgewerkt door zowel de ontwikkelaar van de app als Intune. Er kan door beide worden geprobeerd om een versie van de app op de Windows-client af te dwingen, waardoor een conflict kan ontstaan.

### <a name="additions-to-system-security-settings-for-windows-10-and-later-compliance-policies---1704133---"></a>Toevoegingen aan systeembeveiligingsinstellingen voor nalevingsbeleid voor Windows 10 en hoger <!--1704133 -->

Toevoegingen aan de nalevingsinstellingen voor Windows 10 komen beschikbaar, waaronder het verplichte gebruik van een firewall en Windows Defender Antivirus.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise----1813081---"></a>App-toewijzing op basis van groepen opnemen en uitsluiten voor Android Enterprise <!-- 1813081 -->
Tijdens de app-toewijzing en na het selecteren van een toewijzingstype biedt Android Enterprise (voorheen bekend als Android for Work) ondersteuning voor het uitsluiten van functionaliteit.


### <a name="related-sets-of-app-licenses-supported-in-intune----1864117---"></a>Gerelateerde groepen van app-licenties worden in Intune ondersteund <!-- 1864117 -->
Intune in Azure Portal biedt ondersteuning voor de vermelding van gerelateerde groepen van app-licenties als één app-item in de gebruikersinterface. Bovendien worden apps met offlinelicenties die zijn gesynchroniseerd vanuit Microsoft Store voor Bedrijven geconsolideerd in één app-vermelding. Eventuele implementatiegegevens uit de afzonderlijke pakketten worden naar die ene vermelding gemigreerd. Als u gerelateerde groepen van app-licenties in Azure Portal wilt bekijken, selecteert u **App-licenties** op de blade **Mobiele apps**.

<!-- the following are present prior to 1802 -->

### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625---"></a>Nieuwe optie voor gebruikersverificatie voor bulkinschrijving met Apple <!-- 747625 -->
Intune biedt voor de volgende registratiemethoden de optie om apparaten te verifiëren met behulp van de bedrijfsportal-app:

- Apple Device Enrollment Program
- Apple School Manager
- Apple Configurator Enrollment

Wanneer u de bedrijfsportal-optie gebruikt, kan meervoudige verificatie van Azure Active Directory worden afgedwongen zonder deze registratiemethoden te blokkeren.

Wanneer u de bedrijfsportal-optie gebruikt, slaat Intune verificatie van gebruikers in de iOS-configuratieassistent over voor registratie op basis van gebruikersaffiniteit. Dit betekent dat het apparaat in eerste instantie wordt geregistreerd als een apparaat zonder gebruiker en derhalve geen configuraties of beleid van gebruikersgroepen ontvangt. Het apparaat ontvangt alleen configuraties en beleid voor apparaatgroepen. Intune installeert echter automatisch de bedrijfsportal-app op het apparaat. De eerste gebruiker die de bedrijfsportal-app start en zich aanmeldt, wordt in Intune aan het apparaat gekoppeld. Op dat punt ontvangt de gebruiker configuraties en beleid van zijn of haar gebruikersgroepen. De koppeling met de gebruiker kan niet worden gewijzigd zonder opnieuw te registreren.

### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Intune-ondersteuning voor meerdere Apple DEP-/Apple School Manager-accounts <!-- 747685 -->
Intune ondersteunt de registratie van apparaten uit maximaal 100 verschillende Apple Device Enrollment Program (DEP)- of Apple School Manager-accounts. Elk geüpload token kan afzonderlijk worden beheerd voor registratieprofielen en -apparaten. Er kan automatisch een ander registratieprofiel worden toegewezen per geüpload DEP-/School Manager-token. Als er meerdere School Manager-tokens zijn geüpload, kan er per keer slechts één worden gedeeld met Microsoft School Data Sync.

Na de migratie werken de bèta Graph API's en gepubliceerde scripts voor het beheren van Apple DEP of ASM over Graph niet meer. Nieuwe bèta Graph API's zijn in ontwikkeling en zullen na de migratie worden uitgebracht.

### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963---"></a>Apparaatcategorieën selecteren met behulp van de instellingen voor Toegang tot werk of school <!-- 1058963 -->
Als u [apparaatgroeptoewijzing](https://docs.microsoft.com/intune/device-group-mapping) hebt ingeschakeld, wordt gebruikers van Windows 10 gevraagd een apparaatcategorie te selecteren na registratie via de knop **Verbinding maken** in **Instellingen**  >  **Accounts** > **Toegang tot werk of school** of tijdens de standaardprocedure.

### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Nalevingsbeleid afstemmen op apparaten in apparaatgroepen <!--1307012 -->

U kunt nalevingsbeleid richten op gebruikers in gebruikersgroepen. U kunt nalevingsbeleid richten op apparaten in apparaatgroepen.

### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Versleutelde gegevens van Windows Information Protection (WIP) in zoekresultaten van Windows <!-- 1469193 -->

Met een nieuwe instelling in het WIP-beleid (Windows Information Protection) kunt u zelf regelen of met WIP versleutelde gegevens in de zoekresultaten van Windows worden opgenomen.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>Extern afdrukken via een beveiligd netwerk <!-- 1709994  -->
Met de oplossingen voor draadloos mobiel afdrukken van PrinterOn kunnen gebruikers op afstand vanaf elke locatie en op elk gewenst moment afdrukken via een beveiligd netwerk. PrinterOn wordt geïntegreerd met de Intune APP SDK voor zowel iOS als Android. U kunt app-beveiligingsbeleid toepassen op deze app via de Intune-blade **App-beveiligingsbeleid** in de beheerconsole. Eindgebruikers kunnen de app 'PrinterOn for Microsoft' downloaden via de Play Store of iTunes voor gebruik binnen hun Intune-ecosysteem.



### <a name="microsoft-graph-api-for-intune---general-availability-----1833289---"></a>Microsoft Graph API voor Intune - algemene beschikbaarheid <!-- 1833289 -->
Intune API's in Microsoft Graph bieden programmatisch toegang tot gegevens en methoden voor het automatiseren van beheertaken voor de Intune-service.  Met de **Algemene beschikbaarheid** van deze API's kunnen klanten, partners en ontwikkelaars de API's gebruiken voor integratie met interne of commerciële oplossingen die betrekking hebben op of de ondersteuning nodig hebben van Intune of andere Microsoft-services die beschikbaar zijn via Microsoft Graph.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Beleid voor app-beveiliging <!-- 679615 -->
Via het beveiligingsbeleid voor Intune-apps kunt u algemene standaardbeleidsregels maken om snel beveiliging in te schakelen voor alle gebruikers in de gehele tenant.

### <a name="new-ios-device-action------1244701---"></a>Nieuwe actie voor iOS-apparaten <!-- 1244701 -->
U kunt door iOS 10.3 gecontroleerde apparaten afsluiten. Deze actie sluit het apparaat direct af zonder waarschuwing voor de eindgebruiker. U vindt de actie **Afsluiten (alleen gecontroleerd)** in de apparaateigenschappen wanneer u een apparaat selecteert in de werkbelasting **Apparaat**.

### <a name="intune-provides-the-account-move-operation-----1573558-1579830---"></a>U beschikt in Intune nu over de bewerking Account verplaatsen <!-- 1573558, 1579830 -->
**Account verplaatsen** migreert een tenant van de ene ASU (Azure Scale Unit) naar een andere. **Account verplaatsen** kan worden gebruikt voor door de klant geïnitieerde scenario's, wanneer u het Intune-ondersteuningsteam belt om dit aan te vragen en in een door Microsoft aangestuurd scenario waarin Microsoft aan de back-end wijzigingen moet aanbrengen in de service. Tijdens de **accountverplaatsing** wordt voor de tenant de modus alleen-lezen (ROM) geactiveerd. Servicebewerkingen zoals inschrijven, de naam van apparaten wijzigen of de nalevingsstatus bijwerken mislukken tijdens de ROM-periode.

De wijziging doet iets aan de verwarring wanneer één app is toegewezen aan meerdere groepen met verschillende app-intents.

Als u graag wilt dat uw app beschikbaar wordt in de portal voor informatiemedewerkers en het bedrijfsportal vóór de servicerelease van november, hebt u twee opties:

1. Verwijder de toewijzing **Niet van toepassing** voor uw groep.
2. Maak een nieuwe groep die geen leden bevat met een toegewezen intent **Vereist en Beschikbaar** en wijs die groep aan als **Niet van toepassing**.

Zie [Apps aan groepen toewijzen](apps-deploy.md) voor meer informatie.

> [!Note]
> Na de release kunt u de toewijzingen van Mobile Device Management (MDM)-apps niet meer weergeven of wijzigen in de klassieke Intune-console. U kunt echter met de Azure-console of de Graph API van Intune toewijzingen van uw app maken.

### <a name="configure-an-ios-app-pin----1586774---"></a>Een pincode voor een iOS-app configureren <!-- 1586774 -->
U kunt binnenkort een pincode vereisen voor de betreffende iOS-apps. U kunt de vereisten voor de pincode en de vervaldatum in dagen via Azure Portal configureren. Indien vereist,wordt een gebruiker verplicht om een nieuwe pincode in te stellen en te gebruiken voordat deze toegang krijgt tot een iOS-app. Alleen iOS-apps met een app-beveiliging die is ingeschakeld met de Intune App SDK ondersteunen deze functie.

### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866--"></a>Update van de gebruikerservaring voor de bedrijfsportal-app voor iOS<!--1412866-->

We zullen een grote update uitbrengen van de gebruikerservaring voor de bedrijfsportal-app voor iOS. De update heeft een volledig nieuw visueel ontwerp, waaronder een gemoderniseerde uitstraling met verbeterde bruikbaarheid en toegankelijkheid. De huidige functionaliteit van de iOS-bedrijfsportal-app blijft behouden.

We bieden een voorlopige versie van de bijgewerkte bedrijfsportal-app voor iOS via het Apple TestFlight-programma. U kunt deze versie gebruiken en uw feedback geven. Meld u aan bij https://aka.ms/intune_ios_cp_testflight voor toegang tot TestFlight. 

![teaserafbeeldingen voor de nieuwe iOS-bedrijfsportal-app](./media/ios-cp-app-redesign-1801-teaser.png)

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Azure Active Directory-websites kunnen de Intune Managed Browser-app vereisen en ondersteunen eenmalige aanmelding voor de Managed Browser (openbare preview) <!-- 710595 -->   
Met Azure Active Directory (Azure AD) kunt u de toegang tot websites op mobiele apparaten beperken tot de Intune Managed Browser-app. In de Managed Browser blijven websitegegevens veilig en gescheiden van de persoonlijke gegevens van eindgebruikers. Daarnaast ondersteunt de Managed Browser eenmalige aanmelding voor sites die door Azure AD worden beveiligd. Door u aan te melden bij de Managed Browser of door de Managed Browser op een apparaat te gebruiken met een andere app die door Intune wordt beheerd, krijgt de Managed Browser toegang tot bedrijfssites die door Azure AD worden beveiligd, zonder dat de gebruiker referenties hoeft in te voeren. Deze functionaliteit is van toepassing op sites zoals Outlook Web Access (OWA) en SharePoint Online, evenals andere bedrijfssites zoals intranetbronnen die via de Azure App Proxy worden geopend.

<!-- the following are present prior to 1709 -->
### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Hulpmiddelen voor Intune-app-beveiliging en Citrix MDX <!-- 709185 -->
U kunt apparaten en apps beheren met een combinatie van Citrix XenMobile MDX en Microsoft Intune. Hierdoor kunt u apps beheren met het Intune-beveiligingsbeleid voor apps met behulp van de mVPN-technologie van Citrix.

U kunt een opslagplaats voor codes vinden met de Intune App Wrapping Tool en Intune App SDK voor iOS en Android, die integreren met Citrix MDX mVPN-technologie.

<!-- the following are present prior to 1711 -->

### <a name="redirecting-macos-users-to-the-new-company-portal-app---1380728--"></a>MacOS-gebruikers omleiden naar de nieuwe bedrijfsportal-app <!--1380728-->   
Wanneer eindgebruikers zich aanmelden bij de bedrijfsportalwebsite om hun macOS-apparaten in te schrijven, worden ze gevraagd de nieuwe bedrijfsportal-app voor macOS te downloaden om het proces te voltooien. Dit gebeurt voor macOS-apparaten waarop OS X El Capitan 10.11 of hoger wordt uitgevoerd. 

<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Ondersteuning van Intune Managed Browser voor iOS en Android <!-- 1374196 -->
Vanaf oktober 2017 ondersteunt de app Intune Managed Browser voor Android alleen nog apparaten waarop Android 4.4 en hoger wordt uitgevoerd. De app Intune Managed Browser voor iOS ondersteunt alleen apparaten met iOS 9.0 en hoger. Oudere versies van Android en iOS kunnen Managed Browser nog steeds gebruiken, maar er kunnen geen nieuwe versies van de app op worden geïnstalleerd en kan er dus geen gebruik worden gemaakt van alle mogelijkheden van de app. U wordt aangeraden deze apparaten bij te werken tot een ondersteunde versie van het besturingssysteem.

### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Verbeterd foutbericht als een gebruiker het maximum aantal apparaten bereikt dat mag worden ingeschreven <!-- 1270370 -->
In plaats van een algemeen foutbericht krijgen eindgebruikers van Androis-apparaten een gebruikersvriendelijk foutbericht te zien waarop een actie kan worden uitgevoerd: 'U hebt het maximum aantal apparaten ingeschreven dat door de IT-beheerder is toegestaan. Verwijder een ingeschreven apparaat of vraag assistentie van uw IT-beheerder.'



## <a name="notices"></a>Mededelingen

Er zijn geen actieve meldingen op dit moment.



### <a name="see-also"></a>Zie ook
Zie [Wat is er nieuw in Microsoft Intune?](whats-new.md) voor meer informatie over recente ontwikkelingen.


