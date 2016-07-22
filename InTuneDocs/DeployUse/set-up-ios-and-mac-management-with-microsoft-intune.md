---
# required metadata

title: iOS- en Mac-beheer instellen met Microsoft Intune | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# iOS- en Mac-apparaatbeheer instellen
Met Microsoft Intune kunt u BYOD-apparaatinschrijving ('Bring Your Own Device') inschakelen voor iOS- en Mac OS X-apparaten om deze toegang te geven tot zakelijke e-mail en apps voor iPhone-, iPad- en Mac-gebruikers. Na inschrijving kunnen gebruikers de bedrijfsportal-app van Intune installeren en kan er op hun apparaten beleid worden toegepast vanuit de Intune-beheerconsole.

Voordat u iOS-apparaten met Intune kunt beheren, moeten de apparaten met Intune kunnen communiceren. Apple vereist dat er een vertrouwensrelatie met Intune wordt ingesteld door een APNs-certificaat (Apple Push Notification-service) te importeren.

1.  **Intune instellen**<br>
    Als u dit nog niet hebt gedaan, moet u het beheer van mobiele apparaten voorbereiden door de [beheerautoriteit voor mobiele apparaten in te stellen](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority) op **Microsoft Intune** en MDM in te stellen.

2.  **Certificaatondertekening aanvragen**<br>
    Als gebruiker met beheerdersrechten opent u de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) en gaat u naar **Beheer** &gt; **Mobile Device Management** &gt; **iOS en Mac OS X** &gt; **Een APNs-certificaat uploaden** en klikt u op **De APNs-certificaataanvraag downloaden**. Sla het bestand met de aanvraag voor certificaatondertekening (.csr) lokaal op. Het CSR-bestand wordt gebruikt voor het aanvragen van een vertrouwensrelatiecertificaat uit de Apple Push Certificates Portal.

    ![Het dialoogvenster Een APNs-certificaat uploaden](../media/Intune-iOS-enrollment-with-apns.png)

3.  **APNs-certificaat aanvragen**<br>
    Ga naar de [Apple Push Certificates-portal](http://go.microsoft.com/fwlink/?LinkId=269844) en meld u aan met de Apple-id van uw bedrijf om het APNs-certificaat te maken met behulp van het .csr-bestand. Nadat u in de Apple Push Certificates-portal op **Uploaden** hebt geklikt, ontvangt u een .json-bestand dat niet kan worden gebruikt voor APN’s. Laat het downloaden voltooien en keer terug naar de Apple Push Certificates-portal voor **Certificaten voor servers van derden**. Klik op **Downloaden**.

    Download het APNs-certificaat (.pem) en sla het bestand lokaal op. Deze Apple-id moet in de toekomst worden gebruikt om uw APNs-certificaat te vernieuwen.

4.  **Het APNs-certificaat toevoegen aan Intune**<br>
    Ga in de [Microsoft Intune-beheerconsole](http://manage.microsoft.com) naar **Beheer** &gt; **Mobile Device Management** &gt; **iOS en Mac OS X** &gt; **Een APNs-certificaat uploaden** en klik op **Het APNs-certificaat uploaden**. **Blader naar ** het certificaatbestand (.pem), klik op **Openen** en geef uw **Apple-id** op. Met het APNs-certificaat kan Intune iOS-apparaten inschrijven en beheren door beleid naar ingeschreven mobiele apparaten te pushen.

5.  **Vertel gebruikers hoe ze met de bedrijfsportal toegang krijgen tot bronnen**<br>
    Uw gebruikers moeten weten hoe ze hun apparaten kunnen inschrijven en wat ze kunnen verwachten als deze onder beheer zijn gebracht. [Wat u uw eindgebruikers vertelt over het gebruik van Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)

Als uw bedrijf of organisatie iOS-apparaten voor gebruikers koopt, kunnen die apparaten ook worden ingeschreven om te worden beheerd als [iOS-apparaten die bedrijfseigendom zijn](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

### Zie ook
[Bereid u voor op het registreren van apparaten in Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


