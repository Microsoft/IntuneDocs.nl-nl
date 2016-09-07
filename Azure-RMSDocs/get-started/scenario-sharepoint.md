---
title: 'Scenario: het beheer over documenten die zijn opgeslagen in SharePoint behouden | Azure RMS'
description: In dit scenario en de ondersteunende gebruikersdocumentatie wordt gebruikgemaakt van Azure Rights Management om Office-documenten die zijn opgeslagen in SharePoint onder uw beheer te houden met behulp van beveiligde bibliotheken.
author: cabailey
manager: mbaldwin
ms.date: 08/25/2016
ms.topic: get-started-article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 1b6244c7-5ab9-4881-bc8f-6fa960390d89
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 81426cf43f31625c6e83d443fa925f6426eb89da
ms.openlocfilehash: 048eafc41dcd03c708dca5befbef4e4b9e7113c4


---

# Scenario: het beheer over documenten die zijn opgeslagen in SharePoint behouden

>*Van toepassing op: Azure Rights Management, Office 365*

In dit scenario en de ondersteunende gebruikersdocumentatie wordt gebruikgemaakt van Azure Rights Management om Office-documenten die zijn opgeslagen in SharePoint onder uw beheer te houden met behulp van beveiligde bibliotheken. De documenten worden bijvoorbeeld automatisch beveiligd tegen het onbedoeld of bewust lekken van gegevens door gebruikers en u kunt de toegang tot de inhoud blokkeren, zelfs nadat dit is gedownload of gesynchroniseerd. De bestanden die u wilt beveiligen, worden misschien intern gebruikt door werknemers die samenwerken aan ontwerpdocumenten of -plannen, of aan andere producten. Wanneer u beveiligde bibliotheken voor SharePoint configureert, worden de daarin opgeslagen Office-bestanden beveiligd door Azure Rights Management.

De instructies zijn van toepassing op de volgende omstandigheden:

-   Werknemers delen informatie en werken samen met Office-documenten die zijn opgenomen in een SharePoint-bibliotheek.

-   Werknemers hoeven de machtigingen niet in te stellen of te wijzigen omdat een beheerder deze al instelt op bibliotheekniveau.

-   Werknemers hoeven deze documenten niet te delen met personen buiten uw organisatie.

## Instructies voor de implementatie
![Beheerdersinstructies voor de snelle implementatie van Azure RMS](../media/AzRMS_AdminBanner.png)

Zorg ervoor dat aan de volgende vereisten is voldaan en dat de ondersteunende procedures zijn voorbereid voordat u doorgaat met de gebruikersdocumentatie.

## Vereisten voor dit scenario
Voor dit scenario moet aan het volgende zijn voldaan:

