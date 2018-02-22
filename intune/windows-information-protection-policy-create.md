---
title: Beveiligingsinstelling voor de beveiliging van apps voor Windows Information Protection (WIP) maken en implementeren met Intune
titlesuffix: Azure portal
description: Beveiligingsinstelling voor de beveiliging van apps voor WIP maken en implementeren met Intune
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 12/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4e3627bd-a9fd-49bc-b95e-9b7532f0ed55
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 940c4bc17face7ecef2b6888e199ba47073659ba
ms.sourcegitcommit: a6fd6b3df8e96673bc2ea48a2b9bda0cf0a875ae
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/03/2018
---
# <a name="create-and-deploy-windows-information-protection-wip-app-protection-policy-with-intune"></a>Beveiligingsinstelling voor de beveiliging van apps voor Windows Information Protection (WIP) maken en implementeren met Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Vanaf versie 1704 van Intune kunt u app-beveiligingsbeleid gebruiken met Windows 10 om apps zonder apparaatinschrijving te beveiligen.

## <a name="before-you-begin"></a>Voordat u begint

Hier worden enkele concepten besproken voor het toevoegen van een WIP-beleid.

### <a name="list-of-allowed-and-exempt-apps"></a>Lijst met toegestane en vrijgestelde apps

-   **Toegestane apps**: dit zijn de apps die zich aan dit beleid moeten houden.

-   **Vrijgestelde apps**: deze apps zijn vrijgesteld van dit beleid en hebben zonder beperkingen toegang tot bedrijfsgegevens.

### <a name="types-of-apps"></a>Typen apps

-   **Aanbevolen apps**: een vooraf gevulde lijst met apps (voornamelijk voor Microsoft Office) die u gemakkelijk in het beleid kunt importeren. <!---I really don't know what you mean by "easily import into policy"--->

-   **Store-apps**: u kunt elke app uit Microsoft Store toevoegen aan het beleid.

-   **Windows-bureaublad-apps**: u kunt traditionele Windows-bureaublad-apps toevoegen aan het beleid (zoals .exe, of .dll)

## <a name="pre-requisites"></a>Vereisten

