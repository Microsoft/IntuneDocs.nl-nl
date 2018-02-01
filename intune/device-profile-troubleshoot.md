---
title: Problemen met apparaatprofielen in Microsoft Intune oplossen
titlesuffix: Azure portal
description: Als u er niet uitkomt, raadpleegt u dit onderwerp om problemen met Intune-apparaatprofielen op te lossen.
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 1/17/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6424be562401c672966c0f7f3fbe145c19182299
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="troubleshooting-device-profiles-in-microsoft-intune"></a>Problemen met apparaatprofielen in Microsoft Intune oplossen


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

De informatie in dit onderwerp kan worden gebruikt bij het oplossen van algemene problemen rond Intune-apparaatprofielen.

## <a name="why-doesnt-a-user-get-a-new-profile-when-changing-a-password-or-passphrase-on-an-existing-wi-fi-profile"></a>Waarom krijgt een gebruiker een nieuw profiel als een wachtwoord of wachtwoordzin wordt gewijzigd voor een bestaand Wi-Fi-profiel? 
Wanneer u een zakelijk Wi-Fi-profiel maakt, het profiel voor een groep implementeert, het wachtwoord wijzigt en het profiel vervolgens opslaat, zou u verwachten dat de gebruiker het nieuwe profiel krijgt. Dit is echter niet altijd het geval. 

U kunt dit probleem beperken door ervoor te zorgen dat u een Wi-Fi voor gasten hebt ingesteld, zodat de gebruiker dit Wi-Fi kan gebruiken als hij geen toegang heeft tot het zakelijke Wi-Fi. De instelling voor automatische verbinding moet worden ingeschakeld. Het Wi-Fi-profiel voor gasten moet voor alle gebruikers worden geïmplementeerd.

Er zijn enkele aanvullende aanbevolen procedures die u kunt uitvoeren:
- Aangezien het Wi-Fi-netwerk waarmee u verbinding maakt een wachtwoord of wachtwoordzin gebruikt, moet u ervoor zorgen dat u direct verbinding met de Wi-Fi-router kunt maken. U kunt dit testen met een iOS-apparaat.
- Als u bent verbonden met het Wi-Fi-eindpunt (de Wi-Fi-router), noteert u de SSID en de referentie die wordt gebruikt (dit is het wachtwoord of de wachtwoordzin).
- Voer de SSID en referentie (wachtwoord of wachtwoordzin) in het veld vooraf gedeelde sleutel in. 
- Stel deze instelling in voor een testgroep met een beperkt aantal gebruikers, bij voorkeur het liefst alleen voor het IT-team. 
- Synchroniseer uw iOS-apparaat naar Intune. Registreert u als dit nog niet is gebeurd. 
- Test de verbinding met hetzelfde Wi-Fi-eindpunt opnieuw (zoals vermeld in de eerste stap).
- Implementeer deze instelling naar grotere groepen en uiteindelijk naar alle eindgebruikers in uw organisatie. 

## <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned"></a>Hoe lang duurt het voor mobiele apparaten een beleid of apps hebben ontvangen nadat deze zijn toegewezen?
Wanneer er een beleid of een app wordt toegewezen, probeert Intune het apparaat onmiddellijk te melden dat het moet inchecken bij de Intune-service. Dit vindt meestal binnen vijf minuten plaats.

Als een apparaat geen controle uitvoert of het beleid niet kan worden opgehaald nadat de eerste melding daarover is verzonden, doet Intune nog drie pogingen. Als het apparaat offline is (bijvoorbeeld omdat het is uitgeschakeld of niet is verbonden met een netwerk), kan het geen meldingen ontvangen. In dat geval ontvangt het apparaat het beleid bij de volgende geplande controle bij de Intune-service en wel als volgt:

- iOS en macOS: om de zes uur.
- Android: om de acht uur.
- Windows Phone: om de acht uur.
- Windows 8.1- en Windows 10-pc's die als apparaten zijn ingeschreven: om de acht uur.

Als het apparaat zojuist is ingeschreven, is de controlefrequentie hoger, en wel als volgt:

- iOS en macOS: om de 15 minuten gedurende zes uur en daarna om de zes uur.
- Android: om de drie minuten gedurende 15 minuten, daarna om de 15 minuten gedurende twee uur en vervolgens om de acht uur.
- Windows Phone: om de vijf minuten gedurende 15 minuten, daarna om de 15 minuten gedurende twee uur en vervolgens om de acht uur.
- Windows-computers die als apparaten zijn ingeschreven: om de drie minuten gedurende 30 minuten en vervolgens om de acht uur.

Gebruikers kunnen ook de bedrijfsportal-app openen en het apparaat onmiddellijk synchroniseren om op elk gewenst moment op aanwezig beleid te controleren.

Voor apparaten zonder gebruikersaffiniteit kan de synchronisatiefrequentie die direct volgt op de inschrijving variëren van een aantal uur tot een of meer dagen. Intune verzendt aanvragen met verschillende intervallen om een apparaat in te checken bij de service. Het hangt er nog altijd van af of het apparaat daadwerkelijk wordt ingecheckt. Afhankelijk van het type apparaatinschrijving en de beleidsregels en profielen die zijn toegewezen aan een apparaat, kan niet worden voorspeld hoe lang het duurt voordat het inchecken van een apparaat is voltooid na de initiële inschrijving. Echter, wanneer het apparaat is ingeschreven en alle initiële beleidsregels zijn toegepast, moet het apparaat om de zes uur controleren op nieuwe beleidsregels.

## <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Welke acties zorgen ervoor dat Intune onmiddellijk een melding naar een apparaat verzendt?
Apparaten voeren een controle uit in Intune wanneer ze een melding ontvangen waarin staat dat ze dit moeten doen of wanneer het tijd is voor een geplande periodieke controle. Wanneer u een actie specifiek op een apparaat of gebruiker richt, zoals wissen, vergrendelen, wachtwoord opnieuw instellen, app toewijzen, profiel toewijzen (Wi-Fi, VPN, e-mail enzovoort) of beleidsregels toewijzen, probeert Intune het apparaat onmiddellijk te melden dat het moet inchecken bij de Intune-service om deze updates te ontvangen.

Andere wijzigingen zoals het wijzigen van de contactgegevens in de bedrijfsportal zorgen niet voor een onmiddellijke melding aan apparaten.

## <a name="if-multiple-policies-are-assigned-to-the-same-user-or-device-how-do-i-know-which-settings-gets-applied"></a>Als er meerdere beleidsregels worden toegewezen aan dezelfde gebruiker of hetzelfde apparaat, hoe weet ik dan welke instellingen worden toegepast?
Wanneer er twee of meer beleidsregels worden toegewezen aan dezelfde gebruiker of hetzelfde apparaat, vindt de beoordeling van welke instelling moet worden toegepast plaats op het niveau van de individuele instelling:

-   Nalevingsbeleidsinstellingen hebben altijd voorrang op configuratiebeleidsinstellingen.

-   De strengste nalevingsbeleidsinstelling wordt toegepast als dit beleid wordt vergeleken met dezelfde instelling in een ander nalevingsbeleid.

-   Als een configuratiebeleidsinstelling een conflict veroorzaakt met een instelling in een ander configuratiebeleid, wordt dit conflict weergegeven in Azure Portal. U moet dergelijke conflicten handmatig oplossen.

## <a name="what-happens-when-app-protection-policies-conflict-with-each-other-which-one-is-applied-to-the-app"></a>Wat gebeurt er wanneer beleidsregels voor app-beveiliging met elkaar conflicteren? Welke regel wordt toegepast op de app?
Conflictwaarden zijn de meest beperkende instellingen die beschikbaar zijn in app-beveiligingsbeleid, behalve cijferinvoervelden (zoals aantal pincodepogingen voorafgaand aan opnieuw instellen). De cijferinvoervelden worden op hetzelfde ingesteld als de waarden, alsof u een MAM-beleid hebt gemaakt in de console met behulp van de aanbevolen instellingenoptie.

Er treden conflicten op wanneer twee profielinstellingen hetzelfde zijn. Bijvoorbeeld als u twee MAM-beleidsregels hebt geconfigureerd die identiek zijn met uitzondering van de instelling voor kopiëren en plakken. In dit scenario wordt de instelling voor kopiëren en plakken ingesteld op de meest beperkende waarde, maar de overige instellingen worden toegepast zoals die zijn geconfigureerd.

