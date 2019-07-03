---
title: Netwerkeindpunten voor Microsoft Intune
titleSuffix: ''
description: Lees de tekst over eindpunten voor Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 026536b1f0c059808220273ccffefacc28b80ae0
ms.sourcegitcommit: 119962948045079022aa48f968dde3e961d7cd0c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/12/2019
ms.locfileid: "67031608"
---
# <a name="network-endpoints-for-microsoft-intune"></a>Netwerkeindpunten voor Microsoft Intune

Op deze pagina worden de IP-adressen en poortinstellingen vermeld die nodig zijn voor de proxy-instellingen in uw Intune-implementaties.

Intune is een service die zich alleen in de cloud bevindt, en hiervoor is geen on-premises infrastructuur, zoals servers of gateways, vereist.

Als u apparaten wilt beheren die zich achter firewalls en proxyservers bevinden, moet u communicatie voor Intune inschakelen.

- De proxyserver moet zowel **HTTP (80)** als **HTTPS (443)** ondersteunen omdat Intune-clients beide protocollen gebruiken. Windows Information Protection gebruikt poort 444.
- Voor bepaalde taken, zoals het downloaden van software-updates voor de klassieke pc-agent, is in Intune niet-geverifieerde proxyservertoegang vereist tot manage.microsoft.com

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
|portal.fei.msua01.manage.microsoft.com <br>m.fei.msua01.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com<br>portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com<br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com<br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com<br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com<br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com<br>fei.amsua0202.manage.microsoft.com <br>portal.fei.amsua0202.manage.microsoft.com <br>m.fei.amsua0202.manage.microsoft.com<br>portal.fei.amsua0402.manage.microsoft.com <br>m.fei.amsua0402.manage.microsoft.com|52.160.70.20<br>52.168.54.64 |
|portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com<br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com<br>fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com<br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com<br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com<br>portal.fei.amsub0202.manage.microsoft.com <br>m.fei.amsub0202.manage.microsoft.com<br>portal.fei.amsub0302.manage.microsoft.com <br>m.fei.amsub0302.manage.microsoft.com|52.138.193.149<br>51.144.161.187|
|portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com<br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com<br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com<br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com|52.175.12.209<br>20.188.107.228|
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


### <a name="network-requirements-for-powershell-scripts-and-win32-apps"></a>Netwerkvereisten voor Powershell-scripts en Win32-apps
Als u Intune gebruikt voor het implementeren van Powershell-scripts of Win32-apps, moet u ook toegang verlenen tot eindpunten waarin uw tenant zich momenteel bevindt.

|ASU | Naam van opslag | CDN |
| --- | --- |--- |
| AMSUA0601 | prodmsua06data | https:\//prodmsua06data.azureedge.net |
| AMSUA0602 | prodamsua0602data | https:\//prodamsua0602data.azureedge.net |
| AMSUA0101 | prodmsua01data | https:\//prodmsua01data.azureedge.net |
| AMSUA0201 | prodmsua02data | https:\//prodmsua02data.azureedge.net |
| AMSUA0202 | Prodmsua0202rcdata | https:\//prodamsua0202data.azureedge.net/ |
| AMSUA0401 | prodmsua04data | https:\//prodmsua04data.azureedge.net |
| AMSUA0402 | Prodmsua0402rcdata | https:\//prodamsua0402data.azureedge.net/ |
| AMSUA0501 | prodmsua05data | https:\//prodmsua05data.azureedge.net |
| AMSUA0502 | prodmsua0502data | https:\//prodmsua0502data.azureedge.net |
| AMSUB0101 | prodmsub01data | https:\//prodmsub01data.azureedge.net |
| AMSUB0102 | prodamsub0102data | https:\//prodamsub0102data.azureedge.net |
| AMSUB0201 | prodmsub02data | https:\//prodmsub02data.azureedge.net |
| AMSUB0202 | Prodmsub0202rcdata | https:\//prodamsub0202data.azureedge.net |
| AMSUB0301 | Prodmsub03data2 | https:\//prodmsub03data2.azureedge.net |
| AMSUB0302 | Prodmsub0302rcdata | https:\//prodamsub0302data.azureedge.net |
| AMSUB0501 | prodmsub05data | https:\//prodmsub05data.azureedge.net |
| AMSUC0101 | prodmsuc01data | https:\//prodmsuc01data.azureedge.net |
| AMSUC0201 | prodmsuc02data | https:\//prodmsuc02data.azureedge.net |
| AMSUC0301 | prodmsuc03data | https:\//prodmsuc03data.azureedge.net |
| AMSUC0501 | prodmsuc05data | https:\//prodmsuc05data.azureedge.net |
| AMSUA0701 | pemsua07rcdata | https:\//pemsua07data.azureedge.net |

