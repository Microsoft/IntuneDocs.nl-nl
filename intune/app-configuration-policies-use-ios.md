---
title: App-configuratiebeleidsregels voor beheerde iOS-apparaten toevoegen | Microsoft Docs
titlesuffix: Azure portal
description: Informatie over het gebruiken van app-configuratiebeleidsregels om configuratiegegevens te leveren aan een iOS-app wanneer deze wordt uitgevoerd.
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d293ff6001ef937c7da0055e6642aa5a1226bd2e
ms.sourcegitcommit: 67c037af31c1f167ec9b4f4baa754631c817e7d1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/01/2017
---
# <a name="add-app-configuration-policies-for-managed-ios-devices"></a>App-configuratiebeleidsregels voor beheerde iOS-apparaten toevoegen

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

App-configuratiebeleidsregels gebruiken in Microsoft Intune om instellingen te leveren wanneer gebruikers een iOS-app uitvoeren. U wijst dit beleid niet rechtstreeks toe aan gebruikers en apparaten. In plaats daarvan koppelt u een beleid aan een app en wijst u vervolgens de app toe. De beleidsinstellingen worden gebruikt wanneer de app deze controleert, doorgaans bij de eerste keer dat de app wordt uitgevoerd.

> [!TIP]
> Dit beleidstype is momenteel alleen beschikbaar voor apparaten met iOS 8.0 en hoger. Ondersteunt de volgende typen app-installaties:
>
> -   **Beheerde iOS-app uit de App Store**
> -   **App-pakket voor iOS**
>
> Zie [Apps toevoegen aan Microsoft Intune](apps-add.md) voor meer informatie over app-installatietypen.

## <a name="create-an-app-configuration-policy"></a>Een app-configuratiebeleid maken

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** + **Intune**.
3. Kies de workload **Mobiele apps**.
4. Klik op **App-configuratiebeleidsregels** in de groep **Beheren** en klik vervolgens op **Toevoegen**.
5. Stel de volgende details in:
    - **Naam**  
      De naam van het profiel die in Azure Portal wordt weergegeven.
    - **Beschrijving**  
      De beschrijving van het profiel die in Azure Portal wordt weergegeven.
    - **Type apparaatinschrijving**  
      Kies **Beheerde apparaten**.
6. Selecteer **iOS** bij **Platform**.
7.  Kies **Gekoppelde app**, klik vervolgens op de blade **Gekoppelde app** en kies de beheerde app waarop u de configuratie wilt toepassen.
8.  Kies op de blade **Configuratiebeleid toevoegen** de optie **Configuratie-instellingen**
9. Selecteer **Indeling van de configuratie-instellingen**. Selecteer een optie:
    - **[Configuration Designer gebruiken](#Use-the-configuration-designer)**
    - **[XML-gegevens invoeren](#enter-xml-data)**
10. Klik op **OK** en op **Toevoegen**.

## <a name="use-configuration-designer"></a>Configuration Designer gebruiken

U kunt Configuration Designer gebruiken voor apps op apparaten die wel of niet zijn ingeschreven bij Intune. Met de ontwerper kunt u specifieke configuratiesleutels en -waarden instellen. U kunt tevens het gegevenstype voor elke waarde opgeven. Instellingen worden automatisch aan apps geleverd wanneer de app wordt geïnstalleerd.

### <a name="add-a-setting"></a>Een instelling toevoegen

1. Stel voor elke sleutel en waarde in de configuratie het volgende in: <ul><li>**Configuratiesleutel**<br>Hiermee wordt de specifieke instellingsconfiguratie uniek geïdentificeerd.</li><li>**Waardetype**<br>Het gegevenstype van de configuratiewaarde. Typen zijn onder meer geheel getal, reëel, tekenreeks of booleaans.</li><li>**Configuratiewaarde**<br>De waarde voor de configuratie.</li></ul>
2. Klik op **OK** om uw configuratiewaarden in te stellen.

### <a name="delete-a-setting"></a>Een instelling verwijderen

1. Klik op de ellips (...) naast de instelling.
2. Selecteer **Verwijderen**.

De tekens \{\{ en \}\} worden alleen gebruikt door tokentypen en mogen niet worden gebruikt voor andere doeleinden.

## <a name="enter-xml-data"></a>XML-gegevens invoeren

U kunt een XML-eigenschappenlijst intypen of plakken die de app-configuratie-instellingen bevat voor bij Intune ingeschreven apparaten. De indeling van de XML-eigenschappenlijst is afhankelijk van de app die u wilt configureren. Neem contact op met de leverancier van de app voor meer informatie over de precieze indeling die moet worden gebruikt.

Intune valideert de XML-indeling. Intune controleert echter niet of de XML-eigenschappenlijst met de doelapp werkt.
Zie voor meer informatie over XML-eigenschappenlijsten [Uitleg van XML-eigenschappenlijsten]

Voor meer informatie over XML-eigenschappenlijsten:

  -  Lees [iOS-apps configureren met configuratiebeleidsregels voor mobiele apps in Microsoft Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).
  -  Raadpleeg [Uitleg van XML Plist](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) in de iOS Developer-bibliotheek.

### <a name="example-format-for-an-app-configuration-xml-file"></a>Voorbeeld van een indeling voor het XML-configuratiebestand voor een app

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
### <a name="supported-xml-plist-data-types"></a>Ondersteunde XML PList-gegevenstypen

Intune ondersteunt de volgende gegevenstypen in een eigenschappenlijst:

- &lt;geheel getal&gt;
- &lt;reëel&gt;
- &lt;tekenreeks&gt;
- &lt;matrix&gt;
- &lt;woordenlijst&gt;
- &lt;waar /&gt; of &lt;onwaar /&gt;

### <a name="tokens-used-in-the-property-list"></a>In de eigenschappenlijst gebruikte tokens

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

## <a name="next-steps"></a>Volgende stappen

Ga vervolgens als gebruikelijk door met [toewijzen](apps-deploy.md) en [bewaken](apps-monitor.md) van de app.