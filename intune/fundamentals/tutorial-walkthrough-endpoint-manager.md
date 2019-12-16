---
title: 'Zelfstudie: walkthrough voor Intune in Microsoft Endpoint Manager'
titleSuffix: Microsoft Intune
description: In deze zelfstudie krijgt u een rondleiding in Microsoft Intune in het Microsoft Endpoint Manager-beheercentrum om te leren hoe u taken kunt uitvoeren.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/06/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
Customer intent: As an Intune admin, I want to learn where to find the different features in Intune from the Microsoft Endpoint Manager admin center.
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 267f09c3dc16aab10fbe64f0e8662ee6f7c7ffa0
ms.sourcegitcommit: ec69e7ccc6e6183862a48c1b03ca6a3bf573f354
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/07/2019
ms.locfileid: "74907989"
---
# <a name="tutorial-walkthrough-intune-in-microsoft-endpoint-manager"></a>Zelfstudie: Walkthrough voor Intune in Microsoft Endpoint Manager

[Azure](https://docs.microsoft.com/learn/modules/welcome-to-azure) bevat meer dan 100 services die u met tal van cloud-computingscenario's en -mogelijkheden kunnen helpen. Microsoft Intune is van de vele services die beschikbaar zijn in Azure. Intune helpt u garanderen dat apparaten, apps en gegevens van uw bedrijf voldoen aan de beveiligingsvereisten van uw bedrijf. U bepaalt zelf welke vereisten moeten worden gecontroleerd en wat er gebeurt wanneer er niet aan die vereisten wordt voldaan. In het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) vindt u de Microsoft Intune-service en andere instellingen voor apparaatbeheer. Door te weten welke functies beschikbaar zijn in Intune, kunt u verschillende MDM- (Mobile Device Management) en MAM-taken (Mobile Application Management) uitvoeren.

> [!NOTE]
> Microsoft Endpoint Manager is een zelfstandig, geïntegreerd eindpuntbeheerplatform voor het beheren van al uw eindpunten. In dit Microsoft Endpoint Manager-beheercentrum is ConfigMgr en Microsoft Intune geïntegreerd.

In deze zelfstudie doet u het volgende:
> [!div class="checklist"]
> * Rondleiding door het Microsoft Endpoint Manager-beheercentrum
> * Uw weergave van het Microsoft Endpoint Manager-beheercentrum aanpassen

Als u niet over een Intune-abonnement beschikt, kunt u [zich registreren voor een gratis proefaccount](free-trial-sign-up.md).

## <a name="prerequisites"></a>Vereisten
Bekijk de volgende vereisten voordat u Microsoft Intune instelt:

- [Ondersteunde besturingssystemen en browsers](../supported-devices-browsers.md) 
- [Netwerkconfiguratievereisten en bandbreedte](../network-bandwidth-use.md)

## <a name="sign-up-for-a-microsoft-intune-free-trial"></a>Registreren voor een gratis proefversie van Microsoft Intune

U mag Intune 30 dagen gratis proberen. Als u al een werk- of schoolaccount hebt **meld u dan aan** met dat account en voeg Intune toe aan uw abonnement. Anders kunt u zich [registreren voor een gratis proefversie](free-trial-sign-up.md) om Intune te gebruiken voor uw organisatie.

> [!IMPORTANT]
> U kunt een bestaand werk- of schoolaccount niet combineren nadat u zich hebt aangemeld voor een nieuw account.

## <a name="tour-microsoft-intune-in-the-microsoft-endpoint-manager-admin-center"></a>Rondleiding door Microsoft Intune in het Microsoft Endpoint Manager-beheercentrum

Volg de onderstaande stappen om meer inzicht te krijgen in Intune in het Microsoft Endpoint Manager-beheercentrum. Zodra u de rondleiding hebt voltooid, hebt u meer kennis over een aantal van de belangrijkste onderdelen in Intune.

1. Open een browser en meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431). Als u een nieuwe gebruiker van Intune bent, gebruikt u uw gratis proefabonnement.

    ![Schermopname van het Microsoft Endpoint Manager-beheercentrum - Startpagina](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-01.png)

    Wanneer u de Microsoft Endpoint Manager of een andere service in Azure opent, wordt de service weergegeven in een deelvenster. Een aantal workloads die u in Intune kunt gebruiken zijn **Apparaten**, **Apps**, **Gebruikers** en **Groepen**. Een workload is simpelweg een subgebied van een service. Wanneer u de workload selecteert, wordt hiermee dit deelvenster in een volledige pagina geopend. Andere deelvensters worden vanaf de rechterkant van het deelvenster getoond zodra ze worden geopend. Als ze sluiten, ziet u het vorige deelvenster weer. 

    Wanneer u Microsoft Endpoint Manager opent, ziet u standaard het deelvenster **Startpagina**. Dit deelvenster biedt een algemene visuele momentopname van de tenantstatus en nalevingsstatus, alsmede andere nuttige koppelingen.

