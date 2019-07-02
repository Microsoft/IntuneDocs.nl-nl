---
title: Aangepaste instellingen toevoegen aan Windows Phone 8.1-apparaten in Microsoft Intune - Azure | Microsoft Docs
titleSuffix: ''
description: Maak een aangepast profiel of voeg dit toe om de OMA-URI-instellingen te gebruiken voor apparaten met Windows Phone 8.1 in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/25/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 97d656db3e828ef3377b927395a283fe995bb8a4
ms.sourcegitcommit: a63b9eaa59867ab2b0a6aa415c19d9fff4fda874
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 06/25/2019
ms.locfileid: "67389285"
---
# <a name="use-custom-settings-for-windows-phone-81-devices-in-intune"></a>Aangepaste instellingen gebruiken voor Windows Phone 8.1-apparaten in Intune

Met Microsoft Intune kunt u aangepaste instellingen voor uw Windows Phone 8.1-apparaten toevoegen of maken met behulp van 'aangepaste profielen'. Aangepaste profielen zijn een functie in Intune. Ze zijn ontworpen om apparaatinstellingen en -functies toe te voegen die niet in Intune zijn ingebouwd.

In aangepaste profielen voor Windows Phone 8.1 worden OMA-URI-instellingen (Open Mobile Alliance Uniform Resource Identifier) gebruikt om verschillende functies te configureren. Deze instellingen worden doorgaans gebruikt door fabrikanten van mobiele apparaten om functies op het apparaat te beheren. [Windows Phone 8.1 MDM-protocoldocumentatie voor](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-phone/dn499787(v=technet.10)) vindt u de instellingen.

In dit artikel wordt beschreven hoe u een aangepast profiel maakt voor Windows Phone 8.1-apparaten. 

## <a name="create-the-profile"></a>Het profiel maken

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Voer de volgende instellingen in:

    - **Naam**: voer een naam in voor het profiel, zoals `windows phone custom profile`.
    - **Beschrijving:** voer een beschrijving in voor het profiel.
    - **Platform**: kies **Windows Phone 8.1**.
    - **Profieltype**: kies **Aangepast**.

4. Selecteer in **Aangepaste OMA-URI-instellingen** de optie **Toevoegen**. Voer de volgende instellingen in:

    - **Naam**: voer een unieke naam in voor de OMA-URI-instelling waaraan u deze kunt herkennen in de lijst met instellingen.
    - **Beschrijving**: geef een beschrijving op met een overzicht van de instelling en overige relevante informatie, zodat u het profiel beter kunt vinden.
    - **OMA-URI** (hoofdlettergevoelig): voer de OMA-URI in die u als instelling wilt gebruiken.
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

In het volgende voorbeeld, wordt Windows 8.1 phone-apparaten voorkomen dat mobiele netwerken te wijzigen wanneer buiten de dekkingsgebied provider.

- **Naam**: mobiel dataverkeer Roaming toestaan
- **Beschrijving**: toestaan of weigeren van mobiel dataverkeer roaming
- **OMA-URI** (hoofdlettergevoelig): ./Vendor/MSFT/PolicyManager/My/Connectivity/AllowCellularDataRoaming
- **Gegevenstype**: Integer
- **Waarde**: 0

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt nog niets. Vervolgens [wijst u het profiel toe](device-profile-assign.md).

Bekijk hoe u een aangepast profiel maakt op [Windows 10-apparaten](custom-settings-windows-10.md).
