---
title: Microsoft Intune Exchange Connector instellen
titleSuffix: Microsoft Intune
description: Gebruik de on-premises Intune Exchange-connector om apparaattoegang tot Exchange-postvakken op basis van inschrijving bij Intune en Exchange Active Sync (EAS) te beheren.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/24/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a0376ea1-eb13-4f13-84da-7fd92d8cd63c
ms.reviewer: demerson
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7d00fec5efd9caa54c7f481389e3993e9797699c
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/26/2020
ms.locfileid: "76755719"
---
# <a name="set-up-the-on-premises-intune-exchange-connector"></a>De on-premises Intune Exchange-connector instellen

Voor het beveiligen van de toegang tot Exchange is Intune afhankelijk van het on-premises onderdeel Microsoft Intune Exchange Connector. Deze connector wordt op sommige plaatsen in de Intune-console ook wel de *On-premises Exchange ActiveSync-connector* genoemd.

Met behulp van de informatie in dit artikel kunt u Microsoft Intune Exchange Connector installeren en controleren. U kunt de connector met uw [beleid voor voorwaardelijke toegang](conditional-access-exchange-create.md) gebruiken om toegang tot uw on-premises Exchange-postvakken toe te staan of te blokkeren.

De connector wordt geïnstalleerd en uitgevoerd op uw on-premises hardware. Hiermee worden apparaten gedetecteerd die verbinding maken met Exchange, waardoor de apparaatgegevens worden gecommuniceerd naar de Intune-service. Met de connector kunnen apparaten worden toegestaan of geblokkeerd op basis van het feit of de apparaten zijn ingeschreven en voldoen aan het beleid. Voor deze communicatie wordt het HTTPS-protocol gebruikt.

Wanneer een apparaat toegang tot uw on-premises Exchange-server probeert te krijgen, worden EAS-records (Exchange Active Sync) in Exchange Server met de Exchange-connector toegewezen aan Intune-records om te controleren of het apparaat is ingeschreven bij Intune en voldoet aan uw beleid voor apparaten. Afhankelijk van uw beleid voor voorwaardelijke toegang kan het apparaat toegang worden verleend of worden geblokkeerd. Zie [What are common ways to use conditional access with Intune?](conditional-access-intune-common-ways-use.md) (Wat zijn gebruikelijke manieren om voorwaardelijke toegang met Intune te gebruiken?) voor meer informatie.

De bewerkingen voor het *detecteren* en *toestaan en blokkeren* worden uitgevoerd via standaard PowerShell-cmdlets voor Exchange. Bij deze bewerkingen wordt gebruikgemaakt van het serviceaccount dat is opgegeven bij het installeren van de Exchange-connector.

Intune ondersteunt de installatie van meerdere Intune Exchange-connectors per abonnement. Als u meer dan een on-premises Exchange-organisatie hebt, kunt u voor elke organisatie een afzonderlijke connector instellen. U kunt echter slechts één connector per Exchange-organisatie installeren.  

Volg deze algemene stappen voor het instellen van een verbinding waarmee Intune kan communiceren met de on-premises Exchange-server:

1. Download de on-premises connector vanuit de Intune-portal.
2. Installeer en configureer de Exchange-connector op een computer in de on-premises Exchange-organisatie.
3. Valideer de Exchange-verbinding.
4. Herhaal deze stappen voor elke aanvullende Exchange-organisatie die u wilt koppelen aan Intune.

## <a name="intune-exchange-connector-requirements"></a>Vereisten voor Intune Exchange Connector

Voor de verbinding met Exchange moet u beschikken over een account met een Intune-licentie dat door de connector kan worden gebruikt. U geeft het account op wanneer u de connector installeert.  

De volgende tabel bevat de vereisten voor de computer waarop u de Intune Exchange-connector installeert.  

