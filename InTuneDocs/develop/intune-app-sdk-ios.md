---
# required metadata

title: Ontwikkelaarshandleiding voor Microsoft Intune App SDK voor iOS | Microsoft Intune
description:
keywords:
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Handleiding Microsoft Intune App SDK voor iOS-ontwikkelaars

> [!NOTE] U kunt desgewenst eerst de handleiding [ Aan de slag met Intune App SDK](intune-app-sdk-get-started.md) lezen, waarin wordt uitgelegd hoe u de integratie voor elk ondersteund platform kunt voorbereiden.* 

Met de Microsoft Intune App SDK voor iOS kunt u Intune Mobile App Management (MAM) opnemen in uw iOS-app. Een MAM-toepassing is een app die is geïntegreerd met de Intune App SDK en die u als IT-beheerder in staat stelt om beleid op uw mobiele app te implementeren wanneer de app actief wordt beheerd.

# Inhoud van de SDK

De Intune App SDK voor iOS bevat een statische bibliotheek, bronbestanden API-headers, een plist met instellingen voor foutopsporing en een configuratiehulpprogramma. Mobiele apps kunnen eenvoudig de bronbestanden omvatten en statisch aan de meeste bibliotheken voor beleidsafdwinging worden gekoppeld. Geavanceerde MAM-functies van Intune worden afgedwongen met behulp van API's.
In deze handleiding wordt ingegaan op het gebruik van het volgende bij het integreren van de Intune App SDK voor iOS:

* **`libIntuneMAM.a`**: de Intune App SDK-bibliotheek. Koppel deze bibliotheek aan uw project om uw mobiele app van MAM-functionaliteit te voorzien. Instructies hiervoor vindt u in het gedeelte ‘Uw app ontwikkelen met de Intune App SDK’.

* **`IntuneMAMResources.Bundle`**: een bundel met resources waarvan de SDK afhankelijk is. 

* **Headers**: beschrijft de Intune App SDK-API’s. Als u een API gebruikt, moet u het headerbestand met de API opnemen. 

# De werking van de Intune App SDK

Het doel van de Intune App SDK voor iOS is het toevoegen van beheermogelijkheden voor iOS-toepassingen met minimale codewijzigingen. Door de hoeveelheid codewijzigingen te beperken, kunt u uw mobiele app sneller op de markt brengen en verhoogt u de consistentie en stabiliteit van de app. 

De app moet aan de statische bibliotheek worden gekoppeld en de resourcebundel bevatten. Het bestand MAMDebugSettings.plist is optioneel en kan in het pakket worden opgenomen om te simuleren dat het MAM-beleid op de app wordt toegepast zonder dat u de app via Microsoft Intune hoeft te implementeren. Bovendien kan het bestand MAMDebugSettings.plist in builds voor foutopsporing worden toegepast door het bestand MAMDebugSettings.plist naar de directory Documents van de app te kopiëren middels bestanden delen via iTunes.

# Het bouwen van uw app met Intune App SDK 

Volg de onderstaande stappen voor het inschakelen van de Intune App SDK:

1. Breng als volgt een koppeling tot stand naar de bibliotheek `libIntuneMAM.a` :

    Sleep en zet de bibliotheek libIntuneMAM.a neer op de lijst Gekoppelde frameworks en bibliotheken van het doelproject.  

    ![Intune App SDK iOS - Gekoppelde frameworks en bibliotheken](../media/intune-app-sdk-ios-linked-frameworks-and-libraries.png)
 
    **Opmerking**: Gebruik bij het vrijgeven aan de App Store de releaseversie van libIntuneMAM.a, niet foutopsporingsversie. De releaseversie bevindt zich in map Release. De foutopsporingsversie biedt uitgebreide uitvoer die geschikt is voor het opsporen van problemen met de Intune App SDK.

2. Voeg de volgende iOS-frameworks toe aan het project (indien deze ontbreken).
    * `MessageUI.framework`
    * `Security.framework`
    * `MobileCoreServices.framework`
    * `SystemConfiguration.framework`
    * `libsqlite3.dylib`
    * `libc++.dylib`
    * `ImageIO.framework`
    * `LocalAuthentication.Framework`
    * `AudioToolbox.framework`<br>

    **Opmerking**: Als de app op iOS7 is gericht, stelt u het kenmerk Status van `LocalAuthentication.Framework` in op Optioneel. 

    Als de Status niet is ingesteld, wordt de app niet gestart op iOS7.

    **Opmerking**: Xcode 7 is van `.dylib` -extensies overgeschakeld naar `.tbd`.

