---
title: Beleidsregels voor apparaten, profielen, en Q&A met Intune - Azure | Microsoft Docs
description: Meer informatie over de verschillende beleidsregels en profielen die u in Microsoft Intune kunt gebruiken, met inbegrip van beleid voor het configureren van apparaten, toegang krijgen tot bedrijfsresources, inschakelen van voorwaardelijke toegang en bedrijfsapparaten registreren. U krijgt ook antwoorden op veelgestelde vragen.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 09bae0b9-4f79-4658-8ca1-a71ab992c1b2
ROBOTS: ''
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: 3b1115a91707c639caba6410ace3c2e255e40a39
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52184995"
---
# <a name="manage-settings-and-features-on-your-devices-with-intune-policies"></a>Instellingen en functies op uw apparaten beheren met Intune-beleid

Microsoft Intune-*beleid* bestaat uit groepen instellingen waarmee functies worden beheerd op mobiele apparaten en computers. U maakt beleidsregels met behulp van sjablonen die aanbevolen of aangepaste instellingen bevatten. Vervolgens implementeert u deze naar apparaat- of gebruikersgroepen.

## <a name="types-of-policies"></a>Typen beleidsregels

Intune-beleid valt in de volgende categorieën: De categorie die u gebruikt, is van invloed op hoe u het beleid maakt en implementeert.

- **Configuratiebeleid:**: deze optie wordt doorgaans gebruikt om beveiligingsinstellingen en -functies op uw apparaten te beheren, inclusief toegang tot bedrijfsresources. Aan de slag met [Intune-apparaatprofielen](device-profiles.md).
- **Apparaatnalevingsbeleid**: hiermee definieert u de regels en instellingen waaraan een apparaat moet voldoen om als compatibel te worden beschouwd met het beleid voor voorwaardelijke toegang. U kunt nalevingsbeleid ook gebruiken om de naleving van apparaten te bewaken en te herstellen, onafhankelijk van voorwaardelijke toegang. Aan de slag met [apparaatnalevingsbeleid](device-compliance-get-started.md).
- **Beleid voor voorwaardelijke toegang**: deze optie helpt u bij het beveiligen van e-mail en andere services op basis van de door u opgegeven voorwaarden. [Wat is voorwaardelijke toegang](conditional-access.md) en [gebruikelijke manieren om voorwaardelijke toegang te gebruiken](conditional-access-intune-common-ways-use.md) zijn goede resources om mee aan de slag te gaan.
- **Inschrijvingsbeleid voor bedrijfsapparaten**: zie [iOS-apparaten registreren](ios-enroll.md) voor meer informatie over het registratiebeleid voor bedrijfsapparaten.

## <a name="frequently-asked-questions-about-intune-policies"></a>Veelgestelde vragen over het Intune-beleid

### <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-being-deployed"></a>Hoe lang duurt het voor mobiele apparaten een beleid of apps ontvangen nadat deze zijn geïmplementeerd?
Wanneer er een beleid of een app wordt geïmplementeerd, probeert Intune het apparaat onmiddellijk te melden dat het moet inchecken bij de Intune-service. Deze stap neemt meestal minder dan vijf minuten in beslag.

Als een apparaat geen controle uitvoert of het beleid niet kan worden opgehaald nadat de eerste melding daarover is verzonden, doet Intune nog drie pogingen.  Als het apparaat offline is (bijvoorbeeld omdat het is uitgeschakeld of niet is verbonden met een netwerk), kan het geen meldingen ontvangen. In dat geval ontvangt het apparaat het beleid bij de volgende geplande controle bij de Intune-service en wel als volgt:

| Platform | Incheckfrequentie |
| --- | --- |
| iOS | Om de 6 uur | 
| Mac OS X | Om de 6 uur |
| Android | Om de 8 uur | 
| Windows Phone | Om de 8 uur | 
| Windows 8.1  | Om de 8 uur |  
| Pc’s met Windows 10 die als apparaten zijn geregistreerd | Om de 8 uur | 

Als het apparaat recent is geregistreerd, is de incheckfrequentie hoger, en wel als volgt:

| Platform | Frequentie |
| --- | --- |
| iOS | Om de 15 minuten gedurende 6 uur en daarna om de 6 uur |  
| Mac OS X | Om de 15 minuten gedurende 6 uur en daarna om de 6 uur | 
| Android | Om de 3 minuten gedurende 15 minuten en daarna om de 15 minuten gedurende 2 uur en vervolgens om de 8 uur | 
| Windows Phone | Om de 5 minuten gedurende 15 minuten en daarna om de 15 minuten gedurende 2 uur en vervolgens om de 8 uur | 
| Windows-computers die als apparaten zijn ingeschreven | Elke 3 minuten gedurende 30 minuten en vervolgens om de 8 uur | 

Gebruikers kunnen ook de bedrijfsportal-app openen en het apparaat onmiddellijk synchroniseren om op elk gewenst moment op aanwezig beleid te controleren.

### <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Welke acties zorgen ervoor dat Intune onmiddellijk een melding naar een apparaat verzendt?
Apparaten voeren een controle uit in Intune wanneer ze een melding ontvangen waarin staat dat ze dit moeten doen of wanneer het tijd is voor een geplande periodieke controle.  Wanneer u een actie op een apparaat of gebruiker richt, zoals de actie wissen, vergrendelen, wachtwoord opnieuw instellen, app implementeren, profiel implementeren (Wi-Fi, VPN, e-mail) of beleidsregels implementeren, probeert Intune het apparaat onmiddellijk te melden om in te checken bij de Intune-service.

Andere wijzigingen zoals het wijzigen van de contactgegevens in de bedrijfsportal zorgen niet voor een onmiddellijke melding aan apparaten.

