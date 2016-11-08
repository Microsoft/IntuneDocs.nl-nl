---
title: Toegang tot netwerken beperken met Cisco ISE | Microsoft Intune
description: Gebruik Cisco ISE in combinatie met Intune, zodat apparaten bij Intune zijn ingeschreven en voldoen aan het beleid voordat ze gebruikmaken van Wi-Fi- en VPN-verbindingen die worden beheerd door Cisco ISE.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/05/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5631bac3-921d-438e-a320-d9061d88726c
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 17b957cc2baedddfc53bfdf7b875e4ecb28b8517
ms.openlocfilehash: a29473cb0931c01143614116ce0e99a579f35923


---

# <a name="using-cisco-ise-with-microsoft-intune"></a>Cisco ISE gebruiken met Microsoft Intune
Als u Intune integreert in Cisco ISE (Identity Services Engine) kunt netwerkbeleid schrijven voor uw ISE-omgeving met behulp van de Intune-apparaatinschrijving en de compatibiliteitsstatus. U kunt dit beleid gebruiken om ervoor te zorgen dat uw bedrijfsnetwerk alleen toegankelijk is voor bedrijven die worden beheerd door Intune en die voldoen aan het Intune-beleid.

## <a name="configuration-steps"></a>Configuratiestappen

Als u deze integratie wilt inschakelen, hoeft u geen installatie uit te voeren in uw Intune-tenant. U moet uw server Cisco ISE-server machtigingen geven voor toegang tot uw Intune-tenant. Nadat u dat hebt gedaan, wordt de rest van de installatie op de Cisco ISE-server uitgevoerd. In dit artikel vindt u instructies voor het opgeven van machtigingen in de ISE-server voor toegang tot uw Intune-tenant.

### <a name="step-1-manage-the-certificates"></a>Stap 1: de certificaten beheren
Exporteer het certificaat van de Azure Active Directory-console (Azure AD) en importeer het in het archief met vertrouwde certificaten van de ISE-console:

#### <a name="internet-explorer-11"></a>Internet Explorer 11


   a. Voer Internet Explorer uit als beheerder en meld u aan bij de Azure AD-console.

   b. Kies het vergrendelingspictogram in de adresbalk en kies **Certificaten weergeven**.

   c. Ga naar het tabblad **Details** van de certificaateigenschappen en selecteer **Kopiëren naar bestand**.

   d. Klik op de welkomstpagina van de **wizard Certificaat importeren** op **Volgende**.

   e. Op de pagina **Bestandsindeling voor export** laat u de standaardwaarde staan, **DER Encoded Binary X.509 (.CER)** en kiest u **Volgende**.  

   f. Op de pagina **Te exporteren bestand** kiest u **Bladeren** om een locatie te selecteren om het bestand op te slaan. Geef vervolgens een bestandsnaam op. Hoewel het lijkt alsof u een bestand kiest om het te exporteren, geeft u in feite het bestand waarin u het geëxporteerde certificaat opslaat, een naam. Kies **Volgende** &gt; **Voltooien**.

   g. Importeer in de ISE-console het Intune-certificaat (het bestand dat u hebt geëxporteerd) naar het archief **Vertrouwde certificaten**.

#### <a name="safari"></a>Safari

 a. Meld u aan bij de Azure AD-console.

b. Kies het vergrendelingspictogram &gt;  **Meer informatie**.

   c. Selecteer **Certificaat weergeven** &gt; **Details**.

   d. Kies het certificaat en kies **Exporteren**. 

   e. Importeer in de ISE-console het Intune-certificaat (het bestand dat u hebt geëxporteerd) naar het archief **Vertrouwde certificaten**.

> [!IMPORTANT]
>
> Controleer de vervaldatum van het certificaat omdat u een nieuw certificaat moet exporteren en importeren wanneer dit certificaat is verlopen.


### <a name="obtain-a-selfsigned-cert-from-ise"></a>Een zelfondertekend certificaat verkrijgen van ISE 

1.  Ga in de ISE-console naar **Beheer** > **Certificaten** > **Systeemcertificaten** > **Zelfondertekend certificaat genereren**.  
2.       Exporteer het zelfondertekende certificaat.
3. Bewerk het geëxporteerde certificaat in een teksteditor: [opmerking]: <> ik zou liever geen punt plaatsen aan het eind van deze twee instructies, want ik denk dat dit verwarrend kan zijn.
 - Verwijder ** -----BEGIN CERTIFICATE-----**
 - Verwijder ** -----END CERTIFICATE-----**
 
Zorg ervoor dat alle tekst op één regel staat


