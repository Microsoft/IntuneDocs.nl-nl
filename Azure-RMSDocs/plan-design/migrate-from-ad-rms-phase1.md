---
title: Migreren van AD RMS naar Azure Rights Management - Fase 1 | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 08/17/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 5a189695-40a6-4b36-afe6-0823c94993ef
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 437afd88efebd9719a3db98f8ab0ae07403053f7
ms.openlocfilehash: efe129422348fb30ce7686a5602cb29a1b46d36d


---

# Migratiefase 1 - configuratie voor AD RMS aan serverzijde

*Van toepassing op: Active Directory Rights Management Services, Azure Rights Management*

Gebruik de volgende informatie voor fase 1 van de migratie van AD RMS naar Azure Rights Management (Azure RMS). Deze procedures beslaan stap 1 tot en met 4 van [Migreren van AD RMS naar Azure Rights Management](migrate-from-ad-rms-to-azure-rms.md).


## Stap 1: download de Azure Rights Management Administration Tool
Ga naar het Microsoft Downloadcentrum en download de [Azure Rights Management Administration Tool](https://go.microsoft.com/fwlink/?LinkId=257721), die de Azure RMS-beheermodule voor Windows PowerShell bevat.

Installeer het hulpprogramma. Zie [Installing Windows PowerShell for Azure Rights Management](../deploy-use/install-powershell.md) (Windows PowerShell voor Azure Rights Management installeren) voor instructies.

> [!NOTE]
> Als u deze Windows PowerShell-module eerder hebt gedownload, voert u de volgende opdracht uit om te controleren of u minimaal over versienummer 2.5.0.0 beschikt: `(Get-Module aadrm -ListAvailable).Version`

## Stap 2. Exporteer de configuratiegegevens uit AD RMS en importeer deze in Azure RMS
Deze stap bestaat uit twee fasen:

1.  Exporteer de configuratiegegevens vanuit AD RMS door de vertrouwde uitgiftedomeinen (TPD’s) te exporteren naar een XML-bestand. Dit proces is hetzelfde voor alle migraties.

2.  Importeer de configuratiegegevens naar Azure RMS. Er zijn verschillende processen voor deze stap, afhankelijk van de huidige configuratie van uw AD RMS-implementatie en uw voorkeurstopologie voor de Azure RMS-tenantsleutel.

### De configuratiegegevens vanuit AD RMS exporteren

> [!IMPORTANT]
> Voordat u deze procedure uitvoert, moet u eerst bevestigen dat uw AD RMS-servers worden uitgevoerd in de cryptografische modus 2, wat een vereiste is voor Azure RMS.
> 
> De cryptografische modus bevestigen:
> 
> - Voor Windows Server 2012 R2 en Windows 2012: Ga naar de eigenschappen voor AD RMS en kies het tabblad **Algemeen**. 
> 
> - Voor alle ondersteunde versies van AD RMS: gebruik de opties [RMS Analyzer](https://www.microsoft.com/en-us/download/details.aspx?id=46437) en **AD RMS-beheerder** om de cryptografische modus in de **RMS servicegegevens** weer te geven.
> 
> Zorg ervoor dat de waarde voor de cryptografische modus **2** is. Als dat niet het geval is, raadpleegt u de instructies voor het inschakelen van de cryptografische modus 2 in [AD RMS cryptografische modi](https://technet.microsoft.com/library/hh867439(v=ws.10).aspx).


Voer de volgende procedure uit voor alle AD RMS-clusters en voor alle vertrouwde uitgiftedomeinen die beveiligde inhoud voor uw organisatie bevatten. U hoeft dit niet uit te voeren voor clusters met alleen-licentieverlening.

#### De configuratiegegevens exporteren (gegevens van vertrouwd uitgiftedomein)

1.  Meld u bij het AD RMS-cluster aan als een gebruiker met machtigingen voor AD RMS-beheer.

2.  Vouw in de AD RMS-beheerconsole (**Active Directory Rights Management Services**) de naam van het AD RMS-cluster uit, vouw **Vertrouwensbeleid** uit en klik vervolgens op **Vertrouwde uitgiftedomeinen**.

3.  Selecteer in het resultatenvenster het vertrouwde uitgiftedomein en klik vervolgens in het deelvenster Acties op **Vertrouwd uitgiftedomein exporteren**.

4.  In het dialoogvenster **Vertrouwd uitgiftedomein exporteren**:

    -   Klik op **Opslaan als** en sla de gegevens op naar het pad en de bestandsnaam van uw keuze. Zorg ervoor dat u **.xml** opgeeft als bestandsnaamextensie (deze extensie wordt niet automatisch toegevoegd).

    -   Geef een sterk wachtwoord op en bevestig dit. Onthoud het wachtwoord. U hebt dit later nodig bij het importeren van de configuratiegegevens in Azure RMS.

    -   Schakel het selectievakje niet in om het vertrouwde domeinbestand op te slaan in RMS versie 1.0.

Wanneer u alle vertrouwde uitgiftedomeinen hebt geëxporteerd, bent u klaar om te beginnen met de procedure voor het importeren van deze gegevens in Azure RMS.

### De configuratiegegevens importeren naar Azure RMS
De precieze procedures voor deze stap zijn afhankelijk van de huidige configuratie van uw AD RMS-implementatie en van uw voorkeurstopologie voor de Azure RMS-tenantsleutel.

Uw huidige AD RMS-implementatie gaat een van de volgende configuraties gebruiken voor uw SLC-sleutel (serverlicentiecertificaat):

-   Wachtwoordbeveiliging in de AD RMS-database. Dit is de standaardconfiguratie.

-   HSM-beveiliging met een Thales HSM (Hardware Security Module).

-   HSM-beveiliging met een HSM (Hardware Security Module) van een andere leverancier dan Thales.

-   Wachtwoord beveiligd door een externe cryptografische provider.

> [!NOTE]
> Zie voor meer informatie over het gebruik van Hardware Security Modules met AD RMS het onderwerp [AD RMS gebruiken met Hardware Security Modules](http://technet.microsoft.com/library/jj651024.aspx).

Er zijn twee opties voor de topologie van de Azure RMS-tenantsleutel: Microsoft beheert uw tenantsleutel (**door Microsoft beheerd**) of u beheert uw tenantsleutel (**door de klant beheerd**) in Azure Key Vault. Wanneer u uw eigen Azure RMS-tenantsleutel beheert, wordt dit wordt soms aangeduid als 'Bring Your Own Key' (BYOK) en is er een HSM (Hardware Security Module) van Thales vereist. Zie [Uw Azure Rights Management-tenantsleutel plannen en implementeren](plan-implement-tenant-key.md) voor meer informatie

> [!IMPORTANT]
> Exchange Online is momenteel niet compatibel met BYOK in Azure RMS.  Als u BYOK na de migratie wilt gebruiken en u van plan bent Exchange Online te gebruiken, moet u goed begrijpen waarom deze configuratie leidt tot minder IRM-functionaliteiten voor Exchange Online. Lees de informatie in [BYOK-prijzen en -beperkingen](byok-price-restrictions.md) bij het kiezen van de beste topologie van de Azure RMS-tenantsleutel voor uw migratie.

Bepaal aan de hand van de volgende tabel welke procedure er voor uw migratie moet worden gevolgd. Combinaties die niet zijn opgenomen, worden niet ondersteund.

|Huidige AD RMS-implementatie|Gekozen topologie voor Azure RM- tenantsleutel|Migratie-instructies|
|-----------------------------|----------------------------------------|--------------------------|
|Wachtwoordbeveiliging in de AD RMS-database|Door Microsoft beheerd|Zie de migratieprocedure **Migratie van met software beveiligde sleutel naar met software beveiligde sleutel** na deze tabel.<br /><br />Dit is het eenvoudigste migratiepad. Hierbij is de enige vereiste dat u uw configuratiegegevens naar Azure RMS overdraagt.|
|HSM-beveiliging met een Thales nShield-HSM (Hardware Security Module)|Door de klant beheerd (BYOK)|Zie de migratieprocedure **Migratie van met HSM beveiligde sleutel naar met HSM beveiligde sleutel** na deze tabel.<br /><br />Hiervoor hebt u de BYOK-toolset van Azure Key Vault en drie sets stappen nodig om eerst uw sleutel over te dragen van uw on-premises HSM naar de Azure Key Vault HSM's, om vervolgens Azure RMS te autoriseren voor het gebruik van uw tenantsleutel en om tot slot de configuratiegegevens over te dragen naar Azure RMS.|
|Wachtwoordbeveiliging in de AD RMS-database|Door de klant beheerd (BYOK)|Zie de procedure **Migratie van met software beschermde sleutel naar met HSM beschermde sleutel** na deze tabel.<br /><br />Hiervoor hebt u de BYOK-toolset van Azure Key Vault en vier sets stappen nodig om eerst uw softwaresleutel op te halen en te importeren in een on-premises HSM, om vervolgens de sleutel over te dragen van uw on-premises HSM naar de Azure RMS HSM's, om vervolgens uw Key Vault-gegevens over te dragen naar Azure RMS en om tot slot de configuratiegegevens over te dragen naar Azure RMS.|
|HSM-beveiliging met een HSM (Hardware Security Module) van een andere leverancier dan Thales|Door de klant beheerd (BYOK)|Neem contact op met de leverancier van uw HSM voor instructies om de sleutel van deze HSM over te dragen naar een Thales nShield Hardware Security Module (HSM). Volg daarna de instructies voor de procedure **Migratie van met HSM beschermde sleutel naar met HSM beschermde sleutel** na deze tabel.|
|Met een wachtwoord beveiligd via een externe cryptografische provider|Door de klant beheerd (BYOK)|Neem contact op met de leverancier van uw cryptografische provider voor instructies over het overdragen van uw sleutel naar een Thales nShield Hardware Security Module (HSM). Volg daarna de instructies voor de procedure **Migratie van met HSM beschermde sleutel naar met HSM beschermde sleutel** na deze tabel.|
Controleer voordat u aan deze procedures begint, of u toegang hebt tot de XML-bestanden die u eerder hebt gemaakt tijdens het exporteren van de vertrouwde uitgiftedomeinen. Deze kunnen bijvoorbeeld worden opgeslagen op een USB-stick die u verplaatst van de AD RMS-server naar het werkstation met internetverbinding.

> [!NOTE]
> Ongeacht hoe u deze bestanden opslaat, moet u alle aanbevolen beveiligingsprocedures volgen, omdat deze gegevens uw persoonlijke sleutel bevatten.


Voor het voltooien van stap 2 kiest en selecteert u de instructies voor uw migratiepad: 


- [Met software beschermde sleutel naar met software beschermde sleutel](migrate-softwarekey-to-softwarekey.md)
- [Met HSM beschermde sleutel naar met HSM beschermde sleutel](migrate-hsmkey-to-hsmkey.md)
- [Met software beschermde sleutel naar met HSM beschermde sleutel](migrate-softwarekey-to-hsmkey.md)


## Stap 3. Uw RMS-tenant activeren
De instructies voor deze stap worden volledig behandeld in het artikel [Azure Rights Management activeren](../deploy-use/activate-service.md).


> [!TIP]
> Als u een Office 365-abonnement hebt, kunt u Azure RMS activeren vanuit het beheercentrum van Office 365 of vanuit de klassieke Azure-portal. U wordt aangeraden de klassieke Azure-portal te gebruiken, omdat u deze beheerportal gebruikt voor het voltooien van de volgende stap.

**Wat gebeurt er als uw Azure RMS-tenant is al geactiveerd?** Als de Azure RMS-service al is geactiveerd voor uw organisatie, hebben gebruikers mogelijk al gewerkt met Azure RMS om inhoud met een automatisch gegenereerde tenantsleutel (en de standaardsjablonen) te beveiligen in plaats van met uw bestaande sleutels (en sjablonen) van AD RMS. De kans is klein dat dit op uw intranet gebeurt op computers die goed worden beheerd, omdat ze automatisch worden geconfigureerd voor uw AD RMS-infrastructuur. Dit probleem kan echter wel optreden op werkgroepcomputers en op computers die niet vaak verbinding met uw intranet maken. Helaas is het ook moeilijk om deze computers te identificeren. Daarom raden we u aan de service pas te activeren nadat u de configuratiegegevens uit AD RMS hebt geïmporteerd.

Als uw Azure RMS-tenant al is geactiveerd en u deze computers kunt identificeren, moet u hierop het script CleanUpRMS_RUN_Elevated.cmd uitvoeren, zoals beschreven in stap 5. Door dit script uit te voeren, worden deze computers gedwongen de gebruikersomgeving opnieuw te initialiseren, zodat ze de bijgewerkte tenantsleutel en de geïmporteerde sjablonen moeten downloaden.

Als u daarnaast aangepaste sjablonen hebt gemaakt die u na de migratie wilt gebruiken, moet u deze exporteren en vervolgens importeren. Deze procedure wordt beschreven in de volgende stap. 

## Stap 4. Geïmporteerde sjablonen configureren
Omdat de status van de door u geïmporteerde sjablonen standaard **Gearchiveerd** is, moet u deze status wijzigen in **Gepubliceerd** als u wilt dat gebruikers deze sjablonen met Azure RMS kunnen gebruiken.

Sjablonen die u uit AD RMS importeert, hebben hetzelfde uiterlijk en gedrag als aangepaste sjablonen die u in de klassieke Azure-portal kunt maken. Zie [Aangepaste sjablonen configureren voor Azure Rights Management](../deploy-use/configure-custom-templates.md) om de geïmporteerde sjablonen te wijzigen, zodat ze kunnen worden gepubliceerd en gebruikers ze kunnen weergeven en selecteren vanuit toepassingen.

Naast het publiceren van uw zojuist geïmporteerde sjablonen, zijn er voordat u doorgaat met de migratie twee belangrijke wijzigingen die u wellicht voor de sjablonen wilt aanbrengen. Voor een consistente gebruikerservaring tijdens het migratieproces mag u geen aanvullende wijzigingen aanbrengen in de geïmporteerde sjablonen, de twee standaardsjablonen die worden geleverd met Azure RMS niet publiceren en op dit moment geen nieuwe sjablonen maken. Wacht in plaats daarvan totdat de migratie voltooid is en u de AD RMS-servers buiten gebruik hebt gesteld.

De sjabloonwijzigingen die u mogelijk moet aanbrengen voor deze stap:

- Als u vóór de migratie aangepaste sjablonen in Azure RMS hebt gemaakt, moet u deze handmatig exporteren en importeren.

- Als voor uw sjablonen in AD RMS de groep **IEDEREEN** is gebruikt, moet u de equivalente groep en rechten handmatig toevoegen.

## Procedure als u vóór de migratie aangepaste sjablonen hebt gemaakt

Als u vóór de migratie (voor of na het activeren van Azure RMS) aangepaste sjablonen hebt gemaakt, zijn deze sjablonen na de migratie niet meer beschikbaar voor gebruikers, zelfs niet als ze zijn ingesteld op **Gepubliceerd**. Als u deze sjablonen beschikbaar wilt maken voor gebruikers, moet u eerst het volgende doen: 

1. Identificeer de sjablonen en noteer de sjabloon-id's door [Get-AadrmTemplate](https://msdn.microsoft.com/library/dn727079.aspx) uit te voeren. 

2. Exporteer de sjablonen met behulp van de PowerShell-cmdlet voor Azure RMS [Export-AadrmTemplate](https://msdn.microsoft.com/library/dn727078.aspx).

3. Importeer de sjablonen met behulp van de PowerShell-cmdlet voor Azure RMS [Import-AadrmTemplate](https://msdn.microsoft.com/library/dn727077.aspx).

Vervolgens kunt u deze sjablonen publiceren of archiveren net als elke andere sjabloon die u na de migratie maakt.


## Procedure als voor de sjablonen in AD RMS de groep **IEDEREEN** is gebruikt

Als voor uw sjablonen in AD RMS de groep **IEDEREEN** is gebruikt, wordt deze groep automatisch verwijderd wanneer u de sjablonen in Azure RMS importeert. U moet de equivalente groep of gebruikers en dezelfde rechten handmatig toevoegen aan de geïmporteerde sjablonen. De equivalente groep voor Azure RMS heet **AllStaff-7184AB3F-CCD1-46F3-8233-3E09E9CF0E66@<tenant_name>.onmicrosoft.com**. Deze groep kan er voor Contoso bijvoorbeeld als volgt uitzien: **AllStaff-7184AB3F-CCD1-46F3-8233-3E09E9CF0E66@contoso.onmicrosoft.com**.

Als u niet zeker weet of uw AD RMS-sjablonen de groep IEDEREEN bevat, kunt u het volgende Windows PowerShell-voorbeeldscript gebruiken om deze sjablonen te identificeren. Zie [Windows PowerShell gebruiken om AD RMS te beheren](https://technet.microsoft.com/library/ee221079%28v=ws.10%29.aspx) voor meer informatie over het gebruik van Windows PowerShell met Azure RMS.

U kunt de automatisch gemaakte groep van uw organisatie zien als u een van de standaardrechtenbeleidssjablonen in de klassieke Azure-portal kopieert en vervolgens de **GEBRUIKERSNAAM** identificeert op de pagina **RECHTEN**. U kunt de klassieke portal echter niet gebruiken om deze groep toe te voegen aan een sjabloon die handmatig is gemaakt of geïmporteerd. In plaats daarvan moet u een van de volgende Azure RMS PowerShell-opties gebruiken:

-   Gebruik de PowerShell-cmdlet [New-AadrmRightsDefinition](https://msdn.microsoft.com/library/azure/dn727080.aspx) om de groep ‘AllStaff’ en rechten te definiëren als een rechtendefinitieobject. Voer deze opdracht opnieuw uit voor elk van de andere groepen of gebruikers waaraan al rechten waren verleend in de oorspronkelijke sjabloon naast de groep IEDEREEN. Voeg vervolgens al deze rechtendefinitieobjecten toe aan de sjablonen met behulp van de cmdlet [Set-AadrmTemplateProperty](https://msdn.microsoft.com/library/azure/dn727076.aspx).

-   Gebruik de cmdlet [Export-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727078.aspx) om de sjabloon te exporteren naar een XML-bestand dat u kunt bewerken om de groep ‘AllStaff’ en rechten toe te voegen aan de bestaande groepen en rechten. Gebruik vervolgens de cmdlet [Import-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727077.aspx) om deze wijziging weer te importeren in Azure RMS.

> [!NOTE]
> Deze aan ‘AllStaff’ gelijkwaardige groep is niet precies hetzelfde als de groep IEDEREEN in AD RMS: de groep ‘AllStaff’ bevat alle gebruikers in uw Azure-tenant, terwijl de groep IEDEREEN alle geverifieerde gebruikers bevat die zich buiten uw organisatie kunnen bevinden.
> 
> Door dit verschil tussen de twee groepen moet u naast de groep ‘AllStaff’ wellicht ook externe gebruikers toevoegen. Externe e-mailadressen voor groepen worden momenteel niet ondersteund.


### Windows PowerShell-voorbeeldscript om AD RMS-sjablonen te identificeren die de groep IEDEREEN bevatten
Dit gedeelte bevat het voorbeeldscript om u te helpen bij het identificeren van AD RMS-sjablonen waarvoor de groep IEDEREEN is gedefinieerd, zoals beschreven in voorgaande sectie.

**Disclaimer**: dit voorbeeldscript wordt onder geen enkel ondersteuningsprogramma of -service op basis van Microsoft-standaard ondersteund. Dit voorbeeldscript wordt verstrekt 'in de huidige vorm' zonder garantie van welke aard dan ook.

```
import-module adrmsadmin 

New-PSDrive -Name MyRmsAdmin -PsProvider AdRmsAdmin -Root https://localhost -Force 

$ListofTemplates=dir MyRmsAdmin:\RightsPolicyTemplate

foreach($Template in $ListofTemplates) 
{ 
                $templateID=$Template.id

                $rights = dir MyRmsAdmin:\RightsPolicyTemplate\$Templateid\userright

     $templateName=$Template.DefaultDisplayName 

        if ($rights.usergroupname -eq "anyone")

                         {
                           $templateName = $Template.defaultdisplayname

                           write-host "Template " -NoNewline

                           write-host -NoNewline $templateName -ForegroundColor Red

                           write-host " contains rights for " -NoNewline

                           write-host ANYONE  -ForegroundColor Red
                         }
 } 
Remove-PSDrive MyRmsAdmin -force
```


## Volgende stappen
Ga naar [fase 2 - configuratie aan clientzijde](migrate-from-ad-rms-phase2.md).




<!--HONumber=Aug16_HO3-->


