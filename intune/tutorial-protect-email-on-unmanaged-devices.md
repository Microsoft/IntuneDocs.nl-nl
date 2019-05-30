---
title: 'Zelfstudie: Exchange Online-e-mail beschermen op onbeheerde apparaten'
titleSuffix: Microsoft Intune
description: Leer hoe u Office 365 Exchange Online kunt beveiligen met app-beveiligingsbeleid van Intune en voorwaardelijke toegang via Azure AD.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/26/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b91e3863a23d62921f4145db4460fa07f325df98
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/23/2019
ms.locfileid: "66040301"
---
# <a name="tutorial-protect-exchange-online-email-on-unmanaged-devices"></a>Zelfstudie: Exchange Online-e-mail beschermen op onbeheerde apparaten

Meer informatie over het gebruik van app-beveiligingsbeleid met voorwaardelijke toegang om Exchange Online te beveiligen, zelfs wanneer apparaten niet zijn geregistreerd bij een oplossing voor apparaatbeheer, zoals Intune. In deze zelfstudie leert u het volgende: 

> [!div class="checklist"]
> * Maak een Intune-beveiligingsbeleid voor de Outlook-app. U gaat nu beperken wat de gebruiker kan doen met app-gegevens door 'Opslaan als' te blokkeren en de acties knippen, kopiëren en plakken te beperken. 
> * Maak Azure AD-beleid (Active Directory) voor voorwaardelijke toegang, zodat alleen de Outlook-app toegang heeft tot zakelijke e-mail in Exchange Online. U gaat ook meervoudige verificatie (multi-factor authentication, MFA) vereisen voor clients met moderne verificatie, zoals Outlook voor iOS en Android.

