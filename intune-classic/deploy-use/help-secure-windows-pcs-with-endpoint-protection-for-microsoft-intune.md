---
title: Endpoint Protection voor Windows-pc’s
description: Beveilig uw beheerde computers met Endpoint Protection voor realtime-beveiliging tegen malwarebedreigingen.
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 03/06/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 002241bf-6cd0-4c75-a4f0-891ac7e6721a
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 72a4e977f88a7f397d4f37f723ca1f13c4bc689c
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune"></a>Help Windows-pc's beveiligen met Endpoint Protection Help voor Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Microsoft Intune kunt u uw beheerde computers met Endpoint Protection beschermen. Dit biedt realtime-beveiliging tegen malwarebedreigingen, houdt malwaredefinities bijgewerkt en scant computers automatisch. Ook biedt Endpoint Protection hulpmiddelen waarmee u malware-aanvallen kunt beheren en controleren.

Zie [De Windows-pc-client installeren met Windows Intune](install-the-windows-pc-client-with-microsoft-intune.md) als u de Intune-client nog niet op uw computers hebt geïnstalleerd.

Gebruik de informatie in de volgende rubrieken voor hulp bij het configureren, implementeren en controleren van Endpoint Protection.

## <a name="choose-when-to-use-endpoint-protection"></a>Kiezen wanneer u Endpoint Protection wilt gebruiken
Als IT-beheerder is een van uw eerste prioriteiten de computers die u beheert vrij te houden van malware en virussen staat. Voordat u Intune op Windows-pc’s in uw organisatie implementeert, moet u bepalen hoe u uw computers beveiligt door een van de volgende opties te selecteren en de bijbehorende beleidsinstellingen te configureren:


|                                                                                                                                                                       U wilt:                                                                                                                                                                        |                                                                                                       Endpoint Protection-beleidsinstellingen                                                                                                        |                                                                                                                                                  Meer informatie                                                                                                                                                  |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                             Gebruik Microsoft Intune Endpoint Protection alleen als er geen eindpuntbeveiligingstoepassing van derden is geïnstalleerd.<br /><br />U kunt Microsoft Intune Endpoint Protection gebruiken op alle computers waarop geen eindpuntbeveiligingstoepassing van derden is geïnstalleerd.                                              | Endpoint Protection installeren = <strong>Ja</strong><br /><br />Endpoint Protection inschakelen = <strong>Ja</strong><br /><br />Endpoint Protection installeren, zelfs als er een eindpuntbeveiligingstoepassing van derden is geïnstalleerd = <strong>Nee</strong>  |                                                                      Als een eindpuntbeveiligingstoepassing van derden wordt gedetecteerd, wordt Microsoft Intune Endpoint Protection niet geïnstalleerd of wordt de installatie ongedaan gemaakt als het programma al is geïnstalleerd.                                                                       |
| Microsoft Intune Endpoint Protection gebruiken, zelfs als een eindpuntbeveiligingstoepassing van derden is geïnstalleerd.<br /><br />Met deze methode voert u Microsoft Intune Endpoint Protection en de eindpuntbeveiligingstoepassing van derden tegelijkertijd uit. Deze configuratie wordt afgeraden, omdat zich prestatieproblemen kunnen voordoen. | Endpoint Protection installeren = <strong>Ja</strong><br /><br />Endpoint Protection inschakelen = <strong>Ja</strong><br /><br />Endpoint Protection installeren, zelfs als er een eindpuntbeveiligingstoepassing van derden is geïnstalleerd = <strong>Ja</strong> |                        Gebruiken wanneer:<br /><br />- U wilt overschakelen op het gebruik van Microsoft Intune Endpoint Protection.<br />- U een nieuwe client met Microsoft Intune Endpoint Protection implementeert.<br />- U een client bijwerkt met Microsoft Intune Endpoint Protection.                         |
|                                                                                                             Gebruik Intune zonder Microsoft Intune Endpoint Protection. In plaats daarvan vertrouwt u op een eindpuntbeveiligingstoepassing van derden.                                                                                                             |                                                                                                Endpoint Protection installeren = <strong>Nee</strong>                                                                                                 | Als u geen eindpuntbeveiligingstoepassing van derden gebruikt, wordt deze configuratie afgeraden. De computers worden namelijk blootgesteld aan malware of andere aanvallen.<br /><br />Microsoft Intune Endpoint Protection wordt niet geïnstalleerd of wordt verwijderd als het al is geïnstalleerd. |

