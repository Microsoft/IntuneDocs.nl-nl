---
title: Algemene manieren om Microsoft Intune te gebruiken
description: Lees over zes van de meest algemene taken die Microsoft Intune u kan helpen beheren.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 11/29/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1f37d4ff-b5a7-4a89-8884-a6184908b09c
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: f0e2e2101706b9b9afa77553244a438a2299903b
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "73414029"
---
# <a name="common-ways-to-use-microsoft-intune"></a>Algemene manieren om Microsoft Intune te gebruiken

Voordat u aan de slag gaat met implementatietaken, is het belangrijk om de Enterprise Mobility-belanghebbenden van uw bedrijf op één lijn te krijgen met de bedrijfsdoelen voor het gebruik van Intune. Dit is belangrijk als u nog nooit met Enterprise Mobility te maken hebt gehad, maar ook als u migreert vanaf een ander product.  

De behoeften ten aanzien van Enterprise Mobility veranderen op dynamische wijze, en de aanpak van Microsoft om aan deze behoeften te voldoen kan soms verschillen van die van andere oplossingen in de markt. De beste manier om op één lijn te komen met de bedrijfsdoelen is door te uiten wat u wilt bereiken voor uw werknemers, partners en IT-afdeling.  

Hieronder staat een korte inleiding over de zes meest voorkomende scenario’s waarin Intune wordt gebruikt, met koppelingen naar aanvullende informatie over het plannen en implementeren van die scenario’s.

