---
title: iOS-apps verpakken met de Intune App Wrapping Tool
description: Gebruik de informatie in dit onderwerp om meer te leren over het verpakken van uw iOS-apps zonder de code van de app zelf te wijzigen. Bereid de apps voor, zodat u de Mobile App Management-beleidsregels kunt toepassen.
keywords: 
author: mattbriggs
ms.author: mabriggs
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 99ab0369-5115-4dc8-83ea-db7239b0de97
ms.reviewer: oldang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 109b0867f207742f56886f723c1646432b1260ca
ms.sourcegitcommit: f3b8fb8c47fd2c9941ebbe2c047b7d0a093e5a83
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/11/2017
---
# <a name="prepare-ios-apps-for-app-protection-policies-with-the-intune-app-wrapping-tool"></a>iOS-apps voorbereiden voor app-beveiligingsbeleid met Intune App Wrapping Tool

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Gebruik de Microsoft Intune App Wrapping Tool voor iOS om het beveiligingsbeleid van de Intune-app voor interne iOS-apps in te schakelen zonder dat u de code van de app zelf wijzigt.

Het hulpprogramma is een macOS-opdrachtregelprogramma waarmee een 'wrapper' (soort schil) rond een app wordt gemaakt. Nadat een app is verwerkt, kunt u de functionaliteit ervan wijzigen door een [app-beveiligingsbeleid](/intune-classic/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console) te implementeren.

Zie [Microsoft Intune App Wrapping Tool voor iOS](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios) op GitHub als u het hulpprogramma wilt downloaden.



## <a name="general-prerequisites-for-the-app-wrapping-tool"></a>Algemene vereisten voor de App Wrapping Tool

Voordat u de App Wrapping Tool uitvoert, moet u aan enkele algemene vereisten voldoen:

* Download de [Microsoft Intune App Wrapping Tool voor iOS](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios) vanuit GitHub.

* Een macOS-computer met OS X 10.8.5 of hoger, waarop de Xcode-hulpmiddelenset versie 5 of hoger is geïnstalleerd.

