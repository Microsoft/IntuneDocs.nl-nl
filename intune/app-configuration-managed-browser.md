---
title: Bedrijfstoegang tot het web beheren via een met beleid beveiligde browser
titleSuffix: Microsoft Intune
description: Gebruik een met beleid beveiligde browser die is toegewezen met Intune, om zakelijke browsersessies en de overdracht van webgegevens te beheren.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/08/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1feca24f-9212-4d5d-afa9-7c171c5e8525
ms.reviewer: ilwu
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, seoapril2019
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8f32cfbb5e05958ec9d8f303809d3ffa28c3a3ec
ms.sourcegitcommit: 364a7dbc7eaa414c7a9c39cf53eb4250e1ad3151
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2019
ms.locfileid: "59569724"
---
# <a name="manage-web-access-using-a-microsoft-intune-policy-protected-browser"></a>Webtoegang beheren via een met Microsoft Intune-beleid beveiligde browser

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Met behulp van een browser die wordt beveiligd met Intune-beleid (Microsoft Edge of Intune Managed Browser), kunt u ervoor zorgen dat de toegang tot zakelijke websites altijd is beveiligd.  Als u deze configureert met Intune, bieden beveiligde browsers de volgende voordelen:

- Beleid voor toepassingsbeveiliging
- Voorwaardelijke toegang
- Eenmalige aanmelding
- Configuratie-instellingen voor toepassingen
- Proxyintegratie met Azure-toepassingen

## <a name="microsoft-edge-support"></a>Microsoft Edge-ondersteuning

U kunt Microsoft Edge gebruiken voor zakelijke scenario’s op iOS- en Android-apparaten. Microsoft Edge biedt ondersteuning voor dezelfde beheerscenario's als de Intune Managed Browser met de toevoeging van verbeteringen in de eindgebruikerservaring. Op basis van Intune-beleid zijn de volgende zakelijke functies van Microsoft Edge beschikbaar. Deze zakelijke functies omvatten:

1. **Dual-Identity**. Gebruikers kunnen zowel een werkaccount als een persoonlijk account maken om mee te browsen. Er is sprake van een volledige scheiding tussen de twee identiteiten. Dit is vergelijkbaar met de architectuur en ervaring in Office 365 en Outlook. Intune-beheerders kunnen het gewenste beleid instellen voor beveiligde browsersessies binnen het werkaccount. 
2. **Integratie van beveiligingsbeleid voor Intune-apps**. Beheerders kunnen nu app-beveiligingsbeleid instellen voor Microsoft Edge, inclusief beheer over knippen, kopiëren en plakken, waardoor er geen schermopnamen kunnen worden vastgelegd. Ook kunnen ze ervoor zorgen dat door de gebruiker geselecteerde koppelingen alleen kunnen worden geopend in andere beheerde apps.
3. **Proxyintegratie met Azure-toepassingen**. Beheerders kunnen toegang tot SaaS-app en web-apps beheren, en ervoor zorgen dat browser-apps alleen worden uitgevoerd in de beveiligde Microsoft Edge-browser, of eindgebruikers nu verbinding maken vanuit het bedrijfsnetwerk of vanaf internet. 
4. **Beheerde snelkoppelingen naar Favorieten en naar de startpagina**. Beheerders kunnen, voor een betere toegankelijkheid, URL’s instellen die worden weergegeven onder Favorieten wanneer eindgebruikers zich in hun zakelijke context bevinden. Beheerders kunnen een snelkoppeling naar de startpagina instellen, die wordt weergegeven als primaire snelkoppeling wanneer de zakelijke gebruiker een nieuwe pagina of een nieuw tabblad opent in Microsoft Edge.

Beveiligingsbeleid van Microsoft Intune voor Microsoft Edge helpt u om de gegevens en resources in uw organisatie te beveiligen. Met Intune beveiligde Microsoft Edge-sessies zorgen ervoor dat de resources in uw bedrijf niet alleen zijn beveiligd in systeemeigen geïnstalleerde apps, maar ook bij toegang via een webbrowser.