>[!NOTE]
>Wilt u weten hoe de IT-afdeling van Microsoft gebruikmaakt van Intune om Microsoft toegang te bieden tot bedrijfsbronnen op hun mobiele apparaten, terwijl de zakelijke gegevens goed beveiligd blijven? [Lees deze technische casestudy](https://www.microsoft.com/itshowcase/Article/Content/588) voor gedetailleerde informatie over hoe de IT-afdeling van Microsoft Intune en andere services gebruikt om identiteiten, apparaten, apps en gegevens te beheren.  

>[!IMPORTANT]
>Naar aanleiding van de recente aanvallen met ‘Trident’-malware op iOS-apparaten willen we ervoor zorgen dat mobiele apparaten bijgewerkt zijn. Daarom hebben we een blogbericht gepubliceerd, getiteld [Ervoor zorgen dat mobiele apparaten zijn bijgewerkt met Microsoft Intune](https://blogs.technet.microsoft.com/enterprisemobility/2016/08/26/ensuring-mobile-devices-are-up-to-date-using-microsoft-intune/). Dit bericht bevat informatie over de verschillende manieren waarop u Intune kunt gebruiken om uw apparaten veilig en bijgewerkt te houden.

## <a name="protecting-your-on-premises-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices"></a>Uw on-premises e-mail en -gegevens beveiligen zodat deze veilig kunnen worden geopend vanaf mobiele apparaten

De meeste Enterprise Mobility-strategieën worden ontwikkeld op basis van een plan om toegang tot e-mail te beveiligen voor werknemers met mobiele apparaten die verbinding maken met internet. Veel bedrijven hebben nog steeds on-premises gegevens- en toepassingsservers, zoals Microsoft Exchange, die worden gehost in het bedrijfsnetwerk.

Intune en Microsoft Enterprise Mobility + Security (EMS) bieden een unieke, geïntegreerde [oplossing voor voorwaardelijke toegang](../protect/conditional-access.md) tot Exchange Server, die garandeert dat mobiele apparaten geen toegang krijgen tot e‑mail totdat het apparaat is ingeschreven bij Intune. U kunt dit type toegang tot e-mail implementeren zonder dat u een nieuwe gateway hoeft te implementeren aan de rand van uw bedrijfsnetwerk.

Intune biedt ook ondersteuning voor het inschakelen van beveiligde toegang tot mobiele apps die worden gebruikt om on-premises gegevens te openen, zoals een line-of-business-app. Dit soort toegang vindt meestal plaats met behulp van [door Intune beheerde certificaten](../protect/certificates-configure.md) voor toegangsbeheer in combinatie met een standaard VPN-gateway of proxy in het perimeternetwerk, zoals de Microsoft Azure Active Directory-toepassingsproxy.

In dergelijke gevallen is de enige manier om toegang tot zakelijke gegevens te krijgen, het apparaat in te schrijven voor beheer. Nadat de apparaten zijn ingeschreven, controleert het beheersysteem of ze voldoen aan uw beleid voordat ze toegang krijgen tot bedrijfsgegevens. Daarnaast kunt u [App Wrapping Tool en App SDK](../developer/apps-prepare-mobile-application-management.md) van Intune gebruiken om de geopende gegevens binnen de Line-Of-Business-app te houden, zodat die de bedrijfsgegevens niet kan doorgeven aan consumenten-apps of -services.

<!-- Learn more about how to plan and deploy Intune to help secure on-premises email and data. -->

## <a name="protecting-your-office-365-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices"></a>Uw Office 365-e-mail en -gegevens beveiligen zodat deze veilig kunnen worden geopend vanaf mobiele apparaten

Het beveiligen van bedrijfsgegevens in Office 365 (e-mail, documenten, chatberichten, contactpersonen) is enorm eenvoudig en biedt gebruikers een naadloze ervaring.

Intune en Microsoft Enterprise Mobility + Security bieden een unieke, geïntegreerde oplossing voor voorwaardelijke toegang waardoor gebruikers, apps en apparaten geen toegang krijgen tot Office 365-gegevens tenzij ze voldoen aan de nalevingsvereisten van uw bedrijf ([meervoudige verificatie](../enrollment/multi-factor-authentication.md) uitgevoerd, ingeschreven bij Intune, gebruikt beheerde app, ondersteunde besturingssysteemversie, pincode op apparaat, gebruiker met laag risicoprofiel, enzovoort).

De mobiele Office-apps in hun respectieve app stores zijn klaar om te worden gebruikt met een gegevenscontainmentbeleid dat u via Intune kunt configureren. Hiermee kunt u voorkomen dat gegevens worden gedeeld met apps (zoals een ingebouwde e‑mailapp) en opslaglocaties (zoals Dropbox), die niet door IT worden beheerd. Deze functionaliteit is ook ingebouwd in Office 365 en het EMS. U hoeft geen aanvullende infrastructuur te implementeren om hiervan te profiteren.

Normaal worden bij het implementeren van Office 365 apparaten verplicht ingeschreven voor beheer als ze volledig moeten worden ingesteld met bedrijfs-apps, certificaten, Wi-Fi en VPN-configuraties. Dit is vaak het geval bij bedrijfsapparaten.  

Als uw gebruiker echter alleen toegang nodig heeft tot bedrijfs-e-mail en -documenten, wat vaak het geval is bij apparaten in privé-eigendom, kunt u de gebruiker verplichten om de mobiele Office-apps (waarop u [app-beveiligingsbeleid](../apps/app-protection-policies.md) hebt toegepast) te gebruiken en de registratie van het apparaat over te slaan.  

In beide gevallen worden de Office 365-gegevens beveiligd met beleidsregels die u hebt gedefinieerd.

<!-- Learn more about how to plan and deploy Intune to help secure Office 365 email and data. -->

## <a name="offer-a-bring-your-own-device-program-to-all-employees"></a>Bied een Bring Your Own Device-programma aan alle werknemers

Bring Your Own Device (BYOD) wordt steeds populairder bij organisaties, omdat er minder hoeft te worden uitgegeven aan hardware en de werknemers gemakkelijker mobiel kunnen werken en dus productiever zijn. Bijna iedereen heeft tegenwoordig een telefoon bij zich, dus waarom zou u er nóg een aan werknemers geven? De grootste uitdaging is altijd geweest om werknemers ervan te overtuigen hun persoonlijke apparaat in te schrijven voor beheer, omdat ze bang zijn voor wat de IT-afdeling op het apparaat kan zien en wat de IT-afdeling ermee kan doen.  

Als apparaatregistratie niet mogelijk of gewenst is, biedt Intune ook een alternatieve BYOD-optie waarbij alleen de [apps worden beheerd die zakelijke gegevens bevatten](../apps/app-protection-policies.md). Intune beveiligt zakelijke gegevens zelfs als de betreffende app toegang heeft tot zowel zakelijke als persoonlijke gegevens, zoals het geval is bij de mobiele apps van Office.  

U kunt als beheerder eisen dat gebruikers Office 365 openen via de mobiele apps van Office en dat ze de apps configureren met beleid om de gegevens te beschermen (door ze bijvoorbeeld te versleutelen, te beveiligen met pincode, enzovoort). Dit app-beveiligingsbeleid voorkomt gegevensverlies via niet-beheerde apps en niet-beheerde opslaglocaties (binnen én buiten de apps). Met het beleid wordt bijvoorbeeld voorkomen dat een gebruiker tekst uit een zakelijk e-mailprofiel kopieert naar een consumenten-e-mailprofiel, zelfs als beide profielen in Outlook Mobile zijn geconfigureerd. U kunt vergelijkbare configuraties implementeren voor andere services en toepassingen die uw BYOD-gebruikers nodig hebben.

<!-- Learn more about how to plan and deploy Intune to support BYOD.-->

## <a name="issue-corporate-owned-phones-to-your-employees"></a>Bedrijfstelefoons aan uw medewerkers verstrekken

Tegenwoordig zijn veel werknemers mobiel, waardoor het steeds belangrijker wordt om productiviteit op mobiele apparaten mogelijk te maken; zo blijft het concurrentievermogen behouden. Deze werknemers hebben naadloze toegang nodig tot alle zakelijke toepassingen en gegevens, op elk gewenst moment en waar ze ook zijn. U moet ervoor zorgen dat zakelijke gegevens goed worden beveiligd en dat de administratieve kosten laag blijven.  

Intune biedt [oplossingen voor bulksgewijze inrichting en beheer](../enrollment/device-enrollment.md) die kunnen worden geïntegreerd in de grootste apparaatbeheerplatforms voor bedrijven van dit moment, waaronder het Apple Device Enrollment Program en het Samsung Knox-platform voor mobiele beveiliging. Omdat apparaatconfiguraties centraal kunnen worden opgesteld met Intune kan het inrichten van zakelijke apparaten in grote mate worden geautomatiseerd.  

Stel u dit eens voor: u geeft een werknemer een nieuwe iPhone in een nog niet geopende doos. De werknemer zet de telefoon aan en doorloopt een installatieprocedure waar het bedrijfslogo in is verwerkt. Hierin moet de werknemer zich verifiëren. De iPhone wordt naadloos geconfigureerd voor [beveiligingsbeleid](../configuration/device-profiles.md).

De werknemer start vervolgens de Intune-bedrijfsportal-app voor toegang tot optionele zakelijke apps die voor hem of haar beschikbaar zijn.

<!-- Learn more about how to plan and deploy Intune to support corporate owned devices. -->

## <a name="issue-limited-use-shared-tablets-to-your-employees"></a>Gedeelde tablets voor beperkt gebruik verstrekken aan werknemers

Werknemers maken steeds meer gebruik van mobiele technologieën. Gedeelde tablets zijn bijvoorbeeld heel normaal geworden voor werknemers in winkels.  Met tablets kan er beter worden gecommuniceerd met klanten, omdat daarmee een verkoop kan worden verwerkt of direct de voorraad kan worden gecontroleerd.

Een eenvoudige gebruikerservaring is in dit geval van groot belang. Om die reden worden tablets meestal aan werknemers gegeven in een modus voor beperkt gebruik, zodat de werknemer bijvoorbeeld alleen een Line-Of-Business-app kan gebruiken. Met Intune kunt u deze gedeelde [iOS- en Android](../configuration/device-profiles.md)-apparaten bulksgewijs inrichten, beveiligen en centraal beheren en ervoor zorgen dat ze zodanig worden geconfigureerd dat ze in de modus voor beperkt gebruik kunnen worden uitgevoerd.

<!-- Learn more about how to plan and deploy Intune to support shared tablets. -->

## <a name="enable-your-employees-to-securely-access-office-365-from-an-unmanaged-public-kiosk"></a>Uw werknemers in staat stellen Office 365 veilig te gebruiken vanuit een niet-beheerde openbare kiosk

Soms moeten uw werknemers apparaten, toepassingen of browsers gebruiken die u niet kunt beheren, zoals de openbare computers op beurzen en in hotellobby's.

Moet u uw werknemers toegang bieden tot bedrijfs-e‑mails vanaf deze locaties? Met Intune en Microsoft Enterprise Mobility + Security kunt u gewoon Nee zeggen en [e-mailtoegang beperken tot apparaten die door uw bedrijf worden beheerd](../protect/conditional-access.md). Zo zorgt u ervoor dat geverifieerde werknemers niet per ongeluk bedrijfsgegevens achterlaten op de niet-vertrouwde computer.
