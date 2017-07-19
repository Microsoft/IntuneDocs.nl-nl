---
title: Registratiebeperkingen instellen in Intune
titleSuffix: Intune on Azure
description: Beperk het registreren per platform en geef een registratielimiet voor apparaten op in Intune. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2dfcba8c788f262ce816dcd23dc2921fd57f331b
ms.sourcegitcommit: d1ad84edf4f03cb4c11fe55131556b43fc3a4500
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/05/2017
---
# <a name="set-enrollment-restrictions"></a>Registratiebeperkingen instellen

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Als Intune-beheerder kunt u bepalen welke apparaten kunnen worden geregistreerd voor beheer met Intune. Gebruik de Intune-portal om de volgende beperkingen in te stellen voor apparaatinschrijving:

- Maximum aantal geregistreerde apparaten
- De ondersteunde apparaatplatformen:
  - Android
  - iOS
  - macOS
  - Windows
- Beperkingen opleggen voor apparaten die persoonlijk eigendom zijn (alleen iOS en Android)

>[!NOTE]
>Registratiebeperkingen vormen geen beveiligingsfunctie. Aangetaste apparaten kunnen zich anders voordoen dan ze in werkelijkheid zijn. Deze beperkingen zijn een best-effort barrière voor niet-kwaadwillende gebruikers.

## <a name="set-device-type-restrictions"></a>Beperkingen voor apparaattypen instellen
De standaardbeperkingen voor registratie gelden voor alle gebruikers die niet beschikken over registratiebeperkingen met een hogere prioriteit.  
1. Kies in de Intune-portal de optie **Apparaatinschrijving** en kies vervolgens **Inschrijvingsbeperkingen**.
![Schermopname van de werkruimte Apparaatbeperkingen met de standaardbeperkingen voor apparaattypen en apparaatlimietbeperkingen.](media/device-restrictions-set-default.png)
2. Selecteer **Standaard** onder **Inschrijvingsbeperkingen** > **Apparaattypebeperkingen**.
3. Selecteer **Platformen** onder **Alle gebruikers**. Kies **Toestaan** of **Blokkeren** voor elk platform:
  - **Android**
  - **iOS**
  - **macOS**
  - **Windows**

  Klik op **Opslaan**.
4. Selecteer onder **Alle gebruikers** **Platformconfiguraties** en selecteer de volgende configuraties:
  - **Persoonlijk eigendom**: kies **Toestaan** of **Blokkeren** voor Android- en iOS-apparaten.
  ![Schermopname van de werkruimte Apparaatbeperkingen met de standaard-apparaatplatformconfiguraties met instellingen voor apparaten die persoonlijk eigendom zijn.](media/device-restrictions-platform-configurations.png)
  Klik op **Opslaan**.

>[!NOTE]
>Als u instelt dat Android-apparaten niet mogen worden geregistreerd als deze persoonlijk eigendom zijn, kunnen Android for Work-apparaten nog wel worden geregistreerd.

## <a name="set-device-limit-restrictions"></a>Apparaatlimietbeperkingen instellen
De standaardbeperkingen voor registratie gelden voor alle gebruikers die niet beschikken over registratiebeperkingen met een hogere prioriteit.  
1. Kies in de Intune-portal de optie **Apparaatinschrijving** en kies vervolgens **Inschrijvingsbeperkingen**.
2. Kies **Inschrijvingsbeperkingen** > **Apparaatlimietbeperkingen**.
3. Selecteer **Apparaatlimiet** onder **Alle gebruikers**. Geef het maximum aantal geregistreerde apparaten per gebruiker op.  
![Schermopname van de blade Apparaatlimietbeperkingen met beperkingen voor het aantal apparaten.](./media/device-restrictions-limit.png)

  Klik op **Opslaan**.
