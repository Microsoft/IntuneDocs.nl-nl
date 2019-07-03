---
title: Zelfstudie - Exchange Online e-mail beschermen op Intune-beheerde apparaten
titleSuffix: Microsoft Intune
description: Meer informatie over hoe u Exchange Online kunt beveiligen met iOS Intune-nalevingsbeleid en Azure AD-voorwaardelijke toegang, door beheerde apparaten en de Outlook-app vereist te maken.
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
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a7ab0ecd2802e68dbac32b757e472a74e697da13
ms.sourcegitcommit: 7315fe72b7e55c5dcffc6d87f185f3c2cded9028
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/02/2019
ms.locfileid: "67530743"
---
# <a name="tutorial-protect-exchange-online-email-on-managed-devices"></a>Zelfstudie: Exchange Online e-mail beschermen op beheerde apparaten
Hier vindt u meer informatie over het gebruik van het nalevingsbeleid voor apparaten met voorwaardelijke toegang. Hiermee kunt u ervoor zorgen dat iOS-apparaten uitsluitend toegang tot Exchange Online e-mail hebben als ze door Intune worden beheerd en een goedgekeurde e-mailapplicatie gebruiken. 

In deze zelfstudie leert u het volgende: 
> [!div class="checklist"]
> * Een nalevingsbeleid voor iOS-apparaten in Intune maken om de voorwaarden in te stellen waaraan een apparaat moet voldoen om als conform te worden beschouwd.
> * Een voorwaardelijk toegangsbeleid in Azure Active Directory (Azure AD) maken dat vereist dat iOS-apparaten zich inschrijven bij Intune, voldoen aan het Intune-beleid en de goedgekeurde mobiele Outlook-app gebruiken om toegang te krijgen tot Exchange Online e-mail.

Als u niet over een Intune-abonnement beschikt, kunt u [zich registreren voor een gratis proefaccount](free-trial-sign-up.md).

