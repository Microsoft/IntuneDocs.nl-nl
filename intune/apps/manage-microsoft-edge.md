---
title: Microsoft Edge voor iOS en Android beheren met Intune
titleSuffix: ''
description: Hanteer het Intune-beveiligingsbeleid voor apps met Microsoft Edge zodat bedrijfswebsites altijd onder veilige omstandigheden toegankelijk zijn.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3fb2f050-ec94-42ab-be05-c3d4101148bb
ms.reviewer: ilwu
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3ae5a7508f27dbf15a58ba3386e744bb63bf102b
ms.sourcegitcommit: e1ff157f692983b49bdd6e20cc9d0f93c3b3733c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/11/2020
ms.locfileid: "77125010"
---
# <a name="manage-web-access-by-using-microsoft-edge-with-microsoft-intune"></a>Internettoegang beheren met behulp van Microsoft Edge met Microsoft Intune

Wanneer u het Intune-beveiligingsbeleid voor apps met Microsoft Edge hanteert, helpt dat ervoor te zorgen dat bedrijfswebsites altijd onder veilige omstandigheden toegankelijk zijn. Op basis van Intune-beleid zijn de volgende zakelijke functies van Microsoft Edge beschikbaar:

- **Dual-Identity.** Gebruikers kunnen een werkaccount en een persoonlijk account maken om mee te browsen. Er is sprake van een volledige scheiding tussen de twee identiteiten. Dit is vergelijkbaar met de architectuur en ervaring in Office 365 en Outlook. Intune-beheerders kunnen het gewenste beleid instellen voor beveiligde browsersessies binnen het werkaccount.
- **App-beveiligingsbeleid van Intune integreren.** Aangezien Microsoft Edge is geïntegreerd met de Intune SDK kunt u app-beveiligingsbeleid gericht toepassen om bescherming te bieden tegen gegevensverlies. Met deze functies kan bijvoorbeeld het gebruik van knippen, kopiëren en plakken worden beheerd, en het maken van schermafdrukken worden geblokkeerd. Ook kan ervoor worden gezorgd dat door de gebruiker geselecteerde koppelingen uitsluitend worden geopend in andere beheerde apps.
- **Proxy-integratie met Azure-toepassingen.** U kunt de toegang tot SaaS-apps (software als een dienst) en -web-apps beheren. Hiermee zorgt u ervoor dat browser-apps alleen worden uitgevoerd in de beveiligde Microsoft Edge-browser, of eindgebruikers nu verbinding maken vanuit het bedrijfsnetwerk of vanaf internet.
- **Toepassingsconfiguratie.** U kunt door middel van de configuratie-instellingen voor toepassingen de beveiligingspositie van uw organisatie versterken en gebruiksvriendelijke functies configureren voor uw eindgebruikers. Zo kunt u bladwijzers, een snelkoppeling naar de startpagina, toegestane of geblokkeerde sites en een Azure Active Directory-toepassingsproxy (Azure AD) definiëren.

Beveiligingsbeleid van Microsoft Intune voor Microsoft Edge helpt u om de gegevens en resources in uw organisatie te beveiligen. Wanneer u dit beleid toepast met Microsoft Edge, zijn de resources van uw bedrijf beveiligd, niet alleen in systeemeigen geïnstalleerde apps, maar ook bij toegang via een webbrowser.

## <a name="getting-started"></a>Aan de slag

U en uw eindgebruikers kunnen Microsoft Edge in openbare app stores downloaden en deze in uw organisaties gebruiken. Voor browserbeleid gelden de volgende besturingssysteemvereisten:
- Android 4 en hoger
- iOS 8.0 en hoger

## <a name="application-protection-policies-for-microsoft-edge"></a>Beveiligingsbeleid voor apps voor Microsoft Edge

Aangezien Microsoft Edge is geïntegreerd met de Intune SDK, kunt u ook hierop het beveiligingsbeleid voor apps toepassen.

U kunt deze instellingen toepassen op:
- Apparaten die zijn ingeschreven bij Intune.
- Apparaten die zijn ingeschreven bij een ander Mobile Device Management-product.
- Niet-beheerde apparaten.

Als Microsoft Edge niet wordt gekoppeld aan Intune-beleid, kunnen gebruikers het niet gebruiken om toegang te krijgen tot gegevens in andere door Intune beheerde toepassingen, zoals Office-apps. 

## <a name="conditional-access-for-microsoft-edge"></a>Voorwaardelijke toegang voor Microsoft Edge

