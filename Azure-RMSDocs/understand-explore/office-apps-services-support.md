---
title: Office-toepassingen en -services | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 06/30/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 388e67cd-c16f-4fa0-a7bb-ffe0def2be81
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 99eb67f6296ad1782c787aabb73a28458c02f367
ms.openlocfilehash: affb37cc3b991609f5de51370485b10fed932421


---


# Office-toepassingen en -services

*Van toepassing op: Azure Rights Management, Office 365*

Office-toepassingen voor eindgebruikers (zoals Word, Excel, PowerPoint en Outlook) en Office-services (zoals Exchange en SharePoint) kunnen gebruikmaken van Microsoft Azure Rights Management om gegevens van uw organisatie te beveiligen.

## Office-toepassingen: Word, Excel, PowerPoint, Outlook
Deze toepassingen bieden standaard ondersteuning voor Rights Management door het gebruik van IRM (Information Rights Management) en bieden gebruikers de mogelijkheid om beveiliging toe te passen op een opgeslagen document of op een e-mailbericht dat wordt verzonden. Gebruikers kunnen sjablonen toepassen of, voor Word, Excel en PowerPoint, zeer aangepaste instellingen kiezen voor toegang, rechten en gebruiksbeperkingen. 

Gebruikers kunnen een Word-bestand bijvoorbeeld zo configureren, dat dit alleen kan worden geopend door mensen in uw organisatie of ze kunnen bepalen dat een Excel-spreadsheet kan worden bewerkt, tot alleen-lezen wordt beperkt, of voorkomen dat het wordt afgedrukt. Er kan voor tijdsgebonden bestanden een vervaltijd worden geconfigureerd (rechtstreeks door gebruikers of door het toepassen van een sjabloon) waarna het bestand niet meer kan worden geopend. Gebruikers kunnen voor Outlook de optie **Niet doorsturen** kiezen om te voorkomen dat gegevens worden gelekt, en een sjabloon kiezen.

## Exchange Online en Exchange Server
Wanneer u Exchange Online of Exchange Server gebruikt, kunt u gebruikmaken van de integratie met IRM (Information Rights Management), die u toegang geeft tot aanvullende oplossingen voor gegevensbeveiliging:

-   **Exchange ActiveSync IRM**, waarmee e-mailberichten kunnen worden beveiligd en beveiligde e-mailberichten kunnen worden ontvangen met mobiele apparaten.

-   RMS-ondersteuning voor **Outlook Web App**, die ook op de Outlook-client wordt geïmplementeerd zodat gebruikers hun e-mailberichten kunnen beveiligen via sjablonen of door afzonderlijke opties op te geven. Daarnaast kunnen gebruikers beveiligde e-mailberichten lezen en gebruiken die aan hen worden verzonden.

