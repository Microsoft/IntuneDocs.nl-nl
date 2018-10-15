---
title: Wat was er de vorige maanden nieuw in Microsoft Intune - Azure | Microsoft Docs
titlesuffix: ''
description: Raadpleeg oudere berichten op de Wat is er nieuw-pagina voor Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/12/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9ba01d60-4a03-4e3e-9aba-8be905c0054c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b49a7d83e543855ca9f68426adc979079bbcfc17
ms.sourcegitcommit: 5bfc7a1375fdb2992b9b5d4f6d1b34eec12457ae
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/13/2018
ms.locfileid: "45533724"
---
# <a name="whats-new-in-the-microsoft-intune---previous-months"></a>Wat is er nieuw in Microsoft Intune - vorige maanden

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="march-2018"></a>maart 2018

### <a name="app-management"></a>Appbeheer

#### <a name="alerts-for-expiring-ios-line-of-business-lob-apps-for-microsoft-intune----748789---"></a>Waarschuwingen voor iOS LOB-apps (Line-of-Business) voor Microsoft Intune die verlopen <!-- 748789 -->

In Azure Portal waarschuwt Intune u met betrekking tot iOS line-of-business-apps die bijna verlopen. Nadat een nieuwe versie van de iOS line-of-business-app is geüpload, verwijdert Intune de melding over het verlopen uit de lijst met apps. Deze melding wordt alleen actief voor recent geüploade iOS Line-Of-Business-apps. Een waarschuwing wordt 30 dagen voordat het inrichtingsprofiel voor iOS line-of-business-app verloopt, weergegeven. Zodra het profiel is verlopen, wijzigt de waarschuwing in Verlopen.

#### <a name="customize-your-company-portal-themes-with-hex-codes---1049561---"></a>De bedrijfsportalthema's aanpassen met hexadecimale codes <!--1049561 -->

U kunt de themakleur in de bedrijfsportal-apps aanpassen met hexadecimale codes. Wanneer u de hexadecimale code invoert, wordt door Intune bepaald met welke tekstkleur de hoogste mate van contrast tussen de tekstkleur en de achtergrondkleur wordt bereikt. U kunt in **Client-apps** > **Bedrijfsportal** bekijken hoe de tekstkleur en uw bedrijfslogo bij deze kleur worden weergegeven.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise----1813081---"></a>App-toewijzing op basis van groepen opnemen en uitsluiten voor Android Enterprise <!-- 1813081 -->

Android Enterprise (voorheen bekend als Android for Work) ondersteunt het opnemen en uitsluiten van groepen, maar biedt geen ondersteuning voor de vooraf gemaakte ingebouwde groepen **Alle gebruikers** en **Alle apparaten**. Zie [App-toewijzingen opnemen en uitsluiten in Microsoft Intune](apps-inc-exl-assignments.md) voor meer informatie.


### <a name="device-management"></a>Apparaatbeheer

### <a name="export-all-devices-into-csv-files-in-ie-edge-or-chrome----2258071---"></a>Alle apparaten exporteren naar CSV-bestanden in Internet Explorer, Microsoft Edge of Chrome <!-- 2258071 -->
In **Apparaten** > **Alle apparaten** kunt u de apparaten **Exporteren** naar een lijst met de CSV-indeling. Gebruikers van Internet Explorer (IE) met meer dan 10.000 apparaten kunnen hun apparaten exporteren naar meerdere bestanden. Elk bestand bevat maximaal 10.000 apparaten.

Gebruikers van Edge en Chrome met meer dan 30.000 apparaten kunnen hun apparaten exporteren naar meerdere bestanden. Elk bestand bevat maximaal 30.000 apparaten.

[Apparaten beheren](device-management.md) biedt meer details over wat u kunt doen met apparaten die u beheert.

#### <a name="new-security-enhancements-in-the-intune-service-----1637539---"></a>Verbeteringen in de beveiliging van de Intune-service <!-- 1637539 -->   

Er is een wisselknop in Intune geïntroduceerd waarmee zelfstandige klanten van Intune zonder dat een beleid is toegewezen apparaten kunnen behandelen als **Compatibel** (beveiligingsfunctie uitgeschakeld) of als **Niet compatibel** (beveiligingsfunctie ingeschakeld). Hierdoor kan alleen toegang tot de resources worden verkregen nadat de compatibiliteit van het apparaat is geëvalueerd.

De invloed van deze functies verschilt, afhankelijk of u al nalevingsbeleid hebt toegewezen of niet.

- Als u een nieuw of bestaand account hebt en geen nalevingsbeleid aan uw apparaten hebt toegewezen, wordt de wisselknop automatisch ingesteld op **Compatibel**. De functie wordt standaard uitgeschakeld als standaardinstelling in de console. Dit heeft geen gevolgen voor eindgebruikers.
- Als u een bestaand account hebt en u apparaten hebt waaraan een nalevingsbeleid is toegewezen, wordt de wisselknop automatisch ingesteld op **Niet-compatibel**. Zodra de update van maart is uitgerold, is deze functie beschikbaar als standaardinstelling.

Als u nalevingsbeleid met voorwaardelijke toegang (CA) gebruikt en deze functie is ingeschakeld, worden apparaten waaraan niet ten minste één nalevingsbeleid is toegewezen, door CA geblokkeerd. Eindgebruikers die zijn gekoppeld aan deze apparaten en eerder toegang hadden tot e-mail, raken deze toegang kwijt tenzij u ten minste één nalevingsbeleid aan alle apparaten toewijst.   

Hoewel de standaard status in-/uitschakelen wordt weergegeven in de gebruikersinterface na de update van maart, wordt deze status niet direct afgedwongen. Eventuele wijzigingen die u in de wisselknop aanbrengt, hebben geen invloed op de compatibiliteit van apparaten totdat de wisselknop in uw account werkt. In Berichtencentrum vindt u informatie over wanneer uw account is bijgewerkt. Dit kan enkele dagen duren nadat uw Intune-service is bijgewerkt voor maart.

**Aanvullende informatie**: [https://aka.ms/compliance_policies](https://aka.ms/compliance_policies)

#### <a name="enhanced-jailbreak-detection----846515---"></a>Verbeterde jailbreakdetectie <!-- 846515 -->

Verbeterde jailbreak-detectie is een nieuwe nalevingsinstelling die de manier waarop Intune opengebroken apparaten evalueert, verbetert. De instelling zorgt ervoor dat het apparaat regelmatiger incheckt bij Intune, waarvoor de locatieservices van het apparaat worden gebruikt. Ook heeft dit invloed op het batterijvermogen.

#### <a name="reset-passwords-for-android-o-devices----1238299---"></a>Wachtwoorden voor Android O-apparaten opnieuw instellen <!-- 1238299 -->
U kunt de wachtwoorden voor ingeschreven Android 8.0-apparaten opnieuw instellen met werkprofielen. Wanneer u een aanvraag Wachtwoord opnieuw instellen naar een Android 8.0-apparaat verzendt, wordt hiermee een nieuw wachtwoord voor het ontgrendelen van het apparaat of een vraag voor het beheerde profiel ingesteld voor de huidige gebruiker. Het wachtwoord of de vraag wordt verzonden en is onmiddellijk van kracht.

#### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Nalevingsbeleid afstemmen op apparaten in apparaatgroepen <!--1307012 -->

U kunt nalevingsbeleid richten op gebruikers in gebruikersgroepen. Met deze update kunt u nalevingsbeleid richten op apparaten in apparaatgroepen. Apparaten waarop beleid is gericht als onderdeel van apparaatgroepen, ontvangen geen maatregelen voor naleving.

#### <a name="new-management-name-column----1333586---"></a>Nieuwe kolom Naam voor beheer <!-- 1333586 -->
 Een nieuwe kolom met de naam **Naam voor beheer** is beschikbaar op de blade voor apparaten. Dit is een automatisch gegenereerde, niet bewerkbare naam die per apparaat wordt toegewezen op basis van de volgende formule:
- Standaardnaam voor alle apparaten: <username><em><devicetype></em><enrollmenttimestamp>
- Voor bulksgewijs toegevoegde apparaten: < PackageId/ProfileId ><em><DeviceType></em><EnrollmentTime>

Dit is een optionele kolom in de blade voor apparaten. Deze is niet standaard beschikbaar en u kunt de kolom alleen openen via de kolomkiezer. De naam van het apparaat wordt niet beïnvloed door deze nieuwe kolom.

#### <a name="ios-devices-are-prompted-for-a-pin-every-15-minutes---1550837---"></a>Op iOS-apparaten wordt elke vijftien minuten om een pincode gevraagd <!--1550837 -->
Nadat een nalevings- of configuratiebeleid op een iOS-apparaat is toegepast, wordt gebruikers elke vijftien minuten gevraagd een pincode in te stellen. Gebruikers wordt continu gevraagd een pincode in te stellen totdat de code is ingesteld.

#### <a name="schedule-your-automatic-updates---1805514---"></a>Automatische updates plannen <!--1805514 -->
In Intune kunt u met behulp van de [instellingen voor Windows 10-updatering](windows-update-for-business-configure.md) bepalen hoe automatische updates worden geïnstalleerd. Met deze update kunt u terugkerende updates plannen en de week, de dag en het tijdstip opgeven.

#### <a name="use-fully-distinguished-name-as-subject-for-scep-certificate---2221763---"></a>De volledige DN-naam gebruiken als onderwerp voor het SCEP-certificaat <!--2221763 -->
Wanneer u een SCEP-certificaatprofiel maakt, voert u de naam van het onderwerp in. Met deze update kunt u als naam van het onderwerp de volledige DN-naam gebruiken. Selecteer **Aangepast** bij **Onderwerpnaam** en voer `CN={{OnPrem_Distinguished_Name}}` in. Als u de variabele `{{OnPrem_Distinguished_Name}}` wilt gebruiken, moet u het gebruikerskenmerk `onpremisesdistingishedname` met behulp van [Azure Active Directory (AD) Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) synchroniseren met uw exemplaar van Azure AD.

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="enable-bluetooth-contact-sharing---android-for-work---1098983---"></a>Delen van contactpersonen via Bluetooth inschakelen - Android for Work <!--1098983 -->
Standaard wordt op Android-apparaten voorkomen dat contactpersonen in het werkprofiel kunnen worden gesynchroniseerd met Bluetooth-apparaten. Als gevolg hiervan worden contactpersonen in het werkprofiel niet weergegeven bij Nummerweergave voor Bluetooth-apparaten.

Er is een nieuwe instelling in **Android for Work** > **Apparaatbeperkingen** > **Instellingen voor werkprofiel**:
- Contactpersoon delen via Bluetooth

De Intune-beheerder kan deze instellingen configureren om delen in te schakelen. Dit is handig als u een apparaat wilt koppelen met een Bluetooth-apparaat in auto's waarop Nummerweergave wordt weergegeven voor handsfreegebruik. Als deze instellingen zijn ingeschakeld, worden de contactpersonen voor het werkprofiel weergegeven. Als deze instellingen niet zijn ingeschakeld, worden de contactpersonen voor het werkprofiel niet weergegeven.

#### <a name="configure-gatekeeper-to-control-macos-app-download-source----1690459---"></a>Gatekeeper configureren om de downloadbron van macOS-apps te beheren <!-- 1690459 -->

U kunt Gatekeeper configureren om uw apparaten te beveiligen tegen apps door te bepalen waarvan de apps kunnen worden gedownload. U kunt de volgende downloadbronnen configureren: **Mac App Store**, **Mac App Store en geïdentificeerde ontwikkelaars** of **Overal**. U kunt ook configureren of gebruikers een app kunnen installeren door middel van CTRL+klikken om deze Gatekeeper-voorzieningen te overschrijven.

Deze instellingen zijn te vinden onder **Apparaatconfiguratie** -> **Profiel maken** -> **macOS**  ->  **Eindpuntbeveiliging**.

#### <a name="configure-the-mac-application-firewall----1690461---"></a>De firewall van Mac-toepassingen configureren <!-- 1690461 -->

U kunt de firewall van Mac-toepassingen configureren. U kunt deze gebruiken om verbindingen per toepassing te controleren, in plaats van per poort. Zo kunt u beter profiteren van de voordelen van firewallbeveiliging. Bovendien helpt het te voorkomen dat ongewenste apps gebruikmaken van netwerkpoorten die zijn geopend voor legitieme apps.

Deze functie kunt u vinden onder **Apparaatconfiguratie** -> **Profiel maken** -> **macOS** -> **Eindpuntbeveiliging**.

Wanneer u de Firewall-instelling hebt ingeschakeld, kunt u de firewall configureren met behulp van twee strategieën:

- Alle binnenkomende verbindingen blokkeren

   U kunt alle binnenkomende verbindingen voor de doelapparaten blokkeren. Als u ervoor kiest om dit te doen, worden binnenkomende verbindingen voor alle apps geblokkeerd.

- Specifieke apps blokkeren of toestaan

   U kunt specifieke apps toestemming geven binnenkomende verbindingen te ontvangen of u kunt apps blokkeren. U kunt ook de verborgen modus inschakelen om reacties op peilverzoeken te voorkomen.

####  <a name="detailed-error-codes-and-messages----1376342---"></a>Gedetailleerde foutcodes en -berichten <!-- 1376342 -->

In uw apparaatconfiguratie kunnen gedetailleerde foutcodes en -berichten worden weergegeven. In deze verbeterde rapportage worden de instellingen, de status van deze instellingen en details over probleemoplossing weergegeven.

##### <a name="more-information"></a>Meer informatie

- Alle binnenkomende verbindingen blokkeren

   Hiermee worden alle services voor delen (zoals delen van bestanden en delen van het scherm) geblokkeerd en kunnen deze geen binnenkomende verbindingen ontvangen. De systeemservices die nog steeds binnenkomende verbindingen kunnen ontvangen, zijn:
  - configd - implementeert DHCP en andere services voor netwerkconfiguratie
  - mDNSResponder - implementeert Bonjour
  - racoon - implementeert IPSec

    Als u services voor delen wilt gebruiken, zorgt u ervoor dat **Binnenkomende verbindingen** is ingesteld op **Niet geconfigureerd** (niet op **Blokkeren**).

- Verborgen modus

   Schakel deze optie in om te voorkomen dat de computer reageert op peilverzoeken. De computer reageert nog wel op binnenkomende verzoeken voor toegestane apps. Onverwachte aanvragen, zoals ICMP (ping), worden genegeerd.

#### <a name="disable-checks-on-device-restart---1805490---"></a>Controles bij opnieuw starten van apparaat uitschakelen <!--1805490 -->
In Intune kunt u [software-updates beheren]](windows-update-for-business-configure.md). In deze update is de eigenschap <strong>Controles voor opnieuw starten</strong> beschikbaar en standaard ingeschakeld. Als u de standaardcontroles wilt overslaan die worden uitgevoerd wanneer u een apparaat opnieuw start (controle van actieve gebruikers, batterijniveau, enzovoort), selecteert u <strong>Overslaan</strong>.

