---
title: Stap 2&colon; migratie van met HSM beschermde sleutel naar met HSM beschermde sleutel | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: c5bbf37e-f1bf-4010-a60f-37177c9e9b39
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7a9c8b531ec342e7d5daf0cbcacd6597a79e6a55
ms.openlocfilehash: 7b531ebba1923653cb37c70a02fa888a40e96528


---

# Stap 2: migratie van met HSM beschermde sleutel naar met HSM beschermde sleutel

*Van toepassing op: Active Directory Rights Management Services, Azure Rights Management*


Deze instructies maken deel uit van het [migratiepad van AD RMS naar Azure Rights Management](migrate-from-ad-rms-to-azure-rms.md) en zijn alleen van toepassing als uw AD RMS-sleutel met HSM wordt beveiligd en u wilt migreren naar Azure Rights Management met een tenantsleutel die met HSM wordt beveiligd. 

Als dit niet uw gekozen configuratiescenario is, gaat u terug naar [Stap 2: Exporteer de configuratiegegevens vanuit AD RMS, importeer de gegevens in Azure RMS](migrate-from-ad-rms-phase1.md#step-2-export-configuration-data-from-ad-rms-and-import-it-to-azure-rms) en kies een andere configuratie.

> [!NOTE]
> Voor deze instructies is ervan uitgegaan dat uw AD RMS-sleutel is beveiligd met een module. Dit is in de meeste gevallen zo. Als uw AD RMS-sleutel wordt beveiligd met OCS, neemt u contact op met [AskIPTeam@microsoft.com](mailto: askipteam@microsoft.com?subject=AD%20RMS%20migration%20with%20OCS-protected%20key) voordat u deze instructies opvolgt.

De procedure om uw HSM-sleutel en AD RMS-configuratie te importeren in Azure RMS, wat erin resulteert dat uw Azure RMS-tenantsleutel wordt beheerd door u (BYOK), bestaat uit twee delen.

Eerst moet u uw HSM-sleutel inpakken, zodat deze gereed is om te worden overgedragen naar Azure RMS en vervolgens te worden geïmporteerd met de configuratiegegevens.

## Deel 1: pak uw HSM-sleutel in, zodat deze gereed is om te worden overgedragen naar Azure RMS

1.  Volg de stappen in het gedeelte [BYOK (Bring Your Own Key) implementeren](plan-implement-tenant-key.md#implementing-your-azure-rights-management-tenant-key) van het onderwerp [Uw Azure Rights Management-tenantsleutel plannen en implementeren](plan-implement-tenant-key.md). Maak daarbij gebruik van de procedure **Uw tenantsleutel genereren en overdragen via het internet**, met de volgende uitzonderingen:

    -   U hoeft de stappen voor **Uw tenantsleutel genereren** niet te volgen, omdat u het equivalent van uw AD RMS-implementatie al hebt. U moet de sleutel die wordt gebruikt door uw AD RMS-server uit de Thales-installatie, identificeren en deze sleutel gebruiken tijdens de migratie. Met Thales versleutelde bestanden worden lokaal op de server gewoonlijk aangeduid als **key_(keyAppName)_(keyIdentifier)**.

    -   Volg niet de stappen voor **Uw tenantsleutel overdragen naar Azure RMS**, waarvoor de opdracht Add-AadrmKey wordt gebruikt.  In plaats daarvan draagt u uw voorbereide HSM-sleutel over wanneer u uw geëxporteerde Trusted Publishing Domain uploadt met de opdracht Import-AadrmTpd.

2.  Op het met internet verbonden werkstation maakt u in een Windows PowerShell-sessie opnieuw verbinding met de Azure RMS-service.

Nu u uw HSM-sleutel voor Azure RMS hebt voorbereid, kunt u uw HSM-sleutelbestand en configuratiegegevens van AD RMS importeren.

## Deel 2: de HSM-sleutel en configuratiegegevens importeren in Azure RMS

1.  Upload tijdens de Windows PowerShell-sessie het eerste geëxporteerde Trusted Publishing Domain-bestand (.xml) op het met internet verbonden werkstation. Als u meer dan één .xml-bestand hebt omdat u meerdere Trusted Publishing Domains had, kiest u het bestand dat het geëxporteerde Trusted Publishing Domain bevat dat overeenkomt met de HSM-sleutel die u in Azure RMS wilt gebruiken om na de migratie inhoud te beveiligen. Gebruik de volgende opdracht:

    ```
    Import-AadrmTpd -TpdFile <PathToTpdPackageFile> -ProtectionPassword -HsmKeyFile <PathToBYOKPackage> -Active $True -Verbose
    ```
    Bijvoorbeeld: **Import -TpdFile E:\no_key_tpd_contosokey1.xml -HsmKeyFile E:\KeyTransferPackage-contosokey.byok -ProtectionPassword -Active $true -Verbose**

    Als u hierom wordt gevraagd, typt u het eerder opgegeven wachtwoord en bevestigt u dat u deze actie wilt uitvoeren.

2.  Wanneer de opdracht is voltooid, herhaalt u stap 1 voor elk resterend .xml-bestand dat u hebt gemaakt door uw Trusted Publishing Domains te exporteren. Maar voor deze bestanden stelt u **-Active** in op **false** wanneer u de opdracht Importeren uitvoert.  Bijvoorbeeld: **Import -TpdFile E:\contosokey2.xml -HsmKeyFile E:\KeyTransferPackage-contosokey.byok -ProtectionPassword -Active $false -Verbose**

3.  Gebruik de cmdlet [Disconnect-AadrmService](http://msdn.microsoft.com/library/windowsazure/dn629416.aspx) om de verbinding met de Azure RMS-service te verbreken:

    ```
    Disconnect-AadrmService
    ```

U kunt nu doorgaan naar [stap 3. Uw RMS-tenant activeren](migrate-from-ad-rms-phase1.md#step-3-activate-your-rms-tenant).




<!--HONumber=Jul16_HO3-->


