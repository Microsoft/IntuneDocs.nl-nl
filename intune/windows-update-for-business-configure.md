---
title: Instellingen voor Windows Update voor bedrijven configureren in Intune
titleSuffix: Azure portal
description: Meer informatie over het configureren van instellingen van Windows Update voor Bedrijven in Intune voor het beheren van updates voor Windows 10-apparaten."
keywords: 
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 08f659cf-715e-4e10-9ab2-1bac3c6f2366
ms.reviewer: coryfe
ms.suite: ems
ms.openlocfilehash: fa9b09f97568b54a68f34a609c91426eb12b71e0
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="manage-software-updates"></a>Software-updates beheren

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Windows as a Service is dé manier om Windows 10-apparaten bij te werken. In Windows 10 bevatten nieuwe functie-updates en kwaliteitsupdates de inhoud van alle voorgaande updates. Dit houdt in dat, als u de nieuwste update hebt geïnstalleerd, u zeker weet dat uw Windows 10-apparaten zijn bijgewerkt. In tegenstelling tot eerdere versies van Windows, moet u nu de volledige update installeren in plaats van een onderdeel van een update.

Met Windows Update voor bedrijven kunt u updatebeheer vereenvoudigen, zodat u geen afzonderlijke updates voor groepen apparaten hoeft goed te keuren. U kunt nog steeds risico's in uw omgeving beheren door een strategie voor update-implementatie te configureren. Windows Update zorgt ervoor dat updates op tijd worden geïnstalleerd. Microsoft Intune biedt de mogelijkheid update-instellingen op apparaten te configureren en biedt u de mogelijkheid de installatie van updates uit te stellen. Intune slaat de updates niet op, maar alleen de beleidstoewijzing voor de update. Apparaten maken direct verbinding met Windows Update voor de updates. U kunt Intune gebruiken voor het configureren en beheren van **Windows 10-updateringen**. Een updatering bevat een aantal instellingen waarin is geconfigureerd wanneer en hoe Windows 10-updates worden geïnstalleerd. U kunt bijvoorbeeld het volgende configureren:

- **Windows 10 Servicing Channel** (Windows 10 Servicing-kanaal): kies of u updates wilt ontvangen voor groepen apparaten van het Semi-Annual-kanaal (Targeted) of van het Semi-Annual-kanaal.  
- **Instellingen voor uitstel**: configureer instellingen voor het uitstellen van updates om de installatie van updates voor groepen apparaten uit te stellen. U kunt deze instellingen gebruiken voor een gefaseerde update-implementatie, zodat u kunt de voortgang kunt controleren.
- **Onderbreken**: stel de installatie van updates uit als u op enig moment tijdens de implementatie van de updates problemen ontdekt.
- **Onderhoudsvenster**: configureer de tijden waarop de updates kunnen worden geïnstalleerd.
- **Type update**: kies welke typen updates worden geïnstalleerd. Bijvoorbeeld kwaliteitsupdates, upgrades van onderdelen of stuurprogramma’s.
- **Installatiegedrag**: hiermee configureert u hoe de update wordt geïnstalleerd. Bijvoorbeeld, wordt het apparaat automatisch opnieuw opgestart na de installatie?
- **Peer-download**: u kunt opgeven of u peer-downloaden wilt configureren. Als deze optie is geconfigureerd, kunnen andere apparaten een update downloaden van een apparaat dat het downloaden van de update heeft voltooid. Hierdoor wordt het downloadproces versneld.

Nadat u de updateringen hebt gemaakt, kunt u deze toewijzen aan groepen apparaten. Als u updateringen gebruikt, kunt u een updatestrategie maken die overeenkomt met de behoeften van uw bedrijf. Zie [Manage updates using Windows Update for Business](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb) (Updates beheren met Windows Update voor Bedrijven) voor meer informatie.

## <a name="before-you-start"></a>Voordat u begint

- Als u Windows 10-computers wilt bijwerken, moet hier ten minste Windows 10 Pro met de speciale Windows Jubileumupdate worden uitgevoerd.

