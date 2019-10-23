---
title: Netwerkvereisten en bandbreedtedetails voor Microsoft Intune
titleSuffix: ''
description: Bekijk netwerkconfiguratievereisten en bandbreedtedetails voor Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/17/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: kerimh
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4a3ecf2872832af6199620863a05b4275731db5c
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72505247"
---
# <a name="intune-network-configuration-requirements-and-bandwidth"></a>Netwerkconfiguratievereisten en bandbreedte voor Intune

[!INCLUDE [both-portals](../../intune-classic/includes/note-for-both-portals.md)]

U kunt deze informatie gebruiken om inzicht te krijgen in de bandbreedtevereisten voor uw Intune-implementaties.

## <a name="average-network-traffic"></a>Gemiddeld netwerkverkeer
Deze tabel bevat de geschatte grootte en frequentie van algemene inhoud die via het netwerk voor elke client wordt verzonden.

> [!NOTE]
> Om ervoor te zorgen dat apparaten de updates en inhoud van Intune ontvangen, moeten ze regelmatig verbinding maken met internet. Hoeveel tijd het kost om updates of inhoud te ontvangen verschilt, maar ze moeten ten minste 1 uur per dag continu met internet verbonden zijn.

|Type inhoud|Geschatte grootte|Frequentie en details|
|----------------|--------------------|-------------------------|
|Intune-clientinstallatie<br /><br />**Voor de Intune-clientinstallatie gelden de volgende aanvullende vereisten**|125 MB|**Eén keer**<br /><br />De grootte van de clientdownload is afhankelijk van het besturingssysteem van de clientcomputer.|
|Clientinschrijvingspakket|15 MB|**Eén keer**<br /><br />Meer downloads zijn mogelijk als er updates voor dit type inhoud zijn.|
|Endpoint Protection-agent|65 MB|**Eén keer**<br /><br />Meer downloads zijn mogelijk als er updates voor dit type inhoud zijn.|
|Operations Manager-agent|11 MB|**Eén keer**<br /><br />Meer downloads zijn mogelijk als er updates voor dit type inhoud zijn.|
|Beleidsagent|3 MB|**Eén keer**<br /><br />Meer downloads zijn mogelijk als er updates voor dit type inhoud zijn.|
|Hulp op afstand via Microsoft Easy Assist-agent|6 MB|**Eén keer**<br /><br />Meer downloads zijn mogelijk als er updates voor dit type inhoud zijn.|
|Dagelijkse clientbewerkingen|6 MB|**Dagelijks**<br /><br />De Intune-client communiceert regelmatig met de Intune-service om op updates en beleid te controleren en om de status van de client aan de service te rapporteren.|
|Updates van Endpoint Protection-malwaredefinities|Varieert<br /><br />Meestal 40 kB tot 2 MB|**Dagelijks**<br /><br />Maximaal drie keer per dag.|
|Endpoint Protection-engine-update|5 MB|**Maandelijks**|
|Software-updates|Varieert<br /><br />De grootte is afhankelijk van de updates die u wilt implementeren.|**Maandelijks**<br /><br />Software-updates worden meestal op de tweede dinsdag van elke maand uitgebracht.<br /><br />Een nieuw ingeschreven of geïmplementeerde computer kan meer netwerkbandbreedte gebruiken tijdens het downloaden van de volledige set eerder uitgebrachte updates.|
|Servicepacks|Varieert<br /><br />De grootte varieert voor elke servicepack die u implementeert.|**Varieert**<br /><br />Is afhankelijk van wanneer u servicepacks implementeert.|
|Softwaredistributie|Varieert<br /><br />De grootte is afhankelijk van de software die u wilt implementeren.|**Varieert**<br /><br />Is afhankelijk van wanneer u software implementeert.|

## <a name="ways-to-reduce-network-bandwidth-use"></a>Manieren om het gebruik van netwerkbandbreedte te beperken
U kunt een of meer van de volgende methoden gebruiken om het gebruik van netwerkbandbreedte te beperken voor Intune-clients.

### <a name="use-a-proxy-server-to-cache-content-requests"></a>Een proxyserver gebruiken om aanvragen voor inhoud in cache te plaatsen
Een proxyserver kan inhoud in cache plaatsen om dubbele downloads te voorkomen, en de netwerkbandbreedte voor het downloaden van inhoud van internet te beperken.

Een cacheproxyserver die aanvragen voor inhoud ontvangt van clients, kan die inhoud ophalen en zowel webreacties als downloads in de cache plaatsen. De server gebruikt de gegevens in cache om de volgende aanvragen van clients te beantwoorden.

Hieronder vindt u standaardinstellingen voor een proxyserver die inhoud voor Intune-clients plaatst.