Als u van uw huidige eindpuntbeveiligingstoepassing wilt overschakelen op Microsoft Intune Endpoint Protection, gaat u als volgt te werk:

1.  Houd uw huidige eindpuntbeveiligingstoepassing actief, terwijl u de Intune-clientsoftware op de betreffende computers implementeert.

2.  Controleer of Microsoft Intune Endpoint Protection is geïnstalleerd en u helpt bij de beveiliging van clientcomputers.

3.  Verwijder de eindpuntbeveiligingssoftware van derden door:

    -   Intune-softwaredistributie te gebruiken om een softwareverwijderingshulpmiddel te implementeren dat is geleverd door de fabrikant van de eindpuntbeveiligingstoepassing van derden. Zie [Apps implementeren met Microsoft Intune](deploy-apps.md) voor meer informatie.

    -   De eindpuntbeveiligingstoepassing van derden handmatig te verwijderen.

> [!NOTE]
> Intune verwijdert eindpuntbeveiligingstoepassingen van derden niet automatisch.

## <a name="configure-microsoft-intune-endpoint-protection"></a>Microsoft Intune Endpoint Protection configureren
Gebruik de volgende stappen om u te helpen bij het configureren van Endpoint Protection voor Microsoft Intune.

1.  Ga naar de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) en kies **Beleid** > **Beleid toevoegen**.

2.  Vouw **Computerbeheer** uit en selecteer **Instellingen Microsoft Intune-agent**. Selecteer **Aangepast beleid maken en implementeren** om beleid op te geven voor Endpoint Protection-instellingen. Klik vervolgens op de knop **Beleid maken**.

U kunt de aanbevolen instellingen gebruiken of de instellingen aanpassen. Als u meer informatie wilt over het maken en implementeren van beleid, raadpleegt u het onderwerp [Algemene beheertaken voor Windows-pc’s met de Microsoft Intune-computerclient](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).

  ![Instellingen voor Endpoint Protection](./media/pol-sa-pc-endpoint-policy.png)

U kunt het geïmplementeerde Endpoint Protection-beleid zien op de pagina **Alle beleidsregels** van de werkruimte **Beleid**.

## <a name="specify-endpoint-protection-service-settings"></a>Instellingen van Endpoint Protection-service opgeven

