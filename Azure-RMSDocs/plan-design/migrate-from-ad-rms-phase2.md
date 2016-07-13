---
title: Migreren van AD RMS naar Azure Rights Management - Fase 2 | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 06/23/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: e3fd9bd9-3638-444a-a773-e1d5101b1793
ms.reviewer: esaggese
ms.suite: ems
ms.sourcegitcommit: a9dc45fb5146b0a4d2f013bff9d090723ce95ee5
ms.openlocfilehash: 1016ecdd77e818840f2a2cfab8212e908291bb89


---
# Migratiefase 2: configuratie aan de clientzijde

*Van toepassing op: Active Directory Rights Management Services, Azure Rights Management*

Gebruik de volgende informatie voor fase 2 van de migratie van AD RMS naar Azure Rights Management (Azure RMS). Deze procedures beslaan stap 5 van [Migreren van AD RMS naar Azure Rights Management](migrate-from-ad-rms-to-azure-rms.md).


## Stap 5. Clients opnieuw configureren voor het gebruik van Azure RMS
Voor Windows-clients:

1.  [Download de migratiescripts](http://go.microsoft.com/fwlink/?LinkId=524619):

    -   CleanUpRMS_RUN_Elevated.cmd

    -   Redirect_OnPrem.cmd

    Deze scripts stellen de configuratie van Windows-computers opnieuw in, zodat ze de Azure RMS-service in plaats van AD RMS gebruiken.

2.  Volg de instructies in het omleidingsscript (Redirect_OnPrem.cmd) om het script te laten verwijzen naar uw nieuwe Azure RMS-tenant.

    > [!IMPORTANT]
    > In de instructies vindt u een voorbeeld van hoe u de voorbeeldadressen **adrms** en **adrms.contoso.com** kunt vervangen door de adressen van uw eigen AD RMS-servers. Wanneer u dit doet, moet u erop letten dat er geen extra spaties vóór of na de adressen worden weergegeven. Deze extra spaties zorgen ervoor dat het migratiescript wordt onderbroken en zijn moeilijk te identificeren als de hoofdoorzaak van het probleem. In sommige bewerkingsprogramma's wordt na het plakken van tekst automatisch een spatie toegevoegd.

3. Gebruikers van Office 2016: de scripts zijn nog niet bijgewerkt met de configuratie voor Office 2016, dus als gebruikers met deze Office-versie werken, moet u de scripts handmatig bijwerken:

    - Voor **CleanUpRMS.cmd** - Zoek de regel `reg delete HKCU\Software\Microsoft\Office\15.0\Common\DRM /f` en voeg direct hieronder de volgende regel toe:

            reg delete HKCU\Software\Microsoft\Office\16.0\Common\DRM /f

    - Voor **Redirect_Onprem.cmd** - Zoek de regel `reg add "HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\DRM" /t REG_SZ /v "DefaultServer" /d "%CloudRMS%" /F1` en voeg direct hieronder de volgende twee regels toe:

            reg add "HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Common\DRM" /t REG_SZ /v "DefaultServerUrl" /d "https://%CloudRMS%/_wmcs/licensing" /F 

            reg add "HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Common\DRM" /t REG_SZ /v "DefaultServer" /d "%CloudRMS%" /F

    Optioneel: De scripts bevatten geen verwijzing naar Office 2016 in de opmerkingen. Als u de opmerkingen wilt bijwerken zodat deze toevoegingen voor Office 2016 worden weergegeven, brengt u de volgende wijzigingen aan in **Redirect_Onprem.cmd**:

    - Zoek `::     or MSIPC (Office 2013) with on-premises AD RMS` en vervang deze waarde door het volgende:
    
            ::     or MSIPC (Office 2013 and 2016) with on-premises AD RMS

    - Zoek `echo Redirect SCP for Office 2013` en vervang deze waarde door het volgende:
    
            echo Redirect SCP for Office versions based on MSIPC

    - Zoek `echo Redirect MSIPC for Office 2013` en vervang deze waarde door het volgende:
    
            echo Redirect MSIPC for Office versions based on MSIPC

4.  Op Windows-computers:

    - voer deze scripts met verhoogde bevoegdheden uit in de context van de gebruiker.

    Voor mobiele-apparaatclients en Mac-computers:

    -  Verwijder de DNS SRV-records die u hebt gemaakt tijdens de implementatie van de [AD RMS-extensie voor mobiele apparaten](http://technet.microsoft.com/library/dn673574.aspx).

#### Wijzigingen gemaakt door de migratiescripts
In dit gedeelte worden de wijzigingen gedocumenteerd die de migratiescripts aanbrengen. U kunt deze informatie gebruiken voor referentiedoeleinden, voor het oplossen van problemen of voor het aanbrengen van de wijzigingen (als u dit liever zelf doet).

CleanUpRMS_RUN_Elevated.cmd:

-   Verwijder de inhoud van de mappen %userprofile%\AppData\Local\Microsoft\DRM en %userprofile%\AppData\Local\Microsoft\MSIPC, met inbegrip van alle submappen en bestanden met lange bestandsnamen.

-   Verwijder de inhoud van de volgende registersleutels:

    -   HKEY_LOCAL_MACHINE\Software\Microsoft\Office\(11.0|12.0|14.0)\Common\DRM

    -   HKEY_CURRENT_USER\Software\Microsoft\Office\(11.0|12.0|14.0)\Common\DRM

    -   HKEY_LOCAL_MACHINE\Software\WoW6432Node\Microsoft\Office\(11.0|12.0|14.0)\Common\DRM

    -   HKEY_CURRENT_USER\Software\WoW6432Node\Microsoft\Office\(11.0|12.0|14.0)\Common\DRM

    -   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation

    -   HKEY_LOCAL_MACHINE\SOFTWARE\WoW6432Node\Microsoft\MSIPC\ServiceLocation

    -   HKEY_LOCAL_MACHINE\Software\Microsoft\MSDRM\ServiceLocation

-   Voeg de volgende registerwaarden toe:

    -   HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\DRM\DefaultServerURL

    -   HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\DRM\DefaultServer

Redirect_OnPrem.cmd:

-   Maak de volgende registerwaarden voor elke URL die is opgegeven als parameter bij elk van de volgende locaties:

    -   HKEY_CURRENT_USER\Software\Microsoft\Office\(11.0|12.0|14.0)\Common\DRM\LicenseServerRedirection

    -   HKEY_CURRENT_USER\Software\WoW6432Node\Microsoft\Office\(11.0|12.0|14.0)\Common\DRM\LicenseServerRedirection

    -   HKEY_LOCAL_MACHINE\Software\Microsoft\Office\(11.0|12.0|14.0)\Common\DRM\LicenseServerRedirection

    -   HKEY_LOCAL_MACHINE\Software\WoW6432Node\Microsoft\Office\(11.0|12.0|14.0)\Common\DRM\LicenseServerRedirection

    -   HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC\LicensingRedirection

    Elk item heeft een REG_SZ-waarde van **https://OldRMSserverURL/_wmcs/licensing** met de gegevens in de volgende indeling: **https://&lt;YourTenantURL&gt;/_wmcs/licensing**.

    > [!NOTE]
    > *&lt;YourTenantURL&gt;* heeft de volgende indeling: **{GUID}.rms.[Region].aadrm.com**.
    > 
    > Bijvoorbeeld: 5c6bb73b-1038-4eec-863d-49bded473437.rms.na.aadrm.com
    > 
    > U kunt deze waarde vinden door de waarde **RightsManagementServiceId** te identificeren tijdens het uitvoeren van de cmdlet [Get-AadrmConfiguration](http://msdn.microsoft.com/library/windowsazure/dn629410.aspx) voor Azure RMS.


## Volgende stappen
Als u wilt doorgaan met de migratie, gaat u naar [Stap 3: configuratie van ondersteuningsservices](migrate-from-ad-rms-phase3.md).


<!--HONumber=Jul16_HO2-->