## <a name="prerequisites"></a>Vereisten
  - Voor deze zelfstudie hebt u een testtenant nodig met de volgende abonnementen:
    - Azure Active Directory Premium ([ gratis proefversie](https://azure.microsoft.com/free/?WT.mc_id=A261C142F))
    - Office 365 Business-abonnement inclusief Exchange ([ gratis proefversie](https://go.microsoft.com/fwlink/p/?LinkID=510938))
  - Voordat u begint, maakt u een test-apparaatprofiel voor iOS-apparaten aan door de stappen in de [Snelstartgids: Een e-mailprofiel voor een apparaat voor iOS maken](quickstart-email-profile.md) te volgen.

## <a name="sign-in-to-intune"></a>Aanmelden bij Intune

Meld u aan bij [Intune](https://aka.ms/intuneportal) als globale beheerder of beheerder van een Intune-service. Als u een Intune-proefabonnement hebt gemaakt, is het account waarmee u het abonnement hebt gemaakt de globale beheerder.

## <a name="create-the-ios-device-compliance-policy"></a>Nalevingsbeleid voor iOS-apparaten maken
Stel in Intune een nalevingsbeleid voor apparaten in om de voorwaarden te bepalen waaraan een apparaat moet voldoen om als conform te worden beschouwd. In deze zelfstudie maken we een nalevingsbeleid voor iOS-apparaten. Elk nalevingsbeleid is platformspecifiek, dus u hebt een apart nalevingsbeleid nodig voor elk platform dat u wilt evalueren.

1. In Intune selecteert u **Apparaatconformiteit** > **Beleid** > **Beleid maken**.
2. Onder **Naam** voert u **Test iOS-nalevingsbeleid** in. 
3. Onder **Beschrijving** voert u **Test iOS-nalevingsbeleid** in.
4. Onder **Platform** selecteert u **iOS**. 
5. Selecteer **Instellingen** > **E-mail**. 
     
    1.  Naast **Vereisen dat mobiele apparaten een beheerd e-mailprofiel hebben** selecteert u **Vereisen**.
    2. Selecteer **OK**.

    ![Nalevingsbeleid voor e-mail zodanig instellen dat een beheerd e-mailprofiel is vereist](media/tutorial-protect-email-on-enrolled-devices/ios-compliance-policy-email.png)
    
6. Selecteer **Apparaatstatus**. Naast **Opengebroken apparaten** selecteert u **Blokkeren**, en vervolgens selecteert u **OK**.
7. Selecteer **Systeembeveiliging** en voer de **Wachtwoordinstellingen** in. Voor deze zelfstudie selecteert u de volgende aanbevolen instellingen:
     
    - Voor **Wachtwoord vereisen voor het ontgrendelen van mobiele apparaten** selecteert u **Vereisen**.
    - Voor **Eenvoudige wachtwoorden**, selecteert u **Blokkeren**.
    - Voor **Minimale wachtwoordlengte** voert u **4** in.
    - Voor **Vereist wachtwoordtype** kiest u **Alfanumeriek**.
    - Voor **Max. aantal minuten na schermvergrendeling voordat wachtwoord is vereist** kiest u **Onmiddellijk**.
    - Voor **Verlooptijd wachtwoord (dagen)** voert u **41** in.
    - Voor **Aantal vorige wachtwoorden dat niet opnieuw mag worden gebruikt** voert u **5** in.
 
    ![Wachtwoordinstellingen uitvoeren voor het nalevingsbeleid voor e-mail](media/tutorial-protect-email-on-enrolled-devices/ios-compliance-policy-system-security.png)

8. Selecteer **OK** en vervolgens weer **OK**.
9. Selecteer **Maken**.

## <a name="create-the-conditional-access-policy"></a>Voorwaardelijk toegangsbeleid maken
Nu gaan we een voorwaardelijk toegangsbeleid maken dat vereist dat alle apparaatplatforms zich inschrijven bij Intune en voldoen aan ons Intune-nalevingsbeleid, voordat ze toegang krijgen tot Exchange Online. Ook maken we de Outlook-app vereist voor toegang tot de e-mailfunctie. Het voorwaardelijke toegangsbeleid kan in de Azure AD- of Intune-portal worden geconfigureerd. Omdat we al in de Intune-portal zitten, maken we daarin het beleid.
1. In Intune selecteert u **Voorwaardelijke toegang** > **Beleid** > **Nieuw beleid**.
1.  Onder **Naam**, voert u **Testbeleid voor Office 365 e-mail** in. 
3. Onder **Toewijzingen** selecteert u **Gebruikers en groepen**. Op het tabblad **Opnemen** selecteert u **Alle gebruikers** en vervolgens **Voltooid**.

4. Onder **Toewijzingen** selecteert u **Cloud-apps**. Omdat we Office 365 Exchange Online e-mail willen beschermen, selecteren we deze functie via de volgende stappen:
     
    1. Op het tabblad **Opnemen** selecteert u **Apps selecteren**.
    2. Kies **Selecteren**. 
    3. In de lijst met toepassingen selecteert u **Office 365 Exchange Online** en vervolgens kiest u **Selecteren**. 
    4. Selecteer **Voltooid**.
  
    ![De Office 365 Exchange Online-app selecteren](media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-cloud-apps.png)

5. Onder **Toewijzingen** selecteert u **Voorwaarden** > **Apparaatplatforms**.
     
    1. Onder **Configureren** selecteert u **Ja**.
    2. Op het tabblad **Opnemen** selecteert u **Elk apparaat** en vervolgens **Voltooid**. 
    3. Selecteer opnieuw **Voltooid**.
   
    ![De Office 365 Exchange Online-app selecteren](media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-cloud-device-platforms.png)

6. Onder **Toewijzingen** selecteert u **Voorwaarden** > **Client-apps**.
     
    1. Onder **Configureren** selecteert u **Ja**.
    2. Voor deze zelfstudie selecteert u **Mobiele apps en bureaubladclients** en **Moderne verificatieclients** (dit verwijst naar apps zoals Outlook voor iOS en voor Android). Schakel alle andere selectievakjes uit.
    3. Selecteer **Voltooid** en vervolgens opnieuw **Voltooid**.
    
    ![De Office 365 Exchange Online-app selecteren](media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-client-apps.png)

7. Onder **Toegangscontroles** selecteert u **Verlenen**. 
     
    1. In het deelvenster **Verlenen** selecteert u **Toegang verlenen**.
    2. Selecteer **Vereisen dat het apparaat als conform is gemarkeerd**. 
    3. Selecteer **Goedgekeurde client-app vereisen**.
    4. Onder **Voor meerdere besturingselementen** selecteert u **Alle geselecteerde besturingselementen vereisen**. Deze instelling zorgt ervoor dat beide door u geselecteerde vereisten worden afgedwongen wanneer een apparaat toegang tot de e-mailfunctie probeert te krijgen.
    5. Kies **Selecteren**.
     
    ![De Office 365 Exchange Online-app selecteren](media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-grant-access.png)

8. Onder **Beleid inschakelen** selecteert u **Aan**.
     
    ![De Office 365 Exchange Online-app selecteren](media/tutorial-protect-email-on-enrolled-devices/ios-ca-policy-enable-policy.png)

9. Selecteer **Maken**.

## <a name="try-it-out"></a>Beleid uitproberen
Met het beleid dat u hebt gemaakt, moet elk iOS-apparaat dat probeert om zich bij Office 365 e-mail aan te melden, zich inschrijven bij Intune en ook de mobiele Outlook-app voor iOS gebruiken. Om dit scenario op een iOS-apparaat te testen, probeert u zich aan te melden bij Exchange Online met de referenties van een gebruiker in uw testtenant. U wordt gevraagd om het apparaat in te schrijven en de mobiele Outlook-app te installeren.
1. Als u dit op een iPhone wilt testen, gaat u naar **Instellingen** > **Wachtwoorden & accounts** > **Account toevoegen** > **Exchange**.
2. Voer het e-mailadres van een gebruiker in uw testtenant in en klik vervolgens op **Volgende**.
3. Klik op **Aanmelden**.
4. Voer het wachtwoord van de testgebruiker in en klik op **Aanmelden** .
5. Er verschijnt een bericht dat zegt dat uw apparaat beheerd moet zijn om toegang te krijgen tot de resource. Tegelijk verschijnt een optie voor inschrijving. 

## <a name="clean-up-resources"></a>Resources opschonen
Als het testbeleid niet langer nodig is, kunt u dit verwijderen.
1. Meld u aan bij [Intune](https://aka.ms/intuneportal) als globale beheerder of beheerder van een Intune-service.
2. Selecteer **Apparaatnaleving** > **Beleid**.
3. In de lijst **Naam beleid** selecteert u het contextmenu ( **...** ) voor uw testbeleid, en vervolgens selecteert u **Verwijderen**. Selecteer **OK** om te bevestigen.
4. Selecteer **Voorwaardelijke toegang** > **Beleid**.
5. In de lijst **Naam beleid** selecteert u het contextmenu ( **...** ) voor uw testbeleid, en vervolgens selecteert u **Verwijderen**. Selecteer **Ja** om te bevestigen.

## <a name="next-steps"></a>Volgende stappen 
In deze tutorial hebt u beleid gemaakt dat vereist dat iOS-apparaten zich inschrijven bij Intune en de Outlook-app gebruiken om toegang te krijgen tot Exchange Online e-mail. Voor meer informatie over het gebruik van Intune met voorwaardelijke toegang om andere apps en diensten te beschermen (waaronder Exchange ActiveSync-clients voor Office 365 Exchange Online), zie [Voorwaardelijke toegang instellen](conditional-access.md).
