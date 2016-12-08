---
title: Wi-Fi met een vooraf gedeelde sleutel (PSK) | Microsoft Intune
description: Aangepaste configuratie van Intune gebruiken om een Wi-Fi-profiel te maken met een vooraf gedeelde sleutel.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e977c7c7-e204-47a6-b851-7ad7673ceaab
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: ad5bb09eb18463f541ca0cbb60ff1f27bdc3251e



---
# <a name="use-a-custom-policy-to-create-a-wi-fi-profile-with-a-pre-shared-key"></a>Een aangepast beleid gebruiken om een Wi-Fi-profiel te maken met een vooraf gedeelde sleutel
Hieronder wordt beschreven hoe u de **aangepaste configuratie** van Intune gebruikt om een Wi-Fi-profiel te maken met een vooraf gedeelde sleutel. In dit onderwerp staat ook een voorbeeld van hoe u een EAP Wi-Fi-profiel maakt.

> [!NOTE]
-   Wellicht is het eenvoudiger om de code te kopiëren van een computer die verbinding heeft met dat netwerk, zoals hieronder wordt beschreven.
- Voor Android hebt u ook de mogelijkheid om deze [Android PSK Generator](http://johnathonb.com/2015/05/intune-android-pre-shared-key-generator/) te gebruiken, die wordt aangeboden door Johnathon Biersack.
-   U kunt meerdere netwerken en sleutels toevoegen door meer OMA-URI-instellingen toe te voegen.
-  Voor iOS gebruikt u Apple Configurator op een Mac-computer om het profiel te configureren. U kunt ook deze [iOS PSK Mobile Config Generator](http://johnathonb.com/2015/05/intune-ios-psk-mobile-config-generator/) gebruiken, die wordt aangeboden door Johnathon Biersack.


1.  Als u een Wi-Fi-profiel met een vooraf gedeelde sleutel wilt maken voor Android of Windows, of een Wi-Fi-profiel op basis van EAP, kiest u tijdens het maken van een beleid **Aangepaste configuratie** voor dat apparaatplatform en maakt u geen Wi-Fi profiel.

2.  Geef een naam en beschrijving op.
3.  Een nieuwe OMA-URI-instelling toevoegen:

   a.   Voer een naam in voor deze Wi-Fi-netwerkinstelling.

   b.   Voer een beschrijving in voor de OMA-URI-instelling of laat dit veld leeg.

   c.   **Gegevenstype**: ingesteld op String(XML)

   d.   **OMA-URI**:

    - **Voor Android**: ./Vendor/MSFT/WiFi/Profile/<SSID>/Settings
    - **Voor Windows**: ./Vendor/MSFT/WiFi/Profile/MyNetwork/WlanXml

    > [!NOTE]
Zorg ervoor dat deze string met een punt begint.

    SSID is de SSID waarvoor u het beleid wilt maken. bijvoorbeeld `./Vendor/MSFT/WiFi/Profile/Hotspot-1/Settings`

  e. **Waardeveld**: hier plakt u de XML-code. Hier volgt een voorbeeld. Elke waarde moet worden aangepast aan de instellingen van uw netwerk. Zie het gedeelte met opmerkingen over de code voor een aantal tips.
4. Kies **OK**, opslaan en implementeer het beleid.

    > [!NOTE]
    > Dit beleid kan alleen worden geïmplementeerd voor gebruikersgroepen.

De volgende keer dat met een apparaat wordt ingecheckt, wordt het beleid toegepast en wordt er een Wi-Fi-profiel gemaakt op het apparaat. Het apparaat kan automatisch verbinding maken met het netwerk.
## <a name="android-or-windows-wi-fi-profile"></a>Wi-Fi-profiel voor Android of Windows

Hier volgt een voorbeeld van de XML-code voor een Wi-Fi-profiel voor Android of Windows:

> [!IMPORTANT]
> 
> `<protected>false</protected>` moet worden ingesteld op **onwaar**. Als dit wordt ingesteld op **waar**, kan dit ertoe leiden dat het apparaat een versleuteld wachtwoord verwacht en dit vervolgens probeert te ontsleutelen, waardoor de verbinding kan mislukken.
> 
>  `<hex>53534944</hex>` moet worden ingesteld op de hexadecimale waarde `<name><SSID of wifi profile></name>`.
>  Windows 10-apparaten kunnen ten onrechte de fout *0x87D1FDE8 Doorvoeren is mislukt* retourneren, maar worden wel ingericht met het profiel.

    <!--
    <Name of wifi profile> = Name of profile
    <SSID of wifi profile> = Plain text of SSID. Does not need to be escaped, could be <name>Your Company's Network</name>
    <nonBroadcast><true/false></nonBroadcast>
    <Type of authentication> = Type of authentication used by the network, such as WPA2PSK.
    <Type of encryption> = Type of encryption used by the network
    <protected>false</protected> do not change this value, as true could cause device to expect an encrypted password and then try to decrypt it, which may result in a failed connection.
    <password> = Password to connect to the network
    <hex>53534944</hex> should be set to the hexadecimal value of <name><SSID of wifi profile></name>
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
            <keyType>networkKey</keyType>
            <protected>false</protected>
            <keyMaterial>MyPassword</keyMaterial>
          </sharedKey>
          <keyIndex>0</keyIndex>
        </security>
      </MSM>
    </WLANProfile>

## <a name="eap-based-wi-fi-profile"></a>Wi-Fi-profiel op basis van EAP
Hier volgt een voorbeeld van de XML-code voor een Wi-Fi-profiel op basis van EAP.

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

## <a name="create-the-xml-file-from-an-existing-wi-fi-connection"></a>Het XML-bestand maken op basis van een bestaande Wi-Fi-verbinding
U kunt ook een XML-bestand maken op basis van een bestaande Wi-Fi-verbinding:
1. Op een computer die (onlangs) is verbonden met het draadloze netwerk, opent u de volgende map: C:\ProgramData\Microsoft\Wlansvc\Profiles\Interfaces\{guid}.

    Het is raadzaam een computer te gebruiken die niet met veel draadloze netwerken verbinding heeft gemaakt, omdat u alle profielen moet doorzoeken om het juiste te vinden.
3.     Doorzoek de XML-bestanden om het bestand met de juiste naam te vinden.
4.     Wanneer u het juiste XML-bestand hebt gevonden, kopieert u de XML-code en plakt u deze in het veld Gegevens van de pagina OMA-URI-instellingen.

## <a name="deploy-the-policy"></a>Het beleid implementeren

1.  Selecteer in de werkruimte **Beleid** het beleid dat u wilt implementeren en kies vervolgens **Implementatie beheren**.

2.  In het dialoogvenster **Implementatie beheren** :

    -   **Het beleid implementeren**: selecteer een of meer groepen waarvoor u het beleid wilt implementeren en kies vervolgens **Toevoegen**&gt; **OK**.

    -   **Het dialoogvenster sluiten zonder het beleid te implementeren**: kies **Annuleren**.

Wanneer u een geïmplementeerd beleid selecteert, kunt u meer informatie over de implementatie weergeven onder aan de lijst met beleidsregels.

### <a name="see-also"></a>Zie tevens
[Wi-Fi-verbindingen in Microsoft Intune](wi-fi-connections-in-microsoft-intune.md)



<!--HONumber=Nov16_HO1-->


