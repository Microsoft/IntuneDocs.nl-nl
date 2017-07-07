---
title: Intune-onboarding
description: Dit artikel helpt u bij het bepalen van alle aspecten die moeten worden overwogen bij de onboarding van een cloudoplossing met Intune in uw omgeving.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac7bd764-5365-4920-8fd0-ea57d5ebe039
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ade7caf544d71c062c0fa251d7a113facb700a36
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="intune-implementation"></a>Intune-implementatie

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Tijdens de onboardingfase implementeert u Intune in uw productieomgeving. Het implementatieproces bestaat uit het installeren en configureren van Intune en externe afhankelijkheden (indien nodig) op basis van uw [use-casevereisten](planning-guide-requirements.md) die in eerdere secties van deze handleiding zijn besproken.

De volgende sectie biedt een overzicht van het implementatieproces voor Intune met vereisten en taken op hoog niveau.

>[!TIP]
> Ga naar [Aanvullende bronnen](planning-guide-resources.md) voor meer informatie over het implementatieproces van Intune.

## <a name="intune-requirements"></a>Vereisten voor Intune

Hieronder vindt u de belangrijkste vereisten voor de zelfstandige versie van Intune:

-   EMS/Intune-abonnement

-   Office 365-abonnement (voor Office-apps en door MAM-beleid beheerde apps)

-   Apple APNs-certificaat (voor het beheer van het iOS-apparaatplatform)

-   Azure AD Connect (voor adreslijstsynchronisatie)

-   Intune On-Premises Connector voor Exchange (voor CA voor Exchange On-Premises, indien nodig)

-   Intune Certificate Connector (voor implementatie van SCEP-certificaten, indien nodig)

>[!TIP]
> U kunt [hier](/intune/supported-devices-browsers) meer informatie vinden over de vereisten voor de zelfstandige versie van Intune.

## <a name="intune-implementation-process"></a>Proces van Intune-implementatie

### <a name="overview-of-implementation-tasks"></a>Overzicht van implementatietaken

Hier ziet u een overzicht van de afzonderlijke taken bij het implementeren van Intune.

#### <a name="task-1-add-intune-subscription"></a>Taak 1: Intune-abonnement toevoegen

Zoals vermeld in de vorige sectie over vereisten, is er een EMS- of Intune-abonnement vereist. Als uw organisatie geen EMS- of Intune-abonnement heeft, kunt u contact opnemen met Microsoft of uw Microsoft-accountteam om aan te geven dat u de aanschaf van Enterprise Mobility + Security (EMS) of Intune overweegt.

-   Meer informatie over [het kopen van Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-pricing).

#### <a name="task-2-add-office-365-subscription"></a>Taak 2: Office 365-abonnement toevoegen

Deze stap is optioneel. Zoals vermeld in de vorige sectie over vereisten, hebt u een Office 365-abonnement nodig als u Exchange Online wilt gaan gebruiken en mobiele Office-apps wilt beheren met MAM-beleid. Als uw organisatie geen Office 365-abonnement heeft, kunt u contact opnemen met Microsoft of uw Microsoft-accountteam om aan te geven dat u de aanschaf van Office 365 overweegt.

