---
title: Een pagina Status van de inschrijving instellen
titleSuffix: Microsoft Intune
description: Stel een begroetingspagina in voor gebruikers die Windows 10-apparaten registreren.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/28/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: ericor
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: d2a6b427552e545421e329b900833c889e67bf35
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72503037"
---
# <a name="set-up-an-enrollment-status-page"></a>Een pagina Status van de inschrijving instellen
 
[!INCLUDE [azure_portal](../includes/azure_portal.md)]
 
Op de pagina Status van de inschrijving vindt u de installatie-informatie over Windows 10-apparaten (versie 1803 en later) tijdens de eerste apparaatinschrijving. Bijvoorbeeld:
- bij het gebruik van [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/) 
- of telkens wanneer een beheerd apparaat de eerste keer wordt gestart nadat een beleid voor de pagina Status van de inschrijving is toegepast. 

De pagina Status van de registratie is handig voor gebruikers om de status van hun apparaat te bekijken tijdens de installatie van het apparaat. U kunt voor de pagina Status van de registratie meerdere profielen maken en deze toepassen op verschillende groepen die gebruikers bevatten. Profielen kunnen worden ingesteld op:
- De voortgang van de installatie weergeven.
- Gebruik blokkeren totdat de installatie is voltooid.
- Opgeven wat een gebruiker kan doen als de installatie van het apparaat mislukt.

U kunt ook de volgorde van prioriteit voor elk profiel instellen om problemen met conflicterende profieltoewijzingen aan dezelfde gebruiker te voorkomen.

> [!NOTE]
> De pagina Status van de inschrijving kan alleen worden gebruikt voor een gebruiker die deel uitmaakt van een toegewezen groep en als het beleid is ingesteld op het apparaat op het moment van inschrijving voor alle gebruikers die het apparaat gebruiken.  

## <a name="available-settings"></a>Beschikbare instellingen

 De volgende instellingen kunnen worden geconfigureerd om de werking van de pagina Status van de inschrijving aan te passen:

<table>
<th align="left">Instelling<th align="left">Ja<th align="left">Nee
<tr><td>Voortgang van installatie van app en profiel weergeven<td>De pagina Status van de inschrijving wordt weergegeven.<td>De pagina Status van de inschrijving wordt niet weergegeven.
<tr><td>Apparaatgebruik blokkeren totdat alle apps en profielen zijn geïnstalleerd<td>Met de instellingen in deze tabel kan de werking van de pagina Status van de inschrijving worden aangepast, zodat de gebruiker mogelijke installatieproblemen kan oplossen.
<td>De pagina Status van de inschrijving wordt weergegeven zonder extra opties om installatieproblemen op te lossen.
<tr><td>Toestaan dat gebruikers het apparaat opnieuw instellen als er een installatiefout optreedt<td>Er wordt een knop <b>Apparaat opnieuw instellen</b> weergegeven als er een installatieprobleem is.<td>Er wordt geen knop <b>Apparaat opnieuw instellen</b> weergegeven als er een installatieprobleem is.
<tr><td>Toestaan dat gebruikers het apparaat gebruiken als er een installatiefout optreedt<td>Er wordt een knop <b>Toch doorgaan</b> weergegeven als er een installatieprobleem is.<td>Er wordt geen knop <b>Toch doorgaan</b> weergegeven als er een installatieprobleem is.
<tr><td>Een foutbericht voor de tijdslimiet weergeven als de installatie langer duurt dan het opgegeven aantal minuten<td colspan="2">Geef het aantal minuten op dat moet worden gewacht totdat de installatie is voltooid. De standaardwaarde is 60 minuten.
<tr><td>Aangepast bericht weergeven als er een fout optreedt<td>Er wordt een tekstvak weergegeven waarin u een aangepast bericht kunt invoeren dat wordt weergegeven als er een installatiefout optreedt.<td>Dit is het bericht dat standaard wordt weergegeven: <br><b>De installatie heeft de tijdslimiet overschreden die door uw organisatie is ingesteld. Probeer het opnieuw of neem contact op met de IT-ondersteuning voor hulp.<b>
<tr><td>Gebruikers toestaan om logboeken over installatiefouten te verzamelen<td>Als er een installatiefout optreedt, wordt er een knop <b>Logboeken verzamelen</b> weergegeven. <br>Als de gebruiker op deze knop klikt, kunnen ze een locatie kiezen voor het opslaan van het logboekbestand <b>MDMDiagReport.cab</b>.<td>De knop <b>Apparaat opnieuw instellen</b> wordt niet weergegeven als er een installatieprobleem is.
<tr><td>Gebruik van het apparaat blokkeren totdat de vereiste apps zijn geïnstalleerd als deze zijn toegewezen aan de gebruiker/het apparaat<td colspan="2">Kies <b>Alle</b> of <b>Geselecteerd</b>. <br><br>Als u <b>Geselecteerd</b> kiest, wordt er een knop <b>Apps selecteren</b> weergegeven waarmee u kunt kiezen welke apps moeten worden geïnstalleerd voordat het apparaat wordt ingeschakeld.
</table>

