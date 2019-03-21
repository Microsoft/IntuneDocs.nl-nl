---
title: Problemen met Endpoint Protection oplossen in Microsoft Intune | Microsoft Docs
description: Problemmen oplossen tijdens het gebruik van Microsoft Intune Endpoint Protection.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/14/2018
ms.topic: troubleshooting
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: e31df2d2-bb1b-491b-9a71-04e0b18829c1
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8eddf9af16e0218733f1e0445d85ab7e0176ed27
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57461416"
---
# <a name="troubleshoot-endpoint-protection-in-intune"></a>Problemen met Endpoint Protection oplossen in Intune

Gebruik deze informatie om problemen op te lossen tijdens het gebruik van Endpoint Protection. U kunt ook [gebeurtenislogboeken en foutcodes bekijken om problemen met Windows Defender AV op te lossen](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus).

Als deze informatie geen oplossing biedt, kunt u ook [ondersteuning voor Microsoft Intune krijgen](get-support.md).

### <a name="error-messages"></a>Foutberichten
Deze sectie beschrijft mogelijke oorzaken en oplossingen voor de volgende fouten en waarschuwingen.

|Statusitem|Mogelijke oorzaken|Mogelijke oplossingen|
|---------------|--------------------|-----------------------|
|**Endpoint Protection-engine niet beschikbaar**|De Intune Endpoint Protection-engine is beschadigd of verwijderd.|Als de Intune Endpoint Protection-engine is beschadigd, kunt u proberen om de software bij te werken of deze opnieuw te installeren.<br /><br />Als u een onmiddellijke update wilt afdwingen, kiest u in de Endpoint Protection-clientsoftware **Bijwerken** (in de taakbalk op beheerde computers).<br /><br />Als de engine niet kan worden bijgewerkt, moet u de Engine Protection-engine opnieuw installeren.<br /><br />Zoek in de lijst met geïnstalleerde programma's in het Configuratiescherm op de beheerde computer **Microsoft Intune Endpoint Protection-agent** en verwijder de toepassing.<br /><br />Tijdens de volgende updatesynchronisatie detecteert de Microsoft Online Management-updatebeheerder het ontbrekende programma en installeert het opnieuw op het geplande installatietijdstip.|
|**Endpoint Protection uitgeschakeld**|Intune Endpoint Protection is uitgeschakeld door een beheerder (op basis van een configuratieprofiel) of door de gebruiker van een beheerde computer.|Endpoint Protection inschakelen. Zie [Instellingen voor Endpoint Protection toevoegen](endpoint-protection-configure.md) in Intune, of [ Windows Defender inschakelen om toegang tot bedrijfsresources te krijgen](/intune-user-help/turn-on-defender-windows).|
|**Real-timebeveiliging is uitgeschakeld**|Realtime-beveiliging is uitgeschakeld door een beheerder (op basis van een profiel) of door de gebruiker van een beheerde computer.|Endpoint Protection inschakelen. Zie [Windows Defender Antivirus](device-restrictions-windows-10.md#windows-defender-antivirus) in Intune, of [realtime-beveiliging inschakelen om toegang tot bedrijfsresources te krijgen](/intune-user-help/turn-on-defender-windows). |
|**Scannen van downloads is uitgeschakeld**|Scannen van downloads is uitgeschakeld door een beheerder (op basis van een profiel) of door een gebruiker op een beheerde computer.|Scannen inschakelen. Zie [Windows Defender Antivirus](device-restrictions-windows-10.md#windows-defender-antivirus) in Intune, of [realtime-beveiliging inschakelen om toegang tot bedrijfsresources te krijgen](/intune-user-help/turn-on-defender-windows). |
|**Controle van bestands- en programma-activiteit is uitgeschakeld**|Controle van bestands- en programma-activiteit is uitgeschakeld door een beheerder (op basis van een profiel) of door een gebruiker op een beheerde computer.|Bestands en programma-activiteit inschakelen. Zie [Windows Defender Antivirus](device-restrictions-windows-10.md#windows-defender-antivirus) in Intune, of [realtime-beveiliging inschakelen om toegang tot bedrijfsresources te krijgen](/intune-user-help/turn-on-defender-windows). |
|**Gedragscontrole is uitgeschakeld**|Gedragscontrole is uitgeschakeld door een beheerder (op basis van een profiel) of door de gebruiker van een beheerde computer.|Gedragscontrole inschakelen. Zie [Windows Defender Antivirus](device-restrictions-windows-10.md#windows-defender-antivirus) in Intune, of [realtime-beveiliging inschakelen om toegang tot bedrijfsresources te krijgen](/intune-user-help/turn-on-defender-windows). |
|**Scannen van scripts is uitgeschakeld**|Het scannen van scripts is uitgeschakeld door een beheerder (op basis van een profiel) of door de gebruiker van een beheerde computer.|Scannen van scripts inschakelen. Zie [Windows Defender Antivirus](device-restrictions-windows-10.md#windows-defender-antivirus) in Intune, of [realtime-beveiliging inschakelen om toegang tot bedrijfsresources te krijgen](/intune-user-help/turn-on-defender-windows). |
|**Netwerkinspectiesysteem uitgeschakeld**|Het netwerkinspectiesysteem is uitgeschakeld door een beheerder (op basis van een profiel) of door een gebruiker op een beheerde computer.|Netwerkinspectiesysteem (NIS) inschakelen. Zie [Windows Defender Antivirus](device-restrictions-windows-10.md#windows-defender-antivirus) in Intune, of [realtime-beveiliging inschakelen om toegang tot bedrijfsresources te krijgen](/intune-user-help/turn-on-defender-windows). |
|**Definities van schadelijke software zijn verouderd**|De computer is mogelijk langere tijd losgekoppeld geweest van internet en de definities van schadelijke software zijn mogelijk nog niet bijgewerkt. Deze status wordt weergegeven als de malware-definities op de computer langer dan 14 dagen niet zijn bijgewerkt.|Als de malware-definities verouderd zijn, kunt u de definities bijwerken met [Windows Defender Antivirus](device-restrictions-windows-10.md#windows-defender-antivirus).|
|**Achterstallige volledige scan**|Het is 14 dagen geleden dat een volledige scan is voltooid. Dit kan zijn omdat een computer opnieuw is opgestart tijdens een volledige scan.|Als een volledige scan achterstallig is, kunt u een eenmalige volledige scan uitvoeren of terugkerende volledige scans plannen. Zie [Windows Defender Antivirus](device-restrictions-windows-10.md#windows-defender-antivirus). |
|**Achterstallige snelle scan**|Het is 14 dagen geleden dat een snelle scan is voltooid. Dit kan zijn veroorzaakt door een herstart tijdens een snelle scan.|Als een snelle scan achterstallig is, kunt u een eenmalige volledige scan uitvoeren of terugkerende snelle scans plannen. Zie [Windows Defender Antivirus](device-restrictions-windows-10.md#windows-defender-antivirus).|
|**Er wordt een andere Endpoint Protection-toepassing uitgevoerd**|Er wordt een andere eindpuntbeveiligingstoepassing uitgevoerd en de computer is in orde.|Als er een andere Endpoint Protection-toepassing is geïnstalleerd en Intune de betreffende toepassing detecteert, kan het apparaat instabiel worden.|

### <a name="next-steps"></a>Volgende stappen
Als deze informatie geen oplossing biedt, kunt u ook [ondersteuning voor Microsoft Intune krijgen](get-support.md).
