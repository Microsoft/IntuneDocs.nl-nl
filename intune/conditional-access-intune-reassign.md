---
title: Beleid voor voorwaardelijke toegang migreren van de klassieke Intune-portal naar de nieuwe Azure-portal.
titleSuffix: Intune on Azure
description: Beleid voor voorwaardelijke toegang migreren van de klassieke Intune-portal naar de nieuwe Azure-portal.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 301159ad-5f7e-4fcc-86c7-f72a71701ff4
ms.reviewer: chrisgree
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2450a878424d8c992a43e8028ba59b7136e1d530
ms.sourcegitcommit: fd5b7aa26446d2fa92c21638cb29371e43fe169f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/06/2017
---
# <a name="reassign-conditional-access-policies-from-intune-classic-portal-to-the-new-azure-portal"></a>Beleid voor voorwaardelijke toegang vanuit de klassieke Intune-portal overbrengen naar de nieuwe Azure-portal

Met de introductie van de nieuwe Azure-portal biedt de functie voor voorwaardelijke toegang ondersteuning voor meerdere beleidsregels per toepassing. Daarnaast zijn er nu ook meer aanpassingsmogelijkheden.

## <a name="before-you-begin"></a>Voordat u begint

Als u klaar bent om aan de slag te gaan met de nieuwe Azure-portal, kunt u de onderstaande stappen volgen om de beleidsregels voor voorwaardelijke toegang te migreren die eerder zijn gemaakt in de klassieke Intune-portal:

- De beleidsregels voor voorwaardelijke toegang verzamelen die eerder zijn gemaakt in de klassieke Intune-portal, zodat u weet welke instellingen u later opnieuw moet toewijzen.

- De stappen in dit onderwerp volgen om deze beleidsregels opnieuw te maken in de nieuwe Azure-portal.

- De beleidsregels voor voorwaardelijke toegang uitschakelen in de klassieke Intune-beheerconsole, nadat u hebt gecontroleerd of de nieuwe beleidsregels naar behoren werken in de nieuwe Azure-portal.
<br /><br />
    - Voordat u de beleidsregels voor voorwaardelijke toegang **uitschakelt in de klassieke Intune-portal**, moet u een plan opstellen voor het overbrengen van gebruikers naar het nieuwe beleid. Er zijn twee manieren:
<br /><br />
        - **Gebruik dezelfde insluitingsgroep om beleid toe te passen dat is gemaakt in de nieuwe Azure-portal, en maak een nieuwe uitsluitingsgroep voor gebruik met de beleidsregels die worden toegepast door de klassieke Intune-portal**.
            - Verplaats steeds kleine aantallen gebruikers naar de uitsluitingsgroep die is opgegeven in de klassieke portal.  Hiermee voorkomt u dat de beleidsregels van de klassieke Intune-portal op deze gebruikers worden toegepast. Het beleid dat is gemaakt en gericht op dezelfde gebruikersgroep in de nieuwe Azure-portal, wordt toegepast in aanvulling op het beleid van de klassieke Intune-portal. 
<br /><br />
        - **Maak een nieuwe groep voor het beleid voor voorwaardelijke toegang van de nieuwe Azure-portal**. Als u deze aanpak kiest, moet u het volgende doen:
            - Gebruikers geleidelijk verwijderen uit de beveiligingsgroepen waarop beleid voor voorwaardelijke toegang uit de klassieke Intune-portal is toegepast.
            - Zodra u hebt vastgesteld dat het nieuwe beleid werkt voor deze gebruikers, kunt u het beleid uitschakelen in de klassieke Intune-portal. 
