---
title: De globale beleidsinstellingen configureren voor Azure Information Protection | Azure Rights Management
description: Er zijn drie instellingen in het Azure Information Protection-beleid die van toepassing zijn op alle gebruikers en alle apparaten.
manager: mbaldwin
ms.date: 08/08/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 629815c0-457d-4697-a4cc-df0e6cc0c1a6
translationtype: Human Translation
ms.sourcegitcommit: c9f9211e7c1dcf293caf81475515114b5433d6a7
ms.openlocfilehash: c48f5488e49a54b970f76012e0f2f17fe4158691


---

# De globale beleidsinstellingen configureren voor Azure Information Protection

>*Van toepassing op: Azure Information Protection preview*

**[ Deze informatie is voorlopig en kan worden gewijzigd. ]**

Er zijn drie instellingen in het Azure Information Protection-beleid die van toepassing zijn op alle gebruikers en alle apparaten:

![Globale instellingen van het Azure Information Protection-beleid](../media/info-protect-policy-settings.png)


Deze instellingen configureren:

1. Als u zich nog niet bij [Azure Portal](https://portal.azure.com) hebt aangemeld, meldt u zich nu aan en navigeert u vervolgens naar de blade **Azure Information Protection**. 
    
    Klik bijvoorbeeld in het hub-menu op **Bladeren** en begin met het typen van **Information** in het filtervak. Selecteer **Azure Information Protection**.

2. Configureer deze globale instellingen op de blade **Azure Information Protection**:

    - **Alle documenten en e-mailberichten moeten een label hebben**: als u deze optie instelt op **Aan**, moet op alle opgeslagen documenten en verzonden e-mailberichten een label worden toegepast. De labels kunnen handmatig door een gebruiker, automatisch als gevolg van een [voorwaarde](configure-policy-classification.md) of standaard (door het instellen van de optie **Het standaardlabel selecteren**) worden toegewezen. 

    Als een label niet is toegewezen wanneer een gebruiker een document opslaat of een e-mailbericht verzendt, wordt de gebruiker verzocht een label te selecteren:

    ![Azure Information Protection-prompt als de nieuwe classificatie lager is](../media/info-protect-enforce-label.png)

    - **Het standaardlabel selecteren**: als u deze optie instelt, selecteert u het label dat aan documenten en e-mailberichten moet worden toegewezen die geen label hebben. U kunt een label niet als standaardwaarde instellen als het label sublabels heeft. 

    - **Users must provide justification when lowering the sensitivity level (Gebruikers moeten een reden opgeven wanneer ze het gevoeligheidsniveau verlagen)**: als u deze optie instelt op **Aan** en een gebruiker het label van een bestaand document of e-mailbericht wijzigt in een label met een lager gevoeligheidsniveau (bijvoorbeeld van **Geheim** in **Openbaar**), wordt de gebruiker naar een reden voor deze actie gevraagd. De gebruiker kan bijvoorbeeld verklaren dat het document niet langer gevoelige gegevens bevat. De actie en de reden hiervoor worden vastgelegd in het lokale Windows-gebeurtenissenlogboek: **Toepassing** > **Microsoft Azure Information Protection**.  

    ![Azure Information Protection-prompt als de nieuwe classificatie lager is](../media/info-protect-lower-justification.png)

    Deze optie is niet van toepassing voor sublabels.

3. Sla uw wijzigingen op door op **Opslaan** te klikken.

4. Als u uw wijzigingen beschikbaar wilt stellen voor gebruikers, klikt u op **Publiceren**.

## Volgende stappen

Gebruik de koppelingen in de sectie [Het beleid van uw organisatie configureren](configure-policy.md#configuring-your-organization-s-policy) voor meer informatie over het configureren van uw Azure Information Protection-beleid.  












<!--HONumber=Aug16_HO4-->


