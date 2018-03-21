---
title: App-beveiligingsbeleid voor Windows-gegevensbescherming (WIP) maken en dit implementeren
titlesuffix: Microsoft Intune
description: Met Microsoft Intune app-beveiligingsbeleid voor Windows-gegevensbescherming (WIP) maken en dit implementeren
keywords: 
author: Erikre
ms.author: erikre
manager: doubeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4e3627bd-a9fd-49bc-b95e-9b7532f0ed55
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4325d77982bcca748a38696fbbbb413a1c304ffb
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/08/2018
---
# <a name="create-and-deploy-windows-information-protection-wip-app-protection-policy-with-intune"></a>Beveiligingsinstelling voor de beveiliging van apps voor Windows Information Protection (WIP) maken en implementeren met Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

U kunt app-beveiligingsbeleid gebruiken met Windows 10-apps om apps zonder apparaatinschrijving te beveiligen.

## <a name="before-you-begin"></a>Voordat u begint

U moet enkele concepten begrijpen voor het toevoegen van WIP-beleid:

### <a name="list-of-allowed-and-exempt-apps"></a>Lijst met toegestane en vrijgestelde apps

-   **Toegestane apps**: dit zijn de apps die zich aan dit beleid moeten houden.

-   **Vrijgestelde apps**: deze apps zijn vrijgesteld van dit beleid en hebben zonder beperkingen toegang tot bedrijfsgegevens.

### <a name="types-of-apps"></a>Typen apps

-   **Aanbevolen apps**: een vooraf gevulde lijst met apps (voornamelijk voor Microsoft Office) die u gemakkelijk in het beleid kunt importeren.
-   **Store-apps**: u kunt elke app uit Microsoft Store toevoegen aan het beleid.
-   **Windows-bureaublad-apps**: u kunt traditionele Windows-bureaublad-apps toevoegen aan het beleid (zoals .exe, of .dll)

## <a name="prerequisites"></a>Vereisten

U moet de MAM-provider configureren voordat u een beveiligingsbeleid voor WIP-apps kunt maken. Meer informatie over [de configuratie van uw MAM-provider met Intune](app-protection-policies-configure-windows-10.md).

U moet bovendien beschikken over de volgende licentie en update:

-   Een [Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium)-licentie
-   [Update voor Windows Creators](https://blogs.windows.com/windowsexperience/2017/04/11/how-to-get-the-windows-10-creators-update/#o61bC2PdrHslHG5J.97)

> [!IMPORTANT]
> WIP biedt geen ondersteuning voor meerdere identiteiten; er kan slechts één beheerde identiteit tegelijkertijd bestaan.

## <a name="to-add-a-wip-app-protection-policy"></a>App-beveiligingsbeleid voor WIP toevoegen

Nadat u Intune hebt ingesteld in uw organisatie, kunt u specifiek WIP-beleid maken.

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**.
3. Selecteer **Mobiele apps** op de blade **Microsoft Intune**.
4. Selecteer **App-beveiligingsbeleid** op de blade **Mobiele apps**.
5. Klik op **Een beleid toevoegen** om de blade **Een beleid toevoegen** weer te geven.
6. Voeg de volgende waarden toe:
    - **Naam:** typ een naam (vereist) voor het nieuwe beleid.
    - **Beschrijving:** (optioneel) typ een beschrijving.
    - **Platform:** kies **Windows 10** als het ondersteunde platform voor het beveiligingsbeleid van uw app.
    - **Status van de inschrijving:** kies **Zonder inschrijving** als status van de inschrijving voor het beleid.
7.  Kies **Maken**. Het beleid wordt gemaakt en weergegeven in de tabel op de blade **App-beveiligingsbeleid**.

## <a name="to-add-recommended-apps-to-your-allowed-apps-list"></a>Aanbevolen apps toevoegen aan de lijst met toegestane apps

1. Selecteer **Mobiele apps** op de blade **Microsoft Intune**.
2. Selecteer **App-beveiligingsbeleid** op de blade **Mobiele apps**.
3. Op de blade **App-beveiligingsbeleid** kiest u het beleid dat u wilt bewerken. De blade **Intune-app-beveiliging** wordt weergegeven.
4. Kies **Beveiligde apps** op de blade **Intune-app-beveiliging**. De blade **Beveiligde apps** wordt geopend, waarop alle apps worden weergegeven die al zijn opgenomen in de lijst voor het beveiligingsbeleid voor deze app.
5. Selecteer **Apps toevoegen**. In **Apps toevoegen** ziet u een lijst gefilterde apps. Met de lijst bovenaan de blade kunt u de lijstfilter wijzigen.
6. Selecteer elke app die u toegang wilt bieden tot uw bedrijfsgegevens.
7. Klik op **OK**. De blade **Beveiligde apps** wordt bijgewerkt met alle geselecteerde apps.
8. Klik op **Opslaan**.

## <a name="add-a-store-app-to-your-allowed-apps-list"></a>Een Store-app toevoegen aan de lijst met toegestane apps

**Een Store-app toevoegen**
1. Selecteer **Mobiele apps** op de blade **Microsoft Intune**.
2. Selecteer **App-beveiligingsbeleid** op de blade **Mobiele apps**.
3. Op de blade **App-beveiligingsbeleid** kiest u het beleid dat u wilt bewerken. De blade **Intune-app-beveiliging** wordt weergegeven.
4. Kies **Beveiligde apps** op de blade **Intune-app-beveiliging**. De blade **Beveiligde apps** wordt geopend, waarop alle apps worden weergegeven die al zijn opgenomen in de lijst voor het beveiligingsbeleid voor deze app.
5. Selecteer **Apps toevoegen**. In **Apps toevoegen** ziet u een lijst gefilterde apps. Met de lijst bovenaan de blade kunt u de lijstfilter wijzigen.
6. In de lijst selecteert u **Store-apps**.
7. Voer waarden in voor **Naam**, **Uitgever**, **Productnaam** en **Actie**. Stel de waarde van **Actie** in op **Toestaan** zodat de app toegang heeft tot uw zakelijke gegevens.
9. Klik op **OK**. De blade **Beveiligde apps** wordt bijgewerkt met alle geselecteerde apps.
10. Klik op **Opslaan**.

## <a name="add-a-desktop-app-to-your-allowed-apps-list"></a>Een bureaublad-app toevoegen aan de lijst met toegestane apps

**Een bureaublad-app toevoegen**
1. Selecteer **Mobiele apps** op de blade **Microsoft Intune**.
2. Selecteer **App-beveiligingsbeleid** op de blade **Mobiele apps**.
3. Op de blade **App-beveiligingsbeleid** kiest u het beleid dat u wilt bewerken. De blade **Intune-app-beveiliging** wordt weergegeven.
4. Kies **Beveiligde apps** op de blade **Intune-app-beveiliging**. De blade **Beveiligde apps** wordt geopend, waarop alle apps worden weergegeven die al zijn opgenomen in de lijst voor het beveiligingsbeleid voor deze app.
5. Selecteer **Apps toevoegen**. In **Apps toevoegen** ziet u een lijst gefilterde apps. Met de lijst bovenaan de blade kunt u de lijstfilter wijzigen.
6. In de lijst selecteert u **Bureaublad-apps**.
7. Voer waarden in voor **Naam**, **Uitgever**, **Productnaam**, **Bestand**, **Minimale versie**, **Maximale versie** en **Actie**. Stel de waarde van **Actie** in op **Toestaan** zodat de app toegang heeft tot uw zakelijke gegevens.
9. Klik op **OK**. De blade **Beveiligde apps** wordt bijgewerkt met alle geselecteerde apps.
10. Klik op **Opslaan**.

## <a name="wip-learning"></a>WIP Learning
Nadat u de apps hebt toegevoegd die u wilt beveiligen met WIP, moet u een beveiligingsmodus toepassen via **WIP Learning**.

### <a name="before-you-begin"></a>Voordat u begint

WIP Learning is een rapport waarmee u uw apps met WIP-functionaliteit en uw voor WIP onbekende apps in de gaten kunt houden. Onbekende apps zijn apps die niet zijn geïmplementeerd door de IT-afdeling van uw organisatie. U kunt deze apps uit het rapport exporteren en toevoegen aan uw WIP-beleid om te voorkomen dat de productiviteit wordt onderbroken voordat WIP in de modus Blokkeren wordt afgedwongen.

<!-- 1631908 -->
Er wordt informatie over WIP-apps weergegeven en u kunt een overzicht bekijken van de apparaten die zakelijke gegevens hebben gedeeld met websites. Met deze informatie kunt u bepalen welke websites er moeten worden toegevoegd aan WIP-beleid voor groepen en gebruikers. In het overzicht ziet u welke website-URL's worden gebruikt door apps waarvoor WIP is ingeschakeld.

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

1.  Selecteer een instelling en kies vervolgens **Opslaan**.

### <a name="use-wip-learning"></a>WIP Learning gebruiken

1. Open [Azure Portal](https://portal.azure.com). Kies **Alle services**. Type **Intune** in het tekstvakfilter.

3. Kies **Intune** > **Mobiele apps**.

4. Kies **Status van de app-beveiliging** > **Rapporten** > **Kennismaken met Windows Information Protection**.  

    Zodra de apps worden weergegeven in het rapport voor de logboekregistratie van WIP, kunt u deze toevoegen aan de beveiligingsbeleidsregels voor uw app.

## <a name="allow-windows-search-indexer-to-search-encrypted-items"></a>De Windows Search-indexeerfunctie toestaan om versleutelde items te zoeken
Hiermee kunt u het indexeren van items toestaan of verbieden. Deze schakeloptie dient voor de Windows Search-indexeerfunctie. Hiermee bepaalt u of items die zijn versleuteld, worden geïndexeerd, zoals de bestanden met Windows-gegevensbescherming (WIP).

Deze optie voor app-beveiligingsbeleid bevindt zich in de **geavanceerde instellingen** van het beleid voor Windows-gegevensbescherming. Het beveiligingsbeleid van de app moet worden ingesteld op het *Windows 10*-platform en de **inschrijvingsstatus** van het app-beleid moet worden ingesteld op **Bij inschrijving**.

Wanneer het beleid wordt ingeschakeld, worden de items met WIP-beveiliging geïndexeerd en worden de metagegevens opgeslagen op een niet-versleutelde locatie. De metagegevens bevatten gegevens zoals het bestandspad en de wijzigingsdatum.

Als het beleid is uitgeschakeld, worden de items met WIP-beveiliging niet geïndexeerd en worden ze niet weergegeven in de resultaten in Cortana of Verkenner. Als er te veel mediabestanden met WIP-beveiliging op het apparaat staan, kunnen de prestaties bij gebruik van foto's en Groove-apps ook worden beïnvloed.

## <a name="add-encrypted-file-extensions"></a>Extensies van versleutelde bestanden toevoegen

U kunt niet alleen de optie om de **Windows Search-indexeerfunctie toe te staan om te zoeken naar versleutelde items** gebruiken, maar u kunt ook een lijst bestandsextensies opgeven. De bestanden met deze extensies worden versleuteld wanneer ze vanaf een Server Message Block-share (SMB) binnen het bedrijf worden gekopieerd, zoals gedefinieerd in de lijst netwerklocaties. Als dit beleid niet is opgegeven, wordt het bestaande gedrag voor automatisch versleutelen toegepast. Als dit beleid is geconfigureerd, worden alleen bestanden met de extensies van de lijst versleuteld.

## <a name="deploy-your-wip-app-protection-policy"></a>Uw WIP-beveiligingsbeleid voor apps implementeren

> [!IMPORTANT]
> Deze informatie is van toepassing op WIP zonder apparaatinschrijving.

<!---not sure why you need the Important note. Isn't this what the topic is about? app protection w/o enrollment?--->

Nadat u het beveiligingsbeleid van uw OHW app hebt gemaakt, moet u deze implementeren in uw organisatie met MAM.

1.  Kies op de blade **App-beleid** het nieuwe beveiligingsbeleid voor uw app, kies **Gebruikersgroepen** > **Gebruikersgroep toevoegen**.

    Er wordt een lijst met gebruikersgroepen op basis van de beveiligingsgroepen in uw Azure Active Directory geopend op de blade **Gebruikersgroep toevoegen**.

2.  Kies de groep waarop u uw beleid wilt toepassen en kies vervolgens **Selecteren** om het beleid te implementeren.

## <a name="next-steps"></a>Volgende stappen

Zie [Uw ondernemingsgegevens beveiligen met Windows-gegevensbescherming (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) voor meer informatie over Windows-gegevensbescherming.
