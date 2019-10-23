---
title: Gegevens die JAMF Pro verzendt naar Intune
titleSuffix: Microsoft Intune
description: Bekijk de lijst met gegevens die Jamf Pro naar Microsoft Intune verzendt, wanneer u Jamf Pro integreert om Macs te beheren met Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e4bf6df44335f3375d58d3c2c11da7cb3f982b3e
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72502417"
---
# <a name="data-jamf-pro-sends-to-intune"></a>Gegevens die Jamf Pro verzendt naar Intune

Wanneer u [Jamf Pro](https://www.jamf.com) gebruikt voor het beheren van de Macs van uw eindgebruikers, legt Jamf Pro inventarisinformatie vast over beheerde macOS-apparaten. 

## <a name="data"></a>Gegevens  
Zie [Appendix: Inventarisgegevens die worden gedeeld met Microsoft Intune](https://docs.jamf.com/technical-papers/jamf-pro/microsoft-intune/10.9.0/Appendix__Inventory_Information_Shared_with_Microsoft_Intune.html) in de technische documentatie over Jamf Pro voor de lijst met gegevens van Jamf Pro die worden gedeeld met Intune. 

<!--  
Jamf Pro reports the following information to Intune:  

* Device Azure AD ID
* JAMF Inventory State (inventory state of a computer checked in with Jamf Pro within the last 24 hours)
* OS Version
* User Azure AD ID
* Encrypted (FileVault 2)
* Gatekeeper Status
* Password: minimum number of character sets
* Password expiration (days)
* Password Type - simple, alphanumeric, or unknown
* Prevent Auto Login
* Required Passcode Length
* Password: number of previous passwords to prevent reuse
* System Integrity Protection
* Last Check-In Time
* Architecture Type
* Available RAM Slots
* Battery Capacity
* Boot ROM
* Bus Speed
* Cache Size
* Device Name
* Domain Join
* Jamf ID
* MAC address
* Make
* Model
* Model Identifier
* NIC Speed
* Number of Cores
* Number of Processors
* OS
* Platform
* Processor Speed
* Processor Type
* Secondary MAC Address
* Serial Number
* SMC Version
* Total RAM
* UDID
* User Email
--> 

<!-- 
You can remove a Jamf-managed device from the Intune console by selecting **Delete** in the **All devices** view. Bulk device deletion can be enabled by selecting multiple devices and clicking **Delete**.
-->

## <a name="next-steps"></a>Volgende stappen
U vindt meer informatie over [het verwijderen van door Jamf beheerde apparaten in de Jamf Pro-documenten](https://www.jamf.com/jamf-nation/articles/80/unmanaging-computers-while-preserving-their-inventory-information). U kunt ook een ondersteuningsticket indienen met [Jamf-ondersteuning](https://www.jamf.com/support/) voor meer informatie. 

