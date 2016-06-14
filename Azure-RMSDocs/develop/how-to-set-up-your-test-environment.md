---
# required metadata

title: De testomgeving instellen | Azure RMS
description: Uw toepassing met rechten kan worden getest met verschillende serveropties.
keywords:
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: E480D8D6-F070-43D1-B2B0-6921459C3437
# optional metadata

#ROBOTS:
audience: developer
#ms.devlang:
ms.reviewer: shubhamp
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---
** Deze SDK-inhoud is niet actueel. U kunt tijdelijk de [huidige versie](https://msdn.microsoft.com/library/windows/desktop/hh535290(v=vs.85).aspx) van de documentatie op MSDN vinden. **
# De testomgeving instellen

Uw toepassing met rechten kan worden getest met verschillende serveropties.

**Belangrijk** Het wordt aanbevolen dat u uw Rights Management Services SDK 2.1-toepassing test in de AD RMS-preproductieomgeving met een AD RMS Server. Als u wilt dat uw klant de mogelijkheid heeft om uw toepassing te gebruiken met de Azure RMS-service, moet u tests met die omgeving uitvoeren. Zie [Ervoor zorgen dat uw servicetoepassing werkt met RMS in de cloud](how-to-use-file-api-with-aadrm-cloud.md) (Engelstalig) voor meer informatie.

 

### Vereisten

-   [De SDK installeren](create-your-first-rights-aware-application.md)

Instructies

### Stap 1: stel de testomgeving in

Als u uw toepassing met rechten wilt testen, moet u deze uitvoeren op een RMS-server die is geconfigureerd voor preproductie. De RMS-server van een preproductieomgeving maakt gebruik van het certificaat van de preproductiehiërarchie/ISV-hiërarchie voor het versleutelen en ontsleutelen van bestanden.

Zie [Certificaatketens begrijpen](understanding-certificate-chains.md) voor meer informatie over de AD RMS-certificaathiërarchie.

Voor het testen van uw toepassing op een RMS-server zijn twee opties beschikbaar:

-   **U kunt uw toepassing uitvoeren in de AD RMS ISV 1-box-omgeving**. Als u Windows Server 2012, Windows Server 2008 R2 of Windows Server 2008 gebruikt en Hyper-V is geïnstalleerd, kunt u de AD RMS ISV 1-box-omgeving implementeren door een virtuele machine te bouwen via de AD RMS 1-box VHD. De AD RMS ISV 1-box-omgeving biedt een RMS-server die is geconfigureerd voor preproductie en waarop ook Active Directory Rights Management Services Client 2.1 is geïnstalleerd. De registerinstellingen voor de RMS-server en -client zijn al geconfigureerd. Als u uw toepassing wilt testen, voert u deze uit op de virtuele machine waarop de 1-box-omgeving is geïmplementeerd.
-   **U kunt uw toepassing uitvoeren op een RMS-server die is geconfigureerd voor prepreoductie en is geïmplementeerd in uw netwerk**. In dit geval moet u ook AD RMS-Client 2.1 installeren en configureren op de computer waarop de toepassing zal worden uitgevoerd. Zie [Client configureren](how-to-configure-the-ad-rms-client-2-0.md) voor meer informatie. Zie [De server installeren en configureren](how-to-install-and-configure-an-rms-server.md) voor meer informatie over het implementeren van een RMS-server en het configureren hiervan voor preproductie.

## Verwante onderwerpen

* [Gebruik](how-to-use-msipc.md)
* [Downloadpagina voor ondersteunend materiaal van AD RMS SDK-webinar.](https://connect.microsoft.com/site1170/Downloads/DownloadDetails.aspx?DownloadID=42440)
* [Client configureren](how-to-configure-the-ad-rms-client-2-0.md)
* [De SDK installeren](create-your-first-rights-aware-application.md)
* [De server installeren en configureren](how-to-install-and-configure-an-rms-server.md)
* [Certificaatketens begrijpen](understanding-certificate-chains.md)
 

 





<!--HONumber=Jun16_HO1-->


