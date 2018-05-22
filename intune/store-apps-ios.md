---
title: iOS Store-apps toevoegen aan Microsoft Intune
titlesuffix: ''
description: Meer informatie over hoe u iOS Store-apps toevoegt aan Microsoft Intune.
keywords: Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ac96c66dd6f09a7bd7a1b1c8c37f2f0eda24828c
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/17/2018
---
# <a name="add-ios-store-apps-to-microsoft-intune"></a>iOS Store-apps toevoegen aan Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Gebruik de informatie in dit artikel om iOS Store-apps in Microsoft Intune toe te voegen. iOS Store-apps zijn apps die Intune installeert op de apparaten van uw gebruiker. Een gebruiker maakt deel uit van het personeel van uw bedrijf. iOS Store-apps worden automatisch bijgewerkt.

>[!NOTE]
>Hoewel gebruikers van iOS-apparaten sommige ingebouwde iOS-apps, zoals Stocks en Maps, kunnen verwijderen, kunt u Intune niet gebruiken om die apps opnieuw te implementeren. Als uw gebruikers deze apps verwijderen, moeten ze naar de App Store gaan en ze handmatig opnieuw installeren.

## <a name="before-you-start"></a>Voordat u begint

U kunt apps alleen met deze methode toewijzen als ze gratis verkrijgbaar zijn in de App Store. Als u betaalde apps met Intune wilt toewijzen, kunt u overwegen om het [Volume Purchase Program voor iOS](vpp-apps-ios.md) te gebruiken.

>[!NOTE]
>Als u met Microsoft Intune werkt, kunt u beter de Microsoft Edge- of Google Chrome-browser gebruiken.

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services** > **Intune**.  
    Intune bevindt zich in de sectie **Controle en beheer**.
3. Selecteer **Mobiele apps** in het deelvenster **Intune**.
4. Selecteer **Apps** in het werkbelastingvenster **Mobiele apps** onder **Beheren**.
5. Selecteer **Toevoegen** in het deelvenster **Apps**.
6. Selecteer in de lijst **App-type** onder **Store-apps** de optie **iOS**.
7. Selecteer **Zoeken in de App Store**.
8. Selecteer in het deelvenster **Zoeken in de App Store** de landinstelling voor de App Store.
9. Typ de naam van de app (of een deel daarvan) in het **zoekvak**.  
    De Store wordt doorzocht en in Intune wordt een lijst met relevante resultaten weergegeven.
10. Selecteer de gewenste app in de lijst met resultaten en selecteer **Selecteren**.
11. Selecteer in het deelvenster **App toevoegen** de optie **App-gegevens** om de app te configureren.
12. Voeg in het deelvenster **App-gegevens** de app-gegevens toe. Afhankelijk van de app die u hebt gekozen, worden bepaalde waarden in het deelvenster mogelijk automatisch ingevuld:
    - **Naam**: voer de naam van de app in zoals deze in de bedrijfsportal moet worden weergegeven. Zorg ervoor dat u alleen unieke app-namen gebruikt. Als u twee dezelfde app-namen gebruikt, wordt voor gebruikers slechts één naam in de bedrijfsportal weergegeven.
    - **Beschrijving**: voer een beschrijving in voor de app. Deze beschrijving wordt voor gebruikers weergegeven in de bedrijfsportal.
    - **Uitgever**: voer de naam van de uitgever van de app in.
    - **URL App Store**: typ de URL naar de App Store voor de app die u wilt maken.
    - **Minimumversie van het besturingssysteem**: selecteer in de lijst de minimumversie van het besturingssysteem waarin de app kan worden geïnstalleerd. Als u de app toewijst aan een apparaat met een lager besturingssysteem, wordt de app niet geïnstalleerd.
    - **Toepasselijk apparaattype**: selecteer in de lijst de apparaten die door de app worden gebruikt.
    - **Categorie**: selecteer een of meer van de ingebouwde app-categorieën of een categorie die u hebt gemaakt (optioneel). Hiermee kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: selecteer deze instelling om het app-pakket prominent weer te geven op de startpagina van de bedrijfsportal wanneer gebruikers naar apps zoeken.
    - **Informatie-URL**: voer de URL in van een website die informatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Privacy-URL**: voer de URL in van een website die privacyinformatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Ontwikkelaar**: voer de naam in van de app-ontwikkelaar (optioneel). Dit veld is alleen zichtbaar voor beheerders, niet voor uw gebruikers.
    - **Eigenaar**: voer een naam in voor de eigenaar van deze app, bijvoorbeeld *HR-afdeling* (optioneel). Dit veld is alleen zichtbaar voor beheerders, niet voor uw gebruikers.
    - **Opmerkingen**: voer de opmerkingen in die u aan deze app wilt koppelen (optioneel). Dit veld is alleen zichtbaar voor beheerders en niet voor eindgebruikers.
    - **Pictogram**: upload een pictogram dat aan de app wordt gekoppeld (optioneel). Dit pictogram wordt samen met de app weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
13. Selecteer **OK**.
14. Selecteer **Toevoegen**.

De app die u hebt gemaakt, wordt weergegeven in de lijst met apps waar u de app kunt toewijzen aan de groepen die u selecteert.

## <a name="next-steps"></a>Volgende stappen

- [Apps aan groepen toewijzen](apps-deploy.md)
