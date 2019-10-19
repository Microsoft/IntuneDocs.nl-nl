---
title: instellingen voor macOS-kernel-uitbrei ding in Microsoft Intune-Azure | Microsoft Docs
titleSuffix: ''
description: Het toevoegen, configureren of maken van instellingen op macOS-apparaten voor het gebruik van kernel-extensies. U kunt ook toestaan dat gebruikers goedgekeurde extensies overschrijven, alle uitbrei dingen van een team-ID toestaan of specifieke extensies of apps toestaan in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/10/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8632f5b8df0f483de3bb4d06a6823639ba52c604
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506707"
---
# <a name="macos-device-settings-to-configure-and-use-kernel-extensions-in-intune"></a>instellingen voor macOS-apparaten voor het configureren en gebruiken van kernel-uitbrei dingen in intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

In dit artikel vindt u een overzicht en beschrijving van de verschillende instellingen voor kernelextensies die u kunt beheren op macOS-apparaten. Als onderdeel van uw Mobile Device Management-oplossing (MDM) kunt u deze instellingen gebruiken om kernel-extensies toe te voegen aan en te beheren op uw apparaten.

Zie [macOS kernel Extensions toevoegen](../kernel-extensions-overview-macos.md)voor meer informatie over kernel-uitbrei dingen in intune en eventuele vereisten.

Deze instellingen worden toegevoegd aan een apparaatconfiguratieprofiel in Intune en vervolgens toegewezen aan of geïmplementeerd op uw macOS-apparaten.

## <a name="before-you-begin"></a>Voordat u begint

[Een configuratie profiel voor kernel-uitbrei dingen voor apparaten maken](../kernel-extensions-overview-macos.md).

> [!NOTE]
> Deze instellingen zijn van toepassing op verschillende inschrijvings typen. Zie voor meer informatie over de verschillende inschrijvings typen [macOS-inschrijving](../macos-enroll.md).

## <a name="kernel-extensions"></a>Kernel-extensies

### <a name="settings-apply-to-user-approved-automated-device-enrollment"></a>Instellingen zijn van toepassing op: door de gebruiker goedgekeurde, automatische registratie van apparaten

- **Gebruikers onderdrukkingen toestaan**: met **toestaan** kunnen gebruikers de kernel-extensies goed keuren die niet zijn opgenomen in het configuratie profiel. **Niet geconfigureerd** (standaard) Hiermee voor komt u dat gebruikers extensies kunnen toestaan die niet zijn opgenomen in het configuratie profiel. Dit betekent dat alleen uitbrei dingen die zijn opgenomen in het configuratie profiel, zijn toegestaan.

  Zie door de [gebruiker goedgekeurde kernel-extensie wordt geladen](https://developer.apple.com/library/archive/technotes/tn2459/_index.html) (opent de website van Apple) voor meer informatie over deze functie.

- **Toegestane team-id's**: met deze instelling kunt u een of meer team-id's toestaan. Alle kernel-uitbrei dingen die zijn ondertekend met de team-Id's die u invoert, zijn toegestaan en worden vertrouwd. Met andere woorden, gebruik deze optie om alle kernel-uitbrei dingen binnen dezelfde team-ID toe te staan. Dit kan ook een specifieke ontwikkelaar of partner zijn.

  **Voeg** een team-ID toe van geldige en ondertekende kernel-uitbrei dingen die u wilt laden. U kunt meerdere team-id's toevoegen. De team-ID moet alfanumeriek zijn (letters en cijfers) en mag uit 10 tekens bestaan. Voer bijvoorbeeld `ABCDE12345` in.

  Nadat u een team-ID hebt toegevoegd, kan deze ook worden verwijderd.

  [Zoek uw team-ID](https://help.apple.com/developer-account/#/dev55c3c710c) (Open de website van Apple) voor meer informatie.

- **Toegestane kernel-extensies**: gebruik deze instelling om specifieke kernel-uitbrei dingen toe te staan. Alleen de kernel-uitbrei dingen die u invoert, worden toegestaan of vertrouwd. 

  **Voeg** de bundel-id en team-ID toe van een kernel-uitbrei ding die u wilt laden. Voor niet-ondertekende verouderde kernel-uitbrei dingen gebruikt u een lege team-ID. U kunt meerdere kernel-uitbrei dingen toevoegen. De team-ID moet alfanumeriek zijn (letters en cijfers) en mag uit 10 tekens bestaan. Voer bijvoorbeeld `com.contoso.appname.macos` in voor de **bundel-id**en `ABCDE12345` voor de **Team-ID**.

  > [!TIP]
  > Als u de bundel-ID van een kernel-uitbrei ding (kext) op een macOS-apparaat wilt ophalen, kunt u het volgende doen:
  >
  > 1. Voer `kextstat | grep -v com.apple` uit in de Terminal en noteer de uitvoer. Installeer de gewenste software of kext. Voer `kextstat | grep -v com.apple` opnieuw uit en zoek naar wijzigingen.
  >
  >    In de Terminal bevat `kextstat` alle kernel-uitbrei dingen op het besturings systeem. 
  >
  > 2. Open op het apparaat het bestand met de eigenschappen lijst van de informatie (info. plist) voor een kext. De bundel-ID wordt weer gegeven. Elk kext bevat een info. plist-bestand dat is opgeslagen in. 

> [!NOTE]
> U hoeft geen team-id's en kernel-uitbrei dingen toe te voegen. U kunt een of de andere configureren.

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](../device-profile-assign.md) en [de status ervan controleren](../device-profile-monitor.md).
