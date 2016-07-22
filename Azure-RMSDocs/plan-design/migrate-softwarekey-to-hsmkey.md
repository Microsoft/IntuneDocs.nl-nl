---
title: Stap 2&colon; migratie van met software beschermde sleutel naar met HSM beschermde sleutel | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: c5f4c6ea-fd2a-423a-9fcb-07671b3c2f4f
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7a9c8b531ec342e7d5daf0cbcacd6597a79e6a55
ms.openlocfilehash: 173641b9dada2673b48a1c210419cb933cdd9f13


---

# Stap 2: migratie van met software beschermde sleutel naar met HSM beschermde sleutel

*Van toepassing op: Active Directory Rights Management Services, Azure Rights Management*


Deze instructies maken deel uit van het [migratiepad van AD RMS naar Azure Rights Management](migrate-from-ad-rms-to-azure-rms.md) en zijn alleen van toepassing als uw AD RMS-sleutel softwarebeveiliging heeft en u wilt migreren naar Azure Rights Management met een tenantsleutel met HSM-beveiliging. 

Als dit niet uw gekozen configuratiescenario is, gaat u terug naar [Stap 2: Exporteer de configuratiegegevens vanuit AD RMS, importeer de gegevens in Azure RMS](migrate-from-ad-rms-phase1.md#step-2-export-configuration-data-from-ad-rms-and-import-it-to-azure-rms) en kies een andere configuratie.

Volg deze procedure in drie delen voor het importeren van de AD RMS-configuratie naar Azure RMS, wat erin resulteert dat uw Azure RMS-tenantsleutel wordt beheerd door u (BYOK).

U moet eerst uw SLC-sleutel (serverlicentiecertificaat) uit de gegevens ophalen en de sleutel overdragen naar een on-premises Thales HSM, vervolgens uw HSM-sleutel inpakken en overdragen naar Azure RMS, en tot slot de configuratiegegevens importeren.

## Deel 1: haal uw SLC op uit de configuratiegegevens en importeer de sleutel in on-premises lokale HSM

1.  Volg de stappen in het gedeelte [BYOK (Bring Your Own Key) implementeren](plan-implement-tenant-key.md#implementing-your-azure-rights-management-tenant-key) van het onderwerp [Uw Azure Rights Management-tenantsleutel plannen en implementeren](plan-implement-tenant-key.md). Maak daarbij gebruik van de procedure **Uw tenantsleutel genereren en overdragen via het internet**, met de volgende uitzonderingen:

    -   **Uw tenantsleutel genereren en overdragen via internet**: **uw met internet verbonden werkstation voorbereiden**

    -   **Uw tenantsleutel genereren en overdragen via internet**: **uw niet-verbonden werkstation voorbereiden**

    Volg deze stappen niet om uw tenantsleutel te genereren omdat u het equivalent al hebt in het geëxporteerde bestand met configuratiegegevens (.xml). In plaats daarvan voert u een opdracht uit om deze sleutel uit het bestand uit te pakken en deze te importeren in uw on-premises HSM.

2.  Voer de volgende opdracht uit op het niet-verbonden werkstation:

    ```
    KeyTransferRemote.exe -ImportRmsCentrallyManagedKey -TpdFilePath <TPD> -ProtectionPassword -KeyIdentifier <KeyID> -ExchangeKeyPackage <BYOK-KEK-pka-Region> -NewSecurityWorldPackage <BYOK-SecurityWorld-pkg-Region>
    ```
    Bijvoorbeeld voor Noord-Amerika: **KeyTransferRemote.exe -ImportRmsCentrallyManagedKey -TpdFilePath E:\contosokey1.xml -ProtectionPassword -KeyIdentifier contosorms1key –- -ExchangeKeyPackage &lt;BYOK-KEK-pka-NA-1&gt; -NewSecurityWorldPackage &lt;BYOK-SecurityWorld-pkg-NA-1&gt;**

    Extra informatie:

    -   De parameter ImportRmsCentrallyManagedKey geeft aan dat de bewerking bedoeld is om de SLC-sleutel te importeren.

    -   Als u het wachtwoord niet opgeeft in de opdracht, wordt u gevraagd het op te geven.

    -   De parameter KeyIdentifier is bedoeld voor een beschrijvende sleutelnaam en maakt de naam van het sleutelbestand. Gebruik alleen kleine ASCII-tekens.

    -   De parameter ExchangeKeyPackage specificeert een regiospecifiek pakket met een uitwisselingssleutel voor de sleutel (een KEK-pakket) met een naam die begint met BYOK-KEK-pkg-.

    -   De parameter NewSecurityWorldPackage specificeert een specifiek beveiligingswereldpakket met een naam die begint met BYOK-SecurityWorld-pkg-.

    Deze opdracht resulteert in het volgende:

    -   Een HSM-sleutelbestand: %NFAST_KMDATA%\local\key_mscapi_&lt;KeyID&gt;

    -   Een bestand met RMS-configuratiegegevens met SLC verwijderd: %NFAST_KMDATA%\local\no_key_tpd_&lt;KeyID&gt;.xml

3.  Als u meer dan één bestand met RMS-configuratiegegevens hebt, herhaalt u stap 2 voor de rest van deze bestanden.

Nu uw SLC is uitgepakt zodat het een HSM-gebaseerde sleutel is, kunt u dit inpakken en overbrengen naar Azure RMS.

## Deel 2: uw HSM-sleutel inpakken en overdragen naar Azure RMS

1.  Gebruik de volgende stappen uit het gedeelte [BYOK (Bring Your Own Key) implementeren](plan-implement-tenant-key.md#implementing-your-azure-rights-management-tenant-key) van het onderwerp [Uw Azure Rights Management-tenantsleutel implementeren](plan-implement-tenant-key.md):

    -   **Uw tenantsleutel genereren en overdragen via internet**: **uw tenantsleutel voorbereiden voor overdracht**

    -   **Uw tenantsleutel genereren en overdragen via internet**: **uw tenantsleutel overdragen naar Azure RMS**

Nu u uw HSM-sleutel naar Azure RMS overgebracht hebt, kunt u uw AD RMS-configuratiegegevens importeren. Deze bevatten alleen een pointer naar de zojuist overgebrachte tenantsleutel.

## Deel 3: de configuratiegegevens importeren naar Azure RMS

1.  Terwijl u nog steeds op het met internet verbonden werkstation en in de Windows PowerShell-sessie bent, kopieert u de gegevens via de RMS-configuratiebestanden met het SLC verwijderd (vanaf het niet-verbonden werkstation, %NFAST_KMDATA%\local\no_key_tpd_&lt;KeyID&gt;.xml)

2.  Upload het eerste bestand. Als u meer dan één .xml-bestand hebt omdat u meerdere Trusted Publishing Domains had, kiest u het bestand dat het geëxporteerde Trusted Publishing Domain bevat dat overeenkomt met de HSM-sleutel die u in Azure RMS wilt gebruiken om na de migratie inhoud te beveiligen. Gebruik de volgende opdracht:

    ```
    Import-AadrmTpd -TpdFile <PathToNoKeyTpdPackageFile> -ProtectionPassword -HsmKeyFile <PathToKeyTransferPackage> -Active $true -Verbose
    ```
    Bijvoorbeeld: **Import -TpdFile E:\no_key_tpd_contosorms1key.xml -ProtectionPassword -HsmKeyFile E:\KeyTransferPackage-contosorms1key.byok -Active $true -Verbose**

    Als u hierom wordt gevraagd, typt u het eerder opgegeven wachtwoord en bevestigt u dat u deze actie wilt uitvoeren.

3.  Wanneer de opdracht is voltooid, herhaalt u stap 2 voor elk resterend XML-bestand dat u hebt gemaakt door uw vertrouwde uitgiftedomeinen te exporteren. Maar voor deze bestanden stelt u **-Active** in op **false** wanneer u de opdracht Importeren uitvoert. Bijvoorbeeld: **Import -TpdFile E:\no_key_tpd_contosorms2key.xml -ProtectionPassword -HsmKeyFile E:\KeyTransferPackage-contosorms1key.byok -Active $false -Verbose**

4.  Gebruik de cmdlet [Disconnect-AadrmService](http://msdn.microsoft.com/library/windowsazure/dn629416.aspx) om de verbinding met de Azure RMS-service te verbreken:

    ```
    Disconnect-AadrmService
    ```

U kunt nu doorgaan naar [stap 3. Uw RMS-tenant activeren](migrate-from-ad-rms-phase1.md#step-3-activate-your-rms-tenant).





<!--HONumber=Jul16_HO3-->


