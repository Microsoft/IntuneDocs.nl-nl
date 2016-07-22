---
# required metadata

title: De Microsoft Intune Exchange Connector configureren voor gehoste Exchange | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 05fa5dc9-9bad-4557-987a-9b8ce4edebb0

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# De Intune Service to Service Connector configureren voor gehoste Exchange

Gebruik deze informatie om verbinding maken met Microsoft Intune en de Exchange Online-service die wordt gehost door Office 365.

## Vereisten voor de Service to Service Connector
De **Service to Service Connector** ondersteunt alleen gehoste Exchange en heeft geen vereisten voor een lokale infrastructuur.

|Vereiste|Meer informatie|
|---------------|--------------------|
|Gehoste Exchange geconfigureerd en actief|[Exchange Online](https://technet.microsoft.com/library/jj200580.aspx) |
|Instantie voor beheer van mobiele apparaten| [De instantie voor het beheer van mobiele apparaten instellen op Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority)|
|Microsoft Exchange-versie|U moet een Office 365-abonnement met een Exchange Server-tenant van 2013 of later hebben. Als de tenant Exchange Server 2013 of later is, biedt de connector ondersteuning voor Exchange Server 2010 in diezelfde omgeving.|
|Active Directory-synchronisatie|Voordat u de Intune Connector kunt gebruiken, moet u [Active Directory-synchronisatie instellen](/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3), zodat uw lokale gebruikers en beveiligingsgroepen worden gesynchroniseerd met uw exemplaar van Azure Active Directory.|

### Vereisten voor Exchange-cmdlets

U moet ook een Exchange Online-gebruikersaccount maken dat wordt gebruikt door de Intune Exchange Connector. Het account moet gemachtigd zijn om de Intune-beheerconsole te gebruiken en om deze vereiste Windows PowerShell Exchange-cmdlets uit te voeren.

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

## De Service to Service Connector instellen

1. Open de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) met een gebruikersaccount met Exchange-beheerdersrechten en machtigingen voor [bovenstaande](#exchange-cmdlet-requirements) cmdlets. Microsoft Intune gebruikt het e-mailadres van de momenteel aangemelde gebruiker om de verbinding in te stellen.

2.  Kies in het deelvenster met snelkoppelingen de optie **Beheer** en ga vervolgens naar **Beheer van mobiele apparaten** > **Microsoft Exchange** > **Exchange-verbinding instellen**..
![De pagina Service to Service Connector instellen](../media/intunesa5cservicetoserviceconnector.png)

3.  Klik op de pagina **Exchange-verbinding instellen** op **Service to Service Connector instellen**..


De Service to Service Connector wordt automatisch geconfigureerd en gesynchroniseerd met uw gehoste Exchange-omgeving.

## De Exchange-verbinding valideren

Nadat u de Exchange Connector hebt geconfigureerd, klikt u in de Intune-beheerconsole op de werkruimte **Beheer** en gaat u naar **Beheer van mobiele apparaten** > **Microsoft Exchange** en controleert u of de details die u hebt opgegeven, worden vermeld onder **Exchange-verbindingsgegevens**..

U kunt ook de tijd en datum van de laatste geslaagde synchronisatiepoging controleren.


<!--HONumber=May16_HO1-->


