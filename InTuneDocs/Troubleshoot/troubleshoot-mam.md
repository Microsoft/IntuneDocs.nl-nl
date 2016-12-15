---
title: Problemen met Mobile Application Management oplossen | Microsoft Docs
description: In dit onderwerp worden enkele tips voor het oplossen van problemen met implementaties van voorwaardelijke toegang beschreven.
keywords: 
author: NathBarn
ms.author: oldang
manager: angerobe
ms.date: 09/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
translationtype: Human Translation
ms.sourcegitcommit: d50a5751a5afd987196336e9443dc5a429a283fd
ms.openlocfilehash: b333c0f5097fec38bf0dd78726a028fd7aaccd2f


---

# <a name="troubleshoot-mobile-application-management"></a>Problemen met Mobile Application Management oplossen

Begin hier als u problemen ondervindt met Intune Mobile Application Management. Dit onderwerp bevat een aantal veelvoorkomende problemen en vragen en biedt oplossingen en antwoorden.

## <a name="common-it-administrator-issues"></a>Veelvoorkomende problemen voor IT-beheerders

1. **Probleem**: het app-beveiligingsbeleid zonder apparaatregistratie, gemaakt in Azure Portal is niet van toepassing op de Skype voor Business-app op iOS- en Android-apparaten.

  **Oplossing**: Skype voor Bedrijven moet worden ingesteld voor moderne authenticatie.  Volg de instructies in [Enable your tenant for modern authentication](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) (Moderne authenticatie inschakelen voor uw tenant) om moderne authenticatie in te stellen voor Skype.

2. **Probleem**: de app-beveiligingsbeleidsregels worden niet toegepast op de [ondersteunde Office-apps](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) voor gebruikers.

  **Oplossing**: controleer of de gebruiker een licentie voor Intune heeft en of een geïmplementeerd app-beveiligingsbeleid wordt toegepast op de Office-apps. Het kan tot 8 uur duren voordat een nieuw geïmplementeerd app-beveiligingsbeleid is toegepast.

