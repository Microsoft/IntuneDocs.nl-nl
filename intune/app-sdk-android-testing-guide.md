---
title: Testhandleiding voor ontwikkelaars voor Microsoft Intune App SDK voor Android
description: De Microsoft Intune App SDK voor Android-handleiding testen kunt u uw Intune beheerde Android-app te testen.
keywords: SDK
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/14/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 4ef8f421-9610-4d34-a464-cc02eb1578a9
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4203f424c395399cb0ed1e7472b006602aa0b210
ms.sourcegitcommit: db7a6b8fc9e82dae4f2111ca0b2d3c14e33658f9
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2019
ms.locfileid: "58072468"
---
# <a name="microsoft-intune-app-sdk-for-android-developers-testing-guide"></a>Testhandleiding voor ontwikkelaars voor Microsoft Intune App SDK voor Android

De Microsoft Intune App SDK voor Android-testen handleiding is ontworpen om u te helpen u uw Intune beheerde Android-app testen.  

## <a name="prerequisite-test-accounts"></a>Vereiste testaccounts
Nieuwe accounts kunnen worden gemaakt met en zonder vooraf gegenereerde gegevens. Een nieuw account maken:
1. Navigeer naar de [Microsoft Demos](https://demos.microsoft.com/environments/create/tenant) site. 
2. [Intune instellen](https://docs.microsoft.com/intune/setup-steps) beheer van mobiele apparaten (MDM) inschakelen.
3. [Gebruikers maken](https://docs.microsoft.com/intune/users-add).
4. [Groepen maken](https://docs.microsoft.com/intune/groups-add).
5. [Licenties toewijzen](https://docs.microsoft.com/intune/licenses-assign) die geschikt zijn voor het testen.


## <a name="azure-portal-policy-configuration"></a>Azure portal-beleidsconfiguratie
[Maken en toewijzen van app-beveiligingsbeleid](https://docs.microsoft.com/intune/app-protection-policies) in de [de blade Intune van Azure portal](https://portal.azure.com/?feature.customportal=false#blade/Microsoft_Intune_Apps/MainMenu/14/selectedMenuItem/Overview). Uw [app-configuratiebeleid](https://docs.microsoft.com/intune/app-configuration-policies-overview) kan ook worden gemaakt en toegewezen op de blade Intune.

> [!NOTE]
> Als uw app niet wordt vermeld in de Azure-portal, kunt u deze richten met een beleid dat door het selecteren van de **meer apps** optie en het geven van de naam van het pakket in het tekstvak in.

> [!IMPORTANT]
> Voor een app-configuratiebeleid om toe te passen, de registratie gebruiker moet het doel zijn van een [Intune-beveiligingsbeleid voor](https://docs.microsoft.com/intune/app-protection-policy).

## <a name="test-cases"></a>Testscenario 's

De volgende testcases bieden stappen voor configuratie en de bevestiging. Gebruik deze richtlijnen bij het oplossen van problemen met Intune beheerde Android-app.

### <a name="required-pin-and-corporate-credentials"></a>Vereiste PINCODE en zakelijke referenties

U kunt een pincode vereisen voor toegang tot bedrijfsbronnen. U kunt ook zakelijke verificatie afdwingen voordat gebruikers de beheerde apps kunnen gebruiken. Gebruik de volgende stappen uit om in te stellen van deze vereisten:

1. Configureer **PINCODE vereisen voor toegang tot** en **bedrijfsreferenties vereisen voor toegang tot** naar **Ja**. Zie voor meer informatie, [beveiligingsbeleidsinstellingen voor Android-app in Microsoft Intune](app-protection-policy-settings-android.md#access-requirements).
2. Controleer of de volgende voorwaarden:
    - Starten van de App dient een prompt voor PINCODE invoer/instellen en/of de productie-gebruiker die is gebruikt tijdens de inschrijving met de bedrijfsportal-App te presenteren.
    - Fout om een geldige aanmeldingsprompt kan worden veroorzaakt door een onjuist geconfigureerde android manifest specifiek de waarden voor de integratie van ADAL (SkipBroker, ClientID en -instantie).
    - Fout om een prompt wordt mogelijk veroorzaakt door een onjuist geïntegreerde `MAMActivity` waarde. Voor meer informatie over `MAMActivity`, Zie [Microsoft Intune App SDK voor Android-ontwikkelaarshandleiding](app-sdk-android.md).

> [!NOTE] 
> Als de bovenstaande test niet werkt, wordt waarschijnlijk ook de onderstaande tests mislukken. Beoordeling [SDK](app-sdk-android.md##sdk-integration) en [ADAL](app-sdk-android.md#configure-azure-active-directory-authentication-library-adal) integratie.

### <a name="restrict-transferring-and-receiving-data-with-other-apps"></a>Overbrengen en ontvangen van gegevens met andere apps beperken
U kunt de overdracht van gegevens tussen beheerde bedrijfstoepassingen als volgt beheren:

1. Stel **toestaan dat app gegevens overdraagt naar andere apps** naar **door beleid beheerde apps**.
2. Stel **App mag gegevens ontvangen van andere apps** in op **Alle apps**. Gebruik van intents en inhoudsproviders zullen worden beïnvloed door dit beleid.
3. Controleer of de volgende voorwaarden:
    - Vanuit een niet-beheerde app op in de functies van uw app juist geopend.
    - Delen van inhoud tussen beheerde apps is toegestaan.
    - Delen van beheerde apps op niet-beheerde apps (bijvoorbeeld Chrome) is geblokkeerd.

### <a name="restrict-cut-copy-and-paste"></a>Knippen, kopiëren en plakken beperken
U kunt het systeemklembord beperken tot beheerde toepassingen als volgt te werk:

1. Stel **beperken knippen, kopiëren en plakken met andere apps** naar **met beleidsbeheer met plakken in**.
2. Controleer of de volgende voorwaarden:
    - Tekst uit uw app kopieert naar een beheerde is een niet-beheerde app (bijvoorbeeld berichten) geblokkeerd.

### <a name="prevent-save-as"></a>**Opslaan als** voorkomen
U kunt bepalen **opslaan als** functionaliteit als volgt te werk:

1. Als uw app nodig heeft [geïntegreerde besturingselementen 'opslaan als'](app-sdk-android.md#example-determine-if-saving-to-device-or-cloud-storage-is-permitted), stel **te voorkomen dat OpslaanAls** naar **Ja**.
2. Controleer of de volgende voorwaarden:
    - Opslaan is beperkt tot alleen juiste beheerde locaties.

### <a name="file-encryption"></a>Bestandsversleuteling
U kunt gegevens op het apparaat als volgt versleutelen:

1. Stel **app-gegevens versleutelen** naar **Ja**.
2. Controleer of de volgende voorwaarden:
    - Werking van de normale toepassing wordt niet negatief beïnvloed.

### <a name="prevent-android-backups"></a>Back-ups van Android voorkomen
U kunt als volgt back-up app beheren:

1. Als u hebt ingesteld [geïntegreerde back-beperkingen](app-sdk-android.md#protecting-backup-data), configureren **back-ups van Android voorkomen** naar **Ja**.
2. Controleer of de volgende voorwaarden:
    - Back-ups zijn beperkt.

### <a name="unenrollment"></a>Registratie ongedaan maken
U kunt beheerde apps door zakelijke e-mail en documenten die op afstand wissen en persoonlijke gegevens worden ontsleuteld wanneer deze is niet langer beheerd als volgt:

1. Vanuit de Azure-portal, [uitgeven van een wisbewerking](https://docs.microsoft.com/intune/apps-selective-wipe).
2. Als uw app wordt niet geregistreerd voor elke handlers wissen Bevestig de volgende voorwaarden:
    - Een volledig wissen van de app wordt uitgevoerd.
3. Als uw app is geregistreerd voor `WIPE_USER_DATA` of `WIPE_USER_AUXILARY_DATA`, Controleer of de volgende voorwaarden:
    - De beheerde inhoud wordt verwijderd uit de app. Zie voor meer informatie, [Intune App SDK voor Android-ontwikkelaarshandleiding - selectief wissen](app-sdk-android.md#selective-wipe).

### <a name="multi-identity"></a>Meerdere identiteiten
Integratie van [ondersteuning voor meerdere identiteiten](app-sdk-android.md#multi-identity-optional) een hoog risico wijziging die moet worden getest. De meest voorkomende problemen worden vanwege onjuiste instelling van de identiteit (context versus threat-niveau) en ook bestanden bijhouden (`MAMFileProtectionManager`).

Minimaal de volgende scenario's voor meerdere identiteiten moeten opnieuw worden gevalideerd:

- **OpslaanAls** beleid correct werkt voor beheerde identiteiten.
- Kopiëren en plakken beperkingen correct van gelden beheerd naar persoonlijke.
- Alleen gegevens die behoren tot de beheerde identiteit wordt gecodeerd en persoonlijke bestanden niet worden gewijzigd.
- Selectief wissen tijdens het uitschrijven van apparaten verwijdert alleen gegevens beheerde identiteit.
- De gebruiker wordt gevraagd voor voorwaardelijk starten wanneer het wijzigen van niet-beheerde naar beheerde account (alleen de eerste keer).

### <a name="app-configuration-optional"></a>App-configuratie (optioneel)
Gedrag van beheerde apps kunt u als volgt configureren:

1. Als uw app de app-configuratie-instellingen gebruikt, moet u testen of uw app correct alle waarden die u (als de beheerder verwerkt) kunt instellen. [App-configuratiebeleid](https://docs.microsoft.com/intune/app-configuration-policies-overview) kan worden gemaakt en toegewezen in met behulp van Intune.

## <a name="next-steps"></a>Volgende stappen

- [Een Android Line-Of-Business-app toevoegen aan Microsoft Intune](lob-apps-android.md).
