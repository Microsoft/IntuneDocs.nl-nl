---
title: Instellingen van Windows Update voor Bedrijven voor Microsoft Intune - Azure | Microsoft Docs
description: WUfB-instellingen voor Windows 10-apparaten die u kunt implementeren met behulp van Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/16/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 98c3425c58b6039c8a1c3b5750f9473c74a78634
ms.sourcegitcommit: 93de3423d2d8f0019e676a63784edeb3daf47cb7
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/16/2019
ms.locfileid: "56325466"
---
# <a name="windows-update-settings-for-intune"></a>Windows Update-instellingen voor Intune  

Bekijk de Windows 10 Update-instellingen die u kunt [configureren en beheren](windows-update-for-business-configure.md) met Microsoft Intune.  

Wanneer u instellingen voor Windows 10-update-ringen in Intune configureert, configureert u de instellingen voor Windows Update.  Wanneer een Windows Update-instelling afhankelijk is van een Windows 10-versie, wordt de versieafhankelijkheid vermeld in de instellingsdetails.  

## <a name="update-settings"></a>Update-instellingen  

Update-instellingen bepalen welke bits een apparaat downloadt, en wanneer. Raadpleeg de Windows-documentatie voor meer informatie over het gedrag van elke instelling.  

### <a name="servicing-channel"></a>Servicekanaal  

- **Standaardinstelling**: Semi-Annual-kanaal (Targeted)  
- **Windows-referentiedocumentatie**: [Update/BranchReadinessLevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-branchreadinesslevel)  
Stel het kanaal (branch) in van waaruit het apparaat Windows-updates ontvangt. Verschillende kanalen kunnen verschillende uitstelperioden gebruiken voordat updates worden geleverd.  

Zo heeft het *Semi-Annual-kanaal* een uitstel van zes maanden. Dit betekent dat als u dit kanaal gebruikt zonder extra uitstel in deze groep instellingen, het apparaat de update zes maanden na de release installeert.  

Ondersteunde updatekanalen:  

- Semi-Annual-kanaal  
- Semi-Annual-kanaal (targeted)  
- Windows Insider – Fast  
- Windows Insider – Slow  
- Windows Insider vrijgeven  

Als u een insider-kanaal selecteert, configureert Intune automatisch de Windows-update-instelling [Update/ManagePreviewBuilds](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-managepreviewbuilds), zodat de insider-build werkt.  


> [!IMPORTANT]  
> Vanaf Windows-versie 1903 wordt het gebruik van het *Semi-Annual-kanaal (targeted)* (SAC-T) stopgezet. Met deze wijziging wordt SAC-T samengevoegd met het *Semi-Annual-kanaal*. Zie voor meer informatie over deze wijziging en hoe dit van invloed is op Windows Update voor Bedrijven, het bericht [Windows Update for Business and the retirement of SAC-T](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/Windows-Update-for-Business-and-the-retirement-of-SAC-T/ba-p/339523) in het Windows IT Pro Blog.
 


### <a name="microsoft-product-updates"></a>Microsoft-productupdates  

- **Standaardinstelling**:  Toestaan
- **Windows-referentiedocumentatie**: [Update/AllowMUUpdateService](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-allowmuupdateservice)

Kies *Toestaan* om naar app-updates te zoeken via Microsoft Update.    

### <a name="windows-drivers"></a>Windows-stuurprogramma's  

- **Standaardinstelling**:  Toestaan
- **Windows-referentiedocumentatie**: [Update/ExcludeWUDriversInQualityUpdate](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-excludewudriversinqualityupdate)

Kies *Toestaan* als u Windows Update-stuurprogramma's ook wilt laten bijwerken

### <a name="quality-update-deferral-period-days"></a>Uitstelperiode voor kwaliteitsupdates (dagen)  

- **Standaardinstelling**: 0  
- **Windows-referentiedocumentatie**: [Update/DeferQualityUpdatesPeriodInDays](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-deferqualityupdatesperiodindays)  