3. **Probleem**: een IT-beheerder kan geen app-beveiligingsbeleidsregels configureren in Azure Portal.

  **Oplossing**:

  De volgende gebruikersrollen hebben toegang tot Azure Portal:

  - Globale beheerder, die u kunt instellen in de [Office-portal](http://portal.office.com/).
  - Eigenaar, die u kunt instellen in [Azure Portal](https://portal.azure.com/).
  - Bijdrager, die u kunt instellen in [Azure Portal](https://portal.azure.com/).<br>

  Raadpleeg [Voorbereidingen voor het configureren van beleid voor het beheer van mobiele apps (Mobile App Management) met Microsoft Intune](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md) voor hulp bij het instellen van deze rollen.

4. **Probleem**: er worden geen gebruikersaccounts in de beheerconsolerapporten weergegeven waarvoor onlangs app-beveiligingsbeleid is geïmplementeerd.

  **Oplossing**: als er onlangs app-beveiligingsbeleid is toegepast op een gebruiker, kan het tot 24 uur duren voor die gebruiker in rapporten als gebruiker in de doelgroep wordt weergegeven.

5. **Probleem:** het kan tot wel 8 uur duren voordat beleidswijzigingen/-updates worden toegepast.  

  **Oplossing**: eindgebruikers kunnen zich bij de app afmelden en weer aanmelden om synchroniseren met de service af te dwingen.  

6. **Probleem**: het beveiligingsbeleid voor apps wordt niet toegepast op Apple DEP-apparaten.

  **Oplossing**: zorg ervoor dat u gebruikersaffiniteit gebruikt bij het Device Enrollment Program (DEP) van Apple. Gebruikersaffiniteit is vereist voor elke app die authenticatie van gebruikers vereist volgens het DEP.
Raadpleeg [iOS-apparaten in bedrijfseigendom met het Device Enrollment Program inschrijven](../deploy-use/ios-device-enrollment-program-in-microsoft-intune.md) voor meer informatie over iOS DEP-registratie.

## <a name="common-end-user-issues"></a>Algemene problemen voor eindgebruikers

### <a name="issues-on-ios"></a>Problemen met iOS

Dialoogvenster/foutbericht | Oorzaak | Herstel |
-- | --- | --- |
**De app is niet ingesteld**: Deze app is niet ingesteld om door u te worden gebruikt. Neem contact op met uw IT-beheerder voor hulp. | Kan het vereiste app-beveiligingsbeleid voor de app niet detecteren. |Controleer of er een beveiligingsbeleid voor iOS-apps is geïmplementeerd voor de beveiligingsgroep van de gebruiker en op deze app wordt toegepast.
**Welkom bij de Intune Managed Browser**: Deze app werkt het beste wanneer deze wordt beheerd met Microsoft Intune. U kunt deze app altijd gebruiken om op internet te browsen en als de app wordt beheerd met Microsoft Intune, hebt u toegang tot extra functies voor gegevensbescherming. | Kan het vereiste app-beveiligingsbeleid voor de Intune Managed Browser-app niet detecteren. <br><br>De gebruiker kan de app nog gewoon gebruiken om op internet te surfen, maar de app wordt niet beheerd met Intune. | Controleer of er een beveiligingsbeleid voor iOS-apps is geïmplementeerd voor de beveiligingsgroep van de gebruiker en wordt toegepast op de app Intune Managed Browser.
**Aanmelden is mislukt**: u kunt op dit moment niet worden aangemeld. Probeer het later opnieuw. | Kan de gebruiker niet registreren bij de MAM-service nadat de gebruiker heeft geprobeerd om zich aan te melden met het werk-of schoolaccount. | Controleer of er een beveiligingsbeleid voor iOS-apps is geïmplementeerd voor de beveiligingsgroep van de gebruiker en op deze app wordt toegepast.
**Het account is niet ingesteld**: uw organisatie heeft het account niet ingesteld voor toegang tot werk- of schoolgegevens. Neem contact op met uw IT-beheerder voor hulp. | Het gebruikersaccount heeft geen licentie voor Intune A Direct. | Zorg ervoor dat er een licentie in de [Office-portal](http://portal.office.com) is toegewezen aan het account van de gebruiker.
**Het apparaat voldoet niet aan het beleid**: deze app kan niet worden gebruikt, omdat u een gekraakt apparaat gebruikt. Neem contact op met uw IT-beheerder voor hulp. | Intune heeft gedetecteerd dat de gebruiker een gekraakt apparaat gebruikt. | Zet de fabrieksinstellingen van het apparaat terug. Volg [deze instructies](https://support.apple.com/en-us/HT201274) op de ondersteuningssite van Apple.
**Internetverbinding vereist**: u moet zijn verbonden met internet om te kunnen verifiëren of u deze app mag gebruiken. | Het apparaat is niet verbonden met internet. | Verbind het apparaat met een WiFi- of datanetwerk.
**Onbekende fout**: probeer deze app opnieuw te starten. Als het probleem zich blijft voordoen, neemt u contact op met uw IT-beheerder voor ondersteuning. | Er is een onbekende fout opgetreden. | Wacht enige tijd en probeer het opnieuw. Als de fout zich blijft voordoen, maakt u [hier](/how-to-get-support-for-microsoft-intune.md) een ondersteuningsticket met Intune.
**Toegang tot gegevens van uw organisatie**: het werk- of schoolaccount dat u hebt opgegeven, heeft geen toegang tot deze app. Mogelijk moet u zich aanmelden met een ander account. Neem contact op met uw IT-beheerder voor hulp. | Intune heeft gedetecteerd dat de gebruiker zich probeert aan te melden met een tweede werk- of schoolaccount dat verschilt van het bij MAM geregistreerde account voor het apparaat. Er kan per apparaat slechts één werk- of schoolaccount tegelijkertijd door MAM worden beheerd. | Laat de gebruiker zich aanmelden met het account waarvan de gebruikersnaam vooraf is ingevuld op het aanmeldingsscherm. <br> <br> Of laat de gebruiker zich aanmelden met het nieuwe werk- of schoolaccount en verwijder het bestaande bij MAM geregistreerde account.
**Verbindingsprobleem**: er is een onverwacht verbindingsprobleem opgetreden. Controleer uw verbinding en probeer het opnieuw.  |  Er is een onverwachte fout opgetreden. | Wacht enige tijd en probeer het opnieuw. Als de fout zich blijft voordoen, maakt u [hier](/how-to-get-support-for-microsoft-intune.md) een ondersteuningsticket met Intune.
**Waarschuwing**: deze app kan niet meer worden gebruikt. Neem contact op met uw IT-beheerder voor meer informatie. | Kan het certificaat van de app niet valideren. | Zorg ervoor dat de versie van de app is bijgewerkt. <br><br> installeer de app opnieuw.
**Fout**: er is een probleem opgetreden waardoor deze app moet worden gesloten. Als de fout zich blijft voordoen, neemt u contact op met uw IT-beheerd. | Kan de pincode van de MAM-app in de sleutelhanger van Apple iOS niet lezen. | Start het apparaat opnieuw op. Zorg ervoor dat de versie van de app is bijgewerkt. <br><br> installeer de app opnieuw.


### <a name="issues-on-android"></a>Problemen met Android

Dialoogvenster/foutbericht | Oorzaak | Herstel |
-- | --- | --- |
**De app is niet ingesteld**: Deze app is niet ingesteld om door u te worden gebruikt. Neem contact op met uw IT-beheerder voor hulp. | Kan het vereiste app-beveiligingsbeleid voor de app niet detecteren. |Controleer of er een beveiligingsbeleid voor iOS-apps is geïmplementeerd voor de beveiligingsgroep van de gebruiker en op deze app wordt toegepast.
**Kan de app niet starten**: er is een probleem met het starten van uw app. Probeer de app of de bedrijfsportal-app van Intune bij te werken. Neem contact op met de IT-beheerder als u hulp nodig hebt. | Intune heeft een geldige app-beveiligingsbeleid voor de app gedetecteerd, maar de app loopt vast tijdens de MAM-initialisatie. | Zorg ervoor dat de versie van de app is bijgewerkt. <br><br> Zorg ervoor dat de bedrijfsportal van Intune op het apparaat is geïnstalleerd en is bijgewerkt. <br><br> Als de fout zich blijft voordoen, gebruikt u de bedrijfsportal-app om logboeken naar Intune te verzenden of om [hier](/how-to-get-support-for-microsoft-intune.md) een ondersteuningsticket te maken.
**Geen apps gevonden**: Er staan geen apps op dit apparaat waarmee u van uw organisatie inhoud mag openen. Neem contact op met uw IT-beheerder voor hulp. Neem contact op met uw IT-beheerder voor hulp. | De gebruiker probeert werk- of schoolgegevens te openen met een andere app, maar Intune kan geen andere beheerde apps vinden die de gegevens mogen openen. | Zorg ervoor dat er een beveiligingsbeleid voor Android-apps is geïmplementeerd voor de beveiliging van de gebruiker en dat het beleid wordt toegepast op minimaal nog één andere MAM-app waarmee de desbetreffende gegevens kunnen worden geopend.
**Aanmelden is mislukt**: probeer opnieuw aan te melden. Als dit probleem zich blijft voordoen, neemt u contact op met uw IT-beheerder voor ondersteuning. | Fout bij het verifiëren van het account waarmee de gebruiker zich probeert aan te melden. | Zorg ervoor dat de gebruiker zich aanmeldt met het werk- of schoolaccount dat al is geregistreerd bij de Intune MAM-service (het eerste werk- of schoolaccount dat is aangemeld bij deze app). <br><br> Wis de gegevens van de app. <br><br> Zorg ervoor dat de versie van de app is bijgewerkt. <br><br> Zorg ervoor de versie van de bedrijfsportal up-to-date is.
**Internetverbinding vereist**: U moet zijn verbonden met internet om te kunnen verifiëren of u deze app mag gebruiken. | Het apparaat is niet verbonden met internet. | Verbind het apparaat met een WiFi- of datanetwerk.
**Het apparaat voldoet niet aan het beleid**: Deze app kan niet worden gebruikt, omdat u een geroot apparaat gebruikt. Neem contact op met uw IT-beheerder voor hulp. | Intune heeft gedetecteerd dat de gebruiker een gekraakt geroot gebruikt. | Zet de fabrieksinstellingen van het apparaat terug.
**Het account is niet ingesteld**: Deze app moet worden beheerd met Microsoft Intune, maar uw account is niet ingesteld. Neem contact op met uw IT-beheerder voor hulp. | Het gebruikersaccount heeft geen licentie voor Intune A Direct. | Zorg ervoor dat er een licentie in de [Office-portal](http://portal.office.com) is toegewezen aan het account van de gebruiker.
**Kan de app niet registreren**: Deze app moet worden beheerd door Microsoft Intune, maar momenteel is het niet mogelijk de app te registreren. Neem contact op met uw IT-beheerder voor hulp. | De app wordt niet automatisch geregistreerd bij de MAM-service wanneer app-beveiligingsbeleid is vereist. | Wis de gegevens van de app. <br><br> Verzend logboeken via de bedrijfsportal-app naar Intune of dien [hier](/how-to-get-support-for-microsoft-intune.md) een ondersteuningsticket in.





### <a name="see-also"></a>Zie tevens
- [De Mobile Application Management-configuratie valideren](../deploy-use/validate-mobile-application-management.md)
- [Voorbereidingen voor het configureren van beleid voor het beheer van mobiele apps (Mobile App Management) met Microsoft Intune](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


