---
title: Problemen met Exchange Connector oplossen
description: Problemen met betrekking tot de Intune Exchange Connector oplossen.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c5cb5465-fd8e-4524-83b9-ccdf3393b6dc
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ebcbcbc36c925b3c3d9600eb9a5039b70d7e056d
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="troubleshoot-the-exchange-connector"></a>Problemen met de Exchange Connector oplossen

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

In dit onderwerp wordt beschreven hoe u mogelijke problemen kunt oplossen die verband houden met de Intune Exchange Connector.

## <a name="steps-for-checking-the-connector-configuration"></a>Stappen voor het controleren van de Connector-configuratie 

Controleer de configuratie van de Exchange Connector en controleer vervolgens of het probleem is opgelost.

- Zorg dat u een meldingsaccount opgeeft tijdens de eerste installatie van de Exchange Connector.
- De Exchange Connector-serviceaccount moet de juiste machtigingen hebben voor het uitvoeren van de PowerShell-cmdlets die door de Exchange Connector worden gebruikt.
- Wanneer u de Exchange Connector configureert, geeft u een Client Access Server (CAS) op die zich zo dicht mogelijk bij de server bevindt die als host fungeert voor de Exchange Connector. Vertragingen in de communicatie tussen de CAS en de Exchange Connector kunnen leiden tot vertragingen bij het detecteren van apparaten, vooral als O365 Dedicated wordt gebruikt.
- Houd rekening met een tijdsinterval tussen synchronisaties van de Exchange Connector met de Exchange-CAS. Een volledige synchronisatie vindt elke dag plaats en een (snelle) deltasynchronisatie vindt elke twee uur plaats. Het kan gebeuren dat een gebruiker met een pas geregistreerd apparaat een vertraging ondervindt bij het verkrijgen van toegang.
- 
## <a name="exchange-activesync-device-not-discovered-from-exchange"></a>Een Exchange ActiveSync-apparaat wordt niet gedetecteerd door Exchange
Controleer of de Exchange Connector wordt gesynchroniseerd met de Exchange-server. Ga hiervoor naar de logboeken voor een volledige synchronisatie of een deltasynchronisatie. Raadpleeg de logboeken van de Exchange Connector. Als een volledige synchronisatie of deltasynchronisatie is uitgevoerd sinds het apparaat is toegevoegd, is dit geëlimineerd als de oorzaak van het probleem. Als er geen synchronisatie heeft plaatsgevonden, moet u de synchronisatielogboeken verzamelen en deze bij uw ondersteuningsaanvraag voegen.

- Als een gebruiker geen licentie voor Intune heeft, kan de Exchange Connector zijn apparaten niet detecteren.
- Als het primaire SMTP-adres van een gebruiker anders is dan de UPN in AAD, detecteert de Exchange Connector geen enkel apparaat voor die Intune/AAD-gebruiker. Corrigeer het primaire SMTP-adres.
- Als de CAS waarmee de Exchange Connector tijdens een detectiecyclus communiceert een Exchange 2010-CAS is en u zowel Exchange 2010- als 2013-postvakservers hebt, detecteert de Exchange Connector geen enkel Exchange 2013-apparaat van een gebruiker. U kunt dit oplossen door de Exchange Connector zo te configureren dat deze naar een Exchange 2013-CAS verwijst.  Hoewel dit probleem zich voornamelijk bij O365 Dedicated-topologieën voordoet, wordt als best practice nog steeds aanbevolen om in andere topologieën ook naar een Exchange 2013-CAS te laten verwijzen.
- Voor de omgevingen met Exchange Dedicated (O365 Dedicated) moet u de Exchange Connector tijdens de eerste installatie laten verwijzen naar een Exchange 2013-CAS (geen 2010) in de toegewezen omgeving, omdat deze bij het uitvoeren van Powershell-cmdlets alleen met deze CAS communiceert.


## <a name="using-powershell-to-get-more-data-on-exchange-connector-issues"></a>Powershell gebruiken om meer gegevens over problemen met de Exchange Connector te verkrijgen
- Gebruik Get-ActiveSyncDeviceStatistics -mailbox mbx om een lijst met alle mobiele apparaten voor een postvak op te halen
- Gebruik Get-Mailbox -Identity user | select emailaddresses | fl om een lijst van SMTP-adressen voor een postvak op te halen
- Gebruik Get-CASMailbox <upn> | fl om gedetailleerde informatie over de toegangsstatus van een apparaat op te halen

### <a name="next-steps"></a>Volgende stappen
Als deze informatie over probleemoplossing u niet heeft geholpen, kunt u contact opnemen met Microsoft Ondersteuning zoals is beschreven in [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md).
