---
# required metadata

title: Firewall-beleid voor Windows-pc’s | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9549c072-ac3d-4d14-a931-a2eda8846217

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Windows-pc's beschermen met Windows Firewall-beleid in Microsoft Intune
Microsoft Intune kan u helpen de Windows-pc’s die u beheert met de Intune-client, op verschillende manieren te beschermen, met inbegrip van het gebruik van beleidsregels waarmee u Windows Firewall-instellingen kunt configureren op pc’s.

Als u de Intune Windows-pc-client nog niet op uw computers hebt geïnstalleerd, ziet u [Installeer de Windows-pc-client met Windows Intune](install-the-windows-pc-client-with-microsoft-intune.md)..

Gebruik de informatie in de volgende gedeelten bij het configureren, implementeren en controleren van Windows Firewall-beleid op Windows-pc’s.

## Intune-beleid gebruiken voor het beheren van de Windows Firewall
U kunt met het Windows Firewall-beleid instellingen maken en implementeren waarmee Windows Firewall op beheerde pc’s wordt beheerd. U kunt geen aangepaste uitzonderingen voor Windows Firewall beheren en deze instellingen zijn niet van invloed op firewalls van derden.

> [!NOTE]
> Als het beleid van Microsoft Intune en Groepsbeleid zijn geconfigureerd voor dezelfde instelling op de pc, vervangt de instelling van Groepsbeleid het beleid van Microsoft Intune. Zie [Conflicten tussen GPO-beleid en Microsoft Intune-beleid oplossen](resolve-gpo-and-microsoft-intune-policy-conflicts.md) voor informatie over het voorkomen van conflicten tussen beleid van Intune en Groepsbeleid..
>
> Als u Windows Firewall-instellingen wilt implementeren op computers met Windows Vista, moet u eerst [hotfix KB971800](http://support2.microsoft.com/kb/971800) op deze computers installeren.

> [!IMPORTANT]
> Als u Windows Firewall met Intune wilt beheren, moet u ervoor zorgen dat de volgende twee services zijn ingeschakeld op de computers die u wilt beheren:
>
> -   Windows Firewall
> -   IPsec Beleid Agent

## Windows Firewall-beleid configureren

1.  Ga naar de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) en kies **Beleid** &gt; **Beleid toevoegen**..

2.  Configureer en implementeer een beleid voor **Windows Firewall-instellingen**. U kunt de aanbevolen instellingen gebruiken of de instellingen aanpassen. Als u meer informatie wilt over het maken en implementeren van beleid, raadpleegt u [Algemene beheertaken voor Windows-pc’s met de Microsoft Intune-computerclient](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)..

    De volgende sectie biedt een overzicht van de waarden die u kunt configureren in het beleid, evenals de standaardwaarden die worden gebruikt als u het beleid niet aanpast.

Nadat u een Windows Firewall-beleid hebt geïmplementeerd, kunt u de status ervan weergeven op de pagina **Alle beleidsregels** in de werkruimte **Beleid**.

## Beleidsinstellingen voor Windows Firewall

### Windows Firewall inschakelen

Deze beleidsinstellingen schakelen Windows Firewall in op beheerde computers die zijn verbonden met een domein (bijvoorbeeld op het werk), een particulier (vertrouwd) netwerk (zoals een thuisnetwerk) of een niet-vertrouwd, openbaar netwerk (bijvoorbeeld in een restaurant). De standaardwaarde voor elk van deze instellingen is **Ja**. Dit is ook de veiligste waarde. 



### Alle binnenkomende verbindingen blokkeren, inclusief verbindingen in de lijst met toegestane programma's

Deze beleidsinstellingen configureren Windows Firewall voor het blokkeren van inkomend netwerkverkeer wanneer de beheerde computer is verbonden met een domein (bijvoorbeeld op het werk), een particulier (vertrouwd) netwerk (zoals een thuisnetwerk) of een niet-vertrouwd, openbaar netwerk (bijvoorbeeld in een restaurant). De standaardwaarde voor elk van deze instellingen is **Ja**. Dit is ook de veiligste waarde. 

