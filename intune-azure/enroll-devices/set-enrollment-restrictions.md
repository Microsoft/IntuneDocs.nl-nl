---
title: Registratiebeperkingen instellen in Intune | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: beperk het registreren per platform en geef een registratielimiet voor apparaten op in Intune. '
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: 1bdefce35c20ce24b94ee701a2d13b5408f435ce

---

# <a name="set-enrollment-restrictions"></a>Registratiebeperkingen instellen 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

U kunt de typen apparaten die in Intune mogen worden geregistreerd, beperken door de toegestane platformen op te geven. U kunt ook het maximum aantal apparaten instellen dat een gebruiker mag registreren.

## <a name="set-device-type-restrictions"></a>Beperkingen voor apparaattypen instellen

1. Kies in Azure Portal **Meer services**, voer **Intune** in het tekstvak in en kies **Overige** > **Intune**

2. Kies op de blade Intune de optie **Apparaten inschrijven** en kies vervolgens **Inschrijvingsbeperkingen**.

3. Selecteer onder **Apparaattypebeperkingen** de optie **Standaard**.

4. Selecteer op de blade **Alle gebruikers** de optie **Platformen**.

5. Selecteer **Toestaan** voor platformen waarvoor registratie in Intune is toegestaan. Selecteer **Blokkeren** voor platformen waarvoor u het registreren wilt blokkeren.

6. Selecteer **Opslaan**.

7. Selecteer **Platformconfiguraties**.

8. Kies of u voor iOS-apparaten die het eigendom van de gebruiker zijn, het registreren wilt toestaan of blokkeren.

9. Selecteer **Opslaan**.

## <a name="set-device-limit-restrictions"></a>Apparaatlimietbeperkingen instellen

1. Kies op de blade Intune van Azure Portal de optie **Apparaten inschrijven** en kies vervolgens **Inschrijvingsbeperkingen**.

2. Selecteer onder **Apparaatlimietbeperkingen** de optie **Standaard**.

3. Selecteer op de blade **Alle gebruikers** de optie **Apparaatlimiet**.

4. Selecteer het maximum aantal apparaten dat een gebruiker kan registreren, en selecteer vervolgens **Opslaan**.



<!--HONumber=Feb17_HO1-->


