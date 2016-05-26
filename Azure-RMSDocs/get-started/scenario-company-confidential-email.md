---
# required metadata

title: Scenario: een e-mailbericht met vertrouwelijke bedrijfsinformatie verzenden | Azure RMS
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 950799e9-2289-48c7-b95a-f54a8ead520a

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Scenario: een e-mailbericht met vertrouwelijke bedrijfsinformatie verzenden

*Van toepassing op: Azure Rights Management, Office 365*

In dit scenario en de ondersteunende gebruikersdocumentatie wordt gebruikgemaakt van Azure Rights Management zodat gebruikers in de organisatie veilig e-mailberichten kunnen verzenden die buiten de organisatie niet kunnen worden gelezen. Bijvoorbeeld als iemand het e-mailbericht doorstuurt naar een persoon in een andere organisatie of naar een persoonlijk e-mailaccount. De e-mailberichten en eventuele bijlagen worden beveiligd door Azure Rights Management en een sjabloon die door de gebruikers wordt geselecteerd in de e-mailclient.

De eenvoudigste manier om dit scenario te realiseren, is door een van de ingebouwde standaardsjablonen te gebruiken die automatisch de toegang beperken tot alle gebruikers in uw organisatie. Maar als het nodig is, kunt u een striktere beperking opleggen door een aangepaste sjabloon te maken die bijvoorbeeld de toegang beperkt tot een subset van gebruikers. U kunt ook andere beperkingen, zoals alleen-lezen, een vervaldatum of het uitschakelen van de knop Doorsturen in de e-mailclient opleggen.

> [!IMPORTANT]
> Hoewel u de knop **Doorsturen** kunt verwijderen uit een aangepaste sjabloon die u configureert en hiermee de knop Doorsturen in de e-mailclient wordt uitgeschakeld, wordt in dit scenario met deze configuratie niet voorkomen dat gebruikers het e-mailbericht met een andere geautoriseerde gebruiker delen. De ontvanger kan het e-mailbericht (en eventuele bijlagen) opslaan en vervolgens de gegevens via andere methoden delen.
> 
> Bob verzendt bijvoorbeeld een e-mailbericht naar Els met een aangepaste sjabloon die de aangepaste rechten Bestand opslaan en Inhoud bewerken toepast op de groep Marketing en waarin het recht Doorsturen niet is opgenomen. Hoewel Els het e-mailbericht niet naar anderen kan doorsturen, kan ze het e-mailbericht en eventuele bijlagen op een USB-station of in een bestandsshare op de server opslaan. Elk lid van de groep Marketing kan het bericht en de bijlagen vervolgens lezen en bewerken als ze toegang tot deze bestanden hebben. Gebruikers die niet tot de groep Marketing behoren, kunnen de inhoud niet openen.

De instructies zijn van toepassing op de volgende omstandigheden:

-   Een gebruiker in de organisatie wil informatie delen met anderen binnen de organisatie, maar deze informatie mag niet met personen buiten de organisatie worden gedeeld.

-   De informatie die wordt gedeeld kan zich in het e-mailbericht of de bijlage bevinden.

-   Gebruikers moeten de sjabloon handmatig selecteren vanuit hun e-mailclient.

## Instructies voor de implementatie
![Beheerdersinstructies voor de snelle implementatie van Azure RMS](../media/AzRMS_AdminBanner.png)

Zorg ervoor dat aan de volgende vereisten is voldaan voordat u doorgaat met de gebruikersdocumentatie.

## Vereisten voor dit scenario
De instructies voor dit scenario gelden alleen als aan de volgende voorwaarden is voldaan:

