---
title: Vroege editie
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/3/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: d00c367cdcd0b8172d64c3ebbcd0dec2165407c9
ms.sourcegitcommit: b93db06ba435555f5b126f97890931484372fcfb
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/04/2018
ms.locfileid: "52829127"
---
# <a name="the-early-edition-for-microsoft-intune---december-2018"></a>De vroege editie voor Microsoft Intune - december 2018

> [!Note]
> Melding geheimhoudingsverklaring: de volgende wijzigingen worden momenteel ontwikkeld voor Intune. Deze informatie wordt in heel beperkte mate verstrekt onder de geheimhoudingsverklaring. Plaats deze informatie niet op sociale media of openbare websites als Twitter, UserVoice, Reddit, enzovoort. 

De **vroege editie** bevat een lijst met functies, gedeeld onder geheimhoudingsverklaring, die worden toegevoegd aan toekomstige releases van Microsoft Intune. Deze informatie wordt in beperkte mate verstrekt en kan worden gewijzigd. Stuur over deze informatie geen tweets, plaats hier niets over op UserVoice en deel hier op geen enkele andere wijze iets over buiten uw bedrijf. Sommige functies die hier worden vermeld, zullen mogelijk niet beschikbaar zijn op de sluitingsdatum en worden mogelijk beschikbaar gesteld in een latere release. Andere functies worden getest in een proefversie, zodat we zeker weten dat ze in gebruik kunnen worden genomen. Als u vragen of opmerkingen hebt, kunt contact opnemen met uw contactpersoon voor de Microsoft-productgroep.

Deze pagina wordt regelmatig bijgewerkt. Controleer op andere updates.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune in Azure Portal

<!-- 1812 start -->

### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Android Enterprise APP WE-app-implementatie <!-- 1171203 -->
Voor Android-apparaten in een niet-geregistreerd App Protection Policy Without Enrollment-implementatiescenario (APP-WE), gebruikt u de beheerde Google Play Store om store-apps en LOB-apps te implementeren bij gebruikers. In het bijzonder kan de IT-afdeling eindgebruikers voorzien van een app-catalogus en een installatie waarbij het niet langer nodig is dat eindgebruikers de beveiligingsstatus van hun apparaten versoepelen door installaties uit onbekende bronnen toe te staan. Bovendien biedt dit implementatiescenario een verbeterde eindgebruikerservaring.

### <a name="new-options-to-automatically-connect-and-persist-rules-when-using-dns-settings-on-windows-10-and-later-devices----1333665-2999078---"></a>Nieuwe opties om automatisch verbinding te maken en regels te behouden met DNS-instellingen in Windows 10 en hoger <!-- 1333665, 2999078 -->
In Windows 10 en hoger kunt u een VPN-configuratieprofiel maken dat een lijst DNS-servers bevat om domeinen om te zetten, zoals contoso.com. Dit is inclusief nieuwe instellingen voor naamomzetting: (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > Kies **Windows 10 en hoger** als platform > Kies **VPN** als profieltype > **DNS-instellingen** >**Toevoegen**): 

- **Automatisch verbinden**: wanneer dit is **ingeschakeld**, maakt het apparaat automatisch verbinding met VPN wanneer een apparaat een domein oproept dat u invoert, bijvoorbeeld contoso.com.
- **Permanent**: standaard zijn alle tabelregels voor Naamomzettingsbeleid (NRPT) actief zolang het apparaat is verbonden met behulp van dit VPN-profiel. Wanneer deze instelling is **ingeschakeld** voor een NRPT-regel, blijft de regel actief op het apparaat, zelfs wanneer de VPN-verbinding wordt verbroken of het VPN-profiel wordt verwijderd. De regel blijft totdat deze handmatig wordt verwijderd, wat met PowerShell kan worden gedaan.

In de [Windows 10 VPN-instellingen](vpn-settings-windows-10.md) wordt de huidige lijst instellingen beschreven. 

### <a name="help-and-support-page-in-the-windows-company-portal-app----1488939---"></a>Pagina Help en ondersteuning in de Windows Bedrijfsportal-app <!-- 1488939 -->
Er wordt een nieuwe pagina toegevoegd aan de Windows Bedrijfsportal-app. De pagina Help en ondersteuning biedt contactgegevens van de Helpdesk. Eindgebruikers kunnen eveneens Bedrijfsportallogboeken verzenden wanneer ze problemen ondervinden. De pagina biedt ook een gedeelte met veelgestelde vragen om eindgebruikers te helpen.

