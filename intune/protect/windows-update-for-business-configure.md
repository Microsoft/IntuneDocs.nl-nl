---
title: Windows Update voor Bedrijven configureren in Microsoft Intune - Azure | Microsoft Docs
description: Windows 10-software-updates beheren met updateringen en het beleid voor onderdelenupdates. U kunt naleving bekijken en de installatie van updates onderbreken met instellingen van Windows Update voor Bedrijven met behulp van Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/20/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: a7c3398f28d7c396c873dd29f3e3fdd719c1a7c6
ms.sourcegitcommit: f26039d674eb4d61ab68264dd1a10b2e5e1d842c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/02/2019
ms.locfileid: "74691776"
---
# <a name="manage-windows-10-software-updates-in-intune"></a>Windows 10-software-updates beheren in Intune

Intune gebruiken voor het beheren van de installatie van Windows 10-software-updates via Windows Update voor Bedrijven.

Met behulp van Windows Update voor Bedrijven kunt u de updatebeheerervaring vereenvoudigen. U hoeft geen afzonderlijke updates voor apparaatgroepen goed te keuren. U kunt het risico in uw omgevingen beheren door een strategie voor het implementeren van updates te configureren. Intune biedt de mogelijkheid [update-instellingen te configureren](windows-update-settings.md) op apparaten, en biedt u de mogelijkheid de installatie van updates uit te stellen. U kunt ook voorkomen dat apparaten functies van nieuwe Windows-versies installeren om ze stabiel te houden, en deze apparaten tegelijkertijd wel toestaan de installatie van updates voor kwaliteit en beveiliging te blijven installeren.

In Intune worden alleen de updatebeleidstoewijzingen opgeslagen, niet de updates zelf. Apparaten maken direct verbinding met Windows Update voor de updates.

Intune biedt de volgende beleidstypen voor het beheren van updates:

- **Windows 10-updatering**: dit beleid is een verzameling instellingen die wordt geconfigureerd wanneer Windows 10-updates worden geïnstalleerd.

- **Windows 10-onderdelenupdates (openbare preview)** : dit beleid brengt apparaten naar de Windows-versie die u opgeeft en blokkeert de functie die is ingesteld op deze apparaten totdat u ze bijwerkt naar een hogere Windows-versie.  De onderdelenversie blijft statisch, maar apparaten kunnen de kwaliteits- en beveiligingsupdates die beschikbaar zijn voor de onderdelenversie blijven installeren.

U wijst beleid toe voor Windows 10-updateringen en Windows 10-onderdelenupdates voor groepen apparaten. U kunt beide beleidstypen in dezelfde Intune-omgeving gebruiken om software-updates voor uw Windows 10-apparaten te beheren en om een updatestrategie te maken die overeenkomt met de behoeften van uw bedrijf.

Zie [Manage updates using Windows Update for Business](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb) (Updates beheren met Windows Update voor Bedrijven) voor meer informatie.

## <a name="prerequisites"></a>Vereisten

Aan de volgende vereisten moet worden voldaan om Windows-updates voor Windows 10-apparaten te kunnen gebruiken in Intune.

- Windows 10-pc's moeten de volgende versies van Windows 10 uitvoeren:
  - **Windows 10-updateringen**: versie 1607 of hoger
  - **Windows 10-onderdelenupdates**: versie 1703 of hoger

- Windows Update biedt ondersteuning voor de volgende edities van Windows 10:
  - Windows 10
  - Windows 10 Team: voor Surface Hub-apparaten (geen ondersteuning voor *Windows 10-onderdelenupdates*)
  - Windows Holographic for Business

    Windows Holographic for Business biedt ondersteuning voor een subset instellingen voor Windows-updates, waaronder:
    - **Gedrag van automatische updates**
    - **Productupdates van Microsoft**
    - **Servicekanaal**: Ondersteunt de opties **Semi-Annual-kanaal** en **Semi-Annual-kanaal (Targeted)** . Zie [Windows Holographic beheren](../fundamentals/windows-holographic-for-business.md) voor meer informatie.

  > [!NOTE]
  > **Niet-ondersteunde versies en edities**:
  > - Windows 10 Mobile  
  > - Windows 10 Enterprise LTSC. Windows Update for Business (WUfB) biedt momenteel geen ondersteuning voor *Long Term Service Channel*-releases. Plan het gebruik van alternatieve methoden voor het toepassen van patches, zoals WSUS of Configuration Manager.

