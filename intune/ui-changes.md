---
title: Waar is de Intune-functie die ik zoek gebleven in Azure?
titleSuffix: Intune Azure preview
description: Intune Azure Preview helpt u met het terugvinden van Intune-functies in de Azure-console.
keywords: 
author: dagerrit
ms.author: dagerrit
manager: angrobe
ms.date: 03/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 9dd6e93108ffc46e9e52b6928cf513161d29f7a4
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---
# <a name="where-did-my-intune-feature-go-in-azure"></a>Waar is de Intune-functie die ik zoek gebleven in Azure?
Bij het verplaatsen van Intune naar de Azure-portal hebben we van de gelegenheid gebruikgemaakt om een aantal taken logischer in te delen. Maar dergelijke verbeteringen betekenen wel dat u de nieuwe indeling moet leren kennen. Deze referentiegids is speciaal bedoeld voor degenen die heel vertrouwd zijn met Intune in de klassieke console, en die zich afvragen waar bepaalde functies in Intune zijn gebleven in Azure. Als een functie die u zoekt niet wordt behandeld in dit artikel, laat dan een reactie achter onder het artikel, zodat we het kunnen bijwerken.
## <a name="quick-reference-guide"></a>Naslaggids
|Functie |Pad in klassieke console|Pad in Intune op Azure| |------------||---------------|---------------|
|Device Enrollment Program (DEP) |Beheer > Mobile Device Management > iOS en Mac OS X > Device Enrollment Program|[Apparaatinschrijving > Apple-inschrijving > Enrollment Program-token](#where-did-apple-dep-go) |
|Device Enrollment Program (DEP)| Beheer > Mobile Device Management > iOS en Mac OS X > Device Enrollment Program |[Apparaatinschrijving > Apple-inschrijving > Serienummers inschrijvingsprogramma](#where-did-apple-dep-go) |
|Inschrijvingsregels|Beheer > Mobile Device Management > Inschrijvingsregels|[Apparaatinschrijving > Inschrijvingsbeperkingen](#where-did-enrollment-rules-go) |
|Groepen op iOS-serienummer |Groepen > Alle apparaten > Vooraf geregistreerde bedrijfsapparaten > Op iOS-serienummer|[Apparaatinschrijving > Apple-inschrijving > Serienummers inschrijvingsprogramma](#where-did-corporate-pre-enrolled-devices-go) |
|Groepen op iOS-serienummer |Groepen > Alle apparaten > Vooraf geregistreerde bedrijfsapparaten > Op iOS-serienummer|[Apparaatinschrijving > Apple-inschrijving > AC-serienummers](#where-did-corporate-pre-enrolled-devices-go)|
|Groepen op IMEI (alle platformen)| Groepen > Alle apparaten > Vooraf geregistreerde bedrijfsapparaten > Op IMEI (alle platformen) |[Apparaatinschrijving > Bedrijfsapparaat-id’s](#by-imei-all-platforms)|
|Inschrijvingsprofiel voor bedrijfsapparaten|Beleid > Inschrijving van bedrijfsapparaten |[Apparaatinschrijving > Apple-inschrijving > Profielen voor apparaatinschrijving](#where-did-corporate-pre-enrolled-devices-go) |
| Inschrijvingsprofiel voor bedrijfsapparaten | Beleid > Inschrijving van bedrijfsapparaten| [Apparaatinschrijving > Apple-inschrijving > AC-profielen](#where-did-corporate-pre-enrolled-devices-go) |
| Android for Work | Beheer > Mobile Device Management > Android for Work | Apparaatinschrijving > Android for Work-inschrijving | | Voorwaarden | Beleid > Voorwaarden | Apparaatinschrijving > Voorwaarden |


## <a name="where-do-i-manage-groups"></a>Waar kan ik groepen beheren?
Intune op Azure gebruikt [Azure Active Directory (AD)](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal) om groepen te beheren.

## <a name="where-did-enrollment-rules-go"></a>Waar zijn de inschrijvingsregels gebleven?
In de klassieke console kunt u regels instellen voor de MDM-inschrijving van mobiele en moderne Windows- en macOS-apparaten:

![Afbeelding van regels voor inschrijving van mobiele apparaten in klassieke console](./media/01-classic-rules.png)

Deze regels waren van toepassing op alle gebruikers in uw Intune-account, zonder uitzonderingen. In de Azure-portal zijn deze regels nu onderverdeeld in twee typen beleid, Beperkingen voor apparaattypen en Apparaatlimietbeperkingen:

![Afbeelding van beperkingen voor inschrijving van mobiele apparaten in Azure](./media/02-azure-enroll-restrictions.png)

De standaard Apparaatlimietbeperking komt overeen met de Limiet apparaatinschrijvingen in de klassieke console:

![Afbeeldingen van apparaatlimietbeperkingen in Azure](./media/03-azure-device-limit.png)

De standaard Beperking voor apparaattypen komt overeen met de Platformbeperkingen in de klassieke console:

![Afbeeldingen van beperking voor apparaattype in Azure](./media/04-azure-platform-restrictions.png)

De mogelijkheid om apparaten in persoonlijk eigendom toe te staan of te blokkeren, wordt nu beheerd onder de Platformconfiguraties van de Beperkingen voor apparaattypen:

![Afbeelding van blokkeringsinstellingen voor persoonlijke apparaten in Azure](./media/05-azure-personal-block.png)

Nieuwe beperkingsmogelijkheden worden uitsluitend toegevoegd aan Azure Portal.

## <a name="where-did-apple-dep-go"></a>Waar is Apple DEP gebleven?
In de klassieke console kunt u Intune instellen voor integratie met het Device Enrollment Program van Apple, en handmatig synchroniseren met de service van Apple:

![Afbeelding van klassieke DEP-token](./media/06-classic-dep-token.png)

In de Azure-portal stelt u het Apple Device Enrollment Program in met dezelfde stappen als in de klassieke versie van Intune:

![Afbeelding van Azure DEP-token](./media/07-azure-dep-token.png)

De optie **Synchroniseren** in de klassieke console is echter verplaatst naar de werkstroom voor serienummerbeheer, omdat de resultaten van een handmatige synchronisatie daar worden weergeven:

![Afbeelding van Azure DEP-synchronisatie](./media/08-azure-dep-sync.png)

## <a name="where-did-corporate-pre-enrolled-devices-go"></a>Waar zijn de vooraf geregistreerde bedrijfsapparaten gebleven?
### <a name="by-ios-serial-number"></a>Op iOS-serienummer
In de klassieke console kunt u iOS-apparaten inschrijven via het Apple Device Enrollment Program (DEP) en het hulpprogramma Apple Configurator. In beide methoden is het vooraf inschrijven van apparaten op serienummer mogelijk en worden speciale profielen voor de inschrijving van bedrijfsapparaten gebruikt. Voorafgaand aan de inschrijving kunt u de toewijzing van het inschrijvingsprofiel beheren via de apparaatgroep **Vooraf geregistreerde bedrijfsapparaten op iOS-serienummer**:

![Afbeelding van Apple-serienummers in klassieke console](./media/09-classic-apple-serials.png)

Deze lijst bevat serienummers voor inschrijving met zowel Apple DEP als Configurator. Ter voorkoming van niet-overeenkomende profieltoewijzingen (DEP-profiel aan AC-serienummer en andersom) hebben we de serienummers verdeeld in twee lijsten in de Azure-portal:

**DEP-serienummers**
![Afbeelding van Azure DEP-serienummers](./media/10-azure-dep-serials.png)

**Apple Configurator-serienummers**
![Afbeelding van Azure Apple Configurator-serienummers](./media/11-azure-ac-serials.png)

### <a name="by-imei-all-platforms"></a>Op IMEI (alle platformen)

In de klassieke console kunt u vooraf een lijst maken met de IMEI-nummers van apparaten, om ze te markeren als bedrijfsapparaten voor de inschrijving bij Intune:

![Afbeelding van klassieke lijst met IMEI-nummers](./media/12-classic-corp-imei.png)

In de Azure-console moet u dezelfde IMEI uploaden naar de lijst Bedrijfsapparaat-id’s in een kommagescheiden CSV-bestand. In de nieuwe portal kunt u IMEI-nummers niet handmatig invoeren:

![Afbeelding van lijst met IMEI-nummers in Azure](./media/13-azure-corp-imei.png)

Intune in de Azure-portal is voorbereid op toekomstige identificatienummers anders dan IMEI, maar momenteel kunnen in vooraf opgestelde lijsten alleen IMEI-nummers worden gebruikt.

## <a name="where-did-corporate-device-enrollment-profiles-go"></a>Waar zijn de inschrijvingsprofielen voor bedrijfsapparaten gebleven?
Als u iOS-apparaten wilt inschrijven via het Apple Device Enrollment Program of met het hulpprogramma Apple Configurator, moet u een inschrijvingsprofiel voor bedrijfsapparaten opgeven om aan het apparaat toe te wijzen. In de klassieke console verliep het maken en beheren van deze profielen via een enkele lijst:

![Afbeelding van profielen voor apparaatinschrijving in klassieke console](./media/14-classic-corp-profiles.png)

In de lijst staan profielen die kunnen worden gebruikt met het Apple Device Enrollment Program (**DEP Aan**) en profielen die alleen kunnen worden gebruikt met het hulpprogramma Apple Configurator (**DEP Uit**).

Ter voorkoming van verwarring tussen de twee profieltypen en eventuele onjuiste toewijzingen (DEP-profiel aan Configurator-apparaat en omgekeerd), hebben we het maken en beheren van Inschrijvingsprofielen (ondersteunen zowel Apple Device Enrollment Program en Apple School Manager) en Apple Configurator-profielen gescheiden:

**DEP-profielen**
![Afbeelding van Azure DEP-profielen](./media/15-azure-dep-profiles.png)

**Apple Configurator-profielen**
![Afbeelding van Azure Apple Configurator-profielen](./media/16-azure-ac-profiles.png)

