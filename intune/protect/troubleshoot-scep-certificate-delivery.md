---
title: Problemen oplossen met de levering van certificaten aan apparaten wanneer u SCEP gebruikt met Microsoft Intune | Microsoft Docs
description: Los een probleem op met de levering van een certificaat aan een apparaat vanuit de CA, wanneer u SCEP-certificaatprofielen met Intune gebruikt om certificaten te implementeren.
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
ms.openlocfilehash: 77be59d126dc7e73bee468ca938938c6bb1b2e1a
ms.sourcegitcommit: c46b0c2d4507be6a2786a4ea06009b2d5aafef85
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/01/2020
ms.locfileid: "76915873"
---
# <a name="troubleshoot-the-delivery-of-certificates-provisioned-by-scep-to-devices-in-microsoft-intune"></a>Problemen oplossen met de levering van certificaten die zijn ingericht met SCEP, aan apparaten in Microsoft Intune

Gebruik de informatie in dit artikel om u te helpen de levering van certificaten aan apparaten te onderzoeken wanneer u SCEP (Simple Certificate Enrollment Protocol) gebruikt om certificaten in te richten in Intune. Nadat de NDES-server (registratieservice voor netwerkapparaten) het aangevraagde certificaat voor een apparaat heeft ontvangen van de CA (certificeringsinstantie), wordt dit certificaat weer doorgegeven aan het apparaat.

Dit artikel is van toepassing op stap 5 van de [SCEP-communicatiewerkstroom](troubleshoot-scep-certificate-profiles.md): de levering van het certificaat aan het apparaat waarmee de certificaataanvraag is verzonden.

## <a name="review-the-certification-authority"></a>De certificeringsinstantie controleren

Wanneer de certificeringsinstantie het certificaat heeft verleend, ziet u een vermelding die lijkt op het volgende voorbeeld in de CA:

![Voorbeeld van verleende certificaten](../protect/media/troubleshoot-scep-certificate-delivery/certificate-authority.png)

## <a name="review-the-device"></a>Het apparaat controleren

### <a name="android"></a>Android

Voor apparaten die zijn ingeschreven door een apparaatbeheerder, ziet u een melding die lijkt op de volgende afbeelding, waarin u wordt gevraagd om het certificaat te installeren:

![Android-melding](../protect/media/troubleshoot-scep-certificate-delivery/android-notification.png)

Voor Android Enterprise of Samsung Knox verloopt de installatie van certificaten automatisch en op de achtergrond.

Als u een geïnstalleerd certificaat in Android wilt weergeven, gebruikt u een app van derden voor het weergeven van certificaten.