U kunt gebruikmaken van voorwaardelijke toegang van Azure AD om de gebruikers om te leiden, zodat deze uitsluitend toegang hebben tot bedrijfsinhoud via Microsoft Edge. Dit beperkt de toegang in mobiele browsers tot web-apps die via Azure AD zijn verbonden met Microsoft Edge dat met beleid is beveiligd. De toegang vanuit andere onbeschermde browsers, bijvoorbeeld Safari of Chrome, is geblokkeerd. U kunt voorwaardelijke toegang toepassen op Azure-resources, zoals Exchange Online en SharePoint Online, het Microsoft 365-beheercentrum en zelfs on-premises sites die u aan externe gebruikers beschikbaar hebt gesteld via de [Azure AD-toepassingsproxy](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started).

Ga als volgt te werk als u met Azure AD verbonden web-apps wilt beperken tot gebruik van Microsoft Edge in iOS en Android:
1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer onder het Intune-knooppunt achtereenvolgens **Voorwaardelijke toegang** > **Nieuw beleid**.
3. Selecteer **Verlenen** in het gedeelte **Besturingselementen voor toegang** van het deelvenster.
4. Selecteer **Goedgekeurde client-app vereisen**.
5. Kies **Selecteren** in het deelvenster **Verlenen**. Dit beleid moet worden toegewezen aan de cloud-apps die u alleen voor de Intune Managed Browser-app toegankelijk wilt maken.

    ![Schermopname van beleid voor voorwaardelijke toegang - Toekennen](./media/manage-microsoft-edge/manage-microsoft-edge-01.png)

6. Selecteer in het gedeelte Toewijzingen **Voorwaarden** > **Apps**. Het deelvenster **Apps** wordt weergegeven.
7. Selecteer **Ja** onder **Configureren** om het beleid voor specifieke client-apps toe te passen.
8. Controleer of **Browser** is geselecteerd als client-app.

    ![Schermopname van beleid voor voorwaardelijke toegang - Client-apps selecteren](./media/manage-microsoft-edge/manage-microsoft-edge-02.png)

    > [!NOTE]
    > Als u wilt beperken welke systeemeigen apps (niet-browser-apps) toegang hebben tot deze cloudtoepassingen, kunt u ook **Mobiele apps en bureaublad-clients** selecteren.

9. Selecteer in het gedeelte **Toewijzingen** de optie **Gebruikers en groepen** en kies vervolgens de gebruikers of groepen die u wilt toewijzen aan dit beleid.

10. Selecteer in de sectie **Toewijzingen** de optie **Cloud-apps** om te kiezen welke apps met dit beleid moeten worden beveiligd.

Nadat het bovenstaande beleid is geconfigureerd, worden gebruikers gedwongen om Microsoft Edge te gebruiken voor toegang tot de met Azure AD verbonden web-apps die u met dit beleid hebt beveiligd. Als gebruikers in dit scenario een onbeheerde browser proberen te gebruiken, ontvangen zij een bericht waarin wordt vermeld dat Microsoft Edge moet worden gebruikt.

> [!TIP]
> Voorwaardelijke toegang is een technologie van Azure AD. Het knooppunt voor voorwaardelijke toegang dat via Intune wordt geopend, is hetzelfde als het knooppunt dat u opent via Azure AD.

## <a name="single-sign-on-to-azure-ad-connected-web-apps-in-policy-protected-browsers"></a>Eenmalige aanmelding voor met Azure AD verbonden web-apps in met beleid beveiligde browsers

In Microsoft Edge in iOS en Android kan eenmalige aanmelding (SSO) worden gebruikt voor alle web-apps (SaaS en on-premises) die met Azure AD zijn verbonden. Met eenmalige aanmelding kunnen gebruikers toegang krijgen tot met Azure AD verbonden web-apps via Microsoft Edge, zonder dat ze hun referenties opnieuw hoeven op te geven.

Voor eenmalige aanmelding moet uw apparaat zijn geregistreerd door de Microsoft Authenticator-app voor iOS-apparaten of de Intune-bedrijfsportal voor Android. Als gebruikers over een van beide beschikken, wordt hen gevraagd hun apparaat te registreren wanneer ze naar een met Azure AD verbonden web-app in een met beleid beschermde browser gaan. (Dit geldt alleen als hun apparaat niet al is geregistreerd.) Nadat het apparaat is geregistreerd met het gebruikersaccount dat wordt beheerd door Intune, wordt dat account voor SSO ingeschakeld voor met Azure AD verbonden web-apps.

