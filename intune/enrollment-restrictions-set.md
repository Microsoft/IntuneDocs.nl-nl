---
title: Registratiebeperkingen instellen in Intune
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: beperk het registreren per platform en geef een registratielimiet voor apparaten op in Intune. '
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: d99f7ca5b5e96a7ab113a14d36f0fef474411836
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017

---

# <a name="set-enrollment-restrictions"></a>Registratiebeperkingen instellen 

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

U kunt instellen welke apparaattypen en hoeveel apparaten er maximaal kunnen worden ingeschreven. Op de blade Inschrijvingsbeperkingen kunt u het volgende instellen:

- Welke platforms kunnen worden ingeschreven en of inschrijving moet worden geblokkeerd van Android- en iOS-apparaten die het eigendom van de gebruiker zijn.

- Het maximumaantal apparaten dat een gebruiker mag inschrijven.

## <a name="set-device-type-restrictions"></a>Beperkingen voor apparaattypen instellen

1. Kies in Azure-portal **Meer services** > **Bewaking en beheer** > **Intune**.

2. Kies op de blade Intune de optie **Apparaten inschrijven** en kies vervolgens **Inschrijvingsbeperkingen**.

3. Selecteer onder **Apparaattypebeperkingen** de optie **Standaard**.

4. Selecteer op de blade **Alle gebruikers** de optie **Platformen**.

5. Selecteer **Toestaan** voor platformen waarvoor registratie in Intune is toegestaan. Selecteer **Blokkeren** voor platformen waarvoor u het registreren wilt blokkeren. Platformen zijn standaard ingesteld op **Toestaan**. 

    >[!NOTE]
    >Deze instellingen zijn niet van toepassing op Windows-inschrijvingen die de Intune-softwareclient gebruiken en blokkeren die niet. Deze instellingen hebben alleen invloed op inschrijving via mobiel apparaatbeheer. 

6. Selecteer **Opslaan**.

7. Selecteer **Platformconfiguraties**.

8. Kies of u voor iOS- en Android-apparaten die het eigendom van de gebruiker zijn, inschrijven wilt **toestaan** of **blokkeren**.

9. Selecteer **Opslaan**.

## <a name="set-device-limit-restrictions"></a>Apparaatlimietbeperkingen instellen

1. Kies in Azure-portal **Meer services** > **Bewaking en beheer** > **Intune**.

2. Kies op de blade Intune de optie **Apparaten inschrijven** en kies vervolgens **Inschrijvingsbeperkingen**.

3. Selecteer onder **Apparaatlimietbeperkingen** de optie **Standaard**.

4. Selecteer op de blade **Alle gebruikers** de optie **Apparaatlimiet**.

5. Selecteer het maximum aantal apparaten dat een gebruiker kan registreren, en selecteer vervolgens **Opslaan**.

