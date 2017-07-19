---
title: App-configuratiebeleid van Intune voor iOS gebruiken
titleSuffix: Intune on Azure
description: Informatie over het gebruik van het configuratiebeleid voor apps om configuratiegegevens te bieden aan een iOS-app wanneer deze wordt uitgevoerd.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 112f60ff208c27825ddd0f4c812535b255894333
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2017
---
# <a name="how-to-use-microsoft-intune-app-configuration-policies-for-ios"></a>App-configuratiebeleid van Microsoft Intune voor iOS gebruiken

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Gebruik het configuratiebeleid voor apps in Microsoft Intune om instellingen op te geven die mogelijk zijn vereist wanneer gebruikers een iOS-app uitvoeren. Een app kan gebruikers bijvoorbeeld verplichten het volgende op te geven:

-   Een aangepast poortnummer.

-   Taalinstellingen.

-   Beveiligingsinstellingen.

-   Huisstijlinstellingen, zoals een bedrijfslogo.

Als gebruikers deze instellingen niet correct opgeven, kan dit de werkbelasting van uw helpdesk verhogen en de acceptatie van nieuwe apps vertragen.

Het configuratiebeleid voor apps kan ervoor zorgen dat deze problemen worden voorkomen doordat u deze instellingen bij gebruikers in een beleid kunt toewijzen voordat de gebruikers de app uitvoeren. De instellingen worden vervolgens automatisch aangeleverd, en de gebruikers hoeven geen enkele actie te ondernemen.

U wijst dit beleid niet rechtstreeks toe aan gebruikers en apparaten. In plaats daarvan koppelt u een beleid aan een app en wijst u vervolgens de app toe. De beleidsinstellingen worden gebruikt wanneer de app deze controleert (doorgaans de eerste keer dat de app wordt uitgevoerd).

> [!TIP]
> Dit beleidstype is momenteel alleen beschikbaar voor apparaten met iOS 8.0 en hoger. Ondersteunt de volgende typen app-installaties:
>
> -   **Beheerde iOS-app uit de App Store**
> -   **App-pakket voor iOS**
>
> Zie [Apps toevoegen aan Microsoft Intune](apps-add.md) voor meer informatie over app-installatietypen.

## <a name="create-an-app-configuration-policy"></a>Een app-configuratiebeleid maken

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Mobiele apps** op de blade **Intune**.
1.  Kies **Beheren** > **App-configuratiebeleid** in de workload **Mobiele apps**.

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

Ga vervolgens naar [Toewijzen](apps-deploy.md) en [bewaak](apps-monitor.md) de app als normaal.

Wanneer de toegewezen app op een apparaat wordt uitgevoerd, worden de instellingen uitgevoerd die u in het configuratiebeleid voor de app hebt geconfigureerd.

> [!TIP]
> Als de configuratiebeleidsregels van een of meer apps met elkaar in conflict zijn, wordt geen van de beleidsregels afgedwongen.

## <a name="create-a-mam-targeted-configuration-policy"></a>Een op MAM gericht configuratiebeleid maken
Via een op MAM gerichte configuratie kan een app configuratiegegevens ontvangen via de Intune App SDK. De indeling en varianten van deze gegevens moeten door de eigenaar/ontwikkelaar van de toepassing worden gedefinieerd en gecommuniceerd aan de klanten van Intune. Intune-beheerders kunnen configuratiegegevens gericht implementeren via de Intune-console van Azure. Gegevens van een op MAM gericht configuratiebeleid kunnen worden opgegeven via de MAM-service naar MAM-WE-toepassingen. De app [Intune Managed Browser](https://docs.microsoft.com/intune/app-configuration-managed-browser) hanteert bijvoorbeeld een lijst met toegestane/geblokkeerde URL's. De configuratiegegevens van de toepassing worden via onze MAM-service direct naar de app gepusht en niet via het MDM-kanaal. [MDM-app-configuratiebeleid](https://docs.microsoft.com/intune/app-configuration-policies-use-ios#create-an-app-configuration-policy) is de systeemeigen oplossing via MDM. Het belangrijkste verschil met een op MAM gericht configuratiebeleid is dat het apparaat waarop de app wordt uitgevoerd, niet hoeft te worden ingeschreven bij MDM. Een op MAM gericht configuratiebeleid is beschikbaar op iOS en Android. Voor iOS moet de app zijn bijgewerkt met de Intune APP SDK voor iOS (versie 7.0.1) en moeten er configuratie-instellingen voor de app zijn opgegeven. De stappen voor het opstellen van een op MAM gericht configuratiebeleid: 

1. Meld u aan bij de **Azure-portal**.

2. Kies **Intune > Mobiele apps - App-configuratiebeleid**.

3. Kies op de blade **App-configuratiebeleid** **Toevoegen**.

4. Voer een **Naam** en een optionele **Beschrijving** voor de instellingen voor de app-configuratie in en kies **Niet geregistreerd bij Intune**.

5. Kies **Vereiste apps selecteren** en kies op de blade met de **doel**-apps de apps voor de platforms. <br>
**Opmerking:** voor LOB-apps selecteert u **Meer apps**. Voer de pakket-id voor uw toepassing in.

6. Kies **OK** om terug te keren naar de blade **App-configuratiebeleid toevoegen**.

7. Kies **Configuratie definiëren**. Op de blade **Configuratie** definieert u sleutel- en waardeparen voor de configuraties.

8. Kies **OK** als u klaar bent.

9. Op de blade **App-configuratie toevoegen** kiest u **Maken**.

De nieuwe configuratie wordt gemaakt en weergegeven op de blade App-configuratie.

Ga vervolgens naar [Toewijzen](apps-deploy.md) en [bewaak](apps-monitor.md) de app als normaal.

Wanneer de toegewezen app (die is geïntegreerd met de Intune APP SDK) op een apparaat wordt uitgevoerd, worden de instellingen uitgevoerd die u in het op MAM gericht configuratiebeleid hebt geconfigureerd. In de toegewezen app moet de ondersteunde versie van de Intune APP SDK zijn geïntegreerd. Zie de [iOS Intune APP SDK Integration Guide](https://docs.microsoft.com/intune/app-sdk-ios) voor meer informatie over de vereisten voor de ontwikkeling van apps voor het gebruik van gericht MAM-configuratiebeleid.

Zie [Graph API Reference MAM gericht Config](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create) voor meer informatie over de mogelijkheden van onze Graph API ten opzichte van de op MAM gerichte configuratiewaarden.

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