> [!NOTE]
> Apparaatregistratie is eenvoudig inchecken met de Azure AD-service. Dit vereist geen volledige apparaatinschrijving en geeft IT geen extra bevoegdheden op het apparaat.

## <a name="create-a-protected-browser-app-configuration"></a>Een configuratie voor de beveiligde browser-app maken

Ga als volgt te werk als u een appconfiguratie wilt maken voor Microsoft Edge:

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apps** > **App-configuratiebeleid** > **Toevoegen**.
3. Geef in het deelvenster **Configuratiebeleid toevoegen** een **naam** en een optionele **beschrijving** op voor de app-configuratie-instellingen.
4. Kies voor **Type apparaatregistratie** **Beheerde apps**.
5. Kies **De vereiste app selecteren**. Kies vervolgens in het deelvenster **Doel-apps** **Managed Browser** of **Edge** voor iOS, voor Android of voor beide.
6. Selecteer **OK** om terug te keren naar het deelvenster **Configuratiebeleid toevoegen**.
7. Selecteer **Configuratie-instellingen**. Definieer in het deelvenster **Configuratie** sleutel- en waardeparen om configuraties op te geven voor Microsoft Edge. Gebruik de secties verderop in dit artikel voor meer informatie over de verschillende sleutel- en waardeparen die u kunt definiëren.

    > [!NOTE]
    > Voor Microsoft Edge wordt hetzelfde sleutel- en waardepaar gebruikt als voor Managed Browser. Microsoft Edge moet worden geconfigureerd met een beveiligingsbeleid voor apps om het beleid voor app-configuratie in Android van kracht te laten worden.

8. Selecteer **OK** wanneer u klaar bent.
9. Kies in het deelvenster **Configuratiebeleid toevoegen** de optie **Toevoegen**.<br>
    De nieuwe configuratie wordt gemaakt en weergegeven in het deelvenster **App-configuratie**.

## <a name="assign-the-configuration-settings-you-created"></a>De configuratie-instellingen toewijzen die u hebt gemaakt 

U wijst de instellingen aan groepen gebruikers in Azure AD toe. Als deze gebruiker de beveiligde browser-app heeft geïnstalleerd waarop het beleid is gericht, wordt de app beheerd door de instellingen die u hebt opgegeven.

1. Selecteer in het deelvenster **Apps** van het Intune MAM-dashboard de optie **App-configuratiebeleid**.
2. Selecteer in de lijst met app-configuraties de configuratie die u wilt toewijzen.
3. Selecteer **Toewijzingen** in het volgende deelvenster.
4. Selecteer in het deelvenster **Toewijzingen** de Azure AD-groep waaraan u de app-configuratie wilt toewijzen en selecteer vervolgens **OK**.

## <a name="direct-users-to-microsoft-edge-instead-of-the-intune-managed-browser"></a>Gebruikers doorsturen naar Microsoft Edge in plaats van de Intune Managed Browser 

Zowel de Intune Managed Browser als Microsoft Edge kunnen worden gebruikt als door beleid beveiligde browsers. Geef de volgende configuratie-instelling op voor alle door Intune beheerde apps (bijvoorbeeld Outlook, OneDrive en SharePoint), zodat gebruikers worden doorgestuurd naar de juiste browser-app:

|    Sleutel    |    Waarde    |
|------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `com.microsoft.intune.useEdge`    |    De waarde `true` zal uw gebruikers instructies geven om Microsoft Edge te downloaden en gebruiken.<br>De waarde `false` stelt uw gebruikers in staat de Intune Managed Browser te gebruiken.    |

Als deze app-configuratiewaarde **niet** wordt ingesteld, bepaalt de volgende logica welke browser wordt gebruikt om bedrijfskoppelingen te openen.

Op Android:
- De Intune Managed Browser wordt geopend als een gebruiker zowel de Intune Managed Browser als Microsoft Edge op het apparaat heeft geïnstalleerd. 
- Als alleen Microsoft Edge op het apparaat is geïnstalleerd en hieraan een Intune-beleid is gekoppeld, wordt Microsoft Edge geopend.
- Als alleen de Managed Browser op het apparaat is geïnstalleerd en hieraan een Intune-beleid is gekoppeld, wordt de Managed Browser geopend.

Op iOS, voor apps waarvoor de Intune SDK is geïntegreerd voor iOS v. 9.0.9+ :
- De Intune Managed Browser wordt geopend als zowel de Managed Browser als Microsoft Edge op het apparaat zijn geïnstalleerd.  
- Als alleen Microsoft Edge op het apparaat is geïnstalleerd en hieraan een Intune-beleid is gekoppeld, wordt Microsoft Edge geopend.
- Als alleen de Managed Browser op het apparaat is geïnstalleerd en hieraan een Intune-beleid is gekoppeld, wordt de Managed Browser geopend.

