---
title: In ontwikkeling - Microsoft Intune
titleSuffix: ''
description: Microsoft Intune-functies in ontwikkeling
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1c8a7be6646c0035eaefed6d61d749c8469c8a4e
ms.sourcegitcommit: 119962948045079022aa48f968dde3e961d7cd0c
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 06/12/2019
ms.locfileid: "67031651"
---
# <a name="in-development-for-microsoft-intune---june-2019"></a>In ontwikkeling voor Microsoft Intune - juni 2019

Als ondersteuning bij uw gereedheid en planning worden op deze pagina updates voor en functies van de Intune-gebruikersinterface vermeld die in ontwikkeling zijn, maar nog niet zijn uitgebracht. Daarnaast:

- Als we verwachten dat u actie moet ondernemen voorafgaand aan een wijziging, publiceren we een aanvullend bericht in het Office-berichtencentrum.
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
 
## <a name="intune-in-the-azure-portal"></a>Intune in Azure Portal

<!-- ***********************************************-->
### <a name="app-management"></a>Appbeheer

#### <a name="device-users-can-view-all-managed-apps-theyve-installed-or-tried-to-install----2352913---"></a>Apparaatgebruikers kunnen alle beheerde apps bekijken die ze hebben geïnstalleerd of hebben geprobeerd te installeren <!-- 2352913 -->
In de bedrijfsportal voor Windows worden alle beheerde apps (zowel vereiste als beschikbare) weergegeven die op het apparaat van een gebruiker zijn geïnstalleerd. Gebruikers kunnen geprobeerde en in behandeling zijnde app-installaties bekijken met de huidige status ervan. Als uw organisatie geen apps verplicht of beschikbaar stelt, krijgen gebruikers het bericht te zien dat er geen bedrijfs-apps zijn geïnstalleerd. Gebruikers kunnen hun apps ook sorteren of filteren op installatiestatus.

#### <a name="configure-which-browser-is-allowed-to-link-to-organization-data----3145939---"></a>Configureren welke browser een koppeling met organisatiegegevens mag maken <!-- 3145939 -->
U kunt met Intune App Protection Policies (APP) op Android- en iOS-apparaten webkoppelingen van een organisatie overbrengen naar een specifieke browser buiten Intune Managed Browser of Microsoft Edge.  Zie [Wat is beveiligingsbeleid voor apps?](app-protection-policy.md) voor meer informatie over APP.

#### <a name="installed-apps-page-on-the-company-portal-website-----4224326---"></a>Pagina met geïnstalleerde apps op de bedrijfsportalwebsite  <!-- 4224326 -->
De [bedrijfsportalwebsite](https://portal.manage.microsoft.com/) bevat een nieuwe pagina om voor gebruikers alle apps weer te geven die op hun apparaat zijn geïnstalleerd. Deze lijst bevat zowel de beschikbare apps als de apps die worden vereist door hun organisatie. Gebruikers kunnen op deze pagina de installatie- en vereiste-status van de apps op hun apparaat zien. Zie [De Intune-bedrijfsportalwebsite gebruiken](/intune-user-help/using-the-intune-company-portal-website) en [De Microsoft Intune-bedrijfsportal-app configureren](company-portal-app.md) voor meer informatie over de bedrijfsportalwebsite.

#### <a name="call-graph-api-read-operations-from-an-application-without-user-credentials----4655885---"></a>Graph API-leesbewerkingen aanroepen vanuit een toepassing zonder gebruikersreferenties <!-- 4655885 -->
Toepassingen kunnen met app-identiteiten Intune Graph API-leesbewerkingen aanroepen zonder dat er gebruikersreferenties nodig zijn. Zie [Get access without a user](https://docs.microsoft.com/graph/auth-v2-service) (Toegang verkrijgen zonder een gebruiker) voor meer informatie.

<!-- ***********************************************-->
### <a name="device-configuration"></a>Apparaatconfiguratie


#### <a name="support-for-ikev2-vpn-profiles-for-ios----1943438---"></a>Ondersteuning voor IKEv2 VPN-profielen voor iOS <!-- 1943438 -->
U kunt met het IKEv2-protocol VPN-profielen voor de systeemeigen VPN-client van iOS maken. IKEv2 is een nieuw verbindingstype in **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **VPN** voor profieltype > **Instellingen**.

Met deze VPN-profielen wordt de systeemeigen VPN-client geconfigureerd. Er worden dus geen VPN-client-apps geïnstalleerd of naar beheerde apparaten gepusht. Deze functie vereist dat apparaten zijn ingeschreven bij Intune (MDM-inschrijving).

Als u wilt zien welke VPN-instellingen u momenteel kunt configureren, gaat u naar [Configure VPN settings on iOS devices in Microsoft Intune](vpn-settings-ios.md) (VPN-instellingen configureren op iOS-apparaten in Microsoft Intune).

Van toepassing op: iOS

#### <a name="configure-settings-for-kernel-extensions-on-macos-devices----20430240---"></a>Instellingen voor kernelextensies configureren op macOS-apparaten <!-- 20430240 -->
U kunt op macOS-apparaten een apparaatconfiguratieprofiel maken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** kies > **macOS** als platform). Een toekomstige update bevat een nieuwe groep instellingen waarmee u kernelextensies op uw apparaten kunt configureren en gebruiken.

Van toepassing op: macOS 10.13.2 en hoger

#### <a name="baseline-support-for-keyword-search-----3082036-----------"></a>Basislijnondersteuning voor zoeken op trefwoord  <!-- 3082036         -->
Als u een basislijnprofiel voor beveiliging gaat maken of bewerken, kunt u binnenkort de *zoekfunctie* gebruiken om de instellingen te filteren die in de console worden weergegeven.   

#### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>Toepasselijkheidsregels gebruiken bij het maken van Windows 10-apparaatconfiguratieprofielen <!-- 2549910 -->
U kunt Windows 10-apparaatconfiguratieprofielen maken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10** als platform). U kunt een **toepassingsregel** maken zodat het profiel alleen van toepassing is op een specifieke editie of versie. U maakt bijvoorbeeld een profiel waarmee bepaalde BitLocker-instellingen worden ingeschakeld. Als u het profiel toevoegt, gebruikt u een toepassingsregel zodat het profiel alleen van toepassing is op apparaten met Windows 10 Enterprise.

