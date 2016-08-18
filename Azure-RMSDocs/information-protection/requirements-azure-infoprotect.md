---
title: Vereisten voor Azure Information Protection | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 08/10/2016
ms.topic: get-started-article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: aa4353e5-c5b0-47f6-a6f9-87d13e8f075f
ms.reviewer: eymanor
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c0652e05576ab28d7b77380ab1b8aa0ca2d3e479
ms.openlocfilehash: e3eb845af4e2cfec43c63c9625163f62c83cf954


---

# Vereisten voor Azure Information Protection

>*Van toepassing op: Azure Information Protection preview*

**[ Deze informatie is voorlopig en kan worden gewijzigd. ]**

Om de preview-versie van Azure Information Protection te gebruiken, moet u voldoen aan de volgende vereisten. 

|Vereiste|Meer informatie|
|---------------|--------------------|
|Een cloudabonnement voor onder meer Azure RMS|Uw organisatie moet een cloudabonnement hebben met ondersteuning voor Rights Management.<br /><br />Zie [Cloudabonnementen die Azure RMS ondersteunen](../get-started/requirements-subscriptions.md) voor meer informatie en koppelingen naar gratis proefversies.|
|Azure AD-map|Uw organisatie moet een Azure AD-map hebben om gebruikersverificatie voor RMS en Azure Information Protection te ondersteunen. Als u uw gebruikersaccounts vanuit uw lokale map (AD DS) wilt gebruiken, moet u bovendien mapintegratie configureren.<br /><br />Multi-Factor Authentication (MFA) wordt ondersteund met Azure RMS wanneer u beschikt over de vereiste clientsoftware en een juist geconfigureerde infrastructuur met ondersteuning voor MFA hebt.<br /><br />Zie voor meer informatie [Azure AD-map](../get-started/requirements-azure-ad.md), waarin de gegevens voor Azure RMS ook van toepassing zijn op Azure Information Protection.|
|Clientapparaten|De volgende clientapparaten worden voor deze preview-versie ondersteund:<br /><br />- Windows 10 (x86, x64)<br /><br />- Windows 8.1 (x86, x64)<br /><br />- Windows 8 (x86, x64)<br /><br />- Windows 7 Service Pack 1 (x86, x64)<br /><br />Wanneer u de gegevens beveiligt, kunnen deze worden gebruikt door de dezelfde apparaten (Windows, Mac, iOS, Android), die ondersteuning bieden voor Azure Rights Management. Zie [Azure RMS-vereisten: clientapparaten die Azure RMS ondersteunen](../get-started/requirements-client-devices.md) voor details over deze apparaten en de ondersteunde versies.|
|Toepassingen|Voor de preview-versie en de algemene beschikbaarheid ondersteunt Azure Information Protection labels en beveiliging van bestanden en e-mailberichten die zijn gemaakt met de volgende Office-toepassingen: **Word**, **Excel**, **PowerPoint** en **Outlook** in de volgende Office-suites:<br /><br />- Office Professional Plus 2016<br /><br />- Office Professional Plus 2013 met Service Pack 1<br /><br />- Office Professional Plus 2010<br /><br />Zodra deze versie algemeen beschikbaar is, moet u uitkijken naar een aankondiging op de [Enterprise Mobility en Security-blog](https://blogs.technet.microsoft.com/enterprisemobility/?product=azure-rights-management-services) om te zien wanneer Azure Information Protection ondersteuning biedt voor extra bestandstypen, zoals PDF- en audio-, video- en afbeeldingsbestanden.|
|Infrastructuur die verbinding met internet en afhankelijke cloudservices ondersteunt|Als u een firewall of vergelijkbare tussenkomende netwerkapparaten hebt die moeten worden geconfigureerd voor specifieke verbindingen, raadpleegt u de gegevens voor **Azure Rights Management (RMS)** in de [Office 365-portal en gedeelde](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_Portal-identity) sectie in het volgende Office-artikel: [Office 365-URL's en IP-adresbereiken](https://support.office.com/en-US/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)<br /><br />Daarnaast:<br /><br />- Sta HTTPS-verkeer op TCP 443 naar **informationprotection.azure.com** toe.<br /><br />- Verbreek de TLS client-naar-service-verbinding niet (bijvoorbeeld om een inspectie op pakketniveau uit te voeren). <br /><br />- Als u een webproxy gebruikt die verificatie vereist, moet u deze configureren om geïntegreerde Windows-verificatie te gebruiken met de Active Directory-aanmeldingsreferenties van de gebruiker.|

## Volgende stappen

Als u aan deze vereisten voldoet, kunt u proberen onze zelfgestuurde demo om Azure Information Protection te configureren en zelf uit te proberen: [Zelfstudie voor snel starten met Azure Information Protection](infoprotect-quick-start-tutorial.md).




<!--HONumber=Aug16_HO2-->


