---
title: Extern beheer van apparaten in Microsoft Intune - Azure | Microsoft Docs
description: De vereiste rollen bekijken om TeamViewer te gebruiken, hoe u de TeamViewer-connector installeert en stapsgewijze instructies voor het extern beheren van apparaten met Microsoft Intune in de Azure Portal
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 60d9398b80a30adee194470ac4e5c6c1efc0bd4c
ms.sourcegitcommit: 97b9f966f23895495b4c8a685f1397b78cc01d57
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34744632"
---
# <a name="use-teamviewer-to-remotely-administer-intune-devices"></a>TeamViewer gebruiken voor het extern beheren van Intune-apparaten

Apparaten die worden beheerd door Intune kunnen extern worden beheerd met [TeamViewer](https://www.teamviewer.com). TeamViewer is een programma van derden dat u afzonderlijk aanschaft. In dit onderwerp leest u hoe u TeamViewer binnen Intune configureert en hoe u een apparaat extern beheert. 

## <a name="prerequisites"></a>Vereisten

- Gebruik een ondersteund apparaat. Door Intune beheerde Android-, Windows-, iOS- en macOS-apparaten ondersteunen extern beheer. TeamViewer biedt mogelijk geen ondersteuning voor Windows Holographic (HoloLens), Windows Team (Surface Hub) of Windows 10 S. Zie voor ondersteuning [TeamViewer](https://www.teamviewer.com) voor eventuele updates.

- De Intune-beheerder binnen de Azure Portal moet de volgende [Intune-rollen](role-based-access-control.md) hebben:  

    - **Hulp op afstand bijwerken**: hiermee kunnen beheerders de instellingen van de TeamViewer-connector wijzigen
    - **Hulp op afstand vragen**: hiermee kunnen beheerders een nieuwe sessie van hulp op afstand voor elke gebruiker starten. Gebruikers met deze rol zijn niet beperkt door een Intune-rol binnen een bereik. Gebruikers- of apparaatgroepen aan wie een Intune-rol is toegewezen binnen een scope, kunnen ook hulp op afstand aanvragen. 

- Een [TeamViewer](https://www.teamviewer.com)-account met de aanmeldingsreferenties

Door TeamViewer te gebruiken, kunt u met de TeamViewer voor Intune-connector TeamViewer-sessies maken, Active Directory-gegevens lezen en het toegangstoken voor het TeamViewer-account opslaan.

## <a name="configure-the-teamviewer-connector"></a>De TeamViewer-connector configureren

Als u hulp op afstand voor apparaten wilt bieden, configureert u de Intune TeamViewer-connector door de volgende stappen uit te voeren:

1. In de [Azure-portal](https://portal.azure.com) selecteert u **Alle services** en zoekt u naar **Microsoft Intune**.
2. In **Microsoft Intune** selecteert u **Apparaten** en selecteert u vervolgens **TeamViewer-connector**.
3. Selecteer **Verbinding maken** en accepteer de gebruiksrechtovereenkomst.
4. Selecteer **Aanmelden bij TeamViewer voor goedkeuring**.
5. Er wordt een webpagina van de TeamViewer-site geopend. Voer de referenties van uw TeamViewer-licentie in en klik vervolgens op **Aanmelden**.

## <a name="remotely-administer-a-device"></a>Een apparaat op afstand beheren

Nadat de connector is geconfigureerd, kunt u een apparaat op afstand beheren. Voer de volgende stappen uit: 

1. In de [Azure-portal](https://portal.azure.com) selecteert u **Alle services** en zoekt u naar **Microsoft Intune**.
2. In **Microsoft Intune** selecteert u **Apparaten** en selecteert u vervolgens **Alle apparaten**.
3. Selecteer in de lijst het apparaat dat u extern wilt beheren. Selecteer in de apparaateigenschappen **Nieuwe sessie van hulp op afstand**.
4. Nadat er een verbinding tussen Intune en de TeamViewer-service tot stand is gebracht, worden er enkele gegevens over het apparaat weergegeven. Kies **Verbinden** om de externe sessie te starten.

![TeamViewer gebruiken om een Android-apparaat extern te beheren - voorbeeld](./media/android-teamviewer.png)

Wanneer u een externe sessie start, wordt er een vlag voor meldingen op het pictogram van de bedrijfsportal-app op het apparaat van de eindgebruiker weergegeven. Er wordt ook een melding weergegeven wanneer de app wordt geopend. De gebruiker kan vervolgens het verzoek om hulp op afstand accepteren.

In TeamViewer kunt u een reeks acties op het apparaat uitvoeren, zoals het overnemen van het beheer van het apparaat. Zie de [TeamViewer-richtlijnen](https://www.teamviewer.com/support/documents/) voor meer informatie over wat u kunt doen.

Als u klaar bent, sluit u het TeamViewer-venster.