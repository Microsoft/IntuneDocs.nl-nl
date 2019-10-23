---
title: Extern beheer van apparaten in Microsoft Intune - Azure | Microsoft Docs
description: De vereiste rollen bekijken om TeamViewer te gebruiken, hoe u de TeamViewer-connector installeert en stapsgewijze instructies voor het extern beheren van apparaten met Microsoft Intune in de Azure Portal
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/05/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ac9d22ff4b203a4e7a85121df6c021eec1bcd1e3
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72508537"
---
# <a name="use-teamviewer-to-remotely-administer-intune-devices"></a>TeamViewer gebruiken voor het extern beheren van Intune-apparaten

Apparaten die worden beheerd door Intune kunnen extern worden beheerd met [TeamViewer](https://www.teamviewer.com). TeamViewer is een programma van derden dat u afzonderlijk aanschaft. In dit onderwerp leest u hoe u TeamViewer binnen Intune configureert en hoe u een apparaat extern beheert. 

## <a name="prerequisites"></a>Vereisten

- Gebruik een ondersteund apparaat. Door Intune beheerd Android-apparaatbeheer, Android-werkprofiel, en Windows-, iOS- en macOS-apparaten ondersteunen extern beheer. TeamViewer biedt mogelijk geen ondersteuning voor Windows Holographic (HoloLens), Windows Team (Surface Hub) of Windows 10 S. Zie voor ondersteuning [TeamViewer](https://www.teamviewer.com) voor eventuele updates.

> [!NOTE]
> Android Dedicated en Volledig beheerd worden niet ondersteund.

- De Intune-beheerder binnen de Azure Portal moet de volgende [Intune-rollen](../fundamentals/role-based-access-control.md) hebben:  

  - **Hulp op afstand bijwerken**: hiermee kunnen beheerders de instellingen van de TeamViewer-connector wijzigen
  - **Hulp op afstand aanvragen**: hiermee kunnen beheerders een nieuwe sessie van hulp op afstand voor elke gebruiker starten. Gebruikers met deze rol zijn niet beperkt door een Intune-rol binnen een bereik. Gebruikers- of apparaatgroepen aan wie een Intune-rol is toegewezen binnen een scope, kunnen ook hulp op afstand aanvragen. 

- Een [TeamViewer](https://www.teamviewer.com)-account met de aanmeldingsreferenties. Alleen bepaalde TeamViewer-licenties bieden mogelijk ondersteuning voor integratie met Intune. Zie voor specifieke TeamViewer-behoeften [TeamViewer-integratiepartner: Microsoft Intune](https://www.teamviewer.com/integrations/microsoft-intune/).

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

![TeamViewer gebruiken om een Android-apparaat extern te beheren - voorbeeld](./media/teamviewer-support/android-teamviewer.png)

Wanneer u een externe sessie start, wordt er een vlag voor meldingen op het pictogram van de bedrijfsportal-app op het apparaat van de gebruiker weergegeven. Er wordt ook een melding weergegeven wanneer de app wordt geopend. Gebruikers kunnen het verzoek om hulp op afstand dan accepteren.

> [!NOTE]
> Voor Windows-apparaten die zijn ingeschreven met behulp van methoden zonder tussenkomst van gebruikers, zoals DEM en WCD, wordt de TeamViewer-melding niet in de bedrijfsportal-app weergegeven. In deze scenario's is het raadzaam de sessie te genereren via de TeamViewer-portal.

In TeamViewer kunt u een reeks acties op het apparaat uitvoeren, zoals het overnemen van het beheer van het apparaat. Zie de [TeamViewer-richtlijnen](https://www.teamviewer.com/support/documents/) voor meer informatie over wat u kunt doen.

Als u klaar bent, sluit u het TeamViewer-venster.
