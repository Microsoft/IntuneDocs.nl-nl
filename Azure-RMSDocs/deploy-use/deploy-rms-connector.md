---
title: De Azure Rights Management-connector implementeren | Azure RMS
description: In deze informatie leest u meer over de Azure Rights Management-connector (RMS) en hoe u deze kunt gebruiken om gegevensbeveiliging te bieden met bestaande on-premises implementaties die gebruikmaken van Microsoft Exchange Server, Microsoft SharePoint Server of bestandsservers waarop Windows Server wordt uitgevoerd en die de mogelijkheid voor infrastructuur voor bestandsclassificatie (FCI) van de bestandsserverbronbeheer gebruiken.
author: cabailey
manager: mbaldwin
ms.date: 08/24/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 90e7e33f-9ecc-497b-89c5-09205ffc5066
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 024a29d7c7db2e4c0578a95c93e22f8e7a5b173e
ms.openlocfilehash: 003dcc6a000d303fc42204d61145cf067dc16d32


---

# De Azure Rights Management-connector implementeren

>*Van toepassing op: Azure Rights Management, Windows Server 2012, Windows Server 2012 R2*

In deze informatie leest u meer over de Azure Rights Management-connector (RMS) en hoe u deze kunt gebruiken om gegevensbeveiliging te bieden met bestaande on-premises implementaties die gebruikmaken van Microsoft Exchange Server, Microsoft SharePoint Server of bestandsservers waarop Windows Server wordt uitgevoerd en die de mogelijkheid voor infrastructuur voor bestandsclassificatie (FCI) van de bestandsserverbronbeheer gebruiken.

