---
title: Instellingen van Windows Update voor Bedrijven voor Microsoft Intune - Azure | Microsoft Docs
description: WUfB-instellingen voor Windows 10-apparaten die u kunt implementeren met behulp van Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/18/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 06982bdf0aff1870f1a759f68bc6cdd48227a3cf
ms.sourcegitcommit: e1ff157f692983b49bdd6e20cc9d0f93c3b3733c
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124993"
---
# <a name="windows-update-settings-for-intune"></a>Windows Update-instellingen voor Intune  

Bekijk de Windows 10 Update-instellingen die u kunt [configureren en beheren](windows-update-for-business-configure.md) met Microsoft Intune.  

Wanneer u instellingen voor Windows 10-update-ringen in Intune configureert, configureert u de instellingen voor Windows Update. Wanneer een Windows Update-instelling afhankelijk is van een Windows 10-versie, wordt de versieafhankelijkheid vermeld in de instellingsdetails.  

## <a name="update-settings"></a>Update-instellingen  

Update-instellingen bepalen welke bits een apparaat downloadt, en wanneer. Raadpleeg de Windows-referentiedocumentatie voor meer informatie over het gedrag van elke instelling.  

- **Servicekanaal**  
  **Standaardinstelling**: Semi-Annual-kanaal  
  Windows Update CSP: [Update/BranchReadinessLevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-branchreadinesslevel)  

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
  **Standaardinstelling**:  Toestaan  
  Windows Update CSP: [Update/AllowMUUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowmuupdateservice)

  - **Toestaan**: selecteer *Toestaan* om te scannen op app-updates van Microsoft Update.  
  - **Blokkeren**: selecteer Blokkeren om te voorkomen dat er wordt gescand op app-updates.  

- **Windows-stuurprogramma's**  
  **Standaardinstelling**:  Toestaan  
  Windows Update CSP: [Update/ExcludeWUDriversInQualityUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-excludewudriversinqualityupdate)  

  - Kies **Toestaan**: selecteer *Toestaan* als u Windows Update-stuurprogramma's ook wilt laten bijwerken.  
  - **Blokkeren**: selecteer Blokkeren om scannen voor stuurprogramma’s te voorkomen.  

- **Uitstelperiode voor kwaliteitsupdates (dagen)**  
  **Standaardinstelling**: 0  
  Windows Update CSP: [Update/DeferQualityUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferqualityupdatesperiodindays)  

  Geef het aantal dagen (0 tot 30) op dat kwaliteitsupdates worden uitgesteld. Deze periode wordt opgeteld bij de eventuele uitstelperiode van het servicekanaal dat u selecteert. De uitstelperiode begint wanneer het beleid wordt ontvangen door het apparaat.  

  Kwaliteitsupdates zijn doorgaans oplossingen en verbeteringen in de bestaande Windows-functionaliteit.  

- **Uitstelperiode voor onderdelenupdates (dagen)**  
  **Standaardinstelling**: 0  
  Windows Update CSP: [Update/PauseFeatureUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferfeatureupdatesperiodindays)  

  Geef het aantal dagen op dat onderdelenupdates worden uitgesteld. Deze periode wordt opgeteld bij de eventuele uitstelperiode van het servicekanaal dat u selecteert. De uitstelperiode begint wanneer het beleid wordt ontvangen door het apparaat.  

  Ondersteunde uitstelperiode:  

  - *Windows-versie 1709 en hoger* - 0 tot 365 dagen  
  - *Windows-versie 1703* - 0 tot en met 180 dagen  

  Upgrades van onderdelen zijn over het algemeen nieuwe functies van Windows.  

- **Periode instellen voor onderdelenupdate verwijderen (2-60 dagen)**  
  **Standaardinstelling**: 10  
  Windows Update CSP: [Update/ConfigureFeatureUpdateUninstallPeriod](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configurefeatureupdateuninstallperiod)  

  Configureer een tijd waarna onderdelenupdates niet meer kunnen worden verwijderd.  

  Nadat deze periode is verlopen, worden de bits van de vorige update van het apparaat verwijderd en kan de installatie niet ongedaan worden gemaakt naar een vorige updateversie.  

  Neem bijvoorbeeld een update-ring met een verwijderingsperiode voor onderdelenupdates van 20 dagen. Na 25 dagen besluit u de laatste onderdelenupdate terug te draaien, en gebruikt u de optie Verwijderen.  Op apparaten waarop de functie-update meer dan 20 dagen geleden is geïnstalleerd, is verwijderen niet mogelijk, omdat de vereiste bits als onderdeel van het onderhoud zijn verwijderd. Op apparaten waar de onderdelenupdate nog maar negentien dagen geleden is geïnstalleerd, kan de update wel worden verwijderd, als ze zich aanmelden om de verwijderopdracht te ontvangen voordat de verwijderingsperiode van twintig dagen is verstreken.  

