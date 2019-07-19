---
title: Microsoft Defender ATP in Microsoft Intune gebruiken - Azure | Microsoft Docs
description: Informatie over het inschakelen van Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) in een end-to-end-scenario, waaronder het inschakelen van Microsoft Defender ATP in Intune en Microsoft Defender Security Center, het onboarden van apparaten die een Microsoft Defender ATP-configuratieprofiel gebruiken, het maken van een nalevingsbeleid voor een Intune-apparaat, het maken van een beleid voor voorwaardelijke toegang van Azure AD en het bewaken van de conformiteit van apparaten.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/12/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 069658bdd231be96d7f9fbe23de1b4e38fdc5a9e
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2019
ms.locfileid: "67885153"
---
# <a name="enforce-compliance-for-microsoft-defender-atp-with-conditional-access-in-intune"></a>Naleving voor Microsoft Defender ATP met voorwaardelijke toegang in Intune afdwingen  

Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) en Microsoft Intune werken samen om beveiligingslekken te voorkomen en beperken de gevolgen van schendingen binnen een organisatie.

Deze functie is van toepassing op: Windows 10-apparaten

Iemand verzendt bijvoorbeeld een Word-bijlage met ingesloten schadelijke code naar een gebruiker binnen uw organisatie. De gebruiker opent de bijlage en activeert de inhoud. Een aanval met verhoogde bevoegdheden wordt gestart en een aanvaller vanaf een externe computer heeft beheerdersrechten op het apparaat van het slachtoffer. De aanvaller krijgt vervolgens extern toegang tot de andere apparaten van de gebruiker.

Deze beveiligingsschending kan invloed hebben op de hele organisatie.

Microsoft Defender ATP kan beveiligingsgebeurtenissen zoals dit scenario oplossen. Microsoft Defender Security Center rapporteert de apparaten als 'hoog risico' en levert een gedetailleerd rapport van verdachte activiteiten. In ons voorbeeld detecteert Microsoft Defender ATP dat het apparaat abnormale code uitvoerde, een escalatie van procesbevoegdheden onderging, schadelijke code injecteerde en een verdachte remote shell uitgaf. Microsoft Defender ATP geeft u dan opties om de bedreiging te beperken.

Wanneer u Intune gebruikt, kunt u een nalevingsbeleid maken dat een aanvaardbaar risiconiveau bepaalt. Als een apparaat dit risico overschrijdt, wordt het apparaat vervolgens niet-conform. In combinatie met voorwaardelijke toegang van Azure Active Directory (AD) Conditional Access, wordt voor de gebruiker de toegang vanaf bedrijfsresources geblokkeerd.

In dit artikel leest u informatie over:

- Intune inschakelen in Microsoft Defender Security Center en Microsoft Defender ATP inschakelen in Intune. Met deze taken maakt u een service-naar-service-verbinding tussen Intune en Microsoft Defender ATP. Via deze verbinding kan Microsoft Defender ATP het machinerisico voor uw Intune-apparaten schrijven.
- Het maken van nalevingsbeleid in Intune.
- Het inschakelen van voorwaardelijke toegang in Azure Active Directory (AD) voor apparaten op basis van hun risiconiveau.

## <a name="prerequisites"></a>Vereisten

Als u Microsoft Defender ATP met Intune wilt gebruiken, moet u het volgende geconfigureerd en klaar voor gebruik hebben:

- Tenant met licentie voor Enterprise Mobility + Security E3 en Windows E5 (of Microsoft 365 Enterprise E5)
- Microsoft Intune-omgeving met [Intune-beheerde](windows-enroll.md) Windows 10-apparaten die ook deelnemen aan Azure AD
- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) en toegang tot de Microsoft Defender Security Center (ATP-portal)

## <a name="enable-microsoft-defender-atp-in-intune"></a>Microsoft Defender ATP in Intune inschakelen

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

Gewoonlijk voltooit u deze taak één keer. Als Microsoft Defender ATP al is ingeschakeld in uw Intune-resource, hoeft u dit dus niet opnieuw uit te voeren.

## <a name="onboard-devices-using-a-configuration-profile"></a>Onboard-apparaten die een configuratieprofiel gebruiken

Wanneer een eindgebruiker wordt ingeschreven bij Intune, kunt u verschillende instellingen naar het apparaat pushen met behulp van een configuratieprofiel. Dit geldt ook voor Microsoft Defender ATP.

