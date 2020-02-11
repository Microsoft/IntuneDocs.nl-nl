---
title: Integratie van Symantec met Microsoft Intune instellen
titleSuffix: Microsoft Intune
description: Meer informatie over hoe u de Symantec Endpoint Protection Mobile-oplossing met Microsoft Intune instelt om de toegang van mobiele apparaten tot bedrijfsresources te beheren.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 359448d9-2384-42ac-a21c-a25148c20a7b
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 19c1bb959212ebeaea40f7089cba5533b6efeb71
ms.sourcegitcommit: c46b0c2d4507be6a2786a4ea06009b2d5aafef85
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/01/2020
ms.locfileid: "76912604"
---
# <a name="set-up-symantec-endpoint-protection-mobile-integration-with-intune"></a>Symantec Endpoint Protection Mobile-integratie met Intune instellen

Voltooi de volgende stappen om de SEP Mobile-oplossing (Symantec Endpoint Protection Mobile) te integreren met Intune. U moet SEP Mobile-apps in Azure AD toevoegen om te kunnen gebruikmaken van eenmalige aanmelding.

> [!NOTE]
> Deze Mobile Threat Defense-leverancier wordt niet ondersteund voor niet-ingeschreven apparaten.

## <a name="before-you-begin"></a>Voordat u begint

### <a name="azure-ad-account-used-to-integrate-intune-and-sep-mobile"></a>Het Azure AD-account dat wordt gebruikt voor de integratie van Intune en SEP Mobile

