---
title: Implementatie van Windows 10-apps met Microsoft Intune
titleSuffix: ''
description: Hier vindt u meer informatie over implementatiescenario's voor apps in Windows 10 die beschikbaar zijn met Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/08/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: abebfb5e-054b-435a-903d-d1c31767bcf2
ms.reviewer: priyar
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8168cdaec4d6616b12fa4da225c84fa2d239994d
ms.sourcegitcommit: 1b7ee2164ac9490df4efa83c5479344622c181b5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/08/2019
ms.locfileid: "67648660"
---
# <a name="windows-10-app-deployment-using-microsoft-intune"></a>Implementatie van Windows 10-apps met Microsoft Intune 

Microsoft Intune ondersteunt momenteel verschillende typen apps en implementatiescenario's op Windows 10-apparaten. Nadat u een app hebt toegevoegd aan Intune, kunt u de app toewijzen aan gebruikers en apparaten. De volgende informatie bevat meer details over de ondersteunde Windows 10-scenario's. Daarnaast vindt u hier belangrijke informatie die u in acht moet nemen wanneer u apps naar Windows implementeert. 

LOB-apps (Line-Of-Business) en Microsoft Store voor Bedrijven-apps zijn de typen apps die op Windows 10-apparaten worden ondersteund. De bestandsextensies voor Windows-apps omvatten **.msi**, **.appx** en **.appxbundle**.  

