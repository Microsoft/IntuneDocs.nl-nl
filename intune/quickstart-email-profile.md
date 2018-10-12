---
title: 'Snelstartgids: een e-mailprofiel voor apparaten maken voor iOS'
titlesuffix: Microsoft Intune
description: Ontdek hoe u Microsoft Intune gebruikt om een e-mailprofiel voor apparaten te maken, zodat iOS-apparaten veilig verbinding kunnen maken met de e-mail van het bedrijf.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 09/21/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a0c554315168147249e0842b69e3e6195ed85979
ms.sourcegitcommit: 27eed5aba5c8bfafb079171081b68f75a6cbffaf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2018
ms.locfileid: "46581594"
---
# <a name="quickstart-create-an-email-device-profile-for-ios"></a>Snelstartgids: een e-mailprofiel voor apparaten maken voor iOS

In deze snelstartgids wordt beschreven hoe u een e-mailprofiel voor apparaten maakt voor iOS-apparaten. In dit profiel worden de instellingen opgegeven die vereist zijn voor de ingebouwde e-mail-app op het iOS-apparaat om verbinding maken met de e-mail van het bedrijf. E-mailprofielen voor apparaten zorgen voor uniforme instellingen bij een verzameling apparaten en ze stellen eindgebruikers in staat om op hun apparaten toegang te krijgen tot de e-mail van het bedrijf zonder dat ze daarvoor iets hoeven in te stellen. Als u uw e-mail nog verder wilt beveiligen, kunt u een e-mailprofiel gebruiken om te bepalen of apparaten aan het beleid voldoen en kunt u vervolgens voorwaardelijke toegang instellen, zodat alleen apparaten die aan het beleid voldoen toegang krijgen tot de e-mail. Zie [E-mailinstellingen configureren in Microsoft Intune](email-settings-configure.md) voor meer informatie over e-mailprofielen

Als u niet over een Intune-abonnement beschikt, kunt u [zich aanmelden voor een gratis proefaccount](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Aanmelden bij Intune

Meld u aan bij [Intune](https://aka.ms/intuneportal) als globale beheerder of beheerder van een Intune-service. U gaat in Azure Portal naar Intune door **Alle services** > **Intune** te kiezen.

## <a name="create-an-ios-email-profile"></a>Een e-mailprofiel voor iOS maken
1. Selecteer in Intune de optie **Apparaatconfiguratie** en vervolgens **Profielen**.
2. Selecteer **Profiel maken**.
   
   ![Een e-mailprofiel voor iOS maken](media/quickstart-email-profile/ios-create-profile.png)

3. Voer onder **Naam** een beschrijvende naam in voor het nieuwe profiel. Voor dit voorbeeld voert u **iOS vereist zakelijk e-mailadres** in.
4. Voer de volgende profielgegevens in:
   - Voer voor **Beschrijving** de tekst **Vereisen dat iOS-apparaten het zakelijke e-mailadres gebruiken** in.
   - Selecteer voor **Platform** de optie **iOS**.
   - Selecteer voor **Profieltype** de optie **E-mail**.
    
     ![Een e-mailprofiel voor iOS maken](media/quickstart-email-profile/ios-email-profile-name.png)

5. Selecteer **Instellingen** en voer de volgende instellingen in (handhaaf de standaardwaarden voor andere instellingen):
   - **E-mailserver**: voor deze snelstartgids voert u **outlook.office365.com** in. Met deze instelling wordt de Exchange-locatie (URL) opgegeven van de e-mailserver die de iOS-app voor e-mail gebruikt om verbinding te maken voor de e-mail.
   - **Accountnaam**: voer **E-mail van bedrijf** in.
   - **Het kenmerk Gebruikersnaam van AAD**: deze naam is het kenmerk dat Intune ontvangt van Azure Active Directory (Azure AD). In Intune wordt de gebruikersnaam voor dit profiel dynamisch gegenereerd met deze naam. Voor deze snelstartgids gaan we ervan uit dat we de **user principal name** gebruiken als de gebruikersnaam voor het profiel (bijvoorbeeld user1@contoso.com).
   - **Het kenmerk E-mailadres van AAD**: deze instelling is het e-mailadres van Azure AD dat wordt gebruikt voor aanmelding bij Exchange. Selecteer voor deze snelstartgids **User principal name**.
   - **Verificatiemethode**: selecteer voor deze snelstartgids **Gebruikersnaam en wachtwoord**. (U kunt ook **Certificaat** kiezen als u al een certificaat hebt ingesteld voor Intune.)
    
     ![Een e-mailprofiel voor iOS maken](media/quickstart-email-profile/ios-email-profile.png)

6. Selecteer **OK**.
7. Selecteer **Maken**. Het nieuwe profiel wordt weergegeven in de lijst met profielen terwijl het dashboard wordt weergegeven, zodat u kunt controleren hoe het profiel is toegewezen aan iOS-apparaten en iOS-gebruikers.
8. Selecteer **Toewijzingen**.
9. Selecteer het tabblad **Opnemen** en vervolgens **Alle gebruikers en alle apparaten**. 
10. Selecteer **Opslaan**.

## <a name="clean-up-resources"></a>Resources opschonen
Als u niet van plan bent om het profiel dat u hebt gemaakt te gebruiken voor aanvullende zelfstudies of testen, kunt u dit nu verwijderen.
1. Selecteer in Intune de optie **Apparaatconfiguratie** en vervolgens **Profielen**.
2. Selecteer het testprofiel dat u hebt gemaakt, **iOS vereist zakelijk e-mailadres**.
3. Selecteer de beletselteken (**...**) naast het profiel en selecteer vervolgens **Verwijderen**.

## <a name="next-steps"></a>Volgende stappen

In deze snelstartgids hebt u een e-mailprofiel voor iOS-apparaten gemaakt. U kunt nu met dit profiel bepalen of een iOS-apparaat voldoet aan het beleid door een nalevingsbeleid te maken, waarbij alle iOS-apparaten die niet overeenkomen met het profiel als niet-compatibel worden gemarkeerd. Als u uw e-mail nog verder wilt beveiligen, kunt u een beleid voor voorwaardelijke toegang maken, zodat niet-compatibele apparaten geen toegang krijgen tot de e-mail.

> [!div class="nextstepaction"]
> [Aan de slag met apparaatnalevingsbeleid in Intune](device-compliance-get-started.md)