2. Selecteer in het navigatiedeelvenster **Dashboard** om algemene informatie over de apparaten en client-apps in uw Intune-tenant weer te geven. Als u met een nieuwe Intune-tenant begint, hebt u nog geen geregistreerde apparaten. 

    ![Schermopname van het Microsoft Endpoint Manager-beheercentrum - Dashboard](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-02.png)
    
    Met Intune kunt u de apparaten en apps beheren waarvan uw werknemers gebruikmaken en kunt u beheren hoe zij toegang hebben tot uw bedrijfsgegevens. Om gebruik te kunnen maken van de MDM-service (Mobile Device Management), moeten de apparaten eerst worden geregistreerd bij Intune. Wanneer een apparaat is geregistreerd, wordt een MDM-certificaat voor het apparaat uitgegeven. Dit certificaat wordt gebruikt om te communiceren met de Intune-service. 

    Er zijn verschillende methoden om de apparaten van uw werknemers te registreren in Intune. Elke methode is afhankelijk van het eigendom van het apparaat (persoonlijk of zakelijk), het apparaattype (iOS, Windows, Android), en de beheervereisten (opnieuw instellen, affiniteit, vergrendelen). Voordat u Apparaatregistratie kunt inschakelen, moet u echter uw Intune-infrastructuur instellen. Voor apparaatinschrijving is met name het [instellen van uw MDM-instantie](mdm-authority-set.md) van belang. Zie [Intune instellen](setup-steps.md) voor meer informatie over het gereedmaken van uw Intune-omgeving (tenant). Zodra uw Intune-tenant gereed is, kunt u apparaten registreren. Zie [Wat is apparaatinschrijving?](../enrollment/device-enrollment.md) voor meer informatie over apparaatinschrijving.

3. Selecteer vanuit het navigatiedeelvenster **Apparaten** om details over de geregistreerde apparaten in uw Intune-tenant weer te geven. 

    > [!TIP]
    > Als u Intune eerder hebt gebruikt in Azure Portal, hebt u de bovenstaande gegevens in Azure Portal gevonden door u aan te melden bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) en **Apparaten** te selecteren.

    Het deelvenster **Apparaten - Overzicht** bevat verschillende tabbladen waarmee u een samenvatting van de volgende statussen en waarschuwingen kunt weergeven:
    - **Inschrijvingsstatus**: bekijk details over ingeschreven Intune-apparaten op basis van platform en registratiefouten.
    - **Inschrijvingswaarschuwingen**: geef meer informatie over niet-toegewezen apparaten per platform weer. 
    - **Nalevingsstatus**: controleer de nalevingsstatus op basis van apparaat, beleid, instelling, bedreigingen en beveiliging. Dit deelvenster bevat tevens een lijst met apparaten zonder compliancebeleid.
    - **Configuratiestatus**: controleer de configuratiestatus van apparaatprofielen, evenals de implementatie van het profiel. 
    - **Status van software-updates**: geef een visual weer van de implementatiestatus voor alle apparaten en voor alle gebruikers.

    ![Schermopname van het Microsoft Endpoint Manager-beheercentrum - Apparaten](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-03.png)

