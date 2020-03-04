---
title: Bedrijfstoegang tot het web beheren via een met beleid beveiligde browser
titleSuffix: Microsoft Intune
description: Gebruik een met beleid beveiligde browser die is toegewezen met Intune, om zakelijke browsersessies en de overdracht van webgegevens te beheren.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/28/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1feca24f-9212-4d5d-afa9-7c171c5e8525
ms.reviewer: ilwu
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, seoapril2019
ms.collection: M365-identity-device-management
ms.openlocfilehash: 03b89225ee5691aea2653fb3ca19f99139a015aa
ms.sourcegitcommit: 9ee2401a2f01373a962749b0728c22385dbcba6d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/29/2020
ms.locfileid: "78181809"
---
# <a name="manage-web-access-using-a-microsoft-intune-policy-protected-browser"></a>Webtoegang beheren via een met Microsoft Intune-beleid beveiligde browser

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Met behulp van een browser die wordt beveiligd met Intune-beleid (Microsoft Edge of Intune Managed Browser), kunt u ervoor zorgen dat de toegang tot zakelijke websites altijd is beveiligd.  Als u deze configureert met Intune, bieden beveiligde browsers de volgende voordelen:

- Beleid voor toepassingsbeveiliging
- Voorwaardelijke toegang
- Eenmalige aanmelding
- Configuratie-instellingen voor toepassingen
- Proxyintegratie met Azure-toepassingen

> [!IMPORTANT]
> De Intune Managed Browser wordt buiten gebruik gesteld. Gebruik Microsoft Edge als uw beveiligde Intune-browser. 

## <a name="microsoft-edge-support"></a>Microsoft Edge-ondersteuning

U kunt Microsoft Edge gebruiken voor zakelijke scenario’s op iOS-/iPadOS- en Android-apparaten. Microsoft Edge biedt ondersteuning voor dezelfde beheerscenario's als de Intune Managed Browser met de toevoeging van verbeteringen in de eindgebruikerservaring. Op basis van Intune-beleid zijn onder andere de volgende zakelijke functies van Microsoft Edge beschikbaar:

- **Dual-Identity**. Gebruikers kunnen zowel een werkaccount als een persoonlijk account maken om mee te browsen. Er is sprake van een volledige scheiding tussen de twee identiteiten. Dit is vergelijkbaar met de architectuur en ervaring in Office 365 en Outlook. Intune-beheerders kunnen het gewenste beleid instellen voor beveiligde browsersessies binnen het werkaccount. 
- **Integratie van beveiligingsbeleid voor Intune-apps**. Beheerders kunnen nu app-beveiligingsbeleid instellen voor Microsoft Edge, inclusief beheer over knippen, kopiëren en plakken, waardoor er geen schermopnamen kunnen worden vastgelegd. Ook kunnen ze ervoor zorgen dat door de gebruiker geselecteerde koppelingen alleen kunnen worden geopend in andere beheerde apps.
- **Proxyintegratie met Azure-toepassingen**. Beheerders kunnen toegang tot SaaS-app en web-apps beheren, en ervoor zorgen dat browser-apps alleen worden uitgevoerd in de beveiligde Microsoft Edge-browser, of eindgebruikers nu verbinding maken vanuit het bedrijfsnetwerk of vanaf internet. 
- **Beheerde snelkoppelingen naar Favorieten en naar de startpagina**. Beheerders kunnen, voor een betere toegankelijkheid, URL’s instellen die worden weergegeven onder Favorieten wanneer eindgebruikers zich in hun zakelijke context bevinden. Beheerders kunnen een snelkoppeling naar de startpagina instellen, die wordt weergegeven als primaire snelkoppeling wanneer de zakelijke gebruiker een nieuwe pagina of een nieuw tabblad opent in Microsoft Edge.

Beveiligingsbeleid van Microsoft Intune voor Microsoft Edge helpt u om de gegevens en resources in uw organisatie te beveiligen. Met Intune beveiligde Microsoft Edge-sessies zorgen ervoor dat de resources in uw bedrijf niet alleen zijn beveiligd in systeemeigen geïnstalleerde apps, maar ook bij toegang via een webbrowser.

## <a name="getting-started"></a>Aan de slag

