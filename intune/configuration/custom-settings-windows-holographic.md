---
title: Aangepaste instellingen - Windows Holographic for Business-apparaten - Microsoft Intune
description: Maak een aangepast profiel of voeg dit toe om de OMA-URI-instellingen te gebruiken voor apparaten met Windows Holographic for Business in Microsoft Intune, waaronder Microsoft Hololens. U kunt de instellingen AllowFastReconnect, AllowVPN, AllowUpdateService, UpdateServiceURL, RequireUpdatesApproval, ApprovedUpdates en ApplicationLaunchRestrictions-beleid Configuration Service Provider (CSP) opgeven.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/06/2018
ms.article: article
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.topic: reference
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 54c38bac5ddf9eee1dd5f1dc6d544de3fa2395ab
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72506901"
---
# <a name="use-custom-settings-for-windows-holographic-for-business-devices-in-intune"></a>Aangepaste instellingen gebruiken voor apparaten met Windows Holographic for Business in Intune

Met Microsoft Intune kunt u aangepaste instellingen voor uw Windows Holographic for Business-apparaten toevoegen of maken met behulp van 'aangepaste profielen'. Aangepaste profielen zijn een functie in Intune. Ze zijn ontworpen om apparaatinstellingen en -functies toe te voegen die niet in Intune zijn ingebouwd.

In aangepaste profielen voor Windows Holographic for Business worden OMA-URI-instellingen (Open Mobile Alliance Uniform Resource Identifier) gebruikt om verschillende functies te configureren. Deze instellingen worden doorgaans gebruikt door fabrikanten van mobiele apparaten om functies op het apparaat te beheren.

