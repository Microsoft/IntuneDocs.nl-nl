---
title: Algemene beheertaken voor Windows-pc's | Microsoft Intune
description: Bestudeer de taken in dit onderwerp voor meer informatie over het beheren van computers met de Intune-pc-clientsoftware.
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb912c73-54d2-4d78-ac34-3cbe825804c7
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 385ed597e4af569dc5a2b559d693b6c8421f86fa
ms.openlocfilehash: e08fe1cdaa45ba957986511afb60a54da8152677


---

# Algemene beheertaken voor Windows-pc’s met de Microsoft Intune-computerclient
Bestudeer de taken in dit onderwerp voor meer informatie over het beheren van computers met de Intune-pc-clientsoftware. Zie [De Windows-pc-client installeren met Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md) als u de client nog niet op uw computers hebt geïnstalleerd.


## Beleid gebruiken voor het vereenvoudigen van pc-beheer
### De Windows Firewall beheren
Beleidsregels vereenvoudigen het beheer van Windows Firewall-instellingen op beheerde computers. Zie [Windows-pc's beschermen met Windows Firewall-beleid in Microsoft Intune](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) voor meer informatie.

### Het Microsoft Intune Center beheren
Met het Microsoft Intune Center kunnen gebruikers:

-   Toepassingen ophalen via de bedrijfsportal.

-   Controleren op updates.

-   Microsoft Intune Endpoint Protection beheren.

<!--- -   Request remote assistance.--->

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
Gebruik beleidsregels om de instellingen te configureren die beheerde computers gebruiken voor het controleren op en downloaden van software-updates van Microsoft en derden. Zie voor meer informatie [Windows-pc's up-to-date houden met software-updates in Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).

### Instellingen voor Endpoint Protection beheren
Gebruik beleidsregels voor het configureren van instellingen voor Endpoint Protection die u vervolgens implementeert op beheerde computers. Dit omvat scanschema's, te ondernemen acties wanneer schadelijke software wordt gedetecteerd, en meer. Zie [Help Windows-pc's beveiligen met Endpoint Protection voor Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) voor meer informatie.

## Hardware- en software-inventarisatie weergeven
Intune verzamelt gedetailleerde informatie over de hardware en software van beheerde computers. Gebruik de informatie in de volgende procedures om het volgende te leren maken:

-   Een rapport met een overzicht van de informatie over de hardwaremogelijkheden van uw computers.

-   Een rapport met een overzicht van de software die op elke computer is geïnstalleerd.

-   De inventarisatie van een computer vernieuwen om ervoor te zorgen dat de gegevens in het rapport actueel zijn.

### Informatie over uw computers weergeven

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) de optie **Rapporten**&gt;**Computerinventarisatierapporten**.

2.  Op de pagina **Nieuw rapport maken** accepteert u de standaardwaarden of past u deze aan om de resultaten te filteren die door het rapport worden geretourneerd. U kunt bijvoorbeeld selecteren dat alleen computers met Windows 8.1 worden weergegeven in het rapport.

3.  Klik op **Rapport weergeven** om het **Computerinventarisatierapport** te openen in een nieuw venster.

    U kunt het rapport rangschikken op een kolom, zoals **Naam**, **Chassistype** of **Fabrikant**, door te klikken op de bijbehorende kolomkop.

### Software weergeven die op uw computers is geïnstalleerd

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) de optie **Rapporten**&gt;**Rapporten met gedetecteerde software**.

2.  Op de pagina **Nieuw rapport maken** accepteert u de standaardwaarden of past u deze aan om de resultaten te filteren die door het rapport worden geretourneerd. U kunt bijvoorbeeld selecteren dat alleen de software die is uitgegeven door Microsoft, wordt weergegeven in het rapport.

3.  Klik op **Rapport weergeven** om het **Rapport met gedetecteerde software** te openen in een nieuw venster.

    U kunt het rapport rangschikken op een kolom zoals **Naam**, **Uitgever** of **Categorie** door te klikken op de bijbehorende kolomkop. U kunt de updates in de lijst uitbreiden om meer details weer te geven (zoals de computers waarop deze update is geïnstalleerd) door de richtingspijl naast het item te kiezen.

### Computerinventarisatie vernieuwen zodat deze actueel is

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) de optie **Groepen**&gt;**Alle apparaten** (of een andere groep die de computer bevat waarvoor u de inventarisatie wilt vernieuwen).

2.  Selecteer een computer of houd **Ctrl** ingedrukt om meerdere computers te selecteren.

3.  Kies op de taakbalk **Externe taken**&gt;**Inventarisatie vernieuwen**.

4.  Als u de status van de taak wilt weergeven, klikt u op **Externe taken** in de rechterbenedenhoek van de pagina.

    Het dialoogvenster **Taakstatus** wordt weergegeven met huidige externe taken, taakstatus, apparaatnaam en gerapporteerde fouten, en het bevat een koppeling naar informatie voor probleemoplossing.


## Een Windows-pc op afstand opnieuw opstarten

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) de optie **Groepen**&gt;**Alle apparaten** (of een andere groep die de computer bevat die u opnieuw wilt opstarten).

2.  Selecteer een of meer computers en klik vervolgens op **Externe taken**&gt;**Computer opnieuw opstarten**.

3.  Als u de status van de taak wilt weergeven, klikt u op **Externe taken** in de rechterbenedenhoek van de pagina.

4.  In het dialoogvenster **Taakstatus** controleert u de huidige externe taken, de taakstatus, de apparaatnaam en eventuele gerapporteerde fouten.

## Een computer buiten gebruik stellen

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) de optie **Groepen**&gt;**Alle apparaten** (of een andere groep die de computer bevat die u buiten gebruik wilt stellen).

