---
title: Web-apps toevoegen aan Intune
titleSuffix: ''
description: Meer informatie over hoe u web-apps toevoegt aan Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 45253e061039198aee4aa49b2bf879a1b9929e35
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-web-apps-to-microsoft-intune"></a>Web-apps toevoegen aan Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune biedt ondersteuning voor diverse typen apps, waaronder web-apps. Een web-app is een client-/servertoepassing. De server levert de web-app, waaronder de gebruikersinterface, inhoud en functionaliteit. Bovendien bieden moderne webhostingplatformen meestal beveiliging, taakverdeling en andere voordelen. Een web-app wordt afzonderlijk onderhouden op internet. U gebruikt Microsoft Intune om naar dit type app te verwijzen. U wijst ook de groepen gebruikers toe die toegang krijgen tot deze app. 

Voordat u een app kunt beheren en aan uw gebruikers kunt toewijzen, voegt u de app toe aan Intune. Er wordt door Intune een snelkoppeling gemaakt naar de web-app op het beginscherm van het apparaat van de gebruiker.

> [!Note]
> Web-apps worden niet ondersteund op Android for Work-apparaten en macOS.

Voer de volgende stappen uit om een app toe te voegen aan Intune als een snelkoppeling naar een app op internet:

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Selecteer in het deelvenster **Microsoft Intune** **Mobiele apps**.
4. Selecteert in het deelvenster **Mobiele apps** **Apps**.
5. Selecteer **Toevoegen** boven de lijst met apps. Het deelvenster **App toevoegen** wordt weergegeven.
6. Selecteer in het deelvenster **App toevoegen** het type **Weblink** in de vervolgkeuzelijst **App-type**.
7. Selecteer de optie **Configureren** om het deelvenster **App-gegevens** weer te geven.
8. Voeg in het deelvenster **App-gegevens** de volgende gegevens toe:
    - **Naam**: voer de naam van de app in zoals deze in de bedrijfsportal moet worden weergegeven.
    - **Beschrijving**: voer een beschrijving in voor de app. Deze wordt weergegeven voor eindgebruikers in de bedrijfsportal.
    - **Uitgever**: voer de naam in van de uitgever van deze app.
    - **App-URL**: voer de URL in van de website waarop de app wordt gehost die u wilt toewijzen.
    - **Categorie** (optioneel): selecteer een of meer van de ingebouwde app-categorieën of selecteer een categorie die u hebt gemaakt. Met deze selectie kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: hiermee wordt de app duidelijk zichtbaar op de startpagina van de bedrijfsportal wanneer gebruikers naar apps zoeken.
    - **Een beheerde browser vereisen om deze koppeling te openen**: wanneer u aan gebruikers een koppeling naar een website of web-app toewijst, kunnen ze deze in de door Intune beheerde browser openen. Deze browser moet op hun apparaat zijn geïnstalleerd.
    - **Logo**: upload een logo dat aan de app is gekoppeld. Dit is het logo dat samen met de app wordt weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
9. Wanneer u klaar bent, selecteert u **OK** in het deelvenster **Gegevens toevoegen**.
10. Selecteer vervolgens **Toevoegen** in het deelvenster **App toevoegen**.

> [!Note]
> Gebruikers moeten de Intune-widget toevoegen aan hun beginscherm om web-apps weer te geven die zijn toegewezen aan Android-apparaten.

## <a name="next-steps"></a>Volgende stappen

- De app die u hebt gemaakt, wordt weergegeven in de lijst met apps waar u de app kunt toewijzen aan de groepen die u kiest. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor hulp.