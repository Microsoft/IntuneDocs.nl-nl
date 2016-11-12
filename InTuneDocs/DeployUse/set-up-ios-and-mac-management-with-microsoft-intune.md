---
title: iOS- en Mac-beheer instellen | Microsoft Intune
description: Beheer van mobiele apparaten (MDM) inschakelen voor iOS-apparaten zoals iPads en iPhones en tevens Mac OS X-apparaten met Microsoft Intune.
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b3f6323912707d56d23380217a07e6474593d83f
ms.openlocfilehash: f93f7bfe99e878691dccd24c124a781c8607e7c6


---

# iOS- en Mac-apparaatbeheer instellen
Zie [Uw iOS- of Mac OS X-apparaat gebruiken met Intune](../enduser/using-your-ios-or-mac-os-x-device-with-intune.md) voor informatie over het instellen van uw iOS- of Mac-apparaat.

Intune maakt beheer van mobiele apparaten (MDM) mogelijk voor iPads, iPhones, en Mac OS X-apparaten en geeft gebruikers toegang tot zakelijke e-mail en apps. Een APNs-certificaat (Apple Push Notification-service) is vereist zodat Intune iOS- en Mac-apparaten kan beheren. Nadat het certificaat is toegevoegd aan Intune, kunnen gebruikers de bedrijfsportal-app installeren om hun apparaten in te schrijven, of de beheerder kan [beheer voor iOS-apparaten in bedrijfseigendom](enroll-corporate-owned-ios-devices-in-microsoft-intune.md) instellen.

1.  **Intune instellen**<br>
    Als u dit nog niet hebt gedaan, moet u het beheer van mobiele apparaten voorbereiden door de [beheerautoriteit voor mobiele apparaten in te stellen](prerequisites-for-enrollment.md#set-mobile-device-management-authority) op **Microsoft Intune** en MDM in te stellen.

2.  **Certificaatondertekening aanvragen**<br>
    Als gebruiker met beheerdersrechten opent u de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) en gaat u naar **Beheer** &gt; **Mobile Device Management** &gt; **iOS en Mac OS X** &gt;**Een APNs-certificaat uploaden** en kiest u **De APNs-certificaataanvraag downloaden**. Sla het bestand met de aanvraag voor certificaatondertekening (.csr) lokaal op. Het CSR-bestand wordt gebruikt voor het aanvragen van een vertrouwensrelatiecertificaat uit de Apple Push Certificates Portal.

    ![Het dialoogvenster Een APNs-certificaat uploaden](../media/Intune-iOS-enrollment-with-apns.png)

3.  **APNs-certificaat aanvragen**<br>
    Ga naar de [Apple Push Certificates-portal](http://go.microsoft.com/fwlink/?LinkId=269844) en meld u aan met de Apple-id van uw bedrijf om het APNs-certificaat te maken met het .csr-bestand. Nadat u in de Apple Push Certificates-portal **Uploaden** hebt gekozen, ontvangt u een .json-bestand dat niet kan worden gebruikt voor APN’s. Laat het downloaden voltooien en keer terug naar de Apple Push Certificates-portal voor **Certificaten voor servers van derden**. Kies **Downloaden**.

    Download het APNs-certificaat (.pem) en sla het bestand lokaal op. Deze Apple-id moet later worden gebruikt om uw APNs-certificaat te vernieuwen.

4.  **Het APNs-certificaat toevoegen aan Intune**<br>
    In de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) gaat u naar **Beheer** &gt; **Mobiele apparaten beheren** &gt; **iOS en Mac OS X** &gt; **Een APNs-certificaat uploaden**en kiest u **Het APNs-certificaat uploaden**. Ga naar het certificaatbestand (.pem), klik op **Openen** en voer uw **Apple-id** in. Met het APNs-certificaat kan Intune iOS-apparaten inschrijven en beheren door beleid naar ingeschreven mobiele apparaten te pushen.

5.  **Vertel gebruikers hoe ze met de bedrijfsportal toegang krijgen tot bronnen**<br>
    Uw gebruikers moeten weten hoe ze hun apparaten kunnen inschrijven en wat ze kunnen verwachten nadat deze onder beheer zijn gebracht.
    - [Wat u uw eindgebruikers vertelt over het gebruik van Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
    - [Richtlijnen voor eindgebruikers van iOS- en Mac-apparaten](../enduser/using-your-ios-or-mac-os-x-device-with-intune.md)

Als uw bedrijf of organisatie iOS-apparaten voor gebruikers koopt, kunnen die apparaten ook worden ingeschreven om te worden beheerd als [iOS-apparaten die bedrijfseigendom zijn](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

### Zie ook
[Vereisten voor het registreren van apparaten in Microsoft Intune](prerequisites-for-enrollment.md)



<!--HONumber=Oct16_HO3-->


