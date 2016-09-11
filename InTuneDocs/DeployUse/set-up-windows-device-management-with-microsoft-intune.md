---
title: Windows-apparaatbeheer instellen met Microsoft Intune | Microsoft Intune
description: "Schakel het beheer van mobiele apparaten (MDM) in voor Windows-pc’s, waaronder Windows 10-apparaten met Microsoft Intune."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 06d6c8ce97ba6a259055e94f0eba87f7c5a96531
ms.openlocfilehash: fae2aa496ec38d9ddc2cb6800bed10ccb32fd154


---

# Windows apparaatbeheer instellen
U vindt [hier](../enduser/using-your-windows-device-with-intune.md) meer informatie over het instellen van uw Windows-apparaat.

Met Intune kunt u BYOD ('Bring Your Own Device') instellen om Windows-pc’s in te schrijven en toegang te geven tot bedrijfse-mail en apps. In combinatie met Azure Active Directory beschikt u hiermee ook over een snelle manier om nieuwe Windows 10-apparaten onder beheer te stellen en toegang te krijgen tot bronnen zonder een nieuwe installatiekopie op de computer te installeren. Na inschrijving kunnen gebruikers zich aanmelden en kunnen op hun apparaten beleid, apps en instellingen worden toegepast met behulp van de Intune-beheerconsole. Als u dit wilt, kunt u ook [Windows Phone-beheer instellen met Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md) en [computers beheren met Intune-clientsoftware](manage-windows-pcs-with-microsoft-intune.md)

Door een DNS CNAME te maken, kunnen gebruikers verbinding maken met Intune en bij Intune worden ingeschreven zonder een servernaam te hoeven opgeven.

### Windows apparaatbeheer instellen

  1.  Maak een **CNAME** DNS-bronrecord voor het domein van uw bedrijf. Als de website van uw bedrijf bijvoorbeeld contoso.com is, maakt u een CNAME in DNS die EnterpriseEnrollment.contoso.com omleidt naar EnterpriseEnrollment-s.manage.microsoft.com. Hoewel de CNAME-DNS-vermelding optioneel is voor de inschrijving van Windows-apparaten, wordt u aangeraden om één of meer records te maken, indien nodig, zodat het inschrijvingsproces van het Windows-apparaat gemakkelijker verloopt. Indien geen CNAME-record wordt gevonden, wordt de gebruiker gevraagd de MDM-servernaam handmatig in te voeren.

  Als er meer dan één gecontroleerd domein is, maakt u een CNAME-record voor elk domein. De CNAME-resourcerecords moeten de volgende informatie bevatten:

  |TYPE|Hostnaam|Verwijst naar|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 uur|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 uur|

  Het kan 72 uur duren voordat wijzigingen in DNS-records zijn doorgegeven. U kunt de DNS-wijziging in Intune pas controleren wanneer de DNS-record is doorgegeven.

  **EnterpriseEnrollment-s.manage.microsoft.com**: biedt ondersteuning voor een omleiding naar de Intune-service met domeinherkenning van de domeinnaam via het e-mailadres van het domein

  **EnterpriseRegistration.windows.net**: ondersteunt Windows 8.1- en Windows 10 Mobile-apparaten die worden geregistreerd bij Azure Active Directory met hun werk- of schoolaccount

  2.  Klik in de [Intune-beheerconsole](http://manage.microsoft.com) op **Beheer** &gt; **Mobile Device Management** &gt; **Windows**.
  ![Het dialoogvenster Windows-apparaatbeheer](../media/enroll-intune-winenr.png)

  3.  Typ de URL van het geverifieerde domein voor de bedrijfswebsite in het vak **Geef een geverifieerde domeinnaam op** en klik vervolgens op **Automatische detectie testen**.

  4.  Uw gebruikers moeten weten hoe ze hun apparaten kunnen inschrijven en wat ze kunnen verwachten als deze onder beheer zijn gebracht.
      - [Wat u uw eindgebruikers vertelt over het gebruik van Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
      - [Richtlijnen voor eindgebruikers van Windows-apparaten](../enduser/using-your-windows-device-with-intune.md)

### Zie tevens
[Bereid u voor op het registreren van apparaten in Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Aug16_HO1-->


