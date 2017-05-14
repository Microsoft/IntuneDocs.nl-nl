---
title: Aangepaste profielinstellingen in Intune voor Android for Work
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: in dit onderwerp leest u hoe u in Intune aangepaste profielinstellingen maakt voor apparaten met Android for Work.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4724d6e5-05e5-496c-9af3-b74f083141f8
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: a9748a0ad6b9bbe10e36ba133ba74edb6aa6e09a
ms.openlocfilehash: 69a500c78e0cc732cee2967c35ea4b2fec53b54b
ms.contentlocale: nl-nl
ms.lasthandoff: 05/05/2017


---

# <a name="create-intune-custom-profile-settings-for-android-for-work-devices"></a>In Intune aangepaste profielinstellingen voor apparaten met Android for Work maken

Gebruik het aangepaste Android for Work-configuratiebeleid van Intune om OMA-URI-instellingen toe te wijzen waarmee u de functies op Android for Work-apparaten kunt beheren. Dit zijn standaardinstellingen die door veel fabrikanten van mobiele apparaten worden gebruikt voor het beheren van apparaatfuncties.

Op deze manier kunt u Android-instellingen toewijzen die u niet kunt configureren met Intune-beleid. Intune biedt momenteel ondersteuning voor een beperkt aantal aangepaste Android-beleidsregels. Zie de voorbeelden in dit onderwerp om na te gaan welk beleid u kunt configureren.

## <a name="create-a-custom-profile"></a>Een aangepast profiel maken

1. Volg de instructies in [Aangepaste apparaatinstellingen configureren](/intune-azure/configure-devices/how-to-configure-custom-settings) om aan de slag te gaan.
2. Klik op de blade **Aangepaste OMA-URI-instellingen** op **Toevoegen** om een nieuwe instelling toe te voegen.
3. Configureer op de blade **Rij toevoegen** het volgende:
    - **Naam**: voer een unieke naam in voor de aangepaste instellingen voor Android for Work waarmee u deze gemakkelijk kunt herkennen in de Intune-portal.
    - **Beschrijving**: geef een beschrijving op die een overzicht biedt van het aangepaste Android-beleid, evenals andere relevante informatie waarmee u het beleid kunt vinden.
    - **OMA-URI**: voer de OMA-URI in waarvoor u een instelling wilt opgeven.
    - **Gegevenstype**: selecteer het gegevenstype waarin u deze OMA-URI-instelling opgeeft. Kies uit: **Tekenreeks**, **Tekenreeks (XML-bestand)**, **Datum en tijd**, **Geheel getal**, **Drijvende komma**, **Booleaanse waarde** of **Base64 (bestand)**.
    - **Waarde**: geef de waarde op die u wilt koppelen aan de OMA-URI die u eerder hebt opgegeven. De methode die u gebruikt voor het opgeven van deze waarde verschilt, afhankelijk van het gegevenstype dat u hebt geselecteerd. Als u bijvoorbeeld **Datum en tijd** hebt gekozen, selecteert u de waarde in een datumkiezer.
4. Wanneer u klaar bent, kiest u OK om terug te keren naar **Aangepaste OMA-URI-instellingen** en vervolgens voegt u meer instellingen toe of kiest u **Maken** om het aangepaste profiel te maken.


## <a name="example"></a>Voorbeeld

In dit voorbeeld maakt u een aangepast profiel dat kan worden gebruikt om te beperken of het kopiëren en plakken tussen werk-apps en persoonlijke apps op beheerde apparaten met Android for Work is toegestaan.

1. Gebruik de procedure in dit onderwerp om een aangepast profiel te maken voor apparaten met Android for Work en gebruik hierbij de volgende waarden:
    - **Naam**: voer 'Kopiëren en plakken blokkeren' of een tekst van uw eigen keuze in.
    - **Beschrijving**: voer 'Kopiëren/plakken tussen werk-apps en persoonlijke apps blokkeren' of een tekst van uw eigen keuze in.
    - **OMA-URI**: voer **./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste** in.
    - **Gegevenstype**: selecteer **Booleaanse waarde** om aan te geven dat de waarde voor deze OMA-URI **True** of **False** is.
    - **Waarde**: selecteer **True**.
2. Als u klaar bent, moet de instelling er uitzien zoals op deze afbeelding.
![Kopiëren en plakken blokkeren voor Android for Work.](./media/custom-policy-afw-copy-paste.png)
3. Als u nu dit profiel toewijst aan apparaten met Android for Work die u beheert, is het kopiëren en plakken tussen apps in het werkprofiel en persoonlijke profiel geblokkeerd.
