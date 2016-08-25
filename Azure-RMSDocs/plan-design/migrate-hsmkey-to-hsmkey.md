---
title: Stap 2&colon; migratie van met HSM beschermde sleutel naar met HSM beschermde sleutel | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 08/17/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: c5bbf37e-f1bf-4010-a60f-37177c9e9b39
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 437afd88efebd9719a3db98f8ab0ae07403053f7
ms.openlocfilehash: 86f7bd025824b23c8eecdb05b62d83204ae1ccb4


---

# Stap 2: migratie van met HSM beschermde sleutel naar met HSM beschermde sleutel

*Van toepassing op: Active Directory Rights Management Services, Azure Rights Management*


Deze instructies maken deel uit van het [migratiepad van AD RMS naar Azure Rights Management](migrate-from-ad-rms-to-azure-rms.md) en zijn alleen van toepassing als uw AD RMS-sleutel HSM-beveiliging heeft en u wilt migreren naar Azure Rights Management met een tenantsleutel met HSM-beveiliging in Azure Key Vault. 

Als dit niet uw gekozen configuratiescenario is, gaat u terug naar [stap 2. Exporteer de configuratiegegevens vanuit AD RMS, importeer de gegevens in Azure RMS](migrate-from-ad-rms-phase1.md#step-2-export-configuration-data-from-ad-rms-and-import-it-to-azure-rms) en kies een andere configuratie.

> [!NOTE]
> Voor deze instructies is ervan uitgegaan dat uw AD RMS-sleutel is beveiligd met een module. Dit is de meest voorkomende geval. 

De procedure om uw HSM-sleutel en AD RMS-configuratie te importeren in Azure RMS, wat erin resulteert dat uw Azure RMS-tenantsleutel wordt beheerd door u (BYOK), bestaat uit twee delen.

Aangezien uw Azure RMS-tenantsleutel wordt opgeslagen en beheerd door Azure Key Vault, vereist dit deel van de migratie niet alleen beheer in Azure Key Vault, maar ook in Azure RMS. Als Azure Key Vault voor uw organisatie wordt beheerd door een andere beheerder dan u, moet u coördineren en samenwerken met deze beheerder om deze procedures te voltooien.

Voordat u begint, zorgt u ervoor dat uw organisatie een sleutelkluis heeft die is gemaakt in Azure Key Vault en dat deze sleutelkluis met HSM-beveiligde sleutels ondersteunt. Alhoewel het geen vereiste is, wordt aanbevolen dat u een toegewezen sleutelkluis voor Azure RMS hebt. Deze sleutelkluis wordt zodanig geconfigureerd dat Azure RMS hiertoe toegang heeft, zodat alleen Azure RMS-sleutels in deze sleutelkluis toegang hebben.


> [!TIP]
> Als u de configuratiestappen voor Azure Key Vault uitvoert en u niet bekend bent met deze Azure-service, is het wellicht handig vooraf [Aan de slag met Azure Key Vault ](https://azure.microsoft.com/documentation/articles/key-vault-get-started/) te raadplegen. 


## Stap 1: uw HSM-sleutel overdragen naar Azure Key Vault

Deze procedures moeten worden uitgevoerd door de beheerder van Azure Key Vault.

1.  Volg de instructies in de Azure Key Vault-documentatie, [BYOK (Bring Your Own Key) implementeren voor Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/#implementing-bring-your-own-key-byok-for-azure-key-vault), met de volgende uitzondering:

    - U hoeft de stappen voor **Uw tenantsleutel genereren** niet te volgen, omdat u het equivalent van uw AD RMS-implementatie al hebt. In plaats daarvan moet u de sleutel identificeren die wordt gebruikt door uw AD RMS-server uit de Thales-installatie en deze sleutel gebruiken tijdens de migratie. Met Thales versleutelde bestanden worden lokaal op de server gewoonlijk aangeduid als **key<*keyAppName*><*keyIdentifier*>**.

    Tijdens het uploaden van de sleutel naar Azure Key Vault worden de eigenschappen van de sleutel weergegeven, zoals de sleutel-id. Dit ziet er ongeveer als volgt uit: https://contosorms-kv.vault.azure.net/keys/contosorms-byok/aaaabbbbcccc111122223333. Noteer deze URL. De Azure RMS-beheerder heeft deze namelijk nodig om in Azure RMS in te stellen dat deze sleutel wordt gebruikt voor de tenantsleutel.

2. Gebruik op het met internet verbonden werkstation in een PowerShell-sessie de cmdlet [Set-AzureRmKeyVaultAccessPolicy](https://msdn.microsoft.com/library/mt603625.aspx ) om de Azure RMS-service-principal (Microsoft.Azure.RMS) toegang te geven tot de sleutelkluis waarin de Azure RMS-tenantsleutel is opgeslagen. De vereiste machtigingen zijn decoderen, coderen, sleutel uitpakken, sleutel inpakken, controleren en ondertekenen.
    
    Als de sleutelkluis die u hebt gemaakt voor Azure RMS bijvoorbeeld de naam contoso-byok-ky heeft en uw resourcegroep de naam contoso-byok-rg heeft, voert u de volgende opdracht uit:
    
        Set-AzureRmKeyVaultAccessPolicy -VaultName "contoso-byok-kv" -ResourceGroupName "contoso-byok-rg" -ServicePrincipalName Microsoft.Azure.RMS -PermissionsToKeys decrypt,encrypt,unwrapkey,wrapkey,verify,sign


Nu u uw HSM-sleutel in Azure Key Vault voor Azure RMS hebt voorbereid, kunt u uw configuratiegegevens van AD RMS importeren.

## Deel 2: de configuratiegegevens importeren naar Azure RMS

Deze procedures moeten worden uitgevoerd door de beheerder van Azure RMS.

1.  Maak op het met internet verbonden werkstation tijdens een PowerShell-sessie verbinding met de Azure RMS door de cmdlet [Connnect-AadrmService](https://msdn.microsoft.com/library/dn629415.aspx ) uit te voeren.
    
    Upload vervolgens het eerste Trusted Publishing Domain-bestand (.xml) met behulp van de cmdlet [Import-AadrmTpd](https://msdn.microsoft.com/library/dn857523.aspx). Als u meer dan één .xml-bestand hebt omdat u meerdere Trusted Publishing Domains had, kiest u het bestand dat het geëxporteerde Trusted Publishing Domain bevat dat overeenkomt met de HSM-sleutel die u in Azure RMS wilt gebruiken om na de migratie inhoud te beveiligen. 
    
    Als u deze cmdlet wilt uitvoeren, hebt u de URL nodig die in de vorige stap werd genoemd.
    
    Als u bijvoorbeeld de URL-waarde uit de vorige stap en het TPD-bestand C:\contoso-tpd1.xml gebruikt, voert u het volgende uit:
    
    ```
    Import-AadrmTpd -TpdFile "C:\contoso-tpd1.xml" -ProtectionPassword –KeyVaultStringUrl https://contoso-byok-kv.vault.azure.net/keys/contosorms-byok/aaaabbbbcccc111122223333 -Active $True -Verbose
    ```
    
    Als u hierom wordt gevraagd, typt u het eerder opgegeven wachtwoord en bevestigt u dat u deze actie wilt uitvoeren.

2.  Wanneer de opdracht is voltooid, herhaalt u stap 1 voor elk resterend .xml-bestand dat u hebt gemaakt door uw Trusted Publishing Domains te exporteren. Maar voor deze bestanden stelt u **-Active** in op **false** wanneer u de opdracht Importeren uitvoert.  

3.  Gebruik de cmdlet [Disconnect-AadrmService](http://msdn.microsoft.com/library/windowsazure/dn629416.aspx) om de verbinding met de Azure RMS-service te verbreken:

    ```
    Disconnect-AadrmService
    ```

    > [!NOTE]
    > Als u later moet bevestigen welke sleutel uw Azure RMS-tenantsleutel is in Azure Key Vault, gebruikt u de cmdlet [Get-AadrmKeys](https://msdn.microsoft.com/library/dn629420.aspx) in Azure RMS.

U kunt nu doorgaan naar [stap 3. Uw RMS-tenant activeren](migrate-from-ad-rms-phase1.md#step-3-activate-your-rms-tenant).




<!--HONumber=Aug16_HO3-->


