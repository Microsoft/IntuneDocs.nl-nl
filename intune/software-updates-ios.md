---
title: iOS-software-updatebeleid configureren in Microsoft Intune - Azure | Microsoft Docs
description: Maak of voeg in Microsoft Intune configuratiebeleid toe om beperkingen in te stellen wanneer software-updates automatisch worden geïnstalleerd op iOS-apparaten die door Intune worden beheerd of onder supervisie staan van Intune. U kunt de datum en tijd kiezen wanneer updates niet worden geïnstalleerd. U kunt dit beleid ook toewijzen aan groepen, gebruikers of apparaten en controleren op eventuele fouten bij de installatie.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
search.appverid: MET150
ms.openlocfilehash: d73dc96c966b93f26269cc53527a787824c94d3b
ms.sourcegitcommit: 00fe2b601e3becbe5d644fcbd35a706da3b43af2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/02/2019
ms.locfileid: "55652626"
---
# <a name="configure-ios-update-policies-in-intune"></a>iOS-updatebeleid in Intune configureren

Dankzij beleid voor software-updates kan de nieuwste iOS-update automatisch worden geïnstalleerd door iOS-apparaten die onder supervisie staan. Deze functie is alleen beschikbaar voor apparaten die onder supervisie staan. Wanneer u een beleid configureert, kunt u de dagen en tijden toevoegen wanneer u niet wilt dat apparaten updates installeren. 

Het apparaat wordt ongeveer om de 8 uur bij Intune ingecheckt. Als een update beschikbaar is en het betreft geen beperkte periode, wordt de meest recente update van het besturingssysteem naar het apparaat gedownload en erop geïnstalleerd. Er is geen tussenkomst van de gebruiker nodig om het apparaat bij te werken. Het beleid belet gebruikers niet om het besturingssysteem handmatig bij te werken.

Deze functie biedt ondersteuning voor apparaten met iOS 10.3 en latere versies. De vertragingsinstelling is beschikbaar in iOS 11.3 en in latere versies.

## <a name="configure-the-policy"></a>Het beleid configureren
1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Software-updates** > **Beleidsregels voor iOS bijwerken** > **Maken**.
4. Geef een naam en beschrijving op voor het beleid.
5. Selecteer **Instellingen**. 

    Voer de details in voor het geval waarbij iOS-apparaten niet worden gedwongen de meest recente update te installeren. Deze instellingen zorgen voor een beperkte tijdsperiode. U kunt de **dagen** van de week, de **tijdzone**, de **begintijd** en de **eindtijd** configureren, en instellen of u wel of niet **de zichtbaarheid van de software-update wilt vertragen (dagen)** om gebruikers in te voeren. U kunt een vertragingsbereik van software-updates selecteren van 1 tot 90 dagen. Wanneer de vertraging verloopt, krijgen gebruikers een melding om een update uit te voeren naar de vroegste versie van het besturingssysteem die beschikbaar was toen de vertraging werd geactiveerd. Als u geen vertraging van software-update wilt instellen, geeft u 0 op. Deze update-instellingen zijn alleen van toepassing op iOS-apparaten die onder supervisie staan.
  
    Als bijvoorbeeld iOS 12.a beschikbaar is op **1 januari** en u **Updates besturingssysteem vertragen** hebt ingesteld op **5 dagen**, dan wordt die specifieke versie niet als een beschikbare update weergegeven op apparaten van eindgebruikers die aan dat profiel zijn toegewezen. Op de **zesde dag** na de release wordt die update als beschikbaar weergegeven en mogen alle eindgebruikers een update starten.


6. Selecteer **OK** om uw wijzigingen op te slaan. Selecteer **Maken** om het beleid te maken.

Het profiel wordt gemaakt en wordt weergegeven in de lijst met beleidsregels. Apple MDM staat u niet toe om een apparaat te dwingen om vóór een bepaald tijdstip of een bepaalde datum updates te installeren. 

## <a name="change-the-restricted-times-for-the-policy"></a>De tijdstippen met beperkingen voor het beleid wijzigen

1. Selecteer in **Software-updates** **Beleidsregels voor iOS bijwerken**.
2. Kies een bestaand beleid > **Eigenschappen**.
3. De tijd met beperkingen bijwerken:
    
    1. De dagen van de week kiezen
    2. De tijdzone kiezen waarin dit beleid wordt toegepast
    3. De begin- en eindtijd opgeven voor niet-toegestane uren

    > [!NOTE]
    > Als de **begintijd** en **eindtijd** beide zijn ingesteld op 12:00 uur, wordt de controle van het onderhoudstijdstip uitgeschakeld.

## <a name="assign-the-policy-to-users"></a>Het beleid toewijzen aan gebruikers

Bestaande beleidsregels worden toegewezen aan groepen, gebruikers of apparaten. Wanneer toegewezen, wordt het beleid toegepast.

1. Selecteer in **Software-updates** **Beleidsregels voor iOS bijwerken**.
2. Kies een bestaand beleid > **Toewijzingen**. 
3. Selecteer de Azure Active Directory-groepen, -gebruikers of -apparaten die u wilt opnemen of uitsluiten van dit beleid.
4. Kies **Opslaan** om het beleid voor uw groepen te implementeren.

De apparaten die worden gebruikt door de gebruikers op wie het beleid wordt toegepast, worden gecontroleerd om te zien of ze voldoen aan de updatenaleving. Dit beleid ondersteunt ook apparaten zonder gebruikers.

## <a name="monitor-device-installation-failures"></a>Installatiefouten op apparaten controleren
In <!-- 1352223 -->
**Software-updates** > **Installatiefouten op iOS-apparaten** wordt een lijst opgegeven met gecontroleerde iOS-apparaten waarop een updatebeleid was gericht, waarvoor is geprobeerd een update uit te voeren, maar dit niet mogelijk was. Voor elk apparaat kunt u bekijken waarom het apparaat niet automatisch is bijgewerkt. Bijgewerkte apparaten die in orde zijn, worden niet weergegeven in de lijst. Een apparaat is bijgewerkt als de meest recente update is geïnstalleerd die door het apparaat zelf wordt ondersteund.