### <a name="windows-push-notification-services-wns"></a>Windows Push Notification Services (WNS)
Bij Windows-apparaten die door Intune worden beheerd met behulp van Mobile Device Management (MDM) moet voor apparaatacties en andere directe activiteiten Windows Push Notification Services (WNS) worden gebruikt. Zie [Allowing Windows Notification traffic through enterprise firewalls](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config) (Windows Notification-verkeer via de enterprisefirewalls toestaan) voor meer informatie.    

### <a name="delivery-optimization-port-requirements"></a>Delivery Optimization-poortvereisten

#### <a name="port-requirements"></a>Poortvereisten
Voor peer-to-peerverkeer gebruikt Delivery Optimization 7680 voor TCP/IP of 3544 voor NAT Traversal (eventueel Teredo). Voor communicatie tussen client en service wordt HTTP of HTTPS via poort 80/443 gebruikt.

#### <a name="proxy-requirements"></a>Proxy-vereisten
Als u Delivery Optimization wilt gebruiken, moet u aanvragen van bytebereiken toestaan. Zie [Proxy requirements for Windows Update](https://docs.microsoft.com/windows/deployment/update/windows-update-troubleshooting) (Proxyvereisten voor Windows Update) voor meer informatie.

#### <a name="firewall-requirements"></a>Firewallvereisten
Sta de volgende hostnamen via uw firewall toe voor de ondersteuning van Delivery Optimization.
Voor communicatie tussen clients en de Delivery Optimization-cloudservice:
- *.do.dsp.mp.microsoft.com

Voor Delivery Optimization-metagegevens:
- *.dl.delivery.mp.microsoft.com
- *.emdl.ws.microsoft.com

### <a name="apple-device-network-information"></a>Netwerkgegevens voor Apple-apparaten


|Gebruikt voor|Hostnaam (IP-adres/subnet)|Protocol|Poort|
|-----|--------|------|-------|
|Inhoud van Apple-servers ophalen en weergeven|itunes.apple.com<br>\*.itunes.apple.com<br>\*.mzstatic.com<br>\*.phobos.apple.com<br> \*.phobos.itunes-apple.com.akadns.net |    HTTP    |      80      |
|Communicatie met APNS-servers|#-courier.push.apple.com<br># is een willekeurig getal van 0 tot en met 50.|    TCP     |  5223 en 443  |
|Verschillende functies waaronder toegang tot internet, de iTunes Store, de MacOS App Store, iCloud, berichten, enzovoort. |phobos.apple.com<br>ocsp.apple.com<br>ax.itunes.apple.com<br>ax.itunes.apple.com.edgesuite.net| HTTP/HTTPS |  80 of 443   |

Zie voor meer informatie de documentatie van Apple: [TCP and UDP ports used by Apple software products](https://support.apple.com/en-us/HT202944) (TCP- en UDP-poorten die worden gebruikt voor Apple-softwareproducten), [About macOS, iOS, and iTunes server host connections and iTunes background processes](https://support.apple.com/en-us/HT201999) (Over serververbindingen van macOS-, iOS- en iTunes-hosts, en iTunes-achtergrondprocessen), en [If your macOS and iOS clients aren't getting Apple push notifications](https://support.apple.com/en-us/HT203609) (Als uw macOS- en iOS-clients geen Apple-pushmeldingen ontvangen.
