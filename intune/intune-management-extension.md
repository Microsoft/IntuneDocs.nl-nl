---
title: PowerShell-scripts aan Windows 10-apparaten toevoegen in Microsoft Intune - Azure | Microsoft Docs
description: Maak en voer PowerShell-scripts uit, wijs het scriptbeleid toe aan Azure Active Directory-groepen, gebruik rapporten om de scripts te controleren en zie de stappen om scripts te verwijderen die u toevoegt op Windows 10-apparaten in Microsoft Intune. Zie ook enkele veelvoorkomende problemen en oplossingen.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/03/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 66a23b75913f6465064a988bd8f2ba9c2b4c36d6
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/23/2019
ms.locfileid: "61514117"
---
# <a name="use-powershell-scripts-on-windows-10-devices-in-intune"></a>PowerShell-scripts op Windows 10-apparaten gebruiken in Intune

Gebruik de Microsoft Intune-beheeruitbreiding om PowerShell-scripts te uploaden in Intune om deze uit te voeren op Windows 10-apparaten. De beheeruitbreiding verbetert Windows 10 MDM (Mobile Device Management) en maakt het eenvoudiger om over te stappen op een moderner beheer.

Deze functie is van toepassing op:

- Windows 10 en hoger

## <a name="move-to-modern-management"></a>Uw beheer moderniseren

Computergebruik door de eindgebruiker ondergaat een digitale transformatie. Klassieke, traditionele IT richt zich op een platform voor een enkel apparaat, apparaten in bedrijfseigendom, gebruikers die vanuit hun kantoor werken en verschillende handmatige, reactieve IT-processen. Op de moderne werkplek worden vele platformen gebruikt die in eigendom zijn van de gebruiker en het bedrijf. De moderne werkplek maakt mogelijk dat gebruikers vanuit elke locatie kunnen werken en voorziet in geautomatiseerde en proactieve IT-processen.

Met MDM-services, zoals Microsoft Intune, kunt u mobiele en desktop-apparaten met Windows 10 beheren. De ingebouwde Windows 10-beheerclient communiceert met Intune voor de uitvoering van bedrijfsbeheertaken. Er zijn enkele taken die u mogelijk nodig hebt, zoals geavanceerde apparaatconfiguratie en probleemoplossing. Voor Win32-app-beheer gebruikt u de functie [Win32-app-beheer](apps-win32-app-management.md) op uw Windows 10-apparaten.

De Intune-beheeruitbreiding is een aanvulling op de meegeleverde Windows 10-MDM-functies. U kunt PowerShell-scripts maken die u kunt uitvoeren op Windows 10-apparaten. U kunt bijvoorbeeld een PowerShell-script maken dat geavanceerde apparaatconfiguraties uitvoert, het script uploadt naar Intune, het script toewijst aan een AD-groep (Azure Active Directory) en het script uitvoert. Vervolgens kunt u de uitvoeringsstatus van het script van het begin tot het eind controleren.

## <a name="prerequisites"></a>Vereisten

De Intune-beheeruitbreiding heeft de volgende vereisten:

- Apparaten moeten worden gekoppeld of ingeschreven bij Azure AD en Azure AD en Intune moeten zijn geconfigureerd voor [automatische inschrijving in Intune](quickstart-setup-auto-enrollment.md). De Intune-beheeruitbreiding biedt ondersteuning voor ingeschreven Windows-apparaten die zijn toegevoegd aan Azure AD, zijn toegevoegd aan een hybride Azure AD-domein en gezamenlijk worden beheerd.
- Op apparaten moet Windows 10 versie 1607 of hoger worden uitgevoerd.
- De agent van de Intune-beheeruitbreiding wordt geïnstalleerd wanneer een PowerShell-script of een Win32-app wordt geïmplementeerd in een gebruikers- of apparaatbeveiligingsgroep.

## <a name="create-a-script-policy"></a>Een scriptbeleid maken 

