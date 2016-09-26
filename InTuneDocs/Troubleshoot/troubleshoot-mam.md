---
title:
- Problemen met Mobile Application Management oplossen | Microsoft Intune
description: 
keywords: 
author: karaman
manager: angerobe
ms.date: 09/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
translationtype: Human Translation
ms.sourcegitcommit: 9cfb3694b2fae919fd0554a6e21b497cdcf19c72
ms.openlocfilehash: f33e8de82ee07bb4571a5bfaff63af72f9086376


---

# Problemen met Mobile Application Management oplossen

Begin hier als u problemen ondervindt met Mobile Application Management. Dit onderwerp bevat oplossingen voor een aantal veelvoorkomende problemen.


**Probleem:** MAM zonder registratiebeleid via de Azure-console wordt niet toegepast op de Skype voor Bedrijven-app op iOS- en Android-apparaten.

Oplossing: Skype voor Bedrijven moet worden ingesteld voor moderne authenticatie.  Volg de instructies in [Enable your tenant for modern authentication](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) (Moderne authenticatie inschakelen voor uw tenant) om moderne authenticatie in te stellen voor Skype.

**Probleem:** MAM zonder registratiebeleid wordt voor geen enkele gebruiker toegepast op (ondersteunde Office-app) [https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners].
 
Oplossing: controleer of de gebruiker een licentie heeft voor Intune.  

**Probleem:** een IT-beheerder kan geen MAM-beleid configureren in Azure Portal.

Oplossing: de volgende rollen hebben toegang tot Azure Portal:

- Globale beheerder, die u kunt instellen in de [Office-portal](http://portal.office.com/).
- Eigenaar, die u kunt instellen in [Azure Portal](https://portal.azure.com/).
- Bijdrager, die u kunt instellen in [Azure Portal](https://portal.azure.com/).

Raadpleeg [Voorbereidingen voor het configureren van beleid voor het beheer van mobiele apps (Mobile App Management) met Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) voor hulp bij het instellen van deze rollen. 

**Probleem:** in het app-rapport staan geen gebruikers waarop het MAM-beleid onlangs is toegepast.

Oplossing: als het MAM-beleid onlangs op een gebruiker is toegepast, kan het tot 24 uur duren voor die gebruiker in rapporten als gebruiker in de doelgroep wordt weergegeven. 

**Probleem:** het kan tot wel 8 uur duren voordat beleidswijzigingen/-updates worden toegepast.  

Oplossing: eindgebruikers kunnen zich bij de app afmelden en weer aanmelden om synchroniseren met de service af te dwingen.  

**Probleem:** MAM-beleid wordt niet toegepast op Apple DEP-apparaten

Oplossing: zorg ervoor dat u gebruikersaffiniteit gebruikt bij het Device Enrollment Program (DEP) van Apple. Gebruikersaffiniteit is vereist voor elke app die authenticatie van gebruikers vereist volgens het DEP.
Raadpleeg [iOS-apparaten in bedrijfseigendom met het Device Enrollment Program inschrijven](https://docs.microsoft.com/en-us/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) voor meer informatie over iOS DEP-registratie.


### Zie tevens
- [De Mobile Application Management-configuratie valideren](https://docs.microsoft.com/en-us/intune/deploy-use/validate-mobile-application-management)
- [Voorbereidingen voor het configureren van beleid voor het beheer van mobiele apps (Mobile App Management) met Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) 





<!--HONumber=Sep16_HO2-->


