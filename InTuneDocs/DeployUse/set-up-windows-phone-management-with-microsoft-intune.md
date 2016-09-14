---
title: Windows 10 Mobile- en Windows Phone-beheer instellen | Microsoft Intune
description: Schakel het beheer van mobiele apparaten (MDM) in voor Windows 10 Mobile- of Windows Phone-apparaten met Microsoft Intune.
keywords: 
author: NathBarn
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5615051-2dd1-453b-9872-d3fdcefb2cb8
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ebb1648ab13d31a2ba1ab17615814be8dda8a08c
ms.openlocfilehash: 76aaa33832dc1b765e248f85f739a4955ca90e2d


---


# Windows Phone- en Windows 10 Mobile-beheer met Microsoft Intune instellen

Als Intune-beheerder kunt u de registratie en het beheer voor Windows 10 Mobile- en Windows Phone-apparaten op twee manieren inschakelen:

- **[Automatische registratie met Azure AD](#azure-active-directory-enrollment)**: Windows 10- en Windows 10 Mobile-gebruikers registreren hun apparaat door een werk- of schoolaccount toe te voegen op het apparaat
- **[Registreren via de bedrijfsportal](#company-portal-app-enrollment)**: gebruikers kunnen apparaten met Windows Phone 8.1 en hoger registreren door de bedrijfsportal-app te downloaden en te installeren en vervolgens de inloggegevens van hun werk- of schoolaccount in de app in te voeren.


[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## Registratie via de bedrijfsportal-app
U kunt toestaan dat gebruikers de Intune-bedrijfsportal-app op hun apparaat installeren en hun apparaat via de app registreren. Door een DNS CNAME te maken, kunnen gebruikers verbinding maken met Intune en bij Intune worden ingeschreven zonder een servernaam te hoeven opgeven. Als u Windows Phone 8.0-apparaten beheert of de bedrijfsportal voor Windows Phone-apparaten moet implementeren, moet u bovendien de bedrijfsportal-app downloaden en ondertekenen. Zie [Windows Phone 8.0-beheer instellen](set-up-windows-phone-8.0-management-with-microsoft-intune.md).

1.  **Intune instellen**<br>Als u dit nog niet hebt gedaan, moet u het beheer van mobiele apparaten voorbereiden door de [beheerautoriteit voor mobiele apparaten in te stellen](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority) op **Microsoft Intune** en MDM in te stellen.

2.  **CNAME-records maken** (optioneel)<br>Maak **CNAME**-DNS-bronrecords voor uw bedrijfsdomein. Als de website van uw bedrijf bijvoorbeeld contoso.com is, maakt u een CNAME in DNS die EnterpriseEnrollment.contoso.com omleid naar manage.microsoft.com. Als er meer dan één gecontroleerd domein is, maakt u een CNAME-record voor elk domein. De CNAME-resourcerecords moeten de volgende informatie bevatten:

  |TYPE|Hostnaam|Verwijst naar|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 uur|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 uur|
  Het kan 72 uur duren voordat wijzigingen in DNS-records zijn doorgegeven. U kunt de DNS-wijziging in Intune pas controleren wanneer de DNS-record is doorgegeven.

  `EnterpriseEnrollment-s.manage.microsoft.com` – Biedt ondersteuning voor een omleiding naar de Intune-service met domeinherkenning vanuit de domeinnaam van het e-mailadres

  `EnterpriseRegistration.windows.net` – Biedt ondersteuning voor Windows 8.1- en Windows 10 Mobile-apparaten die met een werk- of schoolaccount bij Azure Active Directory worden geregistreerd

  Als uw bedrijf meerdere domeinen heeft voor gebruikersreferenties, maakt u CNAME-records voor elk domein.

  Als de website van uw bedrijf bijvoorbeeld contoso.com is, maakt u een CNAME in DNS die EnterpriseEnrollment.contoso.com omleidt naar EnterpriseEnrollment-s.manage.microsoft.com. Het kan 72 uur duren voordat wijzigingen in DNS-records zijn doorgegeven. U kunt de DNS-wijziging in Intune pas controleren wanneer de DNS-record is doorgegeven.

3.  **CNAME controleren**<br>Klik in de [Intune-beheerconsole](http://manage.microsoft.com) op **Beheer** &gt; **Mobile Device Management** &gt; **Windows Phone**. Typ de URL van het geverifieerde domein voor de bedrijfswebsite in het vak **Geef een geverifieerde domeinnaam op** en klik vervolgens op **Automatische detectie testen**.

    ![Dialoogvenster Instellingen voor beheer van mobiele apparaten voor Windows](../media/windows-phone-enrollment.png)

4.  **Optionele stappen**<br>De stap **Sideloadsleutels toevoegen** is niet nodig voor Windows 10. De stap **Certificaat voor ondertekening van programmacode uploaden** is alleen nodig als u Line-of-Business-apps (LOB) wilt distribueren op apparaten die niet beschikbaar zijn vanuit Windows Store. [Meer informatie](set-up-windows-phone-8.0-management-with-microsoft-intune.md)

5.  **Gebruikers informeren**<br>Uw gebruikers moeten weten hoe ze hun apparaten kunnen inschrijven en wat ze kunnen verwachten als deze onder beheer zijn gebracht.
    - [Wat u uw eindgebruikers vertelt over het gebruik van Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
    - [Richtlijnen voor eindgebruikers van Windows-apparaten](../enduser/using-your-windows-device-with-intune.md)

Verder hoeft u niets te doen, tenzij u de bedrijfsportal op apparaten wilt implementeren.  Stap 2 en 3 in de beheerconsole kunnen worden genegeerd.



<!--HONumber=Aug16_HO5-->


