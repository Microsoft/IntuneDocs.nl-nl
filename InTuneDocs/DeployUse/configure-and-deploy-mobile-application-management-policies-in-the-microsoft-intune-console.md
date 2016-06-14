---
# required metadata

title: Mobile Application Management-beleid configureren en implementeren in de Microsoft Intune-console | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: b4fb33a8-a2fa-4353-bd89-5bda48b68e83

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Mobile Application Management-beleid configureren en implementeren in de Microsoft Intune-console
Aan de hand van Mobile Application Management-beleid in Microsoft Intune kunt u de functionaliteit van de door u geïmplementeerde apps aanpassen, zodat deze apps voldoen aan het beleid van uw bedrijf met betrekking tot naleving en beveiliging. U kunt bijvoorbeeld knip-, kopieer- en plakbewerkingen beperken in een beheerde app of een app configureren om alle webkoppelingen te openen binnen een beheerde browser.

Ondersteuning voor Mobile Application Management-beleid:

-   Apparaten met Android 4 en hoger.

-   Apparaten met iOS 7 en hoger.

> [!TIP]
> Mobile Application Management-beleid ondersteunt apparaten die zijn ingeschreven met Intune.
> 
> Als u informatie zoekt over het maken van beleid voor het beheer van apps voor apparaten die niet worden beheerd door Intune, raadpleegt u [App-gegevens beschermen met Mobile Application Management-beleid van Microsoft Intune](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).

In tegenstelling tot ander beleid van Intunes hoeft u Mobile Application Management-beleid niet rechtstreeks te implementeren. In plaats daarvan koppelt u het beleid aan de app die u wilt beperken. Wanneer de app op apparaten is geïmplementeerd en geïnstalleerd, zullen de instellingen die u opgeeft, in werking treden.

Als u beperkingen wilt toepassen op een app, moet de app gebruikmaken van de Microsoft App Software Development Kit (SDK). Er zijn twee methoden voor het verkrijgen van dit type app:

-   **Een door beleid beheerde app gebruiken**: beschikt over een ingebouwde App SDK. Om dit type app toe te voegen, geeft u een koppeling op naar de app uit een app store zoals iTunes store of Google Play. Er is geen verdere verwerking vereist voor dit type app. Bekijk een overzicht van [apps die u met Mobile Application Management-beleid van Microsoft Intune kunt gebruiken](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).

-   **Een 'verpakte' app gebruiken**: apps die samen met de App SDK zijn verpakt met behulp van de **Microsoft Intune App Wrapping Tool**. Dit hulpprogramma wordt meestal gebruikt voor het verwerken van bedrijfsapps die intern zijn gemaakt. Het kan niet worden gebruikt voor het verwerken van apps die zijn gedownload uit de app store. Zie [iOS-apps voorbereiden voor Mobile Application Management met de Microsoft Intune App Wrapping Tool](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) en [Android-apps voorbereiden voor Mobile Application Management met de Microsoft Intune App Wrapping Tool](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md).

Sommige beheerde apps, zoals de Outlook-app voor iOS en Android, ondersteunen **meerdere identiteiten**. Dit betekent dat Intune alleen beheerinstellingen toepast op bedrijfsaccounts of -gegevens in de app.

Bijvoorbeeld met de Outlook-app:

-   Als de gebruiker een bedrijfsaccount en een persoonlijk account voor e-mail configureert, past Intune alleen beheerinstellingen toe op het bedrijfsaccount. Het persoonlijke account wordt niet beheerd.

-   Als het apparaat buiten gebruik wordt gesteld of uitgeschreven, worden alleen de zakelijke Outlook-gegevens van het apparaat verwijderd.

-   Het gebruikte bedrijfsaccount moet hetzelfde account zijn als het account dat is gebruikt voor het registreren van het apparaat bij Intune.

