---
title: Vroege editie
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 62028232e4d6c9ab20a05480811978234ed0a3c1
ms.sourcegitcommit: 91802e78cd5014d20a828ca25a54a381d452f0f8
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/16/2018
---
# <a name="the-early-edition-for-microsoft-intune---may-2018"></a>De vroege editie voor Microsoft Intune - mei 2018

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

<!-- 1805 start -->

### <a name="support-for-palo-alto-networks-globalprotect-vpn-profiles----1333680-eeready----"></a>Ondersteuning voor Palo Alto Networks GlobalProtect VPN-profielen <!-- 1333680 eeready ! -->

Met deze update kunt u Palo Alto Networks GlobalProtect kiezen als VPN-verbindingstype voor VPN-profielen in Intune (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Profieltype** > **VPN**). In deze versie worden de volgende platformen ondersteund: 

- iOS
- Windows 10

### <a name="set-compliance-by-device-location----851881----"></a>Naleving instellen per apparaatlocatie <!-- 851881 ! -->
In sommige situaties wilt u mogelijk de toegang beperken tot bedrijfsresources op een specifieke locatie, gedefinieerd door een netwerkverbinding. U kunt een nalevingsbeleid maken (**Apparaatnaleving** > **Locaties**) op basis van het IP-adres van het apparaat. Als het apparaat wordt verplaatst naar een locatie buiten het IP-bereik, heeft het apparaat geen toegang meer tot bedrijfsresources.

Is van toepassing op: Android-apparaten 6.0 en hoger, met de bijgewerkte Bedrijfsportal-app

### <a name="improved-troubleshooting-for-app-installation----928990---"></a>Verbeterde probleemoplossing voor app-installatie <!-- 928990 -->
Op apparaten die met Microsoft Intune MDM worden beheerd, mislukken app-installaties wel eens. Als deze apps niet kunnen worden geïnstalleerd, is het soms lastig om de reden van het probleem te achterhalen of om het probleem op te lossen. We brengen een openbare preview-versie uit van de functies voor het oplossen van problemen met apps. U ziet een nieuw knooppunt, **Beheerde apps**, onder elk apparaat. Hier ziet u de apps die via Intune MDM zijn geleverd. In het knooppunt ziet u een lijst met de installatiestatussen van de apps. Als u een bepaalde app selecteert, ziet u de probleemoplossingsweergave voor die app. In de probleemoplossingsweergave ziet u de gehele levenscyclus van de app, zoals wanneer de app is gemaakt, gewijzigd, gebruikt en geleverd aan een apparaat. En als installatie van de app niet is geslaagd, wordt de foutcode weergegeven en een informatief bericht over de oorzaak van de fout. 

### <a name="block-app-access-based-on-unapproved-device-vendors-and-models-----1425689----"></a>App-toegang blokkeren op basis van niet-goedgekeurde apparaatleveranciers en -modellen <!-- 1425689 ! -->
De Intune-IT-beheerder kan via het Intune-app-beveiligingsbeleid een lijst laten opstellen met Android-fabrikanten en/of iOS-modellen. De IT-beheerder kan een met puntkomma's gescheiden lijst van fabrikanten voor Android-beleid en apparaatmodellen voor iOS-beleid verstrekken. Intune-app-beveiligingsbeleid is alleen van toepassing op Android en iOS. Er zijn twee acties die kunnen worden uitgevoerd op basis van deze lijst:
- Het blokkeren van toegang tot een app voor apparaten die niet in de lijst voorkomen.
- Of het selectief wissen van bedrijfsgegevens op apparaten die niet in de lijst voorkomen. 

