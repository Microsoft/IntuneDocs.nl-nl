---
title: Implementatie van Windows 10-apps met behulp van Microsoft Intune
titleSuffix: ''
description: Hier vindt u meer informatie over implementatiescenario's voor apps in Windows 10 die beschikbaar zijn met Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/30/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: abebfb5e-054b-435a-903d-d1c31767bcf2
ms.reviewer: priyar
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: fa4510b95e1e84d9f94158833dac555daa33c690
ms.sourcegitcommit: c46b0c2d4507be6a2786a4ea06009b2d5aafef85
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/01/2020
ms.locfileid: "76912553"
---
# <a name="windows-10-app-deployment-by-using-microsoft-intune"></a>Implementatie van Windows 10-apps met behulp van Microsoft Intune 

Microsoft Intune ondersteunt verschillende typen apps en implementatiescenario's op Windows 10-apparaten. Nadat u een app hebt toegevoegd aan Intune, kunt u de app toewijzen aan gebruikers en apparaten. Dit artikel biedt meer details over de ondersteunde Windows 10-scenario’s, en behandelt ook de belangrijkste details die u in het achterhoofd moet houden wanneer u apps implementeert in Windows. 

LOB-apps (Line-Of-Business) en Microsoft Store voor Bedrijven-apps zijn de typen apps die op Windows 10-apparaten worden ondersteund. De bestandsextensies voor Windows-apps omvatten .msi, .appx en .appxbundle.  

