---
title: Microsoft Intune on-premises Exchange-connector instellen | Microsoft Intune
description: Gebruik de on-premises Exchange-connector om apparaattoegang tot Exchange-postvakken op basis van inschrijving bij Intune en Exchange Active Sync (EAS) te beheren.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/02/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a0376ea1-eb13-4f13-84da-7fd92d8cd63c
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4481645781e21da4f433f5feae1d685efb73d412
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55841416"
---
# <a name="set-up-the-intune-on-premises-exchange-connector-in-microsoft-intune-azure"></a>Intune on-premises Exchange-connector instellen in Microsoft Intune Azure

In een on-premises Exchange Server-omgeving kan voorwaardelijke toegang van Intune worden gebruikt om toegang tot on-premises Exchange-postvakken te blokkeren of toe te staan. Gebruik on-premises Exchange Active Sync-connectors om Intune te verbinden met uw Exchange-organisaties en stel voorwaardelijke Intune-toegang in samen met het nalevingsbeleid voor apparaten. Wanneer een apparaat dan verbinding maakt met Exchange, bepaalt Intune of het apparaat is ingeschreven bij Intune en conform het beleid is. Om te bepalen welke apparaten zijn ingeschreven bij Intune, wijst de on-premises Exchange-connector Exchange Active Sync-records (EAS) in Exchange Server toe aan Intune-records. Zie [Wat zijn gebruikelijke manieren om voorwaardelijke toegang met Intune te gebruiken?](conditional-access-intune-common-ways-use.md) voor meer informatie over hoe dit werkt.

> [!IMPORTANT]
> Intune ondersteunt nu meerdere on-premises Exchange-connectors per abonnement. Als u meer dan één on-premises Exchange-organisatie hebt, kunt u voor elke Exchange-organisatie een afzonderlijke connector instellen.

Als u een verbinding wilt instellen waarmee Microsoft Intune kan communiceren met de on-premises Exchange-Server, volgt u deze algemene stappen:

1.  Download de Intune on-premises Exchange-connector van de Azure-portal.
2.  Installeer en configureer de Exchange-connector op een computer in de on-premises Exchange-organisatie.
3.  Valideer de Exchange-verbinding.
4. Herhaal deze stappen voor elke Exchange-organisatie die u wilt koppelen aan Intune.

## <a name="intune-on-premises-exchange-connector-requirements"></a>Vereisten voor Intune On-premises Exchange-connector
De volgende tabel bevat de vereisten voor de computer waarop u de on-premises Exchange-connector installeert.


|            Vereiste             |                                                                                                                                                                                                        Meer informatie                                                                                                                                                                                                        |
|------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         Besturingssystemen          |                                                               Intune ondersteunt de on-premises Exchange-connector op een computer waarop een versie van Windows Server 2008 SP2 64-bits, Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2 of Windows Server 2016 wordt uitgevoerd.<br /><br />De connector wordt niet ondersteund op een Server Core-installatie.                                                                |
|         Microsoft Exchange         |                                                                           On-premises connectors vereisen Microsoft Exchange 2010 SP3 of hoger, of het oudere Exchange Online Dedicated. Om te bepalen of uw omgeving met Exchange Online-specifiek de <strong>nieuwe</strong> of <strong>verouderde</strong> configuratie heeft, neemt u contact op met uw accountmanager.                                                                           |
| Instantie voor beheer van mobiele apparaten |                                                                                                                              [De instantie voor het beheer van mobiele apparaten instellen op Intune](mdm-authority-set.md).                                                                                                                               |
|              Hardware              |                                                                                                                                                     De computer waarop u de connector installeert, vereist een 1,6 GHz CPU met 2 GB RAM-geheugen en 10 GB aan vrije schijfruimte.                                                                                                                                                      |
|  Active Directory-synchronisatie  |                                                                                      Voordat u de connector kunt gebruiken om Intune te verbinden met uw Exchange-server, moet u [Active Directory-synchronisatie instellen](users-add.md), zodat uw lokale gebruikers en beveiligingsgroepen worden gesynchroniseerd met uw exemplaar van Azure Active Directory.                                                                                      |
|        Aanvullende software         |                                                                                                                                           Een volledige installatie van Microsoft .NET Framework 4.5 en Windows PowerShell 2.0 moet worden geïnstalleerd op de computer die als host fungeert voor de connector.                                                                                                                                           |
|              Netwerk               | De computer waarop u de connector installeert, moet zich in een domein bevinden dat een vertrouwensrelatie heeft met het domein dat als host fungeert voor uw Exchange-server.<br /><br />Voor de computer zijn configuraties vereist die de computer toegang geven tot de Intune-service via firewalls en proxyservers via de poorten 80 en 443. Domeinen die door Intune worden gebruikt, zijn onder meer manage.microsoft.com, &#42;manage.microsoft.com en &#42;.manage.microsoft.com. |

