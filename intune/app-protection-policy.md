---
title: Wat is beveiligingsbeleid voor apps
titleSuffix: Microsoft Intune
description: Ontdek hoe u met het beveiligingsbeleid voor apps van Microsoft Intune uw bedrijfsgegevens kunt beveiligen en hoe u kunt voorkomen dat gegevens verloren gaan.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/08/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1c086943-84a0-4d99-8295-490a2bc5be4b
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, get-started, seoapril2019
ms.collection: M365-identity-device-management
ms.openlocfilehash: 45e9f50881ff7da0554a4731712441b5fedb01d8
ms.sourcegitcommit: 364a7dbc7eaa414c7a9c39cf53eb4250e1ad3151
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2019
ms.locfileid: "59569412"
---
# <a name="what-are-app-protection-policies"></a>Wat is beveiligingsbeleid voor apps?


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Met het beveiligingsbeleid voor apps van Microsoft Intune kunt u uw bedrijfsgegevens beveiligen en voorkomen dat gegevens verloren gaan.

## <a name="how-you-can-protect-app-data"></a>Hoe u app-gegevens kunt beveiligen
Uw werknemers gebruiken mobiele apparaten voor zowel privé- als werktaken. U wilt er niet alleen voor zorgen dat uw werknemers productief kunnen zijn, maar u wilt bedoeld of onbedoeld gegevensverlies voorkomen. U wilt ook bedrijfsgegevens beveiligen die worden geopend op apparaten die niet door u worden beheerd.

U kunt app-beveiligingsbeleid voor Intune gebruiken **onafhankelijk van een MDM-oplossing (Mobile Device Management)**. Deze onafhankelijkheid helpt u om de gegevens van uw bedrijf te beveiligen, met of zonder dat apparaten zijn ingeschreven bij een oplossing voor apparaatbeheer. Door **beleid op app-niveau** te implementeren, kunt u de toegang tot bedrijfsbronnen beperken en gegevens binnen de controlesfeer van uw IT-afdeling houden.

Beveiligingsbeleid voor apps kan worden geconfigureerd voor apps die worden uitgevoerd op apparaten die:

- **Geregistreerd met Microsoft Intune:** deze apparaten zijn doorgaans in het bezit van het bedrijf.

- **Apparaten die zijn geregistreerd in een oplossing voor mobiel apparaatbeheer van derden:** deze apparaten zijn doorgaans in het bezit van het bedrijf.

  > [!NOTE]
  > MAM-beleid mag niet worden gebruikt met MAM-oplossingen van derden of beveiligde containers.

- **Apparaten die niet zijn geregistreerd in een MDM-oplossing:** Bij deze apparaten gaat het meestal om apparaten die in het bezit zijn van werknemers, of om apparaten die niet worden beheerd door of zijn ingeschreven bij Intune of een andere MDM-oplossing.

