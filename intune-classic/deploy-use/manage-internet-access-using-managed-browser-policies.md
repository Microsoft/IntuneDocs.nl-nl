---
title: Webtoegang beheren met de Managed Browser
description: De toepassing van de beheerde browser implementeren om websurfen en de overdracht van webgegevens naar andere apps te beperken.
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 05/10/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dc946303-e09b-4d73-8bf4-87742299bc54
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 559866fff63b0ad77a43ce337adede5cd8b27302
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="manage-internet-access-using-managed-browser-policies-with-microsoft-intune"></a>Internettoegang beheren met beheerde-browserbeleid met Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

De beheerde browser is een browsertoepassing die u in uw organisatie kunt implementeren met Microsoft Intune. Een beheerde-browserbeleid bevat een lijst met toegestane of een lijst met geblokkeerde websites waarmee de websites die gebruikers van de beheerde browser kunnen bezoeken, worden beperkt.

Omdat deze app is geïntegreerd met de Intune SDK, kunt u ook app-beveiligingsbeleid toepassen op de app. Met de beleidsregels kan bijvoorbeeld het gebruik van knippen, kopiëren en plakken worden beperkt, het maken van schermafdrukken worden geblokkeerd, en worden ingesteld dat koppelingen naar inhoud uitsluitend worden geopend in andere beheerde apps. Zie [Mobile Application Management-beleid configureren en implementeren in de Microsoft Intune-console](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) voor meer informatie.

>[!IMPORTANT]
>De app Managed Browser zal alleen Intune-beleid voor de beveiliging van apps ophalen en toepassen wanneer een andere app op het apparaat app-beveiligingsbeleid heeft opgehaald.<br><br> Als gebruikers de beheerde browser uit de App Store installeren en deze niet door Intune wordt beheerd, geldt ook het volgende gedrag:<br /><br />
>**iOS**: de app Managed Browser kan worden gebruikt als een eenvoudige webbrowser. Sommige functies zijn echter niet beschikbaar en het is niet mogelijk om toegang te krijgen tot gegevens uit andere met Intune beheerde apps.<br />
**Android**: de app Managed Browser kan niet worden gebruikt.<br /><br />
Als gebruikers de beheerde browser zelf installeren op een iOS-apparaat met een versie die lager is dan iOS 9, wordt deze browser niet beheerd door enig beleid dat u maakt. Om ervoor te zorgen dat Intune de browser beheert, moeten ze de app eerst verwijderen, waarna u deze als beheerde app kunt implementeren. Als de gebruiker de beheerde browser zelf installeert in iOS 9 of hoger, wordt de gebruiker gevraagd om toe te staan dat de browser wordt beheerd door beleid.

U kunt beheerde-browserbeleidsregels maken voor de volgende typen apparaten:

-   Apparaten met Android 4 en hoger

-   Apparaten met iOS 8.0 en hoger

De beheerde browser van Intune ondersteunt het openen van webinhoud van [Microsoft Intune-toepassingspartners](https://www.microsoft.com/server-cloud/products/microsoft-intune/partners.aspx).

## <a name="create-a-managed-browser-policy"></a>Een beheerde-browserbeleid maken

1.  Ga naar de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) en kies**Beleid** &gt; **Beleid toevoegen**.

2.  Configureer een van de volgende **Software** -beleidstypen:

    -   **Beheerde browser (Android 4 en hoger)**

    -   **Beheerde browser (iOS 8.0 en hoger)**

    Zie [Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) voor informatie over het maken en implementeren van beleid.

3.  Met de volgende informatie kunt u de instellingen voor beheerde-browserbeleid configureren:

    - **Naam**. Geef een unieke naam op voor het beheerde-browserbeleid om het in de Intune-console te herkennen.
    - **Beschrijving**. Geef een beschrijving op die een overzicht geeft van het beheerde-browserbeleid en overige relevante informatie die u helpt bij het zoeken.
    - **Een lijst met toegestane of geblokkeerde websites inschakelen om de URL's te beperken die door de beheerder browser kunnen worden geopend**. Selecteer een van de volgende opties:
        - **Toestaan dat de beheerde browser alleen de onderstaande URL's opent**. Hier geeft u een lijst met URL’s op die de beheerde browser kan openen.
        - **Niet toestaan dat de beheerde browser de onderstaande URL's opent**. Hier geeft u een lijst met URL’s op die de beheerde browser niet kan openen.
**Opmerking:** in hetzelfde beheerde-browserbeleid kunt u niet zowel toegestane als geblokkeerde URL's opnemen.
Zie **URL-indeling voor toegestane en geblokkeerde URL's** in dit onderwerp voor meer informatie over de URL-indelingen die u kunt opgeven.

4.  Als u klaar bent, kiest u **Beleid opslaan**.

Het nieuwe beleid wordt weergegeven in het knooppunt **Configuratiebeleid** van de werkruimte **Beleid**.

