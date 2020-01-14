---
title: Netwerkeindpunten voor US Government-implementaties - Microsoft Intune
titleSuffix: ''
description: Lees de tekst over US Government-eindpunten voor Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5f6682cb-5fcd-4018-b7f7-71768ad3152e
ms.reviewer: kerimh
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 02c1508dd3eb9c8a8932c1504c6f4d0a53c5a0d5
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2019
ms.locfileid: "75207380"
---
# <a name="us-government-endpoints-for-microsoft-intune"></a>US Government-eindpunten voor Microsoft Intune

Op deze pagina worden de US Government-eindpunten vermeld die nodig zijn voor de proxy-instellingen in uw Intune-implementaties.

Als u apparaten wilt beheren die zich achter firewalls en proxyservers bevinden, moet u communicatie voor Intune inschakelen.

- De proxyserver moet zowel **HTTP (80)** als **HTTPS (443)** ondersteunen omdat Intune-clients beide protocollen gebruiken
- Voor bepaalde taken, zoals het downloaden van software en updates, is in Intune niet-geverifieerde proxyservertoegang vereist tot manage.microsoft.com

U kunt de instellingen voor proxyservers wijzigen op afzonderlijke clientcomputers. U kunt ook de instellingen voor groepsbeleid gebruiken om de instellingen te wijzigen voor alle clientcomputers die zich achter een bepaalde proxyserver bevinden.

Voor beheerde apparaten zijn configuraties vereist waarmee **alle gebruikers** via firewalls toegang krijgen tot services.

Zie [Registratie instellen voor Windows-apparaten](../enrollment/windows-enroll.md#windows-10-auto-enrollment-and-device-registration) voor meer informatie over de automatische registratie van Windows 10 en apparaatregistratie voor Amerikaanse overheidsklanten.

De volgende tabel bevat de poorten en services waartoe de Intune-client toegang heeft:

|**Eindpunt**|**IP-adres**|
|---------------------|-----------|
|*.manage.microsoft.us | 52.243.26.209 <br> 52.247.173.11 <br> 52.227.183.12 <br>52.227.180.205 <br> 52.227.178.107 <br> 13.72.185.168 <br> 52.227.173.179 <br> 52.227.175.242 <br> 13.72.39.209 <br> 52.243.26.209 <br> 52.247.173.11 |
| enterpriseregistration.microsoftonline.us | 13.72.188.239 <br> 13.72.55.179 |

## <a name="us-government-customer-designated-endpoints"></a>Eindpunten die aan US Government-klanten zijn toegewezen:
- Azure Portal: https:\//portal.azure.us/ 
- Office 365: https:\//portal.office365.us/ 
- Intune-bedrijfsportal: https:\//portal.manage.microsoft.us/ 

## <a name="partner-service-endpoints-that-intune-depends-on"></a>Service-eindpunten voor partners waarvan Intune afhankelijk is:
- AAD Sync Services: https:\//syncservice.gov.us.microsoftonline.com/DirectoryService.svc
- Evo STS: https:\//login.microsoftonline.us
- Directoryproxy: https:\//directoryproxy.microsoftazure.us/DirectoryProxy.svc
- AAD Graph: https:\//directory.microsoftazure.us en https:\//graph.microsoftazure.us
- MS Graph: https:\//graph.microsoft.us
- ADRS: https:\//enterpriseregistration.microsoftonline.us

## <a name="windows-push-notification-services"></a>Windows Push Notification Services
Op apparaten die door Intune worden beheerd met behulp van Mobile Device Management (MDM) moet voor apparaatacties en andere directe activiteiten Windows Push Notification Services (WNS) worden gebruikt. Zie [Enterprise Firewall and Proxy Configurations to Support WNS Traffic](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config) (Bedrijfsfirewall en proxyconfiguraties ter ondersteuning van WNS-verkeer) voor meer informatie

## <a name="apple-device-network-information"></a>Netwerkgegevens voor Apple-apparaten

|**Gebruikt voor**|**Hostnaam (IP-adres/subnet)**|**Protocol**|**Poort**|
|------------|-----------|------------|-----------|
|Inhoud van Apple-servers ophalen en weergeven|itunes.apple.com<br>\*.itunes.apple.com<br>\*.mzstatic.com<br>\*.phobos.apple.com<br>\*.phobos.itunes-apple.com.akadns.net|HTTP|80|
|Communicatie met APNS-servers|#-courier.push.apple.com<br># is een willekeurig getal van 0 tot en met 50.|TCP|5223 en 443|
|Verschillende functies waaronder toegang tot internet, de iTunes Store, de macOS App Store, iCloud, berichten, enzovoort.|phobos.apple.com<br>ocsp.apple.com<br>ax.itunes.apple.com<br>ax.itunes.apple.com.edgesuite.net|HTTP/HTTPS|80 of 443|

Zie voor meer informatie:

- [TCP- en UDP-poorten die door Apple software worden gebruikt](https://support.apple.com/HT202944)
- [macOS, iOS en iTunes-server-hostverbindingen en achtergrondprocessen in iTunes](https://support.apple.com/HT201999)
- [Als u geen Apple pushberichten ontvangt in de macOS- en iOS-clients](https://support.apple.com/HT203609)

## <a name="next-steps"></a>Volgende stappen
[Netwerkeindpunten voor Microsoft Intune](intune-endpoints.md)

