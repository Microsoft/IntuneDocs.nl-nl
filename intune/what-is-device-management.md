---
title: Apparaatbeheer in Microsoft 365
description: Microsoft 365 Enterprise bevat Microsoft Intune. Bekijk hoe op welke manier Intune Mobile Device Management en Mobile Application Management biedt voor uw organisatie. Lees algemene scenario's en gebruik Intune om Microsoft 365 in uw omgeving te implementeren.
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/22/2019
ms.topic: conceptual
audience: ITPro
ms.service: microsoft-intune
ms.technology: ''
ms.custom: intune
ms.assetid: 0649d310-43a7-4b01-85d2-da255d03e1da
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5be25e9ab88f4dd44399d6ddc37cfc25955475ba
ms.sourcegitcommit: 614c4c36cfe544569db998e17e29feeaefbb7a2e
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 07/24/2019
ms.locfileid: "68427313"
---
# <a name="what-is-device-management"></a>Wat is apparaatbeheer? 

Beheerders hebben de belangrijke taak om de resources en gegevens van en organisatie te beschermen en beveiligen. Dit heet *apparaatbeheer*. Gebruikers hebben veel apparaten waarop ze persoonlijke bestanden openen en delen, websites bezoeken en apps en games installeren. Diezelfde gebruikers zijn ook werknemers en studenten. Ze willen hun apparaten gebruiken om werk- en schoolresources te openen, zoals e-mail en OneNote. Met apparaatbeheer kunnen organisaties hun resources en gegevens beschermen en beveiligen. 

Met een apparaatbeheerprovider kunnen organisaties ervoor zorgen dat alleen gemachtigde personen en apparaten toegang krijgen tot vertrouwelijke informatie. Op vergelijkbare manier kunnen apparaatgebruikers met een gerust hart gegevens op hun telefoon openen, omdat ze weten dat hun apparaat voldoet aan de beveiligingsvereisten van de organisatie. Als organisatie vraagt u zich misschien af **wat er moet worden gebruikt om de resources te beschermen.**

Het antwoord is [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune). Intune biedt mogelijkheden voor Mobile Device Management (MDM) en Mobile Application Management (MAM). MDM- en MAM-oplossingen worden voor de volgende belangrijke zaken gebruikt:

- Ondersteuning bieden voor een diverse mobiele omgeving en iOS-, Android-, Windows- en macOS-apparaten veilig beheren.
- Ervoor zorgen dat apparaten en apps voldoen aan de beveiligingsvereisten van uw organisatie.
- Beleidsregels maken om de gegevens van uw organisatie te beveiligen op apparaten van het bedrijf en persoonlijke apparaten.
- Eén uniforme mobiele oplossing gebruiken om dit beleid af te dwingen en helpen bij het beheren van apparaten, apps, gebruikers en groepen.

Intune maakt deel uit van Microsoft 365 en kan worden geïntegreerd in Azure Active Directory (Azure AD). Met Azure AD kunt u bepalen wie er toegang krijgt en waartoe deze personen toegang krijgen.

## <a name="hello-intune"></a>Hallo Intune!
Veel organisaties, zoals Microsoft zelf, maken gebruik van Intune om eigen gegevens te beveiligen waarvan gebruikers gebruikmaken op bedrijfs- en persoonlijke mobiele apparaten. Intune bevat configuratiebeleid voor apparaten en apps, software-updatebeleid en installatiestatussen (grafieken, tabellen en rapporten) zodat u de toegang tot gegevens kunt beveiligen en bewaken.

Het is gebruikelijk dat mensen meerdere apparaten hebben waarop gebruik wordt gemaakt van verschillende platforms. Mogelijk gebruikt een werknemer bijvoorbeeld Surface Pro voor het werk en een mobiel Android-apparaat voor privézaken. Het is ook gebruikelijk dat mensen bedrijfsresources, zoals Microsoft Outlook en SharePoint, gebruikt vanaf meerdere apparaten.

Met Intune kunt u meerdere apparaten voor één persoon beheren. Het is daarbij geen probleem als er verschillende platforms op de apparaten worden gebruikt, zoals iOS, macOS, Android en Windows. Beleidsregels en instellingen worden in Intune gescheiden per apparaatplatform. Hierdoor is het eenvoudig om apparaten van een specifiek platform te beheren en te bekijken.