> [!IMPORTANT]
> U kunt MAM-beleid maken voor mobiele Office-apps die verbinding maken met Office 365-services. U kunt de toegang tot Exchange on-premises mailboxen tevens beveiligen door beveiligingsbeleid voor Intune-apps te maken voor Outlook voor iOS en Android met hybride moderne verificatie. Voordat u deze functie gebruikt, moet u ervoor zorgen dat u voldoet aan de [Outlook voor iOS- en Android-vereisten](https://technet.microsoft.com/library/mt846639(v=exchg.160).aspx). Beveiligingsbeleid voor apps wordt niet ondersteund voor andere apps die verbinding maken met on-premises Exchange- of SharePoint-services.

**De belangrijke voordelen van het gebruik van het beveiligingsbeleid voor apps zijn**:

-   Uw bedrijfsgegevens worden beschermd op het niveau van de app. Omdat voor Mobile Application Management geen apparaatbeheer is vereist, kunt u bedrijfsgegevens beveiligen op zowel beheerde als niet-beheerde apparaten. Het beheer wordt gecentreerd rond de identiteit van de gebruiker, waardoor er geen apparaatbeheer is vereist.

-   De productiviteit van eindgebruikers wordt niet beïnvloed en beleid is niet van toepassing wanneer de app wordt gebruikt in een persoonlijke context. Het beleid wordt alleen in een werkcontext toegepast, waardoor u de mogelijkheid hebt om bedrijfsgegevens te beschermen zonder aan persoonlijke gegevens te komen.

Het gebruik van MDM met het beveiligingsbeleid voor apps biedt extra voordelen en bedrijven kunnen het beveiligingsbeleid voor apps met en zonder MDM gelijktijdig gebruiken. Stel, een werknemer gebruikt bijvoorbeeld zowel een telefoon die is verleend door het bedrijf, als een privétablet. De bedrijfstelefoon is ingeschreven bij MDM en beveiligd op basis van het beveiligingsbeleid voor apps, terwijl het privéapparaat alleen wordt beveiligd met beveiligingsbeleid voor apps.

- **MDM zorgt ervoor dat het apparaat wordt beveiligd**. U kunt bijvoorbeeld een pincode vereisen voor toegang tot het apparaat, of u kunt beheerde apps op het apparaat implementeren. U kunt ook apps implementeren op apparaten via uw MDM-oplossing, zodat u meer controle over het beheer van apps hebt.

- **Het beveiligingsbeleid voor apps zorgt ervoor dat de app-laag goed wordt beveiligd**. U kunt bijvoorbeeld:
  - Een pincode vereisen om een app te openen in een werkcontext 
  - Het delen van gegevens tussen apps beheren 
  - Het opslaan van bedrijfsgegevens uit apps op persoonlijke opslaglocaties voorkomen


### <a name="supported-platforms-for-app-protection-policies"></a>Ondersteunde platformen voor het beveiligingsbeleid voor apps
De platformondersteuning voor beveiligingsbeleid voor apps in Intune is afgestemd op platformondersteuning voor mobiele Office-toepassingen voor Android- en iOS-apparaten. Zie de sectie **Mobiele apps** van [Systeemvereisten voor Office](https://products.office.com/office-system-requirements#coreui-contentrichblock-9r05pwg) voor de details.

> [!IMPORTANT]
> De Intune-bedrijfsportalapp is vereist op het apparaat om appbeveiligingsbeleid op Android te ontvangen. Raadpleeg de [Appvereisten voor Intune-bedrijfsportaltoegang](end-user-mam-apps-android.md#access-apps) voor meer informatie.

## <a name="how-app-protection-policies-protect-app-data"></a>Hoe het beveiligingsbeleid voor apps app-gegevens beveiligen

#### <a name="apps-without-app-protection-policies"></a>Apps zonder het beveiligingsbeleid voor apps

![Conceptafbeelding voor gegevensverplaatsing tussen apps waarvoor geen beleid is ingesteld](./media/apps-without-protection-policies.png)

Bedrijfsgegevens en persoonlijke gegevens kunnen met elkaar worden vermengd als er apps zonder beperkingen worden gebruikt. Bedrijfsgegevens kunnen terechtkomen op locaties zoals persoonlijke opslag of kunnen worden overgebracht naar apps die buiten uw controlesfeer liggen, wat leidt tot gegevensverlies. De pijlen in het voorgaande diagram geven onbeperkte verplaatsingen weer van gegevens tussen apps (zowel zakelijke als persoonlijke apps) en naar opslaglocaties.


### <a name="data-protection-with-app-protection-policies"></a>Gegevensbeveiliging met het beveiligingsbeleid voor apps

![Conceptafbeelding met bedrijfsgegevens die door beleid worden beschermd](./media/apps-with-protection-policies.png)


U kunt het beveiligingsbeleid voor apps gebruiken om te voorkomen dat bedrijfsgegevens worden opgeslagen op de lokale opslag van het apparaat. U kunt ook gegevensverplaatsing beperken naar andere apps die niet zijn beveiligd met beveiligingsbeleid voor apps. Beveiligingsbeleidsinstellingen voor apps bevatten:
- Beleid voor gegevensverplaatsing zoals **Opslaan als voorkomen** en **Knippen, kopiëren en plakken beperken**.
- Instellingen voor toegangsbeleid zoals **Eenvoudige pincode vereisen voor toegang** en **Beheerde apps blokkeren op gekraakte of geroote apparaten**.

### <a name="data-protection-with-app-protection-policies-on-devices-managed-by-a-mobile-device-management-solution"></a>Gegevensbeveiliging met het beveiligingsbeleid voor apps op apparaten die worden beheerd met een Mobile Device Management-oplossing

![Afbeelding die laat zien hoe het beveiligingsbeleid voor apps werkt op BYOD-apparaten](./media/app-protection-policies-with-mdm.png)

**Voor apparaten die zijn ingeschreven in een MDM-oplossing**-

De voorgaande afbeelding toont de beveiligingslagen die worden geboden door een combinatie van MDM en beveiligingsbeleid voor apps.

De MDM-oplossing:

-   Schrijft het apparaat in

-   Implementeert de apps op het apparaat

-   Zorgt voor continue apparaatcompatibiliteit en -beheer

**Het beveiligingsbeleid voor apps biedt op de volgende manieren extra waarde:**

-   Het helpt u bedrijfsgegevens te beveiligen tegen het lekken van gegevens naar apps en services van gebruikers

-   Beperkingen, zoals *opslaan als*, *klembord* of *pincode*, toepassen op client-apps

-   Het wist bedrijfsgegevens van apps zonder die apps van het apparaat te verwijderen


### <a name="data-protection-with-app-protection-policies-for-devices-without-enrollment"></a>Het biedt gegevensbeveiliging met het beveiligingsbeleid voor apps voor apparaten die niet zijn ingeschreven

![Afbeelding die laat zien hoe het beveiligingsbeleid voor apps werkt op beheerde apparaten](./media/app-protection-policies-without-mdm.png)

Het voorgaande diagram laat zien hoe het beleid voor gegevensbeveiliging op app-niveau werkt zonder MDM.

Voor BYOD-apparaten die niet zijn ingeschreven in een MDM-oplossing, kan het beveiligingsbeleid voor apps helpen bij het beschermen van bedrijfsgegevens op app-niveau.
Er zijn echter enkele beperkingen waar u rekening mee moet houden, zoals:

-   U kunt geen apps implementeren op het apparaat. De eindgebruiker moet de apps downloaden uit de Store.

-   U kunt geen certificaatprofielen op deze apparaten inrichten.

-   U kunt geen Wi-Fi- en VPN-instellingen van het bedrijf op deze apparaten inrichten.

## <a name="app-protection-global-policy"></a>Algemeen appbeveiligingsbeleid

Als een OneDrive-beheerder naar **admin.office.com** bladert en toegang tot het **Apparaat** selecteert, kan deze beheerder de besturingselementen voor **Mobile Application Management** instellen voor de OneDrive- en SharePoint-client-apps. 

Via de instellingen, die beschikbaar zijn gesteld op de OneDrive-beheerdersconsole, wordt het speciale app-beschermingsbeleid **Algemeen** van Intune geconfigureerd. Dit algemene beleid is van toepassing op alle gebruikers in uw tenant en biedt geen enkele manier om te bepalen waarvoor het beleid wordt gericht. 

Zodra het beleid is ingeschakeld, worden de OneDrive- en SharePoint-apps voor iOS en Android standaard beveiligd met de geselecteerde instellingen. Een IT-professional kan dit beleid in de Intune-console bewerken om meer doelgerichte apps toe te voegen en beleidsinstellingen aan te passen. 

Standaard kan er maar één **algemeen** beleid per tenant zijn. U kunt de [Intune Graph-API’s](intune-graph-apis.md) echter gebruiken om extra algemene beleidsregels per tenant te maken, maar dit wordt niet aanbevolen. Het maken van extra algemene beleidsregels wordt afgeraden omdat het oplossen van problemen met de implementatie van dergelijk beleid erg ingewikkeld kan zijn.

Hoewel het **algemene** beleid van toepassing is op alle gebruikers in uw tenant, worden deze instellingen door eventueel Intune-standaardbeleid voor de beveiliging van apps overschreven.


## <a name="multi-identity"></a>Meerdere identiteiten

Met apps die ondersteuning bieden voor meerdere identiteiten, kunt u verschillende accounts (zakelijk en persoonlijk) gebruiken voor toegang tot dezelfde apps, terwijl beveiligingsbeleid voor apps alleen van toepassing is wanneer de apps worden gebruikt in zakelijke context.

Een voorbeeld van een persoonlijke context is een gebruiker die een nieuw document start in Word. Aangezien dit als persoonlijke context wordt beschouwd, wordt er geen beveiligingsbeleid voor apps van Intune toegepast. Zodra het document is opgeslagen in het zakelijke OneDrive-account, wordt het beschouwd als zakelijke context en wordt er Intune-app-beveiligingsbeleid op toegepast.

Een voorbeeld van werkcontext is een gebruiker die de OneDrive-app start met behulp van een werkaccount. In de werkcontext kan deze gebruiker bestanden niet verplaatsen naar een persoonlijke opslaglocatie. Later, wanneer OneDrive wordt gebruikt voor een persoonlijk account, kunnen de gegevens op de persoonlijke OneDrive-locatie zonder beperkingen worden gekopieerd en verplaatst.

- Meer informatie over de apps die ondersteuning bieden voor [MAM en meerdere identiteiten](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) met Intune.

## <a name="next-steps"></a>Volgende stappen

[Beveiligingsbeleid voor apps maken en implementeren met Microsoft Intune](app-protection-policies.md)

## <a name="see-also"></a>Zie tevens
Apps van derden, zoals de mobiele app van Salesforce, werken gericht met Intune om bedrijfsgegevens te beveiligen. Ga voor meer informatie over hoe de Salesforce-app met Intune werkt (inclusief MDM-configuratie-instellingen voor apps), naar [Salesforce-app en Microsoft Intune](https://gallery.technet.microsoft.com/Salesforce-App-and-Intune-c47d44ee/file/188000/1/Salesforce%20App%20and%20Intune%20for%20external.pdf).
