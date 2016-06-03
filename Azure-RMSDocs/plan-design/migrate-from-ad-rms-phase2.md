---
# required metadata

title: Migreren van AD RMS naar Azure Rights Management - Fase 2 | Azure RMS
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: e3fd9bd9-3638-444a-a773-e1d5101b1793


# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

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

3.  Voer deze scripts met verhoogde bevoegdheden op de Windows-computers uit in de context van de gebruiker.

Voor mobiele-apparaatclients en Mac-computers:

-   Verwijder de DNS SRV-records die u hebt gemaakt tijdens de implementatie van de [AD RMS-extensie voor mobiele apparaten](http://technet.microsoft.com/library/dn673574.aspx).

#### Wijzigingen aangebracht door de migratiescripts
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

-   Verwijder de volgende registerwaarden:

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

<!--HONumber=Apr16_HO4-->