> [!TIP]
> Zie de sectie [Bestanden op bestandsservers met Windows Server en Infrastructuur voor bestandsclassificatie automatisch beveiligen](../understand-explore/what-admins-users-see.md#automatically-protecting-files-on-file-servers-running-windows-server-and-file-classification-infrastructure) in het artikel [Azure RMS in actie](../understand-explore/what-admins-users-see.md) voor een overzicht met voorbeeldscenario’s met schermafbeeldingen.

## Overzicht van de Microsoft Rights Management-connector
Met de Microsoft Rights Management-connector (RMS) kunt u op bestaande on-premises servers snel de IRM-functionaliteit (Information Rights Management) inschakelen voor gebruik van de Microsoft Rights Management-cloudservice (Azure RMS). Met deze functionaliteit kan IT en kunnen gebruikers eenvoudig documenten en afbeeldingen beveiligen, zowel binnen uw organisatie als daarbuiten, zonder dat hiervoor extra infrastructuur moet worden geïnstalleerd of vertrouwensrelaties moeten worden vastgelegd met andere organisaties. In een hybride scenario kunt u deze connector zelfs gebruiken als sommige gebruikers verbinding maken met online services. Bijvoorbeeld wanneer voor het postvak van sommige gebruikers Exchange Online en voor het postvak van andere gebruikers Exchange Server wordt gebruikt. Nadat u de RMS-connector hebt geïnstalleerd, kunnen alle gebruikers e-mailberichten en bijlagen beveiligen en verbruiken met Azure RMS en werkt de gegevensbeveiliging naadloos tussen de twee implementatieconfiguraties.

De RMS-connector is een service met een kleine footprint die u on-premises installeert op servers waarop Windows Server 2012 R2, Windows Server 2012 of Windows Server 2008 R2 wordt uitgevoerd. U kunt de connector niet alleen uitvoeren op fysieke computers, maar ook op virtuele machines, inclusief Azure IaaS-VM's. Nadat het installeren en configureren van de connector, fungeert deze als een communicatie-interface (een relay) tussen de on-premises servers en de cloudservice.

Als u uw eigen sleuteltenant beheert voor Azure RMS (het bring your own key- of BYOK-scenario), hebben de RMS-connector en de on-premises servers die deze gebruiken geen toegang tot de Hardware Security Module (HSM) die de tenantsleutel bevat. Dit komt doordat alle cryptografische bewerkingen die gebruikmaken van de tenantsleutel worden uitgevoerd in Azure RMS, niet on-premises.

![Architectuuroverzicht van de RMS-connector](../media/RMS_connector.png)

De RMS-connector ondersteunt de volgende on-premises servers: Exchange Server, SharePoint Server en bestandsservers waarop Windows Server wordt uitgevoerd en die infrastructuur voor bestandsclassificatie gebruiken om beleidsregels te classificeren en toe te passen op de Office-documenten in een map. Als u alle bestandstypen wilt beveiligen met bestandsclassificatie, gebruikt u niet de RMS-connector, maar de [Cmdlets van RMS-beveiliging](https://msdn.microsoft.com/library/azure/mt433195.aspx).

> [!NOTE]
> Zie [On-premises servers die Azure RMS ondersteunen](..\get-started\requirements-servers.md) voor ondersteunde versies van deze on-premises servers.

Gebruik de volgende informatie voor het te plannen, installeren en configureren van de RMS-connector. Na de installatie moet u nog enkele configuratiestappen uitvoeren zodat uw servers van de connector gebruik kunnen maken.

-   [Vereiste voor de RMS-connector:](deploy-rms-connector.md#prerequisites-for-the-rms-connector)

-   **Stap 1:** [de RMS-connector installeren](install-configure-rms-connector.md#installing-the-rms-connector)

-   **Stap 2:**  [referenties invoeren](install-configure-rms-connector.md#entering-credentials)

-   **Stap 3:**  [servers autoriseren voor het gebruik van de RMS-connector](install-configure-rms-connector.md#authorizing-servers-to-use-the-rms-connector)

-   **Stap 4:**  [taakverdeling en hoge beschikbaarheid configureren](install-configure-rms-connector.md#configuring-load-balancing-and-high-availability)

-   Optioneel: [de RMS-connector configureren voor gebruik van HTTPS](install-configure-rms-connector.md#configuring-the-rms-connector-to-use-https)

-   Optioneel: [de RMS-connector configureren voor een webproxyserver](install-configure-rms-connector.md#configuring-the-rms-connector-for-a-web-proxy-server)

-   Optioneel: [het beheerprogramma voor RMS-connector installeren op beheercomputers](install-configure-rms-connector.md#installing-the-rms-connector-administration-tool-on-administrative-computers)

-   **Stap 5:**  [servers configureren voor het gebruik van de RMS-connector](configure-servers-rms-connector.md)

    -   [Een Exchange-server configureren voor het gebruik van de connector](configure-servers-rms-connector.md#configuring-an-exchange-server-to-use-the-connector)

    -   [Een SharePoint-server configureren voor het gebruik van de connector](configure-servers-rms-connector.md#configuring-a-sharepoint-server-to-use-the-connector)

    -   [Een bestandsserver configureren voor infrastructuur voor bestandsclassificatie voor het gebruik van de connector](configure-servers-rms-connector.md#configuring-a-file-server-for-file-classification-infrastructure-to-use-the-connector)


## Vereiste voor de RMS-connector:
Zorg ervoor dat aan de volgende vereisten wordt voldaan voordat u de RMS-connector installeert.

|Vereiste|Meer informatie|
|---------------|--------------------|
|De Rights Management-service (RMS) wordt geactiveerd|[Azure Rights Management activeren](activate-service.md)|
|Directorysynchronisatie tussen uw on-premises Active Directory-forests en Azure Active Directory|Na activering van RMS moet Azure Active Directory worden geconfigureerd om te werken met de gebruikers en groepen in uw Active Directory-database.<br /><br />**Belangrijk**: u moet deze adreslijstsynchronisatiestap uitvoeren voordat de RMS-connector werkt, zelfs voor een testnetwerk. Hoewel u Office 365 en Azure Active Directory kunt gebruiken met accounts die u handmatig in Azure Active Directory maakt, is voor deze connector vereist dat de accounts in Azure Active Directory worden gesynchroniseerd met Active Directory Domain Services; handmatige wachtwoordsynchronisatie is niet voldoende.<br /><br />Zie de volgende bronnen voor meer informatie:<br /><br />[Uw on-premises identiteiten integreren met Azure Active Directory](/active-directory/active-directory-aadconnect)<br /><br />[Vergelijking van hulpprogramma's voor hybride identiteitsdirectory-integratie](/active-directory/active-directory-hybrid-identity-design-considerations-tools-comparison)|
|Optioneel, maar aanbevolen:<br /><br />Federatie inschakelen tussen uw on-premises Active Directory en Azure Active Directory|U kunt identiteitsfederatie inschakelen tussen uw on-premises Active Directory en Azure Active Directory. Deze configuratie maakt een naadloze gebruikerservaring mogelijk met eenmalige aanmelding bij de RMS-service. Zonder eenmalige aanmelding wordt gebruikers om hun referenties gevraagd voordat ze door rechten beveiligde inhoud kunnen gebruiken.<br /><br />Zie [Controlelijst: Eenmalige aanmelding implementeren en beheren met AD FS](http://technet.microsoft.com/library/jj205462.aspx) in de Windows Server-bibliotheek voor instructies over het configureren van federatie met Active Directory Federation Services (AD FS) tussen Active Directory Domain Services en Azure Active Directory.|
|Minimaal twee computers die lid zijn waarop u de RMS-connector installeert:<br /><br />- Een fysieke of virtuele 64 bitscomputer met een van de volgende besturingssystemen: Windows Server 2012 R2, Windows Server 2012 of Windows Server 2008 R2.<br /><br />- Ten minste 1 GB aan RAM-geheugen.<br /><br />- Minimaal 64 GB aan schijfruimte.<br /><br />- Ten minste één netwerkinterface.<br /><br />- Toegang tot internet via een firewall (of een webproxy) waarvoor geen verificatie vereist is.<br /><br />- Moet zich in een forest of een domein bevinden dat andere forests in de organisatie vertrouwt die een installatie met een Exchange- of SharePoint-server bevatten die u wilt gebruiken met de RMS-connector.|Voor fouttolerantie en hoge beschikbaarheid moet u de RMS-connector installeren op ten minste twee computers.<br /><br />**Tip**: als u gebruikmaakt van Outlook Web Access of mobiele apparaten die Exchange ActiveSync IRM gebruiken, en het essentieel is dat toegang tot e-mailberichten en bijlagen beveiligd blijft door Azure RMS, wordt aangeraden een netwerktaakverdelingsgroep of connectorservers te installeren om hoge beschikbaarheid te garanderen.<br /><br />U hebt geen specifieke servers nodig om de connector uit te voeren, maar u moet deze installeren op een andere computer dan de servers die de connector gebruiken.<br /><br />**Belangrijk**: installeer de connector niet op een computer met Exchange Server, SharePoint Server of een bestandsserver die is geconfigureerd voor infrastructuur voor bestandsclassificatie als u de functionaliteit van deze services met Azure RMS wilt gebruiken. Installeer deze connector ook niet op een domeincontroller.|

## Volgende stappen

Ga naar [De Azure Rights Management-connector installeren en configureren](install-configure-rms-connector.md).


<!--HONumber=Aug16_HO4-->


