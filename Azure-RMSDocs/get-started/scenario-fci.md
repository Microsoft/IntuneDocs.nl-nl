---
title: 'Scenario: bestanden op een bestandsshare van de server beveiligen | Azure RMS'
description: In dit scenario en de ondersteunende gebruikersdocumentatie wordt gebruikgemaakt van Azure Rights Management om alle bestanden op een bestandsshare van de server bulksgewijs te beveiligen zodat uitsluitend werknemers van uw organisatie deze kunnen openen. Dit geldt ook voor het geval waarin de bestanden worden gekopieerd en opgeslagen in een opslag die niet onder het beheer van uw IT-afdeling valt of wanneer deze per e-mail naar anderen worden verzonden.
author: cabailey
manager: mbaldwin
ms.date: 08/24/2016
ms.topic: get-started-article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 283c7db3-5730-439e-a215-40a1088ed506
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 024a29d7c7db2e4c0578a95c93e22f8e7a5b173e
ms.openlocfilehash: adc8ebd3063d8ac4b3710c517f0177fc25a16845


---

# Scenario: bestanden op een bestandsshare van de server beveiligen

>*Van toepassing op: Azure Rights Management, Office 365*

In dit scenario en de ondersteunende gebruikersdocumentatie wordt gebruikgemaakt van Azure Rights Management om alle bestanden op een bestandsshare van de server bulksgewijs te beveiligen zodat uitsluitend werknemers van uw organisatie deze kunnen openen. Dit geldt ook voor het geval waarin de bestanden worden gekopieerd en opgeslagen in een opslag die niet onder het beheer van uw IT-afdeling valt of wanneer deze per e-mail naar anderen worden verzonden.

In deze instructies wordt gebruikgemaakt van een van de standaardsjablonen die de toegang beperkt tot alle werknemers die over alle gebruiksrechten beschikken. U kunt desgewenst de toegang en gebruiksrechten nog verder beperken door een aangepaste sjabloon te configureren in plaats van de standaardsjabloon te gebruiken.

De instructies zijn van toepassing op de volgende omstandigheden:

-   U moet alle bestandstypen en niet alleen de Office-bestanden beveiligen. Bestanden die niet standaard door Azure RMS kunnen worden beveiligd, worden algemeen beveiligd.

-   Alle bestanden in het opgegeven pad (inclusief de submappen) worden beveiligd.

-   Voor alle bestanden wordt de beveiliging volgens een schema opnieuw toegepast zodat wijzigingen in de sjablonen voor het rechtenbeleid worden toegepast op de beveiligde bestanden.

## Instructies voor de implementatie
![Beheerdersinstructies voor de snelle implementatie van Azure RMS](../media/AzRMS_AdminBanner.png)

Zorg ervoor dat aan de volgende vereisten is voldaan en voer vervolgens de instructies voor de ondersteunende procedures uit voordat u doorgaat met de gebruikersdocumentatie.

## Vereisten voor dit scenario
De instructies voor dit scenario gelden alleen als aan de volgende voorwaarden is voldaan:

