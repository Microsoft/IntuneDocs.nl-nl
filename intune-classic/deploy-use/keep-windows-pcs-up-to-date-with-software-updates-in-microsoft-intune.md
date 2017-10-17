---
title: Software-updates voor Windows-pc's
description: "Intune houdt uw beheerde computers bijgewerkt door ervoor te zorgen dat de meest recente patches en software-updates snel worden geïnstalleerd."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 48e9c41a-d2de-424e-9610-cfd1ad514210
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 85299c97c2b0c605adbb83a7c6e8017360511609
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/10/2017
---
# <a name="keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune"></a>Windows-pc’s up-to-date houden met software-updates in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Met Microsoft Intune kunt u beheerde computers op een aantal manieren helpen beveiligen. Zo kunt u software-updates beheren die de computers up-to-date houden door ervoor te zorgen dat de nieuwste patches en software-updates snel worden geïnstalleerd.

Zie [De Windows-pc-client installeren met Windows Intune](install-the-windows-pc-client-with-microsoft-intune.md) als u de Intune-client nog niet op uw computers hebt geïnstalleerd.

Wanneer er nieuwe updates beschikbaar zijn via Microsoft Update, of als u een update van derden hebt gemaakt, en als deze updates van toepassing zijn op de beheerde computers, wordt er een melding weergegeven op de pagina **Overzicht** in de werkruimte **Updates**. Als u op deze meldingskoppeling klikt, kunt u verschillende acties uitvoeren, zoals meer informatie over de update bekijken, de update goedkeuren of weigeren, en de computers weergeven waarop de update wordt geïnstalleerd nadat deze is goedgekeurd.

> [!IMPORTANT]
> De werkruimte **Updates** wordt pas weergegeven in de beheerconsole nadat u de client hebt geïnstalleerd op ten minste één clientcomputer die u beheert.

Nadat updates zijn goedgekeurd en geïnstalleerd, kunt u in de werkruimte **Updates** van de Intune-console controleren of de installatie geslaagd is of mislukt.

In de volgende secties vindt u informatie om de software op de beheerde computers up-to-date te houden.

## <a name="before-you-start"></a>Voordat u begint
Configureer en implementeer beleidsregels voor uw computers om te bepalen wanneer en hoe updates worden geïnstalleerd, voordat u begint met het maken en goedkeuren van software-updates.

### <a name="to-configure-update-policy-settings"></a>Instellingen voor updatebeleid configureren

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) de optie **Beleid** &gt; **Overzicht** &gt; **Beleid toevoegen**.

