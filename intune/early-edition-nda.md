---
title: Vroege editie | Microsoft Intune
titlesuffix: ''
description: Vroege editie van Microsoft Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/09/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 0efc84da6a9efb594600b9ca33aa5eb7622c8101
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203430"
---
# <a name="the-early-edition-for-microsoft-intune---january-2019"></a>De vroege editie voor Microsoft Intune - januari 2019

> [!Note]
> NDA-melding: De volgende wijzigingen worden momenteel ontwikkeld voor Intune. Deze informatie wordt in heel beperkte mate verstrekt onder de geheimhoudingsverklaring. Plaats deze informatie niet op sociale media of openbare websites als Twitter, UserVoice, Reddit, enzovoort. 

De **vroege editie** bevat een lijst met functies, gedeeld onder geheimhoudingsverklaring, die worden toegevoegd aan toekomstige releases van Microsoft Intune. Deze informatie wordt in beperkte mate verstrekt en kan worden gewijzigd. Stuur over deze informatie geen tweets, plaats hier niets over op UserVoice en deel hier op geen enkele andere wijze iets over buiten uw bedrijf. Sommige functies die hier worden vermeld, zullen mogelijk niet beschikbaar zijn op de sluitingsdatum en worden mogelijk beschikbaar gesteld in een latere release. Andere functies worden getest in een proefversie, zodat we zeker weten dat ze in gebruik kunnen worden genomen. Als u vragen of opmerkingen hebt, kunt contact opnemen met uw contactpersoon voor de Microsoft-productgroep.

Deze pagina wordt regelmatig bijgewerkt. Controleer op andere updates.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune in Azure Portal

<!-- 1901 start -->

### <a name="android-enterprise-apps----1352553----"></a>Android Enterprise-apps <!-- 1352553  -->
U kunt beheerde Google Play-apps verwijderen uit Microsoft Intune. Als u een beheerde Google Play-app wilt verwijderen, opent u Microsoft Intune in Azure Portal en selecteert u **Client-apps** > **Apps**. In de lijst met apps selecteert u het beletselteken (...) rechts naast de beheerde Google Play-app en vervolgens **Verwijderen** in de weergegeven lijst. Wanneer u een beheerde Google Play-app uit de lijst met apps verwijdert, wordt de goedkeuring voor de beheerde Google Play-app automatisch verwijderd.

