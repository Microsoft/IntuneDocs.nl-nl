---
title: Problemen oplossen met de communicatie tussen beheerde apparaten en NDES in Microsoft Intune | Microsoft Docs
description: Los problemen op met de communicatie tussen beheerde apparaten en de NDES-server, wanneer u SCEP-certificaatprofielen gebruikt om certificaten te implementeren met Intune.
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
ms.openlocfilehash: 8c81fa9b521b0d950fb69c29f7625981e709863d
ms.sourcegitcommit: c46b0c2d4507be6a2786a4ea06009b2d5aafef85
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/01/2020
ms.locfileid: "76916107"
---
# <a name="troubleshoot-device-to-ndes-server-communication-for-scep-certificate-profiles-in-microsoft-intune"></a>Los problemen op met de communicatie tussen een apparaat en de NDES-server voor SCEP-certificaatprofielen in Microsoft Intune

Gebruik de volgende informatie om te bepalen of een apparaat dat een Intune SCEP- certificaatprofiel (Intune Simple Certificate Enrollment Protocol) heeft ontvangen en verwerkt, contact kan opnemen met een NDES (registratieservice voor netwerkapparaten) om een uitdaging door te geven. Op het apparaat wordt een persoonlijke sleutel gegenereerd, en de aanvraag voor certificaatondertekening (CSR) en de uitdaging worden van het apparaat doorgegeven aan de NDES-server. Het apparaat gebruikt de URI uit het SCEP-certificaatprofiel om contact op te nemen met de NDES-server.

In dit artikel wordt verwezen naar stap 2 van het [Overzicht van de SCEP-communicatiestroom](troubleshoot-scep-certificate-profiles.md).

## <a name="review-iis-logs-for-a-connection-from-the-device"></a>IIS-logboeken controleren op een verbinding vanaf het apparaat

IIS-logboeken bevatten hetzelfde type vermeldingen voor alle platforms.


1. Open op de NDES-server het meest recente IIS-logboekbestand dat u kunt vinden in de volgende map:  *%SystemDrive%\inetpub\logs\logfiles\w3svc1*

2. Zoek in het logboek naar vermeldingen die vergelijkbaar zijn met de volgende voorbeelden. Beide voorbeelden bevatten een status **200**. Deze wordt aan het einde weergegeven:

   `fe80::f53d:89b8:c3e8:5fec%13 GET /certsrv/mscep/mscep.dll/pkiclient.exe operation=GetCACaps&message=default 80 - fe80::f53d:89b8:c3e8:5fec%13 Mozilla/4.0+(compatible;+Win32;+NDES+client) - 200 0 0 186 0.`

   En

   `fe80::f53d:89b8:c3e8:5fec%13 GET /certsrv/mscep/mscep.dll/pkiclient.exe operation=GetCACert&message=default 80 - fe80::f53d:89b8:c3e8:5fec%13 Mozilla/4.0+(compatible;+Win32;+NDES+client) - 200 0 0 3567 0`

