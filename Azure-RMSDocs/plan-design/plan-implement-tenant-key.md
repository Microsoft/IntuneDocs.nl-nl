---
title: Uw Azure Rights Management-tenantsleutel plannen en implementeren | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 08/17/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: f0d33c5f-a6a6-44a1-bdec-5be1bc8e1e14
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a80866576dc7d6400bcebc2fc1c37bc0367bcdf3
ms.openlocfilehash: ee7b9b5f251856f102651f1e8f379f7bbacea77e


---

# Uw Azure Rights Management-tenantsleutel plannen en implementeren

*Van toepassing op: Azure Rights Management, Office 365*

Gebruik de informatie in dit artikel om uw Rights Management-tenantsleutel (RMS) voor Azure RMS te plannen en te beheren. In plaats van Microsoft uw tenantsleutel te laten beheren (standaard), wilt u wellicht zelf uw tenantsleutel beheren om te voldoen aan specifieke regels die gelden voor uw organisatie.  Uw eigen tenantsleutel beheren wordt ook wel aangeduid als BYOK (Bring Your Own Key).

> [!NOTE]
> De RMS-tenantsleutel wordt ook wel aangeduid als de SLC-sleutel (serverlicentiecertificaat). Azure RMS onderhoudt een of meer sleutels voor elke organisatie die zich abonneert op Azure RMS. Wanneer een sleutel wordt gebruikt voor RMS binnen een organisatie (zoals gebruikerssleutels, computersleutels, sleutels voor documentversleuteling), worden ze cryptografisch gekoppeld aan uw RMS-tenantsleutel.

**In één oogopslag:** gebruik de volgende tabel als een snelle handleiding voor de aanbevolen topologie van uw tenantsleutels. Vervolgens gebruikt u de extra documentatie voor meer informatie.

Als u Azure RMS implementeert met een tenantsleutel die wordt beheerd door Microsoft, kunt u later overstappen naar BYOK. U kunt momenteel echter uw Azure RMS-tenantsleutel niet overzetten van BYOK naar Beheerd door Microsoft.

|Zakelijke vereiste|Aanbevolen tenantsleuteltopologie|
|------------------------|-----------------------------------|
|Snel en zonder speciale hardware Azure RMS implementeren|Beheerd door Microsoft|
|Volledige IRM-functionaliteit is vereist in Exchange Online met Azure RMS|Beheerd door Microsoft|
|Uw sleutels worden door u gemaakt en beveiligd in een Hardware Security Module (HSM)|BYOK<br /><br />Op dit moment leidt deze configuratie tot een gereduceerde IRM-functionaliteit in Exchange Online. Zie [BYOK-prijzen en -beperkingen](byok-price-restrictions.md) voor meer informatie.|

## Uw tenantsleuteltopologie kiezen: Beheerd door Microsoft (de standaardinstelling) of Beheerd door uzelf (BYOK)
Beslis welke tenantsleuteltopologie het beste is voor uw organisatie. Standaard genereert Azure RMS uw tenantsleutel en beheert het de meeste aspecten van de levenscyclus van de tenantsleutel. Dit is de eenvoudigste optie met de laagste administratieve overhead. In de meeste gevallen hoeft u zelfs niet te weten dat u een tenantsleutel hebt. U hoeft u alleen aan te melden voor Azure RMS en de rest van het sleutelbeheerproces wordt uitgevoerd door Microsoft.

