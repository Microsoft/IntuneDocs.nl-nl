---
title: 'Scenario: een Office-bestand delen met gebruikers in een andere organisatie | Azure RMS'
description: In dit scenario en de ondersteunende gebruikersdocumentatie wordt gebruikgemaakt van Azure Rights Management zodat gebruikers veilig een Office-bestand kunnen verzenden naar personen in een andere organisatie.
author: cabailey
manager: mbaldwin
ms.date: 08/25/2016
ms.topic: get-started-article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: c10a4d7b-f57a-4a43-b66e-477777be59cc
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 81426cf43f31625c6e83d443fa925f6426eb89da
ms.openlocfilehash: 26e81330c58057aac9629690f1d4fe85e56a64f8


---

# Scenario: een Office-bestand delen met gebruikers in een andere organisatie

>*Van toepassing op: Azure Rights Management, Office 365*

In dit scenario en de ondersteunende gebruikersdocumentatie wordt gebruikgemaakt van Azure Rights Management zodat gebruikers veilig een Office-bestand kunnen verzenden naar personen in een andere organisatie. Het Office-bestand kan bijvoorbeeld een Word-document, Excel-spreadsheet of PowerPoint-presentatie zijn met de prijslijstgegevens voor een partner, een lijst met producten voor een wederverkoper of een lijst met leveringstijdlijnen voor potentiële klanten. Wanneer gebruikers de instructies volgen, wordt het bestand dat is bijgevoegd aan het e-mailbericht beveiligd door Azure Rights Management.

Dit scenario is van toepassing op de volgende omstandigheden:

-   De werknemer moet via e-mail en in de vorm van een Office-documentbijlage informatie verzenden naar een ontvanger buiten de organisatie.

-   Het document bevat informatie die niet openbaar is, maar niet uitsluitend bedoeld is voor intern gebruik.

-   De ontvangers hoeven deze informatie niet verder met anderen te delen, af te drukken of als onderdeel van hun eigen documentatie te gebruiken. Als dat niet het geval is, kunt u de gebruikersinstructies zo wijzigen dat niet de machtigingen voor alleen-weergeven moeten worden geselecteerd, maar een andere optie waarbij de ontvanger wijzigingen kan aanbrengen in de bijlage.

-   De werknemer wil mogelijk weten wanneer dit document wordt geopend door de externe gebruiker.

## Instructies voor de implementatie
![Beheerdersinstructies voor de snelle implementatie van Azure RMS](../media/AzRMS_AdminBanner.png)

Zorg ervoor dat aan de volgende vereisten is voldaan voordat u doorgaat met de gebruikersdocumentatie.

## Vereisten voor dit scenario
De gebruikersinstructies voor dit scenario gelden alleen als aan de volgende voorwaarden is voldaan:

