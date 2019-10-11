---
title: iOS-software-updatebeleid configureren in Microsoft Intune - Azure | Microsoft Docs
description: Maak of voeg in Microsoft Intune configuratiebeleid toe om beperkingen in te stellen wanneer software-updates automatisch worden geïnstalleerd op iOS-apparaten die door Intune worden beheerd of onder supervisie staan van Intune. U kunt de datum en tijd kiezen wanneer updates niet worden geïnstalleerd. U kunt dit beleid ook toewijzen aan groepen, gebruikers of apparaten en controleren op eventuele fouten bij de installatie.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 54e6cc0b3df95c74abf4b4ef1b827f8e121e3645
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71726658"
---
# <a name="add-ios-software-update-policies-in-intune"></a>iOS-software-updatebeleid in Intune configureren

Dankzij beleid voor software-updates kan de nieuwste iOS-update automatisch worden geïnstalleerd door iOS-apparaten die onder supervisie staan. Wanneer u een beleid configureert, kunt u de dagen en tijden toevoegen wanneer u niet wilt dat apparaten updates installeren.

Deze functie is van toepassing op:

- iOS 10.3 of hoger (onder supervisie)

Het apparaat wordt ongeveer om de 8 uur bij Intune ingecheckt. Als een update beschikbaar is en het betreft geen beperkte periode, wordt de meest recente update van het besturingssysteem naar het apparaat gedownload en erop geïnstalleerd. Er is geen tussenkomst van de gebruiker nodig om het apparaat bij te werken. Het beleid belet gebruikers niet om het besturingssysteem handmatig bij te werken.

## <a name="configure-the-policy"></a>Het beleid configureren

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **Software-updates** > **Beleidsregels voor iOS bijwerken** > **Maken**.
3. Voer de volgende instellingen in:

    - **Naam**: Voer een naam in voor uw software-updatebeleid. Voer bijvoorbeeld `iOS restricted update times` in.
    - **Beschrijving**: Voer een beschrijving in voor uw beleid. Deze instelling is optioneel, maar wordt aanbevolen.

4. Selecteer **Instellingen > Configureren**. Voer de volgende instellingen in:

    - **Tijden selecteren om de installatie van updates te voorkomen**: Geef een beperkt tijdsbestek op waarin updates niet geforceerd worden geïnstalleerd.
      - Blokkering voor 's nachts wordt niet ondersteund en werkt mogelijk niet. Configureer bijvoorbeeld geen beleid met 20:00 uur als *begintijd* en 6:00 uur als *eindtijd*.
      - Een beleid dat om 12:00 uur begint en eindigt om 12:00 uur, wordt als 0 uur beschouwd en niet als 24 uur, waardoor er dus geen beperking wordt ingesteld.

      Wanneer u het beperkte tijdsbestek instelt, voert u de volgende gegevens in:

      - **Dagen**: Kies de dag(en) van de week waarop updates niet worden geïnstalleerd. Schakel bijvoorbeeld maandag, woensdag en vrijdag in om te voorkomen dat updates op deze dagen worden geïnstalleerd.
      - **Tijdzone**: Kies een tijdzone.
      - **Begintijd**: Kies de begintijd van het beperkte tijdsbestek. Voer bijvoorbeeld 5:00 uur in, zodat updates vanaf 5:00 uur niet worden geïnstalleerd.
      - **Eindtijd**: Kies de eindtijd van het beperkte tijdsbestek. Voer bijvoorbeeld 1:00 uur in, zodat updates vanaf 1:00 kunnen worden geïnstalleerd.

    - **Zichtbaarheid van software-updates voor eindgebruikers vertragen zonder de geplande updates in het beleid voor software-updates te wijzigen (dagen)** : 

      **Als u de zichtbaarheid van software-updates voor een bepaalde tijd wilt uitstellen op de iOS-apparaten onder uw supervisie, moet u deze instellingen configureren in de [Apparaatbeperkingen](../configuration/device-restrictions-ios.md#general). Het beleid voor software-updates overschrijft eventuele apparaatbeperkingen. Als u beide hebt ingesteld, heeft het beleid voor software-updates altijd prioriteit.

      > [!IMPORTANT]  
      > Een beleid waarvan de *begintijd* en *eindtijd* allebei op 12:00 uur zijn ingesteld, wordt als 0 uur beschouwd en niet als 24 uur. Dit leidt tot geen beperkingen.  

5. Selecteer **OK** > **Maken** om wijzigingen op te slaan en het beleid te maken.

Het profiel wordt gemaakt en wordt weergegeven in de lijst met beleidsregels.

Zie [Zichtbaarheid van software-updates in Intune vertragen voor apparaten die onder toezicht staan](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Delaying-visibility-of-software-updates-in-Intune-for-supervised/ba-p/345753) voor hulp van het Intune-ondersteuningsteam.

> [!NOTE]
> Apple MDM staat u niet toe om een apparaat te dwingen om vóór een bepaald tijdstip of een bepaalde datum updates te installeren.

## <a name="change-the-restricted-times-for-the-policy"></a>De tijdstippen met beperkingen voor het beleid wijzigen

1. Selecteer in **Software-updates** **Beleidsregels voor iOS bijwerken**.
2. Kies een bestaand beleid > **Eigenschappen**.
3. De tijd met beperkingen bijwerken:

    1. De dagen van de week kiezen
    2. De tijdzone kiezen waarin dit beleid wordt toegepast
    3. De begin- en eindtijd opgeven voor niet-toegestane uren

    > [!NOTE]
    > Als de **begintijd** en de **eindtijd** allebei op 12:00 uur zijn ingesteld, controleert Intune niet of er beperkingen gelden voor de installatie van updates. Dit betekent dat al uw configuraties voor **Tijden selecteren om de installatie van updates te voorkomen** worden genegeerd en dat updates op elk moment kunnen worden geïnstalleerd.  

## <a name="assign-the-policy-to-users"></a>Het beleid toewijzen aan gebruikers

Bestaande beleidsregels worden toegewezen aan groepen, gebruikers of apparaten. Wanneer toegewezen, wordt het beleid toegepast.

1. Selecteer in **Software-updates** **Beleidsregels voor iOS bijwerken**.
2. Kies een bestaand beleid > **Toewijzingen**.
3. Selecteer de Azure Active Directory-groepen, -gebruikers of -apparaten die u wilt opnemen of uitsluiten van dit beleid.
4. Kies **Opslaan** om het beleid voor uw groepen te implementeren.

De apparaten die worden gebruikt door de gebruikers op wie het beleid wordt toegepast, worden gecontroleerd om te zien of ze voldoen aan de updatenaleving. Dit beleid ondersteunt ook apparaten zonder gebruikers.

## <a name="monitor-device-installation-failures"></a>Installatiefouten op apparaten controleren
<!-- 1352223 -->
In **Software-updates** > **Installatiefouten op iOS-apparaten** wordt een lijst opgegeven met gecontroleerde iOS-apparaten waarop een updatebeleid was gericht, waarvoor is geprobeerd een update uit te voeren, maar dit niet mogelijk was. Voor elk apparaat kunt u bekijken waarom het apparaat niet automatisch is bijgewerkt. Bijgewerkte apparaten die in orde zijn, worden niet weergegeven in de lijst. Een apparaat is bijgewerkt als de meest recente update is geïnstalleerd die door het apparaat zelf wordt ondersteund.

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](../configuration/device-profile-assign.md) en [de status ervan controleren](../configuration/device-profile-monitor.md).
