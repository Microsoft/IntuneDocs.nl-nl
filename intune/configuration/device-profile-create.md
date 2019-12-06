---
title: Apparaatprofielen maken in Microsoft Intune - Azure | Microsoft Docs
description: Voeg een apparaatconfiguratieprofiel toe in Microsoft Intune of configureer er een. Selecteer het platformtype, configureer de instellingen en voeg een bereiktag toe.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0c4c995322234a4a2486d8e6c5e9efd88f78dd63
ms.sourcegitcommit: 2fddb293d37453736ffa54692d03eca642f3ab58
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/22/2019
ms.locfileid: "74390871"
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Een apparaatprofiel maken in Microsoft Intune

Met apparaatprofielen kunt u instellingen toevoegen en configureren, en deze instellingen vervolgens naar apparaten in uw organisatie pushen. Meer details, onder andere over wat u allemaal kunt doen, vindt u in: [Functies en instellingen toepassen op uw apparaten met apparaatprofielen](device-profiles.md).

Dit artikel:

- Laat zien welke stappen nodig zijn voor het maken van een profiel.
- Laat u zien hoe u een bereiktag kunt toevoegen om het profiel te filteren.
- Beschrijft de regels voor toepasselijkheid op Windows 10-apparaten en laat zien hoe u een regel kunt maken.
- Geeft de cyclusduur voor vernieuwen van check-ins weer wanneer apparaten profielen ontvangen en bij eventuele profielupdates.

## <a name="create-the-profile"></a>Het profiel maken

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecteer **Apparaten** > **Configuratieprofielen**. U hebt de volgende opties:

    - **Overzicht**: geeft de status van uw profielen weer en biedt aanvullende details over de profielen die u aan gebruikers en apparaten hebt toegewezen.
    - **Beheren**: maak apparaatprofielen en upload aangepaste [PowerShell-scripts](../apps/intune-management-extension.md) die binnen het profiel worden uitgevoerd, en voeg met [eSIM](esim-device-configuration.md) gegevensplannen toe aan apparaten.
    - **Bewaken**: controleer de status van een profiel op slagen of falen, en bekijk ook logboeken over uw profielen.
    - **Configureren**: voeg een certificeringsinstantie (SCEP of PFX) toe of schakel [Telecom-onkostenbeheer](telecom-expenses-monitor.md) aan het profiel toe.

3. Selecteer **Profiel maken**. Voer de volgende eigenschappen in:

   - **Naam**: Voer een beschrijvende naam in voor het profiel. Geef uw profielen een naam zodat u ze later eenvoudig kunt identificeren. Een goede profielnaam is bijvoorbeeld **WP-e-mailprofiel voor hele bedrijf**.
   - **Beschrijving**: Voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
   - **Platform**: Kies het platform van uw apparaten. Uw opties zijn:  

       - **Android**
       - **Android Enterprise**
       - **iOS/iPadOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 en hoger**
       - **Windows 10 en hoger**

   - **Profieltype**: Selecteer het type instellingen dat u wilt configureren. De lijst die wordt getoond, is afhankelijk van het **platform** dat u kiest.
   - **Instellingen**: In de volgende artikelen worden de instellingen voor elk profieltype beschreven:

       - [Beheersjablonen](administrative-templates-windows.md)
       - [Aangepast](../custom-settings-configure.md)
       - [Delivery optimization](../delivery-optimization-windows.md)
       - [Apparaatfuncties](../device-features-configure.md)
       - [Apparaatbeperkingen](device-restrictions-configure.md)
       - [Editie-upgrade en modusschakelaar](edition-upgrade-configure-windows-10.md)
       - [Onderwijs](education-settings-configure.md)
       - [E-mail](email-settings-configure.md)
       - [Endpoint Protection](../protect/endpoint-protection-configure.md)
       - [Identiteitsbescherming](../protect/identity-protection-configure.md)  
       - [Kiosk](kiosk-settings.md)
       - [PKCS-certificaat](../protect/certficates-pfx-configure.md)
       - [PKCS-geïmporteerd certificaat](../protect/certificates-imported-pfx-configure.md)
       - [Voorkeursbestand](preference-file-settings-macos.md)
       - [SCEP-certificaat](../protect/certificates-scep-configure.md)
       - [Vertrouwd certificaat](../protect/certificates-configure.md)
       - [Updatebeleid](../software-updates-ios.md)
       - [VPN](vpn-settings-configure.md)
       - [Wi-Fi](wi-fi-settings-configure.md)
       - [Microsoft Defender ATP](../protect/advanced-threat-protection.md)
       - [Windows Information Protection](../protect/windows-information-protection-configure.md)

     Als u bijvoorbeeld **iOS/iPadOS** selecteert als platform, zien uw opties voor het profieltype er ongeveer uit als het volgende profiel:

     ![iOS-profiel maken in Intune](./media/device-profile-create/create-device-profile.png)

