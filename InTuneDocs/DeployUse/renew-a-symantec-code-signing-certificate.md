---
# required metadata

title: Een Symantec-certificaat voor het ondertekenen van programmacode vernieuwen om met Microsoft Intune te gebruiken | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: c4813044-a925-4273-b0ec-e992fd55850a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Een Symantec-certificaat voor het ondertekenen van programmacode vernieuwen voor Windows-apparaten

Het Symantec-certificaat waarmee bepaalde Windows-apparaten en mobiele apparaten met Windows Phone worden beheerd, moet regelmatig worden vernieuwd. Voor Windows Phone 8.0-apparaten zijn een ondertekende bedrijfsportal-app en het certificaat voor ondertekenen van code nodig voor apparaatinschrijving. Latere Windows Phone-apparaten kunnen de bedrijfsportal-app gebruiken die is gedownload uit de Store. Een certificaat voor ondertekenen van code is ook vereist voor de implementatie van line-of-business-apps.

## Het zakelijke Symantec-certificaat voor ondertekening van programmacode vernieuwen

1.  Zoek naar een e-mail over de vereiste vernieuwing die ongeveer 14 dagen vóór de vervaldatum van het certificaat ontvangt van Symantec. Deze e-mail bevat richtlijnen van Symantec om uw zakelijke certificaat te vernieuwen.

    Ga naar [www.symantec.com](http://www.symantec.com) of bel +1-877-438-8776 of +1-650-426-3400 voor meer informatie over Symantec-certificaten.

2.  Ga naar de website (voorbeeld: [https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do)) en meld u aan met de Symantec uitgevers-ID en het e-mailadres dat is gekoppeld aan het certificaat. Start het vernieuwingsproces op het apparaat waarop u daarna ook het certificaat gaat downloaden.

3.  Nadat de vernieuwing is goedgekeurd en betaald, downloadt u het certificaat.

## Het bijgewerkte certificaat voor Windows Phone 8.0 installeren

1.  Download en onderteken de meest recente Windows Phone-bedrijfsportal. U vindt deze hier: [http://www.microsoft.com/en-us/download/details.aspx?id=36060](http://www.microsoft.com/en-us/download/details.aspx?id=36060).

2.  Open uw Intune-beheerconsole ([https://admin.manage.microsoft.com](https://admin.manage.microsoft.com)) en ga naar **Beheer**, **Mobile Device Management** &gt; **Windows Phone** en klik op **Ondertekende app uploaden**.

3.  Upload de zojuist ondertekende bedrijfsportal. U hebt het zojuist ondertekende SSP.xap-bestand en het nieuwe PFX-bestand nodig die u van Symantec hebt ontvangen of het inschrijvingstoken van de toepassing dat is gemaakt met dit nieuwe PFX-bestand.

4.  Wanneer het uploaden is voltooid, verwijdert u de oude versie van de bedrijfsportal in de werkruimte **Software** in de Intune-beheerconsole.

5.  Onderteken alle zakelijke Line-of-Business-apps opnieuw met hetzelfde certificaat en upload en vervang bestaande apps.

Voorzien in een ondertekend SSP.xap-bestand is momenteel de enige manier om het bijgewerkte certificaat voor ondertekening van programmacode te leveren. Om ondersteuning te bieden voor ondertekende line-of-business-apps, moet u een bedrijfsportal-app ondertekenen en uploaden, ook al installeren uw gebruikers de bedrijfsportal-app uit de Store.

## Het bijgewerkte certificaat voor apparaten met Windows Phone 8.1 en hoger installeren

1.  Download en onderteken de meest recente Windows Phone-bedrijfsportal. U vindt deze hier in het Downloadcentrum: [http://www.microsoft.com/en-us/download/details.aspx?id=36060](http://www.microsoft.com/en-us/download/details.aspx?id=36060).

2.  Open uw [Intune-beheerconsole](https://admin.manage.microsoft.com) (https://admin.manage.microsoft.com) en ga naar **Beheer** &gt; **Mobile Device Management** &gt; **Windows Phone** en klik op **Ondertekende app uploaden**.

3.  Upload de zojuist ondertekende bedrijfsportal. U hebt het nieuw ondertekende SSP.xap en het nieuwe PFX-bestand nodig dat u hebt ontvangen van Symantec of het toepassingsinschrijvingstoken dat met dit nieuwe PFX-bestand is gemaakt.

4.  Nadat het uploaden is voltooid, verwijdert u de oude versie van de bedrijfsportal uit de werkruimte **Software**  .

5.  Onderteken alle nieuwe en bijgewerkte bedrijfstak-apps van de onderneming met behulp van het nieuwe certificaat. Bestaande toepassingen hoeven niet opnieuw te worden ondertekend en geïmplementeerd.


### Zie tevens
[Windows Phone 8.0-beheer instellen](set-up-windows-phone-8.0-management-with-microsoft-intune.md)
[Windows Phone-beheer instellen](set-up-windows-phone-management-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->


