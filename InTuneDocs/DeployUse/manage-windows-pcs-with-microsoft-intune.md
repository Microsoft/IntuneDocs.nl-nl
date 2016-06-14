---
# required metadata

title: Windows-pc's met Intune beheren | Microsoft Intune
description:
keywords:
author: nathbarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Windows-pc's met Microsoft Intune beheren
Naast het inschrijven van apparaten kunt u Intune ook gebruiken om Windows-pc's met ondersteunde besturingssystemen te beheren met de Intune-clientsoftware voor Windows-pc’s. De hardware- en softwarevereisten om de computerclient uit te voeren, zijn minimaal. In feite wordt elk systeem ondersteund waarop Windows 7 of hoger kan worden uitgevoerd.  De clientsoftware kan ook gemakkelijk worden geïnstalleerd op computers die lid zijn van een domein (in elk domein) en computers die niet lid zijn van een domein.

Intune beheert Windows-pc’s met beleidsregels op een manier die lijkt op hoe Windows Server Active Directory Domain Services (AD DS) dat met groepsbeleidsobjecten doet. Als u Active Directory-computers die lid zijn van een domein, wilt beheren met Intune, moet u [ervoor zorgen dat het Intune-beleid niet in strijd is met de groepsbeleidsobjecten](resolve-gpo-and-microsoft-intune-policy-conflicts.md) die in uw organisatie van kracht zijn.

> [!NOTE]
> Microsoft Intune als zelfstandige service biedt deze functies om computers te beheren. Apparaten met Windows 8.1 kunnen worden beheerd via de Intune-client of worden ingeschreven als mobiel apparaat. De onderstaande informatie is van toepassing op computers waarop de Intune-client wordt uitgevoerd.

## Vereisten voor Intune-pc-beheer

**Hardware**:
Hieronder vindt u de minimale hardwarevereisten voor het installeren van de Intune-client:

|Vereiste|Meer informatie|
|---------------|--------------------|
|Netwerk|De client vereist dat de computer een internetverbinding heeft.|
|Processor en geheugen|Raadpleeg de vereisten voor de processor en het RAM-geheugen voor het besturingssysteem van de computer.|
|Schijfruimte|200 MB vrije schijfruimte voordat de clientsoftware wordt geïnstalleerd.|

**Software**:
Hieronder vindt u de softwarevereisten voor het installeren van de client:

|Vereiste|Meer informatie|
|---------------|--------------------|
|Beheermachtigingen|Het account waarmee de clientsoftware wordt geïnstalleerd, moet lokale beheerdersmachtigingen op die computer hebben.|
|Windows Installer 3.1|De computer moet minimaal Windows Installer 3.1 hebben.<br /><br />Zo controleer u welke versie van Windows Installer op een computer is geïnstalleerd:<br /><br />Klik op de pc met de rechtermuisknop op **%windir%\System32\msiexec.exe** en klik vervolgens op **Eigenschappen**..<br /><br />U kunt de meest recente versie van Windows Installer downloaden van de pagina [Herdistribueerbare Windows Installer-pakketten](http://go.microsoft.com/fwlink/?LinkID=234258) op de Microsoft Developer Network-website.|
|Niet-compatibele clientsoftware verwijderen|Voordat u de Intune-clientsoftware installeert, moet u de Configuration Manager- of Systems Management Server-clientsoftware van de pc verwijderen.|

## De Intune-clientcomputer installeren
De eerste stap bij het beheren van Windows-pc’s met Intune is om de client te installeren. De clientsoftware kan worden geïnstalleerd wanneer een pc op een van de volgende manieren door de Intune-service wordt ingeschreven om te worden beheerd:

-   U kunt [de Microsoft Intune-clientsoftware handmatig implementeren](install-the-windows-pc-client-with-microsoft-intune.md#to-manually-deploy-the-client-software). Bij dit type implementatie downloadt een beheerder de Intune-clientsoftware en installeert deze handmatig op elke computer.

    Als u de Intune-clientsoftware wilt downloaden, opent u de Intune-beheerconsole en downloadt u het clientsoftwarepakket in de sectie Clientsoftware downloaden. Nadat de clientsoftware is geïnstalleerd, installeert Intune automatisch aanvullende software als dat nodig is om de computer te beheren.

-   U kunt dezelfde bestanden die u downloadt, gebruiken voor handmatige installatie van de Intune-client om [de client met Active Directory-groepsbeleidsobjecten te implementeren op computers die lid zijn van een domein](install-the-windows-pc-client-with-microsoft-intune.md#to-automatically-deploy-the-client-software-by-using-group-policy)..

-   [Eindgebruikers kunnen hun computers zelf inschrijven](install-the-windows-pc-client-with-microsoft-intune.md#how-users-can-self-enroll-their-computers) via de Intune-bedrijfsportal. Elke ingeschreven computer wordt vervolgens automatisch gekoppeld aan het gebruikersaccount dat is gebruikt om de Intune-clientsoftware te installeren.

-   Ten slotte kunt u de Intune-clientsoftware ook implementeren op computers als onderdeel van de [implementatie van een besturingssysteem](install-the-windows-pc-client-with-microsoft-intune.md#install-the-microsoft-intune-client-software-as-part-of-an-image)..

## Computerbeheer met de Intune-computerclient
Nadat de Intune-client is geïnstalleerd, biedt de clientsoftware verschillende mogelijkheden voor computerbeheer, waaronder: [toepassingsbeheer](deploy-apps-in-microsoft-intune.md), Endpoint Protection, hardware- en software-inventarisatie, extern beheer (via Hulp op afstand-aanvragen), software-updates en rapportage over nalevingsinstellingen.

Verschillende computerbeheertaken die door de computerclient zijn ingeschakeld, worden beheerd met Intune-beleid, zoals:

-   Configureren van de [Windows Firewall-instellingen](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) op beheerde computers.

-   Configureren van [software-update-instellingen](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) voor beheerde computers om te controleren op vereiste software-updates en deze te downloaden.

-   Beveiliging van beheerde computers tegen mogelijke bedreigingen en schadelijke software via [real-timebewaking en Endpoint Protection](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md)-beheer.

Naast de agentacties van de Intune-client die lokaal op afzonderlijke computers worden uitgevoerd, kunt u de Intune-beheerconsole ook gebruiken om andere [algemene computerbeheertaken](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) uit te voeren op Windows-pc’s waarop de client is geïnstalleerd en wel om het volgende te doen:

-   Informatie over de hardware en software op beheerde computers weergeven

-   Een computer op afstand opnieuw opstarten

-   Een computer buiten gebruik stellen om de clientsoftware te verwijderen en de computer uit Intune-beheer te verwijderen

-   Gebruikers koppelen aan specifieke beheerde computers

-   Reageren op aanvragen voor hulp op afstand

De Intune-clientagent wordt doorgaans in stille modus op de achtergrond uitgevoerd zonder dat de gebruiker iets hoeft te doen of problemen hoeft op te lossen. Mocht u echter hulp nodig hebben bij het verhelpen van problemen met het beheren van computers, dan zijn er verschillende [bronnen beschikbaar om u te helpen bij het oplossen van problemen](/intune/troubleshoot/troubleshoot-client-setup-in-microsoft-intune)..


<!--HONumber=May16_HO1-->


