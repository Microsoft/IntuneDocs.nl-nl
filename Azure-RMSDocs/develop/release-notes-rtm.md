---
title: Opmerkingen bij de release | Azure RMS
description: 
keywords: 
author: bruceperlerms
manager: mbaldwin
ms.date: 06/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: CE379738-4E1D-42AD-83F4-F89B70456EBB
audience: developer
ms.reviewer: shubhamp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 56d0538243af49580f24c701ad5097b30f3059b0
ms.openlocfilehash: 61df64691ac3f4d7e871043767444ea64dfe1ef3


---

# Opmerkingen bij de release

Dit onderwerp bevat belangrijke informatie over deze en eerdere versies van de RMS SDK 2.1.

## Nieuw voor de SDK-documentatie-update van februari 2016

>[!Note]
> De documentatie-updates voor functies in deze sectie zijn van toepassing op de SDK-download met de datum 11-12-2015.

- **Verbeterde verificatiestroom**: Met op OAuth2-tokens gebaseerde verificatie via de [Azure Active Directory Authentication Library (ADAL)](https://azure.microsoft.com/en-us/documentation/articles/active-directory-authentication-libraries/). Zie [ADAL authentication for your RMS enabled application](how-to-use-adal-authentication.md) (ADAL-verificatie voor uw RMS-toepassing) voor meer informatie over dit proces en de bijbehorende API-uitbreidingen.

- **Update van ADAL**: als u uw toepassing bijwerkt zodat deze ADAL-verificatie gebruikt in plaats van de Microsoft Online-aanmeldhulp, kunnen u en uw klanten het volgende doen:

 - Multi-Factor Authentication gebruiken
 - De RMS 2.1-client installeren zonder dat hiervoor beheerdersrechten voor de computer vereist zijn
 - Uw toepassing certificeren voor Windows 10

- **Ondersteuning voor Microsoft Online Aanmeldhulp (SIA) met de RMS SDK wordt verwijderd.** Er wordt nog zes maanden ondersteuning geboden voor SIA, waarna de ondersteuning wordt gestopt.


## Update van december 2015

- Er zijn prestatieverbeteringen geïmplementeerd op verschillende gebieden, waaronder:
    - Publiceren van primaire licentieserver bij gebruik van alleen-licentieservers.
    - Er treedt sneller een fout met RMS SDK 2.1 op wanneer er geen netwerkverbinding is.

- Veel updates voor betere foutberichten en probleemoplossing.
- Bovendien is de vermelding met [Ondersteunde platformen](supported-platforms.md) bijgewerkt.
- De noodzaak voor de preproductieomgeving en het gebruik van een toepassingsmanifest is verwijderd uit de RMS SDK 2.1. Deze secties van deze set ontwikkeldocumentatie zijn verwijderd en de algehele documentatie is vereenvoudigd en opnieuw ingedeeld.

## Update van mei 2015

-   Voor **service-apps en RMS in de cloud** - [**IPC\_CREDENTIAL\_SYMMETRIC\_KEY**](/rights-management/sdk/2.1/api/win/ipc_credential#msipc_ipc_credential_symmetric_key) zijn drie soorten informatie vereist; symmetrische sleutel, **AppPrincipalId** en **TenantBposId**. Het onderwerp hiervoor is bijgewerkt met advies over het ophalen van deze informatie. Zie de bijgewerkte versie van [Ervoor zorgen dat uw servicetoepassing werkt met RMS in de cloud](how-to-use-file-api-with-aadrm-cloud.md) voor deze update.

## Update van april 2015

-   **Documenttracking** is nu mogelijk via een set nieuwe API's. Zie [Tracking content](tracking-content.md) (Inhoud volgen) voor meer informatie.
-   **Coderingstype**: Er wordt nu ondersteuning geboden voor beheer op API-niveau voor selectie van het versleutelingspakket. Zie [Working with encryption](working-with-encryption.md) (Werken met versleuteling) voor meer informatie.

    **Opmerking** de markering **IPC\_LI\_DEPRECATED\_ENCRYPTION\_ALGORITHMS** wordt niet meer weergegeven in de API. Dit betekent dat toekomstige apps niet langer worden gecompileerd als ze verwijzen naar deze markering. Apps die al zijn gemaakt, blijven werken omdat de markering in de API-code apart wordt verwerkt. U kunt de markering voor oudere, afgeschafte versleutelingsalgoritmen nog steeds gebruiken door een markering te wijzigen. Zie [Working with encryption](working-with-encryption.md) (Werken met versleuteling) voor meer informatie.

-   Voor **servermodustoepassingen** die een [**API-moduswaarde**](/rights-management/sdk/2.1/api/win/api%20mode%20values#msipc_api_mode_values_IPC_API_MODE_SERVER) gebruiken van **IPC\_API\_MODE\_SERVER**, is geen manifest van de toepassing meer vereist. U kunt uw toepassing testen op een RMS-productieserver en hoeft geen productielicentie te verkrijgen wanneer u overschakelt naar productieomgeving. Zie [Toepassingstypen](application-types.md) voor meer informatie over servermodustoepassingen.
-   **Logboekregistratie** wordt nu geïmplementeerd via bestanden en Event Tracing for Windows.
-   Zie de opmerking bij 'Belangrijke opmerkingen voor ontwikkelaars' als u een **computer met Windows 7 SP1 of Windows Server 2008 R2** gebruikt.

## Update van januari 2015

-   **Toename van de grootte voor beveiligde bestanden (.pfile)**: Beveiligde bestanden groter dan één gigabyte (1 GB) worden nu ondersteund. Zie [Supported File Formats](supported-file-formats.md) (Ondersteunde bestandsindelingen) voor meer informatie over beveiligde bestanden.
-   **Verbeterde logboekregistratie voor betere diagnostische gegevens**: In de registratieniveaus wordt **FOUT** of **WAARSCHUWING** weergegeven voor berichten die moeten worden gecontroleerd. Alle andere berichten, inclusief uitzonderingen die nog steeds worden weergegeven, worden geregistreerd als **INFO**.

    Deze benadering is gekozen om te voorkomen dat er details verloren gaan. Nu worden alleen de belangrijke berichten weergegeven met het niveau WAARSCHUWING.

-   **Bedrijfssjablonen ophalen**: aanzienlijke verbeteringen voor de sjabloon voor het ophalen van code, op basis van de klantrapporten en feedback.
-   Verbeterde consistentie van lokalisatie

## Update van oktober 2014

-   Het standaardgedrag voor het bestands-API-onderdeel van de SDK is bijgewerkt. Zie [File API configuration](file-api-configuration.md) (Configuratie van bestands-API) voor meer informatie.
-   De nieuwe functie voor e-mailmeldingen wordt beschreven in het onderwerp [Enabling email notification](how-to-enable-email-notification.md) (E-mailmeldingen inschakelen) in de sectie met opmerkingen voor ontwikkelaars.

## Update van juli 2014

De bestands-API-onderdelen van SDK zijn uitgebreid en kunnen worden gebruikt voor het volgende:

-   Identificeren welke beveiliging moet worden gebruikt.
-   RMS-beveiliging bieden op het granulariteitsniveau van een bestand.

    Functies die in deze zijn release toegevoegd:

    **Opmerking**: Meer ondersteunde gegevenstypen en -structuren, die hier niet hier worden vermeld, zijn toegevoegd voor bestands-API-uitbreidingen. Alle onderwerpen die zijn bijgewerkt voor deze release, zijn gemarkeerd als **voorlopig en kan worden gewijzigd**.

    -   [**IpcfOpenFileOnHandle**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcfopenfileonhandle)
    -   [**IpcfOpenFileOnILockBytes**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcfopenfileonilockbytes)
    -   [**IpcfGetFileProperty**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcfgetfileproperty)
    -   [**IpcfLogicalFileRangeToRawFileRange**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcflogicalfilerangetorawfilerange)
    -   [**IpcfReadFile**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcfreadfile)
    -   [**IpcfSetEndOfFile**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcfsetendoffile)
    -   [**IpcfWriteFile**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcfwritefile)

## Update van april 2014

-   Het **geheugengebruik van de bestands-API** is met name voor grote beveiligde bestanden (PFile) aanzienlijk verbeterd.
-   De **id van inhoud** kan nu worden bewerkt via de eigenschap **IPC\_LI\_CONTENT\_ID**. Zie [**License property types**](/rights-management/sdk/2.1/api/win/License%20property%20types#msipc_license_property_types_IPC_LI_APP_SPECIFIC_DATA) (Typen licentie-eigenschappen) voor meer informatie.
-   **Vereiste voor productiemanifest**: Wanneer uw toepassing/service met RMS-functionaliteit wordt uitgevoerd in de servermodus, is er geen manifest meer vereist. Zie [Soorten toepassingen](application-types.md) voor meer informatie.
-   **Documentatie-updates**

    **Testen van best practices**: Er zijn richtlijnen toegevoegd voor gebruik van een on-premises server voordat u met Azure RMS test. Zie [Ervoor zorgen dat uw servicetoepassing werkt met RMS in de cloud](how-to-use-file-api-with-aadrm-cloud.md) voor meer informatie.

## Belangrijke opmerkingen voor ontwikkelaars

-   **Systeemeigen ondersteuning voor alle bestandstypen**

    Met deze release van Rights Management Services SDK 2.1 kan systeemeigen ondersteuning kan worden toegevoegd voor elk bestandstype (extensie). Zo wordt voor elke extensie &lt;ext&gt; (niet-Office- en PDF-bestanden), \*.p&lt;ext&gt; gebruikt als de beheerconfiguratie voor de extensie SYSTEEMEIGEN is.

    Zie [File API configuration](file-api-configuration.md) (Configuratie van bestands-API) voor meer informatie over ondersteunde bestandstypen.

-   Op **computers met Windows 7 SP1 en Windows Server 2008 R2 SP1** zonder de update [KB2533623](https://support.microsoft.com/en-us/kb/2533623) wordt mogelijk de volgende fout gegenereerd wanneer een Office-bestand wordt beveiligd: De parameter is onjuist. Foutcode 0x80070057. Als u dit ziet, installeert u de update en probeert u het opnieuw. Als u nog steeds problemen ervaart, neemt u contact op via de alias voor feedback over RMS SDK Beta: <rmcstbeta@microsoft.com>.

    **Opmerking** vanaf de release van April 2015 is een controle toegevoegd aan het installatieproces voor deze KB.

     

-   **Integratie van bestands-API**

    Dankzij de integratie van de bestands-API in Active Directory Rights Management Services profiteert u nu van de volgende voordelen en mogelijkheden.

      - U kunt vertrouwelijke gegevens automatisch beveiligen zonder de details te kennen van de Information Rights Management-implementatie (IRM) die wordt gebruikt door verschillende bestandsindelingen.

      - Microsoft Office-bestanden, Portable Document Format-bestanden (PDF) en andere geselecteerde bestandstypen kunnen worden beveiligd met systeemeigen beveiliging. Zie [File API configuration](file-api-configuration.md) (Configuratie van bestands-API) voor een volledige lijst met bestandstypen die kunnen worden beveiligd met systeemeigen beveiliging.

      - Alle bestanden, met uitzondering van systeembestanden en Office-bestanden, kunnen worden beveiligd met de beveiligde bestandsindeling van RMS (PFile).

    De bestands-API wordt geïmplementeerd via de volgende vier nieuwe functies: [IpcfDecryptFile](/rights-management/sdk/2.1/api/win/functions#msipc_ipcfdecryptfile), [IpcfEncryptFile](/rights-management/sdk/2.1/api/win/functions#msipc_ipcfencryptfile), [IpcfGetSerializedLicenseFromFile](/rights-management/sdk/2.1/api/win/functions#msipc_ipcfgetserializedlicensefromfile) en [IpcfIsFileEncrypted](/rights-management/sdk/2.1/api/win/functions#msipc_ipcfisfileencrypted).

    Voor de bestands-API is vereist dat de Rights Management Service Client 2.1 op de clientcomputer is geïnstalleerd en dat de computer verbonden is met een RMS-server. Raadpleeg de TechNet-inhoud [IT Pro-documentatie voor AD RMS](https://technet.microsoft.com/en-us/library/cc771234(v=ws.10).aspx) voor meer informatie over de RMS-server, de RMS-client en de functionaliteit hiervan.

-   **Probleem**: bij het maken van een nieuwe licentie, moeten eigendomsrechten expliciet worden verleend.

    **Oplossing**: In uw toepassing moeten expliciet **eigendomsrechten** worden toegevoegd voor de eigenaar van de licentie wanneer u een nieuwe licentie maakt met [**IpcCreateLicenseFromScratch**](/rights-management/sdk/2.1/api/win/functions#msipc_ipccreatelicensefromscratch). Zie [Add explicit owner rights](add-explicit-owner-rights.md) (Expliciete eigendomsrechten toevoegen) voor meer informatie.

-   **Probleem**: als met een toepassing [**IpcProtectWindow**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcprotectwindow) of [**IpcUnprotectWindow**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcunprotectwindow) tweemaal voor hetzelfde venster wordt aangeroepen met de bijbehorende ingang, retourneert RMS SDK 2.1 een fout in **HRESULT**.

    **Oplossing**: zie de sectie met opmerkingen in [**IpcProtectWindow**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcprotectwindow) en [**IpcUnprotectWindow**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcunprotectwindow) voor specifieke aanwijzingen.

-   **Probleem**: wanneer u meerdere architecturen maakt, moet u deze aanwijzingen gebruiken.

    **Oplossing**: als u het bestand Ipcsecproc\*isv.dll wilt gebruiken voor een andere architectuur (u hebt bijvoorbeeld de 64 bits-SDK geïnstalleerd op een 64 bitscomputer maar wilt deze nu implementeren op een 32 bitscomputer waarvoor Ipcsecproc\*isv.dll is vereist), moet u de 32 bits-SDK installeren op een andere computer en de Ipcsecproc\*isv.dll-bestanden daar naartoe kopiëren vanuit de map %PROGRAMFILES%\\Microsoft Information Protection And Control (de standaardlocatie of de locatie die u kiest voor het installeren van de SDK).

## Veelgestelde vragen

**V**: hoe werkt de standaardtaal met functies die een LCID-parameter gebruiken?

**A**: Gebruik 0 voor de standaardlandinstelling. In dit geval zoekt AD RMS-client 2.1 namen en beschrijvingen in de volgende reeks en wordt het resultaat opgehaald dat het eerst beschikbaar is:

    1 - User preferred LCID.
    2 - System locale LCID.
    3 - The first available language specified in the Rights Management Server (RMS) template.

Als er geen naam en beschrijving kunnen worden opgehaald, wordt een fout geretourneerd. Een bepaalde LCID kan slechts één naam en beschrijving hebben.

## Verwante onderwerpen

* [Overzicht](ad-rms-overview.md)
* [Expliciete eigendomsrechten toevoegen](add-explicit-owner-rights.md)
* [Configuratie van bestands-API](file-api-configuration.md)
* [**IpcfGetSerializedLicenseFromFile**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcfgetserializedlicensefromfile)
* [**IpcfEncryptFile**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcfencryptfile)
* [**IpcfDecryptFile**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcfdecryptfile)
* [**IpcfIsFileEncrypted**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcfisfileencrypted)
* [**IpcCreateLicenseFromScratch**](/rights-management/sdk/2.1/api/win/functions#msipc_ipccreatelicensefromscratch)
* [**IpcProtectWindow**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcprotectwindow)
* [**IpcUnprotectWindow**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcunprotectwindow)
 

 



<!--HONumber=Jul16_HO3-->


