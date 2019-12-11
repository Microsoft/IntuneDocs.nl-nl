---
title: Problemen met software-updates oplossen in Microsoft Intune - Azure | Microsoft Docs
description: Problemen met software-updates in Microsoft Intune oplossen.
keywords: ''
author: Brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/29/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: d17b70f4-17b4-4d89-88fd-70fa4f34fbea
ROBOTS: ''
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7da927754971fb66a5d8442d0cdf18e0ebfbcd4a
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "74059082"
---
# <a name="troubleshoot-software-updates-in-microsoft-intune"></a>Problemen met software-updates oplossen in Microsoft Intune

Gebruik deze informatie om problemen met software-updates in Microsoft Intune op te lossen. Om een lijst met foutcodes en beschrijvingen te bekijken, gaat u naar [Foutcodes voor software-update-agent in Microsoft Intune](../protect/software-update-agent-error-codes.md).

## <a name="windows-7-devices-with-many-superseded-updates-stop-reporting-to-intune"></a>Windows 7-apparaten met veel vervangen updates rapporteren niet meer aan Intune

Microsoft Intune-clients kunnen een of meer van de volgende symptomen ervaren:

- Apparaten rapporteren opeens niet meer aan Intune.  
- Apparaten ervaren een hoog CPU-verbruik.
- Toepassingen worden traag geïnstalleerd wanneer ze via Intune worden geïnstalleerd.
- Het Microsoft Intune Center geeft de volgende fout weer: `An error occurred while updating your computer. Error found: Code 0x800705b4`.
- De Intune-beheerconsole > Groepen > Alle apparaten > status toont: `One or more agents that are installed on this computer have errors. The information for this computer may not be accurate or up-to-date.`

Dit probleem kan optreden als vervangen updates (updates die zijn vervangen door een andere update) gedurende een langere periode niet zijn afgewezen. Tijdens bepaalde processen, zoals het installeren van een toepassing, controleert Windows alle vervangen updates in de juiste volgorde, zodat de updates en de opvolgers hiervan correct worden toegewezen. Als de lijst met vervangen updates te groot wordt, kan deze controletaak leiden tot hoog CPU-verbruik door de verwerkingsbelasting en de daarvoor benodigde tijd. Dit probleem is hoofdzakelijk van invloed op Windows 7-apparaten door het grote aantal vervangen updates dat beschikbaar is voor Windows 7. Nieuwere besturingssystemen hebben mogelijk niet zo veel vervangen updates en zijn mogelijk niet vatbaar voor dit probleem.

**Oplossing**

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **Software-updates**.
3. Wijs alle vervangen updates af die van toepassing zijn op Windows 7 of op toepassingen, zoals Microsoft Office, die zijn geïnstalleerd op de betreffende clients.
4. Start de betreffende clients opnieuw op.

Als u met Windows 7 werkt, moet u controleren of de volgende update is geïnstalleerd:[3050265 Windows Update-client voor Windows 7: juni 2015](https://support.microsoft.com/kb/3050265).

## <a name="next-steps"></a>Volgende stappen

Krijg [ondersteuning van Microsoft](get-support.md) of gebruik de [communityforums](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).