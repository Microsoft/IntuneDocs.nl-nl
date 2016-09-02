---
title: Stap 2&colon; migratie van met software beschermde sleutel naar met HSM beschermde sleutel | Azure RMS
description: Deze instructies maken deel uit van het migratiepad van AD RMS naar Azure Rights Management en zijn alleen van toepassing als uw AD RMS-sleutel softwarebeveiliging heeft en u wilt migreren naar Azure Rights Management met een tenantsleutel met HSM-beveiliging in Azure Key Vault.
author: cabailey
manager: mbaldwin
ms.date: 08/24/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: c5f4c6ea-fd2a-423a-9fcb-07671b3c2f4f
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 024a29d7c7db2e4c0578a95c93e22f8e7a5b173e
ms.openlocfilehash: e470b5b5542536e812749f77353aaf34922d4985


---

# Stap 2: migratie van met software beschermde sleutel naar met HSM beschermde sleutel

>*Van toepassing op: Active Directory Rights Management Services, Azure Rights Management*


Deze instructies maken deel uit van het [migratiepad van AD RMS naar Azure Rights Management](migrate-from-ad-rms-to-azure-rms.md) en zijn alleen van toepassing als uw AD RMS-sleutel softwarebeveiliging heeft en u wilt migreren naar Azure Rights Management met een tenantsleutel met HSM-beveiliging in Azure Key Vault. 