<br /><br />
- Als het beleid voor voorwaardelijke toegang in de klassieke Intune-portal is geconfigureerd voor gebruik van Exchange Active Sync (EAS) , volgt u [de instructies in dit onderwerp](#to-reassign-intune-device-based-conditional-access-policies-for-eas-clients) om **de EAS-beleidsinstellingen voor voorwaardelijke toegang toe te wijzen in de nieuwe Azure-portal**.

### <a name="to-verify-your-device-based-conditional-access-policies-in-the-intune-classic-portal"></a>Op apparaat gebaseerd beleid voor voorwaardelijke toegang controleren in de klassieke Intune-portal

1.  Ga naar de [klassieke Intune-portal](https://manage.microsoft.com) en meld u aan.

2.  Kies **Beleid** in het menu aan de linkerkant.

3.  Kies **Voorwaardelijke toegang** en selecteer vervolgens de Microsoft-cloudservice (zoals Exchange Online of SharePoint Online) waarvoor u beleid voor voorwaardelijke toegang hebt opgesteld.

4.  Noteer de instellingen voor voorwaardelijke toegang en gebruik deze notities om hetzelfde toegangsbeleid te maken in de nieuwe Azure-portal.

### <a name="app-and-device-based-conditional-access-policies-working-together"></a>Beleid voor voorwaardelijke toegang op basis van app en apparaat combineren

Via de blade **Intune-app-beveiliging** in de nieuwe Azure-portal kunnen beheerders app-gebaseerde regels voor voorwaardelijke toegang instellen, zodat alleen apps die ondersteuning bieden voor Intune-app-beveiligingsbeleid toegang hebben tot bedrijfsresources. U kunt deze app-gebaseerde beleidsregels voor voorwaardelijke toegang laten overlappen met apparaat-gebaseerd beleid voor voorwaardelijke toegang. Dit kan door de apparaat- en app-beleidsregels voor voorwaardelijke toegang te combineren (logische EN) of door een keuze te bieden (logische OF). Het werkt als volgt:

- Vereisen dat het apparaat compatibel is **EN** dat een goedgekeurde app wordt gebruikt.
    - U moet het beleid voor voorwaardelijke toegang instellen met de blade [Voorwaardelijke toegang van Azure AD](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) en de blade [Intune-app-beveiliging](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).
<br /><br />
- Vereisen dat het apparaat compatibel is **OF** dat een goedgekeurde app wordt gebruikt.
    - U moet het beleid voor voorwaardelijke toegang instellen met de [klassieke Intune-portal](https://manage.microsoft.com) en de blade [Intune-app-beveiliging](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).

> [!TIP] 
> Dit onderwerp bevat schermafbeeldingen die de gebruikerservaring laten zien in zowel de klassieke Intune-portal als de nieuwe Azure-portal.

## <a name="to-re-assign-intune-device-based-conditional-access-policies"></a>Beleid voor voorwaardelijke toegang op basis van apparaat opnieuw toewijzen

1. Ga naar [Voorwaardelijke toegang in de nieuwe Azure-portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) en meld u aan.

2. Kies **Nieuw beleid**.

3. Geef een naam voor het beleid op.

4. Kies **Gebruikers en groepen** in de sectie **Toewijzingen** om de doelgroep voor het nieuwe beleid voor voorwaardelijke toegang te bepalen.
    
    ![Vergelijking van de gebruikersinterface voor gebruikersgroepen in de klassieke Intune-portal en de nieuwe Azure-portal](./media/reassign-ca-1.png)

    > [!IMPORTANT] 
    > Als de optie Alle gebruikers is geselecteerd in de klassieke Intune-portal, selecteert u Alle gebruikers. Hetzelfde geldt voor groepen. Als u groepen hebt geselecteerd, moet u **Gebruikers en groepen selecteren** kiezen om die groepen op te nemen. Als u bovendien de optie **Groepen uitsluiten** hebt gekozen in de klassieke Intune-portal, moet u de betreffende groepen uitsluiten in de nieuwe Azure-portal.

5. Nadat u uw groep hebt gekozen, klikt u op **Selecteren** en vervolgens op **Gereed**.

6. Kies **Cloud-apps** in de sectie **Toewijzingen**.

7. Kies **Apps selecteren** op de blade **Cloud-apps**.

8. Kies de app waarop u het nieuwe beleid voor voorwaardelijke toegang wilt toepassen en klik op **Selecteren**.

9. Klik op **Gereed**.

    ![Vergelijking van de gebruikersinterface voor cloud-apps in de klassieke Intune-portal en de nieuwe Azure-portal](./media/reassign-ca-3.png)

    > [!TIP] 
    > Als u meerdere apps met hetzelfde beleid hebt, kunt u overwegen de apps in één beleid onder te brengen in de nieuwe Azure-portal.

10. Kies **Voorwaarden** in de sectie **Toewijzingen**.

11. Kies **Apparaatplatformen** op de blade **Voorwaarden** en kies vervolgens de gewenste apparaatplatformen.

12. Als u dat hebt gedaan, klikt u twee keer achter elkaar op **Gereed**.

    ![Vergelijking van de gebruikersinterface voor apparaatplatformen in de klassieke Intune-portal en de nieuwe Azure-portal](./media/reassign-ca-4.png)

    > [!TIP] 
    > Als u afzonderlijke platformen hebt gekozen in de klassieke Intune-portal, kiest u deze platformen in de nieuwe Azure-portal.

    > [!NOTE] 
    > U kunt de opties voor domeinlidmaatschap of compatibiliteit later opgeven voor Windows.

13. Kies **Voorwaarden** in de sectie **Toewijzingen**.

14. Kies **Client-apps** op de blade **Voorwaarden** en kies vervolgens de gewenste client-app.

15. Als u dat hebt gedaan, klikt u twee keer achter elkaar op **Gereed**.

    ![Vergelijking van de gebruikersinterface voor client-apps in de klassieke Intune-portal en de nieuwe Azure-portal](./media/reassign-ca-6.png)

16. Als u browserinstellingen hebt gekozen in de klassieke Intune-portal, schakelt u in de nieuwe Azure-portal de selectievakjes **Browser** en **Mobiele apps en bureaubladclients** in. Als u geen browserinstellingen hebt gekozen in de klassieke Intune-portal, selecteert u alleen **Mobiele apps en bureaubladclients**. 

17. Kies **Verlenen** in de sectie **Besturingselementen voor toegang**.

18. Kies **Vereisen dat het apparaat moet worden gemarkeerd als compatibel** onder **Besturingselementen voor toegang verlenen**en klik vervolgens op **Selecteren**.

19. Als u beleid hebt ingesteld dat Windows-apparaten lid moeten zijn van een domein, en u ook apparaten toestaat die zijn ingeschreven bij Intune en apparaten die compatibel zijn met Windows, moet u behalve **Een van de geselecteerde besturingselementen vereisen** ook de opties **Apparaat dat is toegevoegd aan het domein vereisen** en **Vereisen dat het apparaat moet worden gemarkeerd als compatibel** inschakelen.

20. Als u geen apparaten toestaat die zijn ingeschreven bij Intune en evenmin apparaten die compatibel zijn met Windows, moet u het Windows-beleid uitsluiten van het huidige beleid en vervolgens een afzonderlijk beleid maken met **Apparaatplatformen** ingesteld op **Windows**, de andere voorwaarden opnemen zoals hierboven is ingesteld en **Apparaat dat is toegevoegd aan het domein vereisen** kiezen onder **Besturingselementen voor toegang verlenen**.

21. Zet de wisselknop **Beleid inschakelen** in de nieuwe Azure-portal op **Aan** en klik vervolgens op **Maken**.

    ![Vergelijking van de gebruikersinterface voor inschakelen van beleid voor voorwaardelijke toegang in de klassieke Intune-portal en de nieuwe Azure-portal](./media/reassign-ca-11.png)

## <a name="to-reassign-intune-device-based-conditional-access-policies-for-eas-clients"></a>Beleid voor voorwaardelijke toegang op basis van Intune-apparaat opnieuw toewijzen voor EAS-clients

Als u EAS-instellingen (Exchange Active Sync) hebt geconfigureerd als onderdeel van een Exchange Online-beleid in de klassieke Intune-portal, moet u een tweede beleid voor voorwaardelijke toegang maken in de nieuwe Azure-portal.

1. Ga naar [Voorwaardelijke toegang in de nieuwe Azure-portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) en meld u aan.

2. Kies **Nieuw beleid**.

3. Geef een naam voor het beleid op.

4. Kies **Gebruikers en groepen** in de sectie **Toewijzingen** om de doelgroep voor het nieuwe beleid voor voorwaardelijke toegang te bepalen.

    ![Vergelijking van de gebruikersinterface voor gebruikersgroepen in de klassieke Intune-portal en de nieuwe Azure-portal](./media/reassign-ca-12.png)

    > [!IMPORTANT] 
    > Als de optie Alle gebruikers is geselecteerd in de klassieke Intune-portal, selecteert u Alle gebruikers. Hetzelfde geldt voor groepen. Als u groepen hebt geselecteerd, moet u **Gebruikers en groepen selecteren** kiezen om die groepen op te nemen. Als u bovendien de optie **Groepen uitsluiten** hebt gekozen in de klassieke Intune-portal, moet u de betreffende groepen uitsluiten in de nieuwe Azure-portal.

5. Nadat u uw groep hebt gekozen, klikt u op **Selecteren** en vervolgens op **Gereed**.

6. Kies **Cloud-apps** in de sectie **Toewijzingen**.

7. Klik op de blade **Cloud-apps** op **Geselecteerde apps**, kies **Exchange Online**, klik op **Selecteren** en klik ten slotte op **Gereed**.

    ![Vergelijking van de gebruikersinterface voor cloud-apps in de klassieke Intune-portal en de nieuwe Azure-portal](./media/reassign-ca-14.png)

    > [!IMPORTANT] 
    > Beleid voor voorwaardelijke toegang voor EAS-clients kan geen andere cloud-app bevatten.

8. Kies **Client-apps** op de blade **Voorwaarden** en kies vervolgens de gewenste client-app. Als u ervoor hebt gekozen om clients te blokkeren die niet worden ondersteund door Intune, gebruikt u de optie **Het beleid toepassen op ondersteunde platformen**.

    ![Vergelijking van de gebruikersinterface voor client-apps in de klassieke Intune-portal en de nieuwe Azure-portal](./media/reassign-ca-15.png)

9. Als u de client-app hebt gekozen, klikt u twee keer achter elkaar op **Gereed**.

10. Kies **Verlenen** in de sectie **Besturingselementen voor toegang**.

11. Kies **Vereisen dat het apparaat moet worden gemarkeerd als compatibel** onder **Besturingselementen voor toegang verlenen**en klik vervolgens op **Selecteren**.

    ![Vergelijking van de gebruikersinterface voor het verlenen van toegang in de klassieke Intune-portal en de nieuwe Azure-portal](./media/reassign-ca-16.png)

12. Zet de wisselknop **Beleid inschakelen** in de nieuwe Azure-portal op **Aan** en klik vervolgens op **Maken**.

    ![Vergelijking van de gebruikersinterface voor inschakelen van beleid voor voorwaardelijke toegang in de klassieke Intune-portal en de nieuwe Azure-portal](./media/reassign-ca-17.png)

## <a name="disable-conditional-access-policies-in-the-intune-classic-portal"></a>Beleid voor voorwaardelijke toegang uitschakelen in de klassieke Intune-portal
### <a name="before-you-start"></a>Voordat u begint

Als u het beleid voor voorwaardelijke toegang hebt toegewezen in de nieuwe Azure-portal, is het belangrijk dat u het eerder gemaakte beleid voor voorwaardelijke toegang in de klassieke Intune-portal gefaseerd uitschakelt. Daarnaast moet u mogelijk dezelfde beveiligingsgroep gebruiken om het beleid voor voorwaardelijke toegang dat u hebt gemaakt in de nieuwe Azure-portal toe te passen.

- Zie de sectie [Voordat u begint](#before-you-begin) aan het begin van dit onderwerp voordat u het beleid voor voorwaardelijke toegang in de klassieke Intune-portal uitschakelt.

### <a name="to-disable-the-conditional-access-policies"></a>Het beleid voor voorwaardelijke toegang uitschakelen

1.  Ga naar de [klassieke Intune-portal](https://manage.microsoft.com) en meld u aan.

2.  Kies **Beleid** in het menu aan de linkerkant.

3.  Kies **Voorwaardelijke toegang** en selecteer vervolgens de Microsoft-cloudservice (zoals Exchange Online of SharePoint Online) waarvoor u beleid voor voorwaardelijke toegang hebt opgesteld.

4.  Schakel de optie **Beleid voor voorwaardelijke toegang inschakelen** uit en klik op **Opslaan**.

    ![Beleid voor voorwaardelijke toegang uitschakelen in de klassieke Intune-portal](./media/reassign-ca-18.png)

## <a name="see-also"></a>Zie tevens

- [Gebruikelijke manieren om voorwaardelijke toegang met Intune te gebruiken](conditional-access-intune-common-ways-use.md)
- [Op apps gebaseerde voorwaardelijke toegang met Intune](app-based-conditional-access-intune.md)
- [Voorwaardelijke toegang in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)