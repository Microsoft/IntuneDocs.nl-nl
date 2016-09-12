---
title: Een aangepaste sjabloon maken, configureren en publiceren | Azure RMS
description: U maakt en beheert aangepaste sjablonen in de klassieke Azure-portal. U kunt dit rechtstreeks doen vanuit de klassieke Azure-portal of u kunt zich aanmelden bij het Office 365-beheercentrum en de Geavanceerde functies voor Rights Management kiezen. U wordt dan doorgestuurd naar de klassieke Azure-portal.
author: cabailey
manager: mbaldwin
ms.date: 07/15/2016
ms.topic: article
ms.prod: 
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: d6e9aa0c-1694-4a53-8898-4939f31cc13f
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 26b043f1f9e7a1e0cd00c2f31c28f7d6685f0232
ms.openlocfilehash: 64beb891fda54da3718a322f6628a2987ff35111


---


# Aangepaste sjablonen maken, configureren en publiceren

>*Van toepassing op: Azure Rights Management, Office 365*


U maakt en beheert aangepaste sjablonen in de klassieke Azure-portal. U kunt dit rechtstreeks doen vanuit de klassieke Azure-portal of u kunt zich aanmelden bij het Office 365-beheercentrum en de **Geavanceerde functies** voor Rights Management kiezen. U wordt dan doorgestuurd naar de klassieke Azure-portal.

