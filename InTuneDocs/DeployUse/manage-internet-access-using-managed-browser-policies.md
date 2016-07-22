---
# required metadata

title: Internettoegang beheren met beheerde-browserbeleid | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: dc946303-e09b-4d73-8bf4-87742299bc54

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Internettoegang beheren met beheerde-browserbeleid met Microsoft Intune
De beheerde browser is een toepassing voor websurfen die u in uw organisatie kunt implementeren met behulp van Microsoft Intune. Een beheerde-browserbeleid bevat een lijst met toegestane of een lijst met geblokkeerde websites waarmee de websites die gebruikers van de beheerde browser kunnen bezoeken, worden beperkt.

Omdat dit een beheerde app is, kunt u ook Mobile Application Management-beleidsregels toepassen op de app, zoals het gebruik van knippen, kopiëren en plakken beheren, schermafdrukken verhinderen, en ervoor zorgen dat koppelingen naar inhoud waarop gebruikers klikken, alleen in andere beheerde apps wordt geopend. Zie [Mobile Application Management-beleid configureren en implementeren in de Microsoft Intune-console](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) voor meer informatie..

> [!IMPORTANT]
>Als gebruikers de beheerde browser uit de App Store installeren en deze niet wordt beheerd door Intune, geldt het volgende gedrag:
iOS: de beheerde-browser-app kan worden gebruikt als een eenvoudige webbrowser, maar sommige functies zijn niet beschikbaar en het is niet mogelijk om toegang te krijgen tot gegevens uit andere door Intune beheerde apps.
Android: de beheerde-browser-app kan niet worden gebruikt.
Als gebruikers de beheerde browser zelf installeren op een iOS-apparaat met een versie die lager is dan iOS 9, wordt deze niet beheerd door ander beleid dat u maakt. Om ervoor te zorgen dat de browser wordt beheerd door Intune, moeten ze de app verwijderen voordat u deze als beheerde app voor hun kunt implementeren. Als de gebruiker de beheerde browser zelf installeert in iOS 9 of hoger, wordt deze gevraagd om toe te staan dat de browser wordt beheerd door beleid.

U kunt beheerde-browserbeleidsregels maken voor de volgende typen apparaten:

-   Apparaten met Android 4 en hoger

-   Apparaten met iOS 7.1 en hoger

De beheerde browser van Intune ondersteunt het openen van webinhoud van [Microsoft Intune-toepassingspartners](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx)..

## Een beheerde-browserbeleid maken

1.  Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) op **Beleid** &gt; **Beleid toevoegen**..

2.  Configureer een van de volgende **Software** -beleidstypen:

    -   **Beheerde-browserbeleid (Android 4 en hoger)**

    -   **Managed Browser-beleid (iOS 7.1 en hoger)**

    Zie [Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) voor informatie over het maken en implementeren van beleid.

3.  Met de volgende tabel kunt u de instellingen voor beheerde-browserbeleid configureren:

|Naam van de instelling|Details|
    |----------------|--------------------|
    |**Naam**|Geef een unieke naam op voor het beheerde-browserbeleid om het in de Intune-console te herkennen.|
    |**Beschrijving**|Geef een beschrijving op die een overzicht geeft van het beheerde-browserbeleid en overige relevante informatie die u helpt bij het zoeken.|
    |**Een lijst met toegestane of geblokkeerde websites inschakelen om de URL's te beperken die door de beheerder browser kunnen worden geopend**|Selecteer een van de volgende opties:<br /><br />**De beheerde browser mag alleen de hieronder vermelde URL's openen**: hiermee geeft u een lijst op met de URL's die door de beheerde browser kunnen worden geopend.<br /><br />**De beheerde browser mag de hieronder vermelde URL's niet openen**: hiermee geeft u een lijst op met URL's die niet door de beheerde browser kunnen worden geopend. **Opmerking:** in hetzelfde beheerde-browserbeleid kunt u niet zowel toegestane als geblokkeerde URL's opnemen.<br />Zie **URL-indeling voor toegestane en geblokkeerde URL's** in dit onderwerp voor meer informatie over de URL-indelingen die u kunt opgeven.|

4.  Wanneer u klaar bent, klikt u op **Beleid opslaan**..

Het nieuwe beleid wordt weergegeven in het knooppunt **Configuratiebeleid** van de werkruimte **Beleid** .

## Een implementatie voor de beheerde-browser-app maken
Nadat u het beheerde-browserbeleid hebt gemaakt, kunt u een software-implementatie voor de beheerde-browserapp maken en deze koppelen aan het beheerde-browserbeleid dat u hebt gemaakt.

