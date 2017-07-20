---
title: Intune-onboarding
description: Dit artikel helpt u bij het bepalen van alle aspecten die moeten worden overwogen bij de onboarding van een cloudoplossing met Intune in uw omgeving.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac7bd764-5365-4920-8fd0-ea57d5ebe039
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 71558786cc7f058cee31e9bbe3960ed75a76891b
ms.sourcegitcommit: ce363409d1206e4a3d669709863ccc9eb22b7d5f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/11/2017
---
# <a name="implement-your-intune-plan"></a>Uw Intune-abonnement implementeren

Tijdens de onboardingfase implementeert u Intune in uw productieomgeving. Het implementatieproces bestaat uit het installeren en configureren van Intune en externe afhankelijkheden (indien nodig) op basis van uw [use-casevereisten](planning-guide-requirements.md).

De volgende sectie biedt een overzicht van het implementatieproces voor Intune met vereisten en taken op hoog niveau.

## <a name="intune-requirements"></a>Vereisten voor Intune

De belangrijkste vereisten voor de zelfstandige versie van Intune zijn:

-   Enterprise Mobility + Security (EMS)/Intune-abonnement

-   Office 365-abonnement (voor Office-apps en door MAM-beleid beheerde apps)

-   Apple APNs-certificaat (voor het beheer van het iOS-apparaatplatform)

-   Azure AD Connect (voor adreslijstsynchronisatie)

-   Intune On-Premises Connector voor Exchange (voor voorwaardelijke toegang voor Exchange On-Premises, indien nodig)

-   Intune Certificate Connector (voor implementatie van SCEP-certificaten, indien nodig)

>[!TIP]
> Overzicht van de [ondersteunde apparaten](supported-devices-browsers.md) voor een volledige lijst met apparaten die u met Intune kunt beheren.

## <a name="intune-implementation-process"></a>Proces van Intune-implementatie

We hebben 13 verschillende taken voor het implementeren van een Intune-implementatie geïdentificeerd. Afhankelijk van uw zakelijke vereisten, de bestaande infrastructuur en de strategie voor het beheer van apparaten, zijn sommige van deze taken mogelijk al voltooid. Anderen zijn mogelijk niet van toepassing op uw abonnement.

### <a name="task-1-get-an-intune-subscription"></a>Taak1: een Intune-abonnement kopen

Zoals hierboven aangegeven in de sectie met Intune-vereisten, moet u een EMS- of Intune-abonnement hebben. Als uw organisatie dat niet heeft, kunt u contact opnemen met Microsoft of uw Microsoft-accountteam om aan te geven dat u de aanschaf van Enterprise Mobility + Security (EMS) of Intune overweegt.

-   Meer informatie over [het kopen van Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-pricing).

### <a name="task-2-add-office-365-subscription"></a>Taak 2: Office 365-abonnement toevoegen

Deze stap is optioneel. U moet een Office 365-abonnement hebben als u van plan bent Exchange Online te gebruiken en mobiele Office-apps te beheren met app-beveiligingsbeleid. Als uw organisatie geen Office 365-abonnement heeft, kunt u contact opnemen met Microsoft of uw Microsoft-accountteam om aan te geven dat u de aanschaf van Office 365 overweegt.

