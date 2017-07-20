---
title: De Exchange Connector voor on-premises EAS instellen met Intune
titleSuffix: Intune Azure
description: 'Intune Azure : Exchange ActiveSync MDM: gebruik het Connector-hulpprogramma voor het inschakelen van de communicatie tussen Intune- en de on-premises Exchange Server'
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a0376ea1-eb13-4f13-84da-7fd92d8cd63c
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1dd5143ce6c604f416af1c6b6b1df684346e2f6d
ms.sourcegitcommit: be12974a7eaa4ce9cffe45aabe456c858d582e20
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2017
---
# <a name="set-up-the-intune-on-premises-exchange-connector-in-microsoft-intune-azure"></a>Intune on-premises Exchange Connector instellen in Microsoft Intune Azure

In on-premises Exchange Server-omgevingen kunt u de Intune on-premises Exchange connector voor gebruiken om de toegang van apparaten tot lokale Exchange-postvakken te beheren op basis van het feit of de apparaten zijn ingeschreven bij Intune en voldoen aan het Intune-nalevingsbeleid voor apparaten. De on-premises Exchange Connector is tevens verantwoordelijk voor het detecteren van mobiele apparaten die verbinding maken met on-premises Exchange-Servers door het bestaande EAS-record (Exchange Active Sync ) te synchroniseren met Intune.

> [!IMPORTANT]
> Intune ondersteunt slechts één type on-premises Exchange Connector-verbinding per abonnement.

Als u een verbinding wilt instellen waarmee Microsoft Intune kan communiceren met de on-premises Exchange-Server, volgt u de volgende stappen:

1.  Download de Intune on-premises Exchange Connector van de Intune-portal.
2.  Installeer en configureer de Intune on-premises Exchange Connector.
3.  Valideer de Exchange-verbinding.

## <a name="on-premises-exchange-connector-requirements"></a>Vereisten voor On-premises Exchange Connector
De volgende tabel bevat de vereisten voor de computer waarop u On-premises Exchange Connector installeert.

