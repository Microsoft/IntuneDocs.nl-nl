---
# required metadata

title: Gebruikers helpen bij het beveiligen van bestanden door gebruik te maken van Azure Rights Management | Azure RMS
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 06/09/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 58f9a6ff-4121-4c8c-9865-1bb290604ad2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Gebruikers helpen bij het beveiligen van bestanden door gebruik te maken van Azure Rights Management

*Van toepassing op: Azure Rights Management, Office 365*

Nadat u Azure Rights Management (Azure RMS) hebt geïmplementeerd en geconfigureerd voor uw organisatie, kunt u gebruikers en beheerders en de helpdesk hulp en richtlijnen bieden:

-   **Informatie voor de eindgebruiker:**

    Laat gebruikers weten hoe en wanneer ze documenten en e-mails met gevoelige informatie moeten beveiligen. Indien mogelijk moet u deze informatie verstrekken voorafgaand aan hun huidige werkstromen, zodat ze aanvullende stappen aan een vertrouwd proces kunnen toevoegen en u geen volledig nieuw proces hoeft te introduceren. Informeer ze over de specifieke voordelen (en risico's) voor uw bedrijf en bied ze richtlijnen voor wanneer ze bestanden en e-mailberichten moeten beveiligen. Als u [aangepaste sjablonen](configure-custom-templates.md) hebt geconfigureerd en de naam en beschrijving van de sjablonen niet voldoende informatie bieden om de juiste sjabloon te selecteren, verstrekt u hier instructies voor.

    > [!TIP] Voorbeeldvideo's voor eindgebruikers:
    >
    > -   [Gebruikerservaring van Azure RMS](http://channel9.msdn.com/Series/Information-Protection/Azure-RMS-user-experience)
    > -   [Azure RMS-document bijhouden en intrekken](http://channel9.msdn.com/Series/Information-Protection/Azure-RMS-Document-Tracking-and-Revocation)

-   **Informatie voor beheerders:**

    Met bepaalde toepassingen wordt automatisch gegevensbeveiliging toegepast op basis van beleid en instellingen die door beheerders worden geconfigureerd. Voor deze toepassingen moet u mogelijk instructies verstrekken voor andere beheerders die deze toepassingen en services beheren. Zie [How applications support Azure Rights Management](../understand-explore/applications-support.md) (Hoe toepassingen ondersteuning bieden voor Azure Rights Management) en [Configuring applications for Azure Rights Management](configure-applications.md) (Toepassingen configureren voor Azure Rights Management) voor meer informatie.

-   **Informatie voor de helpdesk:**

    Een van de handigste hulpprogramma's voor de helpdesk is [RMS Analyzer](https://www.microsoft.com/en-us/download/details.aspx?id=46437). Helpdeskmedewerkers kunnen dit programma uitvoeren met de optie Azure RMS-beheerder en ze kunnen gebruikers vragen het programma uit te voeren met de optie Azure RMS-gebruiker. Met dit hulpprogramma kunt u niet alleen problemen identificeren, maar ook oplossen. Als het probleem niet kan worden opgelost, kunt u de problemen registreren in traceerlogboeken.

    Als er legitieme aanvragen worden ingediend om de volledige rechten toe te kennen voor het openen van beveiligde documenten, bijvoorbeeld een aanvraag van de juridische afdeling of een aanvraag van een manager nadat een werknemer de organisatie heeft verlaten, moet u ervoor zorgen dat de helpdesk over processen beschikt om dit aan te vragen met de Azure RMS-functie voor [supergebruikers](configure-super-users.md).

    Daarnaast volgen hier enkele typische problemen die gebruikers kunnen melden:

    -   **Hulp bij aanmelden:**

        Gebruikers worden mogelijk naar referenties gevraagd wanneer Azure RMS een gebruiker moet verifiëren en geen referenties kan gebruiken die zijn opgeslagen in de cache. De referenties bestaan uit het werk- of schoolaccount en het wachtwoord die aan de Office 365- of Azure Active Directory-tenant zijn gekoppeld. Er kan geen Microsoft-account (voorheen Microsoft Live ID) of een persoonlijk e-mailaccount worden gebruikt, aangezien dergelijke accounts niet door Azure RMS worden ondersteund. Verstrek gebruikers en helpdeskmedewerkers instructies over welk account moet worden gebruikt wanneer gebruikers om referenties wordt gevraagd wanneer ze deze toepassingen met Azure RMS gebruiken.

    -   **Problemen met het beveiligen of gebruiken van inhoud:**

        Zorg ervoor dat gebruikers over de juiste instructies beschikken voor de toepassingen die ze gebruiken en dat ze toepassingen en apparaten gebruiken die worden ondersteund door Azure RMS. Zie [Requirements for Azure Rights Management](../get-started/requirements-azure-rms.md) (Vereisten voor Azure Rights Management) voor meer informatie over de toepassingen en apparaten die worden ondersteund.

        Als er een fout wordt weergegeven wanneer gebruikers inhoud willen beveiligen of gebruiken, vraagt u ze [RMS Analyzer](https://www.microsoft.com/en-us/download/details.aspx?id=46437) uit te voeren als een Azure RMS-gebruiker.

        Als gebruikers melden dat ze beveiligde inhoud kunnen openen maar niet over de benodigde rechten beschikken, vraagt u ze [RMS Analyzer](https://www.microsoft.com/en-us/download/details.aspx?id=46437) uit te voeren als Azure RMS-gebruiker en de sjablonen te downloaden en weer te geven. Zodoende kunnen ze controleren of de sjablonen zijn gedownload en welke rechten de sjablonen bieden. Het probleem wordt mogelijk veroorzaakt doordat de gebruiker zich niet in de juiste groep bevindt die voor de sjabloon is geconfigureerd of dat de sjabloon opnieuw moet worden geconfigureerd voor de gebruiker.

Gebruik de volgende secties voor toepassingsspecifieke gegevens om gebruikers te helpen bij het beveiligen van gevoelige documenten en e-mails.

## Gegevensbeveiliging gebruiken met de Rights Management-toepassing voor delen
De Rights Management-toepassing voor delen (RMS) is vereist wanneer gebruikers met Office 2010 beveiligde inhoud willen beveiligen en gebruiken, maar wordt ook aanbevolen voor alle computers en mobiele apparaten die ondersteuning bieden voor Azure RMS.

De RMS-toepassing voor delen maakt het gebruikers niet alleen gemakkelijker om belangrijke documenten beveiligen, ze kunnen hiermee ook de documenten bijhouden die ze hebben beveiligd en indien nodig de toegang tot de documenten intrekken.

Zie de [Rights Management sharing application user guide](../rms-client/sharing-app-user-guide.md) (Gebruikershandleiding voor Rights Management-toepassing voor delen) voor instructies voor het gebruik van deze toepassing voor Windows-computers.

Zie [FAQ for Microsoft Rights Management Sharing Application for Mobile Platforms](http://technet.microsoft.com/dn451248) (Veelgestelde vragen over Microsoft Rights Management-toepassing voor delen voor mobiele platformen) voor informatie over mobiele apparaten.

> [!TIP] Zie [Users safely share attachments with mobile users](../understand-explore/what-admins-users-see.md#users-safely-share-attachments-with-mobile-users) voor een gedetailleerd voorbeeldscenario met screenshots.

## Gegevensbeveiliging gebruiken met behulp van Office 365, Office 2016 of Office 2013
Als u Azure RMS gebruikt en u de Rights Management-toepassing voor delen niet hebt geïnstalleerd, wordt de knop **Beveiligd delen** niet weergegeven op het lint of is **Op locatie beveiligen** niet beschikbaar in de Verkenner. Hiermee kunnen gebruikers eenvoudig bestanden beveiligen. Deze gebruikers moeten instructies volgend die vergelijkbaar zijn met deze.

> [!TIP]Als u toepassingsspecifieke Help-informatie of instructies wilt zoeken voor het gebruik van gegevensbeveiliging met deze toepassingen, zoekt u op **IRM** en de naam en versie van de toepassing.

#### Een document beveiligen in Word 2013

1.  Maak een nieuw document in Microsoft Word.

2.  Klik in het menu **Bestand** op **Info**, klik op **Document beveiligen**, klik op **Toegang beperken** en kies vervolgens een sjabloon om snel de juiste gebruiksrechten toe te passen, of selecteer **Toegang beperken** en selecteer zelf de gebruikersrechten.

    > [!NOTE] Als u Rights Management voor de eerste keer gebruikt, neemt u contact op met de [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)]-service en wordt u naar de referenties gevraagd om de Office IRM-client te configureren.

3.  Sla het document op.

Wanneer anderen het document openen, worden ze eerst geverifieerd. Als ze niet gemachtigd zijn om het document te openen, wordt het document niet geopend. Als ze gemachtigd zijn om het document te openen, wordt het geopend met de beperkte gebruiksrechten die voor de desbetreffende gebruiker zijn opgegeven. Als bijvoorbeeld het gebruiksrecht Alleen-weergeven is toegewezen, kan de gebruiker het document niet bewerken of opslaan, zelfs niet als het eerst wordt gekopieerd naar een andere locatie. De gebruiksrechten worden met een beperkingsbanner weergegeven boven aan het document. De banner bevat mogelijk de machtigingen die zijn toegepast op het bestand of bevat een koppeling om deze weer te geven.

#### Een e-mailbericht beveiligen met Outlook 2013 en Exchange Online

1.  Maak een nieuw e-mailbericht in Outlook dat is geadresseerd aan een ontvanger binnen uw organisatie.

2.  Klik op het tabblad **OPTIES** op **Machtigingen** en selecteer vervolgens een optie. Bijvoorbeeld: **Niet doorsturen**, **&lt;Bedrijfsnaam&gt;: vertrouwelijk** of **&lt;Bedrijfsnaam&gt;: alleen vertrouwelijke weergave**.

3.  Verzend het bericht.

Wanneer ontvangers een e-mailbericht ontvangen, worden ze op een vergelijkbare manier als bij het weergeven van een beveiligd document, eerst geverifieerd. Als ze zijn gemachtigd om het e-mailbericht weer te geven, wordt het bericht geopend met de beperkte gebruiksrechten die voor de desbetreffende gebruiker zijn opgegeven. Als u bijvoorbeeld **Niet doorsturen** hebt geselecteerd, is de knop Doorsturen niet beschikbaar op het lint.

#### Een e-mailbericht beveiligen met Outlook Web App

1.  Maak een nieuw e-mailbericht in Outlook Web App dat is geadresseerd aan een ontvanger binnen uw organisatie.

2.  Klik op **…**, klik op **Machtiging instellen** en selecteer vervolgens een optie. Bijvoorbeeld: **Niet doorsturen**, **Niet iedereen beantwoorden**, **&lt;Bedrijfsnaam&gt;: vertrouwelijk** of **&lt;Bedrijfsnaam&gt;: alleen vertrouwelijke weergave**.

3.  Verzend het bericht.

Wanneer ontvangers een e-mailbericht ontvangen, worden ze op een vergelijkbare manier als bij het weergeven van een beveiligd document, eerst geverifieerd. Als ze zijn gemachtigd om het e-mailbericht weer te geven, wordt het bericht geopend met de beperkte gebruiksrechten die voor de desbetreffende gebruiker zijn opgegeven. Als u bijvoorbeeld**Niet iedereen beantwoorden** hebt geselecteerd, is de optie **ALLEN BEANTWOORDEN** niet beschikbaar in het berichtvenster.




<!--HONumber=Jun16_HO2-->


