---
title: iOS-updatebeleid configureren in Microsoft Intune
titlesuffix: 
description: "Configureer updatebeleid voor iOS zodat de nieuwste software-update automatisch wordt geïnstalleerd door iOS-apparaten die onder supervisie staan."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.openlocfilehash: 2062f9cd551ec6d7f42449041e6c8de837221631
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/05/2018
---
# <a name="configure-ios-update-policies-in-microsoft-intune"></a>iOS-updatebeleid configureren in Microsoft Intune
Dankzij updatebeleid voor iOS kan de nieuwste software-update automatisch worden geïnstalleerd door iOS-apparaten die onder supervisie staan. U kunt dagen en tijdstippen instellen waarop u niet wilt dat de update wordt geïnstalleerd.

## <a name="configure-the-ios-update-policy"></a>Updatebeleid voor iOS configureren
1. Ga naar de Intune-pagina in Azure Portal.
2. Kies **Software-updates** > **Updatebeleid voor iOS** op de pagina **Intune**.
4. Kies op de pagina voor beleid de optie **Maken** en voer een naam en beschrijving voor het beleid in.
5. Selecteer **Instellingen** > **Configureren** en voer de details in voor het geval waarbij iOS-apparaten niet worden gedwongen de meest recente update te installeren.
6. Kies **OK** om deze configuratie op te slaan. U bent nu terug op de pagina **Updatebeleid maken**. Kies **Maken** om het beleid te maken en uw instellingen op te slaan.

Het profiel wordt gemaakt en wordt weergegeven op de pagina met de lijst met updatebeleidsregels voor iOS.

## <a name="assign-an-ios-update-policy-to-users"></a>Updatebeleid voor iOS aan gebruikers toewijzen
Als u een updatebeleid voor iOS aan gebruikers wilt toewijzen, kiest u een beleid dat u hebt geconfigureerd. U kunt bestaande beleidsregel vinden op de pagina **Software-updates** > **Updatebeleid voor iOS**.
1. Kies het beleid dat u aan gebruikers wilt toewijzen en kies **Toewijzingen**. Hiermee opent u de pagina waar u Azure Active Directory-beveiligingsgroepen kunt selecteren en aan het beleid kunt toewijzen.
2. Kies **Groepen selecteren** om de pagina met de Azure AD-beveiligingsgroepen te openen. Kies **Selecteren** om het beleid voor gebruikers te implementeren.

U hebt het beleid toegepast op gebruikers. De apparaten die worden gebruikt door de gebruikers op wie het beleid is toegepast, worden gecontroleerd om te zien of ze voldoen aan de updatenaleving.

## <a name="change-the-restricted-days-for-the-policy"></a>De dagen met beperkingen voor het beleid wijzigen
1. Kies op de pagina **Software-updates** de optie **Updatebeleid voor iOS**.
2. Selecteer het updatebeleid voor iOS dat u wilt bijwerken.
3. Selecteer **Eigenschappen** en werk de gegevens voor de dagen met beperkingen bij.

## <a name="monitor-ios-devices-with-older-ios-versions"></a>iOS-apparaten met oudere iOS-versies bewaken 
<!-- 1352223 -->
Het rapport **Out-of-date iOS Devices** (Verouderde iOS-apparaten) is beschikbaar via de pagina **Software-updates** > **Updatebeleid voor iOS**. Het rapport bevat een lijst met gecontroleerde iOS-apparaten waarop een iOS-updatebeleid van toepassing is geweest en konden worden bijgewerkt. Voor elk apparaat kunt u bekijken waarom het apparaat niet automatisch is bijgewerkt.