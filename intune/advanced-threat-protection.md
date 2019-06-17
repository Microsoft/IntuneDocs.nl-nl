---
title: Windows Defender ATP in Microsoft Intune gebruiken - Azure | Microsoft Docs
description: Informatie over het inschakelen van Windows Defender Advanced Threat Protection (ATP) in een end-to-end-scenario, waaronder het inschakelen van ATP in Intune en Windows Defender Security Center (ATP portal), het onboarden van apparaten die een ATP-configuratieprofiel gebruiken, het maken van een nalevingsbeleid voor een Intune-apparaat, het maken van een beleid voor voorwaardelijke toegang van Azure AD en conformiteit van apparaten bewaken.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 78c34345804f600aa62ff5e25ef27a23591e0f5c
ms.sourcegitcommit: cc5d757018d05fc03ac9ea3d30f563df9bfd61ed
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2019
ms.locfileid: "66819872"
---
# <a name="enforce-compliance-for-windows-defender-atp-with-conditional-access-in-intune"></a>Naleving voor Windows Defender ATP met voorwaardelijke toegang in Intune afdwingen

Windows Defender Advanced Threat Protection (ATP) en Microsoft Intune werken samen om beveiligingslekken te voorkomen en beperken de gevolgen van schendingen binnen een organisatie.

Deze functie is van toepassing op: Windows 10-apparaten

Iemand verzendt bijvoorbeeld een Word-bijlage met ingesloten schadelijke code naar een gebruiker binnen uw organisatie. De gebruiker opent de bijlage en activeert de inhoud. Een aanval met verhoogde bevoegdheden wordt gestart en een aanvaller vanaf een externe computer heeft beheerdersrechten op het apparaat van het slachtoffer. De aanvaller krijgt vervolgens extern toegang tot de andere apparaten van de gebruiker.

Deze beveiligingsschending kan invloed hebben op de hele organisatie.

Windows Defender ATP kan beveiligingsgebeurtenissen zoals dit scenario oplossen. Windows Defender Security Center (ATP console) rapporteert de apparaten als 'hoog risico' en levert een gedetailleerd rapport van verdachte activiteiten. In ons voorbeeld detecteert Windows Defender ATP dat het apparaat abnormale code uitvoerde, een escalatie van procesbevoegdheden onderging, schadelijke code injecteerde en een verdachte remote shell uitgaf. Windows Defender ATP geeft u dan opties om de bedreiging te ondervangen.

Wanneer u Intune gebruikt, kunt u een nalevingsbeleid maken dat een aanvaardbaar risiconiveau bepaalt. Als een apparaat dit risico overschrijdt, wordt het apparaat vervolgens niet-conform. In combinatie met voorwaardelijke toegang van Azure Active Directory (AD) Conditional Access, wordt voor de gebruiker de toegang vanaf bedrijfsresources geblokkeerd.

In dit artikel leest u informatie over:

- Het inschakelen van Intune in ATP en inschakelen van ATP in Intune. Deze taken maken een service-naar-service-verbinding tussen Intune en Windows Defender ATP. Met deze verbinding kan Windows Defender ATP het machinerisico voor uw Intune-apparaten schrijven.
- Het maken van nalevingsbeleid in Intune.
- Het inschakelen van voorwaardelijke toegang in Azure Active Directory (AD) voor apparaten op basis van hun risiconiveau.

## <a name="prerequisites"></a>Vereisten

Om ATP met Intune te gebruiken, moet u het volgende geconfigureerd en klaar voor gebruik hebben:

- Tenant met licentie voor Enterprise Mobility + Security E3 en Windows E5 (of Microsoft 365 Enterprise E5)
- Microsoft Intune-omgeving met [Intune-beheerde](windows-enroll.md) Windows 10-apparaten die ook deelnemen aan Azure AD
- [Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) en toegang tot de Windows Defender Security Center (ATP portal)

