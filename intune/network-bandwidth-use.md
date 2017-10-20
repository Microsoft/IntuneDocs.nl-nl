---
title: Gebruik van netwerkbandbreedte door Intune
description: gebruik van netwerkbandbreedte door intune
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: angerobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d68cbb05025e89e256a22dc88f5c4ee2afc3c536
ms.sourcegitcommit: db7a7bbead3a3fa78c4d643607f709a2909eb608
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2017
---
# <a name="intune-network-bandwidth-use"></a>Gebruik van netwerkbandbreedte door Intune

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Deze richtlijnen geven Intune-beheerders inzicht in de netwerkvereisten voor de Intune-service. U kunt deze informatie gebruiken voor meer inzicht in de bandbreedtevereisten, het IP-adres en de vereiste poortinstellingen voor proxy-instellingen.

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

|Instelling|Aanbevolen waarde|Details|
|-----------|---------------------|-----------|
|Cachegrootte|5 GB tot 30 GB|De waarde is afhankelijk van het aantal clientcomputers in uw netwerk en de configuraties die u gebruikt. Pas de grootte van de cache voor uw omgeving aan om te voorkomen dat bestanden te snel worden verwijderd.|
|Grootte van afzonderlijke cachebestanden|950 MB|Deze instelling is mogelijk niet beschikbaar in alle cacheproxyservers.|
|Objecttypen die in cache worden geplaatst|HTTP<br /><br />HTTPS<br /><br />BITS|Intune-pakketten zijn CAB-bestanden die worden opgehaald door BITS-download (Background Intelligent Transfer Service) via HTTP.|
Zie de documentatie voor uw proxyserver voor informatie over het gebruik van een proxyserver om inhoud in cache te plaatsen.

### <a name="use-background-intelligent-transfer-service-on-computers"></a>Background Intelligent Transfer Service op computers gebruiken
Intune ondersteunt het gebruik van Background Intelligent Transfer Service (BITS) op een Windows-computer om de netwerkbandbreedte te beperken die wordt gebruikt tijdens de uren die u configureert. U kunt beleid voor BITS configureren op de pagina **Netwerkbandbreedte** van het beleid van de Intune-agent.

