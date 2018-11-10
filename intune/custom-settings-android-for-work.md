---
title: Aangepaste instellingen toevoegen aan Android Enterprise-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Een aangepast profiel voor Android Enterprise-apparaten toevoegen of maken om aangepaste instellingen te maken in Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4724d6e5-05e5-496c-9af3-b74f083141f8
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a622264ed7cc091849bacbd02f8ae7bdb33603fe
ms.sourcegitcommit: c969b596ec0fec227484c50f210ba4e159e2e533
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/24/2018
ms.locfileid: "49983139"
---
# <a name="use-custom-settings-for-android-enterprise-devices-in-microsoft-intune"></a>Aangepaste instellingen gebruiken voor Android Enterprise-apparaten in Microsoft Intune

Met Microsoft Intune kunt u aangepaste instellingen voor uw Android Enterprise-apparaten toevoegen of maken met behulp van een 'aangepast profiel'. Aangepaste profielen zijn een functie in Intune. Ze zijn ontworpen om apparaatinstellingen en -functies toe te voegen die niet in Intune zijn ingebouwd.

In aangepaste profielen voor Android Enterprise worden OMA-URI-instellingen (Open Mobile Alliance Uniform Resource Identifier) gebruikt om functies op Android Enterprise-apparaten te beheren. Deze instellingen worden doorgaans gebruikt door fabrikanten van mobiele apparaten om deze functies te beheren.

Intune ondersteunt een beperkt aantal aangepaste profielen voor Android.

In dit artikel wordt beschreven hoe u een aangepast profiel maakt voor Android Enterprise-apparaten. Het bevat ook een voorbeeld van een aangepast profiel waarmee kopieer- en plakbewerkingen worden geblokkeerd.

## <a name="create-the-profile"></a>Het profiel maken

1. Selecteer in [Azure Portal](https://portal.azure.com) **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
2. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Voer de volgende instellingen in:

    - **Naam**: voer een naam in voor het profiel, zoals `android enterprise custom profile`
    - **Beschrijving:** voer een beschrijving in voor het profiel
    - **Platform**: kies **Android Enterprise**
    - **Profieltype**: kies **Aangepast**

4. Selecteer in **Aangepaste OMA-URI-instellingen** de optie **Toevoegen**. Voer de volgende instellingen in:

    - **Naam**: voer een unieke naam in voor de OMA-URI-instelling, zodat u deze gemakkelijk kunt vinden.
    - **Beschrijving**: voer een beschrijving in met een overzicht van de instelling en eventuele andere belangrijke details.
    - **OMA-URI**: voer de OMA-URI in die u als instelling wilt gebruiken.
    - **Gegevenstype**: kies het gegevenstype dat u voor deze OMA-URI-instelling gaat gebruiken. Uw opties zijn:

      - Tekenreeks
      - Tekenreeks (XML-bestand)
      - Datum en tijd
      - Geheel getal
      - Drijvende komma
      - Boolean-waarde
      - Base64 (bestand)

    - **Waarde**: voer de gegevenswaarde in die moet worden gekoppeld aan de OMA-URI die u hebt ingevoerd. De waarde is afhankelijk van het gegevenstype dat u hebt geselecteerd. Als u bijvoorbeeld **Datum en tijd** hebt gekozen, selecteert u de waarde in een datumkiezer.

    Nadat u een aantal instellingen hebt toegevoegd, kunt u **Exporteren** selecteren. Met **Exporteren** maakt u een lijst met alle waarden die u hebt toegevoegd in een bestand met door komma's gescheiden waarden (.csv).

5. Selecteer **OK** om uw wijzigingen op te slaan. Blijf, indien nodig, meer instellingen toevoegen.
6. Wanneer u klaar bent, kiest u **OK** > **Maken** om het Intune-profiel te maken. Wanneer het profiel is gemaakt, wordt dit weergegeven in de lijst **Apparaatconfiguratie - profielen**.

## <a name="example"></a>Voorbeeld

In dit voorbeeld maakt u een aangepast profiel waarmee kopieer- en plakbewerkingen tussen werk-apps en persoonlijke apps op Android Enterprise-apparaten worden beperkt.

1. Selecteer in [Azure Portal](https://portal.azure.com) **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
2. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Voer de volgende instellingen in:

    - **Naam**: voer een naam in voor het profiel, zoals `android ent block copy paste custom profile`.
    - **Beschrijving:** voer een beschrijving in voor het profiel.
    - **Platform**: kies **Android Enterprise**.
    - **Profieltype**: kies **Aangepast**.

4. Selecteer in **Aangepaste OMA-URI-instellingen** de optie **Toevoegen**. Voer de volgende instellingen in:

    - **Naam**: voer iets in als `Block copy and paste`.
    - **Beschrijving**: voer iets in als `Blocks copy/paste between work and personal apps`.
    - **OMA-URI**: voer `./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste` in.
    - **Gegevenstype**: kies **Booleaans**, zodat de waarde voor deze OMA-URI **Waar** of **Onwaar** is.
    - **Waarde**: kies **Waar**.

5. Nadat u de instellingen hebt ingevoerd, moet uw omgeving ongeveer zijn zoals in de volgende afbeelding:

    ![Blokkeer kopiëren en plakken voor een Android-werkprofiel.](./media/custom-policy-afw-copy-paste.png)

Als u dit profiel toewijst aan Android Enterprise-apparaten die u beheert, wordt het kopiëren en plakken tussen apps in het werkprofiel en persoonlijke profiel geblokkeerd.

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt nog niets. Vervolgens [wijst u het profiel toe](device-profile-assign.md).

Bekijk hoe u [het profiel op Android-apparaten maakt](custom-settings-android.md).