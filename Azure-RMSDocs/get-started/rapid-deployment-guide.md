---
# required metadata

title: Snelle implementatiehandleiding voor Azure Rights Management | Azure RMS
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: c994d616-cff6-4930-9228-a7f7d198a160

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Snelle implementatiehandleiding voor Azure Rights Management

*Van toepassing op: Azure Rights Management, Office 365*

Gebruik deze handleiding naast de configuratie-informatie in de sectie **Implementeren en gebruiken** om Azure Rights Management (Azure RMS) sneller te implementeren en te gebruiken door in een lijst de specifieke scenario's te selecteren die u wilt implementeren.

Deze scenario's bevatten zowel instructies voor de beheerder als begeleidende documentatie voor de eindgebruiker. Voordat u de documentatie (instructies of aankondigingen) aan uw eindgebruikers geeft, moet u deze eerst aanpassen aan uw bedrijfsvereisten en de bestaande werkstromen. Een voorbeeldset met instructies of een aankondiging toont u hoe de uiteindelijke documentatie voor de eindgebruiker eruit komt te zien.

Elk scenario bevat indien nodig een lijst met vereisten met koppelingen naar meer informatie, zodat u deze oplossingen onafhankelijk en in een willekeurige volgorde kunt implementeren.

De scenario's die worden weergeven, zijn voorbeelden van de populairste scenario's. Omdat Azure RMS in een groot aantal scenario's, zowel binnen het bedrijf als tussen bedrijven, kan worden gebruikt om gegevens te beveiligen, kunt u dit model ook gebruiken om uw eigen scenario's te definiëren en ze te implementeren voor uw omgeving en uw gebruikers. Door u te focussen op specifieke scenario's, wordt de Azure RMS-implementatie beter afgestemd op uw bedrijfsdoelen. Uit onze ervaring blijkt dat gebruikers de scenariospecifieke instructies nauwkeuriger en systematischer opvolgen dan algemene richtlijnen, zoals 'beveilig gevoelige documenten'.

Voordat u deze oplossingen uitrolt, wilt de eindgebruikers mogelijk eerst een algemene aankondiging sturen om ze te laten weten dat er enkele wijzigingen zullen worden doorgevoerd met betrekking tot het beveiligen van bedrijfsgegevens en dat ze zelf mogelijk ook bepaalde zaken moeten wijzigen. Na de volgende tabel vindt u een voorbeeld van een dergelijke mededeling.

> [!NOTE] Als u vragen of opmerkingen over deze handleiding hebt, kunt u het feedbackmechanismse op deze pagina gebruiken of een e-mail sturen naar [AskIPTeam@Microsoft.com](mailto:%20askipteam@microsoft.com?subject=Rapid%20Deployment%20Guide%20feedback).

## Scenario's voor Azure RMS
Kies de scenario's die het meest overeenkomen met uw bedrijfsdoelen en pas ze indien nodig aan om Azure RMS sneller te implementeren en specifieke bedrijfsproblemen aan te pakken.



**Veilig een Office-bestand naar gebruikers in een andere organisatie mailen en het gebruik van het bestand bijhouden (samenwerking tussen bedrijven)**

Voorbeelden:

- Een prijslijst, roadmap of releaseplannen naar een klant verzenden

- Een werkorder of marketingspecificatie naar een leverancier verzenden

- Een aanbesteding of offerteaanvraag (RFQ; Request For Quotation) naar een partner verzenden

Zie [Scenario: een Office-bestand delen met gebruikers in een andere organisatie](scenario-share-office-file-externally.md)

**Ervoor zorgen dat u de controle behoudt over documenten die zijn opgeslagen in een SharePoint-bibliotheek**

Voorbeelden:

- Spreadsheets en rapporten van afdelingen

- Verschillende teams die samenwerken aan ontwerpdocumenten of andere items

Zie [Scenario: de controle over documenten behouden die zijn opgeslagen in SharePoint](scenario-sharepoint.md)

**Leidinggevenden kunnen veilig vertrouwelijke informatie via e-mail uitwisselen**

Voorbeelden:

- Overnameplannen delen

- Juridische problemen bespreken of verspreiden

- Informatie over mogelijke ontslagen of andere gevoelige onderwerpen

Zie: [Scenario: leidinggevenden wisselen veilig vertrouwelijke informatie uit](scenario-executives-email.md)

**Automatisch alle bestanden op een bestandsserver beveiligen**

Voorbeelden:

- CAD-documenten die intern moeten worden bewaard om het verlies van intellectueel eigendom te voorkomen

- Plannen en datums voor marketingacties die geheim moeten blijven om de concurrentie een stap voor te blijven