### <a name="managed-google-play-app-type----1352580---"></a>App-type Beheerde Google Play-app <!-- 1352580 -->
Met het type **beheerde Google Play-app** hebt u toestemming om specifiek [beheerde Google Play-apps](https://play.google.com/work/search?q=microsoft&c=apps) aan Intune toe te voegen. Als Intune-beheerder kunt u nu door goedgekeurde beheerde Google Play-apps bladeren en goedgekeurde beheerde Google Play-apps zoeken, goedkeuren, synchroniseren en toewijzen in Intune. U hoeft niet langer naar de beheerde Google Play-console afzonderlijk te bladeren en u hoeft niet opnieuw een verificatie uit te voeren. Selecteer in Intune de optie **Client-apps** > **Apps** > **Toevoegen**. In de lijst **App-type** selecteert u **Beheerd Google Play** als app-type.

### <a name="preview-of-support-for-android-corporate-owned-fully-managed-devices----1574342----"></a>Voorbeeld van volledig beheerde, zakelijke Android-apparaten <!-- 1574342  -->
Intune ondersteunt volledig beheerde Android-apparaten, een scenario waarin apparaten 'zakelijk eigendom' zijn en nauw worden beheerd door de IT-afdeling en gekoppeld zijn aan afzonderlijke gebruikers. Hierdoor kunnen beheerders het hele apparaat beheren, een uitgebreide reeks beleidscontroles afdwingen die niet beschikbaar zijn voor werkprofielen en gebruikers beperken tot de installatie van apps uit de beheerde Google Play Store. Ga naar **Apparaatinschrijving** > **Android-inschrijving** > **Volledig beheerde zakelijke gebruikersapparaten** om volledige beheerde Android-apparaten in te stellen. Let op: deze functie wordt momenteel als preview aangeboden. Sommige Intune-mogelijkheden, zoals certificaten, naleving en voorwaardelijke toegang, zijn momenteel niet beschikbaar voor volledig beheerde Android-gebruikersapparaten.

### <a name="deployment-of-online-licensed-microsoft-store-for-business-apps----1672660----"></a>Implementatie van online gelicentieerde Microsoft Store voor Bedrijven-apps <!-- 1672660  -->
U kunt vereiste online gelicentieerde Microsoft Store voor Bedrijven-apps in de apparaatcontext toewijzen. Wanneer u op deze manier een Microsoft Store voor bedrijven-app implementeert, kan de app worden geïnstalleerd voor alle gebruikers op het apparaat. Dit is alleen van toepassing op Windows 10 RS4+ Desktop-apparaten. De optie om de app in de apparaatcontext te installeren, is beschikbaar op de toewijzingspagina voor client-apps voor gelicentieerde MSFB Online-apps.

### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470----"></a>Profiel configureren om bepaalde vensters over te slaan tijdens het doorlopen van de configuratieassistent <!-- 2276470  -->
Wanneer u een macOS-registratieprofiel maakt, kunt u binnenkort instellen dat de configuratieassistent de volgende schermen overslaat:
- Migratie vanaf Android
- Weergavekleur
- Privacy
- iCloudStorage

### <a name="assign-autopilot-profiles-to-the-all-devices-virtual-group---2715522----"></a>Autopilot-profielen toewijzen aan de virtuele groep Alle apparaten <!--2715522  -->
U kunt Autopilot-profielen toewijzen aan de virtuele groep Alle apparaten. Kies hiervoor **Inschrijving apparaat** > **Inschrijving Windows** > **Implementatieprofielen** > kies een profiel >  **Toewijzingen** > onder  **Toewijzen aan** kies **Alle apparaten**. Zie [Windows-apparaten inschrijven met Windows AutoPilot](enrollment-autopilot.md) voor meer informatie over Autopilot-profielen.

### <a name="customize-wallpaper-on-supervised-ios-devices-using-a-device-configuration-profile----2809324----"></a>Achtergronden op iOS-apparaten die onder toezicht staan aanpassen met behulp van een apparaatconfiguratieprofiel <!-- 2809324  -->
Wanneer u een apparaatconfiguratieprofiel voor iOS-apparaten maakt, kunt u bepaalde instellingen toestaan en beperken onder **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype. Deze update bevat nieuwe instellingen voor **Achtergrond** waardoor een beheerder een .png-, .jpg- of .jpeg-afbeelding als achtergrond kan instellen, een voorbeeld van de afbeelding kan bekijken en voorkomen dat gebruikers de achtergrond kunnen veranderen. De achtergrondinstellingen zijn alleen van toepassing op apparaten die onder toezicht staan. Zie [Beperkingsinstellingen voor iOS-apparaten](device-restrictions-ios.md) voor een lijst met de huidige instellingen.

### <a name="toast-notifications-for-win32-apps----3136566-----"></a>Toast-meldingen voor Win32-apps <!-- 3136566   -->
U kunt per app-toewijzing onderdrukken dat toast-meldingen voor eindgebruikers worden weergegeven. Vanuit Intune selecteert u **Client-apps** > **Apps** > selecteer de app > **Toewijzingen** > **Groepen opnemen**. 

### <a name="contact-sharing-via-bluetooth-is-removed-in-device-restrictions--device-owner-for-android-enterprise----3598396---"></a>Contactpersonen delen via Bluetooth wordt verwijderd in Apparaatbeperkingen > Apparaateigenaar voor Android Enterprise <!-- 3598396 -->
Wanneer u een apparaatbeperkingsbeleid voor Android Enterprise-apparaten maakt, is de instelling **Contactpersoon delen via Bluetooth** beschikbaar. In deze update wordt de instelling **Contactpersoon delen via Bluetooth** verwijderd (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** voor platform > **Apparaatbeperkingen > Apparaateigenaar** voor Profieltype > **Algemeen**). 

De instelling **Contactpersoon delen via Bluetooth** wordt niet ondersteund voor het beheer van Android Enterprise-apparaateigenaren. Wanneer deze instelling wordt verwijderd, heeft dit dus geen invloed op apparaten of tenants, zelfs als deze instelling is ingeschakeld en geconfigureerd in uw omgeving.

Ga naar [Met Android Enterprise-apparaatinstellingen functies toestaan of beperken](device-restrictions-android-for-work.md) voor de huidige lijst met instellingen.

Van toepassing op: Android Enterprise-apparaateigenaar

<!-- 1812 start -->

### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Android Enterprise APP WE-app-implementatie <!-- 1171203 -->
Voor Android-apparaten in een niet-geregistreerd App Protection Policy Without Enrollment-implementatiescenario (APP-WE), gebruikt u de beheerde Google Play Store om store-apps en LOB-apps te implementeren bij gebruikers. In het bijzonder kan de IT-afdeling eindgebruikers voorzien van een app-catalogus en een installatie waarbij het niet langer nodig is dat eindgebruikers de beveiligingsstatus van hun apparaten versoepelen door installaties uit onbekende bronnen toe te staan. Bovendien biedt dit implementatiescenario een verbeterde eindgebruikerservaring.

### <a name="the-intune-app-sdk-will-support-256-bit-encryption-keys----1832174---"></a>De Intune App-SDK ondersteunt 256-bits versleutelingssleutels <!-- 1832174 -->
De Intune App-SDK voor Android gebruikt 256-bits versleutelingssleutels wanneer versleuteling is ingeschakeld door app-beveiligingsbeleid. De SDK biedt doorgaande ondersteuning voor 128-bits sleutels voor compatibiliteit met inhoud en apps die gebruikmaken van oudere SDK-versies.


### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359---"></a>Intune-beleid werkt de verificatiemethode en installatie van de Bedrijfsportal-app bij <!-- 1927359 -->
Intune biedt geen ondersteuning meer voor de Bedrijfsportal wanneer deze handmatig door eindgebruikers uit de appstore wordt geïnstalleerd op apparaten die al met behulp van Configuratieassistent zijn ingeschreven via een van de Apple-registratiemethoden voor bedrijfsapparaten. Deze wijziging is alleen relevant wanneer u tijdens de inschrijving verifieert met Apple Setup Assistant. Deze wijziging is eveneens alleen van invloed op iOS-apparaten die zijn ingeschreven via:  
* Apple Configurator
* Apple Business Manager
* Apple School Manager
* Apple Device Enrollment Program (DEP)

Als gebruikers de Bedrijfsportal-app installeren uit de App Store en vervolgens apparaten via de app proberen te registreren, treedt er een foutmelding op. Er wordt van uitgegaan dat deze apparaten de Bedrijfsportal alleen gebruiken wanneer het automatisch door Intune tijdens de registratie is gepusht. Inschrijvingsprofielen in Intune in de Azure-portal worden bijgewerkt zodat u kunt opgeven hoe apparaten zich verifiëren en hoe zij de Bedrijfsportal-app ontvangen. Als u wilt dat uw DEP-apparaatgebruikers de Bedrijfsportal hebben, moet u uw voorkeuren in een inschrijvingsprofiel opgeven. Bovendien wordt binnenkort het scherm **Uw apparaat identificeren** in de Bedrijfsportal-app niet meer gebruikt.  
Als u de Bedrijfsportal wilt installeren op DEP-apparaten die al zijn ingeschreven, gaat u naar Intune > Client-apps en pusht u de app als beheerde app met app-configuratiebeleid. Details over hoe u deze stappen uitvoert, worden beschreven in toekomstige documentatie.

### <a name="non-administrators-can-enable-bitlocker-on-windows-10-devices-joined-to-azure-ad---2147379---"></a>Niet-beheerders kunnen BitLocker gebruiken op Windows 10-apparaten die zijn gekoppeld aan Azure AD<!-- 2147379 -->
Wanneer u BitLocker-instellingen op Windows 10-apparaten inschakelt (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** als platform en **Endpoint Protection** als profieltype > **Windows-versleuteling**), voegt u BitLocker-instellingen toe. Deze update bevat een nieuwe BitLocker-instellingen waarmee standaardgebruikers (niet-beheerders) versleuteling kunnen inschakelen. Raadpleeg [Endpoint Protection-instellingen voor Windows 10](endpoint-protection-windows-10.md#windows-encryption) als u de huidige instellingen wilt bekijken.


### <a name="additional-settings-for-outlook----3301182---"></a>Extra instellingen voor Outlook <!-- 3301182 -->
U kunt nu aanvullende instellingen voor Outlook voor iOS en Android configureren met Intune.  Deze instellingen zijn onder andere:
- Instellen dat alleen werk- of schoolaccounts mogen worden gebruikt in Outlook in iOS en Android
- Moderne verificatie implementeren voor Office 365 en hybride moderne verificatie voor on-premises accounts
- `SAMAccountName` gebruiken in het gebruikersnaamveld in het e-mailprofiel als basisverificatie wordt geselecteerd
- Toestaan dat contactpersonen worden opgeslagen
- E-mailtips voor externe ontvangers configureren
- Het **Postvak IN met prioriteit** configureren
- Biometrie vereisten voor toegang tot Outlook in iOS 
- Externe afbeeldingen blokkeren

> [!NOTE]
> Als u gebruikmaakt van Intune-app-beveiligingsbeleid voor het beheren van toegang tot bedrijfs-id's, wordt afgeraden **biometrie te vereisen**. Zie **Bedrijfsreferenties vereisen voor toegang** voor [iOS-toegangsvereisten](app-protection-policy-settings-ios.md#access-settings) en [Android-toegangsvereisten](app-protection-policy-settings-android.md#access-settings).

### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Beheersjablonen zijn in openbare preview en verplaatst naar hun eigen configuratieprofiel <!-- 3322847 -->
Beheersjablonen in Intune (**Apparaatconfiguratie** > **Beheersjablonen**) zijn momenteel in openbare preview. Bij deze update: Beheersjablonen omvatten circa 300 instellingen die kunnen worden beheerd in Intune. Eerder bestonden deze instellingen alleen in de editor voor groepsbeleid.
Beheersjablonen zijn beschikbaar in openbare preview en worden verplaatst van **Apparaatconfiguratie** > **Beheersjablonen** naar **Apparaatconfiguraatie** > **Profielen** >**Profiel maken** > kies als **Platform** **Windows 10 en later** en kies in **Profieltype** **Beheersjablonen**.
Rapportage is ingeschakeld is van toepassing op: Windows 10 en hoger

### <a name="intune-macos-company-portal-dark-mode----3300524---"></a>Donkere modus van Intune macOS Bedrijfsportal <!-- 3300524 -->
De Intune macOS Bedrijfsportal biedt nu ondersteuning voor de donkere modus voor macOS. Wanneer u de donkere modus inschakelt op een macOS 10.14+-apparaat, wordt de vormgeving door de Bedrijfsportal aangepast naar kleuren die overeenkomen met die modus.

<!-- 1810 start -->

### <a name="use-microsoft-recommended-settings-with-security-baselines----2055484---"></a>Door Microsoft aanbevolen instellingen gebruiken met beveiligingsbasislijnen <!-- 2055484 -->
Intune is geïntegreerd met andere services die op beveiliging gericht zijn, inclusief Windows Defender ATP en Office 365 ATP. Klanten vragen om een gemeenschappelijke strategie en een samenhangende set van end-to-end beveiligingsworkflows voor alle Microsoft 365-diensten. Ons doel is om strategieën af te stemmen en oplossingen te ontwikkelen die beveiligingsactiviteiten en gebruikelijke beheerderstaken combineren. In Intune willen we dit doel bereiken door het publiceren van een set beveiligingsbasislijnen die door Microsoft zijn aanbevolen (**Intune** >  **Beveiligingsbasislijnen**).  Beheerders krijgen de mogelijkheid om direct op basis van deze basislijnen een beveiligingsbeleid op te stellen en dit vervolgens voor hun gebruikers te implementeren. Ze kunnen ook de aanbevolen procedures aanpassen aan de behoeften van hun organisatie. Intune zorgt ervoor dat apparaten deze basislijnen blijven naleven, en waarschuwt beheerders wanneer gebruikers of apparaten van de basislijnen afwijken.

### <a name="deployed-wip-policies-without-user-enrollment----1434452---"></a>Geïmplementeerd WIP-beleid zonder gebruikersinschrijving <!-- 1434452 -->
WIP-beleid (Windows Information Protection) kan worden ingezet zonder dat MDM-gebruikers hun Windows 10-apparaat hoeven in te schrijven. Met deze configuratie kunnen bedrijven hun bedrijfsdocumenten op basis van de WIP-configuratie beschermen, terwijl gebruikers hun eigen Windows-apparaten kunnen blijven beheren. Zodra documenten met WIP-beleid zijn beveiligd, kunnen de beschermde gegevens selectief worden gewist door een Intune-beheerder. Door een gebruiker en een apparaat te selecteren een en wisaanvraag te versturen, worden alle gegevens onbruikbaar die met het WIP-beleid zijn beschermd. Vanuit Intune in de Azure-portal selecteert u hiervoor **Mobiele app** > **App selectief wissen**.


<!-- 1809 start -->  

### <a name="app-protection-policy-app-settings-for-web-data----2662995---"></a>APP-instellingen voor webgegevens <!-- 2662995 -->
De APP-instellingen voor webcontent op zowel Android- als iOS-apparaten worden bijgewerkt om zowel http- als https-webkoppelingen beter te kunnen verwerken, evenals de gegevensoverdracht via iOS Universal- en Android App-koppelingen.  

<!-- 1808 start -->

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Apple VPP-token die wordt gebruikt door een andere MDM <!-- 1488946 -->
Intune kan detecteren of een token van het volumeaankoopprogramma van Apple (VPP) wordt gebruikt door zowel Intune als een andere MDM en vervolgens meer informatie weergeven.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Buiten gebruik gestelde apparaten in het dashboard voor apparaatnaleving <!-- 1981119 -->
In een toekomstige update worden buiten gebruik gestelde apparaten verwijderd uit het dashboard voor apparaatnaleving. Dit zorgt voor veranderingen in de aantallen in uw nalevingsrapporten.



<!-- 1807 start -->

### <a name="check-for-configuration-manager-compliance----2192052---"></a>Controleren op Configuration Manager-compatibiliteit <!-- 2192052 -->
Een toekomstige update bevat een nieuwe instelling voor System Center Configuration Manager-compatibiliteit (**Apparaatcompatibiliteit** > **Beleid** > **Beleid maken** > **Windows 10**). Configuration Manager verzendt signalen naar Intune-naleving. Met de Intune-instelling kunt u vereisen dat alle Configuration Manager-signalen de waarde 'compatibel' retourneren.

U kunt bijvoorbeeld vereisen dat alle software-updates worden geïnstalleerd op apparaten. Deze vereiste heeft in Configuration Manager de status 'Geïnstalleerd'. Als programma's op het apparaat zich in onbekende staat bevinden, is het apparaat niet-compatibel in Intune.

Van toepassing op Windows 10 en hoger



## <a name="notices"></a>Mededelingen

Er zijn geen actieve meldingen op dit moment.

### <a name="see-also"></a>Zie ook
Zie [Wat is er nieuw in Microsoft Intune?](whats-new.md) voor meer informatie over recente ontwikkelingen.