|                                                 Beleidsinstelling                                                  |                                                                                                                                                                                                                                                                                                                                                                                                             Details                                                                                                                                                                                                                                                                                                                                                                                                             |
|-----------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                  <strong>Endpoint Protection installeren</strong>                                   | Ingesteld op <strong>Ja</strong> om Endpoint Protection op beheerde computers te installeren. Als er een eindpuntbeveiligingstoepassing van derden wordt gedetecteerd tijdens de installatie, wordt Endpoint Protection niet geïnstalleerd, tenzij de instelling <strong>Endpoint Protection installeren, zelfs als er een eindpuntbeveiligingstoepassing van derden is geïnstalleerd</strong> is ingesteld op <strong>Ja</strong>. <strong>Opmerking:</strong> Intune Endpoint Protection wordt standaard op beheerde computers geïnstalleerd. Als u Endpoint Protection niet op uw beheerde computers wilt installeren, moet u dit beleid expliciet instellen op <strong>Nee</strong>. Als Endpoint Protection eerder is geïnstalleerd en het beleid wordt bijgewerkt naar <strong>Nee</strong>, wordt de Endpoint Protection-client verwijderd.<br />Aanbevolen waarde: <strong>Ja</strong> |
| <strong>Endpoint Protection installeren, zelfs als er een eindpuntbeveiligingstoepassing van derden is geïnstalleerd</strong> |                                                                                                                                                                                                                                                                                                                Ingesteld op <strong>Ja</strong> om Microsoft Intune Endpoint Protection te gebruiken, zelfs als er een eindpuntbeveiligingstoepassing van derden is gedetecteerd.<br /><br />Aanbevolen waarde: <strong>Ja</strong>                                                                                                                                                                                                                                                                                                                |
|                                   <strong>Endpoint Protection inschakelen</strong>                                   |                                                                                                                                                                                                            Ingesteld op <strong>Ja</strong> om Microsoft Intune Endpoint Protection in te schakelen op computers met de Endpoint Protection-client.<br /><br />Als deze optie is ingesteld op <strong>Nee</strong> en Microsoft Intune Endpoint Protection is geïnstalleerd, wordt de gebruikersinterface van de Endpoint Protection-client niet weergegeven voor gebruikers en zijn alle beveiligingsfuncties inactief.<br /><br />Aanbevolen waarde: <strong>Ja</strong>                                                                                                                                                                                                             |
|                                       <strong>Gebruikersinterface van client uitschakelen</strong>                                        |                                                                                                                                                                                                                                                                                                      Ingesteld op <strong>Ja</strong> om de gebruikersinterface van de Microsoft Intune Endpoint Protection-client voor gebruikers te verbergen (vereist dat een clientcomputer opnieuw wordt opgestart om de instelling door te voeren).<br /><br />Aanbevolen waarde: <strong>Nee</strong>                                                                                                                                                                                                                                                                                                       |
| <strong>Endpoint Protection installeren, zelfs als er een eindpuntbeveiligingstoepassing van derden is geïnstalleerd</strong> |                                                                                                                                                                                                                                                                                                       Ingesteld op <strong>Ja</strong> om de installatie van Microsoft Intune Endpoint Protection af te dwingen, zelfs als er een eindpuntbeveiligingstoepassing van derden is gedetecteerd.<br /><br />Aanbevolen waarde: <strong>Nee</strong>                                                                                                                                                                                                                                                                                                       |
|                    <strong>Een systeemherstelpunt maken vóór het oplossen van malware</strong>                    |                                                                                                                                                                                                                                                                                                                                 Ingesteld op <strong>Ja</strong> om een Windows-systeemherstelpunt te maken voordat er wordt begonnen met het oplossen van malware.<br /><br />Aanbevolen waarde: <strong>Ja</strong>                                                                                                                                                                                                                                                                                                                                  |
|                                 <strong>Opgeloste malware bijhouden (dagen)</strong>                                  |                                                                                                                                                                                                                                                                                      Hiermee kan Endpoint Protection gedurende een bepaalde tijd opgeloste malware bijhouden, zodat u handmatig eerder geïnfecteerde computers kunt controleren.<br /><br />U kunt een waarde van 0 tot 30 dagen opgeven.<br /><br />Aanbevolen waarde: <strong>7 dagen</strong>                                                                                                                                                                                                                                                                                       |

Als u de beleidswaarden voor **Endpoint Protection installeren** en **Endpoint Protection inschakelen** op **Ja**en de beleidswaarde voor **Endpoint Protection installeren, zelfs als er een eindpuntbeveiligingstoepassing van derden is geïnstalleerd** op **Nee** hebt ingesteld, detecteert Microsoft Intune Endpoint Protection dat een andere eindpuntbeveiligingstoepassing is geïnstalleerd. Dit betekent dat Endpoint Protection niet wordt geïnstalleerd of wordt verwijderd als het al is geïnstalleerd. Microsoft Intune Endpoint Protection rapporteert echter wel over de status van de andere eindpuntbeveiligingstoepassing in Intune.

  Met de realtime-beveiliging van Microsoft Security Essentials wordt u gewaarschuwd wanneer mogelijke bedreigingen, zoals virussen of spyware, zichzelf op uw pc proberen te installeren of uit te voeren. Wanneer dit gebeurt, ziet u een bericht in het systeemvak rechts in de taakbalk.

### <a name="specify-real-time-protection-settings"></a>Instellingen voor realtime-beveiliging opgeven

