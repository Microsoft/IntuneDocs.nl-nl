---
title: Kioskinstellingen voor Windows 10 in Microsoft Intune - Azure | Microsoft Docs
description: Configureer uw apparaten met Windows 10 (en hoger) als kiosken voor één app en voor meerdere apps, pas het menu Start aan, voeg apps toe, toon de taakbalk en configureer een webbrowser in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/13/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 78b47decc297c58feadb7cd507a3ff09070d46d4
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57565737"
---
# <a name="windows-10-and-later-device-settings-to-run-as-a-kiosk-in-intune"></a>Instellingen voor apparaten met Windows 10 en hoger om ze als kiosk uit te voeren via Intune

Op apparaten met Windows 10 en hoger kunt u configureren dat deze apparaten worden uitgevoerd in de kioskmodus met één app of in de kioskmodus met meerdere apps.

In dit artikel vindt u een overzicht en beschrijving van de verschillende instellingen die u kunt beheren op apparaten met Windows 10 en hoger. Gebruik deze instellingen voor het configureren van uw apparaten met Windows 10 en hoger, zodat ze in de kioskmodus worden uitgevoerd, als onderdeel van uw MDM-oplossing (Mobile Device Management).

Als Intune-beheerder kunt u deze instellingen maken en toewijzen aan uw apparaten.

Zie voor meer informatie over de Windows-kioskfunctie in Intune [Configure kiosk settings](kiosk-settings.md) (Kioskinstellingen configureren).

## <a name="before-you-begin"></a>Voordat u begint

