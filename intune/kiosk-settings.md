---
title: Kioskinstellingen voor Windows 10 in Microsoft Intune - Azure | Microsoft Docs
description: Configureer uw apparaten met Windows 10 (en hoger) als kiosken voor één app en voor meerdere apps, inclusief het aanpassen van het startmenu, het toevoegen van apps, de taakbalk en het configureren van een webbrowser. Configureer ook Windows Holographic for Business-apparaten als kiosken met meerdere apps in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 59e2ab4635c8488b99781ac123aacd0854967dc8
ms.sourcegitcommit: c3ac9e5f6240223cb5dfed8b44c7425066d6ea86
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/17/2018
ms.locfileid: "49380028"
---
# <a name="kiosk-settings-for-windows-10-and-later-in-intune"></a>Kioskinstellingen voor Windows 10 (en hoger) in Intune

Op Windows 10-apparaten kunt u Intune gebruiken om deze apparaten als een kiosk uit te voeren. De kiosk kan één app uitvoeren of veel apps uitvoeren. U kunt ook een startmenu weergeven en aanpassen, diverse apps toevoegen, waaronder Win32-apps, een specifieke startpagina aan een webbrowser toevoegen en meer. 

Gebruik de stappen in dit artikel om een kiosk met één app of een kiosk met meerdere apps in Intune te maken.

Intune biedt ondersteuning voor één kioskprofiel per apparaat. Als u meerdere kioskprofielen op één apparaat nodig hebt, kunt u een [aangepaste OMA URI gebruiken](custom-settings-windows-10.md).

## <a name="kiosk-settings"></a>Kioskinstellingen