- Windows Update ondersteunt de volgende versies van Windows 10:
    - Windows 10
    - Windows 10 Team (voor Surface Hub-apparaten)

 Apparaten met Windows 10 Mobile en Windows 10 Holographic worden niet ondersteund.

- Op Windows-apparaten moet **Feedback en diagnostische gegevens** > **Diagnostische gegevens en gebruiksgegevens** ten minste zijn ingesteld op **Basic**.

    ![Windows-instelling voor diagnostische gegevens en gebruiksgegevens](./media/telemetry-basic.png)

    U kunt deze instelling handmatig configureren of u kunt een Intune-apparaatbeperkingsprofiel voor Windows 10 en hoger gebruiken. Hiervoor configureert u de instelling **Algemeen** > **Verzending van diagnostische gegevens** ten minste op **Basic**. Zie [How to configure device restriction settings](device-restrictions-configure.md) (Instellingen voor apparaatbeperking configureren) voor meer informatie over apparaatprofielen.

- In de Intune-beheerconsole vindt u vier instellingen die het gedrag van software-updates beheren. Deze instellingen maken deel uit van het algemene configuratiebeleid voor Windows 10 Desktop- en Mobile-apparaten:
    - **Automatische updates toestaan**
    - **Functies van evaluatieversies toestaan**
    - **Geplande installatiedag**
    - **Geplande installatietijd**

  De klassieke portal heeft ook een beperkt aantal andere instellingen voor Windows 10-updates in het apparaatconfiguratieprofiel. Als een van deze instellingen in de Intune-beheerconsole is geconfigureerd wanneer u naar de Azure-portal migreert, wordt het volgende aangeraden:

1. Maak Windows 10 updateringen in de Azure-portal met de instellingen die u nodig hebt. De instelling **Functies van evaluatieversies toestaan** wordt niet ondersteund in Azure Portal omdat deze niet langer van toepassing is op de meest recente builds van Windows 10. U kunt de andere drie instellingen, evenals andere instellingen voor Windows 10-updates, configureren wanneer u updateringen maakt.

  > [!NOTE]
  > Instellingen voor Windows 10-updates die zijn gemaakt in de klassieke portal worden na de migratie niet weergegeven in de Azure-portal. Deze instellingen worden echter nog wel toegepast. Als u deze instellingen hebt gemigreerd en het gemigreerde beleid bewerkt in Azure Portal, worden deze instellingen verwijderd uit het beleid.

2. Verwijder de update-instellingen in de klassieke portal. Nadat u naar Azure Portal bent gemigreerd en dezelfde instellingen toevoegt aan een updatering, moet u de instellingen in de klassieke portal verwijderen om mogelijke beleidsconflicten te voorkomen. Wanneer bijvoorbeeld dezelfde instelling is geconfigureerd met verschillende waarden, ontstaat er een conflict. Er is geen eenvoudige manier om dit te achterhalen, omdat de instelling die is geconfigureerd in de klassieke portal niet wordt weergegeven in de Azure-portal.

## <a name="how-to-create-and-assign-update-rings"></a>Updateringen maken en toewijzen

