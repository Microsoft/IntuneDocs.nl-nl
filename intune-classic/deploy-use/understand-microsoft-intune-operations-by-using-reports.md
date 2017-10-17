---
title: Microsoft Intune-bewerkingen begrijpen met behulp van rapporten
description: Rapporten over software, hardware en softwarelicenties in uw organisatie maken en beheren.
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 04/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 857309c2-61c9-4c22-becf-4839fedeaece
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: pbala
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f812a740f5a703479e001fa2c5b6d1fd3336a2e2
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/10/2017
---
# <a name="understand-microsoft-intune-operations-by-using-reports"></a>Understand Microsoft Intune operations by using reports

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Gebruik de informatie in dit onderwerp om u te helpen bij het maken en beheren van Microsoft Intune-rapporten die informatie geven over software, hardware en softwarelicenties in uw organisatie.

## <a name="using-reports"></a>Using Reports (Rapporten gebruiken)
Intune-rapporten geven informatie over software, hardware en softwarelicenties in uw organisatie. Rapporten kunnen u helpen bij het bevestigen van huidige behoeften en het voorspellen van toekomstige uitgaven. De werkruimte **Rapporten** biedt u de hulpmiddelen voor het maken en beheren van rapporten. 

## <a name="report-types"></a>Rapporttypen

