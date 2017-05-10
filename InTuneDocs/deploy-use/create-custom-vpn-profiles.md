---
title: Aangepaste configuraties voor Microsoft Intune VPN-profielen | Microsoft Docs
description: Aangepaste configuraties gebruiken om VPN-profielen te maken in Intune.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 56095b44e890759202d68312bd684c767d3410ce
ms.openlocfilehash: 284868ba0c79a6cbb1c3e5096a84461e99c0ba76
ms.contentlocale: nl-nl
ms.lasthandoff: 04/28/2017


---

# <a name="custom-configurations-for-microsoft-intune-vpn-profiles"></a>Aangepaste configuraties voor Microsoft Intune VPN-profielen

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="create-a-custom-configuration"></a>Een aangepaste configuratie maken
U kunt aangepast Intune-configuratiebeleid gebruiken om VPN-profielen te maken voor:

* Apparaten met Android 4 en hoger
* Apparaten met Android for Work
* Geregistreerde apparaten met Windows 8.1 en hoger
* Apparaten met Windows Phone 8.1 en hoger
* Geregistreerde apparaten met Windows 10 Desktop
* Apparaten met Windows 10 Mobile

Dit type beleid kan handig zijn wanneer het standaardbeleid voor Intune VPN niet de instellingen bevat die u wilt gebruiken.

## <a name="to-create-a-custom-configuration-policy"></a>Een aangepast configuratiebeleid maken:

   1. Kies in de [Intune-beheerconsole](https://manage.microsoft.com) **Beleid** > **Beleid toevoegen** > *Platform uitbreiden* > **Aangepaste configuratie** > **Beleid maken**.
   2. Geef een naam op voor het beleid.
   3. Kies **Toevoegen** voor elke URI-instelling die u wilt opgeven en verstrek de gevraagde informatie. Hier volgt een voorbeeld:

   ![Dialoogvenster met aangepaste configuratie van een VPN-profiel](./media/Intune_Add_VPN_URI.png)

   4.  Nadat u alle URI-instellingen hebt ingevoerd, kiest u **Beleid opslaan** en implementeert u vervolgens het beleid.

Vervolgens [implementeert u het beleid](/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy) op de gebruikelijke manier.

## <a name="example-uri-settings"></a>Voorbeelden van URI-instellingen

Deze instellingen kunnen worden gebruikt om een aangepaste configuratie te maken voor een VPN-verbinding in een fictief bedrijf met de naam Contoso.
Zie [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776.aspx) voor meer informatie over alle instellingen die u kunt gebruiken.

**Systeemeigen VPN voor Contoso (IKEv2):**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers

**vpn.contoso.com**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/NativeProtocolType

**Ikev2<br />** ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/RoutingPolicyType

**SplitTunnel**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/UserMethod

**Eap**<br />
./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/Eap/Configuration
``` xml
<EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
   <EapMethod>
      <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type>
      <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId>
      <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType>
      <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId>
   </EapMethod>
   <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
      <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1">
         <Type>13</Type>
         <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1">
            <CredentialsSource>
               <CertificateStore>
                  <SimpleCertSelection>true</SimpleCertSelection>
               </CertificateStore>
            </CredentialsSource>
            <ServerValidation>
               <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation>
               <ServerNames></ServerNames>
            </ServerValidation>
            <DifferentUsername>false</DifferentUsername>
            <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
               false
            </PerformServerValidation>
            <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
               false
            </AcceptServerName>
         </EapType>
      </Eap>
   </Config>
</EapHostConfig>
```
**./Vendor/MSFT/VPNv2/ContosoVPN/ByPassForLocal**<br />
True

**./Vendor/MSFT/VPNv2/ContosoVPN/RememberCredentials**<br />
1

**./Vendor/MSFT/VPNv2/ContosoVPN/DomainNameInformationList/1/DomainName**<br />
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/DnsSuffix**<br />
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/TrustedNetworkDetection**<br />
Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/Address**<br />
10.0.0.0

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/PrefixSize**<br />
8

**./Vendor/MSFT/VPNv2/ContosoVPN/AlwaysOn**<br />
waar

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/0/App/Id**<br />
%PROGRAMFILES%\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/1/App/Id**<br />
%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/2/App/Id**<br />
Microsoft.MicrosoftEdge_8wekyb3d8bbwe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/0/App/Id**<br />
%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/1/App/Id**<br />
Microsoft.MicrosoftEdge_8wekyb3d8bbwe

Voor vragen over hoe deze instellingen moeten worden gebruikt of voor meer informatie over wat ze doen, raadpleegt u de [CSP-documentatie (Configration Service Provider)](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx).

## <a name="uri-settings-for-android-per-app-vpn-on-pulsesecure"></a>URI-instellingen voor VPN per Android-app op PulseSecure
### <a name="custom-uri-for-package-list"></a>AANGEPASTE URI VOOR PAKKETLIJST
-  Gegevenstype = tekenreeks
-  OMA-URI = ./Vendor/MSFT/VPN/Profile/Name/PackageList
-  Waarde = door scheidingsteken gescheiden pakketlijst.
   - Scheidingstekens: puntkomma (;), dubbele punt (:), komma (,), sluisteken (|)

Voorbeelden:
- com.android.chrome
- com.android.chrome;com.android.browser

### <a name="custom-uri-for-mode-optional"></a>AANGEPASTE URI VOOR DE MODUS (OPTIONEEL)
- Gegevenstype = tekenreeks
- OMA-URI = ./Vendor/MSFT/VPN/Profile/NAME/Mode

> Opmerkingen
> - Gebruik dezelfde *naam* die u aan het aangepaste profiel hebt toegewezen
> - Mogelijke waarden: *GLOBAL*, *WHITELIST*, *BLACKLIST*
> - De standaardwaarde is *GLOBAL* als er geen pakketlijst is opgegeven (achterwaartse compatibiliteit met systeembrede profielen)
> - De standaardwaarde is *WHITELIST* als er een pakketlijst is opgegeven


### <a name="see-also"></a>Zie tevens
[VPN-verbindingen in Microsoft Intune](vpn-connections-in-microsoft-intune.md)

