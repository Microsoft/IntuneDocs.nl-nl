---
title: Instellingen voor gedeelde apparaten in Windows 10 - Microsoft Intune - Azure | Microsoft Docs
description: Voeg in Microsoft Intune Windows 10 toe en gebruik dit voor het configureren voor apparaten die worden gedeeld of door meerdere gebruikers worden gebruikt. Bekijk een lijst met alle instellingen en wat deze betekenen op de apparaten, inclusief Microsoft Surface. Beheer gastaccounts, beheer accounts, verwijder inactieve accounts, geef toestemming voor of blokkeer opslaan in lokale opslag, stel energie- en slaapopties in, kies wanneer updates worden geïnstalleerd en gebruik apparaten in onderwijsomgevingen in een apparaatconfiguratieprofiel.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/01/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 67393f83ecd76250e01deef3eee20aa1206b3f99
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 05/23/2019
ms.locfileid: "66040553"
---
# <a name="windows-10-and-later-settings-to-manage-shared-devices-using-intune"></a>Instellingen voor Windows 10 (en hoger) om gedeelde apparaten te beheren met Intune

Apparaten met Windows 10 en hoger, zoals de Microsoft Surface, kunnen door veel gebruikers worden gebruikt. Apparaten met meerdere gebruikers worden ook wel gedeelde apparaten genoemd. Deze maken deel uit van MDM-oplossingen (Mobile Device Management).

Met Microsoft Intune kunnen eindgebruikers zich met een gastaccount aanmelden op deze gedeelde apparaten. Tijdens het gebruik van deze apparaten hebben ze alleen toegang tot de functies die u inschakelt. Als Intune-beheerder configureert u de toegang, kiest u wanneer accounts worden verwijderd, bepaalt u de energiebeheerinstellingen en nog veel meer voor uw gedeelde Windows 10-apparaten.

In dit artikel wordt beschreven welke instellingen u kunt gebruiken in een apparaatconfiguratieprofiel voor Windows 10 (of hoger). Wanneer het profiel in Intune is gemaakt, implementeert u het of wijst u het toe aan apparaatgroepen in uw organisatie. U kunt dit profiel ook toewijzen aan apparaatgroepen met verschillende typen apparaten en besturingssysteemversies.

Zie [Control access, accounts, and power features on shared PC or multi-user devices](shared-user-device-settings.md) (Toegang, accounts en energiefuncties beheren voor gedeelde pc's en apparaten met meerdere gebruikers) voor meer informatie over deze Intune-functie. Zie [SharedPC CSP](https://docs.microsoft.com/windows/client-management/mdm/sharedpc-csp) (CSP voor gedeelde pc's) voor meer informatie over de Windows-CSP.

## <a name="before-your-begin"></a>Voordat u begint

[Maak het profiel](shared-user-device-settings.md).

## <a name="shared-multi-user-device-settings"></a>Instellingen voor gedeelde apparaat voor meerdere gebruikers

- **Modus Gedeelde pc**: Kies **Inschakelen** om de modus voor gedeelde pc in te schakelen. In deze modus kan slechts één gebruiker tegelijk zich aanmelden bij het apparaat. Andere gebruikers kunnen zich pas aanmelden wanneer de eerste gebruiker zich heeft afgemeld. Door **niet te configureren** (standaard), wordt deze instelling niet beheerd via Intune en wordt er geen beleid gepusht voor het configureren van deze instelling op apparaten.
- **Gastaccount**: kies ervoor om een gastoptie te maken op het aanmeldingsscherm. Voor een gastaccount zijn er geen gebruikersreferenties en verificatie nodig. Met deze instelling wordt er bij elk gebruik een nieuw lokaal account gemaakt. Uw opties zijn:
  - **Gast**: hiermee wordt lokaal op het apparaat een gastaccount gemaakt.
  - **Domein**: hiermee wordt een gastaccount in Azure Active Directory (AD) gemaakt.
  - **Gast en domein**: hiermee wordt een gastaccount lokaal op het apparaat en in Azure Active Directory (AD) gemaakt.
