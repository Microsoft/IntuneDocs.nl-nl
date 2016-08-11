---
title: De globale beleidsinstellingen configureren voor Azure Information Protection | Azure Rights Management
description: 
author: cabailey
manager: mbaldwin
ms.date: 07/29/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 629815c0-457d-4697-a4cc-df0e6cc0c1a6
translationtype: Human Translation
ms.sourcegitcommit: 93444affe94b280db2c9e4e2960c6902e491dec6
ms.openlocfilehash: 3b22cf76f03a4d36281db7e705359402dcbbde0e


---

# De globale beleidsinstellingen configureren voor Azure Information Protection

>*Van toepassing op: Azure Information Protection preview*

**[ Deze informatie is voorlopig en kan worden gewijzigd. ]**

Er zijn drie instellingen in het Azure Information Protection-beleid die van toepassing zijn op alle gebruikers en alle apparaten:

![Globale instellingen van het Azure Information Protection-beleid](../media/info-protect-policy-settings.png)


Deze instellingen configureren:

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
 
2. Klik vervolgens in het hub-menu op **Bladeren** en typ **Informatie** in het filtervak. Selecteer **Azure Information Protection**.

3. Configureer deze globale instellingen op de blade **Azure Information Protection**:

    - **Alle documenten en e-mailberichten moeten een label hebben**: als u deze optie instelt op **Aan**, moet op alle opgeslagen documenten en verzonden e-mailberichten een label worden toegepast. De labels kunnen handmatig door een gebruiker, automatisch als gevolg van een [voorwaarde](configure-policy-classification.md) of standaard (door het instellen van de optie **Het standaardlabel selecteren**) worden toegewezen. 

    Als een label niet is toegewezen wanneer een gebruiker een document opslaat of een e-mailbericht verzendt, wordt de gebruiker verzocht een label te selecteren:

    ![Azure Information Protection-prompt als de nieuwe classificatie lager is](../media/info-protect-enforce-label.png)

    - **Het standaardlabel selecteren**: als u deze optie instelt, selecteert u het label dat aan documenten en e-mailberichten moet worden toegewezen die geen label hebben. U kunt een label niet als standaardwaarde instellen als het label sublabels heeft. 

    - **Users must provide justification when lowering the sensitivity level (Gebruikers moeten een reden opgeven wanneer ze het gevoeligheidsniveau verlagen)**: als u deze optie instelt op **Aan** en een gebruiker het label van een bestaand document of e-mailbericht wijzigt in een label met een lager gevoeligheidsniveau (bijvoorbeeld van **Geheim** in **Openbaar**), wordt de gebruiker naar een reden voor deze actie gevraagd. De gebruiker kan bijvoorbeeld verklaren dat het document niet langer gevoelige gegevens bevat. De actie en de reden hiervoor worden vastgelegd in het lokale Windows-gebeurtenissenlogboek: **Toepassing** > **Microsoft Azure Information Protection**.  

    ![Azure Information Protection-prompt als de nieuwe classificatie lager is](../media/info-protect-lower-justification.png)

    Deze optie is niet van toepassing voor sublabels.

4. Sla uw wijzigingen op door op **Opslaan** te klikken.

5. Als u uw wijzigingen beschikbaar wilt stellen voor gebruikers, klikt u op **Publiceren**.

## Volgende stappen

Gebruik de koppelingen in de sectie [Het beleid van uw organisatie configureren](configure-policy.md#configuring-your-organization-s-policy) voor meer informatie over het configureren van uw Azure Information Protection-beleid.  












<!--HONumber=Jul16_HO5-->


