---
title: Instellingen van Windows Update voor Bedrijven voor Microsoft Intune - Azure | Microsoft Docs
description: WUfB-instellingen voor Windows 10-apparaten die u kunt implementeren met behulp van Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 08/15/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5aaa964151477896c236e504ec9b378cf580e838
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71736374"
---
# <a name="windows-update-settings-for-intune"></a>Windows Update-instellingen voor Intune  

Bekijk de Windows 10 Update-instellingen die u kunt [configureren en beheren](windows-update-for-business-configure.md) met Microsoft Intune.  

Wanneer u instellingen voor Windows 10-update-ringen in Intune configureert, configureert u de instellingen voor Windows Update. Wanneer een Windows Update-instelling afhankelijk is van een Windows 10-versie, wordt de versieafhankelijkheid vermeld in de instellingsdetails.  

## <a name="update-settings"></a>Update-instellingen  

Update-instellingen bepalen welke bits een apparaat downloadt, en wanneer. Raadpleeg de Windows-referentiedocumentatie voor meer informatie over het gedrag van elke instelling.  

- **Servicekanaal**  
  **Standaard**: Semi-Annual-kanaal  
  Windows Update CSP: [Update-BranchReadinessLevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-branchreadinesslevel)  

  Stel het kanaal (branch) in van waaruit het apparaat Windows-updates ontvangt. Verschillende kanalen kunnen verschillende uitstelperioden gebruiken voordat updates worden geleverd.  

  Zo heeft het *Semi-Annual-kanaal* een uitstel van zes maanden. Als u dit kanaal gebruikt zonder extra uitstel in deze groep instellingen, het apparaat de update zes maanden na de release installeert.  

  Ondersteunde updatekanalen:  

  - Semi-Annual-kanaal  
  - Semi-Annual-kanaal (targeted)  
  - Windows Insider – Fast  
  - Windows Insider – Slow  
  - Windows Insider vrijgeven  

  Als u een insider-kanaal selecteert, configureert Intune automatisch de Windows-update-instelling [Update/ManagePreviewBuilds](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-managepreviewbuilds), zodat de insider-build werkt.  


  > [!IMPORTANT]  
  > Vanaf Windows-versie 1903 wordt het gebruik van het *Semi-Annual-kanaal (targeted)* (SAC-T) stopgezet. Met deze wijziging wordt SAC-T samengevoegd met het *Semi-Annual-kanaal*. Zie voor meer informatie over deze wijziging en hoe dit van invloed is op Windows Update voor Bedrijven, het bericht [Windows Update for Business and the retirement of SAC-T](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/Windows-Update-for-Business-and-the-retirement-of-SAC-T/ba-p/339523) in het Windows IT Pro Blog.  
 
- **Productupdates van Microsoft**  
  **Standaard**: toestaan  
  Windows Update CSP: [Update-AllowMUUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowmuupdateservice)

  - **Toestaan** : Selecteer *toestaan* om te scannen op app-updates van Microsoft Update.  
  - **Blok keren** : Selecteer blok om te voor komen dat er wordt gescand op app-updates.  

- **Windows-stuurprogramma's**  
  **Standaard**: toestaan  
  Windows Update CSP: [Update-ExcludeWUDriversInQualityUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-excludewudriversinqualityupdate)  

  - **Toestaan** : Selecteer Windows Update Stuur Programma's *toestaan* tijdens updates.  
  - **Blok keren** : Selecteer blok om te voor komen dat er Stuur Programma's worden gescand.  

- **Uitstelperiode voor kwaliteitsupdates (dagen)**  
  **Standaard**: 0  
  Windows Update CSP: [Update-DeferQualityUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferqualityupdatesperiodindays)  

  Geef het aantal dagen (0 tot 30) op dat kwaliteitsupdates worden uitgesteld. Deze periode wordt opgeteld bij de eventuele uitstelperiode van het servicekanaal dat u selecteert. De uitstelperiode begint wanneer het beleid wordt ontvangen door het apparaat.  

  Kwaliteitsupdates zijn doorgaans oplossingen en verbeteringen in de bestaande Windows-functionaliteit.  

