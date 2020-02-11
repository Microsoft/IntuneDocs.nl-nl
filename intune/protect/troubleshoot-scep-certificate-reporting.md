---
title: Problemen oplossen met de rapportage van geslaagde certificaatimplementatie op apparaten wanneer u SCEP gebruikt met Microsoft Intune | Microsoft Docs
description: Problemen oplossen met de rapportage door NDES en de connector aan Intune over een geslaagde implementatie van certificaten die zijn ingericht met SCEP-certificaatprofielen.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/30/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2ccc738626efc140efca46d1b997164ed36dd37f
ms.sourcegitcommit: c46b0c2d4507be6a2786a4ea06009b2d5aafef85
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/01/2020
ms.locfileid: "76916016"
---
# <a name="troubleshoot-ndes-reporting-of-certificate-deployments-in-microsoft-intune"></a>Problemen oplossen met de rapportage door NDES over certificaatimplementaties in Microsoft Intune

Gebruik de volgende informatie om te controleren of NDES en de Microsoft Intune Certificate Connector met succes aan Intune rapporteren dat het certificaat aan een apparaat is geleverd. Rapportage aan Intune is de laatste fase van het gebruik van SCEP-certificaatprofielen om Windows-apparaten in te richten met een certificaat.

Dit artikel is van toepassing op stap 6 van de [SCEP-communicatiewerkstroom](troubleshoot-scep-certificate-profiles.md).

## <a name="review-for-signs-of-successful-reporting"></a>Controleren op tekenen van een geslaagde rapportage

Als de rapportage is geslaagd, vindt u vermeldingen die vergelijkbaar zijn met de volgende voorbeelden op de NDES-server:

- **IIS-logboek**:

  `fe80::f53d:89b8:c3e8:5fec%13 POST /CertificateRegistrationSvc/Certificate/Notify - 443 - fe80::f53d:89b8:c3e8:5fec%13 NDES_Plugin - 204 0 0 277 62`

- **NDESPlugin.log**:

  ```
  Calling Notifyrequest ...
  Sending request to certificate registration point.
  Exiting Notify with 0x0
  ```

- **CertificateRegistrationPoint.svclog**:

  ![Intune Certificate Connector-logboek](../protect/media/troubleshoot-scep-certificate-reporting/certificate-registration-point-log.png)

- **NDESConnector.svclog**:

  ![Intune Certificate Connector-logboek](../protect/media/troubleshoot-scep-certificate-reporting/ndesconnector-log.png)

- **CertificateRequestStatus**:

  Ga naar de map *%ProgramFiles%\Microsoft Intune\CertificateRequestStatus*, waar u de mappen **Mislukt**, **Verwerken**en **Geslaagd** ziet met bestanden met de statuswaarden van certificaataanvragen.

  Als de certificaataanvraag met succes is verwerkt, ziet u nieuwe bestanden in de map **Geslaagd**. U kunt *Notepad.exe* gebruiken om de bestanden te openen en de gegevens weer te geven die door de Intune Certificate Connector zijn geüpload naar de Intune-service. Gegevens die zijn geüpload, bevatten details zoals **CertificateSerialNumber**, **UserID**, **DeviceID** en **Thumbprint**.

### <a name="troubleshoot-stuck-files"></a>Problemen met vastgelopen bestanden oplossen

Als er geen nieuwe bestanden worden gemaakt in de map *Geslaagd*, controleert u of er bestanden in de map *Verwerken* staan.

Controleer of de Intune Connector-service is gestart op de NDES-server en of er geen fouten zijn in Ndesconnector.svclog.

## <a name="next-steps"></a>Volgende stappen

[Ondersteuning voor Microsoft Intune krijgen](../fundamentals/get-support.md)
