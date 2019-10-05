---
title: Archief-van intune MDM-beveiligings regels instellingen voor Windows 10
titleSuffix: Microsoft Intune
description: Archief met eerdere release versies van de basis instellingen van de MDM-beveiliging voor het beheren van Windows 10 met Microsoft Intune
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/27/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ROBOTS: NOINDEX
ms.reviewer: shpate
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 19307f2ffc234a1eacf30b3aa43fe9c626073f6c
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71736010"
---
<!-- This article contains the exact baseline details for baseline versions that were previously published in security-baseline-settings-mdm.md.  -->

# <a name="archive-of-mdm-security-baseline-settings"></a>Archief met basis instellingen voor MDM-beveiliging  

Details weer geven voor gearchiveerde versies van de MDM-beveiligings basislijn voor intune.  

Wanneer er een nieuwe basis lijn voor MDM-beveiliging wordt uitgebracht, wordt de vorige lijst met instellingen verplaatst van het artikel beveiligings basislijn instellingen naar dit archief. Deze versies worden nog steeds ondersteund voor gebruik, en dit archief wordt geboden om de standaard instellingen voor oudere basislijn versies te weten te komen.

Wanneer een basislijn versie niet meer wordt ondersteund voor gebruik, wordt deze verwijderd uit dit artikel.

- Bekijk de instellingen die beschikbaar zijn in [de huidige basis voor MDM-beveiliging](security-baseline-settings-mdm-all.md?pivots=mdm-may-2019).
- Meer informatie over [beveiligings basislijnen](security-baselines.md)en het bijwerken van de basislijn versie in uw beveiligings basislijn profielen.

## <a name="preview-mdm-security-baseline-for-october-2018"></a>Preview: MDM-basislijn voor beveiliging voor oktober 2018  

*Deze basis lijn is vervangen door de [MDM-beveiligings basislijn voor mei 2019](security-baseline-settings-mdm-all.md?pivots=mdm-may-2019)*

### <a name="above-lock"></a>Vergrendeling boven  

Zie [Beleids-CSP - AboveLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-abovelock) in de Windows-documentatie voor meer informatie.  

- **Weergave van toast-meldingen blokkeren**  
  Met deze beleidsinstelling kunt u voorkomen dat app-meldingen in het vergrendelingsscherm worden weergegeven. Als u deze beleidsinstelling inschakelt, worden geen app-meldingen weergegeven op het vergrendelingsscherm. Als u deze beleidsinstelling uitschakelt of niet configureert, kunnen gebruikers kiezen voor welke app meldingen op het vergrendelingsscherm worden weergegeven.
  
  **Standaardinstelling**: Ja  

### <a name="app-runtime"></a>App-runtime  

Zie [Beleids-CSP - AppRuntime](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-appruntime
) in de Windows-documentatie voor meer informatie.  

- **Optionele Microsoft-accounts voor Windows Store-apps**  
  Met deze beleidsinstelling kunt u regelen of Microsoft-accounts optioneel zijn voor Windows Store-apps waarvoor gebruikers een account nodig hebben om zich aan melden. Dit beleid heeft alleen invloed op Windows Store-apps die deze functie ondersteunen. Als u deze beleidsinstelling inschakelt, kunnen gebruikers zich aanmelden met een bedrijfsaccount bij Windows Store-apps waarvoor ze normaalgesproken een Microsoft-account nodig hebben om zich aan te melden. Als u deze beleidsinstelling uitschakelt of niet configureert, moeten gebruikers zich aanmelden met een Microsoft-account.  
  
  **Standaardinstelling**: ingeschakeld  

### <a name="application-management"></a>Toepassingsbeheer  

Zie [Beleids-CSP - ApplicationManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationmanagement) in de Windows-documentatie voor meer informatie.  

- **Game DVR blokkeren (alleen desktop)**  
  Hiermee bepaalt u of het opnemen en uitzenden van games is toegestaan.
  
  **Standaardinstelling**: Ja  

### <a name="auto-play"></a>Automatisch afspelen  

Zie [Beleids-CSP - Automatisch afspelen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-autoplay) in de Windows-documentatie voor meer informatie.  

- **Automatisch afspelen: standaardgedrag voor AutoRun**  
  Deze instelling beïnvloedt het standaardgedrag voor AutoRun-opdrachten. AutoRun-opdrachten worden opgeslagen in AutoRun.inf-bestanden en kunnen worden gebruikt voor het starten van installatieprogramma's of andere routines. Wanneer deze optie is *ingeschakeld*, kunnen beheerders het standaardgedrag van AutoRun wijzigen op een apparaat waarop Windows Vista of later wordt uitgevoerd. Gedrag kan worden ingesteld op: a) AutoRun-opdrachten volledig uitschakelen, of b) terugzetten naar gedrag voordat Windows Vista werd uitgevoerd, waarbij de AutoRun-opdracht automatisch werd uitgevoerd. Wanneer deze optie is ingesteld op *Uitgeschakeld* of *Niet geconfigureerd*,worden gebruikers op apparaten waarop Windows Vista of later wordt uitgevoerd, gevraagd om een AutoRun-opdracht moet worden uitgevoerd.
  
  **Standaardinstelling**: Niet uitvoeren  
  
- **De modus Automatisch afspelen**  
  Met deze beleidsinstelling kunt u de functie Automatisch afspelen uitschakelen. Met Automatisch afspelen worden gegevens van een station afgelezen zodra u media in het station plaatst. Hierdoor worden installatiebestanden van programma's direct uitgevoerd en wordt muziek op audiomedia direct afgespeeld. Vóór Windows XP SP2 werd Automatisch afspelen standaard uitgeschakeld op losse stations, zoals het floppydiskstation (maar niet het cd-rom-station) en op netwerkstations. Vanaf Windows XP SP2 is Automatisch afspelen ook ingeschakeld voor losse stations, waaronder zip-stations en een aantal USB-apparaten voor massaopslag. Als u deze beleidsinstelling inschakelt, wordt Automatisch afspelen uitgeschakeld op cd-rom-stations en losse mediastations, of uitgeschakeld op alle stations. Met deze beleidsinstelling wordt Automatisch afspelen op andere stationstypen uitgeschakeld. U kunt deze instelling niet gebruiken voor het uitschakelen van Automatisch afspelen op stations waarop deze functie standaard is uitgeschakeld. Als u deze beleidsinstelling uitschakelt of niet configureert, wordt automatisch afspelen ingeschakeld. Opmerking: deze beleidsinstelling wordt zowel in de map Computerconfiguratie als Gebruikersconfiguratie weergegeven. Als de beleidsinstellingen conflicteren, heeft de beleidsinstelling in Computerconfiguratie een hogere prioriteit dan de beleidsinstelling in Gebruikersconfiguratie.
  
  **Standaardinstelling**: uitgeschakeld

- **Automatisch afspelen voor apparaten zonder volume blokkeren**  
  Met deze beleidsinstelling is Automatisch afspelen niet toegestaan voor MTP-apparaten zoals camera's of telefoons. Als u deze beleidsinstelling inschakelt, is Automatisch afspelen niet toegestaan voor MTP-apparaten zoals camera's of telefoons. Als u deze beleidsinstelling uitschakelt of niet configureert, wordt Automatisch afspelen ingeschakeld voor apparaten zonder volume.
  
  **Standaardinstelling**: ingeschakeld  

### <a name="bitlocker"></a>Bitlocker  

Zie [Beleids-CSP - Bitlocker](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-bitlocker
) in de Windows-documentatie voor meer informatie.  

- **Bitlocker-beleid voor losse stations**  
  Deze beleidsinstelling wordt gebruikt om de versleutelingsmethode en coderingssterkte te regelen. De waarden van dit beleid bepalen de coderingssterkte die door BitLocker wordt gebruikt voor versleuteling. Ondernemingen kunnen het versleutelingsniveau bepalen voor extra beveiliging (AES-256 is sterker dan AES-128). Als u deze instelling inschakelt, kunt u afzonderlijke versleutelingsalgoritmen en belangrijke coderingssterkten configureren voor vaste gegevensstations, besturingssysteemstations en losse gegevensstations. Voor vaste stations en besturingssysteemstations wordt het gebruik van het XTS-AES-algoritme aanbevolen. Gebruik 128-bits AES-CBC of 256-bits AES-CBC voor losse stations als het station in andere apparaten wordt gebruikt waarop geen Windows 10, versie 1511 of later wordt uitgevoerd. Het wijzigen van de versleutelingsmethode heeft geen invloed als het station al is versleuteld of als de versleuteling nog wordt uitgevoerd. In deze gevallen wordt deze beleidsinstelling genegeerd.

  Voor het BitLocker-beleid voor verwisselbare stations moet u de volgende instellingen configureren:

  - **Versleuteling vereisen voor schrijftoegang**  
    **Standaardinstelling**: Ja  

  - **Versleutelingsmethode**  
    **Standaardinstelling**: AES 256-bits CBC  

- **Bitlocker-beleid voor vaste stations**  
  Deze beleidsinstelling wordt gebruikt om de versleutelingsmethode en coderingssterkte te regelen. De waarden van dit beleid bepalen de coderingssterkte die door BitLocker wordt gebruikt voor versleuteling. Ondernemingen kunnen het versleutelingsniveau bepalen voor extra beveiliging (AES-256 is sterker dan AES-128). Als u deze instelling inschakelt, kunt u afzonderlijke versleutelingsalgoritmen en belangrijke coderingssterkten configureren voor vaste gegevensstations, besturingssysteemstations en losse gegevensstations. Voor vaste stations en besturingssysteemstations wordt het gebruik van het XTS-AES-algoritme aanbevolen. Gebruik 128-bits AES-CBC of 256-bits AES-CBC voor losse stations als het station in andere apparaten wordt gebruikt waarop geen Windows 10, versie 1511 of later wordt uitgevoerd. Het wijzigen van de versleutelingsmethode heeft geen invloed als het station al is versleuteld of als de versleuteling nog wordt uitgevoerd. In deze gevallen wordt deze beleidsinstelling genegeerd.  
 
  Voor het BitLocker-beleid voor vaste stations moet u de volgende instellingen configureren: 
  - **Versleutelingsmethode**  
    **Standaardinstelling**: AES 256-bits XTS  

- **Bitlocker-beleid voor systeemstations**  
  Deze beleidsinstelling wordt gebruikt om de versleutelingsmethode en coderingssterkte te regelen. De waarden van dit beleid bepalen de coderingssterkte die door BitLocker wordt gebruikt voor versleuteling. Ondernemingen kunnen het versleutelingsniveau bepalen voor extra beveiliging (AES-256 is sterker dan AES-128). Als u deze instelling inschakelt, kunt u afzonderlijke versleutelingsalgoritmen en belangrijke coderingssterkten configureren voor vaste gegevensstations, besturingssysteemstations en losse gegevensstations. Voor vaste stations en besturingssysteemstations wordt het gebruik van het XTS-AES-algoritme aanbevolen. Gebruik 128-bits AES-CBC of 256-bits AES-CBC voor losse stations als het station in andere apparaten wordt gebruikt waarop geen Windows 10, versie 1511 of later wordt uitgevoerd. Het wijzigen van de versleutelingsmethode heeft geen invloed als het station al is versleuteld of als de versleuteling nog wordt uitgevoerd. In deze gevallen wordt deze beleidsinstelling genegeerd.  

  Voor het BitLocker-beleid voor het systeemstation moet u de volgende instellingen configureren:
  - **Versleutelingsmethode**  
    **Standaardinstelling**: AES 256-bits XTS  

### <a name="browser"></a>Browser  

Zie [Beleids-CSP - Browser](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser) in de Windows-documentatie voor meer informatie.  

- **SmartScreen vereisen voor Microsoft Edge**  

  Microsoft Edge gebruikt standaard Windows Defender SmartScreen (ingeschakeld) om gebruikers tegen mogelijke oplichting door phishing en schadelijke software te beschermen. Bovendien kunnen gebruikers Windows Defender SmartScreen standaard niet uitschakelen (uitzetten). Als u dit beleid inschakelt, wordt Windows Defender SmartScreen uitgeschakeld en kunnen gebruikers deze functie niet inschakelen. Configureer dit beleid niet als u gebruikers Windows Defender SmartScreen zelf wilt kunnen laten in- of uitschakelen.  
  
  **Standaardinstelling**: Ja  
  
- **Toegang tot schadelijke sites blokkeren**  

  Standaard hebben gebruikers in Microsoft Edge toestemming om de Windows Defender SmartScreen-waarschuwingen over mogelijke schadelijke websites te omzeilen (negeren), zodat ze de site kunnen blijven gebruiken. Met dit beleid kunt u Microsoft Edge echter zo configureren dat gebruikers de waarschuwingen niet kunnen omzeilen, waardoor ze de website dus niet langer kunnen gebruiken.
  
  **Standaardinstelling**: Ja  
  
- **Downloaden van niet-geverifieerde bestanden blokkeren** Standaard hebben gebruikers in Microsoft Edge toestemming om de Windows Defender SmartScreen-waarschuwingen over mogelijk schadelijke bestanden te omzeilen (negeren), waardoor ze de niet-geverifieerde bestanden kunnen blijven downloaden. Als u dit beleid inschakelt, voorkomt u dat gebruikers de waarschuwingen kunnen omzeilen, waardoor ze de niet-geverifieerde bestanden niet meer kunnen downloaden.
  
  **Standaardinstelling**: Ja  
  
- **Wachtwoordbeheer blokkeren**  
  Standaard gebruikt Microsoft Edge Wachtwoordbeheer automatisch, waardoor gebruikers wachtwoorden lokaal kunnen beheren. Als u dit beleid uitschakelt, voorkomt u dat Microsoft Edge Wachtwoordbeheer kan gebruiken. Configureer dit beleid niet als u gebruikers wilt laten kiezen om wachtwoorden lokaal te laten opslaan en beheren met Wachtwoordbeheer.
  
  **Standaardinstelling**: Ja  
  
- **Overschrijving van certificaatfouten voorkomen**  
  Deze beleidsinstelling voorkomt dat gebruikers fouten in het SSL/TLS-certificaat (Secure Sockets Layer/Transport Layer Security) negeren die het bladeren in Internet Explorer onderbreken (zoals 'verlopen', 'ingetrokken' of 'namen komen niet overeen'). Als u deze beleidsinstelling inschakelt, kan de gebruiker niet doorgaan met bladeren. Als u deze beleidsinstelling uitschakelt of niet configureert, kan de gebruiker kiezen certificaatfouten te negeren en doorgaan met bladeren.
  
  **Standaardinstelling**: Ja  

### <a name="connectivity"></a>Connectiviteit  

Zie [Beleids-CSP - Connectiviteit](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-connectivity) in de Windows-documentatie voor meer informatie.  

- **Internetdownloads voor de wizards Webpublicaties en Online bestellen blokkeren**  
  Dit beleid bepaalt of Windows moet worden gebruikt voor het downloaden van een lijst met providers voor de wizards Webpublicaties en Online bestellen. Met deze wizards kunnen gebruikers in een lijst met bedrijven een bedrijf selecteren dat services als onlineopslag en het afdrukken van foto's biedt. Standaard worden zowel bedrijven weergegeven die zijn gedownload van een Windows-website als bedrijven die zijn opgegeven in het register. Als u deze beleidsinstelling inschakelt, worden geen providers gedownload en worden alleen de serviceproviders weergegeven die in het cachegeheugen van het lokale register zijn opgeslagen. Als u deze beleidsinstelling uitschakelt of niet configureert, wordt een lijst met providers gedownload wanneer de gebruiker de wizards Publiceren op internet of Online bestellen gebruikt. Zie de documentatie voor de wizards Publiceren op internet of Online bestellen voor meer informatie over bijvoorbeeld het opgeven van serviceproviders in het register.  
  
  **Standaardinstelling**: ingeschakeld  

- **Downloaden van printerstuurprogramma's via HTTP blokkeren**  
  Met deze beleidsinstelling geeft u aan of deze client afdrukstuurprogrammapakketten via HTTP mag downloaden. Als u afdrukken via HTTP wilt instellen, moeten stuurprogramma's die niet in de inbox staan via HTTP worden gedownload. Opmerking: met deze beleidsinstelling wordt niet voorkomen dat de client via HTTP kan afdrukken naar printers op intranet of internet. U voorkomt hiermee alleen dat er stuurprogramma's worden gedownload die niet al lokaal zijn geïnstalleerd. Als u deze beleidsinstelling inschakelt, kunnen printerstuurprogramma's niet via HTTP worden gedownload. Als u deze beleidsinstelling uitschakelt of niet configureert, kunnen gebruikers printerstuurprogramma's via HTTP downloaden.
  
  **Standaardinstelling**: ingeschakeld  

### <a name="credentials-delegation"></a>CredentialsDelegation  

Zie [Beleids-CSP - CredentialsDelegation](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsdelegation
) in de Windows-documentatie voor meer informatie.  

- **Delegatie van externe host van aanmeldingsgegevens die niet kunnen worden geëxporteerd**  
  Met een externe host staat u toe dat aanmeldingsgegevens die niet kunnen worden geëxporteerd, kunnen worden gedelegeerd. Wanneer u overdracht van referenties gebruikt, leveren apparaten een exporteerbare versie van referenties aan de externe host, waarmee gebruikers het risico lopen op diefstal van referenties door aanvallers op de externe host. Als u deze beleidsinstelling inschakelt, biedt de host ondersteuning voor de modi Beperkt beheer of Externe Credential Guard. Als u deze beleidsinstelling uitschakelt of niet configureert, worden de modi Beperkt beheer of Externe Credential Guard niet ondersteund. De gebruiker moet zijn of haar aanmeldingsgegevens altijd doorgeven aan de host.  

  
  **Standaardinstelling**: ingeschakeld  

### <a name="credentials-ui"></a>Referenties gebruikersinterface  

Zie [Beleids-CSP - CredentialsUI](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-credentialsui) in de Windows-documentatie voor meer informatie.  

- **Beheerders opsommen** Met deze beleidsinstelling bepaalt u of beheerdersaccounts worden weergegeven wanneer een gebruiker een toepassing die wordt uitgevoerd probeert uit te breiden. Standaard worden beheerdersaccounts niet weergegeven wanneer de gebruiker een toepassing die wordt uitgevoerd probeert uit te breiden. Als u deze beleidsinstelling inschakelt, worden alle lokale beheerdersaccounts op de pc weergegeven zodat de gebruiker één account kan kiezen en het juiste wachtwoord kan invoeren. Als u deze beleidsinstelling uitschakelt, zijn gebruikers altijd vereist om een gebruikersnaam en wachtwoord in te voeren om toepassingen uit te breiden.  

  
  **Standaardinstelling**: uitgeschakeld  

### <a name="data-protection"></a>Gegevensbescherming  

Zie [Beleids-CSP - DataProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection
) in de Windows-documentatie voor meer informatie.  

- **Direct Memory Access blokkeren**  
  Met deze beleidsinstelling kunt u Direct Memory Access (DMA) blokkeren voor alle hot-pluggable PCI-downstream-poorten totdat een gebruiker zich bij Windows aanmeldt. Zodra een gebruiker zich heeft aangemeld, somt Windows de PCI-apparaten op die met de PCI-poorten van de host zijn verbonden. Steeds wanneer de gebruiker het apparaat vergrendelt, wordt DMA geblokkeerd op hot-pluggable PCI-poorten zonder onderliggende apparaten totdat de gebruiker zich opnieuw aanmeldt. Apparaten die al waren geïnventariseerd toen het apparaat was ontgrendeld, blijven werken totdat ze worden losgekoppeld. Deze beleidsinstelling wordt uitsluitend afgedwongen wanneer BitLocker of apparaatversleuteling is ingeschakeld.
  
  
  **Standaardinstelling**: Ja  

### <a name="device-guard"></a>Device Guard  

Zie [Beleids-CSP - DeviceGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceguard
) in de Windows-documentatie voor meer informatie.  

- **Credential Guard**  
  Met deze instelling kunnen gebruikers Credential Guard inschakelen met op virtualisatie gebaseerde beveiliging om aanmeldingsgegevens bij opnieuw opstarten te beschermen.
   
  **Standaardinstelling**: Inschakelen met UEFI-vergrendeling 

- **Beveiliging op basis van virtualisatie inschakelen**  </br>
  Met deze optie wordt Beveiliging op basis van virtualisatie (VBS) ingeschakeld bij de volgende keer opnieuw opstarten. Beveiliging op basis van virtualisatie maakt gebruik van de Windows-Hypervisor om ondersteuning te bieden voor beveiligingsservices.
  
  **Standaardinstelling**: Ja  

- **SystemGuard starten**    
  **Standaardinstelling**: ingeschakeld  

### <a name="device-installation"></a>Apparaatinstallatie  

Zie [Beleids-CSP - apparaatinstallatie](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-deviceinstallation) in de Windows-documentatie voor meer informatie.  

- **Installatie van hardwareapparaten op basis van apparaat-id's**  
  Met deze beleidsinstelling kunt u een lijst opgeven met Plug en Play-hardware id's en compatibele id's voor apparaten die niet mogen worden geïnstalleerd in Windows. Deze beleidsinstelling heeft een hogere prioriteit dan welke andere beleidsinstelling dan ook waarmee Windows wordt toegestaan een apparaat te installeren. Als u deze beleidsinstelling inschakelt, kunnen apparaten waarvan de hardware-id of compatibele id die in de door u gemaakte lijst staan, niet worden geïnstalleerd in Windows. Als u deze beleidsinstelling inschakelt op een externe desktopserver, heeft deze invloed op de omleiding van de opgegeven apparaten van een externe desktopclient naar de externe desktopserver. Als u deze beleidsinstelling uitschakelt of niet configureert, kunnen apparaten worden geïnstalleerd of bijgewerkt, voor zover dat door andere beleidsinstellingen is toegestaan of verboden.
  
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
  
  **Standaardinstelling**: installatie van hardwareapparaten blokkeren  

  Wanneer *installatie van hardwareapparaten blokkeren* wordt geselecteerd, zijn de volgende instellingen beschikbaar.
  - **Overeenkomende hardwareapparaten verwijderen**    
  Deze instelling is alleen beschikbaar wanneer *Installatie hardwareapparaten op installatieklasse* is ingesteld op *Installatie van hardwareapparaten blokkeren*.  

    **Standaardinstelling**: *Geen standaardconfiguratie*  

  - **Hardwareapparaat-id's die zijn geblokkeerd**  
    Deze instelling is alleen beschikbaar wanneer *Installatie hardwareapparaten op installatieklasse* is ingesteld op *Installatie van hardwareapparaten blokkeren*.
    
    **Standaardinstelling**: *Geen standaardconfiguratie*  

### <a name="device-lock"></a>Apparaatvergrendeling  

Zie [Beleids-CSP - DeviceLock](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock) in de Windows-documentatie voor meer informatie.  

- **Gebruik van de camera voorkomen**  
  Hiermee schakelt u schakelaar voor de camera op het vergrendelingsscherm uit bij de pc-instellingen en voorkomt u dat een camera op het vergrendelingsscherm kan worden aangeroepen. Standaard kunnen gebruikers het aanroepen van een beschikbare camera op het vergrendelingsscherm zelf inschakelen. Als u deze instelling inschakelt, kunnen gebruikers cameratoegang via het vergrendelingsscherm camera niet langer in- of uitschakelen bij de pc-instellingen en kan de camera niet worden aangeroepen op het vergrendelingsscherm. 
  
  **Standaardinstelling**: ingeschakeld  

- **Wachtwoord vereisen**  
  Hiermee geeft u aan of apparaatvergrendeling is ingeschakeld.
  
  **Standaardinstelling**: Ja  
  
  Wanneer *Wachtwoord vereisen* is ingesteld op *Ja*, zijn de volgende instellingen beschikbaar.

  - **Wachtwoord: minimumaantal tekensets**  
    Het aantal complexe elementtypen (hoofdletters en kleine letters, cijfers en leestekens) dat is vereist voor een sterke pincode of een sterk wachtwoord. Pincodes leiden tot het volgende gedrag op computers en mobiele apparaten: 1 - Alleen cijfers 2 - Cijfers en kleine letters zijn vereist 3 - Cijfers, kleine letters en hoofdletters zijn vereist. Niet ondersteund in Microsoft-desktopaccounts en domeinaccounts. 4 - Cijfers, kleine letters, hoofdletters en speciale tekens zijn vereist. Dit wordt niet ondersteund in desktop. De standaardwaarde is 1. 
    
    **Standaardinstelling**: 3  
  
  - **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**  
    Het aantal verificatiefouten dat is toegestaan voordat het apparaat wordt gewist. Met de waarde 0 wordt de wisfunctionaliteit van het apparaat uitgeschakeld.
    
    **Standaard**: 10  
  
  - **Dagen tot wachtwoord verloopt**  
    Met de beleidsinstelling Maximale wachtwoordduur bepaalt u hoe lang (in dagen) een wachtwoord kan worden gebruikt voordat de gebruiker dit moet wijzigen. U kunt instellen dat wachtwoorden na een aantal dagen tussen 1 en 999 verlopen, of u kunt opgeven dat wachtwoorden nooit verlopen door het aantal dagen in te stellen op 0. Als de Maximale wachtwoordduur tussen 1 en 999 dagen ligt, moet de Minimale wachtwoordduur minder zijn dan de Maximale wachtwoordduur. Als Maximale wachtwoordduur is ingesteld op 0, kan Minimale wachtwoordduur op elke waarde tussen 0 en 998 dagen worden ingesteld.
    
    **Standaardinstelling**: 60  
  
  - **Vereist wachtwoordtype**  
    Hiermee bepaalt u het type pincode of wachtwoord dat is vereist.
    
    **Standaardinstelling**: Alfanumeriek  
  
  - **Minimale wachtwoordlengte**  
    Met de beleidsinstelling Minimale wachtwoordlengte bepaalt u het minimumaantal tekens waaruit een wachtwoord voor een gebruikersaccount mag bestaan. U kunt een waarde tussen 1 en 14 tekens instellen, of u kunt instellen dat er geen wachtwoord is vereist door het aantal tekens in te stellen 0.
    
    **Standaardinstelling**: 8  

  - **Eenvoudige wachtwoorden blokkeren**  
    Hiermee geeft u aan of pincodes of wachtwoorden zoals '1111' en '1234' zijn toegestaan. Voor de desktop bepaalt u hiermee ook of afbeeldingswachtwoorden mogen worden gebruikt.
    
    **Standaardinstelling**: Ja  
      *Wanneer u deze optie instelt op Ja mogen eenvoudige wachtwoorden niet worden gebruikt.* 

  - **Wachtwoorden niet opnieuw gebruiken**  
    Hiermee geeft u op hoeveel wachtwoorden in de geschiedenis kunnen worden opgeslagen die niet mogen worden gebruikt. De waarde bevat ook het huidige wachtwoord van de gebruiker. Met de instelling *1* kan de gebruiker bijvoorbeeld zijn huidige wachtwoord niet opnieuw gebruiken bij het kiezen van een nieuw wachtwoord. De instelling *5* betekent een gebruiker zijn nieuwe wachtwoord niet kan instellen op zijn huidige wachtwoord of een van zijn vier wachtwoorden daarvoor.
    
    **Standaardinstelling**: 24  

