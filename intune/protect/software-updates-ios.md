---
title: iOS/iPadOS-software-updatebeleid configureren in Microsoft Intune - Azure | Microsoft Docs
description: Maak configuratiebeleid in Microsoft Intune of voeg het toe om te beperken wanneer software-updates automatisch worden geïnstalleerd op iOS/iPadOS-apparaten. U kunt de datum en tijd kiezen wanneer updates niet worden geïnstalleerd. U kunt dit beleid ook toewijzen aan groepen, gebruikers of apparaten en controleren op eventuele fouten bij de installatie.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/20/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 77d4a90bb2eaa8434ff9c05362dcb0d7cb270651
ms.sourcegitcommit: 47c9af81c385c7e893fe5a85eb79cf08e69e6831
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/25/2020
ms.locfileid: "77576146"
---
# <a name="add-iosipados-software-update-policies-in-intune"></a>iOS/iPadOS-software-updatebeleid in Intune configureren

Dankzij beleid voor software-updates kunnen besturingssysteemupdates automatisch worden geïnstalleerd door iOS/iPadOS-apparaten die onder toezicht staan. Apparaten die onder toezicht staan, zijn apparaten die zijn ingeschreven met behulp van Apple Business Manager of Apple School Manager. Wanneer u een beleid configureert om updates te implementeren, kunt u:

- Ervoor kiezen om de *nieuwste update* die beschikbaar is te implementeren, of ervoor kiezen om een oudere update te implementeren op basis van het versienummer als u niet de nieuwste update wilt implementeren. Als u ervoor kiest om een oudere update te implementeren, moet u ook een apparaatconfiguratiebeleid instellen om de zichtbaarheid van software-updates te beperken.
- Een planning opgeven waarmee u bepaalt wanneer de update wordt geïnstalleerd. Planningen kunnen heel eenvoudig zijn zodat updates worden geïnstalleerd wanneer iemand het apparaat weer incheckt, maar kunnen ook worden gebruikt om datum- en tijdbereiken in te stellen wanneer updates wel of juist niet mogen worden geïnstalleerd.

Deze functie is van toepassing op:

- iOS 10.3 of hoger (onder supervisie)

Apparaten worden standaard ongeveer om de 8 uur bij Intune ingecheckt. Als er via een updatebeleid een update ter beschikking komt, wordt de update op het apparaat gedownload. Vervolgens wordt de update geïnstalleerd zodra het apparaat binnen de planningsconfiguratie wordt ingecheckt. Hoewel het updateproces doorgaans geen tussenkomst van de gebruiker omvat, moet de gebruiker een wachtwoordcode invoeren om een software-update te starten als het apparaat een wachtwoordcode heeft. Met profielen kan niet worden voorkomen dat gebruikers het besturingssysteem handmatig bijwerken. Met een apparaatconfiguratiebeleid waarmee de zichtbaarheid van software-updates wordt beperkt, kunt u voorkomen dat gebruikers het besturingssysteem handmatig bijwerken.

## <a name="configure-the-policy"></a>Het beleid configureren

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apparaten** > **Beleidsregels voor iOS/iPadOS bijwerken** > **Profiel maken**.
3. Geef op het tabblad **Basisinformatie** een naam en optioneel een beschrijving op en selecteer vervolgens **Volgende**.

   ![Tabblad Basisinformatie](./media/software-updates-ios/basics-tab.png)

