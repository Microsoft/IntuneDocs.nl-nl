---
title: Microsoft Intune on-premises Exchange-connector instellen
titleSuffix: Microsoft Intune
description: Gebruik de on-premises Exchange-connector om apparaattoegang tot Exchange-postvakken op basis van inschrijving bij Intune en Exchange Active Sync (EAS) te beheren.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a0376ea1-eb13-4f13-84da-7fd92d8cd63c
ms.reviewer: demerson
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3724f2494dd4e4fe7939a9be87a30e1bc5bfbf27
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/23/2019
ms.locfileid: "61513527"
---
# <a name="set-up-the-intune-on-premises-exchange-connector-in-microsoft-intune"></a>De Intune on-premises Exchange-connector instellen in Microsoft Intune
De informatie in dit artikel helpt u bij het installeren en vervolgens controleren van de on-premises Exchange Active Sync-connector voor Intune.  U gebruikt de Intune on-premises Exchange-connector met uw [beleid voor voorwaardelijke toegang om toegang tot uw on-premises Exchange-postvakken toe te staan of te blokkeren](conditional-access-exchange-create.md). 

Wanneer een apparaat toegang tot uw on-premises Exchange probeert te krijgen, worden EAS-records (Exchange Active Syn) in Exchange Server met de Exchange-connector toegewezen aan Intune-records om op apparaatinschrijving met Intune en naleving van uw beleid voor apparaten te controleren. Afhankelijk van uw beleid voor voorwaardelijke toegang kan aan het apparaat toegang worden verleend of geblokkeerd. Zie [What are common ways to use conditional access with Intune?](conditional-access-intune-common-ways-use.md) (Wat zijn gebruikelijke manieren om voorwaardelijke toegang met Intune te gebruiken?) voor meer informatie.

Intune ondersteunt de installatie van meerdere on-premises Exchange-connectors per abonnement. Als u meer dan een on-premises Exchange-organisatie hebt, kunt u voor elke organisatie een afzonderlijke connector instellen. U kunt echter slechts één connector voor elke afzonderlijke Exchange-organisatie installeren. 

Hieronder vindt u de algemene stappen voor het instellen van een verbinding waarmee Intune kan communiceren met de on-premises Exchange Server:

1. Download de Intune on-premises Exchange-connector vanuit de Intune-portal.
2. Installeer en configureer de Exchange-connector op een computer in de on-premises Exchange-organisatie.
3. Valideer de Exchange-verbinding.
4. Herhaal deze stappen voor elke aanvullende Exchange-organisatie die u wilt koppelen aan Intune.

## <a name="intune-on-premises-exchange-connector-requirements"></a>Vereisten voor Intune On-premises Exchange-connector
U moet beschikken over een account met een Intune-licentie dat door de connector kan worden gebruikt om verbinding te maken met Exchange. Het account wordt opgegeven wanneer u de connector installeert.  

De volgende tabel bevat de vereisten voor de computer waarop u de on-premises Exchange-connector installeert.  

|  Vereiste  |   Meer informatie     |
|---------------|------------------------|
|  Besturingssystemen        | Intune ondersteunt de on-premises Exchange-connector op een computer waarop een versie van Windows Server 2008 SP2 64-bits, Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2 of Windows Server 2016 wordt uitgevoerd.<br /><br />De connector wordt niet ondersteund op een Server Core-installatie.  |
| Microsoft Exchange          | On-premises connectors vereisen Microsoft Exchange 2010 SP3 of hoger, of het oudere Exchange Online Dedicated. Om te bepalen of uw omgeving met Exchange Online-specifiek de <strong>nieuwe</strong> of <strong>verouderde</strong> configuratie heeft, neemt u contact op met uw accountmanager. |
| Instantie voor beheer van mobiele apparaten           | [De instantie voor het beheer van mobiele apparaten instellen op Intune](mdm-authority-set.md). |
| Hardware              | De computer waarop u de connector installeert, vereist een 1,6 GHz CPU met 2 GB RAM-geheugen en 10 GB aan vrije schijfruimte. |
|  Active Directory-synchronisatie             | Voordat u de connector kunt gebruiken om Intune te verbinden met uw Exchange-server, moet u [Active Directory-synchronisatie instellen](users-add.md), zodat uw lokale gebruikers en beveiligingsgroepen worden gesynchroniseerd met uw exemplaar van Azure Active Directory. |
| Aanvullende software         | Een volledige installatie van Microsoft .NET Framework 4.5 en Windows PowerShell 2.0 moet worden geïnstalleerd op de computer die als host fungeert voor de connector. |
| Netwerk               | De computer waarop u de connector installeert, moet zich in een domein bevinden dat een vertrouwensrelatie heeft met het domein dat als host fungeert voor uw Exchange-server.<br /><br />Voor de computer zijn configuraties vereist die de computer toegang geven tot de Intune-service via firewalls en proxyservers via de poorten 80 en 443. Domeinen die door Intune worden gebruikt, zijn onder meer manage.microsoft.com, &#42;manage.microsoft.com en &#42;.manage.microsoft.com. |