2.  Configureer en implementeer een beleid **Instellingen Microsoft Intune-agent** voor de update-instellingen. U kunt de aanbevolen instellingen gebruiken of de instellingen aanpassen. Als u meer informatie wilt over het maken en implementeren van beleid, raadpleegt u [Algemene beheertaken voor Windows-pc's met de Microsoft Intune-computerclient](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).

De volgende tabel biedt een overzicht van de waarden die u kunt configureren in het beleid, evenals de aanbevolen waarden die worden gebruikt als u het beleid niet aanpast. U vindt deze instellingen in de sectie **Updates**.

  |Beleidsinstelling|Details|
    |------------------|--------------------|
    |**Detectiefrequentie in uren van updates en toepassingen** |Hiermee geeft u het interval aan (tussen 8 en 22 uur) tussen opeenvolgende controles van Intune op nieuwe updates en toepassingen.<br /><br />Aanbevolen waarde: **8** uur.|
    |**Updates en toepassingen automatisch of na bevestiging installeren** |Geeft aan dat updates automatisch worden geïnstalleerd of dat de gebruiker om bevestiging wordt gevraagd voordat de installatie wordt uitgevoerd. Bovendien kunt u met deze instelling de installatie van updates en toepassingen plannen.<br /><br />Met **Updates en toepassingen automatisch installeren zoals gepland** worden updates en toepassingen geïnstalleerd op basis van de ingestelde planning.<br /><br />Als afhankelijke beleidsinstelling bepaalt **Automatische onderhoud voor Windows-computers gebruiken**  dat updates en toepassingen worden geïnstalleerd tijdens de periode voor automatisch onderhoud van Windows.<br /><br />Met **Gebruiker vragen voor installatie** wordt de gebruiker gevraagd om updates te installeren wanneer deze gereed zijn.<br /><br />Aanbevolen waarden:<br /><br />**Updates en applicaties automatisch installeren zoals gepland** is geselecteerd<br /><br />**Geplande dag: elke dag**<br /><br />**Geplande tijd: 3:00 uur**<br /><br />**Automatisch onderhoud voor Windows-computers gebruiken** is geselecteerd|
    |**Directe installatie toestaan van updates die Windows niet onderbreken** |Met **Toestaan** worden updates onmiddellijk geïnstalleerd nadat ze zijn gedownload, met uitzondering van updates waarvoor Windows wordt onderbroken of opnieuw moet worden gestart. Deze updates worden geïnstalleerd volgens de configuratie van de instelling **Updates en toepassingen automatisch of na vragen aan gebruiker installeren** .<br /><br />Met **Niet toestaan** worden updates geïnstalleerd volgens de configuratie van de instelling **Updates en toepassingen automatisch of na vragen aan gebruiker installeren**.<br /><br />Aanbevolen waarde: **Toestaan** |
    |**Windows opnieuw starten uitstellen na installatie van geplande updates en toepassingen (minuten)** |Geeft aan hoe lang (van 1 tot 30 minuten) moet worden gewacht om Windows opnieuw te starten na de installatie van geplande updates en toepassingen.<br /><br />Aanbevolen waarde: **15 minuten** |
    |**Vertraging in minuten na het opnieuw starten van Windows voordat de installatie van overgeslagen geplande updates en toepassingen wordt gestart** |Geeft aan hoe lang (van 1 tot 60 minuten) moet worden gewacht om de installatie van updates en toepassingen te starten nadat Windows opnieuw is gestart, als een geplande update is overgeslagen.<br /><br />Aanbevolen waarde: **5 minuten**|
    |**Aangemelde gebruiker mag bepalen wanneer Windows opnieuw wordt gestart na installatie van geplande updates en toepassingen** |Hiermee geeft u aan dat de aangemelde gebruiker het opnieuw starten van Windows kan uitstellen (indien ingesteld op **Ja**), of dat er wordt gemeld dat Windows automatisch opnieuw wordt gestart (indien ingesteld op **Nee**). Als er geen gebruiker is aangemeld wanneer de geplande installatie van updates en toepassingen is voltooid, wordt Windows indien nodig automatisch opnieuw gestart. Als **Nee**is geselecteerd, wordt Windows standaard opnieuw gestart na 5 minuten.<br /><br />Aanbevolen waarde: **Ja**|
    |**Gebruiker vragen Windows opnieuw te starten tijdens verplichte updates van de Intune-clientagent** |Hiermee geeft u aan of aangemelde gebruikers wordt gevraagd Windows opnieuw te starten wanneer dit is vereist vanwege een verplichte update van de Intune-client.<br /><br />Aanbevolen waarde: **Ja**|
    |**Installatieschema voor verplichte updates van Microsoft Intune-clientagent** |Bepaalt wanneer de installatie van clientupdates wordt uitgevoerd.<br /><br />Aanbevolen waarde: niet geconfigureerd|
    |**Vertraging in minuten tussen prompts om Windows opnieuw te starten na de installatie van geplande updates en toepassingen** |Geeft het interval aan (minimaal 1 minuut en maximaal 1440 minuten) tussen opeenvolgende vragen om Windows opnieuw te starten wanneer een geplande update of toepassing waarvoor Windows opnieuw moet worden gestart, is geïnstalleerd en de gebruiker het opnieuw starten uitstelt.<br /><br />Aanbevolen waarde: **30 minuten** |

## <a name="update-software-made-by-microsoft"></a>Software bijwerken die is gemaakt door Microsoft
U hoeft zelf niet veel te doen om Microsoft-software bij te werken. Voordat u begint, zijn er echter twee instellingen die u moet configureren:

-   **Productcategorieën en updateclassificaties** – Bepaalt de categorieën en classificaties van de updates die u beschikbaar wilt maken voor computers. U kunt bijvoorbeeld bepalen dat alleen essentiële updates voor Microsoft Office worden geïnstalleerd.

-   **Automatische goedkeuringsregels** – Deze regels keuren opgegeven updatetypen automatisch goed en reduceren uw administratieve overhead. U kunt bijvoorbeeld automatisch alle essentiële software-updates goedkeuren.

Met de volgende twee procedures kunt u zich voorbereiden op het gebruik van software-updates:

### <a name="configure-the-product-categories-and-update-classifications-you-want-to-make-available-to-managed-computers"></a>De productcategorieën en updateclassificaties configureren die u beschikbaar wilt maken voor beheerde computers

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) **Beheer** &gt; **Updates**.

