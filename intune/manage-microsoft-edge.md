---
title: Internettoegang beheren met behulp van Microsoft Edge met Microsoft Intune
titleSuffix: ''
description: Hanteer het Intune-beveiligingsbeleid voor apps met Microsoft Edge zodat bedrijfswebsites altijd onder veilige omstandigheden toegankelijk zijn.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 06/05/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3fb2f050-ec94-42ab-be05-c3d4101148bb
ms.reviewer: ilwu
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c1a255391a2cf27a764da6122031fd0c9cbb64cf
ms.sourcegitcommit: cb76efd3db60a422a65478ebce83d3aea7b5eeed
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/06/2019
ms.locfileid: "66751356"
---
# <a name="manage-web-access-using-microsoft-edge-with-microsoft-intune"></a>Internettoegang beheren met behulp van Microsoft Edge met Microsoft Intune

Wanneer u het Intune-beveiligingsbeleid voor apps met Microsoft Edge hanteert, kan dat ervoor zorgen dat bedrijfswebsites altijd onder veilige omstandigheden toegankelijk zijn. Op basis van Intune-beleid zijn de volgende zakelijke functies van Microsoft Edge beschikbaar. Deze zakelijke functies omvatten:

1.  **Dual-Identity**. Gebruikers kunnen zowel een werkaccount als een persoonlijk account maken om mee te browsen. Er is sprake van een volledige scheiding tussen de twee identiteiten. Dit is vergelijkbaar met de architectuur en ervaring in Office 365 en Outlook. Intune-beheerders kunnen het gewenste beleid instellen voor beveiligde browsersessies binnen het werkaccount.
2.  **Integratie van het Intune-beveiligingsbeleid voor apps**: omdat Microsoft Edge is geïntegreerd met de Intune SDK, kunt u door middel van het beveiligingsbeleid voor apps zorgen voor een beveiliging tegen gegevensverlies. Met deze functies kan bijvoorbeeld het gebruik van knippen, kopiëren en plakken worden beheerd, het maken van schermafdrukken worden geblokkeerd en kan ervoor worden gezorgd dat door de gebruiker geselecteerde koppelingen uitsluitend worden geopend in andere beheerde apps.
3.  **Integratie met Azure Active Directory-toepassingsproxy**: u kunt de toegang tot SaaS-app en web-apps beheren en ervoor zorgen dat browser-apps alleen worden uitgevoerd in de beveiligde Microsoft Edge-browser, of eindgebruikers nu verbinding maken vanuit het bedrijfsnetwerk of vanaf internet.
4.  **Toepassingsconfiguratie**: u kunt door middel van de configuratie-instellingen voor toepassingen de beveiligingspositie van uw organisatie versterken en gebruiksvriendelijke functies configureren voor uw eindgebruikers. U kunt onder andere bladwijzers, een snelkoppeling naar de startpagina, toegestane/geblokkeerde websites en de Azure-toepassingsproxy definiëren.
Beveiligingsbeleid van Microsoft Intune voor Microsoft Edge helpt u om de gegevens en resources in uw organisatie te beveiligen. Wanneer u dit beleid toepast met Microsoft Edge, zijn de resources van uw bedrijf beveiligd, niet alleen in systeemeigen geïnstalleerde apps, maar ook bij toegang via een webbrowser.

## <a name="getting-started"></a>Aan de slag

U en uw eindgebruikers kunnen Microsoft Edge in openbare app stores downloaden en deze in uw organisaties gebruiken. Besturingssysteemvereisten voor browserbeleid:
- Android 4 en hoger of
- iOS 8.0 en hoger

## <a name="application-protection-policies-for-microsoft-edge"></a>Beveiligingsbeleid voor apps voor Microsoft Edge

Aangezien Microsoft Edge is geïntegreerd met de Intune SDK, kunt u ook hierop het beveiligingsbeleid voor apps toepassen, zoals:
- beperkingen afdwingen voor het knippen, kopiëren en plakken van gegevens;
- voorkomen dat er schermopnamen worden gemaakt;
- ervoor zorgen dat zakelijke koppelingen alleen kunnen worden geopend in beheerde apps en browsers.

