---
title: Versleutelingsrapport voor versleutelde apparaten in Microsoft Intune
titleSuffix: Microsoft Intune
description: Bekijk een rapport over de versleutelingsstatus van iOS- of Windows-apparaat en krijg toegang tot FileVault- en BitLocker-herstelsleutels via de Microsoft Intune-portal.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 08/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: shpate
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 469bdc54385f943fd0c42ccfd921293970b03b64
ms.sourcegitcommit: 05139901411d14a85c2340c0ebae02d2c178a851
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/11/2019
ms.locfileid: "70905043"
---
# <a name="monitor-device-encryption-with-intune"></a>Apparaatversleuteling bewaken met Intune   

Het Microsoft Intune-versleutelingsrapport is een centrale locatie om informatie over de versleutelingsstatus van een apparaat te bekijken en voor opties om herstelsleutels voor apparaten te beheren. Welke opties er voor herstelsleutels beschikbaar zijn, is afhankelijk van het type apparaat dat u bekijkt.  

Voor het rapport meldt u zich aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973). Ga naar **Apparaatconfiguratie** en selecteer vervolgens bij *Monitor* de optie **Versleutelingsrapport**.  

## <a name="view-encryption-details"></a>Versleutelingsgegevens weergeven  

Het versleutelingsrapport bevat algemene informatie over de ondersteunde apparaten die u beheert. In de volgende secties leest u meer over de informatie die Intune in het rapport verwerkt.  
 
### <a name="prerequisites"></a>Vereisten:  

Het versleutelingsrapport kan worden gemaakt op apparaten met een van de volgende besturingssysteemversies:  
- macOS 10.13 of hoger  
- Windows-versie 1607 of hoger  

### <a name="report-details"></a>Rapportdetails  