Microsoft Edge en de Intune Managed Browser zijn webbrowser-apps die u en uw eindgebruikers kunnen downloaden uit openbare app-stores en in uw organisatie kunnen gebruiken. 

Besturingssysteemvereisten voor browserbeleid:
- Android 4 en hoger of
- iOS/iPadOS 8.0 en hoger.

Oudere versies van Android en iOS/iPadOS kunnen Managed Browser nog steeds gebruiken, maar er kunnen geen nieuwe versies van de app op worden geïnstalleerd en kan er dus geen gebruik worden gemaakt van alle mogelijkheden van de app. U wordt aangeraden deze apparaten bij te werken tot een ondersteunde versie van het besturingssysteem.

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

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apparaten** > **Voorwaardelijke toegang** > **Nieuw beleid**.
3. Voeg de **naam** van het beleid toe. 
4. Selecteer in de sectie **Toewijzingen** **Voorwaarden** > **Client-apps**. Het deelvenster **Client-apps** wordt weergegeven.
5. Klik op **Ja** onder **Configureren** om het beleid toe te passen op specifieke client-apps.
6. Controleer of **Browser** is geselecteerd als client-app.

    ![Azure AD - Managed Browser - client-apps selecteren](./media/app-configuration-managed-browser/managed-browser-conditional-access-02.png)

    > [!NOTE]
    > Als u wilt beperken welke systeemeigen apps (niet-browser-apps) toegang hebben tot deze cloudtoepassingen, kunt u ook **Mobiele apps en bureaublad-clients** selecteren.

7. Klik op **Gereed** > **Gereed**.
8. Selecteer in de sectie **Toewijzingen** de optie **Gebruikers en groepen** en kies de gebruikers of groepen waaraan u dit beleid wilt toewijzen. Klik op **Gereed** om het deelvenster te sluiten.
9. Selecteer in de sectie **Toewijzingen** de optie **Cloud-apps of acties** om te kiezen welke apps met dit beleid moeten worden beveiligd. Klik op **Gereed** om het deelvenster te sluiten.
10. Selecteer **Verlenen** in het gedeelte **Besturingselementen voor toegang** van het deelvenster. 
11. Klik op **Toegang verlenen** en klik vervolgens op **Goedgekeurde client-app vereisen**. 
12. Klik op **Selecteren** in het deelvenster **Verlenen**. Dit beleid moet worden toegewezen aan de cloud-apps die u alleen voor de Intune Managed Browser-app toegankelijk wilt maken.

    ![Azure AD - Managed Browser-beleid voor voorwaardelijke toegang](./media/app-configuration-managed-browser/managed-browser-conditional-access-01.png)



Nadat het bovenstaande beleid is geconfigureerd, worden gebruikers gedwongen Intune Managed Browser te gebruiken voor toegang tot de met Azure AD verbonden web-apps die u hebt beveiligd met dit beleid. Als gebruikers in dit scenario een niet-beheerde browser proberen te gebruiken, zien ze een bericht dat Intune Managed Browser moet worden gebruikt.

De Managed Browser ondersteunt geen klassiek beleid voor voorwaardelijke toegang. Zie [Klassiek beleid migreren in Azure Portal](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-migration) voor meer informatie.

## <a name="single-sign-on-to-azure-ad-connected-web-apps-in-policy-protected-browsers"></a>Eenmalige aanmelding voor met Azure AD verbonden web-apps in met beleid beveiligde browsers

In Microsoft Edge en Intune Managed Browser op iOS/iPadOS en Android kan eenmalige aanmelding worden gebruikt voor alle web-apps (SaaS en on-premises) die met Azure AD zijn verbonden. Wanneer de Microsoft Authenticator-app aanwezig is in iOS/iPadOS of de Intune-bedrijfsportal-app op Android, kunnen gebruikers van een met beleid beveiligde browser toegang krijgen tot met Azure AD verbonden web-apps zonder dat ze hun referenties opnieuw hoeven in te voeren.

Voor eenmalige aanmelding moet uw apparaat zijn geregistreerd door de Microsoft Authenticator-app voor iOS/iPadOS of de Intune-bedrijfsportal voor Android. Gebruikers met de Authenticator-app of Intune-bedrijfsportal wordt gevraagd hun apparaat te registreren wanneer ze naar een met Azure AD verbonden web-app in een met beleid beveiligde browser navigeren, als hun apparaat nog niet is geregistreerd door een andere toepassing. Nadat het apparaat is geregistreerd met het account dat wordt beheerd door Intune, wordt dat account voor eenmalige aanmelding ingeschakeld voor met Azure AD verbonden web-apps. 

