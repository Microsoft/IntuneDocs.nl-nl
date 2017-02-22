---
title: Aangepaste Intune-instellingen voor Windows 10-apparaten | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: in dit onderwerp vindt u informatie over de instellingen die u kunt gebruiken in een aangepast Windows 10-profiel.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7bcea136-7260-4042-b21b-c7dab86b380d
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0da8c0fe399f76f43439cc66eaecd12bb454f9a6
ms.openlocfilehash: 05856480f8bb76e561f2b459d4ab800f9909a40a


---

# <a name="custom-device-settings-for-windows-10-devices-in-intune-azure-preview"></a>Aangepaste apparaatinstellingen voor Windows 10-apparaten in Intune Azure Preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

 Gebruik het **aangepaste** profiel van Microsoft Intune voor Windows 10 en Windows 10 Mobile om OMA-URI-instellingen (Open Mobile Alliance Uniform Resource Identifier) te implementeren die kunnen worden gebruikt om functies op apparaten te beheren. In Windows 10 zijn veel instellingen toegankelijk via de [beleids-CSP (Configuration Service Provider)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).

1. Volg de instructies in [Aangepaste apparaatinstellingen configureren in Microsoft Intune](how-to-configure-custom-settings.md) om aan de slag te gaan.
2. Kies op de blade **Profiel maken** de optie **Instellingen** om een of meer OMA-URI-instellingen toe te voegen.
3. Klik op de blade **Aangepaste OMA-URI-instellingen** op **Toevoegen** om een nieuwe waarde toe te voegen. U kunt ook op **Exporteren** klikken om een lijst met alle geconfigureerde waarden te maken in een door komma's gescheiden bestand (.csv).
4. Voer voor elke OMA-URI-instelling die u wilt toevoegen de volgende informatie in. Gebruik de lijst in dit onderwerp voor meer informatie over de instellingen die u kunt gebruiken:
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
5. Als u klaar bent, gaat u terug naar de blade **Profiel maken** en kiest u **Maken**.
Het profiel wordt gemaakt en wordt weergegeven op de blade met de profielenlijst.

## <a name="example"></a>Voorbeeld
In de schermopname hieronder is de instelling **Conectivity/AllowVPNOverCellular** ingeschakeld. Hiermee kan met een Windows-10-apparaat een VPN-verbinding worden gemaakt in een mobiel netwerk.

> ![Voorbeeld van een aangepast beleid met VPN-instellingen](./media/custom-policy-example.png)


## <a name="policy-settings"></a>Beleidsinstellingen

