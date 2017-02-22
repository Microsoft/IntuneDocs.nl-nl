---
title: Intune-apparaatbeperkingsinstellingen voor Windows 10 | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: in dit onderwerp vindt u meer informatie over de Intune-instellingen die u kunt gebruiken voor het beheren van apparaatinstellingen en functionaliteit op Windows 10-apparaten.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 89f2d806-2e97-430c-a9a1-70688269627f
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e6e0540acd5488077ae5217f8862e3bc5462ed71
ms.openlocfilehash: 422826ded029eb8f17856e47e98f5a09dc36bc08


---

# <a name="windows-10-and-later-device-restriction-settings-in-intune-azure-preview"></a>Apparaatbeperkingsinstellingen voor Windows 10-apparaten (en hoger) in Intune Azure Preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="general"></a>Algemeen
-   **Schermafbeelding**: hiermee staat u de toe het apparaatscherm als afbeelding vast te leggen. (Alleen voor Windows 10 Mobile)
-   **Kopiëren en plakken (alleen mobiel)**: hiermee staat u kopieer- en plakbewerkingen tussen apps op het apparaat toe.
-   **Registratie handmatig ongedaan maken**: hiermee kan de gebruiker het werkplekaccount handmatig van het apparaat verwijderen.
-   **Handmatige installatie van basiscertificaat** -  
-   **Verzending van diagnostische gegevens**: mogelijke waarden zijn:
    -       **Geen**: er worden geen gegevens naar Microsoft verzonden
    -       **Basis**: beperkte informatie wordt naar Microsoft verzonden
    -       **Uitgebreid**: uitgebreide diagnostische gegevens worden naar Microsoft verzonden
    -       **Volledig**: hiermee worden dezelfde gegevens verzonden als bij Uitgebreid, aangevuld met gegevens over de apparaatstatus
-   **Camera**: hiermee kunt u het gebruik van de camera op het apparaat toestaan of blokkeren.
-   **Verwisselbare opslag**: hiermee geeft u op of er op het apparaat externe opslagapparaten, zoals een SD-kaart, kunnen worden gebruikt.
-   **Geolocatie**: hiermee geeft u aan of op het apparaat gegevens van locatieservices kunnen worden gebruikt.
-   **Gedeeld internet**: hiermee staat u het gebruik van een gedeelde internetverbinding op het apparaat toe.
-   **Opnieuw instellen van telefoon**: hiermee bepaalt u of de gebruiker de fabrieksinstellingen van het apparaat kan herstellen.
-   **USB-verbinding**: hiermee bepaalt u of apparaten via een USB-verbinding toegang kunnen krijgen tot externe opslagapparaten.
-   **AntiTheft-modus**: hiermee configureert u of de AntiTheft-modus van Windows is ingeschakeld.
-   **Meldingen van Onderhoudscentrum**: hiermee schakelt u de meldingen van Onderhoudscentrum op het vergrendelingsscherm van het apparaat in of uit (alleen voor Windows 10 Mobile).
-   **Cortana**: hiermee schakelt u de spraakassistent Cortana in en uit.
-   **Spraakopname**: hiermee kunt u het gebruik van het spraakopnameapparaat van het apparaat toestaan of blokkeren.

## <a name="password"></a>Wachtwoord
-   **Wachtwoord vereist**: hiermee geeft u aan dat de eindgebruiker een wachtwoord moet invoeren voor toegang tot het apparaat.
-   **Vereist wachtwoordtype**: hiermee geeft u aan of het wachtwoord alleen numeriek of alfanumeriek moet zijn.
-   **Minimale wachtwoordlengte**: alleen van toepassing op Windows 10 Mobile.
-   **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**: voor apparaten met Windows 10: als BitLocker is ingeschakeld op het apparaat, wordt het in de herstelmodus van BitLocker gezet nadat het aanmelden het aantal keren dat u opgeeft is mislukt. Als BitLocker niet is ingeschakeld op het apparaat, is deze instelling niet van toepassing.
Voor Windows 10 Mobile-apparaten: nadat het aanmelden het aantal keren dat u opgeeft is mislukt, wordt het apparaat gewist.
-   **Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld**: hiermee geeft u de hoeveelheid tijd op die een apparaat inactief moet zijn voordat het scherm wordt vergrendeld.
-   **Wachtwoord verloopt (dagen)**: hiermee geeft u de hoeveelheid tijd op waarna het wachtwoord van een apparaat moet worden gewijzigd.
-   **Wachtwoorden niet opnieuw gebruiken**: hiermee geeft u het aantal eerder gebruikte wachtwoorden op dat door het apparaat wordt onthouden.
-   **Wachtwoord vereisen wanneer het apparaat wordt geactiveerd vanuit een niet-actieve status**: hiermee geeft u aan dat de gebruiker een wachtwoord moet opgeven om het apparaat te ontgrendelen (alleen voor Windows 10 Mobile).
-   **Versleuteling**: hiermee schakelt u versleuteling in op bepaalde apparaten (alleen voor Windows 10 Mobile) inschakelen.
## <a name="app-store"></a>App Store

