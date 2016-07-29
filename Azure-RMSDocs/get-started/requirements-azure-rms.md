---
title: Vereisten voor Azure Rights Management | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 07/15/2016
ms.topic: get-started-article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: dc78321d-d759-4653-8818-80da74b6cdeb
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2fab331a26e18730e9cc64a24c0501b7ae21aa1b
ms.openlocfilehash: f225d8579e2440d2eb00a4f821a78727b6442fdd


---

# Vereisten voor Azure Rights Management

*Van toepassing op: Azure Rights Management, Office 365*


Als u Microsoft Azure Rights Management (Azure RMS) wilt implementeren in uw organisatie, moet u voldoen aan de volgende vereisten. U kunt vervolgens het [Azure Rights Management-implementatieschema](../plan-design/deployment-roadmap.md) gebruiken om Rights Management voor uw organisatie te implementeren.

|Vereiste|Meer informatie|
|---------------|--------------------|
|Een cloudabonnement voor RMS|Uw organisatie moet een cloudabonnement hebben met ondersteuning voor RMS.<br /><br />Zie [Cloudabonnementen die Azure RMS ondersteunen](requirements-subscriptions.md) voor informatie over licenties.|
|Azure AD-map|Uw organisatie moet een Azure AD-adreslijst hebben om gebruikersverificatie voor RMS te ondersteunen. Als u uw gebruikersaccounts vanuit uw lokale map (AD DS) wilt gebruiken, moet u bovendien mapintegratie configureren.<br /><br />Multi-Factor Authentication (MFA) wordt ondersteund met Azure RMS wanneer u beschikt over de vereiste clientsoftware en een juist geconfigureerde infrastructuur met ondersteuning voor MFA hebt.<br /><br />Zie [Azure AD-map](requirements-azure-ad.md) voor meer informatie.|
|Clientapparaten|Gebruikers moeten een clientapparaat (computer of mobiel apparaat) hebben met een besturingssysteem dat RMS ondersteunt.<br /><br />Zie [Clientapparaten die Azure RMS ondersteunen](requirements-client-devices.md) voor meer informatie.|
|Toepassingen|Gebruikers moeten toepassingen uitvoeren die RMS ondersteunen.<br /><br />Zie [Toepassingen die Azure RMS ondersteunen](requirements-applications.md) voor meer informatie.|
|Infrastructuur die verbinding met internet en afhankelijke cloudservices ondersteunt|Als u een firewall of vergelijkbare tussenkomende netwerkapparaten hebt die moeten worden geconfigureerd voor specifieke verbindingen, raadpleegt u de gegevens voor **Azure Rights Management (RMS)** in de [Office 365-portal en gedeelde](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_Portal-identity) sectie in het volgende Office-artikel: [Office 365-URL's en IP-adresbereiken](https://support.office.com/en-US/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).<br /><br />Volg de instructies in dit Office-artikel om op de hoogte te blijven van wijzigingen in deze informatie en abonneer u op een RSS-feed.<br /><br />Naast de informatie in het Office-artikel geldt het volgende specifiek voor Azure RMS:<br /><br />- Verbreek de TLS client-naar-service-verbinding niet (bijvoorbeeld om een inspectie op pakketniveau uit te voeren). In dat geval wordt de certificaatkoppeling, die RMS-clients gebruiken in combinatie met door Microsoft beheerde certificeringsinstanties om hun communicatie met Azure RMS te beveiligen, verbroken.<br /><br />- Als u een webproxy gebruikt die verificatie vereist, moet u deze configureren om geïntegreerde Windows-verificatie te gebruiken met de Active Directory-aanmeldingsreferenties van de gebruiker.|

Als u Azure RMS wilt gebruiken in combinatie met lokale servers, worden de volgende producten ondersteund:

-   Exchange Server

-   SharePoint Server

-   Windows Server-bestandsservers die ondersteuning bieden voor Infrastructuur voor Bestandsclassificering

Zie [Lokale servers die Azure RMS ondersteunen](requirements-servers.md) voor meer informatie over de extra Azure RMS-vereisten voor dit scenario.

> [!IMPORTANT]
> Het volgende scenario wordt niet ondersteund:
> 
> -   AD RMS en Azure RMS naast elkaar uitvoeren binnen dezelfde organisatie, behalve tijdens de migratie, zoals beschreven in [Migreren van AD RMS naar Azure Rights Management](../plan-design/migrate-from-ad-rms-to-azure-rms.md).
> 
> Er is een ondersteund migratiepad [van AD RMS naar Azure RMS](http://technet.microsoft.com/library/Dn858447.aspx) en van [Azure RMS naar AD RMS](http://msdn.microsoft.com/library/azure/dn629429.aspx). Als u Azure RMS implementeert en vervolgens besluit dat u deze cloudservice niet langer wilt gebruiken, raadpleegt u [Azure Rights Management uit bedrijf nemen en deactiveren](../deploy-use/decommission-deactivate.md).






<!--HONumber=Jul16_HO3-->