Microsoft Defender ATP bevat een geïntegreerd configuratiepakket dat communiceert met [Microsoft Defender ATP-services](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) om bestanden te scannen, bedreigingen te detecteren en het risico aan Microsoft Defender ATP te rapporteren.

Wanneer u de onboarding uitvoert, ontvangt Intune een automatisch gegenereerd configuratiepakket van Microsoft Defender ATP. Intune pusht het configuratiepakket naar het apparaat wanneer het configuratieprofiel naar het apparaat wordt verzonden, zodat Microsoft Defender ATP het apparaat kan controleren op bedreigingen.

Wanneer u eenmaal onboarding van een apparaat met het configuratiepakket hebt uitgevoerd, dan hoeft u dit niet opnieuw te doen. U kunt apparaten onboarden met behulp van een [Groepsbeleid of System Center Configuration Manager (SCCM)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).

### <a name="create-the-configuration-profile"></a>Het configuratieprofiel maken

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

## <a name="create-the-compliance-policy"></a>Het nalevingsbeleid maken
Het nalevingsbeleid bepaalt een aanvaardbaar risiconiveau op een apparaat.

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **Apparaatconformiteit** > **Beleid** > **Beleid maken**.
3. Voer een **Naam** en **Beschrijving** in.
4. In **Platform** selecteert u **Windows 10 en hoger**.
5. Stel in de instellingen voor **Microsoft Defender ATP** de optie **Vereisen dat het apparaat op of onder het apparaatdreigingsniveau moet zijn** in op het gewenste niveau. De classificatie van bedreigingsniveaus wordt [bepaald door Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/alerts-queue).

   - **Veilig**: Dit is het veiligste niveau. Het apparaat heeft geen toegang tot bedrijfsresources als er ook maar één bedreiging is gevonden. Als er bedreigingen worden gevonden, wordt het apparaat geëvalueerd als niet-compatibel. (Microsoft Defender ATP gebruikt de waarde *Veilig*.)
   - **Laag**: Het apparaat is conform als er alleen bedreigingen van een laag niveau aanwezig zijn. Apparaten met een gemiddeld of hoog dreigingsniveau zijn niet conform.
   - **Gemiddeld**: Het apparaat is conform als de bedreigingen op het apparaat van laag of gemiddeld niveau zijn. Als er bedreigingen van hoog niveau worden aangetroffen, wordt het apparaat als niet-compatibel beoordeeld.
   - **Hoog**: Dit niveau is het minst veilig en laat alle bedreigingsniveaus toe. Apparaten met een hoog, gemiddeld of laag bedreigingsniveau worden daarom beschouwd als conform.

6. Selecteer **OK** en **Maken** om wijzigingen op te slaan (en het beleid aan te maken).

## <a name="assign-the-policy"></a>Wijs het beleid toe

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **Apparaatconformiteit** > **beleid** en selecteer uw Microsoft Defender ATP-nalevingsbeleid.
3. Selecteer **Toewijzingen**.
4. Neem uw Azure AD-groepen op of sluit ze uit om ze toe te wijzen aan het beleid.
5. Selecteer **Opslaan** voor het implementeren van het beleid naar de groepen. De apparaten die worden gebruikt door de gebruikers op wie het beleid is toegepast, worden gecontroleerd om te zien of ze conform zijn.

## <a name="create-a-conditional-access-policy"></a>Beleid voor voorwaardelijke toegang maken
Het beleid voor voorwaardelijke toegang blokkeert de toegang tot resources *als* het apparaat niet conform is. Dus als een apparaat het risiconiveau overschrijdt, kunt u toegang tot bedrijfsresources zoals SharePoint of Exchange Online blokkeren.  

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

[Wat is voorwaardelijke toegang? ](conditional-access.md) is een goede bron.

## <a name="monitor-device-compliance"></a>Apparaatcompatibiliteit bewaken
Bewaak vervolgens de status van apparaten die het nalevingsbeleid voor Microsoft Defender ATP hebben.

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **apparaatconformiteit** > **Beleidsnaleving**.
3. Zoek uw Microsoft Defender ATP-beleid in de lijst op en ga na welke apparaten conform of non-conform zijn.

## <a name="more-good-stuff"></a>Meer goede dingen
[Voorwaardelijke toegang van Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/conditional-access)  
[Microsoft Defender ATP-risicodashboard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)  

[Aan de slag met apparaatnalevingsbeleid](device-compliance-get-started.md)  
[Voorwaardelijke toegang in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)