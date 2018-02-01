---
title: Webtoegang beheren met de app Managed Browser
titlesuffix: Azure portal
description: De app Managed browser implementeren om websurfen en de overdracht van webgegevens naar andere apps te beperken.
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1feca24f-9212-4d5d-afa9-7c171c5e8525
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 613099d1d30a8be3787bd0004a376302da3dc231
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="manage-internet-access-using-managed-browser-policies-with-microsoft-intune"></a>Internettoegang beheren met beleid van de app Managed Browser en Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

De app Managed Browser is een app om te browsen op het web die u voor gebruik in uw organisatie kunt downloaden in vrij toegankelijke App Stores. Als u Managed Browser configureert met Intune, biedt de app deze mogelijkheden:
- Toegang tot bedrijfssites en SaaS-apps met eenmalige aanmelding via de MyApps-service, met beveiliging van de webgegevens.
- Vooraf geconfigureerd met een lijst met URL's en domeinen om te beperken naar welke sites de gebruiker in de zakelijke context kan navigeren.
- Vooraf geconfigureerd met een startpagina en bladwijzers die u opgeeft.

Aangezien deze app is geïntegreerd met de Intune SDK, kunt u ook beleid voor app-beveiliging toepassen op de app, waaronder:
- Beperkingen voor het knippen, kopiëren en plakken van gegevens
- Voorkomen dat er schermopnamen worden gemaakt
- Afdwingen dat koppelingen naar inhoud die gebruikers selecteren uitsluitend worden geopend in andere beheerde apps.

Zie [Wat is beveiligingsbeleid voor apps?](/intune/app-protection-policy) voor meer informatie.

U kunt deze instellingen toepassen op:

- Apparaten die zijn ingeschreven bij Intune
- Apparaten die zijn ingeschreven bij een ander MDM-product
- Niet-beheerde apparaten

Als gebruikers Managed Browser vanuit de app store installeren en deze niet door Intune wordt beheerd, kunt u deze gebruiken als een eenvoudige webbrowser met ondersteuning voor eenmalige aanmelding via de site Microsoft MyApps. Gebruikers worden direct doorgestuurd naar de MyApps-website, waar alle ingerichte SaaS-toepassingen worden weergegeven.
Hoewel Managed Browser niet wordt beheerd door Intune, kan de app geen gegevens gebruiken uit andere apps die wel door Intune worden beheerd. 

Managed Browser biedt geen ondersteuning voor versie 3 van het cryptografische protocol Secure Sockets Layer (SSLv3).

U kunt beleidsregels voor Managed Browser maken voor de volgende apparaattypen:

-   Apparaten met Android 4 en hoger

-   Apparaten met iOS 8.0 en hoger

>[!IMPORTANT]
>Vanaf oktober 2017 ondersteunt de app Intune Managed Browser voor Android alleen nog apparaten waarop Android 4.4 en hoger wordt uitgevoerd. De app Intune Managed Browser voor iOS ondersteunt alleen apparaten met iOS 9.0 en hoger.
>Oudere versies van Android en iOS kunnen Managed Browser nog steeds gebruiken, maar er kunnen geen nieuwe versies van de app op worden geïnstalleerd en kan er dus geen gebruik worden gemaakt van alle mogelijkheden van de app. U wordt aangeraden deze apparaten bij te werken tot een ondersteunde versie van het besturingssysteem.


