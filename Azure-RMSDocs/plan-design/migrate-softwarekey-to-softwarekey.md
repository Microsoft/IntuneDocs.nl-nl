---
# required metadata

title: Stap 2&colon; migratie van met software beschermde sleutel naar met software beschermde sleutel | Azure RMS
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 81a5cf4f-c1f3-44a9-ad42-66e95f33ed27

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Stap 2: migratie van met software beschermde sleutel naar met software beschermde sleutel

*Van toepassing op: Active Directory Rights Management Services, Azure Rights Management*


Deze instructies maken deel uit van het [migratiepad van AD RMS naar Azure Rights Management](migrate-from-ad-rms-to-azure-rms.md) en zijn alleen van toepassing als uw AD RMS-sleutel softwarebeveiliging heeft en u wilt migreren naar Azure Rights Management met een tenantsleutel met softwarebeveiliging. 

Als dit niet uw gekozen configuratiescenario is, gaat u terug naar [stap 2. Exporteer de configuratiegegevens vanuit AD RMS, importeer ze in Azure RMS](migrate-from-ad-rms-to-azure-rms.md#step-2-export-configuration-data-from-ad-rms-and-import-it-to-azure-rms) en kies een andere configuratie.

Volg deze procedure voor het importeren van de AD RMS-configuratie naar Azure RMS, waarna uw Azure RMS-tenantsleutel wordt beheerd door Microsoft.

## De configuratiegegevens importeren in Azure RMS

1.  Download en installeer op een werkstation met internetverbinding de Windows PowerShell-module voor Azure RMS (minimaal versie 2.1.0.0), waarin de cmdlet [Import-AadrmTpd](http://msdn.microsoft.com/library/azure/dn857523.aspx) is inbegrepen.

    > [!TIP]
    > Als u de module eerder hebt gedownload en geïnstalleerd, controleert u het versienummer door de volgende opdracht uit te voeren: `(Get-Module aadrm -ListAvailable).Version`

    Zie [Windows PowerShell voor Azure Rights Management installeren](../deploy-use/install-powershell.md) voor de installatie-instructies..

2.  Start Windows PowerShell met de optie **Uitvoeren als beheerder** en gebruik de cmdlet [Connect-AadrmService](http://msdn.microsoft.com/library/azure/dn629415.aspx) om verbinding te maken met de Azure RMS-service:

    ```
    Connect-AadrmService
    ```
    Wanneer u erom wordt gevraagd, typt u uw [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] tenantbeheerderreferenties (meestal gebruikt u hiervoor een account dat een globale beheerder is voor Azure Active Directory of Office 365).

3.  Gebruik de cmdlet [Import-AadrmTpd](http://msdn.microsoft.com/library/azure/dn857523.aspx) voor het uploaden van het eerste vertrouwde uitgiftedomeinbestand (.xml). Als u meer dan één XML-bestand hebt omdat u meerdere vertrouwde uitgiftedomeinen had, kiest u het bestand dat het geëxporteerde vertrouwde uitgiftedomein bevat dat u na de migratie in Azure RMS wilt gebruiken om inhoud te beveiligen. Gebruik de volgende opdracht:

    ```
    Import-AadrmTpd -TpdFile <PathToTpdPackageFile> -ProtectionPassword -Active $True -Verbose
    ```
    Bijvoorbeeld: **Import-AadrmTpd -TpdFile E:\contosokey1.xml -ProtectionPassword -Active $true -Verbose**

    Als u erom wordt gevraagd, typt u het eerder opgegeven wachtwoord en bevestigt u dat u deze actie wilt uitvoeren.

4.  Wanneer de opdracht is voltooid, herhaalt u stap 3 voor elk resterend XML-bestand dat u hebt gemaakt door uw vertrouwde uitgiftedomeinen te exporteren. Voor deze bestanden stelt echter u **-Active** in op **false** wanneer u de importeeropdracht uitvoert. Bijvoorbeeld: **Import-AadrmTpd -TpdFile E:\contosokey2.xml -ProtectionPassword -Active $false -Verbose**

5.  Gebruik de cmdlet [Disconnect-AadrmService](http://msdn.microsoft.com/library/azure/dn629416.aspx) om de verbinding met de Azure RMS-service te verbreken:

    ```
    Disconnect-AadrmService
    ```

U kunt nu doorgaan naar [stap 3. Activeer uw RMS-tenant](migrate-from-ad-rms-to-azure-rms.md#BKMK_Step3Migration)..



<!--HONumber=Apr16_HO4-->


