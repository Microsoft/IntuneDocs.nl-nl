---
title: Kioskinstellingen voor Windows Holographic for Business in Microsoft Intune - Azure | Microsoft Docs
description: Configureer uw Windows Holographic for Business-apparaten als kiosken voor één app en voor meerdere apps, pas het menu Start aan, voeg apps toe, geef de taakbalk weer, en configureer een webbrowser in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8c5fd9998a4816775b3fc1d7803dc26e223b1e39
ms.sourcegitcommit: e5f501b396cb8743a8a9dea33381a16caadc51a9
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/23/2019
ms.locfileid: "56742429"
---
# <a name="windows-holographic-for-business-device-settings-to-run-as-a-kiosk-in-intune"></a>Instellingen voor Windows Holographic for Business-apparaten om ze als kiosk uit te voeren via Intune

Op apparaten met Windows Holographic for Business kunt u configureren dat deze apparaten worden uitgevoerd in de kioskmodus met één app of in de kioskmodus met meerdere apps. Sommige functies worden niet ondersteund in Windows Holographic for Business.

Dit artikel bevat een overzicht en beschrijving van de verschillende instellingen die u kunt beheren op apparaten met Windows Holographic for Business. Gebruik deze instellingen voor het configureren van apparaten met Windows Holographic zodat ze in de kioskmodus worden uitgevoerd, als onderdeel van uw MDM-oplossing (Mobile Device Management).

Als Intune-beheerder kunt u deze instellingen maken en toewijzen aan uw apparaten.

Zie voor meer informatie over de Windows-kioskfunctie in Intune [Configure kiosk settings](kiosk-settings.md) (Kioskinstellingen configureren).

## <a name="before-you-begin"></a>Voordat u begint

[Maak het profiel](kiosk-settings.md#create-the-profile).

## <a name="single-full-screen-app-kiosks"></a>Kiosken met één app op een volledig scherm

Wanneer u een kioskmodus voor één app kiest, moet u de volgende instellingen opgeven:

- **Aanmeldingstype gebruiker**: Selecteer **Lokaal gebruikersaccount** om het lokale gebruikersaccount (op het apparaat) of een Microsoft-account (MSA) in te voeren dat is gekoppeld aan de kiosk-app. Gebruikersaccounttypen met het kenmerk **AutoLogon** worden niet ondersteund in Windows Holographic for Business.

- **Toepassingstype**: Selecteer **Store-app**.

- **App uitvoeren in kioskmodus**: Kies **Een Store-app toevoegen** en selecteer een app in de lijst.

    Worden er geen apps in de lijst weergegeven? Voeg er een aantal toe met behulp van de stappen in [Client-apps](apps-add.md).

    Selecteer **OK** om uw wijzigingen op te slaan.

## <a name="multi-app-kiosks"></a>Kiosken voor meerdere apps

Apps in deze modus zijn beschikbaar in het startmenu. Deze apps zijn de enige apps die de gebruiker kan openen. Wanneer u een kioskmodus voor meerdere apps kiest, moet u de volgende instellingen opgeven:

- **Gericht op Windows 10-apparaten in de S-modus**: Kies **Nee**. De S-modus wordt niet ondersteund in Windows Holographic for Business.

- **Aanmeldingstype gebruiker**: Voer een of meer gebruikersaccounts in die de apps kunnen gebruiken die u toevoegt. Uw opties zijn: 

  - **Automatisch aanmelden**: Niet ondersteund in Windows Holographic for Business.
  - **Lokale gebruikersaccounts**: **Voeg** het lokale (op het apparaat) gebruikersaccount toe. Het account dat u opgeeft wordt gebruikt om u aan te melden bij de kiosk.
  - **Azure AD-gebruiker of -groep (Windows 10, versie 1803 of hoger)**: Hiervoor zijn gebruikersreferenties voor aanmelding op het apparaat vereist. Selecteer **Toevoegen** als u Azure AD-gebruikers of -groepen in de lijst wilt kiezen. U kunt meerdere gebruikers en groepen selecteren. Kies **Selecteren** om uw wijzigingen op te slaan.
  - **HoloLens-bezoeker**: Het bezoekersaccount is een gastaccount waarvoor geen gebruikersreferenties zijn of verificatie is vereist, zoals wordt beschreven in [Gedeelde pc-modusconcepten](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Toepassingen**: Voeg de apps toe die u op het apparaat in kioskmodus wilt uitvoeren. U kunt verschillende apps toevoegen.

  - **Store-apps toevoegen**: Selecteer een bestaande app die u hebt toegevoegd met [Client-apps](apps-add.md). Als er geen apps worden weergegeven, kunt u apps aanschaffen en deze [aan Intune toevoegen](store-apps-windows.md).
  - **Win32-app toevoegen**: Niet ondersteund in Windows Holographic for Business.
  - **Toevoegen via AUMID**: Gebruik deze optie om Postvak IN-apps voor Windows toe te voegen. Voer de volgende eigenschappen in: 

    - **Toepassingsnaam**: Vereist. Geef een naam op voor de toepassing.
    - **Model-id van toepassingsgebruiker (AUMID)**: Vereist. Voer de AUMID van de Windows-app in. Zie [De model-id van toepassingsgebruiker van een geïnstalleerde app vinden](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) als u wilt weten hoe u aan deze id komt.
    - **Tegelgrootte**: Vereist. Kies een tegelgrootte Klein, Normaal, Breed of Groot voor de app.

- **Browserinstellingen voor de kiosk**: Niet ondersteund in Windows Holographic for Business.

- **Alternatieve indeling van het menu Start gebruiken**: Selecteer **Ja** om een XML-bestand op te geven waarin wordt beschreven hoe de apps worden weergegeven in het menu Start, zoals de volgorde van de apps. Gebruik deze optie als u meer aanpassingsmogelijkheden wilt gebruiken in het startmenu. [Startopmaak aanpassen en exporteren](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-for-hololens) biedt instructies en bevat een specifiek XML-bestand voor apparaten met Windows Holographic for Business.

- **Windows-taakbalk**: Niet ondersteund in Windows Holographic for Business.

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

U kunt ook kioskprofielen maken voor apparaten met [Android ](device-restrictions-android.md#kiosk), [Android Enterprise](device-restrictions-android-for-work.md#dedicated-device-settings) en [Windows 10 en hoger](kiosk-settings-windows.md).