- **Diavoorstelling voorkomen**  
  Hiermee schakelt u de instellingen voor een diavoorstelling op het vergrendelingsscherm bij de pc-instellingen uit en voorkomt u dat een diavoorstelling op het vergrendelingsscherm wordt afgespeeld. Standaard kunnen gebruikers een diavoorstelling inschakelen die wordt uitgevoerd nadat ze het apparaat vergrendelen. Als u deze instelling inschakelt, kunnen gebruikers geen instellingen voor diavoorstellingen bij de pc-instellingen aanpassen en kan er geen diavoorstelling worden gestart.
  
    **Standaardinstelling**: ingeschakeld  
    *De instelling Ingeschakeld voorkomt dat diavoorstellingen worden uitgevoerd.* 

- **Minimale wachtwoordduur in dagen**  
  Met de beleidsinstelling Minimale wachtwoordduur bepaalt u de periode (in dagen) dat een wachtwoord moet worden gebruikt voordat de gebruiker dit kan wijzigen. U kunt een waarde tussen 1 en 998 dagen instellen, of u kunt toestaan dat wachtwoorden direct worden gewijzigd door het aantal dagen in te stellen op 0. De Minimale wachtwoordduur moet korter zijn dan de Maximale wachtwoordduur, tenzij de Maximale wachtwoordduur is ingesteld op 0, waarmee u aangeeft dat die wachtwoorden nooit verlopen. Als de Maximale wachtwoordduur is ingesteld op 0, kan de Minimale wachtwoordduur worden ingesteld op elke waarde tussen 0 en 998.
  
    **Standaardinstelling**: 1  

### <a name="event-log-service"></a>De service Gebeurtenislogboek  

Zie [Beleids-CSP - EventLogService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-eventlogservice) in de Windows-documentatie voor meer informatie.  

- **Maximale bestandsgrootte voor beveiligingslogboeken (in KB)**  
  Met deze beleidsinstelling geeft u de maximale grootte van het logboekbestand (in kB) op. Als u deze beleidsinstelling inschakelt, kunt u een maximale grootte voor logboekbestanden tussen 1 MB (1024 kB) en 2 TB (2147483647 KB) instellen, die per kB kan worden verhoogd. Als u deze beleidsinstelling uitschakelt of niet configureert, wordt de maximale grootte van het logboekbestand ingesteld op de lokaal geconfigureerde waarde. Deze waarde kan door de lokale beheerder worden gewijzigd via het dialoogvenster Logboekeigenschappen. De standaardinstelling is 20 MB.
  
   **Standaardinstelling**: 196608  

- **Maximale bestandsgrootte voor systeemlogboeken (in kB)**  
  Met deze beleidsinstelling geeft u de maximale grootte van het logboekbestand (in kB) op. Als u deze beleidsinstelling inschakelt, kunt u een maximale grootte voor logboekbestanden tussen 1 MB (1024 kB) en 2 TB (2147483647 KB) instellen, die per kB kan worden verhoogd. Als u deze beleidsinstelling uitschakelt of niet configureert, wordt de maximale grootte van het logboekbestand ingesteld op de lokaal geconfigureerde waarde. Deze waarde kan door de lokale beheerder worden gewijzigd via het dialoogvenster Logboekeigenschappen. De standaardinstelling is 20 MB.
  
  **Standaardinstelling**: 32768  

- **Maximale bestandsgrootte voor toepassingslogboeken (in kB)**  
  Met deze beleidsinstelling geeft u de maximale grootte van het logboekbestand (in kB) op. Als u deze beleidsinstelling inschakelt, kunt u een maximale grootte voor logboekbestanden tussen 1 MB (1024 kB) en 2 TB (2147483647 KB) instellen, die per kB kan worden verhoogd. Als u deze beleidsinstelling uitschakelt of niet configureert, wordt de maximale grootte van het logboekbestand ingesteld op de lokaal geconfigureerde waarde. Deze waarde kan door de lokale beheerder worden gewijzigd via het dialoogvenster Logboekeigenschappen. De standaardinstelling is 20 MB.
  
  **Standaardinstelling**: 32768  

### <a name="experience"></a>Ervaring  

Zie [Beleids-CSP - Ervaring](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-experience) in de Windows-documentatie voor meer informatie.  

- **Windows Spotlight blokkeren**  
  Hiermee kunnen IT-beheerders alle Windows Spotlight-functies uitschakelen: Window Spotlight op het vergrendelingsscherm, Windows Tips, Microsoft consumentenfuncties en andere gerelateerde functies.
  
  **Standaardinstelling**: Ja  

  Wanneer *Windows-spotlight blokkeren* is ingesteld op *Ja*, zijn de volgende instellingen beschikbaar.
  
  - **Suggesties van derden in Windows Spotlight blokkeren**  
    Hiermee geeft u op of app- en inhoudssuggesties van uitgevers van externe software zijn toegestaan in Windows Spotlight-functies zoals Spotlight op het vergrendelingsscherm, voorgestelde apps in het startmenu en Windows Tips. Gebruikers zien mogelijk nog wel suggesties voor Microsoft-functies, apps en services.
      
    **Standaardinstelling**: Ja  
  - **Specifieke functies voor consumenten blokkeren**  
    Hiermee kunnen IT-beheerders ervaringen inschakelen die doorgaans alleen voor consumenten worden gebruikt, zoals startsuggesties, lidmaatschapsmeldingen, Post-OOBE-app-installaties en omleidingstegels.
    
    **Standaardinstelling**: Ja  


### <a name="exploit-guard"></a>ExploitGuard  

Zie [Beleids-CSP - ExploitGuard](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-exploitguard) in de Windows-documentatie voor meer informatie.  

- **XML Exploit Guard-beveiliging**  
  Hiermee kan de IT-beheerder een configuratie pushen die de gewenste systeem- en toepassingbeperkingsopties voor alle apparaten in de organisatie aangeeft. De configuratie wordt vertegenwoordigd door een XML. Exploit Protection helpt apparaten te beschermen tegen malware die exploits gebruikt om zichzelf te verspreiden en andere apparaten te infecteren. U gebruikt de Windows-beveiligingsapp of PowerShell om een set beperkingen te maken (dit wordt een configuratie genoemd). U kunt deze configuratie vervolgens als XML-bestand exporteren en delen met meerdere apparaten in uw netwerk, zodat ze allemaal dezelfde set beperkingsinstellingen hebben. U kunt ook een bestaand XML-bestand met een EMET-configuratie naar een XML-bestand voor exploitbeveiligingsconfiguratie converteren en importeren.
  
  **Standaardinstelling**: *Er is een voorbeeld van een XML-bestand meegeleverd* 
 
### <a name="file-explorer"></a>Bestandsverkenner  

Zie [Beleids-CSP - FileExplorer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-fileexplorer) in de Windows-documentatie voor meer informatie.  

- **Preventie van gegevensuitvoering blokkeren**  
  Wanneer u preventie van gegevensuitvoering uitschakelt, kunnen bepaalde verouderde invoegtoepassingen werken zonder de Verkenner af te sluiten.
  
  **Standaardinstelling**: uitgeschakeld  
   
- **Heap-beëindiging blokkeren bij corruptie**  
  Wanneer u Heap-beëindiging blokkeren bij corruptie uitschakelt, kunnen bepaalde verouderde invoegtoepassingen werken zonder de Verkenner direct af te sluiten, hoewel de Verkenner later nog wel steeds onverwacht kan worden beëindigd.
  
  **Standaardinstelling**: uitgeschakeld  
    

### <a name="internet-explorer"></a>Internet Explorer  

Zie [Beleids-CSP - InternetExplorer](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-internetexplorer) in de Windows-documentatie voor meer informatie.  

- **Internet Explorer: toegang tot gegevensbronnen via een internetzone**  
  Met deze beleidsinstelling kunt u beheren of Internet Explorer toegang heeft tot gegevens van een andere beveiligingszone met behulp van de Microsoft XML-parser (MSXML) of ActiveX-gegevensobjecten (ADO). Als u deze beleidsinstelling inschakelt, kunnen gebruikers een pagina laden in de zone die MSXML of ADO gebruikt voor toegang tot gegevens van een andere site in de zone. Als u Prompt selecteert in de vervolgkeuzelijst, wordt gebruikers gevraagd om te kiezen of een pagina mag worden geladen in de zone die MSXML of ADO gebruikt voor toegang tot gegevens van een andere site in de zone. Als u deze beleidsinstelling uitschakelt, kunnen gebruikers geen pagina laden in de zone die MSXML of ADO gebruikt voor toegang tot gegevens van een andere site in de zone. Als u deze beleidsinstelling niet configureert, kunnen gebruikers geen pagina laden in de zone die MSXML of ADO gebruikt voor toegang tot gegevens van een andere site in de zone.
  
  **Standaard**: Uitschakelen  
  
- **Internet Explorer: inhoud van verschillende domeinen in Windows in de beperkte zone verslepen**  
  Met deze beleidsinstelling kunt u opties instellen voor het verslepen van inhoud van het ene naar het andere domein wanneer de bron en de bestemming zich in hetzelfde venster bevinden. Als u deze beleidsinstelling inschakelt en op Inschakelen klikt, kunnen gebruikers inhoud van het ene naar het andere domein verslepen wanneer de bron en de bestemming zich in hetzelfde venster bevinden. Gebruikers kunnen deze instelling niet wijzigen. Als u deze beleidsinstelling inschakelt en op Uitschakelen klikt, kunnen gebruikers geen inhoud van het ene naar het andere domein verslepen wanneer de bron en de bestemming zich in hetzelfde venster bevinden. Gebruikers kunnen deze instelling niet wijzigen in het dialoogvenster Internetopties. Als u deze beleidsinstelling in Internet Explorer 10 uitschakelt of niet configureert, kunnen gebruikers geen inhoud van het ene naar het andere domein verslepen wanneer de bron en de bestemming zich in hetzelfde venster bevinden. Gebruikers kunnen deze instelling wijzigen in het dialoogvenster Internetopties. Als u deze beleidsinstelling in Internet Explorer 9 en eerdere versies uitschakelt of niet configureert, kunnen gebruikers inhoud van het ene naar het andere domein verslepen wanneer de bron en de bestemming zich in hetzelfde venster bevinden. Gebruikers kunnen deze instelling niet wijzigen in het dialoogvenster Internetopties.
  
  **Standaardinstelling**: uitgeschakeld
  
- **Internet Explorer: waarschuwing voor niet-overeenkomende certificaatadressen**  
  Met deze beleidsinstelling kunt u de beveiligingswaarschuwing inschakelen voor het geval dat certificaatadressen niet overeenkomen. Wanneer deze beleidsinstelling is ingeschakeld, krijgt de gebruiker een waarschuwing wanneer hij of zij HTTPS-website (Secure HTTP) bezoekt die certificaten laat zien die voor een ander website-adres zijn uitgegeven. Met deze waarschuwing voorkomt u aanvallen met adresvervalsing (spoofing). Als u deze beleidsinstelling inschakelt, wordt altijd de waarschuwing weergegeven dat de certificaatadressen niet overeenkomen. Als u deze beleidsinstelling uitschakelt of niet configureert, kan de gebruiker kiezen of de waarschuwing dat de certificaatadressen niet overeenkomen wordt weergegeven (met behulp van de pagina Geavanceerd in het internetconfiguratiescherm).
  
  **Standaardinstelling**: ingeschakeld 
  
- **Internet Explorer: sites met minder machtigingen in de beperkte zone**  
  Met deze beleidsinstelling kunt u beheren of websites van zones met minder machtigingen, zoals internetsites, naar deze zone mogen navigeren. Als u deze beleidsinstelling inschakelt, kunnen websites van zones met minder machtigingen nieuwe vensters openen in, of navigeren naar, deze zone. De beveiligingszone wordt uitgevoerd zonder de toegevoegde beveiligingslaag die door de beveiliging van de beveiligingsfunctie Zoneverhoging wordt geleverd. Als u Vragen in de vervolgkeuzelijst selecteert, krijgt de gebruiker een waarschuwing dat er sprake is van mogelijk riskante navigatie. Als u deze beleidsinstelling uitschakelt, is mogelijk schadelijke navigatie verboden. De beveiligingsfunctie van Internet Explorer is in deze zone ingeschakeld, zoals dit is ingesteld bij de functie Zone-uitbreiding. Als u deze beleidsinstelling niet configureert, is mogelijk schadelijke navigatie verboden. De beveiligingsfunctie van Internet Explorer is in deze zone ingeschakeld, zoals dit is ingesteld bij de functie Zone-uitbreiding.
  
  **Standaard**: Uitschakelen  
  
- **Internet Explorer: automatische prompt voor bestanddownloads in de beperkte zone**  
  Met deze beleidsinstelling bepaalt u of gebruikers een melding krijgen bij bestanddownloads die niet door de gebruiker zijn geïnitieerd. Gebruikers krijgen, ongeacht deze instelling, dialoogvensters te zien voor bestanddownloads die ze zelf hebben geïnitieerd. Als u deze instelling inschakelt, krijgen gebruikers een dialoogvenster voor bestanddownloads te zien bij automatische downloadpogingen. Als u deze instelling uitschakelt of niet configureert, worden bestanddownloads die niet door de gebruiker zelf zijn geïnitieerd geblokkeerd en zien gebruikers de Meldingenbalk in plaats van het dialoogvenster voor bestanddownloads. Gebruikers kunnen vervolgens op de Meldingenbalk klikken voor de bestanddownloadprompt.
  
  **Standaardinstelling**: uitgeschakeld
  
- **Internet Explorer: onderdelen in de internetzone die afhankelijk zijn van .NET Framework**  
  Met deze beleidsinstelling kunt u beheren of .NET Framework-onderdelen die niet met Authenticode zijn ondertekend, kunnen worden uitgevoerd in Internet Explorer. Deze onderdelen bevatten beheerde besturingselementen waarnaar vanuit een objectlabel wordt verwezen en beheerde uitvoerbare bestanden waarnaar vanuit een koppeling wordt verwezen. Als u deze beleidsinstelling inschakelt, worden niet-ondertekende beheerde onderdelen in Internet Explorer uitgevoerd. Als u Prompt selecteert in de vervolgkeuzelijst, wordt de gebruiker gevraagd om te bepalen of niet-ondertekende beheerde onderdelen moeten worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, worden niet-ondertekende beheerde onderdelen niet in Internet Explorer uitgevoerd. Als u deze beleidsinstelling niet configureert, worden niet-ondertekende beheerde onderdelen in Internet Explorer uitgevoerd.
  
  **Standaard**: Uitschakelen 
  
- **Internet Explorer: alleen goedgekeurde domeinen in de internetzone toestaan om TDC ActiveX-besturingselementen te gebruiken**  
  Met deze beleidsinstelling bepaalt u of de gebruiker het TDC ActiveX-besturingselement op websites kan uitvoeren. Als u deze beleidsinstelling inschakelt, wordt het TDC ActiveX-besturingselement niet uitgevoerd vanaf websites in deze zone. Als u deze beleidsinstelling uitschakelt, wordt het TDC ActiveX-besturingselement uitgevoerd vanaf alle sites in deze zone.
  
  **Standaardinstelling**: ingeschakeld 
  
- **Internet Explorer: door script geïnitieerde vensters in de beperkte zone**  
  Met deze beleidsinstelling kunt u beperkingen beheren voor door scripts geïnitieerde pop-upvensters en vensters die een titel en statusbalken bevatten. Als u deze beleidsinstelling inschakelt, is de beveiliging door Windows-beperkingen niet van toepassing in deze zone. De beveiligingszone wordt uitgevoerd zonder de toegevoegde beveiligingslaag van deze functie. Als u deze beleidsinstelling uitschakelt, kunnen mogelijk schadelijke acties in door scripts geïnitieerde pop-upvensters en vensters die een titel en statusbalken bevatten, niet worden uitgevoerd. Deze beveiligingsfunctie van Internet Explorer is in deze zone ingeschakeld, zoals dat door de instelling van de functie Gescripte Windows-beveiligingsbeperkingen voor het proces is opgegeven. Als u deze beleidsinstelling niet configureert, kunnen mogelijk schadelijke acties in door scripts geïnitieerde pop-upvensters en vensters die een titel en statusbalken bevatten, niet worden uitgevoerd. Deze beveiligingsfunctie van Internet Explorer is in deze zone ingeschakeld, zoals dat door de instelling van de functie Gescripte Windows-beveiligingsbeperkingen voor het proces is opgegeven.
  
  **Standaardinstelling**: uitgeschakeld 
  
- **Internet Explorer: lokaal pad in internetzone opnemen tijdens het uploaden van bestanden naar de server**  
  Met deze beleidsinstelling bepaalt u of gegevens over het lokale pad worden verzonden wanneer de gebruiker een bestand uploadt via een HTML-formulier. Als er gegevens over het lokale pad zijn verzonden, wordt mogelijk bepaalde informatie onbedoeld op de server weergegeven. Bestanden die vanaf het bureaublad van de gebruiker zijn verzonden, bevatten bijvoorbeeld mogelijk de gebruikersnaam als onderdeel van het pad. Als u deze beleidsinstelling inschakelt, worden gegevens over het pad verzonden wanneer de gebruiker een bestand via een HTML-formulier uploadt. Als u deze beleidsinstelling uitschakelt, worden gegevens over het pad verwijderd wanneer de gebruiker een bestand via een HTML-formulier uploadt. Als u deze beleidsinstelling niet configureert, kan de gebruiker kiezen of gegevens over het pad worden verzonden wanneer ze een bestand uploaden via een HTML-formulier. Standaard worden gegevens over het pad verzonden.
  
  **Standaardinstelling**: uitgeschakeld 
  
- **Internet Explorer-processen uitschakelen in uitgebreide beveiligde modus**  
  Met deze beleidsinstelling bepaalt u of Internet Explorer 11 64-bits-processen (voor meer beveiliging) of 32-bits processen (voor meer compatibiliteit) gebruikt wanneer deze worden uitgevoerd in de uitgebreide beveiligde modus in 64-bits versies van Windows. Belangrijk: een aantal ActiveX-besturingselementen en werkbalken is mogelijk niet beschikbaar wanneer 64-bits processen worden gebruikt. Als u deze beleidsinstelling inschakelt, gebruikt Internet Explorer 11 64-bits tabbladprocessen wanneer deze worden uitgevoerd in de uitgebreide beveiligde modus op 64-bits versies van Windows. Als u deze beleidsinstelling uitschakelt, gebruikt Internet Explorer 11 32-bits tabbladprocessen wanneer deze worden uitgevoerd in de uitgebreide beveiligde modus op 64-bits versies van Windows. Als u deze beleidsinstelling niet configureert, kunnen gebruikers deze functie in-of uitschakelen via de Internet Explorer-instellingen. Deze functie is standaard uitgeschakeld.
  
  **Standaardinstelling**: ingeschakeld 
  
- **Internet Explorer: certificaatfouten negeren**  
  Deze beleidsinstelling voorkomt dat gebruikers fouten in het SSL/TLS-certificaat (Secure Sockets Layer/Transport Layer Security) negeren die het bladeren in Internet Explorer onderbreken (zoals 'verlopen', 'ingetrokken' of 'namen komen niet overeen'). Als u deze beleidsinstelling inschakelt, kan de gebruiker niet doorgaan met bladeren. Als u deze beleidsinstelling uitschakelt of niet configureert, kan de gebruiker kiezen certificaatfouten te negeren en doorgaan met bladeren.
  
  **Standaardinstelling**: uitgeschakeld 
  
- **Internet Explorer: XAML-bestanden laden in de internetzone**  
  Met deze beleidsinstelling kunt u het laden van XAML-bestanden (Extensible Application Markup Language) beheren. XAML is een op XML gebaseerde declaratieve opmaaktaal die veel wordt gebruikt voor het maken van uitgebreide gebruikersinterfaces en graphics waarmee gebruik kan worden gemaakt van de Windows Presentation Foundation. Als u deze beleidsinstelling inschakelt en de vervolgkeuzelijst op Inschakelen instelt, worden XAML-bestanden automatisch in Internet Explorer geladen. Gebruikers kunnen dit gedrag niet wijzigen. Als u de vervolgkeuzelijst instelt op Vragen, wordt de gebruiker gevraagd om XAML-bestanden te laden. Als u deze beleidsinstelling uitschakelt, worden XAML-bestanden niet in Internet Explorer geladen. Gebruikers kunnen dit gedrag niet wijzigen. Als u deze beleidsinstelling niet configureert, kan de gebruiker zelf bepalen of hij of zij XAML-bestanden in Internet Explorer wil laden.
  
  **Standaard**: Uitschakelen 
  
- **Internet Explorer: automatische prompt voor bestanddownloads in internetzone**  
  Met deze beleidsinstelling bepaalt u of gebruikers een melding krijgen bij bestanddownloads die niet door de gebruiker zijn geïnitieerd. Gebruikers krijgen, ongeacht deze instelling, dialoogvensters te zien voor bestanddownloads die ze zelf hebben geïnitieerd. Als u deze instelling inschakelt, krijgen gebruikers een dialoogvenster voor bestanddownloads te zien bij automatische downloadpogingen. Als u deze instelling uitschakelt of niet configureert, worden bestanddownloads die niet door de gebruiker zelf zijn geïnitieerd geblokkeerd en zien gebruikers de Meldingenbalk in plaats van het dialoogvenster voor bestanddownloads. Gebruikers kunnen vervolgens op de Meldingenbalk klikken voor de bestanddownloadprompt.
  
  **Standaardinstelling**: ingeschakeld  
  
- **Internet Explorer: beperkte zonebeveiligingswaarschuwing voor mogelijk onveilige bestanden**  
  Met deze beleidsinstelling bepaalt u of het bericht 'Bestand openen - beveiligingswaarschuwing' wordt weergegeven wanneer de gebruiker uitvoerbare bestanden of andere mogelijk onveilige bestanden (van een intranetbestandsshare met de Verkenner, bijvoorbeeld) probeert te openen. Als u deze beleidsinstelling inschakelt en de vervolgkeuzelijst instelt op Inschakelen, worden deze bestanden geopend zonder beveiligingswaarschuwing. Als u de vervolgkeuzelijst instelt op Prompt, wordt een beveiligingswaarschuwing weergegeven voordat de bestanden worden geopend. Als u deze beleidsinstelling uitschakelt, worden deze bestanden niet geopend. Als u deze beleidsinstelling niet configureert, kan de gebruiker configureren hoe de computer deze bestanden verwerkt. Standaard worden deze bestanden geblokkeerd in de beperkte zone, ingeschakeld in de zones Intranet en Lokale computer en ingesteld op Prompt in de zones Internet en Vertrouwd.
  
  **Standaard**: Uitschakelen  
  
- **Internet Explorer: XSS-filters voor internetzones**  
  Met dit beleid bepaalt u of het XSS-filter (website-overschrijdende Scripting) website-overschrijdende scriptinjecties in websites in deze zone kan detecteren en voorkomen. Als u deze beleidsinstelling inschakelt, wordt het XSS-filter ingeschakeld voor sites in deze zone en probeert het XSS-filter website-overschrijdende scriptinjecties te blokkeren. Als u deze beleidsinstelling uitschakelt, wordt het XSS-filter uitgeschakeld voor sites in deze zone en staat Internet Explorer website-overschrijdende scriptinjecties toe.
  
  **Standaardinstelling**: ingeschakeld 
  
- **Internet Explorer-terugval naar SSL3**  
  Met deze beleidsinstelling kunt u een onbeveiligde terugval naar SSL 3.0 blokkeren. Wanneer dit beleid is ingeschakeld, probeert Internet Explorer verbinding te maken met sites met behulp van SSL 3.0 of lager wanneer TLS 1.0 of hoger is mislukt. U wordt aangeraden onbeveiligde terugval niet toe te staan om een man-in-the-middle-aanval te voorkomen. Dit beleid heeft geen invloed op welke beveiligingsprotocollen worden ingeschakeld. Als u dit beleid uitschakelt, worden systeemstandaarden gebruikt.
  
  **Standaardinstelling**: Geen sites 
  
