---
title: Wat is er nieuw in Microsoft Intune Preview | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: ontdekken wat er nieuw is in Intune Azure Preview'
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/02/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e405363f9d0a89b1589b01d18ee8d2861b07ec60
ms.openlocfilehash: 70007f5501fba37964a0a54807c0e0f565510a74


---

# <a name="whats-new-in-the-microsoft-intune-preview"></a>Wat is er nieuw in Microsoft Intune Preview


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Als de openbare preview-versie verder wordt ontwikkeld en er meer functies worden toegevoegd, wordt u hier op de hoogte gebracht.

<!--## February 2017-->

<!--### Custom app categories <!--748805
You can now create, edit, and assign categories for apps you add to Intune. Currently, categories can only be specified in English.
See [How to add an app to Intune](/intune-azure/manage-apps/add-apps).-->

<!--### Display device categories <!--814654
You can now view the device category as a column in the device list. You can also edit the category from the properties section of the device properties blade.-->

## <a name="january-2017"></a>Januari 2017

### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748823--"></a>Toewijzen van line-of-business-apps, ongeacht of apparaten al dan niet zijn geregistreerd <!--748823-->
U kunt nu line-of-business-apps uit de store toewijzen aan gebruikers, ongeacht of hun apparaten al dan niet zijn geregistreerd bij Intune. Als een apparaat van gebruikers niet is geregistreerd bij Intune, moeten ze daarvoor de bedrijfsportalwebsite gebruiken en niet de bedrijfsportal-app. Zie [Wat is app-beheer](/intune-azure/manage-apps/what-is-app-management).

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>Oplossing voor het probleem waarbij iOS-apparaten inactief zijn of waarbij de beheerconsole er niet mee kan communiceren
Wanneer het contact tussen de apparaten van gebruikers en Intune verloren gaat, kunt u de gebruikers stappen voor probleemoplossing aandragen waarmee ze weer toegang krijgen tot de bedrijfsresources. Zie [Apparaten zijn inactief of de beheerconsole kan er niet mee communiceren](/intune-azure/enroll-devices/troubleshoot-device-enrollment#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## <a name="december-2016-initial-release"></a>December 2016 (oorspronkelijke versie)

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Integratie van onkostenbeheer voor telecom in de openbare preview-versie van Azure-portal<!--747605-->
We beginnen nu met preview-versies van de integratie met externe systemen voor onkostenbeheer voor telecom (TEM) in de Azure-portal. U kunt Intune gebruiken om limieten in te stellen voor gegevensgebruik, voor zowel nationaal als roaming. Hierbij beginnen we met [Saaswedo](http://www.saaswedo.com). Als u deze functie in uw proeftenant wilt inschakelen, neemt u [contact op met Microsoft-ondersteuning](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

- Apps uit een store op iOS-, Android- en Windows-apparaten implementeren en beheren
- LOB-apps (Line-Of-Business) op iOS-, Android- en Windows-apparaten implementeren en beheren
- Apps die zijn gekocht via het volume-aankoopprogramma, implementeren en beheren op iOS- en Windows-apparaten
- Web-apps implementeren en beheren op Android-, iOS- en Windows-apparaten
- Door iOS beheerde app-configuratieprofielen
- App-beveiligingsbeleid configureren en LOB-apps (Line-Of-Business) implementeren op apparaten die niet zijn geregistreerd met Intune
- VPN-profielen, VPN-, Wi-Fi-, e-mail- en certificaatprofielen per app
- Nalevingsbeleid
- Voorwaardelijke toegang voor Azure AD
- Voorwaardelijke toegang voor On-premises Exchange
- Apparaatinschrijving
- Op rollen gebaseerd toegangsbeheer

## <a name="deprecated-features-in-the-azure-portal"></a>Afgeschafte functies in Azure Portal

### <a name="support-for-row-by-row-review-of-hardware-identifiers"></a>Ondersteuning voor beoordeling van hardware-id's per rij
Azure Portal biedt geen ondersteuning voor de beoordeling van hardware-id's per rij voor IMEI-nummers en serienummers van Apple. U kunt in de klassieke Intune-console gegevens importeren uit een bestand met door komma's gescheiden waarden (CSV-bestand) en de bestaande gegevens voor afzonderlijke hardware-id's overschrijven. Azure Portal bevat één gestroomlijnde optie waarmee gegevens voor alle hardware-id's automatisch worden overschreven of nieuwe gegevens voor bestaande id's worden genegeerd.

#### <a name="how-this-affects-you"></a>Welke gevolgen heeft dit voor u
In Azure Portal kunt u niet per rij bepalen welke IMEI-apparaten (International Mobile Equipment Identity) moeten worden bijgewerkt. In de klassieke Intune-console blijft de ondersteuning voor deze functionaliteit gehandhaafd.

#### <a name="how-to-get-ready-for-this-change"></a>Hoe bereidt u zich voor op deze wijziging
Deze informatie wordt nu al verstrekt, zodat u uw ondersteuningsbeheerders van deze wijziging op de hoogte kunt brengen, als dit voor u van toepassing is. Deze wijziging valt samen met de overgang naar Azure Portal (naar verwachting in de eerste helft van 2017).


### <a name="support-for-default-corporate-device-enrollment-profiles-in-apple-dep"></a>Ondersteuning voor de standaardprofielen voor de registratie van bedrijfsapparaten in Apple DEP
Azure Portal biedt geen ondersteuning voor het standaardprofiel voor de registratie van bedrijfsapparaten voor Apple DEP-apparaatserienummers (Device Enrollment Program). Deze functionaliteit, die beschikbaar is in de klassieke Intune-console, wordt stopgezet om het onbedoeld toewijzen van profielen te voorkomen. In Azure Portal worden aan serienummers die zijn gesynchroniseerd vanuit een Apple DEP-account, in eerste instantie geen profiel voor de registratie van bedrijfsapparaten toegewezen.

#### <a name="how-this-affects-you"></a>Welke gevolgen heeft dit voor u
U kunt in Azure Portal geen standaardprofielbeleid voor alle Apple-apparaten instellen. In de klassieke Intune-console blijft de ondersteuning voor deze functionaliteit gehandhaafd.

#### <a name="how-to-get-ready-for-this-change"></a>Hoe bereidt u zich voor op deze wijziging
Deze informatie wordt nu al verstrekt, zodat u uw ondersteuningsbeheerders van deze wijziging op de hoogte kunt brengen, als dit voor u van toepassing is. Deze wijziging valt samen met de overgang naar Azure Portal (naar verwachting in de eerste helft van 2017).



<!--HONumber=Feb17_HO1-->


