---
title: Intune-beveiligingsbasislijninstellingen voor Windows 10
titleSuffix: Microsoft Intune
description: Intune-beveiligingsbasislijninstellingen voor het beheer van Windows 10
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/20/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d3b9f69e745baffd21b55274e173bb75e8581525
ms.sourcegitcommit: 690e680e854b7d707421c5e06f134e493f4f4194
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/27/2019
ms.locfileid: "67418943"
---
# <a name="mdm-security-baseline-settings-for-intune"></a>MDM-beveiligingsbasislijninstellingen voor Intune  

Bekijk de MDM security basislijn-instellingen die worden ondersteund door Microsoft Intune voor apparaten met Windows 10 of hoger. De standaardwaarden voor instellingen in deze basislijn vertegenwoordigen de aanbevolen configuratie voor de toepasselijke apparaten, en mogelijk niet overeen met de standaardinstellingen van de basislijn van andere basisbeveiliging.  

De meest recente versie van de basislijn is **MDM basisbeveiliging voor Spring 2019 Update (19 uur 1)**  

Zie voor meer informatie over wat er gewijzigd in de meest recente versie van deze basislijn van de vorige versie, [wat er gewijzigd in de nieuwe sjabloon](#whats-changed-in-the-new-template).  

> [!NOTE]  
> In juni 2019, de Preview-versie MDM-basisbeveiliging is vervangen door de versie van de *MDM basisbeveiliging voor Spring 2019 Update (19 uur 1)* sjabloon, waarmee generaly beschikbaar (niet in de Preview-versie). Profielen die zijn gemaakt vóór de beschikbaarheid van de *MDM basisbeveiliging voor Spring 2019 Update (19 uur 1)* basislijn niet bijwerken om weer te geven de de instellingen en waarden die zich in de MDM-basisbeveiliging voor Spring 2019 Update () 19 uur 1) versie.  U kunt maar u kunt geen nieuwe profielen op basis van de preview-sjabloon maken, bewerken en echter ook doorgaan met profielen die u eerder hebt gemaakt en die zijn gebaseerd op de preview-sjabloon.   
  
Zie voor meer informatie over het gebruik van basisbeveiliging met Intune, [security basislijnen gebruiken](security-baselines.md).  


   
## <a name="above-lock"></a>Vergrendeling boven  
Zie [Beleids-CSP - AboveLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock) in de Windows-documentatie voor meer informatie.  

- **Weergave van toast-meldingen blokkeren**  
  Met deze beleidsinstelling kunt u voorkomen dat app-meldingen in het vergrendelingsscherm worden weergegeven. Als u deze beleidsinstelling inschakelt, worden geen app-meldingen weergegeven op het vergrendelingsscherm. Als u deze beleidsinstelling uitschakelt of niet configureert, kunnen gebruikers kiezen voor welke app meldingen op het vergrendelingsscherm worden weergegeven.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067101)  

  **Standaardinstelling**: Ja  

- **Voice-mailapps vergrendeld scherm activeren**  

  **Standaardinstelling**: uitgeschakeld

## <a name="app-runtime"></a>App-runtime    
Zie [Beleids-CSP - AppRuntime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-appruntime
) in de Windows-documentatie voor meer informatie.  

- **Optionele Microsoft-accounts voor Windows Store-apps**  
  Met deze beleidsinstelling kunt u regelen of Microsoft-accounts optioneel zijn voor Windows Store-apps waarvoor gebruikers een account nodig hebben om zich aan melden. Dit beleid heeft alleen invloed op Windows Store-apps die deze functie ondersteunen. Als u deze beleidsinstelling inschakelt, kunnen gebruikers zich aanmelden met een bedrijfsaccount bij Windows Store-apps waarvoor ze normaalgesproken een Microsoft-account nodig hebben om zich aan te melden. Als u deze beleidsinstelling uitschakelt of niet configureert, moeten gebruikers zich aanmelden met een Microsoft-account.  
    [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067104)  
  
  **Standaardinstelling**: ingeschakeld  

## <a name="application-management"></a>Toepassingsbeheer   
Zie [Beleids-CSP - ApplicationManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement) in de Windows-documentatie voor meer informatie.  

- **Controle van de gebruiker blokkeren over installaties**  
  Met deze beleidsinstelling kan gebruikers om installatieopties die gewoonlijk alleen beschikbaar voor systeembeheerders zijn te wijzigen. Als u deze beleidsinstelling inschakelt, zijn sommige van de beveiligingsfuncties van Windows Installer omzeild. U kunt hiermee installaties om uit te voeren die anders zouden worden afgebroken vanwege een beveiligingsfout. Als u deze beleidsinstelling niet configureert of uitschakelt, de beveiligingsfuncties van Windows Installer te voorkomen dat gebruikers wijzigen van opties voor de installatie normaal gesproken is gereserveerd voor systeembeheerders, zoals het opgeven van de map waarin bestanden worden geïnstalleerd. Als Windows-installatieprogramma detecteert dat een installatiepakket voor de gebruiker te wijzigen van een beveiligde optie is toegestaan, wordt de installatie gestopt en wordt een bericht weergegeven. Deze beveiligingsfuncties werken alleen als het installatieprogramma wordt uitgevoerd in een beveiligingscontext waarin het toegang tot mappen geweigerd voor de gebruiker heeft. Met deze beleidsinstelling is ontworpen voor minder beperkende omgevingen. Het kan worden gebruikt om fouten in een installatieprogramma dat verhindert dat de software wordt geïnstalleerd te omzeilen.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067060)  

    **Standaardinstelling**: Ja

- **Blok-MSI-app-installaties met verhoogde bevoegdheden**  
  Deze beleidsinstelling geeft Windows Installer de opdracht om verhoogde bevoegdheden te gebruiken wanneer een programma op een systeem wordt geïnstalleerd.  
  - *Als u deze beleidsinstelling inschakelt*, bevoegdheden worden uitgebreid naar alle programma's. Deze rechten zijn meestal gereserveerd voor programma's die zijn toegewezen aan de gebruiker (aangeboden op het bureaublad), die worden toegewezen aan de computer (automatisch geïnstalleerd) f, of beschikbaar gesteld in software in het Configuratiescherm. Dit profiel bepaalt u of gebruikers die programma's die toegang tot mappen vereisen die de gebruiker niet gemachtigd om te bekijken of wijzigen, met inbegrip van mappen op zeer beperkte computers te installeren.
  - *Als u uitschakelt of niet met deze beleidsinstelling configureert*, het systeem de machtigingen van de huidige gebruiker is van toepassing wanneer het programma's die niet worden gedistribueerd of aangeboden door een systeembeheerder wordt geïnstalleerd. Opmerking: deze beleidsinstelling wordt zowel in de map Computerconfiguratie als Gebruikersconfiguratie weergegeven. Als u wilt deze beleidsinstelling doorvoeren, moet u het inschakelen in beide mappen. Let op: Ervaren gebruikers kunnen profiteren van de machtigingen verleent aan hun bevoegdheden wijzigen en permanente toegang krijgen tot beperkte bestanden en mappen van deze beleidsinstelling. Houd er rekening mee dat de versie van de configuratie van de gebruiker van deze instelling kan niet worden gegarandeerd om te beveiligen.  
  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067134)    

  **Standaardinstelling**: Ja

- **Game DVR blokkeren (alleen desktop)**  
  Hiermee bepaalt u of het opnemen en uitzenden van games is toegestaan.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067056)  
  
  **Standaardinstelling**: Ja  

## <a name="auto-play"></a>Automatisch afspelen   
Zie [Beleids-CSP - Automatisch afspelen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-autoplay) in de Windows-documentatie voor meer informatie.  

- **Automatisch afspelen: standaardgedrag voor AutoRun**  
  Deze instelling beïnvloedt het standaardgedrag voor AutoRun-opdrachten. AutoRun-opdrachten worden opgeslagen in AutoRun.inf-bestanden en kunnen worden gebruikt voor het starten van installatieprogramma's of andere routines. Wanneer deze optie is *ingeschakeld*, kunnen beheerders het standaardgedrag van AutoRun wijzigen op een apparaat waarop Windows Vista of later wordt uitgevoerd. Gedrag kan worden ingesteld op: a) AutoRun-opdrachten volledig uitschakelen, of b) terugzetten naar gedrag voordat Windows Vista werd uitgevoerd, waarbij de AutoRun-opdracht automatisch werd uitgevoerd. Wanneer deze optie is ingesteld op *Uitgeschakeld* of *Niet geconfigureerd*,worden gebruikers op apparaten waarop Windows Vista of later wordt uitgevoerd, gevraagd om een AutoRun-opdracht moet worden uitgevoerd.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067133)       
  
  **Standaardinstelling**: Niet uitvoeren  
  
- **De modus Automatisch afspelen**  
  Met deze beleidsinstelling kunt u de functie Automatisch afspelen uitschakelen. Met Automatisch afspelen worden gegevens van een station afgelezen zodra u media in het station plaatst. Hierdoor worden installatiebestanden van programma's direct uitgevoerd en wordt muziek op audiomedia direct afgespeeld. Vóór Windows XP SP2 werd Automatisch afspelen standaard uitgeschakeld op losse stations, zoals het floppydiskstation (maar niet het cd-rom-station) en op netwerkstations. Vanaf Windows XP SP2 is Automatisch afspelen ook ingeschakeld voor losse stations, waaronder zip-stations en een aantal USB-apparaten voor massaopslag. Als u deze beleidsinstelling inschakelt, wordt Automatisch afspelen uitgeschakeld op cd-rom-stations en losse mediastations, of uitgeschakeld op alle stations. Met deze beleidsinstelling wordt Automatisch afspelen op andere stationstypen uitgeschakeld. U kunt deze instelling niet gebruiken voor het uitschakelen van Automatisch afspelen op stations waarop deze functie standaard is uitgeschakeld. Als u deze beleidsinstelling uitschakelt of niet configureert, wordt automatisch afspelen ingeschakeld. Opmerking: deze beleidsinstelling wordt zowel in de map Computerconfiguratie als Gebruikersconfiguratie weergegeven. Als de beleidsinstellingen conflicteren, heeft de beleidsinstelling in Computerconfiguratie een hogere prioriteit dan de beleidsinstelling in Gebruikersconfiguratie.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2066793)  
  
  **Standaardinstelling**: uitgeschakeld

- **Automatisch afspelen voor apparaten zonder volume blokkeren**  
  Met deze beleidsinstelling is Automatisch afspelen niet toegestaan voor MTP-apparaten zoals camera's of telefoons. Als u deze beleidsinstelling inschakelt, is Automatisch afspelen niet toegestaan voor MTP-apparaten zoals camera's of telefoons. Als u deze beleidsinstelling uitschakelt of niet configureert, wordt Automatisch afspelen ingeschakeld voor apparaten zonder volume.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067106)    
  
  **Standaardinstelling**: ingeschakeld  

## <a name="bitlocker"></a>Bitlocker    
Zie [Beleids-CSP - Bitlocker](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bitlocker
) in de Windows-documentatie voor meer informatie.  

- **Bitlocker-beleid voor losse stations**  
  Deze beleidsinstelling wordt gebruikt om de versleutelingsmethode en coderingssterkte te regelen. De waarden van dit beleid bepalen de coderingssterkte die door BitLocker wordt gebruikt voor versleuteling. Ondernemingen kunnen het versleutelingsniveau bepalen voor extra beveiliging (AES-256 is sterker dan AES-128). Als u deze instelling inschakelt, kunt u afzonderlijke versleutelingsalgoritmen en belangrijke coderingssterkten configureren voor vaste gegevensstations, besturingssysteemstations en losse gegevensstations. Voor vaste stations en besturingssysteemstations wordt het gebruik van het XTS-AES-algoritme aanbevolen. Gebruik 128-bits AES-CBC of 256-bits AES-CBC voor losse stations als het station in andere apparaten wordt gebruikt waarop geen Windows 10, versie 1511 of later wordt uitgevoerd. Het wijzigen van de versleutelingsmethode heeft geen invloed als het station al is versleuteld of als de versleuteling nog wordt uitgevoerd. In deze gevallen wordt deze beleidsinstelling genegeerd.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067140) 

  Voor het BitLocker-beleid voor verwisselbare stations moet u de volgende instelling configureren:

    - **Versleuteling vereisen voor schrijftoegang**  
      **Standaardinstelling**: Ja  
  

## <a name="browser"></a>Browser  
Zie [Beleids-CSP - Browser](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser) in de Windows-documentatie voor meer informatie.  

- **SmartScreen vereisen voor Microsoft Edge**  
  Microsoft Edge gebruikt standaard Windows Defender SmartScreen (ingeschakeld) om gebruikers tegen mogelijke oplichting door phishing en schadelijke software te beschermen. Bovendien kunnen gebruikers Windows Defender SmartScreen standaard niet uitschakelen (uitzetten). Als u dit beleid inschakelt, wordt Windows Defender SmartScreen uitgeschakeld en kunnen gebruikers deze functie niet inschakelen. Configureer dit beleid niet als u gebruikers Windows Defender SmartScreen zelf wilt kunnen laten in- of uitschakelen.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067029)   
  
  **Standaardinstelling**: Ja  
  
- **Toegang tot schadelijke sites blokkeren**  
  Standaard hebben gebruikers in Microsoft Edge toestemming om de Windows Defender SmartScreen-waarschuwingen over mogelijke schadelijke websites te omzeilen (negeren), zodat ze de site kunnen blijven gebruiken. Met dit beleid kunt u Microsoft Edge echter zo configureren dat gebruikers de waarschuwingen niet kunnen omzeilen, waardoor ze de website dus niet langer kunnen gebruiken.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067040)   
  
  **Standaardinstelling**: Ja  
  
- **Downloaden van niet-geverifieerde bestanden blokkeren**  
  Standaard hebben gebruikers in Microsoft Edge toestemming om de Windows Defender SmartScreen-waarschuwingen over mogelijk schadelijke bestanden te omzeilen (negeren), waardoor ze de niet-geverifieerde bestanden kunnen blijven downloaden. Als u dit beleid inschakelt, voorkomt u dat gebruikers de waarschuwingen kunnen omzeilen, waardoor ze de niet-geverifieerde bestanden niet meer kunnen downloaden.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067023)  
  
  **Standaardinstelling**: Ja  
  
- **Wachtwoordbeheer blokkeren**  
  Standaard gebruikt Microsoft Edge Wachtwoordbeheer automatisch, waardoor gebruikers wachtwoorden lokaal kunnen beheren. Als u dit beleid uitschakelt, voorkomt u dat Microsoft Edge Wachtwoordbeheer kan gebruiken. Configureer dit beleid niet als u gebruikers wilt laten kiezen om wachtwoorden lokaal te laten opslaan en beheren met Wachtwoordbeheer.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067128)  
  
  **Standaardinstelling**: Ja  
  
- **Overschrijving van certificaatfouten voorkomen**  
  Deze beleidsinstelling voorkomt dat gebruikers fouten in het SSL/TLS-certificaat (Secure Sockets Layer/Transport Layer Security) negeren die het bladeren in Internet Explorer onderbreken (zoals 'verlopen', 'ingetrokken' of 'namen komen niet overeen'). Als u deze beleidsinstelling inschakelt, kan de gebruiker niet doorgaan met bladeren. Als u deze beleidsinstelling uitschakelt of niet configureert, kan de gebruiker kiezen certificaatfouten te negeren en doorgaan met bladeren.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067126)  
  
  **Standaardinstelling**: Ja  

## <a name="connectivity"></a>Connectiviteit  
Zie [Beleids-CSP - Connectiviteit](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity) in de Windows-documentatie voor meer informatie.  

- **Internetdownloads voor de wizards Webpublicaties en Online bestellen blokkeren**  
  Dit beleid bepaalt of Windows moet worden gebruikt voor het downloaden van een lijst met providers voor de wizards Webpublicaties en Online bestellen. Met deze wizards kunnen gebruikers in een lijst met bedrijven een bedrijf selecteren dat services als onlineopslag en het afdrukken van foto's biedt. Standaard worden zowel bedrijven weergegeven die zijn gedownload van een Windows-website als bedrijven die zijn opgegeven in het register. Als u deze beleidsinstelling inschakelt, worden geen providers gedownload en worden alleen de serviceproviders weergegeven die in het cachegeheugen van het lokale register zijn opgeslagen. Als u deze beleidsinstelling uitschakelt of niet configureert, wordt een lijst met providers gedownload wanneer de gebruiker de wizards Publiceren op internet of Online bestellen gebruikt. Zie de documentatie voor de wizards Publiceren op internet of Online bestellen voor meer informatie over bijvoorbeeld het opgeven van serviceproviders in het register.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067136)  
  
  **Standaardinstelling**: ingeschakeld  

- **Downloaden van printerstuurprogramma's via HTTP blokkeren**  
  Met deze beleidsinstelling geeft u aan of deze client afdrukstuurprogrammapakketten via HTTP mag downloaden. Als u afdrukken via HTTP wilt instellen, moeten stuurprogramma's die niet in de inbox staan via HTTP worden gedownload. Opmerking: met deze beleidsinstelling wordt niet voorkomen dat de client via HTTP kan afdrukken naar printers op intranet of internet. U voorkomt hiermee alleen dat er stuurprogramma's worden gedownload die niet al lokaal zijn geïnstalleerd. Als u deze beleidsinstelling inschakelt, kunnen printerstuurprogramma's niet via HTTP worden gedownload. Als u deze beleidsinstelling uitschakelt of niet configureert, kunnen gebruikers printerstuurprogramma's via HTTP downloaden.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067141)  
  
  **Standaardinstelling**: ingeschakeld  

## <a name="credentials-delegation"></a>CredentialsDelegation  
Zie [Beleids-CSP - CredentialsDelegation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsdelegation
) in de Windows-documentatie voor meer informatie.  

- **Delegatie van externe host van aanmeldingsgegevens die niet kunnen worden geëxporteerd**  
  Met een externe host staat u toe dat aanmeldingsgegevens die niet kunnen worden geëxporteerd, kunnen worden gedelegeerd. Wanneer u overdracht van referenties gebruikt, leveren apparaten een exporteerbare versie van referenties aan de externe host, waarmee gebruikers het risico lopen op diefstal van referenties door aanvallers op de externe host. Als u deze beleidsinstelling inschakelt, biedt de host ondersteuning voor de modi Beperkt beheer of Externe Credential Guard. Als u deze beleidsinstelling uitschakelt of niet configureert, worden de modi Beperkt beheer of Externe Credential Guard niet ondersteund. De gebruiker moet zijn of haar aanmeldingsgegevens altijd doorgeven aan de host.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067103)   
  
  **Standaardinstelling**: ingeschakeld  

## <a name="credentials-ui"></a>Referenties gebruikersinterface  
Zie [Beleids-CSP - CredentialsUI](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsui) in de Windows-documentatie voor meer informatie.  

- **Beheerders opsommen** Met deze beleidsinstelling bepaalt u of beheerdersaccounts worden weergegeven wanneer een gebruiker een toepassing die wordt uitgevoerd probeert uit te breiden. Standaard worden beheerdersaccounts niet weergegeven wanneer de gebruiker een toepassing die wordt uitgevoerd probeert uit te breiden. Als u deze beleidsinstelling inschakelt, worden alle lokale beheerdersaccounts op de pc weergegeven zodat de gebruiker één account kan kiezen en het juiste wachtwoord kan invoeren. Als u deze beleidsinstelling uitschakelt, zijn gebruikers altijd vereist om een gebruikersnaam en wachtwoord in te voeren om toepassingen uit te breiden.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067021)

  
  **Standaardinstelling**: uitgeschakeld  

## <a name="data-protection"></a>Gegevensbescherming  
Zie [Beleids-CSP - DataProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection
) in de Windows-documentatie voor meer informatie.  

- **Direct Memory Access blokkeren**  
  Met deze beleidsinstelling kunt u Direct Memory Access (DMA) blokkeren voor alle hot-pluggable PCI-downstream-poorten totdat een gebruiker zich bij Windows aanmeldt. Zodra een gebruiker zich heeft aangemeld, somt Windows de PCI-apparaten op die met de PCI-poorten van de host zijn verbonden. Steeds wanneer de gebruiker het apparaat vergrendelt, wordt DMA geblokkeerd op hot-pluggable PCI-poorten zonder onderliggende apparaten totdat de gebruiker zich opnieuw aanmeldt. Apparaten die al waren geïnventariseerd toen het apparaat was ontgrendeld, blijven werken totdat ze worden losgekoppeld. Deze beleidsinstelling wordt uitsluitend afgedwongen wanneer BitLocker of apparaatversleuteling is ingeschakeld.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067031)     
  
  **Standaardinstelling**: Ja  

## <a name="device-guard"></a>Device Guard  
Zie [Beleids-CSP - DeviceGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceguard
) in de Windows-documentatie voor meer informatie.  

- **Credential Guard**  
  Met deze instelling kunnen gebruikers Credential Guard inschakelen met op virtualisatie gebaseerde beveiliging om aanmeldingsgegevens bij opnieuw opstarten te beschermen.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067044)
   
  **Standaardinstelling**: Inschakelen met UEFI-vergrendeling 

- **Beveiliging op basis van virtualisatie inschakelen**   
  Met deze optie wordt Beveiliging op basis van virtualisatie (VBS) ingeschakeld bij de volgende keer opnieuw opstarten. Beveiliging op basis van virtualisatie maakt gebruik van de Windows-Hypervisor om ondersteuning te bieden voor beveiligingsservices.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067066)  
  
  **Standaardinstelling**: Ja  


- **SystemGuard starten**    
  **Standaardinstelling**: ingeschakeld  

## <a name="device-installation"></a>Apparaatinstallatie  
Zie [Beleids-CSP - apparaatinstallatie](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation) in de Windows-documentatie voor meer informatie.  

- **Installatie van hardwareapparaten op basis van apparaat-id's**  
  Met deze beleidsinstelling kunt u een lijst opgeven met Plug en Play-hardware id's en compatibele id's voor apparaten die niet mogen worden geïnstalleerd in Windows. Deze beleidsinstelling heeft een hogere prioriteit dan welke andere beleidsinstelling dan ook waarmee Windows wordt toegestaan een apparaat te installeren. Als u deze beleidsinstelling inschakelt, kunnen apparaten waarvan de hardware-id of compatibele id die in de door u gemaakte lijst staan, niet worden geïnstalleerd in Windows. Als u deze beleidsinstelling inschakelt op een externe desktopserver, heeft deze invloed op de omleiding van de opgegeven apparaten van een externe desktopclient naar de externe desktopserver. Als u deze beleidsinstelling uitschakelt of niet configureert, kunnen apparaten worden geïnstalleerd of bijgewerkt, voor zover dat door andere beleidsinstellingen is toegestaan of verboden.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2066794)  
  
  **Standaardinstelling**: installatie van hardwareapparaten blokkeren  

    Wanneer *installatie van hardwareapparaten blokkeren* wordt geselecteerd, zijn de volgende instellingen beschikbaar.
  
    - **Overeenkomende hardwareapparaten verwijderen**   
    Deze instelling is alleen beschikbaar als *Installatie hardwareapparaten op apparaat-id* is ingesteld op *Installatie van hardwareapparaten blokkeren*.
      
      **Standaardinstelling**: Ja
  
    - **Hardwareapparaat-id's die zijn geblokkeerd**  
       Deze instelling is alleen beschikbaar als *Installatie hardwareapparaten op apparaat-id* is ingesteld op *Installatie van hardwareapparaten blokkeren*.
      
      **Standaardinstelling**: Ja  
  
- **Installatie van hardwareapparaten op basis van installatieklassen**  
  Met deze beleidsinstelling kunt u een lijst opgeven met GUID's (Globally Unique Identifiers) voor de installatieklasse van apparaten voor apparaatstuurprogramma's die niet mogen worden geïnstalleerd in Windows. Deze beleidsinstelling heeft een hogere prioriteit dan welke andere beleidsinstelling dan ook waarmee Windows wordt toegestaan een apparaat te installeren. Als u deze beleidsinstelling inschakelt, mogen apparaatstuurprogramma's waarvan de GUID's voor de installatieklasse van apparaten niet in de door u gemaakte lijst staan, niet worden geïnstalleerd of bijgewerkt in Windows. Als u deze beleidsinstelling inschakelt op een externe desktopserver, heeft deze invloed op de omleiding van de opgegeven apparaten van een externe desktopclient naar de externe desktopserver. Als u deze beleidsinstelling uitschakelt of niet configureert, kan Windows apparaten installeren en bijwerken, voor zover dat door andere beleidsinstellingen is toegestaan of verboden.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067048)  
  
  **Standaardinstelling**: installatie van hardwareapparaten blokkeren  

    Wanneer *installatie van hardwareapparaten blokkeren* wordt geselecteerd, zijn de volgende instellingen beschikbaar.
    - **Overeenkomende hardwareapparaten verwijderen**    
    Deze instelling is alleen beschikbaar wanneer *Installatie hardwareapparaten op installatieklasse* is ingesteld op *Installatie van hardwareapparaten blokkeren*.  

      **Standaardinstelling**: *Geen standaardconfiguratie*  
  
    - **Hardwareapparaat-id's die zijn geblokkeerd**  
      Deze instelling is alleen beschikbaar wanneer *Installatie hardwareapparaten op installatieklasse* is ingesteld op *Installatie van hardwareapparaten blokkeren*.
      
      **Standaardinstelling**: *Geen standaardconfiguratie*  

## <a name="device-lock"></a>Apparaatvergrendeling  
Zie [Beleids-CSP - DeviceLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock) in de Windows-documentatie voor meer informatie.  

- **Gebruik van de camera voorkomen**  
  Hiermee schakelt u schakelaar voor de camera op het vergrendelingsscherm uit bij de pc-instellingen en voorkomt u dat een camera op het vergrendelingsscherm kan worden aangeroepen. Standaard kunnen gebruikers het aanroepen van een beschikbare camera op het vergrendelingsscherm zelf inschakelen. Als u deze instelling inschakelt, kunnen gebruikers cameratoegang via het vergrendelingsscherm camera niet langer in- of uitschakelen bij de pc-instellingen en kan de camera niet worden aangeroepen op het vergrendelingsscherm.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067052)
  
  **Standaardinstelling**: ingeschakeld  

- **Wachtwoord vereisen**  
  Hiermee geeft u aan of apparaatvergrendeling is ingeschakeld.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067049)  
  
  **Standaardinstelling**: Ja  
  
    Wanneer *Wachtwoord vereisen* is ingesteld op *Ja*, zijn de volgende instellingen beschikbaar.

    - **Wachtwoord: minimumaantal tekensets**  
      Het aantal complexe elementtypen (hoofdletters en kleine letters, cijfers en leestekens) dat is vereist voor een sterke pincode of een sterk wachtwoord. Pincodes leiden tot het volgende gedrag op computers en mobiele apparaten: 1 - Alleen cijfers 2 - Cijfers en kleine letters zijn vereist 3 - Cijfers, kleine letters en hoofdletters zijn vereist. Niet ondersteund in Microsoft-desktopaccounts en domeinaccounts. 4 - Cijfers, kleine letters, hoofdletters en speciale tekens zijn vereist. Dit wordt niet ondersteund in desktop. De standaardwaarde is 1.  
      [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067055)  
      
      **Standaardinstelling**: 3  
  
    - **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**  
      Het aantal verificatiefouten dat is toegestaan voordat het apparaat wordt gewist. Met de waarde 0 wordt de wisfunctionaliteit van het apparaat uitgeschakeld.  
      [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067030)  
        
      **Standaard**: 10  
  
    - **Dagen tot wachtwoord verloopt**  
      Met de beleidsinstelling Maximale wachtwoordduur bepaalt u hoe lang (in dagen) een wachtwoord kan worden gebruikt voordat de gebruiker dit moet wijzigen. U kunt instellen dat wachtwoorden na een aantal dagen tussen 1 en 999 verlopen, of u kunt opgeven dat wachtwoorden nooit verlopen door het aantal dagen in te stellen op 0. Als de Maximale wachtwoordduur tussen 1 en 999 dagen ligt, moet de Minimale wachtwoordduur minder zijn dan de Maximale wachtwoordduur. Als Maximale wachtwoordduur is ingesteld op 0, kan Minimale wachtwoordduur op elke waarde tussen 0 en 998 dagen worden ingesteld.  
      [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067028)  
      
      **Standaardinstelling**: 60  
  
    - **Vereist wachtwoordtype**  
      Hiermee bepaalt u het type pincode of wachtwoord dat is vereist.  
      [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067027)  
      
      **Standaardinstelling**: Alfanumeriek  
  
    - **Minimale wachtwoordlengte**  
      Met de beleidsinstelling Minimale wachtwoordlengte bepaalt u het minimumaantal tekens waaruit een wachtwoord voor een gebruikersaccount mag bestaan. U kunt een waarde tussen 1 en 14 tekens instellen, of u kunt instellen dat er geen wachtwoord is vereist door het aantal tekens in te stellen 0.  
      [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067024)  
      
      **Standaardinstelling**: 8  
  
    - **Eenvoudige wachtwoorden blokkeren**  
      Hiermee geeft u aan of pincodes of wachtwoorden zoals '1111' en '1234' zijn toegestaan. Voor de desktop bepaalt u hiermee ook of afbeeldingswachtwoorden mogen worden gebruikt.  
      [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067127) 
      
      **Standaardinstelling**: Ja  
        *Wanneer u deze optie instelt op Ja mogen eenvoudige wachtwoorden niet worden gebruikt.* 

  - **Wachtwoorden niet opnieuw gebruiken**  
    Hiermee geeft u op hoeveel wachtwoorden in de geschiedenis kunnen worden opgeslagen die niet mogen worden gebruikt. De waarde bevat ook het huidige wachtwoord van de gebruiker. Met de instelling *1* kan de gebruiker bijvoorbeeld zijn huidige wachtwoord niet opnieuw gebruiken bij het kiezen van een nieuw wachtwoord. De instelling *5* betekent een gebruiker zijn nieuwe wachtwoord niet kan instellen op zijn huidige wachtwoord of een van zijn vier wachtwoorden daarvoor.  
    [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2066795)  
    
    **Standaardinstelling**: 24  

- **Diavoorstelling voorkomen**  
  Hiermee schakelt u de instellingen voor een diavoorstelling op het vergrendelingsscherm bij de pc-instellingen uit en voorkomt u dat een diavoorstelling op het vergrendelingsscherm wordt afgespeeld. Standaard kunnen gebruikers een diavoorstelling inschakelen die wordt uitgevoerd nadat ze het apparaat vergrendelen. Als u deze instelling inschakelt, kunnen gebruikers geen instellingen voor diavoorstellingen bij de pc-instellingen aanpassen en kan er geen diavoorstelling worden gestart.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067105) 
  
  **Standaardinstelling**: ingeschakeld  
  *De instelling Ingeschakeld voorkomt dat diavoorstellingen worden uitgevoerd.* 

- **Minimale wachtwoordduur in dagen**  
  Met de beleidsinstelling Minimale wachtwoordduur bepaalt u de periode (in dagen) dat een wachtwoord moet worden gebruikt voordat de gebruiker dit kan wijzigen. U kunt een waarde tussen 1 en 998 dagen instellen, of u kunt toestaan dat wachtwoorden direct worden gewijzigd door het aantal dagen in te stellen op 0. De Minimale wachtwoordduur moet korter zijn dan de Maximale wachtwoordduur, tenzij de Maximale wachtwoordduur is ingesteld op 0, waarmee u aangeeft dat die wachtwoorden nooit verlopen. Als de Maximale wachtwoordduur is ingesteld op 0, kan de Minimale wachtwoordduur worden ingesteld op elke waarde tussen 0 en 998.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067022) 
  
  **Standaardinstelling**: 1  

## <a name="dma-guard"></a>DMA Guard  
Raadpleeg [Beleids-CSP - DmaGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dmaguard) in de Windows-documentatie voor meer informatie.
- **Opsomming van externe apparaten die niet compatibel zijn met DMA-beveiliging van kernel**  
  Dit beleid is bedoeld om extra te beveiligen tegen externe DMA-compatibele apparaten. Het geeft u meer controle over de opsomming van externe DMA-compatibele apparaten die niet compatibel zijn met hertoewijzing/apparaatgeheugenisolatie en sandbox van DMA. Dit beleid wordt alleen uitgevoerd als DMA-beveiliging van kernel wordt ondersteund en ingeschakeld door de systeemfirmware. Kernel DMA-beveiliging is een platform-functie die niet worden beheerd via beleid of door de eindgebruiker. De functie moet door het systeem worden ondersteund ten tijde van de productie. Als u wilt controleren of het systeem Kernel DMA-beveiliging ondersteunt, Controleer of het veld Kernel DMA beveiliging op de overzichtspagina van MSINFO32.exe.  
  [Meer informatie](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dmaguard#dmaguard-deviceenumerationpolicy)

  **Standaardinstelling**: Alles blokkeren   

## <a name="event-log-service"></a>De service Gebeurtenislogboek  
Zie [Beleids-CSP - EventLogService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-eventlogservice) in de Windows-documentatie voor meer informatie.  

- **Maximale bestandsgrootte voor beveiligingslogboeken (in KB)**  
  Met deze beleidsinstelling geeft u de maximale grootte van het logboekbestand (in kB) op. Als u deze beleidsinstelling inschakelt, kunt u een maximale grootte voor logboekbestanden tussen 1 MB (1024 kB) en 2 TB (2147483647 KB) instellen, die per kB kan worden verhoogd. Als u deze beleidsinstelling uitschakelt of niet configureert, wordt de maximale grootte van het logboekbestand ingesteld op de lokaal geconfigureerde waarde. Deze waarde kan door de lokale beheerder worden gewijzigd via het dialoogvenster Logboekeigenschappen. De standaardinstelling is 20 MB.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067042)  
  
   **Standaardinstelling**: 196608  

- **Maximale bestandsgrootte voor systeemlogboeken (in kB)**  
  Met deze beleidsinstelling geeft u de maximale grootte van het logboekbestand (in kB) op. Als u deze beleidsinstelling inschakelt, kunt u een maximale grootte voor logboekbestanden tussen 1 MB (1024 kB) en 2 TB (2147483647 KB) instellen, die per kB kan worden verhoogd. Als u deze beleidsinstelling uitschakelt of niet configureert, wordt de maximale grootte van het logboekbestand ingesteld op de lokaal geconfigureerde waarde. Deze waarde kan door de lokale beheerder worden gewijzigd via het dialoogvenster Logboekeigenschappen. De standaardinstelling is 20 MB.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2066798)  
  
  **Standaardinstelling**: 32768  

- **Maximale bestandsgrootte voor toepassingslogboeken (in kB)**  
  Met deze beleidsinstelling geeft u de maximale grootte van het logboekbestand (in kB) op. Als u deze beleidsinstelling inschakelt, kunt u een maximale grootte voor logboekbestanden tussen 1 MB (1024 kB) en 2 TB (2147483647 KB) instellen, die per kB kan worden verhoogd. Als u deze beleidsinstelling uitschakelt of niet configureert, wordt de maximale grootte van het logboekbestand ingesteld op de lokaal geconfigureerde waarde. Deze waarde kan door de lokale beheerder worden gewijzigd via het dialoogvenster Logboekeigenschappen. De standaardinstelling is 20 MB.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067125)  
  
  **Standaardinstelling**: 32768  

## <a name="experience"></a>Ervaring  
Zie [Beleids-CSP - Ervaring](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience) in de Windows-documentatie voor meer informatie.  

- **Windows Spotlight blokkeren**  
  Hiermee kunnen IT-beheerders alle Windows Spotlight-functies uitschakelen: Window Spotlight op het vergrendelingsscherm, Windows Tips, Microsoft consumentenfuncties en andere gerelateerde functies.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067037)  
  
  **Standaardinstelling**: Ja  

  Wanneer *Windows-spotlight blokkeren* is ingesteld op *Ja*, zijn de volgende instellingen beschikbaar.
  
  - **Suggesties van derden in Windows Spotlight blokkeren**  
    Hiermee geeft u op of app- en inhoudssuggesties van uitgevers van externe software zijn toegestaan in Windows Spotlight-functies zoals Spotlight op het vergrendelingsscherm, voorgestelde apps in het startmenu en Windows Tips. Gebruikers zien mogelijk nog wel suggesties voor Microsoft-functies, apps en services.  
    [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067045)  
      
    **Standaardinstelling**: Ja  
  - **Specifieke functies voor consumenten blokkeren**  
    Hiermee kunnen IT-beheerders ervaringen inschakelen die doorgaans alleen voor consumenten worden gebruikt, zoals startsuggesties, lidmaatschapsmeldingen, Post-OOBE-app-installaties en omleidingstegels.  
    [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067054)  
     
    **Standaardinstelling**: Ja  

## <a name="exploit-guard"></a>ExploitGuard  
Zie [Beleids-CSP - ExploitGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-exploitguard) in de Windows-documentatie voor meer informatie.  

- **XML Exploit Guard-beveiliging**  
  Hiermee kan de IT-beheerder een configuratie pushen die de gewenste systeem- en toepassingbeperkingsopties voor alle apparaten in de organisatie aangeeft. De configuratie wordt vertegenwoordigd door een XML. Exploit Protection helpt apparaten te beschermen tegen malware die exploits gebruikt om zichzelf te verspreiden en andere apparaten te infecteren. U gebruikt de Windows-beveiligingsapp of PowerShell om een set beperkingen te maken (dit wordt een configuratie genoemd). U kunt deze configuratie vervolgens als XML-bestand exporteren en delen met meerdere apparaten in uw netwerk, zodat ze allemaal dezelfde set beperkingsinstellingen hebben. U kunt ook een bestaand XML-bestand met een EMET-configuratie naar een XML-bestand voor exploitbeveiligingsconfiguratie converteren en importeren.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067035)  
  
  **Standaardinstelling**: *Er is een voorbeeld van een XML-bestand meegeleverd* 
 
## <a name="file-explorer"></a>Bestandsverkenner  
Zie [Beleids-CSP - FileExplorer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-fileexplorer) in de Windows-documentatie voor meer informatie.  

- **Preventie van gegevensuitvoering blokkeren**  
  Wanneer u preventie van gegevensuitvoering uitschakelt, kunnen bepaalde verouderde invoegtoepassingen werken zonder de Verkenner af te sluiten.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067043)  
  
  **Standaardinstelling**: uitgeschakeld  
   
- **Heap-beëindiging blokkeren bij corruptie**  
  Wanneer u Heap-beëindiging blokkeren bij corruptie uitschakelt, kunnen bepaalde verouderde invoegtoepassingen werken zonder de Verkenner direct af te sluiten, hoewel de Verkenner later nog wel steeds onverwacht kan worden beëindigd.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067107)  
  
  **Standaardinstelling**: uitgeschakeld  
    

## <a name="internet-explorer"></a>Internet Explorer  
Zie [Beleids-CSP - InternetExplorer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-internetexplorer) in de Windows-documentatie voor meer informatie.  

- **Beperkte updates van de statusbalk vinden plaats in de Internet Explorer-zone via script**  
  Met deze beleidsinstelling kunt u regelen of de statusbalk in de zone via script mag worden bijgewerkt. 
  - *Als u deze beleidsinstelling inschakelt*, mag de statusbalk worden bijgewerkt via script.
  - *Als u deze beleidsinstelling uitschakelt of niet configureert*, mag de statusbalk niet worden bijgewerkt via script.  

  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067074)  

  **Standaardinstelling**: uitgeschakeld

- **Internetzone van Internet Explorer: bestanden slepen en neerzetten of kopiëren en plakken**  
  Met deze beleidsinstelling kunt u beheren of gebruikers bestanden kunnen slepen of kunnen kopiëren slepen en plakken vanuit een bron binnen de zone. Als u deze beleidsinstelling inschakelt, kunnen gebruikers automatisch bestanden slepen of bestanden kopiëren en plakken vanuit deze zone. Als u in de vervolgkeuzelijst Vragen selecteert, moeten gebruikers kiezen of ze bestanden willen slepen of kopiëren vanuit deze zone. Als u deze beleidsinstelling uitschakelt, kunnen geen bestanden slepen of kopiëren en plakken vanuit deze zone. Als u deze beleidsinstelling niet configureert, kunnen gebruikers automatisch bestanden slepen of bestanden kopiëren en plakken vanuit deze zone.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067076)  

  **Standaard**: Uitschakelen

- **Internet Explorer: onderdelen in de beperkte zone die afhankelijk zijn van .NET Framework**    
  Met deze beleidsinstelling kunt u beheren of .NET Framework-onderdelen die niet met Authenticode zijn ondertekend, kunnen worden uitgevoerd vanaf Internet Explorer. Deze onderdelen bevatten beheerde besturingselementen waarnaar vanuit een objectlabel wordt verwezen en beheerde uitvoerbare bestanden waarnaar vanuit een koppeling wordt verwezen. Als u deze beleidsinstelling inschakelt, worden niet-ondertekende beheerde onderdelen in Internet Explorer uitgevoerd. Als u Prompt selecteert in de vervolgkeuzelijst, wordt de gebruiker gevraagd om te bepalen of niet-ondertekende beheerde onderdelen moeten worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, worden niet-ondertekende beheerde onderdelen niet in Internet Explorer uitgevoerd. Als u deze beleidsinstelling niet configureert, voert Internet Explorer niet-ondertekende beheerde onderdelen niet uit.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067077)

  **Standaard**: Uitschakelen


- **Internet Explorer: er wordt geen antimalware uitgevoerd op ActiveX-besturingselementen in de lokale machinezone**  
  Met deze beleidsinstelling wordt bepaald of Internet Explorer antimalwareprogramma's uitvoert op ActiveX-besturingselementen om te controleren of ze veilig zijn om te laden op pagina's. Als u deze beleidsinstelling inschakelt, controleert Internet Explorer niet met uw antimalware-programma om te zien of het veilig is om een exemplaar van het ActiveX-besturingselement te installeren. Als u deze beleidsinstelling uitschakelt, controleert Internet Explorer altijd met uw antimalware-programma om te zien of het veilig is om een exemplaar van het ActiveX-besturingselement te installeren. Als u deze beleidsinstelling niet configureert, controleert Internet Explorer niet met uw antimalware-programma om te zien of het veilig is om een exemplaar van het ActiveX-besturingselement te installeren. Gebruikers kunnen dit gedrag in- of uitschakelen met de beveiligingsinstellingen van Internet Explorer.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067152)

  **Standaardinstelling**: uitgeschakeld

- **Internet Explorer: toegang tot gegevensbronnen via een internetzone**  
  Met deze beleidsinstelling kunt u beheren of Internet Explorer toegang heeft tot gegevens van een andere beveiligingszone met behulp van de Microsoft XML-parser (MSXML) of ActiveX-gegevensobjecten (ADO). Als u deze beleidsinstelling inschakelt, kunnen gebruikers een pagina laden in de zone die MSXML of ADO gebruikt voor toegang tot gegevens van een andere site in de zone. Als u Prompt selecteert in de vervolgkeuzelijst, wordt gebruikers gevraagd om te kiezen of een pagina mag worden geladen in de zone die MSXML of ADO gebruikt voor toegang tot gegevens van een andere site in de zone. Als u deze beleidsinstelling uitschakelt, kunnen gebruikers geen pagina laden in de zone die MSXML of ADO gebruikt voor toegang tot gegevens van een andere site in de zone. Als u deze beleidsinstelling niet configureert, kunnen gebruikers geen pagina laden in de zone die MSXML of ADO gebruikt voor toegang tot gegevens van een andere site in de zone.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067078)  
  
  **Standaard**: Uitschakelen  
  
- **Internet Explorer: inhoud van verschillende domeinen in Windows in de beperkte zone verslepen**  
  Met deze beleidsinstelling kunt u opties instellen voor het verslepen van inhoud van het ene naar het andere domein wanneer de bron en de bestemming zich in hetzelfde venster bevinden. Als u deze beleidsinstelling inschakelt en op Inschakelen klikt, kunnen gebruikers inhoud van het ene naar het andere domein verslepen wanneer de bron en de bestemming zich in hetzelfde venster bevinden. Gebruikers kunnen deze instelling niet wijzigen. Als u deze beleidsinstelling inschakelt en op Uitschakelen klikt, kunnen gebruikers geen inhoud van het ene naar het andere domein verslepen wanneer de bron en de bestemming zich in hetzelfde venster bevinden. Gebruikers kunnen deze instelling niet wijzigen in het dialoogvenster Internetopties. Als u deze beleidsinstelling in Internet Explorer 10 uitschakelt of niet configureert, kunnen gebruikers geen inhoud van het ene naar het andere domein verslepen wanneer de bron en de bestemming zich in hetzelfde venster bevinden. Gebruikers kunnen deze instelling wijzigen in het dialoogvenster Internetopties. Als u deze beleidsinstelling in Internet Explorer 9 en eerdere versies uitschakelt of niet configureert, kunnen gebruikers inhoud van het ene naar het andere domein verslepen wanneer de bron en de bestemming zich in hetzelfde venster bevinden. Gebruikers kunnen deze instelling niet wijzigen in het dialoogvenster Internetopties.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067079)  
  
  **Standaardinstelling**: uitgeschakeld
  
- **Internet Explorer: waarschuwing voor niet-overeenkomende certificaatadressen**  
  Met deze beleidsinstelling kunt u de beveiligingswaarschuwing inschakelen voor het geval dat certificaatadressen niet overeenkomen. Wanneer deze beleidsinstelling is ingeschakeld, krijgt de gebruiker een waarschuwing wanneer hij of zij HTTPS-website (Secure HTTP) bezoekt die certificaten laat zien die voor een ander website-adres zijn uitgegeven. Met deze waarschuwing voorkomt u aanvallen met adresvervalsing (spoofing). Als u deze beleidsinstelling inschakelt, wordt altijd de waarschuwing weergegeven dat de certificaatadressen niet overeenkomen. Als u deze beleidsinstelling uitschakelt of niet configureert, kan de gebruiker kiezen of de waarschuwing dat de certificaatadressen niet overeenkomen wordt weergegeven (met behulp van de pagina Geavanceerd in het internetconfiguratiescherm).  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067153)  
  
  **Standaardinstelling**: ingeschakeld 
  
- **Internet Explorer: sites met minder machtigingen in de beperkte zone**  
  Met deze beleidsinstelling kunt u beheren of websites van zones met minder machtigingen, zoals internetsites, naar deze zone mogen navigeren. Als u deze beleidsinstelling inschakelt, kunnen websites van zones met minder machtigingen nieuwe vensters openen in, of navigeren naar, deze zone. De beveiligingszone wordt uitgevoerd zonder de toegevoegde beveiligingslaag die door de beveiliging van de beveiligingsfunctie Zoneverhoging wordt geleverd. Als u Vragen in de vervolgkeuzelijst selecteert, krijgt de gebruiker een waarschuwing dat er sprake is van mogelijk riskante navigatie. Als u deze beleidsinstelling uitschakelt, is mogelijk schadelijke navigatie verboden. De beveiligingsfunctie van Internet Explorer is in deze zone ingeschakeld, zoals dit is ingesteld bij de functie Zone-uitbreiding. Als u deze beleidsinstelling niet configureert, is mogelijk schadelijke navigatie verboden. De beveiligingsfunctie van Internet Explorer is in deze zone ingeschakeld, zoals dit is ingesteld bij de functie Zone-uitbreiding.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067148)  
  
  **Standaard**: Uitschakelen  
  
- **Internet Explorer: automatische prompt voor bestanddownloads in de beperkte zone**  
  Met deze beleidsinstelling bepaalt u of gebruikers een melding krijgen bij bestanddownloads die niet door de gebruiker zijn geïnitieerd. Gebruikers krijgen, ongeacht deze instelling, dialoogvensters te zien voor bestanddownloads die ze zelf hebben geïnitieerd. Als u deze instelling inschakelt, krijgen gebruikers een dialoogvenster voor bestanddownloads te zien bij automatische downloadpogingen. Als u deze instelling uitschakelt of niet configureert, worden bestanddownloads die niet door de gebruiker zelf zijn geïnitieerd geblokkeerd en zien gebruikers de Meldingenbalk in plaats van het dialoogvenster voor bestanddownloads. Gebruikers kunnen vervolgens op de Meldingenbalk klikken voor de bestanddownloadprompt.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067150)  
  
  **Standaardinstelling**: uitgeschakeld
  
- **Internet Explorer: onderdelen in de internetzone die afhankelijk zijn van .NET Framework**  
  Met deze beleidsinstelling kunt u beheren of .NET Framework-onderdelen die niet met Authenticode zijn ondertekend, kunnen worden uitgevoerd in Internet Explorer. Deze onderdelen bevatten beheerde besturingselementen waarnaar vanuit een objectlabel wordt verwezen en beheerde uitvoerbare bestanden waarnaar vanuit een koppeling wordt verwezen. Als u deze beleidsinstelling inschakelt, worden niet-ondertekende beheerde onderdelen in Internet Explorer uitgevoerd. Als u Prompt selecteert in de vervolgkeuzelijst, wordt de gebruiker gevraagd om te bepalen of niet-ondertekende beheerde onderdelen moeten worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, worden niet-ondertekende beheerde onderdelen niet in Internet Explorer uitgevoerd. Als u deze beleidsinstelling niet configureert, worden niet-ondertekende beheerde onderdelen in Internet Explorer uitgevoerd.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067073)  
  
  **Standaard**: Uitschakelen 
  
- **Internet Explorer: alleen goedgekeurde domeinen in de internetzone toestaan om TDC ActiveX-besturingselementen te gebruiken**  
  Met deze beleidsinstelling bepaalt u of de gebruiker het TDC ActiveX-besturingselement op websites kan uitvoeren. Als u deze beleidsinstelling inschakelt, wordt het TDC ActiveX-besturingselement niet uitgevoerd vanaf websites in deze zone. Als u deze beleidsinstelling uitschakelt, wordt het TDC ActiveX-besturingselement uitgevoerd vanaf alle sites in deze zone.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067151)
  
  **Standaardinstelling**: ingeschakeld 
  
- **Internet Explorer: door script geïnitieerde vensters in de beperkte zone**  
  Met deze beleidsinstelling kunt u beperkingen beheren voor door scripts geïnitieerde pop-upvensters en vensters die een titel en statusbalken bevatten. Als u deze beleidsinstelling inschakelt, is de beveiliging door Windows-beperkingen niet van toepassing in deze zone. De beveiligingszone wordt uitgevoerd zonder de toegevoegde beveiligingslaag van deze functie. Als u deze beleidsinstelling uitschakelt, kunnen mogelijk schadelijke acties in door scripts geïnitieerde pop-upvensters en vensters die een titel en statusbalken bevatten, niet worden uitgevoerd. Deze beveiligingsfunctie van Internet Explorer is in deze zone ingeschakeld, zoals dat door de instelling van de functie Gescripte Windows-beveiligingsbeperkingen voor het proces is opgegeven. Als u deze beleidsinstelling niet configureert, kunnen mogelijk schadelijke acties in door scripts geïnitieerde pop-upvensters en vensters die een titel en statusbalken bevatten, niet worden uitgevoerd. Deze beveiligingsfunctie van Internet Explorer is in deze zone ingeschakeld, zoals dat door de instelling van de functie Gescripte Windows-beveiligingsbeperkingen voor het proces is opgegeven.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067075)  
  
  **Standaardinstelling**: uitgeschakeld 
  
- **Internet Explorer: lokaal pad in internetzone opnemen tijdens het uploaden van bestanden naar de server**  
  Met deze beleidsinstelling bepaalt u of gegevens over het lokale pad worden verzonden wanneer de gebruiker een bestand uploadt via een HTML-formulier. Als er gegevens over het lokale pad zijn verzonden, wordt mogelijk bepaalde informatie onbedoeld op de server weergegeven. Bestanden die vanaf het bureaublad van de gebruiker zijn verzonden, bevatten bijvoorbeeld mogelijk de gebruikersnaam als onderdeel van het pad. Als u deze beleidsinstelling inschakelt, worden gegevens over het pad verzonden wanneer de gebruiker een bestand via een HTML-formulier uploadt. Als u deze beleidsinstelling uitschakelt, worden gegevens over het pad verwijderd wanneer de gebruiker een bestand via een HTML-formulier uploadt. Als u deze beleidsinstelling niet configureert, kan de gebruiker kiezen of gegevens over het pad worden verzonden wanneer ze een bestand uploaden via een HTML-formulier. Standaard worden gegevens over het pad verzonden.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067072)  
  
  **Standaardinstelling**: uitgeschakeld 
  
- **Internet Explorer-processen uitschakelen in uitgebreide beveiligde modus**  
  Met deze beleidsinstelling bepaalt u of Internet Explorer 11 64-bits-processen (voor meer beveiliging) of 32-bits processen (voor meer compatibiliteit) gebruikt wanneer deze worden uitgevoerd in de uitgebreide beveiligde modus in 64-bits versies van Windows. Belangrijk: een aantal ActiveX-besturingselementen en werkbalken is mogelijk niet beschikbaar wanneer 64-bits processen worden gebruikt. Als u deze beleidsinstelling inschakelt, gebruikt Internet Explorer 11 64-bits tabbladprocessen wanneer deze worden uitgevoerd in de uitgebreide beveiligde modus op 64-bits versies van Windows. Als u deze beleidsinstelling uitschakelt, gebruikt Internet Explorer 11 32-bits tabbladprocessen wanneer deze worden uitgevoerd in de uitgebreide beveiligde modus op 64-bits versies van Windows. Als u deze beleidsinstelling niet configureert, kunnen gebruikers deze functie in-of uitschakelen via de Internet Explorer-instellingen. Deze functie is standaard uitgeschakeld.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067149)  
  
  **Standaardinstelling**: ingeschakeld 
  
- **Internet Explorer: certificaatfouten negeren**  
  Deze beleidsinstelling voorkomt dat gebruikers fouten in het SSL/TLS-certificaat (Secure Sockets Layer/Transport Layer Security) negeren die het bladeren in Internet Explorer onderbreken (zoals 'verlopen', 'ingetrokken' of 'namen komen niet overeen'). Als u deze beleidsinstelling inschakelt, kan de gebruiker niet doorgaan met bladeren. Als u deze beleidsinstelling uitschakelt of niet configureert, kan de gebruiker kiezen certificaatfouten te negeren en doorgaan met bladeren.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067071)  
  
  **Standaardinstelling**: uitgeschakeld 
  
- **Internet Explorer: XAML-bestanden laden in de internetzone**  
  Met deze beleidsinstelling kunt u het laden van XAML-bestanden (Extensible Application Markup Language) beheren. XAML is een op XML gebaseerde declaratieve opmaaktaal die veel wordt gebruikt voor het maken van uitgebreide gebruikersinterfaces en graphics waarmee gebruik kan worden gemaakt van de Windows Presentation Foundation. Als u deze beleidsinstelling inschakelt en de vervolgkeuzelijst op Inschakelen instelt, worden XAML-bestanden automatisch in Internet Explorer geladen. Gebruikers kunnen dit gedrag niet wijzigen. Als u de vervolgkeuzelijst instelt op Vragen, wordt de gebruiker gevraagd om XAML-bestanden te laden. Als u deze beleidsinstelling uitschakelt, worden XAML-bestanden niet in Internet Explorer geladen. Gebruikers kunnen dit gedrag niet wijzigen. Als u deze beleidsinstelling niet configureert, kan de gebruiker zelf bepalen of hij of zij XAML-bestanden in Internet Explorer wil laden.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067147)  
  
  **Standaard**: Uitschakelen 
  
- **Internet Explorer: automatische prompt voor bestanddownloads in internetzone**  
  Met deze beleidsinstelling bepaalt u of gebruikers een melding krijgen bij bestanddownloads die niet door de gebruiker zijn geïnitieerd. Gebruikers krijgen, ongeacht deze instelling, dialoogvensters te zien voor bestanddownloads die ze zelf hebben geïnitieerd. Als u deze instelling inschakelt, krijgen gebruikers een dialoogvenster voor bestanddownloads te zien bij automatische downloadpogingen. Als u deze instelling uitschakelt of niet configureert, worden bestanddownloads die niet door de gebruiker zelf zijn geïnitieerd geblokkeerd en zien gebruikers de Meldingenbalk in plaats van het dialoogvenster voor bestanddownloads. Gebruikers kunnen vervolgens op de Meldingenbalk klikken voor de bestanddownloadprompt.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067117)  
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Internet Explorer: beperkte zonebeveiligingswaarschuwing voor mogelijk onveilige bestanden**  
  Met deze beleidsinstelling bepaalt u of het bericht 'Bestand openen - beveiligingswaarschuwing' wordt weergegeven wanneer de gebruiker uitvoerbare bestanden of andere mogelijk onveilige bestanden (van een intranetbestandsshare met de Verkenner, bijvoorbeeld) probeert te openen. Als u deze beleidsinstelling inschakelt en de vervolgkeuzelijst instelt op Inschakelen, worden deze bestanden geopend zonder beveiligingswaarschuwing. Als u de vervolgkeuzelijst instelt op Prompt, wordt een beveiligingswaarschuwing weergegeven voordat de bestanden worden geopend. Als u deze beleidsinstelling uitschakelt, worden deze bestanden niet geopend. Als u deze beleidsinstelling niet configureert, kan de gebruiker configureren hoe de computer deze bestanden verwerkt. Standaard worden deze bestanden geblokkeerd in de beperkte zone, ingeschakeld in de zones Intranet en Lokale computer en ingesteld op Prompt in de zones Internet en Vertrouwd.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2066797)  
  
  **Standaard**: Uitschakelen  
  
- **Internet Explorer: XSS-filters voor internetzones**  
  Met dit beleid bepaalt u of het XSS-filter (website-overschrijdende Scripting) website-overschrijdende scriptinjecties in websites in deze zone kan detecteren en voorkomen. Als u deze beleidsinstelling inschakelt, wordt het XSS-filter ingeschakeld voor sites in deze zone en probeert het XSS-filter website-overschrijdende scriptinjecties te blokkeren. Als u deze beleidsinstelling uitschakelt, wordt het XSS-filter uitgeschakeld voor sites in deze zone en staat Internet Explorer website-overschrijdende scriptinjecties toe.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067053) 
  
  **Standaardinstelling**: ingeschakeld 
  
- **Internet Explorer-terugval naar SSL3**  
  Met deze beleidsinstelling kunt u een onbeveiligde terugval naar SSL 3.0 blokkeren. Wanneer dit beleid is ingeschakeld, probeert Internet Explorer verbinding te maken met sites met behulp van SSL 3.0 of lager wanneer TLS 1.0 of hoger is mislukt. U wordt aangeraden onbeveiligde terugval niet toe te staan om een man-in-the-middle-aanval te voorkomen. Dit beleid heeft geen invloed op welke beveiligingsprotocollen worden ingeschakeld. Als u dit beleid uitschakelt, worden systeemstandaarden gebruikt.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067118)  
  
  **Standaardinstelling**: Geen sites  

- **Ondersteuning voor de versleuteling van Internet Explorer**  
  Met deze beleidsinstelling kunt u de ondersteuning voor Transport Layer Security (TLS) 1.0, TLS 1.1, TLS 1.2, Secure Sockets Layer (SSL) 2.0 of SSL 3.0 in de browser uitschakelen. TLS en SSL zijn protocollen die helpen bij het beveiligen van communicatie tussen de browser en de doelserver. Wanneer de browser probeert het instellen van een beveiligde communicatie met de doelserver, onderhandelen de browser en de server over welk protocol en de versie moet worden gebruikt. De browser en de server probeert zodat deze overeenkomen met elkaars lijst met ondersteunde protocollen en versies en selecteren ze de meest geschikte overeenkomst. Als u deze beleidsinstelling inschakelt, wordt de browser wordt onderhandeld over of onderhandelt niet over een tunnel codering met behulp van de versleutelingsmethoden die u in de vervolgkeuzelijst selecteren. Als u deze beleidsinstelling niet configureert of uitschakelt, kan de gebruiker selecteren welke versleuteling methode de browser ondersteunt.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067057)

  **Standaard**: 2 items: TLS v1.1 en TLS 1.2  
  *Selecteer de pijl-omlaag om opties die u voor deze instelling selecteren kunt weer te geven.*
  
- **Internet Explorer: vergrendeld SmartScreen in internetzone**  
  Met deze beleidsinstelling bepaalt u of het SmartScreen-filter pagina's in deze zone scant op schadelijke inhoud. Als u deze beleidsinstelling inschakelt, scant het SmartScreen-filter pagina's in deze zone op schadelijke inhoud. Als u deze beleidsinstelling uitschakelt, scant het SmartScreen-filter geen pagina's in deze zone op schadelijke inhoud. Als u deze beleidsinstelling niet configureert, kan de gebruiker kiezen of het SmartScreen-filter pagina's in deze zone scant op schadelijke inhoud. Opmerking: in Internet Explorer 7 bepaalt deze beleidsinstelling of het phishing-filter pagina's in deze zone scant op schadelijke inhoud.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067059)  
  
  **Standaardinstelling**: ingeschakeld 
  
- **Internet Explorer: toepassingen en bestanden in een IFRAME openen in een beperkte zone**  
  Met deze beleidsinstelling kunt u beheren of toepassingen kunnen worden uitgevoerd en of bestanden kunnen worden gedownload via een IFRAME-verwijzing in de HTML van de pagina's in deze zone. Als u deze beleidsinstelling inschakelt, kunnen gebruikers toepassingen uitvoeren en bestanden uit IFRAME's op de pagina's in deze zone downloaden zonder gebruikersinterventie. Als u Prompt selecteert in de vervolgkeuzelijst, wordt gebruikers gevraagd of ze toepassingen willen uitvoeren en bestanden willen downloaden van IFRAME's op de pagina's in deze zone. Als u deze beleidsinstelling uitschakelt, kunnen gebruikers geen toepassingen uitvoeren of bestanden downloaden van IFRAME's op de pagina's in deze zone. Als u deze beleidsinstelling niet configureert, kunnen gebruikers geen toepassingen uitvoeren of bestanden downloaden van IFRAME's op de pagina's in deze zone.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067061)  
  
  **Standaard**: Uitschakelen 
  
- **SmartScreen-waarschuwingen over ongebruikelijke bestanden negeren in Internet Explorer**  
  Met deze beleidsinstelling bepaalt u of de gebruiker waarschuwingen van het SmartScreen-filter kan negeren. Het SmartScreen-filter waarschuwt de gebruiker voor uitvoerbare bestanden die Internet Explorer-gebruikers normaalgesproken niet van internet downloaden. Als u deze beleidsinstelling inschakelt, wordt de gebruiker door waarschuwingen van het SmartScreen-filter geblokkeerd. Als u deze beleidsinstelling uitschakelt of niet configureert, kan de gebruiker waarschuwingen van het SmartScreen-filter negeren.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067068)  
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Internet Explorer: pop-upblokkering van internetzone**  
  Met deze beleidsinstelling kunt u beheren of ongewenste pop-upvensters worden weergegeven. Pop-upvensters die worden geopend wanneer de eindgebruiker op een koppeling klikt, worden niet geblokkeerd. Als u deze beleidsinstelling inschakelt, voorkomt u dat de meeste ongewenste pop-upvensters worden weergegeven. Als u deze beleidsinstelling uitschakelt, wordt het weergeven van pop-upvensters niet voorkomen. Als u deze beleidsinstelling niet configureert, voorkomt u dat de meeste ongewenste pop-upvensters worden weergegeven.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067069)  
  
  **Standaardinstelling**: Inschakelen  
  
- **Internet Explorer: consistente MIME-verwerking met processen**  
  Internet Explorer bevat dynamisch binair gedrag: onderdelen die specifieke functionaliteit bevatten voor de HTML-elementen waaraan ze zijn gekoppeld. Met deze beleidsinstelling bepaalt u of de instelling Beveiligingsbeperkingen voor binair gedrag is verboden of is toegestaan. Als u deze beleidsinstelling inschakelt, is binair gedrag verboden voor de Bestandsverkenner en Internet Explorer-processen. Als u deze beleidsinstelling uitschakelt, is binair gedrag toegestaan voor de Bestandsverkenner en Internet Explorer-processen. Als u deze beleidsinstelling niet configureert, is binair gedrag verboden voor de Verkenner en Internet Explorer-processen.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067144)  
  
  **Standaardinstelling**: ingeschakeld  
  
- **Java-machtigingen voor de beperkte zone in Internet Explorer**  
  Met deze beleidsinstelling kunt u machtigingen voor Java-applets beheren. Als u deze beleidsinstelling inschakelt, kunt u opties kiezen in de vervolgkeuzelijst. Aangepast, om instellingen voor machtigingen afzonderlijk te beheren. Met Minimale beveiliging kunnen applets alle bewerkingen uitvoeren. Met Normale beveiliging kunnen applets worden uitgevoerd in hun eigen sandbox (een gebied in het geheugen waarbuiten het programma geen aanroepen kan doen). Daarnaast biedt deze optie mogelijkheden zoals een scratchruimte (een veilig en beveiligd opslaggebied op de clientcomputer) en door de gebruiker beheerde bestandsinvoer en-uitvoer (I/O). Met Strenge beveiliging kunnen applets in hun sandbox worden uitgevoerd. Schakel Java uit om te voorkomen dat er applets worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, kunnen Java-applets niet worden uitgevoerd. Als u deze beleidsinstelling niet configureert, worden Java-applets uitgeschakeld.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067132)  
  
  **Standaardinstelling**: Java uitschakelen  
    
  
- **Internet Explorer: Active X-besturingselementen in de beveiligde modus**  
  Met deze beleidsinstelling voorkomt u dat ActiveX-besturingselementen kunnen worden uitgevoerd in de beveiligde modus wanneer de uitgebreide beveiligde modus is ingeschakeld. Als een gebruiker een ActiveX-besturingselement heeft geïnstalleerd dat niet compatibel is met de uitgebreide beveiligde modus en een website het besturingselement probeert te laden, informeert Internet Explorer de gebruiker en wordt de optie geboden om de website in de gewone beschermde modus uit te voeren. <Met deze beleidsinstelling schakelt u deze melding uit en dwingt u alle websites om te worden uitgevoerd in de uitgebreide beveiligde modus. De uitgebreide beveiligde modus biedt extra bescherming tegen schadelijke websites door gebruik te maken van 64-bits processen op 64-bits versies van Windows. Op computers met minimaal Windows 8 beperkt de uitgebreide beveiligde modus ook de locaties die Internet Explorer in het register en bestandssysteem kan lezen. Als de uitgebreide beveiligde modus is ingeschakeld en een gebruiker een website bezoekt die een ActiveX-besturingselement probeert te laden die niet compatibel is met de uitgebreide beveiligde modus, informeert Internet Explorer de gebruiker en wordt de optie geboden om de uitgebreide beveiligde modus voor die specifieke website uit te schakelen. Als u deze beleidsinstelling inschakelt, biedt Internet Explorer de gebruiker niet de optie om de uitgebreide beveiligde modus uit te schakelen. Alle websites in de beveiligde modus worden uitgevoerd in de uitgebreide beveiligde modus. Als u deze beleidsinstelling uitschakelt of niet configureert, informeert Internet Explorer gebruikers en wordt een mogelijkheid geboden om websites met incompatibele ActiveX-besturingselementen uit te voeren in de gewone beveiligde modus.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067145)  
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Internet Explorer: XAML-bestanden laden in de beperkte zone**  
  Met deze beleidsinstelling kunt u het laden van XAML-bestanden (Extensible Application Markup Language) beheren. XAML is een op XML gebaseerde declaratieve opmaaktaal die veel wordt gebruikt voor het maken van uitgebreide gebruikersinterfaces en graphics waarmee gebruik kan worden gemaakt van de Windows Presentation Foundation. Als u deze beleidsinstelling inschakelt en de vervolgkeuzelijst op Inschakelen instelt, worden XAML-bestanden automatisch in Internet Explorer geladen. Gebruikers kunnen dit gedrag niet wijzigen. Als u de vervolgkeuzelijst instelt op Vragen, wordt de gebruiker gevraagd om XAML-bestanden te laden. Als u deze beleidsinstelling uitschakelt, worden XAML-bestanden niet in Internet Explorer geladen. Gebruikers kunnen dit gedrag niet wijzigen. Als u deze beleidsinstelling niet configureert, kan de gebruiker zelf bepalen of hij of zij XAML-bestanden in Internet Explorer wil laden.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067070)  
  
  **Standaard**: Uitschakelen  
  
- **Internet Explorer verwerkt beveiligingsbeperkingen voor scriptvensters**  
  Internet Explorer staat scripts toe om via een programma uiteenlopende soorten vensters te openen, groter of kleiner te maken en te verplaatsen. De beveiligingsfunctie Vensterbeperkingen beperkt pop-upvensters en verbiedt scripts om vensters weer te geven waarin de titel- en statusbalk niet zichtbaar zijn voor de gebruiker of die de titel- en statusbalk van andere Windows-vensters onleesbaar maken. Als u deze beleidsinstelling inschakelt, worden scriptvensters voor alle processen beperkt. Als u deze beleidsinstelling uitschakelt of niet configureert, gelden er geen beperkingen voor scriptvensters.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067146)  
  
  **Standaardinstelling**: ingeschakeld   
  
- **Active X-besturingselementen en invoegtoepassingen uitvoeren in beperkte zone van Internet Explorer**  
  Met deze beleidsinstelling kunt u beheren of ActiveX-besturingselementen en invoegtoepassingen kunnen worden uitgevoerd op de pagina's in de opgegeven zone. Als u deze beleidsinstelling inschakelt, kunnen besturingselementen en invoegtoepassingen zonder tussenkomst van de gebruiker worden uitgevoerd. Als u in de vervolgkeuzelijst Vragen hebt geselecteerd, wordt gebruikers gevraagd om te kiezen of ze de bedieningselementen of invoegtoepassing willen uitvoeren. Als u deze beleidsinstelling uitschakelt, worden de besturingselementen en invoegtoepassingen niet uitgevoerd. Als u deze beleidsinstelling niet configureert, worden de besturingselementen en invoegtoepassingen niet uitgevoerd.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067114) 
  
  **Standaard**: Uitschakelen  
  
- **ActiveX-besturingselementen die als veilig zijn gemarkeerd voor het uitvoeren van scripts in de beperkte zone van Internet Explorer**  
  Met deze beleidsinstelling kunt u beheren of een ActiveX-besturingselement dat als veilig is gemarkeerd voor het uitvoeren van scripts kan communiceren met een script. Als u deze beleidsinstelling inschakelt, kunnen scripts automatisch communiceren zonder tussenkomst van de gebruiker. Als u in de vervolgkeuzelijst Vragen selecteert, moeten gebruikers kiezen of ze interactie van scripts willen toestaan. Als u deze beleidsinstelling uitschakelt, mag er geen interactie tussen scripts plaatsvinden. Als u deze beleidsinstelling niet configureert, mag er geen interactie tussen scripts plaatsvinden.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067062)  
  
  **Standaard**: Uitschakelen  
  
- **Opties voor aanmelden in de beperkte zone van Internet Explorer**  
  Met deze beleidsinstelling kunt u de instellingen voor aanmeldingsopties beheren. Als u deze beleidsinstelling inschakelt, kunt u kiezen uit de volgende aanmeldingsopties. 
  - *Anoniem*: anoniem aanmelden om HTTP-verificatie uit te schakelen en het gastaccount alleen gebruiken voor het CIFS-protocol (Common Internet File System). 
  - *Vragen*: om een gebruikersnaam en wachtwoord vragen om een query te maken voor de gebruikers-id's en wachtwoorden van gebruikers. Nadat een query voor een gebruiker is uitgevoerd, kunnen deze waarden op de achtergrond worden gebruikt gedurende de rest van de sessie. 
  - *Alleen automatisch aanmelden in de intranetzone*: gebruik deze optie om een query te maken voor de gebruikers-id's en wachtwoorden in andere zones. Nadat een query voor een gebruiker is uitgevoerd, kunnen deze waarden op de achtergrond worden gebruikt gedurende de rest van de sessie. 
  - *Automatisch aanmelden met de huidige gebruikersnaam en het huidige wachtwoord*: gebruik deze optie om aanmelden te proberen met behulp van Windows NT-vraag-antwoord (ook wel NTLM-verificatie genoemd). Als de server Windows NT-vraag-antwoord ondersteunt, gebruikt de aanmelding de gebruikersnaam en het wachtwoord van de gebruiker voor het netwerk om de gebruiker aan te melden. Als Windows NT-vraag-antwoord niet door de server wordt ondersteund, wordt de gebruiker gevraagd om de gebruikersnaam en het wachtwoord op te geven. 

  Als u deze beleidsinstelling uitschakelt, wordt de aanmelding ingesteld op *Alleen automatisch aanmelden in de intranetzone*. Als u deze beleidsinstelling niet configureert, wordt de aanmelding ingesteld op *Om gebruikersnaam en wachtwoord vragen*.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067110)  
  
  **Standaardinstelling**: Anoniem  
  
- **ActiveX-besturingselementen die niet als veilig zijn gemarkeerd initialiseren en als script uitvoeren in de vertrouwde zone in Internet Explorer**  
  Met deze beleidsinstelling kunt u ActiveX-besturingselementen beheren die niet als veilig zijn gemarkeerd. Als u deze beleidsinstelling inschakelt, worden ActiveX-besturingselementen uitgevoerd, voorzien van parameters en als script uitgevoerd zonder de veiligheid van objecten in te stellen voor niet-vertrouwde gegevens of scripts. Deze instelling wordt niet aanbevolen, behalve voor veilige en beheerde zones. Deze instelling zorgt dat zowel onveilige als veilige besturingselementen worden geïnitialiseerd en als script worden uitgevoerd. Daarbij worden de ActiveX-besturingselementen van het script die als veilig zijn gemarkeerd, genegeerd. Als u deze beleidsinstelling inschakelt en in de vervolgkeuzelijst Vragen selecteert, worden gebruikers gevraagd of ze willen toestaan dat het besturingselement met parameters wordt geladen of als script wordt uitgevoerd. Als u deze beleidsinstelling uitschakelt, worden ActiveX-besturingselementen die niet veilig kunnen worden ingesteld, niet geladen met parameters of als script uitgevoerd. Als u deze beleidsinstelling niet configureert, worden gebruikers gevraagd of ze willen toestaan dat het besturingselement wordt geladen met parameters of als script wordt uitgevoerd.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067137)  
  
  **Standaard**: Uitschakelen  
  
- **Intrekking van servercertificaat verkennen in Internet Explorer**  
  Met deze beleidsinstelling kunt u beheren of Internet Explorer de intrekkingsstatus van servercertificaten zal controleren. Certificaten worden ingetrokken als ze zijn aangetast of niet meer geldig zijn. Deze optie beschermt gebruikers tegen het verzenden van vertrouwelijke gegevens op een website die mogelijk frauduleus of onveilig is. Als u deze beleidsinstelling inschakelt, zal Internet Explorer controleren of de servercertificaten zijn ingetrokken. Als u deze beleidsinstelling uitschakelt, wordt in Internet Explorer niet gecontroleerd of de servercertificaten zijn ingetrokken. Als u deze beleidsinstelling niet configureert, wordt in Internet Explorer niet gecontroleerd of de servercertificaten zijn ingetrokken.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067046)  
  
  **Standaardinstelling**: ingeschakeld 
  
- **Internet Explorer: sites met minder machtigingen in de internetzone**  
  Met deze beleidsinstelling kunt u beheren of websites in zones met minder machtigingen, zoals beperkte websites, naar deze zone mogen navigeren. Als u deze beleidsinstelling inschakelt, kunnen websites van zones met minder machtigingen nieuwe vensters openen in, of navigeren naar, deze zone. De beveiligingszone wordt uitgevoerd zonder de toegevoegde beveiligingslaag die door de beveiliging van de beveiligingsfunctie Zoneverhoging wordt geleverd. Als u Vragen in de vervolgkeuzelijst selecteert, krijgt de gebruiker een waarschuwing dat er sprake is van mogelijk riskante navigatie. Als u deze beleidsinstelling uitschakelt, is de mogelijk schadelijke navigatie verboden. De beveiligingsfunctie van Internet Explorer is in deze zone ingeschakeld, zoals dit is ingesteld bij de functie Zone-uitbreiding. Als u deze beleidsinstelling niet configureert, kunnen websites van zones met minder bevoegdheden nieuwe vensters openen in, of navigeren naar, deze zone.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067109)  
  
  **Standaard**: Uitschakelen  
  
- **Bestanden downloaden in de beperkte zone van Internet Explorer**  
  Met deze beleidsinstelling kunt u beheren of het is toegestaan om bestanden te downloaden in de zone. Deze optie wordt bepaald door de zone van de pagina met de koppeling die de download activeert, niet door de zone waarin het bestand wordt geleverd. Als u deze beleidsinstelling inschakelt, kunnen bestanden in de zone worden gedownload. Als u deze beleidsinstelling uitschakelt, wordt het downloaden van bestanden in de zone voorkomen. Als u deze beleidsinstelling niet configureert, wordt het downloaden van bestanden in de zone voorkomen.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067038)  
  
  **Standaard**: Uitschakelen  
  
- **Internet Explorer: onderdelen in de internetzone uitvoeren die afhankelijk zijn van .NET Framework en zijn ondertekend met Authenticode**  
  Met deze beleidsinstelling kunt u beheren of .NET Framework-onderdelen die met Authenticode zijn ondertekend, kunnen worden uitgevoerd in Internet Explorer. Deze onderdelen bevatten beheerde besturingselementen waarnaar vanuit een objectlabel wordt verwezen en beheerde uitvoerbare bestanden waarnaar vanuit een koppeling wordt verwezen. Als u deze beleidsinstelling inschakelt, zal Internet Explorer ondertekende beheerde onderdelen uitvoeren. Als u in de vervolgkeuzelijst Vragen selecteert, wordt de gebruiker gevraagd om te bepalen of ondertekende beheerde onderdelen moeten worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, zal Internet Explorer ondertekende beheerde onderdelen niet uitvoeren. Als u deze beleidsinstelling niet configureert, worden ondertekende beheerde onderdelen niet uitgevoerd in Internet Explorer.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067033)  
  
  **Standaard**: Uitschakelen  
  
- **Installatie van ActiveX-besturingselementen per gebruiker voorkomen in Internet Explorer**  
  Met deze beleidsinstelling kunt u voorkomen dat per gebruiker ActiveX-besturingselementen worden geïnstalleerd. Als u deze beleidsinstelling inschakelt, kunnen er geen ActiveX-besturingselementen per gebruiker worden geïnstalleerd. Als u deze beleidsinstelling uitschakelt of niet configureert, kunnen er ActiveX-besturingselementen per gebruiker worden geïnstalleerd.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067058)  
  
  **Standaardinstelling**: ingeschakeld  
  
- **Beheer van het SmartScreen-filter voorkomen in Internet Explorer**  
  Met deze beleidsinstelling voorkomt u dat de gebruiker SmartScreen Filter kan beheren, waarmee de gebruiker wordt gewaarschuwd als de website die wordt bezocht bekend staat om frauduleuze pogingen om persoonlijke gegevens te verzamelen via phishing of om het hosten van malware. Als u deze beleidsinstelling inschakelt, wordt de gebruiker niet gevraagd om het SmartScreen-filter in te schakelen. Alle websiteadressen die niet op de toegestane lijst van het filter staan, worden automatisch naar Microsoft verzonden zonder dat de gebruiker wordt gevraagd. Als u deze beleidsinstelling niet uitschakelt of configureert, wordt de gebruiker gevraagd om te bepalen of het SmartScreen-filter moet worden ingeschakeld tijdens de eerste uitvoersessie.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067135)  
  
  **Standaardinstelling**: Inschakelen  
  
- **Internet Explorer verwerkt de veiligheidsfunctie MIME-sniffing**  
  Met deze beleidsinstelling wordt bepaald of Internet Explorer MIME-sniffing het niveau verhogen voorkomt van een bestand van het ene type naar een meer gevaarlijk bestandstype. Als u deze beleidsinstelling inschakelt, wordt bij MIME-sniffing nooit het niveau van een bestand van het ene type naar een meer gevaarlijk bestandstype verhoogd. Als u deze beleidsinstelling uitschakelt, kunnen Internet Explorer-processen toestaan dat bij MIME-sniffing het niveau van een bestand van het ene type naar een meer gevaarlijk bestandstype wordt verhoogd. Als u deze beleidsinstelling niet configureert, wordt bij MIME-sniffing nooit het niveau van een bestand van het ene type naar een meer gevaarlijk bestandstype verhoogd.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067124)  
  
  **Standaardinstelling**: ingeschakeld  
  
- **Internet Explorer: ondertekende Active X-besturingselementen downloaden in de beperkte zone**  
  Met deze beleidsinstelling kunt u beheren of gebruikers ondertekende ActiveX-besturingselementen van een pagina in de zone kunnen downloaden. Als u dit beleid inschakelt, kunnen gebruikers ondertekende besturingselementen downloaden zonder tussenkomst van de gebruiker. Als u Vragen selecteert in de vervolgkeuzelijst, wordt aan gebruikers gevraagd of ze besturingselementen willen downloaden die zijn ondertekend door niet-vertrouwde uitgevers. Code die is ondertekend door vertrouwde uitgevers wordt op de achtergrond gedownload. Als u de beleidsinstelling uitschakelt, kunnen ondertekende besturingselementen niet worden gedownload. Als u deze beleidsinstelling niet configureert, wordt aan gebruikers gevraagd of ze besturingselementen willen downloaden die zijn ondertekend door niet-vertrouwde uitgevers. Code die is ondertekend door vertrouwde uitgevers wordt op de achtergrond gedownload.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067120) 
  
  **Standaard**: Uitschakelen  
  
- **Internet Explorer: automatisch aanvullen**  
  Met de functie Automatisch aanvullen worden gebruikersnamen en wachtwoorden in formulieren onthouden en voorgesteld. Als u deze instelling inschakelt, kan de gebruiker opties voor gebruikersnaam en wachtwoorden op formulieren of vragen om wachtwoorden op te slaan niet wijzigen. De functie Automatisch aanvullen voor gebruikersnamen en wachtwoorden in formulieren is ingeschakeld. U moet bepalen of u de optie voor vragen om wachtwoorden op te slaan wilt inschakelen. Als u deze instelling uitschakelt, kan de gebruiker de opties Gebruikersnaam en wachtwoorden op formulieren en vragen om wachtwoorden op te slaan niet wijzigen. De functie Automatisch aanvullen voor gebruikersnamen en wachtwoorden in formulieren is ingeschakeld. De gebruiker kan ook niet kiezen om te worden gevraagd wachtwoorden op te slaan. Als u deze instelling niet configureert, heeft de gebruiker de vrijheid om Automatische aanvullen voor gebruikersnamen en wachtwoorden in formulieren en de optie voor vragen om wachtwoorden op te slaan in te schakelen. Om deze optie weer te geven, openen gebruikers het dialoogvenster Internetopties, klikken ze op het tabblad Inhoud en klikken ze op de knop Instellingen.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067122)  
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Internet Explorer: toestaan om VBscript uit te voeren in de internetzone**  
  Met deze beleidsinstelling kunt u beslissen of VBScript mag worden uitgevoerd op pagina's in specifieke Internet Explorer-zones. Opties zijn onder andere: 
  - *Inschakelen*: er wordt VBScript uitgevoerd op pagina's in specifieke zones, zonder enige tussenkomst. 
  - *Vragen*: werknemers wordt gevraagd of ze willen toestaan dat VBScript wordt uitgevoerd in de zone. 
  - *Uitschakelen*: er wordt voorkomen dat VBScript wordt uitgevoerd in de zone. Als u deze beleidsinstelling uitschakelt of niet configureert, wordt VBScript in de opgegeven zone uitgevoerd zonder enige tussenkomst.    

  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067119)  
  
  **Standaard**: Uitschakelen  
  
- **Internet Explorer: alleen goedgekeurde domeinen mogen TDC Active X-besturingselementen gebruiken in de beperkt zone**  
  Met deze beleidsinstelling bepaalt u of de gebruiker het TDC ActiveX-besturingselement op websites kan uitvoeren. Als u deze beleidsinstelling inschakelt, wordt het TDC ActiveX-besturingselement niet uitgevoerd vanaf websites in deze zone. Als u deze beleidsinstelling uitschakelt, wordt het TDC ActiveX-besturingselement uitgevoerd vanaf alle sites in deze zone.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067032)  
  
  **Standaardinstelling**: ingeschakeld  
  
- **Er wordt geen antimalware uitgevoerd op ActiveX-besturingselementen in de vertrouwde zone van Internet Explorer**  
  Met deze beleidsinstelling wordt bepaald of Internet Explorer antimalwareprogramma's uitvoert op ActiveX-besturingselementen om te controleren of ze veilig zijn om te laden op pagina's. Als u deze beleidsinstelling inschakelt, controleert Internet Explorer niet met uw antimalware-programma om te zien of het veilig is om een exemplaar van het ActiveX-besturingselement te installeren. Als u deze beleidsinstelling uitschakelt, controleert Internet Explorer altijd met uw antimalware-programma om te zien of het veilig is om een exemplaar van het ActiveX-besturingselement te installeren. Als u deze beleidsinstelling niet configureert, controleert Internet Explorer altijd met uw antimalware-programma om te zien of het veilig is om een exemplaar van het ActiveX-besturingselement te installeren. Gebruikers kunnen dit gedrag in- of uitschakelen met de beveiligingsinstellingen van Internet Explorer.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067115)  
  
  **Standaardinstelling**: uitgeschakeld 
  
- **Internet Explorer: Java-machtigingen voor de zone Lokale machine**  
  Met deze beleidsinstelling kunt u machtigingen voor Java-applets beheren. Als u deze beleidsinstelling inschakelt, kunt u opties kiezen in de vervolgkeuzelijst. Aangepast, om instellingen voor machtigingen afzonderlijk te beheren. Met Minimale beveiliging kunnen applets alle bewerkingen uitvoeren. Met Normale beveiliging kunnen applets worden uitgevoerd in hun eigen sandbox (een gebied in het geheugen waarbuiten het programma geen aanroepen kan doen). Daarnaast biedt deze optie mogelijkheden zoals een scratchruimte (een veilig en beveiligd opslaggebied op de clientcomputer) en door de gebruiker beheerde bestandsinvoer en-uitvoer (I/O). Met Strenge beveiliging kunnen applets in hun sandbox worden uitgevoerd. Schakel Java uit om te voorkomen dat er applets worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, kunnen Java-applets niet worden uitgevoerd. Als u deze beleidsinstelling niet configureert, wordt de machtiging ingesteld op Normale beveiliging.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067113)  
  
  **Standaardinstelling**: Java uitschakelen 
  
- **Internet Explorer: er wordt geen antimalware uitgevoerd op ActiveX-besturingselementen in de intranetzone**  
  Met deze beleidsinstelling wordt bepaald of Internet Explorer antimalwareprogramma's uitvoert op ActiveX-besturingselementen om te controleren of ze veilig zijn om te laden op pagina's. Als u deze beleidsinstelling inschakelt, controleert Internet Explorer niet met uw antimalware-programma om te zien of het veilig is om een exemplaar van het ActiveX-besturingselement te installeren. Als u deze beleidsinstelling uitschakelt, controleert Internet Explorer altijd met uw antimalware-programma om te zien of het veilig is om een exemplaar van het ActiveX-besturingselement te installeren. Als u deze beleidsinstelling niet configureert, controleert Internet Explorer niet met uw antimalware-programma om te zien of het veilig is om een exemplaar van het ActiveX-besturingselement te installeren. Gebruikers kunnen dit gedrag in- of uitschakelen met de beveiligingsinstellingen van Internet Explorer.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067138)  
  
  **Standaardinstelling**: uitgeschakeld  

- **Internet Explorer: scriptlets in de beperkte zone**  
  Met deze beleidsinstelling kunt u beheren of gebruikers scriptlets kunnen uitvoeren. Als u deze beleidsinstelling inschakelt, kan de gebruiker scriptlets uitvoeren. Als u deze beleidsinstelling uitschakelt, kan de gebruiker geen scriptlets uitvoeren. Als u deze beleidsinstelling niet configureert, kan de gebruiker scriptlets in- of uitschakelen.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067112)  
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Internet Explorer: meldingsbalk voor processen**  
  Met deze beleidsinstelling kunt u beheren of de meldingsbalk voor Internet Explorer-processen wordt weergegeven als de installatie van bestanden of code wordt beperkt. De meldingsbalk wordt standaard weergegeven voor Internet Explorer-processen. Als u deze beleidsinstelling inschakelt, wordt de meldingsbalk weergegeven voor de Internet Explorer-processen. Als u deze beleidsinstelling uitschakelt, wordt de meldingsbalk niet weergegeven voor Internet Explorer-processen. Als u deze beleidsinstelling niet configureert, wordt de meldingsbalk niet weergegeven voor Internet Explorer-processen.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067139)  
  
  **Standaardinstelling**: ingeschakeld  
  
- **Internet Explorer: ondertekende Active X-besturingselementen downloaden in internetzone**  
  Met deze beleidsinstelling kunt u beheren of gebruikers ondertekende ActiveX-besturingselementen van een pagina in de zone kunnen downloaden. Als u dit beleid inschakelt, kunnen gebruikers ondertekende besturingselementen downloaden zonder tussenkomst van de gebruiker. Als u Vragen selecteert in de vervolgkeuzelijst, wordt aan gebruikers gevraagd of ze besturingselementen willen downloaden die zijn ondertekend door niet-vertrouwde uitgevers. Code die is ondertekend door vertrouwde uitgevers wordt op de achtergrond gedownload. Als u de beleidsinstelling uitschakelt, kunnen ondertekende besturingselementen niet worden gedownload. Als u deze beleidsinstelling niet configureert, wordt aan gebruikers gevraagd of ze besturingselementen willen downloaden die zijn ondertekend door niet-vertrouwde uitgevers. Code die is ondertekend door vertrouwde uitgevers wordt op de achtergrond gedownload.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067064)  
  
  **Standaard**: Uitschakelen  
  
- **Internet Explorer: SmartScreen in de beperkte zone**  
  Met deze beleidsinstelling bepaalt u of het SmartScreen-filter pagina's in deze zone scant op schadelijke inhoud. Als u deze beleidsinstelling inschakelt, scant het SmartScreen-filter pagina's in deze zone op schadelijke inhoud. Als u deze beleidsinstelling uitschakelt, scant het SmartScreen-filter geen pagina's in deze zone op schadelijke inhoud. Als u deze beleidsinstelling niet configureert, kan de gebruiker kiezen of het SmartScreen-filter pagina's in deze zone scant op schadelijke inhoud. Opmerking: in Internet Explorer 7 bepaalt deze beleidsinstelling of het phishing-filter pagina's in deze zone scant op schadelijke inhoud.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067034)  
  
  **Standaardinstelling**: ingeschakeld  
  
- **Internet Explorer: de knop Deze keer uitvoeren verwijderen voor verouderde ActiveX-besturingselementen**  
  Met deze beleidsinstelling kunt u voorkomen dat gebruikers de knop Deze keer uitvoeren zien en specifieke verouderde ActiveX-besturingselementen in Internet Explorer uitvoeren. Als u deze beleidsinstelling inschakelt, zien gebruikers de knop Deze keer uitvoeren niet in het waarschuwingsbericht dat wordt weergegeven als Internet Explorer een verouderd ActiveX-besturingselement blokkeert. Als u deze beleidsinstelling uitschakelt of niet configureert, zien gebruikers de knop Deze keer uitvoeren in het waarschuwingsbericht dat wordt weergegeven als Internet Explorer een verouderd ActiveX-besturingselement blokkeert. Als de gebruiker op deze knop klikt, wordt het verouderde ActiveX-besturingselement eenmaal uitgevoerd. Zie Verouderde ActiveX-besturingselementen in de Internet Explorer TechNet-bibliotheek voor meer informatie.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067123)  
  
  **Standaardinstelling**: ingeschakeld 
  
- **Internet Explorer: toepassingen en bestanden in een IFRAME openen in een internetzone**  
  Met deze beleidsinstelling kunt u beheren of toepassingen kunnen worden uitgevoerd en of bestanden kunnen worden gedownload via een IFRAME-verwijzing in de HTML van de pagina's in deze zone. Als u deze beleidsinstelling inschakelt, kunnen gebruikers toepassingen uitvoeren en bestanden uit IFRAME's op de pagina's in deze zone downloaden zonder gebruikersinterventie. Als u Prompt selecteert in de vervolgkeuzelijst, wordt gebruikers gevraagd of ze toepassingen willen uitvoeren en bestanden willen downloaden van IFRAME's op de pagina's in deze zone. Als u deze beleidsinstelling uitschakelt, kunnen gebruikers geen toepassingen uitvoeren of bestanden downloaden van IFRAME's op de pagina's in deze zone. Als u deze beleidsinstelling niet configureert, wordt gebruikers gevraagd of ze toepassingen willen uitvoeren en bestanden willen downloaden van IFRAME's op de pagina's in deze zone.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067020)  
  
  **Standaard**: Uitschakelen 
  
- **Vensters en frames door verschillende domeinen laten navigeren in de beperkte zone in Internet Explorer**  
  Met deze beleidsinstelling kunt u opties instellen voor het verslepen van inhoud van het ene naar het andere domein wanneer de bron en de bestemming zich in verschillende vensters bevinden. Als u deze beleidsinstelling inschakelt en op Inschakelen klikt, kunnen gebruikers inhoud van het ene naar het andere domein verslepen wanneer de bron en de bestemming zich in verschillende vensters bevinden. Gebruikers kunnen deze instelling niet wijzigen. Als u deze beleidsinstelling inschakelt en op Uitschakelen klikt, kunnen gebruikers geen inhoud van het ene naar het andere domein verslepen als de bron en de bestemming zich in verschillende vensters bevinden. Gebruikers kunnen deze instelling niet wijzigen. Als u deze beleidsinstelling in Internet Explorer 10 uitschakelt of niet configureert, kunnen gebruikers geen inhoud van het ene naar het andere domein verslepen wanneer de bron en de bestemming zich in verschillende vensters bevinden. Gebruikers kunnen deze instelling wijzigen in het dialoogvenster Internetopties. Als u dit beleid in Internet Explorer 9 en eerdere versies uitschakelt of niet configureert, kunnen gebruikers inhoud van het ene naar het andere domein verslepen als de bron en de bestemming zich in verschillende vensters bevinden. Gebruikers kunnen deze instelling niet wijzigen.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067050)  
  
  **Standaard**: Uitschakelen  
  
- **Internet Explorer: SmartScreen van internetzone**  
  Met deze beleidsinstelling bepaalt u of het SmartScreen-filter pagina's in deze zone scant op schadelijke inhoud. Als u deze beleidsinstelling inschakelt, scant het SmartScreen-filter pagina's in deze zone op schadelijke inhoud. Als u deze beleidsinstelling uitschakelt, scant het SmartScreen-filter geen pagina's in deze zone op schadelijke inhoud. Als u deze beleidsinstelling niet configureert, kan de gebruiker kiezen of het SmartScreen-filter pagina's in deze zone scant op schadelijke inhoud. Opmerking: in Internet Explorer 7 bepaalt deze beleidsinstelling of het phishing-filter pagina's in deze zone scant op schadelijke inhoud.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067047)  
  
  **Standaardinstelling**: ingeschakeld  
  
- **Java-machtigingen voor de vertrouwde zone zijn vergrendeld in Internet Explorer**  
  Met deze beleidsinstelling kunt u machtigingen voor Java-applets beheren. Als u deze beleidsinstelling inschakelt, kunt u opties kiezen in de vervolgkeuzelijst. Aangepast, om instellingen voor machtigingen afzonderlijk te beheren. Met Minimale beveiliging kunnen applets alle bewerkingen uitvoeren. Met Normale beveiliging kunnen applets worden uitgevoerd in hun eigen sandbox (een gebied in het geheugen waarbuiten het programma geen aanroepen kan doen). Daarnaast biedt deze optie mogelijkheden zoals een scratchruimte (een veilig en beveiligd opslaggebied op de clientcomputer) en door de gebruiker beheerde bestandsinvoer en-uitvoer (I/O). Met Strenge beveiliging kunnen applets in hun sandbox worden uitgevoerd. Schakel Java uit om te voorkomen dat er applets worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, kunnen Java-applets niet worden uitgevoerd. Als u deze beleidsinstelling niet configureert, worden Java-applets uitgeschakeld.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067142)  
  
  
  **Standaardinstelling**: Java uitschakelen 
  
- **Internet Explorer: handtekeningen controleren voor gedownloade programma's**  
  Met deze beleidsinstelling kunt u beheren of Internet Explorer digitale handtekeningen (met daarin de naam van de uitgever van ondertekende software, ter verificatie dat de software niet is gewijzigd of gesaboteerd) op computers van gebruikers controleert voordat uitvoerbare bestanden worden gedownload. Als u deze beleidsinstelling inschakelt, zal Internet Explorer de digitale handtekeningen van uitvoerbare programma's controleren en hun identiteit weergeven voordat ze op computers van gebruikers worden gedownload. Als u deze beleidsinstelling uitschakelt, worden in Internet Explorer de digitale handtekeningen van uitvoerbare programma's niet gecontroleerd en wordt hun identiteit niet weergeven voordat ze op computers van gebruikers worden gedownload. Als u dit beleid niet configureert, worden in Internet Explorer de digitale handtekeningen van uitvoerbare programma's niet gecontroleerd en wordt hun identiteit niet weergeven voordat ze op computers van gebruikers worden gedownload.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067051)  
  
  **Standaardinstelling**: ingeschakeld  
  
- **Scripts uitvoeren van webbrowserbesturingselementen in de beperkte zone van Internet Explorer**  
  Met deze beleidsinstelling bepaalt u of op een pagina ingesloten webbrowserbesturingselementen via een script kunnen worden beheerd. Als u deze beleidsinstelling inschakelt, is scripttoegang tot het webbrowserbesturingselement toegestaan. Als u deze beleidsinstelling uitschakelt, is scripttoegang tot het webbrowserbesturingselement niet toegestaan. Als u deze beleidsinstelling niet configureert, kan de gebruiker scripttoegang tot het webbrowserbesturingselement in- of uitschakelen. Standaard is scripttoegang tot het besturingselement WebBrowser alleen toegestaan in de lokale computer en intranetzones.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067098)  
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Internet Explorer: XSS-filters voor beperkte zones**  
  Met dit beleid bepaalt u of het XSS-filter (website-overschrijdende Scripting) website-overschrijdende scriptinjecties in websites in deze zone kan detecteren en voorkomen. Als u deze beleidsinstelling inschakelt, wordt het XSS-filter ingeschakeld voor sites in deze zone en probeert het XSS-filter website-overschrijdende scriptinjecties te blokkeren. Als u deze beleidsinstelling uitschakelt, wordt het XSS-filter uitgeschakeld voor sites in deze zone en staat Internet Explorer website-overschrijdende scriptinjecties toe.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067178)  
  
  **Standaardinstelling**: ingeschakeld  
  
- **Internet Explorer: binair gedrag en scriptgedrag in beperkte zones**  
  Met deze beleidsinstelling kunt u dynamische binaire gedragingen en scriptgedrag beheren: onderdelen die specifieke functionaliteit bevatten voor HTML-elementen waaraan ze zijn gekoppeld. Als u deze beleidsinstelling inschakelt, zijn binair gedrag en scriptgedrag beschikbaar. Als u in de vervolgkeuzelijst Goedgekeurd door beheerder selecteert, is alleen gedrag beschikbaar dat staat vermeld in het door de beheerder goedgekeurde gedrag onder het beveiligingsbeperkingsbeleid Binair gedrag. Als u deze beleidsinstelling uitschakelt, zijn binair gedrag en scriptgedrag niet beschikbaar tenzij voor toepassingen aangepast beveiligingsbeheer is geïmplementeerd. Als u deze beleidsinstelling niet configureert, zijn binair gedrag en scriptgedrag niet beschikbaar tenzij voor toepassingen aangepast beveiligingsbeheer is geïmplementeerd.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067224)  
  
  **Standaard**: Uitschakelen  
  
- **Internet Explorer: beveiligingsinstellingen controleren**  
  Met deze beleidsinstelling schakelt u de functie Controle van beveiligingsinstellingen uit. met deze functie controleert u de beveiligingsinstellingen in Internet Explorer om vast te stellen wanneer de instellingen een risico vormen voor Internet Explorer. Als u deze beleidsinstelling inschakelt, wordt de functie uitgeschakeld. Als u deze beleidsinstelling uitschakelt of niet configureert, wordt de functie ingeschakeld.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067182)  
  
  **Standaardinstelling**: ingeschakeld  
  
- **Internet Explorer: beveiligingswaarschuwing voor mogelijk onveilige bestanden in de internetzone**  
  Met deze beleidsinstelling bepaalt u of het bericht 'Bestand openen - beveiligingswaarschuwing' wordt weergegeven wanneer de gebruiker uitvoerbare bestanden of andere mogelijk onveilige bestanden (van een intranetbestandsshare met de Verkenner, bijvoorbeeld) probeert te openen. Als u deze beleidsinstelling inschakelt en de vervolgkeuzelijst instelt op Inschakelen, worden deze bestanden geopend zonder beveiligingswaarschuwing. Als u de vervolgkeuzelijst instelt op Prompt, wordt een beveiligingswaarschuwing weergegeven voordat de bestanden worden geopend. Als u deze beleidsinstelling uitschakelt, worden deze bestanden niet geopend. Als u deze beleidsinstelling niet configureert, kan de gebruiker configureren hoe de computer deze bestanden verwerkt. Standaard worden deze bestanden geblokkeerd in de beperkte zone, ingeschakeld in de zones Intranet en Lokale computer en ingesteld op Prompt in de zones Internet en Vertrouwd.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067204)  
  
  **Standaardinstelling**: Vragen  
  
- **Java-machtigingen voor de intranetzone in Internet Explorer**  
  Met deze beleidsinstelling kunt u machtigingen voor Java-applets beheren. Als u deze beleidsinstelling inschakelt, kunt u opties kiezen in de vervolgkeuzelijst. Aangepast, om instellingen voor machtigingen afzonderlijk te beheren. Met Minimale beveiliging kunnen applets alle bewerkingen uitvoeren. Met Normale beveiliging kunnen applets worden uitgevoerd in hun eigen sandbox (een gebied in het geheugen waarbuiten het programma geen aanroepen kan doen). Daarnaast biedt deze optie mogelijkheden zoals een scratchruimte (een veilig en beveiligd opslaggebied op de clientcomputer) en door de gebruiker beheerde bestandsinvoer en-uitvoer (I/O). Met Strenge beveiliging kunnen applets in hun sandbox worden uitgevoerd. Schakel Java uit om te voorkomen dat er applets worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, kunnen Java-applets niet worden uitgevoerd. Als u deze beleidsinstelling niet configureert, wordt de machtiging ingesteld op Normale beveiliging.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067206)  
  
  **Standaardinstelling**: Hoge beveiliging 
  
- **Internet Explorer: verouderde ActiveX-besturingselementen blokkeren**   
  Met deze beleidsinstelling bepaalt u of Internet Explorer bepaalde verouderde ActiveX-besturingselementen blokkeert. Verouderde ActiveX-besturingselementen worden nooit geblokkeerd in de intranetzone. Als u deze beleidsinstelling inschakelt, stopt Internet Explorer met het blokkeren van verouderde ActiveX-besturingselementen. Als u deze beleidsinstelling uitschakelt of niet configureert, blijft Internet Explorer bepaalde verouderde ActiveX-besturingselementen blokkeren. Zie Verouderde ActiveX-besturingselementen in de Internet Explorer TechNet-bibliotheek voor meer informatie.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067203)  
  
  **Standaardinstelling**: ingeschakeld  
  
- **Pop-upblokkering in de beperkte zone van Internet Explorer**  
  Met deze beleidsinstelling kunt u beheren of ongewenste pop-upvensters worden weergegeven. Pop-upvensters die worden geopend wanneer de eindgebruiker op een koppeling klikt, worden niet geblokkeerd. Als u deze beleidsinstelling inschakelt, voorkomt u dat de meeste ongewenste pop-upvensters worden weergegeven. Als u deze beleidsinstelling uitschakelt, wordt het weergeven van pop-upvensters niet voorkomen. Als u deze beleidsinstelling niet configureert, voorkomt u dat de meeste ongewenste pop-upvensters worden weergegeven.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067180)  
  
  **Standaardinstelling**: Inschakelen  
  
- **Internet Explorer verwerkt beveiligingsbeperkingen voor het MK-protocol**  
  De beleidsinstelling Beveiligingsbeperking voor het MK-protocol vermindert het beveiligingsrisico door het MK-protocol te voorkomen. Resources die op het MK-protocol worden gehost, zullen mislukken. Als u deze beleidsinstelling inschakelt, wordt het MK-protocol voorkomen voor Verkenner en Internet Explorer en mislukken resources die op het MK-protocol worden gehost. Als u deze beleidsinstelling uitschakelt, kunnen toepassingen de API voor het MK-protocol gebruiken. Resources die op het MK-protocol worden gehost, werken voor de processen in Verkenner en Internet Explorer. Als u deze beleidsinstelling niet configureert, wordt het MK-protocol voorkomen voor de Verkenner en Internet Explorer en mislukken resources die op het MK-protocol worden gehost.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067179)  
  
  **Standaardinstelling**: ingeschakeld  
  
- **Java-machtigingen voor de vertrouwde zone in Internet Explorer**   
  Met deze beleidsinstelling kunt u machtigingen voor Java-applets beheren. Als u deze beleidsinstelling inschakelt, kunt u opties kiezen in de vervolgkeuzelijst. Aangepast, om instellingen voor machtigingen afzonderlijk te beheren. Met Minimale beveiliging kunnen applets alle bewerkingen uitvoeren. Met Normale beveiliging kunnen applets worden uitgevoerd in hun eigen sandbox (een gebied in het geheugen waarbuiten het programma geen aanroepen kan doen). Daarnaast biedt deze optie mogelijkheden zoals een scratchruimte (een veilig en beveiligd opslaggebied op de clientcomputer) en door de gebruiker beheerde bestandsinvoer en-uitvoer (I/O). Met Strenge beveiliging kunnen applets in hun sandbox worden uitgevoerd. Schakel Java uit om te voorkomen dat er applets worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, kunnen Java-applets niet worden uitgevoerd. Als u deze beleidsinstelling niet configureert, wordt de machtiging ingesteld op Lage veiligheid.  
    [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067200)  
  
  **Standaardinstelling**: Hoge beveiliging  
  
- **Internet Explorer: scripts voor Java-applets uitvoeren in de beperkte zone**  
  Met deze beleidsinstelling kunt u beheren of applets beschikbaar worden gemaakt voor scripts in de zone. Als u deze beleidsinstelling inschakelt, hebben scripts automatisch toegang tot applets zonder tussenkomst van de gebruiker. Als u in de vervolgkeuzelijst Vragen selecteert, moeten gebruikers kiezen of ze scripts toegang tot applets willen bieden. Als u deze beleidsinstelling uitschakelt, hebben scripts geen toegang tot applets. Als u deze beleidsinstelling niet configureert, hebben scripts geen toegang tot applets.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067202)  
  
  **Standaard**: Uitschakelen  
  
- **Java-machtigingen voor de beperkte zone zijn vergrendeld in Internet Explorer**   
  Met deze beleidsinstelling kunt u machtigingen voor Java-applets beheren. Als u deze beleidsinstelling inschakelt, kunt u opties kiezen in de vervolgkeuzelijst. Aangepast, om instellingen voor machtigingen afzonderlijk te beheren. Met Minimale beveiliging kunnen applets alle bewerkingen uitvoeren. Met Normale beveiliging kunnen applets worden uitgevoerd in hun eigen sandbox (een gebied in het geheugen waarbuiten het programma geen aanroepen kan doen). Daarnaast biedt deze optie mogelijkheden zoals een scratchruimte (een veilig en beveiligd opslaggebied op de clientcomputer) en door de gebruiker beheerde bestandsinvoer en-uitvoer (I/O). Met Strenge beveiliging kunnen applets in hun sandbox worden uitgevoerd. Schakel Java uit om te voorkomen dat er applets worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, kunnen Java-applets niet worden uitgevoerd. Als u deze beleidsinstelling niet configureert, worden Java-applets uitgeschakeld.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067181)  
  
  **Standaardinstelling**: Java uitschakelen 
  
- **Internet Explorer: alleen goedgekeurde domeinen in de internetzone toestaan om ActiveX-besturingselementen te gebruiken**   
  Met deze beleidsinstelling bepaalt u of de gebruiker wordt gevraagd om toe te staan dat ActiveX-besturingselementen op andere websites worden uitgevoerd dan de website waarop het ActiveX-besturingselement is geïnstalleerd. Als u deze beleidsinstelling inschakelt, wordt de gebruiker vooraf gevraagd of het ActiveX-besturingselement mag worden uitgevoerd vanaf websites in deze zone. De gebruiker kan ervoor kiezen dat het besturingselement vanaf de huidige site of vanaf alle sites kan worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, krijgt de gebruiker niet de sitespecifieke ActiveX-melding te zien en kunnen ActiveX-besturingselementen worden uitgevoerd vanaf alle sites in deze zone.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067091)  
  
  **Standaardinstelling**: ingeschakeld  
  
- **Internet Explorer: alle netwerkpaden opnemen**  
  Internet Explorer: alle netwerkpaden opnemen.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067090)  
  
  **Standaardinstelling**: uitgeschakeld 
  
- **Internet Explorer: beveiligde modus van internetzone**  
  Met deze beleidsinstelling kunt u de functie Beveiligde modus inschakelen. Met behulp van Beveiligde modus kunt u Internet Explorer beschermen tegen misbruikte zwakke plekken door het aantal locaties te verminderen waarnaar Internet Explorer in het register en het bestandssysteem kan schrijven. Als u deze beleidsinstelling inschakelt, wordt Beveiligde modus ingeschakeld. De gebruiker kan Beveiligde modus niet uitschakelen. Als u deze beleidsinstelling uitschakelt, wordt Beveiligde modus uitgeschakeld. De gebruiker kan Beveiligde modus niet inschakelen. Als u deze beleidsinstelling niet configureert, kan de gebruiker Beschermde modus in- of uitschakelen.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067171)  
  
  **Standaardinstelling**: Inschakelen 
  
- **ActiveX-besturingselementen die niet als veilig zijn gemarkeerd initialiseren en als script uitvoeren in de internetzone in Internet Explorer**  
  Met deze beleidsinstelling kunt u ActiveX-besturingselementen beheren die niet als veilig zijn gemarkeerd. Als u deze beleidsinstelling inschakelt, worden ActiveX-besturingselementen uitgevoerd, voorzien van parameters en als script uitgevoerd zonder de veiligheid van objecten in te stellen voor niet-vertrouwde gegevens of scripts. Deze instelling wordt niet aanbevolen, behalve voor veilige en beheerde zones. Deze instelling zorgt dat zowel onveilige als veilige besturingselementen worden geïnitialiseerd en als script worden uitgevoerd. Daarbij worden de ActiveX-besturingselementen van het script die als veilig zijn gemarkeerd, genegeerd. Als u deze beleidsinstelling inschakelt en in de vervolgkeuzelijst Vragen selecteert, worden gebruikers gevraagd of ze willen toestaan dat het besturingselement met parameters wordt geladen of als script wordt uitgevoerd. Als u deze beleidsinstelling uitschakelt, worden ActiveX-besturingselementen die niet veilig kunnen worden ingesteld, niet geladen met parameters of als script uitgevoerd. Als u deze beleidsinstelling niet configureert, worden ActiveX-besturingselementen die niet veilig kunnen worden ingesteld, niet geladen met parameters of als script uitgevoerd.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067170)  
  
  **Standaard**: Uitschakelen 
  
- **Internet Explorer: vergrendeld SmartScreen in beperkte zone**   
  Met deze beleidsinstelling bepaalt u of het SmartScreen-filter pagina's in deze zone scant op schadelijke inhoud. Als u deze beleidsinstelling inschakelt, scant het SmartScreen-filter pagina's in deze zone op schadelijke inhoud. Als u deze beleidsinstelling uitschakelt, scant het SmartScreen-filter geen pagina's in deze zone op schadelijke inhoud. Als u deze beleidsinstelling niet configureert, kan de gebruiker kiezen of het SmartScreen-filter pagina's in deze zone scant op schadelijke inhoud. Opmerking: in Internet Explorer 7 bepaalt deze beleidsinstelling of het phishing-filter pagina's in deze zone scant op schadelijke inhoud.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067092)  
  
  **Standaardinstelling**: ingeschakeld  
  
- **Detectie van Internet Explorer-crashes**  
  Met deze beleidsinstelling kunt u de functie voor het detecteren van crashes in het beheer van invoegtoepassingen beheren. Als u deze beleidsinstelling inschakelt, zal een crash in Internet Explorer het gedrag vertonen dat in Windows XP Professional Servicepack 1 en oudere versies werd waargenomen en Windows Foutrapportage aanroepen. Alle beleidsinstellingen voor Windows Foutrapportage blijven van toepassing. Als u deze beleidsinstelling uitschakelt of niet configureert, is de functie voor het detecteren van crashes in het beheer van invoegtoepassingen actief.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067094)  
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Java-machtigingen voor de internetzone in Internet Explorer**  
  Met deze beleidsinstelling kunt u machtigingen voor Java-applets beheren. Als u deze beleidsinstelling inschakelt, kunt u opties kiezen in de vervolgkeuzelijst. Aangepast, om instellingen voor machtigingen afzonderlijk te beheren. Met Minimale beveiliging kunnen applets alle bewerkingen uitvoeren. Met Normale beveiliging kunnen applets worden uitgevoerd in hun eigen sandbox (een gebied in het geheugen waarbuiten het programma geen aanroepen kan doen). Daarnaast biedt deze optie mogelijkheden zoals een scratchruimte (een veilig en beveiligd opslaggebied op de clientcomputer) en door de gebruiker beheerde bestandsinvoer en-uitvoer (I/O). Met Strenge beveiliging kunnen applets in hun sandbox worden uitgevoerd. Schakel Java uit om te voorkomen dat er applets worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, kunnen Java-applets niet worden uitgevoerd. Als u deze beleidsinstelling niet configureert, wordt de machtiging ingesteld op Hoge veiligheid.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067174)  
  
  **Standaardinstelling**: Java uitschakelen  
  
- **Actieve scripts in de beperkte zone van Internet Explorer**  
  Met deze beleidsinstelling kunt u beheren of scriptcode op pagina's in de zone wordt uitgevoerd. Als u deze beleidsinstelling inschakelt, kan scriptcode op pagina's in de zone automatisch worden uitgevoerd. Als u in de vervolgkeuzelijst Vragen selecteert, moeten gebruikers kiezen of ze willen toestaan dat scripts op pagina's in de zone worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, kan scriptcode op pagina's in de zone niet worden uitgevoerd. Als u deze beleidsinstelling niet configureert, kan scriptcode op pagina's in de zone niet worden uitgevoerd.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067172)  
  
  **Standaard**: Uitschakelen  
  
- **Internet Explorer: aanmeldingsopties voor internetzones**  
  Met deze beleidsinstelling kunt u de instellingen voor aanmeldingsopties beheren. Als u deze beleidsinstelling inschakelt, kunt u kiezen uit de volgende aanmeldingsopties. Anoniem aanmelden om HTTP-verificatie uit te schakelen en het gastaccount alleen gebruiken voor het CIFS-protocol (Common Internet File System). Om een gebruikersnaam en wachtwoord vragen om een query te maken voor de gebruikers-id's en wachtwoorden van gebruikers. Nadat een query voor een gebruiker is uitgevoerd, kunnen deze waarden op de achtergrond worden gebruikt gedurende de rest van de sessie. Alleen automatisch aanmelden in de intranetzone om een query uit te voeren voor de gebruikers-id's en wachtwoorden in andere zones. Nadat een query voor een gebruiker is uitgevoerd, kunnen deze waarden op de achtergrond worden gebruikt gedurende de rest van de sessie. Automatisch aanmelden met de huidige gebruikersnaam en het huidige wachtwoord om te proberen aan te melden met behulp van Windows NT-vraag-antwoord (ook wel NTLM-verificatie genoemd). Als Windows NT-vraag-antwoord door de server wordt ondersteund, gebruikt de aanmelding de gebruikersnaam en het wachtwoord van de gebruiker voor het netwerk om de gebruiker aan te melden. Als Windows NT-vraag-antwoord niet door de server wordt ondersteund, wordt de gebruiker gevraagd om de gebruikersnaam en het wachtwoord op te geven. Als u deze beleidsinstelling uitschakelt, wordt de aanmelding ingesteld op Alleen automatisch aanmelden in de intranetzone. Als u deze beleidsinstelling niet configureert, wordt de aanmelding ingesteld op Alleen automatisch aanmelden in de intranetzone.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067194)  
  
  **Standaardinstelling**: Vragen  
  
- **Beperkte zone van Internet Explorer: uitvoeren van VBScript toestaan**   
  Met deze beleidsinstelling kunt u beheren VBScript kan worden uitgevoerd op pagina's via de opgegeven zone in Internet Explorer. Als u in de vervolgkeuzelijst Inschakelen hebt geselecteerd, kan VBScript worden uitgevoerd zonder tussenkomst van de gebruiker. Als u in de vervolgkeuzelijst Vragen hebt geselecteerd, worden gebruikers gevraagd of ze willen toestaan dat VBScript wordt uitgevoerd. Als u in de vervolgkeuzelijst Uitschakelen hebt geselecteerd, wordt voorkomen dat VBScript wordt uitgevoerd. Als u deze beleidsinstelling niet configureert of uitschakelt, kan VBScript niet worden uitgevoerd.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067173)  
  
  **Standaard**: Uitschakelen  
  
- **Beperkte zone van Internet Explorer: inhoud van verschillende domeinen verslepen tussen vensters**  
  Met deze beleidsinstelling kunt u opties instellen voor het verslepen van inhoud van het ene naar het andere domein wanneer de bron en de bestemming zich in verschillende vensters bevinden. Als u deze beleidsinstelling inschakelt en op Inschakelen klikt, kunnen gebruikers inhoud van het ene naar het andere domein verslepen wanneer de bron en de bestemming zich in verschillende vensters bevinden. Gebruikers kunnen deze instelling niet wijzigen. Als u deze beleidsinstelling inschakelt en op Uitschakelen klikt, kunnen gebruikers geen inhoud van het ene naar het andere domein verslepen als de bron en de bestemming zich in verschillende vensters bevinden. Gebruikers kunnen deze instelling niet wijzigen. Als u deze beleidsinstelling in Internet Explorer 10 uitschakelt of niet configureert, kunnen gebruikers geen inhoud van het ene naar het andere domein verslepen wanneer de bron en de bestemming zich in verschillende vensters bevinden. Gebruikers kunnen deze instelling wijzigen in het dialoogvenster Internetopties. Als u dit beleid in Internet Explorer 9 en eerdere versies uitschakelt of niet configureert, kunnen gebruikers inhoud van het ene naar het andere domein verslepen als de bron en de bestemming zich in verschillende vensters bevinden. Gebruikers kunnen deze instelling niet wijzigen.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067093)  
  
  **Standaardinstelling**: uitgeschakeld 
  
- **Intranetzone van Internet Explorer: ActiveX-besturingselementen die niet als veilig zijn gemarkeerd, initialiseren en als script uitvoeren**  
  Met deze beleidsinstelling kunt u ActiveX-besturingselementen beheren die niet als veilig zijn gemarkeerd. Als u deze beleidsinstelling inschakelt, worden ActiveX-besturingselementen uitgevoerd, voorzien van parameters en als script uitgevoerd zonder de veiligheid van objecten in te stellen voor niet-vertrouwde gegevens of scripts. Deze instelling wordt niet aanbevolen, behalve voor veilige en beheerde zones. Deze instelling zorgt dat zowel onveilige als veilige besturingselementen worden geïnitialiseerd en als script worden uitgevoerd. Daarbij worden de ActiveX-besturingselementen van het script die als veilig zijn gemarkeerd, genegeerd. Als u deze beleidsinstelling inschakelt en in de vervolgkeuzelijst Vragen selecteert, worden gebruikers gevraagd of ze willen toestaan dat het besturingselement met parameters wordt geladen of als script wordt uitgevoerd. Als u deze beleidsinstelling uitschakelt, worden ActiveX-besturingselementen die niet veilig kunnen worden ingesteld, niet geladen met parameters of als script uitgevoerd. Als u deze beleidsinstelling niet configureert, worden ActiveX-besturingselementen die niet veilig kunnen worden ingesteld, niet geladen met parameters of als script uitgevoerd.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067175)  
  
  **Standaard**: Uitschakelen 
  
- **Internet Explorer: bijlagen downloaden**  
  Met deze beleidsinstelling kunt u voorkomen dat de gebruiker bestandsbijlagen via een feed naar de computer van de gebruiker downloadt. Als u deze beleidsinstelling inschakelt, kan de gebruiker de feedsynchronisatie-engine niet zodanig instellen dat een bijlage wordt gedownload via de eigenschappenpagina van een feed. Een ontwikkelaar kan de downloadinstelling niet wijzigen via de feed-API's. Als u deze beleidsinstelling uitschakelt of niet configureert, kan de gebruiker de feedsynchronisatie-engine zodanig instellen dat een bijlage wordt gedownload via de eigenschappenpagina van een feed. Een ontwikkelaar kan de downloadinstelling wijzigen via de feed-API's.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067245)  
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Beperkte zone van Internet Explorer: niet-ondertekende Active X-besturingselementen downloaden**  
  Met deze beleidsinstelling kunt u beheren of gebruikers niet-ondertekende ActiveX-besturingselementen in de zone kunnen downloaden. Een dergelijke code is mogelijk schadelijk, vooral als deze afkomstig is van een niet-vertrouwde zone. Als u deze beleidsinstelling inschakelt, kunnen gebruikers niet-ondertekende besturingselementen uitvoeren zonder tussenkomst van de gebruiker. Als u in de vervolgkeuzelijst Vragen selecteert, moeten gebruikers kiezen of ze het niet-ondertekende besturingselement wel of niet laten uitvoeren. Als u deze beleidsinstelling uitschakelt, kunnen gebruikers niet-ondertekende besturingselementen niet uitvoeren. Als u deze beleidsinstelling niet configureert, kunnen gebruikers niet-ondertekende besturingselementen niet uitvoeren.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067177)  
  
  **Standaard**: Uitschakelen  
  
- **Beperkte zone van Internet Explorer: inhoud van verschillende domeinen verslepen binnen vensters**  
  Met deze beleidsinstelling kunt u beheren of gebruikers niet-ondertekende ActiveX-besturingselementen in de zone kunnen downloaden. Een dergelijke code is mogelijk schadelijk, vooral als deze afkomstig is van een niet-vertrouwde zone. Als u deze beleidsinstelling inschakelt, kunnen gebruikers niet-ondertekende besturingselementen uitvoeren zonder tussenkomst van de gebruiker. Als u in de vervolgkeuzelijst Vragen selecteert, moeten gebruikers kiezen of ze het niet-ondertekende besturingselement wel of niet laten uitvoeren. Als u deze beleidsinstelling uitschakelt, kunnen gebruikers niet-ondertekende besturingselementen niet uitvoeren. Als u deze beleidsinstelling niet configureert, kunnen gebruikers niet-ondertekende besturingselementen niet uitvoeren.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067095)  
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Processen van Internet Explorer: installeren van Active X beperken**   
  Met deze beleidsinstelling kan in toepassingen die het webbrowserbesturingselement hosten het automatisch vragen om het ActiveX-besturingselement te installeren, worden geblokkeerd. Als u deze beleidsinstelling inschakelt, wordt het automatisch vragen om het ActiveX-besturingselement te installeren, geblokkeerd met het webbrowserbesturingselement. Als u deze beleidsinstelling uitschakelt of niet configureert, wordt het automatisch vragen om het ActiveX-besturingselement te installeren, niet geblokkeerd met het webbrowserbesturingselement.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067250)  
  
  **Standaardinstelling**: ingeschakeld  
  
- **Internet Explorer internet zone scriptlets**  
  Met deze beleidsinstelling kunt u beheren of gebruikers scriptlets kunnen uitvoeren. Als u deze beleidsinstelling inschakelt, kan de gebruiker scriptlets uitvoeren. Als u deze beleidsinstelling uitschakelt, kan de gebruiker geen scriptlets uitvoeren. Als u deze beleidsinstelling niet configureert, kan de gebruiker scriptlets in- of uitschakelen.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067176)  
  
  **Standaard**: Uitschakelen  
  
- **Beperkte zone van Internet Explorer: bestanden slepen en neerzetten of kopiëren en plakken**  
  Met deze beleidsinstelling kunt u beheren of gebruikers bestanden kunnen slepen of kunnen kopiëren slepen en plakken vanuit een bron binnen de zone. Als u deze beleidsinstelling inschakelt, kunnen gebruikers automatisch bestanden slepen of bestanden kopiëren en plakken vanuit deze zone. Als u in de vervolgkeuzelijst Vragen selecteert, moeten gebruikers kiezen of ze bestanden willen slepen of kopiëren vanuit deze zone. Als u deze beleidsinstelling uitschakelt, kunnen geen bestanden slepen of kopiëren en plakken vanuit deze zone. Als u deze beleidsinstelling niet configureert, moeten gebruikers kiezen of ze bestanden willen slepen of kopiëren vanuit deze zone.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067096)  
  
  **Standaard**: Uitschakelen  
  
- **Software van Internet Explorer: bij ongeldige handtekening**  
  Met deze beleidsinstelling kunt u beheren of software, bijvoorbeeld ActiveX-besturingselementen en bestandsdownloads, kunnen worden uitgevoerd of geïnstalleerd door de gebruiker als de handtekening ongeldig is. Een ongeldige handtekening kan erop wijzen dat iemand het bestand onrechtmatig heeft gewijzigd. Als u deze beleidsinstelling inschakelt, worden gebruikers gevraagd of ze bestanden met een ongeldige handtekening willen uitvoeren of installeren. Als u deze beleidsinstelling uitschakelt, kunnen gebruikers bestanden met een ongeldige handtekening niet uitvoeren of installeren. Als u deze beleidsinstelling niet configureert, kunnen gebruikers kiezen of ze bestanden met een ongeldige handtekening willen uitvoeren of installeren.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067201)
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Beperkte zone van Internet Explorer: kopiëren en plakken via scripts**  
  Met deze beleidsinstelling kunt u beheren of met scripts een klembordbewerking (zoals knippen, kopiëren en plakken) kan worden uitgevoerd in een opgegeven regio. Als u deze beleidsinstelling inschakelt, kan met een script een klembordbewerking worden uitgevoerd. Als u in de vervolgkeuzelijst Vragen selecteert, moeten gebruikers kiezen of ze klembordbewerkingen willen uitvoeren. Als u deze beleidsinstelling uitschakelt, kan er met een script geen klembordbewerking worden uitgevoerd. Als u deze beleidsinstelling niet configureert, kan met een script geen klembordbewerking worden uitgevoerd.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067165)  
  
  **Standaard**: Uitschakelen  
  
- **Beperkte zone van Internet Explorer: inhoud van verschillende domeinen in de verslepen tussen vensters**  
  Met deze beleidsinstelling kunt u opties instellen voor het verslepen van inhoud van het ene naar het andere domein wanneer de bron en de bestemming zich in verschillende vensters bevinden. Als u deze beleidsinstelling inschakelt en op Inschakelen klikt, kunnen gebruikers inhoud van het ene naar het andere domein verslepen wanneer de bron en de bestemming zich in verschillende vensters bevinden. Gebruikers kunnen deze instelling niet wijzigen. Als u deze beleidsinstelling inschakelt en op Uitschakelen klikt, kunnen gebruikers geen inhoud van het ene naar het andere domein verslepen als de bron en de bestemming zich in verschillende vensters bevinden. Gebruikers kunnen deze instelling niet wijzigen. Als u deze beleidsinstelling in Internet Explorer 10 uitschakelt of niet configureert, kunnen gebruikers geen inhoud van het ene naar het andere domein verslepen wanneer de bron en de bestemming zich in verschillende vensters bevinden. Gebruikers kunnen deze instelling wijzigen in het dialoogvenster Internetopties. Als u dit beleid in Internet Explorer 9 en eerdere versies uitschakelt of niet configureert, kunnen gebruikers inhoud van het ene naar het andere domein verslepen als de bron en de bestemming zich in verschillende vensters bevinden. Gebruikers kunnen deze instelling niet wijzigen.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067166)   

  **Standaardinstelling**: uitgeschakeld  
  
- **Gebruikers die websites toevoegen in Internet Explorer**  
  Hiermee wordt voorkomen dat gebruikers websites toevoegen aan of verwijderen uit beveiligingszones. Een beveiligingszone is een groep websites met hetzelfde beveiligingsniveau. Als u dit beleid inschakelt, worden de instellingen voor het beheren van websites voor beveiligingszones uitgeschakeld. (Klik in het dialoogvenster Internetopties op het tabblad Beveiliging en klik daarna op de knop Websites om de instellingen voor websitebeheer voor beveiligingszones weer te geven.) Als u dit beleid uitschakelt of niet configureert, kunnen gebruikers websites toevoegen aan of verwijderen uit de zones Vertrouwde websites en Beperkte websites. Ook kunnen ze de instellingen voor de zone Lokaal intranet aanpassen. Met dit beleid voorkomt u dat gebruikers de instellingen voor het beheren van websites wijzigen voor beveiligingszones die door de beheerder zijn gemaakt. Opmerking: met het beleid De beveiligingspagina uitschakelen (in \User Configuration\Administrative Templates\Windows Components\Internet Explorer\Internet Control Panel) verwijdert u het tabblad Beveiliging in de interface. Dit heeft voorrang ten opzichte van dit beleid. Dit beleid wordt genegeerd als deze optie is ingeschakeld. Zie ook het beleid Beveiligingszones: alleen computerinstellingen gebruiken.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067167)  
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Internet Explorer: door script geïnitieerde vensters in de internetzone**  
  Met deze beleidsinstelling kunt u beperkingen beheren voor door scripts geïnitieerde pop-upvensters en vensters die een titel en statusbalken bevatten. Als u deze beleidsinstelling inschakelt, is de beveiliging door Windows-beperkingen niet van toepassing in deze zone. De beveiligingszone wordt uitgevoerd zonder de toegevoegde beveiligingslaag van deze functie. Als u deze beleidsinstelling uitschakelt, kunnen mogelijk schadelijke acties in door scripts geïnitieerde pop-upvensters en vensters die een titel en statusbalken bevatten, niet worden uitgevoerd. Deze beveiligingsfunctie van Internet Explorer is in deze zone ingeschakeld, zoals dat door de instelling van de functie Gescripte Windows-beveiligingsbeperkingen voor het proces is opgegeven. Als u deze beleidsinstelling niet configureert, kunnen mogelijk schadelijke acties in door scripts geïnitieerde pop-upvensters en vensters die een titel en statusbalken bevatten, niet worden uitgevoerd. Deze beveiligingsfunctie van Internet Explorer is in deze zone ingeschakeld, zoals dat door de instelling van de functie Gescripte Windows-beveiligingsbeperkingen voor het proces is opgegeven.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067088)  
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Internet Explorer: alleen computerinstellingen gebruiken in beveiligingszones**  
  Hiermee past u informatie over de beveiligingszone toe op alle gebruikers met dezelfde computer. Een beveiligingszone is een groep websites met hetzelfde beveiligingsniveau. Als u dit beleid inschakelt, worden wijzigingen die de gebruiker in een beveiligingszone toepast op alle gebruikers van die computer toegepast. Als u dit beleid uitschakelt of niet configureert, kunnen gebruikers van dezelfde computer hun eigen instellingen voor de beveiligingszone instellen. Gebruik dit beleid om ervoor te zorgen dat instellingen voor beveiligingszones eenduidig op dezelfde computer worden toegepast en niet per gebruiker verschillen. Zie ook het beleid Beveiligingszones: gebruikers niet toestaan om beleid te wijzigen.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067086)  
  
  **Standaardinstelling**: ingeschakeld  
  
- **Java-machtigingen voor de vergrendelde zone Lokale machine in Internet Explorer**  
  Met deze beleidsinstelling kunt u machtigingen voor Java-applets beheren. Als u deze beleidsinstelling inschakelt, kunt u opties kiezen in de vervolgkeuzelijst. Aangepast, om instellingen voor machtigingen afzonderlijk te beheren. Met Minimale beveiliging kunnen applets alle bewerkingen uitvoeren. Met Normale beveiliging kunnen applets worden uitgevoerd in hun eigen sandbox (een gebied in het geheugen waarbuiten het programma geen aanroepen kan doen). Daarnaast biedt deze optie mogelijkheden zoals een scratchruimte (een veilig en beveiligd opslaggebied op de clientcomputer) en door de gebruiker beheerde bestandsinvoer en-uitvoer (I/O). Met Strenge beveiliging kunnen applets in hun sandbox worden uitgevoerd. Schakel Java uit om te voorkomen dat er applets worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, kunnen Java-applets niet worden uitgevoerd. Als u deze beleidsinstelling niet configureert, worden Java-applets uitgeschakeld.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067253) 
  
  **Standaardinstelling**: Java uitschakelen 
  
- **Er wordt geen antimalware uitgevoerd op ActiveX-besturingselementen in de beperkte zone van Internet Explorer**   
  Met deze beleidsinstelling wordt bepaald of Internet Explorer antimalwareprogramma's uitvoert op ActiveX-besturingselementen om te controleren of ze veilig zijn om te laden op pagina's. Als u deze beleidsinstelling inschakelt, controleert Internet Explorer niet met uw antimalware-programma om te zien of het veilig is om een exemplaar van het ActiveX-besturingselement te installeren. Als u deze beleidsinstelling uitschakelt, controleert Internet Explorer altijd met uw antimalware-programma om te zien of het veilig is om een exemplaar van het ActiveX-besturingselement te installeren. Als u deze beleidsinstelling niet configureert, controleert Internet Explorer altijd met uw antimalware-programma om te zien of het veilig is om een exemplaar van het ActiveX-besturingselement te installeren. Gebruikers kunnen dit gedrag in- of uitschakelen met de beveiligingsinstellingen van Internet Explorer.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067089)
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Internet Explorer: onderdelen in de beperkte zone uitvoeren die afhankelijk zijn van .NET Framework en zijn ondertekend met Authenticode**  
  Met deze beleidsinstelling kunt u beheren of .NET Framework-onderdelen die met Authenticode zijn ondertekend, kunnen worden uitgevoerd in Internet Explorer. Deze onderdelen bevatten beheerde besturingselementen waarnaar vanuit een objectlabel wordt verwezen en beheerde uitvoerbare bestanden waarnaar vanuit een koppeling wordt verwezen. Als u deze beleidsinstelling inschakelt, zal Internet Explorer ondertekende beheerde onderdelen uitvoeren. Als u in de vervolgkeuzelijst Vragen selecteert, wordt de gebruiker gevraagd om te bepalen of ondertekende beheerde onderdelen moeten worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, zal Internet Explorer ondertekende beheerde onderdelen niet uitvoeren. Als u deze beleidsinstelling niet configureert, worden ondertekende beheerde onderdelen niet uitgevoerd in Internet Explorer.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067169)  
  
  **Standaard**: Uitschakelen  
  
- **Internet Explorer: toegang tot gegevensbronnen via een beperkte zone**  
  Met deze beleidsinstelling kunt u beheren of Internet Explorer toegang heeft tot gegevens van een andere beveiligingszone met behulp van de Microsoft XML-parser (MSXML) of ActiveX-gegevensobjecten (ADO). Als u deze beleidsinstelling inschakelt, kunnen gebruikers een pagina laden in de zone die MSXML of ADO gebruikt voor toegang tot gegevens van een andere site in de zone. Als u Prompt selecteert in de vervolgkeuzelijst, wordt gebruikers gevraagd om te kiezen of een pagina mag worden geladen in de zone die MSXML of ADO gebruikt voor toegang tot gegevens van een andere site in de zone. Als u deze beleidsinstelling uitschakelt, kunnen gebruikers geen pagina laden in de zone die MSXML of ADO gebruikt voor toegang tot gegevens van een andere site in de zone. Als u deze beleidsinstelling niet configureert, kunnen gebruikers geen pagina laden in de zone die MSXML of ADO gebruikt voor toegang tot gegevens van een andere site in de zone.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067161)  
  
  **Standaard**: Uitschakelen 
  
- **Er wordt geen antimalware uitgevoerd op ActiveX-besturingselementen in de internetzone van Internet Explorer**  
  Met deze beleidsinstelling wordt bepaald of Internet Explorer antimalwareprogramma's uitvoert op ActiveX-besturingselementen om te controleren of ze veilig zijn om te laden op pagina's. Als u deze beleidsinstelling inschakelt, controleert Internet Explorer niet met uw antimalware-programma om te zien of het veilig is om een exemplaar van het ActiveX-besturingselement te installeren. Als u deze beleidsinstelling uitschakelt, controleert Internet Explorer altijd met uw antimalware-programma om te zien of het veilig is om een exemplaar van het ActiveX-besturingselement te installeren. Als u deze beleidsinstelling niet configureert, controleert Internet Explorer altijd met uw antimalware-programma om te zien of het veilig is om een exemplaar van het ActiveX-besturingselement te installeren. Gebruikers kunnen dit gedrag in- of uitschakelen met de beveiligingsinstellingen van Internet Explorer.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067162)  
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Internet Explorer: kopiëren en plakken via een script in de internetzone**  
  Met deze beleidsinstelling kunt u beheren of met scripts een klembordbewerking (zoals knippen, kopiëren en plakken) kan worden uitgevoerd in een opgegeven regio. Als u deze beleidsinstelling inschakelt, kan met een script een klembordbewerking worden uitgevoerd. Als u in de vervolgkeuzelijst Vragen selecteert, moeten gebruikers kiezen of ze klembordbewerkingen willen uitvoeren. Als u deze beleidsinstelling uitschakelt, kan er met een script geen klembordbewerking worden uitgevoerd. Als u deze beleidsinstelling niet configureert, kan een script een klembordbewerking uitvoeren.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067084)  
  
  **Standaard**: Uitschakelen  
  
- **Internet Explorer: de ActiveX Installer-service gebruiken**  
  Met deze beleidsinstelling kunt u opgeven hoe ActiveX-besturingselementen worden geïnstalleerd. Als u deze beleidsinstelling inschakelt, wordt ActiveX-besturingselementen alleen geïnstalleerd als de Installer-service aanwezig is en is geconfigureerd om de installatie van ActiveX-besturingselementen toe te staan. Als u deze beleidsinstelling uitschakelt of niet configureert, worden ActiveX-besturingselementen, inclusief besturingselementen per gebruiker, geïnstalleerd via het gewone installatieproces.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067163)
  
  **Standaardinstelling**: ingeschakeld  
  
- **Internet Explorer verwerkt bescherming tegen zone-uitbreiding**  
  Internet Explorer kent beperkingen toe aan elke webpagina die wordt geopend. De beperkingen zijn afhankelijk van de locatie van de webpagina (internet-, intranet-, lokale computer-zone, enzovoort). Voor webpagina's op de lokale computer gelden bijvoorbeeld minder beveiligingsbeperkingen, terwijl deze in de zone Lokale computer verblijven, waardoor de beveiligingszone Lokale computer een belangrijk doelwit is voor kwaadwillende gebruikers. Als u deze beleidsinstelling inschakelt, kan elke zone worden beschermd tegen zone-uitbreiding voor alle processen. Als u deze beleidsinstelling uitschakelt of niet configureert, genieten andere processen dan Internet Explorer of processen in de lijst Proceslijst deze bescherming niet.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067160)  
  
  **Standaardinstelling**: ingeschakeld  
  
- **Niet-ondertekende Active X-besturingselementen downloaden in internetzone van Internet Explorer**   
  Met deze beleidsinstelling kunt u beheren of gebruikers niet-ondertekende ActiveX-besturingselementen in de zone kunnen downloaden. Een dergelijke code is mogelijk schadelijk, vooral als deze afkomstig is van een niet-vertrouwde zone. Als u deze beleidsinstelling inschakelt, kunnen gebruikers niet-ondertekende besturingselementen uitvoeren zonder tussenkomst van de gebruiker. Als u in de vervolgkeuzelijst Vragen selecteert, moeten gebruikers kiezen of ze het niet-ondertekende besturingselement wel of niet laten uitvoeren. Als u deze beleidsinstelling uitschakelt, kunnen gebruikers niet-ondertekende besturingselementen niet uitvoeren. Als u deze beleidsinstelling niet configureert, kunnen gebruikers niet-ondertekende besturingselementen niet uitvoeren.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067325)
  
  **Standaard**: Uitschakelen  
  
- **Vensters en frames door verschillende domeinen laten navigeren in de Internet Explorer-internetzone**   
  Met deze beleidsinstelling kunt u het openen van vensters en frames en de toegang tot toepassingen in verschillende domeinen beheren. Als u deze beleidsinstelling inschakelt, kunnen gebruikers vensters en frames openen vanuit andere domeinen en toegang krijgen tot toepassingen van andere domeinen. Als u Vragen in de vervolgkeuzelijst selecteert, wordt aan gebruikers gevraagd of vensters en frames toegang mogen hebben tot toepassingen van andere domeinen. Als u deze beleidsinstelling uitschakelt, kunnen gebruikers geen vensters en frames openen om toegang te krijgen tot toepassingen vanuit andere domeinen. Als u deze beleidsinstelling niet configureert, kunnen gebruikers vensters en frames openen vanuit andere domeinen en toegang krijgen tot toepassingen van andere domeinen.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067083)  
  
  **Standaard**: Uitschakelen  
  
- **Updates van de statusbalk vinden plaats in de Internet Explorer-internetzone via script**  
  Met deze beleidsinstelling kunt u regelen of de statusbalk in de zone via script mag worden bijgewerkt. Als u deze beleidsinstelling inschakelt, kunnen scripts de statusbalk bijwerken. Als u deze beleidsinstelling uitschakelt of niet configureert, mag de statusbalk niet worden bijgewerkt via script.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067087)  
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Lokaal pad wordt tijdens het uploaden van bestanden naar de server opgenomen in de beperkte zone van Internet Explorer**  
  Met deze beleidsinstelling bepaalt u of gegevens over het lokale pad worden verzonden wanneer de gebruiker een bestand uploadt via een HTML-formulier. Als er gegevens over het lokale pad zijn verzonden, wordt mogelijk bepaalde informatie onbedoeld op de server weergegeven. Bestanden die vanaf het bureaublad van de gebruiker zijn verzonden, bevatten bijvoorbeeld mogelijk de gebruikersnaam als onderdeel van het pad. Als u deze beleidsinstelling inschakelt, worden gegevens over het pad verzonden wanneer de gebruiker een bestand via een HTML-formulier uploadt. Als u deze beleidsinstelling uitschakelt, worden gegevens over het pad verwijderd wanneer de gebruiker een bestand via een HTML-formulier uploadt. Als u deze beleidsinstelling niet configureert, kan de gebruiker kiezen of gegevens over het pad worden verzonden wanneer ze een bestand uploaden via een HTML-formulier. Standaard worden gegevens over het pad verzonden.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067085)  
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Het downloaden van bestanden beperken in processen van Internet Explorer**   
  Met deze beleidsinstelling wordt in toepassingen die het webbrowserbesturingselement hosten een blokkering ingesteld van het automatisch vragen om niet door de gebruiker geïnitialiseerde downloads van bestanden. Als u deze beleidsinstelling inschakelt, wordt in toepassingen die het webbrowserbesturingselement hosten voor alle processen een blokkering ingesteld van het automatisch vragen om niet door de gebruiker geïnitialiseerde downloads van bestanden. Als u deze beleidsinstelling uitschakelt, wordt in toepassingen die het webbrowserbesturingselement hosten voor alle processen geen blokkering ingesteld van het automatisch vragen om niet door de gebruiker geïnitialiseerde downloads van bestanden.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067164)  
  
  **Standaardinstelling**: ingeschakeld  
  
- **Alleen goedgekeurde domeinen mogen Active X-besturingselementen gebruiken in de beperkt zone van Internet Explorer**   
  Met deze beleidsinstelling bepaalt u of de gebruiker wordt gevraagd om toe te staan dat ActiveX-besturingselementen op andere websites worden uitgevoerd dan de website waarop het ActiveX-besturingselement is geïnstalleerd. Als u deze beleidsinstelling inschakelt, wordt de gebruiker vooraf gevraagd of het ActiveX-besturingselement mag worden uitgevoerd vanaf websites in deze zone. De gebruiker kan ervoor kiezen dat het besturingselement vanaf de huidige site of vanaf alle sites kan worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, krijgt de gebruiker niet de sitespecifieke ActiveX-melding te zien en kunnen ActiveX-besturingselementen worden uitgevoerd vanaf alle sites in deze zone.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067233)  
  
  **Standaardinstelling**: ingeschakeld  
  
- **ActiveX-besturingselementen die niet als veilig zijn gemarkeerd initialiseren en als script uitvoeren in de beperkte zone in Internet Explorer**  
  Met deze beleidsinstelling kunt u ActiveX-besturingselementen beheren die niet als veilig zijn gemarkeerd. Als u deze beleidsinstelling inschakelt, worden ActiveX-besturingselementen uitgevoerd, voorzien van parameters en als script uitgevoerd zonder de veiligheid van objecten in te stellen voor niet-vertrouwde gegevens of scripts. Deze instelling wordt niet aanbevolen, behalve voor veilige en beheerde zones. Deze instelling zorgt dat zowel onveilige als veilige besturingselementen worden geïnitialiseerd en als script worden uitgevoerd. Daarbij worden de ActiveX-besturingselementen van het script die als veilig zijn gemarkeerd, genegeerd. Als u deze beleidsinstelling inschakelt en in de vervolgkeuzelijst Vragen selecteert, worden gebruikers gevraagd of ze willen toestaan dat het besturingselement met parameters wordt geladen of als script wordt uitgevoerd. Als u deze beleidsinstelling uitschakelt, worden ActiveX-besturingselementen die niet veilig kunnen worden ingesteld, niet geladen met parameters of als script uitgevoerd. Als u deze beleidsinstelling niet configureert, worden ActiveX-besturingselementen die niet veilig kunnen worden ingesteld, niet geladen met parameters of als script uitgevoerd.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067097)  
  
  **Standaard**: Uitschakelen  
  
- **Gebruikers van Internet Explorer die beleidsregels wijzigen**  
  Hiermee voorkomt u dat gebruikers instellingen voor beveiligingszones wijzigen. Een beveiligingszone is een groep websites met hetzelfde beveiligingsniveau. Als u dit beleid inschakelt, worden de knop Aangepast niveau en de schuifregelaar voor het beveiligingsniveau op het tabblad Beveiliging in het dialoogvenster Internetopties uitgeschakeld. Als u dit beleid uitschakelt of niet configureert, kunnen gebruikers de instellingen voor beveiligingszones wijzigen. Met dit beleid voorkomt u dat gebruikers de instellingen voor beveiligingszones die door de beheerder zijn gemaakt, kunnen wijzigen. Opmerking: het beleid 'De pagina Beveiliging uitschakelen' (te vinden in \Gebruikersconfiguratie\Beheersjablonen\Windows-onderdelen\Internet Explorer\Onderdeel Internetopties van het Configuratiescherm), waardoor het tabblad Beveiliging uit Internet Explorer in Configuratiescherm wordt verwijderd, heeft voorrang op dit beleid. Dit beleid wordt genegeerd als deze optie is ingeschakeld. Zie ook het beleid Beveiligingszones: alleen computerinstellingen gebruiken.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067155)  
    
  **Standaardinstelling**: uitgeschakeld  
  
- **Beveiligde modus van de beperkte zone van Internet Explorer**  
  Met deze beleidsinstelling kunt u de functie Beveiligde modus inschakelen. Met behulp van Beveiligde modus kunt u Internet Explorer beschermen tegen misbruikte zwakke plekken door het aantal locaties te verminderen waarnaar Internet Explorer in het register en het bestandssysteem kan schrijven. Als u deze beleidsinstelling inschakelt, wordt Beveiligde modus ingeschakeld. De gebruiker kan Beveiligde modus niet uitschakelen. Als u deze beleidsinstelling uitschakelt, wordt Beveiligde modus uitgeschakeld. De gebruiker kan Beveiligde modus niet inschakelen. Als u deze beleidsinstelling niet configureert, kan de gebruiker Beschermde modus in- of uitschakelen.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067080)  
  
  **Standaardinstelling**: Inschakelen  
  
- **Persistentie van gebruikersgegevens in de internetzone van Internet Explorer**  
  Met deze beleidsinstelling kunt u het bewaren van gegevens beheren in de geschiedenis van de browser, in Favorieten, in een XML-archief of direct in op een schijf opgeslagen webpagina's. Wanneer een gebruiker naar een permanent bewaarde pagina terugkeert, kan de status van de pagina worden hersteld als deze beleidsinstelling op de juiste wijze is geconfigureerd. Als u deze beleidsinstelling inschakelt, kunnen gebruikers informatie bewaren in de geschiedenis van de browser, in Favorieten, in een XML-archief of direct in op een schijf opgeslagen webpagina's. Als u deze beleidsinstelling uitschakelt, kunnen gebruikers geen informatie bewaren in de geschiedenis van de browser, in Favorieten, in een XML-archief of direct in op een schijf opgeslagen webpagina's. Als u deze beleidsinstelling niet configureert, kunnen gebruikers geen informatie bewaren in de geschiedenis van de browser, in Favorieten, in een XML-archief of direct in op een schijf opgeslagen webpagina's.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067156)  
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Scripts uitvoeren van webbrowserbesturingselementen in de internetzone van Internet Explorer**  
 
  Met deze beleidsinstelling bepaalt u of op een pagina ingesloten webbrowserbesturingselementen via een script kunnen worden beheerd. Als u deze beleidsinstelling inschakelt, is scripttoegang tot het webbrowserbesturingselement toegestaan. Als u deze beleidsinstelling uitschakelt, is scripttoegang tot het webbrowserbesturingselement niet toegestaan. Als u deze beleidsinstelling niet configureert, kan de gebruiker scripttoegang tot het webbrowserbesturingselement in- of uitschakelen. Standaard is scripttoegang tot het besturingselement WebBrowser alleen toegestaan in de lokale computer en intranetzones.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067157)  
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Persistentie van gebruikersgegevens in de beperkte zone van Internet Explorer**  
  Met deze beleidsinstelling kunt u het bewaren van gegevens beheren in de geschiedenis van de browser, in Favorieten, in een XML-archief of direct in op een schijf opgeslagen webpagina's. Wanneer een gebruiker naar een permanent bewaarde pagina terugkeert, kan de status van de pagina worden hersteld als deze beleidsinstelling op de juiste wijze is geconfigureerd. Als u deze beleidsinstelling inschakelt, kunnen gebruikers informatie bewaren in de geschiedenis van de browser, in Favorieten, in een XML-archief of direct in op een schijf opgeslagen webpagina's. Als u deze beleidsinstelling uitschakelt, kunnen gebruikers geen informatie bewaren in de geschiedenis van de browser, in Favorieten, in een XML-archief of direct in op een schijf opgeslagen webpagina's. Als u deze beleidsinstelling niet configureert, kunnen gebruikers informatie bewaren in de geschiedenis van de browser, in Favorieten, in een XML-archief of direct in op een schijf opgeslagen webpagina's.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067081)  
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Java-machtigingen voor de intranetzone zijn in Internet Explorer vergrendeld**  
  Met deze beleidsinstelling kunt u machtigingen voor Java-applets beheren. Als u deze beleidsinstelling inschakelt, kunt u opties kiezen in de vervolgkeuzelijst. Aangepast, om instellingen voor machtigingen afzonderlijk te beheren. Met Minimale beveiliging kunnen applets alle bewerkingen uitvoeren. Met Normale beveiliging kunnen applets worden uitgevoerd in hun eigen sandbox (een gebied in het geheugen waarbuiten het programma geen aanroepen kan doen). Daarnaast biedt deze optie mogelijkheden zoals een scratchruimte (een veilig en beveiligd opslaggebied op de clientcomputer) en door de gebruiker beheerde bestandsinvoer en-uitvoer (I/O). Met Strenge beveiliging kunnen applets in hun sandbox worden uitgevoerd. Schakel Java uit om te voorkomen dat er applets worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, kunnen Java-applets niet worden uitgevoerd. Als u deze beleidsinstelling niet configureert, worden Java-applets uitgeschakeld.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067082)  
  
  **Standaardinstelling**: Java uitschakelen  
  
- **Uitgebreide beveiligde modus van Internet Explorer**  
  De uitgebreide beveiligde modus biedt extra bescherming tegen schadelijke websites door gebruik te maken van 64-bits processen op 64-bits versies van Windows. Op computers met minimaal Windows 8 beperkt de uitgebreide beveiligde modus ook de locaties die Internet Explorer in het register en bestandssysteem kan lezen. Als u deze beleidsinstelling inschakelt, wordt Uitgebreide beveiligde modus ingeschakeld. Voor elke zone waarvoor Beveiligde modus is ingeschakeld, wordt Uitgebreide beveiligde modus gebruikt. Gebruikers kunnen Uitgebreide beveiligde modus niet uitschakelen. Als u deze beleidsinstelling uitschakelt, wordt Uitgebreide beveiligde modus uitgeschakeld. In een zone waarvoor Beveiligde modus is ingeschakeld, wordt de Beveiligde modus-versie gebruikt die is geïntroduceerd in Internet Explorer 7 voor Windows Vista. Als u dit beleid niet configureert, kunnen gebruikers Uitgebreide beveiligde modus inschakelen of uitschakelen op het tabblad Geavanceerd van het dialoogvenster Internetopties.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067158)  
  
  **Standaardinstelling**: ingeschakeld  
  
- **SmartScreen-waarschuwingen negeren in Internet Explorer**  
  Met deze beleidsinstelling bepaalt u of de gebruiker waarschuwingen van het SmartScreen-filter kan negeren. Het SmartScreen-filter waarschuwt de gebruiker voor uitvoerbare bestanden die Internet Explorer-gebruikers normaalgesproken niet van internet downloaden. Als u deze beleidsinstelling inschakelt, wordt de gebruiker door waarschuwingen van het SmartScreen-filter geblokkeerd. Als u deze beleidsinstelling uitschakelt of niet configureert, kan de gebruiker waarschuwingen van het SmartScreen-filter negeren.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067159)  
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Metagegevens vernieuwen in de beperkte zone van Internet Explorer**  
  Met deze beleidsinstelling kunt u bepalen of de browser van een gebruiker kan worden omgeleid naar een andere webpagina als de auteur van de webpagina met behulp van de instelling Metagegevens vernieuwen (tag) browsers omleidt naar een andere webpagina. Als u deze beleidsinstelling inschakelt, kan de browser van een gebruiker waarmee een pagina met een geactiveerde instelling Metagegevens vernieuwen wordt geladen, worden omgeleid naar een andere webpagina. Als u deze beleidsinstelling uitschakelt, kan de browser van een gebruiker waarmee een pagina met een geactiveerde instelling Metagegevens vernieuwen wordt geladen, niet worden omgeleid naar een andere webpagina. Als u deze beleidsinstelling niet configureert, kan de browser van een gebruiker waarmee een pagina met een geactiveerde instelling Metagegevens vernieuwen wordt geladen, niet worden omgeleid naar een andere webpagina.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067154)  
  
  **Standaardinstelling**: uitgeschakeld  
  
## <a name="local-policies-security-options"></a>Beveiligingsopties voor lokaal beleid
Zie [Beleids-CSP - LocalPoliciesSecurityOptions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions) in de Windows-documentatie voor meer informatie. 

- **Anonieme toegang tot named pipes en shares beperken**  
  Wanneer dit is ingeschakeld, wordt met deze beveiligingsinstelling anonieme toegang beperkt tot shares en pipes voor de instellingen van: (1) named pipes die anoniem kunnen worden benaderd (2) shares die anoniem kunnen worden benaderd.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067212)  
  
  **Standaardinstelling**: Ja  
  
- **Minimale sessiebeveiliging voor op NTLM SSP-gebaseerde servers**  
  Via deze beveiligingsinstelling kan een server de onderhandeling van een 128-bits versleuteling en/of een NTLMv2-sessiebeveiliging vereisen. Deze waarden zijn afhankelijk van de beveiligingsinstellingswaarde van het LAN Manager-verificatieniveau. De opties zijn: NTLMv2-sessiebeveiliging vereisen: de verbinding mislukt als niet over berichtintegriteit wordt onderhandeld. 128-bits versleuteling vereisen. De verbinding mislukt als niet wordt onderhandeld over sterke versleuteling (128-bits).  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067246) 
  
  **Standaardinstelling**: NTLM V2 en 128-bits versleuteling vereisen  
  
- **Minuten van inactiviteit van vergrendelingsscherm totdat de schermbeveiliging wordt geactiveerd**  
  Een aanmeldingssessie zonder activiteit wordt opgemerkt door Windows. Als de inactieve tijd de ingestelde limiet voor inactiviteit overschrijdt, wordt de schermbeveiliging ingeschakeld en wordt de sessie vergrendeld.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067210)  
  
  **Standaardinstelling**: 15
  
- **De client verplichten om altijd communicatie digitaal te ondertekenen** Met deze beveiligingsinstelling bepaalt u of al het verkeer via beveiligde kanalen dat is geïnitialiseerd door het domeinlid moet worden ondertekend of versleuteld. Wanneer een computer lid wordt van een domein, wordt een computeraccount gemaakt. Wanneer het systeem daarna wordt gestart, wordt het wachtwoord van het computeraccount gebruikt om een beveiligd kanaal te maken met een domeincontroller voor het domein. Dit beveiligde kanaal wordt gebruikt om bewerkingen uit te voeren zoals NTLM-PassThrough-verificatie, LSA SID/Name Lookup en meer. Met deze instelling bepaalt u of alle verkeer via beveiligde kanalen dat is geïnitialiseerd door een domeinlid aan de minimale beveiligingsvereisten voldoet. Hiermee bepaalt u specifiek of al het verkeer via beveiligde kanalen dat is gestart door een domeinlid moet worden ondertekend of versleuteld. Als dit beleid is ingeschakeld, dan wordt het beveiligde kanaal pas ingesteld als is onderhandeld over de ondertekening of versleuteling van al het verkeer via beveiligde kanalen. Als dit beleid is uitgeschakeld, wordt met de domeincontroller onderhandeld over de versleuteling en ondertekening van al het verkeer via beveiligde kanalen. In dat geval is het niveau van ondertekening en versleuteling afhankelijk van de domeincontrollerversie en de instellingen van de volgende twee beleidsregels: Lid van domein: gegevens in beveiligd kanaal digitaal versleutelen (indien mogelijk) Lid van domein: gegevens in beveiligd kanaal digitaal ondertekenen (indien mogelijk).  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067187) 
  
  **Standaardinstelling**: Ja
  
- **Verificatieniveau**  
  Met deze beveiligingsinstelling bepaalt u welk vraag/antwoord-verificatieprotocol wordt gebruikt voor netwerkaanmeldingen. Deze keuze is als volgt van invloed op het niveau van het verificatieprotocol dat wordt gebruikt door clients, het sessiebeveiligingsniveau dat is onderhandeld en het verificatieniveau dat is geaccepteerd door servers:  
  - *LM- en NTLM-antwoorden verzenden*: clients gebruiken LM- en NTLM-verificatie en gebruiken nooit NTLMv2-sessiebeveiliging; domeincontrollers accepteren LM-, NTLM- en NTLMv2-verificatie. 
  - *LM en NTLM verzenden - NTLMv2 indien onderhandeld*: clients gebruiken LM- en NTLM-verificatie en gebruiken NTLMv2-sessiebeveiliging als de server dit ondersteunt; domeincontrollers accepteren LM-, NTLM- en NTLMv2-verificatie. 
  - *Alleen NTLM-antwoord verzenden*: clients gebruiken alleen NTLM-verificatie en gebruiken NTLMv2-sessiebeveiliging als de server dit ondersteunt; domeincontrollers accepteren LM-, NTLM- en NTLMv2-verificatie. 
  - *Alleen NTLMv2-antwoord verzenden*: clients gebruiken alleen NTLMv2-verificatie en gebruiken NTLMv2-sessiebeveiliging als de server dit ondersteunt; domeincontrollers accepteren LM-, NTLM- en NTLMv2-verificatie. 
  - *Alleen NTLMv2-antwoord verzenden. LM weigeren*: clients gebruiken alleen NTLMv2-verificatie en gebruiken NTLMv2-sessiebeveiliging als de server dit ondersteunt; domeincontrollers weigeren LM (accepteren alleen NTLM- en NTLMv2-verificatie). 
  - *Alleen NTLMv2-antwoord verzenden. LM en NTLM weigeren*: clients gebruiken alleen NTLMv2-verificatie en gebruiken NTLMv2-sessiebeveiliging als de server dit ondersteunt; domeincontrollers weigeren LM en NTLM (accepteren alleen NTLMv2-verificatie).  

  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067189)   
    
  **Standaardinstelling**: alleen NTLMv2-antwoord verzenden. LM en NTLM weigeren
  
- **Voorkomen dat clients niet-versleutelde wachtwoorden verzenden naar de SMB-servers van derden**  
  Als deze beveiligingsinstelling is ingeschakeld, kan de SMB-redirector (Server Message Block) ongecodeerde wachtwoorden verzenden naar niet-Microsoft SMB-servers die geen ondersteuning voor wachtwoordversleuteling bieden tijdens verificatie. Niet-versleutelde wachtwoorden verzenden is een beveiligingsrisico.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067235)  
  
  **Standaardinstelling**: Ja
  
- **Servercommunicatie digitaal ondertekenen altijd vereisen**  
  Met deze beveiligingsinstelling wordt bepaald of de SMB-client probeert te onderhandelen over ondertekening van het SMB-pakket. Het SMB-protocol (Server Message Block) vormt de basis voor bestands- en printerdeling van Microsoft en veel andere netwerkbewerkingen, zoals extern Windows-beheer. Ter voorkoming van man-in-the-middle-aanvallen waardoor SMB-pakketten in-transit worden gewijzigd, ondersteunt het SMB-protocol de digitale ondertekening van SMB-pakketten. Met deze beleidsinstelling wordt bepaald of de SMB-clientonderdeel probeert te onderhandelen over SMB-pakketondertekening wanneer deze verbinding maakt met een SMB-server. Als deze beveiligingsinstelling is ingeschakeld, vraagt de Microsoft-netwerkclient de server om SMB-pakketondertekening uit te voeren bij het instellen van een sessie. Als pakketondertekening is ingeschakeld op de server, wordt over ondertekening van pakketten onderhandeld. Als dit beleid is uitgeschakeld, onderhandelt de SMB-client nooit over SMB-pakketondertekening.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067319)  
  
  **Standaardinstelling**: Ja
  
- **Gedrag bij vragen om uitbreiding van bevoegdheden van beheerders**  
  Met deze beleidsinstelling wordt het gedrag voor het vragen om uitbreiding van bevoegdheden voor beheerders gedefinieerd. U kunt kiezen uit de volgende opties: 
    - *Verhogen zonder te vragen*: hiermee kunnen bevoegde accounts een bewerking uitvoeren waarvoor uitbreiding van bevoegdheden zonder toestemming of referenties is vereist. Opmerking: gebruik deze optie alleen in de meest beperkte omgevingen. 
    - *Vragen om referenties op het beveiligde bureaublad*: wanneer voor een bewerking onrechtmatige uitbreiding van toegangsrechten is vereist, wordt de gebruiker op het beveiligde bureaublad gevraagd een bevoegde gebruikersnaam en bevoegd wachtwoord in te voeren. Als de gebruiker geldige referenties invoert, wordt de bewerking voortgezet met de hoogst beschikbare bevoegdheid. 
    - *Vragen om toestemming op het beveiligde bureaublad*: wanneer voor een bewerking voor een niet-Windows-toepassing uitbreiding van toegangsrechten is vereist, wordt de gebruiker op het beveiligde bureaublad gevraagd om Toestaan of Weigeren te selecteren. Als de gebruiker Toestaan selecteert, wordt de bewerking voortgezet met de hoogst beschikbare bevoegdheid voor de gebruiker. 
    - *Vragen om referenties*: wanneer voor een bewerking onrechtmatige uitbreiding van toegangsrechten is vereist, wordt de gebruiker gevraagd een gebruikersnaam en wachtwoord voor een account met beheerdersrechten in te voeren. Als de gebruiker geldige referenties invoert, wordt de bewerking voortgezet met de toepasselijke bevoegdheid. 
    - *Vragen om toestemming*: wanneer voor een bewerking uitbreiding van toegangsrechten is vereist, wordt de gebruiker gevraagd om Toestaan of Weigeren te selecteren. Als de gebruiker Toestaan selecteert, wordt de bewerking voortgezet met de hoogst beschikbare bevoegdheid voor de gebruiker.  
    - *Vragen om toestemming voor niet-Windows binaire bestanden*: wanneer voor een bewerking voor een niet-Windows-toepassing uitbreiding van toegangsrechten is vereist, wordt de gebruiker op het beveiligde bureaublad gevraagd om Toestaan of Weigeren te selecteren. Als de gebruiker Toestaan selecteert, wordt de bewerking voortgezet met de hoogst beschikbare bevoegdheid voor de gebruiker. 
  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067215)   
  
  **Standaardinstelling**: vragen om toestemming op het beveiligde bureaublad
  
- **Minimale sessiebeveiliging voor op NTLM SSP-gebaseerde clients**  
  Via deze beveiligingsinstelling kan een client de onderhandeling van een 128-bits versleuteling en/of een NTLMv2-sessiebeveiliging vereisen. Deze waarden zijn afhankelijk van de beveiligingsinstellingswaarde van het LAN Manager-verificatieniveau. U kunt kiezen uit de volgende opties:
  - *NTLMv2-sessiebeveiliging vereisen*: de verbinding mislukt als niet over het NTLMv2-protocol wordt onderhandeld. 
  - *128-bits versleuteling vereisen*: de verbinding mislukt als niet wordt onderhandeld over sterke versleuteling (128-bits).
  - *NTLMv2 en 128-bits versleuteling vereisen*.  

  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067324)  

  **Standaardinstelling**: NTLM V2-128-versleuteling vereisen
  
- **Gedrag bij verwijderen van smartcard**  
    Met deze beveiligingsinstelling bepaalt u wat er gebeurt wanneer de smartcard van een aangemelde gebruiker uit de lezer van de smartcard wordt verwijderd. U kunt kiezen uit de volgende opties:
     - *Geen actie*. 
     - *Werkstation vergrendelen*: het werkstation wordt vergrendeld wanneer de smartcard wordt verwijderd, zodat gebruikers de ruimte kunnen verlaten, hun smartcard met zich mee kunnen nemen en nog steeds een beveiligde sessie kunnen beheren.
     - *Afmelden forceren*: de gebruiker wordt automatisch afgemeld wanneer de smartcard wordt verwijderd.
     - *Verbinding verbreken met sessie met Extern bureaublad*: als de smartcard wordt verwijderd, wordt de sessie verbroken zonder de gebruiker af te melden. Zo kan de gebruiker de smartcard plaatsen en de sessie later of op een andere met smartcardlezer uitgeruste computer hervatten zonder zich opnieuw te moeten aanmelden. Als de sessie lokaal is, werkt dit beleid op dezelfde manier als Werkstation vergrendelen.
  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067331) 
    
  **Standaardinstelling**: Werkstation vergrendelen
  
- **Anonieme inventarisatie van SAM-accounts en -shares blokkeren**  
  Met deze beveiligingsinstelling bepaalt u of anonieme inventarisatie van SAM-accounts en shares is toegestaan. Windows staat anonieme gebruikers toe bepaalde activiteiten uit te voeren, zoals het inventariseren van de namen van domeinaccounts en netwerkshares. Dit is bijvoorbeeld handig wanneer een beheerder toegang wil verlenen aan gebruikers in een vertrouwd domein dat geen wederzijdse vertrouwensrelatie onderhoudt. Als u anonieme inventarisatie van SAM-accounts en shares niet wilt toestaan, stelt u dit beleid in op *Ja*.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067191)  
  
  **Standaardinstelling**: Ja
  
- **Externe aanmelding met een leeg wachtwoord blokkeren**  
  Met deze beveiligingsinstelling bepaalt u of de lokale accounts die niet zijn beveiligd met een wachtwoord kunnen worden gebruikt om aan te melden vanaf andere locaties dan de fysieke computerconsole. Bij inschakeling moet voor aanmelden met lokale accounts die niet zijn beveiligd met een wachtwoord het toetsenbord van de computer worden gebruikt. 

  *Waarschuwing*: op computers die zich niet in een fysiek beveiligde locatie bevinden, moeten altijd beleidsregels voor sterke wachtwoorden voor alle lokale gebruikersaccounts worden gehandhaafd. Anders kan iedereen die fysiek toegang tot de computer heeft, zich aanmelden met een gebruikersaccount zonder wachtwoord. Dit is met name belangrijk voor draagbare computers. 

  Als u dit beveiligingsbeleid toepast op de groep Iedereen, kan niemand zich aanmelden via Extern bureaublad-services. Deze instelling heeft geen invloed op aanmeldingen die gebruikmaken van domeinaccounts. Voor toepassingen die gebruikmaken van externe interactieve aanmeldingen is het mogelijk om deze instelling te omzeilen.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067219)  
  
  **Standaardinstelling**: Ja
  
- **Gedrag bij vragen om benodigde bevoegdheden van standaardgebruikers**  
  Met deze beleidsinstelling wordt het gedrag voor het vragen om benodigde bevoegdheden voor standaardgebruikers gedefinieerd. 
  - *Aanvragen voor benodigde bevoegdheden automatisch weigeren*: wanneer voor een bewerking onrechtmatige uitbreiding van toegangsrechten is vereist, wordt een configureerbaar foutbericht weergegeven met de melding dat de toegang is geweigerd. Een onderneming waar bureaubladen als standaardgebruikers worden uitgevoerd, kan deze instelling kiezen om het aantal telefoontje naar de helpdesk te beperken. 
  - *Vragen om referenties op het beveiligde bureaublad*: wanneer voor een bewerking onrechtmatige uitbreiding van toegangsrechten is vereist, wordt de gebruiker op het beveiligde bureaublad gevraagd een andere gebruikersnaam en bevoegd wachtwoord in te voeren. Als de gebruiker geldige referenties invoert, wordt de bewerking voortgezet met de toepasselijke bevoegdheid. 
  - *Vragen om referenties*: wanneer voor een bewerking onrechtmatige uitbreiding van toegangsrechten is vereist, wordt de gebruiker gevraagd een gebruikersnaam en wachtwoord voor een account met beheerdersrechten in te voeren. Als de gebruiker geldige referenties invoert, wordt de bewerking voortgezet met de toepasselijke bevoegdheid.  

  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067183)  
  
  **Standaardinstelling**: aanvragen voor benodigde bevoegdheden automatisch weigeren
  
- **Modus 'Door administrator goedkeuren' vereisen voor beheerders**  
  Met deze beleidsinstelling wordt het gedrag van alle instellingen voor Gebruikersaccountbeheer (UAC) voor de computer bepaald. Als u deze instelling wijzigt, moet u de computer opnieuw opstarten. U kunt kiezen uit de volgende opties:   
  - *Niet geconfigureerd*: de modus Door administrator goedkeuren en alle gerelateerde UAC-beleidsinstellingen zijn uitgeschakeld. Opmerking: als deze instelling is uitgeschakeld, ontvangt u een melding van Security Center dat de algehele beveiliging van het besturingssysteem is verminderd. 
  - *Ja*: de modus Door administrator goedkeuren is ingeschakeld. Dit beleid moet zijn ingeschakeld en de gerelateerde UAC-beleidsinstellingen moeten op de juiste wijze zijn ingesteld om ervoor te zorgen dat het ingebouwde administratoraccount en alle andere gebruikers die lid zijn van de groep Administrators kunnen worden uitgevoerd in de modus Door administrator goedkeuren.  

  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067184)  
  
  **Standaardinstelling**: Ja
  
- **Anonieme inventarisatie van SAM-accounts voorkomen**  
  Met deze beveiligingsinstelling wordt bepaald welke aanvullende machtigingen worden toegekend aan anonieme verbindingen met de computer. Windows staat anonieme gebruikers toe bepaalde activiteiten uit te voeren, zoals het inventariseren van de namen van domeinaccounts en netwerkshares. Dit is bijvoorbeeld handig wanneer een beheerder toegang wil verlenen aan gebruikers in een vertrouwd domein dat geen wederzijdse vertrouwensrelatie onderhoudt. Met deze beveiligingsoptie kunnen als volgt aanvullende beperkingen voor anonieme verbinding worden toegepast: 
  - *Ja*: geen inventarisatie van SAM-accounts toestaan. Met deze optie wordt de instelling Iedereen bij de beveiligingsmachtigingen voor resources vervangen door Geverifieerde gebruikers.
  - *Niet geconfigureerd*: geen aanvullende beperkingen. Vertrouwen op standaardmachtigingen.  
  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067318)  

  **Standaardinstelling**: Ja
  
- **Externe aanroepen van Security Accounts Manager toestaan**  
  Met deze beleidsinstelling kunt u verbindingen voor externe procedureaanroepen van SAM beperken. Als deze instelling niet is geselecteerd, wordt de standaard security descriptor gebruikt.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067209)  
  
  **Standaardinstelling**: *O:BAG:BAD:(A;;RC;;;BA)*

- **De modus 'Door administrator goedkeuren' gebruiken**  
  Met deze beleidsinstelling wordt het gedrag van de modus 'Door administrator goedkeuren' voor het ingebouwde administratoraccount bepaald. U kunt kiezen uit de volgende opties: 
  - *Ja*: de modus Door administrator goedkeuren wordt gebruikt voor het ingebouwde administratoraccount. Voor elke bewerking waarvoor onrechtmatige uitbreiding van toegangsrechten is vereist, wordt de gebruiker standaard gevraagd de bewerking goed te keuren. 
  - *Niet geconfigureerd*: met het ingebouwde administrator worden alle toepassingen met volledige administratorbevoegdheid uitgevoerd. 

  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067186)  

  **Standaardinstelling**: Ja
  
- **Toepassingen met UI-toegang toestaan voor veilige locaties**  
  Met deze beleidsinstelling wordt bepaald of UIA-programma's (User Interface Accessibility of UIAcces) het beveiligde bureaublad automatisch kunnen uitschakelen voor het vragen om benodigde bevoegdheden die door een standaardgebruiker. 
  - *Ja*: UIA-programma's, waaronder Windows Hulp op afstand, kunnen automatisch het beveiligde bureaublad uitschakelen bij vragen om benodigde bevoegdheden. Als u de beleidsinstelling Gebruikersaccountbeheer: naar het beveiligd bureaublad overschakelen tijdens het vragen om benodigde bevoegdheden niet uitschakelt, worden de vragen weergegeven op het bureaublad van de interactieve gebruiker in plaats op van het beveiligde bureaublad. 
  - *Niet geconfigureerd*: het beveiligde bureaublad kan alleen worden uitgeschakeld door de gebruiker van het interactieve bureaublad of door het uitschakelen van de beleidsinstelling Gebruikersaccountbeheer: naar het beveiligde bureaublad overschakelen tijdens het vragen om benodigde bevoegdheden.  

  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067185)  

  **Standaardinstelling**: Ja

- **Installatie van toepassingen detecteren en vragen om benodigde bevoegdheden**  
  Met deze beleidsinstelling wordt het gedrag van detectie voor installatie van toepassingen voor de computer bepaald. U kunt kiezen uit de volgende opties: 
  - *Ingeschakeld*: wanneer een installatiepakket van een toepassing wordt gedetecteerd waarvoor onrechtmatige uitbreiding van toegangsrechten is vereist, wordt de gebruiker gevraagd een gebruikersnaam en wachtwoord voor een account met beheerdersrechten in te voeren. Als de gebruiker geldige referenties invoert, wordt de bewerking voortgezet met de toepasselijke bevoegdheid. 
  - *Uitgeschakeld*: installatiepakketten voor toepassingen worden niet gedetecteerd en worden niet om benodigde bevoegdheden gevraagd. Ondernemingen waar bureaubladen als standaardgebruikers worden uitgevoerd en die gebruikmaken van gedelegeerde installatietechnologieën, zoals Installatie van software van groepsbeleid of Systems Management Server (SMS), moeten deze beleidsinstelling uitschakelen. In dit geval is de detectie van installatieprogramma's niet nodig.  
  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067208)  

  **Standaardinstelling**: Ja
  
- **Voorkomen dat de hashwaarde van LAN manager wordt opgeslagen opslaan bij volgende wachtwoordwijziging**  
  Met deze beveiligingsinstelling wordt bepaald of bij de volgende wachtwoordwijziging de hashwaarde van LAN Manager (LM) voor het nieuwe wachtwoord wordt opgeslagen. De LM-hash is relatief zwak en gevoelig voor aanvallen in vergelijking met de cryptografisch sterkere NT-hash van Windows. Omdat de LM-hash in de beveiligingsdatabase van de lokale computer wordt opgeslagen, kunnen de wachtwoorden worden aangetast als de beveiligingsdatabase wordt aangevallen.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067213)  
  
  **Standaardinstelling**: Ja

- **Schrijffouten in bestanden en registers in locaties per gebruiker virtualiseren**  
  Met deze beleidsinstelling wordt bepaald of schrijffouten voor toepassingen worden omgeleid naar gedefinieerde register- en bestandssysteemlocaties. Met deze beleidsinstelling worden toepassingen beperkt die als administrator worden uitgevoerd en waarvoor toepassingsgegevens van de runtime naar *%ProgramFiles%* , *%Windir%* , *%Windir%\system32* of *HKLM\Software* worden schrijven.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067321)  
  
  **Standaardinstelling**: Ja

## <a name="ms-security-guide"></a>MS-beveiligingshandleiding  
Raadpleeg [Policy CSP - MSSecurityGuide](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mssecurityguide) (Beleids-CSP - MSSecurityGuide) in de Windows-documentatie voor meer informatie.  

- **UAC-beperkingen toepassen op lokale accounts bij netwerkaanmelding**  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067188)  

  **Standaardinstelling**: ingeschakeld
  
- **Configuratie voor starten van stuurprogramma voor SMB-v1-client**  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067214) 
 
  **Standaardinstelling**: uitgeschakeld stuurprogramma
  
- **SMB-v1-server**  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067190)  

  **Standaardinstelling**: uitgeschakeld
  
- **Samenvattingsverificatie**  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067193) 
 
  **Standaardinstelling**: uitgeschakeld
  
- **SEHOP (Structured Exception Handler Overwrite Protection)**  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067217)  

  **Standaardinstelling**: ingeschakeld
  
## <a name="mss-legacy"></a>MSS Legacy  
Raadpleeg [Policy CSP - MSSLegacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-msslegacy) (Beleids-CSP - MSSLegacy) in de Windows-documentatie voor meer informatie.  

- **Beveiligingsniveau voor routering van IP-bron voor netwerk**  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067220)  
  
  **Standaardinstelling**: hoogste beveiliging  
  
- **Aanvragen voor NetBIOS-naamreleases van netwerk negeren met uitzondering van WINS-servers**  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067218)  
 
  **Standaardinstelling**: ingeschakeld
  
- **Beveiligingsniveau voor routering van IPv6-bron voor netwerk**  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067216)  

  **Standaardinstelling**: hoogste beveiliging

- **ICMP-omleidingen van netwerk overschrijven door OSPF gegenereerde omleidingen**  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067326)  

  **Standaardinstelling**: uitgeschakeld
  
## <a name="power"></a>Voeding  
Raadpleeg [Policy CSP - Power](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power) (Beleids-CSP - Voeding) in de Windows-documentatie voor meer informatie.  

- **Wachtwoord bij activering vereisen tijdens aansluiting op netstroom**  
  Met deze beleidsinstelling kunt u opgeven of de gebruiker om een wachtwoord wordt gevraagd als de slaapstand wordt uitgeschakeld. Als u deze beleidsinstelling inschakelt of niet configureert, wordt de gebruiker om een wachtwoord gevraagd wanneer de slaapstand wordt uitgeschakeld. Als u deze beleidsinstelling uitschakelt, wordt de gebruiker niet om een wachtwoord gevraagd wanneer de slaapstand wordt uitgeschakeld.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067221)  
  
  **Standaardinstelling**: ingeschakeld
  
- **Stand-bystatussen tijdens slaapstand bij gebruik van accu**  
  Met deze beleidsinstelling wordt bepaald of de stand-bystatussen kunnen worden ingeschakeld met Windows wanneer de computer in de slaapstand wordt gezet. Als u deze beleidsinstelling inschakelt of niet configureert, worden in Windows de stand-bystatussen gebruikt om de computer in een slaapstand te zetten. Als u deze beleidsinstelling uitschakelt, zijn de stand-bystatussen (S1-S3) niet toegestaan.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067195)  
  
  **Standaardinstelling**: uitgeschakeld
  
- **Stand-bystatussen tijdens slaapstand in aangesloten toestand**  
  Met deze beleidsinstelling wordt bepaald of de stand-bystatussen kunnen worden ingeschakeld met Windows wanneer de computer in de slaapstand wordt gezet. Als u deze beleidsinstelling inschakelt of niet configureert, worden in Windows de stand-bystatussen gebruikt om de computer in een slaapstand te zetten. Als u deze beleidsinstelling uitschakelt, zijn de stand-bystatussen (S1-S3) niet toegestaan.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067196)  
  
  **Standaardinstelling**: uitgeschakeld
  
- **Wachtwoord bij activering vereisen bij gebruik van accu**  
  Met deze beleidsinstelling kunt u opgeven of de gebruiker om een wachtwoord wordt gevraagd als de slaapstand wordt uitgeschakeld. Als u deze beleidsinstelling inschakelt of niet configureert, wordt de gebruiker om een wachtwoord gevraagd wanneer de slaapstand wordt uitgeschakeld. Als u deze beleidsinstelling uitschakelt, wordt de gebruiker niet om een wachtwoord gevraagd wanneer de slaapstand wordt uitgeschakeld.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067322)  
  
  **Standaardinstelling**: ingeschakeld

## <a name="remote-assistance"></a>Hulp op afstand
- **Hulp op afstand aangevraagde**  
  Met deze beleidsinstelling kunt u inschakelen of uitschakelen van Hulp op afstand op deze computer aangevraagde (Ask voor). 
  - *Als u deze beleidsinstelling inschakelt*, kunnen gebruikers op deze computer e-mailbericht of bestand overdracht gebruiken om iemand anders om hulp vragen. Bovendien kunnen gebruikers chatprogramma gebruiken om verbindingen met deze computer toestaan en kunt u aanvullende hulp op afstand-instellingen configureren. 
  - *Als u deze beleidsinstelling uitschakelt*, gebruikers op deze computer niet e-mailbericht of bestand overdracht gebruiken om aan te vragen voor meer informatie over. Gebruikers niet chatprogramma ook gebruiken om toe te staan van verbindingen op deze computer. 
  - *Als u deze beleidsinstelling niet configureert*, gebruikers kunnen inschakelen of uitschakelen hulp op afstand van aangevraagde (Ask voor) zich in de eigenschappen van het systeem in het Configuratiescherm. Gebruikers kunnen ook hulp op afstand-instellingen configureren. 

  Als u deze beleidsinstelling inschakelt, hebt u twee manieren om toe te staan van hulpprogramma's voor hulp op afstand: 'Toestaan hulpprogramma's naar de weergave alleen de computer' of 'Hulpprogramma's voor het extern beheren van de computer toestaan'. De 'Maximum ticket time' beleidsinstelling een limiet op de hoeveelheid tijd die stelt een uitnodiging voor een Hulp op afstand gemaakt met behulp van e-mailbericht of bestand overdracht kan blijven open zijn. De "Selecteer de methode voor het verzenden van e-mailbericht uitnodigingen" instelling geeft u aan welke standaard e-mailadres gebruiken om hulp op afstand uitnodigingen te verzenden. Afhankelijk van uw e-mailprogramma, kunt u de standaard Mailto (de ontvanger uitnodiging verbinding maakt via een internetkoppeling) of de SMAPI (eenvoudige MAPI) standaard (de uitnodiging is gekoppeld aan uw e-mailbericht). Met deze beleidsinstelling is niet beschikbaar in Windows Vista omdat SMAPI de enige methode ondersteund is. Als u deze beleidsinstelling inschakelt, moet u ook juiste firewall-uitzonderingen om hulp op afstand-communicatie inschakelen.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067198)

  **Standaard**: hulp op afstand uitschakelen

  Als de waarde *hulp op afstand inschakelen*, de volgende aanvullende instellingen configureren:  
  - **Hulp op afstand aangevraagde machtiging**  
    **Standaard**: weergeven  

  - **Maximale ticket tijd-waarde**  
    **Standaard**: *niet geconfigureerd*  

  - **Maximale ticket periode**  
    **Standaard**: minuten    

  - **E-mailuitnodiging methode**  
    **Standaard**: eenvoudige MAPI

  
## <a name="remote-desktop-services"></a>Extern bureaublad-services  
Zie [Beleids-CSP - RemoteDesktopServices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotedesktopservices) in de Windows-documentatie voor meer informatie.  

- **Wachtwoord opslaan blokkeren**  
  Hiermee bepaalt u of wachtwoorden op deze computer kunnen worden opgeslagen vanuit een verbinding met extern bureaublad. Als u deze instelling inschakelt, wordt het selectievakje voor het opslaan van het wachtwoord in de verbinding met extern bureaublad uitgeschakeld en kunnen gebruikers niet langer wachtwoorden opslaan. Wanneer gebruikers een RDP-bestand openen met behulp van een verbinding met extern bureaublad en hun instellingen opslaan, wordt een wachtwoord dat voorheen aanwezig was in het RDP-bestand verwijderd. Als u deze instelling uitschakelt of niet configureert, kan de gebruiker met behulp van de verbinding met extern bureaublad wachtwoorden opslaan.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067301)  
  
   **Standaardinstelling**: ingeschakeld
  
- **Beveiligde RPC-communicatie**  
  Hiermee geeft u aan of voor een Remote Desktop Session Host-server beveiligde RPC-communicatie is vereist met alle clients of niet-beveiligde communicatie is toegestaan. U kunt deze instelling gebruiken om de beveiliging van RPC-communicatie met clients te versterken door alleen geverifieerde en versleutelde aanvragen toe te staan. Als de status is ingesteld op Ingeschakeld, accepteert Extern bureaublad-services aanvragen van RPC-clients die ondersteuning bieden voor beveiligde aanvragen en wordt niet-beveiligde communicatie met niet-vertrouwde clients niet toegestaan. Als de status is ingesteld op Uitgeschakeld, vraagt Extern bureaublad-services altijd om beveiliging voor alle RPC-verkeer. Voor RPC-clients die niet op de aanvraag reageren is echter niet-beveiligde communicatie toegestaan. Als de status is ingesteld op Niet geconfigureerd, is niet-beveiligde communicatie toegestaan. Opmerking: de RPC-interface wordt gebruikt voor het beheren en configureren van Extern bureaublad-services.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067248)  
  
  **Standaardinstelling**: ingeschakeld
  
- **Stationsomleiding blokkeren**  
  Met deze beleidsinstelling geeft u aan of u de toewijzing van clientstations in een sessie van Extern bureaublad-services wilt voorkomen (stationsomleiding). Standaard wijst een Extern bureaublad-sessiehostserver clientstations automatisch toe wanneer verbinding wordt gemaakt. Toegewezen stations worden in de structuur van de sessiemap in Verkenner of Computer in de indeling *\<stationsletter>* op *\<computernaam>* weergegeven. Met deze beleidsinstelling kunt u dit gedrag negeren. Als u deze beleidsinstelling inschakelt, is clientstationsomleiding niet toegestaan in sessies van Extern bureaublad-services en is omleiding van kopieën van Klembord-bestanden niet toegestaan op computers met Windows Server 2003, Windows 8 en Windows XP. Als u deze beleidsinstelling uitschakelt, is clientstationsomleiding is altijd toegestaan. Omleiding van kopieën van Klembord-bestanden is bovendien altijd toegestaan als Klembord-omleiding is toegestaan. Als u deze beleidsinstelling niet configureert, worden omleiding van clientstations en omleiding voor kopieën van Klembord-bestanden niet opgegeven op groepsbeleidsniveau.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067197)  
  
  **Standaardinstelling**: ingeschakeld
  
- **Prompt voor wachtwoord bij verbinding maken**  
  Met deze beleidsinstelling geeft u aan of de client in Extern bureaublad-services altijd wordt gevraagd om een wachtwoord wanneer deze verbinding maakt. U kunt deze instelling gebruiken om een wachtwoordprompt af te dwingen voor gebruikers die zich aanmelden bij de Extern bureaublad-services, zelfs als ze het wachtwoord in de client voor Verbinding met extern bureaublad al hebben opgegeven. Standaard kunnen gebruikers zich in Extern bureaublad-services automatisch aanmelden door een wachtwoord op te geven in de client voor Verbinding met extern bureaublad. Als u deze beleidsinstelling inschakelt, kunnen gebruikers zich niet automatisch aanmelden bij Extern bureaublad-services door het opgeven van wachtwoorden in de client voor Verbinding met extern bureaublad. Zij worden bij hun aanmelding gevraagd om een wachtwoord. Als u deze beleidsinstelling uitschakelt, kunnen gebruikers zich altijd automatisch aanmelden bij Extern bureaublad-services door het opgeven van wachtwoorden in de client voor Verbinding met extern bureaublad. Als u deze beleidsinstelling niet configureert, wordt automatische aanmelding niet opgegeven op groepsbeleidsniveau.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067328)  
  
  **Standaardinstelling**: ingeschakeld
  
- **Versleutelingsniveau van Verbinding met extern bureaublad-services**  
  Hiermee geeft u op of het gebruik van een specifiek versleutelingsniveau voor beveiligde communicatie tussen clientcomputers en Extern bureaublad-sessiehostservers tijdens Remote Desktop Protocol (RDP)-verbindingen is vereist. Dit beleid is alleen van toepassing wanneer u systeemeigen RDP-versleuteling gebruikt. Systeemeigen RDP-versleuteling (in plaats van SSL-versleuteling) wordt echter niet aanbevolen. Dit beleid geldt niet voor SSL-versleuteling. Als u deze beleidsinstelling inschakelt, moet in alle communicatie tussen clients en extern bureaublad-sessiehostservers tijdens externe verbindingen de versleutelingsmethode worden gebruikt die is opgegeven in deze instelling. Het versleutelingsniveau is standaard ingesteld op Hoog. De volgende versleutelingsmethoden zijn beschikbaar:  
  - *Hoog*: met de instelling Hoog worden gegevens die van de client naar de server en de server naar de client worden verzonden met behulp van 128-bits versleuteling versleuteld. Gebruik dit versleutelingsniveau in omgevingen die enkel 128-bits clients bevatten (bijvoorbeeld: clients met Verbinding met extern bureaublad). Clients die geen ondersteuning bieden voor dit versleutelingsniveau kunnen geen verbinding maken met Extern bureaublad-sessiehostservers.  
  - *Compatibel met client*: met de instelling Compatibel met client worden gegevens die worden verzonden tussen de client en de server op de maximaal door de client ondersteunde sleutelsterkte versleuteld. Gebruik dit versleutelingsniveau in omgevingen met clients die geen ondersteuning bieden voor 128-bits versleuteling.  
  - *Laag*: met de instelling Laag worden alleen gegevens die van de client naar de server worden verzonden met behulp van 56-bits versleuteling versleuteld.  
  
  Als u deze instelling uitschakelt of niet configureert, wordt het versleutelingsniveau dat moet worden gebruikt voor externe verbindingen met Extern bureaublad-sessiehostservers niet afgedwongen via groepsbeleid. Belangrijke FIPS-compatibiliteit kan worden geconfigureerd via de systeemcryptografie. FIPS-compatibele algoritmes gebruiken voor versleuteling, hashing en ondertekening van de instellingen in groepsbeleid (onder Computerconfiguratie\Windows-instellingen\Beveiligingsinstellingen\Lokaal Beleid\Beveiligingsopties.) Met de instelling FIPS-compatibiliteit worden gegevens die van de client naar de server en de server aan de client worden verzonden, versleuteld met de FIPS 140-versleutelingsalgoritmen (FIPS: Federal Information Processing Standard) met behulp van cryptografische modules van Microsoft. Gebruik dit versleutelingsniveau wanneer voor de communicatie tussen clients en de Extern bureaublad-sessiehostservers de hoogste mate van versleuteling is vereist.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067222)  
  
  **Standaardinstelling**: Hoog
  
## <a name="remote-management"></a>Extern beheer  
Zie [Beleids-CSP - RemoteManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotemanagement) in de Windows-documentatie voor meer informatie.  

- **Referenties opslaan voor Uitvoeren als blokkeren**  
  Basisverificatie voor clients.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067300)  
  
  **Standaardinstelling**: ingeschakeld
  
- **Basisverificatie**  
  Met deze beleidsinstelling kunt u bepalen of de WinRM-service (WinRM: Windows Remote Management) basisverificatie accepteert van een externe client. Als u deze beleidsinstelling inschakelt, accepteert de WinRM-service basisverificatie van een externe client. Als u deze beleidsinstelling uitschakelt of niet configureert, accepteert de WinRM-service geen basisverificatie van een externe client.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067223)  
  
  **Standaardinstelling**: uitgeschakeld
  
- **Digest-verificatie van clients blokkeren**  
  Met deze beleidsinstelling kunt u bepalen of de WinRM-client gebruikmaakt van Digest-verificatie. Als u deze beleidsinstelling inschakelt, gebruikt de WinRM-client geen Digest-verificatie. Als u deze beleidsinstelling uitschakelt of niet configureert, gebruikt de WinRM-client Digest-verificatie.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067302)  
  
  **Standaardinstelling**: ingeschakeld
  
- **Niet-versleuteld verkeer**  
  Met deze beleidsinstelling kunt u bepalen of de WinRM-service (WinRM: Windows Remote Management) niet-versleutelde berichten verzendt en ontvangt via het netwerk. Als u deze beleidsinstelling inschakelt, verzendt en ontvangt de WinRM-client niet-versleutelde berichten via het netwerk. Als u deze beleidsinstelling inschakelt, verzendt en ontvangt de WinRM-client alleen versleutelde berichten via het netwerk.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067226)  
  
  **Standaardinstelling**: uitgeschakeld
  
- **Niet-versleuteld clientverkeer**  
  Met deze beleidsinstelling kunt u bepalen of de WinRM-client (Windows Remote Management-client) via het netwerk niet-versleutelde berichten verzendt en ontvangt. Als u deze beleidsinstelling inschakelt, verzendt en ontvangt de WinRM-client niet-versleutelde berichten via het netwerk. Als u deze beleidsinstelling inschakelt, verzendt en ontvangt de WinRM-client alleen versleutelde berichten via het netwerk.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067304)  
  
  **Standaardinstelling**: uitgeschakeld
  
- **Basisverificatie voor clients**  
  Met deze beleidsinstelling kunt u bepalen of de WinRM-client gebruikmaakt van basisverificatie. Als u deze beleidsinstelling inschakelt, gebruikt de WinRM-client basisverificatie. Als WinRM is geconfigureerd voor het gebruik van HTTP-transport, worden de gebruikersnaam en het wachtwoord via het netwerk als niet-versleutelde tekst verzonden. Als u deze beleidsinstelling uitschakelt of niet configureert, gebruikt de WinRM-client geen basisverificatie.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067252)  
  
  **Standaardinstelling**: uitgeschakeld
  
## <a name="remote-procedure-call"></a>Externe procedureaanroep  
Zie [Beleids-CSP - RemoteProcedureCall](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remoteprocedurecall) in de Windows-documentatie voor meer informatie.  

- **Opties voor RPC niet-geverifieerde clients**  
  Met deze beleidsinstelling bepaalt u hoe de RPC-serverruntime omgaat met niet-geverifieerde RPC-clients die verbinding maken met RPC-servers. Deze beleidsinstelling heeft gevolgen voor alle RPC-toepassingen. In een domeinomgeving dient u voorzichtig te zijn met het gebruik van deze beleidsinstelling, aangezien het gevolgen kan hebben voor een breed scala aan functies, waaronder de verwerking van het groepsbeleid zelf. Het kan zijn dat het herstellen van een wijziging in deze beleidsinstelling handmatig op elke betreffende machine moet worden uitgevoerd. Deze beleidsinstelling moet nooit worden toegepast op een domeincontroller. Als u deze beleidsinstelling uitschakelt, maakt de RPC-serverruntime gebruik van de waarde 'Geverifieerd' op Windows Client en van de waarde 'Geen' op Windows Server-versies die ondersteuning bieden voor deze instelling. Als u deze beleidsinstelling niet configureert, blijft deze uitgeschakeld. De RPC-serverruntime gedraagt zich alsof deze is ingeschakeld met de waarde 'Geverifieerd' die wordt gebruikt voor Windows Client en de waarde 'Geen' die wordt gebruikt voor Server SKU's die ondersteuning bieden voor deze beleidsinstelling. Als u deze beleidsinstelling inschakelt, zorgt deze ervoor dat de RPC-serverruntime beperkingen oplegt aan niet-geverifieerde RPC-clients die verbinding maken met RPC-servers die op een computer worden uitgevoerd. Een client zal worden beschouwd als een geverifieerde client als deze een named pipe gebruikt om te communiceren met de server of als deze RPC-beveiliging gebruikt. RPC-interfaces die specifiek hebben verzocht om toegankelijk te zijn voor niet-geverifieerde clients kunnen worden uitgezonderd van deze beperking, afhankelijk van de geselecteerde waarde voor deze instelling.  
  - Via *Geen* kunnen alle RPC-clients verbinding maken met de RPC-Servers die worden uitgevoerd op de computer waarop de beleidsinstelling wordt toegepast. 
  - Via *Geverifieerd* kunnen alleen geverifieerde RPC-clients (volgens bovenstaande definitie) verbinding maken met RPC-servers die worden uitgevoerd op de computer waarop de beleidsinstelling wordt toegepast. Er kan een uitzondering worden gemaakt op interfaces wanneer daarvoor een aanvraag is gedaan. 
  - Via *Geverifieerd zonder uitzonderingen* kunnen alleen geverifieerde RPC-clients (volgens bovenstaande definitie) verbinding maken met RPC-servers die worden uitgevoerd op de computer waarop de beleidsinstelling wordt toegepast. Er zijn geen uitzonderingen toegestaan. Opmerking: deze beleidsinstelling wordt pas toegepast wanneer het systeem opnieuw wordt opgestart.  

  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067225)  

  **Standaardinstelling**: Geverifieerd

## <a name="search"></a>Zoeken 
Zie [Beleids-CSP - Search](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-search) in de Windows-documentatie voor meer informatie.  

- **Indexeren van versleutelde items uitschakelen**  
  Hiermee kunt u het indexeren van items toestaan of verbieden. Deze schakeloptie dient voor de Windows Search-indexeerfunctie. Hiermee bepaalt u of items die zijn versleuteld, worden geïndexeerd, zoals de bestanden met Windows Information Protection (WIP). Wanneer het beleid wordt ingeschakeld, worden de items met WIP-beveiliging geïndexeerd en worden de metagegevens opgeslagen op een niet-versleutelde locatie. De metagegevens bevatten gegevens zoals het bestandspad en de wijzigingsdatum. Als het beleid is uitgeschakeld, worden de items met WIP-beveiliging niet geïndexeerd en worden ze niet weergegeven in de resultaten in Cortana of Verkenner. Als er te veel mediabestanden met WIP-beveiliging op het apparaat staan, kunnen de prestaties bij gebruik van foto's en Groove-apps ook worden beïnvloed.  
  [Meer informatie]( https://go.microsoft.com/fwlink/?linkid=2067303)  
  
  **Standaardinstelling**: Ja
  
## <a name="smart-screen"></a>SmartScreen  
Zie [Beleids-CSP - SmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-smartscreen) in de Windows-documentatie voor meer informatie.  

- **Uitvoering van niet-geverifieerde bestanden blokkeren**  
  Verhinderen dat een gebruiker niet-geverifieerde bestanden uitvoert. 
  - *Niet geconfigureerd*: werknemers kunnen SmartScreen-waarschuwingen negeren en schadelijke bestanden uitvoeren. 
  - *Ja*: werknemers kunnen SmartScreen-waarschuwingen negeren en schadelijke bestanden uitvoeren.

  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067228)  
  
  **Standaardinstelling**: Ja

- **SmartScreen vereisen voor apps en bestanden**  
  Hiermee kunnen IT-beheerders SmartScreen voor Windows configureren.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067168)  

  **Standaardinstelling**: Ja
  
## <a name="system"></a>Systeem  
Zie [Beleids-CSP - System](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system) in de Windows-documentatie voor meer informatie.  

- **Initialisatie van systeemstartstuurprogramma**  
  Met deze beleidsinstelling kunt u opgeven welke systeemstartstuurprogramma's worden geïnitialiseerd op basis van een classificatie die is bepaald door het systeemstartstuurprogramma Early Launch Antimalware. Het systeemstartstuurprogramma Early Launch Antimalware kan de volgende classificaties retourneren voor elk systeemstartstuurprogramma: 
  - *Goed*: het stuurprogramma is ondertekend en is niet gemanipuleerd.  
  - *Ongeldig*: het stuurprogramma is geïdentificeerd als schadelijke software. Het is raadzaam om niet toe te staan dat bekende ongeldige stuurprogramma's worden geïnitialiseerd. 
  - *Ongeldig, maar vereist voor opstarten*: het stuurprogramma is geïdentificeerd als schadelijke software, maar de computer kan niet worden opgestart zonder dat dit stuurprogramma wordt geladen. 
  - *Onbekend*: dit stuurprogramma is niet beoordeeld door de toepassing voor de detectie van schadelijke software, en is niet geclassificeerd door het systeemstartstuurprogramma Early Launch Antimalware.  

  Als u deze beleidsinstelling inschakelt, kunt u kiezen welke systeemstartstuurprogramma's moeten worden geïnitialiseerd als de computer de volgende keer wordt gestart. Als u dit beleid uitschakelt of niet configureert, worden de systeemstartstuurprogramma's geïnitialiseerd die zijn aangemerkt als Goed, Onbekend of Ongeldig maar essentieel voor opstarten, en wordt de initialisatie van stuurprogramma's die zijn aangemerkt als Ongeldig overgeslagen. Als uw toepassing voor de detectie van schadelijke software niet het systeemstartstuurprogramma Early Launch Antimalware bevat of als dit programma is uitgeschakeld, is deze instelling niet van invloed en worden alle systeemstartstuurprogramma's geïnitialiseerd.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067307)   
  
  **Standaardinstelling**: Goed, Onbekend en Ongeldig maar essentieel


## <a name="wi-fi"></a>Wi-Fi  
Zie [Beleids-CSP - Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi) in de Windows-documentatie voor meer informatie.  

- **Internetverbinding delen blokkeren**  
  Hiermee geeft u op of het delen van internet op het apparaat mogelijk is.   
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067327)   

  **Standaardinstelling**: Ja  

- **Automatisch verbinding maken met Wi-Fi-hotspots blokkeren**  
  Toestaan of weigeren dat het apparaat automatisch verbinding maakt met Wi-Fi-hotspots.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067320)   

  **Standaardinstelling**: Ja  
  
## <a name="windows-connection-manager"></a>Windows-verbindingsbeheer  
Zie [Beleids-CSP - WindowsConnectionManager](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsconnectionmanager) in de Windows-documentatie voor meer informatie.  

- **Verbinding met niet-domeinnetwerken blokkeren**  
  Met deze beleidsinstelling wordt voorkomen dat computers tegelijk verbinding maken met zowel een domein- als niet-domeinnetwerk. Als deze instelling is ingeschakeld, reageert de computer op automatische en handmatige pogingen om verbinding te maken met een netwerk op basis van de volgende omstandigheden: 
  - Automatische pogingen om verbinding te maken Wanneer de computer al met een domeinnetwerk is verbonden, worden alle automatische pogingen om verbinding te maken met niet-domeinnetwerken geblokkeerd. Wanneer de computer al met een niet-domeinnetwerk is verbonden, worden alle automatische pogingen om verbinding te maken met domeinnetwerken geblokkeerd. 
  - Handmatige pogingen om verbinding te maken Wanneer de computer al met een niet-domein- of domeinnetwerk verbonden is via andere media dan Ethernet, en een gebruiker probeert in strijd met deze beleidsinstelling een handmatige verbinding in te stellen met een extra netwerk, wordt de bestaande netwerkverbinding verbroken en de handmatige verbinding toegestaan. Wanneer de computer al met een niet-domein- of domeinnetwerk verbonden is via Ethernet, en een gebruiker probeert in strijd met deze beleidsinstelling een handmatige verbinding in te stellen met een extra netwerk, wordt de bestaande Ethernetverbinding gehandhaafd en de handmatige verbinding geblokkeerd.  

  Als deze beleidsinstelling niet is geconfigureerd of is uitgeschakeld, mogen computers tegelijk met zowel domein- als niet-domeinnetwerken verbinding maken.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067323)  

  **Standaardinstelling**: ingeschakeld
  
## <a name="windows-defender"></a>Windows Defender  
Zie [Beleids-CSP - Defender](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender) in de Windows-documentatie voor meer informatie.  

- **Inkomende e-mailberichten scannen**  
  Hiermee kunt u het scannen van e-mail toestaan of niet toestaan.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067116)  
  
  **Standaardinstelling**: Ja  

- **Onderliggend procestype voor starten van Office-apps**  
  Office-apps mogen geen onderliggende processen maken. Dit is inclusief Word, Excel, PowerPoint, OneNote en Access. Dit is typisch malwaregedrag, met name voor op macro's gebaseerde aanvallen die Office-apps proberen te gebruiken om schadelijke uitvoerbare bestanden te starten of te downloaden.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067121)  
  
  **Standaardinstelling**: Blokkeren
  
- **Voorbeeld van een Defender-toestemmingstype voor indiening**  
  Hiermee wordt het gebruikerstoestemmingsniveau in Windows Defender gecontroleerd om gegevens te verzenden. Als de vereiste toestemming al is verleend, worden de gegevens door Windows Defender ingediend. Als dit niet het geval is (en als de gebruiker heeft opgegeven dat deze vraag nooit mag worden gesteld), wordt de gebruikersinterface geopend om de gebruiker om toestemming te vragen (wanneer Defender/AllowCloudProtection is toegestaan) voordat gegevens worden verzonden.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067131)  
  
  **Standaardinstelling**: veilige voorbeelden automatisch verzenden 
  
- **Interval voor handtekeningupdates (in uren)**  
  Interval voor Defender-handtekeningupdates (in uren)
  
  **Standaardinstelling**: 4
  
- **Uitvoeringstype van de payload die is gedownload met een script**  
  Uitvoeringstype van de payload die is gedownload met een Defender-script
  
  **Standaardinstelling**: Blokkeren
  
- **Type referentiediefstal voorkomen**  
  Windows Defender Credential Guard maakt gebruik van op virtualisatie gebaseerde beveiliging om geheime gegevens te isoleren. Zo hebt u er alleen met bevoegde systeemsoftware toegang toe. Niet-geautoriseerde toegang tot deze geheime gegevens kan leiden tot pogingen tot diefstal, zoals een Pass-the-Hash- of Pass-the-Ticket-aanval. Met Windows Defender Credential Guard worden deze aanvallen voorkomen, doordat NTLM-wachtwoord-hashes, Kerberos Ticket Granting Tickets en referenties die door toepassingen zijn opgeslagen als domeinreferenties worden beschermd.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067065)  
  
  **Standaardinstelling**: Inschakelen

- **Uitvoertype vanuit e-mailinhoud**  
  Deze regel voorkomt dat de volgende bestandstypen worden uitgevoerd of gestart vanuit een e-mailbericht dat wordt weergegeven in Microsoft Outlook of webmail (zoals Gmail.com of Outlook.com): uitvoerbare bestanden (zoals .exe, .dll of .scr) Script-bestanden (zoals de volgende: PowerShell .ps, VisualBasic .vbs of JavaScript .js) Script-archiefbestanden.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067063)  
  
  **Standaardinstelling**: Blokkeren

- **Adobe Reader starten in een onderliggend proces**  

  **Standaardinstelling**: Inschakelen

- **Netwerkbeveiligingstype**  
  Met dit beleid kunt u netwerkbeveiliging inschakelen (blokkeren/controleren) of uitschakelen in Windows Defender Exploit Guard. Netwerkbeveiliging is een functie van Windows Defender Exploit Guard die voorkomt dat werknemers die apps gebruiken in contact komen met phishing-praktijken, sites die misbruik maken en schadelijke inhoud op internet. Dit omvat het voorkomen dat browsers van derden verbinding maken met gevaarlijke websites. Waardetype is geheel getal. Als u deze instelling inschakelt, wordt netwerkbeveiliging ingeschakeld en kunnen werknemers dit niet uitschakelen. Het gedrag kan worden beheerd met de volgende opties: Blokkeren en Controleren. Als u dit beleid inschakelt met de optie Blokkeren, kunnen gebruikers en apps geen verbinding maken met gevaarlijke domeinen. U kunt deze activiteit bekijken in Windows Defender Security Center. Als u dit beleid inschakelt met de optie Controleren, kunnen gebruikers en apps verbinding maken met gevaarlijke domeinen. Maar deze activiteit wordt nog steeds weergegeven in Windows Defender Security Center. Als u dit beleid uitschakelt, kunnen gebruikers/apps verbinding maken met gevaarlijke domeinen. U ziet geen netwerkactiviteit in Windows Defender Security Center. Als u dit beleid niet configureert, wordt netwerkblokkering standaard uitgeschakeld.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067102)  
  
  **Standaardinstelling**: Inschakelen
  
- **Defender: scandag plannen**  
  Scandag voor Defender plannen.
  
  **Standaardinstelling**: Elke dag
  
- **Cloudbeveiliging**  
  Om uw pc zo goed mogelijk te beveiligen, verzendt Windows Defender gegevens naar Microsoft over problemen die worden gevonden. Microsoft analyseert die gegevens, verzamelt meer gegevens over problemen die u en andere klanten ondervinden en biedt verbeterde oplossingen.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067039)
  
  **Standaardinstelling**: Ja  

- **Defender: mogelijk ongewenste app-actie**  
  De beveiligingsfunctie tegen mogelijk ongewenste toepassingen (PUA; potentially unwanted application) in Windows Defender Antivirus kan mogelijk ongewenste toepassingen identificeren en voorkomen dat ze worden gedownload en geïnstalleerd op eindpunten in uw netwerk. Deze toepassingen worden niet beschouwd als virussen, malware of andere soorten bedreigingen, maar kunnen mogelijk acties uitvoeren op eindpunten die nadelige invloed hebben op de prestaties of het gebruik. Mogelijk ongewenste toepassingen kan ook verwijzen naar toepassingen die een slechte reputatie hebben. Standaardgedrag van mogelijk ongewenste toepassingen is: Verschillende typen softwarebundeling Advertentietoevoeging in webbrowsers Optimalisatieprogramma's voor stuurprogramma's en registers die problemen detecteren en vragen om betaling om problemen op te lossen. Ze blijven op het eindpunt en er worden geen wijzigen of optimalisaties aangebracht (ook wel bekend als 'rogue antivirus'-programma's). Deze toepassingen kunnen het risico op infectie van uw netwerk met malware verhogen, ervoor zorgen dat malware-infecties moeilijker kunnen worden geïdentificeerd en kunnen IT-resources verspillen omdat deze de toepassingen moeten opschonen.  
  [Meer informatie](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-puaprotection)    
  
  **Standaardinstelling**: Blokkeren  

- **Macrocode verborgen in scripts**  
  Malware en andere bedreigingen kunnen proberen hun schadelijke code te verbergen in sommige scriptbestanden. Met deze regel wordt voorkomen dat scripts die verborgen lijken te zijn, worden uitgevoerd.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067026)  
  
  **Standaardinstelling**: Blokkeren
  
- **Verwisselbare stations scannen tijdens een volledige scan**  
  Hiermee kan Windows Defender scannen op schadelijke en ongewenste software op verwisselbare stations (bijvoorbeeld flashstations) tijdens een volledige scan. Windows Defender Antivirus scant alle bestanden op USB-apparaten voordat ze worden uitgevoerd.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067036)  
  
  **Standaardinstelling**: Ja  
  
- **Archiefbestanden scannen**  
  Archiefbestanden scannen met Defender.
  
  **Standaardinstelling**: Ja
  
- **Gedragscontrole**  
  Toegestaan of geweigerd Gedragscontrole van Windows Defender-functionaliteit. Deze sensoren, ingesloten in Windows 10, verzamelen en verwerken gedragssignalen van het besturingssysteem en verzenden deze sensorgegevens naar uw persoonlijke, geïsoleerde cloudinstantie van Microsoft Defender ATP.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067111)  
  
  **Standaardinstelling**: Ja

- **Bestanden scannen die zijn geopend vanuit mappen op het netwerk**  
  Als bestanden alleen-lezen zijn, kunnen gebruikers geen gedetecteerde malware verwijderen.
  
  **Standaardinstelling**: Ja

- **Niet-vertrouwd USB-procestype**  
  Met deze regel kunnen beheerders voorkomen dat niet-ondertekende of niet-vertrouwde uitvoerbare bestanden worden uitgevoerd vanaf verwisselbare USB-stations, zoals SD-kaarten.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067100)  
  
  **Standaardinstelling**: Blokkeren
  
- **Office-apps: invoeringstype voor andere processen**  
  Office-apps, inclusief Word, Excel, PowerPoint en OneNote, kunnen geen code invoeren in andere processen. Dit wordt doorgaans gebruikt door malware om schadelijke code uit te voeren in een poging om de activiteit te verbergen voor antivirusscanegines.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067019)  
  
  **Standaardinstelling**: Blokkeren
  
- **Office-macrocode staat Win32-importtype toe**  
  Malware kan macrocode in Office-bestanden gebruiken om Win32-DLL's te importeren en laden, die vervolgens kunnen worden gebruikt om API-aanroepen uit te voeren voor verdere infectie in het hele systeem. Met deze regel wordt geprobeerd Office-bestanden te blokkeren die macrocode bevatten waarmee Win32-DLL's kunnen worden geïmporteerd. Dit is inclusief Word, Excel, PowerPoint en OneNote.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067130)  
  
  **Standaardinstelling**: Blokkeren  
  
- **Defender op cloudblokniveau**  
  Defender op cloudblokniveau.
  
  **Standaardinstelling**: niet geconfigureerd

- **Realtimecontrole**  
  Voor Defender is realtimecontrole vereist.
  
  **Standaardinstelling**: Ja
 
- **Office-communicatieapps worden gestart in een onderliggend proces**  

  **Standaardinstelling**: Inschakelen

- **Office-apps: uitvoerbare inhoud maken of lanceren**  
  Deze regel is gericht op typisch gedrag van verdachte en schadelijke invoegtoepassingen en scripts (extensies) die uitvoerbare bestanden maken of openen. Dit is een typische malwaretechniek. Extensies kunnen niet worden gebruikt door Office-apps. Doorgaans gebruiken deze extensies Windows Scripting Host (WSH-bestanden) om scripts uit te voeren die bepaalde taken automatiseren of door gebruikers gemaakte extra functies leveren.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067108)  
  
  **Standaardinstelling**: Blokkeren

## <a name="windows-defender-firewall"></a>Windows Defender Firewall  
Zie voor meer informatie, [2.2.2 FW_PROFILE_TYPOE]( https://docs.microsoft.com/openspecs/windows_protocols/ms-fasp/7704e238-174d-4a5e-b809-5f3787dd8acc) in de documentatie van Windows-protocollen.  

- **Firewall-profiel domein**  
  Hiermee geeft u de profielen op waartoe de regel behoort: Domein, Privé of Openbaar. Deze waarde vertegenwoordigt het profiel voor netwerken die zijn verbonden met domeinen.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2066796)  

  - **Geblokkeerde binnenkomende verbindingen**  
    **Standaardinstelling**: Ja

  - **Uitgaande verbindingen vereist**  
    **Standaardinstelling**: Ja 

  - **Binnenkomende meldingen geblokkeerd**  
    **Standaardinstelling**: Ja

  - **Firewall ingeschakeld**  
    **Standaardinstelling**: Toegestaan

- **Openbare Firewall-profiel**  
  Hiermee geeft u de profielen op waartoe de regel behoort: Domein, Privé of Openbaar. Deze waarde vertegenwoordigt het profiel voor openbare netwerken. Deze netwerken wordt als openbaar geclassificeerd door de beheerders in de serverhost. De classificatie vindt plaats de eerste keer dat de host verbinding maakt met het netwerk. Deze netwerken bevinden zich meestal op luchthavens, in cafés en in andere openbare ruimten waar de peers in het netwerk of de netwerkbeheerder niet worden vertrouwd.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067143)  

  - **Geblokkeerde binnenkomende verbindingen**  
    **Standaardinstelling**: Ja

  - **Uitgaande verbindingen vereist**  
    **Standaardinstelling**: Ja 

  - **Binnenkomende meldingen geblokkeerd**  
    **Standaardinstelling**: Ja

  - **Firewall ingeschakeld**  
    **Standaardinstelling**: Toegestaan

  - **Beveiligingsregels voor verbindingen van groepsbeleid niet samengevoegd**  
    **Standaardinstelling**: Ja

  - **Beleidsregels van groepsbeleid niet samengevoegd**  
    **Standaardinstelling**: Ja

- **Firewall-profiel privé**  
  Hiermee geeft u de profielen op waartoe de regel behoort: Domein, Privé of Openbaar. Deze waarde vertegenwoordigt het profiel voor privénetwerken.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067041)  

   - **Geblokkeerde binnenkomende verbindingen**  
    **Standaardinstelling**: Ja

  - **Uitgaande verbindingen vereist**  
    **Standaardinstelling**: Ja 

  - **Binnenkomende meldingen geblokkeerd**  
    **Standaardinstelling**: Ja

  - **Firewall ingeschakeld**  
    **Standaardinstelling**: Toegestaan

## <a name="windows-hello-for-business"></a>Windows Hello voor Bedrijven  
- **Verbeterde anti-adresvervalsing vereisen, indien beschikbaar**  
  Zo ja, apparaten wordt verbeterde anti-adresvervalsing gebruiken, indien beschikbaar. Indien Nee, wordt anti-adresvervalsing geblokkeerd. Niet is geconfigureerd, worden configuraties op de client gerespecteerd.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067192)

  **Standaardinstelling**: Ja

- **Windows Hello voor Bedrijven configureren**   
  Windows Hello voor Bedrijven is een alternatieve aanmeldmethode voor Windows die wachtwoorden, smartcards en virtuele smartcards vervangt. Als u deze beleidsinstelling inschakelt of niet configureert, richt het apparaat Windows Hello voor Bedrijven in. Als u deze beleidsinstelling uitschakelt, richt het apparaat voor geen enkele gebruiker Windows Hello voor Bedrijven in.

  **Standaardinstelling**: Ja

- **Kleine letters in pincode vereisen**  
  Indien vereist, moet de PINCODE van de gebruiker ten minste één kleine letter bevatten.

  **Standaardinstelling**: Toegestaan

- **Speciale tekens in pincode vereisen**  
  Indien vereist, moet de PINCODE van de gebruiker ten minste één speciaal teken bevatten.

  **Standaardinstelling**: Toegestaan

- **Minimale lengte pincode**  
  Minimumlengte voor PINCODE moet tussen 4 en 127 tekens.

  **Standaardinstelling**: 6

- **Hoofdletters in pincode vereisen**  
  Indien vereist, moet de PINCODE van de gebruiker ten minste één hoofdletter bevatten.

  **Standaardinstelling**: Toegestaan

## <a name="windows-ink-workspace"></a>Windows Ink-werkruimte  
Raadpleeg [Policy CSP - WindowsInkWorkspace](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsinkworkspace) (Beleids-CSP - WindowsInkWorkspace) in de Windows-documentatie voor meer informatie.  

- **Windows Ink-werkruimte**  
  Hiermee wordt opgegeven of de gebruiker toegang kan krijgen tot de Windows Ink-werkruimte. 
  - *Uitgeschakeld*: toegang tot de Ink-werkruimte is uitgeschakeld. De functie is uitgeschakeld.
  - *Ingeschakeld*: de functie Ink-werkruimte is ingeschakeld, maar de gebruiker kan geen toegang krijgen verder dan het vergrendelingsscherm.
  - *Niet geconfigureerd*: de functie Ink-werkruimte is ingeschakeld en de gebruiker kan toegang krijgen verder dan het vergrendelingsscherm.  

  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067241)  

  **Standaardinstelling**: ingeschakeld
 
## <a name="windows-powershell"></a>Windows PowerShell  
Raadpleeg [Policy CSP - WindowsPowerShell](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowspowershell) (Beleids-CSP - WindowsPowerShell) in de Windows-documentatie voor meer informatie.  

- **PowerShell: logboekregistratie van Shell-script blokkeren**  
  Met deze beleidsinstelling wordt logboekregistratie van alle PowerShell-scriptinvoer naar het gebeurtenislogboek van Microsoft-Windows-PowerShell/Operational ingeschakeld. Als u deze beleidsinstelling inschakelt, wordt met Windows PowerShell de verwerking van opdrachten, scriptblokkeringen, functies en scripts via logboekregistratie bijgehouden, ongeacht of deze interactief worden aangeroepen of via automatisering. Als u deze beleidsinstelling uitschakelt, wordt logboekregistratie van PowerShell-scriptinvoer uitgeschakeld. Als u de logboekregistratie voor het aanroepen van script blokkeren inschakelt, worden gebeurtenissen door PowerShell vastgelegd bij het aanroepen van een opdracht, scriptblokkering, functie of bij het starten of stoppen van een script. Als het aanroeplogbestand wordt ingeschakeld, wordt er een groot aantal gebeurtenislogboeken gegenereerd. Opmerking: deze beleidsinstelling bestaat onder Computerconfiguratie en Gebruikersconfiguratie in de Groepsbeleidseditor. De beleidsinstelling Computerconfiguratie heeft voorrang op de beleidsinstelling Gebruikersconfiguratie.  
  [Meer informatie](https://go.microsoft.com/fwlink/?linkid=2067330)  

  **Standaardinstelling**: ingeschakeld

## <a name="whats-changed-in-the-new-template"></a>Wat er gewijzigd in de nieuwe sjabloon
De *MDM basisbeveiliging voor Spring 2019 Update (19 uur 1)* sjabloon bevat de volgende wijzigingen uit de *preview* sjabloon.

### <a name="changes-to-the-baseline-settings"></a>Wijzigingen in de basislijninstellingen van de
De instellingen kunnen als volgt zijn:
- *Nieuwe* in deze meest recente versie van de basislijn.
- *Verwijderd* uit deze meest recente versie van de basislijn, maar aanwezig waren in de vorige versie.
- *Herziene versie* op een bepaalde manier van hoe de instellingen in de vorige versie werd weergegeven. 

*[Nieuw]*  [ **Vergrendeling**](#above-lock):
-  **Voice-mailapps vergrendeld scherm activeren**    

*[Nieuw]* [**Toepassingsbeheer**](#application-management): 
- **Controle van de gebruiker blokkeren over installaties**  
- **Blok-MSI-app-installaties met verhoogde bevoegdheden**  

*[Verwijderd]* [**Bitlocker**](#bitlocker):  
- Bit van AppLocker verwisselbaar station beleid > **versleutelingsmethode**
- **BitLocker vast station beleid** *(alle instellingen)*
- **Bits BitLocker station systeembeleid** *(alle instellingen)*

*[Nieuw]* [**Connectiviteit**](#connectivity):
- **Beveiligde toegang tot het UNC-paden configureren**

*[Nieuw]* [**Device Guard**](#device-guard):
- **Beveiliging op basis van virtualisatie**


*[Nieuw]*  [ **DMA Guard**](#dma-guard):
- **Opsomming van externe apparaten die niet compatibel zijn met DMA-beveiliging van kernel**  

*[Nieuw]* [**Internet Explorer**](#internet-explorer):
- **Updates van de statusbalk vinden plaats in de Explorer-internetzone via script**
- **Internetzone van Internet Explorer: bestanden slepen en neerzetten of kopiëren en plakken**  
- **Internet Explorer: onderdelen in de beperkte zone die afhankelijk zijn van .NET Framework**  
- **Internet Explorer: er wordt geen antimalware uitgevoerd op ActiveX-besturingselementen in de lokale machinezone**
- **Ondersteuning voor de versleuteling van Internet Explorer**  

*[Aangepast]* [**Internet Explorer**](#internet-explorer):
- **Internet Explorer internet zone automatische prompt voor het downloaden van bestand** > de standaardwaarde is nu **uitgeschakelde**. Preview-versie is deze ingesteld op ingeschakeld.

*[Nieuw]* [**Hulp op afstand**](#remote-assistance):  
- **Hulp op afstand aangevraagde** 
  - **Hulp op afstand aangevraagde machtiging**
  - **Maximale ticket tijd-waarde**  
  - **Maximale ticket periode**  
  - **E-mailuitnodiging methode**


*[Nieuw]* [**Windows Defender**](#windows-defender):
- **Adobe Reader starten in een onderliggend proces**  
- **Office-communicatieapps worden gestart in een onderliggend proces** 

*[Nieuw]* [**Windows Defender Firewall**](#windows-defender-firewall)
- **Firewall-profiel domein**  
  - **Geblokkeerde binnenkomende verbindingen**  
  - **Uitgaande verbindingen vereist**  
  - **Binnenkomende meldingen geblokkeerd**  
  - **Firewall ingeschakeld**  
- **Openbare Firewall-profiel**  
  - **Geblokkeerde binnenkomende verbindingen**  
  - **Uitgaande verbindingen vereist**  
  - **Binnenkomende meldingen geblokkeerd**  
  - **Firewall ingeschakeld** 
  - **Beveiligingsregels voor verbindingen van groepsbeleid niet samengevoegd**   
  - **Beleidsregels van groepsbeleid niet samengevoegd**  
- **Firewall-profiel privé**  
  - **Geblokkeerde binnenkomende verbindingen**  
  - **Uitgaande verbindingen vereist**  
  - **Binnenkomende meldingen geblokkeerd**  
  - **Firewall ingeschakeld**  

*[Nieuw]* [**Windows Hello voor Bedrijven**](#windows-hello-for-business):  
- **Verbeterde anti-adresvervalsing vereisen, indien beschikbaar**  
- **Windows Hello voor Bedrijven configureren**  
- **Kleine letters in pincode vereisen** 
- **Speciale tekens in pincode vereisen** 
- **Minimale lengte pincode**  
- **Hoofdletters in pincode vereisen** 



<!-- The following settings were available in the Preview Baseline.   

   
## Above Lock  
For more information, see [Policy CSP - AboveLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock) in the Windows documentation.  

- **Block display of toast notifications**  
  This policy setting allows you to prevent app notifications from appearing on the lock screen. If you enable this policy setting, no app notifications are displayed on the lock screen. If you disable or don't configure this policy setting, users can choose which apps display notifications on the lock screen.
  
  **Default**: Yes  

## App Runtime    
For more information, see [Policy CSP - AppRuntime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-appruntime
) in the Windows documentation.  

- **Microsoft accounts optional for Windows Store apps**  
  This policy setting lets you control whether Microsoft accounts are optional for Windows Store apps that require an account to sign in. This policy only affects Windows Store apps that support it. If you enable this policy setting, Windows Store apps that typically require a Microsoft account to sign in will allow users to sign in with an enterprise account instead. If you disable or don't configure this policy setting, users must sign in with a Microsoft account.  
  
  **Default**: Enabled  

## Application Management   
For more information, see [Policy CSP - ApplicationManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement) in the Windows documentation.  

- **Block game DVR (desktop only)**  
  Configures whether recording and broadcasting of games is allowed.
  
  **Default**: Yes  

## Auto Play   
For more information, see [Policy CSP - Autoplay](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-autoplay) in the Windows documentation.  

- **Auto play default auto run behavior**  
  This setting affects the default behavior for Autorun commands. Autorun commands are stored in autorun.inf files and can launch installation programs or other routines. When *Enabled*, Administrators can change the default autorun behavior on a device that runs Windows Vista or later. Behavior can be set to: a) completely disable autorun commands, or b) revert back to pre-Windows Vista behavior of automatically executing the autorun command. When set to *Disabled* or *Not Configured*, devices that run Windows Vista or later prompt the user as to whether an autorun command should run.
  
  **Default**: Do not execute  
  
- **Auto play mode**  
  This policy setting allows you to turn off the Autoplay feature. Autoplay begins reading from a drive as soon as you insert media in the drive. As a result, the setup file of programs and the music on audio media start immediately. Prior to Windows XP SP2, Autoplay is disabled by default on removable drives, such as the floppy disk drive (but not the CD-ROM drive), and on network drives. Starting with Windows XP SP2, Autoplay is enabled for removable drives as well, including Zip drives and some USB mass storage devices. If you enable this policy setting, Autoplay is disabled on CD-ROM and removable media drives, or disabled on all drives. This policy setting disables Autoplay on additional types of drives. You can't use this setting to enable Autoplay on drives on which it's disabled by default. If you disable or don't configure this policy setting, AutoPlay is enabled. Note: This policy setting appears in both the Computer Configuration and User Configuration folders. If the policy settings conflict, the policy setting in Computer Configuration takes precedence over the policy setting in User Configuration.
  
  **Default**: Disabled

- **Block auto play for non-volume devices**  
  This policy setting disallows AutoPlay for MTP devices like cameras or phones. If you enable this policy setting, AutoPlay isn't allowed for MTP devices like cameras or phones. If you disable or don't configure this policy setting, AutoPlay is enabled for non-volume devices.
  
  **Default**: Enabled  

## Bitlocker    
For more information, see [Policy CSP - Bitlocker](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bitlocker
) in the Windows documentation.  

- **Bit locker removable drive policy**  
  This policy setting is used to control the encryption method and cipher strength. The values of this policy determine the strength of the cipher that BitLocker uses for encryption. Enterprises may want to control the encryption level for increased security (AES-256 is stronger than AES-128). If you enable this setting, you'll be able to configure an encryption algorithm and key cipher strength for fixed data drives, operating system drives, and removable data drives individually. For fixed and operating system drives, we recommend that you use the XTS-AES algorithm. For removable drives, you should use AES-CBC 128-bit or AES-CBC 256-bit if the drive is used in other devices that aren't running Windows 10, version 1511 or later. Changing the encryption method has no effect if the drive is already encrypted or if encryption is in progress. In these cases, this policy setting is ignored.

  For Bit locker removable drive policy, configure the following settings:

    - **Require encryption for write access**  
      **Default**: Yes  
  
    - **Encryption method**  
      **Default**: AES 256bit CBC  

- **Bit locker fixed drive policy**  
  This policy setting is used to control the encryption method and cipher strength. The values of this policy determine the strength of the cipher that BitLocker uses for encryption. Enterprises may want to control the encryption level for increased security (AES-256 is stronger than AES-128). If you enable this setting, you can configure an encryption algorithm and key cipher strength for fixed data drives, operating system drives, and removable data drives individually. For fixed and operating system drives, we recommend that you use the XTS-AES algorithm. For removable drives, you should use AES-CBC 128-bit or AES-CBC 256-bit if the drive is used in other devices that aren't running Windows 10, version 1511 or later. Changing the encryption method has no effect if the drive is already encrypted or if encryption is in progress. In these cases, this policy setting is ignored.  
 
   For Bit locker fixed drive policy, configure the following settings: 
   - **Encryption method**
     **Default**: AES 256bit XTS  

- **Bit locker system drive policy**  
  This policy setting is used to control the encryption method and cipher strength. The values of this policy determine the strength of the cipher that BitLocker uses for encryption. Enterprises may want to control the encryption level for increased security (AES-256 is stronger than AES-128). If you enable this setting, you can configure an encryption algorithm and key cipher strength for fixed data drives, operating system drives, and removable data drives individually. For fixed and operating system drives, we recommend that you use the XTS-AES algorithm. For removable drives, you should use AES-CBC 128-bit or AES-CBC 256-bit if the drive is used in other devices that aren't running Windows 10, version 1511 or later. Changing the encryption method has no effect if the drive is already encrypted or if encryption is in progress. In these cases, this policy setting is ignored.  

   For Bit locker system drive policy, configure the following settings:
  - **Encryption method**  
    **Default**: AES 256bit XTS  

## Browser  
For more information, see [Policy CSP - Browser](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser) in the Windows documentation.  

- **Require SmartScreen for Microsoft Edge**  
  Microsoft Edge uses Windows Defender SmartScreen (turned on) to protect users from potential phishing scams and malicious software by default. Also, by default, users can't disable (turn off) Windows Defender SmartScreen. Enabling this policy turns off Windows Defender SmartScreen and prevent users from turning it on. Don’t configure this policy to let users choose to turn Windows defender SmartScreen on or off.  
  
  **Default**: Yes  
  
- **Block malicious site access**  
  By default, Microsoft Edge allows users to bypass (ignore) the Windows Defender SmartScreen warnings about potentially malicious sites, allowing them to continue to the site. With this policy though, you can configure Microsoft Edge to prevent users from bypassing the warnings, blocking them from continuing to the site.
  
  **Default**: Yes  
  
- **Block unverified file download**
  By default, Microsoft Edge allows users to bypass (ignore) the Windows Defender SmartScreen warnings about potentially malicious files, allowing them to continue downloading the unverified file(s). Enabling this policy prevents users from bypassing the warnings, blocking them from downloading of the unverified file(s).
  
  **Default**: Yes  
  
- **Block Password Manager**  
  By default, Microsoft Edge uses Password Manager automatically, allowing users to manager passwords locally. Disabling this policy restricts Microsoft Edge from using Password Manager. Don’t configure this policy if you want to let users choose to save and manage passwords locally using Password Manager.
  
  **Default**: Yes  
  
- **Prevent certificate error overrides**  
  This policy setting prevents the user from ignoring Secure Sockets Layer/Transport Layer Security (SSL/TLS) certificate errors that interrupt browsing (such as "expired", "revoked", or "name mismatch" errors) in Internet Explorer. If you enable this policy setting, the user can't continue browsing. If you disable or don't configure this policy setting, the user can choose to ignore certificate errors and continue browsing.
  
  **Default**: Yes  

## Connectivity  
For more information, see [Policy CSP - Connectivity](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity) in the Windows documentation.  

- **Block Internet download for web publishing and online ordering wizards**  
  This policy setting specifies whether Windows should download a list of providers for the web publishing and online ordering wizards. These wizards allow users to select from a list of companies that provide services such as online storage and photographic printing. By default, Windows displays providers downloaded from a Windows website in addition to providers specified in the registry. If you enable this policy setting, Windows doesn't download providers, and only the service providers that are cached in the local registry display. If you disable or don't configure this policy setting, a list of providers downloads when the user uses the web publishing or online ordering wizards. For more information that includes details on specifying service providers in the registry, see the documentation for the web publishing and online ordering wizards.  
  
  **Default**: Enabled  

- **Block downloading of print drivers over HTTP**  
  This policy setting specifies whether to allow this client to download print driver packages over HTTP. To set up HTTP printing, non-inbox drivers need to be downloaded over HTTP. Note: This policy setting doesn't prevent the client from printing to printers on the Intranet or the Internet over HTTP. It only prohibits downloading drivers that aren't already installed locally. If you enable this policy setting, print drivers can't be downloaded over HTTP. If you disable or don't configure this policy setting, users can download print drivers over HTTP.
  
  **Default**: Enabled  

## Credentials Delegation  
For more information, see [Policy CSP - CredentialsDelegation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsdelegation
) in the Windows documentation.  

- **Remote host delegation of non-exportable credentials**  
  Remote host allows delegation of non-exportable credentials. When using credential delegation, devices provide an exportable version of credentials to the remote host, which exposes users to the risk of credential theft from attackers on the remote host. If you enable this policy setting, the host supports Restricted Admin or Remote Credential Guard mode. If you disable or don't configure this policy setting, Restricted Administration and Remote Credential Guard mode aren't supported. User will always need to pass their credentials to the host.  

  
  **Default**: Enabled  

## Credentials UI  
For more information, see [Policy CSP - CredentialsUI](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsui) in the Windows documentation.  

- **Enumerate administrators** 
  This policy setting controls whether administrator accounts display when a user attempts to elevate a running application. By default, administrator accounts aren't displayed when the user attempts to elevate a running application. If you enable this policy setting, all local administrator accounts on the PC display so the user can choose one and enter the correct password. If you disable this policy setting, users will always be required to type a user name and password to elevate.  

  
  **Default**: Disabled  

## Data Protection  
For more information, see [Policy CSP - DataProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection
) in the Windows documentation.  

- **Block direct memory access**  
  This policy setting allows you to block direct memory access (DMA) for all hot pluggable PCI downstream ports until a user logs into Windows. Once a user logs in, Windows will enumerate the PCI devices connected to the host plug PCI ports. Every time the user locks the machine, DMA is blocked on hot plug PCI ports with no children devices until the user logs in again. Devices that were already enumerated when the machine was unlocked will continue to function until unplugged. This policy setting is only enforced when BitLocker or device encryption is enabled.
  
  
  **Default**: Yes  

## Device Guard  
For more information, see [Policy CSP - DeviceGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceguard
) in the Windows documentation.  

- **Credential Guard**  
  This setting lets users turn on Credential Guard with virtualization-based security to help protect credentials at next reboot.
   
  **Default**: Enable with UEFI lock 

- **Enable virtualization based security**   
  Turns on virtualization-based security (VBS) at the next reboot. Virtualization-based security uses the Windows Hypervisor to provide support for security services.
  
  **Default**: Yes  


- **Launch system guard**    
  **Default**: Enabled  

## Device Installation  
For more information, see [Policy CSP - DeviceInstallation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation) in the Windows documentation.  

- **Hardware device installation by device identifiers**  
  This policy setting allows you to specify a list of Plug and Play hardware IDs and compatible IDs for devices that Windows is prevented from installing. This policy setting takes precedence over any other policy setting that allows Windows to install a device. If you enable this policy setting, Windows is prevented from installing a device whose hardware ID or compatible ID appears in the list you create. If you enable this policy setting on a remote desktop server, the policy setting affects redirection of the specified devices from a remote desktop client to the remote desktop server. If you disable or don't configure this policy setting, devices can install and update as allowed or prevented by other policy settings.
  
  **Default**: Block hardware device installation  

    When *Block hardware device installation* is selected, the following settings are available.
  
    - **Remove matching hardware devices**   
    This setting is available only when *Hardware device installation by device identifiers* is set to *Block hardware device installation*.
      
      **Default**: Yes
  
    - **Hardware device identifiers that are blocked**  
       This setting is available only when *Hardware device installation by device identifiers* is set to *Block hardware device installation*.
      
      **Default**: Yes  
  
- **Hardware device installation by setup classes**  
  This policy setting allows you to specify a list of device setup class globally unique identifiers (GUIDs) for device drivers that Windows is prevented from installing. This policy setting takes precedence over any other policy setting that allows Windows to install a device. If you enable this policy setting, Windows is prevented from installing or updating device drivers whose device setup class GUIDs appear in the list you create. If you enable this policy setting on a remote desktop server, the policy setting affects redirection of the specified devices from a remote desktop client to the remote desktop server. If you disable or don't configure this policy setting, Windows can install and update devices as allowed or prevented by other policy settings.
  
  **Default**: Block hardware device installation  

    When *Block hardware device installation* is selected, the following settings are available.
    - **Remove matching hardware devices**    
    This setting is available only when *Hardware device installation by setup classes* is set to *Block hardware device installation*.  

      **Default**: *No default configuration*  
  
    - **Hardware device identifiers that are blocked**  
      This setting is available only when *Hardware device installation by setup classes* is set to *Block hardware device installation*.
      
      **Default**: *No default configuration*  

## Device Lock  
For more information, see [Policy CSP - DeviceLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock) in the Windows documentation.  

- **Prevent use of camera**  
  Disables the lock screen camera toggle switch in PC Settings and prevents a camera from being invoked on the lock screen. By default, users can enable invocation of an available camera on the lock screen. If you enable this setting, users will no longer be able to enable or disable lock screen camera access in PC Settings, and the camera can't be invoked on the lock screen. 
  
  **Default**: Enabled  

- **Require password**  
  Specifies whether device lock is enabled.
  
  **Default**: Yes  
  
    When *Require password* is set to *Yes*, the following settings are available.

    - **Password minimum character set count**  
      The number of complex element types (uppercase and lowercase letters, numbers, and punctuation) required for a strong PIN or password. PIN enforces the following behavior for desktop and mobile devices: 1 - Digits only 2 - Digits and lowercase letters are required 3 - Digits, lowercase letters, and uppercase letters are required. Not supported in desktop Microsoft accounts and domain accounts. 4 - Digits, lowercase letters, uppercase letters, and special characters are required. Not supported in desktop. The default value is 1. 
      
      **Default**: 3  
  
    - **Number of sign-in failures before wiping device**  
      The number of authentication failures allowed before the device is wiped. A value of 0 disables device wipe functionality.
        
      **Default**: 10  
  
    - **Password expiration (days)**  
      The Maximum password age policy setting determines how long (in days) that a password can be used before the system requires the user to change it. You can set passwords to expire after a number of days between 1 and 999, or you can specify that passwords never expire by setting the number of days to 0. If Maximum password age is between 1 and 999 days, the minimum password age must be less than the maximum password age. If Maximum password age is set to 0, Minimum password age can be any value between 0 and 998 days.
      
      **Default**: 60  
  
    - **Required password type**  
      Determines the type of PIN or password required.
      
      **Default**: Alphanumeric  
  
    - **Minimum password length**  
      The Minimum password length policy setting determines the least number of characters that can make up a password for a user account. You can set a value of between 1 and 14 characters, or you can establish that no password is required by setting the number of characters to 0.
      
      **Default**: 8  
  
    - **Block simple passwords**  
      Specifies whether PINs or passwords such as "1111" or "1234" are allowed. For the desktop, it also controls the use of picture passwords.
      
      **Default**: Yes  
        *A setting of Yes prevents use of simple passwords.* 

  - **Prevent reuse of previous passwords**  
    Specifies how many passwords can be stored in the history that can’t be used. The value includes the user's current password. For example, with a setting of *1* the user can't reuse their current password when choosing a new password. A setting of *5* means that a user can't set their new password to their current password or any of their previous four passwords.
    
    **Default**: 24  

- **Prevent slide show**  
  Disables the lock screen slide show settings in PC Settings and prevents a slide show from playing on the lock screen. By default, users can enable a slide show that will run after they lock the machine. If you enable this setting, users can't modify slide show settings in PC Settings, and no slide show can start.
  
    **Default**: Enabled  
    *A setting of Enabled prevents slide shows from running.* 

- **Password minimum age in days**  
  The Minimum password age policy setting determines the period of time (in days) that a password must be used before the user can change it. You can set a value between 1 and 998 days, or you can allow password changes immediately by setting the number of days to 0. The minimum password age must be less than the Maximum password age, unless the maximum password age is set to 0, indicating that passwords will never expire. If the maximum password age is set to 0, the minimum password age can be set to any value between 0 and 998.
  
    **Default**: 1  

## Event Log Service  
For more information, see [Policy CSP - EventLogService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-eventlogservice) in the Windows documentation.  

- **Security log maximum file size in KB**  
  This policy setting specifies the maximum size of the log file in kilobytes. If you enable this policy setting, you can configure the maximum log file size to be between 1 megabyte (1024 kilobytes) and 2 terabytes (2147483647 kilobytes) in kilobyte increments. If you disable or don't configure this policy setting, the maximum size of the log file is set to the locally configured value. This value can be changed by the local administrator using the Log Properties dialog and it defaults to 20 megabytes.
  
   **Default**: 196608  

- **System log maximum file size in KB**  
  This policy setting specifies the maximum size of the log file in kilobytes. If you enable this policy setting, you can configure the maximum log file size to be between 1 megabyte (1024 kilobytes) and 2 terabytes (2147483647 kilobytes) in kilobyte increments. If you disable or don't configure this policy setting, the maximum size of the log file is set to the locally configured value. This value can be changed by the local administrator using the Log Properties dialog and it defaults to 20 megabytes.
  
  **Default**: 32768  

- **Application log maximum file size in KB**  
  This policy setting specifies the maximum size of the log file in kilobytes. If you enable this policy setting, you can configure the maximum log file size to be between 1 megabyte (1024 kilobytes) and 2 terabytes (2147483647 kilobytes) in kilobyte increments. If you disable or don't configure this policy setting, the maximum size of the log file is set to the locally configured value. This value can be changed by the local administrator using the Log Properties dialog and it defaults to 20 megabytes.
  
  **Default**: 32768  

## Experience  
For more information, see [Policy CSP - Experience](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience) in the Windows documentation.  

- **Block Windows Spotlight**  
  Allows IT admins to turn off all Windows Spotlight Features - Window spotlight on lock screen, Windows Tips, Microsoft consumer features, and other related features.
  
  **Default**: Yes  

  When *Block Windows Spotlight* is set to *Yes*, the following settings are available.
  
  - **Block third-party suggestions in Windows Spotlight**  
    Specifies whether to allow app and content suggestions from third-party software publishers in Windows spotlight features like lock screen spotlight, suggested apps in the Start menu, and Windows tips. Users may still see suggestions for Microsoft features, apps, and services.
      
    **Default**: Yes  
   - **Block consumer specific features**  
      Allows IT admins to turn on experiences that are typically for consumers only, such as Start suggestions, Membership notifications, Post-OOBE app install, and redirect tiles.
      
     **Default**: Yes  


## Exploit Guard  
For more information, see [Policy CSP - ExploitGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-exploitguard) in the Windows documentation.  

- **Exploit protection XML**  
  Enables the IT admin to push out a configuration that represents the desired system and application mitigation options to all the devices in the organization. The configuration is represented by an XML. Exploit protection helps protect devices from malware that use exploits to spread and infect. You use the Windows Security app or PowerShell to create a set of mitigations (known as a configuration). You can then export this configuration as an XML file and share it with multiple machines on your network so they all have the same set of mitigation settings. You can also convert and import an existing EMET configuration XML file into an exploit protection configuration XML.
  
  **Default**: *Sample xml is provided* 
 
## File Explorer  
For more information, see [Policy CSP - FileExplorer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-fileexplorer) in the Windows documentation.  

- **Block data execution prevention**  
  Disabling data execution prevention can allow certain legacy plug-in applications to function without terminating Explorer.
  
  **Default**: Disabled  
   
- **Block heap termination on corruption**  
  Disabling heap termination on corruption can allow certain legacy plug-in applications to function without terminating Explorer immediately, although Explorer may still terminate unexpectedly later.
  
  **Default**: Disabled  
    

## Internet Explorer  
For more information, see [Policy CSP - InternetExplorer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-internetexplorer) in the Windows documentation.  


- **Internet Explorer internet zone access to data sources**  
  This policy setting allows you to manage whether Internet Explorer can access data from another security zone using the Microsoft XML Parser (MSXML) or ActiveX Data Objects (ADO). If you enable this policy setting, users can load a page in the zone that uses MSXML or ADO to access data from another site in the zone. If you select Prompt in the drop-down box, users are queried to choose whether to allow a page to load in the zone that uses MSXML or ADO to access data from another site in the zone. If you disable this policy setting, users can't load a page in the zone that uses MSXML or ADO to access data from another site in the zone. If you don't configure this policy setting, users can't load a page in the zone that uses MSXML or ADO to access data from another site in the zone.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone drag content from different domains within windows**  
  This policy setting allows you to set options for dragging content from one domain to a different domain when the source and destination are in the same window. If you enable this policy setting and click Enable, users can drag content from one domain to a different domain when the source and destination are in the same window. Users can't change this setting. If you enable this policy setting and click Disable, users can't drag content from one domain to a different domain when the source and destination are in the same window. Users can't change this setting in the Internet Options dialog. In Internet Explorer 10, if you disable this policy setting or don't configure it, users can't drag content from one domain to a different domain when the source and destination are in the same window. Users can change this setting in the Internet Options dialog. In Internet Explorer 9 and earlier versions, if you disable this policy setting or don't configure it, users can drag content from one domain to a different domain when the source and destination are in the same window. Users can't change this setting in the Internet Options dialog.
  
  **Default**: Disabled
  
- **Internet Explorer certificate address mismatch warning**  
  This policy setting allows you to turn on the certificate address mismatch security warning. When this policy setting is turned on, the user is warned when visiting Secure HTTP (HTTPS) websites that present certificates issued for a different website address. This warning helps prevent spoofing attacks. If you enable this policy setting, the certificate address mismatch warning always appears. If you disable or don't configure this policy setting, the user can choose whether the certificate address mismatch warning appears (by using the Advanced page in the Internet Control panel).
  
  **Default**: Enabled 
  
- **Internet Explorer restricted zone less privileged sites**  
  This policy setting allows you to manage whether Web sites from less privileged zones, such as Internet sites, can navigate into this zone. If you enable this policy setting, Web sites from less privileged zones can open new windows in, or navigate into, this zone. The security zone will run without the added layer of security that is provided by the Protection from Zone Elevation security feature. If you select Prompt in the drop-down box, a warning is issued to the user that potentially risky navigation is about to occur. If you disable this policy setting, possibly harmful navigation is prevented. The Internet Explorer security feature is on in this zone as set by Protection from Zone Elevation feature control. If you don't configure this policy setting, the possibly harmful navigations are prevented. The Internet Explorer security feature is on in this zone as set by Protection from Zone Elevation feature control.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone automatic prompt for file downloads**  
  This policy setting determines whether users are prompted for non user-initiated file downloads. Regardless of this setting, users will receive file download dialogs for user-initiated downloads. If you enable this setting, users will receive a file download dialog for automatic download attempts. If you disable or don't configure this setting, file downloads that aren't user-initiated are blocked, and users will see the Notification bar instead of the file download dialog. Users can then click the Notification bar to allow the file download prompt.
  
  **Default**: Disabled
  
- **Internet Explorer internet zone .NET Framework reliant components**  
  This policy setting allows you to manage whether .NET Framework components that aren't signed with Authenticode can be executed from Internet Explorer. These components include managed controls referenced from an object tag and managed executables referenced from a link. If you enable this policy setting, Internet Explorer will execute unsigned managed components. If you select Prompt in the drop-down box, Internet Explorer will prompt the user to determine whether to execute unsigned managed components. If you disable this policy setting, Internet Explorer won't execute unsigned managed components. If you don't configure this policy setting, Internet Explorer will execute unsigned managed components.
  
  **Default**: Disable 
  
- **Internet Explorer internet zone allow only approved domains to use tdc ActiveX controls**  
  This policy setting controls if the user can run the TDC ActiveX control on websites. If you enable this policy setting, the TDC ActiveX control won't run from websites in this zone. If you disable this policy setting, the TDC Active X control will run from all sites in this zone.
  
  **Default**: Enabled 
  
- **Internet Explorer restricted zone script initiated windows**  
  This policy setting allows you to manage restrictions on script-initiated pop-up windows and windows that include the title and status bars. If you enable this policy setting, Windows Restrictions security won't apply in this zone. The security zone runs without the added layer of security provided by this feature. If you disable this policy setting, the possible harmful actions contained in script-initiated pop-up windows and windows that include the title and status bars can't run. This Internet Explorer security feature is on in this zone as dictated by the Scripted Windows Security Restrictions feature control setting for the process. If you don't configure this policy setting, the possible harmful actions contained in script-initiated pop-up windows and windows that include the title and status bars can't run. This Internet Explorer security feature is on in this zone as dictated by the Scripted Windows Security Restrictions feature control setting for the process.
  
  **Default**: Disabled 
  
- **Internet Explorer internet zone include local path when uploading files to server**  
  This policy setting controls if local path information gets sent when the user is uploading a file via an HTML form. If the local path information is sent, some information may be unintentionally revealed to the server. For instance, files sent from the user's desktop may contain the user name as a part of the path. If you enable this policy setting, path information is sent when the user is uploading a file via an HTML form. If you disable this policy setting, path information is removed when the user is uploading a file via an HTML form. If you don't configure this policy setting, the user can choose whether path information gets sent when they upload a file via an HTML form. By default, path information is sent.
  
  **Default**: Disabled 
  
- **Internet Explorer disable processes in enhanced protected mode**  
  This policy setting determines whether Internet Explorer 11 uses 64-bit processes (for greater security) or 32-bit processes (for greater compatibility) when running in Enhanced Protected Mode on 64-bit versions of Windows. Important: Some ActiveX controls and toolbars may not be available when 64-bit processes are used. If you enable this policy setting, Internet Explorer 11 will use 64-bit tab processes when running in Enhanced Protected Mode on 64-bit versions of Windows. If you disable this policy setting, Internet Explorer 11 will use 32-bit tab processes when running in Enhanced Protected Mode on 64-bit versions of Windows. If you don't configure this policy setting, users can turn this feature on or off using Internet Explorer settings. This feature is turned off by default.
  
  **Default**: Enabled 
  
- **Internet Explorer ignore certificate errors**  
  This policy setting prevents the user from ignoring Secure Sockets Layer/Transport Layer Security (SSL/TLS) certificate errors that interrupt browsing (such as "expired", "revoked", or "name mismatch" errors) in Internet Explorer. If you enable this policy setting, the user can't continue browsing. If you disable or don't configure this policy setting, the user can choose to ignore certificate errors and continue browsing.
  
  **Default**: Disabled 
  
- **Internet Explorer internet zone loading of XAML files**  
  This policy setting allows you to manage the loading of Extensible Application Markup Language (XAML) files. XAML is an XML-based declarative markup language commonly used for creating rich user interfaces and graphics that take advantage of the Windows Presentation Foundation. If you enable this policy setting and set the drop-down box to Enable, XAML files are automatically loaded inside Internet Explorer. The user can't change this behavior. If you set the drop-down box to Prompt, the user is prompted for loading XAML files. If you disable this policy setting, XAML files aren't loaded inside Internet Explorer. The user can't change this behavior. If you don't configure this policy setting, the user can decide whether to load XAML files inside Internet Explorer.
  
  **Default**: Disable 
  
- **Internet Explorer internet zone automatic prompt for file downloads**  
  This policy setting determines whether users are prompted for non user-initiated file downloads. Regardless of this setting, users will receive file download dialogs for user-initiated downloads. If you enable this setting, users will receive a file download dialog for automatic download attempts. If you disable or don't configure this setting, file downloads that aren't user-initiated are blocked, and users will see the Notification bar instead of the file download dialog. Users can then click the Notification bar to allow the file download prompt.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone security warning for potentially unsafe files**  
  This policy setting controls if the "Open File - Security Warning" message appears when the user tries to open executable files or other potentially unsafe files (from an intranet file share by using File Explorer, for example). If you enable this policy setting and set the drop-down box to Enable, these files open without a security warning. If you set the drop-down box to Prompt, a security warning appears before the files open. If you disable this policy setting, these files don't open. If you don't configure this policy setting, the user can configure how the computer handles these files. By default, these files are blocked in the Restricted zone, enabled in the Intranet and Local Computer zones, and set to prompt in the Internet and Trusted zones.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone cross site scripting filter**  
  This policy controls if the Cross-Site Scripting (XSS) Filter will detect and prevent cross-site script injections into websites in this zone. If you enable this policy setting, the XSS Filter is turned on for sites in this zone, and the XSS Filter attempts to block cross-site script injections. If you disable this policy setting, the XSS Filter is turned off for sites in this zone, and Internet Explorer permits cross-site script injections.
  
  **Default**: Enabled 
  
- **Internet Explorer fallback to SSL3**  
  This policy setting allows you to block an insecure fallback to SSL 3.0. When this policy is enabled, Internet Explorer will attempt to connect to sites using SSL 3.0 or below when TLS 1.0 or greater fails. We recommend that you don't allow insecure fallback in order to prevent a man-in-the-middle attack. This policy doesn't affect which security protocols are enabled. If you disable this policy, system defaults are used.
  
  **Default**: No sites 
  
- **Internet Explorer locked down internet zone smart screen**  
  This policy setting controls whether SmartScreen Filter scans pages in this zone for malicious content. If you enable this policy setting, SmartScreen Filter scans pages in this zone for malicious content. If you disable this policy setting, SmartScreen Filter doesn't scan pages in this zone for malicious content. If you don't configure this policy setting, the user can choose whether SmartScreen Filter scans pages in this zone for malicious content. Note: In Internet Explorer 7, this policy setting controls whether Phishing Filter scans pages in this zone for malicious content.
  
  **Default**: Enabled 
  
- **Internet Explorer restricted zone launch applications and files in an iFrame**  
  This policy setting allows you to manage whether applications may be run and files may be downloaded from an IFRAME reference in the HTML of the pages in this zone. If you enable this policy setting, users can run applications and download files from IFRAMEs on the pages in this zone without user intervention. If you select Prompt in the drop-down box, users are queried to choose whether to run applications and download files from IFRAMEs on the pages in this zone. If you disable this policy setting, users are prevented from running applications and downloading files from IFRAMEs on the pages in this zone. If you don't configure this policy setting, users are prevented from running applications and downloading files from IFRAMEs on the pages in this zone.
  
  **Default**: Disable 
  
- **Internet Explorer bypass smart screen warnings about uncommon files**  
  This policy setting determines whether the user can bypass warnings from SmartScreen Filter. SmartScreen Filter warns the user about executable files that Internet Explorer users don't commonly download from the Internet. If you enable this policy setting, SmartScreen Filter warnings block the user. If you disable or don't configure this policy setting, the user can bypass SmartScreen Filter warnings.
  
  **Default**: Disabled  
  
- **Internet Explorer internet zone popup blocker**  
  This policy setting allows you to manage whether unwanted pop-up windows appear. Pop-up windows that are opened when the end user clicks a link aren't blocked. If you enable this policy setting, most unwanted pop-up windows are prevented from appearing. If you disable this policy setting, pop-up windows aren't prevented from appearing. If you don't configure this policy setting, most unwanted pop-up windows are prevented from appearing.
  
  **Default**: Enable  
  
- **Internet Explorer processes consistent MIME handling**  
  Internet Explorer contains dynamic binary behaviors: components that encapsulate specific functionality for the HTML elements to which they're attached. This policy setting controls whether the Binary Behavior Security Restriction setting is prevented or allowed. If you enable this policy setting, binary behaviors are prevented for the File Explorer and Internet Explorer processes. If you disable this policy setting, binary behaviors are allowed for the File Explorer and Internet Explorer processes. If you don't configure this policy setting, binary behaviors are prevented for the File Explorer and Internet Explorer processes.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone java permissions**  
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, Java applets are disabled.
  
  **Default**: Disable java  
    
  
- **Internet Explorer Active X controls in protected mode**  
  This policy setting prevents ActiveX controls from running in Protected Mode when Enhanced Protected Mode is enabled. When a user has an ActiveX control installed that isn't compatible with Enhanced Protected Mode and a website attempts to load the control, Internet Explorer notifies the user and gives the option to run the website in regular Protected Mode. This policy setting disables this notification and forces all websites to run in Enhanced Protected Mode. Enhanced Protected Mode provides additional protection against malicious websites by using 64-bit processes on 64-bit versions of Windows. For computers running at least Windows 8, Enhanced Protected Mode also limits the locations Internet Explorer can read from in the registry and the file system. When Enhanced Protected Mode is enabled, and a user comes across a website that attempts to load an ActiveX control that isn't compatible with Enhanced Protected Mode, Internet Explorer notifies the user and gives the option to disable Enhanced Protected Mode for that particular website. If you enable this policy setting, Internet Explorer won't give the user the option to disable Enhanced Protected Mode. All Protected Mode websites will run in Enhanced Protected Mode. If you disable or don't configure this policy setting, Internet Explorer notifies users and provides an option to run websites with incompatible ActiveX controls in regular Protected Mode.  
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone loading of XAML files**  
  This policy setting allows you to manage the loading of Extensible Application Markup Language (XAML) files. XAML is an XML-based declarative markup language commonly used for creating rich user interfaces and graphics that take advantage of the Windows Presentation Foundation. If you enable this policy setting and set the drop-down box to Enable, XAML files are automatically loaded inside Internet Explorer. The user can't change this behavior. If you set the drop-down box to Prompt, the user is prompted for loading XAML files. If you disable this policy setting, XAML files aren't loaded inside Internet Explorer. The user can't change this behavior. If you don't configure this policy setting, the user can decide whether to load XAML files inside Internet Explorer.
  
  **Default**: Disable  
  
- **Internet Explorer processes scripted window security restrictions**  
  Internet Explorer allows scripts to programmatically open, resize, and reposition windows of various types. The Window Restrictions security feature restricts popup windows and prohibits scripts from displaying windows in which the title and status bars aren't visible to the user or obfuscate other Windows' title and status bars. If you enable this policy setting, scripted windows are restricted for all processes. If you disable or don't configure this policy setting, scripted windows aren't restricted.
  
  **Default**: Enabled   
  
- **Internet Explorer restricted zone run Active X controls and plugins**  
  This policy setting allows you to manage whether ActiveX controls and plug-ins can run on pages from the specified zone. If you enable this policy setting, controls and plug-ins can run without user intervention. If you selected Prompt in the drop-down box, users are asked to choose whether to allow the controls or plug-in to run. If you disable this policy setting, controls and plug-ins are prevented from running. If you don't configure this policy setting, controls and plug-ins are prevented from running.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone script Active X controls marked safe for scripting**  
  This policy setting allows you to manage whether an ActiveX control marked safe for scripting can interact with a script. If you enable this policy setting, script interaction can occur automatically without user intervention. If you select Prompt in the drop-down box, users are queried to choose whether to allow script interaction. If you disable this policy setting, script interaction is prevented from occurring. If you don't configure this policy setting, script interaction is prevented from occurring.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone logon options**  
  This policy setting allows you to manage settings for sign in options. If you enable this policy setting, you can choose from the following sign in options. 
  - *Anonymous*  - Use anonymous sign in to disable HTTP authentication and use the guest account only for the Common Internet File System (CIFS) protocol. 
  - *Prompt* - Use prompt for user name and password to query users for user IDs and passwords. After a user is queried, these values can be used silently for the rest of the session. 
  - *Automatic sign in only in Intranet zone* - Use this option to query users for user IDs and passwords in other zones. After a user is queried, these values can be used silently for the rest of the session. 
  - *Automatic sign in with current user name and password*- Use this option to attempt sign in using Windows NT Challenge Response (also known as NTLM authentication). If the server supports Windows NT Challenge Response, the sign in uses the user's network user name and password for sign in. If the server doesn't support Windows NT Challenge Response, the user is queried to provide the user name and password. 

  If you disable this policy setting, sign-in is set to *Automatic sign in only in Intranet zone*. If you don't configure this policy setting, sign-in is set to *Prompt* for username and password.
  
  **Default**: Anonymous  
  
- **Internet Explorer trusted zone initialize and script Active X controls not marked as safe**  
  This policy setting allows you to manage ActiveX controls not marked as safe. If you enable this policy setting, ActiveX controls run, loaded with parameters, and scripted without setting object safety for untrusted data or scripts. This setting isn't recommended, except for secure and administered zones. This setting causes both unsafe and safe controls to be initialized and scripted, ignoring the Script ActiveX controls marked safe for scripting option. If you enable this policy setting and select Prompt in the drop-down box, users are queried whether to allow the control to load with parameters or scripted. If you disable this policy setting, ActiveX controls that can't be made safe aren't loaded with parameters or scripted. If you don't configure this policy setting, users are queried whether to allow the control to load with parameters or scripted.
  
  **Default**: Disable  
  
- **Internet Explorer check server certificate revocation**  
  This policy setting allows you to manage whether Internet Explorer will check revocation status of servers' certificates. Certificates are revoked when they are compromised or no longer valid, and this option protects users from submitting confidential data to a site that may be fraudulent or not secure. If you enable this policy setting, Internet Explorer will check to see if server certificates have been revoked. If you disable this policy setting, Internet Explorer won't check server certificates to see if they have been revoked. If you don't configure this policy setting, Internet Explorer won't check server certificates to see if they have been revoked.
  
  **Default**: Enabled 
  
- **Internet Explorer internet zone less privileged sites**  
  This policy setting allows you to manage whether Web sites from less privileged zones, such as Restricted Sites, can navigate into this zone. If you enable this policy setting, Web sites from less privileged zones can open new windows in, or navigate into, this zone. The security zone will run without the added layer of security that is provided by the Protection from Zone Elevation security feature. If you select Prompt in the drop-down box, a warning is issued to the user that potentially risky navigation is about to occur. If you disable this policy setting, the possibly harmful navigations are prevented. The Internet Explorer security feature is on in this zone as set by Protection from Zone Elevation feature control. If you don't configure this policy setting, Web sites from less privileged zones can open new windows in, or navigate into, this zone.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone file downloads**  
  This policy setting allows you to manage whether file downloads are permitted from the zone. This option gets determined by the zone of the page with the link causing the download, not the zone from which the file is delivered. If you enable this policy setting, files can be downloaded from the zone. If you disable this policy setting, files are prevented from being downloaded from the zone. If you don't configure this policy setting, files are prevented from being downloaded from the zone.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone run .NET Framework reliant components signed with Authenticode**  
  This policy setting allows you to manage whether .NET Framework components that are signed with Authenticode can be executed from Internet Explorer. These components include managed controls referenced from an object tag and managed executables referenced from a link. If you enable this policy setting, Internet Explorer will execute signed managed components. If you select Prompt in the drop-down box, Internet Explorer will prompt the user to determine whether to execute signed managed components. If you disable this policy setting, Internet Explorer won't execute signed managed components. If you don't configure this policy setting, Internet Explorer won't execute signed managed components.
  
  **Default**: Disable  
  
- **Internet Explorer prevent per user installation of Active X controls**  
  This policy setting allows you to prevent the installation of ActiveX controls on a per-user basis. If you enable this policy setting, ActiveX controls can't be installed on a per-user basis. If you disable or don't configure this policy setting, ActiveX controls can be installed on a per-user basis.
  
  **Default**: Enabled  
  
- **Internet Explorer prevent managing smart screen filter**  
  This policy setting prevents the user from managing SmartScreen Filter, which warns the user if the website they visit is known for fraudulent attempts to gather personal information through "phishing," or is known to host malware. If you enable this policy setting, the user isn't prompted to turn on SmartScreen Filter. All website addresses that aren't on the filters allow list are sent automatically to Microsoft without prompting the user. If you disable or don't configure this policy setting, the user gets prompted to decide whether to turn on SmartScreen Filter during the first-run experience.
  
  **Default**: Enable  
  
- **Internet Explorer processes MIME sniffing safety feature**  
  This policy setting determines whether Internet Explorer MIME sniffing will prevent promotion of a file of one type to a more dangerous file type. If you enable this policy setting, MIME sniffing will never promote a file of one type to a more dangerous file type. If you disable this policy setting, Internet Explorer processes will allow a MIME sniff promoting a file of one type to a more dangerous file type. If you don't configure this policy setting, MIME sniffing will never promote a file of one type to a more dangerous file type.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone download signed Active X controls**  
  This policy setting allows you to manage whether users may download signed ActiveX controls from a page in the zone. If you enable this policy, users can download signed controls without user intervention. If you select Prompt in the drop-down box, users are queried whether to download controls signed by publishers who aren't trusted. Code signed by trusted publishers is silently downloaded. If you disable the policy setting, signed controls can't download. If you don't configure this policy setting, users are queried whether to download controls signed by publishers who aren't trusted. Code signed by trusted publishers is silently downloaded.
  
  **Default**: Disable  
  
- **Internet Explorer auto complete**  
  This Auto-Complete feature can remember and suggest User names and passwords on Forms. If you enable this setting, the user can't change "User name and passwords on forms" or "prompt me to save passwords". The Auto Complete feature for User names and passwords on Forms is turned on. You have to decide whether to select "prompt me to save passwords". If you disable this setting the user can't change "User name and passwords on forms" or "prompt me to save passwords". The Auto Complete feature for User names and passwords on Forms is turned off. The user also can't opt to be prompted to save passwords. If you don't configure this setting, the user has the freedom of turning on Auto complete for User name and passwords on forms and the option of prompting to save passwords. To display this option, the users open the Internet Options dialog box, click the Contents Tab, and click the Settings button.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone allow VBscript to run**  
  This policy setting lets you decide whether VBScript can run on pages in specific Internet Explorer zones. Options include: 
  - *Enable* - VBScript runs on pages in specific zones, without any interaction. 
  - *Prompt* - Employees are prompted whether to allow VBScript to run in the zone. 
  - *Disable* - VBScript is prevented from running in the zone. If you disable or don’t configure this policy setting, VBScript runs without any interaction in the specified zone. 
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone allow only approved domains to use tdc Active X controls**  
  This policy setting controls if the user can run the TDC ActiveX control on websites. If you enable this policy setting, the TDC ActiveX control won't run from websites in this zone. If you disable this policy setting, the TDC Active X control will run from all sites in this zone.
  
  **Default**: Enabled  
  
- **Internet Explorer trusted zone don't run antimalware against Active X controls**  
  This policy setting determines whether Internet Explorer runs antimalware programs against ActiveX controls, to check if they're safe to load on pages. If you enable this policy setting, Internet Explorer won't check with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you disable this policy setting, Internet Explorer always checks with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you don't configure this policy setting, Internet Explorer always checks with your antimalware program to see if it's safe to create an instance of the ActiveX control. Users can turn this behavior on or off, using Internet Explorer Security settings.
  
  **Default**: Disabled 
  
- **Internet Explorer local machine zone java permissions**  
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, the permission is set to Medium Safety.
  
  **Default**: Disable java 
  
- **Internet Explorer intranet zone do not run antimalware against Active X controls**
  This policy setting determines whether Internet Explorer runs antimalware programs against ActiveX controls, to check if they're safe to load on pages. If you enable this policy setting, Internet Explorer won't check with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you disable this policy setting, Internet Explorer always checks with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you don't configure this policy setting, Internet Explorer won't check with your antimalware program to see if it's safe to create an instance of the ActiveX control. Users can turn this behavior on or off, using Internet Explorer Security settings.
  
  **Default**: Disabled  

- **Internet Explorer restricted zone scriptlets**  
  This policy setting allows you to manage whether the user can run scriptlets. If you enable this policy setting, the user can run scriptlets. If you disable this policy setting, the user can't run scriptlets. If you don't configure this policy setting, the user can enable or disable scriptlets.
  
  **Default**: Disabled  
  
- **Internet Explorer processes notification bar**  
  This policy setting allows you to manage whether the Notification bar is displayed for Internet Explorer processes when file or code installs are restricted. By default, the Notification bar is displayed for Internet Explorer processes. If you enable this policy setting, the Notification bar displays for the Internet Explorer Processes. If you disable this policy setting, the Notification bar won't be displayed for Internet Explorer processes. If you don't configure this policy setting, the Notification bar doesn't display for Internet Explorer Processes.
  
  **Default**: Enabled  
  
- **Internet Explorer internet zone download signed ActiveX controls**  
  This policy setting allows you to manage whether users may download signed ActiveX controls from a page in the zone. If you enable this policy, users can download signed controls without user intervention. If you select Prompt in the drop-down box, users are queried whether to download controls signed by publishers who aren't trusted. Code signed by trusted publishers is silently downloaded. If you disable the policy setting, signed controls can't download. If you don't configure this policy setting, users are queried whether to download controls signed by publishers who aren't trusted. Code signed by trusted publishers is silently downloaded.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone smart screen**  
  This policy setting controls whether SmartScreen Filter scans pages in this zone for malicious content. If you enable this policy setting, SmartScreen Filter scans pages in this zone for malicious content. If you disable this policy setting, SmartScreen Filter doesn't scan pages in this zone for malicious content. If you don't configure this policy setting, the user can choose whether SmartScreen Filter scans pages in this zone for malicious content. Note: In Internet Explorer 7, this policy setting controls whether Phishing Filter scans pages in this zone for malicious content.
  
  **Default**: Enabled  
  
- **Internet Explorer remove run this time button for outdated Active X controls**  
  This policy setting allows you to stop users from seeing the "Run this time" button and from running specific outdated ActiveX controls in Internet Explorer. If you enable this policy setting, users won't see the "Run this time" button on the warning message that appears when Internet Explorer blocks an outdated ActiveX control. If you disable or don't configure this policy setting, users will see the "Run this time" button on the warning message that appears when Internet Explorer blocks an outdated ActiveX control. Clicking this button lets the user run the outdated ActiveX control once. For more information, see "Outdated ActiveX Controls" in the Internet Explorer TechNet library.
  
  **Default**: Enabled 
  
- **Internet Explorer internet zone launch applications and files in an iframe**  
  This policy setting allows you to manage whether applications may be run and files may be downloaded from an IFRAME reference in the HTML of the pages in this zone. If you enable this policy setting, users can run applications and download files from IFRAMEs on the pages in this zone without user intervention. If you select Prompt in the drop-down box, users are queried to choose whether to run applications and download files from IFRAMEs on the pages in this zone. If you disable this policy setting, users are prevented from running applications and downloading files from IFRAMEs on the pages in this zone. If you don't configure this policy setting, users are queried to choose whether to run applications and download files from IFRAMEs on the pages in this zone
  
  **Default**: Disable 
  
- **Internet Explorer restricted zone navigate windows and frames across different domains**  
  This policy setting allows you to set options for dragging content from one domain to a different domain when the source and destination are in different windows. If you enable this policy setting and click Enable, users can drag content from one domain to a different domain when the source and destination are in different windows. Users can't change this setting. If you enable this policy setting and click Disable, users can't drag content from one domain to a different domain when both the source and destination are in different windows. Users can't change this setting. In Internet Explorer 10, if you disable this policy setting or don't configure it, users can't drag content from one domain to a different domain when the source and destination are in different windows. Users can change this setting in the Internet Options dialog. In Internet Explorer 9 and earlier versions, if you disable this policy or don't configure it, users can drag content from one domain to a different domain when the source and destination are in different windows. Users can't change this setting.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone smart screen**  
  This policy setting controls whether SmartScreen Filter scans pages in this zone for malicious content. If you enable this policy setting, SmartScreen Filter scans pages in this zone for malicious content. If you disable this policy setting, SmartScreen Filter doesn't scan pages in this zone for malicious content. If you don't configure this policy setting, the user can choose whether SmartScreen Filter scans pages in this zone for malicious content. Note: In Internet Explorer 7, this policy setting controls whether Phishing Filter scans pages in this zone for malicious content.
  
  **Default**: Enabled  
  
- **Internet Explorer locked down trusted zone java permissions**  
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, Java applets are disabled.
  
  **Default**: Disable java 
  
- **Internet Explorer check signatures on downloaded programs**  
  This policy setting allows you to manage whether Internet Explorer checks for digital signatures (which identifies the publisher of signed software and verifies it hasn't been modified or tampered with) on user computers before downloading executable programs. If you enable this policy setting, Internet Explorer will check the digital signatures of executable programs and display their identities before downloading them to user computers. If you disable this policy setting, Internet Explorer won't check the digital signatures of executable programs or display their identities before downloading them to user computers. If you don't configure this policy, Internet Explorer won't check the digital signatures of executable programs or display their identities before downloading them to user computers.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone scripting of web browser controls**  
  This policy setting determines whether a page can control embedded WebBrowser controls via script. If you enable this policy setting, script access to the WebBrowser control is allowed. If you disable this policy setting, script access to the WebBrowser control isn't allowed. If you don't configure this policy setting, the user can enable or disable script access to the WebBrowser control. By default, script access to the WebBrowser control is allowed only in the Local Machine and Intranet zones.
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone cross site scripting filter**  
  This policy controls if the Cross-Site Scripting (XSS) Filter will detect and prevent cross-site script injections into websites in this zone. If you enable this policy setting, the XSS Filter is turned on for sites in this zone, and the XSS Filter attempts to block cross-site script injections. If you disable this policy setting, the XSS Filter is turned off for sites in this zone, and Internet Explorer permits cross-site script injections.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone binary and script behaviors**  
  This policy setting allows you to manage dynamic binary and script behaviors: components that encapsulate specific functionality for HTML elements to which they were attached. If you enable this policy setting, binary and script behaviors are available. If you select Administrator approved in the drop-down box, only behaviors listed in the Admin-approved Behaviors under Binary Behaviors Security Restriction policy are available. If you disable this policy setting, binary and script behaviors aren't available unless applications have implemented a custom security manager. If you don't configure this policy setting, binary and script behaviors aren't available unless applications have implemented a custom security manager.
  
  **Default**: Disable  
  
- **Internet Explorer security settings check**  
  This policy setting turns off the Security Settings Check feature, which checks Internet Explorer security settings to determine when the settings put Internet Explorer at risk. If you enable this policy setting, the feature is turned off. If you disable or don't configure this policy setting, the feature is turned on.
  
  **Default**: Enabled  
  
- **Internet Explorer internet zone security warning for potentially unsafe files**  
  This policy setting controls if the "Open File - Security Warning" message appears when the user tries to open executable files or other potentially unsafe files (from an intranet file share by using File Explorer, for example). If you enable this policy setting and set the drop-down box to Enable, these files open without a security warning. If you set the drop-down box to Prompt, a security warning appears before the files open. If you disable this policy setting, these files don't open. If you don't configure this policy setting, the user can configure how the computer handles these files. By default, these files are blocked in the Restricted zone, enabled in the Intranet and Local Computer zones, and set to prompt in the Internet and Trusted zones.
  
  **Default**: Prompt  
  
- **Internet Explorer intranet zone java permissions**  
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, the permission is set to Medium Safety.
  
  **Default**: High safety 
  
- **Internet Explorer block outdated Active X controls**  
  This policy setting determines whether Internet Explorer blocks specific outdated ActiveX controls. Outdated ActiveX controls are never blocked in the Intranet Zone. If you enable this policy setting, Internet Explorer stops blocking outdated ActiveX controls. If you disable or don't configure this policy setting, Internet Explorer continues to block specific outdated ActiveX controls. For more information, see "Outdated ActiveX Controls" in the Internet Explorer TechNet library.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone popup blocker**  
  This policy setting allows you to manage whether unwanted pop-up windows appear. Pop-up windows that are opened when the end user clicks a link aren't blocked. If you enable this policy setting, most unwanted pop-up windows are prevented from appearing. If you disable this policy setting, pop-up windows aren't prevented from appearing. If you don't configure this policy setting, most unwanted pop-up windows are prevented from appearing.
  
  **Default**: Enable  
  
- **Internet Explorer processes MK protocol security restriction**  
  The MK Protocol Security Restriction policy setting reduces attack surface area by preventing the MK protocol. Resources hosted on the MK protocol will fail. If you enable this policy setting, the MK Protocol is prevented for File Explorer and Internet Explorer, and resources hosted on the MK protocol will fail. If you disable this policy setting, applications can use the MK protocol API. Resources hosted on the MK protocol will work for the File Explorer and Internet Explorer processes. If you don't configure this policy setting, the MK Protocol is prevented for File Explorer and Internet Explorer, and resources hosted on the MK protocol will fail.
  
  **Default**: Enabled  
  
- **Internet Explorer trusted zone java permissions**   
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, the permission is set to Low Safety.
  
  **Default**: High safety  
  
- **Internet Explorer restricted zone scripting of java applets**  
  This policy setting allows you to manage whether applets are exposed to scripts within the zone. If you enable this policy setting, scripts can access applets automatically without user intervention. If you select Prompt in the drop-down box, users are queried to choose whether to allow scripts to access applets. If you disable this policy setting, scripts are prevented from accessing applets. If you don't configure this policy setting, scripts are prevented from accessing applets.
  
  **Default**: Disable  
  
- **Internet Explorer locked down restricted zone java permissions**   
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, Java applets are disabled.
  
  **Default**: Disable java 
  
- **Internet Explorer internet zone allow only approved domains to use ActiveX controls**   
  This policy setting controls if the user is prompted to allow ActiveX controls to run on websites other than the website that installed the ActiveX control. If you enable this policy setting, the user is prompted before ActiveX controls can run from websites in this zone. The user can choose to allow the control to run from the current site or from all sites. If you disable this policy setting, the user doesn't see the per-site ActiveX prompt, and ActiveX controls can run from all sites in this zone.
  
  **Default**: Enabled  
  
- **Internet Explorer include all network paths**  
  Internet Explorer include all network paths
  
  **Default**: Disabled 
  
- **Internet Explorer internet zone protected mode**  
  This policy setting allows you to turn on Protected Mode. Protected Mode helps protect Internet Explorer from exploited vulnerabilities by reducing the locations that Internet Explorer can write to in the registry and the file system. If you enable this policy setting, Protected Mode is turned on. The user can't turn off Protected Mode. If you disable this policy setting, Protected Mode is turned off. The user can't turn on Protected Mode. If you don't configure this policy setting, the user can turn on or turn off Protected Mode.
  
  **Default**: Enable 
  
- **Internet Explorer internet zone initialize and script Active X controls not marked as safe**  
  This policy setting allows you to manage ActiveX controls not marked as safe. If you enable this policy setting, ActiveX controls run, loaded with parameters, and scripted without setting object safety for untrusted data or scripts. This setting isn't recommended, except for secure and administered zones. This setting causes both unsafe and safe controls to be initialized and scripted, ignoring the Script ActiveX controls marked safe for scripting option. If you enable this policy setting and select Prompt in the drop-down box, users are queried whether to allow the control to load with parameters or scripted. If you disable this policy setting, ActiveX controls that can't be made safe aren't loaded with parameters or scripted. If you don't configure this policy setting, ActiveX controls that can't be made safe aren't loaded with parameters or scripted.
  
  **Default**: Disable 
  
- **Internet Explorer locked down restricted zone smart screen**   
  This policy setting controls whether SmartScreen Filter scans pages in this zone for malicious content. If you enable this policy setting, SmartScreen Filter scans pages in this zone for malicious content. If you disable this policy setting, SmartScreen Filter doesn't scan pages in this zone for malicious content. If you don't configure this policy setting, the user can choose whether SmartScreen Filter scans pages in this zone for malicious content. Note: In Internet Explorer 7, this policy setting controls whether Phishing Filter scans pages in this zone for malicious content.
  
  **Default**: Enabled  
  
- **Internet Explorer crash detection**  
  This policy setting allows you to manage the crash detection feature of add-on Management. If you enable this policy setting, a crash in Internet Explorer will exhibit behavior found in Windows XP Professional Service Pack 1 and earlier, namely to invoke Windows Error Reporting. All policy settings for Windows Error Reporting continue to apply. If you disable or don't configure this policy setting, the crash detection feature for add-on management is functional.
  
  **Default**: Disabled  
  
- **Internet Explorer internet zone java permissions**  
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, the permission is set to High Safety.
  
  **Default**: Disable java  
  
- **Internet Explorer restricted zone active scripting**  
  This policy setting allows you to manage whether script code on pages in the zone is run. If you enable this policy setting, script code on pages in the zone can run automatically. If you select Prompt in the drop-down box, users are queried to choose whether to allow script code on pages in the zone to run. If you disable this policy setting, script code on pages in the zone is prevented from running. If you don't configure this policy setting, script code on pages in the zone is prevented from running.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone logon options**  
  This policy setting allows you to manage settings for sign in options. If you enable this policy setting, you can choose from the following sign in options. Anonymous log on to disable HTTP authentication and use the guest account only for the Common Internet File System (CIFS) protocol. Prompt for user name and password to query users for user IDs and passwords. After a user is queried, these values can be used silently for the remainder of the session. Automatic log on only in Intranet zone to query users for user IDs and passwords in other zones. After a user is queried, these values can be used silently for the rest of the session. Automatic sign in with current user name and password to attempt log on using Windows NT Challenge Response (also known as NTLM authentication). If the server supports Windows NT Challenge Response, the sign in uses the user's network user name and password for log on. If If the server doesn't support Windows NT Challenge Response, the user is queried to provide the user name and password. If you disable this policy setting, sign in is set to Automatic log on only in Intranet zone. If you don't configure this policy setting, sign in is set to Automatic sign in only in Intranet zone.
  
  **Default**: Prompt  
  
- **Internet Explorer restricted zone allow vbscript to run**  
  This policy setting allows you to manage whether VBScript can be run on pages from the specified zone in Internet Explorer. If you selected Enable in the drop-down box, VBScript can run without user intervention. If you selected Prompt in the drop-down box, users are asked to choose whether to allow VBScript to run. If you selected Disable in the drop-down box, VBScript is prevented from running. If you don't configure or disable this policy setting, VBScript is prevented from running.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone drag content from different domains across windows**  
  This policy setting allows you to set options for dragging content from one domain to a different domain when the source and destination are in different windows. If you enable this policy setting and click Enable, users can drag content from one domain to a different domain when the source and destination are in different windows. Users can't change this setting. If you enable this policy setting and click Disable, users can't drag content from one domain to a different domain when both the source and destination are in different windows. Users can't change this setting. In Internet Explorer 10, if you disable this policy setting or don't configure it, users can't drag content from one domain to a different domain when the source and destination are in different windows. Users can change this setting in the Internet Options dialog. In Internet Explorer 9 and earlier versions, if you disable this policy or don't configure it, users can drag content from one domain to a different domain when the source and destination are in different windows. Users can't change this setting.
  
  **Default**: Disabled 
  
- **Internet Explorer intranet zone initialize and script Active X controls not marked as safe**  
  This policy setting allows you to manage ActiveX controls not marked as safe. If you enable this policy setting, ActiveX controls run, loaded with parameters, and scripted without setting object safety for untrusted data or scripts. This setting isn't recommended, except for secure and administered zones. This setting causes both unsafe and safe controls to be initialized and scripted, ignoring the Script ActiveX controls marked safe for scripting option. If you enable this policy setting and select Prompt in the drop-down box, users are queried whether to allow the control to load with parameters or scripted. If you disable this policy setting, ActiveX controls that can't be made safe aren't loaded with parameters or scripted. If you don't configure this policy setting, ActiveX controls that can't be made safe aren't loaded with parameters or scripted.
  
  **Default**: Disable 
  
- **Internet Explorer download enclosures**  
  This policy setting prevents the user from having enclosures (file attachments) downloaded from a feed to the user's computer. If you enable this policy setting, the user can't set the Feed Sync Engine to download an enclosure through the Feed property page. A developer can't change the download setting through the Feed APIs. If you disable or don't configure this policy setting, the user can set the Feed Sync Engine to download an enclosure through the Feed property page. A developer can change the download setting through the Feed APIs.
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone download unsigned Active X controls**   
  This policy setting allows you to manage whether users may download unsigned ActiveX controls from the zone. Such code is potentially harmful, especially when coming from an untrusted zone. If you enable this policy setting, users can run unsigned controls without user intervention. If you select Prompt in the drop-down box, users are queried to choose whether to allow the unsigned control to run. If you disable this policy setting, users can't run unsigned controls. If you don't configure this policy setting, users can't run unsigned controls.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone drag content from different domains within windows**  
  This policy setting allows you to manage whether users may download unsigned ActiveX controls from the zone. Such code is potentially harmful, especially when coming from an untrusted zone. If you enable this policy setting, users can run unsigned controls without user intervention. If you select Prompt in the drop-down box, users are queried to choose whether to allow the unsigned control to run. If you disable this policy setting, users can't run unsigned controls. If you don't configure this policy setting, users can't run unsigned controls.
  
  **Default**: Disabled  
  
- **Internet Explorer processes restrict Active X install**   
  This policy setting enables applications hosting the Web Browser Control to block automatic prompting of ActiveX control installation. If you enable this policy setting, the Web Browser Control will block automatic prompting of ActiveX control installation for all processes. If you disable or don't configure this policy setting, the Web Browser Control won't block automatic prompting of ActiveX control installation for all processes.
  
  **Default**: Enabled  
  
- **Internet Explorer internet zone scriptlets**
  This policy setting allows you to manage whether the user can run scriptlets. If you enable this policy setting, the user can run scriptlets. If you disable this policy setting, the user can't run scriptlets. If you don't configure this policy setting, the user can enable or disable scriptlets.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone drag and drop or copy and paste files**  
  This policy setting allows you to manage whether users can drag files or copy and paste files from a source within the zone. If you enable this policy setting, users can drag files or copy and paste files from this zone automatically. If you select Prompt in the drop-down box, users are queried to choose whether to drag or copy files from this zone. If you disable this policy setting, users are prevented from dragging files or copying and pasting files from this zone. If you don't configure this policy setting, users are queried to choose whether to drag or copy files from this zone.
  
  **Default**: Disable  
  
- **Internet Explorer software when signature is invalid**   
  This policy setting allows you to manage whether software, such as ActiveX controls and file downloads, can be installed or run by the user even though the signature is invalid. An invalid signature might indicate that someone has tampered with the file. If you enable this policy setting, users are prompted to install or run files with an invalid signature. If you disable this policy setting, users can't run or install files with an invalid signature. If you don't configure this policy, users can choose to run or install files with an invalid signature.
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone copy and paste via script**   
  This policy setting allows you to manage whether scripts can perform a clipboard operation (for example, cut, copy, and paste) in a specified region. If you enable this policy setting, a script can perform a clipboard operation. If you select Prompt in the drop-down box, users are queried as to whether to perform clipboard operations. If you disable this policy setting, a script can't perform a clipboard operation. If you don't configure this policy setting, a script can't perform a clipboard operation.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone drag content from different domains across windows**  
  This policy setting allows you to set options for dragging content from one domain to a different domain when the source and destination are in different windows. If you enable this policy setting and click Enable, users can drag content from one domain to a different domain when the source and destination are in different windows. Users can't change this setting. If you enable this policy setting and click Disable, users can't drag content from one domain to a different domain when both the source and destination are in different windows. Users can't change this setting. In Internet Explorer 10, if you disable this policy setting or don't configure it, users can't drag content from one domain to a different domain when the source and destination are in different windows. Users can change this setting in the Internet Options dialog. In Internet Explorer 9 and earlier versions, if you disable this policy or don't configure it, users can drag content from one domain to a different domain when the source and destination are in different windows. Users can't change this setting.   
  **Default**: Disabled  
  
- **Internet Explorer users adding sites**  
  Prevents users from adding or removing sites from security zones. A security zone is a group of Web sites with the same security level. If you enable this policy, the site management settings for security zones are disabled. (To see the site management settings for security zones, in the Internet Options dialog box, click the Security tab, and then click the Sites button.) If you disable this policy or don't configure it, users can add Web sites to or remove sites from the Trusted Sites and Restricted Sites zones, and alter settings for the Local Intranet zone. This policy prevents users from changing site management settings for security zones established by the administrator. Note: The "Disable the Security page" policy (located in \User Configuration\Administrative Templates\Windows Components\Internet Explorer\Internet Control Panel), which removes the Security tab from the interface, takes precedence over this policy. If it's enabled, this policy is ignored. Also, see the "Security zones: Use only machine settings" policy.
  
  **Default**: Disabled  
  
- **Internet Explorer internet zone script initiated windows**  
  This policy setting allows you to manage restrictions on script-initiated pop-up windows and windows that include the title and status bars. If you enable this policy setting, Windows Restrictions security won't apply in this zone. The security zone runs without the added layer of security provided by this feature. If you disable this policy setting, the possible harmful actions contained in script-initiated pop-up windows and windows that include the title and status bars can't run. This Internet Explorer security feature is on in this zone as dictated by the Scripted Windows Security Restrictions feature control setting for the process. If you don't configure this policy setting, the possible harmful actions contained in script-initiated pop-up windows and windows that include the title and status bars can't run. This Internet Explorer security feature is on in this zone as dictated by the Scripted Windows Security Restrictions feature control setting for the process.
  
  **Default**: Disabled  
  
- **Internet Explorer security zones use only machine settings**  
  Applies security zone information to all users of the same computer. A security zone is a group of Web sites with the same security level. If you enable this policy, changes that the user makes to a security zone will apply to all users of that computer. If you disable this policy or don't configure it, users of the same computer can establish their own security zone settings. Use this policy to ensure that security zone settings apply uniformly to the same computer and don't vary from user to user. Also, see the "Security zones: don't allow users to change policies" policy.
  
  **Default**: Enabled  
  
- **Internet Explorer locked down local machine zone java permissions**  
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, Java applets are disabled
  
  **Default**: Disable java 
  
- **Internet Explorer restricted zone do not run antimalware against Active X controls**   
  This policy setting determines whether Internet Explorer runs antimalware programs against ActiveX controls, to check if they're safe to load on pages. If you enable this policy setting, Internet Explorer won't check with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you disable this policy setting, Internet Explorer always checks with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you don't configure this policy setting, Internet Explorer always checks with your antimalware program to see if it's safe to create an instance of the ActiveX control. Users can turn this behavior on or off, using Internet Explorer Security settings.
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone run .NET Framework reliant components signed with authenticode**  
  This policy setting allows you to manage whether .NET Framework components that are signed with Authenticode can be executed from Internet Explorer. These components include managed controls referenced from an object tag and managed executables referenced from a link. If you enable this policy setting, Internet Explorer will execute signed managed components. If you select Prompt in the drop-down box, Internet Explorer will prompt the user to determine whether to execute signed managed components. If you disable this policy setting, Internet Explorer won't execute signed managed components. If you don't configure this policy setting, Internet Explorer won't execute signed managed components.
  
  **Default**: Disable  
  
- **Internet Explorer restricted zone access to data sources**  
  This policy setting allows you to manage whether Internet Explorer can access data from another security zone using the Microsoft XML Parser (MSXML) or ActiveX Data Objects (ADO). If you enable this policy setting, users can load a page in the zone that uses MSXML or ADO to access data from another site in the zone. If you select Prompt in the drop-down box, users are queried to choose whether to allow a page to load in the zone that uses MSXML or ADO to access data from another site in the zone. If you disable this policy setting, users can't load a page in the zone that uses MSXML or ADO to access data from another site in the zone. If you don't configure this policy setting, users can't load a page in the zone that uses MSXML or ADO to access data from another site in the zone.
  
  **Default**: Disable 
  
- **Internet Explorer internet zone don't run antimalware against ActiveX controls**   
  This policy setting determines whether Internet Explorer runs antimalware programs against ActiveX controls, to check if they're safe to load on pages. If you enable this policy setting, Internet Explorer won't check with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you disable this policy setting, Internet Explorer always checks with your antimalware program to see if it's safe to create an instance of the ActiveX control. If you don't configure this policy setting, Internet Explorer always checks with your antimalware program to see if it's safe to create an instance of the ActiveX control. Users can turn this behavior on or off, using Internet Explorer Security settings.
  
  **Default**: Disabled  
  
- **Internet Explorer internet zone copy and paste via script**  
  This policy setting allows you to manage whether scripts can perform a clipboard operation (for example, cut, copy, and paste) in a specified region. If you enable this policy setting, a script can perform a clipboard operation. If you select Prompt in the drop-down box, users are queried as to whether to perform clipboard operations. If you disable this policy setting, a script can't perform a clipboard operation. If you don't configure this policy setting, a script can perform a clipboard operation.
  
  **Default**: Disable  
  
- **Internet Explorer use Active X installer service**   
  This policy setting allows you to specify how ActiveX controls are installed. If you enable this policy setting, ActiveX controls are installed only if the ActiveX Installer Service is present and has been configured to allow the installation of ActiveX controls. If you disable or don't configure this policy setting, ActiveX controls, including per-user controls, are installed through the standard installation process.
  
  **Default**: Enabled  
  
- **Internet Explorer processes protection from zone elevation**  
  Internet Explorer places restrictions on each Web page it opens. The restrictions are dependent upon the location of the Web page (Internet, Intranet, Local Machine zone, and so on). For example, Web pages on the local computer have the fewest security restrictions and are in the Local Machine zone, making the Local Machine security zone a prime target for malicious users. If you enable this policy setting, any zone can be protected from zone elevation for all processes. If you disable or don't configure this policy setting, processes other than Internet Explorer or those listed in the Process List receive no such protection.
  
  **Default**: Enabled  
  
- **Internet Explorer internet zone download unsigned ActiveX controls**   
  This policy setting allows you to manage whether users may download unsigned ActiveX controls from the zone. Such code is potentially harmful, especially when coming from an untrusted zone. If you enable this policy setting, users can run unsigned controls without user intervention. If you select Prompt in the drop-down box, users are queried to choose whether to allow the unsigned control to run. If you disable this policy setting, users can't run unsigned controls. If you don't configure this policy setting, users can't run unsigned controls.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone navigate windows and frames across different domains**   
  This policy setting allows you to manage the opening of windows and frames and access of applications across different domains. If you enable this policy setting, users can open windows and frames from other domains and access applications from other domains. If you select Prompt in the drop-down box, users are queried whether to allow windows and frames to access applications from other domains. If you disable this policy setting, users can't open windows and frames to access applications from different domains. If you don't configure this policy setting, users can open windows and frames from other domains and access applications from other domains.
  
  **Default**: Disable  
  
- **Internet Explorer internet zone updates to status bar via script**  
  This policy setting allows you to manage whether a script can update the status bar within the zone. If you enable this policy setting, scripts can update the status bar. If you disable or don't configure this policy setting, script isn't allowed to update the status bar.
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone include local path when uploading files to server**  
  This policy setting controls if local path information is sent when the user is uploading a file via an HTML form. If the local path information is sent, some information may be unintentionally revealed to the server. For instance, files sent from the user's desktop may contain the user name as a part of the path. If you enable this policy setting, path information is sent when the user is uploading a file via an HTML form. If you disable this policy setting, path information is removed when the user is uploading a file via an HTML form. If you don't configure this policy setting, the user can choose whether path information is sent when they are uploading a file via an HTML form. By default, path information is sent.
  
  **Default**: Disabled  
  
- **Internet Explorer processes restrict file download**   
  This policy setting enables applications hosting the Web Browser Control to block automatic prompting of file downloads that aren't user initiated. If you enable this policy setting, the Web Browser Control will block automatic prompting of file downloads that aren't user initiated for all processes. If you disable this policy setting, the Web Browser Control won't block automatic prompting of file downloads that aren't user initiated for all processes.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone allow only approved domains to use Active X controls**   
  This policy setting controls if the user is prompted to allow ActiveX controls to run on websites other than the website that installed the ActiveX control. If you enable this policy setting, the user is prompted before ActiveX controls can run from websites in this zone. The user can choose to allow the control to run from the current site or from all sites. If you disable this policy setting, the user doesn't see the per-site ActiveX prompt, and ActiveX controls can run from all sites in this zone.
  
  **Default**: Enabled  
  
- **Internet Explorer restricted zone initialize and script Active X controls not marked as safe**  
  This policy setting allows you to manage ActiveX controls not marked as safe. If you enable this policy setting, ActiveX controls run, loaded with parameters, and scripted without setting object safety for untrusted data or scripts. This setting isn't recommended, except for secure and administered zones. This setting causes both unsafe and safe controls to be initialized and scripted, ignoring the Script ActiveX controls marked safe for scripting option. If you enable this policy setting and select Prompt in the drop-down box, users are queried whether to allow the control to load with parameters or scripted. If you disable this policy setting, ActiveX controls that can't be made safe aren't loaded with parameters or scripted. If you don't configure this policy setting, ActiveX controls that can't be made safe aren't loaded with parameters or scripted.
  
  **Default**: Disable  
  
- **Internet Explorer users changing policies**  
    Prevents users from changing security zone settings. A security zone is a group of Web sites with the same security level. If you enable this policy, the Custom Level button and security-level slider on the Security tab in the Internet Options dialog box are disabled. If you disable this policy or don't configure it, users can change the settings for security zones. This policy prevents users from changing security zone settings established by the administrator. Note: The "Disable the Security page" policy (located in \User Configuration\Administrative Templates\Windows Components\Internet Explorer\Internet Control Panel), which removes the Security tab from Internet Explorer in Control Panel, takes precedence over this policy. If it's enabled, this policy is ignored. Also, see the "Security zones: Use only machine settings" policy.
    
  **Default**: Disabled  
  
- **Internet Explorer restricted zone protected mode**  
  This policy setting allows you to turn on Protected Mode. Protected Mode helps protect Internet Explorer from exploited vulnerabilities by reducing the locations that Internet Explorer can write to in the registry and the file system. If you enable this policy setting, Protected Mode is turned on. The user can't turn off Protected Mode. If you disable this policy setting, Protected Mode is turned off. The user can't turn on Protected Mode. If you don't configure this policy setting, the user can turn on or turn off Protected Mode.
  
  **Default**: Enable  
  
- **Internet Explorer internet zone user data persistence**  
  This policy setting allows you to manage the preservation of information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk. When a user returns to a persisted page, the state of the page can be restored if this policy setting is appropriately configured. If you enable this policy setting, users can preserve information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk. If you disable this policy setting, users can't preserve information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk. If you don't configure this policy setting, users can preserve information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk.
  
  **Default**: Disabled  
  
- **Internet Explorer internet zone scripting of web browser controls**  
 
  This policy setting determines whether a page can control embedded WebBrowser controls via script. If you enable this policy setting, script access to the WebBrowser control is allowed. If you disable this policy setting, script access to the WebBrowser control isn't allowed. If you don't configure this policy setting, the user can enable or disable script access to the WebBrowser control. By default, script access to the WebBrowser control is allowed only in the Local Machine and Intranet zones.
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone user data persistence**  
    This policy setting allows you to manage the preservation of information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk. When a user returns to a persisted page, the state of the page can be restored if this policy setting is appropriately configured. If you enable this policy setting, users can preserve information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk. If you disable this policy setting, users can't preserve information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk. If you don't configure this policy setting, users can't preserve information in the browser's history, in favorites, in an XML store, or directly within a Web page saved to disk.  
  
  **Default**: Disabled  
  
- **Internet Explorer locked down intranet zone java permissions**  
  This policy setting allows you to manage permissions for Java applets. If you enable this policy setting, you can choose options from the drop-down box. Custom, to control permissions settings individually. Low Safety enables applets to perform all operations. Medium Safety enables applets to run in their sandbox (an area in memory outside of which the program can't make calls), plus capabilities like scratch space (a safe and secure storage area on the client computer) and user-controlled file I/O. High Safety enables applets to run in their sandbox. Disable Java to prevent any applets from running. If you disable this policy setting, Java applets can't run. If you don't configure this policy setting, Java applets are disabled.
  
  **Default**: Disable java  
  
- **Internet Explorer enhanced protected mode**  
  Enhanced Protected Mode provides additional protection against malicious websites by using 64-bit processes on 64-bit versions of Windows. For computers running at least Windows 8, Enhanced Protected Mode also limits the locations Internet Explorer can read from in the registry and the file system. If you enable this policy setting, Enhanced Protected Mode is turned on. Any zone that has Protected Mode enabled will use Enhanced Protected Mode. Users won't be able to disable Enhanced Protected Mode. If you disable this policy setting, Enhanced Protected Mode is turned off. Any zone that has Protected Mode enabled will use the version of Protected Mode introduced in Internet Explorer 7 for Windows Vista. If you don't configure this policy, users can turn on or turn off Enhanced Protected Mode on the Advanced tab of the Internet Options dialog.
  
  **Default**: Enabled  
  
- **Internet Explorer bypass smart screen warnings**  
  This policy setting determines whether the user can bypass warnings from SmartScreen Filter. SmartScreen Filter warns the user about executable files that Internet Explorer users don't commonly download from the Internet. If you enable this policy setting, SmartScreen Filter warnings block the user. If you disable or don't configure this policy setting, the user can bypass SmartScreen Filter warnings.
  
  **Default**: Disabled  
  
- **Internet Explorer restricted zone meta refresh**  
  This policy setting allows you to manage whether a user's browser can be redirected to another Web page if the author of the Web page uses the Meta Refresh setting (tag) to redirect browsers to another Web page. If you enable this policy setting, a user's browser that loads a page containing an active Meta Refresh setting can be redirected to another Web page. If you disable this policy setting, a user's browser that loads a page containing an active Meta Refresh setting can't be redirected to another Web page. If you don't configure this policy setting, a user's browser that loads a page containing an active Meta Refresh setting can't be redirected to another Web page.
  
  **Default**: Disabled  
  
## Local Policies Security Options
For more information, see [Policy CSP - LocalPoliciesSecurityOptions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions) in the Windows documentation. 

- **Restrict anonymous access to named pipes and shares**  
  When enabled, this security setting restricts anonymous access to shares and pipes to the settings for: (1) Named pipes that can be accessed anonymously (2) Shares that can be accessed anonymously
  
  **Default**: Yes  
  
- **Minimum session security for NTLM SSP based servers**  
  This security setting allows a server to require the negotiation of 128-bit encryption and/or NTLMv2 session security. These values are dependent on the LAN Manager Authentication Level security setting value. The options are: Require NTLMv2 session security: The connection will fail if message integrity isn't negotiated. Require 128-bit encryption. The connection will fail if strong encryption (128-bit) isn't negotiated.
  
  **Default**: Require NTLM V2 and 128 bit encryption  
  
- **Minutes of lock screen inactivity until screen saver activates**  
  Windows notices inactivity of a logon session, and if the amount of inactive time exceeds the inactivity limit, then the screen saver will run, locking the session.
  
  **Default**: 15
  
- **Require client to always digitally sign communications** 
  This security setting determines whether all secure channel traffic initiated by the domain member must be signed or encrypted. When a computer joins a domain, a computer account is created. After that, when the system starts, it uses the computer account password to create a secure channel with a domain controller for its domain. This secure channel is used to perform operations such as NTLM pass through authentication, LSA SID/name Lookup and more. This setting determines if all secure channel traffic initiated by the domain member meets minimum security requirements. Specifically it determines whether all secure channel traffic started by the domain member must be signed or encrypted. If this policy is enabled, then the secure channel won't be established unless either signing or encryption of all secure channel traffic is negotiated. If this policy is disabled, then encryption and signing of all secure channel traffic is negotiated with the Domain Controller in which case the level of signing and encryption depends on the version of the Domain Controller and the settings of the following two policies: Domain member: Digitally encrypt secure channel data (when possible) Domain member: Digitally sign secure channel data (when possible)
  
  **Default**: Yes
  
- **Authentication level**  
  This security setting determines which challenge/response authentication protocol is used for network logons. This choice affects the level of authentication protocol used by clients, the level of session security negotiated, and the level of authentication accepted by servers as follows:  
  - *Send LM and NTLM responses*: Clients use LM and NTLM authentication and never use NTLMv2 session security; domain controllers accept LM, NTLM, and NTLMv2 authentication. 
  - *Send LM and NTLM - NTLMv2 if negotiated*: Clients use LM and NTLM authentication and use NTLMv2 session security if the server supports it; domain controllers accept LM, NTLM, and NTLMv2 authentication. 
  - *Send NTLM response only*: Clients use NTLM authentication only and use NTLMv2 session security if the server supports it; domain controllers accept LM, NTLM, and NTLMv2 authentication. 
  - *Send NTLMv2 response only*: Clients use NTLMv2 authentication only and use NTLMv2 session security if the server supports it; domain controllers accept LM, NTLM, and NTLMv2 authentication. 
  - *Send NTLMv2 response only. Refuse LM*: Clients use NTLMv2 authentication only and use NTLMv2 session security if the server supports it; domain controllers refuse LM (accept only NTLM and NTLMv2 authentication). 
  - *Send NTLMv2 response only. Refuse LM and NTLM*: Clients use NTLMv2 authentication only and use NTLMv2 session security if the server supports it; domain controllers refuse LM and NTLM (accept only NTLMv2 authentication). 
    
  **Default**: Send NTLMv2 response only. Refuse LM and NTLM
  
- **Prevent clients from sending unencrypted passwords to third party SMB servers**  
  If this security setting is enabled, the Server Message Block (SMB) redirector can send plaintext passwords to non-Microsoft SMB servers that don't support password encryption during authentication. Sending unencrypted passwords is a security risk.
  
  **Default**: Yes
  
- **Disable server digitally signing communications always**  
  This security setting determines whether the SMB client attempts to negotiate SMB packet signing. The server message block (SMB) protocol provides the basis for Microsoft file and print sharing and many other networking operations, such as remote Windows administration. To prevent man-in-the-middle attacks that modify SMB packets in transit, the SMB protocol supports the digital signing of SMB packets. This policy setting determines whether the SMB client component attempts to negotiate SMB packet signing when it connects to an SMB server. If this setting is enabled, the Microsoft network client will ask the server to perform SMB packet signing upon session setup. If packet signing has been enabled on the server, packet signing is negotiated. If this policy is disabled, the SMB client will never negotiate SMB packet signing.
  
  **Default**: Yes
  
- **Administrator elevation prompt behavior**  
  This policy setting controls the behavior of the elevation prompt for administrators. The options are: 
    - *Elevate without prompting*: Allows privileged accounts to perform an operation that requires elevation without requiring consent or credentials. Note: Use this option only in the most constrained environments. 
    - *Prompt for credentials on the secure desktop*: When an operation requires elevation of privilege, the user is prompted on the secure desktop to enter a privileged user name and password. If the user enters valid credentials, the operation continues with the user's highest available privilege. 
    - *Prompt for consent on the secure desktop*: When an operation requires elevation of privilege, the user is prompted on the secure desktop to select either Permit or Deny. If the user selects Permit, the operation continues with the user's highest available privilege. 
    - *Prompt for credentials*: When an operation requires elevation of privilege, the user is prompted to enter an administrative user name and password. If the user enters valid credentials, the operation continues with the applicable privilege. 
    - *Prompt for consent*: When an operation requires elevation of privilege, the user is prompted to select either Permit or Deny. If the user selects Permit, the operation continues with the user's highest available privilege.  
    - *Prompt for consent for non-Windows binaries*: When an operation for a non-Microsoft application requires elevation of privilege, the user is prompted on the secure desktop to select either Permit or Deny. If the user selects Permit, the operation continues with the user's highest available privilege.   
  
  **Default**: Prompt for consent on the secure desktop
  
- **Minimum session security for NTLM SSP based clients**  
  This security setting allows a client to require the negotiation of 128-bit encryption and/or NTLMv2 session security. These values are dependent on the LAN Manager Authentication Level security setting value. The options are:
  - Require NTLMv2 session security: The connection will fail if NTLMv2 protocol isn't negotiated. 
  - *Require 128-bit encryption*: The connection will fail if strong encryption (128-bit) isn't negotiated.
  - *Require NTLMv2 and 128-bit encryption*. 

  **Default**: Require NTLM V2 128 encryption
  
- **Smart card removal behavior**  
    This security setting determines what happens when the smart card for a logged-on user is removed from the smart card reader. The options are:
     - *No action*. 
     - *Lock Workstation* - The workstation is locked when the smart card is removed, allowing users to leave the area, take their smart card with them, and still maintain a protected session.
     - *Force Logoff* - the user is automatically logged off when the smart card is removed.
     - *Disconnect Remote Desktop session* - Removal of the smart card disconnects the session without logging the user off. This allows the user to insert the smart card and resume the session later, or at another smart card reader-equipped computer, without having to log on again. If the session is local, this policy functions identically to Lock Workstation.   
    
  **Default**: Lock workstation
  
- **Block anonymous enumeration of SAM accounts and shares**  
  This security setting determines whether to allow anonymous enumeration of SAM accounts and shares. Windows allows anonymous users to perform certain activities, such as enumerating the names of domain accounts and network shares. This is convenient, for example, when an administrator wants to grant access to users in a trusted domain that doesn't maintain a reciprocal trust. If you don't want to allow anonymous enumeration of SAM accounts and shares, then set this policy to *Yes*.
  
  **Default**: Yes
  
- **Block remote logon with blank password**  
  This security setting determines whether local accounts that aren't password protected can be used to log on from locations other than the physical computer console. If enabled, local accounts that aren't password protected must use the computer's keyboard to log on. 

  *Warning*: Computers that aren't in physically secure locations should always enforce strong password policies for all local user accounts. Otherwise, anyone with physical access to the computer can log on by using a user account that doesn't have a password. This is especially important for portable computers. 

  If you apply this security policy to the Everyone group, no one can log on through Remote Desktop Services. This setting doesn't affect logons that use domain accounts. It's possible for applications that use remote interactive logons to bypass this setting.
  
  **Default**: Yes
  
- **Standard user elevation prompt behavior**  
  This policy setting controls the behavior of the elevation prompt for standard users. 
  - *Automatically deny elevation requests*: When an operation requires elevation of privilege, a configurable access denied error message is displayed. An enterprise that is running desktops as standard user may choose this setting to reduce help desk calls. 
  - *Prompt for credentials on the secure desktop*: When an operation requires elevation of privilege, the user is prompted on the secure desktop to enter a different user name and password. If the user enters valid credentials, the operation continues with the applicable privilege. 
  - *Prompt for credentials*: When an operation requires elevation of privilege, the user is prompted to enter an administrative user name and password. If the user enters valid credentials, the operation continues with the applicable privilege.  
  
  **Default**: Automatically deny elevation requests
  
- **Require admin approval mode for administrators**  
  This policy setting controls the behavior of all User Account Control (UAC) policy settings for the computer. If you change this policy setting, you must restart your computer. The options are:   
  - *Not configured*: Admin Approval Mode and all related UAC policy settings are disabled. Note: If this policy setting is disabled, the Security Center notifies you that the overall security of the operating system has been reduced. 
  - *Yes*: Admin Approval Mode is enabled. This policy must be enabled and related UAC policy settings must be set appropriately to allow the built-in Administrator account and all other users who are members of the Administrators group to run in Admin Approval Mode.  
  
  **Default**: Yes
  
- **Prevent anonymous enumeration of SAM accounts**  
  This security setting determines what additional permissions are granted for anonymous connections to the computer. Windows allows anonymous users to perform certain activities, such as enumerating the names of domain accounts and network shares. This is convenient, for example, when an administrator wants to grant access to users in a trusted domain that doesn't maintain a reciprocal trust. This security option allows additional restrictions to be placed on anonymous connections as follows: 
  - *Yes*: Don't allow enumeration of SAM accounts. This option replaces Everyone with Authenticated Users in the security permissions for resources.
  - *Not configured*: No additional restrictions. Rely on default permissions.  
  
  **Default**: Yes
  
- **Allow remote calls to security accounts manager**  
  This policy setting allows you to restrict remote rpc connections to SAM. If not selected, the default security descriptor is used.
  
  **Default**: *O:BAG:BAD:(A;;RC;;;BA)*

- **Use admin approval mode**  
  This policy setting controls the behavior of Admin Approval Mode for the built-in Administrator account. The options are: 
  - *Yes*: The built-in Administrator account uses Admin Approval Mode. By default, any operation that requires elevation of privilege will prompt the user to approve the operation. 
  - *Not Configured*: The built-in Administrator account runs all applications with full administrative privilege.  

  **Default**: Yes
  
- **Allow UI access applications for secure locations**  
  This policy setting controls whether User Interface Accessibility (UIAccess or UIA) programs can automatically disable the secure desktop for elevation prompts used by a standard user. 
  - *Yes*: UIA programs, including Windows Remote Assistance, automatically disable the secure desktop for elevation prompts. If you don't disable the "User Account Control: Switch to the secure desktop when prompting for elevation" policy setting, the prompts appear on the interactive user's desktop instead of the secure desktop. 
  - *Not Configured*: The secure desktop can be disabled only by the user of the interactive desktop or by disabling the "User Account Control: Switch to the secure desktop when prompting for elevation" policy setting.  

  **Default**: Yes

- **Detect application installations and prompt for elevation**  
  This policy setting controls the behavior of application installation detection for the computer. The options are: 
  - *Enabled*: When an application installation package is detected that requires elevation of privilege, the user is prompted to enter an administrative user name and password. If the user enters valid credentials, the operation continues with the applicable privilege. 
  - *Disabled*: Application installation packages aren't detected and prompted for elevation. Enterprises that are running standard user desktops and use delegated installation technologies such as Group Policy Software Installation or Systems Management Server (SMS) should disable this policy setting. In this case, installer detection is unnecessary.  
  
  **Default**: Yes
  
- **Prevent storing LAN manager hash value on next password change**  
  This security setting determines if, at the next password change, the LAN Manager (LM) hash value for the new password is stored. The LM hash is relatively weak and prone to attack, as compared with the cryptographically stronger Windows NT hash. Since the LM hash is stored on the local computer in the security database the passwords can be compromised if the security database is attacked.
  
  **Default**: Yes

- **Virtualize file and registry write failures to per user locations**  
  This policy setting controls whether application write failures are redirected to defined registry and file system locations. This policy setting mitigates applications that run as administrator and write run-time application data to *%ProgramFiles%*, *%Windir%*, *%Windir%\system32*, or *HKLM\Software*.
  
  **Default**: Yes

## MS Security Guide  
For more information, see [Policy CSP - MSSecurityGuide](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mssecurityguide) in the Windows documentation.  

- **Apply UAC restrictions to local accounts on network logon**  
  **Default**: Enabled
  
- **SMB v1 client driver start configuration**  
  **Default**: Disabled driver
  
- **SMB v1 server**  
  **Default**: Disabled
  
- **Digest authentication**  
  **Default**: Disabled
  
- **Structured exception handling overwrite protection**  
  **Default**: Enabled
  
## MSS Legacy  
For more information, see [Policy CSP - MSSLegacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-msslegacy) in the Windows documentation.  

- **Network IP source routing protection level**  
  **Default**: Highest protection  
  
- **Network ignore NetBIOS name release requests except from WINS servers**  
  **Default**: Enabled
  
- **Network IPv6 source routing protection level**  
  **Default**: Highest protection

- **Network ICMP redirects override OSPF generated**  
  **Default**: Disabled
  
## Power  
For more information, see [Policy CSP - Power](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power) in the Windows documentation.  

- **Require password on wake while plugged in**  
  This policy setting specifies if the user is prompted for a password when the system resumes from sleep. If you enable or don't configure this policy setting, the user is prompted for a password when the system resumes from sleep. If you disable this policy setting, the user isn't prompted for a password when the system resumes from sleep.
  
  **Default**: Enabled
  
- **Standby states when sleeping while on battery**  
  This policy setting manages if Windows can use standby states when putting the computer in a sleep state. If you enable or don't configure this policy setting, Windows uses standby states to put the computer in a sleep state. If you disable this policy setting, standby states (S1-S3) aren't allowed.
  
  **Default**: Disabled
  
- **Standby states when sleeping while plugged in**  
  This policy setting manages if Windows can use standby states when putting the computer in a sleep state. If you enable or don't configure this policy setting, Windows uses standby states to put the computer in a sleep state. If you disable this policy setting, standby states (S1-S3) aren't allowed.
  
  **Default**: Disabled
  
- **Require password on wake while on battery**  
  This policy setting specifies if the user is prompted for a password when the system resumes from sleep. If you enable or don't configure this policy setting, the user is prompted for a password when the system resumes from sleep. If you disable this policy setting, the user isn't prompted for a password when the system resumes from sleep.
  
  **Default**: Enabled
  
## Remote Desktop Services  
For more information, see [Policy CSP - RemoteDesktopServices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotedesktopservices) in the Windows documentation.  

- **Block password saving**  
  Controls whether passwords can be saved on this computer from Remote Desktop Connection. If you enable this setting the password saving checkbox in Remote Desktop Connection is disabled and users won't be able to save passwords. When a user opens an RDP file using Remote Desktop Connection and saves their settings, any password that previously existed in the RDP file are deleted. If you disable this setting or leave it not configured, the user can save passwords using Remote Desktop Connection.
  
   **Default**: Enabled
  
- **Secure RPC communication**  
  Specifies whether a Remote Desktop Session Host server requires secure RPC communication with all clients or allows unsecured communication. You can use this setting to strengthen the security of RPC communication with clients by allowing only authenticated and encrypted requests. If the status is set to Enabled, Remote Desktop Services accepts requests from RPC clients that support secure requests, and doesn't allow unsecured communication with untrusted clients. If the status is set to Disabled, Remote Desktop Services always requests security for all RPC traffic. However, unsecured communication is allowed for RPC clients that don't respond to the request. If the status is set to Not Configured, unsecured communication is allowed. Note: The RPC interface is used for administering and configuring Remote Desktop Services.
  
  **Default**: Enabled
  
- **Block drive redirection**  
  This policy setting specifies whether to prevent the mapping of client drives in a Remote Desktop Services session (drive redirection). By default, an RD Session Host server maps client drives automatically upon connection. Mapped drives appear in the session folder tree in File Explorer or Computer in the format *\<driveletter>* on *\<computername>*. You can use this policy setting to override this behavior. If you enable this policy setting, client drive redirection isn't allowed in Remote Desktop Services sessions, and Clipboard file copy redirection isn't allowed on computers running Windows Server 2003, Windows 8, and Windows XP. If you disable this policy setting, client drive redirection is always allowed. Also, Clipboard file copy redirection is always allowed if Clipboard redirection is allowed. If you don't configure this policy setting, client drive redirection and Clipboard file copy redirection aren't specified at the Group Policy level.
  
  **Default**: Enabled
  
- **Prompt for password upon connection**  
  This policy setting specifies whether Remote Desktop Services always prompts the client for a password upon connection. You can use this setting to enforce a password prompt for users logging on to Remote Desktop Services, even if they already provided the password in the Remote Desktop Connection client. By default, Remote Desktop Services allows users to automatically log on by entering a password in the Remote Desktop Connection client. If you enable this policy setting, users can't automatically log on to Remote Desktop Services by supplying their passwords in the Remote Desktop Connection client. they're prompted for a password to log on. If you disable this policy setting, users can always log on to Remote Desktop Services automatically by supplying their passwords in the Remote Desktop Connection client. If you don't configure this policy setting, automatic logon isn't specified at the Group Policy level. 
  
  **Default**: Enabled
  
- **Remote desktop services client connection encryption level**  
  Specifies whether to require the use of a specific encryption level to secure communications between client computers and RD Session Host servers during Remote Desktop Protocol (RDP) connections. This policy only applies when you're using native RDP encryption. However, native RDP encryption (as opposed to SSL encryption) isn't recommended. This policy doesn't apply to SSL encryption. If you enable this policy setting, all communications between clients and RD Session Host servers during remote connections must use the encryption method specified in this setting. By default, the encryption level is set to High. The following encryption methods are available:  
  - *High*: The High setting encrypts data sent from the client to the server and from the server to the client by using strong 128-bit encryption. Use this encryption level in environments that contain only 128-bit clients (for example, clients that run Remote Desktop Connection). Clients that don't support this encryption level can't connect to RD Session Host servers.  
  - *Client Compatible*: The Client Compatible setting encrypts data sent between the client and the server at the maximum key strength supported by the client. Use this encryption level in environments that include clients that don't support 128-bit encryption.  
  - *Low*: The Low setting encrypts only data sent from the client to the server by using 56-bit encryption.  
  
  If you disable or don't configure this setting, the encryption level to be used for remote connections to RD Session Host servers isn't enforced through Group Policy. Important FIPS compliance can be configured through the System cryptography. Use FIPS-compliant algorithms for encryption, hashing, and signing settings in Group Policy (under Computer Configuration\Windows Settings\Security Settings\Local Policies\Security Options.) The FIPS-compliant setting encrypts and decrypts data sent from the client to the server and from the server to the client, with the Federal Information Processing Standard (FIPS) 140 encryption algorithms, by using Microsoft cryptographic modules. Use this encryption level when communications between clients and RD Session Host servers requires the highest level of encryption.
  
  **Default**: High
  
## Remote Management  
For more information, see [Policy CSP - RemoteManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotemanagement) in the Windows documentation.  

- **Block storing run as credentials**  
  Client basic authentication
  
  **Default**: Enabled
  
- **Basic authentication**  
  This policy setting allows you to manage whether the Windows Remote Management (WinRM) service accepts Basic authentication from a remote client. If you enable this policy setting, the WinRM service accepts Basic authentication from a remote client. If you disable or don't configure this policy setting, the WinRM service doesn't accept Basic authentication from a remote client.
  
  **Default**: Disabled
  
- **Block client digest authentication**  
  This policy setting allows you to manage whether the Windows Remote Management (WinRM) client uses Digest authentication. If you enable this policy setting, the WinRM client doesn't use Digest authentication. If you disable or don't configure this policy setting, the WinRM client uses Digest authentication.
  
  **Default**: Enabled
  
- **Unencrypted traffic**  
  This policy setting allows you to manage whether the Windows Remote Management (WinRM) service sends and receives unencrypted messages over the network. If you enable this policy setting, the WinRM client sends and receives unencrypted messages over the network. If you disable or don't configure this policy setting, the WinRM client sends or receives only encrypted messages over the network.  
  
  **Default**: Disabled
  
- **Client unencrypted traffic**  
  This policy setting allows you to manage whether the Windows Remote Management (WinRM) client sends and receives unencrypted messages over the network. If you enable this policy setting, the WinRM client sends and receives unencrypted messages over the network. If you disable or don't configure this policy setting, the WinRM client sends or receives only encrypted messages over the network.
  
  **Default**: Disabled
  
- **Client basic authentication**  
  This policy setting allows you to manage whether the Windows Remote Management (WinRM) client uses Basic authentication. If you enable this policy setting, the WinRM client uses Basic authentication. If WinRM is configured to use HTTP transport, the user name and password are sent over the network as clear text. If you disable or don't configure this policy setting, the WinRM client doesn't use Basic authentication.
  
  **Default**: Disabled
  

## Remote Procedure Call  
For more information, see [Policy CSP - RemoteProcedureCall](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remoteprocedurecall) in the Windows documentation.  

- **RPC unauthenticated client options**  
  This policy setting controls how the RPC server runtime handles unauthenticated RPC clients connecting to RPC servers. This policy setting impacts all RPC applications. In a domain environment, use this policy setting with caution as it can impact a wide range of functionality including group policy processing itself. Reverting a change to this policy setting can require manual intervention on each affected machine. This policy setting should never be applied to a domain controller. If you disable this policy setting, the RPC server runtime uses the value of "Authenticated" on Windows Client, and the value of "None" on Windows Server versions that support this policy setting. If you don't configure this policy setting, it remains disabled. The RPC server runtime behaves as though it was enabled with the value of "Authenticated" used for Windows Client and the value of "None" used for Server SKUs that support this policy setting. If you enable this policy setting, it directs the RPC server runtime to restrict unauthenticated RPC clients connecting to RPC servers running on a machine. A client is considered an authenticated client if it uses a named pipe to communicate with the server or if it uses RPC Security. RPC Interfaces that have specifically requested to be accessible by unauthenticated clients may be exempt from this restriction, depending on the selected value for this policy setting.  
  - *None* allows all RPC clients to connect to RPC Servers running on the machine on which the policy setting is applied. 
  - *Authenticated* allows only authenticated RPC Clients (per the definition above) to connect to RPC Servers running on the machine on which the policy setting is applied. Exemptions are granted to interfaces that have requested them. 
  - *Authenticated without exceptions* allows only authenticated RPC Clients (per the definition above) to connect to RPC Servers running on the machine on which the policy setting is applied. No exceptions are allowed. Note: This policy setting won't be applied until the system is rebooted.  

  **Default**: Authenticated

## Search 
For more information, see [Policy CSP - Search](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-search) in the Windows documentation.  

- **Disable indexing encrypted items**  
  Allows or disallows the indexing of items. This switch is for the Windows Search Indexer, which controls whether it will index items that are encrypted, such as the Windows Information Protection (WIP) protected files. When the policy is enabled, WIP protected items are indexed and the metadata about them are stored in an unencrypted location. The metadata includes things like file path and date modified. When the policy is disabled, the WIP protected items aren't indexed and don't show up in the results in Cortana or file explorer. There may also be a performance impact on photos and Groove apps if there are many WIP protected media files on the device.
  
**Default**: Yes
  
## Smart Screen  
For more information, see [Policy CSP - SmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-smartscreen) in the Windows documentation.  

- **Block execution of unverified files**  
  Block user from running unverified files. 
  - *Not Configured* - Employees can ignore SmartScreen warnings and run malicious files. 
  - *Yes* – Employees can't ignore SmartScreen warnings and run malicious files.

  **Default**: Yes

- **Require SmartScreen for apps and files**  
  Allows IT Admins to configure SmartScreen for Windows.

  **Default**: Yes
  
## System  
For more information, see [Policy CSP - System](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system) in the Windows documentation.  

- **System boot start driver initialization**  
  This policy setting allows you to specify which boot-start drivers are initialized based on a classification determined by an Early Launch Antimalware boot-start driver. The Early Launch Antimalware boot-start driver can return the following classifications for each boot-start driver: 
  - *Good*: The driver has been signed and hasn't been tampered with.  
  - *Bad* - The driver has been identified as malware. We recommend that you don't allow known bad drivers to be initialized. 
  - *Bad, but required for boot*: The driver has been identified as malware, but the computer can't successfully boot without loading this driver. 
  - *Unknown* - This driver hasn't been attested to by your malware detection application and hasn't been classified by the Early Launch Antimalware boot-start driver.  

  If you enable this policy setting, you can choose which boot-start drivers to initialize the next time the computer is started. If you disable or don't configure this policy setting, the boot start drivers determined to be Good, Unknown, or Bad but Boot Critical are initialized and the initialization of drivers determined to be Bad is skipped. If your malware detection application doesn't include an Early Launch Antimalware boot-start driver or if your Early Launch Antimalware boot-start driver has been disabled, this setting has no effect and all boot-start drivers are initialized.  
  
  **Default**: Good unknown and bad critical


## Wi-Fi  
For more information, see [Policy CSP - Wifi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi) in the Windows documentation.  

- **Block Internet sharing**  
  Specifies whether internet sharing is possible on the device.  

  **Default**: Yes  

- **Block Automatically connecting to Wi-Fi hotspots**  
  Allow or disallow the device to automatically connect to Wi-Fi hotspots.  

  **Default**: Yes  
  
## Windows Connection Manager  
For more information, see [Policy CSP - WindowsConnectionManager](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsconnectionmanager) in the Windows documentation.  

- **Block connection to non-domain networks**  
  This policy setting prevents computers from connecting to both a domain-based network and a non-domain based network at the same time. If this policy setting is enabled, the computer responds to automatic and manual network connection attempts based on the following circumstances: 
  - Automatic connection attempts When the computer is already connected to a domain-based network, all automatic connection attempts to non-domain networks are blocked. When the computer is already connected to a non-domain based network, automatic connection attempts to domain-based networks are blocked. 
  - Manual connection attempts When the computer is already connected to either a non-domain based network or a domain-based network over media other than Ethernet, and a user attempts to create a manual connection to an additional network in violation of this policy setting, the existing network connection disconnects and the manual connection is allowed. When the computer is already connected to either a non-domain based network or a domain-based network over Ethernet, and a user attempts to create a manual connection to an additional network in violation of this policy setting, the existing Ethernet connection is maintained and the manual connection attempt is blocked.  

  If this policy setting isn't configured or is disabled, computers are allowed to connect simultaneously to both domain and non-domain networks.  

  **Default**: Enabled
  
## Windows Defender  
For more information, see [Policy CSP - Defender](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender) in the Windows documentation.  

- **Scan incoming mail messages**  
  Allows or disallows scanning of email.
  
  **Default**: Yes  

- **Office apps launch child process type**  
  Office apps won't be allowed to create child processes. This includes Word, Excel, PowerPoint, OneNote, and Access. This is a typical malware behavior, especially for macro-based attacks that attempt to use Office apps to launch or download malicious executables.
  
  **Default**: Block
  
- **Defender sample submission consent type**  
  Checks for the user consent level in Windows Defender to send data. If the required consent has already been granted, Windows Defender submits them. If not, (and if the user has specified never to ask), the UI is launched to ask for user consent (when Defender/AllowCloudProtection is allowed) before sending data.
  
  **Default**: Send safe samples automatically 
  
- **Signature update interval (in hours)**  
  Defender signature update interval in hours
  
  **Default**: 4
  
- **Script downloaded payload execution type**  
  Defender script downloaded payload execution type
  
  **Default**: Block
  
- **Prevent credential stealing type**  
  Windows Defender Credential Guard uses virtualization-based security to isolate secrets so that only privileged system software can access them. Unauthorized access to these secrets can lead to credential theft attacks, such as Pass-the-Hash or Pass-The-Ticket. Windows Defender Credential Guard prevents these attacks by protecting NTLM password hashes, Kerberos Ticket Granting Tickets, and credentials stored by applications as domain credentials.
  
  **Default**: Enable

- **Email content execution type**  
  This rule blocks the following file types from being run or launched from an email seen in either Microsoft Outlook or webmail (such as Gmail.com or Outlook.com): Executable files (such as .exe, .dll, or .scr) Script files (such as a PowerShell .ps, VisualBasic .vbs, or JavaScript .js file) Script archive files.
  
  **Default**: Block
  
- **Network protection type**  
  This policy allows you to turn on network protection (block/audit) or off in Windows Defender Exploit Guard. Network protection is a feature of Windows Defender Exploit Guard that protects employees using any app from accessing phishing scams, exploit-hosting sites, and malicious content on the Internet. This includes preventing third-party browsers from connecting to dangerous sites. Value type is integer. If you enable this setting, network protection is turned on and employees can't turn it off. Its behavior can be controlled by the following options: Block and Audit. If you enable this policy with the "Block" option, users and apps are blocked from connecting to dangerous domains. You can see this activity in Windows Defender Security Center. If you enable this policy with the "Audit" option, users/apps won't be blocked from connecting to dangerous domains. However, you'll still see this activity in Windows Defender Security Center. If you disable this policy, users/apps won't be blocked from connecting to dangerous domains. You'll not see any network activity in Windows Defender Security Center. If you don't configure this policy, network blocking is disabled by default.
  
  **Default**: Enable
  
- **Defender schedule scan day**  
  Defender schedule scan day.
  
  **Default**: Everyday
  
- **Cloud-delivered protection**  
  To best protect your PC, Windows Defender will send information to Microsoft about any problems it finds. Microsoft will analyze that information, learn more about problems affecting you and other customers, and offer improved solutions.
  
  **Default**:  Yes  

- **Defender potentially unwanted app action**  
  The potentially unwanted application (PUA) protection feature in Windows Defender Antivirus can identify and block PUAs from downloading and installing on endpoints in your network. These applications aren't considered viruses, malware, or other types of threats, but might perform actions on endpoints that adversely affect their performance or use. PUA can also refer to applications that are considered to have a poor reputation. Typical PUA behavior includes: Various types of software bundling Ad injection into web browsers Driver and registry optimizers that detect issues, request payment to fix the errors, but remain on the endpoint and make no changes or optimizations (also known as "rogue antivirus" programs). These applications can increase the risk of your network being infected with malware, cause malware infections to be harder to identify, and can waste IT resources in cleaning up the applications.  
  
  **Default**: Block  

- **Script obfuscated macro code type**  
  Malware and other threats can attempt to obfuscate or hide their malicious code in some script files. This rule prevents scripts that appear to be obfuscated from running.
  
  **Default**: Block
  
- **Scan removable drives during a full scan**  
  Allows Windows Defender to scan for malicious and unwanted software in removable drives (for example, flash drives) during a full scan. Windows Defender Antivirus scans all files on USB devices before execution.
  
  **Default**: Yes  
  
- **Scan archive files**  
  Defender scan archive files.
  
  **Default**: Yes
  
- **Behavior monitoring**  
  Allows or disallows Windows Defender Behavior Monitoring functionality.Embedded in Windows 10, these sensors collect and process behavioral signals from the operating system and sends this sensor data to your private, isolated, cloud instance of Microsoft Defender ATP.
  
  **Default**: Yes

- **Scan files opened from network folders**  
  If files are read-only, user won't be able to remove any detected malware.
  
  **Default**: Yes

- **Untrusted USB process type**  
  With this rule, admins can prevent unsigned or untrusted executable files from running from USB removable drives, including SD cards.
  
  **Default**: Block
  
- **Office apps other process injection type**  
  Office apps, including Word, Excel, PowerPoint, and OneNote, won't be able to inject code into other processes. This is typically used by malware to run malicious code in an attempt to hide the activity from antivirus scanning engines.
  
  **Default**:  Block
  
- **Office macro code allow Win32 imports type**  
  Malware can use macro code in Office files to import and load Win32 DLLs, which can then be used to make API calls to allow further infection throughout the system. This rule attempts to block Office files that contain macro code that is capable of importing Win32 DLLs. This includes Word, Excel, PowerPoint, and OneNote.
  
  **Default**: Block  
  
- **Defender cloud block level**  
  Defender cloud block level.
  
  **Default**: Not Configured

- **Real-time monitoring**  
  Defender requires real-time monitoring.
  
  **Default**: Yes
  
- **Office apps executable content creation or launch type**  
  This rule targets typical behaviors used by suspicious and malicious add-ons and scripts (extensions) that create or launch executable files. This is a typical malware technique. Extensions are blocked from being used by Office apps. Typically these extensions use the Windows Scripting Host (.wsh files) to run scripts that automate certain tasks or provide user-created add-on features
  
  **Default**: Block

## Windows Ink Workspace  
For more information, see [Policy CSP - WindowsInkWorkspace](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsinkworkspace) in the Windows documentation.  

- **Ink Workspace**  
  Specifies whether to allow the user to access the ink workspace. 
  - *Disabled* - access to ink workspace is disabled. The feature is turned off.
  - *Enabled* - The Ink Workspace feature is turned on, but the user can't access it above the lock screen.
  - *Not Configured* - The Ink Workspace feature is turned on, and the user can use it above the lock screen.  

  **Default**: Enabled
 
## Windows PowerShell  
For more information, see [Policy CSP - WindowsPowerShell](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowspowershell) in the Windows documentation.  

- **Power shell shell script block logging**  
  This policy setting enables logging of all PowerShell script input to the Microsoft-Windows-PowerShell/Operational event log. If you enable this policy setting, Windows PowerShell will log the processing of commands, script blocks, functions, and scripts - whether invoked interactively, or through automation. If you disable this policy setting, logging of PowerShell script input is disabled. If you enable the Script Block Invocation Logging, PowerShell additionally logs events when invocation of a command, script block, function, or script starts or stops. Enabling Invocation Logging generates a high volume of event logs. Note: This policy setting exists under both Computer Configuration and User Configuration in the Group Policy Editor. The Computer Configuration policy setting takes precedence over the User Configuration policy setting.
  
  **Default**: Enabled
 

End of PReview baseilne list  -->