|Vereiste|Als u meer informatie nodig hebt|
|---------------|--------------------------------|
|Azure Rights Management is geactiveerd|[Azure Rights Management activeren](https://technet.microsoft.com/library/jj658941.aspx)|
|U hebt de lokale Active Directory-gebruikersaccounts gesynchroniseerd met Azure Active Directory of Office 365, met inbegrip van de bijbehorende e-mailadressen. Dit is vereist voor alle gebruikers die mogelijk toegang moeten hebben tot de bestanden nadat deze door FCI en Azure Rights Management zijn beveiligd.|[Voorbereiden voor Azure Rights Management](https://technet.microsoft.com/library/jj585029.aspx)|
|Een van de volgende:<br /><br />- Met een standaardsjabloon voor alle gebruikers: u hebt de standaardsjabloon, &lt;organisatienaam&gt;: vertrouwelijk, niet gearchiveerd<br /><br />- Met een aangepaste sjabloon voor specifieke gebruikers: u hebt deze aangepaste sjabloon gemaakt en gepubliceerd|[Aangepaste sjablonen configureren voor Azure Rights Management](https://technet.microsoft.com/library/dn642472.aspx)|
|De Rights Management-toepassing voor delen is geïmplementeerd op computers van gebruikers waarop Windows wordt uitgevoerd|[Automatische implementatie voor de Microsoft Rights Management-toepassing voor delen](https://technet.microsoft.com/library/dn339003%28v=ws.10%29.aspx)|
|U hebt het RMS-beveiligingshulpprogramma gedownload en de vereiste onderdelen voor Azure RMS geconfigureerd|Voor instructies voor het downloaden van het hulpprogramma en de vereisten: [Cmdlets van RMS-beveiliging](https://msdn.microsoft.com/library/mt433195.aspx)<br /><br />Aanvullende vereisten voor Azure RMS, zoals de hoofdaccount voor de service, configureren: [about_RMSProtection_AzureRMS](https://msdn.microsoft.com/library/mt433202.aspx)|

### Een bestandsserver configureren voor het beveiligen van alle bestanden met Azure RMS en File Server Resource Manager met File Classification Infrastructure

1.  Start een Windows PowerShell-sessie. U hoeft deze sessie niet als beheerder uit te voeren.

2.  Verifieer uzelf bij Azure RMS:

    ```
    Set-RMSServerAuthentication
    ```
    Als u hierom wordt gevraagd, geeft u de waarden op voor de hoofdaccount voor de service die u hebt gemaakt als een vereiste voor de cmdlets van de RMS-beveiliging.

3.  Voer de volgende opdracht uit om vast te stellen welke sjabloon-id wordt gebruikt om de bestanden te beveiligen:

    ```
    Get-RMSTemplate
    ```
    Als u de standaardsjabloon wilt gebruiken die de toegang beperkt tot alle werknemers die over alle gebruiksrechten beschikken, zoekt u de sjabloonnaam **&lt;organisatienaam&gt;: vertrouwelijk**. Bijvoorbeeld: **VanArsdel Ltd: vertrouwelijk**.

4.  Voer de stapsgewijze instructies in [RMS-beveiliging met Windows Server File Classification Infrastructure (FCI)](https://technet.microsoft.com/library/mt601315%28v=ws.10%29.aspx) uit.

    Deze instructies bevatten een Windows PowerShell-script die u in File Server Resource Manager uitvoert als een aangepast uitvoerbaar bestand. In de instructies wordt ook uitgelegd hoe u kunt controleren of de bestanden worden beveiligd door Azure Rights Management.

## Instructies voor de gebruikersdocumentatie
Als u uitsluitend Office-bestanden beveiligt, hoeft u de gebruikers mogelijk geen instructies te geven voor de beveiligde bestanden. Wanneer geautoriseerde gebruikers deze documenten openen, worden deze zoals gebruikelijk in Office geopend. Het enige verschil is dat de gebruikers mogelijk worden gevraagd om zich te verifiëren en dat waarschijnlijk een informatiebalk boven aan het document wordt weergegeven waarin wordt vermeld dat het document is beveiligd.

Als de beveiligde bestanden de bestandsextensie **.ppdf** hebben of als ze een beveiligd tekstbestand of afbeeldingsbestand zijn (ze hebben bijvoorbeeld de bestandsextensie **.ptxt** of **.pjpg**), zijn deze bestanden nu alleen-lezen en kunnen ze niet worden bewerkt. Gebruikers kunnen deze bestanden bekijken met de viewer voor RMS-toepassingen voor delen die automatisch voor deze bestandstypen wordt geladen. Deze bestanden worden standaard beveiligd door Azure RMS en alle beleidsinstellingen van de door u opgegeven sjabloon worden toegepast, met uitzondering van de gebruiksrechten omdat het bestand alleen-lezen is. Tenzij u zeker weet dat u deze bestandstypen wilt beveiligen, is het onwaarschijnlijk dat u gebruikersinstructies nodig hebt voor dit scenario. Informeer echter uw helpdesk dat zij mogelijk aan gebruikers moeten uitleggen waarom deze bestanden niet kunnen worden bewerkt.

Als de beveiligde bestanden de bestandsextensie **.pfile** hebben, kunnen gebruikers deze bestanden bekijken. De bestanden moeten echter met hun oorspronkelijke bestandsnaam (verwijder de bestandsextensie .pfile) worden opgeslagen als gebruikers het bestand willen bewerken en de wijzigingen willen opslaan. Deze bestanden worden door Azure RMS algemeen beveiligd en voor de bestanden kunnen niet de gebruiksrechten worden afgedwongen van de sjabloon die u hebt toegepast. Dit houdt in dat het bestand niet meer wordt beveiligd als dit wordt opgeslagen met een nieuwe naam. Voor dit scenario moeten instructies voor gebruikers worden gebruikt.

Kopieer en plak aan de hand van de volgende sjabloon de instructies voor de eindgebruikers, zodat ze weten hoe ze algemeen beveiligde bestanden kunnen bewerken. Breng de volgende wijzigingen aan zodat de instructies van toepassing zijn op uw omgeving:

-   Vervang *&lt;bestandstype&gt;* en *&lt;bestandsshare op de server&gt;* met het bestandstype dat algemeen wordt beveiligd en de naam van de bestandsshare van de server.

-   Vervang *&lt;organisatienaam&gt;* met de naam van uw organisatie zoals deze wordt weergegeven op uw standaardsjablonen van Azure Rights Management.

-   Vervang *&lt;organisatienaam&gt;* met de naam van uw organisatie.

-   Vervang *&lt;instructies voor het opslaan van het bestand en het verwijderen van de bestandsextensie .pfile&gt;* met toepassingsspecifieke instructies voor dit bestandstype.

-   Vervang contactgegevens met instructies voor de gebruikers om contact op te nemen met de helpdesk, zoals een websitekoppeling, e-mailadres of telefoonnummer.

-   Breng eventuele aanvullende wijzigingen aan in deze instructies en verzend deze naar de gebruikers.

In de voorbeelddocumentatie wordt getoond hoe deze instructies, na uw aanpassingen, voor de gebruikers kunnen zijn weergegeven.

![Gebruikersdocumentatiesjabloon voor de snelle implementatie van Azure RMS](../media/AzRMS_UsersBanner.png)

### Het &lt;bestandstype&gt; bewerken in de &lt;bestandsshare op de server&gt;

1.  Dubbelklik op het bestand om dit te openen. Mogelijk moet u uw referenties invoeren.

2.  Er wordt een dialoogvenster voor **beveiligde bestanden** weergegeven in de Microsoft Rights Management-toepassing voor delen. Dit geeft aan dat u de machtigingen voor **&lt;organisatienaam&gt;: vertrouwelijk** moet naleven. Dit houdt in dat u dit document niet mag delen met anderen als ze niet voor &lt;organisatienaam&gt; werken.

3.  Klik op **Openen**.

4.  Als u het bestand wilt bewerken, slaat u het bestand eerst op en verwijdert u de bestandsextensie .pfile:

    -   &lt;Instructies voor het opslaan van het bestand en het verwijderen van de bestandsextensie .pfile&gt;

5.  U kunt het bestand nu zoals gebruikelijk bewerken en opslaan.

Het bestand wordt regelmatig opnieuw beveiligd, zodat de bestandsextensie .pfile weer wordt toegevoegd en u deze stappen weer moet herhalen.

**Hebt u hulp nodig?**

-   Voor aanvullende informatie:

    -   [Weergeven en gebruiken van bestanden die zijn beveiligd](https://technet.microsoft.com/library/dn574741%28v=ws.10%29)

-   Neem contact op met de helpdesk:

    -   *&lt;contactgegevens&gt;*

### Voorbeeld van aangepast gebruikersdocumentatie
![Voorbeeld van gebruikersdocumentatie voor de snelle implementatie van Azure RMS](../media/AzRMS_ExampleBanner.png)

#### CAD-tekeningen in de ProjectNextGen-share bewerken

1.  Dubbelklik op het bestand om dit te openen. Mogelijk moet u uw referenties invoeren.

2.  Er wordt een dialoogvenster voor **beveiligde bestanden** weergegeven in de Microsoft Rights Management-toepassing voor delen. Dit geeft aan dat u de machtigingen voor **VanArsdel Ltd: vertrouwelijk** moet naleven. Dit houdt in dat u dit document niet mag delen met andere personen als ze niet voor VanArsdel Ltd werken.

3.  Klik op **Openen**.

4.  Als u het bestand wilt bewerken, slaat u het bestand eerst op en verwijdert u de bestandsextensie .pfile:

    -   **Bestand** &gt; **Opslaan als**

    -   Verwijder **.pfile** aan het einde van de bestandsnaam en klik op **OK**.

5.  U kunt het bestand nu zoals gebruikelijk bewerken en opslaan.

Het bestand wordt regelmatig opnieuw beveiligd, zodat de bestandsextensie .pfile weer wordt toegevoegd en u deze stappen weer moet herhalen.

**Hebt u hulp nodig?**

-   Voor aanvullende informatie:

    -   [Weergeven en gebruiken van bestanden die zijn beveiligd](https://technet.microsoft.com/library/dn574741%28v=ws.10%29)

-   Neem contact op met de helpdesk: helpdesk@vanarsdelltd.com




<!--HONumber=Aug16_HO4-->


