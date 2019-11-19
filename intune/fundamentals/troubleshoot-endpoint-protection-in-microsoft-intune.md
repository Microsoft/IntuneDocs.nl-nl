---
title: Veelvoorkomende Endpoint Protection-berichten in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk veelvoorkomende berichten en mogelijke oplossingen bij het gebruik van en het oplossen van problemen met Endpoint Protection en Microsoft Defender in Microsoft Intune.
keywords: ''
author: Brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/13/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: e31df2d2-bb1b-491b-9a71-04e0b18829c1
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 819586a923f5c0f3a81a6d59c4a3895898182f6b
ms.sourcegitcommit: 78cebd3571fed72a3a99e9d33770ef3d932ae8ca
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 11/13/2019
ms.locfileid: "74059164"
---
# <a name="endpoint-protection-issues-and-possible-solutions-in-microsoft-intune"></a>Problemen met Endpoint Protection en mogelijke oplossingen in Microsoft Intune

In dit artikel worden mogelijke oorzaken en oplossingen voor sommige fouten en waarschuwingen vermeld en beschreven. Gebruik deze informatie om problemen op te lossen tijdens het gebruik van Endpoint Protection.

## <a name="microsoft-defender-error-codes"></a>Micro soft Defender-fout codes

Gebeurtenislogboeken en foutcodes bekijken om [problemen met Microsoft Defender AV op te lossen](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus).

## <a name="common-intune-errors-and-possible-resolutions"></a>Veelvoorkomende fouten in Intune en mogelijke oplossingen

### <a name="endpoint-protection-engine-unavailable"></a>Endpoint Protection-engine niet beschikbaar

**Mogelijke oorzaak**: de Intune Endpoint Protection-engine is beschadigd of verwijderd.

**Mogelijke oplossingen**:

- Als Endpoint Protection beschadigd is of niet kan worden bijgewerkt, dient u het programma bij te werken of opnieuw te installeren.
- Dwing een onmiddellijke update af. Kies in het Endpoint Protection-clientprogramma (mogelijk in de taakbalk) **Bijwerken**.
- In Configuratiescherm > Programma's selecteert u **Microsoft Intune Endpoint Protection-agent**. Verwijder de toepassing.
- Tijdens de volgende updatesynchronisatie detecteert de Microsoft Online Management-updatebeheerder het ontbrekende programma en installeert het opnieuw op het geplande installatietijdstip.

### <a name="features-are-disabled"></a>De functies zijn uitgeschakeld

U krijgt mogelijk een bericht te zien waarin staat dat sommige functies zijn uitgeschakeld. Deze berichten kunnen verschijnen als Intune Endpoint Protection of Microsoft Defender is uitgeschakeld door een beheerder die een configuratieprofiel gebruikt. Of het programma is uitgeschakeld door een eindgebruiker op het apparaat. Mogelijke berichten:

`Endpoint Protection disabled`  
`Real-time protection disabled`  
`Download scanning disabled`  
`File and program activity monitoring disabled`  
`Behavior monitoring disabled`  
`Script scanning disabled`  
`Network Inspection System disabled`  

**Mogelijke oplossingen**: schakel deze functies in. Zie voor meer informatie:

- [Instellingen voor Endpoint Protection toevoegen](../protect/endpoint-protection-configure.md)
- [Micro soft Defender anti virus](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus)
- [Eindgebruikers: realtime-beveiliging voor toegang tot bedrijfsresources inschakelen](/intune-user-help/turn-on-defender-windows)

### <a name="malware-definitions-out-of-date"></a>De malware-definities zijn verouderd

Deze status wordt weergegeven als de malwaredefinities op het apparaat langer dan 14 dagen niet zijn bijgewerkt. Het bericht kan bijvoorbeeld aangeven dat het apparaat niet met internet is verbonden of dat de malwaredefinities verouderd zijn.

**Mogelijke oplossingen**: als de malwaredefinities verouderd zijn, werkt u de definities bij met [Microsoft Defender Antivirus](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus).

### <a name="full-scan-overdue-or-quick-scan-overdue"></a>Volledige of snelle scan is achterstallig

Er is al 14 dagen geen volledige of snelle scan uitgevoerd. Dit scenario kan plaatsvinden als het apparaat tijdens een volledige scan opnieuw wordt opgestart.

**Mogelijke oplossingen**: als een scan achterstallig is, kunt u een eenmalige scan uitvoeren of terugkerende scans plannen. Zie [micro soft Defender anti virus](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus)(Engelstalig).

### <a name="another-endpoint-protection-application-running"></a>Er wordt een andere eindpuntbeveiligingstoepassing uitgevoerd

Er wordt een andere eindpuntbeveiligingstoepassing uitgevoerd en het apparaat is in orde.

**Mogelijke oplossingen**: als er een andere Endpoint Protection-toepassing is geïnstalleerd en Intune de betreffende toepassing detecteert, kan het apparaat instabiel worden.

## <a name="next-steps"></a>Volgende stappen

Krijg [ondersteuning van Microsoft](get-support.md) of gebruik de [communityforums](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).
