---
title: Problemen met voorwaardelijke toegang oplossen
description: Dit kunt u doen wanneer uw gebruikers geen toegang krijgen tot bedrijfsbronnen via de voorwaardelijke toegang van Intune.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 10/24/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 433fc32c-ca9c-4bad-9616-852c72faf996
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 67a2891e4c7a6adcd7bd132c5663c9a78426ea07
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="troubleshoot-conditional-access"></a>Problemen met voorwaardelijke toegang oplossen

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Normaal gesproken ontvangt een gebruiker die e-mails probeert te openen of die SharePoint opent de vraag om zich in te schrijven. Als de gebruiker zich besluit in te schrijven, wordt deze naar de bedrijfsportal geleid.

In dit onderwerp wordt beschreven wat u moet doen wanneer uw gebruikers geen toegang krijgen tot resources met de voorwaardelijke toegang van Intune.


## <a name="the-basics-for-success-in-conditional-access"></a>De basis voor succesvol gebruik van voorwaardelijke toegang

Als u met voorwaardelijke toegang aan de slag wilt, moet aan de volgende voorwaarden worden voldaan:

-   Het apparaat moet worden beheerd door Intune
-   Het apparaat moet zijn geregistreerd bij Azure Active Directory (ADD). Onder normale omstandigheden vindt deze registratie automatisch plaats tijdens de inschrijving bij Intune
-   Het apparaat moet voldoen aan uw Intune-nalevingsbeleid, dit geldt voor het apparaat en de gebruiker van het apparaat.  Als er geen nalevingsbeleid is, is een inschrijving bij Intune voldoende.
-   EAS (Exchange ActiveSync) moet worden geactiveerd op het apparaat als de gebruiker e-mail ophaalt via de systeemeigen e-mailclient van het apparaat in plaats van met Outlook.     Dit gebeurt automatisch voor iOS-, Windows Phone- en Android/KNOX Standard-apparaten.
-   Uw Intune Exchange Connector moet juist worden geconfigureerd. Zie [Het oplossen van problemen met de Exchange Connector in Microsoft Intune](troubleshoot-exchange-connector.md) voor meer informatie.

De voorwaarden die voor elk apparaat gelden, zijn terug te vinden in Azure Management Portal en in het inventarisrapport van het apparaat.

## <a name="enrollment-issues"></a>Problemen bij het inschrijven

 -  Het apparaat is niet ingeschreven, dus het probleem kan worden opgelost door het apparaat in te schrijven.
 -  De gebruiker heeft het apparaat ingeschreven, maar het toevoegen aan de werkplek is mislukt. De gebruiker moet de inschrijving via de bedrijfsportal bijwerken.

