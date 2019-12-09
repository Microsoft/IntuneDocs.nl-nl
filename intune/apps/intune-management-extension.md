---
title: PowerShell-scripts aan Windows 10-apparaten toevoegen in Microsoft Intune - Azure | Microsoft Docs
description: Maak en voer PowerShell-scripts uit, wijs het scriptbeleid toe aan Azure Active Directory-groepen, gebruik rapporten om de scripts te controleren en zie de stappen om scripts te verwijderen die u toevoegt op Windows 10-apparaten in Microsoft Intune. Zie ook enkele veelvoorkomende problemen en oplossingen.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cef30238a4470395ccf58cf4d0619db78dd85b5a
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563466"
---
# <a name="use-powershell-scripts-on-windows-10-devices-in-intune"></a>PowerShell-scripts op Windows 10-apparaten gebruiken in Intune

Gebruik de Microsoft Intune-beheeruitbreiding om PowerShell-scripts te uploaden in Intune om deze uit te voeren op Windows 10-apparaten. De beheeruitbreiding verbetert Windows 10 MDM (Mobile Device Management) en maakt het eenvoudiger om over te stappen op een moderner beheer.

Deze functie is van toepassing op:

- Windows 10 en hoger

## <a name="move-to-modern-management"></a>Uw beheer moderniseren

Computergebruik door de eindgebruiker ondergaat een digitale transformatie. Klassieke, traditionele IT richt zich op een platform voor een enkel apparaat, apparaten in bedrijfseigendom, gebruikers die vanuit hun kantoor werken en verschillende handmatige, reactieve IT-processen. Op de moderne werkplek worden vele platformen gebruikt die in eigendom zijn van de gebruiker en het bedrijf. De moderne werkplek maakt mogelijk dat gebruikers vanuit elke locatie kunnen werken en voorziet in geautomatiseerde en proactieve IT-processen.

Met MDM-services, zoals Microsoft Intune, kunt u mobiele en desktop-apparaten met Windows 10 beheren. De ingebouwde Windows 10-beheerclient communiceert met Intune voor de uitvoering van bedrijfsbeheertaken. Er zijn enkele taken die u mogelijk nodig hebt, zoals geavanceerde apparaatconfiguratie en probleemoplossing. Voor Win32-app-beheer gebruikt u de functie [Win32-app-beheer](app-management.md) op uw Windows 10-apparaten.

De Intune-beheeruitbreiding is een aanvulling op de meegeleverde Windows 10-MDM-functies. U kunt PowerShell-scripts maken die u kunt uitvoeren op Windows 10-apparaten. U kunt bijvoorbeeld een PowerShell-script maken dat geavanceerde apparaatconfiguraties kan uitvoeren. Upload vervolgens het script naar Intune, wijs het script toe aan een Azure Active Directory-groep (AD) en voer het script uit. Vervolgens kunt u de uitvoeringsstatus van het script van het begin tot het eind controleren.

## <a name="prerequisites"></a>Vereisten

De Intune-beheeruitbreiding heeft de volgende vereisten. Zodra aan de vereisten wordt voldaan, wordt de Intune-beheeruitbreiding altijd automatisch geïnstalleerd wanneer een PowerShell-script of Win32-app wordt toegewezen aan de gebruiker of het apparaat.

- Apparaten met Windows 10 versie 1607 of hoger. Als het apparaat wordt ingeschreven via [bulksgewijze automatische inschrijving](../enrollment/windows-bulk-enroll.md), moeten deze zijn voorzien van Windows 10 versie 1703 of hoger. De Intune-beheeruitbreiding wordt in de S-modus niet ondersteund in Windows 10 omdat het in de S-modus niet is toegestaan om niet-Store-apps uit te voeren. 
  
- Apparaten die zijn gekoppeld aan Azure Active Directory (AD), met inbegrip van:  
  
  - Hybride Azure AD-koppeling: Apparaten die aan Azure Active Directory (AD) én aan een on-premises Active Directory (AD) zijn gekoppeld. Zie [De implementatie van uw hybride Azure Active Directory-deelname plannen](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan) voor hulp.

