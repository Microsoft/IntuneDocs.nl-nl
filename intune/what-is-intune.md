---
title: Inleiding tot Intune in de preview-versie van Azure Portal
titleSuffix: Intune Azure preview
description: 'Preview-versie van Intune Azure: een overzicht van de basisbeginselen van Intune in de preview-versie van Azure Portal en hoe u hiermee uw apparaten kunt beheren.'
keywords: 
author: robstackmsft
ms.author: robstack
nmanager: angrobe
ms.date: 04/24/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 16d7ff50eb821e0927c3c6ea21f3cdb1257762a0
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---


# <a name="introduction-to-microsoft-intune-in-the-azure-portal-preview"></a>Inleiding op Microsoft Intune in de preview-versie van Azure Portal


[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Microsoft Intune wordt verplaatst naar de Azure Portal. Dit betekent dat de werkstromen en functionaliteit waarmee u bekend bent, zullen veranderen.
De nieuwe portal biedt u een preview-versie van de nieuwe en bijgewerkte functionaliteit in Azure Portal waar u de mobiele apparaten, pc's en apps van uw bedrijf kunt beheren.
Uiteindelijk wordt alle functionaliteit van Intune naar Azure verplaatst, maar momenteel kunt u al veel Intune-taken in Azure Portal uitvoeren. Omdat het nog om een preview-versie gaat, is bepaalde functionaliteit nog niet aanwezig in de portal. Zie de sectie [Wat is er nieuw](#whats-new) voor meer informatie.

> [!IMPORTANT]
> **Ziet u de nieuwe portal nog niet?**<br>
> We zijn al begonnen met de implementatie van de preview-versie om tenants te selecteren. Bestaande tenants worden vanaf begin van het kalenderjaar 2017 gemigreerd. U ontvangt een melding in het Office Message Center vóór de migratie van uw tenant.
>
> Intune-accounts die vóór januari 2017 zijn gemaakt, moeten eenmalig worden gemigreerd om de Apple-registratiewerkstromen in Azure beschikbaar te maken. De planning voor de migratie is nog niet aangekondigd, maar de informatie wordt zo snel mogelijk beschikbaar gemaakt. Het wordt aangeraden om een testaccount te maken om de nieuwe ervaring te testen, als u met uw bestaande account geen toegang hebt tot de preview.


In deze bibliotheek vindt u nieuwe productdocumentatie. Deze wordt tijdens de preview-versie voortdurend bijgewerkt. Als u suggesties hebt, kunt u feedback geven in de opmerkingen bij onderwerpen. We graag horen van u.

<!--- You can view the new Intune technical preview console in Azure at [portal.azure.com]. --->

Belangrijke functies van de nieuwe omgeving zijn onder andere:

- Een geïntegreerde console voor al uw Enterprise Mobility + Security-onderdelen (EMS)
- Een console op basis van HTML die is gebouwd op webstandaarden
- Ondersteuning van Microsoft Graph API om veel acties te automatiseren
- Azure Active Directory-groepen (AD) voor compatibiliteit voor al uw Azure-toepassingen
- Ondersteuning voor de meeste moderne webbrowsers

Zie [de Intune-documentatiebibliotheek](https://docs.microsoft.com/intune-classic/) voor documentatie over de klassieke Intune-console.

## <a name="before-you-start"></a>Voordat u begint

U moet een Intune-beheerder- en tenant-account hebben voor het gebruik van Intune in de Azure Portal. [Meld u aan voor een account](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) als u er nog geen hebt.

## <a name="supported-web-browsers-for-the-azure-portal"></a>Ondersteunde webbrowsers voor de Azure Portal

Azure Portal is geschikt voor de meeste moderne pc's, Macs en tablets. Mobiele telefoons worden niet ondersteund.
Momenteel worden de volgende webbrowsers ondersteund:

- Microsoft Edge (meest recente versie)
- Microsoft Internet Explorer 11
- Safari (meest recente versie, alleen Mac)
- Chrome (meest recente versie)
- Firefox (meest recente versie)

Controleer [Azure Portal](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices) voor de meest recente informatie over ondersteunde browsers.

## <a name="whats-in-this-library"></a>Wat bevat deze bibliotheek?

De documentatie volgt de indeling van de Intune-portal, zodat u snel de gewenste informatie vindt.

![Workloads in de Azure Portal](./media/azure-portal-workloads.png)

### <a name="introduction-and-get-started"></a>Inleiding en aan de slag
Deze sectie bevat informatie over [wat er nieuw is](whats-new.md), [bekende problemen](known-issues.md), [ondersteuning krijgen](get-support.md) en hoe u [aan de slag kunt met een gratis proefversie](free-trial-sign-up.md) van Intune.
### <a name="plan-and-design"></a>Plannen en ontwerpen
Informatie over het [plannen en ontwerpen](/intune-classic/plan-and-design/introduction) van uw Intune-omgeving.
### <a name="device-enrollment"></a>Apparaatinschrijving
[Uw apparaten laten beheren door Intune](device-enrollment.md).
### <a name="device-compliance"></a>Apparaatcompatibiliteit
[Een nalevingsniveau voor uw apparaten definiëren en vervolgens rapporteren over apparaten die niet hieraan voldoen](device-compliance.md).
### <a name="device-configuration"></a>Apparaatconfiguratie
[Begrijpen welke profielen u kunt gebruiken om instellingen en functies te configureren op apparaten die u beheert](device-profiles.md).
### <a name="devices"></a>Apparaten
[Meer informatie over de apparaten die u met inventaris en rapporten beheert](device-management.md).
### <a name="mobile-apps"></a>Mobiele apps
[Apps publiceren, beheren, configureren en beveiligen](app-management.md).
### <a name="conditional-access"></a>Voorwaardelijke toegang
[De toegang tot Exchange-services beperken op basis van voorwaarden die u hebt opgegeven](conditional-access.md).
### <a name="on-premises-access"></a>Lokale toegang
[Toegang tot Exchange ActiveSync en Exchange on-premises configureren](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune)
### <a name="users"></a>Users
[Meer informatie over de gebruikers van apparaten die u beheert en bronnen in groepen sorteren](user-management.md).
### <a name="groups"></a>Groepen
[Meer informatie over het gebruik van Azure Active Directory-groepen met Intune](groups-get-started.md)
### <a name="intune-roles"></a>Intune-rollen
[Bepalen welke personen verschillende Intune-acties kunnen uitvoeren en op welke personen deze acties van toepassing zijn](role-based-access-control.md). U kunt de ingebouwde rollen gebruiken die voorzien in bepaalde algemene Intune-scenario's of u kunt uw eigen rollen maken.
### <a name="software-updates"></a>Software-updates
[Meer informatie over de configuratie van software-updates voor Windows 10-apparaten](windows-update-for-business-configure.md).



## <a name="whats-new"></a>Wat is er nieuw?

[Ontdek wat er nieuw is in de preview-versie](whats-new.md).

