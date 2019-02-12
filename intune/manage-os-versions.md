---
title: Besturingssysteemversies beheren met Microsoft Intune | Microsoft Intune
description: Informatie over het beheren van besturingssysteemversies voor meerdere platformen met Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/02/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 361ef17b-1ee0-4879-b7b1-d678b0787f5a
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: faf51236be219a860447d2243967b90e3aab1d01
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55837234"
---
# <a name="manage-operating-system-versions-with-intune"></a>Besturingssysteemversies beheren met Intune
Op moderne mobiele en bureaubladplatformen volgen belangrijke updates, patches en nieuwe versie elkaar in hoog tempo op. U hebt de middelen om updates en patches voor Windows volledig te beheren, maar bij andere platformen, zoals iOS en Android, is de medewerking van uw eindgebruikers vereist.  Microsoft Intune biedt de mogelijkheid om het beheer van besturingssysteemversies voor meerdere platformen beter te structureren.

U kunt Intune gebruiken in de volgende, veelvoorkomende scenario’s: 
- Bepalen welke besturingssysteemversies er op de apparaten van eindgebruikers staan
- Toegang beheren tot bedrijfsgegevens op apparaten gedurende de validatie van een nieuwe release van een besturingssysteem
- Eindgebruikers aanmoedigen/verplichten om te upgraden naar de nieuwste versie van het besturingssysteem die is goedgekeurd door uw organisatie
- Een organisatiebrede implementatie van een nieuwe versie van een besturingssysteem beheren
  
## <a name="operating-system-version-control-using-intune-mobile-device-management-mdm-enrollment-restrictions"></a>Beheer van besturingssysteemversies met Intune MDM-inschrijvingsbeperkingen (Mobile Device Management)
Met Intune MDM-inschrijvingsbeperkingen kunt u de vereisten definiëren waaraan het clientapparaat moet voldoen voordat het kan worden ingeschreven. Het doel is om te vereisten dat uw eindgebruikers alleen compatibele apparaten inschrijven voordat ze toegang krijgen tot organisatiemiddelen. De apparaatvereisten omvatten zowel de toegestane laagste en hoogste besturingssysteemversie voor de ondersteunde platformen.
 
![Blade configuratiebeperkingen voor platformen](./media/os-version-platform-configurations.png) 
 
### <a name="in-practice"></a>In de praktijk
Organisaties gebruiken apparaattypebeperkingen om de toegang tot bedrijfsmiddelen te beheren met de volgende instellingen: 
1. Gebruik een minimale besturingssysteemversie zodat eindgebruikers werken op actuele en ondersteunde platformen binnen de organisatie. 
2. Laat de hoogste besturingssysteemversie ongedefinieerd (geen limiet) of stel die in op dat de laatste door uw organisatie gevalideerde versie, zodat u tijd hebt om nieuwe versies van besturingssystemen intern te testen.

