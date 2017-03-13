---
title: Voorwaarden instellen in Microsoft Intune
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: in dit onderwerp leest u hoe u voorwaarden kunt instellen die voor gebruikers worden weergegeven in de bedrijfsportal voor Intune. '
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 07a42cf8fa10d3223129fbb2932217ff90ac365b
ms.lasthandoff: 02/18/2017

---

# <a name="set-terms-and-conditions"></a>Voorwaarden instellen 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

U kunt de voorwaarden van Intune implementeren voor gebruikersgroepen om uit te leggen hoe zaken als inschrijving, toegang tot werkresources en de bedrijfsportal-app invloed hebben op apparaten en gebruikers. Gebruikers moeten de voorwaarden accepteren voordat ze de bedrijfsportal kunnen gebruiken om hun apparaat te registreren en toegang te krijgen tot hun werk.

U kunt meerdere beleidsregels met verschillende voorwaarden maken en implementeren. U kunt ook meerdere versies van dezelfde voorwaarden in verschillende talen maken en deze voor de betreffende groepen implementeren.

**Ga als volgt te werk om voorwaarden te maken**:

1. Kies in Azure Portal **Meer services** > **Bewaking en beheer** > **Intune**.

2. Kies **Apparaten inschrijven** op de blade Intune en kies vervolgens **Voorwaarden**.

3. Selecteer **Maken**.

4. Geef op de blade **Voorwaarden maken** de volgende gegevens op:

   - **Weergavenaam**: de naam voor de voorwaarden. Gebruikers zien deze naam in de bedrijfsportal-app.

   - **Beschrijving**: informatie waarmee u het beleid in Azure Portal kunt herkennen (optioneel).

5. Selecteer de pijl naast Gebruiksvoorwaarden definiëren om de blade Voorwaarden te openen. Voer de volgende informatie in:

   - **Titel**: de titel die gebruikers zien in de bedrijfsportal.

   - **Overzicht van voorwaarden**: tekst waarmee wordt uitgelegd wat het betekent als gebruikers de voorwaarden accepteren.

   - **Voorwaarden**: het juridische label dat gebruikers zien en moeten accepteren of weigeren, bijvoorbeeld 'Ik ga akkoord met de voorwaarden'.

6. Selecteer **OK**.