Van toepassing op: 
- Windows 10 en hoger

#### <a name="apps-from-the-store-only-setting-for-windows-10-devices-includes-more-configuration-options----2697002----"></a>Instelling Alleen apps van de Store voor Windows 10-apparaten bevat meer configuratieopties <!-- 2697002  -->

Wanneer u een apparaatbeperkingsprofiel voor Windows-apparaten maakt, kunt u de instelling **Alleen apps van de Store** gebruiken, zodat gebruikers alleen apps van Windows App Store installeren (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** voor platform > **Apparaatbeperkingen** voor profieltype). In een toekomstige update wordt deze instelling uitgebreid om meer opties te ondersteunen. 

Als u de huidige instellingen wilt zien, gaat u naar [Apparaatinstellingen voor Windows 10 (en hoger) voor het toestaan of beperken van functies met Intune](device-restrictions-windows-10.md#app-store).

Van toepassing op Windows 10 en hoger

#### <a name="deploy-multiple-zebra-mobility-extensions-device-profiles-to-a-device-same-user-group-or-same-devices-group----4089955---"></a>Meerdere apparaatprofielen voor Zebra-mobiliteitsextensies op een apparaat of voor dezelfde gebruikersgroep of groep apparaten implementeren <!-- 4089955 -->
U kunt in Intune Zebra-mobiliteitsextensies (MX) gebruiken in een apparaatconfiguratieprofiel om instellingen aan te passen of om instellingen toe te voegen die niet in Intune zijn ingebouwd. Op dit moment kunt u één profiel op één apparaat implementeren. In een toekomstige update kunt u meerdere profielen implementeren voor:

- Dezelfde gebruikersgroep
- Dezelfde groep apparaten
- Eén apparaat

In [Use and manage Zebra devices with Zebra Mobility Extensions in Microsoft Intune](android-zebra-mx-overview.md) (Zebra-apparaten gebruiken en beheren met Zebra Mobility Extensions in Microsoft Intune) ziet u hoe u MX in Intune gebruikt.

Van toepassing op: Android

#### <a name="some-kiosk-settings-on-ios-devices-are-set-using-block-replacing-allow----4404075----"></a>Sommige kioskinstellingen op iOS-apparaten worden ingesteld met behulp van Blokkeren, waardoor Toestaan wordt vervangen <!-- 4404075  -->
Wanneer u een apparaatbeperkingsprofiel maakt op iOS-apparaten (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype > **Kiosk**), stelt u de **automatisch vergrendeling**, **schakelaar voor het belsignaal**, **schermrotatie**, **schermsluimerknop** en **volumeknoppen** in. 

Op dit moment zijn deze instellingen geconfigureerd met behulp van **Toestaan** (blokkeert de functie) of **Niet geconfigureerd** (staat de functie toe). In een toekomstige update zijn de waarden **Blokkeren** (blokkeert de functie) of **Niet geconfigureerd** (staat de functie toe).

Als u de huidige instellingen wilt zien, gaat u naar [iOS-apparaatinstellingen voor het toestaan of beperken van functies](device-restrictions-ios.md). 

Van toepassing op: iOS

#### <a name="use-face-id-for-password-authentication-on-ios-devices----4490704----"></a>Face ID voor wachtwoordverificatie op iOS-apparaten gebruiken <!-- 4490704  -->
Wanneer u een apparaatbeperkingsprofiel voor iOS-apparaten maakt, kunt u een vingerafdruk als wachtwoord gebruiken. In een toekomstige update is met de instellingen voor vingerafdrukwachtwoorden ook gezichtsherkenning mogelijk (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype > **Wachtwoord**). Als gevolg hiervan worden de volgende instellingen gewijzigd:

- **Ontgrendelen met vingerafdruk** is nu **Touch ID en Face ID ontgrendelen**.
- **Wijziging van vingerafdruk (alleen onder supervisie)** is nu **Aanpassing van Touch ID en Face ID (alleen onder supervisie)** .

Face ID is beschikbaar in iOS 11.0 en hoger. Als u de huidige instellingen wilt zien, gaat u naar [iOS-apparaatinstellingen voor het toestaan of beperken van functies met Intune](device-restrictions-ios.md#password).

Van toepassing op: iOS

#### <a name="apps-feature-is-dependent-on-ratings-region-when-restricting-gaming-and-app-store-features-on-ios-devices----4593948----"></a>Apps-functie is afhankelijk van classificatieregio bij het beperken van gaming- en App Store-functies op iOS-apparaten <!-- 4593948  -->
Op iOS-apparaten kunt u functies toestaan of beperken met betrekking tot gaming, de App Store en het weergeven van documenten (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype > **App Store, documentweergave, gaming**). U kunt ook de classificatieregio kiezen, zoals de Verenigde Staten. In een toekomstige update wordt de functie **Apps** een onderliggend element van **Classificatieregio** en is deze afhankelijk van **Classificatieregio**.

Als u de huidige instellingen wilt zien, gaat u naar [iOS-apparaatinstellingen voor het toestaan of beperken van functies met Intune](device-restrictions-ios.md#app-store-doc-viewing-gaming).

Van toepassing op: iOS

#### <a name="administrative-templates-for-group-policy---------3510695---"></a>Beheersjablonen voor groepsbeleid     <!--  3510695 -->
Ter verbetering van de beveiliging van apparaten in de cloud worden er beheersjablonen uitgebracht waarmee u Intune kunt gebruiken om bepaalde instellingen voor groepsbeleid te configureren voor Windows-pc's.  Bij deze sjablonen wordt Policy Configuration Service Provider (CSP) gebruikt om maximaal 2500 extra instellingen van Office, Windows en OneDrive te bieden.

####  <a name="new-settings-for-the-windows-security-baseline-----3534649-4217151------------"></a>Nieuwe instellingen voor de Windows-beveiligingsbasislijn  <!-- 3534649, 4217151          -->
Er worden nieuwe instellingen aan de Windows-beveiligingsbasislijn toegevoegd. De eerste instelling is voor Beveiliging op basis van virtualisatie, waarvoor Beveiligd opstarten vereist is. Met de tweede instelling kunt u spraakactivering van Windows-apps beheren wanneer het scherm is vergrendeld.

#### <a name="security-baselines-will-be-generally-available------3785395---------"></a>Beveiligingsbasislijnen worden algemeen beschikbaar  <!--  3785395       -->
Voor de functie Beveiligingsbasislijnen wordt binnenkort de previewfase beëindigd. Deze is dan algemeen beschikbaar. 

#### <a name="the-windows-security-baseline-template-will-be-generally-available-------3794072---------"></a>De sjabloon Windows-beveiligingsbasislijn wordt algemeen beschikbaar gesteld   <!--  3794072       -->
Voor de sjabloon Windows-beveiligingsbasislijn wordt binnenkort de previewfase beëindigd. Deze is dan algemeen beschikbaar. De preview-versie van de sjabloon wordt buiten gebruik gesteld en een nieuwe sjabloon wordt beschikbaar gesteld.

<!-- ***********************************************-->
### <a name="device-management"></a>Apparaatbeheer

#### <a name="assign-scope-tags-to-all-managed-devices-in-a-security-group----3173810---"></a>Bereiktags toewijzen aan alle beheerde apparaten in een beveiligingsgroep <!-- 3173810 -->
U kunt momenteel aan een apparaat een bereiktag toewijzen door naar de pagina **Eigenschappen** van een bepaald apparaat te gaan en de bereiktags te selecteren. In een toekomstige update kunt u bereiktags toewijzen aan een beveiligingsgroep waarbij ook alle apparaten in de beveiligingsgroep aan die bereiktags worden gekoppeld. Kies hiervoor **Intune** > **Rollen** > **Bereik (tags)**  > **Maken** > **Bereik (tags)** > kies de groepen waaraan u de bereiktag wilt toewijzen. De bereiktag wordt ook aan alle apparaten in deze groepen toegewezen. De bereiktags die worden ingesteld met deze functie, vervangen de bereiktags die zijn ingesteld met de huidige stroom voor apparaatbereiktags. (In een toekomstige update wordt de huidige stroom voor het toewijzen van bereiktags aan apparaten alleen-lezen gemaakt.)

#### <a name="see-the-security-patch-level-for-android-devices----4461911----"></a>Het niveau van de beveiligingspatch voor Android-apparaten bekijken <!-- 4461911  -->
U kunt het niveau van de beveiligingspatch voor Android-apparaten bekijken. Kies hiervoor **Intune** > **Apparaten** > **Alle apparaten** > kies een apparaat > **Bewaken** > **Hardware**.


<!-- ***********************************************-->
## <a name="notices"></a>Mededelingen

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

### <a name="see-also"></a>Zie tevens
Zie [Wat is er nieuw in Microsoft Intune?](whats-new.md) voor meer informatie over recente ontwikkelingen.


