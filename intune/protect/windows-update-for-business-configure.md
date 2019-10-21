---
title: Windows Update voor Bedrijven configureren in Microsoft Intune - Azure | Microsoft Docs
description: Werk met Microsoft Intune op Windows 10-apparaten de instellingen voor Software-update in een profiel bij om een update-ring te maken, naleving te controleren en updates in de instellingen voor Windows Update voor bedrijven te onderbreken.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: coryfe
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: aa8cc396c05150006799c1e9b86ecb63351cdb36
ms.sourcegitcommit: 45d7c76e760c5117bf134fb57f7e248e5b6c4ad5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/15/2019
ms.locfileid: "72314719"
---
# <a name="manage-software-updates-in-intune"></a>Software-updates beheren in Intune

Gebruik Intune om updateringen te definiëren die aangeven hoe en wanneer uw Windows 10-apparaten worden bijgewerkt via Windows als een service. Updateringen zijn beleidsregels die u toewijst aan een groep apparaten. Als u updateringen gebruikt, kunt u een updatestrategie maken die overeenkomt met de behoeften van uw bedrijf. Zie [Manage updates using Windows Update for Business](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb) (Updates beheren met Windows Update voor Bedrijven) voor meer informatie.

In Windows 10 bevatten nieuwe functie-updates en kwaliteitsupdates de inhoud van alle voorgaande updates. Dit houdt in dat, als u de nieuwste update hebt geïnstalleerd, u zeker weet dat uw Windows 10-apparaten zijn bijgewerkt. In tegenstelling tot eerdere versies van Windows, moet u nu de volledige update installeren in plaats van een onderdeel van een update.


Met behulp van Windows Update voor Bedrijven kunt u de updatebeheerervaring vereenvoudigen. U hoeft geen afzonderlijke updates voor apparaatgroepen goed te keuren. U kunt het risico in uw omgevingen beheren door een strategie voor het implementeren van updates te configureren. Intune biedt de mogelijkheid [update-instellingen te configureren](../windows-update-settings.md) op apparaten, en biedt u de mogelijkheid de installatie van updates uit te stellen. Intune slaat de updates niet op, maar alleen de beleidstoewijzing voor de update. Apparaten maken direct verbinding met Windows Update voor de updates. Deze verzameling instellingen die wordt geconfigureerd wanneer Windows 10-updates worden geïnstalleerd, heet een *Windows 10-updatering*.

Windows 10-updateringen bieden ondersteuning voor [bereiktags](../fundamentals/scope-tags.md). U kunt bereiktags gebruiken om u te helpen de configuratiesets die u gebruikt, te filteren en te beheren.

## <a name="prerequisites"></a>Vereisten  

Aan de volgende vereisten moet worden voldaan om Windows-updates voor Windows 10-apparaten te kunnen gebruiken in Intune.  

- Op Windows 10-pc’s moet minstens Windows 10 Pro worden uitgevoerd, met de Windows Jubileumupdate of hoger (versie 1607 of hoger)
- Windows Update biedt ondersteuning voor de volgende edities van Windows 10:
  - Windows 10
  - Windows 10 Team (voor Surface Hub-apparaten)
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


## <a name="create-and-assign-update-rings"></a>Update-ringen maken en toewijzen

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Selecteer **Software-updates** > **Windows 10-update-ringen** > **Maken**.
4. Voer een naam en een beschrijving (optioneel) in en kies vervolgens **Configureren**.
5. Configureer in **Instellingen** de instellingen die passen bij de behoeften van uw bedrijf. Zie [Windows-update-instellingen](../windows-update-settings.md) voor meer informatie over de beschikbare instellingen.  
6. Wanneer u klaar bent, selecteert u **OK**. Selecteer in **Update-ring maken** de optie **Maken**. De nieuwe updatering wordt weergegeven in de lijst met updateringen.
7. Als u de ring wilt toewijzen, selecteert u een ring in de lijst met updateringen en klikt u op het \<tabblad>Ringnaam en kiest u **Toewijzingen**.
8. Gebruik de tabbladen **Opnemen** en **Uitsluiten** om te definiëren aan welke groepen deze ring wordt toegewezen, en selecteer vervolgens **Opslaan** om de toewijzing te voltooien.