|Beleidsinstelling|Details|
|------------------|--------------------|
|**Realtime-beveiliging inschakelen**|Hiermee schakelt u in dat alle bestanden en toepassingen waartoe toegang wordt gekregen, worden gecontroleerd en gescand. Ook worden schadelijke bestanden en toepassingen geblokkeerd voordat ze op computers kunnen worden uitgevoerd.<br /><br />Aanbevolen waarde: **Ja**|
|**Alle downloads scannen**|Hiermee schakelt u in dat alle bestanden en bijlagen worden gescand die van internet naar computers worden gedownload.<br /><br />Aanbevolen waarde: **Ja**|
|**Activiteit van bestanden en programma's op de computer bewaken**|Hiermee schakelt u in dat activiteiten van binnenkomende en uitgaande bestanden en van programma's op computers worden bewaakt. Met deze instelling kan Endpoint Protection bewaken wanneer bestanden en programma's worden gestart en wordt u geïnformeerd over alle acties die ze uitvoeren of acties die worden uitgevoerd op deze bestanden en programma's.<br /><br />Aanbevolen waarde: **Ja**|
|**Bewaakte bestanden**|Hiermee kunt u instellen dat alleen binnenkomende, alleen uitgaande of alle bestanden moeten worden bewaakt.<br /><br />Aanbevolen waarde: **Alle bestanden bewaken**|
|**Gedragscontrole inschakelen**|Hiermee kan Microsoft Intune Endpoint Protection controleren op bepaalde patronen van verdachte activiteiten op clientcomputers.<br /><br />Aanbevolen waarde: **Ja**|
|**Netwerkinspectiesysteem inschakelen**|Hiermee schakelt u het systeem voor netwerkinspectie (NIS) in op clientcomputers. NIS maakt gebruik van handtekeningen van bekende beveiligingsproblemen van het [Microsoft Centrum voor beveiliging tegen schadelijke software](https://go.microsoft.com/fwlink/?LinkId=234249) om schadelijk netwerkverkeer te helpen detecteren en blokkeren.<br /><br />Aanbevolen waarde: **Ja**|

  ![Realtime-instellingen voor Endpoint Protection](./media/pol-sa-pc-policy-realtime.png)

### <a name="specify-scan-schedule-settings"></a>Instellingen voor scanschema's opgeven

|Beleidsinstelling|Meer informatie|
|------------------|--------------------|
|**Een dagelijkse snelle scan plannen**|Hiermee plant u een dagelijkse snelle scan van zowel veelgebruikte bestanden als belangrijke systeembestanden op computers. Deze snelle scan heeft een minimale invloed op de prestaties.<br /><br />Aanbevolen waarde: **Ja**|
|**Een snelle scan uitvoeren als u twee opeenvolgende scans hebt gemist**|Hiermee configureert u Endpoint Protection zo dat er op computers automatisch een snelle scan wordt uitgevoerd als er twee opeenvolgende snelle scans zijn gemist.<br /><br />Aanbevolen waarde: **Ja**|
|**Een volledige scan plannen**|Hiermee configureert u een volledige scan van alle bestanden en bronnen op de lokale harde schijven van computers. Deze scan kan even duren en kan van invloed zijn op de prestaties van de computer (de duur is afhankelijk van het aantal bestanden en bronnen dat wordt gescand).<br /><br />Aanbevolen waarde: **Nee**|
|**Een volledige scan uitvoeren als u twee opeenvolgende volledige scans hebt gemist**|Hiermee configureert u Endpoint Protection zo dat er op computers automatisch een volledige scan wordt uitgevoerd als er twee opeenvolgende scans zijn gemist.<br /><br />Aanbevolen waarde: Niet geconfigureerd|

### <a name="specify-scan-options-settings"></a>Instellingen voor scanopties opgeven

|Beleidsinstelling|Details|
|------------------|--------------------|
|**Een volledige scan uitvoeren na de installatie van Endpoint Protection**|Ingesteld op **Ja**, zodat Endpoint Protection automatisch een volledige systeemscan uitvoert nadat het op een computer is geïnstalleerd. Deze scan wordt alleen uitgevoerd als computers niet actief zijn om te voorkomen dat dit gevolgen heeft voor de productiviteit van gebruikers.<br /><br />Aanbevolen waarde: **Ja**|
|**Automatisch een volledige scan uitvoeren als dit nodig is na het verwijderen van malware**|Ingesteld op **Ja** om Endpoint Protection automatisch een volledige systeemscan op computers te laten uitvoeren na het verwijderen van malware om te helpen bevestigen dat andere bestanden niet zijn geïnfecteerd.<br /><br />Aanbevolen waarde: **Ja**|
|**Een geplande scan alleen starten als de computer niet actief is**|Ingesteld op **Ja** om te voorkomen dat geplande scans worden gestart wanneer computers worden gebruikt, om verlies van productiviteit te voorkomen.<br /><br />Aanbevolen waarde: **Ja**|
|**Controleren op de meest recente malware-definities voordat een scan wordt gestart**|Ingesteld op **Ja** om Endpoint Protection automatisch te laten controleren op de meest recente malwaredefinities voordat een scan op computers wordt gestart.<br /><br />Aanbevolen waarde: **Ja**|
|**Archiefbestanden scannen**|Ingesteld op **Ja** om Endpoint Protection zo te configureren dat er op schadelijke software in archiefbestanden (zoals .zip- of .cab-bestanden) op computers wordt gecontroleerd.<br /><br />Aanbevolen waarde: **Nee**|
|**E-mailberichten scannen**|Ingesteld op **Ja** om Endpoint Protection zo te configureren dat binnenkomende e-mailberichten worden gescand als deze op computers binnenkomen.<br /><br />Aanbevolen waarde: **Ja**|
|**Bestanden scannen die zijn geopend vanuit gedeelde mappen op het netwerk**|Ingesteld op **Ja** om Endpoint Protection zo te configureren dat de bestanden worden gecontroleerd die worden geopend vanuit gedeelde mappen op het netwerk. Dit zijn meestal bestanden die toegankelijk zijn via een UNC-pad (Universal Naming Convention). Het inschakelen van deze functie kan problemen veroorzaken voor gebruikers die alleen-lezen toegang hebben, omdat ze geen schadelijke software kunnen verwijderen.<br /><br />Aanbevolen waarde: **Nee**|
|**Toegewezen netwerkstations scannen**|Ingesteld op **Ja** om Endpoint Protection zo te configureren dat bestanden op toegewezen netwerkstations worden gescand. Het inschakelen van deze functie kan problemen veroorzaken voor gebruikers die alleen-lezen toegang hebben, omdat ze geen schadelijke software kunnen verwijderen.<br /><br />Aanbevolen waarde: **Nee**|
|**Verwisselbare stations scannen**|Ingesteld op **Ja** om Endpoint Protection zo te configureren dat er op schadelijke en ongewenste software op verwisselbare stations (bijvoorbeeld USB-stations) wordt gescand wanneer u een volledige scan op computers uitvoert.<br /><br />Aanbevolen waarde: **Ja**|
|**CPU-verbruik tijdens een scan beperken**|Hiermee stelt u het maximale percentage CPU-verbruik in dat kan worden gebruikt tijdens geplande scans op computers. U kunt deze waarde instellen van 1 tot 100 procent.<br /><br />Aanbevolen waarde: **50%**|

### <a name="choose-default-actions-settings"></a>Instellingen voor standaardacties kiezen

Met de instelling **Kiezen hoe Endpoint Protection omgaat met schadelijke software met de volgende waarschuwingsniveaus** geeft u de standaardactie op die door Endpoint Protection moet worden uitgevoerd wanneer er malware van verschillende waarschuwingsniveaus wordt gedetecteerd. Voor elk waarschuwingsniveau kunt u de malware verwijderen of in quarantaine plaatsen of de actie uitvoeren die door Microsoft wordt aanbevolen.

Aanbevolen waarde: **Aanbevolen actie**, waarmee Endpoint Protection actie kan aanbevelen.   

### <a name="decide-whether-to-choose-the-excluded-files-and-folders-settings"></a>Beslissen of u de instellingen voor uitgesloten bestanden en mappen kiest

Met de instelling **Bestanden en mappen die moeten worden uitgesloten bij het scannen en bij realtime-beveiliging** worden specifieke bestanden of mappen uitgesloten wanneer er een scan wordt uitgevoerd of wanneer realtime-beveiliging op computers wordt gebruikt.

### <a name="decide-whether-to-choose-the-excluded-processes-settings"></a>Beslissen of u de instellingen voor uitgesloten processen kiest

Met de instelling **Processen die moeten worden uitgesloten bij het scannen of bij realtime-beveiliging** worden specifieke processen uitgesloten wanneer er een scan wordt uitgevoerd of wanneer realtime-beveiliging op computers wordt gebruikt. U kunt alleen bestanden met de volgende extensies uitsluiten: **.exe**, **.com** en **.scr**.

### <a name="decide-whether-to-choose-the-excluded-file-types-settings"></a>Beslissen of u de instellingen voor uitgesloten bestandstypen kiest

Met de instelling **Bestandsextensies die uitgesloten moeten worden bij het scannen en bij de realtime-beveiliging** worden specifieke bestandsnaamextensies uitgesloten wanneer er een scan wordt uitgevoerd of wanneer realtime-beveiliging op computers wordt gebruikt.

### <a name="specify-microsoft-active-protection-service-settings"></a>Instellingen voor Microsoft Active Protection Service opgeven
Microsoft Active Protection Service is een onlinecommunity die helpt bepalen hoe u op mogelijke bedreigingen reageert. De community helpt ook de verspreiding van nieuwe malware-infecties te stoppen. U kunt zich **aanmelden bij Microsoft Active Protection Service** door **Ja** te selecteren en vervolgens uw **lidmaatschapsniveau** op te geven:
  - **Basis**: verzendt basisinformatie over de gedetecteerde malware naar Microsoft. Dit omvat waar de software van afkomstig is, de acties die u toepast of die Endpoint Protection automatisch toepast en of de acties met succes zijn uitgevoerd.
  - **Geavanceerd**: verzendt meer informatie over malware, spyware en mogelijk ongewenste software naar Microsoft. Dit omvat informatie over de locatie van de software, bestandsnamen, hoe de software werkt en hoe deze uw computer heeft beïnvloed.

U kunt ook **Dynamische definities ontvangen, gebaseerd op rapporten van Microsoft Active Protection Service**.

## <a name="choose-management-tasks-for-endpoint-protection"></a>Beheertaken voor Endpoint Protection kiezen
De volgende taken helpen u bij het uitvoeren van verschillende beheertaken op beheerde computers met Endpoint Protection.
- Malware-definities bijwerken
  - Intune-console: selecteer in de werkruimte **Groepen** de computers die u wilt bijwerken. Kies **Externe taken** &gt; **Malware-definities bijwerken**.
  - Beheerde computer: start de Endpoint Protection-clientsoftware in het systeemvak. Kies het tabblad **Bijwerken** en vervolgens **Bijwerken**.
- Ga als volgt te werk om een scan op schadelijke software uit te voeren:
  - Intune-console: selecteer in de werkruimte **Groepen** de computers die u wilt scannen. Kies **Een volledige scan op malware uitvoeren** of **Een snelle scan op malware uitvoeren**.
  - Beheerde computer: start de Endpoint Protection-clientsoftware in het systeemvak. Selecteer **Snel**, **Volledig**of **Aangepast** en kies vervolgens **Nu scannen**.

U kunt de status van een externe taak weergeven door op de koppeling **Externe taken** in de rechterbenedenhoek van de Intune-console te klikken. In het dialoogvenster **Status externe taak** staan de huidige externe taken, de taakstatus, de apparaatnaam en eventuele gerapporteerde fouten. Hier vindt u ook een koppeling naar informatie over probleemoplossing als dat nodig is.

## <a name="monitor-endpoint-protection"></a>Endpoint Protection controleren
U kunt de status van schadelijke software op uw computers controleren met behulp van de werkruimte **Beveiliging** van de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/). Deze werkruimte bevat twee pagina's:
- **Overzicht Endpoint Protection**: bevat belangrijke zaken als koppelingen waarop u kunt klikken voor meer informatie. Dit kan gaan over:
  - **Malware-exemplaren die moeten worden opgevolgd**: klik op de koppeling voor een overzicht van malwareproblemen, inclusief de actie die moet worden ondernomen om het probleem te verhelpen. U kunt deze lijst nader bestuderen om te zien welke computers zijn beïnvloed.
  - **Computers met malware die moeten worden opgevolgd**: klik op de koppeling om alle computers met niet-opgeloste malwareproblemen weer te geven, en de actie die moet worden ondernomen om het probleem te verhelpen.
  - **Apparaten die niet zijn beveiligd**: klik op de koppeling om te zien welke computers niet zijn beveiligd door eindpuntbeveiligingssoftware omdat er geen software is geïnstalleerd of omdat er een fout is opgetreden. Selecteer een computer om meer details te bekijken.
  - **Apparaten waarop een andere eindpuntbeveiligingstoepassing actief is**: klik op de koppeling om te zien op welke computers een eindpuntbeveiligingstoepassing van derden wordt uitgevoerd.