### <a name="step-2-create-an-app-for-ise-in-your-azure-ad-tenant"></a>Stap 2: een app voor ISE maken in uw Azure AD-tenant
1. Kies in de Azure AD-console **Toepassingen** > **Een toepassing toevoegen** > **Een app toevoegen die mijn organisatie ontwikkelt**.
2. Geef een naam en een URL op voor de app. De URL kan de URL zijn van uw bedrijfswebsite.
3. Download het app-manifest (een JSON-bestand).
4. Bewerk het JSON-manifestbestand. In de instelling **keyCredentials** geeft u de bewerkte certificaattekst op als waarde; dit is de tekst uit stap 1.
5. Sla het bestand zonder de naam ervan te wijzigen.
6. Voorzie uw app van machtigingen voor Microsoft Graph en de Microsoft Intune-API.

 a. Kies het volgende voor Microsoft Graph:
    - **Toepassingsmachtigingen**: mapgegevens lezen
    - **Overgedragen machtigingen**:
        - Altijd toegang tot gegevens van de gebruiker
        - Gebruikers aanmelden

 b. Voor de API van Microsoft Intune kiest u in **Toepassingsmachtigingen** de optie **Apparaatstatus en naleving ophalen uit Intune**.

7. Kies **Eindpunten weergeven** en kopieer de volgende waarden voor gebruik bij het configureren van de ISE-instellingen:

|Waarde in Azure AD-portal|Overeenkomende veld in de ISE-portal|
|-------------------|---------------------------------|
|Microsoft Azure AD Graph-API-eindpunt|AutoDiscovery-URL|
|OAuth 2.0-tokeneindpunt|URL die de token uitgeeft|
|Werk uw code bij met uw client-id|Client-id|

### <a name="step-4-upload-the-selfsigned-certificate-from-ise-into-the-ise-app-you-created-in-azure-ad"></a>Stap 4: het zelfondertekende certificaat van ISE uploaden naar de ISE-app die u in Azure AD hebt gemaakt
1.     Haal de met base64 gecodeerde certificaatwaarde en de vingerafdruk op uit een openbaar X509-certificaatbestand (CER). In dit voorbeeld wordt PowerShell gebruikt:
   
      
      $cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2    $cer.Import(“mycer.cer”)    $bin = $cer.GetRawCertData()    $base64Value = [System.Convert]::ToBase64String($bin)    $bin = $cer.GetCertHash()    $base64Thumbprint = [System.Convert]::ToBase64String($bin)    $keyid = [System.Guid]::NewGuid().ToString()
 
    Sla de waarden voor $base64Thumbprint, $base64Value en $keyid op, die in de volgende stap worden gebruikt.
