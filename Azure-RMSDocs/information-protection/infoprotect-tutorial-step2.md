---
title: Zelfstudie voor snel starten met Azure Information Protection - Stap 2 | Azure Rights Management
description: Stap 2 in de introductiezelfstudie om Microsoft Azure Information Protection snel uit te proberen voor uw organisatie, met slechts vier stappen die minder dan vijftien minuten duren.
author: cabailey
manager: mbaldwin
ms.date: 07/22/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 3bc193c2-0be0-4c8e-8910-5d2cee5b14f7
translationtype: Human Translation
ms.sourcegitcommit: 3bf9fe837c7bb268361b8004352192f0540604b9
ms.openlocfilehash: af2f5eadf3a4993c590f72a8f44e4fea03982505


---

# Stap 2: het Azure Information Protection-beleid configureren en publiceren

*Van toepassing op: Azure Information Protection preview*

Hoewel Azure Information Protection wordt geleverd met een standaardbeleid dat u zonder configuratie kunt gebruiken, zal dit beleid hieronder nader bekeken en worden een aantal wijzigingen doorgevoerd.

1. Meld u aan bij Azure Portal via deze speciale koppeling voor Azure Information Protection: https://portal.azure.com/?microsoft_azure_informationprotection=true
 
2. Klik vervolgens in het hub-menu op **Bladeren** en typ **Informatie** in het filtervak. Selecteer **Azure Information Protection**.

- De hoofdblade van **Azure Information Protection**wordt weergegeven, met het standaardbeleid voor Information Protection dat automatisch is gemaakt. Dit standaardbeleid bevat de volgende labels voor classificatie: **Persoonlijk**, **Openbaar**, **Intern**, **Vertrouwelijk** en **Geheim**. Lees de knopinfo voor elk label om te zien hoe de labels moeten worden gebruikt. Het label **Geheim** heeft twee onderliggende labels: **Alle werknemers** en **Mijn groep**. Dit zijn voorbeelden van onderliggende categorieën.

- Voor de labels **Intern**, **Vertrouwelijk** en **Geheim** zijn visuele markeringen geconfigureerd (zoals voettekst, koptekst en watermerk) en voor deze labels is geen beveiliging ingesteld. Bovendien zijn de drie algemene instellingen niet zo ingesteld dat alle documenten en e-mailberichten een label moeten hebben. Er is geen standaardlabel en gebruikers hoeven geen reden op te geven wanneer ze het vertrouwelijkheidsniveau verlagen.

    ![Zelfstudie voor snel starten met Azure Information Protection - Stap 3 - standaardbeleid](../media/info-protect-policy.png)

In deze zelfstudie worden een aantal algemene instellingen gewijzigd, zodat u kunt zien hoe deze werken:

-  **Selecteer het standaardlabel**: stel dit in op **Intern**.

- **Users must provide justification when lowering the sensitivity level (Gebruikers moeten een reden opgeven wanneer ze het gevoeligheidsniveau verlagen)**: stel deze optie in op **Aan**.

Nu worden de instellingen voor het label **Vertrouwelijk** gewijzigd:

1. Klik op de labelvermelding **Vertrouwelijk**.

2. In de blade **Label: Vertrouwelijk** ziet u de instellingen die voor elk label beschikbaar zijn. Breng de volgende wijzigingen aan:

    a. Als u Azure Rights Managment hebt geactiveerd, moet u voor **Set RMS template for protecting documents and emails containing this label (RMS-sjabloon instellen voor het beveiligen van documenten en e-mailberichten met dit label)** het volgende doen: controleer of **Azure RMS** is geselecteerd en klik vervolgens op de vervolgkeuzelijst en selecteer de standaardsjabloon **\<naam van uw organisatie> - Vertrouwelijk**. Bijvoorbeeld, als uw bedrijf VanArsdel, Ltd heet, selecteert u **VanArsdel, Ltd - Vertrouwelijk**. Als u deze standaardsjabloon voor Azure Rights Management hebt uitgeschakeld, selecteert u een andere sjabloon. Als u een sjabloon voor afdelingen hebt gemaakt, controleert u of uw account in het bereik is opgenomen.

    Als u Azure Rights Management niet hebt geactiveerd, kunt u deze optie niet gebruiken.

    b. **Documenten met dit label hebben een watermerk**: klik op **Aan** en typ in het vak **Tekst** de naam van uw organisatie. In ons voorbeeld: **VanArsdel, Ltd**. 

    c. Klik op **Een nieuwe voorwaarde toevoegen** en selecteer in de blade **Voorwaarde** het volgende:

    - **Het type voorwaarde kiezen**: **Ingebouwd**

    - **Ingebouwde selecteren**: **Creditcardnummer**

    - **Aantal exemplaren**: **1**

    - Klik op **Opslaan** om terug te keren naar de blade **Label: Vertrouwelijk**.

3. In de blade **Label: Vertrouwelijk** wordt **Creditcardnummer** weergegeven als de **VOORWAARDENAAM** met **1** **EXEMPLAAR**.

4. Laat **Selecteren hoe dit label wordt toegepast**: **Aanbevolen** ongewijzigd

5. Typ in het vak **Enter notes for internal housekeeping (Notities invoeren voor intern gebruik)** **Alleen voor testdoeleinden**.

6. Klik op **Opslaan** op de blade **Label: Vertrouwelijk** en klik op de hoofdblade **Azure Information Protection** nogmaals op **Opslaan**.

7. Nu wijzigingen zijn aangebracht en opgeslagen, moeten deze beschikbaar worden stellen voor gebruikers. Hiervoor klikt u op**Publiceren** en vervolgens op **Ja** ter bevestiging.

![Zelfstudie voor snel starten met Azure Information Protection - Stap 3 - standaardbeleid geconfigureerd](../media/info-protect-policy-configured.png)

Als u deze zelfstudie hebt voltooid, kunt u Azure Portal sluiten of open laten om andere configuratieopties uit te proberen.

Nu een overzicht van het standaardbeleid hebt en een aantal wijzigingen hebt aangebracht, moet u als volgende stap de Azure Information Protection-client installeren.


>[!div class="step-by-step"]
[&#171; Stap 1](infoprotect-tutorial-step1.md)
[Stap 3 &#187;](infoprotect-tutorial-step3.md)


<!--HONumber=Jul16_HO4-->


