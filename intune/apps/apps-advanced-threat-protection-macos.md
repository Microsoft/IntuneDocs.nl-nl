---
title: Microsoft Defender ATP toevoegen aan macOS-apparaten met behulp van Microsoft Intune
titleSuffix: ''
description: Meer informatie over het toevoegen van Microsoft Defender ATP aan macOS-apparaten met behulp van Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/21/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: kellieei
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6ae6e8a621b10ec969fa3fcfb2dfeabb8d5a7bdd
ms.sourcegitcommit: 5881979c45fc973cba382413eaa193d369b8dcf6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "77569557"
---
# <a name="add-microsoft-defender-atp-to-macos-devices-using-microsoft-intune"></a>Microsoft Defender ATP toevoegen aan macOS-apparaten met behulp van Microsoft Intune

Voordat u apps kunt implementeren, configureren, bewaken of beveiligen, moet u deze aan Intune toevoegen. Een van de beschikbare [app-typen](~/apps/apps-add.md#app-types-in-microsoft-intune) is Microsoft Defender Advanced Threat Protection (ATP). Door dit app-type in Intune te selecteren, kunt u Microsoft Defender ATP toewijzen aan en installeren op door u beheerde macOS-apparaten. Met dit app-type kunt u Microsoft Defender ATP eenvoudig toewijzen aan macOS-apparaten zonder dat u gebruik hoeft te maken van de macOS App Wrapping Tool. Deze apps worden geleverd met Microsoft AutoUpdate (MAU) om de apps veiliger te maken en up-to-date te houden.

## <a name="prerequisites"></a>Vereisten
- Op het macOS-apparaat moet macOS 10.13 of later worden uitgevoerd.
- Het macOS-apparaat moet ten minste 650 MB aan schijfruimte hebben.
- Implementeer de kernel-extensie in Intune. Zie [macOS kernel-extensies toevoegen in Intune](~/configuration/kernel-extensions-overview-macos.md) voor meer informatie.

> [!IMPORTANT]
> De kernel-extensie kan alleen automatisch worden goedgekeurd als deze aanwezig is op het apparaat voordat de Microsoft Defender ATP-app is geïnstalleerd. Anders zien gebruikers het bericht 'Systeemextensie geblokkeerd' op Macs en moeten ze de extensie goedkeuren door naar **Beveiligingsvoorkeuren** of **Systeemvoorkeuren** > **Beveiliging en privacy** te gaan en vervolgens **Toestaan** selecteren. Zie [Problemen met kernel-extensies oplossen in Microsoft Defender ATP voor Mac](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-support-kext) voor meer informatie.

## <a name="add-microsoft-defender-atp-to-intune"></a>Microsoft Defender ATP toevoegen aan Intune
U kunt Microsoft Defender ATP toevoegen aan Intune met behulp van de volgende stappen:

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apps** > **Alle apps** > **Toevoegen**.
3. Selecteer in de lijst **App-type** onder **Microsoft Defender ATP** de optie **macOS**.

## <a name="configure-app-information"></a>App-gegevens configureren
In deze stap geeft u informatie op over deze app-implementatie. Aan de hand van deze informatie kunt u de app vinden in Intune en kunnen gebruikers de app vinden in de bedrijfsportal.

1. Selecteer de optie **App-gegevens** om het deelvenster **App-gegevens** weer te geven.
2. In het deelvenster **App-gegevens** geeft u informatie op over deze app-implementatie. Aan de hand van deze informatie kunt u de app vinden in Intune en kunnen gebruikers de app vinden in de bedrijfsportal.
    - **Naam**: Voer de naam van de app in zoals deze in de bedrijfsportal zal worden weergegeven. Zorg ervoor dat alle namen uniek zijn. Als dezelfde app-naam twee keer voorkomt, wordt slechts één van de apps weergegeven voor gebruikers in de bedrijfsportal.
    - **Beschrijving**: Voer een beschrijving in voor de app. U kunt bijvoorbeeld de beoogde gebruikers vermelden in de beschrijving.
    - **Uitgever**: Microsoft wordt weergegeven als de uitgever.
    - **Categorie**: selecteer een of meer ingebouwde app-categorieën of een categorie die u hebt gemaakt (optioneel). Met deze instellingen kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: Selecteer deze optie om de app prominent weer te geven op de hoofdpagina van de bedrijfsportal wanneer gebruikers zoeken naar apps.
    - **Informatie-URL**: Voer de URL in van een website die informatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Privacy-URL**: (optioneel) Voer de URL in van een website die privacyinformatie over deze app bevat. De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Ontwikkelaar**: Microsoft wordt weergegeven als de ontwikkelaar.
    - **Eigenaar**: Microsoft wordt weergegeven als de eigenaar.
    - **Opmerkingen**: Voer de opmerkingen in die u aan deze app wilt koppelen (optioneel).
3. Selecteer **OK**.

## <a name="select-scope-tags-optional"></a>Bereiktags selecteren (optioneel)
U kunt bereiktags gebruiken om te bepalen wie er informatie over client-apps mag bekijken in Intune. Zie Op rollen gebaseerd toegangsbeheer en bereiktags gebruiken voor gedistribueerde IT voor uitgebreide informatie over bereiktags.
1.  Selecteer **Bereik (tags)**  > **Toevoegen**.
2.  Gebruik het vak onder **Selecteren** om bereiktags te zoeken.
3.  Schakel het selectievakje in naast de bereiktags die u aan deze app wilt toewijzen.
4.  Klik op **Selecteren** > **OK**.

## <a name="add-the-app"></a>De app toevoegen
Wanneer u klaar bent met configureren, selecteert u **Toevoegen** in het deelvenster **App-app**. 

De app die u hebt gemaakt, wordt weergegeven in de lijst met apps waar u de app kunt toewijzen aan de groepen die u selecteert. 

> [!NOTE]
> Momenteel biedt Apple geen manier om Microsoft Defender ATP via Intune te verwijderen van macOS-apparaten.

## <a name="next-steps"></a>Volgende stappen
- Zie [Microsoft Defender ATP configureren op macOS-apparaten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-preferences) voor meer informatie over het configureren van Microsoft Defender ATP op macOS-apparaten.
- Zie voor meer informatie over app-toewijzingen opnemen in of uitsluiten uit groepen gebruikers [App-toewijzingen opnemen en uitsluiten](~/apps/apps-inc-exl-assignments.md).
- [Apps aan groepen toewijzen](~/apps/apps-deploy.md)