## <a name="create-a-deployment-for-the-managed-browser-app"></a>Een implementatie voor de beheerde-browser-app maken
Nadat u het beheerde-browserbeleid hebt gemaakt, kunt u een software-implementatie voor de beheerde-browserapp maken en deze koppelen aan het beheerde-browserbeleid dat u hebt gemaakt.

> [!IMPORTANT]
> Beheerde-browserbeleidsregels worden niet op dezelfde wijze geïmplementeerd als andere Intune-beleidsregels. Dit type beleid moet worden gekoppeld aan het beheerde-browsersoftwarepakket.

Implementeer de app, waarbij u ervoor zorgt dat u het beheerde-browserbeleid selecteert op de pagina **Mobiel appbeheer** om het beleid te koppelen aan de app.

Zie [Apps implementeren in Microsoft Intune](deploy-apps-in-microsoft-intune.md) voor meer informatie over het implementeren van apps.

## <a name="security-and-privacy-for-the-managed-browser"></a>Beveiliging en privacy voor de beheerde browser

-   Op iOS-apparaten kunnen gebruikers geen websites openen met een verlopen of niet-vertrouwd certificaat.

-   De beheerde browser gebruikt geen instellingen die gebruikers maken voor de ingebouwde browser op hun apparaten. Dit komt doordat de beheerde browser geen toegang tot deze instellingen heeft.

-   Als u de optie **Eenvoudige pincode vereist voor toegang** of **Bedrijfsreferenties vereist voor toegang** configureert in een Mobile Application Management-beleid dat is gekoppeld aan de beheerde browser, en een gebruiker de Help-koppeling op de verificatiepagina selecteert, kan de gebruiker elke internetsite bezoeken ongeacht of deze is toegevoegd aan een lijst met geblokkeerde websites in het beheerde-browserbeleid.

-   De beheerde browser kan alleen toegang tot sites blokkeren wanneer de sites rechtstreeks worden geopend. De browser kan geen toegang blokkeren als er tussenliggende services (zoals een vertaalservice) worden gebruikt voor toegang tot de site.

-   Om verificatie toe te staan en ervoor te zorgen dat de Intune-documentatie toegankelijk is, is **&#42;.microsoft.com** uitgesloten van vermelding in lijsten met toegestane en geblokkeerde instellingen. Dit domein is altijd toegestaan.

### <a name="turn-off-usage-data"></a>Gebruiksgegevens uitschakelen
Microsoft verzamelt automatisch anonieme gegevens over de prestaties en het gebruik van de beheerde browser om Microsoft-producten en -services te verbeteren. Gebruikers kunnen het verzamelen van deze gegevens uitschakelen met de instelling **Gebruiksgegevens** op hun apparaten. U hebt geen controle over het verzamelen van deze gegevens.

## <a name="reference-information"></a>Referentiegegevens

### <a name="url-format-for-allowed-and-blocked-urls"></a>URL-indeling voor toegestane en geblokkeerde URL´s
Gebruik de volgende gegevens voor meer informatie over de toegestane indelingen en jokertekens die u kunt gebruiken bij het opgeven van URL's in de lijsten met toegestane en geblokkeerde websites:

-   U kunt het jokerteken '**&#42;**' gebruiken volgens de regels in de volgende lijst met toegestane patronen.

-   Zorg ervoor dat u alle URL's voorziet van het voorvoegsel **http** of **https** wanneer u ze in de lijst invoert.

-   U kunt poortnummers in het adres opgeven. Als u geen poortnummer opgeeft, zijn de gebruikte waarden:

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
    |http://www.contoso.com:80|Komt overeen met één pagina, met gebruik van een poortnummer|http://www.contoso.com:80||
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

### <a name="how-conflicts-between-the-allow-and-block-list-are-resolved"></a>Conflicten tussen de lijst met toegestane en de lijst met geblokkeerde websites oplossen
Als er meerdere beheerde-browserbeleidsregels zijn geïmplementeerd op een apparaat en de instellingen conflicteren, worden de modus (toestaan of blokkeren) en de URL-lijsten geëvalueerd op conflicten. Bij een conflict geldt het volgende gedrag:

-   Als de modi in elke beleidsregel hetzelfde zijn maar de URL-lijsten verschillen, worden de URL's niet afgedwongen op het apparaat.

-   Als de modi in elke beleidsregel verschillen maar de URL-lijsten hetzelfde zijn, worden de URL's niet afgedwongen op het apparaat.

-   Als een apparaat voor de eerste keer beheerde-browserbeleidsregels ontvangt en twee beleidsregels conflicteren, worden de URL's niet afgedwongen op het apparaat. Gebruik het knooppunt **Conflicterende beleidsinstellingen** knooppunt van de werkruimte **Beleid** om de conflicten weer te geven.

-   Als een apparaat al een beheerde-browserbeleid heeft ontvangen en er een tweede beleid met conflicterende instellingen wordt geïmplementeerd, blijven de oorspronkelijke instellingen op het apparaat. Gebruik het knooppunt **Conflicterende beleidsinstellingen** knooppunt van de werkruimte **Beleid** om de conflicten weer te geven.