3. Voeg de resourcebundel `IntuneMAMResources.bundle` toe aan het project door deze binnen Fasen bouwen naar Bundelresources kopiëren te slepen. 

    ![Intune App SDK iOS - Bundelresources kopiëren](../media/intune-app-sdk-ios-copy-bundle-resources.png)

4. Voeg `-force_load {PATH_TO_LIB}/libIntuneMAM.a` toe aan een van de volgende ter vervanging van `{PATH_TO_LIB}` met de Intune App SDK-locatie:
    * de buildconfiguratie-instelling OTHER_LDFLAGS van het project 
    * de Overige gekoppelde vlaggen<br>

    **Opmerking**: Voor het zoeken naar `PATH_TO_LIB`selecteert u het bestand `libIntuneMAM.a` en kiest u Info ophalen in het menu Bestand. Kopieer en plak de informatie onder Waar (pad) in het gedeelte Algemeen van het venster Info.

5. Als uw mobiele app een hoofd-kroontjespen of hoofd-storyboard definieert in de `info.plist`, verwijdert u de velden uit de bestanden voor hoofd-kroontjespen of hoofd-storyboard. Voeg de waarden voor storyboard of kroontjespen die u eerder hebt verwijderd toe onder een nieuwe woordenlijst met de naam `IntuneMAMSettings` met de volgende sleutelnamen, voor zover van toepassing:
    * `MainStoryboardFile`
    * `MainStoryboardFile~ipad`
    * `MainNibFile`
    * `MainNibFile~ipad `
    
    Als uw mobiele app bevat geen hoofd-kroontjespen of -storyboard in de `info.plist`definieert, zijn deze instellingen **niet vereist**. 

    **Opmerking**: U kunt de `info.plist` in een onbewerkte indeling weergeven (om de sleutelnamen te kunnen bekijken) door met de rechtermuisknop op een willekeurige plaats in de hoofdtekst van het document te klikken en het weergavetype te wijzigen in Onbewerkte sleutels/waarden weergeven.

6. Schakel het delen van sleutelhangers in (indien nog niet ingeschakeld) door in elk projectdoel op Mogelijkheden te klikken en de schakelaar voor het delen van sleutelhangers in te schakelen. Sleutelhanger delen is vereist als u wilt doorgaan met de volgende stap.

    **Opmerking**: Uw inrichtingsprofiel moet ondersteuning bieden voor nieuwe waarden voor sleutelhanger delen. De toegangsgroepen van de sleutelhanger moeten een jokerteken ondersteunen. U kunt dit controleren door het bestand `.mobileprovision` in een teksteditor te openen, te zoeken naar “keychain-access-groups” en te controleren of u een jokerteken hebt, bijvoorbeeld: 

       <key>keychain-access-groups</key>
       <array>
       <string>YOURBUNDLESEEDID.*</string>
       </array>

7. Nadat u sleutelhanger delen hebt ingeschakeld, volgt u deze stappen voor het maken van een afzonderlijke toegangsgroep waarin de gegevens van de Intune App SDK worden opgeslagen. U kunt een toegangsgroep voor de sleutelhanger maken via de gebruikersinterface of met behulp van het rechtenbestand:

    Een toegangsgroep voor de sleutelhanger maken via de gebruikersinterface: 
    
    * Als uw mobiele app geen toegangsgroepen voor de sleutelhanger heeft gedefinieerd, moet u de bundel-id van de app toevoegen als eerste groep.
    * Voeg de groep voor gedeelde sleutelhanger com.microsoft.intune.mam toe. Deze toegangsgroep wordt door de Intune App SDK gebruikt voor het opslaan van gegevens.  
    * Voeg de resourcebundel `com.microsoft.adalcache` aan uw bestaande toegangsgroepen toe. 
 
    ![Intune App SDK iOS - Sleutelhanger delen](../media/intune-app-sdk-ios-keychain-sharing.png)

    Als u in plaats van de reguliere gebruikersinterface het rechtenbestand gebruikt om de toegangsgroep voor de sleutelhanger te maken, moet u de toegangsgroep van de sleutelhanger toevoegen aan het begin van `$(AppIdentifierPrefix)` in het rechtenbestand. Bijvoorbeeld: `$(AppIdentifierPrefix)com.microsoft.intune.mam` en `$(AppIdentifierPrefix)com.microsoft.adalcache`.

    **Opmerking**: Een rechtenbestand is een XML-bestand dat uniek is voor uw mobiele app en dat wordt gebruikt om speciale machtigingen en mogelijkheden binnen uw iOS-app op te geven.

