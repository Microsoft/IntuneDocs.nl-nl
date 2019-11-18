---
title: SCEP-certificaatprofielen gebruiken met Microsoft Intune - Azure | Microsoft Docs
description: Maak Simple Certificate Enrollment Protocol (SCEP)-certificaatprofielen en wijs deze toe met Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5a3cfcc4ac0c5125324102c55dc7bc887006df6b
ms.sourcegitcommit: b5e719fb507b1bc4774674e76c856c435e69f68c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/08/2019
ms.locfileid: "73801428"
---
# <a name="create-and-assign-scep-certificate-profiles-in-intune"></a>SCEP-certificaatprofielen maken en toewijzen in Intune

Nadat u [uw infrastructuur hebt geconfigureerd](certificates-scep-configure.md) voor ondersteuning van SCEP-certificaten (Simple Certificate Enrollment Protocol), kunt u SCEP-certificaatprofielen maken en deze vervolgens toewijzen aan gebruikers en apparaten in Intune.

> [!IMPORTANT]  
> Voordat u SCEP-certificaatprofielen maakt, moeten u ervoor zorgen dat apparaten die gebruik gaan maken van een SCEP-certificaatprofiel, uw vertrouwde basiscertificeringsinstantie (basis-CA) vertrouwen. Gebruik een *vertrouwd certificaatprofiel* in Intune om het vertrouwde basis-CA-certificaat in te richten voor gebruikers en apparaten. Zie [Het vertrouwde basis-CA-certificaat exporteren](certificates-configure.md#export-the-trusted-root-ca-certificate) en [Profielen voor vertrouwde certificaten maken](certificates-configure.md#create-trusted-certificate-profiles) in *Certificaten voor verificatie gebruiken in Intune* voor meer informatie over het vertrouwde certificaatprofiel.


## <a name="create-a-scep-certificate-profile"></a>Een SCEP-certificaatprofiel maken

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecteer **Apparaten** > **Configuratieprofiel** > **Profiel maken**.

3. Voer de volgende eigenschappen in:

4. Voer een **naam** en een **beschrijving** in voor het SCEP-certificaatprofiel.

5. Selecteer in de vervolgkeuzelijst **Platform** een [ondersteund apparaatplatform](certificates-configure.md#supported-platforms-and-certificate-profiles) voor dit SCEP-certificaat.

6. Selecteer in de vervolgkeuzelijst **Profieltype** de optie **SCEP-certificaat**.  

   Voor het **Android Enterprise**-platform is het *Profieltype* onderverdeeld in twee categorieën: *Alleen apparaateigenaar* en *Alleen werkprofiel*. Zorg ervoor dat u het juiste SCEP-certificaatprofiel selecteert voor de apparaten die u beheert.  

   SCEP-certificaatprofielen voor het profiel *Alleen apparaateigenaar* hebben de volgende beperkingen:

   1. Hierbij worden de volgende variabelen niet ondersteund:

      - CN={{OnPrem_Distinguished_Name}}
      - CN={{onPremisesSamAccountName}}

   2. Certificaatrapportage is onder Bewaking niet beschikbaar voor de SCEP-certificaatprofielen voor apparaateigenaar.

   3. U kunt Intune niet gebruiken om certificaten in te trekken die zijn ingericht door SCEP-certificaatprofielen voor eigenaren van apparaten. U kunt het intrekken beheren via een extern proces of rechtstreeks met de certificeringsinstantie. 

7. Selecteer **Instellingen** en voltooi de volgende configuraties:

   - **Certificaattype**:

     *(Van toepassing op:  Android, Android Enterprise, iOS, macOS, Windows 8.1 en later en Windows 10 en later.)*

     Selecteer een type op basis van de wijze waarop u het certificaatprofiel wilt gebruiken:

     - **Gebruiker**: *Gebruiker*-certificaten kunnen zowel gebruikers- als apparaatkenmerken in het onderwerp ende SAN van het certificaat bevatten.  
     - **Apparaat**:  *Apparaat*-certificaten kunnen alleen apparaatkenmerken in het onderwerp en SAN van het certificaat bevatten.

       Gebruik **Apparaat** voor scenario's als apparaten zonder gebruiker, zoals kiosken, of voor Windows-apparaten. Op Windows-apparaten wordt het certificaat in het certificaatarchief van de lokale computer geplaatst.

   - **Indeling van de onderwerpnaam**:

     Selecteer hoe de onderwerpnaam in de certificaataanvraag automatisch wordt gemaakt met Intune. De opties voor de indeling van de onderwerpnaam zijn afhankelijk van het certificaattype dat u selecteert: **Gebruiker** of **Apparaat**.

     > [!NOTE]
     > Er is een [bekend probleem](#avoid-certificate-signing-requests-with-escaped-special-characters) bij het gebruik van SCEP om certificaten op te halen wanneer in de onderwerpnaam in de resulterende aanvraag voor certificaatondertekening (Certificate Signing Request, CSR) een van de volgende tekens staat na een escape-teken (een backslash \\):
     > - \+
     > - ;
     > - ,
     > - =

     - **Certificaattype Gebruiker**

       Indelingsopties voor de *Indeling van de onderwerpnaam* zijn:

       - **Niet geconfigureerd**
       - **Algemene naam**
       - **Algemene naam en e-mailadres**
       - **Algemene naam als e-mailadres**
       - **IMEI (International Mobile Equipment Identity)**
       - **Serienummer**
       - **Aangepast**: Wanneer u deze optie selecteert, wordt het tekstvak **Aangepast** ook weergegeven. Met dit veld kunt u een onderwerpnaam invoeren in een aangepaste indeling, inclusief variabelen. Aangepaste indeling ondersteunt twee variabelen: **Algemene naam (CN)** en **E-mail (E)** . **Algemene naam (CN)** kan worden ingesteld op een van de volgende variabelen:

         - **CN={{UserName}}** : De user principal name van de gebruiker, bijvoorbeeld janedoe@contoso.com.
         - **CN={{AAD_Device_ID}}** : Een id die wordt toegewezen wanneer u een apparaat in Azure Active Directory (AD) registreert. Deze id wordt doorgaans gebruikt voor verificatie met Azure AD.
         - **CN={{SERIALNUMBER}}** : Het unieke serienummer (SN) dat doorgaans wordt gebruikt door de fabrikant om een apparaat te identificeren.
         - **CN={{IMEINumber}}** : Het unieke nummer van de International Mobile Equipment Identity (IMEI) dat wordt gebruikt om een mobiele telefoon te identificeren.
         - **CN={{OnPrem_Distinguished_Name}}** : Een reeks RDN's (Relative Distinguished Name), gescheiden door komma's, zoals *CN=Jane Doe,OU=UserAccounts,DC=corp,DC=contoso,DC=com*.

           Als u de variabele *{{OnPrem_Distinguished_Name}}* wilt gebruiken, moet u het gebruikerskenmerk *onpremisesdistinguishedname* met behulp van [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) synchroniseren met uw Azure AD.

         - **CN={{onPremisesSamAccountName}}** : Beheerders kunnen het kenmerk samAccountName van Active Directory met behulp van Azure AD Connect synchroniseren met Azure AD in een kenmerk met de naam *onPremisesSamAccountName*. Deze variabele kan in Intune worden vervangen als onderdeel van een aanvraag voor certificaatuitgifte in het onderwerp van een certificaat. Het kenmerk samAccountName is de aanmeldingsnaam van de gebruiker die wordt gebruikt ter ondersteuning van clients en servers van een oudere versie dan Windows 2000. De indeling voor de aanmeldingsnaam van de gebruiker is: *DomainName\testUser* of alleen *testUser*.

            Als u de variabele *{{onPremisesSamAccountName}}* wilt gebruiken, moet u het gebruikerskenmerk *onPremisesSamAccountName* met behulp van [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) synchroniseren met uw Azure AD.

         Door een combinatie van een of meer van deze variabelen en statische tekenreeksen te gebruiken, kunt u een aangepaste indeling voor de naam van een certificaathouder maken, bijvoorbeeld:  
         - **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US**

         Dat voorbeeld bevat een indeling van de onderwerpnaam waarin gebruik wordt gemaakt van de variabelen CN en E, plus tekenreeksen voor de waarden Organizational Unit, Organization, Location, State en Country. [De functie CertStrToName](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) beschrijft deze functie en de ondersteunde tekenreeksen.

      - **Certificaattype Apparaat**

        Indelingsopties voor de Indeling van de onderwerpnaam zijn de volgende variabelen:

        - **{{AAD_Device_ID}}**
        - **{{Device_Serial}}**
        - **{{Device_IMEI}}**
        - **{{SerialNumber}}**
        - **{{IMEINumber}}**
        - **{{AzureADDeviceId}}**
        - **{{WiFiMacAddress}}**
        - **{{IMEI}}**
        - **{{DeviceName}}**
        - **{{FullyQualifiedDomainName}}** *(Alleen van toepassing op Windows-apparaten en apparaten die aan een domein zijn toegevoegd)*
        - **{{MEID}}**

        U kunt deze variabelen opgeven in het tekstvak, gevolgd door de tekst voor de variabele. De algemene naam voor een apparaat met de naam *Device1* kan bijvoorbeeld worden toegevoegd als **CN={{DeviceName}}Device1**.

        > [!IMPORTANT]
        > - Plaats bij het opgeven van een variabele de naam van de variabele tussen accolades {}, zoals in het voorbeeld te zien is, om fouten te voorkomen.  
        > - Apparaateigenschappen die worden gebruikt in het *onderwerp* of de *SAN* van een apparaatcertificaat, zoals **IMEI**, **SerialNumber** en **FullyQualifiedDomainName**, zijn eigenschappen die kunnen worden vervalst door een persoon die toegang tot het apparaat heeft.
        > - Een apparaat moet alle variabelen ondersteunen die zijn opgegeven in een certificaatprofiel, anders kan het profiel niet worden geïnstalleerd op het apparaat.  Als bijvoorbeeld **{{IMEI}}** wordt gebruikt in de onderwerpnaam van een SCEP-profiel en deze variabele wordt toegewezen aan een apparaat dat geen IMEI-nummer heeft, mislukt de installatie van het profiel.

   - **Alternatieve naam voor het onderwerp**: Selecteer hoe Intune de alternatieve naam voor onderwerp (SAN) automatisch moet maken in de certificaataanvraag. De opties voor de SAN zijn afhankelijk van het certificaattype dat u hebt geselecteerd: **Gebruiker** of **Apparaat**.

      - **Certificaattype Gebruiker**

        Selecteer een van de beschikbare kenmerken:

        - **E-mailadres**
        - **User Principal Name (UPN)**

        Gebruikerscertificaattypen kunnen bijvoorbeeld de User Principal Name (UPN) bevatten in de alternatieve naam voor onderwerp. Als een clientcertificaat wordt gebruikt om een Network Policy Server te verifiëren, stelt u de alternatieve naam van het onderwerp op de UPN in.

      - **Certificaattype Apparaat**

        Gebruik de vervolgkeuzelijst **Kenmerk** om een kenmerk te selecteren, wijs een **Waarde** toe en selecteer **Toevoegen** voor toevoeging aan het certificaatprofiel. U kunt meerdere waarden toevoegen door extra kenmerken te selecteren.

        Beschikbare kenmerken zijn:

        - **E-mailadres**
        - **User Principal Name (UPN)**
        - **DNS**

        Bij het certificaattype *Apparaat* kunt u de volgende variabelen van het apparaatcertificaat gebruiken voor de waarde:

        - **{{AAD_Device_ID}}**
        - **{{Device_Serial}}**
        - **{{Device_IMEI}}**
        - **{{SerialNumber}}**
        - **{{IMEINumber}}**
        - **{{AzureADDeviceId}}**
        - **{{WiFiMacAddress}}**
        - **{{IMEI}}**
        - **{{DeviceName}}**
        - **{{FullyQualifiedDomainName}}**
        - **{{MEID}}**

        Als u een waarde wilt opgeven voor een kenmerk, neemt u de naam van de variabele op tussen accolades, gevolgd door de tekst voor die variabele. Zo kan bijvoorbeeld een waarde voor het kenmerk DNS worden toegevoegd, **{{AzureADDeviceId}}.domain.com**, waarbij *.domain.com* de tekst is. Een e-mailadres voor een gebruiker met de naam *User1* kan worden weergegeven als {{FullyQualifiedDomainName}}User1@Contoso.com.

        > [!IMPORTANT]
        > - Wanneer u een variabele voor een apparaatcertificaat gebruikt, plaatst u de variabele tussen accolades { }.
        > - Gebruik geen accolades **{}** , verticale streepjes **|** en puntkomma's **;** in de tekst die volgt op de variabele.
        > - Apparaateigenschappen die worden gebruikt in het *onderwerp* of de *SAN* van een apparaatcertificaat, zoals **IMEI**, **SerialNumber** en **FullyQualifiedDomainName**, zijn eigenschappen die kunnen worden vervalst door een persoon die toegang tot het apparaat heeft.
        > - Een apparaat moet alle variabelen ondersteunen die zijn opgegeven in een certificaatprofiel, anders kan het profiel niet worden geïnstalleerd op het apparaat.  Als bijvoorbeeld **{{IMEI}}** wordt gebruikt in de SAN van een SCEP-profiel en deze variabele wordt toegewezen aan een apparaat dat geen IMEI-nummer heeft, mislukt de installatie van het profiel.

   - **Geldigheidsduur van certificaat**:

     U kunt een waarde invoeren die lager is dan de geldigheidsperiode in de certificaatsjabloon, maar niet hoger. Als u de certificaatsjabloon hebt geconfigureerd voor [ondersteuning van een aangepaste waarde die via de Intune-console kan worden ingesteld](certificates-scep-configure.md#modify-the-validity-period-of-the-certificate-template), gebruikt u deze instelling om de resterende tijd op te geven voordat het certificaat verloopt.

     Als de geldigheidsperiode van het certificaat in de certificaatsjabloon bijvoorbeeld twee jaar is, kunt u wel één jaar, maar niet vijf jaar opgeven. De waarde moet ook lager zijn dan de resterende geldigheidsperiode van het certificaat van de verlenende CA.

   - **Sleutelarchiefprovider (KSP)** :

     *(Van toepassing op:  Windows 8.1 en later, en Windows 10 en later)*

     Geef op waar de sleutel voor het certificaat wordt opgeslagen. Kies uit de volgende waarden:

     - **Registeren in de sleutelarchiefprovider voor TPM (Trusted Platform Module) indien TPM aanwezig is, anders registreren in de sleutelarchiefprovider voor software**
     - **Registreren in de sleutelarchiefprovider voor TPM (Trusted Platform Module), anders mislukt**
     - **Registreren bij Passport, anders niet uitvoeren (Windows 10 en hoger)**
     - **Registreren in sleutelarchiefprovider voor software**

   - **Sleutelgebruik**:

     Selecteer sleutelgebruikopties voor het certificaat:

     - **Digitale handtekening**: Sta sleuteluitwisseling alleen toe als de sleutel wordt beveiligd met een digitale handtekening.
     - **Sleutelcodering**: Sta sleuteluitwisseling alleen toe als de sleutel is versleuteld.

   - **Sleutelgrootte (bits)** :

     Selecteer het aantal bits in de sleutel.

   - **Hash-algoritme**:

     *(Van toepassing op Android, Android Enterprise, Windows Phone 8.1, Windows 8.1 en later en Windows 10 en later)*

     Selecteer een van de beschikbare typen hash-algoritme om met dit certificaat te gebruiken. Selecteer het sterkste beveiligingsniveau dat door de verbindende apparaten wordt ondersteund.

   - **Basiscertificaat**:

     Selecteer het *vertrouwde certificaatprofiel* dat u eerder hebt geconfigureerd en hebt toegewezen aan de betreffende gebruikers en apparaten voor dit SCEP-certificaatprofiel. Het vertrouwde certificaatprofiel wordt gebruikt om het vertrouwde basis-CA-certificaat in te richten voor gebruikers en apparaten. Zie [Uw vertrouwde basis-CA-certificaat exporteren](certificates-configure.md#export-the-trusted-root-ca-certificate) en [Profielen voor vertrouwde certificaten maken](certificates-configure.md#create-trusted-certificate-profiles) in *Certificaten voor verificatie gebruiken in Intune* voor meer informatie over het vertrouwde certificaatprofiel. Als u een basiscertificeringsinstantie en een verlenende certificeringsinstantie hebt, selecteert u het vertrouwde basiscertificaatprofiel dat is gekoppeld aan de verlenende certificeringsinstantie.

   - **Uitgebreide-sleutelgebruik**:

     Voeg waarden toe voor het beoogde gebruik van het certificaat. In de meeste gevallen vereist het certificaat *clientverificatie* zodat de gebruiker of het apparaat bij een server kan worden geverifieerd. U kunt zo nodig ook extra sleutelgebruik toevoegen.

   - **Drempelwaarde voor verlenging (%)** :

     Geef het percentage van de levensduur van het certificaat op dat resteert voordat het apparaat verlenging van het certificaat aanvraagt. Als u bijvoorbeeld 20 invoert, wordt geprobeerd het certificaat te vernieuwen wanneer het certificaat voor 80 procent is verlopen. Het vernieuwen wordt steeds opnieuw geprobeerd tot het vernieuwen is voltooid. Bij het vernieuwen wordt een nieuw certificaat gegenereerd dat een nieuw paar openbare/persoonlijke sleutel oplevert.

   - **URL's van SCEP-server**:

     Voer een of meer URL's in voor de NDES-servers die certificaten via SCEP verlenen. Voer bijvoorbeeld iets in als *https://ndes.contoso.com/certsrv/mscep/mscep.dll* . U kunt indien nodig aanvullende SCEP-URL's voor taakverdeling toevoegen, omdat URL's willekeurig op het apparaat met het profiel worden gepusht. Als een van de SCEP-servers niet beschikbaar is, mislukt de SCEP-aanvraag. Dan wordt de volgende keer dat er apparaten worden ingecheckt, de certificaataanvraag mogelijk uitgevoerd op dezelfde niet-actieve server.

8. Selecteer **OK** en selecteer vervolgens **Maken**. Het profiel is gemaakt en wordt weergegeven in de lijst *Apparaatconfiguratie - Profielen*.

### <a name="avoid-certificate-signing-requests-with-escaped-special-characters"></a>Aanvragen voor certificaatondertekening met speciale tekens met escape-teken vermijden

Er is een bekend probleem met SCEP- en PKCS-certificaataanvragen die een onderwerpnaam (CN) bevatten met een of meer van de volgende speciale tekens na een escape-teken. Namen van onderwerpen die een van de speciale tekens bevatten als resultaat van een escape-teken in een CSR met een onjuiste onderwerpnaam. Een onjuiste onderwerpnaam resulteert in het mislukken van de Intune-validatie van de SCEP-controle en er wordt geen certificaat uitgegeven.

Dit gaat over de volgende speciale tekens:
- \+
- ,
- ;
- =

Wanneer de onderwerpnaam een van deze speciale tekens bevat, moet u een van de volgende opties gebruiken om deze beperking te omzeilen:

- Plaats aanhalingstekens om de CN-waarde die het speciale teken bevat.  
- Verwijder het speciale teken uit de CN-waarde.

**Bijvoorbeeld**: u hebt een onderwerpnaam die wordt weergegeven als *Test User (TestCompany, LLC)* .  Een CSR waarin de CN een komma bevat tussen *TestCompany* en *LLC*, leidt tot problemen.  Deze problemen kunnen worden vermeden door aanhalingstekens te plaatsen rond de hele CN of door de komma te verwijderen tussen *TestCompany* en *LLC*:

- **Aanhalingstekens toevoegen**: *CN=* ”Test User (TestCompany, LLC)”,OU=UserAccounts,DC=corp,DC=contoso,DC=com*
- **De komma verwijderen**: *CN=Test User (TestCompany LLC),OU=UserAccounts,DC=corp,DC=contoso,DC=com*

 Pogingen om de komma te escapen met behulp van een backslash-teken mislukken, met een fout in de CRP-logboeken:
 
- **Komma met escape-teken**: *CN=Test User (TestCompany\\, LLC),OU=UserAccounts,DC=corp,DC=contoso,DC=com*

De fout is vergelijkbaar met de volgende foutmelding:

```
Subject Name in CSR CN="Test User (TESTCOMPANY\, LLC),OU=UserAccounts,DC=corp,DC=contoso,DC=com" and challenge CN=Test User (TESTCOMPANY\, LLC),OU=UserAccounts,DC=corp,DC=contoso,DC=com do not match  

  Exception: System.ArgumentException: Subject Name in CSR and challenge do not match

   at Microsoft.ConfigurationManager.CertRegPoint.ChallengeValidation.ValidationPhase3(PKCSDecodedObject pkcsObj, CertEnrollChallenge challenge, String templateName, Int32 skipSANCheck)

Exception:    at Microsoft.ConfigurationManager.CertRegPoint.ChallengeValidation.ValidationPhase3(PKCSDecodedObject pkcsObj, CertEnrollChallenge challenge, String templateName, Int32 skipSANCheck)

   at Microsoft.ConfigurationManager.CertRegPoint.Controllers.CertificateController.VerifyRequest(VerifyChallengeParams value
```

## <a name="assign-the-certificate-profile"></a>Het certificaatprofiel toewijzen

Wijs SCEP-certificaatprofielen op dezelfde manier toe als u [apparaatprofielen implementeert](../configuration/device-profile-assign.md) voor andere doeleinden. Denk echter na over het volgende voordat u verdergaat:

- Wanneer u SCEP-certificaatprofielen aan groepen toewijst, wordt het bestand met het vertrouwde basis-CA-certificaat (zoals gespecificeerd in het *vertrouwde CA-certificaatprofiel*) op het apparaat geïnstalleerd. Het apparaat gebruikt het SCEP-certificaatprofiel om een certificaataanvraag voor dat vertrouwde basis-CA-certificaat te maken.

- Het SCEP-certificaat profiel wordt alleen geïnstalleerd op apparaten die worden uitgevoerd op het platform dat u hebt opgegeven tijdens het maken van het certificaatprofiel.

- U kunt certificaatprofielen toewijzen aan gebruikersverzamelingen of apparaatverzamelingen.

- Als u een certificaat snel naar een apparaat wilt publiceren nadat het apparaat is geregistreerd, wijst u het certificaatprofiel toe aan een gebruikersgroep en niet aan een apparaatgroep. Als u het toewijst aan een apparaatgroep, is een volledige apparaatregistratie vereist voordat het apparaat beleid kan ontvangen.

- Als u co-beheer gebruikt voor Intune en Configuration Manager, stelt u in Configuration Manager de [workloadschuifregelaar](https://docs.microsoft.com/sccm/comanage/how-to-switch-workloads) voor resourcetoegangsbeleid in op **Intune** of **Testfase van Intune**. Met deze instelling is het toegestaan dat Windows 10-clients het proces starten om het certificaat aan te vragen.

- Hoewel u het vertrouwde certificaatprofiel en het SCEP-certificaatprofiel afzonderlijk maakt en toewijst, moeten beide zijn toegewezen. Als deze niet beide op een apparaat zijn geïnstalleerd, mislukt het SCEP-certificaatbeleid. Zorg ervoor dat alle vertrouwde basiscertificaatprofielen ook zijn geïmplementeerd in dezelfde groepen als het SCEP-profiel.

> [!NOTE]
> Als op iOS-apparaten een SCEP-certificaatprofiel aan een extra profiel, zoals een Wi-Fi- of VPN-profiel, is gekoppeld, ontvangt het apparaat een certificaat voor al deze extra profielen. Hierdoor ontvangt het iOS-apparaat meerdere certificaten na de SCEP-certificaataanvraag.  Als een enkel certificaat gewenst is, moet u PKCS-certificaten gebruiken in plaats van SCEP-certificaten.  Dit is nodig vanwege verschillen in de wijze waarop SCEP-en PKCS-certificaten aan apparaten worden geleverd.

## <a name="next-steps"></a>Volgende stappen

[Profielen toewijzen](../configuration/device-profile-assign.md)