### <a name="exchange-cmdlet-requirements"></a>Vereisten voor Exchange-cmdlets

U moet een Active Directory-gebruikersaccount maken dat wordt gebruikt door de on-premises Exchange-connector. Het account moet gemachtigd zijn om de volgende vereiste Windows PowerShell Exchange-cmdlets uit te voeren:


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

## <a name="download-the-on-premises-exchange-connector-software-installation-package"></a>Het software-installatiepakket voor de on-premises Exchange-connector downloaden

1. Open [Azure Portal](https://portal.azure.com) in een ondersteund Windows Server-besturingssysteem voor de on-premises Exchange-connector en meld u aan met een gebruikersaccount dat een beheerder is voor de on-premises Exchange-server en dat een licentie heeft om Exchange Server te gebruiken.

2. Kies **Alle services** in het linkermenu en typ dan **Intune** in het filtertekstvak.

3. Kies **Intune**. Wanneer het Intune-dashboard wordt geopend, kiest u **On-premises toegang**.

4. Kies onder **Instellen** de optie **Exchange ActiveSync-connectors** en kies **De on-premises connector downloaden**.

5.  De on-premises Exchange-connector bevindt zich in een gecomprimeerde map (.zip) die kan worden geopend of opgeslagen. Kies in het dialoogvenster **Bestand downloaden** de optie **Opslaan** om de gecomprimeerde map op een veilige locatie op te slaan.

    > [!IMPORTANT]
    > Wijzig of verplaats de bestanden in de on-premises Exchange-connector-map niet. Als er inhoud van de map wordt hernoemd of verplaatst, wordt de installatie van de Exchange-connector afgebroken.

## <a name="install-and-configure-the-intune-on-premises-exchange-connector"></a>De Intune on-premises Exchange-connector installeren en configureren
Voer de volgende stappen uit om de Intune on-premises Exchange-connector te installeren. Als u meerdere Exchange-organisaties hebt, herhaalt u deze stappen voor elke extra Exchange-connector die u wilt instellen.

1. Pak op een ondersteund besturingssysteem voor de on-premises Exchange-connector de bestanden in **Exchange_Connector_Setup.zip** uit op een veilige locatie.

2. Nadat de bestanden zijn uitgepakt, opent u de map waarin de bestanden zijn uitgepakt en dubbelklikt u op **Exchange_Connector_Setup.exe** om de on-premises Exchange-connector te installeren.

   > [!IMPORTANT]
   > Als de doelmap geen veilige locatie is, verwijdert u het certificaatbestand **MicrosoftIntune.accountcert** wanneer u de on-premises connectors hebt geïnstalleerd.

3. Selecteer in het dialoogvenster **Microsoft Intune Exchange Connector** de optie **On-premises Microsoft Exchange Server** of **Gehoste Microsoft Exchange Server**.

   ![Afbeelding van waar u uw type Exchange Server kunt kiezen](./media/intune-sa-exchange-connector-config.png)

   Voor een On-Premises Exchange-server geeft u de servernaam of de FQDN-naam van de Exchange-server op die als host fungeert voor de **serverfunctie voor clienttoegang**.

   Voor een gehoste Exchange-server geeft u het adres van de Exchange-server op. De URL van de gehoste Exchange-server zoeken:

   1. Open Outlook op het web voor Office 365.

   2. Kies het pictogram **?** linksboven en selecteer **Over**.

   3. Zoek de waarde **POP van externe server**.

   4. Kies **Proxyserver** om proxyserverinstellingen op te geven voor de gehoste Exchange-server.
       1. Selecteer **Proxyserver gebruiken bij synchroniseren van gegevens van mobiel apparaat**.

       2. Voer de **proxyservernaam** en het **poortnummer** in die moeten worden gebruikt voor toegang tot de server.

       3. Als u gebruikersreferenties moet opgeven om toegang te krijgen tot de proxyserver, selecteert u **Referenties gebruiken om verbinding te maken met de proxyserver**. Voer vervolgens de **domein\gebruiker** en het **wachtwoord** in.

       4. Kies **OK**.

4. Geef in de velden **Gebruiker (Domein\gebruiker)** en **Wachtwoord** de referenties op die nodig zijn om verbinding te maken met de Exchange-server.

5. Geef de vereiste referenties op om meldingen te verzenden naar het Exchange Server-postvak van een gebruiker. Deze gebruiker kan worden toegewezen aan alleen meldingen. De meldingengebruiker moet een Exchange-postvak hebben om meldingen te kunnen verzenden via e-mail. U kunt deze meldingen configureren met beleid voor voorwaardelijke toegang in Intune.  

       Ensure that the Autodiscover service and Exchange Web Services are configured on the Exchange Client Access Server. For more information, see [Client Access server](https://technet.microsoft.com/library/dd298114.aspx).

6. Geef in het veld **Wachtwoord** het wachtwoord voor dit account op om Intune in te schakelen voor toegang tot de Exchange-server.

7. Kies **Verbinding maken**.

   > [!NOTE]
   > Het kan enkele minuten duren voordat de verbinding is geconfigureerd.

Tijdens het configureren slaat de Exchange-connector uw proxy-instellingen voor toegang tot internet op. Als de proxy-instellingen worden gewijzigd, moet u de Exchange-connector opnieuw configureren om de bijgewerkte proxy-instellingen toe te passen op de Exchange-connector.

Nadat de Exchange-connector de verbinding heeft ingesteld, worden de mobiele apparaten die zijn gekoppeld aan gebruikers die worden beheerd in Exchange, automatisch gesynchroniseerd en toegevoegd aan de Exchange-connector. Het kan enige tijd duren voordat deze synchronisatie is voltooid.

> [!NOTE]
> Als u de on-premises Exchange-connector hebt geïnstalleerd en u op een bepaald moment de Exchange-verbinding verwijdert, moet u de on-premises Exchange-connector verwijderen van de computer waarop deze is geïnstalleerd.

## <a name="install-connectors-for-multiple-exchange-organizations"></a>Connectors installeren voor meerdere Exchange-organisaties
Intune ondersteunt meerdere on-premises Exchange-connectors per abonnement. Voor een tenant met meerdere Exchange-organisaties kunt u een connector voor elke Exchange-organisatie instellen. Download de map .zip eenmaal en volg dan voor elke Exchange-organisatie de stappen in de vorige sectie om het installatieprogramma uit te pakken en uit te voeren op een server in de organisatie.

De functies voor hoge beschikbaarheid, bewaking en handmatige synchronisatie die in de volgende secties worden beschreven, worden ondersteund voor elke Exchange-organisatie die is verbonden met Intune.

## <a name="on-premises-exchange-connector-high-availability-support"></a>Hoge beschikbaarheid van on-premises Exchange Connector 
Nadat de Exchange Connector verbinding heeft gemaakt met Exchange met behulp van de opgegeven CAS, kan de connector andere CAS-instanties detecteren. Als de primaire CAS niet beschikbaar is, zoekt de connector naar een andere CAS (indien beschikbaar) totdat de primaire CAS beschikbaar komt. Deze functie is standaard ingeschakeld. U kunt deze functie als volgt uitschakelen:
1. Op de server waar de Exchange Connector is geïnstalleerd, gaat u naar %*ProgramData*%\Microsoft\Windows Intune Exchange Connector. 
2. Open **OnPremisesExchangeConnectorServiceConfiguration.xml** met behulp van een teksteditor.
3. Wijzig &lt;IsCasFailoverEnabled&gt;**true**&lt;/IsCasFailoverEnabled&gt; in &lt;IsCasFailoverEnabled&gt;**false** &lt;/IsCasFailoverEnabled&gt; om de functie uit te schakelen.    


## <a name="monitor-the-exchange-connector-activity"></a>De activiteit van de Exchange-connector controleren

Nadat u de Exchange-connectors hebt geconfigureerd, kunt u de status van de verbindingen en de laatste geslaagde synchronisatiepoging weergeven. De verbindingen van de Exchange-connector valideren:

1. Kies op het Intune-dashboard de optie **On-premises toegang**.
2. Selecteer onder **Instellen** de optie **Exchange ActiveSync-connectors** om de status van de verbinding voor elke Exchange-connector te controleren.

U kunt ook de tijd en datum van de laatste geslaagde synchronisatiepoging controleren.

### <a name="system-center-operations-manager-management-pack"></a>Management pack van System Center Operations Manager

Vanaf release 1710 Intune kunt u het [management pack Operations Manager voor Exchange-connector en Intune](https://www.microsoft.com/download/details.aspx?id=55990&751be11f-ede8-5a0c-058c-2ee190a24fa6=True&e6b34bbe-475b-1abd-2c51-b5034bcdd6d2=True&fa43d42b-25b5-4a42-fe9b-1634f450f5ee=True) gebruiken. Hiermee kunt u de Exchange-connector op verschillende manieren controleren wanneer u problemen moet oplossen.

## <a name="manually-force-a-quick-sync-or-full-sync"></a>Een snelle synchronisatie of een volledige synchronisatie handmatig forceren
Een on-premises Exchange-connector synchroniseert regelmatig automatisch EAS- en Intune-apparaatrecords. Als de nalevingsstatus van een apparaat wijzigt, werkt het proces van automatische synchronisatie regelmatig records bij zodat apparaattoegang dienovereenkomstig kan worden geblokkeerd of toegestaan.

   - **Snelle synchronisatie** vindt regelmatig plaats, meerdere keren per dag. Een snelle synchronisatie haalt apparaatinformatie op voor gebruikers met een Intune-licentie en on-premises voorwaardelijke Exchange-toegang die zijn gewijzigd sinds de laatste synchronisatie.

   - **Volledige synchronisatie** vindt standaard eenmaal per dag plaats. Een volledige synchronisatie haalt apparaatinformatie op voor alle gebruikers met een Intune-licentie en on-premises voorwaardelijke Exchange-toegang. Een volledige synchronisatie haalt ook gegevens over de Exchange-server op en zorgt ervoor dat de door Intune opgegeven configuratie in de Azure-portal wordt bijgewerkt op de Exchange-server. 

U kunt afdwingen dat een connector een synchronisatie uitvoert door de volgende stappen te volgen en de opties **Snelle synchronisatie** of **Volledige synchronisatie** op het Intune-dashboard te gebruiken:

   1. Kies op het Intune-dashboard de optie **On-premises toegang**.
   2. Kies onder **Instellen** de optie **Exchange Active Sync-Connectors**.
   3. Selecteer de connector die u wilt synchroniseren en kies vervolgens **Snelle synchronisatie** of **Volledige synchronisatie**.

## <a name="next-steps"></a>Volgende stappen
[Een beleid maken voor voorwaardelijke toegang voor Exchange On-Premises](conditional-access-exchange-create.md)
