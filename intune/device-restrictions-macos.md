---
title: macOS-apparaatinstellingen in Microsoft Intune - Azure | Microsoft Docs
titlesuffix: ''
description: U kunt instellingen voor macOS-apparaten toevoegen, configureren of maken om functies te beperken, zoals wachtwoordvereisten instellen, het vergrendelingsscherm beheren, ingebouwde apps gebruiken, beperkte of goedgekeurde apps toevoegen, bluetooth-apparaten verwerken, verbinding maken met de cloud voor back-up en opslag, de kioskmodus inschakelen, domeinen toevoegen, en bepalen hoe gebruikers de Safari-webbrowser kunnen gebruiken in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/13/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4fa6a68d1b5a8d2ccf87587ecab36c7807770d48
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57565346"
---
# <a name="macos-device-settings-to-allow-or-restrict-features-using-intune"></a>Met macOS-apparaatinstellingen kunt u functies toestaan of beperken met behulp van Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In dit artikel vindt u een overzicht en beschrijving van de verschillende instellingen die u kunt beheren op macOS-apparaten. Gebruik deze instellingen als onderdeel van de MDM-oplossing (Mobile Device Management) om functies toe te staan of uit te schakelen, wachtwoordregels in te stellen, bepaalde apps toe te staan of te beperken en nog veel meer.

Deze instellingen worden toegevoegd aan een apparaatconfiguratieprofiel in Intune en vervolgens toegewezen aan of geïmplementeerd op uw macOS-apparaten.

## <a name="before-you-begin"></a>Voordat u begint