-   Meer informatie over [het kopen van Office 365](https://products.office.com/business/compare-office-365-for-business-plans).

#### <a name="task-3-add-users-groups-in-azure-ad"></a>Taak 3: Gebruikersgroepen toevoegen in Azure AD

Wellicht moet u gebruikers of beveiligingsgroepen toevoegen in AD of AAD op basis van de use-casescenario's en vereisten voor uw Intune-implementatie. Controleer uw huidige gebruikers en beveiligingsgroepen in Active Directory of Azure Active Directory om te bepalen of ze volledig voldoen aan uw behoeften. Nieuwe gebruikers en beveiligingsgroepen worden meestal toegevoegd in Active Directory en gesynchroniseerd met Azure Active Directory via Azure AD Directory Connect.

-   Meer informatie over [gebruikers/groepen toevoegen aan Intune](users-permissions-add.md).

#### <a name="task-4-assign-intune-and-office-365-user-licenses"></a>Taak 4: Intune- en Office 365-gebruikerslicenties toewijzen

Alle gebruikers voor wie de rollout van EMS/Intune en Office 365 is bedoeld, moeten beschikken over een licentie die aan hen is toegewezen. De toewijzing van EMS/Intune- en Office 365-licenties kan worden uitgevoerd in de portal van het Office 365-beheercentrum.

-   Meer informatie over [het toewijzen van Intune-licenties](licenses-assign.md).

#### <a name="task-5-set-mobile-device-management-authority-to-intune"></a>Taak 5: De instantie voor het beheer van mobiele apparaten instellen op Intune

Voordat u apparaten kunt installeren, configureren, beheren en registreren met behulp van Intune, moet u de instantie voor het beheer van mobiele apparaten instellen op Intune. het instellen van de instantie voor het beheer van mobiele apparaten wordt uitgevoerd in de Intune-beheerportal, werkruimte Beheer.

-   Meer informatie over [het instellen van de instantie voor het beheer van mobiele apparaten](/intune-classic/deploy-use/prerequisites-for-enrollment#step-2-set-mdm-authority).

#### <a name="task-6-enable-device-platforms"></a>Taak 6: Platformen voor apparaten inschakelen

In de Intune-beheerconsole zijn de meeste apparaatplatformen standaard ingeschakeld, met uitzondering van Apple-apparaten (iOS en Mac). Voordat iOS-apparaten kunnen worden geregistreerd en beheerd in Intune, moet u het apparaatplatform inschakelen. Het inschakelen van het platform voor iOS-apparaten bestaat uit drie stappen: het APNs-certificaat maken en downloaden en het APNs-certificaat uploaden naar Intune.

-   Meer informatie over [hoe het instellen van iOS- en Mac-apparaatbeheer werkt.](/intune-classic/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)

#### <a name="task-7-add-and-deploy-terms-and-conditions-policies"></a>Taak 7: Voorwaardenbeleid toevoegen en implementeren

Microsoft Intune ondersteunt het toevoegen en implementeren van voorwaardenbeleid. Het toevoegen en implementeren van voorwaardenbeleid wordt uitgevoerd in de Intune-beheerportal, werkruimte Beleid. Voeg waar nodig voorwaardenbeleid toe en implementeer dit voor doelgroepen op basis van de use cases en vereisten van uw Intune-implementatie.

-   Meer informatie over [het toevoegen en implementeren van voorwaardenbeleid](/intune-classic/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune).

#### <a name="task-8-add-and-deploy-configuration-policies"></a>Taak 8: Configuratiebeleid toevoegen en implementeren

Microsoft Intune biedt ondersteuning voor het toevoegen en implementeren van twee typen configuratiebeleid: algemeen en aangepast. Het toevoegen en implementeren van configuratiebeleid wordt uitgevoerd in de Intune-beheerportal, werkruimte Beleid. Voeg waar nodig configuratiebeleid toe en implementeer dit voor doelgroepen op basis van de use cases en vereisten van uw Intune-implementatie.

-   Meer informatie over [het toevoegen en implementeren van configuratiebeleid](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies).

#### <a name="task-9-add-and-deploy-resource-profiles"></a>Taak 9: Resourceprofielen toevoegen en implementeren

Microsoft Intune biedt ondersteuning voor e-mail-, Wi-Fi- en VPN-profielen. Het toevoegen en implementeren van profielen wordt uitgevoerd in de Intune-beheerportal, werkruimte Beleid. Voeg waar nodig e-mail-, Wi-Fi- en VPN-profielen toe en implementeer deze voor doelgroepen op basis van de use cases en vereisten van uw Intune-implementatie.

-   Meer informatie over [toegang tot bedrijfsbronnen inschakelen met Intune](/intune-classic/deploy-use/enable-access-to-company-resources-with-microsoft-intune).

#### <a name="task-10-add-and-deploy-apps"></a>Taak 10: Apps toevoegen en implementeren

Microsoft Intune biedt ondersteuning voor de implementatie van Web-, LOB- en openbare store-apps. Bovendien wordt het beheer ondersteund van apps waarin de Intune SDK is geïntegreerd door deze te koppelen aan MAM-beleid. Het toevoegen en implementeren van apps wordt uitgevoerd in de Intune-beheerportal, werkruimte App. Het toevoegen van MAM-beleid apps wordt uitgevoerd in de Intune-beheerportal, werkruimte Beleid. Voeg waar nodig apps toe en implementeer deze voor doelgroepen op basis van de use cases en vereisten van uw Intune-implementatie.

-   Meer informatie over [toevoegen en implementeren van toepassingen](/intune-classic/deploy-use/deploy-apps).

#### <a name="task-11-add-and-deploy-compliance-policies"></a>Taak 11: Nalevingsbeleid toevoegen en implementeren

Microsoft Intune ondersteunt nalevingsbeleid. Het toevoegen en implementeren van nalevingsbeleid wordt uitgevoerd in de Intune-beheerportal, werkruimte Beleid. Voeg waar nodig nalevingsbeleid toe en implementeer dit voor doelgroepen op basis van de use cases en vereisten van uw Intune-implementatie.

-   Meer informatie over [nalevingsbeleid](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune).

#### <a name="task-12-enable-conditional-access-policies"></a>Taak 12: Beleid voor voorwaardelijke toegang inschakelen

Microsoft Intune biedt ondersteuning voor voorwaardelijke toegang voor Exchange Online en On-premises, SharePoint Online, Skype voor Bedrijven Online en Dynamics CRM Online. U kunt beleid voor voorwaardelijke toegang inschakelen in de Intune-beheerportal, werkruimte Beleid. U kunt voorwaardelijke toegang inschakelen en configureren op basis van de [use cases en vereisten van uw Intune-implementatie](planning-guide-requirements.md).

-   Meer informatie over [voorwaardelijke toegang](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).

#### <a name="task-13-enroll-devices"></a>Taak 13: Apparaten registreren

Intune ondersteunt platformen voor mobiele iOS-, Mac OS-, Android-, Windows- en Windows Mobile-apparaten. Registreer platformen voor mobiele apparaten waar nodig op basis van de use cases en vereisten van uw Intune-implementatie.

-   Meer informatie over [het registreren van apparaten](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune).

>[!TIP]
> Bekijk deze [sessiemodule van Microsoft Virtual Academy Intune](https://mva.microsoft.com/training-courses/deploying-microsoft-enterprise-mobility-suite-16408?l=PPWNoZxvD_1404778676) voor meer informatie over het implementatieproces van Intune.

## <a name="next-section"></a>Volgende sectie

De volgende sectie bevat richtlijnen over het [testen en valideren van uw Intune-implementatie](planning-guide-test-validation.md).
