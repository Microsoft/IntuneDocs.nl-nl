---
# required metadata

title: Instellingen voor configuratiebeleid voor Mac OS X | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 98b2f19b-bee8-42d7-a215-a716d56a25a3

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Instellingen voor configuratiebeleid voor Mac OS X in Microsoft Intune

## Instellingen voor algemeen configuratiebeleid

Gebruik het **algemene Mac OS X-configuratiebeleid** in Microsoft Intune om instellingen te configureren voor:

-   **Beveiligingsinstellingen voor apparaten**: hier kiest u uit een lijst met vooraf gedefinieerde instellingen waarmee u verschillende functies en functionaliteiten op het apparaat kunt beheren.

-   **Compatibele en niet-compatibele apps**: hiermee geeft u een lijst op met toepassingen die compatibel of niet compatibel zijn in uw bedrijf. Het Rapport niet-compatibele apps kan worden gebruikt om de compatibiliteit van apps die u in de lijst hebt opgegeven, te vergelijken met de apps die gebruikers hebben geïnstalleerd (de installatie van de app kan echter niet worden geblokkeerd).

Als de instelling die u zoekt niet wordt weergegeven in deze lijst, kunt u deze maken met behulp van een aangepast Mac OS X-beleid waarmee u instellingen kunt importeren die u hebt gemaakt met behulp van het hulpprogramma Apple Configurator. Zie **Aangepaste beleidsinstellingen** verderop in dit onderwerp voor meer informatie.

### Wachtwoordinstellingen

|Naam van de instelling|Details|
|----------------|---------------|
|**Een wachtwoord vereisen om apparaten te ontgrendelden**|Hiermee geeft u op of gebruikers een wachtwoord moeten invoeren om toegang te krijgen tot hun Mac-computer. **Belangrijk:** in tegenstelling tot gebruikers van iOS-apparaten ontvangen gebruikers van Mac OS X-apparaten niet onmiddellijk een melding dat hun wachtwoord moet worden bijgewerkt om te voldoen aan deze instelling.|
|**Vereist wachtwoordtype**|Hiermee geeft u op of het wachtwoord alleen numerieke tekens hoeft te bevatten of dat het wachtwoord **alfanumeriek** moet zijn (dat het letters en cijfers moet bevatten). **Belangrijk:** deze instelling wordt alleen ondersteund op Mac OS X-versie 10.10.3 of nieuwer.|
|**Aantal complexe tekens dat is vereist in wachtwoord**|Hiermee geeft u op hoeveel complexe tekens zijn vereist in het wachtwoord (tussen **0** - **4** tekens).).<br /><br />Een complex teken is een symbool, zoals **?**'|
|**Minimale wachtwoordlengte**|Hiermee geeft u de minimale lengte op van het wachtwoord (tussen **4** en **14** tekens).|
|**Eenvoudige wachtwoorden toestaan**|Hiermee stelt u in dat eenvoudige wachtwoorden mogen worden gebruikt (zoals**0000**of**1234**).'.|
|**Minuten inactief voordat wachtwoord is vereist**|Hiermee geeft u op hoe lang de computer inactief moet zijn voordat een wachtwoord vereist is om te ontgrendelen.|
|**Wachtwoordverlooptijd (dagen)**|Hiermee geeft u op na hoeveel dagen de gebruiker het wachtwoord moet wijzigen (tussen **1** - **255** dagen).|
|**Wachtwoordgeschiedenis onthouden**|Deze instelling wordt gebruikt om te voorkomen dat de gebruiker een eerder gebruikt wachtwoord opnieuw gebruikt. Wanneer deze optie is ingesteld, kunt u ook **Wachtwoorden niet opnieuw gebruiken** instellen om in te stellen hoeveel eerder gebruikte wachtwoorden niet opnieuw mogen worden gebruikt (van **1** - **24**).|
|**Minuten van inactiviteit voordat de schermbeveiliging wordt geactiveerd**|Hiermee geeft u de tijdsduur op die de computer inactief moet zijn voordat de schermbeveiliging wordt geactiveerd.|

### Instellingen voor compatibele en niet-compatibele apps
In de lijst met **Compatibele &amp; niet-compatibele apps voor Mac OS X**, schakelt u **Beheerde instellingen voor apparaten** in en geeft u een lijst met compatibele of niet-compatibele apps op met behulp van de volgende gegevens:

> [!NOTE]
> Een enkele beleidsregel kan alleen een lijst met compatibele of een lijst met niet-compatibele apps bevatten. U kunt niet beide in dezelfde beleidsregel opgeven.
> 
> Met Intune kunt u apparaten met niet-compatibele apps rapporteren. De installatie van niet-compatibele apps wordt niet geblokkeerd en deze apps worden niet verwijderd.

