---
title: Exchange Connector voor Exchange Online
description: Verbinding maken met Intune Office 365 Exchange-service voor ondersteuning van Exchange ActiveSync MDM (beheer van mobiele apparaten).
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 07/29/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 05fa5dc9-9bad-4557-987a-9b8ce4edebb0
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 8af8d79d6f8ea9037c6bef532ad45185830c358d
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="configure-the-intune-service-to-service-connector-for-exchange-online"></a>De Intune Service to Service Connector configureren voor Exchange Online

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Gebruik deze informatie om verbinding te maken met Microsoft Intune en Exchange Online of de nieuwe Exchange Online Dedicated-service. Neem contact op met uw accountmanager om te bepalen of uw Exchange Online Dedicated-omgeving de **nieuwe** of **verouderde** versie is. Intune ondersteunt slechts één type Exchange Connector-verbinding per abonnement.

## <a name="service-to-service-connector-requirements"></a>Vereisten voor de Service to Service-connector
De **Service to Service Connector** ondersteunt alleen Exchange Online of Exchange Online Dedicated en heeft geen vereisten voor een lokale infrastructuur.


|              Vereiste               |                                                                                                            Meer informatie                                                                                                            |
|----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Exchange Online geconfigureerd en actief |                                                                                 [Exchange Online](https://technet.microsoft.com/library/jj200580.aspx)                                                                                 |
|   Instantie voor beheer van mobiele apparaten   |                                                       [De instantie voor het beheer van mobiele apparaten instellen op Microsoft Intune](prerequisites-for-enrollment.md#step-2-set-mdm-authority)                                                       |
|       Microsoft Exchange-versie       |                                                                                      Exchange Online of de nieuwe Exchange Online Dedicated-service                                                                                      |
|    Active Directory-synchronisatie    | Voordat u de Intune Connector kunt gebruiken, moet u [Active Directory-synchronisatie instellen](/intune/users-permissions-add), zodat uw lokale gebruikers en beveiligingsgroepen worden gesynchroniseerd met uw exemplaar van Azure Active Directory. |

### <a name="exchange-cmdlet-requirements"></a>Vereisten voor Exchange-cmdlets

U moet ook een Exchange Online-gebruikersaccount maken dat wordt gebruikt door de Intune Exchange Connector. Het account moet gemachtigd zijn om de Intune-beheerconsole te gebruiken en om de volgende Windows PowerShell Exchange-cmdlets uit te voeren:

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

## <a name="set-up-the-service-to-service-connector"></a>De Servicesconnector instellen

1. Open de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) met een gebruikersaccount met Exchange-beheerdersrechten en machtigingen voor de [eerder genoemde](#exchange-cmdlet-requirements) cmdlets. Microsoft Intune gebruikt het e-mailadres van de momenteel aangemelde gebruiker om de verbinding in te stellen.

2.  Kies in het deelvenster met snelkoppelingen de optie **Beheer**>**Beheer van mobiele apparaten** > **Microsoft Exchange** > **Exchange-verbinding instellen**.
![De pagina Service to Service Connector instellen](../media/intunesa5cservicetoserviceconnector.png)

3.  Klik op de pagina **Exchange-verbinding instellen** op **Service to Service Connector instellen**.


De Service to Service Connector wordt automatisch geconfigureerd en gesynchroniseerd met uw Exchange Online- of nieuwe Exchange Online Dedicated-omgeving.

## <a name="validate-your-exchange-connection"></a>De Exchange-verbinding valideren

Ga naar de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) nadat u de Exchange Connector hebt geconfigureerd. Kies **Beheer**> **Beheer van mobiele apparaten** > **Microsoft Exchange**. Controleer vervolgens of de door u ingevoerde gegevens worden weergegeven onder **Exchange verbindingsgegevens**.

U kunt ook de tijd en datum van de laatste geslaagde synchronisatiepoging controleren.
