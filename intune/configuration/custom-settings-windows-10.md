---
title: Aangepaste instellingen toevoegen voor Windows 10-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Een aangepast profiel toevoegen of maken om de OMA-URI-instellingen te gebruiken voor apparaten met Windows 10 in Microsoft Intune. Een aangepast profiel gebruiken voor het toevoegen van aangepaste instellingen.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e8f896f514223cdb5e5faae5f781421d37fffd01
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72495354"
---
# <a name="use-custom-settings-for-windows-10-devices-in-intune"></a>Aangepaste instellingen gebruiken voor Windows 10-apparaten in Intune

Met Microsoft Intune kunt u aangepaste instellingen voor uw Windows 10-apparaten toevoegen of maken met behulp van 'aangepaste profielen'. Aangepaste profielen zijn een functie in Intune. Ze zijn ontworpen om apparaatinstellingen en -functies toe te voegen die niet in Intune zijn ingebouwd.

In aangepaste profielen voor Windows 10 worden OMA-URI-instellingen (Open Mobile Alliance Uniform Resource Identifier) gebruikt om verschillende functies te configureren. Deze instellingen worden doorgaans gebruikt door fabrikanten van mobiele apparaten om functies op het apparaat te beheren. 

In Windows 10 zijn veel CSP-instellingen (Configuration Service Provider) beschikbaar, zoals de [beleids-CSP (Policy Configuration Service Provider)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).

Als u een specifieke instelling zoekt, moet u er rekening mee houden dat het [beperkingsprofiel voor Windows 10-apparaten](device-restrictions-windows-10.md) tal van ingebouwde instellingen bevat. U hoeft daarom mogelijk geen aangepaste waarden in te voeren.

In dit artikel wordt het volgende beschreven:

- Een aangepast profiel maken voor Windows 10-apparaten
- Omvat een lijst met de aanbevolen OMA-URI-instellingen
- Biedt een voorbeeld van een aangepast profiel waarmee een VPN-verbinding wordt geopend

## <a name="create-the-profile"></a>Het profiel maken

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Voer de volgende instellingen in:

    - **Naam**: voer een naam in voor het profiel, zoals `windows 10 custom profile`.
    - **Beschrijving:** voer een beschrijving in voor het profiel.
    - **Platform**: kies **Windows 10 en hoger**.
    - **Profieltype**: kies **Aangepast**.

4. Selecteer in **Aangepaste OMA-URI-instellingen** de optie **Toevoegen**. Voer de volgende instellingen in:

    - **Naam**: voer een unieke naam in voor de OMA-URI-instelling waaraan u deze kunt herkennen in de lijst met instellingen.
    - **Beschrijving**: voer een beschrijving in met een overzicht van de instelling en eventuele andere belangrijke details.
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

In het volgende voorbeeld wordt de instelling **Connectivity/AllowVPNOverCellular** ingeschakeld. Met deze instelling kan met een Windows-10-apparaat een VPN-verbinding worden gemaakt in een mobiel netwerk.

![Voorbeeld van een aangepast beleid met VPN-instellingen](./media/custom-settings-windows-10/custom-policy-example.png)

## <a name="find-the-policies-you-can-configure"></a>De beleidsregels zoeken die u kunt configureren

Een complete lijst met alle CSP's (configuratieserviceproviders) die door Windows 10 worden ondersteund, vindt u in de [naslaginformatie voor configuratieserviceproviders](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference).

Niet alle instellingen zijn compatibele met alle versies van Windows 10. In [Referentie voor Configuration Service Providers](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) leest u welke versies worden ondersteund voor elke CSP.

Bovendien biedt Intune geen ondersteuning voor alle instellingen die worden vermeld in de [naslaginformatie voor configuratieserviceproviders](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference). Als u wilt weten of de gewenste instelling door Intune wordt ondersteund, opent u het artikel voor de betreffende instelling. U kunt op elke instellingenpagina zien welke bewerkingen worden ondersteund. Voor gebruik in combinatie met Intune moet de instelling de bewerking **Toevoegen**, **Vervangen** en **Ophalen** ondersteunen. Als de waarde die is geretourneerd door de bewerking **Ophalen** niet overeenkomt met de waarde die is opgegeven door de bewerkingen **Toevoegen** of **Vervangen**, meldt Intune vervolgens een compatibiliteitsfout.

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt nog niets. Vervolgens [wijst u het profiel toe](device-profile-assign.md).
