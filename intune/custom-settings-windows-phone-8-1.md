---
title: Aangepaste Microsoft Intune-instellingen voor apparaten met Windows Phone 8.1
titleSuffix: ''
description: Meer informatie over de instellingen die u kunt gebruiken in een aangepast Windows Phone 8.1-profiel.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 83c123f3752680dbc7faca76aa525a0f035831d7
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-windows-phone-81"></a>Aangepaste Microsoft Intune-apparaat instellingen voor apparaten met Windows Phone 8.1

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Gebruik het **aangepaste** profiel voor Windows Phone 8.1 van Microsoft Intune om OMA-URI-instellingen toe te wijzen die kunnen worden gebruikt om functies op Windows Phone 8.1-apparaten te beheren. Dit zijn standaardinstellingen die door veel fabrikanten van mobiele apparaten worden gebruikt voor het beheren van apparaatfuncties.

Op deze manier kunt u instellingen toewijzen die niet met een ander Intune-beleid kunnen worden geconfigureerd.

## <a name="custom-policy-settings-for-windows-phone-81-devices"></a>Aangepaste beleidsinstellingen voor Windows Phone 8.1-apparaten

1. Volg de instructies in [Aangepaste apparaatinstellingen configureren in Microsoft Intune](custom-settings-configure.md) om aan de slag te gaan.
2. Klik in het deelvenster **Aangepaste OMA-URI-instellingen** op **Toevoegen** om een of meer OMA-URI-instellingen toe te voegen.
3. Configureer voor elke instelling de volgende waarden in het deelvenster **Rij bewerken**:
    - **Naam**: voer een unieke naam in voor de OMA-URI-instelling waaraan u deze kunt herkennen in de lijst met instellingen.
    - **Beschrijving**: geef een beschrijving op die een overzicht geeft van de instelling en overige relevante informatie die u helpt om de instelling terug te vinden.
    - **OMA-URI**: geef aan voor welke OMA-URI u een instelling wilt opgeven.
    - **Gegevenstype**: selecteer het gegevenstype waarin u deze OMA-URI-instelling opgeeft. Kies uit: **Tekenreeks**, **Tekenreeks (XML)**, **Datum en tijd**, **Geheel getal**, **Drijvende komma**, **Booleaanse waarde** of **Base64**.
    - **Waarde**: voer de waarde of het bestand in die of dat moet worden gekoppeld aan de OMA-URI die u hebt ingevoerd.

4. Klik op **OK** als u klaar bent en voeg vervolgens zo nodig meer instellingen toe.
