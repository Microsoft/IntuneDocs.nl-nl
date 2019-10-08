---
title: Problemen met Exchange Connector oplossen
titleSuffix: Microsoft Intune
description: Problemen met betrekking tot de Intune on-premises Exchange-connector oplossen.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/02/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: a7e3c742-295b-40bb-9afa-17f243062500
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 230ee8c1206a4d091661b51dd239a4cb0b1a1963
ms.sourcegitcommit: f04e21ec459998922ba9c7091ab5f8efafd8a01c
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71814041"
---
# <a name="troubleshoot-the-intune-exchange-connector"></a>Problemen met Intune Exchange Connector oplossen

In dit artikel wordt beschreven hoe u problemen met betrekking tot de Intune Exchange-connector kunt oplossen.

## <a name="before-you-start"></a>Voordat u begint

Voordat u begint met het oplossen van problemen met Exchange connector in intune, moet u enkele basis gegevens verzamelen, zodat u aan de slag gaat met een solide basis. Deze aanpak kan u helpen de aard van het probleem beter te begrijpen en het sneller te verhelpen.

- Controleer of het proces voldoet aan de installatie vereisten. Zie [de on-premises intune Exchange connector instellen](exchange-connector-install.md).
- Controleer of uw account zowel Exchange-als intune-beheerders machtigingen heeft.
- Let op de tekst van het volledige en exacte fout bericht, Details en waar het bericht wordt weer gegeven.
- Vaststellen wanneer het probleem is begonnen: 
  - Stelt u de connector voor de eerste keer in? 
  - Werkt de connector goed en mislukt deze?
  - Als het werk was, welke wijzigingen zijn aangebracht in de intune-omgeving, de Exchange-omgeving of op de computer waarop de connector-software wordt uitgevoerd?
- Wat is de MDM-instantie? Als het System Center Configuration Manager, welke versie van Configuration Manager gebruikt u?
- Welke versie van Exchange gebruikt u?

### <a name="use-powershell-to-get-more-data-on-exchange-connector-issues"></a>Powershell gebruiken om meer gegevens over problemen met de Exchange Connector te verkrijgen

- Gebruik `Get-ActiveSyncDeviceStatistics -mailbox mbx` om een lijst met alle mobiele apparaten voor een postvak op te halen.
- Gebruik `Get-Mailbox -Identity user | select emailaddresses | fl` om een lijst met SMTP-adressen voor een postvak op te halen
- Gebruik `Get-CASMailbox <upn> | fl` om gedetailleerde informatie op te halen over de toegangsstatus van een apparaat

## <a name="review-the-connector-configuration"></a>De connector configuratie controleren

Bekijk de [vereisten voor on-premises Exchange connector](exchange-connector-install.md#intune-exchange-connector-requirements) om te controleren of uw omgeving en de connector correct zijn geconfigureerd. 

### <a name="general-considerations-for-the-connector"></a>Algemene overwegingen voor de connector

- Zorg ervoor dat uw firewall en proxy servers communicatie toestaan tussen de server die als host fungeert voor de intune Exchange connector en de intune-service.

- De computer die als host fungeert voor de intune Exchange connector en de Exchange Client Access server (CAS) moet lid zijn van een domein en op hetzelfde LAN zijn. Zorg ervoor dat de vereiste machtigingen zijn toegevoegd voor het account dat wordt gebruikt door de intune Exchange connector.

- Het meldings account wordt gebruikt om instellingen voor *Automatische detectie* op te halen. Zie [autodis cover service in Exchange Server](https://docs.microsoft.com/exchange/architecture/client-access/autodiscover?view=exchserver-2016)(Engelstalig) voor meer informatie over Autodisover in Exchange.

- De intune Exchange connector verzendt een aanvraag naar de EWS-URL met behulp van de referenties van het meldings account voor het verzenden van e-mail berichten met meldingen, samen met de koppeling aan de *slag* (om in te schrijven bij intune). Het gebruik van de koppeling aan *de slag om* in te schrijven is een vereiste voor Android-apparaten die niet van Knox zijn. Anders worden deze apparaten geblokkeerd door voorwaardelijke toegang.

### <a name="common-issues-for-connector-configurations"></a>Veelvoorkomende problemen voor connector configuraties

- **Accountmachtigingen**: Zorg ervoor dat u in het dialoogvenster Microsoft Intune Exchange Connector een gebruikersaccount met de juiste machtigingen hebt opgegeven voor het uitvoeren van de [vereiste Windows PowerShell Exchange-cmdlets](exchange-connector-install.md#exchange-cmdlet-requirements).
- **E-mail berichten met meldingen**: meldingen inschakelen en een meldings account opgeven.
- **Synchronisatie van de server voor client toegang**: Geef bij het configureren van Exchange connector een certificerings instantie op die de laagste netwerk latentie heeft die mogelijk is voor de server die als host fungeert voor de Exchange connector. Vertragingen in de communicatie tussen de CAS en de Exchange-connector kunnen leiden tot vertraging bij het detecteren van apparaten, vooral als Exchange Online Dedicated wordt gebruikt.
- **Synchronisatieschema**: mogelijk krijgt een gebruiker met een nieuw ingeschreven apparaat pas toegang nadat de Exchange-connector synchroniseert met de Exchange CAS. Een volledige synchronisatie vindt elke dag plaats en een (snelle) deltasynchronisatie vindt meerdere keren per dag plaats. U kunt [een snelle synchronisatie of volledige synchronisatie handmatig forceren](exchange-connector-install.md#manually-force-a-quick-sync-or-full-sync) om vertragingen te minimaliseren.

## <a name="next-steps"></a>Volgende stappen
De volgende artikelen kunnen helpen bij het oplossen van veelvoorkomende problemen en specifieke fouten:

- [Los veelvoorkomende problemen voor de intune Exchange connector op](troubleshoot-exchange-connector-common-problems.md).
- [Los veelvoorkomende fouten op voor de intune Exchange connector](troubleshoot-exchange-connector-common-errors.md).

Hulp vragen over ondersteuning of de intune-Community:

- Zie [ondersteuning](../fundamentals/get-support.md) voor het gebruik van de intune-console voor hulp bij het oplossen van het probleem of voor het openen van een ondersteunings aanvraag bij micro soft. 
- Plaats uw probleem in de [Microsoft intune forums](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod).  
