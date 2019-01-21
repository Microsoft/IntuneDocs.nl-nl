---
title: Windows Update voor Bedrijven configureren in Microsoft Intune - Azure | Microsoft Docs
description: Werk met Microsoft Intune op Windows 10-apparaten de instellingen voor Software-update in een profiel bij om een update-ring te maken, naleving te controleren en updates in de instellingen voor Windows Update voor bedrijven te onderbreken.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/15/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: coryfe
ms.suite: ems
search.appverid: MET150
ms.openlocfilehash: ccb91082a3226ec4091a139d31796fd77bdf0616
ms.sourcegitcommit: e9ba1280b95565a5c5674b825881655d0303e688
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54297380"
---
# <a name="manage-software-updates-in-intune"></a>Software-updates beheren in Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Windows as a Service is dé manier om Windows 10-apparaten bij te werken. In Windows 10 bevatten nieuwe functie-updates en kwaliteitsupdates de inhoud van alle voorgaande updates. Dit houdt in dat, als u de nieuwste update hebt geïnstalleerd, u zeker weet dat uw Windows 10-apparaten zijn bijgewerkt. In tegenstelling tot eerdere versies van Windows, moet u nu de volledige update installeren in plaats van een onderdeel van een update.

Met behulp van Windows Update voor Bedrijven kunt u de updatebeheerervaring vereenvoudigen. U hoeft geen afzonderlijke updates voor apparaatgroepen goed te keuren. U kunt het risico in uw omgevingen beheren door een strategie voor het implementeren van updates te configureren. En Windows Update zorgt ervoor dat updates op het juiste moment worden geïnstalleerd. Microsoft Intune biedt de mogelijkheid update-instellingen op apparaten te configureren en biedt u de mogelijkheid de installatie van updates uit te stellen. Intune slaat de updates niet op, maar alleen de beleidstoewijzing voor de update. Apparaten maken direct verbinding met Windows Update voor de updates. U kunt Intune gebruiken voor het configureren en beheren van **Windows 10-updateringen**. Een update-ring bevat een aantal instellingen waarin is geconfigureerd wanneer en hoe Windows 10-updates worden geïnstalleerd. U kunt bijvoorbeeld de volgende instellingen configureren:

