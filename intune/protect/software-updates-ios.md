---
title: iOS-software-updatebeleid configureren in Microsoft Intune - Azure | Microsoft Docs
description: Maak configuratiebeleid in Microsoft Intune of voeg het toe om te beperken wanneer software-updates automatisch worden geïnstalleerd op iOS-apparaten. U kunt de datum en tijd kiezen wanneer updates niet worden geïnstalleerd. U kunt dit beleid ook toewijzen aan groepen, gebruikers of apparaten en controleren op eventuele fouten bij de installatie.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0f9750603d19d9b19697c7d2660351c4586432f6
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "73984183"
---
# <a name="add-ios-software-update-policies-in-intune"></a>iOS-software-updatebeleid in Intune configureren

Dankzij beleid voor software-updates kan de nieuwste iOS-update automatisch worden geïnstalleerd door iOS-apparaten die onder supervisie staan. Wanneer u een beleid configureert, kunt u de dagen en tijden toevoegen wanneer u niet wilt dat apparaten updates installeren.

Deze functie is van toepassing op:

- iOS 10.3 of hoger (onder supervisie)

Het apparaat wordt ongeveer om de 8 uur bij Intune ingecheckt. Als er een update beschikbaar is, wordt deze door het apparaat gedownload en geïnstalleerd, behalve tijdens beperkte tijden. Hoewel het updateproces doorgaans geen tussenkomst van de gebruiker omvat, moet de gebruiker een wachtwoordcode invoeren om een software-update te starten als het apparaat een wachtwoordcode heeft. Dit geldt voor iOS 10.3 en nieuwere versies. Het beleid belet gebruikers niet om het besturingssysteem handmatig bij te werken.

## <a name="configure-the-policy"></a>Het beleid configureren

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **Software-updates** > **Beleidsregels voor iOS bijwerken** > **Maken**.
3. Geef op het tabblad **Basisinformatie** een naam en optioneel een beschrijving op en selecteer vervolgens **Volgende**.

   ![Tabblad Basisinformatie](./media/software-updates-ios/basics-tab.png) 

