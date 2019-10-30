---
title: Wandera Mobile Threat Protection-integratie met Intune instellen
titleSuffix: Intune on Azure
description: Lees hoe u de Wandera Mobile Threat Protection-oplossing instelt met Microsoft Intune om toegang tot uw bedrijfsbronnen met mobiele apparaten te beheren.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: f42acb38d84394a6b61fa16072de6320b84a67b5
ms.sourcegitcommit: 1a5b185acd27954b10b6d59409d82eb80fd71284
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2019
ms.locfileid: "72681297"
---
# <a name="integrate-wandera-mobile-threat-protection-with-intune"></a>Wandera Mobile Threat Protection integreren met Intune  

Voer de volgende stappen uit om de Wandera Mobile Threat Defense-oplossing te integreren met Intune.  

> [!NOTE]
> Deze Mobile Threat Defense-leverancier wordt niet ondersteund voor niet-ingeschreven apparaten.

## <a name="before-you-begin"></a>Voordat u begint  

Voordat u het integratieproces van Wandera met Intune begint, moet u ervoor zorgen dat u beschikt over het volgende:
- Microsoft Intune-abonnement  
- Azure Active Directory-beheerdersreferenties om de volgende machtigingen te verlenen:  
  - Aanmelden en gebruikersprofiel lezen  
  - Toegang tot de map als de aangemelde gebruiker  
  - Mapgegevens lezen  
  - Gegevens van een apparaat verzenden naar Intune  

- Wandera-abonnement:
  - Een of meer Wandera-accounts met een licentie voor EMM Connect  
  - Een account met superbeheerdersrechten in Wandera  
 
### <a name="wandera-mobile-threat-defense-app-authorization"></a>Wandera Mobile Threat Defense-appautorisatie  

Het proces voor Wandera Mobile Threat Defense-appautorisatie:  
- Sta de Wandera Mobile Threat Defense-service toe informatie met betrekking tot de status van apparaten naar Intune te verzenden.  
- Wandera wordt gesynchroniseerd met het Azure AD Enrollment-groepslidmaatschap om de database van het apparaat te vullen.  
- Sta toe dat de Wandera RADAR-beheerdersportal eenmalige aanmelding van Azure AD gebruikt.  
- Sta toe dat de Wandera Mobile Threat Defense-app zich via eenmalige aanmelding van Azure AD kan aanmelden.  


## <a name="set-up-wandera-mobile-threat-defense-integration"></a>Wandera Mobile Threat Defense-integratie instellen  
Voor het instellen van *EMM Connect* voor Wandera is een eenmalig configuratieproces nodig dat u in zowel de Intune- als de Wandera-console doorloopt. De configuratie duurt ongeveer 15 minuten. U kunt de configuratie doorlopen zonder hulp van een technisch accountvertegenwoordiger of ondersteuningsmedewerker van Wandera.  

### <a name="enable-support-for-wandera-in-intune"></a>Ondersteuning voor Wandera in Intune inschakelen
1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) en ga naar **Apparaatcompatibiliteit** > **Mobile Threat Defense**. Selecteer vervolgens **Toevoegen**.

2. Ga naar de pagina **Connector toevoegen** en gebruik de vervolgkeuzelijst om **Wandera** te selecteren. En selecteer vervolgens **Maken**.  