- **Internet Explorer: vergrendeld SmartScreen in internetzone**  
  Met deze beleidsinstelling bepaalt u of het SmartScreen-filter pagina's in deze zone scant op schadelijke inhoud. Als u deze beleidsinstelling inschakelt, scant het SmartScreen-filter pagina's in deze zone op schadelijke inhoud. Als u deze beleidsinstelling uitschakelt, scant het SmartScreen-filter geen pagina's in deze zone op schadelijke inhoud. Als u deze beleidsinstelling niet configureert, kan de gebruiker kiezen of het SmartScreen-filter pagina's in deze zone scant op schadelijke inhoud. Opmerking: in Internet Explorer 7 bepaalt deze beleidsinstelling of het phishing-filter pagina's in deze zone scant op schadelijke inhoud.
  
  **Standaardinstelling**: ingeschakeld 
  
- **Internet Explorer: toepassingen en bestanden in een IFRAME openen in een beperkte zone**  
  Met deze beleidsinstelling kunt u beheren of toepassingen kunnen worden uitgevoerd en of bestanden kunnen worden gedownload via een IFRAME-verwijzing in de HTML van de pagina's in deze zone. Als u deze beleidsinstelling inschakelt, kunnen gebruikers toepassingen uitvoeren en bestanden uit IFRAME's op de pagina's in deze zone downloaden zonder gebruikersinterventie. Als u Prompt selecteert in de vervolgkeuzelijst, wordt gebruikers gevraagd of ze toepassingen willen uitvoeren en bestanden willen downloaden van IFRAME's op de pagina's in deze zone. Als u deze beleidsinstelling uitschakelt, kunnen gebruikers geen toepassingen uitvoeren of bestanden downloaden van IFRAME's op de pagina's in deze zone. Als u deze beleidsinstelling niet configureert, kunnen gebruikers geen toepassingen uitvoeren of bestanden downloaden van IFRAME's op de pagina's in deze zone.
  
  **Standaard**: Uitschakelen 
  
- **SmartScreen-waarschuwingen over ongebruikelijke bestanden negeren in Internet Explorer**  
  Met deze beleidsinstelling bepaalt u of de gebruiker waarschuwingen van het SmartScreen-filter kan negeren. Het SmartScreen-filter waarschuwt de gebruiker voor uitvoerbare bestanden die Internet Explorer-gebruikers normaalgesproken niet van internet downloaden. Als u deze beleidsinstelling inschakelt, wordt de gebruiker door waarschuwingen van het SmartScreen-filter geblokkeerd. Als u deze beleidsinstelling uitschakelt of niet configureert, kan de gebruiker waarschuwingen van het SmartScreen-filter negeren.
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Internet Explorer: pop-upblokkering van internetzone**  
  Met deze beleidsinstelling kunt u beheren of ongewenste pop-upvensters worden weergegeven. Pop-upvensters die worden geopend wanneer de eindgebruiker op een koppeling klikt, worden niet geblokkeerd. Als u deze beleidsinstelling inschakelt, voorkomt u dat de meeste ongewenste pop-upvensters worden weergegeven. Als u deze beleidsinstelling uitschakelt, wordt het weergeven van pop-upvensters niet voorkomen. Als u deze beleidsinstelling niet configureert, voorkomt u dat de meeste ongewenste pop-upvensters worden weergegeven.
  
  **Standaardinstelling**: Inschakelen  
  
- **Internet Explorer: consistente MIME-verwerking met processen**  
  Internet Explorer bevat dynamisch binair gedrag: onderdelen die specifieke functionaliteit bevatten voor de HTML-elementen waaraan ze zijn gekoppeld. Met deze beleidsinstelling bepaalt u of de instelling Beveiligingsbeperkingen voor binair gedrag is verboden of is toegestaan. Als u deze beleidsinstelling inschakelt, is binair gedrag verboden voor de Bestandsverkenner en Internet Explorer-processen. Als u deze beleidsinstelling uitschakelt, is binair gedrag toegestaan voor de Bestandsverkenner en Internet Explorer-processen. Als u deze beleidsinstelling niet configureert, is binair gedrag verboden voor de Verkenner en Internet Explorer-processen.
  
  **Standaardinstelling**: ingeschakeld  
  
- **Java-machtigingen voor de beperkte zone in Internet Explorer**  
  Met deze beleidsinstelling kunt u machtigingen voor Java-applets beheren. Als u deze beleidsinstelling inschakelt, kunt u opties kiezen in de vervolgkeuzelijst. Aangepast, om instellingen voor machtigingen afzonderlijk te beheren. Met Minimale beveiliging kunnen applets alle bewerkingen uitvoeren. Met Normale beveiliging kunnen applets worden uitgevoerd in hun eigen sandbox (een gebied in het geheugen waarbuiten het programma geen aanroepen kan doen). Daarnaast biedt deze optie mogelijkheden zoals een scratchruimte (een veilig en beveiligd opslaggebied op de clientcomputer) en door de gebruiker beheerde bestandsinvoer en-uitvoer (I/O). Met Strenge beveiliging kunnen applets in hun sandbox worden uitgevoerd. Schakel Java uit om te voorkomen dat er applets worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, kunnen Java-applets niet worden uitgevoerd. Als u deze beleidsinstelling niet configureert, worden Java-applets uitgeschakeld.
  
  **Standaardinstelling**: Java uitschakelen  
    
  
- **Internet Explorer: Active X-besturingselementen in de beveiligde modus**  
  Met deze beleidsinstelling voorkomt u dat ActiveX-besturingselementen kunnen worden uitgevoerd in de beveiligde modus wanneer de uitgebreide beveiligde modus is ingeschakeld. Als een gebruiker een ActiveX-besturingselement heeft geïnstalleerd dat niet compatibel is met de uitgebreide beveiligde modus en een website het besturingselement probeert te laden, informeert Internet Explorer de gebruiker en wordt de optie geboden om de website in de gewone beschermde modus uit te voeren. <Met deze beleidsinstelling schakelt u deze melding uit en dwingt u alle websites om te worden uitgevoerd in de uitgebreide beveiligde modus. De uitgebreide beveiligde modus biedt extra bescherming tegen schadelijke websites door gebruik te maken van 64-bits processen op 64-bits versies van Windows. Op computers met minimaal Windows 8 beperkt de uitgebreide beveiligde modus ook de locaties die Internet Explorer in het register en bestandssysteem kan lezen. Als de uitgebreide beveiligde modus is ingeschakeld en een gebruiker een website bezoekt die een ActiveX-besturingselement probeert te laden die niet compatibel is met de uitgebreide beveiligde modus, informeert Internet Explorer de gebruiker en wordt de optie geboden om de uitgebreide beveiligde modus voor die specifieke website uit te schakelen. Als u deze beleidsinstelling inschakelt, biedt Internet Explorer de gebruiker niet de optie om de uitgebreide beveiligde modus uit te schakelen. Alle websites in de beveiligde modus worden uitgevoerd in de uitgebreide beveiligde modus. Als u deze beleidsinstelling uitschakelt of niet configureert, informeert Internet Explorer gebruikers en wordt een mogelijkheid geboden om websites met incompatibele ActiveX-besturingselementen uit te voeren in de gewone beveiligde modus.  
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Internet Explorer: XAML-bestanden laden in de beperkte zone**  
  Met deze beleidsinstelling kunt u het laden van XAML-bestanden (Extensible Application Markup Language) beheren. XAML is een op XML gebaseerde declaratieve opmaaktaal die veel wordt gebruikt voor het maken van uitgebreide gebruikersinterfaces en graphics waarmee gebruik kan worden gemaakt van de Windows Presentation Foundation. Als u deze beleidsinstelling inschakelt en de vervolgkeuzelijst op Inschakelen instelt, worden XAML-bestanden automatisch in Internet Explorer geladen. Gebruikers kunnen dit gedrag niet wijzigen. Als u de vervolgkeuzelijst instelt op Vragen, wordt de gebruiker gevraagd om XAML-bestanden te laden. Als u deze beleidsinstelling uitschakelt, worden XAML-bestanden niet in Internet Explorer geladen. Gebruikers kunnen dit gedrag niet wijzigen. Als u deze beleidsinstelling niet configureert, kan de gebruiker zelf bepalen of hij of zij XAML-bestanden in Internet Explorer wil laden.
  
  **Standaard**: Uitschakelen  
  
- **Internet Explorer verwerkt beveiligingsbeperkingen voor scriptvensters**  
  Internet Explorer staat scripts toe om via een programma uiteenlopende soorten vensters te openen, groter of kleiner te maken en te verplaatsen. De beveiligingsfunctie Vensterbeperkingen beperkt pop-upvensters en verbiedt scripts om vensters weer te geven waarin de titel- en statusbalk niet zichtbaar zijn voor de gebruiker of die de titel- en statusbalk van andere Windows-vensters onleesbaar maken. Als u deze beleidsinstelling inschakelt, worden scriptvensters voor alle processen beperkt. Als u deze beleidsinstelling uitschakelt of niet configureert, gelden er geen beperkingen voor scriptvensters.
  
  **Standaardinstelling**: ingeschakeld   
  
- **Active X-besturingselementen en invoegtoepassingen uitvoeren in beperkte zone van Internet Explorer**  
  Met deze beleidsinstelling kunt u beheren of ActiveX-besturingselementen en invoegtoepassingen kunnen worden uitgevoerd op de pagina's in de opgegeven zone. Als u deze beleidsinstelling inschakelt, kunnen besturingselementen en invoegtoepassingen zonder tussenkomst van de gebruiker worden uitgevoerd. Als u in de vervolgkeuzelijst Vragen hebt geselecteerd, wordt gebruikers gevraagd om te kiezen of ze de bedieningselementen of invoegtoepassing willen uitvoeren. Als u deze beleidsinstelling uitschakelt, worden de besturingselementen en invoegtoepassingen niet uitgevoerd. Als u deze beleidsinstelling niet configureert, worden de besturingselementen en invoegtoepassingen niet uitgevoerd.
  
  **Standaard**: Uitschakelen  
  
- **ActiveX-besturingselementen die als veilig zijn gemarkeerd voor het uitvoeren van scripts in de beperkte zone van Internet Explorer**  
  Met deze beleidsinstelling kunt u beheren of een ActiveX-besturingselement dat als veilig is gemarkeerd voor het uitvoeren van scripts kan communiceren met een script. Als u deze beleidsinstelling inschakelt, kunnen scripts automatisch communiceren zonder tussenkomst van de gebruiker. Als u in de vervolgkeuzelijst Vragen selecteert, moeten gebruikers kiezen of ze interactie van scripts willen toestaan. Als u deze beleidsinstelling uitschakelt, mag er geen interactie tussen scripts plaatsvinden. Als u deze beleidsinstelling niet configureert, mag er geen interactie tussen scripts plaatsvinden.
  
  **Standaard**: Uitschakelen  
  
- **Opties voor aanmelden in de beperkte zone van Internet Explorer**  
  Met deze beleidsinstelling kunt u de instellingen voor aanmeldingsopties beheren. Als u deze beleidsinstelling inschakelt, kunt u kiezen uit de volgende aanmeldingsopties. 
  - *Anoniem*: anoniem aanmelden om HTTP-verificatie uit te schakelen en het gastaccount alleen gebruiken voor het CIFS-protocol (Common Internet File System). 
  - *Vragen*: om een gebruikersnaam en wachtwoord vragen om een query te maken voor de gebruikers-id's en wachtwoorden van gebruikers. Nadat een query voor een gebruiker is uitgevoerd, kunnen deze waarden op de achtergrond worden gebruikt gedurende de rest van de sessie. 
  - *Alleen automatisch aanmelden in de intranetzone*: gebruik deze optie om een query te maken voor de gebruikers-id's en wachtwoorden in andere zones. Nadat een query voor een gebruiker is uitgevoerd, kunnen deze waarden op de achtergrond worden gebruikt gedurende de rest van de sessie. 
  - *Automatisch aanmelden met de huidige gebruikersnaam en het huidige wachtwoord*: gebruik deze optie om aanmelden te proberen met behulp van Windows NT-vraag-antwoord (ook wel NTLM-verificatie genoemd). Als de server Windows NT-vraag-antwoord ondersteunt, gebruikt de aanmelding de gebruikersnaam en het wachtwoord van de gebruiker voor het netwerk om de gebruiker aan te melden. Als Windows NT-vraag-antwoord niet door de server wordt ondersteund, wordt de gebruiker gevraagd om de gebruikersnaam en het wachtwoord op te geven. 

  Als u deze beleidsinstelling uitschakelt, wordt de aanmelding ingesteld op *Alleen automatisch aanmelden in de intranetzone*. Als u deze beleidsinstelling niet configureert, wordt de aanmelding ingesteld op *Om gebruikersnaam en wachtwoord vragen*.
  
  **Standaardinstelling**: Anoniem  
  
- **ActiveX-besturingselementen die niet als veilig zijn gemarkeerd initialiseren en als script uitvoeren in de vertrouwde zone in Internet Explorer**  
  Met deze beleidsinstelling kunt u ActiveX-besturingselementen beheren die niet als veilig zijn gemarkeerd. Als u deze beleidsinstelling inschakelt, worden ActiveX-besturingselementen uitgevoerd, voorzien van parameters en als script uitgevoerd zonder de veiligheid van objecten in te stellen voor niet-vertrouwde gegevens of scripts. Deze instelling wordt niet aanbevolen, behalve voor veilige en beheerde zones. Deze instelling zorgt dat zowel onveilige als veilige besturingselementen worden geïnitialiseerd en als script worden uitgevoerd. Daarbij worden de ActiveX-besturingselementen van het script die als veilig zijn gemarkeerd, genegeerd. Als u deze beleidsinstelling inschakelt en in de vervolgkeuzelijst Vragen selecteert, worden gebruikers gevraagd of ze willen toestaan dat het besturingselement met parameters wordt geladen of als script wordt uitgevoerd. Als u deze beleidsinstelling uitschakelt, worden ActiveX-besturingselementen die niet veilig kunnen worden ingesteld, niet geladen met parameters of als script uitgevoerd. Als u deze beleidsinstelling niet configureert, worden gebruikers gevraagd of ze willen toestaan dat het besturingselement wordt geladen met parameters of als script wordt uitgevoerd.
  
  **Standaard**: Uitschakelen  
  
- **Intrekking van servercertificaat verkennen in Internet Explorer**  
  Met deze beleidsinstelling kunt u beheren of Internet Explorer de intrekkingsstatus van servercertificaten zal controleren. Certificaten worden ingetrokken als ze zijn aangetast of niet meer geldig zijn. Deze optie beschermt gebruikers tegen het verzenden van vertrouwelijke gegevens op een website die mogelijk frauduleus of onveilig is. Als u deze beleidsinstelling inschakelt, zal Internet Explorer controleren of de servercertificaten zijn ingetrokken. Als u deze beleidsinstelling uitschakelt, wordt in Internet Explorer niet gecontroleerd of de servercertificaten zijn ingetrokken. Als u deze beleidsinstelling niet configureert, wordt in Internet Explorer niet gecontroleerd of de servercertificaten zijn ingetrokken.
  
  **Standaardinstelling**: ingeschakeld 
  
- **Internet Explorer: sites met minder machtigingen in de internetzone**  
  Met deze beleidsinstelling kunt u beheren of websites in zones met minder machtigingen, zoals beperkte websites, naar deze zone mogen navigeren. Als u deze beleidsinstelling inschakelt, kunnen websites van zones met minder machtigingen nieuwe vensters openen in, of navigeren naar, deze zone. De beveiligingszone wordt uitgevoerd zonder de toegevoegde beveiligingslaag die door de beveiliging van de beveiligingsfunctie Zoneverhoging wordt geleverd. Als u Vragen in de vervolgkeuzelijst selecteert, krijgt de gebruiker een waarschuwing dat er sprake is van mogelijk riskante navigatie. Als u deze beleidsinstelling uitschakelt, is de mogelijk schadelijke navigatie verboden. De beveiligingsfunctie van Internet Explorer is in deze zone ingeschakeld, zoals dit is ingesteld bij de functie Zone-uitbreiding. Als u deze beleidsinstelling niet configureert, kunnen websites van zones met minder bevoegdheden nieuwe vensters openen in, of navigeren naar, deze zone.
  
  **Standaard**: Uitschakelen  
  
- **Bestanden downloaden in de beperkte zone van Internet Explorer**  
  Met deze beleidsinstelling kunt u beheren of het is toegestaan om bestanden te downloaden in de zone. Deze optie wordt bepaald door de zone van de pagina met de koppeling die de download activeert, niet door de zone waarin het bestand wordt geleverd. Als u deze beleidsinstelling inschakelt, kunnen bestanden in de zone worden gedownload. Als u deze beleidsinstelling uitschakelt, wordt het downloaden van bestanden in de zone voorkomen. Als u deze beleidsinstelling niet configureert, wordt het downloaden van bestanden in de zone voorkomen.
  
  **Standaard**: Uitschakelen  
  
- **Internet Explorer: onderdelen in de internetzone uitvoeren die afhankelijk zijn van .NET Framework en zijn ondertekend met Authenticode**  
  Met deze beleidsinstelling kunt u beheren of .NET Framework-onderdelen die met Authenticode zijn ondertekend, kunnen worden uitgevoerd in Internet Explorer. Deze onderdelen bevatten beheerde besturingselementen waarnaar vanuit een objectlabel wordt verwezen en beheerde uitvoerbare bestanden waarnaar vanuit een koppeling wordt verwezen. Als u deze beleidsinstelling inschakelt, zal Internet Explorer ondertekende beheerde onderdelen uitvoeren. Als u in de vervolgkeuzelijst Vragen selecteert, wordt de gebruiker gevraagd om te bepalen of ondertekende beheerde onderdelen moeten worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, zal Internet Explorer ondertekende beheerde onderdelen niet uitvoeren. Als u deze beleidsinstelling niet configureert, worden ondertekende beheerde onderdelen niet uitgevoerd in Internet Explorer.
  
  **Standaard**: Uitschakelen  
  
- **Installatie van ActiveX-besturingselementen per gebruiker voorkomen in Internet Explorer**  
  Met deze beleidsinstelling kunt u voorkomen dat per gebruiker ActiveX-besturingselementen worden geïnstalleerd. Als u deze beleidsinstelling inschakelt, kunnen er geen ActiveX-besturingselementen per gebruiker worden geïnstalleerd. Als u deze beleidsinstelling uitschakelt of niet configureert, kunnen er ActiveX-besturingselementen per gebruiker worden geïnstalleerd.
  
  **Standaardinstelling**: ingeschakeld  
  
- **Beheer van het SmartScreen-filter voorkomen in Internet Explorer**  
  Met deze beleidsinstelling voorkomt u dat de gebruiker SmartScreen Filter kan beheren, waarmee de gebruiker wordt gewaarschuwd als de website die wordt bezocht bekend staat om frauduleuze pogingen om persoonlijke gegevens te verzamelen via phishing of om het hosten van malware. Als u deze beleidsinstelling inschakelt, wordt de gebruiker niet gevraagd om het SmartScreen-filter in te schakelen. Alle websiteadressen die niet op de toegestane lijst van het filter staan, worden automatisch naar Microsoft verzonden zonder dat de gebruiker wordt gevraagd. Als u deze beleidsinstelling niet uitschakelt of configureert, wordt de gebruiker gevraagd om te bepalen of het SmartScreen-filter moet worden ingeschakeld tijdens de eerste uitvoersessie.
  
  **Standaardinstelling**: Inschakelen  
  
- **Internet Explorer verwerkt de veiligheidsfunctie MIME-sniffing**  
  Met deze beleidsinstelling wordt bepaald of Internet Explorer MIME-sniffing het niveau verhogen voorkomt van een bestand van het ene type naar een meer gevaarlijk bestandstype. Als u deze beleidsinstelling inschakelt, wordt bij MIME-sniffing nooit het niveau van een bestand van het ene type naar een meer gevaarlijk bestandstype verhoogd. Als u deze beleidsinstelling uitschakelt, kunnen Internet Explorer-processen toestaan dat bij MIME-sniffing het niveau van een bestand van het ene type naar een meer gevaarlijk bestandstype wordt verhoogd. Als u deze beleidsinstelling niet configureert, wordt bij MIME-sniffing nooit het niveau van een bestand van het ene type naar een meer gevaarlijk bestandstype verhoogd.
  
  **Standaardinstelling**: ingeschakeld  
  
- **Internet Explorer: ondertekende Active X-besturingselementen downloaden in de beperkte zone**  
  Met deze beleidsinstelling kunt u beheren of gebruikers ondertekende ActiveX-besturingselementen van een pagina in de zone kunnen downloaden. Als u dit beleid inschakelt, kunnen gebruikers ondertekende besturingselementen downloaden zonder tussenkomst van de gebruiker. Als u Vragen selecteert in de vervolgkeuzelijst, wordt aan gebruikers gevraagd of ze besturingselementen willen downloaden die zijn ondertekend door niet-vertrouwde uitgevers. Code die is ondertekend door vertrouwde uitgevers wordt op de achtergrond gedownload. Als u de beleidsinstelling uitschakelt, kunnen ondertekende besturingselementen niet worden gedownload. Als u deze beleidsinstelling niet configureert, wordt aan gebruikers gevraagd of ze besturingselementen willen downloaden die zijn ondertekend door niet-vertrouwde uitgevers. Code die is ondertekend door vertrouwde uitgevers wordt op de achtergrond gedownload.
  
  **Standaard**: Uitschakelen  
  
- **Internet Explorer: automatisch aanvullen**  
  Met de functie Automatisch aanvullen worden gebruikersnamen en wachtwoorden in formulieren onthouden en voorgesteld. Als u deze instelling inschakelt, kan de gebruiker opties voor gebruikersnaam en wachtwoorden op formulieren of vragen om wachtwoorden op te slaan niet wijzigen. De functie Automatisch aanvullen voor gebruikersnamen en wachtwoorden in formulieren is ingeschakeld. U moet bepalen of u de optie voor vragen om wachtwoorden op te slaan wilt inschakelen. Als u deze instelling uitschakelt, kan de gebruiker de opties Gebruikersnaam en wachtwoorden op formulieren en vragen om wachtwoorden op te slaan niet wijzigen. De functie Automatisch aanvullen voor gebruikersnamen en wachtwoorden in formulieren is ingeschakeld. De gebruiker kan ook niet kiezen om te worden gevraagd wachtwoorden op te slaan. Als u deze instelling niet configureert, heeft de gebruiker de vrijheid om Automatische aanvullen voor gebruikersnamen en wachtwoorden in formulieren en de optie voor vragen om wachtwoorden op te slaan in te schakelen. Om deze optie weer te geven, openen gebruikers het dialoogvenster Internetopties, klikken ze op het tabblad Inhoud en klikken ze op de knop Instellingen.
  
  **Standaard**: Uitschakelen  
  
- **Internet Explorer: toestaan om VBscript uit te voeren in de internetzone**  
  Met deze beleidsinstelling kunt u beslissen of VBScript mag worden uitgevoerd op pagina's in specifieke Internet Explorer-zones. Opties zijn onder andere: 
  - *Inschakelen*: er wordt VBScript uitgevoerd op pagina's in specifieke zones, zonder enige tussenkomst. 
  - *Vragen*: werknemers wordt gevraagd of ze willen toestaan dat VBScript wordt uitgevoerd in de zone. 
  - *Uitschakelen*: er wordt voorkomen dat VBScript wordt uitgevoerd in de zone. Als u deze beleidsinstelling uitschakelt of niet configureert, wordt VBScript in de opgegeven zone uitgevoerd zonder enige tussenkomst. 
  
  **Standaard**: Uitschakelen  
  
- **Internet Explorer: alleen goedgekeurde domeinen mogen TDC Active X-besturingselementen gebruiken in de beperkt zone**  
  Met deze beleidsinstelling bepaalt u of de gebruiker het TDC ActiveX-besturingselement op websites kan uitvoeren. Als u deze beleidsinstelling inschakelt, wordt het TDC ActiveX-besturingselement niet uitgevoerd vanaf websites in deze zone. Als u deze beleidsinstelling uitschakelt, wordt het TDC ActiveX-besturingselement uitgevoerd vanaf alle sites in deze zone.
  
  **Standaardinstelling**: ingeschakeld  
  
- **Er wordt geen antimalware uitgevoerd op ActiveX-besturingselementen in de vertrouwde zone van Internet Explorer**  
  Met deze beleidsinstelling wordt bepaald of Internet Explorer antimalwareprogramma's uitvoert op ActiveX-besturingselementen om te controleren of ze veilig zijn om te laden op pagina's. Als u deze beleidsinstelling inschakelt, controleert Internet Explorer niet met uw antimalware-programma om te zien of het veilig is om een exemplaar van het ActiveX-besturingselement te installeren. Als u deze beleidsinstelling uitschakelt, controleert Internet Explorer altijd met uw antimalware-programma om te zien of het veilig is om een exemplaar van het ActiveX-besturingselement te installeren. Als u deze beleidsinstelling niet configureert, controleert Internet Explorer altijd met uw antimalware-programma om te zien of het veilig is om een exemplaar van het ActiveX-besturingselement te installeren. Gebruikers kunnen dit gedrag in- of uitschakelen met de beveiligingsinstellingen van Internet Explorer.
  
  **Standaardinstelling**: uitgeschakeld 
  
- **Internet Explorer: Java-machtigingen voor de zone Lokale machine**  
  Met deze beleidsinstelling kunt u machtigingen voor Java-applets beheren. Als u deze beleidsinstelling inschakelt, kunt u opties kiezen in de vervolgkeuzelijst. Aangepast, om instellingen voor machtigingen afzonderlijk te beheren. Met Minimale beveiliging kunnen applets alle bewerkingen uitvoeren. Met Normale beveiliging kunnen applets worden uitgevoerd in hun eigen sandbox (een gebied in het geheugen waarbuiten het programma geen aanroepen kan doen). Daarnaast biedt deze optie mogelijkheden zoals een scratchruimte (een veilig en beveiligd opslaggebied op de clientcomputer) en door de gebruiker beheerde bestandsinvoer en-uitvoer (I/O). Met Strenge beveiliging kunnen applets in hun sandbox worden uitgevoerd. Schakel Java uit om te voorkomen dat er applets worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, kunnen Java-applets niet worden uitgevoerd. Als u deze beleidsinstelling niet configureert, wordt de machtiging ingesteld op Normale beveiliging.
  
  **Standaardinstelling**: Java uitschakelen 
  