## <a name="prerequisites"></a>Vereisten
  - Voor deze zelfstudie hebt u een testtenant nodig met de volgende abonnementen:
    - Azure Active Directory Premium ([ gratis proefversie](https://azure.microsoft.com/free/?WT.mc_id=A261C142F))
    - Intune-abonnement ([gratis proefversie](free-trial-sign-up.md))
    - Office 365 Business-abonnement inclusief Exchange ([ gratis proefversie](https://go.microsoft.com/fwlink/p/?LinkID=510938))

## <a name="sign-in-to-intune"></a>Aanmelden bij Intune

Meld u aan bij [Intune](https://aka.ms/intuneportal) als globale beheerder of beheerder van een Intune-service. U gaat in Azure Portal naar Intune door **Alle services** > **Intune** te kiezen.

## <a name="create-the-app-protection-policy"></a>Beveiligingsbeleid voor de app maken
Voor deze zelfstudie stellen we een Intune-beveiligingsbeleid in voor de Outlook-app om beveiliging toe te passen op het niveau van de app. We stellen hierbij een pincode verplicht om de app te openen in werkcontext. We beperken ook gegevensdeling tussen apps en voorkomen dat bedrijfsgegevens worden opgeslagen op een persoonlijke locatie.

1.  Selecteer in Intune **Client-apps** > **App-beveiligingsbeleid** > **Een beleid toevoegen**.
2.  Voer bij **Naam** **Outlook-app-testbeleid** in.
3.  Voer bij **Beschrijving** **Outlook-app-testbeleid** in.
4.  Selecteer **Apps**. Selecteer in de lijst met apps **Outlook** en kies vervolgens **Selecteren**.
5.  Selecteer **Instellingen**. 
6.  Selecteer voor deze zelfstudie bij **Gegevensverplaatsing** deze instellingen:

    - Selecteer bij **App mag gegevens overdragen naar ander apps** **Geen**.
    - Selecteer bij **App mag gegevens ontvangen van ander apps** **Geen**.
    - Selecteer bij **'Opslaan als' voorkomen** **Ja**.
    - Selecteer bij **Knippen, kopiëren en plakken met andere apps beperken** **Geblokkeerd**.
   
     ![Selecteer de Instellingen voor herlocatie van gegevens voor de Outlook-app](media/tutorial-protect-email-on-unmanaged-devices/outlook-app-data-relocation.png)
    
7.  Selecteer voor deze zelfstudie bij **Toegangsacties** deze instellingen:

    - Selecteer bij **Pincode vereisen voor toegang** **Ja**.
    - Selecteer bij **Bedrijfsreferenties vereisen voor toegang** **Ja**.
    - Laat alle andere instellingen op hun standaardwaarden.
 
     ![De toegangsacties voor het beveiligingsbeleid van de Outlook-app selecteren](media/tutorial-protect-email-on-unmanaged-devices/outlook-app-access-actions.png)

9.  Selecteer **OK**.
10. Selecteer **Maken**.

Het app-beveiligingsbeleid voor Outlook is gemaakt. U kunt nu voorwaardelijke toegang instellen om te vereisen dat apparaten de Outlook-app gebruiken.

## <a name="create-conditional-access-policies"></a>Beleid voor voorwaardelijke toegang maken
U gaat nu twee beleidsregels voor voorwaardelijke toegang maken, om zo alle apparaatplatforms te bereiken. Het eerste beleid vereist het gebruik van de goedgekeurde Outlook-app en MFA op clients met moderne verificatie, zoals Outlook voor iOS en Outlook voor Android. De tweede beleidsregel vereist dat Exchange ActiveSync-clients de goedgekeurde Outlook-app gebruiken. (Op dit moment biedt Exchange ActiveSync geen ondersteuning voor andere voorwaarden dan het apparaatplatform). U kunt het voorwaardelijke toegangsbeleid instellen in de Azure AD-portal of in de Intune-portal. Omdat we al in de Intune-portal zitten, maken we daarin het beleid.
### <a name="create-an-mfa-policy-for-modern-authentication-clients"></a>Een MFA-beleid maken voor clients met moderne verificatie
1.  In Intune selecteert u **Voorwaardelijke toegang** > **Beleid** > **Nieuw beleid**.
1.  Bij **Naam** voert u **Testbeleid voor clients met moderne verificatie** in. 
3.  Onder **Toewijzingen** selecteert u **Gebruikers en groepen**. Op het tabblad **Opnemen** selecteert u **Alle gebruikers** en vervolgens **Voltooid**.

4.  Onder **Toewijzingen** selecteert u **Cloud-apps**. Omdat we Office 365 Exchange Online e-mail willen beschermen, selecteren we deze functie via de volgende stappen:
     
    1. Op het tabblad **Opnemen** selecteert u **Apps selecteren**.
    2. Kies **Selecteren**. 
    3. In de lijst met toepassingen selecteert u **Office 365 Exchange Online** en vervolgens kiest u **Selecteren**. 
    4. Selecteer **Voltooid**.
  
    ![De Office 365 Exchange Online-app selecteren](media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-cloud-apps.png)

5.  Onder **Toewijzingen** selecteert u **Voorwaarden** > **Apparaatplatforms**.
     
    1. Onder **Configureren** selecteert u **Ja**.
    2. Op het tabblad **Opnemen** selecteert u **Elk apparaat**.
    1. Selecteer **Voltooid**.
   
6.  Selecteer in het deelvenster **Voorwaarden** de optie **Client-apps**.
     
    1. Onder **Configureren** selecteert u **Ja**.
    2. Selecteer **Mobiele apps en bureaubladclients** en **Clients met moderne verificatie**.
    3. Schakel de andere selectievakjes uit.
    4. Selecteer **Voltooid** en vervolgens opnieuw **Voltooid**.
    
    ![De Office 365 Exchange Online-app selecteren](media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-client-apps.png)

7.  Onder **Toegangscontroles** selecteert u **Verlenen**. 
     
    1. In het deelvenster **Verlenen** selecteert u **Toegang verlenen**.
    2. Selecteer **Meervoudige verificatie vereisen**.
    4. Selecteer **Goedgekeurde client-app vereisen**.
    5. Onder **Voor meerdere besturingselementen** selecteert u **Alle geselecteerde besturingselementen vereisen**. Deze instelling zorgt ervoor dat beide door u geselecteerde vereisten worden afgedwongen wanneer een apparaat toegang tot de e-mailfunctie probeert te krijgen.
    6. Kies **Selecteren**.
     
    ![De Office 365 Exchange Online-app selecteren](media/tutorial-protect-email-on-unmanaged-devices/modern-auth-policy-mfa.png)

8.  Onder **Beleid inschakelen** selecteert u **Aan**.
     
    ![De Office 365 Exchange Online-app selecteren](media/tutorial-protect-email-on-unmanaged-devices/enable-policy.png)

9.  Selecteer **Maken**.

Het beleid voor voorwaardelijke toegang voor clients met moderne verificatie is gemaakt. U kunt nu een beleid maken voor Exchange ActiveSync-clients.

### <a name="create-a-policy-for-exchange-active-sync-clients"></a>Een beleid voor Exchange ActiveSync-clients maken
1.  In Intune selecteert u **Voorwaardelijke toegang** > **Beleid** > **Nieuw beleid**.
2.  Onder **Naam** voert u **Testbeleid voor EAS-clients** in. 
3.  Onder **Toewijzingen** selecteert u **Gebruikers en groepen**. Op het tabblad **Opnemen** selecteert u **Alle gebruikers** en vervolgens **Voltooid**.

4.  Onder **Toewijzingen** selecteert u **Cloud-apps**. Selecteer Office 365 Exchange Online-e-mail aan de hand van de volgende stappen:
     
    1. Op het tabblad **Opnemen** selecteert u **Apps selecteren**.
    2. Kies **Selecteren**. 
    3. In de lijst met toepassingen selecteert u **Office 365 Exchange Online** en vervolgens kiest u **Selecteren**. 
    4. Selecteer **Voltooid**.

5.  Onder **Toewijzingen** selecteert u **Voorwaarden** > **Apparaatplatforms**.
     
    1. Onder **Configureren** selecteert u **Ja**.
    2. Op het tabblad **Opnemen** selecteert u **Elk apparaat** en vervolgens **Voltooid**. 
    3. Selecteer opnieuw **Voltooid**.

6.  Selecteer in het deelvenster **Voorwaarden** de optie **Client-apps**.
     
    1. Onder **Configureren** selecteert u **Ja**.
    2. Selecteer **Mobiele apps en bureaubladclients**.
    3. Selecteer **Exchange ActiveSync-clients** en **Het beleid toepassen op ondersteunde platformen**. 
    4. Schakel alle andere selectievakjes uit.
    5. Selecteer **Voltooid** en vervolgens opnieuw **Voltooid**.
    
    ![De Office 365 Exchange Online-app selecteren](media/tutorial-protect-email-on-unmanaged-devices/eas-client-apps.png)

7.  Onder **Toegangscontroles** selecteert u **Verlenen**. 
     
    1. In het deelvenster **Verlenen** selecteert u **Toegang verlenen**.
    4. Selecteer **Goedgekeurde client-app vereisen**. Schakel alle andere selectievakjes uit.
    6. Kies **Selecteren**.
     
    ![De Office 365 Exchange Online-app selecteren](media/tutorial-protect-email-on-unmanaged-devices/eas-grant-access.png)

8.  Onder **Beleid inschakelen** selecteert u **Aan**.

9.  Selecteer **Maken**.

Uw app-beveiligingsbeleid en voorwaardelijke toegang zijn nu ingesteld en kunnen worden getest. 

## <a name="try-it-out"></a>Beleid uitproberen
Met het beleid dat u hebt gemaakt, moeten apparaten zich inschrijven bij Intune en de mobiele Outlook-app gebruiken om toegang tot Office 365-e-mail te krijgen. Om dit scenario op een iOS-apparaat te testen, probeert u zich aan te melden bij Exchange Online met de referenties van een gebruiker in uw testtenant.
1. Als u dit op een iPhone wilt testen, gaat u naar **Instellingen** > **Wachtwoorden & accounts** > **Account toevoegen** > **Exchange**.
2. Voer het e-mailadres van een gebruiker in uw testtenant in en klik vervolgens op **Volgende**.
3. Klik op **Aanmelden**.
4. Voer het wachtwoord van de testgebruiker in en klik op **Aanmelden** .
5. Het bericht **Er is meer informatie vereist** wordt weergegeven. Dit betekent dat u wordt gevraagd om MFA in te stellen. Stel een extra verificatiemethode in.
6. U ziet nu een bericht dat u deze bron probeert te openen met een app die niet is goedgekeurd door uw IT-afdeling. Dit betekent dat de systeemeigen e-mail-app wordt geblokkeerd. Annuleer de aanmelding.
7.  Open de Outlook-app en selecteer **Instellingen** > **Account toevoegen** > **E-mailaccount toevoegen**.
8. Voer het e-mailadres van een gebruiker in uw testtenant in en klik vervolgens op **Volgende**.
9. Druk op **Aanmelden met Office 365**. U wordt gevraagd om extra verificatie en registratie. Nadat u zich hebt aangemeld, kunt u acties zoals knippen, kopiëren, plakken en 'Opslaan als' testen.

## <a name="clean-up-resources"></a>Resources opschonen
Als het testbeleid niet langer nodig is, kunt u dit verwijderen.
1. Meld u aan bij [Intune](https://aka.ms/intuneportal) als globale beheerder of beheerder van een Intune-service.
2. Selecteer **Apparaatnaleving** > **Beleid**.
3. In de lijst **Naam beleid** selecteert u het contextmenu ( **...** ) voor uw testbeleid, en vervolgens selecteert u **Verwijderen**. Selecteer **OK** om te bevestigen.
4. Selecteer **Voorwaardelijke toegang** > **Beleid**.
5. Selecteer in de lijst **Naam beleid** het contextmenu ( **...** ) voor uw testbeleid en selecteer vervolgens **Verwijderen**. Selecteer **Ja** om te bevestigen.

 ## <a name="next-steps"></a>Volgende stappen 
In deze zelfstudie hebt u app-beveiligingsbeleid gemaakt om te beperken wat de gebruiker kan doen met de Outlook-app. Ook hebt u beleid voor voorwaardelijke toegang gemaakt om gebruik van de Outlook-app te vereisen en MFA te vereisen voor clients met moderne verificatie. Zie, voor meer informatie over het gebruik van Intune met voorwaardelijke toegang om andere apps en diensten te beschermen, [Voorwaardelijke toegang instellen](conditional-access.md).