> [!Note]
> Voor het implementeren van moderne apps hebt u minstens het volgende nodig:
> - Voor Windows 10 1803: [23 mei 2018: KB4100403 (build van besturingssysteem: 17134.81)](https://support.microsoft.com/help/4100403/windows-10-update-kb4100403).
> - Voor Windows 10 1709: [21 juni 2018: KB4284822 (build van besturingssysteem: 16299.522)](https://support.microsoft.com/help/4284822).
>
> Alleen Windows 10 versie 1803 en hoger bieden ondersteuning voor het installeren van apps wanneer er geen primaire gebruiker is gekoppeld.
>
> Implementatie van LOB-apps wordt niet ondersteund op apparaten met Windows 10 Home-edities.

## <a name="supported-windows-10-app-types"></a>Ondersteunde typen Windows 10-apps

Specifieke app-typen worden ondersteund op basis van de versie van Windows 10 die door uw gebruikers wordt uitgevoerd. De volgende tabel bevat het app-type en de Windows 10-ondersteuning.

| App-type | Home | Pro | Business | Enterprise | Education | S-Mode | Hololense | SurfaceHub | WCOS | Mobiele telefoon |
|----------------|------|-----|----------|------------|-----------|--------|-----------|------------|------|--------|
|  .MSI | Nee | Ja | Ja | Ja | Ja | Nee | Nee | Nee | Nee | Nee |
| .IntuneWin | Nee | Ja | Ja | Ja | Ja | 19H2+ | Nee | Nee | Nee | Nee |
| Office C2R | Nee | Ja | Ja | Ja | Ja | Nee | Nee | Nee | Nee | Nee |
| LOB: APPX/MSIX | Ja | Ja | Ja | Ja | Ja | Ja | Ja | Ja | Ja | Ja |
| MSFB Offline | Ja | Ja | Ja | Ja | Ja | Ja | Ja | Ja | Ja | Ja |
| MSFB Online | Ja | Ja | Ja | Ja | Ja | Ja | RS4+ | Ja | Ja | Ja |
| Web Apps | Ja | Ja | Ja | Ja | Ja | Ja | Ja<sup>1 | Ja<sup>1 | Ja | Ja |
| Store-koppeling | Ja | Ja | Ja | Ja | Ja | Ja | Ja | Ja | Ja | Ja |

<sup>1</sup> Alleen starten vanuit de bedrijfsportal.

> [!NOTE]
> Alle Windows-app-typen moeten worden ingeschreven.

## <a name="windows-10-lob-apps"></a>Windows 10 LOB-apps

U kunt Windows 10 LOB-apps ondertekenen en uploaden naar de Intune-beheerconsole. Deze kunnen zowel moderne apps, zoals UWP-apps (Universal Windows Platform) en Windows-app-pakketten (AppX), als Win 32-apps bevatten, zoals eenvoudige Microsoft Installer-pakketbestanden (MSI). De beheerder moet updates voor LOB-apps handmatig uploaden en implementeren. Deze updates worden automatisch geïnstalleerd op apparaten van gebruikers die de app hebben geïnstalleerd. Er is geen tussenkomst van de gebruiker vereist, en de gebruiker heeft geen controle over de updates. 

## <a name="microsoft-store-for-business-apps"></a>Apps in de Microsoft Store voor Bedrijven

Microsoft Store voor Bedrijven-apps zijn moderne apps die zijn aangeschaft in de Microsoft Store voor Bedrijven-beheerportal. Ze worden vervolgens gesynchroniseerd naar Microsoft Intune voor beheer. De apps kunnen zowel online gelicentieerd als offline gelicentieerd zijn. In Microsoft Store worden updates rechtstreeks beheert, zonder dat extra actie van de beheerder is vereist. U kunt bovendien met een aangepaste Uniform Resource Identifier (URI) voorkomen dat bepaalde apps worden bijgewerkt. Zie [Enterprise app management - Prevent app from automatic updates](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management#prevent-app-from-automatic-updates) (Bedrijfsappbeheer - Voorkomen dat apps automatisch worden bijgewerkt) voor meer informatie. De gebruiker kan ook updates voor alle Microsoft Store voor Bedrijven-apps uitschakelen. 

### <a name="categorize-microsoft-store-for-business-apps"></a>Microsoft Store voor Bedrijven-apps categoriseren 
Microsoft Store voor Bedrijven-apps categoriseren: 

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apps** > **Alle apps**. 
3. Selecteer een Microsoft Store voor Bedrijven-app. Selecteer vervolgens **Eigenschappen** > **App-gegevens** > **Categorie**. 
4. Selecteer een categorie.

## <a name="install-apps-on-windows-10-devices"></a>Apps installeren op Windows 10-apparaten
Afhankelijk van het type app kunt u de app op twee manieren installeren op een Windows 10-apparaat:

- **Gebruikerscontext**: Wanneer een app wordt geïmplementeerd in de gebruikerscontext, wordt de beheerde app geïnstalleerd op het apparaat van de gebruiker wanneer de gebruiker zich aanmeldt op het apparaat. De installatie van de app wordt pas uitgevoerd als de gebruiker zich op het apparaat aanmeldt. 
  - Moderne LOB-apps en Microsoft Store voor Bedrijven-apps (zowel online als offline) kunnen in de gebruikerscontext worden geïmplementeerd. De apps bieden ondersteuning voor zowel de intentie Vereist als de intentie Beschikbaar.
  - Win32-apps die zijn gemaakt voor Gebruikersmodus of Dual-modus, kunnen in de gebruikerscontext worden geïmplementeerd en bieden ondersteuning voor zowel de intentie Vereist als de intentie Beschikbaar. 
- **Apparaatcontext**: Wanneer een app wordt geïmplementeerd in de apparaatcontext, wordt de beheerde app rechtstreeks op het apparaat geïnstalleerd door Intune.
  - Alleen moderne LOB-apps en offline gelicentieerde Microsoft Store voor Bedrijven-apps kunnen in de apparaatcontext worden geïmplementeerd. Deze apps bieden alleen ondersteuning voor de intentie Vereist.
  - Win32-apps die zijn gemaakt voor Machinemodus of Dual-modus, kunnen in de apparaatcontext worden geïmplementeerd en bieden alleen ondersteuning voor de intentie Vereist.

> [!NOTE]
> Voor Win32-apps die zijn gemaakt voor Dual-modus, moet de beheerder aangeven of de app werkt in Gebruikersmodus of in Machinemodus voor alle toewijzingen die aan dat exemplaar zijn gekoppeld. De implementatiecontext kan niet per toewijzing worden gewijzigd.  

Apps kunnen alleen worden geïnstalleerd in de apparaatcontext wanneer ze worden ondersteund door het apparaat en het Intune-app-type. U kunt de volgende typen apps installeren in de apparaatcontext en deze apps toewijzen aan een apparaatgroep:

- Win32-apps
- Offline gelicentieerde Microsoft Store voor Bedrijven-apps
- LOB-apps (MSI, APPX en MSIX)
- Office 365 ProPlus

Windows LOB-apps (met name APPX en MSIX) en Microsoft Store voor Bedrijven-apps (Offline apps) die u hebt geselecteerd voor installatie in de apparaatcontext, moeten worden toegewezen aan een apparaatgroep. De installatie mislukt als een van deze apps is geïmplementeerd in de gebruikerscontext. De volgende status en fout worden weergegeven in de beheerconsole:
  - Status: Mislukt.
  - Fout: Een gebruiker kan niet het doel zijn van de installatie van apparaatcontext.

> [!IMPORTANT]
> Bij gebruik in combinatie met een inrichtingsscenario met Autopilot-ondersteuning is er geen vereiste voor LOB-apps en Microsoft Store voor Bedrijven-apps die zijn geïmplementeerd in de apparaatcontext voor een apparaatgroep. Zie [Implementatie van Windows Autopilot-ondersteuning](https://docs.microsoft.com/windows/deployment/windows-autopilot/white-glove) voor meer informatie.

> [!Note]
> Nadat u een app-toewijzing hebt opgeslagen met een specifieke implementatie, kunt u de context voor deze toewijzing niet wijzigen, met uitzondering van moderne apps. Voor moderne apps kunt u de context wijzigen van gebruikerscontext in apparaatcontext. 

Als er een conflict is in beleid voor één gebruiker of apparaat, gelden de volgende prioriteiten:
- Het beleid voor apparaatcontext heeft een hogere prioriteit dan het beleid voor gebruikerscontext. 
- Het beleid Installeren heeft een hogere prioriteit dan het beleid Verwijderen.

Zie [App-toewijzingen opnemen en uitsluiten in Microsoft Intune](apps-inc-exl-assignments.md) voor meer informatie. Zie [Apps toevoegen aan Microsoft Intune](apps-add.md) voor meer informatie over typen apps in Intune.

## <a name="next-steps"></a>Volgende stappen

- [Apps toewijzen aan groepen met Microsoft Intune](apps-deploy.md)
- [Apps controleren](apps-monitor.md)
