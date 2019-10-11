---
title: Education-instellingen toevoegen of configureren in Microsoft Intune - Azure | Microsoft Docs
description: Gebruik de app Take a test in een apparaatconfiguratieprofiel op apparaten met Windows 10 en hoger in Microsoft Intune. Maak een configuratieprofiel met behulp van de Education-instellingen, voer een test-app-URL in, kies hoe gebruikers zich aanmelden, bewaak het scherm tijdens de test en sta tekstsuggesties al dan niet toe tijdens de test.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/10/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3fc42193b461b8a0364e4ef2a2c34fe3e446ada3
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71724006"
---
# <a name="use-the-take-a-test-app-on-windows-10-devices-in-microsoft-intune"></a>Gebruik de app Take a test op Windows 10-apparaten in Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Education-profielen in Intune zijn bedoeld voor studenten die een test of examen op apparaten afleggen. Deze functie omvat de app **Take a test** en instellingen om een test-URL toe te voegen, te bepalen hoe eindgebruikers zich voor de test aanmelden en meer. Deze functie ondersteunt het volgende platform:

- Windows 10 en hoger

Wanneer de gebruiker zich aanmeldt, wordt de app Take a test automatisch geopend met de test die u hebt ingevoerd. Er kunnen geen andere apps op het apparaat worden uitgevoerd als de test bezig is. Meer informatie over de app Take a test vindt u in [Take tests in Windows 10](https://docs.microsoft.com/education/windows/take-tests-in-windows-10) (Testen afleggen in Windows 10).

Dit artikel vermeldt de stappen voor het maken van een configuratieprofiel voor een apparaat in Microsoft Intune. Het artikel bevat tevens informatie over de beschikbare education-instellingen voor uw Windows 10-apparaten.

## <a name="create-a-device-profile"></a>Een apparaatprofiel maken

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Voer de volgende eigenschappen in:

    - **Naam**: Voer een beschrijvende naam in voor het nieuwe profiel.
    - **Beschrijving**: Voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
    - **Platform**: Kies **Windows 10 en hoger**.
    - **Profiel**: Kies **Education-profiel**.

4. Voer de instellingen in die u wilt configureren:

    - [Windows 10 en hoger](education-settings-windows.md)

5. Selecteer **OK** > **Maken** om uw wijzigingen op te slaan.

Nadat u uw instellingen hebt ingevoerd en het profiel maakt, wordt uw profiel weergegeven in de lijst met profielen. Vervolgens [wijst u dit profiel toe aan enkele groepen](device-profile-assign.md).

## <a name="next-steps"></a>Volgende stappen

Bekijk een overzicht van de [Windows 10 Education-instellingen](education-settings-windows.md) en de bijbehorende beschrijvingen.

[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).
