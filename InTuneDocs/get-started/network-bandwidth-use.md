---
title: Gebruik van netwerkbandbreedte | Microsoft Docs
description: gebruik van netwerkbandbreedte door intune
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 0f5972171349325eeb750e552481cbcf903fdf95
ms.openlocfilehash: 9f1cd7ea3e92ac2e3a1b828e8185961060a7c619
ms.lasthandoff: 02/10/2017


---

# <a name="intune-network-bandwidth-use"></a>Gebruik van netwerkbandbreedte door Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Deze richtlijnen zijn bedoeld voor systeembeheerders die verantwoordelijk zijn voor het beheer van apparaten in de onderneming. Zie [Veelgestelde vragen over de Intune-bedrijfsportal](https://docs.microsoft.com/intune/enduser/company-portal-frequently-asked-questions) voor informatie over het gebruik van Intune op uw mobiele apparaat.

Lees dit onderwerp en andere vereisten in [Wat u moet weten voordat u met Microsoft Intune aan de slag gaat](what-to-know-before-you-start-microsoft-intune.md) voordat u Microsoft Intune instelt.

Gebruik de informatie in de volgende gedeelten om te plannen voor het netwerkverkeer voor Microsoft Intune-clients.

## <a name="average-network-traffic"></a>Gemiddeld netwerkverkeer
Deze tabel bevat de geschatte grootte en frequentie van algemene inhoud die via het netwerk voor elke client wordt verzonden.

> [!NOTE]
> Om ervoor te zorgen dat computers en mobiele apparaten de vereiste updates en inhoud van de Intune-service ontvangen, moeten ze regelmatig worden verbonden met internet. Hoeveel tijd het duurt om updates of inhoud te ontvangen verschilt, maar als uitgangspunt moeten ze ten minste 1 uur per dag continu met internet verbonden zijn.

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
U kunt een proxyserver gebruiken om inhoud in cache te plaatsen zodat dubbele downloads worden verminderd, en om het gebruik te beperken van de netwerkbandbreedte die clients nodig hebben om inhoud van internet aan te vragen.

Een cacheproxyserver ontvangt verzoeken voor inhoud van clientcomputers in uw netwerk, haalt die inhoud op van internet en plaatst vervolgens zowel HTTP-antwoorden als binaire downloads in cache. De server gebruikt de gegevens in cache om de volgende aanvragen van Intune-clientcomputers te beantwoorden.

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
Intune-clients kunnen BranchCache gebruiken om WAN-verkeer (Wide Area Network) te beperken. De volgende besturingssystemen die worden ondersteund als client, bieden ook ondersteuning voor BranchCache:

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

Als u BranchCache wilt gebruiken, moet BranchCache op de clientcomputer zijn ingeschakeld en moet de computer zijn geconfigureerd voor de **modus Gedistribueerde cache**.

BranchCache en de modus voor gedistribueerde cache zijn standaard ingeschakeld op een computer als de Intune-client is geïnstalleerd. Als de client echter al groepsbeleid heeft waarmee BranchCache wordt uitgeschakeld, wordt dat beleid niet door Intune overschreven en blijft BranchCache uitgeschakeld op die computer.

