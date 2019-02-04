---
title: Registratie voor aan Hybrid Active Directory gekoppelde apparaten met behulp van Windows Autopilot
titleSuffix: ''
description: Gebruik Windows Autopilot om aan Hybrid Active Directory gekoppelde apparaten in Microsoft Intune te registreren.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: 171e994be67a24e351b242967c8af934272da356
ms.sourcegitcommit: 17f58d35a6bdff3e179662f3731fc74d39144470
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/28/2019
ms.locfileid: "55105167"
---
# <a name="deploy-hybrid-azure-ad-joined-devices-using-intune-and-windows-autopilot-preview"></a>Apparaten die zijn gekoppeld aan Hybrid Azure Active Directory implementeren met Intune en Windows Autopilot (preview)
U kunt Intune en Windows Autopilot gebruiken om apparaten in te stellen die zijn gekoppeld aan Hybrid Azure Active Directory. Volg hiertoe de onderstaande stappen.

## <a name="prerequisites"></a>Vereisten

- Configureer [aan Hybrid Azure Active Directory gekoppelde apparaten](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan).
    - Zorg ervoor dat u [de registratie verifieert met behulp van de cmdlet Get-MsolDevice]( https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#verify-the-registration).

De te registreren apparaten moeten ook voldoen aan de volgende voorwaarden:
- Er moet Windows 10 met de [update van oktober 2018](https://blogs.windows.com/windowsexperience/2018/10/02/how-to-get-the-windows-10-october-2018-update/) op worden uitgevoerd.
- Ze moeten toegang hebben tot internet.
- Ze moeten toegang hebben tot uw Active Directory (VPN-verbinding wordt niet ondersteund).
- Ze moeten de OOBE (Out-of-Box Experience) doorlopen.

## <a name="set-up-windows-10-automatic-enrollment"></a>Automatische inschrijving voor Windows 10 instellen

1. Meld u aan bij de [Azure-portal](https://portal.azure.com) en selecteer **Azure Active Directory**.

   ![Schermopname van de Azure-portal](./media/auto-enroll-azure-main.png)

2. Selecteer **Mobiliteit (MDM en MAM)**.

   ![Schermopname van de Azure-portal](./media/auto-enroll-mdm.png)

3. Selecteer **Microsoft Intune**.

   ![Schermopname van de Azure-portal](./media/auto-enroll-intune.png)

4. Zorg ervoor dat de gebruikers die aan Azure Active Directory gekoppelde apparaten implementeren met Intune en Windows, lid zijn van een groep die is opgenomen zijn in uw **Gebruikersbereik van MDM**.

   ![Schermopname van de Azure-portal](./media/auto-enroll-scope.png)

5. Gebruik de standaardwaarden voor de volgende URL's:
    - **URL voor MDM-gebruiksvoorwaarden**
    - **Detectie-URL voor MDM**
    - **URL van MDM-naleving**
6. Kies **Opslaan**.

## <a name="increase-the-computer-account-limit-in-the-organizational-unit"></a>De limiet verhogen voor het aantal computeraccounts in de organisatie-eenheid

Met de Intune-connector voor Active Directory worden via Autopilot geregistreerde computers gemaakt in het on-premises Active Directory-domein. De computer die als host fungeert voor de Intune-connector moet over het recht beschikken om binnen het domein computerobjecten te maken. 

In sommige domeinen worden aan computers geen rechten verleend voor het maken van computers. Bovendien hebben domeinen een ingebouwde limiet (standaard 10) die geldt voor alle gebruikers en computers zonder gedelegeerde rechten voor het maken van computerobjecten. De rechten moeten daarom worden gedelegeerd aan computers die als host fungeren voor de Intune-connector van de organisatie-eenheid waarop aan Hybrid Azure AD gekoppelde apparaten worden gemaakt.

De organisatie-eenheid waaraan het recht is verleend om computers te maken, moet overeenkomen met:
- de organisatie-eenheid die is ingevoerd in het profiel Domeindeelname
- of, als er geen profiel is geselecteerd, de domeinnaam van de computer voor uw domein.

1. Open **Active Directory: gebruikers en computers** (DSA.msc).

2. Klik met de rechtermuisknop op de organisatie-eenheid die u gebruikt om aan Hybrid Azure AD gekoppelde computers te maken > **Beheer delegeren**.

    ![Schermopname van beheer delegeren](media/windows-autopilot-hybrid/delegate-control.png)

3. Kies in de wizard **Overdracht van beheer** **Volgende** > **Toevoegen...**  > **Objecttypen**.

4. Schakel in het dialoogvenster **Objecttypen** de optie **Computers** in en kies vervolgens **OK**.

    ![Schermopname van beheer delegeren](media/windows-autopilot-hybrid/object-types-computers.png)

5. Voer in het dialoogvenster **Gebruikers, computers of groepen selecteren** in het veld **Te selecteren objectnamen invoeren** de naam in van de computer waarop de connector is geïnstalleerd.

    ![Schermopname van beheer delegeren](media/windows-autopilot-hybrid/enter-object-names.png)

6. Kies **Namen controleren** om uw invoer te valideren en kies vervolgens **OK** > **Volgende**.

7. Kies **Een aangepaste taak maken om te delegeren** > **Volgende**.

8. Kies **Alleen de volgende objecten in de map** en controleer vervolgens de volgende opties:
    - **Computerobjecten**
    - **Geselecteerde objecten in deze map maken**
    - **Geselecteerde objecten uit deze map verwijderen**

    ![Schermopname van beheer delegeren](media/windows-autopilot-hybrid/only-following-objects.png)
    
9. Kies **Volgende**.

10. Schakel onder **Machtigingen** de optie **Volledig beheer** in (hiermee worden alle andere opties ingeschakeld) > **Volgende** > **Voltooien**.

    ![Schermopname van beheer delegeren](media/windows-autopilot-hybrid/full-control.png)

## <a name="install-the-intune-connector"></a>De Intune-connector installeren

De Intune-connector voor Active Directory moet worden geïnstalleerd op een computer met Windows Server 2016 (of hoger) die toegang heeft tot internet en uw Active Directory. Als u de schaal en beschikbaarheid wilt verhogen of meerdere Active Directory-domeinen wilt ondersteunen, kunt u in uw omgeving meerdere connectors installeren. Het is raadzaam om de connector te installeren op een server waarop geen andere Intune-connectors worden uitgevoerd.

1. Zorg ervoor dat u een taalpakket hebt geïnstalleerd en geconfigureerd zoals staat beschreven in [Taalvereisten voor de Intune-connector (preview)](https://docs.microsoft.com/windows/deployment/windows-autopilot/intune-connector).
2. Kies in [Intune](https://aka.ms/intuneportal) **Apparaatinschrijving** > **Windows-inschrijving** > **Intune-connector voor Active Directory (preview-versie)** > **Connector toevoegen**. 
3. Volg de instructies voor het downloaden van de connector.
4. Open het gedownloade setup-bestand voor de connector om deze te installeren (ODJConnectorBootstrapper.exe).
5. Kies aan het einde van de installatie **Configureren**.
6. Kies **Aanmelden**.
7. Voer referenties in voor de rol gebruiker, globale beheerder of Intune-beheerder. Aan het gebruikersaccount moet een Intune-licentie zijn toegewezen.
8. Ga naar **Apparaatregistratie** > **Windows-registratie** > **Intune-connector voor Active Directory (preview)** en controleer of de status **Actief** is.

 > [!NOTE]
 > Nadat u bent **aangemeld** in de connector, duurt het een paar minuten duren voordat de connector in [Intune](https://aka.ms/intuneportal) wordt weergegeven. De connector wordt alleen weergegeven als deze met de Intune-service kan communiceren.

### <a name="configure-web-proxy-settings"></a>Webproxyinstellingen configureren

Als u in uw netwerkomgeving over een webproxy beschikt, volgt u deze instructies om ervoor te zorgen dat de Intune-connector voor Active Directory goed werkt: [Werken met bestaande on-premises proxyservers](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-configure-connectors-with-proxy-servers).


## <a name="create-a-device-group"></a>Een apparaatgroep maken
1. Kies in [Intune](https://aka.ms/intuneportal) **Groepen** > **Nieuwe groep**.
2. Op de blade **Groep**:
    1. Als **groepstype** kiest u **Beveiliging**.
    2. Geef een **groepsnaam** en een **beschrijving** voor de groep op.
    3. Kies een **Type lidmaatschap**.
3. Als u hierboven de optie **Dynamische apparaten** hebt gekozen als **lidmaatschapstype**, kiest u op de blade **Groep** de optie **Leden van dynamisch apparaat** en typt u een de volgende codes in het vak **Geavanceerde regel**.
    - Als u een groep wilt maken met al uw Autopilot-apparaten, typt u `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
    - Als u een groep wilt maken met al uw Autopilot-apparaten en een specifieke bestellings-id, typt u `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881") `
    - Als u een groep wilt maken met al uw Autopilot-apparaten en een specifieke inkooporder-id, typt u `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`
    
    Wanneer u de code **Geavanceerde regel** hebt toegevoegd, kiest u **Opslaan**.
5. Kies **Maken**.  

## <a name="register-your-autopilot-devices"></a>De Autopilot-apparaten registreren

Kies een van de volgende manieren om uw Autopilot-apparaten te registreren:

### <a name="register-autopilot-devices-that-are-already-enrolled"></a>Autopilot-apparaten registreren die al zijn geregistreerd

1. Maak een Autopilot-implementatieprofiel waarin **Alle doelapparaten converteren naar Apparaat** is ingesteld op **Ja**. 
2. Wijs het profiel toe aan een groep met de leden waarvan u wilt dat deze automatisch worden geregistreerd met Autopilot.

Zie [Een Autopilot-implementatieprofiel maken](enrollment-autopilot.md#create-an-autopilot-deployment-profile) voor meer informatie.

### <a name="register-autopilot-devices-that-arent-enrolled"></a>Autopilot-apparaten registreren die niet bij Intune zijn geregistreerd

Als uw apparaten nog niet bij Intune zijn geregistreerd, kunt u ze zelf registreren. Zie [Apparaten toevoegen](enrollment-autopilot.md#add-devices) voor meer informatie.

### <a name="register-devices-from-an-oem"></a>OEM-apparaten registreren

Als u nieuwe apparaten koopt, kunnen sommige OEM's de apparaten voor u registreren. Raadpleeg de [pagina Windows Autopilot](http://aka.ms/WindowsAutopilot) voor meer informatie.

Wanneer Autopilot-apparaten worden geregistreerd (en voordat ze worden geregistreerd bij Intune), ziet u deze op drie locaties (met namen die zijn ingesteld op de serienummers):
- De blade AutoPilot-apparaten in Intune in Azure Portal (**Apparaatregistratie** > **Windows-registratie** > **Apparaten**).
- De blade Azure AD-apparaten in Intune in Azure Portal (**Apparaten** > **Azure AD-apparaten**).
- De blade Alle AAD-apparaten in Azure Active Directory in Azure Portal (**Apparaten** > **Alle apparaten**).

Nadat Autopilot-apparaten zijn geregistreerd, ziet u deze op vier plaatsen:
- De blade AutoPilot-apparaten in Intune in Azure Portal (**Apparaatregistratie** > **Windows-registratie** > **Apparaten**).
- De blade Azure AD-apparaten in Intune in Azure Portal (**Apparaten** > **Azure AD-apparaten**).
- De blade Alle AAD-apparaten in Azure Active Directory in Azure Portal (**Apparaten** > **Alle apparaten**).
- De blade Alle apparaten in Intune in Azure Portal (**Apparaten** > **Alle apparaten**).

Nadat Autopilot-apparaten bij Intune zijn geregistreerd, wordt de apparaatnaam gewijzigd in de hostnaam van het apparaat. Standaard begint deze met 'DESKTOP-'.




## <a name="create-and-assign-an-autopilot-deployment-profile"></a>Een Windows AutoPilot-implementatieprofiel maken en toewijzen
Autopilot-profielen worden gebruikt om de Autopilot-apparaten te configureren.

1. Kies in [Intune](https://aka.ms/intuneportal) de optie **Apparaatinschrijving** > **Windows-inschrijving** > **Apparaatprofielen** > **Profiel maken**.
2. Geef een **naam** en desgewenst een **beschrijving** op.
3. Als **implementatiemodus** kiest u **Op basis van gebruiker**.
4. Kies in het vak **Toevoegen aan Azure AD als** de optie **Gekoppeld aan Hybrid Azure AD (preview)**.
5. Kies **Out-Of-Box Experience (OOBE)**, configureer de gewenste opties en klik vervolgens op **Opslaan**.
6. Kies op **Maken** om het profiel te maken. 
7. Op de profielblade kiest u **Toewijzingen**.
8. Kies **Groepen selecteren** > in de blade **Groepen selecteren**, kies de apparaatgroep > **Selecteren**.

Het duurt ongeveer 15 minuten voordat de status van het apparaatprofiel is gewijzigd van **Niet toegewezen** in **Toewijzen** en tot slot in **Toegewezen**.

## <a name="turn-on-the-enrollment-status-page-optional"></a>De pagina Status van de registratie inschakelen (optioneel)

1. In [Intune](https://aka.ms/intuneportal) kiest u **Apparaatinschrijving** > **Windows-inschrijving** > **Pagina Status van de inschrijving (preview)**.
2. In de blade **Pagina Status van de inschrijving** kiest u **Standaard** > **Instellingen**.
3. Bij **Voortgang van installatie van app en profiel weergeven** kiest u **Ja**.
4. Configureer de andere opties indien nodig.
5. Kies **Opslaan**.

## <a name="create-and-assign-a-domain-join-profile"></a>Een profiel voor Domeindeelname maken en toewijzen

1. Kies in [Intune](https://aka.ms/intuneportal) **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
2. Voer de volgende eigenschappen in:
   - **Naam**: Voer een beschrijvende naam in voor het nieuwe profiel.
   - **Beschrijving**: Voer een beschrijving in voor het profiel.
   - **Platform**: Kies **Windows 10 en hoger**.
   - **Profieltype**: Kies **Domeindeelname (preview)**.
3. Kies **Instellingen** en geef een **computernaamvoorvoegsel**, **domeinnaam** en (optioneel) **organisatie-eenheid** in [DN-indeling](https://docs.microsoft.com/windows/desktop/ad/object-names-and-identities#distinguished-name) op. 
4. Kies **OK** > **Maken**. Het profiel wordt gemaakt en wordt weergegeven in de lijst.
5. Als u het profiel wilt toewijzen, volgt u de stappen onder [Een apparaatprofiel toewijzen](device-profile-assign.md#assign-a-device-profile). 

## <a name="next-steps"></a>Volgende stappen

Ontdek hoe u apparaten beheert nadat u Windows Autopilot hebt geconfigureerd. Zie [Wat is Microsoft Intune-apparaatbeheer?](device-management.md) voor meer informatie.
