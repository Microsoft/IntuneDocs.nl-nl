---
title: Er ontbreekt een vereist certificaat voor uw apparaat | Microsoft Docs
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 01/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: df973b18-9166-417d-8aa3-49edd2bda256
searchScope:
- User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: c42e2ee0e4ebf7e2b2bdf7ec5eba8a73b953e867
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="your-android-device-is-missing-a-certificate-that-usually-comes-installed-on-your-phone"></a>Er ontbreekt een certificaat voor uw Android-apparaat dat normaal gesproken op uw telefoon is geïnstalleerd

Als uw apparaat niet bij Intune is geregistreerd en er ontbreekt een certificaat dat normaal gesproken op uw telefoon is geïnstalleerd, kunt u zich niet aanmelden bij de bedrijfsportal-app. Wanneer u zich probeert aan te melden, wordt het volgende bericht weergegeven:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

U kunt dit probleem oplossen door het vereiste certificaat uit te downloaden via de [certificaatpagina van Digicert](https://www.digicert.com/digicert-root-certificates.htm).

1. Zoek en download het certificaat __Baltimore CyberTrust Root__. U kunt het certificaat [hier](https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt) ook rechtstreeks downloaden.

2. Veeg vanaf de bovenkant van het scherm naar beneden om de lijst met recente meldingen te openen en tik op **BaltimoreCyberTrustRoot.crt**.

3. U wordt gevraagd **een naam voor het certificaat op te geven**. Wijzig niet de standaardnaam die voor het certificaat wordt weergegeven.

4. Zorg ervoor dat **Gebruik van referenties** is ingesteld op **Worden gebruikt voor VPN en apps** en tik op **OK**.

    ![screenshot-certificate-name-dialog-showing-baltimore-certificate-name](./media/andr-cert_install-2-add_cert_name.png)

5. Sluit uw browser en de bedrijfsportal-app.

6. Open de bedrijfsportal-app opnieuw. Nu moet u zich bij de bedrijfsportal-app kunnen aanmelden. Als u de bedrijfsportal-app nog steeds niet kunt gebruiken, gebruikt u de gegevens op de [bedrijfsportalwebsite](https://portal.manage.microsoft.com#HelpDeskDialog) om contact met het ondersteuningsteam van uw bedrijf op te nemen voor verdere instructies.

>[!NOTE]
> Als u het probleem niet kunt oplossen door dit certificaat te installeren en er een ander bericht wordt weergegeven dat er een certificaat ontbreekt, [installeert u het ontbrekende certificaat](your-device-is-missing-an-IT-required-certificate-android.md).

Nog hulp nodig? Neem contact op met het ondersteuningsteam van uw bedrijf. Controleer of de contactgegevens beschikbaar zijn op de [bedrijfsportalwebsite](https://portal.manage.microsoft.com#HelpDeskDialog).