4. Geef op het tabblad **Instellingen voor updatebeleid** een beperkt tijdsbestek op waarin updates niet geforceerd worden geïnstalleerd.  
   - Blokkering voor 's nachts wordt niet ondersteund en werkt mogelijk niet. Configureer bijvoorbeeld geen beleid met 20:00 uur als *begintijd* en 6:00 uur als *eindtijd*.
   - Een beleidsregel die om 12:00 uur begint en eindigt om 12:00 uur, wordt als 0 uur beschouwd en niet als 24 uur. Deze configuratie levert geen beperking op.

   Wanneer u het beperkte tijdsbestek instelt, voert u de volgende gegevens in:

   - **Dagen**: Kies de dag(en) van de week waarop updates niet worden geïnstalleerd. Schakel bijvoorbeeld maandag, woensdag en vrijdag in om te voorkomen dat updates op deze dagen worden geïnstalleerd.
   - **Tijdzone**: Kies een tijdzone.
   - **Begintijd**: Kies de begintijd van het beperkte tijdsbestek. Voer bijvoorbeeld 5:00 uur in, zodat updates vanaf 5:00 uur niet worden geïnstalleerd.
   - **Eindtijd**: Kies de eindtijd van het beperkte tijdsbestek. Voer bijvoorbeeld 1:00 uur in, zodat updates vanaf 1:00 kunnen worden geïnstalleerd.
  
   > [!IMPORTANT]  
   > Een beleid waarvan de *begintijd* en *eindtijd* allebei op 12:00 uur zijn ingesteld, wordt als 0 uur beschouwd en niet als 24 uur. Dit leidt tot geen beperkingen.  
    
   Als u de zichtbaarheid van software-updates voor een bepaald tijdvenster wilt uitstellen op de iOS-apparaten onder uw supervisie, moet u deze instellingen configureren in de [Apparaatbeperkingen](../configuration/device-restrictions-ios.md#general). Het beleid voor software-updates overschrijft eventuele apparaatbeperkingen. Wanneer u zowel beleid voor software-updates als een beperking om de zichtbaarheid van software-updates te vertragen instelt, wordt op het apparaat een software-update volgens het beleid afgedwongen. De beperking is van toepassing om te voorkomen dat gebruikers de optie zien om het apparaat zelf bij te werken. De update wordt gepusht in het eerste tijdvenster zoals gedefinieerd in uw iOS-updatebeleid.

   Nadat u *Instellingen voor updatebeleid* hebt geconfigureerd, selecteert u **Volgende**. 

5. Selecteer op het tabblad **Bereiktags** de optie **Bereiktags selecteren** om het deelvenster *Tags selecteren* te openen als u deze wilt toepassing op het updatebeleid.
   
   - Kies in het deelvenster **Tags selecteren** een of meer tags en klik vervolgens op **Selecteren** om deze toe te voegen aan het beleid en terug te keren naar het deelvenster *Bereiktags*.  

   Wanneer u klaar bent, selecteert u **Volgende** om naar *Toewijzingen* te gaan.

6. Kies op het tabblad **Toewijzingen** de optie **Groepen selecteren die moeten worden opgenomen** en wijs het updatebeleid toe aan een of meer groepen. Gebruik **+ Groepen selecteren die moeten worden uitgesloten** om de toewijzing te verfijnen. Wanneer u klaar bent, selecteert u **Volgende** om verder te gaan. 

   De apparaten die worden gebruikt door de gebruikers op wie het beleid wordt toegepast, worden gecontroleerd om te zien of ze voldoen aan de updatenaleving. Dit beleid ondersteunt ook apparaten zonder gebruikers.

7. Controleer de instellingen op het tabblad **Beoordelen en maken** en selecteer vervolgens **Maken** als u klaar bent om uw iOS-updatebeleid op te slaan. Het nieuwe beleid wordt weergegeven in de lijst met updatebeleidsregels voor iOS.


Zie [Zichtbaarheid van software-updates in Intune vertragen voor apparaten die onder toezicht staan](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Delaying-visibility-of-software-updates-in-Intune-for-supervised/ba-p/345753) voor hulp van het Intune-ondersteuningsteam.

> [!NOTE]
> Apple MDM staat u niet toe om een apparaat te dwingen om vóór een bepaald tijdstip of een bepaalde datum updates te installeren.

## <a name="edit-a-policy"></a>Een beleidsregel bewerken
U kunt een bestaande beleidsregel bewerken, waaronder de beperkte tijden:

1. Selecteer in **Software-updates** de optie **Beleidsregels voor iOS bijwerken** en selecteer vervolgens het beleid dat u wilt bewerken.

2. Selecteer bij het weergeven van de **Eigenschappen** van beleidsregels de optie **Bewerken** voor de beleidspagina die u wilt wijzigen.  
   ![Een beleidsregel bewerken](./media/software-updates-ios/edit-policy.png)   

3. Nadat u een wijziging hebt aangebracht, selecteert u **Beoordelen en opslaan** > **Opslaan** om uw wijzigingen op te slaan en gaat u terug naar de *Eigenschappen* van beleidsregels.  
 
> [!NOTE]
> Als de **Begintijd** en de **Eindtijd** allebei op 12:00 uur zijn ingesteld, wordt er in Intune niet gecontroleerd of er tijdbeperkingen gelden voor het installeren van updates. Dit betekent dat al uw configuraties voor **Tijden selecteren om de installatie van updates te voorkomen** worden genegeerd en dat updates op elk moment kunnen worden geïnstalleerd.  


## <a name="monitor-device-installation-failures"></a>Installatiefouten op apparaten controleren
<!-- 1352223 -->
In **Software-updates** > **Installatiefouten op iOS-apparaten** wordt een lijst opgegeven met gecontroleerde iOS-apparaten waarop een updatebeleid was gericht, waarvoor is geprobeerd een update uit te voeren, maar dit niet mogelijk was. Voor elk apparaat kunt u bekijken waarom het apparaat niet automatisch is bijgewerkt. Bijgewerkte apparaten die in orde zijn, worden niet weergegeven in de lijst. Een apparaat is bijgewerkt als de meest recente update is geïnstalleerd die door het apparaat zelf wordt ondersteund.

## <a name="next-steps"></a>Volgende stappen

[Controleer de status ervan.](../configuration/device-profile-monitor.md)