Geef het aantal dagen (0 tot 30) op dat kwaliteitsupdates worden uitgesteld. Deze periode wordt opgeteld bij de eventuele uitstelperiode van het servicekanaal dat u selecteert. De uitstelperiode begint wanneer het beleid wordt ontvangen door het apparaat.  

Kwaliteitsupdates zijn doorgaans oplossingen en verbeteringen in de bestaande Windows-functionaliteit.  

### <a name="feature-update-deferral-period-days"></a>Uitstelperiode voor onderdelenupdates (dagen)  

- **Standaardinstelling**: 0  
- **Windows-referentiedocumentatie**: [Update/PauseFeatureUpdatesPeriodInDays](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-deferfeatureupdatesperiodindays)  

Geef het aantal dagen op dat onderdelenupdates worden uitgesteld. Deze periode wordt opgeteld bij de eventuele uitstelperiode van het servicekanaal dat u selecteert. De uitstelperiode begint wanneer het beleid wordt ontvangen door het apparaat.  
Ondersteunde uitstelperiode:  

- *Windows-versie 1709 of hoger*: 0 tot 365 dagen  
- *Windows-versie 1703*:  0 tot 180 dagen  

Upgrades van onderdelen zijn over het algemeen nieuwe functies van Windows.  

### <a name="set-feature-update-uninstall-period-2--60-days"></a>Periode instellen voor onderdelenupdate verwijderen (2-60 dagen)  

- **Standaardinstelling**: 10  
- **Windows-referentiedocumentatie**:  [Update/ConfigureFeatureUpdateUninstallPeriod](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-configurefeatureupdateuninstallperiod)  

Configureer een tijd waarna onderdelenupdates niet meer kunnen worden verwijderd.  

Nadat deze periode is verlopen, worden de bits van de vorige update van het apparaat verwijderd en kan de installatie niet ongedaan worden gemaakt naar een vorige updateversie.  

Neem bijvoorbeeld een update-ring met een verwijderingsperiode voor onderdelenupdates van 20 dagen. Na 25 dagen besluit u de laatste onderdelenupdate terug te draaien, en gebruikt u de optie Verwijderen.  Op apparaten waarop de functie-update meer dan 20 dagen geleden is geïnstalleerd, is verwijderen niet mogelijk, omdat de vereiste bits als onderdeel van het onderhoud zijn verwijderd. Op apparaten waar de onderdelenupdate nog maar 19 dagen geleden is geïnstalleerd, kan de update wel worden verwijderd, als ze zich aanmelden om de verwijderopdracht te ontvangen voordat de verwijderingsperiode van 20 dagen is verstreken.  


## <a name="user-experience-settings"></a>Instellingen voor gebruikerservaring  

De instellingen voor de gebruikerservaring bepalen de ervaring van de eindgebruiker wat betreft het opnieuw opstarten van het apparaat en ontvangen herinneringen. Raadpleeg de Windows-documentatie voor meer informatie over het gedrag van elke instelling.  

### <a name="automatic-update-behavior"></a>Gedrag van automatische updates  

- **Standaardinstelling**: Automatisch installeren en opnieuw opstarten op een gepland tijdstip  
- **Windows-referentiedocumentatie**: [Update/AllowAutoUpdate](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)  

Kies hoe automatische updates worden geïnstalleerd, en wanneer het apparaat indien nodig opnieuw moet worden opgestart.  

Raadpleeg de naslagdocumentatie van Windows voor een volledige uitleg van de volgende ondersteunde opties:  

- **Download melden** – de gebruiker waarschuwen voordat de update wordt gedownload. Gebruikers kiezen wanneer ze updates willen downloaden en installeren.  

