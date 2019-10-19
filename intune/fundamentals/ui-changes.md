---
title: Waar is de Intune-functie die ik zoek gebleven in Azure?
titleSuffix: Microsoft Intune
description: Hiermee kunt u Microsoft Intune-functies in Azure Portal zoeken.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 1/4/2018
ms.topic: archived
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 809d9d76-20f8-4329-9e18-cd7d4946a9af
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9de5d1550c860d9b160203b47b883550ea4db90e
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72504930"
---
# <a name="where-did-my-intune-feature-go-in-azure"></a>Waar is de Intune-functie die ik zoek gebleven in Azure?
Bij het verplaatsen van Intune naar de Azure-portal hebben we van de gelegenheid gebruikgemaakt om een aantal taken logischer in te delen. Maar dergelijke verbeteringen betekenen wel dat u de nieuwe indeling moet leren kennen. Deze referentiegids is speciaal bedoeld voor degenen die heel vertrouwd zijn met Intune in de klassieke portal, en die zich afvragen waar bepaalde functies in Intune zijn gebleven in Azure Portal. Als een functie die u zoekt niet wordt behandeld in dit artikel, laat dan een reactie achter onder het artikel, zodat we het kunnen bijwerken.
## <a name="quick-reference-guide"></a>Naslaggids

