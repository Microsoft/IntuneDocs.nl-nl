---
title: Apparaten inschrijven met het Windows AutoPilot Deployment-programma
titleSuffix: Microsoft Intune
description: Informatie over het inschrijven van Windows 10-apparaten met het Windows AutoPilot Deployment-programma.
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
ms.openlocfilehash: 934b80d1c174c25d37e30695f46afc88c8d8bfc3
ms.sourcegitcommit: 401cedcd7acc6cb3a6f18d4679bdadb0e0cdf443
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/28/2018
---
# <a name="enroll-windows-devices-by-using-the-windows-autopilot-deployment-program"></a>Windows-apparaten inschrijven met het Windows AutoPilot Deployment-programma
Het Windows AutoPilot Deployment-programma vereenvoudigt het inrichten van apparaten. Het kost veel tijd om aangepaste installatiekopieën van besturingssystemen te bouwen en onderhouden. Mogelijk besteedt u ook tijd aan het toepassen van deze aangepaste installatiekopieën op nieuwe apparaten, om ze voor te bereiden voor gebruik voordat u ze aan eindgebruikers verstrekt. Met Microsoft Intune en AutoPilot kunt u nieuwe apparaten aan uw eindgebruikers geven zonder dat u aangepaste installatiekopieën van besturingssystemen voor de apparaten hoeft te bouwen, onderhouden en toe te passen. Als u Intune gebruikt om AutoPilot-apparaten te beheren, kunt u beleidsregels, profielen, apps enzovoort beheren op de apparaten nadat ze zijn ingeschreven. Zie [Overzicht van Windows AutoPilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot) voor een overzicht van voordelen, scenario’s en vereisten.

