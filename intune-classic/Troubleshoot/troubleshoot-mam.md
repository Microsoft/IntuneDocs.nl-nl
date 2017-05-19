---
title: Problemen met Mobile Application Management oplossen | Microsoft Docs
description: In dit onderwerp worden enkele tips voor het oplossen van problemen met implementaties van voorwaardelijke toegang beschreven.
keywords: 
author: oydang
ms.author: oydang
manager: angerobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: c795b0b5b12d900155e55e0874009177b32a2546
ms.lasthandoff: 04/14/2017


---

# <a name="troubleshoot-mobile-application-management"></a>Problemen met Mobile Application Management oplossen

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Begin hier als u problemen ondervindt met Intune Mobile Application Management. Dit onderwerp bevat een aantal veelvoorkomende problemen en vragen en biedt oplossingen en antwoorden.

Zie [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md) voor meer manieren om hulp te krijgen als u het probleem niet kunt oplossen met deze informatie.


## <a name="common-it-administrator-issues"></a>Veelvoorkomende problemen voor IT-beheerders

Dit zijn veelvoorkomende problemen die een IT-beheerder kan tegenkomen met het Intune-beleid voor app-beveiliging.

| Probleem | Beschrijving | Oplossing |
| -- | -- | -- |
| Beleid niet toegepast op Skype voor Bedrijven | Het beleid voor app-beveiliging zonder apparaatregistratie, gemaakt in Azure Portal, is niet van toepassing op de Skype voor Bedrijven-app op iOS- en Android-apparaten. | Skype voor Bedrijven moet worden ingesteld voor moderne verificatie.  Volg de instructies in [Enable your tenant for modern authentication](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) (Moderne verificatie inschakelen voor uw tenant) om moderne verificatie in te stellen voor Skype. |
| Office-app-beleid niet toegepast | Het beleid voor app-beveiliging wordt niet toegepast op [ondersteunde Office-apps](https://www.microsoft.com/cloud-platform/microsoft-intune-partners) voor alle gebruikers. | Controleer of de gebruiker een licentie voor Intune heeft en of een geïmplementeerd beleid voor app-beveiliging wordt toegepast op de Office-apps. Het kan tot 8 uur duren voordat een nieuw geïmplementeerd beleid voor app-beveiliging is toegepast. |
| Beheerder kan geen beleid voor app-beveiliging configureren in Azure-portal | Een IT-beheerder kan geen beleid voor app-beveiliging configureren in Azure Portal. | De volgende gebruikersrollen hebben toegang tot Azure Portal: <ul><li>Globale beheerder, die u kunt instellen in de [Office-portal](http://portal.office.com/).</li><li>Eigenaar, die u kunt instellen in [Azure Portal](https://portal.azure.com/).</li><li>Bijdrager, die u kunt instellen in [Azure Portal](https://portal.azure.com/).</li></ul>  Raadpleeg [Voorbereidingen voor het configureren van beleid voor het beheer van mobiele apps (Mobile App Management) met Microsoft Intune](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md) voor hulp bij het instellen van deze rollen.|
|Gebruikersaccounts ontbreken in rapporten van beleid voor app-beveiliging | Er worden geen gebruikersaccounts in de beheerconsolerapporten weergegeven waarvoor onlangs beleid voor app-beveiliging is geïmplementeerd. | Als er onlangs beleid voor app-beveiliging is toegepast op een gebruiker, kan het tot 24 uur duren voor die gebruiker in rapporten als gebruiker in de doelgroep wordt weergegeven. |
| Beleidswijzigingen werken niet | Het kan 8 uur duren voordat wijzigingen en updates voor beleid voor app-beveiliging worden toegepast. | Indien van toepassing, kunnen eindgebruikers zich bij de app afmelden en weer aanmelden om synchronisatie met de service af te dwingen. |
| Beleid voor app-beveiliging werkt niet met DEP | Het beleid voor app-beveiliging wordt niet toegepast op Apple DEP-apparaten. | Zorg ervoor dat u gebruikersaffiniteit gebruikt bij het Device Enrollment Program (DEP) van Apple. Gebruikersaffiniteit is vereist voor elke app die verificatie van gebruikers vereist volgens het DEP. <br><br>Raadpleeg [iOS-apparaten in bedrijfseigendom met het Device Enrollment Program inschrijven](../deploy-use/ios-device-enrollment-program-in-microsoft-intune.md) voor meer informatie over iOS DEP-registratie.|
| Beleid voor gegevensoverdracht werkt niet met iOS | Met de beleidsregels **App mag gegevens overdragen naar ander apps** en **App mag gegevens ontvangen van andere apps** kan geen gegevensoverdracht in iOS worden beheerd. | Zie [Gegevensoverdracht beheren tussen iOS-apps met Microsoft Intune](/deploy-use/manage-data-transfer-between-ios-apps-with-microsoft-intune.md). |






## <a name="common-end-user-issues"></a>Algemene problemen voor eindgebruikers

Algemene problemen voor eindgebruikers worden onderverdeeld in de volgende categorieën:

* **Normale gebruiksscenario's**: een eindgebruiker kan met deze scenario's te maken krijgen bij apps die werken met Intune-beleid voor app-beveiliging. Dit zijn geen daadwerkelijke problemen, maar kunnen wel worden beschouwd als bugs of fouten.

* **Dialoogvensters voor normaal gebruik**: dit zijn dialoogvensters die een eindgebruiker kan zien in apps met Intune-beleid voor app-beveiliging. Deze berichten en dialoogvensters geven **geen** fout of bug aan.

* **Foutberichten en dialoogvensters**: dit zijn foutberichten en dialoogvensters die een eindgebruiker kan zien in apps met Intune-beleid voor app-beveiliging. Ze geven vaak een fout aan die is gemaakt door de IT-beheerder of een bug met Intune-app-beveiliging.



### <a name="normal-usage-scenarios"></a>Normale gebruiksscenario's

Platform | Scenario | Uitleg |
---| --- | --- |
iOS | De eindgebruiker kan de iOS-extensie voor delen gebruiken om werk- of schoolgegevens te openen in niet-beheerde apps, zelfs wanneer het beleid voor gegevensoverdracht is ingesteld op **Alleen voor beheerde apps** of **Geen apps.** Ontstaat hierdoor geen gegevenslek? | De iOS-extensie voor delen kan alleen met Intune-beleid voor app-beveiliging worden beheerd als ook het apparaat wordt beheerd. Daarom worden **'bedrijfs'gegevens door Intune versleuteld voordat ze buiten de app worden gedeeld**. U kunt dit controleren door een 'bedrijfs'bestand te openen buiten de beheerde app. Het bestand moet zijn versleuteld en kan niet worden geopend buiten de beheerde app.
Android | Waarom moet de eindgebruiker **de bedrijfsportal-app installeren**, zelfs als ik MAM-app-beveiliging zonder apparaatregistratie gebruik?  | Veel functies voor app-beveiliging in Android zijn ingebouwd in de bedrijfsportal-app. **De bedrijfsportal-app is altijd vereist, maar dat geldt niet voor apparaatregistratie**. Voor app-beveiliging zonder registratie hoeft de eindgebruiker alleen de bedrijfsportal-app op het apparaat te hebben geïnstalleerd.

### <a name="normal-usage-dialogs"></a>Dialoogvensters voor normaal gebruik

Platform | Bericht of dialoogvenster | Uitleg |
--- | --- | --- |
iOS, Android | **Aanmelden**: om de bedrijfsgegevens te beveiligen, moet uw organisatie deze app beheren. Meld u aan met uw werk- of schoolaccount om deze actie uit te voeren. | De eindgebruiker moet zich aanmelden met een werk- of schoolaccount om deze app te gebruiken. Hiervoor is beleid voor app-beveiliging vereist. Om het beleid toe te passen, moet de gebruiker worden geverifieerd door Azure Active Directory.
iOS, Android |**Opnieuw opstarten vereist**: uw organisatie beveiligt nu de gegevens in deze app. U moet de app opnieuw opstarten om door te gaan. | Omdat voor de app zojuist Intune-beleid voor app-beveiliging is ingesteld, moet de app opnieuw worden opgestart om het beleid toe te passen.
iOS, Android |**De actie is niet toegestaan**: uw organisatie heeft ingesteld dat u in deze app alleen werk- of schoolgegevens kunt openen. | De IT-beheerder heeft **App mag gegevens overdragen naar ander apps** ingesteld op **Alleen voor beheerde apps**. Daarom kan de eindgebruiker alleen gegevens overdragen naar deze app vanuit andere apps die app-beveiligingsbeleid hebben.
iOS, Android |**De actie is niet toegestaan**: uw organisatie heeft ingesteld dat u de organisatiegegevens alleen mag overbrengen naar andere beheerde apps. | De IT-beheerder heeft **App mag gegevens overdragen vanuit ander apps** ingesteld op **Alleen voor beheerde apps**. Daarom kan de eindgebruiker alleen gegevens overdragen vanuit deze app naar andere apps die app-beveiligingsbeleid hebben.
iOS, Android |**Waarschuwing wissen**: de organisatiegegevens die zijn gekoppeld aan deze app, zijn verwijderd door uw organisatie. Start de app opnieuw op om door te gaan. | De IT-beheerder heeft het wissen van een app met Intune-beleid voor app-beveiliging gestart.
Android | **Bedrijfsportal vereist**: u moet de bedrijfsportal-app voor Intune installeren om uw werk- of schoolaccount te kunnen gebruiken met deze app. Tik op Ga naar winkel om door te gaan. | Veel functies voor app-beveiliging in Android zijn ingebouwd in de bedrijfsportal-app. **De bedrijfsportal-app is altijd vereist, maar dat geldt niet voor apparaatregistratie**. Voor app-beveiliging zonder registratie hoeft de eindgebruiker alleen de bedrijfsportal-app op het apparaat te hebben geïnstalleerd.


### <a name="error-messages-and-dialogs-on-ios"></a>Foutberichten en dialoogvensters in iOS


Foutbericht of dialoogvenster | Oorzaak | Herstel |
-- | --- | --- |
**De app is niet ingesteld**: Deze app is niet ingesteld om door u te worden gebruikt. Neem contact op met uw IT-beheerder voor hulp. | Kan het vereiste app-beveiligingsbeleid voor de app niet detecteren. |Controleer of er een beveiligingsbeleid voor iOS-apps is geïmplementeerd voor de beveiligingsgroep van de gebruiker en op deze app wordt toegepast.
**Welkom bij de Intune Managed Browser**: Deze app werkt het beste wanneer deze wordt beheerd met Microsoft Intune. U kunt deze app altijd gebruiken om op internet te browsen en als de app wordt beheerd met Microsoft Intune, hebt u toegang tot extra functies voor gegevensbescherming. | Kan het vereiste app-beveiligingsbeleid voor de Intune Managed Browser-app niet detecteren. <br><br>De gebruiker kan de app nog gewoon gebruiken om op internet te surfen, maar de app wordt niet beheerd met Intune. | Controleer of er een beveiligingsbeleid voor iOS-apps is geïmplementeerd voor de beveiligingsgroep van de gebruiker en wordt toegepast op de app Intune Managed Browser.
**Aanmelden is mislukt**: u kunt op dit moment niet worden aangemeld. Probeer het later opnieuw. | Kan de gebruiker niet registreren bij de MAM-service nadat de gebruiker heeft geprobeerd om zich aan te melden met het werk-of schoolaccount. | Controleer of er een beveiligingsbeleid voor iOS-apps is geïmplementeerd voor de beveiligingsgroep van de gebruiker en op deze app wordt toegepast.
**Het account is niet ingesteld**: uw organisatie heeft het account niet ingesteld voor toegang tot werk- of schoolgegevens. Neem contact op met uw IT-beheerder voor hulp. | Het gebruikersaccount heeft geen licentie voor Intune A Direct. | Zorg ervoor dat er een licentie in de [Office-portal](http://portal.office.com) is toegewezen aan het account van de gebruiker.
**Het apparaat voldoet niet aan het beleid**: deze app kan niet worden gebruikt, omdat u een gekraakt apparaat gebruikt. Neem contact op met uw IT-beheerder voor hulp. | Intune heeft gedetecteerd dat de gebruiker een gekraakt apparaat gebruikt. | Zet de fabrieksinstellingen van het apparaat terug. Volg [deze instructies](https://support.apple.com/HT201274) op de ondersteuningssite van Apple.
**Internetverbinding vereist**: u moet zijn verbonden met internet om te kunnen verifiëren of u deze app mag gebruiken. | Het apparaat is niet verbonden met internet. | Verbind het apparaat met een WiFi- of datanetwerk.
**Onbekende fout**: probeer deze app opnieuw te starten. Als het probleem zich blijft voordoen, neemt u contact op met uw IT-beheerder voor ondersteuning. | Er is een onbekende fout opgetreden. | Wacht enige tijd en probeer het opnieuw. Als de fout zich blijft voordoen, maakt u [hier](how-to-get-support-for-microsoft-intune.md) een ondersteuningsticket met Intune.
**Toegang tot gegevens van uw organisatie**: het werk- of schoolaccount dat u hebt opgegeven, heeft geen toegang tot deze app. Mogelijk moet u zich aanmelden met een ander account. Neem contact op met uw IT-beheerder voor hulp. | Intune heeft gedetecteerd dat de gebruiker zich probeert aan te melden met een tweede werk- of schoolaccount dat verschilt van het bij MAM geregistreerde account voor het apparaat. Er kan per apparaat slechts één werk- of schoolaccount tegelijkertijd door MAM worden beheerd. | Laat de gebruiker zich aanmelden met het account waarvan de gebruikersnaam vooraf is ingevuld op het aanmeldingsscherm. <br> <br> Of laat de gebruiker zich aanmelden met het nieuwe werk- of schoolaccount en verwijder het bestaande bij MAM geregistreerde account.
**Verbindingsprobleem**: er is een onverwacht verbindingsprobleem opgetreden. Controleer uw verbinding en probeer het opnieuw.  |  Er is een onverwachte fout opgetreden. | Wacht enige tijd en probeer het opnieuw. Als de fout zich blijft voordoen, maakt u [hier](how-to-get-support-for-microsoft-intune.md) een ondersteuningsticket met Intune.
**Waarschuwing**: deze app kan niet meer worden gebruikt. Neem contact op met uw IT-beheerder voor meer informatie. | Kan het certificaat van de app niet valideren. | Zorg ervoor dat de versie van de app is bijgewerkt. <br><br> installeer de app opnieuw.
**Fout**: er is een probleem opgetreden waardoor deze app moet worden gesloten. Als de fout zich blijft voordoen, neemt u contact op met uw IT-beheerd. | Kan de pincode van de MAM-app in de sleutelhanger van Apple iOS niet lezen. | Start het apparaat opnieuw op. Zorg ervoor dat de versie van de app is bijgewerkt. <br><br> installeer de app opnieuw.


### <a name="error-messages-and-dialogs-on-android"></a>Foutberichten en dialoogvensters in Android

Dialoogvenster/foutbericht | Oorzaak | Herstel |
-- | --- | --- |
**De app is niet ingesteld**: Deze app is niet ingesteld om door u te worden gebruikt. Neem contact op met uw IT-beheerder voor hulp. | Kan het vereiste app-beveiligingsbeleid voor de app niet detecteren. |Controleer of er een beveiligingsbeleid voor Android-apps is geïmplementeerd voor de beveiligingsgroep van de gebruiker en op deze app wordt toegepast.
**Kan de app niet starten**: er is een probleem met het starten van uw app. Probeer de app of de bedrijfsportal-app van Intune bij te werken. Neem contact op met de IT-beheerder als u hulp nodig hebt. | Intune heeft een geldige app-beveiligingsbeleid voor de app gedetecteerd, maar de app loopt vast tijdens de MAM-initialisatie. | Zorg ervoor dat de versie van de app is bijgewerkt. <br><br> Zorg ervoor dat de bedrijfsportal van Intune op het apparaat is geïnstalleerd en is bijgewerkt. <br><br> Als de fout zich blijft voordoen, gebruikt u de bedrijfsportal-app om logboeken naar Intune te verzenden of om [hier](how-to-get-support-for-microsoft-intune.md) een ondersteuningsticket te maken.
**Geen apps gevonden**: Er staan geen apps op dit apparaat waarmee u van uw organisatie inhoud mag openen. Neem contact op met uw IT-beheerder voor hulp. Neem contact op met uw IT-beheerder voor hulp. | De gebruiker probeert werk- of schoolgegevens te openen met een andere app, maar Intune kan geen andere beheerde apps vinden die de gegevens mogen openen. | Zorg ervoor dat er een beveiligingsbeleid voor Android-apps is geïmplementeerd voor de beveiliging van de gebruiker en dat het beleid wordt toegepast op minimaal nog één andere MAM-app waarmee de desbetreffende gegevens kunnen worden geopend.
**Aanmelden is mislukt**: probeer opnieuw aan te melden. Als dit probleem zich blijft voordoen, neemt u contact op met uw IT-beheerder voor ondersteuning. | Fout bij het verifiëren van het account waarmee de gebruiker zich probeert aan te melden. | Zorg ervoor dat de gebruiker zich aanmeldt met het werk- of schoolaccount dat al is geregistreerd bij de Intune MAM-service (het eerste werk- of schoolaccount dat is aangemeld bij deze app). <br><br> Wis de gegevens van de app. <br><br> Zorg ervoor dat de versie van de app is bijgewerkt. <br><br> Zorg ervoor de versie van de bedrijfsportal up-to-date is.
**Internetverbinding vereist**: U moet zijn verbonden met internet om te kunnen verifiëren of u deze app mag gebruiken. | Het apparaat is niet verbonden met internet. | Verbind het apparaat met een WiFi- of datanetwerk.
**Het apparaat voldoet niet aan het beleid**: Deze app kan niet worden gebruikt, omdat u een geroot apparaat gebruikt. Neem contact op met uw IT-beheerder voor hulp. | Intune heeft gedetecteerd dat de gebruiker een gekraakt geroot gebruikt. | Zet de fabrieksinstellingen van het apparaat terug.
**Het account is niet ingesteld**: Deze app moet worden beheerd met Microsoft Intune, maar uw account is niet ingesteld. Neem contact op met uw IT-beheerder voor hulp. | Het gebruikersaccount heeft geen licentie voor Intune A Direct. | Zorg ervoor dat er een licentie in de [Office-portal](http://portal.office.com) is toegewezen aan het account van de gebruiker.
**Kan de app niet registreren**: Deze app moet worden beheerd door Microsoft Intune, maar momenteel is het niet mogelijk de app te registreren. Neem contact op met uw IT-beheerder voor hulp. | De app wordt niet automatisch geregistreerd bij de MAM-service wanneer app-beveiligingsbeleid is vereist. | Wis de gegevens van de app. <br><br> Verzend logboeken via de bedrijfsportal-app naar Intune of dien [hier](how-to-get-support-for-microsoft-intune.md) een ondersteuningsticket in.




### <a name="see-also"></a>Zie tevens
- [De Mobile Application Management-configuratie valideren](../deploy-use/validate-mobile-application-management.md)
- [Voorbereidingen voor het configureren van beleid voor het beheer van mobiele apps (Mobile App Management) met Microsoft Intune](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)
- [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md)