- **Windows 10 Servicing-kanaal**: Kies het Servicing-kanaal van waaruit u updates naar apparaatgroepen wilt sturen. De volgende kanalen zijn beschikbaar: 
  - Semi&#8208;Annual-kanaal
  - Semi&#8208;Annual-kanaal (Targeted)
  - Windows Insider &#8208; snel
  - Windows Insider &#8208; langzaam
  - Windows Insider vrijgeven 
      
  Zie [Overzicht voor Windows als een Service](https://docs.microsoft.com/windows/deployment/update/waas-overview#servicing-channels) voor meer informatie over de beschikbare onderhoudskanalen.
- **Instellingen voor uitstel**: Configureer instellingen voor het uitstellen van updates om de installatie van updates voor groepen apparaten uit te stellen. U kunt deze instellingen gebruiken voor een gefaseerde update-implementatie, zodat u de voortgang kunt controleren.
- **Pauzeren**: Als er zich een probleem voordoet tijdens het uitrollen van de update, kunt u de installatie van de update uitstellen. 
- **Onderhoudsvenster**: Configureer de tijden waarop de updates kunnen worden geïnstalleerd.
- **Type update**: Kies welke typen updates worden geïnstalleerd. Bijvoorbeeld kwaliteitsupdates, upgrades van onderdelen of stuurprogramma’s.
- **Installatiegedrag**: Hiermee configureert u hoe de update wordt geïnstalleerd. Bijvoorbeeld, wordt het apparaat automatisch opnieuw opgestart na de installatie?
- **Peer-download**: U kunt opgeven of u peer-downloaden wilt configureren. Als deze optie is geconfigureerd, kunnen andere apparaten een update downloaden van een apparaat dat het downloaden van de update heeft voltooid. Hierdoor wordt het downloadproces versneld.

Nadat u de updateringen hebt gemaakt, kunt u deze toewijzen aan groepen apparaten. Als u updateringen gebruikt, kunt u een updatestrategie maken die overeenkomt met de behoeften van uw bedrijf. Zie [Manage updates using Windows Update for Business](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb) (Updates beheren met Windows Update voor Bedrijven) voor meer informatie.

## <a name="before-you-start"></a>Voordat u begint

- Als u Windows 10-computers wilt bijwerken, moet hier ten minste Windows 10 Pro met de speciale Windows Jubileumupdate worden uitgevoerd.

- Windows Update ondersteunt de volgende versies van Windows 10:
  - Windows 10
  - Windows 10 Team (voor Surface Hub-apparaten)
  - [Windows Holographic for Business](#windows-holographic-for-business-support)

  Apparaten met Windows 10 Mobile worden niet ondersteund.

- Op Windows-apparaten moet **Feedback en diagnostische gegevens** > **Diagnostische gegevens en gebruiksgegevens** ten minste zijn ingesteld op **Basic**.

    ![Windows-instelling voor diagnostische gegevens en gebruiksgegevens](./media/telemetry-basic.png)

    U kunt deze instelling handmatig configureren of een Intune-profiel voor Windows 10 en hoger gebruiken (**Apparaatbeperkingen** > **Rapporten en telemetrie** > stel **Verbruiksgegevens delen** in op minimaal **Basis**). Zie [Instellingen voor apparaatbeperking configureren](device-restrictions-configure.md) voor meer informatie over apparaatprofielen.

- De klassieke Azure-portal heeft ook een beperkt aantal andere instellingen voor Windows 10-updates in het apparaatconfiguratieprofiel. Als een van deze instellingen is geconfigureerd wanneer u naar Azure Portal migreert, wordt het volgende aangeraden:

  1. Maak Windows 10 updateringen in de Azure-portal met de instellingen die u nodig hebt. De instelling **Functies van evaluatieversies toestaan** wordt niet ondersteund in Azure Portal omdat deze niet langer van toepassing is op de meest recente builds van Windows 10. U kunt de andere instellingen, evenals andere instellingen voor Windows 10-updates, configureren wanneer u update-ringen maakt.

   > [!NOTE]
   > Instellingen voor Windows 10-updates die zijn gemaakt in de klassieke portal worden na de migratie niet weergegeven in de Azure-portal. Deze instellingen worden echter toegepast. Als u deze instellingen migreert en het gemigreerde beleid bewerkt in Azure Portal, worden deze instellingen verwijderd uit het beleid.

  2. Verwijder de update-instellingen in de klassieke portal. Nadat u naar Azure Portal bent gemigreerd en dezelfde instellingen toevoegt aan een update-ring, moet u de instellingen in de klassieke portal verwijderen om mogelijke beleidsconflicten te voorkomen. Wanneer dezelfde instelling bijvoorbeeld met verschillende waarden wordt geconfigureerd, is er sprake van een conflict. Er is geen eenvoudige manier om hierachter te komen, omdat de instelling die in de klassieke portal is geconfigureerd niet in Azure Portal wordt weergegeven.

## <a name="create-and-assign-update-rings"></a>Update-ringen maken en toewijzen

1. Selecteer in [Azure Portal](https://portal.azure.com) **Alle services** > filter op **Intune** en selecteer vervolgens **Microsoft Intune**.
2. Selecteer **Software-updates** > **Windows 10-update-ringen** > **Maken**.
3. Voer een naam en een beschrijving (optioneel) in en kies vervolgens **Configureren**.
4. Voer bij **Instellingen** de volgende informatie in:  

   **Update-instellingen**  
   - **Servicekanaal**: Stel het kanaal in van waaruit het apparaat Windows-updates ontvangt.
   - **Microsoft-productupdates**: Kies of u wilt zoeken naar app-updates via Microsoft Update.
   - **Windows-stuurprogramma's**: Kies of u Windows Update-stuurprogramma's wilt uitsluiten tijdens het bijwerken.
   - **Uitstelperiode voor kwaliteitsupdates (dagen)**: Geef het aantal dagen op dat kwaliteitsupdates worden uitgesteld. U kunt deze kwaliteitsupdates uitstellen gedurende maximaal 30 dagen vanaf de vrijgave.

     Kwaliteitsupdates zijn doorgaans oplossingen en verbeteringen in de bestaande Windows-functionaliteit. Deze worden op de tweede dinsdag van elke maand gepubliceerd. Kwaliteitsupdates via Windows Update voor Bedrijven ontvangen alleen deze updates (versie B), hoewel Microsoft van tijd tot tijd andere updates kan publiceren. U kunt bepalen of en hoe lang u ontvangen kwaliteitsupdates wilt uitstellen nadat ze beschikbaar zijn gekomen in Windows Update. Zie [Deploy updates using Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) (Updates implementeren met Windows Update voor Bedrijven) voor meer informatie.

   - **Uitstelperiode voor onderdelenupdates (dagen)**: Geef het aantal dagen op dat onderdelenupdates worden uitgesteld. U kunt deze functie-updates uitstellen gedurende maximaal 180 dagen vanaf de vrijgave.

     Upgrades van onderdelen zijn over het algemeen nieuwe functies van Windows. Nadat u de instelling voor het **Servicing-kanaal** hebt geconfigureerd, kunt u definiëren of en hoe lang u ontvangen functie-updates uitstelt nadat deze beschikbaar zijn gekomen in Windows Update.

     Bijvoorbeeld: **Als het servicekanaal is ingesteld op Semi-Annual-kanaal (Targeted) en de uitstelperiode 30 dagen is**: Stel dat Onderdelenupdate X voor het eerst openbaar beschikbaar is op Windows Update als Semi-Annual-kanaal (Targeted) in januari. Het apparaat ontvangt de update pas in februari - 30 dagen later.

     **Als het servicekanaal is ingesteld op Semi-Annual-kanaal en de uitstelperiode 30 dagen is**: Stel, de Onderdelenupdate X is voor het eerst openbaar beschikbaar op Windows Update als Semi-Annual-kanaal (Targeted) in januari. Vier maanden later, in april, wordt onderdelenupdate X vrijgegeven voor Semi-Annual-kanaal. Het apparaat ontvangt de onderdelenupdate 30 dagen na deze Semi-Annual-kanaal-vrijgave en wordt in mei bijgewerkt.  

   **Instellingen voor gebruikerservaring**
   
   - **Gedrag van automatische updates**: Kies hoe automatische updates worden geïnstalleerd, wanneer het apparaat opnieuw moet gestart of opnieuw moet worden opgestart. Zie [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#update-allowautoupdate) voor meer informatie.

     Met de instelling *Standaardinstellingen herstellen* herstelt u de oorspronkelijke instellingen voor automatisch bijwerken op Windows 10-computers met de *update van oktober 2018* of later.  

     - **Frequentie van automatisch gedrag**: Als u **Automatisch installeren en opnieuw starten op een geplande tijd** voor het updategedrag selecteert, wordt deze instelling weergegeven. Gebruik deze instelling om te plannen wanneer updates worden geïnstalleerd, inclusief de week, de dag en het tijdstip.

   - **Controles voor opnieuw starten**: Standaard ingeschakeld. Wanneer u een apparaat opnieuw start, worden er een aantal controles uitgevoerd. Zo wordt bijvoorbeeld gecontroleerd op actieve gebruikers, batterijniveau, actieve games en meer. Als u deze controles wilt overslaan wanneer u een apparaat opnieuw start, kiest u **Overslaan**.

   - **Blokkeren dat gebruiker Windows-updates kan onderbreken**: Standaard toegestaan. Gebruik deze instelling om toe te staan of te voorkomen dat gebruikers de installatie van een update onderbreken vanuit de *Instellingen* van hun computer. 
      
   - **Delivery Optimization-downloadmodus**: Delivery Optimization wordt niet meer als onderdeel van een update-ring voor Windows 10 geconfigureerd onder Software-updates. Delivery Optimization wordt nu ingesteld via de apparaatconfiguratie. Eerdere configuraties blijven echter beschikbaar in de console. U kunt deze eerdere configuraties verwijderen door ze te bewerken en te markeren als *Niet geconfigureerd*, maar verder kunnen ze niet worden gewijzigd. Zie [Verplaatsen van bestaande update-ringen naar Delivery Optimization](delivery-optimization-windows.md#move-from-existing-update-rings-to-delivery-optimization) om conflicten tussen nieuwe en oude beleidsregels te voorkomen en uw instellingen vervolgens te verplaatsen naar een Delivery Optimization-profiel. 

5. Wanneer u klaar bent, selecteert u **OK**. Selecteer in **Update-ring maken** de optie **Maken**.

De nieuwe updatering wordt weergegeven in de lijst met updateringen.

1. Als u de ring wilt toewijzen, selecteert u een ring in de lijst met updateringen en klikt u op het tabblad *Ringnaam* > en kiest u **Toewijzingen**.
2. Kies op het volgende tabblad **Groepen selecteren om op te nemen** en kies vervolgens de groepen waaraan u deze ring wilt toewijzen.
3. Als u klaar bent, kiest u **Selecteren** om de toewijzing te voltooien.

## <a name="update-compliance-reporting"></a>Update-nalevingsrapportages
Met de gratis oplossing Update Compliance kunt u de updatenaleving weergeven in Intune.

### <a name="review-update-compliance-in-intune"></a>Updatenaleving weergeven in Intune 
<!-- 1352223 --> Een beleidsrapport weergeven met de implementatiestatus voor de Windows 10-updateringen die u hebt geconfigureerd.

1. Selecteer in [Azure Portal](https://portal.azure.com) **Alle services** > filter op **Intune** en selecteer vervolgens **Microsoft Intune**.
2. Selecteer **Software-updates** > **Overzicht**. Hier wordt algemene informatie weergegeven over de status van de update-ringen die u hebt toegewezen.
3. Open een van de volgende rapporten:

   **Voor alle implementatieringen**:  
   1. In het deelvenster **Software-updates** > **Windows 10-update-ringen**
   2. In de sectie **Bewaken** kiest u **Implementatiestatus per updatering**.

   **Voor specifieke implementatieringen**:  
   1. Kies in **Software-updates** > **Windows 10-update-ringen** de implementatiering die u wilt weergeven.
   2. Kies in de sectie **Bewaken** een van de volgende rapporten om meer gedetailleerde informatie over de implementatiering weer te geven:
      - **Apparaatstatus**
      - **Gebruikersstatus**

### <a name="review-update-compliance-using-oms"></a>Updatenaleving weergeven in OMS
Met de gratis oplossing Update Compliance kunt u de Windows 10 update-implementatie bewaken. Zie [Monitor Windows Updates with Update Compliance](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor) (Windows-updates bewaken met Update Compliance) voor meer informatie. Wanneer u deze oplossing gebruikt, kunt u een commerciële id implementeren op elk van uw door Intune beheerde Windows 10-apparaten waarvoor u over de naleving van updates wilt rapporteren.

In Intune kunt u de OMA-URI-instellingen van een aangepast beleid gebruiken om de commerciële id te configureren. Zie [Beleidsinstellingen voor Windows 10-apparaten in Microsoft Intune](custom-settings-windows-10.md) voor meer informatie.   

Het pad voor de OMA-URI (hoofdlettergevoelig) voor het configureren van de commerciële id is: ./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID

U kunt bijvoorbeeld de volgende waarden gebruiken in **OMA-URI-instelling toevoegen of bewerken**:

- **Naam van instelling**: Commerciële id voor Windows Analytics
- **Beschrijving van instelling**: Commerciële id voor Windows Analytics-oplossingen configureren
- **OMA-URI** (hoofdlettergevoelig): ./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID
- **Gegevenstype**: Tekenreeks
- **Waarde**: <*gebruik de GUID die wordt weergegeven op het tabblad Windows-telemetrie in uw OMS-werkruimte*>

![OMA-URI-instelling - rij bewerken](./media/commID-edit.png)

> [!NOTE]
> Zie [DMClient configuratieserviceprovider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/dmclient-csp) voor meer informatie over MS DM Server.

## <a name="pause-updates"></a>Updates onderbreken
U kunt het ontvangen van upgrades voor onderdelen of kwaliteitsupdates op een apparaat onderbreken gedurende een periode van maximaal 35 dagen vanaf het moment waarop u de updates onderbreekt. Als het maximum aantal dagen is verstreken, verloopt de functionaliteit voor onderbreken automatisch en zoekt het apparaat in Windows Update naar toepasselijke updates. Na deze scan kunt u de updates opnieuw onderbreken.

1. Selecteer in [Azure Portal](https://portal.azure.com) **Alle services** > filter op **Intune** en selecteer vervolgens **Microsoft Intune**.
2. Selecteer **Software-updates** > **Windows 10-update-ringen**.
3. Kies in de lijst met update-ringen de ring die u wilt onderbreken en kies vervolgens **...**   >  **Kwaliteitsupdates onderbreken** > of **Onderdelenupdates onderbreken**, afhankelijk van het type updates dat u wilt onderbreken.

> [!IMPORTANT]
> Wanneer u een opdracht voor onderbreken opgeeft, ontvangen apparaten deze opdracht de volgende keer dat bij de service wordt gecontroleerd op updates. Mogelijk wordt een geplande update geïnstalleerd voordat het apparaat controleert of er nieuwe updates zijn.
> Als het betreffende apparaat is uitgeschakeld wanneer u de opdracht voor onderbreken opgeeft, kan dit apparaat, wanneer het wordt ingeschakeld, geplande updates downloaden en installeren voordat er bij Intune wordt gecontroleerd op nieuwe updates.

### <a name="uninstall-the-latest-from-windows-10-software-updates"></a>De nieuwste versie van software-updates voor Windows 10 verwijderen 
Als u een probleem ontdekt op uw Windows 10-computers, kunt u de meest recente functie-update of de nieuwste kwaliteitsupdate verwijderen (terugdraaien). U kunt alleen een functie- of kwaliteitsupdate verwijderen voor het servicekanaal waarop het apparaat zich bevindt. Door de verwijdering wordt een beleid geactiveerd waarmee de vorige update op uw Windows 10-computers wordt hersteld. Specifiek voor functie-updates kunt u de tijd beperken van 2 tot 60 dagen waarin een verwijdering van de meest recente versie kan worden toegepast. Verwijderopties voor software-updates instellen:

1. Selecteer **Software-updates** in Intune.
2. Selecteer **Windows 10-update-ringen** > selecteer een bestaande update-ring > **Verwijderen**.

> [!NOTE]
> Op Windows 10-computers blijven gebruikers, nadat de kwaliteitsupdate is teruggedraaid, de update wel zien in **Windows-instellingen** > **Updates** > **Geschiedenis van updates**.

## <a name="windows-holographic-for-business-support"></a>Ondersteuning voor Windows Holographic for Business

De volgende instellingen worden in Windows Holographic for Business ondersteund:

- **Gedrag van automatische updates**
- **Productupdates van Microsoft**
- **Servicekanaal**: Ondersteunt de opties **Semi-Annual-kanaal** en **Semi-Annual-kanaal (Targeted)**