- **Accountbeheer**: kies **Inschakelen** om lokale accounts die zijn gemaakt door gasten en accounts in AD en Azure AD automatisch te verwijderen. Wanneer een gebruiker zich afmeldt op het apparaat of wanneer er systeemonderhoud wordt uitgevoerd, worden deze accounts verwijderd. Als deze optie is ingeschakeld, stelt u ook de volgende zaken in:
  - **Accountverwijdering**: Kies wanneer accounts worden verwijderd: **Bij drempelwaarde opslagruimte**, **Bij drempelwaarde opslagruimte en inactiviteit** of **Direct na afmelding**. Voer ook in:
    - **Drempelwaarde verwijderen starten(%)** : Voer een percentage van de schijfruimte in (0-100). Als de totale schijf-/opslagruimte lager is dan de ingevoerde waarde, worden de accounts in de cache verwijderd. Er worden doorlopend accounts verwijderd om schijfruimte terug te winnen. De accounts die het langst inactief zijn, worden als eerste verwijderd.
    - **Drempelwaarde verwijderen stoppen(%)** : Voer een percentage van de schijfruimte in (0-100). Als de totale schijf-/opslagruimte hetzelfde is als de ingevoerde waarde, wordt gestopt met verwijderen.

  Schakel deze optie **uit** om de lokale, AD- en Azure AD-accounts die zijn gemaakt door gasten te behouden.

- **Lokale opslag**: ste deze optie in op **ingeschakeld** om te voorkomen dat gebruikers bestanden opslaan op de harde schijf van het apparaat en bestanden van de harde schijf bekijken. Schakel deze optie **uit** om gebruikers via Verkenner bestanden te laten bekijken en opslaan. Door **niet te configureren** (standaard), wordt deze instelling niet beheerd via Intune en wordt er geen beleid gepusht voor het configureren van deze instelling op apparaten.
- **Energiebeleid**: als dit wordt **ingeschakeld**, kunnen gebruikers de sluimerstand niet uitschakelen, kunnen ze de slaapstandacties niet overschrijven (bijvoorbeeld door de laptop dicht te klappen) en kunnen ze de energie-instellingen niet wijzigen. Als dit wordt **uitgeschakeld**, kunnen gebruikers het apparaat in de sluimerstand zetten, kunnen ze een laptop in de slaapstand zetten door deze dicht te klappen en kunnen ze de energie-instellingen wijzigen. Door **niet te configureren** (standaard), wordt deze instelling niet beheerd via Intune en wordt er geen beleid gepusht voor het configureren van deze instelling op apparaten.
- **Time-out slaapstand (in seconden)** : Voer het aantal seconden inactiviteit in (0-100) voordat de slaapstand wordt ingeschakeld op het apparaat. Als u geen tijd instelt, wordt de slaapstand na 60 minuten ingeschakeld.
- **Aanmelden wanneer de pc uit de slaapstand wordt gehaald**: stel deze optie in op **ingeschakeld** om gebruikers zich met een wachtwoord te laten aanmelden wanneer een apparaat weer uit de slaapstand wordt gehaald. Schakel deze optie **uit** als gebruikers hun gebruikersnaam en wachtwoord niet hoeven in te voeren. Door **niet te configureren** (standaard), wordt deze instelling niet beheerd via Intune en wordt er geen beleid gepusht voor het configureren van deze instelling op apparaten.
- **Begintijd van onderhoud (in minuten vanaf middernacht)** : Voer in minuten (0-1440) in wanneer taken voor automatisch onderhoud, zoals het uitvoeren van Windows Update, moeten worden uitgevoerd. De reguliere begintijd is middernacht, oftewel nul (`0`) minuten. U kunt de begintijd wijzigen door een bepaald aantal minuten vanaf middernacht in te voeren als begintijd. Als u bijvoorbeeld wilt dat onderhoud om 2:00 uur wordt uitgevoerd, voert u `120` in. Als u wilt dat onderhoud om 20:00 uur wordt uitgevoerd, voert u `1200` in.
- **Onderwijsbeleid**: stel deze optie in op **ingeschakeld** om de aanbevolen instellingen voor apparaten op scholen te gebruiken. Met deze instellingen worden meer beperkingen opgelegd. Schakel deze optie **uit** om het standaard- en aanbevolen onderwijsbeleid niet te gebruiken. Door **niet te configureren** (standaard), wordt deze instelling niet beheerd via Intune en wordt er geen beleid gepusht voor het configureren van deze instelling op apparaten.

  Zie [Windows 10 configuration recommendations for education customers](https://docs.microsoft.com/education/windows/configure-windows-for-education) (Windows 10-configuratieaanbevelingen voor klanten uit het onderwijs) voor meer informatie over het onderwijsbeleid.

> [!TIP]
> [Een gedeelde of gast-pc instellen](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc) (hiermee wordt een andere Docs-website geopend) is een geweldige resource in deze Windows 10-functie, met concepten en groepsbeleid die kunnen worden ingesteld in de gedeelde modus.

## <a name="next-steps"></a>Volgende stappen

- [Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).
- Bekijk de instellingen voor [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md).
