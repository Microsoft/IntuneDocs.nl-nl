---
title: App-configuratiebeleid van Intune voor iOS gebruiken
titleSuffix: Intune on Azure
description: Informatie over het gebruik van het configuratiebeleid voor apps om configuratiegegevens te bieden aan een iOS-app wanneer deze wordt uitgevoerd.
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3a9d56a2f570c0332b394b03f25deb6351b6ba67
ms.sourcegitcommit: 4034ac474bfed358270a32459a2cf2fe02f44e45
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/15/2017
---
# <a name="how-to-use-microsoft-intune-app-configuration-policies-for-ios"></a>App-configuratiebeleid van Microsoft Intune voor iOS gebruiken

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Gebruik het configuratiebeleid voor apps in Microsoft Intune om instellingen op te geven die worden gebruikt wanneer gebruikers een iOS-app uitvoeren. Een app kan gebruikers bijvoorbeeld verplichten het volgende op te geven:

-   Een aangepast poortnummer.

-   Taalinstellingen.

-   Beveiligingsinstellingen.

-   Huisstijlinstellingen, zoals een bedrijfslogo.

Als gebruikers deze instellingen niet correct opgeven, kan dit de werkbelasting van uw helpdesk verhogen en de acceptatie van nieuwe apps vertragen.

Het configuratiebeleid voor apps kan ervoor zorgen dat deze problemen worden voorkomen doordat u deze instellingen bij gebruikers in een beleid kunt toewijzen voordat de gebruikers de app uitvoeren. De instellingen worden vervolgens automatisch aangeleverd, en de gebruikers hoeven geen enkele actie te ondernemen. De apps moeten zijn ontwikkeld voor ondersteuning van het gebruik van app-configuraties. Neem contact op met de leverancier van de app voor meer informatie.

U wijst dit beleid niet rechtstreeks toe aan gebruikers en apparaten. In plaats daarvan koppelt u een beleid aan een app en wijst u vervolgens de app toe. De beleidsinstellingen worden gebruikt wanneer de app deze controleert (doorgaans de eerste keer dat de app wordt uitgevoerd).

> [!TIP]
> Dit beleidstype is momenteel alleen beschikbaar voor apparaten met iOS 8.0 en hoger. Ondersteunt de volgende typen app-installaties:
>
> -   **Beheerde iOS-app uit de App Store**
> -   **App-pakket voor iOS**
>
> Zie [Apps toevoegen aan Microsoft Intune](apps-add.md) voor meer informatie over app-installatietypen.

## <a name="create-an-app-configuration-policy"></a>Een app-configuratiebeleid maken
1.  Meld u aan bij Azure Portal.
2.  Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3.  Kies **Mobiele apps** op de blade **Intune**.
4.  Kies **Beheren** > **App-configuratiebeleid** in de workload **Mobiele apps**.
5.  Kies blade met de lijst met configuratiebeleidsregels **Toevoegen**.
6.  Geef op de blade **Configuratiebeleid toevoegen** een **naam** en een optionele **beschrijving** op voor het app-configuratiebeleid.
7.  Kies voor **Type apparaatregistratie** een van de volgende opties:
    - **Geregistreerd bij Intune**: voor apps die worden beheerd door Intune.
    - **Niet geregistreerd bij Intune**: voor apps die niet worden beheerd door Intune of die door derden worden beheerd.
8.  Kies voor **Platform** de optie **iOS** (voor apparaten die alleen bij Intune zijn ingeschreven)
9.  Kies **Gekoppelde app**, klik vervolgens op de blade **Gekoppelde app** en kies de beheerde app waarop u de configuratie wilt toepassen.
10. Kies op de blade **Configuratiebeleid toevoegen** de optie **Configuratie-instellingen**
11. Kies op de blade **Configuratie-instellingen** hoe u de XML-waarden wilt opgeven waaruit het configuratieprofiel bestaat. ER zijn twee opties:
    - **XML-gegevens invoeren** (alleen voor apparaten die zijn ingeschreven bij Intune): voer een XML-eigenschappenlijst in of plak een lijst die de gewenste configuratie-instellingen voor de app bevat. De indeling van de XML-eigenschappenlijst is afhankelijk van de app die u wilt configureren. Neem contact op met de leverancier van de app voor meer informatie over de precieze indeling die moet worden gebruikt.
Er wordt gecontroleerd dat de XML die u hebt ingevoerd een geldige indeling heeft. Er wordt niet gecontroleerd of de XML-eigenschappenlijst werkt met de app waaraan deze is gekoppeld.
Zie [XML-eigenschappenlijsten](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) in de iOS-ontwikkelaarsbibliotheek voor meer informatie over XML-eigenschappenlijsten.
    - **Configuratieontwerper gebruiken** (ongeacht of het apparaat is ingeschreven bij Intune): hiermee kunt u XML-sleutelparen en XML-waardeparen rechtstreeks in de portal opgeven.
11. Als u klaar bent, gaat u terug naar de blade **Configuratieprofiel toevoegen** en kiest u **Maken**.

Het beleid wordt gemaakt en wordt weergegeven op de blade met de lijst met beleidsregels.



>[!Note]
>U kunt de [Intune App SDK](https://docs.microsoft.com/intune/app-sdk-ios) gebruiken om LOB-apps voor te bereiden op beheer door app-beveiligingsbeleid en app-configuratiebeleid van Intune, ongeacht of het apparaat bij Intune is ingeschreven. U kunt bijvoorbeeld een app-configuratiebeleid gebruiken om toegestane en geblokkeerde URL's te configureren voor de [Intune Managed Browser](app-configuration-managed-browser.md). Zodra een app compatibel is met deze beleidsregels, kunt u de app configureren met behulp van een beleidsregel.


Wanneer de toegewezen app op een apparaat wordt uitgevoerd, worden de instellingen uitgevoerd die u in het configuratiebeleid voor de app hebt geconfigureerd.
Zie de documentatie voor de app die u wilt configureren voor informatie over wat er gebeurt als een of meer beleidsregels voor de configuratie van de app strijdig zijn.

>[!Tip]
>U kunt ook Graph API gebruiken om deze taken uit te voeren. Zie het Engelstalige [Graph API Reference MAM Targeted Config](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create) voor meer informatie.


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

## <a name="next-steps"></a>Volgende stappen

Ga vervolgens als gebruikelijk door met [toewijzen](apps-deploy.md) en [bewaken](apps-monitor.md) van de app.