## <a name="getting-started"></a>Aan de slag

Microsoft Edge en de Intune Managed Browser zijn webbrowser-apps die u en uw eindgebruikers kunnen downloaden uit openbare app-stores en in uw organisatie kunnen gebruiken. 

Besturingssysteemvereisten voor browserbeleid:
- Android 4 en hoger of
- iOS 8.0 en hoger.

Oudere versies van Android en iOS kunnen Managed Browser nog steeds gebruiken, maar er kunnen geen nieuwe versies van de app op worden geïnstalleerd en kan er dus geen gebruik worden gemaakt van alle mogelijkheden van de app. U wordt aangeraden deze apparaten bij te werken tot een ondersteunde versie van het besturingssysteem.

>[!NOTE]
>Managed Browser biedt geen ondersteuning voor versie 3 van het cryptografische protocol Secure Sockets Layer (SSLv3).


## <a name="application-protection-policies-for-protected-browsers"></a>Beveiligingsbeleid voor toepassingen voor beveiligde browsers

Aangezien Microsoft Edge en Managed Browser zijn geïntegreerd met de Intune SDK, kunt u ook beleid voor app-beveiliging toepassen op de apps, waaronder:
- beperkingen afdwingen voor het knippen, kopiëren en plakken van gegevens;
- voorkomen dat er schermopnamen worden gemaakt;
- ervoor zorgen dat zakelijke koppelingen alleen kunnen worden geopend in beheerde apps en browsers.

Zie [Wat is beveiligingsbeleid voor apps?](app-protection-policy.md) voor meer informatie.

U kunt deze instellingen toepassen op:

- Apparaten die zijn ingeschreven bij Intune
- Apparaten die zijn ingeschreven bij een ander MDM-product
- Niet-beheerde apparaten

>[!NOTE]
>Als gebruikers Managed Browser vanuit de app store installeren en deze niet door Intune wordt beheerd, kunt u deze gebruiken als een eenvoudige webbrowser met ondersteuning voor eenmalige aanmelding via de site Microsoft MyApps. Gebruikers worden direct doorgestuurd naar de MyApps-website, waar alle ingerichte SaaS-toepassingen worden weergegeven.
Omdat Managed Browser of Microsoft Edge niet worden beheerd door Intune, kunnen de apps geen gegevens gebruiken uit andere apps die wel door Intune worden beheerd. 


## <a name="conditional-access-for-protected-browsers"></a>Voorwaardelijke toegang voor de beveiligde browsers

Managed Browser is nu een goedgekeurde client-app voor voorwaardelijke toegang. Dit betekent dat u de mobiele browsertoegang kunt beperken tot met Azure AD verbonden web-apps waarbij gebruikers alleen Managed Browser kunnen gebruiken en toegang vanaf andere niet-beveiligde browsers zoals Safari of Chrome wordt geblokkeerd. Deze beveiliging kan worden toegepast op Azure-resources zoals Exchange Online en SharePoint Online, het Microsoft 365 Office-beheercentrum en zelfs on-premises sites die u beschikbaar hebt gemaakt voor externe gebruikers via de [Azure AD-toepassingsproxy](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started). 

Als u met Azure AD verbonden web-apps wilt beperken tot het gebruik van Intune Managed Browser op mobiele platforms, kunt u voorwaardelijk toegangsbeleid maken waarbij goedgekeurde clienttoepassingen worden vereist. 

> [!TIP]  
> Voorwaardelijke toegang is een technologie van Azure Active Directory (Azure AD). Het knooppunt voor voorwaardelijke toegang dat via *Intune* wordt geopend, is hetzelfde als het knooppunt dat u opent via *Azure AD*.  


