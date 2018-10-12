---
title: Apparaten inschrijven met Windows AutoPilot
titleSuffix: Microsoft Intune
description: Informatie over het inschrijven van Windows 10-apparaten met Windows AutoPilot.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a2dc5594-a373-48dc-ba3d-27aff0c3f944
ms.openlocfilehash: a640e6d914da6fead7a64d5235c1cdeac164ac9e
ms.sourcegitcommit: 7c70c3e0fcae7c4fa8c9e108aafb1cebb366332d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/07/2018
ms.locfileid: "44096534"
---
# <a name="enroll-windows-devices-by-using-the-windows-autopilot"></a>Windows-apparaten inschrijven met Windows AutoPilot
Windows AutoPilot vereenvoudigt het inrichten van apparaten. Het kost veel tijd om aangepaste installatiekopieën van besturingssystemen te bouwen en onderhouden. Mogelijk besteedt u ook tijd aan het toepassen van deze aangepaste installatiekopieën op nieuwe apparaten, om ze voor te bereiden voor gebruik voordat u ze aan eindgebruikers verstrekt. Met Microsoft Intune en AutoPilot kunt u nieuwe apparaten aan uw eindgebruikers geven zonder dat u aangepaste installatiekopieën van besturingssystemen voor de apparaten hoeft te bouwen, onderhouden en toe te passen. Als u Intune gebruikt om AutoPilot-apparaten te beheren, kunt u beleidsregels, profielen, apps en meer beheren op apparaten nadat ze zijn ingeschreven. Zie [Overzicht van Windows AutoPilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot) voor een overzicht van voordelen, scenario’s en vereisten.

## <a name="prerequisites"></a>Vereisten
- [Automatische inschrijving bij Windows is ingeschakeld](https://docs.microsoft.com/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune#enable-windows-10-automatic-enrollment)
- [Azure Active Directory Premium-abonnement](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->

## <a name="add-devices"></a>Apparaten toevoegen

U kunt Windows AutoPilot-apparaten toevoegen door een CSV-bestand te importeren met de bijbehorende informatie.

1. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) de optie **Apparaatinschrijving** > **Windows-inschrijving** > **Apparaten** > **Importeren**.

    ![Schermafbeelding van Windows AutoPilot-apparaten](media/enrollment-autopilot/autopilot-import-device.png)

2. Onder **Windows AutoPilot-apparaten toevoegen** bladert u naar het CSV-bestand met de apparaten die u wilt toevoegen. Het bestand moet de serienummers, Windows-product-id's, hardwarehashes en optionele bestellings-id's van de apparaten bevatten.

    ![Schermafbeelding van het toevoegen van Windows AutoPilot-apparaten](media/enrollment-autopilot/autopilot-import-device2.png)

3. Kies **Importeren** om apparaatgegevens te importeren. Het importeren kan enkele minuten duren.

4. Wanneer het importeren is voltooid, kiest u **Apparaatinschrijving** > **Windows-inschrijving** > **Windows AutoPilot** > **Apparaten** > **Synchroniseren**. Er wordt een bericht weergegeven dat de synchronisatie wordt uitgevoerd. Het proces kan enige minuten duren, afhankelijk van hoeveel apparaten er worden gesynchroniseerd.

5. Vernieuw de weergave om de nieuwe apparaten te zien.

## <a name="create-an-autopilot-device-group"></a>Een AutoPilot-apparaatgroep maken

1. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) de optie **Groepen**.
2. Op de blade **Groep**:
    1. Als **groepstype** kiest u **Beveiliging**.
    2. Geef een **groepsnaam** en een **beschrijving** voor de groep op.
    3. Als **lidmaatschapstype** kiest u **Toegewezen** of **Dynamisch apparaat**.
3. Als u in de vorige stap voor **Toegewezen** hebt gekozen als **lidmaatschapstype**, kiest u op de blade **Groep** de optie **Leden** en voegt u AutoPilot-apparaten toe aan de groep.
    AutoPilot-apparaten die nog niet zijn ingeschreven, zijn apparaten waarvan de naam overeenkomt met het serienummer van het apparaat.
4. Als u hierboven de optie **Dynamische apparaten** hebt gekozen als **lidmaatschapstype**, kiest u op de blade **Groep** de optie **Leden van dynamisch apparaat** en typt u een de volgende codes in het vak **Geavanceerde regel**.
    - Als u een groep wilt maken met al uw AutoPilot-apparaten, typt u `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
    - Als u een groep wilt maken met al uw AutoPilot-apparaten en een specifieke bestellings-id, typt u `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881") `
    - Als u een groep wilt maken met al uw AutoPilot-apparaten en een specifieke inkooporder-id, typt u `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`
    
    Wanneer u de code **Geavanceerde regel** hebt toegevoegd, kiest u **Opslaan**.
5. Kies **Maken**.