- Zorg ervoor dat het Azure AD-account juist is geconfigureerd in de [Symantec Endpoint Protection Mobile-beheerconsole](https://aad.skycure.com) voordat u de SEP Mobile-basisinstallatie start.
- Het Azure AD-account moet een globaal beheerdersaccount zijn om de integratie uit te voeren.
### <a name="network-setup"></a>Netwerk instellen

Raadpleeg het Symantec-artikel [SEP Manager configureren na installatie](https://support.symantec.com/us/en/article.HOWTO80819.html) om te controleren of uw netwerk juist is geconfigureerd voor integratie met een SEP Mobile-installatie.

### <a name="full-integration-vs-read-only"></a>Volledige integratie tegenover een integratie met alleen-lezen

SEP Mobile biedt ondersteuning voor twee integratiemodi met Intune:

- **Alleen-lezenintegratie (basisconfiguratie):** hierbij worden alleen apparaten uit Azure Active Directory geïnventariseerd en wordt de Symantec Endpoint Protection Mobile-beheerconsole hiermee gevuld.
<br>
  - Als de selectievakjes **Report the health and risk of devices to Intune** en **Also report security incidents to Intune**  niet zijn ingeschakeld in de Symantec Endpoint Protection Mobile-beheerconsole, is er sprake van een integratie met alleen-lezen. Bij een dergelijke integratie wordt de status van een apparaat (compatibel of niet-compatibel) nooit gewijzigd in Intune.
<br></br>
- **Volledige integratie:** stelt SEP Mobile in staat om risico- en beveiligingsincidentgegevens voor apparaten aan Intune te melden. Hierbij wordt een tweerichtingscommunicatie tussen beide cloudservices tot stand gebracht.

### <a name="how-are-the-sep-mobile-apps-used-with-azure-ad-and-intune"></a>Hoe worden de SEP Mobile-apps gebruikt met Azure AD en Intune?

- **iOS-app:** stelt eindgebruikers in staat om zich bij Azure AD aan te melden met een iOS-app.

- **Android-app:** stelt eindgebruikers in staat om zich bij Azure AD aan te melden met een Android-app.

- **Beheer-app:** dit is de SEP Mobile Azure AD-app voor meerdere tenants die communicatie tussen services met Intune mogelijk maakt.

## <a name="to-set-up-the-read-only-integration-between-intune-and-sep-mobile"></a>De integratie met alleen-lezen tussen Intune en SEP Mobile instellen

> [!IMPORTANT]
> De SEP Mobile-beheerdersreferenties moeten bestaan uit een e-mailaccount van een geldige gebruiker in Azure Active Directory. Als dit niet het geval is, mislukt de aanmelding. SEP Mobile maakt gebruik van Azure Active Directory om deze beheerder te verifiëren door middel van eenmalige aanmelding.

1. Ga naar de [Symantec Endpoint Protection Mobile-beheerconsole](https://aad.skycure.com).

2. Voer uw **SEP Mobile-beheerdersreferenties** in en kies vervolgens **Continue**.

3. Ga naar **Settings** en kies onder **Intune Integration** de optie **Basic Setup**.

4. Kies naast **iOS App** de optie **Add to Active Directory**.

    ![Afbeelding van de Symantec Endpoint Protection Mobile-beheerconsole](./media/skycure-mtd-connector-integration/symantec-portal-basic-add.png)

5. Wanneer de aanmeldingspagina wordt geopend, voert u uw Intune-referenties in en kiest u vervolgens **Accept**.

    ![Afbeelding van de aanmeldingsprompt in Intune voor iOS-app](./media/skycure-mtd-connector-integration/symantec-portal-basic-accept.png)

6. Nadat de app is toegevoegd aan Azure AD, ziet u een melding dat de app is toegevoegd.

    ![Afbeelding van het voltooiingsscherm voor de iOS-app](./media/skycure-mtd-connector-integration/symantec-portal-basic-added.png)

7. Herhaal deze stappen voor de **SEP Mobile Android-app** en de **beheer-app**.

### <a name="add-an-azure-ad-security-group-into-sep-mobile"></a>Een Azure AD-beveiligingsgroep toevoegen aan SEP Mobile

U moet een Azure AD-beveiligingsgroep toevoegen met alle apparaten waarop SEP Mobile wordt uitgevoerd.

- Voer alle beveiligingsgroepen met apparaten in waarop SEP Mobile wordt uitgevoerd en selecteer ze.

    ![Afbeelding van de gebruikersgroepen voor SEP Mobile-apps](./media/skycure-mtd-connector-integration/symantec-portal-basic-groups.png)

Met SEP Mobile worden apparaten waarop de Mobile Threat Defense-service wordt uitgevoerd, gesynchroniseerd met de Azure AD-beveiligingsgroepen.

![Afbeelding van de beveiligingsgroepconfiguratie in de SEP Mobile-beheerconsole](./media/skycure-mtd-connector-integration/symantec-portal-basic-status.png)

## <a name="to-set-up-the-full-integration-between-intune-and-sep-mobile"></a>Volledige integratie tussen Intune en SEP Mobile instellen

### <a name="retrieve-the-directory-id-in-azure-ad"></a>Map-id in Azure AD ophalen

1. Meld u aan bij [Azure Portal](https://portal.azure.com).

2. Typ Active Directory in het zoekvak en selecteer vervolgens **Azure Active Directory**.

3. Kies **Eigenschappen**.

4. Kies naast de **Map-id** het kopieerpictogram en plak de id op een veilige locatie. U hebt deze id nodig in een latere stap.

    ![Afbeelding van de map-id in Azure Portal](./media/skycure-mtd-connector-integration/symantec-azure-portal-directory-ID.png)

### <a name="optional-create-a-dedicated-security-group-for-devices-that-need-to-run-the-sep-mobile-apps"></a>Een toegewezen beveiligingsgroep maken voor apparaten waarop de SEP Mobile-apps moeten worden uitgevoerd (optioneel)
1. Kies in [Azure Portal](https://portal.azure.com) onder **Beheren** de optie **Gebruikers en groepen**. Kies vervolgens **Alle groepen**.

2. Kies de knop **Toevoegen**. Typ een **Naam** voor de groep. Kies onder **Type lidmaatschap** de optie **Toegewezen**.

3. Selecteer op de blade **Leden** de groepsleden en kies vervolgens de knop **Selecteren**.

4. Kies op de blade **Groep** de optie **Maken**.

### <a name="set-up-the-integration-between-symantec-endpoint-protection-mobile-and-intune"></a>Symantec Endpoint Protection Mobile-integratie met Intune instellen

1. Ga naar de [Symantec Endpoint Protection Mobile-beheerconsole](https://aad.skycure.com).

2. Voer uw **SEP Mobile-beheerdersreferenties** in en kies vervolgens **Continue**.

3. Ga naar de sectie **Settings** > **Integrations** > **Intune** > **EMM Integration Selection**.

4. Plak in het vak **Directory ID** de map-id die u in de vorige sectie hebt gekopieerd uit Azure Active Directory en sla de instellingen op.

    ![Afbeelding van de map-id in de SEP Mobile-portal](./media/skycure-mtd-connector-integration/symantec-portal-directory-ID.png)

5. Ga naar de sectie **Settings** > **Integrations** > **Intune** > **Basic Setup**.

6. Kies naast **iOS Aapp** de knop **Add to Active Directory**.

    ![Afbeelding van het toevoegen van de iOS-app aan Active Directory](./media/skycure-mtd-connector-integration/symantec-portal-basic-add.png)

7. Meld u aan met de Azure Active Directory-referenties voor het Office 365-account waarmee de map wordt beheerd.

8. Kies de knop **Accept** om de iOS-app SEP Mobile toe te voegen aan Azure Active Directory.

    ![Afbeelding van de knop Accept](./media/skycure-mtd-connector-integration/symantec-portal-basic-accept.png)

9. Herhaal hetzelfde proces voor de **Android-app** en de **beheer-app**.

10. Selecteer alle gebruikersgroepen waarvoor de SEP Mobile-apps moeten worden uitgevoerd, bijvoorbeeld de beveiligingsgroep die u eerder hebt gemaakt.

    ![Afbeelding van de gebruikersgroepen voor SEP Mobile-apps](./media/skycure-mtd-connector-integration/symantec-portal-basic-groups.png)

11. De apparaten in de geselecteerde groepen worden gesynchroniseerd met SEP Mobile en de gegevens worden gerapporteerd in Intune. U kunt deze gegevens weergeven in de sectie Full Integration. Ga naar de sectie **Settings** > **Integrations** > **Intune** > **Full Integration**.

     ![Afbeelding van de voltooide volledige integratie van SEP Mobile](./media/skycure-mtd-connector-integration/symantec-portal-basic-status.PNG)
## <a name="next-steps"></a>Volgende stappen

[SEP Mobile-apps installeren](mtd-apps-ios-app-configuration-policy-add-assign.md)