1. Selecteer in de Intune-portal achtereenvolgens **Voorwaardelijke toegang** > **Nieuw beleid**. 
2. Selecteer vervolgens **Verlenen** in de sectie **Besturingselementen voor toegang** van de blade. 
3. Klik op **Goedgekeurde client-apps vereisen**. 
4. Klik op **Selecteren** op de blade **Verlenen**. Dit beleid moet worden toegewezen aan de cloud-apps die u alleen voor de Intune Managed Browser-app toegankelijk wilt maken.

    ![Azure AD - Managed Browser-beleid voor voorwaardelijke toegang](./media/managed-browser-conditional-access-01.png)

5. Selecteer in de sectie **Toewijzingen** **Voorwaarden** > **Client-apps**. De blade **Client-apps** wordt weergegeven.
6. Klik op **Ja** onder **Configureren** om het beleid toe te passen op specifieke client-apps.
7. Controleer of **Browser** is geselecteerd als client-app.

    ![Azure AD - Managed Browser - client-apps selecteren](./media/managed-browser-conditional-access-02.png)

    > [!NOTE]
    > Als u wilt beperken welke systeemeigen apps (niet-browser-apps) toegang hebben tot deze cloudtoepassingen, kunt u ook **Mobiele apps en bureaublad-clients** selecteren.

8. Selecteer in de sectie **Toewijzingen** de optie **Gebruikers en groepen** en kies vervolgens de gebruikers of groepen die u wilt toewijzen aan dit beleid. 

    > [!NOTE]
    > Gebruikers moeten ook onder Intune App Protection-beleid vallen om app-configuratiebeleid te kunnen ontvangen. Zie [Wat is beveiligingsbeleid voor apps?](app-protection-policy.md) voor meer informatie over het maken van Intune-app-beveiligingsbeleid.

9. Selecteer in de sectie **Toewijzingen** de optie **Cloud-apps** om te kiezen welke apps met dit beleid moeten worden beveiligd.

Nadat het bovenstaande beleid is geconfigureerd, worden gebruikers gedwongen Intune Managed Browser te gebruiken voor toegang tot de met Azure AD verbonden web-apps die u hebt beveiligd met dit beleid. Als gebruikers in dit scenario een niet-beheerde browser proberen te gebruiken, zien ze een bericht dat Intune Managed Browser moet worden gebruikt.

De Managed Browser ondersteunt geen klassiek beleid voor voorwaardelijke toegang. Zie [Klassiek beleid migreren in Azure Portal](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-migration) voor meer informatie.

##  <a name="single-sign-on-to-azure-ad-connected-web-apps-in-policy-protected-browsers"></a>Eenmalige aanmelding voor met Azure AD verbonden web-apps in met beleid beveiligde browsers

In Microsoft Edge en Intune Managed Browser op iOS en Android kan eenmalige aanmelding worden gebruikt voor alle web-apps (SaaS en on-premises) die met Azure AD zijn verbonden. Wanneer de Microsoft Authenticator-app aanwezig is op iOS of de Intune-bedrijfsportal-app op Android, kunnen gebruikers van een met beleid beveiligde browser toegang krijgen tot met Azure AD verbonden web-apps zonder dat ze hun referenties opnieuw hoeven in te voeren.

Voor eenmalige aanmelding moet uw apparaat zijn geregistreerd door de Microsoft Authenticator-app voor iOS of de Intune-bedrijfsportal voor Android. Gebruikers met de Authenticator-app of Intune-bedrijfsportal wordt gevraagd hun apparaat te registreren wanneer ze naar een met Azure AD verbonden web-app in een met beleid beveiligde browser navigeren, als hun apparaat nog niet is geregistreerd door een andere toepassing. Nadat het apparaat is geregistreerd met het account dat wordt beheerd door Intune, wordt dat account voor eenmalige aanmelding ingeschakeld voor met Azure AD verbonden web-apps. 

> [!NOTE]
> Apparaatregistratie is eenvoudig inchecken met de Azure AD-service. Dit vereist geen volledige apparaatinschrijving en geeft IT geen extra bevoegdheden op het apparaat.