- **Alle malware**: er wordt een lijst weergegeven van alle actieve malware op uw computers. U kunt deze lijst nader bestuderen om te zien welke computers worden beïnvloed door een bepaald onderdeel van malware. Ook kunt u een van de volgende taken selecteren:
  - **Eigenschappen weergeven**: opent een pagina met meer informatie over de geselecteerde malware.
  - **Meer informatie over deze malware**: opent een onderwerp van het Microsoft Malware Protection Center met meer informatie over de malware.

> [!IMPORTANT]
> De werkruimte **Beveiliging** wordt pas weergegeven in de beheerconsole nadat u de client op ten minste één computer hebt geïnstalleerd en de client beheert.

  ![Endpoint Protection controleren](./media/pol-sa-ep-monitor.png)

### <a name="how-to-view-recent-detection-paths-for-malware-on-computers"></a>Recente detectiepaden voor malware op computers weergeven
Met Intune kunt u de paden van maximaal tien onlangs gedetecteerde exemplaren van malware op een apparaat weergeven. De optie **Recent detectiepad** is standaard uitgeschakeld. Deze weergave inschakelen:

1. Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) op **Groepen** > **Alle apparaten** > **Alle computers**.
2. Klik met de rechtermuisknop op de computer waarvan u de recente detectiepaden wilt bekijken en selecteer **Eigenschappen**.
3. Selecteer het tabblad **Malware** bovenaan.

   ![Selecteer het tabblad Malware en klik op het selectievakje bij Recente detectiepaden](../media/malware-path-column.png)
