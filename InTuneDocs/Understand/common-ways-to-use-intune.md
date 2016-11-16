---
title: Algemene manieren om Intune te gebruiken | Microsoft Intune
description: Een lijst met zes van de meest algemene taken waarbij Intune kan worden gebruikt
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/09/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f37d4ff-b5a7-4a89-8884-a6184908b09c
ms.reviewer: robstackmsft
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 198f7911db02b349c5be280a382ea26dea383b5b
ms.openlocfilehash: 292a7967deebbcca39d2debc5d8ea9478d08137a


---

# <a name="common-ways-to-use-intune"></a>Algemene manieren om Intune te gebruiken

Voordat u aan de slag gaat met implementatietaken, is het belangrijk om de Enterprise Mobility-belanghebbenden van uw bedrijf op één lijn te krijgen met de bedrijfsdoelen.  Dit is belangrijk als u nog nooit met Enterprise Mobility te maken hebt gehad, maar ook als u migreert vanaf een ander product.  De behoeften ten aanzien van Enterprise Mobility veranderen op dynamische wijze en de aanpak van Microsoft om aan deze behoeften te voldoen, kan soms verschillen van die van andere oplossingen in de markt.  De beste manier om op één lijn te komen met de bedrijfsdoelen is door te uiten wat u wilt bereiken voor uw werknemers, partners en IT.  Hieronder staat een korte inleiding over de zes meest voorkomende scenario’s waarin Intune wordt gebruikt, met koppelingen naar aanvullende informatie over het plannen en implementeren van die scenario’s.