|          Instelling           |           Aanbevolen waarde           |                                                                                                  Details                                                                                                  |
|----------------------------|---------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         Cachegrootte         |             5 GB tot 30 GB             | De waarde is afhankelijk van het aantal clientcomputers in uw netwerk en de configuraties die u gebruikt. Pas de grootte van de cache voor uw omgeving aan om te voorkomen dat bestanden te snel worden verwijderd. |
| Grootte van afzonderlijke cachebestanden |                950 MB                 |                                                                     Deze instelling is mogelijk niet beschikbaar in alle cacheproxyservers.                                                                     |
|   Objecttypen die in cache worden geplaatst    | HTTP<br /><br />HTTPS<br /><br />BITS |                                               Intune-pakketten zijn CAB-bestanden die worden opgehaald door BITS-download (Background Intelligent Transfer Service) via HTTP.                                               |
> [!NOTE]
> Als u een proxyserver gebruikt om inhoudsaanvragen in de cache op te slaan, wordt alleen de communicatie versleuteld tussen de client en de proxy, en van de proxy naar Intune. De verbinding van de client naar Intune is dan niet end-to-end versleuteld.

Zie de documentatie voor uw proxyserver voor informatie over het gebruik van een proxyserver om inhoud in cache te plaatsen.

### <a name="use-background-intelligent-transfer-service-bits-on-computers"></a>BITS (Background Intelligent Transfer Service) gebruiken op computers
U kunt, tijdens de uren die u zelf configureert, BITS gebruiken op een Windows-computer om de netwerkbandbreedte te beperken. U kunt BITS-beleid configureren op de pagina **Netwerkbandbreedte** van het beleid van de Intune-agent.

> [!NOTE]
> Voor MDM-beheer in Windows maakt alleen de OS-beheerinterface voor het type MobileMSI-app gebruik van BITS om te downloaden. Voor AppX/MsiX wordt een systeemeigen niet-BITS-downloadstack gebruikt, en Win32-apps via de Intune-agent gebruiken Delivery Optimization, in plaats van BITS.

Zie [Background Intelligent Transfer Service](https://technet.microsoft.com/library/bb968799.aspx) in de TechNet-bibliotheek voor meer informatie over BITS en Windows-computers.

### <a name="delivery-optimization"></a>Delivery optimization
Met Delivery Optimization kunt u Intune gebruiken om het bandbreedteverbruik te verminderen wanneer toepassingen en updates worden gedownload naar uw Windows 10-apparaten. Door een zelf organiserende gedistribueerde cache te gebruiken, kunnen downloads worden opgehaald van traditionele servers en uit alternatieve bronnen (zoals netwerk-peers).

Raadpleeg het artikel [Delivery Optimization voor Windows 10-updates](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#requirements) voor een volledige lijst met Windows 10-versies en inhoudstypen die worden ondersteund voor Delivery Optimization.

U kunt [Delivery Optimization configureren](../configuration/delivery-optimization-settings.md) als onderdeel van uw apparaatconfiguratieprofielen.


### <a name="use-branchcache-on-computers"></a>BranchCache gebruiken op computers
Intune-clients kunnen BranchCache gebruiken om WAN-verkeer (Wide Area Network) te beperken. De volgende besturingssystemen ondersteunen BranchCache:

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

Als u BranchCache wilt gebruiken, moet BranchCache op de clientcomputer zijn ingeschakeld en moet de computer zijn geconfigureerd voor de **modus Gedistribueerde cache**.

Wanneer de Intune-client is geïnstalleerd op computers, worden BranchCache en de modus Gedistribueerde cache standaard ingeschakeld. Als BranchCache echter is uitgeschakeld door groepsbeleid, overschrijft Intune dat beleid niet en blijft BranchCache uitgeschakeld.

Als u BranchCache gebruikt, moet u samenwerken met andere beheerders in uw organisatie die het groepsbeleid en het beleid voor de Intune Firewall beheren. Zorg ervoor dat zij geen beleid implementeren waarmee BranchCache of Firewall-uitzonderingen worden uitgeschakeld. Zie [Overzicht van BranchCache](https://technet.microsoft.com/library/hh831696.aspx) voor meer informatie over BranchCache.

> [!NOTE]
> U kunt Microsoft Intune gebruiken voor het beheren van Windows-pc's als [mobiele apparaten met MDM (Mobile Device Management)](../enrollment/windows-enroll.md) of als computers met de Intune-softwareclient. Microsoft adviseert klanten om indien mogelijk [de MDM-beheeroplossing](../enrollment/windows-enroll.md) te gebruiken. Wanneer deze beheeroplossing wordt gebruikt, wordt BranchCache niet ondersteund. Raadpleeg [Beheer van Windows-pc's vergelijken als computers of mobiele apparaten](../pc-management-comparison.md) voor meer informatie.


## <a name="next-steps"></a>Volgende stappen

[Eindpunten voor Intune controleren](../intune-endpoints.md)