> [!NOTE]
> Apparaatregistratie is eenvoudig inchecken met de Azure AD-service. Dit vereist geen volledige apparaatinschrijving en geeft IT geen extra bevoegdheden op het apparaat.

## <a name="create-a-protected-browser-app-configuration"></a>Een configuratie voor de beveiligde browser-app maken

>[!IMPORTANT]
>Om app-configuraties toe te passen, moet de beveiligde browser van de gebruiker, of een andere toepassing op het apparaat, al worden beheerd met [beleid voor app-beveiliging van Intune]( ../app-protection-policy.md)

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apps** > **App-configuratiebeleid** > **Toevoegen** > **Beheerde apps**.
3. Geef op de pagina **Basisinformatie** in het deelvenster **Configuratiebeleid toevoegen** een **naam** en een optionele **beschrijving** op voor de app-configuratie-instellingen.
4. Kies **De openbare app selecteren** en kies **Managed Browser** en/of **Edge** voor iOS/iPadOS, voor Android of voor beide besturingssystemen.
5. Klik op **Selecteren** om terug te gaan naar het deelvenster **App-configuratiebeleid maken**.
6. Klik op **Volgende** om de pagina **Instelling** weer te geven.
7. Op de pagina **Instelling** definieert u sleutel- en waardeparen voor configuraties voor de app. Gebruik de secties verderop in dit artikel voor meer informatie over de verschillende sleutel- en waardeparen die u kunt definiëren.
8. Klik op **Volgende** om de pagina **Toewijzing** weer te geven en klik vervolgens op **Groepen selecteren die moeten worden opgenomen** en/of **Groepen selecteren die moeten worden uitgesloten**.
9. Klik op **Volgende** om naar de pagina **Controleren en maken** weer te geven.
10. Klik op **Maken** nadat u het app-configuratiebeleid hebt gecontroleerd.

De nieuwe configuratie wordt gemaakt en weergegeven in het deelvenster **App-configuratiebeleid**.


## <a name="assign-the-configuration-settings-you-created"></a>De configuratie-instellingen toewijzen die u hebt gemaakt

U wijst de instellingen aan Azure AD-groepen gebruikers toe. Als deze gebruiker de beveiligde browser-app heeft geïnstalleerd waarop het beleid is gericht, wordt de app beheerd door de instellingen die u hebt opgegeven.

1. Kies in het deelvenster **Apps** van het Intune MAM-dashboard de optie **App-configuratiebeleid**.
2. Selecteer in de lijst met app-configuraties de configuratie die u wilt toewijzen.
3. Kies **Toewijzingen** in het volgende deelvenster.
4. Selecteer in het deelvenster **Toewijzingen** de Azure AD-groep waaraan u de app-configuratie wilt toewijzen en kies vervolgens **OK**.

## <a name="how-to-set-microsoft-edge-as-the-protected-browser-for-your-organization"></a>Microsoft Edge instellen als de beveiligde browser voor uw organisatie

Met deze instelling kunt u configureren of uw gebruikers worden omgeleid naar Microsoft Edge of Intune Managed Browser, ervan uitgaande dat beide browsers vallen onder het beleid voor app-beveiliging. **Deze instelling voor toepassingsconfiguratiebeleid moet zijn gericht op beheerde Intune-apps vanwaaruit de webkoppeling wordt geopend.** 

Als deze instelling is ingesteld op Waar:

- Uw gebruikers worden omgeleid naar Microsoft Edge wanneer ze koppelingen openen vanuit beheerde Intune-apps die onder deze instelling vallen. 
- Als ze de app nog niet hebben, wordt hun gevraagd Microsoft Edge te downloaden uit de Store, ongeacht of ze Intune Managed Browser hebben gedownload.

Als deze instelling is ingesteld op Onwaar:

- Als gebruikers **zowel** Managed Browser als Microsoft Edge hebben gedownload, wordt Managed Browser gestart. 
- Als gebruikers **of** Managed Browser **of** Microsoft Edge hebben gedownload, wordt de browser-app gestart. 
- Als gebruikers geen van beide browser-apps hebben gedownload, wordt hen gevraagd om Managed Browser te downloaden.

