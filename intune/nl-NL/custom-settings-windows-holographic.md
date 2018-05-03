---
title: Aangepaste instellingen voor apparaten met Windows Holographic for Business in Microsoft Intune - Azure | Microsoft Docs
description: Een aangepast profiel in Intune maken om de OMA-URI-instellingen te gebruiken voor apparaten met Windows Holographic for Business. U kunt de instellingen AllowFastReconnect, AllowVPN, AllowUpdateService, UpdateServiceURL, RequireUpdatesApproval, ApprovedUpdates en ApplicationLaunchRestrictions-beleid Configuration Service Provider (CSP) opgeven.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 4/26/2018
ms.article: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d1825d99243654c9fecac7729153a95234d435ff
ms.sourcegitcommit: 4c18352d5b3b30080f7c7257fa63d852b1894850
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/27/2018
---
# <a name="custom-device-settings-for-devices-running-windows-holographic-for-business-in-intune"></a>Aangepaste apparaatinstellingen voor apparaten met Windows Holographic for Business in Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

 Gebruik het **aangepaste** profiel van Microsoft Intune voor Windows Holographic for Business om OMA-URI-instellingen (Open Mobile Alliance Uniform Resource Identifier) te implementeren die kunnen worden gebruikt om functies op apparaten te beheren. Met behulp van Windows Holographic for Business komen veel instellingen voor configuratieserviceproviders (CSP's) ter beschikking. Zie [Inleiding tot configuratieserviceproviders (CSP's) voor IT-professionals](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers) voor een overzicht van CSP’s. Zie [CSP's die worden ondersteund in Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens) voor specifieke CSP’s die door Windows Holographic worden ondersteund.

Als u een bepaalde instelling zoekt, moet u er rekening mee houden dat het [beperkingsprofiel voor Windows Holographic for Business-apparaten](device-restrictions-windows-holographic.md) tal van ingebouwde instellingen bevat. U hoeft voor deze instellingen geen aangepaste waarden op te geven.

## <a name="create-the-custom-oma-uri-profile"></a>Het aangepaste OMA-URI-profiel maken
1. Volg de instructies in [Aangepaste apparaatinstellingen configureren in Microsoft Intune](custom-settings-configure.md) om aan de slag te gaan.
2. In **Profiel maken** kiest u de optie **Instellingen** om een of meer OMA-URI-instellingen toe te voegen.
3. In **Aangepaste OMA-URI-instellingen** klikt u op **Toevoegen** om een nieuwe waarde toe te voegen. U kunt ook op **Exporteren** klikken om een lijst met alle geconfigureerde waarden te maken in een door komma's gescheiden bestand (.csv).
4. Voer voor elke OMA-URI-instelling die u wilt toevoegen de volgende informatie in:
    - **Naam van de instelling**: voer een unieke naam in voor de OMA-URI-instelling waaraan u deze kunt herkennen in de lijst met instellingen.
    - **Beschrijving van de instelling:** voer eventueel een beschrijving in voor de instelling.
    - **Gegevenstype**: kies uit:
        - **Tekenreeks**
        - **Tekenreeks (XML)**
        - **Datum en tijd**
        - **Geheel getal**
        - **Drijvende komma**
        - **Booleaanse waarde**
    - **OMA-URI (hoofdlettergevoelig)**: geef aan voor welke OMA-URI u een instelling wilt opgeven.
    - **Waarde**: geef de waarde op die moet worden gekoppeld aan de OMA-URI die u hebt opgegeven.
1. Als u klaar bent, gaat u terug naar **Profiel maken** en kiest u **Maken**.
Het profiel wordt gemaakt en wordt weergegeven in de profielenlijst.

## <a name="recommended-custom-settings"></a>Aanbevolen aangepaste instellingen

De volgende instellingen zijn handig voor apparaten waarop Windows Holographic for Business wordt uitgevoerd:

### <a name="allowfastreconnecthttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-authenticationauthentication-allowfastreconnect"></a>[AllowFastReconnect](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-allowfastreconnect)

---
|OMA-URI|Gegevenstype  |
|---------|---------|
|./Vendor/MSFT/Policy/Config/Authentication/AllowFastReconnect|Geheel getal<br>0: niet toegestaan<br>1: toegestaan (standaard)|

### <a name="allowvpnhttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-settingssettings-allowvpn"></a>[AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)

---
|OMA-URI|Gegevenstype  |
|---------|---------|
|./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Geheel getal<br>0: niet toegestaan<br>1: toegestaan (standaard)|

### <a name="allowupdateservicehttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-allowupdateservice"></a>[AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)

---
|OMA-URI|Gegevenstype  |
|---------|---------|
|./Vendor/MSFT/Policy/Config/Update/AllowUpdateService|Geheel getal<br>0: updateservice niet toegestaan <br>1: updateservice toegestaan (standaard).|

### <a name="updateserviceurlhttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-updateserviceurl"></a>[UpdateServiceURL](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

---
|OMA-URI|Gegevenstype  |
|---------|---------|
|./Vendor/MSFT/Policy/Config/Update/UpdateServiceUrl|Tekenreeks<br>URL: het apparaat controleert via de opgegeven URL op updates van de WSUS-server.<br>Niet geconfigureerd: het apparaat controleert op updates via Microsoft Update.|

### <a name="requireupdatesapprovalhttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-requireupdateapproval"></a>[RequireUpdatesApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)

---
|OMA-URI|Gegevenstype  |
|---------|---------|
|./Vendor/MSFT/Policy/Config/Update/RequireUpdateApproval|Geheel getal<br>0: niet geconfigureerd. Alle toepasselijke updates worden op het apparaat geïnstalleerd.<br>1: op het apparaat worden alleen updates geïnstalleerd die toepasselijk zijn en op de lijst Toegestane updates staan. Stel dit beleid in op 1 als de IT-afdeling controle wilt behouden over de implementatie van updates op apparaten, zoals wanneer er vóór het implementeren tests moeten worden uitgevoerd.|

### <a name="approvedupdateshttpsdocsmicrosoftcomwindowsclient-managementmdmupdate-csp"></a>[ApprovedUpdates](https://docs.microsoft.com/windows/client-management/mdm/update-csp)

---
|OMA-URI|Gegevenstype  |
|---------|---------|
|./Vendor/MSFT/Update/ApprovedUpdates/*GUID*<br><br>**Belangrijk**<br>U moet de bijgewerkte gebruiksrechtovereenkomsten lezen en accepteren namens uw eindgebruikers. Als u dit niet doet, is dat een schending van de juridische of contractuele verplichtingen.|Knooppunt voor update-goedkeuringen en acceptatie van gebruiksrechtovereenkomsten namens de eindgebruiker.<br/><br/>Raadpleeg voor meer informatie [Update CSP](https://docs.microsoft.com/windows/client-management/mdm/update-csp).|

### <a name="applicationlaunchrestrictionshttpsdocsmicrosoftcomwindowsclient-managementmdmapplocker-csp"></a>[ApplicationLaunchRestrictions](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp)

---
|OMA-URI|Gegevenstype  |
|---------|---------|
|./Vendor/MSFT/AppLocker/ApplicationLaunchRestrictions/*Grouping*/*ApplicationType*/Policy<br><br>**Belangrijk**<br>In het AppLocker CPS-artikel wordt gebruikgemaakt van XML-voorbeelden met het escape-teken. Als u de instellingen wilt configureren met aangepaste Intune-profielen, moet u gewone XML gebruiken.|Tekenreeks<br>Raadpleeg [AppLocker CSP](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp) voor meer informatie.|

## <a name="find-the-policies-you-can-configure"></a>De beleidsregels zoeken die u kunt configureren

U vindt een volledige lijst met alle configuratieserviceproviders (CSP's) die door Windows Holographic worden ondersteund in [CSP's die worden ondersteund in Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens). Niet alle instellingen zijn compatibel met alle versies van Windows Holographic. In de tabel in het Windows-artikel kunt u zien welke versies voor elke CSP worden ondersteund.

Bovendien worden niet alle instellingen in het artikel door Intune ondersteund. Als u wilt weten of de gewenste instelling door Intune wordt ondersteund, opent u het artikel voor de betreffende instelling. U kunt op elke instellingenpagina zien welke bewerkingen worden ondersteund. Voor gebruik in combinatie met Intune moet de instelling de bewerking **Toevoegen** of **Vervangen** ondersteunen.
