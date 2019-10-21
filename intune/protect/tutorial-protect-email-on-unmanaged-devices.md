---
title: 'Zelfstudie: Exchange Online-e-mail beschermen op onbeheerde apparaten'
titleSuffix: Microsoft Intune
description: Leer hoe u Office 365 Exchange Online kunt beveiligen met app-beveiligingsbeleid van Intune en voorwaardelijke toegang via Azure AD.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/10/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7e0a01034bc35ddf8fd8eb1ede5fcf4c942dc735
ms.sourcegitcommit: dd6755383ba89824d1cc128698a65fde6bb2de55
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/14/2019
ms.locfileid: "72306801"
---
# <a name="tutorial-protect-exchange-online-email-on-unmanaged-devices"></a>Zelfstudie: Exchange Online-e-mail beschermen op onbeheerde apparaten

Meer informatie over het gebruik van app-beveiligingsbeleid met voorwaardelijke toegang om Exchange Online te beveiligen, zelfs wanneer apparaten niet zijn geregistreerd bij een oplossing voor apparaatbeheer, zoals Intune. In deze zelfstudie leert u het volgende: 

> [!div class="checklist"]
> * Maak een Intune-beveiligingsbeleid voor de Outlook-app. U gaat nu beperken wat de gebruiker kan doen met app-gegevens door 'Opslaan als' te blokkeren en de acties knippen, kopiëren en plakken te beperken. 
> * Maak Azure AD-beleid (Active Directory) voor voorwaardelijke toegang, zodat alleen de Outlook-app toegang heeft tot zakelijke e-mail in Exchange Online. U gaat ook meervoudige verificatie (multi-factor authentication, MFA) vereisen voor clients met moderne verificatie, zoals Outlook voor iOS en Android.

