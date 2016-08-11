---
title: Vereisten voor de netwerkinfrastructuur | Microsoft Intune
description: Vereisten voor Intune-firewall, -poort, -domein en -proxyserver
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 074de65b-84a5-4a01-a824-18ffd838eab0
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c671610b9c56d8b92d126d9902cce9c8c689ed63
ms.openlocfilehash: 5f92ecf7d2590150c5341d81a1a976c71518e2fd


---

# Vereisten voor de netwerkinfrastructuur voor Microsoft Intune
Lees dit onderwerp en andere vereisten in [Wat u moet weten voordat u met Microsoft Intune aan de slag gaat](what-to-know-before-you-start-microsoft-intune.md) voordat u Microsoft Intune instelt.

In dit onderwerp staan de vereisten die uw netwerkinfrastructuur in staat stellen communicatie uit te wisselen tussen de apparaten die u beheert en gebruikt om uw Intune-abonnement te beheren, en de websites op internet die worden gebruikt door de cloudservice.

Het gebruik van een lokale infrastructuur (zoals een server waarop u de software moet installeren) is niet vereist, maar u hebt de mogelijkheid om een lokale infrastructuur te gebruiken, waaronder de hulpprogramma's voor Exchange- en Active Directory-synchronisatie.

Als u computers wilt beheren die zich achter firewalls en proxyservers bevinden, moet u firewalls en proxyservers instellen om communicatie voor Intune mogelijk te maken.

## Vereisten voor firewalls, poorten en domeinen
Voor beheerde apparaten zijn configuraties vereist waarmee **alle gebruikers** via firewalls toegang krijgen tot diverse services.

De volgende tabel bevat de poorten en services waartoe de Intune-client toegang heeft.


|**Domein**|**Poorten**|**Het IP-adres**|
|------|----|
|manage.microsoft.com<br>a.manage.microsoft.com<br>admin.manage.microsoft.com<br>enterpriseenrollment.manage.microsoft.com<br>enterpriseenrollment-s.manage.microsoft.com<br>i.manage.microsoft.com<br>m.manage.microsoft.com<br>p.manage.microsoft.com<br>portal.manage.microsoft.com<br>r.manage.microsoft.com|80 en 443|134.170.168.254<br>134.170.51.126
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
|Samsung KNOX-apparaatcommunicatie via de firewall|Als u Samsung KNOX-apparaten via de firewall verbinding wilt laten maken met de KNOX-servers, volgt u de aanwijzingen in Veelgestelde vragen over Samsung KNOX.||
|Documentatie, Help en ondersteuning:</br></br>*.livemeeting.com<br>\*.microsoftonline.com<br>\*.social.technet.microsoft.com<br>blogs.technet.com<br>go.microsoft.com<br>onlinehelp.microsoft.com<br>www.microsoft.com|80|||



## Vereisten voor proxyservers
Als u computers wilt beheren die zich achter een proxyserver bevinden, moet u rekening houden met het volgende:

-   De proxyserver moet zowel **HTTP** als **HTTPS** ondersteunen, omdat Intune-clients beide protocollen gebruiken.

-   Intune ondersteunt niet-geverifieerde proxyservers.

U kunt instellingen voor de proxyserver op afzonderlijke clientcomputers wijzigen of u kunt instellingen voor Groepsbeleid gebruiken om de instellingen te wijzigen voor alle clientcomputers die zich achter een bepaalde proxyserver bevinden.

U kunt ook een proxyserver gebruiken die inhoud opslaat in de cache om [het gebruik van de netwerkbandbreedte](network-bandwidth-use.md) door Intune-clients te reduceren.


### Zie ook
[Wat u moet weten voordat u met Microsoft Intune aan de slag gaat](what-to-know-before-you-start-microsoft-intune.md)



<!--HONumber=Aug16_HO1-->