In het deelvenster Versleutelingsrapport ziet u een lijst met de apparaten die u beheert, met (op hoog niveau) details over die apparaten. U kunt een apparaat in de lijst selecteren om in te zoomen op aanvullende details over dat apparaat. Deze staan in het deelvenster [Status van apparaatversleuteling](#device-encryption-status).  

- **Apparaatnaam**: de naam van het apparaat.  
- **Besturingssysteem**: het apparaatplatform, zoals Windows of macOS.  
- **Besturingssysteemversie**: de versie van Windows of macOS op het apparaat.  
- **TPM-versie** *(alleen van toepassing bij Windows 10)* : de versie van de TPM-chip (Trusted Platform Module) op het Windows 10-apparaat.  
- **Gereedheid voor versleuteling**: een evaluatie van de gereedheid van apparaten om een gebruikte versleutelingstechnologie te ondersteunen, zoals de BitLocker- of FileVault-versleuteling. Apparaten kunnen worden geïdentificeerd als:  
  - **Gereed**: het apparaat kan met behulp van MDM-beleid worden versleuteld. Hiervoor moet het apparaat aan de volgende vereisten voldoen:  
    
    **Voor macOS-apparaten**:  
    - macOS-versie 10.13 of hoger  
    
    **Voor Windows 10-apparaten**:  
    - versie 1703 of hoger van *Business*, *Enterprise* of *Education*, of versie 1809 van *Pro*  
    - Het apparaat moet beschikken over een TPM-chip  
    
    Zie de [BitLocker CSP (configuratieserviceprovider)](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) in de Windows-documentatie voor meer informatie.  

  - **Niet gereed**: Het apparaat beschikt niet over alle versleutelingsmogelijkheden, maar kan nog wel worden versleuteld. Het Windows-apparaat kan bijvoorbeeld handmatig door een gebruiker worden versleuteld of door een groepsbeleid dat zodanig kan worden ingesteld dat versleuteling mogelijk is zonder een TPM.
  - **Niet van toepassing**: er is onvoldoende informatie beschikbaar om dit apparaat te classificeren.  

- **Versleutelingsstatus**: deze optie geeft aan of de besturingssysteemschijf is versleuteld.  

- **Principalnaam naam van gebruiker**: de primaire gebruiker van het apparaat.  

### <a name="device-encryption-status"></a>Status apparaatversleuteling  

Wanneer u een apparaat selecteert in het versleutelingsrapport, wordt in Intune het deelvenster **Status apparaatversleuteling** weergegeven. In dit deelvenster worden de volgende details weergegeven:  

- **Apparaatnaam**: de naam van het apparaat dat wordt weergegeven.  

- **Gereedheid voor versleuteling**: met deze functie controleert u of de apparaten gereed zijn om versleuteling te ondersteunen op basis van het MDM-beleid.  
  
  Bijvoorbeeld: Als een Windows 10-apparaat de status *Niet gereed* heeft, kan het zijn dat het apparaat toch ondersteuning biedt voor versleuteling. De status *Gereed* wordt weergegeven als het Windows 10-apparaat beschikt over een TPM-chip. Er zijn geen TPM-chips vereist voor het ondersteunen van versleuteling. (Raadpleeg *Gereedheid voor versleuteling* voor meer informatie)  

- **Versleutelingsstatus**: deze optie geeft aan of de besturingssysteemschijf is versleuteld. Het kan tot 24 uur duren voordat Intune de versleutelingsstatus van apparaten of een wijziging in deze status rapporteert. Deze tijd omvat de tijd om het besturingssysteem te versleutelen en de tijd die het apparaat nodig heeft om te rapporteren bij Intune.  

  Als u de rapportage van de FileVault-versleutelingsstatus wilt versnellen voordat het apparaat normaal incheckt, moeten gebruikers hun apparaten synchroniseren nadat de versleuteling is voltooid.  

- **Profielen**: een lijst met de profielen voor *apparaatconfiguratie* die op dit apparaat van toepassing zijn en die met de volgende waarden zijn geconfigureerd:  

  - macOS:
    - Profieltype = *Endpoint Protection*  
    - Instellingen > FileVault > FileVault = *Inschakelen*

  - Windows 10:
    - Profieltype = *Endpoint Protection*  
    - Instellingen > Windows-versleuteling > Apparaten versleutelen = *Vereisen*  

  U kunt de lijst profielen gebruiken om afzonderlijke beleidsregels te zoeken om te beoordelen, als in de *samenvatting van de profielstatus* problemen worden aangeduid.  

- **Samenvatting van de profielstatus**: een samenvatting van de profielen die op dit apparaat van toepassing zijn. De samenvatting staat voor de minst gunstige voorwaarde voor alle profielen die van toepassing zijn. Als één van meerdere van toepassing zijnde profielen bijvoorbeeld leidt tot een fout, wordt in de *samenvatting van de profielstatus* *Fout* weergegeven.  
  
  Voor meer informatie over een status gaat u naar **Intune** > **Apparaatconfiguratie** > **Profielen** en selecteert u het profiel. U kunt ook naar **Apparaatstatus** gaan en een apparaat selecteren.  

- **Statusdetails**: geavanceerde details over de versleutelingsstatus van het apparaat.  

  > [!IMPORTANT]  
  > Op Windows 10-apparaten toont Intune alleen de *statusdetails* voor apparaten waarop de *Windows 10-update van april 2019* of hoger wordt uitgevoerd.  
  
  In dit veld staat informatie voor elke toepasselijke fout die kan worden gedetecteerd. Aan de hand van deze informatie kunt u achterhalen waarom een apparaat mogelijk niet gereed is voor versleuteling.  

  Hieronder volgt een aantal voorbeelden van de statusdetails die in een Intune-rapport kunnen staan:  
  
  **macOS**:
  - De herstelsleutel is nog niet opgehaald en opgeslagen. Waarschijnlijk is het apparaat niet ontgrendeld of is het niet ingecheckt.  
 
    *Overweeg het volgende: dit resultaat betekent niet per se dat er sprake is van een fout, maar juist dat er een tijdelijke status is. Deze status kan het gevolg zijn van timing op het apparaat: de escrow voor herstelsleutels moet worden ingesteld voordat de versleutelingsaanvraag naar het apparaat wordt verzonden. Deze status kan ook aangeven dat het apparaat vergrendeld blijft of niet recent heeft ingecheckt bij Intune. Daarnaast is het, omdat de FileVault-versleuteling pas begint wanneer een apparaat is ingestoken (wordt opgeladen), mogelijk dat een gebruiker een herstelsleutel ontvangt voor een apparaat dat nog niet is versleuteld*.  

  - De gebruiker stelt versleuteling uit of is momenteel bezig met versleuteling.  
 
    *Overweeg het volgende: de gebruiker heeft zich nog niet afgemeld na het ontvangen van de versleutelingsaanvraag; dit moet wel gebeuren, want anders kan FileVault het apparaat niet versleutelen. Het kan ook zijn dat de gebruiker het apparaat handmatig heeft ontsleuteld. Intune kan niet voorkomen dat een gebruiker zijn of haar apparaat ontsleutelt.*  

  - Het apparaat is al versleuteld. De gebruiker van het apparaat moet het apparaat ontsleutelen om door te gaan.  
 
    *Overweeg het volgende: Intune kan FileVault niet instellen op een apparaat dat al is versleuteld. In een dergelijk geval moet de gebruiker het apparaat handmatig ontsleutelen; daarna kan het pas worden beheerd met een apparaatconfiguratiebeleid en Intune*. 
 
  - FileVault vereist dat de gebruiker het beheer goedkeurt als er gebruik wordt gemaakt van macOS Catalina of hoger.  
 
    *Overweeg het volgende: vanaf macOS-versie 10.15 (Catalina) kan het gebruik van door de gebruiker goedgekeurde inschrijvingsinstellingen ertoe leiden dat gebruikers de FileVault-versleuteling handmatig moeten goedkeuren. Zie [Door gebruiker goedgekeurde registratie](macos-enroll.md) in de Intune-documentatie voor meer informatie*.  

  - Onbekend.  

    *Overweeg het volgende: een mogelijke oorzaak van een onbekende status is dat het apparaat is vergrendeld en dat het escrow- of versleutelingsproces niet kan worden gestart door Intune. Zodra het apparaat is ontgrendeld, kan het proces worden voortgezet*.  

  **Windows 10**:  
  - Volgens het BitLocker-beleid moeten gebruikers toestemming geven om de wizard BitLocker-stationsversleuteling te starten om het besturingssysteemvolume te versleutelen, maar de gebruiker heeft geen toestemming gegeven.  
  
  - De versleutelingsmethode van het besturingssysteemvolume komt niet overeen met het BitLocker-beleid.  
  
  - Volgens het BitLocker-beleid moet TPM-beveiliging worden gebruikt om het besturingssysteemvolume te beveiligen, maar er is geen TPM gebruikt.  
  
  - Volgens het BitLocker-beleid moet alleen TPM-beveiliging worden gebruikt om het besturingssysteemvolume te beveiligen, maar er is geen TPM-beveiliging gebruikt.  
  
  - Volgens het BitLocker-beleid moet TPM- en pincodebeveiliging worden gebruikt om het besturingssysteemvolume te beveiligen, maar er is geen TPM- en pincodebeveiliging gebruikt.  
  
  - Volgens het BitLocker-beleid moet TPM- en opstartsleutelbeveiliging worden gebruikt om het besturingssysteemvolume te beveiligen, maar er is geen TPM- en opstartsleutelbeveiliging gebruikt.  
  
  - Volgens het BitLocker-beleid moet TPM-, pincode- en opstartsleutelbeveiliging worden gebruikt om het besturingssysteemvolume te beveiligen, maar er is geen TPM-, pincode- en opstartsleutelbeveiliging gebruikt.  
  
  - Het besturingssysteemvolume is niet beveiligd.  
  
  - Back-up van herstelsleutel is mislukt.  
  
  - Een vaste schijf is niet beveiligd.  
  
  - De versleutelingsmethode van de vaste schijf komt niet overeen met het BitLocker-beleid.  
  
  - Als u schijven wilt versleutelen, moeten gebruikers zich volgens het BitLocker-beleid aanmelden als beheerder, of het AllowStandardUserEncryption-beleid moet zijn ingesteld op 1 als het apparaat met Azure AD wordt samengevoegd.  
  
  - Windows Recovery Environment (WinRE) is niet geconfigureerd.  
  
  - Er is geen TPM beschikbaar voor BitLocker. Dit komt omdat er geen TPM aanwezig is, er geen TPM in het register staat of het besturingssysteem zich op een verwisselbaar station bevindt.  
  
  - De TPM is niet gereed voor BitLocker.  
  
  - Het netwerk is niet beschikbaar, maar wel vereist voor back-ups van herstelsleutels.  

## <a name="export-report-details"></a>Rapportdetails exporteren 
Tijdens het weergeven van het deelvenster Versleutelingsrapport kunt u **Exporteren** selecteren om een *CSV*-bestand met de rapportgegevens te maken en te downloaden.  Het rapport bevat op hoog niveau gegevens uit het deelvenster *Versleutelingsrapport* en de gegevens over de *apparaatversleutelingsstatus* van de apparaten die u beheert.   
 
  
![Details exporteren](./media/encryption-monitor/export.png) 
 
Dit rapport kan worden gebruikt bij het identificeren van problemen voor groepen apparaten. U kunt het rapport bijvoorbeeld gebruiken om een lijst macOS-apparaten te maken waarvoor staat geregistreerd dat *FileVault al is ingeschakeld door de gebruiker*; dit geeft aan dat de apparaten handmatig moeten worden ontsleuteld voordat Intune de FileVault-instellingen kan beheren.  
 
## <a name="filevault-recovery-keys"></a>FileVault-herstelsleutels   
Wanneer Intune een macOS-apparaat voor het eerst versleutelt met FileVault, wordt er een persoonlijke herstelsleutel gemaakt. Na het versleutelen wordt de persoonlijke sleutel één keer weergegeven aan de eindgebruiker.  
 
Bij beheerde apparaten kan Intune een escrow-sleutel maken van de persoonlijke herstelsleutel. Met escrow-sleutels kunnen Intune-beheerders sleutels vernieuwen om de bescherming van apparaten te verbeteren en kunnen gebruikers verloren geraakte of vernieuwde persoonlijke herstelsleutels herstellen.  
 
Intune biedt ondersteuning voor meerdere opties voor het vernieuwen en herstellen van persoonlijke herstelsleutels. Persoonlijke herstelsleutels kunnen bijvoorbeeld worden vernieuwd als de huidige persoonlijke herstelsleutel verloren is geraakt of er sprake is van een risico.  
 
> [!IMPORTANT]  
>  Apparaten die door gebruikers zijn versleuteld (en niet door Intune), kunnen niet door Intune worden beheerd. Dit betekent dat Intune geen escrow-sleutel kan maken voor het persoonlijke herstel van de apparaten en dat de vernieuwing van de herstelsleutel niet kan worden beheerd.  Voordat Intune kan worden gebruikt voor het beheer van FileVault en herstelsleutels voor het apparaat, moet de gebruiker het apparaat ontsleutelen. Daarna kan het apparaat met Intune worden versleuteld.  

### <a name="rotate-recovery-keys"></a>Herstelsleutels wijzigen  

- **Automatisch wijzigen**: Als beheerder kunt u de FileVault-instelling voor het wijzigen van persoonlijke herstelsleutels zodanig configureren dat er automatisch periodiek nieuwe herstelsleutels worden gegenereerd.  Wanneer er een nieuwe sleutel wordt gegenereerd voor een apparaat, wordt de sleutel niet weergegeven aan de gebruiker. In plaats daarvan moet de gebruiker de sleutel ophalen bij een beheerder, of de app Bedrijfsportal gebruiken.  

- **Handmatig wijzigen**: u kunt als beheerder informatie bekijken over apparaten die u met Intune beheert en die met FileVault zijn versleuteld. U kunt ervoor kiezen om de herstelsleutels voor zakelijke apparaten handmatig te vernieuwen. Het is niet mogelijk om de herstelsleutels voor persoonlijke apparaten te vernieuwen.  

  Een herstelsleutel vernieuwen: 
  1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973), ga naar  **Apparaten** en klik dan onder Beheren op  **Alle apparaten**.  
  2. Selecteer in de lijst met apparaten het apparaat dat is versleuteld en waarvoor u de sleutel wilt vernieuwen. Selecteer vervolgens onder Bewaken de optie  **Herstelsleutels**.  
  3. In het deelvenster Herstelsleutels selecteert u **FileVault-herstelsleutel vernieuwen**.  
  
     De volgende keer dat het apparaat incheckt bij Intune, wordt de persoonlijke sleutel vernieuwd. Indien nodig kan de nieuwe sleutel door de eindgebruiker worden verkregen via de bedrijfsportal. 


