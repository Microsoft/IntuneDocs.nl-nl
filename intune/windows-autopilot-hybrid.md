---
title: Registratie voor aan Hybrid AD gekoppelde apparaten met behulp van Windows Autopilot
titleSuffix: ''
description: Gebruik Windows Autopilot om aan Hybrid AD gekoppelde apparaten in Microsoft Intune te registreren.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/01/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 81e50c3f79ffe9a3b9bc8068d49ba966c35dbbfd
ms.sourcegitcommit: 1b7ee2164ac9490df4efa83c5479344622c181b5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/08/2019
ms.locfileid: "67649089"
---
# <a name="deploy-hybrid-azure-ad-joined-devices-by-using-intune-and-windows-autopilot"></a>Apparaten die aan hybride Azure AD zijn gekoppeld implementeren met Intune en Windows Autopilot
U kunt Intune en Windows Autopilot gebruiken om apparaten in te stellen die zijn gekoppeld aan Hybrid Azure Active Directory (Azure AD). Volg hiervoor de stappen in dit artikel.

## <a name="prerequisites"></a>Vereisten

Configureer uw [gekoppelde Hybrid Azure AD-apparaten](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan). Zorg ervoor dat u [de registratie van uw apparaat verifieert](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#verify-the-registration) met behulp van de cmdlet Get-MsolDevice.

De te registreren apparaten moeten ook voldoen aan de volgende voorwaarden:
- Apparaten werken met Windows 10 v1809 of hoger.
- Toegang hebben tot internet [op basis van de gedocumenteerde Windows Autopilot-netwerkvereisten](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements#networking-requirements).
- Toegang tot een Active Directory-domeincontroller, zodat het kan worden verbonden met het netwerk van de organisatie. (Waar het DNS-records voor het AD-domein en de AD-domeincontroller kan oplossen en kan communiceren met de domeincontroller om de gebruiker te verifiëren. Een VPN-verbinding wordt momenteel niet ondersteund.)
- Zorg ervoor dat u de domeincontroller van het domein dat u probeert samen te voegen kunt pingen.
- Als u een proxy gebruikt, moet de optie WPAD Proxy-instellingen zijn ingeschakeld en geconfigureerd.
- Doorloop de OOBE (Out-of-Box Experience).

## <a name="set-up-windows-10-automatic-enrollment"></a>Automatische inschrijving voor Windows 10 instellen

1. Meld u aan bij [Azure Portal](https://portal.azure.com) en selecteer **Azure Active Directory** in het linkerdeelvenster.

   ![Azure Portal](./media/auto-enroll-azure-main.png)

1. Selecteer **Mobiliteit (MDM en MAM)** .

   ![Het deelvenster Azure Active Directory](./media/auto-enroll-mdm.png)

1. Selecteer **Microsoft Intune**.

   ![Het deelvenster Mobiliteit (MDM en MAM)](./media/auto-enroll-intune.png)

1. Zorg ervoor dat de gebruikers die aan Azure AD gekoppelde apparaten implementeren met Intune en Windows, lid zijn van een groep die is opgenomen zijn in uw **Gebruikersbereik van MDM**.

   ![Het deelvenster Mobiliteit (MDM en MAM) configureren](./media/auto-enroll-scope.png)

1. Gebruik de standaardwaarden in de vakken **URL naar MDM-gebruiksvoorwaarden**, **Detectie-URL MDM** en **Nalevings-URL MDM** en selecteer vervolgens **Opslaan**.

## <a name="increase-the-computer-account-limit-in-the-organizational-unit"></a>De limiet verhogen voor het aantal computeraccounts in de organisatie-eenheid

Met de Intune-connector voor uw Active Directory worden via Autopilot geregistreerde computers gemaakt in het on-premises Active Directory-domein. De computer die als host fungeert voor de Intune-connector moet over het recht beschikken om binnen het domein computerobjecten te maken. 

In sommige domeinen worden aan computers geen rechten verleend voor het maken van computers. Bovendien hebben domeinen een ingebouwde limiet (standaard 10) die geldt voor alle gebruikers en computers zonder gedelegeerde rechten voor het maken van computerobjecten. De rechten moeten daarom worden gedelegeerd aan computers die als host fungeren voor de Intune-connector van de organisatie-eenheid waarop aan Hybrid Azure AD gekoppelde apparaten worden gemaakt.

De organisatie-eenheid waaraan het recht is verleend om computers te maken, moet overeenkomen met:
- De organisatie-eenheid die is ingevoerd in het profiel Domeindeelname.
- Als er geen profiel is geselecteerd, de domeinnaam van de computer voor uw domein.

1. Open **Active Directory: gebruikers en computers (DSA.msc)** .

1. Klik met de rechtermuisknop op de organisatie-eenheid die u gebruikt om aan Hybrid Azure AD gekoppelde computers te maken en selecteer **Beheer delegeren**.

    ![De opdracht Beheer delegeren](media/windows-autopilot-hybrid/delegate-control.png)

1. Kies in de wizard **Overdracht van beheer** **Volgende** > **Toevoegen** > **Objecttypen**.

1. In het deelvenster **Objecttypen** schakelt u het selectievakje **Computers** in en selecteert u **OK**.

    ![Het deelvenster Objecttypen](media/windows-autopilot-hybrid/object-types-computers.png)

1. Voer in het deelvenster **Gebruikers, computers of groepen selecteren** in het veld **Te selecteren objectnamen invoeren** de naam in van de computer waarop de connector is geïnstalleerd.

    ![Het deelvenster Gebruikers, computers of groepen selecteren](media/windows-autopilot-hybrid/enter-object-names.png)

1. Selecteer **Namen controleren** om uw invoer te valideren en selecteer **OK** en selecteer vervolgens **Volgende**.

1. Selecteer **Een aangepaste taak maken om te delegeren** > **Volgende**.

1. Selecteer het selectievakje **Alleen de volgende objecten in de map** en schakel vervolgens de selectievakjes **Computerobjecten**, **Geselecteerde objecten in deze map maken** en **Geselecteerde objecten in deze map verwijderen** in.

    ![Het deelvenster Active Directory-objecttype](media/windows-autopilot-hybrid/only-following-objects.png)
    
1. Selecteer **Volgende**.

1. Onder **Machtigingen** schakelt u het selectievakje **Volledige bevoegdheid** in.  
    Met deze actie selecteert u alle andere opties.

    ![Het deelvenster Machtigingen](media/windows-autopilot-hybrid/full-control.png)

1. Selecteer **Volgende** en selecteer vervolgens **Voltooien**.

## <a name="install-the-intune-connector"></a>De Intune-connector installeren

De Intune-connector voor Active Directory moet worden geïnstalleerd op een computer waarop Windows Server 2016 of later wordt uitgevoerd. De computer moet ook toegang hebben tot internet en uw Active Directory. Als u de schaal en beschikbaarheid wilt verhogen of meerdere Active Directory-domeinen wilt ondersteunen, kunt u in uw omgeving meerdere connectors installeren. Het is raadzaam om de connector te installeren op een server waarop geen andere Intune-connectors worden uitgevoerd.

1. Zorg ervoor dat u een taalpakket hebt geïnstalleerd en geconfigureerd zoals staat beschreven in [Taalvereisten voor de Intune-connector (preview)](https://docs.microsoft.com/windows/deployment/windows-autopilot/intune-connector).
2. Selecteer [Intune](https://aka.ms/intuneportal) **Apparaatregistratie** > **Windows-registratie** > **Intune-connector voor Active Directory (preview-versie)**  > **Connector toevoegen**. 
3. Volg de instructies voor het downloaden van de connector.
4. Open het gedownloade installatiebestand *ODJConnectorBootstrapper.exe* voor de connector om deze te installeren.
5. Aan het einde van de installatie selecteert u **Configureren**.
6. Selecteer **Aanmelden.**
7. Voer de referenties in voor de rol gebruiker, globale beheerder of Intune-beheerder.  
   Aan het gebruikersaccount moet een Intune-licentie zijn toegewezen.
8. Ga naar **Apparaatregistratie** > **Windows-registratie** > **Intune-connector voor Active Directory (preview)** en controleer of de status **Actief** is.

> [!NOTE]
> Nadat u zich bij de Connector hebt aangemeld, kan het een aantal minuten duren voordat deze in [Intune](https://aka.ms/intuneportal) wordt weergegeven. De connector wordt alleen weergegeven als deze met de Intune-service kan communiceren.

### <a name="turn-off-ie-enhanced-security-configuration"></a>Verbeterde beveiliging van Internet Explorer uitschakelen
De functie Verbeterde beveiliging van Internet Explorer is standaard ingeschakeld in Windows Server. Als u zich niet kunt aanmelden bij de Intune-connector voor Active Directory, schakelt u de functie Verbeterde beveiliging van Internet Explorer uit voor de beheerder. [Verbeterde beveiliging van Internet Explorer uitschakelen](https://blogs.technet.microsoft.com/chenley/2011/03/10/how-to-turn-off-internet-explorer-enhanced-security-configuration)

### <a name="configure-web-proxy-settings"></a>Webproxyinstellingen configureren

Als u in uw netwerkomgeving over een webproxy beschikt, zorgt u ervoor dat de Intune-connector voor Active Directory goed werkt door te verwijzen naar [Werken met bestaande on-premises proxyservers](autopilot-hybrid-connector-proxy.md).


## <a name="create-a-device-group"></a>Een apparaatgroep maken
1. In [Intune](https://aka.ms/intuneportal) selecteert u **Groepen** > **Nieuwe groep**.

1. In het deelvenster **Groep** doet u het volgende:

    a. Selecteer bij **Groepstype** de optie **Beveiliging**.

    b. Geef een **groepsnaam** en een **beschrijving** voor de groep op.

    c. Selecteer een **Type lidmaatschap**.

1. Als u **Dynamische apparaten** hebt geselecteerd voor het lidmaatschapstype, selecteert u in het deelvenster **Groep** de optie **Leden van dynamisch apparaat** en voert u in het vak **Geavanceerde regel** een van de volgende acties uit:
    - Als u een groep wilt maken met al uw Autopilot-apparaten, voert u `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")` in.
    - Het veld Groepstag van Intune komt overeen met het kenmerk OrderID op Azure AD-apparaten. Als u een groep wilt maken met al uw Autopilot-apparaten met een specifieke groepstag (OrderID), typt u: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
    - Als u een groep wilt maken met al uw Autopilot-apparaten en een specifieke inkooporder-id, voert u `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")` in.
    
1. Selecteer **Opslaan**.

1. Selecteer **Maken**.  

## <a name="register-your-autopilot-devices"></a>De Autopilot-apparaten registreren

Selecteer een van de volgende manieren om uw Autopilot-apparaten te registreren.

### <a name="register-autopilot-devices-that-are-already-enrolled"></a>Autopilot-apparaten registreren die al zijn geregistreerd

1. Maak een Autopilot-implementatieprofiel waarin **Alle doelapparaten converteren naar Apparaat** is ingesteld op **Ja**. 
2. Wijs het profiel toe aan een groep met de leden waarvan u wilt dat deze automatisch worden geregistreerd met Autopilot.

Zie [Een Autopilot-implementatieprofiel maken](enrollment-autopilot.md#create-an-autopilot-deployment-profile) voor meer informatie.

### <a name="register-autopilot-devices-that-arent-enrolled"></a>Autopilot-apparaten registreren die niet bij Intune zijn geregistreerd

Als uw apparaten nog niet bij Intune zijn geregistreerd, kunt u ze zelf registreren. Zie [Apparaten toevoegen](enrollment-autopilot.md#add-devices) voor meer informatie.

### <a name="register-devices-from-an-oem"></a>OEM-apparaten registreren

Als u nieuwe apparaten koopt, kunnen sommige OEM's de apparaten voor u registreren. Raadpleeg de [pagina Windows Autopilot](https://aka.ms/WindowsAutopilot) voor meer informatie.

Wanneer uw Autopilot-apparaten worden *geregistreerd*, voordat ze worden geregistreerd bij Intune, worden ze op drie locaties weergegeven (met namen die zijn ingesteld op de serienummers):
- Het deelvenster **Autopilot-apparaten** in Azure Portal in Intune. Selecteer **Apparaatregistratie** > **Windows-registratie** > **Apparaten**.
- Het deelvenster **Azure AD-apparaten** in Azure Portal in Intune. Selecteer **Apparaten** > **Azure AD-apparaten**.
- Het deelvenster **Alle Azure AD-apparaten** in Azure Active Directory in Azure Portal door **Apparaten** > **Alle apparaten** te selecteren.

Nadat uw Autopilot-apparaten zijn *geregistreerd*, worden deze op vier locaties weergegeven:
- Het deelvenster **Autopilot-apparaten** in Azure Portal in Intune. Selecteer **Apparaatregistratie** > **Windows-registratie** > **Apparaten**.
- Het deelvenster **Azure AD-apparaten** in Azure Portal in Intune. Selecteer **Apparaten** > **Azure AD-apparaten**.
- Het deelvenster **Alle Azure AD-apparaten** in Azure Active Directory in Azure Portal. Selecteer **Apparaten** > **Alle apparaten**.
- Het deelvenster **Alle apparaten** in Azure Portal in Intune. Selecteer **Apparaten** > **Alle apparaten**.

Nadat uw Autopilot-apparaten zijn geregistreerd, worden hun namen de hostnaam van het apparaat. De hostnaam begint standaard met *DESKTOP-* .


## <a name="create-and-assign-an-autopilot-deployment-profile"></a>Een Windows AutoPilot-implementatieprofiel maken en toewijzen
Autopilot-profielen worden gebruikt om de Autopilot-apparaten te configureren.

1. Selecteer in [Intune](https://aka.ms/intuneportal) de optie **Apparaatregistratie** > **Windows-registratie** > **Apparaatprofielen** > **Profiel maken**.
1. Typ een **naam** en (optioneel) een **beschrijving**.
1. Als **implementatiemodus** selecteert u **Op basis van gebruiker**.
1. Selecteer in het vak **Toevoegen aan Azure AD als** de optie **Gekoppeld aan Hybrid Azure AD (preview)** .
1. Selecteer **Out-Of-Box Experience (OOBE)** , configureer de gewenste opties en selecteer vervolgens **Opslaan**.
1. Selecteer **Maken** om het profiel te maken. 
1. In het profieldeelvenster selecteert u **Toewijzingen**.
1. Selecteer **Groepen selecteren**.
1. In het deelvenster **Groepen selecteren** selecteert u de apparaatgroep. Klik vervolgens op **Selecteren**.

Het duurt ongeveer 15 minuten voordat de status van het apparaatprofiel is gewijzigd van *Niet toegewezen* in *Toewijzen* en tot slot in *Toegewezen*.

## <a name="optional-turn-on-the-enrollment-status-page"></a>(Optioneel) De pagina Status van de registratie inschakelen

1. Selecteer in [Intune](https://aka.ms/intuneportal) **Apparaatinschrijving** > **Windows-inschrijving** > **Pagina Status van de inschrijving**.
1. In het deelvenster **Pagina Registratiestatus** selecteert u **Standaard** > **Instellingen**.
1. In het vak **Voortgang app- en profielinstallatie weergeven** selecteert u **Ja**.
1. Configureer de andere opties indien nodig.
1. Selecteer **Opslaan**.

## <a name="create-and-assign-a-domain-join-profile"></a>Een profiel voor Domeindeelname maken en toewijzen

1. Selecteer in [Intune](https://aka.ms/intuneportal) **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
1. Voer de volgende eigenschappen in:
   - **Naam**: Voer een beschrijvende naam in voor het nieuwe profiel.
   - **Beschrijving**: Voer een beschrijving in voor het profiel.
   - **Platform**: Kies **Windows 10 en hoger**.
   - **Profieltype**: Selecteer **Domeindeelname (preview)** .
1. Selecteer **Instellingen** en geef vervolgens een **computernaamvoorvoegsel**, **domeinnaam** en (optioneel) **organisatie-eenheid** in [DN-indeling](https://docs.microsoft.com/windows/desktop/ad/object-names-and-identities#distinguished-name) op. 
1. Selecteer **OK** > **Maken**.  
    Het profiel wordt gemaakt en weergegeven in de lijst.
1. Als u het profiel wilt toewijzen, volgt u de stappen onder [Een apparaatprofiel toewijzen](device-profile-assign.md#assign-a-device-profile) en wijst u het profiel toe aan dezelfde groep die u bij de stap [Een apparaatgroep maken](windows-autopilot-hybrid.md#create-a-device-group) hebt gebruikt
   - Meerdere Domeindeelname-profielen implementeren
   
     a. Maak een dynamische groep waarin al uw Autopilot-apparaten met een specifiek Autopilot-implementatieprofiel staan en voer (device.enrollmentProfileName, bijv. 'Autopilot-profielnaam') in. 
     
     b. Vervang 'Naam Autopilot-profiel' door de weergavenaam van het profiel dat u onder [Een Autopilot-implementatieprofiel maken en toewijzen](windows-autopilot-hybrid.md#create-and-assign-an-autopilot-deployment-profile) hebt gemaakt. 
     
     c. Maak meerdere Autopilot-implementatieprofielen en wijs dat apparaat toe aan het profiel dat in deze dynamische groep is opgegeven.

> [!NOTE]
> De naamgevingsmogelijkheden voor Windows Autopilot voor Hybrid Azure AD Join bieden geen ondersteuning voor variabelen zoals %SERIAL% en ondersteunen alleen voorvoegsels voor de computernaam.

## <a name="next-steps"></a>Volgende stappen

Ontdek hoe u apparaten beheert nadat u Windows Autopilot hebt geconfigureerd. Zie [Wat is Microsoft Intune-apparaatbeheer?](device-management.md) voor meer informatie.