### <a name="exchange-cmdlet-requirements"></a>Vereisten voor Exchange-cmdlets

Maak een Active Directory-gebruikersaccount dat wordt gebruikt door de on-premises Exchange-connector. Het account moet gemachtigd zijn om de volgende vereiste Windows PowerShell Exchange-cmdlets uit te voeren:


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

2. Ga naar **Intune** > **Exchange-toegang**  

3. Kies onder **Setup** de optie **On-premises Exchange ActiveSync-connector** en selecteer vervolgens **Toevoegen**.

4. Selecteer op de pagina **Connector toevoegen** de optie **De on-premises connector downloaden**. De on-premises Exchange-connector bevindt zich in een gecomprimeerde map (.zip) die kan worden geopend of opgeslagen. Kies in het dialoogvenster **Bestand downloaden** de optie **Opslaan** om de gecomprimeerde map op een veilige locatie op te slaan.

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

4. Geef in de velden **Gebruiker (Domein\gebruiker)** en **Wachtwoord** de referenties op die nodig zijn om verbinding te maken met de Exchange-server. Aan het account dat u opgeeft, moet een licentie voor Intune zijn toegewezen. 

5. Geef de vereiste referenties op om meldingen te verzenden naar het Exchange Server-postvak van een gebruiker. Deze gebruiker kan worden toegewezen aan alleen meldingen. De meldingengebruiker moet een Exchange-postvak hebben om meldingen te verzenden via e-mail. U kunt deze meldingen configureren met beleid voor voorwaardelijke toegang in Intune.  

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
Intune ondersteunt meerdere on-premises Exchange-connectors per abonnement. Voor een tenant met meerdere Exchange-organisaties kunt u een connector voor elke Exchange-organisatie instellen. U kunt echter per organisatie slechts één connector instellen. 

Als u connectors installeert om verbinding te maken met meerdere Exchange-organisaties, downloadt u de gecomprimeerde map één keer en gebruikt u dezelfde download opnieuw voor elke connector die u installeert. Volg voor elke aanvullende connector de stappen in de vorige sectie om het installatieprogramma uit te pakken en uit te voeren op een server in de Exchange-organisatie.

De functies voor hoge beschikbaarheid, bewaking en handmatige synchronisatie die in de volgende secties worden beschreven, worden ondersteund voor elke Exchange-organisatie die wordt verbonden met Intune.

