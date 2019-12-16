---
title: Overzicht van begeleide scenario's
titleSuffix: Microsoft Intune
description: Lees meer over de begeleide scenario's voor Intune-die beschikbaar zijn in de portal voor Microsoft 365-apparaatbeheer.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ebb17324355fff9631ef74a76388ef0ab797d437
ms.sourcegitcommit: 7cc45ef52dda08479bc6bdff7d11d2f6c0e7b93b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/06/2019
ms.locfileid: "74899133"
---
# <a name="intune-guided-scenarios-overview"></a>Overzicht van begeleide scenario's voor Intune 

Een begeleid scenario is een aangepaste reeks stappen rondom een end-to-end-use-case. Algemene scenario's zijn gebaseerd op de rol die een beheerder, gebruiker of apparaat in uw organisatie speelt. Voor deze rollen is doorgaans een verzameling zorgvuldig gegroepeerde profielen, instellingen, toepassingen en beveiligingsmechanismen vereist om de beste gebruikerservaring en beveiliging te kunnen bieden.    

Als u niet bekend bent met alle stappen en resources die vereist zijn om een bepaald scenario voor Intune te implementeren, kunt u begeleide scenario's als uitgangspunt gebruiken. Met behulp van het begeleide scenario worden beleidsregels, apps, toewijzingen en andere beheerconfiguraties automatisch samengesteld. Daarnaast worden in de begeleide scenario's specifieke opties die niet van toepassing zijn of ongebruikelijk zijn voor het gegeven scenario, soms overgeslagen. 

Begeleide scenario's zijn als beheerruimte niet anders dan de reguliere werkstromen van Intune. Deze werkstromen zijn bedoeld om te worden gebruikt in combinatie met de bestaande werkstromen van Intune voor profielen, apps en beleidsregels. Nadat een begeleid scenario is voltooid, moet in de toekomst alle beheer in het kader van dit scenario plaatsvinden via de bestaande menu's voor beleidsregels, apps en profielen. Bij een begeleid scenario wordt het resourcetype 'begeleid scenario' niet opgeslagen. Ook worden er geen toekomstige wijzigingen van de resources bijgehouden. Elke resource die met een begeleid scenario wordt gemaakt, wordt weergegeven in de respectievelijke workload ervan. Alle opties, zelfs de opties die in het begeleide scenario worden overgeslagen, kunnen worden bewerkt via de bestaande menu's.  

## <a name="types-of-guided-scenarios"></a>Typen begeleide scenario's 

Om het eenvoudig te houden, maken complexe bereikfuncties zoals bereiktags, groepen die zijn uitgesloten en toewijzingen van virtuele groepen geen deel uit van begeleide scenario's. Alle resources die zijn gemaakt met behulp van een begeleid scenario, nemen elke bereiktag van de beheerder die het scenario uitvoert, over. Bepaalde scenario's bieden de mogelijkheid om algemene instellingen enigszins aan te passen zodat ze voor nauw verwante scenario's kunnen worden gebruikt. Door deze scenario's wordt alleen het gebruik van groepstoewijzingen aan insluitingsgroepen ondersteund. Voor andere begeleide scenario's geldt dat er een gegarandeerd consistente ervaring wordt geboden door geen mogelijkheid tot aanpassing te bieden, en wordt er automatisch een nieuwe groep gegenereerd die alle toewijzingen ontvangt. Zodra het begeleide scenario is voltooid, hebt u de mogelijkheid om rechtstreeks geavanceerdere toewijzingen te maken via bestaande workloads voor beleidsregels, apps en profielen.  

De volgende scenario's zijn begeleide scenario's: 
- Microsoft Edge voor mobiel implementeren 
- Een in de cloud beheerde pc proberen
- Veilige Microsoft Office voor mobiel 

## <a name="guided-scenario-functionality"></a>Functionaliteit voor begeleid scenario 

Begeleide scenario's bieden specifieke functionaliteit. Hier volgt een uitleg over wat u wel en niet kunt doen als u een begeleid scenario uitvoert.

### <a name="launching"></a>Starten  