### <a name="recover-recovery-keys"></a>Herstelsleutels herstellen  
- **Beheerder**: beheerders kunnen de persoonlijke herstelsleutels voor apparaten die zijn versleuteld met FileVault niet bekijken.  

- **Eindgebruiker**: eindgebruikers gebruiken de bedrijfsportalwebsite vanaf een apparaat om hun huidige persoonlijke herstelsleutel te gebruiken voor een van hun beheerde apparaten. Het is niet mogelijk om herstelsleutels te bekijken vanuit de app Bedrijfsportal.  

 
  Een herstelsleutel weergeven:  
  1. Meld u op een apparaat aan bij de *Intune-bedrijfsportal*website.  
  2. Ga in de portal naar **Apparaten** en selecteer het macOS-apparaat dat is versleuteld met FileVault.  
  3. Selecteer **Herstelsleutel ophalen**. De huidige herstelsleutel wordt weergegeven.  
 

## <a name="bitlocker-recovery-keys"></a>BitLocker-herstelsleutels  

Intune biedt toegang tot de Microsoft Azure Active Directory-blade voor BitLocker, zodat u via de Intune-portal BitLocker-sleutel-id's en herstelsleutels voor uw Windows 10-apparaten kunt weergeven.  Een apparaat is alleen toegankelijk als de sleutels van dat apparaat naar Azure AD worden geborgd. 
1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973), ga naar **Apparaten** en selecteer onder *Beheren* de optie **Alle apparaten**.  

2. Selecteer een apparaat in de lijst en selecteer vervolgens onder *Monitor* **Herstelsleutels**.  
  
Als er sleutels in Azure AD beschikbaar zijn, is de volgende informatie beschikbaar:
- BitLocker-sleutel-id  
- BitLocker-herstelsleutel  
- Type station  

Als er geen sleutels aanwezig zijn in Azure AD, wordt *Er is geen BitLocker-sleutel gevonden voor dit apparaat* weergegeven.  

De informatie voor BitLocker wordt verkregen met behulp van de [BitLocker-configuratieserviceprovider](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) (CSP). BitLocker CSP wordt ondersteund op Windows 10-versie 1703 en hoger en voor Windows 10 Pro-versie 1809 en hoger.  

## <a name="next-steps"></a>Volgende stappen  

Een [nalevingsbeleid voor apparaten](compliance-policy-create-windows.md) maken.
