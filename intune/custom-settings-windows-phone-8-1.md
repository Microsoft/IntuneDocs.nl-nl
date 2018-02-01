---
title: Aangepaste Intune-instellingen voor Windows Phone 8.1-apparaten
titleSuffix: Azure portal
description: Meer informatie over de instellingen die u kunt gebruiken in een aangepast Windows Phone 8.1-profiel.
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 21c55041-3821-4a62-9f85-855b97dba269
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bbe76f454575d9f09617b12e3811b0c7d5a75ca1
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="custom-settings-for-windows-phone-81-devices-in-microsoft-intune"></a>Aangepaste instellingen voor Windows Phone 8.1-apparaten in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Gebruik het **aangepaste** profiel voor Windows Phone 8.1 van Microsoft Intune om OMA-URI-instellingen toe te wijzen die kunnen worden gebruikt om functies op Windows Phone 8.1-apparaten te beheren. Dit zijn standaardinstellingen die door veel fabrikanten van mobiele apparaten worden gebruikt voor het beheren van apparaatfuncties.

Op deze manier kunt u instellingen toewijzen die niet met een ander Intune-beleid kunnen worden geconfigureerd.

## <a name="custom-policy-settings-for-windows-phone-81-devices"></a>Aangepaste beleidsinstellingen voor Windows Phone 8.1-apparaten

1. Volg de instructies in [Aangepaste apparaatinstellingen configureren in Microsoft Intune](custom-settings-configure.md) om aan de slag te gaan.
2. Kies op de blade **Profiel maken** de optie **Instellingen** om een of meer OMA-URI-instellingen toe te voegen.
3. Configureer voor elke instelling de volgende waarden op de blade **Rij bewerken**:
    - **Naam**: voer een unieke naam in voor de OMA-URI-instelling waaraan u deze kunt herkennen in de lijst met instellingen.
    - **Beschrijving**: geef een beschrijving op die een overzicht geeft van de instelling en overige relevante informatie die u helpt om de instelling terug te vinden.
    - **OMA-URI**: geef aan voor welke OMA-URI u een instelling wilt opgeven.
    - **Gegevenstype**: selecteer het gegevenstype waarin u deze OMA-URI-instelling opgeeft. Kies uit: **Tekenreeks**, **Datum en tijd**, **Geheel getal**, **Drijvende komma** en **Booleaanse waarde**.
    - **Waarde**: voer de waarde in die moet worden gekoppeld aan de OMA-URI die u hebt ingevoerd.

4. Klik op **OK** als u klaar bent en voeg vervolgens zo nodig meer instellingen toe.
