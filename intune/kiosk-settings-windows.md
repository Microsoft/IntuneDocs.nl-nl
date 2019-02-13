---
title: Kioskinstellingen voor Windows 10 in Microsoft Intune - Azure | Microsoft Docs
description: Configureer uw apparaten met Windows 10 (en hoger) als kiosken voor één app en voor meerdere apps, pas het menu Start aan, voeg apps toe, toon de taakbalk en configureer een webbrowser in Microsoft Intune.
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
ms.openlocfilehash: 31cfa617e0ca5d8d0848d1ecb781fda701589ccd
ms.sourcegitcommit: 0142020a7cd75348c6367facf072ed94238e667f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2019
ms.locfileid: "55229947"
---
# <a name="windows-10-and-later-device-settings-to-run-as-a-kiosk-in-intune"></a>Instellingen voor apparaten met Windows 10 en hoger om ze als kiosk uit te voeren via Intune

Op apparaten met Windows 10 en hoger kunt u configureren dat deze apparaten worden uitgevoerd in de kioskmodus met één app of in de kioskmodus met meerdere apps.

In dit artikel vindt u een overzicht en beschrijving van de verschillende instellingen die u kunt beheren op apparaten met Windows 10 en hoger. Gebruik deze instellingen voor het configureren van uw apparaten met Windows 10 en hoger, zodat ze in de kioskmodus worden uitgevoerd, als onderdeel van uw MDM-oplossing (Mobile Device Management).

Als Intune-beheerder kunt u deze instellingen maken en toewijzen aan uw apparaten.

Zie voor meer informatie over de Windows-kioskfunctie in Intune [Configure kiosk settings](kiosk-settings.md) (Kioskinstellingen configureren).

## <a name="before-you-begin"></a>Voordat u begint

