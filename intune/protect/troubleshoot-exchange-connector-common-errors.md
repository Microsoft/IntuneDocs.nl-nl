---
title: Veelvoorkomende fouten bij de intune Exchange connector oplossen
titleSuffix: Microsoft Intune
description: Problemen oplossen en veelvoorkomende fouten voor on-premises Microsoft Intune Exchange Connector oplossen
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/02/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: aa4dbfb7c13d767df41655b391767fc7aa13d914
ms.sourcegitcommit: f04e21ec459998922ba9c7091ab5f8efafd8a01c
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71817583"
---
# <a name="resolve-common-errors-for-the-intune-exchange-connector"></a>Veelvoorkomende fouten voor de intune Exchange connector oplossen

Dit artikel kan de intune-beheerder helpen bij het oplossen van specifieke fouten en berichten over de werking van de intune Exchange connector.  

## <a name="configuration-failed-and-returned-error-code-0x0000001"></a>De configuratie is mislukt en de geretourneerde fout code 0x0000001

**Probleem**:  
Wanneer u probeert de Microsoft Intune Exchange Connector te configureren, wordt het volgende fout bericht weer gegeven:

```
   The Microsoft Intune Exchange Connector cannot connect to the Microsoft Exchange server.  
   The following Microsoft Exchange Server address could not be reached <Exchange server Name FQDN>  
   Verify that the FQDN of the exchange server address and credentials that you entered is correct and the server is running. The Microsoft Intune Exchange Connector does not support Exchange server arrays.  
   Error code: 0x0000001  
```

Dit probleem kan optreden als de Internet proxy instellingen onjuist zijn geconfigureerd.

**Oplossing**:  
Proxy-instellingen configureren
1. Neem contact op met de lokale netwerk beheerder om te controleren of de proxy instellingen juist zijn geconfigureerd. 
2. Gebruik de **netsh WinHTTP** -opdracht om de proxy server te configureren en de vereiste uitsluitings lijst toe te voegen. Bijvoorbeeld:  

   ```
   Netsh winhttp set proxy proxy-server="http=proxy.corp.domain.com" bypass-list"34*.*;134.132.*.*;10.*.*;localhost;*.corp.domain.com;*.staging.domain.com"
   ```

## <a name="configuration-failed-and-returned-error-code-0x000000b"></a>De configuratie is mislukt en de geretourneerde fout code 0x000000b   

**Probleem**:  
Wanneer u probeert de Microsoft Intune Exchange Connector te configureren, wordt het volgende fout bericht weer gegeven:  

```
   The Microsoft Intune Exchange Connector experienced an error:  
   CertEnroll::CX509PrivateKey::Create: The system cannot find the file specified. 0x80070002 (WIN32: 2  
   ERROR_FILE_NOT_FOUND  
   Error code: 0x000000b  
```
Dit probleem kan zich voordoen als het account dat u hebt gebruikt om u aan te melden bij intune, niet het account van de globale beheerder van intune is.

**Oplossing**:  
Meld u aan bij intune met een account dat een globale beheerder is, of Voeg uw account toe aan de groep voor globale beheerders. Zie [Op rollen gebaseerd toegangsbeheer (RBAC) met Microsoft Intune](../fundamentals/role-based-access-control.md) voor meer informatie.

## <a name="configuration-failed-and-returned-error-code-0x0000006"></a>De configuratie is mislukt en de geretourneerde fout code 0x0000006

**Probleem**:  
Wanneer u probeert de Microsoft Intune Exchange Connector te configureren, wordt het volgende fout bericht weer gegeven:  

```  
   The Microsoft Intune Exchange Connector cannot connect to Microsoft Intune  
   Verify that you are connected to the Internet, check the Microsoft Intune Service Status, and try to connect again.  
   Error code: 0x00000006  
```  
Deze fout kan optreden als een proxy server wordt gebruikt om verbinding te maken met internet en verkeer naar de intune-service blokkeert. Ga naar **configuratie scherm** > **Internet opties**, selecteer het tabblad **verbinding** en klik op **LAN-instellingen**om te bepalen of een proxy in gebruik is.