|  Vereiste  |   Meer informatie     |
|---------------|------------------------|
|  Besturingssystemen        | Intune ondersteunt de Intune Exchange-connector op een computer waarop een versie van Windows Server 2008 SP2 64-bits, Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2 of Windows Server 2016 wordt uitgevoerd.<br /><br />De connector wordt niet ondersteund op een Server Core-installatie.  |
| Microsoft Exchange          | On-premises connectors vereisen Microsoft Exchange 2010 SP3 of hoger, of het oudere Exchange Online Dedicated. Om te bepalen of uw omgeving met Exchange Online-specifiek de *nieuwe* of *verouderde* configuratie heeft, neemt u contact op met uw accountmanager. |
| Instantie voor beheer van mobiele apparaten           | [De instantie voor het beheer van mobiele apparaten instellen op Intune](../fundamentals/mdm-authority-set.md). |
| Hardware              | De computer waarop u de connector installeert, vereist een 1,6 GHz CPU met 2 GB RAM-geheugen en 10 GB aan vrije schijfruimte. |
|  Active Directory-synchronisatie             | Voordat u de connector gebruikt om Intune te verbinden met uw Exchange-server, moet u de [Active Directory-synchronisatie instellen](../fundamentals/users-add.md). Uw lokale gebruikers en beveiligingsgroepen moeten worden gesynchroniseerd met uw exemplaar van Azure Active Directory. |
| Aanvullende software         | Op de computer die als host fungeert voor de connector moet een volledige installatie van Microsoft .NET Framework 4.5 en Windows PowerShell 2.0 worden geïnstalleerd. |
| Netwerk               | De computer waarop u de connector installeert, moet zich in een domein bevinden dat een vertrouwensrelatie heeft met het domein dat als host fungeert voor uw Exchange-server.<br /><br />Configureer de computer zo dat deze toegang heeft tot de Intune-service via firewalls en proxyservers via de poorten 80 en 443. Intune maakt gebruik van deze domeinen: <br> - manage.microsoft.com <br> - \*manage.microsoft.com<br> - \*.manage.microsoft.com <br><br> De Intune Exchange-connector communiceert met de volgende services: <br> - Intune service: HTTPS-poort 443 <br> - Exchange-server voor clienttoegang (CAS): WinRM-servicepoort 443<br> - Exchange Autodiscover 443<br> - Exchange-webservices (EWS) 443  |

### <a name="exchange-cmdlet-requirements"></a>Vereisten voor Exchange-cmdlets

Maak een Active Directory-gebruikersaccount voor de Intune Exchange-connector. Het account moet gemachtigd zijn om de volgende Windows PowerShell Exchange-cmdlets uit te voeren:  

- `Get-ActiveSyncOrganizationSettings`, `Set-ActiveSyncOrganizationSettings`
- `Get-CasMailbox`, `Set-CasMailbox`
- `Get-ActiveSyncMailboxPolicy`, `Set-ActiveSyncMailboxPolicy`, `New-ActiveSyncMailboxPolicy`, `Remove-ActiveSyncMailboxPolicy`
- `Get-ActiveSyncDeviceAccessRule`, `Set-ActiveSyncDeviceAccessRule`, `New-ActiveSyncDeviceAccessRule`, `Remove-ActiveSyncDeviceAccessRule`
- `Get-ActiveSyncDeviceStatistics`
- `Get-ActiveSyncDevice`
- `Get-ExchangeServer`
- `Get-ActiveSyncDeviceClass`
- `Get-Recipient`
- `Clear-ActiveSyncDevice`, `Remove-ActiveSyncDevice`
- `Set-ADServerSettings`
- `Get-Command`

## <a name="download-the-installation-package"></a>Het installatiepakket downloaden

Op een Windows-server met ondersteuning voor de Intune Exchange-connector:

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).  Gebruik een account dat een beheerdersaccount is op de on-premises Exchange-server en een licentie heeft voor het gebruik van Exchange-server.

2. Selecteer **Tenantbeheer** > **Toegang tot Exchange**.

3. Kies onder **Setup** de optie **On-premises Exchange ActiveSync-connector** en selecteer vervolgens **Toevoegen**.

   > [!div class="mx-imgBorder"]
   > ![Een on-premises Exchange ActiveSync-connector toevoegen](./media/exchange-connector-install/add-connector.png)

4. Selecteer op de pagina **Connector toevoegen** de optie **De on-premises connector downloaden**. De Intune Exchange-connector bevindt zich in een gecomprimeerde map (.zip) die kan worden geopend of opgeslagen. Kies in het dialoogvenster **Bestand downloaden** de optie **Opslaan** om de gecomprimeerde map op te slaan op een veilige locatie.

## <a name="install-and-configure-the-intune-exchange-connector"></a>De Intune Exchange-connector installeren en configureren