4. Wanneer u klaar bent, selecteert u **OK** > **Maken** om uw wijzigingen op te slaan. Het profiel wordt gemaakt en weergegeven in de lijst.

## <a name="scope-tags"></a>Bereiktags

Nadat u de instellingen hebt toegevoegd, kunt u ook een bereiktag toevoegen aan het profiel. Met bereiktags wordt beleid toegewezen aan en gefilterd voor specifieke groepen, zoals HR of Alle NL-AMST-werknemers.

Zie [RBAC en bereiktags gebruiken voor gedistribueerde IT](../fundamentals/scope-tags.md) voor meer informatie over bereiktags en wat u hiermee kunt doen.

### <a name="add-a-scope-tag"></a>Een bereiktag toevoegen

1. Selecteer **Bereik (tags)** .
2. Selecteer **Toevoegen** om een nieuwe bereiktag te maken. Of selecteer een bestaande bereiktag in de lijst.
3. Selecteer **OK** om uw wijzigingen op te slaan.

## <a name="applicability-rules"></a>Toepasselijkheidsregels

Van toepassing op:

- Windows 10 en hoger

Met regels voor toepasselijkheid kunnen beheerders doelapparaten instellen in een groep die aan bepaalde criteria voldoet. U maakt bijvoorbeeld een profiel voor beperkingen voor apparaten dat van toepassing is op de groep **Alle Windows 10-apparaten**. En u wilt het profiel alleen toewijzen aan apparaten met Windows 10 Enterprise.

Hiertoe maakt u een **regel voor toepasselijkheid**. Deze regels zijn handig voor de volgende scenario's:

- U gebruikt Windows 10 Education (EDU). Bij Bellows College wilt u alle Windows 10 EDU-apparaten tussen RS3 en RS4 instellen als doel.
- U wilt alle gebruikers in HR op Contoso instellen, maar alleen Windows 10 Professional- of Enterprise-apparaten.

In deze scenario's doet u het volgende:

- Maak een groep apparaten die alle apparaten bij Bellows College omvat. Voeg in het profiel een regel voor toepasselijkheid toe die van toepassing is als de minimumversie van het besturingssysteem `16299` is en de maximumversie `17134` is. Wijs dit profiel toe aan de groep Bellows College-apparaten.

  Wanneer deze is toegewezen, is het profiel van toepassing op apparaten tussen de minimum- en maximumversie die u opgeeft. Apparaten waarvan de versie niet tussen de door u ingevoerde minimum- en maximumversie ligt, hebben de status **Niet van toepassing**.

- Maak een gebruikersgroep met alle gebruikers in Human Resources (HR) bij Contoso. Voeg in het profiel een regel voor toepasselijkheid toe die van toepassing is op apparaten met Windows 10 Professional of Enterprise. Wijs dit profiel toe aan de HR-gebruikersgroep.

  Na de toewijzing is het profiel van toepassing op apparaten met Windows 10 Professional of Enterprise. Apparaten met een andere editie dan deze hebben de status **Niet van toepassing**.

- Als er twee profielen zijn met exact dezelfde instellingen, wordt het profiel zonder een regel voor toepasselijkheid toegepast. 

  Profiel A heeft bijvoorbeeld als doel de groep Windows 10-apparaten, schakelt BitLocker in en heeft geen regel voor toepasselijkheid. Profiel B heeft als doel dezelfde groep Windows 10-apparaten, schakelt BitLocker in, en heeft een regel voor toepasselijkheid om het profiel alleen toe te passen op Windows 10 Enterprise.

  Wanneer beide profielen worden toegewezen, wordt profiel A toegepast omdat dat profiel geen regel voor toepasselijkheid heeft. 

Wanneer u het profiel aan de groepen toewijst, fungeren de regels voor toepasselijkheid als filters en worden ze alleen toegepast op de apparaten die voldoen aan uw criteria.

### <a name="add-a-rule"></a>Een regel toevoegen

1. Selecteer **Regels voor toepasselijkheid**. U kunt de **regel**, de **eigenschap** en de **editie van het besturingssysteem** kiezen:

    ![Voeg een regel voor toepasselijkheid aan een apparaatconfiguratieprofiel toe in Microsoft Intune](./media/device-profile-create/applicability-rules.png)