Gebruik de bovenstaande procedure om een app-configuratie voor Microsoft Edge te maken. Geef het volgende sleutel-waardepaar op bij het selecteren van de **Configuratie-instellingen** in het deelvenster **Configuratie** (stap 9):

| Sleutel                              |  Waarde   |
|----------------------------------|----------|
| **com.microsoft.intune.useEdge** | **true** |

> [!NOTE]
> Zorg ervoor dat in het beleid voor app-beveiliging waarmee Microsoft Edge en de in de app-configuratie opgegeven gekoppelde apps worden beheerd, de volgende beleidsinstellingen voor gegevensbescherming zijn ingesteld:
> - Organisatiegegevens naar andere apps verzenden: **Met beleid beheerde apps**
> - Overdracht van webinhoud met andere apps beperken: **Door beleid beheerde browsers**

## <a name="how-to-configure-application-proxy-settings-for-protected-browsers"></a>Application Proxy-instellingen configureren voor beveiligde browsers

Microsoft Edge en Intune Managed Browser en de [Azure AD-toepassingsproxy]( https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) kunnen samen worden gebruikt om de volgende scenario's te ondersteunen voor gebruikers van iOS-/iPadOS- en Android-apparaten:

- Een gebruiker downloadt de Microsoft Outlook-app en meldt zich hierbij aan. Het beleid voor app-beveiliging van Intune wordt automatisch toegepast. Dit houdt in dat opgeslagen gegevens worden versleuteld en dat wordt voorkomen dat de gebruiker bestanden van het bedrijf overbrengt naar niet-beheerde apps of locaties op het apparaat. Wanneer de gebruiker vervolgens in Outlook klikt op een koppeling naar een intranetsite, kunt u instellen dat de koppeling alleen kan worden geopend in een beveiligde browser. De beveiligde browser herkent dat deze intranetsite via de toepassingsproxy beschikbaar is gesteld aan de gebruiker. De gebruiker wordt automatisch omgeleid via de toepassingsproxy om zich bij de betreffende meervoudige verificatie en voorwaardelijke toegang te verifiëren voordat de intranetsite wordt bereikt. Deze site, die eerder niet bereikbaar was omdat de gebruiker extern was, is nu toegankelijk en de koppeling in Outlook werkt zoals verwacht.
- Een externe gebruiker opent de beveiligde browser en gaat naar een intranetsite via de interne URL. De beveiligde browser herkent dat deze intranetsite via de toepassingsproxy beschikbaar is gesteld aan de gebruiker. De gebruiker wordt automatisch omgeleid via de toepassingsproxy om zich bij de betreffende meervoudige verificatie en voorwaardelijke toegang te verifiëren voordat de intranetsite wordt bereikt. Deze site, die eerder niet bereikbaar was omdat de gebruiker extern was, is nu toegankelijk.

### <a name="before-you-start"></a>Voordat u begint

