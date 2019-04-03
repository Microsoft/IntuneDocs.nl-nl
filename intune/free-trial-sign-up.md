---
title: 'Snelstartgids: Microsoft Intune gratis proberen'
titleSuffix: ''
description: In deze snelstartgids maakt u een gratis proefabonnement, leert u de ondersteunde configuraties en netwerkvereisten kennen en kunt u (optioneel) uw domeinnaam configureren.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/11/2019
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 195931c0-8208-43bd-b0af-b1f8e469a32c
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 63f9ef266c9a5754d5de57232a8f7bc41a6c5777
ms.sourcegitcommit: 79baf89e4a7a7b1cecb8ccf5cb976736ae6a7286
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2019
ms.locfileid: "58871392"
---
# <a name="quickstart-try-microsoft-intune-for-free"></a>Quickstart: Microsoft Intune gratis proberen 

Met Microsoft Intune kun u de bedrijfsgegevens van uw werknemers beschermen door middel van het beheer van apparaten en apps. In deze snelstartgids maakt u een gratis abonnement om Intune in een testomgeving te proberen.

Intune biedt Mobile Device Management (MDM) en Mobile Application Management (MAM) via een veilige, op de cloud gebaseerde service die wordt beheerd met behulp van Microsoft Azure Portal. Met behulp van Intune kunt u ervoor zorgen dat de bedrijfsresources van uw werknemers (gegevens, apparaten en apps) op de juiste manier worden geconfigureerd, geopend en bijgewerkt, zodat u aan het nalevingsbeleid en de vereisten van uw bedrijf voldoet. 

## <a name="prerequisites"></a>Vereisten
Bekijk de volgende vereisten voordat u Microsoft Intune instelt:

   - [Ondersteunde besturingssystemen en browsers](supported-devices-browsers.md) 
   - [Netwerkconfiguratievereisten en bandbreedte](network-bandwidth-use.md)

## <a name="sign-up-for-a-microsoft-intune-free-trial"></a>Registreren voor een gratis proefversie van Microsoft Intune

U mag Intune 30 dagen gratis proberen. Als u al een werk- of schoolaccount hebt **meld u dan aan** met dat account en voeg Intune toe aan uw abonnement. Anders kunt u zich **registreren** voor een nieuw account om Intune te gebruiken voor uw organisatie.

> [!IMPORTANT]
> U kunt een bestaand werk- of schoolaccount niet combineren nadat u zich hebt aangemeld voor een nieuw account.

