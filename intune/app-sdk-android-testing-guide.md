---
title: Testhandleiding voor ontwikkelaars voor Microsoft Intune App SDK voor Android
description: Met de testhandleiding voor de Intune App-SDK voor Android kunt u uw door Intune beheerde Android-app testen.
keywords: SDK
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/09/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 4ef8f421-9610-4d34-a464-cc02eb1578a9
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 91b7fc7414c3a6d6517cd4b704cb5e99ddcf96d0
ms.sourcegitcommit: 1494ff4b33c13a87f20e0f3315da79a3567db96e
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 09/20/2019
ms.locfileid: "71167182"
---
# <a name="microsoft-intune-app-sdk-for-android-developers-testing-guide"></a>Testhandleiding voor ontwikkelaars voor Microsoft Intune App SDK voor Android

De testhandleiding voor de Intune App-SDK voor Android is ontworpen om uw door Intune beheerde Android-app testen.  

## <a name="prerequisite-test-accounts"></a>Vereiste testaccounts
Er kunnen nieuwe accounts worden gemaakt met en zonder vooraf gegenereerde gegevens. Een nieuw account maken:
1. Navigeer naar de site [Microsoft Demos](https://demos.microsoft.com/environments/create/tenant). 
2. [Stel Intune in](setup-steps.md) om Mobile Device Management (MDM) in te schakelen.
3. [Gebruikers maken](users-add.md).
4. [Groepen maken](groups-add.md).
5. [Licenties toewijzen](licenses-assign.md) die geschikt zijn voor het testen.


## <a name="azure-portal-policy-configuration"></a>Beleidsconfiguratie Azure Portal
[Maak beveiligingsbeleid voor apps en wijs dit toe](app-protection-policies.md) in de [Intune-blade van Azure Portal](https://portal.azure.com/?feature.customportal=false#blade/Microsoft_Intune_Apps/MainMenu/14/selectedMenuItem/Overview). Uw [app-configuratiebeleid](app-configuration-policies-overview.md) kan ook worden gemaakt en toegewezen in de Intune-blade.

> [!NOTE]
> Als uw app niet wordt vermeld in Azure Portal, kunt u deze toch doelwit maken van een beleid door het selecteren van de optie **Meer apps** en het opgeven van de naam van het pakket in het tekstvak.

> [!IMPORTANT]
> Als u een app-configuratiebeleid wilt toepassen, moet de gebruiker die zich inschrijft aan een [Intune-beveiligingsbeleid](app-protection-policy.md) zijn onderworpen.

## <a name="test-cases"></a>Testcases

De volgende testcases bieden configuratie- en bevestigingsstappen. Gebruik deze richtlijnen bij het oplossen van problemen door Intune beheerde Android-apps.

### <a name="required-pin-and-corporate-credentials"></a>Vereiste pincode en zakelijke referenties

U kunt een pincode vereisen voor toegang tot bedrijfsresources. U kunt ook een zakelijke verificatie afdwingen voordat gebruikers de beheerde apps kunnen gebruiken. Gebruik de volgende stappen uit om deze vereisten in te stellen:

1. Stel **Pincode vereisen voor toegang** en **Zakelijke referenties vereisen voor toegang** in op **Ja**. Zie [Instellingen beveiligingsbeleid voor Android-apps in Microsoft Intune](app-protection-policy-settings-android.md#access-requirements) voor meer informatie.
2. Bevestig de volgende voorwaarden:
    - Bij het starten van de app dient een prompt voor invoer/instellen van de pincode en/of de productiegebruiker die is gebruikt tijdens de inschrijving bij de bedrijfsportal te worden weergegeven.
    - Wanneer er geen geldige aanmeldingsprompt wordt weergegeven, kan dit zijn veroorzaakt door een onjuist geconfigureerd Android-manifest, in het bijzonder de waarden voor de integratie van ADAL (SkipBroker, ClientID en Authority).
    - Wanneer er geen prompt wordt weergegeven, wordt dit mogelijk veroorzaakt door een onjuist geïntegreerde `MAMActivity`-waarde. Zie de [ontwikkelaarshandleiding voor de Microsoft Intune App-SDK voor Android](app-sdk-android.md) voor meer informatie over `MAMActivity`.

> [!NOTE] 
> Als de bovenstaande test niet werkt, mislukken de onderstaande tests waarschijnlijk ook. Controleer de integratie van de [SDK](app-sdk-android.md##sdk-integration) en [ADAL](app-sdk-android.md#configure-azure-active-directory-authentication-library-adal).

### <a name="restrict-transferring-and-receiving-data-with-other-apps"></a>Overdracht en ontvangst van gegevens ten aanzien van andere apps beperken
U kunt de overdracht van gegevens tussen door het bedrijf beheerde toepassingen als volgt regelen:

1. Stel **Apps toestaan om gegevens over te dragen aan andere apps** in op **Door beleid beheerde apps**.
2. Stel **App mag gegevens ontvangen van andere apps** in op **Alle apps**. Het gebruik van intents en inhoudsproviders zullen worden beïnvloed door dit beleid.
3. Bevestig de volgende voorwaarden:
    - Het in uw app openen van gegevens uit een niet-beheerde app werkt correct.
    - Het delen van inhoud tussen beheerde apps is toegestaan.
    - Delen van beheerde apps op niet-beheerde apps (bijvoorbeeld Chrome) is geblokkeerd.

### <a name="restrict-cut-copy-and-paste"></a>Knippen, kopiëren en plakken beperken
U kunt het systeemklembord als volgt beperken tot beheerde toepassingen:

1. Stel **Knippen, kopiëren en plakken met andere apps beperken** in op **Door beleid beheerde apps met Plakken in**.
2. Bevestig de volgende voorwaarden:
    - Tekst kopiëren uit uw app naar beheerde en niet-beheerde apps (bijvoorbeeld Berichten) is geblokkeerd.

### <a name="prevent-save-as"></a>**Opslaan als** voorkomen
U kunt de functionaliteit **Opslaan als** als volgt regelen:

1. Als voor uw app [geïntegreerde Opslaan als-besturingselementen](app-sdk-android.md#example-determine-if-saving-to-device-or-cloud-storage-is-permitted) vereist zijn, stelt u **Opslaan als voorkomen** in op **Ja**.
2. Bevestig de volgende voorwaarden:
    - Opslaan is beperkt tot alleen geschikte, beheerde locaties.

### <a name="file-encryption"></a>Bestandsversleuteling
U kunt gegevens op het apparaat als volgt versleutelen:

1. Stel **App-gegevens versleutelen** in op **Ja**.
2. Bevestig de volgende voorwaarden:
    - Normaal toepassingsgedrag wordt niet beïnvloed.

### <a name="prevent-android-backups"></a>Back-ups van Android voorkomen
U kunt als volgt back-ups van apps regelen:

1. Als u [Geïntegreerde back-upbeperkingen](app-sdk-android.md#protecting-backup-data) hebt ingesteld, stelt u **Back-ups van Android voorkomen** in op **Ja**.
2. Bevestig de volgende voorwaarden:
    - Back-ups zijn beperkt.

### <a name="unenrollment"></a>Registratie ongedaan maken
U kunt zakelijke e-mails en documenten op beheerde apps wissen op afstand, en zorgen dat persoonlijke gegevens worden ontsleuteld wanneer deze niet meer worden beheerd, als volgt:

1. [Geef opdracht om te wissen](apps-selective-wipe.md) vanuit Azure Portal.
2. Bevestig de volgende voorwaarden als er uw app niet voor handlers voor wissen is geregistreerd:
    - De app wordt volledig gewist.
3. Bevestig of de volgende voorwaarden als uw app is geregistreerd voor `WIPE_USER_DATA` of `WIPE_USER_AUXILARY_DATA`:
    - De beheerde inhoud wordt verwijderd uit de app. Zie de [ontwikkelaarshandleiding voor de Microsoft Intune App-SDK voor Android - Selectief wissen](app-sdk-android.md#selective-wipe) voor meer informatie.

### <a name="multi-identity"></a>Meerdere identiteiten
De integratie van [ondersteuning voor meerdere identiteiten](app-sdk-android.md#multi-identity-optional) is een wijziging met een hoog risico die grondig moet worden getest. De meest voorkomende problemen zijn te wijten aan een onjuiste instelling van de identiteit (context versus bedreigingsniveau), evenals het bijhouden van bestanden (`MAMFileProtectionManager`).

Ten minste de volgende scenario's voor meerdere identiteiten moeten opnieuw worden gevalideerd:

- Het beleid voor **Opslaan als** werkt correct voor beheerde identiteiten.
- Beperkingen voor kopiëren en plakken worden correct gehandhaafd van beheerd naar persoonlijk.
- Alleen gegevens die behoren tot de beheerde identiteit worden versleuteld, en persoonlijke bestanden worden niet gewijzigd.
- Met selectief wissen worden tijdens het uitschrijven van apparaten alleen gegevens van de beheerde identiteit verwijderd.
- De eindgebruiker wordt gevraagd om voorwaardelijk te starten wanneer wijziging plaatsvindt van een niet-beheerde in een beheerde account (alleen de eerste keer).

### <a name="app-configuration-optional"></a>App-configuratie (optioneel)
Gedrag van beheerde apps kunt u als volgt configureren:

1. Als uw app de instellingen van de app-configuratie gebruikt, moet u testen of uw app alle waarden correct verwerkt die u (als beheerder) kunt instellen. [App-configuratiebeleid](app-configuration-policies-overview.md) kan worden gemaakt en toegewezen met behulp van Intune.

## <a name="next-steps"></a>Volgende stappen

- [Een Android Line-Of-Business-app toevoegen aan Microsoft Intune](lob-apps-android.md).
