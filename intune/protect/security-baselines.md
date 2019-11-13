---
title: Problemen met beveiligingsbasislijnen oplossen in Microsoft Intune - Azure | Microsoft Docs
description: Gebruik de aanbevolen Windows-beveiligingsinstellingen ter bescherming van gebruikers en gegevens op apparaten met behulp van Microsoft Intune voor Mobile Device Management. Versleuteling inschakelen, Windows Defender Advanced Threat Protection configureren, Internet Explorer beheren, lokaal beveiligingsbeleid instellen, een wachtwoord vereisen, internetdownloads blokkeren en meer.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/28/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 53014376a7e220e975878031ffd759da40db7f6b
ms.sourcegitcommit: 60f0ff6d2efbae0f2ce14b9a9f3f9267309e209b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/01/2019
ms.locfileid: "73413840"
---
# <a name="use-security-baselines-to-configure-windows-10-devices-in-intune"></a>Beveiligingsbasislijnen gebruiken om Windows 10-apparaten te gebruiken in Intune

Gebruik de beveiligingsbasislijnen van Intune om uw gebruikers en apparaten te beschermen. Beveiligingsbasislijnen zijn vooraf geconfigureerde Windows-instellingen waarmee u een beproefde groep instellingen en standaardwaarden kunt toepassen die door relevante beveiligingsteams worden aanbevolen. Wanneer u in Intune een profiel voor beveiligingsbasislijnen maakt, maakt u een sjabloon dat bestaat uit meerde profielen voor *apparaatconfiguratie*.

Deze functie is van toepassing op:

- Windows 10 versie 1809 en hoger

U implementeert beveiligingsbasislijnen in groepen gebruikers of apparaten in Intune en de instellingen zijn van toepassing op apparaten met Windows 10 of hoger. Door de *MDM-beveiligingsbasislijn* wordt bijvoorbeeld automatisch BitLocker voor verwijderbare schijven ingeschakeld, automatisch een wachtwoord voor het ontgrendelen van een apparaat vereist, automatisch basisverificatie uitgeschakeld en meer. Wanneer een standaardwaarde niet geschikt is voor uw omgeving, past u de basislijn aan om de instellingen toe te passen die u nodig hebt.

Verschillende basislijntypen kunnen dezelfde instellingen omvatten, maar hiervoor uiteenlopende waarden gebruiken. Het is belangrijk om inzicht te krijgen in de standaardinstellingen in de basislijnen die u gebruikt en om de basislijnen vervolgens aan te passen aan de behoeften van uw organisatie.

> [!NOTE]
> Microsoft raadt u af om previewversies van beveiligingsbasislijnen te gebruiken in een productieomgeving. De instellingen in de previewversie van een basislijn veranderen mogelijk in de loop van de preview.

Met beveiligingsbasislijnen kunt u een veilige end-to-end-werkstroom inrichten voor het werken met Microsoft 365. Enkele voordelen zijn:

- Een beveiligingsbasislijn bevat de aanbevolen procedures en aanbevelingen voor instellingen die van invloed zijn op beveiliging. Intune werkt samen met hetzelfde Windows-beveiligingsteam dat beveiligingsbasislijnen voor groepsbeleid maakt. Deze aanbevelingen zijn gebaseerd op richtlijnen en uitgebreide ervaring.
- Als Intune nieuw voor u is en u niet zeker weet waar moet beginnen, bieden beveiligingsbasislijnen uitkomst. U kunt snel een beveiligd profiel maken en implementeren, waarbij u er zeker van bent dat u de resources en de gegevens van uw organisatie helpt beschermen.
- Als u momenteel gebruikmaakt van groepsbeleid, is het met deze basislijnen veel eenvoudiger om naar Intune te migreren voor beheer. Deze basislijnen zijn standaard ingebouwd in Intune en bieden een moderne beheerervaring.

