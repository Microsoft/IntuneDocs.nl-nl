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
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: 92e07a49205ffaf287fc3aa2da6a6376b75fda4f
ms.lasthandoff: 04/24/2017


---


# <a name="introduction-to-microsoft-intune-in-the-azure-portal-preview"></a>Inleiding op Microsoft Intune in de preview-versie van Azure Portal


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Microsoft Intune wordt verplaatst naar de Azure Portal. Dit betekent dat de werkstromen en functionaliteit waarmee u bekend bent, zullen veranderen.
De nieuwe portal biedt u een preview-versie van de nieuwe en bijgewerkte functionaliteit in Azure Portal waar u de mobiele apparaten, pc's en apps van uw bedrijf kunt beheren.
Uiteindelijk wordt alle functionaliteit van Intune naar Azure verplaatst, maar momenteel kunt u al veel Intune-taken in Azure Portal uitvoeren. Omdat het nog om een preview-versie gaat, is bepaalde functionaliteit nog niet aanwezig in de portal. Zie de sectie [Wat is er nieuw](#what's-new) voor meer informatie.

> [!IMPORTANT]
> **Ziet u de nieuwe portal nog niet?**<br>
> We zijn al begonnen met de implementatie van de preview-versie om tenants te selecteren. Bestaande tenants worden vanaf begin van het kalenderjaar 2017 gemigreerd. U ontvangt een melding in het Office Message Center vóór de migratie van uw tenant.


In deze bibliotheek vindt u nieuwe productdocumentatie. Deze wordt tijdens de preview-versie voortdurend bijgewerkt. Als u suggesties hebt, kunt u feedback geven in de opmerkingen bij onderwerpen. We graag horen van u.

<!--- You can view the new Intune technical preview console in Azure at [portal.azure.com]. --->

Belangrijke functies van de nieuwe omgeving zijn onder andere:

- Een geïntegreerde console voor al uw Enterprise Mobility + Security-onderdelen (EMS)
- Een console op basis van HTML die is gebouwd op webstandaarden
- Ondersteuning van Microsoft Graph API om veel acties te automatiseren
- Azure Active Directory-groepen (AD) voor compatibiliteit voor al uw Azure-toepassingen
- Ondersteuning voor de meeste moderne webbrowsers

Zie [de Intune-documentatiebibliotheek](https://docs.microsoft.com/en-us/intune/) voor documentatie over de klassieke Intune-console.

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
Deze sectie bevat informatie over [wat er nieuw is](/intune-azure/introduction/whats-new), [bekende problemen](/intune-azure/introduction/known-issues-in-the-intune-preview), [ondersteuning krijgen](/intune-azure/introduction/how-to-get-support-for-microsoft-intune) en hoe u [aan de slag kunt met een gratis proefversie](/intune-azure/introduction/sign-up-free-trial-microsoft-intune) van Intune.
### <a name="plan-and-design"></a>Plannen en ontwerpen
Informatie over het [plannen en ontwerpen](/intune-azure/plan-and-design/get-started) van uw Intune-omgeving.
### <a name="device-enrollment"></a>Apparaatinschrijving
[Uw apparaten laten beheren door Intune](/intune-azure/enroll-devices/what-is).
### <a name="device-compliance"></a>Apparaatcompatibiliteit
[Een nalevingsniveau voor uw apparaten definiëren en vervolgens rapporteren over apparaten die niet hieraan voldoen](/intune-azure/set-device-compliance/what-is-device-compliance).
### <a name="device-configuration"></a>Apparaatconfiguratie
[Begrijpen welke profielen u kunt gebruiken om instellingen en functies te configureren op apparaten die u beheert](/intune-azure/configure-devices/what-are-device-profiles).
### <a name="devices"></a>Apparaten
[Meer informatie over de apparaten die u met inventaris en rapporten beheert](/intune-azure/manage-devices/what-is).
### <a name="mobile-apps"></a>Mobiele apps
[Apps publiceren, beheren, configureren en beveiligen](/intune-azure/manage-apps/what-is-app-management).
### <a name="conditional-access"></a>Voorwaardelijke toegang
[De toegang tot Exchange-services beperken op basis van voorwaarden die u hebt opgegeven](/intune-azure/conditional-access/what-is-conditional-access).
### <a name="on-premises-access"></a>Lokale toegang
[Toegang tot Exchange ActiveSync en Exchange on-premises configureren](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune)
### <a name="users"></a>Users
[Meer informatie over de gebruikers van apparaten die u beheert en bronnen in groepen sorteren](/intune-azure/manage-users/what-is).
### <a name="groups"></a>Groepen
[Meer informatie over het gebruik van Azure Active Directory-groepen met Intune](/intune-azure/manage-users/get-started-with-groups)
### <a name="intune-roles"></a>Intune-rollen
[Bepalen welke personen verschillende Intune-acties kunnen uitvoeren en op welke personen deze acties van toepassing zijn](/intune-azure/access-control/role-based-access-control). U kunt de ingebouwde rollen gebruiken die voorzien in bepaalde algemene Intune-scenario's of u kunt uw eigen rollen maken.
### <a name="software-updates"></a>Software-updates
[Meer informatie over de configuratie van software-updates voor Windows 10-apparaten](/intune-azure/configure-devices/how-to-configure-windows-update-for-business).



## <a name="whats-new"></a>Wat is er nieuw?

[Ontdek wat er nieuw is in de preview-versie](/intune-azure/introduction/whats-new).

