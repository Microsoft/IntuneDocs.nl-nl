---
title: Pc&quot;s beheren met clientsoftware | Microsoft Docs
description: Beheer Windows-pc&quot;s door de Intune-clientsoftware te installeren.
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 45c32cf08e4d6fd570af287ed64411edc9d9b394
ms.openlocfilehash: 21e83b68bb68384a8916db8d7f779cddde18a8a6


---

# <a name="manage-windows-pcs-with-intune-pc-client-software"></a>Windows-pc's beheren met de Intune-pc-clientsoftware
In plaats van [Windows-pc's als mobiele apparaten te registreren](set-up-windows-device-management-with-microsoft-intune.md), kunt u Windows-pc's ook registreren en beheren door de Intune-clientsoftware te installeren.

Intune beheert Windows-pc's met beleidsregels op een manier die lijkt op hoe Windows Server Active Directory Domain Services (AD DS) dat met groepsbeleidsobjecten doet. Als u Active Directory-computers die lid zijn van een domein wilt beheren met Intune, [zorgt u ervoor dat het Intune-beleid niet in strijd is met de groepsbeleidsobjecten](resolve-gpo-and-microsoft-intune-policy-conflicts.md) die in uw organisatie van kracht zijn. Meer informatie over [groepsbeleidsobjecten](https://technet.microsoft.com/library/hh147307.aspx).

Hoewel de Intune-softwareclient [beheermogelijkheden ondersteunt die helpen bij de beveiliging van pc's](policies-to-protect-windows-pcs-in-microsoft-intune.md) door het beheer van software-updates, Windows Firewall en Endpoint Protection, kan er geen ander Intune-beleid worden toegepast op pc's die worden beheerd door de Intune-softwareclient, waaronder **Windows**-beleidsinstellingen die specifiek bedoeld zijn voor Mobile Device Management. 

Als u de Intune-softwareclient gebruikt voor het beheer van Windows-pc's, kunt u alleen de beleidsregels gebruiken die worden weergegeven onder de sectie **Computerbeheer**.

  ![Een sjabloon selecteren voor een nieuw Windows pc-beleid](../media/select-template-for-pc-policy.png)

Zie voor gedetailleerde beschrijvingen van de beleidsregels die u kunt instellen:

- [Gebruik beleid voor het beveiligen van Windows-pc's waarop de Intune-clientsoftware wordt uitgevoerd](https://docs.microsoft.com/intune/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune)
- [Windows-pc's up-to-date houden met software-updates in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)
- [Windows-pc's beschermen met Windows Firewall-beleid in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune)
- [Help Windows-pc's beveiligen met Endpoint Protection Help voor Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)

Bovendien kunt u tijdens de implementatie van apps alleen de Windows Installer (.exe, .msi) gebruiken.

  ![Selecteer het platform en de locatie voor pc-clientsoftwarebestanden](../media/select-platform-of-software-files-for-pc-agent.png)

> [!NOTE]
> U kunt apparaten onder Windows 8.1 of hoger beheren als pc's met behulp van de Intune-client, of als mobiele apparaten met behulp van de functionaliteit voor beheer van mobiele apparaten (MDM). U kunt beide methoden niet tegelijk gebruiken, dus u moet uw beslissing zorgvuldig overwegen voordat u besluit pc's te beheren met behulp van de Intune-softwareclient. Dit onderwerp is alleen bedoeld om apparaten als pc's te beheren door het uitvoeren van de Intune-softwareclient.

## <a name="requirements-for-intune-pc-client-management"></a>Vereisten voor Intune-pc-clientbeheer

**Hardware**: hieronder vindt u de minimale hardwarevereisten voor het installeren van de Intune-client:

|Vereiste|Meer informatie|
|---------------|--------------------|
|Netwerk|De client vereist dat de computer een internetverbinding heeft.|
|Processor en geheugen|Raadpleeg de vereisten voor de processor en het RAM-geheugen voor het besturingssysteem van de computer.|
|Schijfruimte|200 MB vrije schijfruimte voordat de clientsoftware wordt geïnstalleerd.|

**Software**: hieronder staan de softwarevereisten beschreven voor het installeren van de client:

|Vereiste|Meer informatie|
|---------------|--------------------|
|Besturingssysteem | Windows-apparaat waarop Windows Vista of hoger wordt uitgevoerd. </br></br>**Home Edition-versies worden niet ondersteund.**|
|Beheermachtigingen|Het account waarmee de clientsoftware wordt geïnstalleerd, moet lokale beheerdersmachtigingen op het apparaat hebben.|
|Windows Installer 3.1|De computer moet minimaal Windows Installer 3.1 hebben.<br /><br />Zo controleer u welke versie van Windows Installer op een computer is geïnstalleerd:<br /><br />  Klik op de pc met de rechtermuisknop op **%windir%\System32\msiexec.exe** en klik vervolgens op **Eigenschappen**.<br /><br />U kunt de meest recente versie van Windows Installer downloaden van de pagina [Herdistribueerbare Windows Installer-pakketten](http://go.microsoft.com/fwlink/?LinkID=234258) op de Microsoft Developer Network-website.|
|Niet-compatibele clientsoftware verwijderen|Voordat u de Intune-clientsoftware installeert, moet u de Configuration Manager-, Operations Manager-, Operations Management Suite- en Service Manager-clientsoftware van de pc verwijderen.|

## <a name="computer-management-capabilities-with-the-intune-software-client"></a>Mogelijkheden voor computerbeheer met de Intune-softwareclient

Nadat de Intune-clientsoftware is geïnstalleerd, zijn dit de beheermogelijkheden: 

- [Toepassingsbeheer](deploy-apps-in-microsoft-intune.md)

- [Realtime-controle en eindpuntbeveiliging](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md)

 > [!NOTE]
 > Endpoint Protection is hetzelfde als Windows Defender. Endpoint Protection is van toepassing op Windows 7 en Windows 8. Voor Windows 10 en hoger is de productnaam gewijzigd in Windows Defender.

- [Beheer van Windows Firewall-instellingen](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md), hard- en software-inventarisatie, extern beheer (via Hulp op afstand-aanvragen)

- [Instellingen voor software-updates](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)

- Instellingen voor naleving rapporteren

In de Intune-beheerconsole worden bepaalde secties, zoals "Updates", "Beveiliging" en "Licenties" alleen weergegeven als u apparaten hebt ingeschreven met behulp van de Intune-softwareclient.

  ![Beheerconsole-items die alleen voor pc-client worden weergegeven](../media/admin-console-settings-only-for-pc-agent.png)

U kunt de Intune-beheerconsole ook gebruiken om andere [algemene computerbeheertaken](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) uit te voeren op Windows-pc's waarop de client is geïnstalleerd:

-   Informatie over de hardware en software op beheerde computers weergeven

-   Een computer op afstand opnieuw opstarten

-   Een computer buiten gebruik stellen om de softwareclient te verwijderen en de computer uit Intune-beheer te verwijderen

-   Gebruikers koppelen aan specifieke beheerde computers

-   Reageren op aanvragen voor hulp op afstand

## <a name="management-limitations-of-the-intune-software-client"></a>Beperkingen voor beheer van de Intune-softwareclient

Sommige beheeropties, die kunnen worden gebruikt voor het beheer van pc's als mobiele apparaten, kunnen niet worden gebruikt voor pc's die worden beheerd met de Intune-softwareclient:

-   Volledig wissen (selectief wissen is beschikbaar)

-   Voorwaardelijke toegang

## <a name="help-with-troubleshooting"></a>Hulp bij het oplossen van problemen

De Intune-clientagent wordt doorgaans in stille modus op de achtergrond uitgevoerd zonder dat de gebruiker iets hoeft te doen of problemen hoeft op te lossen. Als u problemen met pc-beheer moet oplossen, kunt u de logboeken controleren. De Intune-softwareclient en de bijbehorende logboeken zijn geïnstalleerd in de map %Program Files%\Microsoft\OnlineManagement.

U kunt ook [Troubleshoot client setup in Microsoft Intune (Problemen met clientinstallatie in Microsoft Intune oplossen)](/intune/troubleshoot/troubleshoot-client-setup-in-microsoft-intune) raadplegen om te controleren welke problemen zich kunnen voordoen en welke (tijdelijke) oplossingen hiervoor zijn.



<!--HONumber=Feb17_HO2-->


