---
title: Zelfstudie - Slack configureren om Intune te gebruiken voor de configuratie van EMM en de app
titleSuffix: Microsoft Intune
description: In deze zelfstudie wordt behandeld hoe u Slack configureert om Intune te gebruiken voor de configuratie van EMM en de app.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/09/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 55db37c5-0da7-4d9c-8027-525afb1c6349
Customer intent: As an Intune admin, I want to learn how to configure Slack to use Intune for EMM and app configuration..
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 86e9d100847641064f472f0c3da0c9ec694f72dd
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72496719"
---
# <a name="tutorial-configure-slack-to-use-intune-for-emm-and-app-configuration"></a>Zelfstudie: Slack configureren om Intune te gebruiken voor de configuratie van EMM en de app

Slack is een samenwerkings-app die u kunt gebruiken met Microsoft Intune.   

In deze zelfstudie doet u het volgende:
> [!div class="checklist"]
> - Intune als de Enterprise Mobility Management (EMM)-provider instellen in uw Slack Enterprise Grid. U kunt de toegang tot de werkruimten van uw Grid-abonnement beperken tot door Intune beheerde apparaten.
> - App-configuratiebeleid maken voor beheer van de Slack voor EMM-app voor iOS en de Slack-app voor apparaten met een Android-werkprofiel.
> - Intune-nalevingsbeleid voor apparaten maken om de voorwaarden in te stellen waaraan Android- en iOS-apparaten moeten voldoen om als conform te worden beschouwd.

Als u niet over een Intune-abonnement beschikt, kunt u [zich registreren voor een gratis proefaccount](../fundamentals/free-trial-sign-up.md).

