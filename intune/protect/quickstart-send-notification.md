---
title: Snelstartgids - Meldingen verzenden naar niet-compatibele apparaten
titleSuffix: Microsoft Intune
description: In deze In deze quickstart gaat u Microsoft Intune gebruiken om e-mailmeldingen te verzenden naar niet-compatibele apparaten.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/21/2019
ms.topic: quickstart
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a1b89f2d-7937-46bb-926b-b05f6fa9c749
ms.reviewer: jinyoon
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6d89cfcafd5452b990509e0fa6fd431a614ee5c1
ms.sourcegitcommit: a7b479c84b3af5b85528db676594bdb3a1ff6ec6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/22/2019
ms.locfileid: "74410263"
---
# <a name="quickstart-send-notifications-to-noncompliant-devices"></a>Quickstart: Meldingen verzenden naar niet-compatibele apparaten

In deze quickstart gaat u Microsoft Intune gebruiken om een e-mailmelding te verzenden naar uw medewerkers met niet-compatibele apparaten.

Wanneer Intune een apparaat detecteert dat niet compatibel is, markeert Intune standaard het apparaat onmiddellijk als niet-compatibel. [Voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) van Azure Active Directory (Azure AD) blokkeert vervolgens het apparaat. Wanneer een apparaat niet compatibel is, kunt u via Intune acties voor niet-compatibiliteit toevoegen die u de flexibiliteit geven om te bepalen wat u moet doen. U kunt bijvoorbeeld gebruikers een respijtperiode geven om compatibel te zijn voordat niet-compatibele apparaten worden geblokkeerd.

Eén actie die moet worden uitgevoerd wanneer een apparaat niet aan de compatibiliteitsvereisten voldoet, is het verzenden van e-mail aan de gebruiker van het apparaat. U kunt ook een e-mailmelding aanpassen voordat u deze verzendt. U kunt met name aanpassingen doorvoeren voor de ontvangers, het onderwerp en de berichttekst, inclusief het bedrijfslogo, en contactgegevens. Tevens geeft Intune in de e-mailmelding meer informatie over het apparaat dat niet compatibel is.

Als u niet over een Intune-abonnement beschikt, kunt u [zich registreren voor een gratis proefaccount](../fundamentals/free-trial-sign-up.md).

## <a name="prerequisites"></a>Vereisten

Wanneer u nalevingsbeleid gebruikt om toegang tot bedrijfsbronnen door apparaten te blokkeren, moet voorwaardelijke toegang voor Azure AD zijn ingesteld. Als u de quickstart [Een nalevingsbeleid voor apparaten maken](quickstart-set-password-length-android.md) hebt voltooid, gebruikt u Azure Active Directory. Zie [Voorwaardelijke toegang in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) en [Gebruikelijke manieren om voorwaardelijke toegang met Intune te gebruiken](../protect/conditional-access-intune-common-ways-use.md) voor meer informatie over Azure AD.

## <a name="sign-in-to-intune"></a>Aanmelden bij Intune

