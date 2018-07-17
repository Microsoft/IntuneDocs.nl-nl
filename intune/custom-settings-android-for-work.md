---
title: Aangepaste profielinstellingen in Intune voor Android-werkprofielen
titlesuffix: Microsoft Intune
description: Meer informatie over het maken van aangepaste Microsoft Intune-profielinstellingen voor apparaten met Android-werkprofielen.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/12/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4724d6e5-05e5-496c-9af3-b74f083141f8
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 109c50acf194598017aa507a0979ad3b9298de9e
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905288"
---
# <a name="create-intune-custom-profile-settings-for-android-work-profile-devices"></a>Aangepaste profielinstellingen maken in Intune voor apparaten met Android-werkprofielen

Gebruik het aangepaste configuratiebeleid van Intune voor Android-werkprofielen om OMA-URI-instellingen toe te wijzen waarmee u de functies op apparaten met Android-werkprofielen kunt beheren. Dit zijn standaardinstellingen die door veel fabrikanten van mobiele apparaten worden gebruikt voor het beheren van apparaatfuncties.

Op deze manier kunt u Android-instellingen toewijzen die u niet kunt configureren met Intune-beleid. Intune biedt momenteel ondersteuning voor een beperkt aantal aangepaste Android-beleidsregels. Zie de voorbeelden in dit artikel om na te gaan welk beleid u kunt configureren.

## <a name="create-a-custom-profile"></a>Een aangepast profiel maken

1. Volg de instructies in [Aangepaste apparaatinstellingen configureren](custom-settings-configure.md) om aan de slag te gaan. Kies als **platform** **Android Enterprise** en als **profieltype** **Aangepast**.
2. Klik op de blade **Aangepaste OMA-URI-instellingen** op **Toevoegen** om een nieuwe instelling toe te voegen.
3. Configureer op de blade **Rij toevoegen** het volgende:
    - **Naam**: voer een unieke naam in voor de aangepaste instellingen voor het Android-werkprofiel waarmee u deze gemakkelijk kunt herkennen in de Azure-portal.
    - **Beschrijving**: geef een beschrijving op die een overzicht biedt van het aangepaste Android-beleid, evenals andere relevante informatie waarmee u het beleid kunt vinden.
    - **OMA-URI**: voer de OMA-URI in waarvoor u een instelling wilt opgeven.
    - **Gegevenstype**: selecteer het gegevenstype waarin u deze OMA-URI-instelling opgeeft. Kies uit: **Tekenreeks**, **Tekenreeks (XML-bestand)**, **Datum en tijd**, **Geheel getal**, **Drijvende komma**, **Booleaanse waarde** of **Base64 (bestand)**.
    - **Waarde**: geef de waarde op die u wilt koppelen aan de OMA-URI die u eerder hebt opgegeven. De methode die u gebruikt voor het opgeven van deze waarde verschilt, afhankelijk van het gegevenstype dat u hebt geselecteerd. Als u bijvoorbeeld **Datum en tijd** hebt gekozen, selecteert u de waarde in een datumkiezer.
4. Wanneer u klaar bent, kiest u OK om terug te keren naar **Aangepaste OMA-URI-instellingen** en vervolgens voegt u meer instellingen toe of kiest u **Maken** om het aangepaste profiel te maken.


## <a name="example"></a>Voorbeeld

In dit voorbeeld maakt u een aangepast profiel dat kan worden gebruikt om beperkingen op te leggen in hoeverre de handelingen kopiëren en plakken tussen werk-apps en persoonlijke apps op apparaten met Android-werkprofiel zijn toegestaan.

1. Gebruik de procedure in dit artikel om een aangepast profiel te maken voor apparaten met Android-werkprofielen for Work en gebruik hierbij de volgende waarden:
    - **Naam**: voer 'Kopiëren en plakken blokkeren' of een tekst van uw eigen keuze in.
    - **Beschrijving**: voer 'Kopiëren/plakken tussen werk-apps en persoonlijke apps blokkeren' of een tekst van uw eigen keuze in.
    - **OMA-URI**: voer **./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste** in.
    - **Gegevenstype**: selecteer **Booleaanse waarde** om aan te geven dat de waarde voor deze OMA-URI **True** of **False** is.
    - **Waarde**: selecteer **True**.
2. Als u klaar bent, moet de instelling er uitzien zoals op deze afbeelding.
![Kopiëren en plakken blokkeren voor een Android-werkprofiel.](./media/custom-policy-afw-copy-paste.png)
3. Wanneer u nu dit aangepast profiel aan door u beheerde apparaten met Android-werkprofiel toewijst, wordt kopiëren en plakken tussen apps in de werkprofielen en persoonlijke profielen geblokkeerd.