Zie [Beperkingen voor apparaattypen instellen](https://docs.microsoft.com/intune/enrollment-restrictions-set#set-device-type-restrictions) voor meer informatie.
 
## <a name="operating-system-version-reporting-and-compliance-with-intune-mdm-device-compliance-policies"></a>Rapportage over besturingssysteemversies en naleving van het Intune MDM-nalevingsbeleid voor apparaten
Het Intune MDM-nalevingsbeleid voor apparaten biedt u de volgende hulpmiddelen: 
- Nalevingsregels configureren
- Nalevingsstatus weergeven via rapportage
- Reageren op niet-naleving met quarantainemaatregelen en voorwaardelijke toegang

Net zoals inschrijvingsbeperkingen bevat het nalevingsbeleid voor apparaten zowel een minimale als maximale versie van een besturingssysteem. Het beleid heeft een planning, zodat gebruikers de tijd hebben om voor naleving te zorgen. Het nalevingsbeleid voor apparaten zorgt ervoor dat de ingeschreven gebruikersapparaten voldoen aan het organisatiebeleid.

![Apparaatnaleving - acties bij niet-naleving](./media/os-version-actions-noncompliance.png) 

### <a name="in-practice"></a>In de praktijk
Organisaties gebruiken nalevingsbeleid voor apparaten in dezelfde scenario’s als inschrijvingsbeperkingen. Dit beleid zorgt ervoor dat gebruikers binnen uw organisatie werken met actuele, gevalideerde besturingssysteemversies. Als een apparaat van een gebruiker niet meer aan het nalevingsbeleid voldoet, kan de toegang tot bedrijfsmiddelen worden geblokkeerd met voorwaardelijke toegang, tot de eindgebruikers weer een ondersteunde besturingssysteemversie voor de organisatie hebben. Eindgebruikers worden op de hoogte gesteld van de niet-naleving en de stappen die ze moeten uitvoeren om weer toegang te krijgen.   

Zie [Aan de slag met apparaatnaleving](https://docs.microsoft.com/intune/device-compliance-get-started) voor meer informatie.
 
## <a name="operating-system-version-controls-using-intune-app-protection-policies"></a>Beheer van besturingssysteemversies met Intune-beveiligingsbeleid voor apps    
Met het Intune-beveiligingsbeleid voor apps en de instellingen voor toegang in het beheer van mobiele toepassingen (MAM) kunt u de minimale versie van het besturingssysteem instellen op app-niveau. Hiermee kunt u eindgebruikers informatie geven en ze aanmoedigen of verplichten om hun besturingssysteem te updaten naar minimaal een bepaalde versie.
 
Daarbij hebt u twee opties: 
- **Waarschuwen**: bij Waarschuwen worden eindgebruikers geïnformeerd dat ze beter kunnen upgraden, wanneer ze een app met een beveiligingsbeleid of MAM-toegangsinstellingen openen op een apparaat met een besturingssysteemversie die lager is dan de gespecificeerde versie. Toegang is toegestaan voor de app en de bedrijfsgegevens.
  ![Afbeelding van het dialoogvenster met waarschuwing over bijwerken in Android](./media/os-version-update-warning.png) 

- **Blokkeren**: bij Blokkeren worden eindgebruikers geïnformeerd dat ze een upgrade moeten uitvoeren, wanneer ze een app met een beveiligingsbeleid of MAM-toegangsinstellingen openen op een apparaat met een besturingssysteemversie die lager is dan de gespecificeerde versie. Toegang is niet toegestaan voor de app en de bedrijfsgegevens.
  ![Afbeelding van het dialoogvenster App-toegang geblokkeerd](./media/os-version-access-blocked.png)

### <a name="in-practice"></a>In de praktijk
Organisaties gebruiken de instellingen van beveiligingsbeleid voor apps wanneer apps worden geopend of hervat, als een manier om eindgebruikers te informeren over de noodzaak om hun apps up-to-date te houden. Een voorbeeld van een configuratie is dat eindgebruikers worden gewaarschuwd bij huidige versie min één, en geblokkeerd bij huidige versie min twee.
 
Zie [App-beveiligingsbeleid maken en toewijzen](https://docs.microsoft.com/intune/app-protection-policies) voor meer informatie.

## <a name="managing-a-new-operating-system-version-rollout"></a>De implementatie van een nieuwe besturingssysteemversie beheren
U kunt de mogelijkheden van Intune die in dit artikel worden beschreven gebruiken om uw organisatie over te laten gaan naar een nieuwe besturingssysteemversie, binnen een door u opgestelde planning. De volgende stappen zijn een voorbeeld van een implementatiemodel waarmee u gebruikers in zeven dagen laat upgraden van besturingssysteem v1 naar besturingssysteem v2.
- **Stap 1**: gebruik inschrijvingsbeperkingen om besturingssysteem v2 verplicht te stellen als laagste versie voor de inschrijving van het apparaat. Dit zorgt voor naleving van nieuwe apparaten ten tijde van inschrijving.
- **Stap 2a**: gebruik Intune-beveiligingsbeleid voor apps om gebruikers te waarschuwen dat besturingssysteem v2 is vereist, wanneer de app wordt geopend of hervat.
- **Stap 2b**: gebruik nalevingsbeleid voor apparaten om besturingssysteem v2 te vereisen als laagste versie voor naleving van het apparaat. Gebruik **Acties** voor niet-naleving om gebruikers een overgangsperiode van zeven dagen te bieden, en ze een e-mail te sturen met de planning en vereisten.
  -  Dit beleid informeert gebruikers op meerdere manieren dat hun bestaande apparaten moeten worden bijgewerkt: per e-mail, op de Intune-bedrijfsportal en wanneer de app wordt geopend als er een beveiligingsbeleid voor apps voor is ingeschakeld.
  - U kunt een nalevingsrapport uitvoeren over niet-naleving bij gebruikers. 
- **Stap 3a**: gebruik Intune-beveiligingsbeleid voor apps om gebruikers te blokkeren wanneer een app wordt geopend of hervat en besturingssysteem v2 niet wordt uitgevoerd op het apparaat.
- **Stap 3b**: gebruik nalevingsbeleid voor apparaten om besturingssysteem v2 te vereisen als laagste versie voor naleving van het apparaat.
  - Dit beleid vereist dat apparaten worden bijgewerkt om toegang te krijgen tot organisatiegegevens. Beveiligde services worden geblokkeerd bij gebruik van voorwaardelijk toegang voor apparaten. Apps waarvoor een beveiligingsbeleid is ingeschakeld worden geblokkeerd wanneer ze worden geopend of toegang proberen te krijgen tot organisatiegegevens.

## <a name="next-steps"></a>Volgende stappen
U kunt de volgende hulpmiddelen gebruiken voor het beheer van besturingssysteemversies in uw organisatie: 

- [Beperkingen voor apparaattypen instellen](https://docs.microsoft.com/intune/enrollment-restrictions-set#set-device-type-restrictions)
- [Aan de slag met apparaatnaleving](https://docs.microsoft.com/intune/device-compliance-get-started)
- [App-beveiligingsbeleid maken en toewijzen](https://docs.microsoft.com/intune/app-protection-policies)
