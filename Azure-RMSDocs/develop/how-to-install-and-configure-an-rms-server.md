---
# required metadata

title: De server installeren en configureren| Azure RMS
description: RMS-server installeren en configureren voor het testen van uw toepassing met rechten.
keywords:
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 32C7F387-CF7E-4CE0-AFC9-4C63FE1E134A
# optional metadata

#ROBOTS:
audience: developer
#ms.devlang:
ms.reviewer: shubhamp
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# De server installeren en configureren

Dit onderwerp bevat de stappen voor het installeren en configureren van de RMS-server voor het testen van uw toepassing met rechten.

**Belangrijk** Als u uw toepassing test door deze uit te voeren in de 1 RMS ISV 1-box-omgeving, hoeft u geen RMS-server te installeren omdat er al een is geïnstalleerd en geconfigureerd in de 1-box-omgeving.
Zie [De testomgeving instellen](how-to-set-up-your-test-environment.md) voor meer informatie over de AD RMS ISV 1-box-omgeving.

 

## Instructies

### Stap 1: stel uw RMS-server in

Met de volgende stappen stelt u uw RMS-server in:

-   Het register configureren
-   De server installeren
-   De server registreren

1.  **Het register configureren**

    Stel de volgende registerwaarden in om op te geven dat u het certificaat van de preproductiehiërarchie gebruikt.

    **Opmerking** Als u Windows Server 2008 R2 of Windows Server 2008 gebruikt, stelt u de registerwaarden in voordat u de AD RMS-service installeert.

    Als u AD RMS gebruikt op Windows Server 2008 R2, moet u de volgende waarde instellen voor **REG\_DWORD**. Wijzig deze waarde in 0 (nul) om over te schakelen naar de productiehiërarchie.

    **Computer**\\**HKEY\_LOCAL\_MACHINE**\\**Software**\\**Microsoft**\\**DRMS**\\**Hierarchy** = 0x00000001

    Als u AD RMS gebruikt op Windows Server 2008 R2 en er in Active Directory al een andere AD RMS-service is geïmplementeerd als preproductieservice, moet u de volgende lege tekenreekswaarde toevoegen aan het register.

    **Computer**\\**HKEY\_LOCAL\_MACHINE**\\**Software**\\**Microsoft**\\**DRMS**\\**GICURL** = ""

    Als u AD RMS op Windows Server 2008 gebruikt, moet u de volgende waarde instellen voor **REG\_DWORD**. Wijzig deze waarde in 0 (nul) om over te schakelen naar de productiehiërarchie.

    **Computer**\\**HKEY\_LOCAL\_MACHINE**\\**Software**\\**Microsoft**\\**DRMS**\\**2.0**\\**Hierarchy** = 0x00000001

    Als u AD RMS gebruikt op Windows Server 2008 en er in Active Directory al een andere AD RMS-service is geïmplementeerd als preproductieservice, moet u de volgende lege tekenreekswaarde toevoegen aan het register.

    **Computer**\\**HKEY\_LOCAL\_MACHINE**\\**Software**\\**Microsoft**\\**DRMS**\\**2.0**\\**GICURL** = ""

2.  **De server installeren**

    Active Directory Rights Management Services (AD RMS) bestaat uit afzonderlijke client- en serveronderdelen. Het serveronderdeel wordt geïmplementeerd als een set webservices die kan worden gebruikt om een RMS-infrastructuur te beheren, licenties te verlenen aan consumenten en uitgevers van inhoud, en certificaten uit te geven aan computers en gebruikers.

    Vanaf Windows Server 2008 maken de client- en serveronderdelen deel uit van het besturingssysteem. U kunt de serveronderdelen voor eerdere besturingssystemen downloaden van de volgende locatie.

    -   [RMS Server v1.0 SP2](http://go.microsoft.com/fwlink/p/?linkid=73722)

    Als u het serveronderdeel wilt configureren op Windows Server 2008, moet u de AD RMS-rol installeren. Voordat u dit doet, moet u echter het register configureren om op te geven dat u het certificaat van de preproductiehiërarchie gebruikt in plaats van de productiehiërarchie. Als u echter toepassingen ontwikkelt voor een eerder serverbesturingssysteem, configureert u het register nadat u RMS Server v1.0 SP2 hebt geïnstalleerd, maar voordat u de RMS-service inricht.

    Zie de vorige stap (stap 1, Het register configureren) voor meer informatie.

3.  **De server registreren**

    U moet een Rights Management Services (RMS)-server registreren om deze te identificeren in de preproductiehiërarchie of productiehiërarchie. Na het inschrijvingsproces staat er een serverlicentiecertificaat op de servercomputer. Dit certificaat is gekoppeld aan een Microsoft-vertrouwensbasis. De wijze van registratie van de server is afhankelijk van welke versie van RMS u gebruikt.

    -   **Zelfregistratie**

        Vanaf Windows Server 2008 kunt u een RMS-server in de juiste hiërarchie registreren zonder dat er gegevens naar Microsoft worden verzonden. Wanneer u de RMS-rol installeert, worden er ook een certificaat voor zelfregistratie en een persoonlijke sleutel geïnstalleerd. Deze worden gebruikt om automatisch het serverlicentiecertificaat te maken. Er wordt geen informatie uitgewisseld met Microsoft.

    -   **Online registratie**Als u AD RMS v1.0 SP2 gebruikt, kunt u de server online registreren. Registratie vindt plaats achter de schermen tijdens het inrichtingsproces, maar u moet een internetverbinding hebben en de juiste registerwaarde opgeven om aan te geven in welke hiërarchie u de server registreert. Als u de server wilt registreren in de preproductiehiërarchie, voegt u de volgende waarde voor **REG\_SZ** toe en richt u de server in. Als u de server wilt registreren in de productiehiërarchie, wist u deze waarde en richt u de server in.

        Zie de vorige stap (stap 1, Het register configureren) voor meer informatie.

        **HKEY\_LOCAL\_MACHINE**\\**Software**\\**Microsoft**\\**DRMS**\\**1.0**\\**UddiProvider** = 0e3d9bb8-b765-4a68-a329-51548685fed3

## Verwante onderwerpen

* [Gebruik](how-to-use-msipc.md)
 

 





<!--HONumber=Apr16_HO4-->


