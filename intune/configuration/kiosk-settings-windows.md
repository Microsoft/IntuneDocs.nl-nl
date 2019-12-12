---
title: Kioskinstellingen voor Windows 10 in Microsoft Intune - Azure | Microsoft Docs
description: Configureer uw apparaten met Windows 10 (en hoger) als kiosken voor één app en voor meerdere apps, pas het menu Start aan, voeg apps toe, toon de taakbalk en configureer een webbrowser in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 80da0e6952c5aaab6fa8146b2d91d32259966d5d
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "74691730"
---
# <a name="windows-10-and-later-device-settings-to-run-as-a-kiosk-in-intune"></a>Instellingen voor apparaten met Windows 10 en hoger om ze als kiosk uit te voeren via Intune

Op apparaten met Windows 10 en hoger kunt u configureren dat deze apparaten worden uitgevoerd in de kioskmodus met één app of in de kioskmodus met meerdere apps.

In dit artikel vindt u een overzicht en beschrijving van de verschillende instellingen die u kunt beheren op apparaten met Windows 10 en hoger. Gebruik deze instellingen voor het configureren van uw apparaten met Windows 10 en hoger, zodat ze in de kioskmodus worden uitgevoerd, als onderdeel van uw MDM-oplossing (Mobile Device Management).

Als Intune-beheerder kunt u deze instellingen maken en toewijzen aan uw apparaten.

Zie voor meer informatie over de Windows-kioskfunctie in Intune [Configure kiosk settings](../kiosk-settings.md) (Kioskinstellingen configureren).

## <a name="before-you-begin"></a>Voordat u begint