- **Uitstelperiode voor onderdelenupdates (dagen)**  
  **Standaard**: 0  
  Windows Update CSP: [Update-PauseFeatureUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferfeatureupdatesperiodindays)  

  Geef het aantal dagen op dat onderdelenupdates worden uitgesteld. Deze periode wordt opgeteld bij de eventuele uitstelperiode van het servicekanaal dat u selecteert. De uitstelperiode begint wanneer het beleid wordt ontvangen door het apparaat.  

  Ondersteunde uitstelperiode:  

  - *Windows-versie 1709 en hoger* -0 tot 365 dagen  
  - *Windows-versie 1703* - 0 tot en met 180 dagen  

  Upgrades van onderdelen zijn over het algemeen nieuwe functies van Windows.  

- **Periode instellen voor onderdelenupdate verwijderen (2-60 dagen)**  
  **Standaard**: 10  
  Windows Update CSP: [Update-ConfigureFeatureUpdateUninstallPeriod](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configurefeatureupdateuninstallperiod)  

  Configureer een tijd waarna onderdelenupdates niet meer kunnen worden verwijderd.  

  Nadat deze periode is verlopen, worden de bits van de vorige update van het apparaat verwijderd en kan de installatie niet ongedaan worden gemaakt naar een vorige updateversie.  

  Neem bijvoorbeeld een update-ring met een verwijderingsperiode voor onderdelenupdates van 20 dagen. Na 25 dagen besluit u de laatste onderdelenupdate terug te draaien, en gebruikt u de optie Verwijderen.  Op apparaten waarop de functie-update meer dan 20 dagen geleden is geïnstalleerd, is verwijderen niet mogelijk, omdat de vereiste bits als onderdeel van het onderhoud zijn verwijderd. Op apparaten waar de onderdelenupdate nog maar negentien dagen geleden is geïnstalleerd, kan de update wel worden verwijderd, als ze zich aanmelden om de verwijderopdracht te ontvangen voordat de verwijderingsperiode van twintig dagen is verstreken.  

## <a name="user-experience-settings"></a>Instellingen voor gebruikerservaring  

De instellingen voor de gebruikerservaring bepalen de ervaring van de eindgebruiker wat betreft het opnieuw opstarten van het apparaat en ontvangen herinneringen. Raadpleeg de Windows Update CSP-documentatie voor meer informatie over het gedrag van elke instelling.  

- **Gedrag van automatische updates**  
  **Standaard**: Automatisch installeren op onderhoudstijdstip  
  Windows Update CSP: [Update-AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)  

  Kies hoe automatische updates worden geïnstalleerd, en wanneer het apparaat indien nodig opnieuw moet worden opgestart.  

  Ondersteunde opties:  

  - **Download melden**: De gebruiker waarschuwen voordat de update wordt gedownload. Gebruikers kiezen wanneer ze updates willen downloaden en installeren.  

  - **Automatisch installeren op het tijdstip voor onderhoud**: Updates worden automatisch gedownload en vervolgens geïnstalleerd tijdens Automatisch onderhoud wanneer het apparaat niet in gebruik is of op accustroom werkt. Wanneer opnieuw opstarten nodig is, wordt gebruikers zeven dagen gevraagd opnieuw op te starten, en vervolgens wordt opnieuw opstarten geforceerd.  

    Deze optie kan een apparaat automatisch opnieuw opstarten nadat de update is geïnstalleerd. Gebruik de instelling **Gebruikstijden** om een periode te definiëren waarin automatisch opnieuw opstarten wordt geblokkeerd:  

    - **Start gebruikstijd**: Geef een begintijd op voor het onderdrukken van opnieuw opstarten vanwege update-installaties.  
      **Standaard**: 8: 00 uur  
      Windows Update CSP: [Update-ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)  
  
    - **Einde gebruikstijd**: Geef een eindtijd op voor het onderdrukken van opnieuw opstarten vanwege update-installaties.  
      **Standaard**: 17: 00 uur  
      Windows Update CSP: [Update-ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)  

  - **Automatisch installeren en opnieuw starten op het tijdstip voor onderhoud** – Updates worden automatisch gedownload en vervolgens geïnstalleerd tijdens Automatisch onderhoud wanneer het apparaat niet in gebruik is of op accustroom werkt. Als opnieuw opstarten vereist is, wordt het apparaat opnieuw opgestart wanneer het niet wordt gebruikt. (Dit is de standaardinstelling voor niet-beheerde apparaten.)  

    Deze optie kan een apparaat automatisch opnieuw opstarten nadat de update is geïnstalleerd. Het gebruik van de instelling **Gebruikstijden** wordt niet beschreven in de instellingen van Windows Update, maar worden gebruikt door Intune om een periode te definiëren waarin automatisch opnieuw opstarten wordt geblokkeerd:  

    - **Start gebruikstijd**: Geef een begintijd op voor het onderdrukken van opnieuw opstarten vanwege update-installaties.  
      **Standaard**: 8: 00 uur  
      Windows Update CSP: [Update-ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)  
  
    - **Einde gebruikstijd**: Geef een eindtijd op voor het onderdrukken van opnieuw opstarten vanwege update-installaties.  
      **Standaard**: 17: 00 uur  
      Windows Update CSP: [Update-ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)  

  - **Automatisch installeren en opnieuw starten op het geplande tijdstip**: Geef een installatiedag en -tijd op. Als er niets wordt opgegeven, wordt de installatie dagelijks om 03:00 uur uitgevoerd, gevolgd door een aftelling van 15 minuten naar een herstart. Aangemelde gebruikers kunnen het aftellen en opnieuw opstarten uitstellen.   
  Windows Update CSP: [Update-AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)  

    Deze optie ondersteunt extra instellingen.  

    - **Frequentie van automatisch gedrag**: Gebruik deze instelling om te plannen wanneer updates worden geïnstalleerd, inclusief de week, de dag en het tijdstip.  
      **Standaard**: elke week

    - **Geplande installatiedag**: Geef aan op welke dag van de week u wilt dat updates worden geïnstalleerd.  
      **Standaard**: elke dag  

    - **Geplande installatietijd**: Geef aan op welke dag van de week u wilt dat updates worden geïnstalleerd.  
      **Standaard**: 3: 00 uur  

  - **Automatisch installeren en opnieuw opstarten zonder tussenkomst van de eindgebruiker**: Updates worden automatisch gedownload en vervolgens geïnstalleerd tijdens Automatisch onderhoud wanneer het apparaat niet in gebruik is of op accustroom werkt. Als opnieuw opstarten vereist is, wordt het apparaat opnieuw opgestart wanneer het niet wordt gebruikt. Deze optie stelt het configuratiescherm van de eindgebruiker in op alleen-lezen.  

  - Met de instelling **Standaardinstellingen herstellen** herstelt u de oorspronkelijke instellingen voor automatisch bijwerken op Windows 10-computers met de update van oktober 2018 of later.  