- Stel de interne toepassingen in via de toepassingsproxy van Azure AD.
  - Raadpleeg [deze documentatie](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy) voor het configureren van de toepassingsproxy en het publiceren van toepassingen. 
  - [Gebruikers moeten zijn toegewezen](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-add-on-premises-application#add-a-user-for-testing) aan de ondernemingstoepassing waarvoor de omleiding moet plaatsvinden. Dit moet ook gebeuren als de toepassing is ingesteld op de Doorvoermodus voor Verificatie vooraf, en als de vereiste voor gebruikerstoewijzing is uitgeschakeld in de instellingen voor de toepassingsproxy.
- U moet minimaal versie 1.2.0 van de Managed Browser-app gebruiken.
- Er is een [beleid voor app-beveiliging van Intune](app-protection-policy.md) toegewezen aan de Managed Browser- of Microsoft Edge-app.

    > [!NOTE]
    > Het kan tot 24 uur duren voordat bijgewerkte omleidingsgegevens voor de toepassingsproxy worden doorgevoerd in Managed Browser en Microsoft Edge.


#### <a name="step-1-enable-automatic-redirection-to-a-protected-browser-from-outlook"></a>Stap 1: schakel automatische omleiding naar een beveiligde browser vanuit Outlook in
Outlook moet zijn geconfigureerd met een beleid voor app-beveiliging waarmee de instelling **Webinhoud beperken voor weergave in de Managed Browser** beschikbaar komt.

#### <a name="step-2-assign-an-app-configuration-policy-assigned-for-the-protected-browser"></a>Stap 2: wijs een app-configuratiebeleid toe voor de beveiligde browser
Met deze procedure wordt de Managed Browser- of Microsoft Edge-app geconfigureerd voor omleiding via een proxy. 

Open het tabblad **Edge** in de configuratie-instellingen voor het beleid en selecteer **Inschakelen** voor de omleidingswaarde van de toepassingsproxy. Als u deze instelling inschakelt, krijgen gebruikers toegang tot zakelijke koppelingen en on-premises web-apps die zijn gepubliceerd via de Azure-toepassingsproxy.

Voor meer informatie over het gecombineerde gebruik van Managed Browser, Microsoft Edge en de Azure AD-toepassingsproxy voor naadloze (en beveiligde) toegang tot on-premises web-apps, raadpleegt u de blogpost voor Enterprise Mobility + Security [Better together: Intune and Azure Active Directory team up to improve user access](https://cloudblogs.microsoft.com/enterprisemobility/2017/07/06/better-together-intune-and-azure-active-directory-team-up-to-improve-user-access). (Beter samen: Intune en Azure Active Directory werken samen om de toegang voor gebruikers te verbeteren.)

## <a name="how-to-configure-the-homepage-for-a-protected-browser"></a>Startpagina configureren voor een beveiligde browser

Met deze instelling kunt u de startpagina configureren die gebruikers zien wanneer ze de een beveiligde browser starten of een nieuw tabblad maken. 
- Deze instelling wordt weergegeven op de webpagina in Managed Browser.  Edge geeft in plaats daarvan een snelkoppeling naar de startpagina weer.
- Het snelkoppelingspictogram naar de startpagina verschijnt als pictogram onder het besturingselement voor zoeken.  Het kan niet worden bewerkt of verwijderd.
- De snelkoppeling naar de startpagina geeft de naam van uw organisatie weer om deze te onderscheiden.  Deze verschijnt altijd als het eerste pictogram.

Geef met de procedure voor het maken van een app-configuratie voor Microsoft Edge of Managed Browser het volgende sleutel-waardepaar op:

|                                Sleutel                                |                                                           Waarde                                                            |
|-------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------|
| <strong>com.microsoft.intune.mam.managedbrowser.homepage</strong> | Geef een geldige URL op. Uit veiligheidsoogpunt worden onjuiste URL's geblokkeerd.<br>Voorbeeld: `https://www.bing.com` |

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
|U kunt kiezen uit:<br><ul><li>Geef toegestane URL's op (alleen deze URL's zijn toegestaan; andere sites zijn niet toegankelijk):<br> **com.microsoft.intune.mam.managedbrowser.AllowListURLs**<br><br></li><li>Geef geblokkeerde URL's op (alle andere sites zijn toegankelijk):<br>**com.microsoft.intune.mam.managedbrowser.BlockListURLs**</li></ul>|De overeenkomstige waarde voor de sleutel is een lijst met URL's. U voert alle URL's die u wilt toestaan of blokkeren in als één waarde, gescheiden door een sluisteken **&#124;** .<br><br>Voorbeelden:<br><br><code>URL1&#124;URL2&#124;URL3</code><br><code>http://*.contoso.com/*&#124;https://*.bing.com/*&#124;https://expenses.contoso.com</code>|

>[!IMPORTANT]
>Geef niet beide sleutels op. Als beide sleutels zijn bedoeld voor dezelfde gebruiker, moet de sleutel voor toegestane URL's worden gebruikt, aangezien dit de meest beperkende optie is.
>Controleer ook dat geen belangrijke pagina's worden geblokkeerd, zoals de website van uw bedrijf.

### <a name="url-format-for-allowed-and-blocked-urls"></a>URL-indeling voor toegestane en geblokkeerde URL´s
Gebruik de volgende gegevens voor meer informatie over de toegestane indelingen en jokertekens die u kunt gebruiken bij het opgeven van URL's in de lijsten met toegestane en geblokkeerde websites:

- U kunt het jokerteken ( **&#42;** ) gebruiken volgens de regels in de onderstaande lijst met toegestane patronen.

- Zorg ervoor dat u alle URL's voorziet van het voorvoegsel **http** of **https** wanneer u ze in de lijst invoert.

- U kunt poortnummers in het adres opgeven. Als u geen poortnummer opgeeft, worden deze waarden gebruikt:

  - Poort 80 voor http

  - Poort 443 voor https

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
  
## <a name="soft-transitions-from-work-to-personal-accounts"></a>Tijdelijke overgangen van zakelijke naar persoonlijke accounts

De hoeksteen van de zakelijke Microsoft Edge-versie voor mobiel is het model voor dubbele identiteiten, wat betekent dat Microsoft Edge zowel zakelijke als persoonlijke identiteiten ondersteunt. Net als bij de Office 365- en Outlook-apps kunnen eindgebruikers met dit model voor dubbele identiteiten Microsoft Edge gebruiken voor al hun browserbehoeften, en kunnen ze eenvoudig tussen de twee versies schakelen op basis van het inhoudsbeleid dat is gedefinieerd door de beheerder. Browsen in de persoonlijke context wordt niet beïnvloed en bedrijfsinformatie wordt volledig opgeslagen in de werkcontext van Microsoft Edge. 

Een van de voordelen van dit model is dat wanneer gebruikers een koppeling willen openen (zoals een nieuwsartikel, enzovoort) naar een site die niet is toegestaan in uw organisatie, ze dit in hun persoonlijke context wél kunnen doen, omdat deze volledig gescheiden is van de werkcontext. Deze tijdelijke overgangen zijn standaard ingeschakeld. 

Geef met de procedure voor het maken van een app-configuratie voor Microsoft Edge of Managed Browser het volgende sleutel-waardepaar op:

| Sleutel                                                                | Waarde                                                 |
|--------------------------------------------------------------------|-------------------------------------------------------|
| **com.microsoft.intune.mam.managedbrowser.AllowTransitionOnBlock** | Bij **Onwaar** zijn deze tijdelijke overgangen geblokkeerd |

## <a name="how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios"></a>Toegang tot logboeken van beheerde apps met Managed Browser in iOS

Eindgebruikers bij wie Managed Browser is geïnstalleerd op hun iOS-/iPadOS-apparaat, kunnen de beheerstatus van alle gepubliceerde Microsoft-apps bekijken. Ze kunnen logboeken versturen om problemen met hun beheerde iOS-/iPadOS-apps op te lossen.

1. Open **Instellingen** voor iOS/iPadOS.
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

- Managed Browser gebruikt geen instellingen die gebruikers maken voor de ingebouwde browser op hun apparaten. Managed Browser heeft geen toegang tot deze instellingen.

- Als u de optie **Eenvoudige pincode vereist voor toegang** of **Bedrijfsreferenties vereist voor toegang** configureert in een beleid voor app-beveiliging dat is gekoppeld aan Managed Browser, en een gebruiker de Help-koppeling op de verificatiepagina selecteert, kan de gebruiker elke internetsite bezoeken ongeacht of deze is toegevoegd aan de lijst met geblokkeerde websites in het beleid.

- Managed Browser kan alleen toegang tot sites blokkeren wanneer de sites rechtstreeks worden geopend. De app kan niet de toegang blokkeren als er tussenliggende services (zoals een vertaalservice) worden gebruikt voor toegang tot de site.

- Om verificatie en toegang tot de Intune-documentatie toe te staan, wordt **&#42;.microsoft.com** uitgesloten van opname in lijsten met toegestane en geblokkeerde sites. Dit domein is altijd toegestaan.

### <a name="turn-off-usage-data"></a>Gebruiksgegevens uitschakelen
Microsoft verzamelt automatisch anonieme gegevens over de prestaties en het gebruik van Managed Browser om Microsoft-producten en -services te verbeteren. Gebruikers kunnen het verzamelen van deze gegevens uitschakelen met de instelling **Gebruiksgegevens** op hun apparaten. U hebt geen controle over het verzamelen van deze gegevens.

- Op iOS-/iPadOS-apparaten kunnen gebruikers geen websites openen met een verlopen of niet-vertrouwd certificaat.

## <a name="next-steps"></a>Volgende stappen

- [Wat zijn beleidsregels voor de beveiliging van apps?](app-protection-policy.md) 
