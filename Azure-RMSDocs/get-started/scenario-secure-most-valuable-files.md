---
# required metadata

title: Scenario: uw waardevolste bestanden (enkele) beveiligen | Azure RMS
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 95f1844a-612c-4e67-bbe6-4b6b92295221

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Scenario: uw waardevolste bestanden (enkele) beveiligen

*Van toepassing op: Azure Rights Management, Office 365*

In dit scenario en de ondersteunende gebruikersdocumentatie wordt gebruikgemaakt van Azure Rights Management om handmatig een aangepaste beveiliging toe te passen op een aantal bestanden, die u hebt aangegeven als uw waardevolste bestanden zijn. Deze bestanden krijgen daarom het hoogste niveau van beveiliging tegen onbevoegde toegang. Dit zijn meestal bestanden waartoe slechts enkele personen toegang zouden moeten hebben. Bijvoorbeeld receptinstructies voor het belangrijkste voedingsmiddel van uw bedrijf of overnameplannen die niet openbaar mogen worden gemaakt vóór een bepaalde datum.

De instructies zijn van toepassing op de volgende omstandigheden:

-   U wilt een klein aantal bestanden beveiligen.

-   De bestanden hebben een van de Office-bestandsindelingen die ondersteuning bieden voor Rights Management. Als de bestanden andere bestandsindelingen hebben (bijvoorbeeld CAD-bestanden), zorgt u ervoor dat deze indelingen ondersteuning bieden voor Azure RMS en dat u toepassingen implementeert die standaard Azure RMS ondersteunen. Zie [Hoe toepassingen ondersteuning bieden voor Azure Rights Management](https://technet.microsoft.com/library/jj585004.aspx) voor meer informatie.

-   De bestanden bevatten uiterst vertrouwelijke, gevoelige informatie die toegankelijk moet zijn voor slechts enkele personen.

-   Het feit dat een internetverbinding vereist is voor de verificatie elke keer dat een bestand wordt geopend is voor de gebruikers geen bezwaar, omdat de bestanden zo beter zijn beveiligd.

-   Deze gebruikers hoeven deze informatie niet met anderen te delen, maar ze kunnen de gegevens wijzigen en de wijzigingen opslaan.

-   De beheerder moet kunnen bijhouden wie de bestanden opent en wanneer, en de toegang zo nodig kunnen intrekken.

## Instructies voor de implementatie
![Beheerdersinstructies voor de snelle implementatie van Azure RMS](../media/AzRMS_AdminBanner.png)

Zorg ervoor dat aan de volgende vereisten is voldaan en voer vervolgens de instructies voor de ondersteunende procedures uit voordat u doorgaat met de gebruikersdocumentatie.

## Vereisten voor dit scenario
Voor dit scenario moet aanwezig zijn:

|Vereiste|Als u meer informatie wilt|
|---------------|--------------------------------|
|U hebt voor Office 365 of Azure Active Directory accounts en groepen voorbereid:<br /><br />Een e-mailgroep met de naam **Bevoegde toegang** die de kleine groep mensen bevat die toegang moet hebben tot deze zeer vertrouwelijke documenten<br /><br />Een e-mailgroep met de naam ** IT-nalevingsmanagers** die personen bevat die verantwoordelijk zijn voor eDiscovery, bewaking en controle<br /><br />Een e-mailgroep met de naam **RMS-beheerders**, en alle beheerders die Azure RMS configureren zijn lid van deze groep|[Voorbereiden voor Azure Rights Management](https://technet.microsoft.com/library/jj585029.aspx)|
|Azure Rights Management is geactiveerd|[Azure Rights Management activeren](https://technet.microsoft.com/library/jj658941.aspx)|
|U hebt een aangepaste sjabloon geconfigureerd, zoals hieronder wordt beschreven|[Aangepaste sjablonen configureren voor Azure Rights Management](https://technet.microsoft.com/library/dn642472.aspx)|
|De Rights Management-toepassing voor delen is op uw Windows-computer geïmplementeerd, zodat u deze lokale bestanden kunt beveiligen, zoals in de volgende sectie wordt beschreven|[De Rights Management-toepassing voor delen downloaden en installeren](https://technet.microsoft.com/library/dn574734%28v=ws.10%29.aspx)|
|Gemachtigde gebruikers beschikken minimaal over Office 2013|Als gebruikers Office 2010 hebben, moeten ze ook de Rights Management-toepassing voor delen installeren.|
|Uw Azure RMS-abonnement omvat ook documenttracking|Als documenttracking en het intrekken van toegang niet onder uw Azure RMS-abonnement vallen, kunt u geen gebruik maken van de site voor documenttracking om te bekijken wie deze documenten openen en om de toegang zo nodig in te trekken. In dat geval schaft u een abonnement aan dat documenttracking ondersteunt of u accepteert deze beperking. U kunt ook overwegen om de functies voor [gebruiksregistratie](https://technet.microsoft.com/library/dn529121.aspx) van Azure RMS te gebruiken. Hiermee krijgt u een overzicht van de personen die elk bestand openen en wanneer deze bestanden worden geopend, zodat u mogelijk verdacht gedrag kunt detecteren.<br /><br />De ondersteuning door uw abonnement controleren: [Vergelijking van RMS-aanbiedingen (Rights Management Services)](https://technet.microsoft.com/dn858608)|

### De aangepaste sjabloon configureren

1.  In de klassieke Azure-portal: maak een nieuwe aangepaste sjabloon voor Azure Rights Management die de volgende waarden en instellingen bevat:

    -   Naam: **Bevoegde toegang**

    -   Rechten: ken aan de e-mailgroep **Bevoegde toegang** de rechten voor **Mede-auteur** toe

    -   Bereik: selecteer de e-mailgroep **Bevoegde toegang**, de e-mailgroep **IT-nalevingsmanagers** en de e-mailgroep **RMS-beheerders**.

    -   Offline toegang: **inhoud kan alleen worden verkregen via een internetverbinding**

2.  Publiceer de nieuwe sjabloon.

### De lokale bestanden beveiligen

1.  Ga in Bestandenverkenner naar de eerste map die de bestanden bevat die moeten worden beveiligd:

    -   Als u alle bestanden in de map wilt beveiligen, selecteert u de map.

    -   Als u alleen bepaalde bestanden in de map wilt beveiligen, selecteert u de bestanden die u wilt beveiligen.

2.  Klik met de rechtermuisknop op **Beveiligen met RMS** en selecteer vervolgens **Lokale bestanden beveiligen**.

3.  Selecteer **Bevoegde toegang**.

4.  Mogelijk moet u uw referenties invoeren. Wacht tot de bestanden zijn beveiligd en klik vervolgens op **Sluiten** wanneer de pagina met de melding **De bestanden zijn beveiligd** wordt weergegeven.

5.  Als u nog bestanden in andere mappen moet beveiligen, herhaalt u stap 1 tot en met 4 voor elke map.

Zie [Een bestand beveiligen op een apparaat (lokaal bestand beveiligen) met de Rights Management-toepassing voor delen](https://technet.microsoft.com/library/dn574733%28v=ws.10%29.aspx) voor meer informatie over het beveiligen van lokale bestanden

> [!TIP] Als het aantal bestanden dat moet worden beveiligd te groot is voor deze handmatige verwerking, kunt u overwegen om het [RMS-beveiligingshulpprogramma](https://www.microsoft.com/en-us/download/details.aspx?id=47256) te gebruiken om de bestanden bulksgewijs te beveiligen met de sjabloon.

### De toegang tot de bestanden bewaken en deze zo nodig intrekken

1.  Klik in Bestandenverkenner met de rechtermuisknop op het beveiligde bestand, selecteer **Beveiligen met RMS** en selecteer vervolgens **Gebruik bijhouden**.

2.  Meld u aan voor toegang tot de site voor documenttracking, als u hierom wordt gevraagd.

3.  Bekijk wie het bestand en de andere door u beveiligde bestanden hebben geopend. Let daarbij met name op de mislukte pogingen als deze wijzen op verdacht gedrag. U kunt zo nodig de toegang tot elk bestand intrekken.

## Instructies voor de gebruikersdocumentatie
Er zijn in dit scenario geen specifieke instructies voor de gebruikers, omdat deze bestanden geen speciale actie van de gebruikers vereisen. De bestanden zijn door u beveiligd en worden door u bewaakt. Misschien moet u echter deze gebruikers en uw ondersteuningskanalen informeren over de bestanden die zijn beveiligd en hoe dit het gebruik van de documenten kan beperken. Als geautoriseerde gebruikers bijvoorbeeld niet over een internetverbinding beschikken, kunnen ze het bestand niet openen.

Kopieer en plak aan de hand van de volgende sjabloon de aankondiging in een bericht voor de eindgebruikers en breng de volgende wijzigingen aan:

1.  Geef de werkelijke namen van de bestanden op of gebruik een duidelijke verwijzing die wordt begrepen door de gemachtigde gebruikers.

2.  Vervang *&lt;contactgegevens&gt;* met instructies voor deze gebruikers om contact op te nemen met de helpdesk of IT-afdeling met een ondersteuningskanaal voor geëscaleerde problemen die overeenkomt met het belang van deze documenten. Geef bijvoorbeeld een 24-uurs telefoonnummer op voor telefonische ondersteuning bij ernstige problemen.

3.  Breng eventuele aanvullende wijzigingen aan in de aankondiging en verzend deze naar de gebruikers.

In de voorbeelddocumentatie wordt getoond hoe de aankondiging, na uw aanpassingen, voor de gebruikers kan zijn weergegeven.

![Gebruikersdocumentatiesjabloon voor de snelle implementatie van Azure RMS](../media/AzRMS_UsersBanner.png)

### IT-aankondiging: strikt geheime documenten van &lt;organisatienaam&gt; beveiligen
Op de volgende bestanden wordt nu een zeer hoog niveau van beveiliging toegepast, zodat alleen een &lt;beperkte groep gebruikers&gt; deze bestanden kan openen en hierin wijzigingen kan aanbrengen. Om de bestanden te beschermen tegen onbevoegde toegang, wordt u telkens wanneer u deze bestanden wilt openen automatisch door uw toepassing gevraagd om u te verifiëren. U moet daarom nu over een internetverbinding beschikken om de bestanden te openen en u kunt om uw referenties worden gevraagd:

-   &lt;strikt geheim document, type of locatie 1&gt;

-   &lt;strikt geheim document, type of locatie 2&gt;

-   &lt;strikt geheim document, type of locatie 3&gt;

**Hebt u hulp nodig?**

-   Als u geen toegang krijgt tot deze bestanden of als u verdachte wijzigingen in de bestanden opmerkt: &lt;actie- en contactgegevens&gt;.

#### Voorbeeld van aangepast gebruikersdocumentatie
![Voorbeeld van gebruikersdocumentatie voor de snelle implementatie van Azure RMS](../media/AzRMS_ExampleBanner.png)

##### IT-aankondiging: strikt geheime documenten van VanArsdel beveiligen
Op de volgende bestanden wordt nu een zeer hoog niveau van beveiliging toegepast, zodat alleen de personen op de regel Aan van dit e-mailbericht deze bestanden kunnen openen en hierin wijzigingen kunnen aanbrengen. Om de bestanden te beschermen tegen onbevoegde toegang, wordt u telkens wanneer u deze bestanden wilt openen automatisch door uw toepassing gevraagd om u te verifiëren. U moet daarom nu over een internetverbinding beschikken om de bestanden te openen en u kunt om uw referenties worden gevraagd:

-   Ontwerpspecificaties voor codenaam 'Mercurius'

-   Ontwerpspecificaties voor codenaam 'Jupiter'

-   Ontwerpspecificaties voor codenaam 'Saturnus'

-   Ontwerpspecificaties voor codenaam 'Neptunus'

**Hebt u hulp nodig?**

-   Als u geen toegang krijgt tot deze bestanden of als u verdachte wijzigingen in de bestanden opmerkt, belt u het nummer voor 24-uurs ondersteuning. Dit nummer is door de IT-afdeling in een beveiligd e-mailbericht naar u verzonden.



<!--HONumber=May16_HO2-->