8. Voor mobiele apps die voor iOS 9 + worden ontwikkeld, moet u elk protocol dat door uw mobiele app wordt doorgegeven aan `UIApplication canOpenURL` , opnemen in de matrix `LSApplicationQueriesSchemes` van het bestand `info.plist` van uw mobiele app. Daarnaast moet er voor elk weergegeven protocol een nieuw protocol worden toegevoegd met het achtervoegsel `-intunemam`. U moet ook `http-intunemam`, `https-intunemam`en `ms-outlook-intunemam` in de matrix opnemen. 

9. Als er voor de app URL-schema's in het `info.plist file`zijn gedefinieerd, voegt u een ander schema toe, met het achtervoegsel `-intunemam` voor elk URL-schema.

10. Als er voor de app app-groepen in de rechten zijn gedefinieerd, voegt u deze groepen toe aan de woordenlijst `IntuneMAMSettings` onder de sleutel `AppGroupIdentitifiers` als een matrix met tekenreeksen.

11. Koppel uw mobiele app aan de ADAL-bibliotheek. De ADAL-bibliotheek voor Objective C is [beschikbaar op Github](https://github.com/AzureAD/azure-activedirectory-library-for-objc).

    **Opmerking**: De Intune App SDK is getest met de code van de ADAL-brokervertakking van 19-6-2015. Zorg ervoor dat u een koppeling tot stand brengt met de meeste recente werkende versie van de ADAL-bibliotheek.

12. Voeg de bundel `ADALiOSBundle.bundle resource` toe aan het project door deze binnen Fasen bouwen naar Bundelresources kopiëren te slepen.

13. Gebruik de koppelingsoptie `-force_load PATH_TO_ADAL_LIBRARY` voor het koppelen aan de bibliotheek.

    Voeg `-force_load {PATH_TO_LIB}/libADALiOS.a` aan de buildconfiguratie-instelling OTHER_LDFLAGS van het project of Andere koppelingsvlaggen in de gebruikersinterface toe. “PATH_TO_LIB” moet worden vervangen door de locatie van de binaire ADAL-bestanden. 

Als uw mobiele app ADAL voor de eigen verificatie gebruikt, raadpleegt u het gedeelte 'De instellingen voor Azure Directory Authentication Library configureren'.

## Telemetrie 

De Intune App SDK voor iOS registreert standaard telemetriegegevens van gebruiksgebeurtenissen die naar Microsoft Intune worden verzonden.

De gegevens van de volgende gebruiksgebeurtenissen worden geregistreerd: 

1. Het starten van de app om Microsoft Intune meer inzicht te geven in het MAM-gebruik van de app per beheertype.

2. Het aanroepen van de EnrollApplication-API om Microsoft Intune inzicht te geven in het slagingspercentage en verschillende andere meetwaarden voor het aanroepen van enrollApplication vanaf de client.

**Opmerking**: Als u ervoor kiest geen telemetriegegevens van de Intune App SDK naar Microsoft Intune te verzenden, moet u het vastleggen van telemetriegegevens in de SDK **uitschakelen** door de eigenschap `MAMTelemetryDisabled` in de `IntuneMAMSettings`.

## Het configureren van de instellingen Azure Directory Authentication Library (ADAL)

De Intune App SDK gebruikt ADAL voor het scenario voor verificatie en voorwaardelijk starten. Normaal gesproken vereist ADAL dat apps zich registreren en een unieke id, de `ClientID`, en andere id’s, ophalen om de beveiliging te waarborgen van de tokens die aan de app worden toegekend. De Intune App SDK gebruikt standaardregistratiewaarden voor de communicatie met Azure Active Directory.  Als de app zelf ADAL voor het eigen verificatiescenario gebruikt, moet de app de bestaande registratiewaarden gebruiken en Intune App SDK standaard onderdrukken om ervoor te zorgen dat eindgebruikers niet tweemaal om verificatie wordt gevraagd (eenmaal door de Intune App SDK en een tweede maal door de app). 

De onderstaande stappen zijn vereist als de app zelf ADAL gebruikt voor verificatie. Als uw mobiele app geen gebruik maakt van ADAL, is er geen verdere actie vereist. 

1. In de `Info.plist`van het project, onder een `IntuneMAMSettings` -woordenlijst met de naam van de sleutel `ADALClientId`, geeft u de `ClientID` op die voor ADAL-aanroepen moet worden gebruikt. 

2. In de `Info.plist`van het project, onder een `IntuneMAMSettings` -woordenlijst met de naam van de sleutel `ADALRedirectUri`, geeft u de omleidings-URI op die voor ADAL-aanroepen moet worden gebruikt. U moet mogelijk ook de `ADALRedirectScheme` opgeven, afhankelijk van de indeling van de omleidings-URI van uw app.

## Uw extensies bouwen (optioneel) 

Volg tijdens het bouwen van extensies de instructies voor het bouwen van uw mobiele app, zoals wordt beschreven in het gedeelte ‘Uw app ontwikkelen met de Intune App SDK’. Daarnaast werkt u de info.plist van elke extensie bij door de toevoeging van een sleutel ContainingAppBundleId onder het IntuneMAMSettings-woordenboek met de waarde van de bundel-id van de betreffende app.

## Uw Frameworks bouwen (optioneel)

Door de meest recente wijzigingen in de Intune App SDK hoeft u uw mobiele app niet te compileren met specifieke koppelingsvlaggen als uw mobiele app ingesloten app-frameworks bevat. 

## Afbeeldingsbestanden bij het opstarten (optioneel)

Wanneer een MAM-app actief door Microsoft Intune wordt beheerd, geeft de Intune App SDK na het starten van de app een opstartscherm weer om de gebruiker te laten weten dat de app wordt beheerd. U kunt optioneel een of meer afbeeldingsbestanden toevoegen die op de opstartpagina Beheerd door uw bedrijf worden weergegeven. Gebruik de volgende richtlijnen voor afbeeldingen:

* Voeg de bestandsnamen toe onder de `IntuneMAMSettings` -woordenlijst in de info.plist van de app met de sleutelnamen `SplashIconFile` en `SplashIconFile~ipad`. 

* Afmetingen en vereisten voor afbeeldingen:

    * 180 x 180 voor de iPhone 6s Plus en iPhone 6 Plus, 120 x 120 voor andere iPhone-modellen en 152 x 152 voor de iPad. 
    
    * Verwijder de `.png` -extensie van bestandsnamen. 
    
    * Gebruik de koppelingsoptie `@2x` voor versies met de schaal 2x en het achtervoegsel `@3x` voor versies met de schaal 3x van de afbeeldingsbestanden. Als de afbeeldingen niet de juiste afmetingen hebben, worden ze aan de pagina aangepast. Als de SplashIconFile-waarden niet zijn opgegeven, selecteert de Intune App SDK een van de app-pictogrammen (60x60 voor alle iPhones, 76x76 voor iPad).

**Opmerking**: dit scherm wordt bij het opstarten geactiveerd maar kan permanent door de gebruiker worden gesloten.

# De instellingen van de Intune App SDK configureren

De `IntuneMAMSettings` -woordenlijst die deel uitmaakt van de `info.plist` van de app wordt gebruikt voor het configureren van de Intune App SDK. Hier volgt een lijst met alle ondersteunde instellingen: 

Sommige van deze instellingen zijn in de eerdere gedeeltes aan bod gekomen en sommige zijn niet op alle apps van toepassing. 

Instelling  | Type  | Definitie | Vereist?
--|--|--|--
ADALClientId  | Tekenreeks  | AAD client-id van de app. | Vereist als de app ADAL gebruikt.
ADALRedirectUri  | Tekenreeks  | AAD omleidings-URI van de app. | Vereist als de app ADAL gebruikt. 
AppGroupIdentifier | Matrix van tekenreeks  | Matrix van toepassingsgroepen van het gedeelte com.apple.security.application-groups met rechten van de app. | Vereist als de app toepassingsgroepen gebruikt.
ContainingAppBundleId  | Tekenreeks | Deze geeft de bundel-id aan van de extensie waarvan app onderdeel uitmaakt. | Vereist voor iOS-extensies.
MainNibFile<br>MainNibFile~ipad  | Tekenreeks  | Deze instelling moet de bestandsnaam van de hoofd-kroontjespen van de app bevatten.  | Vereist als de app MainNibFile in de info.plist definieert.
MainStoryboardFile<br>MainStoryboardFile~ipad  | Tekenreeks  | Deze instelling moet de bestandsnaam van het hoofd-storyboard van de app bevatten. | Vereist als de app UIMainStoryboardFile in de info.plist definieert.
SplashIconFile <br>SplashIconFile~ ipad  | Tekenreeks  | Geeft het pictogrambestand van het Intune-welkomstscherm aan. Zie het gedeelte ‘Afbeeldingsbestanden bij het opstarten’ voor meer informatie. | Optioneel.
SplashDuration | Getal | Minimale tijdsduur in seconden voor de weergave van het Intune-welkomstscherm bij het opstarten van de app. De standaardwaarde is 1,5 seconden. | Optioneel.
ADALLogOverrideDisabled | Boolean-waarde  | Geeft aan of de SDK alle ADAL-logboeken (inclusief ADAL-aanroepen van de app, indien van toepassing) naar een eigen logboekbestand routeert. De standaardwaarde is NO (Nee). De waarde is YES (Ja) als de app een eigen ADAL-logboek wil aanroepen. | Optioneel.

# Headers voor de Intune App SDK 

De volgende headers omvatten de API-functieaanroepen die zijn vereist voor het inschakelen van de functionaliteit van de Intune App SDK. 

    IntuneMAMAsyncResult.h
    IntuneMAMDataProtectionInfo.h
    IntuneMAMDataProtectionManager.h
    IntuneMAMFileProtectionInfo.h
    IntuneMAMFileProtectionManager.h
    IntuneMAMPolicyDelegate.h
    IntuneMAMLogger.h

# Foutopsporing voor de Intune App SDK in Xcode

Voordat u uw MAM-app test met Microsoft Intune, kunt u `Settings.bundle` in Xcode gebruiken. Hierdoor kunt u beleidsregels testen zonder dat er een verbinding met Intune is vereist. U kunt deze header als volgt inschakelen:

* Voeg een `Settings.bundle` toe door met de rechtermuisknop op de map op het hoogste niveau in uw project te klikken. Ga naar het menu en selecteer Toevoegen -> Nieuw bestand. Selecteer de sjabloon Instellingenbundel onder Resources en voeg deze toe.

* Kopieer alleen bij builds voor foutopsporing de `MAMDebugSettings.plist` naar `Settings.bundle`.

* In `Root.plist` (in Settings.bundle) voegt u de voorkeur voor het Type onderliggend deelvenster, FileName `MAMDebugSettings`.

* In Instellingen -> uw App-naam schakelt u Beleidsregels testen inschakelen in.

* Start de app (binnen of buiten Xcode). 

* Schakel in Instellingen -> Uw app-naam -> Beleidsregels testen inschakelen een beleid in, bijvoorbeeld Pincode.

* Start de app (binnen of buiten Xcode). Controleer of pincode werkt zoals verwacht.

> [!NOTE] U kunt Instellingen -> Uw app-naam -> Beleidsregels testen inschakelen nu gebruiken voor het in- en uitschakelen van instellingen.

# Aanbevolen procedures voor iOS

Hier volgen enkele aanbevolen procedures voor het ontwikkelen voor iOS:

Het iOS-bestandssysteem is hoofdlettergevoelig. Zorg ervoor dat u de juiste notatie van hoofdletters en kleine letters gebruikt voor bestandsnamen als `libIntuneMAM.a` en `IntuneMAMResources.bundle`.

Als Xcode `libIntuneMAM.a`niet kan vinden, kunt u dit probleem oplossen door het pad naar deze bibliotheek toe te voegen in de zoekpaden aan de linkerzijde.



<!--HONumber=May16_HO2-->