## <a name="enable-windows-defender-atp-in-intune"></a>Windows Defender ATP in Intune inschakelen

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Selecteer **Apparaatcompatibiliteit** > **Windows Defender ATP** > **Het Windows Defender-beveiligingscentrum openen**.

    ![Selecteren om het Windows Defender-beveiligingscentrum te openen](./media/atp-device-compliance-open-windows-defender.png)

4. In het **Windows Defender Beveiligingscentrum**:
    1. Selecteer **Instellingen** > **Geavanceerde functies**.
    2. Voor **Microsoft Intune-verbinding**, kiest u **Aan**:

        ![De verbinding met Intune inschakelen](./media/atp-security-center-intune-toggle.png)

    3. Selecteer **Voorkeuren opslaan**.

5. Ga terug naar Intune, **Apparaatconformiteit** > **Windows Defender ATP**. Stel **Windows-apparaten met versie 10.0.15063 en hoger verbinden met Windows Defender ATP** in op **Aan**.
6. Selecteer **Opslaan**.

Gewoonlijk voltooit u deze taak één keer. Dus als ATP al is ingeschakeld in uw Intune-resource, hoeft u dit niet opnieuw uit te voeren.

## <a name="onboard-devices-using-a-configuration-profile"></a>Onboard-apparaten die een configuratieprofiel gebruiken

Wanneer een eindgebruiker wordt ingeschreven bij Intune, kunt u verschillende instellingen naar het apparaat pushen met behulp van een configuratieprofiel. Dit geldt ook voor Windows Defender ATP.

Windows Defender bevat een geïntegreerd configuratiepakket dat communiceert met [Windows Defender ATP-services](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) om bestanden te scannen, bedreigingen te detecteren en het risico aan Windows Defender ATP te rapporteren.

Wanneer u de onboarding uitvoert, ontvangt Intune een automatisch gegenereerd configuratiepakket van Windows Defender ATP. Wanneer het profiel naar het apparaat wordt gepusht of erop wordt geïmplementeerd, wordt dit configuratiepakket ook naar het apparaat gepusht. Hierdoor kan Windows Defender ATP het apparaat beveiligen tegen de bedreigingen.

Wanneer u eenmaal onboarding van een apparaat met het configuratiepakket hebt uitgevoerd, dan hoeft u dit niet opnieuw te doen. U kunt apparaten onboarden met behulp van een [Groepsbeleid of System Center Configuration Manager (SCCM)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-endpoints-windows-defender-advanced-threat-protection).

### <a name="create-the-configuration-profile"></a>Het configuratieprofiel maken

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Voer een **Naam** en **Beschrijving** in.
4. Voor **Platform** selecteert u **Windows 10 en hoger**
5. Voor **Profieltype** selecteert u **Windows Defender ATP (Windows 10 Desktop)** .
6. Configureer de gewenste instellingen:

  - **Type clientconfiguratiepakket voor Windows Defender ATP**: Selecteer **Onboarding uitvoeren** om het configuratiepakket aan het profiel toe te voegen. Selecteer **Offboarding uitvoeren** om configuratiepakket uit het profiel te verwijderen.
  
    > [!NOTE] 
    > Als u een verbinding met Windows Defender ATP tot stand hebt gebracht, start **Onboarding uitvoeren** in Intune automatisch en wordt het configuratieprofiel voor u toegevoegd. In dat geval is de instelling **Type clientconfiguratiepakket voor Windows Defender ATP** niet beschikbaar.
  
  - **Voorbeelddeling voor alle bestanden**: Via **Inschakelen** staat u toe dat voorbeelden worden verzameld en gedeeld met Windows Defender ATP. Als u bijvoorbeeld een verdacht bestand ziet, kunt u het verzenden naar Windows Defender ATP voor grondige analyse. **Niet geconfigureerd**: eventuele voorbeelden voor het Windows Defender ATP worden niet gedeeld.
  - **Frequentie van telemetrierapporten versnellen**: U kunt deze instelling **inschakelen** voor apparaten met een hoog risico, zodat vaker telemetrie naar de Windows Defender ATP-service wordt gerapporteerd.

    [Onboard Windows 10 machines using System Center Configuration Manager](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-endpoints-sccm-windows-defender-advanced-threat-protection) (Windows 10-apparaten onboarden die System Center Configuration Manager gebruiken) bevat meer informatie over deze instellingen voor Windows Defender ATP.

