---
title: Technisch overzicht voor de Rights Management-toepassing voor delen | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 07/15/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: f7b13fa4-4f8e-489a-ba46-713d7a79f901
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 09effc3dfb238370563981defdcf3c3b4cffcaae
ms.openlocfilehash: 2f249996b9b912f744754357423a0c4f134ec094


---


# Technisch overzicht en beveiligingsdetails voor de Microsoft Rights Management-toepassing voor delen

*Van toepassing op: Active Directory Rights Management Services, Azure Rights Management, Windows 10, Windows 7 met SP1, Windows 8, Windows 8.1*


De Microsoft Rights Management-toepassing voor delen is een optionele downloadbare toepassing voor Microsoft Windows en andere platforms die voorziet in het volgende:

-   Beveiliging van één bestand of bulksgewijs beveiligen van meerdere bestanden of van alle bestanden in een geselecteerde map.

-   Volledige ondersteuning voor de beveiliging van elk bestandstype met een ingebouwde viewer voor veelgebruikte tekst- en afbeeldingsbestandstypen.

-   Algemene beveiliging voor bestanden die RMS-beveiliging niet ondersteunen.

-   Volledige interoperabiliteit met bestanden die zijn beveiligd met Office Information Rights Management (IRM).

-   Volledige compatibiliteit met pdf-bestanden die zijn beveiligd met File Classification Infrastructure (FCI) en ondersteunde pdf-hulpprogramma's voor autoriseren.