- **Automatisch installeren op het tijdstip voor onderhoud** – Updates worden automatisch gedownload en vervolgens geïnstalleerd tijdens Automatisch onderhoud wanneer het apparaat niet in gebruik is of op accustroom werkt. Wanneer opnieuw opstarten nodig is, wordt gebruikers zeven dagen gevraagd opnieuw op te starten, en vervolgens wordt opnieuw opstarten geforceerd.  

  Deze optie kan een apparaat automatisch opnieuw opstarten nadat de update is geïnstalleerd. Gebruik de instelling **Gebruikstijden** om een periode te definiëren waarin automatisch opnieuw opstarten wordt geblokkeerd:  

  - **Start gebruikstijd**: Geef een begintijd op voor het onderdrukken van opnieuw opstarten vanwege update-installaties.  
    **Windows-referentiedocumentatie**:  [Update/ActiveHoursStart](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-activehoursstart)  
    **Standaardinstelling**: 08:00 uur  
  
  - **Einde gebruikstijd**: Geef een eindtijd op voor het onderdrukken van opnieuw opstarten vanwege update-installaties.  
    **Windows-referentiedocumentatie**:  [Update/ActiveHoursEnd](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-activehoursend)  
    **Standaardinstelling**: 17:00 uur  

- **Automatisch installeren en opnieuw starten op het tijdstip voor onderhoud** – Updates worden automatisch gedownload en vervolgens geïnstalleerd tijdens Automatisch onderhoud wanneer het apparaat niet in gebruik is of op accustroom werkt. Als opnieuw opstarten vereist is, wordt het apparaat opnieuw opgestart wanneer het niet wordt gebruikt. (Dit is de standaardinstelling voor niet-beheerde apparaten.)  

  Deze optie kan een apparaat automatisch opnieuw opstarten nadat de update is geïnstalleerd. Het gebruik van de instelling **Gebruikstijden** wordt niet beschreven in de instellingen van Windows Update, maar worden gebruikt door Intune om een periode te definiëren waarin automatisch opnieuw opstarten wordt geblokkeerd:  

  - **Start gebruikstijd**: Geef een begintijd op voor het onderdrukken van opnieuw opstarten vanwege update-installaties.  
    **Windows-referentiedocumentatie**:  [Update/ActiveHoursStart](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-activehoursstart)  
    **Standaardinstelling**: 08:00 uur  

  - **Einde gebruikstijd**: Geef een eindtijd op voor het onderdrukken van opnieuw opstarten vanwege update-installaties.  
    **Windows-referentiedocumentatie**:  [Update/ActiveHoursEnd](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-activehoursend)  
    **Standaardinstelling**: 17:00 uur  

- **Automatisch installeren en opnieuw starten op het geplande tijdstip** – Geef een installatiedag en -tijd op. Als er niets wordt opgegeven, wordt de installatie dagelijks om 03:00 uur uitgevoerd, gevolgd door een aftelling van 15 minuten naar een herstart. Aangemelde gebruikers kunnen het aftellen en opnieuw opstarten uitstellen.  
  
  Deze optie ondersteunt extra instellingen.  
  **Windows-referentiedocumentatie**:  [Update/AllowAutoUpdate](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)  

  - **Frequentie van automatisch gedrag**: Gebruik deze instelling om te plannen wanneer updates worden geïnstalleerd, inclusief de week, de dag en het tijdstip.  
    **Standaardinstelling**: Elke week

  - **Geplande installatiedag**:  Geef op welke dag van de week updates moeten worden geïnstalleerd.  
    **Standaardinstelling**: Elke dag  

  - **Geplande installatietijd**:  Geef de tijd van de dag op waarop updates moeten worden geïnstalleerd.  
    **Standaardinstelling**: 03:00 uur  

- **Automatisch installeren en opnieuw opstarten zonder tussenkomst van de eindgebruiker** – Updates worden automatisch gedownload en vervolgens geïnstalleerd tijdens Automatisch onderhoud wanneer het apparaat niet in gebruik is of op accustroom werkt. Als opnieuw opstarten vereist is, wordt het apparaat opnieuw opgestart wanneer het niet wordt gebruikt. Deze optie stelt het configuratiescherm van de eindgebruiker in op alleen-lezen.  

- Met de instelling **Standaardinstellingen herstellen** herstelt u de oorspronkelijke instellingen voor automatisch bijwerken op Windows 10-computers met de update van oktober 2018 of later.  


