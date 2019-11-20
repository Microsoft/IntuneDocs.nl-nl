---
title: Problemen met apparaatprofielen oplossen in Microsoft Intune - Azure | Microsoft Docs
description: Algemene vragen en antwoorden voor apparaatbeleid en -profielen, waaronder profielwijzigingen die niet worden toegepast op gebruikers of apparaten, hoe lang het duurt voordat nieuw beleid naar apparaten wordt gepusht, welke instellingen worden toegepast wanneer er meerdere beleidsregels zijn, wat er gebeurt wanneer een profiel wordt verwijderd en meer met betrekking tot Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/15/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4a1177a37ddbfa7f760339c4ad0cd7773d670540
ms.sourcegitcommit: 01fb3d844958a0e66c7b87623160982868e675b0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2019
ms.locfileid: "74199196"
---
# <a name="common-questions-issues-and-resolutions-with-device-policies-and-profiles-in-microsoft-intune"></a>Algemene vragen, problemen en oplossingen met apparaatbeleid en -profielen in Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Antwoorden op algemene vragen wanneer u werkt met apparaatprofielen en -beleid in Intune. In dit artikel worden ook de inchecktijdsintervallen vermeld, worden meer gegevens over problemen gegeven en meer.

## <a name="why-doesnt-a-user-get-a-new-profile-when-changing-a-password-or-passphrase-on-an-existing-wi-fi-profile"></a>Waarom krijgt een gebruiker een nieuw profiel als een wachtwoord of wachtwoordzin wordt gewijzigd voor een bestaand Wi-Fi-profiel?

U maakt een zakelijk Wi-Fi-profiel maakt, implementeert het profiel voor een groep, wijzigt het wachtwoord en slaat het profiel op. Wanneer het profiel wordt gewijzigd, ontvangen sommige gebruikers het nieuwe profiel mogelijk niet.

Voor het oplossen van dit probleem stelt u een Wi-Fi-profiel voor gasten in. Als het zakelijke Wi-Fi-profiel niet naar behoren werkt, kunnen gebruikers verbinding maken met het profiel voor gasten. Zorg ervoor dat u alle instellingen voor automatisch verbinden inschakelt. Implementeer het Wi-Fi-profiel voor gasten voor alle gebruikers.

Enkele extra aanbevelingen:  

- Als voor het wifi-netwerk waarmee u verbinding maakt een wachtwoord of wachtwoordzin wordt gebruikt, moet u ervoor zorgen dat u direct verbinding met de wifi-router kunt maken. U kunt dit testen met een iOS-apparaat.
- Als u bent verbonden met het Wi-Fi-eindpunt (de Wi-Fi-router), noteert u de SSID en de referentie die wordt gebruikt (dit is het wachtwoord of de wachtwoordzin).
- Voer de SSID en referentie (wachtwoord of wachtwoordzin) in het veld vooraf gedeelde sleutel in. 
- Stel deze instelling in voor een testgroep met een beperkt aantal gebruikers, bij voorkeur het liefst alleen voor het IT-team. 
- Synchroniseer uw iOS-apparaat naar Intune. Registreert u als dit nog niet is gebeurd. 
- Test de verbinding met hetzelfde Wi-Fi-eindpunt opnieuw (zoals vermeld in de eerste stap).
- Implementeer deze instelling naar grotere groepen en uiteindelijk naar alle eindgebruikers in uw organisatie. 

## <a name="how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned"></a>Hoe lang duurt het voor apparaten een beleid, profiel of app hebben ontvangen nadat deze zijn toegewezen?

Intune meldt dat het apparaat moet worden ingecheckt met de Intune-service. De meldingstijd kan variëren, van onmiddellijk tot enkele uren. De meldingstijd verschilt ook per platform.

Als een apparaat niet incheckt om het beleid of het profiel op te halen na de eerste melding, doet Intune nog drie pogingen. Een apparaat dat offline is, dat bijvoorbeeld is uitgeschakeld of niet is verbonden met een netwerk, ontvangt mogelijk geen meldingen. In dat geval krijgt het apparaat het beleid of het profiel bij de volgende geplande check-in bij de Intune-service, naar **schatting**:

| Platform | Cyclus vernieuwen|
| --- | --- |
| iOS | Ongeveer om de 8 uur |
| macOS | Ongeveer om de 8 uur |
| Android | Ongeveer om de 8 uur |
| Pc’s met Windows 10 die als apparaten zijn geregistreerd | Ongeveer om de 8 uur |
| Windows Phone | Ongeveer om de 8 uur |
| Windows 8.1 | Ongeveer om de 8 uur |

