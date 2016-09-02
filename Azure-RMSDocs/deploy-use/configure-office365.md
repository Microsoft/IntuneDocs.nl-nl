---
title: Office 365&colon; configuratie voor clients en onlineservices | Azure RMS
description: Omdat Office 365 systeemeigen ondersteuning biedt voor Azure RMS, is er geen configuratie van een clientcomputer vereist voor de ondersteuning van de functies voor Information Rights Management (IRM) voor toepassingen zoals Word, Excel, PowerPoint, Outlook en Outlook Web App. Het enige wat gebruikers hoeven te doen, is zich met hun Microsoft Office 365-referenties aan te melden bij hun Office-toepassingen. Vervolgens kunnen zij bestanden en e-mails beveiligen, en bestanden en e-mails gebruiken die door anderen zijn beveiligd.
author: cabailey
manager: mbaldwin
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 0a6ce612-1b6b-4e21-b7fd-bcf79e492c3b
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 26b043f1f9e7a1e0cd00c2f31c28f7d6685f0232
ms.openlocfilehash: 09f152ef910cf9c08c9a693f79c40f491263c5d3


---

# Office 365: configuratie voor clients en onlineservices

>*Van toepassing op: Azure Rights Management, Office 365*

Omdat Office 365 systeemeigen ondersteuning biedt voor Azure RMS, is er geen configuratie van een clientcomputer vereist voor de ondersteuning van de functies voor Information Rights Management (IRM) voor toepassingen zoals Word, Excel, PowerPoint, Outlook en Outlook Web App. Gebruikers hoeven zich alleen maar met hun [!INCLUDE[o365_1](../includes/o365_1_md.md)]-referenties aan te melden bij hun Office-toepassingen om bestanden en e-mails te beveiligen en om bestanden en e-mails te gebruiken die zijn beveiligd door anderen.

We raden echter aan deze toepassingen aan te vullen met de Rights Management-toepassing voor delen, zodat gebruikers kunnen beschikken over de handige Office-invoegtoepassing. Zie [Rights Management-toepassing voor delen: installatie en configuratie voor clients](configure-sharing-app.md) voor meer informatie.