### <a name="restart-checks"></a>Controles voor opnieuw starten  

- **Standaardinstelling**: Toestaan  
- **Windows-referentiedocumentatie**: [Update/SetEDURestart](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-setedurestart)  

Deze instelling heeft verschillende resultaten, afhankelijk van de Windows-versie van het apparaat:  

- Windows-versie 1703 en lager: Wanneer u een apparaat opnieuw start, worden er een aantal controles uitgevoerd. Zo wordt bijvoorbeeld gecontroleerd op actieve gebruikers, batterijniveau, actieve games en meer. Als u deze controles wilt overslaan wanneer u een apparaat opnieuw start, kiest u **Overslaan**.  
- Vanaf Windows-versie 1709: Tijdens de gebruikstijd worden de volgende processen niet uitgevoerd voor updates: scannen, downloaden, installeren en opnieuw opstarten. Na de gebruikstijd worden de updateprocessen wel uitgevoerd en kunnen ze het apparaat uit de slaapstand halen, scannen, downloaden, installeren en opnieuw opstarten, zolang het door de accu- en stroomcontrole komt. Zie [Update/SetEDURestart](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-setedurestart) voor meer informatie.  

### <a name="block-user-from-pausing-windows-updates"></a>Voorkomen dat de gebruiker Windows-updates onderbreekt  

- **Standaardinstelling**: Toestaan  
- **Windows-referentiedocumentatie**: [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)  

Toestaan of verhinderen dat de gebruiker van een apparaat de installatie van een update onderbreekt.  

### <a name="require-users-approval-to-restart-outside-of-work-hours"></a>Goedkeuring van de gebruiker vereisen voor opnieuw opstarten buiten werkuren  