|Vereiste|Als u meer informatie wilt|
|---------------|--------------------------------|
|U hebt voor Office 365 of Azure Active Directory accounts en groepen voorbereid|[Voorbereiden voor Azure Rights Management](https://technet.microsoft.com/library/jj585029.aspx)|
|Azure Rights Management is geactiveerd|[Azure Rights Management activeren](https://technet.microsoft.com/library/jj658941.aspx)|
|Als u SharePoint Server wilt gebruiken: de RMS-connector implementeren en deze configureren voor SharePoint|[De Azure Rights Management-connector implementeren](https://technet.microsoft.com/library/dn375964.aspx)|
|Machtigingen configureren voor de SharePoint-site die moet worden beveiligd|[Machtigingen beheren voor een lijst, bibliotheek, map, document of lijstitem](https://support.office.com/en-ca/article/Manage-permissions-for-a-list-library-folder-document-or-list-item-9d13e7df-a770-4646-91ab-e3c117fcef45)<br /><br />[Information Rights Management toepassen op een lijst of bibliotheek](http://office.microsoft.com/sharepoint-help/apply-information-rights-management-to-a-list-or-library-HA102891460.aspx)|
|SharePoint configureren voor IRM en beveiligde bibliotheken|[Information Rights Management (IRM) instellen in het SharePoint-beheercentrum](https://support.office.com/en-us/article/Set-up-Information-Rights-Management-IRM-in-SharePoint-admin-center-239ce6eb-4e81-42db-bf86-a01362fed65c)<br /><br />[Information Rights Management toepassen op een lijst of bibliotheek](http://office.microsoft.com/sharepoint-help/apply-information-rights-management-to-a-list-or-library-HA102891460.aspx)|

### De SharePoint-bibliotheek voor IRM-instellingen configureren

1.  Nadat u SharePoint voor het gebruik van de IRM -service hebt geconfigureerd, gaat u naar de SharePoint-bibliotheek om documenten te beveiligen met Azure RMS. Klik op de pagina **Instellingen** &gt; **Information Rights Management (IRM)** voor de site, waar u ook **De machtigingen voor deze bibliotheek bij downloaden beperken** selecteert en een beleidstitel voor beheerders en een beleidsbeschrijving voor gebruikers opgeeft, op **OPTIES WEERGEVEN**.

2.  Selecteer het volgende:

    -   **Gebruikers niet toestaan om documenten te uploaden die IRM niet ondersteunen**

    -   Optioneel: **Groepsbeveiliging toestaan. Standaardgroep** en geef vervolgens de naam van een andere groep waarmee mogelijk moet worden samengewerkt aan documenten die in deze bibliotheek, maar buiten SharePoint, zijn opgeslagen. De groep Verkoop beschikt bijvoorbeeld over bewerkingsmachtigingen voor de site en iemand uit deze groep downloadt een document, slaat dit lokaal op en verzendt het per e-mail naar een collega die geen lid is van de groep Verkoop. Als de collega lid is van de groep die u hier opgeeft, neemt deze collega automatisch dezelfde machtigingen over die voor de site zijn geconfigureerd en kan deze het document bewerken.

        Zonder deze optie kunnen alleen gebruikers die toegang hebben tot de SharePoint-bibliotheek samenwerken aan deze documenten, en alleen door de documenten rechtstreeks vanuit SharePoint te downloaden. Deze beperking is in veel gevallen van toepassing.

## Instructies voor de gebruikersdocumentatie
Er zijn in dit scenario geen specifieke instructies voor de gebruikers, omdat beveiligde bibliotheken geen speciale actie van de gebruikers vereisen. Documenten worden bij het downloaden automatisch beveiligd volgens de machtigingen die een SharePoint-beheerder voor de site instelt. Informeer gebruikers echter over deze wijziging zodat ze weten wat ze kunnen verwachten. Stel ook uw helpdesk op de hoogte van de bibliotheken die zijn beveiligd en hoe dit het gebruik van de documenten kan beperken. Vanwege de huidige beperkingen kunnen deze documenten bijvoorbeeld worden bekeken, maar niet worden bewerkt op mobiele apparaten. Als u de groepsbeveiliging hebt geconfigureerd, laat u de gebruikers weten welke groepen documenten buiten SharePoint kunnen openen en bewerken.

Kopieer en plak aan de hand van de volgende sjabloon de aankondiging in een bericht voor de eindgebruikers en breng de volgende wijzigingen aan zodat de instructies van toepassing zijn op uw omgeving:

1.  Vervang *&lt;naam van de SharePoint-bibliotheek&gt;* met de naam en koppeling van de SharePoint-bibliotheek die u hebt geconfigureerd voor Azure Rights Management. Als dit bericht betrekking heeft op meer dan één beveiligde bibliotheek, past u de instructies aan de situatie aan.

2.  Als u de optie **Groepsbeveiliging toestaan. Standaardgroep** hebt geconfigureerd, vervangt u *&lt;groepsnaam&gt;* met de naam van de groep die u hebt geconfigureerd en geeft u de reden op voor &lt;reden waarom deze groep toegangsmachtigingen heeft om samen te werken aan de bestanden, maar niet via de SharePoint-bibliotheek&gt;. Als u deze optie niet hebt geconfigureerd, verwijdert u deze zin.

3.  Vervang *&lt;contactgegevens&gt;* met instructies voor de gebruikers om contact op te nemen met de helpdesk, zoals een websitekoppeling, e-mailadres of telefoonnummer.

4.  Breng eventuele aanvullende wijzigingen aan in de aankondiging en verzend deze naar de gebruikers.

In de voorbeelddocumentatie wordt getoond hoe de aankondiging, na uw aanpassingen, voor de gebruikers kan zijn weergegeven.

![Gebruikersdocumentatiesjabloon voor de snelle implementatie van Azure RMS](../media/AzRMS_UsersBanner.png)

### IT-aankondiging: wijzigingen in de site &lt;naam van de SharePoint-bibliotheek&gt;
De SharePoint-site **&lt;naam van de SharePoint-bibliotheek&gt;** is nu geconfigureerd voor een beveiligde samenwerking. Nu kunnen alleen leden van de &lt;groepsnaam&gt; deze documenten openen vanuit deze site, zelfs als u deze lokaal opslaat of ze per e-mail naar iemand verzendt. De uitzondering hierop is dat u ze met leden van de &lt;groepsnaam&gt; kunt delen nadat u de documenten hebt gedownload zodat &lt;reden waarom deze groep toegangsmachtigingen heeft om samen te werken aan de bestanden, maar niet via de SharePoint-bibliotheek&gt;. Wanneer u de bestanden bewerkt, ziet u boven aan het document een gele informatiebalk, waarin wordt vermeld dat deze beveiliging wordt toegepast en wie er toegang heeft.

Met deze wijziging blijft onze vertrouwelijke bedrijfsinformatie uit het zicht van onbevoegde personen. Als u gebruikmaakt van een mobiel apparaat om toegang te krijgen tot deze beveiligde documenten, kunt u deze bekijken, maar u kunt ze alleen op een desktopcomputer bewerken.

U kunt geen documenten naar de site &lt;naam van de SharePoint-site&gt; uploaden als deze geen ondersteuning bieden voor beveiligde samenwerking.

**Hebt u hulp nodig?**

-   Neem contact op met de helpdesk: &lt;contactgegevens&gt;

### Voorbeeld van gebruikersdocumentatie
![Voorbeeld van gebruikersdocumentatie voor de snelle implementatie van Azure RMS](../media/AzRMS_ExampleBanner.png)

#### IT-aankondiging: wijzigingen in de site Verkoopprognoses en rapporten
De SharePoint-site **Verkoopprognoses en rapporten** is nu geconfigureerd voor een beveiligde samenwerking. Nu kunnen alleen leden van ons team Verkoop en Marketing deze documenten openen vanuit deze site, zelfs als u deze lokaal opslaat of ze per e-mail naar iemand verzendt. De uitzondering hierop is dat u ze met leden van het financiële team kunt delen nadat u de documenten hebt gedownload zodat ze hieruit de maandelijkse prognosecijfers kunnen afleiden. Wanneer u de bestanden bewerkt, ziet u boven aan het document een gele informatiebalk, waarin wordt vermeld dat deze beveiliging wordt toegepast en wie er toegang heeft.

Met deze wijziging blijft onze vertrouwelijke bedrijfsinformatie uit het zicht van onbevoegde personen. Als u gebruikmaakt van een mobiel apparaat om toegang te krijgen tot deze beveiligde documenten, kunt u deze bekijken, maar u kunt ze alleen op een desktopcomputer bewerken.

U kunt geen documenten naar de site Verkoopprognoses en rapporten uploaden als deze geen ondersteuning bieden voor beveiligde samenwerking.

**Hebt u hulp nodig?**

-   Neem contact op met de helpdesk: helpdesk@vanarsdelltd.com




<!--HONumber=Aug16_HO4-->


