---
title: Scenario - Werkmappen voor permanente beveiliging configureren | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 05/20/2016
ms.topic: get-started-article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 1f189345-a69e-4bf5-8a45-eb0fe5bb542b
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 332e102cb27854314b93a71bfeae82a95c9a7812
ms.openlocfilehash: 35ad445e229eac3feeca5522a41b9e3b25fd1180


---

# Scenario - Werkmappen voor permanente beveiliging configureren

*Van toepassing op: Azure Rights Management, Office 365*

In dit scenario en de ondersteunende gebruikersdocumentatie wordt gebruik gemaakt van Azure Rights Management om permanente beveiliging toe te passen op Office-documenten in [Werkmappen](https://technet.microsoft.com/library/dn265974.aspx). Werkmappen gebruikt een functieservice voor bestandsservers met Windows Server waarmee gebruikers consistent toegang hebben tot de werkbestanden op hun pc's en apparaten. Hoewel Werkmappen bestanden beveiligt met een eigen versleuteling, gaat deze beveiliging verloren als de bestanden buiten de Werkmappen-omgeving worden verplaatst. Gebruikers kopiëren de gesynchroniseerde bestanden bijvoorbeeld naar een locatie die niet wordt beheerd door uw IT-afdeling of de bestanden worden per e-mail verzonden naar anderen.

De extra beveiliging die Azure Rights Management biedt, helpt onbedoeld gegevensverlies te voorkomen door te voorkomen dat de bestanden worden weergegeven door mensen buiten uw organisatie. U kunt dit doen met een van de ingebouwde standaardrechtenbeleidssjablonen. Voordat u dit scenario implementeert, moet u echter nagaan of gebruikers deze bestanden daadwerkelijk moeten delen met mensen buiten de organisatie. Wanneer een gebruiker bijvoorbeeld heeft gewerkt aan een conceptprijslijst, verzendt hij de definitieve versie naar zijn klant in een andere organisatie. Wanneer u de standaard Rights Management-sjabloon voor Werkmappen gebruikt, kan die klant in de andere organisatie het per e-mail verzonden document niet lezen. U kunt hier rekening mee houden door een aangepaste sjabloon te maken waarmee gebruikers een nieuw rechtenbeleid kunnen toepassen op het bestand, dat de oorspronkelijke beperking voor alle werknemers vervangt door de mensen die ze in het e-mailbericht opgeven.

> [!NOTE]
> Wanneer u de aangepaste sjabloon gebruikt die wordt beschreven in dit scenario, biedt de extra beveiliging die u met Azure Rights Management toepast veel voordelen, ondanks het feit dat gebruikers bestanden opzettelijk kunnen delen met mensen die u niet in de sjabloon hebt gedefinieerd. Deze extra beveiliging kan onbedoeld gegevensverlies voorkomen als de inhoud buiten de Werkmappen-grens wordt verplaatst, omdat de inhoud beveiligd blijft tegen onbevoegde gebruikers, ongeacht of de inhoud wordt verzonden of niet. Bijvoorbeeld: een gebruiker verliest een apparaat waarop Werkmappen wordt gebruikt, of het apparaat wordt gestolen, of de inhoud die naar en van dit apparaat wordt gesynchroniseerd, wordt via een onbeveiligde infrastructuur overgedragen.
> 
> Als een gebruiker de inhoud deelt met iemand in een andere organisatie en dat doet met de functionaliteit voor Beveiligd delen van de Rights Management-toepassing voor delen, vervangt die gebruiker de oorspronkelijke beveiliging door zijn eigen beveiligingsbeleid. Hierdoor is de inhoud nog steeds beveiligd tegen onbevoegde toegang en hebben alleen de personen die de gebruiker opgeeft, toegang tot de inhoud.

U kunt deze permanente beveiliging toepassen op alle Office-documenten in Werkmappen van gebruikers of alleen op bestanden die gevoelige of bedrijfskritische gegevens bevatten.

De instructies zijn van toepassing op de volgende omstandigheden:

-   De Werkmap-bestanden die u wilt beveiligen met permanente beveiliging zijn Office-bestanden. Deze bestanden kunnen systeemeigen worden beveiligd met Azure Right Management. De bestandsnaamextensie wordt niet gewijzigd en er is geen andere workflow nodig om ze te openen.

-   U wilt de permanente beveiliging toepassen op alle Office-bestanden in Werkmappen van gebruikers, of op bepaalde bestanden die zijn geïdentificeerd met File Classification Infrastructure van Bestandsserverbronbeheer in Windows Server.

-   Voor bestanden die moeten worden gedeeld met mensen die niet zijn opgegeven in de rechtenbeleidssjabloon (bijvoorbeeld gebruikers in een andere organisatie), moeten gebruikers een nieuw rechtenbeleid toepassen ter vervanging van de oorspronkelijke rechtenbeleidsbeveiliging.

## Instructies voor de implementatie
![Beheerdersinstructies voor de snelle implementatie van Azure RMS](../media/AzRMS_AdminBanner.png)

Zorg ervoor dat aan de volgende vereisten is voldaan en voer vervolgens de instructies voor de ondersteunende procedures uit voordat u doorgaat met de gebruikersdocumentatie.

## Vereisten voor dit scenario
De instructies voor dit scenario gelden alleen als aan de volgende voorwaarden is voldaan:

|Vereiste|Als u meer informatie nodig hebt|
|---------------|--------------------------------|
|Azure Rights Management is geactiveerd|[Azure Rights Management activeren](https://technet.microsoft.com/library/jj658941.aspx)|
|U hebt de lokale Active Directory-gebruikersaccounts gesynchroniseerd met Azure Active Directory of Office 365, met inbegrip van de bijbehorende e-mailadressen. Dit is verplicht voor alle gebruikers die gebruikmaken van werkmappen.|[Voorbereiden voor Azure Rights Management](https://technet.microsoft.com/library/jj585029.aspx)|
|Een van de volgende:<br /><br />- Een standaardsjabloon gebruiken voor alle gebruikers die niet toestaat dat gebruikers een nieuw rechtenbeleid toepassen: u hebt de standaardsjabloon **&lt;organisatienaam&gt; - vertrouwelijk** niet gearchiveerd<br /><br />- Een aangepaste sjabloon gebruiken waarmee gebruikers een nieuw rechtenbeleid kunnen toepassen: voer de volgende instructies uit om een aangepaste sjabloon te maken|[Aangepaste sjablonen configureren voor Azure Rights Management](https://technet.microsoft.com/library/dn642472.aspx)|
|De Rights Management-connector is geïnstalleerd, gemachtigd voor de Windows Server-computer en geconfigureerd voor de **FCI Server**-rol.|[De Azure Rights Management-connector implementeren](https://technet.microsoft.com/library/dn375964.aspx)|
|De Rights Management-toepassing voor delen is geïmplementeerd op computers van gebruikers waarop Windows wordt uitgevoerd|[Automatische implementatie voor de Microsoft Rights Management-toepassing voor delen](https://technet.microsoft.com/library/dn339003%28v=ws.10%29.aspx)|

### De aangepaste rechtenbeleidssjabloon configureren zodat gebruikers Work Folders-bestanden kunnen delen buiten de organisatie

1.  Meld u aan bij de klassieke Azure-portal en navigeer naar de Azure Rights Management-sjablonen.

2.  Kopieer de sjabloon **&lt;organisatienaam&gt; - vertrouwelijk** en geef een naam en beschrijving op voor dit Werkmappen-scenario. We raden het volgende aan:

    -   Naam: **Inhoud beveiligd met Werkmappen**

    -   Beschrijving: **Deze inhoud wordt beveiligd met Werkmappen en is alleen toegankelijk voor werknemers van het bedrijf. Als u deze inhoud wilt delen met mensen buiten de organisatie, voegt u het document als bijlage toe aan een e-mailbericht en gebruikt u de functie Beveiligd delen.**

3.  Op de pagina **RECHTEN**:

    -   Wijzig de bestaande rechten van **Aangepast** in **Mede-eigenaar**.

4.  Op de pagina **CONFIGUREREN**:

    -   Zorg ervoor dat de **STATUS** is ingesteld op **PUBLICEREN**

    -   Voor de **naam en beschrijving** verwijdert u de vermeldingen voor de talen die u niet gebruikt. Voor de talen die u wel wilt gebruiken, werkt u de **NAAM** en **BESCHRIJVING** bij zodat deze overeenkomen met de naam en beschrijving die u voor deze sjabloon hebt opgegeven in de gebruikte taal.

5.  Sla de sjabloon op.

### Werkmappen configureren om permanente beveiliging toe te passen op een Office-bestand

1.  Implementeer Werkmappen voor uw gebruikers, zodat lokaal opgeslagen bestanden worden gesynchroniseerd met een bestandsservermap , ook wel aangeduid als een *synchronisatieshare*. De synchronisatieshare op de bestandsserver mag zich niet bevinden op dezelfde server waarop de Rights Management-connector wordt uitgevoerd.

    De functieservice Werkmappen in Serverbeheer vereist deze oplossing voor de functie bestands- en opslagservices. Op de bestandsserver moet minimaal Windows Server 2012 R2 worden uitgevoerd, en deze bestandsserver kan lokaal zijn of deel uitmaken van een virtuele machine in Azure. Zie voor meer informatie over Werkmappen [Overzicht van Werkmappen](https://technet.microsoft.com/library/dn265974.aspx).

    Zie [Werkmappen implementeren](https://technet.microsoft.com/library/dn528861.aspx) voor implementatie-instructies. Zorg ervoor dat u de ingebouwde versleuteling selecteert (de optie **Werkmappen versleutelen**), die wordt toegepast naast Azure Rights Management-versleuteling. Daarnaast:

    -   Wanneer u het SSL-certificaat bindt op de synchronisatieserver (stap 4): gebruik de opdracht netsh (in plaats van de IIS-beheerconsole) om het certificaat te binden aan de HTTPS-interface van de standaardwebsite .

    -   Voorkomen dat gebruikers te maken krijgen met de Werkmappen-setup-fout **Er is een probleem met het toepassen van het beveiligingsbeleid** en de vereiste dat ze een lokale beheerder moeten zijn op hun computers in het domein: gebruik de cmdlet [Set-SyncShare](https://technet.microsoft.com/library/dn296649%28v=wps.630%29.aspx) met de parameter PasswordAutolockExcludeDomain en geef de domeinnamen op waarbinnen deze computers zich bevinden (bijvoorbeeld contoso.com).

2.  De configuratie voor de Rights Management-connector voltooien:

    1.  Maak met Bestandsserverbronbeheer een bestandsbeheertaak waarin de synchronisatieshare-map wordt geïdentificeerd als het bereik.

    2.  Kies voor de actie **RMS-versleuteling** en selecteer een sjabloon:

        -   Als u geen aangepaste sjabloon hebt gemaakt omdat u niet wilt dat gebruikers bestanden met anderen kunnen delen buiten de organisatie, selecteert u de sjabloonnaam **&lt;organisatienaam&gt; - vertrouwelijk**. Bijvoorbeeld: **VanArsdel Ltd - vertrouwelijk**.

        -   Als u met de vorige instructies een aangepaste sjabloon hebt gemaakt, selecteert u deze sjabloon. Bijvoorbeeld **Inhoud beveiligd met Werkmappen**.

    3.  Geef een planning op waarin ruim tijd is voorzien om alle Office-bestanden te laten versleutelen door Azure Rights Management, en selecteer de optie **Continu uitvoeren op nieuwe bestanden**.

3.  Als u deze configuratie handmatig wilt testen, zorg er dan voor dat de map een paar Office-bestanden bevat, gebruik vervolgens de optie **Bestandsbeheertaak nu uitvoeren** en selecteer **Wachten totdat de taak is voltooid**.

    Wacht totdat het dialoogvenster **Bestandsbeheertaak wordt uitgevoerd** wordt gesloten en bekijk vervolgens de resultaten in het rapport dat automatisch wordt weergegeven. U ziet het aantal bestanden in de door u gekozen map in het veld **Bestanden**. Controleer of de bestanden in de door u gekozen map nu zijn beveiligd door Azure Rights Management. Open bijvoorbeeld een bestand en bevestig dat u de informatiebanner boven aan het document ziet met daarin de naam en beschrijving van de Rights Management-sjabloon.

4.  Als u had besloten bestanden selectief te beveiligen met de infrastructuur voor bestandsclassificatie, configureert u de classificatieregel en -planning en wijzigt u vervolgens de bestandsbeheertaak zodanig dat deze de classificatie-eigenschap bevat als een voorwaarde.

## Instructies voor de gebruikersdocumentatie
Als de bestanden die u met Azure Rights Management beveiligt niet hoeven te worden gedeeld met mensen buiten uw organisatie, hoeft u gebruikers wellicht alleen maar de instructies voor het gebruik van Werkmappen te geven. Wanneer gebruikers de met Azure Rights Management beveiligde bestanden en de standaardsjabloon openen, worden de bestanden zoals gewoonlijk in Office geopend, met als enige verschil dat gebruikers mogelijk wordt gevraagd zich te laten verifiëren. De gebruikers zien een informatiebalk boven aan het document, waarin ze worden geïnformeerd dat de inhoud eigendomsrechtelijke gegevens bevat, die uitsluitend bedoeld zijn voor interne gebruikers.

Als u de aangepaste sjabloon had geconfigureerd zoals beschreven voor dit scenario, krijgen de gebruikers de slabloonbeschrijving te zien in de informatiebalk: **Deze inhoud wordt beschermd met Werkmappen en is uitsluitend bedoeld voor medewerkers van het bedrijf. Als u deze inhoud wilt delen met mensen buiten de organisatie, voegt u het document als bijlage toe aan een e-mailbericht en gebruikt u de functie Beveiligd delen.**. Hoewel de beschrijving een overzicht biedt van de manier waarop het bestand kan worden gedeeld buiten de organisatie, hebben de gebruikers waarschijnlijk gedetailleerde instructies nodig om te weten hoe dit moet, vooral wanneer ze dit voor het eerst doen. Gebruik ter ondersteuning van dit vervolgscenario de beheerders- en eindgebruikersinstructies in [Scenario - Een Office-bestand delen met gebruikers in een andere organisatie](scenario-share-office-file-externally.md).

> [!TIP]
> Als u had besloten geen gebruik te maken van de aangepaste sjabloon in deze instructies omdat u niet wilt dat gebruikers deze bestanden kunnen delen buiten de organisatie zonder toezicht van IT, kunt u dit uw helpdesk laten weten zodat als de reden voor het delen gerechtvaardigd is, hier rekening mee kan worden gehouden via het mechanisme dat het meest geschikt is voor uw bedrijf. Bijvoorbeeld iemand die [supergebruiker](https://technet.microsoft.com/library/mt147272.aspx) is, kan op de inhoud een nieuwe sjabloon toepassen die de aanvragende gebruiker de rechten Volledig beheer verleent, zodat deze gebruiker de functie Beveiligd delen kan gebruiken.
> 
> Als u na een bepaalde periode ontdekt dat er veel van dergelijke aanvragen zijn, kunt u besluiten voor dit scenario uw eigen aangepaste sjabloon te maken. In die sjabloon wordt alleen aan specifieke gebruikers (zoals managers of de helpdesk) de optie Mede-eigenaar verleend, terwijl standaardgebruikers de optie Mede-auteur of ieder ander, door u gepast geacht [recht](https://technet.microsoft.com/library/mt169423.aspx) krijgen.




<!--HONumber=Jul16_HO3-->


