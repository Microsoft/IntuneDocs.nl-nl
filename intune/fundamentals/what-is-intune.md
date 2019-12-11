---
title: Wat is Microsoft Intune - Azure | Microsoft Docs
description: Leer over Microsoft Intune als het MDM-onderdeel (beheer van mobiele apparaten) en MAM-onderdeel (beheer van mobiele apps) van de oplossing Enterprise Mobility + Security en hoe u hiermee bedrijfsgegevens kunt beschermen.
keywords: wat is Intune
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 10/14/2019
ms.topic: overview
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3b4e778d-ac13-4c23-974f-5122f74626bc
ms.reviewer: pmay
ms.suite: ems
search.appverid: MET150
ms.custom: get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: c3c03c67a99b78804c999250f8d1148a4b3d1d97
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72504766"
---
# <a name="microsoft-intune-is-an-mdm-and-mam-provider-for-your-devices"></a>Microsoft Intune is een MDM- en MAM-provider voor uw apparaten

Microsoft Intune is een cloudservice die is gericht op MDM (Mobile Device Management) en MAM (Mobile Application Management). Intune is opgenomen in de [EMS-suite (Enterprise Mobility en Security)](https://www.microsoft.com/microsoft-365/enterprise-mobility-security) van Microsoft, en biedt gebruikers de mogelijkheid om productief te zijn terwijl uw bedrijfsgegevens beschermd blijven. Het wordt geïntegreerd met andere services, waaronder Microsoft 365 en Azure AD (Active Directory) om te bepalen wie toegang heeft, en waartoe ze toegang hebben, en Azure Information Protection voor gegevensbescherming. Als u het gebruikt in combinatie met Microsoft 365, kunt u ervoor zorgen dat uw medewerkers productief werken op al hun apparaten terwijl de gegevens van uw organisatie beschermd blijven.

![Afbeelding van Intune-architectuur](./media/what-is-intune/intunearch_sm.png)

Geef een [grotere versie](./media/what-is-intune/intunearchitecture.svg) van het diagram van de Intune-architectuur weer.

Met Intune kunt u het volgende doen:

- Kiezen voor 100% werken in de cloud met Intune, of voor [co-beheer](https://docs.microsoft.com/sccm/comanage/overview) tussen Configuration Manager en Intune.
- Regels instellen en instellingen configureren voor persoonlijke apparaten en apparaten die eigendom zijn van de organisatie, om toegang te krijgen tot gegevens en netwerken.
- Apps implementeren en verifiëren op apparaten: on-premises en mobiel.
- Uw bedrijfsgegevens beschermen door de manier te bepalen waarop gebruikers gegevens kunnen openen en delen.
- Ervoor zorgen dat apparaten en apps voldoen aan de beveiligingsvereisten.

## <a name="manage-devices"></a>Beheer apparaten

In Intune beheert u apparaten met behulp van de methode die het meest geschikt is voor u. Voor apparaten die eigendom zijn van de organisatie, wilt u mogelijk volledig beheer hebben op de apparaten, inclusief instellingen, functies en beveiliging. In deze methode worden apparaten en gebruikers van deze apparaten ingeschreven bij Intune. Nadat ze zijn ingeschreven, ontvangen ze uw regels en instellingen via beleid dat is geconfigureerd in Intune. U kunt bijvoorbeeld vereisten voor wachtwoorden en pincodes instellen, een VPN-verbinding maken, beveiliging tegen bedreigingen instellen, en meer.

Voor persoonlijke apparaten, of BYOD-apparaten (Bring Your Own Devices), willen gebruikers mogelijk niet dat hun organisatiebeheerders volledig beheer krijgen. In deze methode kunt u gebruikers opties geven. Gebruikers kunnen hun apparaten bijvoorbeeld [inschrijven](../enrollment/device-enrollment.md) als ze volledige toegang tot uw organisatieresources willen. Of als deze gebruikers alleen toegang willen tot e-mail of Microsoft Teams, gebruikt u app-beveiligingsbeleid op basis waarvan MFA (Multi-Factor Authentication) is vereist om deze apps te gebruiken.

Als apparaten zijn ingeschreven en worden beheerd in Intune, kunnen beheerders het volgende doen:

- Zien welke apparaten zijn ingeschreven, en een inventaris krijgen van de apparaten die toegang hebben tot organisatieresources.
- Apparaten configureren zodat ze voldoen aan uw beveiligings- en statusstandaarden. Zo wilt u waarschijnlijk bijvoorbeeld opengebroken apparaten blokkeren.
- Certificaten naar apparaten pushen zodat gebruikers eenvoudig toegang kunnen krijgen tot uw Wi-Fi-netwerk, of een VPN gebruiken om verbinding te maken met het netwerk.
- Rapporten bekijken over gebruikers en apparaten die voldoen en die niet voldoen aan het beleid.
- Organisatiegegevens verwijderen als een apparaat is verloren of gestolen, of niet meer wordt gebruikt.

**Onlineresources**:

- [Wat is apparaatinschrijving?](../enrollment/device-enrollment.md)

- [Functies en instellingen toepassen op uw apparaten met behulp van apparaatprofielen](../configuration/device-profiles.md)

- [Apparaten beveiligen met Microsoft Intune](../protect/device-protect.md)

## <a name="manage-apps"></a>Apps beheren

MAM (Mobile Application Management) in Intune is ontworpen om organisatiegegevens te beveiligen op toepassingsniveau, inclusief aangepaste apps en Store-apps. App-beheer kan worden gebruikt op persoonlijke apparaten en apparaten die eigendom zijn van de organisatie.

Wanneer apps worden beheerd in Intune, kunnen beheerders het volgende doen:

- Mobiele apps toevoegen en toewijzen aan gebruikersgroepen en apparaten, inclusief gebruikers in specifieke groepen, apparaten in specifieke groepen, en meer.
- Apps configureren om te starten of te worden uitgevoerd met specifieke instellingen ingeschakeld, en bestaande apps op het apparaat bijwerken.
- Rapporten bekijken over welke apps worden gebruikt, en hun gebruik bijhouden.
- Selectief wissen door alleen organisatiegegevens te verwijderen uit apps.

Een van de manieren waarop Intune beveiliging van mobiele apps biedt, is via **[app-beveiligingsbeleid](../apps/app-protection-policy.md)** . Onderdelen van app-beveiligingsbeleid:

- Het maakt gebruik van Azure AD-identiteit om organisatiegegevens te isoleren van persoonlijke gegevens. Op deze manier worden persoonlijke gegevens geïsoleerd van de organisatie-IT. Gegevens die toegankelijk zijn via organisatiereferenties, zijn extra beveiligd.
- Het helpt om de toegang via persoonlijke apparaten te beveiligen door te beperken welke acties gebruikers kunnen uitvoeren, zoals kopiëren en plakken, opslaan en weergeven.
- Het kan worden gemaakt en geïmplementeerd op apparaten die zijn ingeschreven bij Intune, ingeschreven bij een andere MDM-service, of die niet zijn ingeschreven bij een MDM-service. Op ingeschreven apparaten kan beveiligingsbeleid voor apps een extra beveiligingslaag toevoegen.

Bijvoorbeeld: een gebruiker meldt zich met behulp van de organisatiereferenties aan bij een apparaat. De organisatie-identiteit verleent toegang tot gegevens die op basis van een persoonlijke identiteit zouden worden geweigerd. Als deze organisatiegegevens worden gebruikt, bepaalt het app-beveiligingsbeleid hoe de gegevens worden opgeslagen en gedeeld. Wanneer gebruikers zich aanmelden met hun persoonlijke identiteit, worden deze beveiligingsmaatregelen niet toegepast. De IT-afdeling heeft zo het beheer over de organisatiegegevens, terwijl eindgebruikers het beheer houden over hun persoonlijke gegevens en de privacy hiervan.

En u kunt Intune gebruiken met de andere services in EMS. Deze functie biedt uw organisatie beveiliging van mobiele apps die verder gaat dan de beveiliging die onderdeel uitmaakt van het besturingssysteem en eventuele apps. Apps die worden beheerd met EMS hebben toegang tot een uitgebreidere set functies voor de beveiliging van mobiele apps en gegevens.

![Installatiekopie waarin de niveaus van beheer van gegevensbeveiliging voor apps worden weergegeven](./media/what-is-intune/managing-mobile-apps.png)

## <a name="compliance-and-conditional-access"></a>Naleving en voorwaardelijke toegang

Intune integreert met Azure AD om tal van scenario’s voor toegangsbeheer mogelijk te maken. Bijvoorbeeld, vereisen dat mobiele apparaten voldoen aan organisatiestandaarden die worden gedefinieerd in Intune vóórdat toegang kan worden verkregen tot netwerkresources, zoals e-mail of SharePoint. U kunt ook de services vergrendelen zodat ze alleen beschikbaar zijn voor een specifieke set mobiele apps. Zo kunt u Exchange Online bijvoorbeeld vergrendelen, zodat deze toepassing alleen toegankelijk is voor Outlook of Outlook Mobile.

**Onlineresources**:

- [Regels instellen op apparaten om toegang tot organisatieresources toe te staan](../protect/device-compliance-get-started.md)

- [Gebruikelijke manieren om voorwaardelijke toegang met Intune te gebruiken](../protect/conditional-access-intune-common-ways-use.md)

## <a name="how-to-get-intune"></a>Intune verkrijgen

Intune is beschikbaar:

- Als een zelfstandige [Azure-service](https://go.microsoft.com/fwlink/?linkid=2090973)
- Inbegrepen bij [Microsoft 365 ](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune) en [Microsoft 365 Government](https://www.microsoft.com/microsoft-365/government)
- Als [Mobile Device Management in Office 365 ](https://support.office.com/article/choose-between-mdm-for-office-365-and-microsoft-intune-c93d9ab9-efb2-4349-9b93-30c30562ee22), wat bestaat uit een beperkt aantal Intune-functies

InTune wordt gebruikt in veel sectoren, waaronder [Government ](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-govt-service-description), [Education ](https://www.microsoft.com/en-us/education/intune), [Kiosk of toegewezen apparaat ](../configuration/kiosk-settings.md) voor productie en verkoop, en meer.

## <a name="next-steps"></a>Volgende stappen

- Lees sommige [algemene bedrijfsproblemen die Intune u helpt op te lossen](https://docs.microsoft.com/intune/common-scenarios).
- Begin met een [proefversie van 30 dagen](free-trial-sign-up.md).
- Plan uw [migratie naar Intune](migration-guide.md).
- Voer met behulp van uw gratis proefversie of abonnement de stappen uit in de [Quickstart: Een e-mailprofiel voor een apparaat voor iOS maken](../configuration/quickstart-email-profile.md) te volgen.