2.  Selecteer op de pagina **Service-instellingen: updates** in de lijst **Productcategorie** de updatecategorieën die u beschikbaar wilt maken voor alle computers. De meest voorkomende updates zijn standaard al ingeschakeld.

    > [!IMPORTANT]
    > Als u ervoor wilt zorgen dat computers de updates ontvangen die zijn goedgekeurd door de beheerder, mag de instelling voor Groepsbeleid van WSUS (Windows Server Update Services), **Locatie van Microsoft-updateservice in intranet** niet worden toegepast op computers die zijn ingeschreven met Intune.

3.  Selecteer in de lijst **Updateclassificatie** de updateklassen die u beschikbaar wilt maken voor beheerde computers. Ook hier zijn de meest voorkomende opties standaard al geselecteerd.

4.  Klik op **Opslaan** om uw selecties op te slaan.

### <a name="to-configure-automatic-approval-rules-for-software-updates"></a>Automatische goedkeuringsregels voor software-updates configureren

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) **Beheer** &gt; **Updates**.

2.  Kies in de sectie **Automatische goedkeuringsregels** van de pagina **Service-instellingen: updates** de optie **Nieuw**.

3.  Geef op de pagina **Algemeen** van de wizard Automatische goedkeuringsregel maken een naam en optionele beschrijving voor de regel op.

4.  Selecteer op de pagina **Productclassificaties** alle producten waarvoor u updates automatisch wilt goedkeuren.

5.  Geef op de pagina **Updateclassificaties** de updateclassificaties op die u automatisch wilt goedkeuren.

6.  Doe het volgende op de pagina **Implementatie** :

    -   Selecteer de computergroepen waarvoor u de nieuwe regel wilt implementeren en kies vervolgens **Toevoegen**.

    -   Als u een installatiedeadline voor de updates wilt opgeven, schakelt u het selectievakje **Dwing een installatiedeadline af voor deze updates af** in en selecteert u vervolgens de gewenste deadline in de lijst **Installatiedeadline** .

        > [!NOTE]
        > Als u een installatiedeadline opgeeft, moet de beheerde computer mogelijk een of meer keer opnieuw worden opgestart nadat het deadline-interval is verstreken.

    -   Als u klaar bent, kiest u **Volgende**.

7.  Bekijk op de pagina **Samenvatting** de instellingen voor de nieuwe regel en kies vervolgens **Voltooien**.

De nieuwe regel wordt weergegeven in de sectie **Automatische goedkeuringsregels** van de pagina **Service-instellingen: updates**.

> [!NOTE]
> Wanneer u een automatische goedkeuringsregel maakt, worden alleen toekomstige updates goedgekeurd. Eerdere updates die al bestaan in Intune, worden niet automatisch goedgekeurd. Als u ook deze updates wilt goedkeuren, moet u de automatische goedkeuringsregel uitvoeren.


### <a name="to-edit-run-or-delete-an-automatically-approved-update-rule"></a>Een automatische goedkeuringsregel voor updates bewerken, uitvoeren of verwijderen

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) **Beheer** &gt; **Updates**.