- **Controles voor opnieuw starten**  
  **Standaard**: toestaan  
  Windows Update CSP: [Update-SetEDURestart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setedurestart)  

  Als u deze controles wilt overslaan wanneer u een apparaat opnieuw start, kiest u **Overslaan**. 
  
  Deze instelling heeft verschillende resultaten, afhankelijk van de Windows-versie van het apparaat:  
 
  - *Windows-versie 1703 en eerder*: Wanneer u een apparaat opnieuw start, worden er een aantal controles uitgevoerd. Zo wordt bijvoorbeeld gecontroleerd op actieve gebruikers, batterijniveau, actieve games en meer.  
  
  - *Windows-versie 1709 en later*: Tijdens de gebruikstijd worden de volgende processen niet uitgevoerd voor updates: scannen, downloaden, installeren en opnieuw opstarten. Na de gebruikstijd worden de updateprocessen wel uitgevoerd en kunnen ze het apparaat uit de slaapstand halen, scannen, downloaden, installeren en opnieuw opstarten, zolang het door de accu- en stroomcontrole komt. 

- **Voorkomen dat de gebruiker Windows-updates onderbreekt**  
  **Standaard**: toestaan  
  Windows Update CSP: [Update-SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)  

  - **Toestaan** : Hiermee staat u toe dat apparaat-gebruikers de installatie van een update onderbreken.  
  - **Blok keren** : gebruikers kunnen de installatie van een update niet onderbreken.  

- **Blokkeren dat de gebruiker kan zoeken naar Windows-updates**  
  **Standaard**: toestaan  
  Windows Update CSP: [Update-SetDisableUXWUAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisableuxwuaccess) 

  - **Toestaan** : Hiermee staat u toe dat apparaat-gebruikers Windows Update Scan kunnen gebruiken om updates te zoeken en te downloaden en functies te installeren.
  - **Blok keren** : hiermee voor komt u dat gebruikers van het apparaat toegang hebben tot de Windows Update Scan, het downloaden van updates en het installeren van functies.  

