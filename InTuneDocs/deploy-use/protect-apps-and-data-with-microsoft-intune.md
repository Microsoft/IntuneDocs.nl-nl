---
title: Apps en gegevens beveiligen | Microsoft Docs
description: In dit onderwerp worden de verschillende Intune-functies en -mogelijkheden beschreven die beschikbaar voor u zijn voor het beveiligen van uw bedrijfs-apps en -gegevens.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5c46e188-87eb-4ce2-b184-24809e8bf783
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f46f13e9dbf03fa2b3e2ec7339cad927ea0b38e0
ms.openlocfilehash: 16e4b6ddd1df9c56e36318dfd3050d1a1f627adc


---

# <a name="protect-apps-and-data-with-microsoft-intune"></a>Apps en gegevens beveiligen met Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune beveiligt bedrijfsgegevens via meerdere lagen van de technologie. Op de identiteitslaag beveiligt voorwaardelijke toegang de toegang tot services door alleen toegang te verlenen vanaf beheerde apparaten en apparaten die aan het beleid voldoen. Op de clienttoepassingslaag beveiligt MAM (Mobile Application Management) het verlies van gegevens door te voorkomen dat gegevens naar niet-beveiligde apps of opslaglocaties worden verplaatst en door gegevens te wissen wanneer een apparaat is zoekgeraakt of gestolen. U kunt het beste een combinatie van twee beveiligingslagen gebruiken om gegevens te beveiligen en uw mobiele medewerkers productief te houden.

Een belangrijke eerste stap in de beveiliging van bedrijfsgegevens vormt de implementatie van voorwaardelijke toegang. U kunt dit doen door ervoor te zorgen dat apparaten die worden gebruikt voor toegang tot deze gegevens, gebruikmaken van beveiligingsmaatregelen als sterke wachtwoorden en versleuteling, en geen jailbreak hebben. Met Intune kunt u voorwaarden instellen waaraan de apparaten moeten voldoen voordat ze toegang kunnen krijgen tot uw bedrijfs-e-mail en bedrijfsgegevens.

[Voorwaardelijke toegang](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) wordt bepaald door twee typen beleidsregels die u in Intune kunt instellen:
- U kunt [nalevingsbeleidsregels](introduction-to-device-compliance-policies-in-microsoft-intune.md) gebruiken om de naleving van een apparaat te bepalen. Dit beleid beoordeelt instellingen en voorwaarden zoals:
  - Pincodes en wachtwoorden: u kunt regels maken die het gebruik van een wachtwoord verplicht stellen om een apparaat te kunnen ontgrendelen. Met deze regels kunnen ook de complexiteitsvoorwaarden van het wachtwoord en andere wachtwoordinstellingen worden bepaald.
  - Versleuteling: u kunt de toegang beperken tot apparaten die zijn versleuteld.
  - Als het apparaat niet is gekraakt of geroot: Intune kan detecteren of een geregistreerd apparaat is gekraakt. U kunt het beleid zo instellen dat de toegang voor dergelijke apparaten wordt geblokkeerd.
- U kunt [beleidsregels voor voorwaardelijke toegang](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) configureren voor een bepaalde service, zoals Exchange Online of SharePoint Online. Voor elke service kunt u definiëren op welke groepen gebruikers deze beleidsregels van toepassing zijn. U kunt er bijvoorbeeld voor zorgen dat iedereen in de afdeling Financiën alleen toegang kan krijgen tot zakelijke e-mail van ingeschreven apparaten die aan het nalevingsbeleid voldoen.

Het beveiligen van toegang tot bedrijfsbronnen is de eerste stap in de bescherming van bedrijfsgegevens. U moet de gegevens nog steeds kunnen beveiligen nadat deze zijn geopend op het apparaat. De gegevens kunnen nu worden gekopieerd, verplaatst, opgeslagen op een andere locatie of gedeeld. Intune lost dit probleem op door u de mogelijkheid te bieden het verplaatsen van gegevens te beperken door regels te maken, zoals:
- Kopiëren en plakken blokkeren of verhinderen dat gegevens worden overgebracht buiten de context van het werk.
- Voorkomen dat er back-ups worden gemaakt naar persoonlijke cloudopslagruimte en voorkomen dat Opslaan als wordt gebruikt.
- Beveiligen van de toegang tot apps door een pincode/wachtwoordcode of zakelijke referenties verplicht te stellen.
- Alle webkoppelingen openen in de Intune Managed Browser.

Deze reeks regels wordt aangeduid als [beleid voor Mobile Application Management (MAM)](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md). U kunt MAM-beleid toepassen op apps die worden uitgevoerd op apparaten die wel of niet door u worden beheerd.  

U kunt uw bedrijfsgegevens beveiligen door MAM-beleid te gebruiken voor apparaten die zijn **ingeschreven bij Intune**, voor apparaten die zijn **geregistreerd en worden beheerd door een MDM-oplossing (Mobile Device Management) van derden**, en voor apparaten die **in een MDM-oplossing zijn ingeschreven**, zoals de apparaten van werknemers.

Als u een app wilt koppelen aan MAM-beleid, moet de app gebruikmaken van de Microsoft Intune App Software Development Kit (SDK). U kunt ook de App Wrapping Tool gebruiken.

De Intune App SDK is al ingebouwd in apps zoals de Microsoft Office-apps. U kunt de volledige lijst met ondersteunde apps bekijken in de [galerie met mobiele toepassingen van Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps) op de pagina voor Microsoft Intune-toepassingen van partners. Selecteer een app om de ondersteunde scenario's en platformen te bekijken en om te controleren of de app meerdere identiteiten ondersteunt.

U kunt ook [uw op maat gemaakte Line-Of-Business-apps inschakelen](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md) voor gebruik met MAM-beleid.

Naast het beperken van gegevensverplaatsing kunt u voor een zoekgeraakt of gestolen apparaat, of als de gebruiker niet meer bij uw bedrijf werkt, [selectief bedrijfsgegevens wissen](wipe-managed-company-app-data-with-microsoft-intune.md) en alleen persoonlijke gegevens behouden.



<!--HONumber=Dec16_HO3-->