1. Selecteer in [Azure Portal](https://portal.azure.com) **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
2. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Voer de volgende eigenschappen in:

   - **Naam**: voer een beschrijvende naam in voor het nieuwe profiel.
   - **Beschrijving:** voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
   - **Platform**: selecteer **Windows 10 en hoger**
   - **Profieltype**: selecteer **Kiosk (Preview)**

4. Selecteer een **kioskmodus**. **Kioskmodus** geeft het type kioskmodus aan dat door het beleid wordt ondersteund. Opties zijn onder andere:

    - **Niet geconfigureerd** (standaardinstelling): er wordt door het beleid geen kioskmodus ingeschakeld.
    - **Kiosk met één app, in volledige schermweergave**: het apparaat wordt uitgevoerd als een enkel gebruikersaccount en wordt vastgemaakt een enkele Store-app. Dus wanneer de gebruiker zich aanmeldt, wordt een specifieke app gestart. Deze modus voorkomt ook dat de gebruiker nieuwe apps kan openen of de actieve app kan wijzigen.
    - **Kiosk voor meerdere Apps**: op het apparaat worden meerdere Store-apps, Win32-apps of postvak IN-apps voor Windows uitgevoerd met behulp van de model-id van toepassingsgebruiker (AUMID). Alleen de apps die u toevoegt, zijn op het apparaat beschikbaar.

        Het voordeel van een kiosk voor meerdere apps, of apparaat voor een bepaald doeleinde, is dat het eenvoudig is in het gebruik omdat de gebruikers alleen toegang krijgen tot de apps die ze nodig hebben. Daarnaast worden de apps die de gebruikers niet nodig hebben niet weergegeven.

## <a name="single-full-screen-app-kiosks"></a>Kiosken met één app op een volledig scherm
Wanneer u een kioskmodus voor één app kiest, moet u de volgende instellingen opgeven:

- **Aanmeldingstype gebruiker**: de apps die u toevoegt worden uitgevoerd als het gebruikersaccount dat u invoert. Uw opties zijn:

  - **Automatisch aanmelden (Windows 10, versie 1803 en hoger)**: voor kiosken in openbare omgevingen waar een gebruiker zich niet hoeft aan te melden, vergelijkbaar met een gastaccount. Deze instelling maakt gebruik van [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp).
  - **Lokaal gebruikersaccount**: voer het lokale (op het apparaat) gebruikersaccount in. Het account dat u opgeeft wordt gebruikt om u aan te melden bij de kiosk.

- **Toepassingstype**: selecteer **Store-app**.

- **App wordt uitgevoerd in de kioskmodus**: kies **Een Store-app toevoegen** en selecteer een app in de lijst.

    Worden er geen apps in de lijst weergegeven? Voeg er een aantal toe met behulp van de stappen in [Client-apps](apps-add.md).

    Selecteer **OK** om uw wijzigingen op te slaan.

- **Kioskbrowserinstellingen**: met deze instellingen beheert u een webbrowser-app in de kiosk. Zorg ervoor dat u de [Kioskbrowser-app](https://businessstore.microsoft.com/store/details/kiosk-browser/9NGB5S5XG2KP) uit de Store ophaalt, deze aan Intune toevoegt als een [client-app](apps-add.md) en vervolgens de app aan de kioskapparaten toewijst.

  Voer de volgende instellingen in:

  - **Standaard-URL voor de startpagina**: voer de standaard-URL die wordt weergegeven als de kioskbrowser wordt geopend of opnieuw wordt gestart. Voer bijvoorbeeld `http://bing.com` of `http://www.contoso.com` in.

  - **De knop Startpagina**: **toon** of **verberg** de knop Startpagina van de kioskbrowser. Standaard wordt de knop niet weergegeven.

  - **Navigatieknoppen**: **toon** of **verberg** de knoppen volgende en vorige. De navigatieknoppen worden standaard niet weergegeven.

  - **Knop sessie beëindigen**: **toon** of **verberg** de knop voor het beëindigen van de sessie. Als deze knop wordt getoond, selecteert de gebruiker de knop en wordt in de app gevraagd om de sessie te beëindigen. Wanneer de actie wordt bevestigd, wist de browser alle browsegegevens (cookies, cache etc.) en wordt de standaard-URL geopend. Standaard wordt de knop niet weergegeven.

  - **De browser vernieuwen na niet-actieve tijd**: voer de niet-actieve tijd (1-1440 minuten) in, waarna de kioskbrowser opnieuw wordt gestart en vernieuwd. Niet-actieve tijd wordt weergegeven als het aantal minuten dat is verstreken sinds de laatste interactie van de gebruiker. De waarde is standaard leeg of blanco, wat inhoudt dat er geen time-out is voor inactiviteit.

  - **Toegestane websites**: gebruik deze instelling om toe te staan dat bepaalde websites worden geopend. Met andere woorden, gebruik deze functie om het aantal websites dat op het apparaat kan worden geopend, te beperken. U kunt bijvoorbeeld toestaan dat alle websites op `http://contoso.com*` kunnen worden geopend. Standaard worden alle websites toegestaan.

    Als u alleen bepaalde websites wilt toestaan, moet u een CSV-bestand uploaden dat een lijst met toegestane websites bevat. Als u geen CSV-bestand toevoegt, zijn alle websites toegestaan. Intune biedt ondersteuning voor * (sterretje) als jokerteken.

  Selecteer **OK** om uw wijzigingen op te slaan.

## <a name="multi-app-kiosks"></a>Kiosken voor meerdere apps

Apps in deze modus zijn beschikbaar in het startmenu. Deze apps zijn de enige apps die de gebruiker kan openen.

Wanneer u een kioskmodus voor meerdere apps kiest, moet u de volgende instellingen opgeven:

- **Gericht op Windows 10 met apparaten in de S-modus**: kies **Ja** om Store-apps en AUMID-apps toe te staan (zodat Win32-apps worden uitgesloten) in het kioskprofiel. Kies **Nee** als u Store-apps, Win32-apps AUMID-apps in het kioskprofiel wilt toestaan. Als u **Nee** kiest, wordt het kioskprofiel niet geïmplementeerd op apparaten in de S-modus.

- **Aanmeldingstype gebruiker**: de apps die u toevoegt worden uitgevoerd als het gebruikersaccount dat u invoert. Uw opties zijn:

  - **Automatisch aanmelden (Windows 10, versie 1803 en hoger)**: voor kiosken in openbare omgevingen waar een gebruiker zich niet hoeft aan te melden, vergelijkbaar met een gastaccount. Deze instelling maakt gebruik van [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp).
  - **Lokaal gebruikersaccount**: **voeg** het lokale (op het apparaat) gebruikersaccount toe. Het account dat u opgeeft wordt gebruikt om u aan te melden bij de kiosk.
  - **Azure AD-gebruiker of -groep (Windows 10, versie 1803 en hoger)**: selecteer **toevoegen** als u Azure AD-gebruikers of -groepen in de lijst wilt kiezen. U kunt meerdere gebruikers en groepen selecteren. Kies **Selecteren** om uw wijzigingen op te slaan.
  - **HoloLens-bezoeker**: het bezoekersaccount is een gastaccount waarvoor geen gebruikersreferenties of verificatie is vereist, zoals wordt beschreven in [Gedeelde pc-modusconcepten](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Toepassingen**: voeg de apps toe die u op het apparaat in kioskmodus wilt uitvoeren. U kunt verschillende apps toevoegen.

  - **Store-app toevoegen**: voeg een app toe uit de Microsoft Store voor Bedrijven. Als er geen apps worden weergegeven, kunt u apps aanschaffen en deze [aan Intune toevoegen](store-apps-windows.md). U kunt bijvoorbeeld Kiosk-Browser, Excel, OneNote en meer toevoegen.

  - **Win32-app toevoegen**: een Win32-app is een traditionele bureaublad-app, zoals Visual Studio Code of Google Chrome. Voer de volgende eigenschappen in:

    - **Toepassingsnaam**: vereist. Geef een naam op voor de toepassing.
    - **Lokaal pad**: vereist. Voer het pad naar het uitvoerbare bestand in, zoals `C:\Program Files (x86)\Microsoft VS Code\Code.exe` of `C:\Program Files (x86)\Google\Chrome\Application\chrome.exe`.
    - **Model-id van toepassingsgebruiker (AUMID)**: optioneel. Voer de AUMID van de Win32-app in. Deze instelling bepaalt de indeling van de tegel na het opstarten op het bureaublad. Zie [De model-id van toepassingsgebruiker van een geïnstalleerde app vinden](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) als u wilt weten hoe u aan deze id komt.
    - **Tegelgrootte**: vereist. Kies een tegelgrootte Klein, Normaal, Breed of Groot voor de app.
  
  - **Toevoegen via AUMID**: gebruik deze optie om Postvak IN-apps voor Windows, zoals Kladblok of Calculator toe te voegen. Voer de volgende eigenschappen in: 

    - **Toepassingsnaam**: vereist. Geef een naam op voor de toepassing.
    - **Model-id van toepassingsgebruiker (AUMID)**: vereist. Voer de AUMID van de Windows-app in. Zie [De model-id van toepassingsgebruiker van een geïnstalleerde app vinden](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) als u wilt weten hoe u aan deze id komt.
    - **Tegelgrootte**: vereist. Kies een tegelgrootte Klein, Normaal, Breed of Groot voor de app.

  > [!TIP]
  > Nadat u alle apps hebt toegevoegd, kunt u de volgorde ervan wijzigen door er op te klikken en de apps naar een andere positie op de lijst te slepen.  

  Selecteer **OK** om uw wijzigingen op te slaan.

- **Kioskbrowserinstellingen**: met deze instellingen beheert u een webbrowser-app in de kiosk. Implementeer met [Client-apps](apps-add.md) een webbrowser-app op de kioskapparaten.

  Voer de volgende instellingen in:

  - **Standaard-URL voor de startpagina**: voer de standaard-URL die wordt weergegeven als de kioskbrowser wordt geopend of opnieuw wordt gestart. Voer bijvoorbeeld `http://bing.com` of `http://www.contoso.com` in.

  - **De knop Startpagina**: **toon** of **verberg** de knop Startpagina van de kioskbrowser. Standaard wordt de knop niet weergegeven.

  - **Navigatieknoppen**: **toon** of **verberg** de knoppen volgende en vorige. De navigatieknoppen worden standaard niet weergegeven.

  - **Knop sessie beëindigen**: **toon** of **verberg** de knop voor het beëindigen van de sessie. Als deze knop wordt getoond, selecteert de gebruiker de knop en wordt in de app gevraagd om de sessie te beëindigen. Wanneer de actie wordt bevestigd, wist de browser alle browsegegevens (cookies, cache etc.) en wordt de standaard-URL geopend. Standaard wordt de knop niet weergegeven.

  - **De browser vernieuwen na niet-actieve tijd**: voer de niet-actieve tijd (1-1440 minuten) in, waarna de kioskbrowser opnieuw wordt gestart en vernieuwd. Niet-actieve tijd wordt weergegeven als het aantal minuten dat is verstreken sinds de laatste interactie van de gebruiker. De waarde is standaard leeg of blanco, wat inhoudt dat er geen time-out is voor inactiviteit.

  - **Toegestane websites**: gebruik deze instelling om toe te staan dat bepaalde websites worden geopend. Met andere woorden, gebruik deze functie om het aantal websites dat op het apparaat kan worden geopend, te beperken. U kunt bijvoorbeeld toestaan dat alle websites op `contoso.com*` kunnen worden geopend. Standaard worden alle websites toegestaan.

    Als u alleen bepaalde websites wilt toestaan, moet u een CSV-bestand uploaden dat een lijst met toegestane websites bevat. Als u geen CSV-bestand toevoegt, zijn alle websites toegestaan.

  Selecteer **OK** om uw wijzigingen op te slaan.

- **Alternatieve lay-out van het menu Start gebruiken**: kies **Ja** om een XML-bestand op te geven, waarin wordt beschreven hoe de apps worden weergegeven in het startmenu, zoals de volgorde van de apps. Gebruik deze optie als u meer aanpassingsmogelijkheden wilt gebruiken in het startmenu. [Customize and export Start layout (Aanpassen en indeling Start exporteren)](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) biedt een aantal richtlijnen en een XML-voorbeeld.

- **Windows-taakbalk**: kies of u wilt dat de taakbalk wordt **weergegeven** of **verborgen**. Standaard wordt de taakbalk niet weergegeven.

## <a name="windows-holographic-for-business"></a>Windows Holographic for Business

Op apparaten met Windows Holographic for Business kunt u configureren dat deze apparaten worden uitgevoerd in de kioskmodus met één app of in de kioskmodus met meerdere apps. Sommige functies worden niet ondersteund in Windows Holographic for Business.

#### <a name="single-full-screen-app-kiosks"></a>Kiosken met één app op een volledig scherm
Wanneer u een kioskmodus voor één app kiest, moet u de volgende instellingen opgeven:

- **Aanmeldingstype gebruiker**: selecteer **Lokaal gebruikersaccount** om het lokale gebruikersaccount (op het apparaat) of een Microsoft-account (MSA) in te voeren, dat is gekoppeld aan de kiosk-app. Gebruikersaccounttypen met het kenmerk **AutoLogon** worden niet ondersteund in Windows Holographic for Business.

- **Toepassingstype**: selecteer **Store-app**.

- **App wordt uitgevoerd in de kioskmodus**: kies **Een Store-app toevoegen** en selecteer een app in de lijst.

    Worden er geen apps in de lijst weergegeven? Voeg er een aantal toe met behulp van de stappen in [Client-apps](apps-add.md).

    Selecteer **OK** om uw wijzigingen op te slaan.

#### <a name="multi-app-kiosks"></a>Kiosken voor meerdere apps
Apps in deze modus zijn beschikbaar in het startmenu. Deze apps zijn de enige apps die de gebruiker kan openen. Wanneer u een kioskmodus voor meerdere apps kiest, moet u de volgende instellingen opgeven:

- **Gericht op Windows 10 S met apparaten in de S-modus**: kies **Nee**. De S-modus wordt niet ondersteund in Windows Holographic for Business.

- **Aanmeldingstype gebruiker**: voeg een of meer gebruikersaccounts toe die de door u toegevoegde apps kunnen gebruiken. Uw opties zijn: 

  - **Automatisch aanmelden**: wordt niet ondersteund in Windows Holographic for Business.
  - **Lokale gebruikersaccounts**: **voeg** het lokale (op het apparaat) gebruikersaccount toe. Het account dat u opgeeft wordt gebruikt om u aan te melden bij de kiosk.
  - **Azure AD-gebruiker of -groep (Windows 10, versie 1803 of hoger)**: een gebruiker moet referenties opgegeven om zich te kunnen aanmelden bij het apparaat. Selecteer **Toevoegen** als u Azure AD-gebruikers of -groepen in de lijst wilt kiezen. U kunt meerdere gebruikers en groepen selecteren. Kies **Selecteren** om uw wijzigingen op te slaan.
  - **HoloLens-bezoeker**: het bezoekersaccount is een gastaccount waarvoor geen gebruikersreferenties of verificatie is vereist, zoals wordt beschreven in [Gedeelde pc-modusconcepten](https://docs.microsoft.com/windows/configuration/set-up-shared-or-guest-pc#shared-pc-mode-concepts).

- **Toepassingen**: voeg de apps toe die u op het apparaat in kioskmodus wilt uitvoeren. U kunt verschillende apps toevoegen.

  - **Store-apps toevoegen**: selecteer een bestaande app die u hebt toegevoegd met [Client-apps](apps-add.md). Als er geen apps worden weergegeven, kunt u apps aanschaffen en deze [aan Intune toevoegen](store-apps-windows.md).
  - **Win32-app toevoegen**: wordt niet ondersteund in Windows Holographic for Business.
  - **Toevoegen via AUMID**: gebruik deze optie om Postvak IN-apps voor Windows toe te voegen. Voer de volgende eigenschappen in: 

    - **Toepassingsnaam**: vereist. Geef een naam op voor de toepassing.
    - **Model-id van toepassingsgebruiker (AUMID)**: vereist. Voer de AUMID van de Windows-app in. Zie [De model-id van toepassingsgebruiker van een geïnstalleerde app vinden](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) als u wilt weten hoe u aan deze id komt.
    - **Tegelgrootte**: vereist. Kies een tegelgrootte Klein, Normaal, Breed of Groot voor de app.

- **Kioskbrowserinstellingen**: wordt niet ondersteund in Windows Holographic for Business.

- **Alternatieve lay-out van het menu Start gebruiken**: kies **Ja** om een XML-bestand op te geven, waarin wordt beschreven hoe de apps worden weergegeven in het startmenu, zoals de volgorde van de apps. Gebruik deze optie als u meer aanpassingsmogelijkheden wilt gebruiken in het startmenu. [Startopmaak aanpassen en exporteren](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-for-hololens) biedt instructies en bevat een specifiek XML-bestand voor apparaten met Windows Holographic for Business.

- **Windows-taakbalk**: wordt niet ondersteund in Windows Holographic for Business.



## <a name="next-steps"></a>Volgende stappen
[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).
