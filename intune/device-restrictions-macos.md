---
title: macOS-apparaatinstellingen in Microsoft Intune - Azure | Microsoft Docs
titleSuffix: ''
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
ms.openlocfilehash: 5feec66e791da4038bd069cdad69a7ba573f27f3
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2019
ms.locfileid: "58798374"
---
# <a name="macos-device-settings-to-allow-or-restrict-features-using-intune"></a>Met macOS-apparaatinstellingen kunt u functies toestaan of beperken met behulp van Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In dit artikel vindt u een overzicht en beschrijving van de verschillende instellingen die u kunt beheren op macOS-apparaten. Gebruik deze instellingen als onderdeel van de MDM-oplossing (Mobile Device Management) om functies toe te staan of uit te schakelen, wachtwoordregels in te stellen, bepaalde apps toe te staan of te beperken en nog veel meer.

Deze instellingen worden toegevoegd aan een apparaatconfiguratieprofiel in Intune en vervolgens toegewezen aan of geïmplementeerd op uw macOS-apparaten.

## <a name="before-you-begin"></a>Voordat u begint

[Maak een configuratieprofiel voor apparaatbeperkingen](device-restrictions-configure.md#create-the-profile).

## <a name="general"></a>Algemeen

- **Opzoeken van definities blokkeren**: **Blokkeren** voorkomt dat de gebruiker een woord markeert en vervolgens de definitie ervan opzoekt op het apparaat. **Niet geconfigureerd** (standaard): geeft toegang tot de functie Opzoeken van definities van woorden.
- **Dicteren blokkeren**: met **Blokkeren** zorgt u ervoor dat de gebruiker geen spraak meer kan gebruiken om tekst in te voeren. **Niet geconfigureerd** (standaard): staat de gebruiker toe invoer van Dicteren te gebruiken.
- **Cacheopslag van inhoud blokkeren**: Kies **Niet geconfigureerd** (standaard) om cacheopslag van inhoud mogelijk te maken. Met cacheopslag van inhoud worden app-gegevens, webbrowsergegevens, downloads en meer lokale items op het apparaat opgeslagen. Selecteer **Blokkeren** om te voorkomen dat deze gegevens in de cache worden opgeslagen.

  Zie [Cacheopslag van inhoud beheren op een Mac](https://support.apple.com/guide/mac-help/manage-content-caching-on-mac-mchl3b6c3720/mac) (hiermee wordt een andere website geopend) voor meer informatie over cacheopslag van inhoud in macOS.

  Deze functie is van toepassing op:  
  - macOS 10.13 of hoger

- **Software-updates uitstellen**: Als de waarde is ingesteld op **Niet geconfigureerd** (standaard), worden software-updates weergegeven op het apparaat wanneer Apple deze uitbrengt. Als Apple bijvoorbeeld op een bepaalde datum een macOS-update uitbrengt, wordt deze update rond de releasedatum automatisch op het apparaat weergegeven. Seed-buildupdates zijn zonder vertraging toegestaan.

  Met **Inschakelen** kunt u het weergeven van software-updates op apparaten uitstellen, van 0-90 dagen. Deze instelling bepaalt niet wanneer updates wel of niet worden geïnstalleerd. 

  - **De zichtbaarheid van software-updates vertragen**: Voer een waarde van 0-90 dagen in. Wanneer de vertraging verloopt, krijgen gebruikers een melding om een update uit te voeren naar de vroegste versie van het besturingssysteem die beschikbaar was toen de vertraging werd geactiveerd.

    Als een macOS-update bijvoorbeeld beschikbaar komt op **1 januari** en **Zichtbaarheid vertragen** is ingesteld op **5 dagen**, wordt de update niet als beschikbare update weergeven op apparaten. Op de **zesde dag** na de release komt deze update beschikbaar en kunnen eindgebruikers deze installeren.

    Deze functie is van toepassing op:  
    - macOS 10.13.4 of hoger

## <a name="password"></a>Wachtwoord

- **Wachtwoord**: kies **Vereisen** om af te dwingen dat de eindgebruiker een wachtwoord moet invoeren voor toegang tot het apparaat. Met **Niet geconfigureerd** (standaard) is er geen wachtwoord vereist en worden er geen beperkingen afgedwongen, zoals het blokkeren van eenvoudige wachtwoorden of het instellen van een minimumlengte.
  - **Vereist wachtwoordtype**: hiermee geeft u op of het wachtwoord alleen numerieke tekens mag bevatten of dat het wachtwoord alfanumeriek moet zijn (en dus letters en cijfers moet bevatten). Deze instelling wordt alleen ondersteund op Mac OS X-versie 10.10.3 en hoger.
  - **Het minimumaantal niet-alfanumerieke tekens in een wachtwoord**: hiermee geeft u het aantal complexe tekens (tussen **0** en **4** tekens) op dat het wachtwoord moet bevatten.<br>Een complex teken is een symbool zoals ‘**?**’.
  - **Minimale wachtwoordlengte**: voer de minimale lengte van het wachtwoord in dat een gebruiker moet configureren (tussen **4** en **16** tekens).
  - **Eenvoudige wachtwoorden**: hiermee stelt u in dat eenvoudige wachtwoorden mogen worden gebruikt, zoals **0000** en **1234**.
  - **Maximum aantal minuten waarna een wachtwoord voor het vergrendelde scherm is vereist**: hiermee geeft u op hoe lang de computer inactief moet zijn voordat een wachtwoord is vereist om te ontgrendelen.
  - **Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld**: hiermee geeft u de hoeveelheid tijd op die de computer inactief moet zijn voordat het scherm wordt vergrendeld.
  - **Wachtwoord verloopt (dagen)**: hiermee geeft u op na hoeveel dagen de gebruiker het wachtwoord moet wijzigen (tussen **1** en **255** dagen).
  - **Wachtwoorden niet opnieuw gebruiken**: hiermee geeft u op hoeveel eerder gebruikte wachtwoorden niet opnieuw mogen worden gebruikt (tussen **1** en **24**).

- **Blokkeren dat gebruikers wachtwoordcodes kunnen wijzigen**: Kies **Blokkeren** om ervoor te zorgen dat de wachtwoordcode niet meer kan worden gewijzigd, toegevoegd of verwijderd. **Niet geconfigureerd** (standaard): staat toe dat wachtwoordcodes worden toegevoegd, gewijzigd of verwijderd.
- **Ontgrendelen met vingerafdruk blokkeren**: kies **Blokkeren** om te voorkomen dat vingerafdrukken kunnen worden gebruikt om het apparaat te ontgrendelen. **Niet geconfigureerd** (standaard): staat de gebruiker toe het apparaat te ontgrendelen met een vingerafdruk.

- **Automatisch wachtwoorden doorvoeren blokkeren**: kies **Blokkeren** om te voorkomen dat de functie Wachtwoorden automatisch doorvoeren wordt gebruikt in macOS. Als u **Blokkeren** kiest, heeft dat ook de volgende gevolgen:

  - Gebruikers wordt niet meer gevraagd om een wachtwoord te gebruiken dat is opgeslagen in Safari of in een app.
  - Automatische sterke wachtwoorden zijn uitgeschakeld en gebruikers krijgen geen suggesties voor sterke wachtwoorden.

  **Niet geconfigureerd** (standaard) staat deze functies toe.

- **Aanvragen voor wachtwoordnabijheid blokkeren**: kies **Blokkeren** zodat het apparaat van een gebruiker geen wachtwoorden aanvraagt van apparaten in de buurt. **Niet geconfigureerd** (standaard): staat deze wachtwoordaanvragen toe.

- **Delen van wachtwoorden blokkeren**: **Blokkeren** voorkomt het delen van wachtwoorden tussen apparaten via AirDrop. **Niet geconfigureerd** (standaard): staat toe dat wachtwoorden worden gedeeld.

## <a name="built-in-apps"></a>Ingebouwde apps

- **Automatisch doorvoeren in Safari blokkeren**: met **Blokkeren** wordt de functie Automatisch doorvoeren in Safari uitgeschakeld op het apparaat. **Niet geconfigureerd** (standaard): staat gebruikers toe de instellingen voor automatisch doorvoeren te wijzigen in de webbrowser.
- **Camera blokkeren**: kies **Blokkeren** als u de toegang tot de camera op het apparaat wilt blokkeren. **Niet geconfigureerd** (standaard): staat toegang tot de camera van het apparaat toe.
- **Apple Music blokkeren**: met **Blokkeren** keert u terug naar de klassieke modus van de app Muziek en wordt de Muziek-service uitgeschakeld. **Niet geconfigureerd** (standaard): staat het gebruik van de app Apple Music toe.
- **Zoekresultaten op internet retourneren met Spotlight blokkeren** : **Blokkeren** zorgt ervoor dat Spotlight geen resultaten meer retourneert na een zoekopdracht op internet. **Niet geconfigureerd** (standaard): staat Zoeken met Spotlight toe om verbinding te maken met internet voor zoekresultaten.
- **Bestandsoverdracht via iTunes blokkeren**: Met **Blokkeren** worden services voor het delen van toepassingsbestanden uitgeschakeld. Beschikbaar in macOS 10.13 en later. Met **Niet geconfigureerd** (standaard) zijn services voor het delen van toepassingsbestanden toegestaan.

## <a name="restricted-apps"></a>Beperkte apps

Configureer een van de volgende lijsten in de lijst met beperkte apps:

- Lijst met **niet-toegestane apps**: hiermee maakt u een lijst met apps die niet worden beheerd door Intune en die gebruikers niet mogen installeren en uitvoeren. Er wordt niet voorkomen dat gebruikers een verboden app installeren, maar als zij dit doen, wordt dit wel aan de beheerder gemeld.
- Lijst met **goedgekeurde apps**: hiermee maakt u een lijst met apps die gebruikers mogen installeren. Gebruikers mogen geen apps installeren die niet worden vermeld. Apps die worden beheerd door Intune, zijn automatisch toegestaan. Er wordt niet voorkomen dat gebruikers een app installeren die niet in de goedgekeurde lijst wordt vermeld. Als zij dit doen, wordt dit wel aan de beheerder gemeld.

Als u de lijst wilt configureren, klikt u op **Toevoegen** en geeft u een naam van uw keuze op, eventueel de uitgever van de app, en de bundel-ID van de app (bijvoorbeeld *com.apple.calculator*).

## <a name="connected-devices"></a>Verbonden apparaten

- **AirDrop blokkeren**: selecteer **Blokkeren** om het gebruik van AirDrop op het apparaat te voorkomen. **Niet geconfigureerd** (standaard): staat het gebruik van de functie AirDrop toe voor het uitwisselen van inhoud met apparaten in de omgeving.
- **Automatisch ontgrendelen met Apple Watch blokkeren**: **Blokkeren** voorkomt dat gebruikers hun macOS-apparaat ontgrendelen met hun Apple Watch. Met **Niet geconfigureerd** (standaard) kunnen gebruikers hun macOS-apparaat ontgrendelen met hun Apple Watch.

## <a name="cloud-and-storage"></a>Cloud en opslag

- **Synchronisatie van iCloud-sleutelhanger blokkeren**: kies **Blokkeren** om het synchroniseren van referenties die zijn opgeslagen in de Sleutelhanger, naar iCloud uit te schakelen. **Niet geconfigureerd** (standaard): staat gebruikers toe deze referenties te synchroniseren.
- **Documenten synchroniseren met iCloud blokkeren**: **Blokkeren** voorkomt dat documenten en gegevens worden gesynchroniseerd met iCloud. Met **Niet geconfigureerd** (standaard) staat u het synchroniseren van documenten en sleutelwaarden met uw iCloud-opslagruimte toe.
- **Back-up van Mail in iCloud blokkeren**: **Blokkeren** voorkomt synchronisatie van de app Mail van macOS met iCloud. **Niet geconfigureerd** (standaard) staat synchronisatie van Mail met iCloud toe.
- **Back-up van contactpersonen in iCloud blokkeren**: **Blokkeren** voorkomt synchronisatie van contactpersonen op het apparaat met iCloud. **Niet geconfigureerd** (standaard) staat synchronisatie van contactpersonen met behulp van iCloud toe.
- **Back-up van Agenda in iCloud blokkeren**: **Blokkeren** voorkomt synchronisatie van de app Agenda van macOS met iCloud. **Niet geconfigureerd** (standaard) staat synchronisatie van Agenda met iCloud toe.
- **Back-up van Herinneringen in iCloud blokkeren**: **Blokkeren** voorkomt synchronisatie van de app Herinneringen van macOS met iCloud. **Niet geconfigureerd** (standaard) staat synchronisatie van Herinneringen met iCloud toe.
- **Back-up van Bladwijzers in iCloud blokkeren**: **Blokkeren** voorkomt synchronisatie van Bladwijzers op het apparaat met iCloud. **Niet geconfigureerd** (standaard) staat synchronisatie van Bladwijzers met iCloud toe.
- **Back-up van Notities in iCloud blokkeren**: **Blokkeren** voorkomt synchronisatie van Notities op het apparaat met iCloud. **Niet geconfigureerd** (standaard) staat synchronisatie van Notities met iCloud toe.

## <a name="domains"></a>Domains

- **E-maildomein-URL**: voeg een of meer URL's toe aan de lijst. Wanneer gebruikers een e-mail ontvangen die afkomstig is van een ander domein dan het domein dat u hebt geconfigureerd, wordt de e-mail in de macOS Mail-app gemarkeerd als niet-vertrouwd.

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

U kunt ook apparaatfuncties en -instellingen beperken op [iOS](device-restrictions-ios.md)-apparaten.