## <a name="turn-on-default-enrollment-status-page-for-all-users"></a>De standaardpagina Status van de inschrijving voor alle gebruikers inschakelen

Volg de onderstaande stappen om de pagina Status van de registratie in te schakelen.
 
1. Kies in [Intune](https://aka.ms/intuneportal) **Apparaatinschrijving** > **Windows-inschrijving** > **Pagina Status van de inschrijving**.
2. In de blade **Pagina Status van de inschrijving** kiest u **Standaard** > **Instellingen**.
3. Bij **Voortgang van installatie van app en profiel weergeven** kiest u **Ja**.
4. Kies de andere instellingen die u wilt inschakelen en kies vervolgens **Opslaan**.

## <a name="create-enrollment-status-page-profile-and-assign-to-a-group"></a>Profiel voor pagina Status van de registratie maken en dit aan een groep toewijzen

1. Kies in [Intune](https://aka.ms/intuneportal) **Apparaatinschrijving** > **Windows-inschrijving** > **Pagina Status van de inschrijving** > **Profiel maken**.
2. Geef een **naam** en **beschrijving** op.
3. Kies **Maken**.
4. Kies het nieuwe profiel in de lijst **Pagina Status van de inschrijving**.
5. Kies **Toewijzingen** > **Groepen selecteren** > kies de groepen waarvoor u dit profiel wilt instellen > **Selecteren** > **Opslaan**.
6. Kies **Instellingen** > kies de instellingen die u op dit profiel wilt toepassen > **Opslaan**.

## <a name="set-the-enrollment-status-page-priority"></a>De prioriteit instellen voor de pagina Status van de registratie

Een gebruiker deel uitmaken van verschillende groepen en een groot aantal profielen voor de pagina Status van de inschrijving hebben. U kunt in dergelijke situaties conflicten voorkomen door voor elk profiel een prioriteit in te stellen. Als tijdens het inschrijven iemand meer dan een profiel heeft voor de pagina Status van de inschrijving, wordt alleen het profiel met de hoogste prioriteit toegepast op het apparaat dat wordt ingeschreven.

1. Kies in [Intune](https://aka.ms/intuneportal) **Apparaatinschrijving** > **Windows-inschrijving** > **Pagina Status van de inschrijving**.
2. Beweeg de muisaanwijzer over het profiel in de lijst.
3. Sleep met behulp van de drie verticale puntjes het profiel naar de gewenste positie in de lijst.

## <a name="block-access-to-a-device-until-a-specific-application-is-installed"></a>Toegang blokkeren tot een apparaat tot een bepaalde toepassing is geïnstalleerd

U kunt opgeven welke apps moeten worden geïnstalleerd voordat de gebruiker toegang krijgt tot het bureaublad.

1. Kies in Intune **Apparaatinschrijving** > **Windows-inschrijving** > **Pagina Status van de inschrijving**.
2. Kies een profiel > **Instellingen**.
3. Kies **Ja** bij **Voortgang van installatie van app en profiel weergeven**.
4. Kies **Ja** bij **Apparaatgebruik blokkeren totdat alle apps en profielen zijn geïnstalleerd**.
5. Kies **Geselecteerd** bij **Gebruik van het apparaat blokkeren totdat de vereiste apps zijn geïnstalleerd als deze zijn toegewezen aan de gebruiker/het apparaat**.
6. Kies **Apps selecteren** > kies de apps > **selecteer** > **Opslaan**.

## <a name="enrollment-status-page-tracking-information"></a>Traceringsinformatie op de pagina Status van de inschrijving

Er zijn drie fasen waarvoor gegevens worden bijgehouden op de pagina Status van de inschrijving: voorbereiding van het apparaat, installatie van het apparaat en installatie van het account.

### <a name="device-preparation"></a>Voorbereiding van het apparaat

Deze gegevens worden bijgehouden voor de voorbereiding van het apparaat:
- verklaringen van TPM-sleutels (Trusted Platform Module) (indien van toepassing)
- voortgang van deelnemen aan Azure Active Directory
- inschrijven bij Intune
- installatie van Intune-beheeruitbreidingen

### <a name="device-setup"></a>Installatie van het apparaat

Op de pagina Status van de inschrijving worden de volgende installatie-items van het apparaat bijgehouden (als deze zijn toegewezen aan Alle apparaten of een apparaatgroep waarvan het registrerende apparaat lid is):
- Beveiligingsbeleid
  - Eén configuratieprovider (CSP) voor alle inschrijvingen.
  - Werkelijke CSP's die door Intune zijn geconfigureerd, worden hier niet bijgehouden.
- Toepassingen
  - LOB (Line-of-Business) MSI-apps per apparaat.
  - LOB (Line-of-Business) opslag-apps met installatiecontext = apparaat.
  - Offline opslag- en LOB (Line-of-Business) opslag-apps met installatiecontext = apparaat.
  - Win32-toepassingen (alleen Windows 10 versie 1903 en nieuwer) 
- Connectiviteitsprofielen
  - VPN- of Wi-Fi-profielen die zijn toegewezen aan **Alle apparaten** of een groep apparaten waarvan het apparaat dat wordt geregistreerd lid is, maar alleen voor Autopilot-apparaten
- Certificaatprofielen die zijn toegewezen aan **Alle apparaten** of een groep apparaten waarvan het apparaat dat wordt geregistreerd lid is, maar alleen voor Autopilot-apparaten

### <a name="account-setup"></a>Account instellen
Voor de installatie van het account worden op de pagina Status van de inschrijving de volgende items bijgehouden als deze zijn toegewezen aan de huidige aangemelde gebruiker:
- Beveiligingsbeleid
  - Eén CSP voor alle inschrijvingen.
  - Werkelijke CSP's die door Intune zijn geconfigureerd, worden hier niet bijgehouden.
- Toepassingen
  - LOB (Line-of-Business) MSI-apps per gebruiker die worden toegewezen aan alle apparaten, aan alle gebruikers of aan een gebruikersgroep waarvan de gebruiker die het apparaat inschrijft, lid is.
  - LOB (Line-of-Business) MSI-apps per apparaat die worden toegewezen aan alle gebruikers of aan een gebruikersgroep waarvan de gebruiker die het apparaat inschrijft, lid is.
  - LOB Store-apps, online Store-apps en offline Store-apps die aan een van de volgende objecten zijn toegewezen:
    - Alle apparaten
    - Alle gebruikers
    - Een gebruikersgroep waarvan de gebruiker die het apparaat inschrijft, lid is, met de installatiecontext ingesteld op Gebruiker.
  - Win32-toepassingen (alleen Windows 10 versie 1903 en nieuwer) 
- Connectiviteitsprofielen
  - VPN- of Wi-Fi-profielen die worden toegewezen aan alle gebruikers of aan een gebruikersgroep waarvan de gebruiker die het apparaat inschrijft, lid is.
- Certificaten
  - Certificaatprofielen die worden toegewezen aan alle gebruikers of aan een gebruikersgroep waarvan de gebruiker die het apparaat inschrijft, lid is.

### <a name="troubleshooting"></a>Probleemoplossing
Beste vragen voor probleemoplossing.

- Waarom zijn mijn toepassingen niet geïnstalleerd tijdens de fase Installatie van het apparaat tijdens de implementatie van Autopilot die gebruikmaakt van de pagina Status van de inschrijving?
  - Om er zeker van te zijn dat toepassingen worden geïnstalleerd tijdens de installatiefase van een Autopilot-apparaat, moet u ervoor zorgen dat 
        1. De toepassing is geselecteerd voor het blokkeren van toegang in de lijst met geselecteerde apps
        2. U de toepassingen richt op dezelfde Azure AD-apparaatgroep waaraan uw Autopilot-profiel is toegewezen. 

- Waarom wordt de pagina Status van de inschrijving weergegeven voor implementaties zonder Autopilot, bijvoorbeeld wanneer een gebruiker zich voor de eerste keer aanmeldt op een apparaat dat voor co-beheer is ingeschreven bij Configuration Manager?  
  - Op de pagina Status van de inschrijving wordt de installatiestatus voor alle inschrijvingsmethoden vermeld, met inbegrip van
      - Autopilot
      - co-beheer met Configuration Manager
      - wanneer een nieuwe gebruiker zich voor de eerste keer aanmeldt bij een apparaat waarop het beleid voor de pagina Status van de inschrijving is toegepast

- Hoe kan ik de pagina Status van de inschrijving uitschakelen als deze is geconfigureerd op het apparaat?
  - Het beleid voor de pagina Status van de inschrijving wordt ingesteld op een apparaat op het moment van inschrijving. Als u de pagina Status van de inschrijving wilt uitschakelen, moet u de secties Disable User ESP en Disable Device ESP van de pagina Status van de inschrijving uitschakelen. U kunt dit doen door aangepaste OMA-URI-instellingen te maken met de volgende configuraties.

      Pagina Status van de inschrijving voor gebruikers uitschakelen:

      ```
      Name:  Disable User ESP (choose a name you desire)
      Description:  (enter a description)
      OMA-URI:  ./Vendor/MSFT/DMClient/Provider/MS DM Server/FirstSyncStatus/SkipUserStatusPage
      Data type:  Boolean
      Value:  True 
      ```
      Pagina Status van de inschrijving voor apparaten uitschakelen:

      ```
      Name:  Disable Device ESP (choose a name you desire)
      Description:  (enter a description)
      OMA-URI:  ./Vendor/MSFT/DMClient/Provider/MS DM Server/FirstSyncStatus/SkipDeviceStatusPage
      Data type:  Boolean
      Value:  True 
      ```
- Hoe kan ik logboekbestanden verzamelen?
  - Er zijn twee manieren om logboekbestanden te verzamelen voor de pagina Status van de inschrijving:
      - Schakel in het ESP-beleid de mogelijkheid voor gebruikers in om logboeken te verzamelen. Wanneer er een time-out optreedt op de pagina Status van de inschrijving, kan de eindgebruiker de optie **Logboeken verzamelen** kiezen. Door een USB-stick te plaatsen, kunnen de logboekbestanden worden gekopieerd.
      - Open een opdrachtprompt met Shift-F10 en voer vervolgens de volgende opdrachtregel in om logboekbestanden te genereren: 

      ```
      mdmdiagnosticstool.exe -area Autopilot -cab <pathToOutputCabFile>.cab 
      ```

### <a name="known-issues"></a>Bekende problemen
Hieronder worden enkele bekende problemen beschreven. 
- Als u het ESP-profiel uitschakelt, blijft het ESP-beleid van kracht op apparaten en zien gebruikers nog steeds de pagina Status van de inschrijving wanneer ze zich voor de eerste keer aanmelden bij het apparaat. Het beleid wordt niet verwijderd wanneer het ESP-profiel wordt uitgeschakeld. U moet OMA-URI implementeren om de pagina Status van de inschrijving uit te schakelen. Hierboven vindt u instructies voor het uitschakelen van de pagina Status van de inschrijving met OMA-URI. 
- Als er een aanvraag voor het opnieuw opstarten van het apparaat in behandeling is, treedt er altijd een time-out op. De time-out treedt op omdat het apparaat opnieuw moet worden opgestart. Opnieuw opstarten is nodig om tijd te bieden voor het voltooien van het item dat wordt bijgehouden op de pagina Status van de inschrijving. Als het apparaat opnieuw wordt opgestart, wordt de pagina Status van de inschrijving afgesloten en na het opnieuw opstarten wordt niet de pagina voor accountinstallatie weergegeven.  U kunt overwegen opnieuw opstarten achterwege te laten bij de installatie van een toepassing. 
- Opnieuw opstarten tijdens apparaatinstallatie dwingt de gebruiker om referenties in te voeren voordat de fase voor installatie van het account wordt ingegaan. Gebruikersreferenties blijven niet behouden tijdens het opnieuw opstarten. Laat de gebruiker zijn of haar referenties invoeren, waarna de pagina Status van de inschrijving wordt weergegeven. 
- SCEP-certificaten met beleid van Windows Hello voor Bedrijven veroorzaken een time-out omdat de gebruiker de configuratie van de Hello-pincode niet kan voltooien om de installatie van het SCEP-certificaat af te ronden.  Er is geen tijdelijke oplossing. Naar verwachting zal het probleem in de zomer van 2019 zijn opgelost. 
- Er treedt altijd een time-out op voor de pagina Status van de inschrijving tijdens een inschrijving met Werk- en schoolaccount toevoegen in Windows 10-versie 1903 en lager. De pagina Status van de inschrijving wacht totdat de Azure AD-registratie is voltooid. Het probleem is opgelost in Windows 10-versie 1903 en hoger.  
- Hybride Azure AD Auto Pilot-implementatie met ESP duurt langer dan de time-outperiode die is gedefinieerd in het ESP-profiel. Bij hybride Azure AD Auto Pilot-implementaties duurt de ESP 40 minuten langer dan de waarde die is ingesteld in het ESP-profiel. Deze vertraging geeft de on-premises AD-connector tijd om de nieuwe apparaatrecord te maken in Azure AD. 
- De Windows-aanmeldingspagina wordt niet vooraf ingevuld met de gebruikersnaam in de modus Op basis van gebruiker van Autopilot. Als het apparaat opnieuw wordt opgestart tijdens de installatiefase van het apparaat van ESP, gebeurt het volgende:
    - de gebruikersreferenties blijven niet behouden
    - de gebruiker moet de referenties opnieuw invoeren voordat de installatie van het apparaat kan worden gevolgd door de installatie van het account
- De ESP wordt erg lang weergegeven of de identificatiefase wordt nooit voltooid. In Intune worden de ESP-beleidsregels berekend tijdens de identificatiefase. De kans bestaat dat een apparaat nooit de ESP-beleidsregels kan berekenen als aan de huidige gebruiker geen Intune-licentie is toegewezen.  
- De configuratie van Windows Defender Application Control heeft tot gevolg dat tijdens Autopilot een verzoek wordt weergegeven om het apparaat opnieuw op te starten. Het configureren van Windows Defender Application (AppLocker CSP) vereist opnieuw opstarten. Wanneer dit beleid is geconfigureerd, kan dit ertoe leiden dat het apparaat opnieuw wordt opgestart tijdens Autopilot. Op dit moment is er geen manier om het opnieuw opstarten te onderdrukken of uit te stellen.
- Als het DeviceLock-beleid (https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock) ) is ingeschakeld als onderdeel van een ESP-profiel, kan de OOBE of het automatisch aanmelden bij het bureaublad van de gebruiker om twee redenen onverwacht mislukken.
  - Als het apparaat niet opnieuw is opgestart vóór de ESP-installatiefase van het apparaat, wordt de gebruiker mogelijk gevraagd om Azure AD-referenties in te voeren. Deze vraag wordt gesteld in plaats van een geslaagde automatische aanmelding waarbij de gebruiker de eerste aanmeldingsanimatie van Windows ziet.
  - De automatische aanmelding mislukt als het apparaat opnieuw is opgestart nadat de gebruiker Azure AD-referenties heeft ingevoerd, maar voordat de ESP-installatiefase van het apparaat is afgesloten. Deze fout treedt op omdat de ESP-installatiefase van het apparaat nooit is voltooid. De tijdelijke oplossing is om het apparaat opnieuw in te stellen.

## <a name="next-steps"></a>Volgende stappen
Nadat u Windows-inschrijvingspagina's hebt ingesteld, kunt u leren hoe u Windows-apparaten beheert. Zie [Wat is Microsoft Intune-apparaatbeheer?](../remote-actions/device-management.md) voor meer informatie.