Zie Wat is beveiligingsbeleid voor apps? voor meer informatie.
U kunt deze instellingen toepassen op:
- Apparaten die zijn ingeschreven bij Intune
- Apparaten die zijn ingeschreven bij een ander MDM-product
- Niet-beheerde apparaten

Als Microsoft Edge niet wordt gekoppeld aan Intune-beleid, kunnen gebruikers het niet gebruiken om toegang te krijgen tot gegevens in andere door Intune beheerde toepassingen, zoals Office-apps. 

## <a name="conditional-access-for-microsoft-edge"></a>Voorwaardelijke toegang voor Microsoft Edge

U kunt gebruikmaken van voorwaardelijke toegang van Azure AD om de gebruikers om te leiden, zodat deze uitsluitend toegang hebben tot bedrijfsinhoud via Microsoft Edge. Op die manier wordt mobiele browsertoegang tot met Azure AD verbonden web-apps beperkt tot Microsoft Edge dat met beleid is beveiligd. Hierbij wordt toegang vanuit andere onbeveiligde browsers zoals Safari of Chrome geblokkeerd. Voorwaardelijke toegang kan worden toegepast op Azure-resources, zoals Exchange Online en SharePoint Online, het Microsoft 365 Office-beheercentrum en zelfs on-premises sites die u beschikbaar hebt gemaakt voor externe gebruikers via de [Azure AD-toepassingsproxy](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started).

Als u met Azure AD verbonden web-apps wilt beperken tot gebruik van Microsoft Edge in iOS en Android, voert u de onderstaande stappen uit:
1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer onder het Intune-knooppunt achtereenvolgens **Voorwaardelijke toegang** > **Nieuw beleid**.
3. Selecteer vervolgens **Verlenen** in de sectie **Besturingselementen voor toegang** van de blade.
4. Klik op **Goedgekeurde client-apps vereisen**.
5. Klik op **Selecteren** op de blade **Verlenen**. Dit beleid moet worden toegewezen aan de cloud-apps die u alleen voor de Intune Managed Browser-app toegankelijk wilt maken.

    ![Beleid voor voorwaardelijke toegang - Grant](./media/manage-microsoft-edge/manage-microsoft-edge-01.png)

6. Selecteer Voorwaarden > Client-apps in de sectie Toewijzingen. De blade Client-apps wordt weergegeven.
7. Klik op Ja onder Configureren om het beleid toe te passen op specifieke client-apps.
8. Controleer of Browser is geselecteerd als client-app.

    ![Beleid voor voorwaardelijke toegang - Client-apps selecteren](./media/manage-microsoft-edge/manage-microsoft-edge-02.png)

    > [!NOTE]
    > Als u wilt beperken welke systeemeigen apps (niet-browser-apps) toegang hebben tot deze cloudtoepassingen, kunt u ook **Mobiele apps en bureaublad-clients** selecteren.

9. Selecteer in de sectie **Toewijzingen** de optie **Gebruikers en groepen** en kies vervolgens de gebruikers of groepen die u wilt toewijzen aan dit beleid.

    > [!NOTE]
    > Gebruikers moeten ook onder Intune App Protection-beleid vallen om app-configuratiebeleid te kunnen ontvangen. Zie [Wat is beveiligingsbeleid voor apps?](app-protection-policy.md) voor meer informatie over het maken van Intune-app-beveiligingsbeleid.

10. Selecteer in de sectie **Toewijzingen** de optie **Cloud-apps** om te kiezen welke apps met dit beleid moeten worden beveiligd.

Nadat het bovenstaande beleid is geconfigureerd, worden gebruikers gedwongen om Microsoft Edge te gebruiken voor toegang tot de met Azure AD verbonden web-apps die u met dit beleid hebt beveiligd. Als gebruikers in dit scenario een onbeheerde browser proberen te gebruiken, wordt er een bericht weergegeven waarin wordt vermeld dat Microsoft Edge moet worden gebruikt.

