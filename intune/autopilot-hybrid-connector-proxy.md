---
title: Proxyinstellingen configureren voor de Intune Connector voor Active Directory
description: Hierin leest u hoe u de Intune Connector voor Active Directory moet configureren om te gebruiken in combinatie met bestaande on-premises proxyservers.
keywords: ''
author: master11218
ms.author: tanvira
manager: smantri
ms.date: 4/16/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: tanvira
ms.suite: ems
search.appverid: ''
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: ebefba3f912669166e5e077fe15b0b04f4a7b75f
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/23/2019
ms.locfileid: "61489993"
---
# <a name="work-with-existing-on-premises-proxy-servers"></a>Werken met bestaande on-premises proxyservers

In dit artikel wordt uitgelegd hoe u de Intune Connector voor Active Directory configureert zodat u met uitgaande proxyservers kunt werken. Het is bedoeld voor klanten met netwerkomgevingen met bestaande proxy's.

Zie [Meer informatie over Azure AD-toepassingsproxyconnectoren](https://docs.microsoft.com/en-us/azure/active-directory/manage-apps/application-proxy-connectors) voor meer informatie over de werking van connectoren.

## <a name="bypass-outbound-proxies"></a>Uitgaande proxy's overslaan

Connectoren hebben onderliggende besturingssysteemonderdelen waardoor de uitgaande aanvragen worden gemaakt. Deze onderdelen zoeken automatisch een proxyserver in het netwerk met behulp van Web Proxy Auto-Discovery (WPAD).

De besturingssysteemonderdelen zoeken een proxyserver door een DNS-zoekactie voor wpad.domainsuffix uit te voeren. Als de zoekopdracht wordt omgezet in DNS, wordt vervolgens een HTTP-aanvraag ingediend op het IP-adres voor wpad.dat. Deze aanvraag wordt het proxyconfiguratiescript in uw omgeving. Dit script wordt door de connector gebruikt om een uitgaande proxyserver te selecteren. Het is echter mogelijk dat verkeer op de connector nog steeds niet doorkomt, omdat er extra configuratie-instellingen nodig zijn op de proxy.

U kunt de connector configureren om uw on-premises proxy over te slaan, zodat u zeker weet dat de connector rechtstreeks is verbonden met de Azure-services. Dit is de aanbevolen methode zolang deze mogelijk is volgens uw netwerkbeleid, omdat u in dit geval één configuratie minder hoeft te onderhouden.

Als u het proxygebruik voor de connector wilt uitschakelen, bewerkt u het bestand :\Program Files\Microsoft Intune\ODJConnector\ODJConnectorUI\ODJConnectorUI.exe.config en voegt u het proxyadres en de proxypoort toe in het deel dat in dit codevoorbeeld wordt weergegeven:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
    <system.net>  
        <defaultProxy>   
            <proxy proxyaddress="<PROXY ADDRESS HERE>:<PORT HERE>" bypassonlocal="True" usesystemdefault="True"/>   
        </defaultProxy>  
    </system.net>
    <runtime>
        <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
            <dependentAssembly>
                <assemblyIdentity name="mscorlib" publicKeyToken="b77a5c561934e089" culture="neutral"/>
                <bindingRedirect oldVersion="0.0.0.0-2.0.0.0" newVersion="4.6.0.0" />
            </dependentAssembly>
        </assemblyBinding>
    </runtime>
    <startup> 
        <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6" />
    </startup>
    <appSettings>
        <add key="SignInURL" value="https://portal.manage.microsoft.com/Home/ClientLogon"/>
        <add key="LocationServiceEndpoint" value="RestUserAuthLocationService/RestUserAuthLocationService/ServiceAddresses"/>
    </appSettings>
</configuration>
```
U moet een vergelijkbare wijziging doorvoeren in het bestand C:\Program Files\Microsoft Intune\ODJConnector\ODJConnectorSvc\ODJConnectorSvc.exe.config om ervoor te zorgen dat ook de Connector Updater-service de proxy overslaat.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
    <system.net>  
        <defaultProxy>   
            <proxy proxyaddress="<PROXY ADDRESS HERE>:<PORT HERE>" bypassonlocal="True" usesystemdefault="True"/>   
        </defaultProxy>  
    </system.net>
    <startup>
        <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6" />
    </startup>
    <appSettings>
        <add key="BaseServiceAddress" value="https://manage.microsoft.com/" />
    </appSettings>
</configuration>
```

Vergeet niet om kopieën van de oorspronkelijke bestanden te maken, in het geval u de .config-bestanden naar de standaardinstellingen moet terugzetten.

Zodra de configuratiebestanden zijn aangepast, moet u de Intune-connectorservice opnieuw opstarten. 

1. Open **services.msc**.
2. Zoek en selecteer de **Intune ODJConnector-service**.
3. Selecteer **Opnieuw opstarten**.

![Schermopname van het opnieuw opstarten van de service](media/autopilot-hybrid-connector-proxy/service-restart.png)


## <a name="next-steps"></a>Volgende stappen

[Uw apparaten beheren](device-management.md)