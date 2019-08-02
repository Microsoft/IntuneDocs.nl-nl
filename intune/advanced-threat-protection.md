---
title: Microsoft Defender ATP in Microsoft Intune gebruiken - Azure | Microsoft Docs
description: Gebruik Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) met Intune voor het instellen, configureren en onboarden van uw Intune-apparaten met ATP. Gebruik vervolgens een ATP-risicobeoordeling voor uw apparaten met Intune-beleid voor apparaatcompatibiliteit en voorwaardelijke toegang om uw netwerkresources te beveiligen.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8508915f0b4711b2aa65465dd7ac79f575a8d008
ms.sourcegitcommit: 99b74d7849fbfc8f5cf99cba33e858eeb9f537aa
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/31/2019
ms.locfileid: "68670967"
---
# <a name="enforce-compliance-for-microsoft-defender-atp-with-conditional-access-in-intune"></a>Naleving voor Microsoft Defender ATP met voorwaardelijke toegang in Intune afdwingen  

U kunt Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) integreren met Microsoft Intune als oplossing voor bescherming tegen mobiele bedreigingen, om beveiligingslekken te voorkomen en de gevolgen van beveiligingsschendingen binnen een organisatie te beperken. Microsoft Defender ATP werkt met apparaten waarop Windows 10 of hoger wordt uitgevoerd.

Voor effectieve bescherming gebruikt u een combinatie van de volgende configuraties:
- **Maak een service-naar-service-verbinding tussen Intune en Microsoft Defender ATP**. Met deze verbinding kan Microsoft Defender ATP gegevens verzamelen over risico's voor Windows 10-apparaten die u beheert met Intune.  
- **Gebruik een profiel voor apparaatconfiguratie om apparaten te onboarden met Microsoft Defender ATP**. U kunt apparaten onboarden om deze te configureren zodat ze communiceren met Microsoft Defender ATP en de gegevens aanleveren om hun risiconiveau te bepalen.  
 - **Gebruik een nalevingsbeleid voor apparaten om het risiconiveau dat u wilt toestaan te bepalen**. Risiconiveaus worden gerapporteerd door Microsoft Defender ATP.  Apparaten die het toegestane risiconiveau overschrijden, worden aangeduid als niet-compatibel.  
- **Gebruik beleid voor voorwaardelijke toegang** om te voorkomen dat gebruikers toegang krijgen tot bedrijfsresources vanaf apparaten die niet compatibel zijn.  

Wanneer u Intune integreert met Microsoft Defender ATP, hebt u bovendien ook toegang tot Threat & Vulnerability Management (TVM) van ATP en kunt u [Intune gebruiken voor het wegnemen van beveiligingsproblemen die door TVM zijn geïdentificeerd op eindpunten](atp-manage-vulnerabilities.md).

## <a name="example-of-using-microsoft-defender-atp-with-intune"></a>Voorbeeld van het gebruik van Microsoft Defender ATP met Intune  

In het volgende voorbeeld wordt uitgelegd hoe deze oplossingen samenwerken om uw organisatie te beschermen. Voor dit voorbeeld zijn Microsoft Defender ATP en Intune al geïntegreerd.  

Denk bijvoorbeeld aan een situatie waarin iemand een Word-bijlage met ingesloten schadelijke code verzendt naar een gebruiker binnen uw organisatie.  
- De gebruiker opent de bijlage en activeert de inhoud.  
- Een aanval met verhoogde bevoegdheden wordt gestart en een aanvaller vanaf een externe computer heeft beheerdersrechten op het apparaat van het slachtoffer.  
- De aanvaller krijgt vervolgens extern toegang tot de andere apparaten van de gebruiker. Deze beveiligingsschending kan invloed hebben op de hele organisatie.  