1. Ga naar de pagina [Microsoft Intune Trial](https://go.microsoft.com/fwlink/?linkid=2019088) en vul het formulier in.

    ![Schermafbeelding van de registratiewebpagina van de evaluatieversie van het Microsoft Intune-account](./media/account-sign-up-site-full-browser.png)

    Als de landinstellingen voor de meeste IT-activiteiten en van de meeste gebruikers afwijken van die van u, kunt u de desbetreffende landinstellingen selecteren onder **Land of regio**. Azure gebruikt uw regionale informatie om u de juiste services te bieden. Deze instelling kan later niet worden gewijzigd.

2. Maak een account met behulp van uw bedrijfsnaam gevolgd door **.onmicrosoft.com**. 

    ![Schermopname van het proces voor nieuwe referenties voor het Intune-account](./media/account-sign-up-site-user-id.png)

    Als uw organisatie een eigen aangepast domein heeft dat u wilt gebruiken zonder **.onmicrosoft.com**, kunt u dit wijzigen in het Microsoft 365-beheercentrum dat later in dit artikel wordt beschreven.

3. Bekijk uw nieuwe accountinformatie aan het einde van het aanmeldingsproces.

    ![Afbeelding van accountgegevens](./media/intune-end-of-sign-up-process.png) 

## <a name="sign-in-to-the-azure-portal"></a>Aanmelden bij Azure Portal

1. Open een nieuw browservenster en voer **https://portal.azure.com** in de adresbalk in. 
2. Gebruik de referenties die in de bovenstaande stappen hebt gekregen om u aan te melden.

    ![Afbeelding van de aanmeldingspagina van Azure Portal](./media/azure-portal-signin.png)

3. Als u Microsoft Intune in de Azure-portal wilt weergeven, selecteert u **Alle services** in de zijbalk links op de pagina.
4. Zoek in het filtervak naar **Microsoft Intune** en selecteer dit.
5. Selecteer het **sterretje** om Intune onder aan uw lijst met favoriete services toe te voegen en het Intune-dashboard te openen.

Wanneer u zich aanmeldt voor een proefversie, ontvangt u tevens een e-mailbericht met gegevens over uw account op het e-mailadres dat u hebt opgegeven tijdens het aanmeldingsproces. In deze e-mail wordt bevestigd dat uw proefversie actief is.

> [!TIP]
> Als u werkt met Azure Portal verkrijgt u mogelijk betere resultaten met een browser in de reguliere modus in plaats van de privémodus.

## <a name="set-the-mdm-authority-to-intune"></a>De MDM-instantie instellen op Intune

Wanneer u zich hebt aangemeld bij Azure Portal en u Intune hebt geselecteerd, ziet u mogelijk een oranje banner die aangeeft dat u de MDM-instantie nog niet hebt ingesteld. Met de instantie voor het beheer van mobiele apparaten (MDM) wordt bepaald hoe u uw apparaten beheert. De MDM-instantie moet worden ingesteld voordat gebruikers apparaten voor beheer kunnen inschrijven.

Volg deze stappen om de MDM-instantie op Intune in te stellen.

1. Open een nieuw browservenster en voer **https://portal.azure.com** in de adresbalk in. 
2. Kies **Alle services** > **Microsoft Intune**.
3. Selecteer de banner waarin staat dat u apparaatbeheer nog niet hebt ingeschakeld. Als u de banner niet direct ziet, selecteert u **Apparaatinschrijving**. De blade **MDM-instantie kiezen** wordt weergegeven als u apparaatbeheer nog niet hebt ingeschakeld.

    > [!NOTE]
    > Als u de MDM-instantie hebt ingesteld, wordt de waarde van de MDM-instantie weergegeven op de blade **Apparaatinschrijving**. De oranje banner wordt alleen weergegeven als u de MDM-instantie nog niet hebt ingesteld. 

    ![Afbeelding van de blade MDM-instantie kiezen](./media/choose-mdm-authority.png) 

4. Als de MDM-instantie niet is ingesteld, stelt u onder **MDM-instantie kiezen** uw MDM-instantie in op **Intune MDM-instantie**.

Zie [De instantie voor het beheer van mobiele apparaten instellen](mdm-authority-set.md) voor meer informatie over de MDM-instantie.

## <a name="configure-your-custom-domain-name-optional"></a>Uw aangepaste domeinnaam configureren (optioneel)

Zoals hierboven is gemeld, kunt u de domeinnaam wijzigen in het Microsoft 365-beheercentrum als uw organisatie een eigen aangepast domein heeft dat u wilt gebruiken zonder **.onmicrosoft.com**. U kunt de aangepaste domeinnaam toevoegen, verifiëren en configureren met behulp van de volgende stappen.  

> [!IMPORTANT]
> U kunt het gedeelte **onmicrosoft.com** van de *initiële* domeinnaam niet wijzigen of verwijderen. U kunt *aangepaste* domeinnamen wel toevoegen, verifiëren of verwijderen met Intune om uw bedrijfsidentiteit helder te houden. Zie [Een aangepaste domeinnaam configureren](custom-domain-name-configure.md) voor meer informatie.

1. Ga naar het [Microsoft 365-beheercentrum](https://admin.microsoft.com) en meld u aan met uw beheerdersaccount.

2. Kies in het navigatievenster **Configuratie** > **Domeinen** > **Domein toevoegen**.

3. Typ uw aangepaste domeinnaam. Selecteer vervolgens **Volgende**.

   ![Schermopname van Microsoft 365-beheercentrum - domein toevoegen](./media/domain-custom-add.png)

4. Bevestig dat u de eigenaar van het domein bent dat u in de vorige stap hebt opgegeven. 
    
    Wanneer u de optie **Code verzenden via e-mail** selecteert, wordt er een e-mail naar de geregistreerde contactpersoon van uw domein gestuurd. Nadat u de e-mail hebt ontvangen, kopieert u de code en voert u deze in bij het veld **Typ hier uw verificatiecode**. Als de verificatiecodes overeenkomen, wordt het domein toegevoegd aan uw tenant. Het e-mailadres dat wordt weergegeven, ziet er mogelijk niet bekend uit. Sommige registratieservices verbergen het echte e-mailadres. Het e-mailadres kan bovendien anders zijn dan is opgegeven tijdens de registratie van het domein.

   ![Schermopname van Microsoft 365-beheercentrum - domein verifiëren](./media/domain-custom-verify.png)

   > [!NOTE]
   > Voor meer informatie over de verificatie van TXT records raadpleegt u [DNS-records maken bij DNS-hostingproviders voor Office 365](https://support.office.com/article/Create-DNS-records-at-any-DNS-hosting-provider-for-Office-365-7B7B075D-79F9-4E37-8A9E-FB60C1D95166).

## <a name="admin-experiences"></a>Ervaringen van beheerders

Er zijn twee portals die u kunt gebruiken:
- Het Intune-dashboard in Azure ([portal.azure.com](https://portal.azure.com)) is de locatie waar u de [mogelijkheden van Intune](what-is-intune.md) kunt bekijken. Doorgaans voert u uw werkzaamheden uit in het Intune-dashboard.
- Het Microsoft 365-beheercentrum ([admin.microsoft.com](https://admin.microsoft.com)) is de locatie waar u gebruikers kunt toevoegen en beheren als u Azure Active Directory hiervoor niet gebruikt. U kunt ook andere aspecten van uw account beheren, zoals facturering en ondersteuning.

## <a name="next-steps"></a>Volgende stappen

In deze snelstartgids maakt u een gratis abonnement om Intune in een testomgeving te proberen. Raadpleeg [Intune instellen](setup-steps.md) voor meer informatie over het instellen van Intune.

Als u deze reeks snelstartgidsen voor Intune wilt volgen, kunt u doorgaan met de volgende snelstartgids.

> [!div class="nextstepaction"]
> [Quickstart: Een gebruiker maken en vervolgens een licentie aan deze gebruiker toewijzen](quickstart-create-user.md)