Volg deze stappen om de Intune Exchange-connector te installeren. Als u meerdere Exchange-organisaties hebt, herhaalt u deze stappen voor elke Exchange-connector die u wilt instellen.

1. Pak op een ondersteund besturingssysteem voor de Intune Exchange-connector de bestanden in **Exchange_Connector_Setup.zip** uit op een veilige locatie.
   > [!IMPORTANT]
   > Wijzig of verplaats de bestanden in de map *Exchange_Connector_Setup* niet. Anders mislukt de installatie van de connector.

2. Nadat de bestanden zijn uitgepakt, opent u de map waarin de bestanden zijn uitgepakt en dubbelklikt u op **Exchange_Connector_Setup.exe** om de connector te installeren.

   > [!IMPORTANT]
   > Als de doelmap geen veilige locatie is, verwijdert u het certificaatbestand *MicrosoftIntune.accountcert* nadat u de on-premises connectors hebt geïnstalleerd.

3. Selecteer in het dialoogvenster **Microsoft Intune Exchange Connector** de optie **On-premises Microsoft Exchange Server** of **Gehoste Microsoft Exchange Server**.

   ![Afbeelding van waar u uw type Exchange Server kunt kiezen](./media/exchange-connector-install/intune-sa-exchange-connector-config.png)

   Voor een On-Premises Exchange-server geeft u de servernaam of de FQDN-naam van de Exchange-server op die als host fungeert voor de **serverfunctie voor clienttoegang**.

   Voor een gehoste Exchange-server geeft u het adres van de Exchange-server op. De URL van de gehoste Exchange-server zoeken:

   1. Open Outlook voor Office 365.

   2. Kies het pictogram **?** in de linkerbovenhoek en selecteer **Over**.

   3. Zoek de waarde **POP van externe server**.

   4. Kies **Proxyserver** om proxyserverinstellingen op te geven voor de gehoste Exchange-server.

       1. Selecteer **Proxyserver gebruiken bij synchroniseren van gegevens van mobiel apparaat**.

       1. Voer de **proxyservernaam** en het **poortnummer** in die moeten worden gebruikt voor toegang tot de server.

       1. Als gebruikersreferenties vereist zijn om toegang te krijgen tot de proxyserver, selecteert u **Referenties gebruiken om verbinding te maken met de proxyserver**. Voer vervolgens de **domein\gebruiker** en het **wachtwoord** in.

       1. Kies **OK**.

4. Geef in de velden **Gebruiker (domein\gebruiker)** en **Wachtwoord** de referenties voor de verbinding met de Exchange-server op. Aan het account dat u opgeeft, moet een licentie voor Intune zijn toegewezen.