- Apparaten die zijn ingeschreven bij Intune, met inbegrip van:

  - Apparaten die zijn ingeschreven bij een groepsbeleid (GPO). Zie [Enroll a Windows 10 device automatically using Group Policy](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy) (Windows 10-apparaten automatisch inschrijven aan de hand van groepsbeleid) voor hulp.
  
  - Handmatig bij Intune ingeschreven apparaten. Dit is in de volgende situaties het geval:
  
    - [Automatische inschrijving bij Intune](../enrollment/quickstart-setup-auto-enrollment.md) is ingeschakeld in Azure AD. De eindgebruiker meldt zich via een lokaal gebruikersaccount aan op het apparaat en koppelt het apparaat handmatig aan Azure AD. Vervolgens meldt de eindgebruiker zich op het apparaat aan met een Azure AD-account.
    
    OF  
    
    - De gebruiker meldt zich op het apparaat aan bij diens Azure AD-account, waarna het apparaat bij Intune wordt ingeschreven.

  - Gezamenlijk beheerde apparaten waarop gebruik wordt gemaakt Configuration Manager en Intune. Zorg ervoor dat de workload **Apps** is ingesteld op **testfase voor Intune** of **Intune**. Raadpleeg de volgende artikelen voor meer informatie: 
  
    - [Wat is co-beheer?](https://docs.microsoft.com/sccm/comanage/overview) 
    - [Workload Client-apps](https://docs.microsoft.com/sccm/comanage/workloads#client-apps)
    - [Configuration Manager-workloads overschakelen naar Intune](https://docs.microsoft.com/sccm/comanage/how-to-switch-workloads)
  
> [!TIP]
> Zorg ervoor dat apparaten zijn [gekoppeld](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network) aan Azure AD. Apparaten die alleen [geregistreerd](https://docs.microsoft.com/azure/active-directory/user-help/user-help-register-device-on-network) zijn in Azure AD zullen scripts niet ontvangen.

## <a name="create-a-script-policy-and-assign-it"></a>Een scriptbeleid maken en het toewijzen

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apparaten** > **PowerShell-scripts** > **Toevoegen**.

    ![PowerShell-scripts toevoegen en gebruiken in Microsoft Intune](./media/intune-management-extension/mgmt-extension-add-script.png)

3. Voer in **Basisinformatie** de volgende eigenschappen in en selecteer **Volgende**:
    - **Naam**: Voer een naam in voor het PowerShell-script. 
    - **Beschrijving**: Voer een beschrijving in voor het PowerShell-script. Deze instelling is optioneel, maar wordt aanbevolen.
4. Voer in **Scriptinstellingen** de volgende eigenschappen in en selecteer **Volgende**:
    - **Scriptlocatie**: Blader naar het PowerShell-script. Het script moet kleiner zijn dan 200 KB (ASCII).
    - **U kunt dit script als volgt uitvoeren met behulp van de aanmeldingsgegevens**: Selecteer **Ja** om het script op het apparaat uit te voeren met de referenties van de gebruiker. Kies **Nee** (standaard) om het script in de systeemcontext uit te voeren. Veel beheerders kiezen de optie **Ja**. Kies **Nee** als het noodzakelijk is dat het script wordt uitgevoerd in de systeemcontext.
    - **Controle van handtekening voor script afdwingen**: Selecteer **Ja** als het script moet worden ondertekend door een vertrouwde uitgever. Selecteer **Nee** (standaard) als het script niet hoeft te worden ondertekend. 
    - **Script uitvoeren in 64-bits PowerShell-host**: Selecteer **Ja** om het script in een 64-bits PowerShell-host (PS) uit te voeren in een 64-bits clientarchitectuur. Selecteer **Nee** (standaardinstelling) om het script in een 32-bits PowerShell-host uit te voeren.

      Gebruik de volgende tabel voor het gedrag van nieuw en bestaand beleid als u deze optie instelt op **Ja** of **Nee**:

      | Script uitvoeren in 64-bits PS-host | Clientarchitectuur | Nieuw PS-script | PS-script voor bestaand beleid |
      | --- | --- | --- | --- | 
      | Nee | 32-bits  | 32-bits PS-host wordt ondersteund | Kan alleen worden uitgevoerd in de 32-bits PS-host, die zowel op een 32-bits als 64-bits architectuur werkt. |
      | Ja | 64-bits | Hiermee voert u script uit in de 64-bits PS-host voor 64-bits architecturen. Wanneer u dit uitvoert op 32-bits, wordt het script uitgevoerd in een 32-bits PS-host. | Hiermee wordt script uitgevoerd in de 32-bits PS-host. Als u deze instelling wijzigt in 64-bits, wordt het script geopend (maar niet uitgevoerd) in een 64-bits PS-host en worden de resultaten hiervan gerapporteerd. Wanneer u dit uitvoert op 32-bits, wordt het script uitgevoerd in een 32-bits PS-host. |

5. Selecteer **Bereiktags**. Bereiktags zijn optioneel. [Op rollen gebaseerd toegangsbeheer (RBAC) en bereiktags gebruiken voor gedistribueerde IT](../fundamentals/scope-tags.md) bevat meer informatie.

    Een bereiktag toevoegen:

    1. Selecteer **Bereiktags selecteren** > selecteer een bestaande bereiktag uit de lijst > **Selecteren**.

    2. Selecteer **Volgende** als u klaar bent.

6. Selecteer **Toewijzingen** > **Selecteer groepen om in te sluiten**. Er wordt een bestaande lijst met Azure AD-groepen weergegeven.

    1. Selecteer een of meer groepen die de gebruikers bevatten wiens apparaten het script ontvangen. Kies **Selecteren**. De groepen die u hebt gekozen, worden weergegeven in de lijst en ontvangen uw beleid.

        > [!NOTE]
        > PowerShell-scripts in Intune kunnen worden gericht op Azure AD-apparaatbeveiligingsgroepen of op Azure AD-gebruikersbeveiligingsgroepen.

    2. Selecteer **Volgende**.

        ![PowerShell-script toewijzen aan of implementeren in apparaatgroepen in Microsoft Intune](./media/intune-management-extension/mgmt-extension-assignments.png)

7. In **Controleren en toevoegen** wordt een samenvatting weer gegeven van de instellingen die u hebt geconfigureerd. Selecteer **Toevoegen** om het script op te slaan. Wanneer u **Toevoegen** selecteert, wordt het beleid geïmplementeerd in de groepen die u hebt gekozen.

## <a name="important-considerations"></a>Belangrijke overwegingen

- Als scripts zijn ingesteld op de gebruikerscontext en de gebruiker beheerdersrechten heeft, wordt het PowerShell-script standaard uitgevoerd met beheerdersrechten.

- Eindgebruikers hoeven zich niet aan te melden bij het apparaat om PowerShell-scripts uit te voeren.

- De Intune-beheeruitbreidingsclient neemt één keer per uur contact op met Intune en na elke keer dat er opnieuw is opgestart. Dit gebeurt om te controleren op nieuwe scripts en wijzigingen. Wanneer u het beleid aan de Microsoft Azure Active Directory-groepen toewijst, wordt het PowerShell-script uitgevoerd en worden de resultaten van de uitvoering gerapporteerd. Zodra het script wordt uitgevoerd, wordt deze pas weer opnieuw uitgevoerd als het script of het beleid is gewijzigd.

## <a name="monitor-run-status"></a>Uitvoeringsstatus bewaken

U kunt de uitvoeringsstatus van PowerShell-scripts voor gebruikers en apparaten in Azure Portal controleren.

Selecteer in **PowerShell-scripts** het script dat u wilt controleren, kies **Controleren** en kies vervolgens een van de volgende rapporten:

- **Apparaatstatus**
- **Gebruikersstatus**

## <a name="intune-management-extension-logs"></a>Intune-beheeruitbreidingslogboeken

Agentlogboeken op de clientcomputer staan meestal in `\ProgramData\Microsoft\IntuneManagementExtension\Logs`. U kunt [CMTrace.exe](https://docs.microsoft.com/sccm/core/support/tools) gebruiken om deze logboekbestanden te bekijken. 

![Schermopname of voorbeeldlogboeken van de cmtrace-agent in Microsoft Intune](./media/apps-win32-app-management/apps-win32-app-10.png)  

## <a name="delete-a-script"></a>Een script verwijderen

Klik in **PowerShell-scripts** met de rechtermuisknop op het script en selecteer **Verwijderen**.

## <a name="common-issues-and-resolutions"></a>Veelvoorkomende problemen en oplossingen

### <a name="issue-intune-management-extension-doesnt-download"></a>Probleem: Intune-beheeruitbreiding wordt niet gedownload

**Mogelijke oplossingen**:

- Het apparaat niet is gekoppeld aan Azure AD. Zorg ervoor dat de apparaten voldoen aan de [vereisten](#prerequisites) (uit dit artikel). 
- Er zijn geen PowerShell-scripts of Win32-apps toegewezen aan de groepen waar de gebruiker of het apparaat onderdeel van is.
- Het apparaat kan niet inchecken bij de Intune-service omdat er geen toegang tot internet, geen toegang tot Windows Push Notification Services (WNS) en meer is.
- Het apparaat bevindt zich niet in de S-modus. De Intune-beheeruitbreiding wordt niet ondersteund op apparaten die worden uitgevoerd in de S-modus. 

Als u wilt zien of het apparaat automatisch wordt ingeschreven, kunt u het volgende doen:

  1. Ga naar **Instellingen** > **Accounts** > **Toegang tot werk of school**.
  2. Selecteer het deelnemende account > **Info**.
  3. Selecteer onder **Geavanceerde diagnostische gegevens** de optie **Rapport maken**.
  4. Open de `MDMDiagReport` in een webbrowser.
  5. Zoek de eigenschap **MDMDeviceWithAAD**. Als de eigenschap bestaat, wordt het apparaat automatisch ingeschreven. Als deze eigenschap niet bestaat, wordt het apparaat niet automatisch ingeschreven.

[Automatische inschrijving voor Windows 10 inschakelen](../enrollment/windows-enroll.md#enable-windows-10-automatic-enrollment) bevat de stappen voor het configureren van automatische inschrijving in Intune.

### <a name="issue-powershell-scripts-do-not-run"></a>Probleem: De PowerShell-scripts worden niet uitgevoerd

**Mogelijke oplossingen**:

- De PowerShell-scripts worden niet bij elke aanmelding uitgevoerd. Ze worden uitgevoerd:

  - Wanneer het script wordt toegewezen aan een apparaat
  - Als u het script wijzigt, uploadt u het en wijst u het toe aan een gebruiker of apparaat
  
    > [!TIP]
    > De **Microsoft Intune-beheeruitbreiding** is een service die wordt uitgevoerd op het apparaat, net als andere services die in de app Services worden vermeld (services.msc). Nadat een apparaat opnieuw is opgestart, wordt deze service mogelijk ook opnieuw opgestart. Er wordt dan gecontroleerd op aan de Intune-service toegewezen PowerShell-scripts. Als de **Microsoft Intune-beheeruitbreiding** is ingesteld op Handmatig, wordt de service mogelijk niet opnieuw opgestart wanneer het apparaat opnieuw wordt opgestart.

- Zorg ervoor dat apparaten zijn [gekoppeld aan Azure AD](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network). Apparaten die alleen zijn toegevoegd aan uw werkplek of organisatie ([geregistreerd](https://docs.microsoft.com/azure/active-directory/user-help/user-help-register-device-on-network) in Azure AD) ontvangt uw scripts niet.
- De client met de Intune-beheeruitbreiding controleert eenmaal per uur op wijzigingen in het script of het beleid in Intune.
- Controleer of de Intune-beheeruitbreiding is gedownload naar `%ProgramFiles(x86)%\Microsoft Intune Management Extension`.
- Scripts worden in de S-modus niet uitgevoerd op Surface Hubs en in Windows 10.
- Controleer de logboeken op fouten. Raadpleeg [Intune-beheeruitbreidingslogboeken](#intune-management-extension-logs) (in dit artikel).
- Als u wilt weten of er problemen zijn met machtigingen, controleert u of de eigenschappen van het PowerShell-script zijn ingesteld op `Run this script using the logged on credentials`. Controleer ook of de aangemelde gebruiker de juiste machtigingen heeft om het script uit te voeren.

- Om scriptproblemen te isoleren, kunt u:

  - Controleer de configuratie van PowerShell-uitvoering op uw apparaten. Zie het [PowerShell-uitvoeringsbeleid](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy?view=powershell-6) voor hulp.
  - Voer een voorbeeldscript uit via de Intune-beheeruitbreiding. Maak bijvoorbeeld een map `C:\Scripts` en geef iedereen volledig beheer voor die map. Voer het volgende script uit:

    ```powershell
    write-output "Script worked" | out-file c:\Scripts\output.txt
    ```

    Als dat lukt, moet output.txt worden gemaakt dat de tekst 'Script worked' bevat.

  - Als u de uitvoering van het script wilt testen zonder Intune, voert u de scripts lokaal in het systeemaccount uit met behulp van het hulpprogramma [psexec](https://docs.microsoft.com/sysinternals/downloads/psexec):

    `psexec -i -s`  
    
  - Als het script rapporteert dat het is geslaagd, maar het niet geslaagd is, is het mogelijk dat uw antivirusservice AgentExecutor in een sandbox plaatst. Het volgende script meldt altijd een fout in Intune. Als test kunt u dit script gebruiken:
  
    ```powershell
    Write-Error -Message "Forced Fail" -Category OperationStopped
    mkdir "c:\temp" 
    echo "Forced Fail" | out-file c:\temp\Fail.txt
    ```

    Als het script een succes rapporteert, raadpleegt u `AgentExecutor.log` om de uitvoer van de fout te bekijken. Als het script wordt uitgevoerd, moet de lengte >2 zijn.

  - Als u de .ERROR- en .OUTPUT-bestanden wilt vastleggen, kunt u met het volgende codefragment het script via AgentExecutor uitvoeren naar PSx86 (`C:\Windows\SysWOW64\WindowsPowerShell\v1.0`). De logboeken worden dan bewaard, zodat u deze kunt bekijken. Houd er rekening mee dat de Intune Management Extension de logboeken opschoont nadat het script is uitgevoerd:
  
    ```powershell
    $scriptPath = read-host "Enter the path to the script file to execute"
    $logFolder = read-host "Enter the path to a folder to output the logs to"
    $outputPath = $logFolder+"\output.output"
    $errorPath =  $logFolder+"\error.error"
    $timeoutPath =  $logFolder+"\timeout.timeout"
    $timeoutVal = 60000 
    $PSFolder = "C:\Windows\SysWOW64\WindowsPowerShell\v1.0"
    $AgentExec = "C:\Program Files (x86)\Microsoft Intune Management Extension\agentexecutor.exe"
    &$AgentExec -powershell  $scriptPath $outputPath $errorPath $timeoutPath $timeoutVal $PSFolder 0 0
    ```

## <a name="next-steps"></a>Volgende stappen

Uw profielen [bewaken](../device-profile-monitor.md) en [profielproblemen oplossen](../device-profile-troubleshoot.md).
