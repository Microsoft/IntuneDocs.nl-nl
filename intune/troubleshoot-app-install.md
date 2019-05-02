---
title: Problemen met app-installatie oplossen
titleSuffix: Microsoft Intune
description: Gebruik het Microsoft Intune-deelvenster voor probleemoplossing om u te helpen bij het oplossen van installatieproblemen.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/19/2019
ms.topic: troubleshooting
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: b613f364-0150-401f-b9b8-2b09470b34f4
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 574f509383891ff3e8e0f4c1b04a19832a378829
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2019
ms.locfileid: "58799498"
---
# <a name="troubleshoot-app-installation-issues"></a>Problemen met app-installatie oplossen

Op apparaten die met Microsoft Intune MDM worden beheerd, mislukken app-installaties wel eens. Als deze apps niet kunnen worden geïnstalleerd, is het soms lastig om de reden van het probleem te achterhalen of om het probleem op te lossen. Microsoft Intune biedt details van app-installatiefouten. Zo kunnen helpdeskmedewerkers en Intune-beheerders app-informatie bekijken om de hulpverzoeken van gebruikers te beantwoorden. Het deelvenster voor probleemoplossing binnen Intune biedt foutdetails, waaronder details over beheerde apps op een apparaat van een gebruiker. Er worden details van de end-to-end-levenscyclus van een app van elk afzonderlijk apparaat getoond in het deelvenster **Beheerde apps**. U kunt installatieproblemen bekijken, zoals wanneer de app was gemaakt, bewerkt, ingericht op en geleverd aan een apparaat. 

## <a name="app-troubleshooting-details"></a>Oplossen van problemen met App-details

Intune biedt details van app-probleemoplossing op basis van de geïnstalleerde apps op een specifiek apparaat van een gebruiker.

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies in het deelvenster **Intune** de optie **Problemen oplossen**.
4. Klik op **Gebruiker selecteren** om een gebruiker te selecteren waarvoor er problemen opgelost moeten worden. Het deelvenster **Gebruikers selecteren** wordt weergegeven.
5. Selecteer de gebruiker door een naam of e-mailadres te typen. Klik onder aan het deelvenster op **Selecteren**. De informatie voor het oplossen van problemen voor de gebruiker wordt weergegeven in het deelvenster **Probleemoplossing**. 
6. Selecteer in de lijst **Apparaten** het apparaat waarbij u problemen wilt oplossen.
    ![Het deelvenster Intune-probleemoplossing.](media/troubleshoot-app-install-01.png)
7. Selecteer **Beheerde apps** in het deelvenster van het geselecteerde apparaat. Er wordt een lijst met beheerde apps weergegeven.
    ![Details van een specifiek apparaat dat door Intune wordt beheerd.](media/troubleshoot-app-install-02.png)