Microsoft Defender ATP kan beveiligingsgebeurtenissen zoals dit scenario helpen oplossen.  
- In ons voorbeeld detecteert Microsoft Defender ATP dat het apparaat abnormale code uitvoerde, een escalatie van procesbevoegdheden onderging, schadelijke code injecteerde en een verdachte remote shell uitgaf.  
- Op basis van deze acties van het apparaat [classificeert Microsoft Defender ATP het apparaat als een hoog risico](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/alerts-queue#severity) en wordt een gedetailleerd rapport over de verdachte activiteiten bijgevoegd in de portal van Microsoft Defender Security Center.  

Omdat u Intune-compliancebeleid voor apparaten gebruikt dat apparaten met *Medium* of *Hoog* risiconiveau als niet-compatibel classificeert, wordt het gecompromitteerde apparaat als niet-compatibel geclassificeerd. Deze classificatie zorgt ervoor dat het beleid voor voorwaardelijke toegang wordt toegepast en de toegang tot uw bedrijfsresources voor dit apparaat wordt geblokkeerd.  

## <a name="prerequisites"></a>Vereisten

Als u Microsoft Defender ATP met Intune wilt gebruiken, moet u het volgende geconfigureerd en klaar voor gebruik hebben:

- Tenant met licentie voor Enterprise Mobility + Security E3 en Windows E5 (of Microsoft 365 Enterprise E5)
- Microsoft Intune-omgeving met [Intune-beheerde](windows-enroll.md) Windows 10-apparaten die ook deelnemen aan Azure AD
- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) en toegang tot de Microsoft Defender Security Center (ATP-portal)

## <a name="enable-microsoft-defender-atp-in-intune"></a>Microsoft Defender ATP in Intune inschakelen

De eerste stap is het instellen van een service-naar-service-verbinding tussen Intune en Microsoft Defender ATP. Hiervoor moet u beheerdersrechten hebben tot zowel Microsoft Defender Security Center als voor Intune.  

### <a name="to-enable-defender-atp"></a>Defender ATP inschakelen  

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **Apparaatcompatibiliteit** > **Microsoft Defender ATP** en selecteer vervolgens **Microsoft Defender Security Center openen** onder *Connectorinstellingen*.

    ![Selecteren om het Microsoft Defender Security Center te openen](./media/advanced-threat-protection/atp-device-compliance-open-microsoft-defender.png)

4. In **Microsoft Defender Security Center**:
    1. Selecteer **Instellingen** > **Geavanceerde functies**.
    2. Voor **Microsoft Intune-verbinding**, kiest u **Aan**:

        ![De verbinding met Intune inschakelen](./media/advanced-threat-protection/atp-security-center-intune-toggle.png)

    3. Selecteer **Voorkeuren opslaan**.

4. Ga terug naar Intune en naar **Apparaatconformiteit** > **Microsoft Defender ATP**. Stel **Windows-apparaten met versie 10.0.15063 en hoger verbinden met Microsoft Defender ATP** in op **Aan**.
5. Selecteer **Opslaan**.

Gewoonlijk voltooit u deze taak één keer. Nadat u Microsoft Defender ATP hebt ingeschakeld voor uw Intune-tenant, hoeft u dit niet opnieuw te doen.