4. Vanuit het deelvenster **Apparaten - Overzicht** selecteert u **Compliancebeleidsregels** om details weer te geven over naleving voor apparaten die door Intune worden beheerd. U ziet details die vergelijkbaar zijn met de volgende afbeelding.

    ![Schermopname van het Microsoft Endpoint Manager-beheercentrum - Compliancebeleidsregels](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-04.png)
    
    > [!TIP]
    > Als u Intune eerder hebt gebruikt in Azure Portal, hebt u de bovenstaande gegevens in Azure Portal gevonden door u aan te melden bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) en **Apparaatnaleving** te selecteren.

    Nalevingsvereisten zijn in wezen regels zoals het vereisen van een apparaatpincode of het vereisen van apparaatversleuteling. Het apparaatnalevingsbeleid bevat de regels en instellingen waaraan een apparaat moet voldoen om te voldoen aan het beleid. Als u Apparaatnaleving wilt gebruiken, moet u over het volgende beschikken:
    - Een Intune- en een Azure AD Premium-abonnement (Azure Active Directory)
    - Apparaten waarop een ondersteund platform wordt uitgevoerd
    - Apparaten moeten zijn geregistreerd in Intune
    - Apparaten die zijn geregistreerd bij ofwel één gebruiker of bij een gebruiker die geen primaire gebruiker is.
    
    Zie [Aan de slag met apparaatnalevingsbeleid in Intune](../protect/device-compliance-get-started.md) voor meer informatie.

5. Vanuit het deelvenster **Apparaten - Overzicht** selecteert u **Voorwaardelijke toegang** om details weer te geven over toegangsbeleid.

    ![Schermopname van het Microsoft Endpoint Manager-beheercentrum - Voorwaardelijke toegang](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-05.png)

    > [!TIP]
    > Als u Intune eerder hebt gebruikt in Azure Portal, hebt u de bovenstaande gegevens in Azure Portal gevonden door u aan te melden bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) en **Voorwaardelijke toegang** te selecteren.

    Voorwaardelijke toegang verwijst naar de manieren waarop u de apparaten en apps kunt beheren die toestemming hebben om verbinding te maken met uw e-mail- en bedrijfsgegevens. Zie [Wat is voorwaardelijke toegang?](../protect/conditional-access.md) voor meer informatie over apparaat- en appgebaseerde voorwaardelijke toegang en algemene scenario's voor het gebruiken van voorwaardelijke toegang met Intune.

6. Vanuit het navigatiedeelvenster selecteert u **Apparaten** > **Configuratieprofielen** om details weer te geven over apparaatprofielen in Intune.

    ![Schermopname van het Microsoft Endpoint Manager-beheercentrum - Configuratieprofielen](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-06.png)
    
    > [!TIP]
    > Als u Intune eerder hebt gebruikt in Azure Portal, hebt u de bovenstaande gegevens in Azure Portal gevonden door u aan te melden bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) en **Apparaatconfiguratie** te selecteren.

    Intune omvat instellingen en functies die u op verschillende apparaten binnen uw organisatie kunt in- of uitschakelen. Deze instellingen en functies worden toegevoegd aan 'configuratieprofielen'. U kunt profielen voor verschillende apparaten en verschillende platforms maken, waaronder iOS, Android, macOS en Windows. Vervolgens kunt u Intune gebruiken om het profiel op apparaten in uw organisatie toe te passen.   

    Zie [Functies-instellingen toepassen op uw apparaten met apparaatprofielen in Microsoft Intune](../configuration/device-profiles.md) voor meer informatie over apparaatconfiguratie.

