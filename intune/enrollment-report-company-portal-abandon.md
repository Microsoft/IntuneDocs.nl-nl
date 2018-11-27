---
title: Registratie in de bedrijfsportal afbreken in Intune
titlesuffix: Microsoft Intune
description: Meer informatie over het rapport Bedrijfsportal afbreken.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/20/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.openlocfilehash: 44a6d89b649514a08193d7144dff7d89dc3d9c55
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52183363"
---
# <a name="company-portal-abandonment-report"></a>Rapport Bedrijfsportal afbreken

In dit rapport ziet u op welk moment in de registratie bij de Bedrijfsportal de gebruikers het registratieproces afbreken.

Als u het rapport wilt zien, kiest u **Intune** > **Apparaatregistratie** > **Bedrijfsportal afbreken**.

U kunt met deze onboardinggegevens uw onboardingdocumenten bijwerken om gebruikers te helpen de registratie te voltooien. Als veel gebruikers bijvoorbeeld stoppen bij de Gebruiksvoorwaarden, is het raadzaam dat deel te onderzoeken en intuïtiever te maken voor gebruikers.

## <a name="what-is-abandonment"></a>Wat is afbreken?

Afbreken is het moment waarom een gebruiker een van de volgende bewerkingen uitvoert:

-   Expliciet een actie uitvoert om de registratie te onderbreken
-   De bedrijfsportal sluit tijdens de registratie
-   Meer dan 30 minuten doet over de verschillende secties van de registratie

Als een gebruiker er meerdere keren voor kiest om de registratie te stoppen en deze opnieuw te starten, wordt dit weergegeven als meerdere pogingen en meerdere afbrekingen. Als een gebruiker 30 minuten wacht tussen de verschillende registratieschermen, wordt dit beschouwd als meerdere afbrekingen.

## <a name="what-does-the-report-show"></a>Wat wordt in het rapport weergegeven?

De registratierapporten omvatten gegevens voor iOS en Android-apparaten.

In de rapporten worden gegevens weergegeven voor de afgelopen twee weken. U kunt het rapport echter filteren op weergave van elke willekeurige periode in de afgelopen 30 dagen.

U kunt het datumbereik, het besturingssysteem en de registratiesectie filteren door **Filteren** te kiezen.

### <a name="number-and-percentage-tiles"></a>Tegels voor aantal en percentage

Boven in het rapport ziet u het aantal en het percentage gevallen van afbreking ten opzichte van alle registraties.

-   Gestarte registraties: het aantal gestarte registraties.
-   Afgebroken registraties: het aantal gestarte registraties dat niet heeft geresulteerd in een volledig geregistreerd en compatibel apparaat.
-   Percentage afbrekingen: het percentage gestarte registraties dat is afgebroken (afgebroken registraties/gestarte registraties).

### <a name="line-graph"></a>Lijndiagram

In het lijndiagram ziet u de dagelijkse afbrekingen voor elk van de vier kernsecties voor registratie:

-   Instellingencontrole
-   Platformschermen
-   Gebruiksvoorwaarden
-   Naleving/activering

### <a name="user-abandonment-actions"></a>Gebruikersacties voor afbreking

De volgende tabellen bevatten de lijst met gebruikersacties die worden beschouwd als afbreking. Bekijk de registratievideo’s voor [iOS](https://channel9.msdn.com/Series/IntuneEnrollment/iOS-Enrollment) en [Android](https://channel9.msdn.com/Series/IntuneEnrollment/Android-Enrollment) voor voorbeelden van registratieschermen. 


#### <a name="setup-checklist-section"></a>Sectie Instellingencontrole

| Naam voor afbreken | Scherm of stroom | Platform | Actie |
| ---- |---- |---- |---- |
| EnrollmentWrapUp | Vragen om de pagina te openen in de bedrijfsportal | iOS/Android | **Annuleren** |
| EnrollmentWrapUp | Scherm voor apparaatregistratie tot het **Laden van bedrijfsresources** is voltooid | iOS/Android | Duur > 30 minuten |
| DeviceCategory | Selectie van Apparaatcategorie (indien dit door de beheerder is geconfigureerd) tot op **Gereed** wordt geklikt | iOS/Android | Duur > 30 minuten |
| PreEnrollmentWizard | Scherm voor instellingstoegang wanneer de registratie is gestart, maar de gebruiker is teruggekeerd naar de Instellingstoegang | iOS/Android| **Uitstellen** |
| PreEnrollmentWizard | Scherm voor Instellingstoegang totdat op **Volgende** wordt geklikt in het scherm **Wat moet er nu gebeuren** | iOS/Android | Duur > 30 minuten |

#### <a name="platform-screens-section"></a>Sectie Platformschermen

| Naam voor afbreken | Scherm of stroom | Platform | Actie |
| ---- |---- |---- |---- |
| iOSProfileLaunch | Vragen om weergave van een configuratieprofiel | iOS | **Negeren** |
| iOSProfileLaunch | Scherm Profiel installeren | iOS | **Annuleren** |
| iOSProfileLaunch | Vragen om de bron van het profiel te vertrouwen om het apparaat te registreren | iOS | **Annuleren** |
| iOSProfileLaunch | Scherm Profiel installeren totdat het profiel is geïnstalleerd | iOS | Duur > 30 minuten |
| AndroidPermissions | Het activeringsscherm Apparaatbeheerder | Android | **Annuleren** |
| AndroidPermissions | Vanaf de vraag om goedkeuring voor het maken en beheren van telefoongesprekken tot **Activeren** door apparaatbeheerder | Android | Duur > 30 minuten |
| KnoxActivation | Activering van de KLMS-agent (alleen Samsung) | Android| **Annuleren** |
| KnoxActivation | Activering van de KLMS-agent tot **Bevestigen** | Android | Duur > 30 minuten|

#### <a name="terms-of-use-section"></a>Sectie Gebruiksvoorwaarden

| Naam voor afbreken | Scherm of stroom | Platform | Actie |
| ---- |---- |---- |---- |
| TermsofUse | Gebruiksvoorwaarden (als dit door de beheerder is geconfigureerd) | iOS/Android | **Alles weigeren** |
| TermsofUse | Gebruiksvoorwaarden tot **Alles accepteren** | iOS/Android | Duur > 30 minuten |

#### <a name="complianceactivation-section"></a>Sectie Naleving/activering

| Naam voor afbreken | Scherm of stroom | Platform | Actie |
| ---- |---- |---- |---- |
| Naleving | Apparaatcompatibiliteit (als dit door de beheerder is geconfigureerd) wordt weergegeven als niet groen voor het instellen van toegang na registratie| iOS/Android | **Uitstellen** |
| Naleving | Apparaatcompatibiliteit wordt weergegeven als niet groen totdat na het bijwerken groen wordt weergegeven | iOS/Android | Duur > 30 minuten |
| Activering | Registratieactivering (als dit door de beheerder is geconfigureerd) wordt weergegeven als niet groen voor het instellen van toegang | iOS/Android | **Uitstellen** |
| Naleving | Apparaatactivering wordt weergegeven als niet groen totdat na het bijwerken groen wordt weergegeven | iOS/Android | Duur > 30 minuten |

## <a name="next-steps"></a>Volgende stappen

Nadat u de afbrekingspercentages hebt bekijken, kunt u de [Inschrijvingsopties](enrollment-options.md) beoordelen om te zien of u wijzigingen kunt aanbrengen voor het verbeteren van het registratieproces.