> [!TIP]  
> Wanneer u een nieuwe toepassing integreert in Intune Mobile Threat Defense en u de verbinding inschakelt, maakt Intune een klassiek beleid voor voorwaardelijke toegang in Azure Active Directory. Voor elke MTD-app die u integreert, zoals [Defender ATP](advanced-threat-protection.md) of een app van een van onze aanvullende [MTD-partners](mobile-threat-defense.md#mobile-threat-defense-partners), wordt er een nieuw klassiek beleid voor voorwaardelijke toegang gemaakt.  De beleidsregels kunnen worden genegeerd, maar mogen niet worden bewerkt, verwijderd of uitgeschakeld.
> 
> Klassiek beleid voor voorwaardelijke toegang voor MTD-apps: 
> 
> - Wordt door Intune MTD gebruikt om te vereisen dat apparaten in Azure AD worden geregistreerd; ze beschikken dan over een apparaat-id. De id is vereist omdat apparaten anders hun status niet kunnen doorgeven aan Intune.  
> - Verschilt van beleid voor voorwaardelijke toegang dat u normaal wellicht zou maken om MTD te helpen beheren.
> - Standaard wordt er niet gecommuniceerd met andere beleidsregels voor voorwaardelijke toegang die voor evaluatie worden gebruikt.  
> 
> Als u klassiek beleid voor voorwaardelijke toegang wilt bekijken, gaat u in [Azure](https://portal.azure.com/#home) naar **Azure Active Directory** > **Voorwaardelijke toegang** > **Klassieke beleidsregels**.

## <a name="onboard-devices-by-using-a-configuration-profile"></a>Apparaten onboarden met behulp van een configuratieprofiel

Nadat u de service-naar-service-verbinding tussen intune en Microsoft Defender ATP hebt ingesteld, kunt u uw door Intune beheerde apparaten onboarden bij ATP, zodat gegevens over het risiconiveau kunnen worden verzameld en gebruikt. U gebruikt een profiel voor apparaatconfiguratie om apparaten te onboarden bij Microsoft Defender ATP.  

Wanneer u verbinding maakte met Microsoft Defender ATP, heeft Intune van Microsoft Defender ATP een configuratiepakket voor onboarding gekregen. Dit pakket wordt geïmplementeerd op apparaten met het apparaatconfiguratieprofiel. Het configuratiepakket configureert apparaten zo dat ze communiceren met [Microsoft Defender ATP-services](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) om bestanden te scannen, bedreigingen te detecteren en het risico aan Microsoft Defender ATP te rapporteren.  

Wanneer u eenmaal onboarding van een apparaat met het configuratiepakket hebt uitgevoerd, dan hoeft u dit niet opnieuw te doen. U kunt apparaten onboarden met behulp van een [Groepsbeleid of System Center Configuration Manager (SCCM)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).

### <a name="create-the-device-configuration-profile"></a>Een apparaatconfiguratieprofiel maken

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Voer een **Naam** en **Beschrijving** in.
4. Voor **Platform** selecteert u **Windows 10 en hoger**
5. Voor **Profieltype** selecteert u **Microsoft Defender ATP (Windows 10 Desktop)** .
6. Configureer de gewenste instellingen:

   - **Type clientconfiguratiepakket voor Microsoft Defender ATP**: Selecteer **Onboarding uitvoeren** om het configuratiepakket aan het profiel toe te voegen. Selecteer **Offboarding uitvoeren** om configuratiepakket uit het profiel te verwijderen.
  
     > [!NOTE]  
     > Als u een verbinding met Microsoft Defender ATP tot stand hebt gebracht, start **Onboarding uitvoeren** in Intune automatisch en wordt het configuratieprofiel voor u toegevoegd. In dat geval is de instelling **Type clientconfiguratiepakket voor Microsoft Defender ATP** niet beschikbaar.
  
    - **Voorbeelddeling voor alle bestanden**: Met **Inschakelen** staat u toe dat voorbeelden worden verzameld en gedeeld met Microsoft Defender ATP. Als u bijvoorbeeld een verdacht bestand ziet, kunt u het verzenden naar Microsoft Defender ATP voor grondige analyse. **Niet geconfigureerd**: eventuele voorbeelden voor het Microsoft Defender ATP worden niet gedeeld.
    - **Frequentie van telemetrierapporten versnellen**: U kunt deze instelling **inschakelen** voor apparaten met een hoog risico, zodat er vaker telemetrie naar de Microsoft Defender ATP-service wordt gerapporteerd.

    [Onboard Windows 10 machines using System Center Configuration Manager](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints-sccm) (Windows 10-apparaten onboarden die System Center Configuration Manager gebruiken) bevat meer informatie over deze instellingen voor Microsoft Defender ATP.

7. Selecteer **OK** en **Maken** om wijzigingen op te slaan. Hiermee maakt u het profiel aan.
8. [Wijs een profiel voor apparaatconfiguratie toe](device-profile-assign.md) aan apparaten die u wilt beoordelen met Microsoft Defender ATP.  

## <a name="create-and-assign-the-compliance-policy"></a>Nalevingsbeleid maken en toewijzen  

Het nalevingsbeleid bepaalt het risiconiveau dat u voor een apparaat beschouwt als acceptabel.

### <a name="create-the-compliance-policy"></a>Het nalevingsbeleid maken  

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **Apparaatconformiteit** > **Beleid** > **Beleid maken**.
3. Voer een **Naam** en **Beschrijving** in.
4. In **Platform** selecteert u **Windows 10 en hoger**.
5. Stel in de instellingen voor **Microsoft Defender ATP** de optie **Vereisen dat het apparaat op of onder het apparaatdreigingsniveau moet zijn** in op het gewenste niveau. 
   
   De classificatie van bedreigingsniveaus wordt [bepaald door Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/alerts-queue).

   - **Veilig**: Dit is het veiligste niveau. Het apparaat heeft geen toegang tot bedrijfsresources als er ook maar één bedreiging is gevonden. Als er bedreigingen worden gevonden, wordt het apparaat geëvalueerd als niet-compatibel. (Microsoft Defender ATP gebruikt de waarde *Veilig*.)
   - **Laag**: Het apparaat is conform als er alleen bedreigingen van een laag niveau aanwezig zijn. Apparaten met een gemiddeld of hoog dreigingsniveau zijn niet conform.
   - **Gemiddeld**: Het apparaat is conform als de bedreigingen op het apparaat van laag of gemiddeld niveau zijn. Als er bedreigingen van hoog niveau worden aangetroffen, wordt het apparaat als niet-compatibel beoordeeld.
   - **Hoog**: Dit niveau is het minst veilig en laat alle bedreigingsniveaus toe. Apparaten met een hoog, gemiddeld of laag bedreigingsniveau worden daarom beschouwd als conform.

6. Selecteer **OK** en **Maken** om wijzigingen op te slaan (en het beleid aan te maken).  
7. [Wijs het nalevingsbeleid voor apparaten toe](create-compliance-policy.md#assign-user-groups) aan de toepasselijke groepen.



## <a name="create-a-conditional-access-policy"></a>Beleid voor voorwaardelijke toegang maken  

Het beleid voor voorwaardelijke toegang blokkeert de toegang tot resources voor apparaten die het bedreigingsniveau overschrijden dat u hebt ingesteld in uw nalevingsbeleid. U kunt de toegang van het apparaat tot bedrijfsresources zoals SharePoint of Exchange Online blokkeren.  

> [!TIP]  
> Voorwaardelijke toegang is een technologie van Azure Active Directory (Azure AD). Het knooppunt voor voorwaardelijke toegang dat via *Intune* wordt geopend, is hetzelfde als het knooppunt dat u opent via *Azure AD*.  

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) en selecteer **Voorwaardelijke toegang** > **Nieuw beleid**.
2. Voer een **Naam** voor het beleid in en selecteer **Gebruikers en groepen**. Gebruik de opties Opnemen of Uitsluiten om uw groepen voor het beleid toe te voegen en selecteer **Klaar**.
3. Selecteer **Cloud-apps** en kies welke apps u wilt beveiligen. Kies bijvoorbeeld **Apps selecteren** en selecteer **Office 365 SharePoint Online** en **Office 365 Exchange Online**.

    Selecteer **OK** om uw wijzigingen op te slaan.

4. Selecteer **Voorwaarden** > **Client-apps** om het beleid toe te passen op apps en browsers. Selecteer bijvoorbeeld **Ja** en schakel vervolgens **Browser** en **Mobiele apps en bureaublad-clients** in.

    Selecteer **OK** om uw wijzigingen op te slaan.

5. Selecteer **Verlenen** om voorwaardelijke toegang toe te passen op basis van de apparaatcompatibiliteit. Selecteer bijvoorbeeld **Toegang verlenen** > **Vereisen dat apparaat wordt gemarkeerd als conform**.

    Kies **Selecteren** om uw wijzigingen op te slaan.

6. Selecteer **Beleid inschakelen** en vervolgens **Maken** om uw wijzigingen op te slaan.



## <a name="monitor-device-compliance"></a>Apparaatcompatibiliteit bewaken  

Bewaak vervolgens de status van apparaten die het nalevingsbeleid voor Microsoft Defender ATP hebben.

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **apparaatconformiteit** > **Beleidsnaleving**.
3. Zoek uw Microsoft Defender ATP-beleid in de lijst op en ga na welke apparaten conform of non-conform zijn.

## <a name="next-steps"></a>Volgende stappen  

[Voorwaardelijke toegang van Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/conditional-access)   
[Microsoft Defender ATP-risicodashboard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)  
[Gebruik beveiligingstaken in combinatie met kwetsbaarheidsbeheer in ATP om problemen op apparaten op te lossen](atp-manage-vulnerabilities.md).  
[Aan de slag met apparaatnalevingsbeleid](device-compliance-get-started.md)  
 
