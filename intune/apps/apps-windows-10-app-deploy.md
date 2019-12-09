---
title: Implementatie van Windows 10-apps met behulp van Microsoft Intune
titleSuffix: ''
description: Hier vindt u meer informatie over implementatiescenario's voor apps in Windows 10 die beschikbaar zijn met Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
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
ms.openlocfilehash: c9d792bd07ae8d7d712748874d64314dd258c5e8
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563944"
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

## <a name="windows-10-lob-apps"></a>Windows 10 LOB-apps

U kunt Windows 10 LOB-apps ondertekenen en uploaden naar de Intune-beheerconsole. Deze kunnen zowel moderne apps, zoals UWP-apps (Universal Windows Platform) en Windows-app-pakketten (AppX), als Win 32-apps bevatten, zoals eenvoudige Microsoft Installer-pakketbestanden (MSI). De beheerder moet updates voor LOB-apps handmatig uploaden en implementeren. Deze updates worden automatisch geïnstalleerd op apparaten van gebruikers die de app hebben geïnstalleerd. Er is geen tussenkomst van de gebruiker vereist, en de gebruiker heeft geen controle over de updates. 

## <a name="microsoft-store-for-business-apps"></a>Microsoft Store voor Bedrijven-apps

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
  - Moderne Line-Of-Business-apps en Microsoft Store voor Bedrijven-apps (zowel online als offline) kunnen in de gebruikerscontext worden geïmplementeerd. De apps bieden ondersteuning voor zowel de intentie Vereist als de intentie Beschikbaar.
  - Win32-apps die zijn gemaakt voor Gebruikersmodus of Dual-modus, kunnen in de gebruikerscontext worden geïmplementeerd en bieden ondersteuning voor zowel de intentie Vereist als de intentie Beschikbaar. 
- **Apparaatcontext**: Wanneer een app wordt geïmplementeerd in de apparaatcontext, wordt de beheerde app rechtstreeks op het apparaat geïnstalleerd door Intune.
  - Alleen moderne Line-Of-Business-apps en offline gelicentieerde Microsoft Store voor zakelijke apps kunnen in de apparaatcontext worden geïmplementeerd. Deze apps bieden alleen ondersteuning voor de intentie Vereist.
  - Win32-apps die zijn gemaakt voor Machinemodus of Dual-modus, kunnen in de apparaatcontext worden geïmplementeerd en bieden alleen ondersteuning voor de intentie Vereist.

> [!NOTE]
> Voor Win32-apps die zijn gemaakt voor Dual-modus, moet de beheerder aangeven of de app werkt in Gebruikersmodus of in Machinemodus voor alle toewijzingen die aan dat exemplaar zijn gekoppeld. De implementatiecontext kan niet per toewijzing worden gewijzigd.  

Wanneer een app wordt geïmplementeerd in de apparaatcontext, slaagt de installatie alleen wanneer deze bestemd is voor een apparaat dat de apparaatcontext ondersteunt. Bovendien ondersteunt implementatie in de apparaatcontext de volgende voorwaarden:
- Als een app wordt geïmplementeerd in de apparaatcontext en is gericht op een gebruiker, mislukt de installatie. De volgende status en fout worden weergegeven in de beheerconsole:
  - Status: Mislukt.
  - Fout: Een gebruiker kan niet het doel zijn van de installatie van apparaatcontext.
- Wanneer een app wordt geïmplementeerd in de apparaatcontext, maar is gericht op een apparaat dat geen ondersteuning biedt voor apparaatcontext, mislukt de installatie. De volgende status en fout worden weergegeven in de beheerconsole:
  - Status: Mislukt.
  - Fout: Dit platform biedt geen ondersteuning voor het installeren van apparaatcontext. 

> [!Note]
> Nadat u een app-toewijzing hebt opgeslagen met een specifieke implementatie, kunt u de context voor deze toewijzing niet wijzigen, met uitzondering van moderne apps. Voor moderne apps kunt u de context wijzigen van gebruikerscontext in apparaatcontext. 

Als er een conflict is in beleid voor één gebruiker of apparaat, gelden de volgende prioriteiten:
- Het beleid voor apparaatcontext heeft een hogere prioriteit dan het beleid voor gebruikerscontext. 
- Het beleid Installeren heeft een hogere prioriteit dan het beleid Verwijderen.

Zie [App-toewijzingen opnemen en uitsluiten in Microsoft Intune](apps-inc-exl-assignments.md) voor meer informatie. Zie [Apps toevoegen aan Microsoft Intune](apps-add.md) voor meer informatie over typen apps in Intune.

## <a name="next-steps"></a>Volgende stappen

- [Apps toewijzen aan groepen met Microsoft Intune](apps-deploy.md)
- [Apps controleren](apps-monitor.md)
