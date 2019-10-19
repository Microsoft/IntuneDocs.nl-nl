---
title: Problemen met app-installatie oplossen
titleSuffix: Microsoft Intune
description: Gebruik het Microsoft Intune-deelvenster voor probleemoplossing om u te helpen bij het oplossen van installatieproblemen.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/04/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: b613f364-0150-401f-b9b8-2b09470b34f4
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e1067c8ef23add50c921217b9e4b115346be2951
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72497040"
---
# <a name="troubleshoot-app-installation-issues"></a>Problemen met app-installatie oplossen

Op apparaten die met Microsoft Intune MDM worden beheerd, mislukken app-installaties wel eens. Als deze apps niet kunnen worden geïnstalleerd, is het soms lastig om de reden van het probleem te achterhalen of om het probleem op te lossen. Microsoft Intune biedt details van app-installatiefouten. Zo kunnen helpdeskmedewerkers en Intune-beheerders app-informatie bekijken om de hulpverzoeken van gebruikers te beantwoorden. Het deelvenster voor probleemoplossing binnen Intune biedt foutdetails, waaronder details over beheerde apps op een apparaat van een gebruiker. Er worden details van de end-to-end-levenscyclus van een app van elk afzonderlijk apparaat getoond in het deelvenster **Beheerde apps**. U kunt installatieproblemen bekijken, zoals wanneer de app was gemaakt, bewerkt, ingericht op en geleverd aan een apparaat. 

## <a name="app-troubleshooting-details"></a>Details van de app-probleemoplossing

Intune biedt details van app-probleemoplossing op basis van de geïnstalleerde apps op een specifiek apparaat van een gebruiker.

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Kies in het deelvenster **Intune** de optie **Problemen oplossen**.
4. Klik op **Gebruiker selecteren** om een gebruiker te selecteren waarvoor er problemen opgelost moeten worden. Het deelvenster **Gebruikers selecteren** wordt weergegeven.
5. Selecteer de gebruiker door een naam of e-mailadres te typen. Klik onder aan het deelvenster op **Selecteren**. De informatie voor het oplossen van problemen voor de gebruiker wordt weergegeven in het deelvenster **Probleemoplossing**. 
6. Selecteer in de lijst **Apparaten** het apparaat waarbij u problemen wilt oplossen.
    ![Het deelvenster Intune-probleemoplossing.](./media/troubleshoot-app-install/troubleshoot-app-install-01.png)
7. Selecteer **Beheerde apps** in het deelvenster van het geselecteerde apparaat. Er wordt een lijst met beheerde apps weergegeven.
    ![Details van een specifiek apparaat dat door Intune wordt beheerd.](./media/troubleshoot-app-install/troubleshoot-app-install-02.png)