> [!TIP]
> Zie [Apps beheren met Mobile Application Management-beleid in Configuration Manager](https://technet.microsoft.com/library/mt131414.aspx) als u gebruikmaakt van Intune met Configuration Manager..

## Een app maken en implementeren met Mobile Application Management-beleid

-   **Stap 1:** haal de koppeling naar een door beleid beheerde app op of maak een verpakte app.

-   **Stap 2:** publiceer de app naar uw opslagruimte in de cloud.

-   **Stap 3:** maak een Mobile Application Management-beleid.

-   **Stap 4:** implementeer de app en selecteer daarbij de optie om de app te koppelen aan een Mobile Application Management-beleid.

-   **Stap 5:** controleer de implementatie van de app.

## **Stap 1:** haal de koppeling naar een door beleid beheerde app op of maak een verpakte app

-   **Een koppeling naar een door beleid beheerde app verkrijgen**: zoek in de app store naar de URL van de door beleid beheerde app die u wilt implementeren, en noteer deze URL.

    De URL van de app Microsoft Word voor iPad is bijvoorbeeld **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**

-   **Een verpakte app maken**: gebruik de informatie in de onderwerpen [iOS-apps voorbereiden voor Mobile Application Management met de Microsoft Intune App Wrapping Tool](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) en [Android-apps voorbereiden voor Mobile Application Management met de Microsoft Intune App Wrapping Tool](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) om een verpakte app te maken.

    Het hulpprogramma maakt een verwerkte app die u zult gebruiken wanneer u de app naar de cloudopslag publiceert.

## **Stap 2:** publiceer de app naar uw opslagruimte in de cloud
Wanneer u een beheerde app publiceert, is de procedure afhankelijk van of u een door beleid beheerde app publiceert of een app die is verwerkt met behulp van de Microsoft Intune App Wrapping Tool for iOS.

#### Een door beleid beheerde app publiceren

1.  Wanneer u gereed bent voor het uploaden van de app naar uw opslagruimte in de cloud, volgt u de instructies in [Apps voor mobiele apparaten toevoegen in Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md).

2.  Voor iOS-apps selecteert u **Beheerde iOS-App uit de App Store**onder **Selecteren hoe deze software beschikbaar wordt gesteld aan apparaten**.

    Voor Android-apps selecteert u **Externe koppeling**.

3.  Onder **Geef de URL op** voert u de URL naar de door beleid beheerde app in die u eerder hebt genoteerd.

Nadat het uploaden is voltooid, ziet u **Ja** bij **Beheerbeleid voor apps** op de pagina **Software-eigenschappen** voor de geüploade app.

Nadat u hebt gecontroleerd of de app is geüpload, gaat u verder met stap 3.

#### Een app publiceren die is verwerkt met behulp van de Microsoft Intune App Wrapping Tool

1.  Wanneer u gereed bent voor het uploaden van de app naar uw opslagruimte in de cloud, volgt u de instructies in [Apps voor mobiele apparaten toevoegen in Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md).

2.  Selecteer **Software Installer** onder **Selecteren hoe deze software beschikbaar wordt gesteld aan apparaten**.

3.  Selecteer **App-pakket voor iOS (&#42;.ipa-bestand)** onder **Bestandstype voor Software Installer**.

Nadat het uploaden is voltooid, ziet u **Ja** bij **Beheerbeleid voor apps** op de pagina **Software-eigenschappen** voor de geüploade app.

Nadat u hebt gecontroleerd of de app is geüpload, gaat u verder met stap 3.

## **Stap 3:** maak een Mobile Application Management-beleid

1.  In de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) klikt u op **Beleid** &gt; **Overzicht** &gt; **Beleid toevoegen**.

2.  Configureer en implementeer een van de volgende **Software**-beleidsregels, afhankelijk van het apparaattype waarvoor u apps wilt configureren:

    -   **Mobile Application Management-beleid (Android 4 en hoger)**

    -   **Mobile Application Management-beleid (iOS 7 en hoger)**

    U kunt de aanbevolen instellingen gebruiken of de instellingen aanpassen. Zie [Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) voor meer informatie.

3.  Configureer de volgende instellingen zoals vereist. De opties kunnen variëren, afhankelijk van het apparaattype waarvoor u het beleid configureert.

|Naam van de instelling|Details|
    |---------|--------------------|
    |**Naam**|Geef een naam op voor dit beleid.|
    |**Beschrijving**|Geef desgewenst een beschrijving op voor dit beleid.|
    |**Webinhoud beperken en weergeven in een bedrijfsbeheerde browser**|Als deze instelling is ingeschakeld, worden koppelingen in de app geopend in de beheerde browser. Deze optie werkt alleen als u deze app hebt geïmplementeerd op apparaten.|
    |**Back-ups van Android verhinderen** of **Back-ups van iTunes en iCloud verhinderen**|Hiermee worden back-ups van gegevens uit de app uitgeschakeld.|
    |**App mag gegevens overdragen naar ander apps**|Hiermee geeft u de apps aan waarnaar deze app gegevens kan verzenden. U kunt kiezen om geen gegevensoverdracht naar apps toe te staan, alleen overdracht naar andere beheerde apps toe te staan of overdracht naar alle apps toe te staan. Deze instelling heeft geen controle over het gebruik van de functie **Openen in** op mobiele apparaten.<br /><br />Bijvoorbeeld als gegevensoverdracht niet is toegestaan, beperkt u gegevensoverdrachtservices zoals SMS messaging, afbeeldingen toewijzen aan contactpersonen en items plaatsen op Facebook of Twitter.<br /><br />Voor iOS-apparaten moet u, om documentoverdracht tussen beheerde en onbeheerde apps te voorkomen, ook een beveiligingsbeleid voor mobiele apparaten configureren en implementeren waarmee de instelling **Beheerde documenten toestaan in andere onbeheerde apps** wordt uitgeschakeld. Als u instelt dat alleen overdracht naar andere beheerde apps is toegestaan, worden de Intune PDF- en afbeeldingsviewers (indien geïmplementeerd) gebruikt om inhoud van de verschillende typen te openen.<br /><br />Als u deze optie daarnaast instelt op **Door beleid beheerde apps** of **Geen**, wordt de iOS 9-functie waarmee Spotlight Search naar gegevens in apps kan zoeken, geblokkeerd.|
    |**App mag gegevens ontvangen van andere apps**|Hiermee geeft u de apps op waarvan deze app gegevens mag ontvangen. U kunt kiezen om geen gegevensoverdracht van apps toe te staan, alleen overdracht van andere beheerde apps toe te staan of overdracht van alle apps toe te staan.<br /><br />Voor iOS-apps die ondersteuning bieden voor meerdere identiteiten (waarbij Intune alleen beheerinstellingen toepast op bedrijfsaccounts of -gegevens in de app) voor een geregistreerd apparaat waarop een Mobile Application Management-beleid is toegepast, worden de gegevens behandeld als bedrijfsgegevens en beveiligd door het beleid wanneer een gebruiker toegang krijgt tot gegevens uit een app die niet wordt beheerd door een Mobile Application Management-beleid.|
    |**Opslaan als verhinderen**|Schakelt het gebruik van de optie **Opslaan als** uit voor het opslaan van gegevens naar persoonlijke cloudopslaglocaties (zoals OneDrive Personal of Dropbox) in elke app die gebruikmaakt van dit beleid.|
    |**Knippen, kopiëren en plakken met andere apps beperken**|Hiermee geeft u op hoe knip-, kopieer- en plakbewerkingen kunnen worden gebruikt met de app. U kunt kiezen uit:<br /><br />**Geblokkeerd**: geen knip-, kopieer- en plakbewerkingen toestaan tussen deze app en andere apps.<br /><br />**Door beleid beheerde apps**: alleen knip-, kopieer- en plakbewerkingen toestaan tussen deze app en andere beheerde apps.<br /><br />**Door beleid beheerde apps met Plakken in**: alleen gegevens die uit deze app zijn geknipt of gekopieerd, mogen in andere beheerde apps worden geplakt. Gegevens die uit alle apps zijn geknipt of gekopieerd, mogen in deze app worden geplakt.<br /><br />**Elke app**: geen beperkingen aan knip-, kopieer- en plakbewerkingen naar of vanuit deze app.<br /><br />Als u gegevens wilt kopiëren en plakken tussen beheerde apps, moeten voor beide apps de instellingen voor **door beleid beheerde apps** of **door beleid beheerde apps met Plakken in** zijn geconfigureerd.|
    |**Eenvoudige pincode vereist voor toegang**|De gebruiker moet een zelf opgegeven pincode invoeren om deze app te gebruiken. De eerste keer dat de gebruiker de app uitvoert, wordt gevraagd om dit in te stellen.|
    |**Aantal pogingen voordat pincode opnieuw wordt ingesteld**|Hiermee wordt het aantal invoerpogingen van de pincode opgegeven voordat de gebruiker de pincode opnieuw moet instellen.|
    |**Bedrijfsreferenties vereisen voor toegang**|Hiermee wordt vereist dat gebruikers hun bedrijfsaanmeldingsgegevens invoeren voordat ze toegang krijgen tot de app.|
    |**Apparaatcompatibiliteit met bedrijfsbeleid vereisen voor toegang**|Hiermee mag de app alleen worden gebruikt wanneer het apparaat niet jailbroken of geroot is.|
    |**Toegangsvereisten opnieuw controleren na (minuten)**|In het veld **Time-out** geeft u de tijdsperiode op waarna de toegangsvereisten voor de app opnieuw worden gecontroleerd nadat de app is gestart.|
    |**Offline respijtperiode**|Als het apparaat offline is, geeft u de tijdsperiode op waarna de toegangsvereisten voor de app opnieuw worden gecontroleerd.|
    |**Appgegevens versleutelen**|Hiermee geeft u op dat alle gegevens die aan deze app zijn gekoppeld worden versleuteld, met inbegrip van gegevens die extern zijn opgeslagen, zoals SD-kaarten.<br /><br />**Versleuteling voor iOS**<br /><br />Voor apps die zijn gekoppeld aan een Intune Mobile Application Management-beleid, worden gegevens in rust versleuteld met behulp van versleuteling op apparaatniveau die wordt geleverd door het besturingssysteem. Dit wordt ingeschakeld via apparaatpincodebeleid dat moet worden ingesteld door de IT-beheerder. Als een pincode is vereist, worden de gegevens versleuteld volgens de instellingen in het Mobile Application Management-beleid. Zoals vermeld in de Apple-documentatie, [zijn de modules die worden gebruikt door iOS 7, gecertificeerd volgens FIPS 140-2](http://support.apple.com/en-us/HT202739).<br /><br />**Versleuteling voor Android**<br /><br />Voor apps die zijn gekoppeld aan een Intune Mobile Application Management-beleid, wordt versleuteling geleverd door Microsoft. Gegevens worden synchroon versleuteld tijdens bestands-I/O-bewerkingen overeenkomstig de instelling in het Mobile Application Management-beleid. Beheerde apps op Android gebruiken AES-128-versleuteling in CBC-modus waarbij de cryptografiebibliotheken van het platform worden gebruikt. De versleutelingsmethode is niet gecertificeerd volgens FIPS 140-2. Inhoud in de apparaatopslag wordt altijd versleuteld.|
    |**Schermafbeelding blokkeren** (alleen Android-apparaten)|Hiermee wordt opgegeven dat de schermafbeeldingsmogelijkheden van het apparaat zijn geblokkeerd bij gebruik van deze app.|

4.  Wanneer u klaar bent, klikt u op **Beleid opslaan**.

Het nieuwe beleid wordt weergegeven in het knooppunt **Configuratiebeleid** van de werkruimte **Beleid**.

## **Stap 4:** koppel de app aan een Mobile Application Management-beleid en implementeer de app vervolgens
Implementeer de app, waarbij u ervoor zorgt dat u het Mobile Application Management-beleid selecteert op de pagina **Mobiel appbeheer** om het beleid te koppelen aan de app.

Zie [Apps implementeren in Microsoft Intune](deploy-apps.md) voor meer informatie.

> [!IMPORTANT]
> Voor apparaten met besturingssystemen die ouder zijn dan iOS 7.1, wordt gekoppeld beleid niet verwijderd wanneer de app wordt verwijderd.
> 
> Als het apparaat wordt uitgeschreven uit Intune, wordt beleid niet verwijderd uit de apps; alle apps waarop beleid werd toegepast, behouden de beleidsinstellingen zelfs nadat de app is verwijderd en opnieuw geïnstalleerd.

### Wat te doen wanneer een app al op apparaten is geïmplementeerd
Er zijn mogelijk situaties waarin u een app implementeert terwijl op een van de beoogde gebruikers of apparaten al een onbeheerde versie van de app is geïnstalleerd. De gebruiker heeft bijvoorbeeld Microsoft Word al vanuit de app store geïnstalleerd.

In dit geval vraagt u de gebruiker de onbeheerde versie handmatig te verwijderen, zodat de beheerde versie kan worden geïnstalleerd die u hebt geconfigureerd.

Bij apparaten met iOS 9 en hoger vraagt Intune de gebruiker automatisch toestemming het beheer van de bestaande app over te nemen. Als de gebruiker akkoord gaat, wordt de app beheerd door Intune en alle regels voor het beheren van mobiele toepassingen die u aan de app hebt gekoppeld, worden ook toegepast.

> [!TIP]
> Als het apparaat zich in de bewaakte modus bevindt, neemt Intune het beheer van de bestaande app over zonder de gebruikers om toestemming te vragen.

## **Stap 5:** controleer de implementatie van de app.
Zodra u een app hebt gemaakt en geïmplementeerd die is gekoppeld aan een Mobile Application Management-beleid, gebruikt u de volgende procedures om de app te controleren en eventuele beleidsconflicten op te lossen.

#### De status van de implementatie weergeven

1.  In de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) klikt u op **Groepen** &gt; **Overzicht**.

2.  Voer een van de volgende stappen uit:

    -   Klik op **Alle gebruikers** en dubbelklik op de gebruiker van wie u de apparaten wilt onderzoeken. Klik op de pagina **Gebruikerseigenschappen** op **Apparaten** en dubbelklik op het apparaat dat u wilt onderzoeken.

    -   Klik op **Alle apparaten** &gt; **Alle mobiele apparaten**. Klik op de pagina **Eigenschappen van apparaatgroep** op **Apparaten** en dubbelklik op het apparaat dat u wilt onderzoeken.

3.  Klik op de pagina **Eigenschappen van mobiele apparaten** op **Beleid** voor een overzicht van de Mobile Application Management-beleidsregels die zijn geïmplementeerd op het apparaat.

4.  Selecteer het Mobile Application Management-beleid waarvan u de status wilt weergeven. U kunt details van het beleid in het deelvenster onderaan weergeven en het knooppunt uitvouwen om de instellingen weer te geven.

5.  Onder de kolom **Status** van elk van de Mobile Application Management-beleidsregels wordt **Voldoet**, **Voldoet (in behandeling)**of **Fout** weergegeven. Als bij een of meer instellingen van het geselecteerde beleid een conflict optreedt, wordt **Fout** weergegeven in dit veld.

6.  Zodra u een conflict hebt vastgesteld, kunt u conflicterende beleidsinstellingen herzien zodat ze dezelfde instelling gebruiken of slechts één beleidsregel op de app en gebruiker implementeren.

### Oplossen van beleidsconflicten
Als er een conflict optreedt in het Mobile Application Management-beleid bij de eerste implementatie naar de gebruiker of het apparaat, wordt de specifieke conflicterende instellingswaarde verwijderd uit het beleid dat op de app is geïmplementeerd, en gebruikt de app een ingebouwde conflictwaarde.

Als er een conflict optreedt in het Mobile Application Management-beleid bij latere implementaties naar de app of gebruiker, wordt de specifieke conflicterende instellingswaarde niet bijgewerkt in het Mobile Application Management-beleid dat op de app is geïmplementeerd, en gebruikt de app de bestaande waarde voor die instelling.

In gevallen waarin het apparaat of de gebruiker twee conflicterende sets beleidsregels ontvangt, is het volgende van toepassing:

-   Als er al een beleid is geïmplementeerd op het apparaat, worden de bestaande beleidsinstellingen niet overschreven.

-   Als er nog geen beleid is geïmplementeerd op het apparaat en er twee conflicterende instellingen worden geïmplementeerd, wordt de standaardinstelling gebruikt die is ingebouwd in het apparaat.





<!--HONumber=May16_HO1-->


