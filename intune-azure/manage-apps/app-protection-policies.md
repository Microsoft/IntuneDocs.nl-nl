---
title: Beveiligingsbeleid voor apps maken en implementeren
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: meer informatie over hoe het app-beveiligingsbeleid van Intune kan helpen bij de beveiliging van bedrijfsgegevens die worden gebruikt door apps die u beheert.'
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: 119c7172f8175d128c3e13d37bb9ec3c91719bcf
ms.contentlocale: nl-nl
ms.lasthandoff: 05/10/2017

---

# <a name="how-to-create-and-assign-app-protection-policies"></a>App-beveiligingsbeleid maken en toewijzen

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

**Als u zich niet in de Intune-service in de preview-versie van Azure Portal bevindt**, wordt in dit onderwerp uitgelegd hoe u een [app-beveiligingsbeleid kunt maken](https://docs.microsoft.com/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) in de klassieke Intune-console.

App-beveiligingsbeleid kan worden toegepast op apps die worden uitgevoerd op apparaten die al dan niet door Intune worden beheerd. Zie [What is Microsoft Intune app protection policies](what-is-app-protection-policy.md) (Wat is app-beveiligingsbeleid van Microsoft Intune) voor een gedetailleerde beschrijving van de werking van het app-beveiligingsbeleid en de scenario's die worden ondersteund door het app-beveiligingsbeleid van Intune.

##  <a name="create-an-app-protection-policy"></a>Beveiligingsbeleid voor apps maken
1.  Kies **Beheren** > **App-beveiligingsbeleid** in de workload **Mobiele apps**.

2.  Hiermee opent u de blade **App-beveiligingsbeleid**, waar u nieuw beleid kunt maken en bestaande beleidsregels kunt bewerken. Kies **Een beleid toevoegen**.

  ![Schermafbeelding van het tabblad Een beleid toevoegen](../media/app-protection-add-policy.png)

3.  Geef een naam op voor het beleid, voeg een korte beschrijving toe en selecteer het platformtype om beleidsregels voor iOS of Android te maken. U kunt meer dan één beleid voor elk platform maken.

4.  Kies **Apps** om het tabblad **Apps** te openen, zodat er een lijst met beschikbare apps wordt weergegeven. U kunt een of meer apps in de lijst selecteren die u wilt koppelen aan het beleid dat u maakt. Nadat u de apps hebt geselecteerd, kiest u **Selecteren** onder aan het tabblad **Apps** om uw selectie op te slaan.

    > [!IMPORTANT]
    > U moet ten minste één app selecteren om een beleid maken.

5.  Op het tabblad **Een beleid toevoegen** kiest u **Vereiste instellingen configureren** om het tabblad Beleidsinstellingen te openen.

    Er zijn twee soorten beleidsinstellingen; **Herlocatie van gegevens** en **Toegang**.  Beleid voor herlocatie van gegevens is van toepassing op de verplaatsing van gegevens van en naar de apps, terwijl het toegangsbeleid bepaalt hoe de eindgebruiker in de context van zijn werk toegang tot de apps heeft.
    Om u op gang te hepen, hebben de beleidsinstellingen standaardwaarden. U hoeft niets te wijzigen als de standaardwaarden aan uw vereisten voldoen.

    > [!TIP]
    > Deze beleidsinstellingen worden alleen afgedwongen wanneer u apps in de context van het werk gebruikt.  Als de eindgebruiker de app voor een privétaak gebruikt, worden deze beleidsregels niet toegepast.



6.  Kies **OK** om deze configuratie op te slaan. U bent nu terug op het tabblad **Een beleid toevoegen** . Kies **Maken** om het beleid te maken en uw instellingen op te slaan.


Wanneer u klaar bent met het maken van een beleid, zoals beschreven in de vorige procedure, is het nog niet geïmplementeerd voor gebruikers. Zie de sectie Een beleid implementeren naar gebruikers hieronder voor het implementeren van een beleid.

## <a name="deploy-a-policy-to-users"></a>Een beleid implementeren naar gebruikers

1.  Kies op het tabblad **Beleid** de optie **Gebruikersgroepen**, waarmee het tabblad **Gebruikersgroepen** wordt geopend. Kies **Gebruikersgroep toevoegen** op het tabblad **Gebruikersgroepen** om het tabblad **Gebruikersgroep toevoegen** te openen.

  ![Schermafbeelding van het tabblad Gebruikersgroepen met de menuoptie Gebruikersgroep toevoegen gemarkeerd](../media/app-protection-policy-add-users.png)

2.  Er wordt een lijst met gebruikersgroepen op het tabblad **gebruikersgroep toevoegen** weergegeven. Dit is een lijst met alle beveiligingsgroepen in uw **Azure Active Directory**. Selecteer de gebruikersgroepen waarop u dit beleid wilt toepassen en kies vervolgens **Selecteren**. Als u **Selecteren** kiest, wordt het beleid bij gebruikers geïmplementeerd.
  ![Schermafbeelding van de blade Gebruikersgroep toevoegen waarop de lijst met Azure Active Directory-gebruikers wordt weergegeven](../media/azure-ad-user-group-list.png)

U hebt nu beleid gemaakt en het beleid geïmplementeerd naar gebruikers.

Het beleid is alleen van invloed op gebruikers aan wie Microsoft Intune-licenties zijn toegewezen. Gebruikers die zich in de geselecteerde beveiligingsgroep bevinden en aan wie geen Microsoft Intune-licentie is toegewezen, worden niet door het beleid beïnvloed.

>[!IMPORTANT]
> Als u Intune met Configuration Manager gebruik om uw iOS- en Android-apparaten te beheren, wordt het beleid alleen direct op gebruikers in de geselecteerde groep toegepast. Leden van de onderliggende groepen binnen de geselecteerde groep worden niet door het beleid beïnvloed.

Eindgebruikers kunnen de apps downloaden in de App Store of via Google Play. Zie voor meer informatie:
* [Wat u kunt verwachten wanneer uw Android-app wordt beheerd door een app-beveiligingsbeleid](app-protection-enabled-android-apps.md)
* [Wat u kunt verwachten wanneer uw iOS-app wordt beheerd door een app-beveiligingsbeleid](app-protection-enabled-ios-apps.md)

##  <a name="change-existing-policies"></a>Bestaande beleidsregels wijzigen
U kunt een bestaand beleid bewerken en toepassen op de beoogde gebruikers. Wanneer u echter bestaand beleid wijzigt, worden de wijzigingen pas na 8 uur zichtbaar voor gebruikers die al bij de apps zijn aangemeld.

Om het effect van de wijzigingen onmiddellijk te zien, moet de eindgebruiker zich afmelden bij de app en zich daarna opnieuw aanmelden.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>De lijst met aan het beleid gekoppelde apps wijzigen

1.  Kies het beleid dat u wilt wijzigen, op het tabblad **App-beleid**. Hiermee opent u een tabblad dat specifiek is voor het beleid dat u zojuist hebt geselecteerd.

2.  Kies **Doel-apps** op het tabblad met het beleid om de lijst met apps te openen.

3.  Verwijder apps uit de lijst of voeg ze eraan toe en kies het pictogram **Opslaan** om uw wijzigingen op te slaan.

### <a name="to-change-the-list-of-user-groups"></a>De lijst met gebruikersgroepen wijzigen

1.  Kies het beleid dat u wilt wijzigen, op het tabblad **App-beleid**. Hiermee opent u het tabblad dat specifiek is voor het beleid dat u hebt geselecteerd.

2.  Kies **Gebruikersgroepen** op het tabblad met het beleid om het tabblad **Gebruikersgroep** te openen. Hierin wordt de lijst met huidige gebruikersgroepen weergegeven waarop dit beleid van toepassing is.

3.  Als u een nieuwe gebruikersgroep wilt toevoegen aan het beleid, kiest u **Gebruikersgroep toevoegen** en selecteert u de gebruikersgroep. Kies **Selecteren** om het beleid te implementeren bij de groep die u hebt geselecteerd.

4.  Als u een gebruikersgroep wilt verwijderen, selecteert u de gewenste gebruikersgroep. Kies vervolgens het beletselteken (…) en kies **Verwijderen** om de gebruikersgroep te verwijderen.
  ![Schermafbeelding waarin de optie Verwijderen wordt weergegeven ](../media/app-protection-policy-delete-user.png)

### <a name="to-change-policy-settings"></a>Beleidsinstellingen wijzigen

1.  Kies het beleid dat u wilt wijzigen, op het tabblad **App-beleid**. Hiermee opent u een tabblad dat specifiek is voor het beleid dat u zojuist hebt geselecteerd.


2.  Kies **Beleidsinstellingen** om het tabblad **Beleidsinstellingen** te openen.

3.  Wijzig de instellingen en kies het pictogram **Opslaan** om uw wijzigingen op te slaan.

## <a name="policy-settings"></a>Beleidsinstellingen
Selecteer een van de volgende mogelijkheden voor een volledig overzicht van de beleidsinstellingen voor iOS en Android:

> [!div class="op_single_selector"]
- [iOS-beleid](ios-app-protection-policy-settings.md)
- [Android-beleid](android-app-protection-policy-settings.md)

## <a name="next-steps"></a>Volgende stappen
[Compatibiliteit- en gebruikersstatus controleren](monitor-app-protection-policies-with-microsoft-intune.md)

### <a name="see-also"></a>Zie tevens
* [Wat u kunt verwachten wanneer uw Android-app wordt beheerd door een app-beveiligingsbeleid](app-protection-enabled-android-apps.md)
* [Wat u kunt verwachten wanneer uw iOS-app wordt beheerd door een app-beveiligingsbeleid](app-protection-enabled-ios-apps.md)