5. Geef referenties op om meldingen te verzenden naar het Exchange Server-postvak van een gebruiker. Deze gebruiker kan worden toegewezen aan alleen meldingen. De meldingengebruiker moet een Exchange-postvak hebben om meldingen te verzenden via e-mail. U kunt deze meldingen configureren met behulp van beleid voor voorwaardelijke toegang in Intune.

   Zorg ervoor dat de Autodiscover-service en de Exchange-webservices zijn geconfigureerd op de Exchange-server voor clienttoegang (CAS). Zie [Server voor clienttoegang](https://technet.microsoft.com/library/dd298114.aspx) voor meer informatie.

6. Geef in het veld **Wachtwoord** het wachtwoord voor dit account op om Intune in te schakelen voor toegang tot de Exchange-server.

   > [!NOTE]
   > Het account waarmee u zich aanmeldt bij de tenant moet ten minste een Intune-servicebeheerder zijn. Zonder dit beheerdersaccount krijgt u een mislukte verbinding met de fout 'De externe server heeft een fout geretourneerd: (400) Ongeldige aanvraag'.

7. Kies **Verbinding maken**.

   > [!NOTE]
   > Het configureren van de verbinding kan enkele minuten duren.

Tijdens het configureren slaat de Exchange-connector uw proxy-instellingen voor toegang tot internet op. Als de proxy-instellingen worden gewijzigd, configureert u de Exchange-connector opnieuw om de bijgewerkte proxy-instellingen toe te passen op de Exchange-connector.

Nadat de Exchange-connector de verbinding heeft ingesteld, worden de mobiele apparaten die zijn gekoppeld aan in Exchange beheerde gebruikers automatisch gesynchroniseerd en toegevoegd aan de Exchange-connector. Het kan enige tijd duren voordat deze synchronisatie is voltooid.

> [!NOTE]
> Als u de Intune Exchange connector installeert en u later de Exchange-verbinding moet verwijderen, moet u de connector verwijderen van de computer waarop deze is geïnstalleerd.

## <a name="install-connectors-for-multiple-exchange-organizations"></a>Connectors installeren voor meerdere Exchange-organisaties

Intune ondersteunt meerdere Intune Exchange-connectors per abonnement. Voor een tenant met meerdere Exchange-organisaties kunt u slechts één connector per Exchange-organisatie instellen.

Als u connectors wilt installeren om verbinding te maken met meerdere Exchange-organisaties, moet u de map (.zip) één keer downloaden. Gebruik dezelfde download voor elke connector die u installeert. Volg voor elke aanvullende connector de stappen in de vorige sectie om het installatieprogramma uit te pakken en uit te voeren op een server in de Exchange-organisatie.

Elke Exchange-organisatie die verbinding maakt met Intune, ondersteunt hoge beschikbaarheid, bewaking en handmatige synchronisatie. In de volgende secties worden deze functies beschreven.

## <a name="on-premises-intune-exchange-connector-high-availability-support"></a>Ondersteuning voor hoge beschikbaarheid van on-premises Intune Exchange-connector  

Hoge beschikbaarheid voor de on-premises connector betekent dat de connector een andere Client Access Server (CAS) voor een Exchange-organisatie kan gebruiken als de door de connector gebruikte Exchange CAS niet meer beschikbaar is voor die Exchange-organisatie. De Exchange-connector zelf biedt geen ondersteuning voor hoge beschikbaarheid. Als de connector mislukt, is er geen automatische failover en moet u [een nieuwe connector installeren](#reinstall-the-intune-exchange-connector) om de mislukte connector te vervangen.

Voor een failover moet de connector de opgegeven CAS gebruiken om een verbinding met Exchange tot stand te brengen. Vervolgens worden er extra servers voor clienttoegang voor die Exchange-organisatie gedetecteerd. Door deze detectie is failover naar een andere CAS mogelijk als deze beschikbaar is totdat de primaire CAS beschikbaar komt.

Detectie van aanvullende CAS-exemplaren is standaard ingeschakeld. U kunt failover zo nodig als volgt uitschakelen:

1. Op de server waar de Exchange-connector is geïnstalleerd, gaat u naar **%*ProgramData*%\Microsoft\Windows Intune Exchange Connector**.

2. Open **OnPremisesExchangeConnectorServiceConfiguration.xml** met behulp van een teksteditor.

3. Wijzig **\<IsCasFailoverEnabled>*true*\</IsCasFailoverEnabled>** in **\<IsCasFailoverEnabled>*false*\</IsCasFailoverEnabled>** .

## <a name="performance-tune-the-exchange-connector-optional"></a>Prestatie-afstemming voor de Exchange-connector (optioneel)

Als 5000 of meer apparaten worden ondersteund met Exchange ActiveSync, kunt u een optionele instelling configureren om de prestaties van de connector te verbeteren. U kunt de prestaties verbeteren door voor Exchange in te stellen dat er meerdere exemplaren van een PowerShell-runspace voor opdrachten mogen worden gebruikt.

Voordat u deze wijziging aanbrengt, controleert u of het account dat u gebruikt voor Exchange Connector niet wordt gebruikt voor andere Exchange-beheerdoeleinden. Een Exchange-account heeft een beperkt aantal runspaces, waarvan de meeste door de connector worden gebruikt.

De prestaties kunnen niet worden verbeterd voor connectors die worden uitgevoerd op oudere of langzamere hardware.

De prestaties van de Exchange-connector verbeteren:

1. Open de installatiemap van de connector op de server waarop de connector is geïnstalleerd.  De standaardlocatie is *C:\ProgramData\Microsoft\Windows Intune Exchange Connector*.

2. Bewerk het bestand *OnPremisesExchangeConnectorServiceConfiguration.xml*.

3. Zoek **EnableParallelCommandSupport** en stel de waarde in op **true**:

   \<EnableParallelCommandSupport>true\</EnableParallelCommandSupport>

4. Sla het bestand op en start de Microsoft Intune Exchange Connector-service opnieuw op.

## <a name="reinstall-the-intune-exchange-connector"></a>De Intune Exchange-connector opnieuw installeren

U moet mogelijk een Intune Exchange-connector opnieuw installeren. Omdat u slechts met één connector verbinding kunt maken met een Exchange-organisatie, vervangt de nieuwe connector die u voor de organisatie installeert de oorspronkelijke connector.

1. Als u de nieuwe connector wilt installeren, volgt u de stappen in de sectie [De Exchange-connector installeren en configureren](#install-and-configure-the-intune-exchange-connector).

2. Wanneer u hierom wordt gevraagd, selecteert u **Vervangen** om de nieuwe connector te installeren.
   ![Configuratiewaarschuwing voor het vervangen van een connector](./media/exchange-connector-install/prompt-to-replace.png)

3. Ga door met de stappen in de sectie [De Intune Exchange-connector installeren en configureren](#install-and-configure-the-intune-exchange-connector) en meld u opnieuw aan bij Intune.

4. Selecteer in het laatste venster **Sluiten** om de installatie te voltooien.
   ![Installatie voltooien](./media/exchange-connector-install/successful-reinstall.png)

## <a name="monitor-an-exchange-connector"></a>Een Exchange-connector controleren

Wanneer u de Exchange-connector hebt geconfigureerd, kunt u de status van de verbindingen en de laatste geslaagde synchronisatiepoging weergeven:

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecteer **Tenantbeheer** > **Toegang tot Exchange**.

3. Selecteer **On-premises Exchange ActiveSync-connector** en selecteer vervolgens de connector die u wilt weergeven.

4. De console geeft gegevens weer voor de door u geselecteerde connector, waar u de **Status** en de datum en tijd van de laatste geslaagde synchronisatie kunt bekijken.

Naast de status in de console kunt u het [management pack System Center Operations Manager voor Exchange-connector en Intune](https://www.microsoft.com/download/details.aspx?id=55990&751be11f-ede8-5a0c-058c-2ee190a24fa6=True&e6b34bbe-475b-1abd-2c51-b5034bcdd6d2=True&fa43d42b-25b5-4a42-fe9b-1634f450f5ee=True) gebruiken. Met het management pack kunt u de Exchange-connector op verschillende manieren controleren wanneer u problemen moet oplossen.

## <a name="manually-force-a-quick-sync-or-full-sync"></a>Een snelle synchronisatie of een volledige synchronisatie handmatig forceren

Een Intune Exchange-connector synchroniseert regelmatig automatisch EAS- en Intune-apparaatrecords. Als de nalevingsstatus van een apparaat wordt gewijzigd, worden met het proces van automatische synchronisatie regelmatig records bijgewerkt zodat apparaattoegang kan worden geblokkeerd of toegestaan.

- Een **snelle synchronisatie** vindt regelmatig plaats, meerdere keren per dag. Een snelle synchronisatie haalt apparaatinformatie op voor gebruikers met een Intune-licentie en on-premises voorwaardelijke Exchange-toegang die zijn gewijzigd sinds de laatste synchronisatie.

- Een **volledige synchronisatie** vindt standaard één keer per dag plaats. Een volledige synchronisatie haalt apparaatinformatie op voor alle gebruikers met een Intune-licentie en on-premises voorwaardelijke Exchange-toegang. Een volledige synchronisatie haalt ook informatie over de Exchange-server op en zorgt ervoor dat de door Intune opgegeven configuratie in de Azure-portal wordt bijgewerkt op de Exchange-server.

U kunt afdwingen dat een connector een synchronisatie uitvoert door de optie **Snelle synchronisatie** of **Volledige synchronisatie** op het Intune-dashboard te gebruiken:

   1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).

   2. Selecteer **Tenantbeheer** > **Exchange-toegang** >  **On-premises Exchange ActiveSync-connector**.

   3. Selecteer de connector die u wilt synchroniseren en kies vervolgens Snelle synchronisatie of Volledige synchronisatie.

   > [!div class="mx-imgBorder"]
   > ![Voorbeeldschermopname van connectorgegevens](./media/exchange-connector-install/connector-details.png)

## <a name="next-steps"></a>Volgende stappen

Maak een [beleid voor voorwaardelijke toegang voor on-premises Exchange-servers](conditional-access-exchange-create.md).
