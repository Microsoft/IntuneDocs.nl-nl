---
title: Netwerkvereisten en bandbreedtedetails voor Microsoft Intune
titleSuffix: ''
description: Bekijk netwerkconfiguratievereisten en bandbreedtedetails voor Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/03/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 40f9ada715570de7b5b2f95292b7ed0d238242d2
ms.sourcegitcommit: 04d29d47b61486b3586a0e0e5e8e48762351f2a3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/11/2019
ms.locfileid: "59570790"
---
# <a name="intune-network-configuration-requirements-and-bandwidth"></a>Netwerkconfiguratievereisten en bandbreedte voor Intune

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

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

Zie [Background Intelligent Transfer Service](http://technet.microsoft.com/library/bb968799.aspx) in de TechNet-bibliotheek voor meer informatie over BITS en Windows-computers.

### <a name="use-branchcache-on-computers"></a>BranchCache gebruiken op computers
Intune-clients kunnen BranchCache gebruiken om WAN-verkeer (Wide Area Network) te beperken. De volgende besturingssystemen ondersteunen BranchCache:

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

Als u BranchCache wilt gebruiken, moet BranchCache op de clientcomputer zijn ingeschakeld en moet de computer zijn geconfigureerd voor de **modus Gedistribueerde cache**.

Wanneer de Intune-client is geïnstalleerd op computers, worden BranchCache en de modus Gedistribueerde cache standaard ingeschakeld. Als BranchCache echter is uitgeschakeld door groepsbeleid, overschrijft Intune dat beleid niet en blijft BranchCache uitgeschakeld.

Als u BranchCache gebruikt, moet u samenwerken met andere beheerders in uw organisatie die het groepsbeleid en het beleid voor de Intune Firewall beheren. Zorg ervoor dat zij geen beleid implementeren waarmee BranchCache of Firewall-uitzonderingen worden uitgeschakeld. Zie [Overzicht van BranchCache](http://technet.microsoft.com/library/hh831696.aspx) voor meer informatie over BranchCache.

## <a name="network-communication-requirements"></a>Vereisten voor netwerkcommunicatie

Schakel netwerkcommunicatie in tussen de apparaten die u beheert en de eindpunten die zijn vereist voor cloudservices.

Intune is een service die zich alleen in de cloud bevindt, en hiervoor is geen on-premises infrastructuur, zoals servers of gateways, vereist.

Als u apparaten wilt beheren die zich achter firewalls en proxyservers bevinden, moet u communicatie voor Intune inschakelen.

- De proxyserver moet zowel **HTTP (80)** als **HTTPS (443)** ondersteunen omdat Intune-clients beide protocollen gebruiken
- Voor bepaalde taken, zoals het downloaden van software en updates, is in Intune niet-geverifieerde proxyservertoegang vereist tot manage.microsoft.com

U kunt de instellingen voor proxyservers wijzigen op afzonderlijke clientcomputers. U kunt ook de instellingen voor groepsbeleid gebruiken om de instellingen te wijzigen voor alle clientcomputers die zich achter een bepaalde proxyserver bevinden.


<!--
> [!NOTE] If Windows 8.1 devices haven't cached proxy server credentials, enrollment might fail because the request doesn't prompt for credentials. Enrollment fails without warning as the request wait for a connection. If users might experience this issue, instruct them to open their browser settings and save proxy server settings to enable a connection.   -->

Voor beheerde apparaten zijn configuraties vereist waarmee **alle gebruikers** via firewalls toegang krijgen tot services.

De volgende tabel bevat de poorten en services waartoe de Intune-client toegang heeft:

|**Domeinen**|**IP-adres**|
|---------------------|-----------|
|login.microsoftonline.com | Meer informatie [Office 365-URL's en IP-adresbereiken](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) |
|portal.manage.microsoft.com<br> m.manage.microsoft.com |52.175.12.209<br>20.188.107.228<br>52.138.193.149<br>51.144.161.187<br>52.160.70.20<br>52.168.54.64 |
| sts.manage.microsoft.com | 13.93.223.241 <br>52.170.32.182 <br>52.164.224.159 <br>52.174.178.4 <br>13.75.122.143 <br>52.163.120.84|
|Manage.microsoft.com <br>i.manage.microsoft.com <br>r.manage.microsoft.com <br>a.manage.microsoft.com <br>p.manage.microsoft.com <br>EnterpriseEnrollment.manage.microsoft.com <br>EnterpriseEnrollment-s.manage.microsoft.com | 40.83.123.72<br>13.76.177.110<br>52.169.9.87<br>52.174.26.23<br>104.40.82.191<br>13.82.96.212|
|fei.msua01.manage.microsoft.com<br>portal.fei.msua01.manage.microsoft.com <br>m.fei.msua01.manage.microsoft.com<br>fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com<br>fei.msua04.manage.microsoft.com<br>portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com<br>fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com<br>fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com<br>fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com<br>fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com<br>fei.amsua0202.manage.microsoft.com <br>portal.fei.amsua0202.manage.microsoft.com <br>m.fei.amsua0202.manage.microsoft.com<br>fei.amsua0402.manage.microsoft.com <br>portal.fei.amsua0402.manage.microsoft.com <br>m.fei.amsua0402.manage.microsoft.com|52.160.70.20<br>52.168.54.64 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com<br>fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com<br>fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com<br>fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com<br>fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com<br>fei.amsub0202.manage.microsoft.com <br>portal.fei.amsub0202.manage.microsoft.com <br>m.fei.amsub0202.manage.microsoft.com<br>fei.amsub0302.manage.microsoft.com <br>portal.fei.amsub0302.manage.microsoft.com <br>m.fei.amsub0302.manage.microsoft.com|52.138.193.149<br>51.144.161.187|
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com<br>fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com<br>fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com<br>fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com|52.175.12.209<br>20.188.107.228|
|fef.msua01.manage.microsoft.com|138.91.243.97|
|fef.msua02.manage.microsoft.com|52.177.194.236|
|fef.msua04.manage.microsoft.com|23.96.112.28|
|fef.msua05.manage.microsoft.com|138.91.244.151|
|fef.msua06.manage.microsoft.com|13.78.185.97|
|fef.msua07.manage.microsoft.com|52.175.208.218|
|fef.msub01.manage.microsoft.com|137.135.128.214|
|fef.msub02.manage.microsoft.com|137.135.130.29|
|fef.msub03.manage.microsoft.com|52.169.82.238|
|fef.msub05.manage.microsoft.com|23.97.166.52|
|fef.msuc01.manage.microsoft.com|52.230.19.86|
|fef.msuc02.manage.microsoft.com|23.98.66.118|
|fef.msuc03.manage.microsoft.com|23.101.0.100|
|fef.msuc05.manage.microsoft.com|52.230.16.180|
|fef.amsua0202.manage.microsoft.com|52.165.165.17|
|fef.amsua0402.manage.microsoft.com|40.69.157.122|
|fef.amsua0502.manage.microsoft.com|13.85.68.142|
|fef.amsua0602.manage.microsoft.com|52.161.28.64|
|fef.amsub0102.manage.microsoft.com|40.118.98.207|
|fef.amsub0202.manage.microsoft.com|40.69.208.122|
|fef.amsub0302.manage.microsoft.com|13.74.145.65|
|enterpriseregistration.windows.net|52.175.211.189|
|Admin.manage.microsoft.com|52.224.221.227<br>52.161.162.117<br>52.178.44.195<br>52.138.206.56<br>52.230.21.208<br>13.75.125.10|
|wip.mam.manage.microsoft.com|52.187.76.84<br>13.76.5.121<br>52.165.160.237<br>40.86.82.163<br>52.233.168.142<br>168.63.101.57|
|mam.manage.microsoft.com|104.40.69.125<br>13.90.192.78<br>40.85.174.177<br>40.85.77.31<br>137.116.229.43<br>52.163.215.232<br>52.174.102.180|






### <a name="apple-device-network-information"></a>Netwerkgegevens voor Apple-apparaten


|Gebruikt voor|Hostnaam (IP-adres/subnet)|Protocol|Poort|
|-----|--------|------|-------|
|Ontvangen van pushmeldingen van de Intune-service via de APNS (Apple Push Notification Service). Zie [hier](https://support.apple.com/en-us/HT203609) de documentatie van Apple|                                    gateway.push.apple.com (17.0.0.0/8)                                  |    TCP     |     2195     |
|Feedback verzenden naar de Intune-service via de APNS (Apple Push Notification Service)|                                  feedback.push.apple.com(17.0.0.0/8)                                  |    TCP     |     2196     |
|Inhoud van Apple-servers ophalen en weergeven|itunes.apple.com<br>\*.itunes.apple.com<br>\*.mzstatic.com<br>\*.phobos.apple.com<br> \*.phobos.itunes-apple.com.akadns.net |    HTTP    |      80      |
|Communicatie met APNS-servers|#-courier.push.apple.com (17.0.0.0/8)<br># is een willekeurig getal van 0 tot en met 50.|    TCP     |  5223 en 443  |
|Verschillende functies waaronder toegang tot internet, de iTunes Store, de MacOS App Store, iCloud, berichten, enzovoort. |phobos.apple.com<br>ocsp.apple.com<br>ax.itunes.apple.com<br>ax.itunes.apple.com.edgesuite.net| HTTP/HTTPS |  80 of 443   |

Zie voor meer informatie de documentatie van Apple: [TCP and UDP ports used by Apple software products](https://support.apple.com/en-us/HT202944) (TCP- en UDP-poorten die worden gebruikt voor Apple-softwareproducten), [About macOS, iOS, and iTunes server host connections and iTunes background processes](https://support.apple.com/en-us/HT201999) (Over serververbindingen van macOS-, iOS- en iTunes-hosts, en iTunes-achtergrondprocessen), en [If your macOS and iOS clients aren't getting Apple push notifications](https://support.apple.com/en-us/HT203609) (Als uw macOS- en iOS-clients geen Apple-pushmeldingen ontvangen.