U kunt ook het [OMADM-logboek voor apparaten](troubleshoot-scep-certificate-profiles.md#logs-for-android-devices) raadplegen. Zoek naar vermeldingen die vergelijkbaar zijn met de volgende vermeldingen, die worden vastgelegd bij de installatie van certificaten:

**Basiscertificaat**:

```
2018-02-27T04:50:52.1890000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeRootCertInstallStateMachine     9595        9    Root cert '17…' state changed from CERT_INSTALL_REQUESTED to CERT_INSTALL_REQUESTED
2018-02-27T04:53:31.1300000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeRootCertInstallStateMachine     9595        0    Root cert '17…' state changed from CERT_INSTALL_REQUESTED to CERT_INSTALLING
2018-02-27T04:53:32.0390000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeRootCertInstallStateMachine     9595       14    Root cert '17…' state changed from CERT_INSTALLING to CERT_INSTALL_SUCCESS
```

**Certificaat ingericht via SCEP**

```
2018-02-27T05:16:08.2500000    VERB    Event     com.microsoft.omadm.platforms.android.certmgr.CertificateEnrollmentManager    18327       10    There are 1 requests
2018-02-27T05:16:08.2500000    VERB    Event     com.microsoft.omadm.platforms.android.certmgr.CertificateEnrollmentManager    18327       10    Trying to enroll certificate request: ModelName=AC_51…%2FLogicalName_39907…;Hash=1677525787
2018-02-27T05:16:20.6150000    VERB    Event     org.jscep.transport.UrlConnectionGetTransport    18327       10    Sending GetCACert(ca) to https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACert&message=ca
2018-02-27T05:16:20.6530000    VERB    Event     org.jscep.transport.UrlConnectionGetTransport    18327       10    Received '200 OK' when sending GetCACert(ca) to https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACert&message=ca
2018-02-27T05:16:21.7460000    VERB    Event     org.jscep.transport.UrlConnectionGetTransport    18327       10    Sending GetCACaps(ca) to https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=ca
2018-02-27T05:16:21.7890000    VERB    Event     org.jscep.transport.UrlConnectionGetTransport    18327       10    Received '200 OK' when sending GetCACaps(ca) to https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=ca
2018-02-27T05:16:28.0340000    VERB    Event     org.jscep.transaction.EnrollmentTransaction    18327       10    Response: org.jscep.message.CertRep@3150777b[failInfo=<null>,pkiStatus=SUCCESS,recipientNonce=Nonce [GUID],messageData=org.spongycastle.cms.CMSSignedData@27cc8998,messageType=CERT_REP,senderNonce=Nonce [GUID],transId=TRANSID]
2018-02-27T05:16:28.2440000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeScepCertInstallStateMachine    18327       10    SCEP cert 'ModelName=AC_51…%2FLogicalName_39907…;Hash=1677525787' state changed from CERT_ENROLLED to CERT_INSTALL_REQUESTED
2018-02-27T05:18:44.9820000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeScepCertInstallStateMachine    18327        0    SCEP cert 'ModelName=AC_51…%2FLogicalName_39907…;Hash=1677525787' state changed from CERT_INSTALL_REQUESTED to CERT_INSTALLING
2018-02-27T05:18:45.3460000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeScepCertInstallStateMachine    18327       14    SCEP cert 'ModelName=AC_51…%2FLogicalName_39907…;Hash=1677525787' state changed from CERT_INSTALLING to CERT_ACCESS_REQUESTED
2018-02-27T05:20:15.3520000    INFO    Event     com.microsoft.omadm.platforms.android.certmgr.state.NativeScepCertInstallStateMachine    18327       21    SCEP cert 'ModelName=AC_51…%2FLogicalName_39907…;Hash=1677525787' state changed from CERT_ACCESS_REQUESTED to CERT_ACCESS_GRANTED
```

### <a name="ios-and-ipados"></a>iOS en iPadOS

Op het iOS- of iPadOS-apparaat kunt u het certificaat weergeven in het profiel voor Apparaatbeheer. Zoom in om de details voor geïnstalleerde certificaten te zien.

![iOS-certificaat](../protect/media/troubleshoot-scep-certificate-delivery/ios-certificate.png)

U kunt ook vermeldingen vinden die lijken op de volgende vermeldingen in het [iOS-foutopsporingslogboek](troubleshoot-scep-certificate-profiles.md#logs-for-ios-and-ipados-devices):

```
Debug 18:30:53.691033 -0500 profiled Performing synchronous URL request: https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACert&message=SCEP%20Authority\  
Debug 18:30:54.640644 -0500 profiled Performing synchronous URL request: https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=SCEP%20Authority\ 
Debug 18:30:55.487908 -0500 profiled Performing synchronous URL request: https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=PKIOperation&message=MIAGCSqGSIb3DQEHAqCAMIACAQExDzANBglghkgBZQMEAgMFADCABgkqhkiG9w0BBwGggCSABIIZfzCABgkqhkiG9w0BBwOggDCAAgEAMYIBgjCCAX4CAQAwZjBPMRUwEwYKCZImiZPyLGQBGRYFbG9jYWwxHDAaBgoJkiaJk/IsZAEZFgxmb3VydGhjb2ZmZWUxGDAWBgNVBAMTD0ZvdXJ0aENvZmZlZSBDQQITaAAAAAmaneVjEPlcTwAAAAAACTANBgkqhkiG9w0BAQEFAASCAQCqfsOYpuBToerQLkw/tl4tH9E+97TBTjGQN9NCjSgb78fF6edY0pNDU+PH4RB356wv3rfZi5IiNrVu5Od4k6uK4w0582ZM2n8NJFRY7KWSNHsmTIWlo/Vcr4laAtq5rw+CygaYcefptcaamkjdLj07e/Uk4KsetGo7ztPVjSEFwfRIfKv474dLDmPqp0ZwEWRQG 
Debug 18:30:57.285730 -0500 profiled Adding dependent Microsoft.Profiles.MDM to parent www.windowsintune.com.SCEP.ModelName=AC_51bad41f.../LogicalName_1892fe4c...;Hash=-912418295 in domain ManagedProfileToManagingProfile to system\ 
Default 18:30:57.320616 -0500 profiled Profile \'93www.windowsintune.com.SCEP.ModelName=AC_51bad41f.../LogicalName_1892fe4c...;Hash=-912418295\'94 installed.\ 
```

### <a name="windows"></a>Windows

Controleer op het Windows-apparaat of het certificaat is geleverd:

- Voer **eventvwr.msc** uit om Logboeken te openen. Ga naar **Logboeken Toepassingen en Services** > **Microsoft** > **Windows** > **DeviceManagement-Enterprise-Diagnostic-Provider** > **Beheerder**, en zoek **Gebeurtenis 39**. Deze gebeurtenis moet een algemene beschrijving hebben van: **SCEP: certificaat is geïnstalleerd.**

   ![Gebeurtenis 39 in het Windows-toepassingslogboek](../protect/media/troubleshoot-scep-certificate-delivery/device-app-log.png)

Als u het certificaat wilt weergeven op het apparaat, voert u **certmgr.msc** uit om de MMC-module Certificaten te openen, en controleer u of de hoofdmap en SCEP-certificaten juist zijn geïnstalleerd op het apparaat in het persoonlijke archief:

   1. Ga naar **Certificaten (lokale computer)**  > **Vertrouwde basiscertificeringsinstanties** > **Certificaten**, en controleer of het basiscertificaat van uw CA aanwezig is. De waarden voor *Verleend aan* en *Verleend door* zijn hetzelfde.
   2. Ga in de MMC-module Certificaten naar **Certificaten – Huidige gebruiker** > **Persoonlijke** > **Certificaten**, en controleer of het aangevraagde certificaat aanwezig is, en of *Verleend door* gelijk is aan de naam van de CA.

## <a name="troubleshoot-failures"></a>Fouten bij probleemoplossing

### <a name="android"></a>Android

Als u fouten in deze stap wilt oplossen, bekijkt u de fouten die zijn vastgelegd in het OMA DM-logboek.

### <a name="ios-and-ipados"></a>iOS en iPadOS

Als u fouten in deze stap wilt oplossen, bekijkt u de fouten die zijn vastgelegd in het foutopsporingslogboek.

### <a name="windows"></a>Windows

Als u problemen wilt oplossen waarbij het certificaat niet is geïnstalleerd op het apparaat, controleert u het Windows-gebeurtenislogboek op fouten die mogelijk op problemen duiden:

- Voer op het apparaat **eventvwr.msc** uit om Logboeken te openen, en ga vervolgens naar **Logboeken Toepassingen en Services** > **Microsoft** > **Windows** > **DeviceManagement-Enterprise-Diagnostic-Provider** > **Beheerder**.

Fouten met de levering en installatie van het certificaat op het apparaat zijn doorgaans gerelateerd aan bewerkingen in Windows, en niet in Intune.

## <a name="next-steps"></a>Volgende stappen

Wanneer het certificaat is geïmplementeerd op het apparaat, maar in Intune geen melding over een geslaagde implementatie wordt weergegeven, raadpleegt u [NDES-rapportage in Intune](troubleshoot-scep-certificate-reporting.md) om problemen met de rapportage op te lossen.
