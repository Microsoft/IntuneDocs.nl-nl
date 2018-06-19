---
title: Web-apps aan Microsoft Intune toevoegen
titleSuffix: ''
description: Meer informatie over hoe u web-apps toevoegt aan Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0d62341e35bf851bb429b15a582183bec62a9d4a
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/17/2018
ms.locfileid: "34223387"
---
# <a name="add-web-apps-to-microsoft-intune"></a>Web-apps aan Microsoft Intune toevoegen

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune biedt ondersteuning voor diverse typen apps, waaronder web-apps. Een web-app is een client-/servertoepassing. De server levert de web-app, waaronder de gebruikersinterface, inhoud en functionaliteit. Bovendien bieden moderne webhostingplatformen meestal beveiliging, taakverdeling en andere voordelen. Een web-app wordt afzonderlijk onderhouden op internet. U gebruikt Microsoft Intune om naar dit type app te verwijzen. U wijst ook de groepen gebruikers toe die toegang krijgen tot deze app. 

Voordat u een app kunt beheren en aan uw gebruikers kunt toewijzen, voegt u de app toe aan Intune. Er wordt door Intune een snelkoppeling gemaakt naar de web-app op het beginscherm van het apparaat van de gebruiker.

> [!Note]
> Web-apps worden niet ondersteund op Android for Work-apparaten en macOS.

## <a name="add-a-web-app-to-intune"></a>Een web-app toevoegen aan Intune
Voer de volgende stappen uit om een app toe te voegen aan Intune als een snelkoppeling naar een app op internet:

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services** > **Intune**.  
    Intune bevindt zich in de sectie **Controle en beheer**.
3. Selecteer **Mobiele apps** in het deelvenster **Intune**.
4. Selecteer **Apps** in het werkbelastingvenster **Mobiele apps** onder **Beheren**.
5. Selecteer **Toevoegen** in het deelvenster **Apps**.
6. Selecteer in het deelvenster **App toevoegen** het type **Weblink** in de vervolgkeuzelijst **App-type**.
7. Selecteer **Configureren**.
8. Voeg in het deelvenster **App-gegevens** de volgende gegevens toe:
    - **Naam**: voer de naam van de app in zoals deze in de bedrijfsportal moet worden weergegeven.
    - **Beschrijving**: voer een beschrijving in voor de app. Deze beschrijving wordt voor gebruikers weergegeven in de bedrijfsportal.
    - **Uitgever**: voer de naam in van de uitgever van deze app.
    - **App-URL**: voer de URL in van de website waarop de app wordt gehost die u wilt toewijzen.
    - **Categorie**: selecteer een of meer van de ingebouwde app-categorieën of een categorie die u hebt gemaakt (optioneel). Hiermee kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: selecteer deze instelling om het app-pakket prominent weer te geven op de startpagina van de bedrijfsportal wanneer gebruikers naar apps zoeken.
    - **Een beheerde browser vereisen om deze koppeling te openen**: selecteer deze optie om een koppeling naar een website of web-app aan uw gebruikers toe te wijzen die ze in de door Intune beheerde browser kunnen openen. Deze browser moet op hun apparaat zijn geïnstalleerd.
    - **Logo**: upload een pictogram dat aan de app wordt gekoppeld. Dit pictogram wordt samen met de app weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
9. Selecteer **OK**.
10. Selecteer **Toevoegen** in het deelvenster **App toevoegen**.

> [!Note]
> Gebruikers moeten de Intune-widget toevoegen aan hun beginscherm om web-apps weer te geven die zijn toegewezen aan Android-apparaten.

## <a name="next-steps"></a>Volgende stappen

De app die u hebt gemaakt, wordt weergegeven in de lijst met apps waar u de app kunt toewijzen aan de groepen die u selecteert. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor hulp. 