### <a name="use-trusted-network-detection-for-vpn-profiles-on-windows-10-devices----1500165---"></a>Detectie van vertrouwde netwerken gebruiken voor VPN-profielen in Windows 10-apparaten <!-- 1500165 -->
Wanneer u gebruikmaakt van detectie van vertrouwde netwerken, kunt u voorkomen dat VPN-profielen automatisch een VPN-verbinding maken wanneer de gebruiker zich op een vertrouwd netwerk bevindt. U kunt DNS-achtervoegsels toevoegen om detectie van vertrouwde netwerken in te schakelen op apparaten met Windows 10 en hoger (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** als platform en **VPN** als profieltype).
In [VPN-instellingen voor Windows 10](vpn-settings-windows-10.md) worden de huidige VPN-instellingen vermeld.

### <a name="support-for-android-corporate-owned-fully-managed-devices----574342---"></a>Ondersteuning voor volledig beheerde, zakelijke Android-apparaten <!-- 574342 -->
Intune ondersteunt volledig beheerde Android-apparaten, een scenario waarin apparaten 'zakelijk eigendom' zijn en nauw worden beheerd door de IT-afdeling en gekoppeld zijn aan afzonderlijke gebruikers. Hierdoor kunnen beheerders het hele apparaat beheren, een uitgebreide reeks beleidscontroles afdwingen die niet beschikbaar zijn voor werkprofielen en gebruikers beperken tot de installatie van apps uit de beheerde Google Play Store. Ga naar **Apparaatinschrijving** > **Android-inschrijving** > **Bedrijfseigendom, volledig beheerde gebruikersapparaten** om volledige beheerde Android-apparaten in te stellen.

### <a name="the-intune-app-sdk-will-support-256-bit-encryption-keys----1832174---"></a>De Intune App-SDK ondersteunt 256-bits versleutelingssleutels <!-- 1832174 -->
De Intune App-SDK voor iOS gebruikt 256-bits versleutelingssleutels wanneer versleuteling is ingeschakeld door app-beveiligingsbeleid. De SDK biedt doorgaande ondersteuning voor 128-bits sleutels voor compatibiliteit met inhoud en apps die gebruikmaken van oudere SDK-versies.

### <a name="enabled-shared-pc-settings-in-intune-profile----1907917---"></a>Gedeelde PC-instellingen ingeschakeld in Intune-profiel <!-- 1907917 -->
U kunt momenteel gedeelde PC-instellingen configureren op Windows 10-desktopapparaten met een aangepaste OMA-URI-instelling. Er wordt een nieuw profiel toegevoegd om gedeelde PC-instellingen te configureren (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** > **Gedeeld apparaat met meerdere gebruikers**).
Van toepassing op: Windows 10 en hoger, Windows Holographic for Business

### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359---"></a>Intune-beleid werkt de verificatiemethode en installatie van de Bedrijfsportal-app bij <!-- 1927359 -->
Intune ondersteunt op bepaalde apparaten de Bedrijfsportal-app niet langer wanneer deze is geïnstalleerd van vanuit de App store. Deze wijziging is alleen relevant wanneer u tijdens de inschrijving verifieert met Apple Setup Assistant. Deze wijziging is eveneens alleen van invloed op iOS-apparaten die zijn ingeschreven via:  
* Apple Configurator
* Apple Business Manager
* Apple School Manager
* Apple Device Enrollment Program (DEP)

