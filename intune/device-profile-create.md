---
title: Apparaatprofielen maken in Microsoft Intune - Azure | Microsoft Docs
description: Voeg een apparaatconfiguratieprofiel toe in Microsoft Intune of configureer er een. Selecteer het platformtype, configureer de instellingen en voeg een bereiktag toe.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/03/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 08c6ece37a4ff6eceaa4df735f365453a4bc7d88
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2019
ms.locfileid: "59570400"
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Een apparaatprofiel maken in Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Met apparaatprofielen kunt u instellingen toevoegen en configureren, en deze instellingen vervolgens naar apparaten in uw organisatie pushen. Meer details, onder andere over wat u allemaal kunt doen, vindt u in: [Functies en instellingen toepassen op uw apparaten met apparaatprofielen](device-profiles.md).

Dit artikel:

- Laat zien welke stappen nodig zijn voor het maken van een profiel.
- Laat u zien hoe u een bereiktag kunt toevoegen om het profiel te filteren.
- Geeft de cyclusduur voor vernieuwen van check-ins weer wanneer apparaten profielen ontvangen en bij eventuele profielupdates.

## <a name="create-the-profile"></a>Het profiel maken

1. Selecteer in [Azure Portal](https://portal.azure.com) de optie **Alle services** > filter op **Intune** > selecteer **Intune**.

2. Selecteer **Apparaatconfiguratie**. U hebt de volgende opties:

    - **Overzicht**: geeft de status van uw profielen weer en biedt aanvullende details over de profielen die u aan gebruikers en apparaten hebt toegewezen.
    - **Beheren**: maak apparaatprofielen en upload aangepaste [PowerShell-scripts](intune-management-extension.md) die binnen het profiel worden uitgevoerd, en voeg met [eSIM](esim-device-configuration.md) gegevensplannen toe aan apparaten.
    - **Bewaken**: controleer de status van een profiel op slagen of falen, en bekijk ook logboeken over uw profielen.
    - **Configureren**: voeg een certificeringsinstantie (SCEP of PFX) toe of schakel [Telecom-onkostenbeheer](telecom-expenses-monitor.md) aan het profiel toe.

3. Selecteer **Profielen** > **Profiel maken**. Voer de volgende eigenschappen in:

   - **Naam**: Voer een beschrijvende naam in voor het profiel. Geef uw profielen een naam zodat u ze later eenvoudig kunt identificeren. Een goede profielnaam is bijvoorbeeld **WP-e-mailprofiel voor hele bedrijf**.
   - **Beschrijving**: Voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
   - **Platform**: Kies het platform van uw apparaten. Uw opties zijn:  

       - **Android**
       - **Android Enterprise**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 en hoger**
       - **Windows 10 en hoger**

   - **Profieltype**: Selecteer het type instellingen dat u wilt configureren. De lijst die wordt getoond, is afhankelijk van het **platform** dat u kiest.
   - **Instellingen**: In de volgende artikelen worden de instellingen voor elk profieltype beschreven:

       - [Beheersjablonen](administrative-templates-windows.md)
       - [Aangepast](custom-settings-configure.md)
       - [Delivery optimization](delivery-optimization-windows.md)
       - [Apparaatfuncties](device-features-configure.md)
       - [Apparaatbeperkingen](device-restrictions-configure.md)
       - [Editie-upgrade en modusschakelaar](edition-upgrade-configure-windows-10.md)
       - [Onderwijs](education-settings-configure.md)
       - [E-mail](email-settings-configure.md)
       - [Endpoint Protection](endpoint-protection-configure.md)
       - [Identiteitsbescherming](identity-protection-configure.md)  
       - [Kiosk](kiosk-settings.md)
       - [PKCS-certificaat](certficates-pfx-configure.md)
       - [SCEP-certificaat](certificates-scep-configure.md)
       - [Vertrouwd certificaat](certificates-configure.md)
       - [Updatebeleid](software-updates-ios.md)
       - [VPN](vpn-settings-configure.md)
       - [Wi-Fi](wi-fi-settings-configure.md)
       - [Windows Defender ATP](advanced-threat-protection.md)
       - [Windows Information Protection](windows-information-protection-configure.md)

     Als u bijvoorbeeld **iOS** selecteert als platform, zien uw opties voor het profieltype er ongeveer uit als het volgende profiel:

     ![iOS-profiel maken in Intune](./media/create-device-profile.png)

4. Wanneer u klaar bent, selecteert u **OK** > **Maken** om uw wijzigingen op te slaan. Het profiel wordt gemaakt en weergegeven in de lijst.

## <a name="scope-tags"></a>Bereiktags

Nadat u de instellingen hebt toegevoegd, kunt u ook een bereiktag toevoegen aan het profiel. Met bereiktags wordt beleid toegewezen aan en gefilterd voor specifieke groepen, zoals HR of Alle NL-AMST-werknemers.

Zie [RBAC en bereiktags gebruiken voor gedistribueerde IT](scope-tags.md) voor meer informatie over bereiktags en wat u hiermee kunt doen.

### <a name="add-a-scope-tag"></a>Een bereiktag toevoegen

1. Selecteer **Bereik (tags)**.
2. Selecteer **Toevoegen** om een nieuwe bereiktag te maken. Of selecteer een bestaande bereiktag in de lijst.
3. Selecteer **OK** om uw wijzigingen op te slaan.

## <a name="refresh-cycle-times"></a>Cyclusduur vernieuwen

In Intune worden de volgende vernieuwingscycli gebruikt om te controleren op updates voor configuratieprofielen:

| Platform | Cyclus vernieuwen|
| --- | --- |
| iOS | Om de 6 uur |
| macOS | Om de 6 uur |
| Android | Om de 8 uur |
| Pc’s met Windows 10 die als apparaten zijn geregistreerd | Om de 8 uur |
| Windows Phone | Om de 8 uur |
| Windows 8.1 | Om de 8 uur |

Als het apparaat onlangs is ingeschreven, worden de check-ins vaker uitgevoerd:

| Platform | Frequentie |
| --- | --- |
| iOS | Om de 15 minuten gedurende 6 uur en daarna om de 6 uur |  
| macOS | Om de 15 minuten gedurende 6 uur en daarna om de 6 uur | 
| Android | Om de 3 minuten gedurende 15 minuten en daarna om de 15 minuten gedurende 2 uur en vervolgens om de 8 uur | 
| Pc’s met Windows 10 die als apparaten zijn geregistreerd | Elke 3 minuten gedurende 30 minuten en vervolgens om de 8 uur | 
| Windows Phone | Om de 5 minuten gedurende 15 minuten en daarna om de 15 minuten gedurende 2 uur en vervolgens om de 8 uur | 
| Windows 8.1 | Om de 5 minuten gedurende 15 minuten en daarna om de 15 minuten gedurende 2 uur en vervolgens om de 8 uur | 

Gebruikers kunnen ook de bedrijfsportal-app openen en het apparaat synchroniseren om op elk gewenst moment op aanwezig beleid te controleren.

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).
