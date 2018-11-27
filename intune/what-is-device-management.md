---
title: Apparaatbeheer in Microsoft 365
description: Microsoft 365 Enterprise bevat Microsoft Intune. Ontdek hoe Intune Mobile Device Management en Mobile Application Management biedt voor uw organisatie, met onder andere veelvoorkomende scenario's en informatie over het gebruik van Intune om Microsoft 365 te implementeren in uw omgeving.
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/21/2018
ms.topic: article
audience: ITPro
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.custom: intune
ms.assetid: 0649d310-43a7-4b01-85d2-da255d03e1da
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.openlocfilehash: 83ac68e1f6efa9e5b0c1ee0e031d36989b634edd
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52185216"
---
# <a name="what-is-device-management"></a>Wat is apparaatbeheer? 

Beheerders hebben de belangrijke taak om de resources en gegevens van en organisatie te beschermen en beveiligen. Dit heet apparaatbeheer. Gebruikers hebben veel apparaten van waaruit ze persoonlijke bestanden openen en delen, websites bezoeken en apps en games installeren. Diezelfde gebruikers zijn ook werknemers en leerlingen, en ze willen hun apparaten gebruiken om werk- en schoolresources te openen, zoals hun Postvak IN en OneNote. Met *apparaatbeheer* kunnen organisaties hun resources en gegevens beschermen en beveiligen. 

Met een apparaatbeheerprovider zorgen organisaties ervoor dat alleen gemachtigde personen en apparaten toegang krijgen tot vertrouwelijke informatie. Op vergelijkbare manier kunnen apparaatgebruiker met een gerust hart gegevens op hun telefoon openen, omdat ze weten dat het apparaat voldoet aan de beveiligingsvereisten van de organisatie. Als organisatie vraagt u zich misschien af **wat er moet worden gebruikt om de resources te beschermen.**

[Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) kan u hierbij van dienst zijn. Intune biedt mogelijkheden voor Mobile Device Management (MDM) en Mobile Application Management (MAM). MDM- en MAM-oplossingen worden voor de volgende belangrijke zaken gebruikt:

- Ondersteuning bieden voor een diverse mobiele omgeving&mdash;iOS-, Android-, Windows- en macOS-apparaten veilig beheren
- Ervoor zorgen dat apparaten en apps voldoen aan de beveiligingsvereisten van uw organisatie
- Beleidsregels maken om de gegevens van uw organisatie te beveiligen op apparaten van het bedrijf en persoonlijke apparaten
- Eén uniforme mobiele oplossing gebruiken om dit beleid af te dwingen en helpen bij het beheren van apparaten, apps, gebruikers en groepen.

Intune maakt deel uit van Microsoft 365 en kan worden geïntegreerd in Azure Active Directory (Azure AD). Met Azure AD kunt u bepalen wie er toegang krijgt en waartoe deze personen toegang krijgen.

## <a name="hello-intune"></a>Hallo Intune!
Veel organisaties, zoals Microsoft zelf, maken gebruik van Intune om eigen gegevens te beveiligen waarvan gebruikers gebruikmaken op bedrijfs- en persoonlijke mobiele apparaten. Intune bevat functies voor apparaat- en app-configuratiebeleid, software-updatebeleid en installatiestatussen (inclusief grafieken, tabellen en rapporten) zodat u de toegang tot gegevens kunt beveiligen en bewaken.

Het is gebruikelijk dat mensen meerdere apparaten hebben waarop gebruik wordt gemaakt van verschillende platforms. Mogelijk gebruikt een werknemer bijvoorbeeld Surface Pro voor het werk en een mobiel Android-apparaat voor privézaken. Het is ook gebruikelijk dat mensen bedrijfsresources, zoals Microsoft Outlook en SharePoint, gebruikt vanaf meerdere apparaten.

Met Intune kunt u meerdere apparaten voor één persoon beheren. Het is daarbij geen probleem als er verschillende platforms op de apparaten worden gebruikt, zoals iOS, macOS, Android en Windows. Intune maakt per apparaatplatform onderscheid tussen beleidsregels en instellingen, zodat u eenvoudig apparaten met een specifiek platform kunt beheren en bekijken.