## <a name="prerequisites"></a>Vereisten
- Voor deze zelfstudie hebt u een testtenant nodig met de volgende abonnementen:
  - Azure Active Directory Premium ([ gratis proefversie](https://azure.microsoft.com/free/?WT.mc_id=A261C142F))
  - Intune-abonnement ([gratis proefversie](../fundamentals/free-trial-sign-up.md))
  - Office 365 Business-abonnement inclusief Exchange ([ gratis proefversie](https://go.microsoft.com/fwlink/p/?LinkID=510938))

## <a name="sign-in-to-intune"></a>Aanmelden bij Intune

Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) als globale beheerder of beheerder van een Intune-service. U gaat in Azure Portal naar Intune door **Alle services** > **Intune** te kiezen.

## <a name="create-the-app-protection-policy"></a>Beveiligingsbeleid voor de app maken
Voor deze zelfstudie stellen we een Intune-beveiligingsbeleid in voor de Outlook-app om beveiliging toe te passen op het niveau van de app. We stellen hierbij een pincode verplicht om de app te openen in werkcontext. We beperken ook gegevensdeling tussen apps en voorkomen dat bedrijfsgegevens worden opgeslagen op een persoonlijke locatie.

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) en ga naar **Client-apps** > **Appbeveiligingsbeleid** > **Beleid maken**.  
2. Configureer de volgende instellingen:  
   - **Naam**: Voer **Beleidstest voor de Outlook-app** in.  
   - **Beschrijving**: Voer **Beleidstest voor de Outlook-app** in.  
   - **Platform**: Selecteer **iOS**.  
   - **Toepassen op alle app-typen**: Selecteer **Nee** en schakel vervolgens voor **App-typen** het selectievakje in voor **Apps op onbeheerde apparaten**.  
3. Selecteer **Apps**. Selecteer **Outlook** in de lijst met apps en kies vervolgens **Selecteren**.
4. Selecteer **Instellingen** om het deelvenster Instellingen te openen. 
5. Selecteer in het deelvenster Instellingen de optie **Gegevensbeveiliging**. Configureer in het deelvenster Gegevensbeveiliging onder *Gegevensoverdracht* de volgende instellingen voor deze zelfstudie:

   - Selecteer voor **Organisatiegegevens naar andere apps verzenden** de optie **Geen**.  
   - Selecteer voor **Gegevens ontvangen van andere apps** de optie **Geen**.  
   - Selecteer voor **Kopieën van organisatiegegevens opslaan** de optie **Blokkeren**.  
   - Selecteer voor **Knippen, kopiëren en plakken met andere apps beperken** de optie **Geblokkeerd**. 
   - Laat alle andere instellingen op hun standaardwaarden. 
   
   ![Selecteer de Instellingen voor herlocatie van gegevens voor de Outlook-app](./media/tutorial-protect-email-on-unmanaged-devices/data-protection-settings.png)

   Selecteer **OK** om terug te keren naar het deelvenster Instellingen.  

6. Selecteer **Toegangsvereisten** en configureer vervolgens de volgende instellingen:  

   - Selecteer voor **Pincode voor toegang** de optie **Vereisen**.
   - Selecteer voor **Aanmeldingsgegevens voor werk-of schoolaccount voor toegang** de optie **Vereisen**.
   - Laat alle andere instellingen op hun standaardwaarden.
 
    ![De toegangsacties voor het beveiligingsbeleid van de Outlook-app selecteren](./media/tutorial-protect-email-on-unmanaged-devices/access-requirements-settings.png)

    Selecteer **OK** om terug te keren naar het deelvenster Instellingen.  

7. Selecteer **OK** in het deelvenster Instellingen en vervolgens **Maken** in het deelvenster Beleid maken.

Het app-beveiligingsbeleid voor Outlook is gemaakt. Nu kunt u voorwaardelijke toegang instellen om voor apparaten te vereisen dat de Outlook-app wordt gebruikt.

## <a name="create-conditional-access-policies"></a>Beleid voor voorwaardelijke toegang maken
U gaat nu twee beleidsregels voor voorwaardelijke toegang maken, om zo alle apparaatplatforms te bereiken.  

- Via het eerste beleid wordt vereist dat clients met moderne verificatie de goedgekeurde Outlook-app en meervoudige verificatie (multi-factor authentication of MFA) gebruiken. Onder clients met moderne verificatie vallen Outlook voor iOS en Outlook voor Android.  

- Via het tweede beleid wordt vereist dat Exchange ActiveSync-clients de goedgekeurde Outlook-app gebruiken. (Op dit moment biedt Exchange ActiveSync geen ondersteuning voor andere voorwaarden dan het apparaatplatform). U kunt het voorwaardelijke toegangsbeleid instellen in de Azure AD-portal of in de Intune-portal. Omdat we al in de Intune-portal zitten, maken we daarin het beleid.  

### <a name="create-an-mfa-policy-for-modern-authentication-clients"></a>Een MFA-beleid maken voor clients met moderne verificatie  

1. In Intune selecteert u **Voorwaardelijke toegang** > **Beleid** > **Nieuw beleid**.  

2. Bij **Naam** voert u **Testbeleid voor clients met moderne verificatie** in.  

3. Onder **Toewijzingen** selecteert u **Gebruikers en groepen**. Op het tabblad **Opnemen** selecteert u **Alle gebruikers** en vervolgens **Voltooid**.

4. Onder **Toewijzingen** selecteert u **Cloud-apps of acties**. Omdat we Office 365 Exchange Online e-mail willen beschermen, selecteren we deze functie via de volgende stappen:  
     
   1. Op het tabblad **Opnemen** selecteert u **Apps selecteren**.  
   2. Kies **Selecteren**.  
   3. In de lijst Toepassingen selecteert u **Office 365 Exchange Online** en kiest u vervolgens **Selecteren**.  
   4. Selecteer **Gereed** om terug te keren naar het deelvenster Nieuw beleid.  
  
   ![De Office 365 Exchange Online-app selecteren](./media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-cloud-apps.png)

5. Onder **Toewijzingen** selecteert u **Voorwaarden** > **Apparaatplatforms**.  
   1. Onder **Configureren** selecteert u **Ja**.  
   2. Op het tabblad **Opnemen** selecteert u **Elk apparaat**.  
   3. Selecteer **Voltooid**.  
   
6. Selecteer in het deelvenster **Voorwaarden** de optie **Client-apps**.  
   1. Onder **Configureren** selecteert u **Ja**.  
   2. Selecteer **Mobiele apps en bureaubladclients** en **Clients met moderne verificatie**.  
   3. Schakel de andere selectievakjes uit.  
   4. Selecteer **Gereed** > **Gereed** om terug te keren naar het deelvenster Nieuw beleid.  

   ![Mobiele apps en clients selecteren](./media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-client-apps.png)

7. Onder **Toegangscontroles** selecteert u **Verlenen**. 
     
   1. In het deelvenster **Verlenen** selecteert u **Toegang verlenen**.
   2. Selecteer **Meervoudige verificatie vereisen**.
   3. Selecteer **Goedgekeurde client-app vereisen**.
   4. Onder **Voor meerdere besturingselementen** selecteert u **Alle geselecteerde besturingselementen vereisen**. Deze instelling zorgt ervoor dat beide door u geselecteerde vereisten worden afgedwongen wanneer een apparaat toegang tot de e-mailfunctie probeert te krijgen.
   5. Kies **Selecteren**.
     
   ![Besturingselementen selecteren](./media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-mfa.png)

7. Selecteer onder **Beleid inschakelen** de optie **Aan** en selecteer vervolgens **Maken**.  
     
    ![Beleid maken](./media/tutorial-protect-email-on-unmanaged-devices/enable-policy.png)  

Het beleid voor voorwaardelijke toegang voor clients met moderne verificatie is gemaakt. U kunt nu een beleid maken voor Exchange ActiveSync-clients.

### <a name="create-a-policy-for-exchange-active-sync-clients"></a>Een beleid voor Exchange ActiveSync-clients maken  
1. In Intune selecteert u **Voorwaardelijke toegang** > **Beleid** > **Nieuw beleid**.  
2. Bij **Naam** voert u **Testbeleid voor EAS-clients** in.  
3. Onder **Toewijzingen** selecteert u **Gebruikers en groepen**.  
4. Op het tabblad *Opnemen* selecteert u **Alle gebruikers** en vervolgens **Voltooid**.  

5. Onder **Toewijzingen** selecteert u **Cloud-apps of acties**. Selecteer Office 365 Exchange Online-e-mail aan de hand van de volgende stappen:  
   1. Op het tabblad *Opnemen* selecteert u **Apps selecteren**.  
   2. Kies **Selecteren**.  
   3. In de lijst met *toepassingen* selecteert u **Office 365 Exchange Online** en vervolgens kiest u **Selecteren** en **Gereed**.  
  
6. Onder **Toewijzingen** selecteert u **Voorwaarden** > **Apparaatplatforms**.  
   1. Onder **Configureren** selecteert u **Ja**.  
   2. Op het tabblad **Opnemen** selecteert u **Elk apparaat** en vervolgens **Voltooid**.  

7. Selecteer in het deelvenster **Voorwaarden** de optie **Client-apps**.  
   1. Onder **Configureren** selecteert u **Ja**.  
   2. Selecteer **Mobiele apps en bureaubladclients**.  
   3. Selecteer **Exchange ActiveSync-clients** en **Het beleid toepassen op ondersteunde platformen**.  
   4. Schakel alle andere selectievakjes uit.  
   5. Selecteer **Voltooid** en vervolgens opnieuw **Voltooid**.  
    
   ![Toepassen op ondersteunde platforms](./media/tutorial-protect-email-on-unmanaged-devices/eas-client-apps.png)  

7. Onder **Toegangscontroles** selecteert u **Verlenen**.  
   1. In het deelvenster **Verlenen** selecteert u **Toegang verlenen**.  
   2. Selecteer **Goedgekeurde client-app vereisen**. Schakel alle andere selectievakjes uit.  
   3. Kies **Selecteren**.  
     
   ![Goedgekeurde client-app vereisen](./media/tutorial-protect-email-on-unmanaged-devices/eas-grant-access.png)  

8. Onder **Beleid inschakelen** selecteert u **Aan**.  

9. Selecteer **Maken**.  

Uw app-beveiligingsbeleid en voorwaardelijke toegang zijn nu ingesteld en kunnen worden getest.  

## <a name="try-it-out"></a>Beleid uitproberen  
Met het beleid dat u hebt gemaakt, moeten apparaten zich inschrijven bij Intune en de mobiele Outlook-app gebruiken om toegang tot Office 365-e-mail te krijgen. Om dit scenario op een iOS-apparaat te testen, probeert u zich aan te melden bij Exchange Online met de referenties van een gebruiker in uw testtenant.  
1. Als u dit op een iPhone wilt testen, gaat u naar **Instellingen** > **Wachtwoorden & accounts** > **Account toevoegen** > **Exchange**.  
2. Voer het e-mailadres van een gebruiker in uw testtenant in en klik vervolgens op **Volgende**.  
3. Klik op **Aanmelden**.  
4. Voer het wachtwoord van de testgebruiker in en klik op **Aanmelden** .  
5. Het bericht **Er is meer informatie vereist** wordt weergegeven. Dit betekent dat u wordt gevraagd om MFA in te stellen. Stel een extra verificatiemethode in.  
6. Er wordt vervolgens een bericht weergegeven waarin wordt vermeld dat u deze bron probeert te openen met een app die niet is goedgekeurd door uw IT-afdeling. Dit betekent dat de systeemeigen e-mail-app voor u wordt geblokkeerd. Annuleer de aanmelding.  
7. Open de Outlook-app en selecteer **Instellingen** > **Account toevoegen** > **E-mailaccount toevoegen**.  
8. Voer het e-mailadres van een gebruiker in uw testtenant in en klik vervolgens op **Volgende**.  
9. Druk op **Aanmelden met Office 365**. U wordt gevraagd om extra verificatie en registratie. Nadat u zich hebt aangemeld, kunt u acties zoals knippen, kopiëren, plakken en 'Opslaan als' testen.  

## <a name="clean-up-resources"></a>Resources opschonen  
Als het testbeleid niet langer nodig is, kunt u dit verwijderen.  
1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) als globale beheerder of beheerder van een Intune-service.  
2. Selecteer **Apparaatnaleving** > **Beleid**.  
3. In de lijst **Naam beleid** selecteert u het contextmenu ( **...** ) voor uw testbeleid, en vervolgens selecteert u **Verwijderen**. Selecteer **OK** om te bevestigen.  
4. Selecteer **Voorwaardelijke toegang** > **Beleid**.  
5. Selecteer in de lijst **Naam beleid** het contextmenu ( **...** ) voor uw testbeleid en selecteer vervolgens **Verwijderen**. Selecteer **Ja** om te bevestigen.  

## <a name="next-steps"></a>Volgende stappen  
In deze zelfstudie hebt u app-beveiligingsbeleid gemaakt om te beperken wat de gebruiker kan doen met de Outlook-app. Ook hebt u beleid voor voorwaardelijke toegang gemaakt om gebruik van de Outlook-app te vereisen en MFA te vereisen voor clients met moderne verificatie. Zie, voor meer informatie over het gebruik van Intune met voorwaardelijke toegang om andere apps en diensten te beschermen, [Voorwaardelijke toegang instellen](conditional-access.md).
