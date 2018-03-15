---
title: Apparaten synchroniseren met Intune
titlesuffix: Azure portal
description: Lees hier hoe u apparaten met Intune kunt synchroniseren om het meest recente beleid en de meest recente acties te verkrijgen.
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7d48b81e6df912815d9ef843b4588f8c1076a8a7
ms.sourcegitcommit: eac89306d1391a6d3ae1179612b0820b19c2baa6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/23/2018
---
# <a name="sync-devices-with-intune-to-get-the-latest-policies-and-actions"></a>Apparaten synchroniseren met Intune om het meest recente beleid en de meest recente acties te verkrijgen


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Met apparaatactie **Synchroniseren** wordt het geselecteerde apparaat direct ingecheckt bij Intune. Wanneer een apparaat wordt ingecheckt, worden direct eventuele openstaande acties of toegewezen beleidsregels ontvangen die erop zijn toegepast.  Met deze actie kunt u toegewezen beleid meteen controleren en in het geval van problemen direct aanpassen, zonder dat u hoeft te wachten op de volgende geplande check-in.

## <a name="supported-platforms"></a>Ondersteunde platforms

- Windows
- Windows Phone
- iOS
- macOS
- Android

## <a name="how-to-sync-a-device"></a>Apparaten synchroniseren

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies **Apparaten** op de blade **Intune**.
4. Kies **Alle apparaten** op de blade **Apparaten**.
5. Kies een apparaat in de lijst met apparaten die u beheert en kies vervolgens **...Meer**. Selecteer vervolgens de externe actie **Synchroniseren**.
7. Kies **Ja** om de actie te bevestigen.


## <a name="retriable-error-codes"></a>Codes van fouten waarvoor een nieuwe poging kan worden gedaan

Wanneer een beheerder de apparaatactie **Synchroniseren** uitvoert, zijn iOS- en Android-apps waarbij de actie is mislukt maar die een foutcode genereerden die aangeeft dat een nieuwe poging kan worden gedaan, beschikbaar voor het apparaat. Apps die een foutcode genereerden die aangaf dat er geen nieuwe poging kan worden gedaan, kunnen pas na zeven dagen weer beschikbaar kunnen worden gemaakt voor het apparaat.


| Foutcode  | Voorgestelde beschrijving                                                                                                                  | Nieuwe poging mogelijk |
|-------------|----------------------------------------------------------------------------------------------------------------------------------------|-----------|
| 2016330898 | Er is een onbekende fout opgetreden.                                                                                                             | Nee        |
| 2016330897 | Er is een time-out opgetreden voor de verbinding met Intune. Stel de verbinding opnieuw in                                                                             | Ja       |
| 2016330896 | De verbinding met internet is verbroken. Stel de verbinding opnieuw in.                                                                            | Ja       |
| 2016330895 | De verbinding met internet is verbroken. Stel de verbinding opnieuw in.                                                                            | Ja       |
| 2016330894 | De verbinding met internet is verbroken. Stel de verbinding opnieuw in.                                                                            | Ja       |
| 2016330893 | De verbinding met internet is verbroken. Stel de verbinding opnieuw in.                                                                            | Ja       |
| 2016330892 | Internationale roaming is uitgeschakeld.                                                                                                     | Nee        |
| 2016330891 | De mobiele gegevensverbinding vor dit apparaat kan niet worden gebruikt terwijl er wordt gebeld. Wacht tot het gesprek is beëindigd. | Ja       |
| 2016330890 | Het mobiele netwerk voor dit apparaat. Deze apparaten kunnen momenteel niet worden gebruikt.                                                   | Nee        |
| 2016330889 | De beveiligde verbinding is mislukt. Stel de verbinding opnieuw in.                                                                                   | Ja       |
| 2016330888 | De evaluatie van de vertrouwelijke server is mislukt.                                                                                                | Nee        |

## <a name="next-steps"></a>Volgende stappen

Kies **Apparaatacties** om de status van de synchronisatieactie te zien. 
