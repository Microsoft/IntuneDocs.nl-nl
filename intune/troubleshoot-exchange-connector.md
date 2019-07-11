---
title: Problemen met Exchange Connector oplossen
titleSuffix: Microsoft Intune
description: Problemen met betrekking tot de Intune on-premises Exchange-connector oplossen.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/18/2018
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
ms.openlocfilehash: 5bdb727b542cd66e0b8fcf4a0822eaf0107600ad
ms.sourcegitcommit: 1dc9d4e1d906fab3fc46b291c67545cfa2231660
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 07/10/2019
ms.locfileid: "67735727"
---
# <a name="troubleshoot-the-intune-on-premises-exchange-connector"></a>Problemen met de Intune on-premises Exchange-connector oplossen

In dit artikel wordt beschreven hoe u problemen met betrekking tot de Intune on-premises Exchange-connector kunt oplossen.

## <a name="steps-for-checking-the-connector-configuration"></a>Stappen voor het controleren van de connectorconfiguratie 

Controleer de [installatie van de Intune on-premises Exchange-connector](exchange-connector-install.md) om ervoor te zorgen dat de connector correct is geconfigureerd. Hieronder vindt u enkele veelvoorkomende problemen. Nadat u wijzigingen hebt aangebracht, controleert u of het probleem is opgelost.

- Zorg ervoor dat u in het dialoogvenster Microsoft Intune Exchange Connector een gebruikersaccount met de juiste machtigingen hebt opgegeven voor het uitvoeren van de [vereiste Windows PowerShell Exchange-cmdlets](exchange-connector-install.md#exchange-cmdlet-requirements).
- Schakel meldingen in en geef een meldingsaccount op.
- Wanneer u de Exchange-connector configureert, geeft u een Client Access Server (CAS) op die zich zo dicht mogelijk bij de server bevindt die als host fungeert voor de Exchange-connector. Vertragingen in de communicatie tussen de CAS en de Exchange-connector kunnen leiden tot vertraging bij het detecteren van apparaten, vooral als Exchange Online Dedicated wordt gebruikt.
- Mogelijk krijgt een gebruiker met een nieuw ingeschreven apparaat pas toegang nadat de Exchange-connector synchroniseert met de Exchange CAS. Een volledige synchronisatie vindt elke dag plaats en een (snelle) deltasynchronisatie vindt meerdere keren per dag plaats.  U kunt [een snelle synchronisatie of volledige synchronisatie handmatig forceren](exchange-connector-install.md#manually-force-a-quick-sync-or-full-sync) om vertragingen te minimaliseren.
 
## <a name="exchange-activesync-device-not-discovered-from-exchange"></a>Een Exchange ActiveSync-apparaat wordt niet gedetecteerd door Exchange
[Controleer de activiteit van de Exchange-connector](exchange-connector-install.md#on-premises-exchange-connector-high-availability-support) om te zien of de connector wordt gesynchroniseerd met de Exchange-server. Als een volledige of snelle synchronisatie is uitgevoerd sinds het apparaat is toegevoegd, kunt u controleren of zich andere mogelijke problemen voordoen (zie hieronder). Als er geen synchronisatie heeft plaatsgevonden, moet u de synchronisatielogboeken verzamelen en deze bij uw ondersteuningsaanvraag voegen.

- Zorg ervoor dat gebruikers een licentie voor Intune hebben. Anders kunnen hun apparaten niet worden gedetecteerd door de Exchange-connector.
- Als het primaire SMTP-adres van een gebruiker anders is dan de UPN in Azure AD (Azure Active Directory), detecteert de Exchange-connector geen enkel apparaat voor die gebruiker. Corrigeer het primaire SMTP-adres om het probleem op te lossen.
- Als u zowel een Exchange 2010- als Exchange 2013-postvakserver in uw omgeving hebt, kunt u de Exchange-connector het beste laten verwijzen naar een Exchange 2013-CAS. Als u dit niet doet, kan de Exchange-connector die is ingesteld om te communiceren met een Exchange 2010-CAS, geen Exchange 2013-apparaten van gebruikers detecteren. 
- Voor omgevingen met Exchange Online Dedicated moet u de Exchange-connector tijdens de eerste installatie laten verwijzen naar een Exchange 2013-CAS (geen Exchange 2010-CAS) in de toegewezen omgeving, omdat de connector bij het uitvoeren van Powershell-cmdlets alleen met deze CAS communiceert.


## <a name="using-powershell-to-get-more-data-on-exchange-connector-issues"></a>Powershell gebruiken om meer gegevens over problemen met de Exchange Connector te verkrijgen
- Gebruik Get-ActiveSyncDeviceStatistics -mailbox mbx om een lijst met alle mobiele apparaten voor een postvak op te halen
- Gebruik Get-Mailbox -Identity user | select emailaddresses | fl om een lijst van SMTP-adressen voor een postvak op te halen
- Gebruik Get-CASMailbox <upn> | fl om gedetailleerde informatie over de toegangsstatus van een apparaat op te halen

### <a name="next-steps"></a>Volgende stappen
Als deze informatie geen oplossing biedt, kunt u ook [ondersteuning voor Microsoft Intune krijgen](get-support.md).