> [!TIP]
> Voorwaardelijke toegang is een technologie van Azure Active Directory (Azure AD). Het knooppunt voor voorwaardelijke toegang dat via Intune wordt geopend, is hetzelfde als het knooppunt dat u opent via Azure AD.

## <a name="single-sign-on-to-azure-ad-connected-web-apps-in-policy-protected-browsers"></a>Eenmalige aanmelding voor met Azure AD verbonden web-apps in met beleid beveiligde browsers

In Microsoft Edge in iOS en Android kan eenmalige aanmelding worden gebruikt voor alle web-apps (SaaS en on-premises) die met Azure AD zijn verbonden. Met eenmalige aanmelding kunnen gebruikers toegang krijgen tot met Azure AD verbonden web-apps via Microsoft Edge zonder dat ze hun referenties opnieuw hoeven op te geven.

Voor eenmalige aanmelding moet uw apparaat zijn geregistreerd door de Microsoft Authenticator-app voor iOS-apparaten of de Intune-bedrijfsportal voor Android. Wanneer gebruikers over de Authenticator-app of Intune-bedrijfsportal beschikken, wordt hen gevraagd om hun apparaat te registreren wanneer ze naar een met Azure AD verbonden web-app in een met beleid beveiligde browser navigeren, als hun apparaat nog niet is geregistreerd door een andere toepassing. Nadat het apparaat is geregistreerd met het gebruikersaccount dat wordt beheerd door Intune, wordt dat account voor eenmalige aanmelding ingeschakeld voor met Azure AD verbonden web-apps.

> [!NOTE]
> Apparaatregistratie is eenvoudig inchecken met de Azure AD-service. Dit vereist geen volledige apparaatinschrijving en geeft IT geen extra bevoegdheden op het apparaat.

## <a name="create-a-protected-browser-app-configuration"></a>Een configuratie voor de beveiligde browser-app maken

App-configuraties kunnen pas worden toegepast als de beveiligde browser van de gebruiker of een andere app op het apparaat al wordt beheerd door [het Intune-beveiligingsbeleid voor apps](app-protection-policy.md).

U voert de volgende stappen uit om een app-configuratie voor een beveiligde browser te maken:

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **Client-apps** > **App-configuratiebeleid** > **Toevoegen**.
3. Geef op de blade **Configuratiebeleid toevoegen** een **naam** en een optionele **beschrijving** op voor de app-configuratie-instellingen.
4. Kies voor **Type apparaatregistratie** **Beheerde apps**.
5. Kies **Vereiste app selecteren** en kies vervolgens op de blade **Doel-apps** **Managed Browser** en/of **Microsoft Edge** voor iOS, voor Android of voor beide besturingssystemen.
6. Kies **OK** om terug te keren naar de blade **Configuratiebeleid toevoegen**.
7. Kies **Configuratie-instellingen**. Definieer op de blade **Configuratie** sleutel- en waardeparen om configuraties op te geven voor Microsoft Edge. Gebruik de secties verderop in dit artikel voor meer informatie over de verschillende sleutel- en waardeparen die u kunt definiëren.

    > [!NOTE]
    > Voor Microsoft Edge wordt hetzelfde sleutel- en waardepaar gebruikt als voor Managed Browser. 

8.  Wanneer u klaar bent, klikt u op **OK**.
9.  Kies op de blade **Configuratiebeleid toevoegen** de optie **Toevoegen**.<br>
    De nieuwe configuratie wordt gemaakt en weergegeven op de blade **App-configuratie**.

## <a name="assign-the-configuration-settings-you-created"></a>De configuratie-instellingen toewijzen die u hebt gemaakt 

U wijst de instellingen aan Azure AD-groepen gebruikers toe. Als deze gebruiker de beveiligde browser-app heeft geïnstalleerd waarop het beleid is gericht, wordt de app beheerd door de instellingen die u hebt opgegeven.