## <a name="create-a-protected-browser-app-configuration"></a>Een configuratie voor de beveiligde browser-app maken

>[!IMPORTANT]
>Om app-configuraties toe te passen, moet de beveiligde browser van de gebruiker, of een andere toepassing op het apparaat, al worden beheerd met [beleid voor app-beveiliging van Intune]( app-protection-policy.md)

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3.  Ga in de lijst Beheren naar de blade **Client-apps** en kies **App-configuratiebeleid**.
4.  Kies op de blade **App-configuratiebeleid** **Toevoegen**.
5.  Geef op de blade **Configuratiebeleid toevoegen** een **naam** en een optionele **beschrijving** op voor de app-configuratie-instellingen.
6.  Kies voor **Type apparaatregistratie** **Beheerde apps**.
7.  Kies **Vereiste app selecteren** en kies vervolgens op de blade **Doel-apps** **Managed Browser** en/of **Microsoft Edge** voor iOS, voor Android of voor beide besturingssystemen.
8.  Kies **OK** om terug te keren naar de blade **Configuratiebeleid toevoegen**.
9.  Kies **Configuratie-instellingen**. Op de blade **Configuratie** definieert u sleutel- en waardeparen voor configuraties voor Managed Browser. Gebruik de secties verderop in dit artikel voor meer informatie over de verschillende sleutel- en waardeparen die u kunt definiëren.
10. Kies **OK** als u klaar bent.
11. Kies op de blade **Configuratiebeleid toevoegen** de optie **Toevoegen**.
12. De nieuwe configuratie wordt gemaakt en weergegeven op de blade **App-configuratie**.


## <a name="assign-the-configuration-settings-you-created"></a>De configuratie-instellingen toewijzen die u hebt gemaakt

U wijst de instellingen aan Azure AD-groepen gebruikers toe. Als deze gebruiker de beveiligde browser-app heeft geïnstalleerd waarop het beleid is gericht, wordt de app beheerd door de instellingen die u hebt opgegeven.

1. Kies op de blade **Client-apps** van het Intune MAM-dashboard de optie **App-configuratiebeleid**.
2. Selecteer in de lijst met app-configuraties de configuratie die u wilt toewijzen.
3. Kies **Toewijzingen** op de volgende blade.
4. Selecteer op de blade **Toewijzingen** de Azure AD-groep waaraan u de app-configuratie wilt toewijzen en kies vervolgens **OK**.


## <a name="how-to-configure-application-proxy-settings-for-protected-browsers"></a>Application Proxy-instellingen configureren voor beveiligde browsers

Microsoft Edge en Intune Managed Browser en de [Azure AD-toepassingsproxy]( https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) kunnen samen worden gebruikt om de volgende scenario's te ondersteunen voor gebruikers van iOS- en Android-apparaten:

- Een gebruiker downloadt de Microsoft Outlook-app en meldt zich hierbij aan. Het beleid voor app-beveiliging van Intune wordt automatisch toegepast. Dit houdt in dat opgeslagen gegevens worden versleuteld en dat wordt voorkomen dat de gebruiker bestanden van het bedrijf overbrengt naar niet-beheerde apps of locaties op het apparaat. Wanneer de gebruiker vervolgens in Outlook klikt op een koppeling naar een intranetsite, kunt u instellen dat de koppeling alleen kan worden geopend in een beveiligde browser. De beveiligde browser herkent dat deze intranetsite via de toepassingsproxy beschikbaar is gesteld aan de gebruiker. De gebruiker wordt automatisch omgeleid via de toepassingsproxy, voor meervoudige verificatie en voorwaardelijke toegang, voordat de intranetsite wordt bereikt. Deze site, die eerder niet bereikbaar was omdat de gebruiker extern was, is nu toegankelijk en de koppeling in Outlook werkt zoals verwacht.
- Een externe gebruiker opent de beveiligde browser en gaat naar een intranetsite via de interne URL. De beveiligde browser herkent dat deze intranetsite via de toepassingsproxy beschikbaar is gesteld aan de gebruiker. De gebruiker wordt automatisch omgeleid via de toepassingsproxy, voor meervoudige verificatie en voorwaardelijke toegang, voordat de intranetsite wordt bereikt. Deze site, die eerder niet bereikbaar was omdat de gebruiker extern was, is nu toegankelijk.

