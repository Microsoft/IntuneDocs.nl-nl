---
# required metadata

title: Algemene beheertaken voor Windows-pc’s | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: eb912c73-54d2-4d78-ac34-3cbe825804c7

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Algemene beheertaken voor Windows-pc’s met de Microsoft Intune-computerclient
Bestudeer de taken in dit onderwerp voor meer informatie over het beheren van computers met de Intune-client. Als u de client nog niet op uw computers hebt geïnstalleerd, ziet u [Installeer de Windows-pc-client met Windows Intune](install-the-windows-pc-client-with-microsoft-intune.md).


## Beleid gebruiken voor het vereenvoudigen van pc-beheer
### De Windows Firewall beheren
Beleidsregels vereenvoudigen het beheer van Windows Firewall-instellingen op beheerde computers. Zie voor meer informatie [Windows-pc's beschermen met Windows Firewall-beleid in Microsoft Intune](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md).

### Het Microsoft Intune Center beheren
Met het Microsoft Intune Center kunnen gebruikers:

-   Toepassingen ophalen via de bedrijfsportal.

-   Controleren op updates.

-   Microsoft Intune Endpoint Protection beheren.

-   Hulp op afstand vragen.

Het Microsoft Intune Center wordt geïnstalleerd op alle beheerde computers. U kunt de volgende instellingen in een Intune-beleid configureren en deze instellingen worden weergegeven aan gebruikers in het Microsoft Intune Center:

|Beleidsinstelling|Details|
|------------------|--------------------|
|**Naam**|De naam van de beheerder die de computer beheert.<br /><br />Maximale lengte: 40 tekens|
|**Telefoonnummer**|Het telefoonnummer van de beheerder die de computer beheert.<br /><br />Maximale lengte: 20 tekens|
|**E-mailadres**|Het e-mailadres van de beheerder die de computer beheert.<br /><br />Maximale lengte: 40 tekens|
|**Websitenaam**|De naam van uw ondersteuningswebsite voor gebruikers.<br /><br />Maximale lengte: 40 tekens|
|**Website-URL**|De URL van uw ondersteuningswebsite.<br /><br />Maximale lengte: 150 tekens|
|**Opmerkingen**|Een opmerking die wordt weergegeven voor gebruikers.<br /><br />Maximale lengte: 120 tekens|

### Instellingen voor software-updates beheren
Gebruik beleidsregels om de instellingen te configureren die beheerde computers gebruiken voor het controleren op en downloaden van software-updates van Microsoft en derden. Zie voor meer informatie [Windows-pc’s up-to-date houden met software-updates in Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).

### Instellingen voor Endpoint Protection beheren
Gebruik beleidsregels voor het configureren van instellingen voor Endpoint Protection die u vervolgens implementeert op beheerde computers. Dit omvat scanschema's, te ondernemen acties wanneer schadelijke software wordt gedetecteerd, en meer. Zie voor meer informatie [Help Windows-pc's beveiligen met Endpoint Protection Help voor Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).

## Hardware- en software-inventarisatie weergeven
Intune verzamelt gedetailleerde informatie over de hardware en software van beheerde computers. Gebruik de informatie in de volgende procedures om het volgende te leren maken:

-   Een rapport met een overzicht van de informatie over de hardwaremogelijkheden van uw computers.

-   Een rapport met een overzicht van de software die op elke computer is geïnstalleerd.

-   De inventarisatie van een computer vernieuwen om ervoor te zorgen dat de gegevens in het rapport actueel zijn.

### Informatie over uw computers weergeven

1.  Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) op **Rapporten** &gt; **Computerinventarisatierapporten**..

2.  Op de pagina **Nieuw rapport maken** accepteert u de standaardwaarden of past u deze aan om de resultaten te filteren die door het rapport worden geretourneerd. U kunt bijvoorbeeld selecteren dat alleen computers met Windows 8.1 worden weergegeven in het rapport.

3.  Klik op **Rapport weergeven** om het **Computerinventarisatierapport** te openen in een nieuw venster.

    U kunt het rapport rangschikken op een kolom, zoals **Naam**, **Chassistype** of **Fabrikant**, door te klikken op de bijbehorende kolomkop.

### Software weergeven die op uw computers is geïnstalleerd

1.  Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) op **Rapporten** &gt; **Rapporten met gedetecteerde software**.

2.  Op de pagina **Nieuw rapport maken** accepteert u de standaardwaarden of past u deze aan om de resultaten te filteren die door het rapport worden geretourneerd. U kunt bijvoorbeeld selecteren dat alleen de software die is uitgegeven door Microsoft, wordt weergegeven in het rapport.