De gebruiker heeft geen toegang tot de beoogde toepassing als niet is voldaan aan de vereisten van het beleid. Afhankelijk van de instellingen wordt de gebruiker geblokkeerd of worden zakelijke gegevens selectief in de app gewist. Op iOS-apparaten vereist deze functie dat toepassingen (d.w.z. WXP, Outlook, Managed Browser, Yammer) integreren met de Intune APP SDK opdat de minimale versie-instellingen worden afgedwongen voor de doeltoepassingen. Deze integratie vindt doorlopend plaats en is afhankelijk van de specifieke toepassingsteams. Op Android vereist deze functie de meest recente versie van de bedrijfsportal.

Op apparaten van eindgebruikers moet de Intune-client actie ondernemen op basis van een eenvoudige overeenkomst met de tekenreeksen die zijn opgegeven in de Intune-blade Beveiligingsbeleid van toepassing. Dit is volledig afhankelijk van de waarde die het apparaat rapporteert. De IT-beheerder wordt dan ook aangemoedigd ervoor te zorgen dat het bedoelde gedrag correct is. Dit kan worden bereikt door deze instelling te testen voor verschillende fabrikanten en modellen en voor een kleine groep gebruikers. Selecteer in Microsoft Intune **Mobiele apps** > **App-beveiligingsbeleid** om app-beveiligingsbeleidsregels weer te geven en toe te voegen. Zie [Wat is een app-beveiligingsbeleid?](app-protection-policy.md) voor meer informatie over app-beveiligingsbeleid.

### <a name="enable-kiosk-mode-on-windows-10-devices----1560072----"></a>Kioskmodus inschakelen op Windows 10-apparaten <!-- 1560072 ! -->
Op Windows 10-apparaten kunt u een configuratieprofiel maken en de kioskmodus inschakelen (**Apparaatconfiguratie** > **Profielen** > **Profiel maken**  >  **Windows 10** > **Apparaatbeperkingen** > **Kioskmodus**). In deze update is de naam van de instelling **Kiosk (preview)** gewijzigd in **Kiosk (verouderd)**. Het gebruik van **Kiosk (verouderd)** wordt niet meer aanbevolen maar de optie blijft nog werken tot de update van juli. **Kiosk (verouderd)** wordt vervangen door het nieuwe profieltype **Kiosk** (**Profiel maken** > **Windows 10** > **Kiosk (preview)**). Dit profiel bevat de instellingen voor het configureren van kiosken in Windows 10 RS4 en hoger.

Van toepassing op Windows 10 en hoger.

### <a name="retrieve-the-associated-app-user-model-id-aumid-for-microsoft-store-for-business-apps-in-kiosk-mode----1560077----"></a>De bijbehorende app-gebruikersmodel-id (AUMID) ophalen voor de Microsoft Store voor Bedrijven-apps in de kioskmodus <!-- 1560077 ! -->
Intune kan de app-gebruikersmodel-id's (AUMID's) voor Microsoft Store voor Bedrijven-apps (WSfB) ophalen voor een verbeterde configuratie van het kioskprofiel.

Raadpleeg [Apps die u hebt aangeschaft in Microsoft Store voor Bedrijven, beheren met Microsoft Intune](windows-store-for-business.md) voor meer informatie over Microsoft Store voor Business-apps.

### <a name="access-actions-for-app-protection-policies----1483510-eeready---"></a>Acties voor het apps-beveiligingsbeleid weergeven <!-- 1483510 EEready -->
Over enige tijd kunt u het app-beveiligingsbeleid expliciet configureren voor het blokkeren van niet-compatibele apparaten, het wissen van gegevens op deze apparaten of het verzenden van waarschuwingen naar deze apparaten. Met de meest recente actie *Wissen* worden bedrijfsgegevens van een apparaat verwijderd. Als een wisbewerking wordt uitgevoerd, wordt de gebruiker van het apparaat geïnformeerd over de reden en over de stappen om de gegevens te herstellen. Voor sommige instellingen, zoals de minimale versie van het besturingssysteem, moet u meerdere acties toepassen, bijvoorbeeld blokkeren en wissen.

### <a name="new-inventory-information-for-windows-devices----1333569-eeready---"></a>Nieuwe inventarisgegevens voor Windows-apparaten <!-- 1333569 eeready -->

