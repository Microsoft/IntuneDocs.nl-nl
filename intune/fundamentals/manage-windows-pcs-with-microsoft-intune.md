---
title: Pc's beheren met clientsoftware in Microsoft Intune - Azure | Microsoft Docs
description: Beheer Windows-pc's door de Intune-clientsoftware te installeren.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/15/2019
ms.topic: archived
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: fb67cf2cb17b78c4034c3b73e229e160723d975e
ms.sourcegitcommit: 60f0ff6d2efbae0f2ce14b9a9f3f9267309e209b
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 11/01/2019
ms.locfileid: "73414394"
---
# <a name="manage-windows-pcs-as-computers-via-intune-software-client"></a>Windows-pc's beheren als computers via de Intune-softwareclient

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

> [!WARNING]
> Microsoft heeft aangekondigd dat [ondersteuning voor Windows 7 op 14 januari 2020 wordt beëindigd](https://support.microsoft.com/help/4057281/windows-7-support-will-end-on-january-14-2020). Op deze datum zal Intune ook de ondersteuning beëindigen voor apparaten waarop Windows 7 wordt uitgevoerd. Microsoft raadt u ten zeerste aan over te stappen op Windows 10 om eventuele service- of ondersteuningsproblemen te voorkomen.
> 
> Voor meer informatie, zie [Geplande wijziging voor Intune: aanstaande beëindiging van ondersteuning voor Windows 7](../fundamentals/whats-new.md#intune-plan-for-change-nearing-end-of-support-for-windows-7).

> [!NOTE]
> U kunt Microsoft Intune gebruiken voor het beheren van Windows-pc's [als mobiele apparaten met Mobile Device Management (MDM)](../enrollment/windows-enroll.md) of als computers met de Intune-softwareclient, zoals hieronder beschreven. Microsoft adviseert klanten echter om indien mogelijk [de MDM-beheeroplossing te gebruiken](../enrollment/windows-enroll.md). Raadpleeg [Het beheer van Windows-pc's als computers of mobiele apparaten vergelijken](pc-management-comparison.md) voor meer informatie 

Intune biedt voor organisaties een uitgebreide oplossing voor het beheren van mobiele apparaten. Met Intune kunt u Windows-pc's beheren als mobiele apparaten met behulp van de moderne mogelijkheden voor apparaatbeheer die zijn ingebouwd in Windows 10. Als u wilt voldoen aan de beheerbehoeften van uw organisatie, kan Intune ook Windows-pc's beheren als computers met de Intune-softwareclient. Bij deze beheermethode wordt gebruikgemaakt van traditionele mogelijkheden voor computerbeheer uit het oude Windows-besturingssysteem.

De Intune-softwareclient is het meest geschikt voor Windows-pc's met een ouder besturingssystemen zoals Windows 7, die niet kunnen worden beheerd als mobiele apparaten. De Intune-softwareclient gebruikt beheermogelijkheden zoals Groepsbeleid voor het beheren van pc's vanuit de cloud.

Intune ondersteunt het beheer van Windows-pc's als computers met behulp van de softwareclient voor maximaal 7.000 pc's. Voor grotere implementaties beheert u pc’s met Windows 10 als mobiele apparaten. Elke release van Intune en elke update van Windows 10 bevat beheerfuncties op basis van de beheerarchitectuur voor mobiele apparaten. Het is raadzaam dat uw organisatie overstapt naar Windows 10 dat wordt beheerd als mobiele apparaten.

> [!NOTE]
> U kunt apparaten met Windows 8.1 of hoger beheren als pc's met behulp van de Intune-clientsoftware of als mobiele apparaten. U kunt beide methoden op hetzelfde apparaat gebruiken. Maak een zorgvuldige overweging voordat u besluit pc’s te beheren met de Intune-clientsoftware. Dit onderwerp is alleen bedoeld om apparaten als pc's te beheren door het uitvoeren van de Intune-clientsoftware.

## <a name="requirements-for-intune-pc-client-management"></a>Vereisten voor Intune-pc-clientbeheer

**Hardware**:  
Hieronder vindt u de minimale hardwarevereisten voor het installeren van de Intune-clientsoftware:

|Vereiste|Meer informatie|
|---------------|--------------------|
|Netwerk|De client vereist dat de computer een internetverbinding heeft.|
|Processor en geheugen|Raadpleeg de vereisten voor de processor en het RAM-geheugen voor het besturingssysteem van de computer.|
|Schijfruimte|200 MB vrije schijfruimte voordat de clientsoftware wordt geïnstalleerd.|

**Software**:  
Hieronder staan de softwarevereisten beschreven voor het installeren van de clientsoftware:

|Vereiste|Meer informatie|
|---------------|--------------------|
|Besturingssysteem | Windows-apparaat waarop Windows 7 SP1 en Windows 8.1 of later wordt uitgevoerd. </br></br>**Home Edition-versies worden niet ondersteund.**|
|Beheermachtigingen|Het account waarmee de clientsoftware wordt geïnstalleerd, moet lokale beheerdersmachtigingen op het apparaat hebben.|
|Windows Installer 3.1|De computer moet minimaal Windows Installer 3.1 hebben.<br /><br />Zo controleer u welke versie van Windows Installer op een computer is geïnstalleerd:<br /><br />  Klik op de pc met de rechtermuisknop op **%windir%\System32\msiexec.exe** en klik vervolgens op **Eigenschappen**.<br /><br />U kunt de meest recente versie van Windows Installer downloaden van de pagina [Herdistribueerbare Windows Installer-pakketten](https://go.microsoft.com/fwlink/?LinkID=234258) op de Microsoft Developer Network-website.|
|Niet-compatibele clientsoftware verwijderen|Voordat u de Intune-clientsoftware installeert, moet u de Configuration Manager-, Operations Manager- en Service Manager-clientsoftware van de pc verwijderen.|

## <a name="deploying-the-intune-software-client"></a>De Intune-softwareclient installeren
Als Intune-beheerder kunt u op verschillende manieren de Intune-softwareclient beschikbaar stellen aan gebruikers. Zie [De Intune-softwareclient installeren op Windows-pc's](../install-the-windows-pc-client-with-microsoft-intune.md) voor meer informatie.

## <a name="computer-management-capabilities-with-the-intune-client-software"></a>Mogelijkheden voor computerbeheer met de Intune-clientsoftware
In de meeste gevallen registreert u uw apparaten bij Microsoft Intune, waarmee u over een groter aantal mogelijkheden beschikt. U kunt echter ook pc's beheren met behulp van de Intune-softwareclient, die u de volgende functies biedt:

- **[Beheer van software-updates](../keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)** : u kunt computers up-to-date houden en bepalen wanneer updates moeten worden toegepast.

- **[Windows Firewall-beleid](../help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md)** : hiermee kunt u ervoor zorgen dat geen enkele computer die door uw bedrijf wordt gebruikt, een niet-actieve of niet goed geconfigureerde Windows Firewall heeft.

- **[Anti-malwarebeveiliging](../help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md)** : in Intune is Endpoint Protection opgenomen, waarmee uw computers worden beschermd tegen malware.

- **[Hulp op afstand](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)** : met Intune kunnen gebruikers contact opnemen met IT-ondersteuningsmedewerkers, die vervolgens hulp kunnen bieden met de functie Extern bureaublad, die in Intune is opgenomen (vereist TeamViewer-software).

- **[Softwarelicentiebeheer](../manage-license-agreements-for-windows-pc-software-in-microsoft-intune.md)** : hiermee kunt u bijhouden hoeveel softwarelicenties er nog beschikbaar zijn en hoeveel licenties er al worden gebruikt.
- **[App-implementatie](add-apps-for-windows-pcs-in-microsoft-intune.md)** : implementeer software op pc's die u beheert. Bepaalde app-beheerfuncties zijn niet beschikbaar wanneer u pc's met de softwareclient beheert.

<!-- - **Compliance settings reporting** -->

## <a name="policies-and-app-deployments-for-the-intune-software-client"></a>Beleid en app-implementaties voor de Intune-clientsoftware

Hoewel de Intune-clientsoftware [beheermogelijkheden ondersteunt die helpen bij de beveiliging van pc's](policies-to-protect-windows-pcs-in-microsoft-intune.md) door het beheer van software-updates, Windows Firewall en Endpoint Protection, kan er geen ander Intune-beleid worden toegepast op pc's die worden beheerd door de Intune-clientsoftware, waaronder **Windows**-beleidsinstellingen die specifiek bedoeld zijn voor Mobile Device Management.

Als u de Intune-clientsoftware gebruikt voor het beheer van Windows-pc's, kunt u alleen de beleidsregels gebruiken die worden weergegeven onder de sectie **Computerbeheer**.

Intune beheert Windows-pc’s met beleidsregels, vergelijkbaar met de manier waarop Windows Server Active Directory Domain Services (AD DS) dat met groepsbeleidsobjecten doet. Als u Active Directory-computers die lid zijn van een domein wilt beheren met Intune, [zorgt u ervoor dat het Intune-beleid niet in strijd is met de groepsbeleidsobjecten](resolve-gpo-and-microsoft-intune-policy-conflicts.md) die in uw organisatie worden gebruikt. Zie [Groepsbeleid voor beginners](https://technet.microsoft.com/library/hh147307.aspx) voor meer informatie.

  ![Een sjabloon selecteren voor een nieuw Windows pc-beleid](./media/manage-windows-pcs-with-microsoft-intune/select-template-for-pc-policy.png)

Tijdens de implementatie van apps kunt u alleen de Windows Installer (.exe, .msi) gebruiken.

  ![Selecteer het platform en de locatie voor pc-clientsoftwarebestanden](./media/manage-windows-pcs-with-microsoft-intune/select-platform-of-software-files-for-pc-agent.png)

## <a name="common-tasks-for-windows-pcs"></a>Algemene taken voor het Windows-pc 's

U kunt de Intune-beheerconsole gebruiken om andere algemene computerbeheertaken uit te voeren op Windows-pc's waarop de client is geïnstalleerd:
- [Beleid gebruiken om het beheer van pc's te vereenvoudig](use-policies-to-simplify-windows-pc-management.md): beschrijft de beleidsregels van Intune voor **Computerbeheer** en biedt een overzicht van de instellingen voor het Microsoft Intune Center.

- [Hardware- en software-inventaris weergeven voor Windows-pc's](view-hardware-and-software-inventory-for-windows-pcs-in-microsoft-intune.md): hierin wordt uitgelegd hoe u een rapport maakt met informatie over de hardwaremogelijkheden van pc's en software die erop is geïnstalleerd. Daarnaast wordt uitgelegd hoe u de pc-inventaris vernieuwt om ervoor te zorgen dat deze actueel is.
- [Een Windows-pc buiten gebruik stellen](retire-a-windows-pc-with-microsoft-intune.md): een overzicht van de stappen voor het buiten gebruik stellen van een Windows-pc en een beschrijving van wat er gebeurt wanneer u een pc buiten gebruik stelt.
- [Koppeling tussen gebruiker en apparaat voor Windows-pc's beheren](../manage-user-device-linking-for-windows-pcs-with-microsoft-intune.md): hierin wordt uitgelegd wanneer en hoe u een gebruiker aan een pc koppelt voordat u software naar de gebruiker implementeert.
- [Hulp op afstand voor Windows-pc's aanvragen en bieden](request-and-provide-remote-assistance-for-windows-pcs-in-microsoft-intune.md): hierin wordt uitgelegd hoe pc-gebruikers met Intune hulp op afstand van u kunnen krijgen en worden de vereisten een TeamViewer-instellingen beschreven.

Zie [Algemene computerbeheertaken](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) voor meer informatie over de bovenstaande taken.

## <a name="management-limitations-of-the-intune-client-software"></a>Beperkingen voor beheer van de Intune-clientsoftware

Sommige beheeropties, die kunnen worden gebruikt voor het beheer van pc's als mobiele apparaten, kunnen niet worden gebruikt voor pc's die worden beheerd met de Intune-clientsoftware:

- Volledig wissen (selectief wissen is beschikbaar)
- Voorwaardelijke toegang

In de Intune-beheerconsole worden bepaalde secties, zoals **Updates**, **Beveiliging** en **Licenties** alleen weergegeven als u apparaten hebt geregistreerd met behulp van de Intune-clientsoftware.

  ![Beheerconsole-items die alleen voor pc-client worden weergegeven](./media/manage-windows-pcs-with-microsoft-intune/admin-console-settings-only-for-pc-agent.png)

## <a name="help-with-troubleshooting"></a>Hulp bij het oplossen van problemen

De Intune-clientsoftware wordt doorgaans in stille modus op de achtergrond uitgevoerd zonder dat de gebruiker iets hoeft te doen of problemen hoeft op te lossen. Als u problemen met pc-beheer moet oplossen, kunt u de logboeken controleren. De Intune-clientsoftware en de bijbehorende logboeken zijn geïnstalleerd in de map %Program Files%\Microsoft\OnlineManagement.

U kunt ook [apparaatinschrijving](../enrollment/device-enrollment.md) raadplegen voor meer informatie over het inschrijven van apparaten met Microsoft Intune.