4. Configureer het volgende op het tabblad **Beleidsinstellingen bijwerken**:

   1. **Versie selecteren die moet worden geïnstalleerd**. U kunt kiezen uit:

      - *Laatste update*: Hiermee implementeert u de meest recent uitgebrachte update voor iOS/iPadOS.
      - Elke eerdere versie die beschikbaar is in de vervolgkeuzelijst. Als u een eerdere versie selecteert, moet u ook een apparaatconfiguratiebeleid instellen om de zichtbaarheid van software-updates te vertragen.

   2. **Type planning**: De planning voor dit beleid configureren:

      - *Bijwerken wanneer de volgende keer wordt ingecheckt*: De update wordt op het apparaat geïnstalleerd zodra dit weer bij Intune wordt ingecheckt. Dit is de eenvoudigste optie, zonder extra configuraties.
      - *Bijwerken op gepland tijdstip*: U kunt een of meer tijdvensters configureren waarbinnen de update wordt geïnstalleerd zodra het apparaat weer wordt ingecheckt.
      - *Bijwerken buiten gepland tijdstip*: U kunt een of meer tijdvensters configureren waarbinnen geen updates worden geïnstalleerd zodra het apparaat weer wordt ingecheckt.

   3. **Wekelijkse planning**: als u een ander planningstype kiest dan *Bijwerken wanneer de volgende keer wordt ingecheckt*, moet u de volgende opties configureren:

      ![Voorbeeld van het selecteren van de optie om updates uit te voeren op het geplande tijdstip](./media/software-updates-ios/scheduled-time.png)

      - **Tijdzone**: Kies een tijdzone.
      - **Tijdvenster**: definieer een of meer tijdblokken om te beperken wanneer updates worden geïnstalleerd. Welk effect de volgende opties hebben, hangt af van het geselecteerde type planning. Wanneer u een start- en einddag gebruikt, worden blokken ondersteund die 's nachts plaatsvinden. Opties zijn onder andere:

        - **Startdag**: kies de dag waarop het planningvenster begint.
        - **Begintijd**: kies het tijdstip waarop het planningvenster begint. Als u bijvoorbeeld 5.00 uur selecteert bij het planningstype *Bijwerken op gepland tijdstip*, dan begint de installatie van updates om 5.00 uur. Als u het planningstype *Bijwerken buiten gepland tijdstip* kiest, is 5.00 uur het begin van een periode waarin updates niet kunnen worden geïnstalleerd.
        - **Einddag**: kies de dag waarop het planningvenster eindigt.
        - **Eindtijd**: kies het tijdstip waarop het planningvenster eindigt. Als u bijvoorbeeld 1.00 uur selecteert bij het planningstype *Bijwerken op gepland tijdstip*, dan is 1.00 uur het begin van een periode waarin updates niet meer worden geïnstalleerd. Als u het planningstype *Bijwerken buiten gepland tijdstip* kiest, is 1.00 uur het begin van een periode waarin updates kunnen worden geïnstalleerd.

       Als u geen begin- of eindtijden configureert, worden geen beperkingen toegepast en kunnen updates op elk gewenst moment worden geïnstalleerd.  

       > [!NOTE]
       > Als u de zichtbaarheid van software-updates voor een bepaald tijdvenster wilt uitstellen op de iOS/iPadOS-apparaten onder uw supervisie, moet u deze instellingen configureren in de [Apparaatbeperkingen](../configuration/device-restrictions-ios.md#general). Het beleid voor software-updates overschrijft eventuele apparaatbeperkingen. Wanneer u zowel beleid voor software-updates als een beperking om de zichtbaarheid van software-updates te vertragen instelt, wordt op het apparaat een software-update volgens het beleid afgedwongen. De beperking is van toepassing om te voorkomen dat gebruikers de optie zien om het apparaat zelf bij te werken. De update wordt gepusht zoals gedefinieerd in uw iOS/iPadOS-updatebeleid.

   Nadat u *Instellingen voor updatebeleid* hebt geconfigureerd, selecteert u **Volgende**.

5. Selecteer op het tabblad **Bereiktags** de optie **Bereiktags selecteren** om het deelvenster *Tags selecteren* te openen als u deze wilt toepassing op het updatebeleid.

   - Kies in het deelvenster **Tags selecteren** een of meer tags en klik vervolgens op **Selecteren** om deze toe te voegen aan het beleid en terug te keren naar het deelvenster *Bereiktags*.

   Wanneer u klaar bent, selecteert u **Volgende** om naar *Toewijzingen* te gaan.

6. Kies op het tabblad **Toewijzingen** de optie **Groepen selecteren die moeten worden opgenomen** en wijs het updatebeleid toe aan een of meer groepen. Gebruik **+ Groepen selecteren die moeten worden uitgesloten** om de toewijzing te verfijnen. Wanneer u klaar bent, selecteert u **Volgende** om verder te gaan.

   De apparaten die worden gebruikt door de gebruikers op wie het beleid wordt toegepast, worden gecontroleerd om te zien of ze voldoen aan de updatenaleving. Dit beleid ondersteunt ook apparaten zonder gebruikers.

7. Controleer de instellingen op het tabblad **Beoordelen en maken** en selecteer vervolgens **Maken** als u klaar bent om uw iOS/iPadOS-updatebeleid op te slaan. Het nieuwe beleid wordt weergegeven in de lijst met updatebeleidsregels voor iOS/iPadOS.

Zie [Zichtbaarheid van software-updates in Intune vertragen voor apparaten die onder toezicht staan](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Delaying-visibility-of-software-updates-in-Intune-for-supervised/ba-p/345753) voor hulp van het Intune-ondersteuningsteam.

> [!NOTE]
> Apple MDM staat u niet toe om een apparaat te dwingen om vóór een bepaald tijdstip of een bepaalde datum updates te installeren. U kunt geen software-updatebeleid van Intune gebruiken om de besturingssysteemversie op een apparaat te downgraden.

## <a name="edit-a-policy"></a>Een beleidsregel bewerken

U kunt een bestaande beleidsregel bewerken, waaronder de beperkte tijden:

1. Selecteer **Apparaten** > **Beleidsregels voor iOS bijwerken**. Selecteer het beleid dat u wilt bewerken.

2. Selecteer bij het weergeven van de **Eigenschappen** van beleidsregels de optie **Bewerken** voor de beleidspagina die u wilt wijzigen.

   ![Een beleidsregel bewerken](./media/software-updates-ios/edit-policy.png)

3. Nadat u een wijziging hebt aangebracht, selecteert u **Beoordelen en opslaan** > **Opslaan** om uw wijzigingen op te slaan en gaat u terug naar de *Eigenschappen* van beleidsregels.

> [!NOTE]
> Als de **Begintijd** en de **Eindtijd** allebei op 12:00 uur zijn ingesteld, wordt er in Intune niet gecontroleerd of er tijdbeperkingen gelden voor het installeren van updates. Dit betekent dat al uw configuraties voor **Tijden selecteren om de installatie van updates te voorkomen** worden genegeerd en dat updates op elk moment kunnen worden geïnstalleerd.

## <a name="monitor-device-installation-failures"></a>Installatiefouten op apparaten controleren

<!-- 1352223 -->
In **Software-updates** > **Installatiefouten op iOS/iPadOS-apparaten** wordt een lijst opgegeven met gecontroleerde iOS/iPadOS-apparaten waarop een updatebeleid was gericht, waarvoor is geprobeerd een update uit te voeren, maar dit niet mogelijk was. Voor elk apparaat kunt u bekijken waarom het apparaat niet automatisch is bijgewerkt. Bijgewerkte apparaten die in orde zijn, worden niet weergegeven in de lijst. Een apparaat is bijgewerkt als de meest recente update is geïnstalleerd die door het apparaat zelf wordt ondersteund.

## <a name="next-steps"></a>Volgende stappen

[Controleer de status ervan.](../configuration/device-profile-monitor.md)