Als dit niet uw gekozen configuratiescenario is, gaat u terug naar [stap 2. Exporteer de configuratiegegevens vanuit AD RMS, importeer de gegevens in Azure RMS](migrate-from-ad-rms-phase1.md#step-2-export-configuration-data-from-ad-rms-and-import-it-to-azure-rms) en kies een andere configuratie.

Volg deze procedure in vier delen voor het importeren van de AD RMS-configuratie naar Azure RMS, wat erin resulteert dat uw Azure RMS-tenantsleutel wordt beheerd door u (BYOK) in Azure Key Vault.

U moet eerst uw SLC-sleutel (serverlicentiecertificaat) uit de AD RMS-configuratiegegevens ophalen en de sleutel overdragen naar een on-premises Thales HSM, vervolgens uw HSM-sleutel inpakken en overdragen naar Azure Key Vault, vervolgens instellen dat Azure RMS toegang heeft tot uw sleutelkluis, en tot slot de configuratiegegevens importeren.

Aangezien uw Azure RMS-tenantsleutel wordt opgeslagen en beheerd door Azure Key Vault, vereist dit deel van de migratie niet alleen beheer in Azure Key Vault, maar ook in Azure RMS. Als Azure Key Vault voor uw organisatie wordt beheerd door een andere beheerder dan u, moet u coördineren en samenwerken met deze beheerder om deze procedures te voltooien.

Voordat u begint, zorgt u ervoor dat uw organisatie een sleutelkluis heeft die is gemaakt in Azure Key Vault en dat deze sleutelkluis met HSM-beveiligde sleutels ondersteunt. Alhoewel het geen vereiste is, wordt aanbevolen dat u een toegewezen sleutelkluis voor Azure RMS hebt. Deze sleutelkluis wordt zodanig geconfigureerd dat Azure RMS hiertoe toegang heeft, zodat alleen Azure RMS-sleutels in deze sleutelkluis toegang hebben.


> [!TIP]
> Als u de configuratiestappen voor Azure Key Vault uitvoert en u niet bekend bent met deze Azure-service, is het wellicht handig vooraf [Aan de slag met Azure Key Vault ](https://azure.microsoft.com/documentation/articles/key-vault-get-started/) te raadplegen. 


## Deel 1: uw SLC-sleutel ophalen uit de configuratiegegevens en de sleutel in uw on-premises HSM importeren

1.  Azure Key Vault-beheerder: gebruik de volgende stappen in de sectie [Implementing bring your own key (BYOK) for Azure Key Vault (BYOK (Bring Your Own Key) implementeren voor Azure Key Vault)](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/#implementing-bring-your-own-key-byok-for-azure-key-vault) van de Azure Key Vault-documentatie:

    -   **Uw sleutel genereren en overdragen naar Azure Key Vault HSM**: [Stap 1: uw met internet verbonden werkstation voorbereiden](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/#step-1-prepare-your-internet-connected-workstation)

    -   **Uw tenantsleutel genereren en overdragen via internet**: [Stap 2: uw niet-verbonden werkstation voorbereiden](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/#step-2-prepare-your-disconnected-workstation)

    Volg deze stappen niet om uw tenantsleutel te genereren omdat u het equivalent al hebt in het geëxporteerde bestand met configuratiegegevens (.xml). In plaats daarvan voert u een hulpprogramma uit om deze sleutel uit het bestand uit te pakken en in uw on-premises HSM te importeren. Als u het hulpprogramma uitvoert, worden twee bestanden gemaakt:

    - Een nieuw configuratiegegevensbestand zonder de sleutel, die vervolgens in uw Azure RMS-tenant kan worden geïmporteerd.

    - Een PEM-bestand (sleutelcontainer) met de sleutel, die vervolgens naar uw on-premises HSM kan worden geïmporteerd.

2. Azure RMS-beheerder of Azure Key Vault-beheerder: voer op een niet-verbonden werkstation het hulpprogramma TpdUtil uit de [Azure RMS-migratietoolkit](https://go.microsoft.com/fwlink/?LinkId=524619) uit. Als het hulpprogramma bijvoorbeeld is geïnstalleerd op uw E-station waarnaar u uw configuratiegegevensbestand ContosoTPD.xml kopieert:

    ```
        E:\TpdUtil.exe /tpd:ContosoTPD.xml /otpd:ContosoTPD.xml /opem:ContosoTPD.pem
    ```

    Als u meer dan één RMS-configuratiegegevensbestand hebt, voert u dit hulpprogramma uit voor de rest van deze bestanden.

    Als u de Help van dit hulpprogramma wilt bekijken, waarin u onder andere een beschrijving, uitleg over het gebruik van het programma en voorbeelden vindt, voert u TpdUtil.exe zonder parameters uit

    Aanvullende informatie voor deze opdracht:

    - De **/tpd**: hiermee geeft u het volledige pad en de naam van het geëxporteerde AD RMS-configuratiegegevensbestand op. De volledige parameternaam is **TpdFilePath**.

    - De **/otpd**: hiermee geeft u de naam van het uitvoerbestand op voor het configuratiegegevensbestand zonder de sleutel. De volledige parameternaam is **OutPfxFile**. Als u deze parameter niet opgeeft, krijgt het uitvoerbestand de standaardbestandsnaam met het achtervoegsel **_keyless** en wordt dit bestand opgeslagen in de huidige map.

    - De **/opem**: hiermee geeft u de naam van het uitvoerbestand voor het PEM-bestand op, dat de uitgepakte sleutel bevat. De volledige parameternaam is **OutPemFile**. Als u deze parameter niet opgeeft, krijgt het uitvoerbestand de standaardbestandsnaam met het achtervoegsel **_key** en wordt dit bestand opgeslagen in de huidige map.

    - Als u het wachtwoord niet opgeeft wanneer u deze opdracht uitvoert (met behulp van de volledige parameternaam **TpdPassword** of de korte parameternaam **pwd**), wordt u gevraagd het wachtwoord op te geven.

3. Op hetzelfde niet-verbonden werkstation voegt u uw Thales HSM toe en configureert u deze volgens de Thales-documentatie. U kunt nu uw sleutel in de gekoppelde Thales HSM importeren met behulp van de volgende opdracht. Hierbij moet u uw eigen bestandsnaam gebruiken in plaats van ContosoTPD.pem:

        generatekey --import simple pemreadfile=e:\ContosoTPD.pem plainname=ContosoBYOK protect=module ident=contosobyok type=RSA

    > [!NOTE]
    >Als u meer dan één bestand hebt, kiest u het bestand dat overeenkomt met de HSM-sleutel die u wilt gebruiken in Azure RMS om inhoud te beveiligen na de migratie.

    Hiermee wordt een uitvoerscherm gegenereerd dat er ongeveer zo uitziet:

    **parameters voor het genereren van sleutels:**

    **operation &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Uit te voeren bewerking &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; importeren**

    **application &nbsp;&nbsp;&nbsp;&nbsp;Toepassing&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; eenvoudig**

    **verify &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; De beveiliging van de configuratiesleutel controleren&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ja**

    **type &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Sleuteltype &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; RSA**

    **pemreadfile &nbsp;&nbsp; PEM-bestand met de RSA-sleutel &nbsp;&nbsp; e:\ContosoTPD.pem**

    **ident &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Sleutel-id &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; contosobyok**

    **plainname &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Sleutelnaam &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ContosoBYOK**

    **De sleutel is geïmporteerd.**

    **Pad naar de sleutel: C:\ProgramData\nCipher\Key Management Data\local\key_simple_contosobyok**

Deze uitvoer bevestigt dat de persoonlijke sleutel is gemigreerd naar uw on-premises Thales HSM-apparaat met een versleuteld exemplaar dat is opgeslagen in een sleutel (in dit voorbeeld in key_simple_contosobyok). 

Nu uw SLC-sleutel is uitgepakt en in uw on-premises HSM is geïmporteerd, kunt u de met HSM beveiligde sleutel inpakken en overdragen naar Azure Key Vault.

> [!IMPORTANT]
> Zodra u deze stap hebt voltooid, verwijdert u deze PEM-bestanden van het niet-verbonden werkstation, zodat deze bestanden niet toegankelijk zijn voor onbevoegden. Voer bijvoorbeeld cipher /w:E uit om alle bestanden veilig van het E-station te verwijderen.

## Deel 2: uw HSM-sleutel inpakken en overdragen naar Azure Key Vault

1.  Azure Key Vault-beheerder: gebruik de volgende stappen in de sectie [Implementing bring your own key (BYOK) for Azure Key Vault (BYOK (Bring Your Own Key) implementeren voor Azure Key Vault)](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/#implementing-bring-your-own-key-byok-for-azure-key-vault) van de Azure Key Vault-documentatie:

    -   [Stap 4: uw sleutel voorbereiden voor overdracht](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/#step-4-prepare-your-key-for-transfer)

    -   [Stap 5: uw sleutel overdragen naar Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/#step-5-transfer-your-key-to-azure-key-vault)

    Volg niet de stappen voor het genereren van een sleutelpaar. U hebt de sleutel namelijk al. In plaats daarvan voert u een opdracht uit om deze sleutel over te dragen (in dit voorbeeld gebruikt de KeyIdentifier-parameter contosobyok) vanuit uw on-premises HSM.

    Voordat u uw sleutel naar Azure Key Vault overdraagt, zorgt u ervoor dat het hulpprogramma KeyTransferRemote.exe **Result: SUCCES** retourneert wanneer u een kopie van de sleutel met beperkte bevoegdheden maakt (stap 4.1) en u uw sleutel versleutelt (stap 4.3).

    Tijdens het uploaden van de sleutel naar Azure Key Vault worden de eigenschappen van de sleutel weergegeven, zoals de sleutel-id. Dit ziet er ongeveer als volgt uit: **https://contosorms-kv.vault.azure.net/keys/contosorms-byok/aaaabbbbcccc111122223333**. Noteer deze URL. De Azure RMS-beheerder heeft deze namelijk nodig om in Azure RMS in te stellen dat deze sleutel wordt gebruikt voor de tenantsleutel.

    Nu u uw HSM-sleutel hebt overgedragen naar Azure Key Vault, kunt u uw AD RMS-configuratiegegevens importeren.

## Deel 3: de configuratiegegevens importeren naar Azure RMS

1.  Azure RMS-beheerder: kopieer uw nieuwe configuratiegegevensbestanden (.xml) naar het met internet verbonden werkstation en in de PowerShell-sessie. In deze bestanden is de SLC-sleutel verwijderd na het uitvoeren van het hulpprogramma TpdUtil.

2. Upload het eerste .xml-bestand met behulp van cmdlet [Import-AadrmTpd](https://msdn.microsoft.com/library/dn857523.aspx). Als u meerdere bestanden hebt omdat u meerdere Trusted Publishing Domains had, kiest u het bestand dat overeenkomt met de HSM-sleutel die u in Azure RMS wilt gebruiken om na de migratie inhoud te beveiligen.

    Als u deze cmdlet wilt uitvoeren, hebt u de URL nodig die in de vorige stap werd genoemd.

    Als u bijvoorbeeld de URL-waarde uit de vorige stap en het configuratiegegevensbestand C:\contoso_keyless.xml gebruikt, voert u het volgende uit:

    ```
    Import-AadrmTpd -TpdFile "C:\contoso_keyless.xml" -ProtectionPassword –KeyVaultStringUrl https://contoso-byok-kv.vault.azure.net/keys/contosorms-byok/aaaabbbbcccc111122223333 -Active $True -Verbose
    ```

    Als u hierom wordt gevraagd, typt u het wachtwoord dat u eerder hebt opgegeven voor het configuratiegegevensbestand en bevestigt u dat u deze actie wilt uitvoeren.

    Als u meer configuratiegegevensbestanden hebt, herhaalt u deze opdracht voor de rest van deze bestanden. Maar voor deze bestanden stelt u **-Active** in op **false** wanneer u de opdracht Importeren uitvoert.



3.  Gebruik de cmdlet [Disconnect-AadrmService](http://msdn.microsoft.com/library/windowsazure/dn629416.aspx) om de verbinding met de Azure RMS-service te verbreken:

    ```
    Disconnect-AadrmService
    ```

    > [!NOTE]
    > Als u later moet bevestigen welke sleutel uw Azure RMS-tenantsleutel is in Azure Key Vault, gebruikt u de cmdlet [Get-AadrmKeys](https://msdn.microsoft.com/library/dn629420.aspx) in Azure RMS.


U kunt nu doorgaan naar [stap 3. Uw RMS-tenant activeren](migrate-from-ad-rms-phase1.md#step-3-activate-your-rms-tenant).






<!--HONumber=Aug16_HO4-->


