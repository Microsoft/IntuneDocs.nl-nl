---
title: macOS-apparaatinstellingen in Microsoft Intune - Azure | Microsoft Docs
titleSuffix: ''
description: U kunt instellingen voor macOS-apparaten toevoegen, configureren of maken om functies te beperken, zoals wachtwoordvereisten instellen, het vergrendelingsscherm beheren, ingebouwde apps gebruiken, beperkte of goedgekeurde apps toevoegen, bluetooth-apparaten verwerken, verbinding maken met de cloud voor back-up en opslag, de kioskmodus inschakelen, domeinen toevoegen, en bepalen hoe gebruikers de Safari-webbrowser kunnen gebruiken in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/22/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6513c09f252d5a914ace4e57e5a593877a387172
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2019
ms.locfileid: "75206547"
---
# <a name="macos-device-settings-to-allow-or-restrict-features-using-intune"></a>Met macOS-apparaatinstellingen kunt u functies toestaan of beperken met behulp van Intune



In dit artikel vindt u een overzicht en beschrijving van de verschillende instellingen die u kunt beheren op macOS-apparaten. Gebruik deze instellingen als onderdeel van de MDM-oplossing (Mobile Device Management) om functies toe te staan of uit te schakelen, wachtwoordregels in te stellen, bepaalde apps toe te staan of te beperken en nog veel meer.

Deze instellingen worden toegevoegd aan een apparaatconfiguratieprofiel in Intune en vervolgens toegewezen aan of geïmplementeerd op uw macOS-apparaten.

## <a name="before-you-begin"></a>Voordat u begint

[Maak een configuratieprofiel voor apparaatbeperkingen](../device-restrictions-configure.md).

> [!NOTE]
> Deze instellingen zijn van toepassing op verschillende inschrijvings typen. Zie voor meer informatie over de verschillende inschrijvings typen [macOS-inschrijving](../macos-enroll.md).

## <a name="general"></a>Algemeen

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>Instellingen zijn van toepassing op: registratie van apparaten en automatische apparaatregistratie