7. Selecteer **OK** en **Maken** om wijzigingen op te slaan. Hiermee maakt u het profiel aan.

## <a name="create-the-compliance-policy"></a>Het nalevingsbeleid maken
Het nalevingsbeleid bepaalt een aanvaardbaar risiconiveau op een apparaat.

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **Apparaatconformiteit** > **Beleid** > **Beleid maken**.
3. Voer een **Naam** en **Beschrijving** in.
4. In **Platform** selecteert u **Windows 10 en hoger**.
5. Stel in de instellingen voor **Windows Defender ATP** de optie **Vereisen dat het apparaat op of onder het apparaatdreigingsniveau moet zijn** in op het gewenste niveau. De classificatie van bedreigingsniveaus wordt [bepaald door Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/alerts-queue-windows-defender-advanced-threat-protection).

   - **Veilig**: Dit is het veiligste niveau. Het apparaat heeft geen toegang tot bedrijfsresources als er ook maar één bedreiging is gevonden. Als er bedreigingen worden gevonden, wordt het apparaat geëvalueerd als niet-compatibel. (Windows Defender ATP gebruikt de waarde *Veilig*.)
   - **Laag**: Het apparaat is conform als er alleen bedreigingen van een laag niveau aanwezig zijn. Apparaten met gemiddelde of hoge dreigingsniveaus zijn niet conform.
   - **Gemiddeld**: Het apparaat is conform als de bedreigingen op het apparaat van laag of gemiddeld niveau zijn. Als er bedreigingen van hoog niveau worden aangetroffen, wordt het apparaat als niet-compatibel beoordeeld.
   - **Hoog**: Dit niveau is het minst veilig en laat alle bedreigingsniveaus toe. Dus apparaten met hoge, gemiddelde of lage bedreigingsniveaus worden beschouwd als conform.

6. Selecteer **OK** en **Maken** om wijzigingen op te slaan (en het beleid aan te maken).

## <a name="assign-the-policy"></a>Wijs het beleid toe

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **Apparaatconformiteit** > **beleid**> Selecteer uw Windows Defender ATP-nalevingsbeleid.
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

5. Selecteer **Verlenen** om voorwaardelijke toegang toe te passen op basis van de conformiteit van apparaat. Selecteer bijvoorbeeld **Toegang verlenen** > **Vereisen dat apparaat wordt gemarkeerd als conform**.

    Kies **Selecteren** om uw wijzigingen op te slaan.

6. Selecteer **Beleid inschakelen** en vervolgens **Maken** om uw wijzigingen op te slaan.

[Wat is voorwaardelijke toegang? ](conditional-access.md) is een goede bron.

## <a name="monitor-device-compliance"></a>Apparaatcompatibiliteit bewaken
Bewaak vervolgens de status van apparaten die het nalevingsbeleid voor Windows Defender ATP hebben.

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **apparaatconformiteit** > **Beleidsnaleving**.
3. Vind uw Windows Defender ATP-beleid in de lijst en zie welke apparaten conform of non-conform zijn.

## <a name="more-good-stuff"></a>Meer goede dingen
[Voorwaardelijke toegang van Windows Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/conditional-access-windows-defender-advanced-threat-protection)  
[Windows Defender ATP risico dashboard](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection)  
[Aan de slag met apparaatnalevingsbeleid](device-compliance-get-started.md)  
[Voorwaardelijke toegang in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