|Vereiste|Meer informatie|
|---------------|--------------------|
|Besturingssystemen|Intune ondersteunt On-premises Exchange Connector op een computer waarop een versie van Windows Server 2008 SP2 64-bits, Windows Server 2008 R2, Windows Server 2012 of Windows Server 2012 R2 wordt uitgevoerd.<br /><br />Connector wordt niet ondersteund op een Server Core-installatie.|
|Microsoft Exchange|On-premises Connector vereist Microsoft Exchange 2010 SP1 of hoger, of het oudere Exchange Online-specifiek. Om te bepalen of uw omgeving met Exchange Online-specifiek de **nieuwe** of **verouderde** configuratie heeft, neemt u contact op met uw accountmanager.|
|Instantie voor beheer van mobiele apparaten| [De instantie voor het beheer van mobiele apparaten instellen op Intune](https://docs.microsoft.com/intune-classic/deploy-use/prerequisites-for-enrollment#step-2-mdm-authority-set).|
|Hardware|De computer waarop u de connector installeert, vereist een 1,6 GHz CPU met 2 GB RAM-geheugen en 10 GB aan vrije schijfruimte.|users- add.md
|Active Directory-synchronisatie|Voordat u Connector kunt gebruiken om Intune te verbinden met uw Exchange-server, moet u [Active Directory-synchronisatie instellen](users-add.md), zodat uw lokale gebruikers en beveiligingsgroepen worden gesynchroniseerd met uw exemplaar van Azure Active Directory.|
|Aanvullende software|Een volledige installatie van Microsoft .NET Framework 4.5 en Windows PowerShell 2.0 moet worden geïnstalleerd op de computer die als host fungeert voor de connector.|
|Netwerk|De computer waarop u de connector installeert, moet zich in een domein bevinden dat een vertrouwensrelatie heeft met het domein dat als host fungeert voor uw Exchange-server.<br /><br />Voor de computer zijn configuraties vereist die de computer toegang geven tot de Intune-service via firewalls en proxyservers via de poorten 80 en 443. Domeinen die door Intune worden gebruikt, zijn onder meer manage.microsoft.com, &#42;manage.microsoft.com en &#42;.manage.microsoft.com.|


### <a name="exchange-cmdlet-requirements"></a>Vereisten voor Exchange-cmdlets

U moet een Active Directory-gebruikersaccount maken dat wordt gebruikt door de Intune Exchange Connector. Het account moet gemachtigd zijn om de volgende vereiste Windows PowerShell Exchange-cmdlets uit te voeren:


 -   Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 -   Get-CasMailbox, Set-CasMailbox
 -   Get-ActiveSyncMailboxPolicy, Set-ActiveSyncMailboxPolicy, New-ActiveSyncMailboxPolicy, Remove-ActiveSyncMailboxPolicy
 -   Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 -   Get-ActiveSyncDeviceStatistics
 -   Get-ActiveSyncDevice
 -   Get-ExchangeServer
 -   Get-ActiveSyncDeviceClass
 -   Get-Recipient
 -   Clear-ActiveSyncDevice, Remove-ActiveSyncDevice
 -   Set-ADServerSettings
 -   Get-Command

## <a name="download-the-on-premises-exchange-connector-software-installation-package"></a>Het software-installatiepakket voor On-premises Exchange Connector downloaden

1. Open [Azure Portal](http://portal.azure.com) in een ondersteund Windows Server-besturingssysteem voor on-premises Exchange Connector en meld u aan met een gebruikersaccount dat een beheerder is in de on-premises Exchange-server en dat een licentie heeft om Exchange Server te gebruiken.

2. Kies **Meer services** in het linkermenu en typ dan **Intune** in het vak tekstfilter.

3. Kies **Intune**. Het Intune-dashboard wordt geopend. Kies vervolgens **on-premises toegang**.

4. Kies op de blade **On-premises toegang - Exchange ActiveSync-connector** in de sectie **Instellen**, de optie **De on-premises connector downloaden**.

5.  On-premises Exchange Connector bevindt zich in een gecomprimeerde map (.zip) die kan worden geopend of opgeslagen. Kies in het dialoogvenster **Bestand downloaden** de optie **Opslaan** om de gecomprimeerde map op een veilige locatie op te slaan.

    > [!IMPORTANT]
    > Wijzig of verplaats de bestanden in de on-premises Exchange Connector-map niet. Als er inhoud van de map wordt hernoemd of verplaatst, wordt de installatie van Exchange Connector afgebroken.

## <a name="install-and-configure-the-intune-on-premises-exchange-connector"></a>Intune On-Premises Exchange Connector installeren en configureren
Voer de volgende stappen uit om Intune On-Premises Exchange Connector te installeren. On-Premises Exchange Connector kan maar eenmaal per Intune-abonnement worden geïnstalleerd en slechts op één computer. Als u probeert een extra On-Premises Exchange Connector te configureren, wordt de oorspronkelijke verbinding vervangen door de nieuwe.

1.  Pak op een ondersteund besturingssysteem voor On-Premises Connector de bestanden in **Exchange_Connector_Setup.zip** uit op een veilige locatie.

2.  Nadat de bestanden zijn uitgepakt, opent u de map waarin de bestanden zijn uitgepakt en dubbelklikt u op **Exchange_Connector_Setup.exe** om On-Premises Exchange Connector te installeren.

    > [!IMPORTANT]
    > Als de doelmap geen veilige locatie is, verwijdert u het certificaatbestand **WindowsIntune.accountcert** nadat u On-Premises Connector hebt geïnstalleerd.

3.  Selecteer in het dialoogvenster **Microsoft Intune Exchange Connector** de optie **On-premises Microsoft Exchange Server** of **Gehoste Microsoft Exchange Server**.

  ![Uw type Exchange Server kiezen](./media/intune-sa-exchange-connector-config.png)

  Voor een On-premises Exchange-server geeft u de servernaam of de FQDN-naam van de Exchange-server op die als host fungeert voor de **serverfunctie voor clienttoegang**.

  Voor een gehoste Exchange-server geeft u het adres van de Exchange-server op. De URL van de gehoste Exchange-server zoeken:

    1. Open de Outlook Web App voor Office 365.

    2. Kies het pictogram **?** linksboven en selecteer **Over**.

    3. Zoek de waarde **POP van externe server**.

    4. Kies **Proxyserver** om proxyserverinstellingen op te geven voor de gehoste Exchange-server.
        1. Selecteer **Proxyserver gebruiken bij synchroniseren van gegevens van mobiel apparaat**.

        2. Voer de **proxyservernaam** en het **poortnummer** in die moeten worden gebruikt voor toegang tot de server.

        3. Als u gebruikersreferenties moet opgeven om toegang te krijgen tot de proxyserver, selecteert u **Referenties gebruiken om verbinding te maken met de proxyserver**. Voer vervolgens de **domein\gebruiker** en het **wachtwoord** in.

        4. Kies **OK**.

    5. Geef in de velden **Gebruiker (Domein\gebruiker)** en **Wachtwoord** de referenties op die nodig zijn om verbinding te maken met de Exchange-server.

    6.  Geef de vereiste beheerdersreferenties op om meldingen te verzenden naar het Exchange Server-postvak van een gebruiker. U kunt deze meldingen configureren met beleid voor voorwaardelijke toegang in Intune.

        Zorg ervoor dat de Autodiscover-service en de Exchange-webservices zijn geconfigureerd op de Exchange-server voor clienttoegang. Zie [Server voor clienttoegang](https://technet.microsoft.com/library/dd298114.aspx) voor meer informatie.

    7.  Geef in het veld **Wachtwoord** het wachtwoord voor dit account op om Intune in te schakelen voor toegang tot de Exchange-server.

    8. Kies **Verbinding maken**.

    > [!NOTE]
    > Het kan enkele minuten duren voordat de verbinding is geconfigureerd.

Tijdens het configureren slaat de Exchange Connector uw proxy-instellingen voor toegang tot internet op. Als de proxy-instellingen worden gewijzigd, moet u Exchange Connector opnieuw configureren om de bijgewerkte proxy-instellingen toe te passen op Exchange Connector.

Nadat Exchange Connector de verbinding heeft ingesteld, worden de mobiele apparaten die zijn gekoppeld aan gebruikers die worden beheerd in Exchange Connector, automatisch gesynchroniseerd en toegevoegd aan Exchange Connector. Het kan enige tijd duren voordat deze synchronisatie is voltooid.

> [!NOTE]
> Als u On-Premises Exchange Connector hebt geïnstalleerd en u op een bepaald moment de Exchange-verbinding verwijdert, moet u On-Premises Exchange Connector verwijderen van de computer waarop deze is geïnstalleerd.

## <a name="validate-the-exchange-connection"></a>De Exchange-verbinding valideren

Nadat u de Exchange-Connector hebt geconfigureerd, kunt u de status van de verbinding en de laatste geslaagde synchronisatiepoging weergeven. De Exchange Connector-verbinding valideren:

- Kies op het Intune-dashboard de optie **On-premises toegang**. Selecteer onder **Beheren** de optie **Exchange on-premises toegang** om de status van de verbinding te verifiëren.

U kunt ook de tijd en datum van de laatste geslaagde synchronisatiepoging controleren.

## <a name="next-steps"></a>Volgende stappen
[Een beleid maken voor voorwaardelijke toegang voor Exchange On-Premises](conditional-access-exchange-create.md)
