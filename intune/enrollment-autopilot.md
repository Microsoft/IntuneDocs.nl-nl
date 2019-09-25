---
title: Apparaten inschrijven met Windows Autopilot
titleSuffix: Microsoft Intune
description: Informatie over het inschrijven van Windows 10-apparaten met Windows Autopilot.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a2dc5594-a373-48dc-ba3d-27aff0c3f944
ms.reviewer: spshumwa
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 301945f96b62dce9ee1cf6caedf40fe6b03499e3
ms.sourcegitcommit: 1494ff4b33c13a87f20e0f3315da79a3567db96e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/20/2019
ms.locfileid: "71166442"
---
# <a name="enroll-windows-devices-in-intune-by-using-the-windows-autopilot"></a>Windows-apparaten in Intune inschrijven met Windows Autopilot  
Windows Autopilot maakt het makkelijker om apparaten te registreren in Intune. Het kost veel tijd om aangepaste installatiekopieën van besturingssystemen te bouwen en onderhouden. Mogelijk besteedt u ook tijd aan het toepassen van deze aangepaste installatiekopieën op nieuwe apparaten, om ze voor te bereiden voor gebruik voordat u ze aan eindgebruikers verstrekt. Met Microsoft Intune en Autopilot geeft u nieuwe apparaten aan uw eindgebruikers zonder dat u aangepaste installatiekopieën van besturingssystemen voor de apparaten hoeft te bouwen, onderhouden en toe te passen. Als u Intune gebruikt om Autopilot-apparaten te beheren, kunt u beleidsregels, profielen, apps en meer beheren op apparaten nadat ze zijn ingeschreven. Zie [Overzicht van Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot) voor een overzicht van voordelen, scenario's en vereisten.

