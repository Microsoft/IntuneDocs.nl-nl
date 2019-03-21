---
title: API's voor onboarding van certificeringsinstanties van derden
titlesuffix: Microsoft Intune
description: Voeg de SCEP-GitHub-oplossing voor certificeringsinstanties (CA) van derden toe of integreer deze om SCEP-certificaten te verlenen aan apparaten in Microsoft Intune. Deze oplossing bevat Java- en C#-API's die validaties uitvoeren, meldingen over het al of niet slagen naar Intune verzenden en de SSL-socketfactory gebruiken tijdens de communicatie met Intune. Bekijk ook een overzicht van de stappen voor het testen van uw SCEP-CA-configuratie.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/06/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 274b512a8fa4b4026d26c8b5e6a704f51a0bef95
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57565788"
---
# <a name="use-apis-to-add-third-party-cas-for-scep-to-intune"></a>API's gebruiken om CA's van derden voor SCEP aan Intune toe te voegen

U kunt in Microsoft Intune certificeringsinstanties (CA) van derden toevoegen en deze CA's certificaten laten uitgeven en valideren met behulp van het Simple Certificate Enrollment Protocol (SCEP). [Certificeringsinstantie van derden toevoegen](certificate-authority-add-scep-overview.md) biedt een overzicht van deze functie en bevat een beschrijving van de Administrator-taken in Intune.

Er zijn ook enkele ontwikkelaarstaken waarbij een open source-bibliotheek wordt gebruikt die door Microsoft op GitHub.com is gepubliceerd. De bibliotheek bevat een API waarmee:

- Het SCEP-wachtwoord wordt gevalideerd dat dynamisch door Intune is gegenereerd
- Een melding naar Intune wordt verzonden over de certificaten die zijn gemaakt op apparaten die SCEP-aanvragen indienen

De SCEP-server van derden wordt met deze API geïntegreerd met de Intune SCEP-beheeroplossing voor MDM-apparaten. De bibliotheek abstraheert aspecten zoals verificatie, servicelocatie en de ODATA Intune-service-API van de gebruikers.

## <a name="scep-management-solution"></a>SCEP-beheeroplossing

![Hoe SCEP van certificeringsinstanties van derden wordt geïntegreerd met Microsoft Intune](./media/scep-certificate-vendor-integration.png)

Administrators kunnen met Intune SCEP-profielen maken en deze vervolgens toewijzen aan MDM-apparaten. De SCEP-profielen bevatten parameters, zoals:

- De URL van de SCEP-server
- Het vertrouwde basiscertificaat van de certificeringsinstantie
- Certificaatkenmerken, en meer

Aan apparaten die met Intune worden ingecheckt, wordt het SCEP-profiel toegewezen. Vervolgens worden deze parameters hierop geconfigureerd. In Intune wordt een dynamisch gegenereerd SCEP-controlewachtwoord gemaakt dat wordt toegewezen aan het apparaat.

De controle bevat:

- Het dynamisch gegenereerde controlewachtwoord
- Informatie over de parameters die worden verwacht in de aanvraag voor certificaatondertekening (CSR, certificate signing request) die het apparaat naar de SCEP-server verzendt
- De vervaltijd van de controle

Intune versleutelt de gegevens, ondertekent de versleutelde blob en verpakt deze gegevens vervolgens in het SCEP-controlewachtwoord.

Apparaten die met de SCEP-server communiceren om een certificaat aan te vragen, leveren vervolgens dit SCEP-controlewachtwoord. De SCEP-server stuurt de CSR en het versleutelde SCEP-controlewachtwoord voor validatie naar Intune.  Het controlewachtwoord en de CSR moeten worden gevalideerd voordat de SCEP-server een certificaat aan het apparaat kan verlenen. Bij het valideren van de SCEP-controle vinden de volgende controles plaats:


- Validatie van de handtekening van de versleutelde blob
- Validatie of de vraag niet is verlopen
- Validatie of het profiel het apparaat nog steeds als doel heeft
- Validatie of de certificaateigenschappen die in de aanvraag voor certificaatondertekening door het apparaat zijn aangevraagd, overeenkomen met de verwachte waarden

De SCEP-beheeroplossing biedt ook rapporten. Een administrator kan informatie krijgen over de implementatiestatus van het SCEP-profiel en over de certificaten die zijn verleend aan de apparaten.

## <a name="integrate-with-intune"></a>Integreren met Intune