## <a name="create-an-autopilot-deployment-profile"></a>Een Windows AutoPilot Deployment-profiel maken
AutoPilot-profielen worden gebruikt om de AutoPilot-apparaten te configureren.
1. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) de optie **Apparaatinschrijving** > **Windows-inschrijving** > **Apparaatprofielen** > **Profiel maken**.
2. Geef een **naam** en desgewenst een **beschrijving** op.
3. Voor de **implementatiemodus** kiest u een van deze twee opties:
    - **Op basis van gebruiker**: apparaten met dit profiel worden gekoppeld aan de gebruiker die het apparaat inschrijft. Er zijn gebruikersreferenties vereist om het apparaat te kunnen inrichten.
    - **Zelf-implementerend (preview)**: (hiervoor is de meest recente versie van [Windows 10 Insider Preview Build](https://docs.microsoft.com/windows-insider/at-work-pro/) vereist) apparaten met dit profiel worden niet gekoppeld aan de gebruiker die het apparaat inschrijft. Er zijn gebruikersreferenties vereist om het apparaat te kunnen inrichten.
4. In het vak **Toevoegen aan Azure AD als** kiest u **Toegevoegd aan Azure AD**.
5. Kies **Out-Of-Box Experience (OOBE)**, configureer de volgende opties en klik vervolgens op **Opslaan**:
    - **Taal (regio)***: kies de taal die u voor het apparaat wilt gebruiken. Deze optie is alleen beschikbaar als u **Zelf-implementerend** hebt gekozen als **implementatiemodus**.
    - **Toetsenbord automatisch configureren***: als er een **taal (regio)** is geselecteerd,kiest u **Ja** en slaat u de toetsenbordselectiepagina over. Deze optie is alleen beschikbaar als u **Zelf-implementerend** hebt gekozen als **implementatiemodus**.
    - **Gebruiksrechtovereenkomst (EULA)**: (Windows 10, versie 1709 of nieuwer) kies of u de gebruiksrechtovereenkomst wilt weergeven voor gebruikers.
    - **Privacy-instellingen**: kies of u de privacyinstellingen wilt weergeven voor de gebruikers.
    - **Opties voor account wijzigen verbergen (alleen Windows Insider)**: kies **Verbergen** om te voorkomen dat opties voor account wijzigen worden weergegeven op de aanmeld- en domeinfoutpagina's van het bedrijf. Voor deze optie is vereist dat er een [aangepaste huisstijl wordt geconfigureerd in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/customize-branding).
    - **Gebruikersaccounttype**: kies of het gebruikersaccounttype **Beheerder** of **Standaard**gebruiker is.
    - **Sjabloon computernaam toepassen (alleen Windows Insider)**: kies **Ja** om een sjabloon te maken dat kan worden gebruikt bij het benoemen van een apparaat tijdens de inrichting. Namen moeten 15 tekens of minder bevatten, en mogen letters, cijfers en afbreekstreepjes bevatten. Namen mogen niet alleen uit getallen bestaan. Gebruik de [%SERIAL% macro](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) om het serienummer toe te voegen van specifieke hardware. U kunt ook de optie [% RAND: x % macro](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) gebruiken om een willekeurige tekenreeks van getallen toe te voegen, waarbij x gelijk is aan het aantal toe te voegen cijfers. 

6. Kies op **Maken** om het profiel te maken. Het AutoPilot-implementatieprofiel is nu klaar om te worden toegewezen aan apparaten.

*Zowel **Taal (Regio)** als **Toetsenbord automatisch configureren** zijn alleen beschikbaar als u **Zelf-implementerend (preview)** hebt gekozen als **implementatiemodus** (hiervoor is de meest recente versie van [Windows 10 Insider Preview Build ](https://docs.microsoft.com/windows-insider/at-work-pro/) vereist).


## <a name="assign-an-autopilot-deployment-profile-to-a-device-group"></a>Een AutoPilot-implementatieprofiel toewijzen aan een apparaatgroep

1. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) de optie **Apparaatinschrijving** > **Windows-inschrijving** > **Apparaatprofielen** > kies een profiel.
2. Op de specifieke profielblade kiest u **Toewijzingen**. 
3. Kies **Groepen selecteren** en kies op de blade **Groepen selecteren** de groep(en) waar u het profiel aan wilt toewijzen. Kies vervolgens **Selecteren**.

## <a name="edit-an-autopilot-deployment-profile"></a>Een Windows AutoPilot-implementatieprofiel bewerken
Nadat u een AutoPilot-implementatieprofiel hebt gemaakt, kunt u bepaalde delen ervan bewerken.   

1. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) de optie **Apparaatinschrijving**.
2. Onder **Windows-inschrijving** in het gedeelte **Windows AutoPilot** kiest u **Implementatieprofielen**.
3. Selecteer het profiel dat u wilt bewerken.
4. Klik links op **Eigenschappen** om de naam of beschrijving van het implementatieprofiel te wijzigen. Klik op **Opslaan** wanneer u klaar bent met het aanbrengen van wijzigingen.
5. Klik op **Instellingen** de OOBE-instellingen te wijzigen. Klik op **Opslaan** wanneer u klaar bent met het aanbrengen van wijzigingen.

> [!NOTE]
> Wijzigingen aan het profiel worden toegepast op apparaten die zijn toegewezen aan dit profiel. Het bijgewerkte profiel wordt echter niet toegepast op een apparaat dat al is ingeschreven bij Intune totdat het apparaat opnieuw is ingesteld en ingeschreven.

## <a name="alerts-for-windows-autopilot-unassigned-devices-----163236---"></a>Waarschuwingen voor niet-toegewezen Windows AutoPilot-apparaten <!-- 163236 -->
U kunt een waarschuwing bekijken als u wilt zien aan hoeveel apparaten van het AutoPilot-programma geen AutoPilot-implementatieprofielen zijn toegewezen. Aan de hand van de informatie in de waarschuwing kunt u profielen maken en deze toewijzen aan de niet-toegewezen apparaten. Als u op de waarschuwing klikt, verschijnt een volledige lijst met Windows AutoPilot-apparaten en gedetailleerde informatie.

Als u waarschuwingen over niet-toegewezen apparaten wilt zien, kiest u in [Intune in Azure Portal](https://aka.ms/intuneportal) de optie **Apparaatinschrijving** > **Overzicht** > **Niet-toegewezen apparaten**.  


## <a name="assign-a-user-to-a-specific-autopilot-device"></a>Een gebruiker toewijzen aan een specifiek Autopilot-apparaat

U kunt een gebruiker toewijzen aan een specifiek Autopilot-apparaat. Deze toewijzing wordt vooraf ingevuld voor een gebruiker uit Azure Active Directory op de aanmeldingspagina in de [huisstijl van het bedrijf](https://docs.microsoft.com/azure/active-directory/fundamentals/customize-branding) tijdens de installatie van Windows. Ook kunt u de naam van een aangepast welkomstbericht instellen. Hiermee wordt Windows-aanmelding niet vooraf gevuld of gewijzigd. Alleen gelicentieerde gebruikers van Intune kunnen op deze manier worden toegewezen.

Voorwaarden: de Azure Active Directory-bedrijfsportal is geconfigureerd, evenals de meest recente [Windows 10 Insider Preview-build](https://docs.microsoft.com/windows-insider/at-work-pro/).

1. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) de optie **Apparaatinschrijving** > **Windows-inschrijving** > **Apparaten** > kies het apparaat > **Gebruiker toewijzen**.
    ![Schermafbeelding van Gebruiker toewijzen](media/enrollment-autopilot/assign-user.png)
2. Kies een Azure-gebruiker met een licentie voor het gebruik van Intune en kies **Selecteren**.
    ![Schermafbeelding van Gebruiker selecteren](media/enrollment-autopilot/select-user.png)
3. Typ in het vak **beschrijvende naam van gebruiker** een beschrijvende naam of accepteer de standaardwaarde. Dit is de beschrijvende naam die wordt weergegeven wanneer de gebruiker zich aanmeldt tijdens de installatie van Windows.
    ![Schermafbeelding van beschrijvende naam](media/enrollment-autopilot/friendly-name.png)
4. Kies **OK**.


## <a name="delete-autopilot-devices"></a>AutoPilot-apparaten verwijderen

U kunt Windows AutoPilot-apparaten verwijderen die niet zijn ingeschreven.

1. Als de apparaten zijn ingeschreven bij Intune, moet u ze eerst [verwijderen uit de Azure Active Directory-portal](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).

2. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) de optie **Apparaatinschrijving** > **Windows-inschrijving** > **Apparaten**.

3. Kies onder **Windows AutoPilot-apparaten** de apparaten die u wilt verwijderen, en kies vervolgens **Verwijderen**.

4. Bevestig de verwijdering door **Ja**  te kiezen. Verwijderen kan enkele minuten duren.

## <a name="using-autopilot-in-other-portals"></a>AutoPilot in andere portals gebruiken
Als u geen interesse hebt in Mobile Device Management, kunt u AutoPilot bijvoorbeeld gebruiken in de Microsoft Store voor Bedrijven. Hoewel het gebruik van andere portals een optie is, raden we aan om alleen Intune te gebruiken voor uw AutoPilot-implementaties. Als u Intune en een andere portal gebruikt, kunt u met Intune het volgende niet doen:
- Wijzigingen weergeven in profielen die zijn gemaakt in Intune, maar bewerkt in een andere portal
- Profielen synchroniseren die zijn gemaakt in een andere portal
- Wijzigingen in profieltoewijzingen weergeven die zijn aangebracht in een andere portal
- Profieltoewijzingen synchroniseren die zijn uitgevoerd in een andere portal
- Wijzigingen in de lijst met apparaten weergeven die zijn gemaakt in een andere portal

## <a name="next-steps"></a>Volgende stappen
Ontdek hoe u apparaten beheert nadat u Windows AutoPilot hebt geconfigureerd voor geregistreerde Windows 10-apparaten. Zie [Wat is Microsoft Intune-apparaatbeheer?](https://docs.microsoft.com/intune/device-management) voor meer informatie.