2. Kies in **Regel** of u gebruikers of groepen wilt opnemen of uitsluiten. Uw opties zijn:

    - **Profiel toewijzen als**: hiermee kunt u gebruikers of groepen opnemen die voldoen aan de criteria die u invoert.
    - **Profiel niet toewijzen als**: hiermee kunt u gebruikers of groepen uitsluiten die voldoen aan de criteria die u invoert.

3. Kies in **Eigenschap** het gewenste filter. Uw opties zijn: 

    - **Editie van het besturingssysteem**: Selecteer in de lijst de Windows 10-edities die u in de regel wilt opnemen (of uitsluiten).
    - **Versie van het besturingssysteem**: Voer het **minimum** en **maximum** in voor de Windows 10-versienummers die u met de regel wilt opnemen (of uitsluiten). Beide waarden zijn vereist.

      U kunt bijvoorbeeld `10.0.16299.0` (RS3 of 1709) invoeren voor de minimumversie en `10.0.17134.0` (RS4 of 1803) voor de maximumversie. U kunt ook specifieke waarden opgeven, zoals `10.0.16299.001` voor de minimumversie en `10.0.17134.319` voor de maximumversie.

4. Selecteer **Toevoegen** om uw wijzigingen op te slaan.

## <a name="refresh-cycle-times"></a>Cyclusduur vernieuwen

In Intune worden verschillende vernieuwingscycli gebruikt om te controleren op updates voor configuratieprofielen. Als het apparaat onlangs is ingeschreven, worden de check-ins vaker uitgevoerd. [Vernieuwingscycli voor beleidsregels en profielen](device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned) bevat de geschatte vernieuwingstijden.

Gebruikers kunnen ook de bedrijfsportal-app openen en het apparaat synchroniseren om op elk gewenst moment op aanwezig beleid te controleren.

## <a name="recommendations"></a>Aanbevelingen

Houd bij het maken van profielen rekening met de volgende aanbevelingen:

- Geef elk beleid een naam zodat u weet wat het is en wat het doet. Elk [nalevingsbeleid](../protect/create-compliance-policy.md) en alle [configuratieprofielen](../configuration/device-profile-create.md) hebben een optionele eigenschap **Beschrijving**. Wees specifiek bij het opgeven van de **beschrijving**, zodat anderen weten wat het beleid doet.

  Enkele voorbeelden van configuratieprofielen zijn:

  **Profielnaam**: Beheersjabloon - OneDrive-configuratieprofiel voor alle Windows 10-gebruikers  
  **Profielbeschrijving**: sjabloonprofiel van de OneDrive-beheerder met de minimale en de basisinstellingen voor alle Windows 10-gebruikers. Gemaakt door user@contoso.com om te voorkomen dat gebruikers organisatiegegevens delen met persoonlijke OneDrive-accounts.

  **Profielnaam**: VPN-profiel voor alle iOS-gebruikers  
  **Profielbeschrijving**: VPN-profiel met de minimale en basisinstellingen voor alle iOS-gebruikers om verbinding te maken met Contoso VPN. Gemaakt door user@contoso.com, zodat gebruikers automatisch worden geverifieerd voor VPN, in plaats van gebruikers te vragen om hun gebruikersnaam en wachtwoord op te geven.

- Maak uw profiel op basis van de bijbehorende taak, zoals Microsoft Edge-instellingen configureren, Microsoft Defender-antivirusinstellingen inschakelen, opengebroken iOS apparaten blokkeren enzovoort.

- Maak profielen die van toepassing zijn op specifieke groepen, zoals Marketing, Verkoop, IT-beheerders, of op locatie of schoolsysteem.

- Gebruikersbeleid gescheiden houden van apparaatbeleid.

  [Beheersjablonen in Intune](administrative-templates-windows.md) bevatten bijvoorbeeld honderden ADMX-instellingen. Deze sjabloon toont of een instelling van toepassing is op gebruikers of op apparaten. Als u beheersjablonen maakt, wijst u de gebruikersinstellingen toe aan een gebruikersgroep en wijst u de apparaatinstellingen toe aan een apparaatgroep.

  In de volgende afbeelding ziet u een voorbeeld van een instelling die kan worden toegepast op gebruikers en/of apparaten:

  ![Intune-beheersjabloon die van toepassing is op gebruikers en apparaten](./media/device-profile-create/setting-applies-to-user-and-device.png)

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](../device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).
