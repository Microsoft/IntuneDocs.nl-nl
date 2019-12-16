---
title: Voorwaarden instellen in Microsoft Intune
titleSuffix: ''
description: Voorwaarden instellen die voor gebruikers worden weergegeven in de bedrijfsportal voor Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/20/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: amyro
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3fb5818609763753878fec7a84fd8c19eb154f88
ms.sourcegitcommit: e75718ee6cf93c0e6c915f2776b785fe8db9f7e0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/10/2019
ms.locfileid: "74955436"
---
# <a name="terms-and-conditions-for-user-access"></a>Voorwaarden voor gebruikerstoegang

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Als Intune-beheerder kunt u vereisen dat gebruikers de voorwaarden van uw bedrijf accepteren voordat ze de bedrijfsportal-app voor de volgende zaken gebruiken:
- apparaten inschrijven
- resources openen, zoals bedrijfs-apps en hun Postvak IN.

De configuratie van voorwaarden is optioneel.

U kunt meerdere sets met voorwaarden maken en deze toewijzen aan verschillende groepen om bijvoorbeeld verschillende talen te ondersteunen.

Er zijn twee manieren om algemene voorwaarden op te stellen voor uw bedrijf:
- met behulp van Intune, zoals beschreven in dit artikel.
- met behulp van de [Azure Active Directory-functie voor gebruiksvoorwaarden](https://docs.microsoft.com/azure/active-directory/governance/active-directory-tou)

Als u wilt weten welke methode voor u het beste is, bekijkt u de [blog De juiste voorwaardenoptie kiezen voor uw organisatie](https://go.microsoft.com/fwlink/?linkid=2010506&clcid=0x409). 

## <a name="create-terms-and-conditions"></a>Voorwaarden maken
Voer deze stappen uit om voorwaarden te maken. De weergavenaam en beschrijving zijn bedoeld voor beheerders. De eigenschappen van de voorwaarden worden in de bedrijfsportal weergegeven aan gebruikers.

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431), kies **Tenantbeheer** > **Voorwaarden**.
2. Kies **Maken**.
3. Geef op de pagina **Basisinformatie** de volgende gegevens op:

   - **Naam**: De naam voor de voorwaarden in de Azure-portal. Gebruikers krijgen deze naam niet te zien.
   - **Beschrijving**: Optionele informatie aan de hand waarvan u deze set voorwaarden in de Azure-portal kunt herkennen.

    ![Schermafbeelding van de Azure-portal met de pagina Basisinformatie voor voorwaarden](./media/terms-and-conditions-create/terms-basics-page.png)

4. Kies **Volgende** om naar de pagina **Voorwaarden** te gaan en geef de volgende gegevens op:

   - **Titel**: De naam voor de voorwaarden die in de bedrijfsportal worden weergegeven boven de **Samenvatting**.
   - **Voorwaarden**: De voorwaarden die gebruikers te zien krijgen en die ze moeten accepteren of weigeren.
   - **Overzicht van voorwaarden**: Tekst waarin wordt uitgelegd wat het betekent als gebruikers de voorwaarden accepteren. Bijvoorbeeld: "Door uw apparaat te registreren, stemt u in met de gebruiksvoorwaarden zoals uiteengezet door Contoso. Lees de voorwaarden door voordat u verdergaat."

5. Kies **Volgende** om naar de pagina **Bereiktags** te gaan.

6. Kies **Bereiktags selecteren**, selecteer de bereiktags die u aan deze voorwaarden wilt toewijzen en kies vervolgens **Selecteren**. 

7. Kies **Volgende** om naar de pagina **Toewijzingen** te gaan en kies een van de volgende opties voor **Toewijzen aan**:
    - **Alle gebruikers**: Kies deze optie als u deze voorwaarden wilt toewijzen aan alle gebruikers.
    - **Groepen selecteren**: Kies deze optie als u deze voorwaarden wilt toewijzen aan iedereen in de groepen die u opgeeft door **Groepen selecteren die moeten worden opgenomen** te kiezen.

8. Kies **Volgende** > **Maken**.

## <a name="see-how-terms-are-displayed-to-your-users"></a>Zie hoe voorwaarden worden weergegeven voor uw gebruikers
In het volgende voorbeeld worden de **titel** en **samenvatting van de voorwaarden** in de beheerconsole en de bedrijfsportal weergegeven.

![Schermopname van de titel en samenvatting van de voorwaarden in de beheerconsole en de bedrijfsportal.](./media/terms-and-conditions-create/terms-summary-terms.png)

In het volgende voorbeeld worden de voorwaarden in de beheerconsole en de bedrijfsportal weergegeven.

![Schermopname van de voorwaarden in de beheerconsole en de bedrijfsportal.](./media/terms-and-conditions-create/terms-properties-terms.png)


## <a name="monitor-terms-and-conditions"></a>Voorwaarden controleren

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431), kies **Tenantbeheer** > **Voorwaarden**.
2. Selecteer in de lijst met voorwaarden de voorwaarden die u wilt weergeven en selecteer vervolgens **Acceptatierapporten**.

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a>Werken met meerdere versies van voorwaarden
U kunt de voorwaarden bewerken en de versies van de voorwaarden beheren. Elke keer dat u een belangrijke wijziging doorvoert in uw voorwaarden, moet u:
- het versienummer verhogen
- vereisen dat gebruikers de nieuwe voorwaarden accepteren

Behoud het huidige versienummer als u bijvoorbeeld typfouten herstelt of de opmaak wijzigt.

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431), kies **Tenantbeheer** > **Voorwaarden** > kies de voorwaarden die u wilt wijzigen > **Eigenschappen**.

2. Selecteer in het deelvenster **Eigenschappen** de optie **Voorwaarden** en pas vervolgens **Titel**, **Overzicht van voorwaarden** en **Voorwaarden** naar wens aan. Als gebruikers de nieuwe voorwaarden naar aanleiding van de aangebrachte wijzigingen opnieuw moeten accepteren, selecteert u **Gebruikers moeten de voorwaarden opnieuw accepteren en het versienummer bijwerken naar**

3. Kies **OK** > **Opslaan**.

Gebruikers hoeven de bijgewerkte voorwaarden slechts één keer te accepteren. Gebruikers met meerdere apparaten hoeven de voorwaarden niet voor elk apparaat te accepteren.
