---
title: Intune-onderwijsinstellingen configureren voor Windows 10
titleSuffix: Azure portal
description: Meer informatie over het gebruik van Intune om Windows 10 Education-instellingen te configureren op apparaten die u beheert.
keywords: 
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 02/23/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 18987c65c7ad0443c8bf3dc268284306cf64080d
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/08/2018
---
# <a name="how-to-configure-windows-10-education-settings-in-microsoft-intune"></a>Windows 10 Education-instellingen configureren in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Met opleidingsprofielen kunt u gegevens opgeven waarmee de Windows Toets maken-app wordt geconfigureerd, zoals de accountgegevens en de URL voor de toets. Wanneer u de Toets maken-app hebt geconfigureerd, wordt deze geopend met de toets die u hebt opgegeven en kunnen er geen andere apps op het apparaat worden uitgevoerd totdat de toets is voltooid.

Zie [Toetsen maken in Windows 10](https://docs.microsoft.com/education/windows/take-tests-in-windows-10) voor meer informatie over de Toets maken-app.

## <a name="create-a-device-profile-containing-education-profile-settings"></a>Een apparaatprofiel maken dat de opleidingsprofielinstellingen bevat

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies in het deelvenster **Intune** de optie **Apparaatconfiguratie**.
2. Kies in het deelvenster **Apparaatconfiguratie** onder de sectie **Beheren** de optie **Profielen**.
3. Kies **Profiel maken** in het deelvenster Profielen.
4. Voer in het deelvenster **Profiel maken** een **naam** en **beschrijving** in voor het apparaatbeperkingsprofiel.
5. Selecteer in de vervolgkeuzelijst **Platform** de optie **Windows 10 en hoger**.
6. Kies **Opleidingsprofiel** in de vervolgkeuzelijst **Profieltype**. 
7. Kies **Instellingen > Configureren** en configureer vervolgens in het deelvenster **Toets maken** het volgende:
    - **Accounttype**: selecteer een accounttype in de vervolgkeuzelijst.
    - **Gebruikersnaam voor het account**: voer de gebruikersnaam in voor het account dat wordt gebruikt voor Toets maken. Dit kan een domeinaccount, een AAD-account (Azure Active Directory) of een lokaal account op een computer zijn.
    - **URL van de toets**: geef de URL op van de toets die de gebruikers moeten afleggen. Zie de documentatie van Toets maken voor meer informatie.
    - **Schermcontrole**: geef op of u de schermactiviteiten wilt kunnen controleren terwijl de gebruikers een toets afleggen.
    - **Tekstsuggestie**: tekstsuggesties toestaan of blokkeren terwijl de gebruikers een toets afleggen.
8. Als u klaar bent, gaat u terug naar het deelvenster **Profiel maken** en kiest u **Maken**.

Het profiel wordt gemaakt en wordt weergegeven in het deelvenster met de profielenlijst.

## <a name="next-steps"></a>Volgende stappen

Zie [How to assign device profiles](device-profile-assign.md) (Apparaatprofielen toewijzen) als u wilt doorgaan en dit profiel wilt toewijzen aan groepen.



