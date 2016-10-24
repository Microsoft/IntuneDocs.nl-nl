---
title: MAM-beleid configureren in de Intune-console | Microsoft Intune
description: "Aan de hand van Mobile Application Management-beleid in Microsoft Intune kunt u de functionaliteit van de door u geïmplementeerde apps aanpassen, zodat deze apps voldoen aan het beleid van uw bedrijf met betrekking tot naleving en beveiliging."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 09/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b4fb33a8-a2fa-4353-bd89-5bda48b68e83
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d9e08429fb6c834476fd0029d559059c5132afca
ms.openlocfilehash: a4ab7287b2328fccbea5203bbfe5d87cbfc912b8


---

# Mobile Application Management-beleid configureren en implementeren in de Microsoft Intune-console
Aan de hand van Mobile Application Management-beleid (MAM) in Microsoft Intune kunt u de functionaliteit van de door u geïmplementeerde apps aanpassen, zodat deze apps voldoen aan het beleid van uw bedrijf met betrekking tot naleving en beveiliging. U kunt bijvoorbeeld knip-, kopieer- en plakbewerkingen beperken in een beheerde app of een app configureren om alle webkoppelingen te openen binnen een beheerde browser.

Ondersteuning voor Mobile Application Management-beleid:

-   Apparaten met Android 4 en hoger.

-   Apparaten met iOS 8.0 en hoger.

> [!TIP]
> Mobile Application Management-beleid ondersteunt apparaten die zijn ingeschreven met Intune.
>
> Als u informatie zoekt over het maken van beleid voor het beheer van apps voor apparaten die niet worden beheerd door Intune, raadpleegt u [App-gegevens beschermen met Mobile Application Management-beleid van Microsoft Intune](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).

In tegenstelling tot ander beleid van Intunes hoeft u Mobile Application Management-beleid niet rechtstreeks te implementeren. In plaats daarvan koppelt u het beleid aan de app die u wilt beperken. Wanneer de app op apparaten is geïmplementeerd en geïnstalleerd, zullen de instellingen die u opgeeft, in werking treden.

Als u beperkingen wilt toepassen op een app, moet de app gebruikmaken van de Microsoft Intune App SDK. Er zijn drie methoden om dit type app te verkrijgen:

-   **Een door beleid beheerde app gebruiken**. Een door beleid beheerde app beschikt over een ingebouwde App SDK. Om dit type app toe te voegen, geeft u een koppeling op naar de app uit een app store zoals iTunes store of Google Play. Er is geen verdere verwerking vereist voor dit type app. Bekijk de [lijst met apps die u met Mobile Application Management-beleid van Microsoft Intune kunt gebruiken](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).

-   **Een verpakte app gebruiken**. Een verpakte app is een app die samen met de App SDK wordt verpakt met behulp van Microsoft Intune App Wrapping Tool. Dit hulpprogramma wordt meestal gebruikt voor het verwerken van bedrijfsapps die intern zijn gemaakt. U kunt het niet gebruiken voor het verwerken van apps die zijn gedownload vanuit de app store. Zie voor meer informatie [iOS-apps voorbereiden voor Mobile Application Management met Microsoft Intune App Wrapping Tool](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) en [Android-apps voorbereiden voor Mobile Application Management met Microsoft Intune App Wrapping Tool](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md).

- **Uw eigen app ontwikkelen waarin de Intune App SDK is opgenomen**. Met de Intune App SDK kunt u app-beheerfuncties opnemen in een app terwijl u deze ontwikkelt. Zie [Overzicht van de Intune App SDK](/intune/develop/intune-app-sdk) voor meer informatie.

Zie [Bepalen hoe u apps voorbereidt op Mobile Application Management met Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md) voor meer informatie over de keuze tussen App Wrapping Tool en de Intune App SDK.

Sommige beheerde apps, zoals de Outlook-app voor iOS en Android, ondersteunen *meerdere identiteiten*. Dit betekent dat Intune alleen beheerinstellingen toepast op bedrijfsaccounts of -gegevens in de app.

Bijvoorbeeld met de Outlook-app:

-   Als de gebruiker een bedrijfsaccount en een persoonlijk account voor e-mail configureert, past Intune alleen beheerinstellingen toe op het bedrijfsaccount. Het persoonlijke account wordt niet beheerd.

