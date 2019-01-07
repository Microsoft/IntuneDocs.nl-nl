---
title: iOS Store-apps toevoegen aan Microsoft Intune
titlesuffix: ''
description: Meer informatie over hoe u iOS Store-apps toevoegt aan Microsoft Intune. U kunt op deze manier apps toewijzen als ze gratis in de App Store verkrijgbaar zijn.
keywords: Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 5f1423b0f2f216f65026d2b1a7bf52dda39c9f88
ms.sourcegitcommit: 4e69a8664c289263490daa4c02bc6b81c33196e5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/20/2018
ms.locfileid: "53642503"
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
3. Selecteer in het deelvenster **Intune** de optie **Client-apps**.
4. Selecteer in het workloaddeelvenster **Client-apps** onder **Beheren** de optie **Apps**.
5. Selecteer **Toevoegen** in het deelvenster **Apps**.
6. Selecteer in de lijst **App-type** onder **Store-apps** de optie **iOS**.
7. Selecteer **Zoeken in de App Store**.
8. Selecteer in het deelvenster **Zoeken in de App Store** de landinstelling voor de App Store.
9. Typ de naam van de app (of een deel daarvan) in het **zoekvak**.  
    De Store wordt doorzocht en in Intune wordt een lijst met relevante resultaten weergegeven.
10. Selecteer de gewenste app in de lijst met resultaten en selecteer **Selecteren**.
11. Selecteer in het deelvenster **App toevoegen** de optie **App-gegevens** om de app te configureren.
12. Voeg in het deelvenster **App-gegevens** de app-gegevens toe. Afhankelijk van de app die u hebt gekozen, worden bepaalde waarden in het deelvenster mogelijk automatisch ingevuld:
    - **Naam**: Voer de naam van de app in zoals deze in de bedrijfsportal moet worden weergegeven. Zorg ervoor dat u alleen unieke app-namen gebruikt. Als u twee dezelfde app-namen gebruikt, wordt voor gebruikers slechts één naam in de bedrijfsportal weergegeven.
    - **Beschrijving**: Voer een beschrijving in voor de app. Deze beschrijving wordt voor gebruikers weergegeven in de bedrijfsportal.
    - **Uitgever**: Voer de naam van de uitgever van de app in.
    - **URL App Store**: Typ de URL naar de App Store voor de app die u wilt maken.
    - **Minimumversie van het besturingssysteem**: Selecteer in de lijst de minimumversie van het besturingssysteem waarin de app kan worden geïnstalleerd. Als u de app toewijst aan een apparaat met een lager besturingssysteem, wordt de app niet geïnstalleerd.
    - **Toepasbaar apparaattype**: Selecteer in de lijst de apparaten die door de app worden gebruikt.
    - **Categorie**: Selecteer een of meer ingebouwde app-categorieën of een categorie die u hebt gemaakt (optioneel). Hiermee kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: Selecteer deze optie om het app-pakket prominent weer te geven op de hoofdpagina van de bedrijfsportal wanneer gebruikers naar apps bladeren.
    - **Informatie-URL**: Voer de URL in van een website die informatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Privacy-URL**: (optioneel) Voer de URL in van een website die privacyinformatie over deze app bevat. De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Ontwikkelaar**: Voer de naam in van de app-ontwikkelaar (optioneel). Dit veld is alleen zichtbaar voor beheerders, niet voor uw gebruikers.
    - **Eigenaar**: Voer een naam in voor de eigenaar van deze app, bijvoorbeeld *Hr-afdeling* (optioneel). Dit veld is alleen zichtbaar voor beheerders, niet voor uw gebruikers.
    - **Opmerkingen**: Voer de opmerkingen in die u aan deze app wilt koppelen (optioneel). Dit veld is alleen zichtbaar voor beheerders en niet voor eindgebruikers.
    - **Logo**: Upload een pictogram dat u aan de app wilt koppelen (optioneel). Dit pictogram wordt samen met de app weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
13. Selecteer **OK**.
14. Selecteer **Toevoegen**.

De app die u hebt gemaakt, wordt weergegeven in de lijst met apps waar u de app kunt toewijzen aan de groepen die u selecteert.

## <a name="next-steps"></a>Volgende stappen

- [Apps aan groepen toewijzen](apps-deploy.md)