### <a name="before-you-start"></a>Voordat u begint

- Stel de interne toepassingen in via de toepassingsproxy van Azure AD.
    - Raadpleeg [deze documentatie](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy) voor het configureren van de toepassingsproxy en het publiceren van toepassingen. 
- U moet minimaal versie 1.2.0 van de Managed Browser-app gebruiken.
- Er is een [beleid voor app-beveiliging van Intune](app-protection-policy.md) toegewezen aan de Managed Browser- of Microsoft Edge-app.

    > [!NOTE]
    > Het kan tot 24 uur duren voordat bijgewerkte omleidingsgegevens voor de toepassingsproxy worden doorgevoerd in Managed Browser en Microsoft Edge.


#### <a name="step-1-enable-automatic-redirection-to-a-protected-browser-from-outlook"></a>Stap 1: schakel automatische omleiding naar een beveiligde browser vanuit Outlook in
Outlook moet zijn geconfigureerd met een beleid voor app-beveiliging waarmee de instelling **Webinhoud beperken voor weergave in de Managed Browser** beschikbaar komt.

#### <a name="step-2-assign-an-app-configuration-policy-assigned-for-the-protected-browser"></a>Stap 2: wijs een app-configuratiebeleid toe voor de beveiligde browser.
Met deze procedure wordt de Managed Browser- of Microsoft Edge-app geconfigureerd voor omleiding via een proxy. Geef met de procedure voor het maken van een app-configuratie voor Microsoft Edge of Managed Browser het volgende sleutel-waardepaar op:

| Sleutel                                                             | Waarde    |
|-----------------------------------------------------------------|----------|
| **com.microsoft.intune.mam.managedbrowser.AppProxyRedirection** | **true** |