1. Kies op de blade **Client-apps** van het Intune MAM-dashboard de optie **App-configuratiebeleid**.
2. Selecteer in de lijst met app-configuraties de configuratie die u wilt toewijzen.
3. Kies **Toewijzingen** op de volgende blade.
4. Selecteer op de blade **Toewijzingen** de Azure AD-groep waaraan u de app-configuratie wilt toewijzen en kies vervolgens **OK**.

## <a name="how-to-configure-application-proxy-settings-for-protected-browsers"></a>Application Proxy-instellingen configureren voor beveiligde browsers

Microsoft Edge en de [Azure AD-toepassingsproxy](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) kunnen samen worden gebruikt om gebruikers toegang te verlenen tot intranetsites op hun mobiele apparaten. 

Hier volgen enkele voorbeelden van de scenario's waarin de AD-toepassingsproxy wordt ingeschakeld: 

- Een gebruiker maakt gebruik van de mobiele app van Outlook, die wordt beveiligd door Intune. De gebruiker klikt vervolgens op een koppeling naar een intranetsite in een e-mailbericht en Microsoft Edge herkent dat deze intranetsite beschikbaar is gesteld voor de gebruiker via de toepassingsproxy. De gebruiker wordt automatisch omgeleid via de toepassingsproxy om zich bij de betreffende meervoudige verificatie en voorwaardelijke toegang te verifiëren voordat de intranetsite wordt bereikt. Gebruikers hebben nu zelfs op hun mobiele apparaten toegang tot interne sites en de koppeling in Outlook werkt naar behoren.
- Een gebruiker opent Microsoft Edge op het iOS- of Android-apparaat. Als Microsoft Edge wordt beveiligd met Intune en de toepassingsproxy is ingeschakeld, kan de gebruiker naar een intranetsite navigeren met de gebruikelijke interne URL. Microsoft Edge herkent dat deze intranetsite voor de gebruiker beschikbaar is gesteld via de toepassingsproxy en de gebruiker wordt automatisch omgeleid via de toepassingsproxy om zich te verifiëren voordat de intranetsite wordt geopend. 

### <a name="before-you-start"></a>Voordat u begint

- Stel de interne toepassingen in via de toepassingsproxy van Azure AD.
    - Raadpleeg [deze documentatie](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy) voor het configureren van de toepassingsproxy en het publiceren van toepassingen.
- Aan de Microsoft Edge-app moet een [Intune-beveiligingsbeleid](app-protection-policy.md) zijn toegewezen.

> [!NOTE]
> Het kan tot 24 uur duren voordat bijgewerkte omleidingsgegevens voor de toepassingsproxy worden doorgevoerd in Managed Browser en Microsoft Edge.

#### <a name="step-1-enable-automatic-redirection-to-a-protected-browser-from-outlook"></a>Stap 1: schakel automatische omleiding naar een beveiligde browser vanuit Outlook in
Outlook moet zijn geconfigureerd met een beveiligingsbeleid voor apps waarmee de instelling **Webinhoud delen met door beleid beheerde browsers** wordt ingeschakeld.

![Beveiligingsbeleid voor apps - Webinhoud delen met door beleid beheerde browsers](./media/manage-microsoft-edge/manage-microsoft-edge-03.png)

#### <a name="step-2-set-the-app-configuration-setting-to-enable-app-proxy"></a>Stap 2: Stel de app-configuratie-instelling in voor het inschakelen van de toepassingsproxy
Wijs aan Microsoft Edge het onderstaande sleutel-waardepaar toe om de toepassingsproxy voor Microsoft Edge in te schakelen:

|    Sleutel    |    Waarde    |
|-------------------------------------------------------------------|-------------|
|    com.microsoft.intune.mam.managedbrowser.AppProxyRedirection    |    waar    |

