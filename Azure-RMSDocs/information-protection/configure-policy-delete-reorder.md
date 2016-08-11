---
title: Een label verwijderen of opnieuw rangschikken voor Azure Information Protection | Azure Rights Management
description: 
author: cabailey
manager: mbaldwin
ms.date: 07/29/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: ae0f603f-a632-4ac5-a3f7-6358d4255eff
translationtype: Human Translation
ms.sourcegitcommit: 93444affe94b280db2c9e4e2960c6902e491dec6
ms.openlocfilehash: 50a60f8a0f8cb92aba7453e6c1dedacbe004a5ed


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

1. Meld u aan bij [Azure Portal](https://portal.azure.com).

2. Klik vervolgens in het hub-menu op **Bladeren** en typ **Informatie** in het filtervak. Selecteer **Azure Information Protection**.

3. Voer op de blade **Azure Information Protection** een van de volgende acties uit, afhankelijk van of u wilt verwijderen, wilt uitschakelen of de volgorde van een label wilt wijzigen:

    - Een label verwijderen: klik met de rechtermuisknop of selecteer het snelmenu (**...**) voor het label dat u wilt verwijderen, klik op **Dit label verwijderen** en klik op **Ja** om te bevestigen. Klik vervolgens op **Opslaan**. 

    - Een label uitschakelen: selecteer het label dat u wilt uitschakelen. Klik op de blade **Label** voor **Ingeschakeld** op **Uit**, en klik vervolgens op **Opslaan**.

    - Een label opnieuw rangschikken: klik met de rechtermuisknop of selecteer het snelmenu (**...**) voor het label dat u opnieuw wilt rangschikken en klik op **Omhoog** of **Omlaag** totdat het label op de gewenste positie staat. Klik vervolgens op **Opslaan**. 

4. Maak de wijzigingen beschikbaar voor gebruikers door op de blade **Azure Information Protection** op **Publiceren** te klikken.

## Volgende stappen

Gebruik de koppelingen in de sectie [Het beleid van uw organisatie configureren](configure-policy.md#configuring-your-organization-s-policy) voor meer informatie over het configureren van uw Azure Information Protection-beleid.  





<!--HONumber=Jul16_HO5-->


