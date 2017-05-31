---
title: Profielen voor het inrichten van apps | Microsoft Docs
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: Intune biedt u de hulpmiddelen om proactief een nieuw inrichtingsprofiel toe te wijzen aan apparaten met apps die bijna zijn verlopen.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbc3ba4a-df48-4aeb-988b-69a177764e3a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 966c097280ebebac68749e71c20381ee816360da
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017

---

# <a name="use-ios-mobile-provisioning-profiles-to-prevent-your-apps-from-expiring"></a>Inrichtingsprofielen gebruiken voor mobiele iOS-apps om te voorkomen dat uw apps verlopen

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

## <a name="introduction"></a>Inleiding

Apple iOS mobiele Line-Of-Business-apps die zijn toegewezen aan iPhones en iPads, zijn gebouwd met een inrichtingsprofiel en code die is ondertekend met een certificaat. Wanneer de app wordt uitgevoerd, bevestigt iOS de integriteit van de iOS-app en worden beleidsregels afgedwongen die zijn gedefinieerd door het inrichtingsprofiel. De volgende validaties vinden plaats:

- **Integriteit van installatiebestand**: iOS vergelijkt de details van de app met de openbare sleutel van het handtekeningcertificaat van de onderneming. Als deze verschillen, is de inhoud van de app mogelijk gewijzigd en mag de app niet worden uitgevoerd.
- **Mogelijkheden afdwingen**: iOS probeert de app-mogelijkheden af te dwingen van het inrichtingsprofiel van de onderneming (geen afzonderlijke inrichtingsprofielen van ontwikkelaars) dat zich in het app-installatiebestand (.ipa) bevindt.


Het handtekeningcertificaat voor ondernemingen dat u gebruikt om apps te ondertekenen is doorgaans drie jaar geldig. Echter, het inrichtingsprofiel verloopt na één jaar. Zolang het certificaat nog geldig is, biedt Intune u de hulpmiddelen om proactief een nieuw inrichtingsprofiel toe te wijzen aan apparaten met apps die binnenkort verlopen.
Nadat het certificaat is verlopen, moet u de app opnieuw ondertekenen met een nieuw certificaat en een nieuw inrichtingsprofiel implementeren met de sleutel van het nieuwe certificaat.


## <a name="how-to-create-an-ios-mobile-app-provisioning-profile"></a>Een inrichtingsprofiel voor mobiele iOS-apps maken

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Overige** > **Intune**.
3. Kies **Mobiele apps** op de blade **Intune**.
1.  Kies **Beheren** > **iOS-inrichtingsprofielen** in de workload **Mobiele apps**.
2.  Kies **Profiel maken** op de blade met de profielenlijst.
3. Configureer de volgende waarden op de blade **Profiel maken**:
    - **Naam**: geef een naam op voor dit mobiele inrichtingsprofiel.
    - **Beschrijving**: geef indien gewenst een beschrijving op voor het beleid.
    - **Profielbestand uploaden**: klik op **Importeren** en kies een Apple-profielbestand voor mobiele configuratie (met de extensie **.mobileprovision**) dat u hebt gedownload van de Apple-website voor ontwikkelaars.
4. Als u klaar bent, kiest u **Maken**.

## <a name="next-steps"></a>Volgende stappen

Wijs het profiel toe aan de vereiste iOS-apparaten. Voor meer informatie gebruikt u de stappen in [Apparaatprofielen toewijzen](device-profile-assign.md).