Er zijn vier typen Autopilot-implementatie:
- [De modus voor zelf implementeren](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying), voor kiosken, digitale borden of een gedeeld apparaat
- [White label](https://docs.microsoft.com/windows/deployment/windows-autopilot/white-glove), waarmee partners of IT-medewerkers een Windows 10-pc alvast kunnen inrichten, zodat deze volledig is geconfigureerd en klaar is voor gebruik -[Autopilot voor bestaande apparaten](https://docs.microsoft.com/windows/deployment/windows-autopilot/existing-devices), waarmee u gemakkelijk de meest recente versie van Windows 10 op uw bestaande apparaten kunt implementeren
- [Door gebruiker gestuurde modus](https://docs.microsoft.com/windows/deployment/windows-autopilot/user-driven), voor traditionele gebruikers. 


## <a name="prerequisites"></a>Vereisten
- [Intune-abonnement](licenses.md)
- [Automatische inschrijving bij Windows is ingeschakeld](windows-enroll.md#enable-windows-10-automatic-enrollment)
- [Azure Active Directory Premium-abonnement](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->

## <a name="how-to-get-the-csv-for-import-in-intune"></a>Het CSV-bestand verkrijgen voor het importeren in Intune

Raadpleeg voor meer informatie 'De PowerShell-cmdlet begrijpen'.

- [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)

## <a name="add-devices"></a>Apparaten toevoegen

U kunt Windows Autopilot-apparaten toevoegen door een CSV-bestand te importeren met de bijbehorende informatie.

1. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) de optie **Apparaatinschrijving** > **Windows-inschrijving** > **Apparaten** > **Importeren**.

    ![Schermafbeelding van Windows Autopilot-apparaten](media/enrollment-autopilot/autopilot-import-device.png)

2. Onder **Windows AutoPilot-apparaten toevoegen** bladert u naar het CSV-bestand met de apparaten die u wilt toevoegen. Het CSV-bestand moet de serienummers, Windows-product-id's, hardwarehashes, optionele groepstags en optionele toegewezen gebruiker vermelden. Er mogen maximaal 500 rijen in de lijst staan. Gebruik de header- en regelindeling die hieronder wordt weergegeven:

    `Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User`</br>
    `<serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>`

    ![Schermafbeelding van het toevoegen van Windows Autopilot-apparaten](media/enrollment-autopilot/autopilot-import-device2.png)

    >[!IMPORTANT]
    > Wanneer u CSV-upload gebruikt om een gebruiker toe te wijzen, moet u ervoor zorgen dat u geldige UPN's toewijst. Als u een ongeldige UPN (onjuiste gebruikersnaam) toewijst, is uw apparaat mogelijk ontoegankelijk totdat u de ongeldige toewijzing verwijdert. Tijdens het uploaden van de CSV controleren we alleen of de domeinnaam geldig is in de kolom **Toegewezen gebruiker**. We kunnen geen afzonderlijke UPN-validatie uitvoeren om te controleren of u een bestaande of juiste gebruiker toewijst.

3. Kies **Importeren** om apparaatgegevens te importeren. Het importeren kan enkele minuten duren.

4. Wanneer het importeren is voltooid, kiest u **Apparaatinschrijving** > **Windows-inschrijving** > **Windows Autopilot** > **Apparaten** > **Synchroniseren**. Er wordt een bericht weergegeven dat de synchronisatie wordt uitgevoerd. Het proces kan enige minuten duren, afhankelijk van hoeveel apparaten er worden gesynchroniseerd.

5. Vernieuw de weergave om de nieuwe apparaten te zien.

## <a name="create-an-autopilot-device-group"></a>Een Autopilot-apparaatgroep maken

1. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) de optie **Groepen** > **Nieuwe groep**.
2. Op de blade **Groep**:
    1. Als **groepstype** kiest u **Beveiliging**.
    2. Geef een **groepsnaam** en een **beschrijving** voor de groep op.
    3. Als **lidmaatschapstype** kiest u **Toegewezen** of **Dynamisch apparaat**.
3. Als u in de vorige stap voor **Toegewezen** hebt gekozen als **lidmaatschapstype**, kiest u op de blade **Groep** de optie **Leden** en voegt u Autopilot-apparaten toe aan de groep.
    Autopilot-apparaten die nog niet zijn ingeschreven, zijn apparaten waarvan de naam overeenkomt met het serienummer van het apparaat.
4. Als u hierboven de optie **Dynamische apparaten** hebt gekozen als **lidmaatschapstype**, kiest u op de blade **Groep** de optie **Leden van dynamisch apparaat** en typt u een de volgende codes in het vak **Geavanceerde regel**. Alleen Autopilot-apparaten worden door deze regels verzameld, omdat ze doelkenmerken hebben die alleen zijn gelden voor Autopilot-apparaten.
    - Als u een groep wilt maken met al uw Autopilot-apparaten, typt u: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
    - Het veld met groepstags van Intune komt overeen met het kenmerk OrderID op Azure AD-apparaten. Als u een groep wilt maken met al uw Autopilot-apparaten met een specifieke groepstag (de OrderID voor Azure AD-apparaten), typt u: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
    - Als u een groep wilt maken met al uw Autopilot-apparaten en een specifieke inkooporder-id, typt u `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`
    
    Wanneer u de code **Geavanceerde regel** hebt toegevoegd, kiest u **Opslaan**.
5. Kies **Maken**.  

## <a name="create-an-autopilot-deployment-profile"></a>Een Autopilot-implementatieprofiel maken
Autopilot-profielen worden gebruikt om de Autopilot-apparaten te configureren.
1. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) de optie **Apparaatinschrijving** > **Windows-inschrijving** > **Apparaatprofielen** > **Profiel maken**.
2. Geef op de pagina **Basisinformatie** een waarde op voor **Naam** en eventueel ook voor **Beschrijving**.

    ![Schermopname van de pagina Basisinformatie](media/enrollment-autopilot/create-profile-basics.png)

3. Als u wilt dat alle apparaten in de toegewezen groepen automatisch converteren naar Autopilot, stelt u **Alle doelapparaten converteren naar Autopilot** in op **Ja**. Alle niet-Autopilot-apparaten in toegewezen groepen worden geregistreerd met de Autopilot-implementatieservice. Het kan 48 uur duren voordat de registratie is verwerkt. Wanneer het apparaat wordt uitgeschreven en opnieuw wordt ingesteld, wordt het door Autopilot geregistreerd. Nadat een apparaat op deze manier is geregistreerd, wordt het apparaat niet meer uit de Autopilot-implementatieservice verwijderd door deze optie uit te schakelen of de profieltoewijzing te verwijderen. In plaats daarvan moet u [het apparaat rechtstreeks verwijderen](enrollment-autopilot.md#delete-autopilot-devices).
4. Selecteer **Volgende**.
5. Ga op de pagina **Out-Of-Box Experience (OOBE)** naar **Implementatiemodus** en kies een van deze twee opties:
    - **Op basis van gebruiker**: Apparaten met dit profiel worden gekoppeld aan de gebruiker die het apparaat inschrijft. Er zijn gebruikersreferenties vereist om het apparaat in te kunnen schrijven.
    - **Zelf-implementerend (preview)** : (Windows 10 versie 1809 of hoger vereist) apparaten met dit profiel worden niet gekoppeld aan de gebruiker die het apparaat inschrijft. Er zijn geen gebruikersreferenties vereist om het apparaat te kunnen registreren. Wanneer er geen gebruiker aan een apparaat is gekoppeld, is op het apparaat geen nalevingsbeleid op basis van gebruikers van toepassing. Wanneer u de modus voor zelf-implementatie gebruikt, wordt alleen nalevingsbeleid toegepast dat op het apparaat is gericht.

    ![Schermopname van de OOBE-pagina](media/enrollment-autopilot/create-profile-outofbox.png)

6. In het vak **Toevoegen aan Azure AD als** kiest u **Toegevoegd aan Azure AD**.
7. Configureer de volgende opties:
    - **Gebruiksrechtovereenkomst (EULA)** : (Windows 10, versie 1709 of hoger) Kies of u de gebruiksrechtovereenkomst wilt weergeven aan gebruikers.
    - **Privacyinstellingen**: kies of u de privacyinstellingen wilt weergeven voor de gebruikers.
    >[!IMPORTANT]
    >De standaardwaarde voor de instelling Diagnostische gegevens is afhankelijk van de Windows-versie. Voor apparaten met Windows 10 versie 1903 is de standaardwaarde tijdens de Out-Of-Box Experience ingesteld op Volledig. Zie [Windows Diagnostic Data](https://docs.microsoft.com/windows/privacy/windows-diagnostic-data) (Diagnostische gegevens in Windows) voor meer informatie <br>
    
    - **Opties voor account wijzigen verbergen (Windows 10 versie 1809 of hoger vereist)** : kies **Verbergen** om te voorkomen dat opties voor account wijzigen worden weergegeven op de aanmeldings- en domeinfoutpagina's van het bedrijf. Voor deze optie is vereist dat er een [aangepaste huisstijl wordt geconfigureerd in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/customize-branding).
    - **Gebruikersaccounttype**: kies het gebruikersaccounttype (**Beheerder** of **Standaardgebruiker**).
    - **White Glove OOBE toestaan** (Windows 10, versie 1903 of hoger vereist; [aanvullende fysieke vereisten](https://docs.microsoft.com/windows/deployment/windows-autopilot/white-glove#prerequisites)): Kies **Ja** om ondersteuning van nauwkeurige OOBE toe te staan.
    - **Sjabloon apparaatnaam toepassen (Windows 10 versie 1809 of hoger vereist)** : kies **Ja** om een sjabloon te maken die tijdens de inschrijving kan worden gebruikt bij de naamgeving van een apparaat. Namen moeten 15 tekens of minder bevatten, en mogen letters, cijfers en afbreekstreepjes bevatten. Namen mogen niet alleen uit getallen bestaan. Gebruik de [%SERIAL% macro](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) om het serienummer toe te voegen van specifieke hardware. U kunt ook de optie [% RAND: x % macro](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) gebruiken om een willekeurige tekenreeks van getallen toe te voegen, waarbij x gelijk is aan het aantal toe te voegen cijfers. 
    - **Taal (regio)** \*: Kies de taal die u voor het apparaat wilt gebruiken. Deze optie is alleen beschikbaar als u **Zelf-implementerend** hebt gekozen als **implementatiemodus**.
    - **Toetsenbord automatisch configureren**\*: Als er een **Taal (regio)** is geselecteerd, kiest u **Ja** om de toetsenbordselectiepagina over te slaan. Deze optie is alleen beschikbaar als u **Zelf-implementerend** hebt gekozen als **implementatiemodus**.
8. Selecteer **Volgende**.
9. Voeg op de pagina **Bereiktags** eventueel de bereiktags toe die u wilt toepassen op dit profiel. Zie [Use role-based access control and scope tags for distributed IT](scope-tags.md) (Op rollen gebaseerd toegangsbeheer en bereiktags gebruiken voor gedistribueerde IT) voor meer informatie over bereiktags.
10. Selecteer **Volgende**.
11. Kies op de pagina **Toewijzingen** de optie **Selecteerde groepen** bij **Toewijzen aan**.

    ![Schermopname van pagina Toewijzingen](media/enrollment-autopilot/create-profile-assignments.png)

12. Kies **Groepen selecteren om op te nemen** en kies de groepen die u wilt opnemen in dit profiel.
13. Als u groepen wilt uitsluiten, kiest u **Groepen selecteren die moeten worden uitgesloten** en kiest u vervolgens de groepen die u wilt uitsluiten.
14. Selecteer **Volgende**.
15. Kies op de pagina **Beoordelen en maken** de optie **Maken** om het profiel te maken.

    ![Schermopname van de pagina Beoordelen en maken](media/enrollment-autopilot/create-profile-review.png)

> [!NOTE]
> Er wordt regelmatig door Intune gecontroleerd of de toegewezen groepen nieuwe apparaten bevatten. Vervolgens worden er profielen aan eventuele nieuwe apparaten toegewezen. Dit proces kan enkele minuten duren. Zorg ervoor dat dit proces is voltooid voordat u een apparaat implementeert.  U kunt bij **Apparaatinschrijving** > **Windows-inschrijving** > **Apparaten** controleren waar u de wijzigingen in de profielstatus van 'Niet-toegewezen' naar 'Toewijzen' en tot slot naar 'Toegewezen' kunt bekijken.

## <a name="edit-an-autopilot-deployment-profile"></a>Een Windows Autopilot-implementatieprofiel bewerken
Nadat u een Autopilot-implementatieprofiel hebt gemaakt, kunt u bepaalde delen ervan bewerken.   

1. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) de optie **Apparaatinschrijving**.
2. Onder **Windows-inschrijving** in het gedeelte **Windows Autopilot** kiest u **Implementatieprofielen**.
3. Selecteer het profiel dat u wilt bewerken.
4. Klik links op **Eigenschappen** om de naam of beschrijving van het implementatieprofiel te wijzigen. Klik op **Opslaan** wanneer u klaar bent met het aanbrengen van wijzigingen.
5. Klik op **Instellingen** de OOBE-instellingen te wijzigen. Klik op **Opslaan** wanneer u klaar bent met het aanbrengen van wijzigingen.

> [!NOTE]
> Wijzigingen aan het profiel worden toegepast op apparaten die zijn toegewezen aan dit profiel. Het bijgewerkte profiel wordt echter niet toegepast op een apparaat dat al is ingeschreven bij Intune totdat het apparaat opnieuw is ingesteld en ingeschreven.

## <a name="alerts-for-windows-autopilot-unassigned-devices-----163236---"></a>Waarschuwingen voor niet-toegewezen Windows Autopilot-apparaten  <!-- 163236 -->  

Waarschuwingen geven weer hoeveel Autopilot-programma-apparaten geen Autopilot-implementatieprofielen hebben. Aan de hand van de informatie in de waarschuwing kunt u profielen maken en deze toewijzen aan de niet-toegewezen apparaten. Als u op de waarschuwing klikt, verschijnt een volledige lijst met Windows Autopilot-apparaten en gedetailleerde informatie.


Als u waarschuwingen over niet-toegewezen apparaten wilt zien, kiest u in [Intune in Azure Portal](https://aka.ms/intuneportal) de optie **Apparaatinschrijving** > **Overzicht** > **Niet-toegewezen apparaten**.  


## <a name="assign-a-user-to-a-specific-autopilot-device"></a>Een gebruiker toewijzen aan een specifiek Autopilot-apparaat

U kunt een gebruiker toewijzen aan een specifiek Autopilot-apparaat. Deze toewijzing wordt vooraf ingevuld voor een gebruiker uit Azure Active Directory op de aanmeldingspagina in de [huisstijl van het bedrijf](https://docs.microsoft.com/azure/active-directory/fundamentals/customize-branding) tijdens de installatie van Windows. Ook kunt u de naam van een aangepast welkomstbericht instellen. Hiermee wordt Windows-aanmelding niet vooraf ingevuld of gewijzigd. Alleen gelicentieerde gebruikers van Intune kunnen op deze manier worden toegewezen.

Vereisten: de Azure Active Directory-bedrijfsportal is geconfigureerd en Windows 10 versie 1809 of hoger is geïnstalleerd.

1. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) de optie **Apparaatinschrijving** > **Windows-inschrijving** > **Apparaten** > kies het apparaat > **Gebruiker toewijzen**.

    ![Schermafbeelding van Gebruiker toewijzen](media/enrollment-autopilot/assign-user.png)

2. Kies een Azure-gebruiker met een licentie voor het gebruik van Intune en kies **Selecteren**.

    ![Schermafbeelding van Gebruiker selecteren](media/enrollment-autopilot/select-user.png)

3. Typ in het vak **beschrijvende naam van gebruiker** een beschrijvende naam of accepteer de standaardwaarde. Deze tekenreeks is de beschrijvende naam die wordt weergegeven wanneer de gebruiker zich aanmeldt tijdens de installatie van Windows.

    ![Schermafbeelding van beschrijvende naam](media/enrollment-autopilot/friendly-name.png)

4. Kies **OK**.


## <a name="delete-autopilot-devices"></a>Autopilot-apparaten verwijderen

U kunt Windows Autopilot-apparaten verwijderen die niet bij Intune zijn ingeschreven:

- Verwijder de apparaten uit Windows Autopilot via **Apparaatinschrijving** > **Windows-inschrijving** > **Apparaten**. Kies de apparaten die u wilt verwijderen en kies vervolgens **Verwijderen**. Het verwijderen van Windows Autopilot-apparaten kan enkele minuten duren.

Als u een apparaat volledig uit uw tenant wilt verwijderen, moet u alle records van het Intune-apparaat, het Azure Active Directory-apparaat en de Windows Autopilot-apparaat verwijderen. Dit kan allemaal vanuit Intune worden geregeld:

1. Als de apparaten zijn ingeschreven bij Intune, moet u ze eerst [verwijderen uit de Intune-blade Alle apparaten](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).

2. Verwijder de apparaten in Azure Active Directory-apparaten via **Apparaten** > **Azure AD-apparaten**.

3. Verwijder de apparaten uit Windows Autopilot via **Apparaatinschrijving** > **Windows-inschrijving** > **Apparaten**. Kies de apparaten die u wilt verwijderen en kies vervolgens **Verwijderen**. Het verwijderen van Windows Autopilot-apparaten kan enkele minuten duren.

## <a name="using-autopilot-in-other-portals"></a>Autopilot in andere portals gebruiken
Als u geen interesse hebt in Mobile Device Management, kunt u Autopilot gebruiken in andere portals. Hoewel het gebruik van andere portals een optie is, raden we aan om alleen Intune te gebruiken voor uw Autopilot-implementaties. Wanneer u Intune en een andere portal gebruikt, kunt u met Intune het volgende niet doen:  

- Wijzigingen weergeven in profielen die zijn gemaakt in Intune, maar bewerkt in een andere portal
- Profielen synchroniseren die zijn gemaakt in een andere portal
- Wijzigingen in profieltoewijzingen weergeven die zijn aangebracht in een andere portal
- Profieltoewijzingen synchroniseren die zijn uitgevoerd in een andere portal
- Wijzigingen in de lijst met apparaten weergeven die zijn gemaakt in een andere portal

## <a name="windows-autopilot-for-existing-devices"></a>Windows Autopilot voor bestaande apparaten

U kunt Windows-apparaten groeperen op correlator-id bij registratie met behulp van [Autopilot voor bestaande apparaten](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) via Configuration Manager. De correlator-ID is een parameter van het Autopilot-configuratiebestand. De [enrollmentProfileName van het Azure ID-apparaatkenmerk](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices) wordt automatisch zodanig ingesteld dat deze aansluit bij de ‘OfflineAutopilotprofile-\<correlator-ID\>’. Hierdoor kunnen willekeurige dynamische groepen in Azure AD op basis van de correlator-id worden gemaakt met behulp van het kenmerk enrollmentprofileName.

>[!WARNING] 
> Omdat de correlatie-id niet vooraf wordt weergegeven in Intune, wordt door het apparaat mogelijk elke gewenste correlatie-id gerapporteerd. Als de gebruiker een correlatie-id maakt die overeenkomt met een Autopilot- of Apple DEP-profielnnaam, wordt het apparaat toegevoegd aan alle dynamische Microsoft Azure AD-apparaatgroepen op basis van het kenmerk enrollmentProfileName. U kunt dit conflict als volgt voorkomen:
> - Maak altijd dynamische groepsregels die overeenkomen met de *hele* enrollmentProfileName-waarde
> - Begin een Autopilot- of Apple DEP-profielnaam nooit met 'OfflineAutopilotprofile-'.

## <a name="next-steps"></a>Volgende stappen
Ontdek hoe u apparaten beheert nadat u Windows Autopilot hebt geconfigureerd voor geregistreerde Windows 10-apparaten. Zie [Wat is Microsoft Intune-apparaatbeheer?](device-management.md) voor meer informatie.