- **Internet Explorer: er wordt geen antimalware uitgevoerd op ActiveX-besturingselementen in de intranetzone**: met deze beleidsinstelling wordt bepaald of Internet Explorer antimalwareprogramma's uitvoert op ActiveX-besturingselementen om te controleren of ze veilig zijn om te laden op pagina's. Als u deze beleidsinstelling inschakelt, controleert Internet Explorer niet met uw antimalware-programma om te zien of het veilig is om een exemplaar van het ActiveX-besturingselement te installeren. Als u deze beleidsinstelling uitschakelt, controleert Internet Explorer altijd met uw antimalware-programma om te zien of het veilig is om een exemplaar van het ActiveX-besturingselement te installeren. Als u deze beleidsinstelling niet configureert, controleert Internet Explorer niet met uw antimalware-programma om te zien of het veilig is om een exemplaar van het ActiveX-besturingselement te installeren. Gebruikers kunnen dit gedrag in- of uitschakelen met de beveiligingsinstellingen van Internet Explorer.
  
  **Standaardinstelling**: uitgeschakeld  

- **Internet Explorer: scriptlets in de beperkte zone**  
  Met deze beleidsinstelling kunt u beheren of gebruikers scriptlets kunnen uitvoeren. Als u deze beleidsinstelling inschakelt, kan de gebruiker scriptlets uitvoeren. Als u deze beleidsinstelling uitschakelt, kan de gebruiker geen scriptlets uitvoeren. Als u deze beleidsinstelling niet configureert, kan de gebruiker scriptlets in- of uitschakelen.
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Internet Explorer: meldingsbalk voor processen**  
  Met deze beleidsinstelling kunt u beheren of de meldingsbalk voor Internet Explorer-processen wordt weergegeven als de installatie van bestanden of code wordt beperkt. De meldingsbalk wordt standaard weergegeven voor Internet Explorer-processen. Als u deze beleidsinstelling inschakelt, wordt de meldingsbalk weergegeven voor de Internet Explorer-processen. Als u deze beleidsinstelling uitschakelt, wordt de meldingsbalk niet weergegeven voor Internet Explorer-processen. Als u deze beleidsinstelling niet configureert, wordt de meldingsbalk niet weergegeven voor Internet Explorer-processen.
  
  **Standaardinstelling**: ingeschakeld  
  
- **Internet Explorer: ondertekende Active X-besturingselementen downloaden in internetzone**  
  Met deze beleidsinstelling kunt u beheren of gebruikers ondertekende ActiveX-besturingselementen van een pagina in de zone kunnen downloaden. Als u dit beleid inschakelt, kunnen gebruikers ondertekende besturingselementen downloaden zonder tussenkomst van de gebruiker. Als u Vragen selecteert in de vervolgkeuzelijst, wordt aan gebruikers gevraagd of ze besturingselementen willen downloaden die zijn ondertekend door niet-vertrouwde uitgevers. Code die is ondertekend door vertrouwde uitgevers wordt op de achtergrond gedownload. Als u de beleidsinstelling uitschakelt, kunnen ondertekende besturingselementen niet worden gedownload. Als u deze beleidsinstelling niet configureert, wordt aan gebruikers gevraagd of ze besturingselementen willen downloaden die zijn ondertekend door niet-vertrouwde uitgevers. Code die is ondertekend door vertrouwde uitgevers wordt op de achtergrond gedownload.
  
  **Standaard**: Uitschakelen  
  
- **Internet Explorer: SmartScreen in de beperkte zone**  
  Met deze beleidsinstelling bepaalt u of het SmartScreen-filter pagina's in deze zone scant op schadelijke inhoud. Als u deze beleidsinstelling inschakelt, scant het SmartScreen-filter pagina's in deze zone op schadelijke inhoud. Als u deze beleidsinstelling uitschakelt, scant het SmartScreen-filter geen pagina's in deze zone op schadelijke inhoud. Als u deze beleidsinstelling niet configureert, kan de gebruiker kiezen of het SmartScreen-filter pagina's in deze zone scant op schadelijke inhoud. Opmerking: in Internet Explorer 7 bepaalt deze beleidsinstelling of het phishing-filter pagina's in deze zone scant op schadelijke inhoud.
  
  **Standaardinstelling**: ingeschakeld  
  
- **Internet Explorer: de knop Deze keer uitvoeren verwijderen voor verouderde ActiveX-besturingselementen**  
  Met deze beleidsinstelling kunt u voorkomen dat gebruikers de knop Deze keer uitvoeren zien en specifieke verouderde ActiveX-besturingselementen in Internet Explorer uitvoeren. Als u deze beleidsinstelling inschakelt, zien gebruikers de knop Deze keer uitvoeren niet in het waarschuwingsbericht dat wordt weergegeven als Internet Explorer een verouderd ActiveX-besturingselement blokkeert. Als u deze beleidsinstelling uitschakelt of niet configureert, zien gebruikers de knop Deze keer uitvoeren in het waarschuwingsbericht dat wordt weergegeven als Internet Explorer een verouderd ActiveX-besturingselement blokkeert. Als de gebruiker op deze knop klikt, wordt het verouderde ActiveX-besturingselement eenmaal uitgevoerd. Zie Verouderde ActiveX-besturingselementen in de Internet Explorer TechNet-bibliotheek voor meer informatie.
  
  **Standaardinstelling**: ingeschakeld 
  
- **Internet Explorer: toepassingen en bestanden in een IFRAME openen in een internetzone**  
  Met deze beleidsinstelling kunt u beheren of toepassingen kunnen worden uitgevoerd en of bestanden kunnen worden gedownload via een IFRAME-verwijzing in de HTML van de pagina's in deze zone. Als u deze beleidsinstelling inschakelt, kunnen gebruikers toepassingen uitvoeren en bestanden uit IFRAME's op de pagina's in deze zone downloaden zonder gebruikersinterventie. Als u Prompt selecteert in de vervolgkeuzelijst, wordt gebruikers gevraagd of ze toepassingen willen uitvoeren en bestanden willen downloaden van IFRAME's op de pagina's in deze zone. Als u deze beleidsinstelling uitschakelt, kunnen gebruikers geen toepassingen uitvoeren of bestanden downloaden van IFRAME's op de pagina's in deze zone. Als u deze beleidsinstelling niet configureert, wordt gebruikers gevraagd of ze toepassingen willen uitvoeren en bestanden willen downloaden van IFRAME's op de pagina's in deze zone
  
  **Standaard**: Uitschakelen 
  
- **Vensters en frames door verschillende domeinen laten navigeren in de beperkte zone in Internet Explorer**  
  Met deze beleidsinstelling kunt u opties instellen voor het verslepen van inhoud van het ene naar het andere domein wanneer de bron en de bestemming zich in verschillende vensters bevinden. Als u deze beleidsinstelling inschakelt en op Inschakelen klikt, kunnen gebruikers inhoud van het ene naar het andere domein verslepen wanneer de bron en de bestemming zich in verschillende vensters bevinden. Gebruikers kunnen deze instelling niet wijzigen. Als u deze beleidsinstelling inschakelt en op Uitschakelen klikt, kunnen gebruikers geen inhoud van het ene naar het andere domein verslepen als de bron en de bestemming zich in verschillende vensters bevinden. Gebruikers kunnen deze instelling niet wijzigen. Als u deze beleidsinstelling in Internet Explorer 10 uitschakelt of niet configureert, kunnen gebruikers geen inhoud van het ene naar het andere domein verslepen wanneer de bron en de bestemming zich in verschillende vensters bevinden. Gebruikers kunnen deze instelling wijzigen in het dialoogvenster Internetopties. Als u dit beleid in Internet Explorer 9 en eerdere versies uitschakelt of niet configureert, kunnen gebruikers inhoud van het ene naar het andere domein verslepen als de bron en de bestemming zich in verschillende vensters bevinden. Gebruikers kunnen deze instelling niet wijzigen.
  
  **Standaard**: Uitschakelen  
  
- **Internet Explorer: SmartScreen van internetzone**  
  Met deze beleidsinstelling bepaalt u of het SmartScreen-filter pagina's in deze zone scant op schadelijke inhoud. Als u deze beleidsinstelling inschakelt, scant het SmartScreen-filter pagina's in deze zone op schadelijke inhoud. Als u deze beleidsinstelling uitschakelt, scant het SmartScreen-filter geen pagina's in deze zone op schadelijke inhoud. Als u deze beleidsinstelling niet configureert, kan de gebruiker kiezen of het SmartScreen-filter pagina's in deze zone scant op schadelijke inhoud. Opmerking: in Internet Explorer 7 bepaalt deze beleidsinstelling of het phishing-filter pagina's in deze zone scant op schadelijke inhoud.
  
  **Standaardinstelling**: ingeschakeld  
  
- **Java-machtigingen voor de vertrouwde zone zijn vergrendeld in Internet Explorer**  
  Met deze beleidsinstelling kunt u machtigingen voor Java-applets beheren. Als u deze beleidsinstelling inschakelt, kunt u opties kiezen in de vervolgkeuzelijst. Aangepast, om instellingen voor machtigingen afzonderlijk te beheren. Met Minimale beveiliging kunnen applets alle bewerkingen uitvoeren. Met Normale beveiliging kunnen applets worden uitgevoerd in hun eigen sandbox (een gebied in het geheugen waarbuiten het programma geen aanroepen kan doen). Daarnaast biedt deze optie mogelijkheden zoals een scratchruimte (een veilig en beveiligd opslaggebied op de clientcomputer) en door de gebruiker beheerde bestandsinvoer en-uitvoer (I/O). Met Strenge beveiliging kunnen applets in hun sandbox worden uitgevoerd. Schakel Java uit om te voorkomen dat er applets worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, kunnen Java-applets niet worden uitgevoerd. Als u deze beleidsinstelling niet configureert, worden Java-applets uitgeschakeld.
  
  **Standaardinstelling**: Java uitschakelen 
  
- **Internet Explorer: handtekeningen controleren voor gedownloade programma's**  
  Met deze beleidsinstelling kunt u beheren of Internet Explorer digitale handtekeningen (met daarin de naam van de uitgever van ondertekende software, ter verificatie dat de software niet is gewijzigd of gesaboteerd) op computers van gebruikers controleert voordat uitvoerbare bestanden worden gedownload. Als u deze beleidsinstelling inschakelt, zal Internet Explorer de digitale handtekeningen van uitvoerbare programma's controleren en hun identiteit weergeven voordat ze op computers van gebruikers worden gedownload. Als u deze beleidsinstelling uitschakelt, worden in Internet Explorer de digitale handtekeningen van uitvoerbare programma's niet gecontroleerd en wordt hun identiteit niet weergeven voordat ze op computers van gebruikers worden gedownload. Als u dit beleid niet configureert, worden in Internet Explorer de digitale handtekeningen van uitvoerbare programma's niet gecontroleerd en wordt hun identiteit niet weergeven voordat ze op computers van gebruikers worden gedownload.
  
  **Standaardinstelling**: ingeschakeld  
  
- **Scripts uitvoeren van webbrowserbesturingselementen in de beperkte zone van Internet Explorer**  
  Met deze beleidsinstelling bepaalt u of op een pagina ingesloten webbrowserbesturingselementen via een script kunnen worden beheerd. Als u deze beleidsinstelling inschakelt, is scripttoegang tot het webbrowserbesturingselement toegestaan. Als u deze beleidsinstelling uitschakelt, is scripttoegang tot het webbrowserbesturingselement niet toegestaan. Als u deze beleidsinstelling niet configureert, kan de gebruiker scripttoegang tot het webbrowserbesturingselement in- of uitschakelen. Standaard is scripttoegang tot het besturingselement WebBrowser alleen toegestaan in de lokale computer en intranetzones.
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Internet Explorer: XSS-filters voor beperkte zones**  
  Met dit beleid bepaalt u of het XSS-filter (website-overschrijdende Scripting) website-overschrijdende scriptinjecties in websites in deze zone kan detecteren en voorkomen. Als u deze beleidsinstelling inschakelt, wordt het XSS-filter ingeschakeld voor sites in deze zone en probeert het XSS-filter website-overschrijdende scriptinjecties te blokkeren. Als u deze beleidsinstelling uitschakelt, wordt het XSS-filter uitgeschakeld voor sites in deze zone en staat Internet Explorer website-overschrijdende scriptinjecties toe.
  
  **Standaardinstelling**: ingeschakeld  
  
- **Internet Explorer: binair gedrag en scriptgedrag in beperkte zones**  
  Met deze beleidsinstelling kunt u dynamische binaire gedragingen en scriptgedrag beheren: onderdelen die specifieke functionaliteit bevatten voor HTML-elementen waaraan ze zijn gekoppeld. Als u deze beleidsinstelling inschakelt, zijn binair gedrag en scriptgedrag beschikbaar. Als u in de vervolgkeuzelijst Goedgekeurd door beheerder selecteert, is alleen gedrag beschikbaar dat staat vermeld in het door de beheerder goedgekeurde gedrag onder het beveiligingsbeperkingsbeleid Binair gedrag. Als u deze beleidsinstelling uitschakelt, zijn binair gedrag en scriptgedrag niet beschikbaar tenzij voor toepassingen aangepast beveiligingsbeheer is geïmplementeerd. Als u deze beleidsinstelling niet configureert, zijn binair gedrag en scriptgedrag niet beschikbaar tenzij voor toepassingen aangepast beveiligingsbeheer is geïmplementeerd.
  
  **Standaard**: Uitschakelen  
  
- **Internet Explorer: beveiligingsinstellingen controleren**  
  Met deze beleidsinstelling schakelt u de functie Controle van beveiligingsinstellingen uit. met deze functie controleert u de beveiligingsinstellingen in Internet Explorer om vast te stellen wanneer de instellingen een risico vormen voor Internet Explorer. Als u deze beleidsinstelling inschakelt, wordt de functie uitgeschakeld. Als u deze beleidsinstelling uitschakelt of niet configureert, wordt de functie ingeschakeld.
  
  **Standaardinstelling**: ingeschakeld  
  
- **Internet Explorer: beveiligingswaarschuwing voor mogelijk onveilige bestanden in de internetzone**  
  Met deze beleidsinstelling bepaalt u of het bericht 'Bestand openen - beveiligingswaarschuwing' wordt weergegeven wanneer de gebruiker uitvoerbare bestanden of andere mogelijk onveilige bestanden (van een intranetbestandsshare met de Verkenner, bijvoorbeeld) probeert te openen. Als u deze beleidsinstelling inschakelt en de vervolgkeuzelijst instelt op Inschakelen, worden deze bestanden geopend zonder beveiligingswaarschuwing. Als u de vervolgkeuzelijst instelt op Prompt, wordt een beveiligingswaarschuwing weergegeven voordat de bestanden worden geopend. Als u deze beleidsinstelling uitschakelt, worden deze bestanden niet geopend. Als u deze beleidsinstelling niet configureert, kan de gebruiker configureren hoe de computer deze bestanden verwerkt. Standaard worden deze bestanden geblokkeerd in de beperkte zone, ingeschakeld in de zones Intranet en Lokale computer en ingesteld op Prompt in de zones Internet en Vertrouwd.
  
  **Standaardinstelling**: Vragen  
  
- **Java-machtigingen voor de intranetzone in Internet Explorer**  
  Met deze beleidsinstelling kunt u machtigingen voor Java-applets beheren. Als u deze beleidsinstelling inschakelt, kunt u opties kiezen in de vervolgkeuzelijst. Aangepast, om instellingen voor machtigingen afzonderlijk te beheren. Met Minimale beveiliging kunnen applets alle bewerkingen uitvoeren. Met Normale beveiliging kunnen applets worden uitgevoerd in hun eigen sandbox (een gebied in het geheugen waarbuiten het programma geen aanroepen kan doen). Daarnaast biedt deze optie mogelijkheden zoals een scratchruimte (een veilig en beveiligd opslaggebied op de clientcomputer) en door de gebruiker beheerde bestandsinvoer en-uitvoer (I/O). Met Strenge beveiliging kunnen applets in hun sandbox worden uitgevoerd. Schakel Java uit om te voorkomen dat er applets worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, kunnen Java-applets niet worden uitgevoerd. Als u deze beleidsinstelling niet configureert, wordt de machtiging ingesteld op Normale beveiliging.
  
  **Standaardinstelling**: Hoge beveiliging 
  
- **Internet Explorer: verouderde ActiveX-besturingselementen blokkeren**  </br>
  Met deze beleidsinstelling bepaalt u of Internet Explorer bepaalde verouderde ActiveX-besturingselementen blokkeert. Verouderde ActiveX-besturingselementen worden nooit geblokkeerd in de intranetzone. Als u deze beleidsinstelling inschakelt, stopt Internet Explorer met het blokkeren van verouderde ActiveX-besturingselementen. Als u deze beleidsinstelling uitschakelt of niet configureert, blijft Internet Explorer bepaalde verouderde ActiveX-besturingselementen blokkeren. Zie Verouderde ActiveX-besturingselementen in de Internet Explorer TechNet-bibliotheek voor meer informatie.
  
  **Standaardinstelling**: ingeschakeld  
  
- **Pop-upblokkering in de beperkte zone van Internet Explorer**  
  Met deze beleidsinstelling kunt u beheren of ongewenste pop-upvensters worden weergegeven. Pop-upvensters die worden geopend wanneer de eindgebruiker op een koppeling klikt, worden niet geblokkeerd. Als u deze beleidsinstelling inschakelt, voorkomt u dat de meeste ongewenste pop-upvensters worden weergegeven. Als u deze beleidsinstelling uitschakelt, wordt het weergeven van pop-upvensters niet voorkomen. Als u deze beleidsinstelling niet configureert, voorkomt u dat de meeste ongewenste pop-upvensters worden weergegeven.
  
  **Standaardinstelling**: Inschakelen  
  
- **Internet Explorer verwerkt beveiligingsbeperkingen voor het MK-protocol**  
  De beleidsinstelling Beveiligingsbeperking voor het MK-protocol vermindert het beveiligingsrisico door het MK-protocol te voorkomen. Resources die op het MK-protocol worden gehost, zullen mislukken. Als u deze beleidsinstelling inschakelt, wordt het MK-protocol voorkomen voor Verkenner en Internet Explorer en mislukken resources die op het MK-protocol worden gehost. Als u deze beleidsinstelling uitschakelt, kunnen toepassingen de API voor het MK-protocol gebruiken. Resources die op het MK-protocol worden gehost, werken voor de processen in Verkenner en Internet Explorer. Als u deze beleidsinstelling niet configureert, wordt het MK-protocol voorkomen voor de Verkenner en Internet Explorer en mislukken resources die op het MK-protocol worden gehost.
  
  **Standaardinstelling**: ingeschakeld  
  
- **Java-machtigingen voor de vertrouwde zone in Internet Explorer**  </br>
  Met deze beleidsinstelling kunt u machtigingen voor Java-applets beheren. Als u deze beleidsinstelling inschakelt, kunt u opties kiezen in de vervolgkeuzelijst. Aangepast, om instellingen voor machtigingen afzonderlijk te beheren. Met Minimale beveiliging kunnen applets alle bewerkingen uitvoeren. Met Normale beveiliging kunnen applets worden uitgevoerd in hun eigen sandbox (een gebied in het geheugen waarbuiten het programma geen aanroepen kan doen). Daarnaast biedt deze optie mogelijkheden zoals een scratchruimte (een veilig en beveiligd opslaggebied op de clientcomputer) en door de gebruiker beheerde bestandsinvoer en-uitvoer (I/O). Met Strenge beveiliging kunnen applets in hun sandbox worden uitgevoerd. Schakel Java uit om te voorkomen dat er applets worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, kunnen Java-applets niet worden uitgevoerd. Als u deze beleidsinstelling niet configureert, wordt de machtiging ingesteld op Lage veiligheid.
  
  **Standaardinstelling**: Hoge beveiliging  
  
- **Internet Explorer: scripts voor Java-applets uitvoeren in de beperkte zone**  
  Met deze beleidsinstelling kunt u beheren of applets beschikbaar worden gemaakt voor scripts in de zone. Als u deze beleidsinstelling inschakelt, hebben scripts automatisch toegang tot applets zonder tussenkomst van de gebruiker. Als u in de vervolgkeuzelijst Vragen selecteert, moeten gebruikers kiezen of ze scripts toegang tot applets willen bieden. Als u deze beleidsinstelling uitschakelt, hebben scripts geen toegang tot applets. Als u deze beleidsinstelling niet configureert, hebben scripts geen toegang tot applets.
  
  **Standaard**: Uitschakelen  
  
- **Java-machtigingen voor de beperkte zone zijn vergrendeld in Internet Explorer**  </br>
  Met deze beleidsinstelling kunt u machtigingen voor Java-applets beheren. Als u deze beleidsinstelling inschakelt, kunt u opties kiezen in de vervolgkeuzelijst. Aangepast, om instellingen voor machtigingen afzonderlijk te beheren. Met Minimale beveiliging kunnen applets alle bewerkingen uitvoeren. Met Normale beveiliging kunnen applets worden uitgevoerd in hun eigen sandbox (een gebied in het geheugen waarbuiten het programma geen aanroepen kan doen). Daarnaast biedt deze optie mogelijkheden zoals een scratchruimte (een veilig en beveiligd opslaggebied op de clientcomputer) en door de gebruiker beheerde bestandsinvoer en-uitvoer (I/O). Met Strenge beveiliging kunnen applets in hun sandbox worden uitgevoerd. Schakel Java uit om te voorkomen dat er applets worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, kunnen Java-applets niet worden uitgevoerd. Als u deze beleidsinstelling niet configureert, worden Java-applets uitgeschakeld.
  
  **Standaardinstelling**: Java uitschakelen 
  
- **Internet Explorer: alleen goedgekeurde domeinen in de internetzone toestaan om ActiveX-besturingselementen te gebruiken**  </br>
  Met deze beleidsinstelling bepaalt u of de gebruiker wordt gevraagd om toe te staan dat ActiveX-besturingselementen op andere websites worden uitgevoerd dan de website waarop het ActiveX-besturingselement is geïnstalleerd. Als u deze beleidsinstelling inschakelt, wordt de gebruiker vooraf gevraagd of het ActiveX-besturingselement mag worden uitgevoerd vanaf websites in deze zone. De gebruiker kan ervoor kiezen dat het besturingselement vanaf de huidige site of vanaf alle sites kan worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, krijgt de gebruiker niet de sitespecifieke ActiveX-melding te zien en kunnen ActiveX-besturingselementen worden uitgevoerd vanaf alle sites in deze zone.
  
  **Standaardinstelling**: ingeschakeld  
  
- **Internet Explorer: alle netwerkpaden opnemen**  
  Internet Explorer: alle netwerkpaden opnemen
  
  **Standaardinstelling**: uitgeschakeld 
  
- **Internet Explorer: beveiligde modus van internetzone**  
  Met deze beleidsinstelling kunt u de functie Beveiligde modus inschakelen. Met behulp van Beveiligde modus kunt u Internet Explorer beschermen tegen misbruikte zwakke plekken door het aantal locaties te verminderen waarnaar Internet Explorer in het register en het bestandssysteem kan schrijven. Als u deze beleidsinstelling inschakelt, wordt Beveiligde modus ingeschakeld. De gebruiker kan Beveiligde modus niet uitschakelen. Als u deze beleidsinstelling uitschakelt, wordt Beveiligde modus uitgeschakeld. De gebruiker kan Beveiligde modus niet inschakelen. Als u deze beleidsinstelling niet configureert, kan de gebruiker Beschermde modus in- of uitschakelen.
  
  **Standaardinstelling**: Inschakelen 
  
- **ActiveX-besturingselementen die niet als veilig zijn gemarkeerd initialiseren en als script uitvoeren in de internetzone in Internet Explorer**  
  Met deze beleidsinstelling kunt u ActiveX-besturingselementen beheren die niet als veilig zijn gemarkeerd. Als u deze beleidsinstelling inschakelt, worden ActiveX-besturingselementen uitgevoerd, voorzien van parameters en als script uitgevoerd zonder de veiligheid van objecten in te stellen voor niet-vertrouwde gegevens of scripts. Deze instelling wordt niet aanbevolen, behalve voor veilige en beheerde zones. Deze instelling zorgt dat zowel onveilige als veilige besturingselementen worden geïnitialiseerd en als script worden uitgevoerd. Daarbij worden de ActiveX-besturingselementen van het script die als veilig zijn gemarkeerd, genegeerd. Als u deze beleidsinstelling inschakelt en in de vervolgkeuzelijst Vragen selecteert, worden gebruikers gevraagd of ze willen toestaan dat het besturingselement met parameters wordt geladen of als script wordt uitgevoerd. Als u deze beleidsinstelling uitschakelt, worden ActiveX-besturingselementen die niet veilig kunnen worden ingesteld, niet geladen met parameters of als script uitgevoerd. Als u deze beleidsinstelling niet configureert, worden ActiveX-besturingselementen die niet veilig kunnen worden ingesteld, niet geladen met parameters of als script uitgevoerd.
  
  **Standaard**: Uitschakelen 
  