- **Standaardinstelling**: Niet geconfigureerd  
- **Windows-referentiedocumentatie**: [Update/AutoRestartRequiredNotificationDismissal](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
  
Selecteer *Vereist* om te vereisen dat een gebruiker opnieuw opstarten van het apparaat buiten werkuren goedkeurt.  
   
### <a name="remind-user-prior-to-required-auto-restart-with-dismissible-reminder-hours"></a>Gebruiker voorafgaand aan het vereiste automatisch opnieuw opstarten herinneren met herinnering die kan worden genegeerd (uren)  

- **Standaardinstelling**: *Dit is niet standaard geconfigureerd, en er wordt geen herinnering weergegeven aan gebruikers*.  
- **Windows-referentiedocumentatie**: [Update/ScheduleRestartWarning](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)  

Geef op hoe lang vóór automatisch opnieuw opstarten een negeerbare melding over die herstart moet worden weergegeven aan de gebruiker van een apparaat. Waarden van **2**, **4**, **8**, **12** of **24** uur worden ondersteund.  

### <a name="remind-user-prior-to-required-auto-restart-with-permanent-reminder-minutes"></a>Gebruiker vooraf eraan herinneren dat automatisch opnieuw opstarten is vereist met een permanente herinnering (minuten)  

- **Standaardinstelling**: *Dit is niet standaard geconfigureerd, en er wordt geen herinnering weergegeven aan gebruikers*.  
- **Windows-referentiedocumentatie**: [Update/ScheduleImminentRestartWarning](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning) 

Geef op hoe lang vóór automatisch opnieuw opstarten een niet-negeerbare melding over die herstart moet worden weergegeven aan de gebruiker van een apparaat. Waarden van **15**, **30** of **60** minuten worden ondersteund.  
 
### <a name="allow-user-to-restart-engaged-restart"></a>Gebruikers toestaan opnieuw te starten (gepland opnieuw opstarten)  

- **Standaardinstelling**: Niet geconfigureerd  
- **Windows-referentiedocumentatie**: *Niet van toepassing*  
- **Windows-versie**: Ondersteund voor Windows 10 versie 1803 en hoger  

  > [!NOTE]  
  > In versie 1809 van Windows 10 worden extra instellingen voor gepland opnieuw opstarten geïntroduceerd waarmee afzonderlijke instellingen kunnen worden toegepast op onderdelen- en kwaliteitsupdates. Door Intune beheerde instellingen worden echter niet afzonderlijk toegepast op de verschillende typen updates. In plaats daarvan past Intune dezelfde waarden toe op zowel onderdelen- als kwaliteitsupdates.  

Als dit is ingesteld op **Vereist**, schakelt u het gebruik van de opties voor gepland opnieuw opstarten voor Windows 10-updates in. Met deze opties wordt de gebruiker van een apparaat ingeschakeld om te helpen beheren wanneer een apparaat opnieuw moet worden opgestart na het installeren van een update waarvoor opnieuw opstarten vereist is.  

Zie [Gepland opnieuw opstarten](https://docs.microsoft.com/en-us/windows/deployment/update/waas-restart#engaged-restart) in de Windows 10-documentatie voor het implementeren van updates voor meer informatie over deze optie.  

De volgende instellingen worden gebruikt om te bepalen wanneer acties voor gepland opnieuw opstarten worden uitgevoerd.  

- **Gebruikers overzetten naar gepland opnieuw opstarten na automatisch opnieuw opstarten (dagen)**  
  - **Standaardinstelling**:  Dit is standaard niet geconfigureerd, maar ondersteunt een waarde van **2** tot **30**.  
  - **Windows-referentiedocumentatie**: [Update/EngagedRestartTransitionSchedule](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-engagedrestarttransitionschedule)  
  Geef op hoe lang nadat de update is geïnstalleerd het apparaat overgaat op het gedrag voor gepland opnieuw opstarten. Na het geconfigureerde aantal dagen ontvangen gebruikers een prompt om het apparaat opnieuw op te starten.  

- **Herinnering voor gepland opnieuw opstarten uitstellen (dagen)**  
  - **Standaardinstelling**:  Dit is standaard niet geconfigureerd, maar ondersteunt een waarde van **1** tot **3**.  
  - **Windows-referentiedocumentatie**: [Update/EngagedRestartSnoozeSchedule](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-engagedrestartsnoozeschedule)  
  Geef op hoe lang een prompt voor opnieuw opstarten kan worden uitgesteld.  Na de uitstelperiode wordt de prompt voor opnieuw opstarten opnieuw aangeboden. De gebruiker kan de herinnering blijven uitstellen totdat de installatiedeadline wordt bereikt.  

- **Deadline instellen voor opnieuw opstarten (dagen)**  
  - **Standaardinstelling**:  Dit is standaard niet geconfigureerd, maar ondersteunt een waarde van **2** tot **30**.  
  - **Windows-referentiedocumentatie**: [Update/EngagedRestartDeadline](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-csp-update#update-engagedrestartdeadline)  
  Geef een maximum aantal dagen op dat na het begin van het gedrag voor gepland opnieuw opstarten moet worden gewacht voordat een apparaat een vereiste herstart afdwingt. Bij het opnieuw opstarten wordt de gebruikers gevraagd hun werk op te slaan

### <a name="delivery-optimization-download-mode"></a>Delivery Optimization-downloadmodus  

- **Standaardinstelling**:  Niet van toepassing
- **Windows-referentiedocumentatie**: *Niet van toepassing*

Delivery Optimization wordt niet meer als onderdeel van een update-ring voor Windows 10 geconfigureerd onder Software-updates. Delivery Optimization wordt nu ingesteld via de apparaatconfiguratie. Eerdere configuraties blijven echter beschikbaar in de console. U kunt deze eerdere configuraties verwijderen door ze te bewerken en te markeren als *Niet geconfigureerd*, maar verder kunnen ze niet worden gewijzigd. 

Zie [Verplaatsen van bestaande update-ringen naar Delivery Optimization](https://docs.microsoft.com/en-us/intune/delivery-optimization-windows#move-from-existing-update-rings-to-delivery-optimization) om conflicten tussen nieuwe en oude beleidsregels te voorkomen en uw instellingen vervolgens te verplaatsen naar een Delivery Optimization-profiel.