-   **App Store (alleen mobiel)**: hiermee kunt u het gebruik van de App Store op Windows 10 Mobile-apparaten inschakelen of blokkeren.
## <a name="edge-browser"></a>Edge-browser
-   **Microsoft Edge-browser (alleen mobiele apparaten)**: hiermee staat u het gebruik van de Edge-webbrowser toe op het apparaat.
-   **SmartScreen**: hiermee schakelt u SmartScreen in of uit, waarmee frauduleuze websites worden geblokkeerd.
-   **Do Not Track-headers verzenden**: hiermee configureert u de Edge-browser zodanig, dat verzoeken om niet gevolgd te worden, worden verzonden naar websites die gebruikers bezoeken.
-   **Cookies**: hiermee kunnen internetcookies in de browser op het apparaat worden opgeslagen.
-   **JavaScript**: hiermee staat u de uitvoering van scripts, zoals JavaScript, toe in de Microsoft Edge-browser.
-   **Pop-ups**: hiermee kunt u pop-upvensters in de browser blokkeren.<br>(Alleen van toepassing op Windows 10 Desktop.)
-   **Zoeksuggesties**: hiermee kan de zoekmachine sites voorstellen wanneer er zoektermen worden getypt.
-   **Intranetverkeer naar Internet Explorer sturen**: hiermee kunnen gebruikers intranetwebsites in Internet Explorer openen. <br>(Alleen Windows 10 Desktop.)
-   **Automatisch doorvoeren**: hiermee staat u gebruikers toe instellingen voor automatisch doorvoeren in de browser te wijzigen.<br>(alleen Windows 10 Desktop)
-   **Wachtwoordbeheer**: hiermee schakelt u de functie Wachtwoordbeheer van Microsoft Edge in of uit.
-   **Locatie van de lijst met websites van Bedrijfsmodus**: hiermee geeft u de plaats aan van de lijst met websites die in Bedrijfsmodus worden geopend. Gebruikers kunnen deze lijst niet bewerken.<br>(Alleen Windows 10 Desktop.)
## <a name="cloud-and-storage"></a>Cloud en opslag
-   **Microsoft-account**: hiermee staat u toe dat de gebruiker een Microsoft-account aan het apparaat kan koppelen.
-   **Niet-Microsoft-account**: hiermee staat u toe dat de gebruiker e-mailaccounts aan het apparaat kan toevoegen die niet aan een Microsoft-account zijn gekoppeld.
-   **Synchronisatie van instellingen voor Microsoft-accounts**: hiermee staat u synchronisatie tussen apparaten toe van apparaat- en app-instellingen die aan een Microsoft-account zijn gekoppeld.
## <a name="cellular-and-connectivity"></a>Mobiel en connectiviteit
-   **Dataroaming**: hiermee staat u roaming tussen netwerken toe tijdens het ophalen van data.
-   **VPN via het mobiele netwerk**: hiermee bepaalt u of het apparaat toegang kan krijgen tot VPN-verbindingen indien verbonden met een mobiel netwerk.
-   **VPN-roaming via het mobiele netwerk**: hiermee bepaalt u of het apparaat toegang kan krijgen tot VPN-verbindingen tijdens het roamen op een mobiele netwerk.
-   **Bluetooth**: hiermee bepaalt u of de gebruiker Bluetooth op het apparaat kan inschakelen en configureren.
-   **Bluetooth-detectie**: hiermee geeft u aan dat het apparaat kan worden gedetecteerd door andere Bluetooth-apparaten.
-   **Aankondigingen via Bluetooth**: hiermee geeft u aan dat het apparaat aankondigingen via Bluetooth kan ontvangen.
-   **NFC**: hiermee kan de gebruiker mogelijkheden voor Near Field Communications op het apparaat inschakelen en configureren.
-   **Wi-Fi**: hiermee kan de gebruiker Wi-Fi op het apparaat inschakelen en configureren (alleen voor Windows 10 Mobile).
-   **Automatisch verbinding maken met Wi-Fi-hotspots**: hiermee kunt u het apparaat automatisch verbinding laten maken met gratis Wi-Fi-hotspots en automatisch de voorwaarden voor de verbinding laten accepteren.
-   **Handmatige configuratie van Wi-Fi**: hiermee geeft u aan of de gebruiker zijn of haar eigen Wi-Fi-verbindingen kan instellen, of dat de gebruiker alleen verbindingen kan gebruiken die door een Wi-Fi-profiel zijn geconfigureerd (alleen voor Windows 10 Mobile).
## <a name="defender"></a>Defender

