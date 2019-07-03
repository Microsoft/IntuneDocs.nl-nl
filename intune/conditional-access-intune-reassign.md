---
title: Voorwaardelijke toegang migreren naar Azure Portal
titleSuffix: Microsoft Intune
description: Wijs de beleidsregels voor voorwaardelijke toegang die u eerder hebt gemaakt in de klassieke Intune-portal, opnieuw toe aan Azure Portal.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/02/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 301159ad-5f7e-4fcc-86c7-f72a71701ff4
ms.reviewer: chrisgree
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f4fa42a52e104ef1c9cf13c8490159f3dbb2efed
ms.sourcegitcommit: 4b83697de8add3b90675c576202ef2ecb49d80b2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/13/2019
ms.locfileid: "67045322"
---
# <a name="reassign-conditional-access-policies-from-intune-classic-portal-to-the-azure-portal"></a>Beleid voor voorwaardelijke toegang vanuit de klassieke Intune-portal overbrengen naar Azure Portal

Met de introductie van de nieuwe Azure Portal biedt de functie voor voorwaardelijke toegang ondersteuning voor meerdere beleidsregels per toepassing. Daarnaast zijn er nu ook meer aanpassingsmogelijkheden. Als u eerder beleid voor voorwaardelijke toegang hebt gemaakt in de klassieke Intune-portal Intune, kunt u dit migreren naar Azure Portal. 

## <a name="before-you-begin"></a>Voordat u begint

Als u klaar bent om over te stappen op Azure Portal, volgt u de stappen in dit onderwerp om de beleidsregels voor voorwaardelijke toegang die u eerder hebt gemaakt in de klassieke Intune-portal, opnieuw toe te wijzen:

- Verzamel de beleidsregels voor voorwaardelijke toegang die eerder zijn gemaakt, zodat u weet welke instellingen u later opnieuw moet toewijzen.

- Volg de stappen in dit onderwerp om deze beleidsregels opnieuw te maken in Azure Portal.

- Schakel de beleidsregels voor voorwaardelijke toegang uit in de klassieke Intune-portal, nadat u hebt gecontroleerd of de nieuwe beleidsregels naar behoren werken in Azure Portal.
<br /><br />
    - Voordat u de beleidsregels voor voorwaardelijke toegang **uitschakelt in de klassieke Intune-portal**, moet u een plan opstellen voor het overbrengen van gebruikers naar het nieuwe beleid. Er zijn twee manieren:
<br /><br />
        - **Gebruik dezelfde insluitingsgroep om beleid toe te passen dat is gemaakt in Azure Portal, en maak een nieuwe uitsluitingsgroep voor gebruik met de beleidsregels die worden toegepast door de klassieke Intune-portal**.
            - Verplaats steeds kleine aantallen gebruikers naar de uitsluitingsgroep die is opgegeven in de klassieke portal. Hiermee voorkomt u dat de beleidsregels van de klassieke Intune-portal op deze gebruikers worden toegepast. Het beleid dat is gemaakt en gericht op dezelfde gebruikersgroep in Azure Portal, wordt toegepast in aanvulling op het beleid van de klassieke Intune-portal. 
<br /><br />
        - **Maak een nieuwe groep voor het beleid voor voorwaardelijke toegang van Azure Portal**. Als u deze aanpak kiest, moet u het volgende doen:
            - Verwijder gebruikers geleidelijk uit de beveiligingsgroepen waarop beleid voor voorwaardelijke toegang uit de klassieke Intune-portal is toegepast.
            - Nadat u hebt vastgesteld dat het nieuwe beleid werkt voor deze gebruikers, kunt u het beleid uitschakelen in de klassieke Intune-portal. 