## <a name="on-premises-exchange-connector-high-availability-support"></a>Hoge beschikbaarheid van on-premises Exchange Connector 
Hoge beschikbaarheid voor de on-premises Exchange-connector betekent dat de connector een andere Client Access Server (CAS) voor een Exchange-organisatie kan gebruiken als de door de connector gebruikte Exchange CAS niet meer beschikbaar is voor die Exchange-organisatie. De Exchange-connector zelf biedt geen ondersteuning voor hoge beschikbaarheid. Als de connector mislukt, is er geen automatische failover en moet u die connector vervangen door [een nieuwe connector te installeren](#reinstall-the-on-premises-exchange-connector). 

Om failover uit te voeren detecteert de connector na het tot stand brengen van een verbinding met Exchange met de opgegeven CAS aanvullende CAS-exemplaren voor die Exchange-organisatie. Door op de hoogte te zijn van aanvullende CAS-exemplaren is failover naar een andere CAS mogelijk als deze beschikbaar is totdat de primaire CAS beschikbaar komt. Detectie van aanvullende CAS-exemplaren is standaard ingeschakeld. U kunt failover als volgt uitschakelen:  
1. Op de server waar de Exchange-connector is geïnstalleerd, gaat u naar %*ProgramData*%\Microsoft\Windows Intune Exchange Connector. 
2. Open **OnPremisesExchangeConnectorServiceConfiguration.xml** met behulp van een teksteditor.
3. Wijzig &lt;IsCasFailoverEnabled&gt;**true**&lt;/IsCasFailoverEnabled&gt; in &lt;IsCasFailoverEnabled&gt;**false** &lt;/IsCasFailoverEnabled&gt; om de functie uit te schakelen.    
 

## <a name="reinstall-the-on-premises-exchange-connector"></a>De on-premises Exchange-connector opnieuw installeren
U moet mogelijk een Exchange-connector opnieuw installeren. Omdat er één connector wordt ondersteund om verbinding te maken met elke Exchange-organisatie, vervangt de tweede connector die u voor een organisatie installeert de oorspronkelijke connector.

1. Gebruik de stappen bij [De Intune on-premises Exchange-connector installeren en configureren](#install-and-configure-the-intune-on-premises-exchange-connector) om de installatie van een nieuwe connector te starten. 
2. Wanneer u hierom wordt gevraagd, selecteert u **Vervangen** om de nieuwe connector te installeren.  
   ![Configuratieprompt om een connector te vervangen](./media/exchange-connector-install/prompt-to-replace.png)

3. Ga door met de stappen van de vorige procedure en meld u opnieuw aan bij Intune.
4. Wanneer het laatste scherm wordt weergegeven, selecteert u **Sluiten** om de installatie te voltooien.  
   ![Installatie voltooien](./media/exchange-connector-install/successful-reinstall.png)
 

## <a name="monitor-the-exchange-connector-activity"></a>De activiteit van de Exchange-connector controleren

Nadat u de Exchange-connector hebt geconfigureerd, kunt u de status van de verbindingen en de laatste geslaagde synchronisatiepoging weergeven. De verbinding van de Exchange-connector valideren:

1. Kies op het Intune-dashboard de optie **Exchange-toegang**.
2. Selecteer **On-premises toegang tot Exchange** om de verbindingsstatus voor elke Exchange-verbinding te verifiëren.

U kunt ook de tijd en datum van de laatste geslaagde synchronisatiepoging controleren.
--> 

### <a name="system-center-operations-manager-management-pack"></a>Management pack van System Center Operations Manager

Vanaf release 1710 Intune kunt u het [management pack Operations Manager voor Exchange-connector en Intune](https://www.microsoft.com/download/details.aspx?id=55990&751be11f-ede8-5a0c-058c-2ee190a24fa6=True&e6b34bbe-475b-1abd-2c51-b5034bcdd6d2=True&fa43d42b-25b5-4a42-fe9b-1634f450f5ee=True) gebruiken. U kunt met het management pack de Exchange-connector op verschillende manieren controleren wanneer u problemen moet oplossen.

## <a name="manually-force-a-quick-sync-or-full-sync"></a>Een snelle synchronisatie of een volledige synchronisatie handmatig forceren
Een on-premises Exchange-connector synchroniseert regelmatig automatisch EAS- en Intune-apparaatrecords. Als de nalevingsstatus van een apparaat wordt gewijzigd, worden met het proces van automatische synchronisatie regelmatig records bijgewerkt zodat apparaattoegang kan worden geblokkeerd of toegestaan.

   - **Snelle synchronisatie** vindt regelmatig plaats, meerdere keren per dag. Een snelle synchronisatie haalt apparaatinformatie op voor gebruikers met een Intune-licentie en on-premises voorwaardelijke Exchange-toegang die zijn gewijzigd sinds de laatste synchronisatie.

   - **Volledige synchronisatie** vindt standaard eenmaal per dag plaats. Een volledige synchronisatie haalt apparaatinformatie op voor alle gebruikers met een Intune-licentie en on-premises voorwaardelijke Exchange-toegang. Een volledige synchronisatie haalt ook gegevens over de Exchange-server op en zorgt ervoor dat de door Intune opgegeven configuratie in de Azure-portal wordt bijgewerkt op de Exchange-server. 


U kunt afdwingen dat een connector een synchronisatie uitvoert door de volgende stappen te volgen en de opties **Snelle synchronisatie** of **Volledige synchronisatie** op het Intune-dashboard te gebruiken:

   1. Kies op het Intune-dashboard de optie **Exchange-toegang**.
   2. Selecteer **On-premises toegang tot Exchange**.
   3. Selecteer de connector die u wilt synchroniseren en kies vervolgens **Snelle synchronisatie** of **Volledige synchronisatie**.

## <a name="next-steps"></a>Volgende stappen
[Een beleid maken voor voorwaardelijke toegang voor Exchange On-Premises](conditional-access-exchange-create.md)