## <a name="compliance-issues"></a>Problemen met naleving

 -  Het apparaat is niet compatibel met het Intune-beleid. Veelvoorkomende problemen zijn problemen met de versleutelings- en wachtwoordvereisten. De gebruiker wordt omgeleid naar de bedrijfsportal, waar deze het apparaat zodanig kan configureren dat er aan de voorwaarden wordt voldaan.
 -  Het kan even duren om de nalevingsinformatie te registreren voor een apparaat. Wacht een paar minuten en probeer het opnieuw.
 -  Voor iOS-apparaten:
     -   Een bestaand e-mailprofiel dat is gemaakt door de gebruiker, blokkeert de implementatie van een Intune-profiel dat door een beheerder is gemaakt. Dit is een veelvoorkomend probleem omdat iOS-gebruikers vaak zelf een e-mailprofiel maken en zich vervolgens inschrijven. In de bedrijfsportal ziet de gebruiker dat deze niet voldoet aan de voorwaarden wegens het handmatig geconfigureerde e-mailprofiel. De gebruiker wordt gevraagd dat profiel te verwijderen. Het e-mailprofiel moet worden verwijderd zodat het Intune-profiel kan worden geïmplementeerd. Als u het probleem wilt voorkomen, vertelt u gebruikers om zich in te schrijven zonder een e-mailprofiel te installeren zodat Intune het profiel kan implementeren.
     -   Een iOS-apparaat kan komen vast te hangen in een status voor het controleren van nalevingsvereisten, waardoor de gebruiker wordt verhinderd om een andere incheckprocedure te initiëren. Het opnieuw opstarten van de bedrijfsportal kan dit probleem oplossen en de nalevingsstatus geeft de status van het apparaat in Intune aan. Nadat alle gegevens van een apparaatsynchronisatie zijn verzameld, gaat de nalevingscontrole snel, gemiddeld niet meer dan een halve seconde.

        De reden waarom apparaten in deze status blijven hangen, is doorgaans omdat ze problemen ondervinden bij het maken van verbinding met de service of omdat de synchronisatie lang duurt.  Als het probleem zich blijft voordoen in andere netwerkconfiguraties (mobiel, Wi-Fi-, VPN), zelfs nadat het apparaat opnieuw is opgestart, en nadat u hebt gecontroleerd of de SSP op het apparaat is bijgewerkt, neemt u contact op Microsoft Ondersteuning zoals beschreven in [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md).

 - Voor Android-apparaten:
    - Bepaalde Android-apparaten lijken misschien te zijn versleuteld, maar de bedrijfsportal-app herkent deze apparaten als niet-versleuteld. 
    
        -   Voor apparaten met deze status moet de gebruiker de wachtwoordcode voor beveiligd opstarten instellen. De gebruiker krijgt op het apparaat een bericht van de bedrijfsportal-app waarin wordt gevraagd om een wachtwoordcode voor het opstarten van het apparaat in te stellen. Wanneer u op het apparaatbericht hebt getikt en de bestaande pincode of het wachtwoord hebt bevestigd, kiest u de optie **Pincode vereisen voor het starten van apparaat** op het scherm **Beveiligd opstarten**. Tik vervolgens in de bedrijfsportal-app op de knop **Naleving controleren** voor het apparaat. Het apparaat moet nu worden gedetecteerd als versleuteld.
    
        -   Sommige apparaatfabrikanten versleutelen hun apparaten met behulp van een standaardpincode in plaats van een geheime pincode die door de gebruiker wordt ingesteld. Intune beschouwt versleuteling met een standaardpincode als onveilig omdat de gegevens op het apparaat bij deze methode van versleuteling niet afdoende zijn beschermd tegen kwaadwillende gebruikers met fysieke toegang tot het apparaat. Als dit het probleem is, zou u [app-beveiligingsbeleidsregels](/intune-classic/deploy-use/azure-portal-for-microsoft-intune-mam-policies) kunnen gebruiken.

## <a name="policy-issues"></a>Beleidsproblemen

Wanneer u een nalevingsbeleid maakt en dit koppelt aan een e-mailbeleid, moeten beide soorten beleid voor dezelfde gebruiker worden geïmplementeerd. Ga dus zorgvuldig te werk tijdens het plannen van welk beleid voor welke groepen moet worden geïmplementeerd. Gebruikers waarvoor slechts één beleid is toegepast, zullen merken dat hun apparaat niet compatibel is.


## <a name="exchange-activesync-issues"></a>Problemen met Exchange ActiveSync

### <a name="compliant-android-device-gets-quarantine-notice"></a>Op een compatibel Android-apparaat wordt een quarantainemelding weergegeven
- Op een Android-apparaat dat is ingeschreven en voldoet, kan alsnog een quarantainemelding worden weergegeven wanneer een gebruiker probeert bedrijfsresources te openen. Voordat de gebruiker de koppeling **Begin** selecteert, moet deze controleren of de bedrijfsportal gesloten was tijdens het openen van de resources. De gebruikers moeten de bedrijfsportal sluiten, opnieuw proberen de resources te openen en vervolgens de koppeling **Begin** selecteren.

### <a name="retired-device-continues-to-have-access"></a>Buiten gebruik gesteld apparaat heeft nog steeds toegang.
- Wanneer Exchange Online wordt gebruikt, kan op een apparaat dat buiten gebruik is gesteld mogelijk nog enkele uren toegang worden verkregen. Dit komt doordat Exchange de toegangsrechten gedurende zes uur in het cachegeheugen opslaat. Overweeg andere manieren om gegevens op buiten gebruik gestelde apparaten te beveiligen in dit scenario.

### <a name="device-is-compliant-and-registered-with-aad-but-still-blocked"></a>Apparaat is compatibel en geregistreerd bij AAD maar nog steeds geblokkeerd
- Soms is het inrichten van de Exchange ActiveSync ID (EASID) naar AAD vertraagd. Een veelvoorkomende oorzaak van dit probleem is beperking, dus wacht een paar minuten en probeer het opnieuw.

### <a name="device-blocked"></a>Apparaat is geblokkeerd