- **Internet Explorer: vergrendeld SmartScreen in beperkte zone**  </br>
  Met deze beleidsinstelling bepaalt u of het SmartScreen-filter pagina's in deze zone scant op schadelijke inhoud. Als u deze beleidsinstelling inschakelt, scant het SmartScreen-filter pagina's in deze zone op schadelijke inhoud. Als u deze beleidsinstelling uitschakelt, scant het SmartScreen-filter geen pagina's in deze zone op schadelijke inhoud. Als u deze beleidsinstelling niet configureert, kan de gebruiker kiezen of het SmartScreen-filter pagina's in deze zone scant op schadelijke inhoud. Opmerking: in Internet Explorer 7 bepaalt deze beleidsinstelling of het phishing-filter pagina's in deze zone scant op schadelijke inhoud.
  
  **Standaardinstelling**: ingeschakeld  
  
- **Detectie van Internet Explorer-crashes**  
  Met deze beleidsinstelling kunt u de functie voor het detecteren van crashes in het beheer van invoegtoepassingen beheren. Als u deze beleidsinstelling inschakelt, zal een crash in Internet Explorer het gedrag vertonen dat in Windows XP Professional Servicepack 1 en oudere versies werd waargenomen en Windows Foutrapportage aanroepen. Alle beleidsinstellingen voor Windows Foutrapportage blijven van toepassing. Als u deze beleidsinstelling uitschakelt of niet configureert, is de functie voor het detecteren van crashes in het beheer van invoegtoepassingen actief.
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Java-machtigingen voor de internetzone in Internet Explorer**  
  Met deze beleidsinstelling kunt u machtigingen voor Java-applets beheren. Als u deze beleidsinstelling inschakelt, kunt u opties kiezen in de vervolgkeuzelijst. Aangepast, om instellingen voor machtigingen afzonderlijk te beheren. Met Minimale beveiliging kunnen applets alle bewerkingen uitvoeren. Met Normale beveiliging kunnen applets worden uitgevoerd in hun eigen sandbox (een gebied in het geheugen waarbuiten het programma geen aanroepen kan doen). Daarnaast biedt deze optie mogelijkheden zoals een scratchruimte (een veilig en beveiligd opslaggebied op de clientcomputer) en door de gebruiker beheerde bestandsinvoer en-uitvoer (I/O). Met Strenge beveiliging kunnen applets in hun sandbox worden uitgevoerd. Schakel Java uit om te voorkomen dat er applets worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, kunnen Java-applets niet worden uitgevoerd. Als u deze beleidsinstelling niet configureert, wordt de machtiging ingesteld op Hoge veiligheid.
  
  **Standaardinstelling**: Java uitschakelen  
  
- **Actieve scripts in de beperkte zone van Internet Explorer**  
  Met deze beleidsinstelling kunt u beheren of scriptcode op pagina's in de zone wordt uitgevoerd. Als u deze beleidsinstelling inschakelt, kan scriptcode op pagina's in de zone automatisch worden uitgevoerd. Als u in de vervolgkeuzelijst Vragen selecteert, moeten gebruikers kiezen of ze willen toestaan dat scripts op pagina's in de zone worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, kan scriptcode op pagina's in de zone niet worden uitgevoerd. Als u deze beleidsinstelling niet configureert, kan scriptcode op pagina's in de zone niet worden uitgevoerd.
  
  **Standaard**: Uitschakelen  
  
- **Internet Explorer: aanmeldingsopties voor internetzones**  
  Met deze beleidsinstelling kunt u de instellingen voor aanmeldingsopties beheren. Als u deze beleidsinstelling inschakelt, kunt u kiezen uit de volgende aanmeldingsopties. Anoniem aanmelden om HTTP-verificatie uit te schakelen en het gastaccount alleen gebruiken voor het CIFS-protocol (Common Internet File System). Om een gebruikersnaam en wachtwoord vragen om een query te maken voor de gebruikers-id's en wachtwoorden van gebruikers. Nadat een query voor een gebruiker is uitgevoerd, kunnen deze waarden op de achtergrond worden gebruikt gedurende de rest van de sessie. Alleen automatisch aanmelden in de intranetzone om een query uit te voeren voor de gebruikers-id's en wachtwoorden in andere zones. Nadat een query voor een gebruiker is uitgevoerd, kunnen deze waarden op de achtergrond worden gebruikt gedurende de rest van de sessie. Automatisch aanmelden met de huidige gebruikersnaam en het huidige wachtwoord om te proberen aan te melden met behulp van Windows NT-vraag-antwoord (ook wel NTLM-verificatie genoemd). Als Windows NT-vraag-antwoord door de server wordt ondersteund, gebruikt de aanmelding de gebruikersnaam en het wachtwoord van de gebruiker voor het netwerk om de gebruiker aan te melden. Als Windows NT-vraag-antwoord niet door de server wordt ondersteund, wordt de gebruiker gevraagd om de gebruikersnaam en het wachtwoord op te geven. Als u deze beleidsinstelling uitschakelt, wordt de aanmelding ingesteld op Alleen automatisch aanmelden in de intranetzone. Als u deze beleidsinstelling niet configureert, wordt de aanmelding ingesteld op Alleen automatisch aanmelden in de intranetzone.
  
  **Standaardinstelling**: Vragen  
  
- **Beperkte zone van Internet Explorer: uitvoeren van VBScript toestaan**  </br>  
  Met deze beleidsinstelling kunt u beheren VBScript kan worden uitgevoerd op pagina's via de opgegeven zone in Internet Explorer. Als u in de vervolgkeuzelijst Inschakelen hebt geselecteerd, kan VBScript worden uitgevoerd zonder tussenkomst van de gebruiker. Als u in de vervolgkeuzelijst Vragen hebt geselecteerd, worden gebruikers gevraagd of ze willen toestaan dat VBScript wordt uitgevoerd. Als u in de vervolgkeuzelijst Uitschakelen hebt geselecteerd, wordt voorkomen dat VBScript wordt uitgevoerd. Als u deze beleidsinstelling niet configureert of uitschakelt, kan VBScript niet worden uitgevoerd.
  
  **Standaard**: Uitschakelen  
  
- **Beperkte zone van Internet Explorer: inhoud van verschillende domeinen verslepen tussen vensters**  
  Met deze beleidsinstelling kunt u opties instellen voor het verslepen van inhoud van het ene naar het andere domein wanneer de bron en de bestemming zich in verschillende vensters bevinden. Als u deze beleidsinstelling inschakelt en op Inschakelen klikt, kunnen gebruikers inhoud van het ene naar het andere domein verslepen wanneer de bron en de bestemming zich in verschillende vensters bevinden. Gebruikers kunnen deze instelling niet wijzigen. Als u deze beleidsinstelling inschakelt en op Uitschakelen klikt, kunnen gebruikers geen inhoud van het ene naar het andere domein verslepen als de bron en de bestemming zich in verschillende vensters bevinden. Gebruikers kunnen deze instelling niet wijzigen. Als u deze beleidsinstelling in Internet Explorer 10 uitschakelt of niet configureert, kunnen gebruikers geen inhoud van het ene naar het andere domein verslepen wanneer de bron en de bestemming zich in verschillende vensters bevinden. Gebruikers kunnen deze instelling wijzigen in het dialoogvenster Internetopties. Als u dit beleid in Internet Explorer 9 en eerdere versies uitschakelt of niet configureert, kunnen gebruikers inhoud van het ene naar het andere domein verslepen als de bron en de bestemming zich in verschillende vensters bevinden. Gebruikers kunnen deze instelling niet wijzigen.
  
  **Standaardinstelling**: uitgeschakeld 
  
- **Intranetzone van Internet Explorer: ActiveX-besturingselementen die niet als veilig zijn gemarkeerd, initialiseren en als script uitvoeren**  
  Met deze beleidsinstelling kunt u ActiveX-besturingselementen beheren die niet als veilig zijn gemarkeerd. Als u deze beleidsinstelling inschakelt, worden ActiveX-besturingselementen uitgevoerd, voorzien van parameters en als script uitgevoerd zonder de veiligheid van objecten in te stellen voor niet-vertrouwde gegevens of scripts. Deze instelling wordt niet aanbevolen, behalve voor veilige en beheerde zones. Deze instelling zorgt dat zowel onveilige als veilige besturingselementen worden geïnitialiseerd en als script worden uitgevoerd. Daarbij worden de ActiveX-besturingselementen van het script die als veilig zijn gemarkeerd, genegeerd. Als u deze beleidsinstelling inschakelt en in de vervolgkeuzelijst Vragen selecteert, worden gebruikers gevraagd of ze willen toestaan dat het besturingselement met parameters wordt geladen of als script wordt uitgevoerd. Als u deze beleidsinstelling uitschakelt, worden ActiveX-besturingselementen die niet veilig kunnen worden ingesteld, niet geladen met parameters of als script uitgevoerd. Als u deze beleidsinstelling niet configureert, worden ActiveX-besturingselementen die niet veilig kunnen worden ingesteld, niet geladen met parameters of als script uitgevoerd.
  
  **Standaard**: Uitschakelen 
  
- **Internet Explorer: bijlagen downloaden**  
  Met deze beleidsinstelling kunt u voorkomen dat de gebruiker bestandsbijlagen via een feed naar de computer van de gebruiker downloadt. Als u deze beleidsinstelling inschakelt, kan de gebruiker de feedsynchronisatie-engine niet zodanig instellen dat een bijlage wordt gedownload via de eigenschappenpagina van een feed. Een ontwikkelaar kan de downloadinstelling niet wijzigen via de feed-API's. Als u deze beleidsinstelling uitschakelt of niet configureert, kan de gebruiker de feedsynchronisatie-engine zodanig instellen dat een bijlage wordt gedownload via de eigenschappenpagina van een feed. Een ontwikkelaar kan de downloadinstelling wijzigen via de feed-API's.
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Beperkte zone van Internet Explorer: niet-ondertekende Active X-besturingselementen downloaden**  </br>
  Met deze beleidsinstelling kunt u beheren of gebruikers niet-ondertekende ActiveX-besturingselementen in de zone kunnen downloaden. Een dergelijke code is mogelijk schadelijk, vooral als deze afkomstig is van een niet-vertrouwde zone. Als u deze beleidsinstelling inschakelt, kunnen gebruikers niet-ondertekende besturingselementen uitvoeren zonder tussenkomst van de gebruiker. Als u in de vervolgkeuzelijst Vragen selecteert, moeten gebruikers kiezen of ze het niet-ondertekende besturingselement wel of niet laten uitvoeren. Als u deze beleidsinstelling uitschakelt, kunnen gebruikers niet-ondertekende besturingselementen niet uitvoeren. Als u deze beleidsinstelling niet configureert, kunnen gebruikers niet-ondertekende besturingselementen niet uitvoeren.
  
  **Standaard**: Uitschakelen  
  
- **Beperkte zone van Internet Explorer: inhoud van verschillende domeinen verslepen binnen vensters**  
  Met deze beleidsinstelling kunt u beheren of gebruikers niet-ondertekende ActiveX-besturingselementen in de zone kunnen downloaden. Een dergelijke code is mogelijk schadelijk, vooral als deze afkomstig is van een niet-vertrouwde zone. Als u deze beleidsinstelling inschakelt, kunnen gebruikers niet-ondertekende besturingselementen uitvoeren zonder tussenkomst van de gebruiker. Als u in de vervolgkeuzelijst Vragen selecteert, moeten gebruikers kiezen of ze het niet-ondertekende besturingselement wel of niet laten uitvoeren. Als u deze beleidsinstelling uitschakelt, kunnen gebruikers niet-ondertekende besturingselementen niet uitvoeren. Als u deze beleidsinstelling niet configureert, kunnen gebruikers niet-ondertekende besturingselementen niet uitvoeren.
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Processen van Internet Explorer: installeren van Active X beperken**  </br>
  Met deze beleidsinstelling kan in toepassingen die het webbrowserbesturingselement hosten het automatisch vragen om het ActiveX-besturingselement te installeren, worden geblokkeerd. Als u deze beleidsinstelling inschakelt, wordt het automatisch vragen om het ActiveX-besturingselement te installeren, geblokkeerd met het webbrowserbesturingselement. Als u deze beleidsinstelling uitschakelt of niet configureert, wordt het automatisch vragen om het ActiveX-besturingselement te installeren, niet geblokkeerd met het webbrowserbesturingselement.
  
  **Standaardinstelling**: ingeschakeld  
  
- **Internetzone van Internet Explorer: scriptlets** Met deze beleidsinstelling kunt u beheren of de gebruiker scriptlets kan uitvoeren. Als u deze beleidsinstelling inschakelt, kan de gebruiker scriptlets uitvoeren. Als u deze beleidsinstelling uitschakelt, kan de gebruiker geen scriptlets uitvoeren. Als u deze beleidsinstelling niet configureert, kan de gebruiker scriptlets in- of uitschakelen.
  
  **Standaard**: Uitschakelen  
  
- **Beperkte zone van Internet Explorer: bestanden slepen en neerzetten of kopiëren en plakken**  
  Met deze beleidsinstelling kunt u beheren of gebruikers bestanden kunnen slepen of kunnen kopiëren slepen en plakken vanuit een bron binnen de zone. Als u deze beleidsinstelling inschakelt, kunnen gebruikers automatisch bestanden slepen of bestanden kopiëren en plakken vanuit deze zone. Als u in de vervolgkeuzelijst Vragen selecteert, moeten gebruikers kiezen of ze bestanden willen slepen of kopiëren vanuit deze zone. Als u deze beleidsinstelling uitschakelt, kunnen geen bestanden slepen of kopiëren en plakken vanuit deze zone. Als u deze beleidsinstelling niet configureert, moeten gebruikers kiezen of ze bestanden willen slepen of kopiëren vanuit deze zone.
  
  **Standaard**: Uitschakelen  
  
- **Software van Internet Explorer: bij ongeldige handtekening** </br>
  Met deze beleidsinstelling kunt u beheren of software, bijvoorbeeld ActiveX-besturingselementen en bestandsdownloads, kunnen worden uitgevoerd of geïnstalleerd door de gebruiker als de handtekening ongeldig is. Een ongeldige handtekening kan erop wijzen dat iemand het bestand onrechtmatig heeft gewijzigd. Als u deze beleidsinstelling inschakelt, worden gebruikers gevraagd of ze bestanden met een ongeldige handtekening willen uitvoeren of installeren. Als u deze beleidsinstelling uitschakelt, kunnen gebruikers bestanden met een ongeldige handtekening niet uitvoeren of installeren. Als u deze beleidsinstelling niet configureert, kunnen gebruikers kiezen of ze bestanden met een ongeldige handtekening willen uitvoeren of installeren.
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Beperkte zone van Internet Explorer: kopiëren en plakken via scripts** </br> Met deze beleidsinstelling kunt u beheren of met scripts een klembordbewerking (zoals knippen, kopiëren en plakken) kan worden uitgevoerd in een opgegeven regio. Als u deze beleidsinstelling inschakelt, kan met een script een klembordbewerking worden uitgevoerd. Als u in de vervolgkeuzelijst Vragen selecteert, moeten gebruikers kiezen of ze klembordbewerkingen willen uitvoeren. Als u deze beleidsinstelling uitschakelt, kan er met een script geen klembordbewerking worden uitgevoerd. Als u deze beleidsinstelling niet configureert, kan met een script geen klembordbewerking worden uitgevoerd.
  
  **Standaard**: Uitschakelen  
  
- **Beperkte zone van Internet Explorer: inhoud van verschillende domeinen in de verslepen tussen vensters**  
  Met deze beleidsinstelling kunt u opties instellen voor het verslepen van inhoud van het ene naar het andere domein wanneer de bron en de bestemming zich in verschillende vensters bevinden. Als u deze beleidsinstelling inschakelt en op Inschakelen klikt, kunnen gebruikers inhoud van het ene naar het andere domein verslepen wanneer de bron en de bestemming zich in verschillende vensters bevinden. Gebruikers kunnen deze instelling niet wijzigen. Als u deze beleidsinstelling inschakelt en op Uitschakelen klikt, kunnen gebruikers geen inhoud van het ene naar het andere domein verslepen als de bron en de bestemming zich in verschillende vensters bevinden. Gebruikers kunnen deze instelling niet wijzigen. Als u deze beleidsinstelling in Internet Explorer 10 uitschakelt of niet configureert, kunnen gebruikers geen inhoud van het ene naar het andere domein verslepen wanneer de bron en de bestemming zich in verschillende vensters bevinden. Gebruikers kunnen deze instelling wijzigen in het dialoogvenster Internetopties. Als u dit beleid in Internet Explorer 9 en eerdere versies uitschakelt of niet configureert, kunnen gebruikers inhoud van het ene naar het andere domein verslepen als de bron en de bestemming zich in verschillende vensters bevinden. Gebruikers kunnen deze instelling niet wijzigen.  <br><br>
  **Standaardinstelling**: uitgeschakeld  
  
- **Gebruikers die websites toevoegen in Internet Explorer**  
  Hiermee wordt voorkomen dat gebruikers websites toevoegen aan of verwijderen uit beveiligingszones. Een beveiligingszone is een groep websites met hetzelfde beveiligingsniveau. Als u dit beleid inschakelt, worden de instellingen voor het beheren van websites voor beveiligingszones uitgeschakeld. (Klik in het dialoogvenster Internetopties op het tabblad Beveiliging en klik daarna op de knop Websites om de instellingen voor websitebeheer voor beveiligingszones weer te geven.) Als u dit beleid uitschakelt of niet configureert, kunnen gebruikers websites toevoegen aan of verwijderen uit de zones Vertrouwde websites en Beperkte websites. Ook kunnen ze de instellingen voor de zone Lokaal intranet aanpassen. Met dit beleid voorkomt u dat gebruikers de instellingen voor het beheren van websites wijzigen voor beveiligingszones die door de beheerder zijn gemaakt. Opmerking: met het beleid De beveiligingspagina uitschakelen (in \User Configuration\Administrative Templates\Windows Components\Internet Explorer\Internet Control Panel) verwijdert u het tabblad Beveiliging in de interface. Dit heeft voorrang ten opzichte van dit beleid. Dit beleid wordt genegeerd als deze optie is ingeschakeld. Zie ook het beleid Beveiligingszones: alleen computerinstellingen gebruiken.
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Internet Explorer: door script geïnitieerde vensters in de internetzone**  
  Met deze beleidsinstelling kunt u beperkingen beheren voor door scripts geïnitieerde pop-upvensters en vensters die een titel en statusbalken bevatten. Als u deze beleidsinstelling inschakelt, is de beveiliging door Windows-beperkingen niet van toepassing in deze zone. De beveiligingszone wordt uitgevoerd zonder de toegevoegde beveiligingslaag van deze functie. Als u deze beleidsinstelling uitschakelt, kunnen mogelijk schadelijke acties in door scripts geïnitieerde pop-upvensters en vensters die een titel en statusbalken bevatten, niet worden uitgevoerd. Deze beveiligingsfunctie van Internet Explorer is in deze zone ingeschakeld, zoals dat door de instelling van de functie Gescripte Windows-beveiligingsbeperkingen voor het proces is opgegeven. Als u deze beleidsinstelling niet configureert, kunnen mogelijk schadelijke acties in door scripts geïnitieerde pop-upvensters en vensters die een titel en statusbalken bevatten, niet worden uitgevoerd. Deze beveiligingsfunctie van Internet Explorer is in deze zone ingeschakeld, zoals dat door de instelling van de functie Gescripte Windows-beveiligingsbeperkingen voor het proces is opgegeven.
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Internet Explorer: alleen computerinstellingen gebruiken in beveiligingszones**  
  Hiermee past u informatie over de beveiligingszone toe op alle gebruikers met dezelfde computer. Een beveiligingszone is een groep websites met hetzelfde beveiligingsniveau. Als u dit beleid inschakelt, worden wijzigingen die de gebruiker in een beveiligingszone toepast op alle gebruikers van die computer toegepast. Als u dit beleid uitschakelt of niet configureert, kunnen gebruikers van dezelfde computer hun eigen instellingen voor de beveiligingszone instellen. Gebruik dit beleid om ervoor te zorgen dat instellingen voor beveiligingszones eenduidig op dezelfde computer worden toegepast en niet per gebruiker verschillen. Zie ook het beleid Beveiligingszones: gebruikers niet toestaan om beleid te wijzigen.
  
  **Standaardinstelling**: ingeschakeld  
  
- **Java-machtigingen voor de vergrendelde zone Lokale machine in Internet Explorer**  
  Met deze beleidsinstelling kunt u machtigingen voor Java-applets beheren. Als u deze beleidsinstelling inschakelt, kunt u opties kiezen in de vervolgkeuzelijst. Aangepast, om instellingen voor machtigingen afzonderlijk te beheren. Met Minimale beveiliging kunnen applets alle bewerkingen uitvoeren. Met Normale beveiliging kunnen applets worden uitgevoerd in hun eigen sandbox (een gebied in het geheugen waarbuiten het programma geen aanroepen kan doen). Daarnaast biedt deze optie mogelijkheden zoals een scratchruimte (een veilig en beveiligd opslaggebied op de clientcomputer) en door de gebruiker beheerde bestandsinvoer en-uitvoer (I/O). Met Strenge beveiliging kunnen applets in hun sandbox worden uitgevoerd. Schakel Java uit om te voorkomen dat er applets worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, kunnen Java-applets niet worden uitgevoerd. Als u deze beleidsinstelling niet configureert, worden Java-applets uitgeschakeld
  
  **Standaardinstelling**: Java uitschakelen 
  
- **Er wordt geen antimalware uitgevoerd op ActiveX-besturingselementen in de beperkte zone van Internet Explorer**  </br>
  Met deze beleidsinstelling wordt bepaald of Internet Explorer antimalwareprogramma's uitvoert op ActiveX-besturingselementen om te controleren of ze veilig zijn om te laden op pagina's. Als u deze beleidsinstelling inschakelt, controleert Internet Explorer niet met uw antimalware-programma om te zien of het veilig is om een exemplaar van het ActiveX-besturingselement te installeren. Als u deze beleidsinstelling uitschakelt, controleert Internet Explorer altijd met uw antimalware-programma om te zien of het veilig is om een exemplaar van het ActiveX-besturingselement te installeren. Als u deze beleidsinstelling niet configureert, controleert Internet Explorer altijd met uw antimalware-programma om te zien of het veilig is om een exemplaar van het ActiveX-besturingselement te installeren. Gebruikers kunnen dit gedrag in- of uitschakelen met de beveiligingsinstellingen van Internet Explorer.
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Internet Explorer: onderdelen in de beperkte zone uitvoeren die afhankelijk zijn van .NET Framework en zijn ondertekend met Authenticode**  
  Met deze beleidsinstelling kunt u beheren of .NET Framework-onderdelen die met Authenticode zijn ondertekend, kunnen worden uitgevoerd in Internet Explorer. Deze onderdelen bevatten beheerde besturingselementen waarnaar vanuit een objectlabel wordt verwezen en beheerde uitvoerbare bestanden waarnaar vanuit een koppeling wordt verwezen. Als u deze beleidsinstelling inschakelt, zal Internet Explorer ondertekende beheerde onderdelen uitvoeren. Als u in de vervolgkeuzelijst Vragen selecteert, wordt de gebruiker gevraagd om te bepalen of ondertekende beheerde onderdelen moeten worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, zal Internet Explorer ondertekende beheerde onderdelen niet uitvoeren. Als u deze beleidsinstelling niet configureert, worden ondertekende beheerde onderdelen niet uitgevoerd in Internet Explorer.
  
  **Standaard**: Uitschakelen  
  
- **Internet Explorer: toegang tot gegevensbronnen via een beperkte zone**  
  Met deze beleidsinstelling kunt u beheren of Internet Explorer toegang heeft tot gegevens van een andere beveiligingszone met behulp van de Microsoft XML-parser (MSXML) of ActiveX-gegevensobjecten (ADO). Als u deze beleidsinstelling inschakelt, kunnen gebruikers een pagina laden in de zone die MSXML of ADO gebruikt voor toegang tot gegevens van een andere site in de zone. Als u Prompt selecteert in de vervolgkeuzelijst, wordt gebruikers gevraagd om te kiezen of een pagina mag worden geladen in de zone die MSXML of ADO gebruikt voor toegang tot gegevens van een andere site in de zone. Als u deze beleidsinstelling uitschakelt, kunnen gebruikers geen pagina laden in de zone die MSXML of ADO gebruikt voor toegang tot gegevens van een andere site in de zone. Als u deze beleidsinstelling niet configureert, kunnen gebruikers geen pagina laden in de zone die MSXML of ADO gebruikt voor toegang tot gegevens van een andere site in de zone.
  
  **Standaard**: Uitschakelen 
  
- **Er wordt geen antimalware uitgevoerd op ActiveX-besturingselementen in de internetzone van Internet Explorer**  </br>
  Met deze beleidsinstelling wordt bepaald of Internet Explorer antimalwareprogramma's uitvoert op ActiveX-besturingselementen om te controleren of ze veilig zijn om te laden op pagina's. Als u deze beleidsinstelling inschakelt, controleert Internet Explorer niet met uw antimalware-programma om te zien of het veilig is om een exemplaar van het ActiveX-besturingselement te installeren. Als u deze beleidsinstelling uitschakelt, controleert Internet Explorer altijd met uw antimalware-programma om te zien of het veilig is om een exemplaar van het ActiveX-besturingselement te installeren. Als u deze beleidsinstelling niet configureert, controleert Internet Explorer altijd met uw antimalware-programma om te zien of het veilig is om een exemplaar van het ActiveX-besturingselement te installeren. Gebruikers kunnen dit gedrag in- of uitschakelen met de beveiligingsinstellingen van Internet Explorer.
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Internet Explorer: kopiëren en plakken via een script in de internetzone** </br> Met deze beleidsinstelling kunt u beheren of met scripts een klembordbewerking (zoals knippen, kopiëren en plakken) kan worden uitgevoerd in een opgegeven regio. Als u deze beleidsinstelling inschakelt, kan met een script een klembordbewerking worden uitgevoerd. Als u in de vervolgkeuzelijst Vragen selecteert, moeten gebruikers kiezen of ze klembordbewerkingen willen uitvoeren. Als u deze beleidsinstelling uitschakelt, kan er met een script geen klembordbewerking worden uitgevoerd. Als u deze beleidsinstelling niet configureert, kan een script een klembordbewerking uitvoeren.
  
  **Standaard**: Uitschakelen  
  