7. Selecteer vanuit het navigatiedeelvenster **Apparaten** > **Alle apparaten** om details over de geregistreerde apparaten in uw Intune-tenant weer te geven. Als u met een nieuwe Intune-lijst begint, hebt u nog geen geregistreerde apparaten.

    ![Schermopname van het Microsoft Endpoint Manager-beheercentrum - Alle apparaten](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-07.png)

    In deze lijst met apparaten worden de belangrijkste details over naleving, de besturingssysteemversie en de laatste incheckdatum weergegeven.

    > [!TIP]
    > Als u Intune eerder hebt gebruikt in Azure Portal, hebt u de bovenstaande gegevens in Azure Portal gevonden door u aan te melden bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) en **Apparaten** > **Alle apparaten** te selecteren.
 
8. Selecteer in het navigatiedeelvenster **Apps** om een overzicht van de app-status weer te geven. Dit deelvenster bevat de installatiestatus van de app op basis van de volgende tabbladen:

    > [!TIP]
    > Als u Intune eerder hebt gebruikt in Azure Portal, hebt u de bovenstaande gegevens in Azure Portal gevonden door u aan te melden bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) en **Client-apps** te selecteren.

    Het deelvenster **Apps - Overzicht** bevat twee tabbladen waarmee u een samenvatting van de volgende statussen kunt weergeven:
    - **Installatiestatus**: bekijk de belangrijkste installatiefouten per apparaat en de apps met installatiefouten.  
    - **Status van app-beveiligingsbeleid**: hier vindt u informatie over gebruikers waaraan het app-beveiligingsbeleid is toegewezen, evenals gemarkeerde gebruikers.

    ![Schermopname van het Microsoft Endpoint Manager-beheercentrum - Apps](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-08.png)

    U kunt, als IT-beheerder, Microsoft Intune gebruiken om de client-apps te beheren die de werknemers van uw bedrijf gebruiken. Deze functionaliteit is een aanvulling op het beheren van apparaten en beschermen van gegevens. Een van de prioriteiten van een beheerder is om ervoor te zorgen dat eindgebruikers toegang hebben tot de apps die ze nodig hebben voor hun werk. Verder wilt u misschien apps toewijzen en beheren op apparaten die niet bij Intune zijn geregistreerd. Intune biedt een scala aan mogelijkheden om u te helpen de benodigde apps op de gekozen apparaten te krijgen. 

    > [!NOTE]
    > Het deelvenster **Apps - Overzicht** bevat ook gegevens over de tenantstatus en accounts.

    Zie [Apps toevoegen aan Microsoft Intune](../apps/apps-add.md) en [Apps toewijzen aan groepen met Microsoft Intune](../apps/apps-deploy.md) voor meer informatie over het toevoegen en toewijzen van apps.

9. Selecteer vanuit het deelvenster**Apps - Overzicht** de optie **Alle apps** om een lijst met apps weer te geven die aan Intune zijn toegevoegd.

    > [!TIP]
    > Als u Intune eerder hebt gebruikt in Azure Portal, hebt u de bovenstaande gegevens in Azure Portal gevonden door u aan te melden bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) en **Client-apps** > **Apps** te selecteren.

    U kunt verschillende typen apps toevoegen op basis van het platform in Intune. Zodra een app is toegevoegd, kunt u deze toewijzen aan groepen gebruikers. 

    ![Schermopname van het Microsoft Endpoint Manager-beheercentrum - Alle apps](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-09.png)

    Zie [Web-apps toevoegen aan Microsoft Intune](~/apps/apps-add.md) voor meer informatie. 

10. Selecteer vanuit het navigatiedeelvenster **Gebruikers** om details weer te geven over de gebruikers die u in Intune hebt opgenomen. Deze gebruikers vormen het personeel van uw bedrijf.

    ![Schermopname van het Microsoft Endpoint Manager-beheercentrum - Gebruikers](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-10.png)

    > [!TIP]
    > Als u Intune eerder hebt gebruikt in Azure Portal, hebt u de bovenstaande gegevens in Azure Portal gevonden door u aan te melden bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) en **Gebruikers** te selecteren.

    U kunt gebruikers rechtstreeks toevoegen aan Intune of gebruikers synchroniseren via uw on-premises Active Directory. Zodra gebruikers zijn toegevoegd, kunnen ze apparaten registreren en hebben ze toegang tot bedrijfsresources. U kunt gebruikers ook extra machtigingen geven voor toegang tot Intune. Zie [Gebruikers toevoegen en beheerdersmachtigingen geven in Intune](users-add.md) voor meer informatie.