-   Als het apparaat buiten gebruik wordt gesteld of wordt uitgeschreven, worden alleen de zakelijke Outlook-gegevens van het apparaat verwijderd.

-   Het bedrijfsaccount moet hetzelfde account zijn als het account dat is gebruikt voor het registreren van het apparaat bij Intune.

> [!TIP]
> Zie [Apps beheren met Mobile Application Management-beleid in Configuration Manager](https://technet.microsoft.com/library/mt131414.aspx) als u gebruikmaakt van Intune met Configuration Manager.

## Een app maken en implementeren met Mobile Application Management-beleid

-   **Stap 1:** haal de koppeling naar een door beleid beheerde app op, maak een verpakte app of gebruik de Intune App SDK om een app met MAM-beleid te maken.

-   **Stap 2:** publiceer de app naar uw opslagruimte in de cloud.

-   **Stap 3:** maak een Mobile Application Management-beleid.

-   **Stap 4:** koppel de app aan een Mobile Application Management-beleid en implementeer de app vervolgens.

-   **Stap 5:** controleer de implementatie van de app.

## Stap 1: haal de koppeling naar een door beleid beheerde app op, maak een verpakte app of gebruik de Intune App SDK om een app met MAM-beleid te maken

Zoek in de app store naar de URL van de door beleid beheerde app die u wilt implementeren, en noteer deze URL. De URL van de app Microsoft Word voor iPad is bijvoorbeeld **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**.


## Stap 2: publiceer de app naar uw opslagruimte in de cloud
Wanneer u een beheerde app publiceert, is de procedure afhankelijk van of u een door beleid beheerde app publiceert of een app die is verwerkt met behulp van Microsoft Intune App Wrapping Tool voor iOS.

#### Een door beleid beheerde app publiceren

1.  Wanneer u gereed bent voor het uploaden van de app naar uw opslagruimte in de cloud, volgt u de instructies in [Apps voor mobiele apparaten toevoegen in Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md).

2.  Voor iOS-apps selecteert u **Beheerde iOS-App uit de App Store**onder **Selecteren hoe deze software beschikbaar wordt gesteld aan apparaten**.

    Voor Android-apps selecteert u **Externe koppeling**.

3.  Onder **Geef de URL op**voert u de URL naar de door beleid beheerde app in die u eerder hebt genoteerd.

Nadat het uploaden is voltooid, ziet u **Ja** bij **Beheerbeleid voor apps** op de pagina **Software-eigenschappen** voor de geüploade app.

Nadat u hebt gecontroleerd of de app is geüpload, gaat u verder met stap 3.

#### Een app publiceren die is verwerkt met behulp van Microsoft Intune App Wrapping Tool

1.  Wanneer u gereed bent voor het uploaden van de app naar uw opslagruimte in de cloud, volgt u de instructies in [Apps voor mobiele apparaten toevoegen in Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md).

2.  Selecteer **Software Installer** onder **Selecteren hoe deze software beschikbaar wordt gesteld aan apparaten**.

3.  Selecteer **App-pakket voor iOS (&#42;.ipa-bestand)** onder **Bestandstype voor Software Installer**.

Nadat het uploaden is voltooid, ziet u **Ja** bij **Beheerbeleid voor apps** op de pagina **Software-eigenschappen** voor de geüploade app.

Nadat u hebt gecontroleerd of de app is geüpload, gaat u verder met stap 3.

## Stap 3: maak een Mobile Application Management-beleid

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) de optie **Beleid** &gt; **Overzicht** &gt; **Beleid toevoegen**.

2.  Configureer en implementeer een van de volgende **Software**-beleidsregels, afhankelijk van het apparaattype waarvoor u apps wilt configureren:

    -   **Mobile Application Management-beleid (Android 4 en hoger)**

    -   **Mobile Application Management-beleid (iOS 8.0 en hoger)**

    U kunt de aanbevolen instellingen gebruiken of de instellingen aanpassen. Zie [Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) voor meer informatie.

3.  Configureer de volgende instellingen zoals vereist. De opties kunnen variëren, afhankelijk van het apparaattype waarvoor u het beleid configureert.

|Naam van de instelling|Details|
    |---------|--------------------|
    |**Naam**|Geef een naam op voor dit beleid.|
    |**Beschrijving**|Geef desgewenst een beschrijving op voor dit beleid.|
    |**Webinhoud beperken en weergeven in een bedrijfsbeheerde browser**|Als deze instelling is ingeschakeld, worden koppelingen in de app geopend in de beheerde browser. Deze optie werkt alleen als u deze app hebt geïmplementeerd op apparaten.|
    |**Back-ups van Android verhinderen** of **Back-ups van iTunes en iCloud verhinderen**|Met deze instelling worden back-ups van gegevens uit de app uitgeschakeld.|
    |**App mag gegevens overdragen naar ander apps**|Met deze instelling geeft u de apps aan waarnaar deze app gegevens kan verzenden. U kunt kiezen om geen gegevensoverdracht naar apps toe te staan, alleen overdracht naar andere beheerde apps toe te staan of overdracht naar alle apps toe te staan. <br /><br />Bijvoorbeeld als gegevensoverdracht niet is toegestaan, beperkt u gegevensoverdrachtservices zoals SMS messaging, afbeeldingen toewijzen aan contactpersonen en items plaatsen op Facebook of Twitter.<br /><br />Om bij iOS-apparaten documentoverdracht tussen beheerde en onbeheerde apps te voorkomen, moet u ook een beveiligingsbeleid voor mobiele apparaten configureren en implementeren, waarmee de instelling **Beheerde documenten toestaan in andere onbeheerde apps**wordt uitgeschakeld. Als u kiest om alleen overdracht naar andere beheerde apps toe te staan, worden de Intune PDF- en afbeeldingsviewers (indien geïmplementeerd) gebruikt om inhoud van de verschillende typen te openen.<br /><br />Als u deze optie daarnaast instelt op **Door beleid beheerde apps** of **Geen**, wordt de iOS 9-functie waarmee Spotlight Search naar gegevens in apps kan zoeken, geblokkeerd.<br><br>Deze instelling heeft geen controle over het gebruik van de functie Openen in op mobiele apparaten. Zie [Gegevensoverdracht beheren tussen iOS-apps met Microsoft Intune](manage-data-transfer-between-ios-apps-with-microsoft-intune.md) voor informatie over het beheer van de functie Open in.|
    |**App mag gegevens ontvangen van andere apps**|Met deze instelling geeft u de apps op waarvan deze app gegevens mag ontvangen. U kunt kiezen om geen gegevensoverdracht van apps toe te staan, alleen overdracht van andere beheerde apps toe te staan of overdracht van alle apps toe te staan.<br /><br />Wanneer een gebruiker gegevens gaat gebruiken vanaf een app die niet wordt beheerd door een Mobile Application Management-beleid, worden de gegevens behandeld als bedrijfsgegevens en door het beleid beveiligd. Dit geldt voor iOS-apps die ondersteuning bieden voor meerdere identiteiten (waar Intune alleen beheerinstellingen toepast op bedrijfsaccounts of -gegevens in de app). Of het geldt voor een geregistreerd apparaat waarop een Mobile Application Management-beleid wordt toegepast.|
    |**Opslaan als verhinderen**|Met deze instelling schakelt u het gebruik van de optie **Opslaan als** uit voor het opslaan van gegevens naar persoonlijke cloudopslaglocaties (zoals OneDrive of Dropbox) in elke app die gebruikmaakt van dit beleid.|
    |**Knippen, kopiëren en plakken met andere apps beperken**|Met deze instelling geeft u op hoe knip-, kopieer- en plakbewerkingen kunnen worden gebruikt met de app. U kunt kiezen uit:<br /><br />**Geblokkeerd**. Geen knip-, kopieer- en plakbewerkingen toestaan tussen deze app en andere apps.<br /><br />**Door beleid beheerde apps**. Alleen knip-, kopieer- en plakbewerkingen toestaan tussen deze app en andere beheerde apps.<br /><br />**Door beleid beheerde apps met Plakken in**. Toestaan dat gegevens uit deze app worden geknipt of gekopieerd alleen om in andere beheerde apps te worden geplakt. Gegevens die uit alle apps zijn geknipt of gekopieerd, mogen in deze app worden geplakt.<br /><br />**Elke app**. Er zijn geen beperkingen voor knip-, kopieer- en plakbewerkingen naar of vanuit deze app.<br /><br />Als u gegevens wilt kopiëren en plakken tussen beheerde apps, moeten voor beide apps de instellingen voor **door beleid beheerde apps** of **door beleid beheerde apps met Plakken in** zijn geconfigureerd.|
    |**Eenvoudige pincode vereist voor toegang**|Met deze instelling verplicht u de gebruiker om een zelf opgegeven pincode in te voeren om deze app te kunnen gebruiken. De eerste keer dat de gebruiker de app uitvoert, wordt gevraagd om dit in te stellen.|
    |**Aantal pogingen voordat pincode opnieuw wordt ingesteld**|Geeft het aantal toegestane invoerpogingen voor de pincode op gegeven voordat de gebruiker de pincode opnieuw moet instellen.|
    |**Bedrijfsreferenties vereisen voor toegang**|Met deze instelling worden gebruikers verplicht om hun bedrijfsaanmeldingsgegevens in te voeren voordat ze toegang krijgen tot de app.|
    |**Apparaatcompatibiliteit met bedrijfsbeleid vereisen voor toegang**|Met deze instellingen mag de app alleen worden gebruikt wanneer het apparaat niet jailbroken of geroot is.|
    |**Toegangsvereisten opnieuw controleren na (minuten)**|In het veld **Time-out** geeft u de tijdsperiode op waarna de toegangsvereisten voor de app opnieuw worden gecontroleerd nadat de app is gestart.|
    |**Offline respijtperiode**|Als het apparaat offline is, geeft u de tijdsperiode op waarna de toegangsvereisten voor de app opnieuw worden gecontroleerd.|
    |**App-gegevens versleutelen**|Deze instelling geeft aan dat alle gegevens die zijn gekoppeld aan deze app, worden versleuteld. Dit omvat ook gegevens die extern zijn opgeslagen, zoals SD-kaarten.<br /><br />**Versleuteling voor iOS**<br /><br />Voor apps die zijn gekoppeld aan een Intune Mobile Application Management-beleid, worden gegevens in rust versleuteld met behulp van versleuteling op apparaatniveau die wordt geleverd door het besturingssysteem. Dit wordt ingeschakeld via apparaatpincodebeleid dat wordt ingesteld door de IT-beheerder. Als een pincode is vereist, worden de gegevens versleuteld volgens de instellingen in het Mobile Application Management-beleid. Zoals vermeld in de Apple-documentatie [zijn de modules die worden gebruikt door iOS gecertificeerd volgens FIPS 140-2](http://support.apple.com/en-us/HT202739).<br /><br />**Versleuteling voor Android**<br /><br />Voor apps die zijn gekoppeld aan een Intune Mobile Application Management-beleid, wordt versleuteling geleverd door Microsoft. Gegevens worden synchroon versleuteld tijdens de I/O-bewerkingen voor bestanden.  Inhoud in de apparaatopslag wordt altijd versleuteld. De versleutelingsmethode is niet gecertificeerd volgens FIPS 140-2.|
    |**Schermafbeelding blokkeren** (alleen Android-apparaten)|Met deze instelling wordt opgegeven dat de schermafbeeldingsmogelijkheden van het apparaat zijn geblokkeerd als iemand deze app gebruikt.|
    
4. Als u klaar bent, kiest u **Beleid opslaan**.

Het nieuwe beleid wordt weergegeven in het knooppunt **Configuratiebeleid** van de werkruimte **Beleid**.

## Stap 4: koppel de app aan een Mobile Application Management-beleid en implementeer de app vervolgens
Zorg ervoor dat u het Mobile Application Management-beleid selecteert op de pagina **Mobile App Management** in het dialoogvenster **Implementatie beheren** om het beleid te koppelen aan de app.

Zie [Apps implementeren in Microsoft Intune](deploy-apps.md) voor meer informatie.

> [!IMPORTANT]
> Als het apparaat wordt uitgeschreven bij Intune, wordt er geen beleid uit de apps verwijderd. Apps waarop beleid is toegepast, behouden die beleidsinstellingen nadat de app is verwijderd en opnieuw is geïnstalleerd.

### Wat te doen wanneer een app al op apparaten is geïmplementeerd
Er zijn mogelijk situaties waarin u een app implementeert terwijl op een van de beoogde gebruikers of apparaten al een onbeheerde versie van de app is geïnstalleerd. De gebruiker heeft bijvoorbeeld Microsoft Word al vanuit de app store geïnstalleerd.

In dit geval vraagt u de gebruiker de onbeheerde versie handmatig te verwijderen, zodat de beheerde versie kan worden geïnstalleerd die u hebt geconfigureerd.

Bij apparaten met iOS 9 en hoger vraagt Intune de gebruiker automatisch toestemming het beheer van de bestaande app over te nemen. Als de gebruiker akkoord gaat, wordt de app beheerd door Intune en alle regels voor het beheren van mobiele toepassingen die u aan de app hebt gekoppeld, worden ook toegepast.

> [!TIP]
> Als het apparaat zich in de bewaakte modus bevindt, neemt Intune het beheer van de bestaande app over zonder de gebruikers om toestemming te vragen.

## Stap 5: controleer de implementatie van de app.
Nadat u een app hebt gemaakt en geïmplementeerd die is gekoppeld aan een Mobile Application Management-beleid, gebruikt u de volgende procedure om de app te controleren en eventuele beleidsconflicten op te lossen.

#### De status van de implementatie weergeven

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) de optie **Groepen** &gt; **Overzicht**.

2.  Voer een van de volgende stappen uit:

    -   Kies **Alle gebruikers** en dubbelklik op de gebruiker van wie u het apparaat wilt bekijken. Kies op de pagina **Gebruikerseigenschappen** de optie **Apparaten** en dubbelklik op het apparaat dat u wilt bekijken.

    -   Kies **Alle apparaten** &gt; **Alle mobiele apparaten**. Kies op de pagina **Eigenschappen van apparaatgroep** de optie **Apparaten** en dubbelklik op het apparaat dat u wilt bekijken.

3.  Kies op de pagina **Eigenschappen van mobiele apparaten** de optie **Beleid** voor een overzicht van de Mobile Application Management-beleidsregels die zijn geïmplementeerd op het apparaat.

4.  Selecteer het Mobile Application Management-beleid waarvan u de status wilt weergeven. U kunt details van het beleid in het deelvenster onderaan weergeven en het knooppunt uitvouwen om de instellingen weer te geven.

5.  Onder de kolom **Status** van elk van de Mobile Application Management-beleidsregels wordt **Voldoet**, **Voldoet (in behandeling)**of **Fout** weergegeven. Als bij een of meer instellingen van het geselecteerde beleid een conflict optreedt, wordt **Fout** weergegeven in dit veld.

6.  Nadat u een conflict hebt vastgesteld, kunt u conflicterende beleidsinstellingen herzien zodat ze dezelfde instelling gebruiken of kunt u ervoor zorgen dat slechts één beleidsregel op de app en gebruiker wordt geïmplementeerd.

### Oplossen van beleidsconflicten
Als er een conflict optreedt in het Mobile Application Management-beleid bij de eerste implementatie naar de gebruiker of het apparaat, wordt de specifieke conflicterende instellingswaarde verwijderd uit het beleid dat op de app is geïmplementeerd. De app gebruikt een ingebouwde conflictwaarde.

Als er een conflict optreedt in het Mobile Application Management-beleid bij latere implementaties naar de app of gebruiker, wordt de specifieke conflicterende instellingswaarde niet bijgewerkt in het Mobile Application Management-beleid dat op de app is geïmplementeerd. De app gebruikt de bestaande waarde voor die instelling.

In gevallen waarin het apparaat of de gebruiker twee conflicterende sets beleidsregels ontvangt, is het volgende van toepassing:

-   Als er al een beleid is geïmplementeerd op het apparaat, worden de bestaande beleidsinstellingen niet overschreven.

-   Als er nog geen beleid is geïmplementeerd op het apparaat en er twee conflicterende instellingen worden geïmplementeerd, wordt de standaardinstelling gebruikt die is ingebouwd in het apparaat.



<!--HONumber=Sep16_HO2-->