Voor meer informatie over het gecombineerde gebruik van Managed Browser, Microsoft Edge en de Azure AD-toepassingsproxy voor naadloze (en beveiligde) toegang tot on-premises web-apps, raadpleegt u de blogpost voor Enterprise Mobility + Security [Better together: Intune and Azure Active Directory team up to improve user access](https://cloudblogs.microsoft.com/enterprisemobility/2017/07/06/better-together-intune-and-azure-active-directory-team-up-to-improve-user-access). (Beter samen: Intune en Azure Active Directory werken samen om de toegang voor gebruikers te verbeteren.)

> [!NOTE]
> Voor Microsoft Edge wordt hetzelfde sleutel- en waardepaar gebruikt als voor Managed Browser. 

## <a name="how-to-configure-the-homepage-for-a-protected-browser"></a>Startpagina configureren voor een beveiligde browser

Met deze instelling kunt u de startpagina configureren die gebruikers zien wanneer ze de een beveiligde browser starten of een nieuw tabblad maken. 
- Deze instelling wordt weergegeven op de webpagina in Managed Browser.  Edge geeft in plaats daarvan een snelkoppeling naar de startpagina weer.
- Het snelkoppelingspictogram naar de startpagina verschijnt als pictogram onder het besturingselement voor zoeken.  Het kan niet worden bewerkt of verwijderd.
- De snelkoppeling naar de startpagina geeft de naam van uw organisatie weer om deze te onderscheiden.  Deze verschijnt altijd als het eerste pictogram.

Geef met de procedure voor het maken van een app-configuratie voor Microsoft Edge of Managed Browser het volgende sleutel-waardepaar op:

|                                Sleutel                                |                                                           Waarde                                                            |
|-------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------|
| <strong>com.microsoft.intune.mam.managedbrowser.homepage</strong> | Geef een geldige URL op. Uit veiligheidsoogpunt worden onjuiste URL's geblokkeerd.<br>Voorbeeld: `<https://www.bing.com>` |

## <a name="how-to-configure-bookmarks-for-a-protected-browser"></a>Bladwijzers configureren voor een beveiligde browser

Met deze instelling kunt u een set bladwijzers configureren die beschikbaar zijn voor gebruikers van Microsoft Edge of Managed Browser.

- Deze bladwijzers kunnen niet worden verwijderd of gewijzigd door gebruikers.
- Deze bladwijzers worden bovenaan de lijst weergegeven. Bladwijzers die gebruikers maken, worden onder deze bladwijzers weergegeven.
- Als u App Proxy-omleiding hebt ingeschakeld, kunt u App Proxy-webapps toevoegen met behulp van hun interne of externe URL.

Geef met de procedure voor het maken van een app-configuratie voor Microsoft Edge of Managed Browser het volgende sleutel-waardepaar op:

|                                Sleutel                                 |                                                                                                                                                                                                                                                         Waarde                                                                                                                                                                                                                                                          |
|--------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <strong>com.microsoft.intune.mam.managedbrowser.bookmarks</strong> | De waarde voor deze configuratie is een lijst met bladwijzers. Elke bladwijzer bestaat uit de titel en de URL van de bladwijzer. Scheid de titel en een URL met het teken <strong>&#124;</strong>.<br><br>Voorbeeld:<br> <code>Microsoft Bing&#124;https://www.bing.com</code><br><br>Als u meerdere bladwijzers wilt configureren, typt u een dubbel scheidingsteken <strong>&#124; &#124;</strong> tussen de bladwijzers.<br><br>Voorbeeld:<br> <code>Bing&#124;https://www.bing.com&#124;&#124;Contoso&#124;https://www.contoso.com</code> |

## <a name="how-to-specify-allowed-and-blocked-urls-for-a-protected-browser"></a>Toegestane en geblokkeerde URL's voor een beveiligde browser opgeven

Geef met de procedure voor het maken van een app-configuratie voor Microsoft Edge of Managed Browser het volgende sleutel-waardepaar op:

|Sleutel|Waarde|
|-|-|
|U kunt kiezen uit:<br><ul><li>Geef toegestane URL's op (alleen deze URL's zijn toegestaan; andere sites zijn niet toegankelijk):<br> **com.microsoft.intune.mam.managedbrowser.AllowListURLs**<br><br></li><li>Geef geblokkeerde URL's op (alle andere sites zijn toegankelijk):<br>**com.microsoft.intune.mam.managedbrowser.BlockListURLs**</li></ul>|De overeenkomstige waarde voor de sleutel is een lijst met URL's. U voert alle URL's die u wilt toestaan of blokkeren in als één waarde, gescheiden door een sluisteken **&#124;**.<br><br>Voorbeelden:<br><br><code>URL1&#124;URL2&#124;URL3</code><br><code>http://*.contoso.com/*&#124;https://*.bing.com/*&#124;https://expenses.contoso.com</code>|

>[!IMPORTANT]
>Geef niet beide sleutels op. Als beide sleutels zijn bedoeld voor dezelfde gebruiker, moet de sleutel voor toegestane URL's worden gebruikt, aangezien dit de meest beperkende optie is.
>Controleer ook dat geen belangrijke pagina's worden geblokkeerd, zoals de website van uw bedrijf.

### <a name="url-format-for-allowed-and-blocked-urls"></a>URL-indeling voor toegestane en geblokkeerde URL´s
Gebruik de volgende gegevens voor meer informatie over de toegestane indelingen en jokertekens die u kunt gebruiken bij het opgeven van URL's in de lijsten met toegestane en geblokkeerde websites:

- U kunt het jokerteken (**&#42;**) gebruiken volgens de regels in de onderstaande lijst met toegestane patronen.

- Zorg ervoor dat u alle URL's voorziet van het voorvoegsel **http** of **https** wanneer u ze in de lijst invoert.

- U kunt poortnummers in het adres opgeven. Als u geen poortnummer opgeeft, worden deze waarden gebruikt:

  -   Poort 80 voor http

  -   Poort 443 voor https

  Het gebruik van jokertekens voor het poortnummer wordt niet ondersteund. `http://www.contoso.com:;` en `http://www.contoso.com: /;` bijvoorbeeld worden niet ondersteund.

- Gebruik de volgende tabel voor meer informatie over de toegestane patronen die u kunt gebruiken wanneer u een URL opgeeft:

|                  URL                  |                     Details                      |                                                Komt overeen met                                                |                                Komt niet overeen met                                 |
|---------------------------------------|--------------------------------------------------|-------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------|
|        `http://www.contoso.com`         |              Komt overeen met één pagina               |                                            `www.contoso.com`                                            |  `host.contoso.com`<br /><br />`www.contoso.com/images`<br /><br />`contoso.com`/   |
|          `http://contoso.com`           |              Komt overeen met één pagina               |                                             `contoso.com/`                                              | `host.contoso.com`<br /><br />`www.contoso.com/images`<br /><br />`www.contoso.com` |
|    `http://www.contoso.com/&#42;`     | Komt overeen met alle URL's die beginnen met `www.contoso.com` |      `www.contoso.com`<br /><br />`www.contoso.com/images`<br /><br />`www.contoso.com/videos/tvshows`      |              `host.contoso.com`<br /><br />`host.contoso.com/images`              |
|    `http://*.contoso.com/*`     |     Komt overeen met alle subdomeinen onder contoso.com     | `developer.contoso.com/resources`<br /><br />`news.contoso.com/images`<br /><br />`news.contoso.com/videos` |                               `contoso.host.com`                                |
|     `http://www.contoso.com/images`     |             Komt overeen met een afzonderlijke map              |                                        `www.contoso.com/images`                                         |                          `www.contoso.com/images/dogs`                          |
|       `http://www.contoso.com:80`       |  Komt overeen met één pagina, met gebruik van een poortnummer   |                                       `http://www.contoso.com:80`                                       |                                                                               |
|        `https://www.contoso.com`        |          Komt overeen met een enkele, beveiligde pagina           |                                        `https://www.contoso.com`                                        |                            `http://www.contoso.com`                             |
| `http://www.contoso.com/images/&#42;` |    Komt overeen met een enkele map en alle submappen    |                  `www.contoso.com/images/dogs`<br /><br />`www.contoso.com/images/cats`                   |                            `www.contoso.com/videos`                             |

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
## <a name="opening-links-within-the-intune-managed-browser-vs-microsoft-edge"></a>Koppelingen openen in de Intune Managed Browser versus Microsoft Edge 

Zowel de Intune Managed Browser als Microsoft Edge worden nu beschouwd als door beleid beheerde browsers/beveiligde browsers. Tegenwoordig resulteert beleid voor app-beveiliging in webkoppelingen vanuit door Intune beheerde apps, die moeten worden geopend in een specifieke browser, afhankelijk van uw scenario en platform. 

Op Android: 
* Managed Browser wordt geopend als een gebruiker zowel Managed Browser als Microsoft Edge op het apparaat heeft geïnstalleerd. Om ervoor te zorgen dat Microsoft Edge wordt geopend in plaats van Managed Browser, stelt u de app-configuratie-instelling com.microsoft.intune.useEdge in op true (waar) voor alle met Intune beheerde apps waarbij een door beleid beheerde browser is vereist.  
* Als alleen Microsoft Edge op het apparaat staat en onder beleid valt, wordt Microsoft Edge geopend.
* Als alleen Managed Browser op het apparaat staat en onder beleid valt, wordt Managed Browser geopend. 

Op iOS, voor apps waarvoor de Intune SDK is geïntegreerd voor iOS v. 9.0.9+ : 
* Managed Browser, als zowel MB als Edge op het apparaat staan, tenzij de app-configuratie-instelling com.microsoft.intune.useEdge is ingesteld op true (waar) voor alle met Intune beheerde apps waarbij een door beleid beheerde browser is vereist, **of** Microsoft Edge, als Microsoft Edge is geïnstalleerd en beleid heeft ontvangen. 
* Microsoft Edge, als alleen Microsoft Edge op het apparaat staat, onder beleid valt en beleid heeft ontvangen. 
* Managed Browser, als alleen Managed Browser op het apparaat staat, onder beleid valt en beleid heeft ontvangen.

## <a name="how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios"></a>Toegang tot logboeken van beheerde apps met Managed Browser in iOS

Eindgebruikers bij wie Managed Browser is geïnstalleerd op hun iOS-apparaat, kunnen de beheerstatus van alle gepubliceerde Microsoft-apps bekijken. Ze kunnen logboeken versturen om problemen met hun beheerde iOS-apps op te lossen.

1. Open **iOS-instellingen**.
2. Selecteer de toepassingsinstellingen voor Managed **Browser**.
3. Verschuif de knop **Intune diagnostische gegevens inschakelen** om de browser in te stellen op de probleemoplossingsmodus.
4. Open Managed **Browser**. Klik op **Intune App-status weergeven** om beleidsinstellingen voor toepassingen afzonderlijk te bekijken.
5. Druk op **Aan de slag** en **Logboeken delen** of **Logboeken naar Microsoft verzenden** om de logboeken met probleemoplossing naar uw IT-beheerder of Microsoft te verzenden.

U kunt de browser ook openen in de probleemoplossingsmodus vanuit de app.

1. Open Managed Browser.
2. Type `about:intunehelp` in het adresvak.
De probleemoplossingsmodus van de Browser wordt gestart.

Zie [Logboeken voor app-beveiliging in Managed Browser controleren](app-protection-policy-settings-log.md) voor een lijst met instellingen die worden opgeslagen in app-logboeken.

## <a name="security-and-privacy-for-the-managed-browser"></a>Beveiliging en privacy voor Managed Browser

-   Managed Browser gebruikt geen instellingen die gebruikers maken voor de ingebouwde browser op hun apparaten. Managed Browser heeft geen toegang tot deze instellingen.

-   Als u de optie **Eenvoudige pincode vereist voor toegang** of **Bedrijfsreferenties vereist voor toegang** configureert in een beleid voor app-beveiliging dat is gekoppeld aan Managed Browser, en een gebruiker de Help-koppeling op de verificatiepagina selecteert, kan de gebruiker elke internetsite bezoeken ongeacht of deze is toegevoegd aan de lijst met geblokkeerde websites in het beleid.

-   Managed Browser kan alleen toegang tot sites blokkeren wanneer de sites rechtstreeks worden geopend. De app kan niet de toegang blokkeren als er tussenliggende services (zoals een vertaalservice) worden gebruikt voor toegang tot de site.

-   Om verificatie en toegang tot de Intune-documentatie toe te staan, wordt **&#42;.microsoft.com** uitgesloten van opname in lijsten met toegestane en geblokkeerde sites. Dit domein is altijd toegestaan.

### <a name="turn-off-usage-data"></a>Gebruiksgegevens uitschakelen
Microsoft verzamelt automatisch anonieme gegevens over de prestaties en het gebruik van Managed Browser om Microsoft-producten en -services te verbeteren. Gebruikers kunnen het verzamelen van deze gegevens uitschakelen met de instelling **Gebruiksgegevens** op hun apparaten. U hebt geen controle over het verzamelen van deze gegevens.

-   Op iOS-apparaten kunnen gebruikers geen websites openen met een verlopen of niet-vertrouwd certificaat.

## <a name="next-steps"></a>Volgende stappen

- [Wat zijn beleidsregels voor de beveiliging van apps?](app-protection-policy.md) 