|Naam van beleid en URI|Details|
|---------------|------------|-----------|
|**Automatisch bijwerken toestaan**<br>./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate|Alleen desktop<br>**Gegevenstype:** geheel getal<br />**Waarden:** **0** - **5** (standaard: **1**)|
|**Planning installatiedag**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay|Alleen mobiel<br>**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: elke dag (standaard)<br>**1**: zondag<br>**2**: maandag<br>**3**: dinsdag<br>**4**: woensdag<br>**5**: donderdag<br>**6**: vrijdag<br>**7**: zaterdag|
|**Planning installatietijd**<br>./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0** - **23** uur (**0** is middernacht) (standaard: **3**)|
|**DeviceLock/AllowIdleReturnWithoutPassword**<br>./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: de gebruiker kan de timer van de respijtperiode voor het wachtwoord niet instellen; de waarde is ingesteld als 'elke keer'<br>**1**: de gebruiker kan de timer voor de respijtperiode van het wachtwoord instellen (standaard)|
|**WiFi/AllowWiFi**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: **gebruik van Wi-Fi-verbinding** niet toestaan.<br>**1**: **gebruik van Wi-Fi-verbinding toestaan** (standaard).|
|**WiFi/AllowInternetSharing**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing|Desktop en mobiel<br>**Gegevenstype:** geheel getal<br />**Waarden:** **0**: delen via internet niet toestaan, **1**: delen via internet toestaan (standaard)|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**WiFi/AllowManualWiFiConfiguration**<br>./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: een Wi-Fi-verbinding buiten de ingerichte MDM is niet toegestaan.<br>**1**: het toevoegen van een nieuwe netwerk-SSID buiten de al aanwezige MDM is toegestaan (standaard).|
|**System/AllowLocation**<br>./Vendor/MSFT/Policy/Config/System/AllowLocation|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**System/AllowTelemetry**<br>./Vendor/MSFT/Policy/Config/System/AllowTelemetry|Desktop en mobiel<br>**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0** : niet toegestaan (instelling alleen voor Enterprise)<br>**1** : beperkt<br>**2**: volledig (standaard)<br>**3**: volledig en diagnostische gegevens|
|**System/AllowExperimentation**<br>./Vendor/MSFT/Policy/Config/System/AllowExperimentation|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0** : niet toegestaan<br>**1**: alleen instellingen (standaard)<br>**2**: instellingen en experimenteren|
|**Security/AntiTheftMode**<br>./Vendor/MSFT/Policy/Config/Security/AntiTheftMode|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: Antidiefstalmodus niet toestaan<br>**1**: gebruikersvoorkeur (standaard)|
|**Connectivity/AllowUSBConnection**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**System/AllowUserToResetPhone**<br>./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**Connectivity/AllowCellularDataRoaming**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**Connectivity/AllowVPNOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: VPN is niet toegestaan via mobiele verbindingen<br>**1**: VPN mag alle verbinding gebruiken, inclusief mobiele verbindingen (standaard)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**Connectivity/AllowBluetooth**<br>./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: de gebruiker niet toestaan Bluetooth in te schakelen.<br>**1**: gereserveerd. De gebruiker kan Bluetooth inschakelen en configureren (niet ondersteund in Windows Phone 8.1 voor MDM, EAS-, Windows 10 Desktop en Windows 10 Mobile)<br>**2**: toegestaan. De gebruiker kan Bluetooth inschakelen en configureren (standaard)|
|**Experience/AllowScreenCapture**<br>./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**Experience/AllowTaskSwitcher**<br>./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**Experience/AllowVoiceRecording**<br>./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**Experience/AllowSyncMySettings**<br>./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: roaming niet toestaan, **1**: roaming toestaan (standaard)|
|**Experience/AllowManualMDMUnenrollment**<br>./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**Accounts/AllowMicrosoftAccountConnection**<br>./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**<br>./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**Security/AllowManualRootCertificateInstallation**<br>./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**Security/AllowAddProvisioningPackages**<br>./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**Search/DisableBackoff**<br>./Vendor/MSFT/Policy/Config/Search/DisableBackoff|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0** (standaard), **1**|
|**Search/PreventRemoteQueries**<br>./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**, **1** (standaard)|
|**Search/AllowUsingDiacritics**<br>./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0** (standaard), **1**|
|**Search/AlwaysUseAutoLangDetection**<br>./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0** (standaard), **1**|
|**Search/DisableRemovableDriveIndexing**<br>./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0** (standaard), **1**|
|**Search/PreventIndexingLowDiskSpaceMB**<br>./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**, **1** (standaard)|
|**Search/AllowIndexingEncryptedStoresOrItems**<br>./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0** (standaard), **1**|
|**Security/AllowRemoveProvisioningPackage**<br>./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**Security/RequireProvisioningPackageSignature**<br>./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0** (standaard), **1**|
|**AboveLock/AllowActionCenterNotifications**<br>./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**TextInput/AllowIMENetworkAccess**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0** : niet toestaan<br>De functie Uitgebreid woordenboek openen is uitgeschakeld.<br>Een gebruiker kan niet:<br>- Een nieuwe functie Uitgebreid woordenboek openen toevoegen.<br />- Een nieuw configuratiebestand voor de integratie van zoekopdrachten toevoegen.<br>- De functie Cloudkandidaat gebruiken.<br>- Een door de gebruiker geregistreerd woord verzenden.<br>**1**: toestaan<br>Een functie Uitgebreid woordenboek openen kan standaard worden toegevoegd en gebruikt. De functie voor integratie van zoekbestanden kan ook standaard worden gebruikt.<br>De gebruiker kan:<br>De functie Cloudkandidaat gebruiken.|
|**TextInput/AllowIMELogging**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: Logboekregistratie voor een mislukte conversie is uitgeschakeld.<br>**1**: Logboekregistratie voor een mislukte conversie is ingeschakeld (standaard).|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**TextInput/AllowJapaneseIVSCharacters**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**TextInput/AllowJapaneseUserDictionary**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**er worden geen tekens gefilterd (standaardinstelling)<br>**1**: alle tekens worden gefilterd, behalve Shift-JIS-tekens|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br />**0**er worden geen tekens gefilterd (standaardinstelling)<br>**1**: alle tekens worden gefilterd, behalve JIS0208-tekens|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**<br>./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**er worden geen tekens gefilterd (standaardinstelling)<br>**1**: alle tekens worden gefilterd, behalve JIS0208-tekens en EUDC-tekens|
|**TextInput/AllowInputPanel**<br>./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**Bluetooth/AllowDiscoverableMode**<br>./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**Bluetooth/AllowAdvertising**<br>./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**Settings/AllowDataSense**<br>./Vendor/MSFT/Policy/Config/Settings/AllowDataSense|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**Settings/AllowVPN**<br>./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**Settings/AllowWorkplace**<br>./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**Settings/AllowDateTime**<br>./Vendor/MSFT/Policy/Config/Settings/AllowDateTime|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**Settings/AllowLanguage**<br>./Vendor/MSFT/Policy/Config/Settings/AllowLanguage|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**Settings/AllowRegion**<br>./Vendor/MSFT/Policy/Config/Settings/AllowRegion|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**Settings/AllowSignInOptions**<br>./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**Settings/AllowYourAccount**<br>./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**Settings/AllowPowerSleep**<br>./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**Settings/AllowAutoPlay**<br>./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**Experience/AllowCortana**<br>./Vendor/MSFT/Policy/Config/Experience/AllowCortana|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**Search/SafeSearchPermissions**<br>./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0** : strict, hoogste filtering tegen inhoud voor volwassenen<br>**1**: gemiddeld, gemiddelde filtering op inhoud voor volwassenen (geldige zoekresultaten worden standaard niet gefilterd)|
|**Experience/AllowCopyPaste**<br>./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**Startgrootte forceren**<br>./Vendor/MSFT/Policy/Config/Start/ForceStartSize|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: wijziging van grootte door gebruiker toestaan (standaard)<br>**1**: niet-volledig scherm afdwingen<br>**2**: volledig scherm afdwingen|
|**Update/RequireDeferUpgrade**<br>./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: upgrade niet uitstellen (in huidige vertakking blijven, CB (standaard))<br>**1**: toestaan dat updates en upgrades worden uitgesteld (apparaat volgt huidige vertakking voor bedrijven, CBB, regels)<br />Zie voor meer informatie:<br>[Inleiding tot Onderhoud van Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Plannen voor de implementatie van Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpdatePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod|Desktop en mobiel<br>**Beschrijving:** beleid om software-updates maximaal vier weken uit te stellen<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br> **0**: updates onmiddellijk toepassen (standaardinstelling)<br>**1**-**4**: aantal weken om software-updates uit te stellen.<br />Zie voor meer informatie:<br>[Inleiding tot Onderhoud van Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Plannen voor de implementatie van Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpgradePeriod**<br>./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod|Desktop en mobiel<br>**Beschrijving:** beleid om upgrades van functies tot maximaal 8 maanden uit te stellen<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: updates onmiddellijk toepassen (standaardinstelling)<br>**1**-**8**: aantal maanden dat functie-upgrades moeten worden uitgesteld.<br />Zie voor meer informatie:<br>[Inleiding tot Onderhoud van Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Plannen voor de implementatie van Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/PauseDeferrals**<br>./Vendor/MSFT/Policy/Config/Update/PauseDeferrals|Desktop en mobiel<br>**Beschrijving:** hiermee kunt u instellen dat een apparaat vijf weken geen updates en upgrades ontvangt.<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: updates onmiddellijk toepassen (standaardinstelling)<br>**1**: updates en upgrades tijdelijk onderbreken (vervalt na 5 weken)|

## <a name="windows-defender-settings"></a>Windows Defender-instellingen

|Naam van beleid en URI|Details|
|---------------|-----------|
|**AllowRealtimeMonitoring**<br>./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**AllowBehaviorMonitoring**<br>./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**AllowIntrusionPreventionSystem**<br>./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**AllowIOAVProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**AllowScriptScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**AllowOnAccessProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**RealTimeScanDirection**<br>./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: alle bestanden bewaken (standaard)<br>**1** : binnenkomende bestanden controleren<br>**1** : uitgaande bestanden controleren|
|**DaysToRetainCleanedMalware**<br>./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0** - **90**: geeft aan hoe lang malware behouden blijft<br>**Standaard:** **0**: blijft altijd in de map Quarantaine en wordt niet automatisch verwijderd|
|**AllowUserUIAccess**<br>./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**ScanParameter**<br>./Vendor/MSFT/Policy/Config/Defender/ScanParameter|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**1**: snelle scan (standaard)<br>**2**: volledige scan|
|**ScheduleScanDay**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: elke dag (standaard)<br>**1**: maandag<br>**2**: dinsdag<br>**3**: woensdag<br>**4**: donderdag<br>**5**: vrijdag<br>**6**: zaterdag<br>**7**: zondag<br>**8** : geen geplande scan|
|**ScheduleScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: 00:00 uur<br>**60** – 1:00 uur<br>**120**: 2:00 uur (standaardinstelling)<br>**180** – 3:00 uur<br>**240** – 4:00 uur<br>**300** – 5:00 uur<br>**360** – 6:00 uur<br>**420** – 7:00 uur<br>**480** – 8:00 uur<br>**540** – 9:00 uur<br>**600** – 10:00 uur<br>**660** – 11:00 uur<br>**720** – 12:00 uur<br>**780** – 13:00 uur<br>**840** – 14:00 uur<br>**900** – 15:00 uur<br>**960** – 16:00 uur<br>**1020** – 17:00 uur<br>**1080** – 18:00 uur<br>**1140** – 19:00 uur<br>**1200** – 20:00 uur<br>**1260** – 21:00 uur<br>**1320** – 22:00 uur<br>**1381** : onderhoudsvenster|
|**ScheduleQuickScanTime**<br>./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime|Alleen desktop<br>**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: 00:00 uur<br>**60** – 1:00 uur<br>**120**: 2:00 uur (standaardinstelling)<br>**180** – 3:00 uur<br>**240** – 4:00 uur<br>**300** – 5:00 uur<br>**360** – 6:00 uur<br>**420** – 7:00 uur<br>**480** – 8:00 uur<br>**540** – 9:00 uur<br>**600** – 10:00 uur<br>**660** – 11:00 uur<br>**720** – 12:00 uur<br>**780** – 13:00 uur<br>**840** – 14:00 uur<br>**900** – 15:00 uur<br>**960** – 16:00 uur<br>**1020** – 17:00 uur<br>**1080** – 18:00 uur<br>**1140** – 19:00 uur<br>**1200** – 20:00 uur<br>**1260** – 21:00 uur<br>**1320** – 22:00 uur<br>**1380** – 23:00 uur|
|**AVGCPULoadFactor**<br>./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0** - **100** (standaard: **50**)|
|**AllowArchiveScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**AllowEmailScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning|Alleen desktop<br />**Gegevenstype:** geheel getal<br>**Waarden:** **0**: niet toegestaan (standaard), **1**: toegestaan|
|**AllowFullScanRemovableDriveScanning**<br>./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan (standaard), **1**: toegestaan|
|**AllowFullScanOnMappedNetworkDrives**<br>./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**AllowScanningNetworkFiles**<br>./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard); wordt ook uitgevoerd wanneer RTP is ingesteld op toegestaan|
|**SignatureUpdateInterval**<br>./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: tijdens een interval niet op handtekeningen controleren<br>**1**: elk uur op handtekeningen controleren<br>**2**: elke 2 uur controleren, enz.<br>**24**: elke dag controleren<br>**Standaardwaarde:** 8: elke 8 uur controleren|
|**AllowCloudProtection**<br>./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toegestaan, **1**: toegestaan (standaard)|
|**SubmitSamplesConsent**<br>./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: altijd vragen (standaard)<br>**1** : veilige voorbeelden automatisch verzenden<br>**2** : nooit verzenden<br>**3** : alle voorbeelden automatisch verzenden|
|**ExcludedExtensions**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions|Alleen desktop<br />**Gegevenstype:** tekenreeks<br />**Waarden:**<br>*&lt;door puntkomma's gescheiden lijst met extensies&gt;* Bijvoorbeeld **obj; lib**<br>**Standaard:** er worden geen extensies uitgesloten|
|**ExcludedPaths**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths|Alleen desktop<br />**Gegevenstype:** tekenreeks<br />**Waarden:**<br />*&lt;door puntkomma's gescheiden lijst met paden&gt;*<br />Bijvoorbeeld: **c:\test;c:\test1.exe**<br />**Standaardwaarde:** er worden geen paden uitgesloten|
|**ExcludedProcesses**<br>./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses|Alleen desktop<br />**Gegevenstype:** tekenreeks<br />**Waarden:**<br>*&lt;door puntkomma's gescheiden lijst met paden&gt;*<br>Bijvoorbeeld: **c:\test.exe;c:\test1.exe**<br>**Standaardwaarde:** er worden geen processen uitgesloten|

## <a name="edge-browser-settings"></a>Edge-browserinstellingen

|Naam van beleid en URI|Details|
|---------------|------------|-----------|
|**Browser toestaan**<br>./Vendor/MSFT/Policy/Config/Browser/AllowBrowser|Alleen mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: bladeren uitgeschakeld, **1**: bladeren ingeschakeld (standaard)|
|**AllowSearchSuggestionsinAddressBar**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: suggesties niet weergeven, **1**: suggesties weergeven (standaard)|
|**SendIntranetTraffictoInternetExplorer**<br>./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: uitgeschakeld (intranetsites worden standaard geopend in de Microsoft Edge-browser)<br>**1**: ingeschakeld (intranetsites worden geopend in Internet Explorer)|
|**Do Not Track toestaan**<br>./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: uitgeschakeld (DNT niet verzonden, standaard), **1**: ingeschakeld (DNT verzenden)|
|**SmartScreen configureren**<br>./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: niet toestaan, **1**: toestaan (standaard)|
|**Pop-ups toestaan**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPopups|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: pop-ups blokkeren (standaard), **1**: pop-ups toestaan|
|**Cookies toestaan**<br>./Vendor/MSFT/Policy/Config/Browser/AllowCookies|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: cookies van alle websites toestaan (standaard)<br>**1**: alleen cookies van derden blokkeren<br>**2**: alle cookies blokkeren|
|**Wachtwoord opslaan toestaan**<br>./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager|Desktop en mobiel<br />**Gegevenstype:** geheel getal<br />**Waarden:**<br>**0**: wachtwoordbeheer is uitgeschakeld <br>**1**: wachtwoordbeheer is ingeschakeld (standaard)|
|**Automatisch invullen toestaan**<br>./Vendor/MSFT/Policy/Config/Browser/AllowAutofill|Alleen desktop<br />**Gegevenstype:** geheel getal<br />**Waarden:** **0**: uitgeschakeld (standaard), **1**: ingeschakeld|
|**Sitelijst voor ondernemingen configureren**<br>./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList|Alleen desktop<br />**Gegevenstype:** tekenreeks<br />**Waarden:<br>**0**: niet geconfigureerd, <br>**1**: de lijst met websites van Bedrijfsmodus gebruiken indien geconfigureerd (standaard)<br>**2**: de locatie van de lijst met websites van Bedrijfsmodus opgeven|



<!--HONumber=Feb17_HO1-->