- Op Windows-apparaten moet **Feedback en diagnostische gegevens** > **Diagnostische gegevens en gebruiksgegevens** zijn ingesteld op **Basis**, **Uitgebreid** of **Volledig**.  

  U kunt de instelling *Diagnostische gegevens en gebruiksgegevens* voor Windows 10-apparaten handmatig configureren of een Intune-apparaatbeperkingsprofiel gebruiken voor Windows 10 en hoger. Als u een apparaatbeperkingsprofiel gebruikt, stelt u de [apparaatbeperkingsinstelling](../configuration/device-restrictions-windows-10.md#reporting-and-telemetry) van **Gebruiksgegevens delen** in op ten minste **Basis**. U vindt deze instelling in de categorie **Rapportage en telemetrie** wanneer u een apparaatbeperkingsbeleid configureert voor Windows 10 of hoger.

  Zie [Instellingen voor apparaatbeperking configureren](../configuration/device-restrictions-configure.md) voor meer informatie over apparaatprofielen.

- Als u gebruikmaakt van de klassieke Azure-portal, [migreert u de instellingen naar de Azure-portal](#migrate-update-settings-to-the-azure-portal).


## <a name="windows-10-update-rings"></a>Windows 10-updateringen

Maak updateringen die aangeven hoe en wanneer uw Windows 10-apparaten worden bijgewerkt via Windows als een service met functie- en kwaliteitsupdates. In Windows 10 bevatten nieuwe functie-updates en kwaliteitsupdates de inhoud van alle voorgaande updates. Dit houdt in dat, als u de nieuwste update hebt geïnstalleerd, u zeker weet dat uw Windows 10-apparaten zijn bijgewerkt. In tegenstelling tot eerdere versies van Windows, moet u nu de volledige update installeren in plaats van een onderdeel van een update.

Windows 10-updateringen bieden ondersteuning voor [bereiktags](../fundamentals/scope-tags.md). U kunt bereiktags gebruiken om u te helpen de configuratiesets die u gebruikt, te filteren en te beheren.

### <a name="create-and-assign-update-rings"></a>Update-ringen maken en toewijzen

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum]( https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecteer **Apparaten** > **Windows** > **Windows 10-updateringen** > **Maken**.

3. Geef onder *Basisinformatie* een naam en optioneel een beschrijving op en selecteer vervolgens **Volgende**.
  ![Een updatering maken]( ./media/windows-update-for-business-configure/basics-tab.png)
  
4. Configureer onder **Ringinstellingen bijwerken** de instellingen die passen bij de behoeften van uw bedrijf. Zie Windows-update-instellingen voor meer informatie over de beschikbare instellingen. Nadat u de instellingen *Bijwerken en Gebruikerservaring* hebt geconfigureerd, selecteert u **Volgende**.

5. Selecteer onder **Bereiktags** de optie **Bereiktags selecteren** om het deelvenster *Tags selecteren* te openen als u deze wilt toepassing op de updatering. Kies een of meer tags en klik vervolgens op **Selecteren** om deze toe te voegen aan de updatering en terug te keren naar het deelvenster *Bereiktags*.

   Wanneer u klaar bent, selecteert u **Volgende** om naar *Toewijzingen* te gaan.

6. Kies onder **Toewijzingen** de optie **Groepen selecteren die moeten worden opgenomen** en wijs de updatering toe aan een of meer groepen. Gebruik **+ Groepen selecteren die moeten worden uitgesloten** om de toewijzing te verfijnen. Selecteer **Volgende** om door te gaan.

7. Controleer de instellingen onder **Beoordelen en maken** en selecteer **Maken** als u klaar bent om uw Windows 10-updatering op te slaan. Uw nieuwe update-ring wordt weergegeven in de lijst met update-ringen.

### <a name="manage-your-windows-10-update-rings"></a>Uw Windows 10-updateringen beheren

Navigeer in de portal naar **Apparaten** > **Windows** > **Windows 10-updateringen** en selecteer het beleid dat u wilt beheren.  Het beleid wordt geopend met de pagina **Overzicht**.

Naast het weergeven van de toewijzingsstatus kunt u ook boven aan het deelvenster Overzicht de volgende acties selecteren om de updatering te beheren:

- [Verwijderen](#delete)
- [Onderbreken](#pause)
- [Hervatten](#resume)
- [Uitbreiden](#extend)
- [Verwijderen](#uninstall)

![Beschikbare acties](./media/windows-update-for-business-configure/overview-actions.png)

#### <a name="delete"></a>Verwijderen

Selecteer **Verwijderen** om te stoppen met het afdwingen van de instellingen van de geselecteerde Windows 10-updatering. Als u een ring verwijdert, wordt ook de bijbehorende configuratie uit Intune verwijderd, waardoor deze instellingen niet meer worden toegepast en afgedwongen in Intune.

Als u een ring verwijdert uit Intune, worden de instellingen op apparaten waaraan de updatering is toegewezen, niet gewijzigd.  In plaats hiervan behoudt het apparaat de huidige instellingen. Apparaten behouden geen historisch overzicht van de instellingen die ze eerder hebben bewaard. Apparaten kunnen ook instellingen ontvangen van extra updateringen die actief blijven.

##### <a name="to-delete-a-ring"></a>Een ring verwijderen

1. Selecteer **Verwijderen** tijdens het weergeven van de overzichtspagina voor een updatering.
2. Selecteer **OK**.

#### <a name="pause"></a>Onderbreken

Selecteer **Onderbreken** om te voorkomen dat toegewezen apparaten gedurende maximaal 35 dagen vanaf het moment waarop u de ring onderbreekt, onderdelenupdates of kwaliteitsupdates ontvangen. Als het maximum aantal dagen is verstreken, verloopt de functionaliteit voor onderbreken automatisch en zoekt het apparaat in Windows Update naar toepasselijke updates. Na deze scan kunt u de updates opnieuw onderbreken.
Als u een onderbroken updatering hervat, en deze ring vervolgens opnieuw onderbreekt, wordt de onderbrekingsperiode opnieuw ingesteld op 35 dagen.

##### <a name="to-pause-a-ring"></a>Een ring onderbreken

1. Selecteer **Onderbreken** tijdens het weergeven van de overzichtspagina voor een updatering.
2. Selecteer **Onderdeel** of **Kwaliteit** om het gewenste type update te onderbreken, en selecteer vervolgens **OK**.
3. Als u één type update hebt onderbroken, kunt u opnieuw Onderbreken selecteren om ook het andere updatetype te onderbreken.

Wanneer een updatetype is onderbroken, wordt op het deelvenster Overzicht van deze ring weergegeven hoeveel dagen nog resteren voordat het updatetype wordt hervat.

> [!IMPORTANT]
> Nadat u een opdracht voor onderbreken opgeeft, ontvangen apparaten deze opdracht de volgende keer dat bij de service wordt gecontroleerd op updates. Mogelijk wordt een geplande update geïnstalleerd voordat het apparaat controleert of er nieuwe updates zijn. Als het betreffende apparaat is uitgeschakeld wanneer u de opdracht voor onderbreken opgeeft, kan dit apparaat, wanneer het wordt ingeschakeld, geplande updates downloaden en installeren voordat er bij Intune wordt gecontroleerd op nieuwe updates.

#### <a name="resume"></a>Hervatten

Als een updatering is onderbroken, kunt u **Hervatten** selecteren om de onderdelenupdates en kwaliteitsupdates voor deze ring opnieuw te activeren. Als u een updatering hervat, kunt u deze ring opnieuw onderbreken.

##### <a name="to-resume-a-ring"></a>Een ring hervatten

1. Selecteer **Hervatten** tijdens het weergeven van de overzichtspagina voor een onderbroken updatering.
2. Selecteer de beschikbare opties om **onderdelenupdates** of **kwaliteitsupdates** te hervatten, en selecteer vervolgens **OK**.
3. Als u één type update hebt hervat, kunt u opnieuw Hervatten selecteren om ook het andere updatetype te hervatten.

#### <a name="extend"></a>Uitbreiden  

Als een updatering is onderbroken, kunt u **Uitbreiden** selecteren om de onderbrekingsperiode voor zowel onderdelenupdates als kwaliteitsupdates opnieuw in te stellen op 35 dagen.

##### <a name="to-extend-the-pause-period-for-a-ring"></a>De onderbrekingsperiode voor een ring uitbreiden

1. Selecteer **Uitbreiden** tijdens het weergeven van de overzichtspagina voor een onderbroken updatering.
2. Selecteer de beschikbare opties om **onderdelenupdates** of **kwaliteitsupdates** te hervatten, en selecteer vervolgens **OK**.
3. Als u één type update hebt uitgebreid, kunt u opnieuw Uitbreiden selecteren om ook het andere updatetype uit te breiden.

#### <a name="uninstall"></a>Verwijderen  

Een Intune-beheerder kan **Verwijderen** gebruiken om de meest recente *onderdelenupdate* of de meest recente *kwaliteitsupdate* te verwijderen (terug te draaien) voor een actieve of onderbroken updatering. Nadat u één type hebt verwijderd, kunt u vervolgens ook het andere type verwijderen. Intune biedt geen ondersteuning voor het verwijderen van updates door gebruikers.  

> [!IMPORTANT]
> Wanneer u de optie *Verwijderen* gebruikt, wordt de aanvraag voor verwijderen in Intune onmiddellijk doorgegeven aan apparaten.
>
> - Verwijderen van updates op Windows-apparaten wordt gestart zodra deze de wijziging in Intune-beleid ontvangen. Het verwijderen van updates is niet beperkt tot onderhoudsplanningen, zelfs wanneer ze zijn geconfigureerd als onderdeel van de updatering.
> - Als voor het verwijderen van updates is vereist dat het apparaat opnieuw wordt opgestart, wordt het apparaat opgestart zonder dat gebruikers de mogelijkheid hebben om dit uit te stellen.

Om te kunnen verwijderen:

- Moet op een apparaat de Windows-update van 10 april 2018 (versie 1803) of hoger actief zijn.

Moet op een apparaat de meest recente update zijn geïnstalleerd. Omdat updates cumulatief zijn, beschikken apparaten waarop de meest recente updates zijn geïnstalleerd, ook de meest recente onderdelenupdates en kwaliteitsupdates. Een voorbeeld van het gebruik van deze optie is om de nieuwste update terug te draaien, mocht u een ernstig probleem ondervinden op uw Windows 10-computers.

Houd rekening met het volgende als u Verwijderen gebruikt:

- U kunt alleen een functie- of kwaliteitsupdate verwijderen voor het servicekanaal waarop het apparaat zich bevindt.

- Als u Verwijderen gebruikt voor onderdelenupdates of kwaliteitsupdates, wordt een beleid geactiveerd waarmee de vorige update op uw Windows 10-computers wordt hersteld.

- Op een Windows 10-apparaat blijven apparaatgebruikers, nadat de kwaliteitsupdate is teruggedraaid, de update wel zien in **Windows-instellingen** > **Updates** > **Geschiedenis van updates**.

- Specifiek voor onderdelenupdates is de periode die u de update kunt verwijderen beperkt van 2-60 dagen. Deze periode wordt geconfigureerd door de update-instelling voor updateringen **Periode instellen voor onderdelenupdate verwijderen (2-60 dagen)** . U kunt een onderdelenupdate die is geïnstalleerd op een apparaat, niet terugdraaien als het installeren van deze onderdelenupdate langer geleden is dan de geconfigureerde periode voor verwijderen.

  Neem bijvoorbeeld een update-ring met een verwijderingsperiode voor onderdelenupdates van 20 dagen. Na 25 dagen besluit u de laatste onderdelenupdate terug te draaien, en gebruikt u de optie Verwijderen.  Op apparaten waarop de functie-update meer dan 20 dagen geleden is geïnstalleerd, is verwijderen niet mogelijk, omdat de vereiste bits als onderdeel van het onderhoud zijn verwijderd. Op apparaten waar de onderdelenupdate nog maar negentien dagen geleden is geïnstalleerd, kan de update wel worden verwijderd, als ze zich aanmelden om de verwijderopdracht te ontvangen voordat de verwijderingsperiode van twintig dagen is verstreken.

Zie [CSP bijwerken](https://docs.microsoft.com/windows/client-management/mdm/update-csp) in de beheerdocumentatie voor Windows-clients voor meer informatie over Windows Update.

##### <a name="to-uninstall-the-latest-windows-10-update"></a>De meest recente Windows 10-update verwijderen

1. Selecteer **Verwijderen** tijdens het weergeven van de overzichtspagina voor een onderbroken updatering.
2. Selecteer de beschikbare opties om **onderdelenupdates** of **kwaliteitsupdates** te verwijderen, en selecteer vervolgens **OK**.
3. Als u het verwijderen van één type update hebt geactiveerd, kunt u opnieuw Verwijderen selecteren om ook het resterende updatetype te verwijderen.

## <a name="windows-10-feature-updates"></a>Windows 10-onderdelenupdates

*Deze functie is beschikbaar voor openbare preview.*

Met *Windows 10-onderdelenupdates* selecteert u de Windows-onderdelenversie die op de apparaten moet blijven werken, zoals Windows 10 versie 1803 of versie 1809. U kunt een onderdelenniveau van 1803 of hoger instellen.

Wanneer een apparaat een beleid voor Windows 10-onderdelenupdates ontvangt:

- Het apparaat wordt bijgewerkt naar de versie van Windows die is opgegeven in het beleid. Een apparaat waarop al een nieuwere versie van Windows wordt uitgevoerd, behoudt de huidige versie. Door de versie te bevriezen, blijft de onderdelenset van het apparaat ingesteld voor de duur van het beleid.

- Terwijl de geïnstalleerde versie van Windows aanwezig blijft, kunnen apparaten kwaliteits- en beveiligingsupdates voor hun Windows-versie ontvangen en installeren voor de duur van de ondersteuning voor die versie, waarmee u apparaten actueel en beveiligd kunt houden.

- In tegenstelling tot het gebruik van *Pauzeren* met een updatering, dat na 35 dagen verloopt, blijft het beleid voor de onderdelenupdates van Windows 10 van kracht. Apparaten installeren pas een nieuwe Windows-versie als u het beleid voor de onderdelenupdates voor Windows 10 wijzigt of verwijdert. Als u het beleid bewerkt om een nieuwere versie op te geven, kunnen apparaten de functies installeren vanuit die Windows-versie.

### <a name="limitations-for-windows-10-feature-updates"></a>Beperkingen voor Windows 10-onderdelenupdates

- Wanneer u een beleid voor *Windows 10-onderdelenupdates* voor een *Windows 10-updatering* implementeert, controleert u de updatering op de volgende configuraties:
  - De **Uitstelperiode voor onderdelenupdates (dagen)** moet zijn ingesteld op **0**.
  - Onderdelenupdates voor de updatering moeten *actief* zijn. Ze mogen niet worden gepauzeerd.

- Beleidsregels voor de Windows 10-onderdelenupdate kunnen niet worden toegepast tijdens OOBE (Out of Box Experience) en worden alleen toegepast nadat de eerste scan van Windows Update is uitgevoerd nadat een apparaat is ingericht (doorgaans een dag). Ook worden de beleidsregels niet ontvangen op apparaten die zijn ingericht met Autopilot.

  Momenteel wordt onderzocht of deze beperking in de toekomst kan worden ondersteund.


### <a name="create-and-assign-windows-10-feature-updates"></a>Windows 10-onderdelenupdates maken en toewijzen

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecteer **Apparaten** > **Windows** > **Windows 10-onderdelenupdates** > **Maken**.

3. Geef onder **Basisinformatie** een naam en een beschrijving (optioneel) op en selecteer voor **De functie-update die moet worden geïmplementeerd** de versie van Windows met de gewenste onderdelenset. Selecteer daarna **volgende**.

4. Kies onder **Toewijzingen** de optie **Groepen selecteren die moeten worden opgenomen** en wijs de updatering toe aan een of meer groepen. Selecteer **Volgende** om door te gaan.

5. Controleer de instellingen onder **Beoordelen en maken** en selecteer **Maken** als u klaar bent om het beleid voor Windows 10-onderdelenupdates op te slaan.  

### <a name="manage-windows-10-feature-updates"></a>Windows 10-onderdelenupdates beheren

Navigeer in het beheercentrum naar **Apparaten** > **Windows** > **Windows 10-onderdelenupdates** en selecteer het beleid dat u wilt beheren. Het beleid wordt geopend met het deelvenster **Overzicht**.

In dit deelvenster kunt u het volgende doen:

- **Verwijderen** selecteren om het beleid uit Intune te verwijderen en het van apparaten te verwijderen.
- **Eigenschappen** selecteren om de implementatie te wijzigen.  In het deelvenster *Eigenschappen* de optie **Bewerken** selecteren om de *Implementatie-instellingen of Toewijzingen* te openen, waar u de implementatie vervolgens kunt wijzigen.
- **Updatestatus van eindgebruiker** selecteren om informatie over het beleid weer te geven.

## <a name="migrate-update-settings-to-the-azure-portal"></a>Update-instellingen migreren naar de Azure-portal

De klassieke Azure-portal heeft ook een beperkt aantal andere instellingen voor Windows 10-updates in het apparaatconfiguratieprofiel. Als een van deze instellingen is geconfigureerd wanneer u naar de Azure-portal migreert, worden de volgende acties aangeraden:

1. Maak Windows 10 updateringen in de Azure-portal met de instellingen die u nodig hebt. De instelling **Functies van evaluatieversies toestaan** wordt niet ondersteund in Azure Portal omdat deze niet langer van toepassing is op de meest recente builds van Windows 10. U kunt de andere drie instellingen en de andere update-instellingen voor Windows 10 configureren wanneer u update-ringen maakt.

   > [!NOTE]
   > Instellingen voor Windows 10-updates die zijn gemaakt in de klassieke portal worden na de migratie niet weergegeven in de Azure-portal. Deze instellingen worden echter toegepast. Als u deze instellingen migreert en het gemigreerde beleid bewerkt in Azure Portal, worden deze instellingen verwijderd uit het beleid.

2. Verwijder de update-instellingen in de klassieke portal. Nadat u naar Azure Portal bent gemigreerd en dezelfde instellingen toevoegt aan een update-ring, moet u de instellingen in de klassieke portal verwijderen om mogelijke beleidsconflicten te voorkomen. Wanneer dezelfde instelling bijvoorbeeld met verschillende waarden wordt geconfigureerd, is er sprake van een conflict. Er is geen eenvoudige manier om hierachter te komen, omdat de instelling die in de klassieke portal is geconfigureerd niet in Azure-portal wordt weergegeven.

## <a name="next-steps"></a>Volgende stappen

[Update-instellingen van Windows worden ondersteund in Intune](../windows-update-settings.md)

[Intune-nalevingsrapporten voor updates](../windows-update-compliance-reports.md)

[Problemen met Windows 10-update-ringen oplossen](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Troubleshooting-Windows-10-Update-Ring-Policies/ba-p/714046)

