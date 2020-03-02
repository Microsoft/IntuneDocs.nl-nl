---
title: Problemen met de implementatie van SCEP-certificaatprofielen op apparaten oplossen met Microsoft Intune | Microsoft Docs
description: Problemen met het verzenden van een SCEP-certificaatprofiel naar een apparaat oplossen met Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/30/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 26eb6a5cb8e7aba01ce32ab8bec8ad917604a55c
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514775"
---
# <a name="troubleshoot-deployment-of-a-scep-certificate-profile-to-devices-in-microsoft-intune"></a>Problemen met de implementatie van een SCEP-certificaatprofiel oplossen in Microsoft Intune

Gebruik de volgende informatie bij het oplossen van problemen met de implementatie van SCEP-certificaatprofielen (Simple Certificate Enrollment Protocol) met Intune.

In dit artikel wordt verwezen naar stap 1 van het [Overzicht van de SCEP-communicatiestroom](troubleshoot-scep-certificate-profiles.md).


## <a name="android"></a>Android

SCEP-certificaatprofielen voor Android worden op het apparaat beschikbaar als een SyncML en worden vastgelegd in het [OMADM-logboek](troubleshoot-scep-certificate-profiles.md#logs-for-android-devices).

### <a name="validate-that-the-android-device-was-sent-the-policy"></a>Controleren of het beleid naar het Android-apparaat is verzonden

Als u wilt controleren of een profiel naar het verwachte apparaat is verzonden, gaat u in het [beheercentrum van Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) naar **Probleemoplossing en ondersteuning** > **Probleem oplossen**.  Stel in het venster *Probleem oplossen* **Toewijzingen** in op **Configuratieprofielen** en controleer vervolgens de volgende configuraties:

1. Geef een gebruiker op die het SCEP-certificaatprofiel moet ontvangen.

2. Bekijk het lidmaatschap van de gebruikersgroep om te controleren of dit zich in de beveiligingsgroep bevindt die u hebt gebruikt met het SCEP-certificaatprofiel.

3. Controleer wanneer het apparaat voor het laatst heeft ingecheckt bij Intune.

![Het beleid valideren](../protect/media/troubleshoot-scep-certificate-profile-deployment/validate-policy-android.png)

### <a name="validate-the-policy-reached-the-android-device"></a>Controleren of het beleid op het Android-apparaat is aangekomen

Raadpleeg het [OMADM-logboek van het apparaat](troubleshoot-scep-certificate-profiles.md#logs-for-android-devices). Zoek naar vermeldingen die vergelijkbaar zijn met de volgende, die worden vastgelegd wanneer het apparaat het profiel uit Intune krijgt:

```
Time    VERB    Event     com.microsoft.omadm.syncml.SyncmlSession     9595        9    <?xml version="1.0" encoding="utf-8"?><SyncML xmlns="SYNCML:SYNCML1.2"><SyncHdr><VerDTD>1.2</VerDTD><VerProto>DM/1.2</VerProto><SessionID>1</SessionID><MsgID>6</MsgID><Target><LocURI>urn:uuid:UUID</LocURI></Target><Source><LocURI>https://a.manage.microsoft.com/devicegatewayproxy/AndroidHandler.ashx</LocURI></Source><Meta><MaxMsgSize xmlns="syncml:metinf">524288</MaxMsgSize></Meta></SyncHdr><SyncBody><Status><CmdID>1</CmdID><MsgRef>6</MsgRef><CmdRef>0</CmdRef><Cmd>SyncHdr</Cmd><Data>200</Data></Status><Replace><CmdID>2</CmdID><Item><Target><LocURI>./Vendor/MSFT/Scheduler/IntervalDurationSeconds</LocURI></Target><Meta><Format xmlns="syncml:metinf">int</Format><Type xmlns="syncml:metinf">text/plain</Type></Meta><Data>28800</Data></Item></Replace><Replace><CmdID>3</CmdID><Item><Target><LocURI>./Vendor/MSFT/EnterpriseAppManagement/EnterpriseIDs</LocURI></Target><Data>contoso.onmicrosoft.com</Data></Item></Replace><Exec><CmdID>4</CmdID><Item><Target><LocURI>./Vendor/MSFT/EnterpriseAppManagement/EnterpriseApps/ClearNotifications</LocURI></Target></Item></Exec><Add><CmdID>5</CmdID><Item><Target><LocURI>./Vendor/MSFT/CertificateStore/Root/{GUID}/EncodedCertificate</LocURI></Target><Data>Data</Data></Item></Add><Add><CmdID>6</CmdID><Item><Target><LocURI>./Vendor/MSFT/CertificateStore/Enroll/ModelName=AC_51…%2FLogicalName_39907…%3BHash=-1518303401/Install</LocURI></Target><Meta><Format xmlns="syncml:metinf">xml</Format><Type xmlns="syncml:metinf">text/plain</Type></Meta><Data>&lt;CertificateRequest&gt;&lt;ConfigurationParametersDocument&gt;&amp;lt;ConfigurationParameters xmlns="http://schemas.microsoft.com/SystemCenterConfigurationManager/2012/03/07/CertificateEnrollment/ConfigurationParameters"&amp;gt;&amp;lt;ExpirationThreshold&amp;gt;20&amp;lt;/ExpirationThreshold&amp;gt;&amp;lt;RetryCount&amp;gt;3&amp;lt;/RetryCount&amp;gt;&amp;lt;RetryDelay&amp;gt;1&amp;lt;/RetryDelay&amp;gt;&amp;lt;TemplateName /&amp;gt;&amp;lt;SubjectNameFormat&amp;gt;{ID}&amp;lt;/SubjectNameFormat&amp;gt;&amp;lt;SubjectAlternativeNameFormat&amp;gt;{ID}&amp;lt;/SubjectAlternativeNameFormat&amp;gt;&amp;lt;KeyStorageProviderSetting&amp;gt;0&amp;lt;/KeyStorageProviderSetting&amp;gt;&amp;lt;KeyUsage&amp;gt;32&amp;lt;/KeyUsage&amp;gt;&amp;lt;KeyLength&amp;gt;2048&amp;lt;/KeyLength&amp;gt;&amp;lt;HashAlgorithms&amp;gt;&amp;lt;HashAlgorithm&amp;gt;SHA-1&amp;lt;/HashAlgorithm&amp;gt;&amp;lt;HashAlgorithm&amp;gt;SHA-2&amp;lt;/HashAlgorithm&amp;gt;&amp;lt;/HashAlgorithms&amp;gt;&amp;lt;NDESUrls&amp;gt;&amp;lt;NDESUrl&amp;gt;https://breezeappproxy-contoso.msappproxy.net/certsrv/mscep/mscep.dll&amp;lt;/NDESUrl&amp;gt;&amp;lt;/NDESUrls&amp;gt;&amp;lt;CAThumbprint&amp;gt;{GUID}&amp;lt;/CAThumbprint&amp;gt;&amp;lt;ValidityPeriod&amp;gt;2&amp;lt;/ValidityPeriod&amp;gt;&amp;lt;ValidityPeriodUnit&amp;gt;Years&amp;lt;/ValidityPeriodUnit&amp;gt;&amp;lt;EKUMapping&amp;gt;&amp;lt;EKUMap&amp;gt;&amp;lt;EKUName&amp;gt;Client Authentication&amp;lt;/EKUName&amp;gt;&amp;lt;EKUOID&amp;gt;1.3.6.1.5.5.7.3.2&amp;lt;/EKUOID&amp;gt;&amp;lt;/EKUMap&amp;gt;&amp;lt;/EKUMapping&amp;gt;&amp;lt;/ConfigurationParameters&amp;gt;&lt;/ConfigurationParametersDocument&gt;&lt;RequestParameters&gt;&lt;CertificateRequestToken&gt;PENlcnRFbn... Hash: 1,010,143,298&lt;/CertificateRequestToken&gt;&lt;SubjectName&gt;CN=name&lt;/SubjectName&gt;&lt;Issuers&gt;CN=FourthCoffee CA; DC=fourthcoffee; DC=local&lt;/Issuers&gt;&lt;SubjectAlternativeName&gt;&lt;SANs&gt;&lt;SAN NameFormat="ID" AltNameType="2" OID="{OID}"&gt;&lt;/SAN&gt;&lt;SAN NameFormat="ID" AltNameType="11" OID="{OID}"&gt;john@contoso.onmicrosoft.com&lt;/SAN&gt;&lt;/SANs&gt;&lt;/SubjectAlternativeName&gt;&lt;NDESUrl&gt;https://breezeappproxy-contoso.msappproxy.net/certsrv/mscep/mscep.dll&lt;/NDESUrl&gt;&lt;/RequestParameters&gt;&lt;/CertificateRequest&gt;</Data></Item></Add><Get><CmdID>7</CmdID><Item><Target><LocURI>./Vendor/MSFT/CertificateStore/SCEP</LocURI></Target></Item></Get><Add><CmdID>8</CmdID><Item><Target><LocURI>./Vendor/MSFT/GCM</LocURI></Target><Data>Data</Data></Item></Add><Replace><CmdID>9</CmdID><Item><Target><LocURI>./Vendor/MSFT/GCM</LocURI></Target><Data>Data</Data></Item></Replace><Get><CmdID>10</CmdID><Item><Target><LocURI>./Vendor/MSFT/NodeCache/SCConfigMgr</LocURI></Target></Item></Get><Get><CmdID>11</CmdID><Item><Target><LocURI>./Vendor/MSFT/NodeCache/SCConfigMgr/CacheVersion</LocURI></Target></Item></Get><Get><CmdID>12</CmdID><Item><Target><LocURI>./Vendor/MSFT/NodeCache/SCConfigMgr/ChangedNodes</LocURI></Target></Item></Get><Get><CmdID>13</CmdID><Item><Target><LocURI>./DevDetail/Ext/Microsoft/LocalTime</LocURI></Target></Item></Get><Get><CmdID>14</CmdID><Item><Target><LocURI>./Vendor/MSFT/DeviceLock/DevicePolicyManager/IsActivePasswordSufficient</LocURI></Target></Item></Get><Get><CmdID>15</CmdID><Item><Target><LocURI>./Vendor/MSFT/WorkProfileLock/DevicePolicyManager/IsActivePasswordSufficient</LocURI></Target></Item></Get><Final /></SyncBody></SyncML>
```

Voorbeelden van belangrijke vermeldingen:

- `ModelName=AC_51bad41f-3854-4eb5-a2f2-0f7a94034ee8%2FLogicalName_39907e78_e61b_4730_b9fa_d44a53e4111c%3BHash=-1518303401`
- `NDESUrls&amp;gt;&amp;lt;NDESUrl&amp;gt;https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll&amp;lt;/NDESUrl&amp;gt;&amp;lt;/NDESUrls`

## <a name="iosipados"></a>iOS/iPadOS

### <a name="validate-that-the-iosipados-device-was-sent-the-policy"></a>Controleren of het beleid naar het iOS/iPadOS-apparaat is verzonden

Als u wilt controleren of een profiel naar het verwachte apparaat is verzonden, gaat u in het [beheercentrum van Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) naar **Probleemoplossing en ondersteuning** > **Probleem oplossen**.  Stel in het venster *Probleem oplossen* **Toewijzingen** in op **Configuratieprofielen** en controleer vervolgens de volgende configuraties:

1. Geef een gebruiker op die het SCEP-certificaatprofiel moet ontvangen.

2. Bekijk het lidmaatschap van de gebruikersgroep om te controleren of dit zich in de beveiligingsgroep bevindt die u hebt gebruikt met het SCEP-certificaatprofiel.

3. Controleer wanneer het apparaat voor het laatst heeft ingecheckt bij Intune.

![Het beleid valideren](../protect/media/troubleshoot-scep-certificate-profile-deployment/validate-policy-ios.png)

### <a name="validate-the-policy-reached-the-ios-or-ipados-device"></a>Controleren of het beleid op het iOS- of iPadOS-apparaat is aangekomen

Raadpleeg het [foutopsporingslogboek van het apparaat](troubleshoot-scep-certificate-profiles.md#logs-for-ios-and-ipados-devices). Zoek naar vermeldingen die vergelijkbaar zijn met de volgende, die worden vastgelegd wanneer het apparaat het profiel uit Intune krijgt:

```
debug    18:30:54.638009 -0500    profiled    Adding dependent ModelName=AC_51bad41f.../LogicalName_1892fe4c...;Hash=-912418295 to parent 636572740000000000000012 in domain PayloadDependencyDomainCertificate to system\
```

Voorbeelden van belangrijke vermeldingen:

- `ModelName=AC_51bad41f.../LogicalName_1892fe4c...;Hash=-912418295`
- `PayloadDependencyDomainCertificate`

## <a name="windows"></a>Windows

### <a name="validate-that-the-windows-device-was-sent-the-policy"></a>Controleren of het beleid naar het Windows-apparaat is verzonden

Als u wilt controleren of het profiel is verzonden naar het verwachte apparaat, gaat u in het [beheercentrum van Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)[beheercentrum van Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) naar **Probleemoplossing en ondersteuning** > **Probleem oplossen**.  Stel in het venster *Probleem oplossen* **Toewijzingen** in op **Configuratieprofielen** en controleer vervolgens de volgende configuraties:

1. Geef een gebruiker op die het SCEP-certificaatprofiel moet ontvangen.

2. Bekijk het lidmaatschap van de gebruikersgroep om te controleren of dit zich in de beveiligingsgroep bevindt die u hebt gebruikt met het SCEP-certificaatprofiel.

3. Controleer wanneer het apparaat voor het laatst heeft ingecheckt bij Intune.

![Het beleid valideren](../protect/media/troubleshoot-scep-certificate-profile-deployment/validate-policy-windows.png)

### <a name="validate-the-policy-reached-the-windows-device"></a>Controleren of het beleid op het Windows-apparaat is aangekomen

De ontvangst van het beleid voor het profiel wordt vastgelegd in het logboek *DeviceManagement-Enterprise-Diagnostics-Provider* > **Beheerder** met gebeurtenis-ID **306**. 

U opent het logboek als volgt:

1. Voer op het apparaat **eventvwr.msc** uit om Logboeken van Windows te openen.

2. Vouw uit: **Logboeken Toepassingen en Services** > **Microsoft** > **Windows** > **DeviceManagement-Enterprise-Diagnostic-Provider** > **Beheerder**.

3. Zoek naar gebeurtenis **306**, die op het volgende voorbeeld lijkt:

   ```
   Event ID:      306
   Task Category: None
   Level:         Information
   User:          SYSTEM
   Computer:      <Computer Name>
   Description:
   SCEP: CspExecute for UniqueId : (ModelName_<ModelName>_LogicalName_<LogicalName>_Hash_<Hash>) InstallUserSid : (<UserSid>) InstallLocation : (user) NodePath : (clientinstall)  KeyProtection: (0x2) Result : (Unknown Win32 Error code: 0x2ab0003).
   ```

   De foutcode **0x2ab0003** wordt omgezet in **DM_S_ACCEPTED_FOR_PROCESSING**.

   Een foutcode kan een indicatie geven van het onderliggende probleem.

## <a name="next-steps"></a>Volgende stappen

Als het profiel op het apparaat is aangekomen, bestaat de volgende stap uit het controleren van de [communicatie van het apparaat met de NDES-server](troubleshoot-scep-certificate-device-to-ndes.md).