De code voor de bibliotheek die moet worden geïntegreerd met de Intune SCEP, is beschikbaar voor downloaden in de [GitHub-opslagplaats Microsoft/Intune-Resource-Access](https://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation).

De volgende stappen moeten worden uitgevoerd om de bibliotheek in uw producten te integreren. Voor deze stappen is kennis over het werken met GitHub-opslagplaatsen, en het maken van oplossingen en projecten in Visual Studio vereist.

1. Registreren om meldingen vanuit de opslagplaats te ontvangen
2. De opslagplaats klonen of downloaden
3. Naar de benodigde bibliotheekimplementatie in de map `\src\CsrValidation` gaan (https://github.com/Microsoft/Intune-Resource-Access/tree/develop/src/CsrValidation)
4. De bibliotheek met behulp van de instructies in het Leesmij-bestand maken
5. De bibliotheek opnemen in het project waarmee uw SCEP-server wordt gemaakt
6. Voer de volgende taken uit op de SCEP-server:

    - Sta de administrator toe de [Azure-app-id, Azure-app-sleutel en tenant-id](#onboard-scep-server-in-azure) (in dit artikel) te configureren die door de bibliotheek voor verificatie worden gebruikt. Administrators moeten de Azure-app-sleutel kunnen bijwerken.
    - SCEP-aanvragen identificeren die een door Intune gegenereerd SCEP-wachtwoord bevatten
    - De bibliotheek **API voor aanvraag valideren** gebruiken om door Intune gegenereerde SCEP-wachtwoorden te valideren
    - Gebruik de API's voor bibliotheekmeldingen om Intune te informeren over certificaten die zijn uitgegeven voor SCEP-aanvragen die de door Intune gegenereerde SCEP-wachtwoorden bevatten. Informeer Intune ook over fouten die kunnen optreden bij het verwerken van deze SCEP-aanvragen.
    - Controleer of de server voldoende gegevens vastlegt om administrators te helpen problemen op te lossen

7. Voltooi [het testen van de integratie](#integration-testing) (in dit artikel) en los eventuele problemen op
8. Bied de klant schriftelijke richtlijnen waarin het volgende wordt uitgelegd:

    - Hoe u onboarding van de SCEP-server voor Azure Portal uitvoert
    - Hoe de Azure-app-id en Azure-app-sleutel moeten worden opgehaald die nodig zijn om de bibliotheek te configureren

### <a name="onboard-scep-server-in-azure"></a>Onboarding van de SCEP-server voor Azure uitvoeren

Voor de SCEP-server is een Azure-app-id, Azure-app-sleutel en tenant-id nodig om te kunnen worden geverifieerd bij Intune. Ook moet de SCEP-server worden gemachtigd voor toegang tot de Intune-API.

De administrator van de SCEP-server kan deze gegevens verkrijgen door zich aan te melden bij Azure Portal, de toepassing te registreren, de toepassing de bevoegdheid **Microsoft Intune API\SCEP-vraag valideren** te geven, een sleutel voor de toepassing te maken en vervolgens de app-id, app-sleutel en tenant-id te downloaden.

Zie [Portal gebruiken om een AAD-toepassing en service-principal te maken voor toegang tot resources](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal) voor instructies over het registreren van een toepassing en het ophalen van id's en sleutels.

### <a name="java-library-api"></a>Java-bibliotheek-API

De Java-bibliotheek wordt geïmplementeerd als een Maven-project dat de bijbehorende afhankelijkheden bij het maken ophaalt. De API wordt geïmplementeerd in de naamruimte `com.microsoft.intune.scepvalidation` door de klasse `IntuneScepServiceClient`.

#### <a name="intunescepserviceclient-class"></a>IntuneScepServiceClient-klasse

De klasse `IntuneScepServiceClient` bevat de methoden die door de SCEP-service worden gebruikt om SCEP-wachtwoorden te valideren, om Intune te informeren over certificaten die zijn gemaakt, en om eventuele fouten weer te geven.

##### <a name="intunescepserviceclient-constructor"></a>IntuneScepServiceClient-constructor

Handtekening:

```java
IntuneScepServiceClient(
    Properties configProperties)
```

Beschrijving:

Hiermee wordt een instantie van een `IntuneScepServiceClient`-object gemaakt en wordt de instantie geconfigureerd.

Parameters:

    - configProperties    Eigenschappenobject met clientconfiguratiegegevens

De configuratie moet de volgende eigenschappen bevatten:

    - AAD_APP_ID=De Azure-app-id die is verkregen tijdens onboarding
    - AAD_APP_KEY=De Azure-app-sleutel die is verkregen tijdens onboarding
    - TENANT=De tenant-id die is verkregen tijdens onboarding
    - PROVIDER_NAME_AND_VERSION=Informatie die wordt gebruikt om uw product en de versie ervan te identificeren
    
Als voor uw oplossing een proxy is vereist, al dan niet met verificatie, kunt u de volgende eigenschappen toevoegen:

    - PROXY_HOST=De host waarop de proxy wordt gehost.
    - PROXY_PORT=De poort waarnaar de proxy luistert.
    - PROXY_USER=De gebruikersnaam die moet worden gebruikt als de proxy basisverificatie gebruikt.
    - PROXY_USER=Het wachtwoord dat moet worden gebruikt als de proxy basisverificatie gebruikt.

Genereert:

    - IllegalArgumentException    Gegenereerd als de constructor wordt uitgevoerd zonder het juiste eigenschappenobject.

> [!IMPORTANT]
> Het wordt aanbevolen een instantie van deze klasse te maken en deze te gebruiken om meerdere SCEP-aanvragen te verwerken. In dat geval is er minder overhead nodig omdat verificatietokens en servicelocatiegegevens in de cache worden opgeslagen.

**Beveiligingsopmerkingen**  
De implementeerder van de SCEP-server moet de gegevens die in de configuratie-eigenschappen worden ingevoerd, beveiligen tegen misbruik en openbaarmaking. Het is raadzaam de juiste ACL's en versleuteling te gebruiken om de gegevens te beveiligen.

##### <a name="validaterequest-method"></a>ValidateRequest-methode

Handtekening:

```java
void ValidateRequest(
    String transactionId,
    String certificateRequest)
```

Beschrijving:

Hiermee wordt een SCEP-certificaataanvraag gevalideerd.

Parameters:

    - transactionId         De SCEP-transactie-id
    - certificateRequest    DER-gecodeerde PKCS #10-certificaataanvraag met Base64-gecodeerde tekenreeks

Genereert:

    - IllegalArgumentException      Gegenereerd indien aangeroepen met een ongeldige parameter
    - IntuneScepServiceException    Gegenereerd als is vastgesteld dat de certificaataanvraag ongeldig is
    - Exception                     Gegenereerd als er een onverwachte fout wordt aangetroffen

> [!IMPORTANT]
> Uitzonderingen die door deze methode worden gegenereerd, moeten worden vastgelegd door de server. De `IntuneScepServiceException`-eigenschappen bevatten gedetailleerde informatie over de reden waarom de validatie van de certificaataanvraag is mislukt.

**Beveiligingsopmerkingen**  

  - Als deze methode een uitzondering genereert, mag de SCEP-server **geen** certificaat aan de client verlenen.
  - Het mislukken van de validatie van een SCEP-certificaataanvraag kan duiden op een probleem in de Intune-infrastructuur. Ook kan dit een teken zijn dat een aanvaller een certificaat probeert te krijgen.

##### <a name="sendsuccessnotification-method"></a>SendSuccessNotification-methode

Handtekening:

```java
void SendSuccessNotification(
    String transactionId,
    String certificateRequest,
    String certThumbprint,
    String certSerialNumber,
    String certExpirationDate,
    String certIssuingAuthority)
```

Beschrijving:

Hiermee wordt Intune geïnformeerd dat een certificaat is gemaakt als onderdeel van het verwerken van een SCEP-aanvraag.

Parameters:

    - transactionId           De SCEP-transactie-id
    - certificateRequest      DER-gecodeerde PKCS #10-certificaataanvraag, met Base64-gecodeerde tekenreeks
    - certThumprint           Vingerafdruk van het ingerichte certificaat
    - certSerialNumber        Serienummer van het ingerichte certificaat
    - certExpirationDate      Vervaldatum van het ingerichte certificaat. De tekenreeks met de datum en tijd moet worden opgemaakt als web-UTC-tijd (jjjj-MM-DDThh:mm:ss.sssTZD) ISO 8601.
    - certIssuingAuthority    De naam van de instantie die het certificaat heeft uitgegeven

Genereert:

    - IllegalArgumentException      Gegenereerd indien aangeroepen met een ongeldige parameter
    - IntuneScepServiceException    Gegenereerd als is vastgesteld dat de certificaataanvraag ongeldig is
    - Exception                     Gegenereerd als er een onverwachte fout wordt aangetroffen

> [!IMPORTANT]
> Uitzonderingen die door deze methode worden gegenereerd, moeten worden vastgelegd door de server. De `IntuneScepServiceException`-eigenschappen bevatten gedetailleerde informatie over de reden waarom de validatie van de certificaataanvraag is mislukt.

**Beveiligingsopmerkingen**

  - Als deze methode een uitzondering genereert, mag de SCEP-server **geen** certificaat aan de client verlenen.
  - Het mislukken van de validatie van een SCEP-certificaataanvraag kan duiden op een probleem in de Intune-infrastructuur. Ook kan dit een teken zijn dat een aanvaller een certificaat probeert te krijgen.

##### <a name="sendfailurenotification-method"></a>SendFailureNotification-methode

Handtekening:

```java
void SendFailureNotification(
    String transactionId,
    String certificateRequest,
    long  hResult,
    String errorDescription)
```

Beschrijving:

Hiermee wordt Intune geïnformeerd dat er een fout is opgetreden tijdens het verwerken van een SCEP-aanvraag. Deze methode mag niet worden aangeroepen voor uitzonderingen die door de methoden van deze klasse zijn gegenereerd.

Parameters:

    - transactionId         De SCEP-transactie-id
    - certificateRequest    DER-gecodeerde PKCS #10-certificaataanvraag met Base64-gecodeerde tekenreeks
    - hResult               Win32-foutcode waarmee de opgetreden fout het beste kan worden beschreven. Zie [Win32-foutcodes](https://msdn.microsoft.com/library/cc231199.aspx)
    - errorDescription      Beschrijving van de opgetreden fout

Genereert:

    - IllegalArgumentException      Gegenereerd indien aangeroepen met een ongeldige parameter
    - IntuneScepServiceException    Gegenereerd als is vastgesteld dat de certificaataanvraag ongeldig is
    - Exception                     Gegenereerd als er een onverwachte fout wordt aangetroffen

> [!IMPORTANT]
> Uitzonderingen die door deze methode worden gegenereerd, moeten worden vastgelegd door de server. De `IntuneScepServiceException`-eigenschappen bevatten gedetailleerde informatie over de reden waarom de validatie van de certificaataanvraag is mislukt.

**Beveiligingsopmerkingen**

  - Als deze methode een uitzondering genereert, mag de SCEP-server **geen** certificaat aan de client verlenen.
  - Het mislukken van de validatie van een SCEP-certificaataanvraag kan duiden op een probleem in de Intune-infrastructuur. Ook kan dit een teken zijn dat een aanvaller een certificaat probeert te krijgen.

##### <a name="setsslsocketfactory-method"></a>SetSslSocketFactory-methode

Handtekening:

```java
void SetSslSocketFactory(
    SSLSocketFactory factory)
```

Beschrijving:

Gebruik deze methode om de client te informeren dat deze de opgegeven SSL-socketfactory (in plaats van de standaardinstelling) moet gebruiken bij de communicatie met Intune.

Parameters:

    - factory    De SSL-socketfactory die de client voor HTTPS-aanvragen moet gebruiken

Genereert:

    - IllegalArgumentException    Gegenereerd indien aangeroepen met een ongeldige parameter

> [!NOTE]
> Wanneer de SSL-socketfactory moet worden ingesteld, moet dit worden gedaan voordat de andere methoden van deze klasse worden uitgevoerd.

## <a name="integration-testing"></a>Integratie testen

Valideren en testen of uw oplossing correct is geïntegreerd met Intune, is vereist. Hieronder vindt u een overzicht van de stappen:

1. Stel een [Intune-proefaccount](account-sign-up.md) in.
2. Voer onboarding van de [SCEP-server voor Azure Portal](#onboard-scep-server-in-azure) (in dit artikel) uit.
3. [Configureer de SCEP-server](certificates-scep-configure.md) met de id's en sleutel die zijn gemaakt bij de onboarding van uw SCEP-server.
4. [Registreer apparaten](device-enrollment.md) om de scenario's in de [matrix voor het testen van scenario's](https://github.com/Microsoft/Intune-Resource-Access/blob/develop/src/CsrValidation/doc/TestMatrix.csv) te testen.
5. [Maak een profiel voor een vertrouwd basiscertificaat](certificates-scep-configure.md) voor uw testcertificeringsinstantie.
6. Maak SCEP-profielen om de scenario's in de [matrix voor het testen van scenario's](https://github.com/Microsoft/Intune-Resource-Access/blob/develop/src/CsrValidation/doc/TestMatrix.csv) te testen.
7. [Wijs de profielen toe](device-profile-assign.md) aan gebruikers die hun apparaten hebben geregistreerd.
8. Wacht tot de apparaten met Intune zijn gesynchroniseerd. Of [synchroniseer de apparaten](device-sync.md) handmatig.
9. Controleer of het vertrouwde basiscertificaat en de SCEP-[profielen op de apparaten zijn geïmplementeerd](device-profile-monitor.md).
10. Controleer of het vertrouwde basiscertificaat is geïnstalleerd op alle apparaten.
11. Controleer of de SCEP-certificaten voor de toegewezen profielen zijn geïnstalleerd op alle apparaten.
12. Controleer of de eigenschappen van de geïnstalleerde certificaten overeenkomen met de eigenschappen die zijn ingesteld in het SCEP-profiel.
13. Controleer of de uitgegeven certificaten juist worden vermeld in de Intune-console

## <a name="see-also"></a>Zie tevens

- [Overzicht van het toevoegen van certificeringsinstanties van derden](certificate-authority-add-scep-overview.md)
- [Intune instellen](setup-steps.md)
- [Apparaatinschrijving](device-enrollment.md)
- [SCEP-certificaatprofielen configureren](certificates-scep-configure.md#create-a-scep-certificate-profile) (de installatie van Microsoft NDES Server\Connector wordt voor dit scenario niet gebruikt)
