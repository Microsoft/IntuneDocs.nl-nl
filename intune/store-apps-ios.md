---
title: iOS Store-apps toevoegen aan Microsoft Intune
titlesuffix: 
description: Meer informatie over hoe u iOS Store-apps toevoegt aan Microsoft Intune.
keywords: Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4bd10c4f05204d0e911a7538f5d5133e4a336320
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-add-ios-store-apps-to-microsoft-intune"></a>iOS Store-apps toevoegen aan Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Gebruik de informatie in dit artikel om iOS Store-apps in Microsoft Intune toe te voegen. iOS Store-apps zijn apps die Intune installeert op het apparaat van een gebruiker. De gebruiker maakt deel uit van het personeel van uw bedrijf. iOS Store-apps worden automatisch bijgewerkt.

>[!NOTE]
>Hoewel gebruikers van iOS-apparaten sommige van de ingebouwde iOS-apps, zoals Stocks en Maps, kunnen verwijderen, kunt u Intune niet gebruiken om die apps opnieuw te implementeren. Als eindgebruikers deze apps verwijderen, moeten ze naar de App Store gaan en ze handmatig opnieuw installeren.

## <a name="before-you-start"></a>Voordat u begint

U kunt alleen apps toewijzen met deze methode als ze gratis in de App Store verkrijgbaar zijn. Als u betaalde apps wilt toewijzen met Intune, kunt u overwegen de [Volume Purchase Program-app voor iOS](vpp-apps-ios.md) te gebruiken.

>[!NOTE]
>Chrome en Microsoft Edge zijn de aanbevolen browsers wanneer u met Microsoft Intune werkt.

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies **Mobiele apps** op de blade **Intune**.
4. In de workload **Mobiele apps** kiest u **Apps** in het gedeelte **Beheren**.
5. Kies **Toevoegen** aan de rechterkant van het deelvenster **Apps**.
6. In de lijst **App-type** selecteert u **iOS** bij de beschikbare typen **Store-apps**.
7. Kies **Zoeken in de App Store**.
8. Selecteer in de blade **Zoeken in de App Store** de landinstelling voor de Store.
9. Typ de naam (of een deel daarvan) in het zoekvak. De Store wordt doorzocht met Intune, waarna een lijst met relevante resultaten wordt weergegeven.
10. Kies de gewenste app in de lijst en klik op **Selecteren**.
11. Kies **App-gegevens** op de blade **App toevoegen** om de app te configureren.
12. Voeg op de blade **App-gegevens** de app-gegevens toe. Afhankelijk van de app die u hebt gekozen, worden bepaalde waarden op deze blade mogelijk automatisch ingevuld:
    - **Naam**: typ de naam van de app die u wilt weergeven in de bedrijfsportal. Zorg ervoor dat alle app-namen die u gebruikt, uniek zijn. Als dezelfde app-naam twee keer voorkomt, wordt slechts één van de apps weergegeven voor gebruikers in de bedrijfsportal.
    - **Beschrijving**: typ een beschrijving voor de app die u wilt weergeven voor gebruikers in de bedrijfsportal.
    - **Uitgever**: typ de naam van de uitgever van de app.
    - **URL App Store**: typ de URL naar de App Store voor de app die u wilt maken.
    - **Minimumversie van het besturingssysteem**: selecteer in de lijst de minimumversie van het besturingssysteem waarin de app kan worden geïnstalleerd. De app wordt niet geïnstalleerd op een apparaat met een oudere versie van het besturingssysteem.
    - **Toepasselijk apparaattype**: kies de apparaten waarop de app kan worden geïnstalleerd in de lijst.
    - **Categorie** (optioneel). Selecteer een of meer van de ingebouwde app-categorieën of selecteer een categorie die u hebt gemaakt. Met categorieën kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: hiermee wordt de app duidelijk zichtbaar op de startpagina van de bedrijfsportal wanneer gebruikers naar apps zoeken.
    - **Informatie-URL**: typ de URL van een website die informatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Privacy-URL**: typ de URL van een website die privacyinformatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Ontwikkelaar**: typ de naam van de app-ontwikkelaar (optioneel). Dit veld is alleen zichtbaar voor beheerders en niet voor eindgebruikers.
    - **Eigenaar**: typ de naam van de eigenaar van deze app, bijvoorbeeld **HR-afdeling** (optioneel).  Dit veld is alleen zichtbaar voor beheerders en niet voor eindgebruikers.
    - **Opmerkingen**: typ de opmerkingen die u aan deze app wilt koppelen. Dit veld is alleen zichtbaar voor beheerders en niet voor eindgebruikers.
    - **Logo**: upload een pictogram dat aan de app is gekoppeld. Het pictogram wordt samen met de app weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
13. Wanneer u klaar bent, klikt u op **OK** op de blade **Gegevens toevoegen**.
14. Klik op **Toevoegen** op de blade **App toevoegen**.

De app die u hebt gemaakt, wordt weergegeven in de lijst met apps waar u de app kunt toewijzen aan de groepen die u kiest.

## <a name="next-steps"></a>Volgende stappen

- [Apps aan groepen toewijzen](apps-deploy.md)
