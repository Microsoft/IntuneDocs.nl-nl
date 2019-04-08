---
title: Azure AD gebruiken voor toegang tot Intune-API's in Microsoft Graph
titleSuffix: Microsoft Intune
description: Beschrijft de stappen die voor apps nodig zijn om Azure AD te gebruiken voor toegang tot de Intune-API's in Microsoft Graph.
keywords: machtigingsrollen voor intune graphapi c# powershell
author: dougeby
manager: dougeby
ms.author: dougeby
ms.date: 03/08/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 79A67342-C06D-4D20-A447-678A6CB8D70A
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 26bdeaf2a5860d0c19feba2ec8b5864e95754b12
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2019
ms.locfileid: "58798976"
---
# <a name="how-to-use-azure-ad-to-access-the-intune-apis-in-microsoft-graph"></a>Azure AD gebruiken voor toegang tot de Intune-API's in Microsoft Graph

De [Microsoft Graph API](https://developer.microsoft.com/graph/) biedt nu ondersteuning voor Microsoft Intune met specifieke API's en machtigingsrollen.  De Microsoft Graph API gebruikt Azure Active Directory (Azure AD) voor verificatie en toegangsbeheer.  
Voor toegang tot de Intune-API's in Microsoft Graph is het volgende vereist:

- Een toepassings-ID met:

    - Machtiging voor het aanroepen van Azure AD en Microsoft Graph API's.
    - Machtigingsbereiken die relevant zijn voor de specifieke toepassingstaken.

- Gebruikersreferenties met:

    - Machtiging voor toegang tot de Azure AD-tenant die is gekoppeld aan de toepassing.
    - Rolmachtigingen die zijn vereist voor ondersteuning van de machtigingsbereiken van de toepassing.

- Verlenen van machtiging aan de app door de eindgebruiker om toepassingstaken uit te voeren voor hun Azure-tenant.

Dit artikel:

- Laat zien hoe u een toepassing registreert met toegang tot de Microsoft Graph API en de relevante machtigingsrollen.

- Bevat een beschrijving van de machtigingsrollen voor de Intune-API.

- Toont voorbeelden van Intune API-verificatie voor C# en PowerShell.

- Bevat een beschrijving hoe u tenants ondersteunt.

Zie voor meer informatie:

- [Toegang tot webtoepassingen die gebruikmaken van OAuth 2.0 en Azure Active Directory autoriseren](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code)
- [Aan de slag met Azure AD-verificatie](https://www.visualstudio.com/docs/integrate/get-started/auth/oauth)
- [Toepassingen integreren met Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications)
- [OAuth 2.0 begrijpen](https://oauth.net/2/)

## <a name="register-apps-to-use-the-microsoft-graph-api"></a>Apps voor het gebruik van de Microsoft Graph API registreren

U registreert als volgt apps voor het gebruik van de Microsoft Graph API:

1.  Meld u met beheerdersreferenties aan bij [Azure Portal](https://portal.azure.com).

    U kunt het volgende gebruiken:
    - De beheerdersaccount van de tenant.
    - Een gebruikersaccount van de tenant waarin de instelling **Gebruikers kunnen toepassingen registreren** is ingeschakeld.

2.  Kies in het menu **Azure Active Directory** &gt; **App-registraties**.

    <img src="./media/azure-ad-app-reg.png" width="157" height="170" alt="The App registrations menu command" />

3.  Kies **Registratie van nieuwe toepassing** om een nieuwe toepassing te maken, of kies een bestaande toepassing.  (Als u een bestaande toepassing kiest, slaat u de volgende stap over.)

4.  Geef de volgende informatie op de blade **Maken** op:

    1.  Een **naam** voor de toepassing (weergegeven wanneer gebruikers zich aanmelden).

    2.  De waarden voor het **toepassingstype** en de **omleidings-URI**.

        Dit is afhankelijk van uw vereisten. Bijvoorbeeld, als u een Azure AD-[verificatiebibliotheek](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) (ADAL) gebruikt, stelt u **toepassingstype** in op `Native` en **omleidings-URI** op `urn:ietf:wg:oauth:2.0:oob`.

        <img src="media/azure-ad-app-new.png" width="209" height="140" alt="New app properties and values" />

        Zie [Verificatiescenario's voor Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios) voor meer informatie.

5.  Op de toepassingsblade:

    1.  Noteer de waarde van de **toepassings-ID**.

    2.  Kies **Instellingen** &gt; **API-toegang** &gt; **Vereiste machtigingen**.

    <img src="media/azure-ad-req-perm.png" width="483" height="186" alt="The Required permissions setting" />

6.  Kies op de blade **Vereiste machtigingen** **Toevoegen** &gt; **API toevoegen toegang** &gt; **Een API selecteren**.

    <img src="media/azure-ad-add-graph.png" width="436" height="140" alt="The Microsoft Graph setting" />

7.  Kies op de blade **Een API selecteren** **Microsoft Graph** &gt; **Selecteren**.  De blade **Toegang inschakelen** wordt geopend en er wordt een lijst weergegeven met machtigingsbereiken die beschikbaar zijn voor uw toepassing.

    <img src="media/azure-ad-perm-scopes.png" width="489" height="248" alt="Intune Graph API permission scopes" />

    Kies de rollen die zijn vereist voor uw app door links van de relevante namen een vinkje te plaatsen.  Zie [Intune-machtigingsbereiken](#intune-permission-scopes) voor meer informatie over specifieke Intune-machtigingsbereiken.  Zie [Referentie voor Microsoft Graph-machtigingen](https://developer.microsoft.com/graph/docs/concepts/permissions_reference) voor meer informatie over andere Graph API-machtigingsbereiken.

    Kies het minste aantal rollen dat nodig is voor het implementeren van uw toepassing om de beste resultaten te verkrijgen.

    Wanneer u klaar bent, kiest u **Selecteren** en **Gereed** om de wijzigingen op te slaan.

Op dit moment, kunt u ook:

- Ervoor kiezen alle tenantaccounts de machtiging te verlenen de app te gebruiken zonder referenties op te geven.  

    Hiervoor kiest u **Machtigingen verlenen** en uw keuze te bevestigen.

    Wanneer u de toepassing voor het eerst uitvoert, wordt u gevraagd de app te machtigen de geselecteerde rollen uit te voeren.

    <img src="media/azure-ad-grant-perm.png" width="351" height="162" alt="The Grant permissions button" />

- Maak de app beschikbaar voor gebruikers buiten uw tenant.  (Dit is doorgaans alleen vereist voor partners die meerdere tenants/organisaties ondersteunen.)  

    Hiervoor doet u het volgende:

  1. Kies **Manifest** op de toepassingsblade. De blade **Manifest bewerken** wordt geopend.

     <img src="media/azure-ad-edit-mft.png" width="295" height="114" alt="The Edit manifest blade" />

  2. Wijzig de waarde van de instelling `availableToOtherTenants` in `true`.

  3. Sla de wijzigingen op.

## <a name="intune-permission-scopes"></a>Intune-machtigingsbereiken

Azure AD en Microsoft Graph gebruiken machtigingsbereiken om toegang tot bedrijfsresources te beheren.  

Machtigingsbereiken (ook wel de _OAuth-bereiken_ genoemd) beheren de toegang tot specifieke Intune-entiteiten en hun eigenschappen. Deze sectie bevat een overzicht van de machtigingsbereiken voor functies van de Intune-API.

Zie voor meer informatie:
- [Azure AD-verificatie](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication)
- [Machtigingsbereiken voor toepassingen](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-scopes)

Wanneer u Microsoft Graph machtigt, kunt u de volgende bereiken opgeven voor het beheren van toegang tot de Intune-functies: de volgende tabel bevat een overzicht van de machtigingsbereiken voor de Intune-API.  In de eerste kolom ziet u de naam van de functie, zoals weergegeven in Azure Portal. De tweede kolom bevat de naam van het machtigingbereik.

De instelling _Toegang inschakelen_ | Scopenaam
:--|:--
__Externe acties die gebruikers beïnvloeden uitvoeren op apparaten met Microsoft Intune__ | [DeviceManagementManagedDevices.PrivilegedOperations.All](#mgd-po)
__Microsoft Intune-apparaten lezen en schrijven__ | [DeviceManagementManagedDevices.ReadWrite.All](#mgd-rw)
__Microsoft Intune-apparaten lezen__ | [DeviceManagementManagedDevices.Read.All](#mgd-ro)
__Microsoft Intune RBAC-instellingen lezen en schrijven__ | [DeviceManagementRBAC.ReadWrite.All](#rac-rw)
__Microsoft Intune RBAC-instellingen lezen__ | DeviceManagementRBAC.Read.All
__Microsoft Intune-apps lezen en schrijven__ | [DeviceManagementApps.ReadWrite.All](#app-rw)
__Microsoft Intune-apps lezen__ | [DeviceManagementApps.Read.All](#app-ro)
__Microsoft Intune-apparaatconfiguratie en -beleid lezen en schrijven__ | DeviceManagementConfiguration.ReadWrite.All
__Microsoft Intune-apparaatconfiguratie en -beleid lezen__ | [DeviceManagementConfiguration.Read.All](#cfg-ro)
__Microsoft Intune-configuratie lezen en schrijven__ | [DeviceManagementServiceConfig.ReadWrite.All](#svc-rw)
__Microsoft Intune-configuratie lezen__ | DeviceManagementServiceConfig.Read.All

De tabel bevat de instellingen zoals die worden weergegeven in Azure Portal. In de volgende secties worden de bereiken in alfabetische volgorde beschreven.

Op dit moment is voor alle Intune-machtigingsbereiken beheerderstoegang vereist.  Dit betekent dat u de bijbehorende referenties nodig hebt voor het uitvoeren van apps of scripts die toegang hebben tot resources voor de Intune-API.

### <a name="app-ro"></a>DeviceManagementApps.Read.All

- Instelling **Toegang inschakelen**: __Microsoft Intune-apps lezen__

- Staat leestoegang toe aan de volgende entiteitseigenschappen en -status:
    - Client-apps
    - Mobiele app-categorieën
    - App-beveiligingsbeleid
    - App-configuraties

### <a name="app-rw"></a>DeviceManagementApps.ReadWrite.All

- Instelling **Toegang inschakelen**: __Microsoft Intune-apps lezen en schrijven__

- Hiermee kunt u dezelfde bewerkingen uitvoeren als met __DeviceManagementApps.Read.All__

- Staat ook wijzigingen toe aan de volgende entiteiten:

    - Client-apps
    - Mobiele app-categorieën
    - App-beveiligingsbeleid
    - App-configuraties

### <a name="cfg-ro"></a>DeviceManagementConfiguration.Read.All

- Instelling **Toegang inschakelen**: __Microsoft Intune-apparaatconfiguratie en -beleid lezen__

- Staat leestoegang toe aan de volgende entiteitseigenschappen en -status:
    - Apparaatconfiguratie
    - Nalevingsbeleid voor apparaten
    - Meldingsberichten

### <a name="cfg-ra"></a>DeviceManagementConfiguration.ReadWrite.All

- Instelling **Toegang inschakelen**: __Microsoft Intune-apparaatconfiguratie en -beleid lezen en schrijven__

- Hiermee kunt u dezelfde bewerkingen uitvoeren als met __DeviceManagementConfiguration.Read.All__

- Apps kunnen ook de volgende entiteiten maken, toewijzen, verwijderen en wijzigen:
    - Apparaatconfiguratie
    - Nalevingsbeleid voor apparaten
    - Meldingsberichten

### <a name="mgd-po"></a>DeviceManagementManagedDevices.PrivilegedOperations.All

- Instelling **Toegang inschakelen**: __Externe acties die gebruikers beïnvloeden uitvoeren op apparaten met Microsoft Intune__

- De volgende externe acties zijn toegestaan op een beheerd apparaat:
    - Buiten gebruik stellen
    - Wissen
    - Wachtwoordcode opnieuw instellen/herstellen
    - Vergrendelen op afstand
    - Modus Apparaat verloren in-/uitschakelen
    - Pc opruimen
    - Opnieuw opstarten
    - Gebruiker verwijderen van het gedeelde apparaat

### <a name="mgd-ro"></a>DeviceManagementManagedDevices.Read.All

- Instelling **Toegang inschakelen**: __Microsoft Intune-apparaten lezen__

- Staat leestoegang toe aan de volgende entiteitseigenschappen en -status:
    - Beheerd apparaat
    - Apparaatcategorie
    - Gedetecteerde app
    - Externe acties
    - Malware-informatie

### <a name="mgd-rw"></a>DeviceManagementManagedDevices.ReadWrite.All

- Instelling **Toegang inschakelen**: __Microsoft Intune-apparaten lezen en schrijven__

- Hiermee kunt u dezelfde bewerkingen uitvoeren als met __DeviceManagementManagedDevices.Read.All__

- Apps kunnen ook de volgende entiteiten maken, verwijderen en wijzigen:
    - Beheerd apparaat
    - Apparaatcategorie

- De volgende externe acties zijn ook toegestaan:
    - Apparaten zoeken
    - Activeringsvergrendeling overslaan
    - Hulp op afstand vragen

### <a name="rac-ro"></a>DeviceManagementRBAC.Read.All

- Instelling **Toegang inschakelen**: __Microsoft Intune RBAC-instellingen lezen__

- Staat leestoegang toe aan de volgende entiteitseigenschappen en -status:
    - Roltoewijzingen
    - Roldefinities
    - Resourcebewerkingen

### <a name="rac-rw"></a>DeviceManagementRBAC.ReadWrite.All

- Instelling **Toegang inschakelen**: __Microsoft Intune RBAC-instellingen lezen en schrijven__

- Hiermee kunt u dezelfde bewerkingen uitvoeren als met __DeviceManagementRBAC.Read.All__

- Apps kunnen ook de volgende entiteiten maken, toewijzen, verwijderen en wijzigen:
    - Roltoewijzingen
    - Roldefinities

### <a name="svc-ro"></a>DeviceManagementServiceConfig.Read.All

- Instelling **Toegang inschakelen**: __Microsoft Intune-configuratie lezen__

- Staat leestoegang toe aan de volgende entiteitseigenschappen en -status:
    - Apparaatregistratie
    - Apple Push Notification-certificaat
    - Apple Device Enrollment Program
    - Apple Volume Purchase Program
    - Exchange Connector
    - Voorwaarden
    - Onkostenbeheer telecommunicatie
    - Cloud PKI
    - Huisstijl
    - Mobile Threat Defense

### <a name="svc-rw"></a>DeviceManagementServiceConfig.ReadWrite.All

- Instelling **Toegang inschakelen**: __Microsoft Intune-configuratie lezen en schrijven__

- Hiermee kunt u dezelfde bewerkingen uitvoeren als met DeviceManagementServiceConfig.Read.All_

- Apps kunnen ook de volgende functies van Intune configureren:
    - Apparaatregistratie
    - Apple Push Notification-certificaat
    - Apple Device Enrollment Program
    - Apple Volume Purchase Program
    - Exchange Connector
    - Voorwaarden
    - Onkostenbeheer telecommunicatie
    - Cloud PKI
    - Huisstijl
    - Mobile Threat Defense

## <a name="azure-ad-authentication-examples"></a>Voorbeelden van Azure AD-verificatie

In deze sectie wordt beschreven hoe u Azure AD opneemt in uw C# en PowerShell-projecten.

In elk voorbeeld moet u een toepassings-ID opgeven met ten minste het `DeviceManagementManagedDevices.Read.All`-machtigingsbereik (eerder besproken).

Wanneer u een van de voorbeelden test, worden mogelijk foutberichten voor HTTP-status 403 (verboden) weergegeven. Deze zien er ongeveer als volgt uit:

``` javascript
{
  "error": {
    "code": "Forbidden",
    "message": "Application is not authorized to perform this operation - Operation ID " +
       "(for customer support): 00000000-0000-0000-0000-000000000000 - " +
       "Activity ID: cc7fa3b3-bb25-420b-bfb2-1498e598ba43 - " +
       "Url: https://example.manage.microsoft.com/" +
       "Service/Resource/RESTendpoint?" +
       "api-version=2017-03-06 - CustomApiErrorPhrase: ",
    "innerError": {
      "request-id": "00000000-0000-0000-0000-000000000000",
      "date": "1980-01-0112:00:00"
    }
  }
}
```

Als dit gebeurt, moet u de volgende punten controleren:

- U hebt de toepassings-ID bijgewerkt naar een ID die de Microsoft Graph API mag gebruiken en het `DeviceManagementManagedDevices.Read.All`-machtigingsbereik heeft.

- De referenties van uw tenant ondersteunen beheerfuncties.

- Uw code is vergelijkbaar met de weergegeven voorbeelden.


### <a name="authenticate-azure-ad-in-c"></a>Azure AD verifiëren in C\#

In dit voorbeeld ziet u hoe u C# gebruikt voor het ophalen van een lijst met apparaten die zijn gekoppeld aan uw Intune-account.

1.  Start Visual Studio en maak een nieuw project voor een Visual C# Console-app (.NET Framework).

2.  Voer een naam in voor uw project en geef desgewenst andere informatie op.

    <img src="media/aad-auth-cpp-new-console.png" width="624" height="433" alt="Creating a C# console app project in Visual Studio"  />

3.  Gebruik Solution Explorer om het Microsoft ADAL NuGet-pakket toe te voegen aan het project.

    1.  Klik met de rechtermuisknop op Solution Explorer.
    2.  Kies **NuGet-pakketten beheren...** &gt; **Bladeren**.
    3.  Selecteer `Microsoft.IdentityModel.Clients.ActiveDirectory` en kies vervolgens **Installeren**.

    <img src="media/aad-auth-cpp-install-package.png" width="624" height="458" alt="Selecting the Azure AD identity model module" />

4.  Voeg de volgende instructies toe bovenaan **Program.cs**:

    ``` csharp
    using Microsoft.IdentityModel.Clients.ActiveDirectory;</p>
    using System.Net.Http;
    ```

5.  Voeg een methode toe voor het maken van de autorisatie-header:

    ``` csharp
    private static async Task<string> GetAuthorizationHeader()
    {
        string applicationId = "<Your Application ID>";
        string authority = "https://login.microsoftonline.com/common/";
        Uri redirectUri = new Uri("urn:ietf:wg:oauth:2.0:oob");
        AuthenticationContext context = new AuthenticationContext(authority);
        AuthenticationResult result = await context.AcquireTokenAsync(
            "https://graph.microsoft.com",
            applicationId, redirectUri,
            new PlatformParameters(PromptBehavior.Auto));
        return result.CreateAuthorizationHeader();
    ```

    Vergeet niet de waarde te wijzigen van `application_ID` zodat deze overeenkomt met een waaraan ten minste het `DeviceManagementManagedDevices.Read.All`-machtigingsbereik is verleend, zoals eerder beschreven.

6. Voeg een methode toe voor het ophalen van de lijst met apparaten:

    ``` csharp
    private static async Task<string> GetMyManagedDevices()
    {
        string authHeader = await GetAuthorizationHeader();
        HttpClient graphClient = new HttpClient();
        graphClient.DefaultRequestHeaders.Add("Authorization", authHeader);
        return await graphClient.GetStringAsync(
            "https://graph.microsoft.com/beta/me/managedDevices");
    }
    ```

7.  Werk **Main** bij om **GetMyManagedDevices** aan te roepen:

    ``` csharp
    string devices = GetMyManagedDevices().GetAwaiter().GetResult();
    Console.WriteLine(devices);
    ```

8.  Compileer uw programma en voer dit uit.  

Wanneer u het programma voor het eerst uitvoert, ontvangt u twee vragen.  In de eerste wordt u gevraagd om uw referenties en de tweede verleent machtigingen voor de `managedDevices`-aanvraag.  

Dit is het complete programma ter referentie:

``` csharp
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using System;
using System.Net.Http;
using System.Threading.Tasks;

namespace IntuneGraphExample
{
    class Program
    {
        static void Main(string[] args)
        {
            string devices = GetMyManagedDevices().GetAwaiter().GetResult();
            Console.WriteLine(devices);
        }

        private static async Task<string> GetAuthorizationHeader()
        {
            string applicationId = "<Your Application ID>";
            string authority = "https://login.microsoftonline.com/common/";
            Uri redirectUri = new Uri("urn:ietf:wg:oauth:2.0:oob");
            AuthenticationContext context = new AuthenticationContext(authority);
            AuthenticationResult result = await context.AcquireTokenAsync("https://graph.microsoft.com", applicationId, redirectUri, new PlatformParameters(PromptBehavior.Auto));
            return result.CreateAuthorizationHeader();
        }

        private static async Task<string> GetMyManagedDevices()
        {
            string authHeader = await GetAuthorizationHeader();
            HttpClient graphClient = new HttpClient();
            graphClient.DefaultRequestHeaders.Add("Authorization", authHeader);
            return await graphClient.GetStringAsync("https://graph.microsoft.com/beta/me/managedDevices");
        }
    }
}
```

### <a name="authenticate-azure-ad-powershell"></a>Azure AD verifiëren (PowerShell)

Voor het volgende PowerShell-script wordt de AzureAD PowerShell-module gebruikt voor de verificatie.  Zie [Azure Active Directory PowerShell versie 2](https://docs.microsoft.com/powershell/azure/install-adv2?view=azureadps-2.0) en de [voorbeelden voor Intune PowerShell](https://github.com/microsoftgraph/powershell-intune-samples).

In dit voorbeeld werkt u de waarde bij `$clientID` zodat deze overeenkomt met een geldige toepassings-ID.

``` powershell
function Get-AuthToken {
    [cmdletbinding()]
    param
    (
        [Parameter(Mandatory = $true)]
        $User
    )

    $userUpn = New-Object "System.Net.Mail.MailAddress" -ArgumentList $User
    $tenant = $userUpn.Host

    Write-Host "Checking for AzureAD module..."

    $AadModule = Get-Module -Name "AzureAD" -ListAvailable
    if ($AadModule -eq $null) {
        Write-Host "AzureAD PowerShell module not found, looking for AzureADPreview"
        $AadModule = Get-Module -Name "AzureADPreview" -ListAvailable
    }

    if ($AadModule -eq $null) {
        write-host
        write-host "AzureAD Powershell module not installed..." -f Red
        write-host "Install by running 'Install-Module AzureAD' or 'Install-Module AzureADPreview' from an elevated PowerShell prompt" -f Yellow
        write-host "Script can't continue..." -f Red
        write-host
        exit
    }

    # Getting path to ActiveDirectory Assemblies
    # If the module count is greater than 1 find the latest version

    if ($AadModule.count -gt 1) {
        $Latest_Version = ($AadModule | select version | Sort-Object)[-1]
        $aadModule = $AadModule | ? { $_.version -eq $Latest_Version.version }
        $adal = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.dll"
        $adalforms = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.Platform.dll"
    }

    else {
        $adal = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.dll"
        $adalforms = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.Platform.dll"
    }

    [System.Reflection.Assembly]::LoadFrom($adal) | Out-Null
    [System.Reflection.Assembly]::LoadFrom($adalforms) | Out-Null

    $clientId = "<Your Application ID>"
    $redirectUri = "urn:ietf:wg:oauth:2.0:oob"
    $resourceAppIdURI = "https://graph.microsoft.com"
    $authority = "https://login.microsoftonline.com/$Tenant"

    try {
        $authContext = New-Object "Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext" -ArgumentList $authority
        # https://msdn.microsoft.com/library/azure/microsoft.identitymodel.clients.activedirectory.promptbehavior.aspx
        # Change the prompt behaviour to force credentials each time: Auto, Always, Never, RefreshSession
        $platformParameters = New-Object "Microsoft.IdentityModel.Clients.ActiveDirectory.PlatformParameters" -ArgumentList "Auto"
        $userId = New-Object "Microsoft.IdentityModel.Clients.ActiveDirectory.UserIdentifier" -ArgumentList ($User, "OptionalDisplayableId")
        $authResult = $authContext.AcquireTokenAsync($resourceAppIdURI, $clientId, $redirectUri, $platformParameters, $userId).Result
        # If the accesstoken is valid then create the authentication header
        if ($authResult.AccessToken) {
            # Creating header for Authorization token
            $authHeader = @{
                'Content-Type' = 'application/json'
                'Authorization' = "Bearer " + $authResult.AccessToken
                'ExpiresOn' = $authResult.ExpiresOn
            }
            return $authHeader
        }
        else {
            Write-Host
            Write-Host "Authorization Access Token is null, please re-run authentication..." -ForegroundColor Red
            Write-Host
            break
        }
    }
    catch {
        write-host $_.Exception.Message -f Red
        write-host $_.Exception.ItemName -f Red
        write-host
        break
    }   
}

$authToken = Get-AuthToken -User "<Your AAD Username>"

try {
    $uri = "https://graph.microsoft.com/beta/me/managedDevices"
    Write-Verbose $uri
    (Invoke-RestMethod -Uri $uri –Headers $authToken –Method Get).Value
}
catch {
    $ex = $_.Exception
    $errorResponse = $ex.Response.GetResponseStream()
    $reader = New-Object System.IO.StreamReader($errorResponse)
    $reader.BaseStream.Position = 0
    $reader.DiscardBufferedData()
    $responseBody = $reader.ReadToEnd();
    Write-Host "Response content:`n$responseBody" -f Red
    Write-Error "Request to $Uri failed with HTTP Status $($ex.Response.StatusCode) $($ex.Response.StatusDescription)"
    write-host
    break
}
```

## <a name="support-multiple-tenants-and-partners"></a>Ondersteuning voor meerdere tenants en partners

Als uw organisatie ondersteuning biedt aan organisaties met hun eigen Azure AD-tenants, is het raadzaam om uw clients te machtigen voor het gebruik van uw toepassing met hun respectieve tenants.

Hiervoor doet u het volgende:

1.  Controleer of de clientaccount bestaat in de doel-Azure AD-tenant.

2.  Controleer of uw tenantaccount gebruikers toestaat om toepassingen te registreren (zie **gebruikersinstellingen**).

3.  Breng een relatie tot stand tussen elke tenant.  

    Hiervoor voert u een van de volgende acties uit:

    a. Gebruik de [Microsoft Partner Center](https://partnercenter.microsoft.com/) om een relatie vast te stellen met uw client en hun e-mailadres.

    b. Nodig de gebruiker uit een gast van uw tenant te worden.

De gebruiker uitnodigen een gast van uw tenant te zijn:

1.  Kies **Een gastgebruiker toevoegen** in het deelvenster **Snelle taken**.

    <img src="media/azure-ad-add-guest.png" width="448" height="138" alt="Use Quick Tasks to add a guest user" />

2.  Voer het e-mailadres van de client in en voeg desgewenst een persoonlijk bericht toe voor de uitnodiging (optioneel).

    <img src="media/azure-ad-guest-invite.png" width="203" height="106" alt="Inviting an external user as a guest" />

3.  Kies **Uitnodigen**.

Hierdoor wordt een uitnodiging verzonden naar de gebruiker.

   <img src="media/aad-multiple-tenant-invitation.png" width="624" height="523" alt="A sample guest invitation" />

   De gebruiker moet de koppeling **Aan de slag** selecteren om de uitnodiging te accepteren.

Wanneer de relatie tot stand is gebracht (of uw uitnodiging is geaccepteerd), voegt u het gebruikersaccount toe aan de **Directory-rol**.

Vergeet indien van toepassing niet de gebruiker toe te voegen aan andere rollen. Om een gebruiker te machtigen instellingen voor Intune te beheren, moet deze **Globale beheerder** of **Intune-servicebeheerder** zijn.

Ook:

- Gebruiken om een Intune-licentie aan uw gebruikersaccount toe te voegen https://admin.microsoft.com .

- Werk de toepassingscode bij voor de verificatie van het Azure AD-tenantdomein van de klant, in plaats van uw eigen domein.

    Stel bijvoorbeeld dat uw tenant-domein `contosopartner.onmicrosoft.com` is en het domein van de tenant van uw client is `northwind.onmicrosoft.com`, dan zou u uw code bijwerken voor verificatie bij de tenant van de client.

    Als u dit wilt doen in een C#-toepassing op basis van het vorige voorbeeld, zou u de waarde wijzigen van de variabele `authority`:

    ``` csharp
    string authority = "https://login.microsoftonline.com/common/";
    ```

    in op

    ``` csharp
    string authority = "https://login.microsoftonline.com/northwind.onmicrosoft.com/";
    ```
