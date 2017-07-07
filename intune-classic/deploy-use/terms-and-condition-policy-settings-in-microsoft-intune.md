---
title: Beleidsinstellingen voor voorwaarden
description: U kunt de voorwaarden van Intune implementeren voor gebruikersgroepen om uit te leggen hoe zaken als inschrijving, toegang tot werkresources en het gebruik van de bedrijfsportal-app invloed hebben op apparaten en gebruikers.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6edf0ac1-4f46-4543-a9e5-f484ac37e9a5
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2e8028abe5f25e4a05d79ae543d3029490c01668
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="terms-and-condition-policy-settings-in-microsoft-intune"></a>Beleidsinstellingen voor voorwaarden in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

U kunt de voorwaarden van Intune implementeren voor gebruikersgroepen om uit te leggen hoe zaken als inschrijving, toegang tot werkresources en de bedrijfsportal-app invloed hebben op apparaten en gebruikers. Gebruikers moeten de voorwaarden accepteren voordat ze de bedrijfsportal kunnen gebruiken om hun apparaat te registreren en toegang te krijgen tot hun werk.

U kunt meerdere beleidsregels met verschillende voorwaarden maken en implementeren. U kunt ook meerdere versies van dezelfde voorwaarden in verschillende talen maken en deze voor de betreffende groepen implementeren.

## <a name="create-a-terms-and-conditions-policy"></a>Een beleid voor voorwaarden maken

1.  Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) op **Beleid** &gt; **Voorwaarden**.

    ![Schermafbeelding van beleidsinstellingen voor voorwaarden](./media/pol-sa-terms-conditions.png)

2.  Klik op **Toevoegen** om een nieuw beleid voor voorwaarden te maken.

    U kunt ook een bestaand beleid **bewerken** of **verwijderen**.

3.  Geef op de pagina **Voorwaarden maken** de volgende gegevens op:

    -   **Naam**&mdash;een unieke beleidsnaam die wordt weergegeven in de Intune-console.

    -   **Beschrijving**&mdash;informatie waarmee u het beleid in de Intune-console kunt herkennen.

    -   **Titel**&mdash;de titel die gebruikers zien in de bedrijfsportal.

    -   **Tekst waarmee wordt uitgelegd wat het inhoudt als de gebruiker de voorwaarden accepteert**&mdash;de verklaring die gebruikers zien in verband met aanvaarding. Bijvoorbeeld: 'Ik ga akkoord met de voorwaarden'.

4.  Klik op **Opslaan** als u klaar bent. Het nieuwe beleid wordt weergegeven in het knooppunt **Voorwaarden** van de werkruimte **Beleid**.

## <a name="deploy-a-terms-and-conditions-policy"></a>Een beleid voor voorwaarden implementeren

1.  Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) op **Beleid** &gt; **Voorwaarden**.

2.  Selecteer in de lijst **Beleidsregels voor voorwaarden** het beleid dat u wilt implementeren en klik vervolgens op **Implementatie beheren**.

3.  Selecteer in het dialoogvenster **Implementatie beheren** de gebruikersgroepen waarvoor u het beleid wilt implementeren en klik vervolgens op **OK**.

    Wanneer de betreffende gebruikers de bedrijfsportal openen, worden in Intune de voorwaarden weergegeven die u hebt geïmplementeerd. Gebruikers moeten deze voorwaarden accepteren voordat ze toegang krijgen tot bedrijfsresources.

## <a name="monitor-a-terms-and-conditions-policy"></a>Een beleid voor voorwaarden bewaken

1.  Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) op **Beleid** &gt; **Voorwaarden**.

2.  Klik in het venster **Nieuw rapport maken** op **Rapport weergeven**. Het rapport wordt geopend met gedetailleerde informatie over welke gebruikers de door u geïmplementeerde voorwaarden hebben geaccepteerd.

### <a name="updates-and-version-control-for-terms-and-conditions"></a>Updates en versiebeheer voor voorwaarden
Wanneer u bestaande voorwaarden bewerkt, kunt u kiezen welk gedrag optreedt wanneer u het beleid implementeert. Volg de volgende procedure om bestaande voorwaarden bij te werken.

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a>Werken met meerdere versies van voorwaarden

1.  Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) op **Beleid** &gt; **Voorwaarden**.

2.  Selecteer de voorwaarden die u wilt bewerken en klik op **Bewerken**.

3.  Breng op de pagina **Voorwaarden bewerken** de gewenste wijzigingen aan en geef aan of alle gebruikers de nieuwe voorwaarden moeten accepteren of alleen nieuwe gebruikers de nieuwe versie te zien krijgen.

    Het wordt aangeraden het versienummer te verhogen en elke keer dat u belangrijke wijzigingen doorvoert te vereisen dat gebruikers de nieuwe voorwaarden accepteren. Behoud het huidige versienummer als u bijvoorbeeld typefouten wilt herstellen of de opmaak wilt wijzigen.

### <a name="see-also"></a>Zie tevens
[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
