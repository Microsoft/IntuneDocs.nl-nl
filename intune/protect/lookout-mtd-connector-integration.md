---
title: Uw Lookout-integratie instellen met Microsoft Intune
titleSuffix: Microsoft Intune
description: Meer informatie over de integratie van Intune met Lookout Mobile Endpoint Security als Mobile Threat Defense-oplossing om toegang tot uw bedrijfsresources met mobiele apparaten te beheren.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/11/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5b0d7644-3183-45ba-a165-0d82d70cb71e
ms.reviewer: davera
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: be2e9371288961d0afdf7ad6e8cfec8f734087f6
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71721289"
---
# <a name="set-up-lookout-mobile-endpoint-security-integration-with-intune"></a>Lookout Mobile Endpoint Security-integratie met Intune instellen
Met een omgeving die aan de [vereisten](lookout-mobile-threat-defense-connector.md#prerequisites) voldoet, kunt u Lookout Mobile Endpoint Security integreren met Intune. De informatie in dit artikel helpt u bij het instellen van de integratie en het configureren van belangrijke instellingen in Lookout voor gebruik met Intune.  

> [!IMPORTANT]
> Het is niet mogelijk om een bestaande Lookout Mobile Endpoint Security-tenant die nog niet is gekoppeld aan uw Azure AD-tenant, te gebruiken voor de integratie met Azure AD en Intune. Neem contact op met de Lookout-ondersteuning om een nieuwe Lookout Mobile Endpoint Security-tenant te maken. Gebruik de nieuwe tenant voor de onboarding van Azure AD-gebruikers.

## <a name="collect-azure-ad-information"></a>Azure AD-gegevens verzamelen  
Om Lookout met Intune te integreren koppelt u uw Lookout Mobility Endpoint Security-tenant aan uw AAD-abonnement (Azure Active Directory).

Om de integratie van uw Lookout Mobile Endpoint Security-abonnement met Intune in te schakelen, geeft u de volgende informatie aan de ondersteuning van Lookout (enterprisesupport@lookout.com):  

- **Directory-id van de Azure AD-tenant**  

- **Azure AD-groepsobject-id** voor de groep met **volledige** toegang tot de Lookout MES-console (Mobile Endpoint Security).  
  U maakt deze gebruikersgroep in Azure AD voor gebruikers die *volledige toegang* hebben om zich aan te melden bij de **Lookout-console**. Gebruikers moeten lid zijn van deze groep of van de optionele groep met *beperkte toegang* om zich aan te kunnen melden bij de Lookout-console. 

- **Azure AD-groepsobject-id** voor de groep met **beperkte** toegang tot de Lookout MES-console *(optionele groep)* . 
  U kunt deze optionele gebruikersgroep in Azure AD maken voor gebruikers die geen toegang mogen hebben tot verschillende aan de configuratie en enrollment gerelateerde modules van de Lookout-console. In plaats daarvan hebben deze gebruikers alleen-lezentoegang tot de module **Beveiligingsbeleid** van de Lookout-console. Gebruikers moeten lid zijn van deze optionele groep of van de verplichte groep met *volledige toegang* om zich aan te kunnen melden bij de Lookout-console.

 > [!TIP] 
 > Lees [dit artikel](https://personal.support.lookout.com/hc/articles/114094105653) op de Lookout-website voor meer informatie over de machtigingen.

### <a name="collect-information-from-azure-ad"></a>Gegevens verzamelen van Azure AD 

1. Meld u aan bij de [Azure-portal](https://portal.azure.com) met een account voor globale beheerders.

2. Ga naar **Azure Active Directory** > **Eigenschappen** en zoek uw **map-id**. Gebruik de knop *Kopiëren* om de map-id te kopiëren en sla deze vervolgens op in een tekstbestand.

   ![Azure AD-eigenschappen](./media/lookout-mtd-connector-integration/azure-ad-properties.png)  

3. Zoek vervolgens de Azure AD-groeps-id voor de accounts die u gebruikt om Azure AD-gebruikers toegang te verlenen tot de Lookout-console. Eén groep is voor *volledige toegang*, en de tweede groep, voor *beperkte toegang*, is optioneel. Om de *object-id* voor elk account te achterhalen, gaat u als volgt te werk:  
   1. Ga naar **Azure Active Directory** > **Groepen** om het deelvenster *Groepen - Alle groepen* te openen.  

   2. Selecteer de door u gemaakte groep met *volledige toegang* om het bijbehorende deelvenster *Overzicht* te kunnen openen.  

   3. Gebruik de knop *Kopiëren* om de object-id te kopiëren en sla deze vervolgens op in een tekstbestand.  

   4. Als u een groep met *beperkte toegang* gebruikt, herhaalt u het proces voor deze groep.  

      ![Object-id van Azure AD-groep](./media/lookout-mtd-connector-integration/azure-ad-group-id.png)  

   Nadat u deze informatie hebt verzameld, neemt u contact op met de Lookout-ondersteuning (e-mailadres: enterprisesupport@lookout.com). Met behulp van de gegevens die u verstrekt zal de Lookout-ondersteuning in samenwerking met uw primaire contactpersoon uw abonnement onboarden en uw Lookout Enterprise-account maken.  

## <a name="configure-your-lookout-subscription"></a>Uw Lookout-abonnement configureren  
Nadat Lookout-ondersteuning uw Lookout Enterprise-account heeft gemaakt, stuurt deze een e-mail naar de primaire contactpersoon van uw bedrijf met een koppeling naar de aanmeldings-URL: https://aad.lookout.com/les?action=consent. 

### <a name="initial-sign-in"></a>Eerste aanmelding  
De eerste keer dat u zich aanmeldt bij de Lookout MES-console wordt een instemmingspagina weergegeven (https://aad.lookout.com/les?action=consent) ). Een Azure AD-hoofdbeheerder moet zich aanmelden en voor **Accepteren** kiezen. Voor volgende aanmeldingen heeft de gebruiker dit niveau van Azure AD-bevoegdheden niet nodig. 

 We wordt een instemmingspagina weergegeven. Kies **Accepteren** om de registratie te voltooien. 
   ![schermafbeelding van de pagina voor de allereerste aanmelding bij de Lookout-console](./media/lookout-mtd-connector-integration/lookout_mtp_initial_login.png)

Als u voor Accepteren kiest en toestemming geeft, wordt u doorgestuurd naar de Lookout-console.

Na het voltooien van de eerste aanmelding en het verlenen van toestemming worden gebruikers die zich aanmelden vanaf https://aad.lookout.com doorgestuurd naar de MES-console. Als er nog geen toestemming is verleend, resulteren alle aanmeldpogingen in een aanmeldingsfout.

### <a name="configure-the-intune-connector"></a>De Intune-connector configureren  
Bij de volgende procedure wordt ervan uitgegaan dat u eerder een groep in Azure AD hebt gemaakt voor het testen van uw Lookout-implementatie. De best practice is om te starten met een kleine groep gebruikers, zodat uw Lookout- en Intune-beheerders vertrouwd kunnen raken met de productintegraties. Daarna kunt u de enrollment uitbreiden naar meer gebruikersgroepen.

1. Meld u aan bij de [Lookout MES-console](https://aad.lookout.com), ga naar **Systeem** > **Connectors** en selecteer **Connector toevoegen**.  Selecteer **Intune**.

   ![Afbeelding van de Lookout-console met de Intune-optie op het tabblad Connectors](./media/lookout-mtd-connector-integration/lookout_mtp_setup-intune-connector.png)

2. In het deelvenster *Microsoft Intune* selecteert u **Verbindingsinstellingen** en geeft u de **heartbeatfrequentie** in minuten op. 

   ![Afbeelding van het tabblad Verbindingsinstellingen waarop de heartbeatfrequentie is geconfigureerd](./media/lookout-mtd-connector-integration/lookout-mtp-connection-settings.png)

3. Selecteer **Registratiebeheer** en geef bij **Use the following Azure AD security groups to identify devices that should be enrolled in Lookout for Work** (De volgende Azure AD-beveiligingsgroepen gebruiken om apparaten te identificeren die moeten zijn geregistreerd voor Lookout for Work) de *groepsnaam* van een Azure AD-groep op voor gebruik met Lookout en selecteer vervolgens **Wijzigingen opslaan**.

    ![schermopname van de registratiepagina van de Intune-connector](./media/lookout-mtd-connector-integration/lookout-mtp-enrollment.png)  

   **Over de groepen die u gebruikt**:
   - Begin als best practice met een Azure AD-beveiligingsgroep met een klein aantal gebruikers om de Lookout-integratie te testen.
   - De **groepsnaam** is hoofdlettergevoelig zoals weergegeven in de **eigenschappen** van de beveiligingsgroep in de Azure-portal.  
   - De groepen die u opgeeft voor **registratiebeheer** bepalen van welke gebruikers de apparaten worden geregistreerd bij Lookout. Wanneer een gebruiker in een registratiegroep zit, worden zijn apparaten in Azure AD geregistreerd. Deze kunnen in Lookout MES worden geactiveerd. De eerste keer dat een gebruiker de toepassing *Lookout for Work* op een ondersteund apparaat opent, wordt hij gevraagd om deze te activeren.

4. Selecteer **Statussynchronisatie** en zorg ervoor dat zowel de *apparaatstatus* als de *bedreigingsstatus* zijn ingesteld op **Aan**.  Beide zijn vereist voor een goede integratie van Lookout met Intune.  

5. Selecteer **Foutbeheer**, geef het e-mailadres op waarnaar de foutrapporten moeten worden verzonden en selecteer vervolgens **Wijzigingen opslaan**.
 
   ![schermopname van de foutenbeheerpagina van de Intune-connector](./media/lookout-mtd-connector-integration/lookout-mtp-connector-error-notifications.png)

6. Selecteer **Connector maken** om de configuratie van de connector te voltooien. Als u tevreden bent met uw resultaten, kunt u de enrollment uitbreiden naar andere gebruikersgroepen.

## <a name="configure-intune-to-use-lookout-as-a-mobile-threat-defense-provider"></a>Configureer Intune om Lookout te gebruiken als een Mobile Threat Defense-provider
Nadat u Lookout MES hebt geconfigureerd, moet u in Intune een verbinding met Lookout instellen.  

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

2. Ga naar **Apparaatcompatibiliteit** > **Mobile Threat Defense** en selecteer **Toevoegen**.

3. Gebruik in het deelvenster *Connector toevoegen* de vervolgkeuzelijst om **Lookout for Work** te selecteren.  

4. Selecteer **Maken**. Nadat de connector verbinding met Lookout MES maakt, worden de *connectorinstellingen* beschikbaar.

5. Zet **Synchronisatie van app inschakelen voor iOS-apparaten** op **Aan**. 

6. Selecteer **Opslaan** om de configuratie te voltooien.  Intune en Lookout MES zijn nu geïntegreerd en klaar voor gebruik.


## <a name="additional-settings-in-the-lookout-mes-console"></a>Aanvullende instellingen in de Lookout MES-console
Hieronder vindt u aanvullende instellingen die u in de Lookout MES-console kunt configureren.  

### <a name="configure-enrollment-settings"></a>Enrollmentinstellingen configureren
Selecteer in de Lookout MES-console achtereenvolgens **Systeem** > **Enrollment beheren** > **Enrollmentinstellingen**.  

- Geef bij **de status Niet-verbonden** het aantal dagen op voordat een niet-verbonden apparaat als zodanig wordt gemarkeerd.  

  Niet-verbonden apparaten worden als niet-compatibel beschouwd en krijgen geen toegang meer tot uw bedrijfstoepassingen op basis van de Intune-beleidsregels voor voorwaardelijke toegang. U kunt waarden tussen 1 en 90 dagen opgeven.

  ![Instellingen voor registratie van Lookout in de module Systeem](./media/lookout-mtd-connector-integration/lookout-console-enrollment-settings.png)

### <a name="configure-email-notifications"></a>E-mailmeldingen configureren
Om e-mailwaarschuwingen voor bedreigingen te ontvangen, meldt u zich aan bij de [Lookout MES-console](https://aad.lookout.com) met het gebruikersaccount waarnaar meldingen moeten worden verzonden.  

- Ga naar **Voorkeuren**, zet de meldingen die u wilt ontvangen op **AAN** en kies vervolgens voor **Opslaan** om de wijzigingen op te slaan.  

- Als u geen e-mailmeldingen meer wilt ontvangen, stelt u de meldingen in op **UIT** en slaat u de wijzigingen op.

  ![Schermopname van de pagina Voorkeuren met het gebruikersaccount weergegeven](./media/lookout-mtd-connector-integration/lookout-mtp-email-notifications.png)



## <a name="configure-threat-classifications"></a>Bedreigingsclassificaties configureren  
Met Lookout Mobile Endpoint Security worden mobiele bedreigingen geclassificeerd in verschillende typen. Aan de bedreigingsclassificaties van Lookout zijn standaardrisiconiveaus gekoppeld. De risiconiveaus kunnen op elk gewenst moment worden aangepast aan de vereisten van uw bedrijf.

Zie voor meer informatie over de bedreigingsclassificaties en het beheer van de hieraan verbonden risiconiveaus [Lookout Threat Reference](https://enterprise.support.lookout.com/hc/articles/360011812974) (Lookout-bedreigingsreferentie).

>[!IMPORTANT]
> Risiconiveaus zijn een belangrijk aspect van Mobile Endpoint Security, omdat door de Intune-integratie tijdens runtime wordt berekend in hoeverre het apparaat compatibel is op basis van deze risiconiveaus.  
> 
> De Intune-beheerder stelt een beleidsregel in om een apparaat te identificeren als niet-compatibel als het een actieve bedreiging heeft met een minimumniveau van **Hoog**, **Gemiddeld** of **Laag**. Het bedreigingsclassificatiebeleid in Lookout Mobile Endpoint Security staat rechtstreeks aan de basis van de berekening van de apparaatcompatibiliteit in Intune.  

## <a name="monitor-enrollment"></a>Enrollment bewaken
Nadat de instelling is voltooid, wordt Azure AD met Lookout Mobile Endpoint Security gecontroleerd op apparaten die met de opgegeven inschrijvingsgroepen overeenkomen.  U kunt informatie over geregistreerde apparaten vinden door te gaan naar **Apparaten** in de Lookout MES-console.  
- De initiële status van apparaten is *in behandeling*.  
- De apparaatstatus wordt bijgewerkt nadat de app *Lookout for Work* op het apparaat is geïnstalleerd, geopend en geactiveerd.

Zie [Lookout for Work-apps met Intune toevoegen](mtd-apps-ios-app-configuration-policy-add-assign.md) voor meer informatie over het implementeren van de app *Lookout for Work* op het apparaat.

## <a name="next-steps"></a>Volgende stappen

[Lookout-apps instellen](mtd-apps-ios-app-configuration-policy-add-assign.md)