## <a name="prerequisites"></a>Vereisten
Voor deze zelfstudie hebt u een testtenant nodig met de volgende abonnementen:
- Azure Active Directory Premium ([ gratis proefversie](https://azure.microsoft.com/free/?WT.mc_id=A261C142F))
- Intune-abonnement ([gratis proefversie](../fundamentals/free-trial-sign-up.md))

U hebt ook een [Slack Enterprise Grid](https://get.slack.help/hc/articles/360004150931-What-is-Slack-Enterprise-Grid-)-abonnement nodig.

## <a name="configure-your-slack-enterprise-grid-plan"></a>Uw Slack Enterprise Grid-abonnement configureren
Schakel EMM in voor uw Slack Enterprise Grid-abonnement met behulp van de [instructies van Slack](https://get.slack.help/hc/articles/115002579426-Enable-Enterprise-Mobility-Management-for-your-org#step-2:-turn-on-emm) en [koppel uw Azure Active Directory](https://docs.microsoft.com/azure/active-directory/saas-apps/slack-tutorial) als de id-provider (IDP) van uw Grid-abonnement.

## <a name="sign-in-to-intune"></a>Aanmelden bij Intune
Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) als globale beheerder of beheerder van een Intune-service. Als u een Intune-proefabonnement hebt gemaakt, is het account waarmee u het abonnement hebt gemaakt de globale beheerder.

## <a name="set-up-slack-for-emm-on-ios-devices"></a>Slack voor EMM instellen op iOS-apparaten
Voeg de iOS-app Slack voor EMM toe aan uw Intune-tenant en maak app-configuratiebeleid om de iOS-gebruikers binnen uw organisatie toegang te geven tot Slack met Intune als een EMM-provider.

### <a name="add-slack-for-emm-to-intune"></a>Slack voor EMM toevoegen aan Intune
Voeg Slack voor EMM toe als een beheerde iOS-app in Intune en wijs uw Slack-gebruikers toe. Apps zijn platformspecifiek, dus moet u een afzonderlijke Intune-app toevoegen voor uw Slack-gebruikers met Android-apparaten.
1. Selecteer in Intune de optie **Client-apps** > **Apps** > **Toevoegen**.
2. Selecteer bij Toepassingstype **Store-app - iOS**.
3. Selecteer **Zoeken in de App Store**. Voer de zoekterm 'Slack voor EMM' in en selecteer de app.
4. Selecteer **App-gegevens** en wijzig de configuratie naar wens.
5. Selecteer **Toevoegen**.
6. Voer in de zoekbalk 'Slack voor EMM' in en selecteer de app die u zojuist hebt toegevoegd.
7. Selecteer bij Beheren **Toewijzingen**.
8. Selecteer **Groep toevoegen**. Afhankelijk van wie u hiervoor hebt aangewezen bij het inschakelen van EMM voor Slack, kunt u onder **Toewijzingstype** de volgende opties selecteren:
    - **Beschikbaar voor ingeschreven apparaten**, indien u hebt gekozen voor 'Alle leden (inclusief gasten)', of
    - **Beschikbaar met of zonder inschrijving**, als u hebt gekozen voor 'Alle leden (met uitzondering van gasten)' of 'Optioneel'.
9. Selecteer **Opgenomen groepen** en selecteer bij Deze app beschikbaar maken voor alle gebruikers **Ja**.
10. Klik op **OK** en klik vervolgens nogmaals op **OK**.
11. Klik op **Opslaan**.

### <a name="add-an-app-configuration-policy-for-slack-for-emm"></a>Een app-configuratiebeleid toevoegen voor Slack voor EMM
Voeg een app-configuratiebeleid toe voor Slack voor EMM iOS. App-configuratiebeleidsregels voor beheerde apparaten zijn platform-specifiek, dus u moet een afzonderlijk beleid toevoegen voor uw Slack-gebruikers met Android-apparaten.
1. Selecteer in Intune **Client-apps** > **App-configuratiebeleid** > **Toevoegen**.
2. Voer bij Naam het volgende in: Testbeleid Slack-app-configuratie.
3. Selecteer bij Type apparaatregistratie **Beheerde apparaten**.
4. Selecteer bij Platform **iOS**.
5. Selecteer **Gekoppelde app**.
6. Voer in de zoekbalk 'Slack voor EMM' in en selecteer de app.
7. Klik op **OK** en selecteer vervolgens **Configuratie-instellingen**. 
8. Selecteer **OK** en selecteer vervolgens **Toevoegen**.
9. Voer in de zoekbalk 'Testbeleid Slack-app-configuratie' in en selecteer het beleid dat u zojuist hebt toegevoegd.
10. Selecteer bij Beheren **Toewijzingen**.
11. Selecteer bij Toewijzen aan **Alle gebruikers + alle apparaten**.
12. Klik op **Opslaan**.

### <a name="optional-create-an-ios-device-compliance-policy"></a>(Optioneel) Nalevingsbeleid voor iOS-apparaten maken
Stel in Intune een nalevingsbeleid voor apparaten in om de voorwaarden te bepalen waaraan een apparaat moet voldoen om als conform te worden beschouwd. In deze zelfstudie maken we een nalevingsbeleid voor iOS-apparaten. Nalevingsbeleid is platform-specifiek, dus u moet een afzonderlijk beleid maken voor uw Slack-gebruikers met Android-apparaten.
1. In Intune selecteert u **Apparaatconformiteit** > **Beleid** > **Beleid maken**.
2. Bij Naam voert u 'Test iOS-nalevingsbeleid' in.
3. Bij Beschrijving voert u 'Test iOS-nalevingsbeleid' in.
4. Selecteer bij Platform **iOS**.
5. Selecteer **Apparaatstatus**. Naast Apparaten met jailbreak selecteert u **Blokkeren** en vervolgens selecteert u **OK**.
6. Selecteer **Systeembeveiliging** en voer de Wachtwoordinstellingen in. Voor deze zelfstudie selecteert u de volgende aanbevolen instellingen:
    - Voor Wachtwoord vereisen voor het ontgrendelen van mobiele apparaten selecteert u **Vereisen**.
    - Voor Eenvoudige wachtwoorden, selecteert u **Blokkeren**.
    - Voor Minimale wachtwoordlengte voert u 4 in.
    - Voor Vereist wachtwoordtype kiest u **Alfanumeriek**.
    - Voor Max. aantal minuten na schermvergrendeling voordat wachtwoord is vereist kiest u **Onmiddellijk**.
    - Voor Verlooptijd wachtwoord (dagen) voert u 41 in.
    - Voor Aantal vorige wachtwoorden dat niet opnieuw mag worden gebruikt voert u 5 in.
7. Selecteer **OK** en vervolgens weer **OK**.
8. Klik op **Maken**.

## <a name="set-up-slack-on-android-work-profile-devices"></a>Slack instellen op apparaten met een Android-werkprofiel
Voeg de beheerde Google Play-app van Slack toe aan uw Intune-tenant en maak app-configuratiebeleid om de Android-gebruikers binnen uw organisatie toegang te geven tot Slack met Intune als een EMM-provider.

### <a name="add-slack-to-intune"></a>Slack toevoegen aan Intune
Voeg Slack toe als een beheerde Google Play-app in Intune en wijs uw Slack-gebruikers toe. Apps zijn platformspecifiek, dus moet u een afzonderlijke Intune-app toevoegen voor uw Slack-gebruikers met iOS-apparaten.
1. Selecteer in Intune de optie **Client-apps** > **Apps** > **Toevoegen**.
2. Selecteer onder App-type **Store-app: beheerde Google Play**.
3. Selecteer **Beheerde Google Play: Goedkeuren**. Voer de zoekterm 'Slack voor EMM' in en selecteer de app.
4. Selecteer **Goedkeuren**.
5. Voer in de zoekbalk 'Slack' in en selecteer de app die u zojuist hebt toegevoegd.
6. Selecteer bij Beheren **Toewijzingen**.
7. Selecteer **Groep toevoegen**. Afhankelijk van wie u hiervoor hebt aangewezen bij het inschakelen van EMM voor Slack, kunt u onder **Toewijzingstype** de volgende opties selecteren:
    - **Beschikbaar voor ingeschreven apparaten**, indien u hebt gekozen voor 'Alle leden (inclusief gasten)', of
    - **Beschikbaar met of zonder inschrijving**, als u hebt gekozen voor 'Alle leden (met uitzondering van gasten)' of 'Optioneel'.
8. Selecteer Opgenomen groepen en selecteer bij Deze app beschikbaar maken voor alle gebruikers **Ja**.
9. Klik op **OK** en klik vervolgens nogmaals op **OK**.
10. Klik op **Opslaan**.

### <a name="add-an-app-configuration-policy-for-slack"></a>Een app-configuratiebeleid toevoegen voor Slack
Voeg een app-configuratiebeleid toe voor Slack. App-configuratiebeleidsregels voor beheerde apparaten zijn platform-specifiek, dus u moet een afzonderlijk beleid toevoegen voor uw Slack-gebruikers met iOS-apparaten.
1. Selecteer in Intune **Client-apps** > **App-configuratiebeleid** > **Toevoegen**.
2. Voer bij Naam het volgende in: Testbeleid Slack-app-configuratie.
3. Selecteer bij Type apparaatregistratie **Beheerde apparaten**.
4. Selecteer voor Platform de optie **Android**.
5. Selecteer **Gekoppelde app**.
6. Voer in de zoekbalk 'Slack' in en selecteer de app.
7. Klik op **OK** en selecteer vervolgens **Configuratie-instellingen**.
    - Voor informatie over configuratiesleutels en hun waarden, raadpleegt u de documentatie op het tabblad 'Technisch' van [de AppConfig-webpagina van Slack](https://www.appconfig.org/company/slack/).
8. Selecteer **OK** en selecteer vervolgens **Toevoegen**.
9. Voer in de zoekbalk 'Testbeleid Slack-app-configuratie' in en selecteer het beleid dat u zojuist hebt toegevoegd.
10. Selecteer bij Beheren **Toewijzingen**.
11. Selecteer bij Toewijzen aan **Alle gebruikers + alle apparaten**.
12. Klik op **Opslaan**.

### <a name="optional-create-an-android-device-compliance-policy"></a>(Optioneel) Nalevingsbeleid voor Android-apparaten maken
Stel in Intune een nalevingsbeleid voor apparaten in om de voorwaarden te bepalen waaraan een apparaat moet voldoen om als conform te worden beschouwd. In deze zelfstudie maken we een nalevingsbeleid voor Android-apparaten. Nalevingsbeleid is platform-specifiek, dus u moet een afzonderlijk beleid maken voor uw Slack-gebruikers met iOS-apparaten.
1. In Intune selecteert u **Apparaatconformiteit** > **Beleid** > **Beleid maken**.
2. Bij Naam voert u 'Test Android-nalevingsbeleid' in.
3. Bij Beschrijving voert u 'Test Android-nalevingsbeleid' in.
4. Selecteer voor Platform de optie **Android Enterprise**.
5. Selecteer onder Profieltype **Werkprofiel**.
6. Selecteer **Apparaatstatus**. Naast Apparaten met roottoegang selecteert u **Blokkeren** en vervolgens selecteert u **OK**.
7. Selecteer **Systeembeveiliging** en voer de **Wachtwoordinstellingen** in. Voor deze zelfstudie selecteert u de volgende aanbevolen instellingen:
    - Voor Wachtwoord vereisen voor het ontgrendelen van mobiele apparaten selecteert u **Vereisen**.
    - Voor Vereist wachtwoordtype kiest u **Ten minste alfanumeriek**.
    - Voor Minimale wachtwoordlengte voert u 4 in.
    - Voor Maximaal aantal minuten na schermvergrendeling voordat wachtwoord is vereist kiest u **15 minuten**.
    - Voor Verlooptijd wachtwoord (dagen) voert u 41 in.
    - Voor Aantal vorige wachtwoorden dat niet opnieuw mag worden gebruikt voert u 5 in.
8. Klik op **OK** en klik vervolgens nogmaals op **OK**.
9. Klik op **Maken**.

## <a name="launch-slack"></a>Slack starten

Door het beleid dat u zojuist hebt gemaakt, wordt afgedwongen dat ieder iOS- of Android-apparaat met een werkprofiel dat zich probeert aan te melden bij een van uw werkruimten in Intune moet worden ingeschreven. Als u dit scenario wilt testen, probeert u Slack voor EMM te starten op een iOS-apparaat dat is ingeschreven bij Intune of probeert u Slack te starten op een apparaat met een Android-werkprofiel dat is ingeschreven bij Intune. 

## <a name="next-steps"></a>Volgende stappen

In deze zelfstudie hebt u het volgende gedaan:
- Intune als de Enterprise Mobility Management (EMM)-provider instellen in uw Slack Enterprise Grid. 
- App-configuratiebeleid maken voor beheer van de Slack voor EMM-app voor iOS en de Slack-app voor apparaten met een Android-werkprofiel.
- Intune-nalevingsbeleid voor apparaten maken om de voorwaarden in te stellen waaraan Android- en iOS-apparaten moeten voldoen om als conform te worden beschouwd.

Zie [App-configuratiebeleidsregels voor Microsoft Intune](app-configuration-policies-overview.md) voor meer informatie over app-configuratiebeleid. Zie [Regels instellen op apparaten om toegang tot resources in uw organisatie met behulp van Intune toe te staan](../protect/device-compliance-get-started.md) voor meer informatie over apparaatnalevingsbeleid.