|Vereiste|Als u meer informatie wilt|
|---------------|--------------------------------|
|U hebt voor Office 365 of Azure Active Directory accounts en groepen voorbereid|[Voorbereiden voor Azure Rights Management](https://technet.microsoft.com/library/jj585029.aspx)|
|Uw Azure Rights Management-tenantsleutel wordt beheerd door Microsoft. U maakt geen gebruik van BYOK|[Uw Azure Rights Management-tenantsleutel plannen en implementeren](https://technet.microsoft.com/library/dn440580.aspx)|
|Azure Rights Management is geactiveerd|[Azure Rights Management activeren](https://technet.microsoft.com/library/jj658941.aspx)|
|Een van de volgende:<br /><br />Exchange Online is ingeschakeld voor Azure Rights Management<br /><br />De RMS-connector is geïnstalleerd en geconfigureerd voor Exchange on-premises|Voor Exchange Online: zie de sectie **Exchange Online: IRM-configuratie** in [Toepassingen configureren voor Azure Rights Management](https://technet.microsoft.com/library/jj585031.aspx).<br /><br />Voor Exchange on-premises: [De Azure Rights Management-connector implementeren](https://technet.microsoft.com/library/dn375964.aspx)|
|U hebt de Azure Rights Management-standaardsjabloon **&lt;organisatie&gt;: vertrouwelijk** niet gearchiveerd. Of u hebt een aangepaste sjabloon voor dit doel geconfigureerd omdat u meer beperkende instellingen wilt toepassen of alleen een subset van gebruikers in de organisatie mogen de beveiligde e-mailberichten lezen.|[Aangepaste sjablonen configureren voor Azure Rights Management](https://technet.microsoft.com/library/dn642472.aspx)<br /><br />Tip: als u meer beperkende instellingen voor het gebruiksbeleid wilt toepassen voor alle gebruikers, kunt u beter een van de standaardsjablonen kopiëren en deze vervolgens bewerken dan een compleet nieuwe sjabloon te maken.<br /><br />Bijgewerkte sjablonen worden niet onmiddellijk vernieuwd voor de e-mailclients in dit scenario. Ga naar de sectie [Sjablonen vernieuwen voor gebruikers](https://technet.microsoft.com/library/dn642472.aspx) in het artikel over het configureren van sjablonen voor meer informatie.|
|Gebruikers die de beveiligde e-mail verzenden, beschikken over Outlook 2013 of Outlook 2016, of Outlook Web Access.<br /><br />Gebruikers die de e-mail ontvangen, beschikken over een e-mailclient die ondersteuning biedt voor Azure Rights Management.|U kunt Outlook 2010 gebruiken, maar u moet [de Rights Management-toepassing voor delen voor Windows installeren](https://technet.microsoft.com/library/dn339003.aspx) en de gebruikersinstructies overeenkomstig aanpassen.<br /><br />Zie de kolom **E-mail** in de tabel [Functionaliteit van clientapparaten](https://technet.microsoft.com/library/dn655136.aspx) in [Vereisten voor Azure Rights Management](https://technet.microsoft.com/library/dn655136.aspx) voor een lijst met e-mailclients die ondersteuning bieden voor Azure Rights Management|

## Instructies voor de gebruikersdocumentatie
Kopieer en plak aan de hand van de volgende sjabloon de gebruikersinstructies in een bericht voor de eindgebruikers en breng de volgende wijzigingen aan zodat de instructies van toepassing zijn op uw omgeving:

1.  Vervang alle exemplaren van *&lt;organisatienaam&gt;* met de naam van uw organisatie.

2.  Vervang alle exemplaren van *&lt;organisatienaam: vertrouwelijk&gt;* met de naam van uw standaardsjabloon of aangepaste sjabloon.

3.  Vervang de schermafbeeldingen zodat daarin de sjabloonnamen van uw organisatie worden weergeven.

4.  Vervang *&lt;contactgegevens&gt;* met instructies voor de gebruikers om contact op te nemen met de helpdesk, zoals een websitekoppeling, e-mailadres of telefoonnummer.

5.  **Aanvullende wijzigingen die u misschien wilt aanbrengen:**

    -   Als u het overzichtelijk wilt houden en het praktisch vindt om instructies te beperken tot één e-mailclient, verwijdert u de andere instructies.

    -   Als u een aangepaste sjabloon gebruikt in plaats van de voorgestelde standaardsjabloon, wijzigt u de tekst als volgt:

        -   Maak de titel specifieker.

        -   Geef de gebruikers of groepen op die in stap 1 moeten worden geselecteerd.

        -   Geef de naam op van de aangepaste sjabloon in stap 2.

        -   Voeg in de laatste alinea een uitleg toe over de beperkingen die van toepassing zijn op de ontvangers.

6.  Breng eventueel andere gewenste wijzigingen aan in deze instructies en verzend de tekst naar deze gebruikers.

7.  Omdat Rights Management door sommige clients niet wordt ondersteund, moet u mogelijk richtlijnen en aanbevelingen verstrekken aan de ontvangers van deze beveiligde e-mailberichten. Deze informatie wordt gebaseerd op de apparaten en e-mailtoepassingen die in uw organisatie worden gebruikt en op uw voorkeuren. Geef aan gebruikers van iOS bijvoorbeeld als aanbeveling dat ze beveiligde e-mailberichten lezen met Outlook voor iPad en iPhone in plaats van de systeemeigen e-mailclient voor iOS.

    Zie de kolom **E-mail** in de tabel [Functionaliteit van clientapparaten](https://technet.microsoft.com/library/dn655136.aspx) in [Requirements for Azure Rights Management](https://technet.microsoft.com/library/dn655136.aspx) (Vereisten voor Azure Rights Management) voor meer informatie over de e-mailclients.

In de voorbeelddocumentatie wordt getoond hoe deze instructies, na uw aanpassingen, voor de gebruikers kunnen zijn weergegeven.

![Gebruikersdocumentatiesjabloon voor de snelle implementatie van Azure RMS](../media/AzRMS_UsersBanner.png)

### E-mailberichten met vertrouwelijke bedrijfsinformatie verzenden via Outlook

1.  Maak in Outlook een nieuw e-mailbericht, voeg eventuele bijlagen toe die u wilt opnemen en selecteer vervolgens gebruikers of groepen van *&lt;organisatienaam&gt;*.

2.  Klik op het tabblad **OPTIES** op **Machtiging** en selecteer vervolgens **&lt;organisatienaam: vertrouwelijk&gt;**:

    ![Schermafbeelding voor E-mailberichten met vertrouwelijke bedrijfsinformatie verzenden via Outlook](../media/AzRMS_OutlookTemplate.PNG)

3.  Verzend het bericht.

### E-mailberichten met vertrouwelijke bedrijfsinformatie verzenden via Outlook Web App

1.  Maak in Outlook Web App een nieuw e-mailbericht, voeg eventuele bijlagen toe die u wilt opnemen en selecteer vervolgens *&lt;organisatienaam&gt;*-gebruikers of -groepen in het adresboek.

2.  Klik op **…** en op **Machtigingen instellen**, en selecteer vervolgens **&lt;organisatienaam: vertrouwelijk&gt;**:

    ![Schermafbeelding voor E-mailberichten met vertrouwelijke bedrijfsinformatie verzenden via Outlook Web App](../media/AzRMS_OWATemplate.png)

3.  Verzend het bericht.

Wanneer personen die op de regel **Aan**, **CC** of **BCC** worden vermeld dit e-mailbericht ontvangen, kunnen zij worden gevraagd om zich te verifiëren voordat ze het bericht kunnen lezen. Op deze manier wordt geverifieerd of ze een gebruiker zijn van *&lt;organisatienaam&gt;*. Andere keren worden de gebruikers hierom niet gevraagd omdat ze al zijn geverifieerd.

Personen naar wie u het e-mailbericht verzendt, kunnen dit doorsturen naar anderen, maar alleen gebruikers van *&lt;organisatienaam&gt;* kunnen het lezen. Als u een Office-document bijvoegt, krijgt dit dezelfde beveiliging, zelfs als de bijlage met een andere naam op een andere locatie wordt opgeslagen. Geverifieerde gebruikers kunnen echter inhoud uit het e-mailbericht of de bijlage kopiëren en plakken of inhoud hieruit afdrukken. Als u een meer beperkende beveiliging wilt toepassen om zulke acties te voorkomen, neemt u contact op met de helpdesk.

**Hebt u hulp nodig?**

-   Neem contact op met de helpdesk:

    -   *&lt;contactgegevens&gt;*

### Voorbeeld van aangepast gebruikersdocumentatie
![Voorbeeld van gebruikersdocumentatie voor de snelle implementatie van Azure RMS](../media/AzRMS_ExampleBanner.png)

#### E-mailberichten met vertrouwelijke bedrijfsinformatie verzenden via Outlook

1.  Maak in Outlook een nieuw e-mailbericht, voeg eventuele bijlagen toe die u wilt opnemen en selecteer vervolgens VanArsdel-gebruikers of -groepen in het adresboek.

2.  Klik op het tabblad **OPTIES** op **Machtiging** en selecteer vervolgens **VanArsdel Ltd: vertrouwelijk**:

    ![Schermafbeelding voor E-mailberichten met vertrouwelijke bedrijfsinformatie verzenden via Outlook](../media/AzRMS_OutlookTemplate.PNG)

3.  Verzend het bericht.

#### E-mailberichten met vertrouwelijke bedrijfsinformatie verzenden via Outlook Web App

1.  Maak in Outlook Web App een nieuw e-mailbericht, voeg eventuele bijlagen toe die u wilt opnemen en selecteer vervolgens VanArsdel-gebruikers of -groepen in het adresboek.

2.  Klik op **…** en op **Machtigingen instellen** en selecteer vervolgens **VanArsdel Ltd: vertrouwelijk**:

    ![Schermafbeelding voor E-mailberichten met vertrouwelijke bedrijfsinformatie verzenden via Outlook Web App](../media/AzRMS_OWATemplate.png)

3.  Verzend het bericht.

Wanneer personen die op de regel **Aan**, **CC** of **BCC** worden vermeld dit e-mailbericht ontvangen, kunnen zij gevraagd worden om zich te verifiëren voordat ze het bericht kunnen lezen. Op deze manier wordt geverifieerd of ze een gebruiker zijn van VanArsdel Ltd. Andere keren worden de gebruikers hierom niet gevraagd omdat ze al zijn geverifieerd.

Personen naar wie u het e-mailbericht verzendt, kunnen dit doorsturen naar anderen, maar alleen gebruikers van VanArsdel kunnen het lezen. Als u een Office-document bijvoegt, krijgt dit dezelfde beveiliging, zelfs als de bijlage met een andere naam op een andere locatie wordt opgeslagen. Geverifieerde gebruikers kunnen echter inhoud uit het e-mailbericht of de bijlage kopiëren en plakken of inhoud hieruit afdrukken. Als u een meer beperkende beveiliging wilt toepassen om zulke acties te voorkomen, neemt u contact op met de helpdesk.

**Hebt u hulp nodig?**

-   Neem contact op met de helpdesk:

    -   E-mailadres: helpdesk@vanarsdelltd.com



<!--HONumber=May16_HO2-->