Voor meer informatie over het gecombineerde gebruik van Microsoft Edge en de Azure AD-toepassingsproxy voor naadloze (en beveiligde) toegang tot on-premises web-apps, raadpleegt u de blogpost voor Enterprise Mobility + Security [Better together: Intune and Azure Active Directory team up to improve user access](https://cloudblogs.microsoft.com/enterprisemobility/2017/07/06/better-together-intune-and-azure-active-directory-team-up-to-improve-user-access). (Beter samen: Intune en Azure Active Directory werken samen om de toegang voor gebruikers te verbeteren.) Deze blogpost verwijst naar de Intune Managed Browser, maar de inhoud is ook van toepassing op Microsoft Edge.

## <a name="how-to-configure-a-homepage-shortcut-for-microsoft-edge"></a>Een snelkoppeling naar de startpagina voor Microsoft Edge configureren

Met deze instelling kunt u een snelkoppeling naar de startpagina voor Microsoft Edge configureren.  De snelkoppeling naar de startpagina die u configureert, wordt als eerste pictogram onder de zoekbalk weergegeven, wanneer de gebruiker een nieuw tabblad in Microsoft Edge opent. De gebruiker kan deze snelkoppeling niet bewerken of verwijderen in hun beheerde context. De snelkoppeling naar de startpagina geeft de naam van uw organisatie weer om deze te onderscheiden. 

Gebruik het onderstaande sleutel-waardepaar om een snelkoppeling naar de startpagina te configureren:

|    Sleutel    |    Waarde    |
|-------------------------------------------------------------------|-------------|
|    com.microsoft.intune.mam.managedbrowser.homepage   |    Geef een geldige URL op. Uit veiligheidsoogpunt worden onjuiste URL's geblokkeerd.<br>**Voorbeeld:** `<https://www.bing.com`>
    |

## <a name="how-to-configure-managed-bookmarks-for-microsoft-edge"></a>Beheerde bladwijzers configureren voor Microsoft Edge

Voor een betere toegankelijkheid kunt u bladwijzers configureren die u beschikbaar wilt stellen voor de gebruikers wanneer ze Microsoft Edge gebruiken. Hier volgt enige informatie:

- Deze bladwijzers worden alleen weergegeven voor gebruikers wanneer ze de bedrijfsmodus van Microsoft Edge gebruiken. 
- Deze bladwijzers kunnen niet door de gebruikers worden verwijderd of gewijzigd.
- Deze bladwijzers worden bovenaan de lijst weergegeven. Bladwijzers die gebruikers maken, worden onder deze bladwijzers weergegeven.
- Als u App Proxy-omleiding hebt ingeschakeld, kunt u App Proxy-webapps toevoegen met behulp van hun interne of externe URL.

Gebruik het volgende sleutel-waardepaar om beheerde bladwijzers te configureren:

|    Sleutel    |    Waarde    |
|---------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    com.microsoft.intune.mam.managedbrowser.bookmarks    |    De waarde voor deze configuratie is een lijst met bladwijzers. Elke bladwijzer bestaat uit de titel en de URL van de bladwijzer. Scheid de titel en de URL met het teken `|`.      **Voorbeeld:**<br>`Microsoft Bing|https://www.bing.com`<p>Als u meerdere bladwijzers wilt configureren, typt u een dubbel scheidingsteken `||` tussen de bladwijzers.<p>**Voorbeeld:**<br>`Microsoft Bing|https://www.bing.com||Contoso|https://www.contoso.com`    |

## <a name="how-to-display-myapps-within-microsoft-edge-bookmarks"></a>MyApps weergeven in Microsoft Edge-bladwijzers

Standaard worden voor gebruikers de MyApps-sites weergegeven die voor hen zijn geconfigureerd in een map in Microsoft Edge-bladwijzers. De map krijgt een label met de naam van uw organisatie.

|    Sleutel    |    Waarde    |
|------------------------------------------------------|----------------------------------------------------------------------------------------------------------------|
|    com.microsoft.intune.mam.managedbrowser.MyApps    |    Bij **Waar** wordt MyApps weergegeven in de Microsoft Edge-bladwijzers.<p>Bij **Onwaar** wordt MyApps verborgen in Microsoft Edge.    |

## <a name="how-to-specify-allowed-or-blocked-sites-list-for-microsoft-edge"></a>De lijst met toegestane of geblokkeerde sites voor Microsoft Edge opgeven
U kunt app-configuratie gebruiken om te bepalen tot welke sites gebruikers toegang kunnen krijgen met hun werkprofiel. Als u een lijst met toegestane sites gebruikt, hebben de gebruikers alleen toegang tot de sites die u expliciet hebt vermeld. Als u een lijst met geblokkeerde sites gebruikt, hebben de gebruikers toegang tot alle sites, met uitzondering van de sites die u expliciet hebt geblokkeerd. U moet alleen een lijst met toegestane sites of een lijst met geblokkeerde sites gebruiken, niet beide. Als beide worden gebruikt op het apparaat, wordt alleen de lijst met toegestane sites nageleefd.  

U kunt de onderstaande sleutel-waardeparen gebruiken om een lijst met toegestane sites of een lijst met geblokkeerde sites te configureren voor Microsoft Edge. Hieronder vindt u meer informatie over geldige URL-indelingen. 

|    Sleutel    |    Waarde    |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    U kunt kiezen uit:<p>1. Geef toegestane URL's op (alleen deze URL's zijn toegestaan; andere sites zijn niet toegankelijk):<br>`com.microsoft.intune.mam.managedbrowser.AllowListURLs`<p>2. Geef geblokkeerde URL's op (alle andere sites zijn toegankelijk):<br>`com.microsoft.intune.mam.managedbrowser.BlockListURLs`    |    De overeenkomstige waarde voor de sleutel is een lijst met URL's. U geeft alle URL's die u wilt toestaan of blokkeren op als één waarde, gescheiden door een sluisteken `|`.<p>**Voorbeelden:**<br>`URL1|URL2|URL3`<br>`http://.contoso.com/|https://.bing.com/|https://expenses.contoso.com`  |

