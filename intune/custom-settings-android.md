---
title: Aangepaste Intune-instellingen voor Android-apparaten
titleSuffix: Azure portal
description: Meer informatie over de instellingen die u kunt gebruiken in een aangepast Android-profiel.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 92014eb9fd5564c0527b8cbf68732a51cf83bc96
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/09/2017
---
# <a name="custom-settings-for-android-devices-in-microsoft-intune"></a>Aangepaste instellingen voor Android-apparaten in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Gebruik het **aangepaste** profiel van Microsoft Intune voor Android om OMA-URI-instellingen toe te wijzen die kunnen worden gebruikt om functies op Android-apparaten te beheren. Dit zijn standaardinstellingen die door veel fabrikanten van mobiele apparaten worden gebruikt voor het beheren van apparaatfuncties.

Op deze manier kunt u Android-instellingen toewijzen die u niet kunt configureren met Intune-beleid.

## <a name="custom-profile-settings-for-android-devices"></a>Aangepaste profielinstellingen voor Android-apparaten

1. Volg de instructies in [Aangepaste apparaatinstellingen configureren in Microsoft Intune](custom-settings-configure.md) om aan de slag te gaan.
2. Kies op de blade **Profiel maken** de optie **Instellingen** om een of meer OMA-URI-instellingen toe te voegen.
3. Configureer op de blade **Rij bewerken** de volgende waarden voor elke instelling:
    - **Naam**: voer een unieke naam in voor de OMA-URI-instelling waaraan u deze kunt herkennen in de lijst met instellingen.
    - **Beschrijving**: geef een beschrijving op die een overzicht geeft van de instelling en overige relevante informatie die u helpt om de instelling terug te vinden.
    - **Gegevenstype**: selecteer het gegevenstype waarin u deze OMA-URI-instelling opgeeft. Kies uit **Tekenreeks**, **Tekenreeks (XML)**, **Datum en tijd**, **Geheel getal**, **Drijvende komma** of **Booleaanse waarde**.
    - **OMA-URI**: geef aan voor welke OMA-URI u een instelling wilt opgeven.
    - **Waarde**: voer de waarde in die moet worden gekoppeld aan de OMA-URI die u hebt ingevoerd.
4. Klik op **OK** als u klaar bent en voeg vervolgens zo nodig meer instellingen toe.

## <a name="next-steps"></a>Volgende stappen

Als u de instellingen hebt voltooid, wordt het profiel gemaakt en weergegeven op de blade met de profielenlijst. Zie [How to assign device profiles](device-profile-assign.md) (Apparaatprofielen toewijzen) als u wilt doorgaan en dit profiel wilt toewijzen aan groepen.

Zie de volgende documenten voor een paar voorbeelden van aangepaste instellingen:

- [Een aangepast Microsoft Intune-apparaatprofiel gebruiken om een Wi-Fi-profiel te maken met een vooraf gedeelde sleutel](/intune/wi-fi-profile-shared-key)
- [Een aangepast Microsoft Intune-profiel gebruiken voor het maken van een VPN-profiel per app voor Android-apparaten](/intune/android-pulse-secure-per-app-vpn)
- [Aangepast beleid gebruiken om apps toe te staan of te blokkeren voor Samsung KNOX Standard-apparaten in Microsoft Intune](/intune/samsung-knox-apps-allow-block)