U moet de MAM-provider configureren voordat u een beveiligingsbeleid voor WIP-apps kunt maken. Meer informatie over [de configuratie van uw MAM-provider met Intune](https://docs.microsoft.com/app-protection-policies-configure-windows-10.md).

U moet bovendien beschikken over het volgende:

-   Een [Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium)-licentie.
-   [Update voor Windows Creators](https://blogs.windows.com/windowsexperience/2017/04/11/how-to-get-the-windows-10-creators-update/#o61bC2PdrHslHG5J.97)

> [!IMPORTANT]
> WIP biedt geen ondersteuning voor meerdere identiteiten; er kan slechts één beheerde identiteit tegelijkertijd bestaan.
<!---Should you be linking to a topic that explains what multi-identity is?--->

## <a name="to-add-a-wip-policy"></a>WIP-beleid toevoegen

Nadat u Intune hebt ingesteld in uw organisatie, kunt u een WIP-beleid maken via [Azure Portal](https://docs.microsoft.com/intune-classic/deploy-use/azure-portal-for-microsoft-intune-mam-policies). <!---Is there an azure topic you can use instead of a classic? if not, should this topic be moved into the azure docset?--->

1.  Ga naar het **Intune MAM-dashboard** en kies **Alle instellingen** > **App-beleid**.

2.  Kies op de blade **App-beleid** **Beleid toevoegen** en voer de volgende waarden in:

    a.  **Naam:** typ een naam (vereist) voor het nieuwe beleid.

    b.  **Beschrijving:** typ een optionele beschrijving.

    c.  **Platform:** kies **Windows 10** als het ondersteunde platform voor het beveiligingsbeleid van uw app.

    d.  **Status van de inschrijving:** kies **Zonder inschrijving** als status van de inschrijving voor het beleid.

3.  Kies **Maken**. Het beleid is gemaakt en wordt weergegeven in de tabel op de blade **App- beleid**.

## <a name="to-add-recommended-apps-to-your-allowed-apps-list"></a>Aanbevolen apps toevoegen aan de lijst met toegestane apps

1.  Kies op de blade **App-beleid** de naam van uw beleid en kies vervolgens **Toegestane apps** op de blade **Beleid toevoegen**. De blade **Toegestane apps** wordt geopend, waarop alle apps worden weergegeven die al zijn opgenomen in de lijst voor het beveiligingsbeleid voor deze app.

2.  Kies op de blade **Toegestane apps** **Apps toevoegen**. De blade **Apps toevoegen** wordt geopend, waarin u alle apps ziet die deel van deze lijst uitmaken.

3.  Selecteer elke app waarvoor u toegang wilt krijgen tot uw bedrijfsgegevens en kies vervolgens **OK**. De blade **Toegestane apps** wordt bijgewerkt met alle geselecteerde apps.

## <a name="add-a-store-app-to-your-allowed-apps-list"></a>Een Store-app toevoegen aan de lijst met toegestane apps

**Een Store-app toevoegen**

1.  Kies op de blade **App-beleid** de naam van uw beleid en kies vervolgens **Toegestane apps** in het menu dat wordt weergegeven met alle apps die al zijn opgenomen in de lijst voor dit app-beveiligingsbeleid.

2.  Kies op de blade **Toegestane apps** **Apps toevoegen**.

3.  Kies op de blade **Apps toevoegen** **Store-apps** in de vervolgkeuzelijst. Op de blade worden vakken weergegeven waarmee u een **uitgever** en een **naam** voor de app kunt toevoegen.

4.  Typ de naam van de app en de naam van de uitgever en kies vervolgens **OK**.

    > [!TIP]
    > Dit is een voorbeeld van een app, waarbij de **uitgever** *CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US* is en de **naam** van het product *Microsoft.MicrosoftAppForWindows* is.

5.  Nadat u de gegevens hebt ingevoerd in de velden, kiest u **OK** om de app toe te voegen aan de lijst **Toegestane apps**.

> [!NOTE]
> Als u tegelijkertijd meerdere Store-apps wilt toevoegen, klikt u op het menu **(…)** aan het einde van de rij met apps en voegt u vervolgens meerdere apps toe. Als u klaar bent, kiest u **OK**.

## <a name="add-a-desktop-app-to-your-allowed-apps-list"></a>Een bureaublad-app toevoegen aan de lijst met toegestane apps

**Een bureaublad-app toevoegen**

1.  Kies op de blade **App-beleid** de naam van uw beleid en kies vervolgens **Toegestane apps.** De blade **Toegestane apps** wordt geopend, waarop alle apps worden weergegeven die al zijn opgenomen in de lijst voor het beveiligingsbeleid voor deze app.

2.  Kies op de blade **Toegestane apps** **Apps toevoegen**.

3.  Kies op de blade **Apps toevoegen** **Bureaublad-apps** in de vervolgkeuzelijst.

4.  Nadat u de gegevens hebt ingevoerd in de velden, kiest u **OK** om de app toe te voegen aan de lijst **Toegestane apps**.

> [!NOTE]
> Als u tegelijkertijd meerdere **bureaublad-apps** wilt toevoegen, klikt u op het menu **(…)** aan het einde van de rij met apps en voegt u vervolgens meer apps toe. Als u klaar bent, kiest u **OK**.

## <a name="wip-learning"></a>WIP Learning
<!---You've already defined WIP earlier in the topic. You don't need to keep doing so. --->
Nadat u de apps hebt toegevoegd die u wilt beveiligen met WIP, moet u een beveiligingsmodus toepassen via **WIP Learning**.

### <a name="before-you-begin"></a>Voordat u begint

WIP Learning is een rapport waarmee u uw apps met WIP-functionaliteit en uw voor WIP onbekende apps in de gaten kunt houden. Onbekende apps zijn apps die niet zijn geïmplementeerd door de IT-afdeling van uw organisatie. U kunt deze apps uit het rapport exporteren en toevoegen aan uw WIP-beleid om te voorkomen dat de productiviteit wordt onderbroken voordat WIP in de modus Blokkeren wordt afgedwongen.

<!-- 1631908 --> In addition to viewing information about WIP-enabled apps, you can view a summary of the devices that have shared work data with websites. With this information, you can determine which websites should be added to group and user WIP policies. The summary shows which website URLs are accessed by WIP-enabled apps.

Wanneer u met apps met WIP-functionaliteit en voor WIP onbekende apps werkt, wordt het aanbevolen dat u start met **Stil** of **Onderdrukkingen toestaan** als u met een kleine groep controleert of de juiste apps in de lijst met toegestane apps staan. Vervolgens kunt u uw uiteindelijke afdwingingsbeleid wijzigen via **Blokkeren**.

### <a name="what-are-the-protection-modes"></a>Wat zijn de beveiligingsmodi ?

#### <a name="block"></a>Blokkeren
WIP zoekt naar ongeschikte gegevensuitwisselingsprocedures en zorgt ervoor dat de gebruiker de actie niet verder kan uitvoeren. Dit betreft ook gegevens in niet-zakelijke beveiligde apps en bedrijfsgegevens van personen en apparaten die buiten uw organisatie worden gedeeld.

#### <a name="allow-overrides"></a>Onderdrukkingen toestaan
WIP zoekt naar het delen van onjuiste gegevens en waarschuwt gebruikers als ze een onveilige actie uitvoeren. In deze modus kan de gebruiker echter het beleid negeren en de gegevens delen, waarbij de actie wordt toegevoegd aan uw controlelogboek.

#### <a name="silent"></a>Achtergrond
WIP wordt op de achtergrond uitgevoerd en maakt een registratie van onjuiste gegevensdeling, zonder dat een actie wordt geblokkeerd waarvoor de interactie van een werknemer is vereist in de modus Onderdrukkingen toestaan. Acties die niet zijn toegestaan, zoals apps die ten onrechte toegang willen krijgen tot een netwerkbron of door WIP beveiligde gegevens, worden echter onderbroken.

#### <a name="off-not-recommended"></a>Uit (niet aanbevolen)
WIP is uitgeschakeld en uw gegevens worden niet beveiligd of gecontroleerd.

Als u WIP hebt uitgeschakeld, wordt een poging gedaan om door WIP gemarkeerde bestanden op de lokaal aangesloten schijven te ontsleutelen. Let erop dat de vorige gegevens over de ontsleuteling en het beleid niet automatisch worden toegepast als u de WIP-beveiliging weer inschakelt.

### <a name="add-a-protection-mode"></a>Beschermingsmodus toevoegen

1.  Kies op de blade **App-beleid** de naam van uw beleid en kies vervolgens **Verplichte instellingen**.

    ![Schermopname van trainingsmodus](./media/learning-mode-sc1.png)

1.  Kies **Opslaan**.

### <a name="use-wip-learning"></a>WIP Learning gebruiken

1. Open de Azure-portal. Kies **Meer services**. Type **Intune** in het tekstvakfilter.

3. Kies **Intune** > **Mobiele apps**.

4. Kies **Status van de app-beveiliging** > **Rapporten** > **Kennismaken met Windows Information Protection**.  
 
    Zodra de apps worden weergegeven in het rapport voor de logboekregistratie van WIP, kunt u deze toevoegen aan de beveiligingsbeleidsregels voor uw app.

## <a name="deploy-your-wip-app-protection-policy"></a>Uw WIP-beveiligingsbeleid voor apps implementeren

> [!IMPORTANT]
> Dit is van toepassing op WIP zonder apparaatinschrijving.

<!---not sure why you need the Important note. Isn't this what the topic is about? app protection w/o enrollment?--->

Nadat u het beveiligingsbeleid van uw OHW app hebt gemaakt, moet u deze implementeren in uw organisatie met MAM.

1.  Kies op de blade **App-beleid** het nieuwe beveiligingsbeleid voor uw app, kies **Gebruikersgroepen** > **Gebruikersgroep toevoegen**.

    Er wordt een lijst met gebruikersgroepen op basis van de beveiligingsgroepen in uw Azure Active Directory geopend op de blade **Gebruikersgroep toevoegen**.

1.  Kies de groep waarop u uw beleid wilt toepassen en kies vervolgens **Selecteren** om het beleid te implementeren.