Voor Windows-apparaten zijn per apparaat de volgende inventarisgegevens beschikbaar op het tabblad **Hardware** (**Groepen** > **Alle mobiele apparaten** > **Apparaten** > kies het apparaat van de gebruiker > **eigenschappen weergeven** > **Hardware**):
- TPM
- Antivirus
- Antispyware
- Firewall
- UAC
- Accu
- Domeinnaam.

Zie het artikel [DeviceStatus-CSP](https://docs.microsoft.com/en-us/windows/client-management/mdm/devicestatus-csp) voor meer informatie over hoe deze gegevens worden opgehaald door de CSP.

### <a name="intune-and-the-microsoft-edge-browser----1818969---"></a>Intune en de Microsoft Edge-browser <!-- 1818969 -->
De Microsoft Edge-browser voor mobiele apparaten (iOS en Android) biedt nu ondersteuning voor het app-beveiligingsbeleid van Intune. Gebruikers die zich in de Edge-browsertoepassing aanmelden met hun zakelijk Azure AD-account worden beveiligd door Intune. 

### <a name="new-languageregion-setting-when-configuring-oobe-for-autopilot----1821766---"></a>Nieuwe taal-/landinstelling wanneer u OOBE configureert voor AutoPilot <!-- 1821766 -->
Er is een nieuwe configuratie-instelling waarmee u tijdens de Out of Box Experience de taal en de regio voor AutoPilot-profielen kunt instellen.

### <a name="new-setting-for-configuring-device-keyboard----1821768---"></a>Nieuwe instelling voor het configureren van het apparaattoetsenbord <!-- 1821768 -->
Er is een nieuwe configuratie-instelling waarmee u tijdens de Out of Box Experience het toetsenbord voor AutoPilot-profielen kunt instellen.

### <a name="use-teamviewer-to-screen-share-ios-and-macos-devices----1985547---"></a>TeamViewer gebruiken voor het delen van schermen op iOS- en MacOS-apparaten <!-- 1985547 -->
Op dit moment kunt u TeamViewer gebruiken om op afstand [door Intune beheerde Android- en Windows-apparaten ](device-profile-android-teamviewer.md) te beheren.

Beheerders kunnen verbinding maken met TeamViewer en een sessie voor het delen van schermen starten met iOS- en MacOS-apparaten. iPhone-, iPad- en MacOS-gebruikers kunnen hun schermen live delen met andere pc's of mobiele apparaten. 

### <a name="device-profile-graphical-user-chart-is-back----2160133---"></a>De grafische gebruikersgrafiek van het apparaatprofiel is terug <!-- 2160133 -->
Bij het verbeteren van de aantallen die in de grafische gebruikersgrafiek van het apparaatprofiel (**Apparaatconfiguratie** > **Profielen** > selecteer een bestaand profiel > **Overzicht** ) worden weergegeven, was de grafische gebruikersgrafiek tijdelijk verwijderd.

In deze update is de grafische gebruikersgrafiek terug. Deze wordt weergegeven in de Azure Portal.

### <a name="assign-all-users-and-all-devices-as-scope-groups----2196803---"></a>Alle gebruikers en apparaten toewijzen als bereikgroepen <!-- 2196803 -->
U kunt alle gebruikers, alle apparaten en alle gebruikers en alle apparaten in bereikgroepen toewijzen.

### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>AutoPilot-profielen verplaatst naar de groep met <!-- 1877935 -->
Momenteel kunnen AutoPilot-implementatieprofielen worden toegewezen aan geselecteerde apparaten. Wanneer deze functie beschikbaar is, gaat u als volgt te werk om deze profielen toe te wijzen:
- Maak (Azure AD-)groepen met AutoPilot-apparaten
- Wijs de gewenste profielen toe aan een Azure AD-groep. Het AutoPilot-profiel wordt nu toegewezen aan AutoPilot-apparaten in die groep.

### <a name="management-name-field-will-be-editable----1875989---"></a>Het veld Managementnaam kan worden bewerkt <!-- 1875989 -->
U kunt het veld met de managementnaam bewerken op de blade **Eigenschappen** van een apparaat. Als u dit veld wilt bewerken, kiest u **Apparaten** > **Alle apparaten** > kies het apparaat > **Eigenschappen**. U kunt het veld Managementnaam gebruiken om een apparaat op unieke wijze te identificeren.

<!-- 1804 start -->


### <a name="additions-to-local-device-security-options-settings----1403702---"></a>Toevoegingen aan instellingen voor de beveiligingsopties van lokale apparaten <!-- 1403702 -->
U kunt aanvullende instellingen voor de beveiligingsopties van lokale apparaten voor Windows 10-apparaten configureren. Extra instellingen zijn beschikbaar voor Microsoft Network Client, Microsoft-netwerkserver, toegang tot het netwerk en beveiliging en interactief aanmelden. U vindt deze instellingen in de Endpoint Protection-categorie wanneer u een configuratiebeleid voor Windows 10-apparaten maakt.

### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>Installatie van beleid, apps en certificaat- en netwerkprofielen vereisen <!-- 1553555 -->
Beheerders kunnen de toegang tot het Windows 10 RS4-bureaublad voor eindgebruikers blokkeren totdat beleid, apps en certificaat- en netwerkprofielen worden geïnstalleerd tijdens de inrichting van AutoPilot-apparaten.

### <a name="rules-for-removing-devices----1609459---"></a>Regels voor het verwijderen van apparaten <!-- 1609459 -->
Er zijn nieuwe regels beschikbaar waarmee u automatisch apparaten kunt verwijderen die een aantal dagen niet zijn ingecheckt. U kunt dit aantal instellen. Ga naar het deelvenster **Intune**, selecteer **Apparaten** en selecteer vervolgens **Regels voor het verwijderen van apparaten** om de nieuwe regel te zien.

### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>De installatie van consumenten-apps en -ervaringen op Windows 10 Enterprise RS4 Autopilot-apparaten voorkomen<!-- 1621980 -->
U kunt voorkomen dat consumenten-apps en -ervaringen op uw apparaten met Windows 10 Enterprise RS4 AutoPilot kunnen worden geïnstalleerd. Ga voor deze functie naar **Intune** > **Apparaatinschrijving** > **Windows-inschrijving** > **Windows AutoPilot-profielen** > **Nieuwe maken** > **Inschrijvingsinstellingen**. 

<!-- 1803 start -->

#### <a name="multiple-exchange-connector-support----2070451---"></a>Ondersteuning voor meerdere Exchange Connectors <!-- 2070451 -->

U bent niet langer beperkt tot één Microsoft Intune Exchange Connector per tenant. Intune ondersteunt meerdere Exchange Connectors, zodat u voorwaardelijke toegang van Intune kunt instellen met meerdere on-premises Exchange-organisaties.

Met een on-premises Exchange Connector voor Intune kunt u apparaattoegang tot uw on-premises Exchange-postvakken beheren op basis van of een apparaat is ingeschreven bij Intune en voldoet aan het Intune-nalevingsbeleid voor apparaten. Als u een connector wilt instellen, downloadt u de on-premises Exchange Connector voor Intune vanaf Azure Portal en installeert u deze op een server in uw Exchange-organisatie. Kies op het Microsoft Intune-dashboard **On-premises toegang** en kies vervolgens onder **Installatie** de optie **Exchange ActiveSync-connector**. Download de on-premises Exchange Connector en installeer deze op een server in uw Exchange-organisatie. Nu u niet meer beperkt bent tot één Exchange Connector per tenant, kunt u, als u extra Exchange-organisaties hebt, dit zelfde proces volgen om een connector te downloaden en installeren voor elke extra Exchange-organisatie.

### <a name="support-coming-for-new-cisco-anyconnect-client-for-ios----1333708---"></a>Ondersteuning voor nieuwe Cisco AnyConnect-client voor iOS is binnenkort beschikbaar<!-- 1333708 -->

Nieuwe VPN-profielen gemaakt voor Cisco AnyConnect voor iOS werken met Cisco AnyConnect 4.0.7x en hoger. Bestaande iOS Cisco AnyConnect VPN-profielen krijgen het label **Cisco Legacy AnyConnect** en blijven op dezelfde manier werken met Cisco AnyConnect 4.0.5x .

> [!NOTE]
> Deze wijziging is alleen voor iOS; er blijft slechts één Cisco AnyConnect-optie voor Android, Android for Work en macOS.

#### <a name="more-information"></a>Meer informatie

U moet een nieuw iOS Cisco AnyConnect VPN-profiel maken voor de ondersteuning van de nieuwe app, omdat de nieuwe Cisco AnyConnect-app en de Cisco Legacy AnyConnect-app verschillende apps zijn. Als u de AnyConnect-client in uw omgeving beheert, moet u ook de nieuwe Cisco AnyConnect-app implementeren. Als u een upgrade wilt voltooien, moet u ook uw Cisco Legacy AnyConnect VPN-profiel wissen en de Cisco Legacy AnyConnect-app verwijderen.

NAC-integratie (Network Access Control) werkt in de eerste release niet voor de nieuwe AnyConnect-client. We werken samen met Cisco om NAC-integratie te bieden in een toekomstige versie van Intune.

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Mogelijkheid om vereiste line-of-business-apps (LOB) te implementeren voor alle gebruikers op apparaten met Windows 10 Desktop <!-- 1627835 RS4 -->
Klanten kunnen vereiste Windows 10 line-of-business-apps implementeren om in apparaatcontexten te installeren. Hierdoor worden deze apps beschikbaar voor alle gebruikers op het apparaat. Dit is alleen van toepassing op Windows 10 Desktop-apparaten.

### <a name="company-portal-enrollment-improved----1874230--"></a>Inschrijving bedrijfsportal verbeterd <!-- 1874230-->
Gebruikers die een apparaat inschrijven via de bedrijfsportal op Windows 10 build 1703 en hoger, kunnen de eerste stap van de inschrijving voltooien zonder de app te verlaten.

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>De Help- en Feedback-ervaring op de bedrijfsportal-app voor Android bijwerken <!--1631531 -->

We updaten de Help- en Feedback-ervaring op de bedrijfsportal-app voor Android zodat deze overeenkomt met de aanbevolen procedures voor Android-apps. We werken de bedrijfsportal-app voor Android in de komende maanden bij om het menu-item **Help en Feedback** op te delen in afzonderlijke menu-items, namelijk **Help** en **Feedback verzenden**. Op de **Help**-pagina komt een sectie **Veelgestelde vragen** sectie en een knop **E-mailondersteuning** waarmee eindgebruikers logboeken naar Microsoft kunnen uploaden en e-mail kunnen verzenden naar bedrijfsondersteuning om het probleem te beschrijven. **Feedback verzenden** leidt de gebruiker door een standaard Microsoft-feedbackformulier, waarin de gebruiker wordt gevraagd een keuze te maken uit: "Ik vindt iets leuk", "Ik vind iets niet leuk" of "Ik heb een idee."

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Beleid voor app-beveiliging <!-- 679615 -->
Via het beveiligingsbeleid voor Intune-apps kunt u algemene standaardbeleidsregels maken om snel beveiliging in te schakelen voor alle gebruikers in de gehele tenant.

<!-- the following are present prior to 1711 -->

## <a name="notices"></a>Mededelingen

Er zijn geen actieve meldingen op dit moment.

### <a name="see-also"></a>Zie ook
Zie [Wat is er nieuw in Microsoft Intune?](whats-new.md) voor meer informatie over recente ontwikkelingen.
