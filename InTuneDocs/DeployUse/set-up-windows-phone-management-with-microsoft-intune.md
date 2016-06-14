---
# required metadata

title: Windows 10 Mobile- en Windows Phone-beheer met Microsoft Intune instellen | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f5615051-2dd1-453b-9872-d3fdcefb2cb8

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Windows Phone- en Windows 10 Mobile-beheer met Microsoft Intune instellen
Voordat u Windows 10 Mobile- of Windows Phone-apparaten met Microsoft Intune kunt beheren, moeten de apparaten met Intune kunnen communiceren. U kunt dit vereenvoudigen door een DNS-record te maken, zodat gebruikers het serveradres niet hoeven in te voeren. Hieronder worden de stappen beschreven om inschrijving voor gebruikers te vereenvoudigen.  

In de meeste scenario’s kunnen gebruikers de bedrijfsportal-app installeren vanuit de Windows Store. Als u Windows Phone 8.0-apparaten beheert of de bedrijfsportal voor Windows Phone-apparaten moet implementeren, moet u bovendien de bedrijfsportal-app downloaden en ondertekenen. Zie [Windows Phone 8.0-beheer instellen](set-up-windows-phone-8.0-management-with-microsoft-intune.md).

1.  **Intune instellen**
    Als u dit nog niet hebt gedaan, moet u het beheer van mobiele apparaten voorbereiden door [de beheerautoriteit voor mobiele apparaten in te stellen](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority) als **Microsoft Intune** en MDM in te stellen.

2.  **Een DNS-alias voor het inschrijvingsserveradres** (optioneel)

    Door een DNS-alias (CNAME-recordtype) te maken, kunnen gebruikers hun apparaten eenvoudiger inschrijven. Als u geen DNS-alias maakt, moeten gebruikers

  1.  Maak **CNAME**-DNS-bronrecords voor uw bedrijfsdomein. Als de website van uw bedrijf bijvoorbeeld contoso.com is, maakt u een CNAME in DNS die EnterpriseEnrollment.contoso.com omleid naar manage.microsoft.com. Als er meerdere geverifieerd domeinen zijn, maakt u een CNAME-record voor elk domein. De CNAME-bronrecords moeten de volgende informatie bevatten:

      |TYPE|Hostnaam|Verwijst naar|TTL|
      |--------|-------------|-------------|-------|
      |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 uur|
      |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 uur|

      Het kan 72 uur duren voordat wijzigingen in DNS-records zijn doorgegeven. U kunt de DNS-wijziging in Intune pas controleren wanneer de DNS-record is doorgegeven.

      **EnterpriseEnrollment-s.manage.microsoft.com**: biedt ondersteuning voor een omleiding naar de Intune-service met domeinherkenning van de domeinnaam via het e-mailadres van het domein

      **EnterpriseRegistration.windows.net**: ondersteunt Windows 8.1- en Windows 10 Mobile-apparaten die worden geregistreerd bij Azure Active Directory met hun werk- of schoolaccount

    2.  Klik in de [Intune-beheerconsole](http://manage.microsoft.com) op **Beheer** &gt; **Mobile Device Management** &gt; **Windows Phone**.

      ![Dialoogvenster Instellingen voor beheer van mobiele apparaten voor Windows](../media/windows-device-enrollment.png)

    3.  Typ de URL van het geverifieerde domein voor de bedrijfswebsite in het vak **Geef een geverifieerde domeinnaam op** en klik op **Automatische detectie testen**..



Verder hoeft u niets te doen, tenzij u de bedrijfsportal op apparaten wilt implementeren.  Stap 2, 3 en 4 in de beheerconsole kunnen worden genegeerd.


<!--HONumber=May16_HO1-->