### <a name="if-multiple-policies-are-deployed-to-the-same-user-or-device-how-do-i-know-which-settings-are-applied"></a>Als er meerdere beleidsregels worden geïmplementeerd voor dezelfde gebruiker of hetzelfde apparaat, hoe weet ik dan welke instellingen worden toegepast?
Wanneer er twee of meer sets beleidsregels naar dezelfde gebruiker of hetzelfde apparaat worden geïmplementeerd, vindt de beoordeling van de toegepaste instelling plaats op het niveau van de individuele instelling:

- Nalevingsbeleidsinstellingen hebben altijd voorrang op configuratiebeleidsinstellingen.

- De strengste nalevingsbeleidsinstelling is van toepassing als dit wordt vergeleken met dezelfde instelling in een ander nalevingsbeleid.

- Als een configuratiebeleidsinstelling een conflict veroorzaakt met een instelling in een ander configuratiebeleid, wordt dit conflict weergegeven in Intune. Handmatig deze conflicten oplossen.

### <a name="what-happens-when-mobile-application-management-policies-conflict-with-each-other-which-one-applies-to-the-app"></a>Wat gebeurt er wanneer MAM-beleidsregels elkaar tegenspreken? Welke is van toepassing op de app?
Conflictwaarden zijn de meest beperkende instellingen die beschikbaar zijn in MAM-beleid, uitgezonderd cijferinvoervelden (zoals aantal pincodepogingen voorafgaand aan opnieuw instellen).  De cijferinvoervelden worden op hetzelfde ingesteld als de waarden, alsof u een MAM-beleid hebt gemaakt in de console met behulp van de aanbevolen instellingenoptie.

Er treden conflicten op wanneer twee beleidsinstellingen hetzelfde zijn.  Bijvoorbeeld als u twee MAM-beleidsregels hebt geconfigureerd die identiek zijn met uitzondering van de instelling voor kopiëren en plakken.  In dit scenario wordt de instelling voor kopiëren en plakken ingesteld op de meest beperkende waarde, maar de overige instellingen worden toegepast zoals die zijn geconfigureerd.

Als er een beleid is geïmplementeerd voor de app en dat beleid is van kracht geworden, en er wordt vervolgens een tweede beleid geïmplementeerd, heeft de eerste app prioriteit en blijft van toepassing. De tweede beleidsregel blijkt ermee strijdig te zijn. Indien ze beide op hetzelfde moment worden toegepast, hetgeen wil zeggen dat er dus geen voorafgaand beleid is, zijn ze allebei strijdig. Eventueel conflicterende instellingen worden ingesteld op de meest beperkende waarden.

### <a name="what-happens-when-ios-custom-policies-conflict"></a>Wat gebeurt er als aangepaste iOS-beleidsregels conflicteren?
Intune beoordeelt de payload van Apple-configuratiebestanden of een aangepast beleid voor de Open Mobile Alliance Uniform Resource Identifier (OMA-URI) niet. Het fungeert alleen als bezorgingsmechanisme.

Controleer, wanneer u een aangepast beleid implementeert, of de geconfigureerde instellingen niet conflicteren met naleving, configuratiebeleid of ander aangepast beleid. Als er bij een aangepast beleid sprake is van conflicterende instellingen, dan wordt de instellingen in willekeurige volgorde toegepast.

### <a name="what-happens-when-a-policy-is-deleted-or-no-longer-applicable"></a>Wat gebeurt er wanneer een beleid wordt verwijderd of niet langer van toepassing is?
Wanneer u een beleid of een apparaat verwijdert uit een groep met een geïmplementeerd beleid, worden het beleid en de instellingen van het apparaat verwijderd conform de volgende lijsten.

#### <a name="enrolled-devices"></a>Ingeschreven apparaten

- Wi-Fi-, VPN-, certificaat- en e-mailprofielen: deze profielen worden verwijderd van alle ondersteunde ingeschreven apparaten.
- Alle andere beleidstypen:
  - **Windows- en Android-apparaten**: de instellingen worden niet van het apparaat verwijderd.
  - **Windows Phone 8.1-apparaten**: de volgende instellingen worden verwijderd:
    - Wachtwoord vereist voor het ontgrendelen van mobiele apparaten
    - Eenvoudige wachtwoorden toestaan
    - Minimale wachtwoordlengte
    - Vereist wachtwoordtype
    - Wachtwoordverlooptijd (dagen)
    - Wachtwoordgeschiedenis onthouden
    - Aantal mislukte aanmeldingen dat is toegestaan voordat het apparaat wordt gewist
    - Minuten inactief voordat wachtwoord is vereist
    - Vereist wachtwoordtype – minimum aantal tekensets
    - Camera toestaan
    - Versleuteling vereisen voor mobiel apparaat
    - Verwisselbare opslag toestaan
    - Webbrowser toestaan
    - Toepassingsarchief toestaan
    - Schermafbeelding toestaan
    - Geolocatie toestaan
    - Microsoft-account toestaan
    - Kopiëren en plakken toestaan
    - Wi-Fi-tethering toestaan
    - Automatische verbinding met gratis Wi-Fi-hotspots toestaan
    - Melden van Wi-Fi-hotspots toestaan
    - Wissen toestaan
    - Bluetooth toestaan
    - NFC toestaan
    - Wi-Fi toestaan

  - **iOS**: alle instellingen worden verwijderd, met uitzondering van:
    - Spraakroaming toestaan
    - Gegevensroaming toestaan
    - Automatische synchronisatie tijdens roamen toestaan

### <a name="where-can-i-find-help-troubleshooting-policies"></a>Waar vind ik meer informatie over het oplossen van beleidsproblemen?

Zie [Beleidsproblemen oplossen](troubleshoot-policies-in-microsoft-intune.md).