11. Selecteer vanuit het navigatiedeelvenster **Groepen** om details weer te geven over de Azure AD-groepen (Azure Active Directory) in Intune. Als Intune-beheerder gebruikt u groepen om apparaten en gebruikers te beheren.

    ![Schermopname van het Microsoft Endpoint Manager-beheercentrum - Groepen](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-11.png)

    > [!TIP]
    > Als u Intune eerder hebt gebruikt in Azure Portal, hebt u de bovenstaande gegevens in Azure Portal gevonden door u aan te melden bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) en **Groepen** te selecteren.

    U kunt groepen instellen voor uw organisatiebehoeften. Maak groepen om gebruikers of apparaten in te delen op geografische locatie, afdeling of hardwarekenmerken. Gebruik groepen voor het beheren van taken op schaal. U kunt zo bijvoorbeeld beleidsregels instellen voor een groot aantal gebruikers tegelijk of apps implementeren op een reeks apparaten. Zie [Groepen toevoegen om gebruikers en apparaten te organiseren](../groups-add.md) voor meer informatie over groepen.

12. Selecteer vanuit het navigatiedeelvenster **Tenantbeheer** om details over de Intune-tenant weer te geven.

    > [!TIP]
    > Als u Intune eerder hebt gebruikt in Azure Portal, hebt u de bovenstaande gegevens in Azure Portal gevonden door u aan te melden bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) en **Tenantstatus** te selecteren.

    Het deelvenster **Tenantbeheer - Tenantstatus** bevat tabbladen voor **Tenantgegevens**, **Connectorstatus** en **Servicestatusdashboard**. Als zich problemen voordoen met uw tenant of met Intune zelf, vindt u meer informatie in dit deelvenster. 

    ![Schermopname van het Microsoft Endpoint Manager-beheercentrum - Tenantstatus](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-12.png)

    Zie [Status van Intune-tenant](../tenant-status.md) voor meer informatie.

13. Selecteer in het navigatiedeelvenster **Probleemoplossing en ondersteuning** > **Probleem oplossen** om de statusdetails van een specifieke gebruiker te controleren. 

    > [!TIP]
    > Als u Intune eerder hebt gebruikt in Azure Portal, hebt u de bovenstaande gegevens in Azure Portal gevonden door u aan te melden bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) en **Probleem oplossen** te selecteren.

    Vanuit de vervolgkeuzelijst **Toewijzingen** kunt u ervoor kiezen de gerichte toewijzingen van client-apps, beleidsregels, updateringen en inschrijvingsbeperkingen weer te geven. Daarnaast bevat dit deelvenster apparaatdetails, de app-beveiligingsstatus en inschrijvingsfouten voor een specifieke gebruiker.

    ![Schermopname van het Microsoft Endpoint Manager-beheercentrum - Probleem oplossen](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-13.png)

    Zie [De portal voor probleemoplossing gebruiken om gebruikers in uw bedrijf te helpen](../help-desk-operators.md) voor meer informatie over probleemoplossing met Intune.

14. Selecteer in het navigatiedeelvenster **Probleemoplossing en ondersteuning** > **Help en ondersteuning** om hulp te vragen. 

    > [!TIP]
    > Als u Intune eerder hebt gebruikt in Azure Portal, hebt u de bovenstaande gegevens in Azure Portal gevonden door u aan te melden bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) en **Help en ondersteuning** te selecteren.

    Als IT-beheerder kunt u de optie **Help en ondersteuning** gebruiken om oplossingen te zoeken en te bekijken en om een online-ondersteuningsticket voor Intune in te dienen. 

    ![Schermopname van het Microsoft Endpoint Manager-beheercentrum - Help en ondersteuning](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-14.png)

    Als u een ondersteuningsticket wilt maken, moet in Azure Active Directory aan uw account een beheerdersrol zijn toegewezen. Beheerdersrollen zijn onder andere **Intune-beheerder**, **Algemene beheerder** en **Servicebeheerder**. 

    Zie [Ondersteuning voor Microsoft Intune krijgen](../get-support.md) voor meer informatie.

