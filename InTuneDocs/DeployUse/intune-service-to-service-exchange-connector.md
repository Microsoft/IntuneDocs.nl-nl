---
title: Exchange Connector voor Exchange Online | Microsoft Intune
description: Verbinding maken met Intune Office 365 Exchange-service voor ondersteuning van Exchange ActiveSync MDM (beheer van mobiele apparaten).
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 05fa5dc9-9bad-4557-987a-9b8ce4edebb0
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c880bd9dfb998355a18e78af898a96d4cee393f7
ms.openlocfilehash: a6438bb3ca21e5c46dca5ebe69266fd9bce9a4b8


---

# De Intune Service to Service Connector configureren voor gehoste Exchange

Gebruik deze informatie om verbinding maken met Microsoft Intune en Exchange Online of de nieuwe Exchange Online Dedicated-service. Neem contact op met uw accountmanager om te bepalen of uw Exchange Online Dedicated-omgeving de **nieuwe** of **verouderde** configuratie heeft. Intune ondersteunt slechts één type Exchange Connector-verbinding per abonnement.

## Vereisten voor de Service to Service Connector
De **Service to Service Connector** ondersteunt alleen Exchange Online of nieuwe Exchange Online Dedicated en heeft geen vereisten voor een lokale infrastructuur.

|Vereiste|Meer informatie|
|---------------|--------------------|
|Exchange Online geconfigureerd en actief|[Exchange Online](https://technet.microsoft.com/library/jj200580.aspx) |
|Instantie voor beheer van mobiele apparaten| [De instantie voor het beheer van mobiele apparaten instellen op Microsoft Intune](prerequisites-for-enrollment.md#set-mobile-device-management-authority)|
|Microsoft Exchange-versie|Exchange Online en nieuwe Exchange Online Dedicated-service|
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

2.  Kies in het deelvenster met snelkoppelingen de optie **Beheer** en ga vervolgens naar **Beheer van mobiele apparaten** > **Microsoft Exchange** > **Exchange-verbinding instellen**.
![De pagina Service to Service Connector instellen](../media/intunesa5cservicetoserviceconnector.png)

3.  Klik op de pagina **Exchange-verbinding instellen** op **Service to Service Connector instellen**.


De Service to Service Connector wordt automatisch geconfigureerd en gesynchroniseerd met uw Exchange Online- of nieuwe Exchange Online Dedicated-omgeving.

## De Exchange-verbinding valideren

Nadat u de Exchange Connector hebt geconfigureerd, kiest u in de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) de werkruimte **Beheer** en gaat u naar **Beheer van mobiele apparaten**  > **Microsoft Exchange** en controleert u of de details die u hebt opgegeven, worden weergegeven onder **Exchange-verbindingsgegevens**.

U kunt ook de tijd en datum van de laatste geslaagde synchronisatiepoging controleren.



<!--HONumber=Sep16_HO4-->