2.  Selecteer de apparaten die u buiten gebruik wilt stellen en kies vervolgens **Buiten gebruik stellen/wissen**.

Als u een computer opnieuw wilt registreren bij Intune, installeert u de clientsoftware opnieuw op de computer met behulp van de informatie in het onderwerp [Installeer de Windows-pc-client met Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).

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
Voordat u software voor een gebruiker kunt implementeren, moet u de gebruiker aan een computer koppelen. U kunt een gebruiker aan meerdere computers koppelen, maar elke computer kan aan slechts één gebruiker worden gekoppeld. Gebruikers worden automatisch gekoppeld aan computers die ze registreren bij Intune met behulp van de bedrijfsportal.

### Een gebruiker aan een computer koppelen

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) de optie **Groepen**&gt;**Alle apparaten** (of een andere groep die de computer bevat die u aan een gebruiker wilt koppelen).

2.  Selecteer de computer die u aan een gebruiker wilt koppelen en kies vervolgens **Gebruiker koppelen**.

    In het dialoogvenster **Gebruiker koppelen** wordt een lijst met beschikbare gebruikers weergegeven met hun weergavenaam, gebruikers-id en het aantal computers waaraan elke gebruiker momenteel is gekoppeld. Als een gebruiker al aan de geselecteerde computer is gekoppeld, worden de naam van die gebruiker en de gebruikers-id weergegeven onder **Huidige gebruiker**. Als de computer niet aan een gebruiker is gekoppeld, wordt **Geen gebruiker** weergegeven onder **Huidige gebruiker**.

3.  Voer een van de volgende handelingen uit:

    -   Als u de computer gekoppeld wilt laten aan de huidige gebruiker, indien aanwezig, kiest u **Annuleren**.

    -   Als u de koppeling met de huidige gebruiker, indien aanwezig, wilt verwijderen, kiest u **Koppeling verwijderen**&gt;**OK**.

    -   Als u de computer aan een nieuwe gebruiker wilt koppelen, selecteert u een gebruiker in de lijst **Alle gebruikers** . Controleer of de gebruikersgegevens juist zijn en kies vervolgens **OK**.

> [!TIP]
> Als u de mogelijkheden van eindgebruikers om zichzelf aan computers te koppelen wilt beperken, schakelt u de optie **Koppelingen tussen gebruikers en computers beperken** in het beleid voor **Instellingen Microsoft Intune-agent** in.

<!--- ## Request and provide remote assistance to Windows PCs that use the Intune client software

> [!IMPORTANT]
> You might not see the options to configure TeamViewer integration for remote assistance in the Intune admin console. This capability is not currently available to all customers, but will be rolling our more widely soon.


Microsoft Intune can use the [TeamViewer](https://www.teamviewer.com) software to let users of PCs that run the Intune client software get remote assistance help from you. When a user requests help from the Microsoft Intune Center, you are informed by an alert, can accept the request, and then provide assistance.
This functionality replaces the existing Windows Remote Assistance functionality in Intune.


### Before you start

Before you begin to establish and respond to remote assistance requests, you must ensure the following prerequisites are in place:

- You must have [signed up for a TeamViewer account](https://login.teamviewer.com/LogOn#register) to log into the TeamViewer website.
- Windows PCs that you want to administer must be [managed by the Windows PC client](manage-windows-pcs-with-microsoft-intune.md)
- All Windows PC operating systems supported by Intune can be administered.

### Configure the TeamViewer Connector

1. In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Admin**.
2. In the **Admin** workspace, choose **TeamViewer**.
3. On the **TeamViewer** page, under **TeamViewer Connector**, choose **Enable**.
4. In the **Enable TeamViewer** dialog box, view, then **Accept** the license terms. If you don't already own a TeamViewer license, choose **Purchase a TeamViewer license**.
5. After the TeamViewer browser window opens, sign into the site with your TeamViewer credentials.
6. On the TeamViewer site, read, then accept the options to allow Intune to connect with TeamViewer.
7. In the Intune console, verify that the **TeamViewer Connector** item shows as **Enabled**.


### Open a remote assistance request (end user)

1. On a client Windows PC, open the **Microsoft Intune Center**.
2. Under **Remote Assistance**, choose **Request Remote Assistance**.
3. After you approve the request (see below), TeamViewer opens on the client. The user must accept any messages indicating that the web browser is trying to open the TeamViewer application.
4. The user sees a message asking if you can control their PC. They must accept this message to continue.
5. During the remote assistance session, the user sees a window that shows them you are connected. If they close this window, the remote session ends.

### Respond to a remote assistance request

1. When a user submits a remote assistance request, you can view it in the **Alerts** workspace, under **Monitoring** > **Remote Assistance**. For example:
> ![Screenshot of a remote assistance request](./media/team-viewer.png)

<br>If a request goes unanswered for more than 4 hours, it is removed.
2. To accept the request, choose **Approve request and launch Remote Assistance**.
3. In the **A New Remote Assistance Request is Pending** dialog box, choose **Accept the remote assistance request**. If it's not already installed, TeamViewer will install any necessary apps on your computer.
4. TeamViewer then notifies the end user that you want to take control of their PC. After the user has accepted the request, the TeamViewer windows opens, and you can control the PC.

While in a remote assistance session, you can use all available TeamViewer commands to control the remote PC. For help with these commands, download the [Manual for remote control](http://www.teamviewer.com/en/support/documents/) from the TeamViewer website.

### Close the remote assistance session

From the **Actions** menu of the **TeamViewer** window, choose **End Session**.--->



<!--HONumber=Jul16_HO4-->