Alle begeleide scenario's zijn beschikbaar via de **[portal voor apparaatbeheer](https://devicemanagement.microsoft.com)**  > **Probleemoplossing en ondersteuning** > **Begeleide scenario's**. 

Het begeleide scenario begint met een inleiding waarin wordt uitgelegd wat het doel is van het scenario en aan welke vereisten moet worden voldaan om de installatie te kunnen voltooien. Dit is het punt waarop wordt gecontroleerd of u met uw beheerdersmachtigingen de vereiste bevoegdheden hebt om het scenario te voltooien.  

Nadat alle vereisten zijn gecontroleerd en goedgekeurd, biedt het scenario voldoende instellingen waarmee u aanpassingen kunt uitvoeren. Bij begeleide scenario's gaat het erom dat er bij zo weinig mogelijk instellingen invoer wordt vereist, en tevens worden minder gebruikelijke of geavanceerde instellingen verborgen totdat ze nodig zijn of totdat er zich speciale omstandigheden voordoen. Elk begeleid scenario bevat koppelingen naar documentatie met aanvullende informatie. 

Nadat alle verplichte instellingen zijn ingevoerd, geeft het begeleide scenario een samenvatting van de opgegeven instellingen en van de resources die voor het scenario zijn vereist. Op dit moment is niets opgeslagen, tenzij expliciet vermeld.

De volgende stap is het implementeren van het scenario. Als u een scenario implementeert, worden alle benodigde resources en geselecteerde instellingen gemaakt en opgeslagen. De tijd die nodig is om een implementatie te voltooien, varieert per scenario. Zodra de implementatie is voltooid, wordt in het begeleide scenario een lijst weergegeven met de gemaakte resources, met koppelingen naar de beheerweergave van elke resource, de normale workload van de resource en de documentatie. 

> [!IMPORTANT]
> De lijst die aan het einde van het begeleide scenario wordt weergegeven, wordt niet opgeslagen en is alleen zichtbaar wanneer het begeleide scenario is geopend.  
Als er een fout optreedt bij het implementeren van het scenario, worden alle wijzigingen ongedaan gemaakt. 

### <a name="editing"></a>Bewerken 

Begeleide scenario's kunnen niet worden gebruikt om bestaande resources te bewerken. Nadat u resources hebt gemaakt, moeten alle resources, groepen en toewijzingen worden bewerkt met behulp van de bestaande workloads.

### <a name="monitoring"></a>Controleren 

Begeleide scenario's kunnen niet worden gebruikt voor het bewaken van bestaande resources, met uitzondering van het eerste proces waarbij een resource wordt gemaakt. Nadat u resources hebt gemaakt, moeten alle resources, groepen en toewijzingen worden bewaakt met behulp van de bestaande workloads. 

### <a name="retiring"></a>Buiten gebruik stellen 

Begeleide scenario's kunnen niet worden gebruikt voor het buiten gebruik stellen van bestaande resources, behalve bij het automatisch opschonen tijdens een fout bij de eerste implementatie. Nadat u resources hebt gemaakt, moeten alle resources, groepen en toewijzingen buiten gebruik worden gesteld met behulp van de bestaande workloads. 

### <a name="updating"></a>Bijwerken

Naarmate technologie zich ontwikkelt, wordt er met Intune van tijd tot tijd een begeleid scenario bijgewerkt om de gebruikerservaring, de beveiliging of andere aspecten van het scenario te verbeteren. Deze update is alleen van invloed op nieuwe implementaties die zijn gemaakt met behulp van het begeleide scenario. Met Intune worden bestaande resources die eerder door het begeleide scenario zijn gegenereerd, niet bijgewerkt, zodat deze overeenkomen met nieuwe aanbevolen procedures of aanbevelingen.  

## <a name="next-steps"></a>Volgende stappen

Als u snel met Microsoft Intune aan de slag wilt, wordt aanbevolen de stapsgewijze instructies in de begeleide scenario's voor Intune te volgen. Als u niet bekend bent met Intune, kunt u uw Intune-tenant instellen door de [quickstart voor de gratis proefversie](free-trial-sign-up.md) te volgen.