> [!IMPORTANT]
> Als in uw omgeving computers met Windows Vista zonder servicepacks worden uitgevoerd, moet u de update uit [artikel 971800](http://go.microsoft.com/fwlink/?LinkId=188405) in de Microsoft Knowledge Base installeren of de beleidsinstelling **Alle binnenkomende verbindingen blokkeren** uitschakelen in het beleid dat is geïmplementeerd op deze computers.

### De gebruiker waarschuwen wanneer een nieuw programma door Windows Firewall wordt geblokkeerd

Deze beleidsinstellingen configureren of Windows Firewall de pc-gebruiker een melding stuurt wanneer deze inkomend netwerkverkeer blokkeert wanneer de beheerde computer is verbonden met een domein (bijvoorbeeld op het werk), een particulier (vertrouwd) netwerk (zoals een thuisnetwerk) of een niet-vertrouwd, openbaar netwerk (bijvoorbeeld in een restaurant). De standaardwaarde voor elk van deze instellingen is **Ja**..


### Vooraf gedefinieerde uitzonderingen

Nadat u bovenstaande basiswaarden hebt geconfigureerd, kunt u uitzonderingen configureren die bepaald netwerkverkeer toestaan de firewall te passeren ongeacht de waarden die hierboven zijn geconfigureerd. Standaard is geen van deze instellingen geconfigureerd.

|Naam van de instelling|Details|
|------------------|--------------------|
|**BranchCache - Inhoud ophalen**<br>(Windows 7 of hoger)|Hiermee kunnen BranchCache-clients met behulp van HTTP inhoud van elkaar ophalen in de gedistribueerde modus en uit de gehoste cache in de gehoste-cachemodus. Deze instelling maakt gebruik van HTTP.|
|**BranchCache - Client voor gehoste cache**<br>(Windows 7 of hoger)|Hiermee kunnen BranchCache-clients een gehoste cache gebruiken. Deze instelling maakt gebruik van HTTPS.|
|**BranchCache - Server voor gehoste cache**|Hiermee kunnen BranchCache-clients een gehoste cache gebruiken om te communiceren met andere clients. Deze instelling maakt gebruik van HTTPS.|
|**BranchCache - Peer-detectie**<br>(Windows 7 of hoger)|Hiermee kunnen BranchCache-clients het WS Discovery-protocol gebruiken om te controleren of er inhoud beschikbaar is op het lokale subnet.|
|**BITS Peercaching**|Hiermee kunnen clients Background Intelligent Transfer Service (BITS) gebruiken om bestanden te zoeken en te delen die zijn opgeslagen in de BITS-cache op clients in hetzelfde subnet. Deze instelling maakt gebruik van WSDAPI en RPC.|
|**Verbinding met een netwerkprojector maken**|Hiermee kunnen gebruikers verbinding maken met projectors via bekabelde of draadloze netwerken om presentaties te projecteren. Deze instelling maakt gebruik van WSDAPI.|
|**Core Networking**|Hiermee kunnen clients IPv4 en IPv6 gebruiken om verbinding te maken met netwerkbronnen.|
|**Distributed Transaction Coordinator**|Hiermee kunnen beheerde computers transacties coördineren waarmee tegen transacties beveiligde bronnen, zoals databases, berichtenwachtrijen en bestandssystemen, worden bijgewerkt.|
|**Bestands- en printerdeling**|Hiermee kunnen gebruikers lokale bestanden en printers delen met andere gebruikers in het netwerk. Deze instelling maakt gebruik van NetBIOS, LLMNR, SMB en RPC.|
|**Thuisgroep**<br>(Windows 7 of hoger)|Hiermee kunnen beheerde computers deelnemen aan een thuisgroepnetwerk.|
|**iSCSI-service**|Hiermee kunnen beheerde computers verbinding maken met iSCSI-servers en -apparaten.|
|**Service voor sleutelbeheer**|Hiermee kunnen computers worden geteld voor naleving van de licentieovereenkomst in bedrijfsomgevingen.|
|**Media Center Extenders**|Hiermee kunnen Media Center Extenders communiceren met computers waarop Windows Media Center wordt uitgevoerd. Deze instelling maakt gebruik van SSDP en qWave.|
|**Netlogon-service**|Hiermee configureert u een beveiligingskanaal tussen domeinclients en een domeincontroller voor het verifiëren van gebruikers en services. Deze instelling maakt gebruik van RPC.|
|**Netwerkdetectie**|Hiermee kunnen computers andere apparaten detecteren en door andere apparaten in het netwerk worden gedetecteerd. Deze instelling maakt gebruik van Function Discovery Host and Publication Services en SSDP-, NetBIOS-, LLMNR- en UPnP-netwerkprotocollen.|
|**Performance Logs and Alerts**|Hiermee kan de service Performance Logs and Alerts extern worden beheerd. Deze instelling maakt gebruik van RPC.|
|**Extern beheer**|Hiermee is extern beheer van de computer toegestaan.|
|**Hulp op afstand**|Hiermee kunnen gebruikers van beheerde computers hulp op afstand aanvragen bij andere gebruikers in het netwerk. Deze instelling maakt gebruik van SSDP-, PNRP-, Teredo- en UPnP-netwerkprotocollen.|
|**Extern bureaublad**|Hiermee kan de computer Extern bureaublad gebruiken voor toegang tot andere computers.|
|**Extern logboekbeheer**|Hiermee kunnen de gebeurtenislogboeken van de client op afstand worden bekeken en beheerd. Deze instelling maakt gebruik van Named Pipes en RPC.|
|**Extern beheer van geplande taken**|Hiermee is extern beheer van de service voor het plannen van taken mogelijk. Deze instelling maakt gebruik van RPC.|
|**Extern servicebeheer**|Hiermee is extern beheer van lokale services op clients toegestaan. Deze instelling maakt gebruik van Named Pipes en RPC.|
|**Extern volumebeheer**|Hiermee is extern volumebeheer van software- en hardwareschijven toegestaan. Deze instelling maakt gebruik van RPC.|
|**Routering en RAS**|Hiermee zijn binnenkomende VPN- en RAS-verbindingen met computers toegestaan.|
|**Secure Socket Tunneling Protocol**|Hiermee zijn binnenkomende VPN-verbindingen naar beheerde computers via Secure Socket Tunneling Protocol (SSTP) toegestaan. Deze instelling maakt gebruik van HTTPS.|
|**SNMP Trap**|Hiermee kunnen beheerde computers SNMP Trap-serviceverkeer ontvangen.|
|**UPnP-framework**|Hiermee wordt de UPnP-frameworkservice op computers geconfigureerd voor detectie en gebruik van UPnP-gecertificeerde apparaten.|
|**Windows Collaboration Computer Name Registration-service**|Hiermee kunnen computers andere computers vinden en hiermee communiceren via het Peer Name Resolution Protocol. Deze instelling maakt gebruik van SSDP en PNRP.|
|**Windows Media Player**|Hiermee kunnen gebruikers mediagegevensstromen via UDP ontvangen.|
|**Windows Media Player Network Sharing-service**|Hiermee kunnen gebruikers media delen via een netwerk. Deze instelling maakt gebruik van SSDP-, qWave- en UPnP-netwerkprotocollen.|
|**Windows Media Player Network Sharing-service (internet)**<br>(Windows 7 of hoger)|Hiermee kunnen gebruikers thuismedia delen via internet.|
|**Windows Meeting Space**|Hiermee kunnen gebruikers via een netwerk samenwerken om documenten, programma's of hun bureaublad te delen. Deze instelling maakt gebruik van DFSR en P2P.|
|**Windows Peer to Peer Collaboration Foundation**|Hiermee worden verschillende peer-to-peer-programma's en -technologieën geconfigureerd om deze toe te staan verbinding te maken. Deze instelling maakt gebruik van SSDP en PNRP.|
|**Windows Remote Management (compatibiliteit)**|Hiermee wordt extern beheer van beheerde computers via WS-Management toegestaan. WS-Management is een protocol op basis van webservices voor het extern beheren van besturingssystemen en apparaten.|
|**Windows Remote Management**<br>(Windows 8 of hoger)|Hiermee wordt extern beheer van beheerde computers via WS-Management toegestaan. WS-Management is een protocol op basis van webservices voor het extern beheren van besturingssystemen en apparaten.|
|**Windows Virtual PC**<br>(Windows 7 of hoger)|Hiermee kunnen virtuele computers met andere computers communiceren.|
|**Wireless Portable Devices**|Hiermee configureert u dat media vanaf een camera of media-apparaat in het netwerk kunnen worden overgedragen naar beheerde computers via MTP (Media Transfer Protocol). Deze instelling maakt gebruik van SSDP- en UPnP-netwerkprotocollen.|

### Zie tevens
[Beleid voor het beveiligen van Windows-pc's](policies-to-protect-windows-pcs-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