3. Selecteer in het Mobile Threat Defense-venster de MTD-connector **Wandera** uit de lijst met connectors om het deelvenster *Connector bewerken* te openen. Selecteer **Open de Wandera-beheerdersconsole** om [RADAR](https://radar.wandera.com/login), de beheerdersconsole van Wandera, te openen en meld u aan. 

4. Ga in de Wandera-console naar **Instellingen** > **EMM-integratie** en selecteer het tabblad **EMM Connect**. Gebruik de vervolgkeuzelijst *EMM-leverancier* om *Microsoft Intune* te selecteren.

   ![Intune selecteren](./media/wandera-mtd-connector-integration/set-up-intune-in-radar.png)

5. Selecteer **Machtiging toekennen** om een verbinding met de Intune-portal te openen. Meld u aan met uw Intune-beheerdersreferenties, selecteer het selectievakje en klik vervolgens op **Accepteren** om akkoord te gaan met de machtigingsaanvraag.  

   ![Machtigingen accepteren](./media/wandera-mtd-connector-integration/permissions.png) 

6. Wandera voltooit de verbinding en stuurt u terug naar de RADAR-beheerdersconsole. Herhaal het proces desgewenst om **toegang te verlenen** voor aanvullende configuraties.  

   ![Integraties en machtigingen](./media/wandera-mtd-connector-integration/integrations-and-permissions.png) 

7. Kopieer in de RADAR-console de naam van de **SyncOnly**-groep die onder **EMM-label** wordt weergegeven. U hebt deze naam nodig om in Intune een groep te configureren voor synchronisatie met Wandera.

   ![Synchronisatiegroep](./media/wandera-mtd-connector-integration/sync-group-name.png) 

8. Ga terug naar de [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)-console en bewerk de Wandera MTD-connector. Stel de beschikbare schakelknoppen in op **Aan** en klik op **Opslaan** om de configuratie op te slaan.  

   ![Wandera inschakelen](./media/wandera-mtd-connector-integration/enable-wandera.png) 

Intune en Wandera zijn nu verbonden.  

## <a name="configure-the-wandera-applications-and-synchronization-group"></a>De Wandera-toepassingen en de synchronisatiegroep configureren  
Als u Wandera wilt implementeren, voegt u de mobiele Wandera-apps voor de platforms die u gebruikt (iOS en Android), toe aan Intune en wijst u ze vervolgens toe aan een specifieke synchronisatiegroep: *SyncOnly*. 

De volgende secties en procedures leiden u door dit proces.

Voor meer informatie van Wandera over dit proces meldt zich aan bij Wandera [RADAR](https://radar.wandera.com/login). Ga naar **Instellingen** > **EMM-integratie**, selecteer het tabblad **App-push** en kies vervolgens **Microsoft Intune**. Het tabblad App-push wordt bijgewerkt met instructies die specifiek zijn voor Intune.  

### <a name="add-the-wandera-apps"></a>De Wandera-apps toevoegen  
Maak client-apps in Intune om de Wandera-app te implementeren op Android- en iOS-apparaten. Raadpleeg [MTD-apps toevoegen](mtd-apps-ios-app-configuration-policy-add-assign.md) voor de procedures en aangepaste details die specifiek zijn voor Wandera-apps.  

Nadat u de apps hebt gemaakt, komt u hier terug om de synchronisatiegroep te maken en de apps toe te wijzen.  


### <a name="create-the-synchronization-group-and-assign-the-apps"></a>De synchronisatiegroep maken en de apps toewijzen

1. Haal de naam van de **SyncOnly**-groep op die onder **EMM-label** wordt weergegeven in de Wandera RADAR-console. Mogelijk hebt u deze naam al ergens opgeslagen tijdens stap 7, toen u [ondersteuning voor Wandera in Intune inschakelde](#enable-support-for-wandera-in-intune). Gebruik deze naam als de naam van de groep in Intune voor Wandera-synchronisatie.  

2. Ga in de Intune-console naar **Groepen** en selecteer **Nieuwe groep**. Geef het volgende op om de synchronisatiegroep te configureren die door Wandera moet worden gebruikt:
   - **Groepstype**: **Beveiliging**
   - **Groepsnaam**: Geef de **SyncOnly**-naam op die u hebt opgehaald uit de Wandera RADAR-beheerdersconsole.

   ![De synchronisatiegroep configureren](./media/wandera-mtd-connector-integration/configure-sync-group.png)

3. Selecteer **Leden** en wijs groepen toe met de Android- en iOS-apparaten die u met Wandera wilt gebruiken.

4. Selecteer **Maken** om de groep op te slaan.

Raadpleeg [Apps implementeren](../apps/apps-deploy.md) voor meer informatie

### <a name="assign-the-wandera-apps-to-the-synchronization-group"></a>De Wandera-apps toewijzen aan de synchronisatiegroep  
Herhaal de volgende procedure voor de Wandera-app die u hebt gemaakt voor iOS en voor Android.

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973), ga naar **Client-apps** > **Apps** en selecteer de Wandera-app.  

2. Selecteer **Toewijzingen** en vervolgens **Groep toevoegen**.  

3. Selecteer in het venster *Groep toevoegen* voor *Toewijzingstype* de optie **Vereist**.

4. Selecteer vervolgens **Opgenomen groepen** en daarna **Groepen selecteren die moeten worden opgenomen**. Geef de groep op die u voor Wandera-synchronisatie hebt gemaakt en klik vervolgens op **Selecteren** > **OK** > **OK**. Selecteer **Opslaan** om de groepstoewijzing te voltooien.  
 

## <a name="next-steps"></a>Volgende stappen  
Nadat u de integratie hebt geconfigureerd, kunt u in de Wandera-beheerdersconsole beleid configureren, geavanceerde voorwaardelijke toegang instellen en rapporten bekijken. Voor meer informatie over hoe u Wandera beheert en configureert, raadpleegt u de handleiding [Aan de slag van het ondersteuningscentrum](https://radar.wandera.com/?return_to=https://wandera.force.com/Customer/s/getting-started) in de Wandera-documentatie.  
 