### <a name="url-formats-for-allowed-and-blocked-site-list"></a>URL-indelingen voor een lijst met toegestane sites en een lijst met geblokkeerde sites 
U kunt verschillende URL-indelingen gebruiken om uw lijsten met toegestane/geblokkeerde sites te maken. De toegestane patronen worden in de onderstaande tabel beschreven. Enkele opmerkingen voordat u aan de slag gaat: 
- Zorg ervoor dat u alle URL's voorziet van het voorvoegsel **http** of **https** wanneer u ze in de lijst invoert.
- U kunt het jokerteken (*) gebruiken volgens de regels in de volgende lijst met toegestane patronen.
- U kunt poortnummers in het adres opgeven. Als u geen poortnummer opgeeft, worden deze waarden gebruikt:
    - Poort 80 voor http
    - Poort 443 voor https
- Het gebruik van jokertekens voor het poortnummer wordt **niet** ondersteund. `http://www.contoso.com:*` en `http://www.contoso.com:*/` bijvoorbeeld worden niet ondersteund.

    |    URL    |    Details    |    Komt overeen met    |    Komt niet overeen met    |
    |-------------------------------------------|--------------------------------------------------------|-------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|
    |    `http://www.contoso.com`    |    Komt overeen met één pagina    |    `www.contoso.com`    |    `host.contoso.com`<br>`www.contoso.com/images`<br>`contoso.com/`    |
    |    `http://contoso.com`    |    Komt overeen met één pagina    |    `contoso.com/`    |    `host.contoso.com`<br>`www.contoso.com/images`<br>`www.contoso.com`    |
    |    `http://www.contoso.com/&#42;`   |    Komt overeen met alle URL's die beginnen met `www.contoso.com`    |    `www.contoso.com`<br>`www.contoso.com/images`<br>`www.contoso.com/videos/tvshows`    |    `host.contoso.com`<br>`host.contoso.com/images`    |
    |    `http://*.contoso.com/*`    |    Komt overeen met alle subdomeinen onder `contoso.com`    |    `developer.contoso.com/resources`<br>`news.contoso.com/images`<br>`news.contoso.com/videos`    |    `contoso.host.com`    |
    |    `http://www.contoso.com/images`    |    Komt overeen met een afzonderlijke map    |    `www.contoso.com/images`    |    `www.contoso.com/images/dogs`    |
    |    `http://www.contoso.com:80`    |    Komt overeen met één pagina, met gebruik van een poortnummer    |    http://www.contoso.com:80    |         |
    |    `https://www.contoso.com`    |    Komt overeen met een enkele, beveiligde pagina    |    `https://www.contoso.com`    |    `http://www.contoso.com`    |
    |    `http://www.contoso.com/images/*`    |    Komt overeen met een enkele map en alle submappen    |    `www.contoso.com/images/dogs`<br>`www.contoso.com/images/cats`    |    `www.contoso.com/videos`    |
  