De Microsoft Rights Management-toepassing voor delen maakt gebruik van de nieuwe [AD RMS Client 2.1-runtime](http://www.microsoft.com/download/details.aspx?id=38396). Met behulp van de functionaliteit van AD RMS 2.1 hebben eindgebruikers dankzij de Microsoft Rights Management-toepassing voor delen een eenvoudige ervaring met beveiliging en verbruik.

Met de versie van oktober 2013 van RMS kunt u documenten beveiligen met behulp van Office 2010 en ze verzenden naar mensen in een ander bedrijf, die de documenten vervolgens kunnen gebruiken met Azure RMS. Bovendien kunt u in deze versie, als u AD RMS in de cryptografische modus 2 gebruikt, RMS voor personen gebruiken en inhoud gebruiken van personen bij een ander bedrijf dat Azure RMS gebruikt. Zie [AD RMS Cryptographic Modes](http://technet.microsoft.com/library/hh867439%28v=ws.10%29.aspx) (Cryptografische modi van AD RMS) voor meer informatie over de cryptografische modus 2.

Zie [Automatische implementatie voor de Microsoft Rights Management-toepassing voor delen](sharing-app-admin-guide.md#automatic-deployment-for-the-microsoft-rights-management-sharing-application) voor informatie over de implementatie

## Beveiligingsniveaus: systeemeigen en algemeen
Microsoft Rights Management-toepassing voor delen ondersteunt beveiliging op twee verschillende niveaus, zoals beschreven in de volgende tabel.

|Type beveiliging|Systeemeigen|Algemeen|
|----------------------|----------|-----------|
|Beschrijving|Voor tekst-, afbeelding-, Microsoft Office- (Word, Excel, PowerPoint), .pdf-bestanden en andere bestandstypen van toepassingen die AD RMS ondersteunen, biedt systeemeigen beveiliging een hoog beveiligingsniveau met zowel versleuteling als handhaving van rechten (machtigingen).|Voor alle andere toepassingen en bestandstypen biedt algemene beveiliging een beveiligingsniveau dat bestandsinkapseling met het .pfile-bestandstype bevat en verificatie om te controleren of een gebruiker is gemachtigd om het bestand te openen.|
|Protection|Bestanden zijn volledig versleuteld en beveiliging wordt afgedwongen op de volgende manieren:<br /><br />- Voordat beveiligde inhoud wordt weergegeven, moet de verificatie zonder fouten zijn voltooid voor degenen die het bestand via e-mail ontvangen of toegang krijgen tot het bestand via bestandsmachtigingen of machtigingen voor delen.<br /><br />- Bovendien worden gebruiksrechten en -beleid die door de eigenaar van de inhoud tijdens het beveiligen van de bestanden zijn ingesteld, volledig afgedwongen als de inhoud wordt weergegeven in de IP-viewer (voor beveiligde tekst- en afbeeldingsbestanden) of de bijbehorende toepassing (voor alle andere ondersteunde bestandstypen).|Bestandsbeveiliging wordt afgedwongen op de volgende manieren:<br /><br />- Voordat beveiligde inhoud wordt weergegeven, moet de verificatie zonder fouten zijn voltooid voor gebruikers die zijn gemachtigd om het bestand te openen en te gebruiken. Als de verificatie is mislukt, wordt het bestand niet geopend.<br /><br />- Gebruiksrechten en -beleid die door de eigenaar van de inhoud zijn ingesteld, worden weergegeven om de gemachtigde gebruikers te informeren over het beoogde gebruiksbeleid.<br /><br />- Controlegebeurtenissen vastleggen wordt uitgevoerd voor gemachtigde gebruikers die bestanden openen en gebruiken. Er worden echter geen gebruiksrechten afgedwongen door niet-ondersteunde toepassingen.|
|Standaard voor bestandstypen|Dit is het standaard beveiligingsniveau voor de volgende bestandstypen:<br /><br />- Tekst- en afbeeldingsbestanden<br /><br />- Microsoft Office-bestanden (Word, Excel en PowerPoint)<br /><br />- Portable document format (.pdf)<br /><br />Zie de sectie [Ondersteunde bestandstypen en bestandsnaamextensies](#supported-file-types-and-file-name-extensions) voor meer informatie.|Dit is de standaardbeveiliging voor alle andere bestandstypen (zoals .vsdx en .rtf) die niet worden ondersteund door volledige beveiliging.|
U kunt het standaard beveiligingsniveau wijzigen dat de RMS-toepassing voor delen toepast. U kunt het standaardniveau wijzigen van systeemeigen naar algemeen, van algemeen naar systeemeigen en u kunt zelfs voorkomen dat de RMS-toepassing voor delen beveiliging toepast. Zie voor meer informatie de sectie [Het standaardbeveiligingsniveau van bestanden wijzigen](#changing-the-default-protection-level-of-files) in dit artikel.

## Ondersteunde bestandstypen en bestandsnaamextensies
De volgende tabel bevat bestandstypen die ondersteund worden door de Microsoft Rights Management-toepassing voor delen. Voor deze bestandstypen wordt de originele bestandsnaamextensie gewijzigd wanneer de systeemeigen beveiliging wordt toegepast en deze bestanden worden alleen-lezen.

Wanneer de RMS-toepassing voor delen een Word-, Excel-, of PowerPoint-bestand beveiligt, maakt deze actie bovendien automatisch een tweede bestand dat een kopie is van het origineel. Dit bestand heeft dezelfde bestandsnaam maar de bestandsnaamextensie **.ppdf**¹. Deze versie van het bestand zorgt ervoor dat ontvangers die de RMS-toepassing voor delen installeren altijd het bestand kunnen openen waarop systeemeigen beveiliging toegepast is.

Voor bestanden die algemeen zijn beveiligd, wordt de originele bestandsnaamextensie altijd gewijzigd naar .pfile.

> [!WARNING]
> Als u firewalls, webproxy's of beveiligingssoftware hebt die bestandsnaamextensies controleert en aanpakt, dan moet u deze mogelijk opnieuw configureren om deze nieuwe bestandsnaamextensies te ondersteunen.

|Oorspronkelijke bestandsnaamextensie|RMS-beveiligde bestandsnaamextensie|
|--------------------------------|-------------------------------------|
|.txt|.ptxt|
|.xml|.pxml|
|.jpg|.pjpg|
|.jpeg|.ppng|
|.pdf|.ppdf|
|.png|.ppng|
|.tif|.ptif|
|.tiff|.ptiff|
|.bmp|.pbmp|
|.gif|.pgif|
|.giff|.pgiff|
|.jpe|.pjpe|
|.jfif|.pjfif|
|.jt|.pjt|
¹ PDF-Rendering mogelijk gemaakt door Foxit. Copyright © 2003-2014 van Foxit Corporation.

De volgende tabel bevat de bestandstypen die de Microsoft Rights Management-toepassing voor delen ondersteunt in Microsoft Office 2016, Office 2013 en Office 2010. Voor deze bestanden blijft de bestandsnaamextensie hetzelfde nadat het bestand is beveiligd door RMS.

|Bestandstypen die worden ondersteund door Office|Bestandstypen die worden ondersteund door Office|
|----------------------------------|----------------------------------|
|.doc<br /><br />.docm<br /><br />.docx<br /><br />.dot<br /><br />.dotm<br /><br />.dotx<br /><br />.potm<br /><br />.potx<br /><br />.pps<br /><br />.ppsm<br /><br />.ppsx<br /><br />.ppt<br /><br />.pptm|.pptx<br /><br />.thmx<br /><br />.xla<br /><br />.xlam<br /><br />.xls<br /><br />.xlsb<br /><br />.xlt<br /><br />.xlsm<br /><br />.xlsx<br /><br />.xltm<br /><br />.xltx<br /><br />.xps|

### Het standaard beveiligingsniveau van bestanden wijzigen
U kunt wijzigen hoe de RMS-toepassing voor delen bestanden beveiligt door het register te bewerken. U kunt bijvoorbeeld bestanden die systeemeigen beveiliging ondersteunen forceren om algemeen beveiligd te worden door de RMS-toepassing voor delen.

Redenen waarom u dit zou willen:

-   Om ervoor te zorgen dat alle gebruikers het bestand vanuit hun mobiele apparaten kunnen openen.

-   Om ervoor te zorgen dat alle gebruikers het bestand kunnen openen als ze geen toepassing hebben die systeemeigen beveiliging ondersteunt.

-   Voor beveiligingssystemen die maatregelen nemen op bestanden vanwege de bestandsnaamextensie en opnieuw kunnen worden geconfigureerd voor de .pfile bestandsnaamextensie maar niet opnieuw kunnen worden geconfigureerd voor meerdere bestandsnaamextensies voor systeemeigen beveiliging.

Op deze manier kunt u de RMS-toepassing voor delen systeemeigen beveiliging laten afdwingen op bestanden die standaard algemene beveiliging zouden krijgen. Dit kan uitkomen als u een toepassing hebt die de RMS API's ondersteunt, bijvoorbeeld een bedrijfstoepassing dat door uw interne ontwikkelaars is geschreven of een toepassing die van een onafhankelijke softwareleverancier is gekocht (ISV).

U kunt de RMS-toepassing voor delen ook de beveiliging van bestanden laten afdwingen (geen systeemeigen of algemene beveiliging toepassen) Dit kan bijvoorbeeld vereist zijn als u een geautomatiseerde toepassing of service hebt die een specifiek bestand moet kunnen openen om de inhoud te kunnen verwerken. Als u de beveiliging voor een bestandstype blokkeert, dan kunnen gebruikers de RMS-toepassing voor delen niet gebruiken om een bestand te beveiligen welke dat bestandstype heeft. Wanneer dit wordt geprobeerd, wordt een bericht weergegeven dat de beheerder beveiliging heeft voorkomen en dat de actie moet worden geannuleerd om het bestand te beveiligen.

Maak de volgende registerbewerkingen om de RMS-toepassing voor delen algemene beveiliging toe te laten passen op alle bestanden die standaard algemene beveiliging zouden krijgen:

1.  **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\RMSSharingApp\FileProtection**: maak een nieuwe sleutel met de naam *.

    Deze instelling geeft bestanden aan met elke bestandsnaamextensie.

2.  Maak in de toegevoegde sleutel HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\RMSSharingApp\FileProtection\\\* een nieuwe tekenreekswaarde (REG_SZ) met de naam **Encryption** en de gegevenswaarde **Pfile**.

    Met deze instelling past de RMS-toepassing voor delen algemene beveiliging toe.

Deze twee instellingen zorgen ervoor dat de RMS-toepassing voor delen algemene beveiliging toepast op alle bestanden die een bestandsnaamextensie hebben. Als dit het doel is, is er geen verdere configuratie vereist. U kunt echter ook uitzonderingen definiëren voor specifieke bestandstypen zodat deze nog steeds systeemeigen worden beveiligd. Hiervoor moet u drie aanvullende registerwijzigingen aanbrengen voor elk bestandstype:

1.  **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\RMSSharingApp\FileProtection**: voeg een nieuwe sleutel toe met de naam van de bestandsnaamextensie (zonder de voorafgaande punt).

    Maak bijvoorbeeld voor bestanden met de bestandsnaamextensie .docx een sleutel met de naam **DOCX**.

2.  Maak in de toegevoegde bestandstypesleutel (bijvoorbeeld **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\RMSSharingApp\FileProtection\DOCX**) een nieuwe DWORD-waarde met de naam **AllowPFILEEncryption** en de waarde **0**.

3.  Maak in de toegevoegde bestandstypesleutel (bijvoorbeeld **HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\RMSSharingApp\FileProtection\DOCX**) een nieuwe tekenreekswaarde met de naam **Encryption** en de waarde **Native**.

Als gevolg van deze instellingen worden alle bestanden algemeen beveiligd, behalve bestanden die een .docx-bestandsnaamextensie hebben, welke systeemeigen zijn beveiligd door de RMS-toepassing voor delen.

Herhaal deze drie stappen voor andere bestandstypen die u wilt definiëren als uitzonderingen omdat ze systeemeigen beveiliging ondersteunen en u deze niet algemeen wilt beveiligen met de RMS-toepassing voor delen.

U kunt vergelijkbare registerwijzigingen maken voor andere scenario's door de waarde te wijzigen van de tekenreeks **Encryption**, die ondersteuning biedt voor de volgende waarden:

-   **Pfile**: algemene beveiliging

-   **Native**: systeemeigen beveiliging

-   **Off**: beveiliging blokkeren

## Zie ook
[Gebruikershandleiding voor de Rights Management-toepassing voor delen](sharing-app-user-guide.md)




<!--HONumber=Jul16_HO3-->


