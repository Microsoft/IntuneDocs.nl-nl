---
title: Aangepaste configuraties voor VPN-profielen | Microsoft Intune
description: Aangepaste configuraties gebruiken om VPN-profielen te maken in Intune.
keywords: 
author: Nbigman
manager: Arob98
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 72288296d966b9b9fae4fd721b4460528213f626
ms.openlocfilehash: b61a4c90cfed9922df151a6c1ac93e276db18623


---

# Aangepaste configuraties voor VPN-profielen

## Een aangepaste configuratie maken
Met aangepaste configuraties kunt u VPN-profielen maken in Intune. Ga als volgt te werk om een aangepaste configuratie te maken:

   1. Kies in de Intune-beheerconsole achtereenvolgens **Beleid** -> **Beleid toevoegen** -> *<Expand platform>* -> **Aangepaste configuratie** -> **Beleid maken**.
   2. Geef een naam voor het beleid op.
   3. Klik voor elke URI-instelling op **Toevoegen** en geef de gevraagde informatie op. Hier volgt een voorbeeld:

   ![Dialoogvenster met aangepaste configuratie van een VPN-profiel](./media/Intune_Add_VPN_URI.png)

   4.  Nadat u alle URI-instellingen hebt ingevoerd, klikt u op **Beleid opslaan** en vervolgens implementeert u het beleid.

## Een configuratiebeleid implementeren

1.  Selecteer het beleid dat u wilt implementeren in de werkruimte **Beleid** en klik vervolgens op **Implementatie beheren**.

2.  In het dialoogvenster **Implementatie beheren** :

    -   **Het beleid implementeren**: selecteer een of meer groepen waarvoor u het beleid wilt implementeren en klik vervolgens op **Toevoegen** &gt; **OK**.

    -   **Het dialoogvenster sluiten zonder het beleid te implementeren**: klik op **Annuleren**.

Wanneer u een geïmplementeerde beleid selecteert, kunt u meer informatie over de implementatie weergeven onder in de lijst met beleidsregels.

##Voorbeeld van URI-instellingen voor een aangepaste configuratie voor een VPN-profiel
Nu volgen enkele voorbeelden van vermeldingen voor URI-waarden om een aangepaste configuratie te maken voor een VPN-verbinding in een fictief bedrijf met de naam Contoso. Zie [VPNv2 CSP](https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776.aspx) voor meer informatie, zoals het gegevenstype voor elke vermelding

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

Voor vragen over hoe deze instellingen moeten worden gebruikt of voor meer informatie over wat ze doen, raadpleegt u de CSP-documentatie: https://msdn.microsoft.com/en-us/library/windows/hardware/dn914776(v=vs.85).aspx

## URI-instellingen voor VPN per Android-app op PulseSecure
### AANGEPASTE URI VOOR PAKKETLIJST 
-  Gegevenstype = tekenreeks
-  OMA-URI = ./Vendor/MSFT/VPN/Profile/<Name>/PackageList 
-  Waarde = door scheidingsteken gescheiden pakketlijst.
   - Scheidingstekens: puntkomma (;), dubbele punt (:), komma (,), sluisteken (|)

Voorbeelden: 
- com.android.chrome
- com.android.chrome;com.android.browser

### AANGEPASTE URI VOOR DE MODUS (OPTIONEEL)
- Gegevenstype = tekenreeks
- OMA-URI = ./Vendor/MSFT/VPN/Profile/NAME/Mode 

> Opmerkingen
> - Gebruik dezelfde *naam* die u aan het aangepaste profiel hebt toegewezen
> - Mogelijke waarden: *GLOBAL*, *WHITELIST*, *BLACKLIST*
> - De standaardwaarde is *GLOBAL* als er geen pakketlijst is opgegeven (achterwaartse compatibiliteit met systeembrede profielen)
> - De standaardwaarde is *WHITELIST* als er een pakketlijst is opgegeven


### Zie tevens
(VPN-verbindingen in Microsoft Intune) [vpn-verbindingen-in-microsoft-intune.md]



<!--HONumber=Jul16_HO3-->


