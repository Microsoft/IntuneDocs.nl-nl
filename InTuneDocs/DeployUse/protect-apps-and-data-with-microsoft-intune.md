---
title: Apps en gegevens beveiligen | Microsoft Intune
description: 
keywords: In dit onderwerp worden de verschillende Intune-functies en -mogelijkheden beschreven die beschikbaar voor u zijn voor het beveiligen van uw bedrijfs-apps en -gegevens.
author: karthikaraman
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5c46e188-87eb-4ce2-b184-24809e8bf783
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: be1ebcdf2514e45d383dd49890e0e21acf6ede44
ms.openlocfilehash: cf2ef1510aa9dafeddf54855123c826c9ccc2fd0


---

# Apps en gegevens beveiligen met Microsoft Intune


Intune beveiligt bedrijfsgegevens via meerdere lagen van de technologie.  Op de identiteitslaag beveiligt voorwaardelijke toegang de toegang tot services door alleen toegang te verlenen vanaf beheerde apparaten en apparaten die aan het beleid voldoen.  Op de clienttoepassingslaag beveiligt het beheer van mobiele apps (MAM) het verlies van gegevens door te voorkomen dat gegevens naar niet-beveiligde apps of opslaglocaties worden verplaatst en door gegevens te wissen wanneer een apparaat is zoekgeraakt of gestolen.  Deze twee lagen beveiliging moeten samen worden gebruikt om gegevens te beveiligen en uw mobiele medewerkers productief te houden.

Een belangrijke eerste stap bij de bescherming van bedrijfsgegevens is het implementeren van voorwaardelijke toegang door ervoor te zorgen dat apparaten die worden gebruikt voor toegang tot de gegevens, beveiligingsinstellingen gebruiken, zoals een sterk wachtwoord en versleuteling, en niet zijn gekraakt. Met Microsoft Intune kunt u voorwaarden instellen waaraan de apparaten moeten voldoen voordat ze toegang kunnen krijgen tot uw bedrijfse-mail en bedrijfsgegevens.

[Voorwaardelijke toegang](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) wordt bepaald door twee typen beleidsregels die u in Intune kunt instellen:
- [Nalevingsbeleid](introduction-to-device-compliance-policies-in-microsoft-intune.md) bepaalt de naleving van een apparaat. Dit beleid beoordeelt instellingen en voorwaarden zoals:
  - Pincode en wachtwoorden: u kunt regels maken die het gebruik van een wachtwoord verplicht stellen om een apparaat te kunnen ontgrendelen. Met deze regels kunnen ook de complexiteitsvoorwaarden van het wachtwoord en andere wachtwoordinstellingen worden bepaald.
  - Versleuteling: u kunt de toegang beperken tot apparaten die zijn versleuteld.
  - Het apparaat is niet gekraakt of geroot: Intune kan detecteren of een geregistreerd apparaat is gekraakt. U kunt het beleid zo instellen dat de toegang voor dergelijke apparaten wordt geblokkeerd.
- [Voorwaardelijk toegangsbeleid](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) wordt geconfigureerd voor een bepaalde service, zoals Exchange Online of SharePoint Online. Voor elke service kunt u definiëren op welke groepen gebruikers deze beleidsregels van toepassing zijn. U kunt er bijvoorbeeld voor zorgen dat iedereen in de afdeling Financiën alleen toegang kan krijgen tot zakelijke e-mail van ingeschreven apparaten die aan het nalevingsbeleid voldoen.

Het beveiligen van toegang tot bedrijfsbronnen is de eerste stap in de bescherming van bedrijfsgegevens. U moet de gegevens nog steeds kunnen beveiligen nadat deze zijn geopend op het apparaat. De gegevens kunnen nu worden gekopieerd, verplaatst, opgeslagen op een andere locatie of gedeeld. Intune lost dit probleem op door u de mogelijkheid te bieden het verplaatsen van gegevens te beperken door regels te maken, zoals:
- Kopiëren en plakken blokkeren of verhinderen dat gegevens worden overgebracht buiten de context van het werk.
- Voorkomen dat er back-ups worden gemaakt naar persoonlijke cloudopslagruimte, Opslaan als voorkomen.
- Beveiligen van de toegang tot apps door een pincode/wachtwoordcode of zakelijke referenties verplicht te stellen.
- Alle webkoppelingen openen in de Intune Managed Browser.

Deze reeks regels wordt aangeduid als [beleid voor Mobile App Management (MAM)](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).  MAM-beleid kan worden toegepast op apps die worden uitgevoerd op apparaten die al dan niet door u worden beheerd.  

U kunt uw bedrijfsgegevens beveiligen door MAM-beleid te gebruiken voor apparaten die zijn **ingeschreven bij Intune**, voor apparaten die zijn **ingeschreven en worden beheerd door een MDM van derden**, en voor apparaten die **in een MDM-oplossing zijn ingeschreven**, zoals de apparaten van werknemers.

Als u een app wilt koppelen aan MAM-beleid, moet de app gebruikmaken van de Microsoft Intune App Software Development Kit (SDK) of de App Wrapping Tool.

Bij apps als de Microsoft Office-apps is de SDK al ingebouwd. U vindt de volledige lijst met ondersteunde apps in de [Galerie met mobiele toepassingen van Microsoft Intune](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) op de pagina voor Microsoft Intune-toepassingen van partners. Selecteer een app om de ondersteunde scenario's en platforms te bekijken en om te controleren of de app meerdere identiteiten ondersteunt.

U kunt ook [uw op maat gemaakte line-of-business-apps inschakelen](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md) voor gebruik met MAM-beleid.

Naast het beperken van gegevensverplaatsing kunt u, wanneer een apparaat is zoekgeraakt of gestolen, of als de gebruiker niet meer bij uw bedrijf werkt, [selectief bedrijfsgegevens wissen](wipe-managed-company-app-data-with-microsoft-intune.md) en alleen persoonlijke gegevens behouden.



<!--HONumber=Jul16_HO5-->