[Windows-beveiligingsbasislijnen](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines) is een goede bron voor meer informatie over deze functie. [Mobile Device Management](https://docs.microsoft.com/windows/client-management/mdm/) (MDM) is een goede bron meer informatie over MDM en wat u op Windows-apparaten kunt doen.

## <a name="about-baseline-versions-and-instances"></a>Versies en instanties van basislijnen

In elke nieuwe versie-instantie van een basislijn kunnen instellingen worden toegevoegd, verwijderd of veranderd. Als er in een nieuwe versie van Windows 10 bijvoorbeeld nieuwe Windows 10-instellingen beschikbaar komen, ontvangt de MDM-beveiligingsbasislijn mogelijk een nieuwe versie-instantie met de nieuwste instellingen.

In de Intune-console worden op de tegel voor elke basislijn de naam van de basislijnsjabloon en basisgegevens over die basislijn weergegeven. Zo wordt er aangegeven hoeveel profielen u hebt die dat type basislijn gebruiken, hoeveel verschillende instanties (versies) van het type basislijn er beschikbaar zijn en een *laatste publicatiedatum*, die aangeeft wanneer die basislijnsjabloon aan uw tenant is toegevoegd. In de volgende voorbeelden ziet u de tegel van een vaak gebruikte MDM-beveiligingsbasislijn:

![Basislijntegel](./media/security-baselines/baseline-tile.png)

Als u meer gegevens wilt bekijken over de basislijnversies die u gebruikt, selecteert u een basislijntegel. Het deelvenster *Overzicht* wordt dan geopend. Selecteer vervolgens **Versies**. Intune geeft details weer over de versies van die basislijn die door uw profielen worden gebruikt. In het deelvenster Versies kunt u een versie selecteren om meer informatie weer te geven over de profielen die hiervan gebruikmaken. U kunt ook twee verschillende versies selecteren en vervolgens kiezen voor **Basislijnen vergelijken** om een CSV-bestand te downloaden met de verschillen.

![Basislijnen vergelijken](./media/security-baselines/compare-baselines.png)

Wanneer u een *beveiligingsbasislijnprofiel* maakt, gebruikt het profiel automatisch de meest recente instantie van de beveiligingsbasislijn.  Profielen die u eerder hebt gemaakt en die gebruikmaken van een eerdere instantie van de basislijnversie, kunt u gewoon blijven gebruiken en bewerken. Dit geldt ook voor basislijnen die met een previewversie zijn gemaakt.

U kunt kiezen of u [de versie wilt wijzigen](#change-the-baseline-version-for-a-profile) van een basislijn die wordt gebruikt met een bepaald profiel. Dit betekent dat wanneer er een nieuwe versie uitkomt, u geen nieuw basislijnprofiel hoeft te maken om er gebruik van te kunnen maken. In plaats daarvan selecteert u, wanneer u hier klaar voor bent, een basislijnprofiel en gebruikt u de ingebouwde optie om de instantieversie van dat profiel te wijzigen in een nieuwe versie.

## <a name="available-security-baselines"></a>Beschikbare beveiligingsbasislijnen

 U kunt een of meer van de beschikbare basislijnen tegelijkertijd gebruiken in uw Intune-omgeving. U kunt ook meerdere exemplaren van dezelfde beveiligingsbasislijnen gebruiken die verschillende aanpassingen hebben.

Wanneer u meerdere beveiligingsbasislijnen gebruikt, raadpleegt u de instellingen in elke basislijn om vast te stellen wanneer verschillende basislijnen conflicterende waarden voor dezelfde instelling opgeven. Aangezien u beveiligingsbasislijnen kunt implementeren die voor verschillende doeleinden zijn ontworpen en meerdere exemplaren van dezelfde basislijn met aangepaste instellingen kunt implementeren, onstaan er [configuratieconflicten voor apparaten die moeten worden onderzocht en opgelost](security-baselines-monitor.md#troubleshoot-using-per-setting-status).  Houd ook rekening met uw [apparaatconfiguratieprofielen](../configuration/device-profiles.md), die veel van dezelfde instellingen configureren als beveiligingsbasislijnen.

De volgende beveiligingsbasislijninstanties zijn beschikbaar voor gebruik met Intune. Gebruik de koppelingen om de instellingen weer te geven voor de meest recente instantie van elke basislijn.

- **MDM-beveiligingsbasislijn**
  - [MDM-beveiligingsbasislijn voor mei 2019](security-baseline-settings-mdm-all.md?pivots=mdm-may-2019)
  - [Voorbeeld: MDM-basislijn voor beveiliging voor oktober 2018](security-baseline-settings-mdm-all.md?pivots=mdm-preview)

- **Microsoft Defender ATP-basislijn**
   *(Voor het gebruik van deze basislijn moet uw omgeving voldoen aan de vereisten voor het gebruik van [Microsoft Defender Advanced Threat Protection](advanced-threat-protection.md#prerequisites))* .
  - [Microsoft Defender ATP-basislijn](security-baseline-settings-defender-atp.md)

  > [!NOTE]
  > De beveiligingsbasislijn van de Microsoft Defender ATP is geoptimaliseerd voor fysieke apparaten en wordt momenteel niet aanbevolen voor gebruik met virtuele machines (VM's) of VDI-eindpunten. Bepaalde basislijninstellingen kunnen invloed hebben op externe interactieve sessies in gevirtualiseerde omgevingen.  Voor meer informatie ziet u [Increase compliance to the Microsoft Defender ATP security baseline](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline) (Naleving met de Microsoft Defender ATP-beveiligingsbasislijn vergroten) in de Windows-documentatie.

- **Microsoft Edge-basislijn** 
  - [Voorbeeld: Microsoft Edge-basislijn](security-baseline-settings-edge.md)

Profielen die u eerder hebt gemaakt op basis van een previewsjabloon, kunt u gewoon blijven gebruiken en bewerken, zelfs wanneer de sjabloon niet meer beschikbaar is voor nieuwe profielen.

## <a name="manage-baselines"></a>Basislijnen beheren

Veelvoorkomende taken bij het werken met beveiligingsbasislijnen zijn onder meer:

- [Een profiel maken](#create-the-profile) – Om de instellingen die u wilt gebruiken te configureren en de basislijn aan groepen toe te wijzen.
- [De versie wijzigen](#change-the-baseline-version-for-a-profile): de basislijnversie die wordt gebruikt door een profiel wijzigen.
- [Een basislijntoewijzing verwijderen](#remove-a-security-baseline-assignment): ontdek wat er gebeurt wanneer u stopt met het beheren van instellingen met een beveiligingsbasislijn.


### <a name="prerequisites"></a>Vereisten

- Als u basislijnen in Intune wilt beheren, moet de ingebouwde rol [Beleids- en profielbeheerder](../fundamentals/role-based-access-control.md#built-in-roles) deel uitmaken van uw account.

- Voor het gebruik van sommige basislijnen moet u mogelijk beschikken over een actief abonnement op aanvullende services, bijvoorbeeld Microsoft Defender ATP.

### <a name="create-the-profile"></a>Het profiel maken

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) en selecteer **Apparaatbeveiliging** > **Beveiligingsbaslijnen** om de lijst met beschikbare basislijnen weer te geven.

   ![Beveiligingsbasislijn selecteren om te configureren](./media/security-baselines/available-baselines.png)

2. Selecteer de basislijn die u wilt gebruiken en selecteer vervolgens **Profiel maken**.

3. Geef op het tabblad **Basisinformatie** de volgende eigenschappen op:

   - **Naam**: voer een naam in voor uw beveiligingsbasislijnprofiel. Voer bijvoorbeeld *Standaardprofiel voor Defender ATP* in.

   - **Beschrijving**: voer tekst waarin wordt beschreven wat deze basislijn doet. In de beschrijving kunt u de door u gewenste tekst opgeven. Dit is optioneel, maar wordt wel aanbevolen.

   Selecteer **Volgende** om naar het volgende tabblad te gaan. Nadat u verder bent gegaan naar een ander tabblad, kunt u de naam van een eerder bekeken tabblad selecteren om hiernaar terug te keren.

4. Op het tabblad Configuratie-instellingen bekijkt u de groepen **Instellingen** die beschikbaar zijn in de basislijn die u hebt geselecteerd. U kunt een groep uitvouwen om de instellingen van de groep en de standaardwaarden voor die instellingen in de basislijn te bekijken. Ga als volgt te werk als u specifieke instellingen zoekt:
   - Selecteer een groep om de beschikbare instellingen uit te vouwen en te bekijken.
   - Gebruik de balk *Zoeken* en geef trefwoorden op om de weergave te filteren en alleen groepen weer te geven die uw zoekcriteria bevatten.

   Elke instelling in een basislijn beschikt over een standaardconfiguratie voor de betreffende basislijnversie. Pas de standaardinstellingen aan om optimaal te voldoen aan de behoeften van uw bedrijf. Mogelijk bevatten verschillende basislijnen dezelfde instellingen, maar gebruiken ze hiervoor andere standaardwaarden, afhankelijk van het doel van de basislijn.

   ![Vouw een groep uit om de instellingen voor die groep weer te geven](./media/security-baselines/sample-list-of-settings.png)

5. Selecteer op het tabblad **Bereiktags** de optie **Bereiktags selecteren** om het deelvenster *Tags selecteren* te openen en bereiktags toe te wijzen aan het profiel.

6. Selecteer op het tabblad **Toewijzingen** de optie **Groepen selecteren die moeten worden opgenomen** en wijs de basislijn toe aan een of meer groepen. Gebruik **Groepen selecteren die moeten worden uitgesloten** om de toewijzing te verfijnen.

   ![Een profiel toewijzen](./media/security-baselines/assignments.png)

7. Wanneer u er klaar voor bent om de basislijn te implementeren, gaat u naar het tabblad **Controleren en maken** en controleert u de gegevens van de basislijn. Selecteer **Maken** om het profiel op te slaan en te implementeren.

   Nadat u het profiel hebt gemaakt, wordt het naar de toegewezen groep gepusht en mogelijk meteen toegepast.

   > [!TIP]
   > Als u een profiel opslaat zonder dit toe te wijzen aan groepen, kunt u het profiel later bewerken en alsnog toewijzen.

   ![De basislijn controleren](./media/security-baselines/review.png)

8. Nadat u een profiel hebt maakt, bewerkt u dit door naar **Apparaatbeveiliging** > **Beveiligingsbasislijnen** te gaan, het type basislijn te selecteren dat u hebt geconfigureerd en vervolgens **Profielen** te selecteren. Selecteer het profiel in de lijst met beschikbare profielen en selecteer vervolgens **Eigenschappen**. U kunt de instellingen bewerken op alle beschikbare configuratietabbladen en **Controleren en opslaan** selecteren om uw wijzigingen door te voeren.

### <a name="change-the-baseline-version-for-a-profile"></a>De basislijnversie voor een profiel wijzigen

U kunt de versie van de basislijninstantie die wordt gebruikt met een profiel wijzigen.  Wanneer u de versie wijzigt, selecteert u een beschikbare instantie van dezelfde basislijn. U kunt echter niet wisselen tussen twee verschillende basislijntypen, bijvoorbeeld in een profiel de basislijn veranderen van Defender ATP in de MDM-beveiligingsbasislijn.

Wanneer u een wijziging van de basislijnversie configureert, kunt u een CSV-bestand downloaden met de verschillen tussen de twee basislijnversies. U kunt er ook voor kiezen om al uw aanpassingen in de oorspronkelijke basislijnversie te behouden of de nieuwe versie te implementeren met alle standaardwaarden. U kunt geen wijzigingen aanbrengen in afzonderlijke instellingen wanneer u de versie van een basislijn voor een profiel wijzigt.

Wanneer u de basislijn opslaat nadat de conversie is voltooid, wordt deze onmiddellijk geïmplementeerd in de toegewezen groepen.

**Tijdens de conversie**:

- Nieuwe instellingen die zich niet in uw oorspronkelijke versie bevonden, worden toegevoegd en ingesteld op de standaardwaarden.

- Instellingen die zich niet in de basislijnversie bevinden die u hebt geselecteerd, worden verwijderd en niet langer afgedwongen door het beveiligingsbasislijnprofiel.

  Wanneer een instelling niet langer wordt beheerd door een basislijnprofiel, wordt deze niet opnieuw ingesteld op het apparaat. In plaats daarvan blijft de instelling op het apparaat ingesteld op de laatste configuratie, tot een ander proces de instelling wijzigt. Voorbeelden van processen die mogelijk een instelling wijzigen nadat u bent gestopt met het beheren hiervan, zijn onder meer een ander basislijnprofiel, een groepsbeleidinstelling of een handmatige configuratie op het apparaat.

#### <a name="to-change-the-baseline-version-for-a-profile"></a>De basislijnversie voor een profiel wijzigen

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973), selecteer **Apparaatbeveiliging** > **Beveiligingsbasislijnen** en selecteer vervolgens de tegel voor het type basislijn met het profiel dat u wilt wijzigen.

2. Selecteer daarna **Profielen** en het selectievakje voor het profiel dat u wilt bewerken. Selecteer vervolgens **Versie wijzigen**.

   ![Een basislijn selecteren](./media/security-baselines/select-baseline.png)

3. Gebruik in het deelvenster **Versie wijzigen** de vervolgkeuzelijst **Een beveiligingsbasislijn selecteren om naar bij te werken** om de versie-instantie te selecteren die u wilt gebruiken.

   ![Een versie selecteren](./media/security-baselines/select-instance.png)

4. Selecteer **Update bekijken** om een CSV-bestand te downloaden met de verschillen tussen de huidige instantieversie van het profiel en de nieuwe versie. Neem dit bestand door, zodat u weet welke instellingen nieuw zijn of zijn verwijderd, en wat de standaardwaarden zijn voor deze instellingen in het bijgewerkte profiel.

   Wanneer u klaar bent, gaat u door naar de volgende stap.

5. Kies een van de twee opties voor **Selecteer een methode om het profiel bij te werken**:
   - **Basislijnwijzigingen accepteren, maar mijn bestaande instellingen behouden**: met deze optie behoudt u de wijzigingen die u hebt aangebracht aan het basislijnprofiel en past u deze toe op de nieuwe versie die u hebt geselecteerd.
   - **Basislijnwijzigingen accepteren en bestaande instellingen verwijderen**: met deze optie wordt uw originele profiel volledig overschreven. Het bijgewerkte profiel gebruikt de standaardwaarden voor alle instellingen.

6. Selecteer **Verzenden**. Het profiel wordt bijgewerkt naar de geselecteerde basislijnversie en nadat de conversie is voltooid, wordt de basislijn onmiddellijk opnieuw geïmplementeerd in de toegewezen groepen.

### <a name="remove-a-security-baseline-assignment"></a>Een beveiligingsbasislijntoewijzing verwijderen

Wanneer een beveiligingsbasislijninstelling niet langer van toepassing is op een apparaat, of wanneer bepaalde instellingen in een basislijn zijn ingesteld op *Niet geconfigureerd*, worden deze instellingen op een apparaat niet teruggezet naar een vooraf beheerde configuratie. In plaats daarvan behouden de eerder beheerde instellingen op het apparaat de configuratie zoals die is ontvangen van de basislijn, tot een ander proces die instellingen op het apparaat bijwerkt.

Andere processen die later mogelijk de instellingen op het apparaat wijzigen, zijn onder meer implementatie van een andere of een nieuwe beveiligingsbasislijn, een apparaatconfiguratieprofiel, groepsbeleidconfiguraties of een handmatige bewerking van de instellingen op het apparaat.

## <a name="co-managed-devices"></a>Apparaten met co-beheer

Beveiligingsbasislijnen op met Intune-beheerde apparaten zijn vergelijkbaar met beheerde apparaten met co-beheer met Configuration Manager. Apparaten met co-beheer maken gebruik van System Center Configuration Manager en Microsoft Intune voor het tegelijkertijd beheren van de Windows 10-apparaten. Hiermee kunt u uw bestaande investering in Configuration Manager via de cloud koppelen aan de voordelen van Intune. [Overzicht van co-beheer](https://docs.microsoft.com/sccm/comanage/overview) is een goede informatiebron als u Configuration Manager gebruikt en ook wilt profiteren van de voordelen van de cloud.

Wanneer u apparaten met co-beheer gebruikt, moet u de workload **Apparaatconfiguratie** (de instellingen ervan) overschakelen naar Intune. [Workloads voor apparaatconfiguratie](https://docs.microsoft.com/sccm/comanage/workloads#device-configuration) biedt meer informatie.

## <a name="q--a"></a>Vragenronde

### <a name="why-these-settings"></a>Waarom deze instellingen?

Het Microsoft-beveiligingsteam heeft jarenlang rechtstreeks met de Windows-ontwikkelaars en de beveiligingscommunity samengewerkt om deze aanbevelingen op te stellen. De instellingen in deze basislijn worden beschouwd als de meest relevante beveiligingsgerelateerde configuratieopties. In elke nieuwe build van Windows past het team de aanbevelingen aan op basis van onlangs uitgebrachte functies.

### <a name="is-there-a-difference-in-the-recommendations-for-windows-security-baselines-for-group-policy-vs-intune"></a>Is er een verschil in de aanbevelingen voor Windows-beveiligingsbasisrichtlijnen voor groepsbeleid t.o.v. Intune?

De instellingen voor elke basislijn worden door hetzelfde beveiligingsteam van Microsoft gekozen en georganiseerd. Intune bevat alle relevante instellingen in de Intune-beveiligingsbasislijn. Er zijn enkele instellingen in de basislijn voor groepsbeleid die specifiek zijn voor een on-premises domeincontroller. Deze instellingen worden uitgesloten van de aanbevelingen voor Intune. Alle andere instellingen zijn hetzelfde.

### <a name="are-the-intune-security-baselines-cis-or-nsit-compliant"></a>Zijn de Intune-beveiligingsbasislijnen compatibel met CIS of NSIT?

Strikt genomen niet. Het Microsoft-beveiligingsteam raadpleegt adviesorganisaties, zoals CIS, voor het opstellen van de aanbevelingen. Maar er is niet één-op-één koppeling tussen "Compatibel met CIS" en Microsoft-basislijnen.

### <a name="what-certifications-does-microsofts-security-baselines-have"></a>Welke certificeringen hebben Microsoft-beveiligingsbasislijnen? 

- Microsoft blijft beveiligingsbasislijnen publiceren voor groepsbeleid (GPO's) en de [Security Compliance Toolkit](https://docs.microsoft.com/windows/security/threat-protection/security-compliance-toolkit-10), zoals het dit al vele jaren doet. Deze basislijnen worden door veel organisaties gebruikt. De aanbevelingen in deze basislijnen zijn het gevolg van de samenwerking van het Microsoft Security-team met zakelijke klanten en externe organisaties, inclusief het Ministerie van defensie, de NIST (National Institute of Standards en Technology) en meer. We delen onze aanbevelingen en basislijnen met deze organisaties. Deze organisaties hebben ook hun eigen aanbevelingen die nauw aansluiten bij de aanbevelingen van Microsoft. Aangezien Mobile Device Management (MDM) blijft groeien in de cloud, heeft Microsoft gelijkwaardige MDM-aanbevelingen voor deze basislijnen groepsbeleid opgesteld. Deze aanvullende basislijnen zijn ingebouwd in Microsoft Intune en omvatten nalevingsrapporten voor gebruikers, groepen en apparaten die de basislijn volgen (of niet volgen).

- Veel klanten gebruiken de aanbevelingen voor Intune-basislijnen als uitgangspunt, en passen deze vervolgens aan hun eigen IT- en beveiligingsbehoeften aan. De Windows 10 RS5 **MDM-beveiligingsbasislijn** van Microsoft is de eerste basislijn die wordt uitgebracht. Deze basislijn is gebouwd als een algemene infrastructuur die klanten de mogelijkheid biedt om uiteindelijk andere beveiligingsbasislijnen op basis van CIS, NIST en andere standaarden te importeren. Deze is op dit moment beschikbaar voor Windows en zal later beschikbaar komen voor iOS en Android.

- Het migreren van on-premises Active Directory-groepsbeleid naar een zuivere cloudoplossing met behulp van Azure Active Directory (AD) met Microsoft Intune is een heel traject. Om u hierbij te helpen, zijn er groepsbeleidsjablonen toegevoegd aan de [Toolkit voor beveiliging en compliance](https://docs.microsoft.com/windows/security/threat-protection/security-compliance-toolkit-10). Deze maken het gemakkelijker om hybride AD- en samengevoegde Azure AD-apparaten te beheren. Deze apparaten kunnen, indien nodig, MDM-instellingen van de cloud (Intune) en instellingen voor groepsbeleid van on-premises domeincontrollers krijgen.

## <a name="next-steps"></a>Volgende stappen

- Bekijk de instellingen in de nieuwste versies van de beschikbare basislijnen:
  - [MDM-beveiligingsbasislijn](security-baseline-settings-mdm-all.md)
  - [Microsoft Defender ATP-basislijn](security-baseline-settings-defender-atp.md)

- De status controleren en de [basislijn en het profiel](security-baselines-monitor.md) controleren