2.  Selecteer een regel in de sectie **Automatische goedkeuringsregel** en voer een van de volgende handelingen uit:

    -   Als u de regel wilt bewerken, kiest u **Bewerken** en wijzigt u vervolgens de parameters voor de regel in de **wizard Automatische goedkeuringsregel bijwerken**.

    -   Kies **Geselecteerde uitvoeren** om de regel uit te voeren.

    -   Als u de regel wilt verwijderen, kiest u **Verwijderen**.

        > [!NOTE]
        > Het verwijderen van een regel is niet van invloed op eerdere updates die zijn goedgekeurd door de verwijderde regel.

## <a name="update-software-not-made-by-microsoft"></a>Software bijwerken die niet door Microsoft is gemaakt
U kunt ook updates implementeren voor software die niet door Microsoft is gemaakt. U kunt hiervoor de wizard **Update uploaden** gebruiken om de update naar uw opslagruimte in de cloud te verplaatsen. Vervolgens kunt u de update goedkeuren of weigeren net zoals voor de software van Microsoft.

### <a name="to-upload-and-configure-a-third-party-update"></a>Updates van derden uploaden en configureren

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) **Updates** &gt; **Overzicht** &gt; **Uploaden**.

2.  Kies op de pagina **Updatebestanden** de optie **Bladeren** om de setup-bestanden te selecteren die nodig zijn om het updatepakket te installeren. Het bestand kan een Windows Installer-bestand (.msi), een Windows Installer-patchbestand (.msp) of een programmabestand (.exe) zijn. U kunt ook aanvullende bestanden en mappen uit dezelfde map als het setup-bestand opnemen.

    Vervolgens wordt de totale uploadgrootte van de geselecteerde bestanden weergegeven. Deze grootte houdt geen rekening met de niet-gecomprimeerde of uitgevouwen grootte van de installatiebestanden.

3.  Nadat u de setup-bestanden hebt opgegeven, wordt op de pagina **Beschrijving van update** de naam, de beschrijving en de classificatie van de software weergegeven die met Intune is geëxtraheerd uit de setup-bestanden van de software. U kunt een classificatie selecteren om het updatetype te labelen dat u implementeert (Updates, Essentiële Updates, Beveiligingsupdates, Updatepakketten of Servicepacks). Kies **Volgende** wanneer u klaar bent.

4.  Kies op de pagina **Vereisten** van de wizard de architectuur (32 bits, 64 bits of beide) en de besturingssystemen van de beheerde computers waarop deze update van toepassing is.

5.  Geef op de pagina **Detectieregels** op hoe in Intune kan worden bepaald of de update al bestaat op beheerde computers. Als u gebruikmaakt van de standaardoptie **De standaarddetectieregels gebruiken**, wordt met Intune het updatepakket altijd één keer geïnstalleerd op elke doelcomputer.

    > [!NOTE]
    > Als het setup-bestand dat u voor de update hebt opgegeven, een Windows Installer- of MSP-bestand is, wordt de pagina **Detectieregels** van de wizard niet weergegeven. Windows Installer- en MSP-bestanden bevatten hun eigen instructies voor het detecteren van eerdere update-installaties.

    Selecteer een of meer van de volgende regels om te bepalen of de update al is geïnstalleerd op beheerde computers:

    -   **Bestand bestaat al**

    -   **MSI-productcode bestaat al**

    -   **Registersleutel bestaat**

6.  Geef alle overige informatie op die nodig is om de detectieregel te configureren, zoals een bestandspad en -naam, de productcode van Windows Installer of een registersleutel, en kies **Volgende**.

7.  Geef op de pagina **Vereisten** de software op die al moet zijn geïnstalleerd voordat deze update kan worden geïnstalleerd. U kunt **Geen** kiezen, een softwarepakket selecteren dat al is toegevoegd aan en wordt beheerd in Intune, of een van de volgende regels opgeven om de software te beschrijven:

    -   **Bestand bestaat al**

    -   **MSI-productcode bestaat al**

    -   **Registersleutel bestaat**