3.  Klik op **Rapport weergeven** om het **Rapport met gedetecteerde software** te openen in een nieuw venster.

    U kunt het rapport rangschikken op een kolom zoals **Naam**, **Uitgever** of **Categorie** door te klikken op de bijbehorende kolomkop. U kunt de updates in de lijst uitbreiden om meer details weer te geven (zoals de computers waarop deze update is geïnstalleerd) door te klikken op de pijl naast het item.

### Computerinventarisatie vernieuwen zodat deze actueel is

1.  Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) op **Groepen** &gt; **Alle apparaten** (of een andere groep die de computer bevat waarvoor u de inventarisatie wilt vernieuwen).

2.  Selecteer een computer of houd **Ctrl** ingedrukt om meerdere computers te selecteren.

3.  Klik op de taakbalk op **Externe taken** &gt; **Inventarisatie vernieuwen**.

4.  Als u de status van de taak wilt weergeven, klikt u op **Externe taken** in de rechterbenedenhoek van de pagina.

    Het dialoogvenster **Taakstatus** wordt weergegeven met huidige externe taken, taakstatus, apparaatnaam en gerapporteerde fouten, en het bevat een koppeling naar informatie voor probleemoplossing.


## Een Windows-pc op afstand opnieuw opstarten

1.  Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) op **Groepen** &gt; **Alle apparaten** (of een andere groep die de computer bevat die u opnieuw wilt opstarten).

2.  Selecteer een of meer computers en klik vervolgens op **Externe taken** &gt; **Computer opnieuw opstarten**.

3.  Als u de status van de taak wilt weergeven, klikt u op **Externe taken** in de rechterbenedenhoek van de pagina.

4.  In het dialoogvenster **Taakstatus** controleert u de huidige externe taken, de taakstatus, de apparaatnaam en eventuele gerapporteerde fouten.

## Een computer buiten gebruik stellen

1.  Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) op **Groepen** &gt; **Alle apparaten** (of een andere groep die de computer bevat die u buiten gebruik wilt stellen).

2.  Selecteer de apparaten die u buiten gebruik wilt stellen en klik vervolgens op **Buiten gebruik stellen/Wissen**.

Als u een computer opnieuw wilt inschrijven bij Intune, installeert u de clientsoftware opnieuw op de computer met behulp van de informatie in het onderwerp [Installeer de Windows-pc-client met Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).

Als een computer geen verbinding kan maken met Intune, wordt een bericht weergegeven in de werkruimte **Dashboard**.

Wanneer u een computer buiten gebruik stelt:

-   Wordt deze verwijderd uit de Intune-inventarisatie en wordt de licentie die aan de computer is gekoppeld, beschikbaar gesteld voor hergebruik.

-   Wordt de status ervan niet meer weergegeven de Intune-console.

-   Verwijdert Intune de clientsoftware van de computer. Als de computer niet met de Intune-service is verbonden, wordt de clientsoftware de volgende keer dat de computer verbinding maakt, verwijderd.

-   Microsoft Intune Endpoint Protection wordt verwijderd van de computer. Als op de computer een andere eindpunttoepassing is geïnstalleerd en deze is uitgeschakeld, kan die toepassing opnieuw worden ingeschakeld nadat Microsoft Intune Endpoint Protection is verwijderd om ervoor te zorgen dat uw computers zijn beveiligd.

-   Eventuele beleidsregels worden verwijderd van de computer en de waarden die zijn ingesteld door het beleid, worden gewijzigd.

-   De computer ontvangt geen software-updates of updates voor definities van schadelijke software meer van de Intune-service.

-   Afhankelijk van de configuratie kunnen computers die buiten gebruik zijn gesteld, nog steeds updates ontvangen via Windows Server Update Services, Windows Update of Microsoft Update.

    > [!IMPORTANT]
    > Als de clientsoftware is geïnstalleerd met behulp van een groepsbeleidsobject (GPO), moet u het groepsbeleidsobject verwijderen voordat u de clientsoftware kunt verwijderen om te voorkomen dat de software wordt geïnstalleerd.

    Als de client niet kan worden verwijderd, leest u [Problemen met Endpoint Protection oplossen](/intune/troubleshoot/troubleshoot-endpoint-protection-in-microsoft-intune) voor meer informatie.

## Gebruiker/apparaatkoppeling beheren
Voordat u software voor een gebruiker kunt implementeren, moet u de gebruiker aan een computer koppelen. U kunt een gebruiker aan meerdere computers koppelen, maar elke computer kan aan slechts één gebruiker worden gekoppeld. Gebruikers worden automatisch gekoppeld aan computers die ze inschrijven bij Intune met behulp van de bedrijfsportal.

