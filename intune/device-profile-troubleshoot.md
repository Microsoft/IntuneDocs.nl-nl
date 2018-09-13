---
title: Problemen met apparaatprofielen oplossen in Microsoft Intune - Azure | Microsoft Docs
description: Veelvoorkomende problemen met apparaatprofielen, waaronder profielwijzigingen die niet worden toegepast op enkele gebruikers of apparaten, hoe lang het duurt voordat nieuw beleid naar apparaten wordt gepusht, welke instellingen worden toegepast wanneer er meerdere beleidsregels zijn, wat er gebeurt wanneer een profiel wordt verwijderd en meer met betrekking tot Microsoft Intune in Azure Portal
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 1/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d013ad2aefbfee5eea8f240277b0f84c2c6bf05a
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/30/2018
ms.locfileid: "43312946"
---
# <a name="common-issues-and-resolutions-with-device-profiles-in-microsoft-intune"></a>Veelvoorkomende problemen met en oplossingen voor apparaatprofielen in Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Los algemene problemen met Intune-apparaatprofielen op.

## <a name="why-doesnt-a-user-get-a-new-profile-when-changing-a-password-or-passphrase-on-an-existing-wi-fi-profile"></a>Waarom krijgt een gebruiker een nieuw profiel als een wachtwoord of wachtwoordzin wordt gewijzigd voor een bestaand Wi-Fi-profiel? 
U maakt een zakelijk Wi-Fi-profiel maakt, implementeert het profiel voor een groep, wijzigt het wachtwoord en slaat het profiel op. Wanneer het profiel wordt gewijzigd, ontvangen sommige gebruikers het nieuwe profiel mogelijk niet.

Voor het oplossen van dit probleem stelt u een Wi-Fi-profiel voor gasten in. Als het zakelijke Wi-Fi-profiel niet naar behoren werkt, kunnen gebruikers verbinding maken met het profiel voor gasten. Zorg ervoor dat u alle instellingen voor automatisch verbinden inschakelt. Implementeer het Wi-Fi-profiel voor gasten voor alle gebruikers.

Enkele extra aanbevelingen:  

- Aangezien voor het Wi-Fi-netwerk waarmee u verbinding maakt een wachtwoord of wachtwoordzin wordt gebruikt, moet u ervoor zorgen dat u direct verbinding met de Wi-Fi-router kunt maken. U kunt dit testen met een iOS-apparaat.
- Als u bent verbonden met het Wi-Fi-eindpunt (de Wi-Fi-router), noteert u de SSID en de referentie die wordt gebruikt (dit is het wachtwoord of de wachtwoordzin).
- Voer de SSID en referentie (wachtwoord of wachtwoordzin) in het veld vooraf gedeelde sleutel in. 
- Stel deze instelling in voor een testgroep met een beperkt aantal gebruikers, bij voorkeur het liefst alleen voor het IT-team. 
- Synchroniseer uw iOS-apparaat naar Intune. Registreert u als dit nog niet is gebeurd. 
- Test de verbinding met hetzelfde Wi-Fi-eindpunt opnieuw (zoals vermeld in de eerste stap).
- Implementeer deze instelling naar grotere groepen en uiteindelijk naar alle eindgebruikers in uw organisatie. 

## <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned"></a>Hoe lang duurt het voor mobiele apparaten een beleid of apps hebben ontvangen nadat deze zijn toegewezen?
Wanneer er een beleid of een app wordt toegewezen, probeert Intune het apparaat onmiddellijk te melden dat het moet inchecken bij de Intune-service. De melding wordt meestal binnen vijf minuten gedaan.

Als een apparaat geen controle uitvoert of het beleid niet kan worden opgehaald nadat de eerste melding daarover is verzonden, doet Intune nog drie pogingen. Als het apparaat offline is (bijvoorbeeld omdat het is uitgeschakeld of niet is verbonden met een netwerk), kan het geen meldingen ontvangen. In dat geval ontvangt het apparaat het beleid bij de volgende geplande controle bij de Intune-service en wel als volgt:

