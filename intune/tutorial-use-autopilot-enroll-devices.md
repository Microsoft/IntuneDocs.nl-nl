---
title: 'Zelfstudie: Autopilot gebruiken om apparaten in Intune in te schrijven'
titleSuffix: Microsoft Intune
description: In deze zelfstudie gaat u Windows Autopilot instellen om apparaten in Intune in te schrijven.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/19/2018
ms.topic: tutorial
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
Customer intent: As an Intune admin, I want to set up Windows Autopilot so that users can enroll in Intune.
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.openlocfilehash: 087f890f84c9bc0ff0c46f129ef84b8a268c738e
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52187732"
---
# <a name="tutorial-use-autopilot-to-enroll-windows-devices-in-intune"></a>Zelfstudie: Autopilot gebruiken om Windows-apparaten in Intune in te schrijven
Windows Autopilot maakt het makkelijker om apparaten in te schrijven. Met Microsoft Intune en Autopilot geeft u nieuwe apparaten aan uw eindgebruikers zonder dat u aangepaste installatiekopieën van besturingssystemen hoeft te bouwen, onderhouden en toe te passen. 

In deze zelfstudie leert u het volgende:
> [!div class="checklist"]
> * Apparaten toevoegen aan Intune
> * Een Autopilot-apparaatgroep maken
> * Een Autopilot-implementatieprofiel maken
> * Het Autopilot-implementatieprofiel toewijzen aan de apparaatgroep
> * Windows-apparaten naar gebruikers distribueren

Als u niet over een Intune-abonnement beschikt, kunt u [zich registreren voor een gratis proefaccount](free-trial-sign-up.md).

Zie [Overzicht van Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot) voor een overzicht van voordelen, scenario's en vereisten van Autopilot.


## <a name="prerequisites"></a>Vereisten
- [Automatische inschrijving bij Windows instellen](quickstart-setup-auto-enrollment.md)
- [Azure Active Directory Premium-abonnement](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->


## <a name="add-devices"></a>Apparaten toevoegen

De eerste stap bij het instellen van Windows Autopilot bestaat uit het toevoegen van de Windows-apparaten aan Intune. Alle wat u moet doen, is een CSV-bestand maken en dat importeren in Intune.

1. Maak in een willekeurige teksteditor een lijst met door komma's gescheiden waarden (CSV) die de Windows-apparaten aanduiden. Gebruik de volgende indeling:
    
    *serial-number*, *windows-product-id*, *hardware-hash*, *optional-order-id*
    
    De eerste drie items zijn vereist, maar de order-id is optioneel.

2. Sla het CSV-bestand op.

3. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) de optie **Apparaatinschrijving** > **Windows-inschrijving** > **Apparaten** > **Importeren**.

    ![Schermafbeelding van Windows Autopilot-apparaten](media/enrollment-autopilot/autopilot-import-device.png)

4. Onder **Windows Autopilot-apparaten toevoegen** bladert u naar het CSV-bestand dat u hebt opgeslagen.

    ![Schermafbeelding van het toevoegen van Windows Autopilot-apparaten](media/enrollment-autopilot/autopilot-import-device2.png)

5. Kies **Importeren** om apparaatgegevens te importeren. Het importeren kan enkele minuten duren.

4. Wanneer het importeren is voltooid, kiest u **Apparaatinschrijving** > **Windows-inschrijving** > **Windows Autopilot** > **Apparaten** > **Synchroniseren**. Er wordt een bericht weergegeven dat de synchronisatie wordt uitgevoerd. Het proces kan enige minuten duren, afhankelijk van hoeveel apparaten u synchroniseert.

5. Vernieuw de weergave om de nieuwe apparaten te zien.

## <a name="create-an-autopilot-device-group"></a>Een Autopilot-apparaatgroep maken

Vervolgens gaat u een apparaatgroep maken en de Autopilot-apparaten die u zojuist hebt geladen, erin plaatsen.

1. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) de optie **Groepen** > **Nieuwe groep**.
2. Op de blade **Groep**:
    1. Als **groepstype** kiest u **Beveiliging**.
    2. Als **groepsnaam** voert u *Autopilot-groep* in. Als **groepsbeschrijving** voert u *testgroep voor Autopilot-apparaten* in.
    3. Als **lidmaatschapstype** kiest u **Toegewezen**.
3. In de blade **Groep** kiest u **Leden** en voegt u de Autopilot-apparaten toe aan de groep. Autopilot-apparaten die nog niet zijn ingeschreven, zijn apparaten waarvan de naam overeenkomt met het serienummer van het apparaat.
4. Kies **Maken**.  

## <a name="create-an-autopilot-deployment-profile"></a>Een Autopilot-implementatieprofiel maken

Nadat u een groep apparaten hebt gemaakt, moet u een implementatieprofiel maken zodat u de Autopilot-apparaten kunt configureren.

1. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) de optie **Apparaatinschrijving** > **Windows-inschrijving** > **Apparaatprofielen** > **Profiel maken**.
2. Als **naam** voert u *Autopilot-profiel* in. Als **beschrijving** voert u *Testprofiel voor Autopilot-apparaten* in.
3. Stel **Alle doelapparaten converteren naar Autopilot** in op **Ja**. Deze instelling zorgt ervoor dat alle apparaten in de lijst worden ingeschreven bij de Autopilot-implementatieservice. Het kan 48 uur duren voordat de registratie is verwerkt.
4. Als **implementatiemodus** kiest u **Op basis van gebruiker**. Apparaten met dit profiel worden gekoppeld aan de gebruiker die het apparaat inschrijft. Er zijn gebruikersreferenties vereist om het apparaat in te kunnen schrijven.
5. In het vak **Toevoegen aan Azure AD als** kiest u **Toegevoegd aan Azure AD**.
6. Kies **Out-Of-Box Experience (OOBE)**, configureer de volgende opties (laat andere gewoon op de standaardinstellingen staan) en kies vervolgens **Opslaan**:
    - **Gebruiksrechtovereenkomst (EULA)**: **verbergen**
    - **Privacy-instellingen**: **weergeven**
    - **Gebruikersaccounttype**: **standaard**

6. Kies op **Maken** om het profiel te maken. Het Autopilot-implementatieprofiel is nu klaar om te worden toegewezen aan apparaten.

## <a name="assign-an-autopilot-deployment-profile-to-a-device-group"></a>Een Autopilot-implementatieprofiel toewijzen aan een apparaatgroep

Nu het implementatieprofiel is gemaakt, moet u dit toewijzen aan de apparaatgroep.
1. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) de optie **Apparaatinschrijving** > **Windows-inschrijving** > **Apparaatprofielen** > kies een profiel.
2. Op de specifieke profielblade kiest u **Toewijzingen**. 
3. Kies **Groepen selecteren**, kies vervolgens in de blade **Groepen selecteren** de optie **Autopilot-groep** en kies daarna **Selecteren**.

## <a name="distribute-devices-to-users"></a>Apparaten onder gebruikers distribueren

U kunt de Windows-apparaten nu naar uw gebruikers distribueren. Wanneer ze zich voor de eerste keer aanmelden, schrijft het Autopilot-systeem automatisch de apparaten in en configureert het deze. 

## <a name="clean-up-resources"></a>Resources opschonen

Als u de Autopilot-apparaten niet meer wilt gebruiken, kunt u deze verwijderen.

1. Als de apparaten zijn ingeschreven bij Intune, moet u ze eerst [verwijderen uit de Azure Active Directory-portal](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).

2. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) de optie **Apparaatinschrijving** > **Windows-inschrijving** > **Apparaten**.

3. Kies onder **Windows Autopilot-apparaten** de apparaten die u wilt verwijderen, en kies vervolgens **Verwijderen**.

4. Bevestig de verwijdering door **Ja**  te kiezen. Verwijderen kan enkele minuten duren.

## <a name="next-steps"></a>Volgende stappen

Er bestaat aanvullende informatie over andere opties die voor Windows Autopilot beschikbaar zijn.

> [!div class="nextstepaction"]
> [Diepgaand artikel over Autopilot-inschrijving](enrollment-autopilot.md)


