---
title: Aangepaste VPN-profielen maken met Microsoft Intune
titleSuffix: Azure portal
description: Aangepaste configuraties gebruiken om VPN-profielen te maken in Intune.
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 70af9ce41efa7f52987e1103b89493b4cf200091
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-create-custom-vpn-profiles-in-microsoft-intune"></a>Aangepaste VPN-profielen maken in Microsoft Intune

## <a name="create-a-custom-configuration"></a>Een aangepaste configuratie maken
U kunt aangepast Intune-configuratiebeleid gebruiken om VPN-profielen te maken voor:

* Apparaten met Android 4 en hoger
* Geregistreerde apparaten met Windows 8.1 en hoger
* Apparaten met Windows Phone 8.1 en hoger
* Geregistreerde apparaten met Windows 10 Desktop 
* Apparaten met Windows 10 Mobile

Dit type beleid kan handig zijn wanneer het standaardbeleid voor Intune VPN niet de instellingen bevat die u wilt gebruiken.

## <a name="to-create-a-custom-configuration-policy"></a>Een aangepast configuratiebeleid maken:

1. Meld u aan bij Azure-portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies op de blade **Intune** de optie **Apparaatconfiguratie**.
4. Kies **Beheren** > **Profielen** op de blade **Apparaatconfiguratie**.
5. Kies **Profiel maken** op de blade Profielen.
6. Voer op de blade **Profiel maken** een **naam** en een **beschrijving** in voor het VPN-profiel.
7. Selecteer in de vervolgkeuzelijst **Platform** het apparaatplatform waarop u de VPN-instellingen wilt toepassen. Op dit moment kunt u een van de volgende platformen kiezen voor aangepaste apparaatinstellingen:
    - **Android**
    - **iOS** (geconfigureerd met een bestand dat u hebt geëxporteerd uit Apple Configurator).
    - **macOS** (geconfigureerd met een bestand dat u hebt geëxporteerd uit Apple Configurator).
    - **Windows Phone 8.1**
    - **Windows 10 en hoger**
6. Kies **Aangepast** in de vervolgkeuzelijst **Profieltype**.
7. Kies **Toevoegen** op de blade **Aangepaste OMA-URI-instellingen** voor elke URI-instelling die u wilt opgeven, geef de gevraagde gegevens op en kies vervolgens **OK**. Hier volgt een voorbeeld:

   ![Dialoogvenster met aangepaste configuratie van een VPN-profiel](./media/Intune_Add_VPN_URI.png)

4.  Nadat u alle vereiste URI-instellingen hebt ingevoerd, kiest u **OK** en kiest u **Maken** op de blade **Profiel maken**.

Het profiel wordt gemaakt en wordt weergegeven op de blade met de profielenlijst.
Zie [How to assign device profiles](device-profile-assign.md) (Apparaatprofielen toewijzen) als u wilt doorgaan en dit profiel wilt toewijzen aan groepen.




