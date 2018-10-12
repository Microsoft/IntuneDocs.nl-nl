---
title: Web-apps aan Microsoft Intune toevoegen
titleSuffix: ''
description: Meer informatie over hoe u web-apps toevoegt aan Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/10/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7e974a17506be36c725dddfa21329269c8fcebc8
ms.sourcegitcommit: 572287c3bb0020b6b75e4e2ac27019c20c699159
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2018
ms.locfileid: "44340266"
---
# <a name="add-web-apps-to-microsoft-intune"></a>Web-apps aan Microsoft Intune toevoegen

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune biedt ondersteuning voor diverse typen apps, waaronder web-apps. Een web-app is een client-/servertoepassing. De server levert de web-app, waaronder de gebruikersinterface, inhoud en functionaliteit. Bovendien bieden moderne webhostingplatformen meestal beveiliging, taakverdeling en andere voordelen. Een web-app wordt afzonderlijk onderhouden op internet. U gebruikt Microsoft Intune om naar dit type app te verwijzen. U wijst ook de groepen gebruikers toe die toegang krijgen tot deze app. 

Voordat u een app kunt beheren en aan uw gebruikers kunt toewijzen, voegt u de app toe aan Intune. Er wordt door Intune een snelkoppeling gemaakt naar de web-app op het beginscherm van het apparaat van de gebruiker.

> [!Note]
> Web-apps worden niet ondersteund op apparaten met een Android-werkprofiel en macOS.

## <a name="add-a-web-app-to-intune"></a>Een web-app toevoegen aan Intune
Voer de volgende stappen uit om een app toe te voegen aan Intune als een snelkoppeling naar een app op internet:

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services** > **Intune**.  
    Intune bevindt zich in de sectie **Controle en beheer**.
3. Selecteer in het deelvenster **Intune** de optie **Client-apps**.
4. Selecteer in het workloaddeelvenster **Client-apps** onder **Beheren** de optie **Apps**.
5. Selecteer **Toevoegen** in het deelvenster **Apps**.
6. Selecteer in het deelvenster **App toevoegen** het type **Weblink** in de vervolgkeuzelijst **App-type**.
7. Selecteer **Configureren**.
8. Voeg in het deelvenster **App-gegevens** de volgende gegevens toe:
    - **Naam**: voer de naam van de app in zoals deze in de bedrijfsportal moet worden weergegeven. 
    
        > [!NOTE]
        > Als u de naam van de app wijzigt via Intune Azure Portal nadat u de app hebt geïnstalleerd en geïmplementeerd, kunt u geen beleid meer richten op de app met behulp van opdrachten.
    
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
>
> Momenteel wordt de implementatie van Intune-web-apps op iOS-apparaten gekoppeld aan het beheerprofiel; dit kan niet handmatig worden verwijderd. U kunt het implementatietype in de Intune-portal wijzigen in **Verwijderen**. Daarna kunt u de web-app automatisch verwijderen. Als u de implementatie echter verwijdert voordat u de intentie van de app-toewijzing hebt gewijzigd in **Verwijderen**, bevindt de web-app zich permanent op het apparaat de registratie van het apparaat bij Intune ongedaan wordt gemaakt.

## <a name="next-steps"></a>Volgende stappen

De app die u hebt gemaakt, wordt weergegeven in de lijst met apps waar u de app kunt toewijzen aan de groepen die u selecteert. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor hulp. 