Managed Browser van Intune ondersteunt het openen van webinhoud van [Microsoft Intune-toepassingspartners](https://www.microsoft.com/server-cloud/products/microsoft-intune/partners.aspx).

## <a name="create-a-managed-browser-app-configuration"></a>Een configuratie voor de Managed browser-app maken

1.  Meld u aan bij Azure-portal.
2.  Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3.  Ga in de lijst Beheren naar de blade **Mobile Apps** en kies **App-configuratiebeleid**.
4.  Kies **Toevoegen** op de blade **App-configuratiebeleid**.
5.  Geef op de blade **App-configuratiebeleid toevoegen** een **naam** en een optionele **beschrijving** op voor de app-configuratie-instellingen.
6.  Kies voor **Type apparaatregistratie** **Beheerde apps**.
7.  Kies **Vereiste apps selecteren** en kies vervolgens op de blade **Doel-apps** **Managed Browser** voor iOS, voor Android of voor beide besturingssystemen.
8.  Kies **OK** om terug te keren naar de blade **App-configuratiebeleid toevoegen**.
9.  Kies **Configuratie-instellingen**. Op de blade **Configuratie** definieert u sleutel- en waardeparen voor configuraties voor Managed Browser. Gebruik de secties verderop in dit artikel voor meer informatie over de verschillende sleutel- en waardeparen die u kunt definiëren.
10. Kies **OK** als u klaar bent.
11. Op de blade **App-configuratie toevoegen** kiest u **Maken**.
12. De nieuwe configuratie wordt gemaakt en weergegeven op de blade **App-configuratie**.

>[!IMPORTANT]
>Managed Browser is momenteel afhankelijk van automatische inschrijving. Om app-configuraties toe te passen, moet een andere toepassing op het apparaat al worden beheerd met beleid voor app-beveiliging van Intune.

## <a name="assign-the-configuration-settings-you-created"></a>De configuratie-instellingen toewijzen die u hebt gemaakt

U wijst de instellingen aan Azure AD-groepen gebruikers toe. Als deze gebruiker de app Managed Browser heeft geïnstalleerd, wordt de app beheerd door de instellingen die u hebt opgegeven.

1. Kies op de blade **Instellingen** van het Intune MAM-dashboard **App-configuratie**.
2. Selecteer in de lijst met app-configuraties de configuratie die u wilt toewijzen.
3. Kies **Gebruikersgroepen** op de volgende blade.
4. Selecteer op de blade **Gebruikersgroepen** de Azure AD-groep waaraan u de app-configuratie wilt toewijzen en kies vervolgens **OK**.


## <a name="how-to-configure-application-proxy-settings-for-the-managed-browser"></a>Application Proxy-instellingen configureren voor Managed Browser

De Intune-app Managed Browser en de [Azure AD-toepassingsproxy]( https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) kunnen samen worden gebruikt om de volgende scenario's te ondersteunen voor gebruikers van iOS- en Android-apparaten:

- Een gebruiker downloadt de Microsoft Outlook-app en meldt zich hierbij aan. Het beleid voor app-beveiliging van Intune wordt automatisch toegepast. Dit houdt in dat opgeslagen gegevens worden versleuteld en dat wordt voorkomen dat de gebruiker bestanden van het bedrijf overbrengt naar niet-beheerde apps of locaties op het apparaat. Wanneer de gebruiker vervolgens in Outlook klikt op een koppeling naar een intranetsite, kunt u instellen dat de koppeling wordt geopend in de Managed Browser-app en niet in een andere browser. De Managed Browser-app herkent dat deze intranetsite via de toepassingsproxy beschikbaar is gesteld aan de gebruiker. De gebruiker wordt automatisch omgeleid via de toepassingsproxy, voor meervoudige verificatie en voorwaardelijke toegang, voordat de intranetsite wordt bereikt. Deze site, die eerder niet bereikbaar was omdat de gebruiker extern was, is nu toegankelijk en de koppeling in Outlook werkt zoals verwacht.
- Een externe gebruiker opent de app Managed Browser en gaat naar een intranetsite met behulp van de interne URL. De Managed Browser-app herkent dat deze intranetsite via de toepassingsproxy beschikbaar is gesteld aan de gebruiker. De gebruiker wordt automatisch omgeleid via de toepassingsproxy, voor meervoudige verificatie en voorwaardelijke toegang, voordat de intranetsite wordt bereikt. Deze site, die eerder niet bereikbaar was omdat de gebruiker extern was, is nu toegankelijk.

### <a name="before-you-start"></a>Voordat u begint

- Stel de interne toepassingen in via de toepassingsproxy van Azure AD.
    - Raadpleeg [deze documentatie]( https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started#how-to-get-started) voor het configureren van de toepassingsproxy en het publiceren van toepassingen. 
- U moet minimaal versie 1.2.0 van de Managed Browser-app gebruiken.
- Er is een [beleid voor app-beveiliging van Intune]( app-protection-policy.md) toegewezen aan de Managed Browser-app.
Opmerking: Het kan tot 24 uur duren voordat bijgewerkte omleidingsgegevens voor de toepassingsproxy worden doorgevoerd in Managed Browser.

#### <a name="step-1-enable-automatic-redirection-to-the-managed-browser-from-outlook"></a>Stap 1: automatische omleiding naar Managed Browser vanuit Outlook inschakelen
Outlook moet zijn geconfigureerd met een beleid voor app-beveiliging waarmee de instelling **Webinhoud beperken voor weergave in de Managed Browser** beschikbaar komt.

#### <a name="step-2-assign-an-app-configuration-policy-assigned-for-the-managed-browser"></a>Stap 2: Een app-configuratiebeleid toewijzen voor de Managed Browser-app
Met deze procedure wordt de Managed Browser-app geconfigureerd voor omleiding via een proxy. Geef met behulp van de procedure voor het maken van een app-configuratie voor Managed Browser het volgende sleutel- en waardepaar op:

|||
|-|-|
|Sleutel|Waarde|
|**com.microsoft.intune.mam.managedbrowser.AppProxyRedirection**|**true**|


## <a name="how-to-configure-the-homepage-for-the-managed-browser"></a>Startpagina configureren voor Managed Browser

Met deze instelling kunt u de startpagina configureren die gebruikers zien wanneer ze de app Managed Browser starten of een nieuw tabblad maken. Geef met behulp van de procedure voor het maken van een app-configuratie voor Managed Browser het volgende sleutel- en waardepaar op:

|||
|-|-|
|Sleutel|Waarde|
|**com.microsoft.intune.mam.managedbrowser.homepage**|Geef een geldige URL op. Uit veiligheidsoogpunt worden onjuiste URL's geblokkeerd.<br>Voorbeeld: **https://www.bing.com**|


## <a name="how-to-configure-bookmarks-for-the-managed-browser"></a>Bladwijzers configureren voor Managed Browser

Met deze instelling kunt u een set bladwijzers configureren die beschikbaar zijn voor gebruikers van Managed Browser.

- Deze bladwijzers kunnen niet worden verwijderd of gewijzigd door gebruikers.
- Deze bladwijzers worden bovenaan de lijst weergegeven. Bladwijzers die gebruikers maken, worden onder deze bladwijzers weergegeven.
- Als u App Proxy-omleiding hebt ingeschakeld, kunt u App Proxy-webapps toevoegen met behulp van hun interne of externe URL.

Geef met behulp van de procedure voor het maken van een app-configuratie voor Managed Browser het volgende sleutel- en waardepaar op:

|||
|-|-|
|Sleutel|Waarde|
|**com.microsoft.intune.mam.managedbrowser.bookmarks**|De waarde voor deze configuratie is een lijst met bladwijzers. Elke bladwijzer bestaat uit de titel en de URL van de bladwijzer. Scheid de titel en een URL met het teken **&#124;**.<br><br>Voorbeeld: **Microsoft Bing&#124;https://www.bing.com**<br><br>Als u meerdere bladwijzers wilt configureren, typt u een dubbel scheidingsteken **&#124; &#124;** tussen de bladwijzers.<br><br>Voorbeeld: **Bing&#124;https://www.bing.com&#124;&#124;Contoso&#124;https://www.contoso.com**|

## <a name="how-to-specify-allowed-and-blocked-urls-for-the-managed-browser"></a>Toegestane en geblokkeerde URL's voor Managed Browser opgeven

Geef met behulp van de procedure voor het maken van een app-configuratie voor Managed Browser het volgende sleutel- en waardepaar op:

|||
|-|-|
|Sleutel|Waarde|
|U kunt kiezen uit:<br><br>- Geef toegestane URL's op (alleen deze URL's zijn toegestaan; andere sites zijn niet toegankelijk): **com.microsoft.intune.mam.managedbrowser.AllowListURLs**<br><br>- Geef geblokkeerde URL's op (alle andere sites zijn toegankelijk): <br><br>**com.microsoft.intune.mam.managedbrowser.BlockListURLs**|De overeenkomstige waarde voor de sleutel is een lijst met URL's. U voert alle URL's die u wilt toestaan of blokkeren in als één waarde, gescheiden door een sluisteken **&#124;**.<br><br>Voorbeelden:<br><br>**URL1&#124;URL2&#124;URL3**<br>**http://*.contoso.com/*&#124;https://*.bing.com/*&#124;https://expenses.contoso.com**|

>[!IMPORTANT]
>Geef niet beide sleutels op. Als beide sleutels zijn bedoeld voor dezelfde gebruiker, moet de sleutel voor toegestane URL's worden gebruikt, aangezien dit de meest beperkende optie is.
>Controleer ook dat geen belangrijke pagina's worden geblokkeerd, zoals de website van uw bedrijf.

### <a name="url-format-for-allowed-and-blocked-urls"></a>URL-indeling voor toegestane en geblokkeerde URL´s
Gebruik de volgende gegevens voor meer informatie over de toegestane indelingen en jokertekens die u kunt gebruiken bij het opgeven van URL's in de lijsten met toegestane en geblokkeerde websites:

-   U kunt het jokerteken (**&#42;**) gebruiken volgens de regels in de onderstaande lijst met toegestane patronen.

-   Zorg ervoor dat u alle URL's voorziet van het voorvoegsel **http** of **https** wanneer u ze in de lijst invoert.

-   U kunt poortnummers in het adres opgeven. Als u geen poortnummer opgeeft, worden deze waarden gebruikt:

    -   Poort 80 voor http

    -   Poort 443 voor https

    Het gebruik van jokertekens voor het poortnummer wordt niet ondersteund. **http&colon;//www&period;contoso&period;com:*;** en **http&colon;//www&period;contoso&period;com: /*;** worden bijvoorbeeld niet ondersteund.

-   Gebruik de volgende tabel voor meer informatie over de toegestane patronen die u kunt gebruiken wanneer u een URL opgeeft:

|URL|Details|Komt overeen met|Komt niet overeen met|
|-------|---------------|-----------|------------------|
|http://www.contoso.com|Komt overeen met één pagina|www.contoso.com|host.contoso.com<br /><br />www.contoso.com/images<br /><br />contoso.com/|
|http://contoso.com|Komt overeen met één pagina|contoso.com/|host.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com|
|http://www.contoso.com/&#42;|Komt overeen met alle URL's die beginnen met www.contoso.com|www.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com/videos/tvshows|host.contoso.com<br /><br />host.contoso.com/images|
|http://&#42;.contoso.com/&#42;|Komt overeen met alle subdomeinen onder contoso.com|developer.contoso.com/resources<br /><br />news.contoso.com/images<br /><br />news.contoso.com/videos|contoso.host.com|
|http://www.contoso.com/images|Komt overeen met een afzonderlijke map|www.contoso.com/images|www.contoso.com/images/dogs|
|http://www.contoso.com:80|Komt overeen met één pagina, met gebruik van een poortnummer|http://www.contoso.com:80|
|https://www.contoso.com|Komt overeen met een enkele, beveiligde pagina|https://www.contoso.com|http://www.contoso.com|
|http://www.contoso.com/images/&#42;|Komt overeen met een enkele map en alle submappen|www.contoso.com/images/dogs<br /><br />www.contoso.com/images/cats|www.contoso.com/videos|

-   Hier volgen enkele voorbeelden van een aantal invoerwaarden die u niet kunt opgeven:

    -   &#42;.com

    -   &#42;.contoso/&#42;

    -   www.contoso.com/&#42;images

    -   www.contoso.com/&#42;images&#42;pigs

    -   www.contoso.com/page&#42;

    -   IP-adressen

    -   https://&#42;

    -   http://&#42;

    -   http://www.contoso.com:&#42;

    -   http://www.contoso.com: /&#42;

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
-   Managed Browser gebruikt geen instellingen die gebruikers maken voor de ingebouwde browser op hun apparaten. Managed Browser heeft geen toegang tot deze instellingen.

-   Als u de optie **Eenvoudige pincode vereist voor toegang** of **Bedrijfsreferenties vereist voor toegang** configureert in een beleid voor app-beveiliging dat is gekoppeld aan Managed Browser, en een gebruiker de Help-koppeling op de verificatiepagina selecteert, kan de gebruiker elke internetsite bezoeken ongeacht of deze is toegevoegd aan de lijst met geblokkeerde websites in het beleid.

-   Managed Browser kan alleen toegang tot sites blokkeren wanneer de sites rechtstreeks worden geopend. De app kan niet de toegang blokkeren als er tussenliggende services (zoals een vertaalservice) worden gebruikt voor toegang tot de site.

-   Om verificatie en toegang tot de Intune-documentatie toe te staan, wordt **&#42;.microsoft.com** uitgesloten van opname in lijsten met toegestane en geblokkeerde sites. Dit domein is altijd toegestaan.

### <a name="turn-off-usage-data"></a>Gebruiksgegevens uitschakelen
Microsoft verzamelt automatisch anonieme gegevens over de prestaties en het gebruik van Managed Browser om Microsoft-producten en -services te verbeteren. Gebruikers kunnen het verzamelen van deze gegevens uitschakelen met de instelling **Gebruiksgegevens** op hun apparaten. U hebt geen controle over het verzamelen van deze gegevens.