1. Selecteer in [Azure Portal](https://portal.azure.com) de optie **Alle services** > filter op **Intune** > selecteer **Intune**.
2. Selecteer **Apparaatconfiguratie** > **PowerShell-scripts** > **Toevoegen**.
3. Voer de volgende eigenschappen in:
    - **Naam**: Voer een naam in voor het PowerShell-script. 
    - **Beschrijving**: Voer een beschrijving in voor het PowerShell-script. Deze instelling is optioneel, maar wordt aanbevolen. 
    - **Scriptlocatie**: Blader naar het PowerShell-script. Het script moet kleiner zijn dan 200 KB (ASCII).
4. Kies **Configureren** en voer de volgende eigenschappen in:
    - **U kunt dit script als volgt uitvoeren met behulp van de aanmeldingsgegevens**: Selecteer **Ja** om het script op het apparaat uit te voeren met de referenties van de gebruiker. Kies **Nee** (standaard) om het script in de systeemcontext uit te voeren. Veel beheerders kiezen de optie **Ja**. Kies **Nee** als het noodzakelijk is dat het script wordt uitgevoerd in de systeemcontext.
    - **Controle van handtekening voor script afdwingen**: Selecteer **Ja** als het script moet worden ondertekend door een vertrouwde uitgever. Selecteer **Nee** (standaard) als het script niet hoeft te worden ondertekend. 
    - **Script uitvoeren in 64-bits PowerShell-host**: Selecteer **Ja** om het script in een 64-bits PowerShell-host (PS) uit te voeren in een 64-bits clientarchitectuur. Selecteer **Nee** (standaardinstelling) om het script in een 32-bits PowerShell-host uit te voeren.

      Gebruik de volgende tabel voor het gedrag van nieuw en bestaand beleid als u deze optie instelt op **Ja** of **Nee**:

      | Script uitvoeren in 64-bits PS-host | Clientarchitectuur | Nieuw PS-script | PS-script voor bestaand beleid |
      | --- | --- | --- | --- | 
      | Nee | 32-bits  | 32-bits PS-host wordt ondersteund | Kan alleen worden uitgevoerd in de 32-bits PS-host, die zowel op een 32-bits als 64-bits architectuur werkt. |
      | Ja | 64-bits | Hiermee voert u script uit in de 64-bits PS-host voor 64-bits architecturen. Wanneer u dit uitvoert op 32-bits, wordt het script uitgevoerd in een 32-bits PS-host. | Hiermee wordt script uitgevoerd in de 32-bits PS-host. Als u deze instelling wijzigt in 64-bits, wordt het script geopend (maar niet uitgevoerd) in een 64-bits PS-host en worden de resultaten hiervan gerapporteerd. Wanneer u dit uitvoert op 32-bits, wordt het script uitgevoerd in een 32-bits PS-host. |

    ![PowerShell-scripts toevoegen en gebruiken in Microsoft Intune](./media/mgmt-extension-add-script.png)
5. Selecteer **OK** > **Maken** om het script op te slaan.

## <a name="assign-the-policy"></a>Wijs het beleid toe

1. Selecteer in **PowerShell-scripts** het script dat u wilt toewijzen, en kies vervolgens **Beheren** > **Toewijzingen**.

    ![PowerShell-script toewijzen aan of implementeren in apparaatgroepen in Microsoft Intune](./media/mgmt-extension-assignments.png)

2. Kies **Groepen selecteren** beschikbare Microsoft Azure Active Directory-groepen in een lijst op te nemen. 
3. Selecteer een of meer groepen die de gebruikers bevatten wiens apparaten het script ontvangen. Kies **Selecteren** om het beleid aan de geselecteerde groepen toe te wijzen.

> [!NOTE]
> - Eindgebruikers hoeven zich niet aan te melden bij het apparaat om PowerShell-scripts uit te voeren.
> - PowerShell-scripts in Intune kunnen worden gericht op Azure AD-apparaatbeveiligingsgroepen.
> - PowerShell-scripts in Intune kunnen worden gericht op Azure AD-gebruikersbeveiligingsgroepen.

De Intune-beheerextensieclient controleert één keer per uur en na elke keer dat er opnieuw is opgestart bij Intune of er nieuwe scripts of wijzigingen zijn. Wanneer u het beleid aan de Microsoft Azure Active Directory-groepen toewijst, wordt het PowerShell-script uitgevoerd en worden de resultaten van de uitvoering gerapporteerd. Zodra het script wordt uitgevoerd, wordt deze pas weer opnieuw uitgevoerd als het script of het beleid is gewijzigd.

## <a name="monitor-run-status"></a>Uitvoeringsstatus bewaken

U kunt de uitvoeringsstatus van PowerShell-scripts voor gebruikers en apparaten in Azure Portal controleren.

Selecteer in **PowerShell-scripts** het script dat u wilt controleren, kies **Controleren** en kies vervolgens een van de volgende rapporten:

- **Apparaatstatus**
- **Gebruikersstatus**

## <a name="troubleshoot-scripts"></a>Problemen met scripts oplossen

Agentlogboeken op de clientcomputer staan meestal in `\ProgramData\Microsoft\IntuneManagementExtension\Logs`. U kunt [CMTrace.exe](https://docs.microsoft.com/sccm/core/support/tools) gebruiken om deze logboekbestanden te bekijken. 

![Schermopname of voorbeeldlogboeken van de cmtrace-agent in Microsoft Intune](./media/apps-win32-app-10.png)  

## <a name="delete-a-script"></a>Een script verwijderen

Klik in **PowerShell-scripts** met de rechtermuisknop op het script en selecteer **Verwijderen**.

## <a name="common-issues-and-resolutions"></a>Veelvoorkomende problemen en oplossingen

De PowerShell-scripts worden niet bij elke aanmelding uitgevoerd. Ze worden alleen uitgevoerd wanneer ze opnieuw zijn opgestart of als de **Microsoft Intune-beheeruitbreiding** opnieuw wordt gestart. De client met de Intune-beheeruitbreiding controleert eenmaal per uur op wijzigingen in het script of het beleid in Intune.

#### <a name="issue-intune-management-extension-doesnt-download"></a>Probleem: Intune-beheeruitbreiding wordt niet gedownload

**Mogelijke oplossingen**:

- Controleer of de apparaten automatisch zijn geregistreerd in Azure AD. Om dit te controleren, gaat u op het apparaat als volgt te werk: 

  1. Ga naar **Instellingen** > **Accounts** > **Toegang tot werk of school**.
  2. Selecteer het deelnemende account > **Info**.
  3. Selecteer onder **Geavanceerde diagnostische gegevens** de optie **Rapport maken**.
  4. Open het `MDMDiagReport` in een webbrowser en ga naar de sectie **Geregistreerde configuratiebronnen**.
  5. Zoek de eigenschap **MDMDeviceWithAAD**. Als deze eigenschap niet bestaat, is uw apparaat niet automatisch geregistreerd.

    [Automatische inschrijving voor Windows 10 inschakelen](windows-enroll.md#enable-windows-10-automatic-enrollment) bevat de stappen.

#### <a name="issue-powershell-scripts-do-not-run"></a>Probleem: De PowerShell-scripts worden niet uitgevoerd

**Mogelijke oplossingen**:

- Controleer of de Intune-beheeruitbreiding is gedownload naar `%ProgramFiles(x86)%\Microsoft Intune Management Extension`.
- Scripts worden niet uitgevoerd op Surface Hubs.
- Raadpleeg de logboeken in `\ProgramData\Microsoft\IntuneManagementExtension\Logs` op fouten.
- Als u wilt weten of er problemen zijn met machtigingen, controleert u of de eigenschappen van het PowerShell-script zijn ingesteld op `Run this script using the logged on credentials`. Controleer ook of de aangemelde gebruiker de juiste machtigingen heeft om het script uit te voeren.
- Voer een voorbeeldscript uit om scriptproblemen te isoleren. Maak bijvoorbeeld een map `C:\Scripts` en geef iedereen volledig beheer voor die map. Voer het volgende script uit:

  ```powershell
  write-output "Script worked" | out-file c:\Scripts\output.txt
  ```

  Als dat lukt, moet output.txt worden gemaakt dat de tekst 'Script worked' bevat.

- Als u de uitvoering van het script wilt testen zonder Intune, voert u de scripts lokaal in de systeemcontext uit met behulp van het hulpprogramma [psexec](https://docs.microsoft.com/sysinternals/downloads/psexec):

  `psexec -i -s`

## <a name="next-steps"></a>Volgende stappen

Uw profielen [bewaken](device-profile-monitor.md) en [profielproblemen oplossen](device-profile-troubleshoot.md).
