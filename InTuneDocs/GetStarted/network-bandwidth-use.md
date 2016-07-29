---
title: Gebruik van netwerkbandbreedte | Microsoft Intune
description: gebruik van netwerkbandbreedte door intune
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2a192c71b1b82f59b34ea614d09d895174f8112b
ms.openlocfilehash: 2a600b7948c55a408314aedc3895c25fcc09251d


---

# Gebruik van netwerkbandbreedte door Intune

Lees voor de installatie van [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] dit onderwerp en de andere vereisten in [Wat u moet weten voordat u met Microsoft Intune aan de slag gaat](what-to-know-before-you-start-microsoft-intune.md).

Gebruik de informatie in de volgende gedeelten om te plannen voor het netwerkverkeer voor [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)]-clients.

## Gemiddeld netwerkverkeer
De volgende tabel bevat de geschatte grootte en frequentie van algemene inhoud die via het netwerk voor elke client wordt verzonden.

> [!NOTE]
> Om ervoor te zorgen dat computers en mobiele apparaten de vereiste updates en inhoud van de [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-service ontvangen, moeten ze regelmatig worden verbonden met internet. Hoeveel tijd het duurt om updates of inhoud te ontvangen verschilt, maar als uitgangspunt moeten ze ten minste 1 uur per dag continu met internet verbonden zijn.

|Type inhoud|Geschatte grootte|Frequentie en details|
|----------------|--------------------|-------------------------|
|[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] -clientinstallatie<br /><br />**Voor de [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-clientinstallatie gelden de volgende aanvullende vereisten**|125 MB|**Eén keer**<br /><br />De grootte van de clientdownload is afhankelijk van het besturingssysteem van de clientcomputer.|
|Clientinschrijvingspakket|15 MB|**Eén keer**<br /><br />Meer downloads zijn mogelijk als er updates voor dit type inhoud zijn.|
|Endpoint Protection-agent|65 MB|**Eén keer**<br /><br />Meer downloads zijn mogelijk als er updates voor dit type inhoud zijn.|
|Operations Manager-agent|11 MB|**Eén keer**<br /><br />Meer downloads zijn mogelijk als er updates voor dit type inhoud zijn.|
|Beleidsagent|3 MB|**Eén keer**<br /><br />Meer downloads zijn mogelijk als er updates voor dit type inhoud zijn.|
|Hulp op afstand via Microsoft Easy Assist-agent|6 MB|**Eén keer**<br /><br />Meer downloads zijn mogelijk als er updates voor dit type inhoud zijn.|
|Dagelijkse clientbewerkingen|6 MB|**Dagelijks**<br /><br />De [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-client communiceert regelmatig met de [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-service om op updates en beleid te controleren en om de status van de client aan de service te rapporteren.|
|Updates van Endpoint Protection-malwaredefinities|Varieert<br /><br />Meestal 40 kB tot 2 MB|**Dagelijks**<br /><br />Maximaal drie keer per dag.|
|Endpoint Protection-engine-update|5 MB|**Maandelijks**|
|Software-updates|Varieert<br /><br />De grootte is afhankelijk van de updates die u wilt implementeren.|**Maandelijks**<br /><br />Software-updates worden meestal op de tweede dinsdag van elke maand uitgebracht.<br /><br />Een nieuw ingeschreven of geïmplementeerde computer kan meer netwerkbandbreedte gebruiken tijdens het downloaden van de volledige set eerder uitgebrachte updates.|
|Servicepacks|Varieert<br /><br />De grootte varieert voor elke servicepack die u implementeert.|**Varieert**<br /><br />Is afhankelijk van wanneer u servicepacks implementeert.|
|Softwaredistributie|Varieert<br /><br />De grootte is afhankelijk van de software die u wilt implementeren.|**Varieert**<br /><br />Is afhankelijk van wanneer u software implementeert.|

## Manieren om het gebruik van netwerkbandbreedte te beperken
U kunt een of meer van de volgende methoden gebruiken om het gebruik van netwerkbandbreedte te beperken voor [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-clients.

### Een proxyserver gebruiken om aanvragen voor inhoud in cache te plaatsen
U kunt een proxyserver gebruiken om inhoud in cache te plaatsen zodat dubbele downloads worden verminderd, en om het gebruik te beperken van de netwerkbandbreedte die clients nodig hebben om inhoud van internet aan te vragen.

Een cacheproxyserver ontvangt verzoeken voor inhoud van clientcomputers in uw netwerk, haalt die inhoud op van internet en plaatst vervolgens zowel HTTP-antwoorden als binaire downloads in cache. De server gebruikt de gegevens in cache om de volgende aanvragen van [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-clientcomputers te beantwoorden.

Hieronder vindt u standaardinstellingen voor een proxyserver die inhoud voor [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-clients plaatst.

|Instelling|Aanbevolen waarde|Details|
|-----------|---------------------|-----------|
|Cachegrootte|5 GB tot 30 GB|De waarde is afhankelijk van het aantal clientcomputers in uw netwerk en de configuraties die u gebruikt. Pas de grootte van de cache voor uw omgeving aan om te voorkomen dat bestanden te snel worden verwijderd.|
|Grootte van afzonderlijke cachebestanden|950 MB|Deze instelling is mogelijk niet beschikbaar in alle cacheproxyservers.|
|Objecttypen die in cache worden geplaatst|HTTP<br /><br />HTTPS<br /><br />BITS|[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] -pakketten zijn CAB-bestanden die worden opgehaald door BITS-download (Background Intelligent Transfer Service) via HTTP.|
Zie de documentatie voor uw proxyserver voor informatie over het gebruik van een proxyserver om inhoud in cache te plaatsen.

### Background Intelligent Transfer Service op computers gebruiken
[!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] ondersteunt het gebruik van Background Intelligent Transfer Service (BITS) op een Windows-computer om de netwerkbandbreedte te beperken die wordt gebruikt tijdens de uren dat u configureert. U kunt beleid voor BITS configureren op de pagina **Netwerkbandbreedte** van het beleid van de [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-agent.

Zie [Background Intelligent Transfer Service](http://technet.microsoft.com/library/bb968799.aspx) in de TechNet-bibliotheek voor meer informatie over BITS en Windows-computers.

### BranchCache gebruiken op computers
[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] -clients kunnen BranchCache gebruiken om WAN-verkeer (Wide Area Network) te beperken. De volgende besturingssystemen die worden ondersteund als client, bieden ook ondersteuning voor BranchCache:

-   [!INCLUDE[nextref_client_7](../includes/nextref_client_7_md.md)]

-   [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)]

-   [!INCLUDE[winblue_client_2](../includes/winblue_client_2_md.md)]

Als u BranchCache wilt gebruiken, moet BranchCache op de clientcomputer zijn ingeschakeld en moet de computer zijn geconfigureerd voor de **modus Gedistribueerde cache**.

BranchCache en de modus voor gedistribueerde cache zijn standaard ingeschakeld op een computer als de [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-client is geïnstalleerd. Als de client echter al groepsbeleid heeft waarmee BranchCache wordt uitgeschakeld, wordt dat beleid niet door [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] overschreven en blijft BranchCache uitgeschakeld op die computer.

Als u BranchCache gebruikt, moet u contact opnemen met andere beheerders in uw organisatie die groepsbeleid en het beleid voor de [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] Firewall beheren om ervoor te zorgen dat zij geen beleid implementeren waarmee BranchCache of Firewall-uitzonderingen worden uitgeschakeld. Zie [Overzicht van BranchCache](http://technet.microsoft.com/library/hh831696.aspx) voor meer informatie over BranchCache.

### Zie tevens
[Wat u moet weten voordat u met Microsoft Intune aan de slag gaat](what-to-know-before-you-start-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