Zie [Background Intelligent Transfer Service](http://technet.microsoft.com/library/bb968799.aspx) in de TechNet-bibliotheek voor meer informatie over BITS en Windows-computers.

### <a name="use-branchcache-on-computers"></a>BranchCache gebruiken op computers
Intune-clients kunnen BranchCache gebruiken om WAN-verkeer (Wide Area Network) te beperken. De volgende besturingssystemen ondersteunen BranchCache:

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

Als u BranchCache wilt gebruiken, moet BranchCache op de clientcomputer zijn ingeschakeld en moet de computer zijn geconfigureerd voor de **modus Gedistribueerde cache**.

BranchCache en de modus voor gedistribueerde cache zijn standaard ingeschakeld op computers als de Intune-client is geïnstalleerd. Als BranchCache echter is uitgeschakeld door groepsbeleid, overschrijft Intune dat beleid niet en blijft BranchCache uitgeschakeld.

Als u BranchCache gebruikt, moet u samenwerken met andere beheerders in uw organisatie die het groepsbeleid en het beleid voor de Intune Firewall beheren. Zorg ervoor dat zij geen beleid implementeren waarmee BranchCache of Firewall-uitzonderingen worden uitgeschakeld. Zie [Overzicht van BranchCache](http://technet.microsoft.com/library/hh831696.aspx) voor meer informatie over BranchCache.

## <a name="network-communication-requirements"></a>Vereisten voor netwerkcommunicatie

Schakel netwerkcommunicatie in tussen de apparaten die u beheert en de websites die vereist zijn voor cloudservices.

Intune gebruikt geen on-premises infrastructuur, zoals servers waarop Intune wordt uitgevoerd, maar u hebt de mogelijkheid om on-premises infrastructuur te gebruiken, waaronder de hulpprogramma's voor Exchange- en Active Directory-synchronisatie.

Als u computers wilt beheren die zich achter firewalls en proxyservers bevinden, moet u communicatie voor Intune inschakelen.

-   De proxyserver moet zowel **HTTP (80)** als **HTTPS (443)** ondersteunen omdat Intune-clients beide protocollen gebruiken
-   Intune vereist niet-geverifieerde proxyservertoegang tot manage.microsoft.com voor bepaalde taken, zoals het downloaden van software en updates

U kunt instellingen voor de proxyserver op afzonderlijke clientcomputers wijzigen of u kunt instellingen voor Groepsbeleid gebruiken om de instellingen te wijzigen voor alle clientcomputers die zich achter een bepaalde proxyserver bevinden.


<!--
> [!NOTE] If Windows 8.1 devices haven't cached proxy server credentials, enrollment might fail because the request doesn't prompt for credentials. Enrollment fails without warning as the request wait for a connection. If users might experience this issue, instruct them to open their browser settings and save proxy server settings to enable a connection.   -->

Voor beheerde apparaten zijn configuraties vereist waarmee **alle gebruikers** via firewalls toegang krijgen tot services.

De volgende tabel bevat de poorten en services waartoe de Intune-client toegang heeft:

|**Domeinen**|**IP-adres**|
|---------------------|-----------|
|portal.manage.microsoft.com<br> m.manage.microsoft.com |40.86.181.86<br>13.82.59.78<br>13.74.184.100<br>40.68.188.2<br>13.75.42.6<br>52.230.25.184 |
| sts.manage.microsoft.com | 13.93.223.241 <br>52.170.32.182 <br>52.164.224.159 <br>52.174.178.4 <br>13.75.122.143 <br>52.163.120.84|
|Manage.microsoft.com <br>i.manage.microsoft.com <br>r.manage.microsoft.com <br>a.manage.microsoft.com <br>p.manage.microsoft.com <br>EnterpriseEnrollment.manage.microsoft.com <br>EnterpriseEnrollment-s.manage.microsoft.com | 104.40.82.191 <br>13.82.96.212 <br>52.169.9.87 <br>52.174.26.23 <br>40.83.123.72 <br>13.76.177.110 |
|portal.fei.msua01.manage.microsoft.com<br>m.fei.msua01.manage.microsoft.com |13.64.196.170|
|fei.msua01.manage.microsoft.com<br> portal.fei.msua01.manage.microsoft.com <br>m.fei.msua01.manage.microsoft.com |40.71.34.120 |
|fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com |13.64.198.190|
|fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br> m.fei.msua02.manage.microsoft.com |  13.64.198.190|
|fei.msua04.manage.microsoft.com<br> portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com |13.64.188.173|
|fei.msua04.manage.microsoft.com<br> portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com |40.71.32.174|
|fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com |13.64.197.181 |
|fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com |40.71.38.205|
|fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com |13.64.191.182 |
|fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com |40.71.37.51 |
|fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com |40.118.250.246 |
|fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com |13.90.142.194 |
|fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com |13.64.250.226 |
|fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com |13.90.151.142 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com |52.169.155.165 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com |52.174.188.97 |
|fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com |52.178.190.24 |
|fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com |52.174.16.215 |
|fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com |40.69.69.27 |
|fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com |52.166.196.199 |
|fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com |40.69.71.164 |
|fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com |52.174.182.102 |
|fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com |40.69.78.145 |
|fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com |52.174.192.105 |
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com |13.94.46.250|
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com |52.163.119.15 |
|fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com |13.75.124.145 |
|fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com |52.163.119.5|
|fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com |52.175.35.226|
|fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com |52.163.119.6|
|fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com |52.175.38.24|
|fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com |52.163.119.3|
|fef.msua01.manage.microsoft.com|138.91.243.97|
|fef.msua02.manage.microsoft.com|52.177.194.236|
|fef.msua04.manage.microsoft.com|23.96.112.28|
|fef.msua05.manage.microsoft.com|138.91.244.151|
|fef.msua06.manage.microsoft.com|13.78.185.97|
|fef.msua07.manage.microsoft.com|52.175.208.218|
|fef.msub01.manage.microsoft.com|137.135.128.214|
|fef.msub02.manage.microsoft.com|137.135.130.29|
|fef.msub03.manage.microsoft.com|23.97.165.17|
|fef.msub05.manage.microsoft.com|23.97.166.52|
|fef.msuc01.manage.microsoft.com|52.230.19.86|
|fef.msuc02.manage.microsoft.com|23.98.66.118|
|fef.msuc03.manage.microsoft.com|23.101.0.100|
|fef.msuc05.manage.microsoft.com|52.230.16.180|

### <a name="apple-device-network-information"></a>Netwerkgegevens voor Apple-apparaten
| Hostnaam  | URL (IP-adres/subnet) | Protocol | Poort | Apparaat |
| --- | --- | --- | --- | --- |
|  Beheerconsole  | gateway.push.apple.com (17.0.0.0/8) | TCP | 2195 | Apple iOS en macOS |
| Beheerconsole  | feedback.push.apple.com(17.0.0.0/8) | TCP | 2196 | Apple iOS en macOS |
| Beheerconsole  | Apple iTunesitunes.apple.com, \*.mzstatic.com, \*.phobos.apple.com, \*.phobos.apple.com.edgesuite.net | HTTP | 80 | Apple iOS en macOS  |
| PI-server  | gateway.push.apple.com(17.0.0.0/8) feedback.push.apple.com(17.0.0.0/8) | TCP | 2195, 2196 | Voor Apple iOS- en Mac OS-cloudmessaging. |
| Apparaatservices  | gateway.push.apple.com | TCP | 2195 | Apple  |
| Apparaatservices  | feedback.push.apple.com | TCP | 2196 | Apple  |
| Apparaatservices  | Apple iTunesitunes.apple.com \*.mzstatic.com\*.phobos.apple.com \*.phobos.apple.com.edgesuite.net | HTTP | 80 | Apple  |
| Apparaten (internet/Wi-Fi) | #-courier.push.apple.com(17.0.0.0/8) | TCP | 5223 en 443 | Alleen Apple. &#39;#&#39; is een willekeurig getal van 0 tot 200. |
| Apparaten (internet/Wi-Fi) | phobos.apple.comocsp.apple.comax.itunes.apple.com | HTTP/HTTPS | 80 of 443 | Alleen Apple |
