---
title: Zoek de hoofdgebruiker van een Microsoft Intune-apparaat.
titleSuffix: ''
description: Zoek de hoofdgebruiker (of gebruikersaffiniteit) van een Intune-apparaat.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 312aee3752525ab2898c6d4e4ea06da685d1cdec
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71728361"
---
# <a name="find-the-primary-user-of-an-intune-device"></a>De hoofdgebruiker van een Intune-apparaat zoeken

De hoofdgebruiker, ook wel de gebruikersaffiniteit van het apparaat, is een eigenschap van elk Intune-apparaat. Aan een Intune-apparaat kan ofwel geen of één hoofdgebruiker zijn toegewezen. Wanneer er geen hoofdgebruiker is toegewezen, wordt het apparaat aangeduid als een 'gedeeld apparaat'.

## <a name="how-to-find-a-devices-primary-user"></a>De hoofdgebruiker van een apparaat zoeken

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **Apparaten** > Selecteer een apparaat.
3. Selecteer op de pagina **Overzicht** de optie **Meer weergeven** om de hoofdgebruiker te tonen.

## <a name="what-is-the-primary-user"></a>Wat is de hoofdgebruiker?
De eigenschap Hoofdgebruiker wordt gebruikt om een Intune-gebruiker met een licentie te koppelen aan hun apparaten in:
- De bedrijfsportal-app
- Websites van de eindgebruiker
- Gebruikerservaring voor IT-professionals, zoals probleemoplossingspagina's in de Azure-portal. Deze pagina's koppelen gebruikersaccounts aan apparaten met behulp van de hoofdgebruiker.    

### <a name="company-portal-app"></a>Bedrijfsportal-app
Voor de bedrijfsportal-app wordt aangenomen dat het gebruikersaccount waarmee wordt aangemeld bij de bedrijfsportal de hoofdgebruiker van het apparaat is. Als een andere gebruiker is toegewezen als hoofdgebruiker, wordt in de bedrijfsportal-app een waarschuwing weergegeven:

'Dit apparaat is al toegewezen aan iemand anders in uw organisatie. Neem contact op met uw bedrijfsondersteuning om hoofdgebruiker van het apparaat te worden. U kunt ook doorgaan naar de bedrijfsportal, maar de functionaliteit is dan beperkt.'

Als er geen hoofdgebruiker is toegewezen aan een Intune-apparaat, wordt dit door de bedrijfsportal-app gedetecteerd als een gedeeld apparaat. Gedeelde apparaten zijn visueel identificeerbaar aan de hand van het label 'Gedeeld' dat wordt weergegeven op de apparaattegel. In deze modus kan de bedrijfsportal-app nog steeds worden gebruikt om beschikbare apps aan te vragen en te installeren. Selfservice-acties (opnieuw instellen/naam wijzigen/buiten gebruik stellen) zijn echter niet beschikbaar.  

Apps moeten worden toegewezen aan een gebruikersgroep om voor gedeelde apparaten in de bedrijfsportal te worden weergegeven. Ze worden geïnstalleerd in de systeemcontext of in de gebruikerscontext, afhankelijk van hoe de app is geconfigureerd door de IT-beheerder. Zie voor meer informatie over app-context [Apps installeren op Windows 10-apparaten](../apps/apps-windows-10-app-deploy.md#installing-apps-on-windows-10-devices). Versie 10.3.4651.0 of hoger van de bedrijfsportal-app is vereist om deze functie te gebruiken.


## <a name="who-is-assigned-as-the-primary-user"></a>Wie is toegewezen als hoofdgebruiker?
Intune voegt tijdens of kort na de inschrijving automatisch een hoofdgebruiker toe aan apparaten. De registratiemethode bepaalt wanneer de hoofdgebruiker wordt toegevoegd aan een apparaat.

| Platform | Inschrijvingsmethode | Hoofdgebruiker toegewezen | Hoofdgebruiker wordt toegewezen |
| ---- | ---- | ---- | ---- |
| Windows | Werk- of schoolaccount toevoegen (door de gebruiker) | Gebruiker inschrijven | Tijdens inschrijving |   
| Windows | Moderne app-aanmelding (door de gebruiker) | Gebruiker inschrijven | Tijdens inschrijving | 
| Windows | Alleen inschrijven in MDM (door de gebruiker) | Gebruiker inschrijven | Tijdens inschrijving | 
| Windows | Azure AD-deelname (bij ingebruikname) | Gebruiker inschrijven | Tijdens inschrijving | 
| Windows | Azure AD-deelname (automatisch bij ingebruikname) | Gebruiker inschrijven | Tijdens inschrijving | 
| Windows | Alleen inschrijven in MDM | Gebruiker inschrijven | Tijdens inschrijving | 
| Windows | Hybride AADJ + automatische inschrijving GPO | Eerste gebruiker die zich aanmeldt bij Windows | Als de eerste gebruiker zich aanmeldt bij Windows| 
| Windows | Co-beheer | Eerste gebruiker die zich aanmeldt bij Windows | Als de eerste gebruiker zich aanmeldt bij Windows | 
| Windows | Azure AD-deelname (token voor bulkinschrijving) | Geen | Niet van toepassing | 
| Windows | Azure AD-deelname (modus voor automatische zelfimplementatie) | Geen | Niet van toepassing | 
| Platformoverschrijdend | Door gebruiker gestarte inschrijving met de bedrijfsportal-app | Gebruiker inschrijven | Tijdens inschrijving |
| Platformoverschrijdend | Apparaatinschrijvingsmanager (DEM) | DEM-gebruiker inschrijven | Tijdens inschrijving |
| iOS, macOS | Apple Automated Device Enrollment (DEP met gebruikersaffiniteit) | Gebruiker inschrijven | Tijdens inschrijving |
| iOS, macOS | Apple Automated Device Enrollment (DEP zonder gebruikersaffiniteit) | Geen | Niet van toepassing |
| Android | Android bij bedrijfseigendom, toegewezen apparaten | Geen | Niet van toepassing |

## <a name="primary-user-and-azure-ad-device-owner"></a>Hoofdgebruiker en de eigenaar van het Azure AD-apparaat
In sommige gevallen kan de hoofdgebruiker voor Intune verschillen van de eigenschap **Eigenaar** in Azure AD (te vinden via **Apparaten** > **Azure AD-apparaten**). De apparaateigenaar in Azure AD wordt toegevoegd tijdens de inschrijving van het apparaat in Azure Active Directory.

## <a name="next-steps"></a>Volgende stappen
[Beheer uw Intune-apparaten.](device-management.md)
