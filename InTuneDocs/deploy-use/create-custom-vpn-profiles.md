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
translationtype: Human Translation
ms.sourcegitcommit: f2b364b2c57adab33df2a8e6b34c1f30c02988d3
ms.openlocfilehash: 9dbb44981c1525e6137dd8a469b1582731ee9719


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
Zie [VPNv2 CSP](https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776.aspx) voor meer informatie over alle instellingen die u kunt gebruiken.

Native Contoso VPN (IKEv2): ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers

vpn.contoso.com ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/NativeProtocolType

Ikev2 ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/RoutingPolicyType

SplitTunnel ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/UserMethod

Eap ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/Eap/Configuration &lt;EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig"&gt;&lt;EapMethod&gt;&lt;Type xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;13&lt;/Type&gt;&lt;VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/VendorId&gt;&lt;VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/VendorType&gt;&lt;AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon"&gt;0&lt;/AuthorId&gt;&lt;/EapMethod&gt;&lt;Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig"&gt;&lt;Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1"&gt;&lt;Type&gt;13&lt;/Type&gt;&lt;EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1"&gt;&lt;CredentialsSource&gt;&lt;CertificateStore&gt;&lt;SimpleCertSelection&gt;true&lt;/SimpleCertSelection&gt;&lt;/CertificateStore&gt;&lt;/CredentialsSource&gt;&lt;ServerValidation&gt;&lt;DisableUserPromptForServerValidation&gt;false&lt;/DisableUserPromptForServerValidation&gt;&lt;ServerNames&gt;&lt;/ServerNames&gt;&lt;/ServerValidation&gt;&lt;DifferentUsername&gt;false&lt;/DifferentUsername&gt;&lt;PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2"&gt;false&lt;/PerformServerValidation&gt;&lt;AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2"&gt;false&lt;/AcceptServerName&gt;&lt;/EapType&gt;&lt;/Eap&gt;&lt;/Config&gt;&lt;/EapHostConfig&gt;

**./Vendor/MSFT/VPNv2/ContosoVPN/ByPassForLocal** True

**./Vendor/MSFT/VPNv2/ContosoVPN/RememberCredentials** 1

**./Vendor/MSFT/VPNv2/ContosoVPN/DomainNameInformationList/1/DomainName** Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/DnsSuffix** Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/TrustedNetworkDetection** Corp.Contoso.com

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/Address** 10.0.0.0

**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/PrefixSize** 8

**./Vendor/MSFT/VPNv2/ContosoVPN/AlwaysOn** true

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/0/App/Id** %PROGRAMFILES%\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/1/App/Id** %PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/2/App/Id** Microsoft.MicrosoftEdge_8wekyb3d8bbwe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/0/App/Id** %PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe

**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/1/App/Id** Microsoft.MicrosoftEdge_8wekyb3d8bbwe

Voor vragen over hoe deze instellingen moeten worden gebruikt of voor meer informatie over wat ze doen, raadpleegt u de CSP-documentatie (Configuration Service Provider): https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776(v=vs.85).aspx.

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



<!--HONumber=Dec16_HO3-->