- **Internet Explorer: de ActiveX Installer-service gebruiken**  </br>
  Met deze beleidsinstelling kunt u opgeven hoe ActiveX-besturingselementen worden geïnstalleerd. Als u deze beleidsinstelling inschakelt, wordt ActiveX-besturingselementen alleen geïnstalleerd als de Installer-service aanwezig is en is geconfigureerd om de installatie van ActiveX-besturingselementen toe te staan. Als u deze beleidsinstelling uitschakelt of niet configureert, worden ActiveX-besturingselementen, inclusief besturingselementen per gebruiker, geïnstalleerd via het gewone installatieproces.
  
  **Standaardinstelling**: ingeschakeld  
  
- **Internet Explorer verwerkt bescherming tegen zone-uitbreiding**  
  Internet Explorer kent beperkingen toe aan elke webpagina die wordt geopend. De beperkingen zijn afhankelijk van de locatie van de webpagina (internet-, intranet-, lokale computer-zone, enzovoort). Voor webpagina's op de lokale computer gelden bijvoorbeeld minder beveiligingsbeperkingen, terwijl deze in de zone Lokale computer verblijven, waardoor de beveiligingszone Lokale computer een belangrijk doelwit is voor kwaadwillende gebruikers. Als u deze beleidsinstelling inschakelt, kan elke zone worden beschermd tegen zone-uitbreiding voor alle processen. Als u deze beleidsinstelling uitschakelt of niet configureert, genieten andere processen dan Internet Explorer of processen in de lijst Proceslijst deze bescherming niet.
  
  **Standaardinstelling**: ingeschakeld  
  
- **Niet-ondertekende Active X-besturingselementen downloaden in internetzone van Internet Explorer**  </br>
  Met deze beleidsinstelling kunt u beheren of gebruikers niet-ondertekende ActiveX-besturingselementen in de zone kunnen downloaden. Een dergelijke code is mogelijk schadelijk, vooral als deze afkomstig is van een niet-vertrouwde zone. Als u deze beleidsinstelling inschakelt, kunnen gebruikers niet-ondertekende besturingselementen uitvoeren zonder tussenkomst van de gebruiker. Als u in de vervolgkeuzelijst Vragen selecteert, moeten gebruikers kiezen of ze het niet-ondertekende besturingselement wel of niet laten uitvoeren. Als u deze beleidsinstelling uitschakelt, kunnen gebruikers niet-ondertekende besturingselementen niet uitvoeren. Als u deze beleidsinstelling niet configureert, kunnen gebruikers niet-ondertekende besturingselementen niet uitvoeren.
  
  **Standaard**: Uitschakelen  
  
- **Vensters en frames door verschillende domeinen laten navigeren in de Internet Explorer-internetzone**  </br>
  Met deze beleidsinstelling kunt u het openen van vensters en frames en de toegang tot toepassingen in verschillende domeinen beheren. Als u deze beleidsinstelling inschakelt, kunnen gebruikers vensters en frames openen vanuit andere domeinen en toegang krijgen tot toepassingen van andere domeinen. Als u Vragen in de vervolgkeuzelijst selecteert, wordt aan gebruikers gevraagd of vensters en frames toegang mogen hebben tot toepassingen van andere domeinen. Als u deze beleidsinstelling uitschakelt, kunnen gebruikers geen vensters en frames openen om toegang te krijgen tot toepassingen vanuit andere domeinen. Als u deze beleidsinstelling niet configureert, kunnen gebruikers vensters en frames openen vanuit andere domeinen en toegang krijgen tot toepassingen van andere domeinen.
  
  **Standaard**: Uitschakelen  
  
- **Updates van de statusbalk vinden plaats in de Internet Explorer-internetzone via script**  
  Met deze beleidsinstelling kunt u regelen of de statusbalk in de zone via script mag worden bijgewerkt. Als u deze beleidsinstelling inschakelt, kunnen scripts de statusbalk bijwerken. Als u deze beleidsinstelling uitschakelt of niet configureert, mag de statusbalk niet worden bijgewerkt via script.
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Lokaal pad wordt tijdens het uploaden van bestanden naar de server opgenomen in de beperkte zone van Internet Explorer**  </br> Met deze beleidsinstelling bepaalt u of gegevens over het lokale pad worden verzonden wanneer de gebruiker een bestand uploadt via een HTML-formulier. Als er gegevens over het lokale pad zijn verzonden, wordt mogelijk bepaalde informatie onbedoeld op de server weergegeven. Bestanden die vanaf het bureaublad van de gebruiker zijn verzonden, bevatten bijvoorbeeld mogelijk de gebruikersnaam als onderdeel van het pad. Als u deze beleidsinstelling inschakelt, worden gegevens over het pad verzonden wanneer de gebruiker een bestand via een HTML-formulier uploadt. Als u deze beleidsinstelling uitschakelt, worden gegevens over het pad verwijderd wanneer de gebruiker een bestand via een HTML-formulier uploadt. Als u deze beleidsinstelling niet configureert, kan de gebruiker kiezen of gegevens over het pad worden verzonden wanneer ze een bestand uploaden via een HTML-formulier. Standaard worden gegevens over het pad verzonden.
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Het downloaden van bestanden beperken in processen van Internet Explorer**  </br> Met deze beleidsinstelling wordt in toepassingen die het webbrowserbesturingselement hosten een blokkering ingesteld van het automatisch vragen om niet door de gebruiker geïnitialiseerde downloads van bestanden. Als u deze beleidsinstelling inschakelt, wordt in toepassingen die het webbrowserbesturingselement hosten voor alle processen een blokkering ingesteld van het automatisch vragen om niet door de gebruiker geïnitialiseerde downloads van bestanden. Als u deze beleidsinstelling uitschakelt, wordt in toepassingen die het webbrowserbesturingselement hosten voor alle processen geen blokkering ingesteld van het automatisch vragen om niet door de gebruiker geïnitialiseerde downloads van bestanden.
  
  **Standaardinstelling**: ingeschakeld  
  
- **Alleen goedgekeurde domeinen mogen Active X-besturingselementen gebruiken in de beperkt zone van Internet Explorer**  </br>
  Met deze beleidsinstelling bepaalt u of de gebruiker wordt gevraagd om toe te staan dat ActiveX-besturingselementen op andere websites worden uitgevoerd dan de website waarop het ActiveX-besturingselement is geïnstalleerd. Als u deze beleidsinstelling inschakelt, wordt de gebruiker vooraf gevraagd of het ActiveX-besturingselement mag worden uitgevoerd vanaf websites in deze zone. De gebruiker kan ervoor kiezen dat het besturingselement vanaf de huidige site of vanaf alle sites kan worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, krijgt de gebruiker niet de sitespecifieke ActiveX-melding te zien en kunnen ActiveX-besturingselementen worden uitgevoerd vanaf alle sites in deze zone.
  
  **Standaardinstelling**: ingeschakeld  
  
- **ActiveX-besturingselementen die niet als veilig zijn gemarkeerd initialiseren en als script uitvoeren in de beperkte zone in Internet Explorer**  
  Met deze beleidsinstelling kunt u ActiveX-besturingselementen beheren die niet als veilig zijn gemarkeerd. Als u deze beleidsinstelling inschakelt, worden ActiveX-besturingselementen uitgevoerd, voorzien van parameters en als script uitgevoerd zonder de veiligheid van objecten in te stellen voor niet-vertrouwde gegevens of scripts. Deze instelling wordt niet aanbevolen, behalve voor veilige en beheerde zones. Deze instelling zorgt dat zowel onveilige als veilige besturingselementen worden geïnitialiseerd en als script worden uitgevoerd. Daarbij worden de ActiveX-besturingselementen van het script die als veilig zijn gemarkeerd, genegeerd. Als u deze beleidsinstelling inschakelt en in de vervolgkeuzelijst Vragen selecteert, worden gebruikers gevraagd of ze willen toestaan dat het besturingselement met parameters wordt geladen of als script wordt uitgevoerd. Als u deze beleidsinstelling uitschakelt, worden ActiveX-besturingselementen die niet veilig kunnen worden ingesteld, niet geladen met parameters of als script uitgevoerd. Als u deze beleidsinstelling niet configureert, worden ActiveX-besturingselementen die niet veilig kunnen worden ingesteld, niet geladen met parameters of als script uitgevoerd.
  
  **Standaard**: Uitschakelen  
  
- **Gebruikers van Internet Explorer die beleidsregels wijzigen**  
    Hiermee voorkomt u dat gebruikers instellingen voor beveiligingszones wijzigen. Een beveiligingszone is een groep websites met hetzelfde beveiligingsniveau. Als u dit beleid inschakelt, worden de knop Aangepast niveau en de schuifregelaar voor het beveiligingsniveau op het tabblad Beveiliging in het dialoogvenster Internetopties uitgeschakeld. Als u dit beleid uitschakelt of niet configureert, kunnen gebruikers de instellingen voor beveiligingszones wijzigen. Met dit beleid voorkomt u dat gebruikers de instellingen voor beveiligingszones die door de beheerder zijn gemaakt, kunnen wijzigen. Opmerking: het beleid 'De pagina Beveiliging uitschakelen' (te vinden in \Gebruikersconfiguratie\Beheersjablonen\Windows-onderdelen\Internet Explorer\Onderdeel Internetopties van het Configuratiescherm), waardoor het tabblad Beveiliging uit Internet Explorer in Configuratiescherm wordt verwijderd, heeft voorrang op dit beleid. Dit beleid wordt genegeerd als deze optie is ingeschakeld. Zie ook het beleid Beveiligingszones: alleen computerinstellingen gebruiken.
    
  **Standaardinstelling**: uitgeschakeld  
  
- **Beveiligde modus van de beperkte zone van Internet Explorer**  
  Met deze beleidsinstelling kunt u de functie Beveiligde modus inschakelen. Met behulp van Beveiligde modus kunt u Internet Explorer beschermen tegen misbruikte zwakke plekken door het aantal locaties te verminderen waarnaar Internet Explorer in het register en het bestandssysteem kan schrijven. Als u deze beleidsinstelling inschakelt, wordt Beveiligde modus ingeschakeld. De gebruiker kan Beveiligde modus niet uitschakelen. Als u deze beleidsinstelling uitschakelt, wordt Beveiligde modus uitgeschakeld. De gebruiker kan Beveiligde modus niet inschakelen. Als u deze beleidsinstelling niet configureert, kan de gebruiker Beschermde modus in- of uitschakelen.
  
  **Standaardinstelling**: Inschakelen  
  
- **Persistentie van gebruikersgegevens in de internetzone van Internet Explorer**  
  Met deze beleidsinstelling kunt u het bewaren van gegevens beheren in de geschiedenis van de browser, in Favorieten, in een XML-archief of direct in op een schijf opgeslagen webpagina's. Wanneer een gebruiker naar een permanent bewaarde pagina terugkeert, kan de status van de pagina worden hersteld als deze beleidsinstelling op de juiste wijze is geconfigureerd. Als u deze beleidsinstelling inschakelt, kunnen gebruikers informatie bewaren in de geschiedenis van de browser, in Favorieten, in een XML-archief of direct in op een schijf opgeslagen webpagina's. Als u deze beleidsinstelling uitschakelt, kunnen gebruikers geen informatie bewaren in de geschiedenis van de browser, in Favorieten, in een XML-archief of direct in op een schijf opgeslagen webpagina's. Als u deze beleidsinstelling niet configureert, kunnen gebruikers geen informatie bewaren in de geschiedenis van de browser, in Favorieten, in een XML-archief of direct in op een schijf opgeslagen webpagina's.
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Scripts uitvoeren van webbrowserbesturingselementen in de internetzone van Internet Explorer**  
 
  Met deze beleidsinstelling bepaalt u of op een pagina ingesloten webbrowserbesturingselementen via een script kunnen worden beheerd. Als u deze beleidsinstelling inschakelt, is scripttoegang tot het webbrowserbesturingselement toegestaan. Als u deze beleidsinstelling uitschakelt, is scripttoegang tot het webbrowserbesturingselement niet toegestaan. Als u deze beleidsinstelling niet configureert, kan de gebruiker scripttoegang tot het webbrowserbesturingselement in- of uitschakelen. Standaard is scripttoegang tot het besturingselement WebBrowser alleen toegestaan in de lokale computer en intranetzones.
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Persistentie van gebruikersgegevens in de beperkte zone van Internet Explorer**  
    Met deze beleidsinstelling kunt u het bewaren van gegevens beheren in de geschiedenis van de browser, in Favorieten, in een XML-archief of direct in op een schijf opgeslagen webpagina's. Wanneer een gebruiker naar een permanent bewaarde pagina terugkeert, kan de status van de pagina worden hersteld als deze beleidsinstelling op de juiste wijze is geconfigureerd. Als u deze beleidsinstelling inschakelt, kunnen gebruikers informatie bewaren in de geschiedenis van de browser, in Favorieten, in een XML-archief of direct in op een schijf opgeslagen webpagina's. Als u deze beleidsinstelling uitschakelt, kunnen gebruikers geen informatie bewaren in de geschiedenis van de browser, in Favorieten, in een XML-archief of direct in op een schijf opgeslagen webpagina's. Als u deze beleidsinstelling niet configureert, kunnen gebruikers informatie bewaren in de geschiedenis van de browser, in Favorieten, in een XML-archief of direct in op een schijf opgeslagen webpagina's.  
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Java-machtigingen voor de intranetzone zijn in Internet Explorer vergrendeld**  
  Met deze beleidsinstelling kunt u machtigingen voor Java-applets beheren. Als u deze beleidsinstelling inschakelt, kunt u opties kiezen in de vervolgkeuzelijst. Aangepast, om instellingen voor machtigingen afzonderlijk te beheren. Met Minimale beveiliging kunnen applets alle bewerkingen uitvoeren. Met Normale beveiliging kunnen applets worden uitgevoerd in hun eigen sandbox (een gebied in het geheugen waarbuiten het programma geen aanroepen kan doen). Daarnaast biedt deze optie mogelijkheden zoals een scratchruimte (een veilig en beveiligd opslaggebied op de clientcomputer) en door de gebruiker beheerde bestandsinvoer en-uitvoer (I/O). Met Strenge beveiliging kunnen applets in hun sandbox worden uitgevoerd. Schakel Java uit om te voorkomen dat er applets worden uitgevoerd. Als u deze beleidsinstelling uitschakelt, kunnen Java-applets niet worden uitgevoerd. Als u deze beleidsinstelling niet configureert, worden Java-applets uitgeschakeld.
  
  **Standaardinstelling**: Java uitschakelen  
  
- **Uitgebreide beveiligde modus van Internet Explorer**  
  De uitgebreide beveiligde modus biedt extra bescherming tegen schadelijke websites door gebruik te maken van 64-bits processen op 64-bits versies van Windows. Op computers met minimaal Windows 8 beperkt de uitgebreide beveiligde modus ook de locaties die Internet Explorer in het register en bestandssysteem kan lezen. Als u deze beleidsinstelling inschakelt, wordt Uitgebreide beveiligde modus ingeschakeld. Voor elke zone waarvoor Beveiligde modus is ingeschakeld, wordt Uitgebreide beveiligde modus gebruikt. Gebruikers kunnen Uitgebreide beveiligde modus niet uitschakelen. Als u deze beleidsinstelling uitschakelt, wordt Uitgebreide beveiligde modus uitgeschakeld. In een zone waarvoor Beveiligde modus is ingeschakeld, wordt de Beveiligde modus-versie gebruikt die is geïntroduceerd in Internet Explorer 7 voor Windows Vista. Als u dit beleid niet configureert, kunnen gebruikers Uitgebreide beveiligde modus inschakelen of uitschakelen op het tabblad Geavanceerd van het dialoogvenster Internetopties.
  
  **Standaardinstelling**: ingeschakeld  
  
- **SmartScreen-waarschuwingen negeren in Internet Explorer**  
  Met deze beleidsinstelling bepaalt u of de gebruiker waarschuwingen van het SmartScreen-filter kan negeren. Het SmartScreen-filter waarschuwt de gebruiker voor uitvoerbare bestanden die Internet Explorer-gebruikers normaalgesproken niet van internet downloaden. Als u deze beleidsinstelling inschakelt, wordt de gebruiker door waarschuwingen van het SmartScreen-filter geblokkeerd. Als u deze beleidsinstelling uitschakelt of niet configureert, kan de gebruiker waarschuwingen van het SmartScreen-filter negeren.
  
  **Standaardinstelling**: uitgeschakeld  
  
- **Metagegevens vernieuwen in de beperkte zone van Internet Explorer**  
  Met deze beleidsinstelling kunt u bepalen of de browser van een gebruiker kan worden omgeleid naar een andere webpagina als de auteur van de webpagina met behulp van de instelling Metagegevens vernieuwen (tag) browsers omleidt naar een andere webpagina. Als u deze beleidsinstelling inschakelt, kan de browser van een gebruiker waarmee een pagina met een geactiveerde instelling Metagegevens vernieuwen wordt geladen, worden omgeleid naar een andere webpagina. Als u deze beleidsinstelling uitschakelt, kan de browser van een gebruiker waarmee een pagina met een geactiveerde instelling Metagegevens vernieuwen wordt geladen, niet worden omgeleid naar een andere webpagina. Als u deze beleidsinstelling niet configureert, kan de browser van een gebruiker waarmee een pagina met een geactiveerde instelling Metagegevens vernieuwen wordt geladen, niet worden omgeleid naar een andere webpagina.
  
  **Standaardinstelling**: uitgeschakeld  
  
### <a name="local-policies-security-options"></a>Beveiligingsopties voor lokaal beleid
Zie [Beleids-CSP - LocalPoliciesSecurityOptions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions) in de Windows-documentatie voor meer informatie. 

- **Anonieme toegang tot named pipes en shares beperken**  
  Wanneer dit is ingeschakeld, wordt met deze beveiligingsinstelling anonieme toegang beperkt tot shares en pipes voor de instellingen van: (1) named pipes die anoniem kunnen worden benaderd (2) shares die anoniem kunnen worden benaderd
  
  **Standaardinstelling**: Ja  
  
- **Minimale sessiebeveiliging voor op NTLM SSP-gebaseerde servers**  
  Via deze beveiligingsinstelling kan een server de onderhandeling van een 128-bits versleuteling en/of een NTLMv2-sessiebeveiliging vereisen. Deze waarden zijn afhankelijk van de beveiligingsinstellingswaarde van het LAN Manager-verificatieniveau. De opties zijn: NTLMv2-sessiebeveiliging vereisen: de verbinding mislukt als niet over berichtintegriteit wordt onderhandeld. 128-bits versleuteling vereisen. De verbinding mislukt als niet wordt onderhandeld over sterke versleuteling (128-bits).
  
  **Standaardinstelling**: NTLM V2 en 128-bits versleuteling vereisen  
  
- **Minuten van inactiviteit van vergrendelingsscherm totdat de schermbeveiliging wordt geactiveerd**  
  Een aanmeldingssessie zonder activiteit wordt opgemerkt door Windows. Als de inactieve tijd de ingestelde limiet voor inactiviteit overschrijdt, wordt de schermbeveiliging ingeschakeld en wordt de sessie vergrendeld.
  
  **Standaardinstelling**: 15
  
- **De client verplichten om altijd communicatie digitaal te ondertekenen** Met deze beveiligingsinstelling bepaalt u of al het verkeer via beveiligde kanalen dat is geïnitialiseerd door het domeinlid moet worden ondertekend of versleuteld. Wanneer een computer lid wordt van een domein, wordt een computeraccount gemaakt. Wanneer het systeem daarna wordt gestart, wordt het wachtwoord van het computeraccount gebruikt om een beveiligd kanaal te maken met een domeincontroller voor het domein. Dit beveiligde kanaal wordt gebruikt om bewerkingen uit te voeren zoals NTLM-PassThrough-verificatie, LSA SID/Name Lookup en meer. Met deze instelling bepaalt u of alle verkeer via beveiligde kanalen dat is geïnitialiseerd door een domeinlid aan de minimale beveiligingsvereisten voldoet. Hiermee bepaalt u specifiek of al het verkeer via beveiligde kanalen dat is gestart door een domeinlid moet worden ondertekend of versleuteld. Als dit beleid is ingeschakeld, dan wordt het beveiligde kanaal pas ingesteld als is onderhandeld over de ondertekening of versleuteling van al het verkeer via beveiligde kanalen. Als dit beleid is uitgeschakeld, wordt met de domeincontroller onderhandeld over de versleuteling en ondertekening van al het verkeer via beveiligde kanalen. In dat geval is het niveau van ondertekening en versleuteling afhankelijk van de domeincontrollerversie en de instellingen van de volgende twee beleidsregels: Lid van domein: gegevens in beveiligd kanaal digitaal versleutelen (indien mogelijk) Lid van domein: gegevens in beveiligd kanaal digitaal ondertekenen (indien mogelijk)
  
  **Standaardinstelling**: Ja
  
- **Verificatieniveau**  
  Met deze beveiligingsinstelling bepaalt u welk vraag/antwoord-verificatieprotocol wordt gebruikt voor netwerkaanmeldingen. Deze keuze is als volgt van invloed op het niveau van het verificatieprotocol dat wordt gebruikt door clients, het sessiebeveiligingsniveau dat is onderhandeld en het verificatieniveau dat is geaccepteerd door servers:  
  - *LM- en NTLM-antwoorden verzenden*: clients gebruiken LM- en NTLM-verificatie en gebruiken nooit NTLMv2-sessiebeveiliging; domeincontrollers accepteren LM-, NTLM- en NTLMv2-verificatie. 
  - *LM en NTLM verzenden - NTLMv2 indien onderhandeld*: clients gebruiken LM- en NTLM-verificatie en gebruiken NTLMv2-sessiebeveiliging als de server dit ondersteunt; domeincontrollers accepteren LM-, NTLM- en NTLMv2-verificatie. 
  - *Alleen NTLM-antwoord verzenden*: clients gebruiken alleen NTLM-verificatie en gebruiken NTLMv2-sessiebeveiliging als de server dit ondersteunt; domeincontrollers accepteren LM-, NTLM- en NTLMv2-verificatie. 
  - *Alleen NTLMv2-antwoord verzenden*: clients gebruiken alleen NTLMv2-verificatie en gebruiken NTLMv2-sessiebeveiliging als de server dit ondersteunt; domeincontrollers accepteren LM-, NTLM- en NTLMv2-verificatie. 
  - *Alleen NTLMv2-antwoord verzenden. LM weigeren*: clients gebruiken alleen NTLMv2-verificatie en gebruiken NTLMv2-sessiebeveiliging als de server dit ondersteunt; domeincontrollers weigeren LM (accepteren alleen NTLM- en NTLMv2-verificatie). 
  - *Alleen NTLMv2-antwoord verzenden. LM en NTLM weigeren*: clients gebruiken alleen NTLMv2-verificatie en gebruiken NTLMv2-sessiebeveiliging als de server dit ondersteunt; domeincontrollers weigeren LM en NTLM (accepteren alleen NTLMv2-verificatie). 
    
  **Standaardinstelling**: alleen NTLMv2-antwoord verzenden. LM en NTLM weigeren
  
- **Voorkomen dat clients niet-versleutelde wachtwoorden verzenden naar de SMB-servers van derden**  
  Als deze beveiligingsinstelling is ingeschakeld, kan de SMB-redirector (Server Message Block) ongecodeerde wachtwoorden verzenden naar niet-Microsoft SMB-servers die geen ondersteuning voor wachtwoordversleuteling bieden tijdens verificatie. Niet-versleutelde wachtwoorden verzenden is een beveiligingsrisico.
  
  **Standaardinstelling**: Ja
  
- **Servercommunicatie digitaal ondertekenen altijd uitschakelen**  
  Met deze beveiligingsinstelling wordt bepaald of de SMB-client probeert te onderhandelen over ondertekening van het SMB-pakket. Het SMB-protocol (Server Message Block) vormt de basis voor bestands- en printerdeling van Microsoft en veel andere netwerkbewerkingen, zoals extern Windows-beheer. Ter voorkoming van man-in-the-middle-aanvallen waardoor SMB-pakketten in-transit worden gewijzigd, ondersteunt het SMB-protocol de digitale ondertekening van SMB-pakketten. Met deze beleidsinstelling wordt bepaald of de SMB-clientonderdeel probeert te onderhandelen over SMB-pakketondertekening wanneer deze verbinding maakt met een SMB-server. Als deze beveiligingsinstelling is ingeschakeld, vraagt de Microsoft-netwerkclient de server om SMB-pakketondertekening uit te voeren bij het instellen van een sessie. Als pakketondertekening is ingeschakeld op de server, wordt over ondertekening van pakketten onderhandeld. Als dit beleid is uitgeschakeld, onderhandelt de SMB-client nooit over SMB-pakketondertekening.
  
  **Standaardinstelling**: Ja
  