8.  Geef alle overige informatie op die nodig is om de detectieregel te configureren, zoals een bestandspad en -naam, de productcode van Windows Installer of een registersleutel, en kies **Volgende**.

9. Op de pagina **Opdrachtregelargumenten** van de wizard kunt u de vereiste eigenschappen voor de installatie toevoegen aan de opdrachtregel voor de installatie om het gedrag van het setup-bestand te wijzigen. Sommige software ondersteunt bijvoorbeeld de eigenschap **/q** voor een stille installatie. Raadpleeg de documentatie bij uw softwarepakket voor meer informatie over alle ondersteunde opdrachtregelargumenten. Geef de benodigde opdrachtregelargumenten op en kies **Volgende**.

    > [!NOTE]
    > Als de update geen ondersteuning biedt voor een stille installatie, kunt u de update niet installeren met Intune

10. Op de pagina **Retourcodes** kunt u opgeven hoe de installatieretourcodes van de update worden geïnterpreteerd. In Intune worden standaard retourcodes volgens de industrienorm gebruikt om een mislukte of geslaagde installatie van een updatepakket te melden. De opgegeven retourcodes zijn:

|Retourcode|Details|
|---------------|------------------|
|**0**|Geslaagd|
|**3010**|Geslaagd en opnieuw opgestart|

11. Een retourcode die niet wordt vermeld, wordt als een fout geïnterpreteerd.
Sommige updates gebruiken niet-standaard interpretaties voor retourcodes. In dit geval kunt u uw eigen interpretatie voor de retourcode opgeven.

12. Bewerk de vereiste retourcodes of geef deze op en klik vervolgens op **Volgende**.

13. Bekijk op de pagina **Samenvatting** van de wizard de acties die worden uitgevoerd en kies **Uploaden** om de wizard te voltooien.

De geüploade update wordt opgeslagen in de cloudopslag van uw Intune-account. Als u over onvoldoende schijfruimte beschikt om het app-pakket te uploaden, ontvangt u daar tijdens het uploaden een melding over. Er kan pas worden bepaald of er in Intune voldoende vrije ruimte is nadat het uploaden van de update is gestart, omdat gecomprimeerde setup- en installatiebestanden meer ruimte nodig hebben wanneer ze niet zijn gecomprimeerd.

Nadat de update is geüpload naar Intune, wordt in de werkruimte **Updates** van het deelvenster **Alle updates** een update van derden weergegeven. U kunt de update vervolgens goedkeuren en implementeren. Zie de volgende sectie Updates goedkeuren en weigeren voor meer informatie.

## <a name="approve-and-decline-updates"></a>Updates goedkeuren en weigeren
Wanneer updates gereed zijn om te worden geïnstalleerd, wordt op de pagina **Overzicht** in de werkruimte **Updates** een bericht weergegeven onder **Updatestatus**. Kies dit bericht om de pagina **Alle updates** te openen en te controleren welke updates klaar zijn om te worden goedgekeurd.

U kunt de vervolgkeuzelijst **Filters** gebruiken om updates makkelijker te vinden. Zo kunt u bijvoorbeeld eenvoudig alleen de updates weergeven die zijn mislukt of alleen de updates die zijn vervangen.

Wanneer u een update uit de lijst selecteert, zijn opdrachten beschikbaar waarmee u updates kunt beheren, zoals wordt beschreven in de volgende tabel:

|Taak|Details|
|--------|--------------------|
|**Eigenschappen weergeven**|Gedetailleerde informatie weergeven over de update waaronder het aantal computers waarop deze van toepassing is.|
|**Bewerken**|Alleen voor niet-Microsoft-updates. Hiermee kunt u de eigenschappen voor de update bewerken.|
|**Goedkeuren**|De geselecteerde update goedkeuren en configureren voor welke groepen de update wordt geïmplementeerd. Zie de procedure **Updates goedkeuren** in dit onderwerp voor meer informatie.|
|**Weigeren**|Alle eerdere goedkeuringen voor de update verwijderen en de update verbergen in de standaardweergaven. Bovendien worden alle rapportgegevens voor de update verwijderd.<br /><br />Als u een geweigerde update later wilt vinden, stelt u het filter op de pagina **Alle updates** in op **Geweigerd**. Vervolgens kunt u deze update zo nodig goedkeuren.<br /><br />Als een update is geweigerd omdat de update in Microsoft Update is verlopen, kan deze update niet worden goedgekeurd in de Intune-beheerconsole.<br /><br />Als u een updatebeleid verwijdert dat is geïmplementeerd op computers, worden de waarden van de beleidsinstellingen voor updates opnieuw ingesteld op de standaardstatus voor het besturingssysteem dat is geïnstalleerd op de computers.|
|**Verwijderen**|Alleen voor niet-Microsoft-updates. De geselecteerde update verwijderen.|
|**Uploaden**|Hiermee start u de wizard **Update uploaden**, waarmee u niet-Microsoft-updates kunt uploaden die u wilt implementeren.|

### <a name="to-approve-updates"></a>Updates goedkeuren

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) **Updates** &gt; **Overzicht** &gt; **Nieuwe goed te keuren updates**.

    Kies in de werkruimte **Updates** **Overzicht** &gt; **Nieuwe goed te keuren updates**.

    > [!NOTE]
    > De koppeling **Nieuwe goed te keuren updates** wordt alleen in het venster **Updatestatus** weergegeven als er ten minste één beheerde computer is waarvoor een update moet worden goedgekeurd.

2.  Selecteer een update, controleer onder aan de pagina de eigenschappen van de update om er zeker van te zijn dat u de update wilt goedkeuren, en kies vervolgens **Goedkeuren**. U kunt meerdere updates selecteren door de **Ctrl**-toets ingedrukt te houden terwijl u elk item selecteert.

3.  Selecteer op de pagina **Groepen selecteren** een groep waarvoor u de updates wilt implementeren, en kies **Toevoegen**. Wanneer u de gewenste groepen hebt opgegeven, kiest u **Volgende**.

4.  Voer op de pagina **Implementatieactie** de volgende stappen uit voor elke groep in de lijst:

    -   Selecteer in de lijst **Goedkeuring** een van de volgende opties:

        -   **Vereiste installatie**: de update wordt geïnstalleerd op computers in de opgegeven groep.

        -   **Niet installeren**: er wordt alleen gemeld dat de update van toepassing is, maar de update wordt niet geïnstalleerd.

        -   **Beschikbare installatie**: de gebruiker kan de toepassing op verzoek installeren uit de bedrijfsportal.

        -   **Verwijderen**: updates worden verwijderd van computers in de doelgroep.

            > [!IMPORTANT]
            > De update wordt verwijderd, ook als deze niet is geïnstalleerd met Intune.

    -   Selecteer in de lijst **Deadline** een van de volgende opties:

        -   **Geen**: er wordt geen deadline afgedwongen voor de installatie van de update en gebruikers kunnen de update voortdurend weigeren.

        -   **Zo spoedig mogelijk**: de update wordt bij de eerstvolgende gelegenheid op de doelcomputers geïnstalleerd.

        -   **Aangepast**: hiermee geeft u de datum en tijd op waarop goedgekeurde updates worden geïnstalleerd.

        -   **Een week**, **Twee weken**, **Een maand**: de update wordt binnen de opgegeven periode geïnstalleerd.

5.  Klik op **Voltooien** om de instellingen op te slaan of kies **Annuleren** om de instellingen te negeren en terug te keren naar de lijst met updates.

    > [!IMPORTANT]
    > Tenzij de actie **Niet van toepassing**, **Vereiste installatie**of **Verwijderen** expliciet is geconfigureerd voor een onderliggende groep, wordt een actie die is geconfigureerd voor een bovenliggende groep overgenomen door alle onderliggende groepen.

6.  Controleer het detailvenster onder aan de pagina **Alle updates** op herinneringsberichten voor de update.


### <a name="see-also"></a>Zie tevens
[Beleid voor het beveiligen van Windows-pc's](policies-to-protect-windows-pcs-in-microsoft-intune.md)