## <a name="manage-your-windows-10-update-rings"></a>Uw Windows 10-updateringen beheren
In de portal kunt u een Windows 10-updatering selecteren om het bijbehorende deelvenster **Overzicht** te openen. Vanuit dit deelvenster kunt u de toewijzingsstatus van ringen bekijken en aanvullende acties ondernemen om de ring te beheren. 
### <a name="to-view-an-updates-rings-overview-pane"></a>Het deelvenster Overzicht van een updatering weergeven: 
1. Meld u aan bij Azure Portal.
2. Navigeer naar **Intune** > **Software-updates** > **Windows 10-updateringen**.
3. Selecteer de updatering die u wilt bekijken of beheren.  

Naast het weergeven van de toewijzingsstatus kunt u ook boven aan het deelvenster Overzicht de volgende acties selecteren om de updatering te beheren:  
- [Verwijderen](#delete)  
- [Onderbreken](#pause)  
- [Hervatten](#resume)  
- [Uitbreiden](#extend)  
- [Verwijderen](#uninstall)  

![Beschikbare acties](./media/windows-update-for-business-configure/overview-actions.png)

### <a name="delete"></a>Verwijderen  
Selecteer **Verwijderen** om te stoppen met het afdwingen van de instellingen van de geselecteerde Windows 10-updatering. Als u een ring verwijdert, wordt ook de bijbehorende configuratie uit Intune verwijderd, waardoor deze instellingen niet meer worden toegepast en afgedwongen in Intune.  

Als u een ring verwijdert uit Intune, worden de instellingen op apparaten waaraan de updatering is toegewezen, niet gewijzigd.  In plaats hiervan behoudt het apparaat de huidige instellingen. Apparaten behouden geen historisch overzicht van de instellingen die ze eerder hebben bewaard. Apparaten kunnen ook instellingen ontvangen van extra updateringen die actief blijven.  

#### <a name="to-delete-a-ring"></a>Een ring verwijderen  
1. Selecteer **Verwijderen** tijdens het weergeven van de overzichtspagina voor een updatering.  
2. Selecteer **OK**.  

### <a name="pause"></a>Onderbreken  
Selecteer **Onderbreken** om te voorkomen dat toegewezen apparaten gedurende maximaal 35 dagen vanaf het moment waarop u de ring onderbreekt, onderdelenupdates of kwaliteitsupdates ontvangen. Als het maximum aantal dagen is verstreken, verloopt de functionaliteit voor onderbreken automatisch en zoekt het apparaat in Windows Update naar toepasselijke updates. Na deze scan kunt u de updates opnieuw onderbreken. Als u een onderbroken updatering hervat, en deze ring vervolgens opnieuw onderbreekt, wordt de onderbrekingsperiode opnieuw ingesteld op 35 dagen.  

#### <a name="to-pause-a-ring"></a>Een ring onderbreken  
1. Selecteer **Onderbreken** tijdens het weergeven van de overzichtspagina voor een updatering.  
2. Selecteer **Onderdeel** of **Kwaliteit** om het gewenste type update te onderbreken, en selecteer vervolgens **OK**.  
3. Als u één type update hebt onderbroken, kunt u opnieuw Onderbreken selecteren om ook het andere updatetype te onderbreken.  

Wanneer een updatetype is onderbroken, wordt op het deelvenster Overzicht van deze ring weergegeven hoeveel dagen nog resteren voordat het updatetype wordt hervat.

> [!IMPORTANT]  
> Nadat u een opdracht voor onderbreken opgeeft, ontvangen apparaten deze opdracht de volgende keer dat bij de service wordt gecontroleerd op updates. Mogelijk wordt een geplande update geïnstalleerd voordat het apparaat controleert of er nieuwe updates zijn. Als het betreffende apparaat is uitgeschakeld wanneer u de opdracht voor onderbreken opgeeft, kan dit apparaat, wanneer het wordt ingeschakeld, geplande updates downloaden en installeren voordat er bij Intune wordt gecontroleerd op nieuwe updates.

### <a name="resume"></a>Hervatten  
Als een updatering is onderbroken, kunt u **Hervatten** selecteren om de onderdelenupdates en kwaliteitsupdates voor deze ring opnieuw te activeren. Als u een updatering hervat, kunt u deze ring opnieuw onderbreken.  

#### <a name="to-resume-a-ring"></a>Een ring hervatten  
1. Selecteer **Hervatten** tijdens het weergeven van de overzichtspagina voor een onderbroken updatering.  
2. Selecteer de beschikbare opties om **onderdelenupdates** of **kwaliteitsupdates** te hervatten, en selecteer vervolgens **OK**.  
3. Als u één type update hebt hervat, kunt u opnieuw Hervatten selecteren om ook het andere updatetype te hervatten.  

### <a name="extend"></a>Uitbreiden  
Als een updatering is onderbroken, kunt u **Uitbreiden** selecteren om de onderbrekingsperiode voor zowel onderdelenupdates als kwaliteitsupdates opnieuw in te stellen op 35 dagen.  

#### <a name="to-extend-the-pause-period-for-a-ring"></a>De onderbrekingsperiode voor een ring uitbreiden  
1. Selecteer **Uitbreiden** tijdens het weergeven van de overzichtspagina voor een onderbroken updatering. 
2. Selecteer de beschikbare opties om **onderdelenupdates** of **kwaliteitsupdates** te hervatten, en selecteer vervolgens **OK**.  
3. Als u één type update hebt uitgebreid, kunt u opnieuw Uitbreiden selecteren om ook het andere updatetype uit te breiden.  

### <a name="uninstall"></a>Verwijderen  
Een Intune-beheerder kan **Verwijderen** gebruiken om de meest recente *onderdelenupdate* of de meest recente *kwaliteitsupdate* te verwijderen (terug te draaien) voor een actieve of onderbroken updatering. Nadat u één type hebt verwijderd, kunt u vervolgens ook het andere type verwijderen. Intune biedt geen ondersteuning voor het verwijderen van updates door gebruikers.  

> [!IMPORTANT] 
> Wanneer u de optie *Verwijderen* gebruikt, wordt de aanvraag voor verwijderen in Intune onmiddellijk doorgegeven aan apparaten. 
> - Verwijderen van updates op Windows-apparaten wordt gestart zodra deze de wijziging in Intune-beleid ontvangen. Het verwijderen van updates is niet beperkt tot onderhoudsplanningen, zelfs wanneer ze zijn geconfigureerd als onderdeel van de updatering. 
> - Als voor het verwijderen van updates is vereist dat het apparaat opnieuw wordt opgestart, wordt het apparaat opgestart zonder dat gebruikers de mogelijkheid hebben om dit uit te stellen.


Om te kunnen verwijderen:  
- Moet op een apparaat de Windows-update van 10 april 2018 (versie 1803) of hoger actief zijn.  

Moet op een apparaat de meest recente update zijn geïnstalleerd. Omdat updates cumulatief zijn, beschikken apparaten waarop de meest recente updates zijn geïnstalleerd, ook de meest recente onderdelenupdates en kwaliteitsupdates. Een voorbeeld van het gebruik van deze optie is om de nieuwste update terug te draaien, mocht u een ernstig probleem ondervinden op uw Windows 10-computers.  

Houd rekening met het volgende als u Verwijderen gebruikt:  
- U kunt alleen een functie- of kwaliteitsupdate verwijderen voor het servicekanaal waarop het apparaat zich bevindt.  

- Als u Verwijderen gebruikt voor onderdelenupdates of kwaliteitsupdates, wordt een beleid geactiveerd waarmee de vorige update op uw Windows 10-computers wordt hersteld.  

- Op een Windows 10-apparaat blijven gebruikers, nadat de kwaliteitsupdate is teruggedraaid, de update wel zien in **Windows-instellingen** > **Updates** > **Geschiedenis van updates**.  

- Voor onderdelenupdates is de periode gedurende welke u een update kunt verwijderen, beperkt tot 2-60 dagen. Dit is geconfigureerd met de instelling Bijwerken voor updateringen: **Periode instellen voor onderdelenupdate verwijderen (2-60 dagen)** . U kunt een onderdelenupdate die is geïnstalleerd op een apparaat, niet terugdraaien als het installeren van deze update langer geleden is dan de geconfigureerde periode voor verwijderen.  

  Neem bijvoorbeeld een update-ring met een verwijderingsperiode voor onderdelenupdates van 20 dagen. Na 25 dagen besluit u de laatste onderdelenupdate terug te draaien, en gebruikt u de optie Verwijderen.  Op apparaten waarop de onderdelenupdate meer dan 20 dagen geleden is geïnstalleerd, is verwijderen niet mogelijk, omdat de vereiste bits als onderdeel van het onderhoud zijn verwijderd. Op apparaten waar de onderdelenupdate nog maar 19 dagen geleden is geïnstalleerd, kan de update wel worden verwijderd, als ze zich aanmelden om de verwijderopdracht te ontvangen voordat de verwijderingsperiode van 20 dagen is verstreken.  

Zie [CSP bijwerken](https://docs.microsoft.com/windows/client-management/mdm/update-csp) in de beheerdocumentatie voor Windows-clients voor meer informatie over Windows Update.  

#### <a name="to-uninstall-the-latest-windows-10-update"></a>De meest recente Windows 10-update verwijderen  
1. Selecteer **Verwijderen** tijdens het weergeven van de overzichtspagina voor een onderbroken updatering.  
2. Selecteer de beschikbare opties om **onderdelenupdates** of **kwaliteitsupdates** te verwijderen, en selecteer vervolgens **OK**.  
3. Als u het verwijderen van één type update hebt geactiveerd, kunt u opnieuw Verwijderen selecteren om ook het resterende updatetype te verwijderen.  

## <a name="migrate-update-settings-to-the-azure-portal"></a>Update-instellingen migreren naar de Azure-portal  
De klassieke Azure-portal heeft ook een beperkt aantal andere instellingen voor Windows 10-updates in het apparaatconfiguratieprofiel. Als een van deze instellingen is geconfigureerd wanneer u naar de Azure-portal migreert, worden de volgende acties aangeraden:  

1. Maak Windows 10 updateringen in de Azure-portal met de instellingen die u nodig hebt. De instelling **Functies van evaluatieversies toestaan** wordt niet ondersteund in Azure Portal omdat deze niet langer van toepassing is op de meest recente builds van Windows 10. U kunt de andere drie instellingen, evenals andere instellingen voor Windows 10-updates, configureren wanneer u updateringen maakt.  

   > [!NOTE]  
   > Instellingen voor Windows 10-updates die zijn gemaakt in de klassieke portal worden na de migratie niet weergegeven in de Azure-portal. Deze instellingen worden echter toegepast. Als u deze instellingen migreert en het gemigreerde beleid bewerkt in Azure Portal, worden deze instellingen verwijderd uit het beleid.  

2. Verwijder de update-instellingen in de klassieke portal. Nadat u naar Azure Portal bent gemigreerd en dezelfde instellingen toevoegt aan een update-ring, moet u de instellingen in de klassieke portal verwijderen om mogelijke beleidsconflicten te voorkomen. Wanneer dezelfde instelling bijvoorbeeld met verschillende waarden wordt geconfigureerd, is er sprake van een conflict. Er is geen eenvoudige manier om hierachter te komen, omdat de instelling die in de klassieke portal is geconfigureerd niet in Azure-portal wordt weergegeven.  

## <a name="next-steps"></a>Volgende stappen
[Update-instellingen van Windows worden ondersteund in Intune](../windows-update-settings.md)  

[Intune-nalevingsrapporten voor updates](../windows-update-compliance-reports.md)

[Problemen met Windows 10-update-ringen oplossen](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Troubleshooting-Windows-10-Update-Ring-Policies/ba-p/714046)

