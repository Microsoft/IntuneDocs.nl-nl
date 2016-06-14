---
# required metadata

title: Problemen met app-implementaties oplossen | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 28ac298e-fb73-4c1c-b3fd-8336639e05e6

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Problemen met app-implementaties oplossen in Microsoft Intune
Dit onderwerp helpt u bij het oplossen van problemen met app-implementaties in Microsoft Intune.

Als u het probleem niet kunt oplossen met deze informatie, raadpleegt u [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md) voor meer manieren om hulp te krijgen.


## Gangbare problemen met app-implementatie

### Als u zich niet kunt aanmelden bij de Microsoft Intune-bedrijfsportal

1.  Controleer of uw account bestaat in de [Office 365-portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) of misschien is uitgeschakeld.

2.  Controleer of u in dit account bent ingericht in de [Office 365-portal](http://go.microsoft.com/fwlink/p/?LinkId=698854).

3.  Controleer in de [Office 365-portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) of u de juiste gebruikersnaam en het juiste wachtwoord gebruikt om u aan te melden bij Intune. Controleer ook of uw gebruikersnaam de volgende indeling heeft: **jan@domein.com**..

### Als de gegevens voor contact opnemen met IT ontbreken in de bedrijfsportal

1.  Klik in de Intune-beheerconsole op **Beheer** &gt; **Bedrijfsportal**.

2.  Stel de gegevens voor **Contact opnemen met IT** in.

### Als u specifieke apps niet in de lijst ziet

1.  Zorg ervoor dat u de lijst met apps controleert op een gebruiker of apparaat waarnaar de app is geïmplementeerd.

2.  Controleer of het apparaat voldoet aan de vereisten voor de app.

### Als er een fout optreedt tijdens het downloaden van een app

1.  Controleer of er maar één gelijktijdige download per gebruiker is. Elke gebruiker kan één app tegelijk downloaden.

2.  Controleer of er niet te veel gelijktijdige downloads per account zijn. Wacht enkele minuten en probeer het vervolgens opnieuw.

3.  Als u een systeemeigen iOS-bericht ontvangt met de mededeling dat u de app niet kunt installeren, dat de installatie is geannuleerd of dat u het opnieuw moet proberen, kan dit worden veroorzaakt door intensief verkeer. Wacht enkele minuten en probeer het vervolgens opnieuw.

4.  Als de voortgangsbalk voor het downloaden van de iOS-app voltooid is, maar de app-installatie mislukt, kan er iets mis zijn met de app-bestanden die u hebt opgegeven.

### Als u op een koppeling naar een iOS-app klikt, gaat u naar een vorige locatie in de iTunes App Store

1.  De huidige iTunes App Store-sessie wordt geopend op de vorige pagina van de app.

2.  Sluit de iTunes App Store op het apparaat en probeer de koppeling opnieuw.

### Als u een foutbericht ontvangt bij het starten van een iOS-app

1.  De vervaldatum van de app is mogelijk niet geldig.

### Als uw app blijft steken in 'Wordt uitgevoerd' tijdens het uploaden

1.  Wanneer u een app uploadt, worden eerst de metagegevens toegevoegd, gevolgd door het app-pakket. Nadat de metagegevens zijn geüpload, wordt de app weergegeven als zijnde in uitvoering. Als u ziet dat de app buitengewoon lang in de uitvoeringsstatus blijft, moet u de app verwijderen en opnieuw uploaden.

2.  Zorg ervoor dat u de implementatie van de app niet beheert terwijl de app in de status 'Wordt uitgevoerd' is.

### Als er een fout optreedt tijdens de installatie van een iOS-app

1.  Controleer of de firewall van uw organisatie toegang geeft tot de inrichtings- en certificeringswebsites van Apple.

2.  Zie de Apple-documentatie voor ontwikkelaars voor meer informatie.

### Fout: Uitgever bestaat niet
U gebruikt **Andere softwareovereenkomst toevoegen** om een licentieovereenkomst van derden toe te voegen. U probeert de uitgever toe te voegen vanaf de pagina **Andere softwarelicentieovereenkomst**. De pagina bevat een lijst met de bestaande uitgevers in alfabetische volgorde.
U voert de ontbrekende uitgever in, maar ontvangt het foutbericht **Uitgever bestaat niet**. 

Dit is standaard. Intune biedt alleen licentietracering voor populaire softwaretitels. Intune vereist dat minimaal vier afzonderlijke accounts de software hebben gerapporteerd voordat deze als keuze beschikbaar is in de licentiewerkbelasting.

### Als beheerde apps geen installatiestatus rapporteren

De installatiestatus is niet verzameld voor beheerde app-installaties voorafgaand aan de service-update voor Microsoft Intune in november 2014. Voor apparaten die beheerde apps voorafgaand aan deze service-update hebben geïnstalleerd, moeten alle desbetreffende app-implementaties worden bijgewerkt met de juiste implementatieactie (bijvoorbeeld **Beschikbare installatie**). De app wordt op elk apparaat bijgewerkt tijdens de automatische controle op beschikbare apps. Zie [Apps bijwerken met Microsoft Intune](/intune/deploy-use/update-apps-using-microsoft-intune) voor meer informatie.

## <a name="BKMK_SoftDistErrorCodes"></a>Foutcodes bij app-implementatie
De volgende tabel bevat algemene fouten die zich kunnen voordoen tijdens de implementatie van Intune-apps, evenals mogelijke oorzaken en oplossingen om u te helpen bij het oplossen van deze fouten.

|Foutcode|Mogelijk probleem|Voorgestelde oplossing|
|--------------|--------------------|------------------------|
|0x80073CFF<br /><br />0x80CF201C (clientfout)|Als u deze app wilt installeren, moet u beschikken over een systeem waarop sideloading is ingeschakeld.|Controleer of het app-pakket is ondertekend met een vertrouwde handtekening en is geïnstalleerd op een apparaat dat lid is van een domein en waarop het AllowAllTrustedApps-beleid is ingeschakeld of op een apparaat dat een Windows Sideloading-licentie bevat en waarop het AllowAllTrustedApps-beleid is ingeschakeld (wordt toegepast wanneer een Windows RT-apparaat wordt ingeschreven).|
|0x80073CF0|Het pakket kan niet worden geopend.|Mogelijke oorzaken:<br /><br />-   Het pakket is niet ondertekend.<br />-   De naam van de uitgever komt niet overeen met de ondertekenende certificaathouder.<br /><br />Controleer het gebeurtenislogboek AppxPackagingOM op meer informatie.|
|0x80073CF3|Validatie van updates, afhankelijkheid of conflict voor het pakket is mislukt|Mogelijke oorzaken:<br /><br />-   Het binnenkomende pakket conflicteert met een geïnstalleerd pakket.<br />-   Er is geen opgegeven pakketafhankelijkheid gevonden.<br />-   Het pakket biedt geen ondersteuning voor de juiste processorarchitectuur.<br /><br />Controleer het gebeurtenislogboek AppXDeployment-Server voor meer informatie.|
|0x80073CFB|Het opgegeven pakket is al geïnstalleerd en opnieuw installeren van het pakket is geblokkeerd|Dit foutbericht kan worden weergegeven als u een pakket installeert dat niet gelijk is aan het pakket dat al is geïnstalleerd. Controleer of de digitale handtekening ook onderdeel is van het pakket. Wanneer een pakket opnieuw is samengesteld of opnieuw is ondertekend, is dat pakket niet meer bitsgewijs identiek aan het eerder geïnstalleerde pakket. Er zijn twee mogelijke opties om deze fout te herstellen:<br /><br />-   Verhoog het versienummer van de app, stel het pakket opnieuw samen en onderteken het opnieuw.<br />-   Verwijder het oude pakket voor elke gebruiker op het systeem voordat u het nieuwe pakket installeert.|

### Volgende stappen
Als deze informatie over probleemoplossing u niet heeft geholpen, kunt u contact opnemen met Microsoft Ondersteuning, zoals wordt beschreven in [Ondersteuning voor Microsoft Intune krijgen](how-to-get-support-for-microsoft-intune.md).


<!--HONumber=May16_HO1-->


