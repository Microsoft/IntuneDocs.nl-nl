---
title: Rapport over onvolledige gebruikersinschrijving in Intune
titleSuffix: Microsoft Intune
description: Meer informatie over het rapport over onvolledige gebruikersinschrijving.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 2/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: ae3c2380aa27096be2490d2404858179ea9d222e
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72503189"
---
# <a name="incomplete-user-enrollments-report"></a>Rapport over onvolledige gebruikersinschrijving

In dit rapport ziet u op welk moment in de inschrijving bij de bedrijfsportal de gebruikers het inschrijvingsproces niet voltooien.

Als u het rapport wilt zien, kiest u **Intune** > **Apparaatinschrijving** > **Onvolledige gebruikersinschrijvingen**.

U kunt met deze informatie uw onboardingdocumenten bijwerken om gebruikers te helpen de inschrijving te voltooien. Als veel gebruikers bijvoorbeeld stoppen bij de Gebruiksvoorwaarden, is het raadzaam dat deel te onderzoeken en intuïtiever te maken voor gebruikers.

## <a name="what-is-an-incomplete-enrollment"></a>Wat is een onvolledige inschrijving?

Er is sprake van een onvolledige inschrijving wanneer een gebruiker een van de volgende bewerkingen uitvoert:

- Expliciet een actie uitvoert om de registratie te onderbreken
- De bedrijfsportal sluit tijdens de registratie
- Meer dan 30 minuten doet over de verschillende secties van de registratie

Als een gebruiker er meerdere keren voor kiest om de inschrijving te stoppen en deze opnieuw te starten, wordt dit weergegeven als meerdere pogingen en meerdere onvolledige inschrijvingen. Als een gebruiker 30 minuten wacht tussen de verschillende inschrijvingsschermen, wordt dit beschouwd als meerdere onvolledige inschrijvingen.

## <a name="what-does-the-report-show"></a>Wat wordt in het rapport weergegeven?

De rapporten omvatten gegevens voor iOS- en Android-apparaten.

In de rapporten worden gegevens weergegeven voor de afgelopen twee weken. U kunt het rapport echter filteren op weergave van elke willekeurige periode in de afgelopen 30 dagen.

U kunt het datumbereik, het besturingssysteem en de registratiesectie filteren door **Filteren** te kiezen.

### <a name="number-and-percentage-tiles"></a>Tegels voor aantal en percentage

Boven in het rapport ziet u het aantal en het percentage onvolledige inschrijvingen ten opzichte van alle inschrijvingen.

- Geïnitieerde inschrijvingen: Het aantal gestarte inschrijvingen.
- Onvolledige inschrijvingen: Het aantal gestarte inschrijvingen dat niet heeft geresulteerd in een volledig ingeschreven en compatibel apparaat.
- Percentage onvolledige inschrijvingen: het percentage gestarte inschrijvingen dat is afgebroken (afgebroken inschrijvingen/gestarte inschrijvingen).

### <a name="line-graph"></a>Lijndiagram

In het lijndiagram ziet u de dagelijkse onvolledige inschrijvingen voor elk van de vier kernsecties voor inschrijving:

- Instellingencontrole
- Platformschermen
- Gebruiksvoorwaarden
- Naleving/activering

### <a name="user-abandonment-actions"></a>Gebruikersacties voor afbreking

De volgende tabellen bevatten de lijst met gebruikersacties die worden beschouwd als onvolledige inschrijvingen. Bekijk de registratievideo’s voor [iOS](https://channel9.msdn.com/Series/IntuneEnrollment/iOS-Enrollment) en [Android](https://channel9.msdn.com/Series/IntuneEnrollment/Android-Enrollment) voor voorbeelden van registratieschermen. 


#### <a name="setup-checklist-section"></a>Sectie Instellingencontrole

| Actienaam | Scherm of stroom | Platform | Actie |
| ---- |---- |---- |---- |
| EnrollmentWrapUp | Vragen om de pagina te openen in de bedrijfsportal | iOS/Android | **Annuleren** |
| EnrollmentWrapUp | Scherm voor apparaatregistratie tot het **Laden van bedrijfsresources** is voltooid | iOS/Android | Duur > 30 minuten |
| DeviceCategory | Selectie van Apparaatcategorie (indien dit door de beheerder is geconfigureerd) tot op **Gereed** wordt geklikt | iOS/Android | Duur > 30 minuten |
| PreEnrollmentWizard | Scherm voor instellingstoegang wanneer de registratie is gestart, maar de gebruiker is teruggekeerd naar de Instellingstoegang | iOS/Android| **Uitstellen** |
| PreEnrollmentWizard | Scherm voor Instellingstoegang totdat op **Volgende** wordt geklikt in het scherm **Wat moet er nu gebeuren** | iOS/Android | Duur > 30 minuten |

#### <a name="platform-screens-section"></a>Sectie Platformschermen

| Actienaam | Scherm of stroom | Platform | Actie |
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

| Actienaam | Scherm of stroom | Platform | Actie |
| ---- |---- |---- |---- |
| TermsofUse | Gebruiksvoorwaarden (als dit door de beheerder is geconfigureerd) | iOS/Android | **Alles weigeren** |
| TermsofUse | Gebruiksvoorwaarden tot **Alles accepteren** | iOS/Android | Duur > 30 minuten |

#### <a name="complianceactivation-section"></a>Sectie Naleving/activering

| Actienaam | Scherm of stroom | Platform | Actie |
| ---- |---- |---- |---- |
| Naleving | Apparaatcompatibiliteit (als dit door de beheerder is geconfigureerd) wordt weergegeven als niet groen voor het instellen van toegang na registratie| iOS/Android | **Uitstellen** |
| Naleving | Apparaatcompatibiliteit wordt weergegeven als niet groen totdat na het bijwerken groen wordt weergegeven | iOS/Android | Duur > 30 minuten |
| Activering | Registratieactivering (als dit door de beheerder is geconfigureerd) wordt weergegeven als niet groen voor het instellen van toegang | iOS/Android | **Uitstellen** |
| Naleving | Apparaatactivering wordt weergegeven als niet groen totdat na het bijwerken groen wordt weergegeven | iOS/Android | Duur > 30 minuten |

## <a name="next-steps"></a>Volgende stappen

Nadat u het percentage onvolledige inschrijvingen hebt bekeken, kunt u de [Inschrijvingsopties](enrollment-options.md) beoordelen om te zien of u wijzigingen kunt aanbrengen voor het verbeteren van het inschrijvingsproces.