## <a name="configure-application-proxy-settings-for-microsoft-edge"></a>Toepassingproxy-instellingen configureren voor Microsoft Edge

U kunt Microsoft Edge en de [Azure AD-toepassingsproxy](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) samen gebruiken om gebruikers toegang te verlenen tot intranetsites op hun mobiele apparaten. 

Hier volgen enkele voorbeelden van de scenario's waarin de Azure AD-toepassingsproxy wordt ingeschakeld: 

- Een gebruiker maakt gebruik van de mobiele app van Outlook, die wordt beveiligd door Intune. De gebruiker klikt vervolgens op een koppeling naar een intranetsite in een e-mailbericht en Microsoft Edge herkent dat deze intranetsite beschikbaar is gesteld voor de gebruiker via toepassingsproxy. De gebruiker wordt automatisch omgeleid via de toepassingsproxy om zich bij de betreffende meervoudige verificatie en voorwaardelijke toegang te verifiëren voordat de intranetsite wordt bereikt. De gebruiker heeft nu zelfs op mobiele apparaten toegang tot interne sites en de koppeling in Outlook werkt naar behoren.
- Een gebruiker opent Microsoft Edge op het iOS- of Android-apparaat. Als Microsoft Edge wordt beveiligd met Intune en de toepassingsproxy is ingeschakeld, kan de gebruiker naar een intranetsite navigeren via de gebruikelijke interne URL. Microsoft Edge herkent dat deze intranetsite via toepassingsproxy beschikbaar is gesteld aan de gebruiker. De gebruiker wordt automatisch door de toepassingsproxy gestuurd om zich te verifiëren voordat hij de intranetsite bereikt. 

### <a name="before-you-start"></a>Voordat u begint

- Stel de interne toepassingen in via de Azure AD-toepassingsproxy.
  - Raadpleeg [deze documentatie](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy) voor het configureren van de toepassingsproxy en het publiceren van toepassingen.
- Aan de Microsoft Edge-app moet een [Intune-beveiligingsbeleid](app-protection-policy.md) zijn toegewezen.

> [!NOTE]
> Het kan tot 24 uur duren voordat bijgewerkte omleidingsgegevens voor de toepassingsproxy worden doorgevoerd in Managed Browser en Microsoft Edge.

#### <a name="step-1-enable-automatic-redirection-to-microsoft-edge-from-outlook"></a>Stap 1: Schakel automatische omleiding naar Microsoft Edge vanuit Outlook in
Configureer Outlook met een beveiligingsbeleid voor apps waarmee de instelling **Webinhoud delen met door beleid beheerde browsers** wordt ingeschakeld.

![Schermafbeelding van beveiligingsbeleid voor apps - Webinhoud delen met door beleid beheerde browsers](./media/manage-microsoft-edge/manage-microsoft-edge-03.png)

#### <a name="step-2-set-the-app-configuration-setting-to-enable-app-proxy"></a>Stap 2: Stel de app-configuratie-instelling in voor het inschakelen van de toepassingsproxy
Wijs aan Microsoft Edge het volgende sleutel-waardepaar toe om de toepassingsproxy voor Microsoft Edge in te schakelen:

|    Sleutel    |    Waarde    |
|-------------------------------------------------------------------|-------------|
|    com.microsoft.intune.mam.managedbrowser.AppProxyRedirection    |    waar    |