Als u BranchCache gebruikt, moet u contact opnemen met andere beheerders in uw organisatie die groepsbeleid en het beleid voor de Intune Firewall beheren om ervoor te zorgen dat zij geen beleid implementeren waarmee BranchCache of Firewall-uitzonderingen worden uitgeschakeld. Zie [Overzicht van BranchCache](http://technet.microsoft.com/library/hh831696.aspx) voor meer informatie over BranchCache.

## <a name="network-communication-requirements"></a>Vereisten voor netwerkcommunicatie

U moet netwerkcommunicatie inschakelen tussen de apparaten die u beheert en gebruikt voor het beheren van uw Intune-abonnement en de websites die vereist zijn voor cloudservices.

Intune gebruikt geen on-premises infrastructuur, zoals servers waarop Intune wordt uitgevoerd, maar u hebt de mogelijkheid om on-premises infrastructuur te gebruiken, waaronder de hulpprogramma's voor Exchange- en Active Directory-synchronisatie.

Als u computers wilt beheren die zich achter firewalls en proxyservers bevinden, moet u firewalls en proxyservers instellen om communicatie voor Intune mogelijk te maken.

### <a name="requirements-for-proxy-servers"></a>Vereisten voor proxyservers
Als u computers wilt beheren die zich achter een proxyserver bevinden, moet u rekening houden met het volgende:

-   De proxyserver moet zowel **HTTP** als **HTTPS** ondersteunen, omdat Intune-clients beide protocollen gebruiken
-   Intune ondersteunt niet-geverifieerde proxyservers

U kunt instellingen voor de proxyserver op afzonderlijke clientcomputers wijzigen of u kunt instellingen voor Groepsbeleid gebruiken om de instellingen te wijzigen voor alle clientcomputers die zich achter een bepaalde proxyserver bevinden.

### <a name="requirements-for-firewalls-ports-and-domains"></a>Vereisten voor firewalls, poorten en domeinen
Voor beheerde apparaten zijn configuraties vereist waarmee **alle gebruikers** via firewalls toegang krijgen tot services.

De volgende tabel bevat de poorten en services waartoe de Intune-client toegang heeft.

|**Domein**|**Poorten**|**IP-adres**|
|------|----|---|
|manage.microsoft.com<br>a.manage.microsoft.com<br>admin.manage.microsoft.com<br>enterpriseenrollment.manage.microsoft.com<br>enterpriseenrollment-s.manage.microsoft.com<br>i.manage.microsoft.com<br>p.manage.microsoft.com<br>r.manage.microsoft.com|80 en 443|134.170.168.254<br>134.170.51.126
|m.manage.microsoft.com|80 en 443| 13.91.59.243<br>40.68.30.140
|portal.manage.microsoft.com|80 en 443|40.121.50.69<br>52.169.30.159
|account.manage.microsoft.com|80 en 443|157.56.13.59
|fef.msua01.manage.microsoft.com|80 en 443|138.91.243.97
|fef.msua02.manage.microsoft.com|80 en 443|23.96.112.46
|fef.msua04.manage.microsoft.com|80 en 443|23.96.112.28
|fef.msua05.manage.microsoft.com|80 en 443|138.91.244.151
|fef.msub01.manage.microsoft.com|80 en 443|137.135.128.214
|fef.msub02.manage.microsoft.com|80 en 443|137.135.130.29
|fef.msub03.manage.microsoft.com|80 en 443|23.97.165.17
|fef.msub05.manage.microsoft.com|80 en 443|23.97.166.52
|fef.msuc01.manage.microsoft.com|80 en 443|207.46.225.1
|fef.msuc02.manage.microsoft.com|80 en 443|23.98.66.118
|fef.msuc03.manage.microsoft.com|80 en 443|23.101.0.100
|fef.msuc05.manage.microsoft.com|80 en 443|207.46.154.33
|fef.msua06.manage.microsoft.com|80 en 443|104.42.188.1
|fei.msua01.manage.microsoft.com|80 en 443|138.91.240.131
|fei.msua02.manage.microsoft.com|80 en 443|23.96.112.143
|fei.msua04.manage.microsoft.com|80 en 443|23.96.112.147
|fei.msua05.manage.microsoft.com|80 en 443|138.91.240.163
|fei.msub01.manage.microsoft.com|80 en 443|137.135.130.85
|fei.msub02.manage.microsoft.com|80 en 443|137.135.132.149
|fei.msub03.manage.microsoft.com|80 en 443|23.97.160.232
|fei.msub05.manage.microsoft.com|80 en 443|23.97.162.250
|fei.msuc01.manage.microsoft.com|80 en 443|207.46.224.73
|fei.msuc02.manage.microsoft.com|80 en 443|23.98.66.194
|fei.msuc03.manage.microsoft.com|80 en 443|23.101.2.105
|fei.msuc05.manage.microsoft.com|80 en 443|207.46.147.126
|fei.msua06.manage.microsoft.com|80 en 443|138.91.149.190
|m.fei.msua01.manage.microsoft.com|80 en 443|138.91.240.131
|m.fei.msua02.manage.microsoft.com|80 en 443|23.96.112.143
|m.fei.msua04.manage.microsoft.com|80 en 443|23.96.112.147
|m.fei.msua05.manage.microsoft.com|80 en 443|138.91.240.163
|m.fei.msub01.manage.microsoft.com|80 en 443|137.135.130.85
|m.fei.msub02.manage.microsoft.com|80 en 443|137.135.132.149
|m.fei.msub03.manage.microsoft.com|80 en 443|23.97.160.232
|m.fei.msub05.manage.microsoft.com|80 en 443|23.97.162.250
|m.fei.msuc01.manage.microsoft.com|80 en 443|207.46.224.73
|m.fei.msuc02.manage.microsoft.com|80 en 443|23.98.66.194
|m.fei.msuc03.manage.microsoft.com|80 en 443|23.101.2.105
|m.fei.msuc05.manage.microsoft.com|80 en 443|207.46.147.126
|m.fei.msua06.manage.microsoft.com|80 en 443|138.91.149.190
|m.msua01.manage.microsoft.com|80 en 443|157.55.50.182
|m.msua02.manage.microsoft.com|80 en 443|134.170.49.121
|m.msua04.manage.microsoft.com|80 en 443|134.170.49.126
|m.msua05.manage.microsoft.com|80 en 443|157.55.240.190
|m.msua06.manage.microsoft.com|80 en 443|134.170.49.114
|m.msub01.manage.microsoft.com|80 en 443|94.245.121.50
|m.msub02.manage.microsoft.com|80 en 443|94.245.121.58
|m.msub03.manage.microsoft.com|80 en 443|94.245.121.56
|m.msub05.manage.microsoft.com|80 en 443|157.56.113.123
|m.msuc01.manage.microsoft.com|80 en 443|104.44.84.187
|m.msuc02.manage.microsoft.com|80 en 443|104.44.84.188
|m.msuc03.manage.microsoft.com|80 en 443|104.44.84.189
|m.msuc05.manage.microsoft.com|80 en 443|111.221.76.60
|msua01.manage.microsoft.com|80 en 443|157.55.50.182
|msua02.manage.microsoft.com|80 en 443|134.170.49.121
|msua04.manage.microsoft.com|80 en 443|134.170.49.126
|msua05.manage.microsoft.com|80 en 443|157.55.240.190
|msub01.manage.microsoft.com|80 en 443|94.245.121.50
|msub02.manage.microsoft.com|80 en 443|94.245.121.58
|msub03.manage.microsoft.com|80 en 443|94.245.121.56
|msub05.manage.microsoft.com|80 en 443|157.56.113.123
|msuc01.manage.microsoft.com|80 en 443|104.44.84.187
|msuc02.manage.microsoft.com|80 en 443|104.44.84.188
|msuc03.manage.microsoft.com|80 en 443|104.44.84.189
|msuc05.manage.microsoft.com|80 en 443|111.221.76.60
|msua06.manage.microsoft.com|80 en 443|134.170.49.114
|ncufun.account.manage.microsoft.com|80 en 443|157.55.252.224
|neufun.account.manage.microsoft.com|80 en 443|65.52.229.134
|portal.fei.msua01.manage.microsoft.com|80 en 443|138.91.240.131
|portal.fei.msua02.manage.microsoft.com|80 en 443|23.96.112.143
|portal.fei.msua04.manage.microsoft.com|80 en 443|23.96.112.147
|portal.fei.msua05.manage.microsoft.com|80 en 443|138.91.240.163
|portal.fei.msub01.manage.microsoft.com|80 en 443|137.135.130.85
|portal.fei.msub02.manage.microsoft.com|80 en 443|137.135.132.149
|portal.fei.msub03.manage.microsoft.com|80 en 443|23.97.160.232
|portal.fei.msub05.manage.microsoft.com|80 en 443|23.97.162.250
|portal.fei.msuc01.manage.microsoft.com|80 en 443|207.46.224.73
|portal.fei.msuc02.manage.microsoft.com|80 en 443|23.98.66.194
|portal.fei.msuc03.manage.microsoft.com|80 en 443|23.101.2.105
|portal.fei.msuc05.manage.microsoft.com|80 en 443|207.46.147.126
|portal.fei.msua06.manage.microsoft.com|80 en 443|138.91.149.190
|portal.msua01.manage.microsoft.com|80 en 443|157.55.50.182
|portal.msua02.manage.microsoft.com|80 en 443|134.170.49.121
|portal.msua04.manage.microsoft.com|80 en 443|134.170.49.126
|portal.msua05.manage.microsoft.com|80 en 443|157.55.240.190
|portal.msub01.manage.microsoft.com|80 en 443|94.245.121.50
|portal.msub02.manage.microsoft.com|80 en 443|94.245.121.58
|portal.msub03.manage.microsoft.com|80 en 443|94.245.121.56
|portal.msub05.manage.microsoft.com|80 en 443|157.56.113.123
|portal.msuc01.manage.microsoft.com|80 en 443|104.44.84.187
|portal.msuc02.manage.microsoft.com|80 en 443|104.44.84.188
|portal.msuc03.manage.microsoft.com|80 en 443|104.44.84.189
|portal.msuc05.manage.microsoft.com|80 en 443|111.221.76.60
|portal.msua06.manage.microsoft.com|80 en 443|134.170.49.114
|ssu2.manage.microsoft.com|80 en 443|157.55.99.181
|status.manage.microsoft.com|80 en 443|157.55.99.170
|swda01.manage.microsoft.com<br>swda02.manage.microsoft.com<br>swdb01.manage.microsoft.com<br>swdb02.manage.microsoft.com<br>swdc01.manage.microsoft.com<br>swdc02.manage.microsoft.com|80 en 443|93.184.215.200
|*.microsoftonline-p.com|80 en 443||
|has.spserv.microsoft.com<br>Vereist voor de Health Attestation-service van apparaten|443||
|*.microsoftonline-p.net|80 en 443||
|*.portal.office.com|80 en 443||
|*.spynet2.microsoft.com|443||
|c.microsoft.com|80 en 443||
|c1.microsoft.com|80 en 443||
|blob.core.windows.net|80 en 443||
|ajax.aspnetcdn.com|80 en 443||
|*.googleapis.com<br>Dit domein is vereist voor JQuery-ondersteuning als u de bedrijfsportalwebsite gebruikt.|80 en 443||
|wustat.microsoft.com|80 en 443||
|Microsoft Update-services|\*.update.microsoft.com<br>download.microsoft.com<br>update.microsoft.com<br>\*.download.windowsupdate.com<br>download.windowsupdate.com<br>\*.windowsupdate.com<br>windowsupdate.microsoft.com<br>ntservicepack.microsoft.com|80 en 443|
|DNS-lookup-aanvragen|manage.microsoft.com.nsatc.net|80|
|Samsung KNOX Standard-apparaatcommunicatie via de firewall|Als u Samsung KNOX Standard-apparaten via de firewall verbinding wilt laten maken met de KNOX Standard-servers, volgt u de aanwijzingen in Veelgestelde vragen over Samsung KNOX Standard.||
|Communicatie over voorwaardelijke toegang|443|204.79.197.200|
|Documentatie, Help en ondersteuning:</br></br>*.livemeeting.com<br>\*.microsoftonline.com<br>\*.social.technet.microsoft.com<br>blogs.technet.com<br>go.microsoft.com<br>onlinehelp.microsoft.com<br>www.microsoft.com|80|||


>[!div class="step-by-step"]

>[&larr;**Vereisten**](what-to-know-before-you-start-microsoft-intune.md)     [**Abonnement** &rarr;](start-with-a-paid-subscription-to-microsoft-intune-step-1.md)  