Meld u bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) aan als een [globale beheerder](../fundamentals/users-add.md#types-of-administrators) of een Intune-[servicebeheerder](../fundamentals/users-add.md#types-of-administrators). Als u een Intune-proefabonnement hebt gemaakt, is het account waarmee u het abonnement hebt gemaakt de globale beheerder.

## <a name="create-a-notification-message-template"></a>Een sjabloon voor een meldingsbericht maken

Maak een sjabloon voor berichtmeldingen om een e-mail naar uw gebruikers te versturen. Wanneer een apparaat niet conform is, worden de gegevens die u in de sjabloon invoert, weergegeven in de e-mail die naar uw gebruikers wordt verzonden.

1. Selecteer in Intune **Apparaten** > **Nalevingsbeleid** > **Meldingen** > **Melding maken**.
2. Voer de volgende informatie in:

   - **Naam**: *Contoso Admin*
   - **Onderwerp**: *Apparaatnaleving*
   - **Bericht**: *Uw apparaat voldoet momenteel niet aan de compatibiliteitsvereisten van onze organisatie.*
   - **E-mailkoptekst - Bedrijfslogo opnemen**: Stel in op **Ingeschakeld** om het logo van uw organisatie weer te geven.
   - **E-mailvoettekst - Bedrijfsnaam opnemen**: Stel in op **Ingeschakeld** om de naam van uw organisatie weer te geven.
   - **E-mailvoettekst - Contactgegevens opnemen**: Stel in op **Ingeschakeld** om de contactgegevens van uw organisatie weer te geven.

   ![Voorbeeld van een compatibel meldingsbericht in Intune](./media/quickstart-send-notification/quickstart-send-notification-01.png)

3. Selecteer **Volgende** en controleer uw melding. Als u **Maken** selecteert, is de sjabloon voor het meldingsbericht klaar voor gebruik.

   > [!NOTE]
   > U kunt ook een eerder gemaakte meldingssjabloon bewerken.

Raadpleeg de volgende artikelen voor meer details over het instellen van uw bedrijfsnaam, de contactgegevens van uw bedrijf en het bedrijfslogo:

- [Bedrijfsinformatie en privacyverklaring](../apps/company-portal-app.md#company-information-and-privacy-statement)
- [Ondersteuningsinformatie](../apps/company-portal-app.md#support-information)
- [Aanpassing bedrijfshuisstijl](../apps/company-portal-app.md#company-identity-branding-customization)

## <a name="add-a-noncompliance-policy"></a>Een beleid voor niet-compatibiliteit toevoegen

Wanneer u een nalevingsbeleid voor apparaten maakt, maakt Intune automatisch een actie voor niet-naleving. In Intune worden apparaten vervolgens als niet-compatibel gemarkeerd als ze niet voldoen aan uw nalevingsbeleid. U kunt aanpassen hoe lang het apparaat wordt gemarkeerd als niet-compatibel. U kunt ook nog een actie toevoegen wanneer u een compatibiliteitsbeleid maakt of wanneer u een bestaand compatibiliteitsbeleid bijwerkt.

Via de volgende stappen kunt u een compatibiliteitsbeleid voor Windows 10-apparaten maken.

1. Selecteer in Intune **Apparaten** > **Nalevingsbeleid** > **Beleid maken**.

2. Voer de volgende informatie in:

   - **Naam**: *Compatibiliteit met Windows 10*
   - **Beschrijving**: *Nalevingsbeleid van Windows 10*
   - **Platform**: Windows 10 en hoger

3. Selecteer **Instellingen** > **Systeembeveiliging** om de instellingen met betrekking tot de apparaatbeveiliging weer te geven.

4. Configureer de volgende opties:

   - Stel **Wachtwoord vereisen voor het ontgrendelen van mobiele apparaten** in op **Vereisen**. Met deze beleidsinstelling geeft u aan of gebruikers een wachtwoord moeten invoeren om toegang te krijgen tot informatie op hun mobiele apparaat.

   - Stel **Minimale wachtwoordlengte** in op **6**. Met deze instelling bepaalt u het minimale aantal cijfers of tekens waaruit het wachtwoord moet bestaan.

   ![Systeembeveiligingsinstellingen voor een nieuw compatibiliteitsbeleid](./media/quickstart-send-notification/system-security-settings-01.png)

5. Selecteer **OK** > **OK** > **Maken** om uw compliancebeleid te maken.

6. Selecteer **Eigenschappen** > **Actie voor niet-compatibiliteit** > **Toevoegen**.

7. Controleer in de vervolgkeuzelijst **Actie** of **E-mailbericht verzenden naar eindgebruikers** is geselecteerd.

8. Selecteer **Berichtsjabloon**, de sjabloon die u eerder in dit artikel hebt gemaakt, en vervolgens **Selecteren** om de berichtsjabloon te selecteren.

9. Selecteer **TOEVOEGEN** > **OK** > **Opslaan** om uw wijzigingen op te slaan.

## <a name="assign-the-policy"></a>Wijs het beleid toe

U kunt het compatibiliteitsbeleid toewijzen aan een specifieke groep gebruikers of aan alle gebruikers. Wanneer Intune detecteert dat een apparaat niet compatibel is, wordt de gebruiker geïnformeerd dat ze hun apparaat moeten bijwerken om dit te laten voldoen aan het nalevingsbeleid. Met de volgende stappen kunt u het beleid toewijzen.

1. Ga in Intune naar **Apparaten** > **Nalevingsbeleid** en selecteer het **Windows 10-nalevingsbeleid** dat u eerder hebt gemaakt.

2. Selecteer **Toewijzingen**.

3. Selecteer in de vervolgkeuzelijst **Toewijzen aan** de optie **Alle gebruikers**. Hiermee worden alle gebruikers geselecteerd. Elke gebruiker die een apparaat heeft met **Windows 10 en hoger** dat niet voldoet aan dit compatibiliteitsbeleid wordt op de hoogte gesteld.

    > [!NOTE]
    > U kunt groepen opnemen en uitsluiten bij het toewijzen van compatibiliteitsbeleid.

4. Klik op **Opslaan**.

Als het beleid is gemaakt en opgeslagen, wordt dit weergegeven in de lijst **Nalevingsbeleid - Beleid**. U ziet in de lijst dat **Toegewezen** is ingesteld op **Ja**.

## <a name="next-steps"></a>Volgende stappen

In deze snelstartgids hebt u Intune gebruikt om een compatibiliteitsbeleid te maken en toe te wijzen voor de Windows 10-apparaten van uw werknemers om een wachtwoord van ten minste zes tekens lang te vereisen. Zie [Een compatibiliteitsbeleid voor Windows-apparaten in Intune toevoegen](compliance-policy-create-windows.md) voor meer informatie over het maken van compatibiliteitsbeleid voor Windows-apparaten.

Als u deze reeks snelstartgidsen voor Intune wilt volgen, kunt u doorgaan met de volgende snelstartgids.

> [!div class="nextstepaction"]
> [Quickstart: Een client-app toevoegen en toewijzen](../apps/quickstart-add-assign-app.md)
