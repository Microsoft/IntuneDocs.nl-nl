---
title: 'Stapsgewijze instructies: beheersjabloon maken in Microsoft Intune - Azure | Microsoft Docs'
description: In deze zelfstudie of stapsgewijze instructies wordt Microsoft Intune gebruikt om ADMX-sjablonen voor Office, Windows en Microsoft Edge te configureren op Windows 10- en nieuwere apparaten.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
ms.topic: tutorial
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: ''
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a96f291203e1513ab89196b26a7802856f90e048
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77688087"
---
# <a name="tutorial-use-the-cloud-to-configure-group-policy-on-windows-10-devices-with-admx-templates-and-microsoft-intune"></a>Zelfstudie: De cloud gebruiken voor het configureren van groepsbeleid op Windows 10-apparaten met ADMX-sjablonen en Microsoft Intune

> [!NOTE]
> Deze zelfstudie is gemaakt als technische workshop voor Microsoft Ignite. Er zijn meer vereisten dan gebruikelijk is voor zelfstudies omdat er een vergelijking wordt gemaakt tussen het gebruik en configureren van ADMX-beleid in Intune en on-premises.

Beheersjablonen voor groepsbeleid, ook wel ADMX-sjablonen genoemd, bevatten instellingen die u kunt configureren op Windows 10-apparaten, waaronder pc's. De ADMX-sjablooninstellingen zijn beschikbaar in verschillende services. Deze instellingen worden gebruikt door MDM-providers (Mobile Device Management), waaronder Microsoft Intune. U kunt bijvoorbeeld ontwerpideeën inschakelen in PowerPoint, een startpagina instellen in Microsoft Edge, ActiveX-besturingselementen blokkeren in Internet Explorer en meer.

ADMX-sjablonen zijn beschikbaar voor de volgende services:

- **Microsoft Edge**: download op [Microsoft Edge-beleidsbestand](https://www.microsoftedgeinsider.com/en-us/enterprise).
- **Office**: download op [Office 365 ProPlus, Office 2019 en Office 2016](https://www.microsoft.com/download/details.aspx?id=49030).
- **Windows**: ingebouwd in het Windows 10-besturingssysteem.

Zie [Informatie over door ADMX ondersteund beleid](https://docs.microsoft.com/windows/client-management/mdm/understanding-admx-backed-policies) voor meer informatie over ADMX-beleid.

In Microsoft Intune zijn deze sjablonen ingebouwd in de Intune-service en zijn deze beschikbaar als **Beheersjabloonprofielen**. In dit profiel configureert u de instellingen die u wilt opnemen en vervolgens wijst u dit profiel toe aan uw apparaten.

In deze zelfstudie doet u het volgende:

> [!div class="checklist"]
> * Kennismaken met het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
> * Gebruikersgroepen en apparaatgroepen maken.
> * De instellingen in Intune vergelijken met on-premises ADMX-instellingen.
> * Verschillende beheersjablonen maken en de instellingen configureren die gericht zijn op de verschillende groepen.

Aan het einde van dit lab beschikt u over de vaardigheden om aan de slag te gaan met Intune en Microsoft 365 om uw gebruikers te beheren en beheersjablonen te implementeren.

Deze functie is van toepassing op:

- Windows 10 versie 1703 en hoger

## <a name="prerequisites"></a>Vereisten

- Een Microsoft 365 E3- of E5-abonnement dat Intune en Azure Active Directory (AD) Premium bevat. Als u geen E3- of E5-abonnement hebt, kunt u [het gratis proberen](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365?view=o365-worldwide).

  Zie [Uw bedrijf transformeren met Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) voor meer informatie over wat u krijgt bij de verschillende Microsoft 365-licenties.

- Microsoft Intune is geconfigureerd als de **Intune MDM-instantie**. Zie [De instantie voor het beheer van mobiele apparaten instellen](../fundamentals/mdm-authority-set.md) voor meer informatie.

  > [!div class="mx-imgBorder"]
  > ![De MDM-instantie instellen op Microsoft Intune in uw tenantstatus](./media/tutorial-walkthrough-administrative-templates/tenant-status.png)

- Ga als volgt te werk op een on-premises Active Directory-domeincontroller (DC):

  1. Kopieer de volgende Office- en Microsoft Edge-sjablonen naar de [centrale opslag (map SYSVOL)](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra):

      - [Office-beheersjablonen](https://www.microsoft.com/download/details.aspx?id=49030)
      - [Microsoft Edge-beheersjablonen > Beleidsbestand](https://www.microsoftedgeinsider.com/en-us/enterprise)

  2. Maak groepsbeleid om deze sjablonen te pushen naar de computer van een Windows 10 Enterprise-beheerder in hetzelfde domein als de DC. In deze zelfstudie hebt u het volgende gedaan:

      - Het groepsbeleid dat we met deze sjablonen hebben gemaakt, heet **OfficeandEdge**. Deze naam wordt weergeven in de afbeeldingen.
      - De computer die door de Windows 10 Enterprise-beheerder wordt gebruikt, heet de **Beheercomputer**.

      In sommige organisaties heeft een domeinbeheerder twee accounts: een gebruikelijk domeinwerkaccount en een ander domeinbeheerdersaccount dat alleen wordt gebruikt voor domeinbeheerderstaken, zoals groepsbeleid.

      Het doel van deze **Beheercomputer** is dat beheerders zich kunnen aanmelden met hun domeinbeheerdersaccount en toegang kunnen krijgen tot hulpprogramma's voor het beheren van groepsbeleid.

- Ga als volgt te werk op deze **Beheercomputer**:

  - Meld u aan met een domeinbeheerdersaccount.

  - Installeer de **RSAT: hulpprogramma's voor groepsbeleidsbeheer**:

    1. Open de app **Instellingen** > **Apps** > **Optionele functies** > **Functie toevoegen**.
    2. Selecteer **RSAT: hulpprogramma's voor groepsbeleidsbeheer** > **Installeren**.

        Wacht terwijl de functie door Windows wordt geïnstalleerd. Als dit is gebeurd, wordt deze weergegeven in de app **Windows Systeembeheer**.

        > [!div class="mx-imgBorder"]
        > ![Windows Systeembeheer-apps, waaronder de app Groepsbeleidsbeheer](./media/tutorial-walkthrough-administrative-templates/windows-administrative-tools-app.png)

  - Zorg ervoor dat u beschikt over internettoegang en beheerdersrechten voor het Microsoft 365-abonnement dat het Microsoft Endpoint Manager-beheercentrum bevat.

## <a name="open-the-endpoint-manager-admin-center"></a>Het Endpoint Manager-beheercentrum openen

1. Open een Chromium-webbrowser, zoals Microsoft Edge versie 77 of hoger.
2. Ga naar het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) (https://devicemanagement.microsoft.com). Meld u aan met het volgende account:

    **Gebruiker**: Voer het beheerdersaccount van uw Microsoft 365-tenantabonnement in.  
    **Wachtwoord**: Voer het wachtwoord in.

Dit beheercentrum is gericht op apparaatbeheer en bevat Azure-services, zoals Microsoft Azure AD en Intune. Mogelijk ziet u de huisstijl van **Azure Active Directory** en **Intune** niet, maar deze worden wel gebruikt.

U kunt het Endpoint Manager-beheercentrum ook openen vanuit het [Microsoft 365-beheercentrum](https://admin.microsoft.com):

1. Ga naar [https://admin.microsoft.com](https://admin.microsoft.com).
2. Meld u aan met het beheerdersaccount van uw Microsoft 365-tenantabonnement.
3. Selecteer onder **Beheercentrums** de optie **Alle beheercentrums** > **Eindpuntbeheer**. Het Microsoft Endpoint Manager-beheercentrum wordt geopend.

    > [!div class="mx-imgBorder"]
    > ![Alle beheercentrums in het Microsoft 365-beheercentrum bekijken](./media/tutorial-walkthrough-administrative-templates/microsoft365-admin-centers.png)

## <a name="create-groups-and-add-users"></a>Groepen maken en gebruikers toevoegen

On-premises beleid wordt toegepast op LSDOE-volgorde: lokaal, site, domein en organisatie-eenheid (OE). In deze hiërarchie worden lokale beleidsregels overschreven door OE-beleidsregels, sitebeleidregels door domeinbeleidsregels enzovoort.

In Intune worden beleidsregels toegepast op gebruikers en groepen die u maakt. Hier is geen hiërarchie. Als dezelfde instelling wordt bijgewerkt door twee beleidsregels, wordt de instelling weergegeven als een conflict. Als er sprake is van twee compliancebeleidsregels wordt het meest beperkende beleid toegepast. Als twee configuratieprofielen conflicteren, wordt de instelling niet toegepast. Zie [Algemene vragen, problemen en oplossingen met apparaatbeleid en -profielen](device-profile-troubleshoot.md#if-multiple-policies-are-assigned-to-the-same-user-or-device-how-do-i-know-which-settings-gets-applied) voor meer informatie.

In deze volgende stappen maakt u beveiligingsgroepen en voegt u gebruikers toe aan de groepen. U kunt een gebruiker aan meerdere groepen toevoegen. Het is bijvoorbeeld gebruikelijk dat een gebruiker meerdere apparaten heeft, zoals een Surface Pro voor het werk en een mobiel Android-apparaat voor persoonlijk gebruik. En het is gebruikelijk dat een persoon vanaf meerdere van deze apparaten toegang heeft tot organisatieresources.

1. Selecteer in het Endpoint Manager-beheercentrum **Groepen** > **Nieuwe groep**.

2. Voer de volgende instellingen in:

    - **Groepstype**: Selecteer **Beveiliging**.
    - **Groepsnaam**: Voer **Alle Windows 10-studentapparaten** in.
    - **Type lidmaatschap**: Selecteer **Toegewezen**.

3. Selecteer **Leden** en voeg enkele apparaten toe.

    Het toevoegen van apparaten is optioneel. Het doel is te oefenen met het maken van groepen en te leren hoe u apparaten toevoegt. Wees u bewust van wat u gaat doen als u deze zelfstudie in een productieomgeving gebruikt.

4. Kies **Selecteren** > **Maken** om uw wijzigingen op te slaan.

    Staat uw groep er niet bij? Selecteer **Vernieuwen**.

5. Selecteer **Nieuwe groep** en voer de volgende eigenschappen in:

    - **Groepstype**: Selecteer **Beveiliging**.
    - **Groepsnaam**: Voer **Alle Windows-apparaten** in.
    - **Type lidmaatschap**: Selecteer **Dynamisch apparaat**.
    - **Leden van dynamisch apparaat**: Configureer uw query:

        - **Eigenschap**: Selecteer **deviceOSType**.
        - **Operator**: Selecteer **Is gelijk aan**.
        - **Waarde**: Voer **Windows** in.

        1. Selecteer **Expressie toevoegen**. Uw expressie wordt weergegeven in de **Regelsyntaxis**:

            > [!div class="mx-imgBorder"]
            > ![Een dynamische query maken en een expressie toevoegen in een Microsoft Intune-beheersjabloon](./media/tutorial-walkthrough-administrative-templates/dynamic-group-query.png)

            Wanneer gebruikers of apparaten voldoen aan de criteria die u invoert, worden deze automatisch toegevoegd aan de dynamische groepen. In dit voorbeeld worden apparaten automatisch aan deze groep toegevoegd wanneer het besturingssysteem Windows is. Wees voorzichtig als u deze zelfstudie in een productieomgeving gebruikt. Het doel is te oefenen met het maken van dynamische groepen.

        2. Kies **Opslaan** > **Maken** om uw wijzigingen op te slaan.

6. Maak de groep **Alle docenten** met de volgende instellingen:

    - **Groepstype**: Selecteer **Beveiliging**.
    - **Groepsnaam**: Voer **Alle docenten** in.
    - **Type lidmaatschap**: Selecteer **Dynamische gebruiker**.
    - **Dynamische gebruikersleden**: Configureer uw query:

      - **Eigenschap**: Selecteer **afdeling**.
      - **Operator**: Selecteer **Is gelijk aan**.
      - **Waarde**: Voer **Docenten** in.

        1. Selecteer **Expressie toevoegen**. Uw expressie wordt weergegeven in de **Regelsyntaxis**.

            Wanneer gebruikers of apparaten voldoen aan de criteria die u invoert, worden deze automatisch toegevoegd aan de dynamische groepen. In dit voorbeeld worden gebruikers automatisch aan deze groep toegevoegd wanneer hun afdeling Docenten is. U kunt de afdeling en andere eigenschappen invoeren wanneer gebruikers worden toegevoegd aan uw organisatie. Wees voorzichtig als u deze zelfstudie in een productieomgeving gebruikt. Het doel is te oefenen met het maken van dynamische groepen.

        2. Kies **Opslaan** > **Maken** om uw wijzigingen op te slaan.

### <a name="talking-points"></a>Opmerkingen

- Dynamische groepen zijn een functie in Azure AD Premium. Als u geen Azure AD Premium hebt, kunt u alleen toegewezen groepen maken. Voor meer informatie over dynamische groepen raadpleegt u:

  - [Dynamisch groepslidmaatschap in Azure Active Directory (deel 1)](https://blogs.technet.microsoft.com/pauljones/2017/08/28/dynamic-group-membership-in-azure-active-directory-part-1/)
  - [Dynamisch groepslidmaatschap in Azure Active Directory (deel 2)](https://blogs.technet.microsoft.com/pauljones/2017/08/29/dynamic-group-membership-in-azure-active-directory-part-2/)

- Azure AD Premium bevat andere services die vaak worden gebruikt bij het beheren van apps en apparaten, waaronder [meervoudige verificatie (MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) en [voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).

- Veel beheerders vragen wanneer ze gebruikersgroepen moeten gebruiken en wanneer ze apparaatgroepen moeten gebruiken. Zie [Gebruikersgroepen versus apparaatgroepen](device-profile-assign.md#user-groups-vs-device-groups) voor enkele richtlijnen.

- Zoals u weet kan een gebruiker bij meerdere groepen horen. Overweeg ook om een van de andere dynamische gebruikers- en apparaatgroepen te gebruiken die u kunt maken, zoals:

  - Alle studenten
  - Alle Android-apparaten
  - Alle iOS-/iPadOS-apparaten
  - Marketing
  - Human resources
  - Alle medewerkers in Zaandam
  - Alle werknemers in Redmond
  - IT-beheerders westkust
  - IT-beheerders oostkust

De gebruikers en groepen die zijn gemaakt, kunnen ook worden weergegeven in het [Microsoft 365-beheercentrum](https://admin.microsoft.com), in Azure AD in Azure Portal en in [Microsoft Intune in Azure Portal](https://go.microsoft.com/fwlink/?linkid=2090973). U kunt in al deze gebieden groepen maken en beheren voor uw tenantabonnement. **Als uw doel apparaatbeheer is, gebruikt u het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431)** .

### <a name="review-group-membership"></a>Groepslidmaatschap controleren

1. Selecteer in het Endpoint Manager-beheercentrum **Gebruikers** > selecteer de naam van een bestaande gebruiker.

    > [!div class="mx-imgBorder"]
    > ![Gebruikers selecteren in het Microsoft Endpoint Manager-beheercentrum](./media/tutorial-walkthrough-administrative-templates/select-users-endpoint-manager-admin-center.png)

2. Bekijk enkele van de gegevens die u kunt toevoegen of wijzigen. Bekijk bijvoorbeeld de eigenschappen die u kunt configureren, zoals Functie, Afdeling, Plaats, Kantoorlocatie en meer. U kunt deze eigenschappen in uw dynamische query's gebruiken tijdens het maken van dynamische groepen.
3. Selecteer **Groepen** om het lidmaatschap van deze gebruiker weer te geven. U kunt de gebruiker ook uit een groep verwijderen.
4. Selecteer enkele van de andere opties om meer informatie weer te geven en te zien wat u kunt doen. Bekijk bijvoorbeeld de toegewezen licentie, de apparaten van de gebruiker en meer.

### <a name="what-did-i-just-do"></a>Wat heb ik zojuist gedaan?

In het Endpoint Manager-beheercentrum hebt u nieuwe beveiligingsgroepen gemaakt en bestaande gebruikers en apparaten aan deze groepen toegevoegd. In latere stappen in deze zelfstudie gaan we deze groepen gebruiken.

## <a name="create-a-template-in-intune"></a>Een sjabloon maken in Intune

In deze sectie maken we een beheersjabloon in Intune, bekijken we een aantal instellingen in **Groepsbeleidsbeheer** en vergelijken we dezelfde instelling in Intune. Het doel is om een instelling in groepsbeleid weer te geven en dezelfde instelling in Intune weer te geven.

1. Selecteer in het Endpoint Manager-beheercentrum **Apparaten** > **Configuratieprofielen** > **Profiel maken**.
2. Voer de volgende eigenschappen in:

    - **Naam**: Voer een beschrijvende naam in voor het profiel. Geef uw profielen een naam zodat u ze later eenvoudig kunt identificeren. Voer bijvoorbeeld **Beheersjabloon - Windows 10-studentapparaten** in.
    - **Beschrijving**: Voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
    - **Platform**: Kies **Windows 10 en hoger**.
    - **Profieltype**: Selecteer **Beheersjablonen**.

3. Selecteer **Maken**. Selecteer in de vervolgkeuzelijst **Een categorie selecteren** de optie **Alle producten**. Alle instellingen worden weergegeven. Bekijk de volgende eigenschappen in deze instellingen:

    - Het **Pad** naar het beleid is hetzelfde als dat van groepsbeleidsbeheer of GPEdit.
    - De instelling is van toepassing op gebruikers of apparaten.

### <a name="open-group-policy-management"></a>Groepsbeleidsbeheer openen

In deze sectie wordt beleid in Intune en het overeenkomstige beleid in Groepsbeleidsbeheer-editor weergegeven.

#### <a name="compare-a-device-policy"></a>Apparaatbeleid vergelijken

1. Open op de **Beheercomputer** de app **Groepsbeleidsbeheer**.

    Deze app wordt geïnstalleerd met **RSAT: hulpprogramma's voor groepsbeleidsbeheer**, een optionele functie die u in Windows installeert. Bij [Vereisten](#prerequisites) (in dit artikel) vindt u de stappen om deze functie te installeren.

2. Vouw **Domeinen** uit > selecteer uw domein. Selecteer bijvoorbeeld **contoso.net**.
3. Klik met de rechtermuisknop op het beleid **OfficeandEdge** > **Bewerken**. Hiermee wordt de app Groepsbeleidsbeheer-editor geopend.

    > [!div class="mx-imgBorder"]
    > ![Met de rechtermuisknop op het ADMX-groepsbeleid voor Office en Edge klikken en Bewerken selecteren](./media/tutorial-walkthrough-administrative-templates/open-group-policy-management.png)

    **OfficeandEdge** is groepsbeleid dat de ADMX-sjablonen voor Office en Microsoft Edge bevat. Dit beleid wordt beschreven bij [Vereisten](#prerequisites) (in dit artikel).

4. Vouw **Computerconfiguratie** > **Beleid** > **Beheersjablonen** > **Configuratiescherm** > **Persoonlijke instellingen** uit. Bekijk de beschikbare instellingen.

    > [!div class="mx-imgBorder"]
    > ![Computerconfiguratie uitvouwen in Groepsbeleidsbeheer-editor en naar Persoonlijke instellingen gaan](./media/tutorial-walkthrough-administrative-templates/open-group-policy-management-editor-admx-policy.png)

    Dubbelklik op **Inschakeling camera vanaf vergrendelingsscherm voorkomen** en bekijk de beschikbare opties:

    > [!div class="mx-imgBorder"]
    > ![De opties bekijken voor computerconfiguratie-instellingen in groepsbeleid](./media/tutorial-walkthrough-administrative-templates/prevent-enabling-lock-screen-camera-admx-policy.png)

5. Ga in het beheercentrum voor apparaatbeheer naar uw sjabloon **Beheersjabloon - Windows 10-studentapparaten**.
6. Selecteer **Alle producten** in de vervolgkeuzelijst en zoek naar **Persoonlijke instellingen**:

    > [!div class="mx-imgBorder"]
    > ![Zoeken naar persoonlijke instellingen in de beheersjabloon in Microsoft Intune](./media/tutorial-walkthrough-administrative-templates/search-personalization-administrative-template.png)

    Bekijk de beschikbare instellingen.

    Het instellingstype is **Apparaat** en het pad is **\Control Panel\Personalization**. Dit pad is vergelijkbaar met wat u zojuist hebt gezien in Groepsbeleidsbeheer-editor. Als u de instelling opent, ziet u dezelfde opties **Niet geconfigureerd**, **Ingeschakeld** en **Uitgeschakeld** als u ziet in Groepsbeleidsbeheer-editor.

#### <a name="compare-a-user-policy"></a>Gebruikersbeleid vergelijken

1. Zoek in uw beheersjabloon naar **InPrivate-browsing**. Bekijk het pad en merk op dat de instelling van toepassing is op gebruikers en apparaten.

2. Zoek in **Groepsbeleidsbeheer-editor** de overeenkomstige gebruikers- en apparaatinstellingen:

    - Apparaat: Vouw **Computerconfiguratie** > **Beleid** > **Beheersjablonen** > **Windows-onderdelen** > **Internet Explorer** > **Privacy** > **InPrivate-navigatie uitschakelen** uit.
    - Gebruiker: Vouw **Gebruikersconfiguratie** > **Beleid** > **Beheersjablonen** > **Windows-onderdelen** > **Internet Explorer** > **Privacy** > **InPrivate-navigatie uitschakelen** uit.

    > [!div class="mx-imgBorder"]
    > ![InPrivate-browsing uitschakelen in Internet Explorer met behulp van een ADMX-sjabloon](./media/tutorial-walkthrough-administrative-templates/group-policy-turn-off-inprivate-browsing.png)

> [!TIP]
> Als u het ingebouwde Windows-beleid wilt zien, kunt u ook GPEdit gebruiken (de app **Groepsbeleid bewerken**).

#### <a name="compare-an-edge-policy"></a>Edge-beleid vergelijken

1. Ga in het beheercentrum voor apparaatbeheer naar uw sjabloon **Beheersjabloon - Windows 10-studentapparaten**.
2. Selecteer **Edge versie 77 en hoger** in de vervolgkeuzelijst.
3. Zoeken naar **opstarten**. Bekijk de beschikbare instellingen.
4. Zoek de volgende instellingen in Groepsbeleidsbeheer-editor:

    - Apparaat: Vouw **Computerconfiguratie** > **Beleid** > **Beheersjablonen** > **Microsoft Edge** > **Opstarten, startpagina en nieuwe tabbladpagina** uit.
    - Gebruiker: Vouw **Gebruikersconfiguratie** > **Beleid** > **Beheersjablonen** > **Microsoft Edge** > **Opstarten, startpagina en nieuwe tabbladpagina** uit

### <a name="what-did-i-just-do"></a>Wat heb ik zojuist gedaan?

U hebt een beheersjabloon gemaakt in Intune. We hebben enkele ADMX-instellingen in deze sjabloon bekeken en dezelfde ADMX-instellingen bekeken in groepsbeleidsbeheer.

## <a name="add-settings-to-the-students-admin-template"></a>Instellingen toevoegen aan de beheersjabloon voor studenten

In deze sjabloon configureren we enkele Internet Explorer-instellingen om apparaten te vergrendelen die worden gedeeld door meerdere studenten.

1. Zoek in uw **Beheersjabloon - Windows 10-studentapparaten** naar **InPrivate-navigatie uitschakelen** en selecteer het apparaatbeleid:

    > [!div class="mx-imgBorder"]
    > ![Het apparaatbeleid InPrivate-navigatie uitschakelen in de beheersjabloon in Microsoft Intune](./media/tutorial-walkthrough-administrative-templates/turn-off-inprivate-browsing-administrative-template.png)

2. Bekijk in dit venster de beschrijving en de waarden die u kunt instellen. Deze opties zijn vergelijkbaar met wat u ziet in groepsbeleid.
3. Selecteer **Ingeschakeld** > **OK** om uw wijzigingen op te slaan.
4. Configureer ook de volgende Internet Explorer-instellingen. Zorg ervoor dat u **OK** selecteert om uw wijzigingen op te slaan.

    - **Slepen en neerzetten of kopiëren en plakken van bestanden toestaan**
      - **Type**: Apparaat
      - **Pad**: \Windows Components\Internet Explorer\Internet Control Panel\Security Page\Internet Zone
      - **Waarde**: Uitgeschakeld

    - **Het negeren van certificaatfouten voorkomen**
      - **Type**: Apparaat
      - **Pad**: \Windows Components\Internet Explorer\Internet Control Panel
      - **Waarde**: Ingeschakeld

    - **Het instellen van de startpagina uitschakelen**
      - **Type**: Gebruiker
      - **Pad**: \Windows Components\Internet Explorer
      - **Waarde**: Ingeschakeld
      - **Startpagina**: Voer een URL in, bijvoorbeeld `contoso.com`.

5. Wis uw zoekfilter. Zoals u ziet worden de instellingen die u hebt geconfigureerd bovenaan weergegeven:

    > [!div class="mx-imgBorder"]
    > ![Geconfigureerde instellingen worden bovenaan weergegeven in Microsoft Intune](./media/tutorial-walkthrough-administrative-templates/configured-settings-administrative-template.png)

### <a name="assign-your-template"></a>Uw sjabloon toewijzen

1. Selecteer **Toewijzingen** in uw sjabloon. Mogelijk moet u uw sjabloon sluiten en deze vervolgens selecteren in de lijst **Apparaten - Configuratieprofielen**:

    > [!div class="mx-imgBorder"]
    > ![Selecteer uw beheersjabloonprofiel in de lijst Apparaatconfiguratieprofielen in Microsoft Intune](./media/tutorial-walkthrough-administrative-templates/filter-administrative-template-device-configuration-profiles-list.png)

2. Kies **Groepen selecteren die moeten worden opgenomen**. Er wordt een lijst met bestaande gebruikers en groepen weergegeven.
3. Selecteer de groep **Alle Windows 10-studentapparaten** die u eerder hebt gemaakt > **Selecteren**.

    U kunt groepen toevoegen die leeg zijn als u deze zelfstudie in een productieomgeving gebruikt. Het doel is te oefenen met het toewijzen van uw sjabloon.

4. U moet vervolgens de wijzigingen **Opslaan**.

Zodra het profiel is opgeslagen, wordt op de apparaten toegepast wanneer deze worden ingecheckt bij Intune. Als de apparaten verbonden zijn met internet, kan dit onmiddellijk plaatsvinden. Zie [Hoe lang duurt het voor apparaten een beleidsregel, profiel of app hebben ontvangen nadat deze zijn toegewezen?](device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned) voor meer informatie over vernieuwtijden van beleid.

Sluit uzelf niet uit wanneer u strikt of beperkend beleid en profielen toewijst. U kunt een groep maken die wordt uitgesloten van uw beleid en profielen. Zo hebt u toegang om problemen op te lossen. Bewaak deze groep om te bevestigen dat deze wordt gebruikt zoals bedoeld.

### <a name="what-did-i-just-do"></a>Wat heb ik zojuist gedaan?

In het Endpoint Manager-beheercentrum hebt u een beheersjabloonprofiel voor apparaatconfiguratie gemaakt en dit profiel toegewezen aan een groep die u hebt gemaakt.

## <a name="create-a-onedrive-template"></a>Een OneDrive-sjabloon maken

In deze sectie maakt u een OneDrive-beheersjabloon in Intune om bepaalde instellingen te beheren. Deze specifieke instellingen zijn uitgekozen omdat deze vaak worden gebruikt door organisaties.

1. Maak nog een profiel (**Apparaten** > **Configuratieprofielen** > **Profiel maken**).

2. Voer de volgende eigenschappen in:

    - **Naam**: Voer **Beheersjabloon - OneDrive-beleidsregels die van toepassing zijn op alle Windows 10-gebruikers** in.
    - **Beschrijving**: Voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
    - **Platform**: Kies **Windows 10 en hoger**.
    - **Profieltype**: Selecteer **Beheersjablonen**.

3. Selecteer **Maken**.
4. Selecteer **Office** in de vervolgkeuzelijst.
5. Kies **Inschakelen** voor de volgende instellingen. Zorg ervoor dat u **OK** selecteert om uw wijzigingen op te slaan.

    - **Gebruikers op de achtergrond aanmelden bij de OneDrive-synchronisatieclient met hun Windows-referenties**
    - **OneDrive-bestanden op aanvraag gebruiken**
    - **Voorkomen dat gebruikers persoonlijke OneDrive-accounts synchroniseren**

Uw instellingen zien er ongeveer uit zoals de volgende:

> [!div class="mx-imgBorder"]
> ![Een OneDrive-beheersjabloon maken in Microsoft Intune](./media/tutorial-walkthrough-administrative-templates/one-drive-administrative-template.png)

Zie [Groepsbeleid gebruiken voor het beheren van instellingen voor OneDrive-synchronisatieclients](https://docs.microsoft.com/onedrive/use-group-policy) voor meer informatie over OneDrive-clientinstellingen.

### <a name="assign-your-template"></a>Uw sjabloon toewijzen

1. Selecteer **Toewijzingen** in uw sjabloon.
2. Kies **Groepen selecteren die moeten worden opgenomen**. Er wordt een lijst met bestaande gebruikers en groepen weergegeven.
3. Selecteer de groep **Alle Windows-apparaten** die u eerder hebt gemaakt > **Selecteren**.

    U kunt groepen toevoegen die leeg zijn als u deze zelfstudie in een productieomgeving gebruikt. Het doel is te oefenen met het toewijzen van uw sjabloon.

4. U moet vervolgens de wijzigingen **Opslaan**.

Op dit moment hebt u enkele beheersjablonen gemaakt en deze toegewezen aan groepen die u hebt gemaakt. De volgende stap is het maken van een beheersjabloon met behulp van Windows PowerShell en de Microsoft Graph API voor Intune.

## <a name="optional-create-a-policy-using-powershell-and-graph-api"></a>Optioneel: Beleid maken met behulp van PowerShell en de Graph API

In de sectie worden de volgende resources gebruikt. We gaan deze resources in deze sectie installeren.

- [Intune PowerShell SDK](https://github.com/microsoft/Intune-PowerShell-SDK)
- [Microsoft Graph API voor Intune](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0)

1. Open op de **Beheercomputer** de optie **Windows PowerShell** als administrator:

    1. Voer op de zoekbalk **powershell** in.
    2. Klik met de rechtermuisknop op **Windows PowerShell** > **Als administrator uitvoeren**.

    > [!div class="mx-imgBorder"]
    > ![Windows PowerShell starten als administrator](./media/tutorial-walkthrough-administrative-templates/run-windows-powershell-administrator.png)

2. Haal het uitvoeringsbeleid op en stel het in.

    1. Voer in: `get-ExecutionPolicy`

        Schrijf op waarop het is ingesteld. Mogelijk is dat **Beperkt**. Wanneer u klaar bent met de zelfstudie, stelt u het weer in op de oorspronkelijke waarde.

    2. Voer in: `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`

    3. Voer `Y` in om het te wijzigen.

    Het uitvoeringsbeleid van PowerShell helpt te voorkomen dat schadelijke scripts worden uitgevoerd. Zie [Over uitvoeringsbeleid](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies) voor meer informatie.

3. Voer in: `Install-Module -Name Microsoft.Graph.Intune`

    Voer `Y` in als:

    - Er wordt gevraagd om de NuGet-provider te installeren
    - Er wordt gevraagd om de modules van een niet-vertrouwde opslagplaats te installeren

    Dit kan enkele minuten duren. Als dit is gebeurd, wordt een prompt weergegeven die vergelijkbaar is met de volgende prompt:

    > [!div class="mx-imgBorder"]
    > ![Windows PowerShell-prompt na installatie van een module](./media/tutorial-walkthrough-administrative-templates/powershell-prompt.png)

4. Ga in uw webbrowser naar [https://github.com/Microsoft/Intune-PowerShell-SDK/releases](https://github.com/Microsoft/Intune-PowerShell-SDK/releases) en selecteer het bestand **Intune-PowerShell-SDK_v6.1907.00921.0001.zip**.

    1. Selecteer **Opslaan als** en selecteer een map die u gemakkelijk kunt onthouden. `c:\psscripts` is een goede keuze.
    2. Open uw map, klik met de rechtermuisknop op het ZIP-bestand > **Alles uitpakken** > **Uitpakken**. Uw mapstructuur ziet er ongeveer als volgt uit:

        > [!div class="mx-imgBorder"]
        > ![Mapstructuur van de Intune PowerShell SDK na uitpakken](./media/tutorial-walkthrough-administrative-templates/psscripts-directory.png)

5. Schakel op het tabblad **Weergave** de optie **Bestandsnaamextensies** in:

    > [!div class="mx-imgBorder"]
    > ![Bestandsnaamextensies selecteren op het tabblad Weergave in Verkenner](./media/tutorial-walkthrough-administrative-templates/file-names-extension.png)

6. Ga in uw map naar `c:\psscripts\Intune-PowerShell-SDK_v6.1907.00921.0001\drop\outputs\build\Release\net471`. Klik met de rechtermuisknop op elk DLL-bestand > **Eigenschappen** > **Deblokkeren**.

    > [!div class="mx-imgBorder"]
    > ![De DLL-bestanden deblokkeren](./media/tutorial-walkthrough-administrative-templates/unblock-dll.png)

7. Voer in uw app **Windows PowerShell** het volgende in:

    ```powershell
    Import-Module c:\psscripts\Intune-PowerShell-SDK_v6.1907.00921.0001\drop\outputs\build\Release\net471\Microsoft.Graph.Intune.psd1
    ```

    Voer `R` in als u wordt gevraagd om uit te voeren van de niet-vertrouwde uitgever.

8. Intune-beheersjablonen maken gebruik van de bètaversie van Graph:

    1. Voer in: `Update-MSGraphEnvironment -SchemaVersion 'beta'`

    2. Voer in: `Connect-MSGraph -AdminConsent`

    3. Meld u aan met hetzelfde Microsoft 365-beheerdersaccount als dat wordt gevraagd. Met deze cmdlets wordt het beleid in uw tenantorganisatie gemaakt.

        **Gebruiker**: Voer het beheerdersaccount van uw Microsoft 365-tenantabonnement in.  
        **Wachtwoord**: Voer het wachtwoord in.

    4. Selecteer **Accepteren**.

9. Maak het configuratieprofiel **Testconfiguratie**. Voer het volgende in:

    ```powershell
    $configuration = Invoke-MSGraphRequest -Url https://graph.microsoft.com/beta/deviceManagement/groupPolicyConfigurations -Content '{"displayName":"Test Configuration","description":"A test configuration created through PS"}' -HttpMethod POST
    ```

    Als deze cmdlets goed zijn uitgevoerd wordt het profiel gemaakt. Controleer dit door te gaan naar Endpoint Manager-beheercentrum > **Configuratieprofielen**. Uw profiel **Testconfiguratie** moet worden weergegeven.

10. Alle SettingDefinitions ophalen. Voer het volgende in:

    ```powershell
    $settingDefinitions = Invoke-MSGraphRequest -Url https://graph.microsoft.com/beta/deviceManagement/groupPolicyDefinitions -HttpMethod GET
    ```

11. Zoek de definitie-id met behulp van de weergavenaam van de instelling. Voer het volgende in:

    ```powershell
    $desiredSettingDefinition = $settingDefinitions.value | ? {$_.DisplayName -Match "Silently sign in users to the OneDrive sync client with their Windows credentials"}
    ```

12. Configureer een instelling. Voer het volgende in:

    ```powershell
    $configuredSetting = Invoke-MSGraphRequest -Url "https://graph.microsoft.com/beta/deviceManagement/groupPolicyConfigurations('$($configuration.id)')/definitionValues" -Content ("{""enabled"":""true"",""configurationType"":""policy"",""definition@odata.bind"":""https://graph.microsoft.com/beta/deviceManagement/groupPolicyDefinitions('$($desiredSettingDefinition.id)')""}") -HttpMethod POST
    ```

    ```powershell
    Invoke-MSGraphRequest -Url "https://graph.microsoft.com/beta/deviceManagement/groupPolicyConfigurations('$($configuration.id)')/definitionValues('$($configuredSetting.id)')" -Content ("{""enabled"":""false""}") -HttpMethod PATCH
    ```

    ```powershell
    $configuredSetting = Invoke-MSGraphRequest -Url "https://graph.microsoft.com/beta/deviceManagement/groupPolicyConfigurations('$($configuration.id)')/definitionValues('$($configuredSetting.id)')" -HttpMethod GET
    ```

### <a name="see-your-policy"></a>Uw beleid bekijken

1. Kies in Endpoint Manager-beheercentrum > **Configuratieprofielen** > **Vernieuwen**.
2. Selecteer uw profiel **Testconfiguratie** > **Instellingen**.
3. Selecteer **Alle producten** in de vervolgkeuzelijst.

U kunt zien dat de instelling **Gebruikers op de achtergrond aanmelden bij de OneDrive-synchronisatieclient met hun Windows-referenties** is geconfigureerd.

## <a name="policy-best-practices"></a>Aanbevolen procedures voor beleid

Voor het maken van beleidsregels en profielen in Intune zijn er enkele aanbevelingen en aanbevolen procedures die u kunt overwegen. Zie [Aanbevolen procedures voor beleid en profielen](device-profile-create.md#recommendations) voor meer informatie.

## <a name="clean-up-resources"></a>Resources opschonen

Wanneer u deze niet meer nodig hebt, kunt u het volgende doen:

- Verwijder de groepen die u hebt gemaakt:

  - **Alle Windows 10-studentapparaten**
  - **Alle Windows-apparaten**
  - **Alle docenten**

- Verwijder de beheersjablonen die u hebt gemaakt:

  - **Beheersjabloon - Windows 10-studentapparaten**
  - **Beheersjabloon - OneDrive-beleidsregels die van toepassing zijn op alle Windows 10-gebruikers**
  - **Testconfiguratie**

- Herstel de oorspronkelijke waarde van het Windows PowerShell-uitvoeringsbeleid. In het volgende voorbeeld wordt het uitvoeringsbeleid ingesteld op Beperkt:

  ```powershell
  Set-ExecutionPolicy -ExecutionPolicy Restricted
  ```

## <a name="next-steps"></a>Volgende stappen

In deze zelfstudie bent u meer vertrouwd geraakt met het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431), hebt u de opbouwfunctie voor query's gebruikt om dynamische groepen te maken en hebt u beheersjablonen in Intune gemaakt om [ADMX-instellingen](https://docs.microsoft.com/windows/client-management/mdm/understanding-admx-backed-policies) te configureren. U hebt ook het gebruik van ADMX-sjablonen on-premises en in de cloud met Intune vergeleken. Als bonus hebt u PowerShell-cmdlets gebruikt om een beheersjabloon te maken.

Voor meer informatie over beheersjablonen in Intune raadpleegt u:

> [!div class="nextstepaction"]
> [Windows 10-sjablonen gebruiken voor het configureren van instellingen voor groepsbeleid in Intune](administrative-templates-windows.md)
