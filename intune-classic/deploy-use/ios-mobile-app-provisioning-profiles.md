---
title: Inrichtingsprofielen voor apps
description: Intune biedt u de hulpmiddelen om proactief een nieuw beleid voor inrichtingsprofielen te implementeren op apparaten met apps die bijna zijn verlopen.
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 12/27/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 86fbe736-7bdb-4f5e-ae21-13c91eb2462c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 8d55531dab4b6904fc9552f2be3ac7444073d0d7
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="use-ios-mobile-provisioning-profile-policies-to-prevent-your-apps-from-expiring"></a>Gebruik beleidsregels voor profielinrichting voor mobiele iOS-apps om te voorkomen dat uw apps verlopen

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Apple iOS mobiele Line-Of-Business-apps die zijn geïmplementeerd op iPhones en iPads zijn gebouwd met een inrichtingsprofiel en code die is ondertekend met een certificaat. Wanneer de app wordt uitgevoerd, bevestigt iOS de integriteit van de iOS-app en worden beleidsregels afgedwongen die zijn gedefinieerd door het inrichtingsprofiel. De volgende validaties vinden plaats:

- **Integriteit van installatiebestand**: iOS vergelijkt de details van de app met de openbare sleutel van het handtekeningcertificaat van de onderneming. Als deze verschillen, is de inhoud van de app mogelijk gewijzigd en mag de app niet worden uitgevoerd.
- **Mogelijkheden afdwingen**: iOS probeert de app-mogelijkheden af te dwingen van het inrichtingsprofiel van de onderneming (geen afzonderlijke inrichtingsprofielen van ontwikkelaars) dat zich in het app-installatiebestand (.ipa) bevindt.


Het handtekeningcertificaat voor ondernemingen dat u gebruikt om apps te ondertekenen is doorgaans drie jaar geldig. Echter, het inrichtingsprofiel verloopt na één jaar. Zolang het certificaat nog geldig is, biedt Intune u de hulpmiddelen om proactief een nieuw beleid voor inrichtingsprofielen te implementeren op apparaten met apps die bijna zijn verlopen.
Nadat het certificaat is verlopen, moet u de app opnieuw ondertekenen met een nieuw certificaat en een nieuw inrichtingsprofiel implementeren met de sleutel van het nieuwe certificaat.



## <a name="how-to-find-out-when-a-line-of-business-app-will-expire"></a>Nagaan wanneer een Line-Of-Business-app verloopt

1. Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) de optie **Apps** > **Apps**.
2. Raadpleeg in de lijst met apps de kolom **Vervaldatum** voor de vervaldatum van de app. U kunt ook de vervolgkeuzelijst **Filters** instellen op **Verlopen/bijna verlopen** om alleen apps weer te geven waarvoor u actie moet ondernemen.

## <a name="how-to-create-an-ios-mobile-provisioning-profile-policy"></a>Een iOS-beleid voor mobiele inrichtingsprofielen maken


1. Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) **Beleid** > **Overzicht** > **Beleid toevoegen**.
2. Kies in het dialoogvenster **Een nieuw beleid maken** **iOS** > **Beleid mobiel inrichtingsprofiel** , en kies vervolgens **Beleid maken**.
3. Configureer de volgende waarden op de pagina **Algemeen**:
    - **Naam**: geef een naam op voor dit beleid voor mobiele inrichtingsprofielen.
    - **Beschrijving**: geef indien gewenst een beschrijving op voor het beleid.
    - **Configuratieprofielbestand**: klik op **Importeren** en kies een Apple-profielbestand voor mobiele configuratie (met de extensie **.mobileprovision**) dat u hebt gedownload van de Apple-website voor ontwikkelaars.
4. Als u klaar bent, kiest u **Beleid opslaan**.
5. Implementeer het beleid nu voor de betreffende iOS-apparaten. Zie [Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) voor meer informatie.