- **Goedkeuring van de gebruiker vereisen voor opnieuw opstarten buiten werkuren**  
  **Standaard**: niet geconfigureerd  
  Windows Update CSP: [Update-AutoRestartRequiredNotificationDismissal](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
  
  - **Niet geconfigureerd**  
  - **Vereist**: Vereisen dat een gebruiker opnieuw opstarten van het apparaat buiten werkuren goedkeurt.  
   
- **Gebruiker voorafgaand aan het vereiste automatisch opnieuw opstarten herinneren met herinnering die kan worden genegeerd (uren)**  
  **Standaardinstelling**: 4  
  Windows Update CSP: [Update-ScheduleRestartWarning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)  

  Geef op hoe lang vóór automatisch opnieuw opstarten een negeerbare melding over die herstart moet worden weergegeven aan de gebruiker van een apparaat. Waarden van **2**, **4**, **8**, **12** of **24** uur worden ondersteund.  
  
  Wanneer u de standaard waarde wist, wordt deze instelling *niet geconfigureerd*.  

- **Gebruiker vooraf eraan herinneren dat automatisch opnieuw opstarten is vereist met een permanente herinnering (minuten)**  
  **Standaardinstelling**: 15  
  Windows Update CSP: [Update-ScheduleImminentRestartWarning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning)  

  Geef op hoe lang vóór automatisch opnieuw opstarten een niet-negeerbare melding over die herstart moet worden weergegeven aan de gebruiker van een apparaat. Waarden van **15**, **30** of **60** minuten worden ondersteund.  

  Wanneer u de standaard waarde wist, wordt deze instelling *niet geconfigureerd*.  

- **Niveau van Update-melding wijzigen**  
  **Standaard**: gebruik de standaard Windows Update-meldingen  
  Windows Update CSP: [Update-UpdateNotificationLevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)
  
  Geef aan op welk niveau van Windows Update-meldingen zichtbaar is voor gebruikers. Deze instelling bepaalt niet hoe en wanneer updates worden gedownload en geïnstalleerd.  

  Ondersteunde opties:
  - **Niet geconfigureerd**
  - **Gebruik de standaard Windows Update-meldingen**
  - **Alle meldingen uitschakelen, met uitzonde ring van waarschuwingen voor opnieuw opstarten**
  - **Alle meldingen uitschakelen, inclusief waarschuwingen voor opnieuw opstarten**  

- **Gebruikers toestaan opnieuw te starten (gepland opnieuw opstarten)**  
  **Standaard**: niet geconfigureerd  
  > [!IMPORTANT]  
  > Instellingen voor *ingeschakelde opnieuw opstarten* worden niet meer aanbevolen voor gebruik. Gebruik in plaats daarvan de nieuwe *deadline* instellingen die de *ingeschakelde instellingen voor opnieuw opstarten* vervangen. InTune zal de [ondersteuning voor *ingeschakelde herstart* ](../fundamentals/whats-new.md#plan-for-change-new-windows-updates-settings-in-intune-) -instellingen in een toekomstige update afnemen.

  De ingeschakelde herstart wordt ondersteund voor Windows 10 versie 1803 en hoger. 

  > [!NOTE]  
  > In versie 1809 van Windows 10 worden extra instellingen voor gepland opnieuw opstarten geïntroduceerd waarmee afzonderlijke instellingen kunnen worden toegepast op onderdelen- en kwaliteitsupdates. Door Intune beheerde instellingen worden echter niet afzonderlijk toegepast op de verschillende typen updates. In plaats daarvan past Intune dezelfde waarden toe op zowel onderdelen- als kwaliteitsupdates.  
  
  - **Niet geconfigureerd**  
  - **Vereist**: Instellen op *Vereist* om gebruik van de opties voor gepland opnieuw opstarten voor Windows 10-updates in te schakelen. Met deze opties wordt de gebruiker van een apparaat ingeschakeld om te helpen beheren wanneer een apparaat opnieuw moet worden opgestart na het installeren van een update waarvoor opnieuw opstarten vereist is.  

  Zie [Gepland opnieuw opstarten](https://docs.microsoft.com/windows/deployment/update/waas-restart#engaged-restart) in de Windows 10-documentatie voor het implementeren van updates voor meer informatie over deze optie.  

  De volgende instellingen worden gebruikt om te bepalen wanneer acties voor gepland opnieuw opstarten worden uitgevoerd.  

  - **Gebruikers overzetten naar gepland opnieuw opstarten na automatisch opnieuw opstarten (dagen)**  
    **Standaard**: niet geconfigureerd Windows Update CSP: [Update-EngagedRestartTransitionSchedule](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-engagedrestarttransitionschedule)  
    
    Geef een waarde op van **2** tot **30** dagen op voor hoelang nadat de update is geïnstalleerd het apparaat overgaat op het gedrag voor gepland opnieuw opstarten. Na het geconfigureerde aantal dagen ontvangen gebruikers een prompt om het apparaat opnieuw op te starten.  

  - **Herinnering voor gepland opnieuw opstarten uitstellen (dagen)**  
    **Standaard**: niet geconfigureerd    
    Windows Update CSP: [Update-EngagedRestartSnoozeSchedule](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-engagedrestartsnoozeschedule)  
    
    Geef een waarde op van **1** tot **3** voor hoe lang de prompt voor opnieuw opstarten kan worden uitgesteld.  Na de uitstelperiode wordt de prompt voor opnieuw opstarten opnieuw aangeboden. De gebruiker kan de herinnering blijven uitstellen totdat de installatiedeadline wordt bereikt.  

  - **Deadline instellen voor opnieuw opstarten (dagen)**  
    **Standaard**: niet geconfigureerd  
    Windows Update CSP: [Update-EngagedRestartDeadline](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-engagedrestartdeadline)  
  
    Geef een waarde van **2** tot **30** op als maximumaantal dagen dat na het begin van het gedrag voor gepland opnieuw opstarten moet worden gewacht voordat een apparaat een vereiste herstart afdwingt. Bij het opnieuw opstarten wordt de gebruikers gevraagd hun werk op te slaan.

- **Deadline instellingen gebruiken**  
  **Standaard**: niet geconfigureerd  
  > [!IMPORTANT]  
  > Vanaf de update van augustus voor intune, raden we u aan de volgende deadline-instellingen te gebruiken die de ingeschakelde instellingen voor opnieuw opstarten vervangen. InTune zal de [ondersteuning voor *ingeschakelde herstart* ](../fundamentals/whats-new.md#plan-for-change-new-windows-updates-settings-in-intune-) -instellingen in een toekomstige update van intune afnemen.  

  Hiermee kan de gebruiker deadline instellingen gebruiken.  

  - **Niet geconfigureerd**
  - **Toestaan**

  Wanneer u deze instelling instelt op *toestaan*, kunt u de volgende instellingen voor deadlines configureren:

  - **Deadline voor onderdeel updates**  
    **Standaard**: 7  
    Windows Update CSP: [Update-ConfigureDeadlineForFeatureUpdates](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforfeatureupdates)  

    Hiermee geeft u het aantal dagen op dat een gebruiker heeft voordat de functie-updates automatisch worden geïnstalleerd op hun apparaten (2-30).

  - **Deadline voor kwaliteits updates**  
    **Standaard**: 7  
    Windows Update CSP: [Update-ConfigureDeadlineForQualityUpdates](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforqualityupdates)

    Hiermee geeft u het aantal dagen op dat een gebruiker heeft voordat kwaliteits updates automatisch worden geïnstalleerd op hun apparaten (2-30).

  - **Respijtperiode**  
    **Standaard**: 2 Windows Update CSP: [Update-ConfigureDeadlineGracePeriod]( https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configuredeadlinegraceperiod)

    Hiermee geeft u een minimum aantal dagen na de deadline op waarna de herstart automatisch wordt uitgevoerd (0-7).

  - **Automatisch opnieuw opstarten vóór deadline**  
    **Standaard**: Ja Windows Update CSP: [Update-ConfigureDeadlineNoAutoReboot](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configuredeadlinenoautoreboot)

    Hiermee geeft u op of het apparaat automatisch opnieuw moet worden opgestart vóór de deadline.
    - **Ja**
    - **Nee**




### <a name="delivery-optimization-download-mode"></a>Delivery Optimization-downloadmodus  

Delivery Optimization wordt niet meer als onderdeel van een update-ring voor Windows 10 geconfigureerd onder Software-updates. Delivery Optimization wordt nu ingesteld via de apparaatconfiguratie. Eerdere configuraties blijven echter beschikbaar in de console. U kunt deze eerdere configuraties verwijderen door ze te bewerken en te markeren als *Niet geconfigureerd*, maar verder kunnen ze niet worden gewijzigd. 

Zie [Verplaatsen van bestaande update-ringen naar Delivery Optimization](../configuration/delivery-optimization-windows.md#move-existing-update-rings-to-delivery-optimization) om conflicten tussen nieuwe en oude beleidsregels te voorkomen en uw instellingen vervolgens te verplaatsen naar een Delivery Optimization-profiel.
