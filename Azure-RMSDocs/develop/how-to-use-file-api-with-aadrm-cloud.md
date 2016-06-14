---
# required metadata

title: Ervoor zorgen dat uw servicetoepassing werkt met RMS in de cloud | Azure RMS
description: In dit onderwerp worden de stappen beschreven voor het instellen van uw servicetoepassing voor het gebruik van Azure Rights Management.
keywords:
author: bruceperlerms
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: EA1457D1-282F-4CF3-A23C-46793D2C2F32
# optional metadata

#ROBOTS:
audience: developer
#ms.devlang:
ms.reviewer: shubhamp
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---
** Deze SDK-inhoud is niet actueel. U kunt tijdelijk de [huidige versie](https://msdn.microsoft.com/library/windows/desktop/hh535290(v=vs.85).aspx) van de documentatie op MSDN vinden. **
# Ervoor zorgen dat uw servicetoepassing werkt met RMS in de cloud

In dit onderwerp worden de stappen beschreven voor het instellen van uw servicetoepassing voor het gebruik van Azure Rights Management. Zie [Aan de slag met Azure Rights Management](https://technet.microsoft.com/en-us/library/jj585016.aspx) voor meer informatie.

**Belangrijk**  
Het wordt aanbevolen de Rights Management Services SDK 2.1-toepassing eerst te testen met de RMS-preproductieomgeving op een RMS-server. Daarna kunt u, als u wilt dat uw klant de mogelijkheid heeft om uw toepassing te gebruiken met de Azure RMS-service, tests met die omgeving uitvoeren.

Als u uw RMS SDK 2.1-servicetoepassing wilt gebruiken met Azure RMS, moet u een Azure RMS-tenant aanvragen als u die nog niet hebt. Verzend een e-mail naar <rmcstbeta@microsoft.com> met uw tenantaanvraag.

## Vereisten

-   De RMS SDK 2.1 moet worden geïnstalleerd en geconfigureerd. Zie [Aan de slag met de RMS SDK 2.1](getting-started-with-ad-rms-2-0.md) voor meer informatie.
-   U moet [een service-identiteit maken via ACS](https://msdn.microsoft.com/en-us/library/gg185924.aspx) met behulp van de symmetrische-sleuteloptie of via andere middelen en de sleutelgegevens van dat proces vastleggen.

## Verbinding maken met de Azure Rights Management-service

-   Roep [**IpcInitialize**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcinitialize) aan.
-   Stel [**IpcSetGlobalProperty**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcsetglobalproperty) in.


    int mode = IPC_API_MODE_SERVER; IpcSetGlobalProperty(IPC_EI_API_MODE, &(mode));


**Opmerking** Voor meer informatie raadpleegt u [De API-beveiligingsmodus instellen](setting-the-api-security-mode-api-mode.md)

     

-   Via de volgende stappen maakt u een instantie van een [**IPC\_PROMPT\_CTX**](/rights-management/sdk/2.1/api/win/ipc_prompt_ctx#msipc_ipc_prompt_ctx)-structuur, waarbij het **pcCredential**-lid ([**IPC\_CREDENTIAL**](/rights-management/sdk/2.1/api/win/ipc_credential#msipc_ipc_credential) is ingevuld met de verbindingsinformatie van de Azure Rights Management Service.
-   Gebruik de informatie die u hebt verkregen tijdens het maken van de service-id van de symmetrische sleutel (zie de vereisten die eerder in dit onderwerp zijn vermeld) om de parameters **wszServicePrincipal**, **wszBposTenantId** en **cbKey** in te stellen bij het maken van een instantie van een [**IPC\_CREDENTIAL\_SYMMETRIC\_KEY**](/rights-management/sdk/2.1/api/win/ipc_credential#msipc_ipc_credential_symmetric_key)-structuur.

**Opmerking** Als gevolg van een bestaande voorwaarde van onze Discovery-service worden symmetrische-sleutelreferenties uit andere regio’s (als u niet in Noord-Amerika woont) niet geaccepteerd. Daarom moet u uw tenant-URL’s rechtstreeks opgeven. Dit doet u via de parameter [**IPC\_CONNECTION\_INFO**](/rights-management/sdk/2.1/api/win/ipc_connection_info#msipc_ipc_connection_info) van [**IpcGetTemplateList**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcgettemplatelist) of [**IpcGetTemplateIssuerList**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcgettemplateissuerlist).

## Een symmetrische sleutel genereren en de benodigde gegevens verzamelen

### Instructies voor het genereren van een symmetrische sleutel

-   Installeer de [Microsoft Online-aanmeldhulp](http://go.microsoft.com/fwlink/p/?LinkID=286152)
-   Installeer de [Azure AD PowerShell-module](https://bposast.vo.msecnd.net/MSOPMW/8073.4/amd64/AdministrationConfig-en.msi).

**Opmerking** U moet een tenantbeheerder zijn om de Powershell-cmdlets te kunnen gebruiken.


-   Start PowerShell en voer de volgende opdrachten uit om een sleutel te genereren:         `Import-Module MSOnline`
            `Connect-MsolService` (typ uw beheerreferenties)         `New-MsolServicePrincipal` (typ een weergavenaam)
-   Nadat er een symmetrische sleutel is gegenereerd, worden de sleutel en informatie erover vrijgegeven. Ook komt **AppPrincipalId** beschikbaar.



    De volgende symmetrische sleutel is gemaakt omdat er geen sleutel was opgegeven ZYbF/lTtwE28qplQofCpi2syWd11D83+A3DRlb2Jnv8=

    DisplayName : RMSTestApp ServicePrincipalNames : {7d9c1f38-600c-4b4d-8249-22427f016963} ObjectId : 0ee53770-ec86-409e-8939-6d8239880518 AppPrincipalId : 7d9c1f38-600c-4b4d-8249-22427f016963



### Instructies om **TenantBposId** en **Urls** te achterhalen

-   Installeer de [Azure RMS PowerShell-module](https://technet.microsoft.com/en-us/library/jj585012.aspx).
-   Open PowerShell en voer de volgende opdrachten uit om de RMS-configuratie van de tenant op te halen.

    `Import-Module aadrm`

    `Connect-AadrmService` (voer uw beheerdersreferenties in)

    `Get-AadrmConfiguration`


-   Maak een instantie van een [**IPC\_CREDENTIAL\_SYMMETRIC\_KEY**](/rights-management/sdk/2.1/api/win/ipc_credential#msipc_ipc_credential_symmetric_key) en stel een aantal leden in.

    // Maak een sleutelstructuur.
    IPC_CREDENTIAL_SYMMETRIC_KEY symKey = {0};

    // Stel elk lid in met informatie die u hebt gekregen tijdens het maken van de service.
    symKey.wszBase64Key = de hoofdsleutel voor de service; symKey.wszAppPrincipalId = de hoofd-id van de app; symKey.wszBposTenantId = uw tenant-id;


Zie [**IPC\_CREDENTIAL\_SYMMETRIC\_KEY**](/rights-management/sdk/2.1/api/win/ipc_credential#msipc_ipc_credential_symmetric_key) voor meer informatie.

-   Maak een instantie van een [**IPC\_CREDENTIAL**](/rights-management/sdk/2.1/api/win/ipc_credential#msipc_ipc_credential)-structuur die uw [**IPC\_CREDENTIAL\_SYMMETRIC\_KEY**](/rights-management/sdk/2.1/api/win/ipc_credential#msipc_ipc_credential_symmetric_key)-instantie bevat.

**Opmerking** De *conectionInfo*-leden worden ingesteld met URL's van de vorige aanroep aan `Get-AadrmConfiguration` en worden hier vermeld met de veldnamen.

    // Create a credential structure.
    IPC_CREDENTIAL cred = {0};

    IPC_CONNECTION_INFO connectionInfo = {0};
    connectionInfo.wszIntranetUrl = LicensingIntranetDistributionPointUrl;
    connectionInfo.wszExtranetUrl = LicensingExtranetDistributionPointUrl;

    // Set each member.
    cred.dwType = IPC_CREDENTIAL_TYPE_SYMMETRIC_KEY;
    cred.pcCertContext = (PCCERT_CONTEXT)&symKey;

    // Create your prompt control.
    IPC_PROMPT_CTX promptCtx = {0};

    // Set each member.
    promptCtx.cbSize = sizeof(IPC_PROMPT_CTX);
    promptCtx.hwndParent = NULL;
    promptCtx.dwflags = IPC_PROMPT_FLAG_SILENT;
    promptCtx.hCancelEvent = NULL;
    promptCtx.pcCredential = &cred;

### Een sjabloon identificeren en deze vervolgens versleutelen

-   Selecteer een sjabloon om voor de versleuteling te gebruiken.
    Roep [**IpcGetTemplateList**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcgettemplatelist) aan die wordt doorgegeven in dezelfde instantie van [**IPC\_PROMPT\_CTX**](/rights-management/sdk/2.1/api/win/ipc_prompt_ctx#msipc_ipc_prompt_ctx).


    PCIPC_TIL pTemplates = NULL; IPC_TEMPLATE_ISSUER templateIssuer = (pTemplateIssuerList->aTi)[0];

    hr = IpcGetTemplateList(&(templateIssuer.connectionInfo),        IPC_GTL_FLAG_FORCE_DOWNLOAD,        0,        &promptCtx,        NULL,        &pTemplates);


-   Gebruik de sjabloon van eerder in dit onderwerp om [**IpcfEncrcyptFile**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcfencryptfile) aan te roepen die in dezelfde instantie van [**IPC\_PROMPT\_CTX**](/rights-management/sdk/2.1/api/win/ipc_prompt_ctx#msipc_ipc_prompt_ctx) wordt doorgegeven.

Voorbeeld van het gebruik van [**IpcfEncrcyptFile**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcfencryptfile):

    LPCWSTR wszContentTemplateId = pTemplates->aTi[0].wszID;
    hr = IpcfEncryptFile(wszInputFilePath,
           wszContentTemplateId,
           IPCF_EF_TEMPLATE_ID,
           IPC_EF_FLAG_KEY_NO_PERSIST,
           &promptCtx,
           NULL,
           &wszOutputFilePath);

Voorbeeld van het gebruik van [**IpcfDecryptFile**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcfdecryptfile):

    hr = IpcfDecryptFile(wszInputFilePath,
           IPCF_DF_FLAG_DEFAULT,
           &promptCtx,
           NULL,
           &wszOutputFilePath);

U hebt nu de benodigde stappen voltooid om ervoor te zorgen dat uw toepassing gebruik kan maken van Azure Rights Management.

## Verwante onderwerpen

* [Concepten voor ontwikkelaars](ad-rms-concepts-nav.md)
* [Aan de slag met Azure Rights Management](https://technet.microsoft.com/en-us/library/jj585016.aspx)
* [Aan de slag met de RMS SDK 2.1](getting-started-with-ad-rms-2-0.md)
* [Een service-id maken via ACS](https://msdn.microsoft.com/en-us/library/gg185924.aspx)
* [**IpcSetGlobalProperty**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcsetglobalproperty)
* [**IpcInitialize**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcinitialize)
* [**IPC\_PROMPT\_CTX**](/rights-management/sdk/2.1/api/win/ipc_prompt_ctx#msipc_ipc_prompt_ctx)
* [**IPC\_CREDENTIAL**](/rights-management/sdk/2.1/api/win/ipc_credential#msipc_ipc_credential)
* [**IPC\_CREDENTIAL\_SYMMETRIC\_KEY**](/rights-management/sdk/2.1/api/win/ipc_credential#msipc_ipc_credential_symmetric_key)
* [**IpcGetTemplateIssuerList**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcgettemplateissuerlist)
* [**IpcGetTemplateList**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcgettemplatelist)
* [**IpcfDecryptFile**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcfdecryptfile)
* [**IpcfEncrcyptFile**](/rights-management/sdk/2.1/api/win/functions#msipc_ipcfencryptfile)
* [**IpcCreateLicenseFromScratch**](/rights-management/sdk/2.1/api/win/functions#msipc_ipccreatelicensefromscratch)
* [**IpcCreateLicenseFromTemplateID**](/rights-management/sdk/2.1/api/win/functions#msipc_ipccreatelicensefromtemplateid)
 

 


<!--HONumber=Jun16_HO1-->


