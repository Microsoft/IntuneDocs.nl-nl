---
title: Beslissingen voor de technologie voor BYOD met EMS
description: Belangrijke beslissingen voor de technologie voor het inschakelen van BYOD en beveiligen van zakelijke gegevens met Microsoft Enterprise Mobility + Security.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 12/8/2017
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: ba3f6fc48a68122f0a192adc8e2140bb7a603b31
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/23/2019
ms.locfileid: "66043465"
---
# <a name="technology-decisions-for-enabling-byod-with-microsoft-enterprise-mobility--security-ems"></a>Beslissingen voor de technologie voor het inschakelen van BYOD met Microsoft Enterprise Mobility + Security (EMS)

Bij het ontwikkelen van een strategie om werknemers extern op hun eigen apparaten te laten werken (BYOD) moet u belangrijke beslissingen nemen in de scenario's voor het inschakelen van BYOD en over de manier waarop zakelijke gegevens moeten worden beveiligd. Gelukkig biedt EMS alle mogelijkheden die u nodig hebt, in een uitgebreide reeks oplossingen.  

In dit onderwerp wordt het eenvoudige voorbeeld behandeld waarin BYOD wordt ingeschakeld voor toegang tot zakelijke e-mail. Hier wordt met name behandeld of u het gehele apparaat of alleen de toepassingen moet beheren. Beide opties zijn mogelijk.

## <a name="assumptions"></a>Aannames
* U beschikt over basiskennis van Azure Active Directory en Microsoft Intune
* Uw e-mailaccounts worden gehost in Exchange Online

## <a name="common-reasons-to-manage-the-device-mdm"></a>Veelvoorkomende redenen om het apparaat te beheren (MDM)
U kunt eenvoudig gebruikers ertoe bewegen hun apparaten te registreren bij apparaatbeheer door een beleid voor [voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) voor Exchange Online te implementeren. Misschien wilt u persoonlijke apparaten om een van de volgende redenen beheren:

**Wi-Fi/VPN**: als uw gebruikers een zakelijk connectiviteitsprofiel nodig hebben om productief te zijn, kan dit naadloos worden geconfigureerd.

**Toepassingen**: als voor uw gebruikers een set apps naar hun apparaat moet worden gepusht, kan deze naadloos worden geleverd. Dit omvat toepassingen die u misschien nodig hebt om beveiligingsredenen, zoals een Mobile Threat Defense-app.

**Naleving**: sommige organisaties moeten voldoen aan wettelijke of andere beleidsregels die specifieke MDM-besturingselementen aanroepen. U hebt bijvoorbeeld MDM nodig om het hele apparaat te versleutelen of om een rapport van alle apps op het apparaat te produceren.

## <a name="common-reasons-to-only-manage-the-apps-mam"></a>Veelvoorkomende redenen om alleen de apps te beheren (MAM)
MAM zonder MDM is zeer populair bij organisaties die ondersteuning bieden voor BYOD. U kunt ervoor zorgen dat gebruikers toegang tot e-mail krijgen vanuit Outlook Mobile (waarmee ondersteuning wordt geboden voor MAM-beveiliging) door een beleid voor voorwaardelijke toegang te implementeren voor Exchange Online. Misschien wilt u om een van de volgende redenen alleen apps beheren:

**Gebruikerservaring**: MDM-registratie omvat veel waarschuwingsprompts (afgedwongen door het platform) die er vaak toe leiden dat gebruikers besluiten hun e-mail helemaal niet op het persoonlijke apparaat te gebruiken. MAM is veel minder verontrustend voor gebruikers, omdat ze slechts eenmaal een pop-upvenster krijgen waarin wordt gemeld dat er MAM-beveiligingen zijn ingesteld.

**Naleving**: sommige organisaties moeten voldoen aan beleid waarvoor minder beheermogelijkheden op persoonlijke apparaten nodig zijn. MAM kan bijvoorbeeld alleen zakelijke gegevens uit de apps verwijderen, terwijl MDM alle gegevens van het apparaat kan verwijderen.

![Afbeelding waarin het beheer van het apparaat en het beheer van apps op mobiele apparaten wordt vergeleken](./media/byod-app-device-mgmt.png)

Meer informatie over [de levenscyclus van apparaatbeheer en app-beheer](introduction-device-app-lifecycles.md).

## <a name="mdm-vs-mam-capability-comparison"></a>Vergelijking van MDM- en MAM-mogelijkheden
Zoals al is vermeld, kan er met voorwaardelijke toegang voor worden gezorgd dat gebruikers hun apparaat registreren of een beheerde app, zoals Outlook Mobile, gebruiken. In beide gevallen kunnen veel andere voorwaarden worden toegepast, waaronder:

* Welke gebruiker probeert toegang te krijgen
* Welke locatie wordt vertrouwd of niet vertrouwd
*   Niveau van aanmeldingsrisico's
* Apparaatplatform

Toch maken veel organisaties zich nog steeds zorgen over specifieke risico's waarmee ze te maken hebben.  De volgende tabel bevat de meest voorkomende zorgen en hoe MDM en MAM hierop reageren.

| Zorgen   |   MDM  |   MAM  |
|------------|--------|--------|
|Niet-gemachtigde gegevenstoegang | Groepslidmaatschap vereisen | Groepslidmaatschap vereisen |
|Niet-gemachtigde gegevenstoegang | Apparaatregistratie vereisen | Beveiligde app vereisen |
|Niet-gemachtigde gegevenstoegang | Specifieke locatie vereisen | Specifieke locatie vereisen |
| | | |
|Aangetast gebruikersaccount| MFA vereisen | MFA vereisen|
|Aangetast gebruikersaccount | Gebruikers met een hoog risico blokkeren | Gebruikers met een hoog risico blokkeren |
|Aangetast gebruikersaccount | Pincode voor apparaat | Pincode voor app |
| | | |
| Aangetast apparaat of aangetaste app | Een compatibel apparaat vereisen | Jailbreak-controle bij starten app |
| Aangetast apparaat of aangetaste app | Apparaatgegevens versleutelen | App-gegevens versleutelen |
| | | |
|Verloren of gestolen apparaat | Alle apparaatgegevens verwijderen | Alle app-gegevens verwijderen|
| | | |
| Onbedoeld delen van gegevens of opslaan naar onbeveiligde locaties | Back-ups van apparaatgegevens beperken | Knippen/kopiëren/plakken beperken|
| Onbedoeld delen van gegevens of opslaan naar onbeveiligde locaties | Opslaan als beperken | Opslaan als beperken |
|Onbedoeld delen van gegevens of opslaan naar onbeveiligde locaties | Afdrukken uitschakelen | n.v.t.|

## <a name="next-steps"></a>Volgende stappen
Het is nu tijd om te kiezen of u BYOD in uw organisatie gaat inschakelen door te focussen op apparaatbeheer, app-beheer of een combinatie van beide. Het is aan u om te kiezen hoe u kunt garanderen dat de identiteits- en beveiligingsfuncties die beschikbaar zijn met Azure AD, altijd kunnen worden gebruikt.  

Gebruik de [planningshandleiding](planning-guide.md) van Intune om op een volgend niveau te plannen.
