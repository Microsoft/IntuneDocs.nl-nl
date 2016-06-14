---
# required metadata

title: Wat is er nieuw? | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Wat is er nieuw in Microsoft Intune?

## April 2016
Al deze functies worden ook ondersteund voor hybride klanten (Configuration Manager geïntegreerd met Intune).
### App-beheer
- **Naleving van beleid door MAM-gebruikers.**
U kunt nu de [status](monitor-mobile-app-management-policies-with-Microsoft-Intune.md) van uw beleid voor toepassingsbeheer bekijken voor gebruikers in uw AAD-tenant (Azure Active Directory). Dit omvat:
   - Apparaten
   - Apps op het apparaat

   Statuswaarden:

   **Ingecheckt**: geeft aan dat het beleid is geïmplementeerd voor de gebruiker, dat de app is gebruikt in een werkgerelateerde context en dat het beleid is ontvangen.

    **Niet ingecheckt**: geeft aan dat het beleid voor de gebruiker is geïmplementeerd, maar dat de app sindsdien niet is gebruikt in een werkgerelateerde context.


- **MAM-besturingselementen om te voorkomen dat Outlook-contactpersonen worden gesynchroniseerd (Android).**
Er is een nieuwe instelling beschikbaar voor [Mobile Application Management](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) zonder apparaatinschrijving. Met deze instelling kunt u voorkomen dat een toepassing contactpersonen synchroniseert met het systeemeigen adresboek op Android-apparaten. Wanneer deze instelling is ingeschakeld, kunnen doeltoepassingen niet langer contactpersonen in het systeemeigen adresboek opslaan. Wanneer deze instelling is uitgeschakeld, kunnen doeltoepassingen wel contactpersonen in het systeemeigen adresboek opslaan. Wanneer u [een apparaat of app op afstand wist of verwijdert](wipe-managed-company-app-data-with-Microsoft-Intune.md), worden de contactpersonen verwijderd die al in het systeemeigen adresboek zijn opgeslagen. Deze nieuwe instelling wordt in eerste instantie ondersteund door de Outlook-toepassing op Android-apparaten.

### Apparaatbeheer
- **Nummerherkenning voor apparaten die bedrijfseigendom zijn.** Telefoons die zijn aangemerkt als bedrijfseigendom, worden nu aangeduid met hun volledige telefoonnummer wanneer u bijvoorbeeld een inventarisrapport voor mobiele apparaten uitvoert. Telefoonnummers voor BYOD-apparaten worden nog steeds gemaskeerd met ***, waarbij alleen de laatste 4 cijfers worden weergegeven.


### Updates voor bedrijfsportal
**Bedrijfsportal-app voor Android**
Gebruikers die hun apparaat niet bij Intune hebben ingeschreven en bij wie niet het juiste certificaat is geïnstalleerd, kunnen zich niet aanmelden bij de bedrijfsportal-app voor Android en zien het bericht 'U kunt u niet aanmelden omdat een vereist certificaat ontbreekt op het apparaat'. In het bericht staat een koppeling naar 'Hoe u dit oplost', waarop gebruikers kunnen tikken om instructies te zien voor het installeren van het certificaat. Zie [Er ontbreekt een vereist certificaat voor uw apparaat](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing) om te zien welke stappen eindgebruikers moeten volgen om het probleem op te lossen..

**Bedrijfsportal-app voor iOS**
Er is ondersteuning toegevoegd voor de actie 'veeg naar beneden om te verversen' om de inhoud van het startscherm (met onder meer de lijst met apps, de lijst met apparaten en de contactgegevens van de IT-afdeling) te vernieuwen. De actie 'veeg naar beneden om te verversen' controleert niet op naleving van beleid of beleidsgegevens. Dat kunt u doen door de tegel voor uw huidige apparaat te selecteren en op de knop **Synchroniseren** te tikken.

**Bedrijfsportal-app voor Windows 10 Mobile en Windows Phone 8.1**
Eindgebruikers die LOB-apps installeren, hebben nu een verbeterde ervaring tijdens de installatie van deze apps. Als de app-installatie lang duurt, kunnen gebruikers hun apparaat handmatig synchroniseren om hervatting van het synchronisatieproces af te dwingen. Zie [Uw apparaat handmatig synchroniseren om de installatie van apps te versnellen](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually) om de instructies voor eindgebruikers te bekijken.

**Bedrijfsportalwebsite**
Wanneer gebruikers van Windows 10 Mobile en Windows Phone 8.1 LOB-apps installeren, zien ze nu de volgende nieuwe statussen, waardoor ze meer details over de status van hun installatie krijgen:

* **In afwachting van synchronisatie van het apparaat**: de gebruiker heeft op Installeren getikt en er wordt nu geprobeerd het apparaat te synchroniseren met de Intune-infrastructuur. Synchronisatie is vereist voordat de installatie kan worden voltooid. Het bericht 'In afwachting van synchronisatie van het apparaat' is ook een koppeling waarop gebruikers kunnen tikken om [instructies](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually) te zien over hoe zij hun apparaat handmatig kunnen synchroniseren met Intune als het synchronisatieproces lang duurt of vastloopt.
* **Downloaden**: het downloadverzoek van de gebruiker wordt verwerkt en het apparaat downloadt en installeert de app.

Voordat deze statussen werden toegevoegd, raakten gebruikers in de war als de installatie van een app lang duurde, omdat ze alleen de status 'Installeren' zagen, die mogelijk uren lang op het scherm bleef staan. Het toevoegen van de nieuwe statussen betekent dat gebruikers in plaats van ondersteuning te bellen nu op de koppeling 'In afwachting van synchronisatie van het apparaat' kunnen tikken en de instructies voor het afdwingen van hervatting van het synchronisatieproces kunnen volgen.

### Binnenkort

**Wijzigingen in apparaatinschrijvingsmanager-accounts.** Om de prestaties en schaalbaarheid te verbeteren, worden in het deelvenster Mijn apparaten van de bedrijfsportal-app niet meer alle apparaatinschrijvingsmanager-apparaten door Intune weergegeven. Alleen het lokale apparaat waarop de app wordt uitgevoerd, wordt weergegeven en wel alleen als het apparaat is ingeschreven via de bedrijfsportal-app. De DEM-gebruiker kan acties op het lokale apparaat uitvoeren, maar extern beheer van andere ingeschreven apparaten kan alleen worden uitgevoerd vanuit de Intune-beheerconsole.  Daarnaast is het gebruik in Intune van DEM-accounts met het Apple Device Enrollment Program of het hulpprogramma Apple Configurator beëindigd. Deze twee inschrijvingsmethoden bieden al ondersteuning voor gebruikersloze inschrijving voor gedeelde iOS-apparaten.  Gebruik alleen DEM-accounts wanneer gebruikersloze inschrijving voor gedeelde apparaten niet beschikbaar is.

Blijf op de hoogte van toekomstige ontwikkelingen op het gebied van Intune met de [Cloud Platform Roadmap](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).


## Vorige versies van Intune
Raadpleeg het artikel over [vorige Intune-releases](previous-intune-releases.md) als u wilt zien wat er de afgelopen zes maanden voor Intune is uitgekomen.



### Zie tevens
* [Microsoft Intune-blog](http://go.microsoft.com/fwlink/?LinkID=273882)


<!--HONumber=May16_HO1-->


