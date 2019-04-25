---
title: Instellingen voor gedeelde apparaten en apparaten met meerdere gebruikers in Microsoft Intune - Azure | Microsoft Docs
description: Voeg in Microsoft Intune Windows 10- en Windows Holographic for Business-apparaten toe die worden gedeeld of door meerdere gebruikers worden gebruikt, en gebruik deze. Bekijk een lijst met alle instellingen en wat deze betekenen op de apparaten, inclusief Microsoft HoloLens. Beheer gastaccounts, beheer accounts, verwijder inactieve accounts, geef toestemming voor of blokkeer opslaan in lokale opslag, stel energie- en slaapopties in, kies wanneer updates worden geïnstalleerd en gebruik apparaten in onderwijsomgevingen in een apparaatconfiguratieprofiel.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/09/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8c2cf06508cc21682a580c09e8207343b09e39eb
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/23/2019
ms.locfileid: "61506675"
---
# <a name="control-access-accounts-and-power-features-on-shared-pc-or-multi-user-devices-using-intune"></a>Toegang, accounts en energiefuncties op gedeelde pc's en apparaten met meerdere gebruikers beheren met Intune

Apparaten met meerdere gebruikers worden ook wel gedeelde apparaten genoemd. Deze maken meestal deel uit van MDM-oplossingen (Mobile Device Management). Met Microsoft Intune kunt u gedeelde apparaten met de volgende platformen aanpassen:

- Windows 10 Professional en hoger
- Windows 10 Enterprise en hoger
- Windows Holographic for Business, zoals de HoloLens

Scholen beschikken bijvoorbeeld over apparaten die door veel leerlingen of studenten worden gebruikt. Met deze instelling kan de Intune-beheerder op school de functie voor gedeelde pc's inschakelen zodat er slechts één gebruiker tegelijk een apparaat kan gebruiken. Studenten kunnen op apparaten niet wisselen tussen verschillende accounts waarbij is aangemeld. Wanneer de student zich heeft afgemeld, worden indien gewenst alle gebruikersspecifieke instellingen verwijderd.

Eindgebruikers kunnen zich met een gastaccount aanmelden op deze gedeelde apparaten. Wanneer een gebruiker zich heeft aangemeld, worden de referenties in de cache opgeslagen. Tijdens het gebruik van het apparaat hebben eindgebruikers alleen toegang tot de functies die u inschakelt. U bepaalt bijvoorbeeld wanneer de slaapstand op apparaten wordt ingeschakeld, of gebruikers lokale bestanden kunnen zien en bestanden kunnen opslaan, energiebeheerinstellingen kunnen in- of uitschakelen en meer. U bepaalt ook of het gastaccount wordt verwijderd nadat de gebruiker zich heeft afgemeld en of inactieve accounts worden verwijderd als er een bepaalde drempelwaarde wordt bereikt.

In dit artikel ziet u hoe u een configuratieprofiel maakt. Er staan ook koppelingen in naar de beschikbare instellingen (inclusief beschrijving).

Wanneer het profiel in Intune is gemaakt, implementeert u het of wijst u het toe aan apparaatgroepen in uw organisatie. U kunt dit profiel ook toewijzen aan apparaatgroepen met verschillende typen apparaten en besturingssysteemversies.

## <a name="create-the-profile"></a>Het profiel maken

1. Selecteer in [Azure Portal](https://portal.azure.com) de optie **Alle services** > filter op **Intune** > selecteer **Intune**.
2. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Voer de volgende eigenschappen in:

   - **Naam**: Voer een beschrijvende naam in voor het nieuwe profiel.
   - **Beschrijving**: Voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
   - **Platform**: Kies **Windows 10 en hoger**.
   - **Profieltype**: Selecteer **Gedeelde apparaat voor meerdere gebruikers**.

4. Configureer de instellingen voor [Windows 10 en hoger](shared-user-device-settings-windows.md) of [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md).

5. Selecteer **OK** > **Maken** om uw wijzigingen op te slaan.

Het profiel wordt gemaakt en in de lijst weergegeven, maar er gebeurt nog niets. [Wijs het profiel toe](device-profile-assign.md) aan apparaatgroepen in uw organisatie.

## <a name="next-steps"></a>Volgende stappen

- Zie alle instellingen voor [Windows 10 en hoger](shared-user-device-settings-windows.md) of [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md).
- [Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).
