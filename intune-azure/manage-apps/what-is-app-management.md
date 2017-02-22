---
title: Wat is app-beheer | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: gebruik dit onderwerp voor meer informatie over de basisbeginselen van app-beheer met Microsoft Intune'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 424fae862592c1ab5b4221fb5ad40a52c39f6760
ms.openlocfilehash: 33bc87d16834cb2950cc7c66ad4887dddb12e811


---

# <a name="what-is-app-management"></a>Wat is app-beheer?


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Als IT-beheerder is het waarschijnlijk uw taak ervoor te zorgen dat eindgebruikers toegang hebben tot de apps die ze nodig hebben voor hun werk. Dit kan om de volgende redenen een uitdaging zijn:
- Er is een breed scala aan apparaatplatformen en app-typen.
- U moet mogelijk apps op bedrijfsapparaten evenals op de eigen apparaten van gebruikers beheren.
- U moet dit allemaal doen terwijl u tegelijk moet garanderen dat uw netwerk en de gegevens beveiligd blijven. 

Verder wilt u misschien apps toewijzen en beheren op apparaten die niet met Intune zijn geregistreerd.

Intune biedt een scala aan mogelijkheden om u te helpen de benodigde apps op de gekozen apparaten te krijgen.

## <a name="app-management-capabilities-by-platform"></a>App-beheermogelijkheden per platform

||||||
|-|-|-|-|-|
|&nbsp; |Android|iOS|Windows Phone 8,1|Windows 10|
|Apps toevoegen en aan apparaten en gebruikers toewijzen|Yes|Ja|Ja|Ja|
|Toewijzen van apps aan apparaten die niet zijn geregistreerd met Intune|Ja|Ja|Nee|Nee|
|Beleidsregels voor app-configuratie gebruiken om het opstartgedrag van apps te beheren|Nee|Ja|Nee|Nee|
|Bedrijfsgegevens in apps beveiligen met app-beveiligingsbeleid|Yes|Ja|Nee|Nee<sup>1</sup>|
|Alleen zakelijke gegevens verwijderen uit een geïnstalleerde app (App selectief wissen)|Yes|Ja|Ja|Yes|
|App-toewijzingen controleren|Ja|Ja|Ja|Yes|
|Apps die in een app-winkel zijn gekocht via een volume-aankoopprogramma, toewijzen en bijhouden|Nee|Nee|Nee|Yes|
|Verplichte installatie van apps op apparaten (Vereist)<sup>2</sup>|Ja|Ja|Ja|Yes|
|Optionele installatie op apparaten via de bedrijfsportal (Beschikbare installatie)|Yes|Ja|Ja|Yes|
|Installatiesnelkoppeling naar een app op het web (Web Clip)|Yes|Ja|Ja|Yes|
|Interne apps (Line-Of-Business-apps)|Yes|Ja|Nee|Nee|
|Apps uit een store|Yes|Ja|Ja|Yes|
|Apps bijwerken|Ja|Ja|Ja|Yes|

<sup>1</sup> U kunt gebruikmaken van [Windows Information Protection](/intune-azure/configure-devices/how-to-configure-windows-information-protection) om apps op apparaten met Windows 10 te beveiligen.

<sup>2</sup>Alleen van toepassing op apparaten die worden beheerd door Intune.


## <a name="how-to-get-started"></a>Aan de slag

U vindt de meeste dingen die op apps betrekking hebben, in de workload **Mobiele apps** die als volgt toegankelijk is:

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apps beheren** op de blade **Intune**.

    ![De workload Mobiele apps](./media/apps-workload.png)

### <a name="manage"></a>Manage
- **Apps**: dit is de locatie waar u de meeste apps toevoegt, toewijst en bewaakt. 
    - [Apps toevoegen](add-apps.md)
    - [Apps toewijzen](deploy-apps.md)
    - [Apps bewaken](monitor-apps.md)
- **Apps met licenties**: apps die in de app-stores zijn gekocht via een volume-aankoopprogramma, weergeven, implementeren en bewaken.
    - [Windows Store voor Bedrijven-apps die via het volume-aankoopprogramma zijn gekocht](wsfb-apps.md)
- **App-configuratiebeleid**: u kunt met app-configuratiebeleid instellingen opgeven die mogelijk vereist zijn wanneer een gebruiker een app uitvoert. Zie voor meer informatie:
    - [App-configuratiebeleid](app-configuration-policies.md)
- **App-beveiligingsbeleid**: hiermee kunt u instellingen aan een app koppelen om de bedrijfsgegevens die in de app worden gebruikt, te helpen beveiligen. U kunt bijvoorbeeld de mogelijkheden van een app om met andere apps te communiceren beperken of vereisen dat de gebruiker een pincode voor toegang tot een bedrijfsapp invoert.
    - [App-beveiligingsbeleid](app-protection-policies.md)
- **App selectief wissen**: alleen zakelijke gegevens verwijderen van het gebruikersapparaat dat u selecteert.
    - [App selectief wissen](app-selective-wipe.md)

### <a name="monitor"></a>Monitor
- **Gevonden apps**: hier worden alle apps weergegeven die zijn toegewezen door Intune en op een apparaat zijn geïnstalleerd.
- **Installatiestatus van de app**: hier wordt de status weergegeven van een app-toewijzing die u hebt gemaakt.
- **Gebruikersstatus van de app-beveiliging**: hier wordt de status weergegeven van een app-beveiligingsbeleid voor een gebruiker die u selecteert.

Zie [Apps bewaken](monitor-apps.md) voor meer informatie

### <a name="setup"></a>Setup
<!--- **iOS VPP Tokens**
    - [iOS volume-purchased apps](ios-vpp-apps.md) --->
- **Windows Store voor Bedrijven**: integratie met Windows Store voor Bedrijven instellen. Nadat u dit hebt gedaan, kunt u gekochte toepassingen synchroniseren met Intune, deze toewijzen en uw licentiegebruik bijhouden. 
    - [Windows Store voor Bedrijven-apps die via het volume-aankoopprogramma zijn gekocht](wsfb-apps.md)
- **Aangepaste stijl van de bedrijfsportal**: pas de bedrijfsportal aan de huisstijl van uw bedrijf aan. 
    - [Bedrijfsportal configureren](company-portal-app.md)



<!--HONumber=Feb17_HO1-->