|Onderdeel |Pad in klassieke portal|Pad in Intune in de Azure-portal|
|------------|---------------|---------------|
|Device Enrollment Program (DEP) (alleen iOS)|Beheerder > Mobile Device Management > iOS > Device Enrollment Program|[Apparaatinschrijving > Apple-inschrijving > Token voor het inschrijvingsprogramma](#where-did-apple-dep-go) |
|Device Enrollment Program (DEP) (alleen iOS)| Beheerder > Mobile Device Management > iOS en Mac OS X > Device Enrollment Program |[Apparaatinschrijving > Apple-inschrijving > Serienummers voor het inschrijvingsprogramma](#where-did-apple-dep-go) |
|Inschrijvingsregels |Beheerder > Mobile Device Management > Inschrijvingsregels|[Apparaatinschrijving > Inschrijvingsbeperkingen](#where-did-enrollment-rules-go) |
|Wordt gegroepeerd op iOS-serienummer |Groepen > Alle apparaten > Vooraf geregistreerde bedrijfsapparaten > Op iOS-serienummer|[Apparaatinschrijving > Apple-inschrijving > Serienummers voor het inschrijvingsprogramma](#where-did-corporate-pre-enrolled-devices-go) |
|Wordt gegroepeerd op iOS-serienummer |Groepen > Alle apparaten > Vooraf geregistreerde bedrijfsapparaten > Op iOS-serienummer| [Apparaatinschrijving > Apple-inschrijving > AC-serienummers](#where-did-corporate-pre-enrolled-devices-go)|
|Wordt gegroepeerd op IMEI (alle platformen)| Groepen > Alle apparaten > Vooraf geregistreerde bedrijfsapparaten > Op IMEI (alle platforms) | [Apparaatinschrijving > Bedrijfsapparaat-id's](#by-imei-all-platforms)|
| Inschrijvingsprofiel voor bedrijfsapparaten| Beleid > Inschrijving van bedrijfsapparaten | [Apparaatinschrijving > Apple-inschrijving > Profielen voor het inschrijvingsprogramma](#where-did-corporate-pre-enrolled-devices-go) |
| Inschrijvingsprofiel voor bedrijfsapparaten | Beleid > Inschrijving van bedrijfsapparaten | [Apparaatinschrijving > Apple-inschrijving > AC-profielen](#where-did-corporate-pre-enrolled-devices-go) |
| Android for Work | Beheerder > Mobile Device Management > Android for Work | Apparaatinschrijving > Android-inschrijving |
| Voorwaarden | Beleid > Voorwaarden | Apparaatinschrijving > Voorwaarden |
Instellingen voor de bedrijfsportal|Beheer > Bedrijfsportal|**Beheer** > Mobiele apps<br> **Installatie** > Huisstijl voor bedrijfsportal


## <a name="where-do-i-manage-groups"></a>Waar kan ik groepen beheren?
Intune in de Azure-portal gebruikt [Azure Active Directory (AD)](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal) om groepen te beheren.

## <a name="where-did-enrollment-rules-go"></a>Waar zijn de inschrijvingsregels gebleven?
In de klassieke portal kunt u regels instellen voor de MDM-inschrijving van mobiele en moderne Windows- en macOS-apparaten.

![Afbeelding van regels voor inschrijving van mobiele apparaten in klassieke console](./media/ui-changes/01-classic-rules.png)

Deze regels waren van toepassing op alle gebruikers in uw Intune-account, zonder uitzonderingen. In Azure Portal zijn deze regels nu onderverdeeld in twee typen beleid, Beperkingen voor apparaattypen en Apparaatlimietbeperkingen.

![Afbeelding van beperkingen voor inschrijving van mobiele apparaten in Azure](./media/ui-changes/02-azure-enroll-restrictions.png)

De standaard Apparaatlimietbeperking komt overeen met de Limiet apparaatinschrijvingen in de klassieke portal.

![Afbeeldingen van apparaatlimietbeperkingen in Azure](./media/ui-changes/03-azure-device-limit.png)

De standaard Beperking voor apparaattypen komt overeen met de Platformbeperkingen in de klassieke portal.

![Afbeeldingen van beperking voor apparaattype in Azure](./media/ui-changes/04-azure-platform-restrictions.png)

De mogelijkheid om apparaten in persoonlijk eigendom toe te staan of te blokkeren, wordt nu beheerd onder de Platformconfiguraties van de Beperkingen voor apparaattypen.

![Afbeelding van blokkeringsinstellingen voor persoonlijke apparaten in Azure](./media/ui-changes/05-azure-personal-block.png)

Nieuwe beperkingsmogelijkheden worden uitsluitend toegevoegd aan Azure Portal.

## <a name="where-did-my-conditional-access-policies-go"></a>Waar is mijn beleid voor voorwaardelijke toegang?
Nadat uw tenant is gemigreerd naar de Azure-portal, blijven de beleidsregels voor voorwaardelijke toegang van uw tenant van kracht. U kunt deze echter niet weergeven of wijzigen via Intune in Azure Portal.

Als u beleidsregels voor voorwaardelijke toegang wilt weergeven en er wijzigingen in wilt aanbrengen via de Azure-portal, moet u de oude beleidsregels verwijderen uit de klassieke portal. U maakt ze daarna opnieuw in Azure Portal. Raadpleeg [Klassiek beleid migreren in de Azure-portal](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-migration) voor meer informatie over het migreren van beleidsregels voor voorwaardelijke toegang. 

## <a name="where-did-my-compliance-policies-go"></a>Waar is mijn nalevingsbeleid gebleven?
Nadat uw tenant is gemigreerd naar Azure Portal, blijft het nalevingsbeleid van uw tenant van kracht. U kunt deze echter niet weergeven of wijzigen via Intune in Azure Portal.

Als u het nalevingsbeleid wilt weergeven en er wijzigingen in wilt aanbrengen vanuit Azure Portal, moet u de oude beleidsregels verwijderen uit de klassieke portal. U maakt ze daarna opnieuw in Azure Portal. Zie [Aan de slag met apparaatnalevingsbeleid](../protect/device-compliance-get-started.md) voor meer informatie over beleidsregels voor apparaatnaleving. 

## <a name="where-did-apple-dep-go"></a>Waar is Apple DEP gebleven?
In de klassieke portal kunt u Intune instellen voor integratie met het Device Enrollment Program van Apple, en handmatig synchroniseren met de service van Apple:

![Afbeelding van klassieke DEP-token](./media/ui-changes/06-classic-dep-token.png)

In de Azure-portal stelt u het Apple Device Enrollment Program in met dezelfde stappen als in de klassieke versie van Intune:

![Afbeelding van Azure DEP-token](./media/ui-changes/07-azure-dep-token.png)

De optie **Synchroniseren** in de klassieke portal is echter verplaatst naar de werkstroom voor serienummerbeheer, omdat de resultaten van een handmatige synchronisatie hier worden weergegeven:

![Afbeelding van Azure DEP-synchronisatie](./media/ui-changes/08-azure-dep-sync.png)

## <a name="where-did-corporate-pre-enrolled-devices-go"></a>Waar zijn de vooraf geregistreerde bedrijfsapparaten gebleven?
### <a name="by-ios-serial-number"></a>Op iOS-serienummer
In de klassieke portal kunt u iOS-apparaten inschrijven via het Apple Device Enrollment Program (DEP) en het hulpprogramma Apple Configurator. In beide methoden is het vooraf inschrijven van apparaten op serienummer mogelijk en worden speciale profielen voor de inschrijving van bedrijfsapparaten gebruikt. Voorafgaand aan de inschrijving kunt u de toewijzing van het inschrijvingsprofiel beheren via de apparaatgroep **Vooraf geregistreerde bedrijfsapparaten op iOS-serienummer**:

![Afbeelding van Apple-serienummers in klassieke console](./media/ui-changes/09-classic-apple-serials.png)

Deze lijst bevat serienummers voor inschrijving met zowel Apple DEP als Configurator. Ter voorkoming van niet-overeenkomende profieltoewijzingen (DEP-profiel aan AC-serienummer en andersom) hebben we de serienummers verdeeld in twee lijsten in de Azure-portal:

**DEP-serienummers**
![Afbeelding van Azure DEP-serienummers](./media/ui-changes/10-azure-dep-serials.png)

**Apple Configurator-serienummers**
![Afbeelding van Azure Apple Configurator-serienummers](./media/ui-changes/11-azure-ac-serials.png)

### <a name="by-imei-all-platforms"></a>Op IMEI (alle platformen)

In de klassieke portal kunt u vooraf een lijst maken met de IMEI-nummers van apparaten, om ze te markeren als bedrijfsapparaten voor de inschrijving bij Intune:

![Afbeelding van klassieke lijst met IMEI-nummers](./media/ui-changes/12-classic-corp-imei.png)

In de Azure-portal moet u dezelfde IMEI uploaden naar de lijst Bedrijfsapparaat-id’s in een kommagescheiden CSV-bestand. In de nieuwe portal kunt u IMEI-nummers niet handmatig invoeren:

![Afbeelding van lijst met IMEI-nummers in Azure](./media/ui-changes/13-azure-corp-imei.png)

Intune in de Azure-portal is voorbereid op toekomstige identificatienummers anders dan IMEI, maar momenteel kunnen in vooraf opgestelde lijsten alleen IMEI-nummers worden gebruikt.

## <a name="where-did-corporate-device-enrollment-profiles-go"></a>Waar zijn de inschrijvingsprofielen voor bedrijfsapparaten gebleven?
Als u iOS-apparaten wilt inschrijven via het Apple Device Enrollment Program of met het hulpprogramma Apple Configurator, moet u een inschrijvingsprofiel voor bedrijfsapparaten opgeven om aan het apparaat toe te wijzen. In de klassieke portal verliep het maken en beheren van deze profielen via een enkele lijst:

![Afbeelding van profielen voor apparaatinschrijving in klassieke console](./media/ui-changes/14-classic-corp-profiles.png)

In de lijst staan profielen die kunnen worden gebruikt met het Apple Device Enrollment Program (**DEP Aan**) en profielen die alleen kunnen worden gebruikt met het hulpprogramma Apple Configurator (**DEP Uit**).

Ter voorkoming van verwarring tussen de twee profieltypen en eventuele onjuiste toewijzingen (DEP-profiel aan Configurator-apparaat en omgekeerd), hebben we het maken en beheren van Inschrijvingsprofielen (ondersteunen zowel Apple Device Enrollment Program en Apple School Manager) en Apple Configurator-profielen gescheiden:

**DEP-profielen**
![Afbeelding van Azure DEP-profielen](./media/ui-changes/15-azure-dep-profiles.png)

**Apple Configurator-profielen**
![Afbeelding van Azure Apple Configurator-profielen](./media/ui-changes/16-azure-ac-profiles.png)
