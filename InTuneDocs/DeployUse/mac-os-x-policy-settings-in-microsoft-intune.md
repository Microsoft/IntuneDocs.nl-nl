---
title: Mac OS X-beleidsinstellingen | Microsoft Intune
description: Intune biedt diverse ingebouwde algemene instellingen die u op Mac OS X-apparaten kunt configureren. Daarnaast kunt u het hulpprogramma Apple Configurator gebruiken om aangepaste instellingen te maken die niet beschikbaar zijn vanuit Intune.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 98b2f19b-bee8-42d7-a215-a716d56a25a3
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a4f7a503417938eabb4334757dcf12a63f082fd3
ms.openlocfilehash: ce30ab0e5a4ce709aafa5892789590b42b484db4


---

# Instellingen voor configuratiebeleid voor Mac OS X in Microsoft Intune

Intune biedt diverse ingebouwde algemene instellingen die u op Mac OS X-apparaten kunt configureren. Daarnaast kunt u het hulpprogramma Apple Configurator gebruiken om aangepaste instellingen te maken die niet beschikbaar zijn vanuit Intune.

## Algemene instellingen voor configuratiebeleid

Gebruik het **algemene Mac OS X-configuratiebeleid** in Microsoft Intune om instellingen te configureren voor:

-   **Beveiligingsinstellingen apparaat**. Hier kiest u uit een lijst met vooraf gedefinieerde instellingen waarmee u verschillende functies en functionaliteiten op het apparaat kunt beheren.

-   **Compatibele en niet-compatibele apps**. Hier kunt u een lijst opgeven van apps die in uw bedrijf compatibel of niet compatibel zijn. Het Rapport niet-compatibele apps kan worden gebruikt om de compatibiliteit van apps die u in de lijst hebt opgegeven, te vergelijken met de apps die gebruikers hebben geïnstalleerd (de installatie van de app kan echter niet worden geblokkeerd).

Als de instelling die u zoekt niet wordt weergegeven in deze lijst, kunt u deze maken met een aangepast Mac OS X-beleid waarmee u instellingen kunt importeren die u hebt gemaakt met de Apple Configurator. Zie "Aangepaste beleidsinstellingen" verderop in dit onderwerp voor meer informatie.

### Wachtwoordinstellingen

|Naam van de instelling|Details|
|----------------|---------------|
|**Een wachtwoord vereisen om apparaten te ontgrendelden**|Hier geeft u op of de gebruiker een wachtwoord moet invoeren om toegang te krijgen tot de Mac-computer. **Belangrijk:** in tegenstelling tot gebruikers van iOS-apparaten ontvangen gebruikers van Mac OS X-apparaten niet onmiddellijk een melding dat hun wachtwoord moet worden bijgewerkt om te voldoen aan deze instelling.|
|**Vereist wachtwoordtype**|Hier geeft u op of het wachtwoord alleen **numerieke** tekens mag bevatten of dat het wachtwoord **alfanumeriek** moet zijn (en dus letters en cijfers moet bevatten). **Belangrijk:** deze instelling wordt alleen ondersteund op Mac OS X-versie 10.10.3 en hoger.|
|**Aantal complexe tekens dat is vereist in wachtwoord**|Hier geeft u op hoeveel complexe tekens zijn vereist in het wachtwoord (tussen **0** en **4**).<br /><br />Een complex teken is een symbool, zoals **?**.|
|**Minimale wachtwoordlengte**|Hier geeft u de minimale lengte van het wachtwoord op (tussen **4** en **14** tekens).|
|**Eenvoudige wachtwoorden toestaan**|Hier stelt u in dat eenvoudige wachtwoorden mogen worden gebruikt, zoals **0000** en **1234**.|
|**Minuten inactief voordat wachtwoord is vereist**|Hier geeft u op hoe lang de computer inactief moet zijn voordat een wachtwoord vereist is om te ontgrendelen.|
|**Verlopen van wachtwoorden (dagen)**|Hier geeft u op na hoeveel dagen de gebruiker het wachtwoord moet wijzigen (tussen **1** en **255** dagen).|
|**Wachtwoordgeschiedenis onthouden**|Hiermee voorkomt u dat de gebruiker een eerder gebruikt wachtwoord opnieuw gebruikt. Wanneer deze optie is ingesteld, kunt u ook **Wachtwoorden niet opnieuw gebruiken** instellen om op te geven hoeveel eerder gebruikte wachtwoorden niet opnieuw mogen worden gebruikt (tussen **1** en **24**).|
|**Minuten van inactiviteit voordat de schermbeveiliging wordt geactiveerd**|Hier geeft u de tijdsduur op die de computer inactief moet zijn voordat de schermbeveiliging wordt geactiveerd.|

### Instellingen voor compatibele en niet-compatibele apps
In de lijst met **compatibele en niet-compatibele apps voor Mac OS X** schakelt u **Beheerde instellingen voor apparaten** in en geeft u een lijst met compatibele of niet-compatibele apps op met behulp van de volgende gegevens.

> [!NOTE]
> Een enkele beleidsregel kan alleen een lijst met compatibele apps of een lijst met niet-compatibele apps bevatten. U kunt niet beide in dezelfde beleidsregel opgeven.
>
> Met Intune kunt u apparaten met niet-compatibele apps rapporteren. De installatie van niet-compatibele apps wordt niet geblokkeerd en deze apps worden niet verwijderd.