- **Definitie opzoeken**: Met **Blokkeren** voorkomt u dat de gebruiker een woord markeert en vervolgens de definitie ervan opzoekt op het apparaat. **Niet geconfigureerd** (standaard): geeft toegang tot de functie Opzoeken van definities van woorden.
- **Dicteren**: Met **Blokkeren** zorgt u ervoor dat de gebruiker geen spraak meer kan gebruiken om tekst in te voeren. **Niet geconfigureerd** (standaard): staat de gebruiker toe invoer van Dicteren te gebruiken.
- **Cacheopslag van inhoud**: Kies **Niet geconfigureerd** (standaard) om opslag van inhoud in cache mogelijk te maken. Met cacheopslag van inhoud worden app-gegevens, webbrowsergegevens, downloads en meer lokale items op het apparaat opgeslagen. Selecteer **Blokkeren** om te voorkomen dat deze gegevens in de cache worden opgeslagen.

  Zie [Cacheopslag van inhoud beheren op een Mac](https://support.apple.com/guide/mac-help/manage-content-caching-on-mac-mchl3b6c3720/mac) (hiermee wordt een andere website geopend) voor meer informatie over cacheopslag van inhoud in macOS.

  Deze functie is van toepassing op:  
  - macOS 10.13 en hoger

- **Software-updates uitstellen**: Als de waarde is ingesteld op **Niet geconfigureerd** (standaard), worden software-updates weergegeven op het apparaat wanneer Apple deze uitbrengt. Als Apple bijvoorbeeld op een bepaalde datum een macOS-update uitbrengt, wordt deze update rond de releasedatum automatisch op het apparaat weergegeven. Seed-buildupdates zijn zonder vertraging toegestaan.

  Met **Inschakelen** kunt u het weergeven van software-updates op apparaten uitstellen, van 0-90 dagen. Deze instelling bepaalt niet wanneer updates wel of niet worden geïnstalleerd. 

  - **De zichtbaarheid van software-updates vertragen**: Voer een waarde in tussen 0 en 90 dagen. Wanneer de vertraging verloopt, krijgen gebruikers een melding om een update uit te voeren naar de vroegste versie van het besturingssysteem die beschikbaar was toen de vertraging werd geactiveerd.

    Als een macOS-update bijvoorbeeld beschikbaar komt op **1 januari** en **Zichtbaarheid vertragen** is ingesteld op **5 dagen**, wordt de update niet als beschikbare update weergegeven. Op de **zesde dag** na de release komt deze update beschikbaar en kunnen eindgebruikers deze installeren.

    Deze functie is van toepassing op:  
    - macOS 10.13.4 en hoger

- **Scherm afbeeldingen**: het apparaat moet zijn Inge schreven bij de Apple-registratie voor geautomatiseerd apparaat (DEP). Als deze functie is ingesteld op **blok keren**, kunnen gebruikers geen scherm opname van de weer gave opslaan. Ook wordt voor komen dat de app klas lokaal externe schermen waarneemt. **Niet geconfigureerd** (standaard) Hiermee kunnen gebruikers scherm afbeeldingen vastleggen en kan de app class externe schermen weer geven.

### <a name="settings-apply-to-automated-device-enrollment"></a>Instellingen zijn van toepassing op: automatische registratie van apparaten

- **Waarneming van het externe scherm via de leslokaal-app**: **uitschakelen** voor komt dat docenten de klassikale app gebruiken om de schermen van de cursisten te bekijken. **Niet geconfigureerd** (standaard) Hiermee kunnen docenten hun schermen van studenten bekijken.

  Als u deze instelling wilt gebruiken, stelt u de instelling **scherm opnamen** in op **niet geconfigureerd** (scherm afbeeldingen zijn toegestaan).

- **Observatie van het scherm wordt niet gevraagd door de klas-app**: **toestaan** kunnen docenten de schermen van de studenten zien zonder dat de student akkoord gaat. **Niet geconfigureerd** (standaard) Hiermee moet de student overeenkomen voordat de docent de schermen kan zien.

  Als u deze instelling wilt gebruiken, stelt u de instelling **scherm opnamen** in op **niet geconfigureerd** (scherm afbeeldingen zijn toegestaan).

- **Studenten moeten toestemming vragen voor het verlaten van de klas class**: **vereisen dat** studenten die zijn Inge schreven in een niet-beheerde klassikale cursus om goed keuring van docenten te krijgen om de cursus te verlaten. **Niet geconfigureerd** (standaard) Hiermee kan student de cursus verlaten wanneer de student kiest.

- **Docenten kunnen apparaten of apps automatisch vergren delen in de app class**: **Allow toestaan dat** docenten het apparaat of de app van een student vergren delen zonder de goed keuring van de student. **Niet geconfigureerd** (standaard) Hiermee moet de student overeenkomen voordat de docent het apparaat of de app kan vergren delen.

- **Studenten kunnen automatisch lid worden van een klas lokaal**: toestaan laat studenten **toe** aan een klasse zonder de docent te vragen. **Niet geconfigureerd** (standaard) vereist docenten goedkeuring om lid te worden van een klasse.

## <a name="password"></a>Wachtwoord

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>Instellingen zijn van toepassing op: registratie van apparaten en automatische apparaatregistratie

- **Wachtwoord**: **Vereisen** dat de eindgebruiker een wachtwoord invoert voor toegang tot het apparaat. **Niet geconfigureerd** (standaard) vereist geen wacht woord. Er worden ook geen beperkingen afgedwongen, zoals het blok keren van eenvoudige wacht woorden of het instellen van een minimum lengte.
  - **Vereist wachtwoordtype**: Hier geeft u op of het wachtwoord alleen numerieke tekens mag bevatten of dat het wachtwoord alfanumeriek moet zijn (en dus letters en cijfers moet bevatten).

    Deze functie is van toepassing op:  
    - macOS 10.10.3 en hoger

  - **Het aantal niet-alfanumerieke tekens in het wachtwoord**: Hier geeft u op hoeveel complexe tekens zijn vereist in het wachtwoord (tussen **0** en **4**).<br>Een complex teken is een symbool zoals ‘ **?** ’.
  - **Minimale wachtwoordlengte**: Voer de minimumlengte van het wachtwoord in dat een gebruiker moet opgeven (tussen **4** en **16** tekens).
  - **Eenvoudige wachtwoorden**: Hier stelt u in dat eenvoudige wachtwoorden mogen worden gebruikt, zoals **0000** en **1234**.
  - **Maximum aantal minuten na schermvergrendeling voordat wachtwoord is vereist**: Hier geeft u op hoe lang de computer inactief moet zijn voordat een wachtwoord vereist is om te ontgrendelen.
  - **Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld**: Hier geeft u de tijdsduur op die de computer inactief moet zijn voordat het scherm wordt vergrendeld.
  - **Wachtwoordverlooptijd (dagen)** : Hier geeft u op na hoeveel dagen de gebruiker het wachtwoord moet wijzigen (tussen **1** en **255** dagen).
  - **Wachtwoorden niet opnieuw gebruiken**: Voer het aantal eerder gebruikte wachtwoorden in dat niet opnieuw mag worden gebruikt, van **1** tot **24**.

- **Blokkeren dat gebruiker de wachtwoordcode wijzigt**: Selecteer **Blokkeren** om ervoor te zorgen dat de wachtwoordcode niet meer kan worden gewijzigd, toegevoegd of verwijderd. **Niet geconfigureerd** (standaard): staat toe dat wachtwoordcodes worden toegevoegd, gewijzigd of verwijderd.
- **Ontgrendelen met vingerafdruk blokkeren**: Selecteer **Blokkeren** om te voorkomen dat vingerafdrukken kunnen worden gebruikt om het apparaat te ontgrendelen. **Niet geconfigureerd** (standaard): staat de gebruiker toe het apparaat te ontgrendelen met een vingerafdruk.

- **Automatisch wachtwoorden invullen blokkeren**: Selecteer **Blokkeren** om te voorkomen dat de functie Wachtwoorden automatisch invullen wordt gebruikt in macOS. Als u **Blokkeren** kiest, heeft dat ook de volgende gevolgen:

  - Gebruikers wordt niet meer gevraagd om een wachtwoord te gebruiken dat is opgeslagen in Safari of in een app.
  - Automatische sterke wachtwoorden zijn uitgeschakeld en gebruikers krijgen geen suggesties voor sterke wachtwoorden.

  **Niet geconfigureerd** (standaard) staat deze functies toe.

- **Aanvragen voor wachtwoordnabijheid blokkeren**: Selecteer **Blokkeren**, zodat het apparaat van een gebruiker geen wachtwoorden aanvraagt van apparaten in de omgeving. **Niet geconfigureerd** (standaard): staat deze wachtwoordaanvragen toe.

- **Wachtwoorden delen blokkeren**: Selecteer **Blokkeren** om te voorkomen dat wachtwoorden via AirDrop tussen apparaten worden gedeeld. **Niet geconfigureerd** (standaard): staat toe dat wachtwoorden worden gedeeld.

## <a name="built-in-apps"></a>Ingebouwde apps

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>Instellingen zijn van toepassing op: registratie van apparaten en automatische apparaatregistratie

- **Automatisch invullen in Safari blokkeren**: Selecteer **Blokkeren** om de functie Automatisch invullen in Safari op het apparaat uit te schakelen. **Niet geconfigureerd** (standaard): staat gebruikers toe de instellingen voor automatisch doorvoeren te wijzigen in de webbrowser.
- **Camera blokkeren**: Met **Blokkeren** voorkomt u toegang tot de camera op het apparaat. **Niet geconfigureerd** (standaard): staat toegang tot de camera van het apparaat toe.
- **Apple Music blokkeren**: Met **Blokkeren** keert u terug naar de klassieke modus van de app Muziek en wordt de Muziek-service uitgeschakeld. **Niet geconfigureerd** (standaard): staat het gebruik van de app Apple Music toe.
- **Zoekresultaten van internet blokkeren in Spotlight**: Met **Blokkeren** zorgt u ervoor dat Spotlight geen resultaten meer retourneert na een zoekopdracht op internet. **Niet geconfigureerd** (standaard): staat Zoeken met Spotlight toe om verbinding te maken met internet voor zoekresultaten.
- **Bestandsoverdracht via iTunes blokkeren**: Met **Blokkeren** worden services voor het delen van toepassingsbestanden uitgeschakeld. Met **Niet geconfigureerd** (standaard) zijn services voor het delen van toepassingsbestanden toegestaan.

  Deze functie is van toepassing op:  
  - macOS 10.13 en hoger

## <a name="restricted-apps"></a>Beperkte apps

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>Instellingen zijn van toepassing op: registratie van apparaten en automatische apparaatregistratie

- **Lijst met beperkte apps**: een lijst met apps maken die gebruikers niet mogen installeren of gebruiken. Uw opties zijn:

  - **Niet geconfigureerd** (standaard): er zijn geen beperkingen ten opzichte van intune. Gebruikers hebben toegang tot apps die u toewijst en ingebouwde apps.
  - **Niet-toegestane apps**: Apps die niet worden beheerd in Intune waarvan u niet wilt dat deze op het apparaat worden geïnstalleerd. Gebruikers kunnen geen verboden apps installeren. Maar als een gebruiker een app uit deze lijst installeert, wordt deze in intune gerapporteerd.
  - **Goedgekeurde apps**: Apps die gebruikers mogen installeren. Gebruikers mogen geen apps installeren die niet worden vermeld. Apps die worden beheerd door Intune, zijn automatisch toegestaan. Er wordt niet voorkomen dat gebruikers een app installeren die niet in de goedgekeurde lijst wordt vermeld. Maar als dat wel het geval is, wordt deze in intune gerapporteerd.
- **App-bundel-id**: Voer de [App-bundel-id](bundle-ids-built-in-ios-apps.md) van de gewenste app in. U kunt ingebouwde apps en line-of-Business-Apps weer geven of verbergen. De website van Apple bevat een lijst met [ingebouwde Apple-apps](https://support.apple.com/HT208094).
- **App-naam**: Voer de naam van de gewenste app in. U kunt ingebouwde apps en line-of-Business-Apps weer geven of verbergen. De website van Apple bevat een lijst met [ingebouwde Apple-apps](https://support.apple.com/HT208094).
- **Uitgever**: Voer de uitgever van de gewenste app in.

Als u apps wilt toevoegen aan deze lijsten, kunt u:

- **Toevoegen**: Selecteer deze optie om de lijst met apps te maken.
- **Importeer** een CSV-bestand met details van de app, waaronder de URL. Gebruik de notatie `<app bundle ID>, <app name>, <app publisher>`. U kunt ook **exporteren** om een lijst met apps te maken die u hebt toegevoegd, in dezelfde indeling.

## <a name="connected-devices"></a>Verbonden apparaten

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>Instellingen zijn van toepassing op: registratie van apparaten en automatische apparaatregistratie

- **AirDrop blokkeren**: Selecteer **Blokkeren** om het gebruik van AirDrop op het apparaat te voorkomen. **Niet geconfigureerd** (standaard): staat het gebruik van de functie AirDrop toe voor het uitwisselen van inhoud met apparaten in de omgeving.
- **Automatisch ontgrendelen via Apple Watch blokkeren**: Met **Blokkeren** voorkomt u dat gebruikers hun macOS-apparaat ontgrendelen met hun Apple Watch. Met **Niet geconfigureerd** (standaard) kunnen gebruikers hun macOS-apparaat ontgrendelen met hun Apple Watch.

## <a name="cloud-and-storage"></a>Cloud en opslag

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>Instellingen zijn van toepassing op: registratie van apparaten en automatische apparaatregistratie

- **Synchronisatie van iCloud-sleutelhanger blokkeren**: Selecteer **Blokkeren** om het synchroniseren van referenties die zijn opgeslagen in de Sleutelhanger, naar iCloud uit te schakelen. **Niet geconfigureerd** (standaard): staat gebruikers toe deze referenties te synchroniseren.
- **Synchronisatie van clouddocumenten blokkeren**: **Blokkeren**: voorkomt dat documenten en gegevens worden gesynchroniseerd met iCloud. Met **Niet geconfigureerd** (standaard) staat u het synchroniseren van documenten en sleutelwaarden met uw iCloud-opslagruimte toe.
- **Back-up van iCloud-mail blokkeren**: Met **Blokkeren** voorkomt u synchronisatie van de app Mail van macOS met iCloud. **Niet geconfigureerd** (standaard) staat synchronisatie van Mail met iCloud toe.
- **Back-up van iCloud-contactpersonen blokkeren**: Met **Blokkeren** voorkomt u synchronisatie van contactpersonen op het apparaat met iCloud. **Niet geconfigureerd** (standaard) staat synchronisatie van contactpersonen met behulp van iCloud toe.
- **Back-up van iCloud-agenda blokkeren**: Met **Blokkeren** voorkomt u synchronisatie van de app Agenda van macOS met iCloud. **Niet geconfigureerd** (standaard) staat synchronisatie van Agenda met iCloud toe.
- **Back-up van iCloud-herinneringen blokkeren**: Met **Blokkeren** voorkomt u synchronisatie van de app Herinneringen van macOS met iCloud. **Niet geconfigureerd** (standaard) staat synchronisatie van Herinneringen met iCloud toe.
- **Back-up van iCloud-bladwijzers blokkeren**: Met **Blokkeren** voorkomt u synchronisatie van bladwijzers op het apparaat met iCloud. **Niet geconfigureerd** (standaard) staat synchronisatie van Bladwijzers met iCloud toe.
- **Back-up van iCloud-notities blokkeren**: Met **Blokkeren** voorkomt u synchronisatie van notities op het apparaat met iCloud. **Niet geconfigureerd** (standaard) staat synchronisatie van Notities met iCloud toe.
- **Icloud-foto bibliotheek blok keren**: met **blok** keren wordt de icloud-foto bibliotheek uitgeschakeld en wordt voor komen dat icloud foto's van de apparaten synchroniseert. Foto's die niet volledig uit de iCloud-fotobibliotheek zijn gedownload, worden verwijderd uit de lokale opslag van het apparaat. **Niet geconfigureerd** (standaard) Hiermee staat u toe dat Foto's worden gesynchroniseerd tussen het apparaat en de ICloud-foto bibliotheek.
- Te **leveren:** **niet geconfigureerd** (standaard) Hiermee kunnen gebruikers beginnen met een macOS-apparaat en vervolgens het werk voortzetten dat ze op een ander IOS-of macOS-apparaat hebben gestart. **Blok keren** dat de bewaarde functie op het apparaat wordt voor komen. 

  Deze functie is van toepassing op:  
  - macOS 10.15 of hoger

## <a name="domains"></a>Domains

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>Instellingen zijn van toepassing op: registratie van apparaten en automatische apparaatregistratie

- **URL voor e-maildomein**: U kunt een of meer URL's **Toevoegen** aan de lijst. Wanneer gebruikers een e-mail ontvangen die afkomstig is van een ander domein dan het domein dat u hebt geconfigureerd, wordt de e-mail in de macOS-app Mail gemarkeerd als niet-vertrouwd.

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](../device-profile-assign.md) en [de status ervan controleren](../device-profile-monitor.md).

U kunt ook apparaatfuncties en -instellingen beperken op [iOS](../device-restrictions-ios.md)-apparaten.