## <a name="user-experience-settings"></a>Instellingen voor gebruikerservaring  

De instellingen voor de gebruikerservaring bepalen de ervaring van de eindgebruiker wat betreft het opnieuw opstarten van het apparaat en ontvangen herinneringen. Raadpleeg de Windows Update CSP-documentatie voor meer informatie over het gedrag van elke instelling.  

- **Gedrag van automatische updates**  
  **Standaardinstelling**: Automatisch installeren op onderhoudstijdstip  
  Windows Update CSP: [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)  

  Kies hoe automatische updates worden geïnstalleerd, en wanneer het apparaat indien nodig opnieuw moet worden opgestart.  

  Ondersteunde opties:  

  - **Download melden**: De gebruiker waarschuwen voordat de update wordt gedownload. Gebruikers kiezen wanneer ze updates willen downloaden en installeren.  

  - **Automatisch installeren op het tijdstip voor onderhoud**: Updates worden automatisch gedownload en vervolgens geïnstalleerd tijdens Automatisch onderhoud wanneer het apparaat niet in gebruik is of op accustroom werkt. Wanneer opnieuw opstarten nodig is, wordt gebruikers zeven dagen gevraagd opnieuw op te starten, en vervolgens wordt opnieuw opstarten geforceerd.  

    Deze optie kan een apparaat automatisch opnieuw opstarten nadat de update is geïnstalleerd. Gebruik de instelling **Gebruikstijden** om een periode te definiëren waarin automatisch opnieuw opstarten wordt geblokkeerd:  

    - **Start gebruikstijd**: Geef een begintijd op voor het onderdrukken van opnieuw opstarten vanwege update-installaties.  
      **Standaardinstelling**: 08:00 uur  
      Windows Update CSP: [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)  
  
    - **Einde gebruikstijd**: Geef een eindtijd op voor het onderdrukken van opnieuw opstarten vanwege update-installaties.  
      **Standaardinstelling**: 17:00 uur  
      Windows Update CSP: [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)  

  - **Automatisch installeren en opnieuw starten op het tijdstip voor onderhoud** – Updates worden automatisch gedownload en vervolgens geïnstalleerd tijdens Automatisch onderhoud wanneer het apparaat niet in gebruik is of op accustroom werkt. Als opnieuw opstarten vereist is, wordt het apparaat opnieuw opgestart wanneer het niet wordt gebruikt. (Dit is de standaardinstelling voor niet-beheerde apparaten.)  

    Deze optie kan een apparaat automatisch opnieuw opstarten nadat de update is geïnstalleerd. Het gebruik van de instelling **Gebruikstijden** wordt niet beschreven in de instellingen van Windows Update, maar worden gebruikt door Intune om een periode te definiëren waarin automatisch opnieuw opstarten wordt geblokkeerd:  

    - **Start gebruikstijd**: Geef een begintijd op voor het onderdrukken van opnieuw opstarten vanwege update-installaties.  
      **Standaardinstelling**: 08:00 uur  
      Windows Update CSP: [Update/ActiveHoursStart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursstart)  
  
    - **Einde gebruikstijd**: Geef een eindtijd op voor het onderdrukken van opnieuw opstarten vanwege update-installaties.  
      **Standaardinstelling**: 17:00 uur  
      Windows Update CSP: [Update/ActiveHoursEnd](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-activehoursend)  

  - **Automatisch installeren en opnieuw starten op het geplande tijdstip**: Geef een installatiedag en -tijd op. Als er niets wordt opgegeven, wordt de installatie dagelijks om 03:00 uur uitgevoerd, gevolgd door een aftelling van 15 minuten naar een herstart. Aangemelde gebruikers kunnen het aftellen en opnieuw opstarten uitstellen.   
  Windows Update CSP: [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowautoupdate)  

    Deze optie ondersteunt extra instellingen.  

    - **Frequentie van automatisch gedrag**: Gebruik deze instelling om te plannen wanneer updates worden geïnstalleerd, inclusief de week, de dag en het tijdstip.  
      **Standaardinstelling**: Elke week

    - **Geplande installatiedag**: Geef aan op welke dag van de week u wilt dat updates worden geïnstalleerd.  
      **Standaardinstelling**: Elke dag  

    - **Geplande installatietijd**: Geef aan op welke dag van de week u wilt dat updates worden geïnstalleerd.  
      **Standaardinstelling**: 03:00 uur  

  - **Automatisch installeren en opnieuw opstarten zonder tussenkomst van de eindgebruiker**: Updates worden automatisch gedownload en vervolgens geïnstalleerd tijdens Automatisch onderhoud wanneer het apparaat niet in gebruik is of op accustroom werkt. Als opnieuw opstarten vereist is, wordt het apparaat opnieuw opgestart wanneer het niet wordt gebruikt. Deze optie stelt het configuratiescherm van de eindgebruiker in op alleen-lezen.  

  - Met de instelling **Standaardinstellingen herstellen** herstelt u de oorspronkelijke instellingen voor automatisch bijwerken op Windows 10-computers met de update van oktober 2018 of later.  