- [Maak het profiel](kiosk-settings.md#create-the-profile).

- Deze kiosk-profiel is direct gerelateerd aan het apparaatbeperkingsprofiel u maken met behulp van de [kiosk-instellingen voor Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser). Samenvatting:

  1. Maak deze kiosk-profiel voor het uitvoeren van het apparaat in kioskmodus bevindt.
  2. Maak de [apparaatbeperkingsprofiel](device-restrictions-windows-10.md#microsoft-edge-browser), en configureren van specifieke functies en instellingen die zijn toegestaan in Microsoft Edge.

> [!IMPORTANT] 
> Zorg ervoor dat u deze kiosk-profiel toewijzen aan de dezelfde apparaten als uw [Microsoft Edge-profiel](device-restrictions-windows-10.md#microsoft-edge-browser).

## <a name="single-full-screen-app-kiosks"></a>Kiosken met één app op een volledig scherm

Slechts één app uitvoert op het apparaat.

- **Selecteer een kioskmodus**: kies **één app, volledig scherm kiosk**.

- **Aanmeldingstype gebruiker**: de apps die u toevoegt worden uitgevoerd als het gebruikersaccount dat u invoert. Uw opties zijn:

  - **Automatisch aanmelden (Windows 10, versie 1803 en hoger)**: gebruik deze optie in kiosken in openbare omgevingen waar een gebruiker zich niet hoeft aan te melden, vergelijkbaar met een gastaccount. Deze instelling maakt gebruik van [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp).
  - **Lokaal gebruikersaccount**: voer het lokale (op het apparaat) gebruikersaccount in. Het account dat u zich aanmeldt en de kiosk opgeven.

- **Toepassingstype**: Selecteer het toepassingstype. Uw opties zijn:

  - **Toevoegen van Microsoft Edge-browser**: Selecteer **Microsoft Edge-browser**, en kies de **kiosk modus type van de rand**:

    - **Digitale/interactief borden tot stand brengen**: een URL-volledig scherm geopend en ziet u alleen de inhoud op die website. [Instellen van digitale borden](https://docs.microsoft.com/windows/configuration/setup-digital-signage) vindt u meer informatie over deze functie.
    - **Openbare bladeren (InPrivate)**: een beperkte meerdere tabblad-versie van Microsoft Edge wordt uitgevoerd. Gebruikers kunnen bladeren openbaar of beëindigen van de browsersessie.

    Zie voor meer informatie over deze opties [implementeren Microsoft Edge-kioskmodus](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-configuration-types).

    > [!NOTE]
    > Deze instelling schakelt u de browser Microsoft Edge op het apparaat. Als u wilt configureren in Microsoft Edge-specifieke instellingen, een apparaatconfiguratieprofiel maken (**apparaatconfiguratie** > **profielen** > **-profielmaken**  >  **Windows 10** voor platform > **Apparaatbeperkingen** >  **Microsoft Edge-Browser**). [Microsoft Edge-browser](device-restrictions-windows-10.md#microsoft-edge-browser) bevat en een beschrijving van de beschikbare instellingen.

    Selecteer **OK** om uw wijzigingen op te slaan.

  - **Toevoegen van de Kiosk-browser**: Selecteer **browser kioskinstellingen**. Met deze instellingen beheert u een webbrowser-app op de kiosk. Zorg ervoor dat u de [Kioskbrowser-app](https://businessstore.microsoft.com/store/details/kiosk-browser/9NGB5S5XG2KP) uit de Store ophaalt, deze aan Intune toevoegt als een [client-app](apps-add.md) en vervolgens de app aan de kioskapparaten toewijst.

    Voer de volgende instellingen in:

    - **Standaard-URL voor de startpagina**: voer de standaard-URL die wordt weergegeven als de kioskbrowser wordt geopend of opnieuw wordt gestart. Voer bijvoorbeeld `http://bing.com` of `http://www.contoso.com` in.

    - **De knop Startpagina**: **toon** of **verberg** de knop Startpagina van de kioskbrowser. Standaard wordt de knop niet weergegeven.

    - **Navigatieknoppen**: **toon** of **verberg** de knoppen volgende en vorige. De navigatieknoppen worden standaard niet weergegeven.

    - **Knop sessie beëindigen**: **toon** of **verberg** de knop voor het beëindigen van de sessie. Als deze knop wordt getoond, selecteert de gebruiker de knop en wordt in de app gevraagd om de sessie te beëindigen. Wanneer de actie wordt bevestigd, wist de browser alle browsegegevens (cookies, cache etc.) en wordt de standaard-URL geopend. Standaard wordt de knop niet weergegeven.

    - **De browser vernieuwen na niet-actieve tijd**: voer de niet-actieve tijd (1-1440 minuten) in, waarna de kioskbrowser opnieuw wordt gestart en vernieuwd. Niet-actieve tijd wordt weergegeven als het aantal minuten dat is verstreken sinds de laatste interactie van de gebruiker. De waarde is standaard leeg of blanco, wat inhoudt dat er geen time-out is voor inactiviteit.

    - **Toegestane websites**: gebruik deze instelling om toe te staan dat bepaalde websites worden geopend. Met andere woorden, gebruik deze functie om het aantal websites dat op het apparaat kan worden geopend, te beperken. U kunt bijvoorbeeld toestaan dat alle websites op `http://contoso.com*` kunnen worden geopend. Standaard worden alle websites toegestaan.

      Als u specifieke websites wilt toestaan, moet u een bestand uploaden dat een lijst met toegestane websites op afzonderlijke regels bevat. Als u geen bestand toevoegt, zijn alle websites toegestaan. Intune biedt ondersteuning voor `*` (sterretje) als jokerteken.

      Het voorbeeldbestand moeten eruitzien als het volgende lijst:

      `http://bing.com`  
      `https://bing.com`  
      `http://contoso.com/*`  
      `https://contoso.com/*`  

    Selecteer **OK** om uw wijzigingen op te slaan.

  - **De app Store toevoegen**: Selecteer **een store-app toevoegen**, en kiest u een app in de lijst.

    Worden er geen apps in de lijst weergegeven? Voeg er een aantal toe met behulp van de stappen in [Client-apps](apps-add.md).

  Selecteer **OK** om uw wijzigingen op te slaan.

## <a name="multi-app-kiosks"></a>Kiosken voor meerdere apps

Apps in deze modus zijn beschikbaar in het startmenu. Deze apps zijn de enige apps die de gebruiker kan openen. Als een app een afhankelijkheid van een andere app heeft, moeten beide worden opgenomen in de lijst met toegestane apps. Internet Explorer, 64-bits heeft bijvoorbeeld een afhankelijkheid van Internet Explorer 32-bits, dus moet u zowel "C:\Program Files\internet explorer\iexplore.exe" en 'C:\Program Files (x86) \Internet' toestaan. 

- **Selecteer een kioskmodus**: kies **kiosk voor meerdere Apps**.

- **Gericht op Windows 10-apparaten in de S-modus**:
  - **Ja**: hiermee staat u Store-apps en AUMID-apps (geen Win32-apps) in het kioskprofiel toe.
  - **Nee**: hiermee staat u Store-apps, Win32-apps en AUMID-apps in het kioskprofiel toe. Deze kiosk-profiel is niet geïmplementeerd op apparaten van de S-modus.

- **Aanmeldingstype gebruiker**: de apps die u toevoegt worden uitgevoerd als het gebruikersaccount dat u invoert. Uw opties zijn:

  - **Automatisch aanmelden (Windows 10, versie 1803 en hoger)**: gebruik deze optie in kiosken in openbare omgevingen waar een gebruiker zich niet hoeft aan te melden, vergelijkbaar met een gastaccount. Deze instelling maakt gebruik van [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp).
  - **Lokaal gebruikersaccount**: **voeg** het lokale (op het apparaat) gebruikersaccount toe. Het account dat u zich aanmeldt en de kiosk opgeven.
  - **Azure AD-gebruiker of -groep (Windows 10, versie 1803 en hoger)**: selecteer **Toevoegen** en kies Azure AD-gebruikers of -groepen in de lijst. U kunt meerdere gebruikers en groepen selecteren. Kies **Selecteren** om uw wijzigingen op te slaan.
  - **HoloLens-bezoeker**: het bezoekersaccount is een gastaccount waarvoor geen gebruikersreferenties of verificatie is vereist, zoals wordt beschreven in [Gedeelde pc-modusconcepten](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Browser en toepassingen**: voeg de apps toe die u op het apparaat in kioskmodus wilt uitvoeren. U kunt verschillende apps toevoegen.

  - **Browsers**

    - **Toevoegen van Microsoft Edge**: Microsoft Edge wordt toegevoegd aan het raster app en alle toepassingen kunnen worden uitgevoerd op deze kiosk. Kies de **Microsoft Edge kiosk modus type**:

      - **Normale modus (volledige versie van Microsoft Edge)**: een volledige-versie van Microsoft Edge wordt uitgevoerd met alle functies van de browser. Gebruikersgegevens en -status worden tussen sessies opgeslagen.
      - **Openbare bladeren (InPrivate)**: een meerdere tabblad-versie van Microsoft Edge InPrivate-navigatie wordt uitgevoerd met een op maat gemaakte ervaring voor kiosken die worden uitgevoerd in de modus volledig scherm.

      Zie voor meer informatie over deze opties [implementeren Microsoft Edge-kioskmodus](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-configuration-types).

      > [!NOTE]
      > Deze instelling schakelt u de browser Microsoft Edge op het apparaat. Als u wilt configureren in Microsoft Edge-specifieke instellingen, een apparaatconfiguratieprofiel maken (**apparaatconfiguratie** > **profielen** > **-profielmaken**  >  **Windows 10** voor platform > **Apparaatbeperkingen** >  **Microsoft Edge-Browser**). [Microsoft Edge-browser](device-restrictions-windows-10.md#microsoft-edge-browser) bevat en een beschrijving van de beschikbare instellingen.

      Selecteer **OK** om uw wijzigingen op te slaan.

    - **Kioskbrowser toevoegen**: met deze instellingen beheert u een webbrowser-app in de kiosk. Implementeer met [Client-apps](apps-add.md) een webbrowser-app op de kioskapparaten.

      Voer de volgende instellingen in:

      - **Standaard-URL voor de startpagina**: voer de standaard-URL die wordt weergegeven als de kioskbrowser wordt geopend of opnieuw wordt gestart. Voer bijvoorbeeld `http://bing.com` of `http://www.contoso.com` in.

      - **De knop Startpagina**: **toon** of **verberg** de knop Startpagina van de kioskbrowser. Standaard wordt de knop niet weergegeven.

      - **Navigatieknoppen**: **toon** of **verberg** de knoppen volgende en vorige. De navigatieknoppen worden standaard niet weergegeven.

      - **Knop sessie beëindigen**: **toon** of **verberg** de knop voor het beëindigen van de sessie. Als deze knop wordt getoond, selecteert de gebruiker de knop en wordt in de app gevraagd om de sessie te beëindigen. Wanneer de actie wordt bevestigd, wist de browser alle browsegegevens (cookies, cache etc.) en wordt de standaard-URL geopend. Standaard wordt de knop niet weergegeven.

      - **De browser vernieuwen na niet-actieve tijd**: voer de niet-actieve tijd (1-1440 minuten) in, waarna de kioskbrowser opnieuw wordt gestart en vernieuwd. Niet-actieve tijd wordt weergegeven als het aantal minuten dat is verstreken sinds de laatste interactie van de gebruiker. De waarde is standaard leeg of blanco, wat inhoudt dat er geen time-out is voor inactiviteit.

      - **Toegestane websites**: gebruik deze instelling om toe te staan dat bepaalde websites worden geopend. Met andere woorden, gebruik deze functie om het aantal websites dat op het apparaat kan worden geopend, te beperken. U kunt bijvoorbeeld toestaan dat alle websites op `contoso.com*` kunnen worden geopend. Standaard worden alle websites toegestaan.

        Als u alleen bepaalde websites wilt toestaan, moet u een CSV-bestand uploaden dat een lijst met toegestane websites bevat. Als u geen CSV-bestand toevoegt, zijn alle websites toegestaan.

      Selecteer **OK** om uw wijzigingen op te slaan.

  - **Toepassingen**

    - **Store-app toevoegen**: voeg een app toe uit de Microsoft Store voor Bedrijven. Als er geen apps worden weergegeven, kunt u apps aanschaffen en deze [aan Intune toevoegen](store-apps-windows.md). U kunt bijvoorbeeld Kiosk-Browser, Excel, OneNote en meer toevoegen.

      Selecteer **OK** om uw wijzigingen op te slaan.

    - **Win32-app toevoegen**: een Win32-app is een traditionele bureaublad-app, zoals Visual Studio Code of Google Chrome. Voer de volgende eigenschappen in:

      - **Toepassingsnaam**: vereist. Geef een naam op voor de toepassing.
      - **Lokaal pad**: vereist. Voer het pad naar het uitvoerbare bestand in, zoals `C:\Program Files (x86)\Microsoft VS Code\Code.exe` of `C:\Program Files (x86)\Google\Chrome\Application\chrome.exe`.
      - **Model-id van de toepassingsgebruiker (AUMID)**: voer het model-id van de toepassingsgebruiker (AUMID) van de Win32-app in. Deze instelling bepaalt de indeling van de tegel na het opstarten op het bureaublad. Raadpleeg [Get-StartApps](https://docs.microsoft.com/powershell/module/startlayout/get-startapps?view=win10-ps) om deze id op te halen.

      Selecteer **OK** om uw wijzigingen op te slaan.

    - **Toevoegen via AUMID**: gebruik deze optie om Postvak IN-apps voor Windows, zoals Kladblok of Calculator toe te voegen. Voer de volgende eigenschappen in:

      - **Toepassingsnaam**: vereist. Geef een naam op voor de toepassing.
      - **Model-id van toepassingsgebruiker (AUMID)**: vereist. Voer de AUMID van de Windows-app in. Zie [De model-id van toepassingsgebruiker van een geïnstalleerde app vinden](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) als u wilt weten hoe u aan deze id komt.

      Selecteer **OK** om uw wijzigingen op te slaan.

    - **Tegelgrootte**: vereist. Kies een tegelgrootte Klein, Normaal, Breed of Groot voor de app.

  > [!TIP]
  > Nadat u alle apps hebt toegevoegd, kunt u de volgorde ervan wijzigen door er op te klikken en de apps naar een andere positie op de lijst te slepen.  

- **Alternatieve lay-out van het menu Start gebruiken**: kies **Ja** om een XML-bestand op te geven, waarin wordt beschreven hoe de apps worden weergegeven in het startmenu, zoals de volgorde van de apps. Gebruik deze optie als u meer aanpassingsmogelijkheden wilt gebruiken in het startmenu. [Customize and export Start layout (Aanpassen en indeling Start exporteren)](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) biedt een aantal richtlijnen en een XML-voorbeeld.

- **Windows-taakbalk**: kies of u wilt dat de taakbalk wordt **weergegeven** of **verborgen**. Standaard wordt de taakbalk niet weergegeven. Pictogrammen, zoals het Wi-Fi-pictogram, worden weergegeven, maar de instellingen kunnen niet worden gewijzigd door eindgebruikers.

Selecteer **OK** om uw wijzigingen op te slaan.

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

U kunt ook kiosk-profielen maken voor apparaten met [Android](device-restrictions-android.md#kiosk), [Android Enterprise](device-restrictions-android-for-work.md#dedicated-device-settings) en [Windows Holographic for Business](kiosk-settings-holographic.md).