>[!NOTE]
>Wilt u weten hoe de IT-afdeling van Microsoft Intune gebruikt om Microsoft-werknemers in staat te stellen toegang te krijgen tot bedrijfsbronnen op hun mobiele apparaten, terwijl de zakelijke gegevens goed beveiligd blijven? [Lees deze technische casestudy](https://www.microsoft.com/itshowcase/Article/Content/588) voor gedetailleerde informatie over hoe de IT-afdeling van Microsoft Intune en andere services gebruikt om identiteiten, apparaten, apps en gegevens te beheren.  

>[!IMPORTANT]
>Ervoor zorgen dat mobiele apparaten zijn bijgewerkt<br>
>Na aanleiding van de recente "Trident"-malwareaanvallen op iOS-apparaten is er een nieuw blogbericht gepubliceerd, [Ensuring mobile devices are up to date using Microsoft Intune](https://blogs.technet.microsoft.com/enterprisemobility/2016/08/26/ensuring-mobile-devices-are-up-to-date-using-microsoft-intune/) (Ervoor zorgen dat mobiele apparaten zijn bijgewerkt met Microsoft Intune), voor meer informatie over de verschillende manieren waarmee u met Intune uw apparaten beveiligd en bijgewerkt kunt houden.

## <a name="securing-your-onpremises-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices"></a>Uw on-premises-e-mail en -gegevens beveiligen zodat deze veilig kunnen worden geopend vanaf mobiele apparaten
De meeste Enterprise Mobility-strategieën worden ontwikkeld op basis van een plan om toegang tot e-mail te beveiligen voor werknemers die mobiele apparaten buiten het bedrijf gebruiken. Veel bedrijven hebben nog steeds on-premises gegevens- en toepassingsservers, zoals Microsoft Exchange, die worden gehost op het bedrijfsnetwerk. Intune en Microsoft Enterprise Mobility + Security(EMS) bieden een oplossing voor unieke geïntegreerde [voorwaardelijke toegang](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune) voor de Exchange-server zodat mobiele apps geen toegang meer krijgen tot e-mail tot het apparaat is geregistreerd bij Intune. Daarvoor hoeft geen andere gatewaycomputer te worden geïmplementeerd in uw bedrijfsnetwerk.

Naast e-mail biedt Intune ook ondersteuning voor het inschakelen van beveiligde toegang tot mobiele apps die worden gebruikt om on-premises gegevens te openen, zoals een Line-of-Business-app.  Dit gebeurt meestal met behulp van door [Intune beheerde certificaten](/intune/deploy-use/secure-resource-access-with-certificate-profiles) voor toegangsbeheer in combinatie met een standaard VPN-gateway of proxy in het perimeternetwerk, zoals de Microsoft Azure AD-toepassingsproxy.  In dergelijke gevallen is de enige manier om toegang tot zakelijke gegevens te krijgen het apparaat in te schrijven voor beheer.  Na registratie controleert het beheersysteem of de apparaten waarmee bedrijfsgegevens worden geopend, voldoen aan uw beleid.  Daarnaast kunt u [App Wrapping Tool en App SDK](/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune) van Intune gebruiken om de geopende gegevens binnen de Line-Of-Business-app te houden, zodat deze bedrijfsgegevens niet kan doorgeven aan consumentenapps of -services.

<!-- Learn more about how to plan and deploy Intune to help secure on-premises email and data. -->

## <a name="securing-your-office-365-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices"></a>Uw Office 365-e-mail en -gegevens beveiligen zodat deze veilig kunnen worden geopend vanaf mobiele apparaten
Het beveiligen van bedrijfsgegevens in Office 365 (e-mail, documenten, chatberichten, contactpersonen) is enorm eenvoudig en biedt gebruikers een naadloze ervaring. Intune en Microsoft Enterprise Mobility + Security bieden een unieke, geïntegreerde oplossing voor voorwaardelijke toegang waardoor gebruikers, apps en apparaten geen toegang krijgen tot Office 365-gegevens tenzij ze voldoen aan de nalevingsvereisten van uw bedrijf ([meervoudige verificatie](/intune/deploy-use/protect-windows-devices-with-multi-factor-authentication) uitgevoerd, geregistreerd bij Intune, gebruikt beheerde app, ondersteunde besturingssysteemversie, pincode op apparaat, gebruiker met laag risicoprofiel enzovoort). De mobiele Office-apps in de app stores kunnen direct worden gebruikt met gegevenscontainmentbeleid dat u kunt configureren via Intune. Op die manier kunt u voorkomen dat gegevens worden gedeeld met apps (bijvoorbeeld de systeemeigen e-mail-app) en opslaglocaties (bijvoorbeeld Dropbox) die niet door de IT-afdeling worden beheerd.  Deze functionaliteit is ook ingebouwd in Office 365 en het EMS.  U hoeft geen aanvullende infrastructuur te implementeren om van deze waarde te profiteren.

Normaal worden bij het implementeren van Office 365 apparaten verplicht geregistreerd voor beheer als ze volledig moeten worden ingericht met bedrijfsapps/certificaten/Wi-Fi/VPN-configuraties. Dit is vaak het geval bij bedrijfsapparaten.  Als de gebruiker echter alleen toegang nodig heeft tot bedrijfs-e-mail en -documenten, wat vaak het geval is bij apparaten in privé-eigendom, moet de gebruiker de mobiele Office-apps gebruiken (waar het [gegevenscontainmentbeleid op is toegepast](/intune/deploy-use/protect-apps-and-data-with-microsoft-intune)), zodat de registratie van het apparaat kan worden overgeslagen.  In beide gevallen worden de Office 365-gegevens beveiligd met beleidsregels die u hebt gedefinieerd.

<!-- Learn more about how to plan and deploy Intune to help secure Office 365 email and data. -->

## <a name="offer-a-bring-your-own-device-byod-program-to-all-employees"></a>Bied een Bring Your Own Device-programma (BYOD) aan alle werknemers
BYOD wordt steeds populairder bij organisaties; hierdoor hoeft er minder te worden uitgegeven aan hardware en zijn de werknemers mobieler ten opzichte van hun werkplek. Bijna iedereen heeft tegenwoordig een telefoon bij zich, dus waarom zou u er nóg een aan werknemers geven? De grootste uitdaging is altijd geweest om werknemers ervan te overtuigen hun persoonlijke apparaat in te schrijven voor beheer, omdat ze bang zijn voor wat de IT-afdeling op het apparaat kan zien en wat de IT-afdeling ermee kan doen.  

Als apparaatregistratie niet mogelijk of gewenst is, biedt Intune ook een alternatieve BYOD-optie waarbij alleen de [apps worden beheerd die zakelijke gegevens bevatten](/intune/deploy-use/protect-apps-and-data-with-microsoft-intune).  Intune beveiligt zakelijke gegevens zelfs als de betreffende app toegang heeft tot zowel zakelijke als persoonlijke gegevens, zoals het geval is bij de mobiele apps van Office.  U kunt als beheerder eisen dat gebruikers Office 365 openen via de mobiele apps van Office en dat ze de apps configureren met beleid om de gegevens te beschermen (versleutelen, beveiligen met pincode, enzovoort).  Dit beleid voorkomt dat gegevens worden doorgegeven aan niet-beheerde apps en worden opgeslagen op niet-beheerde opslaglocaties (binnen én buiten de apps).  Met het beleid wordt bijvoorbeeld voorkomen dat een gebruiker tekst uit een zakelijk e-mailprofiel kopieert naar een consumenten-e-mailprofiel, zelfs als beide profielen in Outlook Mobile zijn geconfigureerd.  U kunt vergelijkbare configuraties implementeren voor andere services en toepassingen die uw BYOD-gebruikers nodig hebben.

<!-- Learn more about how to plan and deploy Intune to support BYOD.-->

## <a name="issue-corporateowned-phones-to-your-information-workers"></a>Geef bedrijfstelefoons uit aan uw IT-medewerkers
De meeste IT-medewerkers zijn tegenwoordig mobiel, waardoor het steeds belangrijker wordt om productiviteit op mobiele apparaten mogelijk te maken; zo blijft het concurrentievermogen behouden.  Deze werknemers hebben naadloze toegang nodig tot alle zakelijke toepassingen en gegevens, op elk gewenst moment en waar ze ook zijn.  U moet ervoor zorgen dat zakelijke gegevens goed worden beveiligd en dat de administratieve kosten laag blijven.  

Intune biedt [oplossingen voor bulksgewijze inrichting en beheer](/intune/deploy-use/manage-corporate-owned-devices) die kunnen worden geïntegreerd in de grootste apparaatbeheerplatformen voor bedrijven van dit moment, waaronder het Apple Device Enrollment Program en het Samsung KNOX-platform voor mobiele beveiliging.  Omdat apparaatconfiguraties centraal kunnen worden opgesteld met Intune kan het inrichten van zakelijke apparaten in grote mate worden geautomatiseerd.  

Stel u dit eens voor: u geeft een werknemer een nieuwe iPhone in een nog niet geopende doos. De werknemer zet de telefoon aan en doorloopt een installatieprocedure waar het bedrijfslogo in is verwerkt. Hierin moet de werknemer zich verifiëren. De iPhone wordt naadloos geconfigureerd met [beveiligingsbeleid](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) (versleutelen van de harde schijf, pincode voor het apparaat, enzovoort), [e-mail, Wi-Fi, VPN en certificaatprofielen](/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune) én de basis-[apps](/intune/deploy-use/add-apps) worden geïnstalleerd. De werknemer start vervolgens de Intune-bedrijfsportal-app voor toegang tot optionele zakelijke apps die voor hem of haar beschikbaar zijn.

<!-- Learn more about how to plan and deploy Intune to support corporate owned devices. -->

## <a name="issue-limiteduse-shared-tablets-to-your-task-workers"></a>Tablets voor beperkt gebruik overhandigen aan taakgerichte werknemers
Taakgerichte werknemers maken steeds meer gebruik van mobiele technologieën.  Gedeelde tablets zijn bijvoorbeeld heel normaal geworden voor werknemers in winkels.  Met tablets kan er beter worden gecommuniceerd met klanten. Met een tablet kan bijvoorbeeld een verkoop worden verwerkt of de voorraad kan er mee worden gecontroleerd.  Een eenvoudige gebruikerservaring is in dit geval van groot belang.  Om die reden worden tablets meestal aan werknemers gegeven in een modus voor beperkt gebruik, zodat de werknemer bijvoorbeeld alleen een Line-of-Business-app kan gebruiken.  Met Intune kunt u deze gedeelde [iOS](/intune/deploy-use/ios-policy-settings-in-microsoft-intune#general-configuration-policy-settings)- en [Android](/intune/deploy-use/android-policy-settings-in-microsoft-intune#general-configuration-policy)-tablets bulksgewijs inrichten, beveiligen en centraal beheren en ervoor zorgen dat ze zodanig worden geconfigureerd dat ze in de modus voor beperkt gebruik kunnen worden uitgevoerd.

<!-- Learn more about how to plan and deploy Intune to support shared tablets. -->

## <a name="enable-your-employees-to-securely-access-office-365-from-an-unmanaged-public-kiosk"></a>Uw werknemers in staat stellen Office 365 veilig te gebruiken vanuit een niet-beheerde openbare kiosk
Soms moeten uw werknemers apparaten, toepassingen of browsers gebruiken die u niet kunt beheren, zoals de openbare computers op beurzen en in hotellobby’s. Moet u uw werknemers toegang bieden tot bedrijfs-e-mails vanaf deze locaties? Met Intune en Microsoft Enterprise Mobility + Security <!--you have choices. The--> kunt u gewoon Nee zeggen en [e-mailtoegang beperken tot apparaten die door uw bedrijf worden beheerd](/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).  <!-- Alternatively, you can choose to allow limited access to these untrusted computers by requiring multi-factor authentication and only allowing browser access (Outlook Web Access) in a mode where files cannot be downloaded (e.g. email attachments).--> Zo zorgt u ervoor dat geverifieerde werknemers niet per ongeluk bedrijfsgegevens achterlaten op de niet-vertrouwde computer.

<!-- Learn more about how to plan and deploy Intune to support kiosks. -->



<!--HONumber=Nov16_HO2-->