15. Selecteer in het navigatiedeelvenster **Probleemoplossing en ondersteuning** > **Begeleide scenario's** om beschikbare begeleide Intune-scenario's weer te geven. 

    Een begeleid scenario is een aangepaste reeks stappen rondom een end-to-end-use-case. Algemene scenario's zijn gebaseerd op de rol die een beheerder, gebruiker of apparaat in uw organisatie speelt. Voor deze rollen is doorgaans een verzameling zorgvuldig gegroepeerde profielen, instellingen, toepassingen en beveiligingsmechanismen vereist om de beste gebruikerservaring en beveiliging te kunnen bieden.

    Als u niet bekend bent met alle stappen en resources die vereist zijn om een bepaald scenario voor Intune te implementeren, kunt u begeleide scenario's als uitgangspunt gebruiken. 

    ![Schermopname van het Microsoft Endpoint Manager-beheercentrum - Begeleide scenario's](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-15.png)

    Zie [Overzicht van begeleide scenario's](~/fundamentals/guided-scenarios-overview.md) voor meer informatie over begeleide scenario's.

## <a name="configure-the-microsoft-endpoint-manager-admin-center"></a>Het Microsoft Endpoint Manager-beheercentrum configureren

In Azure kunt u de weergave van de portal aanpassen en configureren.

### <a name="change-the-dashboard"></a>Het dashboard wijzigen

Het **Dashboard** dient om algemene informatie over de apparaten en client-apps in uw Intune-tenant weer te geven. Dashboards bieden u een manier om een toegespitste en georganiseerde weergave te maken in het Microsoft Endpoint Manager-beheercentrum. Gebruik dashboards als werkruimte waar u snel taken kunt starten voor dagelijkse bewerkingen en resources kunt bewaken. Bouw bijvoorbeeld aangepaste dashboards op basis van projecten, taken of gebruikersrollen. Het Microsoft Endpoint Manager-beheercentrum biedt een standaard dashboard als uitgangspunt. U kunt het standaard dashboard bewerken, extra dashboards maken en aanpassen, en dashboards publiceren en delen om ze beschikbaar te maken voor andere gebruikers. 

   ![Schermopname van het Microsoft Endpoint Manager-beheercentrum - Dashboard](./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-16.png)

Selecteer **Bewerken** om uw huidige dashboard te wijzigen. Als u uw standaarddashboard niet wilt wijzigen, kunt u ook een **Nieuw dashboard** maken. Als u een nieuw dashboard maakt, ziet u een leeg privédashboard met de **Tegelgalerie**. Hier kunt u tegels toevoegen of opnieuw rangschikken. U kunt tegels vinden op categorie of resourcetype. U kunt ook zoeken naar bepaalde tegels. Selecteer **Mijn dashboard** om een van uw bestaande aangepaste dashboards te selecteren.

### <a name="change-the-portal-settings"></a>De Portal-instellingen wijzigen

U kunt het Microsoft Endpoint Manager-beheercentrum aanpassen door de standaardweergave, het thema, de time-outperiode van de referenties en de taal- en regio-instellingen te kiezen.

   <img alt="Screenshot of the Microsoft Endpoint Manager admin center - Portal settings" src="./media/tutorial-walkthrough-endpoint-manager/tutorial-walkthrough-mem-17.png" width="250">

## <a name="next-steps"></a>Volgende stappen

Als u aan de slag wilt gaan in Microsoft Intune, doorloopt u de Intune Quickstarts door eerst een gratis Intune-account in te stellen.

> [!div class="nextstepaction"]
> [Quickstart: Microsoft Intune gratis proberen](free-trial-sign-up.md)
