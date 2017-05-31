---
title: Voorwaarden instellen in Microsoft Intune
titleSuffix: Intune Azure preview
description: 'Voorwaarden instellen die voor gebruikers worden weergegeven in de bedrijfsportal voor Intune. '
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: amyro
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: d53e91e24988d1bc71ff8df425f0d82e0fc43b58
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017

---

# <a name="ensure-users-accept-company-terms-for-access"></a>Ervoor zorgen dat gebruikers de bedrijfsvoorwaarden accepteren voor toegang

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Als Intune-beheerder kunt u vereisen dat gebruikers de algemene voorwaarden van uw bedrijf accepteren voordat ze de bedrijfsportal kunnen gebruiken om hun apparaten te registreren en toegang hebben tot bedrijfsresources als apps en e-mail. De configuratie van voorwaarden is optioneel.

U kunt meerdere sets met voorwaarden maken en deze toewijzen aan verschillende groepen om bijvoorbeeld verschillende talen te ondersteunen.

## <a name="create-terms-and-conditions"></a>Voorwaarden maken
Voer deze stappen uit om voorwaarden te maken. De weergavenaam en beschrijving zijn bedoeld voor beheerders. De eigenschappen van de voorwaarden worden in de bedrijfsportal weergegeven aan gebruikers.

1. Kies in Azure Portal **Meer services** > **Bewaking en beheer** > **Intune**.

2. Kies op de blade Intune achtereenvolgens **Apparaatinschrijving** en **Voorwaarden**.

3. Selecteer **Maken**.
![Schermafbeelding van de Intune-portal met de knop Maken voor het maken van voorwaarden](media/terms-create-terms.png)

4. Geef op de uitgevouwen blade de volgende gegevens op:

   - **Weergavenaam**: de naam voor de voorwaarden in de Intune-portal. Gebruikers krijgen deze naam niet te zien.

   - **Beschrijving**: optionele informatie aan de hand waarvan u deze set voorwaarden in de Intune-portal kunt herkennen.

5. Selecteer de pijl naast Gebruiksvoorwaarden definiëren om de blade Voorwaarden te openen. Voer de volgende informatie in:

   ![Schermopname van het scherm voor het accepteren van voorwaarden door gebruikers met een overzicht van de voorwaarden](./media/terms-summary-create.png)

   - **Titel**: de titel die gebruikers zien in de bedrijfsportal.

   - **Overzicht van voorwaarden**: tekst waarmee wordt uitgelegd wat het betekent als gebruikers de voorwaarden accepteren. Bijvoorbeeld: "Door uw apparaat te registreren, stemt u in met de gebruiksvoorwaarden die door Contoso zijn uiteengezet. Lees de voorwaarden door voordat u verdergaat."

   - **Voorwaarden**: de voorwaarden die gebruikers krijgen te zien en die ze moeten accepteren of weigeren.

6. Selecteer **Ok** en selecteer vervolgens **Maken**.

## <a name="assign-terms-and-conditions"></a>Voorwaarden toewijzen

U kunt voorwaarden toewijzen aan groepen gebruikers die ze moeten accepteren voordat ze de bedrijfsportal kunnen gebruiken.

1. Kies in Azure Portal **Meer services** > **Bewaking en beheer** > **Intune**.

2. Kies op de blade Intune achtereenvolgens **Apparaatinschrijving** en **Voorwaarden**.

3. Selecteer in de lijst met voorwaarden de voorwaarden die u wilt toewijzen en selecteer vervolgens **Toegewezen groepen**.
![Schermopname van de blade Groep toewijzen van de Intune-portal waarop de knoppen Groep selecteren en Selecteren worden weergegeven voor het toewijzen van voorwaarden](media/terms-assign-groups.png)

4. Klik op de knop **Groep selecteren** en selecteer in de blade **Groepen selecteren** de groepen waaraan u de voorwaarden wilt toewijzen. Klik vervolgens op **Selecteren**.

5. Klik in de blade **Toegewezen groepen** op **Opslaan**.  De voorwaarden zijn nu toegewezen aan gebruikers in de geselecteerde groepen. De volgende keer dat gebruikers de bedrijfsportal proberen te openen, wordt ze gevraagd de voorwaarden te accepteren.

   ![Schermopname van het scherm voor het accepteren van voorwaarden door gebruikers met een overzicht van de voorwaarden](./media/terms-summary-accept.png)

## <a name="monitor-a-terms-and-conditions"></a>Voorwaarden controleren

1. Kies in Azure Portal **Meer services** > **Bewaking en beheer** > **Intune**. Kies op de blade Intune achtereenvolgens **Apparaatinschrijving** en **Voorwaarden**.
2. Selecteer in de lijst met voorwaarden de voorwaarden die u wilt weergeven en selecteer vervolgens **Acceptatiestatussen**.

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a>Werken met meerdere versies van voorwaarden
U kunt de voorwaarden bewerken en de versies van de voorwaarden beheren. Het wordt aangeraden het versienummer te verhogen en elke keer dat u belangrijke wijzigingen doorvoert te vereisen dat gebruikers de nieuwe voorwaarden accepteren. Behoud het huidige versienummer als u bijvoorbeeld typefouten herstelt of de opmaak wijzigt.

1. Kies in Azure Portal **Meer services** > **Bewaking en beheer** > **Intune**.

2. Kies op de blade Intune de optie **Apparaatinschrijving**, kies **Voorwaarden**, selecteer de voorwaarden die u wilt aanpassen en selecteer vervolgens **Eigenschappen**.

4. Selecteer op de blade **Eigenschappen** de optie **Voorwaarden** en pas vervolgens **Titel**, **Overzicht van voorwaarden** en **Voorwaarden** naar wens aan. Als gebruikers de nieuwe voorwaarden naar aanleiding van de aangebrachte wijzigingen opnieuw moeten accepteren, klikt u op **Gebruikers moeten de voorwaarden opnieuw accepteren en het versienummer bijwerken naar**

4.  Selecteer **OK** en selecteer vervolgens **Opslaan**.

