---
title: Registratiebeperkingen instellen in Intune
titlesuffix: Azure portal
description: Beperk het registreren per platform en geef een registratielimiet voor apparaten op in Intune. "
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d3e3f35648784de860eb7e3f2e203488bc77a96d
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="set-enrollment-restrictions"></a>Registratiebeperkingen instellen

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Als Intune-beheerder kunt u registratiebeperkingen maken en beheren om het aantal en typen apparaten op te geven dat onder beheer met Intune kan worden geregistreerd. U kunt meerdere beperkingen maken en deze toepassen op verschillende gebruikersgroepen. U kunt de [volgorde van prioriteit](#change-enrollment-restriction-priority) voor uw andere beperkingen instellen.

>[!NOTE]
>Inschrijvingsbeperkingen vormen geen beveiligingsfuncties. Aangetaste apparaten kunnen zich anders voordoen dan ze in werkelijkheid zijn. Deze beperkingen zijn een best-effort barrière voor niet-kwaadwillende gebruikers.

>[!NOTE]
>De aan de groep toegewezen registratiebeperking en prioriteitsfunctionaliteit die hieronder worden genoemd, worden geïmplementeerd in het gehele Intune-klantenbestand. Als deze implementatie nog niet is voltooid, hebt u mogelijk geen toegang tot de groep en prioriteitsfuncties. 

U kunt onder ander de volgende registratiebeperkingen maken:

- Maximum aantal geregistreerde apparaten
- De ondersteunde apparaatplatformen:
  - Android
  - Android for Work
  - iOS
  - macOS
  - Windows
- Besturingssysteemversie van platform voor iOS, Android, Android for Work en Windows (alleen Windows 10-versies kunnen worden gebruikt, laat dit leeg als Windows 8.1 is toegestaan)
  - Minimale versie
  - Maximale versie
- Beperkingen opleggen voor apparaten die persoonlijk eigendom zijn (alleen iOS, Android, Android for Work en macOS)

## <a name="default-restrictions"></a>Standaardbeperkingen

Standaardbeperkingen worden automatisch opgegeven voor registratiebeperkingen voor zowel het apparaattype als de apparaatlimiet. U kunt de opties voor de standaardinstellingen wijzigen. De standaardbeperkingen zijn van toepassing op alle gebruikersregistraties en registraties zonder gebruikers. U kunt deze standaardinstellingen onderdrukken door nieuwe beperkingen met een hogere prioriteit te maken.

## <a name="create-a-restriction"></a>Een beperking maken

1. Meld u aan bij Azure-portal.
2. Kies **Meer Services**, zoek naar **Intune** en kies vervolgens **Intune**.
3. Kies **Apparaatinschrijving** > **Inschrijvingsbeperkingen**.
4. Kies **Beperking maken**.
5. Geef een naam en beschrijving voor de beperking op.
6. Kies een **Beperkingstype** en klik op **Maken**.
7. Klik voor apparaatlimietbeperkingen op **Apparaatlimiet** om het maximumaantal apparaten in te stellen dat een gebruiker kan registreren.
8. Klik voor apparaattypebeperkingen op **Platforms** en **Platformconfiguraties** om verschillende platforms en versies toe te staan of te blokkeren.
9. Klik op **Toewijzingen** > **+ Groepen selecteren**.
10. Selecteer onder **Groepen selecteren** een of meer groepen en klik vervolgens op **Selecteren**. De beperking geldt alleen voor de groepen waaraan deze is toegewezen. Als u geen beperking aan ten minste één groep toewijst, heeft deze bewerking dit geen effect.
11. Klik op **Opslaan**.
12. De nieuwe beperking wordt gemaakt met een prioriteit boven de standaardwaarde. U kunt [de prioriteit wijzigen](#change-enrollment-restriction-priority).

## <a name="set-device-type-restrictions"></a>Beperkingen voor apparaattypen instellen

U kunt de instellingen voor een beperking van het type apparaat als volgt wijzigen:

1. Meld u aan bij Azure-portal.
2. Kies **Meer Services**, zoek naar **Intune** en kies vervolgens **Intune**.
3. Kies **Apparaatinschrijving** > **Inschrijvingsbeperkingen**.
4. Kies onder **Beperking voor apparaattypen** de beperking die u wilt instellen.
5. Selecteer onder de naam van de beperking (**Alle gebruikers** voor de standaardbeperking) **Platforms**. Kies **Toestaan** of **Blokkeren** voor elk weergegeven platform.
6. Klik op **Opslaan**.
7. Selecteer onder de naam van de beperking (**Alle gebruikers** voor de standaardbeperking) **Platformconfiguraties** en selecteer de minimale en maximale **Versies** voor de weergegeven platforms. Ondersteunde versies:
  - Android- en Android for Work ondersteunen major.minor.rev.build.
  - iOS ondersteunt major.minor.rev.
  - Windows ondersteunt alleen major.minor.rev.build voor Windows 10.
  Versies van besturingssystemen zijn niet van toepassing op Apple-apparaten die zijn ingeschreven met Device Enrollment Program, Apple School Manager of de app Apple Configurator. 
8. Geef voor elk vermeld platform op of u apparaten die **persoonlijk eigendom zijn** wilt **Toestaan** of **Blokkeren**.

    ![Schermopname van de werkruimte Apparaatbeperkingen met de standaard-apparaatplatformconfiguraties met instellingen voor apparaten die persoonlijk eigendom zijn.](media/device-restrictions-platform-configurations.png)
9. Klik op **Opslaan**.

>[!NOTE]
>- Als u instelt dat Android-apparaten niet mogen worden ingeschreven als deze persoonlijk eigendom zijn, kunnen Android for Work-apparaten die persoonlijk eigendom zijn, nog wel worden ingeschreven.
>- Standaard zijn instellingen voor uw Android for Work-apparaten gelijk aan de instellingen voor uw Android-apparaten. Wanneer u echter uw Android for Work-instellingen wijzigt, is dat niet meer het geval.
>- Als u een persoonlijke Android for Work-inschrijving blokkeert, kunnen alleen zakelijke Android-apparaten worden ingeschreven als Android for Work.

## <a name="set-device-limit-restrictions"></a>Apparaatlimietbeperkingen instellen

U kunt de instellingen voor een beperking van de apparaatlimiet als volgt wijzigen:

1. Meld u aan bij Azure-portal.
2. Kies **Meer Services**, zoek naar **Intune** en kies vervolgens **Intune**.
3. Kies **Apparaatinschrijving** > **Inschrijvingsbeperkingen**.
4. Kies onder **Apparaatlimietbeperkingen** de beperking die u wilt instellen.
5. Kies **Apparaatlimiet** en selecteer in de vervolgkeuzelijst het maximum aantal apparaten dat een gebruiker kan registreren.
    ![Schermopname van de blade Apparaatlimietbeperkingen met beperkingen voor het aantal apparaten.](./media/device-restrictions-limit.png)
6. Klik op **Opslaan**.

## <a name="change-enrollment-restriction-priority"></a>De prioriteit van de registratiebeperking wijzigen

Prioriteit wordt gebruikt wanneer een gebruiker voorkomt in meerdere groepen waaraan beperkingen zijn toegewezen. Voor gebruikers gelden alleen de hoogste prioriteitsbeperkingen die aan de groep waarvan zij deel uitmaken zijn toegewezen. Bijvoorbeeld, Jos maakt deel uit van groep A waaraan beperkingen met prioriteit 5 zijn toegewezen. Bovendien maakt hij deel uit van groep B waaraan beperkingen met prioriteit 2 zijn toegewezen. Voor Jan gelden alleen de beperkingen met prioriteit 2. 

Wanneer u een beperking maakt, wordt deze net boven de standaardbeperking in de lijst geplaatst.

Voor apparaatinschrijving gelden standaardbeperkingen voor zowel het apparaattype als de apparaatlimiet. Deze twee beperkingen gelden voor alle gebruikers, tenzij ze worden overschreven door beperkingen met een hogere prioriteit. 

U kunt de prioriteit van een niet-standaard-beperking wijzigen. 

**Prioriteit van beperkingen wijzigen**

1. Meld u aan bij Azure-portal.
2. Kies **Meer Services**, zoek naar **Intune** en kies vervolgens **Intune**.
3. Kies **Apparaatinschrijving** > **Inschrijvingsbeperkingen**.
4. Beweeg de muisaanwijzer over de beperking in de lijst met prioriteiten.
5. Sleep de drie verticale puntjes voor de prioriteit naar de gewenste positie in de lijst.





