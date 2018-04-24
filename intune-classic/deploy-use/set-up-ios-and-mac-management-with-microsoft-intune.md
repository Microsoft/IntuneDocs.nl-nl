---
title: Set up iOS and Mac management
description: Beheer van mobiele apparaten (MDM) inschakelen voor iOS-apparaten zoals iPads en iPhones en tevens Mac OS X-apparaten met Microsoft Intune.
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 280efe7e7a5a1616ebab9abce7b7a5d78e321e7c
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="set-up-ios-and-mac-device-management"></a>iOS- en Mac-apparaatbeheer instellen

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Intune maakt beheer van mobiele apparaten (MDM) mogelijk voor iPads, iPhones, en macOS-apparaten en geeft gebruikers toegang tot zakelijke e-mail en apps. Een APNs-certificaat (Apple Push Notification-service) is vereist zodat Intune iOS- en Mac-apparaten kan beheren. Nadat het certificaat is toegevoegd aan Intune, kunnen gebruikers de bedrijfsportal-app installeren om hun apparaten in te schrijven, of de beheerder kan [beheer voor iOS-apparaten in bedrijfseigendom](enroll-corporate-owned-ios-devices-in-microsoft-intune.md) instellen.

1.  **Intune instellen**<br>
    Als u dit nog niet hebt gedaan, moet u het beheer van mobiele apparaten voorbereiden door de [beheerautoriteit voor mobiele apparaten in te stellen](prerequisites-for-enrollment.md#step-2-set-mdm-authority) op **Microsoft Intune** en MDM in te stellen.

2.  **Een aanvraag voor certificaatondertekening ophalen**<br>
    Als gebruiker met beheerdersrechten opent u de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) en gaat u naar **Beheer** &gt; **Mobile Device Management** &gt; **iOS en Mac OS X** &gt;**Een APNs-certificaat uploaden** en kiest u **De APNs-certificaataanvraag downloaden**. Sla het bestand met de aanvraag voor certificaatondertekening (.csr) lokaal op. Het CSR-bestand wordt gebruikt voor het aanvragen van een vertrouwensrelatiecertificaat uit de Apple Push Certificates Portal.

    ![Het dialoogvenster Een APNs-certificaat uploaden](../media/Intune-iOS-enrollment-with-apns.png)

3.  **Certificaat van Apple Push Notification Service ophalen**<br>
    Ga naar de [Apple Push Certificates-portal](http://go.microsoft.com/fwlink/?LinkId=269844) en meld u aan met de Apple ID van uw bedrijf om het APNs-certificaat te maken met het CSR-bestand. Nadat u in de Apple Push Certificates-portal **Uploaden** hebt gekozen, ontvangt u een .json-bestand dat niet kan worden gebruikt voor APN’s. Laat het downloaden voltooien en keer terug naar de Apple Push Certificates-portal voor **Certificaten voor servers van derden**. Kies **Downloaden**.

    Download het APNs-certificaat (.pem) en sla het bestand lokaal op.

    > [!NOTE]
    > U moet dit APNs-certificaat elk jaar vernieuwen (niet vervangen). Gebruik deze dezelfde Apple ID om u aan te melden bij de Apple Push Certificate-portal om het certificaat te vernieuwen, en gebruik vervolgens opnieuw de instructies in dit onderwerp om het certificaat te downloaden en vervolgens te uploaden naar Intune.

4.  **Het APNs-certificaat toevoegen aan Intune**<br>
    In de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) gaat u naar **Beheer** &gt; **Mobiele apparaten beheren** &gt; **iOS en Mac OS X** &gt; **Een APNs-certificaat uploaden**en kiest u **Het APNs-certificaat uploaden**. Ga naar het certificaatbestand (.pem), klik op **Openen** en voer uw **Apple ID** in. Met het APNs-certificaat kan Intune iOS-apparaten inschrijven en beheren door beleid naar ingeschreven mobiele apparaten te pushen.

5.  **Vertel uw gebruikers hoe ze hun apparaten moeten registreren om toegang te krijgen tot bedrijfsbronnen.**

    Zie [Uw iOS-apparaat registreren bij Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) of [Uw macOS-apparaat registreren bij Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos) voor inschrijvingsinstructies voor eindgebruikers. Het inschrijvingsproces laat gebruikers weten wat ze kunnen verwachten, en wat IT-beheerders wel en niet kunnen zien op hun apparaten.

    Zie de volgende artikelen voor meer informatie over andere taken voor eindgebruikers:
    - [Bronnen over de eindgebruikerservaring in Microsoft Intune](/intune/end-user-educate)
    - [Richtlijnen voor eindgebruikers van iOS- en Mac-apparaten](https://docs.microsoft.com/intune-user-help/using-your-ios-or-macOS-device-with-intune)

Als uw bedrijf of organisatie iOS-apparaten voor gebruikers koopt, kunnen die apparaten ook worden ingeschreven om te worden beheerd als [iOS-apparaten die bedrijfseigendom zijn](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

### <a name="see-also"></a>Zie ook
[Vereisten voor het registreren van apparaten in Microsoft Intune](prerequisites-for-enrollment.md)