## <a name="prerequisites"></a>Vereisten
- [Automatische inschrijving bij Windows is ingeschakeld](https://docs.microsoft.com/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune#enable-windows-10-automatic-enrollment)
- [Azure Active Directory Premium-abonnement](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->

## <a name="add-devices"></a>Apparaten toevoegen

U kunt Windows AutoPilot-apparaten toevoegen door een CSV-bestand te importeren met de bijbehorende informatie.

1. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) de optie **Apparaatinschrijving** > **Windows-inschrijving** > **Apparaten** > **Importeren**.

    ![Schermafbeelding van Windows AutoPilot-apparaten](media/enrollment-autopilot/autopilot-import-device.png)

2. Blader onder **Windows AutoPilot-apparaten toevoegen** naar een CSV-bestand met het serienummer, de Windows-product-id's, en de hardwarehashes van de apparaten die u wilt toevoegen.

    ![Schermafbeelding van het toevoegen van Windows AutoPilot-apparaten](media/enrollment-autopilot/autopilot-import-device2.png)

3. Kies **Importeren** om apparaatgegevens te importeren. Dit kan enkele minuten duren.

## <a name="synchronize-devices"></a>Apparaten synchroniseren
Synchroniseer uw geregistreerde apparaten met Intune, zodat u ze kunt configureren.

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies **Apparaatinschrijving** onder **Intune**.
4. Kies **Windows-inschrijving** en selecteer in de sectie **Windows AutoPilot Deployment-programma** de optie **Apparaten**.
5. Klik op **Synchroniseren** om uw geregistreerde apparaten te importeren. Er wordt een bericht weergegeven dat de synchronisatie wordt uitgevoerd.
6. Vernieuw de weergave om de nieuwe apparaten te zien. Het proces kan enige minuten duren, afhankelijk van hoeveel apparaten er worden gesynchroniseerd.  

## <a name="create-an-autopilot-deployment-profile"></a>Een Windows AutoPilot Deployment-profiel maken
AutoPilot-profielen worden gebruikt om de AutoPilot-apparaten te configureren.
1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies **Apparaatinschrijving** onder **Intune**.
4. Kies **Windows-inschrijving** en selecteer in de sectie **Windows AutoPilot Deployment-programma** de optie **Implementatieprofielen**.
5. Selecteer **Profiel maken** en kies een naam en optionele beschrijving.
6. Selecteer voor **Aan Azure AD toevoegen als** de optie **Toegevoegd aan Azure AD**.
7. Configureer voor **Out-Of-Box Experience (OOBE)** de volgende opties en klik vervolgens op **Opslaan**:

   - **Gebruiksrechtovereenkomst (EULA)**: kies of u de gebruiksrechtovereenkomst wilt weergeven voor gebruikers.
   - **Privacy-instellingen**: kies of u de privacyinstellingen wilt weergeven voor de gebruikers.
   - **Gebruikersaccounttype**: kies of het gebruikersaccounttype **Beheerder** of **Standaard**gebruiker is.

     > [!Note]    
     > Deze instelling geldt niet voor de accounts van de globale beheerder of bedrijfsbeheerder. Deze accounts kunnen geen standaardgebruikers zijn, omdat ze toegang hebben tot alle beheerfuncties in Azure AD.


6. Klik op **Maken** om het profiel te maken. Het AutoPilot-implementatieprofiel is nu klaar om te worden toegewezen aan apparaten.

> [!Note]    
> De volgende instellingen zijn geconfigureerd in alle AutoPilot-implementatieprofielen:
> - Instelpagina’s voor Cortana, OneDrive en OEM-registratie overslaan
> - Automatisch instellen voor werk of school
> - Aanmeldervaring met naam van bedrijf of school    

## <a name="assign-an-autopilot-deployment-profile"></a>Een Windows AutoPilot-implementatieprofiel toewijzen
Nadat u AutoPilot-implementatieprofielen hebt gemaakt, kunt u ze toewijzen aan geselecteerde apparaten.

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies **Apparaatinschrijving** onder **Intune**.
4. Kies **Windows-inschrijving** en selecteer in de sectie **Windows AutoPilot Deployment-programma** de optie **Apparaten**.
5. Kies de apparaten waaraan u het gemaakte implementatieprofiel wilt toewijzen. U kunt filteren met de kolom **Profielstatus** om snel apparaten te vinden waaraan geen profiel is toegewezen.
6. Klik op **Profiel toewijzen**, selecteer het AutoPilot-implementatieprofiel en klik op **Toewijzen**. Er wordt een bericht weergegeven dat de toewijzing wordt uitgevoerd.
7. Vernieuw de weergave om te zien dat het profiel is toegewezen aan de apparaten. Het proces kan enige minuten duren, afhankelijk van hoeveel apparaten u hebt geselecteerd.

> [!Note]
> Het nieuwe profiel is toegewezen aan het apparaat. Voor apparaten die al zijn ingeschreven bij Intune wordt het profiel toegepast nadat het apparaat opnieuw is ingesteld en geregistreerd.

### <a name="assign-a-different-autopilot-deployment-profile"></a>Een ander AutoPilot-implementatieprofiel toewijzen
Nadat u een AutoPilot-implementatieprofiel hebt toegewezen aan een apparaat, kunt u er indien gewenst een nieuw profiel aan toewijzen.  

## <a name="edit-an-autopilot-deployment-profile"></a>Een Windows AutoPilot-implementatieprofiel bewerken
Nadat u een AutoPilot-implementatieprofiel hebt gemaakt, kunt u bepaalde delen ervan bewerken.   

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies **Apparaatinschrijving** onder **Intune**.
4. Onder **Windows-inschrijving** in de sectie **Windows AutoPilot Deployment-programma** kiest u **Implementatieprofielen**.
5. Selecteer het profiel dat u wilt bewerken.
6. Klik links op **Eigenschappen** om de naam of beschrijving van het implementatieprofiel te wijzigen. Klik op **Opslaan** wanneer u klaar bent met het aanbrengen van wijzigingen.
7. Klik op **Instellingen** de OOBE-instellingen te wijzigen. Klik op **Opslaan** wanneer u klaar bent met het aanbrengen van wijzigingen.

> [!NOTE]
> Het bijgewerkte profiel wordt toegewezen aan apparaten. Het bijgewerkte profiel wordt echter niet toegepast op een apparaat dat al is ingeschreven bij Intune totdat het apparaat opnieuw is ingesteld en ingeschreven.

## <a name="using-autopilot-in-other-portals"></a>AutoPilot in andere portals gebruiken
Als het beheer van mobiele apparaten niet interessant is voor u, kunt u AutoPilot bijvoorbeeld gebruiken in de Microsoft Store voor Bedrijven. Hoewel het gebruik van andere portals een optie is, raden we aan om alleen Intune te gebruiken voor uw AutoPilot-implementaties. Als u Intune en een andere portal gebruikt, kunt u met Intune het volgende niet doen:
- Wijzigingen weergeven in profielen die zijn gemaakt in Intune, maar bewerkt in een andere portal
- Profielen synchroniseren die zijn gemaakt in een andere portal
- Wijzigingen in profieltoewijzingen weergeven die zijn aangebracht in een andere portal
- Profieltoewijzingen synchroniseren die zijn uitgevoerd in een andere portal
- Wijzigingen in de lijst met apparaten weergeven die zijn gemaakt in een andere portal

## <a name="alerts-for-windows-autopilot-unassigned-devices-----163236---"></a>Waarschuwingen voor niet-toegewezen Windows AutoPilot-apparaten <!-- 163236 -->
U kunt een waarschuwing bekijken voor niet-toegewezen Windows AutoPilot-apparaten om te zien aan hoeveel apparaten van het AutoPilot-programma geen AutoPilot-implementatieprofielen zijn toegewezen. Aan de hand van de informatie in de waarschuwing kunt u profielen maken en deze toewijzen aan de niet-toegewezen apparaten. Als u op de waarschuwing klikt, verschijnt een volledige lijst met Windows AutoPilot-apparaten en gedetailleerde informatie.

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies **Apparaatinschrijving** onder **Intune**.
4. Kies **Overzicht** om de waarschuwing te zien. Klik op de waarschuwing voor een lijst met AutoPilot-apparaten.  

## <a name="delete-autopilot-devices"></a>AutoPilot-apparaten verwijderen

U kunt Windows AutoPilot-apparaten verwijderen die niet zijn ingeschreven. U kunt apparaten uitschrijven en ze vervolgens verwijderen.

1. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) de optie **Apparaatinschrijving** > **Windows-inschrijving** > **Apparaten**.

2. Kies onder **Windows AutoPilot-apparaten** de apparaten die u wilt verwijderen, en kies vervolgens **Verwijderen**.

3. Bevestig de verwijdering door **Ja**  te kiezen. Verwijderen kan enkele minuten duren.


## <a name="next-steps"></a>Volgende stappen
Ontdek hoe u apparaten beheert nadat u Windows AutoPilot hebt geconfigureerd voor geregistreerde Windows 10-apparaten. Zie [Wat is Microsoft Intune-apparaatbeheer?](https://docs.microsoft.com/intune/device-management) voor meer informatie.