<br /><br />
- Als het beleid voor voorwaardelijke toegang in de klassieke Intune-portal is geconfigureerd voor gebruik van Exchange Active Sync (EAS), volgt u de [instructies in dit onderwerp](#reassign-intune-device-based-conditional-access-policies-for-eas-clients) om **de EAS-beleidsinstellingen voor voorwaardelijke toegang toe te wijzen in Azure Portal**.

### <a name="to-verify-your-device-based-conditional-access-policies-in-the-intune-classic-portal"></a>Op apparaat gebaseerd beleid voor voorwaardelijke toegang controleren in de klassieke Intune-portal

1.  Ga naar de [klassieke Intune-portal](https://manage.microsoft.com) en meld u aan met uw referenties.

2.  Kies **Beleid** in het menu aan de linkerkant.

3.  Kies **Voorwaardelijke toegang** en selecteer vervolgens de Microsoft-cloudservice (zoals Exchange Online of SharePoint Online) waarvoor u beleid voor voorwaardelijke toegang hebt opgesteld.

4.  Noteer de instellingen voor voorwaardelijke toegang en raadpleeg deze notities om hetzelfde voorwaardelijke toegangsbeleid te maken in Azure Portal.

### <a name="app-and-device-based-conditional-access-policies-working-together"></a>Beleid voor voorwaardelijke toegang op basis van app en apparaat combineren

Via de blade **Intune-app-beveiliging** in Azure Portal kunnen beheerders app-gebaseerde regels voor voorwaardelijke toegang instellen, zodat alleen apps die ondersteuning bieden voor Intune-app-beveiligingsbeleid toegang hebben tot bedrijfsresources. U kunt deze app-gebaseerde beleidsregels voor voorwaardelijke toegang laten overlappen met apparaat-gebaseerd beleid voor voorwaardelijke toegang. U kunt de apparaat- en app-beleidsregels voor voorwaardelijke toegang combineren (logische AND) of een keuze instellen (logische OR). Het werkt als volgt:

- Vereis dat het apparaat compatibel is **EN** dat een goedgekeurde app wordt gebruikt.
    - U moet het beleid voor voorwaardelijke toegang instellen met de blade [Voorwaardelijke toegang van Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) en de blade [Intune-app-beveiliging](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).
<br /><br />
- Vereis dat het apparaat compatibel is **OF** dat een goedgekeurde app wordt gebruikt.
    - U moet het beleid voor voorwaardelijke toegang instellen met de [klassieke Intune-portal](https://manage.microsoft.com) en de blade [Intune-app-beveiliging](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).

> [!TIP] 
> Dit onderwerp bevat schermafbeeldingen die de gebruikerservaring laten zien in zowel de klassieke Intune-portal als Azure Portal.

## <a name="reassign-intune-device-based-conditional-access-policies"></a>Intune-beleid voor voorwaardelijke toegang op basis van apparaat opnieuw toewijzen

1. Ga naar [Voorwaardelijke toegang in Azure Portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) en meld u aan met uw referenties.

2. Kies **Nieuw beleid**.

3. Geef een naam voor het beleid op.

4. Kies **Gebruikers en groepen** in de sectie **Toewijzingen** om de doelgroep voor het nieuwe beleid voor voorwaardelijke toegang te bepalen.
    
    ![Afbeelding met vergelijking van de gebruikersinterface voor Gebruikersgroep tussen de Intune-portal en Azure Portal](./media/reassign-ca-1.png)

    > [!IMPORTANT] 
    > De selectie die u voor Azure Portal hebt gemaakt, moet overeenkomen met de selectie die u voor de klassieke portal hebt gemaakt. Als u bijvoorbeeld alle gebruikers hebt geselecteerd in de klassieke Intune-portal, selecteert u ook **Alle gebruikers** in Azure Portal. Als u bovendien de optie **Groepen uitsluiten** hebt gekozen in de klassieke Intune-portal, moet u de betreffende groepen ook uitsluiten in Azure Portal.

5. Nadat u de groep hebt gekozen, klikt u op **Selecteren** en vervolgens op **Gereed**.

6. Kies **Cloud-apps** in de sectie **Toewijzingen**.

7. Kies **Apps selecteren** op de blade **Cloud-apps**.

8. Kies de app waarop u het nieuwe beleid voor voorwaardelijke toegang wilt toepassen en klik op **Selecteren**.

9. Klik op **Gereed**.

    ![Afbeelding met vergelijking van de gebruikersinterface voor Cloud-apps tussen de Intune-portal en Azure Portal](./media/reassign-ca-3.png)

    > [!TIP] 
    > Als u meerdere apps met hetzelfde beleid hebt, kunt u overwegen de apps in één beleid onder te brengen in Azure Portal.

10. Kies **Voorwaarden** in de sectie **Toewijzingen**.

11. Kies **Apparaatplatformen** op de blade **Voorwaarden** en kies vervolgens de gewenste apparaatplatformen.

12. Als u dat hebt gedaan, klikt u tweemaal op **Gereed**.

    ![Afbeelding van vergelijking van de gebruikersinterface voor Apparaatplatformen tussen de Intune-portal en Azure Portal](./media/reassign-ca-4.png)

    > [!TIP] 
    > Als u afzonderlijke platformen hebt gekozen in de klassieke Intune-portal, kiest u deze platformen in Azure Portal.

    > [!NOTE] 
    > U kunt de opties voor domeinlidmaatschap of compatibiliteit later opgeven voor Windows.

13. Kies **Voorwaarden** in de sectie **Toewijzingen**.

14. Kies **Client-apps** op de blade **Voorwaarden** en kies vervolgens de gewenste client-app.

15. Als u de client-app hebt gekozen, klikt u tweemaal op **Gereed**.

    ![Afbeelding met vergelijking van de gebruikersinterface voor Client-apps tussen de Intune-portal en Azure Portal](./media/reassign-ca-6.png)

16. Als u browserinstellingen hebt gekozen in de klassieke Intune-portal, schakelt u in Azure Portal de selectievakjes **Browser** en **Mobiele apps en bureaubladclients** in. Als u geen browserinstellingen hebt gekozen in de klassieke Intune-portal, selecteert u alleen **Mobiele apps en bureaubladclients**. 

17. Kies **Verlenen** in de sectie **Besturingselementen voor toegang**.

18. Kies **Vereisen dat het apparaat moet worden gemarkeerd als compatibel** onder **Besturingselementen voor toegang verlenen**en klik vervolgens op **Selecteren**.

19. Als u beleid hebt ingesteld dat Windows-apparaten lid moeten zijn van een domein, en u ook apparaten toestaat die zijn ingeschreven bij Intune en apparaten die compatibel zijn met Windows, moet u behalve **Een van de geselecteerde besturingselementen vereisen** ook de opties **Apparaat dat is toegevoegd aan het domein vereisen** en **Vereisen dat het apparaat moet worden gemarkeerd als compatibel** inschakelen.

20. Als u geen apparaten toestaat die zijn ingeschreven bij Intune en compatibel zijn met Windows, kunt u het Windows-beleid van het huidige beleid uitsluiten. Maak vervolgens een aparte beleidsregel waarin **Apparaatplatformen** is ingesteld op **Windows**, neem de andere voorwaarden op zoals hierboven ingesteld en kies **Apparaat dat is toegevoegd aan het domein vereisen** onder **Besturingselementen voor toegang verlenen**.

21. Schakel in de **nieuwe** blade voor het beleid voor voorwaardelijke toegang de wisselknop **Beleid inschakelen** in en klik vervolgens op **Maken**.

    ![Vergelijking van de gebruikersinterface voor Beleid voor voorwaardelijke toegang inschakelen tussen Intune en Azure](./media/reassign-ca-11.png)

## <a name="reassign-intune-device-based-conditional-access-policies-for-eas-clients"></a>Beleid voor voorwaardelijke toegang op basis van Intune-apparaat opnieuw toewijzen voor EAS-clients

Als u EAS-instellingen (Exchange Active Sync) hebt geconfigureerd als onderdeel van een Exchange Online-beleidsregel in de klassieke Intune-portal, moet u een tweede beleidsregel voor voorwaardelijke toegang maken in Azure Portal.

1. Ga naar [Voorwaardelijke toegang in Azure Portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) en meld u aan met uw referenties.

2. Kies **Nieuw beleid**.

3. Geef een naam voor het beleid op.

4. Kies **Gebruikers en groepen** in de sectie **Toewijzingen** om de doelgroep voor het nieuwe beleid voor voorwaardelijke toegang te bepalen.

    ![Afbeelding van een vergelijking van de gebruikersinterface voor een gebruikersgroep tussen de Intune-portal en Azure Portal](./media/reassign-ca-12.png)

    > [!IMPORTANT] 
    > De selectie die u voor Azure-portal maakt, moet overeenkomen met de selectie voor de Azure-portal. Als u bijvoorbeeld alle gebruikers hebt geselecteerd in de klassieke Intune-portal, selecteert u ook **Alle gebruikers** in Azure Portal. Als u bovendien de optie **Groepen uitsluiten** hebt gekozen in de klassieke Intune-portal, moet u de betreffende groepen ook uitsluiten in Azure Portal.

5. Nadat u de groep hebt gekozen, klikt u op **Selecteren** en vervolgens op **Gereed**.

6. Kies **Cloud-apps** in de sectie **Toewijzingen**.

7. Klik op de blade **Cloud-apps** op **Apps selecteren** en kies **Exchange Online**. Klik vervolgens op **Selecteren** en **Gereed**.

    ![Vergelijking van de gebruikersinterface voor Cloud-apps tussen de Intune-portal en Azure Portal](./media/reassign-ca-14.png)

    > [!IMPORTANT] 
    > Beleid voor voorwaardelijke toegang voor EAS-clients kan geen andere cloud-app bevatten.

8. Kies **Client-apps** op de blade **Voorwaarden** en kies vervolgens de gewenste client-app. Als u ervoor hebt gekozen om clients te blokkeren die niet worden ondersteund door Intune, gebruikt u de optie **Het beleid toepassen op ondersteunde platformen**.

    ![Afbeelding van de vergelijking van de gebruikersinterface voor client-apps tussen de Intune-portal en Azure Portal](./media/reassign-ca-15.png)

9. Als u de client-app hebt gekozen, klikt u tweemaal op **Gereed**.

10. Kies **Verlenen** in de sectie **Besturingselementen voor toegang**.

11. Kies **Vereisen dat het apparaat moet worden gemarkeerd als compatibel** onder **Besturingselementen voor toegang verlenen**en klik vervolgens op **Selecteren**.

    ![Afbeelding van de vergelijking van de gebruikersinterface voor Toegang verlenen tussen de Intune-portal en Azure Portal](./media/reassign-ca-16.png)

12. Schakel in de **nieuwe** blade voor het beleid voor voorwaardelijke toegang de wisselknop **Beleid inschakelen** in en klik vervolgens op **Maken**.

    ![Vergelijking van de gebruikersinterface voor Beleid voor voorwaardelijke toegang inschakelen tussen de Intune-portal en Azure Portal](./media/reassign-ca-17.png)

> [!NOTE]
> Als u **Apparaatplatformen** configureert, kunt u het beleid niet opslaan. U krijgt dan de foutmelding: ‘Beleidsconfiguratie wordt niet ondersteund.’ Het platform dat door het verbindende apparaat wordt gebruikt, kan niet door Exchange ActiveSync worden geïdentificeerd. Het configureren van specifieke apparaatplatformen wordt daarom niet ondersteund wanneer u een beleid voor Exchange ActiveSync-apparaten maakt.

## <a name="disable-conditional-access-policies-in-the-intune-classic-portal"></a>Beleid voor voorwaardelijke toegang uitschakelen in de klassieke Intune-portal

Nadat u het beleid voor voorwaardelijke toegang hebt toegewezen in Azure Portal, is het belangrijk dat u het eerder gemaakte beleid voor voorwaardelijke toegang in de klassieke Intune-portal gefaseerd uitschakelt. Daarnaast moet u mogelijk dezelfde beveiligingsgroep gebruiken om het beleid voor voorwaardelijke toegang dat u in Azure Portal hebt gemaakt, toe te passen.

> [!NOTE]
> Raadpleeg de sectie [Voordat u begint](#before-you-begin) aan het begin van dit onderwerp voordat u het beleid voor voorwaardelijke toegang in de klassieke Intune-portal uitschakelt.

### <a name="to-disable-the-conditional-access-policies"></a>Het beleid voor voorwaardelijke toegang uitschakelen

1.  Ga naar de [klassieke Intune-portal](https://manage.microsoft.com) en meld u aan met uw referenties.

2.  Kies **Beleid** in het menu aan de linkerkant.

3.  Kies **Voorwaardelijke toegang** en selecteer vervolgens de Microsoft-cloudservice (zoals Exchange Online of SharePoint Online) waarvoor u beleid voor voorwaardelijke toegang hebt opgesteld.

4.  Schakel de optie **Beleid voor voorwaardelijke toegang inschakelen** uit en klik op **Opslaan**.

    ![Afbeelding van Beleid voor voorwaardelijke toegang uitschakelen in de klassieke Intune-portal](./media/reassign-ca-18.png)

## <a name="see-also"></a>Zie tevens

- [Gebruikelijke manieren om voorwaardelijke toegang met Intune te gebruiken](conditional-access-intune-common-ways-use.md)
- [Op apps gebaseerde voorwaardelijke toegang met Intune](app-based-conditional-access-intune.md)
- [Voorwaardelijke toegang in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)