- **Controles voor opnieuw starten**  
  **Standaardinstelling**: Toestaan  
  Windows Update CSP: [Update/SetEDURestart](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setedurestart)  

  Als u deze controles wilt overslaan wanneer u een apparaat opnieuw start, kiest u **Overslaan**. 
  
  Deze instelling heeft verschillende resultaten, afhankelijk van de Windows-versie van het apparaat:  
 
  - *Windows-versie 1703 en eerder*: Wanneer u een apparaat opnieuw start, worden er een aantal controles uitgevoerd. Zo wordt bijvoorbeeld gecontroleerd op actieve gebruikers, batterijniveau, actieve games en meer.  
  
  - *Windows-versie 1709 en later*: Tijdens de gebruikstijd worden de volgende processen niet uitgevoerd voor updates: scannen, downloaden, installeren en opnieuw opstarten. Na de gebruikstijd worden de updateprocessen wel uitgevoerd en kunnen ze het apparaat uit de slaapstand halen, scannen, downloaden, installeren en opnieuw opstarten, zolang het door de accu- en stroomcontrole komt. 

- **Voorkomen dat de gebruiker Windows-updates onderbreekt**  
  **Standaardinstelling**: Toestaan  
  Windows Update CSP: [Update/SetDisablePauseUXAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisablepauseuxaccess)  

  - **Toestaan**: sta toe dat de gebruiker van een apparaat de installatie van een update kan onderbreken.  
  - **Blokkeren**: voorkom dat de gebruiker van een apparaat de installatie van een update onderbreekt.  

- **Blokkeren dat de gebruiker kan zoeken naar Windows-updates**  
  **Standaardinstelling**: Toestaan  
  Windows Update CSP: [Update/SetDisableUXWUAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-setdisableuxwuaccess) 

  - **Toestaan**: sta toe dat de gebruiker van een apparaat een Windows Update-scan gebruikt om updates te zoeken en te downloaden, en functies te installeren.
  - **Blokkeren**: voorkom dat de gebruiker van een apparaat toegang heeft tot de Windows Update-scan, updates kan downloaden, en functies kan installeren.  

- **Goedkeuring van de gebruiker vereisen voor opnieuw opstarten buiten werkuren**  
  **Standaardinstelling**: Niet geconfigureerd  
  Windows Update CSP: [Update/AutoRestartRequiredNotificationDismissal](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-autorestartrequirednotificationdismissal)
  
  - **Niet geconfigureerd**  
  - **Vereist**: Vereisen dat een gebruiker opnieuw opstarten van het apparaat buiten werkuren goedkeurt.  
   
- **Gebruiker voorafgaand aan het vereiste automatisch opnieuw opstarten herinneren met herinnering die kan worden genegeerd (uren)**  
  **Standaardinstelling**: 4  
  Windows Update CSP: [Update/ScheduleRestartWarning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-schedulerestartwarning)  

  Geef op hoe lang vóór automatisch opnieuw opstarten een negeerbare melding over die herstart moet worden weergegeven aan de gebruiker van een apparaat. Waarden van **2**, **4**, **8**, **12** of **24** uur worden ondersteund.  
  
  Wanneer u de standaardwaarde wist, wordt deze instelling *Niet geconfigureerd*.  

