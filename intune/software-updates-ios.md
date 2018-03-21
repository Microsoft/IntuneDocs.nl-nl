---
title: iOS-updatebeleid configureren in Microsoft Intune
titlesuffix: 
description: "Configureer updatebeleid voor iOS zodat de nieuwste software-update automatisch wordt geïnstalleerd door iOS-apparaten die onder supervisie staan."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.openlocfilehash: 6ba354fb3b39544f09363651abfd9e1a5c0f6154
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/08/2018
---
# <a name="configure-ios-update-policies-in-microsoft-intune"></a>iOS-updatebeleid configureren in Microsoft Intune
Dankzij updatebeleid voor iOS kan de nieuwste software-update automatisch worden geïnstalleerd door iOS-apparaten die onder supervisie staan. U kunt dagen en tijdstippen instellen waarop u niet wilt dat de update wordt geïnstalleerd.

## <a name="configure-the-ios-update-policy"></a>Updatebeleid voor iOS configureren
1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
2. In het deelvenster **Intune** kiest u **Software-updates** > **Updatebeleid voor iOS**.
4. Kies in het deelvenster voor beleid de optie **Maken** en voer een naam en beschrijving in voor het beleid.
5. Selecteer **Instellingen** > **Configureren** en voer de details in voor het geval waarbij iOS-apparaten niet worden gedwongen de meest recente update te installeren.
6. Kies **OK** om deze configuratie op te slaan. U bent nu terug in het deelvenster **Updatebeleid maken**. Kies **Maken** om het beleid te maken en uw instellingen op te slaan.

Het profiel wordt gemaakt en wordt weergegeven in het deelvenster met de lijst met updatebeleidsregels voor iOS.

## <a name="assign-an-ios-update-policy-to-users"></a>Updatebeleid voor iOS aan gebruikers toewijzen
Als u een updatebeleid voor iOS aan gebruikers wilt toewijzen, kiest u een beleid dat u hebt geconfigureerd. U kunt de bestaande beleidsregels vinden in het deelvenster **Software-updates** > **Updatebeleid voor iOS**.
1. Kies het beleid dat u aan gebruikers wilt toewijzen en kies **Toewijzingen**. Hiermee opent u het deelvenster waar u Azure Active Directory-beveiligingsgroepen kunt selecteren en aan het beleid kunt toewijzen.
2. Kies **Geselecteerde groepen** om het deelvenster met de Azure AD-beveiligingsgroepen te openen.
3. Kies **Opslaan** om het beleid voor gebruikers te implementeren.

U hebt het beleid toegepast op gebruikers. De apparaten die worden gebruikt door de gebruikers op wie het beleid is toegepast, worden gecontroleerd om te zien of ze voldoen aan de updatenaleving.

## <a name="change-the-restricted-days-for-the-policy"></a>De dagen met beperkingen voor het beleid wijzigen
1. Kies in het deelvenster **Software-updates** de optie **Updatebeleid voor iOS**.
2. Selecteer het updatebeleid voor iOS dat u wilt bijwerken.
3. Selecteer **Eigenschappen** > **Instellingen** en werk de gegevens voor de dagen met beperkingen bij.

## <a name="monitor-ios-devices-with-older-ios-versions"></a>iOS-apparaten met oudere iOS-versies bewaken
<!-- 1352223 -->
Het rapport **Out-of-date iOS Devices** (Verouderde iOS-apparaten) is beschikbaar via het deelvenster **Software-updates** > **Updatebeleid voor iOS**. Het rapport bevat een lijst met gecontroleerde iOS-apparaten waarop een iOS-updatebeleid van toepassing is geweest en konden worden bijgewerkt. Voor elk apparaat kunt u bekijken waarom het apparaat niet automatisch is bijgewerkt.
