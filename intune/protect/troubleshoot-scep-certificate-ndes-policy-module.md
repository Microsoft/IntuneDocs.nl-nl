---
title: Problemen met de beleidsmodule van Microsoft Intune Certificate Connector oplossen | Microsoft Docs
description: Problemen met de werking van de NDES-beleidsmodule oplossen wanneer in de module een certificaataanvraag wordt verwerkt wanneer u SCEP-certificaatprofielen gebruikt voor het implementeren van certificaten met Intune.
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
ms.openlocfilehash: be53f6102226b004cab2bd953357e8c360a00f67
ms.sourcegitcommit: c46b0c2d4507be6a2786a4ea06009b2d5aafef85
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/01/2020
ms.locfileid: "76915834"
---
# <a name="troubleshoot-the-ndes-policy-module-in-microsoft-intune"></a>Problemen met de NDES-beleidsmodule in Microsoft Intune oplossen

De informatie in dit artikel kan u helpen bij het valideren van de werking van de beleidsmodule voor de registratieservice voor netwerkapparaten die met de Microsoft Intune Certificate Connector wordt geïnstalleerd. Wanneer NDES een aanvraag voor een certificaat ontvangt, stuurt het de aanvraag door naar de beleidsmodule, die de aanvraag als geldig valideert voor het apparaat. Na de validatie neemt NDES contact op met de certificeringsinstantie (CA) om het certificaat namens het apparaat aan te vragen.

Dit artikel is van toepassing op stap 3 en stap 4 van de [SCEP-communicatiewerkstroom](troubleshoot-scep-certificate-profiles.md).

## <a name="ndes-communication-to-the-policy-module"></a>NDES-communicatie met de beleidsmodule

Na ontvangst van de certificaataanvraag van een apparaat valideert NDES die aanvraag bij Intune via de beleidsmodule die met de Microsoft Intune Certificate Connector wordt geïnstalleerd. Deze vermeldingen verwijzen naar het *certificaatregistratiepunt*.

**Logboekvermeldingen die aangeven dat het is geslaagd**:

Om te bevestigen dat de validatieaanvraag bij de module is ingediend, zoekt u in logboeken op de NDES-server naar een vermelding die lijkt op de volgende voorbeelden:

- **IIS-logboeken**:

  ```
  fe80::f53d:89b8:c3e8:5fec%13 POST /CertificateRegistrationSvc/Certificate/VerifyRequest - 443 - 
  fe80::f53d:89b8:c3e8:5fec%13 NDES_Plugin - 201 0 0 341 875
  ```

- **NDESPlugin-logboek**:

  ```
  Calling VerifyRequest ...  
  Sending request to certificate registration point.
  ```

  In het volgende voorbeeld ziet u een geslaagde validatie van de aanvraag voor de controle van de apparaten. De NDES kan nu contact opnemen met de certificeringsinstantie:

  ```
  Verify challenge returns true
  Exiting VerifyRequest with 0x0
  ```

- **CertificateRegistrationPoint.svclog**:

  `Validation Phase 1 finished with status True.`  
  `Validation Phase 3 finished with status True.`  
  `VerifyRequest Finished with status True`


**Als er geen indicatoren voor een geslaagde validatie aanwezig zijn**:

Als u deze vermeldingen niet vindt, controleert u eerst de richtlijnen voor probleemoplossing voor de [communicatie van het apparaat met de NDES-server](troubleshoot-scep-certificate-device-to-ndes.md#troubleshoot-common-errors).

Als de informatie in dat artikel u niet helpt om het probleem op te lossen, kunnen de volgende aanvullende vermeldingen wijzen op problemen.

### <a name="ndespluginlog-contains-an-error-12175"></a>NDESPlugin.log bevat fout 12175

Wanneer het logboek fout 12175 bevat, die er ongeveer als volgt uitziet, is er mogelijk een probleem met het SSL-certificaat:

```
WINHTTP_CALLBACK_STATUS_FLAG_CERT_CN_INVALID
Failed to send http request /CertificateRegistrationSvc/Certificate/VerifyRequest. Error 12175
```

Moderne browsers en browsers op mobiele apparaten negeren de *algemene naam* op een SSL-certificaat als er *alternatieve onderwerpnamen* aanwezig zijn.

**Oplossing**:  Geef het SSL-certificaat van de webserver met de volgende kenmerken uit voor de *algemene naam* en de *alternatieve onderwerpnaam*, en koppel deze vervolgens aan poort 443 in IIS:

  - **Onderwerpnaam**  
    CN = externe servernaam
  - **Alternatieve onderwerpnaam**  
     Naam = naam van externe server  
     DNS-naam = naam van interne server

### <a name="ndespluginlog-contains-an-error-403--forbidden-access-is-denied"></a>NDESPlugin.log bevat fout 403 - Niet toegestaan: Toegang geweigerd"

Wanneer de volgende logboeken fout 403 bevatten, die vergelijkbaar is met de volgende, wordt het clientcertificaat mogelijk niet vertrouwd of is het ongeldig:

**NDESPlugin.log**:

```
Sending request to certificate registration point.
Verify challenge returns <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd"> <html xmlns="http://www.w3.org/1999/xhtml"> <head><meta http-equiv="Content-Type" content="text/html; charset=iso-8859-1"/>
<title>403 - Forbidden: Access is denied.</title>
```

**IIS-logboek**:

```
POST /CertificateRegistrationSvc/Certificate/VerifyRequest - 443 -<IP_address>
NDES_Plugin - 403 16 2148204809 453  
```

Dit probleem treedt op als er tussenliggende CA-certificaten aanwezig zijn in het certificaatarchief van de vertrouwde basiscertificeringsinstanties van de NDES-server.

Als een certificaat dezelfde waarde heeft voor *Uitgegeven aan* en *Uitgegeven door*, is het een basiscertificaat. Anders is het een tussenliggend certificaat.

**Oplossing**: Om het probleem op te lossen, moet u de tussenliggende CA-certificaten identificeren en verwijderen uit het certificaatarchief van de vertrouwde basiscertificeringsinstanties.

### <a name="ndespluginlog-indicates-the-challenge-returns-false"></a>NDESPlugin.log geeft aan dat de aanvraag 'onjuist' retourneert

Wanneer het resultaat van de aanvraag **onjuist** retourneert, controleert u *CertificateRegistrationPoint.svclog* op fouten. Mogelijk wordt bijvoorbeeld de fout 'Handtekeningcertificaat kan niet worden opgehaald' weergegeven, die op de volgende vermelding lijkt:

```
Signing certificate could not be retrieved. System.Security.Cryptography.CryptographicException: m_safeCertContext is an invalid handle. at System.Security.Cryptography.X509Certificates.X509Certificate.ThrowIfContextInvalid() at System.Security.Cryptography.X509Certificates.X509Certificate.GetCertHashString() at Microsoft.ConfigurationManager.CertRegPoint.CRPCertificate.RetrieveSigningCert(String certThumbprint
```

**Oplossing**: Open de register-editor op de server waarop de connector is geïnstalleerd, zoek de registersleutel `HKLM\SOFTWARE\Microsoft\MicrosoftIntune\NDESConnector` en controleer of de waarde voor SigningCertificate aanwezig is.

Als deze waarde niet aanwezig is, start u de Intune Connector-service opnieuw in services.msc en controleert u of de waarde wordt weergegeven in het register. Als de waarde nog ontbreekt, is dit vaak het gevolg van problemen met de netwerkverbinding tussen de NDES-server en de Intune-service.

## <a name="ndes-passes-the-request-to-issue-the-certificate"></a>NDES verstuurt de aanvraag om het certificaat uit te geven

Na een geslaagde validatie door het certificaatregistratiepunt (de beleidsmodule), geeft NDES de certificaataanvraag namens het apparaat door aan de CA.

**Logboekvermeldingen die aangeven dat het is geslaagd**:

- **NDESPlugin-logboek**:

  ```
  Verify challenge returns true
  Exiting VerifyRequest with 0x0
  ```

- **IIS-logboeken**:

  ```
  fe80::f53d:89b8:c3e8:5fec%13 GET /certsrv/mscep/mscep.dll/pkiclient.exe ... 80 - 
  fe80::f53d:89b8:c3e8:5fec%13 Mozilla/4.0+(compatible;+Win32;+NDES+client) - 200 0 0 2713 1296
  ```

- **CertificateRegistrationPoint.svclog**:

  `Validation Phase 1 finished with status True.`  
  `Validation Phase 3 finished with status True.`  
  `VerifyRequest Finished with status True`

**Als er geen indicatoren voor een geslaagde validatie aanwezig zijn**:

Voer de volgende stappen uit als de vermeldingen die een geslaagde validatie aangeven niet worden weergegeven:

1. Zoek naar problemen die zijn vastgelegd in *CertificateRegistrationPoint.svclog* wanneer de aanvraag wordt gecontroleerd door het certificaatregistratiepunt. Zoek naar de vermeldingen tussen de volgende regels:

   - VerifyRequest Started.
   - VerifyRequest Finished with status False

2. Open de certificeringsinstantie MMC op de CA en selecteer **Mislukte aanvragen** om te zoeken naar fouten die u kunnen helpen om het probleem vast te stellen. De volgende afbeelding is een voorbeeld:

   ![Voorbeeld van een mislukte aanvraag](../protect/media/troubleshoot-scep-certificate-ndes-policy-module/failed-requests.png)

3. Controleer het toepassingsgebeurtenislogboek op de CA op fouten. Normaal gesproken ziet u fouten die overeenkomen met wat u ziet bij **Mislukte aanvragen** in de vorige stap. De volgende afbeelding is een voorbeeld:

   ![Het toepassingslogboek controleren](../protect/media/troubleshoot-scep-certificate-ndes-policy-module/application-log-errors.png)

## <a name="next-steps"></a>Volgende stappen

Als de NDES-beleidsmodule de aanvraag valideert en de aanvraag naar de certificeringsinstantie wordt doorgestuurd, bestaat de volgende stap uit het controleren van de [levering van het certificaat op het apparaat](troubleshoot-scep-certificate-delivery.md).