Voor meer informatie over het gecombineerde gebruik van Microsoft Edge en de Azure AD-toepassingsproxy voor naadloze (en beveiligde) toegang tot on-premises web-apps raadpleegt u [Better together: Intune and Azure Active Directory team up to improve user access](https://cloudblogs.microsoft.com/enterprisemobility/2017/07/06/better-together-intune-and-azure-active-directory-team-up-to-improve-user-access). (Beter samen: Intune en Azure Active Directory werken samen om de toegang voor gebruikers te verbeteren.) Deze blogpost verwijst naar de Intune Managed Browser, maar de inhoud is ook van toepassing op Microsoft Edge.

## <a name="configure-a-homepage-shortcut-for-microsoft-edge"></a>Een snelkoppeling naar de startpagina van Microsoft Edge configureren

Met deze instelling kunt u een snelkoppeling naar de startpagina voor Microsoft Edge configureren. De snelkoppeling naar de startpagina die u configureert, verschijnt als eerste pictogram onder de zoekbalk, wanneer de gebruiker een nieuw tabblad in Microsoft Edge opent. De gebruiker kan deze snelkoppeling niet bewerken of verwijderen in zijn beheerde context. De snelkoppeling naar de startpagina geeft voor de duidelijkheid de naam van uw organisatie weer. 

Gebruik het volgende sleutel-waardepaar om een snelkoppeling naar de startpagina te configureren:

|    Sleutel    |    Waarde    |
|-------------------------------------------------------------------|-------------|
|    com.microsoft.intune.mam.managedbrowser.homepage   |    Geef een geldige URL op. Uit veiligheidsoogpunt worden onjuiste URL's geblokkeerd.<br>**Voorbeeld:**  <`https://www.bing.com`>

## <a name="configure-your-organizations-logo-and-brand-color-for-new-tab-pages-in-microsoft-edge"></a>Het logo en de merkkleur van uw organisatie configureren voor nieuwe tabbladen in Microsoft Edge

Met deze instellingen kunt u de nieuwe tabbladpagina voor Microsoft Edge aanpassen om het logo en de kleur van uw organisatie weer te geven als de achtergrond van de pagina.

Als u het logo en de kleur van uw organisatie wilt uploaden, moet u eerst de volgende stappen uitvoeren:
- Ga binnen de Azure Portal naar Intune -> Client-apps -> Huisstijl en aanpassing -> Huisstijl van bedrijfsidentiteit
- Als u het logo van uw merk wilt instellen, kiest u onder 'Weergeven' de optie 'Alleen bedrijfslogo'. Transparante achtergrondlogo's worden aanbevolen. 
- Als u de achtergrondkleur van uw merk wilt instellen, kiest u onder 'Weergeven' de optie 'Themakleur'. Microsoft Edge past een lichtere tint van de kleur toe op de nieuwe tabbladpagina. Dit zorgt ervoor dat de pagina goed leesbaar is. 

Gebruik vervolgens de volgende sleutel-/waardeparen om het merk van uw organisatie in Microsoft Edge weer te geven:

|    Sleutel    |    Waarde    |
|--------------------------------------------------------------------|------------|
|    com.microsoft.intune.mam.managedbrowser.NewTabPage.BrandLogo    |    True    |
|    com.microsoft.intune.mam.managedbrowser.NewTabPage.BrandColor    |    True    |

## <a name="display-relevant-industry-news-on-new-tab-pages"></a>Relevant nieuws van de branche weergeven op Nieuwe tabbladpagina

U kunt de Nieuwe tabbladpagina in Microsoft Edge Mobile configureren zodat er nieuws wordt weergegeven van de branche die relevant is voor uw organisatie. Als u deze functie inschakelt, gebruikt Microosft Edge Mobile de domeinnaam van uw organisatie voor het samenvoegen van nieuws van het web over uw organisatie, de branche van uw organisatie en de concurrentie, zodat uw gebruikers relevant externe nieuws kunnen vinden vanuit de nieuwe gecentraliseerde tabbladpagina's in Microsoft Edge. Nieuws van de branche is standaard uitgeschakeld en u kunt dit inschakelen voor uw organisatie. 

|    Sleutel    |    Waarde    |
|------------------------------------------------------|----------------------------------------------------------------------------------------------------------------|
|    com.microsoft.intune.ShowIndustryNews    |    Met **True** wordt het nieuws van de branche weergegeven op de Nieuwe tabbladpagina van Microsoft Edge Mobile.<p>Met **False** (standaard) wordt het nieuws van de branche verborgen op de Nieuwe tabbladpagina.    |

## <a name="configure-managed-bookmarks-for-microsoft-edge"></a>Beheerde bladwijzers configureren voor Microsoft Edge

Voor een betere toegankelijkheid kunt u bladwijzers configureren die u beschikbaar wilt stellen voor de gebruikers wanneer ze Microsoft Edge gebruiken. 

Hier volgt enige informatie:

- Gebruikers zien deze bladwijzers alleen wanneer ze de [bedrijfsmodus](https://docs.microsoft.com/intune/apps/app-configuration-managed-browser#how-to-configure-bookmarks-for-a-protected-browser) van Microsoft Edge gebruiken. 
- Deze bladwijzers kunnen niet door gebruikers worden verwijderd of gewijzigd.
- Deze bladwijzers worden boven in de lijst weergegeven. Door de gebruiker gemaakte bladwijzers worden onder deze bladwijzers weergegeven.
- Als u omleiding via een toepassingsproxy hebt ingeschakeld, kunt u web-apps met een toepassingsproxy toevoegen met behulp van hun interne of externe URL.
- Zorg ervoor dat u alle URL's voorziet van het voorvoegsel **http://** of **https://** wanneer u ze in de lijst invoert.

Gebruik het volgende sleutel-waardepaar om beheerde bladwijzers te configureren:

|    Sleutel    |    Waarde    |
|---------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    com.microsoft.intune.mam.managedbrowser.bookmarks    |    De waarde voor deze configuratie is een lijst met bladwijzers. Elke bladwijzer bestaat uit de titel en de URL van de bladwijzer. Scheid de titel en de URL met het teken `|`.      Voorbeeld:<br>`Microsoft Bing|https://www.bing.com`<br>Als u meerdere bladwijzers wilt configureren, typt u een dubbel scheidingsteken `||` tussen de bladwijzers.<p>Voorbeeld:<br>`Microsoft Bing|https://www.bing.com||Contoso|https://www.contoso.com`    |

## <a name="display-myapps-within-microsoft-edge-bookmarks"></a>MyApps weergeven in Microsoft Edge-bladwijzers

Standaard worden aan gebruikers de MyApps-sites weergegeven die voor hen zijn geconfigureerd. Deze staan in een map in de Microsoft Edge-bladwijzers. Deze map krijgt een label met de naam van uw organisatie.

|    Sleutel    |    Waarde    |
|------------------------------------------------------|----------------------------------------------------------------------------------------------------------------|
|    com.microsoft.intune.mam.managedbrowser.MyApps    |    Bij **Waar** wordt MyApps weergegeven in de Microsoft Edge-bladwijzers.<p>Bij **Onwaar** wordt MyApps verborgen in Microsoft Edge.    |

## <a name="specify-allowed-or-blocked-sites-list-for-microsoft-edge"></a>De lijst met toegestane of geblokkeerde sites voor Microsoft Edge opgeven
U kunt app-configuratie gebruiken om te bepalen tot welke sites gebruikers toegang kunnen krijgen met hun werkprofiel. Als u een lijst met toegestane sites gebruikt, hebben gebruikers alleen toegang tot de sites die u hierin expliciet hebt opgenomen. Als u een lijst met geblokkeerde sites gebruikt, hebben gebruikers toegang tot alle sites, met uitzondering van de sites die u expliciet hebt geblokkeerd. Gebruik alleen een lijst met toegestane sites of een lijst met geblokkeerde sites, niet beide. Als u beide lijsten gebruikt, heeft de lijst met toegestane sites voorrang.  

Gebruik de volgende sleutel-waardeparen om een lijst met toegestane sites of een lijst met geblokkeerde sites te configureren voor Microsoft Edge. 

|    Sleutel    |    Waarde    |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    U kunt kiezen uit:<p>1. Geef toegestane URL's op (alleen deze URL's zijn toegestaan; andere sites zijn niet toegankelijk):<br>`com.microsoft.intune.mam.managedbrowser.AllowListURLs`<p>2. Geef geblokkeerde URL's op (alle andere sites zijn toegankelijk):<br>`com.microsoft.intune.mam.managedbrowser.BlockListURLs`    |    De overeenkomstige waarde voor de sleutel is een lijst met URL's. U geeft alle URL's die u wilt toestaan of blokkeren op als één waarde, gescheiden door een sluisteken `|`.<br>**Voorbeelden:**<br>`URL1|URL2|URL3`<br>`http://.contoso.com/|https://.bing.com/|https://expenses.contoso.com`  |

### <a name="url-formats-for-allowed-and-blocked-site-list"></a>URL-indelingen voor een lijst met toegestane sites en een lijst met geblokkeerde sites 
U kunt verschillende URL-indelingen gebruiken om uw lijsten met toegestane/geblokkeerde sites te maken. De toegestane patronen worden in de volgende tabel beschreven. Enkele opmerkingen voordat u aan de slag gaat: 
- Zorg ervoor dat u alle URL's voorziet van het voorvoegsel **http://** of **https://** wanneer u ze in de lijst invoert.
- U kunt het jokerteken (\*) gebruiken volgens de regels in de volgende lijst met toegestane patronen.
- Een jokerteken kan alleen overeenkomen met een volledig onderdeel van de hostnaam (gescheiden door punten) of met volledige delen van het pad (gescheiden door slashes). `http://*contoso.com` wordt bijvoorbeeld **niet** ondersteund.
- U kunt poortnummers in het adres opgeven. Als u geen poortnummer opgeeft, worden deze waarden gebruikt:
  - Poort 80 voor http
  - Poort 443 voor https
- Het gebruik van jokertekens voor het poortnummer wordt **niet** ondersteund. `http://www.contoso.com:*` en `http://www.contoso.com:*/` bijvoorbeeld worden niet ondersteund. 

    |    URL    |    Details    |    Komt overeen met    |    Komt niet overeen met    |
    |-------------------------------------------|--------------------------------------------------------|-------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|
    |    `http://www.contoso.com`    |    Komt overeen met één pagina    |    `www.contoso.com`    |    `host.contoso.com`<br>`www.contoso.com/images`<br>`contoso.com/`    |
    |    `http://contoso.com`    |    Komt overeen met één pagina    |    `contoso.com/`    |    `host.contoso.com`<br>`www.contoso.com/images`<br>`www.contoso.com`    |
    |    `http://www.contoso.com/*;`   |    Komt overeen met alle URL's die beginnen met `www.contoso.com`    |    `www.contoso.com`<br>`www.contoso.com/images`<br>`www.contoso.com/videos/tvshows`    |    `host.contoso.com`<br>`host.contoso.com/images`    |
    |    `http://*.contoso.com/*`    |    Komt overeen met alle subdomeinen onder `contoso.com`    |    `developer.contoso.com/resources`<br>`news.contoso.com/images`<br>`news.contoso.com/videos`    |    `contoso.host.com`
    |    `http://*contoso.com/*`    |    Komt overeen met alle subdomeinen die eindigen op `contoso.com/`    |    `http://news-contoso.com`<br>`http://news-contoso.com.com/daily`    |    `http://news-contoso.host.com`    |
    `http://www.contoso.com/images`    |    Komt overeen met een afzonderlijke map    |    `www.contoso.com/images`    |    `www.contoso.com/images/dogs`    |
    |    `http://www.contoso.com:80`    |    Komt overeen met één pagina, met gebruik van een poortnummer    |    `http://www.contoso.com:80`    |         |
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
  - `https://*contoso.com`
  - `http://www.contoso.com:*`
  - `http://www.contoso.com: /*`

## <a name="transition-users-to-their-personal-context-when-trying-to-access-a-blocked-site"></a>Gebruikers overzetten naar hun persoonlijke context wanneer ze toegang proberen te krijgen tot een geblokkeerde site

Met het model voor dubbele identiteit dat is ingebouwd in Microsoft Edge, kunt u eindgebruikers meer flexibiliteit bieden dan mogelijk was met de Intune Managed Browser. Wanneer gebruikers een geblokkeerde site in Microsoft Edge tegenkomen, kunt u hen vragen de koppeling te openen in hun persoonlijke context in plaats van in hun zakelijke context. Op deze manier blijven de gebruikers beschermd en blijven de zakelijke resources veilig. Als een gebruiker bijvoorbeeld via Outlook een koppeling naar een nieuwsbericht krijgt toegestuurd, kan hij deze koppeling openen in zijn persoonlijke context of op een InPrivate-tabblad. In zijn werkcontext zijn nieuwswebsites niet toegestaan. Deze overgangen zijn standaard toegestaan.

Gebruik het volgende sleutel-waardepaar om te configureren of deze zachte overgangen zijn toegestaan:

|    Sleutel    |    Waarde    |
|----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `com.microsoft.intune.mam.managedbrowser.AllowTransitionOnBlock`    |    Bij **True** (standaard) kan Microsoft Edge gebruikers overzetten naar hun persoonlijke context om geblokkeerde sites te openen.<p>Met **False** voorkomt u het overzetten van gebruikers door Microsoft Edge. Gebruikers krijgen een bericht te zien waarin staat dat de site die ze proberen te openen, is geblokkeerd.    |

## <a name="open-restricted-links-directly-in-inprivate-tab-pages"></a>Beperkte links rechtstreeks in InPrivate-tabbladen openen

U kunt instellen dat beperkte links rechtstreeks worden geopend in de InPrivate-navigatie, waardoor gebruikers een vloeiendere browse-ervaring krijgen. Hierdoor hoeven gebruikers niet over te stappen op hun persoonlijke context om een site te bekijken. InPrivate-navigatie wordt beschouwd als niet-beheerd, waardoor gebruikers geen toegang kunnen krijgen wanneer zij de InPrivate-navigatiemodus gebruiken.

|    Sleutel    |    Waarde    |
|----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `com.microsoft.intune.mam.managedbrowser.AllowTransitionOnBlock`    |    Bij **Waar** kan Microsoft Edge gebruikers overzetten naar hun persoonlijke context om geblokkeerde sites te openen.<p>Met **Blokkeren** voorkomt u het overzetten van gebruikers door Microsoft Edge. Gebruikers krijgen een bericht te zien waarin staat dat de site die ze proberen te openen, is geblokkeerd.    |

## <a name="disable-microsoft-edge-prompt-to-save-passwords"></a>Microsoft Edge-prompt voor het opslaan van wachtwoorden uitschakelen

|    Sleutel    |    Waarde    |
|----------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    `com.microsoft.intune.mam.managedbrowser.openInPrivateIfBlock`    |    Met **True** worden beperkte links rechtstreeks in de InPrivate-navigatie geopend.<p>Met **False** (standaard) wordt gebruikers gevraagd een beperkte link te openen met de InPrivate-navigatie of met het persoonlijke account (MSA).    |

Microsoft Edge op iOS biedt standaard de mogelijkheid om de wachtwoorden van uw gebruikers op te slaan in de sleutelhanger. Als u deze prompt voor uw organisatie wilt uitschakelen, configureert u de volgende instelling:

|    Sleutel    |    Waarde    |
|-----------|-------------|
|     com.microsoft.Intune.mam.managedbrowser.disableFeatures    |    Met **Wachtwoord** wordt de prompt voor het opslaan van wachtwoorden uitgeschakeld.    |

## <a name="use-microsoft-edge-on-ios-to-access-managed-app-logs"></a>Met Microsoft Edge in iOS logboeken voor beheerde apps openen 

Gebruikers die Microsoft Edge op hun iOS-apparaat hebben geïnstalleerd, kunnen de beheerstatus van alle gepubliceerde Microsoft-apps bekijken. Ze kunnen logboeken versturen om problemen met hun beheerde iOS-apps op te lossen. Dit werkt als volgt:
1. Open Microsoft Edge op uw iOS-apparaat.
2. Type `about:intunehelp` in het adresvak. 
3. De probleemoplossingsmodus van Microsoft Edge wordt gestart.

Zie [Logboeken voor app-beveiliging in Managed Browser controleren](app-protection-policy-settings-log.md) voor een lijst met instellingen die worden opgeslagen in app-logboeken.

Lees [Send logs to your IT admin by email](https://docs.microsoft.com/intune-user-help/send-logs-to-your-it-admin-by-email-android) (Logboeken naar uw IT-beheerder verzenden via e-mail) om te zien hoe u logboeken op Android-apparaten kunt bekijken. 

## <a name="security-and-privacy-for-microsoft-edge"></a>Beveiliging en privacy voor Microsoft Edge

Hier volgen aanvullende overwegingen voor beveiliging en privacy voor Microsoft Edge:

- Microsoft Edge maakt geen gebruik van de instellingen die gebruikers instellen voor de systeemeigen browser op hun apparaten, omdat Microsoft Edge geen toegang heeft tot deze instellingen.
- U kunt de optie **Eenvoudige pincode vereisen voor toegang** of **Bedrijfsreferenties vereisen voor toegang** configureren in een app-beveiligingsbeleid dat is gekoppeld aan Microsoft Edge. Als een gebruiker de Help-koppeling op de verificatiepagina selecteert, kan hij alle internetsites bezoeken, ongeacht of deze zijn toegevoegd aan de lijst met geblokkeerde sites van het beleid.
- Microsoft Edge kan alleen toegang tot sites blokkeren wanneer de sites rechtstreeks worden geopend. De app kan de toegang niet blokkeren wanneer gebruikers tussenliggende services (zoals een vertaalservice) gebruiken voor toegang tot de site.
- Om verificatie en toegang tot de Intune-documentatie toe te staan, wordt * **.microsoft.com** uitgesloten van opname in lijsten met toegestane en geblokkeerde sites. Dit domein is altijd toegestaan.
- Gebruikers kunnen gegevensverzameling uitschakelen. Microsoft verzamelt automatisch anonieme gegevens over de prestaties en het gebruik van Managed Browser om Microsoft-producten en -services te verbeteren. Gebruikers kunnen het verzamelen van deze gegevens uitschakelen met de instelling **Gebruiksgegevens** op hun apparaten. U hebt geen controle over het verzamelen van deze gegevens. Op iOS-apparaten kunnen gebruikers geen websites openen met een verlopen of niet-vertrouwd certificaat.

## <a name="next-steps"></a>Volgende stappen

- [Wat zijn beleidsregels voor de beveiliging van apps?](app-protection-policy.md) 
