---
title: Een label verwijderen of opnieuw rangschikken voor Azure Information Protection | Azure Rights Management
description: U kunt de labels die gebruikers op de Information Protection-balk zien, verwijderen of opnieuw rangschikken door dit in het Azure Information Protection-beleid te configureren.
manager: mbaldwin
ms.date: 08/10/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: ae0f603f-a632-4ac5-a3f7-6358d4255eff
translationtype: Human Translation
ms.sourcegitcommit: c9f9211e7c1dcf293caf81475515114b5433d6a7
ms.openlocfilehash: 43b43657627135886f6d0be42fef41ba939bdae1


---

# Een label verwijderen of opnieuw rangschikken voor Azure Information Protection

>*Van toepassing op: Azure Information Protection preview*

**[ Deze informatie is voorlopig en kan worden gewijzigd. ]**

U kunt de labels die gebruikers op de Information Protection-balk zien, verwijderen of opnieuw rangschikken door dit in het Azure Information Protection-beleid te configureren.

![Labels verwijderen of opnieuw rangschikken in het Azure Information Protection-beleid](../media/info-protect-contextmenu.png)

In plaats van labels te verwijderen, kunt u deze ook gewoon uitschakelen als u de labelconfiguratie wilt behouden maar de labels niet mogen worden weergegeven op de Information Protection-balk.

Rangschik de labels zodanig dat gebruikers ze in een logische volgorde op de Information Protection-balk zien. U kunt de labels bijvoorbeeld in oplopende gevoeligheid rangschikken zodat gebruikers het minst gevoelige label eerst zien en het meest gevoelige label het laatst. Bij het [standaardbeleid](configure-policy-default.md) wordt deze configuratie gebruikt.

> [!IMPORTANT]
>Als u [voorwaarden](configure-policy-classification.md) voor de labels configureert die mogelijk van toepassing zijn voor meer dan een label, moet u de labels rangschikken van minst gevoelig naar meest gevoelig. Deze volgorde zorgt ervoor dat het meest gevoelige label wordt toegepast wanneer de voorwaarden worden geëvalueerd.


Gebruik de volgende instructies om deze wijzigingen aan te brengen.

1. Als u zich nog niet bij [Azure Portal](https://portal.azure.com) hebt aangemeld, meldt u zich nu aan en navigeert u vervolgens naar de blade **Azure Information Protection**. 
    
    Klik bijvoorbeeld in het hub-menu op **Bladeren** en begin met het typen van **Information** in het filtervak. Selecteer **Azure Information Protection**.

2. Voer op de blade **Azure Information Protection** een van de volgende acties uit, afhankelijk van of u wilt verwijderen, wilt uitschakelen of de volgorde van een label wilt wijzigen:

    - Een label verwijderen: klik met de rechtermuisknop of selecteer het snelmenu (**...**) voor het label dat u wilt verwijderen, klik op **Dit label verwijderen** en klik op **Ja** om te bevestigen. Klik vervolgens op **Opslaan**. 

    - Een label uitschakelen: selecteer het label dat u wilt uitschakelen. Klik op de blade **Label** voor **Ingeschakeld** op **Uit**, en klik vervolgens op **Opslaan**.

    - Een label opnieuw rangschikken: klik met de rechtermuisknop of selecteer het snelmenu (**...**) voor het label dat u opnieuw wilt rangschikken en klik op **Omhoog** of **Omlaag** totdat het label op de gewenste positie staat. Klik vervolgens op **Opslaan**. 

3. Maak de wijzigingen beschikbaar voor gebruikers door op de blade **Azure Information Protection** op **Publiceren** te klikken.

## Volgende stappen

Gebruik de koppelingen in de sectie [Het beleid van uw organisatie configureren](configure-policy.md#configuring-your-organization-s-policy) voor meer informatie over het configureren van uw Azure Information Protection-beleid.  





<!--HONumber=Aug16_HO4-->