-   Meer informatie over [het kopen van Office 365](https://products.office.com/business/compare-office-365-for-business-plans).

### <a name="task-3-add-users-groups-in-azure-ad"></a>Taak 3: Gebruikersgroepen toevoegen in Azure AD

Wellicht moet u gebruikers of beveiligingsgroepen toevoegen in Active Directory of Azure Active Directory op basis van de use-casescenario's en -vereisten voor uw Intune-implementatie. Controleer uw huidige gebruikers en beveiligingsgroepen in Active Directory of Azure Active Directory om te bepalen of ze volledig voldoen aan uw behoeften. Wanneer u nieuwe gebruikers en beveiligingsgroepen toevoegt, raden we aan deze toe te voegen in Active Directory en te synchroniseren met Azure Active Directory met behulp van Azure AD Connect.


-   Meer informatie over [gebruikers/groepen toevoegen aan Intune](users-permissions-add.md).
<!---why not send them to the AAD connect topic? Question out to Andre: https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect--->



### <a name="task-4-assign-intune-and-office-365-user-licenses"></a>Taak 4: Intune- en Office 365-gebruikerslicenties toewijzen

Alle gebruikers voor wie de rollout van EMS/Intune en Office 365 is bedoeld, moeten beschikken over een licentie die aan hen is toegewezen. U kunt de toewijzing van EMS/Intune- en Office 365-licenties uitvoeren in de portal van het Office 365-beheercentrum.

-   Meer informatie over [het toewijzen van Intune-licenties](licenses-assign.md).

### <a name="task-5-set-mobile-device-management-authority-to-intune"></a>Taak 5: De instantie voor het beheer van mobiele apparaten instellen op Intune

Voordat u apparaten kunt installeren, configureren, beheren en registreren met behulp van Intune, moet u de instantie voor het beheer van mobiele apparaten instellen op Intune.

-   Meer informatie over [de instantie voor het beheer van mobiele apparaten instellen op Intune](mdm-authority-set.md).

### <a name="task-6-enable-device-platforms"></a>Taak 6: Platformen voor apparaten inschakelen

De meeste apparaatplatformen zijn standaard ingeschakeld, met uitzondering van Apple-apparaten (iOS en Mac). Voordat iOS-apparaten kunnen worden geregistreerd en beheerd in Intune, moet u het apparaatplatform inschakelen. Om dit te doen, moet u een Push-MDM-certificaat maken en dit toevoegen aan Intune.

-   Meer informatie over [registratie voor Apple-apparaten inschakelen](apple-mdm-push-certificate-get.md).

### <a name="task-7-add-and-deploy-terms-and-conditions-policies"></a>Taak 7: Voorwaardenbeleid toevoegen en implementeren

Intune ondersteunt beleidsregels voor voorwaarden. Voeg waar nodig voorwaardenbeleid toe en implementeer dit voor doelgroepen op basis van de use cases en vereisten van uw Intune-implementatie.

-   Meer informatie over [het toevoegen en implementeren van voorwaardenbeleid](terms-and-conditions-create.md).

### <a name="task-8-add-and-deploy-configuration-policies"></a>Taak 8: Configuratiebeleid toevoegen en implementeren

Intune ondersteunt twee typen configuratiebeleid: algemeen en aangepast. Voeg waar nodig configuratiebeleid toe en implementeer dit voor doelgroepen op basis van de use cases en vereisten van uw Intune-implementatie.

-   Meer informatie over [het toevoegen en implementeren van configuratiebeleid](device-profiles.md).

### <a name="task-9-add-and-deploy-resource-profiles"></a>Taak 9: Resourceprofielen toevoegen en implementeren

Intune biedt ondersteuning voor e-mail, wifi en VPN-profielen. Voeg waar nodig deze profielen toe en implementeer deze voor doelgroepen op basis van de use cases en vereisten van uw Intune-implementatie.

-   Meer informatie over [toegang tot bedrijfsbronnen inschakelen met Intune](device-profiles.md).

### <a name="task-10-add-and-deploy-apps"></a>Taak 10: Apps toevoegen en implementeren

Intune biedt ondersteuning voor de implementatie van web-, bedrijfstakgerichte en openbare store-apps. U kunt ook apps beheren waarin de Intune SDK is geïntegreerd door deze te koppelen aan MAM-beleid. Voeg waar nodig apps toe en implementeer deze voor doelgroepen op basis van de use cases en vereisten van uw Intune-implementatie.

-   Meer informatie over [apps toevoegen en implementeren](app-management.md).

### <a name="task-11-add-and-deploy-compliance-policies"></a>Taak 11: Nalevingsbeleid toevoegen en implementeren

Intune ondersteunt nalevingsbeleid. Voeg waar nodig nalevingsbeleid toe en implementeer dit voor doelgroepen op basis van de use cases en vereisten van uw Intune-implementatie.

-   Meer informatie over [nalevingsbeleid](device-compliance.md).

### <a name="task-12-enable-conditional-access-policies"></a>Taak 12: Beleid voor voorwaardelijke toegang inschakelen

Intune biedt ondersteuning voor voorwaardelijke toegang voor Exchange Online, Exchange on-premises, SharePoint Online, Skype voor Bedrijven Online en Dynamics CRM Online. U kunt voorwaardelijke toegang inschakelen en configureren op basis van de use cases en vereisten van uw Intune-implementatie.

-   Meer informatie over [voorwaardelijke toegang](conditional-access.md).

### <a name="task-13-enroll-devices"></a>Taak 13: Apparaten registreren

Intune ondersteunt platformen voor iOS-, Mac OS-, Android-, Windows- en Windows Mobile-apparaten. Registreer platformen voor mobiele apparaten waar nodig op basis van de use cases en vereisten van uw Intune-implementatie.

-   Meer informatie over [het registreren van apparaten](device-enrollment.md).


## <a name="next-steps"></a>Volgende stappen

Bekijk deze [sessiemodule van Microsoft Virtual Academy Intune](https://mva.microsoft.com/en-US/training-courses/deploying-microsoft-enterprise-mobility-suite-16408) voor meer informatie over het implementatieproces van Intune.


Meer informatie over het [testen en valideren van uw Intune-implementatie](planning-guide-test-validation.md).
