---
title: 'Snelstart: Een e-mailprofiel voor apparaten maken voor iOS/iPadOS'
titleSuffix: Microsoft Intune
description: Ontdek hoe u Microsoft Intune gebruikt om een e-mailprofiel voor apparaten te maken, zodat iOS/iPadOS-apparaten veilig verbinding kunnen maken met de e-mail van het bedrijf.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/18/2020
ms.topic: quickstart
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: af2576c44e0486dbd859a56896db3b7d0ffc6cff
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77511065"
---
# <a name="quickstart-create-an-email-device-profile-for-iosipados"></a>Quickstart: Een e-mailprofiel voor een apparaat maken voor iOS/iPadOS

In deze snelstartgids wordt beschreven hoe u een e-mailprofiel voor apparaten maakt voor iOS/iPadOS-apparaten. In dit profiel worden de instellingen opgegeven die vereist zijn voor de ingebouwde e-mail-app op het iOS/iPadOS-apparaat om verbinding maken met de bedrijfse-mail. E-mailprofielen voor apparaten zorgen voor uniforme instellingen bij een verzameling apparaten en ze stellen eindgebruikers in staat om op hun apparaten toegang te krijgen tot de e-mail van het bedrijf zonder dat ze daarvoor iets hoeven in te stellen. Als u uw e-mail nog verder wilt beveiligen, kunt u een e-mailprofiel gebruiken om te bepalen of apparaten aan het beleid voldoen en kunt u vervolgens voorwaardelijke toegang instellen, zodat alleen apparaten die aan het beleid voldoen toegang krijgen tot de e-mail. Zie [E-mailinstellingen configureren in Microsoft Intune](email-settings-configure.md) voor meer informatie over e-mailprofielen

Als u niet over een Intune-abonnement beschikt, kunt u [zich registreren voor een gratis proefaccount](../fundamentals/free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Aanmelden bij Intune

Meld u bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) aan als een globale beheerder of een Intune-servicebeheerder. Als u een Intune-proefabonnement hebt gemaakt, is het account waarmee u het abonnement hebt gemaakt de globale beheerder.

## <a name="create-an-iosipados-email-profile"></a>Een e-mailprofiel voor iOS/iPadOS maken

1. Selecteer **Apparaten** > **Configuratieprofielen** > **Profiel maken**.

   ![Een e-mailprofiel voor iOS/iPadOS maken in Intune](./media/quickstart-email-profile/ios-create-profile.png)

2. Voer onder **Naam** een beschrijvende naam in voor het nieuwe profiel. Voor dit voorbeeld voert u **iOS vereist zakelijk e-mailadres** in.
3. Voer de volgende profielgegevens in:
    - Voer voor **Beschrijving** de tekst **Vereisen dat iOS/iPadOS-apparaten het zakelijke e-mailadres gebruiken** in.
    - Voor **Platform**, selecteer **iOS/iPadOS**.
    - Selecteer voor **Profieltype** de optie **E-mail**.

        ![Een e-mailprofiel voor iOS/iPadOS-apparaten in Intune maken](./media/quickstart-email-profile/ios-email-profile-name.png)

4. Selecteer **Instellingen** en voer de volgende instellingen in (handhaaf de standaardwaarden voor andere instellingen):
   - **E-mailserver**: voor deze snelstart voert u **outlook.office365.com** in. Met deze instelling wordt de Exchange-locatie (URL) opgegeven van de e-mailserver die de iOS/iPadOS-app voor e-mail gebruikt om verbinding te maken voor de e-mail.
   - **Accountnaam**: voer **het e-mailadres van het bedrijf** in.
   - **Het kenmerk Gebruikersnaam van AAD**: deze naam is het kenmerk dat Intune uit Azure Active Directory (Azure AD) ophaalt. In Intune wordt de gebruikersnaam voor dit profiel dynamisch gegenereerd met deze naam. Voor deze snelstartgids gaan we ervan uit dat we de **user principal name** gebruiken als de gebruikersnaam voor het profiel (bijvoorbeeld user1@contoso.com).
   - **Kenmerk van het e-mailadres van AAD**: deze instelling is het e-mailadres van Azure AD dat wordt gebruikt voor aanmelding bij Exchange. Selecteer voor deze snelstartgids **User principal name**.
   - **Verificatiemethode**: selecteer voor deze snelstart **Gebruikersnaam en wachtwoord**. (U kunt ook **Certificaat** kiezen als u al een certificaat hebt ingesteld voor Intune.)

        ![Een e-mailprofiel voor gebruik met iOS/iPadOS maken](./media/quickstart-email-profile/ios-email-profile.png)

5. Selecteer **OK** > **Maken**. Het nieuwe profiel wordt weergegeven in de lijst met profielen terwijl het dashboard wordt weergegeven, zodat u kunt controleren hoe het profiel is toegewezen aan iOS/iPadOS-apparaten en iOS/iPadOS-gebruikers.
6. Selecteer **Toewijzingen**.
7. Selecteer het tabblad **Opnemen** en vervolgens **Alle gebruikers en alle apparaten**. 
8. Selecteer **Opslaan**.

## <a name="clean-up-resources"></a>Resources opschonen

Als u niet van plan bent om het profiel dat u hebt gemaakt te gebruiken voor aanvullende zelfstudies of testen, kunt u dit nu verwijderen.

1. Selecteer in Intune de optie **Apparaatconfiguratie** en vervolgens **Profielen**.
2. Selecteer het testprofiel dat u hebt gemaakt, **iOS/iPadOS vereist zakelijk e-mailadres**.
3. Selecteer de beletselteken ( **...** ) naast het profiel en selecteer vervolgens **Verwijderen**.

## <a name="next-steps"></a>Volgende stappen

In deze quickstart hebt u een e-mailprofiel voor iOS/iPadOS-apparaten gemaakt. U kunt nu met dit profiel bepalen of een iOS/iPadOS-apparaat voldoet aan het beleid door een nalevingsbeleid te maken, waarbij alle iOS/iPadOS-apparaten die niet overeenkomen met het profiel als niet-compatibel worden gemarkeerd. Als u uw e-mail nog verder wilt beveiligen, kunt u een beleid voor voorwaardelijke toegang maken, zodat niet-compatibele iOS/iPadOS-apparaten geen toegang krijgen tot de e-mail. Zie [Aan de slag met apparaatnalevingsbeleid](../protect/device-compliance-get-started.md) voor meer informatie over beleidsregels voor apparaatnaleving.

> [!div class="nextstepaction"]
> [Zelfstudie: Exchange Online e-mail beschermen op beheerde apparaten](../tutorial-protect-email-on-enrolled-devices.md)
