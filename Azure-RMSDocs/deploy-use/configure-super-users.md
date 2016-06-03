---
# required metadata

title: Supergebruikers configureren voor Azure Rights Management en detectieservices of gegevensherstel | Azure RMS
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: acb4c00b-d3a9-4d74-94fe-91eeb481f7e3

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Supergebruikers configureren voor Azure Rights Management en detectieservices of gegevensherstel

*Van toepassing op: Azure Rights Management, Office 365*

De functie van supergebruiker van Microsoft [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] (Azure RMS) zorgt ervoor dat gemachtigde personen en services de gegevens die voor uw organisatie worden beveiligd met Azure RMS, altijd kunnen lezen en controleren. Een supergebruiker kan zo nodig ook de beveiliging verwijderen of de eerder toegepaste beveiliging wijzigen. Een supergebruiker heeft altijd volledige eigenaarsrechten voor alle licenties die door de RMS-tenant van de organisatie zijn verleend. Deze mogelijkheid wordt soms aangeduid als ‘reasoning over data’ en vormt een cruciaal element in het beheer van de gegevens van uw organisatie. U zou deze functie bijvoorbeeld kunnen gebruiken voor een van de volgende scenario's:

-   Een werknemer verlaat de organisatie en u moet de bestanden lezen die door hem/haar zijn beveiligd.

-   Een IT-beheerder moet het huidige beveiligingsbeleid verwijderen dat is geconfigureerd voor bestanden en een nieuw beveiligingsbeleid toepassen.

-   Exchange-Server moet postvakken indexeren voor zoekopdrachten.

-   U hebt bestaande IT-services voor het voorkomen van gegevensverlies (DLP), gateways voor de versleuteling van inhoud (CEG) en anti-malwareproducten die nodig zijn om bestanden te controleren die al worden beveiligd.

-   U moet bulksgewijs bestanden ontsleutelen ten behoeve van controle, om juridische redenen of om andere nalevingsredenen.

Standaard is de functie van supergebruiker niet ingeschakeld en zijn er geen gebruikers aan deze rol toegewezen. De functie wordt automatisch ingeschakeld als u de Rights Management-connector voor Exchange configureert en is niet vereist voor standaardservices die Exchange Online, SharePoint Online of SharePoint-Server uitvoeren.

Als u de functie van supergebruiker handmatig moet inschakelen, gebruikt u de Windows PowerShell-cmdlet [Enable-AadrmSuperUserFeature](https://msdn.microsoft.com/library/azure/dn629400.aspx) en wijst u vervolgens zo nodig gebruikers (of serviceaccounts) toe met behulp van de cmdlet [Add-AadrmSuperUser](https://msdn.microsoft.com/library/azure/dn629411.aspx) of de cmdlet [Set-AadrmSuperUserGroup](https://msdn.microsoft.com/library/azure/mt653943.aspx). Daarna kunt u naar behoefte gebruikers (of andere groepen) aan deze groep toevoegen. 

> [!NOTE]
> Zie [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)]Windows PowerShell voor Azure Rights Management installeren[ als u de Windows PowerShell-module nog niet hebt geïnstalleerd.](install-powershell.md).

Aanbevolen beveiligingsprocedures voor de functie van supergebruiker:

-   Beperk en controleer de beheerders die als algemeen beheerder zijn toegewezen voor uw Office 365- of Azure RMS-tenant, of aan wie de rol van GlobalAdministrator is toegewezen met behulp van de cmdlet [Add-AadrmRoleBasedAdministrator](https://msdn.microsoft.com/library/azure/dn629417.aspx). Deze gebruikers kunnen de functie van supergebruiker inschakelen en gebruikers (en zichzelf) toewijzen als supergebruiker en mogelijk alle bestanden ontsleutelen die door uw organisatie worden beveiligd.

-   Gebruik de [cmdlet Get-AadrmSuperUser](https://msdn.microsoft.com/library/azure/dn629408.aspx) om te zien welke gebruikers en serviceaccounts afzonderlijk als supergebruiker zijn toegewezen. Als u wilt nagaan of er een supergebruikersgroep is geconfigureerd, gebruikt u de cmdlet [Get-AadrmSuperUser](https://msdn.microsoft.com/library/azure/mt653942.aspx) en uw standaardprogramma's voor gebruikersbeheer om te controleren welke gebruikers deel uitmaken van deze groep. Zoals bij alle beheeracties, wordt ook het inschakelen of uitschakelen van de functie van supergebruiker en het toevoegen of verwijderen van gebruikers in een logboek geregistreerd. U kunt dit raadplegen met behulp van de opdracht [Get-AadrmAdminLog](https://msdn.microsoft.com/library/azure/dn629430.aspx). Wanneer supergebruikers bestanden ontsleutelen, wordt deze actie in het logboek geregistreerd en kan dit worden gecontroleerd met [logboekregistratie van gebruik](log-analyze-usage.md)..

-   Als u de functie van supergebruiker niet nodig hebt voor dagelijkse services, kunt u de functie inschakelen wanneer u deze nodig hebt en weer uitschakelen met behulp van de cmdlet [Disable-AadrmSuperUserFeature](https://msdn.microsoft.com/library/azure/dn629428.aspx).

Het volgende logboekbestandextract toont een aantal voorbeeldvermeldingen uit de cmdlet Get-AadrmAdminLog. In dit voorbeeld bevestigt de beheerder van Contoso Ltd dat de functie van supergebruiker is uitgeschakeld, voegt deze Richard Simone toe als supergebruiker, controleert deze of Richard de enige supergebruiker is die is geconfigureerd voor Azure RMS en schakelt deze vervolgens de functie van supergebruiker in, zodat Richard nu bepaalde bestanden kan ontsleutelen die zijn beveiligd door een werknemer die het bedrijf heeft verlaten.

`2015-08-01T18:58:20    admin@contoso.com   GetSuperUserFeatureState    Passed  Disabled`

`2015-08-01T18:59:44    admin@contoso.com   AddSuperUser -id rsimone@contoso.com    Passed  True`

`2015-08-01T19:00:51    admin@contoso.com   GetSuperUser    Passed  rsimone@contoso.com`

`2015-08-01T19:01:45    admin@contoso.com   SetSuperUserFeatureState -state Enabled Passed  True`

## Scriptopties voor supergebruikers
Vaak moet iemand die als supergebruiker voor [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] is toegewezen, de beveiliging verwijderen van meerdere bestanden op meerdere locaties. Het is mogelijk om dit handmatig te doen, maar het is efficiënter (en vaak betrouwbaarder) om het met een script te doen. [Download hiervoor het RMS-beveiligingshulpprogramma](http://www.microsoft.com/en-us/download/details.aspx?id=47256). Gebruik vervolgens de cmdlet [Unprotect RMSFile](https://msdn.microsoft.com/library/azure/mt433200.aspx) en de cmdlet [Protect-RMSFile](https://msdn.microsoft.com/library/azure/mt433201.aspx).

Zie [RMS-beveiligingscmdlets](https://msdn.microsoft.com/library/azure/mt433195.aspx) voor meer informatie over deze cdmlets..

> [!NOTE]
> De RMS-beveiliging PowerShell-module die wordt geleverd met het RMS-beveiligingshulpprogramma, wijkt af van en vormt een aanvulling op de belangrijkste [Windows PowerShell-module voor Azure Rights Management](administer-powershell.md). De RMS-beveiligingsmodule ondersteunt zowel Azure RMS als AD RMS.




<!--HONumber=Apr16_HO4-->