[Maken van een apparaatconfiguratieprofiel voor beperkingen](device-restrictions-configure.md#create-the-profile).

## <a name="general"></a>Algemeen

- **Opzoeken van definities blokkeren**: **Blokkeren** voorkomt dat de gebruiker een woord markeert en vervolgens de definitie ervan opzoekt op het apparaat. **Niet geconfigureerd** (standaard): geeft toegang tot de functie Opzoeken van definities van woorden.
- **Dicteren blokkeren**: met **Blokkeren** zorgt u ervoor dat de gebruiker geen spraak meer kan gebruiken om tekst in te voeren. **Niet geconfigureerd** (standaard): staat de gebruiker toe invoer van Dicteren te gebruiken.
- **Inhoud in cache opslaan blokkeren**: kies **niet geconfigureerd** (standaard) waarmee de inhoud in cache opslaan. Inhoud in cache opslaan, slaat app-gegevens, web browsergegevens, downloads en meer lokaal op het apparaat. Selecteer **blok** om te voorkomen dat deze gegevens worden opgeslagen in de cache.

  Zie voor meer informatie over de inhoud in cache opslaan op macOS, [beheren van inhoud in cache opslaan op een Mac](https://support.apple.com/guide/mac-help/manage-content-caching-on-mac-mchl3b6c3720/mac) (opent u een andere website).

  Deze functie is van toepassing op:  
  - macOS 10.13 of hoger

- **(Alleen onder supervisie) softwareupdates uitstellen**: als de waarde **niet geconfigureerd** (standaard), software-updates worden weergegeven op het apparaat als Apple worden vrijgegeven. Bijvoorbeeld, als een macOS-update opgehaald die zijn uitgebracht door Apple op een specifieke datum, wordt klikt u vervolgens deze update op een natuurlijke manier weergegeven op het apparaat om de releasedatum.

  **Schakel** kunt u als de software-updates worden weergegeven op apparaten van 0-90 dagen vertraging. Deze instelling bepalen niet wanneer updates worden of niet zijn geïnstalleerd. 

  - **Zichtbaarheid van de software-updates uitstellen**: Voer een waarde van 0-90 dagen. Wanneer de vertraging verloopt, krijgen gebruikers een melding om een update uit te voeren naar de vroegste versie van het besturingssysteem die beschikbaar was toen de vertraging werd geactiveerd.

    Bijvoorbeeld, als een macOS-update is beschikbaar op **1 januari**, en **vertraging zichtbaarheid** is ingesteld op **5 dagen**, en vervolgens de update wordt niet als een update beschikbaar op apparaten weergegeven. Op de **zesde dag** na de release, de dat update beschikbaar is, en eindgebruikers kunnen installeren.

    Deze functie is van toepassing op:  
    - macOS 10.13.4 of hoger

## <a name="password"></a>Wachtwoord

- **Wachtwoord**: kies **Vereisen** om af te dwingen dat de eindgebruiker een wachtwoord moet invoeren voor toegang tot het apparaat. **Niet geconfigureerd** (standaard) geen een wachtwoord vereist en de beperkingen, zoals eenvoudige wachtwoorden blokkeren of het instellen van een minimumlengte niet afdwingen.
  - **Vereist wachtwoordtype**: hiermee geeft u op of het wachtwoord alleen numerieke tekens mag bevatten of dat het wachtwoord alfanumeriek moet zijn (en dus letters en cijfers moet bevatten). Deze instelling wordt alleen ondersteund op Mac OS X-versie 10.10.3 en hoger.
  - **Het minimumaantal niet-alfanumerieke tekens in een wachtwoord**: hiermee geeft u het aantal complexe tekens (tussen **0** en **4** tekens) op dat het wachtwoord moet bevatten.<br>Een complex teken is een symbool zoals ‘**?**’.
  - **Minimale wachtwoordlengte**: voer de minimale lengte van het wachtwoord in dat een gebruiker moet configureren (tussen **4** en **16** tekens).
  - **Eenvoudige wachtwoorden**: hiermee stelt u in dat eenvoudige wachtwoorden mogen worden gebruikt, zoals **0000** en **1234**.
  - **Maximum aantal minuten waarna een wachtwoord voor het vergrendelde scherm is vereist**: hiermee geeft u op hoe lang de computer inactief moet zijn voordat een wachtwoord is vereist om te ontgrendelen.
  - **Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld**: hiermee geeft u de hoeveelheid tijd op die de computer inactief moet zijn voordat het scherm wordt vergrendeld.
  - **Wachtwoord verloopt (dagen)**: hiermee geeft u op na hoeveel dagen de gebruiker het wachtwoord moet wijzigen (tussen **1** en **255** dagen).
  - **Wachtwoorden niet opnieuw gebruiken**: hiermee geeft u op hoeveel eerder gebruikte wachtwoorden niet opnieuw mogen worden gebruikt (tussen **1** en **24**).

- **Aanpassing van wachtwoordcode blokkeren dat gebruiker**: kies **blok** stoppen van de wachtwoordcode wordt gewijzigd, toegevoegd of verwijderd. **Niet geconfigureerd** (standaard): staat toe dat wachtwoordcodes worden toegevoegd, gewijzigd of verwijderd.
- **Ontgrendelen met vingerafdruk blokkeren**: kies **Blokkeren** om te voorkomen dat vingerafdrukken kunnen worden gebruikt om het apparaat te ontgrendelen. **Niet geconfigureerd** (standaard): staat de gebruiker toe het apparaat te ontgrendelen met een vingerafdruk.

- **Automatisch wachtwoorden doorvoeren blokkeren**: kies **Blokkeren** om te voorkomen dat de functie Wachtwoorden automatisch doorvoeren wordt gebruikt in macOS. Kiezen **blok** heeft ook de volgende gevolgen:

  - Gebruikers wordt niet meer gevraagd om een wachtwoord te gebruiken dat is opgeslagen in Safari of in een app.
  - Automatische sterke wachtwoorden zijn uitgeschakeld en gebruikers krijgen geen suggesties voor sterke wachtwoorden.

  **Niet geconfigureerd** (standaard) staat deze functies toe.

- **Aanvragen voor wachtwoordnabijheid blokkeren**: kies **Blokkeren** zodat het apparaat van een gebruiker geen wachtwoorden aanvraagt van apparaten in de buurt. **Niet geconfigureerd** (standaard): staat deze wachtwoordaanvragen toe.

- **Delen van wachtwoorden blokkeren**: **Blokkeren** voorkomt het delen van wachtwoorden tussen apparaten via AirDrop. **Niet geconfigureerd** (standaard): staat toe dat wachtwoorden worden gedeeld.

## <a name="built-in-apps"></a>Ingebouwde apps

- **Automatisch doorvoeren in Safari blokkeren**: met **Blokkeren** wordt de functie Automatisch doorvoeren in Safari uitgeschakeld op het apparaat. **Niet geconfigureerd** (standaard): staat gebruikers toe de instellingen voor automatisch doorvoeren te wijzigen in de webbrowser.
- **Camera blokkeren**: kies **Blokkeren** als u de toegang tot de camera op het apparaat wilt blokkeren. **Niet geconfigureerd** (standaard): staat toegang tot de camera van het apparaat toe.
- **Apple Music blokkeren**: met **Blokkeren** keert u terug naar de klassieke modus van de app Muziek en wordt de Muziek-service uitgeschakeld. **Niet geconfigureerd** (standaard): staat het gebruik van de app Apple Music toe.
- **Blok zoeken Internetresultaten van Spotlight**: **blok** voorkomt dat Spotlight retourneren van resultaten van een Internet-zoekopdracht. **Niet geconfigureerd** (standaard): staat Zoeken met Spotlight toe om verbinding te maken met internet voor zoekresultaten.
- **Blok-bestandsoverdracht gebruiken iTunes**: **blok** services voor bestandsdeling toepassing uitgeschakeld. Beschikbaar in macOS 10.13 en hoger. **Niet geconfigureerd** (standaard) kunt u services voor bestandsdeling toepassing.

## <a name="restricted-apps"></a>Beperkte apps

Configureer een van de volgende lijsten in de lijst met beperkte apps:

- Lijst met **niet-toegestane apps**: hiermee maakt u een lijst met apps die niet worden beheerd door Intune en die gebruikers niet mogen installeren en uitvoeren. Worden niet voorkomen dat gebruikers een niet-toegestane app installeren, maar indien dit het geval is, wordt dit apparaat gerapporteerd aan de beheerder.
- Lijst met **goedgekeurde apps**: hiermee maakt u een lijst met apps die gebruikers mogen installeren. Gebruikers mogen geen apps installeren die niet worden vermeld. Apps die worden beheerd door Intune, zijn automatisch toegestaan. Worden niet voorkomen dat gebruikers een app installeren die niet in de goedgekeurde lijst. Maar indien dit het geval is, wordt dit apparaat gerapporteerd aan de beheerder.

Als u de lijst wilt configureren, klikt u op **Toevoegen** en geeft u een naam van uw keuze op, eventueel de uitgever van de app, en de bundel-ID van de app (bijvoorbeeld *com.apple.calculator*).

## <a name="connected-devices"></a>Verbonden apparaten

- **AirDrop blokkeren**: selecteer **Blokkeren** om het gebruik van AirDrop op het apparaat te voorkomen. **Niet geconfigureerd** (standaard): staat het gebruik van de functie AirDrop toe voor het uitwisselen van inhoud met apparaten in de omgeving.
- **Blok Apple Watch automatisch ontgrendelen**: **blok** wordt voorkomen dat gebruikers hun macOS-apparaat met hun Apple Watch te ontgrendelen. **Niet geconfigureerd** (standaard) kan gebruikers hun macOS-apparaat met hun Apple Watch kan worden ontgrendeld.

## <a name="cloud-and-storage"></a>Cloud en opslag

- **Synchronisatie van iCloud-sleutelhanger blokkeren**: kies **Blokkeren** om het synchroniseren van referenties die zijn opgeslagen in de Sleutelhanger, naar iCloud uit te schakelen. **Niet geconfigureerd** (standaard): staat gebruikers toe deze referenties te synchroniseren.
- **Synchronisatie van documenten iCloud blokkeren**: **blok** voorkomt u dat iCloud synchroniseren van documenten en gegevens. Met **Niet geconfigureerd** (standaard) staat u het synchroniseren van documenten en sleutelwaarden met uw iCloud-opslagruimte toe.
- **ICloud-back-up van e-Mail blokkeren**: **blok** voorkomt u dat iCloud worden gesynchroniseerd met de e-Mail-app voor macOS. **Niet geconfigureerd** (standaard) e-Mail de synchronisatie met iCloud toestaan.
- **Neem contact op met back-up iCloud blokkeren**: **blok** iCloud voorkomt u dat de apparaten-contactpersonen worden gesynchroniseerd. **Niet geconfigureerd** (standaard) kunt u contact op met synchronisatie met iCloud.
- **ICloud-back-up agenda blokkeren**: **blok** voorkomt u dat iCloud worden gesynchroniseerd met de app voor macOS-agenda. **Niet geconfigureerd** (standaard) agenda de synchronisatie met iCloud toestaan.
- **ICloud-back-up herinnering blokkeren**: **blok** voorkomt u dat iCloud worden gesynchroniseerd met de app voor macOS herinneringen. **Niet geconfigureerd** (standaard) herinneringen voor de synchronisatie met iCloud toestaan.
- **ICloud-back-up van de bladwijzer blokkeren**: **blok** voorkomt u dat iCloud synchroniseren van de apparaten bladwijzers. **Niet geconfigureerd** (standaard) bladwijzer de synchronisatie met iCloud toestaan.
- **ICloud opmerkingen bij de back-up blokkeren**: **blok** iCloud voorkomt u dat de apparaten opmerkingen bij de synchronisatie. **Niet geconfigureerd** (standaard) opmerkingen bij de synchronisatie met iCloud toestaan.

## <a name="domains"></a>Domains

- **E-maildomein-URL**: voeg een of meer URL's toe aan de lijst. Wanneer gebruikers een e-mail ontvangen die afkomstig is van een ander domein dan het domein dat u hebt geconfigureerd, wordt de e-mail in de macOS Mail-app gemarkeerd als niet-vertrouwd.

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

U kunt de instellingen en functies van het apparaat ook beperken op [iOS](device-restrictions-ios.md) apparaten.