- Hier volgen enkele voorbeelden van een aantal invoerwaarden die u niet kunt opgeven:
    - `*.com`
    - `*.contoso/*`
    - `www.contoso.com/*images`
    - `www.contoso.com/*images*pigs`
    - `www.contoso.com/page*`
    - IP-adressen
    - `https://*`
    - `http://*`
    - `http://www.contoso.com:*`
    - `http://www.contoso.com: /*`
  
## <a name="defining-behavior-when-users-try-to-access-a-blocked-site"></a>Gedrag definiëren wanneer gebruikers toegang proberen te krijgen tot een geblokkeerde site

Met het model voor dubbele identiteit dat is ingebouwd in Microsoft Edge kunt u de eindgebruikers meer flexibiliteit bieden die niet mogelijk was met de Intune Managed Browser. Wanneer gebruikers op een geblokkeerde site in Microsoft Edge stuiten, kan hen worden gevraagd om de koppeling in hun persoonlijke context te openen in plaats van in hun werkcontext, zodat ze beveiligd blijven en de veiligheid van de bedrijfsresources gewaarborgd blijft. Als er bijvoorbeeld via Outlook een koppeling naar een nieuwsbericht wordt verzonden naar een gebruiker, kan deze de koppeling openen in de persoonlijke context of op een InPrivate-tabblad in plaats van de werkcontext die geen nieuwssites toestaat. Deze overgangen zijn standaard toegestaan.

Gebruik het onderstaande sleutel-waardepaar om te configureren als deze zachte overgangen zijn toegestaan:

|    Sleutel    |    Waarde    |
|----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `com.microsoft.intune.mam.managedbrowser.AllowTransitionOnBlock`    |    Bij **Waar** kunnen door Microsoft Edge gebruikers worden overgezet naar hun persoonlijke context om geblokkeerde sites te openen<p>Bij **Blokkeren** wordt voorkomen dat Microsoft Edge gebruikers overzet. Er wordt voor de gebruikers een bericht weergegeven waarin wordt vermeld dat de site die ze proberen te openen, geblokkeerd is.    |

## <a name="directing-users-to-microsoft-edge-instead-of-the-intune-managed-browser"></a>Gebruikers doorsturen naar Microsoft Edge in plaats van de Intune Managed Browser 

Zowel de Intune Managed Browser als Microsoft Edge kunnen nu worden gebruikt als door beleid beveiligde browsers. Geef de volgende configuratie-instelling op voor alle door Intune beheerde apps (bijvoorbeeld Outlook en OneDrive), zodat de gebruikers worden doorgestuurd naar de juiste browser-app:

|    Sleutel    |    Waarde    |
|------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `com.microsoft.intune.useEdge`    |    Bij `true` wordt ervoor gezorgd dat de gebruikers Microsoft Edge gebruiken.<p>Bij `false` wordt ervoor gezorgd dat de gebruikers de Intune Managed Browser gebruiken.    |

Als deze app-configuratiewaarde niet wordt ingesteld, bepaalt de volgende logica welke browser wordt gebruikt om bedrijfskoppelingen te openen.

