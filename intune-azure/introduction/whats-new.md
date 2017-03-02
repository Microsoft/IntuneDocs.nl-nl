---
title: Wat is er nieuw in Microsoft Intune Preview | Intune Azure Preview | Microsoft Docs
description: Ontdekken wat er nieuw is in Intune Azure Preview
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9852fdb9d1bfeede4931f0ead2fa0898dfcacb0b
ms.openlocfilehash: a05c7464b3f2fbca467d44218904671529320dda
ms.lasthandoff: 02/15/2017

---

# <a name="whats-new-in-the-microsoft-intune-preview"></a>Wat is er nieuw in Microsoft Intune Preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Als de openbare preview-versie verder wordt ontwikkeld en er meer functies worden toegevoegd, wordt u hier op de hoogte gebracht.

## <a name="february-2017"></a>Februari 2017

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Mogelijkheid om de inschrijving van mobiele apparaten te beperken <!--747600, 795782-->
Er zijn in Intune nieuwe inschrijvingsbeperkingen toegevoegd die bepalen welke platforms voor mobiele apparaten kunnen worden ingeschreven. Intune onderscheidt platforms voor mobiele apparaten als iOS, Mac OS, Android, Windows en Windows Mobile.

* Een beperking voor de registratie van mobiele apparaten, betekent niet dat de PC-clientregistratie ook is beperkt.  
* Alleen voor iOS en Android geldt er een extra optie voor het blokkeren van de inschrijving van apparaten die in persoonlijk eigendom zijn.

Intune markeert alle nieuwe apparaten als persoonlijk, tenzij de IT-beheerder actie onderneemt om deze te markeren als bedrijfseigen, zoals uitgelegd in [dit artikel](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices).

### <a name="view-all-actions-on-managed-devices---677150--"></a>Alle acties voor beheerde apparaten weergeven <!--677150-->
Er is een nieuw rapport __Apparaatacties__, waarin wordt weergegeven wie externe acties, zoals het herstellen van fabrieksinstellingen, op apparaten heeft uitgevoerd. In dit rapport wordt ook de status van de actie getoond. Zie [Wat is apparaatbeheer?](https://docs.microsoft.com/intune-azure/manage-devices/what-is).

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Niet-beheerde apparaten hebben toegang tot toegewezen apps <!--664691-->
Als onderdeel van de ontwerpwijzigingen op de bedrijfsportalwebsite kunnen iOS- en Android-gebruikers op hun niet-beheerde apparaten apps installeren die aan hen zijn toegewezen als 'beschikbaar zonder inschrijving'. Gebruikers kunnen zich met behulp van hun Intune-referenties aanmelden bij de bedrijfsportalwebsite en de lijst met aan hen toegewezen apps bekijken. De app-pakketten van de 'beschikbaar zonder inschrijving'-apps kunnen worden gedownload via de bedrijfsportalwebsite. Deze wijziging is niet van toepassing op apps die pas na inschrijving kunnen worden geïnstalleerd, omdat gebruikers wordt gevraagd hun apparaat in te schrijven als zij deze apps willen installeren.

### <a name="custom-app-categories---748805--"></a>Aangepaste app-categorieën <!--748805-->
U kunt nu categorieën maken, bewerken en toewijzen voor apps die u aan Intune toevoegt. Categorieën kunnen momenteel alleen worden opgegeven in het Engels.
Zie [Een app toevoegen aan Intune](/intune-azure/manage-apps/add-apps).

### <a name="display-device-categories---814654--"></a>Apparaatcategorieën weergeven <!--814654-->
U kunt nu de apparaatcategorie als kolom in de lijst met apparaten weergeven. U kunt ook de categorie uit de sectie met eigenschappen van de apparaateigenschappenblade bewerken. Zie [Een app toevoegen aan Intune](/intune-azure/manage-apps/add-apps). 

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