**[Veelvoorkomende scenario's](https://docs.microsoft.com/intune/common-scenarios)** is een uitstekende resource om te ontdekken hoe Intune met bepaalde kwesties omgaat ten aanzien van mobiele apparaten. Er zijn scenario's te vinden over:  
- E-mail beveiligen met on-premises Exchange
- Office 365 veilig gebruiken
- Persoonlijke apparaten gebruiken voor toegang tot bedrijfsresources

## <a name="integration-with-secure-and-protect-services"></a>Integratie met services beveiligen en beschermen
Het is een belangrijke taak van elke apparaatbeheeroplossing om beveiliging en bescherming te bieden. Intune kan hiervoor uitstekend worden geïntegreerd in andere services. Bijvoorbeeld:

- **Microsoft 365** is belangrijk bij het vereenvoudigen van vaak uitgevoerde IT-taken. Via het Microsoft 365-beheercentrum kunt u gebruikers maken, groepen beheren en toegang verkrijgen tot andere services, zoals Intune en Azure Active Directory. U kunt bijvoorbeeld een iOS-apparaatgroep maken in Microsoft 365. Gebruik vervolgens Intune om beleid naar een iOS-apparaatgroep te pushen waarin de focus ligt op iOS-gerelateerde zaken, zoals toegang tot de App Store, gebruikmaken van AirDrop, back-ups maken in iCloud, gebruikmaken van het webfilter van Apple en meer.

- **Windows Defender** bevat veel beveiligingsfuncties ter bescherming van Windows 10-apparaten. Als u Intune en Windows Defender samen gebruikt, kunt u: 

    - [Windows Defender SmartScreen](https://docs.microsoft.com/intune/endpoint-protection-windows-10) inschakelen om te zoeken naar verdachte activiteit in bestanden en apps op mobiele apparaten. 
    - Gebruik [Windows Defender Advanced Threat Protection (ATP)](https://docs.microsoft.com/intune/advanced-threat-protection) om beveiligingsschendingen op mobiele apparaten te voorkomen en om de impact van beveiligingsschendingen te beperken door de toegang van gebruikers tot bedrijfsresources te blokkeren.

- **Voorwaardelijke toegang** wordt mogelijk gemaakt door Azure Active Directory en kan prima worden geïntegreerd in Intune. Met [voorwaardelijke toegang](https://docs.microsoft.com/intune/conditional-access) kunt u ervoor zorgen dat alleen apparaten die voldoen aan het beleid toegang krijgen tot e-mail, SharePoint en andere apps. 

## <a name="choose-the-device-management-solution-thats-right-for-you"></a>De apparaatbeheeroplossing kiezen die het beste bij uw behoeften past

Er zijn verschillende manieren om apparaten te beheren. Ten eerste kunt u alle aspecten van apparaten beheren door alle functies te gebruiken die zijn ingebouwd in Intune. Dit heet **Mobile Device Management (MDM)**. Bij deze aanpak schrijven gebruikers hun apparaten in en worden er certificaten gebruikt om met Intune te communiceren. IT-beheerders kunnen apps naar apparaten pushen, apparaten alleen gebruik laten maken van een specifiek besturingssysteem, persoonlijke apparaten blokkeren en meer. Als een apparaat ooit verloren raakt of wordt gestolen, kunt u ook alle gegevens van het apparaat verwijderen. 

Bij de tweede aanpak beheert u de apps op apparaten. Dit heet **Mobile Application Management (MAM)**. Bij deze aanpak kunnen gebruikers hun persoonlijke apparaten gebruiken om toegang te verkrijgen tot bedrijfsresources. Wanneer gebruikers een app openen, zoals hun Postvak IN of SharePoint, wordt gevraagd om aanvullende verificatie. Als een apparaat ooit verloren raakt of wordt gestolen, kunt u alle bedrijfsgegevens van het apparaat verwijderen. 

U kunt ook een combinatie van [MDM en MAM](https://docs.microsoft.com/intune/byod-technology-decisions) gebruiken.

Wanneer u Intune instelt, kunt u er ook voor kiezen om alleen Azure Portal te gebruiken voor het beheren van apparaten. U kunt er daarnaast voor kiezen om zowel Intune als Microsoft 365 te gebruiken voor het beheren van apparaten. Ontdek hoe de IT-afdeling van Microsoft heeft gekozen voor een moderne apparaatbeheeroplossing en welke lessen er zijn geleerd. Open hiervoor de Microsoft IT-casestudy [Mobile Device Management migreren naar Intune via Azure Portal](https://www.microsoft.com/itshowcase/Article/Content/1042/Migrating-mobile-device-management-to-Intune-in-the-Azure-portal). 

## <a name="simplify-it-tasks-using-the-device-management-dashboard"></a>IT-taken vereenvoudigen via het dashboard Apparaatbeheer

Het [dashboard Apparaatbeheer](https://devicemanagement.portal.azure.com/) biedt alles wat u nodig hebt om taken voor uw mobiele apparaten te beheren en voltooien. Het dashboard biedt services voor apparaatbeheer (inclusief Intune en Azure Active Directory) en voor het beheren van apps van klanten. 

Op het dashboard Apparaatbeheer kunt u:

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
Wanneer u klaar bent om aan de slag te gaan met een MDM- of MAM-oplossing, doorloopt u de verschillende stappen voor het instellen van Intune, het inschrijven van apparaten en het maken van beleid. Zie hiervoor [Mobile Device Management voor Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure). 
