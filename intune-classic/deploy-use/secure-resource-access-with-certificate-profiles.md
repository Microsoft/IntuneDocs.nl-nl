---
title: Certificaatprofielen voor toegang tot bedrijfsresources | Microsoft Docs
description: "Beveiligde VPN-, Wi-Fi en toegang tot e-mail met een certificaat op elk gebruikersapparaat geïnstalleerd."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8cbb8499-611d-4217-a7b4-e9b864785dd0
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 3dd6e5971d084773640c577cace43c2f011dbb69
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="secure-resource-access-with-certificate-profiles-in-microsoft-intune"></a>Toegang tot beveiligde bronnen met certificaatprofielen in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Wanneer u gebruikers toegang verleent tot bedrijfsresources via een VPN-, Wi-Fi- of e-mailprofiel, kunt u deze toegang beveiligen met een certificaat dat op elk gebruikersapparaat wordt geïnstalleerd. Dit werkt als volgt:

1. Zorg ervoor dat de juiste certificaatinfrastructuur aanwezig is, zoals beschreven in [Certificaatinfrastructuur voor SCEP configureren](configure-certificate-infrastructure-for-scep.md) en [Certificaatinfrastructuur voor PFX configureren](configure-certificate-infrastructure-for-pfx.md).

2. Installeer op elk apparaat een basiscertificaat (of het tussenliggende CA-certificaat), zodat het apparaat de geldigheid van uw certificeringsinstantie (CA) erkent. Hiervoor maakt en implementeert u een **vertrouwd certificaatprofiel**. Wanneer u dit profiel implementeert, zullen de apparaten die u met Intune beheert, het basiscertificaat aanvragen en ontvangen. U moet voor elk platform een afzonderlijk profiel maken. Het **Vertrouwd certificaatprofiel** is voor deze platforms beschikbaar:
 -  iOS 8.0 en hoger
 -  Mac OS X 10.9 en hoger
 -  Android 4.0 en hoger
 -  Android for Work
 -  Windows 8.1 en hoger
 -  Windows Phone 8.1 en hoger

3. Maak certificaatprofielen zodat apparaten een certificaat aanvragen ten behoeve van verificatie van toegang per e-mail, VPN en Wi-Fi, zoals beschreven in [Intune-certificaatprofielen configureren](configure-intune-certificate-profiles.md). U kunt een **PKCS #12-certificaatprofiel (.pfx)** *of* een **SCEP-certificaatprofiel** maken en implementeren voor apparaten met deze platformen:

  -  iOS 8.0 en hoger
  -  Android 4.0 en hoger
  -  Android for Work
  -  Windows 10 (Desktop en Mobile) en hoger

  Een **SCEP-certificaatprofiel** gebruiken voor apparaten met deze platformen:
    -   Mac OS X 10.9 en hoger
    -   Windows Phone 8,1

U moet voor elk platform een afzonderlijk profiel maken. Wanneer u het profiel maakt, koppelt u dit aan het **vertrouwde basiscertificaatprofiel** dat u al hebt gemaakt.

> [!NOTE]           
> - Als u geen bedrijfscertificeringsinstantie hebt, moet u er een maken.
>- Als u op basis van uw apparaatplatformen besluit het SCEP-profiel (Simplified Certificate Enrollment Protocol) te gebruiken, moet u ook een NDES-server (Network Device Enrollment Service) configureren.
>-  Bovendien moet u de Microsoft Intune-certificaatconnector downloaden en configureren, ongeacht of u SCEP-profielen of PFX-profielen wilt gebruiken.
>-  In [De certificaatinfrastructuur voor SCEP configureren](configure-certificate-infrastructure-for-scep.md) en [De certificaatinfrastructuur voor PFX configureren](configure-certificate-infrastructure-for-pfx.md) leest u meer over het configureren van de vereiste services.

### <a name="next-steps"></a>Volgende stappen
- [De certificaatinfrastructuur voor SCEP configureren](configure-certificate-infrastructure-for-scep.md)
- [De certificaatinfrastructuur voor PFX configureren](configure-certificate-infrastructure-for-pfx.md)
- [Intune-certificaatprofielen configureren](configure-intune-certificate-profiles.md)

