---
title: Uw macOS-apparaat registreren bij Intune met bedrijfsportal | Microsoft Docs
description: Informatie over hoe u een macOS-apparaat bij Intune kunt registreren met de bedrijfsportal-app
keywords: Mac OS X, Mac OS, OS X
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3bb659cc-9b57-4d19-8631-2c26749fa71c
searchScope: User help
ROBOTS: 
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 1559692de1a8c9c356a3f5b30e80d1abd31853d2
ms.sourcegitcommit: f2f147a1177d1cf5bbc8001701eb8f44dd833b7d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/12/2017
---
# <a name="enroll-your-macos-device-in-intune-with-the-company-portal-app"></a>Uw macOS-apparaten registreren bij Intune met de bedrijfsportal-app

Als u toegang hebt tot de apps, gegevens en bronnen van uw organisatie kunt u gemakkelijker uw werk uitvoeren. Uw organisatie gebruikt Intune voor het [beheren van toegang tot deze bronnen](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-macos.md), waarvoor u de bedrijfsportal-app voor macOS moet downloaden. Deze instructies werken voor macOS-apparaten op OS X El Capitan 10.11 +.

> [!NOTE]
> U vindt [hier](enroll-your-device-in-intune-macos-legacy.md) instructies voor de registratie van macOS-apparaten in eerdere versies van macOS.

1. Ga in de __Dock__ naar __Safari__ en open een nieuw venster. Open vervolgens de [bedrijfsportalwebsite](https://portal.manage.microsoft.com#HelpDeskDialog).

2. Meld u aan bij de bedrijfsportalwebsite met uw werk- of schoolaccount.

[!INCLUDE[wit_nextref](includes/end-user-password-guidance.md)]

3. Nadat u zich hebt aangemeld, klik u op het **Menu** in de linkerbovenhoek van de pagina en selecteert u **Mijn apparaten**.

   ![Een schermafbeelding van de startpagina voor de web-portal waarin wordt aangegeven dat er nog geen apps kunnen worden geïnstalleerd, met een knop Mijn apparaten eronder.](./media/macOS_enroll_001_landing_page.png)

4. Op de pagina __Mijn apparaten__ ziet u ofwel een lijst van geregistreerde apparaten of gewoon een koptekst. Dit is afhankelijk van of u al een apparaat hebt ingeschreven, macOS of anderszins. Om een apparaat in te schrijven dat niet wordt weergegeven, selecteert u de koptekst __Klik hier als uw apparaat in de lijst voorkomt om het te identificeren. U kunt ook hier tikken om uw apparaat in te schrijven als dit niet wordt weergegeven__. Als u geen geregistreerde apparaten hebt, toont de banner **U hebt geen apparaten geregistreerd. U kunt dit apparaat registreren door hier te tikken.**

    ![Een schermafbeelding van de pagina Mijn apparaat met een paar onbekende apparaten boven de koptekst die vraagt naar het inschrijven van niet-vermelde apparaten of het identificeren van ongeïdentificeerde apparaten.](./media/macOS_enroll_002_tap_here_banner.png)

5. Download de bedrijfsportal-app naar uw macOS-apparaat om door te gaan met de registratie.

    ![De melding waarin een gebruiker wordt gevraagd om de bedrijfsportal-app voor macOS te downloaden. Deze melding is de tekst vermeld in de bovenstaande stap waarin 'Downloaden' in de rechterbenedenhoek wordt weergegeven.](./media/macOS_enroll_IWP_CP_app_notice.png)

6. Uw Mac controleert of het downloadbestand van **CompanyPortal.pkg** veilig kan worden geopend. Open het installatieprogramma en volg het installatieproces.

7. Als het installatieprogramma is voltooid, opent u de map **Programma's** of **Launchpad** en opent u vervolgens **Bedrijfsportal**.

8. U krijgt een bericht waarin wordt gemeld dat **'CompanyPortal' een toepassing is die is gedownload van internet. Weet u zeker dat u deze wilt openen?** Klik op **Openen**.

  > [!NOTE]
  > Intune heeft toegang nodig tot uw computer om te controleren of dit apparaat voldoende is beveiligd om toegang te verkrijgen tot de bronnen van uw organisatie. Als u de bedrijfsportal-app niet kunt openen, probeert u [Gatekeeper uit te schakelen](https://support.apple.com/HT202491) en vervolgens de app te openen.

9. In het eerste scherm van de bedrijfsportal-app wordt u gevraagd om u **aan te melden** met hetzelfde werk- of schoolaccount waarmee u zich bij de bedrijfsportal-website hebt aangemeld.

10. De bedrijfsportal bevestigt uw accountgegevens en geeft de status van de **apparaatregistratie** en **apparaatcompatibiliteit** weer. Gele driehoeken geven aan dat er acties zijn die u moet uitvoeren om ervoor te zorgen dat uw Mac veilig is voor gebruik op het werk. Klik op **Begin** om de [registratie van uw apparaat in het beheer](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md) te starten.

11. Uw Mac begint met de registratie in het beheer. Mogelijk wordt u ondertussen gevraagd naar de aanmeldingsgegevens voor uw computer. De registratie kan enkele minuten duren. Gedurende deze tijd kunt u andere dingen doen op uw computer. Er verschijnt een bericht zodra het instellen van de bedrijfstoegang is voltooid, zodat u weet dat u klaar bent.

Nog hulp nodig? Neem contact op met het ondersteuningsteam van uw bedrijf. U vindt de contactgegevens van uw beheerder op de [bedrijfsportalwebsite](https://portal.manage.microsoft.com#HelpDeskDialog).