|Naam van de instelling|Details|
|----------------|---------------|
|**Rapporteren wanneer gebruikers niet-compatibele apps installeren die in de lijst staan**|Hiermee wordt een lijst weergegeven met Mac OS X-apps die gebruikers niet mogen installeren. Als gebruikers deze apps installeren, worden ze gerapporteerd in de **Rapporten over niet-compatibele apps**.|
|**Niet-compliantie melden wanneer gebruikers apps installeren die niet in de lijst staan**|Hiermee wordt een lijst weergegeven met Mac OS X-apps die gebruikers mogen installeren. Als gebruikers andere apps installeren, worden ze gerapporteerd in de **Rapporten over niet-compatibele apps**.|
|**Toevoegen**|Hiermee voegt u een app toe aan de geselecteerde lijst. Geef een naam van uw keuze op, eventueel de uitgever van de app, en de bundel-id van de app. **Tip:** als u de bundel-id van een app wilt vinden, volgt u de volgende stappen op een Mac-computer waarop de app is geïnstalleerd:<ol><li>Open de map waarin de app is geïnstalleerd (bijvoorbeeld **/Toepassingen**)</li><li>Selecteer de *&lt;Appnaam&gt;***.app**-bundel en kies **Pakketinhoud weergeven**</li><li>Open het bestand **Info.plist**</li><li>Controleer de waarde die is gekoppeld aan de sleutel **CFBundleIdentifier**</li></ol>De notatie voor de bundel-id is **com.contoso.appname**|
|**Apps importeren**|Hiermee importeert u een lijst met apps die u hebt opgegeven in een bestand met door komma's gescheiden waarden. Gebruik de indeling, app-naam, uitgever en de app-bundel-id in het bestand.|
|**Bewerken**|Hiermee kunt u de naam, de uitgever en de app-bundel-id van de geselecteerde app bewerken.|
|**Verwijderen**|Hiermee verwijdert u de geselecteerde app uit de lijst.|
> [!TIP]
> Zie [Inzicht in Microsoft Intune-bewerkingen met behulp van rapporten](understand-microsoft-intune-operations-by-using-reports.md) voor meer informatie over Intune-rapporten.

> [!IMPORTANT]
> Als op een Mac OS X-apparaat de slaapstandmodus is ingeschakeld, kunnen beleidsregels en profielen niet worden afgeleverd of geïnventariseerd. Als gevolg hiervan wordt op de Intune-console mogelijk tijdelijk de status **Foutieve beleidsinstellingen** weergegeven tot de volgende keer dat het apparaat uit de slaapstand wordt gehaald.

### Compatibele apps en niet-compatibele apps controleren
Gebruik de **Rapporten met niet-compatibele apps** om de compatibiliteit van de opgegeven apps weer te geven.

#### Het rapport uitvoeren

1.  Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) op **Rapporten** &gt; **Rapporten voor niet-compatibele apps**.

2.  Selecteer de apparaatgroepen die u wilt controleren, geef aan of u op compatibele apps, op niet-compatibele apps of op beide wilt controleren, en klik vervolgens op **Rapport weergeven**.

## Aangepaste beleidsinstellingen voor Mac OS X in Microsoft Intune
Gebruik het **Aangepaste Mac OS X-configuratiebeleid** van Microsoft Intune om instellingen die u met het [hulpprogramma Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) hebt gemaakt, te implementeren op Mac OS X-apparaten. Met dit hulpprogramma kunt u veel instellingen configureren die de werking van deze apparaten regelen en kunt u deze instellingen exporteren naar een configuratieprofiel. U kunt dit configuratieprofiel vervolgens importeren naar een aangepast Mac OS X-beleid voor Intune en de instellingen implementeren voor gebruikers en apparaten in uw organisatie.

Op deze manier kunt u Mac OS X-instellingen implementeren die niet met het algemene configuratiebeleid van Intune voor Mac OS X kunnen worden geconfigureerd.

### Vereisten
Voordat u begint, moet u de Apple Configurator hebben geïnstalleerd en een configuratiebestand hebben gemaakt met de instellingen die u wilt implementeren voor de gebruikers en apparaten. U kunt de Apple Configurator downloaden in de [Mac App Store](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12). Daar vindt u ook meer informatie over dit hulpprogramma.

> [!NOTE]
> Er wordt in Intune niet gerapporteerd of de afzonderlijke instellingen in een aangepast Mac OS X-beleid compatibel zijn. Er wordt echter wel gerapporteerd of het beleid in z’n geheel compatibel is.

### Algemene instellingen

|Naam van de instelling|Details|
    |----------------|--------------------|
    |**Naam**|Voer een unieke naam in voor het aangepaste Mac OS X-beleid, zodat u deze gemakkelijk kunt herkennen in de Intune-console.|
    |**Beschrijving**|Geef een beschrijving op die een overzicht biedt van het aangepaste Mac OS X-beleid, evenals andere relevante informatie die u helpt om het beleid terug te vinden.|


### Aangepaste instellingen

|Naam van de instelling|Details|
    |----------------|--------------------|
    |**Aangepaste configuratieprofielnaam (weergegeven voor gebruikers)**|Geef een naam op voor het beleid, zoals dit moet worden weergegeven op het apparaat en in de Intune-beleidsrapporten.|
    |**Configuratieprofielbestand**|Klik op **Importeren**en blader vervolgens naar het configuratieprofiel dat u hebt gemaakt met behulp van de Apple Configurator. **Tip:** zie [Een configuratieprofielbestand maken](#BKMK_Prof) in dit onderwerp voor informatie over het maken van het configuratieprofiel.|
    |**Configuratieprofieldetails**|Geeft de XML-code weer voor het configuratieprofiel dat u hebt geïmporteerd.|



### Een configuratieprofielbestand maken
U kunt het configuratieprofielbestand dat door het aangepaste beleid wordt gebruikt op twee manieren maken:

-   Exporteer het bestand (met de extensie **.mobileconfig**) uit het hulpprogramma Apple Configurator.

-   Schrijf het bestand zelf met behulp van het bijbehorende schema van de [Apple Configuration Profile Key Reference](https://developer.apple.com/library/ios/featuredarticles/iPhoneConfigurationProfileRef/Introduction/Introduction.html).


> [!IMPORTANT]
> Als op een Mac OS X-apparaat de slaapstandmodus is ingeschakeld, kunnen beleidsregels en profielen niet worden afgeleverd of geïnventariseerd. Als gevolg hiervan wordt op de Intune-console mogelijk tijdelijk de status **Foutieve beleidsinstellingen** weergegeven tot de volgende keer dat het apparaat uit de slaapstand wordt gehaald.

### Zie ook
[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=May16_HO1-->


