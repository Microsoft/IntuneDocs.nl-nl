---
title: Snelstartgids - Meldingen verzenden naar niet-compatibele apparaten
titlesuffix: Microsoft Intune
description: In deze snelstartgids gebruikt u Microsoft Intune om e-mailmeldingen te verzenden naar niet-compatibele apparaten.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/09/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a1b89f2d-7937-46bb-926b-b05f6fa9c749
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e76e173bef7a370f89f60f6c9eb4588bb63aefdc
ms.sourcegitcommit: 4c4e87cb0d8906085fcb7cdd170bd6b0cfeb23ff
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/10/2018
ms.locfileid: "51510904"
---
# <a name="quickstart-send-notifications-to-noncompliant-devices"></a>Snelstartgids: Meldingen verzenden naar niet-compatibele apparaten

In deze snelstartgids gebruikt u Microsoft Intune om een e-mailmelding te verzenden naar degenen van uw personeel met niet-compatibele apparaten.

Wanneer Intune een apparaat detecteert dat niet compatibel is, markeert Intune standaard het apparaat onmiddellijk als niet-compatibel. [Voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) van Azure Active Directory (AAD) blokkeert vervolgens het apparaat. Wanneer een apparaat niet compatibel is, kunt u via Intune acties voor niet-compatibiliteit toevoegen die u de flexibiliteit geven om te bepalen wat u moet doen. U kunt bijvoorbeeld gebruikers een respijtperiode geven om compatibel te zijn voordat niet-compatibele apparaten worden geblokkeerd.

Een van de acties die u kunt uitvoeren wanneer apparaten niet compatibel zijn, is dat u e-mail verzendt naar die eindgebruikers. U kunt ook een e-mailmelding aanpassen voordat u deze naar de eindgebruikers verzendt. U kunt met name aanpassingen doorvoeren voor de ontvangers, het onderwerp en de berichttekst, inclusief het bedrijfslogo, en contactgegevens. Tevens geeft Intune meer informatie over het apparaat dat niet compatibel is in de e-mailmelding.

Als u niet over een Intune-abonnement beschikt, kunt u [zich registreren voor een gratis proefaccount](free-trial-sign-up.md).

## <a name="prerequisites"></a>Vereisten
- Wanneer u nalevingsbeleid gebruikt om toegang tot bedrijfsbronnen door apparaten te blokkeren, moet voorwaardelijke toegang voor AAD zijn ingesteld. Als u de snelstartgids [Een nalevingsbeleid voor apparaten maken](quickstart-set-password-length-android.md) hebt voltooid, gebruikt u Azure Active Directory. Zie [Voorwaardelijke toegang in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) en [Gebruikelijke manieren om voorwaardelijke toegang met Intune te gebruiken](conditional-access-intune-common-ways-use.md) voor meer informatie over AAD.

## <a name="sign-in-to-intune"></a>Aanmelden bij Intune

