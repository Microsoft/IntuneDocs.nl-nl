---
title: Overzicht van App-beveiligingsbeleid
titleSuffix: Microsoft Intune
description: Ontdek hoe u met het beveiligingsbeleid voor apps van Microsoft Intune uw bedrijfsgegevens kunt beveiligen en hoe u kunt voorkomen dat gegevens verloren gaan.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/06/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1c086943-84a0-4d99-8295-490a2bc5be4b
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, get-started, seoapril2019
ms.collection: M365-identity-device-management
ms.openlocfilehash: d2d8d50f7ac5d79d4d0081e7eee2169e9ff45d49
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77512072"
---
# <a name="app-protection-policies-overview"></a>Overzicht van App-beveiligingsbeleid

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Beleidsregels voor de beveiliging van apps (APP's) zijn regels die ervoor zorgen dat de bedrijfsgegevens die zijn opgenomen in een app, veilig of binnen de app blijven. Een beleidsregel kan een regel zijn die wordt afgedwongen wanneer de gebruiker bedrijfsgegevens probeert te openen of te verplaatsen, of een reeks acties die zijn verboden of worden gecontroleerd wanneer de gebruiker zich in de app bevindt. Een beheerde app is een app waarop app-beveiligingsbeleid is toegepast en die door Intune kan worden beheerd.

Met het beveiligingsbeleid voor MAM-apps (Mobile Application Management) kunt u de gegevens van uw organisatie beheren en beveiligen in een toepassing. Met **MAM zonder registratie** (MAM-WE) kunt u op bijna elk [apparaat](app-management.md#app-management-capabilities-by-platform), inclusief persoonlijke apparaten in BYOD-scenario's (**Bring-Your-Own-Device**), een werk- of schoolgerelateerde app beheren die gevoelige gegevens bevat. Veel productiviteits-apps, zoals Microsoft Office-apps, kunnen worden beheerd met Intune MAM. Bekijk de officiële lijst met de [door Microsoft Intune beveiligde apps](apps-supported-intune-apps.md) die beschikbaar zijn voor openbaar gebruik.

## <a name="how-you-can-protect-app-data"></a>Hoe u app-gegevens kunt beveiligen
Uw werknemers gebruiken mobiele apparaten voor zowel privé- als werktaken. U wilt er niet alleen voor zorgen dat uw werknemers productief kunnen zijn, maar u wilt bedoeld of onbedoeld gegevensverlies voorkomen. U wilt ook bedrijfsgegevens beveiligen die worden geopend op apparaten die niet door u worden beheerd.

U kunt app-beveiligingsbeleid voor Intune gebruiken **onafhankelijk van een MDM-oplossing (Mobile Device Management)** . Deze onafhankelijkheid helpt u om de gegevens van uw bedrijf te beveiligen, met of zonder dat apparaten zijn ingeschreven bij een oplossing voor apparaatbeheer. Door **beleid op app-niveau** te implementeren, kunt u de toegang tot bedrijfsbronnen beperken en gegevens binnen de controlesfeer van uw IT-afdeling houden.

### <a name="app-protection-policies-on-devices"></a>App-beveiligingsbeleid op apparaten

Beveiligingsbeleid voor apps kan worden geconfigureerd voor apps die worden uitgevoerd op apparaten die:

- **Geregistreerd met Microsoft Intune:** deze apparaten zijn doorgaans in het bezit van het bedrijf.

- **Apparaten die zijn geregistreerd in een oplossing voor mobiel apparaatbeheer van derden:** deze apparaten zijn doorgaans in het bezit van het bedrijf.

  > [!NOTE]
  > MAM-beleid mag niet worden gebruikt met MAM-oplossingen van derden of beveiligde containers.

- **Apparaten die niet zijn geregistreerd in een MDM-oplossing:** Bij deze apparaten gaat het meestal om apparaten die in het bezit zijn van werknemers, of om apparaten die niet worden beheerd door of zijn ingeschreven bij Intune of een andere MDM-oplossing.

> [!IMPORTANT]
> U kunt MAM-beleid maken voor mobiele Office-apps die verbinding maken met Office 365-services. U kunt de toegang tot Exchange on-premises mailboxen tevens beveiligen door beveiligingsbeleid voor Intune-apps te maken voor Outlook voor iOS/iPadOS en Android met hybride moderne verificatie. Voordat u deze functie gebruikt, moet u ervoor zorgen dat u voldoet aan de [Outlook voor iOS-/iPadOS- en Android-vereisten](https://technet.microsoft.com/library/mt846639(v=exchg.160).aspx). Beveiligingsbeleid voor apps wordt niet ondersteund voor andere apps die verbinding maken met on-premises Exchange- of SharePoint-services.

## <a name="benefits-of-using-app-protection-policies"></a>Voordelen van het gebruik van het beveiligingsbeleid voor apps

Dit zijn de belangrijke voordelen van het gebruik van het beveiligingsbeleid voor apps:

- **Uw bedrijfsgegevens worden beschermd op het niveau van de app.** Omdat voor Mobile Application Management geen apparaatbeheer is vereist, kunt u bedrijfsgegevens beveiligen op zowel beheerde als niet-beheerde apparaten. Het beheer wordt gecentreerd rond de identiteit van de gebruiker, waardoor er geen apparaatbeheer is vereist.

- **De productiviteit van eindgebruikers wordt niet beïnvloed en beleid is niet van toepassing wanneer de app wordt gebruikt in een persoonlijke context.** Het beleid wordt alleen in een werkcontext toegepast, waardoor u de mogelijkheid hebt om bedrijfsgegevens te beschermen zonder aan persoonlijke gegevens te komen.

- **Het beveiligingsbeleid voor apps zorgt ervoor dat de app-laag goed wordt beveiligd.** U kunt bijvoorbeeld:
  - Een pincode vereisen om een app te openen in een werkcontext 
  - Het delen van gegevens tussen apps beheren 
  - Het opslaan van bedrijfsgegevens uit apps op persoonlijke opslaglocaties voorkomen

- **Naast MAM, zorgt MDM ervoor dat het apparaat wordt beveiligd.** U kunt bijvoorbeeld een pincode vereisen voor toegang tot het apparaat, of u kunt beheerde apps op het apparaat implementeren. U kunt ook apps implementeren op apparaten via uw MDM-oplossing, zodat u meer controle over het beheer van apps hebt.

Het gebruik van MDM met het beveiligingsbeleid voor apps biedt extra voordelen en bedrijven kunnen het beveiligingsbeleid voor apps met en zonder MDM gelijktijdig gebruiken. Stel, een werknemer gebruikt bijvoorbeeld zowel een telefoon die is verleend door het bedrijf, als een privétablet. De bedrijfstelefoon is ingeschreven bij MDM en beveiligd op basis van het beveiligingsbeleid voor apps, terwijl het privéapparaat alleen wordt beveiligd met beveiligingsbeleid voor apps.

Als u een MAM-beleid toepast op de gebruiker zonder de apparaatstatus in te stellen, krijgt de gebruiker het MAM-beleid op zowel het BYOD-apparaat als het door Intune beheerde apparaat. U kunt een MAM-beleid ook toepassen op basis van de beheerde status. Bij het maken van een beleid voor de beveiliging van apps selecteert u dan **Nee** voor **Doel voor alle app-typen**. Ga vervolgens op een van de volgende manieren te werk:
- Pas een minder streng MAM-beleid toe op apparaten die met Intune worden beheerd en een meer beperkend MAM-beleid op apparaten die niet bij MDM zijn ingeschreven.
- Pas alleen een MAM-beleid toe op niet-ingeschreven apparaten.

## <a name="supported-platforms-for-app-protection-policies"></a>Ondersteunde platformen voor het beveiligingsbeleid voor apps

Intune biedt een scala aan mogelijkheden om u te helpen de benodigde apps op de apparaten te krijgen waarop u deze wilt uitvoeren. Zie [App-beheermogelijkheden per platform](app-management.md#app-management-capabilities-by-platform) voor meer informatie.

De platformondersteuning voor beveiligingsbeleid voor apps in Intune is afgestemd op platformondersteuning voor mobiele Office-toepassingen voor Android- en iOS-/iPadOS-apparaten. Zie de sectie **Mobiele apps** van [Systeemvereisten voor Office](https://products.office.com/office-system-requirements#coreui-contentrichblock-9r05pwg) voor de details.

> [!IMPORTANT]
> De Intune-bedrijfsportal-app is vereist op het apparaat om appbeveiligingsbeleid op Android te ontvangen. Raadpleeg de [Appvereisten voor Intune-bedrijfsportaltoegang](../fundamentals/end-user-mam-apps-android.md#access-apps) voor meer informatie.

## <a name="how-app-protection-policies-protect-app-data"></a>Hoe het beveiligingsbeleid voor apps app-gegevens beveiligen

### <a name="apps-without-app-protection-policies"></a>Apps zonder het beveiligingsbeleid voor apps

Bedrijfsgegevens en persoonlijke gegevens kunnen met elkaar worden vermengd als er apps zonder beperkingen worden gebruikt. Bedrijfsgegevens kunnen terechtkomen op locaties zoals persoonlijke opslag of kunnen worden overgebracht naar apps die buiten uw controlesfeer liggen, wat leidt tot gegevensverlies. De pijlen in het volgende diagram geven onbeperkte verplaatsingen weer van gegevens tussen apps (zowel zakelijke als persoonlijke apps) en naar opslaglocaties.

![Conceptafbeelding voor gegevensverplaatsing tussen apps waarvoor geen beleid is ingesteld](./media/app-protection-policy/apps-without-protection-policies.png)

### <a name="data-protection-with-app-protection-policies-app"></a>Gegevensbeveiliging met het beveiligingsbeleid voor apps (APP)

U kunt het beveiligingsbeleid voor apps gebruiken om te voorkomen dat bedrijfsgegevens worden opgeslagen op de lokale opslag van het apparaat (zie de onderstaande afbeelding). U kunt ook gegevensverplaatsing beperken naar andere apps die niet zijn beveiligd met beveiligingsbeleid voor apps. Beveiligingsbeleidsinstellingen voor apps bevatten:
- Beleid voor gegevensverplaatsing, zoals **Kopieën van organisatiegegevens opslaan** en **Knippen, kopiëren en plakken beperken**.
- Instellingen voor toegangsbeleid zoals **Eenvoudige pincode vereisen voor toegang** en **Beheerde apps blokkeren op gekraakte of geroote apparaten**.

![Conceptafbeelding met bedrijfsgegevens die door beleid worden beschermd](./media/app-protection-policy/apps-with-protection-policies.png)

### <a name="data-protection-with-app-on-devices-managed-by-an-mdm-solution"></a>Gegevensbeveiliging met APP op apparaten die worden beheerd door een MDM-oplossing

De volgende afbeelding toont de beveiligingslagen die worden geboden door een combinatie van MDM en beveiligingsbeleid voor apps.

![Afbeelding die laat zien hoe het beveiligingsbeleid voor apps werkt op BYOD-apparaten](./media/app-protection-policy/app-protection-policies-with-mdm.png)

De MDM-oplossing biedt de volgende toegevoegde waarde:

- Schrijft het apparaat in
- Implementeert de apps op het apparaat
- Zorgt voor continue apparaatcompatibiliteit en -beheer

Het beveiligingsbeleid voor apps biedt de volgende toegevoegde waarde:

- Het helpt uw bedrijfsgegevens te beveiligen tegen het lekken van gegevens naar consumenten-apps en -services
- Het past beperkingen, zoals *opslaan als*, *klembord* of *pincode* toe op client-apps
- Het wist zo nodig bedrijfsgegevens van apps zonder die apps van het apparaat te verwijderen

### <a name="data-protection-with-app-for-devices-without-enrollment"></a>Het biedt gegevensbeveiliging met APP voor apparaten die niet zijn ingeschreven

Het volgende diagram laat zien hoe het beleid voor gegevensbeveiliging op app-niveau werkt zonder MDM.

![Afbeelding die laat zien hoe het beveiligingsbeleid voor apps werkt op apparaten zonder inschrijving (niet-beheerde apparaten)](./media/app-protection-policy/app-protection-policies-without-mdm.png)

Voor BYOD-apparaten die niet zijn ingeschreven in een MDM-oplossing, kan het beveiligingsbeleid voor apps helpen bij het beschermen van bedrijfsgegevens op app-niveau.
Er zijn echter enkele beperkingen waar u rekening mee moet houden, zoals:

- U kunt geen apps implementeren op het apparaat. De eindgebruiker moet de apps downloaden uit de Store.
- U kunt geen certificaatprofielen op deze apparaten inrichten.
- U kunt geen Wi-Fi- en VPN-instellingen van het bedrijf op deze apparaten inrichten.

## <a name="apps-you-can-manage-with-app-protection-policies"></a>Apps die u kunt beheren met beleidsregels voor de beveiliging van apps

Alle apps die zijn geïntegreerd met de [Intune-SDK](../developer/app-sdk.md) of die zijn ingepakt met de [Intune App Wrapping Tool](../developer/apps-prepare-mobile-application-management.md), kunnen worden beheerd met Intune-beleidsregels voor de beveiliging van apps. Zie de officiële lijst met [door Microsoft Intune beveiligde apps](apps-supported-intune-apps.md) die zijn gemaakt met deze hulpprogramma's en die beschikbaar zijn voor openbaar gebruik.

Het Intune SDK-ontwikkelingsteam houdt zich actief bezig met het testen en onderhouden van ondersteuning voor apps die zijn gebouwd met de systeemeigen Android-, iOS-/iPadOS- (Objective-C, Swift), Xamarin-, Xamarin.Forms- en Cordova-platforms. Hoewel het sommige klanten is gelukt om de Intune SDK te integreren in andere platforms, zoals React Native en NativeScript, bieden we geen specifieke instructies of plug-ins voor app-ontwikkelaars die andere platforms gebruiken dan de platforms die door ons worden ondersteund.

De [Intune-SDK](../developer/app-sdk.md) maakt gebruik van een aantal geavanceerde moderne verificatiefuncties van [Azure Active Directory Authentication Library](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) (ADAL) voor zowel de eigen als de externe versies van de SDK. Hierdoor werkt [Microsoft Authentication Library](https://docs.microsoft.com/azure/active-directory/develop/reference-v2-libraries) (MSAL) niet goed met de meeste belangrijkste scenario's, zoals verificatie in de Intune-app-beveiligingsservice en voorwaardelijk starten. Gezien het feit dat het Identity-team van Microsoft gebruikers over het algemeen aanraadt om voor alle Microsoft Office-apps over te stappen naar MSAL, zal de [Intune-SDK](../developer/app-sdk.md) daar uiteindelijk ondersteuning voor moeten gaan bieden, maar hier zijn momenteel nog geen plannen voor.

## <a name="end-user-requirements-to-use-app-protection-policies"></a>Vereisten voor eindgebruikers voor het gebruik van beveiligingsbeleid voor apps

De volgende lijst bevat de vereisten voor eindgebruikers voor het gebruik van app-beveiligingsbeleidsregels voor een app die door Intune wordt beheerd:

- De eindgebruiker moet een AAD-account (Azure Active Directory) hebben. Zie [Gebruikers toevoegen en beheerdersmachtigingen aan Intune toekennen](../fundamentals/users-add.md) voor informatie over het maken van Intune-gebruikers in Azure Active Directory.

- Er moet een licentie voor Microsoft Intune Azure aan het Azure Active Directory-account van de eindgebruiker zijn toegewezen. Zie [Intune-licenties beheren](../fundamentals/licenses-assign.md) voor informatie over het toewijzen van Intune-licenties aan eindgebruikers.

- De eindgebruiker moet behoren tot een beveiligingsgroep waarop een beleidsregel voor de beveiliging van apps is gericht. Dezelfde beleidsregel voor de beveiliging van apps moet ook zijn gericht op de specifieke app die wordt gebruikt. Beleidsregels voor de beveiliging van apps kunnen worden gemaakt en geïmplementeerd in de Intune-console in [Azure Portal](https://portal.azure.com). Beveiligingsgroepen kunnen op dit moment worden gemaakt in het [Microsoft 365-beheercentrum](https://admin.microsoft.com).

- De eindgebruiker moet zich bij de app aanmelden met zijn AAD-account.

## <a name="app-protection-policies-for-microsoft-office-apps"></a>App-beveiligingsbeleid voor Microsoft Office-apps

Er zijn enkele aanvullende vereisten waarmee u rekening moet houden bij het gebruik van app-beveiligingsbeleid voor Microsoft Office-apps.

### <a name="outlook-mobile-app"></a>Mobiele Outlook-app
Dit zijn de aanvullende vereisten voor het gebruik van de [mobiele Outlook-app](https://products.office.com/outlook):

- De eindgebruiker moet de mobiele app van Outlook op zijn apparaat hebben geïnstalleerd.
- De eindgebruiker moet een [Office 365 Exchange Online](https://products.office.com/exchange/exchange-online)-postvak en -licentie aan het Azure Active Directory-account hebben gekoppeld.

  >[!NOTE]
  > De mobiele app van Outlook ondersteunt momenteel alleen Intune-app-beveiliging voor Microsoft Exchange Online en [Exchange Server met hybride moderne verificatie](https://technet.microsoft.com/library/mt846639(v=exchg.160).aspx) en biedt geen ondersteuning voor Exchange in Office 365 Dedicated.

### <a name="word-excel-and-powerpoint"></a>Word, Excel en PowerPoint
Dit zijn de aanvullende vereisten voor het gebruik van de apps [Word, Excel en PowerPoint](https://products.office.com/business/office):

- De eindgebruiker moet een licentie voor [Office 365 Business of Enterprise](https://products.office.com/business/compare-more-office-365-for-business-plans) aan zijn Azure Active Directory-account hebben gekoppeld. Het abonnement moet de Office-apps voor mobiele apparaten bevatten en kan een cloudopslagaccount met [OneDrive voor Bedrijven](https://onedrive.live.com/about/business/) bevatten. Office 365-licenties kunnen aan de hand van de volgende [instructies](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc) worden toegewezen in het [Microsoft 365-beheercentrum](https://admin.microsoft.com).

- De eindgebruiker moet een beheerde locatie hebben die is geconfigureerd met de gedetailleerde functie voor 'opslaan als', onder de instelling 'Kopieën van organisatiegegevens opslaan' van het beveiligingsbeleid voor toepassingen. Als bijvoorbeeld OneDrive de beheerde locatie is, moet de [OneDrive](https://onedrive.live.com/about/)-app worden geconfigureerd in de Word-, Excel- of PowerPoint-app van de eindgebruiker.

- Als OneDrive de beheerde locatie is, moet de app het doel zijn van het app-beveiligingsbeleid dat voor de eindgebruiker is geïmplementeerd.

  >[!NOTE]
  > De mobiele Office-apps bieden momenteel alleen ondersteuning voor SharePoint Online en niet voor SharePoint On-Premises.

### <a name="managed-location-needed-for-office"></a>Benodigde beheerde locatie voor Office
Voor Office is een beheerde locatie (bijvoorbeeld OneDrive) nodig. Intune markeert alle gegevens in de app als 'zakelijk' of 'persoonlijk'. Gegevens worden als 'zakelijk' beschouwd wanneer ze afkomstig zijn van een bedrijfslocatie. Voor Office-apps worden de volgende locaties door Intune beschouwd als bedrijfslocaties: e-mail (Exchange) of cloudopslag (OneDrive-app met een OneDrive voor Bedrijven-account).

### <a name="skype-for-business"></a>Skype voor bedrijven
Er zijn de aanvullende vereisten voor het gebruik van Skype voor Bedrijven. Zie de licentievereisten voor [Skype voor Bedrijven](https://products.office.com/skype-for-business/it-pros). Zie respectievelijk [Hybride moderne verificatie voor SfB en Exchange wordt algemeen beschikbaar (GA)](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Hybrid-Modern-Auth-for-SfB-and-Exchange-goes-GA/ba-p/134756) en [Moderne verificatie voor on-premises SfB met AAD](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Modern-Auth-for-SfB-OnPrem-with-AAD/ba-p/180910) voor hybride en on-premises configuraties van Skype voor Bedrijven (SfB).

## <a name="app-protection-global-policy"></a>Algemeen appbeveiligingsbeleid

Als een OneDrive-beheerder naar **admin.onedrive.com** bladert en toegang tot het **Apparaat** selecteert, kan deze beheerder de besturingselementen voor **Mobile Application Management** instellen voor de OneDrive- en SharePoint-client-apps. 

Via de instellingen, die beschikbaar zijn gesteld op de OneDrive-beheerdersconsole, wordt het speciale app-beschermingsbeleid **Algemeen** van Intune geconfigureerd. Dit algemene beleid is van toepassing op alle gebruikers in uw tenant en biedt geen enkele manier om te bepalen waarvoor het beleid wordt gericht. 

Zodra het beleid is ingeschakeld, worden de OneDrive- en SharePoint-apps voor iOS/iPadOS en Android standaard beveiligd met de geselecteerde instellingen. Een IT-professional kan dit beleid in de Intune-console bewerken om meer doelgerichte apps toe te voegen en beleidsinstellingen aan te passen. 

Standaard kan er maar één **algemeen** beleid per tenant zijn. U kunt de [Intune Graph-API’s](../developer/intune-graph-apis.md) echter gebruiken om extra algemene beleidsregels per tenant te maken, maar dit wordt niet aanbevolen. Het maken van extra algemene beleidsregels wordt afgeraden omdat het oplossen van problemen met de implementatie van dergelijk beleid erg ingewikkeld kan zijn.

Hoewel het **algemene** beleid van toepassing is op alle gebruikers in uw tenant, worden deze instellingen door eventueel Intune-standaardbeleid voor de beveiliging van apps overschreven.

## <a name="app-protection-features"></a>Functies voor app-beveiliging

### <a name="multi-identity"></a>Meerdere identiteiten

Met ondersteuning voor meerdere identiteiten kan een app meerdere doelgroepen ondersteunen. Deze doelgroepen zijn zowel zakelijke gebruikers als persoonlijke gebruikers. Werk- en schoolaccounts worden gebruikt door zakelijke doelgroepen, terwijl persoonlijke accounts worden gebruikt voor consumentendoelgroepen, zoals Microsoft Office-gebruikers. Een app met ondersteuning voor meerdere identiteiten kan openbaar worden vrijgegeven, waarbij het app-beveiligingsbeleid alleen van toepassing is als de app wordt gebruikt in de werk- en schoolcontext (zakelijk). Via ondersteuning voor meerdere identiteiten kan de [Intune-SDK](../developer/app-sdk.md) beleidsregels voor de beveiliging van apps toepassen op alleen het werk- of schoolaccount dat is aangemeld bij de app. Als een persoonlijk account is aangemeld bij de app, blijven de gegevens ongewijzigd.

Een voorbeeld van een persoonlijke context is een gebruiker die een nieuw document start in Word. Omdat dit als persoonlijke context wordt beschouwd, wordt er geen beveiligingsbeleid voor apps van Intune toegepast. Zodra het document is opgeslagen in het zakelijke OneDrive-account, wordt het beschouwd als zakelijke context en wordt er Intune-app-beveiligingsbeleid op toegepast.

Een voorbeeld van een werk- of zakelijke context is een gebruiker die de OneDrive-app start met behulp van een werkaccount. In de werkcontext kan deze gebruiker bestanden niet verplaatsen naar een persoonlijke opslaglocatie. Later, wanneer OneDrive wordt gebruikt voor een persoonlijk account, kunnen de gegevens op de persoonlijke OneDrive-locatie zonder beperkingen worden gekopieerd en verplaatst.

Outlook heeft een gecombineerde weergave van e-mail met persoonlijke en zakelijke e-mail. In dit geval vraagt de Outlook-app om de Intune-pincode bij het starten van de app.

Zie [MAM en meerdere identiteiten](apps-supported-intune-apps.md) voor meer informatie over meerdere identiteiten in Intune.

### <a name="intune-app-pin"></a>Pincode voor de Intune-app

De pincode is een wachtwoordcode die wordt gebruikt om te verifiëren of de juiste gebruiker de bedrijfsgegevens in een app benadert.

**Pincodeprompt**<br>
Intune vraagt naar de pincode van de gebruiker wanneer de gebruiker 'zakelijke' gegevens benadert. In apps met functionaliteit voor meerdere identiteiten, zoals Word, Excel of PowerPoint, wordt gebruikers om hun pincode gevraagd wanneer ze een 'zakelijk' document of bestand willen openen. In apps waarvoor maar één identiteit kan worden gebruikt, zoals Line-Of-Business-apps die worden beheerd met de [Intune App Wrapping Tool](../developer/apps-prepare-mobile-application-management.md)-functionaliteit, wordt gelijk bij het starten van de app om de pincode gevraagd, omdat de [Intune-SDK](../developer/app-sdk.md) weet dat de gebruiker de app uitsluitend 'zakelijk' gebruikt.

**Pincodeprompt of zakelijke referentieprompt, frequentie**<br>
De IT-beheerder kan de beleidsinstelling voor beveiliging van de Intune-app in de Intune-beheerconsole instellen op **Toegangsvereisten opnieuw controleren na (minuten)** . Deze instelling geeft de hoeveelheid tijd aan voordat de toegangsvereisten op het apparaat worden gecontroleerd en het scherm voor de pincode of zakelijke referentieprompt opnieuw wordt weergegeven. Belangrijke informatie over de pincode die van invloed is op hoe vaak de gebruiker om de pincode wordt gevraagd, is:

- **De pincode wordt gedeeld door apps van dezelfde uitgever om de bruikbaarheid te verbeteren:**<br> Op iOS/iPadOS wordt één pincode voor apps gedeeld door alle apps **van dezelfde app-uitgever**. Zo delen alle Microsoft-apps dezelfde pincode. Op Android wordt één pincode voor apps gedeeld met alle andere apps.
- **Het gedrag van *Toegangsvereisten opnieuw controleren na (minuten)* na het opnieuw opstarten van een apparaat:**<br> een timer houdt het aantal minuten van inactiviteit bij waarna de pincode voor de Intune-app of de zakelijke referentieprompt opnieuw moet worden weergegeven. In iOS/iPadOS wordt de timer niet beïnvloed door het opnieuw starten van het apparaat. Het opnieuw starten van het apparaat is dus niet van invloed op het aantal minuten dat de gebruiker niet actief is in een iOS-/iPadOS-app waarop het beleid voor de Intune-pincode (of zakelijke referenties) is gericht. In Android wordt de timer opnieuw ingesteld bij het opnieuw starten van het apparaat. Hierdoor vragen Android-apps waarvoor het beleid voor Intune-pincodes (of zakelijke referenties) is ingesteld waarschijnlijk om de pincode voor de app, ongeacht de instelling 'Toegangsvereisten opnieuw controleren na (minuten)' **na het opnieuw starten van een apparaat**.  
- **De werking van de timer die aan de pincode is gekoppeld:**<br> zodra een pincode wordt ingevoerd voor toegang tot een app (app A) en de app de voorgrond (primaire invoerfocus) op het apparaat verlaat, wordt de timer opnieuw ingesteld. Voor elke app (app B) die deze pincode deelt, wordt de gebruiker niet om de pincode gevraagd, omdat de timer opnieuw is ingesteld. De prompt verschijnt zodra opnieuw aan de waarde voor Toegangsvereisten opnieuw controleren na (minuten) is voldaan.

Zelfs als de pincode wordt gedeeld met apps van andere uitgevers verschijnt bij iOS-/iPadOS-apparaten de prompt opnieuw wanneer opnieuw is voldaan aan de waarde **Toegangsvereisten na (minuten) opnieuw controleren** voor de app die niet de belangrijkste invoerfocus is. Een gebruiker heeft bijvoorbeeld app _A_ van uitgever _X_ en app _B_ van uitgever _Y_ en deze twee apps delen dezelfde pincode. De gebruiker is gericht op app _A_ (voorgrond) en app _B_ wordt geminimaliseerd. Nadat is voldaan aan de waarde **Toegangsvereisten na (minuten) opnieuw controleren** en de gebruiker overschakelt naar de app _B_, is de pincode vereist.

  >[!NOTE]
  > Als u wilt dat de toegangsvereisten van de gebruiker vaker worden gecontroleerd (oftewel dat er om een pincode wordt gevraagd), met name voor een veelgebruikte app, wordt aanbevolen om de waarde voor de instelling 'Toegangsvereisten opnieuw controleren na (minuten)' te verlagen.

**Ingebouwde app-pincodes voor Outlook en OneDrive**<br>
De pincode van Intune werkt op basis van een timer van inactiviteit (de waarde voor **Toegangsvereisten opnieuw controleren na (minuten)** ). Er wordt dus gevraagd om de pincode van Intune. Dit is onafhankelijk van de prompts voor de pincode van de app voor Outlook en OneDrive, die vaak standaard verschijnen bij het starten van de app. Als beide prompts tegelijk worden weergegeven, moet de pincode van Intune voorrang krijgen.

**Intune-pincodebeveiliging**<br>
De pincode zorgt ervoor dat alleen de juiste gebruiker toegang heeft tot de gegevens van de organisatie in de app. Daarom moet een eindgebruiker zich aanmelden met een werk- of schoolaccount voordat de pincode voor de Intune-app kan worden ingesteld of hersteld. Deze verificatie wordt verwerkt door Azure Active Directory via uitwisseling van een beveiligde token en is niet transparant voor de [Intune-SDK](../developer/app-sdk.md). Vanuit het oogpunt van veiligheid kunt u werk- of schoolgerelateerde gegevens het beste versleutelen. Versleuteling is niet gerelateerd aan de pincode van de app, maar is een eigen app-beveiligingsbeleid.

**Bescherming tegen beveiligingsaanvallen en de Intune-pincode**<br>
Als onderdeel van het app-pincodebeleid kan de IT-beheerder een maximumaantal verificatiepogingen voor gebruikers instellen voordat de app wordt vergrendeld. Na het toegestane aantal aanmeldingspogingen kan de [Intune-SDK](../developer/app-sdk.md) de 'zakelijke' gegevens in de app wissen.

**Intune-pincode en selectief wissen**<br>
Op iOS/iPadOS worden de pincodegegevens op app-niveau opgeslagen in de sleutelhanger die wordt gedeeld tussen apps met dezelfde uitgever, zoals alle apps van Microsoft zelf. Deze pincodegegevens zijn ook gekoppeld aan een eindgebruikersaccount. Selectief wissen van één app hoort geen invloed te hebben op een andere app. 

Zo wordt bijvoorbeeld een voor Outlook ingestelde pincode voor de aangemelde gebruiker opgeslagen in een gedeelde sleutelhanger. Wanneer de gebruiker zich aanmeldt bij OneDrive (ook gepubliceerd door Microsoft), ziet deze dezelfde pincode als Outlook, omdat OneDrive dezelfde gedeelde sleutelhanger gebruikt. Bij het afmelden bij Outlook of het wissen van de gebruikersgegevens in Outlook, maakt de Intune-SDK die sleutelhanger niet leeg, omdat OneDrive die pincode misschien nog gebruikt. Hierdoor wordt die gedeelde sleutelhanger, met inbegrip van de pincode, niet leeggemaakt bij selectief wissen. Dit gedrag blijft hetzelfde, zelfs als er maar één app van een uitgever op het apparaat bestaat. 

Omdat de pincode wordt gedeeld tussen apps met dezelfde uitgever, weet de Intune-SDK wanneer er één app wordt gewist niet of er nog andere apps van dezelfde uitgever op het apparaat staan. Daarom maakt de Intune-SDK de pincode niet leeg, omdat deze mogelijk nog wordt gebruikt voor andere apps. De verwachting is dat de pincode van de app wordt gewist wanneer de laatste app van die uitgever uiteindelijk wordt verwijderd als onderdeel van een of andere opschoning van het besturingssysteem.
 
Als u ziet dat de pincode op sommige apparaten wordt gewist, gebeurt waarschijnlijk het volgende: Aangezien de pincode aan een identiteit is gekoppeld, wordt de gebruiker gevraagd een nieuwe pincode in te voeren als deze zich na het wissen aanmeldt met een ander account. Als de gebruiker zich echter aanmeldt met een al bestaand account, kan een reeds in de sleutelhanger opgeslagen pincode worden gebruikt om aan te melden.

**Twee keer een pincode instellen voor apps van dezelfde uitgever?**<br>
Voor MAM (op iOS/iPadOS) kan momenteel een pincode op toepassingsniveau worden gebruikt met alfanumerieke tekens en speciale tekens (wachtwoordcode genoemd) waarvoor de deelname van toepassingen (zoals WXP, Outlook, Managed Browser, Yammer) is vereist om te integreren met de [Intune-SDK voor iOS](../developer/app-sdk-ios.md). Zonder deze deelname, worden de instellingen voor de wachtwoordcode niet goed afgedwongen voor de betreffende toepassingen. Dit is een functie die is uitgebracht in de Intune SDK voor iOS v. 7.1.12.

Om deze functie te ondersteunen en te zorgen voor compatibiliteit met eerdere versies van de Intune SDK voor iOS/iPadOS, worden alle pincodes (numeriek of als wachtwoordcode) in 7.1.12+ los van de pincode in eerdere versies van de SDK verwerkt. Dus als een apparaat toepassingen met Intune SDK voor iOS-versies lager dan 7.1.12 EN hoger dan 7.1.12 van dezelfde uitgever heeft, moeten er twee pincodes worden ingesteld. De twee pincodes (voor elke app) staan echter volledig los van elkaar: ze moeten voldoen aan het app-beveiligingsbeleid dat voor die app geldt. Dus *alleen* als voor app A en app B hetzelfde beleid is toegepast (met betrekking tot pincodes), kan de gebruiker dezelfde pincode tweemaal instellen. 

Dit gedrag is specifiek voor de pincode voor iOS-/iPadOS-toepassingen die ingeschakeld zijn met het Intune-beheer van mobiele apps. Na verloop van tijd, wanneer toepassingen nieuwere versies van de Intune SDK voor iOS/iPadOS overnemen, wordt het tweemaal instellen van een pincode voor apps van dezelfde uitgever minder problematisch. Zie de opmerking hieronder voor een voorbeeld.

  >[!NOTE]
  > Als app A bijvoorbeeld is gemaakt met een eerdere versie dan 7.1.12 en app B met een versie die hoger is dan of gelijk is aan 7.1.12 van dezelfde uitgever, moet de eindgebruiker afzonderlijke pincodes instellen voor A en B als beide op een iOS-/iPadOS-apparaat zijn geïnstalleerd.
  > Als een app C met SDK-versie 7.1.9 op het apparaat is geïnstalleerd, gebruikt die app dezelfde pincode als app A. Een app D die is gebouwd met versie 7.1.14 heeft dezelfde pincode als app B.  
  > Als alleen app A en app C op een apparaat zijn geïnstalleerd, hoeft er maar één pincode worden ingesteld. Hetzelfde geldt als alleen app B en app D op een apparaat zijn geïnstalleerd.

### <a name="app-data-encryption"></a>App-gegevensversleuteling
IT-beheerders kunnen een app-beveiligingsbeleid instellen dat vereist dat de gegevens in de app worden versleuteld. De IT-beheerder kan als onderdeel van het beleid ook opgeven wanneer de inhoud wordt versleuteld.

**Hoe werkt het versleutelingsproces van Intune-gegevens**<br> Zie de [beleidsinstellingen voor de beveiliging van Android-apps](app-protection-policy-settings-android.md) en de [beleidsinstellingen voor de beveiliging van iOS-/iPadOS-apps](app-protection-policy-settings-ios.md) voor gedetailleerde informatie over elke beleidsinstelling voor de beveiliging van apps.

**Gegevens die worden versleuteld**<br>
Alleen gegevens die zijn gemarkeerd als 'zakelijk' worden versleuteld overeenkomstig het app-beveiligingsbeleid van de IT-beheerder. Gegevens worden als 'zakelijk' beschouwd wanneer ze afkomstig zijn van een bedrijfslocatie. Voor de Office-apps worden de volgende locaties door Intune beschouwd als bedrijfslocaties:

- E-mail (Exchange) 
- Cloudopslag (OneDrive-app met een OneDrive voor Bedrijven-account)

Alle app-gegevens in Line-Of-Business-apps die worden beheerd door de [Intune App Wrapping Tool](../developer/apps-prepare-mobile-application-management.md)-functionaliteit, worden beschouwd als 'zakelijk'.

### <a name="selective-wipe"></a>Selectief wissen

**Gegevens op afstand wissen**<br>
Met Intune kunnen app-gegevens op drie verschillende manieren worden gewist: 
- Apparaat volledig wissen
- Selectief wissen voor MDM 
- Selectief wissen voor MAM

Raadpleeg [Apparaten verwijderen door wissen of buiten gebruik stellen](../remote-actions/devices-wipe.md) voor meer informatie over wissen op afstand voor MDM. Raadpleeg [de actie Buiten gebruik stellen](../remote-actions/devices-wipe.md#retire) en [Alleen zakelijke gegevens wissen uit apps](apps-selective-wipe.md) voor meer informatie over selectief wissen met behulp van MAM.

Met [Volledig wissen](../remote-actions/devices-wipe.md) verwijdert u alle gebruikersgegevens en instellingen van **het apparaat** door het apparaat terug te zetten op de standaardfabrieksinstellingen. Het apparaat wordt uit Intune verwijderd.

  >[!NOTE]
  > Apparaat volledig wissen en Selectief wissen voor MDM kunnen alleen worden uitgevoerd op apparaten die zijn geregistreerd bij Intune Mobile Device Management (MDM).

**Selectief wissen voor MDM**<br>
Raadpleeg [Apparaten verwijderen - buiten gebruik stellen](../remote-actions/devices-wipe.md#retire) voor meer informatie over het verwijderen van zakelijke gegevens.

**Selectief wissen voor MAM**<br>
Bij selectief wissen voor MAM worden gegevens van bedrijfs-apps gewoon gewist uit een app. De aanvraag wordt gestart via de Intune Azure-portal. Raadpleeg [Alleen zakelijke gegevens wissen uit door Intune beheerde apps](apps-selective-wipe.md) voor meer informatie over hoe u een verzoek om te wissen aanvraagt.

Als de gebruiker de app gebruikt wanneer selectief wissen wordt gestart, controleert de [Intune-SDK](../developer/app-sdk.md) om de 30 minuten op aanvragen van de MAM-service voor selectief wissen. Daarnaast wordt er gecontroleerd of er een aanvraag voor selectief wissen is verzonden wanneer de gebruiker de app voor de eerste keer start en zich aanmeldt met een werk- of schoolaccount.

**Wanneer er geen on-premises services (on-prem) kunnen worden gebruikt in combinatie met apps die zijn beveiligd met Intune**<br>
Voor de app-beveiliging van Intune moet de identiteit van de gebruiker voor de toepassing en [Intune-SDK](../developer/app-sdk.md) consistent zijn. Dit kan alleen worden gegarandeerd via moderne verificatie. Er zijn scenario's waarin apps met een on-premisses configuratie werken, maar deze zijn niet consistent en kunnen ook niet worden gegarandeerd.

**Veilige manier om webkoppelingen te openen vanuit beheerde apps**<br>
De IT-beheerder kan een app-beveiligingsbeleid implementeren en instellen voor de [Intune Managed Browser-app](app-configuration-managed-browser.md), een webbrowser die is ontwikkeld door Microsoft Intune en eenvoudig kan worden beheerd met Intune. De IT-beheerder kan ervoor zorgen dat alle webkoppelingen in de door Intune beheerde apps moeten worden geopend met de Managed Browser-app.

## <a name="app-protection-experience-for-ios-devices"></a>App-beveiligingservaring voor iOS-apparaten

### <a name="device-fingerprint-or-face-ids"></a>Vingerafdruk- of gezichts-id van apparaat 
Het Intune-beleid voor app-beveiliging geeft u de mogelijkheid app-toegang te beperken tot enkel de gebruiker met een Intune-licentie. Een van de manieren om toegang tot de app te beheren, is op ondersteunde apparaten Touch ID of Face ID van Apple te vereisen. Intune implementeert een gedrag waarbij Intune, na iedere wijziging in de biometrische database van het apparaat, de gebruiker vraagt een pincode in te voeren wanneer aan de volgende time-outwaarde voor inactiviteit wordt voldaan. Wijzigingen in biometrische gegevens omvatten het toevoegen of verwijderen van een vingerafdruk of gezicht. Als de Intune-gebruiker geen pincode heeft ingesteld, wordt gevraagd om een Intune-pincode in te stellen.
 
Dit proces heeft als doel de gegevens van uw organisatie in de app op app-niveau veilig en beschermd te houden. Deze functie is alleen beschikbaar voor iOS/iPadOS en vereist het gebruik van toepassingen waarin de Intune-SDK voor iOS/iPadOS, versie 9.0.1 of hoger is geïntegreerd. Integratie van de SDK is nodig om het gedrag te kunnen afdwingen in de betreffende toepassingen. Deze integratie vindt doorlopend plaats en is afhankelijk van de specifieke toepassingsteams. Apps die hieraan deelnemen, zijn onder meer WXP, Outlook, Managed Browser en Yammer.
  
### <a name="ios-share-extension"></a>iOS-extensie voor delen
U kunt de iOS-/iPadOS-extensie voor delen gebruiken om werk- of schoolgegevens te openen in niet-beheerde apps, zelfs wanneer het beleid voor gegevensoverdracht is ingesteld op **Alleen voor beheerde apps** of **Geen apps**. De iOS-/iPadOS-extensie voor delen kan alleen met app-beveiligingsbeleid van Intune worden beheerd indien ook het apparaat wordt beheerd. Daarom worden _**'zakelijke' gegevens door Intune versleuteld voordat ze buiten de app worden gedeeld**_ . U kunt dit versleutelingsgedrag controleren door een 'zakelijk' bestand te openen buiten de beheerde app. Het bestand moet zijn versleuteld en kan niet worden geopend bijten de beheerde app.

### <a name="multiple-intune-app-protection-access-settings-for-same-set-of-apps-and-users"></a>Meerdere toegangsinstellingen voor Intune-app-beveiligingsbeleid voor dezelfde set apps en gebruikers
Het Intune-app-beveiligingsbeleid voor toegang wordt in een bepaalde volgorde toegepast op apparaten van eindgebruikers wanneer ze vanaf hun bedrijfsaccount proberen toegang te krijgen tot een doel-app. In het algemeen krijgt wissen voorrang, dan volgt een waarschuwing die kan worden gesloten. Indien van toepassing op de specifieke gebruiker/app, wordt een instelling van een minimumversie van het iOS-/iPadOS-besturingssysteem die een gebruiker waarschuwt om de iOS-/iPadOS-versie bij te werken bijvoorbeeld toegepast na de instelling van de minimumversie van het iOS-/iPadOS-besturingssysteem die toegang door de gebruiker blokkeert. Dus in het scenario waarin de IT-beheerder de minimumversie van het iOS-besturingssysteem configureert naar 11.0.0.0 en de minimumversie van het iOS-besturingssysteem (alleen Waarschuwing) naar 11.1.0.0, terwijl het apparaat dat de app probeert te openen op iOS 10 zit, wordt de eindgebruiker geblokkeerd op basis van de restrictievere instelling voor de minimumversie van het iOS-besturingssysteem die resulteert in geblokkeerde toegang.

Wanneer u te maken hebt met verschillende soorten instellingen, krijgt een Intune-SDK-versie voorrang, dan een app-versievereiste, gevolgd door de versievereisten van het iOS-/iPadOS-besturingssysteem. Vervolgens worden eventuele waarschuwingen voor alle typen instellingen in dezelfde volgorde gecontroleerd. We raden u aan om de Intune-SDK-versievereisten alleen te configureren op advies van het Intune-productteam voor essentiële blokkerende scenario's.

## <a name="app-protection-experience-for-android-devices"></a>App-beveiligingservaring voor Android-apparaten

### <a name="company-portal-app-and-intune-app-protection"></a>Bedrijfsportal-app en beveiliging van Intune-apps
Veel van de functies voor het beveiligen van apps zijn ingebouwd in de bedrijfsportal-app. Hoewel de bedrijfsportal-app altijd vereist is, hoeft een apparaat _niet te worden geregistreerd_. Voor MAM-WE (beheer van mobiele toepassingen zonder registratie), hoeft de eindgebruiker alleen de bedrijfsportal-app op het apparaat te hebben geïnstalleerd.

### <a name="multiple-intune-app-protection-access-settings-for-same-set-of-apps-and-users"></a>Meerdere toegangsinstellingen voor Intune-app-beveiligingsbeleid voor dezelfde set apps en gebruikers
Het Intune-app-beveiligingsbeleid voor toegang wordt in een bepaalde volgorde toegepast op apparaten van eindgebruikers wanneer ze vanaf hun bedrijfsaccount proberen toegang te krijgen tot een doel-app. In het algemeen krijgt een blokkering voorrang, dan volgt een waarschuwing die kan worden gesloten. Indien van toepassing op de specifieke gebruiker/app wordt een instelling van een minimumversie van een Android-patch die een gebruiker waarschuwt om een patchupgrade uit te voeren, bijvoorbeeld toegepast na de instelling van de minimumversie van de Android-patch die toegang door de gebruiker blokkeert. Dus in het scenario waarin de IT-beheerder de minimumversie van de Android-patch configureert naar 2018-03-01 en de minimumversie van de Android-patch (alleen Waarschuwing) naar 2018-02-01, terwijl het apparaat dat de app probeert te openen op de patchversie 2018-01-01 zit, wordt de eindgebruiker geblokkeerd op basis van de restrictievere instelling voor de minimumversie van de Android-patch die resulteert in geblokkeerde toegang. 

Wanneer u te maken hebt met verschillende soorten instellingen, krijgt een app-versievereiste voorrang, gevolgd door de versievereiste van het Android-besturingssysteem en de versievereiste van de Android-patch. Vervolgens worden eventuele waarschuwingen voor alle typen instellingen in dezelfde volgorde gecontroleerd.

### <a name="intune-app-protection-policies-and-googles-safetynet-attestation-for-android-devices"></a>Intune-app-beveiligingsbeleid en SafetyNet-Attestation voor Android-apparaten van Google 
Intune-app-beveiligingsbeleid biedt beheerders de mogelijkheid om eindgebruikers te verplichten om aan de SafetyNet Attestation-API van Google voor Android-apparaten te voldoen. Er wordt een nieuwe Google Play-servicebepaling naar de IT-beheerder gerapporteerd, volgens een interval die door de Intune-service wordt bepaald. Hoe vaak de serviceaanroep wordt uitgevoerd, wordt vertraagd door de belasting. Deze waarde wordt daarom intern onderhouden en kan niet worden geconfigureerd. Elke actie voor de Google SafetyNet Attestation-instelling die door een IT-beheerder is geconfigureerd, wordt uitgevoerd op basis van het meest recent gerapporteerde resultaat naar de Intune-service op het moment van de voorwaardelijke start. Als er geen gegevens zijn, wordt toegang verleend als er geen andere voorwaardelijke opstartcontroles zijn mislukt, en start de Google Play Store-cyclus voor het bepalen van de attestation-resultaten in de back-end en wordt de gebruiker asynchroon gevraagd of het apparaat is mislukt. Als er verouderde gegevens zijn, wordt toegang geblokkeerd of toegestaan op basis van het laatst gerapporteerde resultaat, en start ook de Google Play Store-cyclus voor het bepalen van de attestation-resultaten en wordt de gebruiker asynchroon gevraagd of het apparaat is mislukt.

### <a name="intune-app-protection-policies-and-googles-verify-apps-api-for-android-devices"></a>Intune-app-beveiligingsbeleid en Verify Apps-API voor Android-apparaten van Google
Intune-app-beveiligingsbeleid biedt beheerders de mogelijkheid om eindgebruikers te verplichten om signalen te verzenden via de Verify Apps-API van Google voor Android-apparaten. De instructies hiervoor kunnen per apparaat enigszins verschillen. Bij het algemene proces gaat u naar de Google Play Store en klikt u op **Mijn apps en games**. Klik vervolgens op het resultaat van de laatste app-scan om naar het menu Play Protect te gaan. Zorg ervoor dat de wisselknop voor **Apparaat scannen op beveiligingsrisico's** is ingesteld op Aan.

### <a name="googles-safetynet-attestation-api"></a>SafetyNet Attestation-API van Google 
Intune gebruikt Google Play Protect SafetyNet-API's om aan onze bestaande rootdetectiecontroles toe te voegen voor niet-ingeschreven apparaten. Google heeft deze API-set ontwikkeld en onderhouden die door Android-apps kan worden gebruikt als deze niet op geroote apparaten moeten worden uitgevoerd. Dit is bijvoorbeeld opgenomen in de Android Pay-app. Hoewel Google niet de volledige rootdetectiecontroles die plaatsvinden openbaar deelt, verwachten we wel dat deze API's gebruikers detecteren die hun apparaten hebben geroot. Toegang van deze gebruikers kan vervolgens worden geblokkeerd, of hun zakelijke accounts kunnen worden gewist uit via beleid ingeschakelde apps. Bij **Basisintegriteit controleren** ziet u de algemene integriteit van het apparaat. Geroote apparaten, emulators, virtuele apparaten en apparaten met zichtbare sabotagesporen voldoen niet aan de basisintegriteit. Bij **Basisintegriteit en gecertificeerde apparaten controleren** krijgt u informatie over de compatibiliteit van het apparaat met de services van Google. Alleen niet-aangepaste apparaten die door Google zijn gecertificeerd, voldoen aan deze controle. De volgende apparaten zullen niet voldoen:

- Apparaten die niet aan de basisintegriteit voldoen
- Apparaten met een ontgrendelde bootloader
- Apparaten met een aangepaste systeemkopie/ROM
- Apparaten waarvoor de fabrikant geen Google-certificering heeft aangevraagd of die niet aan de Google-certificering voldoen
- Apparaten waarbij de systeemkopie rechtstreeks vanuit de bronbestanden van het Android open source-programma zijn is gemaakt
- Apparaten met een preview-versie van de systeemkopie voor de bètaversie/ontwikkelaars

Raadpleeg [De documentatie van Google over SafetyNet Attestation](https://developer.android.com/training/safetynet/attestation) voor technische informatie.

### <a name="safetynet-device-attestation-setting-and-the-jailbrokenrooted-devices-setting"></a>SafetyNet Attestion voor apparaten en de instelling Jailbroken/geroote apparaten
Voor de SafetyNet-API-controles van Google Play is het vereist dat eindgebruikers online zijn voor ten minste de periode waarin de volledige cyclus voor het bepalen van de attestation-resultaten wordt uitgevoerd. Als eindgebruikers offline zijn, kunnen IT-beheerders er alsnog van uitgaan dat voor een resultaat de instelling **Jailbroken/geroote apparaten** wordt vereist. Dit gezegd hebbende: als de eindgebruiker te lang offline is geweest, wordt de waarde **Offlinerespijtperiode** geactiveerd en wordt de toegang tot alle werk- of schoolgegevens geblokkeerd zodra die timerwaarde is bereikt, tot de netwerktoegang weer beschikbaar is. Als beide instellingen worden ingeschakeld, is een gelaagde methode mogelijk om de apparaten van eindgebruikers gezond te houden. Dit is belangrijk als eindgebruikers hun werk- of schoolgegevens op een mobiel apparaat openen.

### <a name="google-play-protect-apis-and-google-play-services"></a>Google Play Protect-API's en Google Play Services
Google Play Services moet actief zijn voor de instellingen van het app-beveiligingsbeleid die gebruikmaken van de Google Play Protect-API's. Voor zowel de instelling **SafetyNet Attestion voor apparaten** als de instelling **Bedreigingsscan op apps** moet de door Google bepaalde versie van Google Play Services naar behoren werken. Aangezien dit de instellingen zijn die in het gebied van beveiliging vallen, wordt de eindgebruiker geblokkeerd als deze instellingen op deze gebruiker zijn gericht en niet voldoen aan de juiste versie van Google Play Services of geen toegang hebben tot Google Play Services.

## <a name="next-steps"></a>Volgende stappen

[Beveiligingsbeleid voor apps maken en implementeren met Microsoft Intune](app-protection-policies.md)

[Beschikbare instellingen voor beveiligingsbeleid voor Android-apps met Microsoft Intune](app-protection-policy-settings-android.md)

[Beschikbare instellingen voor beveiligingsbeleid voor iOS-/iPadOS-apps met Microsoft Intune](app-protection-policy-settings-ios.md)

## <a name="see-also"></a>Zie tevens
Apps van derden, zoals de mobiele app van Salesforce, werken gericht met Intune om bedrijfsgegevens te beveiligen. Ga voor meer informatie over hoe de Salesforce-app met Intune werkt (inclusief MDM-configuratie-instellingen voor apps), naar [Salesforce-app en Microsoft Intune](https://gallery.technet.microsoft.com/Salesforce-App-and-Intune-c47d44ee/file/188000/1/Salesforce%20App%20and%20Intune%20for%20external.pdf).