-   **Beveiligingsregels** voor Outlook-clients die een beheerder kan configureren zodat RMS-sjablonen automatisch worden toegepast op e-mailberichten voor de opgegeven ontvangers. Zo kunt u ervoor zorgen dat interne e-mailberichten die naar uw juridische afdeling worden verzonden, alleen worden gelezen door medewerkers van de juridische afdeling en dat deze niet kunnen worden doorgestuurd. Er wordt voor gebruikers weergegeven dat er beveiliging op het e-mailbericht is toegepast voordat ze het verzenden. Standaard kunnen gebruikers de beveiliging verwijderen als ze deze niet nodig achten. E-mailberichten worden versleuteld voordat ze worden verzonden. Zie [Outlook Protection Rules](https://technet.microsoft.com/library/dd638178%28v=exchg.150%29.aspx) (Outlook-beveiligingsregels) en [Create an Outlook Protection Rule](https://technet.microsoft.com/library/dd638196%28v=exchg.150%29.aspx) (Een Outlook-beveiligingsregel maken) in de Exchange-bibliotheek voor meer informatie.

-   **Transportregels** die een beheerder configureert zodat RMS-sjablonen automatisch worden toegepast op e-mailberichten op basis van eigenschappen zoals afzender, geadresseerde , berichtonderwerp en inhoud. Deze zijn te vergelijken met beveiligingsregels, maar bieden gebruikers echter niet de mogelijkheid om de beveiliging te verwijderen. De regels kunnen worden toegepast op Outlook Web Access en e-mailberichten die worden verzonden met mobiele apparaten, maar e-mailberichten worden niet versleuteld voordat ze via de client worden verzonden. Zie [Create a Transport Protection Rule](https://technet.microsoft.com/library/dd302432.aspx) (Een transportbeveiligingsregel maken) in de Exchange-bibliotheek voor meer informatie.

-   **DLP-beleid (preventie van gegevensverlies)** dat sets met voorwaarden bevat waarmee e-mailberichten kunnen worden gefilterd en dat wordt ingezet om gegevensverlies te voorkomen voor vertrouwelijke of gevoelige inhoud (bijvoorbeeld persoonlijke gegevens of creditcardgegevens). Er kan worden gebruikgemaakt van beleidstips wanneer gevoelige gegevens worden gedetecteerd. Hiermee worden gebruikers geïnformeerd dat ze mogelijk gegevensbeveiliging moeten toepassen op basis van de informatie in het e-mailbericht. Zie [Data Loss Prevention](https://technet.microsoft.com/library/jj150527%28v=exchg.150%29.aspx) (Preventie van gegevensverlies) in de Exchange-bibliotheek voor meer informatie.

-   **Office 365-berichtversleuteling** waarbij wordt gebruikgemaakt van transportregels om versleutelde e-mailberichten naar mensen buiten uw bedrijf te verzenden. Het e-mailbericht wordt gelezen in een browser met een interface die vergelijkbaar is met Outlook Web App. U kunt de vrijwaringstekst en koptekst in de versleutelde e-mailberichten van uw bedrijf aanpassen en zelfs uw bedrijfslogo toevoegen. Zie [Office 365-berichtversleuteling](https://office.microsoft.com/o365-message-encryption-FX104179182.aspx) op de Office-website voor meer informatie.

Als u Exchange Server gebruikt, kunt u de functies voor gegevensbeveiliging van [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] gebruiken door de RMS-connector te implementeren, die als een relay fungeert tussen uw on-premises servers en de RMS-cloudservice. Zie [De Azure Rights Management-connector implementeren](../deploy-use/deploy-rms-connector.md) voor meer informatie.

## SharePoint Online en SharePoint Server
Wanneer u SharePoint Online of SharePoint Server gebruikt, kunt u gebruikmaken van de integratie met IRM (Information Rights Management) die beheerders de mogelijkheid biedt om lijsten of bibliotheken te beveiligen. Op die manier is een bestand beveiligd wanneer dit door een gebruiker wordt uitgecheckt, zodat alleen gemachtigde personen het bestand kunnen bekijken en dit kunnen gebruiken volgens de beleidsregels voor gegevensbeveiliging die u opgeeft. Voor het bestand kan bijvoorbeeld zijn bepaald dat het alleen-lezen is, het kopiëren van tekst is uitgeschakeld en dat het opslaan van een lokale kopie en het afdrukken van het bestand niet mogelijk is.

De gegevensbeveiliging voor lijsten en bibliotheken wordt altijd toegepast door een beheerder en nooit door een eindgebruiker. De gegevensbeveiliging wordt voor alle documenten in de container toegepast op het niveau van de lijst of de bibliotheek, en niet op het niveau van de afzonderlijke bestanden.  Als u SharePoint Online gebruikt, kunnen gebruikers ook IRM toepassen op hun OneDrive voor Bedrijven-bibliotheek.

De IRM-service moet eerst worden ingeschakeld voor SharePoint. Vervolgens geeft u Information Rights Management op voor een bibliotheek. In het geval van SharePoint Online en OneDrive voor Bedrijven kunnen gebruikers ook Information Rights Management opgeven voor hun OneDrive voor Bedrijven-bibliotheek. SharePoint maakt geen gebruik van rechtenbeleidsjablonen, hoewel u bepaalde configuratie-instellingen voor SharePoint kunt selecteren die sterke overeenkomst vertonen met de instellingen die u in sjablonen kunt opgeven.

Als u SharePoint Server gebruikt, kunt u de functies voor gegevensbeveiliging van [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] gebruiken door de RMS-connector te implementeren, die als een relay fungeert tussen uw on-premises servers en de RMS-cloudservice. Zie [De Azure Rights Management-connector implementeren](../deploy-use/deploy-rms-connector.md) voor meer informatie.

> [!NOTE]
> Er zijn momenteel enkele beperkingen wanneer u IRM met SharePoint gebruikt:
> 
> -   U kunt de standaardsjablonen of aangepaste sjablonen die u in de klassieke Azure-portal beheert, niet gebruiken.
> -   Bestanden met de bestandsextensie .ppdf voor beveiligde PDF-bestanden worden niet ondersteund. Bestanden met de bestandsextensie .pdf en die standaard door RMS zijn beveiligd, worden ondersteund wanneer u een PDF-reader gebruikt die standaard RMS ondersteunt.
> -   Omdat Office voor mobiele apparaten nog geen ondersteuning biedt voor RMS, moeten deze apparaten gebruikmaken van een browser voor het weergeven van bestanden die met RMS zijn beveiligd en kunnen de bestanden alleen worden gelezen.

Azure RMS past gebruiksbeperkingen en gegevensversleuteling toe voor documenten wanneer deze worden gedownload van SharePoint, en niet wanneer het document in SharePoint wordt gemaakt of naar de bibliotheek wordt geüpload. Zie [Data Encryption in OneDrive for Business and SharePoint Online](https://technet.microsoft.com/library/dn905447.aspx) (Gegevensversleuteling in OneDrive voor Bedrijven en SharePoint Online) in de SharePoint-documentatie voor meer informatie over het beveiligen van documenten voordat ze worden gedownload.

Zie [What’s New with Information Rights Management in SharePoint and SharePoint Online](http://blogs.office.com/2012/11/09/whats-new-with-information-rights-management-in-sharepoint-and-sharepoint-online/) (Wat is er nieuw voor Information Rights Management in SharePoint en SharePoint Online) in de Office-blog voor meer informatie over het gebruik van Azure RMS met SharePoint

## Volgende stappen

Zie [Hoe toepassingen ondersteuning bieden voor Azure Rights Management](applications-support.md) voor meer informatie over de wijze waarop andere toepassingen en services ondersteuning bieden voor Azure Rights Management.


<!--HONumber=Jul16_HO1-->


