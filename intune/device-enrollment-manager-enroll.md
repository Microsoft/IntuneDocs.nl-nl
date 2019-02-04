---
title: Apparaten inschrijven met een apparaatinschrijvingsmanageraccount
titlesuffix: Microsoft Intune
description: Gebruik het manageraccount voor apparaatregistratie om apparaten in te registreren.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: be348840df2e1d7864b0c1c57efbb7abcb698392
ms.sourcegitcommit: 6f2f2fa70f4e47fa5ad2f3c536ba7116e1bd1d05
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2019
ms.locfileid: "55199384"
---
# <a name="enroll-devices-in-intune-by-using-a-device-enrollment-manager-account"></a>Apparaten registreren in Intune met een manageraccount voor apparaatregistratie

U kunt maximaal 1000 mobiele apparaten inschrijven met één Azure Active Directory-account als u gebruikmaakt van een apparaatinschrijvingsmanageraccount (DEM). DEM is een Intune-machtiging die kan worden toegepast op een AAD-gebruikersaccount; hiermee kan de gebruiker maximaal 1000 apparaten inschrijven. Een DEM-account is handig voor gebruik in scenario's waarin apparaten worden ingeschreven en voorbereid vóórdat ze aan de gebruikers van de apparaten worden overhandigd.

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>Beperkingen van apparaten die zijn ingeschreven bij een DEM-account

DEM-gebruikersaccounts en apparaten die zijn ingeschreven met een DEM-gebruikersaccount hebben de volgende beperkingen:

  - Wissen kan niet worden uitgevoerd vanuit de bedrijfsportal. Apparaten die door DEM-gebruikersaccounts zijn ingeschreven, kunnen worden gewist via Intune (Azure Portal).
  - Alleen het lokale apparaat wordt weergegeven in de bedrijfsportal-app of op de website.
  - DEM-gebruikersaccounts kunnen geen Apple Volume Purchase Program-apps (VPP) met gebruikerslicenties gebruiken vanwege de Apple ID-vereisten per gebruiker voor het beheer van apps.
  - Apparaten kunnen VPP-apps installeren als ze over Apple VPP-apparaatlicenties beschikken.
  - Apparaten worden geblokkeerd voor Voorwaardelijke toegang, met uitzondering van Windows 10 1803+
  - Elk apparaat dat is ingeschreven met een DEM-account moet een eigen Intune-apparaatlicentie hebben.


## <a name="add-a-device-enrollment-manager"></a>Een apparaatinschrijvingsmanager toevoegen

1.  Ga naar [Intune in de Azure-portal](https://aka.ms/intuneportal) en kies **Apparaatregistratie** > **Beheerders voor apparaatregistratie**.

2.  Selecteer **Toevoegen**.

3.  Voer op de blade **Gebruiker toevoegen** een UPN-naam (User Principal Name) in voor de DEM-gebruiker en selecteer **Toevoegen**. De DEM-gebruiker wordt toegevoegd aan de lijst met DEM-gebruikers.

## <a name="permissions-for-dem"></a>Machtigingen voor DEM

De Azure AD-rollen Globale beheerder of Intune-servicebeheerder zijn vereist voor
- het toewijzen van DEM-machtigingen aan een Azure AD-gebruikersaccount
- het bekijken van alle DEM-gebruikers

Als een gebruiker niet over de rol van globale beheerder of Intune-servicebeheerder beschikt, maar wel leesmachtigingen voor de toegewezen DEM-rol heeft, kan de gebruiker alleen de zelfgemaakte DEM-gebruikers weergeven.


## <a name="remove-device-enrollment-manager-permissions"></a>Machtigingen voor een apparaatinschrijvingsmanager verwijderen

Het verwijderen van een apparaatinschrijvingsmanager is niet van invloed op ingeschreven apparaten.

**Een apparaatinschrijvingsmanager verwijderen**

1. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) de optie **Apparaatinschrijving** en kies vervolgens **Apparaatinschrijvingsmanagers**.
2. Klik op de blade **Apparaatinschrijvingsmanagers** op de DEM-gebruiker en selecteer **Verwijderen**.