Zie: [Scenario: bestanden op een bestandsshare van de server beveiligen](scenario-fci.md)

**U meest vertrouwelijk documenten met een grote impact voor het bedrijf streng beveiligen**

Voorbeelden:

- Informatie over een uniek recept of unieke formule van uw bedrijf

- Zeer vertrouwelijk informatie over plannen voor een overname of fusie

- Gegevens over de exploratie van natuurlijke bronnen

Zie: [Scenario: uw waardevolste bestanden &#40;enkele&#41; beveiligen](scenario-secure-most-valuable-files.md)

**Veilig bedrijfsvertrouwelijke e-mailberichten en bijlagen verzenden**

Voorbeelden:

- Visieverklaring van het bedrijf

- Organigrammen, reorganisatieplannen of promotieaankondigingen

- Informatie over het bedrijfsbeleid

Zie: [Scenario: een e-mailbericht met vertrouwelijke bedrijfsinformatie verzenden](scenario-company-confidential-email.md)

**Permanente beveiliging voor Office-bestanden in werkmappen toepassen**

Voorbeelden:

- Lokaal bewerkte Word-documenten voor een bedrijfsvertrouwelijk project.

- Lokaal gemaakte spreadsheets die gevoelige gegevens of HBI-gegevens bevatten.

- Lokaal opgeslagen PowerPoint-presentaties met informatie over het onderhanden werk, waarvan u niet wilt dat ze worden gelekt of per ongeluk worden gedeeld met mensen buiten de organisatie totdat de presentaties definitief zijn.

Zie [Scenario: werkmappen voor permanente beveiliging configureren](scenario-work-folders.md)




## Aankondiging voor gebruikers voorafgaand aan de implementatie
U kunt het volgende voorbeeld van een communicatiebericht gebruiken om gebruikers te informeren dat er met de implementatie van Azure RMS enkele veranderingen zullen worden doorgevoerd. Kopieer en plak de volgende tekst die door iemand binnen de leiding van uw organisatie (bij voorkeur de CEO) via e-mail wordt verzonden naar alle gebruikers. Breng eventueel wijzigingen in de tekst aan om het bericht relevanter te maken voor de gebruikers en uw organisatie.

![Voorbeeld van een gebruikersdocumentatiebanner voor een snelle implementatie van Azure RMS](../media/AzRMS_ExampleBanner.png)

### Wijzigingen die we doorvoeren om onze gegevens beveiligen
Wilt u de toegang blokkeren tot het document dat u per ongeluk naar partners hebt verzonden? Hebt u zich wel eens afgevraagd of er een manier is om te controleren of uw klanten het laatste productnieuws hebben gelezen dat u hebt verzonden? Hebt u behoefte aan een manier om vertrouwelijke productinformatie te delen zonder dat u zich zorgen hoeft te maken dat de informatie wordt doorgestuurd naar mensen waarvoor de informatie niet is bestemd?

Binnenkort is dit allemaal mogelijk. De IT-afdeling werkt namelijk aan de implementatie van Microsoft Azure Rights Management (Azure RMS) als oplossing voor de beveiliging van bedrijfsgegevens. In de meeste gevallen verandert er voor u niets en wordt de benodigde beveiliging automatisch door de oplossing toegepast. In bepaalde gevallen is het echter mogelijk dat er iets anders van u wordt verwacht. In dat geval ontvangt u informatie en instructies van de IT-afdeling en kunt u met vragen of problemen terecht bij de helpdesk.

U moet bijvoorbeeld de site voor documenttracking gebruiken om de documenten die u deelt, bij te houden (en indien nodig in te trekken):

![Schermafbeeldingen van Azure RMS-documenttracking](../media/AzRMS_Tutorial_5_Screenshots.png)

Bekijk deze video van twee minuten om een indruk te krijgen van hoe dit werkt: [Documenttracking en -intrekking met Azure RMS](https://channel9.msdn.com/Series/Information-Protection/Azure-RMS-Document-Tracking-and-Revocation).

Een van de waardevolste assets van deze organisatie zijn de gegevens: de gegevens die we dagelijks genereren, opslaan en gebruiken. De gegevens zorgen ervoor dat we onze concurrenten een stap voor blijven en dragen bij aan ons succes. Het is daarom belangrijk dat we de controle over onze gegevens behouden en ervoor zorgen dat de gegevens niet toegankelijk zijn voor onbevoegden.

De oplossingen die we implementeren, dragen bij aan de beveiliging van onze waardevolle gegevens en bieden u de mogelijkheid de controle over die gegevens te behouden. Hartelijk dank voor uw medewerking bij het implementeren van deze wijzigingen.



<!--HONumber=May16_HO2-->