- **Gedrag bij vragen om uitbreiding van bevoegdheden van beheerders**  
  Met deze beleidsinstelling wordt het gedrag voor het vragen om uitbreiding van bevoegdheden voor beheerders gedefinieerd. U kunt kiezen uit de volgende opties: 
  - *Verhogen zonder te vragen*: hiermee kunnen bevoegde accounts een bewerking uitvoeren waarvoor uitbreiding van bevoegdheden zonder toestemming of referenties is vereist. Opmerking: gebruik deze optie alleen in de meest beperkte omgevingen. 
  - *Vragen om referenties op het beveiligde bureaublad*: wanneer voor een bewerking onrechtmatige uitbreiding van toegangsrechten is vereist, wordt de gebruiker op het beveiligde bureaublad gevraagd een bevoegde gebruikersnaam en bevoegd wachtwoord in te voeren. Als de gebruiker geldige referenties invoert, wordt de bewerking voortgezet met de hoogst beschikbare bevoegdheid. 
  - *Vragen om toestemming op het beveiligde bureaublad*: wanneer voor een bewerking voor een niet-Windows-toepassing uitbreiding van toegangsrechten is vereist, wordt de gebruiker op het beveiligde bureaublad gevraagd om Toestaan of Weigeren te selecteren. Als de gebruiker Toestaan selecteert, wordt de bewerking voortgezet met de hoogst beschikbare bevoegdheid voor de gebruiker. 
  - *Vragen om referenties*: wanneer voor een bewerking onrechtmatige uitbreiding van toegangsrechten is vereist, wordt de gebruiker gevraagd een gebruikersnaam en wachtwoord voor een account met beheerdersrechten in te voeren. Als de gebruiker geldige referenties invoert, wordt de bewerking voortgezet met de toepasselijke bevoegdheid. 
  - *Vragen om toestemming*: wanneer voor een bewerking uitbreiding van toegangsrechten is vereist, wordt de gebruiker gevraagd om Toestaan of Weigeren te selecteren. Als de gebruiker Toestaan selecteert, wordt de bewerking voortgezet met de hoogst beschikbare bevoegdheid voor de gebruiker.  
  - *Vragen om toestemming voor niet-Windows binaire bestanden*: wanneer voor een bewerking voor een niet-Windows-toepassing uitbreiding van toegangsrechten is vereist, wordt de gebruiker op het beveiligde bureaublad gevraagd om Toestaan of Weigeren te selecteren. Als de gebruiker Toestaan selecteert, wordt de bewerking voortgezet met de hoogst beschikbare bevoegdheid voor de gebruiker.   
  
  **Standaardinstelling**: vragen om toestemming op het beveiligde bureaublad
  
- **Minimale sessiebeveiliging voor op NTLM SSP-gebaseerde clients**  
  Via deze beveiligingsinstelling kan een client de onderhandeling van een 128-bits versleuteling en/of een NTLMv2-sessiebeveiliging vereisen. Deze waarden zijn afhankelijk van de beveiligingsinstellingswaarde van het LAN Manager-verificatieniveau. U kunt kiezen uit de volgende opties:
  - NTLMv2-sessiebeveiliging vereisen: de verbinding mislukt als niet over het NTLMv2-protocol wordt onderhandeld. 
  - *128-bits versleuteling vereisen*: de verbinding mislukt als niet wordt onderhandeld over sterke versleuteling (128-bits).
  - *NTLMv2 en 128-bits versleuteling vereisen*. 

  **Standaardinstelling**: NTLM V2-128-versleuteling vereisen
  
- **Gedrag bij verwijderen van smartcard**  
  Met deze beveiligingsinstelling bepaalt u wat er gebeurt wanneer de smartcard van een aangemelde gebruiker uit de lezer van de smartcard wordt verwijderd. U kunt kiezen uit de volgende opties:
  - *Geen actie*. 
  - *Werkstation vergrendelen*: het werkstation wordt vergrendeld wanneer de smartcard wordt verwijderd, zodat gebruikers de ruimte kunnen verlaten, hun smartcard met zich mee kunnen nemen en nog steeds een beveiligde sessie kunnen beheren.
  - *Afmelden forceren*: de gebruiker wordt automatisch afgemeld wanneer de smartcard wordt verwijderd.
  - *Verbinding verbreken met sessie met Extern bureaublad*: als de smartcard wordt verwijderd, wordt de sessie verbroken zonder de gebruiker af te melden. Zo kan de gebruiker de smartcard plaatsen en de sessie later of op een andere met smartcardlezer uitgeruste computer hervatten zonder zich opnieuw te moeten aanmelden. Als de sessie lokaal is, werkt dit beleid op dezelfde manier als Werkstation vergrendelen.  <br><br>

  **Standaardinstelling**: Werkstation vergrendelen
  
- **Anonieme inventarisatie van SAM-accounts en -shares blokkeren**  
  Met deze beveiligingsinstelling bepaalt u of anonieme inventarisatie van SAM-accounts en shares is toegestaan. Windows staat anonieme gebruikers toe bepaalde activiteiten uit te voeren, zoals het inventariseren van de namen van domeinaccounts en netwerkshares. Dit is bijvoorbeeld handig wanneer een beheerder toegang wil verlenen aan gebruikers in een vertrouwd domein dat geen wederzijdse vertrouwensrelatie onderhoudt. Als u anonieme inventarisatie van SAM-accounts en shares niet wilt toestaan, stelt u dit beleid in op *Ja*.
  
  **Standaardinstelling**: Ja
  
- **Externe aanmelding met een leeg wachtwoord blokkeren**  
  Met deze beveiligingsinstelling bepaalt u of de lokale accounts die niet zijn beveiligd met een wachtwoord kunnen worden gebruikt om aan te melden vanaf andere locaties dan de fysieke computerconsole. Bij inschakeling moet voor aanmelden met lokale accounts die niet zijn beveiligd met een wachtwoord het toetsenbord van de computer worden gebruikt. 

  *Waarschuwing*: op computers die zich niet in een fysiek beveiligde locatie bevinden, moeten altijd beleidsregels voor sterke wachtwoorden voor alle lokale gebruikersaccounts worden gehandhaafd. Anders kan iedereen die fysiek toegang tot de computer heeft, zich aanmelden met een gebruikersaccount zonder wachtwoord. Dit is met name belangrijk voor draagbare computers. 

  Als u dit beveiligingsbeleid toepast op de groep Iedereen, kan niemand zich aanmelden via Extern bureaublad-services. Deze instelling heeft geen invloed op aanmeldingen die gebruikmaken van domeinaccounts. Voor toepassingen die gebruikmaken van externe interactieve aanmeldingen is het mogelijk om deze instelling te omzeilen.
  
  **Standaardinstelling**: Ja
  
- **Gedrag bij vragen om benodigde bevoegdheden van standaardgebruikers**  
  Met deze beleidsinstelling wordt het gedrag voor het vragen om benodigde bevoegdheden voor standaardgebruikers gedefinieerd. 
  - *Aanvragen voor benodigde bevoegdheden automatisch weigeren*: wanneer voor een bewerking onrechtmatige uitbreiding van toegangsrechten is vereist, wordt een configureerbaar foutbericht weergegeven met de melding dat de toegang is geweigerd. Een onderneming waar bureaubladen als standaardgebruikers worden uitgevoerd, kan deze instelling kiezen om het aantal telefoontje naar de helpdesk te beperken. 
  - *Vragen om referenties op het beveiligde bureaublad*: wanneer voor een bewerking onrechtmatige uitbreiding van toegangsrechten is vereist, wordt de gebruiker op het beveiligde bureaublad gevraagd een andere gebruikersnaam en bevoegd wachtwoord in te voeren. Als de gebruiker geldige referenties invoert, wordt de bewerking voortgezet met de toepasselijke bevoegdheid. 
  - *Vragen om referenties*: wanneer voor een bewerking onrechtmatige uitbreiding van toegangsrechten is vereist, wordt de gebruiker gevraagd een gebruikersnaam en wachtwoord voor een account met beheerdersrechten in te voeren. Als de gebruiker geldige referenties invoert, wordt de bewerking voortgezet met de toepasselijke bevoegdheid.  
  
  **Standaardinstelling**: aanvragen voor benodigde bevoegdheden automatisch weigeren
  
- **Modus 'Door administrator goedkeuren' vereisen voor beheerders**  
  Met deze beleidsinstelling wordt het gedrag van alle instellingen voor Gebruikersaccountbeheer (UAC) voor de computer bepaald. Als u deze instelling wijzigt, moet u de computer opnieuw opstarten. U kunt kiezen uit de volgende opties:   
  - *Niet geconfigureerd*: de modus Door administrator goedkeuren en alle gerelateerde UAC-beleidsinstellingen zijn uitgeschakeld. Opmerking: als deze instelling is uitgeschakeld, ontvangt u een melding van Security Center dat de algehele beveiliging van het besturingssysteem is verminderd. 
  - *Ja*: de modus Door administrator goedkeuren is ingeschakeld. Dit beleid moet zijn ingeschakeld en de gerelateerde UAC-beleidsinstellingen moeten op de juiste wijze zijn ingesteld om ervoor te zorgen dat het ingebouwde administratoraccount en alle andere gebruikers die lid zijn van de groep Administrators kunnen worden uitgevoerd in de modus Door administrator goedkeuren.  
  
  **Standaardinstelling**: Ja
  
- **Anonieme inventarisatie van SAM-accounts voorkomen**  
  Met deze beveiligingsinstelling wordt bepaald welke aanvullende machtigingen worden toegekend aan anonieme verbindingen met de computer. Windows staat anonieme gebruikers toe bepaalde activiteiten uit te voeren, zoals het inventariseren van de namen van domeinaccounts en netwerkshares. Dit is bijvoorbeeld handig wanneer een beheerder toegang wil verlenen aan gebruikers in een vertrouwd domein dat geen wederzijdse vertrouwensrelatie onderhoudt. Met deze beveiligingsoptie kunnen als volgt aanvullende beperkingen voor anonieme verbinding worden toegepast: 
  - *Ja*: geen inventarisatie van SAM-accounts toestaan. Met deze optie wordt de instelling Iedereen bij de beveiligingsmachtigingen voor resources vervangen door Geverifieerde gebruikers.
  - *Niet geconfigureerd*: geen aanvullende beperkingen. Vertrouwen op standaardmachtigingen.  
  
  **Standaardinstelling**: Ja
  
- **Externe aanroepen van Security Accounts Manager toestaan**  
  Met deze beleidsinstelling kunt u verbindingen voor externe procedureaanroepen van SAM beperken. Als deze instelling niet is geselecteerd, wordt de standaard security descriptor gebruikt.
  
  **Standaardinstelling**: *O:BAG:BAD:(A;;RC;;;BA)*

- **De modus 'Door administrator goedkeuren' gebruiken**  
  Met deze beleidsinstelling wordt het gedrag van de modus 'Door administrator goedkeuren' voor het ingebouwde administratoraccount bepaald. U kunt kiezen uit de volgende opties: 
  - *Ja*: de modus Door administrator goedkeuren wordt gebruikt voor het ingebouwde administratoraccount. Voor elke bewerking waarvoor onrechtmatige uitbreiding van toegangsrechten is vereist, wordt de gebruiker standaard gevraagd de bewerking goed te keuren. 
  - *Niet geconfigureerd*: met het ingebouwde administrator worden alle toepassingen met volledige administratorbevoegdheid uitgevoerd.  

  **Standaardinstelling**: Ja
  
- **Toepassingen met UI-toegang toestaan voor veilige locaties**  
  Met deze beleidsinstelling wordt bepaald of UIA-programma's (User Interface Accessibility of UIAcces) het beveiligde bureaublad automatisch kunnen uitschakelen voor het vragen om benodigde bevoegdheden die door een standaardgebruiker. 
  - *Ja*: UIA-programma's, waaronder Windows Hulp op afstand, kunnen automatisch het beveiligde bureaublad uitschakelen bij vragen om benodigde bevoegdheden. Als u de beleidsinstelling Gebruikersaccountbeheer: naar het beveiligd bureaublad overschakelen tijdens het vragen om benodigde bevoegdheden niet uitschakelt, worden de vragen weergegeven op het bureaublad van de interactieve gebruiker in plaats op van het beveiligde bureaublad. 
  - *Niet geconfigureerd*: het beveiligde bureaublad kan alleen worden uitgeschakeld door de gebruiker van het interactieve bureaublad of door het uitschakelen van de beleidsinstelling Gebruikersaccountbeheer: naar het beveiligde bureaublad overschakelen tijdens het vragen om benodigde bevoegdheden.  

  **Standaardinstelling**: Ja

- **Installatie van toepassingen detecteren en vragen om benodigde bevoegdheden**  
  Met deze beleidsinstelling wordt het gedrag van detectie voor installatie van toepassingen voor de computer bepaald. U kunt kiezen uit de volgende opties: 
  - *Ingeschakeld*: wanneer een installatiepakket van een toepassing wordt gedetecteerd waarvoor onrechtmatige uitbreiding van toegangsrechten is vereist, wordt de gebruiker gevraagd een gebruikersnaam en wachtwoord voor een account met beheerdersrechten in te voeren. Als de gebruiker geldige referenties invoert, wordt de bewerking voortgezet met de toepasselijke bevoegdheid. 
  - *Uitgeschakeld*: installatiepakketten voor toepassingen worden niet gedetecteerd en worden niet om benodigde bevoegdheden gevraagd. Ondernemingen waar bureaubladen als standaardgebruikers worden uitgevoerd en die gebruikmaken van gedelegeerde installatietechnologieën, zoals Installatie van software van groepsbeleid of Systems Management Server (SMS), moeten deze beleidsinstelling uitschakelen. In dit geval is de detectie van installatieprogramma's niet nodig.  
  
  **Standaardinstelling**: Ja
  
- **Voorkomen dat de hashwaarde van LAN manager wordt opgeslagen opslaan bij volgende wachtwoordwijziging**  
  Met deze beveiligingsinstelling wordt bepaald of bij de volgende wachtwoordwijziging de hashwaarde van LAN Manager (LM) voor het nieuwe wachtwoord wordt opgeslagen. De LM-hash is relatief zwak en gevoelig voor aanvallen in vergelijking met de cryptografisch sterkere NT-hash van Windows. Omdat de LM-hash in de beveiligingsdatabase van de lokale computer wordt opgeslagen, kunnen de wachtwoorden worden aangetast als de beveiligingsdatabase wordt aangevallen.
  
  **Standaardinstelling**: Ja

- **Schrijffouten in bestanden en registers in locaties per gebruiker virtualiseren**  
  Met deze beleidsinstelling wordt bepaald of schrijffouten voor toepassingen worden omgeleid naar gedefinieerde register- en bestandssysteemlocaties. Met deze beleidsinstelling worden toepassingen beperkt die als administrator worden uitgevoerd en waarvoor toepassingsgegevens van de runtime naar *%ProgramFiles%* , *%Windir%* , *%Windir%\system32* of *HKLM\Software* worden schrijven.
  
  **Standaardinstelling**: Ja

### <a name="ms-security-guide"></a>MS-beveiligingshandleiding  

Raadpleeg [Policy CSP - MSSecurityGuide](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-mssecurityguide) (Beleids-CSP - MSSecurityGuide) in de Windows-documentatie voor meer informatie.  

- **UAC-beperkingen toepassen op lokale accounts bij netwerkaanmelding**  
  **Standaardinstelling**: ingeschakeld
  
- **Configuratie voor starten van stuurprogramma voor SMB-v1-client**  
  **Standaardinstelling**: uitgeschakeld stuurprogramma
  
- **SMB-v1-server**  
  **Standaardinstelling**: uitgeschakeld
  
- **Samenvattingsverificatie**  
  **Standaardinstelling**: uitgeschakeld
  
- **SEHOP (Structured Exception Handler Overwrite Protection)**  
  **Standaardinstelling**: ingeschakeld
  
### <a name="mss-legacy"></a>MSS Legacy  

Raadpleeg [Policy CSP - MSSLegacy](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-msslegacy) (Beleids-CSP - MSSLegacy) in de Windows-documentatie voor meer informatie.  

- **Beveiligingsniveau voor routering van IP-bron voor netwerk**  
  **Standaardinstelling**: hoogste beveiliging  
  
- **Aanvragen voor NetBIOS-naamreleases van netwerk negeren met uitzondering van WINS-servers**  
  **Standaardinstelling**: ingeschakeld
  
- **Beveiligingsniveau voor routering van IPv6-bron voor netwerk**  
  **Standaardinstelling**: hoogste beveiliging

- **ICMP-omleidingen van netwerk overschrijven door OSPF gegenereerde omleidingen**  
  **Standaardinstelling**: uitgeschakeld
  
### <a name="power"></a>Voeding  

Raadpleeg [Policy CSP - Power](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-power) (Beleids-CSP - Voeding) in de Windows-documentatie voor meer informatie.  

- **Wachtwoord bij activering vereisen tijdens aansluiting op netstroom**  
  Met deze beleidsinstelling kunt u opgeven of de gebruiker om een wachtwoord wordt gevraagd als de slaapstand wordt uitgeschakeld. Als u deze beleidsinstelling inschakelt of niet configureert, wordt de gebruiker om een wachtwoord gevraagd wanneer de slaapstand wordt uitgeschakeld. Als u deze beleidsinstelling uitschakelt, wordt de gebruiker niet om een wachtwoord gevraagd wanneer de slaapstand wordt uitgeschakeld.
  
  **Standaardinstelling**: ingeschakeld
  
- **Stand-bystatussen tijdens slaapstand bij gebruik van accu**  
  Met deze beleidsinstelling wordt bepaald of de stand-bystatussen kunnen worden ingeschakeld met Windows wanneer de computer in de slaapstand wordt gezet. Als u deze beleidsinstelling inschakelt of niet configureert, worden in Windows de stand-bystatussen gebruikt om de computer in een slaapstand te zetten. Als u deze beleidsinstelling uitschakelt, zijn de stand-bystatussen (S1-S3) niet toegestaan.
  
  **Standaardinstelling**: uitgeschakeld
  
- **Stand-bystatussen tijdens slaapstand in aangesloten toestand**  
  Met deze beleidsinstelling wordt bepaald of de stand-bystatussen kunnen worden ingeschakeld met Windows wanneer de computer in de slaapstand wordt gezet. Als u deze beleidsinstelling inschakelt of niet configureert, worden in Windows de stand-bystatussen gebruikt om de computer in een slaapstand te zetten. Als u deze beleidsinstelling uitschakelt, zijn de stand-bystatussen (S1-S3) niet toegestaan.
  
  **Standaardinstelling**: uitgeschakeld
  
- **Wachtwoord bij activering vereisen bij gebruik van accu**  
  Met deze beleidsinstelling kunt u opgeven of de gebruiker om een wachtwoord wordt gevraagd als de slaapstand wordt uitgeschakeld. Als u deze beleidsinstelling inschakelt of niet configureert, wordt de gebruiker om een wachtwoord gevraagd wanneer de slaapstand wordt uitgeschakeld. Als u deze beleidsinstelling uitschakelt, wordt de gebruiker niet om een wachtwoord gevraagd wanneer de slaapstand wordt uitgeschakeld.
  
  **Standaardinstelling**: ingeschakeld
  
### <a name="remote-desktop-services"></a>Extern bureaublad-services  

Zie [Beleids-CSP - RemoteDesktopServices](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotedesktopservices) in de Windows-documentatie voor meer informatie.  

- **Wachtwoord opslaan blokkeren**  
  Hiermee bepaalt u of wachtwoorden op deze computer kunnen worden opgeslagen vanuit een verbinding met extern bureaublad. Als u deze instelling inschakelt, wordt het selectievakje voor het opslaan van het wachtwoord in de verbinding met extern bureaublad uitgeschakeld en kunnen gebruikers niet langer wachtwoorden opslaan. Wanneer gebruikers een RDP-bestand openen met behulp van een verbinding met extern bureaublad en hun instellingen opslaan, wordt een wachtwoord dat voorheen aanwezig was in het RDP-bestand verwijderd. Als u deze instelling uitschakelt of niet configureert, kan de gebruiker met behulp van de verbinding met extern bureaublad wachtwoorden opslaan.
  
   **Standaardinstelling**: ingeschakeld
  
- **Beveiligde RPC-communicatie**  
  Hiermee geeft u aan of voor een Remote Desktop Session Host-server beveiligde RPC-communicatie is vereist met alle clients of niet-beveiligde communicatie is toegestaan. U kunt deze instelling gebruiken om de beveiliging van RPC-communicatie met clients te versterken door alleen geverifieerde en versleutelde aanvragen toe te staan. Als de status is ingesteld op Ingeschakeld, accepteert Extern bureaublad-services aanvragen van RPC-clients die ondersteuning bieden voor beveiligde aanvragen en wordt niet-beveiligde communicatie met niet-vertrouwde clients niet toegestaan. Als de status is ingesteld op Uitgeschakeld, vraagt Extern bureaublad-services altijd om beveiliging voor alle RPC-verkeer. Voor RPC-clients die niet op de aanvraag reageren is echter niet-beveiligde communicatie toegestaan. Als de status is ingesteld op Niet geconfigureerd, is niet-beveiligde communicatie toegestaan. Opmerking: de RPC-interface wordt gebruikt voor het beheren en configureren van Extern bureaublad-services.
  
  **Standaardinstelling**: ingeschakeld
  
- **Stationsomleiding blokkeren**  
  Met deze beleidsinstelling geeft u aan of u de toewijzing van clientstations in een sessie van Extern bureaublad-services wilt voorkomen (stationsomleiding). Standaard wijst een Extern bureaublad-sessiehostserver clientstations automatisch toe wanneer verbinding wordt gemaakt. Toegewezen stations worden in de structuur van de sessiemap in Verkenner of Computer in de indeling *\<stationsletter>* op *\<computernaam>* weergegeven. Met deze beleidsinstelling kunt u dit gedrag negeren. Als u deze beleidsinstelling inschakelt, is clientstationsomleiding niet toegestaan in sessies van Extern bureaublad-services en is omleiding van kopieën van Klembord-bestanden niet toegestaan op computers met Windows Server 2003, Windows 8 en Windows XP. Als u deze beleidsinstelling uitschakelt, is clientstationsomleiding is altijd toegestaan. Omleiding van kopieën van Klembord-bestanden is bovendien altijd toegestaan als Klembord-omleiding is toegestaan. Als u deze beleidsinstelling niet configureert, worden omleiding van clientstations en omleiding voor kopieën van Klembord-bestanden niet opgegeven op groepsbeleidsniveau.
  
  **Standaardinstelling**: ingeschakeld
  
- **Prompt voor wachtwoord bij verbinding maken**  
  Met deze beleidsinstelling geeft u aan of de client in Extern bureaublad-services altijd wordt gevraagd om een wachtwoord wanneer deze verbinding maakt. U kunt deze instelling gebruiken om een wachtwoordprompt af te dwingen voor gebruikers die zich aanmelden bij de Extern bureaublad-services, zelfs als ze het wachtwoord in de client voor Verbinding met extern bureaublad al hebben opgegeven. Standaard kunnen gebruikers zich in Extern bureaublad-services automatisch aanmelden door een wachtwoord op te geven in de client voor Verbinding met extern bureaublad. Als u deze beleidsinstelling inschakelt, kunnen gebruikers zich niet automatisch aanmelden bij Extern bureaublad-services door het opgeven van wachtwoorden in de client voor Verbinding met extern bureaublad. Zij worden bij hun aanmelding gevraagd om een wachtwoord. Als u deze beleidsinstelling uitschakelt, kunnen gebruikers zich altijd automatisch aanmelden bij Extern bureaublad-services door het opgeven van wachtwoorden in de client voor Verbinding met extern bureaublad. Als u deze beleidsinstelling niet configureert, wordt automatische aanmelding niet opgegeven op groepsbeleidsniveau. 
  
  **Standaardinstelling**: ingeschakeld
  
- **Versleutelingsniveau van Verbinding met extern bureaublad-services**  
  Hiermee geeft u op of het gebruik van een specifiek versleutelingsniveau voor beveiligde communicatie tussen clientcomputers en Extern bureaublad-sessiehostservers tijdens Remote Desktop Protocol (RDP)-verbindingen is vereist. Dit beleid is alleen van toepassing wanneer u systeemeigen RDP-versleuteling gebruikt. Systeemeigen RDP-versleuteling (in plaats van SSL-versleuteling) wordt echter niet aanbevolen. Dit beleid geldt niet voor SSL-versleuteling. Als u deze beleidsinstelling inschakelt, moet in alle communicatie tussen clients en extern bureaublad-sessiehostservers tijdens externe verbindingen de versleutelingsmethode worden gebruikt die is opgegeven in deze instelling. Het versleutelingsniveau is standaard ingesteld op Hoog. De volgende versleutelingsmethoden zijn beschikbaar:  
  - *Hoog*: met de instelling Hoog worden gegevens die van de client naar de server en de server naar de client worden verzonden met behulp van 128-bits versleuteling versleuteld. Gebruik dit versleutelingsniveau in omgevingen die enkel 128-bits clients bevatten (bijvoorbeeld: clients met Verbinding met extern bureaublad). Clients die geen ondersteuning bieden voor dit versleutelingsniveau kunnen geen verbinding maken met Extern bureaublad-sessiehostservers.  
  - *Compatibel met client*: met de instelling Compatibel met client worden gegevens die worden verzonden tussen de client en de server op de maximaal door de client ondersteunde sleutelsterkte versleuteld. Gebruik dit versleutelingsniveau in omgevingen met clients die geen ondersteuning bieden voor 128-bits versleuteling.  
  - *Laag*: met de instelling Laag worden alleen gegevens die van de client naar de server worden verzonden met behulp van 56-bits versleuteling versleuteld.  
  
  Als u deze instelling uitschakelt of niet configureert, wordt het versleutelingsniveau dat moet worden gebruikt voor externe verbindingen met Extern bureaublad-sessiehostservers niet afgedwongen via groepsbeleid. Belangrijke FIPS-compatibiliteit kan worden geconfigureerd via de systeemcryptografie. FIPS-compatibele algoritmes gebruiken voor versleuteling, hashing en ondertekening van de instellingen in groepsbeleid (onder Computerconfiguratie\Windows-instellingen\Beveiligingsinstellingen\Lokaal Beleid\Beveiligingsopties.) Met de instelling FIPS-compatibiliteit worden gegevens die van de client naar de server en de server aan de client worden verzonden, versleuteld met de FIPS 140-versleutelingsalgoritmen (FIPS: Federal Information Processing Standard) met behulp van cryptografische modules van Microsoft. Gebruik dit versleutelingsniveau wanneer voor de communicatie tussen clients en de Extern bureaublad-sessiehostservers de hoogste mate van versleuteling is vereist.
  
  **Standaardinstelling**: Hoog
  