4. Klik met de rechtermuisknop op de kolomkop. Een lijst met beschikbare kolommen wordt weergegeven. Selecteer in de lijst het selectievakje **Recente detectiepaden**. De kolom **Recente detectiepaden** wordt weergegeven met daarin de tien onlangs op het apparaat gedetecteerde malware-exemplaren.

## <a name="run-a-malware-scan-or-update-malware-definitions-on-a-computer"></a>Een malwarescan uitvoeren of de malwaredefinities op een computer bijwerken
U kunt met Intune een volledige of snelle malwarescan uitvoeren met Endpoint Protection of Windows Defender op een extern beheerde pc waarop de Intune-client is geïnstalleerd.

1. Ga in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com/) naar **Groepen** > **Overzicht** > **Alle apparaten** > **Alle computers** en selecteer de computer die u wilt targeten.

2. Kies de vervolgkeuzelijst **Externe taken** en selecteer de taak om deze uit te voeren op de externe computer.

## <a name="need-more-help"></a>Meer hulp nodig?
Zie [Problemen met Endpoint Protection in Microsoft Intune oplossen](/intune-classic/troubleshoot/troubleshoot-endpoint-protection-in-microsoft-intune) voor meer hulp en ondersteuning.

### <a name="see-also"></a>Zie ook
[Beleid voor het beveiligen van Windows-pc's](policies-to-protect-windows-pcs-in-microsoft-intune.md)