### Een gebruiker aan een computer koppelen

1.  Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) op **Groepen** &gt; **Alle apparaten** (of een andere groep die de computer bevat die u aan een gebruiker wilt koppelen).

2.  Selecteer de computer die u aan een gebruiker wilt koppelen en klik vervolgens op **Gebruiker koppelen**.

    In het dialoogvenster **Gebruiker koppelen** wordt een lijst met beschikbare gebruikers weergegeven met hun weergavenaam, gebruikers-id en het aantal computers waaraan elke gebruiker momenteel is gekoppeld. Als een gebruiker al aan de geselecteerde computer is gekoppeld, worden de naam van die gebruiker en de gebruikers-id weergegeven onder **Huidige gebruiker**. Als de computer niet aan een gebruiker is gekoppeld, wordt **Geen gebruiker** weergegeven onder **Huidige gebruiker**.

3.  Voer een van de volgende handelingen uit:

    -   Als u de computer gekoppeld wilt laten aan de huidige gebruiker, indien aanwezig, klikt u op **Annuleren**.

    -   Als u de koppeling met de huidige gebruiker, indien aanwezig, wilt verwijderen, klikt u op **Koppeling verwijderen**&gt;**OK**.

    -   Als u de computer aan een nieuwe gebruiker wilt koppelen, selecteert u een gebruiker in de lijst **Alle gebruikers** . Controleer of de gebruikersgegevens juist zijn en klik vervolgens op **OK**.

> [!TIP]
> Als u de mogelijkheden van eindgebruikers om zichzelf aan computers te koppelen wilt beperken, schakelt u de optie **Koppelingen tussen gebruikers en computers beperken** in het beleid voor **Instellingen Microsoft Intune-agent** in.

## Reageren op een aanvraag voor hulp op afstand
Gebruikers kunnen om hulp vragen met behulp van Hulp op afstand via Microsoft Easy Assist, dat automatisch wordt geïnstalleerd op beheerde computers. Wanneer er een aanvraag wordt gedaan, wordt er een waarschuwing weergegeven in de Intune-console.

> [!IMPORTANT]
> Hulp op afstand wordt niet ondersteund op computers met Windows 8 of hoger.
>
> Als u een aanvraag voor hulp op afstand accepteert van een computer waarop Microsoft Easy Assist niet is geïnstalleerd, wordt de gebruiker gevraagd om dit te installeren. De computer moet opnieuw worden opgestart na de installatie. U kunt Microsoft Easy Assist vooraf laden op de computers van uw gebruikers om deze herstart te voorkomen.

### Een aanvraag voor hulp op afstand beheren

1.  Klik in de[ Microsoft Intune-beheerconsole](https://manage.microsoft.com/) op **Waarschuwingen** &gt; **Hulp op afstand**.

2.  Selecteer een aanvraag voor hulp op afstand in de lijst **Waarschuwingen** om de eigenschappenpagina van de aanvraag te openen.

3.  Klik op **Aanvraag goedkeuren en Hulp op afstand starten** om een dialoogvenster te openen met opties voor het omzetten van de waarschuwing.

4.  Voer een van de volgende handelingen uit:

    -   **De aanvraag accepteren**: als u aan de externe sessie wilt deelnemen, klikt u op **De aanvraag voor hulp op afstand accepteren**.

        De gebruiker ziet het volgende bericht: **Uw aanvraag is geaccepteerd. Volg de instructies in Easy Assist om een programma of uw bureaublad te delen met uw systeembeheerder**.

        > [!IMPORTANT]
        > U kunt een aanvraag voor hulp op afstand niet accepteren op een Mac-computer waarop de Intune-beheerconsole wordt uitgevoerd.

    -   **De aanvraag weigeren**: sluit het venster **Informatie voor probleemoplossing weergeven** en klik vervolgens op **Deze waarschuwing sluiten** in het venster met waarschuwingseigenschappen.

        De aanvraag wordt gesloten en de gebruiker ziet een bericht waarin staat dat de aanvraag is geweigerd. Als de gebruiker opnieuw hulp op afstand wil aanvragen, moet deze een nieuwe aanvraag voor hulp op afstand verzenden. Als u een waarschuwing voor hulp op afstand per ongeluk hebt gesloten, neemt u contact op met de gebruiker die de aanvraag voor hulp op afstand heeft verzonden en vraagt u de gebruiker om een nieuwe aanvraag te verzenden.


<!--HONumber=May16_HO1-->


