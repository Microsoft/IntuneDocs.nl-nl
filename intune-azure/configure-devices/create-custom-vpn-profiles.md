---
title: Aangepaste VPN-profielen maken met Microsoft Intune
titleSuffix: Intune Azure preview
description: Aangepaste configuraties gebruiken om VPN-profielen te maken in Intune.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: ca4f1adc5704ecd66d2af7823f95ca63ec20469e
ms.openlocfilehash: 990f3ff6528b537d1ea62c82440f1e46bcde8c95
ms.lasthandoff: 03/17/2017


---

# <a name="how-to-create-custom-vpn-profiles-in-microsoft-intune"></a>Aangepaste VPN-profielen maken in Microsoft Intune

## <a name="create-a-custom-configuration"></a>Een aangepaste configuratie maken
U kunt aangepast Intune-configuratiebeleid gebruiken om VPN-profielen te maken voor:

* Apparaten met Android 4 en hoger
* Geregistreerde apparaten met Windows 8.1 en hoger
* Apparaten met Windows Phone 8.1 en hoger
* Geregistreerde apparaten met Windows 10 Desktop 
* Apparaten met Windows 10 Mobile

Dit type beleid kan handig zijn wanneer het standaardbeleid voor Intune VPN niet de instellingen bevat die u wilt gebruiken.

## <a name="to-create-a-custom-configuration-policy"></a>Een aangepast configuratiebeleid maken:

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Overige** > **Intune**.
3. Kies op de blade **Intune** de optie **Apparaatconfiguratie**.
4. Kies **Beheren** > **Profielen** op de blade **Apparaatconfiguratie**.
5. Kies **Profiel maken** op de blade Profielen.
6. Voer op de blade **Profiel maken** een **naam** en een **beschrijving** in voor het VPN-profiel.
7. Selecteer in de vervolgkeuzelijst **Platform** het apparaatplatform waarop u de VPN-instellingen wilt toepassen. Op dit moment kunt u een van de volgende platformen kiezen voor aangepaste apparaatinstellingen:
    - **Android**
    - **iOS** (geconfigureerd met een bestand dat u hebt geëxporteerd uit Apple Configurator).
    - **macOS** (geconfigureerd met een bestand dat u hebt geëxporteerd uit Apple Configurator).
    - **Windows Phone 8.1**
    - **Windows 10 en hoger**
6. Kies **Aangepast** in de vervolgkeuzelijst **Profieltype**.
7. Kies **Toevoegen** op de blade **Aangepaste OMA-URI-instellingen** voor elke URI-instelling die u wilt opgeven, geef de gevraagde gegevens op en kies vervolgens **OK**. Hier volgt een voorbeeld:

   ![Dialoogvenster met aangepaste configuratie van een VPN-profiel](./media/Intune_Add_VPN_URI.png)

4.  Nadat u alle vereiste URI-instellingen hebt ingevoerd, kiest u **OK** en kiest u **Maken** op de blade **Profiel maken**.

Het profiel wordt gemaakt en wordt weergegeven op de blade met de profielenlijst.
Zie [How to assign device profiles](how-to-assign-device-profiles.md) (Apparaatprofielen toewijzen) als u wilt doorgaan en dit profiel wilt toewijzen aan groepen.

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




