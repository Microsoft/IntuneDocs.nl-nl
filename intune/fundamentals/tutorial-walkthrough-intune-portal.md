---
title: 'Zelfstudie: Walkthrough door Intune in Azure Portal'
titleSuffix: Microsoft Intune
description: In deze zelfstudie krijgt u een rondleiding in Microsoft Intune om te leren hoe u taken kunt uitvoeren.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/06/2019
ms.topic: tutorial
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: e892d8a3-7f74-498c-98d5-e968a8fbb049
Customer intent: As an Intune admin, I want to learn where to find the different features in Intune.
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9197d4f96eae1041b00b07110ef421a12a4fe338
ms.sourcegitcommit: 28622c5455adfbce25a404de4d0437fa2b5370be
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2019
ms.locfileid: "73712995"
---
# <a name="tutorial-walkthrough-of-microsoft-intune-in-the-azure-portal"></a>Zelfstudie: Walkthrough door Microsoft Intune in Azure Portal

[Azure](https://docs.microsoft.com/learn/modules/welcome-to-azure) bevat meer dan 100 services die u met tal van cloud-computingscenario's en -mogelijkheden kunnen helpen. Microsoft Intune is van de vele services die beschikbaar zijn in Azure. Intune helpt u garanderen dat apparaten, apps en gegevens van uw bedrijf voldoen aan de beveiligingsvereisten van uw bedrijf. U bepaalt zelf welke vereisten moeten worden gecontroleerd en wat er gebeurt wanneer er niet aan die vereisten wordt voldaan. U vindt de Microsoft Intune-service in [Azure Portal](https://portal.azure.com). Door te weten welke functies beschikbaar zijn in Intune, kunt u verschillende MDM- (Mobile Device Management) en MAM-taken (Mobile Application Management) uitvoeren.

In deze zelfstudie doet u het volgende:
> [!div class="checklist"]
> * Rondleiding door Microsoft Intune
> * Azure Portal configureren

Als u niet over een Intune-abonnement beschikt, kunt u [zich registreren voor een gratis proefaccount](free-trial-sign-up.md).

## <a name="prerequisites"></a>Vereisten
Bekijk de volgende vereisten voordat u Microsoft Intune instelt:

- [Ondersteunde besturingssystemen en browsers](../supported-devices-browsers.md) 
- [Netwerkconfiguratievereisten en bandbreedte](../network-bandwidth-use.md)

## <a name="sign-up-for-a-microsoft-intune-free-trial"></a>Registreren voor een gratis proefversie van Microsoft Intune

U mag Intune 30 dagen gratis proberen. Als u al een werk- of schoolaccount hebt **meld u dan aan** met dat account en voeg Intune toe aan uw abonnement. Anders kunt u zich [registreren voor een gratis proefversie](free-trial-sign-up.md) om Intune te gebruiken voor uw organisatie.

> [!IMPORTANT]
> U kunt een bestaand werk- of schoolaccount niet combineren nadat u zich hebt aangemeld voor een nieuw account.

## <a name="tour-microsoft-intune"></a>Rondleiding door Microsoft Intune

Volg de onderstaande stappen voor meer informatie over Intune in Azure Portal. Zodra u de rondleiding hebt voltooid, hebt u meer kennis over een aantal van de belangrijkste onderdelen in Intune.

1. Open een browser en meld u aan bij de [Intune-portal](https://aka.ms/intuneportal). Als u een nieuwe gebruiker van Intune bent, gebruikt u uw gratis proefabonnement.

    ![Schermopname van de Microsoft Intune-portal](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-01.png)

    Wanneer u Intune of een andere service in Azure opent, wordt de service weergegeven in een deelvenster. Een aantal workloads die u in Intune kunt gebruiken zijn **Apparaten**, **Client-apps**, **Gebruikers** en **Groepen**. Een workload is simpelweg een subgebied van een service. Wanneer u de workload selecteert, wordt hiermee dit deelvenster in een volledige pagina geopend. Andere deelvensters worden vanaf de rechterkant van het deelvenster getoond zodra ze worden geopend. Als ze sluiten, ziet u het vorige deelvenster weer. Een deelvenster wordt ook wel een blade genoemd. 

    Wanneer u Intune opent, ziet u standaard het deelvenster **Overzicht**. Dit deelvenster biedt een algemene visuele momentopname van de toewijzings- en nalevingsstatus van het apparaat, alsmede de installatiestatus van de app.

2. Vanuit [Intune](https://aka.ms/intuneportal) selecteert u **Apparaatregistratie** om details over de geregistreerde apparaten in uw Intune-tenant weer te geven. Als u met een nieuwe Intune-tenant begint, hebt u nog geen geregistreerde apparaten. 

    ![Schermopname van het deelvenster voor apparaatregistratie](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-02.png)
    
    Met Intune kunt u de apparaten en apps beheren waarvan uw werknemers gebruikmaken en kunt u beheren hoe zij toegang hebben tot uw bedrijfsgegevens. Om gebruik te kunnen maken van de MDM-service (Mobile Device Management), moeten de apparaten eerst worden geregistreerd bij Intune. Wanneer een apparaat is geregistreerd, wordt een MDM-certificaat voor het apparaat uitgegeven. Dit certificaat wordt gebruikt om te communiceren met de Intune-service. 

    Er zijn verschillende methoden om de apparaten van uw werknemers te registreren in Intune. Elke methode is afhankelijk van het eigendom van het apparaat (persoonlijk of zakelijk), het apparaattype (iOS, Windows, Android), en de beheervereisten (opnieuw instellen, affiniteit, vergrendelen). Voordat u Apparaatregistratie kunt inschakelen, moet u echter uw Intune-infrastructuur instellen. Voor apparaatinschrijving is met name het [instellen van uw MDM-instantie](mdm-authority-set.md) van belang. Zie [Intune instellen](setup-steps.md) voor meer informatie over het gereedmaken van uw Intune-omgeving (tenant). Zodra uw Intune-tenant gereed is, kunt u apparaten registreren. Zie [Wat is apparaatinschrijving?](../enrollment/device-enrollment.md) voor meer informatie over apparaatinschrijving.

3. Vanuit [Intune](https://aka.ms/intuneportal) selecteert u **Apparaatnaleving** om details weer te geven over naleving voor apparaten die door Intune worden beheerd. U ziet details die vergelijkbaar zijn met de volgende afbeelding.

    ![Schermopname van het deelvenster Apparaatnaleving](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-03.png)
    
    Nalevingsvereisten zijn in wezen regels zoals het vereisen van een apparaatpincode of het vereisen van apparaatversleuteling. Het apparaatnalevingsbeleid bevat de regels en instellingen waaraan een apparaat moet voldoen om te voldoen aan het beleid. Als u Apparaatnaleving wilt gebruiken, moet u over het volgende beschikken:
    - Een Intune- en een Azure AD Premium-abonnement (Azure Active Directory)
    - Apparaten waarop een ondersteund platform wordt uitgevoerd
    - Apparaten moeten zijn geregistreerd in Intune
    - Apparaten die zijn geregistreerd bij ofwel één gebruiker of bij een gebruiker die geen primaire gebruiker is.
    
    Zie [Aan de slag met apparaatnalevingsbeleid in Intune](../protect/device-compliance-get-started.md) voor meer informatie.

4. Vanuit [Intune](https://aka.ms/intuneportal) selecteert u **Apparaatconfiguratie** om details weer te geven over apparaatprofielen in Intune.

    ![Schermopname van het deelvenster Apparaatconfiguratie](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-04.png)
    
    Intune omvat instellingen en functies die u op verschillende apparaten binnen uw organisatie kunt in- of uitschakelen. Deze instellingen en functies worden toegevoegd aan 'configuratieprofielen'. U kunt profielen voor verschillende apparaten en verschillende platforms maken, waaronder iOS, Android en Windows. Vervolgens kunt u Intune gebruiken om het profiel op apparaten in uw organisatie toe te passen.   

    Zie [Functies-instellingen toepassen op uw apparaten met apparaatprofielen in Microsoft Intune](../configuration/device-profiles.md) voor meer informatie over apparaatconfiguratie.

5. Vanuit [Intune](https://aka.ms/intuneportal) selecteert u **Apparaten** om details weer te geven over de geregistreerde apparaten van uw Intune-tenant. Als u met een nieuwe Intune-lijst begint, hebt u nog geen geregistreerde apparaten.

    ![Schermopname van het deelvenster voor apparaatregistratie](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-05.png)

    Het deelvenster **Apparaten** biedt details over de geregistreerde apparaten van uw tenant. U kunt op **Alle apparaten** klikken om een lijst met apparaten voor uw Intune-tenant weer te geven.

6. Vanuit [Intune](https://aka.ms/intuneportal) selecteert u **Client-apps** om de installatiestatus van de app weer te geven.

    ![Schermopname van het deelvenster Client-apps](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-06.png)

    U kunt, als IT-beheerder, Microsoft Intune gebruiken om de client-apps te beheren die de werknemers van uw bedrijf gebruiken. Deze functionaliteit is een aanvulling op het beheren van apparaten en beschermen van gegevens. Een van de prioriteiten van een beheerder is om ervoor te zorgen dat eindgebruikers toegang hebben tot de apps die ze nodig hebben voor hun werk. Verder wilt u misschien apps toewijzen en beheren op apparaten die niet bij Intune zijn geregistreerd. Intune biedt een scala aan mogelijkheden om u te helpen de benodigde apps op de gekozen apparaten te krijgen. Zie [Apps toevoegen aan Microsoft Intune](../apps/apps-add.md) en [Apps toewijzen aan groepen met Microsoft Intune](../apps/apps-deploy.md) voor meer informatie over het toevoegen en toewijzen van apps.

7. Vanuit [Intune](https://aka.ms/intuneportal) selecteert u **Voorwaardelijke toegang** om details weer te geven over toegangsbeleid.

    ![Schermopname van het deelvenster Voorwaardelijke toegang](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-07.png)

    Voorwaardelijke toegang verwijst naar de manieren waarop u de apparaten en apps kunt beheren die toestemming hebben om verbinding te maken met uw e-mail- en bedrijfsgegevens. Zie [Wat is voorwaardelijke toegang?](../protect/conditional-access.md) voor meer informatie over apparaat- en appgebaseerde voorwaardelijke toegang en algemene scenario's voor het gebruiken van voorwaardelijke toegang met Intune.

8. Vanuit [Intune](https://aka.ms/intuneportal) selecteert u **Gebruikers** om details weer te geven over de gebruikers die u in Intune hebt opgenomen. Deze gebruikers vormen het personeel van uw bedrijf.

    ![Schermopname van het deelvenster Gebruikers](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-08.png)

    U kunt gebruikers rechtstreeks toevoegen aan Intune of gebruikers synchroniseren via uw on-premises Active Directory. Zodra gebruikers zijn toegevoegd, kunnen ze apparaten registreren en hebben ze toegang tot bedrijfsresources. U kunt gebruikers ook extra machtigingen geven voor toegang tot Intune. Zie [Gebruikers toevoegen en beheerdersmachtigingen geven in Intune](users-add.md) voor meer informatie.

9. Vanuit [Intune](https://aka.ms/intuneportal) selecteert u **Groepen** om details weer te geven over de Azure AD-groepen (Azure Active Directory) in Intune. Als Intune-beheerder gebruikt u groepen om apparaten en gebruikers te beheren.

    ![Schermopname van het deelvenster Groepen](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-09.png)

    U kunt groepen instellen voor uw organisatiebehoeften. Maak groepen om gebruikers of apparaten in te delen op geografische locatie, afdeling of hardwarekenmerken. Gebruik groepen voor het beheren van taken op schaal. U kunt zo bijvoorbeeld beleidsregels instellen voor een groot aantal gebruikers tegelijk of apps implementeren op een reeks apparaten. Zie [Groepen toevoegen om gebruikers en apparaten te organiseren](../groups-add.md) voor meer informatie over groepen.

10. Vanuit [Intune](https://aka.ms/intuneportal) selecteert u **Help en ondersteuning** als u hulp nodig hebt. Als IT-beheerder kunt u de optie **Help en ondersteuning** gebruiken om oplossingen te zoeken en te bekijken en om een online-ondersteuningsticket voor Intune in te dienen. 

    ![Schermopname van het deelvenster Help en ondersteuning](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-10.png)

    Als u een ondersteuningsticket wilt maken, moet in Azure Active Directory aan uw account een beheerdersrol zijn toegewezen. Beheerdersrollen zijn onder andere **Intune-beheerder**, **Algemene beheerder** en **Servicebeheerder**. Zie [Ondersteuning voor Microsoft Intune krijgen](../get-support.md) voor meer informatie.

11. Vanuit [Intune](https://aka.ms/intuneportal) selecteert u **Tenantstatus** om details weer te geven over uw Intune-tenant.

    ![Schermopname van het deelvenster Tenantstatus](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-11.png)

    Details over de tenantstatus zijn onder andere connectorstatus, Status van Intune-service en Intune-nieuws. Als er zich problemen voordoen met uw tenant of met Intune zelf, vindt u meer informatie in het deelvenster **Tenantstatus**. Zie [Status van Intune-tenant](../tenant-status.md) voor meer informatie.

12. Vanuit [Intune](https://aka.ms/intuneportal) selecteert u **Problemen oplossen** voor een snelkoppeling naar tips voor probleemoplossing. Hier kunt u ook ondersteuning aanvragen of de status van Intune controleren. Deze informatie is specifiek voor de door u geselecteerde Intune-gebruiker.

    ![Schermopname van het deelvenster Probleemoplossing](./media/tutorial-walkthrough-intune-portal/tutorial-walkthrough-intune-portal-12.png)

Zie [De portal voor probleemoplossing gebruiken om gebruikers in uw bedrijf te helpen](../help-desk-operators.md) voor meer informatie over probleemoplossing met Intune.

## <a name="configure-the-azure-portal"></a>Azure Portal configureren

In Azure kunt u de weergave van de portal aanpassen en configureren.

### <a name="change-the-sidebar"></a>De zijbalk wijzigen

In de **zijbalk** aan de linkerzijde van de Azure Portal ziet u een lijst van alle beschikbare Azure-services. U kunt de standaardweergave deze uitgebreide lijst zo wijzigen dat de voor u belangrijkste services continu worden weergegeven. In de onderstaande informatie wordt Intune als voorbeeld van een service gebruikt die boven aan de lijst moet worden toegevoegd.

![Een gebruiker zoekt in de lijst Meer services naar Microsoft Intune.](./media/tutorial-walkthrough-intune-portal/azure-add-intune1.png)

1. Selecteer **Alle services** in de zijbalk links op de pagina.
2. Zoek in het filtervak naar **Intune**.
3. Selecteer het **sterretje** om Intune onder aan uw lijst met favoriete services toe te voegen.
4. Beweeg de muisaanwijzer over de Intune-service. Selecteer Intune met de **drie verticale stippen** rechts van de servicenaam en verplaats de service.

### <a name="change-the-dashboard"></a>Het dashboard wijzigen

Standaard wordt het **dashboard** geopend. Op deze pagina kunt u uw tegels aanpassen, zodat de informatie wordt weergegeven die het meest relevant voor u is.

![Een afbeelding van het generieke nieuwe dashboard. Links wordt de zijbalk met alle services weergegeven en in het midden wordt het hoofddashboard weergegeven. De knoppen voor het wijzigen van het dashboard bevinden zich aan de bovenkant. Ook zijn er tegels die toegang bieden tot alle resources, beknopte zelfstudies, de servicestatus en de Azure-marketplace.](./media/tutorial-walkthrough-intune-portal/azure-default-dashboard.png)

Selecteer de knop **Dashboard bewerken** om uw huidige dashboard te wijzigen. Als u uw standaarddashboard niet wilt wijzigen, kunt u ook een **Nieuw dashboard** maken. Als u een nieuw dashboard maakt, ziet u een leeg privédashboard met de **Tegelgalerie**. Hier kunt u tegels toevoegen of opnieuw rangschikken. U kunt tegels zoeken op basis van de **algemene** categorie, het **type**, door te **zoeken** en door middel van een **resourcegroep** of **tag**.

U kunt ook rechtstreeks tegels aan uw dashboard toevoegen door op een willekeurige knop met het **beletselteken** en vervolgens op **Vastmaken aan dashboard** te klikken.

![Een close-up van de locatie Gebruikers en groepen > Alle groepen in Intune. De optie 'Vastmaken aan dashboard' is uiterst rechts van de groep zichtbaar.](./media/tutorial-walkthrough-intune-portal/azure-pin-to-dashboard.png)

Deze mogelijkheid is relevanter wanneer u eenmaal meer inhoud, zoals groepen en gebruikers, aan Intune hebt toegevoegd.

## <a name="next-steps"></a>Volgende stappen

Als u aan de slag wilt gaan in Microsoft Intune, doorloopt u de Intune Quickstarts door eerst een gratis Intune-account in te stellen.

> [!div class="nextstepaction"]
> [Quickstart: Microsoft Intune gratis proberen](free-trial-sign-up.md)
