---
title: Een RMS-server installeren, configureren en hiermee tests uitvoeren | Azure RMS
description: RMS-server installeren en configureren voor het testen van uw toepassing met rechten.
keywords: 
author: bruceperlerms
manager: mbaldwin
ms.date: 06/28/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 32C7F387-CF7E-4CE0-AFC9-4C63FE1E134A
audience: developer
ms.reviewer: shubhamp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5d2339ece646fc51410186d43facdea28ac8fdfe
ms.openlocfilehash: d046e7f6bbe867b6bc867483441bb0cc5c20df82


---

# Instructies: een RMS-server installeren, configureren en hiermee tests uitvoeren

In dit onderwerp worden de stappen behandeld voor het verbinding maken met een RMS-server of Azure RMS om uw toepassing met rechten te testen.
 
## Instructies

### Stap 1: stel uw RMS-server in

Met de volgende stappen stelt u uw RMS-server in:

-   De server installeren
-   De server registreren

1.  **De server installeren**

    Active Directory Rights Management Services (AD RMS) bestaat uit afzonderlijke client- en serveronderdelen. Het serveronderdeel wordt geïmplementeerd als een set webservices die kan worden gebruikt om een RMS-infrastructuur te beheren, licenties te verlenen aan consumenten en uitgevers van inhoud, en certificaten uit te geven aan computers en gebruikers.

    Vanaf Windows Server 2008 maken de client- en serveronderdelen deel uit van het besturingssysteem. U kunt de serveronderdelen voor eerdere besturingssystemen downloaden van de volgende locatie.

    -   [RMS Server v1.0 SP2](http://go.microsoft.com/fwlink/p/?linkid=73722)

    Als u het serveronderdeel wilt configureren op Windows Server 2008, moet u de AD RMS-rol installeren. Als u toepassingen ontwikkelt voor een eerder serverbesturingssysteem, configureert u het register nadat u RMS Server v1.0 SP2 hebt geïnstalleerd, maar voordat u de RMS-service inricht.

2.  **De server registreren**

    U moet een Rights Management Services (RMS)-server registreren om deze te identificeren in de preproductiehiërarchie of productiehiërarchie. Na het inschrijvingsproces staat er een serverlicentiecertificaat op de servercomputer. Dit certificaat is gekoppeld aan een Microsoft-vertrouwensbasis. De wijze van registratie van de server is afhankelijk van welke versie van RMS u gebruikt.

    -   **Zelfregistratie**

        Vanaf Windows Server 2008 kunt u een RMS-server in de juiste hiërarchie registreren zonder dat er gegevens naar Microsoft worden verzonden. Wanneer u de RMS-rol installeert, worden er ook een certificaat voor zelfregistratie en een persoonlijke sleutel geïnstalleerd. Deze worden gebruikt om automatisch het serverlicentiecertificaat te maken. Er wordt geen informatie uitgewisseld met Microsoft.

    -   **Online-inschrijving**

        Online-inschrijving Als u AD RMS v1.0 SP2 gebruikt, kunt u de server online registreren. Inschrijving vindt plaats achter de schermen tijdens het inrichtingsproces, maar u moet beschikken over een internetverbinding.

        **HKEY\_LOCAL\_MACHINE**\\**Software**\\**Microsoft**\\**DRMS**\\**1.0**\\**UddiProvider** = 0e3d9bb8-b765-4a68-a329-51548685fed3

3. **Testen met RMS-server**

    Voor tests met een RMS-server, configureert u detectie aan de serverzijde of clientzijde om Rights Management Service-client 2.1 in te schakelen voor detectie en communicatie met de RMS-server.

    > [!Note]
    > Voor testen met Azure RMS is geen detectieconfiguratie vereist.

  - Bij detectie aan de serverzijde registreert een beheerder met Active Directory een serviceaansluitpunt (SCP) voor het RMS-basiscluster. De client stuurt een query naar Active Directory om het SCP te detecteren en verbinding te maken met de server.
  - Bij detectie aan de clientzijde configureert u de instellingen voor RMS-servicedetectie in het register op de computer waarop de RMS-client 2.1 wordt uitgevoerd. Deze instellingen verwijzen de RMS-client 2.1 naar de RMS-server die moet worden gebruikt. Als deze aanwezig zijn, wordt er geen detectie uitgevoerd aan de serverzijde.

  Als u detectie aan de clientzijde wilt configureren, kunt u de volgende registersleutels instellen, zodat wordt verwezen naar uw RMS-server. Voor meer informatie over het configureren van detectie aan de servicezijde raadpleegt u [Opmerkingen bij de implementatie van RMS-client 2.0](https://technet.microsoft.com/library/jj159267(WS.10).aspx).

1. **EnterpriseCertification**
        HKEY_LOCAL_MACHINE        SOFTWARE          Microsoft            MSIPC              ServiceLocation                EnterpriseCertification

  **Waarde**: (Standaard): [**http|https**]://RMSClusterName/**_wmcs/Certification**

2. **EnterprisePublishing**
        HKEY_LOCAL_MACHINE        SOFTWARE          Microsoft            MSIPC              ServiceLocation                EnterprisePublishing **Waarde**: (Standaard): [**http|https**]://RMSClusterName/**_wmcs/Licensing**

>[!NOTE] 
> Standaard komen deze sleutels niet voor in het register. Deze moeten worden gemaakt.

>[!IMPORTANT] 
> Als u een 32-bits toepassing uitvoert in een 64-bits versie van Windows, moet u deze sleutels op de volgende sleutellocatie instellen:<p>
  ```    
  HKEY_LOCAL_MACHINE
    SOFTWARE
      Wow6432Node
        Microsoft
          MSIPC
            ```

 

 



<!--HONumber=Aug16_HO4-->


