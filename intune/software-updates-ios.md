---
title: iOS-software-updatebeleid configureren in Microsoft Intune
titlesuffix: ''
description: Configureer updatebeleid voor iOS zodat de nieuwste software-update automatisch wordt geïnstalleerd door iOS-apparaten die onder supervisie staan.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.openlocfilehash: 1d4223ae4feb417f77909b320cd0295347b44461
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="configure-ios-update-policies-in-microsoft-intune"></a>iOS-updatebeleid configureren in Microsoft Intune

Dankzij het software-updatebeleid kan de nieuwste software-update voor het besturingssysteem automatisch worden geïnstalleerd op iOS-apparaten met iOS 10.3 en hoger die onder supervisie staan. Deze functie is alleen beschikbaar voor apparaten die onder supervisie staan. U kunt dagen en tijdstippen instellen waarop u niet wilt dat de update wordt geïnstalleerd. 

Als er een update beschikbaar is wanneer het apparaat wordt ingecheckt (ongeveer elke acht uur) en er verder geen beperkingen gelden voor het tijdstip, wordt de nieuwste update van het besturingssysteem gedownload. Er is geen tussenkomst van de gebruiker nodig om het apparaat bij te werken. Gebruikers kunnen het besturingssysteem ook nog steeds zelf bijwerken.

## <a name="configure-the-ios-update-policy"></a>Updatebeleid voor iOS configureren
1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. In het deelvenster **Intune** kiest u **Software-updates** > **Updatebeleid voor iOS**.
4. Kies in het deelvenster voor beleid de optie **Maken** en voer een naam en beschrijving in voor het beleid.
5. Selecteer **Instellingen** > **Configureren** en voer de details in voor het geval waarbij iOS-apparaten niet worden gedwongen de meest recente update te installeren. U kunt de dagen van de week, de tijdzone, de begintijd en de eindtijd configureren.
6. Kies **OK** om deze configuratie op te slaan. U bent nu terug in het deelvenster **Updatebeleid maken**. Kies **Maken** om het beleid te maken en uw instellingen op te slaan.

Het profiel wordt gemaakt en wordt weergegeven in het deelvenster met de lijst met updatebeleidsregels voor iOS. In Apple MDM kan niet worden afgedwongen dat de update op een bepaald tijdstip of een bepaalde datum op het apparaat wordt geïnstalleerd. 

## <a name="change-the-restricted-times-for-the-policy"></a>De tijdstippen met beperkingen voor het beleid wijzigen

1.  Kies op de blade **Software-updates** de optie **Updatebeleid voor iOS**.
2.  Selecteer het updatebeleid voor iOS dat u wilt bijwerken.
3.  Selecteer **Eigenschappen** en werk de gegevens voor de tijdstippen met beperkingen bij.
4.  De dagen van de week kiezen
5.  De tijdzone waarin dit beleid wordt toegepast
6.  De begin- en eindtijd voor niet-toegestane uren

## <a name="assign-an-ios-update-policy-to-users"></a>Updatebeleid voor iOS aan gebruikers toewijzen

Als u een updatebeleid voor iOS aan gebruikers wilt toewijzen, kiest u een beleid dat u hebt geconfigureerd. U kunt de bestaande beleidsregels vinden in het deelvenster **Software-updates** > **Updatebeleid voor iOS**.

1. Kies het beleid dat u aan gebruikers wilt toewijzen en kies **Toewijzingen**. Hiermee opent u het deelvenster waar u Azure Active Directory-beveiligingsgroepen kunt selecteren en aan het beleid kunt toewijzen.
2. Kies **Geselecteerde groepen** om het deelvenster met de Azure AD-beveiligingsgroepen te openen. Bepaal wie toegang heeft tot het beleid door de groepen die moeten worden opgenomen en uitgesloten toe te wijzen.
3. Kies **Opslaan** om het beleid voor gebruikers te implementeren.

U hebt het beleid toegepast op uw gebruikers of apparaten. De apparaten die worden gebruikt door de gebruikers op wie het beleid is toegepast, worden gecontroleerd om te zien of ze voldoen aan de updatenaleving. Dit beleid ondersteunt ook apparaten zonder gebruikers.

## <a name="monitor-ios-device-installation-failures"></a>Installatiefouten voor iOS-apparaten controleren
<!-- 1352223 -->
Het rapport **Installation Failures for iOS Devices** (Installatiefouten voor iOS-apparaten) is beschikbaar in het deelvenster **Software-updates**. Het rapport bevat een lijst met de iOS-apparaten onder supervisie waarop een iOS-updatebeleid van toepassing is geweest, waarvoor is geprobeerd een update uit te voeren en die niet konden worden bijgewerkt. Voor elk apparaat kunt u bekijken waarom het apparaat niet automatisch is bijgewerkt. Bijgewerkte apparaten die in orde zijn, worden niet weergegeven in de lijst. Een apparaat is bijgewerkt als de nieuwste update die wordt ondersteund, is geïnstalleerd.

