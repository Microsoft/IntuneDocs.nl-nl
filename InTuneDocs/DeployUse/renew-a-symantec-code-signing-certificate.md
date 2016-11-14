---
title: Een Symantec-certificaat voor het ondertekenen van programmacode vernieuwen om met Intune te gebruiken | Microsoft Intune
description: Richtlijnen voor het vernieuwen van Symantec-certificaten waarmee bepaalde mobiele Windows- en Windows Phone-apparaten worden beheerd
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c4813044-a925-4273-b0ec-e992fd55850a
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8fd2a90025ae9310a214978cd2d42ea7ad035fa3
ms.openlocfilehash: 2479f8065a2bb46e63b0e3971700a8d2c0982755


---

# Een Symantec-certificaat voor het ondertekenen van programmacode vernieuwen voor Windows-apparaten

Het Symantec-certificaat waarmee mobiele apps voor Windows en Windows Phone worden geïmplementeerd, moet regelmatig worden vernieuwd.

## Het zakelijke Symantec-certificaat voor ondertekening van programmacode vernieuwen

1.  Zoek naar een e-mail over de vereiste vernieuwing die ongeveer 14 dagen vóór de vervaldatum van het certificaat ontvangt van Symantec. Deze e-mail bevat richtlijnen van Symantec om uw zakelijke certificaat te vernieuwen.

    Ga naar [www.symantec.com](http://www.symantec.com) of bel +1-877-438-8776 of +1-650-426-3400 voor meer informatie over Symantec-certificaten.

2.  Ga naar de website (voorbeeld: [https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do)) en meld u aan met de Symantec uitgevers-ID en het e-mailadres dat is gekoppeld aan het certificaat. Start het vernieuwingsproces op het apparaat waarop u daarna ook het certificaat gaat downloaden.

3.  Nadat de vernieuwing is goedgekeurd en betaald, downloadt u het certificaat.

## Het bijgewerkte certificaat voor Windows Phone 8.0 installeren

1.  Download en onderteken de meest recente Windows Phone-bedrijfsportal die u hier kunt vinden: [http://www.microsoft.com/en-us/download/details.aspx?id=36060](http://www.microsoft.com/en-us/download/details.aspx?id=36060).

2.  Open uw Intune-beheerconsole ([https://admin.manage.microsoft.com](https://admin.manage.microsoft.com)) en ga naar **Beheer**, **Mobile Device Management** &gt; **Windows Phone** en klik op **Ondertekende app uploaden**.

3.  Upload de zojuist ondertekende bedrijfsportal. U hebt het zojuist ondertekende SSP.xap-bestand en het nieuwe PFX-bestand nodig die u van Symantec hebt ontvangen of het inschrijvingstoken van de toepassing dat is gemaakt met dit nieuwe PFX-bestand.

4.  Wanneer het uploaden is voltooid, verwijdert u de oude versie van de bedrijfsportal in de werkruimte **Software** in de Intune-beheerconsole.

5.  Onderteken alle zakelijke Line-of-Business-apps opnieuw met hetzelfde certificaat en upload en vervang bestaande apps.

Voorzien in een ondertekend SSP.xap-bestand is momenteel de enige manier om het bijgewerkte certificaat voor ondertekening van programmacode te leveren. Om ondersteuning te bieden voor ondertekende line-of-business-apps, moet u een bedrijfsportal-app ondertekenen en uploaden, ook al installeren uw gebruikers de bedrijfsportal-app uit de Store.

## Het bijgewerkte certificaat voor apparaten met Windows Phone 8.1 en hoger installeren

1.  Download en onderteken de meest recente Windows Phone-bedrijfsportal uit het Downloadcentrum dat u hier kunt vinden: [http://www.microsoft.com/en-us/download/details.aspx?id=36060](http://www.microsoft.com/en-us/download/details.aspx?id=36060).

2.  Open uw [Intune-beheerconsole](https://admin.manage.microsoft.com) (https://admin.manage.microsoft.com) en ga naar **Beheer** &gt; **Mobile Device Management** &gt; **Windows Phone** en klik op **Ondertekende app uploaden**.

3.  Upload de zojuist ondertekende bedrijfsportal. U hebt het nieuw ondertekende SSP.xap en het nieuwe PFX-bestand nodig dat u hebt ontvangen van Symantec of het toepassingsinschrijvingstoken dat met dit nieuwe PFX-bestand is gemaakt.

4.  Nadat het uploaden is voltooid, verwijdert u de oude versie van de bedrijfsportal uit de werkruimte **Software**  .

5.  Onderteken alle nieuwe en bijgewerkte bedrijfstak-apps van de onderneming met behulp van het nieuwe certificaat. Bestaande toepassingen hoeven niet opnieuw te worden ondertekend en geïmplementeerd.


### Zie tevens
[Windows Phone 8.0-beheer instellen](set-up-windows-phone-8.0-management-with-microsoft-intune.md)
[Windows Phone-beheer instellen](set-up-windows-phone-management-with-microsoft-intune.md)



<!--HONumber=Oct16_HO4-->


