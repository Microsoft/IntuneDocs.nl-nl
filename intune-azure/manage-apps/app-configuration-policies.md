---
title: Configuratiebeleid van Intune-apps gebruiken | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: informatie over het gebruik van het configuratiebeleid voor apps om configuratiegegevens te bieden aan een iOS-app wanneer deze wordt uitgevoerd.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 424fae862592c1ab5b4221fb5ad40a52c39f6760
ms.openlocfilehash: 75e3f3f62dd392cda1530321b12cd27e9ee8847f

---

# <a name="how-to-use-intune-app-configuration-policies"></a>Configuratiebeleid van Intune-apps gebruiken

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Gebruik het configuratiebeleid voor apps in Microsoft Intune om instellingen op te geven die mogelijk zijn vereist wanneer gebruikers een app uitvoeren. Een app kan gebruikers bijvoorbeeld verplichten het volgende op te geven:

-   Een aangepast poortnummer.

-   Taalinstellingen.

-   Beveiligingsinstellingen.

-   Huisstijlinstellingen, zoals een bedrijfslogo.

Als gebruikers deze instellingen niet correct opgeven, kan dit de werkbelasting van uw helpdesk verhogen en de acceptatie van nieuwe apps vertragen.

Het configuratiebeleid voor apps kan ervoor zorgen dat deze problemen worden voorkomen doordat u deze instellingen bij gebruikers in een beleid kunt toewijzen voordat de gebruikers de app uitvoeren. De instellingen worden vervolgens automatisch aangeleverd, en de gebruikers hoeven geen enkele actie te ondernemen.

U wijst dit beleid niet rechtstreeks toe aan gebruikers en apparaten. In plaats daarvan koppelt u een beleid aan een app en implementeert u vervolgens de app. De beleidsinstellingen worden gebruikt wanneer de app deze controleert (doorgaans de eerste keer dat de app wordt uitgevoerd).

> [!TIP]
> Dit beleidstype is momenteel alleen beschikbaar voor apparaten met iOS 8.0 en hoger. Ondersteunt de volgende typen app-installaties:
>
> -   **Beheerde iOS-app uit de App Store**
> -   **App-pakket voor iOS**
>
> Zie [Apps toevoegen aan Microsoft Intune](/intune-azure/manage-apps/add-apps) voor meer informatie over app-installatietypen.

## <a name="create-an-app-configuration-policy"></a>Een app-configuratiebeleid maken

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Overige** > **Intune**.
3. Kies **Apps beheren** op de blade **Intune**.
1.  Kies **Beheren** > **App-configuratiebeleid** in de workload **Apps beheren**.

2.  Kies blade met de lijst met configuratiebeleidsregels **Toevoegen**.

3.  Geef op de blade **Configuratiebeleid toevoegen** een naam en een optionele beschrijving op voor het app-configuratiebeleid.
4.  Kies **Gekoppelde app**, klik vervolgens op de blade **Gekoppelde app** en kies de beheerde app waarop u de configuratie wilt toepassen.
5.  Kies op de blade **Configuratiebeleid toevoegen** **Configuratie-instellingen** en kies vervolgens op deze blade hoe u de XML-waarden wilt opgeven voor het configuratieprofiel uit:
    - **XML-gegevens invoeren**: voer een XML-eigenschappenlijst in of plak een lijst die de gewenste configuratie-instellingen voor de app bevat. De indeling van de XML-eigenschappenlijst is afhankelijk van de app die u wilt configureren. Neem contact op met de leverancier van de app voor meer informatie over de precieze indeling die moet worden gebruikt.
    Er wordt gecontroleerd dat de XML die u hebt ingevoerd een geldige indeling heeft. Er wordt niet gecontroleerd of de XML-eigenschappenlijst werkt met de app waaraan deze is gekoppeld.
    Zie [XML-eigenschappenlijsten](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) in de iOS-ontwikkelaarsbibliotheek voor meer informatie over XML-eigenschappenlijsten.
    - **Configuratieontwerper gebruiken**: hiermee kunt u de XML-sleutel- en -waardeparen rechtstreeks in de portal opgeven.
8. Als u klaar bent, gaat u terug naar de blade **Configuratieprofiel toevoegen** en kiest u **Maken**.

Het beleid wordt gemaakt en wordt weergegeven op de blade met de lijst met configuratiebeleidsregels.

Ga vervolgens naar [Toewijzen](deploy-apps.md) en [bewaak](monitor-apps.md) de app als normaal.

Wanneer de toegewezen app op een apparaat wordt uitgevoerd, worden de instellingen uitgevoerd die u in het configuratiebeleid voor de app hebt geconfigureerd.

> [!TIP]
> Als de configuratiebeleidsregels van een of meer apps met elkaar in conflict zijn, wordt geen van de beleidsregels afgedwongen.

## <a name="information-about-the-xml-file-format"></a>Informatie over de XML-indeling

Intune ondersteunt de volgende gegevenstypen in een eigenschappenlijst:

- &lt;geheel getal&gt;
- &lt;reëel&gt;
- &lt;tekenreeks&gt;
- &lt;matrix&gt;
- &lt;woordenlijst&gt;
- &lt;waar /&gt; of &lt;onwaar /&gt;

Zie [Over eigenschappenlijsten](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) in de iOS-ontwikkelaarsbibliotheek voor meer informatie over gegevenstypen.

Intune ondersteunt verder de volgende typen tokens in de lijst met eigenschappen:
- \{\{userprincipalname\}\} - (voorbeeld: **John@contoso.com**)
- \{\{mail\}\} - (voorbeeld: **John@contoso.com**)
- \{\{partialupn\}\} - (voorbeeld: **Jan**)
- \{\{accountid\}\} - (voorbeeld: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)
- \{\{deviceid\}\} - (voorbeeld: **b9841cd9-9843-405f-be28-b2265c59ef97**)
- \{\{userid\}\} - (voorbeeld: **3ec2c00f-b125-4519-acf0-302ac3761822**)
- \{\{username\}\} - (voorbeeld: **Jan de Vries**)
- \{\{serialnumber\}\} - (voorbeeld: **F4KN99ZUG5V2**) voor iOS-apparaten
- \{\{serialnumberlast4digits\}\} - (Example: **G5V2**) voor iOS-apparaten

De tekens \{\{ en \}\} worden alleen gebruikt door tokentypen en mogen niet worden gebruikt voor andere doeleinden.





## <a name="example-format-for-an-app-configuration-xml-file"></a>Voorbeeld van een indeling voor het XML-configuratiebestand voor een app

Wanneer u een configuratiebestand voor een app maakt, kunt u een of meer van de volgende waarden opgeven door van deze indeling gebruik te maken:

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



<!--HONumber=Feb17_HO1-->


