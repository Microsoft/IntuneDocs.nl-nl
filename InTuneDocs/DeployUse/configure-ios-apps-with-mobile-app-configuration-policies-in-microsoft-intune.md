---
title: Configuratiebeleid voor mobiele iOS-apps gebruiken | Microsoft Intune
description: Gebruik het configuratiebeleid voor mobiele apps in Intune om instellingen op te geven die mogelijk zijn vereist wanneer gebruikers een iOS-app uitvoeren.
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f8808c064589128f7daae810ffbcb3595270685d
ms.openlocfilehash: 953bb702fde1d51303aceff6f84fa62999c5ab57


---

# iOS-apps met configuratiebeleid voor mobiele apps in Microsoft Intune configureren
Gebruik het configuratiebeleid voor mobiele apps in Microsoft Intune om instellingen op te geven die mogelijk zijn vereist wanneer gebruikers een iOS-app uitvoeren. Een app kan gebruikers bijvoorbeeld verplichten het volgende op te geven:

-   Een aangepast poortnummer.

-   Taalinstellingen.

-   Beveiligingsinstellingen.

-   Huisstijlinstellingen, zoals een bedrijfslogo.

Als gebruikers deze instellingen niet correct opgeven, kan dit de werkbelasting van uw helpdesk verhogen en de acceptatie van nieuwe apps vertragen.

Configuratiebeleid voor mobiele apps kan ervoor zorgen dat deze problemen worden voorkomen doordat u deze instellingen bij gebruikers in een beleid kunt implementeren voordat de gebruikers de app uitvoeren. De instellingen worden vervolgens automatisch aangeleverd, en de gebruikers hoeven geen enkele actie te ondernemen.

U implementeert dit beleid niet rechtstreeks bij gebruikers en apparaten. In plaats daarvan koppelt u een beleid aan een app en implementeert u vervolgens de app. De beleidsinstellingen worden gebruikt wanneer de app deze controleert (doorgaans de eerste keer dat de app wordt uitgevoerd).

> [!TIP]
> Dit beleidstype is momenteel alleen beschikbaar voor apparaten met iOS 7.1 en hoger. Ondersteunt de volgende typen app-installaties:
>
> -   **Beheerde iOS-app uit de App Store**
> -   **App-pakket voor iOS**
>
> Zie [Apps implementeren met Microsoft Intune](deploy-apps.md) voor meer informatie over app-installatietypen.

## Een configuratiebeleid voor mobiele apps configureren

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) de optie **Beleid** &gt; **Overzicht** &gt; **Beleid toevoegen**.

2.  Vouw in de lijst met beleidsregels **iOS**uit, kies **Configuratie van mobiele app**en kies vervolgens **Beleid maken**.

    > [!TIP]
    > U kunt alleen aangepaste instellingen voor dit beleidstype configureren. Aanbevolen instellingen zijn niet beschikbaar.

3.  Geef in de sectie **Algemeen** op de pagina **Beleid maken** een naam en optionele beschrijving op voor het configuratiebeleid voor de mobiele app.

4.  In het gedeelte **Configuratiebeleid voor mobiele app** van de pagina typt of plakt u in het vak een XML-eigenschappenlijst met de door u gewenste configuratie-instellingen voor de app. De indeling van de XML-eigenschappenlijst is afhankelijk van de app die u wilt configureren. Neem contact op met de leverancier van de app voor meer informatie over de precieze indeling die moet worden gebruikt.

    > [!TIP]
    > Zie [XML-eigenschappenlijsten](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) in de iOS-ontwikkelaarsbibliotheek voor meer informatie over XML-eigenschappenlijsten.

5.  Klik op **Valideren** om ervoor te zorgen dat het XML-bestand dat u hebt opgegeven een geldige indeling voor de eigenschappenlijst heeft.

    > [!IMPORTANT]
    > Wanneer u op **Valideren** klikt, controleert Intune of het XML-bestand dat u hebt opgegeven, een geldige indeling heeft. Er wordt niet gecontroleerd of de XML-eigenschappenlijst werkt met de app waaraan deze is gekoppeld.