|Rapporttype|Beschrijving|
|---------------|---------------|
|**Updaterapporten**|De software-updates die zijn uitgevoerd op computers in uw organisatie worden weergegeven. Ook worden de updates weergegeven die zijn mislukt, in behandeling zijn of vereist zijn. Voor meer informatie over software-updates raadpleegt u [Windows-pc’s up-to-date houden met software-updates in Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).|
|**Rapporten met gedetecteerde software**|De software die op computers in uw organisatie is geïnstalleerd wordt weergegeven. Ook worden de softwareversies vermeld. U kunt de informatie die wordt weergegeven, filteren op basis van de software-uitgever en de softwarecategorie. U kunt de updates in de lijst uitvouwen voor meer details (zoals de computers waarop een update is geïnstalleerd) door de richtingspijl naast het item te kiezen.<br /><br />Wanneer u computers buiten gebruik stelt of de groepslidmaatschappen ervan in Intune wijzigt, kan het enkele minuten duren voordat deze wijzigingen worden weergegeven in het rapport Gedetecteerde software. Voor de meest nauwkeurige software-inventarisatiegegevens wacht u enkele minuten na het buiten gebruik stellen van computers of het wijzigen van hun groepslidmaatschappen voordat u een rapport met gedetecteerde software voor deze computers uitvoert.|
|**Computerinventarisrapporten**|Tonen informatie over beheerde computers in uw organisatie. Gebruik dit rapport voor het plannen van hardwareaankopen en voor meer begrip van de hardwarebehoeften van gebruikers in uw organisatie. Zie [Windows-pc's met Microsoft Intune beheren](manage-windows-pcs-with-microsoft-intune.md) voor meer informatie over het werken met beheerde computers.|
|**Inventarisrapporten voor mobiele apparaten**|Tonen informatie over de mobiele apparaten in uw organisatie. U kunt de informatie filteren die wordt weergegeven op basis van groepen, of het nu een jailbroken of rooted apparaat betreft, en op besturingssysteem.|
|**Licentie-inkooprapporten**|Tonen de softwaretitels voor alle gelicentieerde software in geselecteerde licentiegroepen, op basis van de licentieovereenkomsten. Als softwarelicentiegegevens langer dan 24 uur niet zijn vernieuwd, worden deze vernieuwd wanneer u een licentierapport genereert. Een licentierapport is geen exacte berekening van de softwaretitels die worden gebruikt, noch een bewijs van naleving van overeenkomsten. Het rapport is een middel waarmee u licentiebeslissingen voor uw organisatie kunt nemen. Intune detecteert mogelijk bepaalde producten niet die over een Microsoft-volumelicentie kunnen beschikken. De beschikbare filters zijn:<br /><br />**Alle overeenkomsten** toont alle gelicentieerde softwareproducten die worden beheerd met Intune.<br /><br />**Volumelicentieovereenkomsten** toont uitsluitend VLSC-softwareproducten (Volume Licensing Service Center).<br /><br />**Overige softwarelicentieovereenkomsten** toont softwareproducten die buiten het VLSC worden beheerd.|
|**Licentie-installatierapporten**|Vergelijk geïnstalleerde software op computers in uw organisatie met de huidige dekking van uw licentieovereenkomst volgens het VLSC. Filters omvatten:<br /><br />**Alle overeenkomsten** toont alle gelicentieerde softwareproducten die worden beheerd met Intune.<br /><br />**Volumelicentieovereenkomsten** toont uitsluitend VLSC-softwareproducten.<br /><br />**Overige softwarelicentieovereenkomsten** toont softwareproducten die buiten het VLSC worden beheerd.|
|**Rapporten van voorwaarden**|Weergeven of gebruikers de door u geïmplementeerde voorwaarden hebben geaccepteerd en welke versie ze hebben geaccepteerd. U kunt voor maximaal 10 gebruikers weergeven of de geïmplementeerde voorwaarden zijn geaccepteerd. U kunt ook de acceptatiestatus weergeven voor een bepaalde voorwaarde die bij hen is geïmplementeerd.|
|**Rapporten over niet-compatibele apps**|Tonen informatie over de gebruikers die apps hebben geïnstalleerd die op uw lijsten met compatibele en niet-compatibele apps staan. Met dit rapport kunt u zoeken naar gebruikers en apparaten die niet voldoen aan uw bedrijfsbeleid inzake apps.|
|**Rapporten voor certificaatnaleving**|Weergeven welke certificaten via SCEP of PKCS #12 (.pfx) zijn uitgegeven aan gebruikers en apparaten. Met dit rapport kunt u zoeken naar certificaten die zijn uitgegeven, verlopen en ingetrokken.|
|**Apparaatgeschiedenisrapporten**|Een historisch logboek van intrekkings-, wis- en verwijderingsacties weergeven. Gebruik dit rapport om te zien wie in het verleden acties op apparaten heeft gestart.|
|**Health Attestation-rapporten**|De status van mobiele apparaten weergeven.|
|**Mac OS X-hardwarerapport**|Geeft de details weer van de hardware van alle ingeschreven Mac OS X-apparaten in de door u geselecteerde groepen. Zie [Inzicht in uw apparaten met inventarisaties in Microsoft Intune](understand-your-devices-with-inventory-in-microsoft-intune.md) voor informatie over de hardware-inventarisatie van deze apparaten.|
|**Mac OS X-softwarerapport**|Geeft de software weer die op alle Mac OS X-apparaten in de door u geselecteerde groepen is geïnstalleerd. Het rapport bevat de softwarenaam (als een bundel-id), de verkorte (of gebruiksvriendelijke) versienaam, de versie en het aantal apparaten waarop de software is geïnstalleerd.|
|**Windows Information Protection-rapporten**|Bevat informatie over Windows Information Protection (WIP)-bewerkingen op apparaten die u beheert.|
|**Health Attestation-rapporten**|Bevat informatie die wordt gerapporteerd door de Windows Health Attestation-service voor apparaten die u hebt beheerd.|

## <a name="to-create-a-report"></a>Een rapport maken

1.  Kies **Rapporten** in de Intune-beheerconsole. Kies vervolgens het rapporttype dat u wilt genereren, zoals beschreven in de vorige tabel.

2.  Op de pagina **Nieuw rapport maken** accepteert u de standaardwaarden of past u deze aan om de resultaten te filteren die door het rapport worden geretourneerd. U kunt bijvoorbeeld selecteren dat alleen de software die is uitgegeven door Microsoft wordt weergegeven in het rapport Gedetecteerde software.

3.  Kies **Rapport weergeven** om het rapport in een nieuw venster te openen.

Kies de kolomkop om het rapport te sorteren op elk van de weergegeven kolommen. Bovendien kunt u in sommige rapporten items in de lijst uitvouwen om meer details weer te geven.

## <a name="more-report-actions"></a>Meer rapportacties
Bovendien ondersteunen rapporten de volgende acties:

|Actie|Meer informatie|
|----------|--------------------|
|**Afdrukken**|Kies in een geopend rapport het pictogram voor afdrukken en volg de instructies.|
|**Exporteren**|Kies in een geopend rapport het pictogram voor exporteren en volg de instructies. U kunt een rapport exporteren naar de indeling met door komma's gescheiden waarden (.csv) of de HTML-indeling.|
|**Opslaan**|Op de pagina **Nieuw rapport maken** kan iedere gebruiker maximaal 100 rapporten opslaan. Configureer de rapportparameters zodat ze aan uw vereisten voldoen en kies **Opslaan**of **Opslaan als** (als u een andere naam wilt gebruiken).|
|**Laden**|Op de pagina **Nieuw rapport maken** kiest u **Laden** om eerder opgeslagen sets met rapportparameters op te halen.|
|**Verwijderen**|Selecteer in de werkruimte **Rapporten** het gewenste rapporttype en kies **Laden**. Kies vervolgens in de lijst met rapporten het pictogram voor verwijderen (x) naast het rapport.|


