---
title: Uw Lookout-integratie instellen met Intune
titlesuffix: Azure portal
description: Uw Lookout-abonnement instellen met Intune
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5b0d7644-3183-45ba-a165-0d82d70cb71e
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6b5d9a5fafdec0750e943dcfb3542d4dfd69f6ae
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="set-up-your-lookout-mobile-threat-defense-integration-with-intune"></a>Integratie van Lookout Mobile Threat Defense met Intune instellen

Voor het instellen van uw Lookout Mobile Threat Defense-abonnement moeten de volgende stappen worden uitgevoerd:

| #        |Stap  |
| ------------- |:-------------|
| 1 | [Azure AD-gegevens verzamelen](#collect-azure-ad-information) |
| 2 | [Uw abonnement configureren](#configure-your-subscription) |
| 3 | [Registratiegroepen configureren](#configure-enrollment-groups) |
| 4 | [Statussynchronisatie configureren](#configure-state-sync) |
| 5 | [Foutenrapport met informatie over geadresseerden configureren](#configure-error-report-email-recipient-information) |
| 6 | [Registratie-instellingen configureren](#configure-enrollment-settings) |
| 7 | [E-mailmeldingen configureren](#configure-email-notifications) |
| 8 | [Bedreigingsclassificatie configureren](#configure-threat-classification) |
| 9 | [Registratie bewaken](#watching-enrollment) |

> [!IMPORTANT]
> Het is niet mogelijk om een bestaande Lookout Mobile Endpoint Security-tenant die nog niet is gekoppeld aan uw Azure AD-tenant, te gebruiken voor de integratie met Azure AD en Intune. Neem contact op met de Lookout-ondersteuning om een nieuwe Lookout Mobile Endpoint Security-tenant te maken. Gebruik de nieuwe tenant voor de onboarding van Azure AD-gebruikers.

## <a name="collect-azure-ad-information"></a>Azure AD-gegevens verzamelen
Uw Lookout Mobility Endpoint Security-tenant wordt gekoppeld aan uw Azure AD-abonnement voor integratie van Lookout met Intune. Voor het inschakelen van uw abonnement voor de Lookout Mobile Threat Defense-service heeft Lookout-ondersteuning (enterprisesupport@lookout.com) de volgende informatie nodig:

* **Azure AD-tenant-id**
* **Azure AD-groepsobject-id** voor **volledige** toegang tot de Lookout-console
* **Azure AD-groepsobject-id** voor **beperkte** toegang tot de Lookout-console (optioneel)

Gebruik de volgende stappen om de gegevens te verzamelen die u aan het Lookout-ondersteuningsteam moet geven.

1. Meld u aan bij [Azure Portal](https://portal.azure.com) en selecteer uw abonnement. 

2. Wanneer u de naam van uw abonnement kiest, bevat de resulterende URL de abonnements-id.  Als u problemen hebt met het vinden van uw abonnements-id, kunt u dit [artikel van Microsoft Ondersteuning](https://support.office.com/article/Find-your-Office-365-tenant-ID-6891b561-a52d-4ade-9f39-b492285e2c9b) tips lezen over het vinden van uw abonnements-id.

3. Zoek uw Azure AD-groeps-id op. De Lookout-console ondersteunt twee toegangsniveaus:  
  * **Volledige toegang:** de Azure AD-beheerder kan een groep maken met gebruikers die volledige toegang hebben en eventueel een groep maken voor gebruikers met beperkte toegang.  Alleen gebruikers in deze groepen kunnen zich aanmelden bij de **Lookout-console**.
  * **Beperkte toegang:** de gebruikers in deze groep hebben geen toegang tot verschillende configuratie- en inschrijvingsgerelateerde modules van de Lookout-console, en hebben alleen-lezentoegang tot de module **Beveiligingsbeleid** van de Lookout-console.  

    > [!TIP] 
    > Lees [dit artikel](https://personal.support.lookout.com/hc/articles/114094105653) op de Lookout-website voor meer informatie over de machtigingen.

    > [!NOTE] 
    > De **groepsobject-id** bevindt zich op de pagina **Eigenschappen** van de groep in de **Azure AD-beheerportal**.

4. Wanneer u deze informatie hebt verzameld, neemt u contact op met de Lookout-ondersteuning (e-mail: enterprisesupport@lookout.com) . Met behulp van de gegevens die u hebt verzameld, zal de Lookout-ondersteuning in samenwerking met uw primaire contactpersoon zorgen voor onboarding van uw abonnement en uw Lookout Enterprise-account maken.

## <a name="configure-your-subscription"></a>Uw abonnement configureren

1. Nadat Lookout-ondersteuning uw Lookout Enterprise-account heeft gemaakt, ontvangt de primaire contactpersoon van uw bedrijf een e-mailbericht van Lookout met een koppeling naar de aanmeldings-URL: https://aad.lookout.com/les?action=consent.

2.  De eerste aanmelding bij de Lookout-console moet worden uitgevoerd met een gebruikersaccount met de Azure AD-rol van globale beheerder om uw Azure AD-tenant te registreren. Daarna is voor aanmelding niet meer dit niveau van Azure AD-bevoegdheden nodig. We wordt een instemmingspagina weergegeven. Kies **Accepteren** om de registratie te voltooien. Zodra u dat hebt gedaan, wordt u omgeleid naar de Lookout-console.

    ![Schermafbeelding van de allereerste aanmeldingspagina van de Lookout-console](./media/lookout_mtp_initial_login.png)
    > [!NOTE] 
    > Zie [integratieproblemen met Lookout oplossen](https://docs.microsoft.com/intune/troubleshoot/troubleshooting-lookout-integration) voor meer informatie over problemen met aanmelden.

3.  Ga in de [Lookout-console](https://aad.lookout.com) naar de module **Systeem**, kies het tabblad **Connectors** en selecteer **Intune**.

    ![schermopname van de Lookout-console waarin het tabblad Connectors is geopend en de Intune-optie is gemarkeerd](./media/lookout_mtp_setup-intune-connector.png)

4.  Ga naar **Connectors** > **Verbindingsinstellingen** en geef de **heartbeatfrequentie** in minuten op.

    ![schermopname van het tabblad Verbindingsinstellingen waarop de heartbeatfrequentie is geconfigureerd](./media/lookout-mtp-connection-settings.png)

## <a name="configure-enrollment-groups"></a>Registratiegroepen configureren
1. Maak als aanbevolen procedure een Azure AD-beveiligingsgroep in de [Azure AD-beheerportal](https://manage.windowsazure.com) met een klein aantal gebruikers om de Lookout-integratie te testen.

    > [!NOTE] 
    > Alle door Lookout ondersteunde en in Intune geregistreerde apparaten van gebruikers in een registratiegroep in Azure AD die worden geïdentificeerd en ondersteund, worden geregistreerd en komen in aanmerking voor activering in de Lookout MTD-console.

2. Ga in de [Lookout-console](https://aad.lookout.com) naar de module **Systeem**, kies het tabblad **Connectors** en selecteer **Registratiebeheer** voor het definiëren van een groep gebruikers van wie de apparaten moeten worden geregistreerd bij Lookout. Voeg de Azure AD-beveiligingsgroep **Weergavenaam** toe voor registratie.

    ![schermopname van de registratiepagina van de Intune-connector](./media/lookout-mtp-enrollment.png)

    >[!IMPORTANT]
    > De **Weergavenaam** is hoofdlettergevoelig zoals weergegeven in de **Eigenschappen** van de beveiligingsgroep in de Azure-portal. Zoals de onderstaande afbeelding laat zien, heeft de **Weergavenaam** van de beveiligingsgroep hoofd- en kleine letters terwijl de titel alleen uit kleine letters bestaat. Stel in de Lookout-console het lettergebruik van de **Weergavenaam** in voor de beveiligingsgroep.
    >![schermopname van de Azure-portal, Azure Active Directory-service, eigenschappenpagina](./media/aad-group-display-name.png)

    >[!NOTE] 
    >U kunt het interval voor het controleren op nieuwe apparaten het best op de standaard 5 minuten laten staan. Huidige beperkingen: **Lookout kan geen weergavenamen van groepen valideren:** Zorg ervoor dat het veld **WEERGAVENAAM** veld in Azure Portal exact overeenkomt met de naam van de Azure AD-beveiligingsgroep. **Het maken van geneste groepen wordt niet ondersteund:**  In Lookout gebruikte Azure AD-beveiligingsgroepen mogen alleen gebruikers bevatten. Ze kunnen geen andere groepen bevatten.

3.  Nadat een groep is toegevoegd, wordt het apparaat in Lookout geactiveerd de eerstvolgende keer dat een gebruiker de Lookout for Work-app op een ondersteund apparaat opent.

4.  Als u tevreden bent met de resultaten, breidt u de registratie uit naar andere gebruikersgroepen.

## <a name="configure-state-sync"></a>Statussynchronisatie configureren
Geef bij de optie **Statussynchronisatie** het type gegevens op dat naar Intune moet worden verzonden.  Zowel de apparaatstatus als de bedreigingsstatus zijn vereist voor een goede integratie van Lookout met Intune. Deze instellingen worden standaard ingeschakeld.

## <a name="configure-error-report-email-recipient-information"></a>Foutenrapport met informatie over geadresseerden configureren
Voer bij de optie **Foutbeheer** het e-mailadres in waarnaar het foutenrapport moet worden verzonden.

![schermopname van de foutenbeheerpagina van de Intune-connector](./media/lookout-mtp-connector-error-notifications.png)

## <a name="configure-enrollment-settings"></a>Registratie-instellingen configureren
Geef in de module **Systeem** op de pagina **Connectors** het aantal dagen op voordat een apparaat wordt beschouwd als niet-verbonden.  Niet-verbonden apparaten worden als niet-compatibel beschouwd en krijgen geen toegang meer tot uw bedrijfstoepassingen op basis van de Intune-beleidsregels voor voorwaardelijke toegang. U kunt waarden tussen 1 en 90 dagen opgeven.

![Inschrijvingsinstellingen voor Lookout](./media/lookout-console-enrollment-settings.png)

## <a name="configure-email-notifications"></a>E-mailmeldingen configureren
Als u e-mailwaarschuwingen voor bedreigingen wilt ontvangen, meldt u zich aan bij de [Lookout-console](https://aad.lookout.com) met het gebruikersaccount waarnaar meldingen moeten worden verzonden. Kies op het tabblad **Voorkeuren** van de **Systeem**-module de bedreigingsniveaus waarbij meldingen moeten worden verzonden en stel ze in op **AAN**. Sla de wijzigingen op.

![schermopname van de pagina Voorkeuren met het gebruikersaccount weergegeven](./media/lookout-mtp-email-notifications.png) Als u geen e-mailmeldingen meer wilt ontvangen, stelt u de meldingen in op **UIT** en slaat u de wijzigingen op.

### <a name="configure-threat-classification"></a>Bedreigingsclassificatie configureren
Met Lookout Mobile Threat Defense worden mobiele bedreigingen geclassificeerd in verschillende typen. Aan de [bedreigingsclassificaties van Lookout](http://personal.support.lookout.com/hc/articles/114094130693) zijn standaardrisiconiveaus gekoppeld. Deze kunnen op elk gewenst moment worden aangepast aan de vereisten van uw bedrijf.

![schermopname van de beleidspagina met bedreiging en classificaties](./media/lookout-mtp-threat-classification.png)

>[!IMPORTANT]
> Risiconiveaus zijn een belangrijk aspect van Mobile Threat Defense omdat door de Intune-integratie tijdens runtime wordt berekend in hoeverre het apparaat compatibel is op basis van deze risiconiveaus. De Intune-beheerder stelt een beleidsregel in om een apparaat te identificeren als niet-compatibel als het een actieve bedreiging heeft met een minimumniveau van **Hoog**, **Gemiddeld** of **Laag**. Het bedreigingsclassificatiebeleid in Lookout Mobile Threat Defense staat rechtstreeks aan de basis van de berekening van de apparaatcompatibiliteit in Intune.

## <a name="watching-enrollment"></a>Registratie bewaken
Wanneer de instelling is voltooid, wordt Azure AD met Lookout Mobile Threat Defense gecontroleerd op apparaten die met de opgegeven inschrijvingsgroepen overeenkomen.  In de module Apparaten vindt u informatie over de apparaten die zijn geregistreerd.  De initiële status van apparaten wordt weergegeven als In behandeling.  De apparaatstatus wordt gewijzigd nadat de Lookout for Work-app op het apparaat is geïnstalleerd, geopend en geactiveerd.  Zie het onderwerp [De Lookout for Work-app configureren en implementeren](mtd-apps-ios-app-configuration-policy-add-assign.md) voor meer informatie over het pushen van de Lookout for Work-app naar het apparaat.

## <a name="next-steps"></a>Volgende stappen

[Lookout-apps instellen](mtd-apps-ios-app-configuration-policy-add-assign.md)