U kunt de controle over uw tenantsleutel ook voltooien met behulp van [Azure Key Vault](https://azure.microsoft.com/services/key-vault/). In dit scenario maakt u uw tenantsleutel en zorgt u ervoor dat het originele exemplaar bij uw organisatie blijft. Dit scenario wordt vaak Bring Your Own Key (BYOK) genoemd. Met deze optie gebeurt er het volgende:

1.  U genereert uw tenantsleutel op uw locatie in overeenstemming met uw IT- en beveiligingsbeleid.

2.  U draagt de tenantsleutel van een Hardware Security Module (HSM) in uw bezit veilig over aan HSM's die eigendom zijn van en worden beheerd door Microsoft via Azure Key Vault. Tijdens dit proces blijft uw tenantsleutel altijd binnen de grenzen van uw hardwarebeveiliging.

3.  Wanneer u uw tenantsleutel overdraagt aan Microsoft, blijft deze beveiligd met Azure Key Vault.

Hoewel dit optioneel is, wilt u waarschijnlijk ook gebruikmaken van de bijna realtime logboeken van Azure RMS om te zien hoe en wanneer uw tenantsleutel precies wordt gebruikt.

> [!NOTE]
> Azure Key Vault gebruikt als extra beveiligingsmaatregel afzonderlijke beveiligingsdomeinen voor de datacentra in Noord-Amerika, EMEA (Europa, Midden-Oosten en Afrika) en Azië. Dit geldt ook voor verschillende exemplaren van Azure, zoals Microsoft Azure Germany en Azure Government. Wanneer u uw eigen tenantsleutel beheert, is deze gebonden aan het beveiligingsdomein van de regio of het exemplaar waarin uw RMS-tenant is geregistreerd. Een tenantsleutel van een Europese klant kan bijvoorbeeld niet worden gebruikt in datacenters in Noord-Amerika of Azië.

## De levenscyclus van de tenantsleutel
Als u besluit dat Microsoft uw tenantsleutel moet beheren, voert Microsoft het grootste deel van de bewerkingen uit tijdens de levenscyclus van de sleutel. Als u echter besluit zelf uw tenantsleutel te beheren, bent u verantwoordelijk voor veel bewerkingen en een aantal extra procedures in Azure Key Vault tijdens de levenscyclus van de sleutel.

In het volgende diagram worden deze twee opties weergegeven en met elkaar vergeleken. Het eerste diagram toont hoe weinig beheerdersoverhead er voor u is in de standaardconfiguratie, waarbij Microsoft de tenantsleutel beheert.

![Levenscyclus van de Azure RMS-tenantsleutel, beheerd door Microsoft, de standaard](../media/RMS_BYOK_cloud.png)

Het tweede diagram toont de extra stappen die vereist zijn wanneer u uw eigen tenantsleutel beheert.

![Levenscyclus van de Azure RMS-tenantsleutel, beheerd door u, BYOK](../media/RMS_BYOK_onprem4.png)

Als u besluit uw tenantsleutel door Microsoft te laten beheren, is er geen verdere actie vereist om de sleutel te genereren. U kunt dan direct door naar [Volgende stappen](plan-implement-tenant-key.md#next-steps).

Als u besluit uw tenantsleutel zelf te beheren, leest u de volgende gedeeltes voor meer informatie.

## Uw Azure Rights Management-tenantsleutel implementeren

Gebruik de informatie en procedures in dit gedeelte als u hebt besloten om uw eigen tenantsleutel te genereren en beheren. Het BYOK-scenario (Bring Your Own Key) uitvoeren:


> [!IMPORTANT]
> Als u [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] al gebruikt (de service is geactiveerd) en u hebt gebruikers die Office 2010 uitvoeren, moet u [contact opnemen met Microsoft Ondersteuning](../get-started/information-support.md#to-contact-microsoft-support) voordat u deze procedures uitvoert. Afhankelijk van uw scenario en vereisten, kunt u BYOK blijven gebruiken, maar met enkele beperkingen of bijkomende stappen.
> 
> U moet ook [contact opnemen met Microsoft Ondersteuning](../get-started/information-support.md#to-contact-microsoft-support) als uw organisatie een specifiek beleid hanteert voor de verwerking van sleutels.

### Vereisten voor BYOK
Zie de volgende tabel voor een lijst met vereisten voor BYOK (Bring Your Own Key).

|Vereiste|Meer informatie|
|---------------|--------------------|
|Een abonnement dat Azure RMS ondersteunt.|Zie [Cloudabonnementen die ondersteuning bieden voor Azure RMS](../get-started/requirements-subscriptions.md) voor meer informatie over de beschikbare abonnementen.|
|U gebruikt geen RMS voor personen of Exchange Online. Of als u Exchange Online gebruikt, begrijpt en accepteert u de beperkingen van het gebruik van BYOK met deze configuratie.|Zie [BYOK-prijzen en -beperkingen](byok-price-restrictions.md) voor meer informatie over de beperkingen en huidige limieten van BYOK.<br /><br />**Belangrijk**: BYOK is momenteel niet compatibel met Exchange Online.|
|Alle vereiste onderdelen voor BYOK-sleutelkluis.|Zie [Prequisites for BYOK (Vereisten voor BYOK)](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/#prerequisites-for-byok) in de documentatie over Azure Key Vault. <br /><br />**Opmerking**: als u van AD RMS migreert naar Azure RMS door over te stappen van een softwaresleutel naar een hardwaresleutel, moet u minimaal versie 11.62 voor de Thales-firmware hebben.|
|De Azure RMS-beheermodule voor Windows PowerShell.|Zie [Windows PowerShell voor Azure Rights Management installeren](../deploy-use/install-powershell.md) voor installatie-instructies. <br /><br />Als u deze Windows PowerShell-module eerder hebt geïnstalleerd, voert u de volgende opdracht uit om te controleren of u minimaal over versienummer **2.5.0.0** beschikt: `(Get-Module aadrm -ListAvailable).Version`|

Zie de [Thales-website](https://www.thales-esecurity.com/msrms/cloud) voor meer informatie over Thales HSM's en hoe deze worden gebruikt met Azure Key Vault.

Volg de procedures in [Met HSM-beveiligde sleutels genereren en overdragen voor Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/) in de documentatie voor Azure Key Vault om uw eigen tenantsleutel te genereren en over te dragen aan Azure Key Vault.

Wanneer de sleutel wordt overgedragen aan Key Vault, krijgt de sleutel een sleutel-ID in Key Vault (een URL die de naam van de sleutelkluis, de sleutelcontainer, de naam van de sleutel en de belangrijkste versie bevat). Bijvoorbeeld: **https://contosorms-kv.vault.azure.net/keys/contosorms-byok/aaaabbbbcccc111122223333**. U moet in Azure RMS kenbaar maken dat deze sleutel moet worden gebruikt door deze URL te specificeren.

Maar voordat Azure RMS de sleutel kan gebruiken, moet Azure RMS worden geautoriseerd om de sleutel in de sleutelkluis van uw organisatie te gebruiken. Hiervoor moet de beheerder van de Azure Key Vault de cmdlet Key Vault PowerShell en [Set-AzureRmKeyVaultAccessPolicy](https://msdn.microsoft.com/library/mt603625.aspx) gebruiken en machtigingen verlenen aan **Microsoft.Azure.RMS**, de service-principal van Azure RMS. Bijvoorbeeld:

    Set-AzureRmKeyVaultAccessPolicy -VaultName 'ContosoRMS-kv' -ResourceGroupName 'ContosoRMS-byok-rg' -ServicePrincipalName Microsoft.Azure.RMS -PermissionsToKeys decrypt,encrypt,unwrapkey,wrapkey,verify,sign 

U bent nu klaar om Azure RMS te configureren voor het gebruik van deze sleutel als de Azure RMS-tenantsleutel van uw organisatie. Met Azure RMS-cmdlets maakt u eerst verbinding met Azure RMS en meldt u zich aan:

    Connect-AadrmService

Voer vervolgens de [cmdlet Use-AadrmKeyVaultKey](https://msdn.microsoft.com/library/azure/mt759829.aspx) uit en geef hierbij de sleutel-URL op. Bijvoorbeeld:

    Use-AadrmKeyVaultKey -KeyVaultKeyUrl "https://contosorms-kv.vault.azure.net/keys/contosorms-byok/aaaabbbbcccc111122223333"

Als u wilt bevestigen dat de sleutel-URL correct is ingesteld in Azure RMS in Azure Key Vault, kunt u [Get-AzureKeyVaultKey](https://msdn.microsoft.com/library/dn868053.aspx) uitvoeren om de sleutel-URL weer te geven.


## Volgende stappen

Nu u een planning hebt gemaakt en u zo nodig de tenantsleutel hebt gegenereerd, doet u het volgende:

1.  Begin uw tenantsleutel te gebruiken:

    -   Als u dat nog niet hebt gedaan, moet u nu Rights Management activeren zodat uw organisatie kan beginnen RMS te gebruiken. Gebruikers beginnen onmiddellijk uw tenantsleutel te gebruiken (beheerd door Microsoft of door u in Azure Key Vault).

        Zie [Azure Rights Management activeren](../deploy-use/activate-service.md) voor meer informatie over activeren.

    -   Als u Rights Management al had geactiveerd en vervolgens hebt besloten uw eigen tenantsleutel te beheren, stappen gebruikers geleidelijk van de oude tenantsleutel over op de nieuwe. Deze gespreide overgang kan een paar weken duren. Documenten en bestanden die waren beveiligd met de oude tenantsleutel, blijven toegankelijk voor gemachtigde gebruikers.

2.  Overweeg gebruikslogboekregistratie te gebruiken: hiermee wordt elke transactie geregistreerd die Azure Rights Management uitvoert.

    Als u had besloten uw eigen tenantsleutel te beheren, bevat de logboekregistratie informatie over het gebruik van uw tenantsleutel. Zie het volgende fragment van een in Excel weergegeven logboekbestand, waarin de aanvraagtypen **KeyVaultDecryptRequest** en **KeyVaultSignRequest** aangeven dat de tenantsleutel wordt gebruikt.

    ![logboekbestand waarin de tenantsleutel wordt gebruikt](../media/RMS_Logging.png)

    Zie [Logging and analyzing Azure Rights Management usage](../deploy-use/log-analyze-usage.md) (Het gebruik van Azure Rights Management registreren in een logboek en analyseren) voor meer informatie over logboekregistratie van het gebruik.

3.  Onderhoud uw tenantsleutel.

    Zie [Operations for your Azure Rights Management tenant key](../deploy-use/operations-tenant-key.md) (Bewerkingen voor uw Azure Rights Management-tenantsleutel) voor meer informatie.




<!--HONumber=Aug16_HO3-->


