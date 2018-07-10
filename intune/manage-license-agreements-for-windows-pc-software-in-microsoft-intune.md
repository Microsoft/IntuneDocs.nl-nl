---
title: Softwarelicentieovereenkomsten voor pc's met de Intune-softwareclient beheren
titlesuffix: Microsoft Intune
description: Gebruik Intune om licentieovereenkomsten te beheren voor software die is gekocht via Microsoft-volumelicentieovereenkomsten en voor software die op een andere manier is gekocht.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c59d8635-3f66-40f5-824a-a71c738e0341
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic-keep
ms.openlocfilehash: 459e722e059d2d868c6de52bb11d5a2f52ce94c8
ms.sourcegitcommit: 116be0eaa44fd5518ff34780d39569224ef4746b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/21/2018
ms.locfileid: "36310586"
---
# <a name="manage-license-agreements-for-windows-pc-software-in-microsoft-intune"></a>Licentieovereenkomsten voor Windows-pc-software in Microsoft Intune beheren

[!INCLUDE [classic-portal](includes/classic-portal.md)]

Met Microsoft Intune kunt u licentiegegevens toevoegen en beheren voor software die is gekocht via Microsoft Volume Licensing-overeenkomsten. U kunt dit ook doen voor Microsoft- of niet-Microsoft-software die op een andere manier is gekocht. U kunt deze gegevens in logische groepen indelen.

> [!IMPORTANT]
> Deze functie is alleen voor uw gemak bedoeld; de nauwkeurigheid van de gegevens kan niet worden gegarandeerd. Het is niet verstandig deze functie te gebruiken om de naleving van Microsoft-volumelicentieovereenkomsten te bevestigen. Gegevens die worden verzameld, worden door Microsoft niet gebruikt voor het onderzoeken van mogelijke schendingen of de naleving van licentieovereenkomsten die u met ons hebt.
>
> Licenties die u toevoegt aan Intune, hebben geen invloed op uw licentieovereenkomsten of rechten om de software te gebruiken. Als u bijvoorbeeld een combinatie van licentie en overeenkomst uit Intune verwijdert, worden de bestaande licentieovereenkomsten tussen u en Microsoft niet verwijderd of ongeldig verklaard.

In de werkruimte **Licenties** van de Intune-beheerconsole kunt u:

-   Microsoft-volumelicentieovereenkomsten toevoegen en bewerken.

-   Andere softwarelicentieovereenkomsten toevoegen en bewerken.

-   Licenties en groepen beheren.

-   Vergelijk de informatie over rechten die door Intune bij het Volume Licensing Service Center (VLSC) is opgehaald, met de inventarisatie van Microsoft-software die door Intune is gedetecteerd op de beheerde Windows-computers.

U kunt bovendien rapporten genereren waarin statistieken voor software-installaties en -licenties worden weergegeven. Met licentierapporten kunt u al uw licenties voor Microsoft-software en niet-Microsoft-software inventariseren.

> [!TIP]
> De werkruimte **Licenties** wordt pas weergegeven in de beheerconsole als u ten minste één Windows-computer met de Intune Windows-computerclient beheert.