- **Gebruiker vooraf eraan herinneren dat automatisch opnieuw opstarten is vereist met een permanente herinnering (minuten)**  
  **Standaardinstelling**: 15  
  Windows Update CSP: [Update/ScheduleImminentRestartWarning](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-scheduleimminentrestartwarning)  

  Geef op hoe lang vóór automatisch opnieuw opstarten een niet-negeerbare melding over die herstart moet worden weergegeven aan de gebruiker van een apparaat. Waarden van **15**, **30** of **60** minuten worden ondersteund.  

  Wanneer u de standaardwaarde wist, wordt deze instelling *Niet geconfigureerd*.  

- **Niveau van Update-melding wijzigen**  
  **Standaardinstelling**: Gebruik de standaardmeldingen van Windows Update  
  Windows Update CSP: [Update/UpdateNotificationLevel](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updatenotificationlevel)
  
  Geef aan op welk niveau van Windows Update-meldingen zichtbaar is voor gebruikers. Deze instelling bepaalt niet hoe en wanneer updates worden gedownload en geïnstalleerd.  

  Ondersteunde opties:
  - **Niet geconfigureerd**
  - **Gebruik de standaard Windows Update-meldingen**
  - **Schakel alle meldingen uit, met uitzondering van waarschuwingen voor opnieuw opstarten**
  - **Schakel alle meldingen uit, inclusief waarschuwingen voor opnieuw opstarten**  

- **Deadline-instellingen gebruiken**  
  **Standaardinstelling**: Niet geconfigureerd  
 
  Hiermee kunnen gebruikers deadline-instellingen gebruiken.  

  - **Niet geconfigureerd**
  - **Toestaan**

  Als de optie is ingesteld op *Toestaan*, kunt u de volgende instellingen voor deadlines configureren:

  - **Deadline voor onderdelenupdates**  
    **Standaardinstelling**: *Niet geconfigureerd*  
    Windows Update CSP: [Update/ConfigureDeadlineForFeatureUpdates](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforfeatureupdates)  

    Hiermee geeft u het aantal dagen op dat een gebruiker heeft voordat de onderdelenupdates automatisch op de apparaten worden geïnstalleerd (2-30).

  - **Deadline voor kwaliteitsupdates**  
    **Standaardinstelling**: *Niet geconfigureerd*  
    Windows Update CSP: [Update/ConfigureDeadlineForQualityUpdates](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configuredeadlineforqualityupdates)

    Hiermee geeft u het aantal dagen op dat een gebruiker heeft voordat de kwaliteitsupdates automatisch op de apparaten worden geïnstalleerd (2-30).

  - **Respijtperiode**  
    **Standaard**: *Niet geconfigureerd* Windows Update CSP: [Update/ConfigureDeadlineGracePeriod]( https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configuredeadlinegraceperiod)

    Hiermee wordt een minimum aantal dagen na de deadline opgegeven voordat er automatische opnieuw wordt opgestart (2-7).

  - **Automatisch opnieuw opstarten vóór deadline**  
    **Standaard**:  Ja Windows Update CSP: [Update/ConfigureDeadlineNoAutoReboot](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-configuredeadlinenoautoreboot)

    Hiermee wordt opgegeven of het apparaat automatisch opnieuw moet worden opgestart vóór de deadline.
    - **Ja**
    - **Nee**

### <a name="delivery-optimization-download-mode"></a>Delivery Optimization-downloadmodus  

Delivery Optimization wordt niet meer als onderdeel van een update-ring voor Windows 10 geconfigureerd onder Software-updates. Delivery Optimization wordt nu ingesteld via de apparaatconfiguratie. Eerdere configuraties blijven echter beschikbaar in de console. U kunt deze eerdere configuraties verwijderen door ze te bewerken en te markeren als *Niet geconfigureerd*, maar verder kunnen ze niet worden gewijzigd. 

Zie [Delivery Optimization verwijderen uit Windows 10 update-ringen](../configuration/delivery-optimization-windows.md#remove-delivery-optimization-from-windows-10-update-rings) om conflicten tussen nieuwe en oude beleidsregels te voorkomen en uw instellingen vervolgens te verplaatsen naar een Delivery Optimization-profiel.