Op Android:
- De Intune Managed Browser wordt gestart als een gebruiker zowel de Intune Managed Browser als Microsoft Edge op het apparaat heeft geïnstalleerd. 
- Als alleen Microsoft Edge op het apparaat is geïnstalleerd en hieraan een Intune-beleid is gekoppeld, wordt Microsoft Edge geopend.
- Als alleen Managed Browser op het apparaat is geïnstalleerd en hieraan een Intune-beleid is gekoppeld, wordt Managed Browser geopend.

Op iOS, voor apps waarvoor de Intune SDK is geïntegreerd voor iOS v. 9.0.9+ :
- De Intune Managed Browser wordt gestart als zowel de Managed Browser als Microsoft Edge op het apparaat zijn geïnstalleerd.  
- Als alleen Microsoft Edge op het apparaat is geïnstalleerd en hieraan een Intune-beleid is gekoppeld, wordt Microsoft Edge gestart.
- Als alleen de Managed Browser op het apparaat is geïnstalleerd en hieraan een Intune-beleid is gekoppeld, wordt de Managed Browser gestart.

## <a name="using-microsoft-edge-on-ios-to-access-managed-app-logs"></a>Met Microsoft Edge in iOS logboeken voor beheerde apps openen 

Eindgebruikers die Microsoft Edge op hun iOS-apparaat hebben geïnstalleerd, kunnen de beheerstatus van alle gepubliceerde Microsoft-apps bekijken. Ze kunnen logboeken versturen om problemen met hun beheerde iOS-apps op te lossen.
1. Open Microsoft Edge op uw iOS-apparaat.
2. Type `about:intunehelp` in het adresvak. 
3. De modus voor probleemoplossing wordt gestart vanuit Microsoft Edge.

Zie [Logboeken voor app-beveiliging in Managed Browser controleren](app-protection-policy-settings-log.md) voor een lijst met instellingen die worden opgeslagen in app-logboeken.

Lees [Send logs to your IT admin by email](https://docs.microsoft.com/intune-user-help/send-logs-to-your-it-admin-by-email-android) (Logboeken naar uw IT-beheerder verzenden via e-mail) om te zien hoe u logboeken op Android-apparaten kunt bekijken. 

## <a name="security-and-privacy-for-microsoft-edge"></a>Beveiliging en privacy voor Microsoft Edge

Overwegingen voor aanvullende beveiliging en privacy voor Microsoft Edge:

- Microsoft Edge maakt geen gebruik van de instellingen die gebruikers instellen voor de systeemeigen browser op hun apparaten, omdat Microsoft Edge geen toegang heeft tot deze instellingen.
- Als u de optie **Eenvoudige pincode vereist voor toegang** of **Bedrijfsreferenties vereist voor toegang** configureert in een beveiligingsbeleid voor apps dat is gekoppeld aan Microsoft Edge, en een gebruiker de Help-koppeling op de verificatiepagina selecteert, kan de gebruiker elke internetsite bezoeken, ongeacht of deze is toegevoegd aan de lijst met geblokkeerde websites in het beleid.
- Microsoft Edge kan alleen toegang tot sites blokkeren wanneer de sites rechtstreeks worden geopend. De app kan niet de toegang blokkeren als er tussenliggende services (zoals een vertaalservice) worden gebruikt voor toegang tot de site.
- Om verificatie en toegang tot de Intune-documentatie toe te staan, wordt * **.microsoft.com** uitgesloten van opname in lijsten met toegestane en geblokkeerde sites. Dit domein is altijd toegestaan.
Gebruiksgegevens uitschakelen Microsoft verzamelt automatisch anonieme gegevens over de prestaties en het gebruik van de Managed Browser om Microsoft-producten en -services te verbeteren. Gebruikers kunnen het verzamelen van deze gegevens uitschakelen met de instelling **Gebruiksgegevens** op hun apparaten. U hebt geen controle over het verzamelen van deze gegevens. Op iOS-apparaten kunnen gebruikers geen websites openen met een verlopen of niet-vertrouwd certificaat.

## <a name="next-steps"></a>Volgende stappen

- [Wat zijn beleidsregels voor de beveiliging van apps?](app-protection-policy.md) 