## <a name="add-microsoft-volume-licensing-agreements"></a>Microsoft-volumelicentieovereenkomsten toevoegen
Intune-volumelicentieovereenkomsten bieden licentie-informatie voor software die is gekocht via Microsoft-volumelicentieovereenkomsten. U kunt Microsoft-volumelicentieovereenkomsten aan Intune toevoegen door overeenkomende sets overeenkomstnummers op te geven. De overeenkomst- of autorisatienummers moeten overeenkomen met de juiste licentie- of inschrijvingsnummers. Sets overeenkomstnummers worden verkregen bij de aankoop van de licentieovereenkomsten van het [Volume Licensing Service Center (VLSC)](http://go.microsoft.com/fwlink/?LinkID=223842).

1.  Kies in de [Microsoft Intune-beheerconsole](https://account.manage.microsoft.com/admin/default.aspx) de optie **Licenties**.

2.  Selecteer op de pagina **Overeenkomsten toevoegen** in de sectie **Overeenkomsttype selecteren**de optie **Volumelicentieovereenkomst**.

3.  Geef in de sectie **Gegevens van overeenkomst toevoegen** op of u een bestand wilt uploaden of de gegevens handmatig wilt toevoegen.

    -   **Een CSV-bestand met overeenkomstgegevens uploaden**. Kies **Bladeren** en selecteer het CSV-bestand dat u wilt uploaden.

        -   Het bestand mag twee of drie kolommen bevatten; twee kolommen als u alleen sets overeenkomsten wilt toevoegen of drie kolommen als u voor elke set overeenkomsten een beschrijvende naam wilt toevoegen.

        -   Het totale aantal tekens in een set overeenkomstnummers mag niet meer zijn dan 16 ASCII-tekens.

        -   Alleen ASCII-tekens worden ondersteund.

        -   De volgende tekens zijn niet toegestaan in de naam van overeenkomst: **~ ! @ # $ ^ &amp; &#42; ( ) = + [ ] { } \ | ; : ' " &lt; &gt; /**. Spaties zijn toegestaan in de naam.

        -   De bestandsnaam mag niet meer dan 128 tekens bevatten.

        -   Het bestand moet ten minste één set overeenkomsten bevatten en mag niet meer dan 5000 sets overeenkomsten bevatten.

        **Indeling voor het bestand**

        U kunt dit bestand maken door uw sets van overeenkomsten toe te voegen aan een document met tekst zonder opmaak in een van de volgende notaties, afhankelijk van het type organisatie dat u bij VLSC hebt geregistreerd. Geef per regel één overeenkomstnummerpaar op.

        -   **Open Value-klanten:** *overeenkomstnummer*, *overeenkomstnummer herhalen*, *naam van de overeenkomst*

        -   **Open klanten:** *autorisatienummer*, *bijbehorend licentienummer*, *naam van de overeenkomst*

        -   **Select- en Enterprise-klanten:** *overeenkomstnummer*, *bijbehorend registratienummer*, *naam van de overeenkomst*

        Wanneer u een nieuwe overeenkomst toevoegt, wordt u in het formulier **Overeenkomsten toevoegen** gevraagd naar dit bestand te bladeren.

        Hieronder vindt u een voorbeeld van de inhoud van een .csv-bestand voor een Open Value-klant.

        `01-07001, 01-07001, Office agreements`

    -   **Gegevens van de overeenkomst handmatig toevoegen**. Geef de volgende informatie op en typ vervolgens de overeenkomstnummerset in de vakken **Autorisatie-/overeenkomstnummer** en **Licentie-/registratie-/klantnummer**. Nadat u de beide nummers hebt getypt, kiest u het pictogram **Set toevoegen** om de nummers op te slaan. Vervolgens kunt u indien gewenst een nieuwe set toevoegen.

        -   **Naam overeenkomst**: geef een unieke naam op voor de overeenkomst.

            De naam van een overeenkomst mag uit maximaal 256 tekens bestaan en mag niet de volgende tekens bevatten: **~ ! @ # $ ^ &amp; &#42; ( ) = + [ ] { } \ | ; : ' " &lt; &gt; /**. Spaties zijn toegestaan in de naam.

        -   **Autorisatie-/overeenkomstnummer**: voer het autorisatie-/overeenkomstnummer van de licentieset in.

        -   **Licentie-/inschrijvings-/klantnummer**: voer het licentie-/inschrijvings-/klantnummer van de licentieset in.

        > [!NOTE]
        > Als u meerdere sets overeenkomstnummers toevoegt, maakt Intune één overeenkomst met de naam die u opgeeft en worden alle sets die u hebt toegevoegd, opgenomen als onderdeel van deze overeenkomst.

    Kies **+** wanneer u nog een andere overeenkomstnummerset wilt toevoegen, of **-** als u een overeenkomstnummerset die u eerder hebt opgegeven, wilt verwijderen.

4.  In het gedeelte **Licentiegroep selecteren** voert u een van de volgende handelingen uit:

    -   **De overeenkomsten toevoegen aan de groep met niet-toegewezen overeenkomsten**. Selecteer deze optie als u de nieuwe overeenkomsten niet aan een licentiegroep wilt toevoegen.

    -   **De overeenkomsten toevoegen aan een nieuwe licentiegroep**. Geef een naam op voor de nieuwe licentiegroep.

    -   **De overeenkomsten toevoegen aan een bestaande licentiegroep**. In de lijst **Groepsnaam** selecteert u de licentiegroep waaraan u de overeenkomsten wilt toevoegen.

5.  Kies **OK**.

De weergave **Alle overeenkomsten** wordt weergegeven en Intune maakt verbinding met het Microsoft VLSC om de sets overeenkomstnummers die u hebt opgegeven, te valideren.

Als u de volumelicentiegegevens wilt bijwerken nadat u licentieovereenkomsten aan Intune hebt toegevoegd, kiest u op de pagina **Licentieoverzicht** de optie **Nu vernieuwen**. Hierdoor worden de huidige licentiegegevens van de [Microsoft Volume Licensing Service Center (VLSC)](http://go.microsoft.com/fwlink/?LinkId=223842)opgehaald.

> [!IMPORTANT]
> Totdat u de volumelicentiegegevens vernieuwt, ziet u op de de pagina **Overeenkomstenoverzicht** mogelijk verschillende gegevens in de lijst met overeenkomsten en rechteninformatie.

Na het vernieuwen van de volumelicentiegegevens kunt u de licentiegegevens vergelijken met de gedetecteerde Microsoft-software in de werkruimte **Apps** . U kunt ook de volgende licentierapporten uitvoeren:

-   **Licentie-inkooprapporten**: hiermee kunt u de gelicentieerde software weergeven in licentiegroepen die u selecteert om hiaten in de dekking op te sporen.

-   **Licentie-installatierapporten**: hiermee kunt u bepalen of de dekking van de licentieovereenkomst voldoende is.

> [!NOTE]
> De **producttitel** die wordt weergegeven voor alle Microsoft-volumelicentieovereenkomsten is **niet beschikbaar**.

## <a name="add-and-edit-other-software-licensing-agreements"></a>Andere softwarelicentieovereenkomsten toevoegen en bewerken
Naast Microsoft-volumelicentieovereenkomsten kunt u ook andere typen licentieovereenkomsten aan Intune toevoegen. Dit kunnen overeenkomsten zijn voor niet-Microsoft-software of voor Microsoft-software die via de detailhandel is gekocht.

> [!IMPORTANT]
> U moet ten minste één Windows-computer bij Intune hebben ingeschreven voordat u een overeenkomst kunt toevoegen.  Bovendien moet voor ten minste één ingeschreven computer een softwarepakket met licentie zijn geüpload dat u wilt gebruiken om een licentieovereenkomst toe te voegen.

### <a name="to-add-other-software-agreements"></a>Andere softwareovereenkomsten toevoegen

1.  Kies in de [Microsoft Intune-beheerconsole](https://account.manage.microsoft.com/admin/default.aspx) de optie **Licenties**.

2.  Kies **Overeenkomsten toevoegen** in de sectie **Andere softwarelicentieovereenkomsten**.

3.  Selecteer **Andere softwarelicentieovereenkomst** in de sectie **Overeenkomsttype selecteren** van de pagina **Overeenkomsten toevoegen** .

4.  Geef in het gedeelte **Gegevens van overeenkomst toevoegen** het volgende op:

    -   **Agreement name** (vereist). De naam van een overeenkomst mag uit maximaal 256 tekens bestaan en mag niet de volgende tekens bevatten: **~ ! @ # $ ^ &amp; &#42; ( ) = + [ ] { } \ | ; : ' " &lt; &gt; /**. Spaties zijn toegestaan in de naam.

    -   **Uitgever** (vereist). Terwijl u de naam van een uitgever typt, worden alle namen van uitgevers opgehaald die de door u getypte letters bevatten. Als u bijvoorbeeld 'soft' typt, worden alle namen opgehaald van uitgevers die 'soft' bevatten, bijvoorbeeld 'Microsoft' en 'Microsoft Research.' De namen van de uitgevers worden opgehaald uit de Software Asset Catalog. Voordat u de titel van het product kunt invoeren, moet u de uitgever selecteren.

        > [!IMPORTANT]
        > Het bedrijf dat u wilt toevoegen, wordt mogelijk niet in deze lijst weergegeven. U kunt alleen softwareovereenkomsten toevoegen voor bedrijven die al voorkomen in Software Asset Catalog. Microsoft probeert echter doorlopend om de meest populaire softwaretitels toe te voegen. Als u een aanvraag wilt indienen om een bedrijf aan deze lijst toe te voegen, kunt u dat doen op de [Intune Uservoice-site](https://microsoftintune.uservoice.com/).

    -   **Producttitel** (vereist). Terwijl u de producttitel typt, worden alle producttitels opgehaald die de door u getypte letters bevatten. U moet een **Publisher** opgeven voordat u een **producttitel**kunt opgeven.

    -   **Aantal licenties** (vereist). Voer het aantal aangekochte licenties in.

    -   **Begindatum licentie**. Voer de begindatum van de licentiedekking in.

    -   **Einddatum licentie**. Voer de einddatum van de licentiedekking in.

    -   **Details overeenkomst**. Indien gewenst kunt u contactgegevens, registratiesleutels en andere informatie opgeven.

5.  In het gedeelte **Licentiegroep selecteren** voert u een van de volgende handelingen uit:

    -   Selecteer **De overeenkomsten toevoegen aan de groep met niet-toegewezen overeenkomsten** als u de nieuwe overeenkomsten niet wilt toevoegen aan een nieuwe of bestaande licentiegroep. U kunt de overeenkomsten op elk gewenst moment toevoegen aan de door de gebruiker gedefinieerde licentiegroepen.

    -   Selecteer **De overeenkomsten toevoegen aan een nieuwe licentiegroep** als u de nieuwe overeenkomsten wilt toevoegen aan een nieuwe licentiegroep. U wordt gevraagd een naam voor de nieuwe licentiegroep op te geven.

    -   Selecteer **De overeenkomsten toevoegen aan een bestaande licentiegroep** als u de nieuwe overeenkomsten wilt toevoegen aan een bestaande licentiegroep. In de lijst **Groepsnaam** selecteert u de licentiegroep waaraan u de overeenkomsten wilt toevoegen.

6.  Kies **OK**.

De lijstweergave **Alle overeenkomsten** wordt weergegeven.

## <a name="manage-license-agreements"></a>Licentieovereenkomsten beheren
Softwarelicentieovereenkomsten kunnen worden toegevoegd aan licentiegroepen. U kunt licentiegroepen gebruiken om uw licentieovereenkomsten te organiseren in groepen die logisch zijn voor uw organisatie. U kunt ook licentieovereenkomsten verwijderen die u eerder hebt gemaakt.


|                            |                                                                                                                                                                                                                                                                                                                                                                          |
|----------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|            Taak            |                                                                                                                                                                                 Details                                                                                                                                                                                  |
|   Een licentiegroep maken   |                                                            Kies op de pagina <strong>Overzicht</strong> in de werkruimte <strong>Licenties</strong> de optie <strong>Licentiegroep maken</strong> in het menu <strong>Taken</strong>. <strong>Opmerking</strong>: u kunt maximaal 500 licentiegroepen maken.                                                             |
|   De naam van een licentiegroep wijzigen   |                                                                                                      Kies in de werkruimte <strong>Licenties</strong> een licentiegroep en kies dan <strong>Licentiegroep bewerken</strong> in het menu <strong>Taken</strong> .                                                                                                       |
|   Een licentiegroep verwijderen   |                                 Kies in de werkruimte <strong>Licenties</strong> een licentiegroep en kies dan <strong>Licentiegroep verwijderen</strong> in het menu <strong>Taken</strong> . <strong>Tip:</strong> alle licenties in de verwijderde groep worden verplaatst naar de licentiegroep <strong>Niet-toegewezen overeenkomsten</strong>.                                 |
| Een licentieovereenkomst verwijderen | Kies in de werkruimte <strong>Licenties</strong> een overeenkomst en kies vervolgens <strong>Verwijderen</strong>. <strong>Tip:</strong> nadat u volumelicentieovereenkomsten hebt verwijderd, kiest u voor het bijwerken van de licentiegegevens de optie <strong>Nu vernieuwen</strong> op de pagina <strong>Licentieoverzicht</strong> of op het tabblad <strong>Algemeen</strong> voor een specifieke licentiegroep. |