> [!IMPORTANT]
> Beheerde-browserbeleidsregels worden niet op dezelfde wijze geïmplementeerd als andere Intune-beleidsregels. Dit type beleid moet worden gekoppeld aan het beheerde-browsersoftwarepakket.

Implementeer de app, waarbij u ervoor zorgt dat u het beheerde-browserbeleid selecteert op de pagina **Mobiel appbeheer** om het beleid te koppelen aan de app.

Zie [Apps implementeren in Microsoft Intune](deploy-apps-in-microsoft-intune.md) voor meer informatie over het implementeren van apps..

## Beveiliging en privacy voor de beheerde browser

-   Op iOS-apparaten kunnen geen websites worden geopend die worden bezocht door gebruikers met een verlopen of niet-vertrouwd certificaat.

-   Instellingen door gebruikers voor de ingebouwde browser op hun apparaten, worden niet gebruikt door de beheerde browser. Dit komt doordat de beheerde browser geen toegang tot deze instellingen heeft.

-   Als u de opties **Eenvoudige pincode vereist voor toegang** of **Bedrijfsreferenties vereist voor toegang** configureert in een Mobile Application Management-beleid dat is gekoppeld aan de beheerde browser, en een gebruiker klikt op de Help-koppeling op de verificatiepagina, kan de gebruiker elke internetsite bezoeken ongeacht of deze is toegevoegd aan een lijst met geblokkeerde websites in het beheerde-browserbeleid.

-   De beheerde browser kan alleen toegang tot sites blokkeren wanneer de sites rechtstreeks worden geopend. De browser kan geen toegang blokkeren als er tussenliggende services (zoals een vertaalservice) worden gebruikt voor toegang tot de site.

-   Om verificatie toe te staan en ervoor te zorgen dat de Intune-documentatie toegankelijk is, is **&#42;.microsoft.com** uitgesloten van vermelding in lijsten met toegestane en geblokkeerde instellingen; dit domein is altijd toegestaan.

### Gebruiksgegevens uitschakelen
Microsoft verzamelt automatisch anonieme gegevens over de prestaties en het gebruik van de beheerde browser om Microsoft-producten en -services te verbeteren. Gebruikers kunnen het verzamelen van gegevens uitschakelen via de instelling **Gebruiksgegevens** op hun apparaat. U hebt geen controle over het verzamelen van deze gegevens.

## Referentiegegevens

### URL-indeling voor toegestane en geblokkeerde URL´s
Gebruik de volgende gegevens voor meer informatie over de toegestane indelingen en jokertekens die u kunt gebruiken bij het opgeven van URL's in de lijsten met toegestane en geblokkeerde websites.

-   U kunt het jokerteken '**&#42;**' gebruiken volgens de regels in de lijst met toegestane patronen hieronder.

-   Zorg ervoor dat u alle URL's voorziet van het voorvoegsel **http** of **https** wanneer u ze in de lijst invoert.

-   U kunt poortnummers in het adres opgeven. Als u geen poortnummer opgeeft, zijn de gebruikte waarden:

    -   Poort 80 voor http

    -   Poort 443 voor https

    Het gebruik van jokertekens voor het poortnummer wordt niet ondersteund, bijvoorbeeld **http://www.contoso.com:*;** en **http://www.contoso.com: /*;**

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

### Conflicten tussen de lijst met toegestane en de lijst met geblokkeerde websites oplossen
Als er meerdere beheerde-browserbeleidsregels zijn geïmplementeerd op een apparaat en de instellingen conflicteren, worden de modus (toestaan of blokkeren) en de URL-lijsten geëvalueerd op conflicten. Bij een conflict geldt het volgende gedrag:

-   Als de modi in elke beleidsregel hetzelfde zijn maar de URL-lijsten verschillen, worden de URL's niet afgedwongen op het apparaat.

-   Als de modi in elke beleidsregel verschillen maar de URL-lijsten hetzelfde zijn, worden de URL's niet afgedwongen op het apparaat.

-   Als een apparaat voor de eerste keer beheerde-browserbeleidsregels ontvangt en twee beleidsregels conflicteren, worden de URL's niet afgedwongen op het apparaat. Gebruik het knooppunt **Conflicterende beleidsinstellingen** knooppunt van de werkruimte **Beleid** om de conflicten weer te geven.

-   Als een apparaat al een beheerde-browserbeleid heeft ontvangen en er een tweede beleid met conflicterende instellingen wordt geïmplementeerd, blijven de oorspronkelijke instellingen op het apparaat. Gebruik het knooppunt **Conflicterende beleidsinstellingen** knooppunt van de werkruimte **Beleid** om de conflicten weer te geven.


<!--HONumber=May16_HO1-->


