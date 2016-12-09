---
title: Windows 10 Mobile- en Windows Phone-beheer instellen | Microsoft Intune
description: Schakel het beheer van mobiele apparaten (MDM) in voor Windows 10 Mobile- of Windows Phone-apparaten met Microsoft Intune.
keywords: 
author: staciebarker
manager: angrobe
ms.date: 11/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5615051-2dd1-453b-9872-d3fdcefb2cb8
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c59707ba2967b069dc30aee71d2642e91d71b23b
ms.openlocfilehash: 3141d4b2ad1a21e2ac5ba7b6cafb74f567d07f7a


---


# <a name="set-up-windows-phone-and-windows-10-mobile-management-with-microsoft-intune"></a>Windows Phone- en Windows 10 Mobile-beheer met Microsoft Intune instellen

Als Intune-beheerder kunt u de registratie en het beheer voor Windows 10 Mobile- en Windows Phone-apparaten op twee manieren inschakelen:

- **[Automatische registratie met Azure Active Directory](#azure-active-directory-enrollment)**: Windows 10- en Windows 10 Mobile-gebruikers registreren hun apparaat door een werk- of schoolaccount toe te voegen op het apparaat
- **[Registreren via de bedrijfsportal](#company-portal-app-enrollment)**: gebruikers van Windows Phone 8.1 en hoger kunnen hun apparaten registreren door de bedrijfsportal-app te downloaden en te installeren en vervolgens de inloggegevens van hun werk- of schoolaccount in de app in te voeren.


[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="company-portal-app-enrollment"></a>Registratie via de bedrijfsportal-app
U kunt toestaan dat gebruikers hun apparaat installeren en registreren met de bedrijfsportal-app van Intune. Als u DNS CNAME-bronrecords maakt, kunnen gebruikers verbinding maken met Intune en bij Intune worden ingeschreven zonder een servernaam te hoeven opgeven.

1.  **Intune instellen**<br>Als u dit nog niet hebt gedaan, moet u het beheer van mobiele apparaten voorbereiden door de [autoriteit voor het beheer voor mobiele apparaten (MDM) in te stellen](prerequisites-for-enrollment.md#step-2-set-mdm-authority) op **Microsoft Intune** en vervolgens MDM in te stellen.

2.  **CNAME-records maken** (optioneel)<br>Maak **CNAME**-DNS-bronrecords voor uw bedrijfsdomein. Als de website van uw bedrijf bijvoorbeeld contoso.com is, maakt u een CNAME in DNS die EnterpriseEnrollment.contoso.com omleidt naar enterpriseenrollment-s.manage.microsoft.com.

    Hoewel het maken van CNAME-DNS-vermeldingen optioneel is, maken CNAME-records het voor gebruikers makkelijker om zich in te schrijven. Als er geen CNAME-inschrijvingsrecord wordt gevonden, wordt gebruikers gevraagd de MDM-servernaam handmatig in te voeren, https://manage.microscoft.com.

    Als u in DNS een CNAME hebt geconfigureerd waarmee EnterpriseEnrollment.contoso.com wordt omgeleid naar manage.microsoft.com, is het raadzaam om dit te vervangen door een CNAME in DNS waarmee EnterpriseEnrollment.contoso.com wordt omgeleid naar enterpriseenrollment-s.manage.microsoft.com. Deze wijziging wordt aanbevolen, omdat het eindpunt manage.microsoft.com voor inschrijvingen in een toekomstige versie wordt afgeschaft.

    Als er meer dan één gecontroleerd domein is, maakt u een CNAME-record voor elk domein. De CNAME-resourcerecords moeten de volgende informatie bevatten:

  |TYPE|Hostnaam|Verwijst naar|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.bedrijfsdomein.com|EnterpriseEnrollment-s.manage.microsoft.com |1 uur|
  |CNAME|EnterpriseRegistration.bedrijfsdomein.com|EnterpriseRegistration.windows.net|1 uur|

  `EnterpriseEnrollment-s.manage.microsoft.com`: biedt ondersteuning voor een omleiding naar de Intune-service met domeinherkenning vanuit de domeinnaam van het e-mailadres

  `EnterpriseRegistration.windows.net`: biedt ondersteuning voor Windows 8.1- en Windows 10 Mobile-apparaten die met een werk- of schoolaccount bij Azure Active Directory worden geregistreerd

  Als uw bedrijf meerdere domeinen heeft voor gebruikersreferenties, maakt u CNAME-records voor elk domein.

  Als de website van uw bedrijf bijvoorbeeld contoso.com is, maakt u een CNAME in DNS die EnterpriseEnrollment.contoso.com omleidt naar EnterpriseEnrollment-s.manage.microsoft.com. Het kan 72 uur duren voordat wijzigingen in DNS-records zijn doorgegeven. U kunt de DNS-wijziging in Intune pas controleren wanneer de DNS-record is doorgegeven.

3.  **CNAME controleren**<br>Kies in de [Intune-beheerconsole](http://manage.microsoft.com) de optie **Beheer** &gt; **Mobile Device Management** &gt; **Windows Phone**. Voer de URL in van het geverifieerde domein voor de bedrijfswebsite in het vak **Geef een geverifieerde domeinnaam op** en kies vervolgens **Automatische detectie testen**.

    ![Dialoogvenster Instellingen voor beheer van mobiele apparaten voor Windows](../media/windows-phone-enrollment.png)

4.  **Optionele stappen**<br>De stap **Sideloadsleutels toevoegen** is niet nodig voor Windows 10. De stap **Certificaat voor ondertekening van programmacode uploaden** is alleen nodig als u Line-of-Business-apps (LOB) die niet beschikbaar zijn vanuit Windows Store distribueert op apparaten.

5.  **Laat uw gebruikers weten hoe ze hun apparaten moeten registreren om toegang te krijgen tot bedrijfsbronnen.**

    Zie [Uw Windows-apparaat inschrijven bij Intune](../enduser/enroll-your-device-in-intune-windows.md) voor inschrijvingsinstructies voor eindgebruikers. U kunt uw gebruikers ook doorsturen naar [Wat kan uw IT-beheerder zien wanneer u uw apparaat registreert bij Intune?](../enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md)

    Zie de volgende artikelen voor meer informatie over andere taken voor eindgebruikers:
    - [Wat u uw eindgebruikers vertelt over het gebruik van Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
    - [Richtlijnen voor eindgebruikers van Windows-apparaten](../enduser/using-your-windows-device-with-intune.md)

Verder hoeft u niets te doen, tenzij u de bedrijfsportal op apparaten wilt implementeren.  Stap 2 en 3 in de beheerconsole kunnen worden genegeerd.



<!--HONumber=Dec16_HO2-->