Meld u aan bij de [Intune](https://aka.ms/intuneportal)-portal als [globale beheerder](users-add.md#types-of-administrators) of Intune-[servicebeheerder](users-add.md#types-of-administrators). 

## <a name="create-a-notification-message-template"></a>Een sjabloon voor een meldingsbericht maken

Maak een sjabloon voor berichtmeldingen om een e-mail naar uw gebruikers te versturen. Wanneer een apparaat niet conform is, worden de gegevens die u in de sjabloon invoert, weergegeven in de e-mail die naar uw gebruikers wordt verzonden.

1. Selecteer in Intune **Apparaatcompatibiliteit** > **Meldingen** > **Melding maken**. 
2. Voer de volgende informatie in:

   - **Naam**: *Beheerder van Contoso*
   - **Onderwerp**: *Apparaatcompatibiliteit*
   - **Bericht**: *Ons apparaat voldoet momenteel niet aan de compatibiliteitsvereisten van onze organisatie.*
   - **E-mailkoptekst - Bedrijfslogo opnemen**: stel in op **Ingeschakeld** om het logo van uw organisatie weer te geven.
   - **E- mailvoettekst -bedrijfsnaam opnemen**: stel in op **Ingeschakeld** om de naam van uw organisatie weer te geven.
   - **E- mailvoettekst -contactgegevens opnemen**: stel in op **Ingeschakeld** om de contactgegevens van uw organisatie weer te geven.

   ![Voorbeeld van een compatibel meldingsbericht in Intune](./media/quickstart-send-notification-01.png)

3. Nadat u klaar bent met het toevoegen van informatie, kiest u **Maken**. De sjabloon voor het meldingsbericht is klaar voor gebruik.

    > [!NOTE]
    > U kunt ook een eerder gemaakte meldingssjabloon bewerken.

Zie [Bedrijfsgegevens en privacyverklaring](company-portal-app.md#company-information-and-privacy-statement), [Ondersteuningsinformatie](company-portal-app.md#support-information), en [Aanpassing huisstijl bedrijfsidentiteit](company-portal-app.md#company-identity-branding-customization) voor meer informatie over het instellen van uw bedrijfsnaam, contactgegevens van bedrijf en uw bedrijfslogo. 

## <a name="add-a-noncompliance-policy"></a>Een beleid voor niet-compatibiliteit toevoegen

Wanneer u een nalevingsbeleid voor apparaten maakt, maakt Intune automatisch een actie voor niet-naleving. Wanneer een apparaat niet voldoet aan uw compatibiliteitsbeleid, wordt het apparaat door Intune als niet-compatibel gemarkeerd. U kunt aanpassen hoe lang het apparaat wordt gemarkeerd als niet-compatibel. U kunt ook nog een actie toevoegen wanneer u een compatibiliteitsbeleid maakt of wanneer u een bestaand compatibiliteitsbeleid bijwerkt. 

Via de volgende stappen kunt u een compatibiliteitsbeleid voor Windows 10-apparaten maken.

1. Selecteer in Intune **Apparaatcompatibiliteit**.
2. Selecteer **Beleid** > **Beleid maken**.
3. Voer de volgende informatie in:

   - **Naam**: *Compatibiliteit met Windows 10*
   - **Beschrijving**: *Compatibiliteitsbeleid van Windows 10*
   - **Platform**: Windows 10 en hoger

4. Selecteer **Instellingen** > **Systeembeveiliging** om de instellingen met betrekking tot de apparaatbeveiliging weer te geven.
5. Stel **Wachtwoord vereisen voor het ontgrendelen van mobiele apparaten** in op **Vereisen**. Met deze beleidsinstelling geeft u aan of gebruikers een wachtwoord moeten invoeren om toegang te krijgen tot informatie op hun mobiele apparaat. 
6. Stel **Minimale wachtwoordlengte** in op **6**. Met deze instelling bepaalt u het minimale aantal cijfers of tekens waaruit het wachtwoord moet bestaan.

    ![Systeembeveiligingsinstellingen voor een nieuw compatibiliteitsbeleid](./media/quickstart-send-notification-02.png) 

7. Klik op **OK**, **OK** en **Maken** om uw compatibiliteitsbeleid te maken.
8. Selecteer de naam van het nieuwe beleid: **Compatibiliteit met Windows 10**.
9. Selecteer **Eigenschappen** > **Actie voor niet-compatibiliteit** > **Toevoegen**.
10. Controleer in de vervolgkeuzelijst **Actie** of **E-mailbericht verzenden naar eindgebruikers** is geselecteerd.
11. Selecteer **Berichtsjabloon** > **Contoso-beheerder** > **Selecteren** om de berichtsjabloon te selcteren die u eerder in dit onderwerp hebt gemaakt.
12. Selecteer **OK** > **OK** > **Opslaan** om uw wijzigingen op te slaan.

## <a name="assign-the-policy"></a>Wijs het beleid toe

U kunt het compatibiliteitsbeleid toewijzen aan een specifieke groep gebruikers of aan alle gebruikers. Wanneer Intune detecteert dat een apparaat niet compatibel is, wordt de gebruiker geïnformeerd dat ze hun apparaat moeten bijwerken om te laten voldoen aan het compatibiliteitsbeleid. Via de volgende stappen kunt u het beleid toewijzen.

1. Selecteer het **Windows 10-compatibiliteitsbeleid** dat u eerder hebt gemaakt.
2. Selecteer **Toewijzingen**.
3. Selecteer in de vervolgkeuzelijst **Toewijzen aan** de optie **Alle gebruikers**. Hiermee worden alle gebruikers geselecteerd. Elke gebruiker die een apparaat heeft met **Windows 10 en hoger** dat niet voldoet aan dit compatibiliteitsbeleid wordt op de hoogte gesteld.

    > [!NOTE]
    > U kunt groepen opnemen en uitsluiten bij het toewijzen van compatibiliteitsbeleid.

4. Klik op **Opslaan**.

Als het beleid is gemaakt en opgeslagen, wordt dit weergegeven in de lijst **Apparaatcompatibiliteit - Beleid**. U ziet in de lijst dat **Toegewezen** is ingesteld op **Ja**.

## <a name="next-steps"></a>Volgende stappen

In deze snelstartgids hebt u Intune gebruikt om een compatibiliteitsbeleid te maken en toe te wijzen voor de Windows 10-apparaten van uw werknemers om een wachtwoord van ten minste zes tekens lang te vereisen. Zie [Een compatibiliteitsbeleid voor Windows-apparaten in Intune toevoegen](compliance-policy-create-windows.md) voor meer informatie over het maken van compatibiliteitsbeleid voor Windows-apparaten.

Als u deze reeks snelstartgidsen voor Intune wilt volgen, kunt u doorgaan met de volgende snelstartgids.

> [!div class="nextstepaction"]
> [Snelstartgids: Een client-app toevoegen en toewijzen](quickstart-add-assign-app.md)
