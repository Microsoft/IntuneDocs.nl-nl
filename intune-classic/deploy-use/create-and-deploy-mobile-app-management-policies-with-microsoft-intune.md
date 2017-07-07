---
title: MAM-beleid maken en implementeren
description: Volg de stapsgewijze instructies in dit onderwerp om beleidsregels voor Mobile App Management te maken en implementeren.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c1b9a343-1737-4a65-a9c6-aca48acad11c
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ebb4b03307f8af7e1390c6db994d3120942fae89
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="create-and-deploy-app-protection-policies-with-microsoft-intune"></a>Beveiligingsbeleid voor apps maken en implementeren met Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

In dit onderwerp wordt het proces beschreven van het maken van beveiligingsbeleid voor apps in **Azure-portal**. Azure Portal is de nieuwe beheerconsole voor het maken van beveiligingsbeleid voor apps. U kunt het beste deze portal gebruiken om beveiligingsbeleid voor apps te maken. Azure Portal ondersteunt de volgende MAM-scenario's:

- Apparaten die zijn ingeschreven in Intune.
- Apparaten die worden beheerd door een externe MDM-oplossing.
- Apparaten die niet worden beheerd door een MDM-oplossing (BYOD).

>[!IMPORTANT]
Houd rekening met het volgende als u momenteel de **Intune-beheerconsole** gebruikt om uw apparaten te beheren:

> * U kunt beveiligingsbeleid voor apps maken dat ondersteuning biedt voor apps voor apparaten die zijn geregistreerd in Intune via de [Intune-beheerconsole](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).
> * Beveiligingsbeleid voor apps gemaakt in de Intune-beheerconsole kan niet worden geïmporteerd in Azure Portal.  Het beveiligingsbeleid voor apps moet opnieuw worden gemaakt in Azure Portal.

> * Mogelijk ziet u in de Intune-beheerconsole niet alle instellingen van het beveiligingsbeleid voor apps. Azure-portal is de nieuwe beheerconsole voor het maken van beveiligingsbeleid voor apps.

> * Voor het implementeren van beheerde apps moet u beveiligingsbeleid voor apps maken in de Intune-beheerconsole. Het kan in dit geval verstandig zijn om beveiligingsbeleid voor apps te maken in zowel de Intune-beheerconsole als Azure-portal: in de Intune-beheerconsole om ervoor te zorgen dat u de mogelijkheid hebt om beheerde apps te implementeren en in Azure-portal omdat dit de nieuwe beheerconsole is die alle instellingen voor beveiligingsbeleid voor apps bevat.

> * Als u beveiligingsbeleid voor apps maakt in zowel de Intune-beheerconsole als Azure-portal, wordt het beleid dat in Azure-portal is gemaakt, toegepast op de apps.

Voor een lijst met beleidsinstellingen die worden ondersteund voor het Android- en iOS-platform, selecteert u een van de volgende mogelijkheden:

> [!div class="op_single_selector"]
- [iOS-beleid](ios-mam-policy-settings.md)
- [Android-beleid](android-mam-policy-settings.md)

- Zie [protect app data using app protection policies](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md) (Appgegevens beveiligen met behulp van beveiligingsbeleid voor apps)voor een gedetailleerde beschrijving van de werking van het beveiligingsbeleid voor apps en de scenario's die worden ondersteund door het Intune-beveiligingsbeleid voor apps.

##  <a name="create-an-app-protection-policy"></a>Beveiligingsbeleid voor apps maken
Beveiligingsbeleid voor apps wordt gemaakt in Azure-Portal. Als dit de eerste keer is dat u Azure-portal gebruikt, lees dan eerst [Azure-portal voor Microsoft Intune-beveiligingsbeleid voor apps](azure-portal-for-microsoft-intune-mam-policies.md) om vertrouwd te raken met Azure-portal. Controleer de [informatie over vereisten en ondersteuning](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md) voordat u beveiligingsbeleid voor apps maakt.

Voer de volgende stappen uit om beveiligingsbeleid voor apps te maken:

1. Ga naar [Azure Portal](https://portal.azure.com) en voer uw referenties in.

2. Kies **Meer services** en voer Intune in.

3. Kies **Intune-app-beveiliging**.

4. Kies **Intune Mobile Application Management &gt; Instellingen** om de blade **Instellingen** te openen.

    ![Schermafbeelding van het tabblad Intune Mobile Application Management](../media/AppManagement/AzurePortal_MAM_Mainblade-2.png)

2.  Kies op de blade **Alle instellingen** de optie **App-beleid**. Hiermee opent u het tabblad **App-beleid**, waar u nieuw beleid kunt maken en bestaande beleidsregels kunt bewerken. Kies **Een beleid toevoegen**.

    ![Schermafbeelding van het tabblad App-beleid met de menuoptie Een beleid toevoegen gemarkeerd ](../media/AppManagement/AzurePortal_MAM_AddPolicy.png)

3.  Geef een naam op voor het beleid, voeg een korte beschrijving toe en selecteer het platformtype om beleidsregels voor iOS of Android te maken. U kunt meer dan één beleid voor elk platform maken.

    ![Schermafbeelding van het tabblad Een beleid toevoegen](../media/AppManagement/AzurePortal_MAM_AddPolicy_only.png)

4.  Kies **Apps** om het tabblad **Apps** te openen, zodat er een lijst met beschikbare apps wordt weergegeven. U kunt een of meer apps in de lijst selecteren die u wilt koppelen aan het beleid dat u maakt. Nadat u de apps hebt geselecteerd, kiest u **Selecteren** onder aan het tabblad **Apps** om uw selectie op te slaan.

    > [!IMPORTANT]
    > U moet ten minste één app selecteren om een beleid maken.

5.  Op het tabblad **Een beleid toevoegen** kiest u **Vereiste instellingen configureren** om het tabblad Beleidsinstellingen te openen.

    Er zijn twee soorten beleidsinstellingen; **Herlocatie van gegevens** en **Toegang**.  Beleid voor herlocatie van gegevens is van toepassing op de verplaatsing van gegevens van en naar de apps, terwijl het toegangsbeleid bepaalt hoe de eindgebruiker in de context van zijn werk toegang tot de apps heeft.
    Om u op gang te hepen, hebben de beleidsinstellingen standaardwaarden. U hoeft niets te wijzigen als de standaardwaarden aan uw vereisten voldoen.

    > [!TIP]
    > Deze beleidsinstellingen worden alleen afgedwongen wanneer u apps in de context van het werk gebruikt.  Als de eindgebruiker de app voor een privétaak gebruikt, worden deze beleidsregels niet toegepast.

    ![Schermafbeelding van het tabblad met instellingen en het tabblad Een beleid toevoegen](../media/AppManagement/AzurePortal_MAM_PolicySettings.png)

6.  Kies **OK** om deze configuratie op te slaan. U bent nu terug op het tabblad **Een beleid toevoegen** . Kies **Maken** om het beleid te maken en uw instellingen op te slaan.

    ![Schermafbeelding van het tabblad Een beleid toevoegen, waarin wordt aangegeven dat de apps en instellingen zijn geconfigureerd](../media/AppManagement/AzurePortal_MAM_CreatePolicy.png)

Wanneer u klaar bent met het maken van een beleid, zoals beschreven in de vorige procedure, is het nog niet geïmplementeerd voor gebruikers. Zie de sectie Een beleid implementeren naar gebruikers hieronder voor het implementeren van een beleid.

> [!IMPORTANT]
> Als u met de Intune-beheerconsole een beveiligingsbeleid voor een app maakt en met Azure-portal een beveiligingsbeleid voor apps, heeft het beleid dat u met Azure-portal hebt gemaakt, prioriteit. In de Intune- of Configuration Manager-console worden echter de beleidsinstellingen gerapporteerd die zijn gemaakt via de Intune-beheerconsole. Bijvoorbeeld:
>
> -   U hebt beveiligingsbeleid voor apps in de Intune-beheerconsole gemaakt waarin het kopiëren vanuit een app wordt geblokkeerd.
> -   U hebt beveiligingsbeleid voor apps in de Azure-console gemaakt waarin het kopiëren vanuit een app is toegestaan.
> -   U koppelt beide sets met beleidsregels aan dezelfde app.
> -   Het beleid dat u hebt gemaakt vanaf de Azure-console krijgt voorrang en kopiëren is toegestaan.
> -   De status en rapporten in de Intune-beheerconsole geven in dat geval echter ten onrechte aan dat kopiëren is geblokkeerd.

## <a name="line-of-business-lob-apps-optional"></a>Line-Of-Business-apps (LOB) (optioneel)

Met ingang van Intune versie 1703 hebt u de optie om LOB-apps toe te voegen in Intune bij het maken van een nieuw app-beveiligingsbeleid. Dat geeft u de optie om een app-beveiligingsbeleid voor LOB-apps te definiëren met de MAM SDK zonder dat u machtigingen voor volledige app-implementatie nodig hebt.
/intune/app-sdk-get-started
> [!TIP]
> U kunt ook LOB-apps toevoegen in Intune wanneer u de werkstroom [Intune App SDK](/intune/app-sdk-get-started) uitvoert.

> [!IMPORTANT]
> Als gebruikers alleen specifieke machtigingen hebben voor het implementeren van MAM-apps en niet voor volledige app-implementatie (waardoor ze iedere app zouden kunnen implementeren in Intune), kunnen ze de Intune SDK-werkstroom niet uitvoeren, maar hun LOB-apps nog steeds toevoegen via de werkstroom voor het maken van een MAM-app-beveiligingsbeleid.

### <a name="to-add-lob-apps-ios-and-android"></a>LOB-apps toevoegen (iOS en Android)

1.  Kies op de blade Een beleid toevoegen **Apps Configureren** om de blade Apps te openen.

    ![MAM-blade Een beleid toevoegen](../media/AppManagement/mam-lob-apps-1.png)

2.  Klik op **Meer apps**, typ de **Bundle ID** (voor iOS), **pakket-id** (voor Android) en klik op Selecteren om uw LOB-apps toe te voegen.

    ![MAM-blade Meer apps](../media/AppManagement/mam-lob-apps-2.png)

### <a name="to-add-lob-apps-windows"></a>LOB-apps toevoegen (Windows)

> [!IMPORTANT]
> Selecteer Windows 10 in de vervolgkeuzelijst wanneer u een nieuwe beleid voor app-beveiliging maakt.

1.  Kies op de blade Een beleid toevoegen de optie **Toegestane apps** of **Vrijgestelde apps** om de blade Toegestane apps of Vrijgestelde apps te openen.

    > [!NOTE]
    >
    - **Toegestane apps**: dit zijn de apps die zich aan dit beleid moeten houden.
    - **Vrijgestelde apps**: deze apps zijn vrijgesteld van dit beleid en hebben zonder beperkingen toegang tot bedrijfsgegevens.
<br></br>
2. Klik op de blade Toegestane of Vrijgestelde apps op **Apps toevoegen**. U kunt aanbevolen Microsoft-apps toevoegen, apps uit de Store of bureaublad-apps.

    a.  **Aanbevolen apps**: een vooraf gevulde lijst met apps (voornamelijk voor Office) die beheerders gemakkelijk in het beleid kunnen importeren.

    b.  **Store-apps**: beheerders kunnen elke app uit de Windows Store toevoegen aan het beleid.

    c.  **Windows-bureaublad-apps**: beheerders kunnen traditionele Windows-bureaublad-apps toevoegen aan het beleid (zoals .exe, .dll, enzovoort).

## <a name="deploy-a-policy-to-users"></a>Een beleid implementeren naar gebruikers

1.  Kies op het tabblad **Beleid** de optie **Gebruikersgroepen**, waarmee het tabblad **Gebruikersgroepen** wordt geopend. Kies **Gebruikersgroep toevoegen** op het tabblad **Gebruikersgroepen** om het tabblad **Gebruikersgroep toevoegen** te openen.

    ![Schermafbeelding van het tabblad Gebruikersgroepen met de menuoptie Gebruikersgroep toevoegen gemarkeerd](../media/AppManagement/AzurePortal_MAM_AddUserstoPolicy.png)

2.  Er wordt een lijst met gebruikersgroepen op het tabblad **gebruikersgroep toevoegen** weergegeven. Dit is een lijst met alle beveiligingsgroepen in uw **Azure Active Directory**. Selecteer de gebruikersgroepen waarop u dit beleid wilt toepassen en kies vervolgens **Selecteren**. Als u **Selecteren** kiest, wordt het beleid bij gebruikers geïmplementeerd.

    ![Schermafbeelding van het tabblad Gebruikersgroep toevoegen waarin de lijst met Azure Active Directory-gebruikers wordt weergegeven](../media/AppManagement/AzurePortal_MAM_SelectUserstoDeploy.png)

    U hebt nu beleid gemaakt en het beleid geïmplementeerd naar gebruikers.

Het beleid is alleen van invloed op gebruikers aan wie Intune-licenties zijn toegewezen. Het beleid is niet van invloed op gebruikers in de geselecteerde beveiligingsgroep aan wie geen Intune-licentie is toegewezen.

>[!IMPORTANT]
> Als u Intune met Configuration Manager gebruik om uw iOS- en Android-apparaten te beheren, wordt het beleid alleen direct op gebruikers in de geselecteerde groep toegepast. Leden van de onderliggende groepen binnen de geselecteerde groep worden niet door het beleid beïnvloed.

Eindgebruikers kunnen de apps downloaden in de App Store of via Google Play. Zie voor meer informatie:
* [Wat u kunt verwachten wanneer uw Android-app wordt beheerd door een app-beveiligingsbeleid](/intune/end-user-mam-apps-android)
* [Wat u kunt verwachten wanneer uw iOS-app wordt beheerd door een app-beveiligingsbeleid](/intune/end-user-mam-apps-ios)

##  <a name="change-existing-policies"></a>Bestaande beleidsregels wijzigen
U kunt een bestaand beleid bewerken en toepassen op de beoogde gebruikers. Wanneer u echter bestaand beleid wijzigt, worden de wijzigingen pas na 8 uur zichtbaar voor gebruikers die al bij de apps zijn aangemeld.

Om het effect van de wijzigingen onmiddellijk te zien, moet de eindgebruiker zich afmelden bij de app en zich daarna opnieuw aanmelden.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>De lijst met aan het beleid gekoppelde apps wijzigen

1.  Kies het beleid dat u wilt wijzigen, op het tabblad **App-beleid**. Hiermee opent u een tabblad dat specifiek is voor het beleid dat u zojuist hebt geselecteerd.

    ![Schermafbeelding van bestaand beleid dat op een afzonderlijk tabblad is geopend](../media/AppManagement/AzurePortal_MAM_OpenPolicy.png)

2.  Kies **Doel-apps** op het tabblad met het beleid om de lijst met apps te openen.

3.  Verwijder apps uit de lijst of voeg ze eraan toe en kies het pictogram **Opslaan** om uw wijzigingen op te slaan.

### <a name="to-change-the-list-of-user-groups"></a>De lijst met gebruikersgroepen wijzigen

1.  Kies het beleid dat u wilt wijzigen, op het tabblad **App-beleid**. Hiermee opent u het tabblad dat specifiek is voor het beleid dat u hebt geselecteerd.

2.  Kies **Gebruikersgroepen** op het tabblad met het beleid om het tabblad **Gebruikersgroep** te openen. Hierin wordt de lijst met huidige gebruikersgroepen weergegeven waarop dit beleid van toepassing is.

3.  Als u een nieuwe gebruikersgroep wilt toevoegen aan het beleid, kiest u **Gebruikersgroep toevoegen** en selecteert u de gebruikersgroep. Kies **Selecteren** om het beleid te implementeren bij de groep die u hebt geselecteerd.

    ![Schermopname van het tabblad Gebruikersgroep toevoegen met twee geselecteerde gebruikersgroepen](../media/AppManagement/AzurePortal_MAM_ChangePolicy_SelectUser.png)

4.  Als u een gebruikersgroep wilt verwijderen, selecteert u de gewenste gebruikersgroep. Kies vervolgens het beletselteken (…) en kies **Verwijderen** om de gebruikersgroep te verwijderen.

    ![Schermopname waarin de optie Verwijderen wordt weergegeven ](../media/AppManagement/AzurePortal_MAM_ChangePolicy_DeleteUser.png)

### <a name="to-change-policy-settings"></a>Beleidsinstellingen wijzigen

1.  Kies het beleid dat u wilt wijzigen, op het tabblad **App-beleid**. Hiermee opent u een tabblad dat specifiek is voor het beleid dat u zojuist hebt geselecteerd.

    ![Schermafbeelding van bestaand beleid dat op een afzonderlijk tabblad is geopend ](../media/AppManagement/AzurePortal_MAM_OpenPolicy.png)

2.  Kies **Beleidsinstellingen** om het tabblad **Beleidsinstellingen** te openen.

3.  Wijzig de instellingen en kies het pictogram **Opslaan** om uw wijzigingen op te slaan.

    ![Schermafbeelding van het tabblad Beleidsinstellingen waarin boven de menuoptie voor opslaan wordt weergegeven](../media/AppManagement/AzurePortal_MAM_ChangePolicy_ChangeSettings.png)

## <a name="policy-settings"></a>Beleidsinstellingen
Selecteer een van de volgende mogelijkheden voor een volledig overzicht van de beleidsinstellingen voor iOS en Android:

> [!div class="op_single_selector"]
- [iOS-beleid](ios-mam-policy-settings.md)
- [Android-beleid](android-mam-policy-settings.md)

## <a name="next-steps"></a>Volgende stappen
[Compatibiliteit- en gebruikersstatus controleren](monitor-mobile-app-management-policies-with-microsoft-intune.md)

### <a name="see-also"></a>Zie tevens
* [Wat u kunt verwachten wanneer uw Android-app wordt beheerd door een app-beveiligingsbeleid](/intune/end-user-mam-apps-android)
* [Wat u kunt verwachten wanneer uw iOS-app wordt beheerd door een app-beveiligingsbeleid](/intune/end-user-mam-apps-ios)