Als het apparaat onlangs is ingeschreven, wordt het inchecken voor naleving en configuratie vaker uitgevoerd, naar **schatting**:

| Platform | Frequentie |
| --- | --- |
| iOS | Om de 15 minuten gedurende 1 uur en daarna ongeveer om de 8 uur |  
| macOS | Om de 15 minuten gedurende 1 uur en daarna ongeveer om de 8 uur | 
| Android | Om de 3 minuten gedurende 15 minuten en daarna om de 15 minuten gedurende 2 uur en vervolgens ongeveer om de 8 uur | 
| Pc’s met Windows 10 die als apparaten zijn geregistreerd | Om de 3 minuten gedurende 15 minuten en daarna om de 15 minuten gedurende 2 uur en vervolgens ongeveer om de 8 uur | 
| Windows Phone | Om de 5 minuten gedurende 15 minuten en daarna om de 15 minuten gedurende 2 uur en vervolgens ongeveer om de 8 uur | 
| Windows 8.1 | Om de 5 minuten gedurende 15 minuten en daarna om de 15 minuten gedurende 2 uur en vervolgens ongeveer om de 8 uur | 

Gebruikers kunnen ook op elk gewenst moment de Bedrijfsportal-app openen en naar **Instellingen** > **Synchroniseren** gaan, om onmiddellijk te controleren op beleids- of profielupdates.

## <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Welke acties zorgen ervoor dat Intune onmiddellijk een melding naar een apparaat verzendt?

Er zijn verschillende acties waarmee een melding wordt geactiveerd, bijvoorbeeld wanneer een beleid, profiel of app wordt toegewezen (of de toewijzing ervan ongedaan wordt gemaakt), bijgewerkt, verwijderd, enzovoort. De tijden van deze acties kunnen per platform verschillen.

Apparaten checken in bij Intune wanneer ze een melding ontvangen waarin staat dat ze dit moeten doen of wanneer het tijd is voor een geplande check-in. Wanneer u een actie op een apparaat of gebruiker richt, zoals vergrendelen, wachtwoord opnieuw instellen of app toewijzen, profiel toewijzen of beleid toewijzen, meldt Intune het onmiddellijk aan het apparaat dat het moet inchecken om deze updates te ontvangen.

Andere wijzigingen, zoals het wijzigen van de contactgegevens in de bedrijfsportal-app, zorgen niet voor een onmiddellijke melding aan apparaten.

## <a name="if-multiple-policies-are-assigned-to-the-same-user-or-device-how-do-i-know-which-settings-gets-applied"></a>Als er meerdere beleidsregels worden toegewezen aan dezelfde gebruiker of hetzelfde apparaat, hoe weet ik dan welke instellingen worden toegepast?

Wanneer er twee of meer beleidsregels worden toegewezen aan dezelfde gebruiker of hetzelfde apparaat, vindt de instelling die wordt toegepast plaats op afzonderlijk instellingsniveau:

- Nalevingsbeleidsinstellingen hebben altijd voorrang op configuratieprofielinstellingen.

- Als een nalevingsbeleidsregel diezelfde instelling vergelijkt in een ander nalevingsbeleid, wordt de strengste nalevingsbeleidsinstelling toegepast.

- Als een configuratiebeleidsinstelling een conflict veroorzaakt met een instelling in een ander configuratiebeleid, wordt dit conflict weergegeven in Intune. Handmatig deze conflicten oplossen.

## <a name="what-happens-when-app-protection-policies-conflict-with-each-other-which-one-is-applied-to-the-app"></a>Wat gebeurt er wanneer beleidsregels voor app-beveiliging met elkaar conflicteren? Welke regel wordt toegepast op de app?

Conflictwaarden zijn de meest beperkende instellingen die beschikbaar zijn in app-beveiligingsbeleid, *behalve* cijferinvoervelden, zoals het aantal pincodepogingen voordat de pincode opnieuw wordt ingesteld. De cijferinvoervelden worden hetzelfde ingesteld als de waarden, alsof u een MAM-beleid hebt gemaakt met behulp van de aanbevolen instellingenoptie.

Er treden conflicten op wanneer twee profielinstellingen dezelfde zijn. Bijvoorbeeld als u twee MAM-beleidsregels hebt geconfigureerd die identiek zijn met uitzondering van de instelling voor kopiëren en plakken. In dit scenario wordt de instelling voor kopiëren en plakken ingesteld op de meest beperkende waarde, maar de overige instellingen worden toegepast zoals die zijn geconfigureerd.