> [!Note]
> Dit zijn de minimaal vereiste Windows 10-updates om moderne apps te implementeren:
> - Voor Windows 10 1803: [23 mei 2018: KB4100403 (build van besturingssysteem: 17134.81)](https://support.microsoft.com/help/4100403/windows-10-update-kb4100403).
> - Voor Windows 10 1709: [21 juni 2018: KB4284822 (build van besturingssysteem: 16299.522)](https://support.microsoft.com/help/4284822).

## <a name="windows-10-line-of-business-apps"></a>Windows 10 Line-Of-Business-apps

Windows 10 LOB-apps worden ondertekend en geüpload naar de Intune-beheerconsole en kunnen zowel moderne apps, zoals UWP-apps (Universal Windows Platform) en Windows-app-pakketten (AppX), als Win 32-apps bevatten, zoals eenvoudige Microsoft Installer-pakketbestanden (MSI). Updates van LOB-apps moeten handmatig worden geüpload en elke keer door de beheerder worden geïmplementeerd. Updates die zijn geïmplementeerd, worden automatisch geïnstalleerd op apparaten van eindgebruikers waarop de app is geïnstalleerd, zonder tussenkomst van de gebruiker. De gebruiker heeft geen controle over de updates. 

## <a name="microsoft-store-for-business-apps"></a>Microsoft Store voor Bedrijven-apps

Microsoft Store voor Bedrijven-apps zijn moderne apps die zijn aangeschaft in de Microsoft Store voor Bedrijven-beheerportal en vervolgens worden gesynchroniseerd met Microsoft Intune voor beheer. De apps kunnen zowel **online gelicentieerd** als **offline gelicentieerd** zijn. Updates van Microsoft Store voor Bedrijven-apps worden rechtstreeks door de Microsoft Store beheerd. Hiervoor is geen extra actie van de beheerder vereist. De beheerder kan bovendien met aangepaste Uniform Resource Identifier (URI) voorkomen dat bepaalde apps worden bijgewerkt. Zie [Enterprise app management - Prevent app from automatic updates](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management#prevent-app-from-automatic-updates) (Bedrijfsappbeheer - Voorkomen dat apps automatisch worden bijgewerkt) voor meer informatie. De gebruiker kan ook op het apparaat updates voor alle Microsoft Store voor Bedrijven-apps uitschakelen. 

## <a name="installing-apps-on-windows-10-devices"></a>Apps installeren op Windows 10-apparaten
Afhankelijk van het type app kan de app op twee manieren worden geïnstalleerd op een Windows 10-apparaat:

- **Gebruikerscontext**: Wanneer een app wordt geïmplementeerd in de gebruikerscontext, wordt de beheerde app geïnstalleerd op het apparaat van de gebruiker wanneer de gebruiker zich aanmeldt op het apparaat. De installatie van de app wordt pas uitgevoerd als de gebruiker zich op het apparaat aanmeldt. 
    - Moderne Line-Of-Business-apps en Microsoft Store voor Bedrijven-apps (zowel online als offline) kunnen in de gebruikerscontext worden geïmplementeerd en bieden ondersteuning voor zowel de intentie Vereist als Beschikbaar.
    - Win32-apps die zijn gemaakt voor **Gebruikersmodus** of **Dual-modus**, kunnen in de gebruikerscontext worden geïmplementeerd en bieden ondersteuning voor zowel de intentie **Vereist** als de intentie **Beschikbaar**. 
- **Apparaatcontext**: Wanneer een app wordt geïmplementeerd in de apparaatcontext, wordt de beheerde app rechtstreeks op het apparaat geïnstalleerd door Intune.
    - Alleen moderne Line-Of-Business-apps en offline gelicentieerde Microsoft Store voor zakelijke apps kunnen in de apparaatcontext worden geïmplementeerd en ondersteunen alleen de intentie Vereist.
    - Win32-apps die zijn gemaakt voor **Machinemodus** of **Dual-modus**, kunnen in de gebruikerscontext worden geïmplementeerd en bieden alleen ondersteuning voor de intentie **Vereist**.

> [!NOTE]
> Voor Win32-apps die zijn gemaakt voor **Dual-modus**, moet u (de beheerder) aangeven of de app werkt in **Gebruikersmodus** of in **Machinemodus** voor alle toewijzingen die aan dat exemplaar zijn gekoppeld. De implementatiecontext kan niet per toewijzing worden gewijzigd.  

Wanneer een app wordt geïmplementeerd in de apparaatcontext, slaagt de installatie alleen wanneer deze bestemd is voor een apparaat dat de apparaatcontext ondersteunt. Bovendien ondersteunt implementatie in de apparaatcontext de volgende voorwaarden:
- Als een app is geïmplementeerd in de apparaatcontext en bestemd is voor een gebruiker, mislukt de installatie met de volgende status en wordt de volgende fout weergegeven in de beheerconsole:
    - Status: Mislukt.
    - Fout: Een gebruiker kan niet het doel zijn van de installatie van apparaatcontext.
- Als een app is geïmplementeerd in de apparaatcontext en bestemd is voor een apparaat dat de apparaatcontext niet ondersteunt, mislukt de installatie met de volgende status en wordt de volgende fout weergegeven in de beheerconsole:
    - Status: Mislukt.
    - Fout: Dit platform biedt geen ondersteuning voor het installeren van apparaatcontext. 

> [!Note]
> Wanneer een app-toewijzing is opgeslagen met een specifieke implementatie, kan de context niet worden gewijzigd voor deze toewijzing, met uitzondering van moderne apps. Bij moderne apps kan de context namelijk worden gewijzigd van gebruikerscontext naar apparaatcontext. 

Wanneer er een conflict in het beleid voor één gebruiker/apparaat is, worden de volgende beleidsprioriteiten gebruikt om het uiteindelijke beleid te bepalen:
- Het beleid voor apparaatcontext heeft een hogere prioriteit dan het beleid voor gebruikerscontext. 
- Het beleid Installeren heeft een hogere prioriteit dan het beleid Verwijderen.

Zie [Apps toewijzen aan groepen met Microsoft Intune](apps-deploy.md) en [App-toewijzingen opnemen en uitsluiten in Microsoft Intune](apps-inc-exl-assignments.md) voor meer informatie over het toewijzen van apps met Microsoft Intune. Zie [Apps toevoegen aan Microsoft Intune](apps-add.md) voor meer informatie over typen apps in Intune.

## <a name="next-steps"></a>Volgende stappen

- Zie [Apps aan groepen toewijzen met Microsoft Intune](apps-deploy.md) voor meer informatie over het toewijzen van apps aan groepen.
- Zie [Apps controleren](apps-monitor.md) voor meer informatie over het controleren van app-toewijzingen.