1. Meld u aan bij Azure-portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Software-updates** op de blade **Intune**.
4. Kies **Beheren** > **Windows 10 Update Rings** op de blade **Software-updates**.
5. Kies **Maken** op de blade met de updateringen.
6. Geef op de blade **Updatering maken** een naam en een optionele omschrijving voor de updatering op en kies vervolgens **Instellingen**.
7. Configureer de volgende gegevens op de blade **Instellingen**:
    - **Onderhoud van kanaal**: stel het kanaal in waarvoor het apparaat Windows-updates (het Semi-Annual-kanaal (Targeted) of het Semi-Annual-kanaal) ontvangt.
    - **Microsoft-updates**: kies of u wilt zoeken naar app-updates via Microsoft Update.
    - **Windows-stuurprogramma's**: kies of u Windows Update-stuurprogramma's wilt uitsluiten tijdens het bijwerken.
    - **Gedrag van automatische updates**: kies hoe het gedrag van automatische update moet worden beheerd voor het zoeken naar, downloaden en installeren van updates. Zie [Update/AllowAutoUpdate](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#update-allowautoupdate) voor meer informatie.
    - **Uitstelperiode voor kwaliteitsupdates (dagen)**: geef het aantal dagen op dat kwaliteitsupdates worden uitgesteld. U kunt deze kwaliteitsupdates uitstellen gedurende maximaal 30 dagen vanaf de release.  

    Kwaliteitsupdates zijn doorgaans oplossingen en verbeteringen in de bestaande Windows-functionaliteit. Deze worden normaal gesproken op de eerste dinsdag van elke maand gepubliceerd, maar kunnen op elk gewenst moment door Microsoft worden vrijgegeven. U kunt opgeven of, en hoe u de installatie van kwaliteitsupdates wilt uitstellen na hun beschikbaarheid.
    - **Uitstelperiode voor upgrades van onderdelen (dagen)**: geef het aantal dagen op dat upgrades van onderdelen worden uitgesteld. U kunt deze upgrades van onderdelen uitstellen gedurende een periode van 180 dagen vanaf de release.

    Upgrades van onderdelen zijn over het algemeen nieuwe functies van Windows. Nadat u de instelling voor **Servicing-kanaal** hebt geconfigureerd (Semi-Annual-kanaal (Targeted) of Semi-Annual-kanaal), kunt u opgeven of en hoe lang u upgrades van onderdelen wilt uitstellen nadat deze door Microsoft beschikbaar zijn gesteld via Windows Update.

    Bijvoorbeeld:  
    **Als het Servicing-kanaal is ingesteld op Semi-Annual-kanaal (Targeted) en de uitstelperiode 30 dagen is**: Stel dat onderdelenupdate x eerst openbaar beschikbaar is op Windows Update als een Semi-Annual-kanaal (Targeted) in januari. Het apparaat ontvangt de update pas in februari - 30 dagen later.

    **Als het Servicing-kanaal is ingesteld op Semi-Annual-kanaal en de uitstelperiode 30 dagen is**: Stel dat onderdelenupdate x eerst openbaar beschikbaar is op Windows Update als een Semi-Annual-kanaal (Targeted) in januari. Vier maanden later, in april, wordt onderdelenupdate X vrijgegeven voor Semi-Annual-kanaal. Het apparaat ontvangt de onderdelenupdate 30 dagen na deze Semi-Annual-kanaal-release en wordt in mei bijgewerkt.

    - **Delivery optimization**: kies de methode waarmee apparaten Windows-updates moeten downloaden. Zie [DeliveryOptimization/DODownloadMode](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#download-mode) voor meer informatie.
1. Wanneer u klaar bent, klikt u op **OK** en klikt u vervolgens op de blade **Updatering maken** op **Maken**.

De nieuwe updatering wordt weergegeven in de lijst met updateringen.

1. Als u de ring wilt toewijzen, selecteert u een ring in de lijst met updateringen en klikt u op het tabblad *Ringnaam* > en kiest u **Toewijzingen**.
2. Kies op het volgende tabblad **Groepen selecteren** en kies vervolgens de groepen waaraan u deze ring wilt toewijzen.
3. Als u klaar bent, kiest u **Selecteren** om de toewijzing te voltooien.

## <a name="update-compliance-reporting"></a>Update-nalevingsrapportages
Met de gratis oplossing Update Compliance in Operations Management Suite (OMS) kunt u de updatenaleving weergeven in Intune.

### <a name="review-update-compliance-in-intune"></a>Updatenaleving weergeven in Intune 
<!-- 1352223 -->
Een beleidsrapport weergeven met de implementatiestatus voor de Windows 10-updateringen die u hebt geconfigureerd. 
1. Meld u aan bij Azure-portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Software-updates** op de blade **Intune**.
4. Kies op de blade **Software-updates** de optie **Overzicht**. Hier wordt algemene informatie weergegeven over de status van de updateringen die u hebt toegewezen.
5. Open een van de volgende rapporten: 
     
   **Voor alle implementatieringen:**
   1. Op de blade **Software-updates** > **Windows 10-updateringen**. 
   2. In de sectie **Bewaken** kiest u **Implementatiestatus per updatering**.
                   
   **Voor specifieke implementatieringen:** 
   1. Kies op de blade **Software-updates** > **Windows 10-updateringen** de implementatiering die u wilt weergeven.
   2. Kies in de sectie **Bewaken** een van de volgende rapporten om meer gedetailleerde informatie over de implementatiering weer te geven:
      - **Updateringimplementatie voor apparaten**
      - **Updateringimplementatie voor gebruikers**
      - **Implementatiestatus per instelling**

### <a name="review-update-compliance-using-oms"></a>Updatenaleving weergeven in OMS
Met de gratis oplossing Update Compliance in Operations Management Suite (OMS) kunt u de Windows 10 update-implementatie bewaken. Zie [Monitor Windows Updates with Update Compliance](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor) (Windows-updates bewaken met Update Compliance) voor meer informatie. Wanneer u deze oplossing gebruikt, kunt u een commerciële id implementeren op elk van uw door Intune beheerde Windows 10-apparaten waarvoor u over de naleving van updates wilt rapporteren.

In de Intune-console kunt u de OMA-URI-instellingen van een aangepast beleid gebruiken om de commerciële id te configureren. Zie [Beleidsinstellingen voor Windows 10-apparaten in Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune) voor meer informatie.   

Het pad voor de OMA-URI (hoofdlettergevoelig) voor het configureren van de commerciële id is: ./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID

U kunt bijvoorbeeld de volgende waarden gebruiken in **OMA-URI-instelling toevoegen of bewerken**:

- **Naam van instelling**: Commerciële id voor Windows Analytics
- **Beschrijving van instelling**: commerciële id voor Windows Analytics-oplossingen configureren
- **Gegevenstype:** tekenreeks
- **OMA-URI** (hoofdlettergevoelig): ./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID
- **Waarde**: <*gebruik de GUID die wordt weergegeven op het tabblad Windows-telemetrie in uw OMS-werkruimte*>

![Windows-instelling voor diagnostische gegevens en gebruiksgegevens](./media/commID.png)

## <a name="how-to-pause-updates"></a>Updates onderbreken
U kunt het ontvangen van upgrades voor onderdelen of kwaliteitsupdates op een apparaat onderbreken gedurende een periode van maximaal 35 dagen vanaf het moment waarop u de updates onderbreekt. Als het maximum aantal dagen is verstreken, verloopt de functionaliteit voor onderbreken automatisch en zoekt het apparaat in Windows-Updates naar toepasselijke updates. Na deze scan kunt u de updates opnieuw onderbreken.
1. Meld u aan bij Azure-portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Software-updates** op de blade **Intune**.
4. Kies **Beheren** > **Windows 10 Update Rings** op de blade **Software-updates**.
5. Kies op de blade met de lijst met updateringen de ring die u wilt onderbreken en kies vervolgens kies **...**   >  **Kwaliteitsupdates onderbreken** > of **Onderdelenupdates onderbreken**, afhankelijk van het type updates dat u wilt onderbreken.

> [!IMPORTANT]
> Wanneer u een opdracht voor onderbreken opgeeft, ontvangen apparaten deze opdracht de volgende keer dat bij de service wordt gecontroleerd op updates. Mogelijk wordt een geplande update geïnstalleerd voordat het apparaat controleert of er nieuwe updates zijn.
> Als het betreffende apparaat is uitgeschakeld wanneer u de opdracht voor onderbreken opgeeft, kan dit apparaat, wanneer het wordt ingeschakeld, geplande updates downloaden en installeren voordat er bij Intune wordt gecontroleerd op nieuwe updates.