- [Maak het profiel](kiosk-settings.md#create-the-profile).

- Dit kioskprofiel is direct gerelateerd aan het apparaatbeperkingsprofiel dat u maakt met behulp van de [Windows Edge kioskinstellingen](device-restrictions-windows-10.md#microsoft-edge-browser). Samenvatting:

  1. Maak dit kioskprofiel om het apparaat in de kioskmodus uit te voeren.
  2. Maak het [apparaatbeperkingsprofiel](device-restrictions-windows-10.md#microsoft-edge-browser) en configureer specifieke functies en instellingen die zijn toegestaan in Microsoft Edge.

- Zorg ervoor dat alle bestanden, scripts en snelkoppelingen zich op het lokale systeem bevinden. Zie voor meer informatie, waaronder andere Windows-vereisten, [aanpassen en de indeling](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout)voor het exporteren van een start.

> [!IMPORTANT]
> Zorg ervoor dat u dit kioskprofiel toewijst aan de dezelfde apparaten als uw [Microsoft Edge-profiel](device-restrictions-windows-10.md#microsoft-edge-browser).

## <a name="single-full-screen-app-kiosks"></a>Kiosken met één app op een volledig scherm

Hiermee wordt slechts één app op het apparaat uitgevoerd.

- **Selecteer een kioskmodus**: kies **één app, volledig-schermweergave**.

- **Aanmeldingstype gebruiker**: de apps die u toevoegt worden uitgevoerd als het gebruikersaccount dat u invoert. Uw opties zijn:

  - **Automatisch aanmelden (Windows 10, versie 1803 en hoger)** : gebruik deze optie in kiosken in openbare omgevingen waar een gebruiker zich niet hoeft aan te melden, vergelijkbaar met een gastaccount. Deze instelling maakt gebruik van [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp).
  - **Lokaal gebruikersaccount**: voer het lokale (op het apparaat) gebruikersaccount in. Met het account dat u invoert, kunt u zich aanmelden bij de kiosk.

- **Toepassingstype**: selecteer het toepassingstype. Uw opties zijn:

  - **Toevoegen van Microsoft Edge-browser**: selecteer **Microsoft Edge-browser**, en kies het **Edge-kioskmodustype**:

    - **Digitale/interactieve ondertekening**: hiermee wordt een volledig URL-scherm geopend en is alleen de inhoud op die website zichtbaar. [Digitale displays instellen](https://docs.microsoft.com/windows/configuration/setup-digital-signage) biedt meer informatie over deze functie.
    - **Openbaar bladeren (InPrivate)** : hiermee wordt een beperkte versie met meerdere tabbladen van Microsoft Edge uitgevoerd. Gebruikers kunnen openbaar bladeren of de browsersessie beëindigen.

    Zie [Microsoft Edge-kioskmodus implementeren](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-configuration-types) voor meer informatie over deze opties.

    > [!NOTE]
    > Via deze instelling schakelt u de Microsoft Edge-browser in op het apparaat. Als u specifieke Microsoft Edge-instellingen wilt configureren, maakt u een apparaatconfiguratieprofiel (**Apparaatconfiguratie** > **Profielen** > **Profiel maken**  >  **Windows 10** voor platform > **Apparaatbeperkingen** >  **Microsoft Edge-browser**). De beschikbare instellingen worden in de [Microsoft Edge-browser](device-restrictions-windows-10.md#microsoft-edge-browser) vermeld en beschreven.

  - **Kioskbrowser toevoegen**: Selecteer **Browserinstellingen voor de kiosk**. Met deze instellingen beheert u een webbrowser-app op de kiosk. Zorg ervoor dat u de [kiosk browser-app](https://businessstore.microsoft.com/store/details/kiosk-browser/9NGB5S5XG2KP) uit de Store haalt, voeg deze toe aan intune als een [client-app](../apps/apps-add.md). Wijs vervolgens de app toe aan de kiosk apparaten.

    Voer de volgende instellingen in:

    - **Standaard-URL voor de startpagina**: voer de standaard-URL die wordt weergegeven als de kioskbrowser wordt geopend of opnieuw wordt gestart. Voer bijvoorbeeld `http://bing.com` of `http://www.contoso.com` in.

    - **De knop Startpagina**: **toon** of **verberg** de knop Startpagina van de kioskbrowser. Standaard wordt de knop niet weergegeven.

    - **Navigatieknoppen**: **toon** of **verberg** de knoppen volgende en vorige. De navigatieknoppen worden standaard niet weergegeven.

    - **Knop sessie beëindigen**: **toon** of **verberg** de knop voor het beëindigen van de sessie. Als deze knop wordt getoond, selecteert de gebruiker de knop en wordt in de app gevraagd om de sessie te beëindigen. Wanneer de actie wordt bevestigd, wist de browser alle browsegegevens (cookies, cache etc.) en wordt de standaard-URL geopend. Standaard wordt de knop niet weergegeven.

    - **De browser vernieuwen na niet-actieve tijd**: voer de niet-actieve tijd (1-1440 minuten) in, waarna de kioskbrowser opnieuw wordt gestart en vernieuwd. Niet-actieve tijd wordt weergegeven als het aantal minuten dat is verstreken sinds de laatste interactie van de gebruiker. De waarde is standaard leeg of blanco, wat inhoudt dat er geen time-out is voor inactiviteit.

    - **Toegestane websites**: gebruik deze instelling om toe te staan dat bepaalde websites worden geopend. Met andere woorden, gebruik deze functie om het aantal websites dat op het apparaat kan worden geopend, te beperken. U kunt bijvoorbeeld toestaan dat alle websites op `http://contoso.com` kunnen worden geopend. Standaard worden alle websites toegestaan.

      Als u specifieke websites wilt toestaan, moet u een bestand uploaden dat een lijst met toegestane websites op afzonderlijke regels bevat. Als u geen bestand toevoegt, zijn alle websites toegestaan. Standaard biedt intune ondersteuning voor joker tekens. Als u dus het domein, zoals `sharepoint.com`, toestaat, kunnen subdomeinen automatisch worden toegestaan, zoals `contoso.sharepoint.com`, `my.sharepoint.com`, enzovoort.

      Het voorbeeldbestand moeten eruitzien als het volgende lijst:

      `http://bing.com`  
      `https://bing.com`  
      `http://contoso.com`  
      `https://contoso.com`  
      `office.com`

    > [!NOTE]
    > Windows 10-kiosken met automatische logo's ingeschakeld in micro soft kiosk browser moet een offline licentie van de Microsoft Store voor bedrijven gebruiken. Deze vereiste is omdat automatisch aanmelden gebruikmaakt van een lokale gebruikers account zonder referenties voor Azure Active Directory (AD). Online licenties kunnen daarom niet worden geëvalueerd. Zie voor meer informatie het [distribueren van offline-Apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps).

  - **Een Store-app toevoegen**: selecteer **Een Store-app toevoegen** en kies een app uit de lijst.

    Worden er geen apps in de lijst weergegeven? Voeg er een aantal toe met behulp van de stappen in [Client-apps](../apps/apps-add.md).
    
 - **Onderhouds venster voor het opnieuw opstarten van de app opgeven**: standaard is niet geconfigureerd, selecteer vereisen om te controleren of er apps zijn die opnieuw moeten worden opgestart om de installatie te volt ooien.
 
     Als u kiosk browser of andere Microsoft Store voor zakelijke apps gebruikt, moet u bepalen hoe vaak moet worden gecontroleerd op app-updates die opnieuw moeten worden gestart om de installatie van de toepassing te volt ooien. Als dat niet zo is geconfigureerd, worden de Microsoft Store voor zakelijke apps na de installatie van een App-Update op een niet-gepland tijdstip 3 dagen opnieuw opgestart.
     
     - **Begin tijd van onderhouds venster**: Selecteer de datum en tijd van de dag waarop u clients wilt controleren op alle app-updates die opnieuw moeten worden gestart. De reguliere begintijd is middernacht, oftewel nul minuten.
     
     - **Terugkeer patroon van onderhouds venster**: standaard is dagelijks.
         Stel in hoe vaak onderhouds Vensters voor app-updates worden uitgevoerd. Aanbeveling is dagelijks om te voor komen dat niet-geplande apps opnieuw worden gestart.

  [ApplicationManagement/ScheduleForceRestartForUpdateFailures CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement#applicationmanagement-scheduleforcerestartforupdatefailures)

## <a name="multi-app-kiosks"></a>Kiosken voor meerdere apps

Apps in deze modus zijn beschikbaar in het startmenu. Deze apps zijn de enige apps die de gebruiker kan openen. Als een app een afhankelijkheid van een andere app heeft, moeten beide worden opgenomen in de lijst met toegestane apps. De 64-bits Internet Explorer-versie heeft bijvoorbeeld een afhankelijkheid van de 32-bits Internet Explorer-versie, dus moet u zowel C:\Program Files\internet explorer\iexplore.exe als C:\Program Files (x86)\Internet Explorer\iexplore.exe toestaan. 

- **Een kioskmodus selecteren**: Kies de optie **Kiosk voor meerdere apps**.

- **Gericht op Windows 10-apparaten in de S-modus**:
  - **Ja**: hiermee staat u Store-apps en AUMID-apps (geen Win32-apps) in het kioskprofiel toe.
  - **Nee**: hiermee staat u Store-apps, Win32-apps en AUMID-apps in het kioskprofiel toe. Dit kioskprofiel wordt niet geïmplementeerd op apparaten in de S-modus.

- **Aanmeldingstype gebruiker**: de apps die u toevoegt worden uitgevoerd als het gebruikersaccount dat u invoert. Uw opties zijn:

  - **Automatisch aanmelden (Windows 10, versie 1803 en hoger)** : gebruik deze optie in kiosken in openbare omgevingen waar een gebruiker zich niet hoeft aan te melden, vergelijkbaar met een gastaccount. Deze instelling maakt gebruik van [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp).
  - **Lokaal gebruikersaccount**: **voeg** het lokale (op het apparaat) gebruikersaccount toe. Met het account dat u invoert, kunt u zich aanmelden bij de kiosk.
  - **Azure AD-gebruiker of -groep (Windows 10, versie 1803 en hoger)** : selecteer **Toevoegen** en kies Azure AD-gebruikers of -groepen in de lijst. U kunt meerdere gebruikers en groepen selecteren. Kies **Selecteren** om uw wijzigingen op te slaan.
  - **HoloLens-bezoeker**: het bezoekersaccount is een gastaccount waarvoor geen gebruikersreferenties of verificatie is vereist, zoals wordt beschreven in [Gedeelde pc-modusconcepten](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Browser en toepassingen**: voeg de apps toe die u op het apparaat in kioskmodus wilt uitvoeren. U kunt verschillende apps toevoegen.

  - **Browsers**

    - **Microsoft Edge toevoegen**: Microsoft Edge wordt toegevoegd aan het app-raster en alle toepassingen kunnen op deze kiosk worden uitgevoerd. Het **Microsoft Edge-kioskmodustype kiezen**:

      - **Normale modus (volledige versie van Microsoft Edge)** : hiermee wordt een volledige-versie van Microsoft Edge uitgevoerd met alle bladerfuncties. Gebruikersgegevens en -statussen worden tussen sessies opgeslagen.
      - **Openbaar bladeren (InPrivate)** : hiermee wordt een versie met meerdere tabbladen van Microsoft Edge InPrivate uitgevoerd met een op maat gemaakte ervaring voor kiosken die worden uitgevoerd in de modus Volledig scherm.

      Zie [Microsoft Edge-kioskmodus implementeren](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-configuration-types) voor meer informatie over deze opties.

      > [!NOTE]
      > Via deze instelling schakelt u de Microsoft Edge-browser in op het apparaat. Als u specifieke Microsoft Edge-instellingen wilt configureren, maakt u een apparaatconfiguratieprofiel (**Apparaatconfiguratie** > **Profielen** > **Profiel maken**  >  **Windows 10** voor platform > **Apparaatbeperkingen** >  **Microsoft Edge-browser**). De beschikbare instellingen worden in de [Microsoft Edge-browser](device-restrictions-windows-10.md#microsoft-edge-browser) vermeld en beschreven.

    - **Kioskbrowser toevoegen**: met deze instellingen beheert u een webbrowser-app in de kiosk. Implementeer met [Client-apps](../apps/apps-add.md) een webbrowser-app op de kioskapparaten.

      Voer de volgende instellingen in:

      - **Standaard-URL voor de startpagina**: voer de standaard-URL die wordt weergegeven als de kioskbrowser wordt geopend of opnieuw wordt gestart. Voer bijvoorbeeld `http://bing.com` of `http://www.contoso.com` in.

      - **De knop Startpagina**: **toon** of **verberg** de knop Startpagina van de kioskbrowser. Standaard wordt de knop niet weergegeven.

      - **Navigatieknoppen**: **toon** of **verberg** de knoppen volgende en vorige. De navigatieknoppen worden standaard niet weergegeven.

      - **Knop sessie beëindigen**: **toon** of **verberg** de knop voor het beëindigen van de sessie. Als deze knop wordt getoond, selecteert de gebruiker de knop en wordt in de app gevraagd om de sessie te beëindigen. Wanneer de actie wordt bevestigd, wist de browser alle browsegegevens (cookies, cache etc.) en wordt de standaard-URL geopend. Standaard wordt de knop niet weergegeven.

      - **De browser vernieuwen na niet-actieve tijd**: voer de niet-actieve tijd (1-1440 minuten) in, waarna de kioskbrowser opnieuw wordt gestart en vernieuwd. Niet-actieve tijd wordt weergegeven als het aantal minuten dat is verstreken sinds de laatste interactie van de gebruiker. De waarde is standaard leeg of blanco, wat inhoudt dat er geen time-out is voor inactiviteit.

      - **Toegestane websites**: gebruik deze instelling om toe te staan dat bepaalde websites worden geopend. Met andere woorden, gebruik deze functie om het aantal websites dat op het apparaat kan worden geopend, te beperken. U kunt bijvoorbeeld toestaan dat alle websites op `contoso.com*` kunnen worden geopend. Standaard worden alle websites toegestaan.

        Als u alleen bepaalde websites wilt toestaan, moet u een CSV-bestand uploaden dat een lijst met toegestane websites bevat. Als u geen CSV-bestand toevoegt, zijn alle websites toegestaan.

      > [!NOTE]
      > Windows 10-kiosken met automatische logo's ingeschakeld in micro soft kiosk browser moet een offline licentie van de Microsoft Store voor bedrijven gebruiken. Deze vereiste is omdat automatisch aanmelden gebruikmaakt van een lokale gebruikers account zonder referenties voor Azure Active Directory (AD). Online licenties kunnen daarom niet worden geëvalueerd. Zie voor meer informatie het [distribueren van offline-Apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps).

  - **Toepassingen**

    - **Store-app toevoegen**: voeg een app toe uit de Microsoft Store voor Bedrijven. Als er geen apps worden weergegeven, kunt u apps aanschaffen en deze [aan Intune toevoegen](../apps/store-apps-windows.md). U kunt bijvoorbeeld Kiosk-Browser, Excel, OneNote en meer toevoegen.

    - **Win32-app toevoegen**: een Win32-app is een traditionele bureaublad-app, zoals Visual Studio Code of Google Chrome. Voer de volgende eigenschappen in:

      - **Toepassingsnaam**: vereist. Geef een naam op voor de toepassing.
      - **Lokaal pad**: vereist. Voer het pad naar het uitvoerbare bestand in, zoals `C:\Program Files (x86)\Microsoft VS Code\Code.exe` of `C:\Program Files (x86)\Google\Chrome\Application\chrome.exe`.
      - **Model-id van de toepassingsgebruiker (AUMID)** : voer het model-id van de toepassingsgebruiker (AUMID) van de Win32-app in. Deze instelling bepaalt de indeling van de tegel na het opstarten op het bureaublad. Raadpleeg [Get-StartApps](https://docs.microsoft.com/powershell/module/startlayout/get-startapps?view=win10-ps) om deze id op te halen.

    - **Toevoegen via AUMID**: gebruik deze optie om Postvak IN-apps voor Windows, zoals Kladblok of Calculator toe te voegen. Voer de volgende eigenschappen in:

      - **Toepassingsnaam**: vereist. Geef een naam op voor de toepassing.
      - **Model-id van toepassingsgebruiker (AUMID)** : vereist. Voer de AUMID van de Windows-app in. Zie [De model-id van toepassingsgebruiker van een geïnstalleerde app vinden](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) als u wilt weten hoe u aan deze id komt.

    - **AutoLaunch**: optioneel. Kies de AutoLaunch-instelling om een toepassing automatisch te starten wanneer de gebruiker zich aanmeldt. Er kan slechts één app automatisch worden gestart.
    - **Tegelgrootte**: vereist. Kies een tegelgrootte Klein, Normaal, Breed of Groot voor de app.

  > [!TIP]
  > Nadat u alle apps hebt toegevoegd, kunt u de volgorde ervan wijzigen door er op te klikken en de apps naar een andere positie op de lijst te slepen.  

- **Alternatieve lay-out van het menu Start gebruiken**: kies **Ja** om een XML-bestand op te geven, waarin wordt beschreven hoe de apps worden weergegeven in het startmenu, zoals de volgorde van de apps. Gebruik deze optie als u meer aanpassingsmogelijkheden wilt gebruiken in het startmenu. [Customize and export Start layout (Aanpassen en indeling Start exporteren)](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) biedt een aantal richtlijnen en een XML-voorbeeld.

- **Windows-taakbalk**: kies of u wilt dat de taakbalk wordt **weergegeven** of **verborgen**. Standaard wordt de taakbalk niet weergegeven. Pictogrammen, zoals het Wi-Fi-pictogram, worden weergegeven, maar de instellingen kunnen niet worden gewijzigd door eindgebruikers.

- **Toegang tot de map Downloads toestaan**: kies **Ja** om gebruikers toegang te verlenen tot de map Downloads in Windows Verkenner. Toegang tot de map Downloads is standaard uitgeschakeld. Deze functie wordt vaak gebruikt voor eindgebruikers om items te openen die zijn gedownload vanuit een browser.

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

U kunt ook kiosk-profielen maken voor apparaten met [Android](device-restrictions-android.md#kiosk), [Android Enterprise](device-restrictions-android-for-work.md#dedicated-device-settings) en [Windows Holographic for Business](kiosk-settings-holographic.md).

Zie ook [een kiosk met één app instellen](https://docs.microsoft.com/windows/configuration/kiosk-single-app) of [een kiosk voor meerdere apps instellen](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps) in de Windows-richt lijnen.