- iOS en macOS: om de zes uur
- Android: om de acht uur
- Windows Phone: om de acht uur
- Windows 8.1- en Windows 10-pc's die als apparaten zijn ingeschreven: om de acht uur

Als het apparaat recent is ingeschreven, is de controlefrequentie hoger, en wel als volgt:

- iOS en macOS: om de 15 minuten gedurende zes uur en daarna om de zes uur
- Android: om de drie minuten gedurende 15 minuten, daarna om de 15 minuten gedurende twee uur en vervolgens om de acht uur
- Windows Phone: om de vijf minuten gedurende 15 minuten, daarna om de 15 minuten gedurende twee uur en vervolgens om de acht uur
- Windows-computers die als apparaten zijn ingeschreven: om de drie minuten gedurende 30 minuten en vervolgens om de acht uur

Gebruikers kunnen ook de bedrijfsportal-app openen en het apparaat synchroniseren om op elk gewenst moment op aanwezig beleid te controleren.

Voor apparaten zonder gebruikersaffiniteit kan de synchronisatiefrequentie die direct volgt op de inschrijving variëren van een aantal uur tot een of meer dagen. Intune verzendt aanvragen met verschillende intervallen om een apparaat in te checken bij de service. Het is echter nog steeds aan het apparaat om in te checken. Afhankelijk van het type apparaatinschrijving en de beleidsregels en profielen die zijn toegewezen aan een apparaat, kan niet worden voorspeld hoe lang het duurt voordat het inchecken van een apparaat is voltooid na de initiële inschrijving. Echter, wanneer het apparaat is ingeschreven en alle initiële beleidsregels zijn toegepast, controleert het apparaat meestal om de zes uur op nieuwe beleidsregels.

## <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Welke acties zorgen ervoor dat Intune onmiddellijk een melding naar een apparaat verzendt?
Apparaten checken in bij Intune wanneer ze een melding ontvangen waarin staat dat ze dit moeten doen of wanneer het tijd is voor een geplande periodieke check-in. Wanneer u een actie op een apparaat of gebruiker richt, zoals wissen, vergrendelen, wachtwoord opnieuw instellen, app toewijzen, profiel toewijzen of beleidsregels toewijzen, meldt Intune het onmiddellijk aan het apparaat dat het moet inchecken bij de Intune-service om deze updates te ontvangen.

Andere wijzigingen zoals het wijzigen van de contactgegevens in de bedrijfsportal zorgen niet voor een onmiddellijke melding aan apparaten.

## <a name="if-multiple-policies-are-assigned-to-the-same-user-or-device-how-do-i-know-which-settings-gets-applied"></a>Als er meerdere beleidsregels worden toegewezen aan dezelfde gebruiker of hetzelfde apparaat, hoe weet ik dan welke instellingen worden toegepast?
Wanneer er twee of meer beleidsregels worden toegewezen aan dezelfde gebruiker of hetzelfde apparaat, wordt per instelling bekeken welke instelling van toepassing is:

-   Nalevingsbeleidsinstellingen hebben altijd voorrang op configuratiebeleidsinstellingen

-   Als een nalevingsbeleidsregel wordt vergeleken met diezelfde instelling in een ander nalevingsbeleid, wordt de strengste nalevingsbeleidsinstelling wordt toegepast.

-   Als een configuratiebeleidsinstelling een conflict veroorzaakt met een instelling in een ander configuratiebeleid, wordt dit conflict weergegeven in Azure Portal. In dit scenario moeten deze conflicten handmatig worden opgelost.

## <a name="what-happens-when-app-protection-policies-conflict-with-each-other-which-one-is-applied-to-the-app"></a>Wat gebeurt er wanneer beleidsregels voor app-beveiliging met elkaar conflicteren? Welke regel wordt toegepast op de app?
Conflictwaarden zijn de meest beperkende instellingen die beschikbaar zijn in app-beveiligingsbeleid, behalve cijferinvoervelden (zoals aantal pincodepogingen voorafgaand aan opnieuw instellen). De cijferinvoervelden worden op hetzelfde ingesteld als de waarden, alsof u een MAM-beleid hebt gemaakt in de console met behulp van de aanbevolen instellingenoptie.

