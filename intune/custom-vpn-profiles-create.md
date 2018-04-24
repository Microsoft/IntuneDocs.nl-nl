---
title: Aangepaste VPN-profielen maken met Microsoft Intune
titleSuffix: ''
description: Aangepaste configuraties gebruiken om VPN-profielen te maken in Intune.
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
ms.openlocfilehash: ec9b959d086051985287a62f7d10fe8d4cbad7e9
ms.sourcegitcommit: 28ed8902a11500b195fff839d59b90c16af6e743
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/29/2018
---
# <a name="how-to-create-custom-vpn-profiles-in-microsoft-intune"></a>Aangepaste VPN-profielen maken in Microsoft Intune

U kunt aangepast Intune-configuratiebeleid gebruiken om VPN-profielen te maken voor de volgende platformen:

* Android 4 en hoger
* Geregistreerde apparaten met Windows 8.1 en hoger
* Windows Phone 8.1 en hoger
* Geregistreerde apparaten met Windows 10 Desktop 
* Windows 10 Mobile

Dit type beleid kan handig zijn wanneer het standaardbeleid voor Intune VPN niet de instellingen bevat die u wilt gebruiken.

## <a name="to-create-a-custom-configuration-policy"></a>Een aangepast configuratiebeleid maken:

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies in het deelvenster **Intune** de optie **Apparaatconfiguratie**.
2. Kies in het deelvenster **Apparaatconfiguratie** onder de sectie **Beheren** de optie **Profielen**.
5. Kies **Profiel maken** in het deelvenster Profielen.
6. Voer in het deelvenster **Profiel maken** een **naam** en een **beschrijving** in voor het VPN-profiel.
7. Selecteer in de vervolgkeuzelijst **Platform** het apparaatplatform waarop u de VPN-instellingen wilt toepassen. Op dit moment kunt u een van de volgende platformen kiezen voor aangepaste apparaatinstellingen:
    - **Android**
    - **Android for Work**
    - **iOS** (geconfigureerd met een bestand dat u hebt geëxporteerd uit Apple Configurator).
    - **macOS** (geconfigureerd met een bestand dat u hebt geëxporteerd uit Apple Configurator).
    - **Windows Phone 8.1**
    - **Windows 8.1 en hoger**
    - **Windows 10 en hoger**
6. Kies **Aangepast** in de vervolgkeuzelijst **Profieltype**.
7. Kies **Toevoegen** in het deelvenster **Aangepaste OMA-URI-instellingen** voor elke URI-instelling die u wilt opgeven, geef de gevraagde gegevens op en kies vervolgens **OK**. Hier volgt een voorbeeld:

   ![Dialoogvenster met aangepaste configuratie van een VPN-profiel](./media/Intune_Add_VPN_URI.png)

4.  Nadat u alle vereiste URI-instellingen hebt ingevoerd, kiest u **OK** en kiest u **Maken** in het deelvenster **Profiel maken**.

Het profiel wordt gemaakt en wordt weergegeven in het deelvenster met de profielenlijst.
Zie [How to assign device profiles](device-profile-assign.md) (Apparaatprofielen toewijzen) als u wilt doorgaan en dit profiel wilt toewijzen aan groepen.




