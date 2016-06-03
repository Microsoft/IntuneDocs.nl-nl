---
# required metadata

title: De client configureren | Azure RMS
description: Instructies voor het configureren van de Active Directory Rights Management Services-client 2.1.
keywords:
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 74C342BF-0F79-486D-AED7-C53230DE5FA7
# optional metadata

#ROBOTS:
audience: developer
#ms.devlang:
ms.reviewer: shubhamp
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# De client configureren

Dit onderwerp bevat instructies voor het configureren van de Active Directory Rights Management Services-client 2.1.

**Belangrijk:** als u uw toepassing gaat testen door deze uit te voeren in een RMS ISV-omgeving met 1 vak, hoeft u de AD RMS Client 2.1 niet te configureren. Zie voor meer informatie [Een toepassing met rechten testen](running-your-first-application.md).

 

### Vereisten

-   De AD RMS Client 2.1 moet op de computer zijn geïnstalleerd waarop u uw toepassing gaat testen.

    -   Als u de toepassing gaat testen op uw ontwikkelingscomputer, zou u de Rights Management Services SDK 2.1 al geïnstalleerd moeten hebben. De AD RMS Client 2.1 is toen op de achtergrond ook geïnstalleerd.

        Zie [De SDK installeren](create-your-first-rights-aware-application.md) voor meer informatie over het installeren van de RMS SDK 2.1.

    -   Als u uw toepassing gaat testen op een andere computer dan uw ontwikkelingscomputer, kunt u de AD RMS Client 2.1 op die computer installeren via de [AD RMS Client 2.1-downloadpagina](http://www.microsoft.com/en-us/download/details.aspx?id=38396).
        **Opmerking:** als uw toepassing gebruikmaakt van de server-API-modus (**IPC\_API\_MODE\_SERVER**), hoeft u geen toepassingsmanifest te gebruiken. U kunt uw toepassing testen op een RMS-productieserver en u hoeft geen productielicentie te verkrijgen wanneer u overschakelt naar een productieomgeving. Zie [Toepassingstypen](application-types.md) voor meer informatie over servermodustoepassingen.

         

-   Als u aan de slag gaat in de preproductieomgeving, moet u een RMS-server hebben geïnstalleerd en geconfigureerd. Zie [De server installeren en configureren](how-to-install-and-configure-an-rms-server.md) voor meer informatie.

Instructies

### Stap 1: de RMS Client 2.1 instellen voor de preproductiecertificeringshiërarchie

In de volgende stappen wordt beschreven hoe u de runtime voor ontwikkelaars installeert, hoe u de client configureert voor gebruik van de ISV-certificeringshiërarchie (voor preproductie) en hoe u servicedetectie op de client instelt.

1.  Kopieer de runtime voor ontwikkelaars, Ipcsecproc\_isv.dll, van %MSIPCSDKDIR%\\bin\\x86 (voor 32-bits versies van Windows) of %MSIPCSDKDIR\\bin\\x64 (voor 64-bits versies van Windows) naar C:\\Program Files\\Active Directory Rights Management Services Client 2.1.

    **Belangrijk:** als u een 32-bits toepassing uitvoert op een 64-bits versie van Windows, moet u Ipcsecproc\_isv.dll vanaf %MSIPCSDKDIR%\\bin\\x86 kopiëren naar C:\\Program Files(x86)\\Active Directory Rights Management Services Client 2.1.

     

2.  Configureer de AD RMS Client 2.1 zodanig dat de ISV-certificeringshiërarchie (voor preproductie) wordt gebruikt. Stel hiervoor de registersleutelwaarde van **Hiërarchie** in op 1.

    ```
    HKEY_LOCAL_MACHINE
       SOFTWARE
          Microsoft
             MSIPC
                Hierarchy DWORD = 00000001
                Data type
                DWORD
    ```

    **Opmerking:** als de waarde **Hiërarchie** niet aanwezig is in het register, staat dat gelijk aan het instellen van de waarde op 0 (nul). Dat betekent dat de RMS SDK 2.1 in de productiemodus wordt uitgevoerd. Zie [Certificaatketens begrijpen](understanding-certificate-chains.md) voor meer informatie over sleutels en certificaatketens.

    **Belangrijk**  
    Als u een 32-bits toepassing uitvoert in een 64-bits versie van Windows, moet u de waarde **Hiërarchie** op de volgende sleutellocatie instellen:

    ```
    HKEY_LOCAL_MACHINE
        SOFTWARE
           Wow6432Node
              Microsoft
                MSIPC
    ```
     

3.  Configureer detectie aan de serverzijde of aan de clientzijde om de AD RMS Client 2.1 in staat te stellen uw RMS-server voor preproductie te detecteren en ermee te communiceren.

    -   Bij detectie aan de serverzijde registreert een beheerder met Active Directory een serviceaansluitpunt (SCP) voor het preproductie-RMS-basiscluster. De client stuurt een query naar Active Directory om het SCP te detecteren en verbinding te maken met de server.
    -   Bij detectie aan de clientzijde configureert u de instellingen voor RMS-servicedetectie in het register op de computer waarop de AD RMS Client 2.1 wordt uitgevoerd. Deze instellingen verwijzen de AD RMS Client 2.1 naar de RMS-server die moet worden gebruikt. Als deze aanwezig zijn, wordt er geen detectie uitgevoerd aan de serverzijde.

    Als u detectie aan de clientzijde wilt configureren, kunt u de volgende registersleutels instellen, zodat wordt verwegen naar uw RMS-server voor preproductie. Voor meer informatie over het configureren van detectie aan de servicezijde raadpleegt u [Opmerkingen bij de implementatie van de RMS Client 2.0](https://TechNet.Microsoft.Com/en-us/library/jj159267(WS.10).aspx).

|Sleutel|Waarde|
|---|-----|
|`HKEY_LOCAL_MACHINE\`<br>`SOFTWARE\`<br>`Microsoft\`<br>`MSIPC\`<br>`ServiceLocation\`<br>`EnterpriseCertification`|(Standaard):<br><br> [**http**&#124;**https**]**://** *RMSClusterName* **/_wmcs/Certification**|
|`HKEY_LOCAL_MACHINE\`<br>`SOFTWARE\`<br>`Microsoft\`<br>`MSIPC\`<br>`ServiceLocation\`<br>`EnterprisePublishing`|(Standaard):<br><br> [**http**&#124;**https**]**://** *RMSClusterName* **/_wmcs/Licensing**|


**Opmerking** Standaard komen deze sleutels niet voor in het register; ze moeten worden aangemaakt.
     
**Belangrijk**  
    Als u een 32-bits toepassing uitvoert in een 64-bits versie van Windows, moet u deze sleutels op de volgende sleutellocatie instellen:


    HKEY_LOCAL_MACHINE
        SOFTWARE
           Wow6432Node
              Microsoft
                MSIPC
    

### Opmerkingen

De instructies in dit onderwerp zijn niet uitgebreid. Voor gedetailleerde informatie over het configureren van de AD RMS Client 2.1 raadpleegt u [Opmerkingen bij de implementatie van de RMS Client 2.0](https://TechNet.Microsoft.Com/en-us/library/jj159267(WS.10).aspx).

## Verwante onderwerpen


* [Gebruik](how-to-use-msipc.md)
* [Opmerkingen bij de implementatie van de RMS-client 2.0](https://TechNet.Microsoft.Com/en-us/library/jj159267(WS.10).aspx)
* [De SDK installeren](create-your-first-rights-aware-application.md)
* [De server installeren en configureren](how-to-install-and-configure-an-rms-server.md)
* [Een toepassing met rechten testen](running-your-first-application.md)
* [Certificaatketens begrijpen](understanding-certificate-chains.md)
 

 


<!--HONumber=Apr16_HO4-->


