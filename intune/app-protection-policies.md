---
title: Beveiligingsbeleid voor apps maken en implementeren
titleSuffix: Microsoft Intune
description: Meer informatie over het maken en toewijzen van app-beveiligingsbeleid van Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8ffe409e376ec2d15c537fb6ac258e5b3b71cdf2
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-and-assign-app-protection-policies"></a>App-beveiligingsbeleid maken en toewijzen

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Meer informatie over het maken en toewijzen van app-beveiligingsbeleid van Microsoft Intune aan uw gebruikers. Dit onderwerp beschrijft ook hoe u wijzigingen aanbrengt in bestaande beleidsregels.

## <a name="before-you-begin"></a>Voordat u begint

Zie [Beveiligingsbeleid voor apps maken](https://docs.microsoft.com/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) voor instructies in de klassieke Intune-portal.

App-beveiligingsbeleid kan worden toegepast op apps die worden uitgevoerd op apparaten die al dan niet door Intune worden beheerd. Zie [What is Microsoft Intune app protection policies](app-protection-policy.md) (Wat is app-beveiligingsbeleid van Microsoft Intune) voor een gedetailleerde beschrijving van de werking van het app-beveiligingsbeleid en de scenario's die worden ondersteund door het app-beveiligingsbeleid van Intune.

Zie [MAM apps list (MAM-app-lijst)](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) voor een lijst met ondersteunde MAM-apps.

##  <a name="create-an-app-protection-policy"></a>Beveiligingsbeleid voor apps maken
1. In de workload **Mobiele apps** selecteert u **App-beveiligingsbeleid** in de sectie **Beheren**. Hiermee opent u de details van het **App-beveiligingsbeleid**, waar u nieuw beleid kunt maken en bestaande beleidsregels kunt bewerken.
2. Kies **Een beleid toevoegen**.

   ![Schermafbeelding van de blade ‘Een beleid toevoegen’](./media/app-protection-add-policy.png)

3. Geef een naam op voor het beleid, voeg een korte beschrijving toe en selecteer het platformtype voor uw beleid. Indien nodig, kunt u meer dan één beleid voor elk platform maken.

4. Kies **Apps** om de blade **Apps** te openen, zodat er een lijst met beschikbare apps wordt weergegeven. U kunt een of meer apps in de lijst selecteren die u wilt koppelen aan het beleid dat u maakt.
5. Wanneer u de apps hebt geselecteerd, kiest u **Selecteren** om uw selectie op te slaan.

    > [!IMPORTANT]
    > U moet ten minste één app selecteren om een beleid maken.

6. Kies **Vereiste instellingen configureren** op de blade **Een beleid toevoegen** om **Instellingen te openen**.

   Er zijn twee soorten beleidsinstellingen; **Herlocatie van gegevens** en **Toegang**.  Beleid voor herlocatie van gegevens zijn van toepassing op de verplaatsing van gegevens in en uit de apps. Het toegangsbeleid bepaalt hoe de gebruiker toegang heeft tot de apps in een werkcontext.
   Om u op gang te hepen, hebben de beleidsinstellingen standaardwaarden. U hoeft niets te wijzigen als de standaardwaarden aan uw vereisten voldoen.

   > [!TIP]
   > Deze beleidsinstellingen worden alleen afgedwongen wanneer u apps in de context van het werk gebruikt. Als eindgebruikers de app gebruiken voor een privétaak, worden deze beleidsregels niet toegepast.

7. Kies **OK** om deze configuratie op te slaan. U bent nu terug in het deelvenster **Een beleid toevoegen**. Kies **Maken** om het beleid te maken en uw instellingen op te slaan.
8. Kies **OK** om deze configuratie op te slaan. U bent nu terug in het deelvenster **Een beleid toevoegen**.
9. Kies **Maken** om het beleid te maken en uw instellingen op te slaan.

Wanneer u klaar bent met het maken van een beleid, zoals beschreven in de vorige procedure, is het nog niet geïmplementeerd voor gebruikers. Zie [Een beleid implementeren naar gebruikers](app-protection-policies.md#deploy-a-policy-to-users) voor het implementeren van een beleid.

## <a name="deploy-a-policy-to-users"></a>Een beleid implementeren naar gebruikers


1. Selecteer een beleid in het deelvenster **App-beveiligingsbeleid**.

1. In de deelvenster **Beleid** kiest u **Toewijzingen**, waardoor het deelvenster **Intune-app-beveiliging - Toewijzingen** wordt geopend. Kies **Groepen selecteren om op te nemen** in het deelvenster **Toewijzingen** om het deelvenster **Groepen selecteren om op te nemen** te openen.

   ![Schermafbeelding van het venster Toewijzingen met de optie Groepen selecteren om op te nemen gemarkeerd](./media/app-protection-policy-add-users.png)

2.  Er wordt een lijst met gebruikersgroepen in het deelvenster **Gebruikersgroep toevoegen** weergegeven. Deze lijst geeft alle beveiligingsgroepen in uw **Azure Active Directory** weer. Selecteer de gebruikersgroepen waarop u dit beleid wilt toepassen en kies vervolgens **Selecteren**. Als u **Selecteren** kiest, wordt het beleid bij gebruikers geïmplementeerd.

    ![Schermafbeelding van het deelvenster Gebruikersgroep toevoegen waarin de lijst met Azure Active Directory-gebruikers wordt weergegeven](./media/azure-ad-user-group-list.png)

U hebt nu beleid gemaakt en het beleid geïmplementeerd naar gebruikers.

Het beleid is alleen van invloed op gebruikers aan wie Microsoft Intune-licenties zijn toegewezen. Gebruikers in de geselecteerde beveiligingsgroep aan wie geen Intune-licentie is toegewezen, worden niet beïnvloed.

>[!IMPORTANT]
> Als u Intune met Configuration Manager gebruik om uw apparaten te beheren, wordt het beleid alleen direct op gebruikers in de geselecteerde groep toegepast. Leden van de onderliggende groepen binnen de geselecteerde groep worden niet door het beleid beïnvloed.

Eindgebruikers kunnen de apps downloaden in de App Store of via Google Play. Zie voor meer informatie:
* [Wat u kunt verwachten wanneer uw Android-app wordt beheerd door een app-beveiligingsbeleid](app-protection-enabled-apps-android.md)
* [Wat u kunt verwachten wanneer uw iOS-app wordt beheerd door een app-beveiligingsbeleid](app-protection-enabled-apps-ios.md)

##  <a name="change-existing-policies"></a>Bestaande beleidsregels wijzigen
U kunt een bestaand beleid bewerken en toepassen op de beoogde gebruikers. Wanneer u echter bestaand beleid wijzigt, worden de wijzigingen pas na 8 uur zichtbaar voor gebruikers die al bij de apps zijn aangemeld.

Om het effect van de wijzigingen onmiddellijk te zien, moet de eindgebruiker zich afmelden bij de app en zich daarna opnieuw aanmelden.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>De lijst met aan het beleid gekoppelde apps wijzigen

1.  In het deelvenster **App-beveiligingsbeleid** kiest u het beleid dat u wilt wijzigen om een deelvenster te openen dat specifiek is voor het beleid dat u zojuist hebt geselecteerd.

2.  Kies **Doel-apps** in het deelvenster met beleid om de lijst met apps te openen.

3.  Verwijder apps uit de lijst of voeg ze eraan toe en kies het pictogram **Opslaan** om uw wijzigingen op te slaan.

### <a name="to-change-the-list-of-user-groups"></a>De lijst met gebruikersgroepen wijzigen


1.  In het deelvenster **App-beveiligingsbeleid** kiest u het beleid dat u wilt wijzigen om het deelvenster te openen dat specifiek is voor het beleid dat u hebt geselecteerd.

2.  Kies **Toewijzingen** in het deelvenster voor beleid om het deelvenster **Intune-app-beveiliging - Toewijzingen** te openen waarin de lijst met huidige gebruikersgroepen die dit beleid hebben wordt weergegeven.

3.  Als u een nieuwe gebruikersgroep wilt toevoegen aan het beleid op het tabblad **Opnemen** kiest u **Selecteer groepen om op te nemen** en selecteert u de gebruikersgroep. Kies **Selecteren** om het beleid te implementeren bij de groep die u hebt geselecteerd.

4.  Als u een gebruikersgroep wilt verwijderen, kiest u op het tabblad **Opnemen** **Groepen selecteren om uit te sluiten** en selecteert u de gebruikersgroep. Kies **Selecteren** om de gebruikersgroep te verwijderen.

### <a name="to-change-policy-settings"></a>Beleidsinstellingen wijzigen

1.  In het deelvenster **App-beveiligingsbeleid** kiest u het beleid dat u wilt wijzigen om een deelvenster te openen dat specifiek is voor het beleid dat u zojuist hebt geselecteerd.

2.  Kies **Beleidsinstellingen** om het deelvenster **Beleidsinstellingen** te openen.

3.  Wijzig de instellingen en kies het pictogram **Opslaan** om uw wijzigingen op te slaan.

## <a name="target-app-protection-policies-based-on-device-management-state"></a>Beleidsregels voor app-beveiliging toepassen op basis van de apparaatbeheerstatus
In veel organisaties is het gebruikelijk dat eindgebruikers gebruik mogen maken van via Intune MDM (Mobile Device Management) beheerde apparaten zoals apparaten in eigendom van het bedrijf, en van niet-beheerde apparaten die alleen door Intune-app-beveiligingsbeleid worden beschermd zoals BYO-apparaten.

Omdat Intune-app-beveiligingsbeleid op de identiteit van een gebruiker is gericht, worden de beveiligingsinstellingen voor een gebruiker van oudsher op zowel ingeschreven (via MDM beheerde) als niet-ingeschreven apparaten (geen MDM) toegepast. Daarom kunt u Intune-app-beveiligingsbeleid richten op ofwel in Intune ingeschreven apparaten of iOS- en Android-apparaten waarvan de registratie ongedaan is gemaakt. U mag één beveiligingsbeleid voor niet-beheerde apparaten hebben waarin strenge DLP-besturingselementen voor preventie van gegevensverlies zijn toegepast, en een afzonderlijk beveiligingsbeleid voor via MDM beheerde apparaten waarbij minder strenge DLP-besturingselementen mogelijk zijn. 

Voor het maken van deze beleidsregels bladert u naar **Mobiele apps** > **App-beveiliging**-beleid in de Intune-console en klikt u op **Beleid toevoegen**. U kunt ook een bestaand app-beveiligingsbeleid bewerken. Als u het app-beveiligingsbeleid op zowel beheerde als niet-beheerde apparaten wilt toepassen, moet u bevestigen dat **Op alle app-typen toepassen** is ingesteld op **Ja**, de standaardwaarde. Als u granulair wilt toewijzen op basis van de beheerstatus, stelt u de optie **Op alle app-typen toepassen** in op **Nee**. 

> [!NOTE]
> Zie [MAM-beveiligingsbeleid toepassen op basis van beheerstatus](whats-new.md#mam-protection-policies-targeted-based-on-management-state----1665993---) voor specifieke iOS-ondersteuningsinformatie over app-beveiligingsbeleid op basis van de apparaatbeheerstatus.

## <a name="policy-settings"></a>Beleidsinstellingen
Selecteer een van de volgende links voor een volledig overzicht van de beleidsinstellingen voor iOS en Android:

- [iOS-beleid](app-protection-policy-settings-ios.md)
- [Android-beleid](app-protection-policy-settings-android.md)

## <a name="next-steps"></a>Volgende stappen
[Compatibiliteit- en gebruikersstatus controleren](app-protection-policies-monitor.md)

### <a name="see-also"></a>Zie tevens
* [Wat u kunt verwachten wanneer uw Android-app wordt beheerd door een app-beveiligingsbeleid](app-protection-enabled-apps-android.md)
* [Wat u kunt verwachten wanneer uw iOS-app wordt beheerd door een app-beveiligingsbeleid](app-protection-enabled-apps-ios.md)