[Maak het profiel](kiosk-settings.md#create-the-profile).

## <a name="single-full-screen-app-kiosks"></a>Kiosken met één app op een volledig scherm

Wanneer u een kioskmodus voor één app kiest, moet u de volgende instellingen opgeven:

- **Aanmeldingstype van gebruiker**: De apps die u toevoegt worden uitgevoerd als het gebruikersaccount dat u invoert. Uw opties zijn:

  - **Automatisch aanmelden (Windows 10 versie 1803 en hoger)**: Voor kiosken in openbare omgevingen waarbij een gebruiker zich niet hoeft aan te melden, vergelijkbaar met een gastaccount. Deze instelling maakt gebruik van [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp).
  - **Lokaal gebruikersaccount**: Voeg het lokale (op het apparaat) gebruikersaccount toe. Het account dat u opgeeft wordt gebruikt om u aan te melden bij de kiosk.

- **Toepassingstype**: Selecteer **Store-app**.

- **App uitvoeren in kioskmodus**: Kies **Een Store-app toevoegen** en selecteer een app in de lijst.

    Worden er geen apps in de lijst weergegeven? Voeg er een aantal toe met behulp van de stappen in [Client-apps](apps-add.md).

    Selecteer **OK** om uw wijzigingen op te slaan.

- **Browserinstellingen voor de kiosk**: Met deze instellingen beheert u een webbrowser-app op de kiosk. Zorg ervoor dat u de [Kioskbrowser-app](https://businessstore.microsoft.com/store/details/kiosk-browser/9NGB5S5XG2KP) uit de Store ophaalt, deze aan Intune toevoegt als een [client-app](apps-add.md) en vervolgens de app aan de kioskapparaten toewijst.

  Voer de volgende instellingen in:

  - **Standaard-URL voor de startpagina**: Voer de standaard-URL in die wordt weergegeven als de kioskbrowser wordt geopend of opnieuw wordt gestart. Voer bijvoorbeeld `http://bing.com` of `http://www.contoso.com` in.

  - **Knop Start**: **Toon** of **verberg** de knop Start van de kioskbrowser. Standaard wordt de knop niet weergegeven.

  - **Navigatieknoppen**: **Toon** of **verberg** de knoppen Volgende en Vorige. De navigatieknoppen worden standaard niet weergegeven.

  - **Knop Sessie beëindigen**: **Toon** of **verberg** de knop voor het beëindigen van de sessie. Als deze knop wordt getoond, selecteert de gebruiker de knop en wordt in de app gevraagd om de sessie te beëindigen. Wanneer de actie wordt bevestigd, wist de browser alle browsegegevens (cookies, cache etc.) en wordt de standaard-URL geopend. Standaard wordt de knop niet weergegeven.

  - **De browser vernieuwen na niet-actieve tijd**: Voer de niet-actieve tijd (1-1440 minuten) in, waarna de kioskbrowser opnieuw wordt gestart en vernieuwd. Niet-actieve tijd wordt weergegeven als het aantal minuten dat is verstreken sinds de laatste interactie van de gebruiker. De waarde is standaard leeg of blanco, wat inhoudt dat er geen time-out is voor inactiviteit.

  - **Toegestane websites**: Gebruik deze instelling om toe te staan dat bepaalde websites worden geopend. Met andere woorden, gebruik deze functie om het aantal websites dat op het apparaat kan worden geopend, te beperken. U kunt bijvoorbeeld toestaan dat alle websites op `http://contoso.com*` kunnen worden geopend. Standaard worden alle websites toegestaan.
 
      Als u specifieke websites wilt toestaan, moet u een bestand uploaden dat een lijst met toegestane websites op afzonderlijke regels bevat. Als u geen bestand toevoegt, zijn alle websites toegestaan. Intune biedt ondersteuning voor * (sterretje) als jokerteken.

      Het voorbeeldbestand moeten eruitzien als het volgende lijst:

      `http://bing.com`  
      `https://bing.com`  
      `http://contoso.com/*`  
      `https://contoso.com/*`  

  Selecteer **OK** om uw wijzigingen op te slaan.

## <a name="multi-app-kiosks"></a>Kiosken voor meerdere apps

Apps in deze modus zijn beschikbaar in het startmenu. Deze apps zijn de enige apps die de gebruiker kan openen.

Wanneer u een kioskmodus voor meerdere apps kiest, moet u de volgende instellingen opgeven:

- **Gericht op Windows 10-apparaten in de S-modus**: Kies **Ja** als u Store-apps en AUMID-apps (geen Win32-apps) in het kioskprofiel wilt toestaan. Kies **Nee** als u Store-apps, Win32-apps AUMID-apps in het kioskprofiel wilt toestaan. Als u **Nee** kiest, wordt het kioskprofiel niet geïmplementeerd op apparaten in de S-modus.

- **Aanmeldingstype gebruiker**: De apps die u toevoegt worden uitgevoerd als het gebruikersaccount dat u invoert. Uw opties zijn:

  - **Automatisch aanmelden (Windows 10 versie 1803 en hoger)**: Voor kiosken in openbare omgevingen waarbij een gebruiker zich niet hoeft aan te melden, vergelijkbaar met een gastaccount. Deze instelling maakt gebruik van [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp).
  - **Lokaal gebruikersaccount**: **Voeg** het lokale (op het apparaat) gebruikersaccount toe. Het account dat u opgeeft wordt gebruikt om u aan te melden bij de kiosk.
  - **Azure AD-gebruiker of -groep (Windows 10, versie 1803 of hoger)**: Selecteer **Toevoegen** als u Azure AD-gebruikers of -groepen in de lijst wilt kiezen. U kunt meerdere gebruikers en groepen selecteren. Kies **Selecteren** om uw wijzigingen op te slaan.
  - **HoloLens-bezoeker**: Het bezoekersaccount is een gastaccount waarvoor geen gebruikersreferenties zijn of verificatie is vereist, zoals wordt beschreven in [Gedeelde pc-modusconcepten](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Toepassingen**: Voeg de apps toe die u op het apparaat in kioskmodus wilt uitvoeren. U kunt verschillende apps toevoegen.

  - **Store-app toevoegen**: Voeg een app toe uit de Microsoft Store voor Bedrijven. Als er geen apps worden weergegeven, kunt u apps aanschaffen en deze [aan Intune toevoegen](store-apps-windows.md). U kunt bijvoorbeeld Kiosk-Browser, Excel, OneNote en meer toevoegen.

  - **Win32-app toevoegen**: Een Win32-app is een traditionele bureaublad-app, zoals Visual Studio Code of Google Chrome. Voer de volgende eigenschappen in:

    - **Toepassingsnaam**: Vereist. Geef een naam op voor de toepassing.
    - **Lokaal pad**: Vereist. Voer het pad naar het uitvoerbare bestand in, zoals `C:\Program Files (x86)\Microsoft VS Code\Code.exe` of `C:\Program Files (x86)\Google\Chrome\Application\chrome.exe`.
    - **Model-id van toepassingsgebruiker (AUMID)**: Voer de AUMID van de Win32-app in. Deze instelling bepaalt de indeling van de tegel na het opstarten op het bureaublad. Raadpleeg [Get-StartApps](https://docs.microsoft.com/powershell/module/startlayout/get-startapps?view=win10-ps) om deze id op te halen.
    - **Tegelgrootte**: Vereist. Kies een tegelgrootte Klein, Normaal, Breed of Groot voor de app.
  
  - **Toevoegen via AUMID**: Gebruik deze optie om Postvak IN-apps voor Windows, zoals Kladblok of Calculator toe te voegen. Voer de volgende eigenschappen in: 

    - **Toepassingsnaam**: Vereist. Geef een naam op voor de toepassing.
    - **Model-id van toepassingsgebruiker (AUMID)**: Vereist. Voer de AUMID van de Windows-app in. Zie [De model-id van toepassingsgebruiker van een geïnstalleerde app vinden](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) als u wilt weten hoe u aan deze id komt.
    - **Tegelgrootte**: Vereist. Kies een tegelgrootte Klein, Normaal, Breed of Groot voor de app.

  > [!TIP]
  > Nadat u alle apps hebt toegevoegd, kunt u de volgorde ervan wijzigen door er op te klikken en de apps naar een andere positie op de lijst te slepen.  

  Selecteer **OK** om uw wijzigingen op te slaan.

- **Browserinstellingen voor de kiosk**: Met deze instellingen beheert u een webbrowser-app op de kiosk. Implementeer met [Client-apps](apps-add.md) een webbrowser-app op de kioskapparaten.

  Voer de volgende instellingen in:

  - **Standaard-URL voor de startpagina**: Voer de standaard-URL in die wordt weergegeven als de kioskbrowser wordt geopend of opnieuw wordt gestart. Voer bijvoorbeeld `http://bing.com` of `http://www.contoso.com` in.

  - **Knop Start**: **Toon** of **verberg** de knop Start van de kioskbrowser. Standaard wordt de knop niet weergegeven.

  - **Navigatieknoppen**: **Toon** of **verberg** de knoppen Volgende en Vorige. De navigatieknoppen worden standaard niet weergegeven.

  - **Knop Sessie beëindigen**: **Toon** of **verberg** de knop voor het beëindigen van de sessie. Als deze knop wordt getoond, selecteert de gebruiker de knop en wordt in de app gevraagd om de sessie te beëindigen. Wanneer de actie wordt bevestigd, wist de browser alle browsegegevens (cookies, cache etc.) en wordt de standaard-URL geopend. Standaard wordt de knop niet weergegeven.

  - **De browser vernieuwen na niet-actieve tijd**: Voer de niet-actieve tijd (1-1440 minuten) in, waarna de kioskbrowser opnieuw wordt gestart en vernieuwd. Niet-actieve tijd wordt weergegeven als het aantal minuten dat is verstreken sinds de laatste interactie van de gebruiker. De waarde is standaard leeg of blanco, wat inhoudt dat er geen time-out is voor inactiviteit.

  - **Toegestane websites**: Gebruik deze instelling om toe te staan dat bepaalde websites worden geopend. Met andere woorden, gebruik deze functie om het aantal websites dat op het apparaat kan worden geopend, te beperken. U kunt bijvoorbeeld toestaan dat alle websites op `contoso.com*` kunnen worden geopend. Standaard worden alle websites toegestaan.

    Als u alleen bepaalde websites wilt toestaan, moet u een CSV-bestand uploaden dat een lijst met toegestane websites bevat. Als u geen CSV-bestand toevoegt, zijn alle websites toegestaan.

  Selecteer **OK** om uw wijzigingen op te slaan.

- **Alternatieve indeling van het menu Start gebruiken**: Selecteer **Ja** om een XML-bestand op te geven waarin wordt beschreven hoe de apps worden weergegeven in het menu Start, zoals de volgorde van de apps. Gebruik deze optie als u meer aanpassingsmogelijkheden wilt gebruiken in het startmenu. [Customize and export Start layout (Aanpassen en indeling Start exporteren)](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) biedt een aantal richtlijnen en een XML-voorbeeld.

- **Windows-taakbalk**: Kies of u wilt dat de taakbalk wordt **weergegeven** of **verborgen**. Standaard wordt de taakbalk niet weergegeven. Pictogrammen, zoals het Wi-Fi-pictogram, worden weergegeven, maar de instellingen kunnen niet worden gewijzigd door eindgebruikers.

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

U kunt ook kiosk-profielen maken voor apparaten met [Android](device-restrictions-android.md#kiosk), [Android Enterprise](device-restrictions-android-for-work.md#kiosk-settings) en [Windows Holographic for Business](kiosk-settings-holographic.md).