Op een apparaat kan voorwaardelijke toegang zijn geblokkeerd zonder dat er een activerings-e-mail is ontvangen.

- Is er een standaardregel in Exchange waardoor apparaten in quarantaine worden geplaatst of geblokkeerd? Als door een standaardregel apparaten worden geblokkeerd of in quarantaine worden geplaatst, kunnen apparaten de activerings-e-mail van de Exchange-Connector niet ontvangen. Dit is standaard.
- Is het account voor meldingen correct geconfigureerd zoals wordt beschreven in de basisconfiguratie?
- Is het apparaat in de Intune-beheerconsole te zien als een Exchange ActiveSync-apparaat? Als dat niet zo is, werkt waarschijnlijk de apparaatdetectie niet, mogelijk vanwege een synchronisatieprobleem in de Exchange Connector. Zie Een Exchange ActiveSync-apparaat wordt niet gedetecteerd door Exchange.
- Zoek in de logboeken van de Exchange Connector naar EmailVerzenden-activiteiten en controleer of u fouten ziet. Een voorbeeld van de opdracht waar u naar moet zoeken is EmailVerzenden van meldingsaccount naar E-mailGebruiker.
- Voordat het apparaat wordt geblokkeerd door de Exchange-Connector wordt de activerings-e-mail verzonden. Als het apparaat offline is, wordt de activerings-e-mail mogelijk niet ontvangen. Controleer of de e-mailclient op het apparaat e-mail ophaalt via Push in plaats van Poll, omdat dit er ook toe kan leiden dat de gebruiker de e-mail niet heeft ontvangen. Schakel over naar Poll en kijk of de e-mail op het apparaat wordt ontvangen.

## <a name="noncompliant-device-not-blocked"></a>Niet-compatibel apparaat niet geblokkeerd

Als u een apparaat hebt dat niet compatibel is en er nog steeds toegang mee hebt, moet u de volgende stappen uitvoeren.

- Controleer de doelgroepen en de groepen die zijn uitgesloten. Als een gebruiker zich niet in de juiste doelgroep of in de groep die is uitgesloten bevindt, wordt deze niet geblokkeerd. Alleen apparaten van gebruikers in een doelgroep worden gecontroleerd op naleving.
- Zorg ervoor dat het apparaat wordt gedetecteerd. Verwijst de Exchange-Connector naar een Exchange 2010 CAS terwijl de gebruiker zich op een Exchange 2013-server bevindt? In dit geval, mits de standaardregel voor Exchange Toestaan is, kan Intune de verbinding van het apparaat met Exchange niet detecteren, zelfs als de gebruiker zich in de doelgroep bevindt.
- Bestaan apparaat/toegangsstatus in Exchange controleren:
    - Gebruik deze PowerShell-cmdlet om een lijst van alle mobiele apparaten voor een postvak op te halen: 'Get-ActiveSyncDeviceStatistics-Postvak mbx'. Als het apparaat niet wordt weergegeven, heeft het geen toegang tot Exchange.
    - Als het apparaat wordt weergegeven, gebruikt u de cmdlet Get-CASmailbox-identity:'upn' | fl voor gedetailleerde informatie over de toegangsstatus en om die informatie aan Microsoft Ondersteuning te verstrekken.

## <a name="before-you-open-a-support-ticket"></a>Voordat u een ondersteuningsticket opent
Als deze procedures voor probleemoplossing uw probleem niet verhelpen, wordt u mogelijk gevraagd om bepaalde informatie aan Microsoft Ondersteuning te verstrekken, zoals OWA-postvaklogboeken of de logboeken van de Exchange Connector.

### <a name="collecting-owa-mailbox-logs"></a>OWA-postvaklogboeken verzamelen

1. Meld u aan via OWA en kies het instellingensymbool (tandwielpictogram) naast uw naam in de rechterbovenhoek.
2. Kies **Opties**
3. Kies **Telefoon** (er staat mogelijk **Mobiele apparaten**) in de kolom aan de linkerkant.
4. Kies in het menu bovenaan de optie **Mobiele apparaten**.
5. Kies uw apparaat in de lijst en kies vervolgens **Vastleggen starten**.
6. Wanneer u een vraag wordt gesteld, kiest u **Ja** in het pop-updialoogvenster.
7. Voer de actie uit waardoor het probleem is veroorzaakt, zodat u het probleem opnieuw produceert.
8. Wacht 1 - 2 minuten en ga dan terug naar de telefoonlijst in OWA. Zorg ervoor dat uw telefoon is geselecteerd in de lijst en kies vervolgens **Logboek ophalen** in het menu bovenaan.
9. U zou nu van uzelf een e-mailbericht met een bijlage moeten ontvangen. Wanneer u een ondersteuningsticket opent, kopieert u de inhoud van de e-mail en stuurt u deze naar Microsoft Ondersteuning.