3. Wanneer via het apparaat contact wordt opgenomen met IIS, wordt een HTTP GET-aanvraag voor mscep.dll vastgelegd.

   Controleer de statuscode aan het einde van deze aanvraag:
   - **Statuscode 200**: Deze status geeft aan dat de verbinding met de NDES-server is geslaagd.
   - **Statuscode 500**: De groep IIS_IURS heeft mogelijk niet de juiste machtigingen. Ga naar [Statuscode 500](#status-code-500) verderop in dit artikel.
   - Als de statuscode niet 200 of 500 is:

     - Raadpleeg [De URL van de SCEP-server testen](#test-the-scep-server-url) verderop in dit artikel om de configuratie te helpen valideren.

     - Raadpleeg [De HTTP-statuscode in IIS 7 en latere versies](https://support.microsoft.com/help/943891) voor informatie over minder veelvoorkomende foutcodes.

   Als de verbindingsaanvraag niet is vastgelegd, wordt communicatie vanaf het apparaat mogelijk geblokkeerd in het netwerk, tussen het apparaat en de NDES-server.

## <a name="review-device-logs-for-connections-to-ndes"></a>Logboeken van apparaten controleren voor verbindingen met NDES

### <a name="android-devices"></a>Android-apparaten

Raadpleeg het [OMADM-logboek van het apparaat](troubleshoot-scep-certificate-profiles.md#logs-for-android-devices). Zoek naar vermeldingen die vergelijkbaar zijn met de volgende vermeldingen, die worden vastgelegd wanneer het apparaat verbinding maakt met NDES:

```
2018-02-27T05:16:08.2500000  VERB  Event  com.microsoft.omadm.platforms.android.certmgr.CertificateEnrollmentManager  18327    10  There are 1 requests
2018-02-27T05:16:08.2500000  VERB  Event  com.microsoft.omadm.platforms.android.certmgr.CertificateEnrollmentManager  18327    10  Trying to enroll certificate request: ModelName=AC_51bad41f-3854-4eb5-a2f2-0f7a94034ee8%2FLogicalName_39907e78_e61b_4730_b9fa_d44a53e4111c;Hash=1677525787
2018-02-27T05:16:09.5530000  VERB  Event  org.jscep.transport.UrlConnectionGetTransport  18327    10  Sending GetCACaps(ca) to https://<server>.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=ca
2018-02-27T05:16:14.6440000  VERB  Event  org.jscep.transport.UrlConnectionGetTransport  18327    10  Received '200 OK' when sending GetCACaps(ca) to https://<server>.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=ca
2018-02-27T05:16:21.8220000  VERB  Event  org.jscep.message.PkiMessageEncoder  18327     10 Encoding message: org.jscep.message.PkcsReq@2b06f45f[messageData=org.<server>.pkcs.PKCS10CertificationRequest@699b3cd,messageType=PKCS_REQ,senderNonce=Nonce [D447AE9955E624A56A09D64E2B3AE76E],transId=251E592A777C82996C7CF96F3AAADCF996FC31FF]
2018-02-27T05:16:21.8790000  VERB  Event  org.jscep.message.PkiMessageEncoder  18327     10  Signing pkiMessage using key belonging to [dn=CN=<uesrname>; serial=1]
2018-02-27T05:16:21.9580000  VERB  Event  org.jscep.transaction.EnrollmentTransaction  18327     10  Sending org.<server>.cms.CMSSignedData@ad57775
```

De belangrijkste vermeldingen zijn onder andere de volgende tekenreeksen:

- Er is 1 200 OK-aanvraag
- ontvangen tijdens het verzenden van GetCACaps(ca) naar https://\<server>.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=ca
- pkiMessage ondertekenen met behulp van de sleutel die hoort bij [dn=CN=\<username>; serial=1]


De verbinding wordt ook vastgelegd met IIS in de map %SystemDrive%\inetpub\logs\LogFiles\W3SVC1\ van de NDES-server. Hier volgt een voorbeeld:

```
fe80::f53d:89b8:c3e8:5fec%13 GET /certsrv/mscep/mscep.dll operation=GetCACert&message=ca 443 - 
fe80::f53d:89b8:c3e8:5fec%13 Dalvik/2.1.0+(Linux;+U;+Android+5.0;+P01M+Build/LRX21V) - 200 0 0 3909 0
fe80::f53d:89b8:c3e8:5fec%13 GET /certsrv/mscep/mscep.dll operation=GetCACaps&message=ca 443 - 
fe80::f53d:89b8:c3e8:5fec%13 Dalvik/2.1.0+(Linux;+U;+Android+5.0;+P01M+Build/LRX21V) - 200 0 0 421 
```

### <a name="ios-and-ipados-devices"></a>iOS- en iPadOS-apparaten

Raadpleeg het [foutopsporingslogboek van het apparaat](troubleshoot-scep-certificate-profiles.md#logs-for-ios-and-ipados-devices). Zoek naar vermeldingen die vergelijkbaar zijn met de volgende vermeldingen, die worden vastgelegd wanneer het apparaat verbinding maakt met NDES:

```
debug    18:30:53.691033 -0500    profiled    Performing synchronous URL request: https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACert&message=SCEP%20Authority\ 
debug    18:30:54.640644 -0500    profiled    Performing synchronous URL request: https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=GetCACaps&message=SCEP%20Authority\ 
default    18:30:55.483977 -0500    profiled    Attempting to retrieve issued certificate...\ 
debug    18:30:55.487798 -0500    profiled    Sending CSR via GET.\  
debug    18:30:55.487908 -0500    profiled    Performing synchronous URL request: https://<server>-contoso.msappproxy.net/certsrv/mscep/mscep.dll?operation=PKIOperation&message=MIAGCSqGSIb3DQEHAqCAMIACAQExDzANBglghkgBZQMEAgMFADCABgkqhkiG9w0BBwGggCSABIIZfzCABgkqhkiG9w0BBwOggDCAAgEAMYIBgjCCAX4CAQAwZjBPMRUwEwYKCZImiZPyLGQBGRYFbG9jYWwxHDAaBgoJkiaJk/IsZAEZFgxmb3VydGhjb2ZmZWUxGDAWBgNVBAMTD0ZvdXJ0aENvZmZlZSBDQQITaAAAAAmaneVjEPlcTwAAAAAACTANBgkqhkiG9w0BAQEFAASCAQCqfsOYpuBToerQLkw/tl4tH9E+97TBTjGQN9NCjSgb78fF6edY0pNDU+PH4RB356wv3rfZi5IiNrVu5Od4k6uK4w0582ZM2n8NJFRY7KWSNHsmTIWlo/Vcr4laAtq5rw+CygaYcefptcaamkjdLj07e/Uk4KsetGo7ztPVjSEFwfRIfKv474dLDmPqp0ZwEWRQGZwmPoqFMbX3g85CJT8khPaqFW05yGDTPSX9YpuEE0Bmtht9EwOpOZe6O7sd77IhfFZVmHmwy5mIYN7K6mpx/4Cb5zcNmY3wmTBlKEkDQpZDRf5PpVQ3bmQ3we9XxeK1S4UsAXHVdYGD+bg/bCafMIAGCSqGSIb3DQEHATAUBggqhkiG9w0DBwQI5D5J2lwZS5OggASCF6jSG9iZA/EJ93fEvZYLV0v7GVo3JAsR11O7DlmkIqvkAg5iC6DQvXO1j88T/MS3wV+rqUbEhktr8Xyf4sAAPI4M6HMfVENCJTStJw1PzaGwUJHEasq39793nw4k268UV5XHXvzZoF3Os2OxUHSfHECOj
```

De belangrijkste vermeldingen zijn onder andere de volgende tekenreeksen:

- operation=GetCACert
- Poging om het verleende certificaat op te halen
- CSR verzenden via GET
- operation=PKIOperation

### <a name="windows-devices"></a>Windows-apparaten

Op een Windows-apparaat dat verbinding maakt met NDES, kunt u Logboeken van Windows voor apparaten bekijken, en zoeken naar aanwijzingen van een geslaagde verbinding. Verbindingen worden vastgelegd als een gebeurtenis-id **36** in het apparaatlogboek *DeviceManagement-Enterprise-Diagnostics-Provide* > **Beheerder**.

U opent het logboek als volgt:

1. Voer op het apparaat **eventvwr.msc** uit om Logboeken van Windows te openen.

2. Vouw uit: **Logboeken Toepassingen en Services** > **Microsoft** > **Windows** > **DeviceManagement-Enterprise-Diagnostic-Provider** > **Beheerder**.

3. Zoek naar gebeurtenis **36**, die op het volgende voorbeeld lijkt, met de belangrijkste regel van **SCEP: certificaataanvraag is gegenereerd**:

   ```
   Event ID:      36
   Task Category: None
   Level:         Information
   Keywords:
   User:          <UserSid>
   Computer:      <Computer Name>
   Description:
   SCEP: Certificate request generated successfully. Enhanced Key Usage: (1.3.6.1.5.5.7.3.2), NDES URL: (https://<server>/certsrv/mscep/mscep.dll/pkiclient.exe), Container Name: (), KSP Setting: (0x2), Store Location: (0x1).
   ```

## <a name="troubleshoot-common-errors"></a>Veelvoorkomende fouten oplossen

De volgende secties kunnen helpen bij algemene verbindingsproblemen vanaf alle platformen naar NDES.

### <a name="status-code-500"></a>Statuscode 500

Verbindingen die lijken op het volgende voorbeeld, met de statuscode 500, geven aan dat het gebruikersrecht *Een client imiteren na verificatie* niet is toegewezen aan de groep IIS_IURS op de NDES-server. De statuswaarde **500** wordt aan het einde weergegeven:

```
2017-08-08 20:22:16 IP_address GET /certsrv/mscep/mscep.dll operation=GetCACert&message=SCEP%20Authority 443 - 10.5.14.22 profiled/1.0+CFNetwork/811.5.4+Darwin/16.6.0 - 500 0 1346 31
```

**Ga als volgt te werk om dit probleem op te lossen**:

1. Voer op de NDES-server **secpol. msc** uit om het lokale beveiligingsbeleid te openen.

2. Vouw **Lokaal beleid** uit en klik vervolgens op **Toewijzing van gebruikersrecht**.

3. Dubbelklik in het rechterdeelvenster op **Een client imiteren na verificatie**.

4. Klik op **Gebruiker of groep toevoegen**, voer **IIS_IURS** in het vak **Geef de objectnamen op** in, en klik vervolgens op **OK**.

5. Klik op **OK**.

6. Start de computer opnieuw op en probeer vervolgens opnieuw verbinding te maken vanaf het apparaat.

### <a name="test-the-scep-server-url"></a>URL van SCEP-server testen

Gebruik de volgende stappen om de URL te testen die is opgegeven in het SCEP-certificaatprofiel.

1. Bewerk in Intune uw SCEP-certificaatprofiel en kopieer de Server-URL. De URL moet lijken op *https://contoso.com/certsrv/mscep/msecp.dll* .

2. Open een webbrowser en blader naar de URL van de SCEP-server. Het resultaat moet zijn: **HTTP-fout 403.0 – Verboden**. Dit resultaat is een indicatie dat de URL correct werkt.

   Als u deze fout niet ontvangt, selecteert u de koppeling die lijkt op de fout die u ziet, voor hulp bij het specifieke probleem:
   - [Ik ontvang een algemeen NDES-bericht](#general-ndes-message)
   - [Ik ontvang: HTTP-fout 503. De service is niet beschikbaar](#http-error-503)
   - [Ik ontvang de fout: Time-out van gateway](#gatewaytimeout)
   - [Ik ontvang: HTTP 414-aanvraag-URI is te lang](#http-414-request-uri-too-long)
   - [Ik ontvang: deze pagina kan niet worden weergegeven](#this-page-cant-be-displayed)
   - [Ik ontvang: 500 - Interne serverfout](#internal-server-error)

#### <a name="general-ndes-message"></a>Algemeen NDES-bericht

Als u naar de URL van de SCEP-server bladert, ontvangt u het volgende NDES-bericht (registratieservice voor netwerkapparaten):

![URL van SCEP-server](../protect/media/troubleshoot-scep-certificate-device-to-ndes/ndes-server-url-message.png)

- **Oorzaak**: Dit probleem is doorgaans een probleem met de installatie van de Microsoft Intune-connector.

  Mscep.dll is een ISAPI-extensie waarmee inkomende aanvragen worden onderschept, en als deze juist is geïnstalleerd wordt de HTTP 403-fout weergegeven.
  
  **Oplossing**: Controleer het bestand *SetupMsi.log* om te bepalen of de installatie van de Microsoft Intune-connector is geslaagd. In het volgende voorbeeld duiden *Installatie is voltooid* en *Installatie is geslaagd of foutstatus: 0* op een geslaagde installatie:

  ```
  MSI (c) (28:54) [16:13:11:905]: Product: Microsoft Intune Connector -- Installation completed successfully.
  MSI (c) (28:54) [16:13:11:999]: Windows Installer installed the product. Product Name: Microsoft Intune Connector. Product Version: 6.1711.4.0. Product Language: 1033. Manufacturer: Microsoft Corporation. Installation success or error status: 0.
  ```

  Als de installatie mislukt, verwijdert u de Microsoft Intune-connector en installeert u deze opnieuw.

#### <a name="http-error-503"></a>HTTP-fout 503

Wanneer u naar de URL van de SCEP-server bladert, ontvangt u de volgende fout:

![HTTP-fout 503. De service is niet beschikbaar](../protect/media/troubleshoot-scep-certificate-device-to-ndes/service-unavailable.png)

Dit probleem wordt meestal veroorzaakt doordat de **SCEP**-groep van toepassingen in IIS niet is gestart. Open **IIS-beheer** op de NDES-server en ga naar **groepen van toepassingen**. Zoek de **SCEP**-groep van toepassingen en bevestig dat deze is gestart.

Als de SCEP-groep van toepassingen niet is gestart, controleert u het toepassingsgebeurtenislogboek op de server:

1. Voer op het apparaat **eventvwr.msc** uit om **Logboeken** te openen, en ga naar **Windows-logboeken** > **Toepassing**.

2. Zoek naar een gebeurtenis die vergelijkbaar is met het volgende voorbeeld, wat betekent dat de groep van toepassingen vastloopt wanneer een aanvraag wordt ontvangen:

   ```
   Log Name:      Application
   Source:        Application Error
   Event ID:      1000
   Task Category: Application Crashing Events
   Level:         Error
   Keywords:      Classic
   Description: Faulting application name: w3wp.exe, version: 8.5.9600.16384, time stamp: 0x5215df96
   Faulting module name: ntdll.dll, version: 6.3.9600.18821, time stamp: 0x59ba86db
   Exception code: 0xc0000005
   ```

**Veelvoorkomende oorzaken voor vastlopen van een groep van toepassingen**:

- **Oorzaak 1**: Er zijn tussenliggende CA-certificaten (niet zelf-ondertekend) aanwezig in het certificaatarchief van de vertrouwde basiscertificeringsinstanties van de NDES-server.

  **Oplossing**: Verwijder tussenliggende certificaten uit het certificaatarchief van de vertrouwde basiscertificeringsinstanties, en start de NDES-server vervolgens opnieuw op.
  
  Als u alle tussenliggende certificaten in het certificaatarchief van de vertrouwde basiscertificeringsinstanties wilt identificeren, voert u de volgende Power shell-cmdlet uit: `Get-Childitem -Path cert:\LocalMachine\root -Recurse | Where-Object {$_.Issuer -ne $_.Subject}`

  Als een certificaat dezelfde waarde heeft voor **Verleend aan** en **Verleend door**, is het een basiscertificaat. Anders is het een tussenliggend certificaat.

  Nadat u certificaten hebt verwijderd en de server opnieuw het opgestart, voert u de PowerShell-cmdlet nog een keer uit om te bevestigen dat er geen tussenliggende certificaten zijn. Als er wel tussenliggende certificaten zijn, controleert u of deze naar de NDES-server worden gepusht op basis van groepsbeleid. Als dit het geval is, sluit u de NDES-server uit van het groepsbeleid en verwijdert u de tussenliggende certificaten opnieuw.

- **Oorzaak 2**: De URL’s in de certificaatintrekkingslijst (CRL) zijn geblokkeerd of onbereikbaar voor de certificaten die worden gebruikt voor Intune Certificate Connector.

  **Oplossing**: Extra logboekregistratie inschakelen om meer informatie te verzamelen:
  1. Open Logboeken, klik op **Weergeven**, en zorg ervoor dat de optie **Logboeken voor analyseren en foutopsporing weergeven** is ingeschakeld.
  2. Ga naar **Logboeken Toepassingen en Services** > **Microsoft** > **Windows** > **CAPI2** > **Operationeel**, klik met de rechtermuisknop op **Operationeel**, en klik vervolgens op **Logboek inschakelen**.
  3. Nadat CAPI2-logboekregistratie is ingeschakeld, reproduceert u het probleem en bekijkt u het gebeurtenislogboek om het probleem op te lossen.

- **Oorzaak 3**: Voor IIS-machtiging in **CertificateRegistrationSvc** is **Windows Authentication** ingeschakeld.

  **Oplossing**: Schakel **Anonieme verificatie** in en schakel **Windows-verificatie** uit, en start de NDES-server opnieuw op.

  ![IIS-machtigingen](../protect/media/troubleshoot-scep-certificate-device-to-ndes/iis-permissions.png)

#### <a name="gatewaytimeout"></a>GatewayTimeout

Wanneer u naar de URL van de SCEP-server bladert, ontvangt u de volgende fout:

![Gatewaytimeout-fout](../protect/media/troubleshoot-scep-certificate-device-to-ndes/gateway-timeout.png)

- **Oorzaak**: De **Microsoft AAD Application Proxy Connector**-service is niet gestart.

  **Oplossing**:  Voer **services.msc** uit, en zorg ervoor dat de **Microsoft AAD Application Proxy Connector**-service actief is en dat **Opstarttype** is ingesteld op **Automatisch**.

#### <a name="http-414-request-uri-too-long"></a>HTTP 414-aanvraag-URI is te lang

Wanneer u naar de URL van de SCEP-server bladert, ontvangt u de volgende fout: `HTTP 414 Request-URI Too Long`

- **Oorzaak**: IIS-aanvraagfiltering is niet geconfigureerd voor ondersteuning van de lange URL's (query's) die de NDES-service ontvangt. Deze ondersteuning wordt geconfigureerd wanneer u de [NDES-service configureert](certificates-scep-configure.md#configure-the-ndes-service) voor gebruik met uw infrastructuur voor SCEP.

- **Oplossing**: Ondersteuning voor lange URL's configureren.

  1. Open IIS-beheer op de NDES-server, selecteer **Standaardwebsite** > **Aanvraagfiltering** > **Functie-instelling bewerken** om de pagina **Instellingen voor aanvraagfiltering bewerken** te openen.

  2. Configureer de volgende instellingen:
     - **Maximale URL-lengte (in bytes)** = 65534
     - **Maximale queryreeks (in bytes)** = 65534

  3. Selecteer **OK** om deze configuratie op te slaan en IIS-beheer te sluiten.

  4. Valideer deze configuratie door de volgende registersleutel te zoeken om te bevestigen dat deze de aangegeven waarden bevat:

     HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters

     De volgende waarden zijn ingesteld als DWORD-vermeldingen:
     - Naam: **MaxFieldLength**, met een decimale waarde van **65534**
     - Naam: **MaxRequestBytes**, met een decimale waarde van **65534**

  5. Start de NDES-server opnieuw op.

#### <a name="this-page-cant-be-displayed"></a>Deze pagina kan niet worden weergegeven

U hebt Azure AD-toepassingsproxy geconfigureerd. Wanneer u naar de URL van de SCEP-server bladert, ontvangt u de volgende fout:

`This page can't be displayed`

- **Oorzaak**: Dit probleem treedt op wanneer de externe URL voor de SCEP onjuist is in de configuratie van de toepassingsproxy. Een voorbeeld van deze URL is https://contoso.com/certsrv/mscep/mscep.dll.

  **Oplossing**: Gebruik het standaarddomein van *yourtenant.msappproxy.net* voor de externe URL voor de SCEP in de configuratie van de toepassingsproxy.

#### <a name="internal-server-error"></a>500 - Interne serverfout

Wanneer u naar de URL van de SCEP-server bladert, ontvangt u de volgende fout:

![500 - Interne serverfout](../protect/media/troubleshoot-scep-certificate-device-to-ndes/500-internal-server-error.png)

- **Oorzaak 1**: Het NDES-serviceaccount is vergrendeld of het wachtwoord is verlopen.

  **Oplossing**: Ontgrendel het account of stel het wachtwoord opnieuw in.

- **Oorzaak 2**: De MSCEP RA-certificaten zijn verlopen.

  **Oplossing**: Als de MSCEP-RA-certificaten zijn verlopen, installeert u de NDES-rol opnieuw of vraagt u nieuwe certificaten aan voor CEP-versleuteling en Exchange-inschrijvingsagent (offlineaanvraag).

  Volg deze stappen om nieuwe certificaten aan te vragen:

  1. Open de MMC-module Certificaatsjablonen in de CA (certificeringsinstantie) of verlenende CA. Zorg ervoor dat de aangemelde gebruiker en de NDES-server beschikken over machtigingen voor **Lezen** en **Inschrijven** voor de certificaatsjablonen CEP-versleuteling en Exchange-inschrijvingsagent (offlineaanvraag).

  2. Controleer de verlopen certificaten op de NDES-server, kopieer de informatie in **Onderwerp** uit het certificaat.

  3. Open de MMC-module Certificaten voor **Computeraccount**.

  4. Vouw **Persoonlijk** uit, klik met de rechtermuisknop op **Certificaten** en selecteer vervolgens **Alle taken** > **Nieuw certificaat aanvragen**.

  5. Selecteer op de pagina **Certificaat aanvragen** de optie **CEP-versleuteling**, en klik vervolgens op **Er zijn meer gegevens nodig voor inschrijving voor dit certificaat. Klik hier om instellingen te configureren**.

     ![CEP-versleuteling selecteren](../protect/media/troubleshoot-scep-certificate-device-to-ndes/select-scep-encryption.png)

  6. Klik in **Certificaateigenschappen** op het tabblad **Onderwerp**. Vul bij **Onderwerpnaam** de informatie in die u hebt verzameld tijdens stap 2, klik op **Toevoegen** en klik vervolgens op **OK**.

  7. Voltooi de certificaatinschrijving.

  8. Open de MMC-module Certificaten voor **Mijn gebruikersaccount**.

     Wanneer u zich inschrijft voor het certificaat Exchange-inschrijvingsagent (offlineaanvraag), moet u dit doen in de gebruikerscontext. Omdat het **Onderwerptype** van deze certificaatsjabloon is ingesteld op **Gebruiker**.

  9. Vouw **Persoonlijk** uit, klik met de rechtermuisknop op **Certificaten** en selecteer vervolgens **Alle taken** > **Nieuw certificaat aanvragen**.

  10. Selecteer op de pagina **Certificaat aanvragen** de optie **Exchange-inschrijvingsagent (offlineaanvraag)** , en klik vervolgens op **Er zijn meer gegevens nodig voor inschrijving voor dit certificaat. Klik hier om instellingen te configureren**.

      ![Exchange-inschrijvingsagent selecteren](../protect/media/troubleshoot-scep-certificate-device-to-ndes/select-exchange-enrollment-agent.png)

  11. Klik in **Certificaateigenschappen** op het tabblad **Onderwerp**. Vul bij **Onderwerpnaam** de informatie in die u hebt verzameld tijdens stap 2, klik op **Toevoegen**.

      ![Certificaateigenschappen](../protect/media/troubleshoot-scep-certificate-device-to-ndes/certificate-properties.png)

      Selecteer het tabblad **Persoonlijke sleutel**, selecteer **Persoonlijke sleutel exporteerbaar maken** en klik vervolgens op **OK**.

      ![Persoonlijke sleutel](../protect/media/troubleshoot-scep-certificate-device-to-ndes/private-key.png)

  12. Voltooi de certificaatinschrijving.

  13. Exporteer het certificaat Exchange-inschrijvingsagent (offlineaanvraag) uit het certificaatarchief van de huidige gebruiker. Selecteer in de wizard Certificaat exporteren **Ja, de persoonlijke sleutel exporteren**.

  14. Importeer het certificaat in het certificaatarchief van de lokale computer.

  15. Voer in de MMC-module Certificaten de volgende actie uit voor elk van de nieuwe certificaten:

      Klik met de rechtermuisknop op het certificaat, klik op **Alle taken** > **Persoonlijke sleutels beheren**, voeg een machtiging voor **Lezen** toe aan het NDES-serviceaccount.

  16. Voer de opdracht **iisreset** uit om IIS opnieuw te starten.

## <a name="next-steps"></a>Volgende stappen

Als de verbinding tot stand is gebracht tussen het apparaat en de NDES-server om de certificaataanvraag te kunnen doen, is de volgende stap het controleren van de [beleidsmodule van Intune Certificate Connector](troubleshoot-scep-certificate-ndes-policy-module.md).