8. Selecteer een app in de lijst waarbij de **Installatiestatus** een fout aangeeft.
    ![Een geselecteerde app waarbij een installatiefout wordt aangegeven.](media/troubleshoot-app-install-03.png)

    > [!Note]  
    > Dezelfde app kan worden toegewezen aan meerdere groepen, maar met verschillende beoogde acties (intenties) voor de app. Een opgeloste intentie voor een app wordt bijvoorbeeld weergegeven als **uitgesloten** als de app voor een gebruiker is uitgesloten tijdens de app-toewijzing. Raadpleeg [Hoe conflicten tussen app-intenties worden opgelost](apps-deploy.md#how-conflicts-between-app-intents-are-resolved) voor meer informatie.<br><br>
    > Als er een installatiefout bij een vereiste app optreedt, kunt u noch uw helpdesk het apparaat synchroniseren en opnieuw proberen de app te installeren.

De details van de app-installatieproblemen geven het probleem aan. U kunt deze details gebruiken om de beste actie vast te stellen waarmee het probleem wordt opgelost. Raadpleeg [Error Codes For Troubleshooting App Installation Issues](https://blogs.technet.microsoft.com/intunesupport/2018/05/15/error-codes-for-troubleshooting-app-installation-issues) (Foutcodes voor oplossing van app-installatieproblemen) voor meer informatie over het oplossen van app-installatieproblemen.

> [!Note]  
> U kunt het deelvenster **Probleemoplossing** ook openen door in uw browser naar het volgende adres te gaan: [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting).

## <a name="win32-app-installation-troubleshooting"></a>Win32-app installatieproblemen oplossen

Selecteer de Win32-app die is geïmplementeerd met behulp van de Intune-beheeruitbreiding. U kunt selecteren de **verzamelen van logboeken** wanneer de installatie van de Win32-app is mislukt. 

> [!IMPORTANT]
> De **verzamelen van logboeken** optie wordt niet ingeschakeld wanneer de Win32-app is geïnstalleerd op het apparaat.<p>Voordat u de Win32-app-logboekgegevens verzamelen kunt, moet u de Intune-beheeruitbreiding geïnstalleerd op de Windows-client. De Intune-beheerextensie wordt geïnstalleerd wanneer een PowerShell-script of een Win32-app wordt geïmplementeerd in een gebruikers- of apparaatbeveiligingsgroep. Zie voor meer informatie, [Intune-beheeruitbreiding - vereisten](intune-management-extension.md#prerequisites).

### <a name="collect-log-file"></a>Verzamelen van logboekbestand

Voor het verzamelen van de installatielogboeken van de Win32-app, volgt u eerst de stappen in de sectie [App probleemoplossingsdetails](troubleshoot-app-install.md#app-troubleshooting-details). Ga vervolgens verder met de volgende stappen uit:

1. Klik op de **verzamelen van logboeken** kiezen op de **installatiegegevens** blade.

    <image alt="Win32 app installation details - Collect log option" src="media/troubleshoot-app-install-04.png" width="500" />

2. Bestandspaden bieden met log namen om te beginnen met het logboekverzamelproces van het bestand en klik op **OK**.
    
    > [!NOTE]
    > Logboekverzameling duurt minder dan twee uur. Ondersteunde bestandstypen: *.log, txt, dmp, cab, ZIP-, .xml, .evtx en .evtl*. Een maximum van 25 paden zijn toegestaan.

3. Zodra de logboekbestanden zijn verzameld, kunt u de **logboeken** koppeling om te downloaden van de logboekbestanden.

    <image alt="Win32 app log details - Download logs" src="media/troubleshoot-app-install-05.png" width="500" />

    > [!NOTE]
    > Een melding weergegeven die wijzen op het succes van de logboekverzamelaar app.

#### <a name="win32-log-collection-requirements"></a>Win32-logboekvereisten verzameling

Er zijn specifieke vereisten die moeten worden gevolgd voor het verzamelen van logboekbestanden:

- U moet het volledige logboek-bestandspad opgeven. 
- U kunt omgevingsvariabelen voor de logboekverzameling, zoals het volgende opgeven:<br>
  *% PROGRAMFILES %, % PROGRAMDATA % % OPENBARE %, % WINDIR %, % TEMP %, % TMP %*
- Alleen exacte bestandsextensies zijn toegestaan, zoals:<br>
  *.log, .txt, .dmp, .cab, .zip, .xml*
- De maximale logboekbestand voor het uploaden is 60 MB of 25-bestanden, indien dit eerder gebeurt. 
- Win32-app installeren-logboekverzameling is ingeschakeld voor apps die voldoen aan de vereiste beschikbaar is, en verwijder de toewijzingsopzet app.
- Opgeslagen logboeken worden ter bescherming van eventuele PII-gegevens die zijn opgenomen in de logboeken versleuteld.
- Tijdens het openen ondersteuning voor Win32-app fouten-tickets, koppelt u de gerelateerde fout-logboeken met behulp van de bovenstaande stappen.

## <a name="app-installation-errors"></a>App-installatiefouten

De volgende foutberichten en beschrijvingen bieden informatie over Android- en iOS-installatiefouten. 

### <a name="android-errors"></a>Android-fouten

|    Foutbericht/-code    |    Beschrijving    |
|----------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Kan de app niet installeren. (0xC7D14FB5)    |    Dit foutbericht wordt weergegeven als Intune de hoofdoorzaak van de fout tijdens de installatie van de Android-app niet kan bepalen. Er is geen informatie opgegeven door Android tijdens de mislukte bewerking.       Deze fout wordt geretourneerd wanneer de APK is gedownload, maar de app-installatie is mislukt. Deze fout kan vaker optreden vanwege een ongeldig APK-bestand dat niet kan worden geïnstalleerd op het apparaat. Een mogelijke oorzaak kan zijn dat de installatie van de app wordt geblokkeerd door Google Play Protect vanwege beveiligingsproblemen. Een andere mogelijke oorzaak van deze fout is dat een apparaat geen ondersteuning biedt voor de app. Bijvoorbeeld als API-versie 21 of hoger wordt vereist voor de app en het apparaat op dit moment beschikt over API-versie 19.         Intune retourneert deze fout voor DA- en KNOX-apparaten en hoewel er mogelijk een melding wordt gegeven dat gebruikers kunnen klikken om het opnieuw te proberen, blijft het probleem bestaan als er een probleem is met de APK. Als de app een beschikbare app is, kan de melding worden gesloten. Als de app vereist is, kan de melding niet worden gesloten.        |
|    De installatie van de app is geannuleerd omdat het installatiebestand (APK) is verwijderd na het downloaden, maar voordat de installatie was voltooid. (0xC7D14FBA)    |    De APK is gedownload, maar het bestand is verwijderd voordat de gebruiker de app had geïnstalleerd. Dit kan gebeuren als er veel tijd zit tussen het downloaden en installeren. De gebruiker heeft bijvoorbeeld de oorspronkelijke installatie geannuleerd, gewacht en vervolgens op de melding geklikt om het opnieuw te proberen.         Dit foutbericht wordt alleen voor DA-scenario's geretourneerd. KNOX-scenario's kunnen op de achtergrond worden uitgevoerd. Er wordt een melding weergegeven om opnieuw te proberen, zodat de gebruiker kan accepteren in plaats van annuleren. Als de app een beschikbare app is, kan de melding worden gesloten. Als de app vereist is, kan de melding niet worden gesloten.    |
|    Het installeren van de app is geannuleerd omdat het proces opnieuw is gestart tijdens de installatie. (0xC7D14FBB)    |    Het apparaat is opnieuw opgestart tijdens het installatieproces van de APK, waardoor de installatie is geannuleerd.        Dit foutbericht wordt geretourneerd voor DA- en KNOX-apparaten. Intune geeft een melding weer waarop gebruikers kunnen klikken om het opnieuw te proberen. Als de app een beschikbare app is, kan de melding worden gesloten. Als de app vereist is, kan de melding niet worden gesloten.    |
|    De toepassing is niet gedetecteerd nadat de installatie was voltooid. (0x87D1041C)    |    De gebruiker heeft de app expliciet verwijderd. Deze fout wordt niet geretourneerd door de client. Het is een fout die wordt geactiveerd wanneer de app is geïnstalleerd, maar vervolgens door de gebruiker is verwijderd. Deze fout zou alleen moeten optreden voor vereiste toepassingen. Gebruikers kunnen niet-vereiste apps verwijderen. Deze fout kan alleen gebeuren in DA. Het verwijderen van beheerde apps wordt voor KNOX geblokkeerd.       Tijdens de volgende synchronisatie wordt de melding opnieuw op het apparaat weergegeven zodat de gebruiker kan installeren.   De melding kan worden genegeerd door de gebruiker. Deze fout blijft bestaan totdat de gebruiker de app verwijdert.    |
|    Kan niet downloaden vanwege een onbekende fout. (0xC7D14FB2)    |    Deze fout treedt op wanneer het downloaden is mislukt. Deze fout kan vaak optreden vanwege problemen met Wi-Fi of langzame verbindingen.       Deze fout wordt alleen voor DA-scenario's geretourneerd. Voor KNOX-scenario's wordt de gebruiker niet gevraagd om te installeren, dit kan op de achtergrond worden gedaan. Intune geeft een melding weer waarop gebruikers kunnen klikken om het opnieuw te proberen. Als de app een beschikbare app is, kan de melding worden gesloten. Als de app vereist is, kan de melding niet worden gesloten.    |
|    Kan niet downloaden vanwege een onbekende fout. Het beleid wordt opnieuw uitgevoerd de volgende keer dat het apparaat wordt gesynchroniseerd. (0xC7D15078)    |    Deze fout treedt op wanneer het downloaden is mislukt. Deze fout kan vaak optreden vanwege problemen met Wi-Fi of langzame verbindingen.       Deze fout wordt alleen voor DA-scenario's geretourneerd. Voor KNOX-scenario's wordt de gebruiker niet gevraagd om te installeren, dit kan op de achtergrond worden gedaan.    |
|    De eindgebruiker heeft de installatie van de app geannuleerd. (0xC7D14FB1)    |    De gebruiker heeft de app expliciet verwijderd. Deze fout wordt geretourneerd wanneer de installatie-activiteit van het Android-besturingssysteem wordt geannuleerd door de gebruiker. De gebruiker heeft op de knop Annuleren gedrukt toen de installatieprompt van het besturingssysteem werd weergegeven of heeft de opdrachtprompt weggeklikt.        Deze fout wordt alleen voor DA-scenario's geretourneerd. Voor KNOX-scenario's wordt de gebruiker niet gevraagd om te installeren, dit kan op de achtergrond worden gedaan. Intune geeft een melding weer waarop gebruikers kunnen klikken om het opnieuw te proberen. Als de app een beschikbare app is, kan de melding worden gesloten. Als de app vereist is, kan de melding niet worden gesloten.    |
|    Het downloadproces voor het bestand is onverwacht gestopt. (0xC7D15015)    |    Het besturingssysteem heeft het downloadproces gestopt voordat dit was voltooid. Deze fout kan optreden als de batterij van het apparaat bijna leeg is of als het downloaden te lang duurt.       Deze fout wordt alleen voor DA-scenario's geretourneerd. Voor KNOX-scenario's wordt de gebruiker niet gevraagd om te installeren, dit kan op de achtergrond worden gedaan. Intune geeft een melding weer waarop gebruikers kunnen klikken om het opnieuw te proberen. Als de app een beschikbare app is, kan de melding worden gesloten. Als de app vereist is, kan de melding niet worden gesloten.    |
|    De downloadservice voor het bestand is onverwacht gestopt. Het beleid wordt opnieuw uitgevoerd de volgende keer dat het apparaat wordt gesynchroniseerd. (0xC7D1507C)    |    Het besturingssysteem heeft het downloadproces gestopt voordat dit was voltooid. Deze fout kan optreden als de batterij van het apparaat bijna leeg is of als het downloaden te lang duurt.       Deze fout wordt alleen voor DA-scenario's geretourneerd. Voor KNOX-scenario's wordt de gebruiker niet gevraagd om te installeren, dit kan op de achtergrond worden gedaan.    |

### <a name="ios-errors"></a>iOS-fouten

| Foutbericht/-code | Beschrijving/probleemoplossing tips |
|------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| (0x87D12906) | Apple MDM-Agent heeft geretourneerd dat de installatieopdracht is mislukt. |
| (0x87D1313C) | De netwerkverbinding is verbroken terwijl de bijgewerkte URL voor de downloadservice naar het apparaat werd verzonden. Een server met de opgegeven hostnaam kan niet worden gevonden. |
| Het iOS-apparaat is momenteel bezet. (0x87D11388) | Het iOS-apparaat is bezet, wat leidt tot een fout. |
| De installatie van de app is mislukt. (0x87D13B64) | Er is een fout opgetreden tijdens de installatie van de app. XCODE-logboeken zijn nodig om deze fout te kunnen oplossen. |
| De app wordt beheerd, maar is verlopen of is verwijderd door de gebruiker. (0x87D13B66) | De gebruiker heeft de app expliciet verwijderd. Of de app is verlopen, maar kan niet worden gedownload. Of de app-detectie komt niet overeen met het antwoord van het apparaat.   Deze fout kan ook optreden op basis van een iOS 9.2.2 iOS-platformfout. |
| Deze app staat ingepland om te worden geïnstalleerd, maar er is een inwisselcode vereist om de transactie te voltooien. (0x87D13B60) | Deze fout treedt meestal op bij iOS Store-apps, die betaalde apps zijn. |
| De toepassing is niet gedetecteerd nadat de installatie was voltooid.   (0x87D1041C) | Het app-detectieproces komt niet overeen met het antwoord van het apparaat. |
| De gebruiker heeft de aanbieding om de app te installeren afgewezen. (0x87D13B62) | Tijdens de eerste installatie van de app heeft de gebruiker op Annuleren geklikt. |
| De gebruiker heeft de aanbieding voor een update van de app afgewezen. (0x87D13B63) | De eindgebruiker heeft tijdens het updateproces op Annuleren geklikt. |
| Onbekende fout (0x87D103E8) | Er is een onbekende app-installatiefout opgetreden. Dit is de resulterende fout als geen van de andere fouten is opgetreden. |
| Kan de VPP-apps alleen installeren op gedeelde iPad (-2016330861). | De apps moeten worden verkregen met behulp van Apple Volume Purchase Program te installeren op een gedeelde iPad. |
| Geen apps installeren als de App Store is uitgeschakeld (-2016330860).  | De Store-App moet zijn ingeschakeld voor de gebruiker de app te installeren. |
| VPP-licentie voor app (-2016330859) is niet gevonden.  | Probeer intrekken en opnieuw toewijzen van de app-licentie. |
| Geen system-apps niet installeren met de MDM-provider (-2016330858). | Installeren van apps die vooraf zijn geïnstalleerd door de iOS-besturingssysteem is niet een ondersteund scenario. |
| Geen installeren apps, wanneer het apparaat zich in de modus apparaat verloren (-2016330857). | Alle gebruik van het apparaat wordt geblokkeerd in de modus apparaat verloren.   Modus apparaat verloren om apps te installeren uitschakelen. |
| Geen installeren apps, wanneer het apparaat zich in de kioskmodus bevindt (-2016330856). | Probeer dit apparaat toevoegen aan een groep uitsluiten voor kioskmodus modus configuratiebeleid voor apps te installeren. |
| Kan de 32-bits apps op dit apparaat (-2016330852) niet installeren. | Het apparaat biedt geen ondersteuning voor 32-bits apps installeren. Probeer de 64-bits versie van de app te implementeren. |
| Gebruiker moet aanmelden bij de App Store (-2016330855). | De gebruiker moet zich aanmelden bij de App Store voordat de app kan worden geïnstalleerd. |
| Onbekend probleem. Probeer het opnieuw (-2016330854). | Installatie van de app is mislukt vanwege een onbekende reden.   Probeer het later opnieuw. |
| Installatie van de app is mislukt. Intune zal proberen opnieuw zodra het apparaat wordt gesynchroniseerd (-2016330853). | Installatie van de app is een fout opgetreden. Het apparaat probeert te installeren de app opnieuw synchroniseren. |

### <a name="other-installation-errors"></a>Overige installatiefouten

|    Foutbericht/-code    |    Beschrijving    |
|-----------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    0x80073CFF,   0x80CF201C (clientfout)    |    Als u deze app wilt installeren, moet u beschikken over een systeem waarop sideloading is ingeschakeld. Controleer of het app-pakket is ondertekend met een vertrouwde handtekening en is geïnstalleerd op een apparaat dat lid is van een domein en waarop het **AllowAllTrustedApps**-beleid is ingeschakeld, of op een apparaat dat een Windows Sideloading-licentie bevat en waarop het **AllowAllTrustedApps**-beleid is ingeschakeld. Meer informatie vindt u in [Troubleshooting packaging, deployment, and query of Windows Runtime-based apps](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting) (Het oplossen van problemen bij het verpakken, implementeren en zoeken van Windows Store-apps).     |
|    0x80073CF0    |    Het pakket kan niet worden geopend. Mogelijke oorzaken:<ul><li> Het pakket is niet ondertekend.</li><li> De naam van de uitgever komt niet overeen met de ondertekenende certificaathouder.</li></ul> Controleer het gebeurtenislogboek **AppxPackagingOM** voor meer informatie. Meer informatie vindt u in [Troubleshooting packaging, deployment, and query of Windows Runtime-based apps](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting) (Het oplossen van problemen bij het verpakken, implementeren en zoeken van Windows Store-apps).    |
|    0x80073CF3    |    Validatie van updates, afhankelijkheid of conflict voor het pakket is mislukt. Mogelijke oorzaken:<ul><li> Het binnenkomende pakket conflicteert met een geïnstalleerd pakket.</li><li> Er is geen opgegeven pakketafhankelijkheid gevonden.</li><li> Het pakket biedt geen ondersteuning voor de juiste processorarchitectuur.</li></ul> Controleer het gebeurtenislogboek **AppXDeployment-Server** voor meer informatie. Meer informatie vindt u in [Troubleshooting packaging, deployment, and query of Windows Runtime-based apps](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting) (Het oplossen van problemen bij het verpakken, implementeren en zoeken van Windows Store-apps).    |
|    0x80073CFB    |    Het opgegeven pakket is al geïnstalleerd en opnieuw installeren van het pakket is geblokkeerd. Dit foutbericht kan worden weergegeven als u een pakket installeert dat niet gelijk is aan het pakket dat al is geïnstalleerd. Controleer of de digitale handtekening ook onderdeel is van het pakket. Wanneer een pakket opnieuw is samengesteld of opnieuw is ondertekend, is dat pakket niet meer bitsgewijs identiek aan het eerder geïnstalleerde pakket. Er zijn twee mogelijke opties om deze fout te herstellen:<ul><li> Verhoog het versienummer van de app en stel het pakket opnieuw samen en onderteken het opnieuw.</li><li> Verwijder het oude pakket voor elke gebruiker op het systeem voordat u het nieuwe pakket installeert.</li></ul> Meer informatie vindt u in [Troubleshooting packaging, deployment, and query of Windows Runtime-based apps](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting) (Het oplossen van problemen bij het verpakken, implementeren en zoeken van Windows Store-apps).    |
|    0x87D1041C    |    De toepassing is geïnstalleerd, maar de toepassing wordt niet gedetecteerd. De app is geïmplementeerd door Intune en daarna verwijderd. Redenen voor het verwijderen van de app zijn onder meer:<ul><li> De eindgebruiker heeft de app verwijderd.</li><li> De identiteitsgegevens in het pakket komen niet overeen met wat het apparaat aangeeft voor slechte apps.</li><li>Voor MSI's die automatisch worden bijgewerkt, komt de productversie niet overeen met de app-gegevens nadat deze buiten Intune zijn bijgewerkt.</li></ul> Geef de gebruiker de opdracht de app opnieuw te installeren via de bedrijfsportal. Houd er rekening mee dat vereiste apps automatisch opnieuw worden geïnstalleerd wanneer het apparaat opnieuw incheckt.    |

## <a name="troubleshooting-apps-from-the-microsoft-store"></a>Het oplossen van problemen met apps van Microsoft Store

De informatie in het Engelstalige onderwerp [Troubleshooting packaging, deployment, and query of Windows Store apps](https://msdn.microsoft.com/library/windows/desktop/hh973484.aspx) (Het oplossen van problemen bij het verpakken, implementeren en zoeken van Microsoft Store-apps) helpt u om algemene problemen op te lossen die optreden tijdens het installeren van apps in Microsoft Store, hetzij met behulp van Intune of op een andere manier.

## <a name="next-steps"></a>Volgende stappen

- Raadpleeg [De portal voor probleemoplossing gebruiken om gebruikers in uw bedrijf te helpen](help-desk-operators.md) voor meer informatie over probleemoplossing met Intune. 
- Ontdek meer over bekende problemen in Microsoft Intune. Zie [Bekende problemen in Microsoft Intune](known-issues.md) voor meer informatie.
- Extra hulp nodig? Zie [Ondersteuning voor Microsoft Intune krijgen](get-support.md).