2.       Upload het certificaat via het manifestbestand. Meld u aan bij de [Windows Azure-beheerportal](https://manage.windowsazure.com).
2.      Zoek in de Azure AD-module de toepassing die u wilt configureren met een X.509-certificaat.
3.      Download het manifestbestand van de toepassing. 
5.      Vervang de lege eigenschap “KeyCredentials”: [], door de volgende JSON.  Het complexe type KeyCredentials wordt gedocumenteerd in [Entity and complex type reference](https://msdn.microsoft.com/library/azure/ad/graph/api/entity-and-complex-type-reference#KeyCredentialType) (Verwijzing naar entiteit en complex type).

 
    “keyCredentials“: [ { “customKeyIdentifier“: “$base64Thumbprint_from_above”, “keyId“: “$keyid_from_above“, “type”: “AsymmetricX509Cert”, “usage”: “Verify”, “value”:  “$base64Value_from_above” }2. 
     ], 
 
Bijvoorbeeld:
 
    “keyCredentials“: [
    {
    “customKeyIdentifier“: “ieF43L8nkyw/PEHjWvj+PkWebXk=”,
    “keyId“: “2d6d849e-3e9e-46cd-b5ed-0f9e30d078cc”,
    “type”: “AsymmetricX509Cert”,
    “usage”: “Verify”,
    “value”: “MIICWjCCAgSgAwIBA***omitted for brevity***qoD4dmgJqZmXDfFyQ”
    }
    ],
 
6.      Sla de wijziging op in het manifestbestand van de toepassing.
7.      Upload het bewerkte manifestbestand van de toepassing via de Azure-beheerportal.
8.      Optioneel: download het manifest opnieuw om te controleren of uw X.509-certificaat in de toepassing aanwezig is.

>[!NOTE]
>
> KeyCredentials is een verzameling. U kunt dus meerdere X.509-certificaten voor overschakelingsscenario's uploaden of certificaten uit scenario's met inbreuk verwijderen.


### <a name="step-4-configure-ise-settings"></a>Stap 4: ISE-instellingen configureren
Geef in de ISE-beheerconsole de volgende instellingswaarden op:
  - **Servertype**: Mobile Device Manager
  - **Verificatietype**: OAuth-clientreferenties
  - **AutoDiscovery**: ja
  - **AutoDiscovery-URL**: *voer de waarde uit stap 1 in.*
  - **Client-id**: *voer de waarde uit stap 1 in.*
  - **URL die de token uitgeeft**: *voer de waarde uit stap 1 in.*



## <a name="information-shared-between-your-intune-tenant-and-your-cisco-ise-server"></a>Informatie die wordt gedeeld tussen uw Intune-tenant en uw Cisco ISE-server
Deze tabel bevat de informatie die wordt gedeeld tussen uw Intune-tenant en uw Cisco ISE-server voor apparaten die worden beheerd door Intune.

|Eigenschap|  Beschrijving|
|---------------|------------------------------------------------------------|
|complianceState|De tekenreeks 'waar' of 'onwaar' die aangeeft of het apparaat compatibel of niet compatibel is.|
|isManaged|De tekenreeks 'waar' of 'onwaar' die aangeeft of de client door Intune wordt beheerd of niet.|
|macAddress|Het MAC-adres van het apparaat.|
|serialNumber|Het serienummer van het apparaat. Dit geldt alleen voor iOS-apparaten.|
|imei|Het IMEI-nummer (15 decimalen: 14 cijfers plus een controlecijfer) of het IMEISV-nummer (16 cijfers) bevat informatie over de oorsprong, het model en het serienummer van het apparaat. De structuur van dit nummer wordt opgegeven in 3GPP TS 23.003. Dit geldt alleen voor apparaten met een simkaart.|
|udid|De unieke apparaat-id, die bestaat uit een reeks van 40 letters en cijfers. Deze id is specifiek voor iOS-apparaten.|
|meid|Dit is de mobiele-apparatuur-id. Deze id bestaat uit een wereldwijd uniek getal dat de identiteit aangeeft van een fysiek onderdeel van mobiele CDMA-apparatuur. De getalsnotatie wordt gedefinieerd door het 3GPP2-rapport S.R0048. In de praktijk kan dit nummer echter worden gezien als een IMEI-nummer, maar dan met hexadecimale cijfers. Een MEID bestaat uit 56 bits (14 hexadecimale cijfers). De id bestaat uit drie velden, met een 8-bits regionale code (RR), een 24-bits fabrikantcode en een 24-bits serienummer dat is toegewezen door de fabrikant.|
|osVersion|De versie van het besturingssysteem van het apparaat.
|model|Het apparaatmodel.
|manufacturer|De fabrikant van het apparaat.
|azureDeviceId|De apparaat-id nadat het apparaat aan de werkplek is toegevoegd met Azure AD. Dit is een lege GUID voor apparaten die niet zijn toegevoegd.|
|lastContactTimeUtc|De datum en tijd waarop het apparaat het laatst heeft ingecheckt bij de Intune-beheerservice.


## <a name="user-experience"></a>Gebruikerservaring

Wanneer een gebruiker toegang probeert te krijgen tot bronnen vanaf een niet-ingeschreven apparaat, krijgt deze de vraag om het apparaat te schrijven, zoals hieronder wordt weergegeven:

![Voorbeeld van een prompt voor inschrijving](../media/cisco-ise-user-iphone.png)

Wanneer de gebruiker ervoor kiest om het apparaat in te schrijven, wordt deze doorverwezen naar het Intune-inschrijvingsproces. De inschrijvingservaring die gebruikers hebben met Intune, wordt in de volgende onderwerpen beschreven:

- [Uw Android-apparaat inschrijven bij Intune](/intune/enduser/enroll-your-device-in-Intune-android)</br>
- [Uw iOS-apparaat inschrijven bij Intune](/intune/enduser/enroll-your-device-in-intune-ios)</br>
- [Uw Mac OS X-apparaat inschrijven bij Intune](/intune/enduser/enroll-your-device-in-intune-mac-os-x)</br>
- [Uw Windows-apparaat inschrijven bij Intune](/intune/enduser/enroll-your-device-in-intune-windows)</br>

Er is ook een [downloadbare reeks inschrijvingsinstructies](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a) die u kunt gebruiken om aangepaste richtlijnen te maken voor uw gebruikerservaring.


### <a name="see-also"></a>Zie tevens

[Cisco Identity Services Engine-beheerdershandleiding, release 2.1](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html#task_820C9C2A1A6647E995CA5AAB01E1CDEF)



<!--HONumber=Nov16_HO1-->