8. Selecteer een app in de lijst waarbij de **Installatiestatus** een fout aangeeft.
    ![Een geselecteerde app waarbij een installatiefout wordt aangegeven.](./media/troubleshoot-app-install/troubleshoot-app-install-03.png)

    > [!Note]  
    > Dezelfde app kan worden toegewezen aan meerdere groepen, maar met verschillende beoogde acties (intenties) voor de app. Een opgeloste intentie voor een app wordt bijvoorbeeld weergegeven als **uitgesloten** als de app voor een gebruiker is uitgesloten tijdens de app-toewijzing. Raadpleeg [Hoe conflicten tussen app-intenties worden opgelost](apps-deploy.md#how-conflicts-between-app-intents-are-resolved) voor meer informatie.<br><br>
    > Als er een installatiefout bij een vereiste app optreedt, kunt u noch uw helpdesk het apparaat synchroniseren en opnieuw proberen de app te installeren.

De details van de app-installatieproblemen geven het probleem aan. U kunt deze details gebruiken om de beste actie vast te stellen waarmee het probleem wordt opgelost. Zie [App-installatiefouten](troubleshoot-app-install.md#app-installation-errors) voor meer informatie over het oplossen van problemen met appinstallatie.

> [!Note]  
> U kunt het deelvenster **Probleemoplossing** ook openen door in uw browser naar het volgende adres te gaan: [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting).

## <a name="user-group-targeted-app-installation-does-not-reach-device"></a>Het apparaat is niet bereikbaar voor de doel-app-installatie van de gebruikers groep
U moet rekening houden met de volgende acties als u problemen hebt met het installeren van apps:
- Als de app niet wordt weer gegeven in de Bedrijfsportal, moet u ervoor zorgen dat de app is geïmplementeerd met **beschik bare** intentie en dat de gebruiker toegang heeft tot de bedrijfsportal met het apparaattype dat wordt ondersteund door de app.
- Voor Windows BYOD-apparaten moet de gebruiker een werk account toevoegen aan het apparaat.
- Controleren of de gebruiker de limiet voor AAD-apparaten overschrijdt:
  1. Navigeer naar [Azure Active Directory Apparaatinstellingen](https://portal.azure.com/#blade/Microsoft_AAD_IAM/DevicesMenuBlade/DeviceSettings/menuId).
  2. Noteer de waarde die is ingesteld voor **maximum aantal apparaten per gebruiker**.
  3. Navigeer naar [Azure Active Directory gebruikers](https://portal.azure.com/#blade/Microsoft_AAD_IAM/UsersManagementMenuBlade/AllUsers).
  4. Selecteer de betrokken gebruiker en klik op **apparaten**.
  5. Als de gebruiker de ingestelde limiet overschrijdt, verwijdert u alle verouderde records die niet meer nodig zijn.
- Voor iOS DEP-apparaten zorgt u ervoor dat de gebruiker wordt vermeld als **geregistreerd door de gebruiker** in de Blade overzicht van intune-apparaten. Als er N.V.T. wordt weer gegeven, implementeert u een configuratie beleid voor de Intune-bedrijfsportal. Zie [Configure the bedrijfsportal app](app-configuration-policies-use-ios.md#configure-the-company-portal-app-to-support-ios-dep-devices)(Engelstalig) voor meer informatie.

## <a name="win32-app-installation-troubleshooting"></a>Problemen met de installatie van Win32-app oplossen

Selecteer de Win32-app die is geïmplementeerd met behulp van de Intune-beheerextensie. U kunt de optie **Logboeken verzamelen** selecteren wanneer de installatie van de Win32-app is mislukt. 

> [!IMPORTANT]
> De optie **Logboeken verzamelen** wordt niet ingeschakeld wanneer de Win32-app succesvol is geïnstalleerd op het apparaat.<p>Voordat u logboekgegevens over de Win32-app kunt verzamelen, moet de Intune-beheerextensie geïnstalleerd zijn op de Windows-client. De Intune-beheerextensie wordt geïnstalleerd wanneer een PowerShell-script of een Win32-app wordt geïmplementeerd in een gebruikers- of apparaatbeveiligingsgroep. Zie [Intune-beheerextensie - vereisten](intune-management-extension.md#prerequisites). voor meer informatie.

### <a name="collect-log-file"></a>Logboekbestand verzamelen

Volg eerst de stappen in de sectie [Details van de app-probleemoplossing](troubleshoot-app-install.md#app-troubleshooting-details) om de installatielogboeken van de Win32-app te verzamelen. Ga vervolgens verder met de volgende stappen:

1. Klik op de optie **Logboeken verzamelen** op de blade **Installatiegegevens**.

    <image alt="Win32 app installation details - Collect log option" src="./media/troubleshoot-app-install/troubleshoot-app-install-04.png" width="500" />

2. Geef bestandspaden met logboekbestandsnamen op om te beginnen met het verzamelen van logboekbestanden en klik op **OK**.

    > [!NOTE]
    > Het verzamelen van logboeken duur minder dan twee uur. Ondersteunde bestandstypen: *.log, .txt, .dmp, .cab, .zip, .xml, .evtx, en .evtl*. Er zijn maximaal 25 bestandspaden toegestaan.

3. Zodra de logboekbestanden zijn verzameld, kunt u de koppeling **Logboeken** selecteren om de logboekbestanden te downloaden.

    <image alt="Win32 app log details - Download logs" src="./media/troubleshoot-app-install/troubleshoot-app-install-05.png" width="500" />

    > [!NOTE]
    > Er wordt een melding weergegeven om aan te geven dat de app-logboeken zijn verzameld.

#### <a name="win32-log-collection-requirements"></a>Vereisten voor het verzamelen van Win32-logboeken

Er zijn specifieke vereisten voor het verzamelen van logboekbestanden:

- U moet het volledige pad naar het logboekbestand opgeven. 
- U kunt omgevingsvariabelen voor het verzamelen van logboeken opgeven, bijvoorbeeld:<br>
  *%PROGRAMFILES%, %PROGRAMDATA% %PUBLIC%, %WINDIR%, %TEMP%, %TMP%*
- Alleen precieze bestandsextensies zijn toegestaan, zoals:<br>
  *.log, .txt, .dmp, .cab, .zip, .xml*
- U kunt maximaal een logboekbestand van 60 MB of 25 bestanden uploaden, wat zich het eerst voordoet. 
- Het verzamelen van Win32-app-installatielogboeken is ingeschakeld voor apps die voldoen aan de vereiste, beschikbare en app-verwijdertoewijzingsintentie.
- Opgeslagen logboeken worden versleuteld om persoonlijke Identificeer bare gegevens in de logboeken te beveiligen.
- Voeg bij het openen van ondersteuningstickets voor Win32-app-fouten de gerelateerde foutenlogboeken bij met behulp van de bovenstaande stappen.

## <a name="app-installation-errors"></a>App-installatiefouten

De volgende foutberichten en beschrijvingen bieden informatie over Android- en iOS-installatiefouten. 

### <a name="android-errors"></a>Android-fouten

In deze sectie wordt zowel Device Administrator (DA) als Samsung Knox-inschrijving vermeld. Zie voor meer informatie Android [device Administrator registratie](../enrollment/android-enroll-device-administrator.md) en [Android-apparaten automatisch inschrijven met behulp van de mobiele inschrijving van Samsung](../enrollment/android-samsung-knox-mobile-enroll.md). 

| Foutbericht/-code | Beschrijving |
|---------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Kan de app niet installeren. (0xC7D14FB5) | Dit foutbericht wordt weergegeven als Intune de hoofdoorzaak van de fout tijdens de installatie van de Android-app niet kan bepalen. Er is geen informatie opgegeven door Android tijdens de mislukte bewerking. Deze fout wordt geretourneerd wanneer de APK is gedownload, maar de app-installatie is mislukt. Deze fout kan vaker optreden vanwege een ongeldig APK-bestand dat niet kan worden geïnstalleerd op het apparaat. Een mogelijke oorzaak kan zijn dat de installatie van de app wordt geblokkeerd door Google Play Protect vanwege beveiligingsproblemen. Een andere mogelijke oorzaak van deze fout is dat een apparaat geen ondersteuning biedt voor de app. Bijvoorbeeld als API-versie 21 of hoger wordt vereist voor de app en het apparaat op dit moment beschikt over API-versie 19. Intune retourneert deze fout voor DA- en KNOX-apparaten en hoewel er mogelijk een melding wordt gegeven dat gebruikers kunnen klikken om het opnieuw te proberen, blijft het probleem bestaan als er een probleem is met de APK. Als de app een beschikbare app is, kan de melding worden gesloten. Als de app vereist is, kan de melding niet worden gesloten. |
| De installatie van de app is geannuleerd omdat het installatiebestand (APK) is verwijderd na het downloaden, maar voordat de installatie was voltooid. (0xC7D14FBA) | De APK is gedownload, maar het bestand is verwijderd voordat de gebruiker de app had geïnstalleerd. Dit kan gebeuren als er veel tijd zit tussen het downloaden en installeren. De gebruiker heeft bijvoorbeeld de oorspronkelijke installatie geannuleerd, gewacht en vervolgens op de melding geklikt om het opnieuw te proberen. Dit foutbericht wordt alleen voor DA-scenario's geretourneerd. KNOX-scenario's kunnen op de achtergrond worden uitgevoerd. Er wordt een melding weergegeven om het opnieuw te proberen, zodat de gebruiker kan accepteren in plaats van annuleren. Als de app een beschikbare app is, kan de melding worden gesloten. Als de app vereist is, kan de melding niet worden gesloten. |
| Het installeren van de app is geannuleerd omdat het proces opnieuw is gestart tijdens de installatie. (0xC7D14FBB) | Het apparaat is opnieuw opgestart tijdens het installatieproces van de APK, waardoor de installatie is geannuleerd. Dit foutbericht wordt geretourneerd voor DA- en KNOX-apparaten. Intune geeft een melding weer waarop gebruikers kunnen klikken om het opnieuw te proberen. Als de app een beschikbare app is, kan de melding worden gesloten. Als de app vereist is, kan de melding niet worden gesloten. |
| De toepassing is niet gedetecteerd nadat de installatie was voltooid. (0x87D1041C) | De gebruiker heeft de app expliciet verwijderd. Deze fout wordt niet geretourneerd door de client. Het is een fout die wordt geactiveerd wanneer de app is geïnstalleerd, maar vervolgens door de gebruiker is verwijderd. Deze fout zou alleen moeten optreden voor vereiste toepassingen. Gebruikers kunnen niet-vereiste apps verwijderen. Deze fout kan alleen gebeuren in DA. Het verwijderen van beheerde apps wordt voor KNOX geblokkeerd. Tijdens de volgende synchronisatie wordt de melding opnieuw op het apparaat weergegeven zodat de gebruiker kan installeren. De melding kan worden genegeerd door de gebruiker. Deze fout blijft bestaan totdat de gebruiker de app verwijdert. |
| Kan niet downloaden vanwege een onbekende fout. (0xC7D14FB2) | Deze fout treedt op wanneer het downloaden is mislukt. Deze fout kan vaak optreden vanwege problemen met wifi of langzame verbindingen. Deze fout wordt alleen voor DA-scenario's geretourneerd. Voor KNOX-scenario's wordt de gebruiker niet gevraagd om te installeren; dit kan op de achtergrond worden gedaan. Intune geeft een melding weer waarop gebruikers kunnen klikken om het opnieuw te proberen. Als de app een beschikbare app is, kan de melding worden gesloten. Als de app vereist is, kan de melding niet worden gesloten. |
| Kan niet downloaden vanwege een onbekende fout. Het beleid wordt opnieuw uitgevoerd de volgende keer dat het apparaat wordt gesynchroniseerd. (0xC7D15078) | Deze fout treedt op wanneer het downloaden is mislukt. Deze fout kan vaak optreden vanwege problemen met wifi of langzame verbindingen. Deze fout wordt alleen voor DA-scenario's geretourneerd. Voor KNOX-scenario's wordt de gebruiker niet gevraagd om te installeren; dit kan op de achtergrond worden gedaan. |
| De eindgebruiker heeft de installatie van de app geannuleerd. (0xC7D14FB1) | De gebruiker heeft de app expliciet verwijderd. Deze fout wordt geretourneerd wanneer de installatie-activiteit van het Android-besturingssysteem wordt geannuleerd door de gebruiker. De gebruiker heeft op de knop Annuleren gedrukt toen de installatieprompt van het besturingssysteem werd weergegeven of heeft de opdrachtprompt weggeklikt. Deze fout wordt alleen voor DA-scenario's geretourneerd. Voor KNOX-scenario's wordt de gebruiker niet gevraagd om te installeren; dit kan op de achtergrond worden gedaan. Intune geeft een melding weer waarop gebruikers kunnen klikken om het opnieuw te proberen. Als de app een beschikbare app is, kan de melding worden gesloten. Als de app vereist is, kan de melding niet worden gesloten. Vraag de gebruiker de installatie niet te annuleren. |
| Het downloadproces voor het bestand is onverwacht gestopt. (0xC7D15015) | Het besturingssysteem heeft het downloadproces gestopt voordat dit was voltooid. Deze fout kan optreden als de batterij van het apparaat bijna leeg is of als het downloaden te lang duurt. Deze fout wordt alleen voor DA-scenario's geretourneerd. Voor KNOX-scenario's wordt de gebruiker niet gevraagd om te installeren; dit kan op de achtergrond worden gedaan. Intune geeft een melding weer waarop gebruikers kunnen klikken om het opnieuw te proberen. Als de app een beschikbare app is, kan de melding worden gesloten. Als de app vereist is, kan de melding niet worden gesloten. Zorg ervoor dat het apparaat een betrouw bare netwerk verbinding heeft.  |
| De downloadservice voor het bestand is onverwacht gestopt. Het beleid wordt opnieuw uitgevoerd de volgende keer dat het apparaat wordt gesynchroniseerd. (0xC7D1507C) | Het besturingssysteem heeft het downloadproces beëindigd voordat dit was voltooid. Deze fout kan optreden als de batterij van het apparaat bijna leeg is of als het downloaden te lang duurt. Deze fout wordt alleen voor DA-scenario's geretourneerd. Voor KNOX-scenario's wordt de gebruiker niet gevraagd om te installeren; dit kan op de achtergrond worden gedaan. Synchroniseer het apparaat hand matig of wacht 24 uur en controleer de status. |
| De app kan niet worden verwijderd. (0xc7d14fb8) | Deze fout is een algemene verwijderings fout. Het besturings systeem heeft niet opgegeven waarom de installatie van de app is mislukt. Sommige beheer-apps kunnen niet eenvoudigweg worden verwijderd. Controleer of de app hand matig kan worden verwijderd en verzamel de Bedrijfsportal-Logboeken als het verwijderen mislukt. |
| Het APK-bestand voor de installatie van de app dat wordt gebruikt voor de upgrade, komt niet overeen met de hand tekening voor de huidige app op het apparaat. (0xc7d14fb7) | Android-besturings systeem heeft de limiet voor het vereisen van het handtekening certificaat voor de upgrade versie precies hetzelfde als het certificaat dat wordt gebruikt voor het ondertekenen van de bestaande versie. Als de ontwikkelaar niet hetzelfde certificaat kan gebruiken voor het ondertekenen van de nieuwe versie, moet u de bestaande app verwijderen en de nieuwe app opnieuw implementeren, in plaats van de bestaande app bij te werken. |
| De eindgebruiker heeft de installatie van de app geannuleerd. (0xc7d14fb9) | Train de gebruiker om de door intune geïmplementeerde app te accepteren en de app te installeren wanneer daarom wordt gevraagd. |
| Het verwijderen van de app is geannuleerd omdat het proces opnieuw is gestart tijdens de installatie. (0xc7d14fbc) | Het installatie proces van de app is beëindigd door het besturings systeem of het apparaat is opnieuw gestart. Probeer de installatie opnieuw uit te voeren en Bedrijfsportal logboeken te verzamelen als deze fout zich opnieuw voordoet. |
| Het APK-bestand van de installatie van de app kan niet worden geïnstalleerd omdat het niet is ondertekend. (0xc7d14fb6) | Standaard vereist Android-besturings systeem dat apps zijn ondertekend. Zorg ervoor dat de app is ondertekend voordat u deze implementeert. |

### <a name="ios-errors"></a>iOS-fouten

| Foutbericht/-code | Beschrijving/probleemoplossingstips |
|------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| (0x87D12906) | Apple MDM-agent heeft geretourneerd dat de installatieopdracht is mislukt. |
| (0x87D1313C) | De netwerkverbinding is verbroken terwijl de bijgewerkte URL voor de downloadservice naar het apparaat werd verzonden. Een server met de opgegeven hostnaam kan niet worden gevonden. |
| Het iOS-apparaat is momenteel bezet. (0x87D11388) | Het iOS-apparaat is bezet, wat leidt tot een fout. Het apparaat is vergrendeld. De gebruiker moet het apparaat ontgrendelen om de app te installeren. |
| De installatie van de app is mislukt. (0x87D13B64) | Er is een fout opgetreden tijdens de installatie van de app. iOS Console-logboeken zijn nodig om deze fout te kunnen oplossen. |
| De app wordt beheerd, maar is verlopen of is verwijderd door de gebruiker. (0x87D13B66) | De gebruiker heeft de app expliciet verwijderd, of de app is verlopen, maar kan niet worden gedownload, of de detectie van de app komt niet overeen met de reactie van het apparaat. Deze fout kan ook optreden op basis van een iOS 9.2.2 iOS-platformfout. |
| Deze app staat ingepland om te worden geïnstalleerd, maar er is een inwisselcode vereist om de transactie te voltooien. (0x87D13B60) | Deze fout treedt meestal op bij iOS Store-apps, wat betaalde apps zijn. |
| De toepassing is niet gedetecteerd nadat de installatie was voltooid. (0x87D1041C) | Het app-detectieproces komt niet overeen met het antwoord van het apparaat. |
| De gebruiker heeft de aanbieding om de app te installeren afgewezen. (0x87D13B62) | Tijdens de eerste installatie van de app heeft de gebruiker op Annuleren geklikt. Vraag de gebruiker de installatie aanvraag de volgende keer te accepteren. |
| De gebruiker heeft de aanbieding voor een update van de app afgewezen. (0x87D13B63) | De eindgebruiker heeft tijdens het updateproces op Annuleren geklikt. Implementeer indien nodig of Train de gebruiker om de upgrade prompt te accepteren. |
| Onbekende fout (0x87D103E8) | Er is een onbekende app-installatiefout opgetreden. Dit is de resulterende fout als geen van de andere fouten is opgetreden. |
| Kan de VPP-apps alleen installeren op een gedeelde iPad (-2016330861). | De apps moeten worden verkregen met behulp van Apple Volume Purchase Program om deze te kunnen installeren op een gedeelde iPad. |
| Kan geen apps installeren als de App Store is uitgeschakeld (-2016330860). | De gebruiker kan de app alleen installeren als de App Store is ingeschakeld. |
| Kan geen VPP-licentie voor de app vinden (-2016330859). | Trek de app-licentie in en wijs deze opnieuw toe. |
| Kan geen systeem-apps installeren met uw MDM-provider (-2016330858). | Het installeren van apps die vooraf zijn geïnstalleerd in het iOS-besturingssysteem is een scenario dat niet wordt ondersteund. |
| Kan geen apps installeren op een apparaat dat zich in de modus Apparaat verloren bevindt (-2016330857). | Het gebruik van het apparaat is volledig geblokkeerd in de modus Apparaat verloren. Schakel de modus Apparaat verloren uit om apps te installeren. |
| Kan geen apps installeren op een apparaat dat zich in de kioskmodus bevindt (-2016330856). | Voeg dit apparaat toe aan een exclusieve groep voor configuratiebeleid voor de kioskmodus om apps te installeren. |
| Kan geen 32-bits apps op dit apparaat installeren (-2016330852). | Het apparaat biedt geen ondersteuning voor het installeren van 32-bits apps. Implementeer de 64-bits versie van de app. |
| De gebruiker moet zich aanmelden bij de App Store (-2016330855). | De gebruiker moet zich aanmelden bij de App Store voordat de app kan worden geïnstalleerd. |
| Onbekend probleem. Probeer het opnieuw (-2016330854). | De installatie van de app is mislukt om een onbekende reden. Probeer het later opnieuw. |
| De installatie van de app is mislukt. De volgende keer dat het apparaat wordt gesynchroniseerd, wordt er vanuit Intune een nieuwe poging ondernomen (-2016330853). | Er is een apparaatfout opgetreden bij het installeren van de app. Synchroniseer het apparaat en probeer de app opnieuw te installeren. |
| De licentie toewijzing is mislukt met Apple error ' er zijn geen VPP-licenties meer ' (0x87d13b7e) | Dit gedrag is inherent aan het ontwerp. U kunt dit oplossen door extra VPP-licenties aan te schaffen of licenties te claimen bij gebruikers die niet meer zijn gericht. |
| Installatie fout 12024 van de app: onbekende oorzaak. (0x87d13b6e) | Apple heeft niet voldoende informatie gegeven om te bepalen waarom de installatie is mislukt. Niets te rapporteren. |
| Het benodigde app-configuratie beleid is niet aanwezig. Zorg ervoor dat het beleid is gericht op dezelfde groepen. (0x87d13b7f) | Voor de app is app-configuratie vereist, maar er is geen app-configuratie bedoeld. De beheerder moet ervoor zorgen dat voor de groepen waarop de app is gericht, ook de vereiste app-configuratie is gericht op de groepen. |
| VPP-licentie verlening voor apparaten is alleen van toepassing op iOS 9.0 +-apparaten. (0x87d13b69) | Update betrokken iOS-apparaten in iOS 9.0 +. |
| De toepassing is geïnstalleerd op het apparaat, maar is niet-beheerd. (0x87d13b8f) | Deze fout treedt alleen op bij LOB-apps. De app is buiten intune geïnstalleerd. U kunt deze fout oplossen door de app van het apparaat te verwijderen. De volgende keer dat de synchronisatie van het apparaat plaatsvindt, wordt de app vanuit intune geïnstalleerd op het apparaat. |
| Gebruiker heeft app-beheer geweigerd (0x87d13b68) | Vraag de gebruiker om het beheer van apps te accepteren. |
| Onbekende fout. (0x87d1279d) | Deze fout treedt op bij iOS Store-apps, maar het fout scenario is onbekend. |
| De nieuwste versie van de app kan niet worden bijgewerkt vanuit een eerdere versie. (0x87D13B9D) | Dit fout bericht wordt weer gegeven als de app is geïnstalleerd en beheerd, maar met een onjuiste versie op het apparaat. Deze situatie kan zich voordoen wanneer een apparaat een opdracht heeft ontvangen om een app bij te werken, maar de nieuwe versie nog niet is geïnstalleerd en weer gemeld. Deze fout wordt gerapporteerd voor de eerste keer dat het apparaat wordt ingecheckt nadat de upgrade is geïmplementeerd. dit gebeurt totdat het apparaat rapporteert dat de nieuwe versie is geïnstalleerd of mislukt als gevolg van een andere fout.  |


### <a name="other-installation-errors"></a>Overige installatiefouten

|  Foutbericht/-code  |  Beschrijving  |
|-----------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  0x80073CFF, 0x80CF201C (clientfout)  |  Als u deze app wilt installeren, moet u beschikken over een systeem waarop sideloading is ingeschakeld. Controleer of het app-pakket is ondertekend met een vertrouwde handtekening en is geïnstalleerd op een apparaat dat lid is van een domein en waarop het **AllowAllTrustedApps**-beleid is ingeschakeld, of op een apparaat dat een Windows Sideloading-licentie bevat en waarop het **AllowAllTrustedApps**-beleid is ingeschakeld. Meer informatie vindt u in [Troubleshooting packaging, deployment, and query of Windows Runtime-based apps](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting) (Het oplossen van problemen bij het verpakken, implementeren en zoeken van Windows Store-apps).   |
|  0x80073CF0  |  Het pakket kan niet worden geopend. Mogelijke oorzaken:<ul><li> Het pakket is niet ondertekend.</li><li> De naam van de uitgever komt niet overeen met de ondertekenende certificaathouder.</li></ul> Controleer het gebeurtenislogboek **AppxPackagingOM** voor meer informatie. Meer informatie vindt u in [Troubleshooting packaging, deployment, and query of Windows Runtime-based apps](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting) (Het oplossen van problemen bij het verpakken, implementeren en zoeken van Windows Store-apps).  |
|  0x80073CF3  |  Validatie van updates, afhankelijkheid of conflict voor het pakket is mislukt. Mogelijke oorzaken:<ul><li> Het binnenkomende pakket conflicteert met een geïnstalleerd pakket.</li><li> Er is geen opgegeven pakketafhankelijkheid gevonden.</li><li> Het pakket biedt geen ondersteuning voor de juiste processorarchitectuur.</li></ul> Controleer het gebeurtenislogboek **AppXDeployment-Server** voor meer informatie. Meer informatie vindt u in [Troubleshooting packaging, deployment, and query of Windows Runtime-based apps](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting) (Het oplossen van problemen bij het verpakken, implementeren en zoeken van Windows Store-apps).  |
|  0x80073CFB  |  Het opgegeven pakket is al geïnstalleerd en opnieuw installeren van het pakket is geblokkeerd. Dit foutbericht kan worden weergegeven als u een pakket installeert dat niet gelijk is aan het pakket dat al is geïnstalleerd. Controleer of de digitale handtekening ook onderdeel is van het pakket. Wanneer een pakket opnieuw is samengesteld of opnieuw is ondertekend, is dat pakket niet meer bitsgewijs identiek aan het eerder geïnstalleerde pakket. Er zijn twee mogelijke opties om deze fout te herstellen:<ul><li> Verhoog het versienummer van de app, stel het pakket vervolgens opnieuw samen en onderteken het opnieuw.</li><li> Verwijder het oude pakket voor elke gebruiker op het systeem voordat u het nieuwe pakket installeert.</li></ul> Meer informatie vindt u in [Troubleshooting packaging, deployment, and query of Windows Runtime-based apps](https://docs.microsoft.com/windows/desktop/appxpkg/troubleshooting) (Het oplossen van problemen bij het verpakken, implementeren en zoeken van Windows Store-apps).  |
|  0x87D1041C  |  De toepassing is geïnstalleerd, maar de toepassing wordt niet gedetecteerd. De app is geïmplementeerd door Intune en daarna verwijderd. Redenen voor het verwijderen van de app zijn onder meer:<ul><li> De eindgebruiker heeft de app verwijderd.</li><li> De identiteitsgegevens in het pakket komen niet overeen met wat het apparaat aangeeft voor slechte apps.</li><li>Voor MSI's die automatisch worden bijgewerkt, komt de productversie niet overeen met de app-gegevens nadat deze buiten Intune zijn bijgewerkt.</li></ul> Geef de gebruiker de opdracht de app opnieuw te installeren via de bedrijfsportal. Houd er rekening mee dat vereiste apps automatisch opnieuw worden geïnstalleerd wanneer het apparaat opnieuw incheckt.  |
|  0x8000FFFF  |  Er is tijdens de installatie een onverwachte fout opgetreden. Raadpleeg de installatie logboeken voor meer informatie.  |

## <a name="troubleshooting-apps-from-the-microsoft-store"></a>Het oplossen van problemen met apps van Microsoft Store

De informatie in het Engelstalige onderwerp [Troubleshooting packaging, deployment, and query of Windows Store apps](https://msdn.microsoft.com/library/windows/desktop/hh973484.aspx) (Het oplossen van problemen bij het verpakken, implementeren en zoeken van Microsoft Store-apps) helpt u om algemene problemen op te lossen die optreden tijdens het installeren van apps in Microsoft Store, hetzij met behulp van Intune of op een andere manier.

## <a name="app-troubleshooting-resources"></a>Resources voor het oplossen van problemen met apps
- [Visio en project implementeren als onderdeel van uw Office Pro Plus-implementatie](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Deploying-Visio-and-Project-as-part-of-your-Office/ba-p/701795)
- [Actie ondernemen om te zorgen voor MSfB-apps die zijn geïmplementeerd via intune-installatie op Windows 10 1903](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Take-Action-to-Ensure-MSfB-Apps-deployed-through/ba-p/658864)
- [Problemen met de implementatie van MSI-apps in Microsoft Intune oplossen](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Troubleshooting-MSI-App-deployments-in-Microsoft/ba-p/359125)
- [Aanbevolen procedures voor software distributie naar de klassieke Windows-PC-agent van intune](https://support.microsoft.com/en-us/help/2583929/best-practices-for-intune-software-distribution-to-windows-pc)

## <a name="next-steps"></a>Volgende stappen

- Raadpleeg [De portal voor probleemoplossing gebruiken om gebruikers in uw bedrijf te helpen](../fundamentals/help-desk-operators.md) voor meer informatie over probleemoplossing met Intune. 
- Ontdek meer over bekende problemen in Microsoft Intune. Zie voor meer informatie [intune-klant succes](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess).
- Extra hulp nodig? Zie [Ondersteuning voor Microsoft Intune krijgen](../fundamentals/get-support.md).
