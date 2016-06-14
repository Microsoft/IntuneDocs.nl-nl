---
# required metadata

title: Toegang tot bedrijfsbronnen met certificaatprofielen in Microsoft Intune | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8cbb8499-611d-4217-a7b4-e9b864785dd0

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Toegang tot beveiligde bronnen met certificaatprofielen in Microsoft Intune
Wanneer u toegang tot bedrijfsbronnen via een VPN-, Wi-Fi- of e-mailprofiel mogelijk wilt maken, kunt u deze toegang beveiligen met een certificaat dat op elk gebruikersapparaat wordt geïnstalleerd. Dit werkt als volgt:

1. Zorg ervoor dat de juiste certificaatinfrastructuur aanwezig is, zoals beschreven in [Certificaatinfrastructuur configureren](configure-certificate-infrastructure.md).

2. Installeer op elk apparaat een basiscertificaat (of het tussenliggende CA-certificaat), zodat het apparaat de geldigheid van uw certificeringsinstantie (CA) erkent. U kunt hiervoor een **Vertrouwd certificaatprofiel** maken en implementeren. Wanneer u dit profiel implementeert, zullen de apparaten die u met Intune beheert, het basiscertificaat aanvragen en ontvangen. U moet voor elk platform een afzonderlijk profiel maken. Het **Vertrouwd certificaatprofiel** is voor deze platforms beschikbaar:
 -  iOS 7.1 en hoger
 -  Mac OS X 10.9 en hoger
 -  Android 4.0 en hoger
 -  Windows 8.1 en hoger
 -  Windows Phone 8.1 en hoger

3. Zorg ervoor dat elk apparaat een certificaat aanvraagt ten behoeve van verificatie van toegang per e-mail, VPN en Wi-Fi, zoals beschreven in [Intune-certificaatprofielen configureren](configure-intune-certificate-profiles.md). U kunt een **PKCS #12-certificaatprofiel (.pfx)** of een **SCEP-certificaatprofiel** maken en implementeren voor apparaten op deze platforms:
 
-  Android 4.0 en hoger
-  iOS 7.1 en hoger
-  Windows 10 (Desktop en Mobile) en hoger 

Gebruik het **SCEP-certificaatprofiel** voor:
-   Mac OS X 10.9 en hoger
-   Windows Phone 8.1 en hoger

U moet voor elk platform een afzonderlijk profiel maken. Wanneer u het profiel maakt, koppelt u dit aan het **vertrouwde basiscertificaatprofiel** dat u al hebt gemaakt.

> [!NOTE]           
> -    Als u geen bedrijfscertificeringsinstantie hebt, moet u er een maken. 
>- Als u op basis van uw apparaatplatforms besluit het SCEP-profiel (Simplified Certificate Enrollment Protocol) te gebruiken, moet u ook een NDES-server (Network Device Enrollment Service) configureren.
>-  Bovendien moet u de Microsoft Intune-certificaatconnector downloaden en configureren, ongeacht of u SCEP-profielen of PFX-profielen wilt gebruiken.
> Configuratie van al deze waarden wordt beschreven in het onderwerp [Certificaatinfrastructuur configureren](configure-certificate-infrastructure.md).

### Volgende stappen
- [Certificaatinfrastructuur configureren](configure-certificate-infrastructure.md)
- [Intune-certificaatprofielen configureren](configure-intune-certificate-profiles.md)



<!--HONumber=May16_HO1-->