* De iOS-invoer-app moet zijn ontwikkeld en ondertekend door uw bedrijf of een ISV (Independent Software Vendor, onafhankelijke softwareleverancier).

  * Het bestand van de invoer-app moet de extensie **.ipa** of **.app** hebben.

  * De invoerapp moet zijn gecompileerd voor iOS 8.0 of hoger.

  * De invoer-app kan niet worden versleuteld.

  * De invoer-app kan geen uitgebreide bestandskenmerken hebben.

  * Voor de invoer-app moeten rechten zijn ingesteld voordat deze wordt verwerkt door de Intune App Wrapping Tool. [Rechten](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/EntitlementKeyReference/Chapters/AboutEntitlements.html) zorgen ervoor dat de app naast de standaardmachtigingen en -mogelijkheden ook over andere machtigingen en -mogelijkheden beschikt. Zie [App-rechten instellen](#setting-app-entitlements) voor instructies.

## <a name="apple-developer-prerequisites-for-the-app-wrapping-tool"></a>Apple Developer-vereisten voor de App Wrapping Tool


Als u verpakte apps uitsluitend naar gebruikers van uw organisatie wilt distribueren, moet u beschikken over een account voor het [Apple Developer Enterprise Program](https://developer.apple.com/programs/enterprise/) en over verschillende entiteiten voor app-ondertekening die zijn gekoppeld aan uw Apple Developer-account.

Meer informatie over het intern distribueren van iOS-apps naar gebruikers van uw organisatie kunt u vinden in de officiële handleiding [Distributing Apple Developer Enterprise Program Apps](https://developer.apple.com/library/content/documentation/IDEs/Conceptual/AppDistributionGuide/DistributingEnterpriseProgramApps/DistributingEnterpriseProgramApps.html#//apple_ref/doc/uid/TP40012582-CH33-SW1).

U hebt het volgende nodig voor het distribueren van apps die zijn verpakt door Intune:

* Een Developer-account voor het Apple Developer Enterprise Program.

* Handtekeningcertificaat voor interne en ad-hocdistributie met geldige team-id.

  * U hebt de SHA1-hash van het handtekeningcertificaat nodig als parameter voor de Intune App Wrapping Tool.


* Inrichtingsprofiel voor interne distributie.

### <a name="steps-to-create-an-apple-developer-enterprise-account"></a>Stappen voor het maken van een Apple Developer Enterprise-account
1. Ga naar de [site Apple Developer Enterprise Program](https://developer.apple.com/programs/enterprise/).

2. Klik in de rechterbovenhoek van de pagina op **Enroll**.

3. Bekijk de controlelijst om te zien wat u moet registreren. Klik op **Start Your Enrollment** aan de onderkant van de pagina.

4. **Meld u aan** met de Apple ID van uw organisatie. Als u die niet hebt, klikt u op **Create Apple ID**.

5. Selecteer uw **Entity Type** en klik op **Continue**.

6. Vul het formulier in met de gegevens van uw organisatie. Klik op **Continue**. Op dat punt vraagt Apple u te controleren of u bent gemachtigd om uw organisatie te registreren.

8. Klik na de verificatie op **Agree to License**.

9. Nadat u akkoord bent gegaan met de licentie, voltooit u de procedure door **het programma te kopen en te activeren**.

10. Als u de teamagent bent (degene die aan het Apple Developer Enterprise Program deelneemt namens uw organisatie), stelt u eerst uw team samen door teamleden uit te nodigen en rollen toe te wijzen. Lees de Apple-documentatie over [het beheren van uw Developer-accountteam](https://developer.apple.com/library/content/documentation/IDEs/Conceptual/AppDistributionGuide/ManagingYourTeam/ManagingYourTeam.html#//apple_ref/doc/uid/TP40012582-CH16-SW1) voor meer informatie over het beheren van uw team.

### <a name="steps-to-create-an-apple-signing-certificate"></a>Stappen voor het maken van een Apple-handtekeningcertificaat

1. Ga naar de [Apple Developer-portal](https://developer.apple.com/).

2. Klik in de rechterbovenhoek van de pagina op **Account**.

3. **Meld u aan** met uw de Apple ID van uw organisatie.

4. Klik op **Certificates, IDs & Profiles**.

  ![Apple Developer-portal](./media/iOS-signing-cert-1.png)

5. Klik op het ![plusteken van de Apple Developer-portal](./media/iOS-signing-cert-2.png) in de rechterbovenhoek om een iOS-certificaat toe te voegen.

6. Maak een **In-House and Ad Hoc**-certificaat onder **Production**.

  ![Selecteer In-House and Ad Hoc als certificaat](./media/iOS-signing-cert-3.png)

  >[!NOTE]
  >Als u niet van plan bent om de app te distribueren en u deze alleen intern wilt testen, kunt u een certificaat voor iOS-appontwikkeling in plaats van een certificaat voor productie gebruiken. Als u een certificaat voor ontwikkeling gebruikt, zorg er dan voor dat het mobiele inrichtingsprofiel verwijst naar de apparaten waarop de app wordt geïnstalleerd.

7. Klik onder aan de pagina op **Next**.

8. Lees de instructies voor het maken van een **Certificate Signing Request (CSR)** met behulp van de toepassing Sleutelhangertoegang op uw macOS-computer.

  ![Instructies doornemen voor het maken van een CSR](./media/iOS-signing-cert-4.png)

9. Volg de bovenstaande instructies om een CSR te maken. Start de toepassing **Sleutelhangertoegang** op uw macOS-computer.

10. In het macOS-menu boven aan het scherm gaat u naar **Sleutelhangertoegang > Certificaatassistent > Vraag een certificaat aan bij een certificaatautoriteit**.  

  ![Een certificaat aanvragen bij een certificeringsinstantie in Sleutelhangertoegang](./media/iOS-signing-cert-5.png)

11. Volg de instructies op de Apple Developer-site hierboven voor het maken van een CSR-bestand. Sla het CSR-bestand op uw macOS-computer op.

  ![Een certificaat aanvragen bij een certificeringsinstantie in Sleutelhangertoegang](./media/iOS-signing-cert-6.png)

12. Ga terug naar de Apple Developer-site. Klik op **Continue**. Upload vervolgens het CSR-bestand.

13. Apple genereert het handtekeningcertificaat. Download het handtekeningcertificaat en sla het op in een gemakkelijk te onthouden locatie op uw macOS-computer.

  ![Uw handtekeningcertificaat downloaden](./media/iOS-signing-cert-7.png)

14. Dubbelklik op het certificaatbestand dat u zojuist hebt gedownload om het certificaat toe te voegen aan een sleutelhanger.

15. Open **Sleutelhangertoegang** opnieuw. Ga naar uw certificaat door te zoeken naar de naam van het certificaat in de zoekbalk rechtsboven. Klik met de rechtermuisknop op het item om het menu te openen en klik op **Toon info**. In de voorbeeldschermen wordt een certificaat voor ontwikkeling in plaats van een certificaat voor productie gebruikt.

  ![Uw certificaat toevoegen aan een sleutelhanger](./media/iOS-signing-cert-8.png)

16. Er wordt een venster met informatie weergegeven. Ga naar de onderkant van het venster en kijk onder het label **Vingerafdrukken**. Kopieer de (grijs weergegeven) **SHA1**-tekenreeks om deze te gebruiken als de parameter -c voor de App Wrapping Tool.

  ![Uw certificaat toevoegen aan een sleutelhanger](./media/iOS-signing-cert-9.png)



### <a name="steps-to-create-an-in-house-distribution-provisioning-profile"></a>Stappen voor het maken van een In-House Distribution Provisioning-profiel

1. Ga terug naar de [Apple Developer-accountportal](https://developer.apple.com/account/) en **meld u aan** met de Apple ID van uw organisatie.

2. Klik op **Certificates, IDs & Profiles**.

3. Klik op het ![plusteken van de Apple Developer-portal](./media/iOS-signing-cert-2.png) in de rechterbovenhoek om een iOS-inrichtingsprofiel toe te voegen.

4. Maakt een **In House**-inrichtingsprofiel onder **Distribution**.

  ![In House-inrichtingsprofiel selecteren](./media/iOS-provisioning-profile-1.png)

5. Klik op **Continue**. Koppel het eerder gegenereerde handtekeningcertificaat aan het inrichtingsprofiel.

6. Volg de stappen om uw profiel (met de extensie .mobileprovision) te downloaden naar uw macOS-computer.

7. Sla het bestand op in een gemakkelijk te onthouden locatie. Dit bestand wordt gebruikt voor de parameter -p bij gebruik van de App Wrapping Tool.



## <a name="download-the-app-wrapping-tool"></a>De App Wrapping Tool downloaden

1.  Download de bestanden voor de App Wrapping Tool van [GitHub](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios) naar een Mac OS-computer.

2.  Dubbelklik op **Microsoft Intune App Wrapping Tool for iOS.dmg**. Er wordt een venster met de gebruiksrechtovereenkomst weergegeven. Lees het document zorgvuldig door.

3. Kies **Akkoord** om de gebruiksrechtovereenkomst te accepteren. Hiermee wordt het pakket aan uw computer gekoppeld.

4.  Open de map **IntuneMAMPackager** en sla de inhoud ervan op uw Mac OS-computer op. U kunt de App Wrapping Tool nu gaan uitvoeren.

## <a name="run-the-app-wrapping-tool"></a>De App Wrapping Tool uitvoeren

### <a name="use-terminal"></a>Terminal gebruiken

Open het Mac OS Terminal-programma en navigeer naar de map waarin u de bestanden van de App Wrapping Tool hebt opgeslagen. Het uitvoerbare programma heet IntuneMAMPackager en bevindt zich in IntuneMAMPackager/Contents/MacOS. Voer de opdracht als volgt uit:

```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager -i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> -p /<path to provisioning profile> -c <SHA1 hash of the certificate> [-b [<output app build string>]] [-v] [-e] [-x /<array of extension provisioning profile paths>]
```

> [!NOTE]
> Sommige parameters zijn optioneel, zoals wordt weergegeven in de volgende tabel.

**Voorbeeld:** met de volgende voorbeeldopdracht voert u de App Wrapping Tool uit voor een app met de naam MyApp.ipa. Een inrichtingsprofiel en een SHA-1-hash van het ondertekeningscertificaat worden opgegeven en gebruikt om de ingepakte app te ondertekenen. De uitvoer-app (MyApp_Wrapped.ipa) wordt gemaakt en opgeslagen in uw Bureaublad-map.

```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager -i ~/Desktop/MyApp.ipa -o ~/Desktop/MyApp_Wrapped.ipa -p ~/Desktop/My_Provisioning_Profile_.mobileprovision -c "12 A3 BC 45 D6 7E F8 90 1A 2B 3C DE F4 AB C5 D6 E7 89 0F AB"  -v true
```

### <a name="command-line-parameters"></a>Opdrachtregelparameters
U kunt de volgende opdrachtregelparameters gebruiken met de App Wrapping Tool:

|Eigenschap|Gebruik|
|---------------|--------------------------------|
|**-i**|`<Path of the input native iOS application file>`. De bestandsnaam moet eindigen op .app of .ipa. |
|**-o**|`<Path of the wrapped output application>` |
|**-p**|`<Path of your provisioning profile for iOS apps>`|
|**-c**|`<SHA1 hash of the signing certificate>`|
|**-h**|Hiermee wordt gedetailleerde informatie weergegeven over de beschikbare opdrachtregeleigenschappen voor de App Wrapping Tool.|
|**-v**|(Optioneel) Hiermee worden uitgebreide berichten naar de console uitgevoerd. Het wordt aanbevolen deze eigenschap te gebruiken voor opsporing van eventuele fouten.|
|**-e**| (Optioneel) Gebruik deze eigenschap om ervoor te zorgen dat ontbrekende rechten worden verwijderd wanneer de app door de App Wrapping Tool wordt verwerkt. Zie App-rechten instellen voor meer informatie.|
|**-xe**| (Optioneel) Hiermee wordt informatie afgedrukt over de iOS-extensies in de app en de rechten die nodig zijn voor het gebruik ervan. Zie App-rechten instellen voor meer informatie. |
|**-x**| (Optioneel) `<An array of paths to extension provisioning profiles>`. Gebruik deze eigenschap als uw app extensie-inrichtingsprofielen nodig heeft.|
|**-f**|(Optioneel) `<Path to a plist file specifying arguments.>` Gebruik deze eigenschap vóór het [PLIST](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/PropertyLists/Introduction/Introduction.html)-bestand als u ervoor kiest om de PLIST-sjabloon te gebruiken om de rest van de IntuneMAMPackager-eigenschappen op te geven, zoals -i, -o en -p. Zie Een PLIST-bestand gebruiken voor het invoeren van argumenten. |
|**-b**|(Optioneel) Gebruik -b zonder argument als u wilt dat de verpakte uitvoer-app dezelfde bundelversie krijgt als de invoer-app (niet aanbevolen). <br/><br/> Gebruik `-b <custom bundle version>` als u wilt dat de verpakte app een aangepaste CFBundleVersion krijgt. Als u ervoor kiest om een aangepaste CFBundleVersion op te geven, wordt u aangeraden om de CFBundleVersion van de oorspronkelijke app te verhogen door de minst significante component te verhogen, bijvoorbeeld 1.0.0 -> 1.0.1. |

### <a name="use-a-plist-to-input-arguments"></a>Een PLIST-bestand gebruiken voor het invoeren van argumenten
U kunt de App Wrapping Tool op een eenvoudige manier uitvoeren door de opdrachtargumenten in een [PLIST](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/PropertyLists/Introduction/Introduction.html)-bestand op te nemen. Een PLIST-bestand heeft een indeling die vergelijkbaar is met die van een XML-bestand en kan worden gebruikt om opdrachtregelargumenten in te voeren met een formulierinterface.

Open in de map IntuneMAMPackager/Contents/MacOS `Parameters.plist` (een lege PLIST-sjabloon) met een teksteditor of Xcode. Voer uw argumenten in voor de volgende sleutels:

| PLIST-sleutel |  Standaardwaarde| Opmerkingen |
|------------------|--------------|-----|
| Pad van invoer-app-pakket  |leeg| Gelijk aan -i|
| Pad van uitvoer-app-pakket |leeg| Gelijk aan -o|
| Pad van inrichtingsprofiel |leeg| Gelijk aan -p|
| SHA-1-certificaat-hash |leeg| Gelijk aan -c|
| Uitgebreid ingeschakeld |onjuist| Gelijk aan -v|
| Ontbrekende rechten verwijderen | onjuist| Gelijk aan -c|
| Standaardbuild voorkomen |onjuist | Komt overeen met het gebruik van -b zonder argumenten|
|Tekenreeks voor build overschrijven | leeg| De aangepaste CFBundleVersion van de verpakte uitvoer-app |
|Paden van extensie-inrichtingsprofielen | leeg| Een matrix van extensie-inrichtingsprofielen voor de app.


Voer de IntuneMAMPackager uit met het PLIST-bestand als het enige argument:

```bash
./IntuneMAMPackager –f Parameters.plist
```

### <a name="post-wrapping"></a>Na het verpakken

Nadat het verpakken is voltooid, wordt het bericht 'De toepassing is verpakt' weergegeven. Zie [Foutberichten](#error-messages-and-log-files) voor hulp als er een fout optreedt.

De verpakte app wordt opgeslagen in de uitvoermap die u eerder hebt opgegeven. U kunt de app uploaden naar de Intune-beheerconsole en koppelen aan een beheerbeleid voor mobiele apps.

> [!IMPORTANT]
> Wanneer u een verpakte app uploadt, kunt u proberen een oudere versie van de app bij te werken als er al een oudere (ingepakte of oorspronkelijke) versie was geïmplementeerd in Intune. Als er een fout optreedt, uploadt u de app als een nieuwe app en verwijdert u de oudere versie.

U kunt de app nu implementeren naar uw gebruikersgroepen en app-beveiligingsbeleid instellen voor de app. De app wordt uitgevoerd op het apparaat met het app-beperkingsbeleid dat u hebt opgegeven.

## <a name="error-messages-and-log-files"></a>Foutberichten en logboekbestanden
Gebruik de volgende informatie voor het oplossen van problemen die zich voordoen met de App Wrapping Tool.

### <a name="error-messages"></a>Foutberichten
Als de App Wrapping Tool niet kan worden voltooid, wordt mogelijk een van de volgende foutberichten weergegeven in de console:

|Foutbericht|Meer informatie|
|-----------------|--------------------|
|U moet een geldig iOS-inrichtingsprofiel opgeven.|Uw inrichtingsprofiel is mogelijk niet geldig. Controleer of u de juiste machtigingen hebt voor apparaten en of uw profiel correct is gemaakt voor ontwikkeling of distributie. Uw inrichtingsprofiel kan ook zijn verlopen.|
|Geef een geldige naam op voor een invoer-app.|Zorg dat u de juiste naam opgeeft voor de invoer-app.|
|Geef een geldig pad naar de uitvoer-app op.|Zorg dat het pad naar de uitvoer-app dat u hebt opgegeven bestaat en correct is.|
|Geef een geldig inrichtingsprofiel voor invoer op.|Zorg dat u een geldige naam en extensie voor het inrichtingsprofiel hebt opgegeven. Er ontbreken mogelijk rechten in uw inrichtingsprofiel of mogelijk hebt u de opdrachtregeloptie –p niet toegevoegd.|
|De invoer-app die u hebt opgegeven, is niet gevonden. Geef een geldige naam en een geldig pad op voor de invoer-app.|Zorg dat het pad naar uw invoer-app geldig is en bestaat. Zorg dat de invoer-app op die locatie bestaat.|
|Het inrichtingsprofielbestand voor invoer dat u hebt opgegeven, is niet gevonden. Geef een geldige inrichtingsprofielbestand voor invoer op.|Zorg dat het pad naar het inrichtingsbestand voor invoer geldig is en dat het opgegeven bestand bestaat.|
|De app-map voor uitvoer die u hebt opgegeven, is niet gevonden. Geef een geldig pad naar de uitvoer-app op.|Zorg dat het opgegeven uitvoerpad geldig is en bestaat.|
|App voor uitvoer heeft geen **IPA**-extensie.|Alleen apps met de extensies **.app** en **.ipa** worden geaccepteerd door de App Wrapping Tool. Zorg dat uw bestand voor uitvoer een geldige extensie heeft.|
|Er is een ongeldig handtekeningcertificaat opgegeven. Geef een geldig handtekeningcertificaat van Apple op.|Zorg dat u het juiste handtekeningcertificaat hebt gedownload vanuit de Apple-portal voor ontwikkelaars. Uw certificaat is mogelijk verlopen of misschien ontbreekt er een openbare of persoonlijke sleutel. Als uw Apple-certificaat en inrichtingsprofiel kunnen worden gebruikt om een app correct te ondertekenen in Xcode, zijn deze ook geldig voor de App Wrapping Tool.|
|De opgegeven app voor invoer is ongeldig. Geef een geldige app op.|Zorg dat u een geldige iOS-app hebt die is gecompileerd als APP of IPA-bestand.|
|De opgegeven app voor invoer is versleuteld. Geef een geldige niet-versleutelde app op.|De App Wrapping Tool ondersteunt geen versleutelde apps. Geef een niet-versleutelde app op.|
|De opgegeven app voor invoer die u hebt opgegeven, heeft geen Position Independent Executable-indeling (PIE). Geef een geldige app in de PIE-indeling op.|Position Independent Executable-apps (PIE) kunnen worden geladen op een willekeurig geheugenadres wanneer ze worden uitgevoerd. Dit kan beveiligingsvoordelen hebben. Zie de Apple-documentatie voor ontwikkelaars voor meer informatie over beveiligingsvoordelen.|
|De opgegeven invoer-app is al verpakt. Geef een geldige niet-verpakte app op.|U kunt een app die al is verwerkt door het hulpprogramma, niet opnieuw verwerken. Als u wilt een app opnieuw wilt verwerken, moet u het hulpprogramma uitvoeren met de oorspronkelijke versie van de app.|
|De app voor invoer die u hebt opgegeven, is niet ondertekend. Geef een geldige ondertekende app op.|De App Wrapping Tool vereist dat apps zijn ondertekend. Raadpleeg de documentatie voor ontwikkelaars voor meer informatie over hoe u een verpakte app ondertekent.|
|De app voor invoer die u hebt opgegeven, moet de indeling .ipa of .app hebben.|Alleen de extensies .app en .ipa worden geaccepteerd door de App Wrapping Tool. Zorg dat uw invoerbestand een geldige extensie heeft en is gecompileerd als bestand met de extensie .app of .ipa.|
|De invoer-app die u hebt opgegeven, is al verpakt en heeft de meest recente beleidssjabloonversie.|De App Wrapping Tool pakt een bestaande verpakte app met de meest recente beleidssjabloonversie niet opnieuw in.|
|WAARSCHUWING: u hebt geen SHA1-certificaat-hash opgegeven. Zorg dat uw verpakte app is ondertekend voordat u deze implementeert.|Zorg dat u een geldige SHA1-hash opgeeft na de opdrachtregeleigenschap –c. |

### <a name="log-files-for-the-app-wrapping-tool"></a>Logboekbestanden voor de App Wrapping Tool
Apps die zijn verpakt met de App Wrapping Tool genereren logboeken die worden geschreven naar de console van het iOS-clientapparaat. Deze informatie is nuttig voor situaties waarin u een probleem ondervindt met de app en wilt achterhalen of dit probleem te maken heeft met de App Wrapping Tool. Als u deze informatie wilt ophalen, gebruikt u de volgende stappen:

1.  Reproduceer het probleem door de app uit te voeren.

2.  Verzamel de uitvoer van de console door de instructies van Apple voor [foutopsporing in geïmplementeerde iOS-apps](https://developer.apple.com/library/ios/qa/qa1747/_index.html)te volgen.

3.  Filter de opgeslagen logboeken op beperkingen voor apps door het volgende script in te voeren in de console:

    ```
    grep “IntuneAppRestrictions” <text file containing console output> > <required filtered log file name>
    ```
    U kunt de gefilterde logboeken naar Microsoft verzenden.

    > [!NOTE]
    > In het logboekbestand komt het item 'build version' overeen met de buildversie van Xcode.

    Verpakte apps bieden gebruikers ook de optie om logboeken rechtstreeks vanaf het apparaat te verzenden nadat de app is vastgelopen. Gebruikers kunnen u de logboeken toesturen, zodat u ze kunt onderzoeken en indien nodig kun doorsturen naar Microsoft.


### <a name="certificate-provisioning-profile-and-authentication-requirements"></a>Certificaat-, inrichtingsprofiel- en verificatievereisten

De App Wrapping Tool voor iOS kan alleen volledig functioneren als aan bepaalde vereisten wordt voldaan.

|Vereiste|Details|
|---------------|-----------|
|iOS-inrichtingsprofiel|Controleer of het inrichtingsprofiel geldig is voordat u het toevoegt. De App Wrapping Tool controleert niet of het inrichtingsprofiel is verlopen bij het verwerken van een iOS-app. Als een verlopen inrichtingsprofiel is opgegeven, voegt de App Wrapping Tool het verlopen inrichtingsprofiel toe en weet u niet dat er een probleem is tot de installatie van de app op een iOS-apparaat mislukt.|
|iOS-handtekeningcertificaat|Controleer of het ondertekeningscertificaat geldig is voordat u het opgeeft. De App Wrapping Tool controleert niet of het certificaat is verlopen bij het verwerken van iOS-apps. Als de hash voor een verlopen certificaat is opgegeven, verwerkt en ondertekent het hulpprogramma de app, maar kan de app niet worden geïnstalleerd op apparaten.<br /><br />Controleer of het certificaat dat is verstrekt voor het ondertekenen van de verpakte app, overeenkomt met het certificaat in het inrichtingsprofiel. De App Wrapping Tool controleert niet of het certificaat in het inrichtingsprofiel overeenkomt met het certificaat dat is opgegeven voor het ondertekenen van de verpakte app.|
|Verificatie|Versleuteling werkt alleen als een apparaat een pincode heeft. Op apparaten waarop u een verpakte app hebt geïmplementeerd, wordt de gebruiker gevraagd om zich opnieuw aan te melden met een werk- of schoolaccount wanneer deze de statusbalk van het apparaat aanraakt. Het standaardbeleid in een verpakte toepassing is *verificatie bij opnieuw opstarten*. iOS verwerkt alle externe meldingen (bijvoorbeeld een telefoongesprek) door de app af te sluiten en deze vervolgens opnieuw te starten.


## <a name="setting-app-entitlements"></a>App-rechten instellen
Voordat u de app verpakt, kunt u *rechten* verlenen zodat de app over meer machtigingen en mogelijkheden beschikt dan standaard het geval is. Voor de ondertekening van de programmacode wordt gebruikgemaakt van een *rechtenbestand* om speciale machtigingen in uw app (bijvoorbeeld de toegang tot een gedeelde sleutelketen) op te geven. Specifieke app-services, ook wel *mogelijkheden* genoemd, worden in Xcode ingeschakeld tijdens het ontwikkelen van de app. Wanneer de mogelijkheden eenmaal zijn ingeschakeld, worden deze weergegeven in uw rechtenbestand. Zie [Mogelijkheden toevoegen](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) in de bibliotheek voor iOS-ontwikkelaars voor meer informatie over rechten en mogelijkheden. Zie [Ondersteunde mogelijkheden](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/SupportedCapabilities/SupportedCapabilities.html) voor een volledige lijst met ondersteunde mogelijkheden.

### <a name="supported-capabilities-for-the-app-wrapping-tool-for-ios"></a>Ondersteunde mogelijkheden voor de App Wrapping Tool voor iOS

|Mogelijkheid|Beschrijving|Aanbevolen richtlijnen|
|--------------|---------------|------------------------|
|App-groepen|Gebruik app-groepen zodat meerdere apps toegang kunnen krijgen tot gedeelde containers en sta aanvullende communicatie tussen processen van de verschillende apps toe.<br /><br />Als u app-groepen wilt inschakelen, opent u het deelvenster **Mogelijkheden** en klikt u op **AAN** in **App-groepen** . U kunt app-groepen toevoegen of bestaande app-groepen selecteren.|Pas omgekeerde DNS-notatie toe wanneer u app-groepen gebruikt:<br /><br />*group.com.companyName.AppGroup*|
|Achtergrondmodi|Wanneer u achtergrondmodi inschakelt, kan uw iOS-app op de achtergrond actief blijven.||
|Gegevensbescherming|Met de gegevensbescherming voegt u een beveiligingsniveau toe aan bestanden die op schijf zijn opgeslagen door de iOS-app. De gegevensbescherming maakt gebruik van de ingebouwde versleutelingshardware die aanwezig is op de specifieke apparaten en waarmee bestanden in een versleutelde indeling op de schijf worden opgeslagen. Uw app moet worden ingericht voor het gebruik van de gegevensbescherming.||
|Aankopen binnen apps|Bij aankopen binnen apps wordt een winkel rechtstreeks in uw app opgenomen en kunt u verbinding maken met de winkel en veilig betalingen van de gebruiker verwerken. U kunt aankopen binnen apps gebruiken voor het ontvangen van betalingen voor uitgebreide functionaliteit of voor aanvullende inhoud die kan worden gebruikt met uw app.||
|Sleutelketens delen|Wanneer u het delen van sleutelketens inschakelt, kan uw app wachtwoorden in de sleutelketen delen met andere apps die door uw team zijn ontwikkeld.|Pas omgekeerde DNS-notatie toe wanneer u gebruikmaakt van het delen van sleutelketens:<br /><br />*com.companyName.KeychainGroup*|
|Persoonlijke VPN|Sta een persoonlijk VPN toe zodat uw app een aangepaste systeemconfiguratie voor VPN kan maken en beheren met Network Extension Framework.||
|Pushmeldingen|Met de Apple Push Notification-service (APNs) kan de gebruiker via een app die actief is op de achtergrond worden geïnformeerd dat er een bericht is voor de gebruiker.|Voor pushmeldingen hebt u een app-specifiek inrichtingsprofiel nodig.<br /><br />Volg de stappen in de [Apple-documentatie voor ontwikkelaars](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html).|
|Configuratie van draadloze accessoires|Wanneer u de configuratie van draadloze accessoires inschakelt, wordt External Accessory Framework aan uw project toegevoegd en kunt u met uw app MFi Wi-Fi-accessoires instellen.||

### <a name="steps-to-enable-entitlements"></a>De stappen voor het inschakelen van rechten

1.  U schakelt als volgt mogelijkheden in uw app in:

    a.  Ga in Xcode naar het doel van uw app en klik op **Mogelijkheden**.

    b.  Schakel de gewenste mogelijkheden in. Zie [Mogelijkheden toevoegen](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) in de bibliotheek voor iOS-ontwikkelaars voor gedetailleerde informatie over elke mogelijkheid en het bepalen van de juiste waarden.

    c.  Noteer de id's die u tijdens de procedure hebt gemaakt.

    d.  Bouw en onderteken uw app zodat deze kan worden verpakt.

2.  U schakelt als volgt rechten in uw inrichtingsprofiel in:

    a.  Meld u aan bij het Apple Developer Member Center.

    b.  Maak een inrichtingsprofiel voor uw app. Zie [De vereisten voor de Intune App Wrapping Tool voor iOS ophalen](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/) voor instructies.

    c.  Schakel in het inrichtingsprofiel dezelfde rechten in als in uw app. U moet dezelfde id's gebruiken die u bij het ontwikkelen van de app hebt opgegeven.

    d.  Voer de wizard voor inrichtingsprofielen uit en download het bestand.

3.  Zorg ervoor dat u aan alle vereisten hebt voldaan en verpak de app.

### <a name="troubleshoot-common-errors-with-entitlements"></a>Veelvoorkomende problemen met rechten oplossen
Als door de App Wrapping Tool voor iOS een fout met de rechten wordt weergegeven, voert u de volgende stappen voor probleemoplossing uit.

|Probleem|Oorzaak|Oplossing|
|---------|---------|--------------|
|Het parseren van rechten die zijn gegenereerd uit de invoertoepassing is mislukt.|Het rechtenbestand dat is opgehaald uit de app kan niet door de App Wrapping Tool worden gelezen. Het rechtenbestand is mogelijk ongeldig.|Controleer het rechtenbestand voor uw app. Hieronder wordt beschreven hoe u dit doet. Controleer bij de inspectie van het rechtenbestand op ongeldige syntaxis. Het bestand moet de XML-indeling hebben.|
|Er ontbreken rechten in het inrichtingsprofiel (de ontbrekende rechten worden weergegeven). Verpak de app opnieuw met een inrichtingsprofiel dat deze rechten bevat.|De rechten die zijn ingeschakeld in het inrichtingsprofiel en de mogelijkheden die zijn ingeschakeld in de app komen niet overeen. Dit verschil geldt ook voor de id's die zijn gekoppeld aan specifieke mogelijkheden (zoals app-groepen en toegang tot de sleutelketen).|Over het algemeen is het mogelijk om een nieuw inrichtingsprofiel te maken waarmee dezelfde mogelijkheden kunnen worden ingeschakeld als voor de app. Wanneer de id’s van het profiel en de app niet overeenkomen, worden deze, indien mogelijk, door de App Wrapping Tool vervangen. Als u nog steeds deze foutmelding krijgt nadat u een nieuw inrichtingsprofiel hebt gemaakt, kunt u de rechten van de app verwijderen met de parameter –e (zie de sectie De parameter–e gebruiken om rechten te verwijderen uit een app).|

### <a name="find-the-existing-entitlements-of-a-signed-app"></a>De bestaande rechten van een ondertekende app zoeken
U kunt als volgt de bestaande rechten van een ondertekende app en inrichtingsprofiel bekijken:

1.  Ga naar het IPA-bestand en wijzig de extensie in .zip.

2.  Pak het ZIP-bestand uit. De map Payload met daarin uw app-bundel wordt weergegeven.

3.  Controleer de rechten voor de app-bundel met het hulpprogramma voor het ondertekenen van de programmacode, waarbij `YourApp.app` de werkelijke naam van uw app-bundel is:

    ```
    $ codesign -d --entitlements :- "Payload/YourApp.app"
    ```

4.  Controleer met het beveiligingsprogramma de rechten van het inrichtingsprofiel dat in de app is opgenomen, waarbij `YourApp.app` de werkelijke naam van uw app-bundel is.

    ```
    $ security -D -i "Payload/YourApp.app/embedded.mobileprovision"
    ```

### <a name="remove-entitlements-from-an-app-by-using-the-e-parameter"></a>Rechten uit een app verwijderen met de parameter –e
Met deze opdracht worden ingeschakelde mogelijkheden in de app verwijderd die niet worden vermeld in het rechtenbestand. Als u mogelijkheden verwijdert die worden gebruikt door de app, kan dit de app beschadigen. Een voorbeeld van waar u mogelijkheden met ontbrekende rechten kunt verwijderen, is in een app van een leverancier die standaard beschikt over alle mogelijkheden.

```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager –i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> –p /<path to provisioning profile> –c <SHA1 hash of the certificate> -e
```

## <a name="security-and-privacy-for-the-app-wrapping-tool"></a>Beveiliging en privacy voor de App Wrapping Tool
Gebruik de volgende aanbevolen procedures voor beveiliging en privacy wanneer u de App Wrapping Tool gebruikt.

-   Het handtekeningcertificaat, het inrichtingsprofiel en de Line-of Business-app die u opgeeft, moeten zich op de macOS-computer bevinden waarop u ook de App Wrapping Tool uitvoert. Als de bestanden zich in een UNC-pad bevinden, moet u ervoor zorgen dat ze toegankelijk zijn vanaf de macOS-computer. Het pad moet worden beveiligd via IPSec- of SMB-ondertekening.

    De verpakte toepassing die in de beheerconsole is geïmporteerd, moet zich op dezelfde computer bevinden als waarop u het hulpprogramma uitvoert. Als het bestand zich op een UNC-pad bevindt, moet u zorgen dat het toegankelijk is op de computer waarop de beheerconsole wordt uitgevoerd. Het pad moet worden beveiligd via IPSec- of SMB-ondertekening.

-   De omgeving waarnaar de App Wrapping Tool wordt gedownload vanuit de GitHub-opslagplaats, moet zijn beveiligd via IPSec- of SMB-ondertekening.

-   De app die u verwerkt, moet afkomstig zijn van een betrouwbare bron zodat bescherming tegen aanvallen gewaarborgd is.

-   Zorg ervoor dat de map voor uitvoer die u in de App Wrapping Tool hebt opgegeven is beveiligd, in het bijzonder als het een externe map is.

-   iOS-apps die een dialoogvenster voor het uploaden van bestanden bevatten, kunnen gebruikers toestaan om beperkingen voor knippen, kopiëren en plakken die gelden voor de app, te omzeilen. Zo kan een gebruiker het dialoogvenster voor het uploaden van bestanden bijvoorbeeld gebruiken om een schermopname van de app-gegevens te uploaden.

-   Wanneer u de documentenmap op uw apparaat bewaakt vanuit een verpakte app, ziet u mogelijk een map met de naam .msftintuneapplauncher. Als deze map wordt gewijzigd of verwijderd, kan dit van invloed zijn op de goede werking van beperkte apps.

### <a name="see-also"></a>Zie tevens
- [Bepalen hoe u apps voorbereidt op Mobile Application Management met Microsoft Intune](apps-prepare-mobile-application-management.md)</br>
- [Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)</br>
- [De SDK gebruiken om apps geschikt te maken voor Mobile Application Management](/intune-classic/deploy-use/use-the-sdk-to-enable-apps-for-mobile-application-management)