#### <a name="new-windows-10-insider-preview-channels-available-for-deployment-rings----1746293---"></a>Nieuwe Windows 10 Insider Preview-kanalen beschikbaar voor implementatieringen <!-- 1746293 -->
U kunt nu de volgende Windows 10 Insider Preview-onderhoudskanalen selecteren wanneer u een Windows 10-implementatiering maakt:
- Windows Insider build &#8208; Snel
- Windows Insider build &#8208; Langzaam
- Windows Insider-build vrijgeven 

Zie [Insider Preview-builds beheren](https://insider.windows.com/for-business-organization-admin/) voor meer informatie over deze kanalen.   
Zie [Software-updates beheren in Intune](windows-update-for-business-configure.md) voor meer informatie over het maken van implementatiekanalen in Intune.

### <a name="new-windows-defender-exploit-guard-settings----1631893---"></a>Nieuwe instellingen voor Windows Defender Exploit Guard <!-- 1631893 -->

Zes nieuwe instellingen voor <strong>Kwetsbaarheid voor aanvallen verminderen</strong> en uitgebreide mogelijkheden voor <strong>Gecontroleerde mappentoegang: mapbeveiliging</strong> zijn nu beschikbaar. Deze instellingen kunt u vinden op: Apparaatconfiguratie\Profielen\
Profiel maken\Endpoint Protection\Windows Defender Exploit Guard.

#### <a name="attack-surface-reduction"></a>Kwetsbaarheid voor aanvallen verminderen

|Naam van de instelling  |Instellingsopties  |Beschrijving  |
|---------|---------|---------|
|Geavanceerde ransomwarebeveiliging|Ingeschakeld, Controleren, Niet geconfigureerd|Gebruik agressieve ransomwarebeveiliging.|
|Referentiediefstal in het Windows-subsysteem voor de lokale beveiligingsautoriteit markeren|Ingeschakeld, Controleren, Niet geconfigureerd|Markeer referentiediefstal in het Windows-subsysteem voor de lokale beveiligingsautoriteit (lsass.exe).|
|Het maken van processen met PSExec- en WMI-opdrachten|Blokkeren, Controleren, Niet geconfigureerd|Blokkeer het maken van processen die afkomstig zijn van PSExec- en WMI-opdrachten.|
|Niet-vertrouwde en niet-ondertekende processen die worden uitgevoerd vanaf een USB|Blokkeren, Controleren, Niet geconfigureerd|Blokkeer niet-vertrouwde en niet-ondertekende processen die worden uitgevoerd vanaf een USB.|
|Uitvoerbare bestanden die niet voldoen aan een bepaalde gangbaarheid, ouderdom of aan criteria voor vertrouwde lijsten blokkeren|Blokkeren, Controleren, Niet geconfigureerd|Voorkomen dat uitvoerbare bestanden worden uitgevoerd tenzij deze voldoen aan een bepaalde gangbaarheid, ouderdom of criteria voor vertrouwde lijsten.|

#### <a name="controlled-folder-access"></a>Gecontroleerde mappentoegang

|              Naam van de instelling               |                                                              Instellingsopties                                                              | Beschrijving |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Mapbeveiliging (al geïmplementeerd) | Niet geconfigureerd, Inschakelen, Alleen controleren (al geïmplementeerd)<br><br> <strong>Nieuw</strong><br>Schijfwijziging blokkeren, schijfwijziging controleren |             |

Beveilig bestanden en mappen tegen niet-geautoriseerde wijzigingen door niet-goedgekeurde apps.<br><br>**Inschakelen**: voorkom dat bestanden in beveiligde mappen door niet-vertrouwde apps worden gewijzigd of verwijderd en dat gegevens door deze apps naar schijfsectoren worden weggeschreven.<br><br>
**Alleen schijfwijziging blokkeren**:<br>Voorkom dat gegevens door niet-vertrouwde apps worden weggeschreven naar schijfsectoren. Bestanden in beveiligde mappen kunnen nog steeds door niet-vertrouwde apps worden gewijzigd of verwijderd.|

### <a name="intune-apps"></a>Intune-apps

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Azure Active Directory-websites kunnen de Intune Managed Browser-app vereisen en ondersteunen eenmalige aanmelding voor de Managed Browser (openbare preview) <!-- 710595 -->

Met Azure Active Directory (Azure AD) kunt u nu de toegang tot websites op mobiele apparaten beperken tot de Intune Managed Browser-app. In de Managed Browser blijven websitegegevens veilig en gescheiden van de persoonlijke gegevens van eindgebruikers. Daarnaast ondersteunt de Managed Browser eenmalige aanmelding voor sites die door Azure AD worden beveiligd. Door u aan te melden bij de Managed Browser of door de Managed Browser op een apparaat te gebruiken met een andere app die door Intune wordt beheerd, krijgt de Managed Browser toegang tot bedrijfssites die door Azure AD worden beveiligd, zonder dat de gebruiker referenties hoeft in te voeren. Deze functionaliteit is van toepassing op sites zoals Outlook Web Access (OWA) en SharePoint Online, evenals andere bedrijfssites zoals intranetbronnen die via de Azure App Proxy worden geopend. Zie [Besturingselementen voor toegang in Azure Active Directory Voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-controls) voor meer informatie.

#### <a name="company-portal-app-for-android-visual-updates---976944---"></a>Bedrijfsportal-app voor visuele Android-updates <!--976944 -->

De bedrijfsportal-app voor Android is bijgewerkt om de richtlijnen voor [Ontwerp van materiaal](https://material.io/) van Android te volgen. In het Engelstalige artikel [What's new in app UI](whats-new-app-ui.md) (Nieuw in de gebruikersinterface van de app) kunt u afbeeldingen van de nieuwe pictogrammen bekijken.

#### <a name="company-portal-enrollment-improved----1874230-eeready--"></a>Inschrijving bedrijfsportal verbeterd <!-- 1874230 eeready-->
Gebruikers die een apparaat inschrijven via de bedrijfsportal in Windows 10-build 1703 en hoger, kunnen de eerste stap van de inschrijving voltooien zonder de app te verlaten.
#### <a name="hololens-and-surface-hub-now-appear-in-device-lists---1725868---"></a>HoloLens en Surface Hub nu worden weergegeven in de apparaatlijsten <!--1725868 -->
Er is ondersteuning toegevoegd voor het weergeven van HoloLens- en Surface Hub-apparaten die via Intune zijn geregistreerd bij de bedrijfsportal-app voor Android.

#### <a name="custom-book-categories-for-volume-purchase-program-vpp-ebooks----1488911---"></a>Aangepaste boekcategorieën voor eBooks in het VPP-programma (volume-aankoopprogramma) <!-- 1488911 -->
U kunt aangepaste eBook-categorieën maken en vervolgens VPP eBooks toewijzen aan deze aangepaste eBook-categorieën. Eindgebruikers kunnen de nieuwe eBook-categorieën en de boeken die zijn toegewezen aan de categorieën bekijken. Zie [Apps en boeken met Microsoft Intune beheren die via het Volume Purchase Program zijn gekocht](vpp-apps.md) voor meer informatie.  

#### <a name="support-changes-for-company-portal-app-for-windows-send-feedback-option----2070166---"></a>Optie voor feedback verzenden voor wijzigingen in de ondersteuning voor de bedrijfsportal-app voor Windows<!-- 2070166 -->
Vanaf 30 april 2018 werkt de optie **Feedback verzenden** in de bedrijfsportal-app voor Windows alleen op apparaten met de Windows 10 Jubileumupdate (1607) en hoger. De optie voor het verzenden van feedback wordt niet meer ondersteund bij gebruik van de bedrijfsportal-app voor Windows met:  
- Windows 10, 1507 release  
- Windows 10, 1511 release  
- Windows Phone 8.1 

Als uw apparaat Windows 10 RS1 of hoger gebruikt, moet u de nieuwste versie van de Windows-bedrijfsportal downloaden in de Store. Als u een niet-ondersteunde versie uitvoert, kunt u feedback blijven verzenden via de volgende kanalen: 
- De Feedback Hub-app in Windows 10
- E-mail WinCPfeedback@microsoft.com  

#### <a name="new-windows-defender-application-guard-settings----1631890---"></a>Nieuwe instellingen voor Windows Defender Application Guard <!-- 1631890 -->

- **Grafische versnelling inschakelen**: beheerders kunnen voortaan een virtuele grafische processor inschakelen voor Windows Defender Application Guard. Met deze instelling kan de CPU taken voor de grafische weergave overdragen aan de vGPU. Dit kan de prestaties verbeteren wanneer u met websites werkt die veeleisende grafische weergaven bevatten of een video in de container bekijkt.

- **SaveFilestoHost**: beheerders kunnen ervoor zorgen dat bestanden worden doorgegeven van Microsoft Edge, die in de container wordt uitgevoerd, naar het hostbestandsysteem. Wanneer u deze optie inschakelt, kunnen gebruikers bestanden uit Microsoft Edge in de container downloaden naar het hostbestandsysteem.

#### <a name="mam-protection-policies-targeted-based-on-management-state----1665993---"></a>Gericht MAM-beleid op basis van de beheerstatus <!-- 1665993 -->
U kunt zich richten op MAM-beleid op basis van de beheerstatus van het apparaat:
- **Android-apparaten**: u kunt zich richten op niet-beheerde apparaten, door Intune beheerde apparaten en door Intune beheerde Android Enterprise-profielen (voorheen Android for Work).
- **iOS-apparaten**: u kunt zich richten op niet-beheerde apparaten (alleen MAM) of door Intune beheerde apparaten.

    > [!NOTE]
    > - iOS-ondersteuning voor deze functionaliteit wordt in april 2018 uitgerold.

Zie [Beleidsregels voor app-beveiliging toepassen op basis van de apparaatbeheerstatus](app-protection-policies.md) voor meer informatie.

#### <a name="improvements-to-the-language-in-the-company-portal-app-for-windows----1683758---"></a>Verbeteringen in de taal in de bedrijfsportal-app voor Windows <!-- 1683758 -->
In de bedrijfsportal voor Windows 10 is de taal gebruiksvriendelijker en meer specifiek voor uw bedrijf gemaakt. Zie [Wat is er nieuw in de gebruikersinterface van apps?](whats-new-app-ui.md) voor een aantal voorbeeldafbeeldingen van wat we hebben gedaan.

#### <a name="new-additions-to-our-docs-about-user-privacy----1440709---"></a>Toevoegingen aan onze documentatie over de privacy van gebruikers <!-- 1440709 -->
Als onderdeel van onze inspanning om eindgebruikers meer controle over hun gegevens en privacy te geven, is de documentatie bijgewerkt waarin wordt uitgelegd hoe u gegevens die lokaal zijn opgeslagen door de bedrijfsportal-apps kunt weergeven en verwijderen. U vindt deze updates op:

- **Android**: [Uw Android-apparaat uit Intune verwijderen](/intune-user-help/unenroll-your-device-from-intune-android.md)
- **Android, wanneer de gebruiker de gebruiksvoorwaarden heeft afgewezen**: [Beheer van uw apparaten verwijderen als u de gebruiksvoorwaarden hebt afgewezen](/intune-user-help/unenroll-your-device-from-intune-if-you-declined-terms-of-use-android.md)
- **iOS**: [Uw iOS-apparaat uit Intune verwijderen](/intune-user-help/unenroll-your-device-from-intune-ios.md)
- **Windows**: [Uw Windows-apparaat uit Intune verwijderen](/intune-user-help/unenroll-your-device-from-intune-windows.md)

## <a name="february-2018"></a>februari 2018

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Intune-ondersteuning voor meerdere Apple DEP-/Apple School Manager-accounts <!-- 747685 -->

Intune ondersteunt nu de inschrijving van apparaten uit maximaal 100 verschillende [Apple Device Enrollment Program (DEP)](device-enrollment-program-enroll-ios.md)- of [Apple School Manager](apple-school-manager-set-up-ios.md)-accounts. Elk geüpload token kan afzonderlijk worden beheerd voor registratieprofielen en -apparaten. Er kan automatisch een ander registratieprofiel worden toegewezen per geüpload DEP-/School Manager-token. Als er meerdere School Manager-tokens zijn geüpload, kan er per keer slechts één worden gedeeld met Microsoft School Data Sync.

Na de migratie werken de bèta Graph API's en gepubliceerde scripts voor het beheren van Apple DEP of ASM over Graph niet meer. Nieuwe bèta Graph API's zijn in ontwikkeling en zullen na de migratie worden uitgebracht.

#### <a name="see-enrollment-restrictions-per-user----1634444-eeready-wnready---"></a>Inschrijvingsbeperkingen per gebruiker bekijken <!-- 1634444 eeready wnready -->
Op de blade **Probleemoplossing** kunt u nu de [inschrijvingsbeperkingen](enrollment-restrictions-set.md) bekijken die gelden voor elke gebruiker. Selecteer hiervoor **Inschrijvingsbeperkingen** in de lijst **Toewijzingen**.

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

### <a name="device-management"></a>Apparaatbeheer

#### <a name="windows-defender-health-status-and-threat-status-reports---854704---"></a>Rapporten over de integriteitsstatus en bedreigingsstatus van Windows Defender<!--854704 -->

Inzicht in de integriteit en status van Windows Defender is essentieel voor het beheren van Windows-pc's.  Dankzij deze update worden door Intune nieuwe rapporten en acties toegevoegd aan de status en integriteit van de Windows Defender-agent. Wanneer u een rapport voor het verzamelen van de status gebruikt in de [workload voor apparaatcompatibiliteit](compliance-policy-monitor.md), worden apparaten weergegeven waarvoor een of meer van de volgende acties moeten worden uitgevoerd:
- het bijwerken van de handtekening
- Opnieuw opstarten
- handmatige interventie
- volledige scan
- interventie die is vereist voor andere agentstatussen

In een gedetailleerd rapport voor elke statuscategorie worden de afzonderlijke pc's vermeld waarvoor aandacht is vereist of die als **schoon** zijn gerapporteerd.

#### <a name="new-privacy-settings-for-device-restrictions---1308926---"></a>Nieuwe privacyinstellingen voor apparaatbeperkingen <!--1308926 -->
Er zijn [twee nieuwe privacyinstellingen](device-restrictions-windows-10.md#privacy) voor apparaten beschikbaar:
- **Gebruikersactiviteiten publiceren**: stel dit in op **Blokkeren** om gedeelde ervaringen en de detectie van recent gebruikte resources in de taakwisselaar te voorkomen.
- **Alleen lokale activiteiten**: stel dit in op **Blokkeren** om gedeelde ervaringen en de detectie van recent gebruikte resources in de taakwisselaar alleen op basis van de lokale activiteit te voorkomen.

#### <a name="new-settings-for-the-edge-browser---1469166---"></a>Nieuwe instellingen voor de Microsoft Edge-browser <!--1469166 -->
Er zijn [twee nieuwe instellingen](device-restrictions-windows-10.md#edge-browser) beschikbaar voor apparaten met de Microsoft Edge-browser: **Pad naar het bestand met favorieten** en **Wijzigingen in Favorieten**.

### <a name="app-management"></a>Appbeheer

#### <a name="protocol-exceptions-for-applications---1035509---"></a>Protocoluitzonderingen voor toepassingen <!--1035509 -->

U kunt nu uitzonderingen maken voor het gegevensoverdrachtbeleid van Intune MAM (Mobile Application Management) om specifieke onbeheerde toepassingen te openen. Dergelijke toepassingen moeten door de IT-afdeling als vertrouwde toepassingen worden beschouwd. Afgezien van de uitzonderingen die u maakt, wordt de gegevensoverdracht nog steeds beperkt tot de toepassingen die door Intune worden beheerd als uw beleid voor gegevensoverdracht is ingesteld op **Uitsluitend beheerde apps**. U kunt de beperkingen maken met behulp van protocollen (iOS) of pakketten (Android).

U kunt bijvoorbeeld het Webex-pakket toevoegen als een uitzondering op het MAM-gegevensoverdrachtbeleid. Op die manier kunnen Webex-koppelingen in een beheerd e-mailbericht van Outlook rechtstreeks in de Webex-toepassing worden geopend. De gegevensoverdracht wordt nog steeds beperkt in andere onbeheerde toepassingen. Zie [Uitzonderingen voor gegevensoverdrachtsbeleid voor apps](app-protection-policies-exception.md) voor meer informatie.

#### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Versleutelde gegevens van Windows Information Protection (WIP) in zoekresultaten van Windows <!-- 1469193 -->
Met een instelling in het WIP-beleid (Windows-gegevensbescherming) kunt u zelf regelen of met WIP versleutelde gegevens in de zoekresultaten van Windows worden opgenomen. Stel deze optie voor app-beveiligingsbeleid in door de optie **Windows Search-indexeerfunctie toestaan om versleutelde items te zoeken** te selecteren in de **geavanceerde instellingen** van het Windows-gegevensbeschermingsbeleid. Het beveiligingsbeleid van de app moet worden ingesteld op het *Windows 10*-platform en de **inschrijvingsstatus** van het app-beleid moet worden ingesteld op **Bij inschrijving**. Zie [De Windows Search-indexeerfunctie toestaan om versleutelde items te zoeken](windows-information-protection-policy-create.md#allow-windows-search-indexer-to-search-encrypted-items) voor meer informatie.

#### <a name="configuring-a-self-updating-mobile-msi-app----1740840---"></a>Een mobiele MSI-app configureren die automatisch wordt bijgewerkt <!-- 1740840 -->
U kunt een bekende mobiele MSI-app die automatisch wordt bijgewerkt configureren om de versiecontrole te negeren. Met deze functie kunt u voorkomen dat er een racevoorwaarde optreedt. Dit type racevoorwaarde kan bijvoorbeeld optreden wanneer de app die automatisch wordt bijgewerkt door de app-ontwikkelaar ook wordt bijgewerkt door Intune. Er kan door beide partijen worden geprobeerd om een versie van de app op een Windows-client af te dwingen, waardoor een conflict kan ontstaan. Voor deze automatisch bijgewerkte MSI-apps kunt u de instelling **App-versie negeren** in de blade **App-informatie** configureren. Wanneer deze instelling op **Ja** staat, negeert Microsoft Intune de app-versie die is geïnstalleerd op de Windows-client.

#### <a name="related-sets-of-app-licenses-supported-in-intune----1864117---"></a>Gerelateerde groepen van app-licenties worden in Intune ondersteund <!-- 1864117 -->
Intune in Azure Portal biedt nu ondersteuning voor de vermelding van gerelateerde groepen van app-licenties als één app-item in de gebruikersinterface. Bovendien worden apps met offlinelicenties die zijn gesynchroniseerd vanuit Microsoft Store voor Bedrijven geconsolideerd in één app-vermelding. Eventuele implementatiegegevens uit de afzonderlijke pakketten worden naar die ene vermelding gemigreerd. Als u gerelateerde groepen van app-licenties in Azure Portal wilt bekijken, selecteert u **App-licenties** op de blade **Client-apps**.

### <a name="device-configuration"></a>Apparaatconfiguratie
#### <a name="windows-information-protection-wip-file-extensions-for-automatic-encryption----1463582---"></a>Bestandsextensies voor automatische versleuteling door Windows-gegevensbescherming (WIP) <!-- 1463582 -->
Met een instelling in het Windows-gegevensbeschermingsbeleid (WIP) kunt u nu opgeven welke bestandsextensies automatisch worden versleuteld bij het kopiëren vanaf een Server Message Block-share (SMB) binnen het bedrijf, zoals gedefinieerd in het WIP-beleid.

#### <a name="configure-resource-account-settings-for-surface-hubs"></a>Resourceaccountinstellingen voor Surface Hubs configureren

U kunt nu resourceaccountinstellingen voor Surface Hubs extern configureren.

Het resourceaccount wordt door een Surface Hub gebruikt voor verificatie bij Exchange/Skype, zodat kan worden deelgenomen aan een vergadering.
U kunt een uniek resourceaccount maken, zodat de Surface Hub in de vergadering kan worden weergegeven als de vergaderruimte.
Bijvoorbeeld een resourceaccount als **Vergaderruimte B41/6233**.

> [!NOTE]
> - Als u velden leeg laat, overschrijft u de eerder geconfigureerde kenmerken op het apparaat.
>
> - Resourceaccounteigenschappen kunnen in de Surface Hub dynamisch worden gewijzigd. Bijvoorbeeld als wisseling van het wachtwoord is ingeschakeld. Het is dus mogelijk dat de waarden in de Azure-console pas na enige tijd in overeenstemming zijn met de waarden op het apparaat.
>
>   Om te weten wat er op dat moment op de Surface Hub is geconfigureerd, kunnen de resourceaccountgegevens in de hardware-inventaris (die al een interval van zeven dagen heeft) of als alleen-lezen eigenschappen worden opgenomen. Voor een grotere nauwkeurigheid na de uitvoering van de externe actie kunt u de status van de parameters onmiddellijk na het uitvoeren van de actie ophalen om het account/de parameters op de Surface Hub bij te werken.

##### <a name="attack-surface-reduction"></a>Kwetsbaarheid voor aanvallen verminderen

|Naam van de instelling  |Instellingsopties  |Beschrijving  |
|---------|---------|---------|
|Uitvoering van met een wachtwoord beschermde uitvoerbare inhoud uit e-mails|Blokkeren, Controleren, Niet geconfigureerd|Voorkom dat uitvoerbare bestanden met wachtwoordbescherming uit e-mails worden uitgevoerd.|
|Geavanceerde ransomwarebeveiliging|Ingeschakeld, Controleren, Niet geconfigureerd|Gebruik agressieve ransomwarebeveiliging.|
|Referentiediefstal in het Windows-subsysteem voor de lokale beveiligingsautoriteit markeren|Ingeschakeld, Controleren, Niet geconfigureerd|Markeer referentiediefstal in het Windows-subsysteem voor de lokale beveiligingsautoriteit (lsass.exe).|
|Het maken van processen met PSExec- en WMI-opdrachten|Blokkeren, Controleren, Niet geconfigureerd|Blokkeer het maken van processen die afkomstig zijn van PSExec- en WMI-opdrachten.|
|Niet-vertrouwde en niet-ondertekende processen die worden uitgevoerd vanaf een USB|Blokkeren, Controleren, Niet geconfigureerd|Blokkeer niet-vertrouwde en niet-ondertekende processen die worden uitgevoerd vanaf een USB.|
|Uitvoerbare bestanden die niet voldoen aan een bepaalde gangbaarheid, ouderdom of aan criteria voor vertrouwde lijsten blokkeren|Blokkeren, Controleren, Niet geconfigureerd|Voorkomen dat uitvoerbare bestanden worden uitgevoerd tenzij deze voldoen aan een bepaalde gangbaarheid, ouderdom of criteria voor vertrouwde lijsten.|

##### <a name="controlled-folder-access"></a>Gecontroleerde mappentoegang

|              Naam van de instelling               |                                                              Instellingsopties                                                              | Beschrijving |
|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|-------------|
| Mapbeveiliging (al geïmplementeerd) | Niet geconfigureerd, Inschakelen, Alleen controleren (al geïmplementeerd)<br><br> <strong>Nieuw</strong><br>Schijfwijziging blokkeren, schijfwijziging controleren |             |

Beveilig bestanden en mappen tegen niet-geautoriseerde wijzigingen door niet-goedgekeurde apps.<br><br>**Inschakelen**: voorkom dat bestanden in beveiligde mappen door niet-vertrouwde apps worden gewijzigd of verwijderd en dat gegevens door deze apps naar schijfsectoren worden weggeschreven.<br><br>
**Alleen schijfwijziging blokkeren**:<br>Voorkom dat gegevens door niet-vertrouwde apps worden weggeschreven naar schijfsectoren. Bestanden in beveiligde mappen kunnen nog steeds door niet-vertrouwde apps worden gewijzigd of verwijderd.|

#### <a name="additions-to-system-security-settings-for-windows-10-and-later-compliance-policies---1704133--"></a>Toevoegingen aan systeembeveiligingsinstellingen voor nalevingsbeleid voor Windows 10 en hoger <!--1704133-->

Toevoegingen aan de nalevingsinstellingen voor Windows 10 zijn nu beschikbaar, waaronder het verplichte gebruik van een firewall en Windows Defender Antivirus.

### <a name="intune-apps"></a>Intune-apps

#### <a name="support-for-offline-apps-from-the-microsoft-store-for-business---1222672--"></a>Ondersteuning voor offlineapps uit Microsoft Store voor Bedrijven <!--1222672-->
Offlineapps die u hebt gekocht in Microsoft Store voor Bedrijven worden voortaan gesynchroniseerd met Azure Portal. Vervolgens kunt u deze apps implementeren in apparaat- of gebruikersgroepen. Offlineapps worden geïnstalleerd door Intune en niet door de Store.

#### <a name="prevent-end-users-from-manually-adding-or-removing-accounts-in-the-work-profile----1728700---"></a>Hiermee voorkomt u dat eindgebruikers handmatig accounts in het werkprofiel kunnen toevoegen of uit het werkprofiel kunnen verwijderen <!-- 1728700 -->

Wanneer u de Gmail-app implementeert in een Android for Work-profiel, kunt u voorkomen dat eindgebruikers accounts handmatig aan het werkprofiel toevoegen of uit het werkprofiel verwijderen door de instelling **Accounts toevoegen en verwijderen** te gebruiken in het Android for Work-apparaatbeperkingsprofiel.


## <a name="january-2018"></a>januari 2018

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

### <a name="intune-apps"></a>Intune-apps

#### <a name="new-functionality-for-the-resolve-action-for-android-devices---1583480--"></a>Nieuwe functionaliteit voor de actie 'Oplossen' voor Android-apparaten <!--1583480-->

De bedrijfsportal-app voor Android breidt de actie 'Oplossen' uit voor **Apparaatinstellingen bijwerken** om [problemen met de versleuteling van het apparaat](/intune-user-help/encrypt-your-device-android) op te lossen.

#### <a name="remote-lock-available-in-company-portal-app-for-windows-10---676506--"></a>Externe vergrendeling is beschikbaar in de bedrijfsportal-app voor Windows 10<!--676506-->
Eindgebruikers kunnen nu in de bedrijfsportal-app voor Windows 10 hun apparaten extern vergrendelen. Dit wordt niet weergegeven voor het lokale apparaat dat op dat moment wordt gebruikt.

#### <a name="easier-resolution-of-compliance-issues-for-the-company-portal-app-for-windows-10---676546--"></a>Eenvoudigere oplossing van problemen met naleving voor de bedrijfsportal-app voor Windows 10 <!--676546-->
Eindgebruikers met Windows-apparaten kunnen tikken op de reden van niet-naleving in de bedrijfsportal-app. Indien mogelijk worden ze hiermee rechtstreeks naar de juiste locatie geleid in de instellingen-app om het probleem te verhelpen.

## <a name="december-2017"></a>december 2017

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


### <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer

#### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1667026---"></a>De nieuwe entiteitverzameling Huidige gebruiker is beperkt tot gegevens van actieve gebruikers <!-- 1667026 -->

De entiteitverzameling **Gebruiker** bevat alle Azure Active Directory-gebruikers (Azure AD) met toegewezen licenties in uw onderneming. Een gebruiker kan bijvoorbeeld worden toegevoegd aan Intune en vervolgens ergens gedurende de afgelopen maand zijn verwijderd. Ook al is deze gebruiker niet aanwezig op het moment dat het rapport wordt gegenereerd, toch zijn de gebruiker en de status aanwezig in de gegevens. U kunt een rapport maken dat de duur van de historische aanwezigheid van de gebruiker in uw gegevens weergeeft.

Daarentegen bevat de nieuwe entiteitverzameling **Huidige gebruiker** alleen gebruikers die niet zijn verwijderd. De entiteitverzameling **Huidige gebruiker** bevat alleen gebruikers die momenteel actief zijn. Zie [Naslaginformatie voor huidige gebruikersentiteit](reports-ref-current-user.md) voor informatie over de entiteitverzameling **Huidige gebruiker**.


### <a name="updated-graph-apis----1736360---"></a>Bijgewerkte Graph API's <!-- 1736360 -->

We hebben in deze release enkele Graph API's voor Intune bijgewerkt die nog in de bètafase zijn. Bekijk de maandelijkse [Graph API changelog](https://developer.microsoft.com/graph/docs/concepts/changelog) voor meer informatie.

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="intune-supports-windows-information-protection-wip-denied-apps----1479103---"></a>Intune biedt ondersteuning voor door Windows Information Protection (WIP) geweigerde apps <!-- 1479103 -->
U kunt geweigerde apps opgeven in Intune. Als een app wordt geweigerd, heeft deze geen toegang tot zakelijke gegevens. Dit is dus eigenlijk het tegenovergestelde van de lijst met toegestane apps. Zie [Aanbevolen lijst voor weigeren voor Windows Information Protection](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp?f=255&MSPPError=-2147217396#recommended-deny-list-for-windows-information-protection) voor meer informatie.


## <a name="november-2017"></a>November 2017

### <a name="troubleshoot-enrollment-issues-----746324---"></a>Inschrijvingsproblemen oplossen <!-- 746324 -->

De werkruimte **Problemen oplossen** toont problemen met gebruikersinschrijving. Details over het probleem en voorgestelde herstelstappen kunnen beheerders en helpdeskmedewerkers helpen problemen op te lossen. Bepaalde inschrijvingsproblemen worden niet vastgelegd en voor sommige fouten zijn er misschien geen herstelvoorstellen.

### <a name="group-assigned-enrollment-restrictions----747598---"></a>Beperkingen aan groepen toegewezen inschrijving <!-- 747598 -->

Als Intune-beheerder kunt u de [aangepaste inschrijvingsbeperkingen Apparaattype en Apparaatlimiet maken voor gebruikersgroepen](enrollment-restrictions-set.md).

Met de Intune Azure Portal kunt u maximaal 25 exemplaren van elk beperkingstype maken die vervolgens kunnen worden toegewezen aan gebruikersgroepen. Aan groepen toegewezen beperkingen overschrijven de standaardbeperkingen.

Alle exemplaren van een beperkingstype worden bijgehouden in een strikt geordende lijst. Deze volgorde bepaalt een prioriteitswaarde voor conflictoplossing. Een gebruiker die getroffen is door meer dan één beperkingsexemplaar wordt alleen beperkt door het exemplaar met de hoogste prioriteitswaarde. U kunt de prioriteit van een bepaald exemplaar wijzigen door dit naar een andere positie in de lijst te slepen.

Deze functionaliteit wordt vrijgegeven met de migratie van Android for Work-instellingen van het menu Android for Work-inschrijving naar het menu Inschrijvingsbeperkingen. Aangezien deze migratie enkele dagen kan duren, kan uw account worden bijgewerkt ten aanzien van andere onderdelen van de release van november voordat u ziet dat groepstoewijzing wordt ingeschakeld voor Inschrijvingsbeperkingen.

### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors----1528104---"></a>Ondersteuning voor meerdere connectors voor de Network Device Enrollment-service (NDES)<!-- 1528104 -->

Met de NDES kunnen mobiele apparaten die zonder domeinreferenties worden uitgevoerd certificaten verkrijgen op basis van het Simple Certificate Enrollment Protocol (SCEP).
Dankzij deze update worden meerdere NDES-connectors ondersteund.

### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731-eeready--"></a>Android for Work-apparaten onafhankelijk van de Android-apparaten beheren<!-- 1490731 EEready-->

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

### <a name="google-play-protect-support-on-android----908720---"></a>Ondersteuning van Google Play Protect op Android <!-- 908720 -->

Google introduceert tegelijkertijd met Android Oreo een reeks beveiligingsfuncties met de naam Google Play Protect waarmee gebruikers en organisaties beveiligde apps en beveiligde Android-installatiekopieën kunnen uitvoeren. Intune ondersteunt de functies van Google Play Protect, inclusief SafetyNet voor externe verklaringen. Beheerders kunnen eisen voor een nalevingsbeleid instellen die vereisen dat Google Play Protect wordt geconfigureerd en in orde is.
De instelling **SafetyNet-apparaatverklaring** vereist dat het apparaat verbinding maakt met een service van Google om te controleren of het apparaat in orde is en er niet mee is geknoeid. Beheerders kunnen tevens een configuratieprofielinstelling voor Android for Work instellen om te vereisen dat geïnstalleerde apps worden geverifieerd met behulp van Google Play-services. Als een apparaat niet aan de eisen van Google Play Protect voldoet, kan voorwaardelijke toegang de toegang van gebruikers tot bedrijfsbronnen blokkeren.

- Meer informatie over [het maken van een nalevingsbeleid voor apparaten om Google Play Protect in te schakelen](https://docs.microsoft.com/intune/compliance-policy-create-google-play-protect).

### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Tekstprotocol toegestaan vanuit beheerde Apps<!-- 1414050  -->

Met apps die worden beheerd door de Intune App SDK kunnen SMS-berichten worden verzonden.


### <a name="app-install-report-updated-to-include-install-pending-status----1249446---"></a>Het statusrapport van de app-installatie wordt bijgewerkt met de status Installatie in behandeling <!-- 1249446 -->  

Het **Statusrapport van de app-installatie**, dat toegankelijk is voor elke app via de lijst **App** in de workload **Client-apps**, bevat nu **Installatie in behandeling** voor gebruikers en apparaten.

### <a name="ios-11-app-inventory-api-for-mobile-threat-detection----1391759---"></a>API iOS 11-app-inventaris voor mobiele detectie van dreigingen (MTD) <!-- 1391759 -->

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

### <a name="migrate-hybrid-mdm-users-and-devices-to-intune-standalone----1463747-wnready---"></a>Hybride MDM-gebruikers en -apparaten migreren naar Intune (zelfstandig)<!-- 1463747 wnready -->
Er zijn nu nieuwe processen en hulpprogramma's beschikbaar om in Azure Portal gebruikers en hun apparaten van hybride MDM naar Intune te verplaatsen, zodat u het volgende kunt doen:
- In Azure Portal beleidsregels en profielen van de Configuration Manager-console naar Intune kopiëren
- In Azure Portal een subset gebruikers naar Intune verplaatsen, terwijl de rest in hybride MDM blijft
- In Azure Portal apparaten naar Intune migreren zonder dat u ze opnieuw hoeft te registreren

Zie [Hybride MDM-gebruikers en -apparaten migreren naar Intune (zelfstandig)](https://docs.microsoft.com/sccm/mdm/deploy-use/migrate-hybridmdm-to-intunesa) voor meer informatie.

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Hoge beschikbaarheid van on-premises Exchange Connector  <!-- 676614 -->
Nadat de Exchange Connector verbinding met Exchange heeft gemaakt met behulp van de opgegeven CAS, kan de connector nu andere CAS-instanties detecteren. Als de primaire CAS niet beschikbaar is, zoekt de connector naar een andere CAS (indien beschikbaar) totdat de primaire CAS beschikbaar komt. Zie [Hoge beschikbaarheid van on-premises Exchange Connector](exchange-connector-install.md#on-premises-exchange-connector-high-availability-support) voor meer informatie.

### <a name="remotely-restart-ios-device-supervised-only----1424595---"></a>iOS-apparaat op afstand opnieuw opstarten (alleen onder supervisie)<!-- 1424595 -->

U kunt een iOS 10.3 +-apparaat onder supervisie activeren om via een apparaatactie opnieuw op te starten. Zie voor meer informatie over het gebruik van de actie voor het opnieuw opstarten van het apparaat [Apparaten op afstand opnieuw opstarten met Intune](device-restart.md).

> [!Note]
> Deze opdracht vereist toegangsrechten tot apparaten onder supervisie en **Apparaatvergrendeling**. Het apparaat wordt onmiddellijk opnieuw opgestart. Met een toegangscode vergrendelde iOS-apparaten wordt niet opnieuw verbonden met een Wi-Fi-netwerk na opnieuw te zijn opgestart; na opnieuw te zijn opgestart kunnen deze mogelijk niet communiceren met de server.

### <a name="single-sign-on-support-for-ios----1333645---"></a>Ondersteuning voor Eenmalige aanmelding voor iOS<!-- 1333645 -->  

U kunt Eenmalige aanmelding voor iOS-gebruikers gebruiken. De iOS-apps die zijn gecodeerd om naar de gebruikersreferenties te zoeken in de Eenmalige aanmelding-payload zijn functioneel voor de update van de payloadconfiguratie. U kunt ook de UPN en de Intune-apparaat-id gebruiken om de Principal-naam en de Realm te configureren. Zie [Intune configureren voor eenmalige aanmelding vanaf iOS-apparaten](sso-ios.md) voor meer informatie.

### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Mijn iPhone vinden toevoegen voor privéapparaten<!--1427287-->
U kunt nu bekijken of bij iOS-apparaten Activeringsslot is ingeschakeld. Deze functie was eerder te vinden in de klassieke portal in Intune.

### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Beheerde macOS-apparaten op afstand vergrendelen met Intune<!-- 1437691 -->

U kunt een verloren Mac OS-apparaat vergrendelen en een 6-cijferige pincode voor wachtwoordherstel instellen. Als het apparaat is vergrendeld, toont de blade **Apparaatoverzicht** de pincode totdat een andere apparaatactie wordt verzonden.

Zie voor meer informatie [Beheerde apparaten op afstand vergrendelen met Intune](device-remote-lock.md).

### <a name="new-scep-profile-details-supported----1559808---"></a>Nieuwe SCEP-profielgegevens ondersteund<!-- 1559808 -->

Beheerders kunnen aanvullende instellingen configureren bij het maken van een SCEP-profiel op Windows-, iOS-, Mac OS- en Android-platformen.  Beheerders kunnen het IMEI-nummer, het serienummer of de algemene naam met inbegrip van e-mail in de indeling van de onderwerpnaam instellen.

<!-- #### Update to what device details your company may see -1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources. -->

### <a name="retain-data-during-a-factory-reset----1588489---"></a>Gegevens behouden tijdens fabrieksinstellingen terugzetten <!--1588489 -->
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


### <a name="window-10-update-ring-assignments-are-displayed----1621837---"></a>Er worden toewijzingen voor de Windows 10-updatering weergegeven <!-- 1621837 -->
Wanneer u bezig bent met de **probleemoplossing** voor de door u weergegeven gebruiker, kunt u eventuele toewijzingen voor de Windows 10-updatering zien.  

### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings-----1455974----"></a>Frequentie-instellingen van rapporten van Windows Defender Advanced Threat Protection <!-- 1455974  -->
Met de service Windows Defender Advanced Threat Protection (WDATP) kunnen beheerders de rapportagefrequentie voor beheerde apparaten beheren. Met de nieuwe optie **Frequentie van telemetrierapporten versnellen** verzamelt vaker WDATP gegevens en beoordeelt vaker risico's. De standaardwaarde voor rapportage zorgt voor optimale snelheid en prestaties. Het verhogen van de rapportagefrequentie kan waardevol zijn voor apparaten met een hoog risico. Deze instelling kunt u vinden in het **Windows Defender ATP**-profiel in **Apparaatconfiguraties**.

### <a name="audit-updates----1412961---"></a>Updates controleren<!-- 1412961 -->  
Controles van Intune biedt een record van de wijzigingsbewerkingen ten aanzien van Intune.  Alle taakbewerkingen voor maken, bijwerken, verwijderen en externe taakbewerkingen worden vastgelegd en een jaar bewaard.  De Azure Portal voorziet in een weergave van de controlegegevens van laatste 30 dagen in elke workload, welke gefilterd kan worden.  Met de bijbehorende Graph API kunt u de controlegegevens ophalen die het afgelopen jaar zijn bewaard.

Controles zijn te vinden onder de groep **CONTROLE**. Er is een menu-item **Controlelogboeken** voor elke workload.

### <a name="company-portal-app-for-macos-is-available---1541700--"></a>De bedrijfsportal-app voor macOS is beschikbaar <!--1541700-->
De Intune-bedrijfsportal op macOS is bijgewerkt en geoptimaliseerd, zodat alle informatie en nalevingsmeldingen die uw gebruikers nodig hebben voor alle apparaten die ze hebben ingeschreven, overzichtelijk wordt weergegeven. En als de Intune-bedrijfsportal eenmaal is geïmplementeerd op een apparaat, zorgt Microsoft AutoUpdate voor macOS voor de updates. U kunt de nieuwe Intune-bedrijfsportal voor macOS downloaden door u aan te melden bij de website van de Intune-bedrijfsportal vanaf een macOS-apparaat.

### <a name="microsoft-planner-is-now-part-of-the-mobile-app-management-mam-list-of-approved-apps-----1248473---"></a>Microsoft Planner maakt nu deel uit van de MAM-lijst (beheer van mobiele apps) met goedgekeurde apps <!-- 1248473 -->
De app Microsoft Planner voor iOS en Android maakt nu deel uit van de goedgekeurde apps voor Mobile App Management (MAM). De app kan via de blade Intune-app-beveiliging in Azure Portal worden geconfigureerd voor alle tenants.
- Meer informatie over de [MAM-lijst met goedgekeurde apps](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

### <a name="per-app-vpn-requirement-update-frequency-on-ios-devices------1547061---"></a>Vereiste updatefrequentie voor VPN per app op iOS-apparaten <!-- 1547061 -->  
Beheerders kunnen nu de vereisten voor VPN per app verwijderen voor apps op iOS-apparaten. Dit wordt toegepast op de betreffende apparaten na de eerstvolgende check-in bij Intune, gewoonlijk binnen 15 minuten.  

### <a name="support-for-system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Ondersteuning van management pack van System Center Operations Manager voor Exchange Connector <!-- 885457 -->
Het management pack van System Center Operations Manager (SCOM) voor Exchange Connector is nu beschikbaar om de logboeken van Exchange Connector te parseren. Hiermee kunt u de service op verschillende manieren controleren wanneer u problemen moet oplossen.

### <a name="co-management-for-windows-10-devices-----1243445---"></a>Co-management voor Windows 10-apparaten <!-- 1243445 -->
Co-management is een oplossing die een brug slaat tussen traditioneel en modern beheer en het biedt een gefaseerde benadering om de overstap te maken. Co-management is in feite een oplossing waarbij Windows 10-apparaten gelijktijdig worden beheerd door Configuration Manager en Microsoft Intune en zijn gekoppeld aan Active Directory (AD) en Azure Active Directory (Azure AD).  Deze configuratie geeft u een manier om mettertijd te moderniseren, in een tempo dat geschikt is voor uw organisatie als u niet allemaal tegelijk kunt overstappen.  

### <a name="restrict-windows-enrollment-by-os-version----245498---"></a>Windows-inschrijving beperken door de versie van het besturingssysteem <!-- 245498 -->
Als Intune-beheerder kunt u een minimale en maximale versie opgeven van Windows 10 voor de inschrijving van apparaten. U kunt deze beperkingen instellen op de blade **Platformconfiguraties**.

Intune blijft ondersteuning bieden voor registratie Windows 8.1-pc's en -telefoons. U kunt echter alleen minimale en maximale versies instellen voor Windows 10-versies. Als u de inschrijving van 8.1-apparaten wilt toestaan, laat u de minimale versie leeg.

### <a name="alerts-for-windows-autopilot-unassigned-devices-----1631236---"></a>Waarschuwingen voor niet-toegewezen Windows AutoPilot-apparaten <!-- 1631236 -->
Er is een nieuwe waarschuwing voor niet-toegewezen Windows AutoPilot-apparaten op de pagina **Microsoft Intune** > **Apparaatinschrijving** > **Overzicht**. Deze waarschuwing geeft aan voor hoeveel apparaten van het AutoPilot-programma geen AutoPilot-implementatieprofielen zijn toegewezen. Aan de hand van de informatie in de waarschuwing kunt u profielen maken en deze toewijzen aan de niet-toegewezen apparaten. Als u op de waarschuwing klikt, verschijnt een volledige lijst met Windows AutoPilot-apparaten en gedetailleerde informatie. Zie [Windows-apparaten inschrijven met het Windows AutoPilot Deployment-programma](https://docs.microsoft.com/intune/enrollment-autopilot) voor meer informatie.


### <a name="refresh-button-for-devices-list-------1333581---"></a>Knop voor het vernieuwen van de lijst met apparaten    <!-- 1333581 -->
Omdat de lijst met apparaten niet automatisch wordt vernieuwd, kunt u de nieuwe knop gebruiken om de apparaten bij te werken die worden weergegeven in de lijst.

### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Ondersteuning voor Symantec Cloud Certification Authority (CA)  <!-- 1333638 -->    
Intune ondersteunt nu Symantec Cloud CA, die de Intune Certificate Connector in staat stelt PKCS-certificaten van Symantec Cloud CA vrij te geven voor beheerde Intune-apparaten. Als u de Intune Certificate Connector al gebruikt met Microsoft Certification Authority (CA), kunt u de bestaande configuratie van de Intune Certificate Connector gebruiken om de ondersteuning voor Symantec CA toe te voegen.

### <a name="new-items-added-to-device-inventory-----1404455---"></a>Nieuwe items toegevoegd aan de apparaatinventarisatie   <!--1404455 -->
De volgende nieuwe items zijn nu beschikbaar voor de [inventaris van ingeschreven apparaten](device-inventory.md):

- Mac-adres van Wi-Fi
- Totale opslagruimte
- Totale vrije ruimte
- MEID
- Provider van abonnee

### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Toegang instellen voor apps via minimale Android-beveiligingspatch op het apparaat<!-- 1278463 -->   
Een beheerder kan de minimale Android-beveiligingspatch definiëren die op het apparaat moet zijn geïnstalleerd om toegang te kunnen krijgen tot een beheerde toepassing onder een beheerd account.

> [!Note]  
> Deze functie beperkt alleen beveiligingspatches die door Google zijn vrijgegeven op Android 6.0+ apparaten.

### <a name="app-conditional-launch-support----1193313---"></a>Ondersteuning voor app-voorwaardelijk starten <!-- 1193313 -->
IT-beheerders kunnen nu via de Azure-beheerportal een vereiste instellen om een wachtwoordcode in plaats van een numerieke pincode af te dwingen via Mobile App Management (MAM) wanneer de toepassing start. Als dit is geconfigureerd, moet de gebruiker een wachtwoordcode instellen en gebruiken wanneer daarom wordt gevraagd, alvorens toegang te krijgen tot toepassingen met MAM-functionaliteit. Een wachtwoordcode wordt gedefinieerd als een numerieke pincode met ten minste één speciaal teken of een hoofdletter/kleine letter. Bij deze release van Intune wordt deze functie **alleen op iOS** ingeschakeld. Intune ondersteunt wachtwoordcodes op dezelfde manier als numerieke pincodes: er is een minimumlengte, en tekens en tekenreeksen mogen worden herhaald. Deze functie vereist dat toepassingen (WXP, Outlook, Managed Browser, Yammer) de Intune App SDK integreren met de code voor deze functie om de wachtwoordcode-instellingen af te dwingen in de doeltoepassingen.

### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>App-versienummer voor line-of-business in rapport Installatiestatus van het apparaat <!-- 1233999 -->
Bij deze release toont het rapport Installatiestatus van het apparaat het app-versienummer voor de line-of-business-apps voor iOS en Android. U kunt deze informatie gebruiken om problemen met uw apps op te lossen of om apparaten te vinden waarop verouderde app-versies worden uitgevoerd.

### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>Beheerders kunnen de firewall-instellingen op een apparaat nu configureren met behulp van een apparaatconfiguratieprofiel <!-- 951708 -->   
Beheerders kunnen de firewall inschakelen voor apparaten, en ook verschillende protocollen voor domein-, privé- en openbare netwerken configureren.  Deze firewall-instellingen staan in het profiel 'Endpoint Protection'.

### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>Windows Defender Application Guard helpt apparaten te beschermen tegen niet-vertrouwde websites, zoals gedefinieerd door uw organisatie <!-- 958257 -->   
Beheerders kunnen sites als 'vertrouwd' of 'zakelijk' definiëren met behulp van een Windows Information Protection-werkstroom of het nieuwe profiel 'Netwerkgrens' onder apparaatconfiguraties. Sites die niet in een vertrouwde netwerkgrens van een 64-bits Windows 10-apparaat staan, worden in een browser op een virtuele Hyper-V-computer geopend als ze met Microsoft Edge worden bekeken.

Application Guard staat in de apparaatconfiguratieprofielen, in het profiel 'Endpoint Protection'. Beheerders kunnen daar interactie configureren tussen de gevirtualiseerde browser en de hostcomputer, niet-vertrouwde sites en vertrouwde sites, en gegevens opslaan die in de gevirtualiseerde browser worden gegenereerd. Als u Application Guard op een apparaat wilt gebruiken, moet er eerst een netwerkgrens worden geconfigureerd. Het is belangrijk slechts één netwerkgrens te definiëren voor een apparaat.  

### <a name="windows-defender-application-control-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>Windows Defender Application Control op Windows 10 Enterprise biedt een modus om alleen geautoriseerde apps te vertrouwen <!-- 1031096 -->    
Aangezien er elke dag duizenden nieuwe schadelijke bestanden worden gemaakt, biedt malwaredetectie op basis van handtekeningen misschien niet meer voldoende bescherming tegen nieuwe aanvallen. Met Windows Defender Application Control op Windows 10 Enterprise kunt u de apparaatconfiguratie wijzigen van een modus waarin apps worden vertrouwd tenzij ze door een antivirus- of andere beveiligingsoplossing worden geblokkeerd, naar een modus waarin het besturingssysteem alleen apps vertrouwt die door uw onderneming zijn geautoriseerd. In Windows Defender Application Control definieert u welke apps u vertrouwt.

Met Intune kunt u het toepassingsbeheerbeleid configureren in de modus 'Alleen controle' of in de modus 'Afdwingen'. Apps worden niet geblokkeerd wanneer ze in de modus 'Alleen controle' worden uitgevoerd. De modus 'Alleen controle' registreert alle gebeurtenissen in lokale clientlogboeken. U kunt ook configureren of alleen Windows-onderdelen en Microsoft Store-apps mogen worden uitgevoerd of dat aanvullende apps met een goede reputatie, zoals die is gedefinieerd door de Intelligent Security Graph, ook mogen worden uitgevoerd.

### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10----1063615---"></a>Window Defender Exploit Guard is een nieuwe verzameling inbraakpreventiefuncties voor Windows 10 <!-- 1063615 -->   
Window Defender Exploit Guard omvat aangepaste regels om de exploiteerbaarheid van toepassingen te reduceren, voorkomt macro- en scriptbedreigingen, blokkeert automatisch netwerkverbindingen naar IP-adressen met een slechte reputatie, en kan gegevens uit ransomware en onbekende bedreigingen beveiligen. Windows Defender Exploit Guard bestaat uit de volgende onderdelen:

- **Attack Surface Reduction (ASR)** biedt regels waarmee u macro-, script- en e-mailbedreigingen kunt voorkomen.
- **Gecontroleerde maptoegang** blokkeert automatisch de toegang tot inhoud in beveiligde mappen.
- **Netwerkfilter** blokkeert uitgaande verbindingen van een app naar een IP/domein met een slechte reputatie
- **Exploit-beveiliging** biedt geheugen-, controlestroom- en beleidsbeperkingen die kunnen worden gebruikt om een toepassing te beschermen tegen aanvallen.

### <a name="manage-powershell-scripts-in-intune-for-windows-10-devices----790537---"></a>PowerShell-scripts in Intune beheren voor Windows 10-apparaten <!-- 790537 -->

Met de Intune-beheeruitbreiding kunt u PowerShell-scripts uploaden in Intune om deze uit te voeren op Windows 10-apparaten. De uitbreiding is een aanvulling op de Windows 10 MDM-functionaliteit en maakt het eenvoudiger voor u om uw beheer te moderniseren. Zie [PowerShell-scripts in Intune beheren voor Windows 10-apparaten](intune-management-extension.md) voor meer informatie.

### <a name="new-device-restriction-settings-for-windows-10---------1308850---"></a>Nieuwe apparaatbeperkingsinstellingen voor Windows 10      <!-- 1308850 -->
-    Berichten (alleen mobiel) - testen of MMS-berichten uitschakelen
-    Wachtwoord - instellingen om FIPS en het gebruik van secundaire Windows Hello-apparaten in te schakelen voor verificatie 
-    Weergave - instellingen om GDI-schaalbaarheid in of uit te schakelen voor verouderde apps

### <a name="windows-10-kiosk-mode-device-restrictions----1308872---"></a>Apparaatbeperkingen Windows 10-kioskmodus <!-- 1308872 -->   
U kunt gebruikers van Windows 10-apparaten beperken tot de kioskmodus, zodat ze worden beperkt tot een verzameling vooraf gedefinieerde apps.  Om dit te doen, maakt u een Windows 10-apparaatbeperkingsprofiel en configureert u de kioskinstellingen.

De kioskmodus ondersteunt twee modi: **één app** (waarbij een gebruiker slechts één app mag uitvoeren) en **meerdere apps** (geeft toegang tot een verzameling apps).  U definieert het gebruikersaccount en de apparaatnaam, waarmee de ondersteunde apps worden bepaald.  Wanneer de gebruiker is aangemeld, is hij/zij beperkt tot de gedefinieerde apps.  Zie [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) voor meer informatie. 

De kioskmodus vereist het volgende:

- Intune moet de MDM-instantie zijn.
- De apps moeten al op het doelapparaat zijn geïnstalleerd.
- Het apparaat moet [goed ingericht](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions) zijn.

### <a name="new-device-configuration-profile-for-creating-network-boundaries----1311967---"></a>Nieuw apparaatconfiguratieprofiel voor het maken van netwerkgrenzen <!-- 1311967 -->   
Bij uw andere apparaatconfiguratieprofielen vindt u een nieuw apparaatconfiguratieprofiel genaamd **Netwerkgrens**. Gebruik dit profiel om onlinebronnen te definiëren die u als zakelijk en vertrouwd wilt beschouwen. U moet een netwerkgrens voor een apparaat definiëren *voordat* functies zoals Windows Defender Application Guard en Windows Information Protection op het apparaat kunnen worden gebruikt. Het is belangrijk slechts één netwerkgrens te definiëren voor elk apparaat.

U kunt bedrijfscloudresources, IP-adresbereiken en interne proxyservers definiëren die u als vertrouwd wilt beschouwen. Nadat u de netwerkgrens hebt gedefinieerd, kan deze worden gebruikt door andere functies zoals Windows Defender Application Guard en Windows Information Protection.

###  <a name="two-additional-settings-for-windows-defender-antivirus----1338409---"></a>Twee aanvullende instellingen voor Windows Defender Antivirus <!-- 1338409 -->  
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

### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Citrix-VPN toegevoegd voor Windows 10-apparaten <!-- 1512457 -->  
U kunt Citrix-VPN configureren voor Windows 10-apparaten van klanten. U kunt de Citrix-VPN kiezen in de lijst *Een verbindingstype selecteren* in de blade **Basis-VPN** wanneer u een VPN voor Windows 10 en hoger configureert.

> [!Note]
> Citrix-configuratie bestond voor iOS en Android.

### <a name="wi-fi-connections-support-pre-shared-keys-on-ios----1550823---"></a>Wi-Fi-verbindingen ondersteunen vooraf gedeelde sleutels voor iOS <!-- 1550823 -->
Klanten kunnen Wi-Fi-profielen configureren voor het gebruik van vooraf gedeelde sleutels (PSK) voor WPA/WPA2 persoonlijke verbindingen op iOS-apparaten. Deze profielen worden gepusht naar het apparaat van de gebruiker als het apparaat is ingeschreven bij Intune.

Wanneer het profiel naar het apparaat is gepusht, is de volgende stap afhankelijk van de profielconfiguratie.  Als automatische verbinding is ingesteld, wordt automatisch verbinding gemaakt zodra het netwerk nodig is.  Als handmatige verbinding is ingesteld, moet de gebruiker de verbinding handmatig activeren.  

### <a name="access-to-managed-app-logs-for-ios----1469920---"></a>Toegang tot de logboeken van de beheerde app voor iOS <!-- 1469920 -->
Eindgebruikers waarvoor de beheerde browser is geïnstalleerd kunnen de beheerstatus van alle gepubliceerde Microsoft-apps bekijken en logbestanden versturen om problemen met hun beheerde iOS-apps op te lossen.

Zie [Toegang tot de logboeken van de beheerde app voor iOS](app-configuration-managed-browser.md#how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios) voor meer informatie over het inschakelen van de probleemoplossingsmodus in de beheerde browser op een iOS-apparaat.

### <a name="improvements-to-device-setup-workflow-in-the-company-portal-for-ios-in-version-290----1417174---"></a>Verbeteringen in de werkstroom voor apparaatinstellingen in de bedrijfsportal voor iOS in versie 2.9.0 <!-- 1417174 -->

De werkstroom voor apparaatinstellingen in de bedrijfsportal-app voor iOS is verbeterd. De taal is gebruiksvriendelijker en waar mogelijk hebben we schermen gecombineerd. De taal is ook specifieker voor uw bedrijf gemaakt door overal in de installatietekst de naam van uw bedrijf te gebruiken. U kunt deze bijgewerkte werkstroom zien op de  [pagina met nieuwe functies in de app](whats-new-app-ui.md).


### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>De gebruikersentiteit bevat de meest recente gebruikersgegevens in het datawarehouse-gegevensmodel <!-- 1544273 -->
De eerste versie van het gegevensmodel Intune-datawarehouse bevat alleen recente, historische Intune-gegevens. Rapportopstellers kunnen de huidige status van een gebruiker niet vastleggen. In deze update wordt  **Gebruikersentiteit** ingevuld met de meest recente gebruikersgegevens.


## <a name="october-2017"></a>Oktober 2017

### <a name="ios-and-android-line-of-business-app-version-number-is-visible----1380712---"></a>Het versienummer van de line-of-business-app voor iOS en Android is zichtbaar <!-- 1380712 -->

In Apps in Intune wordt nu het versienummer voor iOS- en Android-line-of-business-apps weergegeven. Het nummer wordt in de Azure Portal in de app-lijst en in de blade App-overzicht getoond. Eindgebruikers kunnen het app-nummer in de bedrijfsportal-app en in de webportal zien.

__Volledig versienummer__ Het volledige versienummer duidt een specifieke release van de app aan. Het nummer wordt weergegeven als _Versie_(_Build_). Bijvoorbeeld 2.2(2.2.17560800)

Het volledige versienummer bevat twee onderdelen:

 - **Versie**  
   Het versienummer is het door mensen leesbare releasenummer van de app. Dit wordt door eindgebruikers gebruikt om de verschillende releases van de app aan te duiden.

 - **Buildnummer**  
    Het buildnummer is een intern nummer dat voor de detectie van apps en het beheer van apps via een programma kan worden gebruikt. Het buildnummer verwijst naar een iteratie van de app die refereert aan wijzigingen in de code.

Meer informatie over versienummers en het ontwikkelen van line-of-business-apps in [Aan de slag met Microsoft Intune App SDK](app-sdk-get-started.md#line-of-business-app-version-numbers).

### <a name="device-and-app-management-integration----677972---"></a>Integratie van apparaat- en appbeheer <!-- 677972 -->   
Nu Mobile Device Management (MDM) en Mobile Application Management (MAM) van Intune beide toegankelijk zijn vanuit de Azure-portal, is Intune begonnen met het integreren van de IT-beheerervaring omtrent app- en apparaatbeheer. Deze wijzigingen zijn bedoeld om uw apparaat- en appbeheer te vereenvoudigen.

Meer informatie over de aangekondigde MDM- en MAM-wijzigingen staat in de [blog van het Intune-ondersteuningsteam](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/).

### <a name="new-enrollment-alerts-for-apple-devices----1471790---"></a>Nieuwe inschrijvingswaarschuwingen voor Apple-apparaten<!-- 1471790 -->
De overzichtspagina voor de inschrijving toont nuttige waarschuwingen voor IT-beheerders met betrekking tot beheer van apparaten van Apple. Waarschuwingen worden weergegeven op de overzichtspagina wanneer het Apple MDM push-certificaat verloopt of al is verlopen, wanneer het token Device Enrollment Program verloopt of al is verlopen en wanneer er zich niet-toegewezen apparaten in het Device Enrollment Program bevinden.

### <a name="support-token-replacement-for-app-configuration-without-device-enrollment----1080364---"></a>Ondersteuning voor token-vervanging voor de configuratie van de app zonder apparaatinschrijving <!-- 1080364 -->

U kunt tokens gebruiken voor dynamische waarden in app-configuraties voor apps op apparaten die niet zijn ingeschreven. Zie voor meer informatie [App-configuratiebeleidsregels toevoegen voor beheerde apps zonder apparaatinschrijving](app-configuration-policies-managed-app.md).

### <a name="updates-to-the-company-portal-app-for-windows-10---1299474--"></a>Updates in de bedrijfsportal-app voor Windows 10 <!--1299474-->
De pagina Instellingen in de bedrijfsportal-app voor Windows 10 is bijgewerkt, zodat de instellingen en de beoogde gebruikersacties consistenter zijn voor alle instellingen. De pagina komt nu ook beter overeen met de indeling van andere Windows-apps. U vindt afbeeldingen voor/na op de [pagina met nieuwe functies in de app](whats-new-app-ui.md).

### <a name="inform-end-users-what-device-information-can-be-seen-for-windows-10-devices---1337920--"></a>Eindgebruikers informeren welke apparaatgegevens voor Windows 10-apparaten kunnen worden gezien <!--1337920-->
De optie **Eigendomstype** is toegevoegd aan het scherm Apparaatgegevens in de bedrijfsportal-app voor Windows 10. Hierdoor kunnen gebruikers meer over privacy te weten komen vanaf deze pagina in de documenten voor Intune-eindgebruikers. Deze informatie is ook te vinden op het scherm **Info**.

### <a name="feedback-prompts-for-the-company-portal-app-for-android---1165249--"></a>Vragen om feedback over de bedrijfsportal-app voor Android <!--1165249-->
De bedrijfsportal-app voor Android vraagt nu om feedback van eindgebruikers. Deze feedback wordt rechtstreeks naar Microsoft verzonden en biedt eindgebruikers de kans de app te beoordelen in de openbare Google Play Store. Feedback is niet vereist en kan eenvoudig worden gesloten, zodat gebruikers kunnen doorgaan met het gebruik van de app.

<!-- #### Update to what device details an organization can see 1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources.-->

### <a name="helping-your-users-help-themselves-with-the-company-portal-app-for-android----1573324-1573150-1558616-1564878---"></a>Uw gebruikers helpen om zichzelf te redden met de bedrijfsportal-app voor Android<!-- 1573324, 1573150, 1558616, 1564878 -->

De bedrijfsportal-app voor Android voegt aanwijzingen toe, zodat eindgebruikers meer inzicht krijgen en, waar mogelijk, nieuwe gebruikssituaties zelf kunnen oplossen.
- Eindgebruikers worden naar de [Azure Active Directory-portal](https://account.activedirectory.windowsazure.com/r/#/profile) geleid om een apparaat verwijderen als zij het maximum aantal apparaten hebben bereikt dat ze mogen toevoegen.
- Eindgebruikers krijgen een stapsgewijze instructie om hen te helpen [foutberichten bij de activering van Samsung Knox-apparaten op te lossen](https://go.microsoft.com/fwlink/?linkid=859718) of [de energiebesparende modus uit te schakelen](/intune-user-help/power-saving-mode-android). Als geen van deze oplossingen het probleem verhelpt, krijgt u een uitleg over het verzenden van [logboeken naar Microsoft](/intune-user-help/send-logs-to-microsoft-android).

### <a name="new-resolve-action-available-for-android-devices----1583480---"></a>Nieuwe actie 'Oplossen' beschikbaar voor Android-apparaten<!-- 1583480 -->

De bedrijfsportal-app voor Android introduceert een actie 'Oplossen' op de pagina _Apparaatinstellingen bijwerken_. Als de eindgebruiker deze optie selecteert, komt deze rechtstreeks bij de instelling terecht die de oorzaak ervan is dat hun apparaat niet compatibel is. De bedrijfsportal-app voor Android ondersteunt momenteel deze actie ten aanzien van de instellingen [Toegangscode](/intune-user-help/set-your-pin-or-password-android), [USB-foutopsporing](/intune-user-help/you-need-to-turn-off-usb-debugging-android), en [Onbekende bronnen](/intune-user-help/you-need-to-turn-off-unknown-sources-android).

### <a name="device-setup-progress-indicator-in-android-company-portal----1565657---"></a>Voortgangsindicator voor apparaatinstallatie in Android-bedrijfsportal <!-- 1565657 -->
In de bedrijfsportal-app voor Android wordt een voortgangsindicator voor de apparaatinstallatie weergegeven wanneer een gebruiker zijn of haar apparaat inschrijft. De aanduiding toont nieuwe statussen, te beginnen met 'Uw apparaat instellen...', vervolgens 'Het apparaat registreren...', daarna 'Registreren van het apparaat voltooien...' en tot slot 'Instellen van het apparaat voltooien...'.

### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios---1029830--"></a>Ondersteuning voor op certificaten gebaseerde verificatie op de bedrijfsportal voor iOS <!--1029830-->
We hebben ondersteuning voor op certificaten gebaseerde verificatie toegevoegd in de bedrijfsportal-app voor iOS. Gebruikers met deze verificatie voeren hun gebruikersnaam in en tikken vervolgens op de koppeling 'Aanmelden met een certificaat'. Dit wordt al ondersteund in de bedrijfsportal-app voor Android en Windows. Meer informatie staat op de pagina [Aanmelden bij de bedrijfsportal-app](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal).

### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Apps die met of zonder inschrijving beschikbaar zijn, kunnen nu worden geïnstalleerd zonder dat er om inschrijving wordt gevraagd. <!-- 1334712 -->

Bedrijfs-apps die met of zonder inschrijving beschikbaar zijn gemaakt in de bedrijfsportal-app voor Android kunnen nu worden geïnstalleerd zonder dat er om inschrijving wordt gevraagd.

### <a name="windows-autopilot-deployment-program-support-in-microsoft-intune-----747617----"></a>Ondersteuning voor het Windows AutoPilot Deployment-programma in Microsoft Intune <!-- 747617  -->
U kunt nu Microsoft Intune gebruiken met het Windows AutoPilot Deployment-programma om uw gebruikers de mogelijkheid te geven hun bedrijfsapparaten in te richten zonder de tussenkomst van de IT-afdeling. U kunt de Out-of-the-box-ervaring (OOBE) aanpassen en gebruikers begeleiden bij het toevoegen van hun apparaat aan Azure AD en inschrijven bij Intune. Samen nemen Microsoft Intune en Windows AutoPilot de noodzaak weg voor het implementeren, onderhouden en beheren van installatiekopieën van besturingssystemen. Zie [Windows-apparaten inschrijven met het Windows AutoPilot Deployment-programma](https://docs.microsoft.com/intune/enrollment-autopilot) voor meer informatie.

### <a name="quick-start-for-device-enrollment-----1425655---"></a>Snel starten met apparaatinschrijving <!-- 1425655 --> 
Snel starten is nu beschikbaar in **Apparaatinschrijving** en bevat een tabel met naslagonderwerpen voor het beheren van platformen en configureren van het inschrijvingsproces. Dankzij een korte beschrijving van elk item en koppelingen naar documentatie met stapsgewijze instructies kunt u sneller aan de slag.

### <a name="device-categorization----1427491---"></a>Categorisatie van apparaten <!-- 1427491 -->
In de grafiek met platformen van ingeschreven apparaten op de blade **Apparaten > Overzicht** zijn apparaten geordend op platform, zoals Android, iOS, macOS, Windows en Windows Mobile.  Apparaten met een ander besturingssysteem zijn gegroepeerd in de categorie ‘Overig’.  Dit omvat apparaten van Blackberry, Nokia en andere fabrikanten.  

Als u wilt weten wat dit voor gevolgen heeft voor de apparaten in uw tenant, kiest u **Beheren > Alle apparaten** en gebruikt u vervolgens **Filter** om de inhoud van het veld **Besturingssysteem** te beperken.

### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium - nieuwe Mobile Threat Defense-partner   <!-- 954681 -->  
U kunt de toegang van mobiele apparaten tot bedrijfsresources beheren door middel van voorwaardelijke toegang op basis van een risicoanalyse die wordt uitgevoerd door Zimperium, een oplossing voor de beveiliging tegen bedreigingen op mobiele apparaten die met Microsoft Intune is geïntegreerd.

#### <a name="how-integration-with-intune-works"></a>Hoe werkt de integratie met Intune
Risico's worden beoordeeld op basis van telemetrische gegevens die zijn verzameld op apparaten met door Zimperium. U kunt het EMS-beleid voor voorwaardelijke toegang configureren op basis van de Zimperium-risicoanalyse die via het Intune-nalevingsbeleid voor apparaten wordt ingeschakeld. U kunt met dit beleid de toegang tot bedrijfsresources voor niet-compatibele apparaten toestaan of blokkeren op basis van de gedetecteerde bedreigingen.

### <a name="new-settings-for-windows-10-device-restriction-profile------978575-1308849---"></a>Nieuwe instellingen voor het beperkingsprofiel voor Windows 10-apparaten  <!--- 978575, 1308849, -->  
Er worden nieuwe instellingen toegevoegd aan het apparaatbeperkingsprofiel voor Windows 10 in de categorie Windows Defender SmartScreen.

Zie [Apparaatbeperkingsinstellingen voor Windows 10-apparaten en hoger]( device-restrictions-windows-10.md) voor meer informatie.

### <a name="remote-support-for-windows-and-windows-mobile-devices------1070473---"></a>Externe ondersteuning voor Windows- en Windows Mobile-apparaten  <!-- 1070473 -->  
Intune kan de afzonderlijk verkrijgbare [TeamViewer](https://www.teamviewer.com)-software gebruiken zodat u uw gebruikers met Windows- en Windows Mobile-apparaten hulp op afstand kunt bieden.

### <a name="scan-devices-with-windows-defender----1280988--1280990-----"></a>Apparaten scannen met Windows Defender <!-- 1280988  1280990   -->
U kunt nu een **Snelle scan** en **Volledige scan** uitvoeren en **Handtekeningen bijwerken** met Windows Defender Antivirus op beheerde Windows 10-apparaten. Kies op de overzichtsblade van het apparaat de actie die u op het apparaat wilt uitvoeren. U wordt gevraagd om de actie te bevestigen voordat de opdracht naar het apparaat wordt verzonden. 

**Snelle scan**: een snelle scan scant locaties waar malware zich registreert, zoals registercodes en bekende opstartmappen in Windows. Een snelle scan duurt gemiddeld vijf minuten. In combinatie met de instelling **Realtimebeveiliging altijd ingeschakeld**, die bestanden scant wanneer ze worden geopend en gesloten en wanneer een gebruiker naar een map gaat, helpt een snelle scan om bescherming te bieden tegen malware die zich mogelijk in het systeem of de kernel bevindt. Gebruikers zien de scanresultaten op hun apparaten wanneer hij is voltooid. 

**Volledige scan**: een volledige scan kan handig zijn om vast te stellen of er inactieve componenten zijn die een diepgaandere opschoning vereisen op apparaten die met een malwarebedreiging te maken hebben gekregen. De scan is handig voor het uitvoeren van scans op aanvraag. Het uitvoeren van volledige scans kan een uur duren. Gebruikers zien de scanresultaten op hun apparaat wanneer de scan is voltooid. 

**Handtekeningen bijwerken**: de opdracht Handtekeningen bijwerken werkt de malwaredefinities en-handtekeningen in Windows Defender Antivirus bij. Dit helpt ervoor te zorgen dat Windows Defender Antivirus malware effectief detecteert. Deze functie is alleen voor Windows 10-apparaten en zolang er een internetverbinding is. 

### <a name="the-enabledisable-button-is-removed-from-the-intune-certificate-authority-page-of-the-intune-azure-portal-----1400455---"></a>De knop Inschakelen/Uitschakelen is verwijderd van de pagina Intune-certificaatinstantie van de Intune Azure-portal <!-- 1400455 -->
 We verwijderen een extra stap voor het instellen van de certificaatconnector in Intune. Op dit moment downloadt u de certificaatconnector en schakelt u die in de Intune-console in. Als u de connector echter uitschakelt in de Intune-console, blijft de connector toch certificaten uitgeven.

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Met ingang van oktober is de knop Inschakelen/Uitschakelen niet langer aanwezig op de pagina Certificaatinstantie in de Azure-portal. De functionaliteit van de connector blijft hetzelfde. Certificaten worden nog steeds geïmplementeerd naar apparaten die zijn ingeschreven in Intune. U kunt de certificaatconnector nog steeds downloaden en installeren. Als u niet langer certificaten wilt uitgeven, verwijdert u de certificaatconnector in plaats van dat u die uitschakelt.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
Als de certificaatconnector momenteel is uitgeschakeld, moet u die verwijderen.

### <a name="new-settings-for-windows-10-team-device-restriction-profile-------1308838---"></a>Nieuwe instellingen voor het beperkingsprofiel voor Windows 10 Team-apparaten <!--- 1308838 -->
In deze versie hebben we veel nieuwe instellingen toegevoegd aan het beperkingsprofiel voor Windows 10 Team-apparaten, om u te helpen bij het beheren van Surface Hub-apparaten.

Raadpleeg [Intune-apparaatbeperkingen voor Windows 10 Team](device-restrictions-windows-10-teams.md) voor meer informatie over dit profiel.

### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time-----1333292---"></a>Voorkomen dat gebruikers van Android-apparaten de datum en tijd van hun apparaat wijzigen  <!-- 1333292 -->
U kunt een [aangepast beleid voor Android-apparaten](custom-settings-android.md) gebruiken om te voorkomen dat gebruikers van Android-apparaten de datum en tijd van het apparaat wijzigen.

Configureer hiervoor een aangepast Android-beleid met de instelling URI ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange Stel dit in op **TRUE** en wijs het vervolgens toe aan de vereiste groepen.

### <a name="bitlocker-device-configuration----1397398---"></a>Configuratie van BitLocker-apparaat <!-- 1397398 -->
**Windows-versleuteling > Basisinstellingen** bevat een nieuwe instelling **Waarschuwing voor een andere schijfversleuteling** waarmee u de [waarschuwing](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption) voor versleuteling van een andere schijf die mogelijk op het apparaat van de gebruiker wordt gebruikt kunt uitschakelen.  De waarschuwing vereist dat eindgebruikers toestemming geven voordat ze BitLocker op het apparaat configureren en blokkeert de configuratie van Bitlocker totdat de eindgebruiker bevestigend heeft gereageerd.  De nieuwe instelling schakelt de waarschuwing voor de eindgebruiker uit.


### <a name="volume-purchase-program-for-business-apps-will-now-sync-to-your-intune-tenant----800882---"></a>Het volume-aankoopprogramma voor zakelijke apps synchroniseert nu met uw Intune-tenant <!-- 800882 -->  
Externe ontwikkelaars kunnen privé apps distribueren naar geautoriseerde VPP (volume-aankoopprogramma) for Business-leden die zijn opgegeven in iTunes Connect. Deze VPP for Business-leden kunnen zich aanmelden bij de Volume Purchase Program App Store en hun apps kopen.

Met ingang van deze release worden VPP for Business-apps die door de gebruiker zijn gekocht, gesynchroniseerd met hun Intune-tenant.

### <a name="select-apple-country-store-to-sync-vpp-apps-----1332311---"></a>Specifieke Apple Store selecteren om VPP-apps te synchroniseren  <!-- 1332311 -->  
U kunt de store in het land voor het volumeaankoopprogramma (VPP) configureren als u uw VPP-token uploadt. Intune synchroniseert VPP-apps voor alle landinstellingen uit de opgegeven store uit het land waar de VPP geldt.

> [!NOTE]  
> Op dit moment synchroniseert Intune alleen VPP-apps uit de store van het VPP-land dat overeenkomt met de Intune-landinstelling waarin de Intune-tenant werd gemaakt.


### <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>Kopiëren en plakken tussen werkprofielen en persoonlijke profielen blokkeren in Android for Work <!-- 1098994 -->
Door deze release kunt u het werkprofiel voor Android for Work zo configureren dat kopiëren en plakken tussen zakelijke en persoonlijke apps wordt geblokkeerd. U kunt deze nieuwe instelling vinden in het profiel **Apparaatbeperkingen** voor het **Android for Work**-platform onder **Werkprofielinstellingen**.

### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>iOS-apps maken die zijn beperkt tot specifieke regionale Apple App Stores <!-- 1281692 -->
U kunt de landinstelling voor een land opgeven wanneer u een beheerde app voor de Apple App Store maakt.

> [!Note]  
> Op dit moment kunt u alleen beheerde apps voor de Apple App Store maken die aanwezig zijn in de store voor de VS.

###  <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>Gelicentieerde iOS-apps voor VPP-gebruikers en -apparaten bijwerken  <!-- 1305564 -->  
U kunt het VPP-token voor iOS zo configureren dat alle apps die voor dat token zijn gekocht worden bijgewerkt via de Intune-service. Intune detecteert updates voor de VPP-app in de app store en stuurt ze automatisch naar het apparaat als dit incheckt.

Zie [iOS-apps beheren die zijn aangeschaft via een volumeaankoopprogramma met Microsoft Intune] (/intune/vpp-apps-ios) voor meer informatie over het instellen van een VPP-token en inschakelen van automatische updates.


### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Verzameling voor koppelingsentiteit voor apparaten van gebruikers toegevoegd aan het Intune-datawarehouse-gegevensmodel <!-- 1187917 -->
U kunt rapporten en gegevensvisualisaties maken met behulp van de informatie over de gebruikersapparaatkoppelingen; deze koppelen verzamelingen over gebruikers en apparaten. Het gegevensmodel is toegankelijk via het Power BI-bestand (PBIX) dat wordt opgehaald op de datawarehouse-pagina in Intune, via het OData-eindpunt of door een aangepaste client te ontwikkelen.

### <a name="review-policy-compliance-for-windows-10-update-rings----1067886---"></a>Naleving van het beleid voor Windows 10-update-ringen controleren <!-- 1067886 -->
U kunt een beleidsrapport voor uw Windows 10-update-ringen bekijken via Software-updates > Implementatiestatus per update-ring. Het beleidsrapport bevat de implementatiestatus voor de update-ringen die u hebt geconfigureerd. 

### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Nieuw rapport met iOS-apparaten met oudere iOS-versies   <!-- 1352223 -->
Het rapport **Out-of-date iOS Devices** (Verouderde iOS-apparaten) is beschikbaar in de werkruimte **Software-updates**. Het rapport bevat een lijst met gecontroleerde iOS-apparaten waarop een iOS-updatebeleid van toepassing is geweest en waarvoor updates beschikbaar zijn. Voor elk apparaat kunt u bekijken waarom het apparaat niet automatisch is bijgewerkt. 

### <a name="view-app-protection-policy-assignments-for-troubleshooting-----1475003---"></a>Beleidstoewijzingen voor app-beveiliging bekijken om problemen op te lossen <!--  1475003 -->
In deze toekomstige release wordt de optie **App-beveiligingsbeleid** toegevoegd aan de vervolgkeuzelijst **Toewijzingen** op de blad voor probleemoplossing. U kunt nu beleid voor app-beveiliging selecteren om de beleidsregels voor app-beveiliging te zien die aan de geselecteerde gebruikers zijn toegewezen.



### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a>Verbeteringen in de werkstroom voor apparaatinstellingen in de bedrijfsportal <!--1490692-->
We hebben de werkstroom voor apparaatinstellingen in de bedrijfsportal-app voor Android verbeterd. De taal is gebruiksvriendelijker en specifiek voor uw bedrijf. Daarnaast hebben we waar mogelijk schermen gecombineerd. U kunt deze zien op de pagina [Nieuw in de app-gebruikersinterface](whats-new-app-ui.md#week-of-october-2-2017).

### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices---1484985--"></a>Verbeterde richtlijnen voor het aanvragen van toegang tot contactpersonen op Android-apparaten <!--1484985-->

Voor de bedrijfsportal-app voor Android moet de eindgebruiker vaak de machtiging Contactpersonen accepteren. Als een eindgebruiker deze toegang weigert, ziet deze nu een melding in de app waarin wordt aangegeven dat deze moet worden verleend voor voorwaardelijke toegang. 

### <a name="secure-startup-remediation-for-android---1490712--"></a>Beveiligd opstartherstel voor Android<!--1490712-->

Eindgebruikers met Android-apparaten kunnen tikken op de reden van niet-naleving in de bedrijfsportal-app. Indien mogelijk worden ze hiermee rechtstreeks naar de juiste locatie geleid in de instellingen-app om het probleem te verhelpen. 

### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-oreo---1475932--"></a>Aanvullende pushmeldingen voor eindgebruikers op de bedrijfsportal-app voor Android Oreo <!--1475932-->

Eindgebruikers ontvangen aanvullende meldingen wanneer de bedrijfsportal-app voor Android Oreo achtergrondtaken uitvoert, zoals het ophalen van beleid van de Intune-service. Dit biedt gebruikers meer transparantie over wanneer de bedrijfsportal-app beheertaken uitvoert op hun apparaat. Dit maakt deel uit van de algehele [optimalisatie van de gebruikersinterface van de bedrijfsportal](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) voor de bedrijfsportal-app voor Android Oreo. 

Er zijn nog meer optimalisaties voor nieuwe UI-elementen die in Android Oreo zijn ingeschakeld.  Eindgebruikers ontvangen aanvullende meldingen wanneer de bedrijfsportal achtergrondtaken uitvoert, zoals het ophalen van beleid van de Intune-service.  Dit biedt eindgebruikers meer transparantie over wanneer met de bedrijfsportal-app beheertaken worden uitgevoerd op het apparaat.

### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>Nieuw gedrag voor de bedrijfsportal-app voor Android met werkprofielen <!-- 1485783 -->

Als u een Android voor Work-apparaat met een werkprofiel inschrijft, voert de bedrijfsportal-app in het werkprofiel beheertaken uit op het apparaat. 

De bedrijfsportal-app voor Android wordt niet langer gebruikt, tenzij u een app met MAM-functionaliteit in het persoonlijke profiel gebruikt. Intune zal automatisch de persoonlijke bedrijfsportal-app verbergen om uw ervaring met het werkprofiel te verbeteren nadat de inschrijving van het werkprofiel is geslaagd.

De bedrijfsportal-app voor Android kan op elk gewenst moment in het persoonlijke profiel worden ingeschakeld door naar [Bedrijfsportal te zoeken in de Play Store](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) en op **Inschakelen** te tikken.

### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>Bedrijfsportal voor Windows 8.1 en Windows Phone 8.1 wordt verplaatst naar onderhoudsmodus <!--1428681-->

Vanaf oktober 2017 worden de bedrijfsportal-apps voor Windows 8.1 en Windows Phone 8.1 verplaatst naar de onderhoudsmodus. Dit betekent dat de apps en bestaande scenario’s, zoals inschrijving en naleving, op deze platforms ondersteund blijven worden. De apps blijven beschikbaar om te worden gedownload via bestaande release-kanalen, zoals de Microsoft Store. 

In de onderhoudsmodus worden er alleen kritieke beveiligingsupdates voor deze apps uitgebracht. Er worden geen extra updates of functies voor deze apps uitgebracht. Wanneer u nieuwe functies wilt, raden we u aan om uw apparaten bij te werken naar Windows 10 of Windows 10 Mobile. 


### <a name="block-unsupported-samsung-knox-device-enrollment-----1490695---"></a>Registratie van niet-ondersteunde Samsung Knox-apparaten blokkeren <!-- 1490695 -->

Via de bedrijfsportal-app worden alleen ondersteunde Samsung Knox-apparaten geregistreerd. Om Knox-activeringsfouten te voorkomen waardoor de MDM-registratie onmogelijk wordt, wordt de apparaatregistratie alleen uitgevoerd als het apparaat wordt weergegeven in de [lijst met apparaten die is gepubliceerd door Samsung](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Bepaalde modelnummers van Samsung-apparaten bieden ondersteuning voor Knox, andere niet. Controleer de KNOX-compatibiliteit bij de verkoper van uw apparaat voordat u een apparaat koopt en implementeert. U vindt de volledige lijst met gecontroleerde apparaten in de [beleidsinstellingen voor Android en Samsung Knox Standard](/intune/supported-devices-browsers.md#intune-supported-web-browsers).

### <a name="end-of-support-for-android-43-and-lower----1171126-1326920---"></a>Einde van ondersteuning voor Android 4.3 en lager <!-- 1171126, 1326920 -->
Beheerde apps en de Intune-bedrijfsportal-app voor Android vereisen Android 4.4 en hoger voor toegang tot bedrijfsresources. Vanaf december worden alle ingeschreven apparaten verplicht buiten gebruik gesteld, waardoor bedrijfsresources niet meer toegankelijk zijn. Als u beleid voor app-beveiliging zonder MDM gebruikt, krijgen apps geen updates meer en neemt de gebruikservaring na verloop van tijd steeds verder af.

### <a name="inform-end-users-what-device-information-can-be-seen-on-enrolled-devices---1165314--"></a>Eindgebruikers informeren over welke apparaatgegevens worden weergegeven op geregistreerde apparaten <!--1165314-->
Aan het scherm voor apparaatgegevens in alle bedrijfsportal-apps wordt de optie **Eigendomstype** toegevoegd. Hierdoor kunnen gebruikers meer over privacy te weten komen rechtstreeks via het artikel [Welke informatie kan uw bedrijf zien?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune) Dit zal binnenkort worden geïmplementeerd in alle bedrijfsportal-apps. Voor iOS hebben we dit aangekondigd in [september](https://docs.microsoft.com/intune/whats-new#week-of-september-11-2017).

## <a name="september-2017"></a>September 2017

### <a name="intune-supports-ios-11---1428975--"></a>Intune biedt ondersteuning voor iOS 11 <!--1428975-->
Intune biedt ondersteuning voor iOS 11. Dit werd eerder aangekondigd in de [blog Intune Support](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/).

### <a name="end-of-support-for-ios-80----1164477---"></a>Einde van ondersteuning voor iOS 8.0 <!-- 1164477 -->
Beheerde apps en de Intune-bedrijfsportal-app voor iOS vereisen iOS 9.0 en hoger voor toegang tot bedrijfsresources. Apparaten die niet voor september zijn bijgewerkt, hebben geen toegang meer tot de bedrijfsportal of beheerde apps. 

### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Actie voor vernieuwen toegevoegd aan de bedrijfsportal-app voor Windows 10 <!--1132468-->
Met de bedrijfsportal-app voor Windows 10 kunnen gebruikers de gegevens in de app vernieuwen door deze op te halen voor vernieuwing of door op pc’s op F5 te drukken.

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
<!-- 961134, 1104426, 1281327, 1333543 -->In deze versie zijn de volgende verbeteringen aangebracht in de inventarisatiegegevens die zijn verzameld door apparaten die u beheert:
 
-   Voor Android-apparaten kunt u nu een kolom aan de apparaatinventaris toevoegen die het meest recente patchniveau voor elk apparaat laat zien. Voeg de kolom **Beveiligingspatchniveau** toe aan uw apparatenlijst om dit te zien.
-   Als u de apparaatweergave filtert, kunt u nu apparaten filteren op de datum waarop ze zijn geregistreerd. U kunt bijvoorbeeld alleen die apparaten weergeven die zijn geregistreerd na een datum die u opgeeft.
-   We hebben verbeteringen aangebracht aan het filter dat wordt gebruikt door het **Laatste check-in**-item.
-   U kunt nu het telefoonnummer van bedrijfsapparaten weergeven in de lijst met apparaten.
Daarnaast kunt u het filterdeelvenster gebruiken om te zoeken naar apparaten op telefoonnummer.
 
Zie [Inventaris van Intune-apparaten weergeven](device-inventory.md) voor meer informatie over apparaatinventarisatie.

### <a name="conditional-access-support-for-macos-devices"></a>Ondersteuning voor voorwaardelijke toegang voor macOS-apparaten 
<!-- 720172 -->U kunt nu een beleid voor voorwaardelijke toegang instellen waardoor Mac-apparaten moeten worden geregistreerd bij Intune en moeten voldoen aan het Intune-nalevingsbeleid voor apparaten. Gebruikers kunnen bijvoorbeeld de Intune-bedrijfsportal-app voor macOS downloaden en hun Mac-apparaten registreren bij Intune. Er wordt vervolgens een evaluatie uitgevoerd in Intune om te bepalen of het Mac-apparaat al dan niet voldoet aan vereisten zoals pincode, versleuteling, versie van het besturingssysteem en systeemintegriteit.

- Meer informatie over [ondersteuning voor voorwaardelijke toegang voor macOS-apparaten](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).

### <a name="company-portal-app-for-macos-is-in-public-preview----1484796---"></a>Bedrijfsportal-app voor macOS is in openbare preview <!---1484796--->
De bedrijfsportal-app voor macOS is nu beschikbaar als onderdeel van de openbare preview voor voorwaardelijke toegang in Enterprise Mobility + Security. Deze release ondersteunt macOS 10.11 en hoger. Download deze vanaf [https://aka.ms/macOScompanyportal](https://aka.ms/macOScompanyportal). 


### <a name="new-device-restriction-settings-for-windows-10"></a>Nieuwe apparaatbeperkingsinstellingen voor Windows 10    
<!--1063965, 1308850  -->In deze release hebben we nieuwe instellingen toegevoegd voor het [profiel voor apparaatbeperking van Windows 10](/intune/device-restrictions-windows-10), en wel in de volgende categorieën:

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
<!-- 1016201 --> IT-beheerders kunnen nu op apps gebaseerd voorwaardelijk beleid instellen via de nieuwe gebruikersinterface voor beleid voor voorwaardelijke toegang in de Azure AD-werkbelasting. De op apps gebaseerde voorwaardelijke toegang in de sectie Intune-app-beveiliging in de Azure-portal blijft hier voorlopig aanwezig en wordt naast elkaar afgedwongen. Er is in de Intune-werkbelasting ook een handige koppeling naar de nieuwe gebruikersinterface voor beleid voor voorwaardelijke toegang.

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
-  Microsoft Edge-browser

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
Wanneer u een SCEP-certificaatprofiel maakt voor <strong>indeling van de onderwerpnaam</strong>, is de <strong>aangepaste</strong> optie beschikbaar voor iOS-, Android- en Windows-apparaten. Voor deze update was het veld <strong>aangepast</strong> beschikbaar voor iOS-apparaten. Zie [Een SCEP-certificaatprofiel maken](certificates-scep-configure.md#create-a-scep-certificate-profile) voor meer informatie.

Wanneer u een PKCS certificaatprofiel maakt, is voor **Alternatieve naam voor onderwerp** het **Aangepaste Azure AD-kenmerk** beschikbaar. De optie **Afdeling** is beschikbaar wanneer u **Aangepast Azure AD-kenmerk** selecteert. Zie [Een PKCS-certificaatprofiel maken](certficates-pfx-configure.md#create-a-pkcs-certificate-profile) voor meer informatie.

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