U moet een globale beheerder zijn om sjablonen in de klassieke Azure-portal te kunnen aanmaken en beheren. Als u globale beheerder bent voor Azure RMS voor andere gebruikers, kunnen zij ook sjablonen maken en beheren, maar dan moeten ze wel gebruikmaken van [PowerShell](configure-templates-with-powershell.md). Zie [Moet ik een globale beheerder zijn om Azure RMS te configureren of kan ik delegeren aan andere beheerders?](../get-started/faqs.md#do-you-need-to-be-a-global-admin-to-configure-azure-rms-or-can-i-delegate-to-other-administrators) voor meer informatie. 

Gebruik de volgende procedures om aangepaste sjablonen voor Rights Management te maken, configureren en publiceren.

## Een aangepaste sjabloon maken

1.  Afhankelijk van of u zich aanmeldt bij het Office 365-beheercentrum of bij de klassieke Azure-portal, doet u een van de volgende dingen:

    -   Vanuit het [Office 365-beheercentrum](https://portal.office.com/):

        1.  Klik in het linkerdeelvenster op **service-instellingen**.

        2.  Klik op de pagina **service-instellingen** op **Rights management**.

        3.  Klik in het gedeelte **Uw gegevens beveiligen** op **Beheren**.

        4.  Klik in het gedeelte **Rights management** op **geavanceerde functies**.

            > [!NOTE]
            > Als u Rights Management nog niet hebt geactiveerd, klikt u eerst op **Activeren** en bevestigt u uw actie. Zie voor meer informatie [Azure Rights Management activeren](activate-service.md).
            > 
            > Als u nog niet eerder op **geavanceerde functies** hebt geklikt, volgt u, na activering van Rights Management, de scherminstructies voor het ophalen van een gratis Azure-abonnement dat u nodig hebt voor toegang tot de klassieke Azure-portal.

            Wanneer u op **geavanceerde functies** klikt, wordt de klassieke Azure-portal geladen. In deze portal kunt u **RIGHTS MANAGEMENT** voor de Azure Active Directory van uw organisatie beheren.

    -   Vanuit de [klassieke Azure-portal](http://go.microsoft.com/fwlink/p/?LinkID=275081):

        1.  Klik in het linkerdeelvenster op **ACTIVE DIRECTORY**.

        2.  Klik op de pagina **Active directory** op **RIGHTS MANAGEMENT**.

        3.  Selecteer de map om Rights Management te beheren.

        4.  Als u Rights Management nog niet hebt geactiveerd, klikt u op **ACTIVEREN** en bevestigt u de actie.

            > [!NOTE]
            > Zie voor meer informatie [Azure Rights Management activeren](activate-service.md).

2.  Een nieuwe sjabloon maken:

    -   Ga in de klassieke Azure-portal naar de snelstartpagina **Aan de slag met Rights Management** en klik op **Nieuwe rechtenbeleidssjabloon maken**.

        Als u deze pagina niet onmiddellijk ziet nadat u de instructies voor Office 365 hebt uitgevoerd, volgt u de navigatie-instructies hierboven voor de klassieke Azure-portal.

3.  Kies op de pagina **Een nieuwe rechtenbeleidssjabloon toevoegen** de taal waarin u de sjabloonnaam en -beschrijving typt die gebruikers zien (u kunt later meer talen toevoegen). Vervolgens typt u een unieke naam en beschrijving en klikt u op de knop Voltooien.

Ga naar de snelstartpagina **Aan de slag met Rights Management** en klik op **Uw rechtsbeleidssjablonen beheren**. U ziet dat de zojuist gemaakte sjabloon is toegevoegd aan de lijst met sjablonen, met de status **Gearchiveerd**. In deze fase, waarin de sjabloon is gemaakt maar nog niet geconfigureerd, is de sjabloon niet zichtbaar voor gebruikers.

## Een aangepaste sjabloon configureren en publiceren

1.  Selecteer de zojuist gemaakte sjabloon op de pagina **SJABLONEN** in de klassieke Azure-portal.

2.  Ga naar de snelstartpagina **Uw sjabloon is toegevoegd** en klik op **Aan de slag** uit stap 1 en vervolgens op **Rechten voor gebruikers en groepen configureren**. Klik daarna op **NU AAN DE SLAG** of **TOEVOEGEN** en selecteer de gebruikers en groepen die rechten krijgen voor het gebruik van de inhoud die wordt beveiligd met de nieuwe sjabloon.

    > [!NOTE]
    > De gebruikers of groepen die u selecteert, moeten een e-mailadres hebben. Dit is bijna altijd het geval in een productieomgeving, maar in een eenvoudige testomgeving moet u wellicht e-mailadressen toevoegen aan gebruikersaccounts of groepen.

    Het is een best practice om te werken met groepen in plaats van gebruikers omdat dit het beheer van de sjablonen vereenvoudigt. Als u lokaal werkt met Active Directory en synchroniseert met Azure AD, kunt u gebruikmaken van beveiligingsgroepen of distributiegroepen met e-mail. Als u echter rechten aan alle gebruikers in de organisatie wilt verlenen, is het efficiënter een van de standaardsjablonen te kopiëren in plaats van meerdere groepen op te geven. Zie [How to copy a template](copy-template.md) (Een sjabloon kopiëren) voor meer informatie.

    > [!TIP]
    > U kunt gebruikers van buiten uw organisatie ('externe gebruikers') toevoegen aan de sjabloon door een e-mailgroep met contactpersonen uit Office 365 of Exchange Online te selecteren. Hiermee kunt u op dezelfde manier rechten toewijzen aan deze gebruikers als u rechten toewijst aan gebruikers in uw organisatie. U kunt bijvoorbeeld voorkomen dat klanten een prijslijst bewerken die u aan hen verzendt. Gebruik deze sjabloonconfiguratie niet voor het beveiligen van e-mailberichten als gebruikers van buiten uw organisatie de beveiligde e-mailberichten lezen met Outlook Web App.
    > 
    > Daarnaast kunt u later gebruikers van buiten uw organisatie toevoegen aan de sjabloon met de [Windows PowerShell-module voor Azure Rights Management](install-powershell.md) en daarbij een van de volgende methoden volgen:
    > 
    > -  **Een sjabloon bijwerken met een rechtendefinitieobject**: geef de externe e-mailadressen en de rechten hiervan op in een rechtendefinitieobject, waarmee u vervolgens de sjabloon bijwerkt. U geeft het rechtendefinitieobject op met de cmdlet [New-AadrmRightsDefinition](https://msdn.microsoft.com/library/azure/dn727080.aspx) om een variabele te maken en geeft deze variabele vervolgens door aan de parameter -RightsDefinition met de cmdlet [Set-AadrmTemplateProperty instellen](https://msdn.microsoft.com/library/azure/dn727076.aspx) om een bestaande sjabloon te wijzigen. Als u deze gebruikers echter aan een bestaande sjabloon toevoegt, moet u ook rechtendefinitieobjecten definiëren voor de bestaande groepen in de sjablonen en niet alleen voor de nieuwe externe gebruikers.
    > -  **De bijgewerkte sjabloon exporteren, bewerken en importeren**: met de cmdlet [Export-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727078.aspx) kunt u de sjabloon exporteren naar een bestand dat u kunt bewerken om de externe e-mailadressen van deze gebruikers en hun rechten toe te voegen aan de bestaande groepen en rechten. Gebruik vervolgens de cmdlet [Import-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727077.aspx) om deze wijziging weer te importeren in Azure RMS.

3.  Klik op de knop Volgende en wijs vervolgens een van de vermelde rechten toe aan de door u geselecteerde gebruikers en groepen.

    Gebruik de weergegeven beschrijving voor meer informatie over elk recht (en voor aangepaste rechten). Gedetailleerdere informatie is ook beschikbaar in [Gebruiksrechten configureren voor Azure Rights Management](configure-usage-rights.md). Er kunnen echter verschillen zijn in de manier waarop deze rechten zijn geïmplementeerd in toepassingen die ondersteuning bieden voor RMS. Raadpleeg de bijbehorende documentatie en voer uw eigen tests uit met de toepassingen waar gebruikers mee werken, om het gedrag ervan te controleren voordat u de sjabloon voor gebruikers implementeert. Als u wilt dat deze sjabloon tijdens het testen alleen door beheerders kan worden weergegeven, maakt u van deze sjabloon een afdelingssjabloon (stap 6).

4.  Als u **Aangepast** hebt geselecteerd, klikt u op de knop Volgende en selecteert vervolgens de aangepaste rechten.

    Hoewel u elke combinatie van beschikbare individuele rechten kunt gebruiken, kunnen sommige rechten in bepaalde toepassingen afhankelijk zijn van andere individuele rechten. Wanneer dit het geval is, worden de afhankelijke rechten automatisch voor u geselecteerd.

    > [!TIP]
    > Overweeg het recht **Inhoud kopiëren en ophalen** toe te voegen en dit recht te verlenen aan geselecteerde beheerders of medewerkers in andere rollen met verantwoordelijkheden voor het herstellen van gegevens. Wanneer dit recht aan hen is verleend, kunnen zij desgewenst de bescherming verwijderen van bestanden en e-mails die met deze sjabloon worden beschermd. Deze mogelijkheid om bescherming te verwijderen op sjabloonniveau biedt preciezere beheermogelijkheden dan de functie Supergebruiker.

5.  Klik op de knop Voltooien.

6.  Als u wilt dat de sjabloon alleen zichtbaar is voor een subset gebruikers wanneer ze een lijst met sjablonen in toepassingen zien, klikt u op **BEREIK** om de sjabloon als afdelingssjabloon te configureren. Klik vervolgens op **NU AAN DE SLAG**. Anders gaat u naar stap 9.

    Meer informatie over afdelingssjablonen: standaard zien alle gebruikers in uw Azure-map alle gepubliceerde sjablonen en kunnen ze deze selecteren in toepassingen wanneer ze inhoud willen beschermen. Als u wilt dat bepaalde gepubliceerde sjablonen alleen kunnen worden gezien door specifieke gebruikers, moet u voor deze gebruikers het bereik van de sjablonen instellen. Alleen deze gebruikers kunnen deze sjablonen dan selecteren. Andere gebruikers die u niet opgeeft, zien de sjablonen niet en kunnen ze daarom niet selecteren. Met deze techniek kunnen gebruikers gemakkelijker de juiste sjabloon kiezen, vooral wanneer u sjablonen maakt die zijn ontworpen voor gebruik door specifieke groepen of afdelingen. Gebruikers zien dan alleen de sjablonen die voor hen zijn ontworpen.

    U hebt bijvoorbeeld een sjabloon voor de afdeling Human Resources die medewerkers van de afdeling Financiën alleen in de alleen-lezenmodus kunnen openen. Als u ervoor wilt zorgen dat alleen medewerkers van de afdeling Human Resources deze sjabloon kunnen toepassen wanneer ze de Rights Management-toepassing voor delen gebruiken, stelt u het bereik van de sjabloon in op de e-mailgroep HumanResources. Alleen leden van deze groep kunnen deze sjabloon dan zien en weergeven.

7.  Selecteer op de pagina **ZICHTBAARHEID VAN SJABLOON** de gebruikers en groepen die de sjabloon kunnen zien en selecteren in toepassingen met RMS. Volg net zoals eerder de best practice om te werken met groepen in plaats van gebruikers. De geselecteerde groepen of gebruikers moeten een e-mailadres hebben.

8.  Klik op de knop Volgende en beslis of u toepassingscompatibiliteit voor uw afdelingssjabloon moet configureren. Als dat zo is, schakelt u het vakje **TOEPASSINGSCOMPATIBILITEIT** in en klikt u op **Voltooien**.

    Waarom zou u toepassingscompatibiliteit moeten configureren? Niet alle toepassingen bieden ondersteuning voor afdelingssjablonen. De toepassing moet daarvoor eerst worden geverifieerd bij de RMS-service, voordat de sjablonen worden gedownload. Als het verificatieproces niet wordt uitgevoerd, wordt standaard geen van de afdelingssjablonen gedownload. U kunt dit gedrag negeren door op te geven dat alle afdelingssjablonen moeten worden gedownload, door toepassingscompatibiliteit te configureren en door het selectievakje **Deze sjabloon voor alle gebruikers weergeven wanneer de toepassingen geen ondersteuning bieden voor gebruikersidentiteit** in te schakelen.

    Als u toepassingscompatibiliteit bijvoorbeeld niet configureert voor de afdelingssjabloon in ons voorbeeld over Human Resources, zien alleen gebruikers van de afdeling Human Resources de afdelingssjabloon wanneer ze de RMS-toepassing voor delen gebruiken, maar zijn er geen gebruikers die de afdelingssjabloon zien wanneer ze Outlook Web Access (OWA) van Exchange Server 2013 gebruiken, omdat Exchange OWA en Exchange ActiveSync momenteel geen afdelingssjablonen ondersteunen. Als u dit standaardgedrag negeert door toepassingscompatibiliteit te configureren, zien alleen gebruikers van de afdeling Human Resources de afdelingssjabloon wanneer ze de RMS-toepassing voor delen gebruiken, maar zien alle gebruikers de afdelingssjabloon wanneer ze Outlook Web Access (OWA) gebruiken. Als gebruikers OWA of Exchange ActiveSync vanaf Exchange Online gebruiken, zien alle gebruikers de afdelingssjablonen of ziet geen enkele gebruiker de afdelingssjablonen, afhankelijk van de sjabloonstatus (gearchiveerd of gepubliceerd) in Exchange Online.

    Office 2016 ondersteunt systeemeigen afdelingssjablonen, evenals Office 2013 vanaf versie 15.0.4727.1000, uitgebracht in juni 2015 als onderdeel van [KB 3054853](https://support.microsoft.com/kb/3054853).

    > [!NOTE]
    > Als uw toepassingen nog geen systeemeigen afdelingssjablonen ondersteunen, kunt u een aangepast downloadscript voor RMS-sjablonen of andere hulpprogramma's gebruiken om deze sjablonen te implementeren in de lokale RMS-clientmap. Deze toepassingen geven de afdelingssjablonen dan alleen juist weer voor de gebruikers en groepen die u hebt geselecteerd voor het bereik van de sjabloon:
    > 
    > -   Voor Office 2010 is de clientmap **%localappdata%\Microsoft\DRM\Templates**.
    > -   Vanaf een clientcomputer waarop alle sjablonen zijn gedownload, kunt u de sjabloonbestanden kopiëren en plakken naar andere computers.
    > 
    > U kunt [het aangepaste RMS-sjabloonscript downloaden vanaf de Microsoft Connect-website](http://go.microsoft.com/fwlink/?LinkId=524506). Als u een fout ziet wanneer u op deze koppeling klikt, hebt u zich waarschijnlijk niet aangemeld bij Microsoft Connect. Aanmelden:
    > 
    > 1.  Ga naar de [Microsoft Connect-site](http://www.connect.microsoft.com) en meld u aan bij uw Microsoft-account.
    > 2.  Klik op **Directory** en selecteer de categorie **Connect-producten weergeven die momenteel geen feedback accepteren**.
    > 3.  Zoek naar **Rights Management Services** en naar het programma **Microsoft RMS Enterprise-functies**. Klik vervolgens op **Deelnemen**.

9. Klik op **CONFIGUREREN** en voeg extra talen toe die door gebruikers worden gebruikt, samen met de naam en beschrijving van deze sjabloon in die taal. Wanneer u meertalige gebruikers hebt, is het belangrijk om elke taal toe te voegen die ze gebruiken, en een naam en beschrijving in die taal op te geven. Gebruikers krijgen vervolgens de naam en beschrijving van de sjabloon te zien in dezelfde taal als hun clientbesturingssysteem, wat garandeert dat ze het op een document of e-mailbericht toegepaste beleid begrijpen. Als er geen overeenkomst is met hun clientbesturingssysteem, worden de naam en beschrijving die gebruikers zien, teruggezet naar de taal en beschrijving die u hebt opgegeven toen u de sjabloon voor het eerst maakte.

    Ga vervolgens na of u de volgende instellingen wilt wijzigen:

    |Instelling|Meer informatie|
    |-----------|--------------------|
    |**vervaldatum inhoud**|Definieer voor deze sjabloon een datum of aantal dagen gedurende welke door de sjabloon beveiligde bestanden niet mogen worden geopend. U kunt een datum of aantal dagen opgeven, beginnend op het moment dat de beveiliging op het bestand wordt toegepast.<br /><br />Wanneer u een datum opgeeft, gaat deze in om middernacht in uw huidige tijdzone.|
    |**offline toegang**|Gebruik deze instelling om een juist evenwicht te vinden tussen uw beveiligingsvereisten en de vereiste dat gebruikers beschermde bestanden moeten kunnen openen wanneer ze geen internetverbinding hebben.<br /><br />Als u opgeeft dat inhoud niet beschikbaar is zonder internetverbinding of dat inhoud alleen beschikbaar is gedurende een bepaald aantal dagen, moeten gebruikers bij het bereiken van deze drempelwaarde opnieuw worden geverifieerd en wordt hun toegang geregistreerd. Als dit gebeurt en hun referenties niet in het cachegeheugen zijn opgeslagen, wordt gebruikers gevraagd zich aan te melden voordat ze het bestand kunnen openen.<br /><br />Behalve hernieuwde verificatie worden het beleid en het gebruikersgroeplidmaatschap opnieuw geëvalueerd. Dit betekent dat gebruikers verschillende toegangsresultaten voor hetzelfde bestand kunnen ondervinden als het beleid of groepslidmaatschap is gewijzigd sinds ze het bestand voor het laatst hebben geopend.|

10. Als u zeker weet dat de sjabloon juist is geconfigureerd voor uw gebruikers, klikt u op **PUBLICEREN** om de sjabloon zichtbaar te maken voor de gebruikers. Klik vervolgens op **OPSLAAN**.

11. Klik op de knop Terug in de klassieke portal om terug te gaan naar de pagina **SJABLONEN**, waar de sjabloon nu de bijgewerkte status **Gepubliceerd** heeft.

Breng de gewenste wijzigingen aan in de sjabloon, selecteer deze en voer vervolgens de snelstartstappen opnieuw uit. Of selecteer een van de volgende opties:

-   Meer gebruikers en groepen toevoegen en de rechten voor die gebruikers en groepen definiëren: klik op **RECHTEN** en vervolgens op **TOEVOEGEN**.

-   Eerder door u geselecteerde gebruikers of groepen verwijderen: klik op **RECHTEN**, selecteer de gebruiker of groep in de lijst en klik vervolgens op **VERWIJDEREN**.

-   Wijzigen welke gebruikers de sjablonen kunnen zien om deze te selecteren vanuit toepassingen: klik op **BEREIK**, klik vervolgens **TOEVOEGEN** of **VERWIJDEREN** of **TOEPASSINGSCOMPATIBILITEIT**.

-   De sjabloon niet langer zichtbaar maken voor alle gebruikers: klik achtereenvolgens op **CONFIGUREREN**, **ARCHIVEREN** en **OPSLAAN**.

-   Andere configuratiewijzigingen aanbrengen: klik op **CONFIGUREREN**, breng uw wijzigingen aan en klik vervolgens op **OPSLAAN**.

> [!WARNING]
> Wanneer u een eerder opgeslagen sjabloon wijzigt, worden de wijzigingen aan deze sjabloon pas weergegeven op de clientcomputers nadat de sjablonen op deze computers zijn vernieuwd. Zie [Refreshing templates for users](refresh-templates.md) (Sjablonen voor gebruikers vernieuwen) voor meer informatie.

## Zie ook
[Aangepaste sjablonen configureren voor Azure Rights Management](configure-custom-templates.md)


<!--HONumber=Aug16_HO4-->