|Naam van de instelling|Details|
|----------------|---------------|
|**Rapporteren wanneer gebruikers niet-compatibele apps installeren die in de lijst staan**|Hiermee wordt een lijst weergegeven met Mac OS X-apps die gebruikers niet mogen installeren. Als gebruikers deze apps installeren,worden ze gerapporteerd in de **Rapporten over niet-compatibele apps**.|
|**Niet-compliantie melden wanneer gebruikers apps installeren die niet in de lijst staan**|Hiermee wordt een lijst weergegeven met Mac OS X-apps die gebruikers mogen installeren. Als gebruikers andere apps installeren, worden ze gerapporteerd in de **Rapporten over niet-compatibele apps**.|
|**Toevoegen**|Hiermee voegt u een app toe aan de geselecteerde lijst. Geef een naam van uw keuze op, eventueel de uitgever van de app, en de bundel-id van de app. **Tip:** als u de bundel-id van een app zoekt, volgt u de volgende stappen op een Mac-computer waarop de app is geïnstalleerd:<ol><li>Open de map waarin de app is geïnstalleerd (bijvoorbeeld **/Applications**).</li><li>Selecteer de bundel *&lt;app-naam&gt;***.app** en kies **Toon pakketinhoud**.</li><li>Open het bestand **Info.plist**.</li><li>Controleer de waarde die is gekoppeld aan de sleutel **CFBundleIdentifier**.</li></ol>De notatie voor de bundel-id is **com.contoso.appname**.|
|**Apps importeren**|Hiermee importeert u een lijst met apps die u hebt opgegeven in een bestand met door komma's gescheiden waarden. Gebruik in dit bestand deze indeling: app-naam, uitgever, app-bundel-id.|
|**Bewerken**|Hiermee kunt u de naam, de uitgever en de app-bundel-id van de geselecteerde app bewerken.|
|**Verwijderen**|Hiermee verwijdert u de geselecteerde app uit de lijst.|
> [!TIP]
> Zie [Microsoft Intune-bewerkingen begrijpen met behulp van rapporten](understand-microsoft-intune-operations-by-using-reports.md) voor meer informatie over Intune-rapporten.

> [!IMPORTANT]
> Als op een Mac OS X-apparaat de slaapstandmodus is ingeschakeld, kunnen beleidsregels en profielen niet worden afgeleverd of geïnventariseerd. Als gevolg hiervan wordt op de Intune-console mogelijk tijdelijk de status **Foutieve beleidsinstellingen** weergegeven tot de volgende keer dat het apparaat uit de slaapstand wordt gehaald.

### Compatibele apps en niet-compatibele apps controleren
Gebruik **Rapporten met niet-compatibele apps** om de compatibiliteit van de door u opgegeven apps weer te geven.

#### Een rapport uitvoeren

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) de optie **Rapporten** &gt; **Rapport met niet-compatibele apps**.

2.  Selecteer de apparaatgroepen die u wilt controleren, selecteer of u op compatibele en/of niet-compatibele apps wilt controleren, en kies vervolgens **Rapport weergeven**.

## Aangepaste beleidsinstellingen voor Mac OS X in Microsoft Intune
Gebruik het **aangepaste Mac OS X-configuratiebeleid** van Microsoft Intune om op Mac OS X-apparaten instellingen te implementeren die u met het [hulpprogramma Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) hebt gemaakt. Met dit hulpprogramma kunt u veel instellingen configureren die de werking van deze apparaten regelen en kunt u deze instellingen exporteren naar een configuratieprofiel. U kunt dit configuratieprofiel vervolgens importeren naar een aangepast Mac OS X-beleid voor Intune en de instellingen implementeren voor gebruikers en apparaten in uw organisatie.

Hiermee kunt u Mac OS X-instellingen implementeren die niet met het algemene configuratiebeleid van Intune voor Mac OS X kunnen worden geconfigureerd.

### Vereisten
Voordat u begint, moet u de Apple Configurator hebben geïnstalleerd en een configuratiebestand hebben gemaakt met de instellingen die u wilt implementeren voor de gebruikers en apparaten. In [de Mac App Store](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) kunt u de Apple Configurator downloaden en meer informatie over dit hulpprogramma vinden.

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
    |**Configuratieprofielbestand**|Kies **Importeren** en blader vervolgens naar het configuratieprofiel dat u hebt gemaakt met de Apple Configurator. **Tip:** zie "Een configuratieprofielbestand maken" in dit onderwerp voor informatie over het maken van het configuratieprofiel.|
    |**Configuratieprofieldetails**|Hiermee geeft u de XML-code weer voor het configuratieprofiel dat u hebt geïmporteerd.|



### Een configuratieprofielbestand maken
U kunt het configuratieprofielbestand dat door het aangepaste beleid wordt gebruikt op twee manieren maken:

-   Exporteer het bestand (met de extensie **.mobileconfig**) uit het hulpprogramma Apple Configurator.

-   Schrijf het bestand zelf met het bijbehorende schema van de [Apple Configuration Profile Key Reference](https://developer.apple.com/library/ios/featuredarticles/iPhoneConfigurationProfileRef/Introduction/Introduction.html).


### Zie tevens
[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Oct16_HO4-->


