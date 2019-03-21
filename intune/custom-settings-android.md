---
title: Aangepaste instellingen toevoegen aan Android-apparaten Microsoft Intune - Azure | Microsoft Docs
description: Een aangepast profiel toevoegen voor Android-apparaten om een Wi-Fi-profiel te maken met een vooraf gedeelde sleutel, per app een VPN-profiel maken of apps toestemming geven/blokkeren voor Samsung Knox Standard-apparaten in Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ba6d2f60d91388aa1c8ceea6580f1d583d4c987c
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57564819"
---
# <a name="use-custom-settings-for-android-devices-in-microsoft-intune"></a>Aangepaste instellingen gebruiken voor Android-apparaten in Microsoft Intune

Met Microsoft Intune kunt u aangepaste instellingen voor uw Android-apparaten toevoegen of maken met behulp van een 'aangepast profiel'. Aangepaste profielen zijn een functie in Intune. Ze zijn ontworpen om apparaatinstellingen en -functies toe te voegen die niet in Intune zijn ingebouwd.

Aangepaste profielen voor Android gebruiken OMA-URI-instellingen (Open Mobile Alliance Uniform Resource Identifier) om verschillende functies op Android-apparaten te configureren. Deze instellingen worden doorgaans gebruikt door fabrikanten van mobiele apparaten om deze functies te beheren.

Door een aangepast profiel te gebruiken, kunt u de volgende Android-instellingen configureren en toewijzen. De volgende instellingen zijn niet ingebouwd in Intune:

- [Een Wi-Fi-profiel maken met een vooraf gedeelde sleutel](/intune/wi-fi-profile-shared-key)
- [Een VPN per app-profiel maken](/intune/android-pulse-secure-per-app-vpn)
- [Apps toestaan of blokkeren voor Samsung KNOX Standard-apparaten](/intune/samsung-knox-apps-allow-block)

>[!IMPORTANT]
> Alleen de hierboven genoemde instellingen kunnen worden geconfigureerd in een aangepast profiel. Android-apparaten geven geen volledige lijst weer met OMA-URI-instellingen die u kunt configureren. Als u meer instellingen wilt bekijken, stemt u voor meer instellingen op de [Intune Uservoice-site](https://microsoftintune.uservoice.com/forums/291681-ideas).

In dit artikel wordt beschreven hoe u een aangepast profiel maakt voor Android-apparaten.

## <a name="create-the-profile"></a>Het profiel maken

1. Selecteer in [Azure Portal](https://portal.azure.com) **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
2. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Voer de volgende instellingen in:

    - **Naam**: voer een naam in voor het profiel, zoals `android custom profile`.
    - **Beschrijving:** voer een beschrijving in voor het profiel.
    - **Platform**: kies **Android**.
    - **Profieltype**: kies **Aangepast**.

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

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt nog niets. Vervolgens [wijst u het profiel toe](device-profile-assign.md).

Bekijk hoe u [het profiel op Android Enterprise-apparaten maakt](custom-settings-android-for-work.md).
