---
title: Apparaten synchroniseren met Microsoft Intune - Azure | Microsoft Docs
description: Synchroniseer apparaten die zijn geregistreerd bij of worden beheerd met Microsoft Intune om het meest recente beleid en de meest recente acties te verkrijgen. Bevat de stappen voor synchronisatie via Azure Portal en bevat de codes van fouten waarvoor opnieuw een poging kan worden gedaan.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 173d3e4729b3d620167180fb17fcee6c618604eb
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71728413"
---
# <a name="sync-devices-to-get-the-latest-policies-and-actions-with-intune"></a>Apparaten synchroniseren met Intune om het meest recente beleid en de meest recente acties te verkrijgen


Met apparaatactie **Synchroniseren** wordt het geselecteerde apparaat direct ingecheckt bij Intune. Wanneer een apparaat wordt ingecheckt, worden direct eventuele openstaande acties of toegewezen beleidsregels ontvangen die erop zijn toegepast. Met deze functie kunt u toegewezen beleid meteen controleren en in het geval van problemen direct aanpassen, zonder dat u hoeft te wachten op de volgende geplande check-in.

## <a name="supported-platforms"></a>Ondersteunde platforms

- Windows
- Windows Phone
- iOS
- macOS
- Android

## <a name="sync-a-device"></a>Een apparaat synchroniseren

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973). 
3. Selecteer **Apparaten** > **Alle apparaten** in **Intune**.
4. Selecteer een apparaat in de lijst met apparaten die u beheert, selecteer een apparaat om het venster *Overzicht* te openen en selecteer vervolgens **Synchroniseren**.
5. Selecteer **Ja** om de opdracht te bevestigen.

Kies **Apparaten** > **Apparaatacties** om de status van de synchronisatieactie te zien.

U vindt standaardfrequenties voor check-ins van Intune-beleid in [Cyclusduur vernieuwen](../configuration/device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).

## <a name="retryable-error-codes"></a>Codes van fouten waarvoor een nieuwe poging kan worden gedaan

Wanneer een beheerder de apparaatactie **Synchroniseren** uitvoert, zijn iOS- en Android-apps waarbij de actie is mislukt, maar waarbij een foutcode is gegenereerd waarin is aangegeven dat een nieuwe poging kan worden gedaan, nog altijd beschikbaar voor het apparaat. Apps waarbij een foutcode is gegenereerd waarin is aangegeven dat er geen nieuwe poging kan worden gedaan, kunnen pas na zeven dagen weer beschikbaar worden gemaakt voor het apparaat.


| Foutcode  | Voorgestelde beschrijving | Er kan een nieuwe poging worden gedaan |
|---|---|---|
| 2016330898 | Er is een onbekende fout opgetreden. | Nee |
| 2016330897 | Er is een time-out opgetreden voor de verbinding met Intune. Stel de verbinding opnieuw in. | Ja |
| 2016330896 | De verbinding met internet is verbroken. Stel de verbinding opnieuw in. | Ja |
| 2016330895 | De verbinding met internet is verbroken. Stel de verbinding opnieuw in. | Ja |
| 2016330894 | De verbinding met internet is verbroken. Stel de verbinding opnieuw in. | Ja |
| 2016330893 | De verbinding met internet is verbroken. Stel de verbinding opnieuw in. | Ja|
| 2016330892 | Internationale roaming is uitgeschakeld. | Nee|
| 2016330891 | De mobiele gegevensverbinding voor dit apparaat kan niet worden gebruikt terwijl er wordt gebeld. Wacht tot het gesprek is beëindigd. | Ja|
| 2016330890 | Het mobiele netwerk voor dit apparaat. Deze apparaten kunnen momenteel niet worden gebruikt. | Nee|
| 2016330889 | De beveiligde verbinding is mislukt. Stel de verbinding opnieuw in. | Ja|
| 2016330888 | De evaluatie van de vertrouwelijke server is mislukt. | Nee|

## <a name="next-steps"></a>Volgende stappen

U kunt de details van het apparaat [controleren](device-inventory.md).
 