Een beleid wordt in de app geïmplementeerd en gaat van kracht. Er wordt een tweede beleid geïmplementeerd. In dit scenario heeft het eerste beleid voorrang en blijft het toegepast. Het tweede beleid geeft een conflict aan. Als beide tegelijkertijd worden toegepast, dus als er geen beleid met prioriteit is, dan zijn beide conflicterend. Eventueel conflicterende instellingen worden ingesteld op de meest beperkende waarden.

## <a name="what-happens-when-ios-custom-policies-conflict"></a>Wat gebeurt er als aangepaste iOS-beleidsregels conflicteren?

Intune beoordeelt de payload van Apple-configuratiebestanden of een aangepast beleid voor de Open Mobile Alliance Uniform Resource Identifier (OMA-URI) niet. Het fungeert alleen als bezorgingsmechanisme.

Controleer, wanneer u een aangepast beleid toewijst, of de geconfigureerde instellingen niet conflicteren met naleving, configuratiebeleid of ander aangepast beleid. Als een aangepast beleid en de bijbehorende instellingen conflicteren, worden de instellingen willekeurig toegepast.

## <a name="what-happens-when-a-profile-is-deleted-or-no-longer-applicable"></a>Wat gebeurt er wanneer een profiel wordt verwijderd of niet langer van toepassing is?

Wanneer u een profiel verwijdert of een apparaat verwijdert uit een groep waaraan een profiel was toegewezen, worden het profiel en de instellingen van het apparaat verwijderd zoals hier wordt beschreven:

- Wi-Fi-, VPN-, certificaat- en e-mailprofielen: deze profielen worden verwijderd van alle ondersteunde ingeschreven apparaten.
- Alle andere profieltypen:  

  - **Windows- en Android-apparaten**: Instellingen worden niet verwijderd van het apparaat
  - **Windows Phone 8.1-apparaten**: De volgende instellingen worden verwijderd:  
  
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

## <a name="i-changed-a-device-restriction-profile-but-the-changes-havent-taken-effect"></a>Ik heb een beperkingsprofiel voor apparaten gewijzigd, maar de wijzigingen zijn niet doorgevoerd

Bij Windows Phone-apparaten wordt niet toegestaan dat de beveiligingsbeleidsregels die via MDM of EAS zijn ingesteld, worden teruggebracht naar een lager niveau wanneer u die eenmaal hebt ingesteld. U stelt bijvoorbeeld het **minimumaantal tekens voor het wachtwoord** in op 8. U probeert het terug te brengen naar 4. Het meer beperkende profiel is al toegepast op het apparaat.

U moet het beveiligingsbeleid opnieuw instellen om de beveiliging van het profiel naar beneden bij te stellen. Veeg bijvoorbeeld in Windows 8.1 op het bureaublad vanaf rechts over het scherm > selecteer **Instellingen** > **Configuratiescherm**. Selecteer de applet **Gebruikersaccounts** . In het navigatiemenu aan de linkerkant vindt u onderaan de koppeling **Beveiligingsbeleid opnieuw instellen**. Selecteer deze koppeling en kies vervolgens **Beleid opnieuw instellen**.

Andere MDM-apparaten, bijvoorbeeld met Android, Windows Phone 8.1 en hoger, iOS of Windows 10, moeten mogelijk buiten gebruik worden gesteld en weer opnieuw bij Intune worden ingeschreven voordat u een minder beperkend profiel kunt toepassen.

## <a name="some-settings-in-a-windows-10-profile-return-not-applicable"></a>Sommige instellingen in een Windows 10-profiel retourneren de waarde Niet van toepassing

Voor sommige Windows 10-apparaten wordt Niet van toepassing weergegeven. In dat geval wordt die specifieke instelling niet ondersteund door de Windows-versie of -editie die wordt uitgevoerd op het apparaat. Dit bericht kan optreden om de volgende redenen:

- De instelling is alleen beschikbaar voor nieuwere versies van Windows en niet voor het huidige versie van het besturingssysteem (OS) op het apparaat.
- De instelling is alleen beschikbaar voor de specifieke Windows-edities of specifieke SKU's, zoals Home, Professional, Enterprise en Education.

Zie [Configuration Service Provider (CSP) reference](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference) (CSP-referentie (Configuration Service Provider)) voor meer informatie over de versie- en SKU-vereisten voor de verschillende instellingen.

## <a name="next-steps"></a>Volgende stappen

Extra hulp nodig? Zie [Ondersteuning voor Microsoft Intune krijgen](../fundamentals/get-support.md).