## Exchange Online: IRM-configuratie
Als u Exchange Online wilt configureren voor ondersteuning van Azure RMS, moet u de Information Rights Management-service (IRM) voor Exchange Online configureren. Hiervoor gebruikt u Windows PowerShell (u hoeft geen afzonderlijke module te installeren), en voert u [PowerShell-opdrachten voor Exchange Online](https://technet.microsoft.com/library/jj200677.aspx) uit.

> [!NOTE]
> Het is momenteel niet mogelijk om Exchange Online te configureren voor ondersteuning van Azure RMS als u een door de klant beheerde tenantsleutel (BYOK) voor Azure RMS gebruikt, in plaats van de standaardconfiguratie van door Microsoft beheerde tenantsleutel. Zie [BYOK-prijzen en -beperkingen](../plan-design/byok-price-restrictions.md) voor meer informatie.
>
> Als u Exchange Online wilt configureren wanneer Azure RMS gebruikmaakt van BYOK, mislukt de opdracht voor het importeren van de sleutel (stap 5 in de volgende procedure) met het foutbericht **[FailureCategory=Cmdlet-FailedToGetTrustedPublishingDomainFromRmsOnlineException]**.

De volgende stappen bevatten een typische reeks opdrachten die u moet uitvoeren om in te schakelen Exchange Online voor het gebruik van Azure RMS:

1.  Als dit de eerste keer dat u Windows PowerShell voor Exchange Online hebt gebruikt op uw computer, moet u Windows PowerShell configureren voor het uitvoeren van ondertekende scripts. Start de Windows PowerShell-sessie met de optie **Als beheerder uitvoeren** en type vervolgens:

    ```
    Set-ExecutionPolicy RemoteSigned
    ```

2.  Meld u in de Windows PowerShell-sessie aan bij Exchange Online met een account dat is ingeschakeld voor toegang tot externe Shells. Alle accounts die zijn gemaakt in Exchange Online zijn standaard ingeschakeld voor externe toegang tot Shell, maar dit kan worden uitgeschakeld (en ingeschakeld) met de opdracht [Set-User &lt;UserIdentity&gt; -RemotePowerShellEnabled](https://technet.microsoft.com/library/jj984292%28v=exchg.160%29.aspx).

    Als u zich wilt aanmelden, typt u:

    ```
    $Cred = Get-Credential
    ```
    Voer in het dialoogvenster **Referentieaanvraag voor Windows PowerShell** uw Office 365-gebruikersnaam en -wachtwoord in.

3.  Maak verbinding met de Exchange Online-service door de volgende twee opdrachten uit te voeren:

    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell/ -Credential $Cred -Authentication Basic –AllowRedirection
    ```

    ```
    Import-PSSession $Session
    ```

4.  Geef de locatie op van de tenantsleutel voor Azure RMS, op basis van waar de tenant van uw organisatie is gemaakt:

    Voor Noord-Amerika (en overheidsabonnementen):

    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
    ```
    Voor Europa:

    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc"
    ```
    Voor Azië:

    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc"
    ```
    Voor Zuid-Amerika:

    ```
    Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc"
    ```

5.  Importeer de configuratiegegevens uit Azure RMS naar Exchange Online, in de vorm van het Trusted Publishing Domain (TPD). Dit omvat de Azure RMS-tenantsleutel en Azure RMS-sjablonen:

    ```
    Import-RMSTrustedPublishingDomain -RMSOnline -name "RMS Online"
    ```
    In deze opdracht wordt de naam **RMS Online** gebruikt als basisnaam van het TPD voor Azure RMS in Exchange Online. Nadat het TPD is geïmporteerd, heet dit **Online RMS - 1** in Exchange Online.

6.  Schakel de Azure RMS-functionaliteit in zodat IRM-functies beschikbaar zijn voor Exchange Online:

    ```
    Set-IRMConfiguration -InternalLicensingEnabled $true
    ```
    Na het uitvoeren van deze opdracht wordt de Rights Management automatisch ingeschakeld voor de Outlook-client, Outlook Web App en Exchange ActiveSync.

7.  Test indien gewenst of deze configuratie correct is voltooid met de volgende opdracht:

    ```
    Test-IRMConfiguration -Sender <user email address>
    ```
    Bijvoorbeeld: **Test-IRMConfiguration -Sender adams@contoso.com**

    Met deze opdracht wordt een serie controles uitgevoerd om de verbinding met de service te verifiëren, de configuratie, URI's, licenties en eventueel sjablonen op te halen. In de Windows PowerShell-sessie ziet u van elk onderdeel de resultaten en aan het einde, als alle onderdelen voor de controles slagen: **OVERALL RESULT: PASS**

8.  Verbreek de verbinding voor de externe PowerShell-sessie:

    ```
    Remove-PSSession $Session
    ```

Gebruikers kunnen nu hun e-mailberichten beveiligen met Azure RMS. Selecteer bijvoorbeeld in Outlook Web App de optie **Machtigingen instellen** in het uitgebreide menu (**...**) en kies vervolgens **Niet doorsturen** of een van de beschikbare sjablonen om gegevensbeveiliging toe te passen op het e-mailbericht en eventuele bijlagen. Omdat de gebruikersinterface echter een dag wordt opgeslagen in de cache in Outlook Web App, moet u na het uitvoeren van deze configuratieopdrachten wachten tot deze periode is verstreken voordat u informatiebeveiliging toepast op e-mailberichten. Voordat de gebruikersinterface is bijgewerkt en de nieuwe configuratie wordt weergegeven, ziet u geen opties in het menu **Machtigingen instellen**.

> [!IMPORTANT]
> Als u nieuwe [aangepaste sjablonen](configure-custom-templates.md) maakt voor Azure RMS of de sjablonen bijwerkt, moet u elke keer de volgende Exchange Online PowerShell-opdracht uitvoeren (voer indien nodig stap 2 en 3 eerst uit) om deze wijzigingen naar Exchange Online te synchroniseren: `Import-RMSTrustedPublishingDomain -Name "RMS Online - 1" -RefreshTemplates –RMSOnline`

Als Exchange-beheerder kunt u nu functies configureren waarmee gegevensbeveiliging automatisch wordt toegepast, zoals [Transportregels](https://technet.microsoft.com/library/dd302432.aspx), [Beleid ter preventie van gegevensverlies (DLP)](https://technet.microsoft.com/library/jj150527%28v=exchg.150%29.aspx), en [Beveiligde voicemail](https://technet.microsoft.com/library/dn198211%28v=exchg.150%29.aspx) (Unified Messaging).

Zie de documentatie in de Exchange-bibliotheek voor gedetailleerde instructies voor het configureren van Exchange Online om IRM-functionaliteit in te schakelen. Bijvoorbeeld:

-   [Verbinding maken met Exchange Online met externe PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)

-   [IRM configureren voor het gebruik van Azure Rights Management](https://technet.microsoft.com/library/dn151475%28v=exchg.150%29.aspx)

### Office 365-berichtversleuteling
Voer dezelfde stappen uit als beschreven in de vorige sectie. Als u echter niet wilt dat sjablonen worden weergegeven, voert u vóór stap 6 de volgende opdracht uit om te voorkomen dat IRM-sjablonen beschikbaar worden gesteld in Outlook Web App en de Outlook-client: `Set-IRMConfiguration -ClientAccessServerEnabled $false`

Vervolgens bent u klaar om [transportregels](https://technet.microsoft.com/library/dd302432.aspx) te configureren voor het automatisch wijzigen van berichtbeveiliging wanneer ontvangers zich buiten de organisatie bevinden, en selecteert u de optie **Office 365-berichtversleuteling**.

Zie [Encryption in Office 365](https://technet.microsoft.com/library/dn569286.aspx) (Versleuteling in Office 365) in de Exchange-bibliotheek voor meer informatie over berichtversleuteling.

## SharePoint Online en OneDrive voor Bedrijven: IRM-configuratie
Als u SharePoint Online en OneDrive voor Bedrijven wilt configureren voor ondersteuning van Azure RMS, moet u eerst de Information Rights Management-service (IRM) voor SharePoint Online inschakelen met het SharePoint-beheercentrum. Vervolgens kunnen site-eigenaren hun SharePoint-lijsten en documentbibliotheken met IRM beveiligen, en kunnen gebruikers hun bibliotheek van OneDrive voor Bedrijven met IRM beveiligen zodat documenten die daar worden opgeslagen en gedeeld met anderen automatisch worden beveiligd door Azure RMS.

Zie de volgende instructie van de Office-website voor het inschakelen van de Information Rights Management-service (IRM) voor SharePoint Online:

-   [Information Rights Management (IRM) instellen in het SharePoint-beheercentrum](http://office.microsoft.com/office365-sharepoint-online-enterprise-help/set-up-information-rights-management-irm-insharepoint-online-HA102895193.aspx)

Deze configuratie wordt uitgevoerd door de Office 365-beheerder.

### IRM configureren voor bibliotheken en lijsten
Nadat u de IRM-service voor SharePoint hebt ingeschakeld, kunnen site-eigenaren hun SharePoint-documentbibliotheken en -lijsten met IRM beveiligen. Zie de volgende informatie op de Office-website voor instructies:

-   [Information Rights Management toepassen op een lijst of bibliotheek](http://office.microsoft.com/sharepoint-help/apply-information-rights-management-to-a-list-or-library-HA102891460.aspx)

Deze configuratie wordt uitgevoerd door de beheerder van de SharePoint-site.

### IRM configureren voor OneDrive voor Bedrijven
Nadat u de IRM-service voor SharePoint Online hebt ingeschakeld, kan de OneDrive voor Bedrijven-documentbibliotheek van gebruikers worden geconfigureerd voor Rights Management-beveiliging.  Gebruikers kunnen dit voor zichzelf configureren via het pictogram **Instellingen** in hun OneDrive. Hoewel beheerders met het SharePoint-beheercentrum Rights Management niet kunnen configureren voor OneDrive voor Bedrijven van gebruikers, kunt u dit wel doen via Windows PowerShell.

> [!NOTE]
> Zie de Office-documentatie [Set up OneDrive for Business in Office 365](https://support.office.com/article/Set-up-OneDrive-for-Business-in-Office-365-3e21f8f0-e0a1-43be-aa3e-8c0236bf11bb) (OneDrive voor Bedrijven instellen in Office 365) voor meer informatie over het configureren van OneDrive voor Bedrijven.

#### Configuratie voor gebruikers
Geef gebruikers deze instructies zodat ze hun OneDrive voor Bedrijven kunnen configureren en zakelijke bestanden kunnen beveiligen met IRM.

1.  Klik in OneDrive op het pictogram **Instellingen** om het menu Instellingen te openen en klik vervolgens op **Site-inhoud**.

2.  Wijs met de muisaanwijzer de tegel **Documenten** aan, kies het beletselteken (**...**), en klik vervolgens op **INSTELLINGEN.**

3.  Klik op de pagina **Instellingen** in de sectie **Machtigingen en beheer** op **Information Rights Management**.

4.  Schakel op de pagina **Instellingen van Information Rights Management** het selectievakje **De machtigingen voor deze bibliotheek beperken bij het downloaden**, geef uw naamkeuze en een beschrijving voor de machtigingen op, klik desgewenst op **OPTIES WEERGEVEN** om optionele configuraties te configureren en klik vervolgens op **OK**.

    Zie de instructies in [Information Rights Management toepassen op een lijst of documentbibliotheek](https://support.office.com/article/Apply-Information-Rights-Management-to-a-list-or-library-3bdb5c4e-94fc-4741-b02f-4e7cc3c54aa1) in de Office-documentatie voor meer informatie over de configuratieopties.

Omdat deze configuratie afhankelijk is van IRM-beveiliging van bibliotheken voor OneDrive voor Bedrijven door de gebruiker in plaats van een beheerder, moet u gebruikers informeren over de voordelen van het beveiligen van hun bestanden en hoe ze dit moeten doen. Leg bijvoorbeeld uit dat als gebruikers een document van OneDrive voor Bedrijven delen, alleen de personen toegang hebben die zij hebben gemachtigd, met de beperkingen die ze zelf configureren, zelfs als het bestand wordt gewijzigd en naar een andere locatie wordt gekopieerd.

#### Configuratie voor beheerders
Hoewel u met het SharePoint-beheercentrum IRM niet kunt configureren voor OneDrive voor Bedrijven van gebruikers, kunt u dit wel doen via Windows PowerShell. Voer de volgende stappen uit om IRM voor deze bibliotheken in te schakelen:

1.  Download en installeer de [SharePoint Online-SDK voor clientonderdelen](http://www.microsoft.com/en-us/download/details.aspx?id=42038).

2.  Download en installeer de [SharePoint Online-beheershell](http://www.microsoft.com/en-us/download/details.aspx?id=35588).

3.  Kopieer de inhoud van het volgende script en noem het bestand Set-IRMOnOneDriveForBusiness.ps1 op uw computer.

    *&#42;&#42;Disclaimer&#42;&#42;*: dit voorbeeldscript wordt onder geen enkel een ondersteuningsprogramma of -service op basis van Microsoft-standaard ondersteund. Dit voorbeeldscript wordt verstrekt 'in de huidige vorm' zonder garantie van welke aard dan ook.

    ```
    # Requires Windows PowerShell version 3

    <#
      Description:

        Configures IRM policy settings for OneDrive for Business and can also be used for SharePoint Online libraries and lists

     Script Installation Requirements:

       SharePoint Online Client Components SDK
       http://www.microsoft.com/en-us/download/details.aspx?id=42038

       SharePoint Online Management Shell
       http://www.microsoft.com/en-us/download/details.aspx?id=35588

    ======
    #>

    # URL will be in the format https://<tenant-name>-admin.sharepoint.com
    $sharepointAdminCenterUrl = "https://contoso-admin.sharepoint.com"

    $tenantAdmin = "admin@contoso.com"

    $webUrls = @("https://contoso-my.sharepoint.com/personal/user1_contoso_com",
                 "https://contoso-my.sharepoint.com/personal/user2_contoso_com",
                 "https://contoso-my.sharepoint.com/personal/user3_contoso_com")

    <# As an alternative to specifying the URLs as an array, you can import them from a CSV file (no header, single value per row).
       Then, use: $webUrls = Get-Content -Path "File_path_and_name.csv"

    #>

    $listTitle = "Documents"

    function Load-SharePointOnlineClientComponentAssemblies
    {
        [cmdletbinding()]
        param()

        process
        {
            # assembly location: C:\Program Files\Common Files\microsoft shared\Web Server Extensions\16\ISAPI
            try
            {
                Write-Verbose "Loading Assembly: Microsoft.Office.Client.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c"
                [System.Reflection.Assembly]::Load("Microsoft.Office.Client.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null

                Write-Verbose "Loading Assembly: Microsoft.Office.Client.TranslationServices, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c"
                [System.Reflection.Assembly]::Load("Microsoft.Office.Client.TranslationServices, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null

                Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c"
                [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null

                Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.DocumentManagement, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c"
                [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.DocumentManagement, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null

                Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Publishing, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c"
                [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Publishing, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null

                Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Runtime, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c"
                [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Runtime, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null

                Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Search.Applications, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c"
                [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Search.Applications, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null

                Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Search, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c"
                [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Search, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null

                Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Taxonomy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c"
                [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Taxonomy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null

                Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.UserProfiles, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c"
                [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.UserProfiles, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null

                return $true
            }
            catch
            {
                if($_.Exception.Message -match "Could not load file or assembly")
                {
                    Write-Error -Message "Unable to load the SharePoint Server 2013 Client Components.`nDownload Location: http://www.microsoft.com/en-us/download/details.aspx?id=42038"
                }
                else
                {
                    Write-Error -Exception $_.Exception
                }
                return $false
            }
        }
    }

    function Load-SharePointOnlineModule
    {
        [cmdletbinding()]
        param()

        process
        {
            do
            {
                # Installation location: C:\Program Files\SharePoint Online Management Shell\Microsoft.Online.SharePoint.PowerShell
                $spoModule = Get-Module -Name Microsoft.Online.SharePoint.PowerShell -ErrorAction SilentlyContinue

                if(-not $spoModule)
                {
                    try
                    {
                        Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
                        return $true
                    }
                    catch
                    {
                        if($_.Exception.Message -match "Could not load file or assembly")
                        {
                            Write-Error -Message "Unable to load the SharePoint Online Management Shell.`nDownload Location: http://www.microsoft.com/en-us/download/details.aspx?id=35588"
                        }
                        else
                        {
                            Write-Error -Exception $_.Exception
                        }
                        return $false
                    }
                }
                else
                {
                    return $true
                }
            }
            while(-not $spoModule)
        }
    }

    function Set-IrmConfiguration
    {
        [cmdletbinding()]
        param(
            [parameter(Mandatory=$true)][Microsoft.SharePoint.Client.List]$List,
            [parameter(Mandatory=$true)][string]$PolicyTitle,
            [parameter(Mandatory=$true)][string]$PolicyDescription,
            [parameter(Mandatory=$false)][switch]$IrmReject,
            [parameter(Mandatory=$false)][DateTime]$ProtectionExpirationDate,
            [parameter(Mandatory=$false)][switch]$DisableDocumentBrowserView,
            [parameter(Mandatory=$false)][switch]$AllowPrint,
            [parameter(Mandatory=$false)][switch]$AllowScript,
            [parameter(Mandatory=$false)][switch]$AllowWriteCopy,
            [parameter(Mandatory=$false)][int]$DocumentAccessExpireDays,
            [parameter(Mandatory=$false)][int]$LicenseCacheExpireDays,
            [parameter(Mandatory=$false)][string]$GroupName
        )

        process
        {
            Write-Verbose "Applying IRM Configuration on '$($List.Title)'"

            # reset the value to the default settings
            $list.InformationRightsManagementSettings.Reset()

            $list.IrmEnabled = $true

            # IRM Policy title and description

                $list.InformationRightsManagementSettings.PolicyTitle       = $PolicyTitle
                $list.InformationRightsManagementSettings.PolicyDescription = $PolicyDescription

            # Set additional IRM library settings

                # Do not allow users to upload documents that do not support IRM
                $list.IrmReject = $IrmReject.IsPresent

                $parsedDate = Get-Date
                if([DateTime]::TryParse($ProtectionExpirationDate, [ref]$parsedDate))
                {
                    # Stop restricting access to the library at <date>
                    $list.IrmExpire = $true
                    $list.InformationRightsManagementSettings.DocumentLibraryProtectionExpireDate = $ProtectionExpirationDate
                }

                # Prevent opening documents in the browser for this Document Library
                $list.InformationRightsManagementSettings.DisableDocumentBrowserView = $DisableDocumentBrowserView.IsPresent

            # Configure document access rights

                # Allow viewers to print
                $list.InformationRightsManagementSettings.AllowPrint = $AllowPrint.IsPresent

                # Allow viewers to run script and screen reader to function on downloaded documents
                $list.InformationRightsManagementSettings.AllowScript = $AllowScript.IsPresent

                # Allow viewers to write on a copy of the downloaded document
                $list.InformationRightsManagementSettings.AllowWriteCopy = $AllowWriteCopy.IsPresent

                if($DocumentAccessExpireDays)
                {
                    # After download, document access rights will expire after these number of days (1-365)
                    $list.InformationRightsManagementSettings.EnableDocumentAccessExpire = $true
                    $list.InformationRightsManagementSettings.DocumentAccessExpireDays   = $DocumentAccessExpireDays
                }

            # Set group protection and credentials interval

                if($LicenseCacheExpireDays)
                {
                    # Users must verify their credentials using this interval (days)
                    $list.InformationRightsManagementSettings.EnableLicenseCacheExpire = $true
                    $list.InformationRightsManagementSettings.LicenseCacheExpireDays   = $LicenseCacheExpireDays
                }

                if($GroupName)
                {
                    # Allow group protection. Default group:
                    $list.InformationRightsManagementSettings.EnableGroupProtection = $true
                    $list.InformationRightsManagementSettings.GroupName             = $GroupName
                }
        }
        end
        {
            if($list)
            {
                Write-Verbose "Committing IRM configuration settings on '$($list.Title)'"
                $list.InformationRightsManagementSettings.Update()
                $list.Update()
                $script:clientContext.Load($list)
                $script:clientContext.ExecuteQuery()
            }
        }
    }

    function Get-CredentialFromCredentialCache
    {
        [cmdletbinding()]
        param([string]$CredentialName)

        #if( Test-Path variable:\global:CredentialCache )
        if( Get-Variable O365TenantAdminCredentialCache -Scope Global -ErrorAction SilentlyContinue )
        {
            if($global:O365TenantAdminCredentialCache.ContainsKey($CredentialName))
            {
                Write-Verbose "Credential Cache Hit: $CredentialName"
                return $global:O365TenantAdminCredentialCache[$CredentialName]
            }
        }
        Write-Verbose "Credential Cache Miss: $CredentialName"
        return $null
    }

    function Add-CredentialToCredentialCache
    {
        [cmdletbinding()]
        param([System.Management.Automation.PSCredential]$Credential)

        if(-not (Get-Variable CredentialCache -Scope Global -ErrorAction SilentlyContinue))
        {
            Write-Verbose "Initializing the Credential Cache"
            $global:O365TenantAdminCredentialCache = @{}
        }

        Write-Verbose "Adding Credential to the Credential Cache"
        $global:O365TenantAdminCredentialCache[$Credential.UserName] = $Credential
    }

    # load the required assemblies and Windows PowerShell modules

        if(-not ((Load-SharePointOnlineClientComponentAssemblies) -and (Load-SharePointOnlineModule)) ) { return }

    # Add the credentials to the client context and SharePoint Online service connection

        # check for cached credentials to use
        $o365TenantAdminCredential = Get-CredentialFromCredentialCache -CredentialName $tenantAdmin

        if(-not $o365TenantAdminCredential)
        {
            # when credentials are not cached, prompt for the tenant admin credentials
            $o365TenantAdminCredential = Get-Credential -UserName $tenantAdmin -Message "Enter the password for the Office 365 admin"

            if(-not $o365TenantAdminCredential -or -not $o365TenantAdminCredential.UserName -or $o365TenantAdminCredential.Password.Length -eq 0 )
            {
                Write-Error -Message "Could not validate the supplied tenant admin credentials"
                return
            }

            # add the credentials to the cache
            Add-CredentialToCredentialCache -Credential $o365TenantAdminCredential
        }

    # connect to Office365 first, required for SharePoint Online cmdlets to run

        Connect-SPOService -Url $sharepointAdminCenterUrl -Credential $o365TenantAdminCredential

    # enumerate each of the specified site URLs

        foreach($webUrl in $webUrls)
        {
            $grantedSiteCollectionAdmin = $false

            try
            {
                # establish the client context and set the credentials to connect to the site
                $script:clientContext = New-Object Microsoft.SharePoint.Client.ClientContext($webUrl)
                $script:clientContext.Credentials = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($o365TenantAdminCredential.UserName, $o365TenantAdminCredential.Password)

                # initialize the site and web context
                $script:clientContext.Load($script:clientContext.Site)
                $script:clientContext.Load($script:clientContext.Web)
                $script:clientContext.ExecuteQuery()

                # load and ensure the tenant admin user account if present on the target SharePoint site
                $tenantAdminUser = $script:clientContext.Web.EnsureUser($o365TenantAdminCredential.UserName)
                $script:clientContext.Load($tenantAdminUser)
                $script:clientContext.ExecuteQuery()

                # check if the tenant admin is a site admin
                if( -not $tenantAdminUser.IsSiteAdmin )
                {
                    try
                    {
                        # grant the tenant admin temporary admin rights to the site collection
                        Set-SPOUser -Site $script:clientContext.Site.Url -LoginName $o365TenantAdminCredential.UserName -IsSiteCollectionAdmin $true | Out-Null
                        $grantedSiteCollectionAdmin = $true
                    }
                    catch
                    {
                        Write-Error $_.Exception
                        return
                    }
                }

                try
                {
                    # load the list orlibrary using CSOM

                    $list = $null
                    $list = $script:clientContext.Web.Lists.GetByTitle($listTitle)
                    $script:clientContext.Load($list)
                    $script:clientContext.ExecuteQuery()

                    # **************  ADMIN INSTRUCTIONS  **************
                    # If necessary, modify the following Set-IrmConfiguration parameters to match your required values
                    # The supplied options and values are for example only
                    # Example that shows the Set-IrmConfiguration command with all parameters: Set-IrmConfiguration -List $list -PolicyTitle "Protected Files" -PolicyDescription "This policy restricts access to authorized users" -IrmReject -ProtectionExpirationDate $(Get-Date).AddDays(180) -DisableDocumentBrowserView -AllowPrint -AllowScript -AllowWriteCopy -LicenseCacheExpireDays 25 -DocumentAccessExpireDays 90

                    Set-IrmConfiguration -List $list -PolicyTitle "Protected Files" -PolicyDescription "This policy restricts access to authorized users"  
                }
                catch
                {
                    Write-Error -Message "Error setting IRM configuration on site: $webUrl.`nError Details: $($_.Exception.ToString())"
                }
           }
           finally
           {
                if($grantedSiteCollectionAdmin)
                {
                    # remove the temporary admin rights to the site collection
                    Set-SPOUser -Site $script:clientContext.Site.Url -LoginName $o365TenantAdminCredential.UserName -IsSiteCollectionAdmin $false | Out-Null
                }
           }
        }

    Disconnect-SPOService -ErrorAction SilentlyContinue
    ```

4.  Bekijk het script en breng de volgende wijzigingen aan:

    1.  Zoek naar `$sharepointAdminCenterUrl` en vervang de voorbeeldwaarde door de URL van uw eigen SharePoint-beheercentrum.

        U vindt deze waarde als de basis-URL als u naar het SharePoint-beheercentrum gaat. De URL heeft de volgende indeling: https://*&lt;tenant_name&gt;*-admin.sharepoint.com

        Als de naam van de tenant bijvoorbeeld 'contoso' is, geeft u het volgende op: **https://contoso-admin.sharepoint.com**

    2.  Zoek naar `$tenantAdmin` en vervang de voorbeeldwaarde door uw eigen volledig gekwalificeerde account van de algemeen beheerder van Office 365.

        Deze waarde is hetzelfde als de waarde die u gebruikt om u als algemeen beheerder aan te melden bij het Office 365-beheerportal en heeft de volgende indeling: gebruikersnaam@*&lt;tenant domeinnaam&gt;*.com

        Als de gebruikersnaam voor de algemeen beheerder van Office 365 'admin' is voor het domein van de tenant 'contoso.com', voert u in: **admin@contoso.com**

    3.  Zoek naar `$webUrls` en vervang de voorbeeldwaarden door de web-URL’s van OneDrive voor Bedrijven van uw gebruikers. U kunt hierbij naar behoefte waarden invoeren of verwijderen.

        U kunt ook de opmerkingen in het script volgen over hoe u een CSV-bestand kunt importeren met alle URL's die u wilt configureren.  Er is nog een ander voorbeeldscript beschikbaar voor het automatisch zoeken en extraheren van de URL's om dit CSV-bestand in te vullen. Als u klaar bent voor deze stap, gaat u naar de sectie [Extra script om alle URL's van OneDrive voor Bedrijven naar een .CSV-bestand uit te voeren](#additional-script-to-output-all-onedrive-for-business-urls-to-a-csv-file), direct na deze stappen.

        De indeling van de web-URL voor OneDrive voor Bedrijven van de gebruikers, is als volgt: https://*&lt;tenantnaam&gt;*-my.sharepoint.com/personal/*&lt;gebruikersnaam&gt;*_*&lt;tenantnaam&gt;*_com

        Als bijvoorbeeld de gebruikersnaam van een gebruiker in de contoso-tenant 'rsimone' is, voert u het volgende in: **https://contoso-my.sharepoint.com/personal/rsimone_contoso_com**

    4.  Als u het script gebruikt voor de configuratie van OneDrive voor Bedrijven, mag u de waarde voor **Documenten** niet veranderen in de variabele voor `$listTitle`.

    5.  Zoek naar `ADMIN INSTRUCTIONS`. Als u geen wijzigingen aanbrengt in deze sectie, wordt de OneDrive voor Bedrijven van de gebruiker geconfigureerd voor IRM met de beleidsnaam 'Beveiligde bestanden' en de beschrijving 'This policy restricts access to authorized users' (Dit beleid beperkt toegang tot geautoriseerde gebruikers).  Er worden geen andere IRM-opties ingesteld. Voor de meeste omgevingen is dit waarschijnlijk voldoende. U kunt echter de voorgestelde beleidsnaam en de beschrijving wijzigen. Verder kunt u andere IRM-opties toevoegen die geschikt zijn voor uw omgeving. Zie het voorbeeld met de opmerkingen in het script om uw eigen set parameters voor de opdracht Set-IrmConfiguration samen te stellen.

5.  Sla het script op en onderteken het. Als u het script niet ondertekent (veiliger), moet u Windows PowerShell op de computer configureren voor het uitvoeren van niet-ondertekende scripts. Hiervoor voert u een Windows PowerShell-sessie uit met de optie **Als beheerder uitvoeren** en typt u: **Set-ExecutionPolicy Unrestricted**. Met deze configuratie kunnen echter alle niet-ondertekende scripts worden uitgevoerd (minder veilig).

    Zie [about_Signing](https://technet.microsoft.com/library/hh847874.aspx) in de PowerShell-documentatiebibliotheek voor meer informatie over het ondertekenen van Windows PowerShell-scripts.

6.  Voer het script uit en geef, wanneer u hierom wordt gevraagd, het wachtwoord op voor het Office 365-beheeraccount. Als u het script wijzigt en uitvoert in dezelfde Windows PowerShell-sessie, wordt u niet gevraagd om referenties.

> [!TIP]
> U kunt ook dit script ook gebruiken om IRM te configureren voor een SharePoint Online-bibliotheek. Voor deze configuratie wilt u waarschijnlijk de extra optie **Gebruikers niet toestaan om documenten te uploaden die IRM niet ondersteunen** inschakelen, om ervoor te zorgen dat de bibliotheek alleen beveiligde documenten bevat.    Voeg hiervoor de parameter `-IrmReject` toe aan de opdracht Set-IrmConfiguration in het script.
>
> U moet tevens de variabele `$webUrls` (bijvoorbeeld **https://contoso.sharepoint.com**) en de variabele `$listTitle` (bijvoorbeeld **$Reports**) wijzigen.

Zie de sectie [Script voor het uitschakelen van IRM voor OneDrive voor Bedrijven](#script-to-disable-irm-for-onedrive-for-business) als u IRM voor de bibliotheken voor OneDrive voor Bedrijven van de gebruiker moet uitschakelen.

##### Extra script voor uitvoer van alle URL’s van OneDrive voor Bedrijven naar een CSV-bestand
Voor stap 4c hierboven kunt u het volgende Windows PowerShell-script gebruiken om de URL's voor de bibliotheken voor OneDrive voor Bedrijven van gebruikers te extraheren. Deze kunt u vervolgens controleren, indien nodig bewerken en vervolgens importeren in het hoofdscript.

Voor dit script zijn tevens de [SharePoint Online SDK voor clientonderdelen](http://www.microsoft.com/en-us/download/details.aspx?id=42038) en de [SharePoint Online-beheershell](http://www.microsoft.com/en-us/download/details.aspx?id=35588) vereist. Volg dezelfde instructies voor het kopiëren en plakken, sla het bestand lokaal op (bijvoorbeeld 'Report-OneDriveForBusinessSiteInfo.ps1'), wijzigen de waarden `$sharepointAdminCenterUrl` en `$tenantAdmin` zoals eerder en voer het script uit.

*&#42;&#42;Disclaimer&#42;&#42;*: dit voorbeeldscript wordt onder geen enkel een ondersteuningsprogramma of -service op basis van Microsoft-standaard ondersteund. Dit voorbeeldscript wordt verstrekt 'in de huidige vorm' zonder garantie van welke aard dan ook.

```
# Requires Windows PowerShell version 3

<#
  Description:

    Queries the search service of an Office 365 tenant to retrieve all OneDrive for Business sites.  
    Details of the discovered sites are written to a .CSV file (by default,"OneDriveForBusinessSiteInfo_<date>.csv").

 Script Installation Requirements:

   SharePoint Online Client Components SDK
   http://www.microsoft.com/en-us/download/details.aspx?id=42038

   SharePoint Online Management Shell
   http://www.microsoft.com/en-us/download/details.aspx?id=35588

======
#>

# URL will be in the format https://<tenant-name>-admin.sharepoint.com
$sharepointAdminCenterUrl = "https://contoso-admin.sharepoint.com"

$tenantAdmin = "admin@contoso.onmicrosoft.com"                           

$reportName = "OneDriveForBusinessSiteInfo_$((Get-Date).ToString("yyyy-MM-dd_hh.mm.ss")).csv"

$oneDriveForBusinessSiteUrls= @()
$resultsProcessed = 0

function Load-SharePointOnlineClientComponentAssemblies
{
    [cmdletbinding()]
    param()

    process
    {
        # assembly location: C:\Program Files\Common Files\microsoft shared\Web Server Extensions\16\ISAPI
        try
        {
            Write-Verbose "Loading Assembly: Microsoft.Office.Client.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c"
            [System.Reflection.Assembly]::Load("Microsoft.Office.Client.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null

            Write-Verbose "Loading Assembly: Microsoft.Office.Client.TranslationServices, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c"
            [System.Reflection.Assembly]::Load("Microsoft.Office.Client.TranslationServices, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null

            Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c"
            [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null

            Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.DocumentManagement, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c"
            [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.DocumentManagement, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null

            Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Publishing, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c"
            [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Publishing, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null

            Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Runtime, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c"
            [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Runtime, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null

            Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Search.Applications, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c"
            [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Search.Applications, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null

            Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Search, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c"
            [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Search, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null

            Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Taxonomy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c"
            [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Taxonomy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null

            Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.UserProfiles, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c"
            [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.UserProfiles, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null

            return $true
        }
        catch
        {
            if($_.Exception.Message -match "Could not load file or assembly")
            {
                Write-Error -Message "Unable to load the SharePoint Server 2013 Client Components.`nDownload Location: http://www.microsoft.com/en-us/download/details.aspx?id=42038"
            }
            else
            {
                Write-Error -Exception $_.Exception
            }
            return $false
        }
    }
}

function Load-SharePointOnlineModule
{
    [cmdletbinding()]
    param()

    process
    {
        do
        {
            # Installation location: C:\Program Files\SharePoint Online Management Shell\Microsoft.Online.SharePoint.PowerShell
            $spoModule = Get-Module -Name Microsoft.Online.SharePoint.PowerShell -ErrorAction SilentlyContinue

            if(-not $spoModule)
            {
                try
                {
                    Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
                    return $true
                }
                catch
                {
                    if($_.Exception.Message -match "Could not load file or assembly")
                    {
                        Write-Error -Message "Unable to load the SharePoint Online Management Shell.`nDownload Location: http://www.microsoft.com/en-us/download/details.aspx?id=35588"
                    }
                    else
                    {
                        Write-Error -Exception $_.Exception
                    }
                    return $false
                }
            }
            else
            {
                return $true
            }
        }
        while(-not $spoModule)
    }
}

function Get-CredentialFromCredentialCache
{
    [cmdletbinding()]
    param([string]$CredentialName)

    #if( Test-Path variable:\global:CredentialCache )
    if( Get-Variable O365TenantAdminCredentialCache -Scope Global -ErrorAction SilentlyContinue )
    {
        if($global:O365TenantAdminCredentialCache.ContainsKey($CredentialName))
        {
            Write-Verbose "Credential Cache Hit: $CredentialName"
            return $global:O365TenantAdminCredentialCache[$CredentialName]
        }
    }
    Write-Verbose "Credential Cache Miss: $CredentialName"
    return $null
}

function Add-CredentialToCredentialCache
{
    [cmdletbinding()]
    param([System.Management.Automation.PSCredential]$Credential)

    if(-not (Get-Variable CredentialCache -Scope Global -ErrorAction SilentlyContinue))
    {
        Write-Verbose "Initializing the Credential Cache"
        $global:O365TenantAdminCredentialCache = @{}
    }

    Write-Verbose "Adding Credential to the Credential Cache"
    $global:O365TenantAdminCredentialCache[$Credential.UserName] = $Credential
}

# load the required assemblies and Windows PowerShell modules

    if(-not ((Load-SharePointOnlineClientComponentAssemblies) -and (Load-SharePointOnlineModule)) ) { return }

# Add the credentials to the client context and SharePoint Online service connection

    # check for cached credentials to use
    $o365TenantAdminCredential = Get-CredentialFromCredentialCache -CredentialName $tenantAdmin

    if(-not $o365TenantAdminCredential)
    {
        # when credentials are not cached, prompt for the tenant admin credentials
        $o365TenantAdminCredential = Get-Credential -UserName $tenantAdmin -Message "Enter the password for the Office 365 admin"

        if(-not $o365TenantAdminCredential -or -not $o365TenantAdminCredential.UserName -or $o365TenantAdminCredential.Password.Length -eq 0 )
        {
            Write-Error -Message "Could not validate the supplied tenant admin credentials"
            return
        }

        # add the credentials to the cache
        Add-CredentialToCredentialCache -Credential $o365TenantAdminCredential
    }

# establish the client context and set the credentials to connect to the site

    $clientContext = New-Object Microsoft.SharePoint.Client.ClientContext($sharepointAdminCenterUrl)
    $clientContext.Credentials = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($o365TenantAdminCredential.UserName, $o365TenantAdminCredential.Password)

# run a query against the Office 365 tenant search service to retrieve all OneDrive for Business URLs

    do
    {
        # build the query object
        $query = New-Object Microsoft.SharePoint.Client.Search.Query.KeywordQuery($clientContext)
        $query.TrimDuplicates        = $false
        $query.RowLimit              = 500
        $query.QueryText             = "SPSiteUrl:'/personal/' AND contentclass:STS_Site"
        $query.StartRow              = $resultsProcessed
        $query.TotalRowsExactMinimum = 500000

        # run the query
        $searchExecutor = New-Object Microsoft.SharePoint.Client.Search.Query.SearchExecutor($clientContext)
        $queryResults = $searchExecutor.ExecuteQuery($query)
        $clientContext.ExecuteQuery()

        # enumerate the search results and store the site URLs
        $queryResults.Value[0].ResultRows | % {
            $oneDriveForBusinessSiteUrls += $_.Path
            $resultsProcessed++
        }
    }
    while($resultsProcessed -lt $queryResults.Value.TotalRows)

$oneDriveForBusinessSiteUrls | Out-File -FilePath $reportName
```

##### Script voor het uitschakelen van IRM voor OneDrive voor Bedrijven
Gebruik het volgende voorbeeldscript gebruiken als u IRM voor OneDrive voor Bedrijven van gebruikers moet uitschakelen.

Voor dit script zijn tevens de [SharePoint Online SDK voor clientonderdelen](http://www.microsoft.com/en-us/download/details.aspx?id=42038) en de [SharePoint Online-beheershell](http://www.microsoft.com/en-us/download/details.aspx?id=35588) vereist. Kopieer en plak de inhoud, sla het bestand lokaal op (bijvoorbeeld 'Disable-IRMOnOneDriveForBusiness.ps1') en wijzigen de waarden `$sharepointAdminCenterUrl` en `$tenantAdmin`. Geef handmatig de URL’s van OneDrive voor Bedrijven op of gebruik het script in de voorgaande sectie zodat u deze kunt importeren, en voer vervolgens het script uit.

*&#42;&#42;Disclaimer&#42;&#42;*: dit voorbeeldscript wordt onder geen enkel een ondersteuningsprogramma of -service op basis van Microsoft-standaard ondersteund. Dit voorbeeldscript wordt verstrekt 'in de huidige vorm' zonder garantie van welke aard dan ook.

```
# Requires Windows PowerShell version 3

<#
  Description:

    Disables IRM for OneDrive for Business and can also be used for SharePoint Online libraries and lists

 Script Installation Requirements:

   SharePoint Online Client Components SDK
   http://www.microsoft.com/en-us/download/details.aspx?id=42038

   SharePoint Online Management Shell
   http://www.microsoft.com/en-us/download/details.aspx?id=35588

======
#>

$sharepointAdminCenterUrl = "https://contoso-admin.sharepoint.com"

$tenantAdmin = "admin@contoso.com"

$webUrls = @("https://contoso-my.sharepoint.com/personal/user1_contoso_com",
             "https://contoso-my.sharepoint.com/personal/user2_contoso_com",
             "https://contoso-my.sharepoint.com/personal/person3_contoso_com")

<# As an alternative to specifying the URLs as an array, you can import them from a CSV file (no header, single value per row).
   Then, use: $webUrls = Get-Content -Path "File_path_and_name.csv"

#>

$listTitle = "Documents"

function Load-SharePointOnlineClientComponentAssemblies
{
    [cmdletbinding()]
    param()

    process
    {
        # assembly location: C:\Program Files\Common Files\microsoft shared\Web Server Extensions\16\ISAPI
        try
        {
            Write-Verbose "Loading Assembly: Microsoft.Office.Client.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c"
            [System.Reflection.Assembly]::Load("Microsoft.Office.Client.Policy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null

            Write-Verbose "Loading Assembly: Microsoft.Office.Client.TranslationServices, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c"
            [System.Reflection.Assembly]::Load("Microsoft.Office.Client.TranslationServices, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null

            Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c"
            [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null

            Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.DocumentManagement, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c"
            [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.DocumentManagement, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null

            Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Publishing, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c"
            [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Publishing, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null

            Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Runtime, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c"
            [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Runtime, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null

            Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Search.Applications, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c"
            [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Search.Applications, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null

            Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Search, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c"
            [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Search, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null

            Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.Taxonomy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c"
            [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.Taxonomy, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null

            Write-Verbose "Loading Assembly: Microsoft.SharePoint.Client.UserProfiles, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c"
            [System.Reflection.Assembly]::Load("Microsoft.SharePoint.Client.UserProfiles, Version=16.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c") | Out-Null

            return $true
        }
        catch
        {
            if($_.Exception.Message -match "Could not load file or assembly")
            {
                Write-Error -Message "Unable to load the SharePoint Server 2013 Client Components.`nDownload Location: http://www.microsoft.com/en-us/download/details.aspx?id=42038"
            }
            else
            {
                Write-Error -Exception $_.Exception
            }
            return $false
        }
    }
}

function Load-SharePointOnlineModule
{
    [cmdletbinding()]
    param()

    process
    {
        do
        {
            # Installation location: C:\Program Files\SharePoint Online Management Shell\Microsoft.Online.SharePoint.PowerShell
            $spoModule = Get-Module -Name Microsoft.Online.SharePoint.PowerShell -ErrorAction SilentlyContinue

            if(-not $spoModule)
            {
                try
                {
                    Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
                    return $true
                }
                catch
                {
                    if($_.Exception.Message -match "Could not load file or assembly")
                    {
                        Write-Error -Message "Unable to load the SharePoint Online Management Shell.`nDownload Location: http://www.microsoft.com/en-us/download/details.aspx?id=35588"
                    }
                    else
                    {
                        Write-Error -Exception $_.Exception
                    }
                    return $false
                }
            }
            else
            {
                return $true
            }
        }
        while(-not $spoModule)
    }
}

function Remove-IrmConfiguration
{
    [cmdletbinding()]
    param(
        [parameter(Mandatory=$true)][Microsoft.SharePoint.Client.List]$List
    )

    process
    {
        Write-Verbose "Disabling IRM Configuration on '$($List.Title)'"

        $List.IrmEnabled = $false
        $List.IrmExpire  = $false
        $List.IrmReject  = $false
        $List.InformationRightsManagementSettings.Reset()
    }
    end
    {
        if($List)
        {
            Write-Verbose "Committing IRM configuration settings on '$($list.Title)'"
            $list.InformationRightsManagementSettings.Update()
            $list.Update()
            $script:clientContext.Load($list)
            $script:clientContext.ExecuteQuery()
        }
    }
}

function Get-CredentialFromCredentialCache
{
    [cmdletbinding()]
    param([string]$CredentialName)

    #if( Test-Path variable:\global:CredentialCache )
    if( Get-Variable O365TenantAdminCredentialCache -Scope Global -ErrorAction SilentlyContinue )
    {
        if($global:O365TenantAdminCredentialCache.ContainsKey($CredentialName))
        {
            Write-Verbose "Credential Cache Hit: $CredentialName"
            return $global:O365TenantAdminCredentialCache[$CredentialName]
        }
    }
    Write-Verbose "Credential Cache Miss: $CredentialName"
    return $null
}

function Add-CredentialToCredentialCache
{
    [cmdletbinding()]
    param([System.Management.Automation.PSCredential]$Credential)

    if(-not (Get-Variable CredentialCache -Scope Global -ErrorAction SilentlyContinue))
    {
        Write-Verbose "Initializing the Credential Cache"
        $global:O365TenantAdminCredentialCache = @{}
    }

    Write-Verbose "Adding Credential to the Credential Cache"
    $global:O365TenantAdminCredentialCache[$Credential.UserName] = $Credential
}

# load the required assemblies and Windows PowerShell modules

    if(-not ((Load-SharePointOnlineClientComponentAssemblies) -and (Load-SharePointOnlineModule)) ) { return }

# Add the credentials to the client context and SharePoint Online service connection

    # check for cached credentials to use
    $o365TenantAdminCredential = Get-CredentialFromCredentialCache -CredentialName $tenantAdmin

    if(-not $o365TenantAdminCredential)
    {
        # when credentials are not cached, prompt for the tenant admin credentials
        $o365TenantAdminCredential = Get-Credential -UserName $tenantAdmin -Message "Enter the password for the Office 365 admin"

        if(-not $o365TenantAdminCredential -or -not $o365TenantAdminCredential.UserName -or $o365TenantAdminCredential.Password.Length -eq 0 )
        {
            Write-Error -Message "Could not validate the supplied tenant admin credentials"
            return
        }

        # add the credentials to the cache
        Add-CredentialToCredentialCache -Credential $o365TenantAdminCredential
    }

# connect to Office365 first, required for SharePoint Online cmdlets to run

    Connect-SPOService -Url $sharepointAdminCenterUrl -Credential $o365TenantAdminCredential

# enumerate each of the specified site URLs

    foreach($webUrl in $webUrls)
    {
        $grantedSiteCollectionAdmin = $false

        try
        {
            # establish the client context and set the credentials to connect to the site
            $script:clientContext = New-Object Microsoft.SharePoint.Client.ClientContext($webUrl)
            $script:clientContext.Credentials = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($o365TenantAdminCredential.UserName, $o365TenantAdminCredential.Password)

            # initialize the site and web context
            $script:clientContext.Load($script:clientContext.Site)
            $script:clientContext.Load($script:clientContext.Web)
            $script:clientContext.ExecuteQuery()

            # load and ensure the tenant admin user account if present on the target SharePoint site
            $tenantAdminUser = $script:clientContext.Web.EnsureUser($o365TenantAdminCredential.UserName)
            $script:clientContext.Load($tenantAdminUser)
            $script:clientContext.ExecuteQuery()

            # check if the tenant admin is a site admin
            if( -not $tenantAdminUser.IsSiteAdmin )
            {
                try
                {
                    # grant the tenant admin temporary admin rights to the site collection
                    Set-SPOUser -Site $script:clientContext.Site.Url -LoginName $o365TenantAdminCredential.UserName -IsSiteCollectionAdmin $true | Out-Null
                    $grantedSiteCollectionAdmin = $true
                }
                catch
                {
                    Write-Error $_.Exception
                    return
                }
            }

            try
            {
                # load the list orlibrary using CSOM

                $list = $null
                $list = $script:clientContext.Web.Lists.GetByTitle($listTitle)
                $script:clientContext.Load($list)
                $script:clientContext.ExecuteQuery()

               Remove-IrmConfiguration -List $list                 
            }
            catch
            {
                Write-Error -Message "Error setting IRM configuration on site: $webUrl.`nError Details: $($_.Exception.ToString())"
            }
       }
       finally
       {
            if($grantedSiteCollectionAdmin)
            {
                # remove the temporary admin rights to the site collection
                Set-SPOUser -Site $script:clientContext.Site.Url -LoginName $o365TenantAdminCredential.UserName -IsSiteCollectionAdmin $false | Out-Null
            }
       }
    }

Disconnect-SPOService -ErrorAction SilentlyContinue
```




<!--HONumber=Aug16_HO4-->


