---
# required metadata

title: Vorige versies | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Vorige versies van Intune
## Maart 2016
### Wat is er nieuw vanaf 29 maart 2016
Met uitzondering van de update voor het algemene configuratiebeleid voor Windows 10, worden alle functies die op 29 maart 2016 worden vrijgeven ook ondersteund voor hybride klanten (Configuration Manager geïntegreerd met Intune). Hybride ondersteuning voor de update van het algemene configuratiebeleid voor Windows 10 wordt binnenkort beschikbaar. Voor sommige van deze functies is mogelijk de nieuwste versie van Configuration Manager vereist.

### App-beheer
- **MAM-besturingselementen om te voorkomen dat Outlook-contactpersonen worden gesynchroniseerd (iOS).** Er is een nieuwe instelling beschikbaar voor Mobile Application Management zonder apparaatinschrijving. Met deze instelling kunt u voorkomen dat een toepassing contactpersonen synchroniseert met het systeemeigen adresboek op iOS-apparaten. Wanneer deze instelling is ingeschakeld, kan de app niet langer contactpersonen in het systeemeigen adresboek opslaan. Wanneer deze instelling is uitgeschakeld, kan de app contactpersonen in het systeemeigen adresboek opslaan. Wanneer u een apparaat selectief wist, worden de contactpersonen verwijderd die al in het systeemeigen adresboek waren opgeslagen. Deze nieuwe instelling wordt ondersteund door de Outlook-toepassing op iOS-apparaten. Zie voor meer informatie over deze en andere instellingen [MAM-beleid maken en implementeren](https://technet.microsoft.com/en-us/library/dn292747.aspx).

### Toegangsbeheer
- **Skype voor Bedrijven Online biedt ondersteuning voor voorwaardelijke toegang.** Je kunt een beleid voor voorwaardelijke toegang instellen voor Skype voor Bedrijven Online, zodat het programma alleen toegankelijk is voor beheerde en compatibele iOS- en Android-apparaten. Eindgebruikers die zich willen aanmelden bij de mobiele app voor Skype voor Bedrijven op iOS en Android, worden gevraagd zich in te schrijven bij Intune en eventuele problemen met de compatibiliteit op te lossen. Hierna kan de aanmelding worden voltooid. Zie voor meer informatie [Toegang tot Skype voor Bedrijven Online beheren](https://technet.microsoft.com/en-us/library/mt695297.aspx).

### Apparaatbeheer
- **Intune-ondersteuning voor iOS 9.3.** Op maandag 21 maart heeft Apple aangekondigd dat iOS 9.3 beschikbaar wordt. Er is druk aan gewerkt om ervoor te zorgen dat Microsoft Intune compatibel is met de nieuwste versie van het mobiele besturingssysteem van Apple. [Intune biedt nu ondersteuning voor het beheer van iOS 9.3-apparaten](https://blogs.technet.microsoft.com/microsoftintune/2016/03/23/microsoft-intune-provides-support-for-ios-9-3/).

  Alle bestaande Intune-functies die momenteel beschikbaar zijn voor het beheren van iOS-apparaten blijven naadloos werken wanneer gebruikers hun apparaten upgraden naar iOS 9.3. iOS 9.3 wordt daarnaast nu ook ondersteund voor hybride klanten (Configuration Manager geïntegreerd met Intune).

- **Het algemene configuratiebeleid voor Windows 10 bevat nu instellingen voor het beheren van Windows Defender op ingeschreven Windows 10-pc’s.** Zie [Instellingen voor configuratiebeleid voor Windows 10 in Microsoft Intune](https://technet.microsoft.com/en-us/library/mt404697.aspx) voor meer informatie.


### Bedrijfsportal

- **Windows-app-pakketten die rechtstreeks via de bedrijfsportal-website beschikbaar zijn.** Gebruikers van pc's met Windows 8, Windows 8.1 en Windows RT kunnen nu Windows-app-pakketten (met de extensie .appx) rechtstreeks installeren vanaf de website van de bedrijfsportal. Eerder moest u de bedrijfsportal-app implementeren of moesten gebruikers deze installeren op hun apparaten om apps te installeren.

- **Gebruikers kunnen hun apparaat extern vergrendelen op de website van de bedrijfsportal.** Er is een nieuwe optie voor vergrendeling op afstand toegevoegd aan de website van de bedrijfsportal, zodat eindgebruikers hun apparaat via de portal op afstand kunnen vergrendelen als hun apparaat zoekgeraakt of gestolen is. Zie de [instructies voor eindgebruikers](https://technet.microsoft.com/library/mt590895.aspx/?wt.mc_id=ui#BKMK_iwp_remote_lock). In de volgende tabel ziet u een lijst met de beschikbare platformondersteuning voor vergrendelen op afstand voor Intune Standalone en Intune met Configuration Manager.

|Platform | Ondersteuningsgegevens|
|---------|----------------|
|Android |Ondersteund|
|iOS |Ondersteund|
|Windows 10 Mobile |Alleen ondersteund als op de telefoon een wachtwoordcode is ingesteld|
|Windows 10 Desktop |Niet ondersteund|
|Windows Phone 8,1 |Alleen ondersteund als op de telefoon een wachtwoordcode is ingesteld|
|Windows Phone 8.0 |Niet ondersteund|
|Pc (Windows 8.0 en eerder) |Niet ondersteund|
|Pc (Windows 8.1) |Niet ondersteund|

### Wat is er nieuw vanaf 10 maart 2016

### App-beheer

- **Profiteren van Open-In iOS-beheer voor apparaten die zijn ingeschreven bij een externe MDM-oplossing**
U kunt uw externe Mobile Device Manager-leverancier (MDM) gebruiken om te profiteren van Open-In iOS-beheer. U kunt de beperkingen in de configuratieprofielinstellingen configureren en de app implementeren via [Gegevensoverdracht tussen iOS-apps beheren](manage-data-transfer-between-ios-apps-with-microsoft-intune.md).

     Deze methode biedt twee belangrijke voordelen:

     1. Gebruikers moeten zich aanmelden met hun werkaccount voordat ze toegang tot zakelijke gegevens krijgen via Cloud Services of andere apps. Hiermee zorgt u ervoor dat het Mobile App Management-beleid (MAM) wordt toegepast bij het openen van de gegevens.

     2. Beheerde e-mailprofielen en andere beheerde apps die worden geïmplementeerd via een MDM-oplossing van derden kunnen bestanden en gegevens delen met apps met Intune MAM-beleid.

- **De Microsoft Outlook-app met MAM-beleid beheren voor apparaten die niet zijn ingeschreven bij Intune**
U kunt nu de Microsoft Outlook-app beheren op apparaten die niet zijn ingeschreven bij Intune, met het Intune Mobile Application Management-beleid. De bijgewerkte Microsoft Outlook-app met MAM-mogelijkheden is beschikbaar voor zowel [iOS](https://itunes.apple.com/us/app/microsoft-outlook-email-calendar/id951937596?mt=8)- als [Android](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook)-apparaten. Volg de instructies in het onderwerp [Beleid voor Mobile App Management maken en implementeren](https://technet.microsoft.com/library/mt627829.aspx) om MAM-beleid te maken.  


- **Configuratiebeleid voor mobiele apps biedt u meer flexibiliteit om gebruikersdetails op te geven voor iOS-apps**
U kunt de gebruikersinstellingen opgeven die een iOS-app mogelijk nodig heeft wanneer deze wordt geopend. U kunt bijvoorbeeld een netwerkpoort of een gebruikersnaam opgeven. Zie [iOS-apps met configuratiebeleid voor mobiele apps in Microsoft Intune configureren](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md) voor meer informatie.


- **Adobe Reader voor Microsoft Intune implementeren voor door Intune beheerde iOS-apparaten in uw onderneming**
De Adobe Reader-app voor iOS kan nu worden beheerd op ingeschreven apparaten met het Intune Mobile Application Management-beleid.

- **Ervoor zorgen dat geïmplementeerde webclips worden geopend in de Managed Browser**
U kunt doelwebclips implementeren op iOS- en Android-apparaten die alleen kunnen worden geopend met behulp van de Managed Browser. U implementeert bijvoorbeeld koppelingen naar bedrijfsresources via de bedrijfsportal, en wanneer gebruikers naar de koppelingen navigeren, worden deze rechtstreeks in de Managed Browser geopend zodat er sprake is van beveiliging via MAM-beleid. Zie voor meer informatie [Apps implementeren ](deploy-apps.md).


- **Windows Store voor Bedrijven-apps voor Windows 10-apparaten zoeken, beheren en distribueren via de Intune-beheerconsole**
In Intune is ondersteuning voor de Windows Store voor Bedrijven beschikbaar om u te helpen apps voor de Windows 10-apparaten die u beheert te zoeken, beheren en distribueren. In de Windows Store voor Bedrijven kunt u het proces voor het implementeren en bewaken van deze apps beheren via de Intune-beheerconsole: dezelfde console die u gebruikt voor het beheren van uw andere apps. De Windows Store voor Bedrijven beheert de inhoud en licenties van online gelicentieerde apps. Zie voor meer informatie [Apps beheren die u hebt aangeschaft in de Windows Store voor Bedrijven](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md).


### Apparaatbeheer
- **Distributie van PFX-certificaten voor iOS-apparaten**
Intune-beheerders kunnen iOS PFX-certificaten maken en implementeren voor Wi-Fi-, e-mail- en VPN-verificatie op iOS-apparaten. Deze functie is al beschikbaar voor Android- en Windows 10-apparaten. Voor meer informatie ziet u [Toegang tot bedrijfsbronnen inschakelen met behulp van certificaatprofielen](secure-resource-access-with-certificate-profiles.md).


- **Apps en beleidsregels toepassen op verschillende apparaatgroepen op basis van een gebruikerscategorieselectie**
Intune-beheerders kunnen nu aangepaste apparaatcategorieën definiëren waar gebruikers uit kunnen kiezen tijdens het inschrijven. Beheerders kunnen bijvoorbeeld hun gebruikers laten opgeven of ze een apparaat inschrijven dat gebruikt wordt voor de kassa, de vrachtwagen of het magazijn. Afhankelijk van de geselecteerde categorie wordt het apparaat lid van een Intune-apparaatgroep, welke kan worden gebruikt voor het implementeren van verschillende apps en beleidsregels voor het ingeschreven apparaat. Zie [Apparaten categoriseren met apparaatgroeptoewijzing](categorize-devices-with-device-group-mapping-in-microsoft-intune.md) voor meer informatie.

### Wijzigingen en updates voor de Microsoft-bedrijfsportal
In deze release zijn de volgende wijzigingen aangebracht aan de bedrijfsportal.

**Android-bedrijfsportal-app**

* Wanneer gebruikers een app openen die wordt beheerd via Mobile Application Management (MAM), krijgen ze een bericht te zien met de melding dat de app wordt beheerd door het bedrijf. Gebruikers kunnen nu tikken op Meer informatie om [meer informatie](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_use_mgd_apps) te ontvangen over wat het betekent als apps worden beheerd. Ze kunnen ook tikken op Niet opnieuw weergeven zodat het bericht niet meer wordt weergegeven bij het openen van de app.
* Er zijn ook nieuwe schermen toegevoegd om gebruikers door het inschrijvingsproces te leiden en meer informatie te bieden over waarom de gebruikers zich moeten inschrijven en over wat IT-beheerders wel en niet kunnen zien op de geregistreerde apparaten. Zie de [inschrijvingsinstructies](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc) voor meer informatie.
* Inschrijvingsfoutberichten worden nu weergegeven in de bedrijfsportal-app. Voorheen werden deze berichten weergegeven op de bedrijfsportal-website. Dankzij deze wijziging worden alle foutberichten nu op één plaats weergegeven in plaats van op twee verschillende plaatsen.


**iOS-bedrijfsportal-app**
* Wanneer gebruikers een app openen die wordt beheerd via Mobile Application Management (MAM), krijgen ze een bericht te zien met de melding dat de app wordt beheerd door het bedrijf. Gebruikers kunnen nu tikken op Meer informatie om [meer informatie](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_use_mgd_apps) te ontvangen over wat het betekent als apps worden beheerd. Ze kunnen ook tikken op Niet opnieuw weergeven zodat het bericht niet meer wordt weergegeven bij het openen van de app.
* Er zijn ook nieuwe schermen toegevoegd om gebruikers door het inschrijvingsproces te leiden en meer informatie te bieden over waarom de gebruikers zich moeten inschrijven en over wat IT-beheerders wel en niet kunnen zien op de geregistreerde apparaten. Zie de [inschrijvingsinstructies](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device) voor meer informatie.
* Inschrijvingsfoutberichten worden nu weergegeven in de bedrijfsportal-app. Voorheen werden deze berichten weergegeven op de bedrijfsportal-website. Dankzij deze wijziging worden alle foutberichten nu op één plaats weergegeven in plaats van op twee verschillende plaatsen.




## Februari 2016
### Wijzigingen en updates voor de Microsoft-bedrijfsportal

In deze release zijn de volgende wijzigingen aangebracht aan de bedrijfsportal.

#### Android-bedrijfsportal-app
- Er zijn ook nieuwe schermen toegevoegd om gebruikers door het inschrijvingsproces te leiden en meer informatie te bieden over waarom de gebruikers zich moeten inschrijven en over wat IT-beheerders wel en niet kunnen zien op de geregistreerde apparaten. Zie de [inschrijvingsinstructies](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc) voor meer informatie.
- Inschrijvingsfoutberichten worden nu weergegeven in de bedrijfsportal-app. Voorheen werden deze berichten weergegeven op de bedrijfsportal-website. Dankzij deze wijziging worden alle foutberichten nu op één plaats weergegeven in plaats van op twee verschillende plaatsen.

#### iOS-bedrijfsportal-app
 - Er zijn ook nieuwe schermen toegevoegd om gebruikers door het inschrijvingsproces te leiden en meer informatie te bieden over waarom de gebruikers zich moeten inschrijven en over wat IT-beheerders wel en niet kunnen zien op de geregistreerde apparaten. Zie de [inschrijvingsinstructies](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device) voor meer informatie.

 - Inschrijvingsfoutberichten worden nu weergegeven in de bedrijfsportal-app. Voorheen werden deze berichten weergegeven op de bedrijfsportal-website. Dankzij deze wijziging worden alle foutberichten nu op één plaats weergegeven in plaats van op twee verschillende plaatsen.


## Januari 2016

### Profiteren van Windows 10-functies
* **Voorwaardelijke toegang met Health Attestation van apparaten**
Intune-beheerders kunnen nu de status van Windows 10 Health Attestation van apparaten bekijken in de Intune-beheerconsole. Met Health Attestation van apparaten kan de beheerder zorgen dat clientcomputers over betrouwbare configuraties van BIOS, TPM en opstartsoftware beschikken. De functie Health Attestation van apparaten wordt alleen ondersteund op clientapparaten waarop Windows 10 wordt uitgevoerd en TPM 2 is ingeschakeld. Met Health Attestation van apparaten wordt het aantal apparaten weergegeven dat is ingeschakeld voor elk van de volgende:
    * Vroegtijdig starten van anti-malware
    * BitLocker
    * Beveiligd opstarten
    * Code-integriteit

    Lees [Inleiding in nalevingsbeleid voor apparaten voor Microsoft Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md) voor meer informatie over de apparaatstatusinstelling, verzamelde gegevenspunten en het statusverklaringsrapport. In de [HAS-servicedetails](https://msdn.microsoft.com/en-us/library/dn934876.aspx) staat meer uitleg over de service.

* **Windows 10 Passport for Work-beleid en certificaatbeheer**
Intune biedt de mogelijk van [integratie met Microsoft Passport for Work](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md). Dit is een alternatieve aanmeldingsmethode voor Windows 10 waarbij Active Directory of een Azure Active Directory-account wordt gebruikt ter vervanging van een wachtwoord, smartcard of virtuele smartcard. Met Passport kan de gebruiker zich aanmelden met een gebaar van de gebruiker in plaats van met een wachtwoord. Een gebaar van de gebruiker kan een eenvoudige pincode zijn, biometrische verificatie zoals Windows Hello of een extern apparaat zoals een vingerafdruklezer.

* **VPN voor specifieke toepassingen**
U kunt apps selecteren die automatisch via VPN verbinding maken met uw bedrijfsnetwerk. Maak de lijst met apps wanneer u het VPN-profiel instelt, zoals wordt beschreven in Gebruikers helpen om verbinding met hun werk te maken met behulp van VPN-profielen met Microsoft Intune.

* **Windows 10-ondersteuning voor Volledig wissen**
U kunt de opdracht Volledig wissen nu op afstand activeren voor Windows 10-desktopapparaten die zijn ingeschreven bij Intune via de Intune-beheerconsole. Bij het volledig wissen van Windows 10 worden de fabrieksinstellingen op het apparaat teruggezet.


### Het Apple-VPP (volume-aankoopprogramma) bijwerken
Intune kan u nu helpen bij het [beheren van apps die u hebt aangeschaft via het Apple-volume-aankoopprogramma (VPP) voor bedrijven](manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md). Dit omvat het synchroniseren van licentiegegevens tussen Apple en Intune en het bijhouden hoeveel exemplaren van elke app u hebt geïmplementeerd.

### IMEI-nummers gebruiken om apparaten in bedrijfseigendom te identificeren
U kunt nu [IMEI-nummers (International Mobile Equipment Identity) importeren](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) voor mobiele-apparaatplatforms met een IMEI-nummer om mobiele apparaten in bedrijfseigendom te identificeren. Wanneer apparaten met geïmporteerde IMEI-nummers zijn ingeschreven in Intune, worden deze gelabeld als bedrijfseigendom, zodat op die apparaten andere beleidsregels kunnen worden toegepast dan op persoonlijke apparaten.

### Er zijn nu meer apps compatibel met Intune MAM-beleid
Aanvullende apps van Microsoft-partners zijn nu compatibel met Intune Mobile Application Management-beleid (MAM) (voor apparaten die worden beheerd door Intune):
* Box for EMM (van Box Inc) - alleen iOS
* Adobe Reader (van Adobe) - alleen Android
* Foxit PDF Reader (van Foxit Corporation) - iOS en Android


### IE9-ondersteuning eindigt in januari
Vanaf februari 2016 wordt Internet Explorer 9 niet meer ondersteund als officiële browser voor toegang tot de website van de Microsoft Intune-bedrijfsportal, de Intune-accountportal en de Intune-beheerconsole. U moet dan migreren naar Internet Explorer 10 of hoger.

## December 2015
### Wijzigingen en updates voor de Microsoft-bedrijfsportal
In deze release zijn de volgende wijzigingen aangebracht aan de bedrijfsportal.

**Android-bedrijfsportal-app**

De volgende wijzigingen zijn aangebracht om te voldoen aan nieuwe Google-vereisten. Op apparaten met Android 6.0 en hoger worden twee nieuwe berichten weergegeven voor gebruikers:
* De bedrijfsportal toestaan telefoongesprekken uit te voeren en te beheren?
* De bedrijfsportal toegang verlenen tot foto's, media en bestanden op uw apparaat?

Zie de volgende tabellen voor meer informatie over deze twee berichten.



Berichttekst  |De bedrijfsportal toestaan telefoongesprekken uit te voeren en te beheren?  
---------|---------
Betekenis van het bericht     |  Het telefoonnummer en het IMEI-nummer van het apparaat van de gebruiker kunnen naar de Intune-service worden verzonden en worden weergegeven in de beheerconsole op de pagina Hardware.   </br></br>**OPMERKING: de bedrijfsportal-app voert nooit telefoongesprekken uit en beheert deze niet.** De berichttekst wordt beheerd door Google en kan niet worden gewijzigd. </br></br>Als u de pagina **Hardware** wilt weergeven, gaat u naar **Groepen** > **Alle mobiele apparaten** > **Apparaten**. Selecteer het apparaat van de gebruiker en ga naar **Eigenschappen weergeven** > **Hardware**.    
Waar en wanneer het bericht wordt weergegeven  | Het bericht wordt weergegeven wanneer gebruikers zich voor het eerst aanmelden bij de bedrijfsportal-app om hun apparaat in te schrijven.|         
Wat er gebeurt als gebruikers toegang toestaan  |  Het telefoonnummer en het IMEI-nummer van het apparaat worden weergegeven op de pagina Hardware in de beheerconsole. |         
Wat er gebeurt als gebruikers toegang weigeren     | Gebruikers kunnen de bedrijfsportal-app blijven gebruiken en hun apparaten inschrijven, maar het telefoonnummer en het IMEI-nummer van het apparaat van de gebruikers zijn leeg op de pagina Hardware in de beheerconsole.       </br></br> De tweede keer dat gebruikers zich aanmelden bij de bedrijfsportal-app nadat ze toegang hebben geweigerd, wordt in het bericht een selectievakje bij **Niet opnieuw vragen** weergegeven dat gebruikers kunnen selecteren zodat het bericht nooit meer wordt weergegeven.</br></br>Als gebruikers toegang verlenen en deze later weer intrekken, wordt het bericht de volgende keer dat gebruikers zich aanmelden bij de bedrijfsportal-app weergegeven na de registratie.</br></br>Als gebruikers later alsnog besluiten om toegang te verlenen, kunnen ze naar **Instellingen** > **Apps** > **Bedrijfsportal** > **Machtigingen** > **Telefoon** gaan en de machtiging instellen.
Meer informatie     |  Voor uw gebruikers: [aanmelden bij de bedrijfsportal](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_signin_cp)  </br></br>Voor IT-professionals: de informatie in deze tabel bevindt zich ook in [Gebruikers informatie geven over berichten over de bedrijfsportal-app](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs)   

Berichttekst  |De bedrijfsportal toegang verlenen tot foto's, media en bestanden op uw apparaat?  
---------|---------
Betekenis van het bericht     |  Het apparaat kan gegevenslogboeken schrijven naar de SD-kaart van het apparaat waardoor logboeken kunnen worden verplaatst via een USB-kabel.   </br></br>**OPMERKING: de bedrijfsportal-app gebruikt nooit foto's, media en bestanden van de gebruiker.** De berichttekst wordt beheerd door Google en kan niet worden gewijzigd.     
Waar en wanneer het bericht wordt weergegeven  | Het bericht wordt weergegeven wanneer gebruikers op **Gegevens verzenden** tikken om gegevenslogboeken te verzenden naar de IT-beheerder.|         
Wat er gebeurt als gebruikers toegang toestaan  |  De logboeken worden gekopieerd naar de SD-kaart. |         
Wat er gebeurt als gebruikers toegang weigeren     | Ze kunnen nog steeds gegevenslogboeken verzenden, maar de logboeken worden niet gekopieerd naar de SD-kaart van het apparaat.       </br></br> De tweede keer dat gebruikers zich aanmelden bij de bedrijfsportal-app nadat ze toegang hebben geweigerd, wordt in het bericht een selectievakje bij **Niet opnieuw vragen** weergegeven dat gebruikers kunnen selecteren zodat het bericht nooit meer wordt weergegeven.</br></br>Als gebruikers toegang verlenen en deze later weer intrekken, wordt het bericht de volgende keer dat ze logboeken verzenden weergegeven.</br></br>Als gebruikers later alsnog besluiten om toegang te verlenen, kunnen ze naar **Instellingen** > **Apps** > **Bedrijfsportal** > **Machtigingen** > **Opslag** gaan en de machtiging instellen.
Meer informatie     |  Voor uw gebruikers: [logboeken met diagnostische gegevens naar de IT-beheerder verzenden via e-mail](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_send_diag_logs)  </br></br>Voor IT-professionals: de informatie in deze tabel bevindt zich ook in [Gebruikers informatie geven over berichten over de bedrijfsportal-app](https://technet.microsoft.com/library/dn948527.aspx#BKMK_help_users_understd_msgs)   


**iOS-bedrijfsportal-app**
* Gebruikers kunnen nu Microsoft Outlook of andere e-mailapps gebruiken om diagnostische logboeken te verzenden naar de IT-beheerder. Eerder kon alleen de systeemeigen app worden gebruikt.
* Ondersteuning voor het Device Enrollment Program (DEP) van Apple en zakelijke ingeschreven apparaten is verbeterd. Voor meer informatie ziet u [U wordt gevraagd uw apparaat te identificeren wanneer u het apparaat probeert in te schrijven](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_id_your_device).
* In de lijst met geregistreerde apparaten van de gebruiker wordt nu een groen vinkje weergegeven naast het apparaat dat momenteel wordt gebruikt door de gebruiker. Voordat dit selectievakje werd toegevoegd, konden gebruikers niet zien welk ingeschreven apparaat ze gebruikten.

**Windows-bedrijfsportal-app**

Microsoft verzamelt automatisch anonieme gegevens over de prestaties en het gebruik van de bedrijfsportal om Microsoft-producten en -services te verbeteren. Eindgebruikers kunnen het verzamelen van gegevens uitschakelen met de instelling Gebruiksgegevens op hun apparaat. Beheerders hebben geen controle over het verzamelen van deze gegevens en ze kunnen de selectie van de gebruiker voor deze instelling niet wijzigen.



## November 2015
### App-beheer
Intune ondersteunt Mobile Application Management-beleidsregels (MAM) die helpen te voorkomen dat bedrijfsgegevens uitlekken naar consumenten-apps of -services. Deze beleidsregels zouden normaal alleen worden toegepast op mobiele apps op apparaten die ook bij Intune zijn ingeschreven voor Mobile Device Management (MDM).

In de update van deze maand biedt Intune aanvullende MAM-mogelijkheden met nieuwe apparaatklasses. U kunt nu, naast de apparaten die zijn ingeschreven bij Intune, MAM-beleid ook toepassen op:
* apparaten die worden beheerd door een andere MDM-oplossing
* apparaten die niet zijn ingeschreven bij een apparaatbeheersysteem, meestal BYO-apparaten (Bring Your Own)

U vindt meer informatie over deze nieuwe MAM-mogelijkheden in de volgende blogberichten:
* [Beheerde mobiele productiviteit verbeteren](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)
* [Nieuwe mogelijkheden van Microsoft Enterprise Mobility aangekondigd](http://blogs.technet.com/b/microsoftintune/archive/2015/11/17/enhancing-managed-mobile-productivity.aspx)

Hier volgen bovendien enkele belangrijke functies en aanvullende informatie over de MAM-functies van Intune:
* Bedrijfsgegevens worden geïsoleerd van de klantgegevens in apps die geschikt zijn voor Intune, waaronder Office Mobile-apps, apps van derden met de Intune-SDK of line-of-business-apps die zijn ingepakt door Intune.
* Bedrijfsgegevens kunnen worden gedeeld (**knippen/kopiëren/plakken**) tussen bedrijfs-apps, terwijl wordt voorkomen dat bedrijfsgegevens worden gedeeld in persoonlijke apps. Lees [Hoe MAM-beleid app-gegevens beschermt](https://technet.microsoft.com/library/mt627825.aspx) voor meer informatie. In dit voorbeeldscenario, waarin [de Microsoft Word-app wordt gebruik voor het werk en persoonlijke taken](https://technet.microsoft.com/library/mt627827.aspx), ziet u hoe het delen van bedrijfsgegevens met persoonlijke apps wordt voorkomen.
* Beleidsregels ter preventie van het verlies van sleutelgegevens zoals pincodes per app, ‘opslaan als’-besturingselementen en beheerd gegevens delen tussen apps. Zie [Beleid voor Mobile App Management maken en implementeren met Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx) voor een lijst met alle beleidsregels.
* Word, Excel, PowerPoint, Outlook, OneNote en OneDrive voor Bedrijven hebben deze nieuwe functies en kunnen worden beheerd met en zonder apparaatinschrijving. Er zijn systeemeigen mogelijkheden voor preventie van gegevensverlies ingebouwd in de standaard Office-apps uit de App Store en Google Play. Hierbij is er geen noodzaak voor het inpakken van apps of sideloading.
* Voor meer informatie over aan de slag gaan, ziet u [Aan de slag met beleid voor het beheer van mobiele apps in de Azure-portal](https://technet.microsoft.com/library/mt627830.aspx). Voor meer informatie over het configureren en implementeren van Mobile App Management-beleid ziet u [Beleid voor Mobile App Management maken en implementeren met Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx).
* Wanneer eindgebruikers zich in de app verifiëren met hun bedrijfsreferenties, worden de mogelijkheden voor preventie van gegevensverlies automatisch ingesteld. Het onderwerp [Eindgebruikerservaring voor apps die zijn gekoppeld aan MAM-beleid van Microsoft Intune](https://technet.microsoft.com/library/mt627827.aspx) bevat enkele voorbeeldscenario’s over het benaderen van OneDrive op iOS- en Android-apparaten.
* Werkt op iOS- en Android-apparaten.

De lijst van [Microsoft-apps die u met MAM-beleidsregels van Microsoft Intune kunt gebruiken](https://technet.microsoft.com/library/dn708489.aspx) is bijgewerkt met de nieuwste apps.

### Apparaatbeheer
 **Mac OS X-apparaatbeheer**
Met Intune kunt u nu Mac OS X-apparaten inschrijven en beheren. U kunt het volgende doen met uw Mac OS X-apparaten:
* Apparaten inschrijven om ze te laten beheren door Intune. Zie [iOS- en Mac-beheer instellen met Microsoft Intune](https://technet.microsoft.com/library/dn408185.aspx).
* Instellingen beheren voor apparaten met een algemeen configuratiebeleid Zie [Instellingen voor configuratiebeleid voor Mac OS X in Microsoft Intune](https://technet.microsoft.com/library/mt627823.aspx).
* Mac OS X-instellingen implementeren die u hebt gemaakt met de Apple Configurator. Zie [Aangepaste beleidsinstellingen voor Mac OS X in Microsoft Intune](https://technet.microsoft.com/library/mt627820.aspx).
* Hardware- en software-inventarisaties verzamelen van Mac OS X-apparaten. Zie [Inzicht in uw apparaten met inventarisaties in Microsoft Intune](https://technet.microsoft.com/library/jj733634.aspx).
* Nieuwe rapporten genereren met informatie over de Mac OS X-apparaten die u beheert. Zie [Microsoft Intune-bewerkingen begrijpen met behulp van rapporten](https://technet.microsoft.com/library/dn646977.aspx).

**Nieuwe Edge-browserinstellingen voor Windows-10-apparaten**
Er zijn nieuwe instellingen toegevoegd aan de het algemene configuratiebeleid van Windows 10 waarmee u instellingen en functies van de Microsoft Edge-browser kunt beheren. Zie [Instellingen voor configuratiebeleid voor Windows 10 in Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx).

**E-mailprofielen**
Er is een nieuw beleid voor e-mailprofielen toegevoegd voor (mobiele) Windows 10-apparaten. Zie [Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](https://technet.microsoft.com/library/dn646984.aspx).

**Nieuwe beleidsinstellingen voor naleving**
De volgende nieuwe beveiligings- en systeembeleidinstellingen zijn toegevoegd aan de lijst met nalevingsbeleidsregels:
* Om ervoor te zorgen dat apparaten met Windows 8.1 of hoger die toegang hebben tot uw bedrijfsresources beschikken over de nieuwste updates, gebruikt u de instelling **Automatische updates vereisen**. U kunt ook opgeven welk type updates automatisch moet worden geïnstalleerd: ofwel alle als belangrijk gemarkeerde updates worden geïnstalleerd of alle updates die als belangrijk of aanbevolen zijn gemarkeerd. Zie voor de volledige lijst met instellingen voor nalevingsbeleid [Nalevingsbeleid voor apparaten beheren voor Microsoft Intune](https://technet.microsoft.com/library/dn705843.aspx).
* Met de nieuwe instelling **Wachtwoord vereisen wanneer het apparaat wordt geactiveerd vanuit een niet-actieve status** in combinatie met de bestaande instelling **Minuten van inactiviteit voordat wachtwoord vereist is** kunt u een nalevingsinstelling maken waarbij de eindgebruiker een wachtwoord moet invoeren om een apparaat te gebruiken dat al een bepaalde tijd inactief is.

**Nieuwe beleidsopties voor voorwaardelijke toegang**
U kunt beleidsregels voor voorwaardelijke toegang toepassen op **alle gebruikers** in een nieuw of bestaand beleid voor voorwaardelijke toegang. Alle gebruikers met een licentie voor Intune en Office 365 moeten hun apparaten inschrijven. Als het apparaatplatform niet wordt ondersteund door Intune, wordt de toegang tot clienttoepassingen geblokkeerd via [aanmelding op basis van Active Directory-verificatie (moderne verificatie)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/).

U kunt ook opgeven dat het beleid voor voorwaardelijke toegang van toepassing is op **alle platforms**.  Elke clienttoepassing die gebruikmaakt van [aanmelding op basis van Active Directory-verificatie (moderne verificatie)](https://blogs.office.com/2014/11/12/office-2013-updated-authentication-enabling-multi-factor-authentication-saml-identity-providers/), moet voldoen aan het beleid voor voorwaardelijke toegang. Als het platform niet door Intune wordt ondersteund, wordt het geblokkeerd.

### Wijzigingen en updates voor de Microsoft-bedrijfsportal
In deze release zijn de volgende wijzigingen aangebracht aan de bedrijfsportal-apps:

* **Android**: er is een welkomstscherm toegevoegd aan de Android-bedrijfsportal-app om gebruikers meer inzicht te geven in het doel van de bedrijfsportal-app. Dit scherm is bedoeld om de app alleen beschikbaar te stellen als download voor gebruikers van bedrijven die geen Intune-abonnement hebben.

* **iOS**: Intune ondersteunt nu de inschrijving van Mac OS X-apparaten via de [bedrijfsportalwebsite](https://portal.manage.microsoft.com). Zie [Uw Mac OS X-apparaat inschrijven bij Intune](https://technet.microsoft.com/library/mt598622.aspx) voor instructies.

* **Bedrijfsportalwebsite**: gebruikers die hun apparaat bij Intune hebben ingeschreven kunnen nu hun wachtwoordcode opnieuw instellen met de optie **Wachtwoordcode opnieuw instellen** op de bedrijfsportalwebsite. Eerder konden alleen IT-beheerders de wachtwoordcodes van gebruikers opnieuw instellen. De optie Wachtwoordcode opnieuw instellen wordt niet ondersteund op Windows 8.1- en Windows RT-apparaten. De optie wordt alleen weergegeven wanneer apparaten zijn ingeschreven in Mobile Device Management (MDM) of MDM met Exchange ActiveSync. Zie [Uw wachtwoordcode opnieuw instellen](https://technet.microsoft.com/library/mt590895.aspx) voor gebruikersinstructies.

### Wijzigingen in de licentieverlening voor hoofdbeheerders
In oktober is bekendgemaakt dat hoofdbeheerders (ook wel tenantbeheerders genoemd) de reguliere beheertaken zouden kunnen voortzetten zonder afzonderlijke Intune- of Enterprise Mobility Suite-licentie (ESM). Als hoofdbeheerders echter de service willen gebruiken, bijvoorbeeld om hun eigen apparaat in te schrijven, een bedrijfsapparaat in te schrijven of om de Intune-bedrijfsportal te gebruiken, moeten ze net als anderen beschikken over een Intune- of EMS-licentie. Hieronder vindt u aanvullende informatie.
* In de Intune-bedrijfsportal kunnen eindgebruikers:
    * hun apparaat inschrijven
    * de status van hun apparaten weergeven
    * software downloaden die een hoofdbeheerder heeft geïmplementeerd voor de organisatie
    * koppelingen zoeken die door de hoofdbeheerder zijn gepubliceerd met contactgegevens van de IT-afdeling

    [Meer informatie over de bedrijfsportal](https://technet.microsoft.com/library/dn646966.aspx#BKMK_CompanyPortal) en [manieren om de bedrijfsportal aan te passen](https://technet.microsoft.com/library/dn646983.aspx#BKMK_ConfigureCompanyPortal).
* De persoon die zich aanmeldt om Intune of EMS te kopen namens een organisatie, wordt automatisch de eerste hoofdbeheerder in de tenant. Sinds deze herfst wijst Intune automatisch een Intune- of EMS-licentie toe aan die eerste hoofdbeheerder, als onderdeel van de overstap op de [Office 365-portal](http://portal.office.com/) en het buiten gebruik stellen van de [Intune-accountportal](http://account.manage.microsoft.com/). Er kunnen zonder afzonderlijke Intune- en EMS-licenties eventueel andere hoofdbeheerders worden toegevoegd voor het dagelijkse beheer. Als er acties worden uitgevoerd als eindgebruiker en wanneer er eigen (of bedrijfs)apparaten worden ingeschreven, of wanneer er software wordt gedownload via de bedrijfsportal, moet er toch een licentie worden aangeschaft, net als voor andere gebruikers het geval is.
* De wijziging wordt gefaseerd geïmplementeerd en is van toepassing vanaf januari 2016.
* Voor Microsoft-partners heeft deze wijziging geen invloed op het vermogen om de service namens klanten te beheren. Voor eindgebruikerstaken moet een gebruiker beschikken over een Intune- of EMS-licentie, bijvoorbeeld als deze een apparaat wilt inschrijven en software via de bedrijfsportal wilt openen of downloaden.

Als u vragen hebt over deze wijziging, kunt u gerust contact opnemen met het ondersteuningsteam van Intune:
* [Ondersteuningskanalen voor Microsoft Intune](https://technet.microsoft.com/library/jj839713.aspx)
* [Communityondersteuning](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod)

Voor algemene feedback over Microsoft Intune en het rapporteren van ontwerpwijzigingsaanvragen (DCR’s) en fouten, gaat u naar [Intune UserVoice](https://microsoftintune.uservoice.com/).


### Wat is er nieuw in Intune-documentatie -- november 2015
**Nieuwe inhoud**
* [Instellingen voor configuratiebeleid voor Mac OS X in Microsoft Intune](https://technet.microsoft.com/library/mt627823.aspx): apparaatinstellingen en functies beheren voor Mac OS X-apparaten.
* [Aangepaste beleidsinstellingen voor Mac OS X in Microsoft Intune](https://technet.microsoft.com/library/mt627820.aspx): Mac OS X-apparaatinstellingen implementeren die u hebt gemaakt met het hulpprogramma Apple Configurator.
* [App-beleid voor het voorkomen van gegevensverlies configureren met Microsoft Intune](https://technet.microsoft.com/library/mt627825.aspx): bevat informatie over de scenario’s waarin Mobile App Management-beleid wordt ondersteund en hoe het beleid werkt bij het beveiligen van gegevens.
* [Aan de slag met beleid voor het beheer van mobiele app in de Azure-portal](https://technet.microsoft.com/library/mt627830.aspx): wat u nodig hebt om aan de slag te gaan met de Azure Preview Portal voor Mobile App Management-beleid.
* [Beleid voor Mobile App Management maken en implementeren met Microsoft Intune](https://technet.microsoft.com/library/mt627829.aspx): bevat een stapsgewijze walkthrough over het maken van Mobile App Management-beleid in de Azure Preview Portal.
* [Mobile App Management-beleid bewaken met Microsoft Intune](https://technet.microsoft.com/library/mt627824.aspx): informatie over het bewaken van Mobile App Management-beleid via de Azure Preview Portal.
* [Microsoft Intune MAM-beleid en iOS Open in](https://technet.microsoft.com/library/mt627821.aspx): informatie over hoe Mobile App Management-beleid werkt met de functie iOS Open in.
* [Eindgebruikerservaring voor apps die zijn gekoppeld aan MAM-beleid van Microsoft Intune](https://technet.microsoft.com/library/mt627827.aspx): wat de ervaring voor eindgebruikers is wanneer apps worden gebruikt die zijn gekoppeld aan Mobile App Management-beleid.
* [Bedrijfsgegevens van beheerde apps wissen met Microsoft Intune](https://technet.microsoft.com/library/mt627826.aspx): hoe u gegevens van bedrijfsapps kunt wissen.

**Bijgewerkte inhoud**
* [Instellingen voor configuratiebeleid voor Windows 10 in Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx): nieuwe Edge-browserinstellingen toegevoegd.
* [iOS- en Mac-beheer instellen met Microsoft Intune](http://technet.microsoft.com/library/dn408185.aspx): informatie toegevoegd over het inschrijven van Mac OS X-apparaten.
* [Inzicht in uw apparaten met inventarisaties in Microsoft Intune](https://technet.microsoft.com/library/jj733634.aspx): informatie toegevoegd over de inventarisaties die worden verzameld van Mac OS X-apparaten. Het onderwerp met de nieuwste informatie over alle apparaatplatforms is ook bijgewerkt.
* [Microsoft Intune-bewerkingen begrijpen met behulp van rapporten](https://technet.microsoft.com/library/dn646977.aspx): informatie toegevoegd over de twee nieuwe rapporten die worden gebruikt om informatie weer te geven over uw beheerde Mac OS X-apparaten.
* [Nalevingsbeleid voor apparaten beheren voor Microsoft Intune](https://technet.microsoft.com/library/dn705843.aspx): informatie toegevoegd over het nieuwe nalevingsbeleid voor het vereisen van automatische updates en wachtwoorden wanneer een apparaat wordt geactiveerd vanuit een niet-actieve status.
* [Toegang tot e-mail beheren met Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx): informatie toegevoegd over de mogelijkheid om beleid voor voorwaardelijke toegang toe te passen op alle platforms en alle gebruikers.
* [Toegang tot SharePoint Online beheren met Microsoft Intune](https://technet.microsoft.com/library/dn705844.aspx): informatie toegevoegd over de mogelijkheid om beleid voor voorwaardelijke toegang toe te passen op alle platforms en alle gebruikers.

## Oktober 2015

### Updates voor voorwaardelijke toegang voor de on-premises Exchange-toepassing
**U kunt nu toegang tot Exchange ActiveSync-e-mail toestaan voor compatibele apparaten die zijn ingeschreven bij Intune, wanneer de algemene Exchange-regel is ingesteld op blokkeren of in quarantaine plaatsen** Tot nu toe moest de algemene Exchange-regel worden ingesteld op **Toestaan** om e-mailtoegang toe te staan op ingeschreven en compatibele apparaten.

Door deze service-update is deze instelling niet langer een vereiste voor voorwaardelijke toegang. Als uw Exchange-omgeving vereist dat de standaard toegepaste globale regel moet worden ingesteld op **Blokkeren/In quarantaine**, schakelt u gewoon het selectievakje **Standaardregel negeren** in op de pagina met het beleid voor voorwaardelijke toegang tot de on-premises Exchange-toepassing. Het onderwerp [Toegang tot e-mail beheren met Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx) bevat meer informatie over de regels en de daaruit voortkomende meldingen voor de eindgebruikers.

**Nieuwe mogelijkheid om in e-mailberichten in quarantaine met één klik een apparaat in te schrijven**: het inschrijven vanuit een e-mailbericht in quarantaine is vereenvoudigd en kan nu met één klik worden gedaan. Door deze service-update hoeven eindgebruikers maar op één koppeling in het e-mailbericht in quarantaine te klikken om het apparaat bij de bedrijfsportal-app in te schrijven.
### Updates voor mobiele apparaten en appbeheer
**Android** Alle Intune-beheerfuncties ondersteunen nu Android 6.0 (Marshmallow) zoals is beschreven in dit blogbericht: [Microsoft Intune Provides Day 0 Support for Android Marshmallow](http://blogs.technet.com/b/microsoftintune/archive/2015/10/09/microsoft-intune-to-provide-day-0-support-for-android-marshmallow.aspx)

**iOS** U kunt geen nieuwe apps meer implementeren op iOS-apparaten met een besturingssysteem dat ouder is dan iOS 7.1. Eventuele bestaande geïmplementeerde apps op apparaten met een ouder besturingssysteem dan iOS 7.1 blijven werken en worden beheerd door Intune.

**Windows 10** Intune ondersteunt nu de implementatie van Windows 10 Universal-apps met een software-installatieprogramma van het type **App-pakket voor Windows**. Zie [Aan de slag met app-implementatie in Microsoft Intune](http://technet.microsoft.com/en-US/library/dn646955.aspx) voor meer informatie en vereisten.


### Wijzigingen en updates voor Microsoft-bedrijfsportal-apps
In deze release zijn de volgende wijzigingen aangebracht aan de bedrijfsportal-apps:
**iOS**
Er zijn nieuwe knoppen aan de bedrijfsportal-app zodat gebruikers eenvoudiger logboeken met diagnostische gegevens kunnen verzenden naar de IT-beheerders:

|Naam van de knop|Waar deze wordt weergegeven|
|------------|---------------|
|Rapport|Waarschuwingsberichten bij fouten|
|Diagnostisch rapport verzenden|Het scherm Over van de bedrijfsportal-app|


>[!div class="step-by-step"]

>[&larr; **Wat is er nieuw in Intune?**](whats-new-in-microsoft-intune.md)    


<!--HONumber=May16_HO1-->


