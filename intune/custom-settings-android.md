---
title: Aangepaste instellingen toevoegen voor Android-apparaten Microsoft Intune - Azure | Microsoft Docs
description: Een aangepast profiel toevoegen voor Android-apparaten om een Wi-Fi-profiel te maken met een vooraf gedeelde sleutel, per app een VPN-profiel maken of apps toestemming geven/blokkeren voor Samsung Knox Standard-apparaten in Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0195e138b59fae019fa2bc02aadf211257a65cac
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="custom-settings-for-android-devices---intune"></a>Aangepaste instellingen voor Android-apparaten - Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Aangepaste profielen gebruiken OMA-URI-instellingen (Open Mobile Alliance Uniform Resource Identifier) om verschillende functies op Android-apparaten te configureren. Deze instellingen worden doorgaans gebruikt door fabrikanten van mobiele apparaten om functies op het apparaat te beheren.

Door een aangepast profiel te gebruiken, kunt u de volgende Android-instellingen configureren en toewijzen. Deze instellingen niet zijn ingebouwd in het Intune-beleid:

- [Een Wi-Fi-profiel maken met een vooraf gedeelde sleutel](/intune/wi-fi-profile-shared-key)
- [Een VPN per app-profiel maken](/intune/android-pulse-secure-per-app-vpn)
- [Apps toestaan of blokkeren voor Samsung KNOX Standard-apparaten](/intune/samsung-knox-apps-allow-block)

>[!IMPORTANT]
> Alleen de hierboven genoemde instellingen kunnen worden geconfigureerd door dit profieltype. Android-apparaten geven geen volledige lijst weer met OMA-URI-instellingen die u kunt configureren. Als u meer instellingen wilt bekijken, stemt u voor meer instellingen op de [Intune Uservoice-site](https://microsoftintune.uservoice.com/forums/291681-ideas).

## <a name="custom-profile-settings-for-android-devices"></a>Aangepaste profielinstellingen voor Android-apparaten

1. Meld u aan bij [Azure Portal](https://portal.azure.com). 
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Maak een aangepast profiel met behulp van het Android-platform. In [Aangepaste apparaatinstellingen configureren in Microsoft Intune](custom-settings-configure.md) staan de stappen beschreven.
4. Selecteer in **Aangepaste OMA-URI-instellingen** **Toevoegen** en selecteer vervolgens **Rij toevoegen**.
5. Voer de volgende eigenschappen in:

   - **Naam**: voer een unieke naam in voor de OMA-URI-instelling, zodat u deze gemakkelijk kunt vinden.
   - **Beschrijving**: voer een beschrijving in die een overzicht geeft van de instelling en eventuele andere belangrijke details.
   - **Gegevenstype**: voer het gegevenstype in dat u voor deze OMA-URI-instelling gebruikt. Kies uit **Tekenreeks**, **Tekenreeks (XML)**, **Datum en tijd**, **Geheel getal**, **Drijvende komma** of **Booleaanse waarde**.
   - **OMA-URI**: voer de gewenste OMA-URI in.
   - **Waarde**: voer de waarde in die moet worden gekoppeld aan de OMA-URI die u hebt ingevoerd.

6. Selecteer **OK** om uw wijzigingen op te slaan. Blijf, indien nodig, meer instellingen toevoegen.

## <a name="next-steps"></a>Volgende stappen

Als u de instellingen hebt voltooid, wordt het profiel gemaakt en weergegeven in de lijst. Zie [Apparaatprofielen toewijzen](device-profile-assign.md) als u dit profiel wilt toewijzen aan groepen.