Als gebruikers de Bedrijfsportal-app installeren uit de App Store en vervolgens apparaten via de app proberen te registreren, treedt er een foutmelding op. Er wordt van uitgegaan dat deze apparaten de Bedrijfsportal alleen gebruiken wanneer het automatisch door Intune tijdens de registratie is gepusht. Inschrijvingsprofielen in Intune in de Azure-portal worden bijgewerkt zodat u kunt opgeven hoe apparaten zich verifiëren en hoe zij de Bedrijfsportal-app ontvangen. Als u wilt dat uw DEP-apparaatgebruikers de Bedrijfsportal hebben, moet u uw voorkeuren in een inschrijvingsprofiel opgeven. Bovendien wordt binnenkort het scherm **Uw apparaat identificeren** in de Bedrijfsportal-app niet meer gebruikt.  
Als u de Bedrijfsportal wilt installeren op DEP-apparaten die al zijn ingeschreven, gaat u naar Intune > Client-apps en pusht u de app als beheerde app met app-configuratiebeleid. Details over hoe u deze stappen uitvoert, worden beschreven in toekomstige documentatie.

### <a name="non-administrators-can-enable-bitlocker-on-windows-10-devices-joined-to-azure-ad---2147379---"></a>Niet-beheerders kunnen BitLocker gebruiken op Windows 10-apparaten die zijn gekoppeld aan Azure AD<!-- 2147379 -->
Wanneer u BitLocker-instellingen op Windows 10-apparaten inschakelt (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** als platform en **Endpoint Protection** als profieltype > **Windows-versleuteling**), voegt u BitLocker-instellingen toe. Deze update bevat een nieuwe BitLocker-instellingen waarmee standaardgebruikers (niet-beheerders) versleuteling kunnen inschakelen. Raadpleeg [Endpoint Protection-instellingen voor Windows 10](endpoint-protection-windows-10.md#windows-encryption) als u de huidige instellingen wilt bekijken.

### <a name="intune-app-pin----2298397---"></a>Pincode voor de Intune-app <!-- 2298397 -->
Als IT-beheerder kunt u het aantal dagen configureren dat een eindgebruiker kan wachten voordat zijn pincode voor de Intune-app moet worden gewijzigd. De nieuwe instellingen is beschikbaar in de Azure-portal via **Intune** > **Client-apps** > **App-beveiligingsbeleid** > **Beleid maken** > **Instellingen** > **Toegangsvereisten**. Deze functie is beschikbaar voor iOS- en Android-apparaten. Deze instelling ondersteunt een positief geheel getal.

### <a name="new-windows-10-update-settings----2626030-2512994---"></a>Nieuwe Windows 10-update-instellingen <!-- 2626030 2512994 -->
Voor uw Windows 10-updateringen kunt u nu:
- de originele automatische update-instellingen herstellen in een Windows 10-machine in machines die met de *update van oktober 2018* worden uitgevoerd
- een nieuwe update-instelling voor software configureren waarmee u kunt toestaan of blokkeren dat gebruikers de installatie van een update pauzeren vanuit de *Instellingen* van hun machines. 



### <a name="ios-email-profiles-can-use-smime-signing-and-encryption----2662949---"></a>iOS-e-mailprofielen kunnen gebruikmaken van S/MIME-ondertekening en versleuteling <!-- 2662949 -->
U kunt een e-mailprofiel maken dat verschillende instellingen bevat. Dit omvat S/MIME-instellingen die kunnen worden gebruikt voor de ondertekening en versleuteling van e-mailcommunicatie op iOS-apparaten (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > kies **iOS** als platform en **E-mail** als profieltype).

In [Configuratie-instellingen voor iOS-e-mail](email-settings-ios.md) worden de huidige instellingen vermeld.

### <a name="skip-more-setup-assistant-screens-on-an-ios-dep-device----2687509---"></a>Meer Setup Assistant-schermen overslaan op een iOS-DEP-apparaat <!-- 2687509 -->
Naast de schermen die u momenteel kunt overslaan, kunt u iOS-DEP-apparaten zo instellen dat de volgende schermen in Setup Assistant worden overgeslagen wanneer een gebruiker een apparaat registreert: Display Tone, Privacy, Android Migration, Home Button, iMessage & FaceTime, Onboarding, Watch Migration, Appearance, Screen Time, Software Update, SIM Setup.
Als u wilt kiezen welke schermen moeten worden overgeslagen, gaat u naar **Apparaatinschrijving** > **Apple-inschrijving** > **Tokens voor inschrijvingsprogramma** > kies een token > **Profielen** > kies een profiel > **Eigenschappen** > **Setup Assistant aanpassen** > kies **Verbergen** voor schermen die u wilt overslaan > **OK**.

### <a name="some-bitlocker-settings-support-windows-10-pro-edition---2727036---"></a>Sommige BitLocker-instellingen ondersteunen Windows 10 Pro <!-- 2727036 -->
U kunt een configuratieprofiel maken dat Endpoint Protection-instellingen op Windows 10-apparaten instelt, waaronder BitLocker. Hiermee wordt voor sommige BitLocker-instellingen ondersteuning toegevoegd voor Windows 10 Professional. Raadpleeg [Endpoint Protection-instellingen voor Windows 10](endpoint-protection-windows-10.md#windows-encryption) als u de huidige Windows 10-instellingen wilt bekijken.
Intune biedt aanvullende velden voor apparaatrapporten, waaronder de Android-fabrikant, het model, de versie van de beveiligingspatch en het iOS-model. In Intune zijn deze velden beschikbaar door **Client-apps** > **App-beveiligingsstatus** te selecteren en **App-beveiligingsrapport: iOS, Android** te selecteren. Bovendien helpen deze parameters u de lijst **Toestaan** te configureren voor de apparaatfabrikant (Android), evenals de lijst **Toestaan** voor het apparaatmodel (Android en iOS) en de versie-instellingen van de minimale Android-beveiligingspatch. 

### <a name="shared-device-configuration-is-renamed-to-lock-screen-message-for-ios-devices-in-the-azure-portal----2809362---"></a>Configuratie voor gedeelde apparaten is hernoemd naar Vergrendelingsschermbericht voor iOS-apparaten in de Azure-portal <!-- 2809362 -->
Wanneer u een configuratieprofiel voor iOS-apparaten maakt, is het mogelijk om de instelling **Configuratie voor gedeelde apparaten** toe te voegen, zodat er specifieke tekst op het vergrendelingsscherm wordt weergegeven. Dit omvat de volgende wijzigingen: 

- De instellingen voor **Configuratie voor gedeelde apparaten** in de Azure-portal worden hernoemd naar 'Vergrendelingsschermbericht (alleen onder supervisie)' (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > kies **iOS** als platform > kies **Apparaatfuncties** als profieltype > **Vergrendelingsschermbericht**).
- Wanneer u vergrendelingsschermberichten toevoegt, kunt u een serienummer, apparaatnaam of een andere apparaatspecifieke waarde als variabele invoegen in **Informatie over de assettag**. U kunt bijvoorbeeld `Device name: {{device name}}` of `Serial number is {{serial number}}` invoeren met accolades. De lijst [iOS-tokens](app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) bevat de beschikbare tokens die kunnen worden gebruikt.

In [Instellingen om berichten op het vergrendelingsscherm weer te geven](shared-device-settings-ios.md) staan de huidige instellingen.

### <a name="more-detailed-enrollment-restriction-failure-messaging----3111564--"></a>Gedetailleerdere berichten over fouten bij inschrijvingsbeperking <!-- 3111564-->
Er komen meer gedetailleerdere foutberichten beschikbaar wanneer er niet wordt voldaan een inschrijvingsbeperkingen. Als u deze berichten wilt bekijken, gaat u naar **Intune** > **Probleemoplossing** en bekijkt u het tabel Inschrijvingsfouten.

### <a name="new-notification-hints-and-keyguard-settings-to-android-enterprise-device-owner-devices----3201839-3201843---"></a>Nieuwe instellingen voor meldingen, hints en keyguard voor Android Enterprise-apparaten in zakelijk eigendom <!-- 3201839 3201843 -->
Deze update omvat verschillende nieuwe functies in Android Enterprise-apparaten wanneer deze worden uitgevoerd in zakelijk eigendom. Als u deze functies wilt gebruiken, gaat u naar **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > als **Platform** kiest u **Android Enterprise** > in **Profieltype** kiest u **Alleen zakelijk eigendom** > **Apparaatbeperkingen**.
Nieuwe functies omvatten: 
- Systeemmeldingen uitschakelen, waaronder binnenkomende oproepen, systeemwaarschuwingen, systeemfouten en meer
- Suggestie om uitleg en hints over te slaan voor apps die voor de eerste keer worden gestart
- Geavanceerde keyguard-instellingen uitschakelen, bijvoorbeeld de camera, meldingen, ontgrendelen met vingerafdruk en meer

Raadpleeg [Instellingen van Android Enterprise-apparaatbeperking](device-restrictions-android-for-work.md) als u de huidige instellingen wilt bekijken.

### <a name="android-enterprise-device-owner-devices-can-use-always-on-vpn-connections----3202194---"></a>Android Enterprise-apparaten in zakelijk eigendom kunnen AlwaysOn-VPN-verbindingen gebruiken <!-- 3202194 -->
In deze update kunt u ingeschakelde VPN-verbindingen gebruiken op Android Enterprise-apparaten in zakelijk eigendom. Altijd ingeschakelde VPN-verbindingen blijven verbonden en maken direct opnieuw verbinding wanneer gebruikers hun apparaat ontgrendelen, het apparaat opnieuw wordt opgestart of het draadloze netwerk wordt gewijzigd. U kunt de verbinding ook in de vergrendelingsmodus zetten. Hiermee wordt al het netwerkverkeer geblokkeerd totdat de VPN-verbinding actief is.
U vindt altijd ingeschakelde VPN in **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** voor platform > **Apparaatbeperkingen** voor apparaten in zakelijk eigendom > **Connectiviteit**. Raadpleeg [Instellingen van Android Enterprise-apparaatbeperking](device-restrictions-android-for-work.md) als u de huidige instellingen wilt bekijken.

### <a name="new-setting-to-end-processes-in-task-manager-on-windows-10-devices----3285177---"></a>Nieuwe instelling om processen in Taakbeheer in Windows 10-apparaten te beëindigen <!-- 3285177 --> 
Deze update omvat een nieuwe instelling om processen via Taakbeheer in Windows 10-apparaten te beëindigen. Met behulp van een apparaatconfiguratieprofiel (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > als **Platform** kiest u **Windows 10** > in **Profieltype** kiest u **Apparaatbeperkingen** > **Algemene** instellingen) kunt u deze instellingen toestaan of blokkeren.
Raadpleeg [Instellingen voor Windows 10-apparaatbeperkingen](device-restrictions-windows-10.md) als u de huidige instellingen wilt bekijken.
Van toepassing op Windows 10 en hoger

### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Beheersjablonen zijn in openbare preview en verplaatst naar hun eigen configuratieprofiel <!-- 3322847 -->
Beheersjablonen in Intune (**Apparaatconfiguratie** > **Beheersjablonen**) zijn momenteel in openbare preview. Bij deze update: beheersjablonen omvatten 300 instellingen die kunnen worden beheerd in Intune. Eerder bestonden deze instellingen alleen in de editor voor groepsbeleid.
Beheersjablonen zijn beschikbaar in openbare preview en worden verplaatst van **Apparaatconfiguratie** > **Beheersjablonen** naar **Apparaatconfiguraatie** > **Profielen** >**Profiel maken** > kies als **Platform** **Windows 10 en later** en kies in **Profieltype** **Beheersjablonen**.
Rapportage is ingeschakeld en van toepassing op: Windows 10 en hoger


<!-- 1810 start -->

### <a name="use-microsoft-recommended-settings-with-security-baselines----2055484---"></a>Door Microsoft aanbevolen instellingen gebruiken met beveiligingsbasislijnen <!-- 2055484 -->
Intune is geïntegreerd met andere services die op beveiliging gericht zijn, inclusief Windows Defender ATP en Office 365 ATP. Klanten vragen om een gemeenschappelijke strategie en een samenhangende set van end-to-end beveiligingsworkflows voor alle Microsoft 365-diensten. Ons doel is om strategieën af te stemmen en oplossingen te ontwikkelen die beveiligingsactiviteiten en gebruikelijke beheerderstaken combineren. In Intune willen we dit doel bereiken door het publiceren van een set beveiligingsbasislijnen die door Microsoft zijn aanbevolen (**Intune** >  **Beveiligingsbasislijnen**).  Beheerders krijgen de mogelijkheid om direct op basis van deze basislijnen een beveiligingsbeleid op te stellen en dit vervolgens voor hun gebruikers te implementeren. Ze kunnen ook de aanbevolen procedures aanpassen aan de behoeften van hun organisatie. Intune zorgt ervoor dat apparaten deze basislijnen blijven naleven, en waarschuwt beheerders wanneer gebruikers of apparaten van de basislijnen afwijken.

### <a name="scope-tags-for-apps---1081941---"></a>Bereiktags voor apps <!--1081941 -->
Binnenkort kunt u bereiktags gebruiken om de toegang tot Intune-resources te beperken. Voeg een bereiktag toe aan een roltoewijzing en voeg de bereiktag vervolgens toe aan een configuratieprofiel. De rol heeft dan alleen toegang tot resources met configuratieprofielen met overeenkomende bereiktags (of zonder bereiktag).
Selecteer voor het maken van een bereiktag **Intune-rollen** > **Bereik (tags)** > **Maken**.
Als u een bereiktag wilt toevoegen aan een roltoewijzing, selecteert u **Intune-rollen** > **Alle rollen** > **Beleid- en profielbeheerder** > **Toewijzingen** > **Bereik (tags)**.
Als u een bereiktag wilt toevoegen aan een configuratieprofiel, selecteert u **Apparaatconfiguratie** > **Profielen** > Een profiel kiezen > **Eigenschappen** > **Bereik (tags)**.

### <a name="tenant-health-dashboard----1124854---"></a>Dashboard voor tenantstatus<!-- 1124854 -->
De pagina Tenantstatus in Intune biedt een uitputtend overzicht van alle informatie over de status van tenants. De pagina is onderverdeeld in vier secties:  
- **Tenantdetails**: bevat uiteenlopende informatie, zoals uw MDM-instantie, het totale aantal ingeschreven apparaten in uw tenant en uw aantal licenties. Deze sectie bevat ook de huidige servicerelease voor uw tenant.
- **Connectorstatus**: bevat informatie voor geconfigureerde connectoren, zoals Apple VPP, Windows Store for Business en certificaatconnectoren. Op basis van hun huidige status worden de connectoren gemarkeerd als *In orde*,  *Waarschuwing* of *Niet in orde*.
- **Intune servicestatus**: bevat actieve incidenten of storingen voor uw tenant. De informatie in deze sectie wordt rechtstreeks opgehaald uit het Office Message Center ([https://portal.office.com](https://portal.office.com)).
- **Intune nieuws**: bevat actieve berichten voor uw tenant, zoals meldingen dat uw tenant de laatste Intune-functies heeft ontvangen. De informatie in deze sectie wordt rechtstreeks opgehaald uit het Office Message Center ([https://portal.office.com](https://portal.office.com)).


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


### <a name="change-in-the-update-process-for-on-premises-connectors----2277554---"></a>Wijziging in het updateproces voor on-premises connectors <!-- 2277554 -->
Op basis van feedback van klanten passen we de manier aan waarop on-premises connectors worden bijgewerkt. Nadat u een on-premises connector hebt geïnstalleerd, worden updates automatisch uitgevoerd. Deze wijziging begint met de nieuwe PFX-certificaatconnector voor Microsoft Intune en wordt vervolgens voor andere soorten on-premises connectors doorgevoerd. 

<!-- 1807 start -->

### <a name="check-for-configuration-manager-compliance----2192052---"></a>Controleren op Configuration Manager-compatibiliteit <!-- 2192052 -->
Een toekomstige update bevat een nieuwe instelling voor System Center Configuration Manager-compatibiliteit (**Apparaatcompatibiliteit** > **Beleid** > **Beleid maken** > **Windows 10**). Configuration Manager verzendt signalen naar Intune-naleving. Met de Intune-instelling kunt u vereisen dat alle Configuration Manager-signalen de waarde 'compatibel' retourneren.

U kunt bijvoorbeeld vereisen dat alle software-updates worden geïnstalleerd op apparaten. Deze vereiste heeft in Configuration Manager de status 'Geïnstalleerd'. Als programma's op het apparaat zich in onbekende staat bevinden, is het apparaat niet-compatibel in Intune.

Van toepassing op Windows 10 en hoger



## <a name="notices"></a>Mededelingen

Er zijn geen actieve meldingen op dit moment.

### <a name="see-also"></a>Zie ook
Zie [Wat is er nieuw in Microsoft Intune?](whats-new.md) voor meer informatie over recente ontwikkelingen.