Met behulp van Windows Holographic for Business komen veel instellingen voor configuratieserviceproviders (CSP's) ter beschikking. Zie [Inleiding tot configuratieserviceproviders (CSP's) voor IT-professionals](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers) voor een overzicht van CSP’s. Zie [CSP's die worden ondersteund in Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens) voor specifieke CSP’s die door Windows Holographic worden ondersteund.

Als u een specifieke instelling zoekt, moet u er rekening mee houden dat het [beperkingsprofiel voor Windows Holographic for Business-apparaten](device-restrictions-windows-holographic.md) tal van ingebouwde instellingen bevat. U hoeft daarom mogelijk geen aangepaste waarden in te voeren.

In dit artikel wordt beschreven hoe u een aangepast profiel maakt voor Windows Holographic for Business-apparaten. Het bevat ook een lijst met de aanbevolen OMA-URI-instellingen.

## <a name="create-the-profile"></a>Het profiel maken

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Voer de volgende instellingen in:

    - **Naam**: voer een naam in voor het profiel, zoals `hololens custom profile`.
    - **Beschrijving:** voer een beschrijving in voor het profiel.
    - **Platform**: kies **Windows 10 en hoger**.
    - **Profieltype**: kies **Aangepast**.

4. Selecteer in **Aangepaste OMA-URI-instellingen** de optie **Toevoegen**. Voer de volgende instellingen in:

    - **Naam**: voer een unieke naam in voor de OMA-URI-instelling waaraan u deze kunt herkennen in de lijst met instellingen.
    - **Beschrijving**: voer een beschrijving in met een overzicht van de instelling en eventuele andere belangrijke details.
    - **OMA-URI** (hoofdlettergevoelig): voer de OMA-URI in die u als instelling wilt gebruiken.
    - **Gegevenstype**: kies het gegevenstype dat u voor deze OMA-URI-instelling gaat gebruiken. Uw opties zijn:

        - Tekenreeks
        - Tekenreeks (XML-bestand)
        - Datum en tijd
        - Geheel getal
        - Drijvende komma
        - Boolean-waarde
        - Base64 (bestand)

    - **Waarde**: voer de gegevenswaarde in die moet worden gekoppeld aan de OMA-URI die u hebt ingevoerd. De waarde is afhankelijk van het gegevenstype dat u hebt geselecteerd. Als u bijvoorbeeld **Datum en tijd** hebt gekozen, selecteert u de waarde in een datumkiezer.

    Nadat u een aantal instellingen hebt toegevoegd, kunt u **Exporteren** selecteren. Met **Exporteren** maakt u een lijst met alle waarden die u hebt toegevoegd in een bestand met door komma's gescheiden waarden (.csv).

5. Selecteer **OK** om uw wijzigingen op te slaan. Blijf, indien nodig, meer instellingen toevoegen.
6. Wanneer u klaar bent, kiest u **OK** > **Maken** om het Intune-profiel te maken. Wanneer het profiel is gemaakt, wordt dit weergegeven in de lijst **Apparaatconfiguratie - profielen**.

## <a name="recommended-custom-settings"></a>Aanbevolen aangepaste instellingen

De volgende instellingen zijn handig voor apparaten waarop Windows Holographic for Business wordt uitgevoerd:

### <a name="allowfastreconnecthttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-authenticationauthentication-allowfastreconnect"></a>[AllowFastReconnect](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-allowfastreconnect)

> [!div class="mx-tableFixed"]
> |OMA-URI|Gegevenstype|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Authentication/AllowFastReconnect|Geheel getal<br/>0: niet toegestaan<br/>1: toegestaan (standaard)|

### <a name="allowupdateservicehttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-allowupdateservice"></a>[AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)

> [!div class="mx-tableFixed"]
> |OMA-URI|Gegevenstype|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Update/AllowUpdateService|Geheel getal<br/>0: updateservice niet toegestaan <br/>1: updateservice toegestaan (standaard).|

### <a name="allowvpnhttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-settingssettings-allowvpn"></a>[AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)

> [!div class="mx-tableFixed"]
> |OMA-URI|Gegevenstype|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Geheel getal<br/>0: niet toegestaan<br/>1: toegestaan (standaard)|

### <a name="requireupdatesapprovalhttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-requireupdateapproval"></a>[RequireUpdatesApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)

> [!div class="mx-tableFixed"]
> |OMA-URI|Gegevenstype|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Update/RequireUpdateApproval|Geheel getal<br/>0: niet geconfigureerd. Alle toepasselijke updates worden op het apparaat geïnstalleerd.<br/>1: op het apparaat worden alleen updates geïnstalleerd die toepasselijk zijn en op de lijst Toegestane updates staan. Stel dit beleid in op 1 als de IT-afdeling controle wilt behouden over de implementatie van updates op apparaten, zoals wanneer er vóór het implementeren tests moeten worden uitgevoerd.|

### <a name="scheduledinstalltimehttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-scheduledinstalltime"></a>[ScheduledInstallTime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduledinstalltime)

> [!div class="mx-tableFixed"]
> |OMA-URI|Gegevenstype|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime|Geheel getal 0-23, waarbij 0=12AM en 23=11PM<br/>De standaardwaarde is 3.|

### <a name="updateserviceurlhttpsdocsmicrosoftcomwindowsclient-managementmdmpolicy-csp-updateupdate-updateserviceurl"></a>[UpdateServiceURL](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)

> [!div class="mx-tableFixed"]
> |OMA-URI|Gegevenstype|
> |---|---|
> |./Vendor/MSFT/Policy/Config/Update/UpdateServiceUrl|Tekenreeks<br/>URL: het apparaat controleert via de opgegeven URL op updates van de WSUS-server.<br/>Niet geconfigureerd: het apparaat controleert op updates via Microsoft Update.|

### <a name="approvedupdateshttpsdocsmicrosoftcomwindowsclient-managementmdmupdate-csp"></a>[ApprovedUpdates](https://docs.microsoft.com/windows/client-management/mdm/update-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Gegevenstype|
> |---|---|
> |./Vendor/MSFT/Update/ApprovedUpdates/*GUID*<br/><br/>**Belangrijk**<br/>U moet de bijgewerkte gebruiksrechtovereenkomsten lezen en accepteren namens uw eindgebruikers. Als u dit niet doet, is dat een schending van de juridische of contractuele verplichtingen.|Knooppunt voor update-goedkeuringen en acceptatie van gebruiksrechtovereenkomsten namens de eindgebruiker.<br/><br/>Raadpleeg voor meer informatie [Update CSP](https://docs.microsoft.com/windows/client-management/mdm/update-csp).|

### <a name="applicationlaunchrestrictionshttpsdocsmicrosoftcomwindowsclient-managementmdmapplocker-csp"></a>[ApplicationLaunchRestrictions](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Gegevenstype|
> |----|---|
> |./Vendor/MSFT/AppLocker/ApplicationLaunchRestrictions/*Grouping*/*ApplicationType*/Policy<br/><br/>**Belangrijk**<br/>In het AppLocker CPS-artikel wordt gebruikgemaakt van XML-voorbeelden met het escape-teken. Als u de instellingen wilt configureren met aangepaste Intune-profielen, moet u gewone XML gebruiken.|Tekenreeks<br/>Raadpleeg [AppLocker CSP](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp) voor meer informatie.|

### <a name="deletionpolicyhttpsdocsmicrosoftcomwindowsclient-managementmdmaccountmanagement-csp"></a>[DeletionPolicy](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Gegevenstype|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/DeletionPolicy|Geheel getal<br/>0 - meteen verwijderen zodra het apparaat terugkeert naar een toestand zonder momenteel actieve gebruikers<br/>1 - verwijderen bij limiet opslagcapaciteit (standaard)<br/>2 - verwijderen bij zowel een opslagcapaciteitslimiet als limiet voor inactieve profielen|

### <a name="enableprofilemanagerhttpsdocsmicrosoftcomwindowsclient-managementmdmaccountmanagement-csp"></a>[EnableProfileManager](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Gegevenstype|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/EnableProfileManager|Boolean-waarde<br/>Waar - inschakelen<br/>Onwaar - uitschakelen (standaard)|

### <a name="profileinactivitythresholdhttpsdocsmicrosoftcomwindowsclient-managementmdmaccountmanagement-csp"></a>[ProfileInactivityThreshold](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Gegevenstype|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/ProfileInactivityThreshold|Geheel getal<br/>De standaardwaarde is 30.|


### <a name="storagecapacitystartdeletionhttpsdocsmicrosoftcomwindowsclient-managementmdmaccountmanagement-csp"></a>[StorageCapacityStartDeletion](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Gegevenstype|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/StorageCapacityStartDeletion|Geheel getal<br/>De standaardwaarde is 25.|

### <a name="storagecapacitystopdeletionhttpsdocsmicrosoftcomwindowsclient-managementmdmaccountmanagement-csp"></a>[StorageCapacityStopDeletion](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp)

> [!div class="mx-tableFixed"]
> |OMA-URI|Gegevenstype|
> |----|---|
> |./Vendor/MSFT/AccountManagement/UserProfileManagement/StorageCapacityStopDeletion|Geheel getal<br/>De standaardwaarde is 50.|

## <a name="find-the-policies-you-can-configure"></a>De beleidsregels zoeken die u kunt configureren

U vindt een volledige lijst met alle configuratieserviceproviders (CSP's) die door Windows Holographic worden ondersteund in [CSP's die worden ondersteund in Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens). Niet alle instellingen zijn compatibel met alle versies van Windows Holographic. In de tabel in [CSP's die worden ondersteund in Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens) worden de ondersteunde versies voor elke CSP vermeld.

Bovendien worden niet alle instellingen ondersteund die worden vermeld in [CSP's die worden ondersteund in Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens) door Intune. Als u wilt weten of de gewenste instelling door Intune wordt ondersteund, opent u het artikel voor de betreffende instelling. U kunt op elke instellingenpagina zien welke bewerkingen worden ondersteund. Voor gebruik in combinatie met Intune moet de instelling de bewerking **Toevoegen** of **Vervangen** ondersteunen.

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt nog niets. Vervolgens [wijst u het profiel toe](device-profile-assign.md).

Bekijk hoe u een aangepast profiel maakt op [Windows 10-apparaten](../custom-settings-windows-10.md).