### <a name="remote-management"></a>Extern beheer  

Zie [Beleids-CSP - RemoteManagement](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remotemanagement) in de Windows-documentatie voor meer informatie.  

- **Referenties opslaan voor Uitvoeren als blokkeren**  
  Basisverificatie voor clients
  
  **Standaardinstelling**: ingeschakeld
  
- **Basisverificatie**  
  Met deze beleidsinstelling kunt u bepalen of de WinRM-service (WinRM: Windows Remote Management) basisverificatie accepteert van een externe client. Als u deze beleidsinstelling inschakelt, accepteert de WinRM-service basisverificatie van een externe client. Als u deze beleidsinstelling uitschakelt of niet configureert, accepteert de WinRM-service geen basisverificatie van een externe client.
  
  **Standaardinstelling**: uitgeschakeld
  
- **Digest-verificatie van clients blokkeren**  
  Met deze beleidsinstelling kunt u bepalen of de WinRM-client gebruikmaakt van Digest-verificatie. Als u deze beleidsinstelling inschakelt, gebruikt de WinRM-client geen Digest-verificatie. Als u deze beleidsinstelling uitschakelt of niet configureert, gebruikt de WinRM-client Digest-verificatie.
  
  **Standaardinstelling**: ingeschakeld
  
- **Niet-versleuteld verkeer**  
  Met deze beleidsinstelling kunt u bepalen of de WinRM-service (WinRM: Windows Remote Management) niet-versleutelde berichten verzendt en ontvangt via het netwerk. Als u deze beleidsinstelling inschakelt, verzendt en ontvangt de WinRM-client niet-versleutelde berichten via het netwerk. Als u deze beleidsinstelling inschakelt, verzendt en ontvangt de WinRM-client alleen versleutelde berichten via het netwerk.  
  
  **Standaardinstelling**: uitgeschakeld
  
- **Niet-versleuteld clientverkeer**  
  Met deze beleidsinstelling kunt u bepalen of de WinRM-client (Windows Remote Management-client) via het netwerk niet-versleutelde berichten verzendt en ontvangt. Als u deze beleidsinstelling inschakelt, verzendt en ontvangt de WinRM-client niet-versleutelde berichten via het netwerk. Als u deze beleidsinstelling inschakelt, verzendt en ontvangt de WinRM-client alleen versleutelde berichten via het netwerk.
  
  **Standaardinstelling**: uitgeschakeld
  
- **Basisverificatie voor clients**  
  Met deze beleidsinstelling kunt u bepalen of de WinRM-client gebruikmaakt van basisverificatie. Als u deze beleidsinstelling inschakelt, gebruikt de WinRM-client basisverificatie. Als WinRM is geconfigureerd voor het gebruik van HTTP-transport, worden de gebruikersnaam en het wachtwoord via het netwerk als niet-versleutelde tekst verzonden. Als u deze beleidsinstelling uitschakelt of niet configureert, gebruikt de WinRM-client geen basisverificatie.
  
  **Standaardinstelling**: uitgeschakeld
  

### <a name="remote-procedure-call"></a>Externe procedureaanroep  

Zie [Beleids-CSP - RemoteProcedureCall](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-remoteprocedurecall) in de Windows-documentatie voor meer informatie.  

- **Opties voor RPC niet-geverifieerde clients**  
  Met deze beleidsinstelling bepaalt u hoe de RPC-serverruntime omgaat met niet-geverifieerde RPC-clients die verbinding maken met RPC-servers. Deze beleidsinstelling heeft gevolgen voor alle RPC-toepassingen. In een domeinomgeving dient u voorzichtig te zijn met het gebruik van deze beleidsinstelling, aangezien het gevolgen kan hebben voor een breed scala aan functies, waaronder de verwerking van het groepsbeleid zelf. Het kan zijn dat het herstellen van een wijziging in deze beleidsinstelling handmatig op elke betreffende machine moet worden uitgevoerd. Deze beleidsinstelling moet nooit worden toegepast op een domeincontroller. Als u deze beleidsinstelling uitschakelt, maakt de RPC-serverruntime gebruik van de waarde 'Geverifieerd' op Windows Client en van de waarde 'Geen' op Windows Server-versies die ondersteuning bieden voor deze instelling. Als u deze beleidsinstelling niet configureert, blijft deze uitgeschakeld. De RPC-serverruntime gedraagt zich alsof deze is ingeschakeld met de waarde 'Geverifieerd' die wordt gebruikt voor Windows Client en de waarde 'Geen' die wordt gebruikt voor Server SKU's die ondersteuning bieden voor deze beleidsinstelling. Als u deze beleidsinstelling inschakelt, zorgt deze ervoor dat de RPC-serverruntime beperkingen oplegt aan niet-geverifieerde RPC-clients die verbinding maken met RPC-servers die op een computer worden uitgevoerd. Een client zal worden beschouwd als een geverifieerde client als deze een named pipe gebruikt om te communiceren met de server of als deze RPC-beveiliging gebruikt. RPC-interfaces die specifiek hebben verzocht om toegankelijk te zijn voor niet-geverifieerde clients kunnen worden uitgezonderd van deze beperking, afhankelijk van de geselecteerde waarde voor deze instelling.  
  - Via *Geen* kunnen alle RPC-clients verbinding maken met de RPC-Servers die worden uitgevoerd op de computer waarop de beleidsinstelling wordt toegepast. 
  - Via *Geverifieerd* kunnen alleen geverifieerde RPC-clients (volgens bovenstaande definitie) verbinding maken met RPC-servers die worden uitgevoerd op de computer waarop de beleidsinstelling wordt toegepast. Er kan een uitzondering worden gemaakt op interfaces wanneer daarvoor een aanvraag is gedaan. 
  - Via *Geverifieerd zonder uitzonderingen* kunnen alleen geverifieerde RPC-clients (volgens bovenstaande definitie) verbinding maken met RPC-servers die worden uitgevoerd op de computer waarop de beleidsinstelling wordt toegepast. Er zijn geen uitzonderingen toegestaan. Opmerking: deze beleidsinstelling wordt pas toegepast wanneer het systeem opnieuw wordt opgestart.  

  **Standaardinstelling**: Geverifieerd

### <a name="search"></a>Zoeken  

Zie [Beleids-CSP - Search](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-search) in de Windows-documentatie voor meer informatie.  

- **Indexeren van versleutelde items uitschakelen**  
  Hiermee kunt u het indexeren van items toestaan of verbieden. Deze schakeloptie dient voor de Windows Search-indexeerfunctie. Hiermee bepaalt u of items die zijn versleuteld, worden geïndexeerd, zoals de bestanden met Windows Information Protection (WIP). Wanneer het beleid wordt ingeschakeld, worden de items met WIP-beveiliging geïndexeerd en worden de metagegevens opgeslagen op een niet-versleutelde locatie. De metagegevens bevatten gegevens zoals het bestandspad en de wijzigingsdatum. Als het beleid is uitgeschakeld, worden de items met WIP-beveiliging niet geïndexeerd en worden ze niet weergegeven in de resultaten in Cortana of Verkenner. Als er te veel mediabestanden met WIP-beveiliging op het apparaat staan, kunnen de prestaties bij gebruik van foto's en Groove-apps ook worden beïnvloed.
  
**Standaardinstelling**: Ja
  
### <a name="smart-screen"></a>SmartScreen  

Zie [Beleids-CSP - SmartScreen](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-smartscreen) in de Windows-documentatie voor meer informatie.  

- **Uitvoering van niet-geverifieerde bestanden blokkeren**  
  Verhinderen dat een gebruiker niet-geverifieerde bestanden uitvoert. 
  - *Niet geconfigureerd*: werknemers kunnen SmartScreen-waarschuwingen negeren en schadelijke bestanden uitvoeren. 
  - *Ja*: werknemers kunnen SmartScreen-waarschuwingen negeren en schadelijke bestanden uitvoeren.

  **Standaardinstelling**: Ja

<!-- Not currently available? - **Block unverified file download**  
  By default, Microsoft Edge allows users to bypass (ignore) the Windows Defender SmartScreen warnings about potentially malicious files, allowing them to continue downloading the unverified file(s). Enabling this policy prevents users from bypassing the warnings, blocking them from downloading of the unverified file(s).
  
  **Default**: Yes
 --> 
- **SmartScreen vereisen voor apps en bestanden**  
  Hiermee kunnen IT-beheerders SmartScreen voor Windows configureren.

  **Standaardinstelling**: Ja
  
### <a name="system"></a>Systeem  

Zie [Beleids-CSP - System](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system) in de Windows-documentatie voor meer informatie.  

- **Initialisatie van systeemstartstuurprogramma**  
  Met deze beleidsinstelling kunt u opgeven welke systeemstartstuurprogramma's worden geïnitialiseerd op basis van een classificatie die is bepaald door het systeemstartstuurprogramma Early Launch Antimalware. Het systeemstartstuurprogramma Early Launch Antimalware kan de volgende classificaties retourneren voor elk systeemstartstuurprogramma: 
  - *Goed*: het stuurprogramma is ondertekend en is niet gemanipuleerd.  
  - *Ongeldig*: het stuurprogramma is geïdentificeerd als schadelijke software. Het is raadzaam om niet toe te staan dat bekende ongeldige stuurprogramma's worden geïnitialiseerd. 
  - *Ongeldig, maar vereist voor opstarten*: het stuurprogramma is geïdentificeerd als schadelijke software, maar de computer kan niet worden opgestart zonder dat dit stuurprogramma wordt geladen. 
  - *Onbekend*: dit stuurprogramma is niet beoordeeld door de toepassing voor de detectie van schadelijke software, en is niet geclassificeerd door het systeemstartstuurprogramma Early Launch Antimalware.  

  Als u deze beleidsinstelling inschakelt, kunt u kiezen welke systeemstartstuurprogramma's moeten worden geïnitialiseerd als de computer de volgende keer wordt gestart. Als u dit beleid uitschakelt of niet configureert, worden de systeemstartstuurprogramma's geïnitialiseerd die zijn aangemerkt als Goed, Onbekend of Ongeldig maar essentieel voor opstarten, en wordt de initialisatie van stuurprogramma's die zijn aangemerkt als Ongeldig overgeslagen. Als uw toepassing voor de detectie van schadelijke software niet het systeemstartstuurprogramma Early Launch Antimalware bevat of als dit programma is uitgeschakeld, is deze instelling niet van invloed en worden alle systeemstartstuurprogramma's geïnitialiseerd.  
  
  **Standaardinstelling**: Goed, Onbekend en Ongeldig maar essentieel


### <a name="wi-fi"></a>Wi-Fi  

Zie [Beleids-CSP - Wi-Fi](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-wifi) in de Windows-documentatie voor meer informatie.  

- **Internetverbinding delen blokkeren**  
  Hiermee geeft u op of het delen van internet op het apparaat mogelijk is.  

  **Standaardinstelling**: Ja  

- **Automatisch verbinding maken met Wi-Fi-hotspots blokkeren**  
  Toestaan of weigeren dat het apparaat automatisch verbinding maakt met Wi-Fi-hotspots.  

  **Standaardinstelling**: Ja  
  
### <a name="windows-connection-manager"></a>Windows-verbindingsbeheer  

Zie [Beleids-CSP - WindowsConnectionManager](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsconnectionmanager) in de Windows-documentatie voor meer informatie.  

- **Verbinding met niet-domeinnetwerken blokkeren**  
  Met deze beleidsinstelling wordt voorkomen dat computers tegelijk verbinding maken met zowel een domein- als niet-domeinnetwerk. Als deze instelling is ingeschakeld, reageert de computer op automatische en handmatige pogingen om verbinding te maken met een netwerk op basis van de volgende omstandigheden: 
  - Automatische pogingen om verbinding te maken Wanneer de computer al met een domeinnetwerk is verbonden, worden alle automatische pogingen om verbinding te maken met niet-domeinnetwerken geblokkeerd. Wanneer de computer al met een niet-domeinnetwerk is verbonden, worden alle automatische pogingen om verbinding te maken met domeinnetwerken geblokkeerd. 
  - Handmatige pogingen om verbinding te maken Wanneer de computer al met een niet-domein- of domeinnetwerk verbonden is via andere media dan Ethernet, en een gebruiker probeert in strijd met deze beleidsinstelling een handmatige verbinding in te stellen met een extra netwerk, wordt de bestaande netwerkverbinding verbroken en de handmatige verbinding toegestaan. Wanneer de computer al met een niet-domein- of domeinnetwerk verbonden is via Ethernet, en een gebruiker probeert in strijd met deze beleidsinstelling een handmatige verbinding in te stellen met een extra netwerk, wordt de bestaande Ethernetverbinding gehandhaafd en de handmatige verbinding geblokkeerd.  

  Als deze beleidsinstelling niet is geconfigureerd of is uitgeschakeld, mogen computers tegelijk met zowel domein- als niet-domeinnetwerken verbinding maken.  

  **Standaardinstelling**: ingeschakeld
  
### <a name="windows-defender"></a>Windows Defender  

Zie [Beleids-CSP - Defender](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender) in de Windows-documentatie voor meer informatie.  

- **Inkomende e-mailberichten scannen**  
  Hiermee kunt u het scannen van e-mail toestaan of niet toestaan.
  
  **Standaardinstelling**: Ja  

- **Onderliggend procestype voor starten van Office-apps**  
  Office-apps mogen geen onderliggende processen maken. Dit is inclusief Word, Excel, PowerPoint, OneNote en Access. Dit is typisch malwaregedrag, met name voor op macro's gebaseerde aanvallen die Office-apps proberen te gebruiken om schadelijke uitvoerbare bestanden te starten of te downloaden.
  
  **Standaardinstelling**: Blokkeren
  
- **Voorbeeld van een Defender-toestemmingstype voor indiening**  
  Hiermee wordt het gebruikerstoestemmingsniveau in Windows Defender gecontroleerd om gegevens te verzenden. Als de vereiste toestemming al is verleend, worden de gegevens door Windows Defender ingediend. Als dit niet het geval is (en als de gebruiker heeft opgegeven dat deze vraag nooit mag worden gesteld), wordt de gebruikersinterface geopend om de gebruiker om toestemming te vragen (wanneer Defender/AllowCloudProtection is toegestaan) voordat gegevens worden verzonden.
  
  **Standaardinstelling**: veilige voorbeelden automatisch verzenden 
  
- **Interval voor handtekeningupdates (in uren)**  
  Interval voor Defender-handtekeningupdates (in uren)
  
  **Standaardinstelling**: 4
  
- **Uitvoeringstype van de payload die is gedownload met een script**  
  Uitvoeringstype van de payload die is gedownload met een Defender-script
  
  **Standaardinstelling**: Blokkeren
  
- **Type referentiediefstal voorkomen**  
  Windows Defender Credential Guard maakt gebruik van op virtualisatie gebaseerde beveiliging om geheime gegevens te isoleren. Zo hebt u er alleen met bevoegde systeemsoftware toegang toe. Niet-geautoriseerde toegang tot deze geheime gegevens kan leiden tot pogingen tot diefstal, zoals een Pass-the-Hash- of Pass-the-Ticket-aanval. Met Windows Defender Credential Guard worden deze aanvallen voorkomen, doordat NTLM-wachtwoord-hashes, Kerberos Ticket Granting Tickets en referenties die door toepassingen zijn opgeslagen als domeinreferenties worden beschermd.
  
  **Standaardinstelling**: Inschakelen

- **Uitvoertype vanuit e-mailinhoud**  
  Deze regel voorkomt dat de volgende bestandstypen worden uitgevoerd of gestart vanuit een e-mailbericht dat wordt weergegeven in Microsoft Outlook of webmail (zoals Gmail.com of Outlook.com): uitvoerbare bestanden (zoals .exe, .dll of .scr) Script-bestanden (zoals de volgende: PowerShell .ps, VisualBasic .vbs of JavaScript .js) Script-archiefbestanden.
  
  **Standaardinstelling**: Blokkeren
  
- **Netwerkbeveiligingstype**  
  Met dit beleid kunt u netwerkbeveiliging inschakelen (blokkeren/controleren) of uitschakelen in Windows Defender Exploit Guard. Netwerkbeveiliging is een functie van Windows Defender Exploit Guard die voorkomt dat werknemers die apps gebruiken in contact komen met phishing-praktijken, sites die misbruik maken en schadelijke inhoud op internet. Dit omvat het voorkomen dat browsers van derden verbinding maken met gevaarlijke websites. Waardetype is geheel getal. Als u deze instelling inschakelt, wordt netwerkbeveiliging ingeschakeld en kunnen werknemers dit niet uitschakelen. Het gedrag kan worden beheerd met de volgende opties: Blokkeren en Controleren. Als u dit beleid inschakelt met de optie Blokkeren, kunnen gebruikers en apps geen verbinding maken met gevaarlijke domeinen. U kunt deze activiteit bekijken in Windows Defender Security Center. Als u dit beleid inschakelt met de optie Controleren, kunnen gebruikers en apps verbinding maken met gevaarlijke domeinen. Maar deze activiteit wordt nog steeds weergegeven in Windows Defender Security Center. Als u dit beleid uitschakelt, kunnen gebruikers/apps verbinding maken met gevaarlijke domeinen. U ziet geen netwerkactiviteit in Windows Defender Security Center. Als u dit beleid niet configureert, wordt netwerkblokkering standaard uitgeschakeld.
  
  **Standaardinstelling**: Inschakelen
  
- **Defender: scandag plannen**  
  Scandag voor Defender plannen.
  
  **Standaardinstelling**: Elke dag
  
- **Cloudbeveiliging**  
  Om uw pc zo goed mogelijk te beveiligen, verzendt Windows Defender gegevens naar Microsoft over problemen die worden gevonden. Microsoft analyseert die gegevens, verzamelt meer gegevens over problemen die u en andere klanten ondervinden en biedt verbeterde oplossingen.
  
  **Standaardinstelling**: Ja  

- **Defender: mogelijk ongewenste app-actie**  
  De beveiligingsfunctie tegen mogelijk ongewenste toepassingen (PUA; potentially unwanted application) in Windows Defender Antivirus kan mogelijk ongewenste toepassingen identificeren en voorkomen dat ze worden gedownload en geïnstalleerd op eindpunten in uw netwerk. Deze toepassingen worden niet beschouwd als virussen, malware of andere soorten bedreigingen, maar kunnen mogelijk acties uitvoeren op eindpunten die nadelige invloed hebben op de prestaties of het gebruik. Mogelijk ongewenste toepassingen kan ook verwijzen naar toepassingen die een slechte reputatie hebben. Standaardgedrag van mogelijk ongewenste toepassingen is: Verschillende typen softwarebundeling Advertentietoevoeging in webbrowsers Optimalisatieprogramma's voor stuurprogramma's en registers die problemen detecteren en vragen om betaling om problemen op te lossen. Ze blijven op het eindpunt en er worden geen wijzigen of optimalisaties aangebracht (ook wel bekend als 'rogue antivirus'-programma's). Deze toepassingen kunnen het risico op infectie van uw netwerk met malware verhogen, ervoor zorgen dat malware-infecties moeilijker kunnen worden geïdentificeerd en kunnen IT-resources verspillen omdat deze de toepassingen moeten opschonen.  
  
  **Standaardinstelling**: Blokkeren  

- **Macrocode verborgen in scripts**  
  Malware en andere bedreigingen kunnen proberen hun schadelijke code te verbergen in sommige scriptbestanden. Met deze regel wordt voorkomen dat scripts die verborgen lijken te zijn, worden uitgevoerd.
  
  **Standaardinstelling**: Blokkeren
  
- **Verwisselbare stations scannen tijdens een volledige scan**  
  Hiermee kan Windows Defender scannen op schadelijke en ongewenste software op verwisselbare stations (bijvoorbeeld flashstations) tijdens een volledige scan. Windows Defender Antivirus scant alle bestanden op USB-apparaten voordat ze worden uitgevoerd.
  
  **Standaardinstelling**: Ja  
  
- **Archiefbestanden scannen**  
  Archiefbestanden scannen met Defender.
  
  **Standaardinstelling**: Ja
  
- **Gedragscontrole**  
  Hiermee wordt de functie voor gedragscontrole van Windows Defender toegestaan of geweigerd. Deze sensoren zijn ingesloten in Windows 10 en verzamelen en verwerken gedragssignalen van het besturingssysteem en verzenden deze sensorgegevens naar uw persoonlijke, geïsoleerde, cloudinstantie van Microsoft Defender ATP.
  
  **Standaardinstelling**: Ja

- **Bestanden scannen die zijn geopend vanuit mappen op het netwerk**  
  Als bestanden alleen-lezen zijn, kunnen gebruikers geen gedetecteerde malware verwijderen.
  
  **Standaardinstelling**: Ja

- **Niet-vertrouwd USB-procestype**  
  Met deze regel kunnen beheerders voorkomen dat niet-ondertekende of niet-vertrouwde uitvoerbare bestanden worden uitgevoerd vanaf verwisselbare USB-stations, zoals SD-kaarten.
  
  **Standaardinstelling**: Blokkeren
  
- **Office-apps: invoeringstype voor andere processen**  
  Office-apps, inclusief Word, Excel, PowerPoint en OneNote, kunnen geen code invoeren in andere processen. Dit wordt doorgaans gebruikt door malware om schadelijke code uit te voeren in een poging om de activiteit te verbergen voor antivirusscanegines.
  
  **Standaardinstelling**: Blokkeren
  
- **Office-macrocode staat Win32-importtype toe**  
  Malware kan macrocode in Office-bestanden gebruiken om Win32-DLL's te importeren en laden, die vervolgens kunnen worden gebruikt om API-aanroepen uit te voeren voor verdere infectie in het hele systeem. Met deze regel wordt geprobeerd Office-bestanden te blokkeren die macrocode bevatten waarmee Win32-DLL's kunnen worden geïmporteerd. Dit is inclusief Word, Excel, PowerPoint en OneNote.
  
  **Standaardinstelling**: Blokkeren  
  
- **Defender op cloudblokniveau**  
  Defender op cloudblokniveau.
  
  **Standaardinstelling**: niet geconfigureerd

- **Realtimecontrole**  
  Voor Defender is realtimecontrole vereist.
  
  **Standaardinstelling**: Ja
  
- **Office-apps: uitvoerbare inhoud maken of lanceren**  
  Deze regel is gericht op typisch gedrag van verdachte en schadelijke invoegtoepassingen en scripts (extensies) die uitvoerbare bestanden maken of openen. Dit is een typische malwaretechniek. Extensies kunnen niet worden gebruikt door Office-apps. Meestal gebruiken deze extensies Windows Scripting Host (WSH-bestanden) om scripts uit te voeren die bepaalde taken automatiseren of door gebruikers gemaakt extra functies te leveren
  
  **Standaardinstelling**: Blokkeren

### <a name="windows-ink-workspace"></a>Windows Ink-werkruimte  

Raadpleeg [Policy CSP - WindowsInkWorkspace](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowsinkworkspace) (Beleids-CSP - WindowsInkWorkspace) in de Windows-documentatie voor meer informatie.  

- **Windows Ink-werkruimte**  
  Hiermee wordt opgegeven of de gebruiker toegang kan krijgen tot de Windows Ink-werkruimte. 
  - *Uitgeschakeld*: toegang tot de Ink-werkruimte is uitgeschakeld. De functie is uitgeschakeld.
  - *Ingeschakeld*: de functie Ink-werkruimte is ingeschakeld, maar de gebruiker kan geen toegang krijgen verder dan het vergrendelingsscherm.
  - *Niet geconfigureerd*: de functie Ink-werkruimte is ingeschakeld en de gebruiker kan toegang krijgen verder dan het vergrendelingsscherm.  

  **Standaardinstelling**: ingeschakeld
 
### <a name="windows-powershell"></a>Windows PowerShell  

Raadpleeg [Policy CSP - WindowsPowerShell](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-windowspowershell) (Beleids-CSP - WindowsPowerShell) in de Windows-documentatie voor meer informatie.  

- **PowerShell: logboekregistratie van Shell-script blokkeren**  
  Met deze beleidsinstelling wordt logboekregistratie van alle PowerShell-scriptinvoer naar het gebeurtenislogboek van Microsoft-Windows-PowerShell/Operational ingeschakeld. Als u deze beleidsinstelling inschakelt, wordt met Windows PowerShell de verwerking van opdrachten, scriptblokkeringen, functies en scripts via logboekregistratie bijgehouden, ongeacht of deze interactief worden aangeroepen of via automatisering. Als u deze beleidsinstelling uitschakelt, wordt logboekregistratie van PowerShell-scriptinvoer uitgeschakeld. Als u de logboekregistratie voor het aanroepen van script blokkeren inschakelt, worden gebeurtenissen door PowerShell vastgelegd bij het aanroepen van een opdracht, scriptblokkering, functie of bij het starten of stoppen van een script. Als het aanroeplogbestand wordt ingeschakeld, wordt er een groot aantal gebeurtenislogboeken gegenereerd. Opmerking: deze beleidsinstelling bestaat onder Computerconfiguratie en Gebruikersconfiguratie in de Groepsbeleidseditor. De beleidsinstelling Computerconfiguratie heeft voorrang op de beleidsinstelling Gebruikersconfiguratie.
  
  **Standaardinstelling**: ingeschakeld
 
## <a name="next-steps"></a>Volgende stappen  

[De huidige basislijn versie weer geven](security-baseline-settings-mdm-all.md?pivots=mdm-may-2019)  
[Profielen bijwerken om een nieuwe basislijn versie te gebruiken](security-baselines.md#change-the-baseline-version-for-a-profile)