**Oplossing**:  

- **Optie 1** : de proxy-instellingen verwijderen zodat de computer verbinding kan maken met internet zonder de proxy te passeren.  

- **Optie 2** : Configureer uw proxy server om communicatie toe te staan voor de intune-service, zoals beschreven in de vereisten voor de [Exchange connector van intune](exchange-connector-install.md#intune-exchange-connector-requirements).



## <a name="event-7000-or-7041-microsoft-intune-exchange-connector-service-wont-start"></a>Gebeurtenis 7000 of 7041: de Microsoft Intune Exchange Connector-service wordt niet gestart

**Probleem**:  
Een iOS-apparaat kan niet worden inge schreven bij intune en er wordt een van de volgende fout berichten gegenereerd:  

```  
   Log Name:      System
   Source:            Service Control Manager
   Date:               <time>
   Task Category: None
   Level:               Error
   Keywords:        Classic
   User:                N/A
   Computer:      <computer>
   Description:
   The Microsoft Intune Exchange Connector Service service failed to start because of the following error:  
   The service did not start because of a logon failure.
```  

```  
   Log Name:      System
   Source:            Service Control Manager
   Date:               <time>
   Event ID:          7041
   Task Category: None
   Level:               Error   
   Keywords:        Classic
   User:                N/A
   Computer:       <computer>
   Description:
   The WIEC service was unable to log on as .\WIEC_USER with the currently configured password because of the following error:
   Logon failure: the user has not been granted the requested logon type at this computer.
   Service: WIEC
   Domain and account: .\WIEC_USER
   This service account does not have the required user right "Log on as a service."  
```
Dit probleem kan zich voordoen als het **WIEC_User** -account het gebruikers recht **Aanmelden als service** niet heeft in het lokale beleid.

**Oplossing**:  
Wijs op de computer waarop de intune Exchange-connector wordt uitgevoerd, het recht **Aanmelden als service** gebruiker toe aan het **WIEC_User** -service account. Als de computer een knoop punt in een cluster is, moet u het recht *Aanmelden als service* gebruiker toewijzen aan het cluster service account op alle knoop punten in het cluster.  

Als u het recht **Aanmelden als service** gebruiker wilt toewijzen aan het **WIEC_User** -service account op de computer, volgt u deze stappen:

1. Meld u bij de computer aan als beheerder of als lid van de groep Administrators.
2. Voer **secpol. msc** uit om het lokale beveiligings beleid te openen.
3. Ga naar **beveiligings instellingen** > **lokaal beleid**en selecteer vervolgens **toewijzing van gebruikers rechten**.
4. Dubbel klik in het rechterdeel venster op **Aanmelden als een service**.
5. Selecteer **gebruiker of groep toevoegen**, Voeg **WIEC_USER** toe aan het beleid en selecteer vervolgens twee keer op **OK** .

Als het recht **Aanmelden als service** gebruiker is toegewezen aan **WIEC_User** , maar later is verwijderd, neemt u contact op met de domein beheerder om te bepalen of een Groepsbeleid instelling wordt overschreven.  

## <a name="next-steps"></a>Volgende stappen  

In het volgende artikel vindt u meer informatie over het oplossen van specifieke fouten:
- [Veelvoorkomende problemen oplossen voor de intune Exchange connector](troubleshoot-exchange-connector-common-problems.md). git 

Zoek hulp van ondersteuning of de intune-community.
- Zie [ondersteuning](../fundamentals/get-support.md) voor het gebruik van de intune-console voor hulp bij het oplossen van het probleem of voor het openen van een ondersteunings aanvraag bij micro soft. 
- Plaats uw probleem in de [Microsoft intune forums](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod).  