Als er een profiel is toegewezen aan de app en van kracht is, en er wordt vervolgens een tweede profiel toegewezen, heeft het eerste profiel prioriteit en blijft dit toegepast, terwijl het tweede als conflicterend wordt beschouwd. Indien beide op hetzelfde moment worden toegepast, wanneer er dus geen voorafgaand profiel is, worden ze allebei als conflicterend beschouwd. Eventueel conflicterende instellingen worden ingesteld op de meest beperkende waarden.

## <a name="what-happens-when-ios-custom-policies-conflict"></a>Wat gebeurt er als aangepaste iOS-beleidsregels conflicteren?
Intune beoordeelt de payload van Apple-configuratiebestanden of een aangepast profiel voor de Open Mobile Alliance Uniform Resource Identifier (OMA-URI) niet. Het fungeert alleen als bezorgingsmechanisme.

Bij het toewijzen van een aangepast profiel zorgt u dat de geconfigureerde instellingen niet conflicteren met het nalevingsbeleid, configuratiebeleid of ander aangepast beleid. Als er bij een aangepast profiel sprake is van conflicterende instellingen, worden instellingen in willekeurige volgorde toegepast.

## <a name="what-happens-when-a-profile-is-deleted-or-no-longer-applicable"></a>Wat gebeurt er wanneer een profiel wordt verwijderd of niet langer van toepassing is?
Wanneer u een profiel verwijdert of een apparaat verwijdert uit een groep waaraan een profiel was toegewezen, worden het profiel en de instellingen van het apparaat verwijderd volgens de volgende lijsten.

### <a name="enrolled-devices"></a>Ingeschreven apparaten

- Wi-Fi-, VPN-, certificaat- en e-mailprofielen: deze profielen worden verwijderd van alle ondersteunde ingeschreven apparaten.
- Alle andere profieltypen:
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
        - Terugzetten op fabrieksinstellingen toestaan
        - Bluetooth toestaan
        - NFC toestaan
        - Wi-Fi toestaan

    - **iOS**: alle instellingen worden verwijderd, met uitzondering van:
        - Spraakroaming toestaan
        - Gegevensroaming toestaan
        - Automatische synchronisatie tijdens roamen toestaan

## <a name="i-changed-a-device-restriction-profile-but-the-changes-havent-taken-effect"></a>Ik heb een beperkingsprofiel voor apparaten gewijzigd, maar de wijzigingen zijn niet doorgevoerd
Bij Windows Phone-apparaten wordt niet toegestaan dat de beveiligingsbeleidsregels die via MDM of EAS zijn ingesteld, worden teruggebracht naar een lager niveau wanneer u die eenmaal hebt ingesteld. U stelt bijvoorbeeld een **minimumaantal tekens voor het wachtwoord** in op 8 en wilt dit vervolgens terugbrengen tot 4. Het meer beperkende profiel is al toegepast op het apparaat.

Afhankelijk van het apparaatplatform moet u mogelijk het beveiligingsbeleid opnieuw instellen als u de beveiliging van het profiel naar beneden wilt bijstellen.
Veeg bijvoorbeeld in Windows op het bureaublad vanaf rechts over het scherm om de balk **Charms** te openen en kies **Instellingen** &gt; **Configuratiescherm**. Selecteer de applet **Gebruikersaccounts** .
In het navigatiemenu aan de linkerkant vindt u onderaan een koppeling **Beveiligingsbeleid opnieuw instellen**. Kies deze koppeling en kies vervolgens **Beleid opnieuw instellen**.
Andere MDM-apparaten, zoals Android, Windows Phone 8.1 en hoger of iOS moeten mogelijk buiten gebruik worden gesteld en weer opnieuw bij de service worden geregistreerd voordat u een minder beperkend profiel kunt toepassen.


### <a name="next-steps"></a>Volgende stappen
Als deze informatie over probleemoplossing u niet heeft geholpen, kunt u contact opnemen met Microsoft Ondersteuning zoals is beschreven in [Ondersteuning voor Microsoft Intune krijgen](get-support.md).