### <a name="exchange-connector-logs"></a>Logboeken van de Exchange Connector

#### <a name="general-log-information"></a>Algemene logboekgegevens
Als u logboeken van de Exchange Connector wilt bekijken, moet u [Server Trace Viewer Tool](server trace viewer tool (https://msdn.microsoft.com/library/ms732023(v=vs.110).aspx) gebruiken. Dit hulpprogramma vereist dat u de Windows Server SDK downloadt.

>[!NOTE]
>De logboeken bevinden zich in C:\ProgramData\Microsoft\Windows Intune Exchange Connector\Logs. De logboeken zijn opgenomen in een reeks van 30 logboekbestanden. De reeks begint bij *Connector0.log* en eindigt bij *Connector29.log*. Logboeken lopen van het ene logboek over in het andere nadat 10 MB aan gegevens in een logboek zijn verzameld. Zodra de logboeken bij Connector29 aanbelanden, wordt alles opnieuw gestart bij Connector0, waarbij eerdere logboeken worden overschreven.

#### <a name="locating-sync-logs"></a>Zoeken naar synchronisatielogboeken

-    Vind een volledige synchronisatie in de logboeken door te zoeken naar **full sync**. Het begin van een volledige synchronisatie wordt aangegeven door deze tekst:

    Handling command: Getting the mobile device list without a time filter (full sync) for <number> users (Opdracht wordt verwerkt: de lijst met mobiele apparaten zonder een tijdfilter (volledige synchronisatie) voor (aantal) gebruikers wordt opgehaald)

    Het einde van het logboek voor een volledige synchronisatie ziet er als volgt uit:

    Getting the mobile device list without a time filter (full sync) for 4 users completed successfully. (De lijst met mobiele apparaten zonder een tijdfilter (volledige synchronisatie) voor 4 gebruikers kon worden opgehaald. Details: Inventory command result - Devices synced: 0 Commmand ID: commandIDGUID' Exchange health: 'Server health 'Name: 'PowerShellExchangeServer: <Name=mymailservername>' Status: Connected','

-   Vind een snelle (delta-)synchronisatie in de logboeken door te zoeken naar **quick sync**.

##### <a name="exceptions-in-get-next-command"></a>Uitzonderingen in de opdracht Get next
Controleer de logboeken van de Exchange Connector op uitzonderingen in de **opdracht Get next** en verstrek deze aan Microsoft Ondersteuning.

#### <a name="verbose-logging"></a>Uitgebreide logboekregistratie

Uitgebreide logboekregistratie inschakelen:

1.  Open het configuratiebestand voor tracering van de Exchange Connector. Het bestand bevindt zich hier: %ProgramData%\Microsoft\Windows Intune Exchange Connector\TracingConfiguration.xml.
2.  Zoek de TraceSourceLine met de volgende sleutel: OnPremisesExchangeConnectorService
3.  Wijzig de knooppuntwaarde **SourceLevel** van **Warning ActivityTracing** (de standaardinstelling) in **Verbose ActivityTracing**, zoals hieronder weergegeven.

    <TraceSourceLine> <Key xsi:type="xsd:string">OnPremisesExchangeConnectorService</Key> <Value xsi:type="TraceSource"> <SourceLevel>All</SourceLevel> <Listeners> <Listener> <ListenerType>CircularTraceListener</ListenerType> <SourceLevel>Verbose ActivityTracing</SourceLevel> <FileSizeQuotaInBytes>10000000</FileSizeQuotaInBytes> <FileName>Microsoft\Windows Intune Exchange Connector\Logs\Connector.svclog</FileName> <FileQuota>30</FileQuota> </Listener> </Listeners> </Value>
    </TraceSourceLine>



### <a name="next-steps"></a>Volgende stappen
Als deze informatie over probleemoplossing u niet heeft geholpen, kunt u contact opnemen met Microsoft Ondersteuning zoals is beschreven in [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md).
