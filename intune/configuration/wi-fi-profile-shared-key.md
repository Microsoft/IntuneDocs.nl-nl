---
title: Een Wi-Fi-profiel met een vooraf gedeelde sleutel maken - Microsoft Intune - Azure | Microsoft Docs
description: Gebruik een aangepast profiel om een Wi-Fi-profiel met een vooraf gedeelde sleutel te maken en ontvang XML-voorbeeldcode voor Android-, Windows- en op EAP gebaseerde Wi-Fi-profielen in Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/25/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c6fd72a6-7dc8-48fc-9df1-db5627a51597
ms.reviewer: karanda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 623c6652964ae5a4f16a9c689dda3aee99c50d31
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506491"
---
# <a name="use-a-custom-device-profile-to-create-a-wifi-profile-with-a-pre-shared-key---intune"></a>Een aangepast apparaatprofiel gebruiken om een Wi-Fi-profiel te maken met een vooraf gedeelde sleutel - Intune
[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Vooraf gedeelde sleutels (PSK) worden doorgaans gebruikt om gebruikers in Wi-Fi-netwerken of draadloze LAN's te verifiëren. Met Intune kunt u Wi-Fi-profielen met vooraf gedeelde sleutels maken. Als u een profiel wilt maken, gebruikt u de functie **Aangepaste apparaatprofielen** in Intune. Dit artikel bevat ook enkele voorbeelden over het maken van op EAP gebaseerde Wi-Fi-profielen.

> [!IMPORTANT]
>- Door gebruik van een vooraf gedeelde sleutel met Windows 10 wordt een herstelfout weergegeven in Intune. Als dit gebeurt, wordt het Wi-Fi-profiel correct toegewezen aan het apparaat en werkt het profiel zoals verwacht.
>- Als u een Wi-Fi-profiel met een vooraf gedeelde sleutel exporteert, moet u ervoor zorgen dat het bestand is beveiligd. De sleutel bestaat uit tekst zonder opmaak. Het is dus uw verantwoordelijkheid om de sleutel te beveiligen.

## <a name="before-you-begin"></a>Voordat u begint

- Het kan eenvoudiger zijn om de code te kopiëren vanaf een computer die verbinding heeft met dat netwerk, zoals verderop in dit artikel wordt beschreven.
- U kunt meerdere netwerken en sleutels toevoegen door meer OMA-URI-instellingen toe te voegen.
- Voor iOS gebruikt u Apple Configurator op een Mac-computer om het profiel te configureren.
- Voor PSK is een tekenreeks van 64 hexadecimale cijfers vereist of een wachtwoordzin van 8 tot 63 afdrukbare ASCII-tekens. Sommige tekens, zoals sterretje (*), worden niet ondersteund.

## <a name="create-a-custom-profile"></a>Een aangepast profiel maken
U kunt voor Android-, Windows- en op EAP gebaseerde Wi-Fi-profielen een aangepast profiel maken met een vooraf gedeelde sleutel. Zie [Aangepaste apparaatinstellingen maken](custom-settings-configure.md) als u het profiel wilt maken via Azure Portal. Tijdens het maken van het apparaatprofiel kiest u **Aangepast** als apparaatplatform. Selecteer het Wi-Fi-profiel niet. Als u Aangepast kiest, doet u het volgende: 

1. Geef een naam en beschrijving op voor het profiel.
2. Voeg een nieuwe OMA-URI-instelling met de volgende eigenschappen toe: 

   a. Voer een naam in voor deze Wi-Fi-netwerkinstelling.

   b. (optioneel) Voer een beschrijving in voor de OMA-URI-instelling of laat dit veld leeg.

   c. Stel het **gegevenstype** in op **Tekenreeks**.

   d. **OMA-URI**:

   - **Voor Android**: ./Vendor/MSFT/WiFi/Profile/SSID/Settings
   - **Voor Windows**: ./Vendor/MSFT/WiFi/Profile/SSID/WlanXml

     > [!NOTE]
     > Zorg ervoor dat deze string met een punt begint.

     SSID is de SSID waarvoor u het beleid wilt maken. Als de Wi-Fi bijvoorbeeld de naam `Hotspot-1` heeft, voert u `./Vendor/MSFT/WiFi/Profile/Hotspot-1/Settings` in.

   e. **Waardeveld**: hier plakt u de XML-code. Zie de voorbeelden in dit artikel. Werk elke waarde bij zodat de waarden overeenkomen met uw netwerkinstellingen. In het gedeelte met opmerkingen over de code staat een aantal tips.
3. Selecteer **OK**, sla op en wijs het beleid toe.

    > [!NOTE]
    > Dit beleid kan alleen worden toegewezen aan gebruikersgroepen.

De volgende keer dat met een apparaat wordt ingecheckt, wordt het beleid toegepast en wordt er een Wi-Fi-profiel gemaakt op het apparaat. Het apparaat kan dan automatisch verbinding maken met het netwerk.

## <a name="android-or-windows-wi-fi-profile-example"></a>Voorbeeld van een Wi-Fi-profiel voor Android of Windows

Het volgende voorbeeld bevat de XML-code voor een Wi-Fi-profiel voor Android of Windows. Het voorbeeld is bedoeld om de juiste indeling te laten zien en meer details te bieden. Dit is slechts een voorbeeld en moet niet worden beschouwd als een aanbevolen configuratie voor uw omgeving.

### <a name="important-considerations"></a>Belangrijke overwegingen

- `<protected>false</protected>` moet worden ingesteld op **onwaar**. Als dit wordt ingesteld op **waar**, kan dit ertoe leiden dat het apparaat een versleuteld wachtwoord verwacht en dit vervolgens probeert te ontsleutelen, waardoor het verbinden kan mislukken.

- `<hex>53534944</hex>` moet worden ingesteld op de hexadecimale waarde `<name><SSID of wifi profile></name>`. Windows 10-apparaten kunnen ten onrechte de fout `x87D1FDE8 Remediation failed` retourneren terwijl het apparaat het profiel nog wel bevat.

- XML heeft speciale tekens, zoals de `&` (en-teken). Het gebruik van speciale tekens kan ertoe leiden dat XML niet werkt zoals verwacht. 

### <a name="example"></a>Voorbeeld

``` xml
<!--
<hex>53534944</hex> = The hexadecimal value of <name><SSID of wifi profile></name>
<Name of wifi profile> = Name of profile shown to users. It could be <name>Your Company's Network</name>.
<SSID of wifi profile> = Plain text of SSID. Does not need to be escaped. It could be <name>Your Company's Network</name>.
<nonBroadcast><true/false></nonBroadcast>
<Type of authentication> = Type of authentication used by the network, such as WPA2PSK.
<Type of encryption> = Type of encryption used by the network, such as AES.
<protected>false</protected> do not change this value, as true could cause device to expect an encrypted password and then try to decrypt it, which may result in a failed connection.
<password> = Plain text of the password to connect to the network
-->

<WLANProfile
xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
  <name><Name of wifi profile></name>
  <SSIDConfig>
    <SSID>
      <hex>53534944</hex>
 <name><SSID of wifi profile></name>
    </SSID>
    <nonBroadcast>false</nonBroadcast>
  </SSIDConfig>
  <connectionType>ESS</connectionType>
  <connectionMode>auto</connectionMode>
  <autoSwitch>false</autoSwitch>
  <MSM>
    <security>
      <authEncryption>
        <authentication><Type of authentication></authentication>
        <encryption><Type of encryption></encryption>
        <useOneX>false</useOneX>
      </authEncryption>
      <sharedKey>
        <keyType>passPhrase</keyType>
        <protected>false</protected>
        <keyMaterial>password</keyMaterial>
      </sharedKey>
      <keyIndex>0</keyIndex>
    </security>
  </MSM>
</WLANProfile>
```

## <a name="eap-based-wi-fi-profile-example"></a>Voorbeeld van een op EAP gebaseerd profiel
Het volgende voorbeeld bevat de XML-code voor een Wi-Fi-profiel op basis van EAP: Het voorbeeld is bedoeld om de juiste indeling te laten zien en meer details te bieden. Dit is slechts een voorbeeld en moet niet worden beschouwd als een aanbevolen configuratie voor uw omgeving.


```xml
    <WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
      <name>testcert</name>
      <SSIDConfig>
        <SSID>
          <hex>7465737463657274</hex>
          <name>testcert</name>
        </SSID>
        <nonBroadcast>true</nonBroadcast>
      </SSIDConfig>
      <connectionType>ESS</connectionType>
      <connectionMode>auto</connectionMode>
      <autoSwitch>false</autoSwitch>
      <MSM>
        <security>
          <authEncryption>
            <authentication>WPA2</authentication>
            <encryption>AES</encryption>
            <useOneX>true</useOneX>
            <FIPSMode     xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode>
          </authEncryption>
          <PMKCacheMode>disabled</PMKCacheMode>
          <OneX xmlns="http://www.microsoft.com/networking/OneX/v1">
            <cacheUserData>false</cacheUserData>
            <authMode>user</authMode>
            <EAPConfig>
              <EapHostConfig     xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
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
                      <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</PerformServerValidation>
                      <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName>
                      <TLSExtensions xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
                        <FilteringInfo xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV3">
                          <AllPurposeEnabled>true</AllPurposeEnabled>
                          <CAHashList Enabled="true">
                            <IssuerHash>75 f5 06 9c a4 12 0e 9b db bc a1 d9 9d d0 f0 75 fa 3b b8 78 </IssuerHash>
                          </CAHashList>
                          <EKUMapping>
                            <EKUMap>
                              <EKUName>Client Authentication</EKUName>
                              <EKUOID>1.3.6.1.5.5.7.3.2</EKUOID>
                            </EKUMap>
                          </EKUMapping>
                          <ClientAuthEKUList Enabled="true"/>
                          <AnyPurposeEKUList Enabled="false">
                            <EKUMapInList>
                              <EKUName>Client Authentication</EKUName>
                            </EKUMapInList>
                          </AnyPurposeEKUList>
                        </FilteringInfo>
                      </TLSExtensions>
                    </EapType>
                  </Eap>
                </Config>
              </EapHostConfig>
            </EAPConfig>
          </OneX>
        </security>
      </MSM>
    </WLANProfile>
```

## <a name="create-the-xml-file-from-an-existing-wi-fi-connection"></a>Het XML-bestand maken op basis van een bestaande Wi-Fi-verbinding

U kunt ook een XML-bestand maken op basis van een bestaande Wi-Fi-verbinding. Voer de volgende stappen uit op een Windows-computer:

1. Maak een lokale map voor de geëxporteerde Wi-Fi-profielen, zoals C:\WiFi.
2. Open een opdrachtprompt als beheerder (klik met de rechtermuisknop op `cmd` > **Als administrator uitvoeren**)
3. Voer `netsh wlan show profiles` uit. De namen van alle profielen worden vermeld.
4. Voer `netsh wlan export profile name="YourProfileName" folder=c:\Wifi` uit. Met deze opdracht maakt u een bestand met de naam `Wi-Fi-YourProfileName.xml` in C:\Wifi.

    - Als u een Wi-Fi-profiel met een vooraf gedeelde sleutel exporteert, moet u `key=clear` aan de opdracht toevoegen:
  
      `netsh wlan export profile name="YourProfileName" key=clear folder=c:\Wifi`

      Met `key=clear` wordt de sleutel geëxporteerd als tekst zonder opmaak, wat nodig is om het profiel te kunnen gebruiken.

Nadat u het XML-bestand hebt gemaakt, kopieert en plakt u de XML-syntaxis in OMA-URI-instellingen > **Gegevenstype**. De stappen worden vermeld in [Een aangepast profiel maken](#create-a-custom-profile) (in dit artikel).

> [!TIP]
> `\ProgramData\Microsoft\Wlansvc\Profiles\Interfaces\{guid}` bevat ook alle profielen in XML-indeling.

## <a name="best-practices"></a>Aanbevolen procedures

- Voordat u een Wi-Fi-profiel met PSK implementeert, moet u controleren of het apparaat rechtstreeks verbinding met het eindpunt kan maken.

- Wanneer u sleutels (wachtwoorden of wachtwoordzinnen) roteert, kunt u downtime verwachten en moet u hiermee rekening houden in uw implementaties. U kunt nieuwe Wi-Fi-profielen pushen buiten kantooruren. Waarschuw gebruikers dat dit een negatieve gevolgen kan hebben voor de connectiviteit.

- Zorg ervoor dat het apparaat van de eindgebruiker over een alternatieve internetverbinding beschikt, zodat de overgang soepel kan verlopen. De gebruiker moet bijvoorbeeld weer kunnen overschakelen naar gast-Wi-Fi (of een ander Wi-Fi-netwerk) of moet over een mobiele verbinding beschikken om met Intune te communiceren. Met de extra verbinding kan de gebruiker beleidsupdates ontvangen wanneer het zakelijke Wi-Fi-profiel op het apparaat wordt bijgewerkt.
