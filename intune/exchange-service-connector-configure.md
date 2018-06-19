---
title: Intune Exchange Connector voor Exchange Online
titleSuffix: ''
description: Verbinding maken met Intune Office 365 Exchange-service voor ondersteuning van Exchange ActiveSync MDM (beheer van mobiele apparaten).
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 640d1a5cbd785248cb309bc250c95631295955b3
ms.sourcegitcommit: 71497f0215fc8bed454ac318b0548b1281a8fe0f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/08/2018
ms.locfileid: "33914152"
---
# <a name="configure-the-exchange-service-connector-for-intune-and-exchange-online"></a>De Exchange Connector-service configureren voor Intune en Exchange Online

In dit artikel leest u hoe u de Microsoft Intune-service verbindt met Exchange Online of de nieuwe Exchange Online Dedicated-service. Neem contact op met uw accountmanager om te bepalen of uw Exchange Online Dedicated-omgeving de **nieuwe** of **verouderde** versie is.

## <a name="service-to-service-connector-requirements"></a>Vereisten voor de Service to Service-connector
De **Service to Service Connector** ondersteunt alleen Exchange Online of Exchange Online Dedicated en heeft geen vereisten voor een on-premises infrastructuur.


|              Vereiste               |                                                                                                            Meer informatie                                                                                                            |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Exchange Online geconfigureerd en actief |                                                                                 [Exchange Online](https://technet.microsoft.com/library/jj200580.aspx)                                                                                 |
|   Instantie voor beheer van mobiele apparaten   |                                                       [De instantie voor het beheer van mobiele apparaten instellen op Microsoft Intune](mdm-authority-set.md)                                                       |
|       Microsoft Exchange-versie       |                                                                                      Exchange Online of de nieuwe Exchange Online Dedicated-service                                                                                      |
|    Active Directory-synchronisatie    | Voordat u de Intune Connector kunt gebruiken, moet u [Active Directory-synchronisatie instellen](/intune/users-add), zodat uw lokale gebruikers en beveiligingsgroepen worden gesynchroniseerd met uw exemplaar van Azure Active Directory. |

### <a name="exchange-cmdlet-requirements"></a>Vereisten voor Exchange-cmdlets

U moet ook een Exchange Online-gebruikersaccount maken dat wordt gebruikt door de Intune Exchange-serviceconnector. Het account moet gemachtigd zijn om de volgende vereiste Windows PowerShell Exchange-cmdlets uit te voeren:

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

## <a name="set-up-the-service-to-service-connector"></a>De Servicesconnector instellen

1. Meld u bij de [Azure Portal](http://portal.azure.com) aan met een gebruikersaccount met Exchange-beheerdersrechten en machtigingen voor de [eerder genoemde](#exchange-cmdlet-requirements) cmdlets. Microsoft Intune gebruikt het e-mailadres van de momenteel aangemelde gebruiker om de verbinding in te stellen.

2. Kies **Alle services** in het linkermenu en typ dan **Intune** in het filtertekstvak.

3. Kies **Intune** om het Microsoft Intune-dashboard te openen. Kies **Voorwaardelijke toegang** en kies onder **Setup** de optie **Exchange-serviceconnector**.

4.  Op de pagina **Voorwaardelijke toegang - Exchange-serviceconnector** kiest u **Service to Service Connector instellen**. 
   
     ![Afbeelding van het selecteren van de koppeling Service to Service Connector instellen](media/exchange_service_connector.png)

De Service to Service Connector wordt automatisch geconfigureerd en gesynchroniseerd met uw Exchange Online- of nieuwe Exchange Online Dedicated-omgeving.

## <a name="validate-your-exchange-connection"></a>De Exchange-verbinding valideren

Nadat u de Service to Service Connector hebt geconfigureerd, kunt u de gegevens van de Exchange Connector-server valideren op de pagina **Voorwaardelijke toegang - Exchange-serviceconnector**.

U kunt ook de **verbindingsstatus** en de tijd en datum van de laatste geslaagde synchronisatiepoging controleren.

## <a name="next-steps"></a>Volgende stappen
[Voorwaardelijke toegang voor Exchange in Microsoft Intune controleren](conditional-access-exchange-monitor.md)