---
title: Windows Holographic upgraden naar Windows Holographic for Business
titleSuffix: Microsoft Intune
description: Lees hoe u apparaten met Windows Holographic kunt upgraden naar Windows Holographic for Business
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e7c750b372c297637abcdb9e941dae17714d081b
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/08/2018
---
# <a name="upgrade-devices-running-windows-holographic-to-windows-holographic-for-business"></a>Apparaten met Windows Holographic upgraden naar Windows Holographic for Business


Als u met Microsoft Intune apparaten wilt beheren waarop Windows Holographic wordt uitgevoerd, moet u upgraden van Windows Holographic naar Windows Holographic for Business. U kunt een Edition Upgrade-profiel maken voor de upgrade. Voor Microsoft HoloLens kunt u de Commercial Suite aanschaffen om de vereiste licentie voor de upgrade op te halen. Zie [Windows Holographic for Business-functies ontgrendelen](https://docs.microsoft.com/en-us/hololens/hololens-upgrade-enterprise) voor meer informatie.

## <a name="to-set-up-an-edition-upgrade-device-configuration-profile"></a>Een apparaatconfiguratieprofiel van Edition Upgrade instellen

1. Meld u aan bij de [Azure-portal](https://portal.azure.com) met uw beheerdersaccount.


2.  Klik op **Apparaatconfiguratie**, **Profielen** en vervolgens op **+ Profiel maken**.

    ![Profiel maken](media/Holographic-create-profile.png)

3.  Typ in het deelvenster **Profiel maken** een naam voor het profiel, selecteer **Windows 10 en later** als platform en selecteer **Edition Upgrade** als profieltype. Klik op **Instellingen configureren**.

5. Ga naar de pagina **Edition Upgrade** en selecteer bij **Editie om naar te upgraden** de optie **Windows 10 Holographic for Business**. Blader bij **Licentiebestand** naar het XML-licentiebestand dat voor u is opgegeven en selecteer dit bestand.

    ![Voer de naam van het XML-bestand in](media/Holographic-edition-upgrade.png)
 
5.  Klik op **OK** en klik vervolgens op **Maken** om het profiel te maken.


## <a name="deploy-the-edition-upgrade-policy"></a>Het editie-upgradebeleid implementeren

Daarna kunt u het Edition Upgrade-profiel toewijzen aan geselecteerde groepen of apparaten.

1. Klik op het profiel dat u in de vorige stappen hebt gemaakt op **Toewijzingen**.

2. Selecteer in de pagina **Toewijzingen** de gebruikersgroepen en apparaten die u wilt opnemen en uitsluiten met het beleid.

![Groepen opnemen en uitsluiten](media/Holographic-groups.PNG)

Als deze gebruikers of apparaten zijn ingeschreven in Intune, wordt het Edition Upgrade-profiel toegepast. 

## <a name="next-steps"></a>Volgende stappen

Zie [Aan de slag met groepen](get-started-groups.md) voor meer informatie over groepen.