6.  Wanneer u alle instellingen hebt toegevoegd, klikt u op **Beleid opslaan**.

Het nieuwe beleid wordt weergegeven in het knooppunt **Configuratiebeleid** .

## Informatie over de XML-indeling

Intune ondersteunt de volgende gegevenstypen in een eigenschappenlijst:
    
- &lt;integer&gt;
- &lt;real&gt;
- &lt;string&gt;
- &lt;matrix&gt;
- &lt;dict&gt;
- &lt;waar /&gt; of &lt;onwaar /&gt;
     
Zie [Over eigenschappenlijsten](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) in de iOS-ontwikkelaarsbibliotheek voor meer informatie over gegevenstypen.

Intune ondersteunt verder de volgende typen tokens in de lijst met eigenschappen:
- \{\{userprincipalname\}\} - (voorbeeld: **John@contoso.com**)
- \{\{mail\}\} - (voorbeeld: **John@contoso.com**)
- \{\{partialupn\}\} - (voorbeeld: **John**)
- \{\{accountid\}\} - (voorbeeld: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)
- \{\{deviceid\}\} - (voorbeeld: **b9841cd9-9843-405f-be28-b2265c59ef97**)
- \{\{userid\}\} - (voorbeeld: **3ec2c00f-b125-4519-acf0-302ac3761822**)
- \{\{username\}\} - (voorbeeld: **John Doe**)
- \{\{serialnumber\}\} - (voorbeeld: **F4KN99ZUG5V2**) voor iOS apparaten
- \{\{serialnumberlast4digits\}\} - (voorbeeld: **G5V2**) voor iOS apparaten
    
De tekens \{\{ en \}\} worden alleen gebruikt door tokentypen en mogen niet worden gebruikt voor andere doeleinden.

## Een configuratiebeleid voor mobiele apps aan een app koppelen
Nadat u een configuratiebeleid voor mobiele apps hebt gemaakt, moet u dit koppelen aan de iOS-app waarop u de instellingen in het configuratiebeleid wilt toepassen.

Volg hiervoor de stappen voor het maken van een app-implementatie in [Apps voor mobiele apparaten toevoegen in Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md) en [Apps met Microsoft Intune implementeren](deploy-apps-in-microsoft-intune.md). Wanneer u de pagina **Configuratie van mobiele app** van de wizard hebt bereikt, selecteert u in de vervolgkeuzelijst **Beleid voor configuratie van apps** het beleid dat u aan de app wilt koppelen.

Ga daarna verder met de gebruikelijke implementatie van de app.

Wanneer de geïmplementeerde app op een apparaat wordt uitgevoerd, worden de instellingen uitgevoerd die u in het configuratiebeleid voor de mobiele app hebt geconfigureerd.

> [!TIP]
> Als de configuratiebeleidsregels van een of meer mobiele apps met elkaar in conflict zijn, wordt geen van de beleidsregels afgedwongen. Het conflict wordt gemeld in het **Dashboard** in de Intune-beheerconsole.

## Voorbeeld van een indeling voor het XML-configuratiebestand voor een mobiele app

Wanneer u een configuratiebestand voor een mobiele app maakt, kunt u een of meer van de volgende waarden opgeven door van deze indeling gebruik te maken:

```
<dict>
  <key>userprincipalname</key>
  <string>{{userprincipalname}}</string>
  <key>mail</key>
  <string>{{mail}}</string>
  <key>partialupn</key>
  <string>{{partialupn}}</string>
  <key>accountid</key>
  <string>{{accountid}}</string>
  <key>deviceid</key>
  <string>{{deviceid}}</string>
  <key>userid</key>
  <string>{{userid}}</string>
  <key>username</key>
  <string>{{username}}</string>
  <key>serialnumber</key>
  <string>{{serialnumber}}</string>
  <key>serialnumberlast4digits</key>
  <string>{{serialnumberlast4digits}}</string>
  <key>udidlast4digits</key>
  <string>{{udidlast4digits}}</string>
</dict>

```



<!--HONumber=Jul16_HO4-->


