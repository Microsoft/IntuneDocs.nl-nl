---
title: Problemen met Mobile Application Management oplossen
titlesuffix: Microsoft Intune
description: In dit onderwerp worden enkele tips voor het oplossen van problemen met implementaties van voorwaardelijke toegang beschreven.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/21/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c94fc26543123f0b3cf6a0f08f8089c48d78778b
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57232196"
---
# <a name="troubleshoot-mobile-application-management"></a>Problemen met Mobile Application Management oplossen

Dit onderwerp bevat oplossingen voor veelvoorkomende problemen die kunnen optreden bij het gebruik van Mobile Application Management van Intune.

Zie [Ondersteuning voor Microsoft Intune krijgen](get-support.md) voor meer manieren om hulp te krijgen als u het probleem niet kunt oplossen met deze informatie.

## <a name="common-it-administrator-issues"></a>Veelvoorkomende problemen voor IT-beheerders

Dit zijn veelvoorkomende problemen die een IT-beheerder kan tegenkomen bij het gebruik van Intune-beleid voor app-beveiliging.

| Probleem | Beschrijving | Oplossing |
| -- | -- | -- |
| Beleid niet toegepast op Skype voor Bedrijven | Het beleid voor app-beveiliging zonder apparaatregistratie, gemaakt in Azure Portal, is niet van toepassing op de Skype voor Bedrijven-app op iOS- en Android-apparaten. | Skype voor Bedrijven moet worden ingesteld voor moderne verificatie.  Volg de instructies in [Enable your tenant for modern authentication](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) (Moderne verificatie inschakelen voor uw tenant) om moderne verificatie in te stellen voor Skype. |
| Office-app-beleid niet toegepast | Het beleid voor app-beveiliging wordt niet toegepast op [ondersteunde Office-apps](https://www.microsoft.com/cloud-platform/microsoft-intune-partners) voor alle gebruikers. | Controleer of de gebruiker een licentie voor Intune heeft en of een geïmplementeerd beleid voor app-beveiliging wordt toegepast op de Office-apps. Het kan tot 8 uur duren voordat een nieuw geïmplementeerd beleid voor app-beveiliging is toegepast. |
| Beheerder kan geen beleid voor app-beveiliging configureren in Azure-portal | Een IT-beheerder kan geen beleid voor app-beveiliging configureren in Azure Portal. | De volgende gebruikersrollen hebben toegang tot Azure Portal: <ul><li>Globale beheerder, die u kunt instellen in de [Office-portal](https://portal.office.com/).</li><li>Eigenaar, die u kunt instellen in [Azure Portal](https://portal.azure.com/).</li><li>Bijdrager, die u kunt instellen in [Azure Portal](https://portal.azure.com/).</li></ul> Raadpleeg [RBAC (beheer op basis van rollen) met Microsoft Intune](role-based-access-control.md) voor hulp bij het instellen van deze rollen.|
|Gebruikersaccounts ontbreken in rapporten van beleid voor app-beveiliging | Er worden geen gebruikersaccounts in de beheerconsolerapporten weergegeven waarvoor onlangs beleid voor app-beveiliging is geïmplementeerd. | Als er onlangs beleid voor app-beveiliging is toegepast op een gebruiker, kan het tot 24 uur duren voor die gebruiker in rapporten als gebruiker in de doelgroep wordt weergegeven. |
| Beleidswijzigingen werken niet | Het kan 8 uur duren voordat wijzigingen en updates voor beleid voor app-beveiliging worden toegepast. | Indien van toepassing, kunnen eindgebruikers zich bij de app afmelden en weer aanmelden om synchronisatie met de service af te dwingen. |
| Beleid voor app-beveiliging werkt niet met DEP | Het beleid voor app-beveiliging wordt niet toegepast op Apple DEP-apparaten. | Zorg ervoor dat u gebruikersaffiniteit gebruikt bij het Device Enrollment Program (DEP) van Apple. Gebruikersaffiniteit is vereist voor elke app die verificatie van gebruikers vereist volgens het DEP. <br><br>Raadpleeg [iOS-apparaten automatisch inschrijven met het Device Enrollment Program van Apple](device-enrollment-program-enroll-ios.md) voor meer informatie over iOS DEP-inschrijving.|
| Beleid voor gegevensoverdracht werkt niet met iOS | Met de beleidsregels **App mag gegevens overdragen naar ander apps** en **App mag gegevens ontvangen van andere apps** kan geen gegevensoverdracht in iOS worden beheerd. | Zie [Gegevensoverdracht beheren tussen iOS-apps met Microsoft Intune](data-transfer-between-apps-manage-ios.md). |

## <a name="common-end-user-issues"></a>Algemene problemen voor eindgebruikers

Algemene problemen voor eindgebruikers worden onderverdeeld in de volgende categorieën:

* **Normale gebruiksscenario's**: Een eindgebruiker kan met deze scenario's te maken krijgen bij apps die werken met Intune-beleid voor app-beveiliging. Dit zijn geen daadwerkelijke problemen, maar kunnen wel worden beschouwd als bugs of fouten.

* **Dialoogvensters voor normaal gebruik**: Dit zijn dialoogvensters die een eindgebruiker kan zien in apps met Intune-beleid voor app-beveiliging. Deze berichten en dialoogvensters geven **geen** fout of bug aan.

* **Foutberichten en dialoogvensters**: Dit zijn foutberichten en dialoogvensters die een eindgebruiker kan zien in apps met Intune-beleid voor app-beveiliging. Ze geven vaak een fout aan die is gemaakt door de IT-beheerder of een bug met Intune-app-beveiliging.

### <a name="normal-usage-scenarios"></a>Normale gebruiksscenario's

Platform | Scenario | Uitleg |
---| --- | --- |
iOS | De eindgebruiker kan de iOS-extensie voor delen gebruiken om werk- of schoolgegevens te openen in niet-beheerde apps, zelfs wanneer het beleid voor gegevensoverdracht is ingesteld op **Alleen voor beheerde apps** of **Geen apps.** Ontstaat hierdoor geen gegevenslek? | De iOS-extensie voor delen kan alleen met Intune-beleid voor app-beveiliging worden beheerd als ook het apparaat wordt beheerd. Daarom worden **'bedrijfs'gegevens door Intune versleuteld voordat ze buiten de app worden gedeeld**. U kunt dit controleren door een 'bedrijfs'bestand te openen buiten de beheerde app. Het bestand moet zijn versleuteld en kan niet worden geopend buiten de beheerde app.
Android | Waarom moet de eindgebruiker **de bedrijfsportal-app installeren**, zelfs als ik MAM-app-beveiliging zonder apparaatregistratie gebruik?  | Veel functies voor app-beveiliging in Android zijn ingebouwd in de bedrijfsportal-app. **De bedrijfsportal-app is altijd vereist, maar dat geldt niet voor apparaatregistratie**. Voor app-beveiliging zonder registratie hoeft de eindgebruiker alleen de bedrijfsportal-app op het apparaat te hebben geïnstalleerd.

### <a name="normal-usage-dialogs"></a>Dialoogvensters voor normaal gebruik

Platform | Bericht of dialoogvenster | Uitleg |
--- | --- | --- |
iOS, Android | **Aanmelden**: Uw organisatie moet deze app beheren om de bedrijfsgegevens te beveiligen. Meld u aan met uw werk- of schoolaccount om deze actie uit te voeren. | De eindgebruiker moet zich aanmelden met een werk- of schoolaccount om deze app te gebruiken. Hiervoor is beleid voor app-beveiliging vereist. De gebruiker moet worden geverifieerd met Azure Active Directory om het beleid toe te passen.
iOS, Android |**Opnieuw opstarten vereist**: De gegevens in deze app zijn nu beveiligd in uw organisatie. U moet de app opnieuw opstarten om door te gaan. | Omdat voor de app zojuist Intune-beleid voor app-beveiliging is ingesteld, moet de app opnieuw worden opgestart om het beleid toe te passen.
iOS, Android |**Actie niet toegestaan**: In uw organisatie is ingesteld dat u in deze app alleen werk- of schoolgegevens kunt openen. | De IT-beheerder heeft **App mag gegevens overdragen naar ander apps** ingesteld op **Alleen voor beheerde apps**. Daarom kan de eindgebruiker alleen gegevens overdragen naar deze app vanuit andere apps die app-beveiligingsbeleid hebben.
iOS, Android |**Actie niet toegestaan**: In uw organisatie is ingesteld dat u de organisatiegegevens alleen mag overdragen vanuit andere beheerde apps. | De IT-beheerder heeft **App mag gegevens overdragen vanuit ander apps** ingesteld op **Alleen voor beheerde apps**. Daarom kan de eindgebruiker alleen gegevens overdragen vanuit deze app naar andere apps die app-beveiligingsbeleid hebben.
iOS, Android |**Waarschuwing over wissen**: De organisatiegegevens die zijn gekoppeld aan deze app, zijn verwijderd in uw organisatie. Start de app opnieuw op om door te gaan. | De IT-beheerder heeft het wissen van een app met Intune-beleid voor app-beveiliging gestart.
Android | **Bedrijfsportal vereist**: U moet de bedrijfsportal-app voor Intune installeren om uw werk- of schoolaccount te kunnen gebruiken met deze app. Klik op Naar de store om door te gaan. | Veel functies voor app-beveiliging in Android zijn ingebouwd in de bedrijfsportal-app. **De bedrijfsportal-app is altijd vereist, maar dat geldt niet voor apparaatregistratie**. Voor app-beveiliging zonder registratie hoeft de eindgebruiker alleen de bedrijfsportal-app op het apparaat te hebben geïnstalleerd.

### <a name="error-messages-and-dialogs-on-ios"></a>Foutberichten en dialoogvensters in iOS

Foutbericht of dialoogvenster | Oorzaak | Herstel |
-- | --- | --- |
**App niet ingesteld**: Deze app is niet ingesteld om door u te worden gebruikt. Neem contact op met uw IT-beheerder voor hulp. | Kan het vereiste app-beveiligingsbeleid voor de app niet detecteren. |Controleer of er een beveiligingsbeleid voor iOS-apps is geïmplementeerd voor de beveiligingsgroep van de gebruiker en op deze app wordt toegepast.
**Welkom bij de Intune Managed Browser**: De app werkt het beste wanneer deze wordt beheerd in Microsoft Intune. U kunt deze app altijd gebruiken om op internet te browsen en als de app wordt beheerd met Microsoft Intune, hebt u toegang tot extra functies voor gegevensbescherming. | Kan het vereiste app-beveiligingsbeleid voor de Intune Managed Browser-app niet detecteren. <br><br>De gebruiker kan de app nog gewoon gebruiken om op internet te surfen, maar de app wordt niet beheerd met Intune. | Controleer of er een beveiligingsbeleid voor iOS-apps is geïmplementeerd voor de beveiligingsgroep van de gebruiker en wordt toegepast op de app Intune Managed Browser.
**Aanmelden mislukt**: U kunt op dit moment niet worden aangemeld. Probeer het later opnieuw. | Kan de gebruiker niet registreren bij de MAM-service nadat de gebruiker heeft geprobeerd om zich aan te melden met het werk-of schoolaccount. | Controleer of er een beveiligingsbeleid voor iOS-apps is geïmplementeerd voor de beveiligingsgroep van de gebruiker en op deze app wordt toegepast.
**Account niet ingesteld**: Uw organisatie heeft het account niet ingesteld voor toegang tot werk- of schoolgegevens. Neem contact op met uw IT-beheerder voor hulp. | Het gebruikersaccount heeft geen licentie voor Intune A Direct. | Zorg ervoor dat er een licentie in de [Office-portal](https://portal.office.com) is toegewezen aan het account van de gebruiker.
**Apparaat niet-compatibel**: Deze app kan niet worden gebruikt, omdat u een gekraakt apparaat gebruikt. Neem contact op met uw IT-beheerder voor hulp. | Intune heeft gedetecteerd dat de gebruiker een gekraakt apparaat gebruikt. | Zet de fabrieksinstellingen van het apparaat terug. Volg [deze instructies](https://support.apple.com/HT201274) op de ondersteuningssite van Apple.
**Internetverbinding vereist**: U moet zijn verbonden met internet om te kunnen verifiëren of u deze app mag gebruiken. | Het apparaat is niet verbonden met internet. | Verbind het apparaat met een WiFi- of datanetwerk.
**Onbekende fout**: Start de app opnieuw. Als het probleem zich blijft voordoen, neemt u contact op met uw IT-beheerder voor ondersteuning. | Er is een onbekende fout opgetreden. | Wacht enige tijd en probeer het opnieuw. Als de fout zich blijft voordoen, maakt u een [ondersteuningsticket](get-support.md#create-an-online-support-ticket) met Intune.
**Toegang tot de gegevens van uw organisatie**: Het werk- of schoolaccount dat u hebt opgegeven, heeft geen toegang tot deze app. Mogelijk moet u zich aanmelden met een ander account. Neem contact op met uw IT-beheerder voor hulp. | Intune heeft gedetecteerd dat de gebruiker zich probeert aan te melden met een tweede werk- of schoolaccount dat verschilt van het bij MAM geregistreerde account voor het apparaat. Er kan per apparaat slechts één werk- of schoolaccount tegelijkertijd door MAM worden beheerd. | Laat de gebruiker zich aanmelden met het account waarvan de gebruikersnaam vooraf is ingevuld op het aanmeldingsscherm. <br> <br> Of laat de gebruiker zich aanmelden met het nieuwe werk- of schoolaccount en verwijder het bestaande bij MAM geregistreerde account.
**Verbindingsprobleem**: Er is een onverwacht verbindingsprobleem opgetreden. Controleer uw verbinding en probeer het opnieuw.  |  Er is een onverwachte fout opgetreden. | Wacht enige tijd en probeer het opnieuw. Als de fout zich blijft voordoen, maakt u een [ondersteuningsticket](get-support.md#create-an-online-support-ticket) met Intune.
**Waarschuwing**: Deze app kan niet meer worden gebruikt. Neem contact op met uw IT-beheerder voor meer informatie. | Kan het certificaat van de app niet valideren. | Zorg ervoor dat de versie van de app is bijgewerkt. <br><br> installeer de app opnieuw.
**Fout**: Er is een probleem opgetreden waardoor deze app moet worden gesloten. Als de fout zich blijft voordoen, neemt u contact op met uw IT-beheerd. | Kan de pincode van de MAM-app in de sleutelhanger van Apple iOS niet lezen. | Start het apparaat opnieuw op. Zorg ervoor dat de versie van de app is bijgewerkt. <br><br> installeer de app opnieuw.

### <a name="error-messages-and-dialogs-on-android"></a>Foutberichten en dialoogvensters in Android

Dialoogvenster/foutbericht | Oorzaak | Herstel |
-- | --- | --- |
**App niet ingesteld**: Deze app is niet ingesteld om door u te worden gebruikt. Neem contact op met uw IT-beheerder voor hulp. | Kan het vereiste app-beveiligingsbeleid voor de app niet detecteren. |Controleer of er een beveiligingsbeleid voor Android-apps is geïmplementeerd voor de beveiligingsgroep van de gebruiker en op deze app wordt toegepast.
**Starten van app mislukt**: Er is een probleem met het starten van de app. Probeer de app of de bedrijfsportal-app van Intune bij te werken. Neem contact op met de IT-beheerder als u hulp nodig hebt. | Intune heeft een geldige app-beveiligingsbeleid voor de app gedetecteerd, maar de app loopt vast tijdens de MAM-initialisatie. | Zorg ervoor dat de versie van de app is bijgewerkt. <br><br> Zorg ervoor dat de bedrijfsportal van Intune op het apparaat is geïnstalleerd en is bijgewerkt. <br><br> Als de fout zich blijft voordoen, gebruikt u de bedrijfsportal-app om logboeken naar Intune te verzenden of maakt u een [ondersteuningsticket](get-support.md#create-an-online-support-ticket).
**Geen apps gevonden**: Er staan geen apps op dit apparaat waarmee u van uw organisatie inhoud mag openen. Neem contact op met de IT-beheerder voor hulp. Neem contact op met uw IT-beheerder voor hulp. | De gebruiker probeert werk- of schoolgegevens te openen met een andere app, maar Intune kan geen andere beheerde apps vinden die de gegevens mogen openen. | Zorg ervoor dat er een beveiligingsbeleid voor Android-apps is geïmplementeerd voor de beveiliging van de gebruiker en dat het beleid wordt toegepast op minimaal nog één andere MAM-app waarmee de desbetreffende gegevens kunnen worden geopend.
**Aanmelden mislukt**: Probeer u opnieuw aan te melden. Als dit probleem zich blijft voordoen, neemt u contact op met uw IT-beheerder voor ondersteuning. | Fout bij het verifiëren van het account waarmee de gebruiker zich probeert aan te melden. | Zorg ervoor dat de gebruiker zich aanmeldt met het werk- of schoolaccount dat al is geregistreerd bij de Intune MAM-service (het eerste werk- of schoolaccount dat is aangemeld bij deze app). <br><br> Wis de gegevens van de app. <br><br> Zorg ervoor dat de versie van de app is bijgewerkt. <br><br> Zorg ervoor de versie van de bedrijfsportal up-to-date is.
**Internetverbinding vereist**: U moet zijn verbonden met internet om te kunnen verifiëren of u deze app mag gebruiken. | Het apparaat is niet verbonden met internet. | Verbind het apparaat met een WiFi- of datanetwerk.
**Apparaat niet-compatibel**: Deze app kan niet worden gebruikt, omdat u een geroot apparaat gebruikt. Neem contact op met uw IT-beheerder voor hulp. | Intune heeft gedetecteerd dat de gebruiker een gekraakt geroot gebruikt. | Zet de fabrieksinstellingen van het apparaat terug.
**Account niet ingesteld**: Deze app moet worden beheerd met Microsoft Intune, maar uw account is niet ingesteld. Neem contact op met uw IT-beheerder voor hulp. | Het gebruikersaccount heeft geen licentie voor Intune A Direct. | Zorg ervoor dat er een licentie in de [Office-portal](https://portal.office.com) is toegewezen aan het account van de gebruiker.
**Kan de app niet registreren**: Deze app moet worden beheerd met Microsoft Intune, maar momenteel is het niet mogelijk de app te registreren. Neem contact op met uw IT-beheerder voor hulp. | De app wordt niet automatisch geregistreerd bij de MAM-service wanneer app-beveiligingsbeleid is vereist. | Wis de gegevens van de app. <br><br> Verzend logboeken via de bedrijfsportal-app naar Intune of dien een ondersteuningsticket in. Zie [Ondersteuning voor Microsoft Intune krijgen](get-support.md) voor meer informatie.

## <a name="next-steps"></a>Volgende stappen

- [De Mobile Application Management-configuratie valideren](app-protection-policies-validate.md)
- Raadpleeg [De portal voor probleemoplossing gebruiken om gebruikers in uw bedrijf te helpen](help-desk-operators.md) voor meer informatie over probleemoplossing met Intune. 
- Ontdek meer over bekende problemen in Microsoft Intune. Zie [Bekende problemen in Microsoft Intune](known-issues.md) voor meer informatie.
- Extra hulp nodig? Zie [Ondersteuning voor Microsoft Intune krijgen](get-support.md).