-   **Realtime-controle**: hiermee schakelt u het realtime scannen op malware, spyware en andere ongewenste software in.
-   **Gedragscontrole**: hiermee kunt u Defender laten controleren op de aanwezigheid van bepaalde bekende patronen van verdachte activiteiten op apparaten.
-   **Netwerkinspectiesysteem (NIS)**: Netwerkinspectiesysteem (NIS) kan u op basis van de handtekeningen van bekende beveiligingsproblemen van het Microsoft Endpoint Protection Center helpen met het detecteren en blokkeren van schadelijk verkeer, zodat de apparaten in het netwerk zijn beveiligd tegen exploits.
-   **Alle downloads scannen**: hiermee bepaalt u of Windows Defender alle bestanden moet scannen die van internet worden gedownload.
-   **Scripts scannen die in webbrowsers van Microsoft worden geladen**: hiermee geeft u aan dat Defender scripts moet scannen die worden gebruikt in Internet Explorer.
-   **Toegang van eindgebruikers tot Defender**: hiermee geeft u aan of de gebruikersinterface van Windows Defender voor eindgebruikers wordt verborgen.
Als deze instelling wordt gewijzigd, gaat de wijziging in wanneer de pc van de eindgebruiker de volgende keer opnieuw wordt opgestart.
-   **Interval voor handtekeningupdates (in uren)**: hiermee geeft u het interval op waarmee Defender op nieuwe handtekeningbestanden moet controleren.
-   **Activiteiten van bestanden en programma's bewaken**: hiermee staat u Defender toe activiteiten van bestanden en programma's op apparaten te bewaken.
-   **Het aantal dagen voordat in quarantaine geplaatste malware wordt verwijderd**: hiermee kunt u Defender gedurende het aantal dagen dat u opgeeft, opgeloste malware laten bijhouden, zodat u handmatig eerder aangevallen apparaten kunt controleren. Als u het aantal dagen instelt op **0**, blijft malware in de map Quarantaine staan en wordt malware niet automatisch verwijderd.
-   **Limiet voor het CPU-gebruik tijdens het scannen**: hiermee kunt u de hoeveelheid CPU beperken die scans mogen gebruiken (tussen **1** en **100**).
-   **Archiefbestanden scannen**: hiermee kunt u toestaan dat Defender gearchiveerde bestanden scant, zoals ZIP- of CAB-bestanden.
-   **Inkomende e-mailberichten scannen**: hiermee kunt u toestaan dat Defender e-mailberichten scant wanneer deze op het apparaat binnenkomen.
-   **Verwisselbare stations scannen tijdens een volledige scan**: hiermee kunt u toestaan dat Defender verwisselbare stations, zoals USB-sticks, scant.
-   **Toegewezen netwerkschijven scannen tijdens een volledige scan**: hiermee kunt u Defender op toegewezen netwerkstations laten scannen.<br>Als de bestanden op de schijf het kenmerk Alleen-lezen hebben, kan Defender eventueel gevonden malware niet verwijderen.
-   **Bestanden die zijn geopend vanuit mappen op het netwerk scannen**: hiermee kunt u Defender bestanden op gedeelde stations laten scannen (bijvoorbeeld gedeelde stations die via een UNC-pad toegankelijk zijn).
Als de bestanden op de schijf het kenmerk Alleen-lezen hebben, kan Defender eventueel gevonden malware niet verwijderen.
-   **Cloudbeveiliging**: hiermee kunt u toestaan of blokkeren dat de Microsoft Active Protection-service informatie ontvangt over malware-activiteit op apparaten die u beheert. Deze informatie wordt gebruikt om de service in de toekomst te verbeteren.
-   **Gebruikers vragen voordat een voorbeeld wordt verzonden**: hiermee bepaalt u of bestanden waarvoor verdere analyse door Microsoft nodig is om te bepalen of deze schadelijk zijn, automatisch naar Microsoft moeten worden verzonden.
-   **Tijd waarop een dagelijkse snelle scan moet worden uitgevoerd**: hiermee kunt u een snelle scan plannen die dagelijks wordt uitgevoerd op het moment dat u selecteert.
-   **Type systeemscan dat moet worden uitgevoerd**: hiermee kunt u het scanniveau opgeven wanneer u een systeemscan plant.
## <a name="defender-exclusions"></a>Defender-uitsluitingen

-   **Bestanden en mappen die moeten worden uitgesloten van scans en de realtime-beveiliging**: hiermee voegt u een of meer bestanden aan de uitsluitingslijst toe, zoals **C:\pad** of **%ProgramFiles%\pad\bestandsnaam.exe**. Deze bestanden en mappen worden niet opgenomen in real-timescans of geplande scans.
-   **Bestandsextensies die moeten worden uitgesloten van scans en de realtime-beveiliging**: hiermee voegt u een of meer bestandsextensies zoals **jpg** of **txt** aan de uitsluitingslijst toe. Bestanden met deze extensies worden niet opgenomen in realtime-scans of geplande scans.
-   **Processen die moeten worden uitgesloten van scans en de realtime-beveiliging**: hiermee voegt u een of meer processen van het type **.exe**, **.com** of **.scr** aan de uitsluitingslijst toe. Deze processen worden niet opgenomen in real-timescans of geplande scans.



<!--HONumber=Feb17_HO1-->


