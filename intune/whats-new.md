---
title: Wat is er nieuw in Microsoft Intune?
titlesuffix: 
description: Ontdekken wat er nieuw is in Intune Azure Portal
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 01/02/2018
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 513164a1f734fddb6ac66fcaffdc2fb885a4659a
ms.sourcegitcommit: 9cf05d3cb8099e4a238dae9b561920801ad5cdc6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/09/2018
---
# <a name="whats-new-in-microsoft-intune"></a>Wat is er nieuw in Microsoft Intune?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ontdek elke week wat er nieuw is in Microsoft Intune. U vindt hier ook informatie over [toekomstige wijzigingen](#whats-coming), [belangrijke kennisgevingen](#notices) betreffende de service en informatie over [oudere releases](whats-new-archive.md).

> [!Note]
> Zie de [pagina Wat is er nieuw](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) voor informatie over nieuwe functionaliteit in het hybride beheer van mobiele apparaten (MDM).


<!-- Common categories:  
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
  ### Role-based access control
  ### Intune apps
  ### Monitor and troubleshoot

-->   


## <a name="week-of-february-19-2018"></a>Week van 19 februari 2018
### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Intune-ondersteuning voor meerdere Apple DEP-/Apple School Manager-accounts <!-- 747685 -->
 
Intune ondersteunt nu de registratie van apparaten uit maximaal 100 verschillende Apple Device Enrollment Program (DEP)- of Apple School Manager-accounts. Elk geüpload token kan afzonderlijk worden beheerd voor registratieprofielen en -apparaten. Er kan automatisch een ander registratieprofiel worden toegewezen per geüpload DEP-/School Manager-token. Als er meerdere School Manager-tokens zijn geüpload, kan er per keer slechts één worden gedeeld met Microsoft School Data Sync.

Na de migratie werken de bèta Graph API's en gepubliceerde scripts voor het beheren van Apple DEP of ASM over Graph niet meer. Nieuwe bèta Graph API's zijn in ontwikkeling en zullen na de migratie worden uitgebracht.

#### <a name="see-enrollment-restrictions-per-user----1634444-eeready-wnready---"></a>Inschrijvingsbeperkingen per gebruiker bekijken <!-- 1634444 eeready wnready -->
Op de blade **Probleemoplossing** kunt u nu de inschrijvingsbeperkingen bekijken die gelden voor elke gebruiker. Selecteer hiervoor **Inschrijvingsbeperkingen** in de lijst **Toewijzingen**.

### <a name="device-management"></a>Apparaatbeheer
#### <a name="windows-defender-health-status-and-threat-status-reports---854704---"></a>Rapporten over de integriteitsstatus en bedreigingsstatus van Windows Defender<!--854704 -->

Inzicht in de integriteit en status van Windows Defender is essentieel voor het beheren van Windows-pc's.  Dankzij deze update worden door Intune nieuwe rapporten en acties toegevoegd aan de status en integriteit van de Windows Defender-agent. Wanneer u een rapport voor het verzamelen van de status gebruikt in de workload voor apparaatcompatibiliteit, worden apparaten weergegeven waarvoor een of meer van de volgende acties moeten worden uitgevoerd:
- het bijwerken van de handtekening
- Opnieuw opstarten
- handmatige interventie
- volledige scan
- interventie die is vereist voor andere agentstatussen

In een gedetailleerd rapport voor elke statuscategorie worden de afzonderlijke pc's vermeld waarvoor aandacht is vereist of die als **schoon** zijn gerapporteerd.

#### <a name="new-privacy-settings-for-device-restrictions---1308926---"></a>Nieuwe privacyinstellingen voor apparaatbeperkingen <!--1308926 -->
Er zijn twee nieuwe privacyinstellingen voor apparaten beschikbaar:
- **Gebruikersactiviteiten publiceren**: stel dit in op **Blokkeren** om gedeelde ervaringen en de detectie van recent gebruikte resources in de taakwisselaar te voorkomen.
- **Alleen lokale activiteiten**: stel dit in op **Blokkeren** om gedeelde ervaringen en de detectie van recent gebruikte resources in de taakwisselaar alleen op basis van de lokale activiteit te voorkomen.

#### <a name="new-settings-for-the-edge-browser---1469166---"></a>Nieuwe instellingen voor de Microsoft Edge-browser <!--1469166 -->
Er zijn twee nieuwe instellingen beschikbaar voor apparaten met de Microsoft Edge-browser: **Pad naar het bestand met favorieten** en **Wijzigingen in Favorieten**. 

### <a name="app-management"></a>Appbeheer
#### <a name="protocol-exceptions-for-applications---1035509---"></a>Protocoluitzonderingen voor toepassingen <!--1035509 -->

U kunt nu uitzonderingen maken voor het gegevensoverdrachtbeleid van Intune MAM (Mobile Application Management) om specifieke onbeheerde toepassingen te openen. Dergelijke toepassingen moeten door de IT-afdeling als vertrouwde toepassingen worden beschouwd. Afgezien van de uitzonderingen die u maakt, wordt de gegevensoverdracht nog steeds beperkt tot de toepassingen die door Intune worden beheerd als uw beleid voor gegevensoverdracht is ingesteld op **Uitsluitend beheerde apps**. U kunt de beperkingen maken met behulp van protocollen (iOS) of pakketten (Android).
 
U kunt bijvoorbeeld het Webex-pakket toevoegen als een uitzondering op het MAM-gegevensoverdrachtbeleid. Op die manier kunnen Webex-koppelingen in een beheerd e-mailbericht van Outlook rechtstreeks in de Webex-toepassing worden geopend. De gegevensoverdracht wordt nog steeds beperkt in andere onbeheerde toepassingen. Zie [Uitzonderingen voor gegevensoverdrachtsbeleid voor apps](app-protection-policies-exception.md) voor meer informatie.

#### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Versleutelde gegevens van Windows Information Protection (WIP) in zoekresultaten van Windows <!-- 1469193 -->
Met een instelling in het WIP-beleid (Windows-gegevensbescherming) kunt u zelf regelen of met WIP versleutelde gegevens in de zoekresultaten van Windows worden opgenomen. Stel deze optie voor app-beveiligingsbeleid in door de optie **Windows Search-indexeerfunctie toestaan om versleutelde items te zoeken** te selecteren in de **geavanceerde instellingen** van het Windows-gegevensbeschermingsbeleid. Het beveiligingsbeleid van de app moet worden ingesteld op het *Windows 10*-platform en de **inschrijvingsstatus** van het app-beleid moet worden ingesteld op **Bij inschrijving**. Zie [De Windows Search-indexeerfunctie toestaan om versleutelde items te zoeken](windows-information-protection-policy-create.md#allow-windows-search-indexer-to-search-encrypted-items) voor meer informatie.

#### <a name="configuring-a-self-updating-mobile-msi-app----1740840---"></a>Een mobiele MSI-app configureren die automatisch wordt bijgewerkt <!-- 1740840 -->
U kunt een bekende mobiele MSI-app die automatisch wordt bijgewerkt configureren om de versiecontrole te negeren. Met deze functie kunt u voorkomen dat er een racevoorwaarde optreedt. Dit type racevoorwaarde kan bijvoorbeeld optreden wanneer de app die automatisch wordt bijgewerkt door de app-ontwikkelaar ook wordt bijgewerkt door Intune. Er kan door beide partijen worden geprobeerd om een versie van de app op een Windows-client af te dwingen, waardoor een conflict kan ontstaan. Voor deze automatisch bijgewerkte MSI-apps kunt u de instelling **App-versie negeren** in de blade **App-informatie** configureren. Wanneer deze instelling op **Ja** staat, negeert Microsoft Intune de app-versie die is geïnstalleerd op de Windows-client. 

#### <a name="related-sets-of-app-licenses-supported-in-intune----1864117---"></a>Gerelateerde groepen van app-licenties worden in Intune ondersteund <!-- 1864117 -->
Intune in Azure Portal biedt nu ondersteuning voor de vermelding van gerelateerde groepen van app-licenties als één app-item in de gebruikersinterface. Bovendien worden apps met offlinelicenties die zijn gesynchroniseerd vanuit Microsoft Store voor Bedrijven geconsolideerd in één app-vermelding. Eventuele implementatiegegevens uit de afzonderlijke pakketten worden naar die ene vermelding gemigreerd. Als u gerelateerde groepen van app-licenties in Azure Portal wilt bekijken, selecteert u **App-licenties** op de blade **Mobiele apps**.

### <a name="device-configuration"></a>Apparaatconfiguratie
#### <a name="windows-information-protection-wip-file-extensions-for-automatic-encryption----1463582---"></a>Bestandsextensies voor automatische versleuteling door Windows-gegevensbescherming (WIP) <!-- 1463582 -->
Met een instelling in het Windows-gegevensbeschermingsbeleid (WIP) kunt u nu opgeven welke bestandsextensies automatisch worden versleuteld bij het kopiëren vanaf een Server Message Block-share (SMB) binnen het bedrijf, zoals gedefinieerd in het WIP-beleid.

#### <a name="configure-resource-account-settings-for-surface-hubs"></a>Resourceaccountinstellingen voor Surface Hubs configureren

U kunt nu resourceaccountinstellingen voor Surface Hubs extern configureren.

Het resourceaccount wordt door een Surface Hub gebruikt voor verificatie bij Exchange/Skype, zodat kan worden deelgenomen aan een vergadering. U kunt een uniek resourceaccount maken, zodat de Surface Hub in de vergadering kan worden weergegeven als de vergaderruimte. Bijvoorbeeld een resourceaccount als **Vergaderruimte B41/6233**.

> [!NOTE]
> - Als u velden leeg laat, overschrijft u de eerder geconfigureerde kenmerken op het apparaat.
>
> - Resourceaccounteigenschappen kunnen in de Surface Hub dynamisch worden gewijzigd. Bijvoorbeeld als wisseling van het wachtwoord is ingeschakeld. Het is dus mogelijk dat de waarden in de Azure-console pas na enige tijd in overeenstemming zijn met de waarden op het apparaat. 
>
>   Om te weten wat er op dat moment op de Surface Hub is geconfigureerd, kunnen de resourceaccountgegevens in de hardware-inventaris (die al een interval van zeven dagen heeft) of als alleen-lezen eigenschappen worden opgenomen. Voor een grotere nauwkeurigheid na de uitvoering van de externe actie kunt u de status van de parameters onmiddellijk na het uitvoeren van de actie ophalen om het account/de parameters op de Surface Hub bij te werken.


##### <a name="attack-surface-reduction"></a>Kwetsbaarheid voor aanvallen verminderen


|Naam van de instelling  |Instellingsopties  |Description  |
|---------|---------|---------|
|Uitvoering van met een wachtwoord beschermde uitvoerbare inhoud uit e-mails|Blokkeren, Controleren, Niet geconfigureerd|Voorkom dat uitvoerbare bestanden met wachtwoordbescherming uit e-mails worden uitgevoerd.|
|Geavanceerde ransomwarebeveiliging|Ingeschakeld, Controleren, Niet geconfigureerd|Gebruik agressieve ransomwarebeveiliging.|
|Referentiediefstal in het Windows-subsysteem voor de lokale beveiligingsautoriteit markeren|Ingeschakeld, Controleren, Niet geconfigureerd|Markeer referentiediefstal in het Windows-subsysteem voor de lokale beveiligingsautoriteit (lsass.exe).|
|Het maken van processen met PSExec- en WMI-opdrachten|Blokkeren, Controleren, Niet geconfigureerd|Blokkeer het maken van processen die afkomstig zijn van PSExec- en WMI-opdrachten.|
|Niet-vertrouwde en niet-ondertekende processen die worden uitgevoerd vanaf een USB|Blokkeren, Controleren, Niet geconfigureerd|Blokkeer niet-vertrouwde en niet-ondertekende processen die worden uitgevoerd vanaf een USB.|
|Uitvoerbare bestanden die niet voldoen aan een bepaalde gangbaarheid, ouderdom of aan criteria voor vertrouwde lijsten blokkeren|Blokkeren, Controleren, Niet geconfigureerd|Voorkomen dat uitvoerbare bestanden worden uitgevoerd tenzij deze voldoen aan een bepaalde gangbaarheid, ouderdom of criteria voor vertrouwde lijsten.|

##### <a name="controlled-folder-access"></a>Gecontroleerde mappentoegang

|Naam van de instelling  |Instellingsopties  |Description  |
|---------|---------|---------|
|Mapbeveiliging (al geïmplementeerd)|Niet geconfigureerd, Inschakelen, Alleen controleren (al geïmplementeerd)<br><br> **Nieuw**<br>Schijfwijziging blokkeren, schijfwijziging controleren|
Beveilig bestanden en mappen tegen niet-geautoriseerde wijzigingen door niet-goedgekeurde apps.<br><br>**Inschakelen**: voorkom dat bestanden in beveiligde mappen door niet-vertrouwde apps worden gewijzigd of verwijderd en dat gegevens door deze apps naar schijfsectoren worden weggeschreven.<br><br>
**Alleen schijfwijziging blokkeren**:<br>Voorkom dat gegevens door niet-vertrouwde apps worden weggeschreven naar schijfsectoren. Bestanden in beveiligde mappen kunnen nog steeds door niet-vertrouwde apps worden gewijzigd of verwijderd.|

#### <a name="additions-to-system-security-settings-for-windows-10-and-later-compliance-policies---1704133--"></a>Toevoegingen aan systeembeveiligingsinstellingen voor nalevingsbeleid voor Windows 10 en hoger <!--1704133-->

Toevoegingen aan de nalevingsinstellingen voor Windows 10 zijn nu beschikbaar, waaronder het verplichte gebruik van een firewall en Windows Defender Antivirus. 


### <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer
### <a name="intune-apps"></a>Intune-apps
#### <a name="support-for-offline-apps-from-the-microsoft-store-for-business---1222672--"></a>Ondersteuning voor offlineapps uit Microsoft Store voor Bedrijven <!--1222672-->
Offlineapps die u hebt gekocht in Microsoft Store voor Bedrijven worden voortaan gesynchroniseerd met Azure Portal. Vervolgens kunt u deze apps implementeren in apparaat- of gebruikersgroepen. Offlineapps worden geïnstalleerd door Intune en niet door de Store.

#### <a name="prevent-end-users-from-manually-adding-or-removing-accounts-in-the-work-profile----1728700---"></a>Hiermee voorkomt u dat eindgebruikers handmatig accounts in het werkprofiel kunnen toevoegen of uit het werkprofiel kunnen verwijderen <!-- 1728700 -->

Wanneer u de Gmail-app implementeert in een Android for Work-profiel, kunt u voorkomen dat eindgebruikers accounts handmatig aan het werkprofiel toevoegen of uit het werkprofiel verwijderen door de instelling **Accounts toevoegen en verwijderen** te gebruiken in het Android for Work-apparaatbeperkingsprofiel.

## <a name="week-of-february-5-2018"></a>Week van 5 februari 2018

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625-eeready---"></a>Nieuwe optie voor gebruikersverificatie voor bulkinschrijving met Apple <!-- 747625 eeready -->

> [!NOTE]
> Voor nieuwe tenants is deze nieuwe optie direct beschikbaar. Voor bestaande tenants wordt deze functie in april geïmplementeerd. Zolang deze implementatie nog niet is voltooid, hebt u mogelijk geen toegang tot deze nieuwe functies.

Intune biedt voor de volgende registratiemethoden de optie om apparaten te verifiëren met behulp van de bedrijfsportal-app:

- Apple Device Enrollment Program
- Apple School Manager
- Apple Configurator Enrollment

Wanneer u de bedrijfsportal-optie gebruikt, kan meervoudige verificatie van Azure Active Directory worden afgedwongen zonder deze registratiemethoden te blokkeren.

Wanneer u de bedrijfsportal-optie gebruikt, slaat Intune verificatie van gebruikers in de iOS-configuratieassistent over voor registratie op basis van gebruikersaffiniteit. Dit betekent dat het apparaat in eerste instantie wordt geregistreerd als een apparaat zonder gebruiker en derhalve geen configuraties of beleid van gebruikersgroepen ontvangt. Het apparaat ontvangt alleen configuraties en beleid voor apparaatgroepen. Intune installeert echter automatisch de bedrijfsportal-app op het apparaat. De eerste gebruiker die de bedrijfsportal-app start en zich aanmeldt, wordt in Intune aan het apparaat gekoppeld. Op dat punt ontvangt de gebruiker configuraties en beleid van zijn of haar gebruikersgroepen. De koppeling met de gebruiker kan niet worden gewijzigd zonder opnieuw te registreren.

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685-eeready---"></a>Intune-ondersteuning voor meerdere Apple DEP-/Apple School Manager-accounts <!-- 747685 eeready -->

Intune ondersteunt nu de registratie van apparaten uit maximaal 100 verschillende Apple Device Enrollment Program (DEP)- of Apple School Manager-accounts. Elk geüpload token kan afzonderlijk worden beheerd voor registratieprofielen en -apparaten. Er kan automatisch een ander registratieprofiel worden toegewezen per geüpload DEP-/School Manager-token. Als er meerdere School Manager-tokens zijn geüpload, kan er per keer slechts één worden gedeeld met Microsoft School Data Sync.

Na de migratie werken de bèta Graph API's en gepubliceerde scripts voor het beheren van Apple DEP of ASM over Graph niet meer. Nieuwe bèta Graph API's zijn in ontwikkeling en zullen na de migratie worden uitgebracht.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>Extern afdrukken via een beveiligd netwerk <!-- 1709994  -->
Met de oplossingen voor draadloos mobiel afdrukken van PrinterOn kunnen gebruikers op afstand vanaf elke locatie en op elk gewenst moment afdrukken via een beveiligd netwerk. PrinterOn wordt geïntegreerd met de Intune APP SDK voor zowel iOS als Android. U kunt app-beveiligingsbeleid toepassen op deze app via de Intune-blade **App-beveiligingsbeleid** in de beheerconsole. Eindgebruikers kunnen de app 'PrinterOn for Microsoft' downloaden via de Play Store of iTunes voor gebruik binnen hun Intune-ecosysteem.

### <a name="macos-company-portal-support-for-enrollments-that-use-the-device-enrollment-manager----1352411---"></a>Ondersteuning van de macOS-bedrijfsportal voor inschrijvingen die gebruikmaken van de apparaatinschrijvingsmanager <!-- 1352411 -->

Gebruikers kunnen nu de apparaatinschrijvingsmanager gebruiken bij het inschrijven via de macOS-bedrijfsportal.

## <a name="week-of-january-29-2018"></a>De week van 29 januari 2018

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire----1639263---"></a>Waarschuwingen voor vervallen tokens en tokens die binnenkort vervallen <!-- 1639263 -->
De overzichtspagina geeft nu waarschuwingen weer voor vervallen tokens en tokens die binnenkort vervallen. Wanneer u op een waarschuwing voor een specifiek token klikt, gaat u naar de detailpagina van dat token.  Als u op een waarschuwing met meerdere tokens klikt, gaat u naar een lijst met alle tokens met hun status. Beheerders moeten hun tokens vóór de vervaldatum vernieuwen.

### <a name="device-management"></a>Apparaatbeheer

#### <a name="remote-erase-command-support-for-macos-devices----1438084---"></a>Ondersteuning voor externe opdracht 'Wissen' voor macOS-apparaten <!-- 1438084 -->

Beheerders kunnen op afstand een opdracht voor wissen geven voor macOS-apparaten.

> [!IMPORTANT]
> De wisopdracht kan niet ongedaan worden gemaakt en moet voorzichtig worden gebruikt.

Met de wisopdracht worden alle gegevens van een apparaat verwijderd, inclusief het besturingssysteem. Hiermee wordt ook het apparaat uit Intune verwijderd. De gebruiker krijgt geen waarschuwing te zien en het verwijderen gebeurt onmiddellijk nadat de opdracht is gegeven.

U moet wel een 6-cijferige herstelpincode configureren. Deze pincode kan worden gebruikt voor het ontgrendelen van het gewiste apparaat, waarna het besturingssysteem opnieuw wordt geïnstalleerd. Nadat het verwijderen is gestart, wordt de pincode weergegeven in een statusbalk op de overzichtsblade van het apparaat in Intune. De pincode blijft intact zolang het verwijderen wordt uitgevoerd. Nadat het verwijderen is voltooid, verdwijnt het apparaat volledig uit Intune-beheer. Zorg ervoor dat u de herstelpincode vastlegt zodat degene die het apparaat terugzet deze kan gebruiken.

#### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>Licenties intrekken voor een token van het iOS-volume-aanschafprogramma<!-- 820870 --> 
U kunt de licentie van alle iOS-apps uit het volume-aanschafprogramma (VPP) voor een bepaalde VPP-token intrekken.

### <a name="app-management"></a>Appbeheer

#### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>Apps uit het volume-aankoopprogramma voor iOS intrekken <!-- 820863 -->
Voor een bepaald apparaat met een of meer iOS-apps uit het volume-aankoopprogramma (VPP) kunt u de gekoppelde op een apparaat gebaseerde app-licentie voor het apparaat intrekken. Als u een app-licentie intrekt, wordt de desbetreffende VPP-app niet van het apparaat verwijderd. Als u een VPP-app wilt verwijderen, moet u de toewijzingsactie wijzigen in **Verwijderen**. Zie [iOS-apps beheren die zijn aangeschaft via een volume-aankoopprogramma met Microsoft Intune](vpp-apps-ios.md) voor meer informatie.

#### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Mobiele apps van Office 365 toewijzen aan iOS- en Android-apparaten met behulp van de ingebouwde app-type<!-- 1332318 -->
Het **ingebouwde** app-type maakt het eenvoudiger voor u om Office 365-apps te maken en toe te wijzen aan door u beheerde iOS- en Android-apparaten. Deze apps zijn onder andere 0365-apps, zoals Word, Excel, PowerPoint en OneDrive. U kunt specifieke apps toewijzen aan het app-type en de configuratie van de app-gegevens bewerken.

#### <a name="including-and-excluding-app-assignment-based-on-groups----1406920---"></a>App-toewijzing opnemen en uitsluiten op basis van groepen <!-- 1406920 -->

Tijdens toewijzing van een app en na het selecteren van een toewijzingstype, kunt u selecteren welke groepen u wilt opnemen en welke u wilt uitsluiten.

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="you-can-assign-an-application-configuration-policy-to-groups-by-including-and-excluding-assignments-----1480316---"></a>U kunt een toepassingsconfiguratiebeleid toewijzen aan groepen door toewijzingen op te nemen en uit te sluiten <!-- 1480316 --> 

U kunt een toepassingsconfiguratiebeleid toewijzen aan een groep gebruikers en apparaten met behulp van een combinatie van opgenomen en uitgesloten toewijzingen. U kunt toewijzingen kiezen als een aangepaste selectie groepen of als afzonderlijke groep. Een virtuele groep kan **Alle gebruikers**, **Alle apparaten** of **Alle gebruikers + alle apparaten** bevatten.

#### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Ondersteuning voor het editie-upgradebeleid voor Windows 10   <!-- 903672(archived), 1119689 -->  
U kunt een editie-upgradebeleid voor Windows 10 maken dat Windows 10-apparaten upgradet naar Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education en Windows 10 Professional Education N. Raadpleeg [Editie-upgrades voor Windows 10 configureren](edition-upgrade-configure-windows-10.md) voor meer informatie over editie-upgrades voor Windows 10.

#### <a name="conditional-access-policies-for-intune-is-only-available-from-the-azure-portal-----1737088-1634311---"></a>Beleid voor voorwaardelijke toegang voor Intune is alleen beschikbaar vanuit Azure Portal <!-- 1737088 1634311 -->

Vanaf deze versie moet u uw beleid voor voorwaardelijke toegang configureren en beheren in het [Azure Portal](https://portal.azure.com) via **Azure Active Directory** > **Voorwaardelijke toegang**. Voor uw gemak hebt u ook toegang tot deze blade vanuit Intune in Azure Portal via **Intune** > **Voorwaardelijke toegang**.

#### <a name="updates-to-compliance-emails---1637547---"></a>Updates voor e-mailberichten over naleving <!--1637547 -->

Wanneer er een e-mailbericht wordt verzonden om een niet-compatibel apparaat te melden, worden daarin gegevens over het niet-compatibele apparaat opgenomen. 


## <a name="week-of-january-22-2018"></a>De week van 22 januari 2018

### <a name="intune-apps"></a>Intune-apps

#### <a name="new-functionality-for-the-resolve-action-for-android-devices---1583480--"></a>Nieuwe functionaliteit voor de actie 'Oplossen' voor Android-apparaten <!--1583480-->

De bedrijfsportal-app voor Android breidt de actie 'Oplossen' uit voor **Apparaatinstellingen bijwerken** om [problemen met de versleuteling van het apparaat](/intune-user-help/encrypt-your-device-android) op te lossen.

#### <a name="remote-lock-available-in-company-portal-app-for-windows-10---676506--"></a>Externe vergrendeling is beschikbaar in de bedrijfsportal-app voor Windows 10<!--676506-->
Eindgebruikers kunnen nu in de bedrijfsportal-app voor Windows 10 hun apparaten extern vergrendelen. Dit wordt niet weergegeven voor het lokale apparaat dat op dat moment wordt gebruikt.

#### <a name="easier-resolution-of-compliance-issues-for-the-company-portal-app-for-windows-10---676546--"></a>Eenvoudigere oplossing van problemen met naleving voor de bedrijfsportal-app voor Windows 10 <!--676546-->
Eindgebruikers met Windows-apparaten kunnen tikken op de reden van niet-naleving in de bedrijfsportal-app. Indien mogelijk worden ze hiermee rechtstreeks naar de juiste locatie geleid in de instellingen-app om het probleem te verhelpen.

## <a name="week-of-december-11-2017"></a>Week van 11 december 2017

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="new-automatic-redeployment-setting----1469168---"></a>Nieuwe instelling voor automatisch opnieuw implementeren <!-- 1469168 -->
De instelling **Automatisch opnieuw implementeren** maakt het mogelijk dat gebruikers met beheerdersrechten alle gebruikersgegevens en -instellingen verwijderen met **CTRL + Win + R** op het vergrendelingsscherm van het apparaat. Het apparaat wordt automatisch opnieuw geconfigureerd en opnieuw ingeschreven bij het beheer. U vindt deze instelling onder Windows 10 > Apparaatbeperkingen > Algemeen > Automatisch opnieuw installeren. Zie [Intune-apparaatbeperkingsinstellingen voor Windows 10](device-restrictions-windows-10.md#general) voor meer informatie.

#### <a name="support-for-additional-source-editions-in-the-windows-10-edition-upgrade-policy-----903672--1119689---"></a>Ondersteuning voor extra bronedities in het beleid voor editie-upgrades voor Windows 10<!-- 903672,  1119689 -->
U kunt nu het beleid voor editie-upgrades voor Windows 10 gebruiken om een upgrade uit te voeren voor extra edities van Windows 10 (Windows 10 Pro, Windows 10 Pro Education, Windows 10 Cloud, enzovoort). Vóór deze release waren de ondersteunde editie-upgradepaden beperkter. Zie [Editie-upgrades voor Windows 10 configureren](edition-upgrade-configure-windows-10.md) voor meer informatie.

#### <a name="new-windows-defender-security-center-wdsc-device-configuration-profile-settings----1335507---"></a>Nieuwe profielinstellingen voor apparaatconfiguratie voor Windows Defender Security Center (WDSC) <!-- 1335507 -->

Intune voegt een nieuwe sectie toe in de profielinstellingen voor apparaatconfiguratie onder de eindpuntbeveiliging genaamd **Windows Defender Security Center**. IT-beheerders kunnen configureren tot welke onderdelen van de Windows Defender Security Center-app eindgebruikers toegang hebben. Als een IT-beheerder een onderdeel verbergt in de Windows Defender Security Center-app, worden alle meldingen die betrekking hebben op het verborgen onderdeel, niet weergeven op het apparaat van de gebruiker.

De volgende onderdelen kunnen worden verborgen in de profielinstellingen voor apparaatconfiguratie van Windows Defender Security Center:
- Virus- en bedreigingsbeveiliging
- Prestaties en status van apparaat
- Firewall- en netwerkbeveiliging
- App- en browserbeheer
- Gezinsopties

IT-beheerders kunnen ook aanpassen welke meldingen gebruikers ontvangen. U kunt bijvoorbeeld configureren of de gebruikers alle meldingen ontvangen die worden gegenereerd door zichtbare onderdelen in het WDSC of alleen kritieke meldingen. Niet-kritieke meldingen zijn bijvoorbeeld periodieke samenvattingen van Windows Defender Antivirus-activiteiten en meldingen wanneer scans zijn voltooid. Alle andere meldingen worden beschouwd als kritiek. Daarnaast kunt u ook de inhoud van meldingen zelf aanpassen. U kunt bijvoorbeeld contactgegevens van de IT-afdeling toevoegen aan meldingen die worden weergegeven op apparaten van gebruikers.

#### <a name="multiple-connector-support-for-scep-and-pfx-certificate-handling----1361755---"></a>Ondersteuning voor meerdere connectoren voor het verwerken van SCEP- en PFX-certificaten <!-- 1361755 -->

Klanten die de on-premises NDES-connector gebruiken om certificaten aan apparaten te leveren, kunnen nu meerdere connectoren in één tenant configureren.

Deze nieuwe mogelijkheid biedt ondersteuning voor het volgende scenario:

- **Hoge beschikbaarheid**

Elke NDES-connector haalt certificaataanvragen uit Intune op.  Als één NDES-connector offline gaat, kan de andere connector aanvragen blijven verwerken.

#### <a name="customer-subject-name-can-use-aaddeviceid-variable-----1468599---"></a>Aangepaste onderwerpnaam kan de AAD_DEVICE_ID-variabele <!-- 1468599 --> gebruiken

Wanneer u een SCEP-certificaatprofiel in Intune maakt, kunt u nu de AAD_DEVICE_ID-variabele gebruiken bij het samenstellen van de aangepaste onderwerpnaam.   Wanneer het certificaat wordt aangevraagd via dit SCEP-profiel, wordt de variabele vervangen door de AAD-apparaat-id van het apparaat dat de certificaataanvraag doet.


### <a name="device-management"></a>Apparaatbeheer

#### <a name="manage-jamf-enrolled-macos-devices-with-intunes-device-compliance-engine----1592747---"></a>Via Jamf ingeschreven macOS-apparaten beheren met de Intune-engine voor apparaatnaleving<!-- 1592747 -->
U kunt nu Jamf gebruiken om statusinformatie over macOS-apparaten naar Intune te sturen, waarna het apparaat wordt geëvalueerd op naleving van het beleid dat is gedefinieerd in de Intune-console. Op basis van de nalevingsstatus van het apparaat en van andere omstandigheden (zoals locatie, gebruikersrisico en dergelijke) dwingt voorwaardelijke toegang naleving af voor macOS-apparaten die toegang hebben tot toepassingen in de cloud en on-premises die zijn verbonden met Azure AD, met inbegrip van Office 365. Meer informatie over [integratie met Jamf instellen](conditional-access-integrate-jamf.md) en [afdwingen van naleving voor door Jamf beheerde apparaten](conditional-access-assign-jamf.md).

#### <a name="new-ios-device-action------1424701---"></a>Nieuwe actie voor iOS-apparaten <!-- 1424701 -->

U kunt nu door iOS 10.3 gecontroleerde apparaten afsluiten. Deze actie sluit het apparaat direct af zonder waarschuwing voor de eindgebruiker. U vindt de actie **Afsluiten (alleen gecontroleerd)** in de apparaateigenschappen wanneer u een apparaat selecteert in de werkbelasting **Apparaat**.

#### <a name="disallow-datetime-changes-to-samsung-knox-devices----1468103---"></a>Geen datum-/tijdwijzigingen voor Samsung Knox-apparaten toestaan <!-- 1468103 -->

We hebben een nieuwe functie toegevoegd waarmee u datum- en tijdwijzigingen op Samsung Knox-apparaten kunt blokkeren. U kunt dit vinden in **Apparaatconfiguratieprofielen** > **Apparaatbeperkingen (Android)** > **Algemeen**.

#### <a name="surface-hub-resource-account-supported----1566442----"></a>Resource-account voor Surface Hub ondersteund <!-- 1566442  -->

Er is een nieuwe apparaatactie toegevoegd, zodat beheerders het resource-account dat is gekoppeld aan een Surface Hub, kunnen definiëren en bijwerken.

Het resource-account wordt door een Surface Hub gebruikt voor verificatie bij Exchange/Skype, zodat kan worden deelgenomen aan een vergadering. U kunt een uniek resource-account maken, zodat de Surface Hub als vergaderruimte wordt weergegeven in de vergadering. Het resource-account kan bijvoorbeeld worden weergegeven als *Vergaderzaal B41/6233*. Het resource-account (ook wel het apparaataccount genoemd) voor de Surface Hub moet meestal worden geconfigureerd voor de locatie van de vergaderruimte en wanneer andere parameters van het resource-account moeten worden gewijzigd.

Wanneer beheerders het resource-account op een apparaat willen bijwerken, moeten ze de huidige referenties voor Active Directory/Azure Active Directory voor het apparaat opgeven. Als wisseling van het wachtwoord is ingeschakeld voor het apparaat, moeten beheerders het wachtwoord zoeken in Azure Active Directory.

> [!NOTE]
> Alle velden in een bundel worden verzonden en overschrijven alle velden die eerder zijn geconfigureerd. Lege velden overschrijven ook bestaande velden.

Beheerders kunnen de volgende instellingen configureren:

- **Resource-account**
   - **Active Directory-gebruiker**

      Domeinnaam\gebruikersnaam of UPN (Principle-naam van gebruiker):user@domainname.com

   - **Wachtwoord**

- **Optionele parameters voor het resource-account** (moeten worden ingesteld met het opgegeven resource-account)

   - **Periode voor de wisseling van het wachtwoord**

     Zorgt ervoor dat het accountwachtwoord uit veiligheidsoverwegingen elke week automatisch wordt bijgewerkt door de Surface Hub. Als u parameters wilt configureren nadat dit is ingeschakeld, moet eerst het wachtwoord voor het account in Azure Active Directory opnieuw worden ingesteld.

   - **SIP-adres (Session Initiation Protocol)**

     Wordt alleen gebruikt als automatische detectie mislukt.

   - **E-mail**

     Het e-mailadres van het apparaat-/resource-account.

   - **Exchange-server**

     Alleen vereist wanneer automatische detectie mislukt.

   - **Agendasynchronisatie**

     Hiermee geeft u op of agendasynchronisatie en andere Exchange Server-services zijn ingeschakeld. Bijvoorbeeld: synchronisatie van vergaderingen.

#### <a name="install-office-apps-on-macos-devices----1494311---"></a>Office-apps installeren op macOS-apparaten <!-- 1494311 -->
U kunt nu Office-apps installeren op macOS-apparaten. Met dit nieuwe app-type kunt u Word, Excel, PowerPoint, Outlook en OneNote installeren. Deze apps worden ook geleverd met Microsoft AutoUpdate (MAU) om te zorgen dat uw apps veilig en up-to-date blijven.

### <a name="app-management"></a>Appbeheer

#### <a name="delete-an-ios--volume-purchasing-program-token----820879---"></a>Een token van het iOS-volume-aanschafprogramma verwijderen <!-- 820879 -->
U kunt het token van het iOS-volume-aanschafprogramma (VPP) verwijderen via de console. Dit kan nodig zijn als er dubbele exemplaren van een VPP-token zijn.

### <a name="intune-apps"></a>Intune-apps

#### <a name="end-user-messaging-for-accounts---1573558-for-1712--"></a>Eindgebruikersberichten voor accounts <!--1573558 for 1712-->

Gebruikers van de bedrijfsportal-website worden geblokkeerd voor het uitvoeren van acties waarvoor schrijftoegang tot uw tenant is vereist. Ze krijgen een foutbericht te zien waarin wordt uitgelegd dat hun account in onderhoud is. Dergelijke wijzigingen worden binnenkort ook toegepast op de bedrijfsportal-apps voor Android, iOS, macOS en Windows. U kunt deze fout zien op de pagina [Nieuw in de app-gebruikersinterface](whats-new-app-ui.md).



### <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer

#### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1667026---"></a>De nieuwe entiteitverzameling Huidige gebruiker is beperkt tot gegevens van actieve gebruikers <!-- 1667026 -->

De entiteitverzameling **Gebruiker** bevat alle Azure Active Directory-gebruikers (Azure AD) met toegewezen licenties in uw onderneming. Een gebruiker kan bijvoorbeeld worden toegevoegd aan Intune en vervolgens ergens gedurende de afgelopen maand zijn verwijderd. Ook al is deze gebruiker niet aanwezig op het moment dat het rapport wordt gegenereerd, toch zijn de gebruiker en de status aanwezig in de gegevens. U kunt een rapport maken dat de duur van de historische aanwezigheid van de gebruiker in uw gegevens weergeeft.

Daarentegen bevat de nieuwe entiteitverzameling **Huidige gebruiker** alleen gebruikers die niet zijn verwijderd. De entiteitverzameling **Huidige gebruiker** bevat alleen gebruikers die momenteel actief zijn. Zie [Naslaginformatie voor huidige gebruikersentiteit](reports-ref-current-user.md) voor informatie over de entiteitverzameling **Huidige gebruiker**.


### <a name="updated-graph-apis----1736360---"></a>Bijgewerkte Graph API's <!-- 1736360 -->

We hebben in deze release enkele Graph API's voor Intune bijgewerkt die nog in de bètafase zijn. Bekijk de maandelijkse [Graph API changelog](https://developer.microsoft.com/graph/docs/concepts/changelog) voor meer informatie.

## <a name="week-of-december-4-2017"></a>Week van 4 december 2017

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="intune-supports-windows-information-protection-wip-denied-apps----1479103---"></a>Intune biedt ondersteuning voor door Windows Information Protection (WIP) geweigerde apps <!-- 1479103 -->
U kunt geweigerde apps opgeven in Intune. Als een app wordt geweigerd, heeft deze geen toegang tot zakelijke gegevens. Dit is dus eigenlijk het tegenovergestelde van de lijst met toegestane apps. Zie [Aanbevolen lijst voor weigeren voor Windows Information Protection](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp?f=255&MSPPError=-2147217396#recommended-deny-list-for-windows-information-protection) voor meer informatie.


## <a name="week-of-november-27-2017"></a>Week van 27 november 2017

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="troubleshoot-enrollment-issues-----746324---"></a>Inschrijvingsproblemen oplossen <!-- 746324 -->

De werkruimte **Problemen oplossen** toont problemen met gebruikersinschrijving. Details over het probleem en voorgestelde herstelstappen kunnen beheerders en helpdeskmedewerkers helpen problemen op te lossen. Bepaalde inschrijvingsproblemen worden niet vastgelegd en voor sommige fouten zijn er misschien geen herstelvoorstellen.

#### <a name="group-assigned-enrollment-restrictions----747598---"></a>Beperkingen aan groepen toegewezen inschrijving <!-- 747598 -->

Als Intune-beheerder kunt u de [aangepaste inschrijvingsbeperkingen Apparaattype en Apparaatlimiet maken voor gebruikersgroepen](enrollment-restrictions-set.md).

Met de Intune Azure Portal kunt u maximaal 25 exemplaren van elk beperkingstype maken die vervolgens kunnen worden toegewezen aan gebruikersgroepen. Aan groepen toegewezen beperkingen overschrijven de standaardbeperkingen.

Alle exemplaren van een beperkingstype worden bijgehouden in een strikt geordende lijst. Deze volgorde bepaalt een prioriteitswaarde voor conflictoplossing. Een gebruiker die getroffen is door meer dan één beperkingsexemplaar wordt alleen beperkt door het exemplaar met de hoogste prioriteitswaarde. U kunt de prioriteit van een bepaald exemplaar wijzigen door dit naar een andere positie in de lijst te slepen.

Deze functionaliteit wordt vrijgegeven met de migratie van Android for Work-instellingen van het menu Android for Work-inschrijving naar het menu Inschrijvingsbeperkingen. Aangezien deze migratie enkele dagen kan duren, kan uw account worden bijgewerkt ten aanzien van andere onderdelen van de release van november voordat u ziet dat groepstoewijzing wordt ingeschakeld voor Inschrijvingsbeperkingen.

#### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors----1528104---"></a>Ondersteuning voor meerdere connectors voor de Network Device Enrollment-service (NDES)<!-- 1528104 -->

Met de NDES kunnen mobiele apparaten die zonder domeinreferenties worden uitgevoerd certificaten verkrijgen op basis van het Simple Certificate Enrollment Protocol (SCEP).
Dankzij deze update worden meerdere NDES-connectors ondersteund.

#### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731-eeready--"></a>Android for Work-apparaten onafhankelijk van de Android-apparaten beheren<!-- 1490731 EEready-->

**Opmerking**: De volgende wijzigingen gaan van start bij de update van november, maar de uitvoering ervan voor uw account kan nog wel even duren. U ontvangt een bevestigingsbericht in de Office 365-portal wanneer deze wijzigingen voor uw account van kracht zijn. Na de implementatie hebt u aanvullende beheeropties. Er zijn geen wijzigingen in de ervaringen van de eindgebruiker tijdens de implementatie.

Intune ondersteunt het inschrijvingsbeheer voor Android for Work-apparaten onafhankelijk van het Android-platform. Deze instellingen worden beheerd onder **Apparaatinschrijving** > **Inschrijvingsbeperkingen** > **Apparaattypebeperkingen**. (Ze bevonden zich eerder onder **Apparaatinschrijving** > **Android for Work-inschrijving** > **Android for Work-inschrijvingsinstellingen**.)

Standaard zijn instellingen voor uw Android for Work-apparaten gelijk aan de instellingen voor uw Android-apparaten. Wanneer u echter uw Android for Work-instellingen wijzigt, is dat niet meer het geval.

Als u een persoonlijke Android for Work-inschrijving blokkeert, kunnen alleen zakelijke Android-apparaten worden ingeschreven als Android for Work.

Bedenk de volgende punten wanneer u met de nieuwe instellingen werkt:

##### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Als u nog nooit een Android for Work-inschrijving hebt toegevoegd

Het nieuwe Android for Work-platform wordt geblokkeerd in de standaard apparaattypebeperkingen. Wanneer u de functie toevoegt, kunt u de Android for Work-inschrijving van apparaten toestaan. Hiervoor wijzigt u de standaardinstelling of maakt u een nieuwe apparaattypebeperking ter vervanging van de standaard apparaattypebeperking.

##### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Als u de Android for Work-inschrijving hebt toegevoegd

Als u dit al eerder hebt gedaan, is uw situatie afhankelijk van de instelling die u hebt gekozen:

| Instelling | De status van Android for Work bij een standaard apparaattypebeperking | Opmerkingen |
| --- | --- | --- |
| **Alle apparaten beheren als Android** | Geblokkeerd | U mag geen Android-apparaten bij Android for Work hebben ingeschreven. |
| **Ondersteunde apparaten beheren als Android for Work** | Toegestaan | Alle Android-apparaten die ondersteuning bieden voor Android for Work moeten zijn ingeschreven bij Android for Work. |
| **Alleen ondersteunde apparaten voor de gebruikers in deze groepen beheren als Android for Work** | Geblokkeerd | Er is een afzonderlijk beleid voor apparaattypebeperkingen gemaakt om de standaardinstelling te overschrijven. Dit beleid bepaalt de groepen die u eerder hebt geselecteerd om Android for Work-inschrijving toe te staan. Gebruikers binnen de geselecteerde groepen mogen hun Android for Work-apparaten blijven inschrijven. Alle andere gebruikers worden uitgesloten van inschrijving bij Android for Work. |

In alle gevallen blijft uw beoogde regel behouden. Er is geen actie vereist van uw kant om de globale of groepsgewijze toestemming voor Android for Work in uw omgeving te handhaven.

### <a name="app-management"></a>Appbeheer

#### <a name="app-install-report-updated-to-include-install-pending-status----1249446---"></a>Het statusrapport van de app-installatie wordt bijgewerkt met de status Installatie in behandeling <!-- 1249446 -->  

Het **Statusrapport van de app-installatie**, dat toegankelijk is voor elke app via de **App**-lijst in de **Mobiele apps**-workload, bevat nu **Installatie in behandeling** voor gebruikers en apparaten.

#### <a name="ios-11-app-inventory-api-for-mobile-threat-detection----1391759---"></a>API iOS 11-app-inventaris voor mobiele detectie van dreigingen (MTD) <!-- 1391759 -->

Intune verzamelt informatie over de app-inventaris van apparaten in zowel privé- als bedrijfseigendom en maakt deze informatie beschikbaar voor MTD-providers om op te halen, zoals Lookout for Work. U kunt de app-inventaris verzamelen van gebruikers van iOS 11+-apparaten.

**App-inventaris**  
Inventarissen van iOS 11 +-apparaten in zowel bedrijfs- en privé-eigendom worden verzonden naar uw MTD-serviceprovider. Gegevens in de app-inventarisatie bestaan onder andere uit:

 - App-id
 - App-versie
 - Verkorte App-versie
 - App-naam
 - Grootte van de App-bundel
 - Dynamische grootte van de App
 - App is wel of niet gevalideerd
 - App is wel of niet beheerd


### <a name="device-management"></a>Apparaatbeheer

#### <a name="migrate-hybrid-mdm-users-and-devices-to-intune-standalone----1463747-wnready---"></a>Hybride MDM-gebruikers en -apparaten migreren naar Intune (zelfstandig)<!-- 1463747 wnready -->
Er zijn nu nieuwe processen en hulpprogramma's beschikbaar om in Azure Portal gebruikers en hun apparaten van hybride MDM naar Intune te verplaatsen, zodat u het volgende kunt doen:
- In Azure Portal beleidsregels en profielen van de Configuration Manager-console naar Intune kopiëren
- In Azure Portal een subset gebruikers naar Intune verplaatsen, terwijl de rest in hybride MDM blijft
- In Azure Portal apparaten naar Intune migreren zonder dat u ze opnieuw hoeft te registreren

Zie [Hybride MDM-gebruikers en -apparaten migreren naar Intune (zelfstandig)](https://docs.microsoft.com/sccm/mdm/deploy-use/migrate-hybridmdm-to-intunesa) voor meer informatie.

#### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Hoge beschikbaarheid van on-premises Exchange Connector  <!-- 676614 -->
Nadat de Exchange Connector verbinding met Exchange heeft gemaakt met behulp van de opgegeven CAS, kan de connector nu andere CAS-instanties detecteren. Als de primaire CAS niet beschikbaar is, zoekt de connector naar een andere CAS (indien beschikbaar) totdat de primaire CAS beschikbaar komt. Zie [Hoge beschikbaarheid van on-premises Exchange Connector](exchange-connector-install.md#on-premises-exchange-connector-high-availability-support) voor meer informatie.

#### <a name="remotely-restart-ios-device-supervised-only----1424595---"></a>iOS-apparaat op afstand opnieuw opstarten (alleen onder supervisie)<!-- 1424595 -->

U kunt een iOS 10.3 +-apparaat onder supervisie activeren om via een apparaatactie opnieuw op te starten. Zie voor meer informatie over het gebruik van de actie voor het opnieuw opstarten van het apparaat [Apparaten op afstand opnieuw opstarten met Intune](device-restart.md).

> [!Note]
> Deze opdracht vereist toegangsrechten tot apparaten onder supervisie en **Apparaatvergrendeling**. Het apparaat wordt onmiddellijk opnieuw opgestart. Met een toegangscode vergrendelde iOS-apparaten wordt niet opnieuw verbonden met een Wi-Fi-netwerk na opnieuw te zijn opgestart; na opnieuw te zijn opgestart kunnen deze mogelijk niet communiceren met de server.

#### <a name="single-sign-on-support-for-ios----1333645---"></a>Ondersteuning voor Eenmalige aanmelding voor iOS<!-- 1333645 -->  

U kunt Eenmalige aanmelding voor iOS-gebruikers gebruiken. De iOS-apps die zijn gecodeerd om naar de gebruikersreferenties te zoeken in de Eenmalige aanmelding-payload zijn functioneel voor de update van de payloadconfiguratie. U kunt ook de UPN en de Intune-apparaat-id gebruiken om de Principal-naam en de Realm te configureren. Zie [Intune configureren voor eenmalige aanmelding vanaf iOS-apparaten](sso-ios.md) voor meer informatie.

#### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Mijn iPhone vinden toevoegen voor privéapparaten<!--1427287-->
U kunt nu bekijken of bij iOS-apparaten Activeringsslot is ingeschakeld. Deze functie was eerder te vinden in de klassieke portal in Intune.


#### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Beheerde macOS-apparaten op afstand vergrendelen met Intune<!-- 1437691 -->

U kunt een verloren Mac OS-apparaat vergrendelen en een 6-cijferige pincode voor wachtwoordherstel instellen. Als het apparaat is vergrendeld, toont de blade **Apparaatoverzicht** de pincode totdat een andere apparaatactie wordt verzonden.

Zie voor meer informatie [Beheerde apparaten op afstand vergrendelen met Intune](device-remote-lock.md).

#### <a name="new-scep-profile-details-supported----1559808---"></a>Nieuwe SCEP-profielgegevens ondersteund<!-- 1559808 -->

Beheerders kunnen aanvullende instellingen configureren bij het maken van een SCEP-profiel op Windows-, iOS-, Mac OS- en Android-platformen.  Beheerders kunnen het IMEI-nummer, het serienummer of de algemene naam met inbegrip van e-mail in de indeling van de onderwerpnaam instellen.

<!-- #### Update to what device details your company may see -1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources. -->

#### <a name="retain-data-during-a-factory-reset----1588489---"></a>Gegevens behouden tijdens fabrieksinstellingen terugzetten <!--1588489 -->
Wanneer Windows 10 versie 1709 en later naar de fabrieksinstellingen wordt hersteld, is een nieuwe functie beschikbaar. Beheerders kunnen opgeven of apparaatinschrijving en andere ingerichte gegevens worden bewaard op een apparaat via fabrieksinstellingen terugzetten.

De volgende gegevens wordt behouden via fabrieksinstellingen terugzetten:
- Gebruikersaccounts die zijn gekoppeld aan het apparaat
- Status van de machine (lid van domein, lid van Azure Active Directory)
- MDM-inschrijving
- Door OEM geïnstalleerde apps (Store- en Win32-apps)
- Gebruikersprofiel
- Gebruikersgegevens buiten het gebruikersprofiel
- Autologon gebruiker

De volgende gegevens blijven niet behouden:
- Gebruikersbestanden
- Door de gebruiker geïnstalleerde apps (Store- en Win32-apps)
- Niet-standaard apparaatinstellingen

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen
#### <a name="window-10-update-ring-assignments-are-displayed----1621837---"></a>Er worden toewijzingen voor de Windows 10-updatering weergegeven <!-- 1621837 -->
Wanneer u bezig bent met de **probleemoplossing** voor de door u weergegeven gebruiker, kunt u eventuele toewijzingen voor de Windows 10-updatering zien.  

#### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings-----1455974----"></a>Frequentie-instellingen van rapporten van Windows Defender Advanced Threat Protection <!-- 1455974  -->
Met de service Windows Defender Advanced Threat Protection (WDATP) kunnen beheerders de rapportagefrequentie voor beheerde apparaten beheren. Met de nieuwe optie **Frequentie van telemetrierapporten versnellen** verzamelt vaker WDATP gegevens en beoordeelt vaker risico's. De standaardwaarde voor rapportage zorgt voor optimale snelheid en prestaties. Het verhogen van de rapportagefrequentie kan waardevol zijn voor apparaten met een hoog risico. Deze instelling kunt u vinden in het **Windows Defender ATP**-profiel in **Apparaatconfiguraties**.

#### <a name="audit-updates----1412961---"></a>Updates controleren<!-- 1412961 -->  
Controles van Intune biedt een record van de wijzigingsbewerkingen ten aanzien van Intune.  Alle taakbewerkingen voor maken, bijwerken, verwijderen en externe taakbewerkingen worden vastgelegd en een jaar bewaard.  De Azure Portal voorziet in een weergave van de controlegegevens van laatste 30 dagen in elke workload, welke gefilterd kan worden.  Met de bijbehorende Graph API kunt u de controlegegevens ophalen die het afgelopen jaar zijn bewaard.

Controles zijn te vinden onder de groep **CONTROLE**. Er is een menu-item **Controlelogboeken** voor elke workload.




## <a name="week-of-november-20-2017"></a>Week van 20 november 2017

### <a name="app-management"></a>Appbeheer

#### <a name="google-play-protect-support-on-android----908720---"></a>Ondersteuning van Google Play Protect op Android <!-- 908720 -->

Google introduceert tegelijkertijd met Android Oreo een reeks beveiligingsfuncties met de naam Google Play Protect waarmee gebruikers en organisaties beveiligde apps en beveiligde Android-installatiekopieën kunnen uitvoeren. Intune ondersteunt de functies van Google Play Protect, inclusief SafetyNet voor externe verklaringen. Beheerders kunnen eisen voor een nalevingsbeleid instellen die vereisen dat Google Play Protect wordt geconfigureerd en in orde is.
De instelling **SafetyNet-apparaatverklaring** vereist dat het apparaat verbinding maakt met een service van Google om te controleren of het apparaat in orde is en er niet mee is geknoeid. Beheerders kunnen tevens een configuratieprofielinstelling voor Android for Work instellen om te vereisen dat geïnstalleerde apps worden geverifieerd met behulp van Google Play-services. Als een apparaat niet aan de eisen van Google Play Protect voldoet, kan voorwaardelijke toegang de toegang van gebruikers tot bedrijfsbronnen blokkeren.

- Meer informatie over [het maken van een nalevingsbeleid voor apparaten om Google Play Protect in te schakelen](https://docs.microsoft.com/intune/compliance-policy-create-google-play-protect).

#### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Tekstprotocol toegestaan vanuit beheerde Apps<!-- 1414050  -->

Met apps die worden beheerd door de Intune App SDK kunnen SMS-berichten worden verzonden.

## <a name="week-of-november-13-2017"></a>Week van 13 november 2017

### <a name="intune-apps"></a>Intune-apps
#### <a name="company-portal-app-for-macos-is-available---1541700--"></a>De bedrijfsportal-app voor macOS is beschikbaar <!--1541700-->
De Intune-bedrijfsportal op macOS is bijgewerkt en geoptimaliseerd, zodat alle informatie en nalevingsmeldingen die uw gebruikers nodig hebben voor alle apparaten die ze hebben ingeschreven, overzichtelijk wordt weergegeven. En als de Intune-bedrijfsportal eenmaal is geïmplementeerd op een apparaat, zorgt Microsoft AutoUpdate voor macOS voor de updates. U kunt de nieuwe Intune-bedrijfsportal voor macOS downloaden door u aan te melden bij de website van de Intune-bedrijfsportal vanaf een macOS-apparaat.

#### <a name="microsoft-planner-is-now-part-of-the-mobile-app-management-mam-list-of-approved-apps-----1248473---"></a>Microsoft Planner maakt nu deel uit van de MAM-lijst (beheer van mobiele apps) met goedgekeurde apps <!-- 1248473 -->
De app Microsoft Planner voor iOS en Android maakt nu deel uit van de goedgekeurde apps voor Mobile App Management (MAM). De app kan via de blade Intune-app-beveiliging in Azure Portal worden geconfigureerd voor alle tenants.
- Meer informatie over de [MAM-lijst met goedgekeurde apps](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

#### <a name="per-app-vpn-requirement-update-frequency-on-ios-devices------1547061---"></a>Vereiste updatefrequentie voor VPN per app op iOS-apparaten <!-- 1547061 -->  
Beheerders kunnen nu de vereisten voor VPN per app verwijderen voor apps op iOS-apparaten. Dit wordt toegepast op de betreffende apparaten na de eerstvolgende check-in bij Intune, gewoonlijk binnen 15 minuten.  

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen
#### <a name="support-for-system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Ondersteuning van management pack van System Center Operations Manager voor Exchange Connector <!-- 885457 -->
Het management pack van System Center Operations Manager (SCOM) voor Exchange Connector is nu beschikbaar om de logboeken van Exchange Connector te parseren. Hiermee kunt u de service op verschillende manieren controleren wanneer u problemen moet oplossen.

## <a name="week-of-november-6-2017"></a>Week van 6 november 2017

### <a name="device-enrollment"></a>Apparaatinschrijving
#### <a name="co-management-for-windows-10-devices-----1243445---"></a>Co-management voor Windows 10-apparaten <!-- 1243445 -->
Co-management is een oplossing die een brug slaat tussen traditioneel en modern beheer en het biedt een gefaseerde benadering om de overstap te maken. Co-management is in feite een oplossing waarbij Windows 10-apparaten gelijktijdig worden beheerd door Configuration Manager en Microsoft Intune en zijn gekoppeld aan Active Directory (AD) en Azure Active Directory (Azure AD).  Deze configuratie geeft u een manier om mettertijd te moderniseren, in een tempo dat geschikt is voor uw organisatie als u niet allemaal tegelijk kunt overstappen.  

#### <a name="restrict-windows-enrollment-by-os-version----245498---"></a>Windows-inschrijving beperken door de versie van het besturingssysteem <!-- 245498 -->
Als Intune-beheerder kunt u een minimale en maximale versie opgeven van Windows 10 voor de inschrijving van apparaten. U kunt deze beperkingen instellen op de blade **Platformconfiguraties**.

Intune blijft ondersteuning bieden voor registratie Windows 8.1-pc's en -telefoons. U kunt echter alleen minimale en maximale versies instellen voor Windows 10-versies. Als u de inschrijving van 8.1-apparaten wilt toestaan, laat u de minimale versie leeg.

#### <a name="alerts-for-windows-autopilot-unassigned-devices-----1631236---"></a>Waarschuwingen voor niet-toegewezen Windows AutoPilot-apparaten <!-- 1631236 -->
Er is een nieuwe waarschuwing voor niet-toegewezen Windows AutoPilot-apparaten op de pagina **Microsoft Intune** > **Apparaatinschrijving** > **Overzicht**. Deze waarschuwing geeft aan voor hoeveel apparaten van het AutoPilot-programma geen AutoPilot-implementatieprofielen zijn toegewezen. Aan de hand van de informatie in de waarschuwing kunt u profielen maken en deze toewijzen aan de niet-toegewezen apparaten. Als u op de waarschuwing klikt, verschijnt een volledige lijst met Windows AutoPilot-apparaten en gedetailleerde informatie. Zie [Windows-apparaten inschrijven met het Windows AutoPilot Deployment-programma](https://docs.microsoft.com/intune/enrollment-autopilot) voor meer informatie.

### <a name="device-management"></a>Apparaatbeheer

#### <a name="refresh-button-for-devices-list-------1333581---"></a>Knop voor het vernieuwen van de lijst met apparaten    <!-- 1333581 -->
Omdat de lijst met apparaten niet automatisch wordt vernieuwd, kunt u de nieuwe knop gebruiken om de apparaten bij te werken die worden weergegeven in de lijst.

#### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Ondersteuning voor Symantec Cloud Certification Authority (CA)  <!-- 1333638 -->    
Intune ondersteunt nu Symantec Cloud CA, die de Intune Certificate Connector in staat stelt PKCS-certificaten van Symantec Cloud CA vrij te geven voor beheerde Intune-apparaten. Als u de Intune Certificate Connector al gebruikt met Microsoft Certification Authority (CA), kunt u de bestaande configuratie van de Intune Certificate Connector gebruiken om de ondersteuning voor Symantec CA toe te voegen.

#### <a name="new-items-added-to-device-inventory-----1404455---"></a>Nieuwe items toegevoegd aan de apparaatinventarisatie   <!--1404455 -->
De volgende nieuwe items zijn nu beschikbaar voor de [inventaris van ingeschreven apparaten](device-inventory.md):

- Mac-adres van Wi-Fi
- Totale opslagruimte
- Totale vrije ruimte
- MEID
- Provider van abonnee


### <a name="app-management"></a>Appbeheer
#### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Toegang instellen voor apps via minimale Android-beveiligingspatch op het apparaat<!-- 1278463 -->   
Een beheerder kan de minimale Android-beveiligingspatch definiëren die op het apparaat moet zijn geïnstalleerd om toegang te kunnen krijgen tot een beheerde toepassing onder een beheerd account.

> [!Note]  
> Deze functie beperkt alleen beveiligingspatches die door Google zijn vrijgegeven op Android 6.0+ apparaten.

#### <a name="app-conditional-launch-support----1193313---"></a>Ondersteuning voor app-voorwaardelijk starten <!-- 1193313 -->
IT-beheerders kunnen nu via de Azure-beheerportal een vereiste instellen om een wachtwoordcode in plaats van een numerieke pincode af te dwingen via Mobile App Management (MAM) wanneer de toepassing start. Als dit is geconfigureerd, moet de gebruiker een wachtwoordcode instellen en gebruiken wanneer daarom wordt gevraagd, alvorens toegang te krijgen tot toepassingen met MAM-functionaliteit. Een wachtwoordcode wordt gedefinieerd als een numerieke pincode met ten minste één speciaal teken of een hoofdletter/kleine letter. Bij deze release van Intune wordt deze functie **alleen op iOS** ingeschakeld. Intune ondersteunt wachtwoordcodes op dezelfde manier als numerieke pincodes: er is een minimumlengte, en tekens en tekenreeksen mogen worden herhaald. Deze functie vereist dat toepassingen (WXP, Outlook, Managed Browser, Yammer) de Intune App SDK integreren met de code voor deze functie om de wachtwoordcode-instellingen af te dwingen in de doeltoepassingen.

#### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>App-versienummer voor line-of-business in rapport Installatiestatus van het apparaat <!-- 1233999 -->
Bij deze release toont het rapport Installatiestatus van het apparaat het app-versienummer voor de line-of-business-apps voor iOS en Android. U kunt deze informatie gebruiken om problemen met uw apps op te lossen of om apparaten te vinden waarop verouderde app-versies worden uitgevoerd.


### <a name="device-configuration"></a>Apparaatconfiguratie
#### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>Beheerders kunnen de firewall-instellingen op een apparaat nu configureren met behulp van een apparaatconfiguratieprofiel <!-- 951708 -->   
Beheerders kunnen de firewall inschakelen voor apparaten, en ook verschillende protocollen voor domein-, privé- en openbare netwerken configureren.  Deze firewall-instellingen staan in het profiel 'Endpoint Protection'.

#### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>Windows Defender Application Guard helpt apparaten te beschermen tegen niet-vertrouwde websites, zoals gedefinieerd door uw organisatie <!-- 958257 -->   
Beheerders kunnen sites als 'vertrouwd' of 'zakelijk' definiëren met behulp van een Windows Information Protection-werkstroom of het nieuwe profiel 'Netwerkgrens' onder apparaatconfiguraties. Sites die niet in een vertrouwde netwerkgrens van een 64-bits Windows 10-apparaat staan, worden in een browser op een virtuele Hyper-V-computer geopend als ze met Microsoft Edge worden bekeken.

Application Guard staat in de apparaatconfiguratieprofielen, in het profiel 'Endpoint Protection'. Beheerders kunnen daar interactie configureren tussen de gevirtualiseerde browser en de hostcomputer, niet-vertrouwde sites en vertrouwde sites, en gegevens opslaan die in de gevirtualiseerde browser worden gegenereerd. Als u Application Guard op een apparaat wilt gebruiken, moet er eerst een netwerkgrens worden geconfigureerd. Het is belangrijk slechts één netwerkgrens te definiëren voor een apparaat.  

#### <a name="windows-defender-application-control-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>Windows Defender Application Control op Windows 10 Enterprise biedt een modus om alleen geautoriseerde apps te vertrouwen <!-- 1031096 -->    
Aangezien er elke dag duizenden nieuwe schadelijke bestanden worden gemaakt, biedt malwaredetectie op basis van handtekeningen misschien niet meer voldoende bescherming tegen nieuwe aanvallen. Met Windows Defender Application Control op Windows 10 Enterprise kunt u de apparaatconfiguratie wijzigen van een modus waarin apps worden vertrouwd tenzij ze door een antivirus- of andere beveiligingsoplossing worden geblokkeerd, naar een modus waarin het besturingssysteem alleen apps vertrouwt die door uw onderneming zijn geautoriseerd. In Windows Defender Application Control definieert u welke apps u vertrouwt.

Met Intune kunt u het toepassingsbeheerbeleid configureren in de modus 'Alleen controle' of in de modus 'Afdwingen'. Apps worden niet geblokkeerd wanneer ze in de modus 'Alleen controle' worden uitgevoerd. De modus 'Alleen controle' registreert alle gebeurtenissen in lokale clientlogboeken. U kunt ook configureren of alleen Windows-onderdelen en Microsoft Store-apps mogen worden uitgevoerd of dat aanvullende apps met een goede reputatie, zoals die is gedefinieerd door de Intelligent Security Graph, ook mogen worden uitgevoerd.

#### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10----1063615---"></a>Window Defender Exploit Guard is een nieuwe verzameling inbraakpreventiefuncties voor Windows 10 <!-- 1063615 -->   
Window Defender Exploit Guard omvat aangepaste regels om de exploiteerbaarheid van toepassingen te reduceren, voorkomt macro- en scriptbedreigingen, blokkeert automatisch netwerkverbindingen naar IP-adressen met een slechte reputatie, en kan gegevens uit ransomware en onbekende bedreigingen beveiligen. Windows Defender Exploit Guard bestaat uit de volgende onderdelen:

- **Attack Surface Reduction (ASR)** biedt regels waarmee u macro-, script- en e-mailbedreigingen kunt voorkomen.
- **Gecontroleerde maptoegang** blokkeert automatisch de toegang tot inhoud in beveiligde mappen.
- **Netwerkfilter** blokkeert uitgaande verbindingen van een app naar een IP/domein met een slechte reputatie
- **Exploit-beveiliging** biedt geheugen-, controlestroom- en beleidsbeperkingen die kunnen worden gebruikt om een toepassing te beschermen tegen aanvallen.


#### <a name="manage-powershell-scripts-in-intune-for-windows-10-devices----790537---"></a>PowerShell-scripts in Intune beheren voor Windows 10-apparaten <!-- 790537 -->

Met de Intune-beheeruitbreiding kunt u PowerShell-scripts uploaden in Intune om deze uit te voeren op Windows 10-apparaten. De uitbreiding is een aanvulling op de Windows 10 MDM-functionaliteit en maakt het eenvoudiger voor u om uw beheer te moderniseren. Zie [PowerShell-scripts in Intune beheren voor Windows 10-apparaten](intune-management-extension.md) voor meer informatie.

#### <a name="new-device-restriction-settings-for-windows-10---------1308850---"></a>Nieuwe apparaatbeperkingsinstellingen voor Windows 10      <!-- 1308850 -->
-    Berichten (alleen mobiel) - testen of MMS-berichten uitschakelen
-    Wachtwoord - instellingen om FIPS en het gebruik van secundaire Windows Hello-apparaten in te schakelen voor verificatie 
-    Weergave - instellingen om GDI-schaalbaarheid in of uit te schakelen voor verouderde apps

#### <a name="windows-10-kiosk-mode-device-restrictions----1308872---"></a>Apparaatbeperkingen Windows 10-kioskmodus <!-- 1308872 -->   
U kunt gebruikers van Windows 10-apparaten beperken tot de kioskmodus, zodat ze worden beperkt tot een verzameling vooraf gedefinieerde apps.  Om dit te doen, maakt u een Windows 10-apparaatbeperkingsprofiel en configureert u de kioskinstellingen.

De kioskmodus ondersteunt twee modi: **één app** (waarbij een gebruiker slechts één app mag uitvoeren) en **meerdere apps** (geeft toegang tot een verzameling apps).  U definieert het gebruikersaccount en de apparaatnaam, waarmee de ondersteunde apps worden bepaald.  Wanneer de gebruiker is aangemeld, is hij/zij beperkt tot de gedefinieerde apps.  Zie [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) voor meer informatie. 

De kioskmodus vereist het volgende:

- Intune moet de MDM-instantie zijn.
- De apps moeten al op het doelapparaat zijn geïnstalleerd.
- Het apparaat moet [goed ingericht](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions) zijn.

#### <a name="new-device-configuration-profile-for-creating-network-boundaries----1311967---"></a>Nieuw apparaatconfiguratieprofiel voor het maken van netwerkgrenzen <!-- 1311967 -->   
Bij uw andere apparaatconfiguratieprofielen vindt u een nieuw apparaatconfiguratieprofiel genaamd **Netwerkgrens**. Gebruik dit profiel om onlinebronnen te definiëren die u als zakelijk en vertrouwd wilt beschouwen. U moet een netwerkgrens voor een apparaat definiëren *voordat* functies zoals Windows Defender Application Guard en Windows Information Protection op het apparaat kunnen worden gebruikt. Het is belangrijk slechts één netwerkgrens te definiëren voor elk apparaat.

U kunt bedrijfscloudresources, IP-adresbereiken en interne proxyservers definiëren die u als vertrouwd wilt beschouwen. Nadat u de netwerkgrens hebt gedefinieerd, kan deze worden gebruikt door andere functies zoals Windows Defender Application Guard en Windows Information Protection.

####  <a name="two-additional-settings-for-windows-defender-antivirus----1338409---"></a>Twee aanvullende instellingen voor Windows Defender Antivirus <!-- 1338409 -->  
**Blokkeringsniveau voor bestanden**

| | |
|---|---|
| Niet geconfigureerd | **Niet geconfigureerd** gebruikt het standaard Windows Defender Antivirus-blokkeringsniveau en biedt sterke detectie zonder het risico te vergroten dat legitieme bestanden worden gedetecteerd. |
| Hoog | **Hoog** past een sterk detectieniveau toe.
| Hoog +  | **Hoog +** biedt het niveau Hoog met aanvullende beveiligingsmaatregelen die de clientprestaties kunnen beïnvloeden.
| Zero tolerance  | **Zero tolerance** blokkeert alle onbekende uitvoerbare bestanden. |

Als u dit op **Hoog** instelt, worden sommige legitieme bestanden misschien gedetecteerd, hoewel dit onwaarschijnlijk is.
Het is raadzaam het Blokkeringsniveau voor bestanden in te stellen op de standaardinstelling **Niet geconfigureerd**.

**Time-outverlenging voor het scannen van bestanden door de cloud**  

| | |
|--|--|
| Aantal seconden (0-50) | Geef op hoelang Windows Defender Antivirus een bestand maximaal moet blokkeren terwijl u op een resultaat van de cloud wacht. De standaardinstelling is 10 seconden: de aanvullende tijd die u hier opgeeft (tot 50 seconden) wordt toegevoegd aan die 10 seconden. In de meeste gevallen duurt de scan veel korter dan de maximuminstelling. Als u de tijd verlengt, kan de cloud verdachte bestanden grondig onderzoeken. Het is raadzaam deze instelling in te schakelen en ten minste 20 aanvullende seconden op te geven. |

#### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Citrix-VPN toegevoegd voor Windows 10-apparaten <!-- 1512457 -->  
U kunt Citrix-VPN configureren voor Windows 10-apparaten van klanten. U kunt de Citrix-VPN kiezen in de lijst *Een verbindingstype selecteren* in de blade **Basis-VPN** wanneer u een VPN voor Windows 10 en hoger configureert.

> [!Note]
> Citrix-configuratie bestond voor iOS en Android.

#### <a name="wi-fi-connections-support-pre-shared-keys-on-ios----1550823---"></a>Wi-Fi-verbindingen ondersteunen vooraf gedeelde sleutels voor iOS <!-- 1550823 -->
Klanten kunnen Wi-Fi-profielen configureren voor het gebruik van vooraf gedeelde sleutels (PSK) voor WPA/WPA2 persoonlijke verbindingen op iOS-apparaten. Deze profielen worden gepusht naar het apparaat van de gebruiker als het apparaat is ingeschreven bij Intune.

Wanneer het profiel naar het apparaat is gepusht, is de volgende stap afhankelijk van de profielconfiguratie.  Als automatische verbinding is ingesteld, wordt automatisch verbinding gemaakt zodra het netwerk nodig is.  Als handmatige verbinding is ingesteld, moet de gebruiker de verbinding handmatig activeren.  

### <a name="intune-apps"></a>Intune-apps

#### <a name="access-to-managed-app-logs-for-ios----1469920---"></a>Toegang tot de logboeken van de beheerde app voor iOS <!-- 1469920 -->
Eindgebruikers waarvoor de beheerde browser is geïnstalleerd kunnen de beheerstatus van alle gepubliceerde Microsoft-apps bekijken en logbestanden versturen om problemen met hun beheerde iOS-apps op te lossen.

Zie [Toegang tot de logboeken van de beheerde app voor iOS](app-configuration-managed-browser.md#how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios) voor meer informatie over het inschakelen van de probleemoplossingsmodus in de beheerde browser op een iOS-apparaat.

#### <a name="improvements-to-device-setup-workflow-in-the-company-portal-for-ios-in-version-290----1417174---"></a>Verbeteringen in de werkstroom voor apparaatinstellingen in de bedrijfsportal voor iOS in versie 2.9.0 <!-- 1417174 -->

De werkstroom voor apparaatinstellingen in de bedrijfsportal-app voor iOS is verbeterd. De taal is gebruiksvriendelijker en waar mogelijk hebben we schermen gecombineerd. De taal is ook specifieker voor uw bedrijf gemaakt door overal in de installatietekst de naam van uw bedrijf te gebruiken. U kunt deze bijgewerkte werkstroom zien op de  [pagina met nieuwe functies in de app](whats-new-app-ui.md).

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>De gebruikersentiteit bevat de meest recente gebruikersgegevens in het datawarehouse-gegevensmodel <!-- 1544273 -->
De eerste versie van het gegevensmodel Intune-datawarehouse bevat alleen recente, historische Intune-gegevens. Rapportopstellers kunnen de huidige status van een gebruiker niet vastleggen. In deze update wordt  **Gebruikersentiteit** ingevuld met de meest recente gebruikersgegevens.


## <a name="notices"></a>Mededelingen


### <a name="coming-soon-workflow-updates-to-intune-administration-ui"></a>Binnenkort beschikbaar: workflowupdates in de beheergebruikersinterface van Intune

Voor Intune wordt de beheerervaring bijgewerkt in de servicerelease van maart. U hoeft geen actie te ondernemen, maar omdat Microsoft ernaar streeft om transparant te zijn, wordt u wel op de hoogte gesteld. Als Android- of Apple-apparaatbeheer is ingeschakeld, verstuurt Intune apparaat- en gebruikersgegevens, zodat deze kunnen worden geïntegreerd in de externe services voor het beheren van apparaten. De verbeterde gebruikersinterface-ervaring voor beheerders uit de servicerelease van maart biedt meer inzicht in welke gegevens worden gedeeld. Deze wijzigingen aan de gebruikersinterface hebben geen gevolgen voor eindgebruikers.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?

Scenario's waarin toestemming moet worden gegeven om gegevens te delen, zijn:
- Wanneer u Android for Work inschakelt 
- Wanneer u Apple MDM-pushcertificaten inschakelt en uploadt 
- Bij het inschakelen van een van de Apple-services zoals Device Enrollment Program, School Manager en Volume Purchasing Program

In elk geval wordt de toestemming beperkt tot het uitvoeren van een MDM-service, bijvoorbeeld om te bevestigen dat een IT-beheerder heeft goedgekeurd dat Google- of Apple-apparaten worden ingeschreven. U vindt hier documentatie over welke informatie wordt gedeeld wanneer de nieuwe werkstromen live gaan:
- [Gegevens die Intune naar Google verzendt](data-intune-sends-to-google.md)
- [Gegevens die Intune naar Apple verzendt](data-intune-sends-to-apple.md)

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?

U hoeft niets te doen om u voor te bereiden op deze wijziging omdat er slechts sprake is van kleine aanpassingen aan de gebruikersinterface voor werkstromen. Zie het Trust Center (te openen via de koppeling Meer informatie) voor meer informatie over de GDPR-naleving van Microsoft.



### <a name="plan-for-change-update-where-you-configure-your-app-protection-policies"></a>Plan voor wijziging: bijwerken waar u uw app-beveiligingsbeleid configureert

Vanaf maart 2018 wordt u van de serviceblade Intune-app-beveiliging in Azure Portal tijdelijk omgeleid naar de blade Mobiele app in Intune in Azure Portal. Al uw beleidsregels voor de beveiliging van apps staan al in de blade Mobiele app in Intune onder App-configuratie. Het enige verschil is dat u naar Intune gaat in plaats van naar Intune-app-beveiliging. In april wordt deze omleiding beëindigd en wordt de serviceblade Intune-app-beveiliging definitief verwijderd. De gegevens die nu in Intune zijn geïntegreerd, worden gedupliceerd. 

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Deze wijziging is van invloed op zowel zelfstandige als hybride klanten (Intune met Configuration Manager) van Intune. Door deze integratie wordt het beheer van uw cloud vereenvoudigd. U kunt groepen, beleidsregels, apps en mobiele apparaten voortaan vanaf één blade in Azure, de blade Intune, beheren.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
Label Intune als favoriet in plaats van de serviceblade Intune-app-beveiliging en zorg ervoor dat u bekend bent met de werkstroom voor het beleid voor app-beveiliging in de blade Mobiele app in Intune. U wordt slechts tijdelijk omgeleid. De blade App-beveiliging wordt uiteindelijk verwijderd. Alle beleidsregels voor de beveiliging van apps staan al in Intune en u kunt uw beleid voor voorwaardelijke toegang wijzigen aan de hand van de volgende documentatie: [https://aka.ms/azuread_ca](https://aka.ms/azuread_ca).

**Aanvullende informatie**: [https://aka.ms/intuneapppolicy](https://aka.ms/intuneapppolicy)

### <a name="updated-new-security-enhancements-in-the-intune-service-----1637539---"></a>Bijgewerkt: nieuwe verbeteringen in de beveiliging van de Intune-service <!-- 1637539 -->   

Verbeteringen in de beveiliging van de Intune-service worden uitgerold. Als onderdeel van deze wijziging is in de update van maart in de Intune-service een wisselknop beschikbaar in Intune op de Azure-console om deze beveiligingsfunctie in of uit te schakelen. Als deze functie is ingeschakeld, worden apparaten waaraan geen nalevingsbeleid is toegewezen gemarkeerd als Niet-compatibel.

**Hybride klanten**: deze wijziging wordt momenteel niet geïntroduceerd voor hybride klanten. U hoeft verder niets te doen. Het wordt echter ten zeerste aangeraden ervoor te zorgen dat er ten minste één nalevingsbeleid aan uw apparaten is toegewezen.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?

Wanneer we deze wijziging uitrollen in de update van maart, hangt de invloed van deze wijziging ervan af of u wel of niet een nalevingsbeleid hebt toegewezen.

- Als u een nieuwe of bestaande tenant bent en geen nalevingsbeleid aan uw apparaten hebt toegewezen, wordt de wisselknop automatisch ingesteld op **Compatibel**. De functie wordt standaard uitgeschakeld als standaardinstelling in de console. Dit heeft geen gevolgen voor eindgebruikers.
- Als u een bestaande tenant bent en u apparaten hebt waaraan een nalevingsbeleid is toegewezen, wordt de wisselknop automatisch ingesteld op Niet-compatibel. Zodra de update van maart is uitgerold, is deze functie beschikbaar als standaardinstelling. 

Als u nalevingsbeleid met voorwaardelijke toegang (CA) gebruikt en deze functie is ingeschakeld, worden apparaten waaraan niet ten minste één nalevingsbeleid is toegewezen, door CA geblokkeerd. Eindgebruikers die zijn gekoppeld aan deze apparaten en eerder toegang hadden tot e-mail, raken deze toegang kwijt tenzij u ten minste één nalevingsbeleid aan alle apparaten toewijst.   
 
#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?  

Als u voorwaardelijke toegang gebruikt, raden wij aan dat u deze functie inschakelt en de wisselknop instelt op **Niet-compatibel**. Om te voorkomen dat uw eindgebruikers geen toegang meer tot e-mail hebben, moet u ervoor zorgen dat aan alle apparaten ten minste één nalevingsbeleid is toegewezen. Hier volgen enkele wijzigingen die we doorvoeren zodat u dit kunt doen:   

- In de Intune-portal vindt u een rapport met de naam **Apparaten zonder nalevingsbeleid**, waarmee u alle apparaten in uw omgeving kunt identificeren waaraan geen nalevingsbeleid is toegewezen. 
- De optie **Alle gebruikers** is beschikbaar, waarmee u eenvoudig een nalevingsbeleid aan alle gebruikers kunt toewijzen.

Als u de wisselknop uitgeschakeld laat, hoeft u verder niets te doen.

**Aanvullende informatie**: [https://aka.ms/compliance_policies](https://aka.ms/compliance_policies)

### <a name="plan-for-change-change-in-support-for-the-microsoft-intune-app-sdk-for-cordova-plugin"></a>Plannen voor wijziging: wijziging in de ondersteuning voor Microsoft Intune App SDK voor Cordova-invoegtoepassing
Intune beëindigt de ondersteuning voor de [Microsoft Intune App SDK Cordova-invoegtoepassing](app-sdk-cordova.md) op 1 mei 2018. We raden u aan in plaats daarvan de Intune App Wrapping Tool te gebruiken om uw op Cordova gebaseerde apps voor te bereiden op beheerbaarheid en beschikbaarheid in Intune. Zodra deze wijziging is doorgevoerd, wordt de Microsoft Intune APP SDK voor de Cordova-invoegtoepassing niet langer onderhouden en worden er geen updates meer voor gegeven. App-ontwikkelaars kunnen deze invoegtoepassing dan niet langer gebruiken. Intune is van plan apps die met Cordova zijn gebouwd te blijven ondersteunen. Alle apps die zijn gebouwd met Microsoft Intune APP SDK voor de Cordova-invoegtoepassing zullen echter kampen met beperkte functionaliteit in Intune. Nadat u apps hebt verpakt met de Intune App Wrapping Tool, kunnen deze apps zoals u gewend bent voor eindgebruikers worden geïmplementeerd. Voor Android-apps op basis van Cordova die in de Google Play Store worden gepubliceerd, geldt het volgende:
- Wanneer eindgebruikers de app voor het eerst starten, moeten ze referenties opgeven om het Intune-beleid te ontvangen.
- Apps moeten gericht op Intune-gebruikers worden gepubliceerd in de App Store, bijvoorbeeld ‘Contoso-app voor Intune’. 

Zie [App Wrapping Tool voor iOS](app-wrapper-prepare-ios.md) en [App Wrapping Tool voor Android](app-wrapper-prepare-android.md) voor meer informatie over de App Wrapping Tool. Voor eventuele problemen of vragen neemt u contact op met [msintuneappsdk@microsoft.com](mailto:msintuneappsdk@microsoft.com). 

### <a name="plan-for-change-use-intune-on-azure-now-for-your-mdm-management----1227338---"></a>Wijzigingsplannen: u kunt Intune op Azure nu gebruiken voor uw MDM-beheer <!-- 1227338 -->
Een jaar geleden hebben we de [openbare preview van Intune op Azure](https://cloudblogs.microsoft.com/enterprisemobility/2016/12/07/public-preview-of-intune-on-azure/) aangekondigd en zes maanden geleden hebben we deze opgevolgd met de [algemene beschikbaarheid van de nieuwe beheerderservaring](https://cloudblogs.microsoft.com/enterprisemobility/2017/06/08/the-new-intune-and-conditional-access-admin-consoles-are-ga/) voor Intune. Vanaf 31 augustus 2018 wordt MDM (Mobile Device Management) uitgeschakeld in de klassieke Silverlight-console voor klanten met de zelfstandige versie van Intune. In plaats daarvan kunt u [Intune op Azure](https://aka.ms/Intune_on_Azure) gebruiken voor MDM. Als u nog steeds de klassieke console voor MDM gebruikt, moet u hiermee stoppen en uzelf vertrouwd maken met Intune op Azure. We verwachten niet dat deze wijziging gevolgen heeft voor eindgebruikers. Klassiek pc-beheer blijft in Silverlight nog gewoon aanwezig. U vindt [hier](https://aka.ms/Intune_on_Azure_mdm) meer informatie over deze wijziging en over eventuele gevolgen voor u.


### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731-eeready--"></a>Android for Work-apparaten onafhankelijk van de Android-apparaten beheren<!-- 1490731 EEready-->    
**Opmerking**: De volgende wijzigingen gaan van start bij de update van november, maar de uitvoering ervan voor uw account kan nog wel even duren. U ontvangt een bevestigingsbericht in de Office 365-portal wanneer deze wijzigingen voor uw account van kracht zijn. Na de implementatie hebt u aanvullende beheeropties. Er zijn geen wijzigingen in de ervaringen van de eindgebruiker tijdens de implementatie.

Intune ondersteunt het inschrijvingsbeheer voor Android for Work-apparaten onafhankelijk van het Android-platform. Deze instellingen worden beheerd onder **Apparaatinschrijving** > **Inschrijvingsbeperkingen** > **Apparaattypebeperkingen**. (Ze bevonden zich eerder onder **Apparaatinschrijving** > **Android for Work-inschrijving** > **Android for Work-inschrijvingsinstellingen**.)

Standaard zijn instellingen voor uw Android for Work-apparaten gelijk aan de instellingen voor uw Android-apparaten. Wanneer u echter uw Android for Work-instellingen wijzigt, is dat niet meer het geval.

Als u een persoonlijke Android for Work-inschrijving blokkeert, kunnen alleen zakelijke Android-apparaten worden ingeschreven als Android for Work.

Bedenk de volgende punten wanneer u met de nieuwe instellingen werkt:

#### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Als u nog nooit een Android for Work-inschrijving hebt toegevoegd

Het nieuwe Android for Work-platform wordt geblokkeerd in de standaard apparaattypebeperkingen. Wanneer u de functie toevoegt, kunt u de Android for Work-inschrijving van apparaten toestaan. Hiervoor wijzigt u de standaardinstelling of maakt u een nieuwe apparaattypebeperking ter vervanging van de standaard apparaattypebeperking.

#### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Als u de Android for Work-inschrijving hebt toegevoegd

Als u dit al eerder hebt gedaan, is uw situatie afhankelijk van de instelling die u hebt gekozen:

| Instelling | De status van Android for Work bij een standaard apparaattypebeperking | Opmerkingen |
| --- | --- | --- |
| **Alle apparaten beheren als Android** | Geblokkeerd | U mag geen Android-apparaten bij Android for Work hebben ingeschreven. |
| **Ondersteunde apparaten beheren als Android for Work** | Toegestaan | Alle Android-apparaten die ondersteuning bieden voor Android for Work moeten zijn ingeschreven bij Android for Work. |
| **Alleen ondersteunde apparaten voor de gebruikers in deze groepen beheren als Android for Work** | Geblokkeerd | Er is een afzonderlijk beleid voor apparaattypebeperkingen gemaakt om de standaardinstelling te overschrijven. Dit beleid bepaalt de groepen die u eerder hebt geselecteerd om Android for Work-inschrijving toe te staan. Gebruikers binnen de geselecteerde groepen mogen hun Android for Work-apparaten blijven inschrijven. Alle andere gebruikers worden uitgesloten van inschrijving bij Android for Work. |

In alle gevallen blijft uw beoogde regel behouden. Er is geen actie vereist van uw kant om de globale of groepsgewijze toestemming voor Android for Work in uw omgeving te handhaven.

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Rechtstreekse toegang tot Apple-scenario's voor inschrijving <!--951869-->
Voor Intune-accounts die na januari 2017 zijn gemaakt, heeft Intune rechtstreekse toegang ingeschakeld tot Apple-inschrijvingsscenario's. Hiervoor is de werkstroom voor het inschrijven van apparaten gebruikt in Azure Portal. Voorheen was de Apple-inschrijvingspreview alleen toegankelijk via koppelingen in de klassieke Intune-portal. Intune-accounts die vóór januari 2017 zijn gemaakt, moeten eenmalig worden gemigreerd om de functies in Azure beschikbaar te maken. De planning voor de migratie is nog niet aangekondigd, maar de informatie wordt zo snel mogelijk beschikbaar gemaakt. Het wordt aangeraden om een testaccount te maken om de nieuwe ervaring te testen als u met uw bestaande account geen toegang hebt tot Azure Portal.

## <a name="whats-coming"></a>Binnenkort

### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866--"></a>Update van de gebruikerservaring voor de bedrijfsportal-app voor iOS<!--1412866-->

We zullen een grote update uitbrengen van de gebruikerservaring voor de bedrijfsportal-app voor iOS. De update heeft een volledig nieuw visueel ontwerp, waaronder een gemoderniseerde uitstraling met verbeterde bruikbaarheid en toegankelijkheid. De huidige functionaliteit van de iOS-bedrijfsportal-app blijft behouden.

We bieden een voorlopige versie van de bijgewerkte bedrijfsportal-app voor iOS via het Apple TestFlight-programma. U kunt deze versie gebruiken en uw feedback geven. Meld u aan bij https://aka.ms/intune_ios_cp_testflight voor toegang tot TestFlight.

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple vereist updates voor Application Transport Security <!--748318-->
Apple heeft aangekondigd dat specifieke vereisten gaan gelden voor Application Transport Security (ATS). ATS wordt gebruikt om betere beveiliging af te dwingen voor alle app-communicatie die verloopt via HTTPS. Deze wijziging heeft gevolgen voor Intune-klanten die de bedrijfsportal-app gebruiken op iOS.

Een versie van de bedrijfsportal-app is beschikbaar gemaakt voor iOS via het Apple TestFlight-programma waarmee naleving van de nieuwe ATS-vereisten wordt afgedwongen. Als u dit wilt proberen zodat u uw ATS-compatibiliteit kunt testen, stuurt u een e-mail naar <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app"> CompanyPortalBeta@microsoft.com </a> met uw voornaam, achternaam, e-mailadres en bedrijfsnaam. Bekijk ons [Intune-ondersteuningsblog](https://aka.ms/compportalats) voor meer informatie.

## <a name="see-also"></a>Zie ook
* [Microsoft Intune-blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Roadmap voor cloudplatform](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Wat is er nieuw in de gebruikersinterface van de bedrijfsportal?](whats-new-app-ui.md)
* [Wat was er in de vorige maanden nieuw](whats-new-archive.md)
