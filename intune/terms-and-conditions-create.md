---
title: Voorwaarden instellen in Microsoft Intune
titlesuffix: ''
description: Voorwaarden instellen die voor gebruikers worden weergegeven in de bedrijfsportal voor Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: amyro
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: d126852366ff67adbbfecd2eb5ebe14a129c5945
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55839225"
---
# <a name="terms-and-conditions-for-user-access"></a>Voorwaarden voor gebruikerstoegang

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Als Intune-beheerder kunt u vereisen dat gebruikers de voorwaarden van uw bedrijf accepteren voordat ze de bedrijfsportal-app voor de volgende zaken gebruiken:
- apparaten inschrijven
- resources openen, zoals bedrijfs-apps en hun Postvak IN.    
De configuratie van voorwaarden is optioneel.

U kunt meerdere sets met voorwaarden maken en deze toewijzen aan verschillende groepen om bijvoorbeeld verschillende talen te ondersteunen.

Er zijn twee manieren om algemene voorwaarden op te stellen voor uw bedrijf:
- met behulp van Intune, zoals beschreven in dit artikel.
- met behulp van de [Azure Active Directory-functie voor gebruiksvoorwaarden](https://docs.microsoft.com/azure/active-directory/governance/active-directory-tou) Als u wilt weten welke methode voor u het beste is, bekijkt u [de blog De juiste voorwaardenoptie kiezen voor uw organisatie](https://go.microsoft.com/fwlink/?linkid=2010506&clcid=0x409). 

## <a name="create-terms-and-conditions"></a>Voorwaarden maken
Voer deze stappen uit om voorwaarden te maken. De weergavenaam en beschrijving zijn bedoeld voor beheerders. De eigenschappen van de voorwaarden worden in de bedrijfsportal weergegeven aan gebruikers.

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies in het deelvenster **Intune** de optie **Apparaatinschrijving** > **Algemene voorwaarden**.
2. Kies **Maken**.
![Schermafbeelding van de Azure-portal met de knop Maken voor het maken van voorwaarden](media/terms-create-terms.png)
3. Geef op het uitgevouwen deelvenster de volgende gegevens op:

   - **Weergavenaam**: De naam voor de voorwaarden in de Azure-portal. Gebruikers krijgen deze naam niet te zien.

   - **Beschrijving**: Optionele informatie aan de hand waarvan u deze set voorwaarden in de Azure-portal kunt herkennen.

4. Selecteer de pijl naast **Gebruiksvoorwaarden definiëren** om het deelvenster Voorwaarden te openen. Voer de volgende informatie in:

   ![Schermopname van het scherm voor het accepteren van voorwaarden door gebruikers met een overzicht van de voorwaarden](./media/terms-summary-create.png)

   - **Titel**: De naam voor de voorwaarden die in de bedrijfsportal worden weergegeven boven de **Samenvatting**.
   - **Overzicht van voorwaarden**: Tekst waarin wordt uitgelegd wat het betekent als gebruikers de voorwaarden accepteren. Bijvoorbeeld: "Door uw apparaat te registreren, stemt u in met de gebruiksvoorwaarden zoals uiteengezet door Contoso. Lees de voorwaarden door voordat u verdergaat."
   - **Voorwaarden**: De voorwaarden die gebruikers te zien krijgen en die ze moeten accepteren of weigeren.

5. Kies **OK** > **Maken**.

## <a name="see-how-terms-are-displayed-to-your-users"></a>Zie hoe voorwaarden worden weergegeven voor uw gebruikers
In het volgende voorbeeld worden de **titel** en **samenvatting van de voorwaarden** in de beheerconsole en de bedrijfsportal weergegeven.

![Schermopname van de titel en samenvatting van de voorwaarden in de beheerconsole en de bedrijfsportal.](./media/terms-summary-terms.png)

In het volgende voorbeeld worden de voorwaarden in de beheerconsole en de bedrijfsportal weergegeven.

![Schermopname van de voorwaarden in de beheerconsole en de bedrijfsportal.](./media/terms-properties-terms.png)

## <a name="assign-terms-and-conditions"></a>Voorwaarden toewijzen

U kunt voorwaarden toewijzen aan groepen gebruikers die ze moeten accepteren voordat ze de bedrijfsportal kunnen gebruiken.

1. Kies in de Azure-portal achtereenvolgens **Apparaatinschrijving** en **Voorwaarden**.
2. Selecteer in de lijst met voorwaarden de voorwaarden die u wilt toewijzen > **Beheren** > **Toewijzingen**.
![Schermopname van het deelvenster Groep toewijzen van Azure Portal waarop de knoppen Groep selecteren en Selecteren worden weergegeven voor het toewijzen van voorwaarden](media/terms-assign-groups.png)
3. Klik op **Groepen selecteren om op te nemen** > selecteer de groepen waaraan u de voorwaarden wilt toewijzen > **Selecteren**. Er kunnen geen voorwaarden worden toegewezen aan dynamische groepen.
4. Selecteer in het deelvenster **Toegewezen groepen** de optie **Opslaan**.  De voorwaarden zijn nu toegewezen aan gebruikers in de geselecteerde groepen. De volgende keer dat gebruikers de bedrijfsportal proberen te openen, wordt ze gevraagd de voorwaarden te accepteren. U hoeft de voorwaarden slechts één keer te accepteren. Gebruikers met meerdere apparaten hoeven de voorwaarden niet voor elk apparaat te accepteren.


## <a name="monitor-terms-and-conditions"></a>Voorwaarden controleren

1. Kies in Azure-portal **Alle services** > **Bewaking en beheer** > **Intune**. 
1. Kies in het deelvenster Intune **Apparaatinschrijving** > **Algemene voorwaarden**.
2. Selecteer in de lijst met voorwaarden de voorwaarden die u wilt weergeven en selecteer vervolgens **Acceptatierapporten**.

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a>Werken met meerdere versies van voorwaarden
U kunt de voorwaarden bewerken en de versies van de voorwaarden beheren. Elke keer dat u een belangrijke wijziging doorvoert in uw voorwaarden, moet u:
- het versienummer verhogen
- eisen dat gebruikers de nieuwe voorwaarden accepteren Houd het huidige versienummer als u bijvoorbeeld alleen typfouten corrigeert of u alleen de opmaak wijzigt.

1. Kies in Azure-portal **Alle services** > **Bewaking en beheer** > **Intune**.

2. Kies in het Intune-deelvenster de optie **Apparaatinschrijving** > **Voorwaarden** > selecteer de voorwaarden die u wilt aanpassen > **Eigenschappen**.

4. Selecteer in het deelvenster **Eigenschappen** de optie **Voorwaarden** en pas vervolgens **Titel**, **Overzicht van voorwaarden** en **Voorwaarden** naar wens aan. Als gebruikers de nieuwe voorwaarden naar aanleiding van de aangebrachte wijzigingen opnieuw moeten accepteren, selecteert u **Gebruikers moeten de voorwaarden opnieuw accepteren en het versienummer bijwerken naar**

4.  Kies **OK** > **Opslaan**.

Gebruikers hoeven de bijgewerkte voorwaarden slechts één keer te accepteren. Gebruikers met meerdere apparaten hoeven de voorwaarden niet voor elk apparaat te accepteren.