|Vereiste|Als u meer informatie wilt|
|---------------|--------------------------------|
|U hebt voor Office 365 of Azure Active Directory accounts en groepen voorbereid|[Voorbereiden voor Azure Rights Management](https://technet.microsoft.com/library/jj585029.aspx)|
|Azure Rights Management is geactiveerd|[Azure Rights Management activeren](https://technet.microsoft.com/library/jj658941.aspx)|
|De Rights Management-toepassing voor delen is geïmplementeerd op computers van gebruikers waarop Windows wordt uitgevoerd|[Automatische implementatie voor de Microsoft Rights Management-toepassing voor delen](https://technet.microsoft.com/library/dn339003%28v=ws.10%29.aspx)|
|Gebruikers beschikken over Outlook van Office 2013|Als gebruikers over Office 2010 beschikken, vervangt u de schermafbeelding met een gelijksoortige versie zodat de afbeelding overeenkomt met wat de gebruikers te zien krijgen.|
|Uw Azure RMS-abonnement omvat ook documenttracking|Als documenttracking en het intrekken van toegang niet onder uw Azure RMS-abonnement vallen, kunnen gebruikers niet alle stappen in de gebruikersinstructies uitvoeren. In dat geval schaft u een abonnement aan dat deze functies ondersteunt of u wijzigt de gebruikersinstructies en verwijdert de stappen die gebruikmaken van deze functies.<br /><br />De ondersteuning door uw abonnement controleren: [Vergelijking van RMS-aanbiedingen (Rights Management Services)](https://technet.microsoft.com/dn858608)|

## Instructies voor de gebruikersdocumentatie
Kopieer en plak aan de hand van de volgende sjabloon de gebruikersinstructies in een bericht voor de eindgebruikers en breng de volgende wijzigingen aan zodat de instructies van toepassing zijn op uw omgeving:

1.  Vervang *&lt;naam van het Office-documenttype&gt;* met het documenttype dat uw gebruikers verzenden. Gebruik termen die specifiek en gebruikelijk zijn in hun werkprocessen, zoals 'prijslijst', 'leveringstijden' en 'offertevoorstel' in plaats van 'Word-document' en 'Excel-spreadsheet'. Als u specifieke termen gebruikt, is de kans groter dat ze de instructies volgen als ze met deze documenten werken.

2.  Vervang *&lt;contactgegevens&gt;* met instructies voor de gebruikers om contact op te nemen met de helpdesk, zoals een websitekoppeling, e-mailadres of telefoonnummer.

3.  **Aanvullende wijzigingen die u misschien wilt aanbrengen:**

    -   In stap 2 wordt **Viewer: alleen weergeven** voorgesteld voor de machtigingen. Hierdoor wordt het bijgevoegde document (maar niet het oorspronkelijke document) voor de ontvangers alleen-lezen. Als deze beperking niet van toepassing is op uw bedrijfsbehoeften, wijzigt u deze optie in een andere machtiging, zoals **Revisor: weergeven en bewerken**.

    -   In stap 3 wordt **Mij toestaan direct de toegang tot deze documenten in te trekken** voorgesteld zodat er geen vertraging optreedt als de gebruikers het document later intrekken. Als u deze optie instelt, moet de ontvanger echter altijd over een internetverbinding beschikken om de bijlage te openen. Voor deze stap moet u ook over een abonnement beschikken dat ondersteuning biedt voor documenttracking en het intrekken van de toegang. Verwijder deze stap als deze niet van toepassing is op uw gebruikers.

    -   In stap 4 wordt de optie **Stuur mij een e-mail wanneer iemand dit document probeert te openen** voorgesteld. Als gebruikers hun documenten bijhouden met de portal voor documenttracking, vindt u een kennisgeving via e-mail misschien niet nodig en verwijdert u deze stap.

    -   In de stappen is het instellen van een vervaldatum niet opgenomen. Als de informatie niet meer mag worden gebruikt na een bepaalde datum, voegt u nog een stap toe om een geschikte vervaldatum in te stellen. Bijvoorbeeld 90 dagen na het verzenden van het e-mailbericht.

    > [!NOTE]
    > Zie [Dialoogvensteropties voor de Rights Management-toepassing voor delen](https://technet.microsoft.com/library/dn574738.aspx) voor meer informatie over elk van de opties die gebruikers kunnen selecteren

4.  Breng eventueel andere gewenste wijzigingen aan in deze instructies en verzend de tekst naar deze gebruikers.

In de voorbeelddocumentatie wordt getoond hoe deze instructies, na uw aanpassingen, voor de gebruikers kunnen zijn weergegeven.

![Gebruikersdocumentatiesjabloon voor de snelle implementatie van Azure RMS](../media/AzRMS_UsersBanner.png)

### Het delen van een &lt;naam van het Office-documenttype&gt;

1.  Maak uw e-mailbericht: geef het e-mailadres of de e-mailadressen op, typ uw bericht en voeg het/de *&lt;naam van het Office-documenttype&gt;* toe aan het e-mailbericht. Klik vervolgens op het tabblad **BERICHT** in de groep **RMS** op **Beveiligd delen** en klik vervolgens nogmaals op **Beveiligd delen**:

    ![Schermafbeelding voor het delen van een Office-document via Outlook](../media/AzRMSUserInstructions_ShareProtectedRibbon2013.png)

2.  Selecteer in het dialoogvenster **Beveiligd delen** de optie **Viewer: alleen weergeven**:

    ![dialoogvenster Beveiligd delen - Viewer - Alleen weergeven](../media/AzRMS_SharedProtected_ViewerOnly.PNG)

3.  Selecteer **Mij toestaan direct de toegang tot deze documenten in te trekken**:

    ![dialoogvenster Beveiligd delen - direct de toegang intrekken](../media/AzRMS_SharedProtected_InstantRevoke.PNG)

4.  Selecteer **Stuur mij een e-mail wanneer iemand dit document probeert te openen**:

    ![dialoogvenster Beveiligd delen - stuur mij een e-mail](../media/AzRMS_SharedProtected_EmailMe.PNG)

5.  Klik op **Nu verzenden**.

Wanneer personen op de regel **Aan**, **CC** of **BCC** dit e-mailbericht ontvangen, zien ze een bericht met instructies voor het lezen van het/de bijgevoegde *&lt;naam van het Office-documenttype&gt;*. Het document kan op veel apparaten worden gelezen, zoals iPads, iPhones, Android-tablets en -telefoons, Mac-computers en Windows-computers.

Houd met de [portal voor documenttracking](https://track.azurerms.com/) bij of en wanneer zij het/de bijgevoegde &lt;naam van het Office-documenttype&gt; openen. U kunt eventueel telefonisch een opvolgingsgesprek voeren met deze personen, kort nadat u hebt gezien dat ze de/het &lt;naam van het Office-documenttype&gt; hebben geopend.

**Hebt u hulp nodig?**

-   Voor aanvullende informatie:

    -   [Een bestand beveiligen dat u per e-mail deelt](https://technet.microsoft.com/library/dn574735%28v=ws.10%29.aspx)

    -   [Uw documenten bijhouden en de toegang hiertoe intrekken](https://technet.microsoft.com/library/dn986611.aspx)

-   Neem contact op met de helpdesk:

    -   *&lt;contactgegevens&gt;*

### Voorbeeld van aangepast gebruikersdocumentatie
![Voorbeeld van gebruikersdocumentatie voor de snelle implementatie van Azure RMS](../media/AzRMS_ExampleBanner.png)

#### Een prijslijst delen met uw klant

1.  Maak uw e-mailbericht: geef het e-mailadres of de e-mailadressen van uw klant op, typ uw bericht en voeg de laatste prijslijst toe aan het e-mailbericht. Klik vervolgens op het tabblad **BERICHT** in de groep **RMS** op **Beveiligd delen** en klik vervolgens nogmaals op **Beveiligd delen**:

    ![Schermafbeelding voor het delen van een Office-document via Outlook](../media/AzRMSUserInstructions_ShareProtectedRibbon2013.png)

2.  Selecteer in het dialoogvenster **Beveiligd delen** de optie **Viewer: alleen weergeven**:

    ![dialoogvenster Beveiligd delen - Viewer - Alleen weergeven](../media/AzRMS_SharedProtected_ViewerOnly.PNG)

3.  Selecteer **Mij toestaan direct de toegang tot deze documenten in te trekken**:

    ![dialoogvenster Beveiligd delen - direct de toegang intrekken](../media/AzRMS_SharedProtected_InstantRevoke.PNG)

4.  Selecteer **Stuur mij een e-mail wanneer iemand dit document probeert te openen**:

    ![dialoogvenster Beveiligd delen - stuur mij een e-mail](../media/AzRMS_SharedProtected_EmailMe.PNG)

5.  Klik op **Nu verzenden**.

Wanneer personen op de regel **Aan**, **CC** of **BCC** dit e-mailbericht ontvangen, zien ze een bericht met instructies voor het lezen van de bijgevoegde prijslijst. Het document kan op veel apparaten worden gelezen, zoals iPads, iPhones, Android-tablets en -telefoons, Mac-computers en Windows-computers.

Houd met de [portal voor documenttracking](https://track.azurerms.com/) bij of en wanneer deze personen de bijgevoegde prijslijst openen. U kunt eventueel telefonisch een opvolgingsgesprek voeren met deze personen, kort nadat u hebt gezien dat ze de prijslijst hebben geopend.

**Hebt u hulp nodig?**

-   Voor aanvullende informatie:

    -   [Een bestand beveiligen dat u per e-mail deelt](https://technet.microsoft.com/library/dn574735%28v=ws.10%29.aspx)

    -   [Uw documenten bijhouden en de toegang hiertoe intrekken](https://technet.microsoft.com/library/dn986611.aspx)

-   Neem contact op met de helpdesk:

    -   E-mailadres: helpdesk@vanarsdelltd.com




<!--HONumber=Aug16_HO4-->