**[Veelvoorkomende scenario's](https://docs.microsoft.com/intune/common-scenarios)** is een uitstekende resource om te ontdekken hoe Intune met bepaalde kwesties omgaat ten aanzien van mobiele apparaten. Er zijn scenario's te vinden over:  
- E-mail beveiligen met on-premises Exchange
- Office 365 veilig gebruiken
- Persoonlijke apparaten gebruiken voor toegang tot bedrijfsresources

## <a name="integration-with-secure-and-protect-services"></a>Integratie met services beveiligen en beschermen
Het is een belangrijke taak van elke apparaatbeheeroplossing om beveiliging en bescherming te bieden. Intune kan hiervoor uitstekend worden geïntegreerd in andere services. Bijvoorbeeld:

- **Microsoft 365** is belangrijk bij het vereenvoudigen van vaak uitgevoerde IT-taken. In het beheercentrum van Microsoft 365 kunt u gebruikers maken en groepen beheren. Ook krijgt u toegang tot andere services, zoals Intune, Microsoft Azure AD en meer. 

  U kunt bijvoorbeeld een iOS-apparaatgroep maken in Microsoft 365. Gebruik vervolgens Intune om beleid naar een iOS-apparaatgroep te pushen waarin de focus ligt op iOS-gerelateerde zaken, zoals toegang tot de App Store, gebruikmaken van AirDrop, back-ups maken in iCloud, gebruikmaken van het webfilter van Apple en meer.

- **Windows Defender** bevat veel beveiligingsfuncties ter bescherming van Windows 10-apparaten. Als u Intune en Windows Defender samen gebruikt, kunt u: 

  - [Windows Defender SmartScreen](https://docs.microsoft.com/intune/endpoint-protection-windows-10) inschakelen om te zoeken naar verdachte activiteit in bestanden en apps op mobiele apparaten. 
  - Gebruik [Microsoft Defender Advanced Threat Protection (ATP)](https://docs.microsoft.com/intune/advanced-threat-protection) om beveiligingsschending op mobiele apparaten te voorkomen. En beperk de gevolgen van een schending door een gebruiker te blokkeren vanuit bedrijfsresources.

- **Voorwaardelijke toegang** wordt mogelijk gemaakt door Azure Active Directory en kan prima worden geïntegreerd in Intune. Met [voorwaardelijke toegang](https://docs.microsoft.com/intune/conditional-access) kunt u ervoor zorgen dat alleen apparaten die voldoen aan het beleid, toegang krijgen tot e-mail, SharePoint en andere apps. 

## <a name="choose-the-device-management-solution-thats-right-for-you"></a>De apparaatbeheeroplossing kiezen die het beste bij uw behoeften past

Er zijn verschillende manieren om apparaten te beheren. Ten eerste kunt u verschillende aspecten van apparaten beheren met behulp van de ingebouwde functies van Intune. Deze aanpak heet **Mobile Device Management (MDM)** . Gebruikers 'registreren' hun apparaten en gebruiken certificaten om met Intune te communiceren. Als IT-beheerder kunt u apps naar apparaten pushen, apparaten alleen gebruik laten maken van een specifiek besturingssysteem, persoonlijke apparaten blokkeren en meer. Als een apparaat ooit verloren raakt of wordt gestolen, kunt u ook alle gegevens van het apparaat verwijderen. 

Bij de tweede aanpak beheert u de apps op apparaten. Deze aanpak heet **Mobile Application Management (MAM)** . Gebruikers kunnen hun persoonlijke apparaten gebruiken om toegang te krijgen tot bedrijfsresources. Wanneer gebruikers een app openen, zoals hun Postvak IN of SharePoint, wordt gevraagd om aanvullende verificatie. Als een apparaat ooit verloren raakt of wordt gestolen, kunt u alle bedrijfsgegevens van het apparaat verwijderen. 

U kunt ook een combinatie van [MDM en MAM](https://docs.microsoft.com/intune/byod-technology-decisions) gebruiken.

Wanneer u Intune instelt, kunt u er ook voor kiezen om alleen Azure Portal te gebruiken voor het beheren van apparaten. U kunt er daarnaast voor kiezen om zowel Intune als Microsoft 365 te gebruiken voor het beheren van apparaten. [Mobile Device Management migreren naar Intune via Azure Portal](https://www.microsoft.com/itshowcase/Article/Content/1042/Migrating-mobile-device-management-to-Intune-in-the-Azure-portal) is een Microsoft IT-casestudy. In deze casestudy is te zien hoe Microsoft IT tot de keuze voor een moderne apparaatbeheeraanpak is gekomen en is te lezen welke kennis hierbij is opgedaan.

## <a name="simplify-it-tasks-using-the-device-management-admin-center"></a>IT-taken vereenvoudigen via het beheercentrum Apparaatbeheer

Het [beheercentrum Apparaatbeheer](https://devicemanagement.portal.azure.com/) biedt alles wat u nodig hebt om taken voor uw mobiele apparaten te beheren en voltooien. Deze werkruimte biedt services voor apparaatbeheer (inclusief Intune en Azure Active Directory) en voor het beheren van apps van klanten. 

In het beheer centrum voor Apparaatbeheer kunt u het volgende doen:

- [Apparaten inschrijven](https://docs.microsoft.com/intune/device-enrollment)
- [Apparaatcompatibiliteit instellen](https://docs.microsoft.com/intune/device-compliance-get-started)
- [Apparaten beheren](https://docs.microsoft.com/intune/device-management)
- [Apps beheren](https://docs.microsoft.com/intune/app-management)  
- [iOS eBooks](https://docs.microsoft.com/intune/vpp-ebooks-ios)  
- [Exchange On-Premises Connector installeren](https://docs.microsoft.com/intune/exchange-connector-install)  
- [Rollen beheren](https://docs.microsoft.com/intune/role-based-access-control)  
- Software-updates beheren
  - [Windows 10-updates beheren](https://docs.microsoft.com/intune/windows-update-for-business-configure)  
  - [iOS-updates beheren](https://docs.microsoft.com/intune/software-updates-ios)  
- [Azure Active Directory](https://docs.microsoft.com/azure/active-directory)  
- [Gebruikers beheren](https://docs.microsoft.com/azure/active-directory/fundamentals/add-users-azure-active-directory)
- [Groepen en leden beheren](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-manage-groups)
- [Problemen oplossen](https://docs.microsoft.com/intune/help-desk-operators)

## <a name="next-step"></a>Volgende stap
Wanneer u klaar bent om aan de slag te gaan met een MDM- of MAM-oplossing, doorloopt u de verschillende stappen voor het instellen van Intune, het inschrijven van apparaten en het maken van beleid. [Mobile Device Management voor Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure) is ook een goede resource.
