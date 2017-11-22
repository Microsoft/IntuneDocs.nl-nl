---
title: Registratiebeperkingen instellen in Intune
titlesuffix: Azure portal
description: Beperk het registreren per platform en geef een registratielimiet voor apparaten op in Intune. "
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 11/6/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 463278e4dc9ad677f654754d4710b110b376cc2d
ms.sourcegitcommit: 5279a0bb8c5aef79aa57aa247ad95888ffe5a12b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/08/2017
---
# <a name="set-enrollment-restrictions"></a>Registratiebeperkingen instellen

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Als Intune-beheerder kunt u bepalen welke apparaten kunnen worden geregistreerd voor beheer met Intune. Gebruik de Azure-portal om de volgende beperkingen in te stellen voor apparaatinschrijving:

- Maximum aantal geregistreerde apparaten
- De ondersteunde apparaatplatformen:
  - Android
  - iOS
  - macOS
  - Windows
- Besturingssysteemversie van platform voor iOS, Android en Windows (alleen Windows 10-versies kunnen worden gebruikt, laat dit leeg als Windows 8.1 is toegestaan)
  - Minimale versie
  - Maximale versie
- Beperkingen opleggen voor apparaten die persoonlijk eigendom zijn (alleen iOS, Android en macOS)

>[!NOTE]
>Inschrijvingsbeperkingen vormen geen beveiligingsfuncties. Aangetaste apparaten kunnen zich anders voordoen dan ze in werkelijkheid zijn. Deze beperkingen zijn een best-effort barrière voor niet-kwaadwillende gebruikers.

## <a name="set-device-type-restrictions"></a>Beperkingen voor apparaattypen instellen
De standaardinschrijvingsbeperkingen zijn van toepassing op alle gebruikersinschrijvingen en inschrijvingen zonder gebruikers.
1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apparaatinschrijving** > **Inschrijvingsbeperkingen**.
4. Selecteer **Standaard** onder **Inschrijvingsbeperkingen** > **Apparaattypebeperkingen**.
5. Selecteer **Platformen** onder **Alle gebruikers**. Kies **Toestaan** of **Blokkeren** voor elk platform:
  - **Android**
  - **iOS**
  - **macOS**
  - **Windows**

  Klik op **Opslaan**.
6. Selecteer onder **Alle gebruikers** **Platformconfiguraties** en selecteer de volgende configuraties. Voor elk toegestaan platform kunt u de volgende opties configureren:
  - **Versies**: geef de **minimale** en **maximale** versie van het besturingssysteem van het platform op voor Android-, iOS- of Windows-apparaten. Android ondersteunt major.minor.rev.build. iOS ondersteunt major.minor.rev. Windows ondersteunt alleen major.minor.rev.build voor Windows 10. Versies van besturingssystemen zijn niet van toepassing op Apple-apparaten die zijn ingeschreven met Device Enrollment Program, Apple School Manager of de app Apple Configurator. 
  - **Persoonlijk eigendom**: kies **Toestaan** of **Blokkeren** voor Android-, iOS- en macOS-apparaten.
  ![Schermopname van de werkruimte Apparaatbeperkingen met de standaard-apparaatplatformconfiguraties met instellingen voor apparaten die persoonlijk eigendom zijn.](media/device-restrictions-platform-configurations.png)
  Klik op **Opslaan**.

>[!NOTE]
>Als u instelt dat Android-apparaten niet mogen worden ingeschreven als deze persoonlijk eigendom zijn, kunnen Android for Work-apparaten die persoonlijk eigendom zijn, nog wel worden ingeschreven.

## <a name="set-device-limit-restrictions"></a>Apparaatlimietbeperkingen instellen
De standaardinschrijvingsbeperkingen zijn van toepassing op alle gebruikers.
1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apparaatinschrijving** > **Inschrijvingsbeperkingen**.
4. Kies in de Azure-portal de optie **Apparaatinschrijving** en kies vervolgens **Inschrijvingsbeperkingen**.
5. Kies **Inschrijvingsbeperkingen** > **Apparaatlimietbeperkingen**.
6. Selecteer **Apparaatlimiet** onder **Alle gebruikers**. Geef het maximum aantal geregistreerde apparaten per gebruiker op.  
![Schermopname van de blade Apparaatlimietbeperkingen met beperkingen voor het aantal apparaten.](./media/device-restrictions-limit.png)

  Klik op **Opslaan**.
