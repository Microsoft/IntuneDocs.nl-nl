---
title: Aangepaste instellingen toevoegen aan Android Enterprise-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Een aangepast profiel voor Android Enterprise-apparaten toevoegen of maken om aangepaste instellingen te maken in Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/21/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 4724d6e5-05e5-496c-9af3-b74f083141f8
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: bd2ab7ad8eb155719695bede1f539d5c264d455b
ms.sourcegitcommit: eb2e420b304c7da9d3be5ef49a676cba66766d2b
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 11/22/2019
ms.locfileid: "74319835"
---
# <a name="use-custom-settings-for-android-enterprise-devices-in-microsoft-intune"></a>Aangepaste instellingen gebruiken voor Android Enterprise-apparaten in Microsoft Intune

Met Microsoft Intune kunt u met behulp van een 'aangepast profiel' aangepaste instellingen toevoegen of maken voor uw apparaten met een Android Enterprise-werkprofiel. Aangepaste profielen zijn een functie in Intune. Ze zijn ontworpen om apparaatinstellingen en -functies toe te voegen die niet in Intune zijn ingebouwd.

In aangepaste profielen voor Android Enterprise worden OMA-URI-instellingen (Open Mobile Alliance Uniform Resource Identifier) gebruikt om functies op Android Enterprise-apparaten te beheren. Deze instellingen worden doorgaans gebruikt door fabrikanten van mobiele apparaten om deze functies te beheren.

InTune biedt ondersteuning voor het volgende beperkte aantal aangepaste Android Enter prise-profielen:

- ./Vendor/MSFT/WiFi/Profile/SSID/Settings: [het maken van een Wi-Fi-profiel met een vooraf gedeelde sleutel](wi-fi-profile-shared-key.md) bevat enkele voor beelden.
- ./Vendor/MSFT/VPN/Profile/Name/PackageList: [het maken van een VPN-profiel per app](android-pulse-secure-per-app-vpn.md) bevat enkele voor beelden.
- ./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste: Zie het [voor beeld](#example) in dit artikel. Deze instelling is ook beschikbaar in de gebruikers interface. Zie [Android Enterprise-apparaatinstellingen voor beheer van functies](device-restrictions-android-for-work.md) voor meer informatie.

Zie [OEMConfig voor Android Enter prise](android-oem-configuration-overview.md)(Engelstalig) als u aanvullende instellingen nodig hebt.

In dit artikel wordt beschreven hoe u een aangepast profiel maakt voor Android Enterprise-apparaten. Het bevat ook een voorbeeld van een aangepast profiel waarmee kopieer- en plakbewerkingen worden geblokkeerd.

## <a name="create-the-profile"></a>Het profiel maken

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
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

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
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

    ![Blokkeer kopiëren en plakken voor een Android-werkprofiel.](./media/custom-settings-android-for-work/custom-policy-afw-copy-paste.png)

Als u dit profiel toewijst aan Android Enterprise-apparaten die u beheert, wordt het kopiëren en plakken tussen apps in het werkprofiel en persoonlijke profiel geblokkeerd.

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt nog niets. Vervolgens [wijst u het profiel toe](device-profile-assign.md).

Bekijk hoe u [het profiel op Android-apparaten maakt](../custom-settings-android.md).