Er treden conflicten op wanneer twee profielinstellingen hetzelfde zijn. Bijvoorbeeld als u twee MAM-beleidsregels hebt geconfigureerd die identiek zijn met uitzondering van de instelling voor kopiëren en plakken. In dit scenario wordt de instelling voor kopiëren en plakken ingesteld op de meest beperkende waarde, maar de overige instellingen worden toegepast zoals die zijn geconfigureerd.

Als er een profiel is toegewezen aan de app en van kracht is, en er wordt vervolgens een tweede profiel toegewezen, heeft het eerste profiel prioriteit en blijft dit toegepast, terwijl het tweede als conflicterend wordt beschouwd. Indien beide op hetzelfde moment worden toegepast, wanneer er dus geen voorafgaand profiel is, worden ze allebei als conflicterend beschouwd. Eventueel conflicterende instellingen worden ingesteld op de meest beperkende waarden.

## <a name="what-happens-when-ios-custom-policies-conflict"></a>Wat gebeurt er als aangepaste iOS-beleidsregels conflicteren?
Intune beoordeelt de payload van Apple-configuratiebestanden of een aangepast profiel voor de Open Mobile Alliance Uniform Resource Identifier (OMA-URI) niet. Het fungeert alleen als bezorgingsmechanisme.

Bij het toewijzen van een aangepast profiel zorgt u dat de geconfigureerde instellingen niet conflicteren met het nalevingsbeleid, configuratiebeleid of ander aangepast beleid. Als een aangepast profiel en de instellingen niet goed op elkaar aansluiten, worden de instellingen willekeurig toegepast.

## <a name="what-happens-when-a-profile-is-deleted-or-no-longer-applicable"></a>Wat gebeurt er wanneer een profiel wordt verwijderd of niet langer van toepassing is?
Wanneer u een profiel verwijdert of een apparaat verwijdert uit een groep waaraan een profiel was toegewezen, worden het profiel en de instellingen van het apparaat verwijderd volgens de volgende lijsten:

- Wi-Fi-, VPN-, certificaat- en e-mailprofielen: deze profielen worden verwijderd van alle ondersteunde ingeschreven apparaten.
- Alle andere profieltypen:  
    - **Windows- en Android-apparaten**: de instellingen worden niet van het apparaat verwijderd
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

## <a name="i-changed-a-device-restriction-profile-but-the-changes-havent-taken-effect"></a>Ik heb een beperkingsprofiel voor apparaten gewijzigd, maar de wijzigingen zijn niet doorgevoerd
Bij Windows Phone-apparaten wordt niet toegestaan dat de beveiligingsbeleidsregels die via MDM of EAS zijn ingesteld, worden teruggebracht naar een lager niveau wanneer u die eenmaal hebt ingesteld. U stelt bijvoorbeeld het **minimumaantal tekens voor het wachtwoord** in op 8 en wilt dit vervolgens terugbrengen tot 4. Het meer beperkende profiel is al toegepast op het apparaat.

Afhankelijk van het apparaatplatform moet u het beveiligingsbeleid opnieuw instellen als u de beveiliging van het profiel naar beneden wilt bijstellen. Veeg bijvoorbeeld in Windows op het bureaublad vanaf rechts over het scherm om **Instellingen** > **Configuratiescherm** te selecteren. Selecteer de applet **Gebruikersaccounts** .

In het navigatiemenu aan de linkerkant vindt u onderaan de koppeling **Beveiligingsbeleid opnieuw instellen**. Selecteer deze koppeling en kies vervolgens **Beleid opnieuw instellen**. Andere MDM-apparaten, bijvoorbeeld met Android, Windows Phone 8.1 en hoger of iOS, moeten mogelijk buiten gebruik worden gesteld en weer opnieuw bij de service worden ingeschreven voordat u een minder beperkend profiel kunt toepassen.

## <a name="next-steps"></a>Volgende stappen
Extra hulp nodig? Zie [Ondersteuning voor Microsoft Intune krijgen](get-support.md).